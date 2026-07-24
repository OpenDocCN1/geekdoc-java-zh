![](images/00001.jpeg)

Lambda Expressions in Java 8

VLIGHT

Table Of Contents

[Why Lambdas](#part0000_split_002.html__Toc470969056)

[Standard syntax](#part0000_split_003.html__Toc470969057)

[Parameter type can be inferred](#part0000_split_004.html__Toc470969058)

[Multiple lines of code](#part0000_split_005.html__Toc470969059)

[Single parameter with inferred types](#part0000_split_006.html__Toc470969060)

[Method references](#part0000_split_007.html__Toc470969061)

# 
Why Lambdas

In Java 8, a Lambda Expression is nothing but a block of code which can be passed around to execute

You need to create an object then pass the object around if you want a block of code to be executed

Lambda Expressions are very powerful and compelling

A Lambda Expression can be declared in some ways as follows:

+ Standard syntax

+ Parameter type can be inferred

+ Multiple lines of code

+ Single parameter with inferred types

+ Method references

# 
Standard syntax

The standard syntax of a lambda expression has the following blocks:

+ A comma-separated list of formal parameters which are enclosed in the parenthesis

+ The arrow (->)

+ A body which consists of a single expression or a block of code

Sample Code

String[] friendList = {"Tuan", "Nam", "Lan"};

Arrays.sort(friendList,

(String friend01, String friend02) ->

 Integer.compare(friend01.length(), friend02.length()));

System.out.print(Arrays.toString(friendList));

Output

[Lan, Nam, Tuan]

# 
Parameter type can be inferred

The parameter types can be omitted if they can be inferred from the context. This makes your code more cleaner

Sample Code

String[] friendList = {"Tuan", "Nam", "Lan"};

Arrays.sort(friendList,

(friend01, friend02) ->

 Integer.compare(friend01.length(), friend02.length()));

System.out.print(Arrays.toString(friendList));

Output

[Lan, Nam, Tuan]

# 
Multiple lines of code

If your code cannot be written in 1 line, it can be enclosed in {} and your code now should explicitly contain a return statement

Sample Code

String[] friendList = {"Tuan", "Nam", "Lan"};

Arrays.sort(friendList,

(String friend01, String friend02) ->

{

   if (friend01.length() > friend02.length())

      return -1;

   else

      return 0;

});

System.out.print(Arrays.toString(friendList));

Output

[Lan, Nam, Tuan]

# 
Single parameter with inferred types

You can omit the parenthesis for a single parameter when its type can be inferred

Sample Code

String[] friendList = {"Tuan", "Nam", "Lan"};

Stream<String> friendStream = Stream.of(friendList);

stream.forEach(friend -> System.out.println(friend));

Output

Tuan

Nam

Lan

# 
Method references

You can reduce code using the method reference (::)

Sample Code

String[] friendList = {"Tuan", "Nam", "Lan"};

Stream<String> friendStream = Stream.of(friendList);

stream.forEach(System.out::println);

Output

Tuan

Nam

Lan