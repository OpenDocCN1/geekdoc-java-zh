![](Image00018.jpg)

LEARN KOTLIN QUICKLY

AND

PYTHON CODING PRACTICE EXERCISES

CODING FOR BEGINNERS

WITH HANDS ON PROJECTS

BY

J J TAM

[Introduction to Kotlin](#text00003.html__Toc77010732)

[Kotlin: Hello World program](#text00004.html__Toc77010733)

[Setting up Kotlin in Eclipse](#text00005.html__Toc77010734)

[Define variables in Kotlin](#text00006.html__Toc77010735)

[Data types in Kotlin](#text00007.html__Toc77010736)

[Kotlin: nullable types](#text00008.html__Toc77010737)

[Kotlin: Numbers](#text00008.html__Toc77010738)

[Kotlin: Characters](#text00009.html__Toc77010739)

[Kotlin: Convert character to Int](#text00009.html__Toc77010740)

[Kotlin: Booleans](#text00009.html__Toc77010741)

[Kotlin: Strings](#text00010.html__Toc77010742)

[Kotlin: String template expressions](#text00011.html__Toc77010743)

[Kotlin: Arrays](#text00012.html__Toc77010744)

[Kotlin: Define array of nulls](#text00012.html__Toc77010745)

[Kotlin: Define array using factory function](#text00012.html__Toc77010746)

[Kotlin: Print array elements](#text00013.html__Toc77010747)

[Kotlin: Bit wise operators](#text00014.html__Toc77010748)

[Kotlin: Logical Operators](#text00015.html__Toc77010749)

[Kotlin: Control flow statements](#text00017.html__Toc77010750)

[Kotlin: if statement](#text00018.html__Toc77010751)

[Kotlin: if-else statement](#text00018.html__Toc77010752)

[Kotlin: if-else if-else](#text00018.html__Toc77010753)

[Kotlin: when expression](#text00019.html__Toc77010754)

[Kotlin: Using when as if-else if ladder](#text00020.html__Toc77010755)

[Kotlin: Use When as expression](#text00021.html__Toc77010756)

[Kotlin: for loop](#text00022.html__Toc77010757)

[Kotlin: while, do-while loops](#text00023.html__Toc77010758)

[Kotlin: break statement](#text00024.html__Toc77010759)

[Kotlin: continue statement](#text00025.html__Toc77010760)

[Kotlin: classes and objects](#text00026.html__Toc77010761)

[Kotlin: Declaring properties](#text00027.html__Toc77010762)

[Kotlin: getters & setters to properties](#text00028.html__Toc77010763)

[Kotlin: Define member functions of class](#text00029.html__Toc77010764)

[Kotlin: const: Compile time constants](#text00031.html__Toc77010765)

[Kotlin: const vs val](#text00032.html__Toc77010766)

[Kotlin: lateinit : Late initialized properties](#text00033.html__Toc77010767)

[Kotlin: Constructors](#text00034.html__Toc77010768)

[Kotlin: Secondary Constructors](#text00035.html__Toc77010769)

[Kotlin: Passing default values to primary constructor](#text00036.html__Toc77010770)

[Kotlin: Define private primary constructor](#text00037.html__Toc77010771)

[Kotlin: How to create Object](#text00038.html__Toc77010772)

[PYTHON CODING EXERCISES](#text00040.html__Toc77010773)

[PYTHON String – Exercises](#text00040.html__Toc77010774)

[Python: Reverse a string](#text00040.html__Toc77010775)

[Remove a newline in Python](#text00041.html__Toc77010776)

[Find the common values](#text00042.html__Toc77010777)

[Python Data Type: List – Exercises](#text00043.html__Toc77010778)

[Python: Sum all the items in a list](#text00043.html__Toc77010779)

[Get the largest number from a list](#text00044.html__Toc77010780)

[Remove duplicates from a list](#text00045.html__Toc77010781)

[Python Data Types: Dictionary – Exercises](#text00046.html__Toc77010782)

[Add a key to a dictionary](#text00046.html__Toc77010783)

[Iterate over dictionaries using for loops](#text00047.html__Toc77010784)

[Merge two Python dictionaries](#text00048.html__Toc77010785)

[Multiply all the items in a dictionary](#text00049.html__Toc77010786)

[Remove a key from a dictionary](#text00050.html__Toc77010787)

[Get a dictionary from an object's fields](#text00051.html__Toc77010788)

[Combine two dictionary adding values for common keys](#text00052.html__Toc77010789)

[Find the highest 3 values](#text00053.html__Toc77010790)

LEARN

KOTLIN QUICKLY

# Introduction to Kotlin

Kotlin is a high-level programming language runs on JVM. Kotlin compiles the sources code into java byte code and runs the application using jvm. You can use java and kotlin interchangeably, means you can call a kotlin function from Java and vice versa.

Prerequisites

Java fundamentals are necessary.

Is Kotlin Object oriented?

Yes, Kotlin is object oriented language, you can create classes, objects, and apply oops concepts like polymorphism, inheritance etc.,

Is kotlin functional?

Yes, Kotlin is a functional language. In functional programming lngauge, functions are basic building blocks, you can return a function, pass a function as argument to other function etc.,

Is Kotlin open source?

Yes

What kind of application Can I develop using Kotlin?

*   Build Mobile Applications
*   Develop server side applications
*   You can develop any application, that can be developed in Java

Can I run kotlin code in web browser?

Kotlin can be compiled to JavaScript, so you can run the applications in browser.

Is Kotlin statically typed?

Yes kotlin is statically typed language. For statically typed languages, type of the variable is known at compile time. You can refer my post  statically vs dynamically typed languages  to know the difference between statically and dynamically typed languages.

Can kotlin infer type?

Yes, unlike Java, you no need to specify the type while defining the variable. Kotlin infer the type based on the context.

Ex

var name = "Krishna"

Since "Krishna" is assigned to the variable ‘name’, koltin infer the type as String.

var age = 28

Since number 28 is assigned to the variable ‘age’, kotlin infer the type as int.

# Kotlin: Hello World program

 ‘.kt’ is the extension for kotlin files. Create a file ‘HelloWorld.kt’ with below content.

HelloWorld.kt

fun main (args:Array<String>){

println( "Hello World" )

}

Keyword ‘fun’ is used to define a function.

‘main’ is the main function of the application. Program execution starts from here.

args:Array<String>

In Kotlin variable name is declared first, followed by the type. In above case, args is variable of type array of strings.

println("Hello World")

Above statement prints the message ‘Hello World’ to the console. As you see, unlike java, Kotlin statements do not end with ‘;’.

Compile HelloWorld.kt
Open command prompt and type the command ‘kotlinc HelloWorld.kt’.

C:\Users\Krishna\Documents\Study\Kotlin\Programs>kotlinc HelloWorld.kt

C:\Users\Krishna\Documents\Study\Kotlin\Programs>dir

Volume in drive C is OSDisk

Volume Serial Number is 1034-4F6F

Directory of C:\Users\Krishna\Documents\Study\Kotlin\Programs

09/02/2017  11:18 AM    <DIR>          .

09/02/2017  11:18 AM    <DIR>          ..

09/02/2017  11:09 AM                57 HelloWorld.kt

09/02/2017  11:18 AM               980 HelloWorldKt.class

09/02/2017  11:18 AM    <DIR>          META-INF

               2 File(s)          1,037 bytes

               3 Dir(s)  63,190,188,032 bytes free

As you see the output of dir command, you can observe, kotlin generates ‘HelloWorldKt.class’ and a META-INF directory.

Run HelloWorld.kt
You can run the HelloWorldkt file using ‘kotlin HelloWorldKt’ command.

C:\Users\krishna\Documents\Study\Kotlin\Programs>kotlin HelloWorldKt

Hello World

Creating and run jar

You can also create a jar file and run the jar file using java launcher.

Use the command ‘kotlinc HelloWorld.kt -include-runtime -d HelloWorld.jar

‘ to create a jar file.

The ‘include-runtime’ option tells kotlin compiler, include kotlin run time in HelloWorld.jar file.

C:\Users\Krishna\Documents\Study\Kotlin\Programs>kotlinc HelloWorld.kt -include-runtime -d HelloWorld.jar

C:\Users\Krishna\Documents\Study\Kotlin\Programs>dir

Volume in drive C is OSDisk

Volume Serial Number is 1034-4F6F

Directory of C:\Users\Krishna\Documents\Study\Kotlin\Programs

09/02/2017  11:24 AM    <DIR>          .

09/02/2017  11:24 AM    <DIR>          ..

09/02/2017  11:24 AM           869,262 HelloWorld.jar

09/02/2017  11:09 AM                57 HelloWorld.kt

               2 File(s)        869,319 bytes

               2 Dir(s)  63,401,816,064 bytes free

Once the jar file is created, you can call the jar file, just like how you run other jar files. Use the command ‘java -jar HelloWorld.jar’

C:\Users\Krishna\Documents\Study\Kotlin\Programs>java -jar HelloWorld.jar

Hello World

# Setting up Kotlin in Eclipse

Open Eclipse. Help -> Eclipse Marketplace.

![https://4.bp.blogspot.com/--jOmFNqRCgM/Wg2eFHMLi3I/AAAAAAAAJGE/7K-S0KXUm6QiS4xCaRBRLSBr25NxRAhwgCLcBGAs/s400/Eclipse%2BKotlin%2B1.png](Image00000.jpg)

Search for kotlin.

![https://2.bp.blogspot.com/-jX-DhHd8nMA/Wg2eRkx3gZI/AAAAAAAAJGI/Xxpu-4uILfgsj0dStVJDeD6B1XFY9ffzwCLcBGAs/s400/Eclipse%2BKotlin%2B2.png](Image00001.jpg)

Click on the button ‘Install’ to install the kotlin plugin.

Once the installation is successful, Eclipse asks for a restart. Restart the Eclipse.

Create new Kotlin Project

Open Eclipse. File -> New -> Other.

![https://2.bp.blogspot.com/-ssfP-Jmov0g/Wg2ehC40vPI/AAAAAAAAJGM/PCmtTAP41rgJjSYlkPr03WBxUwIUmB8cQCLcBGAs/s400/eclipse%2Bkotlin%2Bproject1.png](Image00002.jpg)

Kotlin -> Kotlin Project.

![https://2.bp.blogspot.com/-vO3pApz8d3M/Wg2es6gBKHI/AAAAAAAAJGU/BNIBQ_-YpxkSyDDpFqjl3lPPvui3e-PCgCLcBGAs/s400/eclipse%2Bkotlin%2Bproject2.png](Image00003.jpg)

Press Next.

In the ‘Kotlin Project’ window, give the project name as ‘Hello World’ and click on the button Finish.

Kotlin project structure looks like below.

![https://4.bp.blogspot.com/-2PXfV1Fz8TY/Wg2e4KvUcbI/AAAAAAAAJGY/j4wml-mNTT0t4V1ElYv8154z9y6QBxbvwCLcBGAs/s400/eclipse%2Bkotlin%2Bproject3.png](Image00004.jpg)

Create HelloWorld.kt file

Right click on ‘src’ folder -> New -> Other.

![https://1.bp.blogspot.com/-7wGQfPyFoEg/Wg2fCzt6imI/AAAAAAAAJGc/UQEtAW7geMgFzk-doAWRVm5-OJITfAM-wCLcBGAs/s400/eclipse%2Bkotlin%2Bproject4.png](Image00005.jpg)

Select ‘Kotlin File’ and press Next.

![https://1.bp.blogspot.com/-_y0wpMTJ6E4/Wg2fNKJye_I/AAAAAAAAJGk/dcnwrzQg8CQvDqeR8iTozHsKYQ1vhQ0HwCLcBGAs/s400/eclipse%2Bkotlin%2Bproject5.png](Image00006.jpg)

Give the file name as ‘HelloWorld’ and press the button ‘Finish’.

![https://3.bp.blogspot.com/-pEiPDvKjAgk/Wg2fYDnrUxI/AAAAAAAAJGo/BuwP-2ZMTn02-6Aa8UNsZ__U28hPtNpdQCLcBGAs/s400/eclipse%2Bkotlin%2Bproject6.png](Image00007.jpg)

Copy below snippet to HelloWorld.kt file.

HelloWorld.kt

fun main (args: Array<String>) {

println( "Hello World" )

}

Run HelloWorld.kt file
Right click on source code of HelloWorld.kt file -> Run As -> Kotlin Application.

![https://2.bp.blogspot.com/-SnRNFT2Y4MA/Wg2ftrnVWZI/AAAAAAAAJGw/FuSKFVl-_pU3c-GyYrl6quHvY8K281LnACLcBGAs/s400/eclipse%2Bkotlin%2Bproject7.png](Image00008.jpg)

If everything goes well, you can see the message ‘Hello World’ in console.

![https://3.bp.blogspot.com/-RL0AgvzfVoo/Wg2f5lOTuYI/AAAAAAAAJG0/sM0FDoh1v3476Hh9krviz5MOf71LOZ3qQCLcBGAs/s400/eclipse%2Bkotlin%2Bproject8.png](Image00009.jpg)

# Define variables in Kotlin

Variable is a named memory location used to store data.

Syntax

var variableName : DataType = value

val variableName : DataType = value

Both ‘var’ and ‘val’ are the keywords.

Ex
var a : Int  =10;

‘a’ is of type int and assigned with value 10.

val b : Double = 1.23

‘b’ is of type Double and assigned with value 1.23\. The keyword ‘val’ is used to define constants (immutable objects).

HelloWorld.kt

fun main (args: Array<String>) {

  var a : Int  = 10 ;

  val b : Double = 1.23

println( "a : ${a}" )

println( "b : ${b}" )

}

C:\>kotlinc HelloWorld.kt

C:\>kotlin HelloWorldKt

a : 10

b : 1.23

# Data types in Kotlin

Java has primitive types like int, float, char etc., what about Kotlin?

In Users point of view, kotlin designed everything as object, but at run time Booleans, numbers and characters are represented as primitive types.

HelloWorld.kt

fun main (args: Array<String>) {

  var doubleVar: Double = 1.23

  var floatVar: Float = 1.23f

  var longVar: Long = 123

  var intVar: Int = 123

  var shortVar: Short = 123

  var byteVar: Byte = 123

println( "doubleVar : ${doubleVar}" )

println( "doubleVar : ${floatVar}" )

println( "longVar : ${longVar}" )

println( "intVar : ${intVar}" )

println( "shortVar : ${shortVar}" )

println( "byteVar : ${byteVar}" )

}

Output

doubleVar : 1.23

doubleVar : 1.23

longVar : 123

intVar : 123

shortVar : 123

byteVar : 123

# Kotlin: nullable types

By default, kotlin reference types (Int, Float, Double, String etc.,) do not take null values. Kotlin introduced this feature to avoid null pointer exceptions.

Test.kt

fun main (args: Array<String>) {

  var name : String = "Krishna"

name = null

}

When you try to compile above program, kotlin throws below error.

ERROR: Null can not be a value of a non-null type String (6, 9)

How can I define a variable that take null value?

By using nullable types, you can define a variable that takes null values. Append the ‘?’ to the reference type to take null values.

| Type | Nullable type |
| Int | Int? |
| String | String? |
| Double | Double? |
| Person | Person? |

Ex

  var id: Int? = 1

  var name: String? = "Krishna"

  var salary: Double? = 123.456

  var person: Person? = Person( "Krishna" )

id = null

name = null

salary = null

person = null

# Kotlin: Numbers

Kotlin provides below data types to support numbers.

| Data Type | Size in Bits |
| Double | 64 |
| Float | 32 |
| Long | 64 |
| Int | 32 |
| Short | 16 |
| Byte | 8 |

Numbers.kt

fun main (args: Array<String>) {

  var doubleVar: Double = 1.23

  var floatVar: Float = 1.23f

  var longVar: Long = 123

  var intVar: Int = 123

  var shortVar: Short = 123

  var byteVar: Byte = 123

println( "doubleVar : ${doubleVar}" )

println( "doubleVar : ${floatVar}" )

println( "longVar : ${longVar}" )

println( "intVar : ${intVar}" )

println( "shortVar : ${shortVar}" )

println( "byteVar : ${byteVar}" )

}

Output

doubleVar : 1.23

doubleVar : 1.23

longVar : 123

intVar : 123

shortVar : 123

byteVar : 123

Hexa, octal and Binary literal notation

Kotlin support Hexa and binary notation, but not support octal notation. Hexa numbers are represented by prefixing 0x,

Numbers.kt

fun main (args: Array<String>) {

  var hexaNum : Int = 0 x123

  var binaryNum : Int = 0 b10101010

println( "hexaNum : ${hexaNum}" )

println( "binaryNum : ${binaryNum}" )

}

Output

hexaNum : 291

binaryNum : 170

You can also represent numbers using ‘_’.

Numbers.kt

fun main (args: Array<String>) {

  var ten = 10

  var hundred = 100

  var thousand = 1000

  var tenThousand = 10 _000

  var oneLaksh = 100 _000

  var tenLaksh = 1 _000_000

println( "ten : ${ten}" )

println( "hundred : ${hundred}" )

println( "thousand : ${thousand}" )

println( "tenThousand : ${tenThousand}" )

println( "oneLaksh : ${oneLaksh}" )

println( "tenLaksh : ${tenLaksh}" )

}

Output

ten : 10

hundred : 100

thousand : 1000

tenThousand : 10000

oneLaksh : 100000

tenLaksh : 1000000

# Kotlin: Characters

'Char; keyword is used to define single character. Character is enclosed in single quotes.

Ex

var myChar : Char = 'a'

HelloWorld.kt

fun main (args: Array<String>) {

  var myChar : Char = 'a'

println( "Value of myChar is : ${myChar}" )

}

Output

Value of myChar is : a

All the escape sequences that are supported by Java are also supported by Kotlin.

# Kotlin: Convert character to Int

Char type provides toInt() method to convert a character to integer.

IntConverter.kt

fun main (args: Array<String>) {

  var myChar : Char = 'a'

println( "Value of myChar is : ${myChar}" )

println( "Value of myChar in int is : ${myChar.toInt()}" )

}

Output

Value of myChar is : a

Value of myChar in int is : 97

# Kotlin: Booleans

Boolean type is used to represent true, false states.

Booleans.kt

fun main (args: Array<String>) {

  var trueState : Boolean  = true

  var falseState : Boolean  = false

println( "Value of trueState is : ${trueState}" )

println( "Value of falseState is : ${falseState}" )

}

Output

Value of trueState is : true

Value of falseState is : false

# Kotlin: Strings

String is a collection of characters, enclosed in double quotes. Strings in kotlin are defined by using the keyword String and these are  immutable .

Ex

var message: String = "Good Morning"

StringsDemo.kt

fun main (args: Array<String>) {

  var message: String = "Good Morning"

println(message)

}

Output

Good Morning

All the escape sequences (\n, \t, \a etc.,) supported by java are also supported by kotlin.

Ex

var message: String = "Good Morning\nHow are you\nsee you soon"

StringDemo.kt

fun main (args: Array<String>) {

  var message: String = "Good Morning\nHow are you\nsee you soon"

println(message)

}

Output

Good Morning

How are you

see you soon

If you do not want to perform escaping, then embed the string in """ (triple quotes).

StringDemo.kt

fun main (args: Array<String>) {

  var message: String = """Good Morning\nHow are you\nsee you soon

      After two lines\bgood bye"""

println(message)

}

Output

Good Morning\nHow are you\nsee you soon

                                                    After two lines\bgood bye

# Kotlin: String template expressions

By using template expression, you can evaluate the expression in a string. Template expression starts with $ symbol followed by a name.

Ex

var a = 10

println("Value of a is : $a")

Arbitrary expression are enclosed in curly braces

var str = "Hello World"

println("$str length is ${str.length}")

Expression.kt

fun main (args: Array<String>) {

  var a = 10

  var str = "Hello World"

println( "Value of a is : $a" )

println( "$str length is ${str.length}" )

}

Output

Value of a is : 10

Hello World length is 11

# Kotlin: Arrays

Array represents a collection of elements of same type. Kotlin provides Array class to represent arrays.

By using the library function arrayOf, you can define an array.

Ex

val numbers: Array<Int> = arrayOf(10, 20, 30, 40, 50)

ArrayDemo.kt

fun main (args: Array<String>) {

  val numbers: Array<Int> = arrayOf( 10 , 20 , 30 , 40 , 50 )

  for (element in numbers) {

  println(element)

}

}

Output

10

20

30

40

50

Kotlin provides below library functions to define array of primitive types.

byteArrayOf()

shortArrayOf()

intArrayOf()

longArrayOf()

floatArrayOf()

doubleArrayOf()

CharArray()

BooleanArray()

# Kotlin: Define array of nulls

Kotlin provides 'arrayOfNulls' library function to define array of null values.

ArrayOfNulls.kt

fun main (args: Array<String>) {

  var a: Array<Int?> = arrayOfNulls( 5 )

  for (element in a) {

  println(element)

}

}

Output

null

null

null

null

null

# Kotlin: Define array using factory function

Kotlin provides a factory function, which takes size and a function ‘f’ as arguments to define an array. The function ‘f’ is used to provide initial values to the array.

var squares = Array(5, { i -> i * i })

Above statement define an array 'squares' of size 5 and initialize {1, 4, 9, 16, 25}

ArrayFactoryFunction.kt

fun main (args: Array<String>) {

  var squares = Array( 5 , { i -> i * i })

  var cubes = Array( 5 , { i -> i * i * i })

println( "Elements in squares array : " )

  for (ele in squares) {

  println(ele)

}

println( "\nElements in cubes array : " )

  for (ele in cubes) {

  println(ele)

}

}

Output

Elements in squares array :

0

1

4

9

16

Elements in cubes array :

0

1

8

27

64

# Kotlin: Print array elements

. In this post, I am going to show,how to print elements of an array.

Print elements of array using for loop

ArrayUtil.kt

fun main (args: Array<String>) {

  var arr: Array<Int> = arrayOf( 1 , 2 , 3 , 4 )

  for (ele in arr) {

  println(ele)

}

}

Output

1

2

3

4

Print array elements using 'Arrays.toString' method

ArrayUtil.kt

import java.util.Arrays

fun main (args: Array<String>) {

  var arr: Array<Int> = arrayOf( 1 , 2 , 3 , 4 )

println(Arrays.toString(arr))

}

Output

[1, 2, 3, 4]

Print array elements using array.indices

ArrayUtil.kt

fun main (args: Array<String>) {

  var arr: Array<Int> = arrayOf( 2 , 3 , 5 , 7 )

  for (index in arr.indices) {

  println(arr[index])

}

}

Output

2

3

5

7

Print array elements using array.withIndex

ArrayUtil.kt

fun main (args: Array<String>) {

  var arr: Array<Int> = arrayOf( 2 , 3 , 5 , 7 )

  for ((index, value) in arr.withIndex()) {

  println( "index : $index, value : $value" )

}

}

Output

index : 0, value : 2

index : 1, value : 3

index : 2, value : 5

index : 3, value : 7

Print array elements using while loop

ArrayUtil.kt

fun main (args: Array<String>) {

  var arr: Array<Int> = arrayOf( 2 , 3 , 5 , 7 )

  var sizeOfTheArray = arr.size;

  var index : Int = 0 ;

  while (index < sizeOfTheArray){

  println( "index : $index, value : ${arr[index]}" )

  index++

}

}

Output

index : 0, value : 2

index : 1, value : 3

index : 2, value : 5

index : 3, value : 7

# Kotlin: Bit wise operators

Below table summarizes the bit wise operators supported by Kotlin.

| Operator | Description | Java Equivalant |
| shl | Perform signed shift left | <<  |
| shr | Perform signed shift right | >>  |
| ushr | Perform unsigned shift right | >>>  |
| and | Bitwise and | & |
| or | Bitwise or | &#124; |
| xor | Bitwise X-OR | ^ |
| inv() | Bitwise inversion | ~ |

Other than inv(), all other operators are used in infix form.

Ex:

var1 shl var2

var1 or var2

1\. shl: Perform signed shift left

Left shift operator shifts all the bits to one bit left, i.e, it doubles the value.

Syntax:

    variable shl n

    left shift the variable by 'n' number of times.

Variable shl n is equals to variable = variable * 2 power n

        var var1 : Int = 2

        var1 shl 1 = 2 * 2 power 1 = 4

        var1 shl 2 = 2 * 2 power 2 = 8

        var1 shl 9 = 2 * 2 power 9 = 1024

LeftShift.kt

fun main (args: Array<String>) {

  var var1: Int = 2

  var res1 = var1 shl 1

  var res2 = var1 shl 2

  var res3 = var1 shl 9

println( "res1 : ${res1}" )

println( "res2 : ${res2}" )

println( "res3 : ${res3}" )

}

Output

res1 : 4

res2 : 8

res3 : 1024

2\. shr: Perform signed shift right

Right shift operator shifts all the bits to one bit right, i.e, it half (divide by 2) the value

   Syntax:

   variable shr n

      right shift the variable by 'n' number of times.

   Variable shr n is equals to variable = variable / 2 power n

   var a : Int = 128

   a shr 1 = 128 / (2 power 1) = 64

   a shr 2 = 128 / (2 power 2) = 32

RightShift.kt

fun main (args: Array<String>) {

  var a: Int = 128

  var res1 = a shr 1

  var res2 = a shr 2

  var res3 = a shr 3

println( "res1 : ${res1}" )

println( "res2 : ${res2}" )

println( "res3 : ${res3}" )

}

Output

res1 : 64

res2 : 32

res3 : 16

3\. ushr: Unsigned right shift

Shifts all the bits to one bit right, and make the left most bit to zero

Syntax

Variable ushr n

UnsignedRightShift.kt

fun main (args: Array<String>) {

  var a: Int = - 128

  var res1 = a ushr 1

println( "res1 : ${res1}" )

}

Output

res1 : 2147483584

Explanation

-128 in 2's complement form is

11111111 11111111 11111111 10000000

>>> shifts the one bit right and replace leftmost bit by zero

so (-128 ushr 1) is like below sequence

01111111 11111111 11111111 11000000

4\. Bit Wise and, or, xor

| Bit1 | Bit2 | and | or | xor |
| 0 | 0 | 0 | 0 | 0 |
| 0 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 1 | 1 |
| 1 | 1 | 1 | 1 | 0 |

HelloWorld.kt

fun main (args: Array<String>) {

  var a: Int = 8

  var b: Int = 9

println( "a and b is ${a and b} " )

println( "a or b is ${a or b} " )

println( "a xor b is ${a xor b}" )

}

Output

a and b is 8

a or b is 9

a xor b is 1

Explanation

   a    = 0000 1000

   b    = 0000 1001

   a&b = 0000 1000

   a    = 0000 1000

   b    = 0000 1001

   a|b = 0000 10001

   a     = 0000 1000

   b     = 0000 1001

   a^b = 0000 0001

Note:

Bit wise operators are applicable only to integer values like byte, short etc., these are not applicable to float, double, Boolean.

5\. inv(): Bitwise inversion

Inversion operator change the bit value to zero, if it is one and change the bit value to one if it is zero.

Example

var a : Int = 8

a in binary format is              0 0 0 0 0 1 1 1

a.inv() in binary format is      1 1 1 1 1 0 0 0

Inverse.kt

fun main (args: Array<String>) {

  var a: Int = 8

println( "Value of a is : ${a}" )

println( "inversion of a is : ${a.inv()}" )

}

Output

Value of a is : 8

inversion of a is : -9

# Kotlin: Logical Operators

Kotlin supports logical operators (also called as Boolean operators), to combine multiple conditions. 

*   || – lazy disjunction
*   && – lazy conjunction
*   ! - negation

1\. || – lazy disjunction

operand1 || operand2:  It returns true, if any of the operand evaluates to true, otherwise returns false.

| Operand1 | Operand2 | Evaluates To |
| False | false | false |
| False | true | true |
| True | false | true |
| True | true | true |

BooleanOr.kt

fun main (args: Array<String>) {

  var operand1: Boolean = false

  var operand2: Boolean = false

println( "${operand1} || ${operand2}: ${(operand1 || operand2)}" )

operand1 = false

operand2 = true

println( "${operand1} || ${operand2}: ${(operand1 || operand2)}" )

operand1 = true

operand2 = false

println( "${operand1} || ${operand2}: ${(operand1 || operand2)}" )

operand1 = true

operand2 = true

println( "${operand1} || ${operand2}: ${(operand1 || operand2)}" )

}

Output

false || false : false

false || true : true

true || false : true

true || true : true

Why || is called as Lazy Disjunciton?

If the first expression evaluates to true, then Kotlin won't evaluates the entire expression. So Logical OR is called short circuit OR (or) Lazy disjunction operator.

LazyDisjunciton.kt

fun main (args: Array<String>) {

  var a : Int = 10

  var b : Int = 21

  if ((a < b) || (a++ < b)) {

  System. out .println( "This statement evaluated" );

}

System. out .println( "a is not incremented " + a);

  if ((a > b) || (a++ > b)) {

  System. out .println( "This statement is evaluated" );

}

System. out .println( "a is incremented " + a);

}

Output

This statement evaluated

a is not incremented 10

a is incremented 11

&& – lazy conjunction

operand1 && operand2: It returns true, if both the operand evaluates to true, otherwise returns false.

| Operand1 | Operand2 | Evaluates To |
| False | false | false |
| False | true | false |
| True | false | false |
| True | true | true |

BooleanAnd.kt

fun main (args: Array<String>) {

  var operand1: Boolean = false

  var operand2: Boolean = false

println( "${operand1} && ${operand2}: ${(operand1 && operand2)}" )

operand1 = false

operand2 = true

println( "${operand1} && ${operand2}: ${(operand1 && operand2)}" )

operand1 = true

operand2 = false

println( "${operand1} && ${operand2}: ${(operand1 && operand2)}" )

operand1 = true

operand2 = true

println( "${operand1} && ${operand2}: ${(operand1 && operand2)}" )

}

Output

false && false: false

false && true: false

true && false: false

true && true: true

Why && is called Lazy conjunction operator?

If the first statement in the expression evaluates to false, then kotlin won't evaluate the entire expression. So, Logical AND is called short circuit AND.

LazyConjunction.kt

fun main (args: Array<String>) {

  var a: Int = 10

  var b: Int = 21

  if ((a > b) && (a++ > b)) {

  System. out .println( "This statement not evaluated" );

}

System. out .println( "a is not incremented " + a);

  if ((a < b) && (a++ < b)) {

  System. out .println( "This statement is evaluated" );

}

System. out .println( "a is incremented " + a);

}

Output

a is not incremented 10

This statement is evaluated

a is incremented 11

3\. Logical not (!) Operator

If the operand is false, ! Operator evaluates it to true

If the operand is true, ! Operator evaluates it to false

| Operand | Evaluates To |
| False | true |
| True | false |

LogicalNot.kt

fun main (args: Array<String>) {

  var operand1: Boolean = false

  var operand2: Boolean = true

println( "operand1 : ${operand1}" )

println( "!operand1 : ${!operand1}" )

println( "operand2 : ${operand2}" )

println( "!operand2 : ${!operand2}" )

}

Output

operand1 : false

!operand1 : true

operand2 : true

!operand2 : false

## Kotlin: === vs ==

Kotlin supports two types of equality.

*   Referential Equality
*   Structural Equality

Referential Equality (===)

 ‘===’ operator is used to check, whether two references point to same object or not.

Ex:

ref1 === ref2

Above statement returns true, if references ‘ref1’ and ‘ref2’ points to same object, else false.

Structural Equality(==)

Structural equality is used to check, whether the values of both references are equal (checks by using equals() method of java).

Ex:

ref1 == ref2

Above statement returns true, if ref1.equals(ref2) return true, else false.

Equality.kt

fun main (args: Array<String>) {

  var intVar1 : Int = 10000

  var intBoundedVar1 : Int? = intVar1

  var intBounderdVar2 : Int? = intVar1

println( "(intBoundedVar1===intBounderdVar2) : ${(intBoundedVar1 === intBounderdVar2)}" )

println( "(intBoundedVar1==intBounderdVar2) : ${(intBoundedVar1 == intBounderdVar2)}" )

}

Output

(intBoundedVar1===intBounderdVar2) : false

(intBoundedVar1==intBounderdVar2) : true

# Kotlin: Control flow statements

Kotlin provides control flow statements

     for decision making (if, if-else, when) and

     for looping (for, while, do-while)

Decision Making statements

*   if statement
*   if-else statement
*   if-else if-else ladder
*   when statement

Looping statements

*   for
*   while
*   do-while

# Kotlin: if statement

"if" tell the program execute the section of code when the condition evaluates to true.

Syntax

if(condition){

         // Executes if the condition true

}

IfStmt.kt

fun main (args: Array<String>) {

  var marks: Int = 20

  if (marks < 35 ) {

  println( "You failed in the Exam. Better luck next time" );

}

marks = 55

  if (marks < 35 ) {

  println( "You failed in the Exam again. Better luck next time" );

}

}

Output

You failed in the Exam. Better luck next time

# Kotlin: if-else statement

If the condition true, then if block code will execute, otherwise else block code will execute.

Syntax:

if(condition){

}else{

}

IfElse.kt

fun main (args: Array<String>) {

  var marks: Int = 65

  if (marks < 35 ) {

  println( "You failed in the Exam. Better luck next time" );

} else {

  println( "You passed in the exam" )

}

}

Output

You passed in the exam

# Kotlin: if-else if-else

By using if-else if-else construct, you can choose between number of alternatives.

An if statement can be followed by an optional else if...else statement, which is very useful to test various conditions.

IfElseIf.kt

fun main (args: Array<String>) {

  var marks: Int = 65

  if (marks < 35 )

  println( "You are failed" );

  else if (marks < 50 )

  println( "You are passed and got third class" );

  else if (marks < 60 )

  println( "You are passed and got second class" );

  else if (marks < 70 )

  println( "You are passed and got first class" );

  else

  println ( "You are passed and got distinction" );

}

Output

You are passed and got first class

# Kotlin: when expression

‘when’ is equivalent to  switch statement in Java .

Syntax

when(expression){

         1 -> {//Perform Something}

         2 -> {//Perform Something}

         else -> {//Perform something}

}

‘when’ evaluates the expression  against all the possible cases sequentially. If none of the case is satisfied, then else block will execute.

WhenDemo.kt

fun main (args: Array<String>) {

  var a : Int = 5

  when (a){

  12 -> println( "Value 12 is checked" )

  5 -> println( "Value 5 is checked" )

  3 -> println( "Value 3 is checked" )

  else -> println( "No value is checked" )

}

}

Output

Value 5 is checked

You can combine multiple branch statements in when expression.

WhenDemo.kt

fun main (args: Array<String>) {

  var a : Int = 5

  when (a){

  2 , 3 , 5 , 7 -> println( "Prime number" )

  4 , 6 , 8 -> println( "Even number other than 2" )

  else -> println( "No value is checked" )

}

}

Output

Prime number

You can also use arbitrary expressions as branch conditions. For example, I used 2+3 as branch condition.

WhenDemo.kt

fun main (args: Array<String>) {

  var a : Int = 5

  when (a){

  2 + 3 -> println( "Checked value 5" )

  4 , 6 , 8 -> println( "Even number other than 2" )

  else -> println( "No value is checked" )

}

}

Output

Checked value 5

You can also check the ranges (or) not in ranges in branch condition.

WhenDemo.kt

fun main (args: Array<String>) {

  var a : Int = 5

  when (a){

  in 1. . 5 , in 11. . 15 -> println( "a is in between 1 to 5 (or) 11 to 15" )

  in 6. . 10 -> println( "a is in range of 6 to 10" )

  else -> println( "x is not in range" )

}

}

Output

a is in between 1 to 5 (or) 11 to 15

# Kotlin: Using when as if-else if ladder

You can also use ‘when’ expression as if-elseif ladder. If you do not specify any argument to when expression, it can be used as if-else if ladder.

ConditionDemo.kt

fun main (args: Array<String>) {

  var marks: Int = 65

  if (marks < 35 )

  println( "You are failed" );

  else if (marks < 50 )

  println( "You are passed and got third class" );

  else if (marks < 60 )

  println( "You are passed and got second class" );

  else if (marks < 70 )

  println( "You are passed and got first class" );

  else

  println ( "You are passed and got distinction" );

}

Output

You are passed and got first class

You can implement above if-else if-else logic using when expression like below.

WhenDemo.kt

fun main (args: Array<String>) {

  var marks: Int = 65

  when {

  (marks < 35 ) -> println( "You are failed" )

  (marks < 50 ) -> println( "You are passed and got third class" )

  (marks < 60 ) -> println( "You are passed and got second class" )

  (marks < 70 ) -> println( "You are passed and got first class" )

  else -> println( "You are passed and got distinction" )

}

}

Output

You are passed and got first class

# Kotlin: Use When as expression

You can use 'when' as expression. If you use 'when' as expression, the value of the matched branch will be the value of 'when' expression.

WhenDemo.kt

fun main (args: Array<String>) {

  var a : Int = 2

  var s : String = "cube"

  var result = when {

  s.equals( "double" ) -> a * a

  s.equals( "cube" ) -> a * a * a

  else -> a

}

println( "result is $result" )

}

Output

result is 8

# Kotlin: for loop

‘for’ loop is used to iterate over a collection, array, ranges etc.,

By using ‘for’ loop, you can iterate over anything that provides iterator.

Looping through arrays

Syntax

for(ele in array){

}

ArrayDemo.kt

fun main (args: Array<String>) {

  var arr: Array<Int> = arrayOf( 2 , 3 , 5 , 7 )

  for (ele in arr){

  println(ele)

}

}

Output

2

3

5

7

Loop over a range
ArrayDemo.kt

fun main (args: Array<String>) {

  for (ele in 1. . 10 ){

  println(ele)

}

}

Output

1

2

3

4

5

6

7

8

9

10

Loop over a string
ArrayDemo.kt

fun main (args: Array<String>) {

  var message = "Good Morning"

  for (c in message){

  print(c)

}

}

Output

Good Morning

# Kotlin: while, do-while loops

while loop

while statement executes a block of statements until a particular condition is true

Syntax

while (expression) {

      //statements

}

The expression in the while statement must evaluates to a boolean value, otherwise compiler will throw error. While statement first evaluates the expression, until the expression evaluates to true, it executes the code inside the while block, otherwise it comes out of the while loop.

Example: Print numbers from 0 to 9 using while loop.

WhileDemo.kt

fun main (args: Array<String>) {

  var counter : Int = 0

  while (counter < 10 ){

  println(counter)

  counter++

}

}

Output

0

1

2

3

4

5

6

7

8

9

do-while loop

do-while is also a loop construct like while, but evaluates its expression at the bottom of the loop instead of the top.

     Syntax

    do {

        //statement(s)

    } while (expression)

DoWhileDemo.kt

fun main (args: Array<String>) {

  var counter : Int = 0

  do {

  println(counter)

  counter++

} while (counter < 10 )

}

Output

0

1

2

3

4

5

6

7

8

9

What is the difference between while and do-while ?
Statements within the do block are always execute at least once even if the expression evaluates to false.

# Kotlin: break statement

'break' statement is used to come out of the loop. 'break' statement can be used in two forms.

         a. unlabeled break

         b. labeled break

unlabeled break

Unlabeled break is used to come out from nearest closing loop.

Syntax

break

BreakDemo.kt

fun main (args: Array<String>) {

  for (i in 1. . 10 ) {

  println(i)

  if (i == 5 ) {

   break

  }

}

}

Output

1

2

3

4

5

BreakDemoInnerLoop.kt

fun main (args: Array<String>) {

  for (i in 1. . 5 ) {

  for (j in 1. .i) {

   print( "$j" )

  }

  println()

}

}

Output

1

12

123

1234

12345

Labelled break

Kotlin allows us to label any expression.

How to create a label?

Define an identifier followed by @ sign.

Ex:

outerLoop@, processState@

By specifying the label, we can come out of the label.

Syntax

break@labelIdentifier

Ex

break@outerLoop

break@processState

LabelledBreakDemo.kt

fun main (args: Array<String>) {

  var counter: Int = 0 ;

outerLoop @ for (i in 1. . 5 ) {

  for (j in 1. .i) {

   counter++

   print( "$j" )

   if (counter == 6 ) {

    println( "\nBreaking out of the outer loop" )

    break @outerLoop

   }

  }

  println()

}

}

Output

1

12

123

Breaking out of the outer loop

# Kotlin: continue statement

continue statement skips the current iteration of loops(Ex: for, while, do-while loops). Just like break, continue also has two forms.

    1\. unlabelled continue

    2\. labelled continue

Unlabelled continue

    Syntax

        continue;

ContinueDemo.kt

fun main (args: Array<String>) {

  for (i in 1. . 10 ) {

  if (i % 2 != 0 ) {

   continue

  }

  print( "$i " )

}

}

Output

2 4 6 8 10

UnlabelledContinueInnerLoop.kt

fun main (args: Array<String>) {

  for (i in 1. . 5 ) {

  for (j in 1. . 10 ){

   if (j % 2 != 0 ){

    continue

   }

   print( "$j " )

  }

  println()

}

}

Output

2 4 6 8 10

2 4 6 8 10

2 4 6 8 10

2 4 6 8 10

2 4 6 8 10

Labelled Continue

Kotlin allows us to label any expression.

How to create a label?

Define an identifier followed by @ sign.

Ex:

outerLoop@, processState@

we can use continue statement with labels.

Syntax

continue@labelIdentifier

Ex

continue @outerLoop

continue @processState

ContinueLabelledDemo.kt

fun main (args: Array<String>) {

outerLoop @ for (i in 1. . 5 ) {

  for (j in 1. . 10 ) {

   if (j > 5 ) {

    println()

    continue @outerLoop

   }

   print( "$i " )

  }

}

}

Output

1 1 1 1 1

2 2 2 2 2

3 3 3 3 3

4 4 4 4 4

5 5 5 5 5

# Kotlin: classes and objects

Objects and class in Real World scenario

Object

An Object is a real-world entity. For example, book, cat, box, bus, keyboard, person, screen, cell phone etc., all are objects.

How can we differentiate objects

1\. Depend on their properties

2\. Depend on their behaviors

Differentiating two objects based on their properties

Let’s say, there are two persons A and B.

First let’s try to find what are the possible properties for the person object

Possible properties for a person

height, weight, color, Education Qualification, country, address are all come under person properties.

Now by comparing these properties we can easily differentiate two persons.

| Properties | Person A | Person B |
| Height | 6ft | 5.5ft |
| Weight | 75Kg | 60Kg |
| Color | White | Black |
| Country | India | America |

As shown in the above table, both the persons has their own properties, So we can differentiate based on them.

Differentiating two objects based on their behavior

consider the same two persons A and B. will try to figure out possible behaviors for the person object

Possible behaviors are

walk, run, swim, eat, sleep, see, hear etc., Now by comparing these behaviors we can easily differentiate two persons.

| Behavior | Person A | Person B |
| Walk | 10km/hr | 12km/hr |
| run | 20km/hr | 18km/hr |
| sleep | 8 Hrs/day | 6Hrs/day |
| Behavior | Person A | Person B |

Class

In normal terms I call class as a category.

All persons come under Human category

cat, lion, Elephant come under Animals Category

So a class or category is a group of objects with similar properties and behaviors.

Objects and class in Programming Terminology

What Is an Object?

An object is a software bundle of related state and behavior. The main advantage of Kotlin is you can compare objects in Kotlin with real world objects. So it is very easy to work with objects in Kotlin.

What Is a Class?

A class is a blueprint or prototype from which objects are created.

You can define a class using 'class' keyword.

Syntax

class ClassName {

  // Properties

  // Functions

}

Example

class Employee {

  var firstName : String = ""

  var lastName : String = ""

}

Above snippet define 'Employee' class, it has two properties (firstName, lastName) defined.

How to define object to the class Employee?

var emp1 = Employee()

Above statement is used to define an object to the class Employee.

How to access the properties associated with object emp1?

Members of the object (firstName and lastName) are accessed using ‘.’ Notation.

Syntax

objName.propertyName

Example

emp1.firstName = "Chamu"

emp1.lastName = "Gurram"

Employee.kt

class Employee {

  var firstName: String = ""

  var lastName: String = ""

}

Main.kt

fun main (args: Array<String>) {

  var emp1 = Employee()

emp1.firstName = "Chamu"

emp1.lastName = "Gurram"

println( "First name : ${emp1.firstName}" )

println( "Last name : ${emp1.lastName}" )

}

Output

First name : Chamu

Last name : Gurram

# Kotlin: Declaring properties

You can define properties in a class. Properties can be mutable (or) immutable (Can't be changed once defined).

How to define mutable properties?

Mutable properties are defined using ‘var’ keyword.

Ex

var name : String = "Krishna"

How to define immutable properties?

Immutable properties are defined using ‘val’ keyword.

Ex

val name : String = "Krishna"

class Employee{

         var name : String = "Krishna"

         var age : Int = 28

         val orgID : String = "ORG1234"

}

As you notify Employee class, I defined name and age as mutable properties, orgID as immutable property.

How to access properties in a class?

By defining an object, you can access the properties of a class. ‘.’ Notation is used to access the instance property of a class.

Syntax

objectName.propertyName

HelloWorld.kt

class Employee {

  var name: String = "Krishna"

  var age: Int = 28

  val orgID: String = "ORG1234"

}

fun main (args: Array<String>) {

  var emp = Employee()

println( "name : ${emp.name}" )

println( "age : ${emp.age}" )

println( "orgID : ${emp.orgID}" )

}

Output

name : Krishna

age : 28

orgID : ORG1234

You no need to add property type while defining a property, it will be inferred by kotlin environment. But adding type improves the program readability.

class Employee {

  var name = "Krishna"

  var age = 28

  val orgID = "ORG1234"

}

# Kotlin: getters & setters to properties

In my previous post, I explained how to define properties, in addition to defining, we can add getter and setter methods to the properties.

Syntax

var <propertyName>[: <PropertyType>] [= <property_initializer>]

    [<getter>]

    [<setter>]

PropertyType, getter and setter are optional while defining a property.

HelloWorld.kt

class Employee {

  var name: String = "Krishna"

  get () = field

  set (value) {

   field = value

  }

  var age : Int = 28

  get () = field

  set (value) {

   field = value

  }

  val orgID = "ORG1234"

}

fun main (args: Array<String>) {

  var emp = Employee()

println( "name : ${emp.name}" )

println( "age : ${emp.age}" )

println( "orgID : ${emp.orgID}" )

}

Output

name : Krishna

age : 28

orgID : ORG1234

As you notify the code, I used ‘field’ identifier to refer backing field. By convention setter method takes ‘value’ as argument name, you can use any name.

Why do I require getter and setter methods?

Getter and setter methods are used to transform/validate the the data before sending/setting the information.

         var age : Int = 28

                 get() = field

                 set(value) {

                          if(value < 0 || value > 100)

                                  field = 3

                 }

For example, in the above snippet, setter method validate the age before setting it to the property age. If user sets the age to <0 (or) > 100, age will be set to 3\. Find the below working application.

HelloWorld.kt

class Employee {

  var name: String = "Krishna"

  get () = field

  set (value) {

   field = value

  }

  var age: Int = 28

  get () = field

  set (value) {

   if (value < 0 || value > 100 )

    field = 3

  }

  val orgID = "ORG1234"

}

fun main (args: Array<String>) {

  var emp = Employee()

println( "name : ${emp.name}" )

println( "age : ${emp.age}" )

println( "orgID : ${emp.orgID}" )

emp.age = - 100

println( "\nAfter setting the age to -100" )

println( "name : ${emp.name}" )

println( "age : ${emp.age}" )

println( "orgID : ${emp.orgID}" )

}

Output

name : Krishna

age : 28

orgID : ORG1234

After setting the age to -100

name : Krishna

age : 3

orgID : ORG1234

Kotlin provides default getter and setter methods for mutable (Properties defined with var keyword) properties, where as it provides only getter method for immutable (Properties defined with val keyword) properties.

var name = "Krishna" //  has type String and a default getter and setter

val orfID = "orf1234" // has type String and a default getter

# Kotlin: Define member functions of class

Functions in kotlin are defined using ‘fun’ keyword.

Ex:

fun square(x : Int) : Int{

         return x*x

}

Above code snippet define a function named ‘square’, it takes one argument of type Int and return the integer.

Employee.kt

class Employee {

  private var firstName: String = ""

  private var lastName: String = ""

  fun getFirstName (): String {

  return firstName

}

  fun getLastName (): String {

  return lastName

}

  fun setFirstName (firstName: String) {

  this .firstName = firstName

}

  fun setLastName (lastName: String) {

  this .lastName = lastName

}

}

Main.kt

fun main (args: Array<String>) {

  var emp1 = Employee()

emp1.setFirstName( "Chamu" )

emp1.setLastName( "Gurram" )

println( "firstName : ${emp1.getFirstName()}" )

println( "lastName : ${emp1.getLastName()}" )

}

Output

firstName : Chamu

lastName : Gurram

Kotlin: Member properties must be initialized

In kotlin, member properties either initialized (or) must be declared as abstract. Let’s see it by an example.

Employee.kt

class Employee {

  private var firstName: String

  private var lastName: String

  fun getFirstName (): String {

  return firstName

}

  fun getLastName (): String {

  return lastName

}

  fun setFirstName (firstName: String) {

  this .firstName = firstName

}

  fun setLastName (lastName: String) {

  this .lastName = lastName

}

}

Try to compile above program, you will end up with below error.

C:\>kotlinc Employee.kt

Employee.kt:2:2: error: property must be initialized or be abstract

        private var firstName: String

^

Employee.kt:3:2: error: property must be initialized or be abstract

        private var lastName: String

How to get rid of above error?

There are two ways, either initialize the property (or) make the property as abstract.

Way1:  Initialize the properties firstName and lastName

Employee.kt

class Employee {

  private var firstName: String = ""

  private var lastName: String = ""

  fun getFirstName (): String {

  return firstName

}

  fun getLastName (): String {

  return lastName

}

  fun setFirstName (firstName: String) {

  this .firstName = firstName

}

  fun setLastName (lastName: String) {

  this .lastName = lastName

}

}

Way 2:  Make the properties as abstract

Employee.kt

abstract class Employee {

  abstract var firstName: String

  abstract var lastName: String

}

# Kotlin: const: Compile time constants

You can define the compile time constants using ‘const’ keyword.

Ex

const val VENDOR_NAME = "Self Learning Java blog"

HelloWorld.kt

const val VENDOR_NAME = "Self Learning Java blog"

const val PI = 3.14

fun main (args: Array<String>) {

println( "Vendor Name $VENDOR_NAME" )

println( "Value of PI : $PI" )

}

Output

Vendor Name Self Learning Java blog

Value of PI : 3.14

While defining compile time constants, the properties must fulfil below preconditions.

*   Top-level or member of an object
*   Initialized with a value of type String or a primitive type
*   No custom getter

# Kotlin: const vs val

'const' keyword is used to define compile time constants,I.e, the value of the const variable is known at compile time. Whereas ‘val’ is used to define constants at run time.

For example, you can’t define a const like below.

const val PICon = getPI()

When you try to compile the kotlin program with above statement, you will endup in below error.
‘Const 'val' has type 'Unit'. Only primitives and String are allowed’. 

This is because, getPI() is evaluated at run time and assign the value to PICon, but const is used to define the constant at compile time.

Find the below working application.

HelloWorld.kt

const val VENDOR_NAME = "Self Learning Java blog"

val PICon = getPI()

fun getPI (): Double {

  return 3.14

}

fun main (args: Array<String>) {

println( "Vendor Name $VENDOR_NAME" )

println( "Value of PI : $PICon" )

}

Output

Vendor Name Self Learning Java blog

Value of PI : 3.14

# Kotlin: lateinit : Late initialized properties

By default, kotlin do not allow uninitialized properties. You must initialize them at the time of declaration (or) in the constructor. Let me explain with an example.

HelloWorld.kt

class Employee {

  var id : String

  var name : String

  var city : String

}

When you try to compile above program, you will end up in below error.

         ERROR: Property must be initialized or be abstract (2, 2)

         ERROR: Property must be initialized or be abstract (3, 2)

         ERROR: Property must be initialized or be abstract (4, 2)

How to resolve above problem?

There are three ways:

         a. Initialize the variables at the time of declaration

         b. Define the variables in constructor

         c. Use late initialization

Initialize the variables at the time of declaration

class Employee {

  var id: String = "123"

  var name: String = "Krishna"

  var city: String = "Ongole"

}

Define the variables in constructor

class Employee {

  var id: String

  var name: String

  var city: String

constructor() {

  id = "123"

  name = "Krishna"

  city = "Ongole"

}

}

Use late initialization
By using lateinit keyword, we can inform kotlin that this variable will be initialized at later point of time.

class Employee {

lateinit var id: String

lateinit var name: String

lateinit var city: String

}

Can I access lateint property before initialization?

No, If you try to access a lateinit property before initialization, you will end up in 'UninitializedPropertyAccessException'

HelloWorld.kt

class Employee {

lateinit var id: String

lateinit var name: String

lateinit var city: String

}

fun main (args: Array<String>) {

  var obj = Employee()

println( "Id : ${obj.id}" )

}

When you try to run above program, you will end up in below exception.

Exception in thread "main" kotlin.UninitializedPropertyAccessException: lateinit property id has not been initialized

         at Employee.getId(HelloWorld.kt:2)

         at HelloWorldKt.main(HelloWorld.kt:10)

To resolve the error define the lateinit properties before accessing.

HelloWorld.kt

class Employee {

lateinit var id: String

lateinit var name: String

lateinit var city: String

}

fun main (args: Array<String>) {

  var obj = Employee()

obj.id = "123"

println( "Id : ${obj.id}" )

}

Output

Id : 123

# Kotlin: Constructors

Kotlin classes have a primary constructor and one or more secondary constructors. Constructors are defined using constructor keyword.

Primary Constructor

Primary constructor is defined as part of the class header.

Ex

class Employee constructor(fName: String, lName: String) {

         ....

         ....

}

Employee.kt

class Employee constructor (fName: String, lName: String) {

init{

  println( "fName : $fName, lName : $lName" )

}

}

Main.kt

fun main (args: Array<String>) {

  var emp1 = Employee( "Hareesh" , "Seeram" )

}

Output

fName : Hareesh, lName : Seeram

init{} is equivalent to the  initializer block  of java, it is used to place the object initialization code. This block is called on every object instantiation.

You can omit the constructor keyword while defining primary constructor, if the constructor do not have any modifier (or) annotation associated with it.

Employee.kt

class Employee (fName: String, lName: String) {

init{

  println( "fName : $fName, lName : $lName" )

}

}

Defining member variables as part of primary constructor

If you add the keyword ‘var’/’val’ to the type parameter in primary constructor, it creates a field in class.

Main.kt

class Employee ( var firstName: String, var lastName: String) {

}

fun main (args: Array<String>) {

  var emp1 = Employee( "Hareesh" , "Seeram" )

println( "firstName : ${emp1.firstName}, lastName : ${emp1.lastName}" )

}

Output

firstName : Hareesh, lastName : Seeram

In the above snippet, I defined firstName and lastName fields as part of primary constructor

# Kotlin: Secondary Constructors

Kotlin class can have more than one secondary constructors.

How to define secondary constructor?

You should use the keyword ‘constructor’ to define secondary constructor.

Syntax
constructor(arguments){

}

ConstructorDemo.kt

class Employee {

  var firstName: String = ""

  var lastName: String = ""

constructor(firstName: String) {

  this .firstName = firstName

  this .lastName = firstName

}

constructor(firstName: String, lastName: String) {

  this .firstName = firstName

  this .lastName = lastName

}

}

fun printEmployee (emp: Employee) {

println( "firstName : ${emp.firstName}, lastName : ${emp.lastName}" )

}

fun main (args: Array<String>) {

  var emp1 = Employee( "Hareesh" , "Seeram" )

  var emp2 = Employee( "Praneeth" )

printEmployee(emp1)

printEmployee(emp2)

}

Output

firstName : Hareesh, lastName : Seeram

firstName : Praneeth, lastName : Praneeth

Primary constructor must be called from secondary constructor explicitly. What I mean is, if a class has primary constructor, then the secondary constructor must delegate to the primary constructor either directly (or) indirectly using other secondary constructors.

class Employee(var firstName: String) {

         ....

         ....

         constructor(fName: String, lName: String) : this(fName) {

                 this.lastName = lName

                 this.id = ""

         }

}

In the above example, Employee class has a primary constructor, We are calling primary constructor using 'this' keyword, while defining secondary constructor.

ConstructorDemo.kt

class Employee ( var firstName: String) {

  var lastName: String = ""

  var id: String = ""

constructor(fName: String, lName: String) : this (fName) {

  this .lastName = lName

  this .id = ""

}

constructor(fName: String, lName: String, id: String) : this (fName) {

  this .lastName = lName

  this .id = id

}

}

fun printEmployee (emp: Employee) {

println( "id : ${emp.id}, firstName : ${emp.firstName}, lastName : ${emp.lastName}" )

}

fun main (args: Array<String>) {

  var emp1 = Employee( "Krishna" )

  var emp2 = Employee( "Hareesh" , "Seeram" )

  var emp3 = Employee( "Praneeth" , "Sai" , "123" )

printEmployee(emp1)

printEmployee(emp2)

printEmployee(emp3)

}

Output

id : , firstName : Krishna, lastName :

id : , firstName : Hareesh, lastName : Seeram

id : 123, firstName : Praneeth, lastName : Sai

# Kotlin: Passing default values to primary constructor

You can pass default values to the primary constructor.

Ex:

class Employee(var firstName: String = "Krishna", var lastName: String = "Gurram") {

}

Above snippet defines a primary constructor to the class Employee, with default values.

var emp1 = Employee()

Since we do not pass any arguments to the constructor, firstName and lastName are initialized with default values. 'firstName' is initialized with 'Krishna' and lastName is initialized with 'Gurram'

var emp2 = Employee("Rachit")

Since we passed only first argument, 'firstName' is assigned with value 'Rachit' and 'lastName' is assigned with value 'Gurram'

var emp3 = Employee("Shwetha", "kam")

'firstName' is assigned with value 'Shwetha' and 'lastName' is assigned with value 'Kam'.    

ConstructorDemo.kt

class Employee ( var firstName: String = "Krishna" , var lastName: String = "Gurram" ) {

}

fun printEmployee (emp: Employee) {

println( "firstName : ${emp.firstName}, lastName : ${emp.lastName}" )

}

fun main (args: Array<String>) {

  var emp1 = Employee()

  var emp2 = Employee( "Rachit" )

  var emp3 = Employee( "Shwetha" , "kam" )

printEmployee(emp1)

printEmployee(emp2)

printEmployee(emp3)

}

Output

firstName : Krishna, lastName : Gurram

firstName : Rachit, lastName : Gurram

firstName : Shwetha, lastName : kam

# Kotlin: Define private primary constructor

By specifying the 'private' access specifier in the class header, you can define a private primary constructor.

PrivateConDemo.kt

class Employee private constructor ( var firstName: String) {

  var lastName: String = ""

constructor(fName: String, lName: String) : this (fName) {

  this .lastName = lName

}

}

fun printEmployee (emp: Employee) {

println( "firstName : ${emp.firstName}, lastName : ${emp.lastName}" )

}

fun main (args: Array<String>) {

  var emp1 = Employee( "Shwetha" , "kam" )

printEmployee(emp1)

}

Output

firstName : Shwetha, lastName : kam

# Kotlin: How to create Object

Unlike  Java , ' new ' keyword is not required to define an object.

Syntax

var objectName  = ClassName(arguments)

Ex

var emp1 = Employee("Shwetha")

var emp2 = Employee("Krishna", "G")

ConstructorDemo.kt

class Employee {

  var firstName: String = ""

  var lastName: String = ""

constructor(fName: String) {

  this .firstName = fName

  this .lastName = fName

}

constructor(fName: String, lName: String) {

  this .firstName = fName

  this .lastName = lName

}

}

fun printEmployee (emp: Employee) {

println( "firstName : ${emp.firstName}, lastName : ${emp.lastName}" )

}

fun main (args: Array<String>) {

  var emp1 = Employee( "Shwetha" )

  var emp2 = Employee( "Krishna" , "G" )

printEmployee(emp1)

printEmployee(emp2)

}

Output

firstName : Shwetha, lastName : Shwetha

firstName : Krishna, lastName : G

PYTHON

CODING PRACTICE EXERCISES

CODING FOR BEGINNERS

JJ TAM

# PYTHON CODING EXERCISES

# PYTHON String – Exercises

# Python: Reverse a string

![](Image00010.jpg)

### PYTHON CODE

##### def reverse_string(str1):

#####     return ''.join(reversed(str1))

##### print()

##### print(reverse_string("abcdef"))

##### print(reverse_string("Python Exercises."))

##### print()

### OUTPUT

fedcba

.sesicrexE nohtyP

# Remove a newline in Python

![](Image00011.jpg)

### PYTHON CODE

##### str1='Python Exercises\n'

##### print(str1)

##### print(str1.rstrip())

### OUTPUT

Python Exercises

Python Exercises

# Find the common values

## that appear in two given strings

### PYTHON CODE

def intersection_of_two_string(str1, str2):

    result = ""

    for ch in str1:

        if ch in str2 and not ch in result:

            result += ch

    return result

str1 = 'Python3'

str2 = 'Python2.7'

print("Original strings:")

print(str1)

print(str2)

print("\nIntersection of two said String:")

print(intersection_of_two_string(str1, str2))

### OUTPUT

Original strings:

Python3

Python2.7

Intersection of two said String:

Python

# Python Data Type: List – Exercises

# Python: Sum all the items in a list

![](Image00012.jpg)

### PYTHON CODE

##### def sum_list(items):

#####     sum_numbers = 0

#####     for x in items:

#####         sum_numbers += x

#####     return sum_numbers

##### print(sum_list([1,2,-8]))

### OUTPUT

-5

### FLOWCHART

![](Image00013.jpg)

# Get the largest number from a list

![](Image00014.jpg)

### PYTHON CODE

##### def max_num_in_list( list ):

#####     max = list[ 0 ]

#####     for a in list:

#####         if a > max:

#####             max = a

#####     return max

##### print(max_num_in_list([1, 2, -8, 0]))

### OUTPUT

2

### FLOWCHART

![](Image00015.jpg)

# Remove duplicates from a list

![](Image00016.jpg)

### PYTHON CODE

##### a = [10,20,30,20,10,50,60,40,80,50,40]

##### dup_items = set()

##### uniq_items = []

##### for x in a:

#####     if x not in dup_items:

#####         uniq_items.append(x)

#####         dup_items.add(x)

##### print(dup_items)

### OUTPUT

{40, 10, 80, 50, 20, 60, 30}

### FLOWCHART

![](Image00017.jpg)

# Python Data Types: Dictionary – Exercises

# Add a key to a dictionary

### PYTHON CODE

##### d = {0:10, 1:20}

##### print(d)

##### d.update({2:30})

##### print(d)

### OUTPUT

{0: 10, 1: 20}                                                                                               

{0: 10, 1: 20, 2: 30}

# Iterate over dictionaries using for loops

### PYTHON CODE

##### d = {'x': 10, 'y': 20, 'z': 30}

##### for dict_key, dict_value in d.items():

#####     print(dict_key,'->',dict_value)

### OUTPUT

x -> 10

y -> 20

z -> 30

# Merge two Python dictionaries

### PYTHON CODE

##### d1 = {'a': 100, 'b': 200}

##### d2 = {'x': 300, 'y': 200}

##### d = d1.copy()

##### d.update(d2)

##### print(d)

### OUTPUT

{'x': 300, 'y': 200, 'a': 100, 'b': 200}

# Multiply all the items in a dictionary

### PYTHON CODE

my_dict = {'data1':100,'data2':-54,'data3':247}

result=1

for key in my_dict:   

    result=result * my_dict[key]

print(result)

### OUTPUT

-1333800

# Remove a key from a dictionary

### PYTHON CODE

##### myDict = {'a':1,'b':2,'c':3,'d':4}

##### print(myDict)

##### if 'a' in myDict:

#####     del myDict['a']

##### print(myDict)

### OUTPUT

{'a': 1, 'b': 2, 'c': 3, 'd': 4}

{'b': 2, 'c': 3, 'd': 4}

# Get a dictionary from an object's fields

### PYTHON CODE

##### class dictObj(object):

#####      def __init__(self):

#####          self.x = 'red'

#####          self.y = 'Yellow'

#####          self.z = 'Green'

#####      def do_nothing(self):

#####          pass

##### test = dictObj()

##### print(test.__dict__)

### OUTPUT

{'x': 'red', 'y': 'Yellow', 'z': 'Green'}

# Combine two dictionary adding values for common keys

### PYTHON CODE

##### from collections import Counter

##### d1 = {'a': 100, 'b': 200, 'c':300}

##### d2 = {'a': 300, 'b': 200, 'd':400}

##### d = Counter(d1) + Counter(d2)

##### print(d)

### OUTPUT

Counter({'b': 400, 'd': 400, 'a': 400, 'c': 300})

# Find the highest 3 values

## of corresponding keys in a dictionary

### PYTHON CODE

##### from heapq import nlargest

##### my_dict = {'a':500, 'b':5874, 'c': 560,'d':400, 'e':5874, 'f': 20} 

##### three_largest = nlargest(3, my_dict, key=my_dict.get)

##### print(three_largest)

### OUTPUT

['b', 'e', 'c']