
# Java 中编译器生成的类、方法和字段

> 原文：<https://medium.com/javarevisited/compiler-generated-classes-methods-and-fields-in-java-343dde2cce61?source=collection_archive---------0----------------------->

## 看看编译器在什么情况下可以生成什么。

![](img/ca0a7fc66b63c4d2550c7f50291e0533.png)

[来源](https://unsplash.com/photos/tdsG7cUNrOo)

## 介绍

当我们用 Java 编写程序时，我们创建一些类、方法、字段，并将所有这些放入我们的源代码— `.java`文件中。这些文件用`javac`（Java 编译器）编译成`.class`文件后，我们得到了一堆 Java 字节码。

事实证明，不仅我们在源代码中创建类、方法和字段，编译器本身也可以在需要时创建它们。

在本文中，我们将尝试进入编译器生成的主题，了解什么是合成和桥接、访问标志，从官方文档中了解一些新的东西，也许还有更多。让我们开始吧。

## 综合定义

类、方法和字段可以是合成的，这意味着它不会出现在源代码中（因此是由编译器生成的）。

参考[参考](https://docs.oracle.com/javase/specs/jvms/se7/html/jvms-4.html#jvms-4.7.8)

基本上就这么简单。如果某些东西是由编译器生成的（不在源代码中），那么编译器必须将这些生成的东西标记为合成的。

> **注意**：这种规则也有例外，比如默认构造函数——它不会被标记为合成的。在[规范](https://docs.oracle.com/javase/specs/jvms/se7/html/jvms-4.html#jvms-4.7.8)中可以找到例外的完整列表。

### 嵌套类

编译器使用 synthetic 的经典例子是嵌套类（包含对父类的引用）。首先我们来看看内部（静态）类和生成的字节码。

我们的例子将是：

```
class Main { static Child { }
}
```

接下来我们用`javac Main.java`进行编译，会产生两个文件：`Main.class`和`Main$Child.class`。

为了查看生成的代码，我们将使用`javap`：`javap -v Main\$Child.class`

生成结果的一部分将是：

```
{
  Main$Child();
    descriptor: ()V
    flags:
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1   // Method java/lang/Object."<init>":()V
         4: return
```

这里我们看到的是用默认构造函数（`<init>`）声明的类。不会。任何对主类的引用都由子类保存（因为它是静态的）。

如果我们移除静态修改器并重复该过程，我们将会看到：

```
class Main$Child
...
{
  final Main this$0;
    descriptor: LMain;
    flags: ACC_FINAL, ACC_SYNTHETIC Main$Child(Main);
    descriptor: (LMain;)V
    flags:
    Code:
      stack=2, locals=2, args_size=2
         0: aload_0
         1: aload_1
         2: putfield      #1     // Field this$0:LMain;
         5: aload_0
         6: invokespecial #2     // Method java/lang/Object."<init>":()V
         9: return
```

正如我们看到的，我们现在有了对父类的`this$0`引用，它在构造函数内部传递。

还要注意那个字段有`ACC_SYNTHETIC`标志，这表明这个字段是合成的——是由编译器生成的。

这种对父类的引用不是为了以防万一而添加的，它在嵌套类想要访问父类的实例方法和字段（包括私有方法和字段）的情况下很有用。

例如：

```
class Main { private void foo() {} class Child {

        private void bar() {
            foo();
        }
    }
}
```

这里我们将使用带有`-p`标志的`javap`来查看私有成员：

```
class Main$Child
...
{
  final Main this$0;
    descriptor: LMain;
    flags: ACC_FINAL, ACC_SYNTHETIC Main$Child(Main);
    descriptor: (LMain;)V
    flags:
    Code:
      stack=2, locals=2, args_size=2
         0: aload_0
         1: aload_1
         2: putfield      #1     // Field this$0:LMain;
         5: aload_0
         6: invokespecial #2     // Method java/lang/Object."<init>":()V
         9: return
      LineNumberTable:
        line 4: 0 private void bar();
    descriptor: ()V
    flags: ACC_PRIVATE
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: getfield      #1          // Field this$0:LMain;
         4: invokestatic  #3          // Method Main.access$000:(LMain;)V
         7: return
```

在这里，我们不仅看到合成字段，而且我们的私有方法`bar`也在引用父方法来调用方法`acess$000`。但这是什么？让我们来看看 Main 类的字节码：

```
class Main
...
{
  Main();
    descriptor: ()V
    flags:
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #2      // Method java/lang/Object."<init>":()V
         4: return
      LineNumberTable:
        line 1: 0 private void foo();
    descriptor: ()V
    flags: ACC_PRIVATE
    Code:
      stack=0, locals=1, args_size=1
         0: return
      LineNumberTable:
        line 2: 0 static void access$000(Main);
    descriptor: (LMain;)V
    flags: ACC_STATIC, ACC_SYNTHETIC
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1                  // Method foo:()V
         4: return
```

这里我们看到不仅有私有的 foo 方法，还有静态方法`access$000`，它也有`ACC_SYNTHETIC`标志——所以它也是合成的。它是由编译器为子类生成的，以便能够访问私有方法 foo。

### $

特别需要注意生成代码中`$`符号的用法。它被大量使用，尤其是对于由编译器生成的东西。因此，不建议在类、方法、字段等中使用`$`符号。java 源代码中的名字。

### 匿名类

下一个例子我们将看看匿名类。我们将尝试创建一些 runnable，看看字节码中会有什么。

```
class Main { void foo() {
        new Runnable() { public void run() {}
        };
    }
}
```

我们会看到会有两个`.class`文件：`Main.class`和`Main$1.class`。第二个是为我们的匿名`Runnable`创建的，在里面我们会看到以下内容：

```
class Main$1 implements java.lang.Runnable
...
{
  final Main this$0;
    descriptor: LMain;
    flags: ACC_FINAL, ACC_SYNTHETIC Main$1(Main);
    descriptor: (LMain;)V
    flags:
    Code:
      stack=2, locals=2, args_size=2
         0: aload_0
         1: aload_1
         2: putfield      #1     // Field this$0:LMain;
         5: aload_0
         6: invokespecial #2     // Method java/lang/Object."<init>":()V
         9: return
      LineNumberTable:
        line 4: 0 public void run();
    descriptor: ()V
    flags: ACC_PUBLIC
    Code:
      stack=0, locals=1, args_size=1
         0: return
```

这里我们看到同样的画面：匿名类在一个合成字段中保持对父类的引用。

### 类型擦除和桥接方法

在 Java 中使用泛型有一个重要的限制：泛型在运行时不可用。在编译时删除关于泛型的所有信息的过程称为类型擦除。

这意味着如果你在生成的字节码中使用 in 代码`List<String>`，它将变成没有任何泛型的`List`。应用这一点，让我们想象一下在下面的情况下会发生什么。我们将创建一些类，并使其与相同类型的类具有可比性。

```
class MyInt implements Comparable<MyInt> { public int compareTo(MyInt other) {
        return 0; // TODO: implement
    }
}
```

如果我们应用类型擦除，这将意味着我们的类将有效地拥有方法`compareTo(MyInt other)`，同时在没有任何类型信息的情况下实现 Comparable（这意味着我们正在使用`Object`）。在这种情况下，由于我们没有`compareTo(Object other)`方法，似乎没有什么会起作用。

这里来帮助特殊类型的合成——桥方法。

如果我们反编译我们的`MyInt.class`：

```
class MyInt extends java.lang.Object implements java.lang.Comparable<MyInt>
...
{
  MyInt();
    descriptor: ()V
    flags:
    Code:
      stack=1, locals=1, args_size=1
         0: aload_0
         1: invokespecial #1   // Method java/lang/Object."<init>":()V
         4: return
      LineNumberTable:
        line 1: 0public int compareTo(MyInt);
    descriptor: (LMyInt;)I
    flags: ACC_PUBLIC
    Code:
      stack=1, locals=2, args_size=2
         0: iconst_0
         1: ireturn
      LineNumberTable:
        line 4: 0public int compareTo(java.lang.Object);
    descriptor: (Ljava/lang/Object;)I
    flags: ACC_PUBLIC, ACC_BRIDGE, ACC_SYNTHETIC
    Code:
      stack=2, locals=2, args_size=2
         0: aload_0
         1: aload_1
         2: checkcast     #2      // class MyInt
         5: invokevirtual #3      // Method compareTo:(LMyInt;)I
         8: ireturn
```

我们在这里看到，除了我们的`compareTo(MyInt)`方法之外，我们还有用`ACC_SYNTHETIC`标记的`compareTo(javalang.Object)`方法，这意味着它是合成的。而且它还有`ACC_BRIDGE`旗。

桥接方法所做的是处理类型擦除方法，并在检查提供的值类型后（由`checkcast`）将调用重定向到方法的原始类型版本。

## 结论

合成和桥接是非常强大的概念，它们允许我们拥有一些功能，如果我们没有它们，拥有它们会有问题。其他语言如 Kotlin 在某些特性上也依赖于 synthetic，尤其是在增加 Java 兼容性时。例如方法中的默认参数。希望这篇文章对你有用。

编码快乐！

*感谢阅读！

如果你喜欢这篇文章，你可以点击* ***来喜欢它👏按钮***（最多 50 次！），也可以* ***分享*** *这篇文章来帮助别人。*

*有什么反馈，随时在*[*Twitter*](https://twitter.com/krossovochkin)*[*Facebook*](https://www.facebook.com/vasya.drobushkov)上联系我*

*<https://twitter.com/krossovochkin> *
