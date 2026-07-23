![](cover.jpeg)

| Java Basics |
|  |
| Java can be written in regular text editors, and compile on Command Prompt or Terminal. Compilation is made by "javac", for more information please visit [Oracle](http://docs.oracle.com/javase/7/docs/technotes/tools/windows/javac.html). 
For this book, I will also explain Integrated Development Environment Eclipse 4.2. Common ConceptEclipse is a universal programming platform used for creation of Integrated Development Environments (IDE). This platform is built on an open source. Although Eclipse can be used as an IDE for development programs in C++, C#, and other programming languages, - its great popularity is as a Java IDE, and it comes with built-in Java support.

The term Workbench refers to the desktop development environment. Eclipse's Workbench window contains one or more perspectives. A perspective defines the initial set and layout of views in the Workbench window. Each perspective provides a set of functionality aimed at accomplishing a specific type of task or works. Perspectives control what appears in certain menus and toolbars. Examples of perspectives are Java, Debug, C++, etc.

When the Workbench is launched for the first time, the first thing you see is a dialog that allows you to select where the workspace should be located. The workspace is the directory where your work will be stored. After workspace location is chosen, a Welcome window is displayed ("Welcome to Eclipse IDE for Java Developers"). You can then close the "Welcome" and, if necessary, change the workspace. To start Java development, you should choose necessary perspective (Window &#124; Open Perspective &#124; Other... &#124; Java). In most cases, this is default perspective.

If the workspace was created before, main window opens with several views according to chosen perspective. Unnecessary windows should close. You can continue to work on previous projects, or create a new one.Creating New Project
To create a new project, choose File &#124; New &#124; Project function of a main menu. Choose Java Project (Adapted menu provides short invocation: File &#124; New &#124; Java Project). Now press Next button. On the next step you must type project name and then press Finish button.

All Java functions can be implemented in the context of classes only. Now you should create a new class with static main() method that is a starting point of your Java program. Choose File &#124; New &#124; Class function to activate Class Wizard. It allows adding a new source file, which contains a description of a class. Now you type package name and class name. The new class should be public. It must contain main() method.

Assume that package called test contains class called TestClass. The Class Wizard generates the following code:

CODE :
package test;

public class TestClass {

/**
* @param args
*/
public static void main(String[] args) {
// TODO Auto-generated method stub

}
}

Parameter of this method (String[] args) provides access to command line arguments.What I mean is; you want to run the program via terminal/cmd, and you want to control your program with flags or give input values inline, you have to use command line arguments.

CODE :
c:\>myProgram -f arg3 arg4As you know, arrays are zero indexed. So, the very first argument is args[0] which is myProgram. "-f" is second argument, and is saved in args[1], so on.

Let's write a program which reads values for a and b, then returns c as a+b.

CODE :
package test;

import java.util.Scanner;

public class TestClass {

/**
* @param args
*/
public static void main(String[] args) {
Scanner scanner = new Scanner(System.in);
int a = scanner.nextInt();
int b = scanner.nextInt();
int c = a + b;
System.out.println(c);
}
}
For those who do not know what is import, and java.util.Scanner;
In order to read user input for variable a, and b, you have to read from console. So, you need some predefined methods from the Class (java.util.Scanner). Scanner class takes one argument (System.in). Since, you want to scan inputs on console, you have to define (System.in).

The result is printed onto standard output device (console) using println() method of out object. This object is a static field of System class.

As you can see, automatically generated source file called TestClass.java is stored in test subfolder. You cannot modify names of files and folders manually. Source file can contain the only non-nested public class with the same name as file name. The name of package is always the same as subfolder name. If you want to modify these names, you should use Refactor &#124; Rename... function.

New program should be launched using Run &#124; Run (Ctrl-F11) function of main menu, or Run as &#124; Java Application function of context menu. You can also create runtime configuration using Run &#124; Run Cofigurations...[i/] function. Choose Java application item and then press New. Choose necessary project name and class name and press Run button. Special view called Console appears in lower part of Eclipse window. Next times you can press [i]"Run project name" button (or Ctrl-F11).

If the project was previously created on another computer, you can copy it to the folder that represents the workspace, and then import your project using the import function (File &#124; Import... General &#124; Existing Project into Workspace). Import does not involve physical copying project files.Debugging Program
Debugging is used to find and fix run-time errors. Choose Window &#124; Open Perspective &#124; Debug function for debugging. You can add breakpoints (Run &#124; Toggle Line Breakpoint function, or Ctrl-Shift-B) . To run the program in debugging mode, use the Run &#124; Debug F11 function of main menu. You can also use Step Into (F5) and Step Over (F6) functions. You can obtain values of variables in hints.

The Run &#124; Resume function allows you to resume execution. The Run &#124; Terminate function terminates execution.Common Program Structure
There are no global variables in Java. That should avoid name conflicts. Neither are global functions or procedures, for that matter. There are only classes with fields (data members) and methods (member functions). A program in Java consists of one or more class definitions. One of these classes must define a method main() method, which is where the program starts running. Code of classes definition should be stored in text files with the Java extension. Class name (without extension) must match the name of a public class that defined in the file. Please keep in mind that capitalized and small letters are different.

Each class is compiled into its own file containing the binary code and Class extension. Unlike C++, this binary code is not a set of machine commands of particular processor, but so called byte code.

Compiled program can be executed on your computer only if so-called Java Virtual Machine is installed. Java Virtual Machine (JVM) is a special program, which provides interpretation of byte codes. This approach allows you to create applications that can be transferred from one operating environment (operating system, hardware platform) to another without additional recompilation. Unlike C++, Java does not provide static linking of binary code into an executable file. Linking (getting of a byte code from different files with the Class extension and interpreting of byte code) is always dynamic.Identifiers, Keywords, Reserved Words, and Comments
Like C + +, Java language is case-sensitive.

Java source code consists of tokens. Token is a sequence of characters that have some meaning. Separators (space, tab, new line, etc.) are placed between individual tokens.

Tokens are divided into the following groups:

- keywords (reserved words)
- identifiers
- literals (explicit constants)
- operators.

A set of keywords is finite. All keywords are reserved. Keywords cannot be used as identifiers. In Java there are also reserved words that are not keywords. They generally cannot be used. These words are const and goto.

Identifiers used for naming variables, functions and other software objects. The first character must be a letter or underscore character ("_"). Numbers also can be used as nonstarting characters. Using an underscore at the beginning of the name is not desirable.

It is advisable to use meaningful names that reflect the nature of the object or function. Do not use spaces inside identifiers. So if you need to create identifier with several words, these words should be written down together, starting second, third and other words with capital letters. For example, you can create a variable name:

thisIsMyVariable

Use English mnemonics for meaningful names. Names of classes and interfaces should begin with capital letters, and other names - only with lowercase letters. Names of static constants are composed of capital letters and an underscore characters, for example PI, CONST_VALUE etc.

The Java language supports three kinds of comments: C++-style (double slashes), C-style (/* */), and doc comments (/** */).

The JDK javadoc tool uses doc comments when preparing automatically generated documentation. The doc comments must be formatted according to Javadoc standards. You can add class and interface-level Javadoc comments as well as method, constructor and field-level comments. Doc comments must be placed before corresponding parts of code. Each comment consists of a description followed by one or more tags. If desired, you can use HTML formatting in your Javadoc comments. There is a special set of Javadoc tags such as @author, @param, @return, and so on. The tags allow standard representation of documentation concerning classes and methods. For example, the following comments before method;

CODE :
/**
* Returns file name with given index.<br>
* File names are stored in array of strings.
* @param i index
* @return file name.
* */
public String getFileName(int i) {
return names;
}

produce such fragment of HTML documentation file:

Method Details
getFileName

public String getFileName(int i)

Returns file name with given index.
File names are stored in array of strings.

Parameters:
i - index
Returns:
file name.
 Definition of Local Variables, and Primitive Types
Java supports local variables, declared within method definitions. These local variables behave just like local variables in C++. Here are examples of local variables definition.

CODE :
int i = 11;
double d= 0, x;
float f;
int j, k;

You can define and initialize local variables anywhere in a function body or other block of code. You cannot use the same variable names in outer and inner blocks:

CODE :
{
int i = 0;
{
int j = 1; // OK. j is local variable defined in inner block
int i = 2; // Error! A variable i is defined in outer block
}
}[i]You cannot declare variables without definition!

The final keyword can be applied to variables. Such variables cannot be modified.

CODE :
final int h = 0;The const keyword is a reserved word in Java. This word cannot be used in anyway.

Primitive, or basic, data types are classified as integer (for whole numbers), floating-point (for decimal numbers), character (for Unicode characters), or Boolean (specifying true / false). The definition of local variables of primitive types looks like one in C++ programming language. Here is primitive data types;Integers
byte : Byte-length integer : 8-bit
short : Short integer : 16-bit
int : Integer : 32-bit
long : Long integer : 64-bitReal Numbers
float : Single-precision floating point : 32-bit
double : Double-precision floating point : 64-bitOthers
char : A single Unicode character : 16-bit
boolean : A Boolean value (true or false)

In some languages (for instance, C and C++), the format and size of primitive data types may depend on the platform on which a program runs. In contrast, the Java programming language specifies the size and format of its primitive data types for all platforms.

Integer constants are represented by a sequence of decimal digits. The default type of such constants is int. It can be adjusted by adding letter L or l (long type) at the end of the constant. Integer constants can be represented in octal notation, in this case the first digit should be zero (0), and the number can only contain digits 0 ... 7\. Integer constants can also be represented in hexadecimal number system, in this case constant starts with 0x (or 0X) characters. To represent digits between 10 and 15, letters a, b, c, d, e and f (large or small) are used. For example:

CODE :
int octal = 023; // 19
int hex = 0xEF; // 239

A literal character value is any single Unicode character between single quote marks. You can use whether symbols of the current character set, or integer constant, which precedes the backslash character. It is a set of special control characters (these double characters are called escape sequences):

'\n' - a new line,
'\t' - horizontal tab,
'\r' - jump at the beginning of line,
'\'' - single quote,
'\"' - double quote,
'\\' - backslash character itself.

Constants of real types can be written whether with decimal point or in scientific notation and are double by default. If necessary, type of constant can be specified by adding suffix f or F for type float, d or D for type double. For example:

1.5f // 1.5 (float)
2.4E-2d // 0.25 (double)

You cannot assign floating point values to integer variables. A narrowing conversion - converting from a larger type (for instance, double) to a smaller type (for instance, float) - risks data. A narrowing conversion requires a special operation called a cast. For example:

CODE :
int i = 10;
float f = i; // Permissible conversion
long l = f; // Error! Narrowing conversion
long l1 = (long) f; // Type cast

Numeric literals without decimal point are constants of type int. Numeric literals with decimal point are constants of type double. To assign them to smaller types, you must use type cast:

CODE :
float f = 10.5; // Error! Narrowing conversion
float f1 = (float) 10.5; // Type cast

You can specify a long integer by putting an 'L' or 'l' after the number. 'L' is preferred as it cannot be confused with the digit '1'.The Java programming language has no unsigned data types.
What is an unsigned data type? Unsigned data type works like "unsigned int variable ", and this variables cannot contain any negative number.

The two Boolean literals are simply true and false. There is no conversion between the Boolean type and other types (specifically int). You cannot apply explicit typecasting for obtaining int from Boolean and vice versa.

The string constant is a series of characters enclosed in quotation marks. For example:

"This is a string"

Adding strings to variables of other types provides conversion of values into their string representation. In particular, this approach is used to output values of several variables. For example:

CODE :
int k = 1;
double d = 2.5;
System.out.println(k + " " + d); // 1 2.5Expressions and Operations
Java class includes fields (data) and methods (functions). Methods may contain statements, which in turn are composed of expressions. Expression consists of one or more operations.

Java supports almost all of the standard numeric, logical and comparison C++ operators. These standard operators have the same precedence and associativity in Java as they do in C++. Java supports the comma operator only in loop headings.

Java provides additional unsigned shift operator (>>>).

Since Java does not allow you to manipulate pointers directly, it does not support the reference and dereference operators *, ->, and & (address of).

There is no sizeof() operator in Java. In C++, the sizeof() operator tells you the number of bytes allocated for data items. Java does not need a sizeof( ) operator for this purpose because all the data types are the same size on all machines.Statements, Control over Program Execution
Statements are the smallest separate parts of the programming language. A program is a sequence of statements. Most of Java statements are similar to ones in C++.
Empty statement consists of one semicolon.
Expression statement is an expression that ends with a semicolon. For examples are as follows:

CODE :
k = i + j + 1; // assignment
Arrays.sort(a); // invocation of function
return; // termination of current function execution

Compound statement is a sequence of statements enclosed in braces. Compound statement is often referred to as block. Compound statement does not contain semicolon after closing brace. Syntactically block can be considered as a separate statement, but it also defines scope of visibility. Identifier declared inside the block, has a scope from the point of definition to the closing brace. Blocks can be nested in each other.

Selection statement is whether conventional statement or switch statement. Conditional statement is used in two forms:

CODE :
if (condition_expression)
statement1
else
statement2
//or
if (condition_expression)
statement1

If condition_expression is true then statement1 is executed, otherwise flow of control jumps to statement2 (in first form), or to the next statement (in second form). Unlike C + +, expression-condition can only be of type Boolean

Syntax of switch statement is the same as one in C++. In addition, Java 7 allows usage of string expressions in switch() header and string constants in case labels:

The break and continue statements, used alone, behave the same in Java as they do in C++. However, in Java, they may optionally be followed by a label that specifies an enclosing loop. The labeled forms of these statements allow you to "break" and "continue" any specified loop within a method definition, not only the nearest enclosing loop. For example:

CODE :
int a;
. . .
double b = 0;
label:
for (int i = 0; i < 10; i++) {
for (int j = 0; j < 10; j++) {
if (i + j + a == 0) {
break label;
}
b += 1 / (i + j + a);
}
}

The goto statement is not currently part of the Java language, but goto is a reserved word in Java. This word cannot be used in any way.

There is no typedef operator in Java. Java does not support C++ struct and union types.Packages and Functions
Java code does not require header files. All code is written inline. To avoid naming conflicts a mechanism of packages is used. In the Java language, packages are used to group classes.

A package is a collection of related classes and interfaces providing access protection and namespace management.

In the Java language, every class must be placed into a package. If the source code for a class doesn't have a package statement at the top, declaring the package the class is in, then the class is in the default package.

Physically each package is essential a folder with the same name as package. Subpackages are reflected to subfolders.

The first line of most Java programs is so called package statement. Only blank lines and comments can precede package statement.

CODE :
package package_name;

The package statement specifies which package the code in the file is part of. Java code that is part of a particular package has access to all classes (public and non-public) in the package, and all non-private methods and fields in all those classes. If the package statement is omitted from a file, the code in that file is part of an unnamed default package.

Java does not allow creation of global functions. Instead of this, you can create so called static methods within classes. In simplest case, definition of a static method can be as follows:

CODE :
static result_type function_name(list_of_formal_parameters) body

Parameters (arguments) of function defined in brackets are called formal parameters. Parameters, which are used by invocation of a function, are called actual parameters. Storage for formal parameters is allocated by invocation of a function. Appropriate cells are created in the program stack. Values of actual parameters are copied into these cells.

Function's body is a block (compound statement). In the following example, function returns sum of two arguments:

CODE :
static int sum(int a, int b)
{
int c = a + b;
return c;
}

We can omit c variable:

CODE :
static int sum(int a, int b)
{
return a + b;
}

To invoke function from another block, you should use its name followed by actual arguments (constants, variables, or expressions of appropriate types):

CODE :
int x = 4;
int y = 5;
int z = sum(a, b);
int t = sum(1, 3);

It can be no parameters in argument list:

CODE :
int zero()
{
return 0;
}

The call of such function also requires empty brackets:

CODE :
System.out.println(zero());

The return statement within function body causes termination of funcntion's execution. The expression after return keyword defines a value, which will be return from this function.

Sometimes, function returns no value. To declare such function, void keyword is used as resulting type.

CODE :
void hello()
{
System.out.println("Hello!");
}

In this case, you can omit return keyword in function's body. The return statement (without succeeding expression) allows termination of function before end of body. Function with void type can be called using separate statement only:

CODE :
hello();

Arguments can be transferred to functions by value only. Values of actual parameters cannot be changed within function's body:

CODE :
static void f(int k)
{
k++; // k = 2;
}

public static void main(String[] args) {
int k = 1;
f(k);
System.out.println(k); // k = 1;
}

Within a single class, you can create several functions with the same names. Such functions must have different argument lists (count and / or types of arguments). Such approach is called function overloading. If names and argument lists are the same, compiler produces compile error.

Function overloading is used when you want to apply analogous operations to different types using different algorithms:

CODE :
static int max(int a, int b) { } // Finding of maximum of two integers
static int max(double x, double y, double z) { } // Finding of maximum of three floating point values

In contrast to Java, you cannot create functions with default arguments.

Static functions within class can be invoked using function's name and list of actual parameters. To invoke static functions from another class, you should use the following syntax;

CODE :
class_name.function_name(actual_parameters);

In this way, you can only use methods of current package or java.lang standard package. This package provides classes with very useful functions. For instance, Math class provides numerical methods.

double pow(doublea,doubleb) : Calculation of a^b
double sqrt(doublea) : Calculation of square root
double sin(doublea) : Calculation of sine
double cos(doublea) : Calculation of cosine
double tan(doublea) : Calculation of tangent
double asin(doublea) : Calculation of arc sine
double acos(doublea) : Calculation of arc cosine
double atan(doublea) : Calculation of arc tangent
double exp(doublea) : Calculation of e^x
double log(doublea) : Calculation of natural logarithm (base e)
double abs(doublea) : Obtaining of the absolute value
int abs(inta) : Obtaining of the absolute value
long round(doublea) : Obtaining of the closest integer value

Usage :

Math.pow(x,y);
Math.sin(x);

If you want to access classes, which are defined in other packages (not in java.lang), you should use special prefix: package_name.class_name. If you want to access classes of nested packages, prefix will be more complex. To avoid use of full names, import directive is used. The import directive should be placed at the top of source file (or directly after package statement).

To import a class or an interface that's in a different package, you have three choices:

- Import the class or the interface (using import keyword).
- Import the entire package of which the class or the interface is a member (using import keyword).
- Static import

The following example demonstrates two of these choices.

CODE :
import java.io.FileReader; // Import of the class or the interface
import java.util.*; // Import of the entire package

public class TestClass {
public static void main(String[] args) {
java.io.FileWriter fw; // Fully qualified name
FileReader fr; // Direct access to the imported name;
ArrayList al; // ArrayList is a part of in java.util package
. . .
}
}

You never need an import java.lang.* statement to use the compiled classes in that package. This package is always imported automatically.

A new additional form of import that was added in Java 5 version, allows import of static element of a given class. Most programs that need numerical functions of Math class contain the following statement:

CODE :
import static java.lang.Math.*;

Now you can invoke static methods of Math class without extra qualifiers:

CODE :
double d = sin(1);Use of Command Line Arguments and Console Input
You can easy read command line arguments in Java program. For example, the following program shows value of the first command line argument on the screen:

CODE :
public static void main(String[] args) {
System.out.println(args[0]);
}

Command line arguments within main() function can be accessed in the form of array of strings (arrays and strings will be explained later). To access particular array elements, [] is used. To obtain numeric value, represented by string, static functions of Integer and Double classes are used. In the following example, program reads integer and real values from the command line and finds their sum.

CODE :
Public class TestArgs {

public static void main(String[] args) {
int n = Integer.parseInt(args[0]);
double x = Double.parseDouble(args[1]);
double y = n + x;
System.out.println(y);
}

}

Count of arguments typed in command line can be determined using args.length expression.

To set command line arguments in eclipse environment, Arguments tab of "Run" window is used. Necessary arguments should be typed in "Program arguments:" text area. String type arguments that contain several words should be quoted.Console Input and Output
You can use Scanner class of java.util package for data input from the keyboard at runtime. For keyboard input at runtime you can use Scanner class of java.util package. First, we need to create an object of this class by new operation.

CODE :
Scanner s = new Scanner(System.in);

Now this object can be used for reading data of different types. For example, next() function returns the next read value of String type, nextInt() allows to obtain an integer, nextDouble() reads and returns the number of double type. There are also functions nextBoolean(), nextByte(), nextShort(), nextLong(), nextFloat() etc.. All these functions cause termination of the program that resumes after reading corresponding value from the keyboard. For example:

CODE :
Scanner s = new Scanner(System.in);
double d = s.nextDouble();
int i = s.nextInt();
float f = s.nextFloat();

Output onto console window is based on using functions of out object declared within System class. The print() function can print results without jump to a new line, println() function moves cursor to a new line after output. You can also use the printf() for formatted output. Using this function is similar to use of one in C language.

The following sample program reads real and integer numbers, and displays their sum:

CODE :
import java.util.Scanner;

public class Average {

public static void main(String[] args) {
Scanner s = new Scanner(System.in);
int i = s.nextInt();
double d = s.nextDouble();
double sum = i + d;
System.out.println("Sum: " + sum);
}

}References
There is no pointer type in Java. The names of variables of non-primitive types are essentially names of references to corresponding objects. These non-primitive types are often called reference types because they are handled by reference. By comparison, primitive types are handled by value. Dereference * and -> operators do not exist in Java: primitive types are always passed by value; arrays and objects are always passed by reference. A reference type can never be cast to a primitive type or vice versa. Java does not allow you to do pointer arithmetic.

A special keyword null is used as a reference to nothing. This indicates "an absence of reference". The null value may be assigned to any variable of reference type.

You can create objects in dynamic store using new operator:

CODE :
SomeType st = new SomeType();

Because reference types are not passed by value, assigning one object to another in Java does not copy the value of the object. It merely assigns a reference to the object.

CODE :
SomeType a = new SomeType();
SomeType b = new SomeType();
a = b;

After these lines are executed, the variable a contains a reference to the object that b refers to. The object that a used to refer to is lost.

You don't need to deallocate objects. There is no delete operator in Java. A special mechanism called garbage collection is used for object's deallocation. The garbage collection is based of reference counting. This means that each object contains a reference counter, and every time a reference is attached to an object the reference count is increased. Every time a reference goes out of scope or is set to null, the reference count is decreased. The garbage collector moves through the entire list of objects and when it finds one with a reference count of zero it releases that storage.Arrays
Java arrays are zero indexed; that is, the array indexes start at zero. When declaring an array, the square brackets ([]) must come after the type, not the identifier. Placing the brackets after the identifier is legal but is not recommended in Java.

CODE :
int[] a;

In this example, a is a reference to an array that can be created later. The size of the array is not part of its type as it is in the C++ language. This allows you to declare an array and assign any array of appropriate objects to it, regardless of the array's length.

CODE :
int[] numbers; // declare a reference to an int array of any size
numbers = new int[10]; // numbers is a 10-element array
numbers = new int[20]; // now it's a 20-element array

Java supports single-dimensional arrays and multidimensional arrays (array-of-arrays). The following examples show how to declare different kinds of references to arrays:

CODE :
int[] numbers; // single-dimensional array
byte[][] scores; // two-dimensional array

Declaring references does not actually create the arrays. In Java, arrays are objects and must be instantiated. The following examples show how to create arrays:

CODE :
int[] numbers = new int[5]; // single-dimensional array
String[][] names = new String[5][4]; // rectangular array
byte[][] scores = new byte[5][]; // jagged array
for (int x = 0; x < 5; x++) {
scores[x] = new byte[x + 4];
}

The last example shows how to create two-dimensional array with different lengths of lines. The size of an array can be defined using integer constants and variables as well as expressions with integer result.

In Java, arrays hold elements as well as their count. The count of elements can be obtained using special read only field called 'length':

CODE :
int[] a = new int[10];
System.out.println(a.length); // 10

The typical array traversal is as follows:

CODE :
for (int i = 0; i < a.length; i++) {
a[i] = 0;
}

Java provides simple way to initialize arrays at declaration time by enclosing the initial values in curly braces ({}). Array members are automatically initialized to the default initial value for the array type if the array is not initialized at the time it is declared.

CODE :
int[] numbers = new int[] {1, 2, 3, 4, 5};
String[] names = new String[] {"Matt", "Joanne", "Robert"};

You can omit the new statement if an initializer is provided, like this:

CODE :
int[] numbers = {1, 2, 3, 4, 5};
String[] names = {"Matt", "Joanne", "Robert"};

Multidimensional arrays can be initialized in a similar manner:

CODE :
int[][] b = {{1, 2, 3},
{0, 0, 1},
{1, 1, 11},
{0, 0, 0}};

In this example, two-dimensional array contains four rows and three columns.

New form of for loop simplifies full array traversal. For instance, instead of

CODE :
int[] nums = {1, 2, 3, 4, 5, 6};
for (int i = 0; i < nums.length; i++)
System.out.println(nums[i]);

you can write

CODE :
int[] nums = {1, 2, 3, 4, 5, 6};
for(int n : nums)
System.out.println(n);

A new form can be applied for reading elements only (not for modification).

The assignment of one array to another is essentially copying of a reference. If you wont to assign all elements of array a to elements of array b, you must create a cycle. Class System offers you a simplest way of copying one array into another: an arraycopy() function:

CODE :
System.arraycopy(a, a_from, b, b_from, size);

This is equivalent to the following loop:

CODE :
for (int i = a_from, j = b_from; i < size + a_from; i++, j++) {
b[j] = a[i];
}

You can copy entire array a into b using such function call:

CODE :
System.arraycopy(a, 0, b, 0, a.length);Definition of Classes
Class is a structured data type that contains data members of different types, as well as functions for processing these data. Class definition contains of specifiers (e. g. public, final), class name, base class name, list of implemented interfaces, and class body enclosed in braces.

The class body contains declarations for the fields (data members in C++) and methods (member functions in C++). Variables and methods collectively are called members. Declaration of Java classes looks a lot like ones in C++. Here is an example of a simple class:

CODE :
class Rectangle {
double width;
double height;
double area() {
return width * height;
}
}

Note that you don't need to put in a semicolon after closing brace. Methods always go inside the class definition in Java, not outside with the :: operator as programmers usually do in C++.

Java initializes all fields with default values. In contrast to C++, Java allows fields' initialization on the spots:

CODE :
class Rectangle {
double width = 10;
double height = 20;
double area() {
return width * height;
}
}

You can create initialization block inside of class body:

CODE :
class Rectangle {
double width;
double height;
{
width = 10;
height = 20;
}
double area() {
return width * height;
}
}

Methods and fields can be declared with static keyword. A static method can be invoked without an instance of the class. Static fields can be accessed using class name. A static field is a kind of global variable declared in class scope. You don't need to define static members in global scope. You can initialize static fields on the spots:

CODE :
class SomeClass {
static double x = 10;
static int i = 20;
}

You can create initialization block for static fields:

CODE :
class SomeClass {
static double x;
static int i;
static {
x = 10;
i = 20;
}
}

In contrast to non-static initialization, creation of static fields occurs by the first use of a class. Java does not create static members for idle classes.

You can access static member using both class name and object name:

CODE :
SomeClass.x = 30;
SomeClass s = new SomeClass();
s.x = 40;

In Java methods, arguments are passed by value.

The this keyword refers to the current instance for which a method is called. All non-static methods implicitly obtain this reference. You can explicitly use this reference if you want to return reference to current object or need to prevent name conflicts. Static member functions do not have a this reference.Visibility
Like C++, Java supports private, protected, and public visibility levels. Class itself can be specified as public. In contrast to C++, Java requires separate definition of visibility for any member:

CODE :
public class SomeClass {
private int i;
private double x;
public void setI(int value) {
i = value;
}
public int getI() {
return i;
}
public void setX(double value) {
x = value;
}
public int getI() {
return i;
}
}

Access to private class members is restricted to methods within the class. There is no friend keyword in Java.

A public class member can be accessed by any function from any package.

Class members without visibility attributes have default access. The default access has no keyword, but it is commonly referred to as "friendly." All the other classes in the current package have access to the friendly member, but to all the classes outside of this package the member appears to be private.

Access to protected class members is restricted to methods within the class, member functions of derived classes, and to classes within current package.Constructors
A user instantiates a class by applying the new operator to the class constructor.

A constructor is a function whose name matches with the class name and does not define any return type. A class may define multiple constructors. If no constructor is defined by the class a default (no argument) constructor is automatically made available to the class. The default constructor initializes all the fields to their default values.

You can invoke constructor with arguments from another constructor using this keyword.

CODE :
class Rectangle {
double width;
double height;
Rectangle(double width, double height) {
this.width = width;
this.height = height;
}
Rectangle() {
this(10, 20); // calls another constructor
}
}

There are no destructors in Java. You can create a special method called finalize(). A Garbage Collector invokes finalize() method before the destruction of object. Object can be never destroyed by Garbage Collector, and therefore finalize() method can be never invoked.Strings
Strings in Java are instances of the java.lang.String class. The object of string type represents Unicode character string.

You can create a String object simply by enclosing characters in double quotes:

CODE :
String s = "The first string";

When one or both operands are of type string, the predefined addition operators concatenate the string representation of the operands

An instance of String is said to be immutable because its value cannot be modified once it has been created. Methods that appear to modify a String actually return a new String containing the modification. If you need to modify the contents of a String, you have to create a StringBuffer object from the String object, modify the contents of the StringBuffer, and then create a new String from the contents of the StringBuffer.

Some of the more important String methods are as follows:

length() : Returns the int number of characters in the string.
charAt(int index) : Returns the character at the specified index of the string.
equals(Object obj) : Compares this string to the specified object, returns true or false.
compareTo(String value) : Compares a string to the argument string. The result is a negative integer if this String object lexicographically precedes the argument string. The result is a positive integer if this String object lexicographically follows the argument string. The result is zero if the strings are equal.
indexOf(char ch) : Returns the index location of the first occurrence of the specified character.
substring(int beginIndex,int endIndex) : Returns a new string that is a substring of the string.
toLowerCase() : Returns the string in lowercase.
toUpperCase() : Returns the string in uppercase.

The following example demonstrates the use of methods for processing of string data.

CODE :
String s1 = new String("Hello World.");
int i = s1.length(); // i = 12
char c = s1.charAt(6); // c = 'W'
i = s1.indexOf('e'); // i = 1 (index of 'e' in "Hello World.")
String s2 = "abcdef".substring(2, 5); // s2 = "cde"
int k = "AA".compareTo("AB"); // k = -1

The Java language provides special support for the string concatenation operator ( + ), and for conversion of other objects to strings. The "plus" operator is used for string concatenation:

CODE :
String s1 = "first";
String s2 = s1 + " and second";

If one of operands is not a string type value, Java automatically obtains its string representation.

CODE :
int n = 1;
String sn = "n is " + n; // "n is 1"
double d = 1.1;
String sd = d + ""; // "1.1"

You can also use "+=" operator.Classes Integer and Double
The Integer and Double classes wrap values of the primitive types int and double in appropriate objects. In addition, those classes provide several methods for converting a numeric values to a String and a String to numbers, as well as other constants and methods useful when dealing with integers and doubles.

The Double.parseDouble() function returns a new double initialized to the value represented by the specified string:

CODE :
String s = "1.2";
double d = Double.parseDouble(s);

Functions Integer.parseInt() and Boolean.parseBoolean() provide analogous functionality.

In Java 5 (JDK 1.5) objects of Integer type can be initialized using expressions of int type. Such object can be also used in expressions as integer values. Constants and expressions of int type can be added to lists and containers instead of Integer objects that will be created automatically. In previous versions, you should write:

CODE :
Integer m = new Integer(10); // initialization of Integer object
int k = m.intValue() + 1; // stored value is used in an expression
// Creation of an array:
Integer[] a = {new Integer(1), new Integer(2), new Integer(3)};
List li = new ArrayList();
a[2] = new Integer(4); // replacing given element with new object
// extraction of Integer object and using of its value:
int i = a[1].intValue() + 2;

In Java 5, this code can be more simply:

CODE :
Integer m = 10; // initialization of Integer object
int k = m + 1; // stored value is used in an expression
// Creation of an array:
Integer[] a = {1, 2, 3};
a[2] = 4; // replacing given element with new object
// extraction of Integer object and using of its value:
int i = a[1] + 2;

The same rules can be applied to Double and Boolean types. In fact, objects of Integer, Double, and Boolean can be used instead of int, double, and Boolean variables.Class Composition
Class composition assumes creation of classes, which contain object of other classes as class fields. In Java, you cannot place objects into another object. Only references are allowed here. You can create objects direct after the declaration or in constructors.

CODE :
ClassX {
}

class Y {
}

class Z {
X x = new X();
Y y;
Z() {
y = new Y();
}
}
I think, details are the most important part of programming. Thus, i tried to explain every single detail.
I hope I did not forget something, and you find this Book useful. Feel free to ask me questions if you don't understand.Email me at [renuxsofttech@gmail.com](mailto:renuxsofttech@gmail.com) |
|  |