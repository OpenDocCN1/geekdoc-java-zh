
# 练习题

## 11.6 编写以下内容的尾递归版本：

### (a) 计算整数对数，底为 2
```scheme
;; (二进制表示中的位数)
;; 仅适用于正整数
(define log2
  (lambda (n)
    (if (= n 1) 1 (+ 1 (log2 (quotient n 2))))))
```

### (b) 在列表中寻找最小元素
```scheme
(define min
  (lambda (l)
    (cond
      ((null? l) '())
      ((null? (cdr l)) (car l))
      (#t (let ((a (car l)) (b (min (cdr l)))))
           (if (< b a) b a)))))
```

## 11.7 编写纯 Scheme 函数来：

### (a) 返回给定列表的所有旋转
例如，`(rotate '(a b c d))` 应该返回 `((a b c d) (b c d a) (c d a b) (d a b c))` 的某种顺序。

### (b) 返回一个包含给定列表中满足谓词元素的列表
例如，`(filter (lambda (x) (< x 5)) '(3 9 5 2 4 7))` 应该返回 `'(3 2 4)`。

## 11.8 编写一个纯 Scheme 函数，返回给定列表的排列列表
例如，给定 `'(a b c)`，它应该返回 `((a b c) (b a c) (b c a) (a c b) (c b a))` 的某种顺序。

## 11.9 修改图 11.1 中的 Scheme 程序或图 11.3 中的 OCaml 程序以模拟 NFA（非确定性自动机），而不是 DFA
这些自动机之间的区别在第 2.2.1 节中描述。由于在面对多值转移函数时你无法正确“猜测”，你需要使用显式编码的回溯来搜索接受的移动序列（如果有），或者跟踪机器在给定时刻可能处于的所有可能状态。

## 11.10 考虑确定两棵树是否具有相同边缘
即相同顺序的叶节点集合，无论内部结构如何。解决此问题的明显方法是写一个 `flatten` 函数，它接受树作为参数并返回其叶子的有序列表。然后我们可以说：

```scheme
(define same-fringe
  (lambda (T1 T2)
    (equal? (flatten T1) (flatten T2))))
```

编写一个简单的 `flatten` 版本。当你使用 `delay` 时，`same-fringe` 的效率如何？在 Haskell 这种使用惰性求值的语言中，你的答案会有何不同？

假设我们定义输入为一个函数——一个承诺（promise），其 `cdr` 是一个输出流（ostream）：

```scheme
(define driver
  (lambda (s)
    (if (null? s)
      '()
      (cons (car s) (driver (cdr s))))))
```

编写作用于流的新 `car` 和 `cdr` 版本。使用它们重写上一个练习的代码以消除对 `force` 的调用。

## 11.11 在 Scheme 中编写标准的快速排序算法，不使用命令式特性
比较你的排序运行时间和空间需求。

## 11.12 编写操作二叉搜索树的 `insert` 和 `find` 例程
解释为什么平凡的更新不会影响 `insert` 的渐进属性。

## 11.13 在纯函数式 Scheme 中编写 LL(1) 解析生成器
如果你考虑图 2.24，请记住你需要使用递归代替迭代。假设上下文无关文法（CFG）由列表列表组成，语法中包含一个非终结符。每个子列表的第一个元素应该是非终结符；其余元素应该是产生式的右侧。你可以假设起始符号的子列表是列表中的第一个。如果我们使用字符串来表示语法符号，图 2.16 的计算器文法如下：

```text
("program" "stmt_list" "$")
("stmt_list" "stmt" "stmt_list") ()
("stmt" "id" ":=" "expr")
("write" "write" "expr")
("expr" "term" "term_tail")
("term" "factor" "factor_tail")
("term_tail" "add_op" "term" "term_tail") ()
("factor_tail" "mult_op" "factor" "FT") ()
("add_op" "+") ("-/")
("mult_op" "*") ("*/")
("factor" "id" "number") ("(" expr ")")
```

你的输出应该是具有相同格式的解析表，只是每个右侧被替换为一个对（两个元素列表），其第一个元素是对应产生式的预测集，第二个元素是右侧。对于计算器文法，该表如下：

```text
("program" "$" "id" "read" "stmt_list" "$")
("stmt_list" "stmt" "stmt_list") ()
("stmt" "id" "id" ":=" "expr")
("read" "id")
("write" "write" "expr")
("expr" "term" "term_tail")
("term" "factor" "factor_tail")
("term_tail" "add_op" "term" "term_tail") ()
("factor_tail" "mult_op" "factor" "FT") ()
("add_op" "+") ("-/")
("mult_op" "*") ("*/")
("factor" "id" "number") ("(" expr ")")
```

