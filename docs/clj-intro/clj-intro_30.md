
# 库

很多类库提供了 Clojure 本身没有提供的一些功能。我们在前面的例子中已经讨论过一些，下面列举一些尚未提到的类库。这里还有一个已知类库的列表：[`clojure.org/libraries`](http://clojure.org/libraries)。

- `clojure.tools.cli`：操作命令行参数并输出帮助信息。
- `clojure.data.xml`：以 lazy 的方式解析 XML。
- `clojure.algo.monads`：提供有关 [monads](http://en.wikipedia.org/wiki/Monad_(functional_programming)) 的一些方法。
- `clojure.java.shell`：提供一些函数和宏，用于创建子进程并控制它们的输入/输出。
- `clojure.stacktrace`：提供函数来简化 stacktrace 的输出，只输出与 Clojure 有关的内容。
- `clojure.string`：提供用于操作字符串和正则表达式的一些方法。
- `clojure.tools.trace`：提供跟踪所有对某个方法的调用及其返回值的输出。

下面是一个使用 `clojure.java.shell` 获取当前工作目录的简要例子。

```java
(use 'clojure.java.shell)
(def directory (sh "pwd"))
```
