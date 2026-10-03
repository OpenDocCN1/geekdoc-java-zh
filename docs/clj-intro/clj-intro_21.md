
# 宏

宏是用来给语言添加新的结构、新的元素的机制。它们会在读入期（而不是编译期）实际进行代码替换。

对于函数来说，它们的所有参数都会被求值，而宏则会自动判断哪些参数需要求值。这对于实现类似`(if _condition_ _then-expr_ _else-expr_)`这样的结构非常重要。如果`condition`是`true`，那么只有`then`表达式需要被求值；如果条件是`false`，那么只有`else`表达式应该被求值。这意味着`if`不能被实现成一个函数（它其实也不是宏，而是一个特殊形式）。

其它一些因为这个原因而必须实现成宏的结构包括`and`和`or`，因为它们需要实现“短路”属性。

## 判断函数还是宏

要想知道一个东西到底是函数还是宏，可以在 REPL 里面输入`(doc _name_)`，或者查看它的元数据。如果是一个宏，那么它的元数据里面包含一个`:macro`键，并且它的值为`true`。

比如，要查看`and`是不是宏，可以在 REPL 里面输入下面的命令：

```java
((meta (var and)) :macro) ; long way -> true
(^#'and :macro) ; short way -> true
```

## 定义宏

让我们通过一些例子来看看如何编写并使用宏。假设代码里面很多地方要对一个数字进行判断，通过判断它是接近 0、是正数还是负数来执行不同的逻辑；我们又不想这种判断代码到处重复，那么这种情况下就可以使用宏了。我们使用`defmacro`宏来定义一个宏。

```java
(defmacro around-zero [number negative-expr zero-expr positive-expr]
  `(let [number# ~number] ; so number is only evaluated once
    (cond
      (< (Math/abs number#) 1e-15) ~zero-expr
      (pos? number#) ~positive-expr
      true ~negative-expr)))
```

Clojure 的 reader 会把所有调用`around-zero`的地方全部换成`defmacro`方法体里面的具体代码。这里使用`let`是为了性能，因为传进来的`number`是一个表达式而不是一个简单的值，而且被`cond`语句使用了两次。

自动产生的变量`number#`是为了产生一个不会和用户指定的其它 binding 冲突的名字。这使得我们可以创建[hygienic macros](http://en.wikipedia.org/wiki/Hygienic_macros)。

宏定义开始时的反引号（也称为语法引号）会防止宏体内的表达式被求值，除非显式地进行转义。这意味着宏体里面的代码会原封不动地替换到使用这个宏的所有地方，除了以波浪号开始的表达式（`number`、`zero-expr`、`positive-expr`和`negative-expr`）。

当一个名字前面被加了波浪号，并且还在反引号里面时，它的值会被替换。如果这个名字代表的是一个序列，那么可以使用`~@`语法来替换序列里面的具体元素。

## 使用宏

下面是两个使用这个宏的例子，输出都应该是`+`：

```java
(around-zero 0.1 (println "-") (println "0") (println "+"))
(println (around-zero 0.1 "-" "0" "+")) ; same thing
```

如果对于每种条件要执行多于一个表达式，那么用`do`把它们包起来。看下面的例子：

```java
(around-zero 0.1
  (do (log "really cold!") (println "-"))
  (println "0")
  (println "+"))
```

为了验证这个宏是否被正确展开，可以在 REPL 里面输入：

```java
(macroexpand-1
  '(around-zero 0.1 (println "-") (println "0") (println "+")))
```

它会输出下面这个结果。为了容易看懂，这里添加了缩进：

```java
(clojure.core/let [number__3382__auto__ 0.1]
  (clojure.core/cond
    (clojure.core/< (Math/abs number__3382__auto__) 1.0E-15) (println "0")
    (clojure.core/pos? number__3382__auto__) (println "+")
    true (println "-")))
```

下面是一个使用这个宏来返回描述输入数字属性的字符串的函数：

```java
(defn number-category [number]
  (around-zero number "negative" "zero" "positive"))
```

下面是一些示例用法：

```java
(println (number-category -0.1)) ; -> negative
(println (number-category 0)) ; -> zero
(println (number-category 0.1)) ; -> positive
```

因为宏不会求值它们的参数，所以可以在宏体里面写一个对函数参数的调用。函数定义不能这么做；相反，只能用匿名函数把它们包起来。

下面是一个接受两个参数的宏。第一个参数是一个接受一个参数的函数，这个参数是一个弧度。如果它是一个三角函数，比如`sin`或`cos`，第二个参数就是一个弧度。

如果将其写成函数而不是宏，就需要传递`#(Math/sin %)`而不是简单的`Math/sin`作为参数。注意后面的`#`符号，它会产生一个唯一且不冲突的本地 binding。`#`和`~`都必须在反引号引着的列表里面才能使用。

```java
(defmacro trig-y-category [fn degrees]
  `(let [radians# (Math/toRadians ~degrees)
         result# (~fn radians#)]
     (number-category result#)))
```

让我们试一下。下面代码的期望输出应该是`zero`、`positive`、`zero`和`negative`。

```java
(doseq [angle (range 0 360 90)] ; 0, 90, 180 and 270
  (println (trig-y-category Math/sin angle)))
```

## 宏作为参数

宏的名字不能作为参数传递给函数。例如，宏的名字`and`不能作为参数传递给`reduce`函数。

一种绕过方法是定义一个匿名函数把这个宏包起来，例如`(fn [x y] (and x y))`或`#(and %1 %2)`。宏会在读入期在这个匿名函数体内展开。当这个函数被传递给`reduce`等函数时，传递的是函数而不是宏。

宏的调用是在读入期处理的。
