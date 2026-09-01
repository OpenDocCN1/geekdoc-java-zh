
# 编译

## 编译

当 Clojure 的源代码文件被当作脚本文件执行时，它们会在运行时被编译成 Java bytecode。同时，我们也可以提前编译（AOT，ahead-of-time）它们为 Java bytecode。这会缩短 Clojure 程序的启动时间，并且产生的 `.class` 文件还可以供 Java 程序使用。我们推荐按照下面的步骤来做：

1. 为你要编译的文件选择一个名字空间，比如：`com.ociweb.talk`。
2. 在父目录里面创建两个目录：`src` 和 `classes`。
3. 使其中一个文件的文件名和包名的最后一段相同，比如：`talk.clj`。
4. 把源文件放在 `src` 目录下面，并且创建和名字空间一样的目录层级，比如：`src/com/ociweb/talk.clj`。
5. 在源代码的最上面给文件指定名字空间，并且包含 `:gen-class` 标记：`(ns com.ociweb.talk (:gen-class))`。
6. 在主源文件里面，使用 `load` 函数来加载同一个目录下面的其它源文件。比如，如果 `more.clj` 在目录 `src/com/ociweb` 的子目录 `talk` 下面，那么使用这个语句来加载：`(load "talk/more")`。
7. 在其它源文件里面，使用 `in-ns` 函数来设置它们的名字空间。比如，在 `more.clj` 文件上面指定名字空间：`(in-ns 'com.ociweb.talk)`。
8. 把 `src` 和 `classes` 目录添加到 REPL 的 classpath 里面。如果使用脚本来运行 REPL，那么修改那个脚本。
9. 启动一个 REPL。
10. 使用 `compile` 函数来编译一个给定名字空间的 Clojure 文件：`(compile '_namespace_)`。比如：`(compile 'com.ociweb.talk)`。

这些步骤会为每个函数创建一个单独的 `.class` 文件。它们会被写到 `classes` 文件夹下对应的子文件夹下面。

如果被编译的名字空间有一个叫做 `-main` 的函数，那么你可以把它当作 Java 的主类来运行。命令行参数会被当作参数传递给这个函数。比如，如果 `talk.clj` 包含一个叫 `-main` 的函数，你可以用下面的命令来运行：

```java
java -classpath <em>path</em>/classes:<em>path</em>/clojure.jar com.ociweb.talk <em>args</em>
```

# 在 Java 里面调用 Clojure

提前编译的 Clojure 函数如果是静态函数，那么它们可以被 Java 程序调用。可以通过把函数的元数据项 `:static` 设置为 `true` 来达到这个目的。语法是这样的：

```java
(ns <em>namespace</em>
  (:gen-class
   :methods [#^{:static true} [<em>function-name</em> [<em>param-types</em>] <em>return-type</em>]]))
```

让我们看一个例子：下面是一个名字叫做 `Demo.clj` 的文件，它的路径是 `src/com/ociweb/clj`。

```java
(ns com.ociweb.clj.Demo
  (:gen-class
   :methods [#^{:static true} [getMessage [String] String]]))

# Note the hyphen at the beginning of the function name!
(defn -getMessage [name]
  (str "Hello, " name "!"))
```

下面是一个叫做 `Main.java` 的 Java 文件，它和 `src` 以及 `classes` 在同一个目录。

```java
import com.ociweb.clj.Demo; // class created by compiling Clojure source file

public class Main {

    public static void main(String[] args) {
        String message = Demo.getMessage("Mark");
        System.out.println(message);
    }
}
```

下面是编译并且运行它的步骤：

1. `cd` 到包含 `src` 和 `classes` 的目录。
2. 通过 `clj` 命令来打开一个 REPL。
3. 运行 `(compile 'com.ociweb.clj.Demo)`。
4. 退出 REPL（Ctrl-D 或者 Ctrl-C）。
5. 运行 `javap -classpath classes com.ociweb.clj.Demo` 来查看生成的 class 文件里面的方法。
6. 运行 `javac -cp classes Main.java`。
7. 运行 `java -cp .:classes:_path_/clojure.jar Main.java`。注意，Windows 下面的路径分隔符是分号而不是冒号。
8. 输出应该是 `Hello, Mark!`。

Clojure 还有一些更加高级的编译特性。更多细节可以参考宏 [`gen-class`](http://clojure.github.com/clojure/clojure.core-api.html#clojure.core/gen-class) 的文档以及 [`clojure.org/compilation/`](http://clojure.org/compilation)。
