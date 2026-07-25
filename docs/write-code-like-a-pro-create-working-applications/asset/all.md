![](images/cover.jpg)

# **INTRODUCTION**

So you want to make your very own videogame? And you want to learn how to code in Java? That is an awesome idea!

Writing Java code can be really hard work, especially writing Java code to make a videogame. For example, the original Legend of Zelda took more than 100 people three years to make! But don’t worry, this book will guide your through all the steps to learn the basics of Java programming and to make two videogames of your own. The first game you’ll make is kind of like Mario, where you have a character that runs across the screen and tries to avoid lava pits and enemies. The second, larger game that you’ll code is kind of like Flappy Bird. It’s called Ninja Bird. Keeping track of scores, making pipes move on their own randomly, and even helping the bird fly — you’ll have your friends playing games you make for hours!

## ABOUT THIS BOOK

This book uses a computer application called Processing that was made to make coding Java video games much easier. As you’ll see, you can easily make drawings with different shapes and colors, you can add images that you find online (with adult permission, of course!) into your drawing and games, and it comes with an entire library of code that you get to just *use.* It’s free, and available online. In the first chapter, you’ll learn how to download it and begin using it in just a couple of simple steps.

*Write Code Like a Pro* has three different types of programs that you’ll write. First, you’ll make a simple drawing using a lot of what Processing provides to you in its library. With shapes and colors, the first couple chapters of this book guide you through an art program. The next part of this book teaches you how to turn that drawing into an animation — making shapes and images move around the canvas. Finally, you’ll get a chance to build two different videogames.

Though this book will guide you step-by-step in making these games, you’re highly encouraged to keep coding *after* you finish this book and make variations of the games you learn here! This is just the beginning of your coding and videogame development career. With this book as a starting point, you never know what you can achieve!

## FOOLISH ASSUMPTIONS

Everybody has to start somewhere, right? I had to start writing this book by assuming that you’re comfortable doing this stuff:

*   **Typing on a computer and using a mouse:** You may know how to use a Windows system or a Mac; either one will do. This book shows examples on a Mac.
*   **Following instructions:** Coding is very precise. There are a lot of pieces to the puzzle when you’re making an application. It’s very important that you already know how to follow instructions carefully, and compare pictures in the book to what you’re making on your own.

## ICONS USED IN THIS BOOK

As you read through the projects in this book, you’ll see icons. The icons point out different things:

![remember](images/remember.png) The Remember icon highlights ideas that you should keep in mind.

![tip](images/tip.png) The Tip icon marks advice and shortcuts that can make coding easier.

## WHERE TO GO FROM HERE