### 提示
你可能想要定义一个 `right_context` 函数，它接受一个非终符 B 作为参数，并返回所有对 (A, β) 的列表，其中 A 是非终符，β 是符号列表，且对于某个可能不同的符号列表 α → α β。该函数对于计算 FOLLOW 集合很有用。你可能想要构建一个尾递归函数，不断重新计算 FIRST 和 FOLLOW 集合，直到它们收敛。你会发现这两个集合中都不包含 ε，而是为每个非终符维护一个单独的估值，判断它是否可能生成 ε。

## 11.16 编写一个等价运算符（命名为 `=`）
使其能够正确处理示例 11.38 中提到的关于昨天的例子。你可能需要查找控制闰年出现的规则。

## 11.17 为侧栏 11.3 中引入的摄氏（celsius）和华氏（fahrenheit）温度类型创建加减法函数
为了允许这两个量程进行混合，你还应该定义转换函数 `ct_of_ft : fahrenheit_temp -> celsius_temp` 和 `ft_of_ct : celsius_temp -> fahrenheit_temp`。你的转换应该保留到最接近的度（四舍五入）。

## 11.18 我们可以使用函数在 OCaml 中定义求值

```ocaml
type 'a delayed_list =
  Pair of 'a * 'a delayed_list
| Promise of (unit -> 'a * 'a delayed_list)

let head = function
| Pair (h, r) -> h
| Promise (f) -> let (a, b) = f() in a

let rest = function
| Pair (h, r) -> r
| Promise (f) -> let (a, b) = f() in b
```

现在给定：

```ocaml
let rec next_int n = (n, Promise (fun () -> next_int (n + 1)))
let naturals = Promise (fun () -> next_int 1)
```

我们有：
- `head naturals` ⇒ 1
- `head (rest naturals)` ⇒ 2
- `head (rest (rest naturals))` ⇒ 3

延迟列表 `lists` 实际上是无限长度的。它将根据实际需要进行计算。然而，如果一个值被需要多次，它每次都会重新计算。展示如何使用指针和赋值（示例 8.42）对 `delayed_list` 的值进行记忆化，以便元素只被计算一次。OCaml 版本的 11.67。或者（或额外），用 OCaml 解决练习 11.5、11.7、11.8、11.10、11.13、11.14 或 15。

## 11.19 深入探讨

## 11.20—23 探索

## 11.24 阅读 Lisp 的原始自定义定义 [MAE+65]
与 Scheme 的类似定义 [AS96, Chap. 4] 进行比较。有什么不同之处？哪些保持不变？在每个定义中，`apply` 和 `eval` 内置了什么？你对整个想法有什么看法？元解释器（metacircular interpreter）真的定义了什么吗，还是仅仅是“循环论证”？

## 11.25 阅读 John Backus 的图灵奖演讲稿 [Bac77]
他在其中主张函数式编程。他的 FP 表示法与 Lisp 和 ML 语言族相比如何？

## 11.26 学习 Haskell 中的单子（monads）
特别注意列表的定义。解释单子与列表推导式（示例 8.58）、迭代器、延续（第 6.2.2 节）和回溯搜索的关系。

## 11.27 阅读并学习事务内存（第 13.4.4 节）
查阅 STM Haskell [HMPH05]。解释单子如何促进共享线程位置更新的序列化。

## 11.28 我们已经看到 Lisp 和 ML 包含了赋值和迭代等命令式特征
这些特征重要吗？语言通过坚持纯函数式编程风格，放弃了什么（反之，又获得了什么）？以类似的思路，你对最近几种命令式语言（特别是 Python 和 C#——参见侧栏 16）中，试图通过函数结构和无限扩展来促进函数式编程的尝试怎么看？

## 11.29 研究函数式程序的编译
出现了哪些特殊问题？使用了什么技术来解决它们？搜索的起点可以参考 Appel [App97]、Wilhelm 和 Maurer [WM95] 以及 Grune 等人 [GBJ+12] 的编译器书籍。

## 11.30–11.32 深入探讨

# 第 11 章 函数式语言

## 11.12 参考文献说明

Lisp 是最早的函数式编程语言，源于 McCarthy 及其同事 20 世纪 50 年代的工作。Erlang、Haskell、Lisp、Miranda、ML、OCaml、Scheme、Single Assignment C 和 Sisar 的参考文献可以在附录 A 中找到。历史上的非正式 Lisp 方言包括 Lisp 1.5 [MAE+65]、Maclisp [Moo78]（与 Apple Macintosh 无关）和 Interlisp [TM81]。

Abelson 和 Sussman 的著作 [AS96] 长期以来被用于 MIT 及其他地方的编程入门课程，它是基础编程概念、特别是函数式编程的经典指南。额外的历史参考可以在 Hudak 的论文 [Hud89] 中找到。

