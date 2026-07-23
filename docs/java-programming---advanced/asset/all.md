![](Image00000.jpg)

Java Programming - Advanced

# Chapter 1: An Overview of Java

OBJECT ORIENTED PROGRAMMING

Java's core is object-oriented programming (OOP). All Java programs are, in fact, at least partially object-oriented. OOP is an integral part of Java. It is important to be familiar with its principles before you start writing simple Java programs. This chapter will discuss the theoretical aspects and applications of OOP.

TWO PARADIGMS

Computer programs are composed of code and data. A program can also be conceptually organized around either its code or its data. This means that some programs are written around what is happening, while others are written around who is being affected. These two paradigms govern how programs are constructed. The process-oriented model is the first. This model describes a program in a series or steps (that is code). This model is code that acts on data. This model is used to great effect in procedural languages like C.

ABSTRAACTION

Abstraction is an essential component of object-oriented programming. Abstraction is how humans manage complexity. People don't think of a car, for example, as a collection of thousands of parts. It is a clearly defined object that has its own behavior. This abstraction allows people the freedom to drive a car to the grocery without worrying about the intricate parts. They don't have to pay attention to the intricate details of the engine, transmission, or braking system. They can instead use the entire object.

ENCAPSULATION

Encapsulation is a mechanism that binds code and data together and protects them from misuse and interference. Encapsulation can be described as a protective wrapper that blocks code and data being accessed by code outside of the wrapper. The interface that controls access to code and data within the wrapper is well-defined. This is analogous to an automobile's automatic transmission. This information contains hundreds of bits about your engine. It includes the amount of acceleration, pitch of the surface, and position of the shift lever.

POLYMORPHISM AND ENCAPSULATION WORK TOGETHER

Polymorphism, inheritance, and encapsulation can be combined to create a programming environment that is far more robust than the process-oriented model. The basis for reuse of the code you have spent time developing and testing is a well-designed hierarchy. Encapsulation makes it possible to move your implementations without breaking any code that relies on your public interface. Polymorphism allows for the creation of clean, sensible, readable and resilient code.

THE FIRST SIMPLE PROGRAM

Let's now look at actual Java programs after we have covered the basics of Java object-oriented underpinnings. Let's begin by running and compiling the following sample program. This takes a bit more effort than you might think.

/*

This Java program is very simple.

This file is called "Example.java".

*/

