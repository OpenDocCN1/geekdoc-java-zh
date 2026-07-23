![](Images/cover00118.jpeg)

JAVA AND C#

CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

[JAVA CODING EXERCISES](#part0002.xhtml__Toc59455724)

[Print hello](#part0002.xhtml__Toc59455725)

[Print the sum](#part0003.xhtml__Toc59455726)

[Divide two numbers](#part0004.xhtml__Toc59455727)

[Print the result](#part0005.xhtml__Toc59455728)

[Print multiplication table](#part0006.xhtml__Toc59455729)

[Find the area](#part0007.xhtml__Toc59455730)

[Swap two variables](#part0008.xhtml__Toc59455731)

[Print a face](#part0009.xhtml__Toc59455732)

[Fahrenheit to Celsius degree](#part0010.xhtml__Toc59455733)

[Inches to meters](#part0011.xhtml__Toc59455734)

[Adds all the digits](#part0012.xhtml__Toc59455735)

[Print the number of years and days](#part0013.xhtml__Toc59455736)

[Compute (BMI)](#part0014.xhtml__Toc59455737)

[Calculate speed in meters](#part0015.xhtml__Toc59455738)

[Divide the two specified integers](#part0016.xhtml__Toc59455739)

[Multiply two specified integers](#part0017.xhtml__Toc59455740)

[Print the sum](#part0018.xhtml__Toc59455741)

[Find the greatest of three numbers](#part0019.xhtml__Toc59455742)

[Display the multiplication table](#part0020.xhtml__Toc59455743)

[Display the pattern](#part0021.xhtml__Toc59455744)

[Print a pattern like a pyramid](#part0022.xhtml__Toc59455745)

[Display the number rhombus structure](#part0023.xhtml__Toc59455746)

[C# SHARP CODING EXERCISES](#part0025.xhtml__Toc59455747)

[Print hello and your name](#part0025.xhtml__Toc59455748)

[Print the result of the specified operations](#part0026.xhtml__Toc59455749)

[Program to swap two numbers](#part0027.xhtml__Toc59455750)

[Print the output of multiplication](#part0028.xhtml__Toc59455751)

[Adding, subtracting, multiplying and dividing](#part0029.xhtml__Toc59455752)

[Print the average of four numbers](#part0030.xhtml__Toc59455753)

[Program to convert Temperature](#part0031.xhtml__Toc59455754)

[Compute the sum](#part0032.xhtml__Toc59455755)

[Compute sum](#part0033.xhtml__Toc59455756)

[C# program to check](#part0034.xhtml__Toc59455757)

[C# Sharp program to check two given integers](#part0035.xhtml__Toc59455758)

[C# Sharp program to check a given positive number](#part0036.xhtml__Toc59455759)

[check whether a given string starts with 'C#' or not](#part0037.xhtml__Toc59455760)

[C# Sharp program to check the largest number](#part0038.xhtml__Toc59455761)

[Program to check which number is nearest to the value 100](#part0039.xhtml__Toc59455762)

[Program to convert the last 3 characters](#part0040.xhtml__Toc59455763)

[Program to create a new string](#part0041.xhtml__Toc59455764)

[Perform an operation](#part0042.xhtml__Toc59455765)

[Calculate the perimeter](#part0043.xhtml__Toc59455766)

[C# Sharp Conditional Statement](#part0044.xhtml__Toc59455767)

[C program to Check whether a number is even or odd](#part0044.xhtml__Toc59455768)

[Check a number is positive or negative](#part0045.xhtml__Toc59455769)

[C# Sharp program to accept the height of a person](#part0046.xhtml__Toc59455770)

[Find the largest of three numbers](#part0047.xhtml__Toc59455771)

[Calculate profit and loss](#part0048.xhtml__Toc59455772)

# JAVA CODING EXERCISES

# Print hello

## And your name

### On a separate lines

### JAVACODE

##### import java.util.Scanner;

##### public class Main {

#####   public static void main(String[] args)

#####   {

#####     Scanner input = new Scanner (System.in);

#####     System.out.print("Input your first name: ");

#####     String fname = input.next();

#####     System.out.print("Input your last name: ");

#####     String lname = input.next();

#####     System.out.println();

#####     System.out.println("Hello \n"+fname+" "+lname);

#####   }

##### }

### OUTPUT

Input your first name: JJ

Input your last name: TAM

Hello

JJ TAM

# Print the sum

## Of two numbers

### JAVACODE

##### import java.util.Scanner;

##### public class Main {

#####   public static void main(String[] args)

#####   {

#####     Scanner input = new Scanner (System.in);

#####     System.out.print("Input the first number: ");

#####     int num1 = input.nextInt();

#####     System.out.print("Input the second number: ");

#####     int num2 = input.nextInt();

#####     int sum = num1 + num2;

#####     System.out.println();

#####     System.out.println("Sum: "+sum);

#####   }

##### }

### OUTPUT

Input the first number: 545

Input the second number: 455

Sum: 1000

# Divide two numbers

## And print on the screen

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####   public static void main(String[] args)

#####   {

#####     Scanner input = new Scanner (System.in);

#####     System.out.print("Input the first number: ");

#####     int a = input.nextInt();

#####     System.out.print("Input the second number: ");

#####     int b = input.nextInt();

#####     int d = (a/b);

#####     System.out.println();

#####     System.out.println("The division of a and b is:" +d);

#####   }

##### }

### OUTPUT

Input the first number: 100

Input the second number: 25

The division of a and b is:4

# Print the result

## Of specified operations

### JAVA CODE

##### public class Main {

##### public static void main(String[] args) {

#####    int w = -5 + 8 * 6;

#####    int x = (55 + 9) % 9;

#####    int y = 20 + (-3 * 5 / 8);

#####    int z = 5 + 15 / 3 * 2 - 8 % 3;

#####    System.out.print(w + "\n" + x + "\n" + y + "\n" + z);

#####   }

##### }

# Print multiplication table

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

##### public static void main(String[] args) {

#####   Scanner in = new Scanner(System.in);

#####   System.out.println("Input the Number: ");

#####   int n = in .nextInt();

#####   for (int i = 1; i <= 10; i++) {

#####    System.out.println(n + "*" + i + " = " + (n * i));

#####   }

##### }

##### }

### OUTPUT

Input the Number:

15

15*1 = 15

15*2 = 30

15*3 = 45

15*4 = 60

15*5 = 75

15*6 = 90

15*7 = 105

15*8 = 120

15*9 = 135

15*10 = 150

# Find the area

## And perimeter of a circle

### JAVA CODE

import java.util.Scanner;

public class Main {

public static void main(String[] args) {

  Scanner io = new Scanner(System.in);

  System.out.println("Input the radius of the circle: ");

  double radius = io.nextDouble();

  System.out.println("Perimeter is = " + (2 * radius * Math.PI));

  System.out.println("Area is = " + (Math.PI * radius * radius));

}

}

### OUTPUT

Input the radius of the circle:

10

Perimeter is = 62.83185307179586

Area is = 314.1592653589793

# Swap two variables

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

##### public static void main(String[] args) {

#####    int x, y, z;

#####    Scanner in = new Scanner(System.in);

#####    System.out.println("Input the first number: ");

#####    x = in.nextInt();

#####    System.out.println("Input the second number: ");

#####    y = in.nextInt();

#####    z = x;

#####    x = y;

#####    y = z;

#####    System.out.println(" Swapped values are3:" + x + " and " + y);

#####   }

##### }

### OUTPUT

Input the first number:

25

Input the second number:

50

Swapped values are3:50 and 25

# Print a face

### JAVA CODE

##### public class Main {

##### public static void main(String[] args) {

#####   String[] arra = new String[5];

#####   arra[0] = " +\"\"\"\"\"+ ";

#####   arra[1] = "[| o o |]";

#####   arra[2] = " |  ^  |";

#####   arra[3] = " | '-' |";

#####   arra[4] = " +-----+";

#####   for (int i = 0; i < 5; i++) {

#####    System.out.println(arra[i]);

#####   }

##### }

##### }

### OUTPUT

+"""""+

[| o o |]

|  ^  |

| '-' |

+-----+

# Fahrenheit to Celsius degree

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] Strings) {

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input a degree in Fahrenheit: ");

#####         double fahrenheit = input.nextDouble();

#####         double  celsius =(( 5 *(fahrenheit - 32.0)) / 9.0);

#####         System.out.println(fahrenheit + " degree Fahrenheit is equal to " + celsius + " in Celsius");

#####     }

##### }

### OUTPUT

Input a degree in Fahrenheit: 96

96.0 degree Fahrenheit is equal to 35.55555555555556 in Celsius

# Inches to meters

![](Images/image00109.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] Strings) {

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input a value for inch: ");

#####         double inch = input.nextDouble();

#####         double meters = inch * 0.0254;

#####         System.out.println(inch + " inch is " + meters + " meters");

#####     }

##### }

### OUTPUT

Input a value for inch: 5

5.0 inch is 0.127 meters

# Adds all the digits

![](Images/image00110.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] Strings) {

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input an integer between 0 and 1000: ");

#####         int num = input.nextInt();

#####         int firstDigit = num % 10;

#####         int remainingNumber = num / 10;

#####         int SecondDigit = remainingNumber % 10;

#####         remainingNumber = remainingNumber / 10;

#####         int thirdDigit = remainingNumber % 10;

#####         remainingNumber = remainingNumber / 10;

#####         int fourthDigit = remainingNumber % 10;

#####         int sum = thirdDigit + SecondDigit + firstDigit + fourthDigit;

#####         System.out.println("The sum of all digits in " + num + " is " + sum);

#####     }

##### }

### OUTPUT

Input an integer between 0 and 1000: 750

The sum of all digits in 750 is 12

# Print the number of years and days

## From minutes

![](Images/image00111.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] Strings) {

#####         double minutesInYear = 60 * 24 * 365;

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input the number of minutes: ");

#####         double min = input.nextDouble();

#####         long years = (long) (min / minutesInYear);

#####         int days = (int) (min / 60 / 24) % 365;

#####         System.out.println((int) min + " minutes is approximately " + years + " years and " + days + " days");

#####     }

##### }

### OUTPUT

Input the number of minutes: 123456

123456 minutes is approximately 0 years and 85 days

# Compute (BMI)

## Body mass index

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] Strings) {

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input weight in pounds: ");

#####         double weight = input.nextDouble();

#####         System.out.print("Input height in inches: ");

#####         double inches = input.nextDouble();

#####         double BMI = weight * 0.45359237 / (inches * 0.0254 * inches * 0.0254);

#####         System.out.print("Body Mass Index is " + BMI+"\n");

#####     }

##### }

### OUTPUT

Input weight in pounds: 450

Input height in inches: 72

Body Mass Index is 61.03034545478814

# Calculate speed in meters

## per second, kilometers and miles per hour

![](Images/image00112.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] args) {

##### Scanner scanner = new Scanner(System.in);

##### float timeSeconds;

##### float mps,kph, mph;

##### System.out.print("Input distance in meters: ");

##### float distance = scanner.nextFloat();

##### System.out.print("Input hour: ");

##### float hr = scanner.nextFloat();

##### System.out.print("Input minutes: ");

##### float min = scanner.nextFloat();

##### System.out.print("Input seconds: ");

##### float sec = scanner.nextFloat();

##### timeSeconds = (hr*3600) + (min*60) + sec;

##### mps = distance / timeSeconds;

##### kph = ( distance/1000.0f ) / ( timeSeconds/3600.0f );

##### mph = kph / 1.609f;

##### System.out.println("Your speed in meters/second is "+mps);

##### System.out.println("Your speed in km/h is "+kph);

##### System.out.println("Your speed in miles/h is "+mph);

##### scanner.close();

##### }

##### }

### OUTPUT

Input distance in meters: 3000

Input hour: 5

Input minutes: 32

Input seconds: 29

Your speed in meters/second is 0.15038347

Your speed in km/h is 0.5413805

Your speed in miles/h is 0.3364702

# Divide the two specified integers

## using subtraction operator

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

##### public static float divide_using_subtraction(int dividend, int divider) {

##### if (divider == 0) {

#####        return 0;

##### }  

#####     float result = 0;

#####     while (dividend > divider) {

#####       dividend -= divider;

#####       result++;

#####     }

#####     float decimalPart = (float) dividend / (float) divider;

#####     result += decimalPart;

#####     return result;

#####   }

#####     public static void main(String[] args) {

##### Scanner in = new Scanner(System.in);

#####         System.out.print("Input the dividend: ");

#####         int dividend = in.nextInt();

##### System.out.print("Input the divider: ");

#####         int divider = in.nextInt();

##### System.out.println("\nResult: " + divide_using_subtraction(dividend,divider));                           

##### }

##### }

### OUTPUT

Input the dividend: 900

Input the divider: 30

Result: 30.0

# Multiply two specified integers

## without using the multiply operator

### JAVA CODE

##### import java.util.*;

##### public class Main {

#####   public static int multiply(int n1, int n2) {

#####     int result = 0;

#####     boolean negative_num = (n1 < 0 && n2 >= 0) || (n2 < 0 && n1 >= 0);

#####     boolean positive_num = !negative_num;

#####     n1 = Math.abs(n1);

#####     for (int i = 0; i < n1; i++) {

#####       if (negative_num && n2 > 0 || positive_num && n2 < 0)

#####         result -= n2;

#####       else

#####         result += n2;

#####     }

#####     return result;

##### }

#####    public static void main(String[] args) {

#####         Scanner in = new Scanner(System.in);

#####         System.out.print("Input the first number: ");

#####         int n1 = in.nextInt();

##### System.out.print("Input the second number: ");

#####         int n2 = in.nextInt();

##### System.out.println("\nResult: " + multiply(n1,n2));

##### }

##### }

### OUTPUT

Input the first number: 25

Input the second number: 30

Result: 750

# Print the sum

## Difference, product, average, distance, maximum and minimum

![](Images/image00113.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####     public static void main(String[] args)

#####     {

#####         Scanner in = new Scanner(System.in);

#####         System.out.print("Input 1st integer: ");

#####         int firstInt = in.nextInt();

#####         System.out.print("Input 2nd integer: ");

#####         int secondInt = in.nextInt();

#####         System.out.printf("Sum of two integers: %d%n", firstInt + secondInt);

#####         System.out.printf("Difference of two integers: %d%n", firstInt - secondInt);

#####         System.out.printf("Product of two integers: %d%n", firstInt * secondInt);

#####         System.out.printf("Average of two integers: %.2f%n", (double) (firstInt + secondInt) / 2);

#####         System.out.printf("Distance of two integers: %d%n", Math.abs(firstInt - secondInt));

#####         System.out.printf("Max integer: %d%n", Math.max(firstInt, secondInt));

#####         System.out.printf("Min integer: %d%n", Math.min(firstInt, secondInt));

#####     }

##### }

### OUTPUT

Input 1st integer: 50

Input 2nd integer: 30

Sum of two integers: 80

Difference of two integers: 20

Product of two integers: 1500

Average of two integers: 40.00

Distance of two integers: 20

Max integer: 50

Min integer: 30

# Find the greatest of three numbers

## Java Conditional Statement

![](Images/image00114.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####   public static void main(String[] args) {

#####   Scanner in = new Scanner(System.in);

#####   System.out.print("Input the 1st number: ");

#####   int num1 = in.nextInt();

#####   System.out.print("Input the 2nd number: ");

#####   int num2 = in.nextInt();

#####   System.out.print("Input the 3rd number: ");

#####   int num3 = in.nextInt();

#####   if (num1 > num2)

#####    if (num1 > num3)

#####     System.out.println("The greatest: " + num1);

#####   if (num2 > num1)

#####    if (num2 > num3)

#####     System.out.println("The greatest: " + num2);

#####   if (num3 > num1)

#####    if (num3 > num2)

#####     System.out.println("The greatest: " + num3);

##### }

##### }

### OUTPUT

Input the 1st number: 25

Input the 2nd number: 58

Input the 3rd number: 98

The greatest: 98

# Display the multiplication table

## of a given integer

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####    public static void main(String[] args)

##### {

#####    int j,n;

#####    System.out.print("Input the number(Table to be calculated): ");

##### {

#####    System.out.print("Input number of terms : ");

#####     Scanner in = new Scanner(System.in);

#####     n = in.nextInt();

#####    System.out.println ("\n");

#####    for(j=0;j<=n;j++)

#####      System.out.println(n+" X "+j+" = " +n*j);

#####    }

##### }

##### }

### OUTPUT

Input the number(Table to be calculated): Input number of terms : 7

7 X 0 = 0

7 X 1 = 7

7 X 2 = 14

7 X 3 = 21

7 X 4 = 28

7 X 5 = 35

7 X 6 = 42

7 X 7 = 49

# Display the pattern

## like right angle triangle

### with a number

![](Images/image00115.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####    public static void main(String[] args)

##### {

#####    int i,j,n;

#####    System.out.print("Input number of rows : ");

##### Scanner in = new Scanner(System.in);

#####     n = in.nextInt();

#####    for(i=1;i<=n;i++)

#####    {

##### for(j=1;j<=i;j++)

#####   System.out.print(j);

#####     System.out.println("");

#####     }

##### }

##### }

### OUTPUT

Input number of rows : 9

1

12

123

1234

12345

123456

1234567

12345678

123456789

# Print a pattern like a pyramid

![](Images/image00116.jpeg)

### JAVA CODE

import java.util.Scanner;

public class Main {

  public static void main(String[] args)

{

   int i,j,n,s,x;

   System.out.print ("Input number of rows : ");

   Scanner in = new Scanner(System.in);

    n = in.nextInt();

   s=n+4-1;

    for(i=1;i<=n;i++)

   {

   for(x=s;x!=0;x--)

    {

   System.out.print(" ");

    }

    for(j=1;j<=i;j++)

    {

     System.out.print(i+" ");

     }

System.out.println();

    s--;

   }

}

}

### OUTPUT

Input number of rows : 7

          1

         2 2

        3 3 3

       4 4 4 4

      5 5 5 5 5

     6 6 6 6 6 6

    7 7 7 7 7 7 7

# Display the number rhombus structure

![](Images/image00117.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Main {

#####   public static void main(String args[])

#####     {

#####         Scanner in = new Scanner(System.in);

#####         System.out.print("Input the number:  ");

#####         int n = in.nextInt();

#####         int count = 1;

#####         int no_of_spaces = 1;

#####         int start = 0;

#####         for (int i = 1; i < (n * 2); i++)

#####         {

#####             for (int spc = n - no_of_spaces; spc > 0; spc--)

#####             {

#####                 System.out.print(" ");

#####             }

#####             if (i < n)

#####             {

#####                 start = i;          //for number

#####                 no_of_spaces++;    //for spaces

#####             } else

#####             {

#####                 start = n * 2 - i;   //for number

#####                 no_of_spaces--;      //for space

#####             }

#####             for (int j = 0; j < count; j++)

#####             {

#####                 System.out.print(start);

#####                 if (j < count / 2)

#####                 {

#####                     start--;

#####                 } else

#####                 {

#####                     start++;

#####                 }

#####             }

#####             if (i < n)

#####             {

#####                 count = count + 2;

#####             } else {

#####                 count = count - 2;

#####             }

#####             System.out.println();

#####         }

#####     }

##### }

### OUTPUT

Input the number: 7

      1

     212

    32123

   4321234

  543212345

65432123456

7654321234567

65432123456

  543212345

   4321234

    32123

     212

      1

C# SHARP

CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

# C# SHARP CODING EXERCISES

# Print hello and your name

## in a separate line in C#

### C# CODE

##### public class Exercise1

##### {

#####     public static void Main( )

#####     {

#####          System.Console.WriteLine("Hello");

#####          System.Console.WriteLine("JJ TAM!");

#####     }

##### }

### Output:

Hello

JJ TAM

# Print the result of the specified operations

### C# CODE

##### public class Exercise4

##### {

#####     public static void Main()

#####     {

#####         System.Console.WriteLine(-1+4*6);

##### //-1 + 24 = 23

#####         System.Console.WriteLine((35+5)%7);

##### //40 % 7 = 5 (remainder of 40/7)

#####         System.Console.WriteLine(14+-4*6/11);

#####         //14 - (24/11)= 14 - 2 = 12

#####         System.Console.WriteLine(2+15/6*1-7%2);

##### //2 + (15/6) - remainder of (7/2) = 2 + 2 - 1 = 4 - 1 = 3

#####     }

##### }

### Output:

23                                                                                                           

5                                                                                                            

12                                                                                                           

3

# Program to swap two numbers

### C# CODE

##### using System;

##### public class Exercise5

##### {

#####        public static void Main(string[] args)

#####          {

#####             int number1, number2, temp;

#####             Console.Write("\nInput the First Number : ");

#####             number1 = int.Parse(Console.ReadLine());

#####             Console.Write("\nInput the Second Number : ");

#####             number2 = int.Parse(Console.ReadLine());

#####             temp = number1;

#####             number1 = number2;

#####             number2 = temp;

#####             Console.Write("\nAfter Swapping : ");

#####             Console.Write("\nFirst Number : "+number1);

#####             Console.Write("\nSecond Number : "+number2);

#####             Console.Read();

#####         }

##### }

### Output:

Input the First Number : 2   

Input the Second Number : 5   

After Swapping :                                                                                             

First Number : 5                                                                                             

Second Number : 2

# Print the output of multiplication

## of three numbers

### which will be entered by the user

### C# CODE

##### using System;

##### public class Exercise6

##### {

#####   public static void Main()

#####   {

#####     int num1, num2, num3;

#####     Console.Write("Input the first number to multiply: ");

#####     num1 = Convert.ToInt32(Console.ReadLine());

#####     Console.Write("Input the second number to multiply: ");

#####     num2 = Convert.ToInt32(Console.ReadLine());

#####     Console.Write("Input the third number to multiply: ");

#####     num3 = Convert.ToInt32(Console.ReadLine());

#####     int result = num1 * num2 * num3;

#####     Console.WriteLine("Output: {0} x {1} x {2} = {3}",

#####                         num1, num2, num3, result);

#####   }

##### }

### Output:

Input the first number to multiply: 2                                                                        

Input the second number to multiply: 8                                                                       

Input the third number to multiply: 5                                                                        

Output: 2 x 8 x 5 = 80

# Adding, subtracting, multiplying and dividing

## of two numbers which

### will be entered by the user

### C# CODE

##### using System;

##### public class Exercise7

##### {

#####     public static void Main()

#####     {

#####         Console.Write("Enter a number: ");

#####         int num1= Convert.ToInt32(Console.ReadLine());

#####         Console.Write("Enter another number: ");

#####         int num2= Convert.ToInt32(Console.ReadLine());

#####         Console.WriteLine("{0} + {1} = {2}", num1, num2, num1+num2);

#####         Console.WriteLine("{0} - {1} = {2}", num1, num2, num1-num2);

#####         Console.WriteLine("{0} x {1} = {2}", num1, num2, num1*num2);

#####         Console.WriteLine("{0} / {1} = {2}", num1, num2, num1/num2);

#####         Console.WriteLine("{0} mod {1} = {2}", num1, num2, num1%num2);

#####    }

##### }

### Output:

Enter a number: 10                                                                                           

Enter another number: 2                                                                                      

10 + 2 = 12                                                                                                  

10 - 2 = 8                                                                                                   

10 x 2 = 20                                                                                                  

10 / 2 = 5                                                                                                   

10 mod 2 = 0

# Print the average of four numbers

### C# CODE

##### using System;

##### using System.IO;

##### public class Exercise9

##### {

#####   public static void Main()

#####   {

#####      double number1,number2,number3,number4;

#####      Console.Write("Enter the First number: ");

#####      number1 = Convert.ToDouble(Console.ReadLine());

#####      Console.Write("Enter the Second number: ");

#####      number2 = Convert.ToDouble(Console.ReadLine());

#####      Console.Write("Enter the third number: ");

#####      number3 = Convert.ToDouble(Console.ReadLine());

#####      Console.Write("Enter the fourth number: ");

#####      number4 = Convert.ToDouble(Console.ReadLine());

#####      double result = (number1 + number2 + number3 + number4) / 4;

#####      Console.WriteLine("The average of {0}, {1}, {2}, {3} is: {4} ",

#####   number1, number2, number3, number4, result);

#####    }

##### }

### Output:

Enter the First number: 17                                                                                   

Enter the Second number: 17                                                                                   

Enter the third number: 517                                                                                  

Enter the four number: 51                                                                                   

The average of 17, 17, 517, 51 is: 150.5

# Program to convert Temperature

## from celsius degrees

### to Kelvin and Fahrenheit

kelvin = celsius + 273
fahrenheit = celsius x 18 / 10 + 32

### C# CODE

##### using System;

##### public class Exercise14

##### {

#####    public static void Main( )

#####     {

#####         Console.Write("Enter the amount of celsius: ");

#####         int celsius = Convert.ToInt32(Console.ReadLine());

#####         Console.WriteLine("Kelvin = {0}", celsius + 273);

#####         Console.WriteLine("Fahrenheit = {0}", celsius * 18 / 10 + 32);

#####     }

##### }

### Output:

Enter the amount of celsius: 40                                                                              

Kelvin = 313                                                                                                 

Fahrenheit = 104

# Compute the sum

## of two given integers,

### if two values are equal then return the triple of their sum

### C# CODE

##### using System;

##### using System.Collections.Generic;

##### public class Exercise19 {

#####   static void Main(string[] args)

#####         {

#####             Console.WriteLine(SumTriple(2,2));

#####             Console.WriteLine(SumTriple(12,10));

#####             Console.WriteLine(SumTriple(-5,2));         

#####         }

#####         public static int SumTriple(int a, int b)

#####         {

#####             return a == b ? (a + b)*3 : a + b;

#####         }

##### }

### Output:

12                                                                    

22                                                                    

-3

# Compute sum

## of all the elements

### of an array of integers

### C# CODE

##### using System;

##### using System.Collections.Generic;

##### using System.Linq;

##### using System.Text;

##### using System.Threading.Tasks;

##### public class Exercise47

##### { 

#####    public static void Main()

#####       {

#####          int[] nums = {1, 2, 2, 3, 3, 4, 5, 6, 5, 7, 7, 7, 8, 8, 1};

#####          Console.WriteLine("\nArray1: [{0}]", string.Join(", ", nums));

#####          var sum = 0;

#####             for (var i = 0; i < nums.Length; i++)

#####             {

#####                 sum += nums[i];

#####             }

#####            Console.WriteLine("Sum: "+ sum);

#####     }

##### }

### Output:

Array1: [1, 2, 2, 3, 3, 4, 5, 6, 5, 7, 7, 7, 8, 8, 1]                 

Sum: 69

# C# program to check

## if an array contains an odd number

### CODE

##### using System;

##### using System.Collections.Generic;

##### using System.Linq;

##### using System.Text;

##### using System.Threading.Tasks;

##### public class Exercise53

##### { 

#####    public static void Main()

#####       {

#####          int[] nums = {2, 4, 7, 8, 6};

#####          Console.WriteLine("\nOriginal array: [{0}]", string.Join(", ", nums));

#####          Console.WriteLine("Check if an array contains an odd number? "+even_odd(nums));

#####       } 

#####     public static bool even_odd(int[] nums) 

#####     {

#####          foreach (var n in nums)

#####             {

#####                 if (n % 2 != 0)

#####                 return true;

#####             }

#####         return false;

#####      }

##### }

### OUTPUT

Original array: [2, 4, 7, 8, 6]                                       

Check if an array contains an odd number? True

# C# Sharp program to check two given integers

### and return true if one of them is 30 or if their sum is 30

### C# CODE

##### using System;

##### namespace exercises

##### {

#####      class Program

#####     {

#####         static void Main(string[] args)

#####         {

#####             Console.WriteLine(test(30, 0));

#####             Console.WriteLine(test(25, 5));

#####             Console.WriteLine(test(20, 30));

#####             Console.WriteLine(test(20, 25));

#####             Console.ReadLine();

#####         }

#####       public static bool test(int x, int y)

#####         {

#####             return x == 30 || y == 30 || (x + y == 30);

#####         }

#####   }

##### }

Output:

True

True

True

False

# C# Sharp program to check a given positive number

## is a multiple of 3 or a multiple of 7

### C# CODE

##### using System;

##### namespace exercises

##### {

##### class Program

#####     {

#####         static void Main(string[] args)

#####         {

#####             Console.WriteLine(test(3));

#####             Console.WriteLine(test(14));

#####             Console.WriteLine(test(12));

#####             Console.WriteLine(test(37));

#####             Console.ReadLine();

#####         }

#####         public static bool test(int n)

#####         {

#####             return n % 3 == 0 || n % 7 == 0;

#####         }

#####     }

##### }

Output:

True

True

True

False

# check whether a given string starts with 'C#' or not

### C# CODE

##### using System;

##### namespace exercises

##### {

##### class Program

#####     {

#####         static void Main(string[] args)

#####         {

#####             Console.WriteLine(test("C# Sharp"));

#####             Console.WriteLine(test("C#"));

#####             Console.WriteLine(test("C++"));

#####             Console.ReadLine();

#####         }

#####    public static bool test(string str)

#####         {

#####             return (str.Length < 3 && str.Equals("C#")) || (str.StartsWith("C#") && str[2] == ' ');

#####         }

#####     }

##### }

Output:

True

True

False

# C# Sharp program to check the largest number

## among three given integers

### C# CODE

##### using System;

##### namespace exercises

##### {

#####    class Program

#####     {

#####         static void Main(string[] args)

#####         {

#####             Console.WriteLine(test(1,2,3));

#####             Console.WriteLine(test(1,3,2));

#####             Console.WriteLine(test(1,1,1));

#####             Console.WriteLine(test(1,2,2));

#####             Console.ReadLine();

#####         }

#####        public static int test(int x, int y, int z)

#####         {

#####             var max = Math.Max(x, Math.Max(y, z));

#####             return max;

#####         }

#####     }

##### }

 Output:

3

3

1

2

# Program to check which number is nearest to the value 100

## among two given integers

### Return 0 if the two numbers are equal.

### C# CODE

##### using System;

##### namespace exercises

##### {

#####    class Program

#####     {

#####         static void Main(string[] args)

#####         {

#####             Console.WriteLine(test(78, 95));

#####             Console.WriteLine(test(95, 95));

#####             Console.WriteLine(test(99, 70));

#####             Console.ReadLine();

#####         }

#####         public static int test(int x, int y)

#####         {

#####             const int n = 100;

#####             var val = Math.Abs(x - n);

#####             var val2 = Math.Abs(y - n);

#####             return val == val2 ? 0 : (val < val2 ? x : y);

#####         }

#####     }

##### }

Output:

95

0

99

# Program to convert the last 3 characters

## of a given string in upper case

### If the length of the string has less than 3 then uppercase all the characters.

### C# CODE

##### using System;

##### namespace exercises

##### {

#####    class Program

#####     {

#####         static void Main(string[] args)

#####         {

#####             Console.WriteLine(test("Python"));

#####             Console.WriteLine(test("Javascript"));

#####             Console.WriteLine(test("js"));

#####             Console.WriteLine(test("PHP"));

#####             Console.ReadLine();

#####         }

#####      public static string test(string str)

#####         {

#####             return str.Length < 3 ? str.ToUpper() : str.Remove(str.Length - 3) + str.Substring(str.Length - 3).ToUpper();

#####         }

#####   }

##### }

 Output:

PytHON

JavascrIPT

JS

PHP

# Program to create a new string

### of the characters at indexes 0,1, 4,5, 8,9 ... from a given string.

### C# CODE

##### using System;

##### using System.Linq;

##### namespace exercises

##### {

#####    class Program

#####     {

#####        static void Main(string[] args)

#####         {

#####             Console.WriteLine(test("Python"));

#####             Console.WriteLine(test("JavaScript"));

#####             Console.WriteLine(test("HTML"));

#####             Console.ReadLine();

#####         }

#####         public static string test(string str1)

#####           {

#####            var result = string.Empty;

#####             for (var i = 0; i < str1.Length; i += 4)

#####             {

#####                 var c = i + 2;

#####                 var n = 0;

#####                 n += c > str1.Length ? 1 : 2;

#####                 result += str1.Substring(i, n);

#####             }

#####             return result;

#####         }

#####     }

##### }

Output:

Pyon

JaScpt

HT

# Perform an operation

### on +, -, *, x, / and displays the result of that operation

### C# CODE

##### using System;

##### public class Exercise4

##### {

#####     public static void Main()

#####     {

#####         int x, y;

#####         char operation;

#####         Console.Write("Input first number: ");

#####         x = Convert.ToInt32(Console.ReadLine());

#####         Console.Write("Input operation: ");

#####         operation = Convert.ToChar(Console.ReadLine());

#####         Console.Write("Input second number: ");

#####         y = Convert.ToInt32(Console.ReadLine());

#####         if (operation=='+')

#####             Console.WriteLine("{0} + {1} = {2}", x, y, x+y);

#####         else if (operation=='-')

#####             Console.WriteLine("{0} - {1} = {2}", x, y, x-y);

#####         else if ((operation=='x') || (operation=='*'))

#####             Console.WriteLine("{0} * {1} = {2}", x, y, x*y);

#####         else if (operation=='/')

#####             Console.WriteLine("{0} / {1} = {2}", x, y, x/y);

#####         else

#####             Console.WriteLine("Wrong Character");

#####     }

##### }

Output:

Input first number: 4                                                                                        

Input operation: *                                                                                           

Input second number: 4                                                                                       

4 * 4 = 16

# Calculate the perimeter

## of a circle

### C# CODE

##### using System;

##### public class Exercise5

##### {

#####     public static void Main()

#####     {

#####         double r,per_cir;

#####         double PI = 3.14;

#####         Console.WriteLine("Input the radius of the circle : ");

#####         r = Convert.ToDouble(Console.ReadLine());

#####         per_cir = 2 * PI * r;

#####         Console.WriteLine("Perimeter of Circle : {0}", per_cir);

#####         Console.Read();

#####     }

##### }

Output:

Input the radius of the circle :                                                                           

25

Perimeter of Circle : 157

# C# Sharp Conditional Statement

# C program to Check whether a number is even or odd

### C# CODE

##### using System; 

##### public class Exercise2 

##### { 

#####     public static void Main() 

#####     {

#####     int num1, rem1;

#####     Console.Write("\n\n");

#####     Console.Write("Check whether a number is even or odd :\n");

#####     Console.Write("---------------------------------------");

#####     Console.Write("\n\n");

#####     Console.Write("Input an integer : ");

#####     num1= Convert.ToInt32(Console.ReadLine());

#####     rem1 = num1 % 2;

#####     if (rem1 == 0)

##### Console.WriteLine("{0} is an even integer.\n",num1);

#####     else

##### Console.WriteLine("{0} is an odd integer.\n",num1);

##### }

##### }

Output:

##### Check whether a number is even or odd :                                                                      

##### ---------------------------------------

##### Input an integer : 10                                                                                        

##### 10 is an even integer.

# Check a number is positive or negative

### C# CODE

##### using System; 

##### public class Exercise3 

##### { 

#####     public static void Main() 

#####     {

#####     int num;

#####     Console.Write("\n\n");

#####     Console.Write("Check whether a number is positive or negative:\n");

#####     Console.Write("----------------------------------------------");

#####     Console.Write("\n\n");

#####     Console.Write("Input an integer : ");

#####     num= Convert.ToInt32(Console.ReadLine());

#####     if (num >= 0)

##### Console.WriteLine("{0} is a positive number.\n",num);

#####     else

#####         Console.WriteLine("{0} is a negative number. \n", num);

##### }

##### }

Output:

##### Check whether a number is positive or negative:                                                              

##### ----------------------------------------------

##### Input an integer : -10                                                                                       

##### -10 is a negative number.

# C# Sharp program to accept the height of a person

## in centimeter and categorize the person according to their height

### C# CODE

##### using System; 

##### public class Exercise7 

##### { 

#####     public static void Main()

##### {

#####     float PerHeight;

#####     Console.Write("\n\n");

#####     Console.Write("Accept the height of a person in centimeter and categorize them:\n");

#####     Console.Write("----------------------------------------------------------------");

#####     Console.Write("\n\n");

#####     Console.Write("Input the height of the person (in centimetres):");

#####     PerHeight = Convert.ToInt32(Console.ReadLine());

#####     if (PerHeight < 150.0)

#####         Console.Write("The person is Dwarf. \n\n");

#####     else if ((PerHeight >= 150.0) && (PerHeight <= 165.0))

#####        Console.Write("The person is  average heighted. \n\n");

#####     else if ((PerHeight >= 165.0) && (PerHeight <= 195.0))

#####         Console.Write("The person is taller. \n\n");

#####     else

#####         Console.Write("Abnormal height.\n\n");

##### }  

##### }

### OUTPUT

Accept the height of a person in centimeter and categorize them:                                             

----------------------------------------------------------------

Input the height of the person (in centimetres):190                                                          

The person is taller.

# Find the largest of three numbers

### C# CODE

##### using System; 

##### public class Exercise8 

##### { 

#####     public static void Main()

##### {

#####     int num1, num2, num3;

#####     Console.Write("\n\n");

#####     Console.Write("Find the largest of three numbers:\n");

#####     Console.Write("------------------------------------");

#####     Console.Write("\n\n");

#####     Console.Write("Input the 1st number :");

#####     num1 = Convert.ToInt32(Console.ReadLine());

#####     Console.Write("Input the  2nd number :");

#####     num2 = Convert.ToInt32(Console.ReadLine());

#####     Console.Write("Input the 3rd  number :");

#####     num3 = Convert.ToInt32(Console.ReadLine());

#####   if (num1 > num2)

#####     {

#####         if (num1 > num3)

#####         {

#####             Console.Write("The 1st Number is the greatest among three. \n\n");

#####         }

#####         else

#####         {

#####             Console.Write("The 3rd Number is the greatest among three. \n\n");

#####         }

#####     }

#####     else if (num2 > num3)

#####         Console.Write("The 2nd Number is the greatest among three \n\n");

#####     else

#####         Console.Write("The 3rd Number is the greatest among three \n\n");

##### }

##### }

Output:

Find the largest of three numbers:                                                                           

------------------------------------                                                                                                 

Input the 1st number :20                                                                                     

Input the  2nd number :25                                                                                    

Input the 3rd  number :15                                                                                    

The 2nd Number is the greatest among three

# Calculate profit and loss

### C# CODE

##### using System; 

##### public class Exercise17 

##### { 

#####     public static void Main() 

##### { 

#####     int cprice,sprice, plamt;

#####            Console.Write("\n\n");

#####            Console.Write("Calculate profit and loss:\n");

#####            Console.Write("----------------------------");

#####            Console.Write("\n\n");

#####      Console.Write("Input Cost Price: "); 

#####      cprice= Convert.ToInt32(Console.ReadLine());

#####      Console.Write("Input Selling Price: "); 

#####      sprice= Convert.ToInt32(Console.ReadLine()); 

#####     if(sprice>cprice)

#####     { 

#####         plamt = sprice-cprice; 

#####         Console.Write("\nYou can booked your profit amount : {0}\n", plamt); 

#####     } 

#####     else if(cprice>sprice) 

#####     { 

#####         plamt = cprice-sprice; 

#####         Console.Write("\nYou got a loss of amount : {0}\n", plamt); 

#####     } 

#####     else  

#####     { 

#####         Console.Write("\nYou are running in no profit no loss condition.\n"); 

#####     } 

##### }

##### } 

Output:

Calculate profit and loss:                                                                                   

----------------------------                                             

Input Cost Price: 1000                                                                                       

Input Selling Price: 1200                                                                                    

You can booked your profit amount : 200