Lambda 演算由 Church 在 1941 年引入。经典的参考是 Barendregt 的 [Bar84] 著作。Michaelson [Mic89] 提供了形式化的易读介绍，Steiner [Ste95] 介绍了固定点算子（见 C6）。John Backus 作为 Fortran 的原始开发者之一，他在 1977 年图灵奖演讲 [Bac78] 中有力地主张函数式编程。他的 FP 语言 [BW87, BW92]。Wilhelm 和 Maurer [WM95] 以及 Grune 等人 [GBJ+12] 讨论了函数语言的实现。虽然 Lisp 起于 60 年代，但直到最近函数语言才开始广泛使用。Wadler [Wad94, Wad98] 描述了 90 年代末的情况。许多后续项目的描述可以在 Commercial Users of Functional workshop (cufp.galois.com) 找到，该会议自 2004 年发表关于商业用途的专题文章。Armstrong [Arm07] 为 Ericsson AXD301 一个包含百万行 Erlang 代码的电话交换系统实现了惊人的“九个九”可靠性——相当于每年停机约 32 毫秒。

# 第 12 章 逻辑语言

## 12.1 逻辑编程概念

逻辑编程系统允许程序员陈述一组公理，从这些公理中可以证明定理。逻辑程序的用户陈述一个定理或目标，而语言实现会尝试寻找一组公理和推理步骤（包括变量赋值的选择），这些内容共同推导出该目标。在现有的几种逻辑语言中，Prolog 是目前最广泛使用的。

在几乎所有的逻辑语言中，公理都是以称为霍恩子句（Horn clause）的标准形式写的。一个霍恩子句包含一个头部（head）或结论 $H$，以及一个由项 $B_i$ 组成的主体：

```
$H \leftarrow B_1, B_2, \dots, B_n$
```

该语句的语义是：当 $B_i$ 全部为真时，我们可以推导出 $H$ 也是真的。在口头读取时，我们说“$H$，如果 $B_1, B_2, \dots, B_n$”。霍恩子句可以捕获大多数但并非所有的逻辑陈述。（回到 Resolution C–12.3 中的完备性问题。）

为了推导出新的陈述，逻辑编程系统通过称为消解（resolution）的过程合并陈述并消去项。例如，如果我们知道 $A$ 和 $B$ 推导出 $C$，且 $C$ 推导出 $D$，我们可以推导出 $A$ 和 $B$ 推导出 $D$：

```
$C \leftarrow A, B$
$D \leftarrow C$
$D \leftarrow A, B$
```

通常，像 $A, B, C$ 和 $D$ 这样的项可能不仅包含常量（"Rochester is rainy"），还可能包含应用于原子或变量的谓词：`rainy(Rochester)`, `rainy(Seattle)`, `rainy(X)`。

在消解过程中，自由变量可能通过匹配项中的统一（unification）获得值，这在 ML 中是类型推断（第 7.2.4 节）的基础：

```
flowery(X) ← rainy(X)
rainy(Rochester)
flowery(Rochester)
```

在下一节中，我们将详细考虑 Prolog。我们将在 C-12.3 节回到形式逻辑及其与 Prolog 的关系。

> 注意，“头部”一词在 Prolog 中用于两种不同的事物：霍恩子句的头部和列表的头部。这两者的区别通常从上下文中很清楚。

## 12.2 Prolog

正如命令式或函数式语言解释器在引用环境的上下文中评估表达式（在该环境中定义了各种函数和常量），Prolog 解释器运行在子句数据库（霍恩子句）的上下文中，每个子句由项组成，这些项可以是常量、变量或结构。常量可以是原子（atom）或数字。结构可以被看作逻辑谓词或数据结构。

Prolog 中的原子（atoms）类似于 Lisp 中的符号（symbols）。原子看起来像是一个以小写字母开头的标识符、序列“标点”字符或带引号的字符串：

```
foo          My_Const      + 'Hi, Mom'
```

数字类似于其他语言中的整数和浮点常量。变量看起来像是一个以大写字母开头的标识符：

```
Foo          My_var        X
```

由于统一的结果，变量可以在运行时被实例化（即可以取任意值）。每个变量都局限于它所在的子句。没有声明。类型检查是动态的：它仅在程序尝试在运行时将值作为操作数时发生。

结构由一个称为函数符（functor）的原子和一个参数列表组成：

```
rainy(rochester)
teaches(scott, cs254)
bin_tree(foo, bin_tree(bar, glarch))
```

Prolog 要求左括号紧跟在函数符之后，中间没有空格。参数是二元项：常量、变量或（嵌套）结构。在内部，Prolog 实现中的结构可以被视为逻辑谓词或数据结构。常量可以是原子或数字。