In this book, it’s best if you start from [Chapter 1](#04_9781119404170-ch01.xhtml) and move through to [Chapter 12](#15_9781119404170-ch12.xhtml). There are some things you learn in early chapters that really help you complete the larger problems in later chapters. The chapters in this book do fall under three categories: [Chapters 1](#04_9781119404170-ch01.xhtml) through [6](#09_9781119404170-ch06.xhtml) guide you through the basics of coding in Java with a drawing canvas; you’ll get to learn how to make shapes, add color, make objects move, and even have user interaction — all very important for coding a videogame. [Chapters 7](#10_9781119404170-ch07.xhtml) through [8](#11_9781119404170-ch08.xhtml) guide you through making your very first videogame! This game is similar to Mario, but just a preview to videogame making. Finally, [Chapters 9](#12_9781119404170-ch09.xhtml) through [12](#15_9781119404170-ch12.xhtml) guide you through making Ninja Bird, which is a game like Flappy Bird.

![image](images/c1.png)

So, you want to learn how to code in Java. That’s a great goal! In this book, you’ll learn the basics of Java while learning how to make a videogame! Coding can be tricky. Sometimes it’s frustrating. Remember to keep trying, test your code, and double-check that you’ve typed everything correctly. With dedication, you’ll learn a lot and have fun doing it!

In this chapter, you’ll install the Processing application, which will allow you to write Java code. Then you’ll get a chance to test out some real Java code and make sure you understand how the application will work throughout the rest of the book.

## GETTING STARTED WITH PROCESSING

To get started with Java, you’ll be using a programming environment called Processing. Processing comes with a library of code that you can use to make objects move around the screen and create a fun gaming experience for your players! That makes writing your first videogame faster and easier.

### DOWNLOADING AND INSTALLING PROCESSING

To get started with Processing, you need to download and install the application on your computer.

Follow these steps to download and install Processing:

1.  **Go to** [`www.processing.org`](http://www.processing.org) **(shown in** [**Figure 1-1**](#04_9781119404170-ch01.xhtml_c01-fig-0001)**) and click the Download Processing button.**
2.  **Find the operating system that you’re using in the list of downloads (see** [**Figure 1-2**](#04_9781119404170-ch01.xhtml_c01-fig-0002)**), and choose the correct version.**

    If you aren’t sure which operating system you’re using, ask an adult.

    A file begins downloading to your computer.

3.  **After the file downloads, unzip the file by double-clicking it.**

    The Processing application should be created.

![image](images/9781119404170-fg0101.png)

[FIGURE 1-1:](#04_9781119404170-ch01.xhtml_rc01-fig-0001) The Processing website.

![image](images/9781119404170-fg0102.png)

[FIGURE 1-2:](#04_9781119404170-ch01.xhtml_rc01-fig-0002) Options for downloading Processing.

![image](images/9781119404170-fg0103.png)

[FIGURE 1-3:](#04_9781119404170-ch01.xhtml_rc01-fig-0003) Optional contribution to the Processing application development.

After you have unzipped the Processing application, you can move it to your Desktop if you want by dragging the file from the Downloads folder to the Desktop folder.

### STARTING TO USE PROCESSING

Now that you have Processing installed on your computer, you can start using it! Follow these steps:

1.  **Double-click the Processing file that you extracted.**
2.  **The first time you open Processing, you might get an alert that asks if you’re sure you want to open the file (see** [**Figure 1-4**](#04_9781119404170-ch01.xhtml_c01-fig-0004)**). Click Open.**

    You see a welcome screen (see [Figure 1-5](#04_9781119404170-ch01.xhtml_c01-fig-0005)).

3.  **Uncheck the Show This Welcome Message Each Time box and then click the Get Started button.**

    A new Sketch opens. A Sketch is what Processing calls a new program file. You’ll notice that the Sketch has Java as the programming language set in the upper right of the screen (see [Figure 1-6](#04_9781119404170-ch01.xhtml_c01-fig-0006)).

![image](images/9781119404170-fg0104.png)

[FIGURE 1-4:](#04_9781119404170-ch01.xhtml_rc01-fig-0004) A warning you might see when opening Processing the first time.

![image](images/9781119404170-fg0105.png)

[FIGURE 1-5:](#04_9781119404170-ch01.xhtml_rc01-fig-0005) A welcome popup you see when opening Processing.

![image](images/9781119404170-fg0106.png)

[FIGURE 1-6:](#04_9781119404170-ch01.xhtml_rc01-fig-0006) The Processing window with a new Sketch opened.

Now that you have Processing open, you can test out some code to make sure everything is working!

### TRYING SOME CODE

In this book, you’re going to be learning how to write your own code from scratch, but when you first set up a programming environment, it’s a good idea to test some code that you know *should* work to make sure your programming environment is working. Follow these steps:

1.  **Go to** [`www.processing.org/examples/star.html`](http://www.processing.org/examples/star.html) **(see** [**Figure 1-7**](#04_9781119404170-ch01.xhtml_c01-fig-0007)**).**
2.  **Scroll down to the code that creates these stars, shown in** [**Figure 1-8**](#04_9781119404170-ch01.xhtml_c01-fig-0008)**.**
3.  **Highlight all the code. Then right-click the code and choose Copy from the pop-up menu that appears (see** [**Figure 1-9**](#04_9781119404170-ch01.xhtml_c01-fig-0009)**).**

    You can also highlight the code and then press Command+C if you’re on a Mac or Ctrl+C if you’re on a Windows computer.

4.  **Click the Processing application again, right-click in the Sketch window, and choose Paste from the pop-up menu that appears (see** [**Figure 1-10**](#04_9781119404170-ch01.xhtml_c01-fig-0010)**).**

    You can also click in the Sketch window and press Command+V if you’re on a Mac or Ctrl+V if you’re on a Windows computer.

5.  **Click the Run button in the upper left of the Processing window (see** [**Figure 1-11**](#04_9781119404170-ch01.xhtml_c01-fig-0011)**).**
6.  **Watch the three different stars spin (see** [**Figure 1-12**](#04_9781119404170-ch01.xhtml_c01-fig-0012)**)!**

![image](images/9781119404170-fg0107.png)

[FIGURE 1-7:](#04_9781119404170-ch01.xhtml_rc01-fig-0007) The Star program example on the Processing website.

![image](images/9781119404170-fg0108.png)

[FIGURE 1-8:](#04_9781119404170-ch01.xhtml_rc01-fig-0008) The Star program code that you’ll copy.

![image](images/9781119404170-fg0109.png)

[FIGURE 1-9:](#04_9781119404170-ch01.xhtml_rc01-fig-0009) Copy the Star program code by highlighting and right-clicking.

![image](images/9781119404170-fg0110.png)

[FIGURE 1-10:](#04_9781119404170-ch01.xhtml_rc01-fig-0010) Paste the Star program code by right-clicking in the Sketch.

![image](images/9781119404170-fg0111.png)

[FIGURE 1-11:](#04_9781119404170-ch01.xhtml_rc01-fig-0011) Test the Star program by clicking the Run button.

![image](images/9781119404170-fg0112.png)

[FIGURE 1-12:](#04_9781119404170-ch01.xhtml_rc01-fig-0012) The canvas with stars spinning.

Congratulations! You’ve tested your first Java program! Don’t worry if the code doesn’t make sense yet. Throughout this book, you’ll learn a lot of Java and have a chance to understand how everything works.

## SAVE AND REOPEN PROCESSING PROGRAMS

Before I wrap up this chapter, you need to know how to save your work and then access it again after you’ve closed the Processing application. Follow these steps:

1.  **Save your code by choosing File ⇒Save (see** [**Figure 1-13**](#04_9781119404170-ch01.xhtml_c01-fig-0013)**).**
2.  **Rename your file “StarProgram” and click Save (see** [**Figure 1-14**](#04_9781119404170-ch01.xhtml_c01-fig-0014)**).**
3.  **Close the Processing application by choosing Processing⇒Quit Processing (see** [**Figure 1-15**](#04_9781119404170-ch01.xhtml_c01-fig-0015)**).**
4.  **If you want to open this file again, just open the Processing application and choose File ⇒Open (see** [**Figure 1-16**](#04_9781119404170-ch01.xhtml_c01-fig-0016)**).**

    Processing shows the programs that were saved to the Processing folder, which is where you saved your program in Step 2.

5.  **Choose the StarProgram folder and click Open (see** [**Figure 1-17**](#04_9781119404170-ch01.xhtml_c01-fig-0017)**).**
6.  **Select the StarProgram.dpe file and click Open (see** [**Figure 1-18**](#04_9781119404170-ch01.xhtml_c01-fig-0018)**).**

    The code that you saved in Step 1 will open (see [Figure 1-19](#04_9781119404170-ch01.xhtml_c01-fig-0019)).

7.  **If you want to start a new program, choose File ⇒New (see** [**Figure 1-20**](#04_9781119404170-ch01.xhtml_c01-fig-0020)**).**

    A new Processing window opens (see [Figure 1-21](#04_9781119404170-ch01.xhtml_c01-fig-0021)), and you can write new code!

![image](images/9781119404170-fg0113.png)

[FIGURE 1-13:](#04_9781119404170-ch01.xhtml_rc01-fig-0013) Save your Star program from the File menu.

![image](images/9781119404170-fg0114.png)

[FIGURE 1-14:](#04_9781119404170-ch01.xhtml_rc01-fig-0014) Rename the program.

![image](images/9781119404170-fg0115.png)

[FIGURE 1-15:](#04_9781119404170-ch01.xhtml_rc01-fig-0015) Quit Processing from the Processing menu.

![image](images/9781119404170-fg0116.png)

[FIGURE 1-16:](#04_9781119404170-ch01.xhtml_rc01-fig-0016) Open a saved program from the File menu.

![image](images/9781119404170-fg0117.png)

[FIGURE 1-17:](#04_9781119404170-ch01.xhtml_rc01-fig-0017) Find saved programs inside the folders with the same name.

![image](images/9781119404170-fg0118.png)

[FIGURE 1-18:](#04_9781119404170-ch01.xhtml_rc01-fig-0018) Open the StarProgram.dpe file to see the code.

![image](images/9781119404170-fg0119.png)

[FIGURE 1-19:](#04_9781119404170-ch01.xhtml_rc01-fig-0019) The Star program code reopened in Processing.

![image](images/9781119404170-fg0120.png)

[FIGURE 1-20:](#04_9781119404170-ch01.xhtml_rc01-fig-0020) Create a new program from the File menu.

![image](images/9781119404170-fg0121.png)

[FIGURE 1-21:](#04_9781119404170-ch01.xhtml_rc01-fig-0021) A blank Sketch file.

![image](images/c2.png)

In this chapter, you’ll learn about two very important concepts in Java programming: methods and variables. While you’re learning about those, you’ll get to create your own canvas and add color to it!

## GETTING TO KNOW THE CANVAS

As you may have noticed in [Chapter 1](#04_9781119404170-ch01.xhtml), when you run a Processing program, a canvas pops up. The *canvas* is the window that displays the visual part of your program, like the spinning stars in the program you tested.

### CREATING A CANVAS

In this section, you learn a little about the canvas, which will be important to understand how you can interact with it. Follow these steps:

1.  **Open the Processing application and create a new program (see** [**Figure 2-1**](#05_9781119404170-ch02.xhtml_c02-fig-0001)**).**
2.  **Type one line of code to create a canvas that is 500 pixels wide and 500 pixels tall (see** [**Figure 2-2**](#05_9781119404170-ch02.xhtml_c02-fig-0002)**):**

    `size(500, 500);`

3.  **Click the Run button at the upper left of the Processing window, which you can see in** [**Figure 2-2**](#05_9781119404170-ch02.xhtml_c02-fig-0002)**.**

    A canvas should pop up on your screen (see [Figure 2-3](#05_9781119404170-ch02.xhtml_c02-fig-0003)).

4.  **Close the canvas by clicking the red X in the upper left of the screen.**
5.  **Change the code to 500 by 250 pixels, as shown in** [**Figure 2-4**](#05_9781119404170-ch02.xhtml_c02-fig-0004)**:**

    `size(500, 250);`

6.  **Before clicking the Run button, predict whether the canvas will be a horizontal rectangle or a vertical rectangle.**
7.  **Click the Run button and see if your prediction was correct!**

![image](images/9781119404170-fg0201.png)

[FIGURE 2-1:](#05_9781119404170-ch02.xhtml_rc02-fig-0001) A blank Sketch file.

![image](images/9781119404170-fg0202.png)

[FIGURE 2-2:](#05_9781119404170-ch02.xhtml_rc02-fig-0002) The code needed to create a 500-x-500-pixel canvas.

![image](images/9781119404170-fg0203.png)

[FIGURE 2-3:](#05_9781119404170-ch02.xhtml_rc02-fig-0003) The blank 500-x-500-pixel canvas.

![image](images/9781119404170-fg0204.png)

[FIGURE 2-4:](#05_9781119404170-ch02.xhtml_rc02-fig-0004) The code needed to create a 500-x-200-pixel canvas.

Now you know that the following line of code creates a canvas that is Num1 pixels wide and Num2 pixels tall.

`size (Num1, Num2);`

### UNDERSTANDING THE PIXELS IN THE CANVAS

Each canvas that you create is created by a lot of pixels. For example, with the first bit of code that you wrote in the preceding section, you created a canvas that contained 250,000 pixels! There are 500 rows of pixels, and in each row, there are 500 pixels.

Each pixel that is on the canvas has a location and a color. The location of the pixel is specified by the *x* and *y* location of the pixel. You can change the color of individual pixels by using the method set. Follow these steps:

1.  **Make sure your code is creating a canvas that is 500 by 500 pixels, as shown in** [**Figure 2-5**](#05_9781119404170-ch02.xhtml_c02-fig-0005)**:**

    `size(500, 500);`

2.  **Add a second line of code that creates a new color variable (see** [**Figure 2-6**](#05_9781119404170-ch02.xhtml_c02-fig-0006)**):**

    `color black = color(0);`

3.  **Add a third line of code that changes the color of the centermost pixel to the color that you just created in Step 2 (see** [**Figure 2-7**](#05_9781119404170-ch02.xhtml_c02-fig-0007)**):**

    `set(250, 250, black);`

4.  **Click the Run button.**

    Notice that the center pixel is now black (see [Figure 2-8](#05_9781119404170-ch02.xhtml_c02-fig-0008)).

5.  **Try changing the number in Step 2 to be any number between 0 and 255 and click the Run button again to see that center button change to different colors.**

    You can also add more lines like you did in Step 3, to change other pixels in your canvas to other colors. For example, here’s how to make a line that has every other pixel black or white (see [Figure 2-9](#05_9781119404170-ch02.xhtml_c02-fig-0009)):

    `size(500, 500);`
    `color black = color(0);`
    `color white = color(255);`
    `set(240, 250, black);`
    `set(241, 250, white);`
    `set(242, 250, black);`
    `set(243, 250, white);`
    `set(244, 250, black);`
    `set(245, 250, white);`
    `set(246, 250, black);`
    `set(247, 250, white);`
    `set(248, 250, black);`
    `set(249, 250, white);`
    `set(250, 250, black);`
    `set(251, 250, white);`
    `set(252, 250, black);`
    `set(253, 250, white);`
    `set(254, 250, black);`
    `set(255, 250, white);`
    `set(256, 250, black);`
    `set(257, 250, white);`
    `set(258, 250, black);`
    `set(259, 250, white);`

    And here’s how to make a line that has 10 pixels black and then 10 pixels white (see [Figure 2-10](#05_9781119404170-ch02.xhtml_c02-fig-0010)):

    `size(500, 500);`
    `color black = color(0);`
    `color white = color(255);`
    `set(240, 250, black);`
    `set(241, 250, black);`
    `set(242, 250, black);`
    `set(243, 250, black);`
    `set(244, 250, black);`
    `set(245, 250, black);`
    `set(246, 250, black);`
    `set(247, 250, black);`
    `set(248, 250, black);`
    `set(249, 250, black);`
    `set(250, 250, white);`
    `set(251, 250, white);`
    `set(252, 250, white);`
    `set(253, 250, white);`
    `set(254, 250, white);`
    `set(255, 250, white);`
    `set(256, 250, white);`
    `set(257, 250, white);`
    `set(258, 250, white);`
    `set(259, 250, white);`

![image](images/9781119404170-fg0205.png)

[FIGURE 2-5:](#05_9781119404170-ch02.xhtml_rc02-fig-0005) The code needed to create a 500-x-500-pixel canvas.

![image](images/9781119404170-fg0206.png)

[FIGURE 2-6:](#05_9781119404170-ch02.xhtml_rc02-fig-0006) The code needed to create the color black.

![image](images/9781119404170-fg0207.png)

[FIGURE 2-7:](#05_9781119404170-ch02.xhtml_rc02-fig-0007) The code needed to change a particular pixel black.

![image](images/9781119404170-fg0208.png)

[FIGURE 2-8:](#05_9781119404170-ch02.xhtml_rc02-fig-0008) A 500-x-500-pixel canvas with a single black pixel in the center.

![image](images/9781119404170-fg0209.png)

[FIGURE 2-9:](#05_9781119404170-ch02.xhtml_rc02-fig-0009) The code and output of making a black-and-white line of pixels.

![image](images/9781119404170-fg0210.png)

[FIGURE 2-10:](#05_9781119404170-ch02.xhtml_rc02-fig-0010) The code and output of making another black-and-white line.

In [Chapter 4](#07_9781119404170-ch04.xhtml), you’ll learn a lot more about colors, but this is a general introduction to pixels and their attributes: location and color.

![image](images/9781119404170-fg0211.png)

[FIGURE 2-11:](#05_9781119404170-ch02.xhtml_rc02-fig-0011) A guideline of where the pixel locations are.

Congratulations! You’ve now learned a bit about pixels, location, color, and how to call methods in Java! In the next section, you’ll get an overview of the methods you’ve used so far and find out how calling Java methods works.

![image](images/9781119404170-fg0212.png)

[FIGURE 2-12:](#05_9781119404170-ch02.xhtml_rc02-fig-0012) Be sure to name files before saving them.

## CALLING METHODS IN JAVA

You’ve already called quite a few methods in the code that you wrote for this chapter, but it’s important to understand what you’re writing when you’re writing code. In the methods that you’ve called so far, there are two parts: method name and parameters:

`methodName(Parameters);`

After the method name, there is always open and closed parentheses. In all the examples you’ve used so far, there are parameters in the middle of the parentheses, but sometimes there are none. For example, there is a method that you haven’t used yet that doesn’t have any parameters:

`exit();`

You can try to add this line of code to the very last line in your program. When you click Run, you should see the canvas appear and then almost immediately close. That’s because the exit method closes the canvas.

If a method does have parameters, then the parameters need to be in the correct order and they need to be the correct type. For example, the size method requires two parameters that are integers (or numbers); the first number must be the width of the canvas while the second number is the height of the canvas:

`size(width, height);`

You can test out putting fewer or more parameters and changing the type, and you’ll notice that you get an error. For example, say you had the following as your first line

`size("abc");`

You would get an error message explaining that the method size requires two integer parameters (see [Figure 2-13](#05_9781119404170-ch02.xhtml_c02-fig-0013)).

![image](images/9781119404170-fg0213.png)

[FIGURE 2-13:](#05_9781119404170-ch02.xhtml_rc02-fig-0013) An example of an error message you could get in Processing.

Between each parameter, you have to put a comma.

Finally, every method call ends in a semicolon. This tells Processing that you’re done with that line of code.

In [Chapter 2](#05_9781119404170-ch02.xhtml), you’ve already called four different methods:

`size(width, height);`
`color(colorCode);`
`set(x, y, color);`
`exit();`

It’s important that the first method you call is the size method, so that your canvas is created at the right size. After that, you can call the color and set methods as many times as you want! And if you call the exit method last, then everything will happen before the canvas closes.

## CREATING VARIABLES

Variables are basically names that you give to values that you want to reuse over and over. In this chapter, you created two variables: `black` and `white`.

Just like calling a method, when you create a variable there is a format:

`type variableName = value;`

In this chapter, the type that we used was `color`. Some other simple types that you might encounter in this book are

*   `int`: Integer/number
*   `boolean`: True or false
*   `char`: A single character like `a` or `b`
*   `color`: The color of a pixel

The usefulness of variables is that you can name a value, like `color(0)` and then use that value by just using the name. As an example, here is the same code — the first uses a variable and the second doesn’t:

`color black = color(0);`
`set(240, 250, black);`
`set(241, 250, black);`
`set(242, 250, black);`

`set(240, 250, color(0));`
`set(241, 250, color(0));`
`set(242, 250, color(0));`

You can see that not only is it faster to type `black` instead of `color(0)`, but it’s also much clearer to humans to use the word `black` instead of the code `color(0)`.

This would still set the 3 pixels to the color black because you’re using `0` as the parameter when you call the `color` method, but any human reading this code might think that the 3 pixels would be set to purple instead!

In the rest of this book, you’ll revisit methods, parameters, and variables.

![image](images/c3.png)

In [Chapter 2](#05_9781119404170-ch02.xhtml), you learned how to make a black-and-white line. It was a lot of code just to make a line that was 20 pixels long! Imagine if you wanted to make a square that was black and white. You’d have to make 20 lines, which would mean 400 lines of code! That would be crazy — and it would be really easy to make a mistake.

Even though making a square that is 20 pixels wide and 20 pixels tall is basically changing each of those pixels to be a different color, the Processing programming environment has created methods that you can call to create a square instead of having to write all 400 lines of code to change each individual pixel!

The five primitive (or simple) shapes that Processing provides to you are:

`triangle(x1, y1, x2, y2, x3, y3);`
`rect(x, y, width, height);`
`quad(x1, y1, x2, y2, x3, y3, x4, y4);`
`ellipse(x, y, width, height);`
`arc(x, y, width, height, start, stop);`

Even though Processing makes it simpler to create these shapes, it can still be tricky. In this chapter, you’ll create each of the shapes and change the parameters a bit to draw the shapes on different parts of the canvas, and make them different sizes.

## DRAWING A TRIANGLE

In Processing, the `triangle` method will create a triangle that takes six parameters, which are the *x* and *y* locations of each of the points of the triangle. Follow these steps:

1.  **Open the Processing application and create a new program.**
2.  **Create a canvas that is 500 by 500 pixels (see** [**Figure 3-1**](#06_9781119404170-ch03.xhtml_c03-fig-0001)**):**

    `size(500, 500);`

3.  **Create a triangle that has its upper-point right in the center of the canvas (*x* = 250, *y* = 250). The height of the triangle should be 100 pixels and the width of the triangle should be 200 pixels (see** [**Figure 3-2**](#06_9781119404170-ch03.xhtml_c03-fig-0002)**):**

    `triangle(250, 250, 150, 350, 350, 350);`

4.  **Click Run to see the triangle that you created (see** [**Figure 3-4**](#06_9781119404170-ch03.xhtml_c03-fig-0004)**).**
5.  **Try changing the *x* and *y* coordinates for each point to create different triangles.**

    This code makes the triangle shown in [Figure 3-5](#06_9781119404170-ch03.xhtml_c03-fig-0005):

    `triangle(250, 250, 250, 350, 300, 300);`

    This code makes the triangle shown in [Figure 3-6](#06_9781119404170-ch03.xhtml_c03-fig-0006):

    `triangle(250, 250, 150, 450, 350, 450);`

    This code makes the triangle shown in [Figure 3-7](#06_9781119404170-ch03.xhtml_c03-fig-0007):

    `triangle(250, 250, 250, 450, 450, 450);`

6.  **When you’re done exploring different triangle shapes, comment out the line of code that creates the triangle.**

    To do this, add two forward slashes in front of the method name (see [Figure 3-8](#06_9781119404170-ch03.xhtml_c03-fig-0008)):

    `//triangle(250, 250, 250, 450, 450, 450);`

    This will make the Processing application ignore everything written on the same line as the `//`.

![image](images/9781119404170-fg0301.png)

[FIGURE 3-1:](#06_9781119404170-ch03.xhtml_rc03-fig-0001) The code needed to create a 500-x-500-pixel canvas.

![image](images/9781119404170-fg0302.png)

[FIGURE 3-2:](#06_9781119404170-ch03.xhtml_rc03-fig-0002) The code needed to create a triangle.

![image](images/9781119404170-fg0303.png)

[FIGURE 3-3:](#06_9781119404170-ch03.xhtml_rc03-fig-0003) An example of a hand-drawn sketch to help visualize code.

![image](images/9781119404170-fg0304.png)

[FIGURE 3-4:](#06_9781119404170-ch03.xhtml_rc03-fig-0004) The triangle created from the code in [Figure 3-2](#06_9781119404170-ch03.xhtml_c03-fig-0002).

![image](images/9781119404170-fg0305.png)

[FIGURE 3-5:](#06_9781119404170-ch03.xhtml_rc03-fig-0005) An example of a small, sideways triangle.

![image](images/9781119404170-fg0306.png)

[FIGURE 3-6:](#06_9781119404170-ch03.xhtml_rc03-fig-0006) An example of a tall, skinny triangle.

![image](images/9781119404170-fg0307.png)

[FIGURE 3-7:](#06_9781119404170-ch03.xhtml_rc03-fig-0007) An example of a right triangle.

![image](images/9781119404170-fg0308.png)

[FIGURE 3-8:](#06_9781119404170-ch03.xhtml_rc03-fig-0008) Comment out code by putting `//` at the beginning of the line.

## DRAWING A RECTANGLE

In Processing, the `rect` method will create a rectangle that takes four parameters: the upper-left corner *x* and *y* values, the width, and the height. Follow these steps:

1.  **Create a rectangle that has the upper-left corner at *x* = 100 and *y* = 100 and is 50 pixels wide and 50 pixels tall. Click Play to see the square (see** [**Figure 3-9**](#06_9781119404170-ch03.xhtml_c03-fig-0009)**).**

    `rect(100, 100, 50, 50);`

2.  **Try changing the *x* and *y* coordinates and the width and height to create different kinds of rectangles.**

    This code creates the rectangle shown in [Figure 3-10](#06_9781119404170-ch03.xhtml_c03-fig-0010):

    `rect(100, 100, 200, 100);`

    This code creates the rectangle shown in [Figure 3-11](#06_9781119404170-ch03.xhtml_c03-fig-0011):

    `rect(100, 50, 200, 400);`

3.  **When you’re done exploring different rectangle shapes, comment out the line of code that creates the rectangle (see** [**Figure 3-12**](#06_9781119404170-ch03.xhtml_c03-fig-0012)**).**

![image](images/9781119404170-fg0309.png)

[FIGURE 3-9:](#06_9781119404170-ch03.xhtml_rc03-fig-0009) An example of a 50-x-50-pixel square.

![image](images/9781119404170-fg0310.png)

[FIGURE 3-10:](#06_9781119404170-ch03.xhtml_rc03-fig-0010) An example of a horizontal rectangle.

![image](images/9781119404170-fg0311.png)

[FIGURE 3-11:](#06_9781119404170-ch03.xhtml_rc03-fig-0011) An example of a vertical rectangle.

![image](images/9781119404170-fg0312.png)

[FIGURE 3-12:](#06_9781119404170-ch03.xhtml_rc03-fig-0012) The rectangle code commented out.

## DRAWING A QUADRILATERAL

In Processing, the `quad` method will create a shape that has four sides. Similar to the triangle, there are eight parameters, which represent the *x* and *y* coordinates of each point. Follow these steps:

1.  **Create a quadrilateral that has the upper-left corner at *x* = 50 and *y* = 50, the upper-right corner at *x* = 100 and *y* = 100, the lower-right corner at *x* = 100 and *y* = 150, and lower-left corner at *x* = 50 and *y* = 200 (see** [**Figure 3-13**](#06_9781119404170-ch03.xhtml_c03-fig-0013)**).**

    `quad(50, 50, 100, 100, 100, 150, 50, 200);`

2.  **Try changing the *x* and *y* coordinates to create different kinds of quadrilaterals.**

    This code creates the quadrilateral shown in [Figure 3-14](#06_9781119404170-ch03.xhtml_c03-fig-0014):

    `quad(50, 50, 150, 50, 200, 150, 100, 150);`

    This code creates the quadrilateral shown in [Figure 3-15](#06_9781119404170-ch03.xhtml_c03-fig-0015):

    `quad(50, 50, 150, 50, 150, 150, 50, 150);`

3.  **When you’re done exploring different quadrilateral shapes, comment out the line of code that creates the quadrilateral (see** [**Figure 3-16**](#06_9781119404170-ch03.xhtml_c03-fig-0016)**).**

![image](images/9781119404170-fg0313.png)

[FIGURE 3-13:](#06_9781119404170-ch03.xhtml_rc03-fig-0013) An example of a sideways trapezoid.

![image](images/9781119404170-fg0314.png)

[FIGURE 3-14:](#06_9781119404170-ch03.xhtml_rc03-fig-0014) An example of a parallelogram.

![image](images/9781119404170-fg0315.png)

[FIGURE 3-15:](#06_9781119404170-ch03.xhtml_rc03-fig-0015) An example of a square.

![image](images/9781119404170-fg0316.png)

[FIGURE 3-16:](#06_9781119404170-ch03.xhtml_rc03-fig-0016) The quadrilateral code commented out.

## DRAWING AN ELLIPSE

In Processing, the `ellipse` method will create a shape that is round. Similar to the quadrilateral, there are four parameters, which represent the *x* and *y* coordinates of the center of the shape, the width, and the height. Follow these steps:

1.  **Create an ellipse that has the center at *x* = 250 and *y* = 250, a height of 100 pixels, and a width of 100 pixels (see** [**Figure 3-17**](#06_9781119404170-ch03.xhtml_c03-fig-0017)**).**

    `ellipse(250, 250, 100, 100);`

2.  **Try changing the *x* and *y* coordinates and the width and height to create different kinds of circular shapes (ellipses).**

    This code creates the ellipse shown in [Figure 3-18](#06_9781119404170-ch03.xhtml_c03-fig-0018):

    `ellipse(250, 250, 100, 300);`

    This code creates the ellipse shown in [Figure 3-19](#06_9781119404170-ch03.xhtml_c03-fig-0019):

    `ellipse(250, 250, 300, 100);`

3.  **When you’re done exploring different ellipse shapes, comment out the line of code that creates the ellipse (see** [**Figure 3-20**](#06_9781119404170-ch03.xhtml_c03-fig-0020)**).**

![image](images/9781119404170-fg0317.png)

[FIGURE 3-17:](#06_9781119404170-ch03.xhtml_rc03-fig-0017) An example of a small circle.

![image](images/9781119404170-fg0318.png)

[FIGURE 3-18:](#06_9781119404170-ch03.xhtml_rc03-fig-0018) An example of a vertical oval.

![image](images/9781119404170-fg0319.png)

[FIGURE 3-19:](#06_9781119404170-ch03.xhtml_rc03-fig-0019) An example of a horizontal oval.

![image](images/9781119404170-fg0320.png)

[FIGURE 3-20:](#06_9781119404170-ch03.xhtml_rc03-fig-0020) The ellipse code commented out.

## DRAWING AN ARC

In Processing, the `arc` method will create a shape that is round. Similar to the ellipse, there are four parameters, which represent the *x* and *y* coordinates of the center of the shape, the width and the height of the arc, and the start and stop angles. This shape is a lot more complicated than the others, because it involves using values for the last two parameters that can be confusing.

1.  **Create an arc that has the center at *x* = 50 and *y* = 55, a height of 50 pixels and width of 50 pixels. The arc should start at 0 and end at PI (see** [**Figure 3-21**](#06_9781119404170-ch03.xhtml_c03-fig-0021)**):**

    `arc(50, 55, 50, 50, 0, PI);`

2.  **Try changing the *x* and *y* coordinates, the width and height, and the start and stop angles to create different kinds of arcs.**

    This code creates the arc shown in [Figure 3-22](#06_9781119404170-ch03.xhtml_c03-fig-0022):

    `arc(50, 55, 50, 50, 0, HALF_PI);`

    This code creates the arc shown in [Figure 3-23](#06_9781119404170-ch03.xhtml_c03-fig-0023):

    `arc(50, 55, 50, 50, 0, QUARTER_PI+PI);`

3.  **When you’re done exploring different arcs, comment out the line of code that creates the arc (see** [**Figure 3-24**](#06_9781119404170-ch03.xhtml_c03-fig-0024)**).**

![image](images/9781119404170-fg0321.png)

[FIGURE 3-21:](#06_9781119404170-ch03.xhtml_rc03-fig-0021) An example of a half-circle arc.

![image](images/9781119404170-fg0322.png)

[FIGURE 3-22:](#06_9781119404170-ch03.xhtml_rc03-fig-0022) An example of a quarter-circle arc.

![image](images/9781119404170-fg0323.png)

[FIGURE 3-23:](#06_9781119404170-ch03.xhtml_rc03-fig-0023) An example arc that uses an eighth of a circle and a half-circle.

![image](images/9781119404170-fg0324.png)

[FIGURE 3-24:](#06_9781119404170-ch03.xhtml_rc03-fig-0024) The arc code commented out.

## CREATING A UNIQUE DRAWING

Now that you know how to make the five basic shapes using the `triangle`, `rect`, `quad`, `ellipse`, and `arc` methods, try making a unique drawing placing more than one shape within your canvas (see [Figure 3-25](#06_9781119404170-ch03.xhtml_c03-fig-0025))!

![image](images/9781119404170-fg0325.png)

[FIGURE 3-25:](#06_9781119404170-ch03.xhtml_rc03-fig-0025) An example of all the shapes drawn on one canvas.

There is no wrong way to draw your unique drawing. Try adding more than one ellipse and changing the order of the shapes. For example, if you call the `rect` method first and then you call the `ellipse` method, which will be on top?

![image](images/c4.png)

In the first three chapters of this book, you’ve been working on a gray canvas with white shapes. You added a little bit of color in [Chapter 2](#05_9781119404170-ch02.xhtml) when you made a black-and-white line, but it still wasn’t very colorful.

In this chapter, you’ll learn how to add a lot of color to your static drawings, which you’ll be able to use in your animations in later chapters, too!

## ADDING COLOR TO YOUR CANVAS

The first step is to add color to your canvas. This is similar to what you did in [Chapter 2](#05_9781119404170-ch02.xhtml). Follow these steps:

1.  **Create a new Processing program and create a canvas that is 500 by 500 pixels (see** [**Figure 4-1**](#07_9781119404170-ch04.xhtml_c04-fig-0001)**):**

    `size(500, 500);`

2.  **Before the** `size` **method call, add a method call to** `background` **(see** [**Figure 4-2**](#07_9781119404170-ch04.xhtml_c04-fig-0002)**):**

    `background(10, 80, 100);`

3.  **Click Run.**

    You can see that the color of the background of your canvas is now teal (see [Figure 4-3](#07_9781119404170-ch04.xhtml_c04-fig-0003))!

4.  **Try changing the three parameter values in the background method call to change the color.**

    This code colors the canvas as shown in [Figure 4-4](#07_9781119404170-ch04.xhtml_c04-fig-0004):

    `background(255, 0, 0);`

    This code colors the canvas as shown in [Figure 4-5](#07_9781119404170-ch04.xhtml_c04-fig-0005):

    `background(0, 255, 0);`

    This code colors the canvas as shown in [Figure 4-6](#07_9781119404170-ch04.xhtml_c04-fig-0006):

    `background(0, 0, 255);`

    In the next section, you will learn what these values represent.

![image](images/9781119404170-fg0401.png)

[FIGURE 4-1:](#07_9781119404170-ch04.xhtml_rc04-fig-0001) The code needed to create a 500-x-500-pixel canvas.

![image](images/9781119404170-fg0402.png)

[FIGURE 4-2:](#07_9781119404170-ch04.xhtml_rc04-fig-0002) The code needed to change the color of the canvas’s background.

![image](images/9781119404170-fg0403.png)

[FIGURE 4-3:](#07_9781119404170-ch04.xhtml_rc04-fig-0003) An example of changing the background to teal.

![image](images/9781119404170-fg0404.png)

[FIGURE 4-4:](#07_9781119404170-ch04.xhtml_rc04-fig-0004) An example of changing the background completely red.

![image](images/9781119404170-fg0405.png)

[FIGURE 4-5:](#07_9781119404170-ch04.xhtml_rc04-fig-0005) An example of changing the background completely green.

![image](images/9781119404170-fg0406.png)

[FIGURE 4-6:](#07_9781119404170-ch04.xhtml_rc04-fig-0006) An example of changing the background completely blue.

## LEARNING ABOUT RGB VALUES

As you may have noticed in the preceding section, there is something unique about each of the values of the parameters for the background method call. Each parameter can have a number value from 0 to 255:

*   `Red` represents how much red will be in the color.
*   `Green` represents how much green will be in the color.
*   `Blue` represents how much blue will be in the color.

Notice that the parameters are `Red`, then `Green`, and then `Blue`. That’s why it’s called RGB! If all the values for these three parameters are `0`, the color will be black (see [Figure 4-7](#07_9781119404170-ch04.xhtml_c04-fig-0007)):

`background(0, 0, 0);`

![image](images/9781119404170-fg0407.png)

[FIGURE 4-7:](#07_9781119404170-ch04.xhtml_rc04-fig-0007) An example of changing the background color completely black.

If all the values for the three parameters are 255, the color will be white (see [Figure 4-8](#07_9781119404170-ch04.xhtml_c04-fig-0008)):

`background(255, 255, 255);`

![image](images/9781119404170-fg0408.png)

[FIGURE 4-8:](#07_9781119404170-ch04.xhtml_rc04-fig-0008) An example of changing the background completely white.

You can play around with the value of each parameter to get very specific colors.

![image](images/9781119404170-fg0409.png)

[FIGURE 4-9:](#07_9781119404170-ch04.xhtml_rc04-fig-0009) The RGB picker on the Rapid Tables website for color choosing.

![image](images/9781119404170-fg0410.png)

[FIGURE 4-10:](#07_9781119404170-ch04.xhtml_rc04-fig-0010) Using the RGB numbers from the website in your code.

## ADDING COLOR TO SHAPES

Shapes can have color in two different ways:

*   **Stroke:** The outline of the shape
*   **Fill:** The inside color of the shape

Add three lines of code to your program (see [Figure 4-11](#07_9781119404170-ch04.xhtml_c04-fig-0011)):

`stroke(255, 255, 255);`
`fill(56, 205, 130);`
`triangle(250, 250, 250, 450, 450, 450);`

![image](images/9781119404170-fg0411.png)

[FIGURE 4-11:](#07_9781119404170-ch04.xhtml_rc04-fig-0011) An example of changing the triangle to be green with a white outline.

Notice that the stroke is white and the fill is green. If you don’t want to have the outline be visible, you can make it the same color as the fill (see [Figure 4-12](#07_9781119404170-ch04.xhtml_c04-fig-0012)):

`stroke(56, 205, 130);`
`fill(56, 205, 130);`
`triangle(250, 250, 250, 450, 450, 450);`

![image](images/9781119404170-fg0412.png)

[FIGURE 4-12:](#07_9781119404170-ch04.xhtml_rc04-fig-0012) An example of making the entire triangle green.

If you want all your shapes to be the same color, you only have to call `stroke` and `fill` once, at the beginning (see [Figure 4-13](#07_9781119404170-ch04.xhtml_c04-fig-0013)):

`stroke(56, 205, 130);`
`fill(56, 205, 130);`
`triangle(250, 250, 250, 450, 450, 450);`
`rect(100, 50, 200, 400);`
`quad(50, 50, 150, 50, 150, 150, 50, 150);`

![image](images/9781119404170-fg0413.png)

[FIGURE 4-13:](#07_9781119404170-ch04.xhtml_rc04-fig-0013) An example of making three shapes completely green.

But if you want all your shapes to be different colors, you need to call `stroke` and `fill` before you draw each shape (see [Figure 4-14](#07_9781119404170-ch04.xhtml_c04-fig-0014)):

`stroke(56, 205, 130);`
`fill(56, 205, 130);`
`triangle(250, 250, 250, 450, 450, 450);`

`stroke(56, 105, 205);`
`fill(556, 105, 205);`
`rect(100, 50, 200, 400);`

`stroke(205, 56, 205);`
`fill(205, 56, 205);`
`quad(50, 50, 150, 50, 150, 150, 50, 150);`

![image](images/9781119404170-fg0414.png)

[FIGURE 4-14:](#07_9781119404170-ch04.xhtml_rc04-fig-0014) An example of making three shapes different colors.

Try adding color to the drawing you made in [Chapter 3](#06_9781119404170-ch03.xhtml), or creating a new drawing now that you can have color!

![image](images/c5.png)

In the first four chapters of this book, you saw how to *call* methods. You called methods to create a canvas, change the color of the canvas, create shapes, and change the color of those shapes. Methods are a really useful tool in coding because a lot of lines of code get written once, get named, and then coders can use the name of the method to execute all those lines of code. Methods make code easier to understand and more manageable.

In this chapter, you’ll learn why methods are useful, discover methods that you’ll want to write to make animations (and later, games!), and find out how to write your own methods. But first, a short overview of methods!

## LEARNING ABOUT METHODS

In this section, you’ll learn more about Java methods. Methods are a really important part of coding, because they break your code up into small chunks that are named. You can then use the name of these code chunks to call the same code over and over again. Methods are one of the fundamentals of coding and will be useful even in other programming languages, not just Java.

### A METHOD SIGNATURE

In Java, you always write a method the same way:

*`returnType`**`methodName`*`(`*`parameterType`**`parameterName`*`)`
`{`
*`CODE`*
`}`

The first line of code in the above code snippet is called the *method signature.* It has all the information you (or another coder using your code) would need to call the method.

The method signature has three parts:

*   `returnType`: The return type is the type of data that will be returned when the code in the method finishes executing (or running). You’ll get more examples of this as you go through this book. In a lot of the code you’ll be writing, you’ll use the return type `void`. But there are times when it’s important to have data returned. For example, in [Chapter 2](#05_9781119404170-ch02.xhtml), you added a line of code to call a method called `color`. The return type for the `color` method is `Color`. When the `color` method finishes executing, it returns data that is of type `Color`, and that data gets named `black` when you assigned it to the variable you created. Don’t worry if this doesn’t make sense yet — you’ll re-visit this idea throughout the book to get a better understanding.
*   `methodName`: The method name can be anything you want, but typically it describes what the method does. For example, if you had a method that added two numbers, you might call it `add`.
*   `(parameterType parameterName)`: After the method name there is always an open and closed parentheses. Between the open and closed parentheses is an optional parameter list. Sometimes, methods don’t have parameters, like in the method `exit()`. When a method does have parameters, you, as the coder, have to specify what type the parameter is and what its name is. It’s kind of like creating a new variable to be used in the method. For example, the `color` method from [Chapter 2](#05_9781119404170-ch02.xhtml) has one parameter that is of type `int` (integer or number) and, though you never saw it, the parameter was named `gray`. Later in this book, you’ll write methods that take in parameters and this will become clearer.

### A METHOD BODY

The last three lines of the code snippet is called the *method body.* This is where all the code for the method goes. All the code that is inside the method body will be executed when the method is called.

If the method needs to return data of a certain type, let’s say an `int` (or number), then a `return` statement needs to be the last line of code in the method body:

*`returnType`**`methodName`*`(`*`parameterType`**`parameterName`*`)`
`{`
*`CODE`*

`return 5;`
`}`

You’ll learn more about method bodies throughout this book.

## WRITING YOUR FIRST TWO METHODS

To practice what you just read, you’ll now write two of your own methods! When you want to make an animation or videogame using the Processing application, there are two methods that you should write that are critical. In this case, the methods have specific names that you have to use. Don’t worry — later in this chapter, you’ll write a method with a name that you can choose.

### WRITING THE SETUP METHOD

The first method is called `setup`. This method is automatically called first, when you click the Run button.

1.  **Open a new Sketch window.**
2.  **Write the method signature and empty method body of a method called** `setup` **that returns nothing and has no parameters (see** [**Figure 5-1**](#08_9781119404170-ch05.xhtml_c05-fig-0001)**):**

    `void setup()`
    `{`

    `}`

3.  **Add two lines of code inside the method body for the** `setup` **method to create a 500-x-500-pixel canvas that has a red background color (see** [**Figure 5-2**](#08_9781119404170-ch05.xhtml_c05-fig-0002)**):**

    `void setup()`
    `{`
    **`size(500, 500);`**
    **`background(255, 0, 0);`**
    `}`

4.  **Click the Run button to test your code.**

    A red canvas appears (see [Figure 5-3](#08_9781119404170-ch05.xhtml_c05-fig-0003)).

![image](images/9781119404170-fg0501.png)

[FIGURE 5-1:](#08_9781119404170-ch05.xhtml_rc05-fig-0001) An empty `setup` method.

![image](images/9781119404170-fg0502.png)

[FIGURE 5-2:](#08_9781119404170-ch05.xhtml_rc05-fig-0002) The `setup` method body with a new, red canvas.

![image](images/9781119404170-fg0503.png)

[FIGURE 5-3:](#08_9781119404170-ch05.xhtml_rc05-fig-0003) A red canvas appears when you click the Run button.

When making a simple program, the `setup` method will probably be very simple, like the one you just wrote. But when you move into making a videogame, the setup code can get more complicated. You’ll see that later in this book.

### WRITING THE DRAW METHOD

The next method is called `draw`. This method is automatically called after the setup method finishes executing. The `draw` method is then called repeatedly (over and over) until the canvas is closed.

1.  **Under the** `setup` **method, *after* the closed curly brace, add another method called** `draw` **that has no return data and doesn’t take any parameters (see** [**Figure 5-4**](#08_9781119404170-ch05.xhtml_c05-fig-0004)**):**

    `void draw()`
    `{`

    `}`

2.  **Inside the** `method` **body, add three lines of code to draw a circle in the center of the canvas that has a white outline and blue fill (see** [**Figure 5-5**](#08_9781119404170-ch05.xhtml_c05-fig-0005)**):**

    `void draw()`
    `{`
    **`stroke(255, 255, 255);`**
    **`fill(0, 0, 250);`**
    **`ellipse(250, 250, 300, 300);`**
    `}`

3.  **Press the Run button and make sure that the circle is drawn (see** [**Figure 5-6**](#08_9781119404170-ch05.xhtml_c05-fig-0006)**).**

![image](images/9781119404170-fg0504.png)

[FIGURE 5-4:](#08_9781119404170-ch05.xhtml_rc05-fig-0004) An empty `draw` method.

![image](images/9781119404170-fg0505.png)

[FIGURE 5-5:](#08_9781119404170-ch05.xhtml_rc05-fig-0005) Three lines of code to create a blue circle with a white outline.

![image](images/9781119404170-fg0506.png)

[FIGURE 5-6:](#08_9781119404170-ch05.xhtml_rc05-fig-0006) The blue-and-white circle on the canvas.

The `draw` method is called over and over and over again, but the circle only appears once. This is because the circle is actually being drawn over and over, but it’s being drawn in the exact same place, so you can’t see any changes. In the next section, you’ll learn how to make a simple animation!

## WRITING YOUR FIRST TWO ORIGINAL METHODS

Your goal for this section is to make the circle you made in the previous section (refer to [Figure 5-6](#08_9781119404170-ch05.xhtml_c05-fig-0006)) move across the screen!

### CREATING TWO USEFUL VARIABLES

Above the two methods, you need to add two variables that will keep track of the *x*- and *y*-coordinates of your ellipse.

1.  **To get started, add two variables called** `xCoordinate` **and** `yCoordinate`**. The variables should be type** `int` **(number) and should have the value 250 (see** [**Figure 5-7**](#08_9781119404170-ch05.xhtml_c05-fig-0007)**):**

    `int xCoordinate = 250;`
    `int yCoordinate = 250;`

2.  **Replace both the 250 values in the** `ellipse` **method call with the variables you created in Step 1 (see** [**Figure 5-8**](#08_9781119404170-ch05.xhtml_c05-fig-0008)**):**

    `void draw()`
    `{`
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    **`ellipse(xCoordinate, yCoordinate, 300, 300);`**
    `}`

3.  **Click the Run button to test to make sure the blue-and-white circle is still where it was in** [**Figure 5-6**](#08_9781119404170-ch05.xhtml_c05-fig-0006)**.**

    Because you set the two variables both to 250, the circle stays in the same place (see [Figure 5-9](#08_9781119404170-ch05.xhtml_c05-fig-0009)).

4.  **Change the** `xCoordinate` **variable to have a value of 0 (see** [**Figure 5-10**](#08_9781119404170-ch05.xhtml_c05-fig-0010)**):**

    `int xCoordinate = 0;`
    `int yCoordinate = 250;`

5.  **Click the Run button and test where the blue-and-white circle is.**

    The circle will now be at *x* = 0 and *y* = 250, putting it in the center on the very left of the canvas (refer to [Figure 5-10](#08_9781119404170-ch05.xhtml_c05-fig-0010)).

6.  **Change the yCoordinate variable to have a value of 0, too (see** [**Figure 5-11**](#08_9781119404170-ch05.xhtml_c05-fig-0011)**):**

    `int xCoordinate = 0;`
    `int yCoordinate = 0;`

7.  **Click the Run button and make sure the blue-and-white circle is in the upper-left corner of the canvas.**

![image](images/9781119404170-fg0507.png)

[FIGURE 5-7:](#08_9781119404170-ch05.xhtml_rc05-fig-0007) Two variables to keep track of the *x* and *y* location of the circle.

![image](images/9781119404170-fg0508.png)

[FIGURE 5-8:](#08_9781119404170-ch05.xhtml_rc05-fig-0008) Using the two variables in the ellipse method call.

![image](images/9781119404170-fg0509.png)

[FIGURE 5-9:](#08_9781119404170-ch05.xhtml_rc05-fig-0009) Test the code to make sure the circle is still in the center.

![image](images/9781119404170-fg0510.png)

[FIGURE 5-10:](#08_9781119404170-ch05.xhtml_rc05-fig-0010) Change the `xCoordinate` variable to 0 to move the circle to the left.

![image](images/9781119404170-fg0511.png)

[FIGURE 5-11:](#08_9781119404170-ch05.xhtml_rc05-fig-0011) Change the `yCoordinate` variable to 0 to move the circle to the top.

Now that you have two variables that can help move your circle around the canvas, you can write two methods to change the value of the variables while the canvas is still open.

### CREATING A CUSTOM METHOD

Now that you have two variables, `xCoordinate` and `yCoordinate`, that control where your circle is drawn on the canvas, you can write a method to change the value of the variables while the canvas is still open.

1.  **Write a new method called** `moveDownAndRight` **that doesn’t return anything and has no parameters (see** [**Figure 5-12**](#08_9781119404170-ch05.xhtml_c05-fig-0012)**):**

    `void moveDownAndRight()`
    `{`

    `}`

    Make sure the `xCoordinate` and `yCoordinate` variables are both set to 0 (refer to [Figure 5-12](#08_9781119404170-ch05.xhtml_c05-fig-0012)):

    `int xCoordinate = 0;`
    `int yCoordinate = 0;`

2.  **Set the** `xCoordinate` **and** `yCoordinate` **variables to be what they were before, plus 1 (see** [**Figure 5-13**](#08_9781119404170-ch05.xhtml_c05-fig-0013)**):**

    `void moveDownAndRight()`
    `{`
    **`xCoordinate = xCoordinate + 1;`**
    **`yCoordinate = yCoordinate + 1;`**
    `}`

    So, if `xCoordinate` starts at 0, then the first time the `moveDownAndRight` method is called, the `xCoordinate` variable will be set to 1, and the second time the method is called, the variable will be set to 2\. This will happen forever until the canvas is closed.

3.  **Add a line of code to call the** `moveDownAndRight` **method after the circle is drawn (see** [**Figure 5-14**](#08_9781119404170-ch05.xhtml_c05-fig-0014)**):**

    `void draw()`
    `{`
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    `ellipse(xCoordinate, yCoordinate, 300, 300);`
    **`moveDownAndRight();`**
    `}`

4.  **Click the Run button to test the code you just wrote.**

    Because the draw method is called over and over until the canvas is closed, the circle should start to move down and to the right (see [Figure 5-15](#08_9781119404170-ch05.xhtml_c05-fig-0015)).

5.  **As you noticed, the circle gets drawn over and over, but you can see the trail of circles that it draws. If you want to make the circle move without seeing its trail, add a call to the** `background` **method before you draw the circle (see** [**Figure 5-16**](#08_9781119404170-ch05.xhtml_c05-fig-0016)**):**

    `void draw()`
    `{`
    **`background(255, 0, 0);`**
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    `ellipse(xCoordinate, yCoordinate, 300, 300);`
    `moveDownAndRight();`
    `}`

    Now, your `draw` method does the following steps:

    *   Makes the canvas all red
    *   Draws a circle that has a white outline and a blue fill
    *   Updates the location of the circle
    *   Repeats until the canvas is closed
6.  **Click the Run button and make sure your circle moves across the screen without having a trail behind it (see** [**Figure 5-17**](#08_9781119404170-ch05.xhtml_c05-fig-0017)**).**

![image](images/9781119404170-fg0512.png)

[FIGURE 5-12:](#08_9781119404170-ch05.xhtml_rc05-fig-0012) An empty `moveDownAndRight` method.

![image](images/9781119404170-fg0513.png)

[FIGURE 5-13:](#08_9781119404170-ch05.xhtml_rc05-fig-0013) Two lines of code added to `moveDownAndRight` to update the `xCoordinate` and `yCoordinate` variables.

![image](images/9781119404170-fg0514.png)

[FIGURE 5-14:](#08_9781119404170-ch05.xhtml_rc05-fig-0014) A call to `moveDownAndRight` every time the circle is drawn.

![image](images/9781119404170-fg0515.png)

[FIGURE 5-15:](#08_9781119404170-ch05.xhtml_rc05-fig-0015) The blue-and-white circle moves across the canvas with a tail.

![image](images/9781119404170-fg0516.png)

[FIGURE 5-16:](#08_9781119404170-ch05.xhtml_rc05-fig-0016) Another call to the background method to overwrite the circle trail.

![image](images/9781119404170-fg0517.png)

[FIGURE 5-17:](#08_9781119404170-ch05.xhtml_rc05-fig-0017) The circle moving across the canvas with no trail.

Congratulations! You’ve now made an animation! In the next section, you’ll learn how to adjust the speed of your animation.

## ADDING PARAMETERS TO YOUR METHOD

Now that you have an animation, you can add a parameter to speed up your animation. Adding 1 to the `xCoordinate` and 1 to the `yCoordinate` is basically moving the circle 1 pixel left and 1 pixel down each time it’s drawn. If you change the 1 to a 2, the circle will move 2 pixels left and 2 pixels down, which will make the circle look like it’s moving twice as fast (see [Figure 5-18](#08_9781119404170-ch05.xhtml_c05-fig-0018)):

`void moveDownAndRight()`
`{`
`xCoordinate = xCoordinate + 2;`
`yCoordinate = yCoordinate + 2;`
`}`

![image](images/9781119404170-fg0518.png)

[FIGURE 5-18:](#08_9781119404170-ch05.xhtml_rc05-fig-0018) Change the `xCoordinate` and `yCoordinate` variables to move 2 pixels each time instead of 1 pixel.

In this example, there are only two places where you have to change the value that shows the speed:

`xCoordinate = xCoordinate + 2;`
`yCoordinate = yCoordinate + 2;`

But you still don’t want to accidentally change one of them and not the other. To avoid that error, you can add a parameter to your `moveDownAndRight` method so that the `xCoordinate` and `yCoordinate` variables always change by the same amount.

1.  **Add the parameter type and parameter name to the** `moveDownAndRight` **method signature. The type should be** `int` **(because the value is a number) and the name should be** `speed`**:**

    **`void moveDownAndRight(int speed)`**
    `{`
    `xCoordinate = xCoordinate + 2;`
    `yCoordinate = yCoordinate + 2;`
    `}`

    You can actually make the parameter name anything you want, but it’s best if the name actually represents the value, so `speed` is a good choice.

    Notice that you get an error message at the bottom of the Processing window (see [Figure 5-20](#08_9781119404170-ch05.xhtml_c05-fig-0020)). That happens because, when you call `moveDownAndRight`, you don’t pass a number value.

2.  **Put the number 2 between the parentheses of the** `moveDownAndRight` **method call (see** [**Figure 5-21**](#08_9781119404170-ch05.xhtml_c05-fig-0021)**):**

    `void draw()`
    `{`
    `background(255, 0, 0);`
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    `ellipse(xCoordinate, yCoordinate, 300, 300);`
    **`moveDownAndRight(2);`**
    `}`

3.  **Replace the two 2’s in the method body of the** `moveDownAndRight` **method with the parameter** `speed` **(see** [**Figure 5-22**](#08_9781119404170-ch05.xhtml_c05-fig-0022)**):**

    `void moveDownAndRight(int speed)`
    `{`
    **`xCoordinate = xCoordinate + speed;`**
    **`yCoordinate = yCoordinate + speed;`**
    `}`

4.  **Click the Run button and make sure the circle is still moving as fast as it was at the beginning of this section, when you originally changed the circle to move twice as fast (the code changes are shown in** [**Figure 5-18**](#08_9781119404170-ch05.xhtml_c05-fig-0018)**).**
5.  **Try changing the value of the parameter to 8 (see** [**Figure 5-23**](#08_9781119404170-ch05.xhtml_c05-fig-0023)**):**

    `void draw()`
    `{`
    `background(255, 0, 0);`
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    `ellipse(xCoordinate, yCoordinate, 300, 300);`
    **`moveDownAndRight(8);`**
    `}`

6.  **Press the Run button to see how fast the circle moves.**

![image](images/9781119404170-fg0519.png)

Figure 5-19: The new `speed` parameter in the `moveDownAndRight` method.

![image](images/9781119404170-fg0520.png)

[FIGURE 5-20:](#08_9781119404170-ch05.xhtml_rc05-fig-0020) The error message shown when the `moveDownAndRight` method call doesn’t pass a value for the parameter.

![image](images/9781119404170-fg0521.png)

[FIGURE 5-21:](#08_9781119404170-ch05.xhtml_rc05-fig-0021) Passing in the value 2 to the `moveDownAndRight` method.

![image](images/9781119404170-fg0522.png)

[FIGURE 5-22:](#08_9781119404170-ch05.xhtml_rc05-fig-0022) Using the speed parameter in the `moveDownAndRight` method.

![image](images/9781119404170-fg0523.png)

[FIGURE 5-23:](#08_9781119404170-ch05.xhtml_rc05-fig-0023) Change the parameter of the `moveDownAndRight` method to 8.

Wow! That is some incredible coding! In this chapter, you made new variables, three methods, and added a parameter! You did all that coding to make an animation. In the next chapter, you’ll learn how to have users interact with your animation. Before ending, make sure you save your Sketch program under the name CircleAnimation so that you can open it in [Chapter 6](#09_9781119404170-ch06.xhtml).

![image](images/c6.png)

One of the most important parts of a videogame is the player! And the player can’t do much if she’s just watching an animation happen on screen. In this chapter, you learn how to make your shapes and animations interact with the user. This is the first step to making a videogame!

## MOVING WITH THE MOUSE

Processing is a great application, because it has a lot of built-in functions and variables that you get to use. You’ve already used some of these — like the shape functions earlier in this book. In [Chapter 5](#08_9781119404170-ch05.xhtml), you even defined two methods that Processing already knows about: setup and draw.

Here I’ll introduce you to two variables that Processing gives you to use: `mouseX` and `mouseY`. These variables represent the *x*- and *y*-coordinates of where the mouse is on the canvas at all times. In [Chapter 5](#08_9781119404170-ch05.xhtml), you had two variables — `xCoordinate` and `yCoordinate` — and when you changed their values in the `moveDownAndRight` method, the shape’s location was moved. Using the `mouseX` and `mouseY` variables is exactly like that. The only difference is that the values of `mouseX` and `mouseY` are automatically changed when the user moves the mouse (instead of having to call a method).

To make your shapes follow your mouse around the canvas, follow these steps:

1.  **Open Processing, choose File ⇒ Open, and then open the CircleAnimation Sketch file that you saved at the end of** [**Chapter 5**](#08_9781119404170-ch05.xhtml) **(see** [**Figure 6-1**](#09_9781119404170-ch06.xhtml_c06-fig-0001)**).**

    To make sure you have all the code you need, here is the code your CircleAnimation should have:

    `int xCoordinate = 0;`
    `int yCoordinate = 0;`

    `void setup()`
    `{`
    `size(500, 500);`
    `background(255, 0, 0);`
    `}`

    `void draw()`
    `{`
    `background(255, 0, 0);`
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    `ellipse(xCoordinate, yCoordinate, 300, 300);`
    `moveDownAndRight(8);`
    `}`

    `void moveDownAndRight(int speed)`
    `{`
    `xCoordinate = xCoordinate + speed;`
    `yCoordinate = yCoordinate + speed;`
    `}`

2.  **Find the call to the** `ellipse` **method in your `draw` method, and change** `xCoordinate` **to** `mouseX` **and** `yCoordinate` **to** `mouseY` **(see** [**Figure 6-2**](#09_9781119404170-ch06.xhtml_c06-fig-0002)**).**

    The line of code that you should change is the call to `ellipse`:

    `ellipse(mouseX, mouseY, 300, 300);`

3.  **Comment out the line of code that calls your `moveDownAndRight` method (see** [**Figure 6-3**](#09_9781119404170-ch06.xhtml_c06-fig-0003)**).**

    Because the location of the circle will be updated with the `mouseX` and `mouseY` variables now, you don’t need to update the `xCoordinate` or `yCoordinate` variables anymore.

    ***Remember:*** To comment out the code, you put two `//` in front of the line of code, like this:

    `//moveDownAndRight(8);`

    Even though it’s usually better to remove code that isn’t being used, when you’re not sure of the changes you’re going to make, it can be better to comment lines out first. Then, once you have your code working the way you want it to, you can remove commented-out code to make it easier to read.

4.  **Press the Run button and watch how your circle moves to wherever your mouse is (see** [**Figure 6-5**](#09_9781119404170-ch06.xhtml_c06-fig-0005)**)!**

![image](images/9781119404170-fg0601.png)

[FIGURE 6-1:](#09_9781119404170-ch06.xhtml_rc06-fig-0001) The CircleAnimation Sketch from the end of [Chapter 5](#08_9781119404170-ch05.xhtml).

![image](images/9781119404170-fg0602.png)

[FIGURE 6-2:](#09_9781119404170-ch06.xhtml_rc06-fig-0002) Change the code to move the circle to the mouse’s location.

![image](images/9781119404170-fg0603.png)

[FIGURE 6-3:](#09_9781119404170-ch06.xhtml_rc06-fig-0003) Comment out the method call to `moveDownAndRight`.

![image](images/9781119404170-fg0604.png)

[FIGURE 6-4:](#09_9781119404170-ch06.xhtml_rc06-fig-0004) A variation of the CircleAnimation code where unused code is removed.

![image](images/9781119404170-fg0605.png)

[FIGURE 6-5:](#09_9781119404170-ch06.xhtml_rc06-fig-0005) When you run the code, the circle always stays with the mouse.

## INTERACTING WITH MOUSE CLICKS

Sometimes you’ll want your shapes to always move with your mouse, but other times you’ll want your shapes to move with your mouse only when the user is clicking the mouse. Think about it like a click and drag. You might have encountered something like this on a website or game where there was a circle that you had to click and drag to submit an answer to a question.

For example, you might have encountered sliders like the ones on the W3Schools.com website ([`www.w3schools.com/howto/howto_js_rangeslider.asp`](http://www.w3schools.com/howto/howto_js_rangeslider.asp); see [Figure 6-6](#09_9781119404170-ch06.xhtml_c06-fig-0006)).

![image](images/9781119404170-fg0606.png)

[FIGURE 6-6:](#09_9781119404170-ch06.xhtml_rc06-fig-0006) Sliders that are made to have a shape move horizontally only when the user clicks and drags them.

You can quickly turn your code into a version of a slider by using another one of the Processing methods that comes with the application: `mouseDragged`. Follow these steps:

1.  **Add another method called** `mouseDragged` **that does not return a value and takes no parameters (see** [**Figure 6-7**](#09_9781119404170-ch06.xhtml_c06-fig-0007)**).**

    `mouseDragged` is a method that Processing knows to call when the user has clicked the mouse button and moved the mouse with the button still pressed. The code that you will be adding is after your `draw` method and before your `moveDownAndRight` method:

    `void mouseDragged()`
    `{`
    `}`

2.  **Add two lines of code to the** `mouseDragged` **method that update the** `xCoordinate` **and** `yCoordinate` **variables to be the current position of the mouse (**`mouseX` **and** `mouseY`**), as shown in** [**Figure 6-8**](#09_9781119404170-ch06.xhtml_c06-fig-0008)**.**

    The two lines of code you should add to the method from Step 1 are:

    `xCoordinate = mouseX;`
    `yCoordinate = mouseY;`

3.  **Change the method call of the ellipse to move to the** `xCoordinate` **and** `yCoordinate` **location instead of the** `mouseX` **and** `mouseY` **location (see** [**Figure 6-9**](#09_9781119404170-ch06.xhtml_c06-fig-0009)**).**

    The call to the `ellipse` method should now be:

    `ellipse(xCoordinate, yCoordinate, 300, 300);`

4.  **Press the Run button.**

    When you move the mouse around the canvas, the circle shouldn’t move. But if you click and hold the mouse button and then move the mouse, the circle should follow the mouse.

![image](images/9781119404170-fg0607.png)

[FIGURE 6-7:](#09_9781119404170-ch06.xhtml_rc06-fig-0007) An empty `mouseDragged` method.

![image](images/9781119404170-fg0608.png)

[FIGURE 6-8:](#09_9781119404170-ch06.xhtml_rc06-fig-0008) Two lines of code that change the `xCoordinate` and `yCoordinate` variables to match the location of the mouse (using `mouseX` and `mouseY`).

![image](images/9781119404170-fg0609.png)

[FIGURE 6-9:](#09_9781119404170-ch06.xhtml_rc06-fig-0009) Update the call to the `ellipse` function to use `xCoordinate` and `yCoordinate`.

You’re doing a lot with user interaction! This is your first step to making a real videogame. Learning how to do simple interactions with basic shapes is how all professional coders start to learn how to integrate what they’ll need for their full-fledged games.

## MAKING A HORIZONTAL SLIDER

Let’s say you wanted to make a more realistic horizontal slider. You could change your code to make sure that the circle always stayed at the center of the screen on the *y*-axis, and only moved with the mouse on the *x*-axis. Follow these steps:

1.  **Change parameter in the `ellipse` method call from `yCoordinate` to 250, as shown in** [**Figure 6-10**](#09_9781119404170-ch06.xhtml_c06-fig-0010)**.**

    This will keep the circle at the center of the canvas on the vertical (or *y*-) axis.

    `ellipse(xCoordinate, 250, 300, 300);`

2.  **Comment out the update to the** `yCoordinate` **variable in the** `mouseDragged` **method (see** [**Figure 6-11**](#09_9781119404170-ch06.xhtml_c06-fig-0011)**).**

    Only the `xCoordinate` variable needs to be updated as the mouse is dragged.

    `void mouseDragged()`
    `{`
    `xCoordinate = mouseX;`
    `//yCoordinate = mouseY;`
    `}`

3.  **Press the Run button and make sure that the circle only moves left and right when you click and drag the mouse.**

    If you let go of the mouse button, the circle should stop moving. If you move your mouse up and down while pressing the mouse button, the circle should not move up and down.

![image](images/9781119404170-fg0610.png)

[FIGURE 6-10:](#09_9781119404170-ch06.xhtml_rc06-fig-0010) Keep the circle at the center of the canvas on the vertical axis.

![image](images/9781119404170-fg0611.png)

[FIGURE 6-11:](#09_9781119404170-ch06.xhtml_rc06-fig-0011) Comment out the `yCoordinate` variable update in the `mouseDragged` method.

Can you figure out how to change the code so that the circle is in the center of the canvas on the horizontal (*x*-) axis and moves with the mouse up and down, instead of left and right?

## WORKING WITH CONDITIONAL STATEMENTS

Now that you know how to have some experience with user interaction, it’s time to learn about a very important part of coding: conditional statements.

### GETTING ACQUAINTED WITH CONDITIONAL STATEMENTS

*Conditional statements,* also sometimes called *if statements* or *if-else statements,* are bits of code that you add to change the effect of your code based on some condition. One way to understand this is in the context of your everyday life: If you eat dinner, you get ice cream; otherwise, you get a banana. I could imagine that written in code something like this:

`if(eatDinner == true)`
`{`
`giveIceCream();`
`}`
`else`
`{`
`giveBanana();`
`}`

As you might notice, there are very specific parts to a conditional statement, just like there were for method calls and method definitions:

`if(CONDITION)`
`{`
`CODE`
`}`
`else`
`{`
`CODE`
`}`

A conditional statement always starts with a lower-cased `if` followed by open and closed parentheses. In between the open and closed parentheses there is a condition. This is something that must evaluate to true or false. In the `eatDinner` example above, the condition was `eatDinner == true`. If the variable `eatDinner` is true, then the entire condition is actually `true == true`, which evaluates to true. If the `eatDinner` is false, then the entire condition is actually `false == true`, which evaluates to false. You can think of a condition as a question that has a yes or no answer (true = yes, false = no).

Another interesting feature of conditional statements is that you don’t always have to have the `else` part. This is a valid conditional statement:

`if(CONDITION)`
`{`

`}`

Sometimes you don’t have an alternative. For example, maybe your parents say if you don’t eat dinner, you don’t get anything! Your code would look like this:

`if(eatDinner == true)`
`{`
`giveIceCream();`
`}`

You also might have more than one option. For example, maybe you have a deal with your parents that says if you get at least 90 points on your exam, you get a chocolate sundae, but if you get at least 70 points you at least get a scoop of ice cream, and if you get under 70 points you get grounded. Your code would look like this:

`if(examPoints >= 90)`
`{`
`giveChocolateSundae();`
`}`
`else if(examPoints >= 70)`
`{`
`giveScoop();`
`}`
`else`
`{`
`giveGrounding();`
`}`

Notice that the condition for these `if` statements still evaluate to true or false, but they’re comparing a variable to a number instead of to true or false.

Do you think that if you received 91 points you would get a chocolate sundae *and* a scoop of ice cream? You did get >= 90 points, but you also got >= 70 points.

No. You’ll only get the chocolate sundae. That’s because conditional statements are considered a block of code and you actually skip all the code after you’ve found a condition that is true. So, if you got 91 points on the exam, then the code inside of the first `if` statement would execute (giving you a chocolate sundae) and the code inside the second `if` statement and inside of the `else` statement would be skipped over. This is something you’ll see throughout this book as well.

### ADDING CONDITIONAL STATEMENTS TO YOUR CODE

Now that you’ve had a brief introduction to conditional statements, it’s time to add some to the code! You’re going to make it so that when the mouse is being pressed, the color of the circle is blue, and when the mouse is let go, the color of the circle is green. Follow these steps:

1.  **Add some space around the stroke and fill lines of code so that you can visually separate the area where you’re going to add the conditional statement (see** [**Figure 6-12**](#09_9781119404170-ch06.xhtml_c06-fig-0012)**).**
2.  **Add an `if` statement around the calls to the stroke and fill methods (see** [**Figure 6-13**](#09_9781119404170-ch06.xhtml_c06-fig-0013)**).**

    Make sure that the curly braces are around both lines. The condition for this `if` statement should be as follows:

    `mousePressed == true`

    `mousePressed` is a variable that the Processing application gives you to use, just like `mouseX` and `mouseY`.

    `if(mousePressed == true)`
    `{`
    `stroke(255, 255, 255);`
    `fill(0, 0, 250);`
    `}`

3.  **Add an `else` statement below the `if` statement to complete the conditional statement, and add two lines of code inside the curly braces of the `if` statement to make the stroke white and the fill green (see** [**Figure 6-14**](#09_9781119404170-ch06.xhtml_c06-fig-0014)**).**

    `else`
    `{`
    `stroke(255, 255, 255);`
    `fill(0, 255, 0);`
    `}`

4.  **Press the Run button and make sure that when you’re pressing the mouse the circle is blue and when you let go it turns green!**

![image](images/9781119404170-fg0612.png)

[FIGURE 6-12:](#09_9781119404170-ch06.xhtml_rc06-fig-0012) Add space where your conditional statement will go.

![image](images/9781119404170-fg0613.png)

[FIGURE 6-13:](#09_9781119404170-ch06.xhtml_rc06-fig-0013) Add the `if` part of the conditional statement.

![image](images/9781119404170-fg0614.png)

[FIGURE 6-14:](#09_9781119404170-ch06.xhtml_rc06-fig-0014) Add the `else` part of the conditional statement.

Incredible! Your code is really coming along! You have a moving shape that changes color based on user input. In the last section of this chapter, you’ll learn how to interact with your shape using the keyboard instead of the mouse.

## MOVING SHAPES WITH THE KEYBOARD

This section introduces you to using the keyboard to interact with your animation. This is going to be very important because it’s how you’ll move your character when you make a videogame. Follow these steps:

1.  **Change the call to the `ellipse` method to use the `yCoordinate` variable again (see** [**Figure 6-15**](#09_9781119404170-ch06.xhtml_c06-fig-0015)**).**

    `ellipse(xCoordinate, yCoordinate, 300, 300);`

2.  **Delete the `mouseDragged` method that you created (see** [**Figure 6-16**](#09_9781119404170-ch06.xhtml_c06-fig-0016)**).**

    This time you *do* want to delete the code. You don’t need the `mouseDragged` call anymore because the keys are going to change the location of the circle. Because `mouseDragged` is automatically called by the Processing application, you don’t want any code accidentally being called.

3.  **Add a new method called `keyPressed` that returns no value and has no parameters (see** [**Figure 6-17**](#09_9781119404170-ch06.xhtml_c06-fig-0017)**).**

    This is just like the `mouseDragged` method. It’s one that the Processing application knows about and will automatically call when any key is pressed on the keyboard.

    `void keyPressed()`
    `{`

    `}`

4.  **Add a conditional statement to the `keyPressed` method that checks if the key that was pressed was the letter W (see** [**Figure 6-18**](#09_9781119404170-ch06.xhtml_c06-fig-0018)**).**

    If you look at the keyboard, the letters W, A, S, and D create a shape similar to the four arrow keys. Because we still have mouse interactions (when you click the mouse it changes color), you want to leave the right hand for the mouse and use your left hand for moving the shape. This is often done in videogames, using WASD to move a character and the mouse to be able to look around and aim.

    `void keyPressed()`
    `{`
    `if(key == 'w')`
    `{`

    `}`
    `}`

5.  **Add a line of code to change the yCoordinate variable to be the same value, minus 1 pixel.**

    This will move the shape up 1 pixel. This line should be between the open and closed curly braces of the conditional statement:

    `yCoordinate = yCoordinate – 1;`

6.  **Press the Run button and then press the W key.**

    Make sure that the circle moves up by one pixel each time you press the key.

7.  **Add three more `if` statement parts to your conditional statement to check if the key that was pressed was A, S, or D (see** [**Figure 6-20**](#09_9781119404170-ch06.xhtml_c06-fig-0020)**).**

    Make sure that you’re changing the `xCoordinate` and `yCoordinate` variables correctly!

    `void keyPressed()`
    `{`
    `if(key == 'w')`
    `{`
    `yCoordinate = yCoordinate – 1;`
    `}`
    `else if(key == 'a')`
    `{`
    `xCoordinate = xCoordinate – 1;`
    `}`
    `else if(key == 's')`
    `{`
    `yCoordinate = yCoordinate + 1;`
    `}`
    `else if(key == 'd')`
    `{`
    `xCoordinate = xCoordinate + 1;`
    `}`
    `}`

8.  **Press the Run button and try pressing all four keys (W, A, S, and D) to move the circle around the canvas.**
9.  **Just to make sure that what you just wrote didn’t mess anything up, try also pressing the mouse to make sure it still changes color.**

![image](images/9781119404170-fg0615.png)

[FIGURE 6-15:](#09_9781119404170-ch06.xhtml_rc06-fig-0015) Control the circle’s location with the `xCoordinate` and `yCoordinate` variables.

![image](images/9781119404170-fg0616.png)

[FIGURE 6-16:](#09_9781119404170-ch06.xhtml_rc06-fig-0016) Delete the `mouseDragged` method so that it isn’t accidentally called.

![image](images/9781119404170-fg0617.png)

[FIGURE 6-17:](#09_9781119404170-ch06.xhtml_rc06-fig-0017) Create a new method called `keyPressed`.

![image](images/9781119404170-fg0618.png)

[FIGURE 6-18:](#09_9781119404170-ch06.xhtml_rc06-fig-0018) Add a conditional statement to the `keyPressed` method.

![image](images/9781119404170-fg0619.png)

Figure 6-19: Update the `yCoordinate` variable to move the circle up when w is pressed.

![image](images/9781119404170-fg0620.png)

[FIGURE 6-20:](#09_9781119404170-ch06.xhtml_rc06-fig-0020) Add three more if statements to the conditional to move the shape in all four directions.

![image](images/9781119404170-fg0621.png)

[FIGURE 6-21:](#09_9781119404170-ch06.xhtml_rc06-fig-0021) Start the circle in the center of the canvas.

You can also create a variable called `speed` that will move the shape faster if you make the variable a bigger number (see [Figure 6-22](#09_9781119404170-ch06.xhtml_c06-fig-0022)).

`int speed = 5;`

![image](images/9781119404170-fg0622.png)

[FIGURE 6-22:](#09_9781119404170-ch06.xhtml_rc06-fig-0022) Add a new variable called `speed` that is set to 5.

Then change the `xCoordinate` and `yCoordinate` variables by the variable `speed` instead of 1 in the `keyPressed` method (see [Figure 6-23](#09_9781119404170-ch06.xhtml_c06-fig-0023)).

`void keyPressed()`
`{`
`if(key == 'w')`
`{`
`yCoordinate = yCoordinate – speed;`
`}`
`else if(key == 'a')`
`{`
`xCoordinate = xCoordinate – speed;`
`}`
`else if(key == 's')`
`{`
`yCoordinate = yCoordinate + speed;`
`}`
`else if(key == 'd')`
`{`
`xCoordinate = xCoordinate + speed;`
`}`
`}`

![image](images/9781119404170-fg0623.png)

[FIGURE 6-23:](#09_9781119404170-ch06.xhtml_rc06-fig-0023) Change the `xCoordinate` and `yCoordinate` variables by `speed` instead of 1.

Congratulations! You’ve made a shape move with the keyboard and change colors with the mouse! This is really exciting because in the next chapter you’ll take everything you learned to create your very first videogame!

![image](images/c7.png)

The time has come to create your first videogame! This chapter guides you through all the steps needed to make a simple videogame where you have an actual character (not just a shape) that moves around the screen when the player uses the keyboard and collects points!

The game you’ll make in this chapter, and finish making in the next chapter, is kind of like Mario. You have a character that can

*   Move left and right with the A and D keys
*   Jump with the spacebar
*   Run into yellow circles (coins!) to collect them
*   Earn points

## CREATING A SCENE

To start, you need a scene that your character can explore. You may want to draw it on paper first. Here’s what you’ll need:

*   Some kind of ground
*   A colorful sky
*   Something to jump over or on top of

Now that you have an idea of what you want to create in your scene — either with the preceding list or from your drawing — it’s time to get started building your game! Follow these steps:

1.  **Open the Processing application and create a new Sketch file.**
2.  **Create the `setup` method (see** [**Figure 7-1**](#10_9781119404170-ch07.xhtml_c07-fig-0001)**):**

    `void setup()`
    `{`

    `}`

3.  **Create a canvas that is 1,000 x 500 pixels with a light-blue background color (see** [**Figure 7-2**](#10_9781119404170-ch07.xhtml_c07-fig-0002)**):**

    `void setup()`
    `{`
    **`size(1000, 500);`**
    **`background(173, 216, 230);`**
    `}`

4.  **Add a comment above the code you added in Step 3 to keep your code clear for humans (see [Figure 7-3](#10_9781119404170-ch07.xhtml_c07-fig-0003)):**

    `void setup()`
    `{`
    **`//Canvas and sky`**
    `size(1000, 500);`
    `background(173, 216, 230);`
    `}`

5.  **Add a comment and three lines of code to create the grass (see** [**Figure 7-4**](#10_9781119404170-ch07.xhtml_c07-fig-0004)**):**

    `void setup()`
    `{`
    `//Canvas and sky`
    `size(1000, 500);`
    `background(173, 216, 230);`

    **`//Grass`**
    **`stroke(0, 255, 0);`**
    **`fill(0, 255, 0);`**
    **`rect(0, 400, 1000, 500);`**
    `}`

    The grass is essentially a rectangle at the bottom of the screen that is green.

6.  **Add a comment and three lines of code to create a hill (see** [**Figure 7-5**](#10_9781119404170-ch07.xhtml_c07-fig-0005)**):**

    `void setup()`
    `{`
    `//Canvas and sky`
    `size(1000, 500);`
    `background(173, 216, 230);`

    `//Grass`
    `stroke(0, 255, 0);`
    `fill(0, 255, 0);`
    `rect(0, 400, 1000, 500);`

    **`//Hill`**
    **`stroke(165, 42, 42);`**
    **`fill(165, 42, 42);`**
    **`arc(300, 400, 100, 150, PI, TWO_PI);`**
    `}`

    The hill is essentially an arc on top of the grass that is brown.

7.  **Add three lines of code to create a second hill (see** [**Figure 7-6**](#10_9781119404170-ch07.xhtml_c07-fig-0006)**):**

    `void setup()`
    `{`
    `//Canvas and sky`
    `size(1000, 500);`
    `background(173, 216, 230);`

    `//Grass`
    `stroke(0, 255, 0);`
    `fill(0, 255, 0);`
    `rect(0, 400, 1000, 500);`

    **`//Hills`**
    `stroke(165, 42, 42);`
    `fill(165, 42, 42);`
    `arc(300, 400, 100, 150, PI, TWO_PI);`
    **`arc(600, 400, 100, 150, PI, TWO_PI);`**
    `}`

    Make sure you change the comment to say “Hills” instead of “Hill,” because the code below the comment is creating two hills.

![image](images/9781119404170-fg0701.png)

[FIGURE 7-1:](#10_9781119404170-ch07.xhtml_rc07-fig-0001) An empty `setup` method.

![image](images/9781119404170-fg0702.png)

[FIGURE 7-2:](#10_9781119404170-ch07.xhtml_rc07-fig-0002) A canvas that looks like the sky.

![image](images/9781119404170-fg0703.png)

[Figure 7-3:](#10_9781119404170-ch07.xhtml_rc07-fig-0003) Comments added for clarity in code.

![image](images/9781119404170-fg0704.png)

[FIGURE 7-4:](#10_9781119404170-ch07.xhtml_rc07-fig-0004) Code to create a green rectangle that represents grass.

![image](images/9781119404170-fg0705.png)

[FIGURE 7-5:](#10_9781119404170-ch07.xhtml_rc07-fig-0005) Code to create a brown arc that represents a hill.

![image](images/9781119404170-fg0706.png)

[FIGURE 7-6:](#10_9781119404170-ch07.xhtml_rc07-fig-0006) Code to create a second hill.

Great! Now you have a scene for your character to jump around! It’s time to choose and add your character to the scene.

## ADDING A CHARACTER TO YOUR GAME

Now it’s time to choose a character. If you have experience creating characters on the computer, you can create your own. Otherwise, you can find one that you can use for free online.

Follow these steps:

1.  **Open a web browser and go to** [`www.google.com`](http://www.google.com)**.**
2.  **Type** cartoon **in the search bar and click the Images tab (see** [**Figure 7-7**](#10_9781119404170-ch07.xhtml_c07-fig-0007)**).**
3.  **Click Tools and then click License.**
4.  **Choose Labeled for Reuse with Modification (see** [**Figure 7-8**](#10_9781119404170-ch07.xhtml_c07-fig-0008)**).**
5.  **Find a cartoon character that you’d like to use, click the image of the character, and then click View Image (see** [**Figure 7-9**](#10_9781119404170-ch07.xhtml_c07-fig-0009)**).**

    Sometimes, when you click View Image, a new tab opens with the picture and you can right-click it and choose Save Picture As. Other times, when you click View Image, a new tab opens with a website where you can download the image. In this example, a new tab opened to [`www.pixabay.com`](http://www.pixabay.com).

6.  **Click Free Download (see** [**Figure 7-10**](#10_9781119404170-ch07.xhtml_c07-fig-0010)**).**
7.  **Choose a size that you want (see** [**Figure 7-11**](#10_9781119404170-ch07.xhtml_c07-fig-0011)**).**

    You’ll change the size later, so the size you choose doesn’t really matter right now.

8.  **A popup window might appear with a captcha (see** [**Figure 7-12**](#10_9781119404170-ch07.xhtml_c07-fig-0012)**); if it does, fill it out.**
9.  **Open the picture you just downloaded.**

    If you’re using a Mac, open the picture in Preview. (If you double-click the picture file, it will most likely open in Preview automatically.) Choose Tools ⇒ Adjust Size (see [Figure 7-13](#10_9781119404170-ch07.xhtml_c07-fig-0013)).

    If you’re using a PC, open the picture in Paint. Click the Home tab in the menu bar and choose Resize.

10.  **Change the height of the image to 100 pixels (see** [**Figure 7-14**](#10_9781119404170-ch07.xhtml_c07-fig-0014)**).**

    On a Mac, make sure the Scale Proportionally button is checked so that the picture doesn’t get squashed.

    On a PC, the button is Maintain Aspect Ratio instead of Scale Proportionally.

11.  **Choose Processing ⇒ Preferences to find the Processing folder where your projects are saved (see** [**Figure 7-15**](#10_9781119404170-ch07.xhtml_c07-fig-0015)**).**

    At the top of the popup window, you should see the Sketchbook Location, which is where your Processing folder is on your computer (see [Figure 7-16](#10_9781119404170-ch07.xhtml_c07-fig-0016)).

12.  **Save your Sketch project, and name it FirstVideoGame.**
13.  **Open the FirstVideoGame folder and move the image you downloaded into that folder (see** [**Figure 7-17**](#10_9781119404170-ch07.xhtml_c07-fig-0017)**).**
14.  **Add three lines of code to your program to add the character to the scene (see** [**Figure 7-18**](#10_9781119404170-ch07.xhtml_c07-fig-0018)**).**

    First, add the variable that will represent the character. This needs to be added to the top of your program, outside of the `setup` method so that all methods can access it:

    `PImage character;`

    Add one line of code to load the image into the program and one line of code to place the image right on top of the grass on the very left of the screen:

    `character = loadImage("penguin.png");`
    `image(character, 0, 300);`

15.  **Click the Run button to test that your character is loading in the right place.**

![image](images/9781119404170-fg0707.png)

[FIGURE 7-7:](#10_9781119404170-ch07.xhtml_rc07-fig-0007) Search for cartoon images on Google.

![image](images/9781119404170-fg0708.png)

[FIGURE 7-8:](#10_9781119404170-ch07.xhtml_rc07-fig-0008) Look for images you can use and modify.

![image](images/9781119404170-fg0709.png)

[FIGURE 7-9:](#10_9781119404170-ch07.xhtml_rc07-fig-0009) Choose a character.

![image](images/9781119404170-fg0710.png)

[FIGURE 7-10:](#10_9781119404170-ch07.xhtml_rc07-fig-0010) Download the image.

![image](images/9781119404170-fg0711.png)

[FIGURE 7-11:](#10_9781119404170-ch07.xhtml_rc07-fig-0011) Choosing the image size.

![image](images/9781119404170-fg0712.png)

[FIGURE 7-12:](#10_9781119404170-ch07.xhtml_rc07-fig-0012) You might need to fill out a captcha.

![image](images/9781119404170-fg0713.png)

[FIGURE 7-13:](#10_9781119404170-ch07.xhtml_rc07-fig-0013) Open the picture to adjust the size.

![image](images/9781119404170-fg0714.png)

[FIGURE 7-14:](#10_9781119404170-ch07.xhtml_rc07-fig-0014) Adjust the size of the picture to be 100 pixels tall and stay proportional on the width.

![image](images/9781119404170-fg0715.png)

[FIGURE 7-15:](#10_9781119404170-ch07.xhtml_rc07-fig-0015) The Processing Preferences option.

![image](images/9781119404170-fg0716.png)

[FIGURE 7-16:](#10_9781119404170-ch07.xhtml_rc07-fig-0016) The location of your Processing folder.

![image](images/9781119404170-fg0717.png)

[FIGURE 7-17:](#10_9781119404170-ch07.xhtml_rc07-fig-0017) Move the image to the FirstVideoGame folder.

![image](images/9781119404170-fg0718.png)

[FIGURE 7-18:](#10_9781119404170-ch07.xhtml_rc07-fig-0018) Three lines of code to add the character to your scene.

Awesome! Now you have a character in your scene! In the next section, you’ll learn how to move the character around the screen.

## ADDING MOVEMENT TO YOUR VIDEOGAME

Now that you have a scene and a character, it’s time to make it so that your character can move around the scene. Follow these steps:

1.  **Add two variables at the top of your program for the character’s *x*- and *y*-coordinates; initialize them to** `characterX = 0` **and** `characterY = 300` **(see** [**Figure 7-19**](#10_9781119404170-ch07.xhtml_c07-fig-0019)**):**

    `int characterX = 0;`
    `int characterY = 300;`

2.  **Replace the 0 and 300 in the image method call with** `characterX` **and** `character` **(see** [**Figure 7-20**](#10_9781119404170-ch07.xhtml_c07-fig-0020)**):**

    `image(character, characterX, characterY);`

3.  **Add an empty** `keyPressed` **method (see** [**Figure 7-21**](#10_9781119404170-ch07.xhtml_c07-fig-0021)**):**

    `void keyPressed()`
    `{`

    `}`

4.  **Add a conditional statement to the** `keyPressed` **method to check to see if either A or D was pressed (see** [**Figure 7-22**](#10_9781119404170-ch07.xhtml_c07-fig-0022)**):**

    `void keyPressed()`
    `{`
    **`if(key == 'a')`**
    **`{`**

    **`}`**
    **`else if(key == 'd')`**
    **`{`**

    **`}`**
    `}`

5.  **Add code to update the** `characterX` **variable to move left or right depending on if the A or D key was pressed (see** [**Figure 7-23**](#10_9781119404170-ch07.xhtml_c07-fig-0023)**):**

    `void keyPressed()`
    `{`
    `if(key == 'a')`
    `{`
    **`characterX = characterX - 10;`**
    `}`
    `else if(key == 'd')`
    `{`
    **`characterX = characterX + 10;`**
    `}`
    `}`

6.  **Add a `draw` method with a call to the image method continuously so that the character’s location gets updated each time the A or D key is pressed (see** [**Figure 7-24**](#10_9781119404170-ch07.xhtml_c07-fig-0024)**):**

    `void draw()`
    `{`
    `image(character, characterX, characterY);`
    `}`

7.  **Test your code to make sure the character moves left and right when you press A and D (see** [**Figure 7-25**](#10_9781119404170-ch07.xhtml_c07-fig-0025)**).**

![image](images/9781119404170-fg0719.png)

[FIGURE 7-19:](#10_9781119404170-ch07.xhtml_rc07-fig-0019) Two variables to keep track of the character’s location.

![image](images/9781119404170-fg0720.png)

[FIGURE 7-20:](#10_9781119404170-ch07.xhtml_rc07-fig-0020) Update the character’s location using the variables from Step 1.

![image](images/9781119404170-fg0721.png)

[FIGURE 7-21:](#10_9781119404170-ch07.xhtml_rc07-fig-0021) Add a `keyPressed` method.

![image](images/9781119404170-fg0722.png)

[FIGURE 7-22:](#10_9781119404170-ch07.xhtml_rc07-fig-0022) Conditional statement to check if A or D was pressed.

![image](images/9781119404170-fg0723.png)

[FIGURE 7-23:](#10_9781119404170-ch07.xhtml_rc07-fig-0023) Use the variables from Step 1 instead of hard-coded values.

![image](images/9781119404170-fg0724.png)

[FIGURE 7-24:](#10_9781119404170-ch07.xhtml_rc07-fig-0024) Add a `draw` method to always update the location of the character.

![image](images/9781119404170-fg0725.png)

[FIGURE 7-25:](#10_9781119404170-ch07.xhtml_rc07-fig-0025) Watch your character move around your scene.

## UPDATING THE BACKGROUND

As you may have noticed in [Figure 7-25](#10_9781119404170-ch07.xhtml_c07-fig-0025), there is a trail of your character being left behind each time you press A or D. To fix this, you have to redraw the scene each time you redraw the character. Follow these steps:

1.  **Create a new method called** `drawScene` **and move the code for the background color, grass, and two hills into the** drawScene **method (see** [**Figure 7-26**](#10_9781119404170-ch07.xhtml_c07-fig-0026)**):**

    `void drawScene()`
    `{`
    `//Sky`
    `background(173, 216, 230);`

    `//Grass`
    `stroke(0, 255, 0);`
    `fill(0, 255, 0);`
    `rect(0, 400, 1000, 500);`

    `//Hills`
    `stroke(165, 42, 42);`
    `fill(165, 42, 42);`
    `arc(300, 400, 100, 150, PI, TWO_PI);`
    `arc(600, 400, 100, 150, PI, TWO_PI);`
    `}`

    Make sure you update the comments in your code.

2.  **Add a call to the** `drawScene` **method in your** `setup` **method (see** [**Figure 7-27**](#10_9781119404170-ch07.xhtml_c07-fig-0027)**):**

    `void setup()`
    `{`
    `//Canvas`
    `size(1000, 500);`

    **`//Draw the sky, grass, and hills`**
    **`drawScene();`**

    `//Create the character`
    `character = loadImage("penguin.png");`
    `image(character, characterX, characterY);`
    `}`

3.  **Add a call to the** `drawScene` **method in your** `draw` **method (see** [**Figure 7-28**](#10_9781119404170-ch07.xhtml_c07-fig-0028)**):**

    `void draw()`
    `{`
    **`//Redraw the sky, grass, and hills`**
    **`drawScene();`**

    `//Redraw the character`
    `image(character, characterX, characterY);`
    `}`

4.  **Test your code to make sure the scene is still correct (see** [**Figure 7-29**](#10_9781119404170-ch07.xhtml_c07-fig-0029)**).**

    Now when you move your character, it shouldn’t leave a trail.

![image](images/9781119404170-fg0726.png)

[FIGURE 7-26:](#10_9781119404170-ch07.xhtml_rc07-fig-0026) Move the `drawScene` code to a new method.

![image](images/9781119404170-fg0727.png)

[FIGURE 7-27:](#10_9781119404170-ch07.xhtml_rc07-fig-0027) Call `drawScene` from `setup`.

![image](images/9781119404170-fg0728.png)

[FIGURE 7-28:](#10_9781119404170-ch07.xhtml_rc07-fig-0028) Call `drawScene` from `draw`.

![image](images/9781119404170-fg0729.png)

[FIGURE 7-29:](#10_9781119404170-ch07.xhtml_rc07-fig-0029) Test to make sure that your character moves without a trail.

## ADDING GRAVITY TO YOUR VIDEOGAME

One strange aspect of your game right now is that your character just runs right through the hills (see [Figure 7-30](#10_9781119404170-ch07.xhtml_c07-fig-0030)).

![image](images/9781119404170-fg0730.png)

[FIGURE 7-30:](#10_9781119404170-ch07.xhtml_rc07-fig-0030) Your character can run through the hills.

In this section, you’ll make it so that your character can move up when you press the spacebar and will move down automatically. This is essentially simulating gravity. Follow these steps:

1.  **Add a third condition to the conditional statement to change the** `characterY` **variable when the spacebar is pressed (see** [**Figure 7-31**](#10_9781119404170-ch07.xhtml_c07-fig-0031)**):**

    `else if(key == ' ' )`
    `{`
    `characterY = characterY – 5;`
    `}`

2.  **Add a conditional statement to the** `draw` **method to change the** `characterY` **variable to move the character down, as long as it’s still above the grass (see** [**Figure 7-32**](#10_9781119404170-ch07.xhtml_c07-fig-0032)**):**

    `void draw()`
    `{`
    `//Redraw the sky, grass, and hills`
    `drawScene();`

    **`if(characterY < 300)`**
    **`{`**
    **`characterY = characterY + 2;`**
    **`}`**

    `//Redraw the character`
    `image(character, characterX, characterY);`
    `}`

3.  **Adjust the numbers for changing the** `characterY` **variable so that you can jump high and fall slowly (see** [**Figure 7-33**](#10_9781119404170-ch07.xhtml_c07-fig-0033)**):**

    In the condition in the `draw` method that checks if character is less than 300:

    `characterY = characterY + 2;`

    In the condition in the `keyPressed` method that checks if the key that was pressed was the spacebar:

    `characterY = characterY – 100;`

4.  **Adjust the numbers for changing the `characterX` variable so that you can jump over the hills (see [Figure 7-34](#10_9781119404170-ch07.xhtml_c07-fig-0034)):**

    In the condition in the `keyPressed` method that checks if the key that was pressed was the letter A:

    `characterX = characterX – 10;`

    In the condition in the `keyPressed` method that checks if the key that was pressed was the letter D:

    `characterX = characterX + 10;`

![image](images/9781119404170-fg0731.png)

[FIGURE 7-31:](#10_9781119404170-ch07.xhtml_rc07-fig-0031) Move the character up when the spacebar is pressed.

![image](images/9781119404170-fg0732.png)

[FIGURE 7-32:](#10_9781119404170-ch07.xhtml_rc07-fig-0032) Move the character down when it’s above the grass.

![image](images/9781119404170-fg0733.png)

[FIGURE 7-33:](#10_9781119404170-ch07.xhtml_rc07-fig-0033) Make the jumping and gravity more realistic.

![image](images/9781119404170-fg0734.png)

[Figure 7-34:](#10_9781119404170-ch07.xhtml_rc07-fig-0034) Make the movement more realistic now that the character can jump.

Congratulations! You’ve added gravity to your world!

## MAKING LAVA PITS

Making it so that your character can land on the hills is very complex coding, because Processing doesn’t support detecting when a character is touching a certain color. So, instead, you’ll modify your code to replace the hills with lava! Follow these steps:

1.  **In your** `drawScene` **method, modify the code to be upside down and red (see** [**Figure 7-35**](#10_9781119404170-ch07.xhtml_c07-fig-0035)**):**

    `void drawScene()`
    `{`
    `//Sky`
    `background(173, 216, 230);`

    `//Grass`
    `stroke(0, 255, 0);`
    `fill(0, 255, 0);`
    `rect(0, 400, 1000, 500);`

    **`//Lava Pits`**
    **`stroke(255, 0, 0);`**
    **`fill(255, 0, 0);`**
    **`arc(300, 400, 100, 150, 0, PI);`**
    **`arc(600, 400, 100, 150, 0, PI);`**
    `}`

2.  **Add a line of code to the end of your `draw` method to display the value of** `characterX` **as it moves so that you know when it’s touching the lava (see** [**Figure 7-36**](#10_9781119404170-ch07.xhtml_c07-fig-0036)**):**

    `text(characterX, characterX + 60, characterY – 5);`

3.  **Add a conditional statement to the end of your `draw` method that checks to see if the** `characterX` **variable is within the range of the lava pit.**

    To do this, you need to make sure that `characterX` is between the 150 and 310 mark. You can use the `&&` symbol to do this. This symbol means “and,” so you’re checking to see if the value of the `characterX` variable is greater than 150 *and* less than 310\. It’s also a good idea to put this into an extra set of parentheses so that when you add more conditions (in Step 4) the computer knows which comparisons to make together (see [Figure 7-37](#10_9781119404170-ch07.xhtml_c07-fig-0037)):

    `//Check to see if the character hit the lava`
    `if((characterX >= 150 && characterX <= 310))`
    `{`

    `}`

4.  **Add to the conditional statement to check to see if the character variable is within the range of the second lava pit. To do this, you’ll use the || symbol, which means “or” (see** [**Figure 7-38**](#10_9781119404170-ch07.xhtml_c07-fig-0038)**):**

    `if((characterX >= 150 && characterX <= 310) || (characterX >= 450 && characterX <= 610))`

    This line of code means “if `characterX` is between 150 and 310 *or* between 450 and 610.” Notice that there are parentheses around each part of the statement. This is to make sure that you’re checking that the variable is between 150 and 310 *or* between 450 and 610\. Without the parentheses, the code might get read by the computer incorrectly. Adding parentheses ensures that the computer knows exactly what you meant to code.

5.  **Add a call to the text method to have the character say “OW!” when it touches the lava (see** [**Figure 7-39**](#10_9781119404170-ch07.xhtml_c07-fig-0039)**):**

    **`//text(characterX, characterX + 60, characterY – 5);`**

    `//Check to see if the character hit the lava`
    `if((characterX >= 150 && characterX <= 310) || (characterX >= 450 && characterX <= 610))`
    `{`
    **`text("OW!", characterX + 60, characterY – 5);`**
    `}`

    Comment out the code you added in Step 2 to so that it only says something when it touches the lava.

6.  **Add one final condition to your conditional statement to make sure your character only says “OW!” if it’s touching the lava, not jumping above it (see** [**Figure 7-40**](#10_9781119404170-ch07.xhtml_c07-fig-0040)**):**

    `//Check to see if the character hit the lava`
    `if(`**`(`**`(characterX >= 150 && characterX <= 310) || (characterX >= 450 && characterX <= 610)`**`) && characterY >= 300`**`)`
    `{`
    `text("OW!", characterX + 60, characterY – 5);`
    `}`

![image](images/9781119404170-fg0735.png)

[FIGURE 7-35:](#10_9781119404170-ch07.xhtml_rc07-fig-0035) Make the `arc` methods create lava pits instead of hills.

![image](images/9781119404170-fg0736.png)

[FIGURE 7-36:](#10_9781119404170-ch07.xhtml_rc07-fig-0036) Use the `text` method to gather information about the character.

![image](images/9781119404170-fg0737.png)

[FIGURE 7-37:](#10_9781119404170-ch07.xhtml_rc07-fig-0037) Add a conditional statement to test whether the character is touching the first lava.

![image](images/9781119404170-fg0738.png)

[FIGURE 7-38:](#10_9781119404170-ch07.xhtml_rc07-fig-0038) Add to the conditional statement to test whether the character is touching the second lava.

![image](images/9781119404170-fg0739.png)

[FIGURE 7-39:](#10_9781119404170-ch07.xhtml_rc07-fig-0039) Add a call to the text method to say “OW!” when touching lava.

![image](images/9781119404170-fg0740.png)

[FIGURE 7-40:](#10_9781119404170-ch07.xhtml_rc07-fig-0040) Add an additional condition to ensure that the character is on the ground on the lava, not in the air above it.

Congratulations! You’ve made a short game. In this game, the goal is to avoid the lava pits so that your character doesn’t get hurt! In the next chapter, you’ll add points and other characters to your game.

![image](images/c8.png)

This chapter is exciting! Here, you’ll add new characters to your game that aren’t controlled by a player, but instead are controlled by your code! This is what artificial intelligence is, and it’s what this chapter is all about.

## ADDING AN ENEMY TO YOUR VIDEOGAME

The first step to creating artificial intelligence is to get the enemy into your game.

1.  **Open the Processing application and open your FirstVideoGame Sketch that you made in** [**Chapter 7**](#10_9781119404170-ch07.xhtml) **(see** [**Figure 8-1**](#11_9781119404170-ch08.xhtml_c08-fig-0001)**).**
2.  **Find another character online, download it, and save it to your FirstVideoGame folder (see** [**Figure 8-2**](#11_9781119404170-ch08.xhtml_c08-fig-0002)**).**

    You can do this using the technique I introduced in [Chapter 7](#10_9781119404170-ch07.xhtml); just turn to the “[Adding a Character to Your Videogame](#10_9781119404170-ch07.xhtml_c07-sec-0003)” section.

3.  **Add the code needed to create the enemy, place it in your videogame, and control its *x* and *y* location (see** [**Figure 8-3**](#11_9781119404170-ch08.xhtml_c08-fig-0003)**).**

    First, add this code above your `setup` method:

    `PImage enemy;`
    `int enemyX = 200;`
    `int enemyY = 300;`

    Then, add this code at the bottom of your `setup` method:

    `//Create the enemy`
    `enemy = loadImage("crab.png");`
    `image(enemy, enemyX, enemyY);`

4.  **Add a line of code to redraw the enemy every time the draw method is called (see** [**Figure 8-4**](#11_9781119404170-ch08.xhtml_c08-fig-0004)**).**

    This code should be added at the bottom of your `draw` method:

    `//Redraw the enemy`
    `image(enemy, enemyX, enemyY);`

5.  **Test your code to make sure your first enemy is where you want it to be (see** [**Figure 8-5**](#11_9781119404170-ch08.xhtml_c08-fig-0005)**).**
6.  **Adjust the start location of your enemy to be more realistic (see** [**Figure 8-6**](#11_9781119404170-ch08.xhtml_c08-fig-0006)**).**

    Change the code from Step 3 that goes above the `setup` method to:

    `PImage enemy;`
    `int enemyX =` **`350`**`;`
    `int enemyY =` **`325`**`;`

![image](images/9781119404170-fg0801.png)

[FIGURE 8-1:](#11_9781119404170-ch08.xhtml_rc08-fig-0001) The Sketch program from [Chapter 7](#10_9781119404170-ch07.xhtml).

![image](images/9781119404170-fg0802.png)

[FIGURE 8-2:](#11_9781119404170-ch08.xhtml_rc08-fig-0002) Download an enemy image into your FirstVideoGame folder.

![image](images/9781119404170-fg0803.png)

[FIGURE 8-3:](#11_9781119404170-ch08.xhtml_rc08-fig-0003) The code needed to create the enemy on the canvas.

![image](images/9781119404170-fg0804.png)

[FIGURE 8-4:](#11_9781119404170-ch08.xhtml_rc08-fig-0004) The code needed to redraw the enemy to allow it to move.

![image](images/9781119404170-fg0805.png)

[FIGURE 8-5:](#11_9781119404170-ch08.xhtml_rc08-fig-0005) The enemy in your videogame for the first time.

![image](images/9781119404170-fg0806.png)

[FIGURE 8-6:](#11_9781119404170-ch08.xhtml_rc08-fig-0006) Modify the code to place the enemy on the canvas correctly.

Great! Now you have a character and an enemy in your videogame!

## MAKING THE ENEMY MOVE

The next step is to make the enemy move with code, instead of user input (like the keyboard or mouse). To start with, the enemy is going to move between the two lava pits, adding an extra layer of difficulty for the player. To do this, you’re going to use a new variable to keep track of whether the enemy should be moving left (–1) or right (+1).

1.  **Create a new variable called** `enemyMovement` **that is initialized to 1 (see** [**Figure 8-7**](#11_9781119404170-ch08.xhtml_c08-fig-0007)**).**

    Add this line of code above your `setup` method:

    `int enemyMovement = 1;`

2.  **Add a conditional statement to update the** `enemyMovement` **variable depending on which lava pit the enemy reaches (see** [**Figure 8-8**](#11_9781119404170-ch08.xhtml_c08-fig-0008)**).**

    If the enemy gets to the left lava pit (`enemyX = 350`), it should move right (+1). If the enemy gets to the right lava pit (`enemyX = 450`), it should move left (–1).

    This code should be added to the bottom of your `draw` method:

    `//Move enemy`
    `if(enemyX == 350)`
    `{`
    `enemyMovement = 1;`
    `}`
    `else if(enemyX == 450)`
    `{`
    `enemyMovement = -1;`
    `}`

3.  **Update the enemy’s** `enemyX` **by either 1 or –1 depending on Step 2 (see** [**Figure 8-9**](#11_9781119404170-ch08.xhtml_c08-fig-0009)**).**

    This code should be added to the bottom of your `draw` method:

    `enemyX = enemyX + enemyMovement;`

4.  **Test your code by pressing the Run button to make sure the enemy moves back and forth between the two lava pits (see** [**Figure 8-10**](#11_9781119404170-ch08.xhtml_c08-fig-0010)**).**

![image](images/9781119404170-fg0807.png)

[FIGURE 8-7:](#11_9781119404170-ch08.xhtml_rc08-fig-0007) The `enemyMovement` variable to set the direction of the enemy.

![image](images/9781119404170-fg0808.png)

[FIGURE 8-8:](#11_9781119404170-ch08.xhtml_rc08-fig-0008) The conditional to switch directions of the enemy.

![image](images/9781119404170-fg0809.png)

[FIGURE 8-9:](#11_9781119404170-ch08.xhtml_rc08-fig-0009) The code to make your enemy move left or right, depending on the conditional statement in Step 4.

![image](images/9781119404170-fg0810.png)

[FIGURE 8-10:](#11_9781119404170-ch08.xhtml_rc08-fig-0010) The enemy moving between the two lava pits.

Your first artificial intelligence (AI) has been written! That’s all AI really is: code that makes virtual characters move on their own!

## CREATING YOUR OWN JAVA CLASS

Before moving on, you’re going to learn how to create a Java class. A *class* is way of defining a virtual object. The object might have properties (like location and color) and might have methods (like movement). By moving your enemy and character code to classes, you can easily create more enemies and classes that work!

### CREATING AN ENEMY CLASS

The first class you’ll create is the enemy class. That way you can add more enemies if you want, and you can update them all with ease.

1.  **At the bottom of your Sketch file, create a new class called** `Enemy` **(see** [**Figure 8-11**](#11_9781119404170-ch08.xhtml_c08-fig-0011)**).**

    `class Enemy`
    `{`

    `}`

2.  **Move all the** `enemy` **variables from the top of your Sketch file to your** `Enemy` **class (see** [**Figure 8-12**](#11_9781119404170-ch08.xhtml_c08-fig-0012)**).**

    `class Enemy`
    `{`
    **`PImage enemy;`**
    **`int enemyX = 350;`**
    **`int enemyY = 325;`**

    **`int enemyMovement = 1;`**
    `}`

3.  **Create a constructor and move the create enemy code from the setup method to the constructor (see** [**Figure 8-13**](#11_9781119404170-ch08.xhtml_c08-fig-0013)**).**

    A constructor is the creation of the object. Put this code at the bottom of your `Enemy` class.

    `Enemy()`
    `{`
    **`enemy = loadImage("crab.png");`**
    **`image(enemy, enemyX, enemyY);`**
    `}`

4.  **Create a new variable at the top of your Sketch file that is of type** `Enemy` **and named** `enemy1`**. Initialize the** `enemy1` **variable in your** `setup` **method by using the constructor you made in Step 3 (see** [**Figure 8-14**](#11_9781119404170-ch08.xhtml_c08-fig-0014)**).**

    Type this code above your `setup` method, where the code you moved from Step 2 used to be:

    `Enemy enemy1;`

    Then type this code at the bottom of your `setup` method, where the code from Step 3 used to be:

    `//Create the enemy`
    `enemy1 = new Enemy();`

5.  **Create a new method called** `move` **that returns nothing and takes in two integer parameters called** `leftX` **and** `rightX`**. Move the code from the** `draw` **method that moves the enemy into this new method (see** [**Figure 8-15**](#11_9781119404170-ch08.xhtml_c08-fig-0015)**).**

    This method should be inside your `Enemy` class, just below the constructor you wrote in Step 3:

    `void move(int leftX, int rightX)`
    `{`
    `//Redraw the enemy`
    `image(enemy, enemyX, enemyY);`

    `//Move enemy`
    `if(enemyX == 350)`
    `{`
    `enemyMovement = 1;`
    `}`
    `else if(enemyX == 450)`
    `{`
    `enemyMovement = -1;`
    `}`

    `enemyX = enemyX + enemyMovement;`
    `}`

6.  **Update the conditional statement to use the parameters instead of the hard-coded values (see** [**Figure 8-16**](#11_9781119404170-ch08.xhtml_c08-fig-0016)**).**

    `void move(int leftX, int rightX)`
    `{`
    `//Redraw the enemy`
    `image(enemy, enemyX, enemyY);`

    `//Move enemy`
    `if(enemyX ==` **`leftX`**`)`
    `{`
    `enemyMovement = 1;`
    `}`
    `else if(enemyX ==` **`rightX`**`)`
    `{`
    `enemyMovement = -1;`
    `}`

    `enemyX = enemyX + enemyMovement;`
    `}`

7.  **Call the new** `move` **method that you just created in the original** `draw` **method (see** [**Figure 8-17**](#11_9781119404170-ch08.xhtml_c08-fig-0017)**).**

    Make sure you pass the original values that you replaced in Step 6 as the parameters.

    `//Redraw the enemy`
    `enemy1.move(350, 450);`

8.  **Test to make sure your enemy still moves back and forth.**
9.  **Modify your** `Enemy` **constructor to have two parameters, which are the start locations of the enemy (see** [**Figure 8-18**](#11_9781119404170-ch08.xhtml_c08-fig-0018)**).**

    `Enemy(`**`int x, int y`**`)`
    `{`
    **`enemyX = x;`**
    **`enemyY = y;`**
    `enemy = loadImage("crab.png");`
    `image(enemy, enemyX, enemyY);`
    `}`

10.  **Modify the call to the** `Enemy` **constructor to still have the enemy start at the same location (see** [**Figure 8-19**](#11_9781119404170-ch08.xhtml_c08-fig-0019)**).**

    This code is in your `setup` method in the main part of the sketch:

    `//Create the enemy`
    `enemy1 = Enemy(`**`350, 325`**`);`

![image](images/9781119404170-fg0811.png)

[FIGURE 8-11:](#11_9781119404170-ch08.xhtml_rc08-fig-0011) A new empty `Enemy` class.

![image](images/9781119404170-fg0812.png)

[FIGURE 8-12:](#11_9781119404170-ch08.xhtml_rc08-fig-0012) Add `enemy` variables to your `Enemy` class.

![image](images/9781119404170-fg0813.png)

[FIGURE 8-13:](#11_9781119404170-ch08.xhtml_rc08-fig-0013) An `Enemy` constructor.

![image](images/9781119404170-fg0814.png)

[FIGURE 8-14:](#11_9781119404170-ch08.xhtml_rc08-fig-0014) Creating the enemy in the main Sketch coding area.

![image](images/9781119404170-fg0815.png)

[FIGURE 8-15:](#11_9781119404170-ch08.xhtml_rc08-fig-0015) The `move` method to move the enemy.

![image](images/9781119404170-fg0816.png)

[FIGURE 8-16:](#11_9781119404170-ch08.xhtml_rc08-fig-0016) Use the `move` method parameters instead of hard-coded values.

![image](images/9781119404170-fg0817.png)

[FIGURE 8-17:](#11_9781119404170-ch08.xhtml_rc08-fig-0017) Call the `move` method in the `draw` method.

![image](images/9781119404170-fg0818.png)

[FIGURE 8-18:](#11_9781119404170-ch08.xhtml_rc08-fig-0018) Update the constructor to accept parameters.

![image](images/9781119404170-fg0819.png)

[FIGURE 8-19:](#11_9781119404170-ch08.xhtml_rc08-fig-0019) Update the call to the constructor to provide parameters.

### CREATING A SECOND ENEMY

Now that you have a class for your enemies, it’s easy to add a second enemy! Follow these steps:

1.  **Create another** `Enemy` **variable called** `enemy2` **and create a new enemy in your setup method (see** [**Figure 8-20**](#11_9781119404170-ch08.xhtml_c08-fig-0020)**).**

    First, add this code right above your `setup` method:

    `Enemy enemy2;`

    Then add this code at the bottom of your `setup` method:

    `enemy2 = new Enemy(650, 325);`

2.  **Add another** `move` **call in your** `draw` **method, this time moving** `enemy2` **between the second lava pit and the edge of the screen (see** [**Figure 8-21**](#11_9781119404170-ch08.xhtml_c08-fig-0021)**).**

    This code should be added to the very end of your `draw` method:

    `enemy2.move(650, 900);`

3.  **Press the Run button to make sure both enemies are moving between the lava pits and the edges (see** [**Figure 8-22**](#11_9781119404170-ch08.xhtml_c08-fig-0022)**).**

![image](images/9781119404170-fg0820.png)

[FIGURE 8-20:](#11_9781119404170-ch08.xhtml_rc08-fig-0020) A second enemy in the videogame.

![image](images/9781119404170-fg0821.png)

[FIGURE 8-21:](#11_9781119404170-ch08.xhtml_rc08-fig-0021) Moving the second enemy in the videogame.

![image](images/9781119404170-fg0822.png)

[FIGURE 8-22:](#11_9781119404170-ch08.xhtml_rc08-fig-0022) Testing the second enemy.

You now can add as many enemies as you want!

## CREATING A SECOND JAVA CLASS

The second class that you’ll create is the class for the character. Even though you’ll only have one character in this game, creating a second class will help clean up the code by separating the code, making it easier to read.

1.  **Create a new class called** `Character` **(see** [**Figure 8-23**](#11_9781119404170-ch08.xhtml_c08-fig-0023)**).**

    Add this code to the bottom of your Sketch file, under the `Enemy` class:

    `class Character`
    `{`

    `}`

2.  **Create a constructor like you did in the section called “**[**Creating an Enemy class**](#11_9781119404170-ch08.xhtml_c08-sec-0005)**,” where you create the character and initialize its starting location (see** [**Figure 8-24**](#11_9781119404170-ch08.xhtml_c08-fig-0024)**).**

    `class Character`
    `{`
    **`PImage character;`**
    **`int characterX;`**
    **`int characterY;`**

    **`Character(int x, int y)`**
    **`{`**
    **`characterX = x;`**
    **`characterY = y;`**
    **`character = loadImage("penguin.png");`**
    **`image(character, characterX, characterY);`**
    **`}`**
    `}`

3.  **Call the** `Character` **constructor from the** `setup` **method (see** [**Figure 8-25**](#11_9781119404170-ch08.xhtml_c08-fig-0025)**).**

    First, add this line of code to the very top of your Sketch file:

    `Character character;`

    Then add this code to the middle of your `setup` method:

    `void setup()`
    `{`
    `//Canvas`
    `size(1000, 500);`

    `//Draw the sky, grass, and hills`
    `drawScene();`

    **`//Create the character`**
    **`character = new Character(0, 300);`**

    `//Create the enemies`
    `enemy1 = new Enemy(350, 325);`
    `enemy2 = new Enemy(650, 325);`
    `}`

4.  **Create a** `move` **method in the** `Character` **class and move all the character movement code from the** `draw` **method to the new** `move` **method (see** [**Figure 8-26**](#11_9781119404170-ch08.xhtml_c08-fig-0026)**).**

    `void move()`
    `{`
    `if(characterY < 300)`
    `{`
    `characterY = characterY + 1;`
    `}`

    `//Redraw the character`
    `image(character, characterX, characterY);`

    `//text(characterX, characterX + 60, characterY – 5);`

    `//Check to see if the character hit the lava`
    `if(((characterX >= 150 && characterX <= 310)`
    `|| (characterX >= 450 && characterX <= 610))`
    `&& characterY >= 300)`
    `{`
    `text("OW!", characterX + 60, characterY – 5);`
    `}`
    `}`

5.  **Call the** `move` **method from the** `draw` **method (see** [**Figure 8-27**](#11_9781119404170-ch08.xhtml_c08-fig-0027)**).**

    This code should be right above where you called the enemy `move` methods earlier in this chapter:

    `//Redraw the character`
    `character.move();`

6.  **Create a** `keyPressed` **method in the** `Character` **class and move all the code from the original** `keyPresssed` **method into the new one (see** [**Figure 8-28**](#11_9781119404170-ch08.xhtml_c08-fig-0028)**).**

    Inside of the `Character` class:

    `void keyPressed()`
    `{`
    `if(key == 'a')`
    `{`
    `characterX = characterX – 10;`
    `}`
    `else if(key == 'd')`
    `{`
    `characterX = characterX + 10;`
    `}`
    `else if(key == ' ')`
    `{`
    `characterY = characterY – 100;`
    `}`
    `}`

7.  **Call the new** `keyPressed` **method from the original** `keyPressed` **method (see** [**Figure 8-29**](#11_9781119404170-ch08.xhtml_c08-fig-0029)**).**

    This code should be typed in the `keyPressed` method in the main sketch:

    `void keyPressed()`
    `{`
    **`character.keyPressed();`**
    `}`

8.  **Test to make sure your character still moves when you press A or D, still jumps when you press the spacebar, still falls when it’s above the ground, and still says “OW!” when it touches lava.**

![image](images/9781119404170-fg0823.png)

[FIGURE 8-23:](#11_9781119404170-ch08.xhtml_rc08-fig-0023) A new `Character` class.

![image](images/9781119404170-fg0824.png)

[FIGURE 8-24:](#11_9781119404170-ch08.xhtml_rc08-fig-0024) Create a constructor to create the character.

![image](images/9781119404170-fg0825.png)

[FIGURE 8-25:](#11_9781119404170-ch08.xhtml_rc08-fig-0025) Create the character in the `setup` method.

![image](images/9781119404170-fg0826.png)

[FIGURE 8-26:](#11_9781119404170-ch08.xhtml_rc08-fig-0026) The new `move` method in the `Character` class.

![image](images/9781119404170-fg0827.png)

[FIGURE 8-27:](#11_9781119404170-ch08.xhtml_rc08-fig-0027) Call the new `move` method.

![image](images/9781119404170-fg0828.png)

[FIGURE 8-28:](#11_9781119404170-ch08.xhtml_rc08-fig-0028) The `keyPressed` method in the new `Character` class.

![image](images/9781119404170-fg0829.png)

[FIGURE 8-29:](#11_9781119404170-ch08.xhtml_rc08-fig-0029) Call the `Character` `keyPressed` from the original `keyPressed`.

## ADDING HEALTH TO YOUR CHARACTER

Now that you have a working game, the only thing you need to do is to add a variable that keeps track of health. This will make your players want to avoid the lava and enemies. Follow these steps:

1.  **Add a variable at the top of your** `Character` **class called** `health` **that has a type integer and a value 100 (see** [**Figure 8-30**](#11_9781119404170-ch08.xhtml_c08-fig-0030)**).**

    `int health = 100;`

2.  **Create a method called** `updateHealth` **that doesn’t return a value and doesn’t have any parameters (see** [**Figure 8-31**](#11_9781119404170-ch08.xhtml_c08-fig-0031)**).**

    The method will reduce the health by 1 point.

    `void updateHealth()`
    `{`
    `health = health - 1;`
    `}`

3.  **Add a line of code to your** `Character` `move` **method that calls** `updateHealth` **every time the character touches the lava (see** [**Figure 8-32**](#11_9781119404170-ch08.xhtml_c08-fig-0032)**).**

    This line of code should go inside the conditional statement at the bottom of your `move` method:

    `text("OW!", characterX + 60, characterY – 5);`
    **`updateHealth();`**

4.  **Create a method called** `getHealth` **that returns an integer (the health) and does not have any parameters (see** [**Figure 8-33**](#11_9781119404170-ch08.xhtml_c08-fig-0033)**).**

    You can type this code underneath your `Character` constructor:

    `int getHealth()`
    `{`
    `return health;`
    `}`

5.  **Make sure the** `drawScene` **method is called last in your original setup method (see** [**Figure 8-34**](#11_9781119404170-ch08.xhtml_c08-fig-0034)**).**

    `void setup()`
    `{`
    `//Canvas`
    `size(1000, 500);`

    `//Create the character`
    `character = new Character(0, 300);`

    `//Create the enemies`
    `enemy1 = new Enemy(350, 325);`
    `enemy2 = new Enemy(650, 325);`

    **`//Draw the sky, grass, and hills`**
    **`drawScene();`**
    `}`

    This is important because the character must be created first so that you can access the character variable to display the health.

6.  **Add text (size 32 font) to your canvas to always display the health of the character (see** [**Figure 8-35**](#11_9781119404170-ch08.xhtml_c08-fig-0035)**).**

    This code should be added to the bottom of your `drawScene` method:

    `//Character’s Health`
    `textSize(32);`
    `text(character.getHealth(), 900, 50);`

![image](images/9781119404170-fg0830.png)

[FIGURE 8-30:](#11_9781119404170-ch08.xhtml_rc08-fig-0030) A new variable to keep track of health.

![image](images/9781119404170-fg0831.png)

[FIGURE 8-31:](#11_9781119404170-ch08.xhtml_rc08-fig-0031) A new method to update the health.

![image](images/9781119404170-fg0832.png)

[FIGURE 8-32:](#11_9781119404170-ch08.xhtml_rc08-fig-0032) Update the health when the character touches lava.

![image](images/9781119404170-fg0833.png)

[FIGURE 8-33:](#11_9781119404170-ch08.xhtml_rc08-fig-0033) A new method to access the health of the character.

![image](images/9781119404170-fg0834.png)

[FIGURE 8-34:](#11_9781119404170-ch08.xhtml_rc08-fig-0034) Updating the `setup` method to ensure the character is created before you try to access the character’s health.

![image](images/9781119404170-fg0835.png)

[FIGURE 8-35:](#11_9781119404170-ch08.xhtml_rc08-fig-0035) Code added to the `drawScene` method to display the health.

## GIVING YOUR ENEMIES COLLISION DETECTION

The final step to making this videogame is to add collision detection to your enemies. This means that when the enemy touches the character, your code has to detect that and do something (for example, update the health). Follow these steps:

1.  **Create a new method in your** `Enemy` **class called** `collidedWith` **that returns a Boolean (true or false) and has four integer parameters (**`x`**,** `y`**,** `x2`**, and** `y2`**), as shown in** [**Figure 8-36**](#11_9781119404170-ch08.xhtml_c08-fig-0036)**.**

    These four parameters will eventually have the values of the character’s location.

    You can add this code underneath your `Enemy` constructor:

    `boolean collidedWith(int x, int y, int x2, int y2)`
    `{`
    `return false;`
    `}`

2.  **Add a conditional statement to see if the location of the enemy is anywhere within the square of the character (see** [**Figure 8-37**](#11_9781119404170-ch08.xhtml_c08-fig-0037)**).**

    `boolean collidedWith(int x, int y, int x2, int y2)`
    `{`
    **`if(enemyX >= x && enemyX <= x2 && enemyY >= y && enemyY <= y2)`**
    **`{`**
    **`return true;`**
    **`}`**
    `return false;`
    `}`

3.  **Add four methods to your** `Character` **class to return the *x* and *y* coordinates of the start of the character and the *x* and *y* coordinates of the end of the character (see** [**Figure 8-38**](#11_9781119404170-ch08.xhtml_c08-fig-0038)**).**

    Add these methods underneath the `Character` constructor:

    `int getX()`
    `{`
    `return characterX - (character.width/2);`
    `}`
    `int getY()`
    `{`
    `return characterY;`
    `}`
    `int getX2()`
    `{`
    `return characterX + (character.width/2);`
    `}`
    `int getY2()`
    `{`
    `return characterY + character.height;`
    `}`

4.  **Add a conditional to the** `draw` **method to check to see if either enemy is colliding with the character; if it is, call the** updateHealth **method (see** [**Figure 8-39**](#11_9781119404170-ch08.xhtml_c08-fig-0039)**).**

    Add this conditional to the bottom of the `draw` method:

    `if(enemy1.collidedWith(character.getX(), character.`
    `getY(), character.getX2(), character.getY2()))`
    `{`
    `character.updateHealth();`
    `}`
    `else if(enemy2.collidedWith(character.getX(),`
    `character.getY(), character.getX2(), character.`
    `getY2()))`
    `{`
    `character.updateHealth();`
    `}`

5.  **Test your code to make sure it works. When your character touches lava or an enemy, it should start to lose health (see** [**Figure 8-40**](#11_9781119404170-ch08.xhtml_c08-fig-0040)**).**

![image](images/9781119404170-fg0836.png)

[FIGURE 8-36:](#11_9781119404170-ch08.xhtml_rc08-fig-0036) The new `collidedWith` method.

![image](images/9781119404170-fg0837.png)

[FIGURE 8-37:](#11_9781119404170-ch08.xhtml_rc08-fig-0037) A conditional to check to see if the enemy is within the bounds of the character.

![image](images/9781119404170-fg0838.png)

[FIGURE 8-38:](#11_9781119404170-ch08.xhtml_rc08-fig-0038) The four methods to determine the bounds of the character.

![image](images/9781119404170-fg0839.png)

[FIGURE 8-39:](#11_9781119404170-ch08.xhtml_rc08-fig-0039) The conditional statement that will update the health if the character collides with either enemy.

![image](images/9781119404170-fg0840.png)

[FIGURE 8-40:](#11_9781119404170-ch08.xhtml_rc08-fig-0040) The final game in action.

You’ve just made a game! The goal of the game is to try to get the character to the edge before losing all its health points! In the next chapter, you’ll build a game that is very similar to this one. Don’t forget: You can always refer back to earlier chapters to get help if you get stuck.

![image](images/c9.png)

Before you get started, you’re going to play Flappy Bird online to get an idea of what you need to do in order to re-create your own version of this game, called Ninja Bird.

1.  **Open a web browser and go to** [`http://flappybird.io`](http://flappybird.io)**.**

    As the page loads, you may see an ad (see [Figure 9-1](#12_9781119404170-ch09.xhtml_c09-fig-0001)). Wait until you can click the Skip button, and then press Skip.

2.  **You should see a Flappy Bird game playing in your browser (see** [**Figure 9-2**](#12_9781119404170-ch09.xhtml_c09-fig-0002)**).**
3.  **Click the Flappy Bird to start the game.**

    As you play, you’ll have to keep clicking your mouse to keep the bird up. Notice the menu that pops up when you hit a pipe (see [Figure 9-3](#12_9781119404170-ch09.xhtml_c09-fig-0003)).

4.  **Play the game a few times to get a feeling for how everything works.**

    To keep playing, you can click the Restart button.

5.  **Notice that when you play, the game keeps track of your current score and your highest score (see** [**Figure 9-4**](#12_9781119404170-ch09.xhtml_c09-fig-0004)**).**

![image](images/9781119404170-fg0901.png)

[FIGURE 9-1:](#12_9781119404170-ch09.xhtml_rc09-fig-0001) An example of an ad you may see before playing Flappy Bird.

![image](images/9781119404170-fg0902.png)

[FIGURE 9-2:](#12_9781119404170-ch09.xhtml_rc09-fig-0002) An in-browser Flappy Bird game.

![image](images/9781119404170-fg0903.png)

[FIGURE 9-3:](#12_9781119404170-ch09.xhtml_rc09-fig-0003) The menu that appears when you lose the first time.

![image](images/9781119404170-fg0904.png)

[FIGURE 9-4:](#12_9781119404170-ch09.xhtml_rc09-fig-0004) This game keeps track of your highest and most recent scores.

## MAKING SENSE OF THE FLAPPY BIRD CODE

When you have been writing code for a long time, you’ll be able to start using new technology and guessing what kind of code had to be written to make that software work. Even though you’re just starting out, you’re going to practice doing that in this book right now.

### THE START SCREEN

The first thing to notice about the Flappy Bird game that you’re playing is the start screen (see [Figure 9-5](#12_9781119404170-ch09.xhtml_c09-fig-0005)). There are three parts to it:

*   **The background:** The background has a blue background, an image of clouds, buildings, and trees; a brown ground; and a green grass that seems to be moving.
*   **The bird:** The next part is the bird itself. The bird is a simple little image, but it has an animation that makes it look like it’s flapping its wings. The bird also is bouncing up and down.
*   **The score:** The last part is a big white number with a black outline that represents the score.

![image](images/9781119404170-fg0905.png)

[FIGURE 9-5:](#12_9781119404170-ch09.xhtml_rc09-fig-0005) The Flappy Bird start screen.

From the work that you’ve done so far in this book, creating all that should be pretty simple. What’s complicated is making the grass look like it’s moving and making the bird’s wing flap. Those are pieces of code that you’ll have to research how to make happen. In the first versions of your game, they won’t move.

### THE GAMEPLAY SCREEN

When you start to play the game, the interface changes slightly, and there are four parts to pay attention to (see [Figure 9-6](#12_9781119404170-ch09.xhtml_c09-fig-0006)):

*   **The background:** The background is the same as the start screen.
*   **The bird:** The bird looks the same, but now it falls unless the player clicks it. When the player clicks the bird, it moves up. If the bird hits a pipe, it automatically falls to the ground, face first.
*   **The score:** The score is the same style as the start screen, but updates by 1 each time the bird successfully gets through a set of pipes.
*   **The pipes:** There are at most four pipes on the screen at a time. Two of them are coming from the bottom of the screen going up and two of them are directly above those bottom pipes, coming from the top of the screen going down. Whenever a new set of pipes appears on the right side of the screen, the opening between them is in a different position on the vertical axis. The opening between the pipes seems to always be the same number of pixels.

![image](images/9781119404170-fg0906.png)

[FIGURE 9-6:](#12_9781119404170-ch09.xhtml_rc09-fig-0006) The Flappy Bird game during gameplay.

You’ve already done a lot of the coding in this book to make all of this happen. The one part that might be difficult is making the opening between the pipes be in a random spot each time a new set of pipes is shown coming from the right side of the screen.

### THE END SCREEN

When you lose the game, the interface changes one last time. In this case, there are three parts to pay attention to (see [Figure 9-7](#12_9781119404170-ch09.xhtml_c09-fig-0007)):

*   **The background:** The background is exactly the same as the gameplay screen. The only difference is that now the grass is not moving.
*   **The bird and pipes:** The bird and pipes are left in the exact same location as they were in when the gameplay screen finished. They aren’t moving.
*   **The score:** The score now has a square around it with the score of the game that was just played and the best score over all of the games that have been played.
*   **The buttons:** In this version, there are three buttons: Restart, Share, and Add to Leaderboard.

![image](images/9781119404170-fg0907.png)

[FIGURE 9-7:](#12_9781119404170-ch09.xhtml_rc09-fig-0007) The end screen, shown when you lose a game.

Because your game is not on the Internet, but instead just on your computer, you can ignore the Share and Add to Leaderboard buttons. The button you’ll need to figure out is the Restart button. When pressed, this button moves the pipes back to the start, puts the bird back into the sky, makes the buttons disappear, makes the grass start moving again, and resets the Score display.

## OUTLINING YOUR NINJA BIRD

Now that you have had a chance to play a version of Flappy Bird and try to decipher what is happening in the code, it’s time to plan out how you want your Ninja Bird to work.

*   **The background:** This part should be straightforward, because you’ve created shapes and images on your canvas earlier in this book. The tricky part here will be making the grass move, but this is optional.
*   **The bird:** Your bird needs to always be falling, unless the user does something, like click the mouse or a certain key on the keyboard. The bird needs to have an image (probably of a bird) so that it isn’t just a dot. Optionally, the wing on the bird should be moving.
*   **The pipes:** This is an interesting one. Even though when you play it looks like the bird is flying through an infinite number of pipes, if you play long enough, you’ll notice that there are only ever two sets of pipes on the screen at once. What is actually happening is the two sets of pipes are moving from the right side of the screen to the left side of the screen. When they get to the left side, they turn invisible, move back to the right, and turn visible again! It’s a clever way to make a game look like there are infinite items when there are really only a couple! The trick here is that you’ll have to figure out how to make sure the gap between the pipes is in a random place each time it comes back to the right.
*   **The score:** Just like in the Flappy Bird game you played earlier, you should have a score variable that keeps track of how many pipes the bird has successfully flown through. You should have a second variable that keeps track of the highest number of pipes that the bird has successfully flown through as well. The current score should be displayed when playing, and both scores should be displayed once the player loses.
*   **The buttons:** For your Ninja Bird game, you should have one button that restarts the game. When the game is restarted, you will have to change the bird (location), the pipes (location), and the two score variables (reset the current score to 0 and the highest score should be updated if the current score is higher than the highest score).

## DESIGNING YOUR JAVA CLASSES

Now that you have an idea of how your game will play out, it’s time to plan out your Java classes so that you know what variables and methods you need to write. In this section, you’ll add comments to a new Sketch file to outline what you want to code. This strategy is one that software engineers sometimes use when coding complicated programs. By adding the comments first, you can make sure you don’t forget anything when you write your code. It also helps with debugging (finding errors in your code) because you can compare what you wanted to do (the comments) with what you actually do (the code).

Open the Processing application and create a new Sketch file. Save the file right away and call it NinjaBird.

### MAIN CLASS

Even though you don’t have to add the word *class* like you do for the other classes you’ll make, your first class is the Sketch file that you start with, which has the `setup` and `draw` methods.

In this class, you’ll want to

*   Keep track of both score variables.
*   Draw the background.
*   Display the buttons when it’s time to do so.
*   Keep track of the state of the game (start, playing, end).

In your empty Sketch file, type the following code to create the comments and empty method signatures for the code you’ll need for your main class. (See [Figure 9-8](#12_9781119404170-ch09.xhtml_c09-fig-0008) as a reference for where the code is in your file.)

`//Two variables that keep track of current and best`
`//score`

`//Variable that keeps track of the state of the game`

`//Method to set up the background`
`void setup()`
`{`

`}`

`//Method to constantly draw the bird, pipes, and`
`//score and to show the buttons when it's time`
`void draw()`
`{`

`}`

![image](images/9781119404170-fg0908.png)

[FIGURE 9-8:](#12_9781119404170-ch09.xhtml_rc09-fig-0008) The setup of your main class.

### BIRD CLASS

The next class to build is the `Bird` class. To make it easier to keep track of all your code, you’re going to write the class in a separate file within your program. Follow these steps:

1.  **Click the down arrow next to the NinjaBird tab in your Sketch File and choose New Tab (see** [**Figure 9-9**](#12_9781119404170-ch09.xhtml_c09-fig-0009)**).**
2.  **Name the new file Bird, with a capital B (see** [**Figure 9-10**](#12_9781119404170-ch09.xhtml_c09-fig-0010)**).**

    You should now see an empty sketch tab called Bird next to the tab called NinjaBird (see [Figure 9-11](#12_9781119404170-ch09.xhtml_c09-fig-0011)).

![image](images/9781119404170-fg0909.png)

[FIGURE 9-9:](#12_9781119404170-ch09.xhtml_rc09-fig-0009) Create a new tab by clicking the arrow.

![image](images/9781119404170-fg0910.png)

[FIGURE 9-10:](#12_9781119404170-ch09.xhtml_rc09-fig-0010) Name the new file Bird.

![image](images/9781119404170-fg0911.png)

[FIGURE 9-11:](#12_9781119404170-ch09.xhtml_rc09-fig-0011) You now have two classes: NinjaBird and Bird.

In this class, you’ll want to

*   Create an image of the bird.
*   Create a constructor for creating the actual bird on the canvas.
*   Know the location of the bird.
*   Update the location of the bird.
*   Know when the mouse is clicked.
*   Have an end sequence for the bird when it should hit the floor.

In your empty Bird sketch file, type the following code. Look at [Figure 9-12](#12_9781119404170-ch09.xhtml_c09-fig-0012) as a reference for where the code should go.

`class Bird`
`{`
`//Variable for the image of the bird`

`//Two variables for the location of the bird`

`//Constructor to create the bird`
`Bird()`
`{`

`}`

`//Method to move the bird`
`void move()`
`{`

`}`

`//Method that is called when the mouse is clicked`
`void mouseClicked()`
`{`

`}`

`//Method to make the bird hit the floor`
`void endSequence()`
`{`

`}`
`}`

![image](images/9781119404170-fg0912.png)

[FIGURE 9-12:](#12_9781119404170-ch09.xhtml_rc09-fig-0012) The code outline for the `Bird` class.

### PIPE CLASS

Finally, the last class you need to outline is the `Pipe` class. You need to create another class, in another tab, to complete this. Follow the same process as you did in the preceding section. You should have three tabs in your programming environment now: NinjaBird, Bird, and Pipes (see [Figure 9-13](#12_9781119404170-ch09.xhtml_c09-fig-0013)).

![image](images/9781119404170-fg0913.png)

[FIGURE 9-13:](#12_9781119404170-ch09.xhtml_rc09-fig-0013) The three tabs for your three classes.

In this class, you’ll want to

*   Create an image for the pipes.
*   Create a constructor for two pipes.
*   Draw two pipes, one of them upside down.
*   Know the location of all the pipes.
*   Update the location of the pipes.
*   Have an end sequence to stop the pipes.

In your empty Pipes sketch file, type the following code. Look at [Figure 9-14](#12_9781119404170-ch09.xhtml_c09-fig-0014) as a reference for where the code should go.

`class Pipes`
`{`
`//Variable for the image of the pipes`

`//Two variables for the location of the pipes`

`//Constructor to create the pipes`
`Pipes()`
`{`

`}`

`//Method to move the pipes`
`void move()`
`{`

`}`

`//Method to make the pipes stop when the bird hits`
`//them`
`void endSequence()`
`{`

`}`
`}`

![image](images/9781119404170-fg0914.png)

[FIGURE 9-14:](#12_9781119404170-ch09.xhtml_rc09-fig-0014) The outline for your Pipes class.

Make sure you save your code before you close the Processing application. In the next chapter, you’re going to plan out all your methods.

![image](images/c10.png)

In [Chapter 9](#12_9781119404170-ch09.xhtml), you did a lot of planning for your Ninja Bird game. You created and outlined your three classes and thought about the variables you might need. As a challenge, in this chapter, you’re going to write the code within your methods, but as English comments instead of code. Just like in [Chapter 9](#12_9781119404170-ch09.xhtml), it can be useful to understand what you’re planning on doing before you do it.

## DESIGNING YOUR SETUP METHOD

In your `setup` method, you’ll need to:

*   Create the canvas.
*   Color the canvas.
*   Create the ground.
*   Create the background of the city.
*   Create the bird.
*   Create at least two sets of pipes.

You can add these comments into your code. Just like before, the comments and code you’ll add will be written in this book, and the image will help you see where the code should be added. Follow these steps:

1.  **Add a comment where you want to create the 800-x-800-pixel canvas (see** [**Figure 10-1**](#13_9781119404170-ch10.xhtml_c10-fig-0001)**):**

    `//Create an 800-x-800-pixel canvas`

2.  **Add where you want to turn the canvas blue (see** [**Figure 10-2**](#13_9781119404170-ch10.xhtml_c10-fig-0002)**):**

    `//Turn the background of the canvas blue`

3.  **Add where you want to create the ground (see** [**Figure 10-3**](#13_9781119404170-ch10.xhtml_c10-fig-0003)**):**

    `//Create a green rectangle that spans across the`
    `//bottom of the canvas`

4.  **Add where you want to display the city image (see** [**Figure 10-4**](#13_9781119404170-ch10.xhtml_c10-fig-0004)**):**

    `//Create an image that represents the city`

5.  **Above your** `setup` **method, create the three variables for your bird and two sets of pipes (see** [**Figure 10-5**](#13_9781119404170-ch10.xhtml_c10-fig-0005)**):**

    `//Variables for the bird and two sets of pipes`

6.  **Add where you want to call the constructor for the bird and two sets of pipes (see** [**Figure 10-6**](#13_9781119404170-ch10.xhtml_c10-fig-0006)**):**

    `//Call the constructors for the bird and two sets of`
    `//pipes`

![image](images/9781119404170-fg1001.png)

[FIGURE 10-1:](#13_9781119404170-ch10.xhtml_rc10-fig-0001) Where you’ll create the 800-x-800-pixel canvas.

![image](images/9781119404170-fg1002.png)

[FIGURE 10-2:](#13_9781119404170-ch10.xhtml_rc10-fig-0002) Where you’ll turn the canvas blue.

![image](images/9781119404170-fg1003.png)

[FIGURE 10-3:](#13_9781119404170-ch10.xhtml_rc10-fig-0003) Where you’ll create the grass.

![image](images/9781119404170-fg1004.png)

[FIGURE 10-4:](#13_9781119404170-ch10.xhtml_rc10-fig-0004) Where you’ll create the city.

![image](images/9781119404170-fg1005.png)

[FIGURE 10-5:](#13_9781119404170-ch10.xhtml_rc10-fig-0005) Where to add the three variables above your `setup` method.

![image](images/9781119404170-fg1006.png)

[FIGURE 10-6:](#13_9781119404170-ch10.xhtml_rc10-fig-0006) Where to call the constructor for the bird and two sets of pipes.

Awesome! Now you have your entire `setup` method planned out. In the next chapter, when you go to add the code, it should be really simple!

## DESIGNING YOUR DRAW METHOD

The next method to design is your `draw` method. This one is a little more intricate because you’ll want to

*   Redraw the entire background.
*   Redraw the bird with the updated location.
*   Redraw the two sets of pipes with their updated location.
*   Detect if the bird has hit any pipes.

By designing our code with comments first, you can already see that a lot of what’s in this method you’ve already done in the `setup` method. This means you’ll want to create a method that gets called from both `setup` and `draw`, so that you don’t have to write the code twice! Follow these steps:

1.  **Write a new method called** `drawScene` **that doesn’t return anything and doesn’t take any parameters (see** [**Figure 10-7**](#13_9781119404170-ch10.xhtml_c10-fig-0007)**):**

    `//Method to draw the background color, grass, and`
    `//city image`
    `void drawScene()`
    `{`

    `}`

2.  **Move the comments to turn the background blue, draw the grass, and draw the image of the city from the** `setup` **method into the** `drawScene` **method (see** [**Figure 10-8**](#13_9781119404170-ch10.xhtml_c10-fig-0008)**):**

    `//Turn the background of the canvas blue`

    `//Create a green rectangle that spans across the`
    `//bottom of the canvas`

    `//Create an image that represents the city`

3.  **Call the** `drawScene` **method from the** `setup` **method where the lines of code you moved in Step 2 used to be (see** [**Figure 10-9**](#13_9781119404170-ch10.xhtml_c10-fig-0009)**):**

    `//Call the drawScene method`

4.  **Call the** `drawScene` **method from inside the** `draw` **method as well (see** [**Figure 10-10**](#13_9781119404170-ch10.xhtml_c10-fig-0010)**).**

    `//Call the drawScene method`

5.  **Call the bird** `move` **method from inside the** `draw` **method (see** [**Figure 10-11**](#13_9781119404170-ch10.xhtml_c10-fig-0011)**):**

    `//Call the bird move method to redraw the bird`

6.  **Call the pipes** `move` **method for both sets of pipes from inside the** `draw` **method (see** [**Figure 10-12**](#13_9781119404170-ch10.xhtml_c10-fig-0012)**):**

    `//Call the pipes move method for both sets of pipes`
    `//to redraw the pipes`

7.  **Add a conditional statement to check to see if the bird has hit any of the pipes (see** [**Figure 10-13**](#13_9781119404170-ch10.xhtml_c10-fig-0013)**):**

    `//Conditional statement to check if the bird has hit`
    `//the pipes`

![image](images/9781119404170-fg1007.png)

[FIGURE 10-7:](#13_9781119404170-ch10.xhtml_rc10-fig-0007) Where the new `drawScene` method should be.

![image](images/9781119404170-fg1008.png)

[FIGURE 10-8:](#13_9781119404170-ch10.xhtml_rc10-fig-0008) Where the code to draw the scene should be moved to (from `setup` to `drawScene`).

![image](images/9781119404170-fg1009.png)

[FIGURE 10-9:](#13_9781119404170-ch10.xhtml_rc10-fig-0009) Where the `drawScene` method should be called from in the setup method.

![image](images/9781119404170-fg1010.png)

[FIGURE 10-10:](#13_9781119404170-ch10.xhtml_rc10-fig-0010) Where the `drawScene` method should be called from in the `draw` method.

![image](images/9781119404170-fg1011.png)

[FIGURE 10-11:](#13_9781119404170-ch10.xhtml_rc10-fig-0011) Where the bird `move` method should be called from in the `draw` method.

![image](images/9781119404170-fg1012.png)

[FIGURE 10-12:](#13_9781119404170-ch10.xhtml_rc10-fig-0012) Where the pipes `move` method should be called from in the `draw` method.

![image](images/9781119404170-fg1013.png)

[FIGURE 10-13:](#13_9781119404170-ch10.xhtml_rc10-fig-0013) Where the conditional statement should go to check if the bird has hit the pipes in the `draw` method.

Wow! That is going to be a lot of code. The one piece you’re still missing to make this complete is to test whether the bird has hit any of the pipes.

## DESIGNING YOUR COLLISION METHODS

The last step of this chapter is to design your collision method. This method will return a Boolean value (true or false) if the bird touches one of the pipes. Follow these steps:

1.  **Create a new method called** `checkCollision` **that returns a Boolean and doesn’t take any parameters (see** [**Figure 10-14**](#13_9781119404170-ch10.xhtml_c10-fig-0014)**).**

    `//Method to check to see if the bird has hit any of`
    `//the pipes`
    `boolean checkCollision()`
    `{`

    `return false;`
    `}`

2.  **Get the location, width, and height of the bird (see** [**Figure 10-15**](#13_9781119404170-ch10.xhtml_c10-fig-0015)**).**

    `//Get the location, width, and height of the bird`

3.  **Get the location, width, and height of the both sets of pipes (see** [**Figure 10-16**](#13_9781119404170-ch10.xhtml_c10-fig-0016)**).**

    `// Get the location, width, and height of both sets`
    `//of pipes`

4.  **Add a conditional statement to check to see if the bird is within the same location as any of the pipes (see** [**Figure 10-17**](#13_9781119404170-ch10.xhtml_c10-fig-0017)**).**

    `//Conditional statement to check if the bird is in`
    `//the same location as the pipes`

![image](images/9781119404170-fg1014.png)

[FIGURE 10-14:](#13_9781119404170-ch10.xhtml_rc10-fig-0014) Where the new `checkCollision` method should be written.

![image](images/9781119404170-fg1015.png)

[FIGURE 10-15:](#13_9781119404170-ch10.xhtml_rc10-fig-0015) Where the location, width, and height of the bird should be retrieved in the new `checkCollision` method.

![image](images/9781119404170-fg1016.png)

[FIGURE 10-16:](#13_9781119404170-ch10.xhtml_rc10-fig-0016) Where the location, width, and height of both sets of pipes should be retrieved in the `checkCollision` method.

![image](images/9781119404170-fg1017.png)

[FIGURE 10-17:](#13_9781119404170-ch10.xhtml_rc10-fig-0017) Where the conditional statement to actually test collision should be in the `checkCollision` method.

## ADDING HELPER METHODS

In the previous section, you added comments in Steps 2 and 3 to get the location, width, and height of the bird and two sets of pipes. However, you currently don’t have any methods to help get that information. In this section, you’ll add four methods to your `Bird` and `Pipes` classes to gather and return that information.

1.  **Add four methods called** `getX`**,** `getY`**,** `getWidth`**, and** `getHeight`**. Each method should return an integer (number) and should not have any parameters (see** [**Figure 10-18**](#13_9781119404170-ch10.xhtml_c10-fig-0018)**).**

    `//Method to return the x-coordinate of the bird`
    `int getX()`
    `{`
    `return 0;`
    `}`

    `//Method to return the y-coordinate of the bird`
    `int getY()`
    `{`
    `return 0;`
    `}`

    `//Method to return the width of the bird`
    `int getWidth()`
    `{`
    `return 0;`
    `}`

    `//Method to return the height of the bird`
    `int getHeight()`
    `{`
    `return 0;`
    `}`

2.  **You don’t currently have variables to keep track of the width and height of the bird, so add those at the top of your `Bird` class (see** [**Figure 10-19**](#13_9781119404170-ch10.xhtml_c10-fig-0019)**).**

    `//Two variables for the width and height of the bird`

3.  **For the `Pipes` class, you need to know the *x*-coordinate, *y*-coordinate, width, and height of the top pipe *and* the bottom pipe, so you need to add eight methods to your pipe class (see** [**Figure 10-20**](#13_9781119404170-ch10.xhtml_c10-fig-0020)**).**

    `//Method to return the x-coordinate of the top`
    `//pipe`
    `int getXTop()`
    `{`
    `return 0;`
    `}`

    `//Method to return the y-coordinate of the top`
    `//pipe`
    `int getYTop()`
    `{`
    `return 0;`
    `}`

    `//Method to return the width of the top pipe`
    `int getWidthTop()`
    `{`
    `return 0;`
    `}`

    `//Method to return the height of the top pipe`
    `int getHeightTop()`
    `{`
    `return 0;`
    `}`

    `//Method to return the x-coordinate of the bottom`
    `//pipe`
    `int getXBottom()`
    `{`
    `return 0;`
    `}`

    `//Method to return the y-coordinate of the bottom`
    `//pipe`
    `int getYBottom()`
    `{`
    `return 0;`
    `}`

    `//Method to return the width of the bottom pipe`
    `int getWidthBottom()`
    `{`
    `return 0;`
    `}`

    `//Method to return the height of the bottom pipe`
    `int getHeightBottom()`
    `{`
    `return 0;`
    `}`

4.  **Add the four variables to keep track of the width and height of the top and bottom pipes (see** [**Figure 10-21**](#13_9781119404170-ch10.xhtml_c10-fig-0021)**).**

    `//Four variables for the width and height of the top`
    `//and bottom pipes`

5.  **Add two more variables to keep track of the location of *both* pipes, not just one (see** [**Figure 10-22**](#13_9781119404170-ch10.xhtml_c10-fig-0022)**).**

    `//Four variables for the location of the top and`
    `//bottom pipes`

![image](images/9781119404170-fg1018.png)

[FIGURE 10-18:](#13_9781119404170-ch10.xhtml_rc10-fig-0018) Where the four new methods in the `Bird` class should be written.

![image](images/9781119404170-fg1019.png)

[FIGURE 10-19:](#13_9781119404170-ch10.xhtml_rc10-fig-0019) Where the width and height variables should be added.

![image](images/9781119404170-fg1020.png)

[FIGURE 10-20:](#13_9781119404170-ch10.xhtml_rc10-fig-0020) A reference for where the eight methods should be added to the Pipes class.

![image](images/9781119404170-fg1021.png)

[FIGURE 10-21:](#13_9781119404170-ch10.xhtml_rc10-fig-0021) The location of where the four new variables should be created in the Pipes class.

![image](images/9781119404170-fg1022.png)

[FIGURE 10-22:](#13_9781119404170-ch10.xhtml_rc10-fig-0022) Updating the `location` variables to include the top *and* bottom pipes in the `Pipes` class.

Congratulations! You have now completely outlined your entire Ninja Bird game! In the next chapter, you’ll start adding in all the code beneath your comments and testing out your game.

![image](images/c11.png)

In [Chapters 9](#12_9781119404170-ch09.xhtml) and [10](#13_9781119404170-ch10.xhtml), you completely outlined your program and wrote comments everywhere that you’ll need code. In this chapter, you’ll be challenged with writing and testing the actual code to make your game! By the end of this chapter, you’ll have a basic, working videogame.

## CONVERTING COMMENTS TO CODE

Make sure you have your NinjaBird code open from [Chapter 10](#13_9781119404170-ch10.xhtml) (see [Figure 11-1](#14_9781119404170-ch11.xhtml_c11-fig-0001)). You should have three tabs: NinjaBird, Bird, and Pipes. In each tab, you should have a lot of empty methods and a lot of comments, which will guide you through this chapter.

![image](images/9781119404170-fg1101.png)

[FIGURE 11-1:](#14_9781119404170-ch11.xhtml_rc11-fig-0001) Your NinjaBird code from [Chapter 10](#13_9781119404170-ch10.xhtml).

In this section, you’re going to start converting your comments to code. It won’t make sense to just start at the top of the file, and move down, because you want to be able to test small pieces of your code as you write the code. So, you’ll break up the code writing into logical steps: the background, the bird and pipes, and the user input.

### CONVERTING BACKGROUND COMMENTS TO CODE

First, you should create the background. You will have to

*   Create an 800-x-800-pixel canvas.
*   Color the canvas blue.
*   Find a picture of a city.
*   Create grass.
*   Put the city on top of the grass.

The code that you’ll write for this section will be split between the `setup` and `drawScene` methods in your main class (the NinjaBird tab).

1.  **Create a canvas that is 800 x 800 pixels (see** [**Figure 11-2**](#14_9781119404170-ch11.xhtml_c11-fig-0002)**):**

    `size(800, 800);`

2.  **Test your code to make sure that a canvas gets created that is a good size (800 x 800 pixels).**

    To test, click the Run button shown in [Figure 11-3](#14_9781119404170-ch11.xhtml_c11-fig-0003). You should see a similar canvas to the one in [Figure 11-4](#14_9781119404170-ch11.xhtml_c11-fig-0004).

3.  **Call the** `background` **method from inside your** `drawScene` **method to turn the background of the canvas blue like the sky (see** [**Figure 11-5**](#14_9781119404170-ch11.xhtml_c11-fig-0005)**):**

    `background(173, 216, 230);`

4.  **Call the** `drawScene` **method from your** `setup` **method so that you can actually test to make sure the canvas is being turned blue (see** [**Figure 11-6**](#14_9781119404170-ch11.xhtml_c11-fig-0006)**):**

    `drawScene();`

5.  **Test your code to make sure the canvas is now blue instead of gray (see** [**Figure 11-7**](#14_9781119404170-ch11.xhtml_c11-fig-0007)**).**
6.  **Create a green rectangle along the bottom of your canvas to look like grass (see** [**Figure 11-8**](#14_9781119404170-ch11.xhtml_c11-fig-0008)**):**

    `stroke(0, 255, 0);`
    `fill(0, 255, 0);`
    `rect(0, 700, 1000, 1000);`

7.  **Test to make sure the grass looks good on your canvas (see** [**Figure 11-9**](#14_9781119404170-ch11.xhtml_c11-fig-0009)**).**
8.  **Just as in earlier chapters, go online to find an image of a city that you want to use in the background of your game (see** [**Figure 11-10**](#14_9781119404170-ch11.xhtml_c11-fig-0010)**).**

    Search “cityscape drawing” on Google images, and make sure you have permission to use the drawing.

9.  **When you have found and downloaded an image you want to use, save the file to your NinjaBird folder where your code is (see** [**Figure 11-11**](#14_9781119404170-ch11.xhtml_c11-fig-0011)**).**
10.  **Add a line of code to load in the city image to your program (see** [**Figure 11-12**](#14_9781119404170-ch11.xhtml_c11-fig-0012)**):**

    `PImage city = loadImage("cityscape.png");`

11.  **Add the city image to your canvas (see** [**Figure 11-13**](#14_9781119404170-ch11.xhtml_c11-fig-0013)**):**

    `image(city, 0, 500);`

12.  **Test your code to make sure your city is in the right location (see** [**Figure 11-14**](#14_9781119404170-ch11.xhtml_c11-fig-0014)**). If it isn’t, adjust the size of your image or location of your image to make it look the way you want it.**

![image](images/9781119404170-fg1102.png)

[FIGURE 11-2:](#14_9781119404170-ch11.xhtml_rc11-fig-0002) Where the canvas should be created in the setup method.

![image](images/9781119404170-fg1103.png)

[FIGURE 11-3:](#14_9781119404170-ch11.xhtml_rc11-fig-0003) The Run button you should press to test your code.

![image](images/9781119404170-fg1104.png)

[FIGURE 11-4:](#14_9781119404170-ch11.xhtml_rc11-fig-0004) The canvas that should pop up after you press the Run button.

![image](images/9781119404170-fg1105.png)

[FIGURE 11-5:](#14_9781119404170-ch11.xhtml_rc11-fig-0005) Where the `background` method should be called in the `drawScene` method.

![image](images/9781119404170-fg1106.png)

[FIGURE 11-6:](#14_9781119404170-ch11.xhtml_rc11-fig-0006) Where you should call the `drawScene` method from the `setup` method.

![image](images/9781119404170-fg1107.png)

[FIGURE 11-7:](#14_9781119404170-ch11.xhtml_rc11-fig-0007) What the canvas should look like when you test your code.

![image](images/9781119404170-fg1108.png)

[FIGURE 11-8:](#14_9781119404170-ch11.xhtml_rc11-fig-0008) Where the code for the grass should be in the `drawScene` method.

![image](images/9781119404170-fg1109.png)

[FIGURE 11-9:](#14_9781119404170-ch11.xhtml_rc11-fig-0009) What your canvas should look like when you add the grass.

![image](images/9781119404170-fg1110.png)

[FIGURE 11-10:](#14_9781119404170-ch11.xhtml_rc11-fig-0010) Search for a cityscape drawing that you can legally use.

![image](images/9781119404170-fg1111.png)

[FIGURE 11-11:](#14_9781119404170-ch11.xhtml_rc11-fig-0011) The cityscape image should be in your NinjaBird code folder.

![image](images/9781119404170-fg1112.png)

[FIGURE 11-12:](#14_9781119404170-ch11.xhtml_rc11-fig-0012) The location of where your city image code should be in your `drawScene` method.

![image](images/9781119404170-fg1113.png)

[FIGURE 11-13:](#14_9781119404170-ch11.xhtml_rc11-fig-0013) Where to add the code to draw the city on the canvas.

![image](images/9781119404170-fg1114.png)

[FIGURE 11-14:](#14_9781119404170-ch11.xhtml_rc11-fig-0014) Your canvas with the cityscape image in it.

Congratulations! Your background now looks similar to the version of Flappy Bird that you played on [`www.flappybird.io`](http://www.flappybird.io) in [Chapter 9](#12_9781119404170-ch09.xhtml)!

### CONVERTING BIRD COMMENTS TO CODE

Now that you have a background, it’s time to get your bird into your game and flying around! Follow these steps:

1.  **Find an image of a bird that you want to use (and have permission to use), and put it in your NinjaBird code folder (see** [**Figure 11-15**](#14_9781119404170-ch11.xhtml_c11-fig-0015)**).**
2.  **Create the bird image in your** `Bird` **class (see** [**Figure 11-16**](#14_9781119404170-ch11.xhtml_c11-fig-0016)**).**

    `PImage bird = loadImage("bird.png");`

3.  **Draw the bird on the canvas toward the center (see** [**Figure 11-17**](#14_9781119404170-ch11.xhtml_c11-fig-0017)**):**

    `//Draw the bird on the canvas`
    `image(bird, 300, 200);`

4.  **Back in your main class, create a variable for the bird at the top of the file (see** [**Figure 11-18**](#14_9781119404170-ch11.xhtml_c11-fig-0018)**):**

    `Bird bird;`

5.  **In your main class still, call the constructor for the** `Bird` **class in your** `setup` **method (see** [**Figure 11-19**](#14_9781119404170-ch11.xhtml_c11-fig-0019)**).**

    `bird = new Bird();`

6.  **Test your code to make sure your bird is in your game in a good location (see** [**Figure 11-20**](#14_9781119404170-ch11.xhtml_c11-fig-0020)**).**
7.  **Add the four variables that keep track of the location, width, and height of your bird (see** [**Figure 11-21**](#14_9781119404170-ch11.xhtml_c11-fig-0021)**):**

    `//Two variables for the location of the bird`
    `int xCoordinate = 300;`
    `int yCoordinate = 200;`

    `//Two variables for the width and height of the`
    `//bird`
    `int width = bird.width;`
    `int height = bird.height;`

8.  **Update your constructor to use the location variables you just created (see** [**Figure 11-22**](#14_9781119404170-ch11.xhtml_c11-fig-0022)**):**

    `image(bird, xCoordinate, yCoordinate);`

9.  **Add code to the** `move` **method in the** `Bird` **class to make the bird always falling (see** [**Figure 11-23**](#14_9781119404170-ch11.xhtml_c11-fig-0023)**):**

    `//Simulate gravity to make your bird constantly fall`
    `if(yCoordinate < 700)`
    `{`
    `yCoordinate = yCoordinate + 5;`
    `}`

    This is very similar to the code you wrote in [Chapter 7](#10_9781119404170-ch07.xhtml) when you made your game simulate gravity.

10.  **Redraw the bird on the canvas, now that you have updated its location (see** [**Figure 11-24**](#14_9781119404170-ch11.xhtml_c11-fig-0024)**):**

    `//Redraw the bird in on the canvas`
    `image(bird, xCoordinate, yCoordinate);`

11.  **Call the bird** `move` **method from the main class’s** `draw` **method to redraw the bird (see** [**Figure 11-25**](#14_9781119404170-ch11.xhtml_c11-fig-0025)**):**

    `bird.move();`

12.  **Call the** `drawScene` **method in the** `draw` **method in the main class so that the bird doesn’t have a trail as it falls (see** [**Figure 11-26**](#14_9781119404170-ch11.xhtml_c11-fig-0026)**):**

    `drawScene();`

13.  **Test your code to make sure the bird falls and stops when it hits the ground (see** [**Figure 11-27**](#14_9781119404170-ch11.xhtml_c11-fig-0027)**).**
14.  **Add a line of code to move the bird back up when the player clicks the mouse. This is in the** `mouseClicked` **method in the** `Bird` **class (see** [**Figure 11-28**](#14_9781119404170-ch11.xhtml_c11-fig-0028)**).**

    `//Move the bird up when the mouse is clicked`
    `yCoordinate = yCoordinate - 75;`

15.  **The** `mouseClicked` **method isn’t automatically called by the Processing application unless there is also a** `draw` **method in the same class. Because the** `Bird` **class doesn’t have a** `draw` **method, you have to create a** `mouseClicked` **method in the main class and call the bird** `mouseClicked` **method from it. Add a new method to the main class to do this (see** [**Figure 11-29**](#14_9781119404170-ch11.xhtml_c11-fig-0029)**):**

    `//Call the mouseClicked button for the bird when the`
    `//mouse is clicked`
    `void mouseClicked()`
    `{`
    `bird.mouseClicked();`
    `}`

16.  **Test your code and make sure that when you click inside the canvas the bird moves up.**

![image](images/9781119404170-fg1115.png)

[FIGURE 11-15:](#14_9781119404170-ch11.xhtml_rc11-fig-0015) The image of the bird in your NinjaBird code folder.

![image](images/9781119404170-fg1116.png)

[FIGURE 11-16:](#14_9781119404170-ch11.xhtml_rc11-fig-0016) Where the bird image should be created in the `Bird` class.

![image](images/9781119404170-fg1117.png)

[FIGURE 11-17:](#14_9781119404170-ch11.xhtml_rc11-fig-0017) The bird should be drawn in the constructor of the `Bird` class.

![image](images/9781119404170-fg1118.png)

[FIGURE 11-18:](#14_9781119404170-ch11.xhtml_rc11-fig-0018) Where the `bird` variable should be created in the main class.

![image](images/9781119404170-fg1119.png)

[FIGURE 11-19:](#14_9781119404170-ch11.xhtml_rc11-fig-0019) Where to call the constructor for the `Bird` class.

![image](images/9781119404170-fg1120.png)

[FIGURE 11-20:](#14_9781119404170-ch11.xhtml_rc11-fig-0020) Your bird should now appear in your game when you test.

![image](images/9781119404170-fg1121.png)

[FIGURE 11-21:](#14_9781119404170-ch11.xhtml_rc11-fig-0021) The location, width, and height variables should be added to the top of the `Bird` class.

![image](images/9781119404170-fg1122.png)

[FIGURE 11-22:](#14_9781119404170-ch11.xhtml_rc11-fig-0022) The updated code in the `Bird` constructor.

![image](images/9781119404170-fg1123.png)

[FIGURE 11-23:](#14_9781119404170-ch11.xhtml_rc11-fig-0023) Where you should type your gravity code in your `move` method in the `Bird` class.

![image](images/9781119404170-fg1124.png)

[FIGURE 11-24:](#14_9781119404170-ch11.xhtml_rc11-fig-0024) Where to add the code to redraw the bird in the `Bird` class.

![image](images/9781119404170-fg1125.png)

[FIGURE 11-25:](#14_9781119404170-ch11.xhtml_rc11-fig-0025) The line of code added to the `draw` method in the main class.

![image](images/9781119404170-fg1126.png)

[FIGURE 11-26:](#14_9781119404170-ch11.xhtml_rc11-fig-0026) The `drawScene` method being called from the `draw` method.

![image](images/9781119404170-fg1127.png)

[FIGURE 11-27:](#14_9781119404170-ch11.xhtml_rc11-fig-0027) The bird falling to the ground.

![image](images/9781119404170-fg1128.png)

[FIGURE 11-28:](#14_9781119404170-ch11.xhtml_rc11-fig-0028) Where to put the code to move the bird up in the `Bird` class.

![image](images/9781119404170-fg1129.png)

[FIGURE 11-29:](#14_9781119404170-ch11.xhtml_rc11-fig-0029) The new `mouseClicked` method in the main class.

Wow! What you’ve done so far is incredible! There is just a bit more to code in this chapter: making the pipes move across the screen!

### CONVERTING PIPES COMMENTS TO CODE

The last part to this chapter is making pipes move from the right side of the canvas to the left side of the canvas. In this section, you won’t be guided line by line; instead, you’ll be shown large chunks of code to write at once. A lot of what you’ll be coding in this section is similar to what you coded for your bird and very similar to the code you wrote for your enemies in [Chapter 8](#11_9781119404170-ch08.xhtml). Follow these steps:

1.  **Find an image of a pipe you want to use in your game, save it in your NinjaBird code folder, copy the image, and flip the copied image vertically so that you can have one top pipe and one bottom pipe (see** [**Figure 11-30**](#14_9781119404170-ch11.xhtml_c11-fig-0030)**).**
2.  **At the top of your** `Pipes` **class, create the ten variables you’ll need to use throughout your code (see** [**Figure 11-31**](#14_9781119404170-ch11.xhtml_c11-fig-0031)**):**

    `//Variable for the image of the pipes`
    `PImage topPipe = loadImage("topPipe.png");`
    `PImage bottomPipe = loadImage("bottomPipe.png");`

    `//Four variables for the location of the top and`
    `//bottom pipes`
    `int xCoordinateTop = 500;`
    `int yCoordinateTop = -300;`
    `int xCoordinateBottom = 500;`
    `int yCoordinateBottom = 500;`

    `//Four variables for the width and height of the`
    `//top and bottom pipes`
    `int widthTop = topPipe.width;`
    `int heightTop = topPipe.height;`
    `int widthBottom = bottomPipe.width;`
    `int heightBottom = bottomPipe.height;`

3.  **Draw the top and bottom pipes in the constructor and in the** `move` **methods in the** `Pipes` **class (as shown in [Figure 11-32](#14_9781119404170-ch11.xhtml_c11-fig-0032)).**

    `//Constructor to create the pipes`
    `Pipes()`
    `{`
    `//Draw the pipes in on the canvas`
    `image(topPipe, xCoordinateTop, yCoordinateTop);`
    `image(bottomPipe, xCoordinateBottom, yCoordinateBottom);`
    `}`

    `//Method to move the pipes`
    `void move()`
    `{`
    `//Redraw the pipes on the canvas`
    `image(topPipe, xCoordinateTop, yCoordinateTop);`
    `image(bottomPipe, xCoordinateBottom, yCoordinateBottom);`
    `}`

4.  **In your NinjaBird main class, create a new variable for the pipes (see** [**Figure 11-33**](#14_9781119404170-ch11.xhtml_c11-fig-0033)**):**

    `Pipes pipes;`

    **Call the `Pipes` constructor in the setup method (refer to** [**Figure 11-33**](#14_9781119404170-ch11.xhtml_c11-fig-0033)**):**

    `pipes = new Pipes();`

    **And call the pipes `move` method in the `draw` method (see** [**Figure 11-33**](#14_9781119404170-ch11.xhtml_c11-fig-0033)**):**

    `pipes.move();`

5.  **Test your code to make sure your pipes are showing up on your canvas in the correct locations (see** [**Figure 11-34**](#14_9781119404170-ch11.xhtml_c11-fig-0034)**).**
6.  **Add two lines of code to move the pipes from the right side of the screen to the left side of the screen (see** [**Figure 11-35**](#14_9781119404170-ch11.xhtml_c11-fig-0035)**):**

    `//Move the pipes from right to left across the`
    `//screen`
    `xCoordinateTop = xCoordinateTop - 3;`
    `xCoordinateBottom = xCoordinateBottom - 3;`

7.  **Add a conditional statement to move the pipes from the left side of the canvas back to the right, when they reach the very left (see** [**Figure 11-36**](#14_9781119404170-ch11.xhtml_c11-fig-0036)**).**

    `//Conditional to move the pipe from the left back to`
    `//the right`
    `if(xCoordinateTop < - 150)`
    `{`
    `xCoordinateTop = 800;`
    `xCoordinateBottom = 800;`
    `}`

8.  **To make the game a bit more difficult, you can add in a second set of pipes! But to do that, you have to adjust the** `Pipes` **constructor to first take in the starting *x*- and *y*-coordinates for the top and bottom pipes.**

    First, get rid of the initial values at the top of the `Pipes` class:

    `//Four variables for the location of the top and`
    `//bottom pipes`
    `int xCoordinateTop;`
    `int yCoordinateTop;`
    `int xCoordinateBottom;`
    `int yCoordinateBottom;`

    Then, add four parameters to the `Pipes` constructor, and set the four location variables to those new parameters:

    `Pipes(int xTop, int yTop, int xBottom, int yBottom)`
    `{`
    `xCoordinateTop = xTop;`
    `yCoordinateTop = yTop;`
    `xCoordinateBottom = xBottom;`
    `yCoordinateBottom = yBottom;`

    Next, update the call to the `Pipes` constructor in the NinjaBird main class to include the initial values:

    `pipes = new Pipes(500, -300, 500, 500);`

    The beginning of your `Pipes` class should now reflect what you see in [Figure 11-37](#14_9781119404170-ch11.xhtml_c11-fig-0037).

    The `setup` method in your NinjaBird main class should now reflect what you see in [Figure 11-38](#14_9781119404170-ch11.xhtml_c11-fig-0038).

9.  **Test your code to make sure your pipes still move from right to left and then reset to the right of the canvas.**
10.  **Add a second set of pipes that starts at a different location on your canvas.**

    First, create a second pipes variable at the top of your NinjaBird main class:

    `Pipes pipes2;`

    Then, call the constructor for the second pipes variable in your `setup` method. Be sure to use different *x*-coordinates than the first pipes variable:

    `pipes2 = new Pipes(0, -300, 0, 500);`

    Finally, call the `move` method for the second pipes variable so that it moves as well:

    `pipes2.move();`

    [Figure 11-39](#14_9781119404170-ch11.xhtml_c11-fig-0039) shows all the locations where these three lines of code are added.

11.  **Test your code and watch as two sets of pipes moves across your canvas from right to left and then reset to the right side (see** [**Figure 11-40**](#14_9781119404170-ch11.xhtml_c11-fig-0040)**)!**

![image](images/9781119404170-fg1130.png)

[FIGURE 11-30:](#14_9781119404170-ch11.xhtml_rc11-fig-0030) Flipping an image horizontally in Preview on the Mac.

![image](images/9781119404170-fg1131.png)

[FIGURE 11-31:](#14_9781119404170-ch11.xhtml_rc11-fig-0031) The ten variables needed in the `Pipes` class.

![image](images/9781119404170-fg1132.png)

[Figure 11-32:](#14_9781119404170-ch11.xhtml_rc11-fig-0032) The `Pipes` constructor and `move` methods drawing the pipes.

![image](images/9781119404170-fg1133.png)

[FIGURE 11-33:](#14_9781119404170-ch11.xhtml_rc11-fig-0033) The three different locations where the code in Step 4 should be added to the main class.

![image](images/9781119404170-fg1134.png)

[FIGURE 11-34:](#14_9781119404170-ch11.xhtml_rc11-fig-0034) The canvas with the pipes.

![image](images/9781119404170-fg1135.png)

[FIGURE 11-35:](#14_9781119404170-ch11.xhtml_rc11-fig-0035) The movement code in the `move` method in the `Pipes` class.

![image](images/9781119404170-fg1136.png)

[FIGURE 11-36:](#14_9781119404170-ch11.xhtml_rc11-fig-0036) The updated `move` method in the `Pipes` class to reset the pipes to the right side of the canvas.

![image](images/9781119404170-fg1137.png)

[FIGURE 11-37:](#14_9781119404170-ch11.xhtml_rc11-fig-0037) The top of the Pipes class with the changes from Step 8.

![image](images/9781119404170-fg1138.png)

[FIGURE 11-38:](#14_9781119404170-ch11.xhtml_rc11-fig-0038) The `setup` method in the main class with the changes from Step 8.

![image](images/9781119404170-fg1139.png)

[FIGURE 11-39:](#14_9781119404170-ch11.xhtml_rc11-fig-0039) The NinjaBird main class updated to have a second set of pipes.

![image](images/9781119404170-fg1140.png)

[FIGURE 11-40:](#14_9781119404170-ch11.xhtml_rc11-fig-0040) Your NinjaBird game with two sets of pipes.

Congratulations! You’ve made a version of your Ninja Bird game! In the final chapter of this book, you’ll add in the scores and collision detection, and make the pipes move up and down!

![image](images/c12.png)

In the previous three chapters, you’ve planned, outlined, and started to code your Ninja Bird videogame. In this final chapter, you’ll add some randomness to your game, making it more challenging for your players. At the end of this chapter, you’ll find all the code for the entire game, so that you can compare the final, correct code, to yours! Completing an entire videogame is not easy. Congratulations!

## ADDING RANDOMNESS TO YOUR PIPES

Make sure you have your Ninja Bird code open from [Chapter 11](#14_9781119404170-ch11.xhtml). In this section, you’re going to learn how to add some randomness to your code — specifically, to make the pipes have their opening be in different places each time they come back around to the right side of the canvas.

To use randomness, you’re going to learn about Java libraries. Java libraries are bits of code that anyone coding in Java can use. They’re very similar to the code that you’ve been using given to you by the Processing application, like the method rect. Follow these steps:

1.  **At the very top of your** `Pipes` **class, import the Random library (see** [**Figure 12-1**](#15_9781119404170-ch12.xhtml_c12-fig-0001)**):**

    `import java.util.Random;`

2.  **Add a new variable to your** `Pipes` **class that will let you choose random numbers (see** [**Figure 12-2**](#15_9781119404170-ch12.xhtml_c12-fig-0002)**):**

    `//Variable to create random numbers`
    `Random rand = new Random();`

3.  **Add two lines of code to update the *y*-coordinate of the top and bottom pipes.**

    First, choose a random number as the *y*-coordinate for the bottom pipe:

    `yCoordinateBottom = rand.nextInt(450) + 250;`

    Then, set the *y*-coordinate for the top pipe to be exactly 800 pixels away from the bottom pipe:

    `yCoordinateTop = yCoordinateBottom - 800;`

    [Figure 12-3](#15_9781119404170-ch12.xhtml_c12-fig-0003) shows where these two new lines of code should be added to the `move` method in the `Pipes` class.

4.  **Test your code to make sure that your pipes have random *y*-coordinates each time they move to back to the right side of the screen (see** [**Figure 12-4**](#15_9781119404170-ch12.xhtml_c12-fig-0004)**).**

![image](images/9781119404170-fg1201.png)

[FIGURE 12-1:](#15_9781119404170-ch12.xhtml_rc12-fig-0001) The Random library imported at the top of the `Pipes` class.

![image](images/9781119404170-fg1202.png)

[FIGURE 12-2:](#15_9781119404170-ch12.xhtml_rc12-fig-0002) The location of your new random variable.

![image](images/9781119404170-fg1203.png)

[FIGURE 12-3:](#15_9781119404170-ch12.xhtml_rc12-fig-0003) The location of the code to update the *y*-coordinates of the top and bottom pipes.

![image](images/9781119404170-fg1204.png)

[FIGURE 12-4:](#15_9781119404170-ch12.xhtml_rc12-fig-0004) The two sets of pipes should have random *y*-coordinates when you test your code.

You now have randomness in your game, and you’ve made your game more like the real Flappy Bird!

## DETECTING COLLISION

This section will guide you through coding collision detection and adding a score to your game.

Go into your NinjaBird main class and find the `checkCollision` method that you outlined in [Chapter 10](#13_9781119404170-ch10.xhtml). Notice that you need to access the location, width, and height of the bird and the pipes. Instead of creating new variables for this, you can simply use the helper methods you planned out earlier in this book. But first, you need to actually return the correct values in those helper methods:

1.  **Return the correct variables from the four methods in your Bird class (see** [**Figure 12-5**](#15_9781119404170-ch12.xhtml_c12-fig-0005)**):**

    `//Method to return the x-coordinate of the bird`
    `int getX()`
    `{`
    `return xCoordinate;`
    `}`

    `//Method to return the y-coordinate of the bird`
    `int getY()`
    `{`
    `return yCoordinate;`
    `}`

    `//Method to return the width of the bird`
    `int getWidth()`
    `{`
    `return width;`
    `}`

    `//Method to return the height of the bird`
    `int getHeight()`
    `{`
    `return height;`
    `}`

2.  **Return the correct variables from the eight helper methods in the Pipes class:**

    `//Method to return the x-coordinate of the top pipe`
    `int getXTop()`
    `{`
    `return xCoordinateTop;`
    `}`

    `//Method to return the y-coordinate of the top pipe`
    `int getYTop()`
    `{`
    `return yCoordinateTop;`
    `}`

    `//Method to return the width of the top pipe`
    `int getWidthTop()`
    `{`
    `return widthTop;`
    `}`

    `//Method to return the height of the top pipe`
    `int getHeightTop()`
    `{`
    `return heightTop;`
    `}`

    `//Method to return the x-coordinate of the bottom`
    `//pipe`
    `int getXBottom()`
    `{`
    `return xCoordinateBottom;`
    `}`

    `//Method to return the y-coordinate of the bottom`
    `//pipe`
    `int getYBottom()`
    `{`
    `return yCoordinateBottom;`
    `}`

    `//Method to return the width of the bottom pipe`
    `int getWidthBottom()`
    `{`
    `return widthBottom;`
    `}`

    `//Method to return the height of the bottom pipe`
    `int getHeightBottom()`
    `{`
    `return heightBottom;`
    `}`

    [Figure 12-6](#15_9781119404170-ch12.xhtml_c12-fig-0006) shows where these eight helpers are in your `Pipes` class file.

3.  **Delete the two comments in the** `checkCollision` **method in the NinjaBird main class (see** [**Figure 12-7**](#15_9781119404170-ch12.xhtml_c12-fig-0007)**).**

    Now that you have the helper methods available to you, you don’t need the comments to remind you to access those methods.

4.  **Because you have two sets of pipes, it makes more sense to check to see if the bird hits the pipes inside of the** `Pipes` **class; that way, you don’t have to write the collision detection code for each set of pipes. In the** `Pipes` **class, create a new method called** `checkIfHit` **that returns a Boolean and takes three integer parameters (see** [**Figure 12-8**](#15_9781119404170-ch12.xhtml_c12-fig-0008)**):**

    `boolean checkIfHit(int x, int topY, int bottomY)`
    `{`

    `return false;`
    `}`

5.  **In your NinjaBird main class, create three variables for the** `rightX`**,** `topY`**, and** `bottomY` **of the bird and then pass them in to the** `checkIfHit` **method for both the** `pipes` **and** `pipes2` **sets of pipes. If *either* returns true, then the bird has hit some set of pipes and your** `checkCollision` **method should return true. Otherwise, your** `checkCollision` **method should return false. The new `checkCollision` method is shown in** [**Figure** **12-9**](#15_9781119404170-ch12.xhtml_c12-fig-0009)**.**

    `//Method to check to see if the bird has hit any of`
    `//the pipes`
    `boolean checkCollision()`
    `{`
    `int birdRightX = bird.getX() + bird.getWidth()/2;`
    `int birdTopY = bird.getY() - bird.getHeight()/2;`
    `int birdBottomY = bird.getY() + bird.getHeight()/2;`

    `if(pipes.checkIfHit(birdRightX,`
    `birdTopY, birdBottomY) || pipes2.checkIfHit(birdRightX,`
    `birdTopY, birdBottomY))`
    `{`
    `return true;`
    `}`

    `return false;`
    `}`

6.  **Back in the** `Pipes` **class, create three variables to determine if the bird is within the set of pipes horizontally (see** [**Figure 12-10**](#15_9781119404170-ch12.xhtml_c12-fig-0010)**):**

    `//Determine if the bird is within the pipes`
    `//horizontally`
    `boolean birdPastPipesBeg = x >= xCoordinateTop;`
    `boolean birdBeforePipesEnd = x <= (xCoordinateTop + widthTop);`
    `boolean birdWithinPipes = birdPastPipesBeg && birdBeforePipesEnd;`

    **Add three more variables to determine if the bird is within the gap of the pipes vertically:**

    `//Determine if the bird is within the gap of the`
    `//pipes vertically`
    `boolean birdBelowTopPipes = topY > (yCoordinateTop + heightTop);`
    `boolean birdAboveBottomPipes = bottomY < yCoordinateBottom;`
    `boolean withinGap = birdBelowTopPipes && birdAboveBottomPipes;`

    **Finally, add a conditional statement that will return true if the bird is within the pipes horizontally and *not* within the gap (meaning it is touching the pipes):**

    `//Conditional statement to check if the bird is in`
    `//the same location as the pipes`
    `if(birdWithinPipes && !withinGap)`
    `{`
    `return true;`
    `}`

7.  **Add a conditional in the** `draw` **method in the NinjaBird main class to check if there was a collision. If there was, have the word *YES* appear over the bird; otherwise, have the word *NO* appear over the bird (see** [**Figure** **12-11**](#15_9781119404170-ch12.xhtml_c12-fig-0011)**).**

    `//Conditional statement to check if the bird has hit`
    `//the pipes`
    `if(checkCollision())`
    `{`
    `text("YES", bird.getX() + 60, bird.getY() - 5);`
    `}`
    `else`
    `{`
    `text("NO", bird.getX() + 60, bird.getY() - 5);`
    `}`

8.  **Test your code to make sure your bird updates the word above its head depending on if it’s avoiding the pipes (as in** [**Figure 12-12**](#15_9781119404170-ch12.xhtml_c12-fig-0012)**) or touching the pipes (as in** [**Figure 12-13**](#15_9781119404170-ch12.xhtml_c12-fig-0013)**).**

![image](images/9781119404170-fg1205.png)

[FIGURE 12-5:](#15_9781119404170-ch12.xhtml_rc12-fig-0005) The four helper methods in the `Bird` class are at the bottom of the class.

![image](images/9781119404170-fg1206.png)

[FIGURE 12-6:](#15_9781119404170-ch12.xhtml_rc12-fig-0006) The location of the eight helper methods in the `Pipes` class.

![image](images/9781119404170-fg1207.png)

[FIGURE 12-7:](#15_9781119404170-ch12.xhtml_rc12-fig-0007) The `checkCollision` method without the extra comments.

![image](images/9781119404170-fg1208.png)

[FIGURE 12-8:](#15_9781119404170-ch12.xhtml_rc12-fig-0008) The location of the new `checkIfHit` method in the `Pipes` class.

![image](images/9781119404170-fg1209.png)

[FIGURE 12-9:](#15_9781119404170-ch12.xhtml_rc12-fig-0009) The location of the `checkCollision` method in the main class.

![image](images/9781119404170-fg1210.png)

[FIGURE 12-10:](#15_9781119404170-ch12.xhtml_rc12-fig-0010) The completed `checkIfHit` method in the `Pipes` class.

![image](images/9781119404170-fg1211.png)

[FIGURE 12-11:](#15_9781119404170-ch12.xhtml_rc12-fig-0011) The updated `draw` method in the main NinjaBird class.

![image](images/9781119404170-fg1212.png)

[FIGURE 12-12:](#15_9781119404170-ch12.xhtml_rc12-fig-0012) Your Ninja Bird game when the bird is avoiding the pipes.

![image](images/9781119404170-fg1213.png)

[FIGURE 12-13:](#15_9781119404170-ch12.xhtml_rc12-fig-0013) Your Ninja Bird game when the bird is touching the pipes.

## KEEPING SCORE IN YOUR GAME

Now that you can determine when the bird has hit a pipe, it’s time to keep track of the score of your game. Luckily, you already know if the bird is going between a gap in pipes — you just have to add another method to let the main class know that. Follow these steps:

1.  **In your** `Pipes` **method, create two new methods that both return a Boolean and take integer parameters. The first method is called** `birdWithinPipes`**; the second method is called** `birdWithinGap`**. Move the code from the** `checkIfHit` **method into the two methods you just created (see** [**Figure 12-14**](#15_9781119404170-ch12.xhtml_c12-fig-0014)**).**

    `boolean birdWithinPipes(int x)`
    `{`
    `//Determine if the bird is within the pipes`
    `//horizontally`
    `boolean birdPastPipesBeg = x >= xCoordinateTop;`
    `boolean birdBeforePipesEnd = x <= (xCoordinateTop + widthTop);`
    `boolean birdWithinPipes = birdPastPipesBeg && birdBeforePipesEnd;`

    `return birdWithinPipes;`
    `}`

    `boolean birdWithinGap(int topY, int bottomY)`
    `{`
    `//Determine if the bird is within the gap of the`
    `//pipes vertically`
    `boolean birdBelowTopPipes = topY > (yCoordinateTop + heightTop);`
    `boolean birdAboveBottomPipes = bottomY < yCoordinateBottom;`
    `boolean withinGap = birdBelowTopPipes && birdAboveBottomPipes;`

    `return withinGap;`
    `}`

    `boolean checkIfHit(int x, int topY, int bottomY)`
    `{`
    `//Conditional statement to check if the bird is in`
    `//the same location as the pipes`
    `if(birdWithinPipes(x) && !birdWithinGap(topY, bottomY))`
    `{`
    `return true;`
    `}`
    `return false;`
    `}`

2.  **Create a new method called** `birdPassedPipes` **that takes in an integer parameter and returns a Boolean. This method should return true if the bird has reached the right side of the pipe, meaning it successfully went through.**

    `boolean birdPassedPipes(int x)`
    `{`
    `boolean birdAtPipesEndLeft = x >= ((xCoordinateTop + widthTop) - 2);`
    `boolean birdAtPipesEndRight = x <= ((xCoordinateTop + widthTop) + 2);`
    `if(birdAtPipesEndLeft && birdAtPipesEndRight)`
    `{`
    `return true;`
    `}`

    `return false;`
    `}`

3.  **Create a new method called** `checkIfPassed` **that returns a Boolean and takes three integer parameters. This new method should return true if the bird passed the pipes *and* the bird is within the gap (see** [**Figure 12-15**](#15_9781119404170-ch12.xhtml_c12-fig-0015)**).**

    `boolean checkIfPassed(int x, int topY, int bottomY)`
    `{`
    `//Conditional statement to check if the bird is in`
    `//the same location as the pipes`
    `if(birdPassedPipes(x) && birdWithinGap(topY, bottomY))`
    `{`
    `return true;`
    `}`
    `return false;`
    `}`

4.  **Create two variables at the top of your NinjaBird main class that will keep track of the current and best scores (see** [**Figure 12-16**](#15_9781119404170-ch12.xhtml_c12-fig-0016)**).**

    `//Two variables that keep track of current and best`
    `//score`
    `int currentScore = 0;`
    `int bestScore = 0;`

5.  **Create a new method called** `trackScore` **in your NinjaBird main class to check to see if the bird has passed through either of the sets of pipes (see** [**Figure 12-17**](#15_9781119404170-ch12.xhtml_c12-fig-0017)**).**

    `//Method to check if the bird has successfully gone`
    `//through a set of pipes`
    `void trackScore()`
    `{`
    `int birdRightX = bird.getX() + bird.getWidth()/2;`
    `int birdTopY = bird.getY() - bird.getHeight()/2;`
    `int birdBottomY = bird.getY() + bird.getHeight()/2;`

    `if(pipes.checkIfPassed(birdRightX, birdTopY,`
    `birdBottomY) || pipes2.checkIfPassed(birdRightX,`
    `birdTopY, birdBottomY))`
    `{`
    `currentScore = currentScore + 1;`
    `}`
    `}`

6.  **Call the** `trackScore` **method from the draw method, and print the current score above the bird’s head.**

    `//Keep checking to see if the bird should get`
    `//another point`
    `trackScore();`
    `text(currentScore, bird.getX() + 60, bird.getY() - 5);`

7.  **Add a conditional statement *inside* the** `checkCollision` **conditional statement to update the** `bestScore` **variable when the bird hits a pipe *if* the current score is better than the best score. Then reset the** `currentScore` **back to 0 (see** [**Figure 12-18**](#15_9781119404170-ch12.xhtml_c12-fig-0018)**).**

    `//Conditional statement to check if the bird has hit`
    `//the pipes`
    `if(checkCollision())`
    `{`
    `if(currentScore > bestScore)`
    `{`
    `bestScore = currentScore;`
    `currentScore = 0;`
    `}`
    `}`

8.  **Test your code to make sure that the score gets updated every time the bird makes it through the pipes, as in** [**Figure 12-19**](#15_9781119404170-ch12.xhtml_c12-fig-0019)**, and that the score gets set back to 0 every time the bird hits a pipe, as in** [**Figure 12-20**](#15_9781119404170-ch12.xhtml_c12-fig-0020)**.**
9.  **Add a line of code to the end of your** `draw` **method in the main NinjaBird class to print the best score at the top of the screen always (see** [**Figure 12-21**](#15_9781119404170-ch12.xhtml_c12-fig-0021)**):**

    `text("BEST:" + bestScore, 400, 50);`

10.  **Test your code to make sure the best score gets updated every time the bird hits a pipe and the current score is better than the best score (see** [**Figure 12-22**](#15_9781119404170-ch12.xhtml_c12-fig-0022)**).**

![image](images/9781119404170-fg1214.png)

[FIGURE 12-14:](#15_9781119404170-ch12.xhtml_rc12-fig-0014) Updating the `checkIfHit` method to call the two new methods.

![image](images/9781119404170-fg1215.png)

[FIGURE 12-15:](#15_9781119404170-ch12.xhtml_rc12-fig-0015) The new `birdPassedPipes` and `checkIfPassed` methods in the `Pipes` class.

![image](images/9781119404170-fg1216.png)

[FIGURE 12-16:](#15_9781119404170-ch12.xhtml_rc12-fig-0016) The two new score variables.

![image](images/9781119404170-fg1217.png)

[FIGURE 12-17:](#15_9781119404170-ch12.xhtml_rc12-fig-0017) The new `trackScore` method in the NinjaBird main class.

![image](images/9781119404170-fg1218.png)

[FIGURE 12-18:](#15_9781119404170-ch12.xhtml_rc12-fig-0018) The updated `draw` method with the `trackScore` method called and the `checkCollision` conditional statement updated.

![image](images/9781119404170-fg1219.png)

[FIGURE 12-19:](#15_9781119404170-ch12.xhtml_rc12-fig-0019) The score updating when the bird gets through the pipes.

![image](images/9781119404170-fg1220.png)

[FIGURE 12-20:](#15_9781119404170-ch12.xhtml_rc12-fig-0020) The score going back to 0 when the bird hits a pipe.

![image](images/9781119404170-fg1221.png)

[FIGURE 12-21:](#15_9781119404170-ch12.xhtml_rc12-fig-0021) The best score should be displayed at the top of the screen.

![image](images/9781119404170-fg1222.png)

[FIGURE 12-22:](#15_9781119404170-ch12.xhtml_rc12-fig-0022) The best score showing at the top of the game.

## CLEANING UP THE CODE

Sometimes you plan code, but when you write it, your plans change. This is a natural part of coding and software development. In this case, your Ninja Bird game is a ton of fun just how it is right now.

At this point, you should go through your code and find all the comments and methods that you haven’t filled in yet.

### CLEANING UP THE NINJABIRD MAIN CLASS

Originally, the plan was to have a variable that keeps track of the state of the game in your main NinjaBird class. However, you don’t need that anymore because the game is just continuously playing, which can be a lot more fun!

Delete the comment at the top of your NinjaBird main class:

`//Variable that keeps track of the state of the game`

### CLEANING UP THE BIRD AND PIPES CLASSES

Originally, the plan was to have an “end sequence” where the bird and pipes would do something interesting when the player lost. Because the game that you made just has continuous play, these are no longer necessary either. Delete the empty method in the `Bird` class:

`//Method to make the bird hit the floor`
`void endSequence()`
`{`

`}`

And delete the empty method in the `Pipes` class:

`//Method to make the pipes stop when the bird hits`
`//them`
`void endSequence()`
`{`

`}`

Congratulations! You now have a working Ninja Bird game that keeps track of the highest score ever achieved, has random pipe movement, and allows your players to keep playing forever without stopping!

## ABOUT THE AUTHOR

**SARAH GUTHALS** received her PhD from UCSD in Computer Science specializing in CS Education in 2014\. During graduate school, she built the beta version of CodeSpells, a 3D immersive videogame designed to teach children to code through playing a wizard and writing “spells.” She went on to co-found ThoughtSTEM, a company that builds software (such as LearnToMod), curriculum, and pedagogies for teaching children to code and empowering K–12 teachers to teach their students. She has written four books around Minecraft and one on mobile development, launched a Coursera and EdX course for teachers interested in teaching coding, was recently named Forbes 30 under 30 in Science, and founded We Can, a company dedicated to encouraging *all* kids to do anything. Her passion is making coding accessible to everyone, with the goal of making it a basic literacy. Sarah currently teaches at UCSD.

## DEDICATION

I would like to dedicate this book to my close friends and family members who have supported me, not only in writing this book, but in becoming who I am today. I’d like to specifically dedicate this book to Adrian Guthals, who has always helped me to see that, with passion and dedication, I can really do anything I want.

## AUTHOR’S ACKNOWLEDGMENTS

I would like to acknowledge all of the hard work that went into making Processing — without these amazing engineers, making videogames would be so much harder. I would also like to acknowledge the teachers and parents around the world who have recognized the importance of coding in learning so many valuable lessons to our next generation of makers.

## PUBLISHER’S ACKNOWLEDGMENTS

**EXECUTIVE EDITOR:** Steven Hayes

**PROJECT EDITOR:** Elizabeth Kuball

**SR. EDITORIAL ASSISTANT:** Cherie Case

**PRODUCTION EDITOR:** Antony Sami

**COVER IMAGE:** © FrankRamspott/iStockphoto

# WILEY END USER LICENSE AGREEMENT

Go to [www.wiley.com/go/eula](http://www.wiley.com/go/eula) to access Wiley’s ebook EULA.