

# REPL

REPL 是 read-eval-print loop 的缩写。这是 Lisp 的方言提供给用户的一种标准交互方式。如果用过 Python，应该使用过类似工具：你输入一个表达式，它立刻输出结果，然后继续输入，如此循环。REPL 是一个非常有用的学习语言和测试特性的工具。

## 启动 REPL

为了启动 REPL，运行我们上面写好的`clj`脚本。成功的话会显示一个`user=>`。`=>`前面的字符串表示当前的默认名字空间，`=>`后面则是你输入的 form 以及它的输出结果。下面是一个简单的例子：

```java
user=> (def n 2)
#'user/n
user=> (* n 3)
6 
```

`def`是一个 special form，它相当于 Java 里面的定义加赋值语句。它的输出表示一个名字叫`n`的 symbol 被定义在当前的名字空间`user`里面。

## 查看文档

要查看一个函数、宏或者名字空间的文档，输入`(doc _name_)`。看下面的例子：

```java
(require 'clojure.contrib.str-utils)
(doc clojure.contrib.str-utils/str-join) ; ->
; -------------------------
; clojure.contrib.str-utils/str-join
; ([separator sequence])
;   Returns a string of all elements in 'sequence', separated by
;   'separator'.  Like Perl's 'join'. 
```

如果要查找所有包含某个字符串的函数或宏的文档，那么输入命令`(find-doc "_text_")`。

如果要查看一个函数或宏的源代码，使用`(source _name_)`。`source`是一个定义在`clojure.contrib.repl-utils`名字空间里面的宏，REPL 会自动加载这个宏。

## 加载并执行文件

如果要加载并执行文件里面的 Clojure 代码，使用命令`(load-file "_file-path_")`。Clojure 源文件一般以`.clj`作为后缀。

## 退出 REPL

如果要退出 REPL，在 Windows 下面输入`ctrl-z`然后回车，或者直接输入`ctrl-c`；在其他平台下（包括 UNIX、Linux 和 Mac OS X），输入`ctrl-d`。

