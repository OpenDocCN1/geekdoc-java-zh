![](Images/cover00119.jpeg)

C AND JAVA

CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

[Print your name](#part0003.xhtml__Toc57990414)

[Print a block](#part0004.xhtml__Toc57990415)

[Compute the perimeter](#part0005.xhtml__Toc57990416)

[C programming: Area and circumference of a circle](#part0006.xhtml__Toc57990417)

[Display multiple variables](#part0007.xhtml__Toc57990418)

[Convert specified days](#part0008.xhtml__Toc57990419)

[Calculate the sum](#part0009.xhtml__Toc57990420)

[Calculate the product](#part0010.xhtml__Toc57990421)

[Find the maximum](#part0011.xhtml__Toc57990422)

[Calculate the distance](#part0012.xhtml__Toc57990423)

[Convert a given integer](#part0013.xhtml__Toc57990424)

[sum of all odd values](#part0014.xhtml__Toc57990425)

[Print the average of all positive values](#part0015.xhtml__Toc57990426)

[Check the password](#part0016.xhtml__Toc57990427)

[Read an integer](#part0018.xhtml__Toc57990428)

[Compute the simple interest](#part0019.xhtml__Toc57990429)

[Print the powers of 2 table](#part0020.xhtml__Toc57990430)

[Read five subject marks (0-100)](#part0021.xhtml__Toc57990431)

[Converts a temperature](#part0022.xhtml__Toc57990432)

[Calculates the volume](#part0023.xhtml__Toc57990433)

[Converts kilometers per hour](#part0024.xhtml__Toc57990434)

[Calculate the total hours and minutes](#part0025.xhtml__Toc57990435)

[JAVA CODING EXERCISES](#part0027.xhtml__Toc57990436)

[Print hello](#part0027.xhtml__Toc57990437)

[Print the sum](#part0028.xhtml__Toc57990438)

[Divide two numbers](#part0029.xhtml__Toc57990439)

[Print the result](#part0030.xhtml__Toc57990440)

[Print multiplication table](#part0031.xhtml__Toc57990441)

[Find the area](#part0032.xhtml__Toc57990442)

[Swap two variables](#part0033.xhtml__Toc57990443)

[Print a face](#part0034.xhtml__Toc57990444)

[Fahrenheit to Celsius degree](#part0035.xhtml__Toc57990445)

[Inches to meters](#part0036.xhtml__Toc57990446)

[Adds all the digits](#part0037.xhtml__Toc57990447)

[Print the number of years and days](#part0038.xhtml__Toc57990448)

[Compute (BMI)](#part0039.xhtml__Toc57990449)

[Calculate speed in meters](#part0040.xhtml__Toc57990450)

[Divide the two specified integers](#part0041.xhtml__Toc57990451)

[Multiply two specified integers](#part0042.xhtml__Toc57990452)

[Print the sum](#part0043.xhtml__Toc57990453)

[Find the greatest of three numbers](#part0044.xhtml__Toc57990454)

[Display the multiplication table](#part0045.xhtml__Toc57990455)

[Display the pattern](#part0046.xhtml__Toc57990456)

[Print a pattern like a pyramid](#part0047.xhtml__Toc57990457)

[Display the number rhombus structure](#part0048.xhtml__Toc57990458)

C

CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

# Print your name

## date of birth, and mobile number

### C CODE

##### #include <stdio.h>

##### int main() 

#####   {

#####      printf("Name   : JJ Tam\n");

#####      printf("DOB    : July 14, 1975\n");

#####      printf("Mobile : 99-9999999999\n");

#####      return(0);

#####   }

### OUTPUT

Name   : JJ Tam

DOB    : July 14, 1975

Mobile : 99-9999999999

# Print a block

## F and big C

### BLOCK OF ‘F’

### C CODE

##### #include <stdio.h>

##### int main()

##### {

##### printf("######\n");

##### printf("#\n");

##### printf("#\n");

##### printf("#####\n");

##### printf("#\n");

##### printf("#\n");

##### printf("#\n");

##### return(0);

##### }

### OUTPUT

######

#

#

#####

#

#

#

### BLOCK OF BIG C

### C CODE

##### #include <stdio.h>

##### int main()

##### {

#####    printf("    ######\n");

#####    printf("  ##      ##\n");

#####    printf(" #\n");

#####    printf(" #\n");

#####    printf(" #\n");

#####    printf(" #\n");

#####    printf(" #\n");

#####    printf("  ##      ##\n");

#####    printf("    ######\n");

##### return(0);

##### }

### OUTPUT

   ######

  ##      ##

#

#

#

#

#

  ##      ##

    ######

# Compute the perimeter

## and area of a rectangle

### C CODE

##### #include <stdio.h>

##### /* height and width of a rectangle in inches */

##### int width;         

##### int height;        

##### int area;          

##### int perimeter;     

##### int main() {

##### height = 7;

##### width = 5;

#####     perimeter = 2*(height + width);

##### printf("Perimeter of the rectangle = %d inches\n", perimeter);

##### area = height * width;

##### printf("Area of the rectangle = %d square inches\n", area);

##### return(0);

##### }

### OUTPUT

Perimeter of the rectangle = 24 inches                                

Area of the rectangle = 35 square inches

# C programming: Area and circumference of a circle

### C CODE

##### #include <stdio.h>

##### int main() {

#####    int radius;

#####    float area, perimeter;   

#####    radius = 6;

#####    perimeter = 2*3.14*radius;

#####    printf("Perimeter of the Circle = %f inches\n", perimeter);

##### area = 3.14*radius*radius;

##### printf("Area of the Circle = %f square inches\n", area);

##### return(0);

##### }

### OUTPUT

Perimeter of the Circle = 37.680000 inches                            

Area of the Circle = 113.040001 square inches

# Display multiple variables

C program to display following variables.
a+ c, x + c,dx + x, ((int) dx) + ax, a + x, s + b, ax + b, s + c, ax + c, ax + ux
Variable declaration :
int a = 125, b = 12345;
long ax = 1234567890;
short s = 4043;
float x = 2.13459;
double dx = 1.1415927;
char c = 'W';
unsigned long ux = 2541567890;

### C CODE

##### #include <stdio.h>

##### int main()

##### {

#####     int a = 125, b = 12345;

#####     long ax = 1234567890;

#####     short s = 4043;

#####     float x = 2.13459;

#####     double dx = 1.1415927;

#####     char c = 'W';

#####     unsigned long ux = 2541567890;

#####     printf("a + c =  %d\n", a + c);

#####     printf("x + c = %f\n", x + c);

#####     printf("dx + x = %f\n", dx + x);

#####     printf("((int) dx) + ax =  %ld\n", ((int) dx) + ax);

#####     printf("a + x = %f\n", a + x);

#####     printf("s + b =  %d\n", s + b);

#####     printf("ax + b = %ld\n", ax + b);

#####     printf("s + c =  %hd\n", s + c);

#####     printf("ax + c = %ld\n", ax + c);

#####     printf("ax + ux = %lu\n", ax + ux);

#####     return 0;

##### }

### OUTPUT

a + c =  212                                                          

x + c = 89.134590                                                     

dx + x = 3.276183                                                     

((int) dx) + ax =  1234567891                                         

a + x = 127.134590                                                    

s + b =  16388                                                        

ax + b = 1234580235                                                   

s + c =  4130                                                         

ax + c = 1234567977                                                   

ax + ux = 3776135780

# Convert specified days

## into years, weeks and days

### C CODE

##### #include <stdio.h>

##### int main()

##### {

#####     int days, years, weeks;

#####     days = 1329;

#####     // Converts days to years, weeks and days

#####     years = days/365;

#####     weeks = (days % 365)/7;

#####     days = days- ((years*365) + (weeks*7));

#####     printf("Years: %d\n", years);

#####     printf("Weeks: %d\n", weeks);

#####     printf("Days: %d \n", days);

#####     return 0;

##### }

### OUTPUT

Years: 3                                                              

Weeks: 33                                                             

Days: 3

# Calculate the sum

## of the two integers

### C CODE

##### #include <stdio.h>

##### int main()

#####    {

##### int x, y, sum;

#####     printf("\nInput the first integer: ");

#####     scanf("%d", &x);

#####     printf("\nInput the second integer: ");

#####     scanf("%d", &y);

#####     sum = x + y;

#####     printf("\nSum of the above two integers = %d\n", sum);

#####     return 0;

##### }

### OUTPUT

Input the first integer: 25                                           

Input the second integer: 38                                          

Sum of the above two integers = 63

# Calculate the product

## of the two integers

### C CODE

##### #include <stdio.h>

##### int main()

#####    {

##### int x, y, result;

#####     printf("\nInput the first integer: ");

#####     scanf("%d", &x);

#####     printf("\nInput the second integer: ");

#####     scanf("%d", &y);

#####     result = x * y;

##### printf("Product of the above two integers = %d\n", result);

##### }

### OUTPUT

Input the first integer: 25                                           

Input the second integer: 15                                          

Product of the above two integers = 375

# Find the maximum

## From three integers

### C CODE

##### #include <stdio.h>

##### #include <stdlib.h>

##### int main()

##### {

#####     int x, y, z, result, max;

#####     printf("\nInput the first integer: ");

#####     scanf("%d", &x);

#####     printf("\nInput the second integer: ");

#####     scanf("%d", &y);

#####     printf("\nInput the third integer: ");

#####     scanf("%d", &z);

#####     result=(x+y+abs(x-y))/2;

#####     max=(result+z+abs(result-z))/2;

#####     printf("\nMaximum value of three integers: %d", max);

##### printf("\n");

#####     return 0;

##### }

### OUTPUT

Input the first integer: 25                                           

Input the second integer: 35                                          

Input the third integer: 15                                           

Maximum value of three integers: 35

# Calculate the distance

## between the two points

![](Images/image00104.jpeg)

### C CODE

##### #include <stdio.h>

##### #include <math.h>

##### int main() {

##### float x1, y1, x2, y2, gdistance;

##### printf("Input x1: ");

##### scanf("%f", &x1);

##### printf("Input y1: ");

##### scanf("%f", &y1);

#####               printf("Input x2: ");

##### scanf("%f", &x2);

##### printf("Input y2: ");

##### scanf("%f", &y2);

##### gdistance = ((x2-x1)*(x2-x1))+((y2-y1)*(y2-y1));

##### printf("Distance between the said points: %.4f", sqrt(gdistance));

##### printf("\n");

##### return 0;

##### }

### OUTPUT

Input x1: 25                                                          

Input y1: 15                                                          

Input x2: 35                                                          

Input y2: 10                                                          

Distance between the said points: 11.1803 

# Convert a given integer

## to hours, minutes and seconds

### C CODE

##### #include <stdio.h>

##### int main() {

##### int sec, h, m, s;

##### printf("Input seconds: ");

##### scanf("%d", &sec);

##### h = (sec/3600);

##### m = (sec -(3600*h))/60;

##### s = (sec -(3600*h)-(m*60));

##### printf("H:M:S - %d:%d:%d\n",h,m,s);

##### return 0;

##### }

### OUTPUT

Input seconds: 25300                                                  

H:M:S - 7:1:40

# sum of all odd values

## C program that read 5 numbers and sum of all odd values

### C CODE

##### #include <stdio.h>

##### int main() {

##### int j, numbers[5],total=0;

##### printf("\nInput the first number: ");

#####     scanf("%d", &numbers[0]);

#####     printf("\nInput the second number: ");

#####     scanf("%d", &numbers[1]);

#####     printf("\nInput the third number: ");

#####     scanf("%d", &numbers[2]);

##### printf("\nInput the fourth number: ");

#####     scanf("%d", &numbers[3]);

#####     printf("\nInput the fifth number: ");

#####     scanf("%d", &numbers[4]);

##### for(j = 0; j < 5; j++) {

##### if((numbers[j]%2) != 0)

##### {

#####    total += numbers[j];

##### }

#####     }

#####  printf("\nSum of all odd values: %d", total);

##### printf("\n");

##### return 0;

##### }

### OUTPUT

Input the first number: 11                                            

Input the second number: 17                                           

Input the third number: 13                                            

Input the fourth number: 12                                           

Input the fifth number: 5                                             

Sum of all odd values: 46

# Print the average of all positive values

## In given integers

### C CODE

##### #include <stdio.h>

##### int main() {

##### float numbers[5],total=0, avg;

##### int j, pctr=0;

##### printf("\nInput the first number: ");

#####     scanf("%f", &numbers[0]);

#####     printf("\nInput the second number: ");

#####     scanf("%f", &numbers[1]);

#####     printf("\nInput the third number: ");

#####     scanf("%f", &numbers[2]);

##### printf("\nInput the fourth number: ");

#####     scanf("%f", &numbers[3]);

#####     printf("\nInput the fifth number: ");

#####     scanf("%f", &numbers[4]);

##### for(j = 0; j < 5; j++) {

##### if(numbers[j] > 0)

##### {

##### pctr++;

##### total += numbers[j];

##### }

#####     }

#####     avg = total/pctr;

##### printf("\nNumber of positive numbers: %d", pctr);

##### printf("\nAverage value of the said positive numbers: %.2f", avg);

##### printf("\n");

##### return 0;

##### }

### OUTPUT

Input the first number: 5                                             

Input the second number: 8                                            

Input the third number: 10                                            

Input the fourth number: -5                                           

Input the fifth number: 25                                            

Number of positive numbers: 4                                         

Average value of the said positive numbers: 12.00

# Check the password

## until it is correct

### For wrong password print "Incorrect password"

### C CODE

##### #include <stdio.h>

##### int main() {

##### int pass, x=10;

##### while (x!=0)

##### {

##### printf("\nInput the password: ");

##### scanf("%d",&pass);

##### if (pass==1234)

##### {

##### printf("Correct password");

##### x=0;

#####     }

#####     else

#####     {

#####        printf("Wrong password, try another");      

##### }

##### printf("\n");

#####    }

##### return 0;

##### }

### OUTPUT

Input the password: 1234                                                                            

Correct password

## Calculate the value

## of a specified series of 50 numbers

#### C program to calculate the value of S where S = 1 + 1/2 + 1/3 + … + 1/50

### C CODE

##### #include <stdio.h>

##### int main() {

##### float S = 0;

##### int i;

##### for(i=1; i<=50; i++)

##### {

##### S += (float)1/i;

#####     }

#####     printf("Value of S: %.2f\n", S);

##### return 0;

##### }

### OUTPUT

Value of S: 4.50

# Read an integer

## and find all its divisor

![](Images/image00105.jpeg)

### C CODE

#include <stdio.h>

int main() {

int x, i;

printf("\nInput an integer: ");

scanf("%d", &x);

printf("All the divisor of %d are: ", x);

for(i = 1; i <= x; i++) {

if((x%i) == 0){

printf("\n%d", i);

printf("\n");

}

}

return 0;

}

### OUTPUT

Input an integer: 45                                                  

All the divisor of 45 are:                                            

1                                                                     

3                                                                     

5                                                                     

9                                                                     

15                                                                    

45

# Compute the simple interest

![](Images/image00106.jpeg)

### C CODE

##### #include<stdio.h>

##### int main()

##### {

##### int p,r,t,int_amt;

##### printf("Input principle, Rate of interest & time to find simple interest: \n");

##### scanf("%d%d%d",&p,&r,&t);

##### int_amt=(p*r*t)/100;

##### printf("Simple interest = %d",int_amt);

##### return 0;

##### }

### OUTPUT

Input Data: p = 10000, r = 10% , t = 12 year

Input principle, Rate of interest & time to find simple interest:

Simple interest = 12000

# Print the powers of 2 table

## for the power 0 to 10

### C CODE

##### #include<stdio.h>

#####   int main() {

#####     long int p;

#####     int n;

#####     double q;

#####     printf("\n=======================================");

#####     printf("\n n    2 to power n      2 to power -n");

#####     printf("\n=======================================");

#####     p = 1;

#####     for (n = 0; n < 11; ++n) {

#####       if (n == 0)

#####         p = 1;

#####       else

#####         p = p * 2;

#####       q = 1.0 / (double) p;

#####       printf("\n%2d   %8d     %20.12lf", n, p, q);

#####     }

#####     printf("\n======================================");

#####     return 0;

#####   }

### OUTPUT

![](Images/image00107.jpeg)

# Read five subject marks (0-100)

## of a student and calculate the average

### C CODE

##### #include <stdio.h>

##### int main () {

#####   float marks, tot_marks = 0;

#####   int i = 0, subject = 0;

#####   printf("Input five subject marks(0-100):\n");

#####   while (subject != 5)

#####   {

#####     scanf("%f", &marks);

#####     if (marks < 0 || marks > 100)

#####     {

#####       printf("Not a valid marks\n");

#####     }

#####     else

#####     {

#####       tot_marks += marks;

#####       subject++;

#####     }

#####   }

#####   printf("Average marks = %.2f\n", tot_marks/5);

##### }

### OUTPUT

Input five subject marks(0-100):

75

84

56

98

68

Average marks = 76.20

# Converts a temperature

## from Centigrade to Fahrenheit

#### C = (5/9) * (F - 32)

### C CODE

##### #include <stdio.h>

##### float temp_f;     /* degrees fahrenheit */

##### float temp_c;     /* degrees centigrade */

##### char line_text[50];        /* a line of input */

##### int main() {

##### printf("Input a temperature (in Centigrade): ");

##### fgets(line_text, sizeof(line_text), stdin);

##### sscanf(line_text, "%f", &temp_c);

##### temp_f = ((9.0 / 5.0) * temp_c) + 32.0;

##### printf("%f degrees Fahrenheit.\n", temp_f);

##### return(0);

##### }

### OUTPUT

Input a temperature (in Centigrade): 45                                                                      

113.000000 degrees Fahrenheit.

# Calculates the volume

## of a sphere

V = 4/3*π*r3

### C CODE

##### #include <stdio.h>

##### float myradius;          /* radius of the sphere */

##### float myvolume;          /* volume of the sphere (to be computed) */

##### char line_text[50];      /* a line from the keyboard */

##### /* the value of pi to 50 places, from wikipedia */

##### const float PI = 3.14159265358979323846264338327950288419716939937510;

##### int main() {

##### printf("Input the radius of the sphere : ");

##### fgets(line_text, sizeof(line_text), stdin);

##### sscanf(line_text, "%f", &myradius);

##### myvolume = (4.0 / 3.0) * PI * (myradius * myradius * myradius);  /* volumn=(4/3) * pi * r^3*/

##### printf("The volume of sphere is %f.\n", myvolume);

##### return(0);

##### }

### OUTPUT

Input the radius of the sphere : 2.56                                                                        

The volume of sphere is 70.276237.

# Converts kilometers per hour

## to miles per hour

![](Images/image00108.jpeg)

### C CODE

##### #include <stdio.h>

##### float kmph;              /* kilometers per hour */

##### float miph;              /* miles per hour (to be computed) */

##### char  line_text[50];      /* a line from the keyboard */

##### int main()

##### {

##### printf("Input kilometers per hour: ");

##### fgets(line_text, sizeof(line_text), stdin);

##### sscanf(line_text, "%f", &kmph);

##### miph = (kmph * 0.6213712);

##### printf("%f miles per hour\n", miph);

##### return(0);

##### }

### OUTPUT

Input kilometers per hour: 15                                                                                

9.320568 miles per hour

# Calculate the total hours and minutes

![](Images/image00109.jpeg)

### C CODE

##### #include <stdio.h>

##### int tot_mins;  /* given number of minutes */

##### int hrs;          /* number of hours (to be computed) */

##### int mins;        /* number of minutes (to be computed) */

##### const int MINaHOUR = 60;      /* number of minutes in an hour */

##### char line_text[50];      /* line of input from keyboard */

##### int main() {

##### printf("Input minutes: ");

##### fgets(line_text, sizeof(line_text), stdin);

##### sscanf(line_text, "%d", &tot_mins);

##### hrs = (tot_mins / MINaHOUR);

##### mins = (tot_mins % MINaHOUR);

##### printf("%d Hours, %d Minutes.\n", hrs, mins);

##### return(0);

##### }

### OUTPUT

Input minutes: 546                                                                                           

9 Hours, 6 Minutes.

JAVA

CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

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

![](Images/image00110.jpeg)

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

![](Images/image00111.jpeg)

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

![](Images/image00112.jpeg)

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

![](Images/image00113.jpeg)

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

![](Images/image00114.jpeg)

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

![](Images/image00115.jpeg)

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

![](Images/image00116.jpeg)

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

![](Images/image00117.jpeg)

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

![](Images/image00118.jpeg)

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