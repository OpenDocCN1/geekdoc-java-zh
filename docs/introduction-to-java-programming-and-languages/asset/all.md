![](Images/cover00518.jpeg)

Introduction to Java Programming and languages

by Theo Ryan

Contents

[Introduction](#part0002.xhtml__Toc102306513)

[1.             Types  data, literals, variables](#part0003.xhtml__Toc102306514)

[2.             Operations  and  operators](#part0004.xhtml__Toc102306515)

[3.             Classes  and  objects](#part0005.xhtml__Toc102306516)

[4.             Inheritance  and  polymorphism](#part0012.xhtml__Toc102306517)

[5.             Treatment  exceptions](#part0014.xhtml__Toc102306518)

[6.             Treatment  lines](#part0018.xhtml__Toc102306519)

[7.             Input Output](#part0025.xhtml__Toc102306520)

[8.             Containers](#part0028.xhtml__Toc102306521)

[9.             Multithreaded  programming](#part0031.xhtml__Toc102306522)

[10.Technology  access  to  bases  data  JDBC](#part0033.xhtml__Toc102306523)

[11.network  programming](#part0038.xhtml__Toc102306524)

# Introduction

The textbook is intended for students of the Bachelors of the faculty  informatics  and  computing  technology, students  on  special  laity "Mathematical support and administration of information  mating systems". It describes the means of the programming language. Java  and  some  related  with  technology.  Benefit  contains  See also some general information about object-oriented software.  gamming  and  design.

First  two  chapters  devoted  basic  funds  language   types operations and operators. Much of the material in these chapters  presented in a comparison of Java language tools with similar tools -  mi  language  C++.

AT  chapters  3–5  set out  principles  object-oriented  programming and describes the language tools that implement these principles.  cycles. Particular attention is paid to the processing of erroneous situations with  might  exceptions  a  also  some  issues  design  class  owls.

Chapters 6-8 describe the features of the Java Standard Library. Ras-  issues of processing string data, streaming input / you-  water,  a  also  use  container  classes  Java  —  extremely  powerful and convenient means of storing and processing data in the application  niyakh.

Chapters  9–11  present  yourself  introduction  in  some  from  Java techno  logy. The presented material allows us to study the ideas underlying  ve  relevant  technology,  a  also  master  basic  facilities  these  technologies.

At the end of the manual is a list of the main and additional  literature on the subject under consideration. In this list I would like  highlight the book [ [1](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ], which contains a very detailed and in-depth exposition of  understanding of the mechanisms of the language, as well as a book [ [2](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ], which can serve as  a guide to the main tools and especially the libraries of the language.  wanted  would  also  recommend  book  [ [3](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ],  describing  character-  nye  mistakes  design  java applications,  study of  which  maybe  substantially  raise  qualification  programmer.

# 1. Types  data, literals, variables

1.1. Primitive data types.

 Java defines 8 primitives -  data types. These include four integer byte , short ,  int , long , two real floats and doubles , character char and logical  boolean data types. Their main characteristics are given in  tab.  [1.1](#part0003.xhtml__bookmark4) .  AT  difference  from  C++  in  Java  No  type  data  "pointer".The main feature of primitive data types in Java is  that variables of these types are not objects. Variables  all other types, including arrays and string type variables  String , are object references (object references). By-  more fractional  they  will  considered  in  P.  [3.3](#part0005.xhtml__bookmark20) .

1.2. Literals. Integer literals can be specified in ten  tic,  octal  and  hexadecimal  form.  Literals  in  decimal  in some form are written directly, for the rest they are used  prefixes similar to prefixes in the C language: "0" - for octal  and "0x" for hexadecimal literals. For example, integer  the literal 47 can be represented as 47, 057, or 0x2F. All integers  fief  literals  automatically  are given  to  minimum  possible  type, but not higher than int . Long literals must have an "L" suffix  or  "l"  (For example,  47L).

Literals  with  floating  dot  may  introduce yourself  in  usual  or  in  scientific  format.  Literals  type  float  should  have  suffix  F  or

"f"  (For example,  3.5F),  a  literals  type  double - suffix  "D"  or  "d",  which  maybe  sink  (3.5D  or  simply  3.5).

| Type  data | The size,  byte | Permissible  values |
| byte | one | –128  127 |
| short | 2 | –32768  32767 |
| int | 4 | –2147483648  2147483647 |
| long | eight | -2 63   263 _  -  one |
| float | eight |    1.4  10–45 3.4  1038 |
| double | 16 |    1.7  10–324 4.9  10308 |
| char | 2 | 0 65535 |
| Boolean | — | true,  false |

Table  1.1.  Primitive  types  data  in  Java

Symbolic  literals  are limited  single  quotes.  So-  hexadecimal representation in Unicode is also possible. AT  in the latter case, the literal is written as a sequence of  four hexadecimal digits prefixed with "\u"). For example, the literal  ' yu '  maybe  be  presented  in  form  ' \u044E ' .

String  literals  are limited  double  quotation marks  ("abcd").

Two boolean literals true and false are defined that are not equal to an integer  literals  one  and  0  respectively.

1.3. Variables. Declaring variables in Java is similar to  the phenomenon of variables in C++. Any variable can be initialized  zated at the time of description by any valid expression. Region  the action and lifetime of a local variable is limited by the block,  in  which  this  variable  described.

Unlike C++, no declaration is allowed in an inner block  variable with the same name as the variable in the outer block (except  me case when the variable in the outer block is an argument  method).

Variables declared with the final specifier are unchangeable.  replaceable  (constant).  For example:

![](Images/image00479.jpeg)final  double  PI  =  3.141592653589793116;

1.4. Type conversions. Type conversions in Java are divided  on the  implicit  and explicit.  Implicit  transformations  carried out  com-  peeler automatically. Rules for Automatic Casting in Java  are much more rigid than in C++. Unlike C++  implicit conversions in Java are performed only when  when  possibly  guarantee  what  in  result  transformations  not  pro-  there will be a loss of significance. For example, the following line, which is  correct from the point of view of the C ++ language, in Java it will cause a compilation error  tions:

![](Images/image00479.jpeg)int  x = 2.5; // try  implicit conversion from double to int

Let us give more formal rules for implicit conversion like  pov. Automatic type conversion when assigning  found,  if  fulfilled  the following  conditions:

  required  cast  integer  type  or  type  char  to  to some  or  numerical  type  or  material  to  real;

  type,  to  to whom  required  cast,  It has  more  the size,  how  original.

Automatic  transformation  types  in  expressions  carried out

  for  arguments  operations  concatenation  lines  (more  detail  cm.  P.  [6.3](#part0022.xhtml__bookmark51) );

  if  one  from  arguments  binary  operations  It has  type  double ,  second  is given  to  type  double ;

  otherwise:  if  one  from  arguments  It has  type  float ,  second  is given  to  type  float ;

  otherwise:  if  one  from  arguments  It has  type  long ,  second  is given  to  type  long ;

  otherwise  both  argument  are given  to  type  int .

The last point should be noted here. In some cases it  application may lead to unnatural results.  For example, the following snippet is wrong in terms of  language:

![](Images/image00480.jpeg)short a  =  5;

short b = a + 1; // error: short is required, not int

The error is related to the fact that when adding 1 to the value of the variable a  the result has been converted to type int . Since the transformation  change from type int to short can lead to underflow, then it  must  be produced  explicitly:

![](Images/image00479.jpeg)short  b  =  (short)(a  +  1);

The reason for this "weird" behavior is the fact that the types  byte and short data were not created to perform arithmetic  operations, but for exchange with external devices. For execution  arithmetic  operations  should  use  types  int  and  long .

Explicit conversion of compatible types is carried out as follows:  blowing  rules:

  constriction  integer  types  produced  through  truncation  old-  shih  bits

  truncation of real types when assigning them to integer products  is carried out by discarding the fractional part and applying the previous  future  item.

The syntax for explicit type conversion is the same as for pre-  education  types  in  C  (cm.  example  higher).

Finally, some type conversions are not valid -  mi.  AT  number  such  transformations  includes:  any  transformations  two type Boolean , class conversions to primitive types, and accept  tive types to classes (with some exceptions), etc. Trying  fulfillment  such  transformations  will  drive  to  mistakes  on the  stage  compilation.

1.5. Arrays. Arrays in Java are objects, so they  all rules for working with objects apply (see clause [3.3](#part0005.xhtml__bookmark20) ). However,  insofar as  arrays  are  alone  from  most  wide  applied  structures  data,  they  will  considered  here.

The syntax for declaring a one-dimensional array is ana-  logical description of variables, but to the name of the variable or to the name  type  data  added  empty  square  parentheses.  For example:

int  a[];  //  first  option

int []  b;  //  second  option

In this case, the array itself is not created . To create an array, use  use  operation  new :

a  =  new  int [50];

Maybe  simultaneous  announcement  and  selection  memory:

int  a[]  =  new  int [50];

Possible  also  initialization  array  at  his  creation:

int  a[]  =  {  20,  50,  166,  72,  0,  –53  };

[] operator is used to access the elements of an array . Element-  you array are numbered from zero. Attempt to refer to non-existent  array element results in a run-time error. Arrays  support obtaining information about their sizes through  exemplary  variable  length .

Multidimensional arrays are arrays of arrays. They are  may  be created  likewise  one-dimensional:

int  a[][]  =  new  int [5][2];

Maybe  creation  non-rectangular  arrays.  Way  work  with  still-  mi  arrays  illustrated  next  example.

//  Example:  construction  tables  binomial  coefficients

public  class  Binomial

{

public  static  void  main(String  args[])

{

final  int  N  =  ten;

int  c[][]  =  new  int [N][];

//  Formation  tables  binomial  coefficients

for ( int  i  =  0;  i  <  N;  ++i)

{

c[i] = new int[i  + 1];  c[i][0]  =  c[i][i]  =  1;

for(int j  =  1;  j  <  i;  ++j)

c[i][j]  =  c[i  -  1][j  -  one]  +  c[i  -  1][j];

}

//  Conclusion  tables

for(int  i  =  0;  i  <  c.length;  ++i)

{

for(int  j  =  0;  j  <  c[i].length;  ++j)  System.out.print("\t"  +  c[i][j]);

System.out.println();

}

}

}

# 2. Operations  and  operators

2.1. General characteristics of operations.  Most Java Operations  are similar to C++ operations, although some of them function  a little differently. Since there are no pointers in Java, it is natural to  There are no operations for taking an address ( & ), dereferencing ( * ) and  indirect addressing ( –> ). Operation . ("dot") in Java is used for  accessing fields and methods of objects through object references (more  detail  cm.  P.  [3.3](#part0005.xhtml__bookmark20) ).

The following paragraphs describe basic Java operations. Priori-  theta  operations  given  in  tab.  [2.1](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) .

2.2. Arithmetic operations. Arithmetic includes the following  blowing  operations:  unary  operations  conservation  and  changes  sign  ( + and - ); unary increment and decrement operators ( ++ and –– ); binary  nye operations of addition, subtraction, multiplication, division and finding  remainder  from  division  ( + ,  - ,  * ,  / ,  % ),  a  also  operations  with  assignment  ( += ,

–= ,  *= ,  /= ,  %= ).Arithmetic operations apply to numeric types and have  the result is also a numeric type. Division operation for integers  types gives the result of integer type (incomplete quotient), for ve-  natural  —  real.If, when performing operations in integer arithmetic,  comes out  overflow,  then  one  or  some  senior  bits  result  can be truncated (at the same time, since the most significant bit is responsible for the sign  numbers,  possibly  change  sign)  without  generation  messages  about  error.  The only operation in integer arithmetic that results in  mistake,  is an  operation  division  on the  0.At  implementation  operations  in  real  arithmetic  mistake  not  arises  never:  at  overflows  and  division  on the  zero  re-  result  receives  one  from  special  values  NaN  ("not  number"),  Infinity  ("plus  infinity"),  –Infinity  ("minus  infinity").  At  If necessary, they can be obtained by referring to the NaN constants ,  POSITIVE_INFINITY , NEGATIVE_INFINITY respectively in classes  Float and Double . For example, the result of evaluating the expression -3.0f/0.0f  equals  Float.NEGATIVE_INFINITY ,  a  result  calculations  expressions  0.0/0.0  equals  Double.NaN .

| 1.() | [] | . |  |
| 2.++ | –– | ~ | ! |
| 3.*4.+ | /– | % |  |
| 5.<< | >> | >>> |
| 6.< | > | <=>= |
| 7.== | != |  |
| 8.& |  |  |
| 9.^ |  |  |
| 10.&#124; |  |  |
| 11.&& |  |  |
|  |  |  |  |

2.3. comparison operations. Comparison operations include operations  radios == , != , < , > , <= , >= . Their only difference from the corresponding  The most common C++ operations is that their result is always of type  Boolean .

2.4. brain teaser  operations.  brain teaser  operations  apply  to  ar-  arguments of type Boolean and produce a result of type Boolean . to logical  include: unary operation of logical "not" ( ! ), binary operations  logical  "and"  ( && ,  & ),  "or"  ( | ,  || )  and  "exclusive  or"  ( ˆ ) ,  a  also  similar  operations  with  assignment  ( &= ,  |= ,  ˆ= ).

Operations && and || calculate the value of their second argument  only  in  volume  case,  if  result  impossible  define  on  meaning  first. In contrast, the operations & and | always calculate values  both  their  arguments.  For example:

int x = 10,  y = 10;

if(x == 10 || ++y == 10)  System.out.println(y);

prints  "ten",  So  as  second  argument  operations  ||  not  is calculated.  If a  replace  ||  on the  | ,  result  work  will  "eleven".

2.5. conditional operation. Java has a similar C++ conditional  operation  ?: .  Her  syntax: If the condition is true, then the result of this operation is the expression expression1 , otherwise expression2 . In this case, an expression that is not re- the result of the operation is not evaluated. It is significant that in Java the condition must have type  boolean (cm. also P. [2.7](#part0004.xhtml__bookmark16) ).

2.6. The assignment operator and the expression operator. All opera-  Java language statements (as in all other languages) have a return value  chenie. However, other than that, they are (as in C, C++, but not in other languages)  may also change their operands. Such operations include  operations  ++ ,  –– ,  =  and  all  operations  with  assignment.  By  this  reason there is no assignment operator in C, C++ and Java , but there is an operation  assignments  and  expression operator .

The assignment operation is a binary operation that is assigned  Gives the value of its second argument to the first. First argument  operations  assignments  should  be  lvalue ,  t.  e.  "allowing  assigned  ing". The result of an assignment operation is equal to the value of its second  argument.  For example,  next  operation

x  =  y  =  ten

assigns the value 10 to the variable y , after which the  result  this  operations  (t.  e.  ten)  assigned  variable  x .

expression operator  It has  syntax:

expression ;

Thus, adding a semicolon to any expression pre-  rotates  his  in  operator,  a  possibility  unite  in  one  express-  nii multiple operations allows one operator to change at once  multiple variables, which is not possible when using the operator  assignments.

Unlike C++, Java has an additional requirement that  the last operation included in the operator-expression changed its  operands,  t.  e.  requirement  absence  useless  code  (code  having  no  effect)  in  program.  For example,  operator

x + 1;

is valid in C++ and invalid in Java because it is not  changes  values  none  variables.

2.7. flow control statements.  To the control operators  current include: conditional statement if , selection statement case , operator  ry  cycles  while ,  do - while  and  for ,  operators  early  exit  from  cyclebreak  and  transition  to  next  iterations  continue ,  a  also  operator  you-  move from the return function . The syntax of these operators is similar to C++ with  small  modifications. AT in particular all operators, performing verification conditions, required ut that the condition had type boolean . This means that, unlike C++, the if (n) and if (n != 0) constructs are not equivalent, and the first one is lyatsya syntactically wrong, if variable n It has type, a great from  boolean . for statement , just like in C++, it is possible to declare variables nyh. for example

for ( int  i  =  0;  i  <  N;  ++i)

Variables declared in this way are only valid inside  cycle. You can use multiple expressions in the header of an operator  ra  for ,  dividing  them  commas:

![](Images/image00479.jpeg)for (i  =  0,  j  =  0;  i  +  j  <  20;  ++i,  ++j)

The control expression in the case statement must be one of  integer  types.

Java does not contain a goto statement . Instead, there are extensions  break statements  and continue to exit  from multiple nested loops. They are not very common and therefore  here  not  are considered.  It is important to note that the presence of inaccessible code in the program (on-  example, code following a return statement ) is prohibited in Java and  leads  to  mistake  compilation.

# 3. Classes  and  objects

3.1. Main  concepts  object-oriented  program-  roving. The Java programming language supports the paradigm of  project-oriented programming (OOP). Central  The concept of OOP is the concept of a class. A class is a data type defined  shared by the user. The class can contain fields (variables) and  methods (functions). Variables of type "class" are called objects  (or class instances ). Each object has its own  kit  copies  fields,  certain  in  class.  Content  fields determines the state of this object at any given time . Method-  das exist in one instance for each class, however the call  any (non-static) method can only be carried out with the specified  class object. Typically, this method processes the fields  exactly  Togo  instance  class,  on the  which  is he  called  (changes  his condition). Thus, class methods determine the behavior of all  objects of this class. It is very important to note that neither fields nor methods  class  not  exist  themselves  by oneself  outside  objects  of this class .

The concept of a class can be viewed as a development of the concept of a structure  ry  language  c,  at  which  functions,  processing  data,  posted-  nye in structures are placed inside these structures. At the same time, the medium  properties of object-oriented programming languages allow  deny access to object data from the outside and process  data  only  through  methods.  AT  this  case  they say,  what  methods  class  provide  interface  to  his  data .

The previous presentation describes the concepts of class and object with the technical  technical side, from the point of view of the means of the programming language.  However, another interpretation can be given. A characteristic especially  object-oriented programming versus  early  paradigms  (structural  programming)  is an  then,  that the programmer gets the opportunity not to select language environments  stva for expressing the mechanisms of data processing of the subject area  sti, but to model the subject area within the program. objects  in the program in this case correspond (in most cases)  objects of the subject area, and classes - universal concepts of pre-  marked area, characterizing the properties and behavior of the same type  objects.  Such  an approach  to  programming,  as  rule  is and more efficient (especially when developing large software  complexes,  a  also  at  collective  development),  insofar as  pro-  grammarian  receives  possibility  describe  interaction  objects  in the language of the subject area, and not in the language that reflects the internal  details  work  computing  cars.

3.2. Class declaration. The following is used to declare a class:  blowing  syntax:

[  access spec  ]  class  class name

{

[  access spec  ]  data type  fieldname  [  =  initial_value  ];

[  access_spec  ]  datatype  method_name ( argument_list )

{

method_body

}

}

The order in which fields and methods are declared in a class can be  free. Possible access specifiers are described in [3.10](#part0007.xhtml__bookmark27) . Here-  difference  from  C++  announcement  class  and  his  implementation  are placed  in  one  and  volume  same  file.

The constructor has the same name as the class name and does not have  return value. If the class constructor is not explicitly declared, then  created  empty  constructor,  not  having  arguments  (constructor  on  by default).If a class has two methods with the same name, then  such methods are called overloaded . Selecting the required re-  loaded method is carried out by the compiler based on the number of  The number and type of arguments passed to the method. It is not allowed to define  division of two methods with the same signatures (a signature is called  etsya  totality  name  method  and  types  his  arguments),  So  as  in  this  case  compiler  not  will be able  define,  which  from  methods  should  you-  call.Default arguments are not supported. If such a possibility  required, then you should explicitly implement the methods with all the necessary  smoke  sets  arguments.

Java does not allow code outside of classes, i.e. there are no non-local  variables that are not fields, and there are no functions in the sense  C++.

3.3. Creation of objects. In Java, all objects are created dynamically.  skoy  memory  virtual  cars.  variable-objects  in  volume  sense,  in  what  they  there is  in  C++,  in  Java  not  exist,  a  variables,  type  cat-  ryx (syntax) is some class, in fact are  not objects, but references to these objects (object references). On the-  example

MyClass  myObject;

This declares an object reference of type MyClass named myObject  and  not  created  myself  an object  (in  C++  analogue  given  ads  would-  for a pointer declaration: MyClass* myObject). The actual creation  object  carried out  with  help  operations  new :

myObject  =  new  MyClass();

An object of type MyClass is created here (on creation, the end  constructor with no arguments), and a reference to it is written to a variable  myObject .  Maybe  simultaneous  announcement  object  links  and  her  initialization:

MyClass  myObject  =  new  MyClass();

3.4. Access to fields and methods. Once the object has been created, access to  his  fields  and  methods  carried out  through  operations  .  (dot):

myObject.someMethod();

When accessing a field or method of an object from a method called  on the same object, the name of the object can be omitted or replaced the this keyword . The this keyword is also used to  call  constructor  class  from  another  constructor  (cm.  example  below).  In the latter case, such a call must be the first statement  constructor.

3.5. Example. As an example, consider the class Box ("box"),  storing the dimensions of some box (three integers). Content class  lives overloaded constructors with different arguments, as well as  the volume() method , which calculates the volume of the box. SimpleBoxDemo class de-  monsters  creation  and  usage  copies  class  box . To simplify the example, access control (see [3.10](#part0007.xhtml__bookmark27) ) is not used. In practice, this approach should not be used by any when!

/** Class  "Box" */

class  box

{

/**  Dimensions  drawer  */

int  width,  height,  depth;

/**  Constructor  on  default  */

Box() { width = height =  depth = 0; }

/**  Basic  constructor  */

Box( int  width,  int  height,  int  depth)

{

this.width  =  width;  this.height  =  height;  this.depth  =  depth;

}

Box(int  size)

{

this (size,  size,  size);  //  width  =  height  =  depth  =  size;

}

/**  Method  calculations  volume  */

int  volume()  {  return  width  *  height  *  depth;  }

}

public  class  SimpleBoxDemo

{

static  void  main(String  args[])

{

Box  b1  =  new  Box(5),  b2  =  new  Box(5,  10,  20);  b1.width  =  10;

System.out.println(b1.volume()  +  "\n"  +  b2.volume());

}

}

3.6. Removal  objects.  Operation  removal  objects  in  Java  not  warning  looked.  Her  replaces  mechanism  automatic  assembly  garbage.  For  ensure  work  this  mechanism  JVM  (virtual  the car  Java) keeps track of the number of object references to each created object ect and, as soon as there is no reference left to the object, it becomes candidate on the removal. Samo removal objects carried out peri- odically and only in the case when the amount of memory that needs Destructors are not provided in Java. Since the release of memory  ty implements the JVM, then the need for them arises not too  often. If they are still needed, you should define your own methods.  toda and call them explicitly. An example here is the close() method  in-line  classes  Java,  exercising  closing  flow  I/O

3.7. Static fields and methods.  Static Fields and Existing Methods  exist in a single instance for each class, that is, they are  shared  for  all  copies  this  class.

To declare static fields and methods, a special  fikator  static :

static  int  static_field  =  ten;

Static fields are initialized at class load time, either  the value specified in the declaration (see the example of paragraph [3.5](#part0005.xhtml__bookmark22) ), or in a special  real  static block.

Static methods cannot (without explicitly specifying an object)  say goodbye  to  non-static  fields  and  non-static  methods  class.

Call  static  fields  and  methods  maybe  carried out  without  decree-  instance of a class. In this case, instead of the instance name  used  name  most  class.  For example:

double  x  =  Math.sqrt(2.0);

Method  main() ,  which  is an  dot  entrance  in  java program  all-  where  should  announce  static  (cm.  example  P.  [3.5](#part0005.xhtml__bookmark22) ).

3.8. Broadcast  arguments  methods  and  peculiarities  use  object links. An object reference behaves like a pointer in C,  so assigning one object reference to another does not result in  copying an object. To perform copying of objects in a class  usually  implemented  constructor  copies  and,  possibly,  method  clone() .

Primitive types are passed to methods by value .  This applies to object references as well, so the objects themselves are passed  are  on  link  (similar  copying  pointer  in  C).

Let's consider a typical mistake when using object references.  lok.  Let be  available  Class  "dot  plane"  co  next  implementation:

class  point

{

public  double  x,  y;

public  Coords(double  _x,  double  _y)

{

x  =  _x;  y  =  _y;

}

}

Let it be required to implement a method that performs the exchange of two objects.  projects  class  point .  Insofar as  objects  transmitted  on  link,  natural-  Noah  maybe  seem  next  implementation

static void  swap(Coords  c1,  Coords c2)

{

//  This  implementation  wrong!

Coords s = c1;  c1  =  c2;

c2  =  s;

}

However, this implementation is incorrect because it  Dit exchange copies of references to objects to be exchanged. Insofar as  copies are local variables, they are destroyed when  output  from  method.

Faithful  implementation  (implemented  in  form  method)  should  exchange-  vat  content  objects,  a  not  links  on the  them:

static void  swap(Coords  c1,  Coords c2)

{

double  s;

s  =  c1.x;  c1.x  =  c2.x;  c2.x  =  s;  s  =  c1.y;  c1.y  =  c2.y;  c2.y  =  s;

}

Finally,  we note  what  with  points  vision  object-oriented  the  programming  preferred  is an  decision  given  behind-

dachas,  formalized  in  form  method  most  class  point .  Example  such  implementations:

void  swap(Coords  c)

{

double  s;

s  =  x;  x  =  c.x;  c.x  =  s;

s  =  y;  y  =  c.y;  c.y  =  s;

}

Here  going on  exchange  content  object,  on the  which  called  method  swap() with another object passed to this method as an argument  cop. Note that this implementation does not provoke the programmer  use  described  higher  incorrect  an approach.

3.9. Packages and structure of the translation module. Packages are  means of grouping types (classes and interfaces) in Java programs  me. Each package may contain one or more classes and  interfaces, as well as other packages. Distribution of classes by packages  allows you to solve the problem of name conflicts, as well as more efficient  but  realize  control  access.

To refer to the elements of the package, the full path is used,  consisting of a set of subpackages separated by dots (e.g. java.  util.HashSet ). To refer to classes in the same package, you can  use  simply  them  names,  omitting  name  package.

The translation unit in Java is a file. Each trans-  An expression may begin with a package statement that defines a package,  to whom  belong  classes,  described  in  given  module.  For example,

![](Images/image00479.jpeg)package  mypackage.mysubpackage;

If a  package -statement  is absent,  then  counts,  what  Class  belong-  lies to a default package that has no name, cannot have  sub-packages  and  not  is an  visible  from  others  packages.

A translation module may contain one or more imports -  statements that allow package names to be omitted when referring to  classes.  For example,  if  in  module  broadcasts  present  line

![](Images/image00479.jpeg)import  java.util.*;

then to all classes of the java.util package (but not to the classes of its subpackages!)  can  will  address  on  short  names  ( HashSet  instead of  java.util.  HashSet  and  t.  d.).  Maybe  and  importing  single  class  package,  For example:

![](Images/image00479.jpeg)import  java.util.HashSet;

The translation module must contain the source text  main  class  (or  interface)  module.  Name  this  class  should-  but match the name of the translation module file. This class is  the only translation module class that can be declared  linen  open  ( public ,  cm.  P.  [3.10](#part0007.xhtml__bookmark27) ).  Module  broadcasts  maybe  contain  also  one  or  some  auxiliary  classes.Search  files,  containing  bytecode  classes  carried out  in  subdirectories corresponding to the location of the classes in the hierarchy  packages,  inside  directories,  listed  in  variable  environment ..

CLASSPATH .

For example,  for  Togo  to  JVM  found  bytecode  class  java.util.  HashSet , it must be in a file named HashSet.class in a subdirectory  log  java/util  any  catalog  variable  environment  CLASSPATH .  As a rule, it includes the current directory, as well as the directory containing  pulling standard Java libraries. Source files are usually  are also located in the file system in accordance with the hierarchy  packages.

3.10. Access control and encapsulation.  Access control  is used in order, on the one hand, to prevent unauthorized  tsionirovannoe change of data contained in the objects, as a result of  misuse or malicious use, and on the other hand  rons to separate the class interface from its implementation (hiding  implementation). The programmer using the class sees only its in-  interface (fields and methods with public access) and may not know anything  about the internal structure of the class. The latter allows you to change the real  lization of a class is transparent to the programmer. For example, you can replace  thread the implementation of a more efficient, completely restructuring the internal  it is a class device, and the program code using the class,  will  without  changes  work  with  new  version  class.

Placing fields and methods inside classes along with hiding  implementation is called encapsulation . Encapsulation is a characteristic  thorns  trait  object-oriented  programming.

Access control is carried out by setting certain  access specifier in the description of classes, fields and methods. AT  Java  exist  two  specifier  access  for  classes  and  four -  for fields and methods. All of them, together with scopes, correspond to  existing  elements  programs  listed  in  tab.  [3.1](#part0009.xhtml__bookmark28) ,  [3.2](#part0009.xhtml__bookmark29) .  Levels

| Region  visibility | private | on  default | protected | public |
| that  same | that  same  Class | + | + | + | + |
| package |
| another  Class | - | + | + | + |
| another | subclass | - | - | + | + |
| package |
| not  subclass | - | - | - | + |
|  |  |  |  |  |  |

Table  3.1.  Levels  access  fields  and  methods

| Region  visibility | on  default | public |
| that  same  package | + | + |
| another  package | - | + |

Table  3.2.  Levels  access  classes  and  interfaces

access  are designated  their  specifiers  Besides  level  access

"default", which does not have any special specifier  matches.

Here are some guidelines for using control  access  in  Java programs.The main thing  rule  management  access:  at  designing  for  all  elements of the program should be set to the most limited level  access vein that allows these elements to function correctly  vat . The less classes know about each other, the more likely they are to  have  be  used  again.

Class fields use private access . To read and change  to change their values from the outside, special methods are used (setters and  getters),  having  specifier  access  public .  For example,

class  MyClass

{

private  int  value;

public  void  setValue(int  value)  {  this.value  =  value;  }

public  int  getValue()  {  return  value;  }

}

This approach is quite flexible. For example, you can always  make a certain field a read-only field by deleting or simply not re-  by aliasing the appropriate setter, or by limiting the possible values  for  fields,  inserting  relevant  check.

Methods  class,  having  specifier  access  public ,  form

interface  to  data  this  class.  Only  through  these  methods  externalclasses will be able to access the data encapsulated by the class, and  only  they  determine  possible  ways  processing  these  data.

In the presence of inheritance (see clause [4.1](#part0012.xhtml__bookmark34) ), access specifiers of element  cops private and "default" are often replaced by a specifier  protected to allow class descendants to access the appropriate  corresponding class elements. It is also possible to use access  by default, if the entire descendant hierarchy is in the same folder  kete,  what  and  inherited  Class. Default access can be used to create friendly  private classes that can access private fields and local  todam each other. Such friend classes are placed in one  package. Access control capabilities in this case are more flexible than in  case of friend classes in C++. However, to abuse this  possibility is not recommended, since friend classes are  are said to be more strongly related to each other than ordinary ones, so  changes in one class may require major changes in  others.

3.11. Example. Consider as an example the class "stack of integers  numbers"  co  next  implementation:

/**  Class  "stack  whole  numbers"  */

public  class  IntStack

{

private  final  int  MAXLEN  =  64;  //  maximum  the size  stack

private  int  s[],  size;

/**  Constructor  on  default  */

public  IntStack()

{

size  =  0;

s  =  new  int [MAXLEN];

};

/ **  Constructor  copies  * /

public  IntStack (IntStack  stack)

{

size  =  stack.size;

s = new int [MAXLEN];  for ( int  i  =  0;  i  <  size;  ++i)

s[i]  =  stack.s[i];

}

/**  Receipt  size  stack  */

public  int  getSize()  {  return  size;  }

/**  Recording  element  in  stack  */

public  void  push( int  e)  {  s[size++]  =  e;  }

/**  Receipt  element  from  stack  */

public  int  pop()  {  return  s[––size];  }

/**  Examination  stack  on the  emptiness  */

public  boolean  isEmpty()  {  return  size  ==  0;  }

}

The state of the stack is determined by its current actual size  size and the content stored in the s array . For the field size is defined  getSize() method to get the current stack size. Nepo- there is no means of accessing the array s . Appeal to him can lead to  be available only through the methods push() , pop() , isEmpty() , which in  combination with the getSize() method and two class constructors define  share an interface to stack data. Note that, in order to  to use a class, you only need to have the signatures of these methods and  description of what operations they carry out. Internal details  implementations in this approach are hidden and can be easily changed  neny. For example, you can replace the array s with a doubly linked list, and this is  no way  not  will be reflected  on the  classes  using  Class  IntStack .

3.12. Comparison  objects. Standard  operation  Java  ==  wasp-  compares object references . However, as a rule, it is required  etsya  comparison  objects  not  on  links,  a  on  them  content .  For  this  intended  method

![](Images/image00479.jpeg)boolean equals(Object  obj)

defined in the Object class (see section [4.1](#part0012.xhtml__bookmark34) ) and therefore contained in all  classes  Java.  Implementation  this  method  on  default  functioning  So  the same as the == operator , i.e. it compares object references. Programmer  should  redefine  this  method  So,  to  is he  carried out  comparison  in the required way. For example, for the class Coords ("point of the plane"),  containing two integer coordinates x and y , corresponding to  method  can  implement  next  way:

public  boolean  equals(Object  obj)

{

if(!(obj  instanceof  Point))

return false;  Point  c  =  (Point)obj;

return  x  ==  c.x  &&  y  ==  c.y;

}

If a  in  program  are used  standard  container classes  (see [section 8.1](#part0028.xhtml__bookmark66) ), it is usually necessary to override not only the equals() method ,  then  also  method

![](Images/image00479.jpeg)int  hashCode()

which  returns  hash code  object.  Hash code  object  —  This  whole  a number that is calculated based on the state of the object (contain-  bench press  his  fields).  Equal  objects  (t.  e.  objects,  for  which  method  equals() returns true ) must match the same  same hash code. For unequal objects, hash codes need not be unequal.  nym, however, this should be strived for. In addition, one should take into account  that the more uniform is the distribution of hash codes  objects, the better will be the performance of built-in collections,  them  using  (sets  and  associative  arrays).

For  reviewed  higher  class  point  can  define  method

hashCode()  next  way:

int  hashCode()

{

return  x  +  y;

}

3.13. Wrappers of primitive types. As already noted, change  The primitive types in Java are not objects. In some  cases, however, it is required to represent them as objects (for example,  for storage in containers, see [section 8.1](#part0028.xhtml__bookmark66) ). For this, they are used as  called wrappers of primitive types - classes that encapsulate  primitive  types.

For each of the eight primitive types, a corresponding  a wrapper class that gives it. When creating instances of these types, the wrapper  tyvayuschy  an object  transmitted  in  constructor  relevant  class:

Byte(byte value)  Short(short  value)  Integer(int  value)  Long(long  value)  Float(float  value)  Double(double value)  Character(char value)  Boolean(boolean  value) Also, all wrapper classes except Character have constructors  with  argument  type  String .  They are  carry out  transformation  lines  to the corresponding primitive type and wrap the resulting  result. All  wrapper classes  redefine  methods  equals() ,  toString()

(cm.  P.  [3.12](#part0010.xhtml__bookmark31) ),  a  also  implement  interface  Comparable<T>  (cm.  P.  [8.4](#part0029.xhtml__bookmark71) ).

To perform the reverse conversion from wrapper objects to  primitive  types  are used  methods

byteValue ()  short value()  int  intValue()

.  .  .

called on the corresponding objects. Starting with Java version 1.5,  most of these transformations are done automatically. All  wrapper classes  are  immutable  (immutable).

Wrapper classes  contain  also  static  methods

static byte parseByte(String s)  static short parseShort(String s)  static  int  parseInt(String  s)

.  .  .

which  may  used  for  transformations  lines  to  accept-  active types. If the conversion fails,  thrown out  exception  type  NumberFormatException .

# 4. Inheritance  and  polymorphism

4.1. Inheritance.  Inheritance is  mechanism  building  but-  new classes based on existing ones. At the same time, the heirs of the class  ca ( subclasses ) get the properties and functionality of the parent class  ( superclass )  and  have  possibility  change  and  expand  them.  Mechanism  inheritance is used to create more private, specialized  bathrooms  classes  on  comparison  with  superclass.

For  Togo  to  announce  Class  heir  some  another class, the extends keyword is used followed by the name  inherited  class,  added  in  announcement  class:

![](Images/image00479.jpeg)[  access_spec  ]  class  subclass_name  extends  superclass_name

Java only allows inheritance from one class. Subclass  inherits all fields and methods of the superclass, however, those that are  are declared with access specifiers private and by default (by default  the latter only if the subclass is outside the package containing the subclass  first class),  turn out  inaccessible  for  subclass.

The subclass can override the fields and methods of the superclass. In that  case, access to parent fields and methods is closed and may  be carried out only from subclass methods through the key  word super , the syntax of which is the same as that of the explicit  accessing the elements of the current instance via this . For example, follow-  The following code snippet shows a call to the superridenMethod method .  class  from  of the same name  method  subclass.

public  void  overridenMethod()

{

super.overridenMethod();

//  .  .  .

}

At  redefining  fields  and  methods  possibly  change  specificity  Torah  access  on the  more  wide  ( private  on the  any  another;  on  default  on the  any  another,  Besides  private  and  t.  d.).

Constructors are not inherited, but subclass constructors are required.  necessarily  cause  constructors  their  superclasses.  Last thing  maybe  occur explicitly (for this, the first statement of the constructor must  be  call  constructor  superclass  through  super )  or  implicitly  (in  thiscase  going on  call  constructor  on  by default).  Call  design  tori  parental  classes  going on  above  down  on  tree  inherited  vanity. AT  next  example  on the  basis  class  "box"  created  more  special  a cialized "weight box" class that adds additional  a tangible field "weight" and a method for obtaining it, and also uses you  calls  designers  superclass.

/** Class  "Box" */

class  box

{

/**  Dimensions  drawer  */

protected  int  width,  height,  depth;

/**  Getter 's */

public int getWidth() { return width; }  public  int  getHeight()  {  return  height;  }  public  int  getDepth()  {  return  depth;  }

public  Box(int  w,  int  h,  int  d)  {  width  =  w;  height  =  h;  depth  =  d;  }

/**  Constructor  for  Cuba  */

public  Box( int  size)  {  this (size,  size,  size);  }

/**  Method  calculations  volume  */

public  int  volume()  {  return  width  *  height  *  depth;  }

}

/** Class  "Box with  weight"  */

class  BoxWeight  extends  box

{

/**  The weight  drawer  */

protected  int  weight;

/**  getter  for  weight  */

public  int  getWeight()  {  return  weight;  }

/**  Basic  constructor  */

public  BoxWeight( int  w,  int  h,  int d,  int  wg)

{

super (w,  h,  d);  weight  =  wg;

}

/**  Constructor  for  Cuba  */

public  BoxWeight(int  size,  int  wg)

{

super(size);  weight  =  wg;

![](Images/image00481.jpeg)}

}

If the class description does not define a superclass for it, then  default  produced  inheritance  from  library  class  object .  This  Class  is  yourself  root  hierarchy  inheritance  in  Java  and contains the methods necessary for the correct functioning  jvm,  a  also  methods,  performing  such  common  operations,  as a conversion to a string (clause [6.3](#part0022.xhtml__bookmark51) ), comparison of objects for equality  (P.  [3.12](#part0010.xhtml__bookmark31) )  and  t.  d.

4.2. Limitation  and  forcing  inheritance.  If a  method  volume is declared with the final specifier , then its redefinition is prohibited.  If a  same  co  specifier  final  announced  Class,  then  prohibited  inherited  ing  from  such  class.

Individual class methods can be declared abstract. AT  in this case, they are declared with the abstract specifier and do not have  bodies:

![](Images/image00479.jpeg)abstract  void  abstractMethod();

Such  methods  should  necessarily  redefine  in  subclasses.  If a  class contains at least one abstract method, it must also  be declared abstract. In this case, the creation of an object is prohibited.  objects of this class. To be able to instantiate  subclasses of such a class, all abstract methods should be implemented in them.  superclass todas. If the subclass does not implement all abstract methods  superclass,  is he  also  should  announce  abstract.

4.3. Polymorphism.  Polymorphism is  mechanism,  which  let-  Allows you to refer to objects inherited from the same class as  objects of this class. With this access to objects of subclasses  they react in the manner defined in the corresponding subclass  se, not in the parent class. In this case, the methods defined in  superclass, form a single data access interface for all sub-  classes . Polymorphism is one of the most powerful means of  project-oriented  programming,  insofar as  is he  allows  uniformly process sets of objects belonging to different  classes, and the choice of the implementation of a particular operation is  happens  automatically  on the  basis  type  data  object. Implementation polymorphism in Java founded on the next rules.

1. A reference to a class object can be cast to a reference to an object  an object of any of the classes above the given one in the hierarchy  inheritance. This transformation is expanding and can be  can be done automatically. The reverse transformation is  same  maybe  be  produced,  but  it  performed  always  obviously.  At  attempt to cast an object reference to an invalid type  no error. To check the admissibility of the transformation,  zhet  be  used  operation  instanceof :

![](Images/image00482.jpeg)if(myObject instanceof MyClass)  ((MyClass)myObject).doSomethingSpecificForMyClass();

2. If some of the superclass methods have been overridden in  subclass, then when accessing these methods, even through  references to the superclass object will be called exactly  overridden methods . This differs from the implementation of poly-  morphism in C++, where the call to overridden methods in  described situation will occur only if  relevant  methods  were  announced  virtual. Consider an example. Let there be a base class "geometric goura." He contains method  area() , designed for calculations plo- spare the figure. Each of the subclasses of the "shape" class overrides this method in such a way that the area of the corresponding cabbage soup figures. Links to created instances of classes of specific figures are are stored in an array of links of type "shape", and then unified processed differently: for each figure, its area is displayed. At this does not require any shape type checks, for each shape automatically called required method.

3.  

/**  Abstract  Class  "Geometric  figure"  */

abstract  class  figure

{

/**  Method  calculations  area  figures  */

abstract  public  double  area();

}

/**  Class  "Rectangle"  */

class  Rectangle  extends  figure

{

private  double  a,  b;

public  Rectangle(double  a,  double  b)  {  this.a  =  a;  this.b  =  b;  }

public  double  area()  {  return  a  *  b;  }

}

/**  Класс  "круг"  */

class  Circle  extends  Figure

{

private  double  r;

public  Circle(double  r)  {  this.r  =  r;  }

public  double  area()  {  return  Math.PI  *  r  *  r;  }

}

/**  Class  "triangle"  */

class  triangle  extends  figure

{

private  double  a,  b,  c;

public  Triangle( double  a,  double  b,  double  c)

{

this.a =  a;  this.b  =  b;  this.c  =  c;

}

public double area()

{

double  p  =  (a  +  b  +  c)  /  2;

return  Math.sqrt(p  *  (p  –  a)  *  (p  –  b)  *  (p  –  c));

}

}

public  class  FiguresPolymorphism

{

public  static  void  main(String  args[])

{

figure  f[]  =  new  Figure[3];  //  array  objective  links

f[0] = new Rectangle(2, 3);  f[1]  =  new  Triangle(3,  4,  5);  f[2]  =  new  Circle(1);

for(int  i  =  0;  i  <  f.length;  ++i)  System.out.println(f[i].area());

}

}

4.4. interfaces.  AT  Java  not  allowed  inheritance  one  class  from  several.  However  exist  limited  analogue  multiple-  foot  inheritance  in  form  multiple  implementation  one  class  several  interfaces .  functional  interfaces  close  to  abstract-  nymph  classes  with  certain  restrictions  (allowed  only  abs-contractual  methods  and  only  static  fields),  but  any  Class  mo-  zhet  implement  (analogue  inheritance)  some  interfaces.

For  ads  interface  used  next  syntax:

interface  interface name  [  extends  list_of_interface_ancestors_names  ]

All  methods  interface  implicitly  receive  specifier  abstract  public , and all interface variables are the final static public specifier and must  us  be  straightaway  same  initialized.  Usage  others  specific  kators  access  in  interfaces  not  allowed.

Any  Class  maybe  implement  any  amount  interfaces.  For  ads  class,  implementing  one  or  some  interfaces,  is-  enjoys  next  syntax:

[  access_spec  ]  class  class_name  [  extends  superclass_name  ]

implements  list_of_interface_names

The elements of the list of interface names are separated by commas. If class  declared to implement some interfaces, it must either  implement all methods declared in these interfaces, or be  abstract.

4.5. Interface  links. Like  opportunities  casts  a reference to a class object to a reference to an object of its superclass,  it is possible to cast such a reference to a reference to any of  interfaces that the class implements. Such links behave absolutely  fiercely  likewise  links  on the  objects  abstract  classes.  For example:

interface  Ifc1

{

void  f();

}

interface  Ifc2

{

void  g();

}

class  MyClass  implements  Ifc1

{

public  void  f()  {  };

public  void  g()  {  };

}

public  class  InterfRef

{

public  static  void  main(String  args[])

{

MyClass  m  =  new  MyClass();

Ifc1  ir  =  m;  //  cast  to  interface  link

ir.f();  //  call  method  through  interface  link

 ((MyClass)ir).g();  //  reverse  transformation  to  link  on the  MyClass

}

}

4.6. Guidelines for Using Inheritance and Polymorphism  physics.  At  developing  hierarchy  classes  should  build  wood  inherited  dovaniya  in  accordance  with  principle:  subclass  is an  more  private,  specialized  class  on  relation  to  superclass .  non-compliance  Failure to follow this principle leads to serious design errors,  manifested in the strong coherence of classes, the non-obviousness of mutual  between them and the difficulty of designing for subsequent  stages.Despite the obvious similarity between abstract classes and interfaces,  owls, their purpose, generally speaking, is somewhat different. Ab-  a abstract class is an abstract entity, an entity,  the details of which are not fully described due to its generality. Unlike  interface class is not an entity, but rather a collection of potential  features that can be implemented by different classes,  not  having  between  yourself  nothing  general  Besides  these  opportunities. Inheritance supports polymorphism "genetically" general me- tods. Method polymorphism, which is of a different nature, must be implemented through interfaces. An example would be the  Comparable<T> interface (see Section [8.4](#part0029.xhtml__bookmark71) ). This interface can be re- alized by any class that allows its instances to be ordered ditch. AT then same time assumption about volume, what all objects, allowing comparison, must be subclasses of the same class looks invalid active.

# 5. Treatment  exceptions

5.1. Concept  exceptions.  Exceptions  present  yourself  volume  object-oriented mechanism for handling exceptional situations  tions during the execution of the program. This mechanism allows processing  vat  such  situations  more  simple  and  conceptually  clear  way  compared to traditional error handling methods such as  like returning special values or using the setjmp() functions  and  longjmp()  in  C.

Exception  —  an object,  which  thrown out  program  at  WHO-  exception. It usually encapsulates descriptions  sanation of this situation. The thrown exception catches some ob-  worker - a software block that processes exceptions  telny situation. After the execution of the handler, control is transferred  on the statement immediately following the handler. So  way  carried out  transition  from  one  parts  programs  in  another  with the performance of some special actions enclosed in the form  botchike  exceptional  situations.

5.2. Throwing and handling exceptions. In order for you-  quit  exception,  used  next  syntax:

throw  exception object;

Usually  exception object  created  directly  in  operator

throw ,  For example:

throw  new  NullPointerException();

The statement that throws the exception must be inside  ri special try block immediately followed by  handlers  exceptions:

try

{

exception-throwing-operators

}

catch (  exception_class_name  variable_name)

{

exception_handler_body

}

[  finally

{

operators

}

If some statement of the try block throws an exception, then all  further  operators  this  block  not  performed  and  starts  Search  handler whose header contains a type that matches the type  thrown exception object, or a type whose successor  (not necessarily immediate) he is. The search is carried out  on  next  rules:

  if the statement that threw the exception is not in a try -block  ke, then the method exits and the search continues.  bot in the calling method (this may be repeated several times)  times until one of the statements calling the method is in  block  try );  

the handler is searched among the catch blocks immediately following  shchih  behind  data  try -block;

  if  suitable  handler  not  located,  Search  continues  among catch blocks related to the enclosing try block, etc.  (at  this  also  maybe  take place  output  from  one  or  several  to their  methods);    if no suitable handler is found at all, an exception  catches the default handler, which prints a description of the  keys,  track  stack  and  completes  work  programs. If a  suitable  handler  found,  then  is he  will be fulfilled  and  the exception object is passed to the handler as an argument. By  At the end of the handler execution, control is transferred to the operator  torus immediately following all catch blocks that are  after  block,  processed  exception.

Subclass exception handlers must be present before they are handled.  superclass exception bots, since otherwise all such exceptions  the exceptions will be handled by the superclass exception handler and  arise  Not available  the code.

At  availability  block  finally  operators  this  block  performed  not-  depending  from  Togo,  It was  whether  exception  thrown out  or  No:

  if an exception occurred and was handled, the finally block you-  fills up  after  handler  exceptions;

  if  handler  not  was  found,  then  block  finally  performed  before  search  handler  in  including  block;

  if  output  from  try -block  was  completed  through  operator

return ,  then  block  finally  performed  before  way out  from  method.

5.3. Example. Consider an example that is an improvement on the  ra from paragraph [3.11](#part0010.xhtml__bookmark30) . This implementation of the "stack of integers" class performs  checking the correctness of actions performed with the stack, and throwing  vaet  exceptions  in  case  errors.

/**  Class  "stack  whole  numbers"  */

class  IntStack

{

private  final  int  MAXLEN  =  64;  //  maximum  the size  stack

private  int  s[]  =  new  int [MAXLEN],  size  =  0;

/**  Receipt  size  stack  */

public  int  getSize()  {  return  size;  }

/**  Recording  element  in  stack  */

public  void  push( int  e)

{

if (size  <  MAXLEN)  s[size++] =  e;

else

throw  new  Runtime Exception("Overflow  stack");

}

/**  Receipt  element  from  stack  */

public  int  pop()

{

if (size  !=  0)  return  s[––size];

throw  new  RuntimeException("In  stack  No  elements");

}

/**  Examination  stack  on the  emptiness  */

public  boolean  isEmpty()  {  return  size  ==  0;  }

}

public  class  IntStackExample

{

/**  Removal n  elements from the top  stack and output  them on the screen  */

static  void  pop And  Print(Int Stack  st,  int  n)

{

for ( int  i  =  0;  i  <  n;  ++i)  System.out.println(st.pop());

}

/**  Dot  entrance  in  program  */

public  static  void  main(String  args[])

{

IntStack  st  =  new  IntStack();

try

{

st.push(3);  st.push(5);  st.push(7);  popAndPrint(st,  4);

}

catch (RuntimeException  e)

{

System.out.println("Thrown out  exception:  "  +  e);

}

}

}

Method  main()  class  IntStackDemo  creates  instance  class  IntStack  and sequentially puts three elements into it, and then calls  method  popAndPrint() ,  which  trying  take off  co  stack  four  element.  When trying to remove the fourth element in the pop() method of the IntStack class  an exception is thrown. Since this method does not contain a block  try , then exits to the popAndPrint() method . This method is also not  contains  block  try ,  That's why  going on  output  and  from  this  method,  after  which causes the catch() statement of the main( ) method to handle the exception. Conclusion  this  programs:

7

5

3

thrown out  exception:  java.lang.RuntimeException:

 AT  stack  No  elements

5.4. Hierarchy  classes  exceptions  and  ejection  exceptions  from methods.  All exception objects in Java must belong to a class.  itself, inherited from the Throwable class , which has two subclasses:  Exception and Error . Exceptions of type Error are thrown by the JVM when  occurrence of serious errors. As a rule, the programmer should not  wives  neither  toss out,  neither  handle  such  exceptions.  All  rest exceptions are instances of the Exception class and its subclasses.  In addition, there is a special group of exceptions, represented by the class  catfish Runtime Exception and its subclasses. Because the Exception class  is an  superclass  all  custom  exceptions  for  Togo  what-  handle all thrown exceptions regardless of their types,  can  use  construction: catch(Exception e)

{

//  .  .  .

}

There is an important feature regarding exceptions, which is  which are instances of the Exception class and its subclasses, except for the class  RuntimeException  and  his  subclasses.  If a  such  exception  ejection-  from a method, then its type must be specified in the assertion.  research institutes  throws  in  header  this  method

[  access spec  ]  data type  method name ( argument list )

[throws  list_of_class_names_of_exceptions_thrown_by_method  ]

a  also  all  methods,  which  cause  such  methods,  but  not  about-  appropriate exceptions work. Otherwise, com-  the compiler will give an error message. This is done in order to  draw the programmer's attention to exceptional situations that  which require mandatory processing. In the standard library for  so  exceptions  relate:  mistakes  I/O  ( IOException )  database access errors ( SQLException ) and some other  gie. When throwing exceptions that are instances of a class  ca RuntimeException and its subclasses, no special declaration  tion is not required. In the library, these exceptions include:  key  at  implementation  unacceptable  mathematical  operations  ( ArithmeticException )  attempt  appeals  to  non-existent  element-  that of the array ( IndexOutOfBoundsException ), to a field or method of a non-  existing object ( NullPointerException ) and others. Such errors are  when should not occur in the correct program, at the same time  requiring mandatory processing would lead to clutter  source text (for example, the need to place each operation  walkie-talkie  division  inside  block  try during  avoid  mistakes  division  on the  zero).

# 6. Treatment  lines

6.1. String class. The String class is the main class for  significant  for  storage  and  processing  lines  characters.

For  creation  copies  class  String  maybe  be  used  one  from  next  constructors:

![](Images/image00483.jpeg)String()  String(String  str)

String(StringBuffer strbuf)  String( char []  arr)

String(char[]  arr,  int  first,  int  count)

The first of them creates an empty string, the second and third copy  contents of objects of classes String and StringBuffer into the created object.  The last two constructors allow you to create a string based on the symbol  free array or part of it. In addition, any object reference  of type String can be initialized by assigning  her  string  literal:

![](Images/image00479.jpeg)String  filename  =  "data.txt";

Perhaps a somewhat unexpected feature of the String class is  The rule is that instances of this class cannot be changed after  their creations (immutable). However, this does not create restrictions for their use.  use,  insofar as  all  methods,  which  should  were  would  change  string, just create a new modified string, leaving the  running  without  changes.  Let's explain  work  this  mechanism  on the  example:

String  s  =  "abcd";

s =  s.toUpperCase();

Here, the toUpperCase() method creates a new string containing the after-  sequence of characters "ABCD", and returns a reference to this string,  which is assigned to the variable s , the old value of the variable te-  rushes. The original string remains unchanged and, since  there are no more object references left, will be removed by the assembler  garbage.

Main  methods  class  String  given  in  tab.  [6.1](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) .

![](Images/image00484.jpeg)

int  length() Get  length  lines

char charAt( int  index) Extract  symbol

char []  toCharArray() Getting a string as a character  array

![](Images/image00485.jpeg)

Boolean  equals(String  str) Compare  lines  on the  equality  boolean equalsIgnoreCase(String str)               Comparison  lines  without  accounting  register  int  compareTo(String  str)               Lexicographic string comparison  int  compareToIgnoreCase(String  str)               Lexicographic  comparison  lines

without  accounting  register

boolean  startsWith(String  prefix)               Check,  starts  whether  line  with  behind-

given  substrings

![](Images/image00486.jpeg)boolean  endsWith(String  suffix)               Check,

ends  whether  line  behind-

given  substring

int indexOf(String subStr)

int  indexOf(String  subStr,

int  fromIndex)

int  lastIndexOf(String  subStr)

int  lastIndexOf(String  subStr,

![](Images/image00487.jpeg)int  fromIndex)

String  substring( int  beginIndex,

int  endIndex)

Search  first  occurrences  substrings

in the line from the beginning of the line / from the given  positions

Search  last  occurrences  sub-  ki  in  line  with  start  lines/s  given  positions

Receipt  substrings  (symbol  endIndex  not  included  in  substring!)

String  substring( int  beginIndex)               Getting  tail  lines  String  concat(String  str)               Concatenation  lines

String toUpperCase()  String  toLowerCase()

transformation  lines  to  top/  lower  register

String  trim() Remove  leading  and  final

gaps  in  line

| String  replace(String  target,  String  replacement) Metacharacter(s) | Meaning |
| \.&#124; | designation  special  symbol  or  shielding  ordinaryany  symbol,  Besides  limiters  lines  ("\n",  "\r"  and  etc.)choice  one  from  two  regular  expressions |
| [  ][ˆ]  [  -  ] | one  from  symbols,  incoming  in  given  kitone  from  symbols,  not  incoming  in  given  kit  one  from  symbols,  incoming  in  range |
| ˆ$ | sign  start  linessign  end  lines |
| *+?{ k }{ k ,}{ k , m } | zero  and  more  previous  symbolsone or more previous characters  zero or one previous character  smooth  k  previous  symbolsnot  less  k  previous  symbolsnot  less  k  and  not  more  m  previous  symbols |
| ( )\ k | grouping/saving  lines,  relevant  reg-polar  expressionsk -th  saved  Group |

Table  6.2.  Regular Metacharacters  expressions

6.2. Regular  expressions.  Regular  expressions are  express-  zheniya,  describing  structure  textual  lines  with  using  conventional  symbols  and  metacharacters ,  defining  properties  lines  as a whole or its individual parts. Standard Library Tools  Java allows you to check strings against a given  regular expression, as well as to replace substrings,  satisfying  regular  expressions,  others  substrings.

Basic metacharacters used in regular expressions in  Java are given in Table. [6.2](#part0020.xhtml__bookmark48) . Examples of regular expressions are given  in  tab.  [6.3](#part0022.xhtml__bookmark50) .

To check if a string matches a given regular expression,  zheniya  used  method

![](Images/image00479.jpeg)boolean  matches(String  regex)

class  String .  Note  what  insofar as  is he  checks  all  string  on the  co-  responsibility  regular  expression  then  usage  symbols  "ˆ"  and

"$"  in  this  case  unnecessarily.

| Regular  expression | Meaning |
| abc&#124;def  ac  https?://ˆa.*z$  [A–Z]+  [ˆ0–9]{5,}\.\.\.(.+)a\1 | character sequence "abc" or "def"  characters "a" and "c" separated by any character the character               sequence               "http://"               or"https://".line,  beginning  with  symbol  "a"  and  ending-  lingering  symbol  "z"non-empty  subsequence  uppercase  Latin  sky  letterssubsequence  not  less  how  from  five  symbolic  fishing,  not  being  figuressubsequence  symbols  ".  .  ."two  the same  substrings,  divided  symbol"a" |

Table 6.3. Examples of regular  expressions. The following methods replace the first and all occurrences, respectively.  nia  substrings ,  relevant  regular  expression:

String  replaceFirst(String  regex,  String  replacement)  String  replaceAll(String  regex,  String  replacement)

For example, the following statement replaces the ellipsis located  in  end  line,  interrogative  sign:

someString.replaceFirst("\\.\\.\\.$",  "?");

Since the character "." is a metacharacter, then in order to use  to use it as a regular character, it must be escaped  scrap  "\".  However  last  symbol  used  in  Java  for  designations  special characters (such as "\n"), so must also be escaped  roam:  "\\.".

In a replacement string, you can use the "$" metacharacter followed by  following number, denoting the corresponding group in the replacement  my prompt. For example, the following statement replaces the angle brackets in  line  square,  at  this  content  brackets  remains  the same:

someString.replaceFirst("<(.*)>",  "[$1]");

It should be noted that if a line contains several opening  shchih  and  closing  corner  brackets,  then  replaced  will  first  opening-  ing  and  last  closing,  insofar as  pattern  ".*"  corresponds  any number of any characters, including  all nested parentheses.

Method

String[]  split(String  regex)

allows you to split a string into substrings, using division to describe  divisors regular expressions. The result is written as a string  array.  For example,  operator

String[]  m  =  "abc:::de:f::gh".split(":+");

will fill  array  m  lines  "abc",  "de",  "f"  and  "gh".

In conclusion, we note that regular expressions seem to  are the most powerful tool for processing string data,  and their capabilities are much broader than it was possible to show on the  given examples. More information about

6.3. String conversion and concatenation operation. Class  String is in a sense an exclusive class in Java,  since any data type can be converted to it. For  primitive types, such a conversion gives them a natural structure representation, the toString() method is called for objects , defining  divided in class Object and therefore present in any  classroom  Java.

For  lines  determined  operation  concatenation,  denoted  sign

+ . This is a binary operation, one of whose arguments must have  type String . It performs automatic conversion  argument to String type (if needed) and merge the resulting  lines. Note that this is the only case when the transformation to  line is done implicitly. There is also a concatenation operation  assignment with += , whose first argument must be of type  String (and must be an lvalue ) and the second one can be arbitrary.  At  implementation  operations  is he  will  converted  to  type  String .

Let's give an example of using the conversion to a string and op-  concatenation radios. For the class "point of the plane" it is possible to define  operation  transformations  to  line  next  way:

class  point

{

private  double  x,  y;

public  String  toString()

{

return  "("  +  x  +  ",  "  +  y  +  ")";

}

public  Point(double  _x,  double  _y)

{

x  =  _x;  Y  =  _Y;

}

}

Here automatic conversion of double values to strings  is carried out in the expression of the return statement . Defined above  method  toString()  maybe  be  used  next  way:

![](Images/image00488.jpeg)Point p = new Point(2.0, 5.0);  System.out.println(p);  //  conclusion  on the  screen:  (2.0,  5.0)

For  Togo  to  get  and  withdraw  on the  screen  string  performance  object,  method  println()  causes  method  toString()  class  point .

Sometimes  required  manage  view  string  representation.  For  this  maybe  be  used  static  method  format()  class  String :

![](Images/image00479.jpeg)static String  format(String  format,  Object.  .  .  args)

It accepts a format string and a variable number of expressions  and  transforms  them  in  string  in  format,  certain  format  string.  The rules for writing a format string generally correspond to the rules  writing  format  lines  functions  printf()  in  language  C.  For example,

![](Images/image00479.jpeg)System.out.println(String.format("%04d%4.1f",  25,  3.58));

will bring out  "0025  3.6".

6.4. StringBuffer class.  The StringBuffer class is designed to work  with modified lines. Each object of this class contains  some  buffer,  storing  line.  At  changes  lines  the size  buffer  maybe  automatically  change.

how  rule  usage  objects  class  StringBuffer  in  program-  max  not  is an  necessary,  insofar as  all  those  same  operations  can  you-  complete using objects of class String . However, in some cases  the use of the StringBuffer class increases the efficiency of the program  we, since it allows us to avoid repeated copying of the modi-  fitted  lines.

To create instances of the StringBuffer class , the following are used :  ing  constructors:

![](Images/image00479.jpeg)StringBuffer()

![](Images/image00489.jpeg)

int  length() Get  length  lines

![](Images/image00490.jpeg)char charAt( int  index) Extract  symbol

char  setCharAt( int  index) Change  symbol

StringBuffer  append(String  str)

StringBuffer  append(int  i)  StringBuffer  append(Object  obj)

.  .  .

StringBuffer  insert(int  index,  String  str)

StringBuffer  delete(int  beginIndex,

int  endIndex)

StringBuffer  replace ( int  beginIndex,

int  endIndex,  String  page)

Addition  strings  k  the end  (existing

there are  overloaded  versions  for  all  primitive  types  and  type  object )

![](Images/image00491.jpeg)Inserting a string at a given position  Removal  substrings

Replacement  one  substrings  another

String Buffer  reverse( )  lines

Table  6.4.  Methods  class  StringBuffer

StringBuffer( int capacity)  StringBuffer(String  str)

The first two of them create an object that stores an empty string from the beginning.  buffer of length 16 in the first case and a given length in the second  case. The third constructor initializes the buffer with the given string.  The buffer size in this case is set to the length of the string,  increased  on the  sixteen.

Main  methods  class  StringBuffer  given  in  tab.  [6.4](#part0023.xhtml__bookmark53) .

AT  difference  from  methods  modifications  lines  class  String ,  similar  methods  class  StringBuffer  change  exactly  that  copy  object,  on the  which they are called. In doing so, they return a link to this  object ( this ). The latter was done in order to be able to combine  Take a set of sequential operations on a string into one expression  like  to that  as  This  made  in  standard  library  language  C:

StringBuffer  sb  =  new  StringBuffer("abc");  sb.append("ef").reverse();

System.out.println(sb);  //  displays  on the  screen:  fedcba

# 7. Input Output

7.1. I/O streams. Input/output in Java is  means  streaming  classes.  All  streams  are separated  on the  byte  and symbolic. Byte streams are designed to transfer binary  ny data, and character - text. To present information  tions  symbolic  streams  use  Unicode.  Streaming  library  Java is designed in such a way that data input/output is done  almost the same, regardless of sources and receivers  transmitted data. This feature is due to the fact that all  current classes are inherited from the same abstract classes,  determining the methods through which the interaction takes place  action of user applications with streams. Byto superclasses  output streams are the classes InputStream and OutputStream , char-  nyh - Reader and Writer . The main methods of these classes are listed in  tab.  [7.1](#part0026.xhtml__bookmark56) ,  [7.2](#part0026.xhtml__bookmark58) .

In case of I/O errors, the methods of the stream classes are chosen  throw an exception of class IOException or its subclasses (for example,  FileNotFoundException ).  Classes  these  exceptions  not  are  subclass  themselves of the RuntimeException class and therefore need to be obligatory  work.

![](Images/image00492.jpeg)Facilities  streaming  I/O  are placed  in

package  java.io .

void  write( int a ) throws IOException one  byte/character  in  flow

void  write( }  a)  throws  IOException               Write  content  from  array  in  on-

current

void  write( } []  a,  int  offset,  int  len)

throws  IOExceptionWriting the contents of a portion of an array to  flow

![](Images/image00493.jpeg)

void  flush()  throws  IOException               Reset  buffers  output,  related  with

![](Images/image00494.jpeg)flow

void  close()  throws  IOException               Closing  flow

Table 7.1. The main methods of the abstract classes OutputStream and Writer .  Instead of the character } , int is substituted for bytes and char for characters .  free  flows

7.2. Byte  streams,  related  with  files.  Byte  streams,  related  with  files,  are used  for  work  with  binary  files.

int  read()  throws  IOException               Read  one  byte/character  from  on-current  (in  case  achievements  end  file  returns  -one) int  read( } []  a)  throws  IOException  filling  array  content, read  from  flow  (returns  actual  amount  counted  bytes/characters)

int  read( } []  a,  int  offset,  int  len)

throws  IOException

filling  parts  array  contain-  we M,  read  from  flow

oolean  ready()  throws  IOException  Examination  availability  data  in  flow

(if the method returns false , then the following  The next call to the read() method will be  wait for data and only complete  when you receive them). The method is determined  lyatsya  only  interface  Reader ! long  skip( long  n)  throws  IOException  Pass  given  quantities  buy-goods/characters  in  flowvoid  close()  throws  IOException Closing  flow

Table 7.2. The main methods of the abstract classes InputStream and Reader . Together-  hundred  symbol  }  substituted  int  for  byte  and  char  for  symbol-  nyh  flows

For these streams I/O is done directly  without performing any transformations on the content. Funk-  the rationality of byte streams associated with files is ensured  classes FileInputStream and FileOutputStream . To create objects  are used  the following  constructors:

FileInputStream(String fileName) throws FileNotFoundException  FileOutputStream(String  fileName)  throws  FileNotFoundException  FileOutputStream(String  fileName,  boolean  append)

throws  FileNotFoundException

All constructors try to open the file whose name is passed to them  as an argument. If, when creating an output stream,  If the existing file already existed, it will be truncated to zero length.  However, if you use the third of the above con- constructors with the value of the append argument equal to true , the file will be  open  in  mode  re-recording  in  the end.

7.3. Character streams wrappers for byte streams.  Because-  Since all character information is represented in Java in Unicode, while  time  as  external  data  often  presented  in  others  encodings  then for Java to communicate effectively with the outside world, it requires  encoding conversion. This operation is performed by symbolic  wrapper currents. They can join any byte stream  (“wrap” it) and allow the received stream to be treated as  with  symbolic,  performing  all  necessary  transformations.

The streams in question correspond to the classes InputStreamReader  (converts data read from a byte stream to Unicode) and  OutputStreamWriter (converts character data output to  byte stream from Unicode). To create class data objects  are used  the following  constructors:

InputStreamReader(InputStream  in)  InputStreamReader(InputStream  in,  String  charSet)  OutputStreamWriter(OutputStream  out)  OutputStreamWriter(OutputStream  out,  String  charSet)

Required  encoding  determined  argument  charSet .  If a  she is  not  uka-  zana,  used  encoding  systemic  locales.

7.4. Character streams associated with files. Symbolic  currents associated with files are designed to work with text  files. In fact, they are a combination of byte  stream and a character wrapper stream that performs the conversion  nie.  At  this  always  used  encoding  systemic  locales.

These streams correspond to the FileReader and FileWriter classes with  next  constructors:

FileReader(String  filename)  throws  FileNot FoundException  FileWriter(String  filename)  throws  FileNot FoundException

FileWriter(String  filename,  boolean  append)  throws  FileNot FoundException

They are used in the same way as byte-code constructors.  currents,  related  with  files  (cm.  P.  [7.2](#part0026.xhtml__bookmark57) ).

7.5. Character print stream. Character print stream (corresponding to it  corresponds to the class PrintWriter ) is a wrapper stream for another  character stream, adding formatting functionality to it  bathroom output  —  methods  print() and println() .  They are defined for  argu-  cops of all primitive types and type Object . In the latter case, in  flow  output  string  performance  object  (cm.  P.  [6.3](#part0022.xhtml__bookmark51) ).

For  creation  objects  class  PrintWriter  are used  the following  constructors:

PrintWriter(Writer  out)

PrintWriter(Writer  out,  boolean  autoFlush)

Note  what  Class  printreader  not  provides  automatic  dump-  sa  buffers  in  file  at  appearance  in  flow  symbol  translation  stro-  ki. Automatic reset is only possible using the method  println() provided that when creating the object, the value of the parameter  autoFlush  It was  established  equal  true .

AT  recent  versions  Java  Class  PrintWriter  contains  constructors,  allowing you to join byte and even file byte  streams:

PrintWriter(OutputStream out)  PrintWriter(OutputStream  out,  boolean  autoFlush)

PrintWriter(String  filename)  throws  FileNot FoundException  PrintWriter(String  filename,  String  charset)

These  constructors  simply  create  intermediate  objects  types

InputStreamWriter  and  FileInputStream ,  to  which  and  are joining.

Note  what  along with  with  class  PrintWriter  exist  Class  PrintStream with similar functionality. In new Java programs  creating objects of this class is not recommended, however, this  type  have  objects  System.out  (standard  flow  output)  and  System.err  (standard error stream). This is due to historical reasons  us.

7.6. Buffered  flows. Buffered  streams  are  wrappers for other streams. They provide an increase in the efficiency  activity  I/O  behind  check  buffering.  Functionality  boo-  ferized streams is provided by the classes BufferedInputStream ,  BufferedOutputStream (input and output byte streams with buffered  rization), BufferedReader and BufferedWriter (similar character  streams).  For  creation  objects  these  classes  are used  constructive  ry,  host  in  quality  argument  link  on the  wrapped  flow:

![](Images/image00495.jpeg)BufferedInputStream(InputStream  in)  BufferedOutputStream(OutputStream  out)  BufferedReader(Reader  in)  BufferedWriter(Writer  out)

In addition, the buffered input character stream adds  method

![](Images/image00479.jpeg)String  readLine()  throws  IOException

exercising  reading  one  lines  from  input  symbolic  flow.  AT  case  reaching the end  file  this method  returns  null . _

7.7. Console I/O. Standard output streams and errors  ci are represented in Java by System.out and System.err objects , which have  type PrintStream (see [section 7.5](#part0027.xhtml__bookmark61) ). Functionally, they are similar to symbolic  nym print-streams, therefore, for output, they usually use  toda  print()  and  println() ,  For example:

System.err.println("This  line  output  in  standard  flow  errors");

A slightly more complicated situation arises with the standard flow  com input. In Java, it corresponds to the System.in object , however, due to  historical  reasons  is he  is an  not  symbolic,  a  byte  on-  current  and  because  for  input  data  from  him  required  transformation  in Unicode. The latter can be done using a wrapper thread  InputStreamReader : Reader  in  =  new  InputStreamReader(System.in); Insofar as  usually  input  from  standard  input  flow  carries out-  Xia  line by line  a  not  character by character  then  often  used  more  one  wrapper  type  BufferedReader : reader  in  =  new  BufferedReader( new  InputStreamReader(System.in));

# 8. Containers

8.1. Overview of containers. Containers are objects that  own to store other objects. They differ in the way they organize  tion, the time to perform basic operations (adding, extracting  and deleting elements), as well as supported workarounds.  Yes  elements  container.

Containers  in  Java  can  divide  on the  three  groups:  arrays,  collection  tions and associative arrays. Arrays were discussed in Section [1.5](#part0003.xhtml__bookmark7) . Them  a distinctive feature is the impossibility of resizing  after creation. All other containers in Java change dynamically  mine  the size  at  adding  and  removal  elements.

Collections form the largest group of containers .  All collection classes in Java are parameterized types .  (generics). A parameterized type is a class or interface that has  The general parameter is the name of the type that must be specified when creating  objects. Parameterized types resemble C++ templates and pre-  appointed in the first place in order to ensure the control of the right  type fidelity at compile time. They represent very  flexible and at the same time complex mechanism, detailed consideration  which is beyond the scope of this manual. Detailed information  about  parameterized  types  can  get  in  article  [ [11](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ].

The parameter of Java collection classes is the type of objects that  they can store (here and throughout below, this type is denoted by the letter E ).  Parameter  maybe  be  only  class  or  interface.  For  storage  in  collections  data  primitive  types  should  use  classes-  wrappers  (cm.  P.  [3.13](#part0011.xhtml__bookmark32) ).

Collection<E> interface . Basic-  nye methods of this interface are given in table. [8.1](#part0029.xhtml__bookmark67) . All of them correspond  These are operations that are practically independent of the type of the collection. AT  the number of most commonly used collections includes dynamic  arrays, doubly linked lists, sets, and ordered sets.  classes,  implementing  functionality  these  collections,  described  in  pp.  [8.3](#part0029.xhtml__bookmark69) ,  [8.5](#part0029.xhtml__bookmark72) .Associative arrays (the terms "dictionary" are also used  and "display map") are more complex data types than  collections.  Actually  they  present  yourself  arrays,  use-

![](Images/image00496.jpeg)

booleanadd(Eo) Addendum  element  in  collection  (returns  true  in  case  success)

boolean  remove(Object  o) Deletion  element  from  collections

boolean  contains(Object  o) Verification  accessories  element collections

int  size() Get  quantities  elements  in  collections

boolean  isEmpty() Check  collections  on the  emptiness

boolean  equals(Object  o) Comparison  collections  on the  equality

Iterator<E>  iterator() Get  iterator  collections

object[]  toArray() Copy  content  collection  tion to the array in the order of bypass count  lectures  iterator

![](Images/image00497.jpeg)

Table  8.1.  Main  methods  interface  Collection<E>

containing arbitrary objects instead of indices. They are described in detail in  P.  [8.6](#part0029.xhtml__bookmark73) .

8.2. Iterators.  Iterators  intended  for  bypass  collections  in some order. Using an iterator is the fastest  a way to enumerate all elements of a collection. Iterator classes re- parse the Iterator<E> interface , which defines three methods: hasNext() ,  next()  and  remove() .

An iterator can be obtained by calling the iterator() method on  the corresponding collection object. Initially, the iterator is set  pouring  before  first  element  collections.  Everyone  call  method

E  next()

returns the element that the iterator was before the call, and  advances the iterator, placing it after the returned element. If a  the iterator is after the last element of the collection, the next() method  throws an exception of type NoSuchElementException . For check  availability  element  before  iterator  used  method

![](Images/image00479.jpeg)boolean  hasNext()

For  removal  last  returned  method  next()  element  maybe  be  used  method

void  remove()

Allowed  only  single  call  method  remove()  after  call-  wa  method  next() .  AT  otherwise  case,  a  also  in  case,  when  you-  next () was not called at all, throwing an exception like  IllegalStateException .

AT  quality  example  consider  usage  iterator  for  output  content  collections  collection ,  containing  elements  type  MyClass :

for (Iterator<MyClass>  it  =  collection.iterator();  it.hasNext();  )  System.out.println(it.next());

For collections (and also for arrays) there is an alternative  option  cycle  for :

for ([  type  data  ]  variable  :  collection)  operator;

It traverses the contents of the collection in the order specified by  iterator (for arrays in order from the first element to the  the last one), while the variable specified in the loop header is followed by  importantly  assigned  links  on the  elements  collections.  For example:

for(MyClass  e  :  collection)  System.out.println(e);

8.3. Lists and dynamic arrays.  Lists and Dynamic Masses  Sivy  —  This  collections  with  arbitrary  in order  following  elements.  The order of elements in such collections is determined by their numbers, as follows  the same as in regular arrays. All classes that provide functionality  the nature of these collections, implement the List<E> interface (subinterface  interface  Collection<E> ),  methods  whom  given  in  tab.  [8.2](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) .

For  considered  collections  method  add() ,  definite  in  inter-  face  Collection<E> ,  carries out  insert  in  the end  collections,  a  method  remove()  removes the first occurrence of the given  element.

Standard  library  contains  the following  classes  collections  with  arbitrary  in order  following  elements:  LinkedList<E> ,  ArrayList<E>  and  Vector<E> .

The LinkedList<E> class is a collection organized  nuyu  in  form  doubly connected  list.  He  provides  receiving  element  on  index  behind  time  order  O ( N ),  a  also  insert  and  removal  elements  in  position  iterator  behind  time  order  O (1).

For  creation  copies  class  LinkedList<E>  may  be  use-  called  the following  constructors: void  add( int  index,  E  element)               Addition  element  in  the specified

position

E  get( int  index) Getting  element  with  given  in-  dex

E  set( int  index,  E  element) Change  element  with  given  in-

dex  (returns  old  meaning  element)

E  remove( int  index) Delete  element  with  given  in-

dex  (returns  remote  ele-  cop)

int  indexOf(Object  o)

int  lastIndexOf(Object  o)

ListIterator<E>  listIterator()  ListIterator<E>  listIterator( int  index)

Search  first/last  entry-  element (in case of failure,  rotate  -one)

Receipt  payroll  iterator,  established  on the  Start  list/ne-  ed  given  element  list

constructors:

ArrayList()

ArrayList(Collection<?  extends  E>  c)  ArrayList( int  capacity)

The last constructor allows you to set the amount of memory, initially  initially  allocated  under  array.

Iterators  bypass  lists  and  dynamic  arrays  in  okay  increasing element indexes. Collections Implementing an Interface  List<E> ,  support  special  list  iterators  (inter-  face ListIterator<E> ), which have more functionality than  ordinary.  AT  in particular  such  iterators  may  move  on  collections  in both directions. To check if the previous element exists and  his  receiving  intended  methods

![](Images/image00498.jpeg)boolean hasPrevious()  E  previous()

similar to the hasNext() and next() methods . Also list iterators  allow you to replace the last received element with the help of  shew  method

![](Images/image00479.jpeg)void  set(E  o)

as well as inserting an element at the current position of the iterator with  method

![](Images/image00479.jpeg)void  add(E  o)

After  inserts  iterator  placed  after  inserted  element.

8.4. Ordering of objects. Many container handling tasks  moat  connected  with  accommodation  objects  in  some  okay.  For  This-  it is necessary to define some operation for objects, which  will allow you to find out which of the objects is larger or smaller than the other. AT  Java has two standard ways to define such an operation.  AT  first  case  Class,  objects  whom  subject to  streamlining,  dol-  wives  implement  interface  Comparable<T> .  AT  quality  parameter  T must be substituted with the name of the class that implements the given interface.  For example:

class  MyClass  implements  Comparable<MyClass>

Interface  Comparable<T>  defines  method

int  compareTo(T  obj)

which should compare the object of the class on which  this object is called ( this ), with the object passed to this method  and return a value less than zero if the this object is greater than the object  obj , which is zero if this.equals(obj) == true and greater than zero if the obj object is greater than the this object . The relation "greater" itself can be  arbitrary and corresponds to the criterion by which  ordering.

For example, if there is a class "complex number" with two real  re and im fields and it is required to perform ordering of objects  of this class in ascending or descending order of the modules of the corresponding  complex numbers, the compareTo operation can be defined as follows :  shchim  way:

class ComplexNumber  implements  Comparable<ComplexNumber>

{

public  double  re,  im;

public  ComplexNumber(double  re,  double  im)

{

this.re  =  re;  this.im  =  im;

}

public  int compareTo(ComplexNumber c)

{

double  diff = (re  * re +  im * im)  – (c.re * c.re  + c.im *  c.im);

return  (int)(Math.signum(diff));

}

}

A way of ordering objects based on a particular  nym  way  operations  comparisons,  called  in  Java  natural  mention-  rowing . Each class can define at most one way  natural  ordering.

Another way of ordering is to define an outer  class  ( comparator ),  objects  whom  will  realize  comparison  objects of the required class. Comparator classes must implement define the Comparator<T> interface , where the parameter T defines the type of the object  goods compared by this comparator. Comparator<T> interface  defines  method

![](Images/image00479.jpeg)int  compare(T  o1,  T  o2)

which compares two objects passed to it in  as arguments and returns as a result  comparisons are positive

oah,  negative  or  equal  zero  whole  number  likewise  method

compare()  interface  Comparable<T> .

So,  in  example,  given  higher,  instead of  method  compareTo()  can-  but  implement  comparator  next  way:

class  ComplexNumberLenComp  implements  Comparator<ComplexNumber>

{

public  int  compare(ComplexNumber  c1,  ComplexNumber  c2)

{

double  diff  =  (c1.re  *  c1.re  +  c1.im  *  c1.im)

-  (c2.re  *  c2.re  +  c2.im  *  c2.im);

return  ( int )(Math.sign(diff));

}

}

It is easy to see that for one class one can define any number of  number of comparators, so this method is usually used in  in cases where the program uses different sequencing criteria  nia  objects.

Many standard container handling algorithms, as well as self-  Containers require you to define how objects are ordered.  An example of using various methods of ordering when storing  research institutes  and  processing  data  brought  in  P.  [8.8](#part0029.xhtml__bookmark76) .

8.5. Sets and ordered sets. Sets and mentions  rowed sets are collections that provide a fast addition  Adding and removing elements, but not allowing you to install  order  them  following  and  keep  duplicates.

Set<E> interface , and also implement the enclosing HashSet<E> class . None of them adds new me-  methods compared to the Collection<E> interface . For storage  cops class HashSet<E> uses hashing, so objects  stored in collections-sets must be implemented use the equals() and hashCode() methods (see [section 3.12](#part0010.xhtml__bookmark31) ) Thanks to hashing  time to perform basic operations (adding, deleting and checking  occurrence of an element in a set) is practically independent of the size  set ra. The order in which the elements of the set are traversed by the iterator is  is called rather arbitrary, since it is determined by hash codes  elements.  For  creation  copies  class  HashSet<E>  are used  the following  constructors:

![](Images/image00479.jpeg)HashSet()

![](Images/image00479.jpeg)HashSet(Collection<?  extends  E>  c)

sets are represented by the SortedSet interface and  implementing it with the class TreeSet<E> . The latter uses for storage  balanced binary trees, which allows  guarantee the order in which iterator traverses the set in ascending order  okay. Operations of adding, deleting and checking occurrences of elements  cop  in  a bunch of  require  time  order  N  log  N. _

For  creation  copies  class  TreeSet<E>  are used  follow-  ing  constructors:

![](Images/image00499.jpeg)TreeSet()

TreeSet(Collection<?  extends  E>  c)  TreeSet(SortedSet<E>  s)  TreeSet(Comparator<?  super  E>  c)

The last of these allows you to create sets ordered in  arbitrary  okay,  determined  transmitted  in  constructor  com-  parator (see paragraph [8.4](#part0029.xhtml__bookmark71) ). In all other cases, the set of orderings  develop in a natural order. In this case, element classes  sets  obliged  implement  interface  Comparable<T> .

8.6. Associative arrays. As already noted, association  arrays can be thought of as arrays using instead of in-  dexes are arbitrary objects. We can assume that they set the display  reduction of a set of key objects into a set of value objects .  They are not collections in the sense that they do not implement  interface Collection<E> . It is replaced by the Map<K, V> interface , which has  two options. The first defines the data type of the keys of the associative  array, and the second is the type of its values. Basic Interface Methods  Map<K,  V>  given  in  tab.  [8.3](#part0029.xhtml__bookmark74) .

Associative arrays are used to store pairs of con-  set containers. Therefore, both the hierarchy and the properties of both  match:  classes  HashSet  and  treeset  correspond  classes  hashmap  and  treemap  respectively,  a  interface  SortedSet  —  interface  SortedMap .  Ratings  time  fulfillment  major  operations  for  associative  lists  such  same,  as  and  for  relevant  them  sets.

Association lists do not have iterators of their own. For their  traversal uses set iterators of their keys, returned by  keySet() method . The following code snippet demonstrates the use of  ing  associative  arrays:

V  put(K  key,  V  value) Appending  couples  key-value  (returns  old  meaning,  asso-  cited  with  key  or  null ,  if  such  key  not  It was)V  get(Object  key) Get  values,  correspond-  key (returns null if  the key is not in  associative array)

V  remove(Object  key) Delete  couples  key-value  (WHO-

rotates  meaning  deleted  couples)

boolean  containsKey(Object  key)               Check,  contains  whether  associative

ny  array  given  key

int  size() Get  size  associative  array

boolean  isEmpty() Check  associative  array  on the  emptiness

void  clear() Clearing  associative  array

boolean  equals(Object  o) Comparison  associative  arrays  on the  equalitySet<K>  keySet()               Get  set  keys  in  form  sets

Table  8.3.  Main  methods  interface  Map<K,  V>

TreeMap<string,  String>  capitals  =  new  TreeMap<string,  string>();  capitals.put(" ",  "Moscow");

capitals.put("France",  "Paris");  capitals.put("Italy", "London"); // not right  capitals.put("Italy",  "Rome");  //  correction  mistakes

System.out.println("Capital  Italy  -  "  +  capitals.get("Italy"));

//  Conclusion  Total  array,  sorted  on  titles  countries

for (String  s  :  capitals.keySet())  System.out.println(s  +  ":  "  +  capitals.get(s));

8.7. Inherited (legacy) container classes. Except classes  ArrayList<E> , HashSet<E> and HashMap<E> , there are similar  functionality  classes  Vector<E>  and  Hashtable<E>  and  Dictionary<E> .  These are the so-called legacy classes from older versions.  libraries. Their main purpose is to provide backward compatibility  value. Although they are not considered deprecated, it is likely that  it is better  avoid  use  them  in  new  programs. Table  8.4.  Main  methods  class  collections .  All  methods  are  stat-  calic

8.8. Standard container processing algorithms. Standard-  naya  library  Java  contains  implementation  some  standard  algo-  rhythms  processing  containers,  a  also  some  service  operations.  All of them are presented as static methods of the Collections classes.  (for collections and association lists) and Arrays (for arrays). Co-  relevant  methods  given  in  tab.  [8.4](#part0029.xhtml__bookmark77) ,  [8.5](#part0030.xhtml__bookmark78) . Especially note family methods, returning immutable our container wrappers ( unmodifiableCollection() , unmodifiableList()  etc.). These methods return an object that implements the con- container of the appropriate type. When using methods estimating and getting the values of the returned object, the latter leads itself in exactly the same way as the original object. When trying to call any th container change method throws an exception of type  UnsupportedOperationException .

The following example demonstrates the capabilities of the tools described-  nyh  in  given  chapter.![](Images/image00500.jpeg)

void  sort( int []  a) Sorting  array

void  sort(T[]  a,Comparator<?  super  T>  c)  int binarySearch( int [] a, int key)  int  binarySearch(T[]  a,  T  key,

Comparator<?  super  T>  c)Sorting an array of objects is ok,  determined  comparatorBinary search for the index of an element in the reference  row array. If the element is not found  den, a value equal to (minus  the position in which the element should have been  cop,  minus  unit)

![](Images/image00501.jpeg)

boolean  equals( int []  a,  int []  a2)               Comparison  arrays  on the  equality

void  fill( int [] a, int val )  all  elements  array  given-

![](Images/image00502.jpeg)nym  meaning

List<T>  asList(T[]  a)

List<T>  asList(t.  .  .  a)

Array/Set Conversion  element-

Comrade  in  list

![](Images/image00503.jpeg)

Table  8.5.  Main  methods  class  arrays .  Given  methods  for  work  with  arrays  type  int[] .  Exist  similar  methods  for  work  with arrays of all other primitive types and of type Object . All  methods  are  static

import  java.util.*;

/**  Class  "questionnaire  data  human"  */

class  person  implements  Comparable<Person>

{

/**  Data  and  methods  for  them  receiving  */

private  String  name;

public  String  getName()  {  return  name;  }

private  int  age;

public  int  getAge()  {  return  age;  }

/**  Конструктор  */

public  Person(String  name,  int  age)  {  this .name  =  name;  this .age  =  age;  }

/**  transformation  object  to  line  */

public  String  toString()  {  return  name  +  "  ("  +  age  +  ")";  }

/**  Comparison  objects  on the  equality  */

public  boolean  equals(Object  obj)

{

if(!(obj  instanceof  Person))

return  false;

return  ((Person)obj).name.equals(name)  &&  ((Person)obj).age  ==  age;

}

/**  Receipt  hash code  object  */

public  int  hashCode()  {  return  name.hashCode()  +  age;  }

public  int  compareTo(Person  p)  {  return  name.compareTo(p.name);  }

}

/**  Class  "comparator  for  comparisons  on  age"  */

class  PersonAgeComparator  implements  Comparator<Person>

{

public  int  compare(Person  p1,  Person  p2)

{

return  p1.getAge()  –  p2.getAge();

}

}

public  class  PersonsSortExample

{

public  static  void  main(String  args[])

{

TreeSet <Person>  data  =  new  TreeSet <Person> ();  data.add ( new  Person ("Petrov",  31));

data.add ( new  Person ("Ivanov")  45));

data.add ( new  Person ("Smirnov",  20));

data.add( new  Person("Smirnov",  20));  //  such  element  already  there is

System.out.println(data);  //  conclusion  sorted  on  surnames

// Copy the contents of the set to a list  ArrayList<Person>  data2  =  new  ArrayList<Person>(data);  Collections.sort(data2,  new  PersonAgeComparator());  System.out.println(data2);  //  output sorted  on  age

}

}

Conclusion  this  programs:

[Ivanov  (45)  Petrov  (31),  Smirnov  (20)]

[Smirnov  (20),  Petrov  (31),  Ivanov  (45)]

# 9. Multithreaded  programming

9.1. Creation and management of threads.  Multithreading is  a method of organizing the execution of a program, in which its individual  parts  performed  simultaneously  or  pseudosimultaneously.

The Thread class encapsulates a thread of execution. Basic Methods  of this class are listed in Table. [9.1](#part0032.xhtml__bookmark81) . Each thread of execution in  the program corresponds to an instance of this class or its subclasses.  As a rule, programs create subclasses of the class Thread , re-  defining  method

![](Images/image00479.jpeg)void  run()

which is the entry point to the stream. When creating instances  of the current class, the corresponding threads of execution do not receive  management.  To  run  flow,  should  call  method

![](Images/image00479.jpeg)void  start()

relevant  him  object.  At  this  flow,  on the  which  was  called  method  start() ,  continues  performance,  and  simultaneously  with  him  on the  friend  the thread starts executing the run() method of the corresponding object  ("simultaneously" in this case usually means that the threads after-  consistently receive small quanta of processor time, which  creates the illusion of their simultaneous execution). As soon as If the run() method is called , the thread corresponding to it will be executed.  nia  stop  own  Existence.  Method  start()  can  call  only  one  once  for  everyone  stream object.

For  Togo  to  check,  exist  whether  more  some  flow  execution, the isAlive() method of the corresponding object is used.  There is also the option to pause the current thread until  completion of another. To do this, use the join() method , you-  called on the object corresponding to the thread whose completion  expected.

A running thread can itself enter sleep mode by  calling the sleep() method . In this case, the processor time is suspended  lazy thread will be used by other threads. Besides,  flow  maybe  refuse  from  his  quantum  time  through  call  me-  then yes  yield() .  AT  this  case  his  quantum  also  redistributed  between

![](Images/image00504.jpeg)

void  start() Start  flow

![](Images/image00505.jpeg)

void  run() entry point  into the stream

static  void yield() Voluntary  short-term  broadcast  management  others  streams

static  void  sleep( long  millis)

throws  InterruptedException

void  join()

throws  Interrupted Exception suspension  flow  on the  specified

interval  time suspension  current  flow  before  mo-  cop  completion  another  flowboolean  isAlive()               Check,  not  ended  whether  flow

void  interrupt() Setting  flag  interrupted

boolean  isInterrupted() Get the status of the

interrupted flag  void  setPriority( int  newPriority)               Change  priority  flow

int  getPriority( )  priority  flow

void  setDaemon( boolean  on)               Announcement  flow  demon

Table  9.1.  Main  methods  class  Thread

other streams. This is usually used in cases where  the current is waiting for some event triggered by another  flow.  For example:

if (!somethingHappened)  yield();

The use of yield() allows you to increase the speed of the program,  because multiple useless value   checks are avoided  variable until other threads get a chance to change  this  values.

The ratio between the time that different threads receive  ki, is determined by their priorities. Priority is a value in the range  zone from 1 (lowest priority) to 10 (highest priority).  Methods are used to set and get the priority value.  dy setPriority() and getPriority() respectively. Default threads  created  with  priority  equal  5.

AT  any  program  always  exist  on  extreme  measure  one  on-  current  execution,  on the  which  performed  method  main()  (dot  entrance  to the program). Program execution ends only when  all threads started by the program will terminate. The exception to this is  Its rules are only daemon threads. In order to announce  some daemon thread, you should call the setDaemon() method before  launch  this  flow.  daemon threads  interrupted  virtual  wave-Noah  automatically,  when  come to an end  all  rest  flows.  Main  appointment  such  flows  —  give  the rest  parts  programs  some  Services  in  background  mode.

Sometimes it becomes necessary to prematurely terminate a thread  and possibly resume its execution in the future. For this in  Class  Thread  were  introduced  methods  stop() ,  suspend()  and  resume() ,  but  later they were recognized as unsafe because they do not allow  before stopping the thread, perform actions such as, for example,  release of the specified resources, and therefore can lead to a hang-up  nyu  or  incorrect  functioning  programs.  These  methods  not  should be used in new programs. An alternative way  bom flow control is to use a special flag  interrupted of the Thread class . In order to interrupt the execution  current, the setInterrupted() method is used . If the flow at this moment  is an  suspended  (calling  method  sleep() ,  join()  and  etc.),  then  is he  resumes  my  work,  a  corresponding  method  ejection-  there is an exception. Otherwise, a special flag is set  interrupted . The thread must check the status of this on its own.  flag by calling the isInterrupted() method and terminate  work  in  case,  if  is he  set,  For example:

void  run()

{

boolean  done  =  false ;

while (!done)  //  main  cycle  flow

{

if (isInterrupted())

{

//  conduct  final  actions

return ;

}

}

}

Everyone  call  method  isInterrupted()  resets  meaning  flag  interrupted .  Note  what,  if  flow  not  checks  meaning  flag  interrupted ,  maybe  arise  situation,  when  his  generally  it is forbidden  will  stop.

The following example demonstrates the use of various methods  dov class Thread . In this example, the main thread instantiates  class  hello Thread ,  deducing  on the  screen  phrase  Hello,  world!”  on the  from-separate thread of execution and making a delay before its completion  sewing. The main thread, in turn, is waiting for the completion of the child  thread, after which it displays a message that the child thread has completed  sya.

class  hello thread  extends  Thread

{

/**  Dot  entrance  in  flow  */

public  void  run()

{

System.out.println("Hello,  world!");

try

{

sleep(1000);

}

catch(InterruptedException  e)

{

System.err.println("Поток  MyHelloThread  прерван");

}

}

}

public  class  SimpleThreadsExample

{

public  static  void  main(String  args[])

{

Thread  t  =  new  HelloThread();  t.start();  //  launch  flow

try

{

t.join();  //  expectation  completion  flow

}

catch (InterruptedException  e)

{

System.err.println("Main  flow  interrupted");

}

System.out.println("Stream  MyHelloThread  ended");

}

}

9.2. Interface  runnable. Sometimes  it happens  necessary  add  the functionality of the Thread class to an already existing class. One-  to  fulfill  inheritance  from  class  Thread  it is forbidden,  insofar as  Classis already a subclass of some other class. In this case, mo- The Runnable interface can be used . This interface defines  the only one  method

void  run()

similar  eponymous  method  class  thread .

Class,  realizing  interface  runnable ,  used  next  way: an instance of this class is created, which is passed to the con-  constructor  class  thread :

MyRunnableClass  r  =  new  MyRunnableClass();  Thread  t  =  new  Thread(r);

t.start();

Sometimes  an object  class  Thread  placed  directly  internal  ri class that implements the Runnable interface and is initialized in  constructor  this  class:

class  MyRunnableClass  implements  runnable

{

private  Thread  thread;

/**  Constructor:  creates  an object  class  Thread  and  Launches  his  */

public MyThread()

{

thread  =  new  Thread( this );  thread.start();

}

/**  Dot  entrance  in  flow  */

public  void  run()

{

//  .  .  .

}

}

9.3. Synchronization.  The  multithreaded  applications  often  byva-  It is not necessary for the same object or method to be  used by only one thread. In order to provide this  possibility,  used  mechanism  sync .

Consider  protozoan  example,  where  maybe  required  synchro-  nization.

/**  Constructor  (saves  name  flow  and  Launches  flow)  */

public  MyThread(String  name)  {  super (name);  start();  }

/**  Точка  входа  в  поток  */

public  void  run()

{

try

{

}

System.out.print("[");  Thread.sleep(1);  System.out.print(getName());  Thread.sleep(1);  System.out.print("]");}

catch(InterruptedException  e)

{

System.err.println("Поток  "  +  getName()  +  "  прерван");

}

}

}

public  class  SyncExample

{

public  static  void  main(String[]  args)

{

for ( int  i  =  0;  i  <  ten;  ++i)

new  MyThread(String.valueOf(i));

}

}

This example creates 10 threads, each of which outputs  to the console your number in square brackets and terminated. Example  output  this  programs:

![](Images/image00479.jpeg)[[[[[[[[[1[4320586]79]]]]]]]]]

Insofar as  all  streams  simultaneously  use  one  that  same  an object  ( System.out ),  then  results  output  various  flows  get mixed up.  Not difficult  introduce  yourself  the situation  when  similar  a joint  usage  objects  maybe  drive  to  mistakes.  Should  also  have  in  mind  what  insofar as  distribution  time  between  streams  wears  non-deterministic  character,  then  mistakes  may  manifest  not  at  everyone  startup  programs,  what  complicates  them  finding.  On the-  example,  if  in  given  higher  example  put away  delays  ( sleep )  then

this effect almost never occurs, since one quantum  the time allotted to a thread is almost always sufficient for  Togo,  to  implement  required  conclusion.

The main concept of synchronization is the monitor. Monitor -  it is an (implicit) object that is used for mutually exclusive  blocking. In Java, each object initially has its own  monitor. When a thread enters a monitor, the corresponding block object  checked. If at the same time another thread tries to enter the same  monitor, it pauses until the first thread  will come out  from  monitor  and  topics  most  not  remove  blocking  with  object.

There are two kinds of synchronization in Java:  nized methods and synchronized blocks. Entrance (exit) to  synchronized  method  or  block  automatically  leads  to  input  control of the current stream to the monitor (exit from the monitor) of the corresponding  object.

To make a method synchronized, just add to  its header is the synchronized keyword . Synchronized blocks  ki (also sometimes called critical sections) have the following  shchy  syntax.

synchronized (object_name)

{

//  .  .  .

}

AT  in particular  in  given  higher  example  enough  place  content  block  try  in  synchronized  block:

synchronized (System.in)

{

System.out.print("[");  Thread.sleep(1);  System.out.print(getName());  Thread.sleep(1);  System.out.print("]");

}

In this case, the thread that entered the monitor of the System.in object first ,  suspends all other threads trying to enter the same  monitor, and releases the monitor only after it performs  mine  conclusion  fully.  Then  in  monitor  included  next  flow  and  t.  d.

Conclusion  programs  after  additions  in  her  synchronized  block:

![](Images/image00479.jpeg)[0][9][8][7][6][5][4][3][2][1]

In conclusion, we note that Java provides much more  extensive control over thread synchronization. In private  sti, a thread that has entered the monitor may temporarily yield the monitor  another  flow  and  again  get  control  after  Togo,  as  last  will release the monitor. These features, as well as typical errors  inter-

# 10. Technology  access  to  bases  data  JDBC

10.1. Architecture  JDBC.  JDBC  (Java  DataBase  Connectivity is  platform-independent database access technology from Java  applications. It provides a set of data access interfaces,  through which Java applications interact with external  database drivers, as well as tools that provide integration  these  external  drivers  in  Wednesday  Java.

Such  an approach  is an  enough  flexible  insofar as  Java application  nia  turn out  separated  from  details  interactions  with  DB,  a  drivers  It is enough for the database to provide the implementation of certain JDBC interfaces -  owls  for  Togo,  to  be  compatible  with  Java applications.

The JDBC classes and interfaces are hosted in the java.sql package . Additional  yarn  intelligence  about  technology  JDBC  can  to find  in  books  [ [4](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ,  [5](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ].

10.2. Database drivers. To connect to the database, you need  We must first load the driver corresponding to the database used.  The standard distribution of Java includes only one such driver - JDBC -  ODBC Bridge. This driver bridges the JDBC interface  and a standard interface for connecting to Microsoft databases  ODBC (Open DataBase Connectivity). This method is sufficient  but universal, since for most databases there are  There are corresponding ODBC drivers. However, the preferred way  connection is still considered to be the use of JDBC drivers  specific databases, since such drivers are usually  are more functional and faster than  JDBC-ODBC Bridge. In addition, they can provide cross-platform  application variability (using ODBC is usually possible  only on MS Windows). JDBC drivers can be found in  delivery of most existing DBMS, or on the Internet  by the address

JDBC Drivers  usually  supplied  in  form  jar archives,  cat-  which must be placed in any of the directories listed in  CLASSPATH  (cm.  P.  [3.9](#part0006.xhtml__bookmark26) ),  to  JVM  could  to find  required  driver.

Loading the driver is carried out by calling the method  tic  method  class  class :

![](Images/image00479.jpeg)static  class  forName(String  classname)  throws  ClassNotFoundException

AT  quality  argument  method  transmitted  name  driver class  For example:

![](Images/image00506.jpeg)Class.forName("sun.jdbc.odbc.JdbcOdbcDriver");  //  driver  ODBC-JDBC  Bridge

Class.forName("com.mysql.jdbc.Driver");  //  driver  MySQL  Connector/J

AT  case  impossibility  downloads  drivers  will  thrown out  except-  nie  type  classNotFoundException .

10.3. Connection  to  base  data.  Connection  to  base  data  correspond  objects  classes  implementing  interface  connection .

For  creation  these  objects  used  static  method

![](Images/image00507.jpeg)static  connection  getConnection(String  url,  String  user,  String  password)

throws  SQLException

class  DriverManager .  First  argument  this  method  defines  stro-  ku connection to the database, the other two - the username and his  password.

Connection string  It has  next  format:

![](Images/image00479.jpeg)jdbc: subprotocol_name: data_source_name

Here  "name  subprotocol"  defines  driver  or  protocol  plug-in  to the database, and "data source name" is usually the name of the database.  The connection string can also contain additional parameters -  ry.  Them  format,  equals  as  and  format  name  source  data,  depends  from a specific driver. For example, the following line could be  used  for  connections  through  drivers  JDBC-ODBC  Bridge  to  DB  with  name  "Clients"  located  on the  local  car:

![](Images/image00479.jpeg)jdbc:odbc:Clients

Relevant  DB  should  be  previously  registered  in  ODBC  administrator.  More  one  example:

![](Images/image00479.jpeg)jdbc:mysql://http://mydbserv.ru:3105/Students?useUnicode=true

Such  line  connections  used  for  connections  with  remote  DB

students,  located  on the  server  MySQL  on  address  The connection will be made through port 3105, for encoding  transmitted  lines  will  used  Unicode.

10.4. Creation  and  performance  requests  to  base  data.  Request  to  ba-

ze  data  encapsulated  classes  implementing  interface  Statement .  To each  object  such  class  corresponds  not  more  one  object,  representing  resulting  kit  data.  If a  required  have more than one result set, each of them must  be  generated  separate  Statement object.  Performance  new  The SQL query closes the existing data set created by the topic  same  Statement object.

For  creation  request  used  method

![](Images/image00508.jpeg)Statement  createStatement()  throws  SQLException

Statement  createStatement( int  resultSetType,  int  resultSetConcurrency,

int  resultSetHoldability)  throws  SQLException

called on the connection object. The second version of this method allows  lays  install  options  resulting  set  data.  Possible  nye  values  these  parameters  given  in  tab.  [10.1](#part0035.xhtml__bookmark90)[ ](#part0035.xhtml__bookmark90)(cm.  also  P.  [10.5](#part0034.xhtml__bookmark89) ).  For  fulfillment  request  to  DB  are used  the following  methods  in-

терфейса  Statement:

![](Images/image00509.jpeg)boolean execute(String sql) throws SQLException  ResultSet  executeQuery(String  sql)  throws  SQLException  int  executeUpdate(String  sql)  throws  SQLException

The first method is usually used for queries that do not return  resulting values (for example, DROP ), the second method is for  queries that return a set of data (for example, SELECT ). The third me-  tod  applied  for  fulfillment  SQL statements  INSERT ,  UPDATE  and  DELETE . It returns the number of added, removed or changed  records retrieved from the query. When errors occur, all  methods  throw away  exception  type  SQLException .

After  processing  results  request  last  should  be  closed  through  call  method

![](Images/image00479.jpeg)void  close()  throws  SQLException

If a  in  result  request  was  created  kit  data,  is he  closes  automatically  at  closing  request.

The following example demonstrates how to create, populate, and modify  cation  tables  "people"  through  SQL queries.

//  Loading  drivers  and  compound  with  DB

String  dbUrl  =  "jdbc:mysql://localhost/test?useUnicode=true";  Class.forName("com.mysql.jdbc.Driver");

Connection conn = DriverManager.getConnection(dbUrl, "pgm", "");  Statement  s  =  conn.createStatement();

//  Создание таблицы и заполнение её

s.execute("CREATE TABLE people "

+  "(Id  INTEGER  AUTO_INCREMENT  PRIMARY  KEY,"

+  "Name  VARCHAR(40),  "

+  "Telephone  VARCHAR(10),"

+  "Age  INTEGER)");

s.execute("INSERT  INTO  people(Name,  Telephone,  Age)"

+  "VALUES ( ' Ivanov ' ,  '12 -02-00 ' ,  37) ");

s.execute ("INSERT  INTO  people (Name,  Telephone,  Age) "

+  VALUES ( ' Petrov ' ,  '43 -55-47 ' ,  26) ");

s.execute("INSERT  INTO  people(Name,  phone,  age)"

+  "VALUES( ' Sidorov ' ,  '43 –88–90 ' ,  59)");

//  Modification and deletion  records

System.out.println("Updated  records:  "

+  s.executeUpdate("UPDATE  people  SET  Telephone= '63 -16-00 ' "

+  "WHERE  Name= ' Petrov ' "));  System.out.println("Removed  entries:  "

+  s.executeUpdate("DELETE  FROM  people  WHERE  Name='Иванов'"));

s.close();

10.5. Navigation through datasets.  The dataset is an object  a class that implements the ResultSet interface , encapsulating the result  tat of execution of the query to the database. The capabilities of the data set are determined by  are defined by its parameters. These parameters are set when the object is created -  request  methods  createStatement()  or  prepareStatement()  object-co-  unity (see paragraphs [10.4](#part0034.xhtml__bookmark88) , [10.7](#part0036.xhtml__bookmark93) ). The rsType parameter specifies the type of set  data,  rsConcurrency - mode  updates  set,  a  rsholdability- _  mode  conservation  cursor  after  commits  transactions.  Possible  values  these  parameters  given  in  tab.  [10.1](#part0035.xhtml__bookmark90) .

The dataset contains a cursor that allows you to move between  lines of this set. The technique of working with cursors is largely analogous to  is logical to the technique of working with collection iterators (see [section 8.2](#part0029.xhtml__bookmark68) ). First-  initially  cursor  placed  before  first  string  set  data.

Challenges  methods

![](Images/image00510.jpeg)boolean  next()  throws  SQLException

boolean  previous()  throws  SQLException

allow  fulfill  moving  on the  one  string  set  forward  and  back  respectively  (cursor  remains  between  lines!).  Methods

![](Images/image00511.jpeg)boolean  relative ( int  rows)  throws  SQLException

boolean  absolute ( int  row)  throws  SQLException

| Meaning | Description |
| Parameter  rsType |
| TYPE_FORWARD_ONLY  (after  default)TYPE_SCROLL_INSENSITIVETYPE_SCROLL_SENSITIVE | kit  data  is an  unidirectional  lazy;  cursor  maybe  move  on  set  data  only  forward  allowed  motion  cursor  in  arbitrary  direction,  a  also  arbitrary  access  to  content-  mu  set  dataallowed  motion  cursor  in  random direction, and  random access to content  mu of the data set; content on-  boron  data  automatically  up-to-date  zirovatsya when the contents of the database is changed  nyatsya  in  result  fulfillment  other  gih  requests |
| Parameter  rsConcurrency |
| CONCUR_READ_ONLY (default)  CONCUR_UPDATABLE | mode  "only  for  reading";  change-  nia  set  data  prohibited  changes  set  data  permit-  us;  these  changes  automatically  are made  in  DB |
| Parameter  rsHoldability |
| HOLD_CURSORS_OVER_COMMITCLOSE_CURSORS_AT_COMMIT(after  default) | after  commits  transactions  kit  data  remains  open,  and  polo-  ing  cursor  in  him  preserved  after  commits  transactions  kit  data  closes |
|  |  |

Table  10.1.  Values  parameters  set  data.  All  values  are  one hundred  tic  constants  class  result set

allow relative and absolute positioning  cursor in the dataset. The specified methods return a value  true if the move was successful, and false if requested  element  is absent.  Note  what  numbering  records  set  implement-  lyatsya  with  units!  For  positioning  cursor  before  first  and  after  last  element  set  are used  methods

| Type  data  SQL | Type  data  Java | Type  data  SQL | Type  data  Java |
| BOOLEAN | boolean | DOUBLE | double |
| TINYINT | byte | VARCHAR | String |
| SMALLINT | short | NUMERIC | BigDecimal |
| INTEGER | int | DATE | Date |
| BIGINT | long | TIME | Time |
| FLOAT | float | BLOB | blob |

Table  10.2.  Conformity  between  types  data  SQL  and  Java

![](Images/image00512.jpeg)void  beforeFirst()  throws  SQLException

void  afterLast()  throws  SQLException

All  listed  higher  methods,  Besides  method  next() ,  work  only  in the event that the data set is not unidirectional (significantly  reading  parameter  rsType  not  equals  TYPE_FORWARD_ONLY ).

For  receiving  values  fields  latest  lines  set  data,  che-  which any of the positioning methods moved ( next() ,  previous()  and  t.  etc.),  are used  methods

![](Images/image00513.jpeg)***  get***(int  columnIndex)  throws  SQLException

***  get***(String  columnName)  throws  SQLException

Here  instead of  ***  substituted  name  type  data  Java,  corresponding  the SQL data type of the parameter (see Table [10.2](#part0036.xhtml__bookmark91) ). The required field is defined  is specified either by its name in the database or by its number in the request ( numbering  fields starts from one! ). Instead of get*** methods , you can use  vat  universal  method

Object getObject(int columnIndex) throws SQLException  Object  getObject(String  columnName)  throws  SQLException

It returns the value of the requested field as an object of the corresponding  existing type (Table [10.2](#part0036.xhtml__bookmark91) ). If this type is primitive, then  revolves  his  wrapper  ( Integer  instead of  int  and  t.  d.;  cm.  also  P.  [3.13](#part0011.xhtml__bookmark32) ).

The following method displays the contents of an arbitrary table on the screen.  the person whose name is passed to the method as an argument. In the example  an object of the ResultSetMetadata class is used , which allows you to get  the number and names of dataset fields. More information  mation  about  this  classroom  can  get  in  documentation  on  JDBC.

/**  Seal  content  tables  DB  */

public  static  void  printDB(Connection  conn,  String  tableName)

throws  SQLException

{

Statement  s  =  conn.createStatement();

ResultSet  r  =  s.executeQuery("SELECT  *  FROM  "  +  tableName);

//  Receipt  and  conclusion  titles  columns  ResultSetMetaData  md  =  r.getMetaData();  for ( int  i  =  one;  i  <=  md.getColumnCount();  ++i)

System.out.print(md.getColumnName(i) + "\t");  System.out.println();

//  Вывод  данных  таблицы

while(r.next())

{

for(int  i  =  1;  i  <=  md.getColumnCount();  ++i)  System.out.print(r.getObject(i) +  "\t");

System.out.println();

}

s.close();}

10.6. Modifiable datasets. If the data set is  holds the fields of only one database table, among the fields of the set contains  the primary key of this table and the rsConcurrency option is set  equal  CONCUR_UPDATABLE ,  then  such  kit  data  can  use-  call to modify the corresponding database table, bypassing explicit  challenges  SQL statements.  For  this  are used  methods

![](Images/image00514.jpeg)void  update***(int  columnIndex,  ***  x)  throws  SQLException

void  update***(String  columnName,  ***  x)  throws  SQLException

Changes  are recorded  in  DB  through  call  method

![](Images/image00479.jpeg)void  updateRow()  throws  SQLException

To delete the current record of a dataset from the database, use  method

![](Images/image00479.jpeg)void  deleteRow()  throws  SQLException

A somewhat more complicated way is the addition of  pisi. First you need to move the cursor to a special line  dataset to be inserted. For this, it is used  method

void  moveToInsertRow()  throws  SQLException

Then  with  help  methods  update***()  carried out  filling  fields  added  records.  Addendum  records  in  table  produces  method

void  insertRow()  throws  SQLException

For  Togo  to  return  cursor  in  position,  in  which  is he  was  before  inserts,  used  method

void  moveToCurrentRow()  throws  SQLException

Next  example  modifies  DB  from  example  P.  [10.4](#part0034.xhtml__bookmark88)  middle-  stvom  changes  set  data.

Statement  s  =  conn.createStatement(ResultSet.TYPE_SCROLL_INSENSITIVE,  ResultSet.CONCUR_UPDATABLE);

ResultSet  r  =  s.executeQuery("SELECT  Id,  Name,  Telephone,  Age  "

+  "FROM  people");

//  Addendum  units  to  age  all  of people

while (r.next())

{

r.updateInt(4,  r.getInt(4)  +  one);  r.updateRow();

}

//  Addendum  new  records  r.moveToInsertRow();  r.updateString("Name", "Smirnov");  r.updateObject("Telephone",  "26-08-58");

r.updateInt("Age", 43);  r.insertRow();  r.moveToCurrentRow();  s.close();

10.7. Using precompiled queries. In those  teas,  when  carried out  a bunch of  similar  requests  to  DB,  different  only  parameters,  for  raise  performance  you can use precompiled queries. precompiled-  nym  requests  correspond  objects  classes  implementing  interface  PreparedStatement .  Are being created  such  objects  method

PreparedStatement  prepareStatement(String  sql)  throws  SQLException  PreparedStatement prepareStatement(String  sql,  int resultSetType,

int  resultSetConcurrency,  int  resultSetHoldability)  throws  SQLException

on the  connection object.  These  methods  accept  on the  entrance  pattern string  request,  containing  signs  question  on the  place  parameters,  For example,

INSERT  INTO  people(Name,  phone,  age)  VALUES (?,  ?,  ?)

Values  parameters  are given  through  call  methods

void  set***(int  parameterIndex,  ***  x)  throws  SQLException

void  setObject(int  parameterIndex,  Object  x)  throws  SQLException

*** is replaced by the Java data type name corresponding to the type  pu data SQL parameter (see table. [10.2](#part0036.xhtml__bookmark91) ). parameterIndex argument  defines the number of the precompiled query parameter to be set  sa.  Numbering  parameters  starts  with  units!

After the parameter values are set, the query is executed  through  call  one  from  methods:

![](Images/image00515.jpeg)boolean execute() throws SQLException  result set  executeQuery()  throws  SQLException  int  executeUpdate()  throws SQLException

similar  eponymous  methods  interface  Statement  (cm.  P.  [10.4](#part0034.xhtml__bookmark88) ).  Next  fragment  fills  table  from  example  P.  [10.4](#part0034.xhtml__bookmark88)[ ](#part0034.xhtml__bookmark88)data-  mi,  stored  in  array  objects,  using  at  this  precompiled-

рованный  запрос.

PreparedStatement  s  =  conn.prepareStatement(

"INSERT  INTO  people(Name,  Telephone,  Age)  VALUES(?,  ?,  ?)");  Object[][]  data  =  {

{  "Ivanov",  "12-02-00",  37  },

{  "Petrov",  "43–55–47",  26  },

{  "Sidorov",  "43–88–90",  59  }  };

for(int  i  =  0;  i  <  data.length;  ++i)

{

for(int j =  0; j  < data[i].length; ++j)  s.setObject(j  +  1,  data[i][j]);

s.execute();

}

s.close();

10.8. Transaction management. The default mode is  automatic commit transactions. This means that each  a request to the database is considered as a separate automatically fixed  transaction.  However  this  mode  can  disable,  causing  method

![](Images/image00479.jpeg)void  setAutoCommit( boolean  autocommit)  throws  SQLException

In this case, all transactions must be explicitly committed through  call  method

![](Images/image00479.jpeg)void  commit()  throws  SQLException

or  deviate  through  call  method

![](Images/image00479.jpeg)void  rollback()  throws  SQLException

If an error occurs during the execution of a transaction, the transaction  tion  automatically  is rejected.

JDBC does not require you to explicitly define the start of a transaction. First  the transaction starts at the moment the setAutoCommitMode() method is called ,  all  subsequent ones directly  after  call  methods  commit()  or  rollback()  for  commits  or  deviations  previous  transactions.

# 11. network  programming

11.1. Survey of means of network programming. Java support-  a wide range of tools and technologies for developing network applications  provisions. This includes: means of direct data transmission from  using the TCP and UDP protocols, protocol support tools  application level catches http, https, ftp, etc., technologies that extend  functionality of web pages on the client side (applets), as well as  functionality  web servers  (servlets  and  jsp),  technology  remote  procedure calls RMI (Remote Method Invocation), as well as technology  building  distributed  applications  Enterprise  Java  beans.

This chapter is only a brief introduction to the  tevy programming in Java. It considers the means of mutual  application interactions via TCP/IP sockets, as well as tools  obtaining web resources using application layer protocols  zheny.  All  they  are placed  in  package  java.net .

A more detailed description of the technologies for developing network applications  ny  can  to find  in  books  [ [1](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ,  [3](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ,  [4](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ,  [5](XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX) ].

11.2. Class  InetAddress.  Class  InetAddress  encapsulates  IP address  and host domain name. It has no visible ( public ) constructors, and  to create instances of this class, use the following pro-  manufacturing  methods:

![](Images/image00516.jpeg)static InetAddress getByName(String host) throws UnknownHostException  static  InetAddress  getByAddress(byte[]  addr)  throws  UnknownHostException  static  InetAddress  getLocalHost()  throws  UnknownHostException

The first one creates an instance by the domain name of the host (for example,  measures  [ ](http://www.uniyar.ac.ru/)),  second - by  his  IP address  given  massi-  vom of four numbers. Similar behavior can be obtained by  giving the first method a string of four numbers instead of a domain name,  divided  dots  (For example,  "193.233.51.122").  The third  method  created-  is an instance that encapsulates the address of the local host (usually  127.0.0.1). If a domain name is used to create an instance  host, then the getByName() method queries the DNS server for  to resolve this name to an IP address. If a  the required host was not found or the network connection is inactive, select  succumbs  exception  type  UnknownHostException .  This is  same  exception thrown when any other errors occur while executing  nenie  described  methods.

11.3. TCP sockets.  A socket is an abstraction used to pre-  setting a "socket", which includes a "cable" connecting the ho-  ports on a TCP/IP network. Because the same host can provide  various services, to identify a particular service, use  the number of the port to which the connection is made. Rooms  from  one  before  1024  reserved  for  systemic  services.

The Socket class is a class of TCP sockets used  to connect to a remote or local host. For creating  copies  this  class  are used  the following  constructors:

Socket(String host, int port) throws UnknownHostException, IOException  Socket(InetAddress  address,  int  port)  throws  IOException

Arguments  constructor  are  line,  containing  domain  name  host, or an object of type InetAddress encapsulating its IP address, and  also the port number of the host to connect to. At  When a socket object is created, an attempt is immediately made to set  leniya  connections  with  given  host.  If a  she is  ends  bad luck  thrown out  exception.

When  compound  established,  methods

![](Images/image00517.jpeg)InputStream getInputStream() throws IOException  OutputStream  getOutputStream()  throws  IOException

return  byte  streams  input  and  output  (cm.  P.  [7.1](#part0025.xhtml__bookmark55) ),  which  may  be  used  for  receiving  and  departures  data  host.

After  use  socket  should  be  necessarily  closed  middle-  stvom  call  method

![](Images/image00479.jpeg)void  close()  throws  IOException

Note that instances of the Socket class are used to set  leniya  connections  as  on the  side  client,  So  and  on the  side  server.  In this case, the interaction of the client with the server on the client side, as  usually boils down to just creating an instance of the Socket class , semi-  I/O streams and exchange of information with the server through  these  flows.

11.4. Establishing a connection on the server side. client-ser-  proper server-side interaction usually consists of steps  auditions  some  port  (through  this  port  to  server  maycontact customers), establishing a connection and exchanging data with  client. The second of these tasks is performed by the class discussed above  Socket (as noted above, client and server sockets between  du  yourself  not  differ),  third  —  classes  flows  input/  output.  For For the first task, a special ServerSocket class is used .  Name  this  class  is an  unsuccessful  insofar as  no  juice-  that it does not encapsulate. It would be more accurate to call him "listener  port."  For  creation  copies  class  used  constructor

![](Images/image00479.jpeg)ServerSocket( int  port)

receiving  on the  entrance  room  port,  subject  listening.  Os-  new  method  class  ServerSocket  is an  method

![](Images/image00479.jpeg)Socket  accept()  throws  IOException

which blocks the execution thread of the program until  no client will request a connection to the server. At the same time, auto-  a connection is established mathematically and a socket object is returned,  through which the connection is made. Usually the server calls  accept() method in a loop, passing socket objects to other threads you  completion,  which  carry out  service  clients.

At the end of the work, you must always close the listener object.  body  with  help  method

void  close()  throws  IOException

11.5. Example. This example demonstrates the simplest client-  server  Appendix.  "Mathematical  server"  accepts  from  client  two  numbers,  calculates  them  amount  and  returns  her  client.

import  java.io.*;

import  java.net.*;

/**  Class  "Mathematical  server"  */

public  class  MathServer

{

/**  Number  port,  which  listening  server  */

public  static  final  int  PORT  =  21370;

/**  Dot  entrance  in  program  */

public  static  void  main(String[]  args)  throws  IOException

{

ServerSocket  serv  =  new  ServerSocket(PORT);

try

{

// main loop  servers

while ( true )

{

//  Compound  and  receiving  flows  I/O

Socket  s  =  serv.accept();

try

{

BufferedReader  in  =  new  BufferedReader(

new InputStreamReader(s.getInputStream()));  PrintWriter  out  =  new  PrintWriter(

new  OutputStreamWriter(s.getOutputStream()),

true);

//  Receipt  data,  treatment  and  return  result

try

{

if (!in.ready())

throw new NumberFormatException();  int  a  =  Integer.parseInt(in.readLine());  if (!in.ready())

throw new NumberFormatException();  int  b  =  Integer.parseInt(in.readLine());  out.println(a  +  b);

in.close();

out.close();

}

catch (NumberFormatException e)

{

out.println("Invalid  format  input  data");

}

}

catch (Exception  e)

{

System.err.println("Error  I/O");

}

finally

{

s.close();  //  guaranteed  closing  client  socket

}

}

}

finally

{

serv.close(); //  guaranteed  closing  listener  port

}

}

}

Server  opens  port  21370,  after  what  included  in  endless  cycle  service  clients  (in  real  servers  should  provide for  full-time  way  completion  work).  how  only  arrives  request  from  client,  method  accept()  opens  corresponding  socket.  Server  chi-  melts  numbers,  transferred  him  client,  calculates  them  amount  and  returns  her  client.  If a  customer  forwarded  server  data  in  wrong  format  (For example,  one  number  instead of  two  or  transferred  not  numbers),  server  sends  client  message  about  error.  If a  in  process  input/output  Yes  arises  mistake,  server  displays  message  in  standard  flow  errors.  Regardless  from  Togo,  happened  mistake  or  No,  client  socket  closes  and  server  passes  to  expectation  next  request.  If the port is not open or the accept() method fails, then  relevant  exception  will  intercepted  handler  on  beg-

hope  and  Job  servers  will end.

The "math server" client is a console  Appendix. The input data is passed to the client via co-arguments.  mandline. It is assumed that the client is running on the same  machine as the server, however, this behavior can be easily changed by  modifications  addresses,  transmitted  method  getByName() .

import  java.io.*;

import  java.net.*;

/**  Class  "Customer  mathematical  server"  */

public  class  MathClient

{

public  static  void  main(String[]  args)  throws  IOException

{

if (args. length !=  2)

{

System.out.println("Invalid  call  programs");

return ;

}

//  Compound  and  receiving  flows  I/O  InetAddress  addr  =  InetAddress.getByName("127.0.0.1");  Socket  s  =  new  Socket(addr,  MathServer.PORT);

try

{

}

BufferedReader  in  =  new  BufferedReader(

new InputStreamReader(s.getInputStream()));  PrintWriter  out  =  new  PrintWriter(

new  OutputStreamWriter(s.getOutputStream()),  true);

// Отправка данных  серверу

out.println(args[0]  +  "\n"  +  args[1]);

//  Receipt  response  and  seal  his  on the  screen

System.out.println(in.readLine());

finally

{

s.close();  //  guaranteed  closing  client  socket

}

}

}

11.6. Support for application layer protocols. One of the most  more important classes that support network protocols  foot  level,  is an  Class  url .  He  encapsulates  URL  resource  World  Wide Web, and also allows you to get the content of this resource via  alone  from  next  protocols:  http,  https,  ftp,  file,  jar.

To create instances of a class, as a rule, the con-  constructor

![](Images/image00479.jpeg)URL(String  url)  throws  MalformedURLException

For  establishing  connections  and  discoveries  input  flow,  bound-  foot  with  required  resource,  used  method

![](Images/image00479.jpeg)InputStream openStream()  throws  IOException

It returns a stream that can be used to get co-  held  requested  resource.

The following example demonstrates the use of the URL class . He  reads the content of the resource specified by the URL and writes it to  file.  URL  resource  and  name  weekend  file  are given  parameters  entrance-  Noah  lines.

![](Images/image00479.jpeg)import  java.io.*;

import  java.net.*;

class  getfile

{

public  static  void  main(String  args[])

{

if (args. length !=  2)

{

}

try

{

}

System.out.println("Invalid  call  programs");

return ;

URL  url  =  new  URL(args[0]);  String  filename  =  args[1];  InputStream  in  =  url.openStream();

FileOutputStream  out  =  new  FileOutputStream(filename);

int  b;

while ((b  =  in.read())  !=  -one)  out.write(b);

in.close();

out.close();

catch (IOException  e)

{

System.err.println("Error  I/O");

}

}

}