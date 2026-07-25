![](images/00001.jpeg)

the answers of the assignments

Java Quizmaster
for Beginners

teacher's guide

Sar Maroof

 Copyright © 2017 Sar Maroof

All rights reserved.

ISBN: 978-1-975-78205-4

Table of contents

[About the teacher’s guide](#part0000_split_003.html__Toc491697144)[.............................................................................................4](#part0000_split_003.html__Toc491697144)

[Chapter 1—Data Types And Variables](#part0000_split_004.html__Toc491697145)[....................................................................5](#part0000_split_004.html__Toc491697145)

[Chapter 2—Operators](#part0000_split_005.html__Toc491697146)[.............................................................................................................8](#part0000_split_005.html__Toc491697146)

[Chapter 3—Conditional Statements](#part0000_split_006.html__Toc491697147)[........................................................................15](#part0000_split_006.html__Toc491697147)

[Chapter 4—Iteration (Loop) Statements](#part0000_split_007.html__Toc491697148)[...........................................................25](#part0000_split_007.html__Toc491697148)

[Chapter 5—Classes, Objects And Constructors](#part0000_split_009.html__Toc491697149)[...........................................32](#part0000_split_009.html__Toc491697149)

[Chapter 6—Methods](#part0000_split_010.html__Toc491697150)[................................................................................................................39](#part0000_split_010.html__Toc491697150)

[Chapter 7—Strings And Stringbuffers](#part0000_split_011.html__Toc491697151)[...............................................................46](#part0000_split_011.html__Toc491697151)

[Chapter 8—Packages & Access Modifiers](#part0000_split_012.html__Toc491697152)[.........................................................53](#part0000_split_012.html__Toc491697152)

[Chapter 9—Array And Arraylist](#part0000_split_013.html__Toc491697153)[...............................................................................57](#part0000_split_013.html__Toc491697153)

[Chapter 10—Static Members](#part0000_split_015.html__Toc491697154)[...........................................................................................66](#part0000_split_015.html__Toc491697154)

[Chapter 11—Inheritance](#part0000_split_016.html__Toc491697155)[.....................................................................................................71](#part0000_split_016.html__Toc491697155)

[Chapter 12—Final Classes And The Final Keyword](#part0000_split_016.html__Toc491697156)[.................................80](#part0000_split_016.html__Toc491697156)

[Chapter 13—Abstract Classes](#part0000_split_017.html__Toc491697157)[......................................................................................83](#part0000_split_017.html__Toc491697157)

[Chapter 14—Interfaces](#part0000_split_018.html__Toc491697158)[......................................................................................................88](#part0000_split_018.html__Toc491697158)

[Chatper 15—Casting](#part0000_split_019.html__Toc491697159)[..............................................................................................................92](#part0000_split_019.html__Toc491697159)

[Chapter 16—Nested Classes](#part0000_split_020.html__Toc491697160)[...........................................................................................96](#part0000_split_020.html__Toc491697160)

[Chapter 17—Exceptions](#part0000_split_021.html__Toc491697161)[....................................................................................................101](#part0000_split_021.html__Toc491697161)

About the teacher’s guide

In this manual you will find all the answers of the questions and the chapter assignments. The book Java quizmaster for beginners is intended to learn Java. Students who can master the content of the book will be able to work as a beginner Java programmer.

I recommend beginner programmers to avoid cutting and pasting code, but typing it. By typing the code you will learn from the error messages of the compiler. In every subject, you have specific parts that you need to understand, but also parts that you need to memorize. In math, for example you need to memorize the multiplication table, because that makes complicated calculations easier.

By learning programming you also need to memorize some parts. By typing the code, you start to understand the structure of the program. Many beginners who have the habit of cutting and pasting code don't know how to start writing code from scratch. They often seek other programs to modify it to their wishes.

On [www.sarmaroof.com](http://www.sarmaroof.com/), you can find more information about this book and how to setup the code in Eclipse.

— Sar Maroof

Chapter 1—Data Types and Variables

Quiz 1

public  class Worker

{

 static  boolean  isMarried;

 public  static  void main(String[] args)

  {

 int age = 29;

 long bankAccount = 6552;

 double wage = 110.30;

 char gender = 'm';// female: f, male: m

    System.out.print(age + ", ");

    System.out.print(bankAccount + ", ");

    System.out.print(wage + ", ");

    System.out.print(isMarried + ", ");

    System.out.println(gender);

    // Answer

    System.out.print("Het antwoord: ");

 boolean isForeigner = true;

    System.out.print(isForeigner);

  }

}

1.  A practical variable choice is boolean because the value of the variable isForeigner is either true (foreigner) or false (not foreigner).
2.  To avoid unnecessary work, the variable "isForeigner" should be true by default. The reason is that most of the workers are foreigners.

Quiz 2

public class MyVariable

{

 static  byte  b = 122;

 static  short  s;

 static  float  f1 = 3.50f;

 static  float  f2 = 43.9f;

 static  double  d = 335.35;

 static  char  myChar = 'Q';

 public  static  void main(String[] args)

  {

    System.out.print(b + ", ");

    // System.out.print(myChar + ", ");

    System.out.print(s + ", ");

    System.out.print(f1 + ", ");

    // System.out.print(myChar + ", ");

    System.out.print(f2 + ", ");

    System.out.println(d);

    // Answer

    System.out.print(myChar);

  }

}

Quiz 3

public class MyClass

{

 static  int  i;

 static  double  d;

 static  boolean  b;

 public  static  void main(String[] args)

  {

    System.out.print(i + ", ");

    System.out.print(d + ", ");

    System.out.println(b);

    // Answer

 double myVar = 1344.98;

 char myVar2 = 'g';

 int myVar3 = 766;

    System.out.print("The answer: ");

    System.out.print(myVar + ", ");

    System.out.print(myVar2 + ", ");

    System.out.print(myVar3);

  }

}

1.  The value of 1344.98 is a floating point type, it should be double or float.
2.  The value of the "g" is a character type, it should be char.
3.  The value of 766 is an integer type, it should be short, int or long.

Quiz 4

public class MyClass

{

 static  int  i1 = 7;

 static  int  i2 = 12;

 public  static  void main(String[] args)

  {

 i1 = 9;

 i2 = 8;

 i1 = i1 - 3;

 i2 = i2 + i1;

    System.out.print(i1 + ", ");

    System.out.print(i2 + " ");

  }

}

3\. The statement "i1 = 9" is under the previous initial value of i1, and that is why the value i1 = i1 - 3 = 9 - 3 = 6\.

The statement "i2 = 8" is under the previous initial value of i2\. The new value of i2 is 8\.

i2 = i2 + i1 = 8 + 6 = 14\.

Chapter 2—Operators

Quiz 1

public class Calculate

{

 public  static  void main(String[] args)

  {

 int x = 20;

 int y = 5;

 int z = 3;

 double d = 2.2;

 double d2 = 3.7;

    System.out.print(x / y + ", ");

    System.out.print(x * z + ", ");

    System.out.print(x + y - z + ", ");

    System.out.print(x / y + z * 2 + ", ");

    System.out.println(d2 - d);

    // Answer

    System.out.print("The answer is: ");

    System.out.print(x * y / 10 + ", ");

    System.out.print(2 * d2 + 2.5 + ", ");

    System.out.print(z * 3 - 6);

  }

}

The answer is: 10, 9.9, 3

Quiz 2

public class MyClass

{

 public  static  void main(String[] args)

  {

    System.out.print(21 % 7 + ", ");

    System.out.print(12 % 5 + ", ");

    System.out.println(23 % 6);

    // Answer

    System.out.print("The answer is: ");

    System.out.print(44 % 10 + ", ");

    System.out.print(7 % 2 + ", ");

    System.out.print(30 % 3);

  }

}

The answer is: 4, 1, 0

Quiz 3

public class MyClass

{

 public  static  void main(String[] args)

  {

 int x = 4;

 int y = 6;

    x--;

    y++;

    // Answer

    System.out.print("The answer is: ");

    x++;

    System.out.print(x + ", " + y);

    // x++;

  }

}

1.  The value of x is incremented by one after it is written to the standard output. The result remains the same.

The answer: 3, 7

2.  The value of x is incremented by one before its value is written to the standard output. This will change the result.

The answer is: 4, 7

Quiz 4

public class MyClass

{

 public  static  void main(String[] args)

  {

 int x = 15;

 int y = 8;

 int z = 3;

 if (x == z)

    {

      System.out.print("N");

    }

 if (x >= y)

    {

      System.out.print("O");

      System.out.print("Z");

    }

 if (x <= z)

    {

      System.out.print("P");

    }

 if (z > y)

    {

      System.out.print("Q");

    }

 if (y != z)

    {

      System.out.print("R");

    }

  }

}

By assigning the value 15 to the variable x, the statement if(x >= y) returns true.

The statement if(x == z) returns false.

The result is that OZR is written to the standard output.

Quiz 5

public class MyClass

{

 public  static  void main(String[] args)

  {

 boolean isDefect = false;

 int x = 1;

 int y = 7;

 int z = 9;

 if (x < y && x > 1)

    {

      System.out.print("N");

    }

 if (z > y || x > y)

    {

      System.out.print("O");

    }

 if (!isDefect)

    {

      System.out.print("P");

    }

  }

}

1.  If isDefect is false then the last statement if( ! isDefect)  returns true, and the program writes also P to the standard output.
2.  If x is equal to 1, the statement if(x < y && x > 1) returns false. In this case x is not greater than one.

The result is that the code writes OP to the standard output.

Quiz 6

public class MyClass

{

 public  static  void main(String[] args)

  {

 boolean isOld = true;

 int x = 5;

 int y = 14;

 int z = 17;

 if (y > x && z > y && (x + 12) >= z)

    {

      System.out.print("P");

    }

 if (x >= 6 || z <= y || z <= 18)

    {

      System.out.print("Q");

    }

 if (!isOld || y > z)

    {

      System.out.print("R");

    }

  }

}

1.  The statement if( ! isOld || y > z) returns false, because the first operand !isOld also returns false. In this case the block is ignored and R is not written to the standard output.
2.  If z is equal to 17, the statement if(y > x && z > y && (x + 12) >= z) returns true. Because the first operand y > x is true, the second operand z > y is true and the third operand (x + 12) >= z also returns true. The block is executed and  P is written to the standard output.

If z is equal to 17, the statement if(x >= 6 || z <= y || z <= 18) returns true, because the operand z <= 18 returns true.

Quiz 7

public class MyClass

{

 public  static  void main(String[] args)

  {

 int i1 = 3;

 int i2 = 5;

 int i3 = 12;

 int i4 = 20;

    i1 += 4;

    i2 *= 3;

    i3 /= 3;

    i4 -= 12;

    // Answer

    System.out.print("The answer is: ");

    i1++;

    i2 -= 3;

    i3 *= 2;

    i4 /= 4;

    System.out.print(i1 + ", ");

    System.out.print(i2 + ", ");

    System.out.print(i3 + ", ");

    System.out.print(i4 + " ");

  }

}

The result is that the code writes the following to the standard output.

The answer is: 8, 12, 8, 2

Quiz 8

public class MyClass

{

 public  static  void main(String[] args)

  {

 int i1 = 22;

 int i2 = 17;

 int i3 = 30;

    i1 %= 6;

    i2 %= 5;

    i3 %= 6;

    // Answer

    System.out.print("The answer is: ");

    i1 %= 3;

    i2 %= 7;

    System.out.print(i1 + " ");

    System.out.print(i2 + " ");

    System.out.print(i3 + " ");

  }

}

The result is that the code writes the following to the standard output.

The answer is: 1 2 0

Quiz 9

public class MyClass

{

 public  static  void main(String[] args)

  {

 int x = 6;

 int x2 = 4;

 int y = (x == 3) ? 24 : 8;

 int z = (x2 == 4) ? 33 : 21;

    System.out.print(y);

    System.out.print(z);

  }

}

The code writes 833 to the standard output.

Chapter 3—Conditional Statements

Quiz 1

public class MyClass

{

 public  static  void main(String[] args)

  {

 int i = 2;

    // Answer

 if (i == 2)

    {

      System.out.print("N");

    }

 if (i > 0)

    {

      System.out.print("X");

      System.out.print("Y");

    }

 if (i > 3)

    {

      System.out.print("Z");

    }

  }

}

Quiz 2

public class MyClass

{

 public  static  void main(String[] args)

  {

 int a = 3;

 int b = 1;

 int x = 0;

 if (a > b)

    {

      x++;

 if (a > x)

      {

        x += 5;

      }

      x -= 4;

    }

 if (b == a)

    {

      x += 2;

 if (x < b)

      {

        x += 3;

      }

    }

    System.out.print(x);

    // Answer

 if (a <= 4)

    {

      System.out.print("G");

    }

  }

}

Quiz 3

public class MyClass

{

 public  static  void main(String[] args)

  {

 char c1 = 'g';

 char c2 = 'h';

 if (c1 == 'k')

    {

      System.out.print('w');

    }

 if (c2 == 'h')

    {

      System.out.print('x');

      System.out.print('p');

    }

 if (c1 != c2)

    {

      System.out.print('y');

    }

    // Answer

 if (c1 == 'd')

    {

      // ignored

    }

 else

    {

      System.out.print('z');

    }

  }

}

Quiz 4

public class MyClass

{

 public  static  void main(String[] args)

  {

 int a = 2;

 int b = 2;

 int x = 5;

    // answer 1

 if (a != b)

    {

      x++;

    }

    // answer 2

 else  if (b >= 1)

    {

      System.out.print("X");

    }

 else  if (b == 2)

    {

      x += 2;

    }

    // wrong answer check out why

    /*

    else if(b >= 1) {

 System.out.print("X");

    }*/

 else

    {

      x += 3;

    }

    System.out.print(x);

  }

}

Quiz 5

public class MyClass

{

 public  static  void main(String[] args)

  {

 int i = 1;

 int i2 = 4;

 int x = 2;

 if (i == (i2 - 3) && i2 > 5)

    {

      x++;

    }

    // answer

 else  if ((i + i2) == 5)

    {

      System.out.print("D");

    }

 else  if (i2 == 4)

    {

      x += 2;

    }

    // wrong answer, check out why

    /*else if((i + i2) == 5)

     {

 System.out.print("D");

     }*/

 else  if (i2 > 3)

    {

      x += 3;

    }

    // wrong answer, check out why

    /*else if((i + i2) == 5)

     {

 System.out.print("D");

     }*/

 else

    {

      x += 4;

    }

    System.out.print(x);

  }

}

Quiz 6

public class MyClass

{

 public  static  void main(String[] args)

  {

 int i1 = 3;

 int i2 = 9;

 int i3 = 12;

 int x = 0;

 if (x > -1)

    {

      x++;

 if (i3 == (i1 + i2))

      {

        x += 4;

 if (i1 < 5)

        {

          x += 2;

          // first possible answer

          System.out.print(x);

        }

 else  if (i2 == 9)

        {

          x++;

        }

 else

        {

          x -= 2;

        }

        // second possible answer

        // system.out.print(x);

        x -= 6;

      }

 if (i3 < 10)

      {

        x += 7;

      }

 else

      {

        x += 5;

      }

    }

    System.out.print(x);

  }

}

Quiz 7

public class MyClass

{

 public  static  void main(String[] args)

  {

 int i = 2;

 int i2 = 5;

 int i3 = 9;

 int x = 3;

 boolean isSlow = true;

 if (isSlow)

    {

      x++;

      // answer

      System.out.print("x" + x + ", ");

 if (i >= 2 && i2 > 7)

      {

        x += 4;

        System.out.print("x" + x + ", ");

 if (i3 == 9)

        {

          x += 5;

          System.out.print("x" + x + ", ");

        }

      }

 else

      {

        x += 6;

        System.out.print("x" + x + ", ");

 if (i3 >= 3)

        {

          x += 7;

        }

        System.out.print("x" + x + ", ");

      }

      x += 3;

    }

    System.out.print("x" + x);

  }

}

Answer

The program writes "x4, x10, x17, x20" to the standard output.

Quiz 8

public class MyClass

{

 public  static  void main(String[] args)

  {

 int x = 8;

 switch (x)

    {

 case 6:

        x += 5;

 case 7:

        x += 3;

 case 8:

        x += 2;

        // answer 2

 break;

 case 9:

        x++;

        // answer 1

 break;

 default:

        x += 4;

    }

    System.out.print(x);

  }

}

Answer

1.  15
2.  10

Quiz 9

public class Year

{

 public  static  void main(String[] args)

  {

 int intMonth = 9;

    String strMonth;

 switch (intMonth)

    {

 case 1:

        strMonth = "JAN ";

 break;

 case 2:

        strMonth = "FEB ";

 break;

 case 3:

        strMonth = "MAR ";

 break;

 case 4:

        strMonth = "APR ";

 break;

 case 5:

        strMonth = "MAY ";

 break;

 case 6:

        strMonth = "JUN ";

 break;

 case 7:

        strMonth = "JUL ";

 break;

 case 8:

        strMonth = "AUG ";

 break;

 case 9:

        strMonth = "SEP ";

 break;

 case 10:

        strMonth = "OCT ";

 break;

 case 11:

        strMonth = "NOV ";

 break;

 case 12:

        strMonth = "DEC ";

 break;

 default:

        strMonth = "INVALID ";

    }

    System.out.println(strMonth);

  }

}

Quiz 10

public class Examen

{

 public  static  void main(String args[])

  {

    // answer 3

 char grade = 'N';

 switch (grade)

    {

 case 'A':

        System.out.print("Excellent! ");

 break;

 case 'B':

        System.out.print("Very good ");

 break;

      // answer 1

 case 'C':

        System.out.print("Good ");

 break;

      // answer 2

 case 'D':

        System.out.print("Fair ");

 break;

 case 'E':

        System.out.print("Try again ");

 break;

 default:

        System.out.print("Invalid ");

    }

  }

}

Chapter 4—Iteration (Loop) Statements

Quiz 1

public class MyLoop

{

 public  static  void main(String[] args)

  {

 int i = 3;

 while (i > 1)

    {

      i--;

      System.out.print(i);

    }

  }

}

1.  21
2.  When i is equal to 1, nothing is written to the standard output because the condition i>1 is false.

when i is equal to 2 the answer is 1.

3.  When i is equal to 5, the answer is 4321.

Quiz 2

public class MyLoop

{

 public  static  void main(String[] args)

  {

 int i = 8;

 while (i > 1)

    {

      i++;

      System.out.print(i);

      // answer

      i -= 5;

    }

  }

}

The statement while(i > 1) returns always true, because i is equal to 8 and each time

the loop is executed the statement i ++; increments the value of i by one.

The value of i remains greater than one forever.

Quiz 3

public class MyLoop

{

 public  static  void main(String[] args)

  {

 int i = 4;

 do

    {

      i += 6;

      System.out.print(i);

    }

 while (i <= 12);

  }

}

The result is 1016.

Quiz 4

public class MyLoop

{

 public  static  void main(String[] args)

  {

 int i = 2;

 do

    {

      i += 3;

 if (i != 4)

      {

        System.out.print("x");

      }

 else

      {

        System.out.print("y");

      }

    }

 while (i != 10);

  }

}

1.  The program loops endlessly, because the statement while(i != 10) always returns false.
2.  The program writes xxx to the standard output.

Quiz 5

public class MyLoop

{

 public  static  void main(String[] args)

  {

    // answer

 for (int i = 1; i < 10; i += 3)

    {

      System.out.print(i);

    }

  }

}

The program writes 147 to the standard output.

Quiz 6

public  class MyLoop

{

 public  static  void main(String[] args)

  {

 int x = 1;

    // answer

 for (int i = 3; i < 13; i += 5)

    {

      x += i;

    }

    x -= 2;

    System.out.print(x);

  }

}

The program writes 10 to the standard output.

Quiz 7

public  class MyLoop

{

 public  static  void main(String[] args)

  {

 char c = 'a';

 char c2 = 'b';

    // answer

 for (int i = 4; i >= 0; i--)

    {

 if (i < 2 || i == 4)

      {

        System.out.print(c2);

      }

 else

      {

        System.out.print(c);

      }

    }

  }

}

The program writes baabb to the standard output.

Quiz 8

public class MyLoop

{

 public  static  void main(String[] args)

  {

 int x = 14;

 int y = 5;

 for (int i = 0; i < 10; i++)

    {

      x += 2;

      y += 5;

 if (x >= 21)

      {

 break;

      }

    }

    System.out.print(y);

  }

}

1.  The program writes 25 to the standard output.
2.  If you remove the break statement from the above program, it writes 55 to the standard output.

Quiz 9

public class LeapYear

{

 public  static  void main(String[] args)

  {

 for (int jaar = 2016; jaar <= 2040; jaar++)

    {

 if ((jaar % 4 == 0))

      {

 continue;

      }

      System.out.print(jaar + " ");

    }

  }

}

If you remove the continue statement, the program writes all the years from 2016 to 2040 to the standard output.

Quiz 10

public class MiniTheater

{

 public  static  void main(String[] args)

  {

 for (int row = 1; row <= 5; row++)

    {

 for (int column = 1; column < 4; column++)

      {

 if (row == 1 || row == 3)

        {

 continue;

        }

        System.out.print(row + "," + column + " ");

      }

    }

  }

}

Quiz 11

public class Theater

{

 public  static  void main(String[] args)

  {

    outer:for (int row = 1; row < 4; row++)

    {

      inner:for (int column = 1; column < 5; column++)

      {

 if (column == 2 && column == 3)

        {

 break inner;

        }

        System.out.print(row + "," + column + " ");

      }

    }

  }

}

The program writes 1,1 1,2 1,3 1,4 2,1 2,2 2,3 2,4 3,1 3,2 3,3 3,4 to the standard output.

Chapter 5—Classes, Objects and Constructors

Quiz 1

public class Employee

{

  String name = "Anna";

 int age = 22;

  String phone;

  String city;

 public  static  void main(String[] args)

  {

Employee em = new Employee();

Employee em2 = new Employee();

Employee employee = new Employee();

    employee.name = "Emma";

    employee.age = 25;

    employee.phone = "00233-786854";

    employee.city = "New York City";

    em.name = "John";

    em.age = 20;

    em.phone = "00383-384833";

    em.city = "London";

    System.out.println("-------- Employees -----------");

    System.out.println("Name:         " + em.name);

    System.out.println("Age:          " + em.age);

    System.out.println("Phone:        " + em.phone);

    System.out.println("City:         " + em.city);

    System.out.println("-------------------");

    System.out.println("Name:         " + employee.name);

    System.out.println("Age:          " + employee.age);

    System.out.println("Phone:        " + employee.phone);

    System.out.println("City:         " + employee.city);

  }

}

If the program is compiled and run, the following is written to the standard output.

-------- Employees -----------

Name:         John

Age:          20

Phone:        00383-384833

City:         London

-------------------

Name:         Emma

Age:          25

Phone:        00233-786854

City:         New York City

Quiz 2

public  class MyClass

{

 int x;

 int y = 7;

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.x = 5;

    mc.y = 8;

MyClass mc2 = new MyClass();

    MyClass mc3 = mc;

    System.out.println(mc.x + ", " + mc2.x + ", " + mc3.y);

    // answer

    System.out.print("The answer is: ");

MyClass myClass = new MyClass();

    myClass = mc3;

    System.out.println(myClass.x + ", " + myClass.y);

  }

}

Quiz 3

public class MyClass

{

 int x = 2;

 int y = 5;

  // no-argument constructor

  MyClass()

  {

    // answer 1

 this(6, 3);

  }

  // one-argument constructor

  MyClass(int x)

  {

 this.y = x;

  }

  // two-arguments constructor

  MyClass(int x, int y)

  {

 this.x = x;

 this.y = y;

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

MyClass mc2 = new MyClass(7);

MyClass mc3 = new MyClass(9, 3);

    System.out.println(mc.y + ", " + mc2.y + ", " + mc3.x);

    // answer 2

MyClass myObject = new MyClass();

    // answer 3

    System.out.print("The answer is: ");

    System.out.print("x:" + myObject.x + ", ");

    System.out.print("y:" + myObject.y);

  }

}

The answer is: x = 6, y = 3

Quiz 4

public class Staff

{

  String name = "Ron";

 double salary = 400.0;

  Staff(String name)

  {

 this(name, 780.0);

  }

Staff(String name, double salary)

  {

 this.name = name;

 this.salary = salary;

  }

 public  static  void main(String[] args)

  {

Staff st = new Staff("Ben");

    System.out.println(st.name + ", " + st.salary);

    // answer 1

Staff staffObject = new Staff("Mary", 2000.55);

    // answer 2

    System.out.print("The answer is: ");

    System.out.print(staffObject.name + ", " + staffObject.salary);

  }

}

The answer is: Mary, 2000.55

Quiz 5

public class MyClass

{

 int x = 3;

 int y = 5;

  // answer 1

 int z;

  MyClass()

  {

 this(4, 6);

  }

  MyClass(int x, int y)

  {

 this.y = y;

  }

  // answer 2

  MyClass(int x, int y, int z)

  {

 this.x = x;

 this.y = y;

 this.z = z;

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

MyClass mc2 = new MyClass(9, 7);

    System.out.println(mc.x + ", " + mc.y + ", " + mc2.x + ", " + mc2.y);

    // answer 3

MyClass mc3 = new MyClass(7, 8, 9);

    // answer 4

    System.out.print("The answer is: ");

    System.out.print(mc3.x + ", " + mc3.y + ", " + mc3.z);

  }

}

The answer is: 7, 8, 9

Assignment chapter 5

// the first method without constructors

public  class Employee

{

  String name;

 double salary = 2400.55;

  String country = "France";

 public  static  void main(String[] args)

  {

Employee employee = new Employee();

Employee employee2 = new Employee();

    employee.name = "Olivia";

    employee.salary = 3100.45;

    employee.country = "Canada";

    employee2.name = "James";

    System.out.println("-------- Employees -----------");

    System.out.println("Name:            " + employee.name);

    System.out.println("Salary:          $ " + employee.salary);

    System.out.println("Country:         " + employee.country);

    System.out.println("-----------------");

    System.out.println("Name:            " + employee2.name);

    System.out.println("Salary:          $ " + employee2.salary);

    System.out.println("Country:         " + employee2.country);

  }

}

// the second method using constructors

public  class Employee

{

  String name;

 double salary;

  String country;

  Employee(String name)

  {

 this.name = name;

 this.salary = 2400.55;

 this.country = "France";

  }

Employee(String name, double salary, String country)

  {

 this.name = name;

 this.salary = salary;

 this.country = country;

  }

 public  static  void main(String[] args)

  {

Employee employee = new Employee("Olivia", 3100.45, "Canada");

Employee employee2 = new Employee("James");

    System.out.println("-------- Employees -----------");

    System.out.println("Name:             " + employee.name);

    System.out.println("Salary:           $ " + employee.salary);

    System.out.println("Country:          " + employee.country);

    System.out.println("-----------------");

    System.out.println("Name:             " + employee2.name);

    System.out.println("Salary:           $ " + employee2.salary);

    System.out.println("Country:          " + employee2.country);

  }

}

Chapter 6—Methods

Quiz 1

public  class PreciousMetal

{

 double ozGold = 1300.0; // the price of one ounce of gold

 double ozSilver = 20.0; // the price of one ounce of silver

 double ozPlatinum = 936; // the price of one ounce of platinum

 boolean isGold = true;

 public  double getMetalPrice(boolean isGold, int ounce)

  {

 if (isGold)

    {

 return ozGold * ounce;

    }

 else

    {

 return ozSilver * ounce;

    }

  }

  // answer 1

 public  double getPlatinumPrice(double ounce)

  {

 return ounce * ozPlatinum;

  }

 public  static  void main(String[] args)

  {

PreciousMetal pm = new PreciousMetal();

    System.out.print(pm.getMetalPrice(false, 4));

    System.out.print(", ");

    System.out.println(pm.getMetalPrice(true, 2));

    // answer 2, 3

    System.out.println("5.5 oz: " + "$ " + pm.getPlatinumPrice(5.5));

    System.out.println("4.5 oz: " + "$ " + pm.getPlatinumPrice(4.5));

    System.out.println("6.0 oz: " + "$ " + pm.getPlatinumPrice(6.0));

  }

}

Quiz 2

public class Calculation

{

 int i = 5;

 int i2 = 3;

 public  int getResult()

  {

    i++;

 if (i <= i2)

    {

 return i * i2;

    }

 else  if ((i + i2) >= 9)

    {

 return i + i2 + 5;

    }

 return i * i2 + 3;

  }

  // answer 1

 public  int calculate(int x, int y)

  {

 return x * y;

  }

 public  static  void main(String[] args)

  {

Calculation cal = new Calculation();

    System.out.println(cal.getResult());

    // answer 2

    System.out.println("The answer is: ");

    System.out.println("22 * 4  = " + cal.calculate(22, 4));

    // answer 3

    System.out.println("9 * 12  = " + cal.calculate(9, 12));

    System.out.println("41 * 11 = " + cal.calculate(41, 11));

  }

}

Quiz 3

public class MyClass

{

 int i = 3;

 int i2 = 8;

 public MyClass()

  {

    i += 4;

    i2 += 2;

  }

 public  void print()

  {

 int x = i + i2;

    System.out.print(x);

  }

  // answer 1

 double getNetSalary(double grossSalary, double taxRate)

  {

 double taxAmount = grossSalary * taxRate;

 double netSalary = grossSalary - taxAmount;

 return netSalary;

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.print();

    // answer 2

    System.out.println("Calculate net salary, tax rate = 20%: ");

    System.out.println("$ 3000 is $ " + mc.getNetSalary(3000, 0.20));

    System.out.println("$ 2400 is $ " + mc.getNetSalary(2400, 0.20));

    System.out.println("$ 1466 is $ " + mc.getNetSalary(1466, 0.20));

    System.out.println("Calculate net salary, tax rate = 30%: ");

    System.out.println("$ 3000 is $ " + mc.getNetSalary(3000, 0.30));

    System.out.println("$ 2400 is $ " + mc.getNetSalary(2400, 0.30));

    System.out.println("$ 1466 is $ " + mc.getNetSalary(1466, 0.30));

  }

}

Quiz 4

public class MyClass

{

 int x = 2;

 public  void print()

  {

 for (int i = 0; i <= 3; i++)

    {

 if (i < 2)

      {

        x++;

      }

 else

      {

        x += 2;

      }

    }

    System.out.print(x);

  }

  // answer 1,2

 public  int getGreaterNumber(int x, int y)

  {

 if (x > y)

    {

 return x;

    }

 else  if (y > x)

    {

 return y;

    }

 else

    {

 return -1;

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // answer 3

    System.out.println(mc.getGreaterNumber(57, 57));

    System.out.println(mc.getGreaterNumber(49, 22));

    System.out.println(mc.getGreaterNumber(7, 89));

    System.out.println(mc.getGreaterNumber(0, -3));

  }

}

Quiz 5

public class Currency

{

  // dollar exchange rate

 double euro = 0.907; // $1 = € 0.907

 double britishPound = 0.762; // $1 = £ 0.762

 double swissFranc = 0.986; // $1 = 0.986 CHF

 double chineseYuan = 6.674; // $1 = ¥ 6.674

 double russianRuble = 64.459; // $ 1 = 64.459; RUB

 public  void convertToDollar(char valuta, int bedrag)

  {

 switch (valuta)

    {

 case ('e'):

        System.out.print(bedrag * euro);

 break;

 case ('p'):

        System.out.print(bedrag * britishPound);

 break;

 case ('f'):

        System.out.print(bedrag * swissFranc);

 break;

 case ('y'):

        System.out.print(bedrag * chineseYuan);

 break;

 case ('r'):

        System.out.print(bedrag * russianRuble);

 break;

 default:

        System.out.print("Invalid");

    }

  }

  // answer 1

 public  double convertEuroToChineseYuan(double amountEuro)

  {

 double chineseYuan = amountEuro * (6.674 / 0.907);

 return chineseYuan;

  }

 public  static  void main(String[] args)

  {

Currency cr = new Currency();

    // cr.convertToDollar('y',100);

    // answer 2, 3

    System.out.println("€ 100 = ¥ " + cr.convertEuroToChineseYuan(100));

    System.out.println("€ 220 = ¥ " + cr.convertEuroToChineseYuan(220));

    System.out.println("€ 300 = ¥ " + cr.convertEuroToChineseYuan(300));

    System.out.println("€ 2   = ¥ " + cr.convertEuroToChineseYuan(2));

  }

}

Quiz 6

public  class Gold

{

 double ozGold = 1300.00; // the price of an ounce of gold

  // answer 1

 public  double getAmountOunceByPrice(double price)

  {

 return price / ozGold;

  }

 public  static  void main(String[] args)

  {

Gold gd = new Gold();

    // answer 2

    System.out.println("$ 7150 = " + gd.getAmountOunceByPrice(7150));

    System.out.println("$ 1300 = " + gd.getAmountOunceByPrice(1300));

    System.out.println("$ 2600 = " + gd.getAmountOunceByPrice(2600));

    System.out.println("$ 5525 = " + gd.getAmountOunceByPrice(5525));

  }

}

Assignment chapter 6

public class Gold

{

 double ozGold = 1300.00; // the price of an ounce of gold

  // answer 1

 public  double getAmountOunceByPrice(double price)

  {

 return price / ozGold;

  }

 public  static  void main(String[] args)

  {

Gold gd = new Gold();

    // answer 2

    System.out.println("$ 7150 = " + gd.getAmountOunceByPrice(7150));

    System.out.println("$ 1300 = " + gd.getAmountOunceByPrice(1300));

    System.out.println("$ 2600 = " + gd.getAmountOunceByPrice(2600));

    System.out.println("$ 5525 = " + gd.getAmountOunceByPrice(5525));

  }

}

Chapter 7—Strings and StringBuffers

Quiz 1

public class Quote

{

  String strQuote = "The weak can never forgive";

  // answer 1

  String myStr = "I feel good";

 public  void myMethod()

  {

    System.out.print(strQuote.charAt(4));

    System.out.print(", " + strQuote.indexOf('k'));

    System.out.print(", " + strQuote.indexOf('e'));

  }

 public  static  void main(String[] args)

  {

Quote qt = new Quote();

    // ms.myMethod();

    // answer 2

    System.out.print(qt.myStr.charAt(7));

    // answer 3

    System.out.print(", " + qt.myStr.indexOf('l'));

  }

}

If this program compiled and run it writes g, 5 to the standard output.

Quiz 2

public  class MyClass

{

  String str1 = "Jack";

String str2 = new String("Jack");

 public  void myMethod()

  {

 if (str1 == str2)

    {

      System.out.print("X");

    }

 if (str1.equals(str2))

    {

      System.out.print("Y");

    }

 else

    {

      System.out.print("Z");

    }

  }

  // Answer 1

 public  boolean compareTwoStrings(String s1, String s2)

  {

 return s1.equals(s2);

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.myMethod();

    // Answer 2

    System.out.println(mc.compareTwoStrings("France", "france"));

    // Answer 3

    System.out.println(mc.compareTwoStrings("Hello", "Hello"));

    System.out.println(mc.compareTwoStrings("123Str", "1234Str"));

    System.out.println(mc.compareTwoStrings("My friend", "My friend"));

  }

}

Quiz 3

public class MyClass

{

  String strQuote = "We cannot solve our problems with the same " +

      "thinking we used when we created them. Albert Einstein";

 public  void myMethod()

  {

    System.out.println(strQuote.substring(21, 26));

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.myMethod();

    // answer 1

    System.out.print(mc.strQuote.substring(82, 97));

  }

}

Quiz 4

public class MyClass

{

  String str = "He$llo $World$";

 public  void myMethod()

  {

    System.out.print(str.replace("$", ""));

  }

  // answer 1

 public String replaceEuroWithDollar(String str)

  {

 return str.replace("€", "$");

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.myMethod();

    // answer 2

    String str = mc.replaceEuroWithDollar("€ 233, € 12, € 90, € 62");

    System.out.print(str);

  }

}

Quiz 5

public class MyClass

{

  String str = " the subconscious mind ";

 public  void myMethod()

  {

 int strLength = str.length();

    str = str.toUpperCase();

    str = str.trim();

    System.out.print(strLength + " " + str + " " + str.length());

  }

  // Answer 1

 public  int getNrCharacter(String str)

  {

 return str.length(); // index starts from 0

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.myMethod();

    // Answer 2a

 int quote1 = mc.getNrCharacter("What we think, we become.");

    System.out.println("The first quote: " + quote1 + " characters");

    // Answer 2b

 int quote2 = mc.getNrCharacter("Logic will get you from A to B. " +

        "Imagination will take you everywhere");

    System.out.print("The second quote: " + quote2 + " characters");

  }

}

Quiz 6

public class MyClass

{

StringBuffer sb = new StringBuffer();

StringBuffer sb2 = new StringBuffer("Jack");

 public  void myMethod()

  {

    sb.append("Elvis ");

    sb2.append(" Ben");

    sb.append(22);

    // Answer 1

    sb.append(" music");

    // Answer 2

    sb2.append(" 2000");

    System.out.print(sb + ", " + sb2);

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.myMethod();

  }

}

Quiz 7

public class MyClass

{

StringBuffer sb = new StringBuffer("He is friend.");

  // answer 1

StringBuffer sb2 = new StringBuffer("He is from ,,, India");

 public  void myMethod()

  {

    // insert code here

    System.out.print(sb);

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.myMethod();

    // answer 2

    System.out.print(mc.sb2.delete(11, 15));

  }

}

Quiz 8

public class MyClass

{

StringBuffer sb = new StringBuffer("He was her friend");

 public  void myMethod()

  {

    // insert code here

    System.out.print(sb);

  }

  // answer 1

 public String convertSbToString(StringBuffer sb)

  {

 return sb.toString();

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.myMethod();

    // answer 2

    String strSb = mc.convertSbToString(mc.sb);

    System.out.print(strSb);

  }

}

Assignment chapter 7

public  class TextManipulation

{

 public  void stringDemo()

  {

    String text = "Brazil $ is $ one $of the largest country in the $ world.";

    System.out.println("Upper case: " + text.toUpperCase());

    System.out.println("Lower case: " + text.toLowerCase());

    System.out.println("Number chars: " + text.length());

    System.out.println("Remove $: " + text.replace("$", ""));

    System.out.println("Remove first 14 chars: " + text.substring(14));

    System.out.println("Return only largest country:" + text.substring(26, 41));

    System.out.println("The index of the first $:" + text.indexOf("$"));

    System.out.println("The index of the Last $:" + text.lastIndexOf("$"));

    System.out.println("Replace Brazil:" + text.replace("Brazil", "Canada"));

  }

 public  static  void main(String[] args)

  {

TextManipulation tmObject = new TextManipulation();

    tmObject.stringDemo();

  }

}

Chapter 8—Packages & access modifiers

Quiz 1

public class ClassB

{

 public  int w = 1;

 protected  int x = 2;

 int y = 3;

 private  int  z = 4;

  // answer 1

 private  char  myChar;

}

public class ClassA

{

 public  static  void main(String[] args)

  {

ClassB cb = new ClassB();

    // System.out.print(cb.w); /* 1 */

    // System.out.print(cb.x); /* 2 */

    // System.out.print(cb.y); /* 3 */

    // System.out.print(cb.z); /* 4 */

    // Answer 2

    // System.out.print(cb.myChar);

  }

}

Quiz 2

package package_02;

public  class ClassB

{

 public  int w = 1;

 protected  int x = 2;

 int y = 3;

 private  int  z = 4;

  // answer 1

 public  int myInt;

}

package package_01;

import package_02.ClassB;

public  class ClassA

{

 public  static  void main(String[] args)

  {

ClassB cb = new ClassB();

    // System.out.print(cb.w); /* 1 */

    // System.out.print(cb.myInt);

    // System.out.print(cb.x); /* 2 */

    // System.out.print(cb.y); /* 3 */

    // System.out.print(cb.z); /* 4 */

    // answer 2

    System.out.print(cb.myInt);

  }

}

Quiz 3

ClassB becomes invisible, because the two classes namely; ClassA and ClassB are in two different packages.

Assignment chapter 8

package assignment.calendar;

public  class DateInfo

{

 private  int day = 16;

 private  int month = 3;

 private  int year = 1998;

 public DateInfo(int day, int month, int year)

  {

 this.day = day;

 this.month = month;

 this.year = year;

  }

 public String getDateFormat()

  {

 return month + "-" + day + "-" + year;

  }

}

package assignment.personal_data;

import assignment.calendar.DateInfo;

public  class Student

{

 private String name;

 private DateInfo birthDate;

 public  static  void main(String[] args)

  {

Student isab = new Student();

Student dav = new Student();

DateInfo bdIsab = new DateInfo(28, 8, 1998);

DateInfo bdDav = new DateInfo(13, 9, 1996);

    isab.name = "Isabella";

    isab.birthDate = bdIsab;

    dav.name = "David";

    dav.birthDate = bdDav;

    System.out.println("---First Student---");

    System.out.println("Name: " + isab.name);

    System.out.println("Birth date: " + isab.birthDate.getDateFormat());

    System.out.println("---Second Student---");

    System.out.println("Name: " + dav.name);

    System.out.println("Birth date: " + dav.birthDate.getDateFormat());

  }

}

If this program is compiled and run, the following is written to the standard outpt.

---First Student---

Name: Isabella

Birth date: 8-28-1998

---Second Student---

Name: David

Birth date: 9-13-1996

Chapter 9—Array and ArrayList

Quiz 1

public  class MyArray

{

 public  static  void main(String[] args)

  {

    // answer

 int[] arrayInt = new  int[11];

 for (int i = 0; i < arrayInt.length; i++)

    {

      System.out.print(arrayInt[i] + " ");

    }

  }

}

The number 11 in this case represents the length or the size of the arrayInt, and that is why the program prints 11 uninitialized integers

to the standard output.

Quiz 2

public  class MyArray

{

 public  static  void main(String[] args)

  {

 int[] arr = new  int[5];

    arr[0] = 3;

    arr[1] = 7;

    arr[4] = 3;

    arr[3] = 1;

    arr[1] = 8;

 for (int i = 0; i < arr.length; i++)

    {

      // answer 1

 if (arr[i] >= 3)

      {

        System.out.print(arr[i] + " ");

      }

    }

  }

}

Quiz 3

import java.util.Arrays;

public  class Animal

{

 public  static  void main(String[] args)

  {

    // answer 2

String[] arrAnimal = new String[8];

    arrAnimal[0] = "Wolf ";

    arrAnimal[1] = "Lion ";

    arrAnimal[2] = "Leopard ";

    arrAnimal[3] = "Elephant ";

    arrAnimal[4] = "Tiger ";

    // answer 1

    arrAnimal[5] = "Bear ";

    arrAnimal[6] = "Zebra ";

    arrAnimal[7] = "Monkey ";

    // see the class "Arrays" of the Java standard API

    Arrays.sort(arrAnimal);

    // answer 3

 for (int i = 0; i < arrAnimal.length; i++)

    {

      System.out.println(arrAnimal[i]);

    }

  }

}

2\. The array size is 5, By adding three elements the error "java.lang.ArrayIndexOutOfBoundsException" is written to the standard

output. To fix the error, you need to resize the array from 5 elements capacity to 8 elements.

Quiz 4

import java.util.Arrays;

public  class MyArray

{

 public  static  void main(String[] args)

  {

 char[] arrCharA = new  char[4];

    arrCharA[0] = 'g';

    arrCharA[1] = 'h';

    arrCharA[2] = 'e';

    arrCharA[3] = 'f';

    // see the class "Arrays" of the Java standard API

 char[] arrCharB = Arrays.copyOf(arrCharA, arrCharA.length);

    Arrays.sort(arrCharA);

    // System.out.print(arrCharA[2]);

    // System.out.print(arrCharB[3]);

    // answer 1

 int[] arrayInt = new  int[5];

    arrayInt[0] = 3;

    arrayInt[1] = 4;

    arrayInt[2] = 2;

    arrayInt[3] = 7;

    arrayInt[4] = 9;

    // answer 2

 for (int i = 0; i < arrayInt.length; i++)

    {

      System.out.println(arrayInt[i]);

    }

  }

}

Quiz 5

import java.util.Arrays;

public  class MyArray

{

 public  static  void main(String[] args)

  {

 char[] arrCharA = new  char[4];

    arrCharA[0] = 'w';

    arrCharA[1] = 'k';

    arrCharA[2] = 'd';

    arrCharA[3] = 'r';

 char[] arrCharB = arrCharA.clone();

    // returns the index of the element 'k'

 int  i = Arrays.binarySearch(arrCharA, 'k');

    // checks whether the two arrays are equal

 boolean  b = Arrays.equals(arrCharA, arrCharB);

    // System.out.print(i + " " + b);

    // Answer 1

 char[] arrayChar = new  char[8];

    arrayChar[0] = 'R';

    arrayChar[1] = 'N';

    arrayChar[2] = 'B';

    arrayChar[3] = 'S';

    arrayChar[4] = 'M';

    arrayChar[5] = 'O';

    arrayChar[6] = 'A';

    arrayChar[7] = 'C';

    // Answer 2

 boolean isEqual = Arrays.equals(arrayChar, arrCharA);

    System.out.println("Is arrayChar equal to arrCharA? " + isEqual);

    // Answer 3

    Arrays.sort(arrayChar);

    // Answer 4

 for (int x = 0; x < arrayChar.length; x++)

    {

      System.out.print(arrayChar[x] + ", ");

    }

  }

}

This program writes the following to the standard output.

Is arrayChar equal to arrCharA? false

A, B, C, M, N, O, R, S,

Quiz 6

public class MyClass

{

 void myMethod()

  {

    // Answer 1

    String strArray[] = { "n", "b", "a", "z" };

 for (int i = 0; i < strArray.length; i++)

    {

 if (strArray[i].equals("z"))

      {

        System.out.print("x1 ");

      }

 else  if (strArray[i].equals("a"))

      {

        System.out.print("x2 ");

      }

 else  if (strArray[i].equals("b"))

      {

        System.out.print("x2 ");

      }

 else

      {

        System.out.print("x3 ");

      }

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.myMethod();

  }

}

Quiz 7

import java.util.ArrayList;

public  class CountryList

{

 public  static  void main(String[] args)

  {

ArrayList<String> countries = new ArrayList<String>();

    countries.add("Germany");

    countries.add("United States");

    countries.add("Russia");

    countries.add("United Kingdom");

    countries.add(2, "India");

    System.out.println("");

    System.out.println("- Before removing Germany from the list -");

 for (int i = 0; i < countries.size(); i++)

    {

      System.out.print(" " + countries.get(i));

    }

    System.out.println("");

    System.out.println("");

    System.out.println("-------- Countries -------");

    System.out.println("Is the list  empty: " + countries.isEmpty());

    System.out.println("Check Spain :       " + countries.contains("Spain"));

    System.out.println("Check Russia:       " + countries.contains("Russia"));

    System.out.println("Index US: " + countries.indexOf("United States"));

    System.out.println("The size:           " + countries.size());

    // Germany is the first country on the list, its index is 0

    countries.remove(0);

    System.out.println("");

    System.out.println("- After removing Germany from the list -");

 for (int i = 0; i < countries.size(); i++)

    {

      System.out.print(" " + countries.get(i));

    }

  }

}

Quiz 8

public class Student

{

  String name;

 int age;

  String email;

 public Student(String name, int age, String email)

  {

 this.name = name;

 this.age = age;

 this.email = email;

  }

}

import java.util.ArrayList;

public  class College

{

 private ArrayList<Student> studentList = new ArrayList<Student>();

 public  void populateStudentArray()

  {

Student st1 = new Student(" Smith", 24, "smith@itmail.com");

Student st2 = new Student(" Jennifer", 22, "jennifer@dzork.com");

Student st3 = new Student(" Thomas", 33, "thomas@ysmail.com");

Student st4 = new Student(" Susan", 25, "susan@rzmail.com");

Student st5 = new Student(" Rita", 28, "rita@online.com");

    studentList.add(st1);

    studentList.add(st2);

    studentList.add(st3);

    studentList.add(st4);

    studentList.add(st5);

  }

 public  static  void main(String[] args)

  {

College cl = new College();

    cl.populateStudentArray();

 for (int i = 0; i < cl.studentList.size(); i++)

    {

 if (i == 2)

      {

        System.out.print(cl.studentList.get(i).name +

            ", " + cl.studentList.get(i).age +

            ", " + cl.studentList.get(i).email);

      }

    }

  }

}

Assignment chapter 9

public class Item

{

  String name;

 double price;

 public Item(String name, double price)

  {

 this.name = name;

 this.price = price;

  }

}

import java.util.ArrayList;

public  class ShoppingCart

{

  // String[] shoppingCart = new String[4];

 private ArrayList<Item> items = new ArrayList<Item>();

 public  void printItems()

  {

 for (int i = 0; i < items.size(); i++)

    {

      System.out.println("Item: " + items.get(i).name + ", Price: " + items.get(i).price);

    }

  }

 public  static  void main(String[] args)

  {

Item item = new Item("Shirt", 20.39);

Item item2 = new Item("Pants", 32.85);

Item item3 = new Item("Socks", 11.25);

Item item4 = new Item("Coat ", 120.65);

ShoppingCart sc = new ShoppingCart();

    sc.items.add(item);

    sc.items.add(item2);

    sc.items.add(item3);

    sc.items.add(item4);

    sc.printItems();

  }

}

Chapter 10—Static members

Quiz 1

public  class Employee

{

 int nr; // instance variable

 static  int  stNr; // class variable

 public Employee()

  {

    nr++;

 stNr++;

  }

 public  static  void main(String[] args)

  {

Employee emp1 = new Employee();

Employee emp2 = new Employee();

Employee emp3 = new Employee();

    // answer 1

Employee emp4 = new Employee();

Employee emp5 = new Employee();

    // answer 2, check the value of stNr

    System.out.print(Employee.stNr + ", ");

    System.out.print(emp1.nr + ", ");

    System.out.print(emp2.nr + ", ");

    System.out.print(emp3.nr);

  }

}

The program writes 5, 1, 1, 1 to the standard output.

Quiz 2

public class MyClass

{

 static  int  x = 3;

 public MyClass()

  {

 x++;

  }

 public  static  int method(int i, int i2)

  {

 x += (i - i2);

 return  x;

  }

  // answer 1

 public  static  void resetX(int resetNummer)

  {

 x = resetNummer;

  }

 public  static  void main(String[] args)

  {

MyClass mk1 = new MyClass();

MyClass mk2 = new MyClass();

    System.out.print(MyClass.x + ", ");

MyClass mk3 = new MyClass();

    MyClass.method(8, 3);

    System.out.print(MyClass.x + ", ");

    // answer 2

    System.out.println("");

    MyClass.resetX(0);

    System.out.println(MyClass.x);

    MyClass.resetX(10);

    System.out.println(MyClass.x);

    MyClass.resetX(100);

    System.out.println(MyClass.x);

  }

}

Quiz 3

public class MyClass

{

 static  int  x = 6;

 int y = 3;

  MyClass()

  {

 x += 3;

    y += 2;

  }

 void method(int i)

  {

 this.y = y - i;

 x++;

  }

 public  static  void main(String[] args)

  {

MyClass mc1 = new MyClass();

MyClass mc2 = new MyClass();

MyClass mc3 = new MyClass();

    mc1.method(3);

    // answer 1, 2, 3

    MyClass mc4, mc5, mc6, mc7, mc8;

    System.out.print(mc2.x + ", " + mc1.y);

  }

}

By creating object references the constructor is not called, therefore the value of the static variable x doesn't change.

Quiz 4

public class MyClass

{

 static  int  x = 2;

  MyClass()

  {

 x++;

  }

 static  void methodA(int i)

  {

 x = x - i;

  }

 int methodB(int i)

  {

 return  x + i;

  }

 public  static  void main(String[] args)

  {

MyClass mc1 = new MyClass();

    MyClass.methodA(2);

MyClass mc2 = new MyClass();

    System.out.print(mc2.methodB(3));

  }

}

By replacing the statement x += 4 with the statement x++, the program writes 5 to the standard output. See the explanation of the quiz.

Quiz 5

public  class MyClass

{

 int x;

StringBuffer sb = new StringBuffer();

 public MyClass()

  {

    myMethod();

  }

 public  void myMethod()

  {

    x += 3;

    sb.append(x);

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

MyClass mc2 = new MyClass();

MyClass mc3 = new MyClass();

    System.out.println(mc.sb);

  }

}

2\. By removing the static keyword from the class variable x, the program writes 333 to the standard output.

4\. By removing the both static keywords from the variables x and sb the program writes 3 to the standard output.

5\. yes.

Assignment chapter 10

public class ProgrammingLanguage

{

 static  int  numberOfLanguages;

 static String language = "";

  ProgrammingLanguage(String lg)

  {

 numberOfLanguages++;

 language += lg;

  }

 public  static  void main(String[] args)

  {

ProgrammingLanguage pl1 = new ProgrammingLanguage("Java, ");

ProgrammingLanguage pl2 = new ProgrammingLanguage("C++, ");

ProgrammingLanguage pl3 = new ProgrammingLanguage("Python, ");

ProgrammingLanguage pl4 = new ProgrammingLanguage("PHP, ");

ProgrammingLanguage pl5 = new ProgrammingLanguage("Ruby");

    System.out.println("Nr: " + ProgrammingLanguage.numberOfLanguages);

    System.out.println("Languages: " + ProgrammingLanguage.language);

  }

}

The code writes the following to the standard output.

Nr: 5

Languages: Java, C++, Python, PHP, Ruby

Chapter 11—Inheritance

Quiz 1

public  class MySuper

{

 protected  int x = 5;

}

public  class MySub extends MySuper

{

 private  int y = 8;

  MySub()

  {

    x += 2;

    y++;

    System.out.print(x + ", " + y);

  }

 public  static  void main(String[] args)

  {

MySub ms = new MySub();

  }

}

The program writes 7, 9  to the standard output.

Quiz 2

public class MySuper

{

 protected  int x = 1;

  MySuper()

  {

    x += 2;

  }

}

public class MySub extends MySuper

{

  MySub(int y)

  {

    x += y;

  }

 public  static  void main(String[] args)

  {

MySub ms = new MySub(4);

MySub ms2 = new MySub(6);

    System.out.print(ms2.x);

  }

}

The program writes 9  to the standard output.

Quiz 3

public  class MySuper

{

 protected  char c = 'G';

  MySuper()

  {

    System.out.print('Q');

  }

 void method()

  {

    System.out.print(c);

  }

}

class MySub extends MySuper

{

 char c2 = 'A';

  MySub()

  {

 this('N');

    System.out.print(c2);

  }

  MySub(char c)

  {

    System.out.print(c);

  }

 void method()

  {

 super.method();

    System.out.print(c2);

  }

 public  static  void main(String[] args)

  {

MySub mySub = new MySub();

    mySub.method();

  }

}

By creating mySub object, the MySuper() constructor is called and it writes "Q" to the standard output.

The result is: QNAGA

Quiz 4

public class SuperB

{

 protected  int x = 3;

 public SuperB()

  {

    x += 2;

    System.out.print(" x" + x);

  }

}

public class SuperA extends SuperB

{

 int y = 7;

 public SuperA()

  {

    y++;

    System.out.print(" y" + y);

  }

}

public class MySub extends SuperA

{

 int x;

 public MySub()

  {

    x += 2;

    y += 3;

    System.out.print(" x" + x);

    System.out.print(" y" + y);

  }

 public  static  void main(String[] args)

  {

MySub mySub = new MySub();

  }

}

The result would be: x5 y8 x2 y11

All the values remain as they were except the x that is printed inside MySub constructor.

That is because MySub now has its own x variable.

Quiz 5

public  class MySuper

{

 protected  int x = 2;

 int method(int i)

  {

 return x + i;

  }

}

public  class MySub extends MySuper

{

 int method(int i, int i2)

  {

 return method(i) + x + i2;

  }

 public  static  void main(String[] args)

  {

MySub mySub = new MySub();

    System.out.print(mySub.method(2, 8));

  }

}

This program writes 14 to the standard output.

Quiz 6

public class MySuper

{

 protected  int x = 3;

 protected  char e = 'd';

 void myMethod()

  {

    x += 4;

    System.out.print(e);

    System.out.print(x);

  }

}

public class MySub extends MySuper

{

 char e = 'p';

 void myMethod()

  {

    x++;

    System.out.print(e);

 super.myMethod();

    x += 2;

    System.out.print(x);

  }

 public  static  void main(String[] args)

  {

MySub ms = new MySub();

    ms.myMethod();

  }

}

This program writes pd810 to the standard output.

Quiz 7

public class MySuper

{

  MySuper(String name)

  {

 this(name, "d");

    System.out.print(name);

  }

  MySuper(String name, String name2)

  {

    System.out.print(name);

    System.out.print(name2);

  }

}

public class MySub extends MySuper

{

  MySub(String name)

  {

 super("s");

    System.out.print(name);

  }

 public  static  void main(String[] args)

  {

MySub ms = new MySub("x");

  }

}

This program writes sdsx to the standard output.

Quiz 8

package package_02;

public  class MySuper

{

 public String str1 = "String 1";

 protected String str2 = "String 2";

  String str3 = "String 3";

 private String str4 = "String 4";

  // answer 1

 protected  int myInt;

}

package package_01;

import package_02.MySuper;

public  class MySub extends MySuper

{

 public  static  void main(String[] args)

  {

MySuper mySuper = new MySuper();

MySub mySub = new MySub();

    // System.out.print(mySuper.str1); /* 1 */

    // System.out.print(mySuper.str2); /* 2 */

    // System.out.print(mySuper.str3); /* 3 */

    // System.out.print(mySuper.str4); /* 4 */

    // System.out.print(mySub.str2); /* 5 */

    // System.out.print(mySub.str1);

    // Answer 2, 3

    // System.out.print(mySuper.myInt); // mySuper cannot access myInt

    System.out.print(mySub.myInt); // mySub can access myInt

  }

}

Assignment chapter 11

public class Vehicle

{

 protected String brand;

 protected  int manufactureYear;

 protected String color;

 public Vehicle(String brand, int manufactureYear, String color)

  {

 this.brand = brand;

 this.manufactureYear = manufactureYear;

 this.color = color;

  }

 public  void print()

  {

    System.out.println("Brand:                    " + brand);

    System.out.println("Manufacture year:          " + manufactureYear);

    System.out.println("Color:                    " + color);

  }

}

public class Car extends Vehicle

{

 private  int maxNrPassenger;

 public Car(String brand, int manufactureYear, String color, int maxNrPassenger)

  {

 super(brand, manufactureYear, color);

 this.maxNrPassenger = maxNrPassenger;

  }

 public  void print()

  {

    System.out.println("----------------Car------------------------");

 super.print();

    System.out.println("Max passengers: " + maxNrPassenger);

  }

}

public class Truck extends Vehicle

{

 private  double maxLoad;

 public Truck(String brand, int manufactureYear, String color, double maxLoad)

  {

 super(brand, manufactureYear, color);

 this.maxLoad = maxLoad;

  }

 public  void print()

  {

    System.out.println("----------------Truck---------------");

 super.print();

    System.out.println("Maximum Load:             " + maxLoad);

  }

}

public class TestProgram

{

 public  static  void main(String[] args)

  {

Truck tk1 = new Truck("BMW", 2016, "green", 6550);

Truck tk2 = new Truck("Volvo", 2014, "black", 4000);

Car car1 = new Car("Toyota", 2013, "red", 5);

Car car2 = new Car("Mazda", 2017, "blue", 8);

    car1.print();

    car2.print();

    tk1.print();

    tk2.print();

  }

}

Chapter 12—Final classes and the final keyword

Quiz 1

1.  Yes.
2.  No, you cannot extend final classes.

Quiz 2

Although the method methodeB returns a variable type int, its name causes nevertheless, an error. The reason is that this method has the same number of parameters and the same variable type as the final method methodeB of the superclass.

Quiz 3

public  class MySuper

{

 final  int x = 4;

 final String methodA(int i, String s)

  {

    String str = i + ", " + s;

 return str;

  }

}

public  class MyClass extends MySuper

{

 int x = 3;

String methodA(String s, int i)

  {

    String str = s + ", " + i;

 super.x++;

 return str;

  }

 public  static  void main(String[] args)

  {

MySuper ms = new MySuper();

    System.out.print(ms.methodA(23, "Emma"));

  }

}

The variable x in the superclass is final , so its value is not be changed . A final variable is actually a constant.

Quiz 4

public class MySuper

{

 final  void methodeA(int x, double y)

  {

 double z = x * y;

    System.out.print(z);

  }

}

public final class MyClass extends MySuper

{

 void methodeA(int x, int y)

  {

 int z = x - y;

    System.out.print(z);

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    // mc.methodeA(5,3.0);

    mc.methodeA(6, 4);

  }

}

The program writes 2 to the standard output.

Assignment chapter 12

1.  You cannot extend the class Math.
2.  The class Math is final therefore it is not possible to use it as a superclass for your class.
3.  No, because all the methods of the class Math are static and you can invoke them by using the name of the class Math.

For the rest of the question see the code.

public  class MyCalculation

{

 public  static  void main(String[] args)

  {

    System.out.println("The greater number is: " + Math.max(35, 46));

    System.out.println("The smaller number is: " + Math.min(46.98, 44.99));

    System.out.println("The greater number is: " + Math.sqrt(81.0));

    System.out.println("The greater number is: " + Math.random());

  }

}

This code writes the following to the standard output.

The greater number is: 46

The smaller number is: 44.99

The rootof 81 is:      9.0

The random number is:  0.4192215620231091

Chapter 13—Abstract classes

Quiz 1

public  abstract  class MyAbstract

{

 protected  int x = 6;

 public MyAbstract()

  {

    x += 2;

  }

 abstract  int getSum(int x);

 abstract  void printMyName(String name);

}

public  class MyClass extends MyAbstract

{

 int getSum()

  {

 return x + 5;

  }

 int getSum(int x)

  {

 return  super.x + x;

  }

 void printMyName(String name)

  {

    System.out.print("Name: " + name);

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    System.out.println(mc.getSum(4));

    mc.printMyName("Emily");

  }

}

This program writes the name Emily to the standard output.

Quiz 2

By adding the statement super(10); above the statement System.out.print(“p”); the program writes n10ps to the standard output. See the explanation of this quiz.

Quiz 3

The program writes NOL27 to the standard output, because the statement this.str += str; adds the letter O to the str variable which has the value N.

Quiz 4

public  abstract  class MyClassB

{

  MyClassB()

  {

    System.out.print("a");

  }

 public  abstract  int getResult(int x, int y);

}

public  class MyClassA extends MyClassB

{

  MyClassA()

  {

    System.out.print("b");

  }

  MyClassA(int i)

  {

    System.out.print("d" + i);

  }

 public  int getResult(int x, int y)

  {

 return x * y;

  }

}

public  class MyClass extends MyClassA

{

  MyClass(int i)

  {

    System.out.print("c" + i);

  }

 public  static  void main(String[] args)

  {

 new MyClass(4);

 new MyClassA(4);

  }

}

The class MyClassA extends the abstract class MyClassB, therfore it should override the abstract method getResult or the MyClassB should be declared abstract.

Quiz 5

public  abstract  class MyAbstract

{

 int x;

 abstract  void methodeA();

 abstract String methodeB(String s);

  // Methode 1

 public  double getPrice(double price)

  {

 return price;

  }

  // Methode 2

 public  static  double getPrice2(double price)

  {

 return price;

  }

}

public  class MyClass extends MyAbstract

{

 void methodeA()

  {

    System.out.print("x");

  }

 void methodeA(int x)

  {

    System.out.print("y" + x);

  }

  String methodeB(String s)

  {

 return s + x;

  }

  String methodeB(int x)

  {

 return "x" + x;

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.methodeA();

    System.out.println(mc.methodeB("y"));

// Methode 1

    System.out.println("The price is: " + mc.getPrice(33));

// Methode 2

    System.out.println("The price is: " + MyAbstract.getPrice2(33));

  }

}

Answers

1.  Yes.
2.  By defining the method static, you can invoke the method using the class name without the necessity of instantiating any objects.

Assignment chapter 13: What is the current date and time?

import java.util.Calendar;

public  class DateAndTime

{

 public  static  void main(String[] args)

  {

    Calendar now = Calendar.getInstance();

    System.out.println(now.getTime());

  }

}

Chapter 14—Interfaces

Quiz 1

public  interface MyInterface

{

 int  x = 5;

 void methode();

 void methode(int i);

}

public  class MyClass implements MyInterface

{

 public  void methode()

  {

    // x ++ ; /* 1*/

    System.out.print(x);

  }

 public  void methode(int i)

  {

 int z = i;

    // z = z + x; /* 2*/

    methode();

    System.out.print(z);

  }

 public  static  void main(String[] args)

  {

 int  x = 7;

    x++;

 new MyClass().methode(4);

  }

}

There would be no error because the statement x++; increments the value of the variable x inside the main method by one. This program writes 54 to the standard output.

Quiz 2

public interface InterfaceA

{

 void myMethod();

 void myMethod(char c);

}

public  interface InterfaceB

{

 int  MAX_ALLOWED = 3;

 int getSum();

}

public  class MyClass implements InterfaceA,InterfaceB

{

// int MAX_ALLOWED; /*1*/

 int z = 2;

 public  void myMethod()

  {

z = MAX_ALLOWED + 4;

    System.out.print("H");

  }

 public  void myMethod(char j)

  {

    // MAX_ALLOWED += 3; /* 2*/

    myMethod();

    System.out.print(j);

    System.out.print(z);

  }

 public  int getSum()

  {

 return  MAX_ALLOWED + z;

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.myMethod();

  }

}

This code writes H to the standard output.

Quiz 3

1.  An error occurs in the class MySuper, because it uses the variable x. Remember that MuSuper class has no access to the variable x of its subclass.
2.  By executing the code, the output would be m4qw4.

Assignment chapter 14: A practical application of interfaces

public interface Payable

{

 double getSalary();

}

public class Employee implements Payable

{

 double taxRate = 0.30;

 double salary;

 public Employee(double salary)

  {

 this.salary = salary;

  }

 public  double getSalary()

  {

 double netSalary = salary - (salary * taxRate);

 return netSalary;

  }

}

public class Freelancer implements Payable

{

 int workingHours;

 double hourlyRate;

 public Freelancer(int workingHours, double hourlyRate)

  {

 this.workingHours = workingHours;

 this.hourlyRate = hourlyRate;

  }

 public  double getSalary()

  {

 double salary = workingHours * hourlyRate;

 return salary;

  }

}

public class Test

{

 public  static  void main(String[] args)

  {

Employee emp = new Employee(3000.0);

Freelancer fr = new Freelancer(140, 60);

    System.out.println("The employee wage is:   $ " + emp.getSalary());

    System.out.println("The freelancer wage is: $ " + fr.getSalary());

  }

}

This program writes the following to the standard output.

The employee wage is:   $ 2100.0

The freelancer wage is: $ 8400.0

Chatper 15—Casting

Quiz 1

public  class MyClass

{

 public  static  void main(String[] args)

  {

 int i1 = 127;

 int i2 = 134;

 byte b1 = (byte) i1;

 byte b2 = (byte) i2;

    System.out.print(b1 + ", ");

    System.out.println(b2);

    // answer

    System.out.print("The answer is: ");

 int myInt = i1 + i2;

    System.out.print(myInt);

    // short myShort = i1;

  }

}

This program writes the following to the standard output.

127, -122

The answer is: 261

Quiz 2

public  class MyClass

{

 public  static  void main(String[] args)

  {

 int i = 122;

    i = 187; // answer

 double d = i;

    System.out.print(d);

  }

}

This program writes 187.0 to standard output.

Quiz 3

public  class MySub extends MySuper

{

 int i = 3;

 public  int method()

  {

 return 2 * i;

  }

 public  static  void main(String[] args)

  {

MySuper s = new MySub();

    // Answer 1, 2

    MySub ms = (MySub) s;

    // Answer 3

    System.out.println(" " + ms.i + ", " + ms.method());

    System.out.println(" " + s.i + ", " + s.method());

  }

}

Quiz 4

public class MySuper

{

 protected  int x;

  MySuper()

  {

    x++;

    System.out.print("N");

  }

 int myMethod()

  {

 return x + 3;

  }

}

public class MySub extends MySuper

{

  MySub()

  {

    x += 2;

    System.out.print("P");

  }

 int myMethod()

  {

 return x + 4;

  }

 public  static  void main(String[] args)

  {

MySuper ms = new MySuper();

    System.out.print(ms.myMethod());

  }

}

The program writes N4 to the standard output.

Quiz 5

public class MySuper

{

 public MySuper()

  {

    System.out.print("m");

  }

 public  void method()

  {

    System.out.print("s");

  }

 public  void method(int i)

  {

    method();

    System.out.print("k" + i);

  }

}

public class MySub extends MySuper

{

 public  void method()

  {

    System.out.print("t");

  }

 public  static  void main(String[] args)

  {

// MySuper ms = new MySub();

    // Answer 1

MySuper ms = new MySuper();

    ms.method(3);

  }

}

Assignment chapter 15

public class MyList

{

List<String> list = new ArrayList<String>();

ArrayList<String> aList = new ArrayList<String>();

 public  static  void main(String[] args)

  {

MyList mc = new MyList();

    mc.aList.clone();

    mc.list.clone();

  }

}

The class ArrayList implements the interface List. Therefore it must override all the methods of the interface.

The class ArrayList also has its own specific methods, which does not exist in the interface List. One of those methods is the method clone. Therefore, the object list cannot access the method clone.

Chapter 16—Nested Classes

Quiz 1

public  class Outer

{

 int x;

  Outer()

  {

    x += 4;

  }

 class Inner

  {

 int y;

 public  void methodA()

    {

      x++;

      System.out.print(x);

    }

  }

 public  static  void main(String[] args)

  {

Outer.Inner inner = new Outer().new Inner();

    inner.methodA();

  }

}

The output is 5, because the inner class has access to the integer variable x of the outer class.

Quiz 2

public  class Outer

{

  // question

 private  int a = 5;

  Outer()

  {

    a += 4;

  }

 class Inner

  {

    Inner()

    {

      a++;

    }

  }

 public  static  void main(String[] args)

  {

Outer outer = new Outer();

    Inner inner = outer.new Inner();

    System.out.print(outer.a);

  }

}

This program writes 10 to the standard output.

Quiz 3

class Outer

{

 private  int x = 2;

  Outer()

  {

 this(3);

    x++;

  }

  Outer(int i)

  {

    x += i;

    System.out.print(x);

  }

 class Inner

  {

 public  void methodA()

    {

      x -= 3;

      System.out.print(x);

    }

  }

 public  static  void main(String[] args)

  {

    // answer

Outer.Inner inner = new Outer(7).new Inner();

    inner.methodA();

  }

}

This program writes 96 to the standard output.

Quiz 4

class Outer

{

 static  int  x = 3;

  Outer()

  {

 x += 4;

  }

 static  class Nested

  {

    Nested()

    {

 x += 2;

    }

 int method(int i)

    {

      System.out.print(x);

 return i + x;

    }

  }

 public  static  void main(String[] args)

  {

Outer outer = new Outer();

Outer.Nested nested = new Outer.Nested();

    System.out.print(nested.method(2));

  }

}

By creating an instance of the Outer class the no-argument Outer constructor is invoked.

x += 4; increments the value of x by 4.

x = 3 + 4 + 2 = 9\.

The program writes 911 to the standard output.

Read the explanation of the quiz!

Assignment chapter 16: Working with Java API documentation

public  class Car

{

  String brand;

  String manufactureYear;

  String licensePlate;

 public Car(String brand, String manufactureYear, String licensePlate)

  {

 this.brand = brand;

 this.manufactureYear = manufactureYear;

 this.licensePlate = licensePlate;

  }

 public  void printInfo()

  {

    System.out.println("Brand:               " + brand);

    System.out.println("Year of manufacture: " + manufactureYear);

    System.out.println("License plate:       " + licensePlate);

  }

 public  class Engine

  {

    String engineCode;

    String fuel;

 public Engine(String engineCode, String fuel)

    {

 this.engineCode = engineCode;

 this.fuel = fuel;

    }

 public  void printInfo()

    {

      System.out.println("Engine code:         " + engineCode);

      System.out.println("Fuel:                " + fuel);

    }

  }

 public  static  void main(String[] args)

  {

Car car = new Car("BMW", "2016", "XN-45-489");

    Engine engine = car.new Engine("N45B20A", "Petrol");

    car.printInfo();

    engine.printInfo();

  }

}

Chapter 17—Exceptions

Quiz 1

public class MyClass

{

 public  void method()

  {

 try

    {

      System.out.print("x");

 int  x = Integer.parseInt("38");

      System.out.print("y");

    }

 catch (NumberFormatException e)

    {

      System.out.print("z");

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.method();

  }

}

3\. The output is xy because we passed an int number to the method parseInt. That is what the program expects. The catch block is ignored.

Quiz 2

public  class MyClass

{

 public  void method()

  {

 try

    {

 int[] intArray = new  int[5];

 int  z = intArray[6];

      System.out.print("w");

    }

 catch (ArithmeticException e)

    {

      System.out.print("x");

    }

 catch (ArrayIndexOutOfBoundsException e)

    {

      System.out.print("y");

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.method();

  }

}

The finally-block is removed therefore z is not printed to the standard output.

The program writes only y to the standard output.

Quiz 3

public class MyClass

{

  String str = "Boris";

 public  void method()

  {

 try

    {

      str.substring(1);

      System.out.print("s");

    }

 catch (NullPointerException e)

    {

      System.out.print("x");

    }

 catch (Exception e)

    {

      System.out.print("y");

    }

 finally

    {

      System.out.print("z");

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.method();

  }

}

The output of the program is "sz", because the str object is not null anymore.

Quiz 4

public class MyClass

{

 int x = 20;

 public  void method()

  {

 try

    {

 int  i = 2 / x;

      System.out.print("a");

    }

 catch (NullPointerException n)

    {

      System.out.print("b");

    }

 catch (ArithmeticException e)

    {

      System.out.print("d");

    }

 finally

    {

      System.out.print("f");

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.method();

  }

}

int i = 2/x was dividing a number by zero which causes ArithmeticException.

By initializing the variable x, the divide isn't by zero but by 20\. In this case, the exception does not occur. The try-catch is executed as well as the finally-block.

The program writes af to the standard output.

Quiz 5

public class MyClass

{

  StringBuffer sb;

 int z;

 public  void myMethod()

  {

 try

    {

      sb.append("s");

      z = 5 / 0;

    }

 catch (NullPointerException e)

    {

      System.out.print("n");

    }

 catch (ArithmeticException ae)

    {

      System.out.print("a");

    }

  }

 public  static  void main(String[] args)

  {

MyClass mc = new MyClass();

    mc.myMethod();

  }

}

The first statement is sb.append(“sb“); .

Since sb is only a reference to an object therefore, the NullPointerException is caught.

The program writes n to the standard output.

Quiz 6

public class MyClass

{

 static String str = "";

 static  void calculate(int x, int y)

  {

 str += "A";

 if (y == 0)

    {

 throw  new ArrayIndexOutOfBoundsException();

    }

 int  z = x / y;

 str += "B";

  }

 public  static  void main(String[] args)

  {

 try

    {

 str += "C";

 calculate(10, 0);

 str += "D";

    }

 catch (ArithmeticException e)

    {

 str += "E";

    }

 catch (ArrayIndexOutOfBoundsException ae)

    {

 str += "F";

    }

    System.out.println(str);

  }

}

The code throws a wrong type of exception because the exception has nothing to do with arrays. Anyway, the catch block ArrayIndexOutOfBoundsException is caught, and the program writes CAF to the standard output.

Quiz 7

public class MyClass

{

 public  static  void test(String str)

  {

 if (str == null)

    {

 throw  new NullPointerException();

    }

 else

    {

 throw  new RuntimeException();

    }

  }

 public  static  void main(String[] args)

  {

 try

    {

      System.out.print("A");

 test(null);

    }

 catch (NullPointerException e)

    {

      System.out.print("B");

    }

 catch (Exception e)

    {

      System.out.print("C");

    }

 finally

    {

      System.out.print("D");

    }

  }

}

The program writes ABD to the standard output, because the NullPointerException is thrown.import java.util.ArrayList;

Assignment chapter 17

public  class MyException extends Exception

{

 public MyException(String message)

  {

 super(message);

  }

}

import java.util.ArrayList;

public  class Test

{

 private  static ArrayList<String> movieList = new ArrayList<String>();

 public  static  void populateList()

  {

 movieList.add("The Godfather");

 movieList.add("Titanic");

 movieList.add("Dances with Wolves");

 movieList.add("The Pianist");

 movieList.add("Wall Street");

 movieList.add("Amadeus");

  }

 public  static String getMovie(int movieIndex) throws MyException

  {

 if (movieIndex >= movieList.size())

    {

 throw  new MyException("The movie " + movieIndex + " does not exist.");

    }

 return  movieList.get(movieIndex);

  }

 public  static  void main(String args[])

  {

 populateList();

 try

    {

String movie = getMovie(5);

      System.out.print("The movie title is: " + movie);

    }

 catch (MyException me)

    {

      // System.out.print(me.getMessage());

      me.printStackTrace();

    }

  }

}