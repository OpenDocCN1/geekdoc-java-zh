![](images/00046.jpeg)

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
### VOLUME Ⅱ
SHAPE DRAWING TOOLS
in Java 8 (JDK 8u66)

 |

|  
## JavaFX 8 Tutorial

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

*   [ABOUT THE AUTHORS](#part0003.html_2RHM0-4cbb8f9352704a549e363e38a5243855)
*   [ACKNOWLEDGMENT](#part0004.html_3Q280-4cbb8f9352704a549e363e38a5243855)
*   [PREFACE](#part0005_split_000.html_4OIQ0-4cbb8f9352704a549e363e38a5243855)
    *   [How this book is organized](#part0005_split_001.html_how-this-book-organize)
    *   [Why Choose This Book](#part0005_split_002.html_why-choose-this-book)
    *   [What You Need for This Book](#part0005_split_003.html_what-you-need)
*   [**INTRODUCTION**](#part0006_split_000.html_5N3C0-4cbb8f9352704a549e363e38a5243855)
*   VOLUME Ⅱ: DEVELOPING INTERACTIVE SHAPE DRAWING TOOLS
    *   [**Chapter 1**: Line Drawer](#part0007_split_000.html_6LJU0-4cbb8f9352704a549e363e38a5243855)

        Draw lines from mouse events on a drawing board.

        *   [1.1 Create `LineDrawer` Class as Subclass of `Application`](#part0007_split_001.html_create-line-drawer)
            *   [1.1.1 Add `Pane` as Drawing Board in the Center of `BorderPane`](#part0007_split_001.html_pane-as-drawing-board)
        *   [1.2 Register Event Handlers to Handle Mouse Events and Key Events](#part0007_split_002.html_handle-mouse-event-key-event)
            *   [1.2.1 Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key)
        *   [1.3 Properties and Binding in `LineDrawer` Class](#part0007_split_002.html_properties-binding)
            *   [1.3.1 Define Properties to Hold Locations of Mouse Events](#part0007_split_003.html_properties-for-mouse-locations)
            *   [1.3.2 Define `ObjectProperty<Shape>` to Hold a Sketch](#part0007_split_003.html_define-property-shape)
            *   [1.3.3 Bind Properties for the Ending Point of Line](#part0007_split_003.html_bind-end-point)
        *   [1.4 Get Key Code of Key Event](#part0007_split_004.html_key-code-key-event)
        *   [1.5 Complete Source Codes of `LineDrawer` class](#part0007_split_005.html_complete-source-codes)
        *   [1.6 Summary](#part0007_split_006.html_summary)
    *   [**Chapter 2**: Polyline Drawer](#part0008_split_000.html_7K4G0-4cbb8f9352704a549e363e38a5243855)

        Draw polylines from mouse events on a drawing board.

        *   [2.1 Create `PolylineDrawer` Class as Subclass of `Application`](#part0008_split_001.html_create-polyline-drawer)
            *   [2.1.1 Create an Instance of `Polyline`](#part0008_split_001.html_create-polyline)
            *   [2.1.2 Define `ObjectProperty<Line>` to Hold a Temperary Line](#part0008_split_001.html_define-line-property)
            *   [2.1.3 Implement `onMouseDragStarted()` method](#part0008_split_001.html_implement-on-mouse-drag-started)
            *   [2.1.4 Implement `onMouseDragFinished()` method](#part0008_split_001.html_implement-on-mouse-drag-finished)
        *   [2.2 Complete Source Codes of `PolylineDrawer` class](#part0008_split_002.html_complete-source-codes)
        *   [2.3 Summary](#part0008_split_003.html_summary)
    *   [**Chapter 3**: Polygon Drawer](#part0009_split_000.html_8IL20-4cbb8f9352704a549e363e38a5243855)

        Draw polygons from mouse events on a drawing board.

        *   [3.1 Create `PolygonDrawer` Class as Subclass of `Application`](#part0009_split_001.html_create-polygon-drawer)
            *   [3.1.1 Create an Instance of `Polygon`](#part0009_split_001.html_create-polygon)
        *   [3.2 Complete Source Codes of `PolygonDrawer` class](#part0009_split_002.html_complete-source-codes)
        *   [3.3 Summary](#part0009_split_003.html_summary)
    *   [**Chapter 4**: Path Drawer](#part0010_split_000.html_9H5K0-4cbb8f9352704a549e363e38a5243855)

        Draw paths from mouse events on a drawing board.

        *   [4.1 Create `PathDrawer` Class as Subclass of `Application`](#part0010_split_001.html_create-path-drawer)
            *   [4.1.1 Create an Instance of `Path`](#part0010_split_001.html_create-path)
            *   [4.1.2 Implement `onMouseDragStarted()` Method](#part0010_split_001.html_implement-on-mouse-darg-started)
            *   [4.1.3 Implement `OnMouseDragFinished()` method](#part0010_split_001.html_implement-on-mouse-darg-finished)
*   [4.2 Complete Source Codes of `PathDrawer` class](#part0010_split_002.html_complete-source-codes)
*   [4.3 Summary](#part0010_split_003.html_summary)

[**Chapter 5**: Quadratic Bézier Curve Drawer](#part0011_split_000.html_AFM60-4cbb8f9352704a549e363e38a5243855)

Draw paths composed of quadratic Bézier curves from mouse events on a drawing board.

*   [5.1 Create `BezierCurveDrawer` Class as Subclass of `Application`](#part0011_split_001.html_create-bezier-curve-drawer)
    *   [5.1.1 Introduce Quadratic Bézier Curves](#part0011_split_001.html_intro-quad-curve)
    *   [5.1.2 Register Event Handler of Mouse Dragged Event](#part0011_split_001.html_register-mouse-dragged-event)
    *   [5.1.3 Register Event Handler of Mouse Released Event](#part0011_split_001.html_register-mouse-released-event)
*   [5.2 Implement `handleMouseClicked(Pane` pane`)` method](#part0011_split_002.html_handle-mouse-clicked)
    *   [5.2.1 Add `MoveTo` Element to `Path`](#part0011_split_002.html_add-move-to)
    *   [5.2.2 Draw Circles to Represent Control Points of a Quadratic Bézier Curve](#part0011_split_002.html_draw-circles)
*   [5.3 Implement `onMouseDragStarted(Pane` pane`)` method](#part0011_split_003.html_implement-on-mouse-darg-started)
    *   [5.3.1 Add Straight Line `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-line-to)
    *   [5.3.2 Add Normal `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-quad-curve-to)
*   [5.4 Implement `OnMouseDragFinished(Pane` pane`)` method](#part0011_split_004.html_implement-on-mouse-darg-finished)
*   [5.5 Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event)
    *   [5.5.1 Implement `deleteLastPathElement(Pane` pane`, Path` path`)` Method](#part0011_split_005.html_implement-delete-last-element)
*   [5.6 The Complete Source Codes of `BezierCurveDrawer` class](#part0011_split_006.html_complete-source-codes)
*   [5.7 Summary](#part0011_split_007.html_summary)

[**Chapter 6**: Basic Draw Tool](#part0012_split_000.html_BE6O0-4cbb8f9352704a549e363e38a5243855)

Create integral classes in a package named `drawtool` to facilitate developments of various shape drawers -- Rectangle Drawer, Circle Drawer and Ellipse Drawer.

*   [6.1 Create `ShapeDrawer` Class](#part0012_split_001.html_create-shape-drawer)
    *   [6.1.1 Define Properties](#part0012_split_001.html_define-properties-shape-drawer)
    *   [6.1.2 Define Methods](#part0012_split_001.html_define-methods-shape-drawer)
    *   [6.1.3 Complete Source Codes of `ShapeDrawer` class](#part0012_split_001.html_complete-source-codes-shape-drawer)
*   [6.2 Create `DrawPane` Class](#part0012_split_002.html_create-draw-pane)
    *   [6.2.1 Define Properties](#part0012_split_002.html_define-properties-draw-pane)
    *   [6.2.2 Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers)
    *   [6.2.3 Define `drawOnMouseDragged` Method](#part0012_split_002.html_define-draw-on-mouse-dragged)
    *   [6.2.4 Take Default Actions for `ENTER` Key, `ESCAPE` Key and `DELETE` Key](#part0012_split_002.html_handle-key-codes)
    *   [6.2.5 Define Constructor with a Parameter of Type `ShapeDrawer`](#part0012_split_002.html_constructor-with-arg)
    *   [6.2.6 Complete Source Codes of `DrawPane` class](#part0012_split_002.html_complete-source-codes-draw-pane)
*   [6.3 Develop Drawer Applications Using Draw Tool APIs](#part0012_split_003.html_develop-drawers)
    *   [6.3.1 Create `RectangleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-rectangle-drawer-class)
    *   [6.3.2 Create `CircleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-circle-drawer-class)
    *   [6.3.3 Create `EllipseDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-ellipse-drawer-class)
*   [6.4 Summary](#part0012_split_004.html_summary)

[**Chapter 7**: Enhanced Draw Tool with Predefined Drawers](#part0013_split_000.html_CCNA0-4cbb8f9352704a549e363e38a5243855)

Enhance `drawtool` package and implement a variety of drawers, reside in `drawtool.drawer` package, containing predefined shape drawers -- LineDrawer, PolylineDrawer, PolygonDrawer, PathDrawer, BazierCurveDrawer, RectangleDrawer, CircleDrawer, EllipseDrawer, and ShapeMover -- which are subclasses of `ShapeDrawer`.

*   [7.1 Enhance `ShapeDrawer` Class](#part0013_split_001.html_enhance-shape-drawer)
    *   [7.1.1 Define Shape Rendering Properties](#part0013_split_001.html_define-shape-properties)
    *   [7.1.2 Define a Boolean Property `polySegment`](#part0013_split_001.html_define-poly-segment)
    *   [7.1.3 Complete Source Codes of Enhanced `ShapeDrawer` class](#part0013_split_001.html_complete-source-codes-shape-drawer)
*   [7.2 Create Subclasses of `ShapeDrawer`](#part0013_split_002.html_create-subclasses-shape-drawer)
    *   [7.2.1 Implement `LineDrawer` Class](#part0013_split_002.html_implement-line-drawer)
        *   [7.2.1.1 Create Line Drawer App](#part0013_split_002.html_create-line-drawer-app)
    *   [7.2.2 Implement `PolylineDrawer` Class](#part0013_split_002.html_implement-polyline-drawer)
        *   [7.2.2.1 Create Polyline Drawer App](#part0013_split_002.html_create-polyline-drawer-app)
    *   [7.2.3 Implement `PolygonDrawer` Class](#part0013_split_002.html_implement-polygon-drawer)
        *   [7.2.3.1 Create Polygon Drawer App](#part0013_split_002.html_create-polygon-drawer-app)
    *   [7.2.4 Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer)
        *   [7.2.4.1 Create Path Drawer App](#part0013_split_002.html_create-path-drawer-app)
    *   [7.2.5 Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer)
        *   [7.2.5.1 Create Bezier Curve Drawer App](#part0013_split_002.html_create-bezier-curve-drawer-app)
    *   [7.2.6 Implement `RectangleDrawer` Class](#part0013_split_002.html_implement-rectangle-drawer)
        *   [7.2.6.1 Create Rectangle Drawer App](#part0013_split_002.html_create-rectangle-drawer-app)
    *   [7.2.7 Implement `CircleDrawer` Class](#part0013_split_002.html_implement-circle-drawer)
        *   [7.2.7.1 Create Circle Drawer App](#part0013_split_002.html_create-circle-drawer-app)
    *   [7.2.8 Implement `EllipseDrawer` Class](#part0013_split_002.html_implement-ellipse-drawer)
        *   [7.2.8.1 Create Ellipse Drawer App](#part0013_split_002.html_create-ellipse-drawer-app)
    *   [7.2.9 Implement `ShapeMover` Class](#part0013_split_002.html_implement-shape-mover)
*   [7.3 Enhance `DrawPane` Class](#part0013_split_003.html_enhance-draw-pane)
*   [7.4 Summary](#part0013_split_004.html_summary)

[**Chapter 8**: Initial `JFXDrawTools` Application](#part0014_split_000.html_DB7S0-4cbb8f9352704a549e363e38a5243855)

Develop initial version of `JFXDrawTools` by integrating with all predefined shape drawers as well as utilizing enhanced shape drawing APIs available at this stage in `drawtool` package.

*   [8.1 Create Skeleton of `JFXDrawTools`](#part0014_split_001.html_create-skeleton)
    *   [8.1.1 Create `JFXDrawTools` Class as Subclass of Application](#part0014_split_001.html_create-jfx-draw-tools-class)
    *   [8.1.2 Create Status Bar](#part0014_split_001.html_create-status-bar)
    *   [8.1.3 Create Menu Bar](#part0014_split_001.html_create-menu-bar)
    *   [8.1.4 Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator)
    *   [8.1.5 Define Enumeration Type `DrawTools`](#part0014_split_001.html_define-enum-draw-tools)
    *   [8.1.6 Complete Source Codes of Skeleton of `JFXDrawTools` Class](#part0014_split_001.html_complete-source-codes-skeleton)
*   [8.2 Create Instances of Shape Drawers](#part0014_split_002.html_create-drawers)
    *   [8.2.1 Activate Drawer for a Draw Pane](#part0014_split_002.html_activate-drawer)
*   [8.3 Complete Source Codes of `JFXDrawTools` Class](#part0014_split_003.html_complete-source-codes-jfx-draw-tools)
*   [8.4 Summary](#part0014_split_004.html_summary)

[EPILOGUE](#part0015.html_E9OE0-4cbb8f9352704a549e363e38a5243855)

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

This book is VOLUME Ⅱ of the book series, `Coding in JavaFX Step by Step Build Graphics Toolkit`. Since contents are abundant and unfeasible to be managed into one book, chapters are organized among volumes:

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

### Contents of VOLUME Ⅱ

Let's glance at the contents of VOLUME Ⅱ:

*   [**Chapter 1**: Line Drawer](#part0007_split_000.html_6LJU0-4cbb8f9352704a549e363e38a5243855)

    Draw lines from mouse events on a drawing board.

    *   [1.1 Create `LineDrawer` Class as Subclass of `Application`](#part0007_split_001.html_create-line-drawer)
    *   [1.2 Register Event Handlers to Handle Mouse Events and Key Events](#part0007_split_002.html_handle-mouse-event-key-event)
    *   [1.3 Properties and Binding in `LineDrawer` Class](#part0007_split_002.html_properties-binding)
    *   [1.4 Get Key Code of Key Event](#part0007_split_004.html_key-code-key-event)
    *   [1.5 Complete Source Codes of `LineDrawer` class](#part0007_split_005.html_complete-source-codes)
    *   [1.6 Summary](#part0007_split_006.html_summary)
*   [**Chapter 2**: Polyline Drawer](#part0008_split_000.html_7K4G0-4cbb8f9352704a549e363e38a5243855)

    Draw polylines from mouse events on a drawing board.

    *   [2.1 Create `PolylineDrawer` Class as Subclass of `Application`](#part0008_split_001.html_create-polyline-drawer)
    *   [2.2 Complete Source Codes of `PolylineDrawer` class](#part0008_split_002.html_complete-source-codes)
    *   [2.3 Summary](#part0008_split_003.html_summary)
*   [**Chapter 3**: Polygon Drawer](#part0009_split_000.html_8IL20-4cbb8f9352704a549e363e38a5243855)

    Draw polygons from mouse events on a drawing board.

    *   [3.1 Create `PolygonDrawer` Class as Subclass of `Application`](#part0009_split_001.html_create-polygon-drawer)
    *   [3.2 Complete Source Codes of `PolygonDrawer` class](#part0009_split_002.html_complete-source-codes)
    *   [3.3 Summary](#part0009_split_003.html_summary)
*   [**Chapter 4**: Path Drawer](#part0010_split_000.html_9H5K0-4cbb8f9352704a549e363e38a5243855)

    Draw paths from mouse events on a drawing board.

    *   [4.1 Create `PathDrawer` Class as Subclass of `Application`](#part0010_split_001.html_create-path-drawer)
*   [4.2 Complete Source Codes of `PathDrawer` class](#part0010_split_002.html_complete-source-codes)
*   [4.3 Summary](#part0010_split_003.html_summary)

[**Chapter 5**: Quadratic Bézier Curve Drawer](#part0011_split_000.html_AFM60-4cbb8f9352704a549e363e38a5243855)

Draw paths composed of quadratic Bézier curves from mouse events on a drawing board.

*   [5.1 Create `BezierCurveDrawer` Class as Subclass of `Application`](#part0011_split_001.html_create-bezier-curve-drawer)
*   [5.2 Implement `handleMouseClicked(Pane` pane`)` method](#part0011_split_002.html_handle-mouse-clicked)
*   [5.3 Implement `onMouseDragStarted(Pane` pane`)` method](#part0011_split_003.html_implement-on-mouse-darg-started)
*   [5.4 Implement `OnMouseDragFinished(Pane` pane`)` method](#part0011_split_004.html_implement-on-mouse-darg-finished)
*   [5.5 Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event)
*   [5.6 The Complete Source Codes of `BezierCurveDrawer` class](#part0011_split_006.html_complete-source-codes)
*   [5.7 Summary](#part0011_split_007.html_summary)

[**Chapter 6**: Basic Draw Tool](#part0012_split_000.html_BE6O0-4cbb8f9352704a549e363e38a5243855)

Create integral classes in a package named `drawtool` to facilitate developments of various shape drawers -- Rectangle Drawer, Circle Drawer and Ellipse Drawer.

*   [6.1 Create `ShapeDrawer` Class](#part0012_split_001.html_create-shape-drawer)
*   [6.2 Create `DrawPane` Class](#part0012_split_002.html_create-draw-pane)
*   [6.3 Develop Drawer Applications Using Draw Tool APIs](#part0012_split_003.html_develop-drawers)
*   [6.4 Summary](#part0012_split_004.html_summary)

[**Chapter 7**: Enhanced Draw Tool with Predefined Drawers](#part0013_split_000.html_CCNA0-4cbb8f9352704a549e363e38a5243855)

Enhance `drawtool` package and implement a variety of drawers, reside in `drawtool.drawer` package, containing predefined shape drawers -- LineDrawer, PolylineDrawer, PolygonDrawer, PathDrawer, BazierCurveDrawer, RectangleDrawer, CircleDrawer, EllipseDrawer, and ShapeMover -- which are subclasses of `ShapeDrawer`.

*   [7.1 Enhance `ShapeDrawer` Class](#part0013_split_001.html_enhance-shape-drawer)
*   [7.2 Create Subclasses of `ShapeDrawer`](#part0013_split_002.html_create-subclasses-shape-drawer)
*   [7.3 Enhance `DrawPane` Class](#part0013_split_003.html_enhance-draw-pane)
*   [7.4 Summary](#part0013_split_004.html_summary)

[**Chapter 8**: Initial `JFXDrawTools` Application](#part0014_split_000.html_DB7S0-4cbb8f9352704a549e363e38a5243855)

Develop initial version of `JFXDrawTools` by integrating with all predefined shape drawers as well as utilizing enhanced shape drawing APIs available at this stage in `drawtool` package.

*   [8.1 Create Skeleton of `JFXDrawTools`](#part0014_split_001.html_create-skeleton)
*   [8.2 Create Instances of Shape Drawers](#part0014_split_002.html_create-drawers)
*   [8.3 Complete Source Codes of `JFXDrawTools` Class](#part0014_split_003.html_complete-source-codes-jfx-draw-tools)
*   [8.4 Summary](#part0014_split_004.html_summary)

Figure 1. Snapshot of the JFXDrawTools V1.0 application in JavaFX 8

![](images/00001.jpeg "jfx_draw_tools_1_0.jpg")

## Why Choose This Book

This book is for software developers who are interested in developing GUIs using JavaFX library for rich client applications.

Important features in JavaFX are illustrated by step-by-step development of real world Java applications.

Instructive diagrams are used to help readers capture abstract concepts instantly. And all diagrams used in each chapter are created using the graphics tools developed in this book series.

The book series is for you if you are:

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

![](images/00002.jpeg "javafx_app_guis.jpg")

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
Line Drawer
--Developing Line Drawer V1.0

## Preface

In this chapter, we'll develop a drawing module that interactively creates JavaFX `Line` objects through mouse dragged events. By gradually enhance its capabilities, at the final phase it will be integrated into a comprehensive JavaFX `Shape` drawing application, `JFXDrawTools V1.x`. From detailed descriptions and well-documented example codes excerpted from Line Drawer V1.0, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0007_split_006.html_summary) section.

The complete development process of `Line Drawer V1.0` is characterized by the following steps:

*   [1.1 Create `LineDrawer` Class as Subclass of `Application`](#part0007_split_001.html_create-line-drawer)
    *   [1.1.1 Add `Pane` as Drawing Board in the Center of `BorderPane`](#part0007_split_001.html_pane-as-drawing-board)
*   [1.2 Register Event Handlers to Handle Mouse Events and Key Events](#part0007_split_002.html_handle-mouse-event-key-event)
    *   [1.2.1 Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key)
*   [1.3 Properties and Binding in `LineDrawer` Class](#part0007_split_002.html_properties-binding)
    *   [1.3.1 Define Properties to Hold Locations of Mouse Events](#part0007_split_003.html_properties-for-mouse-locations)
    *   [1.3.2 Define `ObjectProperty<Shape>` to Hold a Sketch](#part0007_split_003.html_define-property-shape)
    *   [1.3.3 Bind Properties for the Ending Point of Line](#part0007_split_003.html_bind-end-point)
*   [1.4 Get Key Code of Key Event](#part0007_split_004.html_key-code-key-event)
*   [1.5 Complete Source Codes of `LineDrawer` class](#part0007_split_005.html_complete-source-codes)
*   [1.6 Summary](#part0007_split_006.html_summary)

## 1.1 Create `LineDrawer` Class as Subclass of `Application`

`Line` class, resides in `javafx.scene.shape package`, is one of direct subclasses of `Shape` class that provides APIs for rendering 2D geometric primitives.

To have an insight into the features of JavaFX `Shape` class, please read the descriptions from the section [2D Geometric Primitives and `Text` Are JavaFX Nodes](#part0006_split_005.html_2d-geometric-primitives-text) of [INTRODUCTION](#part0006_split_000.html_5N3C0-4cbb8f9352704a549e363e38a5243855), and further more, from VOLUME Ⅰ: DEVELOPING IMAGE VIEWING COMPONENTS Chapter 2 Enhanced Image Viewer with Browsing Buttons Section 2.1 Add Next Button, in which we demonstrate how to design visual objects using shapes like `Polygon` and `Rectangle`.

The following properties are defined in `Line` class:

*   `startX`

    It's a property of type `DoubleProperty` to specify the X coordinate of start point of a `Line`.

*   `startY`

    It's a property of type `DoubleProperty` to specify the Y coordinate of start point of a `Line`.

*   `endX`

    It's a property of type `DoubleProperty` to specify the X coordinate of end point of a `Line`.

*   `endY`

    It's a property of type `DoubleProperty` to specify the Y coordinate of end point of a `Line`.

To create an operable `Line` object, values for the above properties must be specified since their default values are `0.0`.

Here's an example to create a hard-coded `Line` object:

Import Statements:

```
 import javafx.scene.shape.Line;
```

Listing 1-1. Create a `Line` with start point at (120, 120) and end point at (360, 360):

```
 Line line = new Line(120.0f, 120.0f, 360.0f, 360.0f);
```

Here's another way to create the same `Line` object:

Listing 1-2. Create a `Line` with start point at (120, 120) and end point at (360, 360):

```
 Line line = new Line();
  line.setStartX(120.0f);
  line.setStartY(120.0f);
  line.setEndX(360.0f);
  line.setEndY(360.0f);
```

The `Shape` class provides APIs to render a sketch with a variety of style; we'll use this method:

```
 public final ObservableList<Double> getStrokeDashArray()
```

to specify a dash pattern, given a sequence of double value representing a length of dash followed by a length of space.

Following is the example of creating a dash line with line width set to 4.0 pixels.

Listing 1-3. Create a dash line with start point at (120, 120) and end point at (360, 360), and stroke width set to 4.0 pixels:

```
 Line line = new Line();
    line.setStartX(120.0f);
    line.setStartY(120.0f);
    line.setEndX(360.0f);
    line.setEndY(360.0f);
    // Set lengths of dash and space in pixels
    // 16 for dash, 8 for space, 2 for dash, 8 for dash
    // then repeat the pattern
    line.getStrokeDashArray().addAll(16.0, 8.0, 2.0, 8.0);
    line.setStrokeWidth(4.0);
```

The following snapshot shows the rendering of a `Line` from above codes:

Figure 1-1. Snapshot of a dash line from above codes

![](images/00003.jpeg "dash_line.jpg")

Now, we'll demonstrate how to develop a `LineDrawer` application that interactively draws `Line` objects. The (X, Y) coordinates for both start point and end point of a line are obtained dynamically through mouse pressed and mouse dragged events.

Eventually this simple module will evolve into a sophisticated drawing tool handling not only `Line` object, but also `Polyline`, `Polygon`, `Path`, `circle`, etc.

### 1.1.1 Add `Pane` as Drawing Board in the Center of `BorderPane`

In VOLUME Ⅰ: DEVELOPING IMAGE VIEWING COMPONENTS Chapter 1 Basic Image Viewer Section 1.1 Create ImageViewer Class as Subclass of Application, we have revealed the capabilities of `BorderPane` class; it's one of build-in layout panes, resided in `javafx.scene.layout` package and a direct subclass of `javafx.scene.layout.Pane` class.

Similar to the `ImageViewer` application, the `LineDrawer` application employs a `BorderPane` as the root node of a scene graph, and places a `Pane` in the center of `BorderPane` as a sketch drawing board.

The following is a partial descendant tree of `Node` class, illustrating the relation of `Parent` to `Pane`, `Group`, and other containers.

Figure 1-2. Diagram of a partial descendant tree of `Node` class showing where the `Pane` is located

![](images/00004.jpeg "class_tree.png")

`Pane` class, a direct subclass of `Region,` resides in `javafx.scene.layout` package, is the base class of JavaFX build-in layout panes. First of all, we'll explore reasons why we employ `Pane` class as our sketch drawing board.

Developing an interactive drawing tool for rendering objects at the mouse pointed locations requires a container that fulfils two basic conditions as follows:

1.  It does not automatically layout its children.
2.  It provides the `getChildren()` method for adding as many nodes as needed.

The `Group` class, a direct subclass of `javafx.scene.Parent`, resided in `javafx.scene` package, also fulfills these two conditions; however, it is not feasible to engage a `Group` as our drawing board. A `Group` is un-resizable by its parent, and its bounds is entirely determined by bounds of its contents. When the application is launched, the container for sketches is empty. And a `Group` without any child node in it does not occupy any space in a scene, thus, is unable to receive events.

An empty `Pane` doesn't cause the same kind of problem as an empty `Group` does. In our case, when the application starts, the `Pane`'s boundary is calculated by its parent node which is a `BorderPane`, the root node of a scene. Initially, the scene's size is set to 600 pixels by 400 pixels, the `Pane` is the only child of the root node, and is resized to the same size as the scene.

Following is the initial appearance of `LineDrawer` class, creating a `BorderPane` as the root of a `Scene`, and placing a `Pane` in the center of `BorderPane`:

Listing 1-4. Create `LineDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of `Scene`, and place `Pane` in the center of `BorderPane` as drawing board:

```
 package drawtool;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: LineDrawer.java
 * @author: Shufen Kuo
 *
 */
public class LineDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("LineDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

To gain an insight into `Scene`, `Stage` and `Application`, please refer to VOLUME Ⅰ: DEVELOPING IMAGE VIEWING COMPONENTS Chapter 1 Basic Image Viewer Section 1.1 Create ImageViewer Class as Subclass of Application.

## 1.2 Register Event Handlers to Handle Mouse Events and Key Events

An effective yet simple approach is taken to draw lines, using mouse dragging around a `Pane`, the drawing board. Here's a preview of how it works:

When the mouse is pressed, we obtain x location and y location of the event, that will become the start point of a line to be created. When the first mouse dragged event that immediately follows the mouse pressed event occurs, a temporary `Line` object is created, and the previously obtained location is set as the start point of the line. And while the mouse being dragged around the drawing board, the end point of the line is continuously adjusted in accordance with the latest mouse dragged location, using Properties and Binding mechanism. The drawing of this temporary line is completed when a mouse released event occurs to end the sequence of mouse dragged events.

Repeat MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle until you are satisfied with the rendering of this line. Hit ESCAPE key to cancel this line, and hit ENTER key to finalize this line. Once ENTER key is hit, the line exists forever on the drawing board, the next MOUSE_PRESSED event will start a new line.

In the final version of a sketch drawing application, `JFXDrawTools`, we'll implement `Delete` action to erase selected existing sketches, and `Show Properties` action to update available properties of a sketch.

### 1.2.1 Register Event Handlers Using Convenience Methods

The following convenience methods, provided in `Node` class, are used to register event handlers for the mentioned events:

*   `public final void setOnMousePressed(EventHandler<? super MouseEvent>` value`)`

    Set value of `OnMousePressed` property defined in `Node` class, providing the implementation of `handle` method, which is called when mouse is pressed on this node.

*   `public final void setOnMouseDragged(EventHandler<? super MouseEvent>` value`)`

    Set value of `OnMouseDragged` property defined in `Node` class, providing the implementation of `handle` method, which is called when mouse is dragged on this node.

*   `public final void setOnMouseReleased(EventHandler<? super MouseEvent>` value`)`

    Set value of `OnMouseReleased` property defined in `Node` class, providing the implementation of `handle` method, which is called when mouse is released on this node.

*   `public final void setOnKeyPressed(EventHandler<? super KeyEvent>` value`)`

    Set value of `OnKeyPressedd` property defined in `Node` class, providing the implementation of `handle` method, which is called when key is pressed on this node.

Following snippets of codes show how to register event handlers to handle `MOUSE_PRESSED`, `MOUSE_DRAGGED`, `MOUSE_RELEASED`, and `KEY_PRESSED` events:

Import Statements:

```
 import javafx.event.EventHandler;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
```

Listing 1-5. Register event handlers to handle `MOUSE_PRESSED`, `MOUSE_DRAGGED`, `MOUSE_RELEASED`, and `KEY_PRESSED` events:

```
 final Pane drawPane = new Pane();

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Add codes here to handle mouse pressed event
      }
    });

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Add codes here to handle mouse dragged event
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Add codes here to handle mouse released event
      }
    });
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        // Add codes here to handle key event
    });
```

## 1.3 Properties and Binding in `LineDrawer` Class

### 1.3.1 Define Properties to Hold Locations of Mouse Events

To keep track of mouse locations while mouse events occur, we define the following properties of type `DoubleProperty`:

Import Statements:

```
 import javafx.beans.property.DoubleProperty;
import javafx.beans.property.SimpleDoubleProperty;
```

Listing 1-6. Define `startX`, `startY`, `translateX` and `translateX`, properties of type `DoubleProperty`:

```
 // startX, startY hold locations of mouse pressed event
  DoubleProperty startX = new SimpleDoubleProperty();
  DoubleProperty startY = new SimpleDoubleProperty();

  // translateX, translateY hold the distance from dragged/moved location to startX, startY
  DoubleProperty translateX = new SimpleDoubleProperty();
  DoubleProperty translateY = new SimpleDoubleProperty();
```

`MouseEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`; it provides methods, `getX()` and `getY()`, to get X, Y locations of the mouse while this event occurs.

`public final double getX()`

Get the X location of the mouse, relative to the origin of the source object of this event.

`public final double getY()`

Get the Y location of the mouse, relative to the origin of the source object of this event.

The values for `startX` and `startY` are set inside the event handler that handles mouse pressed event, here are the codes:

Listing 1-7. Register event handler to handle `MOUSE_PRESSED` event:

```
 final Pane drawPane = new Pane();

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get the starting mouse location
        startX.set(me.getX());
        startY.set(me.getY());
      }
    });
```

The values for `translateX` and `translateY` are set inside the event handler that handles mouse dragged event, here are the codes:

Listing 1-8. Set value for properties `translateX`, `translateY`:

```
 drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get());

        ...

      }
    });
```

### 1.3.2 Define `ObjectProperty<Shape>` to Hold a Sketch

The class field, `shape`, of type `ObjectProperty<Shape>` is defined to temporarily hold a sketch, a `Shape` object, drawn on a drawing board. When the first mouse dragged event is detected, the line object is created and set as the value of `shape` property.

Inside the mouse dragged event handler, we need to tell whether this is the first mouse dragged event subsequent to the mouse pressed event; if it is, then a line is created, it is created only once over a MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle. A `boolean` field `dragged` is defined for this purpose, it is set to `true` when the first mouse dragged event detected, and reset to `false` when the mouse released event occurs. Here are snippets of codes to accomplish these tasks:

Import Statements:

```
 import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.scene.paint.Color;
import javafx.scene.shape.Line;
import javafx.scene.shape.Shape;
```

Listing 1-9. Define shape property and dragged variable, create a line as mouse starts dragging:

```
 // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Do this only once
          if (getShape() == null)	{
            Shape tmpShape = new Line();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;

          ...

        }
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;

          ...

        }
      }
    });
```

A listener for `shape` property is added to observe the value changed. If a none-null value is set to the property, it is added to the children list of the drawing board, and the shape becomes visible in the application window.

Import Statements:

```
 import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
```

Listing 1-10. Add listener to shape property:

```
 // Listen to the value changed of shape property,
    // add the shape to drawing board if a new shape is created.
    shape.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
      }
    });
```

When a line is finalized, that is, when `Enter` key is pressed, the line's start point and end point are finalized, and the value of `shape` property is set to null, this is carried out inside the event handler, registered for `KEY_PRESSED` event type, described in later section.

### 1.3.3 Bind Properties for the Ending Point of Line

The following two methods are defined to handle `bind` and `unbind`, for `endX` property and `endY` property, the ending point of a line currently drawing on a drawing board.

`void onMouseDragStarted()`

`void onMouseDragFinished()`

Inside the `onMouseDragStarted()` method, we are using an `add` method, provided in `javafx.beans.binding.DoubleExpression` class, to produce a `DoubleBinding` which calculates the sum of starting position and translate distance:

```
 public DoubleBinding add(ObservableNumberValue other) 
```

Here are implementations of `onMouseDragStarted()` method and `onMouseDragFinished()` method:

Listing 1-11. Define Methods to deal with properties of a line, invoked from event handlers of MOUSE_DRAGGED and MOUSE_RELEASED:

```
 void onMouseDragStarted() {
    Line line = (Line)getShape();
    // Set value of properties startX, startY
    line.setStartX(startX.get());
    line.setStartY(startY.get());
    // bind for properties endX, endY
    line.endXProperty().bind(startX.add(translateX));
    line.endYProperty().bind(startY.add(translateY));
  }

  void onMouseDragFinished() {
    Line line = (Line)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (line != null) {
      // unbind for properties endX, endY
      line.endXProperty().unbind();
      line.endYProperty().unbind();
    }
  }
```

The `onMouseDragStarted()` method is called from an event handler that handles `MOUSE_DRAGGED` event, it is executed only once for each MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle, dealing with computing value for starting point property and ending point property of a line.

Here are complete codes to register an event handler to handle `MOUSE_DRAGGED` event:

Listing 1-12. Register event handler to handle `MOUSE_DRAGGED` event:

```
 drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Line();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });
```

Likewise, the `onMouseDragFinished()` method is called from event handler that handles `MOUSE_RELEASED` event, it is executed only once for each MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle, deal with unbinding for ending point property of a line.

Here are complete codes to register an event handler to handle `MOUSE_RELEASED` event:

Listing 1-13. Register event handler to handle `MOUSE_RELEASED` event:

```
 drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          onMouseDragFinished();
        }
      }
    });
```

## 1.4 Get Key Code of Key Event

`KeyEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines static fields for event types such as `KEY_PRESSED`, `KEY_RELEASED`, `KEY_TYPED`, etc,

`static EventType<KeyEvent> KEY_PRESSED`

`KEY_PRESSED` event occurs when a key is pressed.

`static EventType<KeyEvent> KEY_RELEASED`

`KEY_RELEASED` event occurs when a key is released.

`static EventType<KeyEvent> KEY_TYPED`

`KEY_TYPED` event occurs when a key is pressed and released.

`KeyCode` class, resides in `javafx.scene.input` package, is an enumerated type defines constants for keys of a keyboard; it covers letter keys (`A` to `Z`), digits keys (`DIGIT0` to `DIGIT9`), modifier keys (such as `CONTROL`, `SHIFT`, etc.), function keys (such as `F1`, `F2`), `ENTER`, `ESCAPE`, `HOME`, `END`, `BACKSPACE`, etc.

Here are two methods, provided in `KeyEvent` class, to get information about a key when `KEY_PRESSED` or `KEY_RELEASED` event occurs.

`public final KeyCode getCode()`

Get the code of a key pressed or released, as type of `KeyCode`, when `KEY_PRESSED` or `KEY_RELEASED` event occurs. `KeyCode.UNDEFINED` is returned for `KEY_TYPED` event.

`public final String getText()`

Get information about a key pressed or released, in `String` representation, when `KEY_PRESSED` or `KEY_RELEASED` event occurs. An empty string is returned for `KEY_TYPED` event.

Following boolean methods are also available in `KeyEvent` class, to verify whether modifier keys are pressed at the same time when a key event occurs.

`public final boolean isControlDown()`

Check if Ctrl key is down when this event occurs.

`public final boolean isAltDown()`

Check if Alt key is down when this event occurs.

`public final boolean isShiftDown()`

Check if Shift key is down when this event occurs.

To enable a source node to receive key events, the value of `focusTraversable` property should be set to `true`; its default value is `false`.

`public final void setFocusTraversable(boolean value)`

Set the value of `focusTraversable` property to `true` making this node traversable and eligible to receive focus, usually by using `TAB` key or `SHIFT+TAB` keys to move focus forward or backward among traversable nodes.

Following snippets of codes show how to register event handler to handle `KEY_PRESSED` event, and how does a `handle(KeyEvent` event`)` method look like:

Import Statements:

```
 import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
```

Listing 1-14. Register event handlers to handle `KEY_PRESSED` event:

```
 // Must set focusTraversable to true in order to handle KeyEvent, 
    // default is false.
    drawPane.setFocusTraversable(true);
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this line
            System.out.format("Enter key hit%n");
            // Must call dragged finished method to unbind
            onMouseDragFinished();
            setShape(null);  // complete this line
            break;
          case ESCAPE:
            // Hit Esc key to clear this line
            System.out.format("Esc key hit%n");
            Shape s = getShape();
            if (s != null) {
              // Must call dragged finished method to unbind
              onMouseDragFinished();
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this line
            }
            break;
        }       
      }
    });
```

## 1.5 Complete Source Codes of `LineDrawer` class

Listing 1-15. Create `LineDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of scene, and place `Pane` in the center of a `BorderPane` as a drawing board:

```
 package drawtool;

import javafx.application.Application;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.EventHandler;
import javafx.event.EventType;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Line;
import javafx.scene.shape.Shape;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: LineDrawer.java
 * (in directory: LineDrawer1.0/src/example1/drawtool/)
 * This JavaFX application is the initial phase of implementation of a comprehensive
 * drawing tool JFXDrawTools.
 * The first step is to implement Line drawing through consecutive mouse dragged events
 * A Pane object is employed as a drawing board
 * It takes the following mouse events to draw lines on a drawing board:
 *   MOUSE_PRESSED, MOUSE_DRAGGED, MOUSE_RELEASED
 * As MOUSE_PRESSED event occurs, the mouse position is obtained to be used as
 * the start point of a line,
 * a line is created when a MOUSE_PRESSED event is followed immediately by a
 * MOUSE_DRAGGED event,
 * the ending point of this line binds to the position of MOUSE_DRAGGED event,
 * this line is completed as MOUSE_RELEASE event occurs,
 * repeat MOUSE_PRESSED, MOUSE_DRAGGED, MOUSE_RELEASED event cycles until you are
 * satisfied with the rendering of this line
 * To finalize this line, hit ENTER key,
 * the next MOUSE_PRESSED event will start a new line
 * To cancel this line, hit  ESCAPE key
 *
 * @author: Shufen Kuo
 */
public class LineDrawer extends Application {

  // Keep track of the cursor locations while mouse event occurs
  // startX, startY hold locations of mouse pressed event
  DoubleProperty startX = new SimpleDoubleProperty();
  DoubleProperty startY = new SimpleDoubleProperty();

  // translateX, translateY hold the distance from dragged/moved location to the startX, startY
  DoubleProperty translateX = new SimpleDoubleProperty();
  DoubleProperty translateY = new SimpleDoubleProperty();

  // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    final Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get the starting mouse location
        startX.set(me.getX());
        startY.set(me.getY());
      }
    });

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Line();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          onMouseDragFinished();
        }
      }
    });

    // Must set focusTraversable to true in order to handle KeyEvent, 
    // default is false.
    drawPane.setFocusTraversable(true);
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this line
            System.out.format("Enter key hit%n");
            // Must call dragged finished method to unbind
            onMouseDragFinished();
            setShape(null);  // complete this line
            break;
          case ESCAPE:
            // Hit Esc key to clear this line
            System.out.format("Esc key hit%n");
            Shape s = getShape();
            if (s != null) {
              // Must call dragged finished method to unbind
              onMouseDragFinished();
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this line
            }
            break;
        }       
      }
    });

    // Listen to the value changed of shape property,
    // add the shape to drawing board if a new shape is created.
    shape.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
      }
    });

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("LineDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  void onMouseDragStarted() {
    Line line = (Line)getShape();
    line.setStartX(startX.get());
    line.setStartY(startY.get());
    line.endXProperty().bind(startX.add(translateX));
    line.endYProperty().bind(startY.add(translateY));
  }

  void onMouseDragFinished() {
    Line line = (Line)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (line != null) {
      // unbind for properties endX, endY
      line.endXProperty().unbind();
      line.endYProperty().unbind();
    }
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 1-3. Snapshot of sketch drawing using `Line Drawer` module

![](images/00005.jpeg "draw_house.jpg")

Compile and run the application. Try these steps to test it:

1.  Press the mouse and drag it around the drawing board.
2.  Release the mouse.
3.  Repeat the previous two steps several times.
4.  Hit `Enter` key.
5.  Press the mouse and drag it around the drawing board.
6.  Release the mouse.
7.  Repeat the previous two steps several times.
8.  Hit `Esc` key.

Output from Compiling and Running the Program in Command Line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\LineDrawer1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf DrawTool.jar drawtool

java -cp DrawTool.jar drawtool.LineDrawer

shape value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x0000ffff, strokeWidth=1.0]
Enter key hit
shape value changed: null
shape value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x0000ffff, strokeWidth=1.0]
Esc key hit
shape value changed: null
```

## 1.6 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Line` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides four properties to specify a line's location: `startX`, `startY`, `endX`, and `endY`.
    (See section [Create `LineDrawer` Class as Subclass of `Application`](#part0007_split_001.html_create-line-drawer))
*   `public final ObservableList<Double> getStrokeDashArray()` is a method defined in `Shape` class for specifying a dash pattern to stroke the border of a `Shape`.
    (See [here](#part0007_split_001.html_dash-line))
*   `Pane` class, extends `javafx.scene.layout.Region` and resides in `javafx.scene.layout` package, is the base class of JavaFX build-in layout panes.
    (See section [Add `Pane` as Drawing Board in the Center of `BorderPane`](#part0007_split_001.html_pane-as-drawing-board))
*   `Group` class, resides in `javafx.scene.Group` package, is a subclass of `javafx.scene.Parent`, its bounds is decided by its contents, and is un-resizable by its parent.
    (See [here](#part0007_split_001.html_group-as-container))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See section [Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key))
*   `MouseEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `MOUSE_CLICKED`, `MOUSE_DRAGGED`, `MOUSE_ENTERED`, `MOUSE_EXITED`, `MOUSE_MOVED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, etc., and provides methods such as `getX()`, `getY()`, etc., to get the position of mouse cursor while the event occurs.
    (See sections: [Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key), and [Define Properties to Hold Locations of Mouse Events](#part0007_split_003.html_properties-for-mouse-locations))
*   Some of convenience methods provided in `Node` class to register `EventHandler`s to handle mouse events and key events.

    `public final void setOnMousePressed(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnMouseDragged(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnMouseReleased(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnKeyPressed(EventHandler<? super KeyEvent>` value`)`

    (See section [Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key), [here](#part0007_split_003.html_set-on-mouse-pressed-codes), [here](#part0007_split_003.html_set-on-mouse-dragged-codes), [here](#part0007_split_003.html_set-on-mouse-released-codes), and [here](#part0007_split_004.html_set-on-key-pressed-codes))
*   Some of Classes reside in `javafx.beans.property` package:

    `DoubleProperty`

    An abstract class, derived from `javafx.beans.binding.DoubleExpression` class, implements `Property<Number>` and `WritableDoubleValue`.
    `WritableDoubleValue` extends `WritableNumberValue`.

    `SimpleDoubleProperty`

    Derived from `DoubleProperty` class.

    `ObjectProperty<T>`

    An abstract class, derived from `javafx.beans.binding.ObjectExpression<T>` class, implements `Property<T>` and `WritableObjectValue<T>`.

    `SimpleObjectProperty<T>`

    Derived from `ObjectProperty<T>` class.

    (See sections: [Define Properties to Hold Locations of Mouse Events](#part0007_split_003.html_properties-for-mouse-locations), and [Define `ObjectProperty<Shape>`](#part0007_split_003.html_define-property-shape))
*   `void addListener(ChangeListener<? super T> listener)` method, defined in `javafx.beans.value.ObservableValue` interface, adds a `ChangeListener` by providing a `changed(ObservableValue<? extends T>` observable`, T` oldValue`, T` newValue`)` method, to be invoked when this property's value is changed.
    (See [here](#part0007_split_003.html_shape-listener))
*   `void bind(ObservableValue<? extends T>` observable`)` and `void unbind()` are methods defined in `Property` interface, reside in `javafx.beans.property` package, to create/remove a unidirectional binding for this property.
    (See section [Bind Properties for the Ending Point of Line](#part0007_split_003.html_bind-end-point))
*   `DoubleBinding`, an abstract class resides in `javafx.beans.binding` package, extends `DoubleExpression` and implements `NumberBinding`. The `computeValue()` method need to be implemented in order to instantiate a `DoubleBinding` object.
    (See [here](#part0007_split_003.html_double-expression-add))
*   `public DoubleBinding add(ObservableNumberValue` other`)` method, provided in `javafx.beans.binding.DoubleExpression` class, returns a new `DoubleBinding` that calculates sum of this `NumberExpression` and the given `NumberExpression`.
    (See [here](#part0007_split_003.html_double-expression-add))
*   `KeyEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `KEY_PRESSED`, `KEY_RELEASED`, `KEY_TYPED`, etc., and provides methods such as `getCode()`, `getCharacter()`, `getText()`, etc., to get information about keys in type of either `KeyCode`, or `String`. It also provides boolean methods such as `isControlDown()`, `isShiftDown()`, `isAltDown()`, etc., to verify whether some of modifier keys are pressed at the same time.
    (See section [Get Key Code of Key Event](#part0007_split_004.html_key-code-key-event))
*   `KeyCode` class, resides in `javafx.scene.input` package, is an enumerated type defines constants for keys of keyboard, it covers letter keys (`A` to `Z`), digits keys(`DIGIT0` to `DIGIT9`), modifier keys(such as `CONTROL`, `SHIFT`, etc.), function keys, etc.
    (See [here](#part0007_split_004.html_key-code))
*   `focusTraversable` is a property defined in `Node` class for specifying whether this node is traversable and eligible to receive focus.
    (See [here](#part0007_split_004.html_focus-traversable))

# Chapter 2
Polyline Drawer
--Developing Polyline Drawer V1.0

## Preface

In this chapter, we'll develop a `Polyline Drawer` module, similar to `Line Drawer V1.0` developed in the preceding chapter. For common aspects, please refer to previous chapter. Here we'll only cover the features unique to the implementation of `Polyline Drawer`. From detailed descriptions and well-documented example codes excerpted from `Polyline Drawer V1.0`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0008_split_003.html_summary) section.

The complete development process of `Polyline Drawer V1.0` is characterized by the following steps:

*   [2.1 Create `PolylineDrawer` Class as Subclass of `Application`](#part0008_split_001.html_create-polyline-drawer)
    *   [2.1.1 Create an Instance of `Polyline`](#part0008_split_001.html_create-polyline)
    *   [2.1.2 Define `ObjectProperty<Line>` to Hold a Temporary Line](#part0008_split_001.html_define-line-property)
    *   [2.1.3 Implement `onMouseDragStarted()` method](#part0008_split_001.html_implement-on-mouse-drag-started)
    *   [2.1.4 Implement `onMouseDragFinished()` method](#part0008_split_001.html_implement-on-mouse-drag-finished)
*   [2.2 Complete Source Codes of `PolylineDrawer` class](#part0008_split_002.html_complete-source-codes)
*   [2.3 Summary](#part0008_split_003.html_summary)

## 2.1 Create `PolylineDrawer` Class as Subclass of `Application`

The `Polyline` class, resides in `javafx.scene.shape package`, is one of direct subclasses of `Shape` class.

Here's an example to create a hard-coded `Polyline` object:

Import Statements:

```
import javafx.scene.shape.Polyline;
```

Listing 2-1. Create a `Polyline` composed of 5 line segments, given 6 points:

```
 Polyline polyline = new Polyline(
      50.0, 20.0,
      220.0, 170.0,
      50.0, 320.0,
      50.0, 250.0,
      140.0, 170.0,
      50.0, 90.0);
```

Here's another way to create the same `Polyline` object:

Listing 2-2. Create a `Polyline` composed of 5 line segments, given 6 points:

```
 Polyline polyline = new Polyline();
  Double[] dArray = {
      50.0, 20.0,
      220.0, 170.0,
      50.0, 320.0,
      50.0, 250.0,
      140.0, 170.0,
      50.0, 90.0};
  polyline.getPoints().addAll(dArray);
```

The following snapshot shows the rendering of a `Polyline` from above codes:

Figure 2-1. Snapshot of a polyline created from above codes.

![](images/00006.jpeg "example_polyline.jpg")

The following illustration shows coordinates of each point from the above codes which render a `Polyline`.

Figure 2-2. Snapshot illustrates a polyline composed of 5 line segments, given 6 points.

![](images/00007.jpeg "diagram_polyline.jpg")

Now, we'll demonstrate how to develop a `PolylineDrawer` application that interactively draws `Polyline` objects. The (X, Y) coordinates for all points of a `Polyline` are obtained dynamically through mouse pressed and mouse dragged events.

The approach to interactively draw polylines on a drawing board is similar to drawing lines described in last chapter. Here's a preview of how the `PolylineDrawer` works:

A `Line` representing one segment of a `Polyline` is created through each MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle. Draw as many segments as required for a `Polyline`. If the start point of this segment is not identical with the end point of last segment, a segment connecting the two is automatically created. Hit `Enter` key to finalize a `Polyline`, or hit `Esc` key to cancel it.

In terms of source codes, differences between the development of `PolylineDrawer` module and `LineDrawer` module are mostly inside two methods: the `onMouseDragStarted()` method and the `onMouseDragFinished()` method.

Following is the initial appearance of `PolylineDrawer` class, creating a `BorderPane` as the root of a `Scene`, and placing a `Pane` in the center of `BorderPane`:

Listing 2-3. Create `PolylineDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of `Scene`, and place `Pane` in the center of `BorderPane` as drawing board:

```
package drawtool;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: PolylineDrawer.java
 * @author: Shufen Kuo
 *
 */
public class PolylineDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("PolylineDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

### 2.1.1 Create an Instance of `Polyline`

A `Polyline` object is created inside the event handler of `MOUSE_DRAGGED` event. It is set as the current value of `shape` property until the drawing for all segments of a polyline are finished. The value of `shape` is reset to `null` when `Enter` key is pressed, which finalizes the shape, or `Esc` key is pressed, which cancels the shape.

To understand how to register event handlers using convenience methods, provided in `Node` class, to handle mouse events and key events, please read Section 1.2.1 [Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key) and Section 1.4 [Get Key Code of Key Event](#part0007_split_004.html_key-code-key-event) in Chapter 1.

Followings are codes that create an instance of `Polyline` inside the event handler that handles `MOUSE_DRAGGED` event.

Import Statements:

```
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.event.EventHandler;
import javafx.scene.input.MouseEvent;
import javafx.scene.paint.Color;
import javafx.scene.shape.Polyline;
import javafx.scene.shape.Shape;
```

Listing 2-4. Register event handler of `MOUSE_DRAGGED` event, create an instance of `Polyline` when the first mouse dragged event is detected:

```
 // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Polyline();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });
```

### 2.1.2 Define `ObjectProperty<Line>` to Hold a Temporary Line

A `line` property of type `ObjectProperty<Line>` is defined to hold a `Line` which stands for the currently drawing segment of a `Polyline`. This is only a temporary line with its end point tracing the mouse dragged locations, using Properties and Binding mechanism. As mouse is released, the line is removed from the scene and its end point is added to the points list of a polyline.

The tasks, creating a temporary `Line` object and setting as the value of `line` property, is accomplished inside the [`onMouseDragStarted()`](#part0008_split_001.html_on-mouse-drag-started-codes) method, called from the event handler of `MOUSE_DRAGGED` event, when the first mouse dragged event, subsequent to each mouse pressed event, is detected.

And inside the [`onMouseDragFinished()`](#part0008_split_001.html_on-mouse-drag-finished-codes) method, called from the event handler of `MOUSE_RELEASED` event, the value of `line` property is set to `null`.

A listener is added for the `line` property, to observe the value changed.

In the listener of `line` property, the newly created line is added to the children list of a `Pane`, the drawing board, and becomes visible in the application window. It will be removed from the drawing board, as a result of setting the value of `line` property to `null` inside the `onMouseDragFinished()` method.

Listing 2-5. Define `line` property and add listener to observe the value changed:

```
 // This is to hold a temporary line 
  ObjectProperty<Line> line = new SimpleObjectProperty<>();

    // Listener to observe the value changed of line property,
    // add the line to drawing board if a new line is created,
    // remove the line if one segment of polyline is finished.
    line.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
         else // remove this temporary line
           drawPane.getChildren().remove(newVal);
      }
    });
```

### 2.1.3 Implement `onMouseDragStarted()` Method

The major differences between the implementation of `Line Drawer` and that of `Polyline Drawer` are laid inside the `onMouseDragStarted()` method. It is called from the event handler of `MOUSE_DRAGGED` event when the first dragged event occurs.

Two tasks are carried out here for the `Polyline Drawer`:

*   Create a temporary `Line` object, having a start point set at the location where mouse is pressed, and an end point binding to a `DoubleBinding` object which calculates the sum of starting position and translate distance.
*   Verify whether the start point of a current drawing line segment is same as the end point of a previous line segment. If they are not the same means the current line segment is not connected to previous one, we'll add the start point of current line segment to the points list of a `Polyline`.

    Be aware that the end point of a previous line segment can be found in the points list of the `Polyline`, it is stored in the last two cells of the points list.

    If the points list of the `Polyline` contains empty points, it means the current drawing line segment is the first segment of the `Polyline`, simply add the start point of this segment to the point list, it becomes the first point of the `Polyline`.

Import Statements:

```
import javafx.collections.ObservableList;
```

Listing 2-6. Implement `onMouseDragStarted()` Method, called from event handler of MOUSE_DRAGGED event:

```
 void onMouseDragStarted() {
    Line tmpLine = new Line();
    // Set this tmpLine as value of line property,
    // as a result, it will be added to drawing board's children list
    // inside the line property's listener.
    line.set(tmpLine);
    tmpLine.setStroke(Color.AQUA);
    tmpLine.setStartX(startX.get());
    tmpLine.setStartY(startY.get());
    tmpLine.endXProperty().bind(startX.add(translateX));
    tmpLine.endYProperty().bind(startY.add(translateY));

    Polyline polyline = (Polyline)getShape();
    // Verify whether the start point of this line is same as the end point of the last line
    // If they are not the same means this segment is not connected to last segment,
    // we'll add the start point of this segment to the polyline's points list.
    ObservableList<Double> list = polyline.getPoints();
    if (list.size() > 1) {
      // check if the last point is same as the start point of this line
      double lastX = list.get(list.size()-2);
      double lastY = list.get(list.size()-1);
      // if start point of this segment coincide with the last point
      // in the points list of polyline,
      // no need to add start point to the polyline
      if (lastX != startX.get() && lastY != startY.get()) {
        // add the start point to polyline
        polyline.getPoints().addAll(startX.get(), startY.get());
      }        
    } else {
      // There's no points in the points list yet,
      // add the start point to the points list,
      // this is the beginning point of the polyline.
      polyline.getPoints().addAll(startX.get(), startY.get());
    }
  }
```

### 2.1.4 Implement `onMouseDragFinished()` Method

The `onMouseDragFinished()` Method is called from the event handler of `MOUSE_RELEASED` event.

It carries out the following tasks:

*   Unbind the end point of `Line`. And set value of `line` property to `null`, causing the line to be removed from the drawing board, see [codes for the listener of `line` property](#part0008_split_001.html_line-listener-codes).
*   Add the end point of `Line` to the points list of a `Polyline`, which is temporarily held in the `shape` property.

The MOUSE_DRAGGED event followed by MOUSE_RELEASED event completes the drawing of one segment in a `Polyline`.

Listing 2-7. Implement `onMouseDragFinished()` Method, called from event handler of MOUSE_RELEASED event:

```
 void onMouseDragFinished() {
    Line tmpLine = line.get();
    if (tmpLine != null) {
      tmpLine.endXProperty().unbind();
      tmpLine.endYProperty().unbind();
      line.set(null); // clear this line
    }

    Polyline polyline = (Polyline)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (polyline != null) {
      // Add the end point of the current line to the polyline
      polyline.getPoints().addAll(startX.get() + translateX.get(),
        startY.get() + translateY.get());
    }
  }
```

## 2.2 Complete Source Codes of `PolylineDrawer` class

The changes, comparing to `LineDrawer` class in previous chapter, are shown in bold face:

Listing 2-8. Create `PolylineDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of scene, and place `Pane` in the center of `BorderPane` as a drawing board:

```
package drawtool;

import javafx.application.Application;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.collections.ObservableList;
import javafx.event.EventHandler;
import javafx.event.EventType;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Line;
import javafx.scene.shape.Polyline;
import javafx.scene.shape.Shape;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: PolylineDrawer.java
 * (in directory: PolylineDrawer1.0/src/example1/drawtool/)
 * This JavaFX application implements polyline drawing through
 * consecutive mouse dragged events,
 * later will be intergrated into a comprehensive drawing tool JFXDrawTools.
 * A Pane object is employed as a drawing board
 * It takes the following mouse events to draw each segment of a polyline on a drawing board:
 *   MOUSE_PRESSED, MOUSE_DRAGGED, MOUSE_RELEASED
 * A segment is drawn through the following actions:
 * As the MOUSE_PRESSED event occurs, the mouse position is obtained to be used as
 * the start point of a segment of a polyline,
 * a polyline object is created and set as the value of shape property
 * until all segments are completed,
 * that is, when Enter key is pressed to finalize it,  or Esc key is pressed to cancel it
 * When the MOUSE_PRESSED event is followed immediately by a
 * MOUSE_DRAGGED event,	
 * a temporary line is created as the current segment of a polyline,
 * it is held in the line property, 
 * the ending point of this line binds to the position of MOUSE_DRAGGED event,
 * this current segment of polyline is completed as MOUSE_RELEASED event occurs,
 * repeat the MOUSE_PRESSED-MOUSE_DRAGGED-MOUSE_RELEASED event cycle to draw the next segment
 * One detail needs be taken care of: if start point of the next segment is not
 * the end point of previous segment,
 * a new segment will be automatically added to connect these two segments
 * When you finish all the segments of a polyline, hit ENTER key to finalize it,
 * the next MOUSE_PRESSED event will start the first segment of a new polyline
 * To cancel this polyline, hit  ESCAPE key
 *
 * @author: Shufen Kuo
 */
public class PolylineDrawer extends Application {

  // Keep track of the cursor locations while mouse event occurs
  // startX, startY hold locations of mouse pressed event
  DoubleProperty startX = new SimpleDoubleProperty();
  DoubleProperty startY = new SimpleDoubleProperty();

  // translateX, translateY hold the distance from dragged/moved location to startX, startY
  DoubleProperty translateX = new SimpleDoubleProperty();
  DoubleProperty translateY = new SimpleDoubleProperty();

  // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This is to hold a temporary line which stands for one segment of a polyline
  ObjectProperty<Line> line = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    final Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get the starting mouse location
        startX.set(me.getX());
        startY.set(me.getY());
      }
    });

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Polyline();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          onMouseDragFinished();
        }
      }
    });

    // Must set focusTraversable to true in order to handle KeyEvent, 
    // default is false.
    drawPane.setFocusTraversable(true);
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this shape
            System.out.format("Enter key hit%n");
            // Must call dragged finished method to unbind
            onMouseDragFinished();
            setShape(null);  // complete this shape
            break;
          case ESCAPE:
            // Hit Esc key to clear this shape
            System.out.format("Esc key hit%n");
            Shape s = getShape();
            if (s != null) {
              // Must call dragged finished method to unbind
              onMouseDragFinished();
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this shape
            }
            break;
        }       
      }
    });

    // Listener to observe the value changed of shape property,
    // add the shape to drawing board if a new shape is created.
    shape.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
      }
    });

    // Listener to observe the value changed of line property,
    // add the line to drawing board if a new line is created,
    // remove the line if one segment of polyline is finished.
    line.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("line value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
         else if (oldVal != null)// remove this temporary line
           drawPane.getChildren().remove(oldVal);
      }
    });

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("PolylineDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  void onMouseDragStarted() {
    Line tmpLine = new Line();
    // Set this tmpLine as value of line property,
    // as a result, it will be added to drawing board's children list
    // inside the line property's listener.
    line.set(tmpLine);
    tmpLine.setStroke(Color.AQUA);
    tmpLine.setStartX(startX.get());
    tmpLine.setStartY(startY.get());
    tmpLine.endXProperty().bind(startX.add(translateX));
    tmpLine.endYProperty().bind(startY.add(translateY));

    Polyline polyline = (Polyline)getShape();
    // Verify whether the start point of this line is same as
    // the end point of the last line
    // If they are not the same means
    // this segment is not connected to last segment,
    // we'll add the start point of this segment to the polyline's points list.
    ObservableList<Double> list = polyline.getPoints();
    if (list.size() > 1) {
      // check if the last point is same as the start point of this line
      double lastX = list.get(list.size()-2);
      double lastY = list.get(list.size()-1);
      // if start point of this segment coincide with the last point
      // in the points list of polyline,
      // no need to add start point to the polyline
      if (lastX != startX.get() && lastY != startY.get()) {
        // add the start point to polyline
        polyline.getPoints().addAll(startX.get(), startY.get());
      }        
    } else {
      // There's no points in the points list yet,
      // add the start point to the points list,
      // this is the beginning point of the polyline.
      polyline.getPoints().addAll(startX.get(), startY.get());
    }
  }

  void onMouseDragFinished() {
    Line tmpLine = line.get();
    if (tmpLine != null) {
      tmpLine.endXProperty().unbind();
      tmpLine.endYProperty().unbind();
      line.set(null); // clear this line from drawing board
    }

    Polyline polyline = (Polyline)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (polyline != null) {
      // Add the end point of the current line to the polyline
      polyline.getPoints().addAll(startX.get() + translateX.get(),
        startY.get() + translateY.get());
    }
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 2-3. Snapshot of sketch drawing using `Polyline Drawer` module

![](images/00008.jpeg "draw_house.jpg")

Compile and run the application. Try these steps to test it:

1.  Press the mouse and drag it around the drawing board.
2.  Release the mouse, the first line segment of a polyline is drawn.
3.  Press the mouse at the same location (at the end point of last line segment), drag the mouse around the drawing board and release the mouse, another line segment connected to previous one is drawn.
4.  Repeat the previous step several times to draw more line segments connected one by one.
5.  Hit `Enter` key to finalize the drawing of one polyline.
6.  Now start drawing another polyline.
7.  Move mouse to a new location, press the mouse and drag it around the drawing board.
8.  Release the mouse, the first line segment of a polyline is drawn.
9.  Move the mouse to another location (different from the end point of last line segment), drag the mouse around the drawing board and release the mouse, two more line segments are drawn.
10.  Repeat the previous step several times.
11.  Hit `Enter` key to finalize the drawing of one polyline.
12.  Try the similar pressed-dragged-released steps several times, then hit `Esc` key to cancel the drawing.

Output from Compiling and Running the Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\PolylineDrawer1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf DrawTool.jar drawtool

java -cp DrawTool.jar drawtool.PolylineDrawer

shape value changed: Polyline[points=[], fill=null, stroke=0x0000ffff,
strokeWidth=1.0]
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
Enter key hit
shape value changed: null
shape value changed: Polyline[points=[], fill=null, stroke=0x0000ffff,
strokeWidth=1.0]
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
Enter key hit
shape value changed: null
shape value changed: Polyline[points=[], fill=null, stroke=0x0000ffff,
strokeWidth=1.0]
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
Esc key hit
shape value changed: null
```

## 2.3 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Polyline`, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. Use the `getPoints()` method to obtain a list which is type of `ObservableList<Double>`, then use the basic utilities, defined in `Collection` interface, to add a series of x and y coordinates, stored in an array of `Double` value, to the list, representing points of a `Polyline`.
    (See section [Create `PolylineDrawer` Class as Subclass of `Application`](#part0008_split_001.html_create-polyline-drawer), section [Create an Instance of Polyline](#part0008_split_001.html_create-polyline) and [here](#part0008_split_001.html_on-mouse-drag-started-codes))
*   Some of Classes reside in `javafx.beans.property` package:

    `ObjectProperty<T>`

    is an abstract class, derived from `javafx.beans.binding.ObjectExpression<T>` class, implements `Property<T>` and `WritableObjectValue<T>`.

    `SimpleObjectProperty<T>`

    derived from `ObjectProperty<T>` class.

    (See section [Define ObjectProperty<Line> to Hold a Temporary Line](#part0008_split_001.html_define-line-property))
*   `Line` class, resides in `javafx.scene.shape` package, is one of direct subclasses of `javafx.scene.shape.Shape`.
    (See section [Define ObjectProperty<Line> to Hold a Temporary Line](#part0008_split_001.html_define-line-property))
*   `void addListener(ChangeListener<? super T>` listener`)` method, defined in `javafx.beans.value.ObservableValue` interface, adds a `ChangeListener` by providing a `changed(ObservableValue<? extends T>` observable`, T` oldValue`, T` newValue`)` method, to be invoked when this property's value is changed.
    (See [here](#part0008_split_001.html_add-listener-for-line))
*   `void bind(ObservableValue<? extends T>` observable`)` and `void unbind()` are methods defined in `Property` interface, reside in `javafx.beans.property` package, to create/remove a unidirectional binding for this property. (See [Here](#part0008_split_001.html_on-mouse-drag-started-codes), [Here](#part0008_split_001.html_on-mouse-drag-finished-codes))
*   `public DoubleBinding add(ObservableNumberValue` other`)` method, provided in `javafx.beans.binding.DoubleExpression` class, returns a new `DoubleBinding` that calculates the sum of this `NumberExpression` and the given `NumberExpression`. (See [here](#part0008_split_001.html_on-mouse-drag-started-codes))

# Chapter 3
Polygon Drawer
--Developing Polygon Drawer V1.0

## Preface

In this chapter, we'll develop a `Polygon Drawer` module, based on the source codes of `Polyline Drawer V1.0` developed in the preceding chapter. For common aspects among drawings of `Line`, `Polyline` and `Polygon`, please refer to previous chapters. Here we'll only cover the features unique to the implementation of `Polygon Drawer`. From detailed descriptions and well-documented example codes excerpted from `Polygon Drawer V1.0`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0009_split_003.html_summary) section.

The complete development process of `Polygon Drawer V1.0` is characterized by the following steps:

*   [3.1 Create `PolygonDrawer` Class as Subclass of `Application`](#part0009_split_001.html_create-polygon-drawer)
    *   [3.1.1 Create an Instance of `Polygon`](#part0009_split_001.html_create-polygon)
*   [3.2 Complete Source Codes of `PolygonDrawer` class](#part0009_split_002.html_complete-source-codes)
*   [3.3 Summary](#part0009_split_003.html_summary)

## Create `PolygonDrawer` Class as Subclass of `Application`

The `Polygon` class, resides in `javafx.scene.shape package`, is one of direct subclasses of `Shape` class. The characteristics of `Polygon` are similar to those of `Polyline`, with one exception:

*   For a `Polygon`, if the given last point and first point are not the same, a line segment is automatically added to connect these two points.

Here's an example to create a hard-coded `Polygon` object:

Import Statements:

```
import javafx.scene.shape.Polygon;
```

Listing 3-1. Create a `Polygon` composed of 6 line segments, given 6 points:

```
 Polygon polygon = new Polygon(
      50.0, 20.0,
      220.0, 170.0,
      50.0, 320.0,
      50.0, 250.0,
      140.0, 170.0,
      50.0, 90.0);
  polygon.setFill(Color.web("#B3E6E6"));
  polygon.setStroke(Color.BLACK);
```

Here's another way to create the same `Polygon` object:

Listing 3-2. Create a `Polygon` composed of 6 line segments, given 6 points:

```
 Polygon polygon = new Polygon();
  Double[] dArray = {
      50.0, 20.0,
      220.0, 170.0,
      50.0, 320.0,
      50.0, 250.0,
      140.0, 170.0,
      50.0, 90.0};
  polygon.getPoints().addAll(dArray);
  polygon.setFill(Color.web("#B3E6E6"));
  polygon.setStroke(Color.BLACK);
```

The following snapshot shows the rendering of a `Polygon` from above codes:

Figure 3-1. Snapshot of a polygon created from above codes.

![](images/00009.jpeg "example_polygon.jpg")

The following illustration shows coordinates of each point from the above codes which render a `Polygon`.

Figure 3-2. Snapshot illustrates a polygon composed of 6 line segments, given 6 points.

![](images/00010.jpeg "diagram_polygon.jpg")

To create `PolygonDrawer` class, we adopt the complete source codes of `PolylineDrawer` class, developed in the preceding chapter, and make a little modification.

By far, you must have noticed that two methods, `onMouseDragStarted()` and `onMouseDragFinished()`, are significant in the development process of each different shape drawer. The source codes of `Polygon Drawer` are so similar to `Polyline Drawer`, no need to alter any line of codes for these two methods.

From user's perspective, the approach to interactively draw polygons on the drawing board is same as that of drawing polylines described in previous chapter. When first mouse dragged event is detected, a `Polyline` object is created, exactly like the `Polyline Drawer`; the slight differences in terms of implementation are described as follows:

### Create an Instance of `Polygon`

When `Enter` key is pressed, the `Polyline` object is removed from the children list of a `Pane`, and a `Polygon` object, with the same set of points, is created and adds to the children list of the `Pane`.

Here's the `createPolygon(Pane` pane`)` method which is call from the event handler of `KeyEvent` when `Enter` key is pressed.

Import Statements:

```
import javafx.scene.shape.Polygon;
```

Listing 3-3. Create an instance of `Polygon` when `Enter` key is pressed, inside the event handler of `KEY_PRESSED` event:

```
 drawPane.setOnKeyPressed(new EventHandler() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this shape
            System.out.format("Enter key hit%n");
            // Must call dragged finished method to unbind
            onMouseDragFinished();
            createPolygon(drawPane);
            setShape(null);
            break;
          case ESCAPE:
            // Hit Esc key to clear this shape
            System.out.format("Esc key hit%n");
            Shape s = getShape();
            if (s != null) {
              // Must call dragged finished method to unbind
              onMouseDragFinished();
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this shape
            }
            break;
        }       
      }
    });

  void createPolygon(Pane pane) {
    Polyline polyline = (Polyline)getShape();
    if (polyline != null) {
      Polygon polygon = new Polygon();
      polygon.setFill(polyline.getFill());
      polygon.setStroke(polyline.getStroke());
      polygon.getPoints().addAll(polyline.getPoints());
      pane.getChildren().remove(polyline); // clear polyline
      pane.getChildren().add(polygon); // add polygon
    }
  }
```

## Complete Source Codes of `PolygonDrawer` class

Here are the complete source codes. The changes, comparing to `PolylineDrawer` class in previous chapter, are shown in bold face:

Listing 3-4. Create `PolygonDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of scene, and place `Pane` in the center of a `BorderPane` as a drawing board:

```
package drawtool;

import javafx.application.Application;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.collections.ObservableList;
import javafx.event.EventHandler;
import javafx.event.EventType;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Line;
import javafx.scene.shape.Polygon;
import javafx.scene.shape.Polyline;
import javafx.scene.shape.Shape;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: PolygonDrawer.java
 * (in directory: PolygonDrawer1.0/src/example1/drawtool/)
 * This JavaFX application implements polygon drawing through consecutive mouse dragged events,
 * consecutive mouse dragged events,
 * later will be integrated into a comprehensive drawing tool JFXDrawTools
 * A Pane object is employed as a drawing board
 * It takes the following mouse events to draw each segment of a polygon on a drawing board:
 *   MOUSE_PRESSED, MOUSE_DRAGGED, MOUSE_RELEASED
 * A segment is drawn through the following actions:
 * As the MOUSE_PRESSED event occurs, the mouse position is obtained to be used as
 * the start point of a segment of a polygon,
 * a polyline object is created and set as the value of shape property
 * until all segments are completed,
 * that is, when Enter key is pressed to finalize it,  or Esc key is pressed to cancel it
 * When the MOUSE_PRESSED event is followed immediately by a
 * MOUSE_DRAGGED event,	
 * a temporary line is created as the current segment of a polyline,
 * it is held in the line property, 
 * the ending point of this line binds to the position of MOUSE_DRAGGED event,
 * this current segment of polyline is completed as MOUSE_RELEASED event occurs,
 * repeat the MOUSE_PRESSED-MOUSE_DRAGGED-MOUSE_RELEASED event cycle to draw the next segment
 * One detail needs be taken care of: if start point of the next segment is not
 * the end point of previous segment,
 * a new segment will be automatically added to connect these two segments
 * When you finish all the segments of a polyline, hit ENTER key to finalize it,
 * the next MOUSE_PRESSED event will start the first segment of a new polyline
 * To cancel this polyline, hit  ESCAPE key
 * 
 * The difference from PolylineDrawer is as follows:
 * When Enter key is pressed,
 * a Polygon object is created with the same set of points as Polyline object,
 * the Polyline object is removed, 
 * and the Polygon object is added to the drawing board and
 * becomes visible in the scene 
 *
 * @author: Shufen Kuo
 */
public class PolygonDrawer extends Application {

  // Keep track of the cursor locations while mouse event occurs
  // startX, startY hold locations of mouse pressed event
  DoubleProperty startX = new SimpleDoubleProperty();
  DoubleProperty startY = new SimpleDoubleProperty();

  // translateX, translateY hold the distance from dragged/moved location to the startX, startY
  DoubleProperty translateX = new SimpleDoubleProperty();
  DoubleProperty translateY = new SimpleDoubleProperty();

  // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This is to hold a temporary line which stands for one segment of a polyline
  ObjectProperty<Line> line = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    final Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get the starting mouse location
        startX.set(me.getX());
        startY.set(me.getY());
      }
    });

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Polyline();
            tmpShape.setFill(Color.web("#E6F2E8"));
            tmpShape.setStroke(Color.DARKSEAGREEN);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          onMouseDragFinished();
        }
      }
    });

    // Must set focusTraversable to true in order to handle KeyEvent, 
    // default is false.
    drawPane.setFocusTraversable(true);
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this shape
            System.out.format("Enter key hit%n");
            // Must call dragged finished method to unbind
            onMouseDragFinished();
            createPolygon(drawPane);
            setShape(null);
            break;
          case ESCAPE:
            // Hit Esc key to clear this shape
            System.out.format("Esc key hit%n");
            Shape s = getShape();
            if (s != null) {
              // Must call dragged finished method to unbind
              onMouseDragFinished();
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this shape
            }
            break;
        }       
      }
    });

    // Listener to observe the value changed of shape property,
    // add the shape to drawing board if a new shape is created.
    shape.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
      }
    });

    // Listener to observe the value changed of line property,
    // add the line to drawing board if a new line is created,
    // remove the line if one segment of polyline is finished.
    line.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("line value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
         else if (oldVal != null)// remove this temporary line
           drawPane.getChildren().remove(oldVal);
      }
    });

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("PolygonDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  void createPolygon(Pane pane) {
    Polyline polyline = (Polyline)getShape();
    if (polyline != null) {
      Polygon polygon = new Polygon();
      polygon.setFill(polyline.getFill());
      polygon.setStroke(polyline.getStroke());
      polygon.getPoints().addAll(polyline.getPoints());
      pane.getChildren().remove(polyline); // clear polyline
      pane.getChildren().add(polygon); // add polygon
    }
  }

  void onMouseDragStarted() {
    Line tmpLine = new Line();
    // Set this tmpLine as value of line property,
    // as a result, it will be added to drawing board's children list
    // inside the line property's listener.
    line.set(tmpLine);
    tmpLine.setStroke(Color.AQUA);
    tmpLine.setStartX(startX.get());
    tmpLine.setStartY(startY.get());
    tmpLine.endXProperty().bind(startX.add(translateX));
    tmpLine.endYProperty().bind(startY.add(translateY));

    Polyline polyline = (Polyline)getShape();
    // Verify whether the start point of this line is same as the end point of the last line
    // If they are not the same means this segment is not connected to last segment,
    // we'll add the start point of this segment to the polyline's points list.
    ObservableList<Double> list = polyline.getPoints();
    if (list.size() > 1) {
      // check if the last point is same as the start point of this line
      double lastX = list.get(list.size()-2);
      double lastY = list.get(list.size()-1);
      // if start point of this segment coincide with the last point
      // in the points list of polyline,
      // no need to add start point to the polyline
      if (lastX != startX.get() && lastY != startY.get()) {
        // add the start point to polyline
        polyline.getPoints().addAll(startX.get(), startY.get());
      }        
    } else {
      // There's no points in the points list yet,
      // add the start point to the points list,
      // this is the beginning point of the polyline.
      polyline.getPoints().addAll(startX.get(), startY.get());
    }
  }

  void onMouseDragFinished() {
    Line tmpLine = line.get();
    if (tmpLine != null) {
      tmpLine.endXProperty().unbind();
      tmpLine.endYProperty().unbind();
      line.set(null); // clear this line from drawing board
    }

    Polyline polyline = (Polyline)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (polyline != null) {
      // Add the end point of the current line to the polyline
      polyline.getPoints().addAll(startX.get() + translateX.get(),
        startY.get() + translateY.get());
    }
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 3-3. Snapshot of sketch drawing using `Polygon Drawer` module

![](images/00011.jpeg "draw_house.jpg")

Compile and run the application. Try these steps to test it:

1.  Press the mouse and drag it around the drawing board.
2.  Release the mouse, the first line segment of a polygon is drawn.
3.  Press the mouse at the same location (at the end point of last line segment), drag the mouse around the drawing board and release the mouse, a line segment connected to previous one is drawn.
4.  Repeat the previous step several times to draw more line segments connected one by one.
5.  Hit `Enter` key to finalize the drawing of one polygon.
6.  Now start drawing another polygon.
7.  Move mouse to a new location, press the mouse and drag it around the drawing board.
8.  Release the mouse, the first line segment of a polygon is drawn.
9.  Move the mouse to another location (different from the end point of last line segment), drag the mouse around the drawing board and release the mouse, two more line segments are drawn.
10.  Repeat the previous step several times.
11.  Hit `Enter` key to finalize the drawing of one polygon.
12.  Try the similar pressed-dragged-released steps several times, then hit `Esc` key to cancel the drawing.

Output from Compiling and Running the Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\PolygonDrawer1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf DrawTool.jar drawtool

java -cp DrawTool.jar drawtool.PolygonDrawer

shape value changed: Polyline[points=[], fill=0xe6f2e8ff, stroke=0x8fbc8fff,
strokeWidth=1.0]
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
Enter key hit
shape value changed: null
shape value changed: Polyline[points=[], fill=0xe6f2e8ff, stroke=0x8fbc8fff,
strokeWidth=1.0]
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
Enter key hit
shape value changed: null
shape value changed: Polyline[points=[], fill=0xe6f2e8ff, stroke=0x8fbc8fff,
strokeWidth=1.0]
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
line value changed: Line[startX=0.0, startY=0.0, endX=0.0, endY=0.0,
stroke=0x000000ff, strokeWidth=1.0]
line value changed: null
Esc key hit
shape value changed: null
```

## Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Polyline` and `Polygon`, reside in `javafx.scene.shape` package, are two of direct subclasses of `javafx.scene.shape.Shape`. Use `getPoints()` method to obtain a list which is type of `ObservableList<Double>`, then use basic utilities, defined in `Collection` interface, to add a series of x and y coordinates, stored in an array of `Double` value, to the list, representing points of a `Polyline` or a `Polygon`.
    (See section [Create `PolygonDrawer` Class as Subclass of `Application`](#part0009_split_001.html_create-polygon-drawer), section [Create an Instance of Polygon](#part0009_split_001.html_create-polygon) and [here](#part0009_split_001.html_create-polygon-codes))

# Chapter 4
Path Drawer
--Developing Path Drawer V1.0

## Preface

In this chapter, we'll develop a `Path Drawer` module, based on `Polyline Drawer V1.0` developed in prior chapter. Here we'll only cover the features unique to the implementations of `Path Drawer`. For common aspects among interactive shape drawings for `Line`, `Polyline`, `Polygon`, and `Path`, please refer to previous chapters.

In later chapters, all these modules will be integrated and evolved into a sophisticated JavaFX `Shape` Drawing Tools.

From detailed descriptions and well-documented example codes excerpted from `Path Drawer V1.0`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0010_split_003.html_summary) section.

The complete development process of `Path Drawer V1.0` is characterized by the following steps:

*   [4.1 Create `PathDrawer` Class as Subclass of `Application`](#part0010_split_001.html_create-path-drawer)
    *   [4.1.1 Create an Instance of `Path`](#part0010_split_001.html_create-path)
    *   [4.1.2 Implement `onMouseDragStarted()` Method](#part0010_split_001.html_implement-on-mouse-darg-started)
    *   [4.1.3 Implement `OnMouseDragFinished()` method](#part0010_split_001.html_implement-on-mouse-darg-finished)
*   [4.2 Complete Source Codes of `PathDrawer` class](#part0010_split_002.html_complete-source-codes)
*   [4.3 Summary](#part0010_split_003.html_summary)

## 4.1 Create `PathDrawer` Class as Subclass of `Application`

The `Path` class, resides in `javafx.scene.shape` package, is one of direct subclasses of `Shape` class.

A `Path` is composed of multiple elements. Each element is type of `PathElement`, representing a basic geometric form such as line, arc, quadratic Bézier curve, cubic Bézier curve, etc. The `PathElement` is a direct subclass of `java.lang.Object`.

We use this constructor,

```
 public Path() 
```

to create an instance of `Path` with empty elements, then use this method provided in `Path` class,

```
 public final ObservableList<PathElement> getElements() 
```

to obtain a list which is type of `ObservableList<PathElement>`, and use the basic utilities, defined in `Collection` interface to add `PathElement` objects to the list.

Followings are direct subclasses of `PathElement`, objects of these types are valid to be added to a `Path`:

*   `ArcTo`

    Create an arc as path element, specifying radius X, radius Y, end X and end Y. The end point of last element is the start point of this arc.

*   `ClosePath`

    Close this path.

*   `CubicCurveTo`

    Create a cubic Bézier curve as path element, specifying two control points and an end point. The end point of last element is the start point of this Bézier curve.

*   `HLineTo`

    Create a horizontal line as path element, specifying end X coordinate. The line is drawn from the end point of last element to the specified X coordinate.

*   `LineTo`

    Create a line as path element, from end point of last element to the specified X, Y coordinates.

*   `MoveTo`

    Create an element by specifying X, Y coordinates, as the location to move to.

*   `QuadCurveTo`

    Create a quadratic Bézier curve as path element, specifying one control point and an end point. The end point of the last element is the start point of this Bézier curve.

*   `VLineTo`

    Create a vertical line as path element, specifying end Y coordinate. The line is drawn from the end point of last element to the specified Y coordinate.

Here's an example to create a hard-coded `Path` object which consists of 8 `PathElement`s, composed of 4 strokes representing a Chinese character:

Import Statements:

```
 import javafx.scene.shape.HLineTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.Path;
import javafx.scene.shape.QuadCurveTo;
```

Listing 4-1. Create a `Path` composed of 8 `PathElement`s (4 strokes in total):

```
 Path path = new Path();

    // Stroke 1:
    // draw a HLine from (87, 76) to (211, 76)
    MoveTo moveTo1 = new MoveTo(87.0f, 76.0f);
    HLineTo hLineTo1 = new HLineTo(211.0f);

    // Stroke 2:
    // draw a HLine from (93, 115) to (206, 115)
    MoveTo moveTo2 = new MoveTo(93.0f, 115.0f);
    HLineTo hLineTo2 = new HLineTo(206.0f);

    // Stroke 3:
    // draw a QuadCurve from (149, 76) to (86, 188)
    // control point at (156, 166) 
    MoveTo moveTo3 = new MoveTo(149.0f, 76.0f);
    QuadCurveTo quadCurveTo1 = new QuadCurveTo(156.0f, 166.0f, 86.0f, 188.0f);

    // Stroke 4:
    // Draw a QuadCurve from (149, 115) to (212, 188)
    // control point at (167, 173) 
    MoveTo moveTo4 = new MoveTo(149.0f, 115.0f);
    QuadCurveTo quadCurveTo2 = new QuadCurveTo(167.0f, 173.0f, 212.0f, 188.0f);

    path.getElements().addAll(
      moveTo1, hLineTo1, moveTo2, hLineTo2,
      moveTo3, quadCurveTo1, moveTo4, quadCurveTo2);

    path.setStrokeWidth(3.0);
```

Here's another way to create the same `Path` object:

Listing 4-2. Create a `Path` composed of 8 `PathElement`s (4 strokes in total):

```
 Path path = new Path();

    // Draw a HLine from (87, 76) to (211, 76)
    MoveTo moveTo1 = new MoveTo();
    moveTo1.setX(87.0f);
    moveTo1.setY(76.0f);
    HLineTo hLineTo1 = new HLineTo();
    hLineTo1.setX(211.0f);

    // Draw a HLine from (93, 115) to (206, 115)
    MoveTo moveTo2 = new MoveTo();
    moveTo2.setX(93.0f);
    moveTo2.setY(115.0f);
    HLineTo hLineTo2 = new HLineTo();
    hLineTo2.setX(206.0f);

    // Draw a QuadCurve from (149, 76) to (86, 188)
    // control point at (156, 166) 
    MoveTo moveTo3 = new MoveTo();
    moveTo3.setX(149.0f);
    moveTo3.setY(76.0f);
    QuadCurveTo quadCurveTo1 = new QuadCurveTo();
    quadCurveTo1.setControlX(156.0f);
    quadCurveTo1.setControlY(166.0f);
    quadCurveTo1.setX(86.0f);
    quadCurveTo1.setY(188.0f);

    // Draw a QuadCurve from (149, 115) to (212, 188)
    // control point at (167, 173) 
    MoveTo moveTo4 = new MoveTo();
    moveTo4.setX(149.0f);
    moveTo4.setY(115.0f);
    QuadCurveTo quadCurveTo2 = new QuadCurveTo();
    quadCurveTo2.setControlX(167.0f);
    quadCurveTo2.setControlY(173.0f);
    quadCurveTo2.setX(212.0f);
    quadCurveTo2.setY(188.0f);

    path.getElements().addAll(
      moveTo1, hLineTo1, moveTo2, hLineTo2,
      moveTo3, quadCurveTo1, moveTo4, quadCurveTo2);

    path.setStrokeWidth(3.0);
```

The following snapshot shows the rendering of the `Path` from codes in Listing 4-2:

Figure 4-1. Snapshot of the path created from above codes; it's a Chinese character composed of 4 strokes.

![](images/00012.jpeg "example_path.jpg")

Please notice that in above drawing the start point of each stroke is not the end point of its prior stroke because there is a `MoveTo` element preceding each stroke. The following snapshot illustrates the drawing order of strokes in the `Path` from codes in Listing 4-2:

Figure 4-2. Diagram of drawing order of strokes in the `Path` from codes in Listing 4-2.

![](images/00013.jpeg "stroke_order.jpg")

The following is another example to create a hard-coded `Path` composed of a `MoveTo`, a `HLineTo`, a `QuadCurveTo`, and a `LineTo`. It takes 3 strokes to draw the path, in which the end point of first stroke is the start point of second stroke, and the end point of second stroke is the start point of third stroke:

Import Statements:

```
 import javafx.scene.paint.Color;
import javafx.scene.shape.HLineTo;
import javafx.scene.shape.LineTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.Path;
import javafx.scene.shape.QuadCurveTo;
import javafx.scene.shape.StrokeLineCap;
import javafx.scene.shape.StrokeLineJoin;
```

Listing 4-3. Create a `Path` composed of 4 `PathElement`s (3 strokes in total):

```
 Path path = new Path();

    // 1st stroke: Draw a HLine from (120, 87) to (195, 87)
    MoveTo moveTo = new MoveTo();
    moveTo.setX(120.0f);
    moveTo.setY(87.0f);
    HLineTo hLineTo = new HLineTo();
    hLineTo.setX(195.0f);

    // 2nd stroke: Draw a QuadCurve from (195, 87) to (205, 170)
    // control point at (36, 201) 
    // (195, 87) is end point of first stroke
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    quadCurveTo.setControlX(36.0f);
    quadCurveTo.setControlY(201.0f);
    quadCurveTo.setX(205.0f);
    quadCurveTo.setY(170.0f);

    // 3rd stroke: Draw a Line from (205, 170) to (209, 149)
    // (205, 170) is end point of 2nd stroke
    LineTo lineTo = new LineTo();
    lineTo.setX(209.0f);
    lineTo.setY(149.0f);

    path.getElements().addAll(
      moveTo, hLineTo, quadCurveTo, lineTo);

    // Set values for some properties
    path.setStrokeLineCap(StrokeLineCap.ROUND);
    path.setStrokeLineJoin(StrokeLineJoin.BEVEL);
    path.setStrokeWidth(8.0);
    path.setStroke(Color.web("#A0522D"));
```

Please notice that, to make the path distinctive, we set values of several properties defined in `Shape` class:

`strokeLineCap`

This is a property of type `ObjectProperty<StrokeLineCap>` to specify end cap style of a line. `StrokeLineCap` is an `enum` type defines these constants: `BUTT`, `ROUND`, and `SQUARE`. Play around these values in your codes to apprehend differences among them. Default value is `SQUARE`.

`strokeLineJoin`

This is a property of type `ObjectProperty<StrokeLineJoin>` to specify join style between strokes. `StrokeLineJoin` is an `enum` type defines these constants: `BEVEL`, `MITER`, and `ROUND`. Play around these values in your codes to apprehend differences among them. Default value is `MITER`.

`strokeWidth`

This is a property of type `DoubleProperty` to specify the width of stroke. Default value is `0.0`.

`stroke`

This is a property of type `ObjectProperty<Paint>` to specify a color to paint the border of a shape. Default value is `Color.BLACK` for `Line`, `Polyline`, and `Path`; and `null` for the other shapes.

The following snapshot shows the rendering of the `Path` from codes in Listing 4-3:

Figure 4-3. Snapshot of the path created from codes in Listing 4-3; it's a Chinese character composed of 3 strokes.

![](images/00014.jpeg "example_path_2.jpg")

The following snapshot illustrates the drawing order of strokes in the `Path` from codes in Listing 4-3:

Figure 4-4. Diagram of drawing order of strokes in the `Path` from codes in Listing 4-3.

![](images/00015.jpeg "stroke_order_2.jpg")

Now, we'll demonstrate how to develop a `PathDrawer` application that interactively draws `Path` objects. The (X, Y) coordinates of points in each `PathElement` that assembles a `Path` are obtained dynamically through mouse pressed and mouse dragged events. To simplify the approach at this stage, we only implement two types of `PathElement`: `MoveTo` and `LineTo`. In next chapter, we'll demonstrate how to interactively draw a `Path` composed of `MoveTo` and `QuadCurveTo`.

To create `PathDrawer` class, we adopt the complete source codes of `PolylineDrawer` class, and make a little modification. The key differences are the implementations of two methods, `onMouseDragStarted()` and `onMouseDragFinished()`, to be described in later sections.

Following is the initial appearance of `PathDrawer` class, creating a `BorderPane` as the root of a `Scene`, and placing a `Pane` in the center of `BorderPane`:

Listing 4-4. Create `PathDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of `Scene`, and place `Pane` in the center of `BorderPane` as drawing board:

```
 package drawtool;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: PathDrawer.java
 * @author: Shufen Kuo
 *
 */
public class PathDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("PathDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

### 4.1.1 Create an Instance of `Path`

In general, both `Polyline` and `Path` are recognized as a `Shape` with multiple elements. A `Polyline`, a shape with multiple lines, is constructed by connecting a series of points in the given order; two adjacent lines are always connected. However two adjacent elements in a `Path` may not be connected because of the existence of `MoveTo` element. A `MoveTo` element simply advances the path to the specified X, Y coordinates without performing any drawing. A `Path` also plays an interesting role in JavaFX animations of `PathTransition` that transits a JavaFX `Node` along a specified `Path`.

To understand how to register event handlers using convenience methods, provided in `Node` class, to handle mouse events and key events, please read Section 1.2.1 [Register Event Handlers Using Convenience Methods](#part0007_split_002.html_convenience-method-mouse-key) and Section 1.4 [Get Key Code of Key Event](#part0007_split_004.html_key-code-key-event) in Chapter 1.

Following codes show a `Path` object created inside the event handler of `MOUSE_DRAGGED` event when the first mouse dragged event is detected:

Import Statements:

```
 import javafx.scene.shape.Path;
```

Listing 4-5. Register event handler of `MOUSE_DRAGGED` event, create an instance of `Path` when the first mouse dragged event is detected:

```
 drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Path();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });
```

### 4.1.2 Implement `onMouseDragStarted()` Method

The `onMouseDragStarted()` method is called from an event handler of `MOUSE_DRAGGED` event when the first dragged event occurs. It carries out the following tasks:

*   Create a `MoveTo` object:

    Set the x, y coordinates of this `MoveTo` element to the location where the mouse is pressed; this is the starting position to be referred later.

*   Create a `LineTo` object:

    Binds the x, y coordinates of this `LineTo` element to a `DoubleBinding` object which calculates the sum of starting position and translating distance.

*   Add `MoveTo` and `LineTo` to this path:

    Get the list of `PathElement` of this path, and add `MoveTo` and `LineTo` to it.

Following is the initial implementation of the `onMouseDragStarted()` Method.

Import Statements:

```
 import javafx.scene.shape.LineTo;
import javafx.scene.shape.MoveTo;
```

Listing 4-6. Implement `onMouseDragStarted()` Method, called from event handler of `MOUSE_DRAGGED` event:

```
 void onMouseDragStarted() {
    MoveTo moveTo = new MoveTo();
    moveTo.setX(startX.get());
    moveTo.setY(startY.get());

    LineTo lineTo = new LineTo();
    lineTo.xProperty().bind(startX.add(translateX));
    lineTo.yProperty().bind(startY.add(translateY));

    Path path = (Path)getShape();
    path.getElements().addAll(moveTo, lineTo);
  }
```

Now, let's make a little effort to enhance the above codes.

It's not necessarily to add a `MoveTo` element for each `MOUSE_PRESSED`—`MOUSE_DRAGGED`—`MOUSE_RELEASED` event cycle. First, we'll check if this is the beginning of a new path, since a `MoveTo` element is always needed for a new path. While for an existing path, we'll retrieve the last `LineTo` element, and verify its x, y coordinates to determine whether a `MoveTo` element is needed or not. If the x, y coordinates of this `LineTo` element is the location where the MOUSE_PRESSED event occurs, then there is no need to add a `MoveTo` element.

Here's the enhancement of the `onMouseDragStarted()` Method:

Import Statements:

```
 import javafx.scene.shape.LineTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.PathElement;
```

Listing 4-7. Enhance `onMouseDragStarted()` Method, retrieve the last `LineTo` element, and verify its x, y coordinates to determine if a `MoveTo` element is needed for this path:

```
 void onMouseDragStarted() {
    Path path = (Path)getShape();
    ObservableList<PathElement> list = path.getElements();
    // Check if this is the beginning of a new path
    if (list.size() > 1) {
      // This is not the beginning of a new path.
      // Check if a MoveTo is necessary.
      // Get the last LineTo and verify its x,y cooradinates.
      LineTo lineTo = (LineTo) list.get(list.size() - 1);
      if (lineTo.getX() != startX.get() ||
          lineTo.getY() != startY.get()) {
        // Need a MoveTo element
        MoveTo moveTo = new MoveTo();
        moveTo.setX(startX.get());
        moveTo.setY(startY.get());
        path.getElements().add(moveTo);
      }      
    } else {
      // This is a new path, must create a MoveTo
      MoveTo moveTo = new MoveTo();
      moveTo.setX(startX.get());
      moveTo.setY(startY.get());
      path.getElements().add(moveTo);
    }

    // Create a LineTo and add to list
    LineTo lineTo = new LineTo();
    lineTo.xProperty().bind(startX.add(translateX));
    lineTo.yProperty().bind(startY.add(translateY));

    path.getElements().add(lineTo);
  }
```

### 4.1.3 Implement `OnMouseDragFinished()` method

The `onMouseDragFinished()` Method is called from the event handler of `MOUSE_RELEASED` event.

It carries out the following tasks:

*   Get the list of `PathElement` of this path.
*   Retrieve the last `LineTo` element from the list.
*   Unbind the x, y coordinates of the last `LineTo` element.

A sequence of `MOUSE_DRAGGED` events followed by a `MOUSE_RELEASED` event completes the drawing of one `PathElement` in a `Path`.

Listing 4-8. Implement `onMouseDragFinished()` Method, called from event handler of `MOUSE_RELEASED` event:

```
 void onMouseDragFinished() {
    Path path = (Path)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (path != null) {    
      ObservableList<PathElement> list = path.getElements();
      // unbind the x, y location of the last lineTo element of the list
      if (list.size() > 1) {
         LineTo lineTo = (LineTo) list.get(list.size() - 1);
         lineTo.xProperty().unbind();
         lineTo.yProperty().unbind();
      }
    }
  }
```

## 4.2 Complete Source Codes of `PathDrawer` class

Here are the complete source codes. The changes, comparing to `PolylineDrawer` class in previous chapter, are shown in bold face:

Listing 4-9. Create `PathDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of scene, and place `Pane` in the center of `BorderPane` as a drawing board:

```
 package drawtool;

import javafx.application.Application;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.collections.ObservableList;
import javafx.event.EventHandler;
import javafx.event.EventType;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.LineTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.Path;
import javafx.scene.shape.PathElement;
import javafx.scene.shape.Shape;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: PathDrawer.java
 * (in directory: PathDrawer1.0/src/example1/drawtool/)
 * This JavaFX application implements path drawing
 * through consecutive mouse dragged events,
 * later will be integrated into a comprehensive drawing tool JFXDrawTools
 * 
 * For each MOUSE_PRESSED-MOUSE_DRAGGED-MOUSE_RELEASED event cycle,
 * a MoveTo element is created only if the location of mouse pressed event is
 * not the same as x, y coordinates of last LineTo element,
 * and a LineTo element is always created
 * When you finish all the elements of this path, hit the ENTER key to finalize it,
 * the next MOUSE_PRESSED event will start the first element of a new path
 * To cancel this path, hit the ESCAPE key
 *
 * @author: Shufen Kuo
 */
public class PathDrawer extends Application {

  // Keep track of the cursor locations while mouse event occurs
  // startX, startY hold locations of mouse pressed event
  DoubleProperty startX = new SimpleDoubleProperty();
  DoubleProperty startY = new SimpleDoubleProperty();

  // translateX, translateY hold the distance from dragged/moved location to the startX, startY
  DoubleProperty translateX = new SimpleDoubleProperty();
  DoubleProperty translateY = new SimpleDoubleProperty();

  // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    final Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get the starting mouse location
        startX.set(me.getX());
        startY.set(me.getY());
      }
    });

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Path();
            tmpShape.setStroke(Color.BLUE);
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted();
        }
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          onMouseDragFinished();
        }
      }
    });

    // Must set focusTraversable to true in order to handle KeyEvent, 
    // default is false.
    drawPane.setFocusTraversable(true);
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this shape
            System.out.format("Enter key hit%n");
            // Must call dragged finished method to unbind
            onMouseDragFinished();
            setShape(null);  // complete this shape
            break;
          case ESCAPE:
            // Hit Esc key to clear this shape
            System.out.format("Esc key hit%n");
            Shape s = getShape();
            if (s != null) {
              // Must call dragged finished method to unbind
              onMouseDragFinished();
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this shape
            }
            break;
        }       
      }
    });

    // Listener to observe the value changed of shape property,
    // add the shape to drawing board if a new shape is created.
    shape.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
      }
    });

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("PathDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  void onMouseDragStarted() {
    Path path = (Path)getShape();
    ObservableList<PathElement> list = path.getElements();
    // Check if this is the beginning of a new path
    if (list.size() > 1) {
      // This is not the beginning of a new path.
      // Check if a MoveTo is necessary.
      // Get the last LineTo and verify its x,y cooradinates.
      LineTo lineTo = (LineTo) list.get(list.size() - 1);
      if (lineTo.getX() != startX.get() ||
          lineTo.getY() != startY.get()) {
        // Need a MoveTo element
        MoveTo moveTo = new MoveTo();
        moveTo.setX(startX.get());
        moveTo.setY(startY.get());
        path.getElements().add(moveTo);
      }      
    } else {
      // This is a new path, must create a MoveTo
      MoveTo moveTo = new MoveTo();
      moveTo.setX(startX.get());
      moveTo.setY(startY.get());
      path.getElements().add(moveTo);
    }

    // Create a LineTo and add to list
    LineTo lineTo = new LineTo();
    lineTo.xProperty().bind(startX.add(translateX));
    lineTo.yProperty().bind(startY.add(translateY));

    path.getElements().add(lineTo);
  }

  void onMouseDragFinished() {
    Path path = (Path)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (path != null) {    
      ObservableList<PathElement> list = path.getElements();
      // unbind the x, y location of the last lineTo element of the list
      if (list.size() > 1) {
         LineTo lineTo = (LineTo) list.get(list.size() - 1);
         lineTo.xProperty().unbind();
         lineTo.yProperty().unbind();
      }
    }
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 4-5. Snapshot of various icon drawing using the `Path Drawer` module.

![](images/00016.jpeg "draw_icon.jpg")

Compile and run the application. Try these steps to test it:

1.  Move mouse to a location on the drawing board.
2.  Press the mouse and drag it around the drawing board.
3.  Release the mouse to create one line in a path.
4.  Press the mouse at the same location and drag it around the drawing board.
5.  Release the mouse to create another line connected to previous one.
6.  Repeat the previous two steps several times to create more lines connected one by one.
7.  Move mouse to a new location away from the end point of last line.
8.  Press the mouse and drag it around the drawing board.
9.  Release the mouse to create a line not connected to previous one.
10.  Repeat the previous three steps several times to create lines one by one not connected each other.
11.  Hit `Enter` key to finalize the drawing of one path.
12.  Try the similar moved-pressed-dragged-released steps several times, then hit `Esc` key to cancel the drawing of one path.

Output from Compiling and Running the Program in Command Line:

```
 Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\PathDrawer1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf DrawTool.jar drawtool

java -cp DrawTool.jar drawtool.PathDrawer

shape value changed: Path[elements=[], fill=null, fillRule=NON_ZERO,
stroke=0x0000ffff, strokeWidth=1.0]
Enter key hit
shape value changed: null
shape value changed: Path[elements=[], fill=null, fillRule=NON_ZERO,
stroke=0x0000ffff, strokeWidth=1.0]
Esc key hit
shape value changed: null
```

## 4.3 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Path` class, resides in `javafx.scene.shape` package, is a direct subclass of `Shape`. A `Path` is constructed with `PathElement`s.
    (See sections: [Create `PathDrawer` Class as Subclass of `Application`](#part0010_split_001.html_create-path-drawer) and [Create an Instance of `Path`](#part0010_split_001.html_create-path))
*   `PathElement`, an abstract class, resides in `javafx.scene.shape` package; its direct subclasses are: `ArcTo`, `ClosePath`, `CubicCurveTo`, `HLineTo`, `LineTo`, `MoveTo`, `QuadCurveTo`, `VLineTo`.
    (See [here](#part0010_split_001.html_path-element-class) and section [Implement `onMouseDragStarted()` Method](#part0010_split_001.html_implement-on-mouse-darg-started))
*   `public final ObservableList<PathElement> getElements()` method, provided in `Path` class, returns a list which is type of `ObservableList<PathElement>`. Use the basic utilities, defined in `Collection` interface to add `PathElement` objects to the list.
    (See [here](#part0010_split_001.html_get-elements) and [here](#part0010_split_001.html_get-elements-codes))
*   `HLineTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`, creates a horizontal line as path element, specifying end X coordinate, drawn from the end point of last element to the specified X coordinate.
    (See [here](#part0010_split_001.html_path-element-class))
*   `MoveTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`, creates a path element which moves the location to the specified x, y coordinates.
    (See [here](#part0010_split_001.html_path-element-class) and section [Implement `onMouseDragStarted()` Method](#part0010_split_001.html_implement-on-mouse-darg-started))
*   `LineTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`, creates a line element for a path, from the end point of last element to the specified x, y coordinates.
    (See sections: [Implement `onMouseDragStarted()` Method](#part0010_split_001.html_implement-on-mouse-darg-started) and [Implement `OnMouseDragFinished()` method](#part0010_split_001.html_implement-on-mouse-darg-finished))
*   `strokeLineCap` is a property of type `ObjectProperty<StrokeLineCap>`, defined in `Shape` class, to specify end cap style of a line.
    (See [here](#part0010_split_001.html_shape-properties-codes))
*   `StrokeLineCap` class, resides in `javafx.scene.shape` package, is an `enum` type defines these constants: `BUTT`, `ROUND`, and `SQUARE`.
    (See [here](#part0010_split_001.html_shape-properties-codes))
*   `strokeLineJoin` is a property of type `ObjectProperty<StrokeLineJoin>`, defined in `Shape` class, to specify join style between strokes.
    (See [here](#part0010_split_001.html_shape-properties-codes))
*   `StrokeLineJoin` class, resides in `javafx.scene.shape` package, is an `enum` type defines these constants: `BEVEL`, `MITER`, and `ROUND`.
    (See [here](#part0010_split_001.html_shape-properties-codes))
*   `strokeWidth` is a property of type `DoubleProperty` to specify the width of stroke. Default value is `0.0`.
    (See [here](#part0010_split_001.html_shape-properties-codes))
*   `stroke` is a property of type `ObjectProperty<Paint>` to specify a color to paint the border of a shape. Default value is `Color.BLACK` for `Line`, `Polyline`, and `Path`; and `null` for the other shapes.
    (See [here](#part0010_split_001.html_shape-properties-codes))

# Chapter 5
Quadratic Bézier Curve Drawer
--Developing Quadratic Bézier Curve Drawer V1.0

## Preface

In this chapter, we'll develop a `Bézier Curve Drawer` module, based on the `Path Drawer V1.0` developed in the preceding chapter. In the `Path Drawer` module, `MoveTo` and `LineTo`, both are types of `PathElement`, are employed to draw a path, while the `Bézier Curve Drawer` features the interactive creation of a path composed of `QuadCurveTo` element, a quadratic Bézier curve, drawn from the end point of last element in the path to the current mouse pressed location, with control point binds to the mouse dragged location.

From detailed descriptions and well-documented example codes excerpted from `Bézier Curve Drawer V1.0`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0011_split_007.html_summary) section.

The complete development process of `Bézier Curve Drawer V1.0` is characterized by the following steps:

*   [5.1 Create `BezierCurveDrawer` Class as Subclass of `Application`](#part0011_split_001.html_create-bezier-curve-drawer)
    *   [5.1.1 Introduce Quadratic Bézier Curves](#part0011_split_001.html_intro-quad-curve)
    *   [5.1.2 Register Event Handler of Mouse Dragged Event](#part0011_split_001.html_register-mouse-dragged-event)
    *   [5.1.3 Register Event Handler of Mouse Released Event](#part0011_split_001.html_register-mouse-released-event)
*   [5.2 Implement `handleMouseClicked(Pane` pane`)` method](#part0011_split_002.html_handle-mouse-clicked)
    *   [5.2.1 Add `MoveTo` Element to `Path`](#part0011_split_002.html_add-move-to)
    *   [5.2.2 Draw Circles to Represent Control Points of a Quadratic Bézier Curve](#part0011_split_002.html_draw-circles)
*   [5.3 Implement `onMouseDragStarted(Pane` pane`)` method](#part0011_split_003.html_implement-on-mouse-darg-started)
    *   [5.3.1 Add Straight Line `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-line-to)
    *   [5.3.2 Add Normal `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-quad-curve-to)
*   [5.4 Implement `OnMouseDragFinished(Pane` pane`)` method](#part0011_split_004.html_implement-on-mouse-darg-finished)
*   [5.5 Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event)
    *   [5.5.1 Implement `deleteLastPathElement(Pane` pane`, Path` path`)` Method](#part0011_split_005.html_implement-delete-last-element)
*   [5.6 The Complete Source Codes of `BezierCurveDrawer` class](#part0011_split_006.html_complete-source-codes)
*   [5.7 Summary](#part0011_split_007.html_summary)

## 5.1 Create `BezierCurveDrawer` Class as Subclass of `Application`

In previous chapter, we have presented examples of creating hard-coded `Path` composed of quadratic Bézier curves. Now, we'll demonstrate how to develop a `BezierCurveDrawer` application that interactively draws quadratic Bézier curves.

This application is a tool to create `Path` objects that consist of quadratic Bézier curves, through sequences of mouse events.

To create `BezierCurveDrawer` class, we adopt the complete source codes of `PathDrawer` class, and make necessary modifications. The key differences are the implementation of event handlers for `MOUSE_DRAGGED` and `MOUSE_RELEASED`.

Following is the initial appearance of `BezierCurveDrawer` class, creating a `BorderPane` as the root of a `Scene`, and placing a `Pane` in the center of `BorderPane`:

Listing 5-1. Create `BezierCurveDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of `Scene`, and place `Pane` in the center of `BorderPane` as drawing board:

```
package drawtool;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: BezierCurveDrawer.java
 * @author: Shufen Kuo
 *
 */
public class BezierCurveDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("BezierCurveDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

### 5.1.1 Introduce Quadratic Bézier Curves

Here we'll illustrate how to draw quadratic Bézier curves dynamically on a drawing board.

Three points are required to construct a quadratic Bézier curve:

1.  Start point
2.  End point
3.  Control point

Coordinates of these three points are obtained through interactive mouse events, here's how it works specifically:

1.  Initially, move the mouse to a desired location, make a mouse single clicked, the location of mouse clicked event becomes the start point. Refer to Step 1 in Figure 5-1, in which the start point is depicted as a red circle.
2.  Then, move the mouse to a new location, press the mouse (do not release it), the location of mouse pressed event becomes the end point. Refer to Step 2 in Figure 5-1.
3.  Now, drag the mouse around, the control point is bounded to the location of mouse dragged event. While you drag the mouse, the shape of curve keeps changing as the control point changed. Refer to Step 3 in Figure 5-1, in which the end point of the curve is depicted as a green circle, control point in blue circle. While the dragged event in process, we hide the mouse cursor to bring focus on the control point which tracks the location of mouse dragged.
4.  Finally, release the mouse. Refer to Step 4 in Figure 5-1, once the mouse is released, the control point and end point are hidden, and the red circle is move to the location of the end point of the curve.

Figure 5-1. Snapshots of illustrations of drawing a quadratic Bézier curve.

|  

&#124; ![](images/00017.jpeg) &#124;
&#124; Step 1 click mouse &#124;

 |  

&#124; ![](images/00018.jpeg) &#124;
&#124; Step 2 move to a location &#124;

 |  

&#124; ![](images/00019.jpeg) &#124;
&#124; Step 3 drag to draw curve &#124;

 |  

&#124; ![](images/00020.jpeg) &#124;
&#124; Step 4 release mouse &#124;

 |

The above sequence of actions draws a quadratic Bézier curve on a drawing board. Suppose this is the beginning of a new path, the `Path` now consists of two elements, a `MoveTo` followed by a `QuadCurveTo`.

A `MoveTo` element is created as the result of mouse clicked (at the end of Step 1 in Figure 5-1).

And a `QuadCurveTo` element is created when the dragging starts (at the beginning of Step 3 in Figure 5-1). The quadratic Bézier curve is drawn from the coordinates specified in the previous element, to the position where mouse is pressed.

There are two ways to create more quadratic Bézier curves added to the same path depicted in Figure 5-1:

1.  To create a new curve which is not connected to the previous curve:

    Repeat the sequence of actions, from Step 1 to Step 4.

2.  To create a new curve which is connected to the previous curve:

    Skip the mouse clicked event (depicted in Step 1), simply move the mouse to a new location and press the mouse without releasing it, drag it around until you are satisfied with the shape of curve, then release the mouse. The location of the mouse pressed event is the end point of a new curve, while the end point of previous curve is the start point of the new curve.

Figure 5-2 illustrates how to draw a new curve connecting to the previous curve. Step 1 to Step 4 renders the first curve. Step 5 to Step 7 renders the second curve.

Figure 5-2. Snapshots of illustrations of drawing two Bézier curve, connecting together.

|  

&#124; ![](images/00017.jpeg) &#124;
&#124; Step 1 click mouse &#124;

 |  

&#124; ![](images/00018.jpeg) &#124;
&#124; Step 2 move to a location &#124;

 |  

&#124; ![](images/00019.jpeg) &#124;
&#124; Step 3 drag to draw curve &#124;

 |  

&#124; ![](images/00020.jpeg) &#124;
&#124; Step 4 release mouse &#124;

 |
|  

&#124; ![](images/00021.jpeg) &#124;
&#124; Step 5 move to a location &#124;

 |  

&#124; ![](images/00022.jpeg) &#124;
&#124; Step 6 drag to draw curve &#124;

 |  

&#124; ![](images/00023.jpeg) &#124;
&#124; Step 7 release mouse &#124;

 |  |

A path constructed by this application consists of two types of elements:

*   `MoveTo`

    A `MoveTo` is created when a mouse clicked event occurs.

*   `QuadCurveTo`

    A `QuadCurveTo` is created when a mouse dragged event subsequent to a mouse pressed event occurs.

In some situation, you may require a straight line rendered in a path. Here's how to draw a line using `QuadCurveTo` class:

1.  Move mouse to the location of the start point, which is shown as a small red color circle on a drawing board. Refer to Step 1 in [Figure 5-3](#part0011_split_001.html_figure-5-3):

    The center of the red circle will become the start point of the line.

2.  Press the mouse without releasing it, and drag to the desired location. Refer to Step 2 in [Figure 5-3](#part0011_split_001.html_figure-5-3):

    When the dragged event first detected, a `QuadCurveTo` object is created, its `X`, `Y` properties as well as `controlX` and `controlY` properties are all bound to the location of mouse dragged event.

3.  Release the mouse. Refer to Step 3 in [Figure 5-3](#part0011_split_001.html_figure-5-3):

    The location of mouse released will become the end point of the line.

The above actions result in the rendering of a straight line, drawn from the center of the red circle to the location of mouse released event.

Figure 5-3. Snapshots of illustrations of drawing a straight line of quadratic Bézier curve.

|  

&#124; ![](images/00024.jpeg) &#124;
&#124; Step 1 move to red circle &#124;

 |  

&#124; ![](images/00025.jpeg) &#124;
&#124; Step 2 drag to draw line &#124;

 |  

&#124; ![](images/00026.jpeg) &#124;
&#124; Step 3 release mouse &#124;

 |

### 5.1.2 Register Event Handler of Mouse Dragged Event

Inside the event handler of `MOUSE_DRAGGED` event, a `Path` object is created if it does not exist yet, and the `onMouseDragStarted` method is called which undertakes major tasks described in later section.

Recall that the `startX` and `startY` are properties to hold the location of mouse pressed event, their values are set inside the event handler of mouse pressed event. `translateX` and `translateY` are properties to hold translating distance, calculated from where mouse is pressed to where mouse is dragged.

Here are source codes to register an event handler of `MOUSE_DRAGGED` event for a drawing board.

Listing 5-2. Register event handler of `MOUSE_DRAGGED` event, create an instance of `Path`, and call `onMouseDragStarted` method:

```
 drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Path();
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted(drawPane);
        }
      }
    });
```

### 5.1.3 Register Event Handler of Mouse Released Event

Inside the event handler of `MOUSE_RELEASED` event, we check whether this `MOUSE_RELEASED` event was preceded by any `MOUSE_DRAGGED` event. If it is not, then we consider this is a genuine mouse clicked event, the method defined to handle mouse clicked event, `handleMouseClicked(Pane` pane), is invoked. Otherwise, we consider this is the conclusion of a sequence of mouse dragged events, the `onMouseDragFinished(Pane` pane) method is invoked, in the same way as other shape drawers developed in previous chapters.

Please recall that the boolean variable `dragged` is set to `true` inside the event handler of `MOUSE_DRAGGED` event when the first dragged event occurs. It is reset to `false` in event handler of `MOUSE_RELEASED` event since dragged events have finished.

Listing 5-3. Register event handler of `MOUSE_RELEASED` event, call `handleMouseClicked` method if mouse released was not preceded by mouse dragged, otherwise call `onMouseDragFinished` method:

```
 drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          // This is the end of mouse dragged events
          onMouseDragFinished(drawPane);
        } else {
          // This is a genuine mouse clicked event
          handleMouseClicked(drawPane);
        }

      }
    });
```

## 5.2 Implement `handleMouseClicked(Pane` pane`)` method

The `handleMouseClicked(Pane` pane) method, called from event handler of `MOUSE_RELEASED` event when a genuine mouse clicked event has been detected, performs the following tasks:

*   Create an instance of `Path` if it doesn't exist yet.
*   Check whether this is the beginning of a new path or not. If it is, create an instance of `MoveTo`﹐a direct subclass of `PathElement`, set its `x`, `y` properties to the mouse clicked location, and add it to the path.
*   Otherwise, check whether the last element of the existing path is a `MoveTo` type or not. If it is, update its `x`, `y` properties. Otherwise, Create a `MoveTo`, set its `x`, `y` properties to the mouse clicked location, and add it to the path.

Here are source codes of the `handleMouseClicked(Pane` pane`)` method:

Import Statements:

```
import javafx.collections.ObservableList;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.Path;
import javafx.scene.shape.PathElement;
```

Listing 5-4. Implement `handleMouseClicked(Pane pane)` method, called from event handler of `MOUSE_RELEASED` event:

```
 void handleMouseClicked(Pane pane) {
    // Create a new Path if it does not exist yet
    if (getShape() == null)	{
      Shape tmpShape = new Path();
      shape.set(tmpShape);
    }
    Path path = (Path) getShape();
    // Add a MoveTo element if this is the beginning of a path,
    // otherwise, get the last element,
    // if last element is a MoveTo, update its x, y properties.
    // if last element is not a MoveTo, add a MoveTo to list 
    ObservableList<PathElement> list = path.getElements();
    if (list.size() > 0) {
      // This is not the beginning of a new path.
      // Get the last element
      PathElement element = list.get(list.size() - 1);
      if (element instanceof MoveTo) {
        // update its x, y
        MoveTo moveTo = (MoveTo) element;
        moveTo.setX(startX.get());
        moveTo.setY(startY.get());
        setStartPoint(startX.get(), startY.get());
      } else {
        // is not a MoveTo, add a MoveTo to list
        addMoveTo(pane, path);        
      }
    } else {
      // This is a new path, must create a MoveTo to begin a path
      addMoveTo(pane, path);        
    }
  }
```

### 5.2.1 Add `MoveTo` Element to `Path`

We define an `addMoveTo(Pane` pane`, Path` path`)` method to perform these tasks:

1.  Create an instance of `MoveTo` added to the specified path.
2.  Set the location of `MoveTo` to the location of start point.
3.  Draw a circle on the specified pane to represent the start point.

Besides invoking from the `handleMouseClicked(Pane` pane`)` method, the `addMoveTo` method may be invoked from the `onMouseDragStarted` method, refer to later section. Following is the implementation of the `addMoveTo` method.

Listing 5-5. Create a `MoveTo` adding to the specified path, set its x and y properties, and call `showStartPoint` method to draw a circle on the location of `MoveTo`:

```
 /**
   * Create a MoveTo, add it to the path
   * Its x, y properties are set to startX, startY
   * Show the start point
   */
  void addMoveTo(Pane pane, Path path) {
    MoveTo moveTo = new MoveTo();
    moveTo.setX(startX.get());
    moveTo.setY(startY.get());
    path.getElements().add(moveTo);
    showStartPoint(pane, startX.get(), startY.get());        
  }
```

### 5.2.2 Draw Circles to Represent Control Points of a Quadratic Bézier Curve

To distinguish points that control the shape of a quadratic Bézier curve, we draw circles in different colors to represent each of them. As mentioned at the beginning of this chapter, three points are needed to construct a quadratic Bézier curve, they are:

1.  Start point, drawn in red color.
2.  Control point, drawn in blue color.
3.  End point, drawn in green color.

Here are source codes to initialize these circles:

Import Statements:

```
import javafx.scene.shape.Circle;
```

Listing 5-6. Create circles and initialize their colors:

```
 // For displaying locations of 3 points required
  // to draw a quadratic Bezier curve
  Circle startPoint = new Circle(2.5f, Color.TRANSPARENT);
  Circle endPoint = new Circle(2.5f, Color.TRANSPARENT);
  Circle controlPoint = new Circle(3.5f, Color.TRANSPARENT);
  {
    startPoint.setStroke(Color.RED);
    endPoint.setStroke(Color.GREEN);
    controlPoint.setStroke(Color.BLUE);
  }
```

Utilities to deal with these circles are defined as follows:

Listing 5-7. Utilities of show points, hide points, set locations, etc.:

```
 void setStartPoint(double x, double y) {
    startPoint.setCenterX(x);
    startPoint.setCenterY(y);
  }

  void setEndPoint(double x, double y) {
    endPoint.setCenterX(x);
    endPoint.setCenterY(y);
  }

  void showStartPoint(Pane pane, double x, double y) {
    if (!pane.getChildren().contains(startPoint))
      pane.getChildren().add(startPoint);
    setStartPoint(x, y);
  }

  void showEndPoint(Pane pane) {
    if (!pane.getChildren().contains(endPoint))
      pane.getChildren().add(endPoint);
  }

  void showEndPoint(Pane pane, double x, double y) {
    if (!pane.getChildren().contains(endPoint))
      pane.getChildren().add(endPoint);
    setEndPoint(x, y);
  }

  void showControlPoint(Pane pane) {
    if (!pane.getChildren().contains(controlPoint))
      pane.getChildren().add(controlPoint);
  }

  void hideStartPoint(Pane pane) {
    pane.getChildren().remove(startPoint);
  }

  void hideEndPoint(Pane pane) {
    pane.getChildren().remove(endPoint);
  }

  void hideControlPoint(Pane pane) {
    pane.getChildren().remove(controlPoint);
  }
```

## 5.3 Implement `onMouseDragStarted(Pane` pane`)` method

The major tasks of `QuadCurveDrawer V1.0` are undertaken in the `onMouseDragStarted(Pane` pane`)` method, called from the event handler of `MOUSE_DRAGGED` event.

It carries out the following tasks:

*   Set cursor to `Cursor.NONE`:

    This is to bring focus on the control point which tracks the location of mouse dragged event.

*   Add a `MoveTo` object to a path:

    Set x, y coordinates of this `MoveTo` element to the location where the mouse is pressed.

    A `MoveTo` object is created here, only if the path contains empty element. In a normal procedure, a `MoveTo` is created as a result of mouse clicked event, refer to [Introduce Quadratic Bézier Curves](#part0011_split_001.html_intro-quad-curve) and [Implement `handleMouseClicked(Pane` pane`)` method](#part0011_split_002.html_handle-mouse-clicked).

    However, we allow novice users to start a new path by simply pressing the mouse and dragging it without initiating in advance a mouse clicked event.

*   Add a `QuadCurveTo` object that renders like a straight line to the path:

    Bind `x`, `y` properties as well as `controlX`, `controlY` properties of this `QuadCurveTo` element to the mouse dragged locations.

    If this dragged event occurs at the beginning of a new path, besides adding a `MoveTo` object, a straight line `QuadCurveTo` is also added.

    If this dragged event does not occur at the beginning of a new path, a straight line `QuadCurveTo` is created and added to the path only if the mouse pressed location, held in `startX` and `startY` properties, is within the area of the start point circle (Refer to Step 1 in [Figure 5-3](#part0011_split_001.html_figure-5-3)).

*   Add a normal `QuadCurveTo` object to the path:

    Bind `x` and `y` properties to the mouse pressed location, and bind `controlX` and `controlY` properties to the mouse dragged location.

    This is the normal situation, in which we obtain three distinct points to construct a `QuadCurveTo` element. That is, the curve's end point does not coincide with its start point, and the control point is bound to the mouse dragged location.

Here are source codes of the `onMouseDragStarted` Method.

Import Statements:

```
import javafx.scene.Cursor;
```

Listing 5-8. Implement `onMouseDragStarted` Method, called from event handler of `MOUSE_DRAGGED` event:

```
 void onMouseDragStarted(Pane pane) {
    // hide cursor
    pane.setCursor(Cursor.NONE);
    Path path = (Path)getShape();
    ObservableList<PathElement> list = path.getElements();
    // Check if this is the beginning of a new path
    if (list.size() == 0) {
      // This is a new path with empty element
      // Add a MoveTo followed by a QuadCurveTo
      // Since 3 points are needed to construct a curve,
      // here we only have two points,
      // the QuadCurveTo will look like a straight line,
      // with end point and control point both at the same location.
      addMoveTo(pane, path);
      addLineTo(pane, path);
    } else {
      // This is an existing path with elements in the list,
      // verify if mouse pressed location is inside the area of start point circle
      if (startPoint.contains(startX.get(), startY.get())) {
        // This is a special case,
        // startX, startY inside the area of start point circle,
        // we can only draw QuadCurveTo that looks like a straight line,
        // with end point and control point both at the same location.
        addLineTo(pane, path);
      }	else {
        // This is a normal case,
        // startX, startY are not within the bounds of start point,
        // Create a normal QuadCurveTo
        addQuadCurveTo(pane, path);
      }
    }
  }
```

### 5.3.1 Add Straight Line `QuadCurveTo` Element to `Path`

We define an `addLineTo(Pane` pane`, Path` path`)` method, called from the `onMouseDragStarted` method, to add a `QuadCurveTo` element rendered like a straight line to a `Path`. The method performs the following tasks:

1.  Create an instance of `QuadCurveTo` and add to a given path.
2.  Bind the curve's end point, specified in `x` and `y` properties, to a `DoubleBinding` object which calculates the sum of starting position and translating distance.
3.  Bind the curve's control point, specified in `controlX` and `controlY` properties, to a `DoubleBinding` object which calculates the sum of starting position and translating distance.
4.  Bind the center of control point circle, specified in `centerX` and `centerY` properties, to a `DoubleBinding` object which calculates the sum of starting position and translating distance.
5.  Bind the center of end point circle, specified in `centerX` and `centerY` properties, to a `DoubleBinding` object which calculates the sum of starting position and translating distance.
6.  Show control point circle and end point circle.

Here are source codes of the `addLineTo(Pane` pane`, Path` path`)` method:

Import Statements:

```
import javafx.beans.binding.DoubleBinding;
import javafx.scene.shape.QuadCurveTo;
```

Listing 5-9. Implement `addLineTo` Method, called from `onMouseDragStarted` method, create `QuadCurveTo`, do necessary binding, show control point circle, show end point circle:

```
 void addLineTo(Pane pane, Path path) {
    // Create a QuadCurveTo rendered like a straight line
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    path.getElements().add(quadCurveTo);
    // Create a DoubleBinding calculates the sum of
    // start position and translate distance
    DoubleBinding draggedX = startX.add(translateX);
    DoubleBinding draggedY = startY.add(translateY);
    // Bind end point of curve to the mouse dragged location
    quadCurveTo.xProperty().bind(draggedX);
    quadCurveTo.yProperty().bind(draggedY);
    // Bind control point of curve to the mouse dragged location
    quadCurveTo.controlXProperty().bind(draggedX);
    quadCurveTo.controlYProperty().bind(draggedY);
    // Take care of end point circle:
    // center of end point circle binds to dragged location
    endPoint.centerXProperty().bind(draggedX);
    endPoint.centerYProperty().bind(draggedY);
    showEndPoint(pane);
    // Take care of control point circle:
    // center of circle binds to dragged location
    controlPoint.centerXProperty().bind(draggedX);
    controlPoint.centerYProperty().bind(draggedY);
    showControlPoint(pane);
  }
```

### 5.3.2 Add Normal `QuadCurveTo` Element to `Path`

We define an `addQuadCurveTo(Pane` pane`, Path` path`)` method, called from the `onMouseDragStarted` method, to add a normal `QuadCurveTo` element to a `Path`. The method performs the following tasks:

1.  Create an instance of `QuadCurveTo` and add to a given path.
2.  Set the curve's end point, specified in `x` and `y` properties, to the mouse pressed location, specified in `startX` and `startY` properties.
3.  Set the center of end point circle at the mouse pressed location, and show it.
4.  Bind the curve's control point, specified in `controlX` and `controlY` properties, to a `DoubleBinding` object which calculates the sum of starting position and translating distance.
5.  Bind center of control point circle, specified in `centerX` and `centerY` properties, to a `DoubleBinding` object which calculates the sum of starting position and translating distance.
6.  Show control point circle, the location keeps on changing while mouse dragged in process.

Here are source codes of the `addQuadCurveTo(Pane` pane`, Path` path`)` method:

Listing 5-10. Implement `addQuadCurveTo` Method, called from `onMouseDragStarted` method, create `QuadCurveTo`, set x, y properties, do necessary binding, show control point circle, show end point circle:

```
 void addQuadCurveTo(Pane pane, Path path) {
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    path.getElements().add(quadCurveTo);

    // Set x, y properties of curve to mouse pressed location
    quadCurveTo.setX(startX.get());
    quadCurveTo.setY(startY.get());
    // Show end point circle at mouse pressed location 
    showEndPoint(pane, startX.get(), startY.get());

    // Create a DoubleBinding calculates the sum of
    // start position and translate distance
    DoubleBinding draggedX = startX.add(translateX);
    DoubleBinding draggedY = startY.add(translateY);

    // Bind control point of curve to mouse dragged location
    quadCurveTo.controlXProperty().bind(draggedX);
    quadCurveTo.controlYProperty().bind(draggedY);
    // Bind center of control point circle to dragged location
    controlPoint.centerXProperty().bind(draggedX);
    controlPoint.centerYProperty().bind(draggedY);
    // Show control point circle
    showControlPoint(pane);
  }
```

## 5.4 Implement `OnMouseDragFinished(Pane` pane`)` method

The `OnMouseDragFinished(Pane` pane`)` Method, called from an event handler of `MOUSE_RELEASED` event, wraps up the drawing of one `QuadCurveTo` element in a path.

The method accomplishes the following tasks:

1.  Restore the default cursor, it was set to none when the mouse dragged event started.
2.  Get the list of `PathElement` of this path, retrieve the last element from the list, and perform the following tasks on the last element (it must be an instance of `QuadCurveTo`):

    *   Do the necessary unbinding.

        If the curve is created by the `AddLineTo` method, it's a straight line `QuadCurveTo` element, properties related to control point and end point need do unbinding. If the curve is created by the `AddQuadCurveTo` method, it's a normal `QuadCurveTo` element, only properties related to control point need do unbinding.

    *   Hide the circle of end point.
    *   Hide the circle of control point.
    *   Move the circle of start point to the location of the end point of this curve.

The `MOUSE_DRAGGED` event followed by `MOUSE_RELEASED` event completes the drawing of one `PathElement` in a `Path`.

Here are source codes of the `OnMouseDragFinished(Pane` pane`)` method:

Listing 5-11. Implement `onMouseDragFinished` Method, called from event handler of `MOUSE_RELEASED` event:

```
 void onMouseDragFinished(Pane pane) {
    // Restore cursor
    pane.setCursor(Cursor.DEFAULT);
    Path path = (Path)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (path != null) {    
      ObservableList<PathElement> list = path.getElements();
      // The list has at least 2 elements created by either
      // addLineTo method or addQuadCurveTo method, 
      // the checking is redundant.
      if (list.size() > 0) {
        PathElement element = list.get(list.size() - 1);
        //The element must be a QuadCurveTo
        QuadCurveTo quadCurveTo = (QuadCurveTo) element;
        if (quadCurveTo.xProperty().isBound()) {          
          quadCurveTo.xProperty().unbind();
          quadCurveTo.yProperty().unbind();
        }
        if (quadCurveTo.controlXProperty().isBound()) {
          quadCurveTo.controlXProperty().unbind();
          quadCurveTo.controlYProperty().unbind();
        }
        // Take care of end point circle
        if (endPoint.centerXProperty().isBound()) {          
          endPoint.centerXProperty().unbind();
          endPoint.centerYProperty().unbind();
        }
        hideEndPoint(pane);
        // Take care of control point circle
        if (controlPoint.centerXProperty().isBound()) {
          controlPoint.centerXProperty().unbind();
          controlPoint.centerYProperty().unbind();
        }
        hideControlPoint(pane);
        // Take care of start point circle:
        // end point of this element now becomes the start point of
        // next new element.
        setStartPoint(quadCurveTo.getX(), quadCurveTo.getY());
      }
    }
  }
```

## 5.5 Register Event Handler of Key Pressed Event

Recall the acts of other shape drawing modules developed in previous chapters: press `Enter` key to finalize a sketch, and press `Esc` key to cancel a sketch. The `Bezier Curve Drawer` module does likewise. These tasks are accomplished inside the event handler of `KEY_PRESSED` event. Besides handling `Enter` key and `Esc` key, the `Bezier Curve Drawer` module takes care of additional key, the `Delete` key pressed event.

Very often, a user may be dissatisfied with a curve finished just now, but press `Esc` key to cancel the whole path is too much. We provide the functionality of `Delete` key, instead of deleting the whole path, it only deletes the last element from the path. Hit `Delete` key repeatedly will delete elements one by one, until the path contains no elements. However, you cannot delete any element from a path that has been finalized. A path is finalized as soon as `Enter` key is pressed.

Here are source codes to register event handler of `KEY_PRESSED` event:

Import Statements:

```
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
```

Listing 5-12. Register event handler of `KEY_PRESSED` event, handle `ENTER`, `ESCAPE` and `DELETE` key codes:

```
 drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this shape
            // Must call drag finished method to handle unbinding
            if (getShape() != null) {
              if (dragged)
                onMouseDragFinished(drawPane);
              hideStartPoint(drawPane);
              setShape(null);  // complete this shape
            }
            break;
          case ESCAPE:
            // Hit Esc key to clear this shape
            Shape s = getShape();
            if (s != null) {
              // Must call drag finished method to handle unbinding
              if (dragged)
                onMouseDragFinished(drawPane);
              hideStartPoint(drawPane);
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this shape
            }
            break;
          case DELETE:
            // Hit Delete key to delete the last element
            if (getShape() != null && !dragged) {
              // Do not allow the delete action if it is
              // in the middle of dragging events, that is,
              // if you hit the Delete key while dragging is in progress,
              // nothing happens.
              deleteLastPathElement(drawPane, (Path)getShape());
            }
            break;
        }       
      }
    });
```

Inside the above `handle` method, invoked when `KEY_PRESSED` event occurs, the actions for `ENTER` key and `ESCAPE` key are very similar to that of other shape drawers, the only difference is to call the `hideStartPoint` method to hide the red color circle that represents the start point.

We define the `deleteLastPathElement(Pane` pane`, Path` path`)` method to deal with action of `DELETE` key, this is a new feature available for `Bezier Curver Drawer` only.

### 5.5.1 Implement `deleteLastPathElement(Pane` pane`, Path` path`)` Method

The `deleteLastPathElement(Pane` pane`, Path` path`)` method, delete the last element of a given path, is called from an event handler of `KEY_PRESSED` event when `Delete` key is pressed.

Besides removing the last element from the list of `PathElement`, we need update the location of the circle that represents the start point. After removing the last element, if the list becomes empty, simply hide the circle of start point, otherwise, update the location of circle.

Here are source codes of the `deleteLastPathElement` method:

Listing 5-13. Implement `deleteLastPathElement` method, get the list of `PathElement` from a given path, remove the last element from list, update circle of start point status:

```
 void deleteLastPathElement(Pane pane, Path path) {
    ObservableList<PathElement> list = path.getElements();
    if (list.size() > 0) {
      list.remove(list.get(list.size() - 1));
      // If the resulting list is empty,
      // hide circle of start point
      if (list.size() == 0) {
        hideStartPoint(pane);
      }	else {
        PathElement element = list.get(list.size() - 1);
        if (element instanceof MoveTo) {
          // update center coordinates of circle of start point 
          MoveTo moveTo = (MoveTo) element;
          setStartPoint(moveTo.getX(), moveTo.getY());
        } else {
          // it must be a QuadCurveTo
          // update center coordinates of circle of start point 
          QuadCurveTo quadCurveTo = (QuadCurveTo) element;
          setStartPoint(quadCurveTo.getX(), quadCurveTo.getY());
        }
      }
    }
  }
```

## 5.6 The Complete Source Codes of `BezierCurverDrawer` class

Here are the complete source codes. The major differences, comparing to `PathDrawer` class in previous chapter, are shown in bold face:

Listing 5-14. Create `BezierCurveDrawer` class which extends `Application` class, override `start` method, create `BorderPane` as root node of scene, and place `Pane` in the center of `BorderPane` as a drawing board:

```
package drawtool;

import javafx.application.Application;
import javafx.beans.binding.DoubleBinding;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.collections.ObservableList;
import javafx.event.EventHandler;
import javafx.event.EventType;
import javafx.scene.Cursor;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.Path;
import javafx.scene.shape.PathElement;
import javafx.scene.shape.QuadCurveTo;
import javafx.scene.shape.Shape;
import javafx.scene.Scene;
import javafx.stage.Stage;

/**
 * File Name: BezierCurveDrawer.java
 * (in directory: QuadCurveDrawer1.0/src/example1/drawtool/)
 * This JavaFX application is an interactive drawing tool to draw
 * quadratic Bezier curves added to a path object
 * You can create as many paths as you like, 
 * when you finish all the elements of this path,
 * hit ENTER key to finalize it,
 * to cancel this path, hit ESCAPE key
 * If you are dissatisfied with the curve finished just now,
 * hit DELETE key to delete this curve
 * However, you cannot do DELETE action if you are in the middle of dragging 
 * The DELETE key deletes the last element from the path you are currently working on
 * Hit DELETE key repeatedly will delete elements one by one.
 * Once ENTER key is hit, a path is finalized, 
 * you cannot delete any element from a finalized path
 *
 * @author: Shufen Kuo
 */
public class BezierCurveDrawer extends Application {

  // Keep track of the cursor locations while mouse event occurs
  // startX, startY hold locations of mouse pressed event
  DoubleProperty startX = new SimpleDoubleProperty();
  DoubleProperty startY = new SimpleDoubleProperty();

  // translateX, translateY hold the distance from dragged/moved location to startX, startY
  DoubleProperty translateX = new SimpleDoubleProperty();
  DoubleProperty translateY = new SimpleDoubleProperty();

  // This is to hold the shape of current drawing 
  ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // This variable is set to true inside mouse dragged event handler
  // when the first mouse dragged event occurs,
  // and reset to false when mouse released event occurs.
  boolean dragged = false;

  // For displaying locations of 3 points required
  // to draw a quadratic Bezier curve
  Circle startPoint = new Circle(2.5f, Color.TRANSPARENT);
  Circle endPoint = new Circle(2.5f, Color.TRANSPARENT);
  Circle controlPoint = new Circle(3.5f, Color.TRANSPARENT);
  {
    startPoint.setStroke(Color.RED);
    endPoint.setStroke(Color.GREEN);
    controlPoint.setStroke(Color.BLUE);
  }

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    // We can't use Group object as drawPane here because
    // the size of group is not dynamically adjusted when size of rootPane changed
    final Pane drawPane = new Pane();
    rootPane.setCenter(drawPane);

    drawPane.setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Get the starting mouse location
        startX.set(me.getX());
        startY.set(me.getY());
      }
    });

    drawPane.setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        // Compute distance from mouse location to starting location
        double x2 = me.getX();
        double y2 = me.getY();
        translateX.set(x2 - startX.get());
        translateY.set(y2 - startY.get()); 
        if (!dragged) {
          // Did this only once
          if (getShape() == null)	{
            Shape tmpShape = new Path();
            shape.set(tmpShape);
          } 
          dragged = true;
          onMouseDragStarted(drawPane);
        }
      }
    });

    drawPane.setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        if (dragged) {
          dragged = false;
          // This is the end of mouse dragged events
          onMouseDragFinished(drawPane);
        } else {
          // This is a genuine mouse clicked event
          handleMouseClicked(drawPane);
        }

      }
    });

    // Must set focusTraversable to true in order to handle KeyEvent, 
    // default is false.
    drawPane.setFocusTraversable(true);
    drawPane.setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        KeyCode kc = ke.getCode();
        switch (kc) {
          case ENTER : 
            // Hit Enter key to finalize this shape
            // Must call drag finished method to handle unbinding
            if (getShape() != null) {
              if (dragged)
                onMouseDragFinished(drawPane);
              hideStartPoint(drawPane);
              setShape(null);  // complete this shape
            }
            break;
          case ESCAPE:
            // Hit Esc key to clear this shape
            Shape s = getShape();
            if (s != null) {
              // Must call drag finished method to handle unbinding
              if (dragged)
                onMouseDragFinished(drawPane);
              hideStartPoint(drawPane);
              drawPane.getChildren().remove(s);
              setShape(null);  // clear this shape
            }
            break;
          case DELETE:
            // Hit Delete key to delete the last element
            if (getShape() != null && !dragged) {
              // Do not allow the delete action if it is
              // in the middle of dragging events, that is,
              // if you hit the Delete key while dragging is in progress,
              // nothing happens.
              deleteLastPathElement(drawPane, (Path)getShape());
            }
            break;
        }       
      }
    });

    // Listener to observe the value changed of shape property,
    // add the shape to drawing board if a new shape is created.
    shape.addListener(new ChangeListener<Shape>() {
      @Override
      public void changed(ObservableValue o, Shape oldVal,
          Shape newVal) {
         //System.out.format("shape value changed: %s%n", newVal);
         if (newVal != null)
           drawPane.getChildren().add(newVal);
      }
    });

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("BezierCurveDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  /* Followings are utilities for displaying start point, end point, and
   * control point. Each of them is represented by a circle with 
   * different color.
   */

  void setStartPoint(double x, double y) {
    startPoint.setCenterX(x);
    startPoint.setCenterY(y);
  }

  void setEndPoint(double x, double y) {
    endPoint.setCenterX(x);
    endPoint.setCenterY(y);
  }

  void showStartPoint(Pane pane, double x, double y) {
    if (!pane.getChildren().contains(startPoint))
      pane.getChildren().add(startPoint);
    setStartPoint(x, y);
  }

  void showEndPoint(Pane pane) {
    if (!pane.getChildren().contains(endPoint))
      pane.getChildren().add(endPoint);
  }

  void showEndPoint(Pane pane, double x, double y) {
    if (!pane.getChildren().contains(endPoint))
      pane.getChildren().add(endPoint);
    setEndPoint(x, y);
  }

  void showControlPoint(Pane pane) {
    if (!pane.getChildren().contains(controlPoint))
      pane.getChildren().add(controlPoint);
  }

  void hideStartPoint(Pane pane) {
    pane.getChildren().remove(startPoint);
  }

  void hideEndPoint(Pane pane) {
    pane.getChildren().remove(endPoint);
  }

  void hideControlPoint(Pane pane) {
    pane.getChildren().remove(controlPoint);
  }

  /**
   * This method is called when DELETE key is hit
   */
  void deleteLastPathElement(Pane pane, Path path) {
    ObservableList<PathElement> list = path.getElements();
  	if (list.size() > 0) {
      list.remove(list.get(list.size() - 1));
      // If the resulting list is empty,
      // hide circle of start point
      if (list.size() == 0) {
        hideStartPoint(pane);
      }	else {
        PathElement element = list.get(list.size() - 1);
        if (element instanceof MoveTo) {
          // update center coordinates of circle of start point 
          MoveTo moveTo = (MoveTo) element;
          setStartPoint(moveTo.getX(), moveTo.getY());
        } else {
          // it must be a QuadCurveTo
          // update center coordinates of circle of start point 
          QuadCurveTo quadCurveTo = (QuadCurveTo) element;
          setStartPoint(quadCurveTo.getX(), quadCurveTo.getY());
        }
      }
    }
  }

  /**
   * Create a MoveTo, add it to the path
   * Its x, y properties are set to startX, startY
   * Show the start point
   */
  void addMoveTo(Pane pane, Path path) {
    MoveTo moveTo = new MoveTo();
    moveTo.setX(startX.get());
    moveTo.setY(startY.get());
    path.getElements().add(moveTo);
    showStartPoint(pane, startX.get(), startY.get());        
  }

  /**
   * Create a QuadCurveTo, add it to the path.
   * Since we only obtain coordinates of 2 points,
   * a straight line instead of a curve is rendered. 
   * Its x, y properties (the end point) are bound to
   * start point add translate distance,
   * do the same binding for controlX, controlY properties.
   * Bind centerX, centerY of end point circle
   * to start point add translate distance. 
   * Show end point.
   * Bind centerX, centerY of control point circle
   * to start point add translate distance. 
   * Show control point.
   */
  void addLineTo(Pane pane, Path path) {
    // Create a QuadCurveTo rendered like a straight line
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    path.getElements().add(quadCurveTo);
    // Create a DoubleBinding calculates the sum of
    // start position and translate distance
    DoubleBinding draggedX = startX.add(translateX);
    DoubleBinding draggedY = startY.add(translateY);
    // Bind end point of curve to the mouse dragged location
    quadCurveTo.xProperty().bind(draggedX);
    quadCurveTo.yProperty().bind(draggedY);
    // Bind control point of curve to the mouse dragged location
    quadCurveTo.controlXProperty().bind(draggedX);
    quadCurveTo.controlYProperty().bind(draggedY);
    // Take care of end point circle:
    // center of end point circle binds to dragged location
    endPoint.centerXProperty().bind(draggedX);
    endPoint.centerYProperty().bind(draggedY);
    showEndPoint(pane);
    // Take care of control point circle:
    // center of circle binds to dragged location
    controlPoint.centerXProperty().bind(draggedX);
    controlPoint.centerYProperty().bind(draggedY);
    showControlPoint(pane);
  }

  /**
   *
   */
  void addQuadCurveTo(Pane pane, Path path) {
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    path.getElements().add(quadCurveTo);

    // Set x, y properties of curve to mouse pressed location
    quadCurveTo.setX(startX.get());
    quadCurveTo.setY(startY.get());
    // Show end point circle at mouse pressed location 
    showEndPoint(pane, startX.get(), startY.get());

    // Create a DoubleBinding calculates the sum of
    // start position and translate distance
    DoubleBinding draggedX = startX.add(translateX);
    DoubleBinding draggedY = startY.add(translateY);

    // Bind control point of curve to mouse dragged location
    quadCurveTo.controlXProperty().bind(draggedX);
    quadCurveTo.controlYProperty().bind(draggedY);
    // Bind center of control point circle to dragged location
    controlPoint.centerXProperty().bind(draggedX);
    controlPoint.centerYProperty().bind(draggedY);
    // Show control point circle
    showControlPoint(pane);
  }

  void handleMouseClicked(Pane pane) {
    if (getShape() == null)	{
      Shape tmpShape = new Path();
      shape.set(tmpShape);
    }
    Path path = (Path) getShape();
    // Add a MoveTo element if this is the beginning of a path,
    // otherwise, get the last element,
    // if last element is a MoveTo, update its x, y properties.
    // if last element is not a MoveTo, add a MoveTo to list 
    ObservableList<PathElement> list = path.getElements();
    if (list.size() > 0) {
      // This is not the beginning of a new path.
      // Get the last element
      PathElement element = list.get(list.size() - 1);
      if (element instanceof MoveTo) {
        // update its x, y
        MoveTo moveTo = (MoveTo) element;
        moveTo.setX(startX.get());
        moveTo.setY(startY.get());
        setStartPoint(startX.get(), startY.get());
      } else {
        // is not a MoveTo, add a MoveTo to list
        addMoveTo(pane, path);        
      }
    } else {
      // This is a new path, must create a MoveTo to begin a path
      addMoveTo(pane, path);        
    }
  }

  void onMouseDragStarted(Pane pane) {
    // hide cursor
    pane.setCursor(Cursor.NONE);
    Path path = (Path)getShape();
    ObservableList<PathElement> list = path.getElements();
    // Check if this is the beginning of a new path
    if (list.size() == 0) {
      // This is a new path with empty element
      // Add a MoveTo followed by a QuadCurveTo
      // Since 3 points are needed to construct a curve,
      // here we only have two points,
      // the QuadCurveTo will look like a straight line,
      // with end point and control point both at the same location.
      addMoveTo(pane, path);
      addLineTo(pane, path);
    } else {
      // This is an existing path with elements in the list,
      // verify if mouse pressed location is inside the area of start point circle
      if (startPoint.contains(startX.get(), startY.get())) {
        // This is a special case,
        // startX, startY inside the area of start point circle,
        // we can only draw QuadCurveTo that looks like a straight line,
        // with end point and control point both at the same location.
        addLineTo(pane, path);
      }	else {
        // This is a normal case,
        // startX, startY are not within the bounds of start point,
        // Create a normal QuadCurveTo
        addQuadCurveTo(pane, path);
      }
    }
  }

  void onMouseDragFinished(Pane pane) {
    // Restore cursor
    pane.setCursor(Cursor.DEFAULT);
    Path path = (Path)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (path != null) {    
      ObservableList<PathElement> list = path.getElements();
      // The list has at least 2 elements created by either
      // addLineTo method or addQuadCurveTo method, 
      // the checking is redundant.
      if (list.size() > 0) {
        PathElement element = list.get(list.size() - 1);
        //The element must be a QuadCurveTo
        QuadCurveTo quadCurveTo = (QuadCurveTo) element;
        if (quadCurveTo.xProperty().isBound()) {          
          quadCurveTo.xProperty().unbind();
          quadCurveTo.yProperty().unbind();
        }
        if (quadCurveTo.controlXProperty().isBound()) {
          quadCurveTo.controlXProperty().unbind();
          quadCurveTo.controlYProperty().unbind();
        }
        // Take care of end point circle
        if (endPoint.centerXProperty().isBound()) {          
          endPoint.centerXProperty().unbind();
          endPoint.centerYProperty().unbind();
        }
        hideEndPoint(pane);
        // Take care of control point circle
        if (controlPoint.centerXProperty().isBound()) {
          controlPoint.centerXProperty().unbind();
          controlPoint.centerYProperty().unbind();
        }
        hideControlPoint(pane);
        // Take care of start point circle:
        // end point of this element now becomes the start point of
        // next new element.
        setStartPoint(quadCurveTo.getX(), quadCurveTo.getY());
      }
    }
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 5-4. Snapshot of various icon drawing using `Bézier Curve Drawer` module.

![](images/00027.jpeg "draw_icons.jpg")

Compile and run the application. Try these steps to test it:

1.  Move mouse to a location on the drawing board.
2.  Press the mouse and release it without dragging, this action creates a start point, a red circle is shown on the drawing board.
3.  Move mouse to another location and drag it around the drawing board to draw a curve.
4.  Release the mouse when you are satisfied with the shape of curve.
5.  Move mouse to another location, drag to draw another curve which connect to previous curve.
6.  Release the mouse when you are satisfied with the shape of this curve.
7.  Repeat previous two steps several times to draw more curves added to the path.
8.  If you are not satisfied with the curve you just drew, hit `Delete` key to delete it, and continue draw more curves.
9.  Now, try to draw a straight line: move mouse inside the area of red circle, drag the mouse to a location, then release the mouse.
10.  Draw more curves and lines added to the same path.
11.  Try to draw a curve not connected to previous curve:
    1.  Move the mouse to a location and press the mouse then release it without dragging, this action creates a start point.
    2.  Move the mouse to location and press the mouse, this is the end point.
    3.  Drag the mouse to draw a curve.
    4.  Finally, release the mouse when you are satisfied with the shape of this curve.
12.  Hit `Enter` key to finalize this path.
13.  Try the similar sequence of steps to create another path, then hit `Esc` key to cancel the drawing.

Output from Compiling and Running the Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\QuadCurveDrawer1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf DrawTool.jar drawtool

java -cp DrawTool.jar drawtool.BezierCurveDrawer
```

## 5.7 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Path` class, resides in `javafx.scene.shape` package, is a direct subclass of `Shape`. A `Path` is constructed with `PathElement`s.
    (See sections: [Create `BezierCurveDrawer` Class as Subclass of `Application`](#part0011_split_001.html_create-bezier-curve-drawer), [Register Event Handler of Mouse Dragged Event](#part0011_split_001.html_register-mouse-dragged-event), [Implement `handleMouseClicked(Pane` pane`)` method](#part0011_split_002.html_handle-mouse-clicked))
*   `PathElement`, an abstract class, resides in `javafx.scene.shape` package; its direct subclasses are: `ArcTo`, `ClosePath`, `CubicCurveTo`, `HLineTo`, `LineTo`, `MoveTo`, `QuadCurveTo`, `VLineTo`.
    (See [here](#part0011_split_002.html_handle-mouse-clicked-codes), [Add `MoveTo` Element to `Path`](#part0011_split_002.html_add-move-to), [here](#part0011_split_003.html_quad-curve-to-1), [here](#part0011_split_003.html_quad-curve-to-2), [here](#part0011_split_003.html_add-quad-curve-to-codes), and [Implement `deleteLastPathElement(Pane` pane`, Path` path`)` Method](#part0011_split_005.html_implement-delete-last-element))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See sections: [Register Event Handler of Mouse Dragged Event](#part0011_split_001.html_register-mouse-dragged-event), [Register Event Handler of Mouse Released Event](#part0011_split_001.html_register-mouse-released-event), and [Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event))
*   `MouseEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `MOUSE_CLICKED`, `MOUSE_DRAGGED`, `MOUSE_ENTERED`, `MOUSE_EXITED`, `MOUSE_MOVED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, etc., and provides methods such as `getX()`, `getY()`, etc., to get position of mouse cursor while event occurs.
    (See sections: [Register Event Handler of Mouse Dragged Event](#part0011_split_001.html_register-mouse-dragged-event) and [Register Event Handler of Mouse Released Event](#part0011_split_001.html_register-mouse-released-event))
*   Some of convenience methods provided in `Node` class to register `EventHandler`s to handle mouse events and key events.

    `public final void setOnMousePressed(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnMouseDragged(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnMouseReleased(EventHandler<? super MouseEvent>` value`)`

    `public final void setOnKeyPressed(EventHandler<? super KeyEvent>` value`)`

    (See sections: [Register Event Handler of Mouse Dragged Event](#part0011_split_001.html_register-mouse-dragged-event), [Register Event Handler of Mouse Released Event](#part0011_split_001.html_register-mouse-released-event), and [Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event))
*   `MoveTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`, creates a path element which moves the location to the specified x, y coordinates.
    (See [here](#part0011_split_002.html_handle-mouse-clicked-codes), and [Add `MoveTo` Element to `Path`](#part0011_split_002.html_add-move-to))
*   `QuadCurveTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`, creates a quadratic Bézier curve element for a path.
    (See [Introduce Quadratic Bézier Curves](#part0011_split_001.html_intro-quad-curve), [here](#part0011_split_003.html_quad-curve-to-1), [here](#part0011_split_003.html_quad-curve-to-2), and [here](#part0011_split_003.html_add-quad-curve-to-codes))
*   `public final ObservableList<PathElement> getElements()` method, provided in `Path` class, returns a list which is type of `ObservableList<PathElement>`. Use the basic utilities, defined in `Collection` interface to add `PathElement` objects to the list.
    (See [here](#part0011_split_002.html_handle-mouse-clicked-codes), [here](#part0011_split_003.html_on-mouse-drag-started-codes), [here](#part0011_split_004.html_on-mouse-drag-finished-codes), and [here](#part0011_split_005.html_delete-last-path-element-codes))
*   `void bind(ObservableValue<? extends T>` observable`)` and `void unbind()` are methods defined in `Property` interface, reside in `javafx.beans.property` package, to create/remove a unidirectional binding for this property.
    (See [Add Straight Line `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-line-to), [Add Normal `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-quad-curve-to) and [here](#part0011_split_004.html_unbind-in-drag-finished))
*   `DoubleBinding`, an abstract class resides in `javafx.beans.binding` package, extends `DoubleExpression` and implements `NumberBinding`. The `computeValue()` method need to be implemented in order to instantiate a `DoubleBinding` object.
    (See sections: [Add Straight Line `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-line-to) and [Add Normal `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-quad-curve-to))
*   `public DoubleBinding add(ObservableNumberValue` other`)` method, provided in `javafx.beans.binding.DoubleExpression` class, returns a new `DoubleBinding` that calculates the sum of this `NumberExpression` and the given `NumberExpression`.
    (See sections: [Add Straight Line `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-line-to) and [Add Normal `QuadCurveTo` Element to `Path`](#part0011_split_003.html_add-quad-curve-to))
*   `KeyEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `KEY_PRESSED`, `KEY_RELEASED`, `KEY_TYPED`, etc., and provides methods such as `getCode()`, `getCharacter()`, `getText()`, etc., to get information about keys in type of either `KeyCode`, or `String`. It also provides boolean methods such as `isControlDown()`, `isShiftDown()`, `isAltDown()`, etc., to verify whether some of modifier keys are pressed at the same time.
    (See section [Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event))
*   `KeyCode` class, resides in `javafx.scene.input` package, is an enumerated type defines constants for keys of keyboard, it covers letter keys (`A` to `Z`), digits keys(`DIGIT0` to `DIGIT9`), modifier keys(such as `CONTROL`, `SHIFT`, etc.), function keys, etc.
    (See section [Register Event Handler of Key Pressed Event](#part0011_split_005.html_register-key-pressed-event))

# Chapter 6
Basic Draw Tool
--Developing Shape Drawing Tools V1.0

## Preface

Up to this point, we have developed various shape drawers, each as an individual application. The first drawer is `Line Drawer`, and for the others, we simply adopt complete source codes of the drawer developed in preceding chapter, and make necessary modification. This is a makeshift to focus on implementation of interactively drawing each different shape, derived from `Shape` class, such as `Line`, `Polyline`, `Polygon`, etc. Shapes are drawn on a drawing board by means of mouse dragged events; major differences of codes are mostly embedded in event handlers of mouse dragged events.

In this chapter, to avoid tediously modifying existing codes as well as to simplify developing process of any new shape drawing application, we develop a package named `drawtool` which contains a useful set of comprehensive shape drawing APIs. Initially, it consists of two classes, `ShapeDrawer` and `DrawPane`.

`ShapeDrawer`, the base class for all drawers, defines properties of rendering shapes and necessary methods to draw shapes on a drawing board. While `DrawPane`, a subclass of `Pane`, as a drawing board, defines required variables and registers event handlers to handle events significant to draw shapes interactively on it.

We'll also show you how to apply these drawing APIs to simplify developments of interactive drawing applications, such as `Rectangle Drawer`, `Circle Drawer`, and `Ellipse Drawer`.

From detailed descriptions and well-documented example codes excerpted from developments of `Shape Drawing Tools V1.0` as well as shape drawing applications, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0012_split_004.html_summary) section.

The complete development process of `Shape Drawing Tools V1.0` is characterized by the following steps:

*   [6.1 Create `ShapeDrawer` Class](#part0012_split_001.html_create-shape-drawer)
    *   [6.1.1 Define Properties](#part0012_split_001.html_define-properties-shape-drawer)
    *   [6.1.2 Define Methods](#part0012_split_001.html_define-methods-shape-drawer)
    *   [6.1.3 Complete Source Codes of `ShapeDrawer` class](#part0012_split_001.html_complete-source-codes-shape-drawer)
*   [6.2 Create `DrawPane` Class](#part0012_split_002.html_create-draw-pane)
    *   [6.2.1 Define Properties](#part0012_split_002.html_define-properties-draw-pane)
    *   [6.2.2 Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers)
    *   [6.2.3 Define `drawOnMouseDragged` Method](#part0012_split_002.html_define-draw-on-mouse-dragged)
    *   [6.2.4 Take Default Actions for `ENTER` Key, `ESCAPE` Key and `DELETE` Key](#part0012_split_002.html_handle-key-codes)
    *   [6.2.5 Define Constructor with a Parameter of Type `ShapeDrawer`](#part0012_split_002.html_constructor-with-arg)
    *   [6.2.6 Complete Source Codes of `DrawPane` class](#part0012_split_002.html_complete-source-codes-draw-pane)
*   [6.3 Develop Drawer Applications Using Draw Tool APIs](#part0012_split_003.html_develop-drawers)
    *   [6.3.1 Create `RectangleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-rectangle-drawer-class)
    *   [6.3.2 Create `CircleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-circle-drawer-class)
    *   [6.3.3 Create `EllipseDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-ellipse-drawer-class)
*   [6.4 Summary](#part0012_split_004.html_summary)

## 6.1 Create `ShapeDrawer` Class

`ShapeDrawer` is the base class for all drawers that draw shapes by dragging the mouse around a drawing board. It defines required variables and provides basic methods to facilitate developments of shape drawing applications.

### 6.1.1 Define Properties

Followings are properties defined within `ShapeDrawer` class to specify appropriate attributes to render a shape.

`shapeClass`

A property of type `ObjectProperty<Class<? extends Shape>>` to specify the class of a shape to be drawn on a drawing board.

`shape`

A property of type `ObjectProperty<Shape>` to temporarily hold a shape object drawn on a drawing board.

`strokeColor`

A property of type `ObjectProperty<Color>` to specify a color object used to paint the border of a shape.

`fillColor`

A property of type `ObjectProperty<Color>` to specify a color object used to fill the interior of a shape.

The value of `shapeClass` is set in the constructor as below:

```
 public ShapeDrawer(Class<? extends Shape> sc) {
    shapeClass.set(sc);
  }
```

For instance, to instantiate a `ShapeDrawer` which draws `Rectangle` shapes on a drawing board through mouse dragged events, you pass `Rectangle.class` as a parameter to the constructor.

If the value of `shapeClass` property is not set, that is, if the value is `null`, no shape will be drawn when mouse dragged events occur on a drawing board.

Following snippets of codes define required properties in `ShapeDrawer` class:

Import Statements:

```
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.scene.paint.Color;
import javafx.scene.shape.Shape;
```

Listing 6-1. Define properties in `ShapeDrawer` class:

```
public abstract class ShapeDrawer {

  public ObjectProperty<Class<? extends Shape>> shapeClass =
    new SimpleObjectProperty<>();
  public static ObjectProperty<Shape> shape =
    new SimpleObjectProperty<>();

  public static ObjectProperty<Color> strokeColor =
    new SimpleObjectProperty<>(Color.GREENYELLOW);
  public static ObjectProperty<Color> fillColor = 
    new SimpleObjectProperty<>(Color.TRANSPARENT);

     ...

}
```

Following snippets of codes are utilities provided in `ShapeDrawer` class to manipulate above declared properties:

Listing 6-2. Provide utilities to manipulate properties:

```
 public Class<? extends Shape> getShapeClass() {
    return shapeClass.get();
  }

  public void setShapeClass(Class<? extends Shape> value) {
    shapeClass.set(value);
  }

  public ObjectProperty<Class<? extends Shape>> shapeClassProperty() {
    return shapeClass;
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  public Color getStrokeColor() {
    return strokeColor.get();
  }

  public void setStrokeColor(Color value) {
    strokeColor.set(value);
  }

  public ObjectProperty<Color> strokeColorProperty() {
    return strokeColor;
  }

  public Color getFillColor() {
    return fillColor.get();
  }

  public void setFillColor(Color value) {
    fillColor.set(value);
  }

  public ObjectProperty<Color> fillColorProperty() {
    return fillColor;
  }
```

### 6.1.2 Define Methods

`ShapeDrawer` is an abstract class. It defines two abstract methods as follows:

Listing 6-3. Define abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane);
  public abstract void onMouseDragFinished(DrawPane drawPane);
```

A parameter passed to both methods is type of `DrawPane`, a class providing functionality of a drawing board which will be discussed later in this chapter.

The `onMouseDragStarted` method, invoked when a mouse dragged event occurs, handles user defined actions. Please notice that it is invoked only once as soon as the first dragged event is detected.

The `onMouseDragFinished` method is invoked when mouse dragged events completed by a mouse released event.

Here's how it works to draw a shape interactively on a drawing board: When a mouse pressed event is followed by a mouse dragged event, a shape of `shapeClass`, a property specifies which shape to be drawn, is created and displayed on a drawing board, the `onMouseDragStarted` method is then invoked. Various properties of a shape may be altered according to specifications set by an application. When a sequence of drag events is ended by a mouse released event, the `onMouseDragFinished` method is invoked. In short, to complete drawing of one shape, it takes following mouse events: a mouse pressed event, followed by a sequence of mouse dragged events, and ended by a mouse released event.

Here is an example of creating an instance of `ShapeDrawer` which draws rectangle shapes, specifying `Rectangle.class` as a parameter passed to the constructor, and providing implementations of two abstract methods:

Listing 6-4. Define `newRectangleDrawer()` method which returns an instance of `ShapeDrawer` to draw rectangle shapes on a drawing board, creating `DoubleBinding` to compute values for x, y, width and height properties of a rectangle, calling the `bind(Observable... dependencies)` method defined in `DoubleBinding` class to observe value changes of dependencies for this `DoubleBinding` object, calling `bind` method to bind two observable values, and calling `unbind` method to remove bindings:

```
 ShapeDrawer newRectangleDrawer() {
    return new ShapeDrawer(Rectangle.class) {
      @Override
      public void onMouseDragStarted(final DrawPane drawPane) {

        Rectangle rect = (Rectangle)getShape();

        DoubleBinding xB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty());
          }

          @Override
          protected double computeValue() {
          return (drawPane.getDragX() < 0.0)
              ? drawPane.getStartX() + drawPane.getDragX() : drawPane.getStartX();
          }
        };

        DoubleBinding yB = new DoubleBinding() {
          {
            super.bind(drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            return (drawPane.getDragY() < 0.0)
                ? drawPane.getStartY() + drawPane.getDragY() : drawPane.getStartY();
          }
        };

        DoubleBinding wB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragX());
          }
        };

        DoubleBinding hB = new DoubleBinding() {
          {
            super.bind(drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragY());
          }
        };

        rect.xProperty().bind(xB);
        rect.yProperty().bind(yB);
        rect.widthProperty().bind(wB);
        rect.heightProperty().bind(hB);   
      }

      @Override
      public void onMouseDragFinished(final DrawPane drawPane) {
        Rectangle rect = (Rectangle)getShape();
        if (rect != null) {
          rect.xProperty().unbind();
          rect.yProperty().unbind();
          rect.widthProperty().unbind();
          rect.heightProperty().unbind();
        }
      }
    };
  } 
```

Please note that, inside the `onMouseDragStarted` method from the preceding listing, we have starting point, `x` coordinate and `y` coordinate, of a rectangle shape bind to x location and y location of mouse pressed event, which is specified respectively in `startX` and `startY` properties, defined in `DrawPane` class. Likewise, we have `width` and `height` of a rectangle shape bind to translate x and translate y of mouse dragged event, which is specified respectively in `dragX` and `dragY` properties, also defined in `DrawPane` class. As a result of properties bindings, you will see the ending point of a rectangle is adjusted constantly to coincide with the current location of mouse, while the mouse is dragged around a drawing board.

To finish up drawing of one rectangle, we need to do unbinding, it is done inside the `onMouseDragFinished` method, invoked as soon as a mouse released event occurs to end the sequence of mouse dragged events.

### 6.1.3 Complete Source Codes of `ShapeDrawer` class

Here are complete source codes of `ShapeDrawer` class.

Listing 6-5. Create `ShapeDrawer` Class:

```
package drawtool;

import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.scene.paint.Color;
import javafx.scene.shape.Shape;

/**
 * File Name: ShapeDrawer.java
 * (in directory: DrawTool1.0/src/example1/drawtool/)
 * ShapeDrawer is the base class for all drawers which draw shapes on a drawing board
 * It provides basic methods to facilitate the development of shape drawing applications
 * A shape is drawn on a drawing board by mouse dragged events 
 *
 * shapeClass is a property which specifies the shape to be drawn on a drawing board
 * If the value is not set, no shape will be drawn when mouse dragged events occur
 * on the drawing board 
 * See the following two examples:
 *   The LineDrawer is a subclass of ShapeDrawer, the value of shapeClass is set
 *   to Line.class in the constructor of LineDrawer
 *   The ShapeMover is a subclass of ShapeDrawer, the value of shapeClass is set to null,
 *   therefore, no shape will be drawn when mouse is dragged
 *   The ShapeMover is to move the existing shapes when mouse is dragged on it
 *
 * shape is a property to temporarily hold the shape drawn on a drawing board
 *
 * strokeColor/fillColor are properties to hold value of stroke/fill properties of
 *   a shape to be drawn on a drawing board 
 * 
 * The following abstract methods must be implemented by a subclass of ShapeDrawer:
 *   public abstract void onMouseDragStarted(DrawPane drawPane)
 *   public abstract void onMouseDragFinished(DrawPane drawPane)
 *
 * Followings are methods that do nothing, they can be overridden by a subclass of ShapeDrawer:
 *   public void handleMouseClicked(DrawPane drawPane) {}
 *   public void handleDeleteKeyPressed(DrawPane drawPane) {}
 *   public void clean(DrawPane drawPane) {}
 *
 * @author: Shufen Kuo
 */
public abstract class ShapeDrawer {

  /* Declare variables */

  public ObjectProperty<Class<? extends Shape>> shapeClass =
    new SimpleObjectProperty<>();
  public ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // basic properties for rendering shape
  public ObjectProperty<Color> strokeColor =
    new SimpleObjectProperty<>(Color.GREENYELLOW);
  public ObjectProperty<Color> fillColor =
    new SimpleObjectProperty<>(Color.TRANSPARENT);

  /* Define abstract methods */

  public abstract void onMouseDragStarted(DrawPane drawPane);
  public abstract void onMouseDragFinished(DrawPane drawPane);

  public ShapeDrawer(Class<? extends Shape> sc) {
    shapeClass.set(sc);
  }

  /* Define methods that do nothing */

  public void handleMouseClicked(DrawPane drawPane) {}
  public void handleDeleteKeyPressed(DrawPane drawPane) {}
  public void clean(DrawPane drawPane) {}

  /* Utilities to access properties */

  public Class<? extends Shape> getShapeClass() {
    return shapeClass.get();
  }

  public void setShapeClass(Class<? extends Shape> value) {
    shapeClass.set(value);
  }

  public ObjectProperty<Class<? extends Shape>> shapeClassProperty() {
    return shapeClass;
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  public Color getStrokeColor() {
    return strokeColor.get();
  }

  public void setStrokeColor(Color value) {
    strokeColor.set(value);
  }

  public ObjectProperty<Color> strokeColorProperty() {
    return strokeColor;
  }

  public Color getFillColor() {
    return fillColor.get();
  }

  public void setFillColor(Color value) {
    fillColor.set(value);
  }

  public ObjectProperty<Color> fillColorProperty() {
    return fillColor;
  }

}
```

## 6.2 Create `DrawPane` Class

The `Pane` class, extends `javafx.scene.layout.Region`, does not impose automatic layout on its children, and is best adapted as a drawing board. Therefore, we create `DrawPane` class, as a direct subclass of `Pane` class, to define required variables, and register event handlers to handle events significant to draw shapes interactively.

Read more about `Pane` class in Chapter 1 Line Drawer Section 1.1.1 [Add Pane as Drawing Board in the Center of BorderPane](#part0007_split_001.html_pane-as-drawing-board).

### 6.2.1 Define Properties

Followings are properties defined within `DrawPane` class for drawing a shape when a mouse dragged event occurs.

`startX`

A property of type `DoubleProperty` to specify X location of a mouse pressed event.

`startY`

A property of type `DoubleProperty` to specify Y location of a mouse pressed event.

`dragX`

A property of type `DoubleProperty` to specify X distance calculated from the current mouse dragged location to `startX`. `startX` is X location of a mouse pressed event which occurs prior to mouse dragged events.

`dragY`

A property of type `DoubleProperty` to specify Y distance calculated from the current mouse dragged location to `startY`. `startY` is Y location of a mouse pressed event which occurs prior to mouse dragged events.

`dragged`

A property of type `BooleanProperty` to specify whether a dragged event occurs right after a mouse pressed event. Its value is initialized to `false`, and is set to `true` once a mouse dragged event detected. It is reset to `false` as soon as a sequence of dragged events completed, that is, when mouse dragged events are ended by a mouse released event.

`drawer`

A property of type `ObjectProperty<ShapeDrawer>` to specify the current draw tool of a drawing board. An application may create multiple drawers and switch between them dynamically as required.

Following snippets of codes define required properties in `DrawPane` class:

Import Statements:

```
import javafx.beans.property.BooleanProperty;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleBooleanProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.scene.layout.Pane;
```

Listing 6-6. Define properties:

```
public class DrawPane extends Pane {

  /* Declare variables */

  public static DoubleProperty startX = new SimpleDoubleProperty();
  public static DoubleProperty startY = new SimpleDoubleProperty();
  public static DoubleProperty dragX = new SimpleDoubleProperty();
  public static DoubleProperty dragY = new SimpleDoubleProperty();

  public static BooleanProperty dragged = new SimpleBooleanProperty();

  public ObjectProperty<ShapeDrawer> drawer = new SimpleObjectProperty<>();

     ...

}
```

Following codes are utilities provided in `DrawPane` class to manipulate above declared properties:

Listing 6-7. Provide utilities to manipulate properties:

```
 public void setDrawer(ShapeDrawer value) {
    drawer.set(value);
  }

  public ShapeDrawer getDrawer() {
    return drawer.get();
  }

  public ObjectProperty<ShapeDrawer> drawerProperty() {
    return drawer;
  }

  public boolean isDragged() {
    return dragged.get();
  }

  public void setDragged(boolean value) {
    dragged.set(value);
  }

  public BooleanProperty draggedProperty() {
    return dragged;
  }

  public double getStartX() {
    return startX.get();
  }

  public void setStartX(double value) {
    startX.set(value);
  }

  public DoubleProperty startXProperty() {
    return startX;
  }

  public double getStartY() {
    return startY.get();
  }

  public void setStartY(double value) {
    startY.set(value);
  }

  public DoubleProperty startYProperty() {
    return startY;
  }
  public double getDragX() {
    return dragX.get();
  }

  public void setDragX(double value) {
    dragX.set(value);
  }

  public DoubleProperty dragXProperty() {
    return dragX;
  }

  public double getDragY() {
    return dragY.get();
  }

  public void setDragY(double value) {
    dragY.set(value);
  }

  public DoubleProperty dragYProperty() {
    return dragY;
  } 
```

### 6.2.2 Register Event Handlers inside the Default Constructor

`DrawPane` class registers event handlers to handle the following types of events: `MOUSE_PRESSED`, `MOUSE_DRAGGED`, `MOUSE_RELEASED` and `KEY_PRESSED`. Simply handling these events allows us to draw shapes interactively on a drawing board with ease.

Here is the default constructor of `DrawPane` within which all required event handlers are registered using convenience methods provided in `Node` class:

Listing 6-8. Define default constructor to register event handlers:

```
 public DrawPane() {
    setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMousePressed(me);
      }
    });

    setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseDragged(me);
      }
    });

    setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseReleased(me);
      }
    });

    // set focusTraversable property to true in order to handle KeyEvent, 
    // default is false.
    setFocusTraversable(true);
    setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        drawOnKeyPressed(ke);
      }
    });
  }
```

### 6.2.3 Define `drawOnMouseDragged` Method

A shape is created and set as the value of `shape` property, defined in `ShapeDrawer` class, as soon as a mouse dragged event is detected. We define the `drawOnMouseDragged` method to carry out these tasks. it is invoked from the `handle` method of an event handler registered for `MOUSE_DRAGGED` event. Here's the implementation of the `drawOnMouseDragged` method:

Listing 6-9. Define `drawOnMouseDragged` method to handle mouse dragged event, set value for `dragX` property and `dragY` property, create a shape object and set as value of `shape` property that is defined in `ShapeDrawer` class, and invoke `onMouseDragStarted` method also defined in `ShapeDrawer` class:

```
 protected void drawOnMouseDragged(MouseEvent me) {
    setDragX(me.getX() - getStartX());
    setDragY(me.getY() - getStartY()); 
    if (!isDragged()) {
      // Did this only once, and create the temporary shape only once
      // for each PRESSED-DRAGGED-RELEASED event cycle. 
      if (getDrawer() != null && getDrawer().getShapeClass() != null) {
        ShapeDrawer tool = getDrawer();
        Shape sketch = tool.getShape();
        if (sketch == null ||
            !tool.getShapeClass().isInstance(sketch)) {
          try {
            Shape tmpShape = tool.getShapeClass().newInstance();
            tmpShape.setFill(tool.getFillColor());
            tmpShape.setStroke(tool.getStrokeColor());
            tool.setShape(tmpShape);
            getChildren().add(tmpShape);
          } catch (InstantiationException | IllegalAccessException ex) {
          }
        }
      } 
      setDragged(true);
      // onMouseDragStarted method, defined in ShapeDrawer, is called from
      // event handler that handles MOUSE_DRAGGED type of mouse event,
      // it is called only once,
      // at the first time mouse dragged event is detected.
      if (getDrawer() != null)
        getDrawer().onMouseDragStarted(this);
    }
  }
```

These major tasks are carried out within the `drawOnMouseDragged` method:

1.  Calculates translating distance, from current mouse dragged location to mouse pressed location, and stores in `dragX` property and `dragY` property respectively.
2.  Creates a shape when dragged action starts, the `getShapeClass()` method is invoked to determine which shape to be created.
3.  Invokes the `onMouseDragStarted` method which is abstract defined in `ShapeDrawer` class.

Here's the location where the `drawOnMouseDragged` method is called:

```
 setOnMouseDragged(new EventHandler() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseDragged(me);
      }
    }); 
```

### 6.2.4 Take Default Actions for `ENTER` Key, `ESCAPE` Key and `DELETE` Key

`DrawPane` class registers event handler to handle `KEY_PRESSED` event type of key events. Here we'll details default actions taken respectively for `ENTER` key, `ESCAPE` key and `DELETE` key:

*   A shape object, temporarily held in `shape` property defined in `ShapeDrawer` class, is finalized as `ENTER` key is pressed.
*   A shape object is cancelled -- deleted from the children list of a drawing board -- as `ESCAPE` key is pressed.
*   Do nothing as `DELETE` key is pressed.

Here are methods defined to accomplish the above tasks:

Listing 6-10. Define methods to handle `ENTER`, `ESCAPE` and `DELETE` key codes:

```
 /**
   * This method is invoked from handle method of event handler of key pressed
   */
  protected void drawOnKeyPressed(KeyEvent ke) {
    KeyCode kc = ke.getCode();
    switch (kc) {
      case ENTER:
        drawOnEnterKeyPressed(); 
        break;
      case ESCAPE:
        drawOnEscapeKeyPressed();
        break;
      case DELETE:
        drawOnDeleteKeyPressed();
        break;
     }       
  }

  protected void drawOnEnterKeyPressed() {
    // Hit Enter key to finalize this shape
    // Must call drag finished method to handle unbinding
    ShapeDrawer tool = getDrawer();
    if (tool != null && tool.getShape() != null) {
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      tool.setShape(null);  // complete this shape
    }
  } 

  protected void drawOnEscapeKeyPressed() {
    // Hit Esc key to clear this shape
    if (getDrawer() != null && getDrawer().getShape() != null) {
      // Must call drag finished method to handle unbinding
      ShapeDrawer tool = getDrawer();
      Shape s = tool.getShape();
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      getChildren().remove(s);
      tool.setShape(null);  // clear this shape
    }
  }

  protected void drawOnDeleteKeyPressed() {
    if (getDrawer() != null)
      getDrawer().handleDeleteKeyPressed(this);
  }
```

From preceding listing, you see `DrawPane` handles `DELETE` key by invoking the `handleDeleteKeyPressed` method. The method is defined inside `ShapeDrawer` class like this:

```
 public void handleDeleteKeyPressed(DrawPane drawPane) {} 
```

A sophisticated drawer application may require a delete function in place while delete key is pressed, if this is the case, just override `handleDeleteKeyPressed` method when instantiate a `ShapeDrawer` class. Similarly, you can create a subclass of `DrawPane`, and override the `drawOnKeyPressed` method to carry out different actions for `ENTER` key and `ESCAPE` key to fulfill requirements of you applications.

### 6.2.5 Define Constructor with a Parameter of Type `ShapeDrawer`

Now, let's look at the constructor with a parameter of type `ShapeDrawer`:

Listing 6-11. Define the constructor with a parameter of type `ShapeDrawer`:

```
 public DrawPane(ShapeDrawer tool) {
    this();
    drawer.set(tool);
  }
```

An applicable instance of `ShapeDrawer` must be created, and passed to a constructor of `DrawPane` class, to engage on drawing tasks effectively and interactively. If the value of `drawer` property is never set, a `DrawPane` is only an ordinary `Pane`, its interactive drawing capacity is not utilized.

To learn more about creating a `DrawPane` object, read later sections in this chapter.

### 6.2.6 Complete Source Codes of `DrawPane` class

Here are complete source codes of `DrawPane` class.

Listing 6-12. Create `DrawPane` Class:

```
package drawtool;

import javafx.beans.property.BooleanProperty;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleBooleanProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.EventHandler;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.Pane;
import javafx.scene.shape.Shape;

/**
 * File Name: DrawPane.java
 * (in directory: DrawTool1.0/src/example1/drawtool/)
 * DrawPane is a subclass of Pane which does not perform automatic layout on its children.
 *
 * Define variables
 *   startX, startY, dragX, dragY are properties to hold double values:
 *
 *     startX/startY specifies coordinates of mouse pressed event.
 *
 *     dragX/dragY specifies translate distance from current dragged location to
 *     mouse pressed location. 
 *
 *   dragged is a boolean property, its value is initialized to false, 
 *   and is set to true during the first mouse dragged event occurs.
 *   It is reset to false when dragged event finished, that is, 
 *   when a sequence of mouse dragged events is ended by a mouse released event.
 *
 *   drawer, a property to hold the current drawer, a subclass of ShapeDrawer.
 *   ShapeDrawer, resides in drawtool package, is the base class for all drawers. 
 *
 * Register event handlers to handle the following events:
 *  mouse pressed, mouse dragged, mouse released, key pressed
 * these events are significant to draw shapes interactively on a drawing board.
 *
 * @author: Shufen Kuo
 */

public class DrawPane extends Pane {

  /* Declare variables */

  // mouse location when mouse pressed
  public DoubleProperty startX = new SimpleDoubleProperty();
  public DoubleProperty startY = new SimpleDoubleProperty();
  // mouse dragged distance calculated from mouse dragged location to
  // mouse pressed location
  public DoubleProperty dragX = new SimpleDoubleProperty();
  public DoubleProperty dragY = new SimpleDoubleProperty();

  public BooleanProperty dragged = new SimpleBooleanProperty();

  // Specify the current drawer of pane
  // An application may create multiple drawers and
  // switch between drawers dynamically as required
  public ObjectProperty<ShapeDrawer> drawer = new SimpleObjectProperty<>();

  // Passing drawer to constructor
  public DrawPane(ShapeDrawer tool) {
    this();
    drawer.set(tool);
  }

  public DrawPane() {
    setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMousePressed(me);
      }
    });

    setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseDragged(me);
      }
    });

    setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseReleased(me);
      }
    });

    // set focusTraversable property to true in order to handle KeyEvent, 
    // default is false.
    setFocusTraversable(true);
    setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        drawOnKeyPressed(ke);
      }
    });

  }

  /**
   * This method is invoked from handle method of event handler of mouse pressed
   *
   * Keep the coordinate of mouse pressed location in correlated properties  
   */
  protected void drawOnMousePressed(MouseEvent me) {
    setStartX(me.getX());
    setStartY(me.getY());
  }

  /**
   * This method is invoked from handle method of event handler of mouse dragged
   *
   * Keep the translate distance in dragX and dragY properties,
   * it's calculated from current mouse dragged location to mouse pressed location 
   *
   * A shape is created when the dragged action starts, 
   * invoke getDrawer().getShapeClass() methods to determine which shape to be created
   */
  protected void drawOnMouseDragged(MouseEvent me) {
    setDragX(me.getX() - getStartX());
    setDragY(me.getY() - getStartY()); 
    if (!isDragged()) {
      // Did this only once, and create the temporary shape only once
      // for each PRESSED-DRAGGED-RELEASED event cycle. 
      if (getDrawer() != null && getDrawer().getShapeClass() != null) {
        ShapeDrawer tool = getDrawer();
        Shape sketch = tool.getShape();
        if (sketch == null ||
            !tool.getShapeClass().isInstance(sketch)) {
          try {
            Shape tmpShape = tool.getShapeClass().newInstance();
            tmpShape.setFill(tool.getFillColor());
            tmpShape.setStroke(tool.getStrokeColor());
            tool.setShape(tmpShape);
            getChildren().add(tmpShape);
          } catch (InstantiationException | IllegalAccessException ex) {
          }
        }
      } 
      setDragged(true);
      // onMouseDragStarted method, defined in ShapeDrawer, is called from
      // event handler that handles MOUSE_DRAGGED type of mouse event,
      // it is called only once,
      // at the first time mouse dragged event is detected.
      if (getDrawer() != null)
        getDrawer().onMouseDragStarted(this);
    }
  }

  /**
   * This method is invoked from handle method of event handler of mouse released
   */
  protected void drawOnMouseReleased(MouseEvent me) {
    if (isDragged()) {
      setDragged(false);
      if (getDrawer() != null)
        getDrawer().onMouseDragFinished(this);
    } else {
      // This is a genuine mouse clicked
      if (getDrawer() != null)
        getDrawer().handleMouseClicked(this);
    }    
  }

  /**
   * This method is invoked from handle method of event handler of key pressed
   */
  protected void drawOnKeyPressed(KeyEvent ke) {
    KeyCode kc = ke.getCode();
    switch (kc) {
      case ENTER:
        drawOnEnterKeyPressed(); 
        break;
      case ESCAPE:
        drawOnEscapeKeyPressed();
        break;
      case DELETE:
        drawOnDeleteKeyPressed();
        break;
     }       
  }

  protected void drawOnEnterKeyPressed() {
    // Hit Enter key to finalize this shape
    // Must call drag finished method to handle unbinding
    ShapeDrawer tool = getDrawer();
    if (tool != null && tool.getShape() != null) {
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      tool.setShape(null);  // complete this shape
    }
  } 

  protected void drawOnEscapeKeyPressed() {
    // Hit Esc key to clear this shape
    if (getDrawer() != null && getDrawer().getShape() != null) {
      // Must call drag finished method to handle unbinding
      ShapeDrawer tool = getDrawer();
      Shape s = tool.getShape();
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      getChildren().remove(s);
      tool.setShape(null);  // clear this shape
    }
  }

  protected void drawOnDeleteKeyPressed() {
    if (getDrawer() != null)
      getDrawer().handleDeleteKeyPressed(this);
  }

  /* Followings are utilities to manipulate properties */

  public void setDrawer(ShapeDrawer value) {
    drawer.set(value);
  }

  public ShapeDrawer getDrawer() {
    return drawer.get();
  }

  public ObjectProperty<ShapeDrawer> drawerProperty() {
    return drawer;
  }

  public boolean isDragged() {
    return dragged.get();
  }

  public void setDragged(boolean value) {
    dragged.set(value);
  }

  public BooleanProperty draggedProperty() {
    return dragged;
  }

  public double getStartX() {
    return startX.get();
  }

  public void setStartX(double value) {
    startX.set(value);
  }

  public DoubleProperty startXProperty() {
    return startX;
  }

  public double getStartY() {
    return startY.get();
  }

  public void setStartY(double value) {
    startY.set(value);
  }

  public DoubleProperty startYProperty() {
    return startY;
  }

  public double getDragX() {
    return dragX.get();
  }

  public void setDragX(double value) {
    dragX.set(value);
  }

  public DoubleProperty dragXProperty() {
    return dragX;
  }

  public double getDragY() {
    return dragY.get();
  }

  public void setDragY(double value) {
    dragY.set(value);
  }

  public DoubleProperty dragYProperty() {
    return dragY;
  }

}
```

## 6.3 Develop Drawer Applications Using Draw Tool APIs

In this section, we'll develop several applications to interactively draw different shape objects on a drawing board. Unlike the other drawers developed previously, here we'll utilize two classes, `ShapeDrawer` and `DrawPane`, defined in `drawtool` package, to cope with tedious lower level tasks of dynamic drawings. The coding process becomes much intuitive, each drawer simply implements two abstract methods, the `onMouseDragStarted` method and the `onMouseDragFinished` method, defined within `ShapeDrawer` class.

### 6.3.1 Create `RectangleDrawer` Class as Subclass of `Application`

Here we demonstrate how to develop `RectangleDrawer` application which draws rectangle shapes on a drawing board, using APIs provided in `drawtool` package.

A rectangle shape object is created as soon as a mouse dragged event is detected. The location of a mouse pressed event prior to the detected mouse dragged event, is set as the starting point of rectangle. And as mouse dragged event continues, the ending point of rectangle is adjusted constantly to coincide with x coordinate and y coordinate of the latest mouse dragged event. This is accomplished by properties binding mechanism, refer to [Listing 6-4.](#part0012_split_001.html_new-rectangle-drawer-codes)

To create an effective instance of `DrawPane`, a direct subclass of `Pane`, we pass a `ShapeDrawer` object to the constructor of `DrawPane`. `ShapeDrawer` knows which shape to draw and how to draw it. More specifically, `shapeClass` property specifies which shape to be drawn on `DrawPane`, and the `onMouseDragStarted` method describes how to draw it. Here is a line of code to create a `DrawPane` object.

```
 DrawPane drawPane = new DrawPane(newRectangleDrawer()); 
```

We define a `newRectangleDrawer()` method which returns a `ShapeDrawer` object that draws rectangle shapes on a `DrawPane`, refer to [Listing 6-4.](#part0012_split_001.html_new-rectangle-drawer-codes), the `DrawPane` is then set in the center of a `BorderPane`, as a drawing board.

Followings are complete source codes of `RectangleDrawer` class:

Listing 6-13. Complete source codes of `RectangleDrawer` class:

```
package rectangledrawer;

import javafx.application.Application;
import javafx.beans.binding.DoubleBinding;
import javafx.scene.Scene;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.shape.Rectangle;
import javafx.stage.Stage;
import drawtool.*;

/**
 * File Name: RectangleDrawer.java
 * (in directory: DrawTool1.0/src/example1/rectangledrawer/)
 *
 * @author: Shufen Kuo
 */

public class RectangleDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(newRectangleDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("RectangleDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  ShapeDrawer newRectangleDrawer() {
    return new ShapeDrawer(Rectangle.class) {
      @Override
      public void onMouseDragStarted(final DrawPane drawPane) {

        Rectangle rect = (Rectangle)getShape();

        DoubleBinding xB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty());
          }

          @Override
          protected double computeValue() {
          return (drawPane.getDragX() < 0.0)
              ? drawPane.getStartX() + drawPane.getDragX() : drawPane.getStartX();
          }
        };

        DoubleBinding yB = new DoubleBinding() {
          {
            super.bind(drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            return (drawPane.getDragY() < 0.0)
                ? drawPane.getStartY() + drawPane.getDragY() : drawPane.getStartY();
          }
        };

        DoubleBinding wB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragX());
          }
        };

        DoubleBinding hB = new DoubleBinding() {
          {
            super.bind(drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragY());
          }
        };

        rect.xProperty().bind(xB);
        rect.yProperty().bind(yB);
        rect.widthProperty().bind(wB);
        rect.heightProperty().bind(hB);   
      }

      @Override
      public void onMouseDragFinished(final DrawPane drawPane) {
        Rectangle rect = (Rectangle)getShape();
        if (rect != null) {
          rect.xProperty().unbind();
          rect.yProperty().unbind();
          rect.widthProperty().unbind();
          rect.heightProperty().unbind();
        }
      }
    };
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 6-1. Snapshot of drawing various rectangles using `Rectangle Drawer` module.

![](images/00028.jpeg "draw_rect_icons.jpg")

Compile and run the application. Try these steps to test it:

1.  Move mouse to a location on the drawing board.
2.  Press the mouse without releasing it, drag it around the drawing board to draw a rectangle.
3.  Release the mouse when you are satisfied with the size of rectangle.
4.  Hit `Enter` key to finalize the rectangle.
5.  Repeat the above steps several times to draw rectangles in different locations with different sizes, remember hit `Enter` key after each MOUSE_RELEASED event.
6.  Repeat MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle several times, do not hit `Enter` key for each event cycle, to see what happens.
7.  Now, hit `Esc` key to cancel the last rectangle rendered on the drawing board.

Output from Compiling and Running Rectangle Drawer Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar rectangledrawer\*.java

jar cf rectangledrawer.jar rectangledrawer

java -cp drawtool.jar;rectangledrawer.jar rectangledrawer.RectangleDrawer 
```

### 6.3.2 Create `CircleDrawer` Class as Subclass of `Application`

Here we demonstrate how to develop `CircleDrawer` application which draws circle shapes on a drawing board, using APIs provided in `drawtool` package.

A circle shape object is created as soon as a mouse dragged event is detected. The location of mouse pressed event, prior to the detected mouse dragged event, is set as the center of the circle. And as mouse dragged event continues, the radius of the circle is adjusted constantly to coincide with x coordinate and y coordinate of the latest mouse dragged event. This is carried out inside the `onMouseDragStarted` method, using properties binding mechanism. As a result, you will see the radius of the circle adjusted constantly so that the latest mouse dragged location always stays in the circumference of the circle.

To finish up drawing of one circle, we need to take care of unbinding, which is done inside the `onMouseDragFinished` method, invoked from the event handler of `MOUSE_RELEASED` event which ends a sequence of mouse dragged events.

To instantiate a `ShapeDrawer` to handle drawings of circle shapes, we define a `newCircleDrawer` method as below:

Listing 6-14. Define `newCircleDrawer` method which returns an instance of `ShapeDrawer` to draw circle shapes on a drawing board:

```
 ShapeDrawer newCircleDrawer() {
    return new ShapeDrawer(Circle.class) {
      @Override
      public void onMouseDragStarted(final DrawPane drawPane) {

        Circle cs = (Circle)getShape();

        DoubleBinding rB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty(), drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            double dx = drawPane.getDragX();
            double dy = drawPane.getDragY();
            return Math.sqrt(dx*dx + dy*dy);
          }
        };
        cs.centerXProperty().bind(drawPane.startXProperty());
        cs.centerYProperty().bind(drawPane.startYProperty());
        cs.radiusProperty().bind(rB);
      }

      @Override
      public void onMouseDragFinished(final DrawPane drawPane) {
        Circle cs = (Circle)getShape();
        if (cs != null) {
          cs.centerXProperty().unbind();
          cs.centerYProperty().unbind();
          cs.radiusProperty().unbind();
        }
      }
    };
  }
```

From the preceding listing of codes, we have center point, `centerX` property and `centerY` property, of a circle shape bind to location of mouse pressed event, specified respectively in `startX` property and `startY` property, defined inside `DrawPane` class. And, we have radius of the circle bind to dragging distance calculated like this:

```
 @Override
          protected double computeValue() {
            double dx = drawPane.getDragX();
            double dy = drawPane.getDragY();
            return Math.sqrt(dx*dx + dy*dy);
          } 
```

`dragX` and `dragY` are properties defined inside `DrawPane` class, refer to [Define Properties](#part0012_split_002.html_define-properties-draw-pane).

An instance of `DrawPane` is created like this:

```
 DrawPane drawPane = new DrawPane(newCircleDrawer()); 
```

The `newCircleDrawer()` method returns a `ShapeDrawer` object, which is passed as a parameter to the constructor of `DrawPane` class. An instance of `DrawPane` is created to serve as a drawing board placed in the center of a `BorderPane`.

Followings are complete source codes of `CircleDrawer` class:

Listing 6-15. Complete source codes of `CircleDrawer` class:

```
package circledrawer;

import javafx.application.Application;
import javafx.beans.binding.DoubleBinding;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;
import javafx.scene.shape.Circle;
import drawtool.*;

/**
 * File Name: CircleDrawer.java
 * (in directory: DrawTool1.0/src/example1/circledrawer/)
 *
 * @author: Shufen Kuo
 */

public class CircleDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(newCircleDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("CircleDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  ShapeDrawer newCircleDrawer() {
    return new ShapeDrawer(Circle.class) {
      @Override
      public void onMouseDragStarted(final DrawPane drawPane) {

        Circle cs = (Circle)getShape();

        DoubleBinding rB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty(), drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            double dx = drawPane.getDragX();
            double dy = drawPane.getDragY();
            return Math.sqrt(dx*dx + dy*dy);
          }
        };
        cs.centerXProperty().bind(drawPane.startXProperty());
        cs.centerYProperty().bind(drawPane.startYProperty());
        cs.radiusProperty().bind(rB);
      }

      @Override
      public void onMouseDragFinished(final DrawPane drawPane) {
        Circle cs = (Circle)getShape();
        if (cs != null) {
          cs.centerXProperty().unbind();
          cs.centerYProperty().unbind();
          cs.radiusProperty().unbind();
        }
      }
    };
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 6-2. Snapshot of drawing various circles using `Circle Drawer` module.

![](images/00029.jpeg "draw_circle_icons")

Compile and run the application. Try these steps to test it:

1.  Move mouse to a location on the drawing board.
2.  Press the mouse without releasing it, drag it around the drawing board to draw a circle.
3.  Release the mouse when you are satisfied with the size of circle.
4.  Hit `Enter` key to finalize the circle.
5.  Repeat the above steps several times to draw circles, each with different center and radius, remember hit `Enter` after each MOUSE_RELEASED event.
6.  Repeat MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle several times, do not hit `Enter` key for each event cycle, to see what happens.
7.  Now, hit `Esc` key to cancel the last circle rendered on the drawing board.

Output from Compiling and Running Circle Drawer Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar circledrawer\*.java

jar cf circledrawer.jar circledrawer

java -cp drawtool.jar;circledrawer.jar circledrawer.CircleDrawer 
```

### 6.3.3 Create `EllipseDrawer` Class as Subclass of `Application`

Here we demonstrate how to develop `EllipseDrawer` application which draws ellipse shapes on a drawing board, using APIs provided in `drawtool` package.

Similar to all drawers described previously, an ellipse shape object is created as soon as a mouse dragged event is detected. The location of a mouse pressed event which occurred prior to the detected mouse dragged event, is set as the center point of the ellipse. `radiusX` property and `radiusY` property of the ellipse coincides with `dragX` property and `dragY` property respectively. This is carried out inside the `onMouseDragStarted` method, using properties binding mechanism. As a result, you will see radius x and radius y of the ellipse are adjusted constantly as mouse dragged event continues, and the latest mouse dragged location always stays in the circumference of the ellipse.

To finish up drawing of one ellipse, we need to take care of unbinding, which is done inside the `onMouseDragFinished` method, invoked from the event handler of `MOUSE_RELEASED` event which ends a sequence of mouse dragged events.

To instantiate a `ShapeDrawer` to handle drawings of ellipse shapes, we define `newEllipseDrawer` method as below:

Listing 6-16. Define `newEllipseDrawer` method which returns an instance of `ShapeDrawer` to draw ellipse shapes on a drawing board:

```
 ShapeDrawer newEllipseDrawer() {
    return new ShapeDrawer(Ellipse.class) {
      @Override
      public void onMouseDragStarted(final DrawPane drawPane) {

        Ellipse es = (Ellipse)getShape();

        DoubleBinding wB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragX());
          }
        };
        DoubleBinding hB = new DoubleBinding() {
          {
            super.bind(drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragY());
          }
        };    
        es.centerXProperty().bind(drawPane.startXProperty());
        es.centerYProperty().bind(drawPane.startYProperty());
        es.radiusXProperty().bind(wB);
        es.radiusYProperty().bind(hB);    
      }

      @Override
      public void onMouseDragFinished(final DrawPane drawPane) {
        Ellipse es = (Ellipse)getShape();
        if (es != null) {
          es.centerXProperty().unbind();
          es.centerYProperty().unbind();
          es.radiusXProperty().unbind();
          es.radiusYProperty().unbind();
        }
      }
    };
  }
```

From the preceding listing of codes, we have the center point, `centerX` property and `centerY` property, of an ellipse shape bind to location of mouse pressed event, specified respectively in `startX` property and `startY` property, defined inside `DrawPane` class. And, we have radius X bind to dragging X distance calculated like this:

```
 @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragX());
          } 
```

And, have radius Y bind to dragging Y distance calculated like this:

```
 @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragY());
          } 
```

`dragX` and `dragY` are properties defined inside `DrawPane` class, refer to [Define Properties](#part0012_split_002.html_define-properties-draw-pane).

An instance of `DrawPane` is created like this:

```
 DrawPane drawPane = new DrawPane(newEllipseDrawer()); 
```

The `newEllipseDrawer()` method returns a `ShapeDrawer` object, which is passed as a parameter to the constructor of `DrawPane`. An instance of `DrawPane` is created to serve as a drawing board placed in the center of a `BorderPane`.

Followings are complete source codes of `EllipseDrawer` class:

Listing 6-17. Complete source codes of `EllipseDrawer` class:

```
package ellipsedrawer;

import javafx.application.Application;
import javafx.beans.binding.DoubleBinding;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.Pane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;
import javafx.scene.shape.Ellipse;
import drawtool.*;

/**
 * File Name: EllipseDrawer.java
 * (in directory: DrawTool1.0/src/example1/ellipsedrawer/)
 *
 * @author: Shufen Kuo
 */
public class EllipseDrawer extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(newEllipseDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("EllipseDrawer V1.0 Shufen Source Code");
    stage.show();
  }

  ShapeDrawer newEllipseDrawer() {
    return new ShapeDrawer(Ellipse.class) {
      @Override
      public void onMouseDragStarted(final DrawPane drawPane) {

        Ellipse es = (Ellipse)getShape();

        DoubleBinding wB = new DoubleBinding() {
          {
            super.bind(drawPane.dragXProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragX());
          }
        };
        DoubleBinding hB = new DoubleBinding() {
          {
            super.bind(drawPane.dragYProperty());
          }

          @Override
          protected double computeValue() {
            return Math.abs(drawPane.getDragY());
          }
        };    
        es.centerXProperty().bind(drawPane.startXProperty());
        es.centerYProperty().bind(drawPane.startYProperty());
        es.radiusXProperty().bind(wB);
        es.radiusYProperty().bind(hB);    
      }

      @Override
      public void onMouseDragFinished(final DrawPane drawPane) {
        Ellipse es = (Ellipse)getShape();
        if (es != null) {
          es.centerXProperty().unbind();
          es.centerYProperty().unbind();
          es.radiusXProperty().unbind();
          es.radiusYProperty().unbind();
        }
      }
    };
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 6-3. Snapshot of drawing various ellipses using `Ellipse Drawer` module.

![](images/00030.jpeg "draw_ellipse_icons")

Compile and run the application. Try these steps to test it:

1.  Move mouse to a location on the drawing board.
2.  Press the mouse without releasing it, drag it around the drawing board to draw an ellipse.
3.  Release the mouse when you are satisfied with the size of ellipse.
4.  Hit `Enter` key to finalize the ellipse.
5.  Repeat the above steps several times to draw ellipses, each with different center and radius, remember hit `Enter` after each MOUSE_RELEASED event.
6.  Repeat MOUSE_PRESSED—MOUSE_DRAGGED—MOUSE_RELEASED event cycle several times, do not hit `Enter` key for each event cycle, to see what happens.
7.  Now, hit `Esc` key to cancel the last ellipse rendered on the drawing board.

Output from Compiling and Running Ellipse Drawer Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.0\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar ellipsedrawer\*.java

jar cf ellipsedrawer.jar ellipsedrawer

java -cp drawtool.jar;ellipsedrawer.jar ellipsedrawer.EllipseDrawer 
```

## 6.4 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   Some of classes from `javafx.beans.property` package:

    `ObjectProperty<T>`

    Is an abstract class, derived from `javafx.beans.binding.ObjectExpression<T>` class, implements `Property<T>` and `WritableObjectValue<T>`.

    `SimpleObjectProperty<T>`

    Derived from `ObjectProperty<T>` class.

    `DoubleProperty`

    Is an abstract class, derived from `javafx.beans.binding.DoubleExpression` class, implements `Property<Number>` and `WritableDoubleValue`.
    `WritableDoubleValue` extends `WritableNumberValue`.

    `SimpleDoubleProperty`

    Derived from `DoubleProperty` class.

    `BooleanProperty`

    Is an abstract class, derived from `javafx.beans.binding.BooleanExpression` class, implements `Property<java.lang.Boolean>` and `WritableBooleanValue`.
    `WritableBooleanValue` extends `WritableValue<java.lang.Boolean>`.

    `SimpleBooleanProperty`

    Derived from `BooleanProperty` class.

    (See sections: [Define Properties](#part0012_split_001.html_define-properties-shape-drawer), [Define Properties](#part0012_split_002.html_define-properties-draw-pane))
*   `WritableObjectValue<T>` interface, resides in `javafx.beans.value` package and extends `WritableValue<T>`, defines the following methods:

    `T get()`

    Get the wrapped value.

    `void set(T value)`

    Set the wrapped value.

    (See [here](#part0012_split_001.html_utils-shape-drawer-properties-codes), and [here](#part0012_split_002.html_utils-draw-pane-properties-codes))
*   `DoubleBinding`, an abstract class resides in `javafx.beans.binding` package, extends `DoubleExpression` and implements `NumberBinding`. The `computeValue()` method need to be implemented in order to instantiate a `DoubleBinding` object. Usually call `bind(Observable... dependencies)` method to observe the value changes of dependencies for this `DoubleBinding`.
    (See [here](#part0012_split_001.html_new-rectangle-drawer-codes), [here](#part0012_split_003.html_new-circle-drawer-codes), [here](#part0012_split_003.html_new-ellipse-drawer-codes))
*   `Property<T>` interface, resides in `javafx.beans.property` package, defines methods common to all properties such as:

    `void bind(ObservableValue<? extends T> observable)`

    Bind this property unidirectionally to the given `ObservableValue`.

    `void unbind()`

    Unbind for this property.

    (See [here](#part0012_split_001.html_new-rectangle-drawer-codes), [here](#part0012_split_003.html_new-circle-drawer-codes), [here](#part0012_split_003.html_new-ellipse-drawer-codes))
*   `Pane` class, extends `javafx.scene.layout.Region` and resides in `javafx.scene.layout` package, is the base class of JavaFX build-in layout panes.
    (See section [Create `DrawPane` Class](#part0012_split_002.html_create-draw-pane))
*   `WritableBooleanValue` interface, resides in `javafx.beans.value` package and extends `WritableValue<Boolean>`, defines the following methods:

    `boolean get()`

    Get the wrapped value. It returns primitive boolean.

    `void set(boolean` value`)`

    Set the wrapped value. It accepts primitive boolean.

    (See [here](#part0012_split_002.html_utils-draw-pane-properties-codes))
*   `WritableDoubleValue` interface, resides in `javafx.beans.value` package and extends `WritableNumberValue`, defines the following methods:

    `double get()`

    Get the wrapped value. It returns primitive double.

    `void set(double` value`)`

    Set the wrapped value. It accepts primitive double.

    (See [here](#part0012_split_002.html_utils-draw-pane-properties-codes))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See section [Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers))
*   `MouseEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `MOUSE_CLICKED`, `MOUSE_DRAGGED`, `MOUSE_ENTERED`, `MOUSE_EXITED`, `MOUSE_MOVED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, etc., and provides methods such as `getX()`, `getY()`, etc., to get position of mouse cursor while event occurs.
    (See section [Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers))
*   Some of convenience methods provided in `Node` class to register `EventHandler`s to handle mouse events.

    `public final void setOnMousePressed(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_PRESSED` event type of `MouseEvent`.

    `public final void setOnMouseDragged(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_DRAGGED` event type of `MouseEvent`.

    `public final void setOnMouseReleased(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_RELEASED` event type of `MouseEvent`.

    (See section [Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers))
*   `KeyEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `KEY_PRESSED`, `KEY_RELEASED`, `KEY_TYPED`, etc., and provides methods such as `getCode()`, `getCharacter()`, `getText()`, etc., to get information about keys in type of either `KeyCode`, or `String`. It also provides boolean methods such as `isControlDown()`, `isShiftDown()`, `isAltDown()`, etc., to verify whether some of modifier keys are pressed at the same time.
    (See sections: [Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers), [Take Default Actions for `ENTER` key, `ESCAPE` key and `DELETE` key](#part0012_split_002.html_handle-key-codes))
*   `public final void setOnKeyPressed(EventHandler<? super KeyEvent>` value`)`, a convenience method provided in `Node` class, registers an `EventHandler` to handle `KEY_PRESSED` event type of `KeyEvent`.
    (See sections: [Register Event Handlers inside the Default Constructor](#part0012_split_002.html_register-event-handlers), [Take Default Actions for `ENTER` key, `ESCAPE` key and `DELETE` key](#part0012_split_002.html_handle-key-codes))
*   `focusTraversable` is a property defined in `Node` class for specifying whether this node is traversable and eligible to receive focus.
    (See [here](#part0012_split_002.html_focus-traversable))
*   `KeyCode` class, resides in `javafx.scene.input` package, is an enumerated type defines constants for keys of keyboard; it covers letter keys (`A` to `Z`), digits keys(`DIGIT0` to `DIGIT9`), modifier keys(such as `CONTROL`, `SHIFT`, etc.), function keys, etc.
    (See section [Take Default Actions for `ENTER` key, `ESCAPE` key and `DELETE` key](#part0012_split_002.html_handle-key-codes))
*   `Shape` class, resides in `javafx.scene.shape` package, provides functionality for rendering 2D geometric primitives such as rectangle, circle, ellipse, etc.
    (See section [Develop Drawer Applications Using Draw Tool APIs](#part0012_split_003.html_develop-drawers))
*   `Rectangle` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw rectangle shapes with specified properties, such as `x`, `y`, `width`, `height`, etc. (See section [Create `RectangleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-rectangle-drawer-class) )
*   `Circle` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw circle shapes with specified properties, such as `centerX`, `centerY`, and `radius`. (See section [Create `CircleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-circle-drawer-class) )
*   `Ellipse` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw ellipse shapes with specified properties, such as `centerX`, `centerY`, `radiusX`, and `radiusY`. (See section [Create `EllipseDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-ellipse-drawer-class) )

# Chapter 7
Enhanced Draw Tool with Predefined Drawers
--Developing Shape Drawing Tools V1.1

## Preface

In this chapter, we will enhance shape drawing APIs provided in `drawtool` package, and create `drawtool.drawer` package containing these predefined shape drawers -- `LineDrawer`, `PolylineDrawer`, `PolygonDrawer`, `PathDrawer`, `BezierCurveDrawer`, `RectangleDrawer`, `CircleDrawer`, `EllipseDrawer`, and `ShapeMover` -- which are direct subclasses of `ShapeDrawer`.

From detailed descriptions and well-documented example codes excerpted from developments of `Shape Drawing Tools V1.1`, you will become familiar with fundamental capabilities of JavaFX library recounted in the [Summary](#part0013_split_004.html_summary) section.

The complete development process of `Shape Drawing Tools V1.1` is characterized by the following steps:

*   [7.1 Enhance `ShapeDrawer` Class](#part0013_split_001.html_enhance-shape-drawer)
    *   [7.1.1 Define Shape Rendering Properties](#part0013_split_001.html_define-shape-properties)
    *   [7.1.2 Define a Boolean Property `polySegment`](#part0013_split_001.html_define-poly-segment)
    *   [7.1.3 Complete Source Codes of Enhanced `ShapeDrawer` class](#part0013_split_001.html_complete-source-codes-shape-drawer)
*   [7.2 Create Subclasses of `ShapeDrawer`](#part0013_split_002.html_create-subclasses-shape-drawer)
    *   [7.2.1 Implement `LineDrawer` Class](#part0013_split_002.html_implement-line-drawer)
        *   [7.2.1.1 Create Line Drawer App](#part0013_split_002.html_create-line-drawer-app)
    *   [7.2.2 Implement `PolylineDrawer` Class](#part0013_split_002.html_implement-polyline-drawer)
        *   [7.2.2.1 Create Polyline Drawer App](#part0013_split_002.html_create-polyline-drawer-app)
    *   [7.2.3 Implement `PolygonDrawer` Class](#part0013_split_002.html_implement-polygon-drawer)
        *   [7.2.3.1 Create Polygon Drawer App](#part0013_split_002.html_create-polygon-drawer-app)
    *   [7.2.4 Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer)
        *   [7.2.4.1 Create Path Drawer App](#part0013_split_002.html_create-path-drawer-app)
    *   [7.2.5 Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer)
        *   [7.2.5.1 Create Bezier Curve Drawer App](#part0013_split_002.html_create-bezier-curve-drawer-app)
    *   [7.2.6 Implement `RectangleDrawer` Class](#part0013_split_002.html_implement-rectangle-drawer)
        *   [7.2.6.1 Create Rectangle Drawer App](#part0013_split_002.html_create-rectangle-drawer-app)
    *   [7.2.7 Implement `CircleDrawer` Class](#part0013_split_002.html_implement-circle-drawer)
        *   [7.2.7.1 Create Circle Drawer App](#part0013_split_002.html_create-circle-drawer-app)
    *   [7.2.8 Implement `EllipseDrawer` Class](#part0013_split_002.html_implement-ellipse-drawer)
        *   [7.2.8.1 Create Ellipse Drawer App](#part0013_split_002.html_create-ellipse-drawer-app)
    *   [7.2.9 Implement `ShapeMover` Class](#part0013_split_002.html_implement-shape-mover)
*   [7.3 Enhance `DrawPane` Class](#part0013_split_003.html_enhance-draw-pane)
*   [7.4 Summary](#part0013_split_004.html_summary)

## 7.1 Enhance `ShapeDrawer` Class

`ShapeDrawer`, an abstract class, is the base class for all drawers that draw shapes by dragging mouse around a drawing board. It provides basic methods to facilitate developments of shape drawing applications. In this section, we'll define additional properties.

### 7.1.1 Define Shape Rendering Properties

More properties for rendering shapes are required in `ShapeDrawer` Class:

Import Statements:

```
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.scene.paint.Color;
import javafx.scene.shape.StrokeType;
```

Listing 7-1. Define shape rendering properties in `ShapeDrawer` Class:

```
 public ObjectProperty<Color> fillColor = 
    new SimpleObjectProperty<>(Color.WHITE); 
  public ObjectProperty<Color> strokeColor = 
    new SimpleObjectProperty<>(Color.GREY); 

  // more properties for rendering shape
  public DoubleProperty strokeWidth = new SimpleDoubleProperty(1);  
  public ObjectProperty<StrokeType> strokeType = 
      new SimpleObjectProperty<>(StrokeType.CENTERED); // default
```

You will see effective usage in later sections where we assign different fill color and stroke color for each subclass of `ShapeDrawer`.

### 7.1.2 Define a Boolean Property `polySegment`

For drawers like `Polyline Drawer`, `Polygon Drawer`, `Path Drawer` and `Bezier Curve Drawer`, we need a boolean property to distinguish them from other drawers like `Line Drawer`, `Rectangle Drawer`, `Circle Drawer`, and `Ellipse Drawer`. In our initial approach, it requires a user press `Enter` key to finalize a shape. To simplify user interfaces, the enhanced approach ignores `Enter` key for finishing a shape like rectangle, circle or ellipse, that is, the shape will stay on a drawing board after a `MOUSE_PRESSED-MOUSE_DRAGGED-MOUSE_RELEASED` event cycle, unless `Esc` key is pressed. And, for a shape like polyline, polygon, or path, which consists of multiple segments, pressing `Enter` is required to finalize it.

Import Statements:

```
import javafx.beans.property.BooleanProperty;
import javafx.beans.property.SimpleBooleanProperty;
```

Listing 7-2. Define `polySegment` property in `ShapeDrawer` Class:

```
 // this property is added for drawing poly segments like polyline, polygon, path
  public BooleanProperty polySegment = new SimpleBooleanProperty();
```

The `polySegment`, type of `BooleanProperty`, specifies whether a shape to be drawn consisting multiple segments; default value is `false`. Its value is checked inside the `handle` method of `MouseDragged` event registered within the default constructor of `DrawPane` class.

### 7.1.3 Complete Source Codes of Enhanced `ShapeDrawer` class

Complete source codes of enhanced `ShapeDrawer` becomes like these:

Listing 7-3. Enhanced `ShapeDrawer` Class:

```
package drawtool;

import javafx.beans.property.BooleanProperty;
import javafx.beans.property.SimpleBooleanProperty;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.scene.paint.Color;
import javafx.scene.shape.Shape;
import javafx.scene.shape.StrokeType;

/**
 * File Name: ShapeDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/)
 * ShapeDrawer is the base class for all drawers which draw shapes on a drawing board.
 * It provides basic methods to facilitate the development of shape drawing applications.
 * A shape is drawn on a drawing board by mouse dragged events. 
 *
 * shapeClass is a property which specifies the shape to be drawn on a drawing board.
 * If the value is not set, no shape will be drawn when mouse dragged events occur
 * on the drawing board. 
 * See the following two examples:
 *   The LineDrawer is a subclass of ShapeDrawer, the value of shapeClass is set
 *   to Line.class in the constructor of LineDrawer.
 *   The ShapeMover is a subclass of ShapeDrawer, the value of shapeClass is set to null,
 *   therefore, no shape will be drawn when mouse is dragged.
 *   The ShapeMover is to move the existing shapes when mouse is dragged on it.
 *
 * shape is a property to temporarily hold the shape drawn on a drawing board.
 *
 * strokeColor/fillColor are properties to hold value of stroke/fill properties of
 *   a shape to be drawn on a drawing board. 
 * 
 * The following abstract methods must be implemented by a subclass of ShapeDrawer:
 *   public abstract void onMouseDragStarted(DrawPane drawPane)
 *   public abstract void onMouseDragFinished(DrawPane drawPane)
 *
 * Followings are methods that do nothing, they can be overridden by a subclass of ShapeDrawer:
 *   public void handleMouseClicked(DrawPane drawPane) {}
 *   public void handleDeleteKeyPressed(DrawPane drawPane) {}
 *   public void clean(DrawPane drawPane) {}
 *
 * @author: Shufen Kuo
 */

public abstract class ShapeDrawer {

  /* Declare variables */

  public ObjectProperty<Class<? extends Shape>> shapeClass =
    new SimpleObjectProperty<>();
  public ObjectProperty<Shape> shape = new SimpleObjectProperty<>();

  // basic properties for rendering shape
  public ObjectProperty<Color> fillColor = 
    new SimpleObjectProperty<>(Color.WHITE); 
  public ObjectProperty<Color> strokeColor = 
    new SimpleObjectProperty<>(Color.GREY); 

  // more properties for rendering shape
  public DoubleProperty strokeWidth = new SimpleDoubleProperty(1);  
  public ObjectProperty<StrokeType> strokeType = 
      new SimpleObjectProperty<>(StrokeType.CENTERED); // default

  // this property is added for drawing poly segments like polyline, polygon, path
  public BooleanProperty polySegment = new SimpleBooleanProperty();

  /* Define abstract methods */

  public abstract void onMouseDragStarted(DrawPane drawPane);
  public abstract void onMouseDragFinished(DrawPane drawPane);

  public ShapeDrawer(Class<? extends Shape> sc) {
    shapeClass.set(sc);
  }

  /* Define methods that do nothing */

  public void handleMouseClicked(DrawPane drawPane) {}
  public void handleDeleteKeyPressed(DrawPane drawPane) {}
  public void clean(DrawPane drawPane) {}

  /* Utilities to access properties */

  public Class<? extends Shape> getShapeClass() {
    return shapeClass.get();
  }

  public void setShapeClass(Class<? extends Shape> value) {
    shapeClass.set(value);
  }

  public ObjectProperty<Class<? extends Shape>> shapeClassProperty() {
    return shapeClass;
  }

  public Shape getShape() {
    return shape.get();
  }

  public void setShape(Shape value) {
    shape.set(value);
  }

  public ObjectProperty<Shape> shapeProperty() {
    return shape;
  }

  public boolean isPolySegment() {
    return polySegment.get();
  }

  public void setPolySegment(boolean value) {
    polySegment.set(value);
  }

  public BooleanProperty polySegmentProperty() {
    return polySegment;
  }
  public Color getStrokeColor() {
    return strokeColor.get();
  }

  public void setStrokeColor(Color value) {
    strokeColor.set(value);
  }

  public ObjectProperty<Color> strokeColorProperty() {
    return strokeColor;
  }

  public Color getFillColor() {
    return fillColor.get();
  }

  public void setFillColor(Color value) {
    fillColor.set(value);
  }

  public ObjectProperty<Color> fillColorProperty() {
    return fillColor;
  }

  public void setStrokeType(StrokeType value) {
    strokeType.set(value);
  }

  public StrokeType getStrokeType() {
    return strokeType.get();
  }

  public ObjectProperty<StrokeType> strokeTypeProperty() {
    return strokeType;
  }

  public void setStrokeWidth(double value) {
    strokeWidth.set(value);
  }

  public double getStrokeWidth() {
    return strokeWidth.get();
  }

  public DoubleProperty strokeWidthProperty() {
    return strokeWidth;
  }

}
```

## 7.2 Create Subclasses of `ShapeDrawer`

In this section, we'll implement classes -- `LineDrawer`, `PolylineDrawer`, `PolygonDrawer`, `PathDrawer`, `BezierCurveDrawer`, `RectangleDrawer`, `CircleDrawer`, `EllipseDrawer`, and `ShapeMover` -- which extend `ShapeDrawer` and reside in `drawtool.drawer` package.

In later chapter of this book, we'll utilize them to build our `JFXDrawTools` application, a comprehensive sketch drawing tool for dynamically drawing a variety of shapes on a drawing board.

### 7.2.1 Implement `LineDrawer` Class

`LineDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

For detailed descriptions of drawing `Line` objects, refer to [Chapter 1 Line Drawer--Developing Line Drawer V1.0](#part0007_split_000.html_6LJU0-4cbb8f9352704a549e363e38a5243855).

Here are complete source codes of `LineDrawer` class.

Listing 7-4. Implement `LineDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.scene.paint.Color;
import javafx.scene.shape.Line;

import drawtool.*;

/**
 * File Name: LineDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class LineDrawer extends ShapeDrawer {

  public LineDrawer() {
    super(Line.class);
    setFillColor(null);
    setStrokeColor(Color.ORANGERED);
  }

  @Override
  public void onMouseDragStarted(DrawPane drawPane) {
    Line line = (Line)getShape();
    // Set value of properties startX, startY
    line.setStartX(drawPane.getStartX());
    line.setStartY(drawPane.getStartY());
    // bind for properties endX, endY
    line.endXProperty().bind(
      drawPane.startXProperty().add(drawPane.dragXProperty()));
    line.endYProperty().bind(
      drawPane.startYProperty().add(drawPane.dragYProperty()));
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Line line = (Line)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (line != null) {
      // unbind for properties endX, endY
      line.endXProperty().unbind();
      line.endYProperty().unbind();
    }
  }

}
```

#### 7.2.1.1 Create Line Drawer App

To test `LineDrawer` class, we create a primitive drawing application that simply draws lines on a drawing board dynamically. Followings are complete source codes.

Listing 7-5. Source codes of a line drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: LineDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws lines dynamically on a drawing board.
 * A simple application that tests LineDrawer class.
 *
 * @author: Shufen Kuo
 */

public class LineDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new LineDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("LineDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 7-1. Snapshot of drawing lines using `Line Drawer App` module.

![](images/00031.jpeg "draw_line_icons.jpg")

Output from Compiling and Running Line Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac  -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.LineDrawerApp
```

### 7.2.2 Implement `PolylineDrawer` Class

`PolylineDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

`polySegment` property, defined in super class `ShapeDrawer`, need be set to `true` inside the constructor. To finish drawing of one polyline object, `Enter` key must be pressed.

For detailed descriptions of drawing `Polyline` objects, refer to [Chapter 2 Polyline Drawer--Developing Polyline Drawer V1.0](#part0008_split_000.html_7K4G0-4cbb8f9352704a549e363e38a5243855).

Here are complete source codes of `PolylineDrawer` class.

Listing 7-6. Implement `PolylineDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.collections.ObservableList;
import javafx.scene.paint.Color;
import javafx.scene.shape.Line;
import javafx.scene.shape.Polyline;

import drawtool.*;

/**
 * File Name: PolylineDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class PolylineDrawer extends ShapeDrawer {
  // This is to hold a temporary line which stands for one segment of a polyline
  ObjectProperty<Line> line = new SimpleObjectProperty<>();

  public PolylineDrawer() {
    super(Polyline.class);
    setPolySegment(true); // default is false
    setFillColor(null);
    setStrokeColor(Color.BLUEVIOLET);
  }

  @Override
  public void onMouseDragStarted(DrawPane drawPane) {
    Line tmpLine = new Line();
    drawPane.getChildren().add(tmpLine);
    // Set this tmpLine as value of line property,
    // as a result, it will be added to drawing board's children list
    // inside the line property's listener.
    line.set(tmpLine);
    tmpLine.setStroke(getStrokeColor());
    tmpLine.setStartX(drawPane.getStartX());
    tmpLine.setStartY(drawPane.getStartY());
    tmpLine.endXProperty().bind(
      drawPane.startXProperty().add(drawPane.dragXProperty()));
    tmpLine.endYProperty().bind(
      drawPane.startYProperty().add(drawPane.dragYProperty()));

    Polyline polyline = (Polyline)getShape();
    // Verify whether the start point of this line is
    // same as the end point of the last line
    // If they are not the same means this segment is
    // not connected to last segment,
    // we'll add the start point of this segment to polyline's points list.
    ObservableList<Double> list = polyline.getPoints();
    if (list.size() > 1) {
      // check if the last point is same as the start point of this line
      double lastX = list.get(list.size()-2);
      double lastY = list.get(list.size()-1);
      // if start point of this segment coincide with the last point
      // in the points list of polyline,
      // no need to add start point to the polyline
      if (lastX != drawPane.getStartX() && lastY != drawPane.getStartY()) {
        // add the start point to polyline
        polyline.getPoints().addAll(drawPane.getStartX(), drawPane.getStartY());
      }        
    } else {
      // There's no points in the points list yet,
      // add the start point to the points list,
      // this is the beginning point of the polyline.
      polyline.getPoints().addAll(drawPane.getStartX(), drawPane.getStartY());
    }
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Line tmpLine = line.get();
    if (tmpLine != null) {
      tmpLine.endXProperty().unbind();
      tmpLine.endYProperty().unbind();
      line.set(null); // clear this temp line
      drawPane.getChildren().remove(tmpLine);
    }

    Polyline polyline = (Polyline)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (polyline != null) {
      // Add the end point of the current line to the polyline
      polyline.getPoints().addAll(drawPane.getStartX() + drawPane.getDragX(),
        drawPane.getStartY() + drawPane.getDragY());
    }
  }

}
```

#### 7.2.2.1 Create Polyline Drawer App

To test `PolylineDrawer` class, we create a primitive drawing application that simply draws polylines on a drawing board dynamically. Followings are complete source codes.

Listing 7-7. Source codes of a polyline drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: PolylineDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws polylines dynamically on a drawing board.
 * A simple application that tests PolylineDrawer class.
 *
 * @author: Shufen Kuo
 */

public class PolylineDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new PolylineDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("PolylineDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 7-2. Snapshot of drawing polylines using `Polyline Drawer App` module.

![](images/00032.jpeg "draw_polyline_icons.jpg")

Output from Compiling and Running Polyline Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.PolylineDrawerApp
```

### 7.2.3 Implement `PolygonDrawer` Class

`PolygonDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

`polySegment` property, defined in super class `ShapeDrawer`, need be set to `true` inside the constructor. To finish drawing of one polygon object, `Enter` key must be pressed.

Here are complete source codes of `PolygonDrawer` class, they are almost identical to that of `PolylineDrawer`, and differences are shown in bold face.

Listing 7-8. Implement `PolygonDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.collections.ObservableList;
import javafx.scene.paint.Color;
import javafx.scene.shape.Line;
import javafx.scene.shape.Polygon; 

import drawtool.*;

/**
 * File Name: PolygonDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class PolygonDrawer extends ShapeDrawer {
  // This is to hold a temporary line which stands for one segment of a polygon
  ObjectProperty<Line> line = new SimpleObjectProperty<>();

  public PolygonDrawer() {
    super(Polygon.class);
    setPolySegment(true); // default is false
    setStrokeColor(Color.MEDIUMBLUE);
    setFillColor(Color.AQUA);
  }

  @Override
  public void onMouseDragStarted(DrawPane drawPane) {
    Line tmpLine = new Line();
    drawPane.getChildren().add(tmpLine);
    // Set this tmpLine as value of line property,
    // as a result, it will be added to drawing board's children list
    // inside the line property's listener.
    line.set(tmpLine);
    tmpLine.setStroke(getStrokeColor());
    tmpLine.setStartX(drawPane.getStartX());
    tmpLine.setStartY(drawPane.getStartY());
    tmpLine.endXProperty().bind(
      drawPane.startXProperty().add(drawPane.dragXProperty()));
    tmpLine.endYProperty().bind(
      drawPane.startYProperty().add(drawPane.dragYProperty()));

    Polygon polygon = (Polygon)getShape();
    // Verify whether the start point of this line is
    // same as the end point of the last line
    // If they are not the same means this segment is
    // not connected to last segment,
    // we'll add the start point of this segment to polygon's points list.
    ObservableList<Double> list = polygon.getPoints();
    if (list.size() > 1) {
      // check if the last point is same as the start point of this line
      double lastX = list.get(list.size()-2);
      double lastY = list.get(list.size()-1);
      // if start point of this segment coincide with the last point
      // in the points list of polygon,
      // no need to add start point to the polygon
      if (lastX != drawPane.getStartX() && lastY != drawPane.getStartY()) {
        // add the start point to polygon
        polygon.getPoints().addAll(drawPane.getStartX(), drawPane.getStartY());
      }        
    } else {
      // There's no points in the points list yet,
      // add the start point to the points list,
      // this is the beginning point of the polygon.
      polygon.getPoints().addAll(drawPane.getStartX(), drawPane.getStartY());
    }
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Line tmpLine = line.get();
    if (tmpLine != null) {
      tmpLine.endXProperty().unbind();
      tmpLine.endYProperty().unbind();
      line.set(null); // clear this temp line
      drawPane.getChildren().remove(tmpLine);
    }

    Polygon polygon = (Polygon)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (polygon != null) {
      // Add the end point of the current line to the polygon
      polygon.getPoints().addAll(drawPane.getStartX() + drawPane.getDragX(),
        drawPane.getStartY() + drawPane.getDragY());
    }
  }

}
```

#### 7.2.3.1 Create Polygon Drawer App

To test `PolygonDrawer` class, we create a primitive drawing application that simply draws polygons on a drawing board dynamically. Followings are complete source codes.

Listing 7-9. Source codes of a polygon drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: PolygonDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws polygons dynamically on a drawing board.
 * A simple application that tests PolygonDrawer class.
 *
 * @author: Shufen Kuo
 */

public class PolygonDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new PolygonDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("PolygonDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 7-3. Snapshot of drawing polygons using `Polygon Drawer App` module.

![](images/00033.jpeg "draw_polygon_icons.jpg")

Output from Compiling and Running Polygon Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.PolygonDrawerApp
```

### 7.2.4 Implement `PathDrawer` Class

`PathDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

`polySegment` property, defined in super class `ShapeDrawer`, need be set to `true` inside the constructor. To finish drawing of one path object, `Enter` key must be pressed.

For detailed descriptions of drawing `Path` objects, refer to [Chapter 4 Path Drawer--Developing Path Drawer V1.0](#part0010_split_000.html_9H5K0-4cbb8f9352704a549e363e38a5243855).

Here are complete source codes of `PathDrawer` class.

Listing 7-10. Implement `PathDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.collections.ObservableList;
import javafx.scene.shape.LineTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.PathElement;
import javafx.scene.paint.Color;
import javafx.scene.shape.Path;

import drawtool.*;

/**
 * File Name: PathDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class PathDrawer extends ShapeDrawer {

  public PathDrawer() {
    super(Path.class);
    setPolySegment(true); // default is false
    setStrokeColor(Color.DODGERBLUE);
    setFillColor(null);
  }

  @Override
  public void onMouseDragStarted(DrawPane drawPane) {
    Path path = (Path)getShape();
    ObservableList<PathElement> list = path.getElements();
    // Check if this is the beginning of a new path
    if (list.size() > 1) {
      // This is not the beginning of a new path.
      // Check if a MoveTo is necessary.
      // Get the last LineTo and verify its x,y cooradinates.
      LineTo lineTo = (LineTo) list.get(list.size() - 1);
      if (lineTo.getX() != drawPane.getStartX() ||
          lineTo.getY() != drawPane.getStartY()) {
        // Need a MoveTo element
        MoveTo moveTo = new MoveTo();
        moveTo.setX(drawPane.getStartX());
        moveTo.setY(drawPane.getStartY());
        path.getElements().add(moveTo);
      }      
    } else {
      // This is a new path, must create a MoveTo
      MoveTo moveTo = new MoveTo();
      moveTo.setX(drawPane.getStartX());
      moveTo.setY(drawPane.getStartY());
      path.getElements().add(moveTo);
    }

    // Create a LineTo and add to list
    LineTo lineTo = new LineTo();
    lineTo.xProperty().bind(
      drawPane.startXProperty().add(drawPane.dragXProperty()));
    lineTo.yProperty().bind(
      drawPane.startYProperty().add(drawPane.dragYProperty()));

    path.getElements().add(lineTo);
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Path path = (Path)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (path != null) {    
      ObservableList<PathElement> list = path.getElements();
      // unbind the x, y location of the last lineTo element of the list
      if (list.size() > 1) {
         LineTo lineTo = (LineTo) list.get(list.size() - 1);
         lineTo.xProperty().unbind();
         lineTo.yProperty().unbind();
      }
    }
  }

}
```

#### 7.2.4.1 Create Path Drawer App

To test `PathDrawer` class, we create a primitive drawing application that simply draws paths of straight lines on a drawing board dynamically. Followings are complete source codes.

Listing 7-11. Source codes of a path drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: PathDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws paths of straight lines
 * dynamically on a drawing board.
 * A simple application that tests PathDrawer class.
 *
 * @author: Shufen Kuo
 */
public class PathDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new PathDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("PathDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Please note that, Figure 7-4 shows a single `Path` object that consists of multiple elements. The path is rendered into multiple straight lines.

Figure 7-4. Snapshot of drawing one path using `Path Drawer App` module.

![](images/00034.jpeg "draw_path_icons.jpg")

Output from Compiling and Running Path Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.PathDrawerApp
```

### 7.2.5 Implement `BezierCurveDrawer` Class

`BezierCurveDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

`polySegment` property, defined in super class `ShapeDrawer`, need be set to `true` inside the constructor. To finish drawing of one path object, `Enter` key must be pressed.

`BezierCurveDrawer` draws `Path` objects, just like `PathDrawer` does; however, instead of rendering a path into straight lines as `PathDrawer` does, `BezierCurveDrawer` renders a path into multiple quadratic Bézier curves. For detailed descriptions of drawing `Path` objects that consist of quadratic Bézier Curves, refer to [Chapter 5 Quadratic Bézier Curve Drawer--Developing Quadratic Bézier Curve Drawer V1.0](#part0011_split_000.html_AFM60-4cbb8f9352704a549e363e38a5243855).

Here are complete source codes of `BezierCurveDrawer` class.

Listing 7-12. Implement `BezierCurveDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.binding.DoubleBinding;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.collections.ObservableList;
import javafx.scene.Cursor;
import javafx.scene.shape.Circle;
import javafx.scene.shape.LineTo;
import javafx.scene.shape.MoveTo;
import javafx.scene.shape.PathElement;
import javafx.scene.shape.QuadCurveTo;
import javafx.scene.shape.Shape;
import javafx.scene.paint.Color;
import javafx.scene.shape.Path;

import drawtool.*;

/**
 * File Name: BezierCurveDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class BezierCurveDrawer extends ShapeDrawer {
  // For displaying locations of 3 points required
  // to draw a quadratic Bezier curve
  Circle startPoint = new Circle(2.5f, Color.TRANSPARENT);
  Circle endPoint = new Circle(2.5f, Color.TRANSPARENT);
  Circle controlPoint = new Circle(3.5f, Color.TRANSPARENT);
  {
    startPoint.setStroke(Color.RED);
    endPoint.setStroke(Color.GREEN);
    controlPoint.setStroke(Color.BLUE);
  }

  public BezierCurveDrawer() {
    super(Path.class);
    setPolySegment(true); // default is false
    setFillColor(Color.MOCCASIN);
    setStrokeColor(Color.SIENNA);
  }

  /**
   * Create a MoveTo, add it to the path
   * Its x, y properties are set to startX, startY
   * Show the start point
   */
  void addMoveTo(DrawPane drawPane, Path path) {
    MoveTo moveTo = new MoveTo();
    moveTo.setX(drawPane.getStartX());
    moveTo.setY(drawPane.getStartY());
    path.getElements().add(moveTo);
    showStartPoint(drawPane, drawPane.getStartX(), drawPane.getStartY());        
  }

  /**
   * Create a QuadCurveTo, add it to the path.
   * Since we only obtain coordinates of 2 points,
   * a straight line instead of a curve is rendered. 
   * Its x, y properties (the end point) are bound to
   * start point add translate distance,
   * do the same binding for controlX, controlY properties.
   * Bind centerX, centerY of end point circle
   * to start point add translate distance. 
   * Show end point.
   * Bind centerX, centerY of control point circle
   * to start point add translate distance. 
   * Show control point.
   */
  void addLineTo(DrawPane drawPane, Path path) {
    // Create a QuadCurveTo rendered like a straight line
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    path.getElements().add(quadCurveTo);
    // Create a DoubleBinding calculates the sum of
    // start position and translate distance
    DoubleBinding draggedX = 
      drawPane.startXProperty().add(drawPane.dragXProperty());
    DoubleBinding draggedY = 
      drawPane.startYProperty().add(drawPane.dragYProperty());
    // Bind end point of curve to the mouse dragged location
    quadCurveTo.xProperty().bind(draggedX);
    quadCurveTo.yProperty().bind(draggedY);
    // Bind control point of curve to the mouse dragged location
    quadCurveTo.controlXProperty().bind(draggedX);
    quadCurveTo.controlYProperty().bind(draggedY);
    // Take care of end point circle:
    // center of end point circle binds to dragged location
    endPoint.centerXProperty().bind(draggedX);
    endPoint.centerYProperty().bind(draggedY);
    showEndPoint(drawPane);
    // Take care of control point circle:
    // center of circle binds to dragged location
    controlPoint.centerXProperty().bind(draggedX);
    controlPoint.centerYProperty().bind(draggedY);
    showControlPoint(drawPane);
  }

  void addQuadCurveTo(DrawPane drawPane, Path path) {
    QuadCurveTo quadCurveTo = new QuadCurveTo();
    path.getElements().add(quadCurveTo);

    // Set x, y properties of curve to mouse pressed location
    quadCurveTo.setX(drawPane.getStartX());
    quadCurveTo.setY(drawPane.getStartY());
    // Show end point circle at mouse pressed location 
    showEndPoint(drawPane, drawPane.getStartX(), drawPane.getStartY());

    // Create a DoubleBinding calculates the sum of
    // start position and translate distance
    DoubleBinding draggedX = 
      drawPane.startXProperty().add(drawPane.dragXProperty());
    DoubleBinding draggedY = 
      drawPane.startYProperty().add(drawPane.dragYProperty());

    // Bind control point of curve to mouse dragged location
    quadCurveTo.controlXProperty().bind(draggedX);
    quadCurveTo.controlYProperty().bind(draggedY);
    // Bind center of control point circle to dragged location
    controlPoint.centerXProperty().bind(draggedX);
    controlPoint.centerYProperty().bind(draggedY);
    // Show control point circle
    showControlPoint(drawPane);
  }

  /**
   * This method is called when DELETE key is hit
   */
  void deleteLastPathElement(DrawPane drawPane, Path path) {
    ObservableList<PathElement> list = path.getElements();
  	if (list.size() > 0) {
      list.remove(list.get(list.size() - 1));
      // If the resulting list is empty,
      // hide circle of start point
      if (list.size() == 0) {
        hideStartPoint(drawPane);
      }	else {
        PathElement element = list.get(list.size() - 1);
        if (element instanceof MoveTo) {
          // update center coordinates of circle of start point 
          MoveTo moveTo = (MoveTo) element;
          setStartPoint(moveTo.getX(), moveTo.getY());
        } else {
          // it must be a QuadCurveTo
          // update center coordinates of circle of start point 
          QuadCurveTo quadCurveTo = (QuadCurveTo) element;
          setStartPoint(quadCurveTo.getX(), quadCurveTo.getY());
        }
      }
    }
  }

  /***
   * This method, defined in ShapeDrawer, is called from
   * DrawPane KeyPressed handler when Enter key is pressed
   */
  @Override
  public void clean(DrawPane drawPane) {
    hideStartPoint(drawPane);
  }

  /***
   * This method, defined in ShapeDrawer, is called from
   * DrawPane KeyPressed handler when Delete key is pressed
   */
  @Override
  public void handleDeleteKeyPressed(DrawPane drawPane) {
    // Hit Delete key to delete the last element
    if (getShape() != null && !drawPane.isDragged()) {
      // Do not allow the delete action if it is
      // in the middle of dragging events, that is,
      // if you hit the Delete key while dragging is in progress,
      // nothing happens.
      deleteLastPathElement(drawPane, (Path)getShape());
    }
  }

  /***
   * This method, defined in ShapeDrawer, is called from
   * DrawPane MouseReleased handler when a genuine clicked
   * is detected
   */
  @Override
  public void handleMouseClicked(DrawPane drawPane) {
    // Create a new Path if it does not exist yet
    if (getShape() == null)	{
      Shape tmpShape = new Path();
      drawPane.setTmpShapeProperties(this, tmpShape);
      setShape(tmpShape);
      drawPane.getChildren().add(tmpShape);
    }
    Path path = (Path) getShape();
    // Add a MoveTo element if this is the beginning of a path,
    // otherwise, get the last element,
    // if last element is a MoveTo, update its x,y properties.
    // if last element is not a MoveTo, add a MoveTo to list 
    ObservableList<PathElement> list = path.getElements();
    if (list.size() > 0) {
      // This is not the beginning of a new path.
      // Get the last element
      PathElement element = list.get(list.size() - 1);
      if (element instanceof MoveTo) {
        // update its x, y
        MoveTo moveTo = (MoveTo) element;
        moveTo.setX(drawPane.getStartX());
        moveTo.setY(drawPane.getStartY());
        setStartPoint(drawPane.getStartX(), drawPane.getStartY());
      } else {
        // is not a MoveTo, add a MoveTo to list
        addMoveTo(drawPane, path);        
      }
    } else {
      // This is a new path, must create a MoveTo to begin a path
      addMoveTo(drawPane, path);        
    }
  }

  @Override
  public void onMouseDragStarted(DrawPane drawPane) {
    // hide cursor
    drawPane.setCursor(Cursor.NONE);
    Path path = (Path)getShape();
    ObservableList<PathElement> list = path.getElements();
    // Check if this is the beginning of a new path
    if (list.size() == 0) {
      // This is a new path with empty element
      // Add a MoveTo followed by a QuadCurveTo
      // Since 3 points are needed to construct a curve,
      // here we only have two points,
      // the QuadCurveTo will look like a straight line,
      // with end point and control point both at the same location.
      addMoveTo(drawPane, path);
      addLineTo(drawPane, path);
    } else {
      // This is an existing path with elements in the list,
      // verify if mouse pressed location is inside the area of start point circle
      if (startPoint.contains(drawPane.getStartX(), drawPane.getStartY())) {
        // This is a special case,
        // startX, startY inside the area of start point circle,
        // we can only draw QuadCurveTo that looks like a straight line,
        // with end point and control point both at the same location.
        addLineTo(drawPane, path);
      }	else {
        // This is a normal case,
        // startX, startY are not within the bounds of start point,
        // Create a normal QuadCurveTo
        addQuadCurveTo(drawPane, path);
      }
    }
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    // Restore cursor
    drawPane.setCursor(Cursor.DEFAULT);
    Path path = (Path)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (path != null) {    
      ObservableList<PathElement> list = path.getElements();
      // The list has at least 2 elements created by either
      // addLineTo method or addQuadCurveTo method, 
      // the checking is redundant.
      if (list.size() > 0) {
        PathElement element = list.get(list.size() - 1);
        //The element must be a QuadCurveTo
        QuadCurveTo quadCurveTo = (QuadCurveTo) element;
        if (quadCurveTo.xProperty().isBound()) {          
          quadCurveTo.xProperty().unbind();
          quadCurveTo.yProperty().unbind();
        }
        if (quadCurveTo.controlXProperty().isBound()) {
          quadCurveTo.controlXProperty().unbind();
         quadCurveTo.controlYProperty().unbind();
        }
        // Take care of end point circle
        if (endPoint.centerXProperty().isBound()) {          
          endPoint.centerXProperty().unbind();
          endPoint.centerYProperty().unbind();
        }
        hideEndPoint(drawPane);
        // Take care of control point circle
        if (controlPoint.centerXProperty().isBound()) {
          controlPoint.centerXProperty().unbind();
          controlPoint.centerYProperty().unbind();
        }
        hideControlPoint(drawPane);
        // Take care of start point circle:
        // end point of this element now becomes the start point of
        // next new element.
        setStartPoint(quadCurveTo.getX(), quadCurveTo.getY());
      }
    }
  }

  /* Followings are utilities for displaying start point, end point, and
   * control point. Each of them is represented by a circle with 
   * different color.
   */

  void setStartPoint(double x, double y) {
    startPoint.setCenterX(x);
    startPoint.setCenterY(y);
  }

  void setEndPoint(double x, double y) {
    endPoint.setCenterX(x);
    endPoint.setCenterY(y);
  }

  void showStartPoint(DrawPane drawPane, double x, double y) {
    if (!drawPane.getChildren().contains(startPoint))
      drawPane.getChildren().add(startPoint);
    setStartPoint(x, y);
  }

  void showEndPoint(DrawPane drawPane) {
    if (!drawPane.getChildren().contains(endPoint))
      drawPane.getChildren().add(endPoint);
  }

  void showEndPoint(DrawPane drawPane, double x, double y) {
    if (!drawPane.getChildren().contains(endPoint))
      drawPane.getChildren().add(endPoint);
    setEndPoint(x, y);
  }

  void showControlPoint(DrawPane drawPane) {
    if (!drawPane.getChildren().contains(controlPoint))
      drawPane.getChildren().add(controlPoint);
  }

  void hideStartPoint(DrawPane drawPane) {
    drawPane.getChildren().remove(startPoint);
  }

  void hideEndPoint(DrawPane drawPane) {
    drawPane.getChildren().remove(endPoint);
  }

  void hideControlPoint(DrawPane drawPane) {
    drawPane.getChildren().remove(controlPoint);
  }

}
```

#### 7.2.5.1 Create Bezier Curve Drawer App

To test `BezierCurveDrawer` class, we create a primitive drawing application that simply draws paths of Bézier curves on a drawing board dynamically. Followings are complete source codes.

Listing 7-13. Source codes of a Bezier curve drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: BezierCurveDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws paths of Bezier curves 
 * dynamically on a drawing board.
 * A simple application that tests BezierCurveDrawer class.
 *
 * @author: Shufen Kuo
 */
public class BezierCurveDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new BezierCurveDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("BezierCurveDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Please note that, Figure 7-5 shows a single `Path` object that consists of multiple elements. The path is rendered into multiple Bézier curves.

Figure 7-5. Snapshot of drawing one path using `Bezier Curve Drawer App` module.

![](images/00035.jpeg "draw_bezier_curve_icons.jpg")

Output from Compiling and Running Bezier Curve Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac  -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.BezierCurveDrawerApp
```

### 7.2.6 Implement `RectangleDrawer` Class

`RectangleDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

For detailed descriptions of drawing `Rectangle` objects, refer to Chapter 6 Basic Draw Tool--Developing Shape Drawing Tools V1.0 Section 6.3.1 [Create `RectangleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-rectangle-drawer-class).

Here are complete source codes of `RectangleDrawer` class.

Listing 7-14. Implement `RectangleDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.binding.DoubleBinding;
import javafx.scene.paint.Color;
import javafx.scene.shape.Rectangle;

import drawtool.*;

/**
 * File Name: RectangleDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class RectangleDrawer extends ShapeDrawer {

  public RectangleDrawer() {
    super(Rectangle.class);
    setFillColor(Color.MISTYROSE);
    setStrokeColor(Color.LIGHTPINK);
  }

  @Override
  public void onMouseDragStarted(final DrawPane drawPane) {
    Rectangle rect = (Rectangle)getShape();

    DoubleBinding xB = new DoubleBinding() {
      {
        super.bind(drawPane.dragXProperty());
      }

      @Override
      protected double computeValue() {
      return (drawPane.getDragX() < 0.0)
        ? drawPane.getStartX() + drawPane.getDragX() : drawPane.getStartX();
      }
    };

    DoubleBinding yB = new DoubleBinding() {
      {
        super.bind(drawPane.dragYProperty());
      }

      @Override
      protected double computeValue() {
        return (drawPane.getDragY() < 0.0)
          ? drawPane.getStartY() + drawPane.getDragY() : drawPane.getStartY();
      }
    };

    DoubleBinding wB = new DoubleBinding() {
      {
        super.bind(drawPane.dragXProperty());
      }

      @Override
      protected double computeValue() {
        return Math.abs(drawPane.getDragX());
      }
    };

    DoubleBinding hB = new DoubleBinding() {
      {
        super.bind(drawPane.dragYProperty());
      }

      @Override
      protected double computeValue() {
        return Math.abs(drawPane.getDragY());
      }
    };

    rect.xProperty().bind(xB);
    rect.yProperty().bind(yB);
    rect.widthProperty().bind(wB);
    rect.heightProperty().bind(hB);   
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Rectangle rect = (Rectangle)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (rect != null) {
      rect.xProperty().unbind();
      rect.yProperty().unbind();
      rect.widthProperty().unbind();
      rect.heightProperty().unbind();
    }
  }

}
```

#### 7.2.6.1 Create Rectangle Drawer App

To test `RectangleDrawer` class, we create a primitive drawing application that simply draws rectangles on a drawing board dynamically. Followings are complete source codes.

Listing 7-15. Source codes of a rectangle drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: RectangleDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws rectangles 
 * dynamically on a drawing board.
 * A simple application that tests RectangleDrawer class.
 *
 * @author: Shufen Kuo
 */

public class RectangleDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new RectangleDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("RectangleDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 7-6. Snapshot of drawing rectangles using `Rectangle Drawer App` module.

![](images/00036.jpeg "draw_rectangle_icons.jpg")

Output from Compiling and Running Rectangle Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.RectangleDrawerApp
```

### 7.2.7 Implement `CircleDrawer` Class

`CircleDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

For detailed descriptions of drawing `Circle` objects, refer to Chapter 6 Basic Draw Tool--Developing Shape Drawing Tools V1.0 Section 6.3.2 [Create `CircleDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-circle-drawer-class).

Here are complete source codes of `CircleDrawer` class.

Listing 7-16. Implement `CircleDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.binding.DoubleBinding;
import javafx.scene.paint.Color;
import javafx.scene.shape.Circle;

import drawtool.*;

/**
 * File Name: CircleDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class CircleDrawer extends ShapeDrawer {

  public CircleDrawer() {
    super(Circle.class);
    setFillColor(Color.GOLD);
    setStrokeColor(Color.CORAL);
  }

  @Override
  public void onMouseDragStarted(final DrawPane drawPane) {
    Circle cs = (Circle)getShape();

    DoubleBinding rB = new DoubleBinding() {
      {
        super.bind(drawPane.dragXProperty(), drawPane.dragYProperty());
      }

      @Override
      protected double computeValue() {
        double dx = drawPane.getDragX();
        double dy = drawPane.getDragY();
        return Math.sqrt(dx*dx + dy*dy);
      }
    };
    cs.centerXProperty().bind(drawPane.startXProperty());
    cs.centerYProperty().bind(drawPane.startYProperty());
    cs.radiusProperty().bind(rB);

  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Circle cs = (Circle)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (cs != null) {
      cs.centerXProperty().unbind();
      cs.centerYProperty().unbind();
      cs.radiusProperty().unbind();
    }
  }

}
```

#### 7.2.7.1 Create Circle Drawer App

To test `CircleDrawer` class, we create a primitive drawing application that simply draws circles on a drawing board dynamically. Followings are complete source codes.

Listing 7-17. Source codes of a circle drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: CircleDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws circles 
 * dynamically on a drawing board.
 * A simple application that tests CircleDrawer class.
 *
 * @author: Shufen Kuo
 */
public class CircleDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new CircleDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("CircleDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 7-7. Snapshot of drawing circles using `Circle Drawer App` module.

![](images/00037.jpeg "draw_circle_icons.jpg")

Output from Compiling and Running Circle Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.CircleDrawerApp
```

### 7.2.8 Implement `EllipseDrawer` Class

`EllipseDrawer` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

For detailed descriptions of drawing `Ellipse` objects, refer to Chapter 6 Basic Draw Tool--Developing Shape Drawing Tools V1.0 Section 6.3.3 [Create `EllipseDrawer` Class as Subclass of `Application`](#part0012_split_003.html_create-ellipse-drawer-class).

Here are complete source codes of `EllipseDrawer` class.

Listing 7-18. Implement `EllipseDrawer` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.beans.binding.DoubleBinding;
import javafx.scene.paint.Color;
import javafx.scene.shape.Ellipse;

import drawtool.*;

/**
 * File Name: EllipseDrawer.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class EllipseDrawer extends ShapeDrawer {

  public EllipseDrawer() {
    super(Ellipse.class);
    setFillColor(Color.GREENYELLOW);
    setStrokeColor(Color.DARKGREEN);
  }

  @Override
  public void onMouseDragStarted(final DrawPane drawPane) {
    Ellipse es = (Ellipse)getShape();

    DoubleBinding wB = new DoubleBinding() {
      {
        super.bind(drawPane.dragXProperty());
      }

      @Override
      protected double computeValue() {
        return Math.abs(drawPane.getDragX());
      }
    };
    DoubleBinding hB = new DoubleBinding() {
      {
        super.bind(drawPane.dragYProperty());
      }

      @Override
      protected double computeValue() {
        return Math.abs(drawPane.getDragY());
      }
    };    
    es.centerXProperty().bind(drawPane.startXProperty());
    es.centerYProperty().bind(drawPane.startYProperty());
    es.radiusXProperty().bind(wB);
    es.radiusYProperty().bind(hB);    
  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    Ellipse es = (Ellipse)getShape();
    // Must verify shape is not null here
    // shape is set to null if Enter key or Esc key has been hit
    if (es != null) {
      es.centerXProperty().unbind();
      es.centerYProperty().unbind();
      es.radiusXProperty().unbind();
      es.radiusYProperty().unbind();
    }
  }

}
```

#### 7.2.8.1 Create Ellipse Drawer App

To test `EllipseDrawer` class, we create a primitive drawing application that simply draws ellipses on a drawing board dynamically. Followings are complete source codes.

Listing 7-19. Source codes of an ellipse drawing application:

```
package drawerapp;

import javafx.application.Application;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: EllipseDrawerApp.java
 * (in directory: DrawTool1.1/src/example1/drawerapp/)
 * This application draws ellipses 
 * dynamically on a drawing board.
 * A simple application that tests EllipseDrawer class.
 *
 * @author: Shufen Kuo
 */
public class EllipseDrawerApp extends Application {

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    DrawPane drawPane = new DrawPane(new EllipseDrawer());
    rootPane.setCenter(drawPane);

    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);
    stage.setScene(scene);
    stage.setTitle("EllipseDrawerApp V1.0 Shufen Source Code");
    stage.show();
  }

  public static void main(String[] args) {
    launch(args);
  }
}
```

Figure 7-8. Snapshot of drawing ellipses using `Ellipse Drawer App` module.

![](images/00038.jpeg "draw_ellipse_icons.jpg")

Output from Compiling and Running Ellipse Drawer App in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar drawerapp\*.java

jar cf drawerapp.jar drawerapp

java -cp drawtool.jar;drawerapp.jar drawerapp.EllipseDrawerApp
```

### 7.2.9 Implement `ShapeMover` Class

Unlike the other subclasses of `ShapeDrawer`, `ShapeMover` does not perform any drawing while mouse dragged events occur, it moves the target node around a drawing board.

`ShapeMover` class extends `ShapeDrawer` by implementing two abstract methods:

```
 public abstract void onMouseDragStarted(DrawPane drawPane)
  public abstract void onMouseDragFinished(DrawPane drawPane) 
```

A major difference in implementation between a drawer and a mover is that the value of `shapeClass` property for a mover is set to `null`, which is passed to the constructor of super class.

Here are complete source codes of `ShapeMover` class.

Listing 7-20. Implement `ShapeMover` class, a direct subclass of `ShapeDrawer`:

```
package drawtool.drawer;

import javafx.event.EventTarget;
import javafx.scene.Node;
import javafx.scene.shape.Shape;
import javafx.scene.input.MouseEvent;
import drawtool.*;

/**
 * File Name: ShapeMover.java
 * (in directory: DrawTool1.1/src/example1/drawtool/drawer)
 *
 * @author: Shufen Kuo
 */

public class ShapeMover extends ShapeDrawer {

  public ShapeMover() {
    super(null);
  }

  @Override
  public void onMouseDragStarted(final DrawPane drawPane) {
    MouseEvent me = drawPane.getMouseEvent();

    if (me != null) {
      EventTarget et = me.getTarget();
      if (et instanceof Shape) {
        Node node = (Node)et;
        double origx = node.getTranslateX();
        double origy = node.getTranslateY();
        node.translateXProperty().bind(drawPane.dragXProperty().add(origx));
        node.translateYProperty().bind(drawPane.dragYProperty().add(origy));
      }
    }

  }

  @Override
  public void onMouseDragFinished(DrawPane drawPane) {
    MouseEvent me = drawPane.getMouseEvent();
    if (me != null) {
      EventTarget et = me.getTarget();
      if (et instanceof Shape) {
        Node node = (Node)et;
        node.translateXProperty().unbind();
        node.translateYProperty().unbind();
      }
    }
  }

}
```

Usages of `ShapeMover` will be explored in next chapter, where we develop initial version of `JFXDrawTools` application.

## 7.3 Enhance `DrawPane` Class

To fulfill demands from advanced shape drawing applications, we empower `DrawPane` with more capabilities.

Here are complete source codes of enhanced `DrawPane` class, major differences comparing to V1.0, developed from [Chapter 6 Basic Draw Tool--Developing Shape Drawing Tools V1.0](#part0012_split_000.html_BE6O0-4cbb8f9352704a549e363e38a5243855), are shown in bold face.

Listing 7-21. Enhance `DrawPane` Class:

```
package drawtool;

import javafx.beans.property.BooleanProperty;
import javafx.beans.property.DoubleProperty;
import javafx.beans.property.ObjectProperty;
import javafx.beans.property.SimpleBooleanProperty;
import javafx.beans.property.SimpleDoubleProperty;
import javafx.beans.property.SimpleObjectProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.EventHandler;
import javafx.scene.input.KeyCode;
import javafx.scene.input.KeyEvent;
import javafx.scene.input.MouseEvent;
import javafx.scene.layout.Pane;
import javafx.scene.shape.Shape;

/**
 * File Name: DrawPane.java
 * (in directory: DrawTool1.1/src/example1/drawtool/)
 * DrawPane is a subclass of Pane which does not perform automatic layout on its children.
 *
 * Define variables
 *   startX, startY, dragX, dragY are properties to hold double values:
 *
 *     startX/startY specifies coordinates of mouse pressed event.
 *
 *     dragX/dragY specifies translate distance from current dragged location to
 *     mouse pressed location. 
 *
 *   dragged is a boolean property, its value is initialized to false, 
 *   and is set to true during the first mouse dragged event occurs.
 *   It is reset to false when dragged event finished, that is, 
 *   when a sequence of mouse dragged events is ended by a mouse released event.
 *
 *   drawer, a property to hold the current drawer, a subclass of ShapeDrawer.
 *   ShapeDrawer, resides in drawtool package, is the base class for all drawers. 
 *
 * Register event handlers to handle the following events:
 *  mouse pressed, mouse dragged, mouse released, key pressed
 * these events are significant to draw shapes interactively on a drawing board.
 *
 * @author: Shufen Kuo
 */

public class DrawPane extends Pane {

  /* Declare variables */

  // mouse location relative to origin of MouseEvent's source, which is DrawPane
  public DoubleProperty eventX = new SimpleDoubleProperty();
  public DoubleProperty eventY = new SimpleDoubleProperty();

  // mouse location relative to origin of screen,
  // this information is referenced when key event occurs
  public DoubleProperty screenX = new SimpleDoubleProperty();
  public DoubleProperty screenY = new SimpleDoubleProperty();

  // this is for ShapeMover, to get event target when mouse event occurs
  public ObjectProperty<MouseEvent> mouseEvent = 
    new SimpleObjectProperty<>();

  // mouse location when mouse is pressed
  public DoubleProperty startX = new SimpleDoubleProperty();
  public DoubleProperty startY = new SimpleDoubleProperty();
  // mouse dragged distance calculated from mouse dragged location to
  // mouse pressed location
  public DoubleProperty dragX = new SimpleDoubleProperty();
  public DoubleProperty dragY = new SimpleDoubleProperty();

  public BooleanProperty dragged = new SimpleBooleanProperty();

  // Specify the current drawer of pane
  // An application may create multiple drawers and
  // switch between drawers dynamically as required
  public ObjectProperty<ShapeDrawer> drawer = new SimpleObjectProperty<>();

  // Passing drawer to constructor
  public DrawPane(ShapeDrawer tool) {
    this();
    drawer.set(tool);
  }

  public DrawPane() {

    setOnMouseMoved(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseMoved(me);
      }
    });

    setOnMousePressed(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMousePressed(me);
      }
    });

    setOnMouseDragged(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseDragged(me);
      }
    });

    setOnMouseReleased(new EventHandler<MouseEvent>() {
      @Override
      public void handle(MouseEvent me) {
        drawOnMouseReleased(me);
      }
    });

    // set focusTraversable property to true in order to handle KeyEvent, 
    // default is false.
    setFocusTraversable(true);
    setOnKeyPressed(new EventHandler<KeyEvent>() {
      @Override
      public void handle(KeyEvent ke) {
        drawOnKeyPressed(ke);
      }
    });

    // Listen to the value changed of property drawer
    drawerProperty().addListener(new ChangeListener<ShapeDrawer>() {
      @Override
      public void changed(ObservableValue o, ShapeDrawer oldVal,
          ShapeDrawer newVal) {
         // this is important for poly segments shape
         // need take care of unfinished job
         // especially when old drawer is path drawer and
         // new drawer is bezier curve drawer
         if (oldVal != null)
           finalizeUnfinished(oldVal);
      }
    });

  }

  void setMouseLoc(MouseEvent me) {
    eventX.set(me.getX());
    eventY.set(me.getY());
    screenX.set(me.getScreenX());
    screenY.set(me.getScreenY());
    mouseEvent.set(me);
  }

  public void setTmpShapeProperties(ShapeDrawer drawTool, Shape tmpShape) {
    tmpShape.setFill(drawTool.getFillColor());
    tmpShape.setStroke(drawTool.getStrokeColor());
    if (drawTool.getStrokeWidth() > 0)
      tmpShape.setStrokeWidth(drawTool.getStrokeWidth());
    if (drawTool.getStrokeType() != null)
      tmpShape.setStrokeType(drawTool.getStrokeType());
  }

  public void drawOnMouseMoved(MouseEvent me) {
    setMouseLoc(me);
  }

  /**
   * This method is invoked from handle method of event handler of mouse pressed
   *
   * Keep the coordinate of mouse pressed location in correlated properties 
   */
  // change from protected to public for application showing context menu, tmp solution
  public void drawOnMousePressed(MouseEvent me) {
    setStartX(me.getX());
    setStartY(me.getY());

    // also need update event x/y, screen x/y
    setMouseLoc(me);
  }

  /**
   * This method is invoked from handle method of event handler of mouse dragged
   *
   * Keep the translate distance in dragX and dragY properties,
   * it's calculated from current mouse dragged location to mouse pressed location 
   *
   * A shape is created when the dragged action starts, 
   * invoke getDrawer().getShapeClass() methods to determine which shape to be created
   *
   * Take into account the following special case:
   *   if a menu is on showing, and
   *   mouse pressed on the drawing board, 
   *   the event is caught and consumed by menu items, results in
   *   draw pane catches the mouse dragged event without
   *   catching the prior mouse pressed event,
   *   this problem occurs: current startX, startY locations are not updated.
   *   To solve it: update startX/startY when the first dragged event detected. 
   */
  protected void drawOnMouseDragged(MouseEvent me) {
    // also need update event x/y, screen x/y
    setMouseLoc(me);

    // this is to fix the problem caused by	menu item
    // menu item catches and consumes the mouse pressed event prior to dragged event
    // pressed is a boolean property defined in Node class
    if (!isPressed() && !isDragged()){
      // pressed event prior to dragged event is not caught by drawpane
      // therefore, startX/startY location is not updated,
      // we need do this only once, when the first dragged event detected:
      setStartX(me.getX());
      setStartY(me.getY());
    }
    setDragX(me.getX() - getStartX());
    setDragY(me.getY() - getStartY()); 
    if (!isDragged()) {
      // Did this only once, and create the temporary shape only once
      // for each PRESSED-DRAGGED-RELEASED event cycle. 
  /*
   * Note: we want slightly different actions in here
   * we don't want hit Enter key to finalize a shape each time,
   * instead, we want a shape to stay on drawing board unless Esc key
   * is pressed.
   */
  /*
   * We want support both cases:
   * case 1: hit Enter key to finalize a shape drawn.
   * case 2: need not hit Enter key, this is default,
   *         a shape is finalized unless Esc key is hit.
   * For a shape need multiple pressed-dragged-released cycles,
   * such as polyline, polygon, path of straight lines, and
   * path of Bezier curves,
   * case 1 is adopted, need to set polySegment property to true
   */     
      if (getDrawer() != null && getDrawer().getShapeClass() != null) {
        ShapeDrawer tool = getDrawer();
        Shape sketch = tool.getShape();
        if (sketch == null ||
            !tool.getShapeClass().isInstance(sketch) ||
            !tool.isPolySegment())
          // if it is a shape with poly segments,
          // we do not want to re-create a new shape when
          // getShape() is not null  
          try {
            Shape tmpShape = tool.getShapeClass().newInstance();
            setTmpShapeProperties(tool, tmpShape);
            tool.setShape(tmpShape);
            getChildren().add(tmpShape);
          } catch (InstantiationException | IllegalAccessException ex) {
          }
      }

      setDragged(true);
      // onMouseDragStarted method, defined in ShapeDrawer, is called from
      // event handler that handles MOUSE_DRAGGED type of mouse event,
      // it is called only once,
      // at the first time mouse dragged event is detected.
      if (getDrawer() != null)
        getDrawer().onMouseDragStarted(this);
    }
  }

  /**
   * This method is invoked from handle method of event handler of mouse released
   */
  protected void drawOnMouseReleased(MouseEvent me) {
    // Need to update mouse loc ???

    if (isDragged()) {
      setDragged(false);
      if (getDrawer() != null)
        getDrawer().onMouseDragFinished(this);
    } else {
      // This is a genuine mouse clicked
      if (getDrawer() != null)
        getDrawer().handleMouseClicked(this);
    }    
  }

  /**
   * This method is invoked from handle method of event handler of key pressed
   */
  protected void drawOnKeyPressed(KeyEvent ke) {
    KeyCode kc = ke.getCode();
    switch (kc) {
      case ENTER:
        drawOnEnterKeyPressed(); 
        break;
      case ESCAPE:
        drawOnEscapeKeyPressed();
        break;
      case DELETE:
        drawOnDeleteKeyPressed();
        break;
     }       
  }

  /**
   *  This method is called when drawer is changed
   *  Need clean up unfinished jobs
   */
  void finalizeUnfinished(ShapeDrawer tool) {
    if (tool != null && tool.getShape() != null) {
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      tool.setShape(null);  // complete this shape
    }
  }

  protected void drawOnEnterKeyPressed() {
    // Hit Enter key to finalize this shape
    // Must call drag finished method to handle unbinding
    ShapeDrawer tool = getDrawer();
    if (tool != null && tool.getShape() != null) {
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      tool.setShape(null);  // complete this shape
    }
  } 

  protected void drawOnEscapeKeyPressed() {
    // Hit Esc key to clear this shape
    if (getDrawer() != null && getDrawer().getShape() != null) {
      // Must call drag finished method to handle unbinding
      ShapeDrawer tool = getDrawer();
      Shape s = tool.getShape();
      if (isDragged()) {
        tool.onMouseDragFinished(this);
      }
      tool.clean(this);
      getChildren().remove(s);
      tool.setShape(null);  // clear this shape
    }
  }

  protected void drawOnDeleteKeyPressed() {
    if (getDrawer() != null)
      getDrawer().handleDeleteKeyPressed(this);
  }

  /* Followings are utilities to manipulate properties */

  public void setDrawer(ShapeDrawer value) {
    drawer.set(value);
  }

  public ShapeDrawer getDrawer() {
    return drawer.get();
  }

  public ObjectProperty<ShapeDrawer> drawerProperty() {
    return drawer;
  }

  public boolean isDragged() {
    return dragged.get();
  }

  public void setDragged(boolean value) {
    dragged.set(value);
  }

  public BooleanProperty draggedProperty() {
    return dragged;
  }

  public double getStartX() {
    return startX.get();
  }

  public void setStartX(double value) {
    startX.set(value);
  }

  public DoubleProperty startXProperty() {
    return startX;
  }

  public double getStartY() {
    return startY.get();
  }

  public void setStartY(double value) {
    startY.set(value);
  }

  public DoubleProperty startYProperty() {
    return startY;
  }

  public double getDragX() {
    return dragX.get();
  }

  public void setDragX(double value) {
    dragX.set(value);
  }

  public DoubleProperty dragXProperty() {
    return dragX;
  }

  public double getDragY() {
    return dragY.get();
  }

  public void setDragY(double value) {
    dragY.set(value);
  }

  public DoubleProperty dragYProperty() {
    return dragY;
  }

  public void setScreenX(double value) {
    screenX.set(value);
  }

  public double getScreenX() {
    return screenX.get();
  }

  public DoubleProperty screenXProperty() {
    return screenX;
  }

  public void setScreenY(double value) {
    screenY.set(value);
  }

  public double getScreenY() {
    return screenY.get();
  }

  public DoubleProperty screenYProperty() {
    return screenY;
  }

  public void setEventX(double value) {
    eventX.set(value);
  }

  public double getEventX() {
    return eventX.get();
  }

  public DoubleProperty eventXProperty() {
    return eventX;
  }

  public void setEventY(double value) {
    eventY.set(value);
  }

  public double getEventY() {
    return eventY.get();
  }

  public DoubleProperty eventYProperty() {
    return eventY;
  }

  public void setMouseEvent(MouseEvent value) {
    mouseEvent.set(value);
  }

  public MouseEvent getMouseEvent() {
    return mouseEvent.get();
  }

  public ObjectProperty<MouseEvent>mouseEventProperty() {
    return mouseEvent;
  }
}
```

## 7.4 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in the chapter:

*   `Shape` class, resides in `javafx.scene.shape` package, provides functionality for rendering 2D geometric primitives such as rectangle, circle, ellipse, etc.
    (See sections: [Enhance `ShapeDrawer` Class](#part0013_split_001.html_enhance-shape-drawer), [Implement `ShapeMover`](#part0013_split_002.html_implement-shape-mover), [Enhance `DrawPane` Class](#part0013_split_003.html_enhance-draw-pane))
*   Some of classes from `javafx.beans.property` package:

    `BooleanProperty`

    Is an abstract class, derived from `javafx.beans.binding.BooleanExpression` class, implements `Property<java.lang.Boolean>` and `WritableBooleanValue`.
    `WritableBooleanValue` extends `WritableValue<java.lang.Boolean>`.

    `SimpleBooleanProperty`

    Derived from `BooleanProperty` class.

    `DoubleProperty`

    Is an abstract class, derived from `javafx.beans.binding.DoubleExpression` class, implements `Property<Number>` and `WritableDoubleValue`.
    `WritableDoubleValue` extends `WritableNumberValue`.

    `SimpleDoubleProperty`

    Derived from `DoubleProperty` class.

    `ObjectProperty<T>`

    Is an abstract class, derived from `javafx.beans.binding.ObjectExpression<T>` class, implements `Property<T>` and `WritableObjectValue<T>`.

    `SimpleObjectProperty<T>`

    Derived from `ObjectProperty<T>` class.

    (See sections: [Define Shape Rendering Properties](#part0013_split_001.html_define-shape-properties), [Define a Boolean Property `polySegment`](#part0013_split_001.html_define-poly-segment))
*   `Color`, resides in `javafx.scene.paint package`, is a direct subclass of `Paint` class, the base class of colors and gradients, for painting background or border of `Shape`.
    (See [here](#part0013_split_001.html_define-shape-properties-codes), [here](#part0013_split_002.html_line-drawer-constructor), [here](#part0013_split_002.html_polyline-drawer-constructor), [here](#part0013_split_002.html_polygon-drawer-constructor), [here](#part0013_split_002.html_path-drawer-constructor), [here](#part0013_split_002.html_init-control-points-codes), [here](#part0013_split_002.html_bezier-curve-drawer-constructor), [here](#part0013_split_002.html_rectangle-drawer-constructor), [here](#part0013_split_002.html_circle-drawer-constructor), [here](#part0013_split_002.html_ellipse-drawer-constructor))
*   Some of properties defined in `Shape` class:

    `fill`

    Specify a `Paint` object as background color of a shape.

    `stroke`

    Specify a `Paint` object as border color of a shape.

    `strokeType`

    Specify a `StrokeType` object, an enumeration type, as border type of a shape. The constant values are: `CENTERED`, `INSIDE`, `OUTSIDE`. Default value is `CENTERED`.

    `strokeWidth`

    Specify a double value as border width of a shape.

    (See [Define Shape Rendering Properties](#part0013_split_001.html_define-shape-properties), [here](#part0013_split_003.html_set-tmp-shape-properties-method) )
*   `WritableObjectValue<T>` interface, resides in `javafx.beans.value` package and extends `WritableValue<T>`, defines the following methods:

    `T get()`

    Get the wrapped value.

    `void set(T value)`

    Set the wrapped value.

    (See [here](#part0013_split_001.html_shape-drawer-property-utils), [here](#part0013_split_003.html_draw-pane-property-utils))
*   `Line` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides four properties to specify a line's location: `startX`, `startY`, `endX`, and `endY`.
    (See section [Implement `LineDrawer` Class](#part0013_split_002.html_implement-line-drawer))
*   `Property<T>` interface, resides in `javafx.beans.property` package, defines methods common to all properties such as:

    `void bind(ObservableValue<? extends T> observable)`

    Bind this property unidirectional to the given `ObservableValue`.

    `void unbind()`

    Unbind for this property.

    (See [here](#part0013_split_002.html_line-drawer-class-source-codes), [here](#part0013_split_002.html_polyline-drawer-class-source-codes), [here](#part0013_split_002.html_polygon-drawer-class-source-codes), [here](#part0013_split_002.html_bezier-curve-drawer-class-source-codes), [here](#part0013_split_002.html_rectangle-drawer-class-source-codes), [here](#part0013_split_002.html_circle-drawer-class-source-codes), [here](#part0013_split_002.html_ellipse-drawer-class-source-codes), [here](#part0013_split_002.html_shape-mover-class-source-codes))
*   `Polyline`, reside in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. Use `getPoints()` method to obtain a list which is type of `ObservableList<Double>`, then use the basic utilities, defined in `Collection` interface, to add a series of x and y coordinates, stored in an array of `Double` value, to the list, representing points of a `Polyline`.
    (See section [Implement `PolylineDrawer` Class](#part0013_split_002.html_implement-polyline-drawer))
*   `Polygon`, reside in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. Use `getPoints()` method to obtain a list which is type of `ObservableList<Double>`, then use the basic utilities, defined in `Collection` interface, to add a series of x and y coordinates, stored in an array of `Double` value, to the list, representing points of a `Polygon`.
    (See section [Implement `PolygonDrawer` Class](#part0013_split_002.html_implement-polygon-drawer))
*   `Path` class, resides in `javafx.scene.shape` package, is a direct subclass of `Shape`. A `Path` is constructed with `PathElement`s.
    (See sections: [Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer), [Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer))
*   `PathElement`, an abstract class, resides in `javafx.scene.shape` package; its direct subclasses are: `ArcTo`, `ClosePath`, `CubicCurveTo`, `HLineTo`, `LineTo`, `MoveTo`, `QuadCurveTo`, `VLineTo`.
    (See sections: [Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer), [Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer))
*   `public final ObservableList<PathElement> getElements()` method, provided in `Path` class, returns a list which is type of `ObservableList<PathElement>`. Use the basic utilities, defined in `Collection` interface to add `PathElement` objects to the list.
    (See sections: [Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer), [Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer))
*   `LineTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`; it creates a line element for a path, from the end point of last element to the specified x, y coordinates.
    (See section [Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer))
*   `MoveTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`; it creates a path element which moves the location to the specified x, y coordinates.
    (See sections: [Implement `PathDrawer` Class](#part0013_split_002.html_implement-path-drawer), [Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer))
*   `QuadCurveTo`, resides in `javafx.scene.shape` package, a direct subclass of `PathElement`; it creates a quadratic Bézier curve element for a path.
    (See section [Implement `BezierCurveDrawer` Class](#part0013_split_002.html_implement-bezier-curve-drawer))
*   `DoubleBinding`, an abstract class resides in `javafx.beans.binding` package, extends `DoubleExpression` and implements `NumberBinding`. The `computeValue()` method need to be implemented in order to instantiate a `DoubleBinding` object. Usually call `bind(Observable... dependencies)` method to observe the value changes of dependencies for this `DoubleBinding`.
    (See [here](#part0013_split_002.html_bezier-curve-drawer-class-source-codes), [here](#part0013_split_002.html_rectangle-drawer-class-source-codes), [here](#part0013_split_002.html_circle-drawer-class-source-codes), [here](#part0013_split_002.html_ellipse-drawer-class-source-codes))
*   `Rectangle` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw rectangle shapes with specified properties, such as `x`, `y`, `width`, `height`, etc.
    (See section [Implement `RectangleDrawer` Class](#part0013_split_002.html_implement-rectangle-drawer))
*   `Circle` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw circle shapes with specified properties, such as `centerX`, `centerY`, and `radius`.
    (See section [Implement `CircleDrawer` Class](#part0013_split_002.html_implement-circle-drawer))
*   `Ellipse` class, resides in `javafx.scene.shape` package, is a direct subclass of `javafx.scene.shape.Shape`. It provides functionality to draw ellipse shapes with specified properties, such as `centerX`, `centerY`, `radiusX`, and `radiusY`.
    (See section [Implement `EllipseDrawer` Class](#part0013_split_002.html_implement-ellipse-drawer))
*   `Pane` class, extends `javafx.scene.layout.Region` and resides in `javafx.scene.layout` package, is the base class of JavaFX build-in layout panes.
    (See section [Enhance `DrawPane` Class](#part0013_split_003.html_enhance-draw-pane))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See [here](#part0013_split_003.html_draw-pane-class-source-codes))
*   `MouseEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `MOUSE_CLICKED`, `MOUSE_DRAGGED`, `MOUSE_ENTERED`, `MOUSE_EXITED`, `MOUSE_MOVED`, `MOUSE_PRESSED`, `MOUSE_RELEASED`, etc., and provides methods such as `getX()`, `getY()`, etc., to get position of mouse cursor while event occurs.
    (See [here](#part0013_split_003.html_draw-pane-class-source-codes))
*   Some of convenience methods provided in `Node` class to register `EventHandler`s to handle mouse events.

    `public final void setOnMouseMoved(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_MOVED` event type of `MouseEvent`.

    `public final void setOnMousePressed(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_PRESSED` event type of `MouseEvent`.

    `public final void setOnMouseDragged(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_DRAGGED` event type of `MouseEvent`.

    `public final void setOnMouseReleased(EventHandler<? super MouseEvent>` value`)`

    Register an `EventHandler` to handle `MOUSE_RELEASED` event type of `MouseEvent`.

    (See [here](#part0013_split_003.html_draw-pane-constructor-codes))
*   `KeyEvent` class, resides in `javafx.scene.input` package, is a subclass of `javafx.scene.input.InputEvent`. It defines event types such as `KEY_PRESSED`, `KEY_RELEASED`, `KEY_TYPED`, etc., and provides methods such as `getCode()`, `getCharacter()`, `getText()`, etc., to get information about keys in type of either `KeyCode`, or `String`. It also provides boolean methods such as `isControlDown()`, `isShiftDown()`, `isAltDown()`, etc., to verify whether some of modifier keys are pressed at the same time.
    (See [here](#part0013_split_003.html_set-focus-traversable), [here](#part0013_split_003.html_draw-on-key-pressed-codes))
*   `public final void setOnKeyPressed(EventHandler<? super KeyEvent>` value`)`, a convenience method provided in `Node` class, registers an `EventHandler` to handle `KEY_PRESSED` event type of `KeyEvent`.
    (See [here](#part0013_split_003.html_set-focus-traversable))
*   `focusTraversable` is a property defined in `Node` class for specifying whether this node is traversable and eligible to receive focus. Default value is `false`.
    (See [here](#part0013_split_003.html_set-focus-traversable))
*   `void addListener(ChangeListener<? super T> listener)` method, defined in `javafx.beans.value.ObservableValue` interface, adds a `ChangeListener` by providing `changed(ObservableValue<? extends T>` observable`, T` oldValue`, T` newValue`)` method, to be invoked when this property's value is changed.
    (See [here](#part0013_split_003.html_draw-pane-add-listener-codes))
*   `KeyCode` class, resides in `javafx.scene.input` package, is an enumerated type defines constants for keys of keyboard, it covers letter keys (`A` to `Z`), digits keys(`DIGIT0` to `DIGIT9`), modifier keys(such as `CONTROL`, `SHIFT`, etc.), function keys, etc.
    (See [here](#part0013_split_003.html_draw-on-key-pressed-codes))

# Chapter 8
Initial JFXDrawTools Application
--Developing JFXDrawTools V1.0

## Preface

In this chapter, we will develop initial version of `JFXDrawTools` utilizing enhanced shape drawing APIs provided in `drawtool` package and `drawtool.drawer` package. All of drawing modules developed prior to this chapter are integrated into `JFXDrawTools V1.0`. And more functions will be incrementally added to it in chapters from later volumes of the book series.

From detailed descriptions and well-documented example codes excerpted from developments of `JFXDrawTools V1.0`, you will become familiar with fundamental capabilities of JavaFX packages recounted in the [Summary](#part0014_split_004.html_summary) section.

The complete development process of `JFXDrawTools V1.0` is characterized by the following steps:

1.  [8.1 Create Skeleton of `JFXDrawTools`](#part0014_split_001.html_create-skeleton)
    *   [8.1.1 Create `JFXDrawTools` Class as Subclass of Application](#part0014_split_001.html_create-jfx-draw-tools-class)
    *   [8.1.2 Create Status Bar](#part0014_split_001.html_create-status-bar)
    *   [8.1.3 Create Menu Bar](#part0014_split_001.html_create-menu-bar)
    *   [8.1.4 Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator)
    *   [8.1.5 Define Enumeration Type `DrawTools`](#part0014_split_001.html_define-enum-draw-tools)
    *   [8.1.6 Complete Source Codes of Skeleton of `JFXDrawTools` Class](#part0014_split_001.html_complete-source-codes-skeleton)
2.  [8.2 Create Instances of Shape Drawers](#part0014_split_002.html_create-drawers)
    *   [8.2.1 Activate Drawer for a Draw Pane](#part0014_split_002.html_activate-drawer)
3.  [8.3 Complete Source Codes of `JFXDrawTools` Class](#part0014_split_003.html_complete-source-codes-jfx-draw-tools)
4.  [8.4 Summary](#part0014_split_004.html_summary)

## 8.1 Create Skeleton of `JFXDrawTools`

In this section, we create a skeleton of `JFXDrawTools` application which possesses all required user interfaces: a `MenuBar` with `Tools` menu, a `DrawPane` as drawing board, and a status bar to display footer.

### 8.1.1 Create `JFXDrawTools` Class as Subclass of Application

The first step, we create `JFXDrawTools` as subclass of application, having a `BorderPane` as root node, with a `DrawPane` in the center as a drawing board.

Listing 8-1. Create `JFXDrawTools` Class which extends `Application` class, override `start` method, create `BorderPane` as root node of scene, and place `DrawPane` in the center of `BorderPane` as a drawing board:

```
package jfxdrawtools;

import javafx.application.Application;
import javafx.scene.image.Image;
import javafx.scene.layout.BorderPane;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.stage.Stage;

import drawtool.*;

/**
 * File Name: JFXDrawTools.java
 *
 * This application draws a variety of shapes dynamically on a drawing board.
 *
 * @author: Shufen Kuo
 */

public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane;

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    drawPane = new DrawPane();
    rootPane.setCenter(drawPane);

    rootPane.setStyle("-fx-background-color: transparent;");
    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("JFXDrawTools V1.0 Shufen Source Code");

    // set application's closed icon
    String iconName = "/resource/swan16.jpg";
    Image iconImage = new Image(getClass().getResourceAsStream(
        iconName));
    stage.getIcons().add(iconImage);

    stage.show();
  }

}
```

In the above codes, we set an image, /resource/swan16.jpg, as the minimized icon of application's window. Here's the image:

Figure 8-1. Image as minimized icon of application's window.

![](images/00039.jpeg "resource/swan16.jpg")

If you are a developer interested in compiling this program successfully, you can either replace the icon image with the one you prefer, or extract the image file, swan16.jpg, from HTML files of this e-Book to a directory named `resource`. The `resource` directory should be inside the directory where you put the `jfxdrawtools` package.

Here's a suggestion regarding converting `.mobi` format of an e-Book to HTML:

1.  Install `Calibre`, a free and open source E book Management software, to your PC.
2.  Use `Add books` function in `Calibre` to add the `.mobi` file of this e-Book to `Calibre` Library.
3.  Use `Convert books` function in `Calibre`, select `HTMLZ` as output format, click `OK` button to proceed to the conversion.
4.  When the conversion completes, you'll get an output file with extension `.htmlz`. Rename the extension to be `.zip` and unzip the file, you'll get one large HTML file with a directory named `images` containing all image files that are linked within contents of the HTML file.

    If you are using Windows 8, the `.htmlz` output file is stored in a sub directory of this directory:

    ```
    C:\Users\<User Name>\Documents\Calibre Library
    ```

### 8.1.2 Create Status Bar

An `HBox` containing a `Text` object is created and placed at the bottom of `BorderPane` as a status bar. A `StringProperty`, `footer`, is defined to specify strings to be displayed on the status bar. Here are snippets of codes to do these:

Import Statements:

```
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
import javafx.geometry.Insets;
import javafx.scene.layout.HBox;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.Text;
```

Listing 8-2. Create status bar, placed at the bottom of border pane:

```
 // Specify text to be shown on status bar at bottom of border pane 
  StringProperty footer = new SimpleStringProperty();

  @Override
  public void start(Stage stage) {

    ...

    // Add status bar to show footer
    HBox statusBar = createStatusBar();
    rootPane.setBottom(statusBar);

    ...

  }

  /***
   * Create status bar
   ***/
  HBox createStatusBar() {
    HBox statusBar = new HBox();
    Text statusText = new Text("");

    // binding text and footer
    statusText.textProperty().bind(footer);
    statusBar.getChildren().add(statusText);

    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(" +
        "from 0% 0% to 100% 100%, #7080A7 55%, #F0FFFF);" + 
        "-fx-border-color: #e6e6d3;");

    statusText.setFont(Font.font("Courier New", FontWeight.BOLD, 14));
    statusText.setFill(Color.web("#F0FFFF"));

    return statusBar;
  }
```

From above codes, we bind the `text` property of a `Text` to `footer` property. In the following section we will show you when the value of `footer` is set.

### 8.1.3 Create Menu Bar

A `MenuBar` is created and placed at the top of `BorderPane`. At this moment, the menu bar contains only one menu, `Tools`, which consists of menu items, each is type of `RadioMenuItem`, for selecting a draw tool, one at a time, to draw shapes on a drawing board.

`RadioMenuItem` extends `MenuItem`, its purpose is providing mutually exclusive choices. A `ToggleGroup` need be created, and all of radio menu items in `Tools` menu are placed in the same toggle group. A listener is added to observe selection changed for the toggle group. The text of the selected menu item is set as footer and is instantly displayed on a status bar. Here are codes to do these:

Import Statements:

```
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
```

Listing 8-3. Create `ToggleGroup`, add listener to observe selection changed:

```
 @Override
  public void start(Stage stage) {

    ...

    // Add menu bar on top of BorderPane
    MenuBar menuBar = createMenuBar();
    rootPane.setTop(menuBar); 

    ...

  }

  /***
   * Create menu bar
   ***/
  MenuBar createMenuBar() {
    MenuBar menuBar = new MenuBar();
    Menu menuTools = createMenuTools();
    menuBar.getMenus().add(menuTools);

    return menuBar;
  }

  /***
   * Create menu tools
   ***/
  Menu createMenuTools() {
    // Create toggle group
    ToggleGroup groupTools = new ToggleGroup();

    // Add listener for toggle group   
    groupTools.selectedToggleProperty().addListener(new ChangeListener<Toggle>() {
      @Override
      public void changed(ObservableValue<? extends Toggle> ov,
                      Toggle oldVal, Toggle newVal) {
        if (newVal != null) {
          RadioMenuItem mi = (RadioMenuItem) newVal;
          footer.set(String.format("%s is selected", mi.getText()));
        }
      }
    });   

    // Create radio menu items
    RadioMenuItem drawLine = new RadioMenuItem("Line Drawer");
    drawLine.setToggleGroup(groupTools);

    ...

  } 
```

### 8.1.4 Set Accelerator for Menu Items

The `accelerator` property defined in `MenuItem` class specifies a `KeyCombination` to trigger an `ActionEvent` of a `MenuItem`. Here's the snippet of codes to set `accelerator` for a `RadioMenuItem`, a direct subclass of `MenuItem`.

Import Statements:

```
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.input.KeyCharacterCombination;
import javafx.scene.input.KeyCombination;
```

Listing 8-4. Set accelerator for `RadioMenuItem`, create an `EventHandler` to handle `ActionEvent` of `RadioMenuItem`, and call `setOnAction` method to register the event handler:

```
 // This event handler is for ActionEvent,
    // it is called from accelerator of MenuItem
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
    drawLine.setAccelerator(
        new KeyCharacterCombination("L", KeyCombination.CONTROL_DOWN));
    drawLine.setOnAction(toolSelector);
```

### 8.1.5 Define Enumeration Type `DrawTools`

We define an enumeration type, `DrawTools`, to specify constants to represent currently available shape drawers. They are: `LineDrawer`, `PolylineDrawer`, `PolygonDrawer`, `PathDrawer`, `BezierCurveDrawer`, `RectangleDrawer`, `CircleDrawer`, `EllipseDrawer`, and `ShapeMover`. Refer to previous chapter for detailed descriptions of each of these predefined shape drawers.

Here are codes to define `enum` type `DrawTools`:

Listing 8-5. Define `enum` type `DrawTools`:

```
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
    NO_TOOL
} 
```

Values in `enum DrawTools` are used as `id`s of radio menu items; see the following snippet of codes:

Listing 8-6. Set `id` for `RadioMenuItem`:

```
 // Create radio menu items
    RadioMenuItem drawLine = new RadioMenuItem("Line Drawer");
    drawLine.setId(DrawTools.LINE_DRAWER.name());
```

### 8.1.6 Complete Source Codes of Skeleton of `JFXDrawTools` Class

Here are complete sources codes of skeleton of `JFXDrawTools`.

Listing 8-7. Create skeleton of `JFXDrawTools`:

```
package jfxdrawtools;

import javafx.application.Application;
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Insets;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.image.Image;
import javafx.scene.input.KeyCharacterCombination;
import javafx.scene.input.KeyCombination;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.HBox;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.Text;
import javafx.stage.Stage;

import drawtool.*;

/**
 * File Name: JFXDrawTools.java
 * (in directory: JFXDrawTools1.0/src/example1/jfxdrawtools/)
 * This application draws a variety of shapes dynamically on a drawing board.
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
    NO_TOOL
} 

public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane;

  // Specify text to be shown on status bar at bottom of border pane 
  StringProperty footer = new SimpleStringProperty();

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    drawPane = new DrawPane();
    rootPane.setCenter(drawPane);

    // Add menu bar on top of BorderPane
    MenuBar menuBar = createMenuBar();
    rootPane.setTop(menuBar);   

    // Add status bar to show footer
    HBox statusBar = createStatusBar();
    rootPane.setBottom(statusBar);

    rootPane.setStyle("-fx-background-color: transparent;");
    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("JFXDrawTools V1.0 Shufen Source Code");

    // set application's closed icon
    String iconName = "/resource/swan16.jpg";
    Image iconImage = new Image(getClass().getResourceAsStream(
        iconName));
    stage.getIcons().add(iconImage);

    stage.show();
  }

  /***
   * Create menu bar
   ***/
  MenuBar createMenuBar() {
    MenuBar menuBar = new MenuBar();
    Menu menuTools = createMenuTools();
    menuBar.getMenus().add(menuTools);

    return menuBar;
  }

  /***
   * Create menu tools
   ***/
  Menu createMenuTools() {
    // Create toggle group
    ToggleGroup groupTools = new ToggleGroup();

    // This event handler is for ActionEvent,
    // it is called from accelerator of MenuItem
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
          footer.set(String.format("%s is selected", mi.getText()));
        }
      }
    });   

    // Create Tools menu
    Menu menuTools = new Menu("Tools");
    menuTools.getItems().addAll(
        drawLine, drawPolyline, drawPolygon, drawPath, drawBezierCurve,
        drawRectangle, drawCircle, drawEllipse,
        moveShape);

    return menuTools;
  }

  /***
   * Create status bar
   ***/
  HBox createStatusBar() {
    HBox statusBar = new HBox();
    Text statusText = new Text("");
    // binding text and footer
    statusText.textProperty().bind(footer);
    statusBar.getChildren().add(statusText);

    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(" +
        "from 0% 0% to 100% 100%, #7080A7 55%, #F0FFFF);" + 
        "-fx-border-color: #e6e6d3;");

    statusText.setFont(Font.font("Courier New", FontWeight.BOLD, 14));
    statusText.setFill(Color.web("#F0FFFF"));

    return statusBar;
  }

  public static void main(String[] args) {
    launch(args);
  }

}
```

Figure 8-2. Snapshot of initial appearance of `JFXDrawTools` application.

![](images/00040.jpeg "skeleton1.jpg")

Figure 8-3. Snapshot of `Tools` menu when mouse clicked on it.

![](images/00041.jpeg "skeleton2.jpg")

Figure 8-4. Snapshot of `Tools` menu when `Line Drawer` radio menu item is selected.

![](images/00042.jpeg "skeleton3.jpg")

Figure 8-5. Snapshot of `Tools` menu when `Bezier Curve Drawer` radio menu item is selected.

![](images/00043.jpeg "skeleton4.jpg")

Compile and run the application. Try these steps to test it:

1.  Click on `Tools` menu to show the menu.
2.  Click on `Line Drawer` menu item to select Line Drawer.
3.  Click on the others menu items.
4.  Press key combinations `Control-B` to select `Bezier Curve Drawer`.
5.  Try the others key combinations: `Control-L`, `Control-P`, `Control-G`, `Control-T`, `Control-R`, `Control-C`, `Control-E`, and `Control-M`. The selected menu item's text is shown on footer.

Output from Compiling and Running `JFXDrawTools` Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac  -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac  -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\JFXDrawTools1.0\src\example1>

copy /Y "..\..\..\DrawTool1.1\src\example1\drawtool.jar".

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar jfxdrawtools\*.java

jar cf jfxdrawtools.jar jfxdrawtools resource

java -cp drawtool.jar;JFXDrawTools.jar jfxdrawtools.JFXDrawTools
```

## 8.2 Create Instances of Shape Drawers

In last chapter, we have implemented a variety of `ShapeDrawer`. Now we'll create an instance for each of them. Here's the snippet of codes:

Import Statements:

```
import drawtool.drawer.*;
```

Listing 8-8. Create instances of drawers:

```
 LineDrawer lineDrawer = new LineDrawer();
  PolylineDrawer polylineDrawer = new PolylineDrawer();
  PolygonDrawer polygonDrawer = new PolygonDrawer();
  PathDrawer pathDrawer = new PathDrawer();
  BezierCurveDrawer bezierCurveDrawer = new BezierCurveDrawer();
  RectangleDrawer rectangleDrawer = new RectangleDrawer();
  CircleDrawer circleDrawer = new CircleDrawer();
  EllipseDrawer ellipseDrawer = new EllipseDrawer();
  ShapeMover shapeMover = new ShapeMover();
```

### 8.2.1 Activate Drawer for a Draw Pane

We create drawers required by the application all at once, however only one drawer can be active on a drawing board at one time. An application can instantiate as many drawers as needed, and switch active status among them. To activate a drawer, we call the `setDrawer(ShapeDrawer` shapeDrawer`)` method, to set the value of `drawer` property which is defined in `DrawPane` class. An `activateDrawer(DrawTools` value`)` method is defined to do this:

Listing 8-9. Define `activateDrawer` method, call `setDrawer` method to activate a drawer:

```
 void activateDrawer(DrawTools value) {
    switch (value) {
      case LINE_DRAWER:
        drawPane.setDrawer(lineDrawer);
        break;
      case POLYLINE_DRAWER:
        drawPane.setDrawer(polylineDrawer);
        break;
      case POLYGON_DRAWER:
        drawPane.setDrawer(polygonDrawer);
        break;
      case PATH_DRAWER:
        drawPane.setDrawer(pathDrawer);
        break;
      case BEZIER_CURVE_DRAWER:
        drawPane.setDrawer(bezierCurveDrawer);
        break;
      case RECTANGLE_DRAWER:
        drawPane.setDrawer(rectangleDrawer);
        break;
      case CIRCLE_DRAWER:
        drawPane.setDrawer(circleDrawer);
        break;
      case ELLIPSE_DRAWER:
        drawPane.setDrawer(ellipseDrawer);
        break;
      case SHAPE_MOVER:
        drawPane.setDrawer(shapeMover);
        break;
      default:
    }
  }
```

The `void activateDrawer(DrawTools` value`)` method is called from `changed` method of a listener registered for the `selectedToggle` property of a toggle group. Here's the snippet of codes:

Listing 8-10. Call `activateDrawer` method from `changed` method of listener registered for `selectedToggle` property:

```
 // Add listener for toggle group   
    groupTools.selectedToggleProperty().addListener(new ChangeListener() {
      @Override
      public void changed(ObservableValue<? extends Toggle> ov,
                      Toggle oldVal, Toggle newVal) {
        if (newVal != null) {
          RadioMenuItem mi = (RadioMenuItem) newVal;
          footer.set(String.format("%s is selected", mi.getText()));
          activateDrawer(Enum.valueOf(DrawTools.class, mi.getId()));
        }
      }
    }); 
```

## 8.3 Complete Source Codes of `JFXDrawTools` Class

Complete source codes of `JFXDrawTools` class become these:

Listing 8-11. Complete source codes of `JFXDrawTools` class:

```
package jfxdrawtools;

import javafx.application.Application;
import javafx.beans.property.SimpleStringProperty;
import javafx.beans.property.StringProperty;
import javafx.beans.value.ChangeListener;
import javafx.beans.value.ObservableValue;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.geometry.Insets;
import javafx.scene.control.Menu;
import javafx.scene.control.MenuBar;
import javafx.scene.control.MenuItem;
import javafx.scene.control.RadioMenuItem;
import javafx.scene.control.Toggle;
import javafx.scene.control.ToggleGroup;
import javafx.scene.image.Image;
import javafx.scene.input.KeyCharacterCombination;
import javafx.scene.input.KeyCombination;
import javafx.scene.layout.BorderPane;
import javafx.scene.layout.HBox;
import javafx.scene.paint.Color;
import javafx.scene.Scene;
import javafx.scene.text.Font;
import javafx.scene.text.FontWeight;
import javafx.scene.text.Text;
import javafx.stage.Stage;

import drawtool.*;
import drawtool.drawer.*;

/**
 * File Name: JFXDrawTools.java
 * (in directory: JFXDrawTools1.0/src/example2/jfxdrawtools/)
 * This application draws a variety of shapes dynamically on a drawing board.
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
    NO_TOOL
} 

public class JFXDrawTools extends Application {
  // The drawing board to draw/move shapes dynamically 
  DrawPane drawPane;

  // Specify text to be shown on status bar at bottom of border pane 
  StringProperty footer = new SimpleStringProperty();

  // Create drawers
  LineDrawer lineDrawer = new LineDrawer();
  PolylineDrawer polylineDrawer = new PolylineDrawer();
  PolygonDrawer polygonDrawer = new PolygonDrawer();
  PathDrawer pathDrawer = new PathDrawer();
  BezierCurveDrawer bezierCurveDrawer = new BezierCurveDrawer();
  RectangleDrawer rectangleDrawer = new RectangleDrawer();
  CircleDrawer circleDrawer = new CircleDrawer();
  EllipseDrawer ellipseDrawer = new EllipseDrawer();
  ShapeMover shapeMover = new ShapeMover();

  @Override
  public void start(Stage stage) {
    BorderPane rootPane = new BorderPane();
    drawPane = new DrawPane();
    rootPane.setCenter(drawPane);

    // Add menu bar on top of BorderPane
    MenuBar menuBar = createMenuBar();
    rootPane.setTop(menuBar);   

    // Add status bar to show footer
    HBox statusBar = createStatusBar();
    rootPane.setBottom(statusBar);

    rootPane.setStyle("-fx-background-color: transparent;");
    Scene scene = new Scene(rootPane, 600, 400, Color.FLORALWHITE);

    stage.setScene(scene);
    stage.setTitle("JFXDrawTools V1.0 Shufen Source Code");

    // set application's closed icon
    String iconName = "/resource/swan16.jpg";
    Image iconImage = new Image(getClass().getResourceAsStream(
        iconName));
    stage.getIcons().add(iconImage);

    stage.show();
  }

  /***
   * Create menu bar
   ***/
  MenuBar createMenuBar() {
    MenuBar menuBar = new MenuBar();
    Menu menuTools = createMenuTools();
    menuBar.getMenus().add(menuTools);

    return menuBar;
  }

  /***
   * Create menu tools
   ***/
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
        //System.out.format("in action: %s is selected%n", mi.getId());
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
          footer.set(String.format("%s is selected", mi.getText()));
          activateDrawer(Enum.valueOf(DrawTools.class, mi.getId()));
        }
      }
    });   

    // Create Tools menu
    Menu menuTools = new Menu("Tools");
    menuTools.getItems().addAll(
        drawLine, drawPolyline, drawPolygon, drawPath, drawBezierCurve,
        drawRectangle, drawCircle, drawEllipse,
        moveShape);

    return menuTools;
  }

  /***
   * Create status bar
   ***/
  HBox createStatusBar() {
    HBox statusBar = new HBox();
    Text statusText = new Text("");
    // binding text and footer
    statusText.textProperty().bind(footer);
    statusBar.getChildren().add(statusText);

    statusBar.setPadding(new Insets(4, 12, 4, 12));
    statusBar.setSpacing(4);
    statusBar.setStyle(
        "-fx-background-color: linear-gradient(" +
        "from 0% 0% to 100% 100%, #7080A7 55%, #F0FFFF);" + 
        "-fx-border-color: #e6e6d3;");

    statusText.setFont(Font.font("Courier New", FontWeight.BOLD, 14));
    statusText.setFill(Color.web("#F0FFFF"));

    return statusBar;
  }

  /***
   * Activate a drawer of a draw pane,
   * this method is called from changed method of listener registered
   * for selectedToggle property
   ***/
  void activateDrawer(DrawTools value) {
    switch (value) {
      case LINE_DRAWER:
        drawPane.setDrawer(lineDrawer);
        break;
      case POLYLINE_DRAWER:
        drawPane.setDrawer(polylineDrawer);
        break;
      case POLYGON_DRAWER:
        drawPane.setDrawer(polygonDrawer);
        break;
      case PATH_DRAWER:
        drawPane.setDrawer(pathDrawer);
        break;
      case BEZIER_CURVE_DRAWER:
        drawPane.setDrawer(bezierCurveDrawer);
        break;
      case RECTANGLE_DRAWER:
        drawPane.setDrawer(rectangleDrawer);
        break;
      case CIRCLE_DRAWER:
        drawPane.setDrawer(circleDrawer);
        break;
      case ELLIPSE_DRAWER:
        drawPane.setDrawer(ellipseDrawer);
        break;
      case SHAPE_MOVER:
        drawPane.setDrawer(shapeMover);
        break;
      default:
    }
  }

  public static void main(String[] args) {
    launch(args);
  }

}
```

Figure 8-6. Snapshot of testing all drawers one by one with similar strokes.

![](images/00044.jpeg "draw_sketches.jpg")

Figure 8-7. Snapshot of drawing a variety of icons using the initial version of `JFXDrawTools` application.

![](images/00045.jpeg "draw_icons.jpg")

Compile and run the application. Try these steps to test it:

1.  Click on `Tools` menu, select `Line Drawer` menu item.
2.  Move mouse to drawing board, drag mouse around to draw a few lines.
3.  Click on the other menu items one by one, do the same dragging to see different rendering of each shape.
4.  Test all accelerators one by one to select a drawer.
5.  Select `Shape Drawer` menu item, try move some shapes around drawing board.

Output from Compiling and Running `JFXDrawTools` Program in Command Line:

```
Microsoft Windows [Version 6.3.9600]
(c) 2013 Microsoft Corporation. All rights reserved.

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\DrawTool1.1\src\example1>
javac  -encoding utf-8 -Xlint:unchecked drawtool\*.java

javac  -encoding utf-8 -Xlint:unchecked -cp . drawtool\drawer\*.java

jar cf drawtool.jar drawtool

F:\My Documents\DocRoot\SHUFEN_JAVA\MyBookJFX\VolumeTwo\JFXDrawTools1.0\src\example2>

copy /Y "..\..\..\DrawTool1.1\src\example1\drawtool.jar".

javac -encoding utf-8 -Xlint:unchecked -cp drawtool.jar jfxdrawtools\*.java

jar cf jfxdrawtools.jar jfxdrawtools resource

java -cp drawtool.jar;JFXDrawTools.jar jfxdrawtools.JFXDrawTools
```

## 8.4 Summary

This chapter features the following key aspects of JavaFX library, listing in the order of their appearance in this article:

*   Two of Classes from `javafx.beans.property` package:

    `StringProperty`

    Is an abstract class, derived from `javafx.beans.binding.StringExpression` class, implements `Property<java.lang.String>` and `WritableStringValue`.
    `WritableStringValue` extends `WritableObjectValue<java.lang.String>`.

    `SimpleStringProperty`

    Derived from `StringProperty` class.

    (See section: [Create Status Bar](#part0014_split_001.html_create-status-bar))
*   `HBox` class, one of built-in JavaFX layout panes﹐resides in `javafx.scene.layout` package, is a direct subclass of `javafx.scene.layout.Pane`, placing its children in one row horizontally.
    (See section: [Create Status Bar](#part0014_split_001.html_create-status-bar))
*   `Text` class, resides in `javafx.scene.text` package, is one of direct subclasses of `javafx.scene.shape.Shape` class which takes care of common needs for rendering geometric primitives.
    (See section: [Create Status Bar](#part0014_split_001.html_create-status-bar))
*   `void setPadding(Insets` value`)` method, provided in `Region` class, defines the top, right, bottom, left padding for the region.
    (See [here](#part0014_split_001.html_status-bar-set-properties))
*   `void setSpacing(double` value`)` method, provided in `HBox` class, specifies the horizontal space between children in the HBox pane.
    (See [here](#part0014_split_001.html_status-bar-set-properties))
*   `void setStyle(String` value`)` method, provided in `Node` class, specifies CSS style for this node.
    (See [here](#part0014_split_001.html_status-bar-set-properties))
*   `static Font font(java.lang.String` family`, FontWeight` weight`, double` size`)` method is provided in `javafx.scene.text.Font` class, for obtaining a font to render text.
    (See [here](#part0014_split_001.html_status-bar-set-properties))
*   `void bind(ObservableValue<? extends T>` observable`)` method defined in `Property` interface, resides in `javafx.beans.property` package, to bind this property unidirectional to the given `ObservableValue`.
    (See [here](#part0014_split_001.html_bind-text-footer))
*   `MenuBar`, `Menu`, and `MenuItem` are among fundamental JavaFX UI components, reside in `javafx.scene.control` package, for designing compact look-and-feel graphical user interfaces using less space.
    (See section [Create Menu Bar](#part0014_split_001.html_create-menu-bar))
*   `RadioMenuItem` and `ToggleGroup`, reside in `javafx.scene.control` package, for creating mutually exclusive choices among a menu.
    (See section [Create Menu Bar](#part0014_split_001.html_create-menu-bar))
*   `void addListener(ChangeListener<? super T>` listener`)` method, defined in `javafx.beans.value.ObservableValue` interface, adds a `ChangeListener` by providing `changed(ObservableValue<? extends T>` observable`, T` oldValue`, T` newValue`)` method, to be invoked when this property's value is changed.
    (See [here](#part0014_split_001.html_toggle-add-listener-codes))
*   `EventHandler<T extends Event>`, an interface which extends `java.util.EventListener`, defines a `handle`(`T` event) method to be invoked when the specified event happens.
    (See section [Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator))
*   `void setOnAction(EventHandler<ActionEvent>` value`)` method, provided in `MenuItem` class, registers an `EventHandler` to be notified when `ActionEvent` occurs.
    (See section [Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator), and [here](#part0014_split_001.html_key-character-combination-codes))
*   `accelerator` property, defined in `MenuItem` class, specifies a `KeyCombination` to trigger an `ActionEvent` of a `MenuItem`.
    (See section [Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator), and [here](#part0014_split_001.html_key-character-combination-codes))
*   `KeyCombination`, an abstract class resides in j`avafx.scene.input package`, defines static fields of type `KeyCombination.Modifier`, such as CONTROL_DOWN, META_DOWN, SHIFT_DOWN, etc. which are useful in construction of `KeyCharacterCombination` instances.
    (See section [Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator), and [here](#part0014_split_001.html_key-character-combination-codes))
*   `KeyCharacterCombination`, resides in j`avafx.scene.input package`, a direct subclass of `javafx.scene.input.KeyCombination` for creating shortcuts to trigger an `ActionEvent`.
    (See section [Set Accelerator for Menu Items](#part0014_split_001.html_set-accelerator), and [here](#part0014_split_001.html_key-character-combination-codes))

#   EPILOGUE

The authors are working on the rest of volumes of this book series, to be released one by one soon. Let's have a sneak peek of coming features besides others revealed in the PREFACE section:

*   More interactive sketching tools: Free Hand Drawer, Rubber Band Drawer, Text Writer, Color Gradienter, Arc Drawer, Cursor Key Mover, etc.
*   Color palette tools
*   Image clipping tools
*   Path transition animater
*   Dynamic context menu controller
*   And more...

Wish you a happy, healthy, and prosperous year of the Monkey.