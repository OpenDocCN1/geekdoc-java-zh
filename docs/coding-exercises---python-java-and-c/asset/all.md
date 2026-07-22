![](Images/cover00118.jpeg)

CODING EXERCISES

PYTHON, JAVA AND C#

CODING FOR BEGINNERS

JJ TAM

[Python Basic – Exercises](#part0003.xhtml__Toc62371804)

[Get Python version](#part0003.xhtml__Toc62371805)

[Display current date and time](#part0004.xhtml__Toc62371806)

[Print the calendar](#part0005.xhtml__Toc62371807)

[Computes the value of n+nn+nnn](#part0006.xhtml__Toc62371808)

[Calculate number of days](#part0007.xhtml__Toc62371809)

[volume of a sphere in Python](#part0008.xhtml__Toc62371810)

[Compute the area of Triangle](#part0009.xhtml__Toc62371811)

[Compute the GCD](#part0010.xhtml__Toc62371812)

[CALCULATE THE LCM](#part0011.xhtml__Toc62371813)

[Convert feet and inches to centimeters](#part0012.xhtml__Toc62371814)

[Convert time – seconds](#part0013.xhtml__Toc62371815)

[Convert seconds to day](#part0014.xhtml__Toc62371816)

[Calculate BMS](#part0015.xhtml__Toc62371817)

[Sort three integers](#part0016.xhtml__Toc62371818)

[Get system time](#part0017.xhtml__Toc62371819)

[Check a number](#part0018.xhtml__Toc62371820)

[Python code to Remove first item](#part0019.xhtml__Toc62371821)

[Filter positive numbers](#part0020.xhtml__Toc62371822)

[Count the number 4](#part0021.xhtml__Toc62371823)

[Find a number even or odd](#part0022.xhtml__Toc62371824)

[Difference between the two lists](#part0023.xhtml__Toc62371825)

[Generate all permutations](#part0024.xhtml__Toc62371826)

[Find the second smallest](#part0025.xhtml__Toc62371827)

[Get unique values](#part0026.xhtml__Toc62371828)

[Get the frequency of the elements](#part0027.xhtml__Toc62371829)

[Generate all sublists](#part0028.xhtml__Toc62371830)

[Find common items](#part0029.xhtml__Toc62371831)

[Create a list](#part0030.xhtml__Toc62371832)

[Remove consecutive duplicates](#part0031.xhtml__Toc62371833)

[Flatten a nested](#part0032.xhtml__Toc62371834)

[JAVA CODING EXERCISES](#part0034.xhtml__Toc62371835)

[Print hello](#part0034.xhtml__Toc62371836)

[Print the sum](#part0035.xhtml__Toc62371837)

[Divide two numbers](#part0036.xhtml__Toc62371838)

[Print the result](#part0037.xhtml__Toc62371839)

[Print multiplication table](#part0038.xhtml__Toc62371840)

[Find the area](#part0039.xhtml__Toc62371841)

[Swap two variables](#part0040.xhtml__Toc62371842)

[Print a face](#part0041.xhtml__Toc62371843)

[Fahrenheit to Celsius degree](#part0042.xhtml__Toc62371844)

[Inches to meters](#part0043.xhtml__Toc62371845)

[Adds all the digits](#part0044.xhtml__Toc62371846)

[Print the number of years and days](#part0045.xhtml__Toc62371847)

[Compute (BMI)](#part0046.xhtml__Toc62371848)

[Find the greatest of three numbers](#part0047.xhtml__Toc62371849)

[Display the multiplication table](#part0048.xhtml__Toc62371850)

[Display the pattern](#part0049.xhtml__Toc62371851)

[Print a pattern like a pyramid](#part0050.xhtml__Toc62371852)

[Display the number rhombus structure](#part0051.xhtml__Toc62371853)

[C# SHARP CODING EXERCISES](#part0053.xhtml__Toc62371854)

[Print hello and your name](#part0053.xhtml__Toc62371855)

[Print the result of the specified operations](#part0054.xhtml__Toc62371856)

[Program to swap two numbers](#part0055.xhtml__Toc62371857)

[Print the output of multiplication](#part0056.xhtml__Toc62371858)

[Adding, subtracting, multiplying and dividing](#part0057.xhtml__Toc62371859)

[Print the average of four numbers](#part0058.xhtml__Toc62371860)

[Program to convert Temperature](#part0059.xhtml__Toc62371861)

[Compute the sum](#part0060.xhtml__Toc62371862)

[Compute sum](#part0061.xhtml__Toc62371863)

[C# program to check](#part0062.xhtml__Toc62371864)

[C# Sharp program to check two given integers](#part0063.xhtml__Toc62371865)

[C# Sharp program to check a given positive number](#part0064.xhtml__Toc62371866)

[check whether a given string starts with 'C#' or not](#part0065.xhtml__Toc62371867)

[C# Sharp program to check the largest number](#part0066.xhtml__Toc62371868)

[Program to check which number is nearest to the value 100](#part0067.xhtml__Toc62371869)

[Program to convert the last 3 characters](#part0068.xhtml__Toc62371870)

 PYTHON CODING EXERCISES

CODING FOR BEGINNERS

JJ TAM

# Python Basic – Exercises

# Get Python version

### CODE

##### import sys

##### print("Python version")

##### print (sys.version)

##### print("Version info.")

##### print (sys.version_info)

#### OUTPUT

Python version

3.6.6 (default, Jun 28 2018, 04:42:43)

[GCC 5.4.0 20160609]

Version info.

sys.version_info(major=3, minor=6, micro=6, releaselevel='final', serial=0)

# Display current date and time

### PYTHON CODE

##### import datetime

##### now = datetime.datetime.now()

##### print ("Current date and time : ")

##### print (now.strftime("%Y-%m-%d %H:%M:%S"))

#### OUTPUT

Current date and time :

2020-10-22 10:35:31

# Print the calendar

### PYTHON CODE

import calendar

y = int(input("Input the year : "))

m = int(input("Input the month : "))

print(calendar.month(y, m))

#### OUTPUT

Input the year : 2020

Input the month : 10

    October 2020

Mo Tu We Th Fr Sa Su

          1  2  3  4

5  6  7  8  9 10 11

12 13 14 15 16 17 18

19 20 21 22 23 24 25

26 27 28 29 30 31

# Computes the value of n+nn+nnn

### PYTHON CODE

a = int(input("Input an integer : "))

n1 = int( "%s" % a )

n2 = int( "%s%s" % (a,a) )

n3 = int( "%s%s%s" % (a,a,a) )

print (n1+n2+n3)

#### OUTPUT

Input an integer : 6

738

# Calculate number of days

### PROGRAM

##### from datetime import date

##### f_date = date(2014, 7, 2)

##### l_date = date(2015, 7, 11)

##### delta = l_date - f_date

##### print(delta.days)

#### OUTPUT

374

# volume of a sphere in Python

### PROGRAM

##### pi = 3.1415926535897931

##### r= 6.0

##### V= 4.0/3.0*pi* r**3

##### print('The volume of the sphere is: ',V)

#### OUTPUT

The volume of the sphere is:  904.7786842338603

# Compute the area of Triangle

### PROGRAM

##### b = int(input("Input the base : "))

##### h = int(input("Input the height : "))

##### area = b*h/2

##### print("area = ", area)

#### OUTPUT

Input the base : 20 

Input the height : 40

area =  400.0  

# Compute the GCD

### PROGRAM

##### def gcd(x, y):

#####     gcd = 1

#####     if x % y == 0:

#####         return y

#####     for k in range(int(y / 2), 0, -1):

#####         if x % k == 0 and y % k == 0:

#####             gcd = k

#####             break 

#####     return gcd

##### print(gcd(12, 17))

##### print(gcd(4, 6))

#### OUTPUT

1

2

# CALCULATE THE LCM

#### PROGRAM

##### def lcm(x, y):

#####    if x > y:

#####        z = x

#####    else:

#####        z = y

#####    while(True):

#####        if((z % x == 0) and (z % y == 0)):

#####            lcm = z

#####            break

#####        z += 1

#####    return lcm

##### print(lcm(4, 6))

##### print(lcm(15, 17))

OUTPUT

12

255

# Convert feet and inches to centimeters

### PROGRAM

##### print("Input your height: ")

##### h_ft = int(input("Feet: "))

##### h_inch = int(input("Inches: "))

##### h_inch += h_ft * 12

##### h_cm = round(h_inch * 2.54, 1)

##### print("Your height is : %d cm." % h_cm)

#### OUTPUT

Input your height:

Feet:  5

Inches:  3

Your height is : 160 cm.

# Convert time – seconds

### PYTHON CODE

##### days = int(input("Input days: ")) * 3600 * 24

##### hours = int(input("Input hours: ")) * 3600

##### minutes = int(input("Input minutes: ")) * 60

##### seconds = int(input("Input seconds: "))

##### time = days + hours + minutes + seconds

##### print("The  amounts of seconds", time)

#### Output:

Input days:  4

Input hours:  5

Input minutes:  20

Input seconds:  10

The  amounts of seconds 364810

# Convert seconds to day

### PROGRAM

##### time = float(input("Input time in seconds: "))

##### day = time // (24 * 3600)

##### time = time % (24 * 3600)

##### hour = time // 3600

##### time %= 3600

##### minutes = time // 60

##### time %= 60

##### seconds = time

##### print("d:h:m:s-> %d:%d:%d:%d" % (day, hour, minutes, seconds))

#### OUTPUT

Input time in seconds: 1234565                                                                               

d:h:m:s-> 14:6:56:5

# Calculate BMS

### PROGRAM

##### height = float(input("Input your height in meters: "))

##### weight = float(input("Input your weight in kilogram: "))

##### print("Your body mass index is: ", round(weight / (height * height), 2))

#### OUTPUT

Input your height in meters: 6.2

Input your weight in kilogram: 72

Your body mass index is:  1.87

# Sort three integers

### PROGRAM

##### x = int(input("Input first number: "))

##### y = int(input("Input second number: "))

##### z = int(input("Input third number: "))

##### a1 = min(x, y, z)

##### a3 = max(x, y, z)

##### a2 = (x + y + z) - a1 - a3

##### print("Numbers in sorted order: ", a1, a2, a3)

#### OUTPUT

Input first number: 2                                                                                        

Input second number: 4                                                                                       

Input third number: 5                                                                                        

Numbers in sorted order:  2 4 5

# Get system time

### PROGRAM

##### import time

##### print()

##### print(time.ctime())

##### print()

#### OUTPUT

Thu Oct 22 14:59:27 2020

# Check a number

### PYTHON CODE

##### num = float(input("Input a number: "))

##### if num > 0:

#####    print("It is positive number")

##### elif num == 0:

#####    print("It is Zero")

##### else:

#####    print("It is a negative number")

#### OUTPUT

Input a number: 200

It is positive number

# Python code to Remove first item 

### PROGRAM

##### color = ["Red", "Black", "Green", "White", "Orange"]

##### print("\nOriginal Color: ",color)

##### del color[0]

##### print("After removing the first color: ",color)

##### print()

#### OUTPUT

Original Color:  ['Red', 'Black', 'Green', 'White', 'Orange']

After removing the first color:  ['Black', 'Green', 'White', 'Orange']

# Filter positive numbers

### PYTHON CODE

##### nums = [34, 1, 0, -23]

##### print("Original numbers in the list: ",nums)

##### new_nums = list(filter(lambda x: x >0, nums))

##### print("Positive numbers in the list: ",new_nums)

#### OUTPUT

Original numbers in the list:  [34, 1, 0, -23]                                                               

Positive numbers in the list:  [34, 1]

# Count the number 4

## in a given list

### SAMPLE PROGRAM

##### def list_count_4(nums):

#####   count = 0 

#####   for num in nums:

#####     if num == 4:

#####       count = count + 1

#####   return count

##### print(list_count_4([1, 4, 6, 7, 4]))

##### print(list_count_4([1, 4, 6, 4, 7, 4]))

#### OUTPUT

2                                                                                                            

3

# Find a number even or odd

### SAMPLE PROGRAM

##### num = int(input("Enter a number: "))

##### mod = num % 2

##### if mod > 0:

#####     print("This is an odd number.")

##### else:

#####     print("This is an even number.")

#### OUTPUT

Enter a number: 5                                                                                            

This is an odd number.

# Difference between the two lists

### PYTHON CODE

##### list1 = [1, 3, 5, 7, 9]

##### list2=[1, 2, 4, 6, 7, 8]

##### diff_list1_list2 = list(set(list1) - set(list2))

##### diff_list2_list1 = list(set(list2) - set(list1))

##### total_diff = diff_list1_list2 + diff_list2_list1

##### print(total_diff)

### OUTPUT

[9, 3, 5, 8, 2, 4, 6]

# Generate all permutations

## of a list

### PYTHON CODE

##### import itertools

##### print(list(itertools.permutations([1,2,3])))

#### OUTPUT

[(1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2), (3, 2, 1)]

# Find the second smallest

## number in a list

### PYTHON PROGRAM

##### def second_smallest(numbers):

#####   if (len(numbers)<2):

#####     return

#####   if ((len(numbers)==2)  and (numbers[0] == numbers[1]) ):

#####     return

#####   dup_items = set()

#####   uniq_items = []

#####   for x in numbers:

#####     if x not in dup_items:

#####       uniq_items.append(x)

#####       dup_items.add(x)

#####   uniq_items.sort()   

#####   return  uniq_items[1]  

##### print(second_smallest([1, 2, -8, -2, 0, -2]))

##### print(second_smallest([1, 1, 0, 0, 2, -2, -2]))

##### print(second_smallest([1, 1, 1, 0, 0, 0, 2, -2, -2]))

##### print(second_smallest([2,2]))

##### print(second_smallest([2]))

#### OUTPUT

-2

0

0

None

None

# Get unique values

## from a list

### Python Code

##### my_list = [10, 20, 30, 40, 20, 50, 60, 40]

##### print("Original List : ",my_list)

##### my_set = set(my_list)

##### my_new_list = list(my_set)

##### print("List of unique numbers : ",my_new_list)

#### OUTPUT

Original List :  [10, 20, 30, 40, 20, 50, 60, 40]                                                            

List of unique numbers :  [40, 10, 50, 20, 60, 30] 

# Get the frequency of the elements

### Python Code

##### import collections

##### my_list = [10,10,10,10,20,20,20,20,40,40,50,50,30]

##### print("Original List : ",my_list)

##### ctr = collections.Counter(my_list)

##### print("Frequency of the elements in the List : ",ctr)

#### OUTPUT

Original List :  [10, 10, 10, 10, 20, 20, 20, 20, 40, 40, 50, 50, 30]                                        

Frequency of the elements in the List :  Counter({10: 4, 20: 4, 40: 2, 50: 2, 30: 1})

# Generate all sublists

## of a list in Python

### Python Code

##### from itertools import combinations

##### def sub_lists(my_list):

##### subs = []

##### for i in range(0, len(my_list)+1):

#####   temp = [list(x) for x in combinations(my_list, i)]

#####   if len(temp)>0:

#####     subs.extend(temp)

##### return subs

##### l1 = [10, 20, 30, 40]

##### l2 = ['X', 'Y', 'Z']

##### print("Original list:")

##### print(l1)

##### print("S")

##### print(sub_lists(l1))

##### print("Sublists of the said list:")

##### print(sub_lists(l1))

##### print("\nOriginal list:")

##### print(l2)

##### print("Sublists of the said list:")

##### print(sub_lists(l2))

#### OUTPUT

Original list:

[10, 20, 30, 40]

S

[[], [10], [20], [30], [40], [10, 20], [10, 30], [10, 40], [20, 30], [20, 40], [30, 40], [10, 20, 30], [10, 20, 40], [10, 30, 40], [20, 30, 40], [10, 20, 30, 40]]

Sublists of the said list:

[[], [10], [20], [30], [40], [10, 20], [10, 30], [10, 40], [20, 30], [20, 40], [30, 40], [10, 20, 30], [10, 20, 40], [10, 30, 40], [20, 30, 40], [10, 20, 30, 40]]

Original list:

['X', 'Y', 'Z']

Sublists of the said list:

[[], ['X'], ['Y'], ['Z'], ['X', 'Y'], ['X', 'Z'], ['Y', 'Z'], ['X', 'Y', 'Z']]

# Find common items

## from two lists

### Python Code

##### color1 = "Red", "Green", "Orange", "White"

##### color2 = "Black", "Green", "White", "Pink"

##### print(set(color1) & set(color2))

#### OUTPUT

'Green', 'White'}

# Create a list

## with infinite elements

### Python Code

##### import itertools

##### c = itertools.count()

##### print(next(c))

##### print(next(c))

##### print(next(c))

##### print(next(c))

##### print(next(c))

#### OUTPUT

0                                                                                                            

1                                                                                                            

2                                                                                                            

3                                                                                                            

4

# Remove consecutive duplicates

## of a given list

### Python Code

##### from itertools import groupby

##### def compress(l_nums):

#####     return [key for key, group in groupby(l_nums)]

##### n_list = [0, 0, 1, 2, 3, 4, 4, 5, 6, 6, 6, 7, 8, 9, 4, 4 ]

##### print("Original list:")

##### print(n_list)

##### print("\nAfter removing consecutive duplicates:")

##### print(compress(n_list))

#### OUTPUT

Original list:

[0, 0, 1, 2, 3, 4, 4, 5, 6, 6, 6, 7, 8, 9, 4, 4]

After removing consecutive duplicates:

[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 4]

# Flatten a nested

## list structure

### Python Code

##### def flatten_list(n_list):

#####     result_list = []

#####     if not n_list: return result_list

#####     stack = [list(n_list)]

#####     while stack:

#####         c_num = stack.pop()

#####         next = c_num.pop()

#####         if c_num: stack.append(c_num)

#####         if isinstance(next, list):

#####             if next: stack.append(list(next))

#####         else: result_list.append(next)

#####     result_list.reverse()

#####     return result_list

##### n_list = [0, 10, [20, 30], 40, 50, [60, 70, 80], [90, 100, 110, 120]]

##### print("Original list:")

##### print(n_list)

##### print("\nFlatten list:")

##### print(flatten_list(n_list))

#### OUTPUT

Original list:

[0, 10, [20, 30], 40, 50, [60, 70, 80], [90, 100, 110, 120]]

Flatten list:

[0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120]

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

![](Images/image00111.jpeg)

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

![](Images/image00112.jpeg)

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

![](Images/image00113.jpeg)

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