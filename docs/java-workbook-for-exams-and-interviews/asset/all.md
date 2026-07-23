![](Images/cover00073.jpeg)

JAVA

WORKBOOK

FOR

EXAMS AND INTERVIEWS

FAST AND EASY WAY TO

LEARN CODING BASICS

JP TAM

[Java program to find sum of all digits](#part0002.xhtml__Toc68690837)

[Java program to calculate compound interest](#part0003.xhtml__Toc68690838)

[Java program to find largest number](#part0004.xhtml__Toc68690839)

[Java program to run an application](#part0005.xhtml__Toc68690840)

[Java program to print Fibonacci Series](#part0006.xhtml__Toc68690841)

[Using for loop to print numbers from 1 to N](#part0007.xhtml__Toc68690842)

[Java Data Type Exercises](#part0008.xhtml__Toc68690843)

[Fahrenheit to Celsius degree](#part0008.xhtml__Toc68690844)

[Java Data Type Exercises: Inches to meters](#part0009.xhtml__Toc68690845)

[Adds all the digits in the integer](#part0010.xhtml__Toc68690846)

[Takes the user to input the minutes](#part0011.xhtml__Toc68690847)

[Reads a number and display the square](#part0012.xhtml__Toc68690848)

[Java Conditional Statement : Exercises](#part0013.xhtml__Toc68690849)

[Check the number is negative, zero, or positive](#part0013.xhtml__Toc68690850)

[Input 5 numbers find their sum and average](#part0014.xhtml__Toc68690851)

[Display n terms of natural numbers and their sum](#part0015.xhtml__Toc68690852)

[Displays the weekday between 1 and 7](#part0016.xhtml__Toc68690853)

[Using while loop to print numbers from 1 to N](#part0017.xhtml__Toc68690854)

[Addition of one dimensional and two dimensional arrays](#part0018.xhtml__Toc68690855)

[Java program to convert Decimal to Binary](#part0019.xhtml__Toc68690856)

[Java program to read a file line by line](#part0020.xhtml__Toc68690857)

# Java program to find sum of all digits

#### Provided a number and we have to use java program to find sum of all its digits.

Example 1:

    Input:

    Number: 852

    Output:

    Sum of all digits: 15

Example 2:

    Input:

    Number: 256868

    Output:

    Sum of all digits: 35

#### PROGRAM

##### import java.util.Scanner;

##### public class AddDigits

##### {

#####     public static void main(String args[])

#####     {

#####  // initializing and declaring the objects.

#####         int num, rem=0, sum=0, temp;

#####         Scanner scan = new Scanner(System.in);

#####         // enter number here.

#####         System.out.print("Enter the Number : ");

#####         num = scan.nextInt();

#####         // temp is to store number.

#####         temp = num;

#####         while(num>0)

#####         {

#####             rem = num%10;

#####             sum = sum+rem;

#####             num = num/10;

#####         }

#####         System.out.print("Sum of Digits of " +temp+ " is : " +sum);       

#####     }

##### }

Output

First run:

Enter the Number : 582

Sum of Digits of 582 is : 15

Second run:

Enter the Number : 256868

Sum of Digits of 256868 is : 35

# Java program to calculate compound interest

#### Given the principle, rate and time, and using java program we have to find compound interest.

Example:

    Enter Principal : 5000

    Enter Rate : 5

    Enter Time : 3

    Amount : 5788.125000000001

    Compound Interest : 788.1250000000009

#### PROGRAM

##### import java.util.Scanner;

##### public class CompoundInterest

##### {

##### public static void main(String args[])

##### {

##### // declare and initialize here.

##### double A=0,Pri,Rate,Time,t=1,CI;

##### // create object.

##### Scanner S=new Scanner(System.in);

##### // enter principal, rate, time here

##### System.out.print("Enter Principal : ");

##### Pri=S.nextFloat();

##### System.out.print("Enter Rate : ");

##### Rate=S.nextFloat();

##### System.out.print("Enter Time : ");

##### Time=S.nextFloat();

##### Rate=(1 + Rate/100);

##### for(int i=0;i<Time;i++)

##### t*=Rate;

##### A=Pri*t;

##### System.out.print("Amount : " +A);

##### CI=A-Pri;

##### System.out.print("\nCompound Interest : " +CI);

##### }

##### }

Output

First run:

Enter Principal : 5000

Enter Rate : 5

Enter Time : 3

Amount : 5788.125000000001

Compound Interest : 788.1250000000009

Second run:

Enter Principal : 10000

Enter Rate : 20

Enter Time : 5

Amount : 24883.199999999997

Compound Interest : 14883.199999999997

# Java program to find largest number 

#### The program reads from the keyboard (three integer numbers), and selects the largest number.

#### PROGRAM

##### //Java program to find largest number among three numbers.

##### import java.util.*;

##### class LargestFrom3

##### {

#####     public static void main(String []s)

#####     {

#####         int a,b,c,largest;

#####         //Scanner class to read value

#####         Scanner sc=new Scanner(System.in);

#####         System.out.print("Enter first  number:");

#####         a=sc.nextInt();

#####         System.out.print("Enter second number:");

#####         b=sc.nextInt();

#####         System.out.print("Enter third  number:");

#####         c=sc.nextInt();

#####         if ( a>b && a>c )

#####             largest=a;

#####         else if ( b>a && b>c )

#####             largest=b;

#####         else

#####             largest=c;

#####         System.out.println("Largest Number is : "+largest);

#####     }

##### }

Output

 Complie  :javac LargestFrom3.java

 Run:java LargestFrom3

 Output

    Enter first  number:45

    Enter second number:56

    Enter third  number:67

    Largest Number is : 67

# Java program to run an application

#### Using Java program this program can open (run) applications (Notepad, Calculator). We use instance of Runtime.getRuntime() and method exec() to open / run application.

#### PROGRAM

##### //Java program to run an application.

##### import java.util.*;

##### class OpenNotepad

##### {

#####   public static void main(String[] args)

#####   {

#####       Runtime app=Runtime.getRuntime();

#####       try

#####       {

#####           //open notepad

#####           app.exec("notepad");

#####           //open calculator

#####           app.exec("calc");

#####       }

#####       catch (Exception Ex)

#####       {

#####           System.out.println("Error: " + Ex.toString());

#####       }

#####   }

##### }

#### OUTPUT

  Notepad and Calculator will be opened.

# Java program to print Fibonacci Series

#### Fibonacci Series is a series where the term is the sum of two preceding terms.

#### PROGRAM

##### /*Java program to print Fibonacci Series.*/

##### import  java.util.Scanner;

##### public  class  Fabonacci {

#####     public  static  void  main(String[] args) {

#####         int  SeriesNum ;

#####         Scanner sc=new  Scanner(System.in);

#####         System.out.print("Enter the length of fibonacci series : ");

#####         SeriesNum=sc.nextInt();

#####              int[] num = new  int[SeriesNum];

#####              num[0] = 0;

#####              num[1] = 1;

#####             //number should be sum of last two numbers of Series    

#####              for(int  i=2; i < SeriesNum; i++){

#####                  num[i] = num[i-1] + num[i-2];

#####              }

#####              System.out.println("fibonacci series : ");

#####              for(int  i=0; i< SeriesNum; i++){

#####                      System.out.print(num[i] + " ");

#####              }

#####     }

##### }

#### OUTPUT

  Enter the length of fibonacci series : 10

    fibonacci series :

    0 1 1 2 3 5 8 13 21 34

# Using for loop to print numbers from 1 to N

#### PROGRAM

##### import java.util.Scanner;

##### public class Print_1_To_N_UsingFor

##### {

##### public static void main(String[] args)

##### {

##### //create object of scanner class

##### Scanner scanner = new Scanner(System.in);

##### // enter the value of " n ".

##### System.out.print("Enter the value n : ");

##### // read the value.

##### int n = scanner.nextInt();

##### System.out.println("Numbers are : " );

##### for(int i=1; i<=n; i++)

##### {

##### System.out.println(i);

##### }

##### }

##### }

Output

Enter the value n : 15

Numbers are :

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

11

12

13

14

15

# Java Data Type Exercises

# Fahrenheit to Celsius degree

![](Images/image00066.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise1 {

#####     public static void main(String[] Strings) {

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input a degree in Fahrenheit: ");

#####         double fahrenheit = input.nextDouble();

#####         double  celsius =(( 5 *(fahrenheit - 32.0)) / 9.0);

#####         System.out.println(fahrenheit + " degree Fahrenheit is equal to " + celsius + " in Celsius");

#####     }

##### }

### OUTPUT

Input a degree in Fahrenheit: 212

212.0 degree Fahrenheit is equal to 100.0 in Celsius

# Java Data Type Exercises: Inches to meters

Write a Java program that takes an inch value and converts it to meters.

INCHES TO METERS

1 INCH = 0.025400 METERS

2 INCH = 0.050800 METERS

3 INCH = 0.076200 METERS

4 INCH = 0.101600 METERS

5 INCH = 0.127000 METERS

6 INCH =  0.152400 METERS

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise2 {

#####     public static void main(String[] Strings) {

#####         Scanner input = new Scanner(System.in);

#####         System.out.print("Input a value for inch: ");

#####         double inch = input.nextDouble();

#####         double meters = inch * 0.0254;

#####         System.out.println(inch + " inch is " + meters + " meters");

#####     }

##### }

### OUTPUT

Input a value for inch: 1000                                                                                 

1000.0 inch is 25.4 meters

# Adds all the digits in the integer

Create a Java program that takes an integer between 0 and 1000 and adds all of its digits.

![](Images/image00067.jpeg)

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

Input an integer between 0 and 1000: 565                                                                     

The sum of all digits in 565 is 16

# Takes the user to input the minutes

## and print the number of years and days

### for the minutes

#### Write a Java program to convert minutes into a number of years and days.

![](Images/image00068.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise4 {

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

Input the number of minutes: 3456789                                                                         

3456789 minutes is approximately 6 years and 210 days

# Reads a number and display the square

## cube, and fourth power

#### Create a Java program that reads a number and displays the square, cube, and fourth power of that number.

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise8 {

#####     public static void main(String[] args)

#####     {

#####         Scanner in = new Scanner(System.in);

#####         System.out.print("Input the side length value: ");

#####         double val = in.nextDouble();

#####         System.out.printf("Square: %12.2f\n", val * val);

#####         System.out.printf("Cube: %14.2f\n", val * val * val);

#####         System.out.printf("Fourth power: %6.2f\n", Math.pow(val, 4));

#####     }

##### }

### OUTPUT

Input the side length value: 15

Square:       225.00

Cube:        3375.00

Fourth power: 50625.00

# Java Conditional Statement : Exercises

# Check the number is negative, zero, or positive

![](Images/image00069.jpeg)

### JAVA CODE

import java.util.Scanner;

public class Exercise27 {

public static void main(String[] args)

    {

        Scanner in = new Scanner(System.in);

        System.out.print("Input a number: ");

        int n = in.nextInt();

        if (n > 0)

        {

            System.out.println("Number is positive");

        }

        else if (n < 0)

        {

            System.out.println("Number is negative");

        }

        else

        {

            System.out.println("Number is zero");

        }

    }

}

### OUTPUT

Input a number: 7                                             

Number is positive

# Input 5 numbers find their sum and average

![](Images/image00070.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise12 {

#####   public static void main(String[] args)

##### {      

#####     int i,n=0,s=0;

##### double avg;

##### {

#####         System.out.println("Input the 5 numbers : "); 

##### }

##### for (i=0;i<5;i++)

##### {

#####     Scanner in = new Scanner(System.in);

#####     n = in.nextInt();

#####  s +=n;

##### }

##### avg=s/5;

##### System.out.println("The sum of 5 no is : " +s+"\nThe Average is : " +avg);

##### }

##### }

### OUTPUT

Input the 5 numbers :                                                                                        

1                                                                                                    

2                                                                                                    

3                                                                                                    

4                                                                                                    

5                                                                                                    

The sum of 5 no is : 15                                                                                      

The Average is : 3.0

# Display n terms of natural numbers and their sum

#### Input number: 7

![](Images/image00071.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise11 {

#####   public static void main(String[] args)

##### {

#####    int i, n, sum=0;

#####    {

#####    Scanner in = new Scanner(System.in); 

#####         System.out.print("Input number: "); 

#####          n = in.nextInt();

##### }

#####   System.out.println("The first n natural numbers are : "+n);

##### for(i=1;i<=n;i++)

#####    {

#####      System.out.println(i);

#####      sum+=i;

#####    }

##### System.out.println("The Sum of Natural Number upto "+n+ " terms : " +sum);

##### }

##### }

### OUTPUT

Input number: 7                                                                                              

The first n natural numbers are : 7                                                                          

1                                                                                                    

2                                                                                                    

3                                                                                                    

4                                                                                                    

5                                                                                                    

6                                                                                                    

7                                                                                                    

The Sum of Natural Number upto n terms : 28

# Displays the weekday between 1 and 7

![](Images/image00072.jpeg)

### JAVA CODE

##### import java.util.Scanner;

##### public class Exercise5 {

#####   public static void main(String[] args)

#####     {

#####         Scanner in = new Scanner(System.in);

#####         System.out.print("Input number: ");

#####         int day = in.nextInt();

#####         System.out.println(getDayName(day));

#####     }

#####     // Get the name for the Week

#####     public static String getDayName(int day) {

#####         String dayName = "";

#####         switch (day) {

#####             case 1: dayName = "Monday"; break;

#####             case 2: dayName = "Tuesday"; break;

#####             case 3: dayName = "Wednesday"; break;

#####             case 4: dayName = "Thursday"; break;

#####             case 5: dayName = "Friday"; break;

#####             case 6: dayName = "Saturday"; break;

#####             case 7: dayName = "Sunday"; break;

#####             default:dayName = "Invalid day range";

#####         }

#####         return dayName;

#####     }

##### }

### OUTPUT

Input number: 3                                                                                              

Wednesday

# Using while loop to print numbers from 1 to N

#### PROGRAM

##### import java.util.Scanner;

##### public class Print_1_To_N_UsingWhile

##### {

##### public static void main(String[] args)

##### {

##### //loop counter initialisation

##### int i =1;

##### //create object of scanner class

##### Scanner Sc = new Scanner(System.in);

##### // enter the value of " n "

##### System.out.print("Enter the value n : ");

##### // read the value.

##### int n = Sc.nextInt();

##### System.out.println("Numbers are : ");

##### while(i<=n)

##### {

##### System.out.println(i);

##### i++;

##### }

##### }

##### }

Output

Enter the value n : 15

Numbers are :

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

11

12

13

14

15

# Addition of one dimensional and two dimensional arrays

## IN JAVA PROGRAM

#### There are 2 programs: two one-dimensional arrays added, and two two-dimensional arrays added

### 1)  Addition of two one dimensional arrays in java

##### class AddTwoArrayClass{

##### public static void main(String[] args){

##### // Declaration and initialization of  array

##### int a[] = {1,2,3,4,5};

##### int b[] = {6,7,8,9,10};

##### // Instantiation of third array to store results

##### int c[] = new int[5];

##### for(int i=0; i<5; ++i){

##### // add two array and result store in third array

##### c[i] = a[i] + b[i];

##### //Display results

##### System.out.println("Enter sum of "+i +"index" +" " + c[i]);

##### }

##### }

##### }

. Output

Enter sum of 0index 7

Enter sum of 1index 9

Enter sum of 2index 11

Enter sum of 3index 13

Enter sum of 4index 15

### 2)  Addition of two two dimensional arrays in java

##### class AddTwoArrayOf2DClass{

##### public static void main(String[] args){

##### // Declaration and initialization of  2D array

##### int a[][] = {{1,2,3},{4,5,6}};

##### int b[][] = {{7,8,9},{10,11,12}};

##### // Instantiation of third array to store results

##### int c[][] = new int[2][3];

##### for(int i=0; i<2; ++i){

##### for(int j=0; j<3; ++j){

##### // add two array and result store in third array

##### c[i][j] = a[i][j] + b[i][j];

##### System.out.println("Enter sum of "+i + " " + j +"index" +" " + c[i][j]);

##### }

##### }

##### }

##### }

Output

Enter sum of 0 0index 8

Enter sum of 0 1index 10

Enter sum of 0 2index 12

Enter sum of 1 0index 14

Enter sum of 1 1index 16

Enter sum of 1 2index 18

# Java program to convert Decimal to Binary

Given an Integer (Decimal) number, and using java program we have to convert it to Binary.

#### PROGRAM

##### // Scanner class is used for taking input from user

##### import java.util.Scanner;

##### class DecimalToBinaryConversionClass{

##### public static void main(String[] args){

##### // create Scanner class object

##### Scanner sc = new Scanner(System.in);

##### System.out.println("Enter Any Decimal Number :");

##### //Accept input from user

##### int input_decimal_num = sc.nextInt();

##### String binary_string = " ";

##### //Loop continues till input_decimal_num >0

##### while(input_decimal_num > 0){

##### //remainder add to string variable

##### binary_string = input_decimal_num%2 + binary_string;

##### input_decimal_num = input_decimal_num/2;

##### }

##### // Display Final Result

##### System.out.println("Conversion of decimal to binary is : " + binary_string);

##### }

##### }

Output

Enter Any Decimal Number :

30

Conversion of decimal to binary is : 11110

# Java program to read a file line by line

#### Given a file, and using java program we have to read its contents line by line.

#### We use a file called "B.txt" for this program that is located at the "F:\" drive, thus the file path is "F:\B.txt," and the file content is:

    This is line 1

    This is line 2

    This is line 3

    This is line 4

#### PROGRAM

##### import java.io.FileInputStream;

##### import java.io.IOException;

##### import java.util.Scanner;

##### public class ReadLineByLine

##### {

##### public static void main(String[] args)

##### {

#####         // create object of scanner class.

##### Scanner Sc=new Scanner(System.in);

##### // enter file name.

##### System.out.print("Enter the file name:");

##### String sfilename=Sc.next();

##### Scanner Sc1= null;

##### FileInputStream fis=null;

##### try

##### {

#####     FileInputStream FI=new FileInputStream(sfilename);

#####     Sc1=new Scanner(FI);

#####     // this will read data till the end of data.

#####     while(Sc1.hasNext())

#####     {

#####  String data=Sc1.nextLine();

#####  // print the data.

#####  System.out.print("The file data is : " +data);

#####     }

##### }

##### catch(IOException e)

##### {

##### System.out.println(e);

##### }

##### }

Output

Enter the file name: F:/B.txt

This is line 1

This is line 2

This is line 3

This is line 4