
# Java 接口

> 原文：<https://medium.com/javarevisited/interface-in-java-99e6838addff?source=collection_archive---------1----------------------->

![](img/7e57286293a6ef918d63aff6addf6d50.png)

接口是 Java 的一个非常重要的特性，它的定义以关键字`interface`开始。很像一个类，但有些不同。基本上，通过`interface`关键字，你可以在 Java 中声明和定义一个接口。

```
接口 接口_名称
{
………………………………….
}
```

一个[接口](https://javarevisited.blogspot.com/2012/04/10-points-on-interface-in-java-with.html)基本上指定了方法声明并包含字段或变量。

```
接口 接口名称
{
int a = 5；
void 方法1()；
}
```

注意：任何接口的方法都是隐式的`public`和`abstract`，变量是`public static`和`final`。

## 如何实现一个接口？

```
接口 IOne
{
int a = 5；
void 方法1()；
}

A类实现 IOne{
公共 void 方法1(){
system.out.println(a)；
}
}
```

Java 中的类基本都是通过关键字`implements`来实现接口。

现在看一个例子：

```
接口 A {
void print()；
}

类 B 实现 A
{
public void print()
{
system.out.println("It is warm up")；
}
}

public class Main {
public static void main(String[] args){
A a；//接口引用
a = new B()；//接口引用 a 引用的 B 类实例
a.print()；
}
}
```

你可以在上面的程序中看到，接口 A 包含一个由实现接口 A 的类 B 定义和实现的方法`print()`。由于一个[接口](https://www.java67.com/2012/09/what-is-difference-between-interface-abstract-class-java.html)的方法在该接口中没有任何实现，它们由实现该接口的类来实现。

现在仔细看看主类。一个接口创建了一个引用`a`，但是这个引用引用了实现这个接口的 B 类实例。基本上，问题是，**接口不能被实例化**。它创建引用，并且该引用引用实现该接口的任何类的实例。

看另一个例子：

```
public interface myInterface {
int a = 10；//公共、静态和最终
void display()；//公共和抽象
}

class myClass implements myInterface {
public void display() //实现抽象方法
{
System.out.println("好吧！")；
}

public static void main(String[] args){
myClass m = new myClass()；
m.display()；
system.out.println("myInterface 中的最终值 a "+a)；
}
}
```

**要点记住：**

1. 无法实例化接口。
2. 接口没有构造函数。

## 一个接口可以扩展另一个接口：

```
interface I1 {
double x = 4.444；
void method1()；
}

interface I2 extends I1 {
double y = 5.555；
void method2()；//默认情况下为公共静态
}

class A1 implements I2 {
public void method1(){
System.out.println("来自 I1:"+(x+y))；
}

public void method2(){
system.out.println("From I2:"+(x+y))；
}
}

public class myClass{
public static void main(String[] args){
A1 a = new A1()；
a.method1()；
a.method2()；
}
}
```

这里 I2 接口扩展了接口 I1 并继承了它的属性。因此，当类 A 实现 I2 时，它也可以使用 I1 的属性。

## 接口的多重扩展：

```
package blog；

public interface IOne {
void print1()；
}

public interface ITwo {
void print2()；
}

public interface IThree extends IOne, ITwo{
void print3()；
}
```

```
package blog；

public class Main implements IThree{
public void print1(){
system.out.println("IOne 的方法")；
}

public void print2(){
system.out.println("ITwo 的方法")；
}

public void print3(){
system.out.println("IThree 的方法")；
}

public static void main(String[] args){
Main m1 = new Main()；
m1.print1()；
m1.print2()；
m1.print3()；
}
}
```

## 嵌套接口：

一个接口可以被声明为一个类或另一个接口的成员。这样的接口被称为**嵌套接口**。一个嵌套的接口可以声明为`public`、`private`、`protected`。

```
package nestedInterface；

public class A{
public interface Nestin
{
boolean nonNegative(int x)；
}
}

class B implements A.Nestin
{
public boolean nonNegative(int x)
{
return x < 0 ? false : true；
}
}
```

```
package nestedInterface；

public class Main {
public static void main(String[] args){
A.Nestin i1 = new B()；
System.out.println(i1.nonNegative(-1))；
system.out.println(i1.nonNegative(5))；
}
}
```

## 相关主题：

- [为什么 Java 不支持多重继承？](https://javarevisited.blogspot.com/2011/07/why-multiple-inheritances-are-not.html)
- [Java 中的继承](https://javarevisited.blogspot.com/2012/10/what-is-inheritance-in-java-and-oops-programming.html)
