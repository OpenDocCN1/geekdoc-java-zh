![](cover.jpeg)

JAVA

CODING PRACTICE EXERCISES

CODING FOR BEGINNERS

JJ TAM

[Java String Exercises](#text00002.html__Toc68382835)

[Get the character at the given index within the String](#text00002.html__Toc68382836)

[Test if a given string contains the specified sequence of char values](#text00003.html__Toc68382837)

[Compare a given string to the specified string buffer](#text00004.html__Toc68382838)

[Check whether a given string ends with the contents of another string](#text00005.html__Toc68382839)

[Get the contents of a given string as a byte array](#text00006.html__Toc68382840)

[Java Array Exercises](#text00007.html__Toc68382841)

[Sum values of an array](#text00007.html__Toc68382842)

[Calculate the average value of array elements](#text00008.html__Toc68382843)

[Test if an array contains a specific value](#text00009.html__Toc68382844)

[Remove a specific element from an array](#text00010.html__Toc68382845)

[Insert an element into an array](#text00011.html__Toc68382846)

[JAVA BASIC EXERCISES](#text00012.html__Toc68382847)

[Swap two variables](#text00012.html__Toc68382848)

[Print a face](#text00013.html__Toc68382849)

[Fahrenheit to Celsius degree](#text00014.html__Toc68382850)

[Inches to meters](#text00015.html__Toc68382851)

[Adds all the digits](#text00016.html__Toc68382852)

[Print the number of years and days](#text00017.html__Toc68382853)

[Compute (BMI)](#text00018.html__Toc68382854)

[Print the sum](#text00019.html__Toc68382855)

[Find the greatest of three numbers](#text00020.html__Toc68382856)

[Display the multiplication table](#text00021.html__Toc68382857)

[Display the pattern](#text00022.html__Toc68382858)

[Print a pattern like a pyramid](#text00023.html__Toc68382859)

[Print the sum](#text00024.html__Toc68382860)

[Divide two numbers](#text00025.html__Toc68382861)

# Java String Exercises

# Get the character at the given index within the String

![](OEBPS/Image00000.jpg)

### JAVA CODE

##### public class Exercise1 {

#####    public static void main(String[] args)

#####     {

#####         String str = "Java Exercises!";

#####         System.out.println("Original String = " + str);

#####         // Get the character at positions 0 and 10.

#####         int index1 = str.charAt(0);

#####         int index2 = str.charAt(10);

#####         // Print out the results.

#####         System.out.println("The character at position 0 is " +

#####             (char)index1);

#####         System.out.println("The character at position 10 is " +

#####             (char)index2);

#####     }

##### }

### OUTPUT

Original String = Java Exercises!                                                                            

The character at position 0 is J                                                                             

The character at position 10 is i

# Test if a given string contains the specified sequence of char values

![](OEBPS/Image00001.jpg)

### JAVA CODE

##### public class Exercise8 {

#####     public static void main(String[] args)

#####     {

#####         String str1 = "PHP Exercises and Python Exercises";

#####         String str2 = "and";

#####         System.out.println("Original String: " + str1);

#####         System.out.println("Specified sequence of char values: " + str2);

#####         System.out.println(str1.contains(str2));

#####     }

##### }

### OUTPUT

Original String: PHP Exercises and Python Exercises                                                          

Specified sequence of char values: and                                                                       

true

# Compare a given string to the specified string buffer

### JAVA CODE

##### public class Exercise10 {

##### public static void main(String[] args) {

#####     String str1 = "example.com", str2 = "Example.com";

#####     StringBuffer strbuf = new StringBuffer(str1);

#####     System.out.println("Comparing "+str1+" and "+strbuf+": " + str1.contentEquals(strbuf));

#####     System.out.println("Comparing "+str2+" and "+strbuf+": " + str2.contentEquals(strbuf));

#####       }

##### }

### OUTPUT

Comparing example.com and example.com: true                                                                  

Comparing Example.com and example.com: false

# Check whether a given string ends with the contents of another string

![](OEBPS/Image00002.jpg)

### JAVA CODE

##### public class Exercise12 {

#####     public static void main(String[] args)

#####     {

#####         String str1 = "Python Exercises";

#####         String str2 = "Python Exercise";

#####         // The String to check the above two Strings to see

#####         // if they end with this value (se).

#####         String end_str = "se";

#####         // Check first two Strings end with end_str

#####         boolean ends1 = str1.endsWith(end_str);

#####         boolean ends2 = str2.endsWith(end_str);

#####         // Display the results of the endsWith calls.

#####         System.out.println("\"" + str1 + "\" ends with " +

#####             "\"" + end_str + "\"? " + ends1);

#####         System.out.println("\"" + str2 + "\" ends with " +

#####             "\"" + end_str + "\"? " + ends2);

#####     }

##### }

### OUTPUT

"Python Exercises" ends with "se"? false                                                                     

"Python Exercise" ends with "se"? true

# Get the contents of a given string as a byte array

### JAVA CODE

##### import java.util.Calendar;

##### public class Exercise16 {

#####   public static void main(String[] args)

#####     {

#####         String str = "This is a sample String.";

#####         // Copy the contents of the String to a byte array.

#####         byte[] byte_arr = str.getBytes();

#####         // Create a new String using the contents of the byte array.

#####         String new_str = new String(byte_arr);

#####         // Display the contents of the byte array.

#####         System.out.println("\nThe new String equals " +

#####             new_str + "\n");

#####     }

##### }

### OUTPUT

The new String equals This is a sample String.

# Java Array Exercises

# Sum values of an array

![](OEBPS/Image00003.jpg)

### JAVA CODE

##### public class Exercise2 {

##### public static void main(String[] args) {     

##### int my_array[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};

##### int sum = 0;

##### for (int i : my_array)

#####     sum += i;

##### System.out.println("The sum is " + sum);

##### }

##### }

### OUTPUT

The sum is 55

# Calculate the average value of array elements

![](OEBPS/Image00004.jpg)

### JAVA CODE

##### public class Exercise4 {

##### public static void main(String[] args) {  

#####        int[] numbers = new int[]{20, 30, 25, 35, -16, 60, -100};

#####        //calculate sum of all array elements

#####        int sum = 0;

#####        for(int i=0; i < numbers.length ; i++)

#####         sum = sum + numbers[i];

#####        //calculate average value

#####         double average = sum / numbers.length;

#####         System.out.println("Average value of the array elements is : " + average);

#####    }

##### }

### OUTPUT

Average value of the array elements is : 7.0

# Test if an array contains a specific value

![](OEBPS/Image00005.jpg)

### JAVA CODE

##### public class Exercise5 {

#####   public static boolean contains(int[] arr, int item) {

#####       for (int n : arr) {

#####          if (item == n) {

#####             return true;

#####          }

#####       }

#####       return false;

#####    }

#####    public static void main(String[] args) {

#####           int[] my_array1 = {

#####             1789, 2035, 1899, 1456, 2013,

#####             1458, 2458, 1254, 1472, 2365,

#####             1456, 2265, 1457, 2456};

#####       System.out.println(contains(my_array1, 2013));

#####       System.out.println(contains(my_array1, 2015));

#####    }

##### }

### OUTPUT

true                                                                                                      

false

# Remove a specific element from an array

![](OEBPS/Image00006.jpg)

### JAVA CODE

##### import java.util.Arrays;

##### public class Exercise7 {

##### public static void main(String[] args) {

#####    int[] my_array = {25, 14, 56, 15, 36, 56, 77, 18, 29, 49};

#####    System.out.println("Original Array : "+Arrays.toString(my_array));    

#####   // Remove the second element (index->1, value->14) of the array

#####    int removeIndex = 1;

#####    for(int i = removeIndex; i < my_array.length -1; i++){

#####         my_array[i] = my_array[i + 1];

#####       }

##### // We cannot alter the size of an array , after the removal, the last and second last element in the array will exist twice

#####     System.out.println("After removing the second element: "+Arrays.toString(my_array));

##### }

##### }

### OUTPUT

Original Array : [25, 14, 56, 15, 36, 56, 77, 18, 29, 49]                                                    

After removing the second element: [25, 56, 15, 36, 56, 77, 18, 29, 49, 49]

# Insert an element into an array

![](OEBPS/Image00007.jpg)

### JAVA CODE

##### import java.util.Arrays;

##### public class Exercise9 {

##### public static void main(String[] args) {

#####    int[] my_array = {25, 14, 56, 15, 36, 56, 77, 18, 29, 49};

#####     // Insert an element in 3rd position of the array (index->2, value->5)

#####    int Index_position = 2;

#####    int newValue    = 5;

#####   System.out.println("Original Array : "+Arrays.toString(my_array));    

#####   for(int i=my_array.length-1; i > Index_position; i--){

#####     my_array[i] = my_array[i-1];

#####    }

#####    my_array[Index_position] = newValue;

#####    System.out.println("New Array: "+Arrays.toString(my_array));

##### }

##### }

### OUTPUT

Original Array : [25, 14, 56, 15, 36, 56, 77, 18, 29, 49]                                                    

New Array: [25, 14, 5, 56, 15, 36, 56, 77, 18, 29]

# JAVA BASIC EXERCISES

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

![](OEBPS/Image00008.jpg)

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

![](OEBPS/Image00009.jpg)

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

![](OEBPS/Image00010.jpg)

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

# Print the sum

## Difference, product, average, distance, maximum and minimum

![](OEBPS/Image00011.jpg)

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

![](OEBPS/Image00012.jpg)

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

![](OEBPS/Image00013.jpg)

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

![](OEBPS/Image00014.jpg)

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