{class Example Class Example

// Start your program with a call back to main()

{public static void main(String args[]) public static void main (String args[]).

System.out.println("This is a simple Java program. "

|}

|}

ENTERING THE PROGRAM

The name of the file containing the source code for a program in most computer languages is irrelevant. Java is different. Java's first lesson is to understand that the name of a source file is extremely important. This is an example of what the source file name should look like.java. Let's find out why. A compilation unit is what Java calls a source file. A text file that contains one, or more, class definitions. Java compiler requires that source files use the extension.java.

COMPILING

Execute the compiler javac to compile the Example program.

C.>javac Examples.java

The javac compiler creates an example.class file that contains the bytecode version. The Java bytecode, which is an intermediate representation of your program and contains instructions that the Java Virtual Machine will execute, is what we discussed earlier. The output of javac therefore is not code that can directly be executed.

You must use Java's application launcher (called java) to actually run the program. As shown below, you need to pass the class name Example as an argument on the command line.

C:\>java Example

The following output will be displayed when the program is executed:

This Java program is very simple.

THE IF STATEMENT

The Java if statement functions in the same way as any other language's IF statement. It is syntactically identical with the if statements of C, C++ and C#. This is its simplest form:

If(condition) statement;

This is condition. It's a Boolean expression. If condition is true, the statement will be executed.

False condition means that the statement can be ignored. Here's an example:

if (num 100); System.out.println ("num is less than 100");

/*

Show the if.

This file should be called "IfSample.java".

*/

{class IfSample class IfSample

{public static void main(String args[]) public static main(String arguments[])

intx,y;

x = 10,

y = 20,

if (x y). System.out.println ("x is less than or equal to y");

x = * 2;

if(x == y) System.out.println("x now equal to y");

x = * 2;

if(x > y) System.out.println("x now greater than y");

// This won't show anything

if(x == y) System.out.println("you won't see this");

| }

| }

# Chapter 2: Data Types and Variables.

THE PRIMITIVE TTYPES

Java supports eight types of primitive data: byte and short, int, long; char, float; double; and boolean. Both simple and primitive types are commonly used to refer to the primitive types. You can group them into four categories:

* Integers The group includes byte and short as well as int and long which are whole-valued signed numbers.

* Floating numbers This group includes double and float, which are numbers with fractional precision.

INTEGERS

Java has four types of integers: byte (short), int (int), and long (long). All these integer types can be signed and have positive or negative values. Java doesn't support unsigned, positive only integers. Many other computer languages can support both signed integers and unsigned integers. Java's developers felt unsigned integers were unnecessary. They felt that unsigned integers were unnecessary because they could be used to describe the behavior of high-order bits, which define the sign of an integer value. Java adds a special "unsigned rightshift" operator to clarify the meaning of high-order bits. This eliminated the need to have an unsigned integer type.

FLOATING POINT TYPES

When evaluating expressions with fractional precision, floating-point numbers (also known as real numbers) are used. Calculations such as square root or transcendentals like sine and cosine can result in values whose precision requires a floating point type. Java implements the standard (IEEE-754) set of floating-point operators and types. There are two types of floating-point types: float and double. These represent single- or double-precision numbers.

CHARACTERS

Java uses char as the data type to store characters. C/C++ programmers need to be aware that char in Java may not be the same as C++ or C++. C/C++ has char that is 8 bits in width. Java, however, does not have this limitation. Java instead uses Unicode to represent characters. Unicode is a fully international character set, which can represent all characters in all human languages. Unicode is the unification of many character sets such as Latin Greek, Arabic Cyrillic Hebrew, Cyrillic Hebrew, Katakana and Hangul. It requires 16 bits to accomplish this task. Java char is therefore a type of 16 bits. A char can be anywhere from 0 to 65,536. There are no negative characters.

BOOLEANS

Java supports a primitive type called boolean for logical values. It can only have one of the two possible values, true/false. This type is returned by all relational operations, as in the case a b. The type required by conditional expressions such as for and if is boolean.

// Showcase boolean values.

{class BoolTest BoolTest class

{public static void main(String args[]) public static void main (String args[]).

boolean b

b = false

System.out.println("b is " + b);

b = true

System.out.println("b is " + b);

// A boolean value may control the if statem

if(b) System.out.println("This is executed. ";

b = false

if(b) System.out.println("This is not executed. ");

// The result of a relational operation is a boolean number

System.out.println("10 > 9 is " + (10 > 9));

|}

|}

FLOATING POINT LITERALS

Floating-point numbers are decimal values that include a fractional component. They can be expressed either in scientific or standard notation. Standard notation is composed of a whole-number component, followed by a decimal and then a fractional component. 2., 3.14159, 0.6667, and 0.6667 are valid floating-point numbers in standard-notation. A standard-notation floating-point number and a suffix specifying a power of 10, which is how the number should be multiplied in scientific notation. An E or e is followed by a decimal, which can be either positive or negative.

DYNAMIC INSITIALIZATION

While the previous examples used constants as initializers for variables, Java allows variables that are declared to be initialized dynamically using any expression that is valid at the time they are declared. Here is an example program that calculates the length of the hypotenuse in a right triangle based on the lengths of its opposing sides.

// Demonstrate dynamic initialization.

{class DynInit DynInit class

{public static void main(String args[]) public static void main (String args[]).

Double a = 3.0, double b = 4.

// c is dynamically initialized

Double c = Math.sqrt (a* a + b* b);

System.out.println("Hypotenuse is " + c);

|}

|}

TYPE CONVERSION AND CASTING

You may have some programming experience. It is quite common to assign one type of value to another type of variable. Java will automatically convert the types if they are compatible. It is possible, for example, to assign an int value a long variable. But not all types are compatible and therefore not all type conversions can be implicitly permitted. There is, for example, no automatic conversion from double to bytes. It is possible to convert between incompatible types. Casts are used to convert between incompatible types. Let's take a look at casting and automatic type conversions.

# Chapter 3: Operators

THE BASIC ARITHMETIC OPERATORS

The basic arithmetic operations--addition, subtraction, multiplication, and division-- all behave as you would expect for all numeric types. There is also a unary form of the minus operator that negates its one operand. When the division operator is applied on an integer type, the result will not contain a fractional component.

// Demonstrate basic arithmetic operators.

{class BasicMath BasicMath class

{public static void main(String args[]) public static void main (String args[]).

// Arithmetic with integers

System.out.println("Integer Arithmetic");

int a = 1 + 1.

int b = * 3

int c = 4;

int d = c - a;

int e = -d;

System.out.println("a = " + a);

System.out.println("b = " + b);

System.out.println("c = " + c);

System.out.println("d = " + d);

System.out.println("e = " + e);

// Arithmetic with doubles

System.out.println("\nFloating Point Arithmetic");

double da = 1 + 1;

double db = da * 3;

double dc = db / 4;

double dd = dc - a;

double de = -dd;

System.out.println("da = " + da);

System.out.println("db = " + db);

System.out.println("dc = " + dc);

System.out.println("dd = " + dd);

System.out.println("de = " + de);

|}

|}

THE MODULUS OPERATOR

Modulus operator % returns the remainder of a division operation. This operator can be used to both floating-point and integer types. This example program illustrates the %.

// Demonstrate % operator.

class Modulus {

{public static void main(String args[]) public static void main (String args[]).

int x = 42

double y = 42.25;

System.out.println("x mod 10 = " + x % 10);

System.out.println("y mod 10 = " + y % 10);

|}

|}

This program will produce the following output when it is run:

x mod 10 = 2

y mod 10 = 2.25

THE BITWISE OPERATORS

Java has several bitwise operators that can be used to integer types long, int and short, char, byte, and byte. These operators are able to act on the bits of individual operands.

THE BITWISELOGICAL OPERATORS

, ^, and ~. Below is a table that shows the results of each operation. The following table shows the outcome of each operation.

The Bitwise NOT

The bitwise complement is also known as the unary NOT operator. inverts all bits of its operand. The following bit pattern is found in the number 42:

00101010

It is

11010101

After the NOT operator has been applied.

THE UNSIGNED RIGHT SLIP

As you can see, the >> operator fills the high order bit automatically with its previous contents every time there is a shift. This preserves the sign value. Sometimes, however, this can be undesirable. If you're shifting something that doesn't represent a numerical value, sign extension may not be desired. This is often the case when working with pixels-based values or graphics. These cases will require you to shift a zero into a high-order bit regardless of its initial value. This is called an unsigned shift. Java's unsigned shift-right operator >>>, is used to accomplish this. It always shifts zeros into high-order bits.

SHORT-CIRCUIT OPERATORS LOGICAL OPERATORS

Java has two unique Boolean operators that are not available in other languages. These are secondary versions to the Boolean AND/OR operators, and are also known as short-circuit logic operators. The OR operator returns true when A is true regardless of what B is, as you can see in the table. The AND operator returns false if A is false. This is useful when the right hand operand depends on its value in order to function correctly.

# Chapter 4: Control Statements

JAVA SELECTION STATEMENTS

Java supports two types of selection statements: switch and if. These statements can be used to control the execution of your program based on conditions that are only known during runtime. These statements will surprise you with their power and flexibility.

If

In Chapter 2, the if statement was introduced. This chapter explains it in greater detail. Java's conditional branch statement is the if statement. It can be used for routing program execution along two paths. This is the if statement in its general form:

Statement 1; if (condition)

Other statement2

ITERATION STATEMENTS

Java's iteration clauses are for do-while and while. These statements create loops, which we call them. A loop executes the same set instructions repeatedly until it reaches a termination condition. Java provides a loop that can be used to meet any programming need.

While

The most fundamental Java loop statement is the while loop. It repeats a block or statement while its controlling expression remains true. This is the general form of it:

{while(condition) While(condition)

// Body of loop

|}

SOME TO LOOP VARIATIONS

There are many variations of the for loop that can increase its power and utility. It is flexible because its three sections--the initialization and conditional tests, as well as the iteration-simply can be used for any purpose. The three sections of for can be used for whatever purpose you want.

boolean done = false;

{for(int i=1; !done; i++) for(int: i=1!done i++)

//

If(interrupted()) done = true

|}

THE FOR-EACH VARIATION OF THE FOR LOOP

JDK 5 introduced a second form for that implements a style loop called "for-each". The for-each concept is becoming an expected feature in modern programming languages. Foreach loops are designed to cycle through an object collection, such as an array in a strictly sequential fashion from start to end. Java, unlike C# which implements a for-each loop using the keyword foreach. Java enhances the for statement to add the for-each capability.

USEING BREAK TO EXIT LOOP

Break can be used to force the termination of a loop. This bypasses the conditional expressions and any code that remains in the loop's body. If a break statement is found within a loop, it terminates the loop and program control is resumed at the next statement after the loop. Here's an example:

// Use break to exit a loop.

{class BreakLoop Class BreakLoop

{public static void main(String args[]) public static void main (String args[]).

{for(int i=0; i<100; i++) for(int:i=0;i100;i++)

If(i == 10), break; // Terminate loop if you are 10.

System.out.println("i: " + i);

|}

System.out.println("Loop complete. System.out.println("Loop complete.

|}

|}

BREAK AS A FORMAT OF GOTO

The break statement can be used to create a civilized version of the goto statements. It is also useful with loops and switch statements. Java doesn't have a goto clause because it allows you to branch in an unstructured and arbitrary way. This makes it difficult to understand and maintain goto-ridden Java code. This also prevents some compiler optimizations. However, there are a few instances where the goto can be useful and legal for flow control. The goto is useful in situations where you need to exit from a complex set of loops. Java provides an extended form of the break statement to handle these situations. This form of break allows you to break out of a block of code. These blocks do not have to be in a loop. They can be any type of block.

CONTINUE

Sometimes, it can be useful to force an earlier iteration of the loop. This means that you may want to keep running the loop, but not process the rest of the code within its body. This is essentially a geto that goes just beyond the body of the loop to the end. This is accomplished by the continue statement. A continue statement allows control to be transferred to the conditional expression controlling the loop in while and do-while loops. For loops have control transferred to the conditional expression and the iteration section of the for statement. Any intermediate code is ignored for all three loops.

# Chapter 5: Inheritance

INHERITANCE

Basics You can inherit a class by simply incorporating the definition of one class into the other using the extends keyword. Let's take a look at a quick example to show you how. This program creates A superclass and B subclasses. You can see how the keyword extends was used to create a subclass for A.

// An example of inheritance.

// Create a Superclass.

{class A Class A

int i,j;

{void showij() void showij()

System.out.println("i and j: " + i + " " + j);

|}

|}

// Create a subclass of class A by extending it.

{class B extends A Class B extends to A

Int k

{void showk() void showk()

System.out.println("k: " + k);

|}

void sum() {

System.out.println("i+j+k: " + (i+j+k));

|}

|}

MEMBER ACCESS AND INHERITANCE

A subclass can access all members of its superclass even though it includes the entire superclass. However, the superclass members that have been declared private cannot be accessed by the subclass. Consider the following class hierarchy example:

Private members are not included in a class hierarchy.

Private to their class

This program has an error.

Compile.

*/

// Create a Superclass.

{class A Class A

int i, // public by default

private int.j; // private A

void setij(int x, int y) {

i = x

j = y

|}

|}

// A's J is not available here.

{class B extends A Class B extends to A

Int Total

void sum() {

total = i+j; // ERROR j is not available here

|}

|}

{class Access Class Access

{public static void main(String args[]) public static void main (String args[]).

B subOb = new BB()

subOb.setij(10, 12);

SubOb.sum()

System.out.println("Total is " + subOb.total);

|}

|}

A SUPERCLASS VARIEABLE CAN REFERENCE A SUBCLASS OBJECT

Any subclass that is derived from a superclass can have a reference to a reference variable in a superclass. This aspect of inheritance is very useful in many situations. Consider the following:

class RefDemo {

{public static void main(String args[]) public static void main (String args[]).

BoxWeight weightbox = New BoxWeight (3, 5, 7, 8.37);

Box plainbox = new box()

double vol;

Vol = weightbox.volume()

System.out.println("Volume of weightbox is " + vol);

System.out.println("Weight of weightbox is " +

Weightbox.weight

System.out.println();

// Assign BoxWeight reference Box reference

Plainbox = Weightbox

vol = plainbox.volume() // OK, volume() as defined in Box

System.out.println("Volume of plainbox is " + vol);

/* This statement is invalid due to plainbox

Does not determine a weight member. */

// System.out.println("Weight of plainbox is " + plainbox.weight);

|}

|}

SUPER

The classes derived form Box were not implemented in the above examples as well as as as effectively as they could. BoxWeight's constructor explicitly sets the BoxWeight width, height, depth fields ( ). This duplicate code is not only inefficient but also implies that subclasses must have access to these members. There will be occasions when you want to create a superclass which keeps its implementation details private (i.e., its data members). This would prevent a subclass from accessing or initializing these variables directly. Java has a solution for this problem, since encapsulation is an OOP primary attribute.

CREATING A MULTILEVEL HIERARCHY

We have used simple class hierarchies, which consist only of a superclass or subclass. You can create hierarchies with as many layers as you want. It is acceptable to use a subclass of another class as a superclass. If you have three classes A, B and C, then C could be a subclass or subclass of C. This type of situation means that each subclass inherits all the traits from all its superclasses. C inherits all aspects from A and B. The following program illustrates how a multilevel hierarchy is useful.

CONSTRUCTORS ARE Dubbed

In what order is the class hierarchy's constructors called when it is created? If A is a subclass of B, and A is a superclass, how are A's constructors called? Or vice versa. In a class hierarchy constructors are called in the order of their derivation from superclasses to subclasses. Super() must be executed first in subclass constructors. This order remains the same regardless of whether super( ) has been used. If super() isn't used, the default or parameter-less constructor for each superclass will be executed.

METHOD OVERRIDING

If a method within a subclass has the exact same type signature and name as a superclass method, it is considered to be overriding the method in that superclass. If an overridden method can be called from within a class, it will always refer the subclass's version. The superclass version will be hidden.

DYNAMIC METHOD DISPATCH

Although the examples shown in the previous section illustrate the mechanics and power of method overriding they don't show it. If method overriding were limited to a name space convention, it would be a curiosity at best and of no real value. This is not true. Method overriding is the foundation for dynamic method dispatch, one of Java's most powerful concepts. Dynamic method dispatch refers to the way that a call for an overridden method can be resolved at run-time, not compile time. This is the way Java implements runtime polymorphism. Dynamic method dispatch is crucial.

WHY OVERRIDDEN METHODS?

Overridden methods, as mentioned earlier, allow Java to support runtime polymorphism. Polymorphism is crucial to object-oriented programming because it allows a general type to specify methods that are common to all its derivatives while allowing subclasses the ability to define specific implementations of any or all of these methods. Java also implements polymorphism's "one interface, many methods" concept by using overridden methods.

# Chapter 6: Exception Handling

EXCEPTION-HANDLING FUNDAMENTALS

Java exceptions are objects that describe an unusual (or error) condition in a piece or code. An exception object is created when an unusual condition occurs and is thrown in the code that caused it. The method that created the exception may either handle it or pass it along. The exception will be caught and processed in any case. You can either generate exceptions by the Java runtime system or manually by your code. Java throws exceptions when there are fundamental errors. These exceptions can be caused by Java breaking the Java language rules or the constraints of Java's execution environment. Most commonly, exceptions that are manually generated are used to notify the caller of a method about an error condition.

EXCEPTION TTYPES

All exception types are subclasses the built-in class Throwable. Throwable is the highest level of the exception class hierarchy. Two subclasses immediately below Throwable divide exceptions into distinct branches. Exception heads one branch. This class is for special conditions that user programs must catch. This class is also where you'll subclass it to create custom exception types. RuntimeException is a subclass of Exception. These exceptions are automatically created for your programs and include invalid array indexing and division by zero.

EXCEPTIONS

It is important to understand what happens when you don’t handle exceptions before you can learn how to handle them in your program. This program contains an expression that causes a divide by zero error.

{class Exc0 Class Exc0

{public static void main(String args[]) public static void main (String args[]).

int d = 0;

int a = 42/d;

|}

|}

TRY AND CATCH

The Java run-time system's default exception handler is great for debugging but you may want to manually handle any exceptions. Doing so provides two benefits. It allows you to correct the error. It prevents the program's termination from happening automatically. Your program would cause confusion for most users if it stopped running and printed stack trace information whenever an error occurred. It is easy to avoid this. You can prevent and manage a runtime error by simply including the code you wish to monitor in a try block. Include a catch clause immediately after the try block that specifies the exception type you want to catch.

DISPLAYING THE DESCRIPTION OF A EXCEPTION

Throwable overrides toString(.) method (defined in Object). It returns a string that contains a description for the exception. This description can be displayed in a println() statement by passing the exception as an argument. This is an example of how you can rewrite the catch block from the previous program.

{catch (ArithmeticException e) catch (ArithmeticExceptione e)

System.out.println("Exception: " + e);

// Set a = 0 to continue

|}

This message is displayed for each divide-byzero error that occurs when this version is used in the program.

Exception: java.lang.ArithmeticException: / by zero

MULTIPLE CRATCH CLAUSES

Sometimes, multiple exceptions can be raised with a single code block. This situation can be handled by specifying multiple catch clauses that each catch a different type. Each catch statement that is executed after an exception has been thrown is reviewed in order. Once one catch statement is executed, all others are ignored and execution continues after the "try/catch" block.

NESTED TERY STATEMENTS

You can nest the try statement. A try statement can be placed inside a block of another try. The context of the exception is added to the stack each time a try is entered. If the catch handler for an exception in an inner try statement is not present, the stack will be unwound. The catch handlers for the next try statement are checked for a match. The process continues until either one of the catch phrases succeeds or all the nested attempt statements have been exhausted. If there is no match for a catch statement, the Java runtime system will handle the exception.

JAVA’S BUILT IN EXCEPTIONS

Java defines many exception classes within the standard package Java.lang. Several of these exception classes have been covered in the examples. These exceptions can be subclasses or variants of RuntimeException, which is the most common. These exceptions, as previously explained, do not need to be added to any method's throws. These exceptions are known in Java as unchecked. This is because the compiler doesn't check to see whether a method handles these exceptions. Table 10-1 lists the unchecked exceptions in Java.lang. Table 10-2 lists the exceptions that java.lang has defined that must be included into a method’s throws list. These are known as checked exceptions. Java also defines other types of exceptions related to its class libraries.

# Chapter 7: String Handling

THE STRING CONSTRUCTORS

There are several constructors for the String class. You can call the default constructor to create an empty String. You can use this example:

String s = new String();

String will be created with no characters.

You will often need to create strings with initial values. This is possible with the help of the String class, which provides many constructors. The constructor shown below can be used to create a String that is initialized with an array of characters.

String(char chars[ ])

Here's an example:

char chars[] = 'a', 'b', 'c' ;

String s = new String(chars);

STRING CONSTRUCTORS ADOPTED BY J2SE5

J2SE 5 has two constructors for String. This is the first constructor that supports extended Unicode characters and can be seen here:

String(int codePoints[?], int startIndex and int numChars).

CodePoints is an array containing Unicode code points. The range that starts at startIndex runs for numChars is used to create the string.

This second constructor is compatible with the StringBuilder class. It can be seen here:

String(StringBuilder strBuildObj).

This creates a string from the StringBuilder passed to strBuildObj.

STRING LENGTH

The length of a string refers to the number of characters it contains. This value can be obtained using the length( ), shown here.

int length( )

Because there are three characters in the string, s:3, the following fragment prints "3".

char chars[] = 'a', 'b', 'c' ;

String s = new String(chars);

System.out.println(s.length());

SPECIAL STRING OPERATIONS

Strings are an important part of programming so Java provides special support for string operations in the syntax. These operations include automatic creation of String instances from string literals and concatenation multiple String objects using the + operator. They also allow for the conversion of data types to a String representation. Java performs all these functions by using explicit methods, but Java makes it easy for programmers and adds clarity.

CHARACTER XTRACTION

String objects can have characters extracted from them in a variety of ways using the String class. We will examine each one. The characters within a String object can't be indexed like a character array. However, many String methods use an offset (or index) to the string to perform their operations. String indexes start at zero, just like arrays.

You can use the charAt ( ) method to extract one character from a String. This is its general form:

char charAt (int where).

Where is the index of your desired character? The where value must not be negative and should specify a place within the string. charAt() returns the character at specified location. Take, for example.

char ch;

ch = "abc".charAt(1)

The value "b" is assigned to ch.

SEARCHING STRENGS

Two methods can be used by the String class to search for a specific character or substring in a string.

* indexOf() Searches for substrings or characters that are first encountered.

* lastIndexOf ( ) Searches for characters or substrings that have been found in the past.

Both of these methods can be overloaded in many different ways. The methods return the index where the character or substring were found. If the method fails, it returns -1.

Use this search tool to find the first appearance of a particular character.

int indexOf (int ch).

Use this tool to search for the last appearance of a character.

int lastIndexOf (int ch).

Here, ch stands for the character being sought.

Use this method to search for substrings that occur in their first or last instances.

int indexOf (String str)

int lastIndexOf (String str).

DATA CONVERSION Using VALUEOF ( )

ValueOf( ), which converts data from an internal format to a human-readable format, is a method. It is a static method, which is loaded within String for all Java's built in types. This allows each 372 Part 2: The Java Library type to be properly converted into a string. valueOf( ( ) is also loaded for type Object so that any object you create can be used as argument. (Remember that Object is a superclass of all classes. Here are some examples of its forms:

static String valueOf(double num)

static String valueOf(long num)

static String valueOf(Object ob)

static String valueOf(char chars[ ])

STRINGBUILDER

J2SE 5 introduces a new string class into Java's already impressive string handling capabilities. StringBuilder is the new class. It is identical to StringBuffer, except that it isn't synchronized. This means it isn't thread-safe. StringBuilder has a faster performance. StringBuffer is recommended for multithreading cases.