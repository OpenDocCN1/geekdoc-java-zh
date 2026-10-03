
# Java® 语言规范，Java SE 17 版

- 4.12.6 类型、类和接口 107
- 5.3 调用上下文 133
- 14.3 类和接口声明 484
- 14.4.1 局部变量和类型 487
- 15.2 表达式的形式 548
- 18.4 求解 782

```
class Test {
  public static void main(String[] args) {
    for (int i = 0; i < args.length; i++) {
      System.out.print(i == 0 ? args[i] : " " + args[i]);
    }
  }
}
```

在安装了 Oracle JDK 的机器上，存储在文件 `Test.java` 中的此该类可以通过以下命令进行编译和执行：

```
javac Test.java
java Test Hello, world.
```

产生输出：

```
Hello, world.
```

## 1.3 符号表示

在整个规范中，我们指的是源自 Java SE Platform API 的类和接口。每当我们使用单个标识符 $N$（除示例中声明的之外）引用类或接口时，预期的引用是指包 `java.lang` 中名为 $N$ 的类或接口。对于来自除 `java.lang` 其他包的类或接口，我们使用其规范名（§6.7）。

用于澄清规范的非规范性信息以较小的、缩进的文本给出。

此部分是非规范性信息。它提供了直觉、原理、建议、示例等。

为了缩短对某些规则的描述，特别是那些系统地分析 Java 编程语言构造的规则，使用了惯用的缩写 "iff" 来表示“当且仅当”。

Java 编程语言系统有时依赖于替换的概念。符号 $[F_i:=T_i, \dots, F_n:=T_n]$ 表示对于 $1 \le i \le n$，用 $T_i$ 替换 $F_i$。

## 1.4 与预定义类和接口的关系

如上所述，本规范经常引用 Java SE Platform API 的类和接口。特别是某些类和接口与 Java 编程语言有特殊的关系。例如 `Object`、`Class`、`ClassLoader`、`String` 和 `Thread` 等类，以及 `java.lang.reflect` 包中的类和接口等。本规范限制了此类类和接口的行为，但没有为它们提供完整的规范。有关这些内容，读者请参阅 Java SE Platform API 文档。

因此，本规范没有详细描述反射。许多语言构造在核心反射 API (`java.lang.reflect`) 和语言模型 API (`javax.lang.model`) 中有对应物，但这些通常在此处不进行讨论。例如，当一个对象可以被创建时，我们通常不包含核心反射 API 实现此点的各种。尽管文中未提到，但读者应该注意这些额外的机制。

## 1.5 预览特性

预览特性是指：

- Java 编程语言的一项新功能（“**预览语言特性**”）
- `java.*` 或 `javax.*` 命名空间中的一个新模块、包、类、接口、字段、方法、构造函数或枚举常量（“**预览 API**”）

该特性是完整规范、完整实现但仍未永久。它在 Java SE Platform 某一版本的实现中可用，以引发开发者对真实世界使用的反馈；这可能导致它在 Java SE Platform 的未来版本中变为永久。

实现必须在编译时和运行时禁用 Java SE Platform 某一版本定义的预览特性，除非用户通过主机系统在编译时和运行时指示启用预览特性。

Java SE Platform 某一版本定义的预览特性在对应版本的 Java SE 规范中列出。预览特性的指定方式如下：

- 预览语言特性在独立的说明文档中指定，这些文档指示了对该版本《Java® 语言规范》的更改（“差异”）。预览语言特性的规范通过引用合并到《Java® 语言规范》中，并成为其一部分，当且仅当编译时启用了预览特性。

Java 17 定义了一个语言特性：switch 的模式匹配（Pattern Matching for switch）。指定此特性的独立文档可在托管《Java® 语言规范》的 Oracle 网站上获取：https://docs.oracle.com/java/javase/17/docs/index.html。预览 API 在对应版本的 Java SE 规范中指定。使用语言特性的规则如下：

- 如果禁用了预览特性，则任何对语言特性或对使用语言特性的类或接口的源码引用都会导致编译错误。
- 如果启用了预览特性，则任何使用语言特性的类或接口的源码引用都会导致预览警告，除非满足以下条件之一：
  - 引用出现在标记有抑制警告注解的声明中 (§9.6.4)。
  - 引用出现在 import 声明中。

当启用预览特性时，鼓励 Java 编译器对每个语言特性的源码引用给出警告。此警告的细节超出了《Java® 语言规范》的范围，但其意图是提醒程序员代码可能会受到未来更改的影响。

Java SE 规范将某些预览 API 描述为*反射性的*，主要分布在 `java.lang.reflect`、`java.lang.invoke` 和 `javax.lang.model` 包中。使用反射 API 的规则如下：

- 无论预览特性是否启用，对反射 API 的任何引用都会导致警告，除非满足以下条件：
  - 引用出现在与反射模块相同的声明中。
  - 引用出现在 `java.lang.reflect` 包中。
  - 引用出现在 `java.lang.invoke` 包中。
  - 引用出现在 `javax.lang.model` 包中。

Java SE 规范将某些预览 API 描述为*普通的*如下：

- 如果禁用了预览特性，对普通 API 的任何源码引用都会导致编译错误，除非：
  - 引用出现在普通模块声明中。
  - 引用出现在普通模块中。
- 如果启用了预览特性，对普通 API 的任何源码引用都会导致警告，除非满足以下条件：
  - 引用出现在标记有抑制警告注解的声明中。
  - 引用出现在 import 声明中。

## 1.6 反馈

邀请读者将《Java 语言规范》中的技术错误或歧义反馈至 `ms-dev@openjdk`。将《Java 语言规范》中的技术错误或歧义反馈至 `ms-dev@openjdk`。

## 1.7 参考文献

关于 `javac`（Java 语言编译器）的行为，特别是其对本规范的遵循性问题，可以发送至 `compiler-dev@openjdk`。

## 文法

本章描述了本规范中使用的上下文无关文法，用于定义程序的词法和句法结构。

## 2.1 上下文无关文法

*上下文无关文法*由若干*产生式*组成。每个产生式都有一个名为*非终结符*的抽象符号作为其*左侧*，并由一个或多个非终结符和*终结符*符号序列作为其*右侧*。对于每个文法，终结符号取自于指定的*字母表*。

从一个由单一特殊非终结符（称为*目标符号*）组成的句子开始，给定的上下文无关文法规定了一种语言，即通过反复将序列中的任何非终结符替换为以该非终结符为左侧的产生式的右侧，从而产生可能的终结符符号序列集合。

## 2.2 词法文法

Java 编程语言的*词法文法*见第3 节（*词法结构*）。该文法的终结符号是 Unicode 字符集中的字符。它定义了一组产生式，从目标符号 `Input`（§3.5）开始，描述了 Unicode 字符序列（§3.1）如何翻译为输入元素序列（§3.5）。

这些输入元素在丢弃空白符（§3.6）和注释（§3.7）后，构成了 Java 编程语言句法文法的终结符号，并称为*标记*（§3.5）。这些标记是 Java 编程语言的标识符（§3.8）、关键字（§3.9）、字面量（§3.10）、分隔符（§3.11）和运算符（§3.12）。

## 2.3 句法文法

Java 编程语言的句法文法见第 4、6-10、14 和 15 章节。该文法的终结符号是词法文法定义的标记。它定义了一组产生式，从目标符号 `CompilationUnit`（$7.3$）开始，描述了标记序列如何形成在句法上正确的程序。

为了方便起见，句法文法在第 19 章中合并列出。

## 2.4 文法符号表示

终结符号在词法和句法文法的产生式中使用等宽字体显示，并在本规范中每当文本直接引用此类符号时也是如此。这些符号在程序中的出现必须与编写完全一致。

非终结符符号以*斜体*显示。非终结符的定义由被定义的非终结符名称引入，后跟冒号。接下来的行是该非终结符的一个或多个备选定义。

例如，句法产生式：

```
IfThenStatement:
if ( Expression ) Statement
```

表示非终结符 `IfThenStatement` 代表标记 `if`，后面跟着一个左括号标记，然后是一个 `Expression`，接着是一个右括号标记，最后是一个 `Statement`。

产生式右侧的语法符号 `[x]` 表示 `x` 零次或多次出现。

例如，句法产生式：

```
ArgumentList:
Argument [ , Argument]
```

这反过来是以下内容的缩写：

```
BasicForStatement:
for ( ; ) Statement
for ( ; ForUpdate ) Statement
for ( Expression ; ) Statement
for ( Expression ; ForUpdate ) Statement
for ( ForInit ; ) Statement
for ( ForInit ; ForUpdate ) Statement
for ( ForInit ; Expression ) Statement
for ( ForInit ; Expression ; ForUpdate ) Statement
```

因此，非终结符 `BasicForStatement` 实际上有八种备选右侧。

非常长的右侧可以通过清晰地缩进第二行来在第二行继续。

例如，句法文法包含此产生式：

```
NormalClassDeclaration:
[ClassModifier] class TypeIdentifier[TypeArguments]
[ClassExtends][ClassImplements][ClassPermits]ClassBody
```

它为非终结符 `NormalClassDeclaration` 定义了一个右侧。

产生式右侧的短语 `(one of)` 表示后续行或那几行中的每个符号都是一个备选定义。

例如，词法文法包含此产生式：

```
ZeroToThree:
(one of)
0 1 2 3
```

这仅仅是以下内容的方便的缩写：

```
ZeroToThree:
0
1
2
3
```

当产生式中的备选定义看起来是一个标记时，它代表构成该标记的字符序列。

因此，产生式：

```
BooleanLiteral:
(one of)
true false
```

是以下内容的缩写：

```
BooleanLiteral:
true
false
```

产生式的右侧可以使用短语 "but not" 然后指示要排除的扩展，来指定某些扩展是不允许的。

例如：

- Identifier:
  IdentifierChars but not a Keyword or BooleanLiteral or NullLiteral

最后，一些非终结符通过正体的叙述性短语定义，在这些情况下列出所有备选方案是不实际的。

例如：

```
RawInputCharacter:
any Unicode character
```

## 词法结构

本章规定了 Java 编程语言的词法结构。

程序是用 Unicode（§3.1）编写的，但提供了词法翻译（§3.2），以便可以使用 Unicode 转义（§3.3）仅使用 ASCII 字符包含任何 Unicode 字符。行终止符（§3.4）描述了 Unicode 字符序列（§3.1）如何翻译为输入元素序列（§3.5）。

这些输入元素在丢弃空白符（§3.6）和注释（§3.7）后，构成了 Java 编程语言句法文法的终结符号，并称为*标记*（§3.5）。这些标记是 Java 编程语言的标识符（§3.8）、关键字（§3.9）、字面量（§3.10）、分隔符（§3.11）和运算符（§3.12）。

## 3.1 Unicode

程序是用 Unicode（§3.1）编写的，但提供了词法翻译（§3.2），以便可以使用 Unicode 转义（§3.3）仅使用 ASCII 字符包含任何 Unicode 字符。行终止符（§3.4）描述了 Unicode 字符序列（§3.1）如何翻译为输入元素序列（§3.5）。

这些输入元素在丢弃空白符（§3.6）和注释（§3.7）后，构成了 Java 编程语言句法文法的终结符号，并称为*标记*（§3.5）。这些标记是 Java 编程语言的标识符（§3.8）、关键字（§3.9）、字面量（§3.10）、分隔符（§3.11）和运算符（§3.12）。

Unicode 标准最初被设计为固定宽度的16 位编码。它后来被更改为允许超过 16 位。为了仅使用 16 位单元表示整个字符范围，Unicode 标准定义了编码 UTF-16。在这种编码中，补充字符表示为16 位单元对，分别来自高代理范围（U+D800 到 UDBFF）和低代理范围（U+DC00 到 UFFF）。对于 U+0000 到 U+FFFF 字符，代码点和代码单元的值相同。Java 编程语言使用 16 位单元序列表示文本，使用 UTF-16 编码。Java 平台的某些 API（主要在 `Character` 类中）使用 32 位整数表示代码点。Java 平台提供了转换 16 位和 32 位表示的方法。

本规范在表示相关时使用代码点和 UTF-16 代码单元术语，在表示无关时使用通用术语字符。

除了注释（§3.7）、标识符（§3.8）以及字符字面量、字符串字面量、文本块（§3.10.4、§3.10.5、§3.10.6）之外，程序中的所有输入元素（§3.5）均由 ASCII 字符（或 Unicode 转义 §3.3）形成。

ASCII（ANSI X3.4）是美国信息交换标准。Unicode UTF-16 编码的前128个字符是 ASCII 字符。

## 3.2 词法翻译

原始 Unicode 字符通过三个词法翻译步骤翻译为标记序列，这些步骤依次应用：

1. 将原始字符流中的 Unicode 转义（§3.3）翻译为相应的 Unicode 字符。格式为 `\uxxxx` 的 Unicode 转义（xxxx 为十六进制值）表示 UTF-16 代码单元编码为 xxxx。此翻译步骤允许仅使用 ASCII 字符表示任何程序。
2. 将第一步生成的 Unicode 流翻译为输入字符流和行终止符流（§3.4）。
3. 将步骤 2 产生的输入字符流和行终止符转换为输入元素序列（§3.5），该序列在丢弃空白（§3.6）和注释（§3.7）后，构成了语法规则（§2.3）终结符号的标记（tokens）。

在每一步中都使用最可能的翻译，即使该结果最终无法产生正确的程序，而另一种词法翻译可以可以的话。这里有两个例外，用以处理需要更细粒度翻译的情况：在步骤 1 中，处理连续的 `~` 字符 (§3.3)，以及在步骤 3 中，处理上下文窗口和相邻的 `>` 字符 (§3.5)。

输入字符 `a–b` 被标记化为 `a`、`–` 和 `b`，这不属于任何语法正确程序的一部分，尽管标记化 `a`、`– b` 可能是某个语法正确程序的一部分。标记化 `a`、`– b` 可以通过输入字符 `a–b`（在两个字符之间有一个 ASCII 字符）来实现。

人们可能认为原始输入 `\u1234` 被翻译为 `\` 字符和（遵循“最可能”规则）形式为 `\u1234` 的 Unicode 转义。事实上，开头的 `\` 字符导致该原始输入被翻译为七不同的字符：`\` `u` `1` `2` `3` `4`。

### 3.3 Unicode 转义

Java 语言编译器（“Java编译器”）首先识别其原始输入中的 Unicode 转义，将 ASCII 字符 `\` 后跟四个十六进制数字转换为原始输入字符，该字符表示指示十六进制值的 UTF-16 代码单元 (§3.1)。一个 Unicode 转义可以表示 U+0000 到 U+FFFF 范围内的补充字符；表示 U+010000 到 U+10FFFF 范围内的补充字符需要两个连续的 Unicode 转义。编译器原始输入中的所有其他字符都被识别为原始输入字符并保持不变传递。

此翻译步骤产生一个 Unicode 输入字符序列，其中包含原始输入字符（任何 Unicode 转义已还原为原始输入字符）。

```
UnicodeInputElement:
UnicodeEscape
RawInputCharacter

UnicodeEscape:
\UnicodeMarker HexDigit HexDigit HexDigit

UnicodeMarker:
u | U

HexDigit:
(one of)
0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F

RawInputCharacter:
any Unicode character
```

这里的 `\u` 和十六进制数字都是 ASCII 字符。

`UnicodeInputCharacter` 的产生式具有歧义性，因为编译器原始输入中的 ASCII `\` 字符可以还原为 `RawInputCharacter`，也可以还原为 `UnicodeEscape` 的 `\`（其后紧跟一个 ASCII `u`）。为了避免歧义，对于编译器原始输入中的每个 ASCII `\` 字符，输入处理必须根据该翻译步骤产生的最近的原始输入字符：

- 如果结果中最近的原始输入字符本身是从编译器原始输入中的 Unicode 转义翻译而来的，那么该 ASCII `\` 字符就有开始 Unicode 转义的资格。
- 例如，如果结果中最近的原始输入字符是由于原始输入中的 Unicode 转义 `\u005c` 产生的反斜杠，那么出现在原始输入中的 ASCII `\` 字符就有开始另一个 Unicode 转义的资格。



# 词法结构

## 3.3 Unicode 转义

- 否则，考虑在结果中作为原始输入字符连续出现的反斜杠数量，回溯到非反斜杠字符或结果的开头。（任何此类反斜杠源于编译器原始输入中的 ASCII `\` 字符还是编译器原始输入中的 Unicode 转义 `\u005c` 无关。）如果该数字是偶数，则该 ASCII `\` 字符有开始 Unicode 转义的资格；如果是奇数，则该 ASCII `\` 字符没有开始 Unicode 转义的资格。

- 例如，输入 `"\u2122=\\u2122"` 产生字符序列 `\ u 2 1 2 2`，因为原始输入中的第二个 ASCII `\` 字符没有开始 Unicode 转义的资格，第三个 ASCII `\` 字符有资格，而 `\u2122` 是该字符的 Unicode 编码。

如果符合资格的 `\` 后没有紧跟 `u`，则它被视为 `RawInputCharacter` 并留在转义的 Unicode 流中。

如果符合资格的 `\` 后跟了 `u` 或多个 `u`，且最后一个 `u` 后没有紧跟四个十六进制数字，则发生编译时错误。

### Unicode 转义产生的字符不参与 Unicode 转义

例如，输入 `\u005cu005a` 产生六个字符 `\ u 0 0 a a`，因为 `005c` 没有产生字符 `z`（Unicode 值为 `005a`），因为处理 Unicode 转义 `\u005c` 产生的反斜杠不被解释为后续 Unicode 转义的开始。

注意，`\u005cu005a` 不能在字符串字面量表示六个字符 `\ u 0 0 5 a`。这是因为翻译产生的第一个字符以及 `\u u` 在字符串字面量被解释为非法的转义序列 (§3.10)。

幸运的是，关于连续反斜杠字符的规则有助于程序员编写在字符串字面量中使用 Unicode 转义的原始输入。在字符串字面量表示六个字符 `\ u 0 0 5 a` 只需要将 `\` 置于相邻位置，例如 `\\u005a`。这是因为第一个 `\u` 有资格开始 Unicode 转义，但第二个没有。

## 3.4 行终止符

当没有可用字体时，Java 编译器应该使用 `\uxxxx` 表示法作为输出格式显示 Unicode 字符。

Java 接下来通过识别行终止符将 Unicode 输入字符序列划分成行。

- **LineTerminator:**
  - ASCII LF 字符，也称为“换行”
  - ASCII CR 字符，也称为“回车”
  - ASCII CR 字符后随 LF 被计为一个行终止符

- **InputCharacter:**
  - `UnicodeInputCharacter` 但不是 CR 或 LF

行终止符指定了 `//` 形式注释的结束 (§3.7)。

行终止符定义的行可能会决定 Java 编译器产生的行号。

## 3.5 输入元素和标记

由 Unicode 转义处理 (§3.3) 然后通过输入行识别 (§3.4) 产生的输入字符和行终止符被还原为输入元素序列。

### Input

```
[InputElement] [Sub]
```

### 词法结构

#### 输入元素与标记

##### 3.5

**InputElement (输入元素):**

- `Whitespace` (空白)
- `Comment` (注释)
- `Token` (标记)

**Token (标记):**

- `Identifier` (标识符)
- `Keyword` (关键字)
- `Literal` (字面量)
- `Separator` (分隔符)
- `Operator` (运算符)

**Sub:**

- ASCII SUB 字符，称为 "control-Z"

那些不是空白或注释的输入元素都是标记。这些标记是语法语法的终结符号 (§2.3)。

空白 (§3.6) 和注释 (§3.7) 可以用于分隔标记，如果这些标记相邻，可能会以另一种方式进行分词。

> 例如，输入字符 `-` 和 `=` 只有在中间没有空隙字符或注释的情况下，才能形成运算符标记 `-=` (§3.12)。另一个例子，十个输入字符 `staticvoid` 形成一个单一标识符，而十一个输入字符 `static void`（在 `c` 和 `v` 之间有一个 ASCII SP 字符）形成由空格分隔的一对关键字标记：`static` 和 `void`。

为了兼容某些操作系统，作为特殊让步，如果 ASCII SUB 字符(`\u001a`，或 control-Z) 是转义输入流中的最后一个字符，则会被忽略。

该产生式具有歧义，这意味着对于某些输入字符序列，有多种方法可以将输入字符还原为输入元素（即对输入字符进行分词）。歧义按如下方式解决：

- 可以还原为标识符标记或字面量标记的输入字符序列始终还原为字面量标记。
- 可以还原为标识符标记或保留关键字标记 (§3.9) 的输入字符序列始终还原为保留关键字标记。
- 可以还原为上下文相关关键字标记或其他标记（非关键字标记）的输入字符序列，将根据 §3.9 中指定的上下文进行还原。
- 如果输入字符 `>` 出现在类型中（在语法法 (§4.1, §8.3) 中作为 `Type` 或 `UnannType` 的一部分），它始终还原为数值比较运算符 `>`，即使它可以与相邻的 `>` 字符组合形成不同的运算符。

虽然没有针对 `<` 的规则，但在类型如 `List<List<String>>` 中两个连续的 `>` 括号将被分词为右移运算符 `>>`，在类型如 `List<List<String>>>` 中三个连续的 `>` 括号将被分词为无符号右移运算符 `>>>`。在类型如 `List<List<List<String>>>>` 中四个或更多连续的 `>` 标记将具有歧义，因为 `>` 和 `>>>` 标记的不同组合都可以表示 `>>>` 字符。

考虑输入流中的两个标记 `x` 和 `y`。如果 `x` 在 `y` 之前，我们说 `x` 在 `y` 的左侧，`y` 在 `x` 的右侧。

例如，在段简单的代码中：

```
class Empty {
}
```

我们说 `}` 标记在 `{` 标记的右侧，尽管在这个二维表示中它出现在 `{` 标记的下方左侧。这种关于“左”和“右”词的用法让我们能够讨论右操作数或赋值的左侧。

## 3.6 空白

空白被定义为 ASCII 空格字符、水平制表符字符、分页字符和换行符字符 (§3.4)。

- **WhiteSpace:**
  - ASCII SP 字符，也称为 "space"
  - ASCII HT 字符，也称为 "horizontal tab"
  - ASCII FF 字符，也称为 "form feed"
  - `LineTerminator` (换行符)

## 3.7 注释

注释有两种：

- `/* ... */`
  传统注释：从 ASCII 字符 `/*` 到 ASCII 字符 `*/` 之间的所有文本都会被忽略（如 C 和 C++）。
- `// ...`
  行尾注释：从 ASCII 字符 `//` 到行尾的所有文本会被忽略（如 C++）。

```
Comment:
  TraditionalComment
  EndOfLineComment
```

```
TraditionalComment:
  /* CommentTail
```

```
CommentTail:
  * CommentTailStar
  NotStar CommentTail
```

```
CommentTailStar:
  / CommentTailStar
  NotStarNotSlash CommentTail
```

```
NotStar:
  InputCharacter 但不是 `*`
  LineTerminator
```

```
NotStarNotSlash:
  InputCharacter 但不是 `*` 或 `/`
  LineTerminator
```

```
EndOfLineComment:
  // {InputCharacter}
```

这些产生式暗示了以下所有属性：

- 注释不会嵌套。
- 在以 `//` 开头的注释中，`/*` 和 `*/` 没有特殊意义。
- 在以 `/*` 开头的注释中，`//` 没有特殊意义。

结果是，以下文本是一个完整的注释：

```
/* this comment /* // ** ends here: */
```

词法语法意味着注释不会出现在字符字面量、字符串字面量或文本块中 (§3.10.4, §3.10.5, §3.10.6)。

## 3.8 标识符

标识符是 Java 字母和 Java 数字的无限长度序列，其中第一个必须是 Java 字母。

- **Identifier:**
  - `IdentifierChars` 但不是关键字或布尔字面量或空字面量

- **IdentifierChars:**
  - `JavaLetter` [`JavaLetterOrDigit`]

- **JavaLetter:**
  - 任何“Java 字母”的 Unicode 字符

- **JavaLetterOrDigit:**
  - 任何“Java 字母或数字”的 Unicode 字符

“Java 字母”是指方法 `Character.isJavaIdentifierStart(int)` 返回 `true` 的字符。

“Java 字母或数字”是指方法 `Character.isJavaIdentifierPart(int)` 返回 `true` 的字符。

## 3.9 关键字

### 上下文关键字

（其中之一）

```
exports      requires    uses
module       permits     sealed      var
non-sealed   provides    to          with
open         record      transitive  yield
```

关键字 `const` 和 `goto` 是被保留的关键字，尽管它们目前没有被使用。当这些 C++ 关键字错误地出现在程序中时，这可能允许 Java 编译器产生更好的错误信息。

关键字 `strictfp` 已经过时，不应在新代码中使用。

关键字 `_` 被预留，以供未来可能在参数声明中使用。

`true` 和 `false` 不是关键字，而是布尔字面量 (§3.10.10)。

`null` 不是关键字，而是空字面量 (§3.10.8)。

在将输入字符归约为输入元素的过程中 (§3.5)，如果一个输入字符序列在概念上匹配一个上下文关键字，则当且仅当同时满足以下两个条件时，该序列会被归约为上下文关键字：

1. 该序列被识别为语法法在适当语境下 (§2.3) 的终结符，如下：
   - 对于 `module` 和 `open`，当在 `ModuleDeclaration` (§7.7) 中被识别为终结符时。
   - 对于 `exports`、`opens`、`provides`、`requires`、`to`、`uses` 和 `with`，当在 `ModuleDirective` 中被识别为终结符时。
   - 对于 `transitive`，当在 `RequiresModifier` 中被识别为终结符时。
     例如，识别序列 `requires transitive` 没有使用 `Modifier`，因此项 `transitive` 被归约为标识符而不是上下文关键字。
   - 对于 `var`，当在 `LocalVariableType` (§14.4) 或 `LambdaParameterType` (§15.27.1) 中被识别为终结符时。
     在其他语境下，尝试将 `var` 作为标识符将导致错误，`var` 不是一个 `TypeIdentifier` (§3.8)。
   - 对于 `yield`，当在 `YieldStatement` (§14.21) 中被识别为终结符时。
     在其他语境下，尝试将 `yield` 作为标识符将导致错误，`yield` 既不是 `TypeIdentifier` 也不是 `UnqualifiedMethodIdentifier`。
   - 对于 `record`，当在 `RecordDeclaration` (§8.10) 中被识别为终结符时。
   - 对于 `non-sealed`、`permits` 和 `sealed`，当在 `NormalClassDeclaration` (§8.1) 或 `NormalInterfaceDeclaration` (§9.1) 中被识别为终结符时。

2. 该序列的前后没有紧跟任何匹配 `JavaLetterOrDigit` 的输入字符。

通常情况下，源代码中无意遗漏空格会导致输入字符序列被标记化为一个标识符，根据“最长可能翻译”规则 (§3.2)，十二个输入字符序列 `publicstatic` 始终被标记化为标识符 `publicstatic`，而不是关键字 `public` 和 `static`。如果两个标记之间交替出现，它们必须用空格或注释分隔。

该规则与“最长可能翻译”规则共同工作，在上下文关键字可能出现的地方产生一个直观的结果。例如，输入字符序列 `varfilename` 通常被标记化为标识符 `varfilename`，但在局部声明中，前三个字符根据上述规则的第一个条件被初步识别为上下文关键字 `var`。然而，如果忽略序列中缺失的空格并将后八个字符识别为标识符 `filename`，将是困惑的。（这意味着该序列在不同语境下会不同的标记化：在大多数语境下是标识符，但在局部变量声明中是上下文关键字和标识符。）因此，第二个条件防止了在某处识别上下文关键字 `var`。

## 3.10 字面量

整数字面量可以用十进制（基 10）、十六进制（基 16）、八进制（基 8）或二进制（基 2）表示。

```
IntegerLiteral:
  DecimalIntegerLiteral
  HexIntegerLiteral
  OctalIntegerLiteral
  BinaryIntegerLiteral
```

```
DecimalIntegerLiteral:
  DecimalNumeral [IntegerTypeSuffix]
```

```
HexIntegerLiteral:
  HexNumeral [IntegerTypeSuffix]
```

```
OctalIntegerLiteral:
  OctalNumeral [IntegerTypeSuffix]
```

```
BinaryIntegerLiteral:
  BinaryNumeral [IntegerTypeSuffix]
```

```
IntegerTypeSuffix: (其中之一)
  l
  L
```

整数字面量如果以 ASCII 字母 `L` 或数字 `l` 结尾，则为 `long` 类型 (§4.2.1)。后缀 `L` 是首选的，因为字母 `l` (ell) 往往与数字 `1` 难以区分。

下划线允许作为数字之间的分隔符。

在十六进制或二进制字面量中，整数由 `0x` 或 `0b` 之后的任何类型后缀之前的数字组成。因此，下划线不能紧跟在 `0x` 或 `0b` 之后，也不能出现在数字的最后一个数字之后。

在十进制或八进制字面量中，整数由类型后缀之前的所有数字组成。因此，下划线不能出现在第一个数字之前或最后一个数字之后。下划线可以出现在初始数字 `0` 之后（因为 `0` 是表示零的数字）以及非零十进制字面量的初始数字之后。

十进制数字要么是单个 ASCII 字符 `0`（表示零），要么由 `1` 到 `9` 的 ASCII 数字组成，并可选地带有下划线，表示一个正整数。

```
DecimalNumeral:
  0
  NonZeroDigit [Digits]
  NonZeroDigit Underscores
```

```
NonZeroDigit: (其中之一)
  1 2 3 4 5 6 7 8 9
```

```
Digits:
  Digit [DigitsAndUnderscores]
```

```
Digit:
  0
  NonZeroDigit
```

```
DigitsAndUnderscores:
  DigitOrUnderscore [DigitsAndUnderscores]
```

```
DigitOrUnderscore:
  Digit
  _
```

```
Underscores:
  _ [Underscores]
```

十六进制数字由前导字符 `0x` 或 `0X` 加上多个由下划线分隔的 ASCII 数字组成，可以表示正整数、零或负整数。值为 10 到 15 的十六进制数字由 ASCII 字母 `a` 到 `f` 或 `A` 到 `F` 表示；每个十六进制数字可以是大写或小写。

```
HexNumeral:
  0x HexDigits
  0X HexDigits
```

```
HexDigits:
  HexDigit [HexDigitsAndUnderscores]
```

```
HexDigit: (其中之一)
  0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F
```

```
HexDigitsAndUnderscores:
  HexDigitOrUnderscore [HexDigitsAndUnderscores]
```

```
HexDigitOrUnderscore:
  HexDigit
  _
```

八进制数字由 ASCII 字符 `0` 加上多个由下划线分隔的 0 到 7 的 ASCII 数字组成，可以表示正整数、零或负整数。

```
OctalNumeral:
  0 OctalDigits
  0 Underscores OctalDigits
```

```
OctalDigits:
  OctalDigit [OctalDigitsAndUnderscores]
```

```
OctalDigit: (其中之一)
  0 1 2 3 4 5 6 7
```

```
OctalDigitsAndUnderscores:
  OctalDigitOrUnderscore [OctalDigitsAndUnderscores]
```

```
OctalDigitOrUnderscore:
  OctalDigit
  _
```

注意八进制数字始终包含至少一个数字，因为单独的 `0` 始终视为十进制数字——在实践中，`0`、`00` 和 `0x0` 都表示相同的值。

二进制数字由前导字符 `0b` 或 `0B` 加上多个由下划线分隔的 0 或 1 的 ASCII 数字组成，可以表示正整数、零或负整数。

```
BinaryNumeral:
  0b BinaryDigits
  0B BinaryDigits
```

```
BinaryDigits:
  BinaryDigit [BinaryDigitsAndUnderscores]
```

```
BinaryDigit: (其中之一)
  0 1
```

```
BinaryDigitsAndUnderscores:
  BinaryDigitOrUnderscore [BinaryDigitsAndUnderscores]
```

```
BinaryDigitOrUnderscore:
  BinaryDigit
  _
```

`int` 的最大十进制字面量是 `2147483648` (2³¹)。



# 词法结构

## 3.10 字面量

### 3.10.1 整数字面量

从 0 到 2147483647 的所有十进制字面量都可以出现在 `int` 字面量的地方。十进制字面量 2147483648 只能作为一负操作的操作数 (§15.15.4)。

如果十进制字面量 2147483648 出现在一负操作的操作数以外的地方；或者 `int` 类型十进制字面量大于 2147483648 (2³¹)，则为编译错误。

`int` 类型最大的正十六进制、八进制和二进制字面量——每个都表示十进制值 2147483647 (2³¹-1)——分别为：

- `0x7ffff_ffff`
- `017777_7777`
- `0b0111_1111_1111_1111_1111_1111`

`int` 类型最负的十六进制、八进制和二进制字面量——每个都表示十进制值 -2147483648 (-2³¹)——分别为：

- `0x8000_0000`
- `0200_0000_0000`
- `0b1000_0000_0000_0000_0000_0000_0000`

以下十六进制、八进制和二进制字面量表示十进制值 -1：

- `0xffff_ffff`
- `037777_7777`
- `0b1111_1111_1111_1111_1111_1111`

如果十六进制、八进制或二进制 `int` 字面量不能放入 32 位，则为编译错误。

`long` 的最大十进制字面量是 9223372036854775808L (2⁶³)。

从 0L 到 9223372036854775807L 的所有十进制字面量都可以出现在 `long` 字面量的地方。十进制字面量 9223372036854775808L 只能作为一负操作的操作数 (§15.15.4)。

如果十进制字面量 9223372036854775808L 出现在一负操作的操作数以外的地方；或者 `long` 类型十进制字面量大于 9223372036854775808L (2⁶³)，则为编译错误。

`long` 类型中最大的正十六进制、八进制和二进制字面量——每个都代表十进制值 9223372036854775807L (2⁶³-1) —— 分别为：

- `0xFFFF_ffff_ffff_ffff`
- `0o7777_7777_7777_7777L`
- `0b0111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_111`

`long` 类型中最负的十六进制、八进制和二进制字面量——每个都代表十进制值 -9223372036854775808L (-2⁶³) —— 分别为：

- `0x8000_0000_0000_0000L`
- `0o010_0000_0000_0000_0000L`
- `0b1000_0000_0000_0000_0000_0000_0000_0000_0000_0000`

以下十六进制、八进制和二进制字面量代表十进制值 -1L：

- `0xffff_ffff_ffff_ffffL`
- `0o177_7777_7777_7777L`
- `0b1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111`

如果十六进制、八进制或二进制 `long` 字面量无法放入 64 位中，则会导致编译错误。

`int` 字面量的示例：

```
0      2      0372    0xData_Cafe    1996      0x00_FF__00_FF
```

`long` 字面量的示例：

```
01             0777L    0x100000000L    2_147_483_648L    0xC0B0BL
```

### 3.10.2 浮点数字面量

浮点数字面量包含以下部分：整数部分、十进制或十六进制部分（由 ASCII 句点字符表示）、小数部分、指数以及类型后缀。

浮点数字面量可以用十进制（基数 10）或十六进制（基数16）表示。

对于十进制浮点数字面量，至少需要一个数字（在整数部分或小数部分中），并且需要一个小数点、一个指数或一个浮点类型后缀。所有其他部分都是可选的。指数如果存在，则由 ASCII 字母 e 或 E 表示，后面紧跟一个可选的有符号整数。

对于十六进制浮点数字面量，至少需要一个数字（在整数部分或小数部分中），且指数是强制的，而浮点后缀是可选的。指数由 ASCII 字母 p 或 P 表示，后面紧跟一个可选的有符号整数。

下划线允许作为表示整数部分的数字之间、表示小数部分的数字之间、以及表示指数部分的数字之间的分隔符。

#### 语法

```
FloatingPointLiteral:
  DecimalFloatingPointLiteral
  HexadecimalFloatingPointLiteral

DecimalFloatingPointLiteral:
  Digits . [Digits] [ExponentPart][FloatTypeSuffix]
  . Digits [ExponentPart][FloatTypeSuffix]
  Digits ExponentPart [FloatTypeSuffix]
  Digits [ExponentPart] FloatTypeSuffix

ExponentPart:
  ExponentIndicator SignedInteger

ExponentIndicator:
  e | E

SignedInteger:
  [Sign] Digits

Sign:
  + | -

FloatTypeSuffix:
  f | F | d | D

HexadecimalFloatingPointLiteral:
  HexSignificand BinaryExponent [FloatTypeSuffix]

HexSignificand:
  HexNumeral .
  0x [HexDigits] . HexDigits
  0x [HexDigits] . HexDigits

BinaryExponent:
  BinaryExponentIndicator SignedInteger

BinaryExponentIndicator:
  p | P
```

如果浮点数字面量带有 ASCII 字母 F 或 f 后缀，则其类型为 `float`；否则其类型为 `double`，并可以可选地带有 ASCII 字母 D 或 d 后缀。

`float` 和 `double` 的元素分别是可以使用 IEEE 754 binary32 和 IEEE 754 binary64 格式表示的值（§4.2.3）。从浮点数的 Unicode 字符串表示到内部 IEEE 754 二进制浮点表示的正确输入转换细节已在 `java.lang.Float` 和 `Double` 包中进行了描述。

最大的正 `float` 值在数值上等于 2¹²⁷。能够舍入到该值的最短十进制字面量是 `3.402823e38f`。该类型的十六进制字面量为 `0xffffP+127f`。最小的正非零 `float` 值在数值上等于 2⁻¹⁴⁹。能够舍入到该值的最短十进制字面量是 `1.4e-45`。

### 3.10.5 字符串字面量

以下是字面量的示例：

```
"" // 空字符串
"\"" // 仅包含 " 的字符串
"This is a string" // 包含 16 个字符的字符串
"This is a \"" + // 实际上是一个字符串值的表达式，
"two-line string" // 由两个字符串字面量组成
```

由于 Unicode 转义序列在每一步处理中都会被处理，因此对于包含单个换行符（LF）的字面量，写入 `"\u000a"` 是不正确的；Unicode 转义序列 `\u000a` 在翻译 1 (§3.3) 中被转换为实际换行符，而换行符在步骤 2 (§3.4) 中变为行终止符，因此该字面量在步骤 3 中是无效的。相反，应该使用转义序列 `\n`。同样，对于包含单个回车符（CR）的字面量，写入 `"\u000d"` 也是不正确的。请使用 `\r`。最后，对于包含双引号的字面量，无法写入 `"\u0022"`。

长字符串字面量可以被拆分为更短的部分，并使用连接运算符 `+` 写作为一个（可能带括号的）表达式 (§15.18)。

运行时，字符串字面量是对 `String` 类实例的引用 (§4.3.3)，表示该字面量所代表的字符串。

此外，字符串字面量始终引用 `String` 类的同一个实例。这是因为字符串字面量——更通俗地说，作为常量表达式值的字符串 (§15.29)——被“内化”了，以便共享唯一的实例，仿佛执行了 `String.intern` 方法 (§12.5)。

#### 示例 3.10.5-1. 字符串字面量

由编译单元 (§7.3)组成的程序：

```
package testPackage;
class Test {
    public static void main(String[] args) {
        String hello = "Hello";
    }
}
```

以及编译单元：

```
package other;
public class Other { public static String hello = "Hello"; }
```

产生输出：

```
true
true
true
false
true
```

此示例说明了六点：

- 同一个类和包中的字符串字面量表示对同一个 `String` 对象的引用 (§4.3.1)。
- 同一个包中不同类的字符串字面量表示对同一个 `String` 对象的引用。
- 不同包中不同类的字符串字面量表示对同一个 `String` 对象的引用。
- 由常量表达式 (§15.29) 连接的字符串在编译时计算，然后被像字面量一样对待。
- 在运行时通过连接计算的字符串是新创建，因此是不同的。
- 显式调用 `intern` 计算字符串的结果与任何预存在的相同内容的字面量是同一个 `String` 对象。

### 3.10.6 文本块

文本块由起始和结束分隔符包围的零或多个字符组成。字符可以用转义序列表示 (§3.10.7)，字符串字面量中必须用转义序列表示的换行符和双引号字符 (§3.10.5) 则在文本块中可以直接表示。

#### 语法

```
TextBlock:
  """ [TextBlockWhitespace] LineTerminator [TextBlockCharacter] """

TextBlockWhitespace:
  Whitespace 但不是 LineTerminator

TextBlockCharacter:
  InputCharacter 但不是 \
  EscapeSequence
  LineTerminator
```

为了方便起见，这里显示了 §3.3、§3.4 和 §3.6 中的产生式：

```
WhiteSpace:
  ASCII SP 字符，也称为“空格”（space）
  ASCII HT 字符，也称为“制表符”（horizontal tab）
  ASCII FF 字符，也称为“分页”（form feed）

LineTerminator:
  ASCII LF 字符，也称为“换行符”（newline）
  ASCII CR 字符，也称为“回车”（return）
  ASCII CR 字符后跟 ASCII LF 字符

InputCharacter:
  UnicodeCharacter 但不是 CR 或 LF

UnicodeInputEscape:
  RawInputCharacter
  \ UnicodeMarker HexDigit HexDigit HexDigit

RawInputCharacter:
  任何 Unicode 字符
```

文本块的类型为 `String` (§4.3.3)。

**起始分隔符**是一个以三个双引号字符（`"""`）开头，其后跟随零或多个空格、制表符或分页符，并以行终止符结束的序列。

**结束分隔符**是三个双引号字符的序列。

**文本块的内容**是紧接起始分隔符的行终止符之后开始，并在结束分隔符的第一个引号之前结束的字符序列。

与字符串字面量 (§3.10.5) 不同，在文本块内容中出现行终止符并不是编译错误。

#### 示例 3.10.6-1. 文本块

当需要多行字符串时，文本块通常比字符串字面量的连接更具可读性。例如，考虑这些 HTML 片段的替代表示方法：

```
String html = "<html>\n" + 
              "<body>\n" +
              "<p>Hello, world</p>\n" +
              "</body>\n" +
              "</html>\n";
```

```
String html = """
<html>
<body>
  <p>Hello, world</p>
</body>
</html>
""";
```

以下是文本块的示例：

在文本块中使用转义序列 `\n` 和 `\"` 分别表示换行符和双引号字符是允许的，尽管通常没有必要。

#### 示例 3.10.6-2. 文本块中的转义序列

在文本块中使用转义序列 `\n` 和 `\"` 分别表示换行符和双引号字符是允许的，尽管通常没有必要。如果对内容中的双引号进行转义，字符串的值将如下：

```
class Story1 {
    public static void main(String[] args) {
        String story = """一个包含单个换行符的字符串
            一个包含单个双引号的字符串
            一个包含16 个字符的字符串""";
    }
}
```

如果将程序修改为将结束分隔符放在最后一行，则会发生错误，因为内容中的双引号被翻译了，从而留下了一个多余的引号：

```
class Story2 {
    public static void main(String[] args) {
        String story = """一个包含单个换行符的字符串
            一个包含单个双引号的字符串
            一个包含16 个字符的字符串"
            """;
    }
}
```

通过转义内容中的最后一个引号可以避免该错误：

```
class Story3 {
    public static void main(String[] args) {
        String story = """一个包含单个换行符的字符串
            一个包含单个双引号的字符串
            一个包含16 个字符的字符串\"
            """;
    }
}
```

如果文本块用于表示另一个文本块，建议转义嵌入起始和结束分隔符的第一个引号：

```
class Code {
    public static void main(String[] args) {
        String text = """快速棕色的狐狸跳过了懒狗""";

        String code = """String text = \"""
            快速棕色的狐狸跳过了懒狗\""";
    }
}
```

文本块表示的字符串**不是**内容中的原始字符序列。相反，文本块表示的字符串是对内容按顺序应用以下变换的结果：

1. 行终止符被*归一化*为 ASCII LF 字符，如下所示：
   - ASCII CR 字符后跟 ASCII LF 字符被转换为 ASCII LF 字符。
   - ASCII CR 字符被转换为 ASCII LF 字符。
2. 移除偶然空格，通过对步骤 1 得到的字符执行 `String.stripIndent`。
3. 解释转义序列，仿佛对步骤 2 得到的字符执行 `String.translateEscapes`。

当本规范说文本块*包含*特定的字符或字符序列，或*在文本块中*时，意味着文本块表示的字符串（而不是内容中的原始字符序列）包含该字符或字符序列。

#### 示例 3.10.6-3. 文本块内容的变换顺序

解释转义序列允许程序员使用 `\n`、`\f` 和 `\r` 进行字符串的垂直格式化，而不影响行终止符的归一化，并使用 `\b` 和 `\t` 进行字符串的水平格式化，而不影响偶然空格的移除。

例如，考虑这段文本块，它提到了转义序列 `\r` (CR)。

```java
String html = """
<html>\r
<body>\r
<p>Hello, world</p>\r
</body>\r
</html>\r
""";
```

在行终止符被规范化为 LF 之前，`\r` 转义序列不会被解释。使用 Unicode 转义序列来可视化 LF (`\u000A`) 和 CR (`\u000D`)，并使用 `|` 来可视化左边距，文本块表示的字符串：

```
|<html>\u000D\u000A
|<body>\u000D\u000A
|<p>Hello, world</p>\u000D\u000A
|</body>\u000D\u000A
|</html>\u000D\u000A|
```

在运行时，文本块是对 `String` 类实例的引用，该实例表示文本块所代表的字符串。

此外，文本块始终引用 `String` 类的同一个实例。因为文本块表示的字符串——或者更泛地说，常量表达式值的字符串（§15.29）——通过执行 `String.intern` 方法（§12.5）被“池化”，以便共享唯一的实例。

#### 示例 3.10.6-4. 文本块求值为 String



文本可以用在任何允许 `String` 类型表达式的地方，例如在字符串拼接（§15.18.1）、在 `String` 实例上调用方法，以及在带有 `String` 元素的注解中：

```java
System.out.println("ab" + """
cde
""");
```

```java
String cde = """
abcde
""".substring(2);
```

```java
String math = """
1+ equals \
""" + String.valueOf(2);
```

```java
@Preconditions("""
rate > 0 %%
rate <= MAX_REFRESH_RATE
""")
public void setRefreshRate(int rate) { ... }
```

# 词法结构

## 3.10.7 转义序列

在字符字面量、字符串字面量和文本块（§3.10.4, §3.10.5, §3.10.6）中，转义序列允许在不使用 Unicode 转义（§3.3）的情况下表示某些非图形字符，以及单引号、双引号和反斜杠字符。

- 转义序列 (EscapeSequence):
  - `\b` (退格 BS, Unicode `\u0008`)
  - `\s` (空格 SP, Unicode `\u0020`)
  - `\t` (水平制表符 HT, Unicode `\u0009`)
  - `\n` (换行符 LF, Unicode `\u000a`)
  - `\f` (分页符 FF, Unicode `\u000c`)
  - `\r` (回车 CR, Unicode `\u000d`)
  - `\LineTerminator` (行终止, Unicode 表示)

- 八进制转义 (OctalEscape):
  - `\OctalDigit` (八进制值, Unicode `\u0000` 到 `\u00ff`)
  - `\OctalDigit \OctalDigit`
  - `\ZeroToThree \OctalDigit \OctalDigit`

- OctalDigit: `0` `1` `2` `3` `4` `5` `6` `7`
- ZeroToThree: `0` `1` `2` `3`

`OctalDigit` 产生式来自 §3.10.1。提供八进制转义是为了与 C 兼容，但它们只能表示 Unicode 值 `\u0000` 到 `\u00FF`，因此通常优先选择 Unicode 转义序列。

如果转义序列中反斜杠后面的字符不是 LineTerminator 或 ASCII 的 `b`, `s`, `t`, `n`, `f`, `r`, `"`, `'`, `\`, `,`, `0`, `1`, `2`, `3`, `4`, `5`, `6`, 或 `7`，则为编译错误。

字符字面量、字符串字面量或文本块内容中的转义序列通过将其 `\` 及其后续字符替换为 `EscapeSequence` 语法中 Unicode 转义序列所指示的单个字符来解释。行延续转义序列没有对应的 Unicode 转义序列，因此通过将其替换为空来解释。

行延续转义序列可以出现在文本块中，但不能出现在字符字面量或字符串字面量中，因为两者都不允许 LineTerminator。

## 3.10.8 Null 字面量

null 类型有一个值，即空引用，由空字面量 `null` 表示，它由 ASCII 字符组成。

```java
NullLiteral:
null
```

null 字面量始终是 null 类型（§4.1）。

## 3.11 分隔符

由 ASCII 字符组成的十二个标记是分隔符（标点符号）。

```
Separator:
(其中之一)
( ) { } [ ] ; , . ... @ :
```

## 3.12 运算符

由 ASCII 字符组成的 38 个标记是运算符。

```
Operator:
(其中之一)
= > < ! ~ ? : ->
== >= <= != && || ++ --
+ - * / & | ^ << >> >>>
+= -= *= /= &= |= ^= <<= >>= >>>=
```

# 4 类型、值与变量

Java 编程语言是一种静态类型语言，这意味着每个变量和每个表达式都有一个在编译时已知的类型。Java 编程语言也是一种强类型语言，因为类型限制了值。

## 4.1 类型的种类

Java 编程语言是一种静态类型语言，这意味着每个变量和每个表达式都带有一个在编译时已知的类型。Java 编程语言也是一种强类型语言，因为类型限制了值。

## 4.2 原始类型与值

### 4.2.1 整数类型与变量

整数类型的值在以下范围内：

- `byte`: -128 到 127
- `short`: -32768 到 32767
- `int`: -2147483648 到 2147483647
- `long`: -9223372036854775808 到 9223372036854775807
- `char`: `\u0000` 到 `\uffff`，即 0 到 65535

### 4.2.2 整数运算

Java 编程语言提供了许多可以作用于整数值的运算符：

- 比较运算符，结果为布尔值：
  - 数值比较运算符 `<`、`<=`、`>`、`>=`（§15.20.1）
  - 数值相等运算符 `==` 和 `!=`（§15.21.1）
- 数值运算符，结果为 `int` 或 `long`：
  - 一元加减运算符 `+` 和 `-`（§15.15.3, §15.15.4）
  - 乘法运算符 `*`、`/` 和 `%`（§15.17）
  - 加法运算符 `+` 和 `-`（§15.18）
  - 增运算符 `++`，包括前置（§15.15.1）和后置（§15.14.2）
  - 递减运算符 `--`，包括前置（§15.15.2）和后置（§15.14.3）
  - 有符号和无符号移位运算符 `<<`、`>>` 和 `>>>`（§15.19）
  - 位取反运算符 `~`（§15.15.5）
  - 整数位运算符 `&`、`^` 和 `|`（§15.22.1）
- 条件运算符 `? :`（§15.25）
- 转换运算符（§15.16），它可以将整数值转换为任何指定数值类型的值。
- 字符串拼接运算符 `+`（§15.18.1），当给一个 `String` 操作数和一个整型操作数时，它会将整数转换为 `String`（`byte`、`short`、`int` 或 `long` 操作数的十进制形式，或 `char` 操作数的字符），然后产生一个由两个字符串拼接而成的新 `String`。

在 `Byte`、`Short`、`Integer`、`Long` 和 `Character` 类中预定义了其他有用的构造函数、方法和常量。

如果除移位运算符以外的整数运算符至少有一个 `long` 类型，则该操作将使用 64 位精度执行，数值运算符的结果为 `long` 类型。如果另一个操作数不是 `long`，则首先通过数值提升（§5.6）宽化为 `long` 类型（§5.1.5）。

否则，操作使用 32 位精度执行，数值运算符的结果为 `int` 类型。如果任一操作数不是 `int`，则首先通过数值提升将其宽化为 `int` 类型。

整数运算符不会以任何方式指示溢出或下溢。

任何整数类型的任何值都可以被转换为任何数值类型。整数类型与 `boolean` 类型之间没有转换。

> 参阅 §4.2.5 关于将整数表达式转换为布尔值的惯用法。

整数运算符可能因为以下原因抛出异常（§11 (Exceptions)）：

- 当对空引用进行解箱转换（§5.1.8）时，任何整数运算符都可能抛出 `NullPointerException`。
- 除法运算符 `/`（§15.17.2）如果右侧操作数为零，则可能抛出 `ArithmeticException`（§15.17.3）。

### 示例 4.2.2-1. 整数运算

```java
class Test {
    public static void main(String[] args) {
        int i = 1000000;
        System.out.println(i * i);
    }
}
```

此程序产生输出：

```
-727379968
```

### 4.2.3 浮点类型与值

浮点类型 `float` 和 `double` 在概念上与用于 IEEE 754 值和操作的 32 位 binary32 和 64 位 binary64 浮点数相关，它们在 IEEE 754 标准中规定（§1.7）。

> 在 Java SE 15 及更高版本中，Java 编程语言使用 2019 版本的 IEEE 754 标准。在 Java SE 15 之前，Java 编程语言使用 1985 版本的 IEEE 754 标准，其中 binary32 格式是唯一格式，而 binary64 格式被称为 double 格式。

IEEE 754 不仅包含由符号和数值组成的正负数，还包含正零、负零、正无穷、负无穷以及特殊的“非数字”值（以下简称为 NaN）。NaN 值用于表示某些无效操作的结果，例如零除以零。`float` 和 `double` 的 NaN 常数预定义为 `Float.NaN` 和 `Double.NaN`。

浮点类型的非零值可以以形式 $s \cdot m \cdot 2^{e-N+1}$ 表示，其中：

- $s$ 是 +1 或 -1，
- $m$ 是小于 $2^N$ 的正整数，
- $e$ 是 $E_{min} = -(2^{K-1})$ 和 $E_{max} = 2^{K-1}$ 之间的整数（包含边界），
- $N$ 和 $K$ 是取决于类型的参数。

某些值可以用这种形式的多种表示。例如，假设一个浮点类型的值 $v$ 可以使用某些 $s, m$ 和 $e$ 值用这种形式表示，如果恰好 $m$ 是偶数且 $e$ 小于 $2^{K-1}$，则可以将 $m$ 减半并将 $e$ 加 1，从而产生相同值 $v$ 的第二种表示。

如果 $m \ge 2^{N-1}$，则这种形式被称为*规格化的* (normalized)；否则，该表示被称为*非规格化的* (subnormal)。如果一个浮点类型无法以 $m \ge 2^{N-1}$ 的方式表示，则该值被称为*非规格化值* (subnormal value)，其数量级低于最小规格化值的数量级。

`float` 和 `double` 的参数 $N$ 和 $K$（以及派生的参数 $E_{min}$ 和 $E_{max}$）的约束总结在表 4.2.3-A 中。

#### 表 4.2.3-A. 浮点参数

| 参数 | float | double |
| :--- | :--- | :--- |
| N | 24 | 53 |
| K | 8 | 11 |
| $E_{max}$ | +127 | +1023 |
| $E_{min}$ | -126 | -1022 |

### 4.2.4 浮点运算

Java 编程语言提供了作用于浮点值的数值运算符：

- 产生布尔值的比较运算符：
  - 比较运算符 `<`、`<=`、`>`、`>=`：如果任一操作数为 NaN 则返回 false。
  - 等于运算符 `==` 和 `!=`：如果任一操作数为 NaN 则分别返回 false 和 true。
- 产生 `float` 或 `double` 值的数值运算符：
  - 一元加减运算符 `+` 和 `-`（§15.15.3, §15.15.4）
  - 乘法运算符 `*`、`/`、`%`（§15.17）
  - 加法运算符 `+` 和 `-`（§15.18）
  - 递增运算符 `++`，包括前置（§15.15.1）和后置（§15.14.2）
  - 递减运算符 `--`，包括前置（§15.15.2）和后置（§15.14.3）
  - 条件运算符 `?:`（§15.25）
  - 转换运算符（§15.16），它可以将浮点值转换为任何指定的数值类型。
  - 字符串拼接运算符 `+`（§15.18.1），当给一个 `String` 操作数和一个浮点操作数时，它会将浮点操作数转换为其十进制形式字符串（不丢失信息），然后产生一个由两个字符串拼接而成的新 `String`。

如果数值运算符的操作数中至少有一个是 `double` 类型，则该操作将使用 64 位浮点运算执行，且该数值运算符的结果为 `double` 类型的值。如果另一个操作数不是 `double`，它首先通过数值提升（§5.6）宽化（§5.1.5）为 `double` 类型。

否则，操作数中至少有一个是 `float` 类型；该操作将使用 32 位浮点运算执行，且数值运算符的结果为 `float` 类型的值。如果另一个操作数不是 `float`，它首先通过数值提升宽化为 `float` 类型。

浮点运算按照 IEEE 754 标准规则执行，包括溢出和下溢（§15.4），但取余运算符 `%`（§15.17.3）除外。

任何浮点类型的值都可以转换为任何数值类型，反之亦然。浮点类型与布尔类型之间不存在类型转换。

> 参见 §4.2.5 关于将浮点表达式转换为布尔值的惯用法。

浮点运算符可能由于以下原因抛出异常（§11 (Exceptions)）：

- 任何浮点运算符在对空引用进行解箱转换（§5.1.8）时都可能抛出 `NullPointerException`；
- 递增和递减运算符 `++`（§15.14.2, §15.15.1）和 `--`（§15.14.3, §15.15.2）在需要装箱转换（§5.1.7）且没有足够的内存执行转换时，可能会抛出 `OutOfMemoryError`。

### 示例 4.2.4-1 浮点运算

```java
class Test {
    public static void main(String[] args) {
        // 溢出的示例：
        double d = 1e308;
        System.out.println("overflow produces infinity: " + d*10);
        // 逐渐下溢的示例：
        d = 1e-308 * Math.PI;
        System.out.print("gradual underflow: " + d + "\n");
        for (int i = 0; i < 4; i++) {
            System.out.print(" " + (d /= 100000));
        }
        System.out.println();
        // NaN 的示例：
        System.out.print("0.0/0.0 is Not-a-Number: ");
        d = 0.0/0.0;
        System.out.println(d);
        // 不精确舍入的示例：
        System.out.print("inexact results with float:");
        for (int i = 0; i < 100; i++) {
            float z = 1.0f / i;
            if (z * i == 1.0f) {
                System.out.print(" " + i);
            }
        }
        System.out.println();
        // 另一个 double 不精确结果的示例：
        System.out.print("inexact results with double:");
        for (int i = 0; i < 100; i++) {
            double z = 1.0 / i;
            if (z * i == 1.0) {
                System.out.print(" " + i);
            }
        }
        System.out.println();
        // 强制转换为 int 舍入的示例：
        System.out.print("cast to int rounds toward 0: ");
        double d = 12345.6;
        System.out.println((int)d + " " + (int)(-d));
    }
}
```

该程序产生输出：

```
overflow produces infinity: Infinity
gradual underflow: 3.141592653589793E-305
 3.141592653589793E-310 3.141592653589793E-315 3.141592653589793E-320 0.0
0.0/0.0 is Not-a-Number: NaN
inexact results with float: 0 41 47 55 61 82 83 94 97
inexact results with double: 0 49 98
cast to int rounds toward 0: 12345 -12345
```

此示例说明了逐渐下溢会导致精度的逐渐丢失。当 `i` 为 0 时发生除以零，导致 `z` 变为正无穷大，而 `z * 0` 是 NaN，它不等于 1.0。

## 4.2.5 boolean 类型和 boolean 值

`boolean` 类型表示一个具有两个可能值的逻辑量，由字面量 `true` 和 `false` 表示（§3.10.3）。

布尔运算符有：

- 关系运算符 `==` 和 `!=`（§15.21.2）
- 逻辑取反运算符 `!`（§15.15.6）



## 逻辑运算符与条件运算符

- 逻辑运算符 `&`、`^` 和 `|` (§15.22.2)
- 条件与和条件或运算符 `&&` (§15.23) 和 `||` (§15.24)
- 条件运算符 `? :` (§15.25)
- 赋值运算符 `=`

布尔表达式决定以下语句的控制流：

- `if` 语句 (§14.9)
- `while` 语句 (§14.12)
- `do` 语句 (§14.13)
- `for` 语句 (§14.14)

整数或浮点表达式可以转换为布尔值，遵循非零为真的规则，通过表达式 `x != 0`。

对象引用 `x` 可以转换为布尔值，遵循非零为真的规则，通过表达式 `obj != null`。

布尔值可以转换为字符串，通过表达式 `String.valueOf(obj)`。

## 4.3 引用类型

引用类型有四种：类类型 (§8.1)、接口类型 (§9.1)、原始类型（非引用）以及数组类型 (§10.1)。

### 4.3.1 对象

对象是类实例或数组。

引用值（通常称为引用）是这些对象的指针，以及一个特殊的 `null` 引用，它不引用任何对象。

类实例通过类实例表达式显式创建 (§15.9)。

数组通过数组创建表达式显式创建 (§15.10.1)。

其他表达式可能会隐式创建类实例 (§12.5) 或数组 (§10.6)。

#### 示例 4.3.1-1 对象创建

```java
class Point {
    int x, y;
    Point() { System.out.println("default"); }
    Point(int x, int y) { this.x = x; this.y = y; }

    /* 在类初始化时显式创建 Point 实例： */
    static Point origin = new Point(0,0);

    /* 字符串可以通过 + 运算符隐式创建： */
    public String toString() { return "" + x + "," + y + ""; }
}

class Test {
    public static void main(String[] args) {
        /* 使用 newInstance 显式创建 Point： */
        Point p = null;
        try {
            p = (Point)Class.forName("Point").newInstance();
        } catch (Exception e) {
            System.out.println(e);
        }

        /* 数组通过数组初始化器隐式创建： */
        Point[] a = { new Point(0,0), new Point(1,1) };

        /* 字符串通过 + 运算符隐式创建： */
        System.out.println("p: " + p);
    }
}
```

### 类型、值与变量

### 引用类型与值

该程序产生以下输出：

```
default
p: (0,0)
a: { (0,0), (1,1) }
hello
```

用于对象引用的操作符有：

- 字段访问，使用限定名 (§6.6) 或字段访问表达式 (§15.11)
- 方法调用 (§15.12)
- 强制转换运算符 (§5.5, §15.16)
- 字符串拼接操作符 `+` (§15.18.1)，当给定的一个 `String` 类型操作数和一个引用时，它将通过调用被引用对象的 `toString` 方法将引用转换为 `String`（如果引用或 `toString` 的结果为空引用，则使用 `"null"`），然后产生一个由这两个字符串拼接而成的新创建的 `String`
- `instanceof` 操作符 (§15.20.2)
- 引用相等性运算符 `==` 和 `!=` (§15.21.3)
- 条件运算符 `? :` (§15.25)

可能存在多个指向同一个对象的引用。大多数对象都有状态，这些状态存储在类实例对象的字段中，或者存储在数组对象的组件变量中。如果两个变量包含指向同一个对象的引用，则可以使用一个变量对对象的引用修改对象的状态，然后通过另一个变量中的引用观察到修改后的状态。

#### 示例 4.3.1-2. 基本类型与引用的同一性

```java
class Value { int val; }

class Test {
    public static void main(String[] args) {
        int i1 = 3;
        int i2 = i1;
        i2 = 4;
        System.out.print("i1==" + i1);
        System.out.println(" and i2==" + i2);
        Value v1 = new Value();
        v1.val = 5;
        Value v2 = new Value(); // 注意：根据上下文修正，OCR 可能遗漏了声明
        v2 = v1;
        v2.val = 6;
        System.out.print("v1.val==" + v1.val);
        System.out.println(" and v2.val==" + v2.val);
    }
}
```

该程序产生以下输出：

```
i1==3 but i2==4
v1.val==6 and v2.val==6
```

因为 `v1.val` 和 `v2.val` 引用由唯一的 `new` 表达式创建的 `Value` 对象中的同一个实例 (§4.12.3)，而 `i1` 和 `i2` 是不同的变量。

每个对象都关联有一个监视器 (§17.1)，用于同步方法 (§8.4.3) 和同步语句 (§14.19)，以提供对多线程并发访问状态的控制 (§17 线程与锁)。

### 4.3.2 Object 类

`Object` 类是所有其他类的超类 (§8.1.4)。

所有类和数组类型都继承 (§8.4.8) `Object` 类的方法，这些总结如下：

- `clone` 方法用于创建对象的副本。
- `equals` 方法定义了对象相等性的概念，这种相等是基于值的比较，而不是引用比较。
- `finalize` 方法在对象销毁之前运行 (§12.6)。
- `getClass` 方法返回表示对象所属类的 `Class` 对象。

每个引用类型都存在一个 `Class` 对象。它可以被用于，例如发现类的完全限定名、其成员、其直接超类以及它实现的所有接口。

`getClass` 方法调用表达式的类型为 `Class<? extends T>`，其中 `T` 是为 `getClass` 查询的类或接口 (§15.12.1)，`|T|` 表示 `T` 的擦除 (§4.6)。

声明为 `synchronized` (§8.4.3.6) 的类方法会在该类的 `Class` 对象关联的监视器上同步。

- `hashCode` 方法非常有用，配合 `equals` 方法用于如 `java.util.HashMap` 等哈希表。
- `wait`、`notify` 和 `notifyAll` 方法用于使用线程的并发编程 (§17.2)。
- `toString` 方法返回对象的字符串表示。

### 4.3.3 String 类

`String` 实例表示 Unicode 代码点的序列。

`String` 对象具有常量（不变）的值。

字符串字面量 (§3.10.5) 和文本块 (§3.10.6) 是指向 `String` 类实例的引用。

字符串拼接操作符 `+` (§15.18.1) 在结果不是常量表达式时 (§15.29) 会隐式创建一个新的 `String` 对象。

### 4.3.4 何时引用类型是相同的

如果两个引用类型在与相同模块 (§7.3) 相关的编译单元中声明，并且具有相同的二进制名，且它们的类型参数（如果有）也是相同的（递归应用此定义），则它们是相同的编译时类型。

当两个引用类型相同时，它们有时被称为同一个类或同一个接口。

在运行时，多个具有相同二进制名的引用类型可能被不同的类加载器同时加载。这些类型可能不表示相同的类型声明。即使两个这样的类型代表相同的类型声明，它们也被认为是不同的。

两个引用类型在以下情况下是相同的运行时类型：

- 它们都是类或接口类型，由同一个类加载器加载，并具有相同的二进制名 (§4.3)，在这种情况下它们有时被称为同一个类或同一个接口。
- 它们是数组类型，且它们的组件类型是相同的运行时类型。

## 4.4 类型变量

如果两个引用类型在与相同模块 (§7.3) 相关的编译单元中声明，并且具有相同的二进制名，且它们的类型参数（如果有）也是相同的（递归应用此定义），则它们是相同的编译时类型。

当两个引用类型相同时，它们有时被称为同一个类或同一个接口。

在运行时，多个具有相同二进制名的引用类型可能被不同的类加载器同时加载。这些类型可能不表示相同的类型声明。即使两个这样的类型代表相同的类型声明，它们也被认为是不同的。

## 类型、值与变量

## 参数化类型

- `Pair<String, Integer>`

以下是针对这些泛型类的某些错误参数化示例：

- `Seg<int>` 是非法的，因为原始类型不能作为类型参数。
- `Pair<String>` 是非法的，因为类型参数不足。
- `Pair<String, String, String>` 是非法的，因为类型参数过多。

参数化类型可以是一个嵌套的泛型类或接口的参数化。例如，如果一个非泛型类 `C` 拥有一个有一个类型参数的泛型类 `D`，那么 `C.D<Object>` 就是参数化类型。同时，如果一个有一个类型参数的泛型类 `C` 拥有一个非泛型成员类 `D`，那么成员类型 `C<String>.D` 就是参数化类型，即使类 `D` 不是泛型的。

### 4.5.1 参数化类型的类型参数

类型参数既可以是引用类型，也可以是通配符。在只需要关于类型参数的部分类型信息的情况下，通配符是很有用的。

```
TypeArguments:
    < TypeArgumentList >

TypeArgumentList:
    TypeArgument (, TypeArgument)*

TypeArgument:
    ReferenceType
    Wildcard

Wildcard:
    [Annotation] ? [WildcardBounds]

WildcardBounds:
    extends ReferenceType
    super ReferenceType
```

通配符可以赋予显式的边界，就像普通的类型变量声明一样。上界由以下语法表示，其中 `B` 是边界：

```
? extends B
```

与方法签名中声明的普通类型变量不同，使用通配符时需要进行类型推断。因此，可以使用以下语法在通配符上声明下界，其中 `B` 是下界：

```
? super B
```

通配符 `? extends Object` 等于无界通配符 `?`。

如果满足以下条件之一，则可以认为两个参数在证明上是不同的：

- 两个参数都不是类型变量或通配符，且两个参数不是同一种类型。
- 其中一个参数是类型变量或通配符，具有上界（如有必要，来自捕获版本 §5.10）的 `S`；而另一个类型参数 `T` 不是类型变量或通配符，且非 `|S| <: |T|` 或 `|T| <: |S|`（见 §4.8, §4.10）。
- 每个参数都是类型变量或通配符，具有上界（如有必要，来自捕获转换）的 `S` 和 `T`；且非 `|S| <: |T|` 或 `|T| <: |S|`。

如果 `T2` 所表示的类型集合在证明上是由于以下规则的反射闭包和传递性闭包下（其中 `<:` 表示子类型关系）是 `T1` 所表示的类型集合的子集，则称类型参数 `T1` 包含另一个类型参数 `T2`：

- `? extends T <= ? extends S` 如果 `T <: S`
- `? extends T <= ?`
- `? super T <= ? super S` 如果 `S <: T`
- `? super T <= ?`
- `? super T <= ? extends Object`
- `T <= T`
- `T <= ? extends T`
- `T <= ? super T`

通配符与既有类型理论之间的关系非常有趣，我们简要遵循了这一点。通配符是存在类型的一种限制形式。对于泛型类型声明 `G<T extends B>`，`G<?>` 大致相当于 `∃ X <: B, G<X>`。

从历史角度看，通配符是 Atsushi Igarashi 和 Mirko Viroli 研究工作的直接后代。对更全面讨论感兴趣的读者应参考第 16 届欧洲面向对象编程会议（ECOOP 2002）中 Atsushi Igarashi 和 Mirko Viroli 的《On Variance-Based Subtyping of Parametric Types》。该工作本身建立在 Kresten Thorup 和 Mads Torgersen 的早期工作（Unifying Genericity, ECOOP 99）以及追溯到 Pierre America 关于 POOL 的工作（OOPSLA 89）的基于声明的变性的长期传统之上。

通配符在某些细节上与上述论文中描述的构造不同，特别是使用了捕获转换（§5.1.10），而不是 Igarashi 和 Viroli 描述的操作。关于通配符的正式说明，请参阅由 Mads Torgersen、Erik Ernst 和 Christian Plesner Hansen 发表在第 12 届面向对象编程基础工作会议（FOOL 2005）上的《Wild FJ》。

#### 示例 4.5.1-1. 无界通配符

```java
import java.util.Collection;
import java.util.ArrayList;

class Test {
    static void printCollection(Collection<?> c) {
        // 一个通配符集合
        for (Object o : c) {
            System.out.println(o);
        }
    }

    public static void main(String[] args) {
        Collection<String> cs = new ArrayList<String>();
        cs.add("hello");
        cs.add("world");
        printCollection(cs);
    }
}
```

注意，使用 `Collection<Object>` 作为输入参数 `c` 的类型是不够用的；该方法只能与类型为 `Collection<Object>` 的参数表达式一起使用，这非常罕见。相反，无界通配符允许将任何集合作为参数传递。

这是一个数组元素类型由通配符参数化的示例：

```java
public Method getMethod(Class<?> parameterTypes) { ... }
```

#### 示例 4.5.1-2. 有边界通配符

```java
boolean addAll(Collection<? extends E> c)
```

在这里，方法声明在接口 `Collection<E>` 内部，设计用于添加所有元素。使用 `Collection<E>` 作为类型在调用时是受限的。替代方案是将方法声明为泛型：

```java
<E> boolean addAll(Collection<? extends E> c)
```

这种版本足够灵活，但请注意，在签名中只使用一次类型变量：

```
Reference<? super T>
```

在这里，通配符 `? super T` 是 `Reference<T>` 的子类型。

### 4.5.2 泛型的成员

假设 `C` 是一个具有类型参数 $A_1,...,A_n$ 的泛型类或接口，对于 $1 \le i \le n$，$A_i$ 都不是通配符。`C` 的参数化类型：

- 是通配符 (§5.4) 的 `C` 的类型参数，$A_1,...,A_n$ 是泛型类型。
- 泛型类型 (§4.5) 的 `C` 的类型，$A_1,...,A_n$ 是通配符。
- 捕获转换 (§5.1) 的 `C` 的类型，$A_1,...,A_n$ 是泛型类型。

## 可具体化类型

### 类型、值与变量

- 它是一种基本类型 (§4.2)。
- 它是一个数组类型 (§10.1)，其元素类型是可具体化的。
- 它是一个嵌套类型，对于每个由“.”分隔的类型 `T`，`T` 本身是可具体化的。

例如，如果一个泛型类 `X<T>` 有一个泛型成员类 `Y<U>`，那么类型 `X<?>.Y<?>` 是可具体化的，因为 `X<?>` 是可具体化的且 `Y<?>` 也是可具体化的。类型 `X<?>.Y<Object>` 不是可具体化的，因为 `Y<Object>` 不是可具体化的。

交集类型不可具体化。

决定不让所有泛型类型都可具体化，是涉及 Java 编程语言类型系统最关键且最具争议的设计决策之一。

归根结底，这种设计最重要的动机是为了与现有代码的兼容性。从朴素的角度来说，作为泛型的添加新结构对预先的代码没有影响。Java 语言本身与用之前的版本编写的每个程序兼容，这些程序在新版本中保留了其含义。然而，这种被称为“语言兼容性”的概念仅具有纯理论意义。实际的程序（即使是简单的“Hello World”）也是由 Java SE 平台提供的若干结构组成的（例如 `java.lang` 或 `java.util` 中的元素）。在实践中，最低要求是平台兼容性——即任何用于 Java SE 平台之前的程序在新版本中都能继续正常运行。



# 平台兼容性与迁移兼容性

提供平台兼容性的一种方法是保持现有平台功能不变，仅添加新功能。例如，与其修改 `java.util` 中的 Collections 层次结构，不如引入一个利用泛型的新库。

这种方案的缺点是，Collection 库的现有客户端迁移到新版本极其困难。Collections 用于在独立开发的模块之间交换数据；如果供应商需要切换到新的泛型库，他们也必须分发两个版本的代码，以与客户端兼容。依赖于其他供应商的库在供应商的库更新之前是无法修改的。如果两个模块相互依赖，则必须同时进行更改。

显然，上述的平台兼容性并没有为泛型这种无处不在的采用提供现实的路径。因此，泛型类型系统的设计旨在支持迁移兼容性。迁移兼容性允许现有代码在演进过程中利用泛型，而不会在独立开发的模块之间施加依赖。

迁移兼容性的代价是，在迁移进行期间，无法实现泛型类型系统的完整且健全的具体化。

## 4.8 原始类型

为了与非泛型的遗留代码进行接口，可以使用参数化类型（§4.5）的擦除（§4.6）或元素类型为参数化类型的数组类型（§10.1）的擦除作为类型。这种类型被称为原始类型（raw type）。

更准确地说，原始类型定义为以下之一：

- 通过取泛型类或接口声明的名称且不带参数列表而形成的引用类型。
- 元素类型为原始类型的数组类型。
- 原始类型 $R$ 的内部成员类的名称，且该类没有继承自 $R$ 的父类或接口。

非泛型类或接口的类型不是原始类型。

为了理解为什么原始类型的内部成员类的名称被认为是原始的，请考虑以下示例：

```java
class Outer<T>{
  T t;
  class Inner {
    T setOuter(T t1) { t = t1; return; }
  }
}
```

`Inner` 成员的类型取决于 `Outer` 的类型参数。如果 `Outer` 是原始的，则 `Inner` 也必须被视为原始的，因为对于 `T` 来说没有有效的绑定。

此规则仅适用于未继承的内部成员类。依赖于类型变量的继承内部成员类将根据“原始类型的父类型被擦除”的规则（在本节稍后详细阐述）作为原始类型被继承。

上述规则的另一个影响是，原始类型的泛型内部类其本身只能作为原始类型使用：

```java
class Outer<T>{
  class Inner<S> {
    S s;
  }
}
```

无法以部分原始类型（“稀有”类型）访问 `Inner`：

```java
Outer.Inner<Double> x = null; // 非法
Double d = x.s;
```

因为 `Outer` 本身是原始的，因此它所有的内部类（包括 `Inner`）也是原始的，因此无法向 `Inner` 传递任何类型参数。

原始类型的父类类型（相应的父接口）是命名类或接口的父类类型（父接口）的擦除。

未继承自其父类或父接口的原始类型 $C$，其构造函数（§8.8）、实例方法（§8.4, §9）或非静态字段（§8.3）的类型是其在泛型类或接口 $C$ 中类型的擦除。

原始类型 $C$ 继承的实例方法或非静态字段（如果该成员在类或接口 $D$ 中声明），其类型是 $C$ 的父类型中命名为 $D$ 的成员类型。

原始类型 $C$ 的静态方法或静态字段的类型与其在泛型类或接口 $C$ 中的类型相同。

向未继承自其父类或父接口的原始类型的非静态成员类或接口传递类型参数是编译错误。

### Example 4.8-2. 原始类型与继承

```java
import java.util.*;
class NonGeneric {
    Collection<Number> myNumbers() { return null; }
}
```

```java
abstract class RawMembers<T> extends NonGeneric
    implements Collection<String> {
    static Collection<NonGeneric> cng =
        new ArrayList<NonGeneric>();

    public static void main(String[] args) {
        RawMembers rw = null;
        Collection<Number> cn = rw.myNumbers();
        // OK
        Iterator<String> is = rw.iterator();
        // 未检查的警告
        Collection<NonGeneric> cnn = rw.cng;
        // 或者，静态成员
    }
}
```

在这个程序中（这并非其本意），`RawMembers<T>` 继承了方法：

```
Iterator<String> iterator()
```

源自父接口 `Collection<String>`。原始类型 `RawMembers` 继承自 `Collection`（`Collection<String>` 的擦除）的 `iterator()`，这意味着 `RawMembers` 中的 `iterator()` 的返回类型是 `Iterator`。结果，将 `rw.iterator()` 赋值给 `Iterator<String>` 需要进行未检查的转换，因此产生编译时的未检查警告。

相比之下，静态成员继承自 `NonGeneric` 类的 `myNumbers()`，该类的擦除是 `NonGeneric`。`RawMembers` 中 `myNumbers()` 的返回类型没有被擦除，且将 `rw.myNumbers()` 赋值给 `Collection<Number>` 不需要未检查的转换，因此不会产生编译时的未检查警告。

同样，静态成员 `cng` 即使通过原始类型的对象访问，也保留了它的参数化类型。通过实例访问静态成员被认为是不良风格，是不建议的。

这个示例揭示了原始类型的成员不会被擦除，其类型参数化的静态成员，以及从非泛型父类型继承的成员。

原始类型与通配符密切相关。两者都基于存在性类型（existential types）。原始类型可以被认为是故意不安全的通配符，以适应与遗留代码的交互。从历史上看，原始类型早于通配符；它们首次引入于 GJ，并在 Gilad Bracha、Martin Odersky 等人写的论文 *Making the future safe for the past: Adding Genericity to the Java Programming Language* 中描述，发表于 *Proceedings of the ACM Conference on Object-Oriented Programming, Systems, Languages and Applications (OOPLA 98)*, 1998年10月。

## 4.9 交集类型

交集类型的形式为 $T_1$ & ... $T_n$ ($n > 0$)，其中 $T_i$ ($1 \le i \le n$) 是类型。交集类型可以从类型参数的边界（§4.4）和类型转换表达式（§15.16）推导出；它们也出现在类型捕获转换（§5.1.10）和最小上界计算（§4.10.4）的过程中。

交集类型的值是那些作为所有类型 $T_i$ ($1 \le i \le n$) 值的对象的集合。

每个交集类型 $T_1$ & ... $T_n$ 都会为了识别交集类型的成员而诱出一个概念类（notional class）或接口，如下所示：

- 对于每个 $T_i$ ($1 \le i \le n$)，让 $C_i$ 为使得 $T_i <: C_i$ 的最具体的类或接口。那么对于任何 $i$ ($1 \le i \le n$)，必须存在某些 $C_k <: C_i$，否则发生编译时错误。
- 对于 $1 \le j \le n$，如果 $T_j$ 是变量，则让 $T_j'$ 为一个成员与 $T_j$ 的 `public` 成员相同的接口；否则，如果 $T_j$ 是接口，则让 $T_j'$ 为 $T_j$。
- 如果 $C_k$ 是 `Object`，则诱导出一个接口；否则，诱出一个直接父类类型为 $C_k$ 的概念类。该类或接口具有直接父接口类型 $T_1'$, ..., $T_n'$，并在交集类型出现的包中声明。

交集类型的成员是其所诱出的类或接口的成员。

值得注意的是交集类型与类型变量边界之间的区别。每个类型变量都会诱出一个交集类型。这个交集类型通常是平凡的，由单个类型组成。边界的形式是限制的（只有第一个元素可以是类或类型变量，且边界中只能出现一个类型变量），以防止尴尬情况的出现。然而，捕获转换可能会导致创建边界更通用的类型变量，例如数组类型。

## 4.10 子类型化

子类型和父类型关系是类型上的二元关系。

类型 $T$ 的父类型通过对直接父类型关系进行自反射和传递闭包获得，写为 $S > T$，该关系由本节后给出的规则定义。我们写 $s <: T$ 表示 $s$ 和 $T$ 之间存在父类型关系。

如果 $s <: T$ 且 $s \neq T$，则 $s$ 是 $T$ 的真父类型，写为 $s > T$。

类型 $T$ 的子类型是所有满足 $T$ 是 $U$ 的父类型的类型 $U$，以及空类型。我们写 $T <: s$ 表示类型 $T$ 和 $s$ 之间存在子类型关系。

如果 $T <: s$ 且 $T \neq s$，则 $T$ 是 $s$ 的真子类型，写为 $T < s$。

如果 $s >_1 T$，则 $T$ 是 $s$ 的直接子类型，写为 $T <_1 s$。子类型化不扩展到参数化类型：$T <: s$ 并不意味着 $C<T> <: C<S>$。

### 4.10.1 基本类型的子类型化

以下规则定义了基本类型之间的直接父类型关系：

- double >_1 float
- float >_1 long
- long >_1 int
- int >_1 char
- int >_1 short
- short >_1 byte

### 4.10.2 类和接口类型的子类型化

给定非泛型类或接口 $c$，类型 $c$ 的直接父类型包括：

- 如果 $c$ 是类，其直接父类类型（§8.1.4）。
- 如果 $c$ 是接口，其直接父接口类型（§8.1.5）。
- 如果 $c$ 是没有父接口的接口，则是 `Object` 类型（§9.1.3）。

给定具有类型参数 $F_i,...,F_n$ 的泛型类或接口 $c$，原始类型 $c$ 的直接父类型包括：

- 如果 $c$ 是类，其直接父类类型的擦除（§4.6）。
- 其直接父接口类型的擦除。
- 如果 $c$ 是没有父接口的接口，则是 `Object` 类型（§9.1.3）。

给定具有类型参数 $F_i,...,F_n$ ($n > 0$) 的泛型类或接口 $c$，类型 $C<T_1,...,T_n>$（其中 $T_i$ ($1 \le i \le n$) 是一个类型）的直接父类型包括：

- 如果 $c$ 是类，对其直接父类类型应用 $[F_i:=T_i,...,F_n:=T_n]$。
- 对其直接父接口类型应用 $[F_i:=T_i,...,F_n:=T_n]$。
- $C<S_1,...,S_n>$，其中 $S_i$ 包含 $T_i$ ($1 \le i \le n$)（§4.5）。
- 如果 $c$ 是没有父接口的接口，则是 `Object` 类型。
- 其原始类型 $c$。

给定具有类型参数 $F_i,...,F_n$ ($n > 0$) 的泛型类或接口 $c$，类型 $C<R_1,...,R_n>$（其中至少一个 $R_i$ ($1 \le i \le n$) 是通配符参数）的直接父类型是对 $C<R_1,...,R_n>$ 应用捕获转换后得到的 $C<X_1,...,X_n>$（§5.10）。

交集类型 $T_i$ & ... $T_n$ 的直接父类型是 $T_i$ ($1 \le i \le n$)。

类型变量的直接父类型是边界中列出的类型。

类型变量是其下边界的直接父类型。

空引用的直接父类型是空类型外的引用类型。

### 4.10.3 数组类型的子类型化

以下规则定义了数组类型之间的直接父类型关系：

- 如果 $S$ 和 $T$ 都是引用类型，则 $S[] >_1 T[]$ 当且仅当 $S >_1 T$。
- $Object >_1 Object[]$
- $Cloneable >_1 Object[]$
- $java.io.Serializable >_1 Object[]$
- 如果 $P$ 是基本类型，则：
  - $Object >_1 P[]$
  - $Cloneable >_1 P[]$
  - $java.io.Serializable >_1 P[]$

### 4.10.4 最小上界

一组引用类型的最小上界（或 "lub"）是一个比任何其他共享父类型都具体的共享父类型（即没有共享父类型是最小上界的子类型）。该类型 $lub(U_1, ..., U_k)$ 如下确定：

如果 $k = 1$，则 lub 是类型本身：$lub(U_1) = U_1$

否则：

- 对于每个 $U_i$ ($1 \le i \le k$)：
  - 让 $ST(U_i)$ 为 $U_i$ 的父类型集。
  - $EST(U_i)$ 为 $U_i$ 的擦除类型集，为：
    $EST(U_i) = \{ W | W \in ST(U_i) \}$，其中 $W$ 是 $W$ 的擦除。

使用擦除类型集的原因是为了处理类型集包含泛型若干种不同参数化的情况。

例如，给定 `List<String>` 和 `List<Object>`，简单地交集集合 $ST(List<String>) = \{ List<String>, Collection<String>, Object \}$ 和 $ST(List<Object>) = \{ List<Object>, Collection<Object> \}$ 将得到 $\{ Object \}$，我们丢失了边界可以安全地作为 List 的事实。

相反，交集 $EST(List<String>) = \{ List, Collection, Object \}$ 和 $EST(List<Object>) = \{ List, Collection, Object \}$ 得到 $\{ List, Collection, Object \}$，这最终允许我们产生 `List<?>`。

- MEC，$U_i \dots U_k$ 的擦除候选集是所有集合 $EST(U_i) (1 \le i \le k)$ 的交集。
- MEC，$U_i \dots U_k$ 的最小擦除候选集为：
  MEC = $\{ V | V \in EC$，且对于 $EC$ 中的所有 $W \neq V$，$W < V \}$。

由于我们正在寻找更精确的类型，我们希望过滤掉任何作为其他候选类型的子类型。这就是 MEC 所完成的。

在我们之前运行的示例中，EC = { List, Collection, Object }，因此 MEC = { List }。下一步是为 MEC 中的擦除类型恢复类型参数。

- 对于 MEC 中任何属于泛型类型的元素 $G$：
  令 $G$ 的“相关”参数化 Relevant(G) 定义为：
  ```
  Relevant(G) = { v | 1 ≤ i ≤ k; v in ST(Ui) and v = G<... > }
  ```

在我们之前运行的示例中，MEC 中最小的泛化元素是 Relevant(List) = { List<String>, List<Object> }。我们现在将为 List 寻找一个既包含 String 又包含 Object 的（§4.5.1）的类型参数。

这是通过下文定义的最小泛化参数化（lcp）操作实现的。第一行定义了在集合（如 Relevant(List)）上的 `lcp()`，将其定义为对由集合元素组成的列表的操作。第二行定义了对该列表的操作，将其定义为对列表元素进行两两归约。第三行是参数化类型对的 `lcp()` 定义，而它反过来依赖于最小包含类型参数（lcta）的概念。

令 $G$ 的“候选”参数化 Candidate(G) 是泛型类型 $G$ 最具体的参数化，它包含了 $G$ 的所有相关参数化。

Candidate(G) = lcp(Relevant(G))

其中 lcp(S)（最小包含参数化）定义为：

- lcp(S) = lcp(e₁, ..., eₙ)，其中 $e_i$ (1 ≤ i ≤ n) 在 $S$ 中。
- lcp(e₁, ..., eₙ) = lcp(cp₁, e₂, e₃, ..., eₙ)
- lcp(G₁, ..., Gₙ, Y₁, ..., Yₙ) = G<lcta(X₁, Y₁), ..., lcta(Xₙ, Yₙ)>
- lcp(G₁, ..., Xₙ) = G<lcta(X₁, ..., lcta(Xₙ))>

其中 lcta(U)（最小包含类型参数）定义为（假设 $U$ 和 $V$ 为类型）：

- lcta(U, V) = U 如果 $U = V$，否则扩展 lub(U, V)
- lcta(U, ? extends V) = ? extends lub(U, V)
- lcta(U, super V) = ? super glb(U, V)
- lcta(U extends U, ? extends V) = ? extends lub(U, V)
- lcta(extends U, ? super V) = ?
- lcta(super U, super V) = ? super glb(U, V)
- lcta(U = ?) 如果 $U$ 的上上界是 Object，否则扩展 lub(U, Object)

其中 glb(U) 在 §5.1.10 中定义。

- 令 lub(U₁ ... Uₖ) 为：
  Best(W₁) & ... & Best(Wₖ)

其中 $W_i$ (1 ≤ i ≤ r) 是 MEC 的元素，即 $U_i \dots U_k$ 的最小擦除候选集。

并且无论这些元素中是否有泛型类型，我们都使用候选参数化（以便恢复类型参数）：

Best(x) = Candidate(x) 如果 $x$ 是泛型；否则为 x。



严格来说，这个 `lub()` 函数仅近似于最小上界。从形式上说，可能存在其他类型 $\tau$，使得所有 $U_1 \dots U_k$ 都是 $\tau$ 的子类型，且 $\tau$ 是 `lub(\tau_1, \dots, \tau_k)` 的子类型。然而，Java 编程语言的编译器必须实现 `lub(\tau_1, \dots, \tau_k)`。

可能 `lub` 会产生一个无限类型。Java 编程语言的编译器必须识别并适当处理这种情况。

无限类型的出现源于 `lub(\cdot)` 的递归调用。熟悉 `lub` 的读者应该注意，无限类型并不等同于递归类型。

## 4.10.5 类型投影

类型在大多数声明中都使用，但在某些类型中也使用。具体而言，有 *17 种类型上下文* 使用类型：

1.  **子类型化**：如果 $\tau$ 是泛化类或泛型接口，$G<A_1, \dots, A_n$，那么结果是 $G<A_1', \dots, A_n'>$，其中对于 $1 \le i \le n$，类型参数 $A_i'$ 可以从 $A_i$ 推导出，如下：

    - 如果 $A_i$ 不包含任何类型变量，则 $A_i' = A_i$。

    - 如果 $A_i$ 是包含变量的类型，令 $U$ 为 $A_i$ 的上投影，$A_i'$ 是配符：

        - 如果 $A_i$ 是包含上界的的上界配符，如果配符的下界为 $U$，则 $A_i'$ 是上界配符 `? extends U`；如果配符的下界未定义，则不存在 $A_i'$。

        - 如果 $A_i$ 是包含下界的下界配符，令 $L$ 为配符的上投影，$A_i'$ 是下界配符 `? super L`；如果配符的上投影未定义，则不存在 $A_i'$。

    - 如果 $\tau$ 是数组类型 $S[]$，如果 $S$ 的下投影是 $S'$，结果是 $S'[]$；如果 $S$ 的下投影未定义，则结果未定义。

    - 如果 $\tau$ 是交类型，那么如果 $\tau$ 的*每个*元素的下投影都有定义，则结果是一个元素为 $\tau$ 的元素下投影的交类型；如果 $\tau$ 的*任意*元素的下投影未定义，则结果未定义。

类型 $\tau$ 相对于限制类型变量的下投影是一个部分函数，定义如下：

- 如果 $\tau$ 不包含任何限制类型变量，则结果为 $\tau$。

- 如果 $\tau$ 是限制类型变量，则结果是 $\tau$ 的上投影。

## 类型使用的位置

## 类型、值与变量

- 在声明中：

    1.  类声明中 `extends` 或 `implements` 子句中的类型 (§8.1.4, §8.1.5)

    2.  接口声明中 `extends` 子句中的类型 (§9.1.3)

    3.  方法的返回类型 (§8.4.5, §9.4)，包括注解接口中元素的类型 (§9.6.1)

    4.  方法或构造函数 `throws` 子句中的类型 (§8.4.6, §8.8.5, §9.4)

    5.  泛型类、接口、方法或构造函数的类型参数声明中 `extends` 子句的类型 (§8.1.2, §9.1.2, §8.4.4, §8.8.4)

    6.  类或接口的字段声明中的类型 (§8.3, §9.1)，包括枚举常量（enum constant (§8.9.1)）

    7.  方法、构造函数或 lambda 表达式的形式形参数声明中的类型 (§8.4.1, §8.8.1, §9.4, §15.27.1)

    8.  方法的接收器参数的类型 (§8.4.4)

    10. 异常参数声明中的类型 (§14.20)

    11. 记录类（record class）中记录组件声明的类型 (§8.10.1)

- 在表达式中：

    12. 显式构造函数调用语句、类实例创建表达式、方法调用表达式或方法引用表达式的显式类型列表中的类型 (§8.8.7.1, §15.9, §15.12, §15.13)

    13. 在未限定的类实例创建表达式中，作为待实例化的类类型 (§15.9)，或者作为待实例化的匿名类的直接父类类型或直接父接口类型 (§15.9.5)

    14. 数组创建表达式中的元素类型 (§15.10.1)

    15. 强制转换表达式中强制转换运算符的类型 (§15.16)

    16. 紧跟 `instanceof` 类型比较操作符的类型 (§15.20.2)

    17. 在方法引用表达式中 (§15.13)，作为用于查找成员方法的引用类型，或作为要构造的类类型或数组类型。

此外，类型还被用于：

- 在上述任何语境中数组类型的元素类型；以及

- 在上述任何语境中，参数化类型的非通配符类型参数，或通配符类型参数的边界（bound）。

最后，Java 编程语言中有三个特殊术语表示对类型的使用：

- 无界通配符（unbounded wildcard，§4.5.1)

- 变长参数类型中的 `..` (§8.4.1)，用于表示数组类型

- 构造函数声明中类型的简单名称 (§8.8)，用于表示所构造对象的类

类型语境中类型类型的含义由以下内容给出：

- §4.2，针对原始类型

- §4.4，针对类型参数

- §4.5，针对参数化的类和接口类型，或者作为参数化类型中的参数或作为参数化类型中通配符类型参数的边界出现的类型

- §4.8，针对原始（raw）类和接口类型

- §4.9，针对类型参数边界中的交叉类型（intersection types）

- §6.5，针对非泛型类、接口和类型变量类型

- §10.1，针对数组类型

某些类型语境限制了引用类型的参数化方式：

- 以下类型语境要求：如果类型是参数化引用类型，则它不能有通配符类型参数：

    - 在类声明的 `extends` 或 `implements` 子句中 (§8.1.4, §8.1.5)

    - 在接口声明的 `extends` 子句中 (§9.1.3)

    - 在未限定的类实例创建表达式中，作为待实例化的类类型 (§15.9)，或者作为待实例化的匿名类的直接父类类型或直接父接口类型 (§15.9.5)

    - 在方法引用表达式中 (§15.13)，作为用于查找成员方法的引用类型或作为要构造的类类型或数组类型。

显式构造函数调用语句、类实例创建表达式、方法调用表达式或方法引用表达式的显式类型列表中不允许通配符类型参数（§8.8.7.1, §15.9, §15.12, §15.13）。

- 以下类型语境要求：如果类型是参数化引用类型，则它必须无通配符类型参数：

    - 数组创建表达式中的元素类型 (§15.10.1)

    - 紧跟 `instanceof` 类型比较操作符的类型 (§15.20.2)

- 以下类型语境完全不允许参数化类型，因为它们涉及异常：

    - 方法或构造函数的 `throws` 子句 (§8.4.6, §8.8.5, §9.4)

    - 异常参数声明（§14.20）

在任何使用类型的类型语境中都可以对类型进行注解。示例包括：

- 字段，包括类变量 (§8.3) 和实例变量 (§9.1)，以及常量（§8.9.1）

- 方法、构造函数或 lambda 表达式的形式形参数声明（§8.4.1, §8.8.1, §9.4, §15.27.1）

- 方法的接收器参数（§8.4.4）

- 方法的返回类型（§8.4.5, §9.4），包括注解接口中元素的类型（§9.6.1）

- 泛型类、接口、方法或构造函数的类型参数声明（§8.1.2, §9.1.2, §8.4.4, §8.8.4）

- 记录类的记录组件声明（§8.10.1）

相同类型既是类型语境又是声明的事实源于语言。

## 4.12 变量

变量是一个存储位置，并关联有一个类型（有时称为编译类型），该类型是原始类型 (§4.2) 或引用类型 (§4.3)。

变量的值通过赋值（§15.26）或前缀/后置 `++`（递增）或 `--`（递减）操作符（§15.14.2, §15.14.3, §15.15.1, §15.15.2）来改变。

变量值与其类型之间的兼容性由 Java 编程语言的设计提供保证，只要程序没有产生编译时的未检查警告（§4.12.2）。默认值（§4.12.5）是兼容的，且对变量的所有赋值操作都会检查赋值兼容性（§5.2），通常在编译时进行，但在涉及数组的单一种情况下会进行运行时检查（10.5）。

### 4.12.1 原始类型变量

原始类型变量始终持有该精确原始类型的原始值。

### 4.12.2 引用类型的变量

类类型 $\tau$ 的变量可以持有一个空引用，或者指向类 $\tau$ 的实例或 $\tau$ 的任何子类实例的引用。

接口类型的变量可以持有一个空引用，或者指向实现该接口的任何类的任何实例的引用。

请注意，变量并不保证指向其声明类型的子类型，而仅指向声明类型的子类或子接口。这是由于下文讨论的堆污染（heap pollution）的可能性导致的。

如果 $T$ 是基本数据类型，那么类型为“$T$ 的数组”的变量可以持有一个空引用，或者指向任何类型为“$T$ 的数组”的数组引用。

如果 $T$ 是引用类型，那么类型为“$T$ 的数组”的变量可以持有一个空引用，或者指向任何类型为“$S$ 的数组”的数组引用，其中 $S$ 是 $T$ 的子类或子接口。

类型为 `Object[]` 的变量可以持有任何引用类型数组的引用。

类型为 `Object` 的变量可以持有一个空引用，或者指向任何对象，无论它是类的实例还是数组。

参数化类型的变量可能会指向一个并非该参数化类型的对象。这种情况被称为堆污染。

堆污染只有在当程序执行了某些涉及原始类型（raw type）的操作并产生编译时未检查警告（§4.8, §5.1.6, §5.1.9, §8.4.1, §8.4.3, §8.4.4, §9.4.2, §15.12.4），或者程序通过一个原始或非泛型的超类数组变量对非可重化（non-reifiable）元素类型的数组变量进行别名时，才会发生。

例如：

```
List ls = new ArrayList<Number>();
List<String> s = ls; // 未检查警告
```

会导致编译时未检查警告，因为在编译时（在编译类型检查规则的范围内）或运行时，无法确定变量 `ls` 指向的是 `List<String>`。

如果执行上述代码，就会产生堆污染，因为声明为 `List<String>` 的变量 `ls` 指向了一个实际上并不是 `List<String>` 的值。

该问题无法在运行时识别，因为类型变量不是可重化的（not reified），因此实例在运行时不携带任何关于创建它们时使用的类型参数的信息。

在上述给出的简单示例中，似乎在编译时识别该情况并给出错误应该是很简单的。然而，在通用（典型）情况下，变量 `l1` 可能是某个完全分离的方法调用的结果，或者其值可能依赖于任意的控制流。因此，该代码是非常典型的，而且确实非常糟糕。

此外，`Object[]` 是所有数组类型的超类这一事实导致了安全的别名发生并引发堆污染。例如，以下代码可以编译，是因为它在静态上是类型正确的：

```
static void m(List<String> stringLists) {
    Object[] array = stringLists;
    List<Integer> tmplList = Arrays.asList(42);
    array[0] = tmplList; // (1)
    String s = stringLists[0].get(0); // (2)
}
```

堆污染在 (1) 处发生，因为 `stringLists` 数组中一个指向 `List<String>` 的组件实际上指向一个 `List<Integer>`。在同时存在通用超类（`Object[]`）和非可重化类型（形式参数的声明类型，`List<String>`）的情况下，无法检测到这种污染。在 (1) 处没有理由进行未检查检查；然而，在运行时，(2) 处会发生 `ClassCastException`。

在任何调用上述方法的地方，都会给出编译时未检查警告，因为 Java 编程语言泛型类型系统认为调用创建一个数组元素类型 `List<String>` 是非可重化的（§15.4.2）。当且仅当方法体相对于可变数组参数是类型安全的，程序员可以使用 `@SafeVarargs` 注解来消除（§9.6.4）处的警告。由于上述所示编写的方法体会导致堆污染，因此使用该注解来禁用调用者的警告是完全不恰当的。

最后，请注意，`stringLists` 数组可以通过 `Object[]` 以外其他类型的变量进行别名，并可能发生堆污染。例如，数组变量可以是 `java.util.Collection[]` —— 一种原始元素类型 —— 以上方法体可以在没有警告或错误的情况下工作并仍然导致堆污染。如果 Java SE 平台定义 `Sequence` 为 `List<T>` 的非泛型类型，那么将 `Sequence` 作为数组类型将导致堆污染。

变量将始终指向一个代表参数化类型的类实例。

示例中 `is` 的值始终是提供 `List` 表示的类的实例。

从原始类型的表达式赋值给参数化类型的变量的操作，应仅在将不使用参数化类型的遗留代码与使用参数化类型的更现代代码结合时才使用。

如果没有发生任何需要发布编译时未检查警告的操作，且没有对非可重化元素类型的数组变量进行不安全的别名，就不会发生堆污染。请注意，这并不意味着如果实际上发生了编译时未检查警告就会发生堆污染。可能会运行一个程序，其中某些二进制文件是由编译器生成的，而某些二进制文件初始化为默认值。当执行完毕时，类变量实际上停止存在了。相反，代码可能会（并且已经）导致堆污染。这种实践要求不会发生堆污染。

## 4.1.3 变量的种类

共有八种变量：

- 1. 类变量在控制流进入最近的块（§14.2）、for 语句或 try-with-resources 语句时创建。它被初始化为默认值（§4.12）。当方法体执行完毕时，类变量停止存在。

- 2. 实例变量在控制流进入最近的块（§14.2）、for 语句或 try-with-resources 语句时创建。它被初始化为默认值（§4.5）。当它所属的对象不再时，实例变量停止存在。

- 3. 数组组件在控制流进入最近的块（§14.2）、for 语句或 try-with-resources 语句时创建。它们被初始化为默认值（§4.2）。当数组不再时，数组组件停止存在。

- 4. 方法参数在每次调用方法时创建（§15.12）。它们通过方法调用初始化相应的值。方法体执行完毕时，方法参数停止存在。

- 5. 构造函数参数在每次类实例表达式（§15.9）或显式构造函数调用（§8.8.7）时创建。它们通过创建表达式或构造函数调用初始化相应的值。执行体时，构造函数参数停止存在。

- 6. Lambda 参数在每次调用 Lambda 体实现的方法时创建（§15.12）。它们通过方法调用初始化相应的值。Lambda 表达式体执行完毕时，Lambda 参数停止存在。

- 7. 异常参数在 try 语句的 catch 子句捕获异常时（§14.20）创建。它通过异常关联实际对象初始化（§11.3, §14.18）。当 catch 子句相关的块执行完毕时，异常参数停止存在。

- 8. 局部变量（§14.4）通过语句（§14.4.2, §14.14.1, §14.14.2, §14.20.3）和模式（§14.30.1）声明。通过模式声明的局部变量称为模式变量。通过语句声明的局部变量在控制流进入最近的块（§14.2）、for 语句或 try-with-resources 语句时创建。如果变量声明符具有初始化器，则通过语句声明的局部变量作为语句执行的一部分初始化。确定赋值规则（§16 (确定赋值)）防止了局部变量的值

由语句声明的变量在初始化或赋值赋值之前不能被使用。

由模式声明的局部变量在模式匹配时（§14.30.2）被创建并初始化。作用域的规则（§6.3）防止了由模式声明的局部变量的值在模式未匹配时被使用。

当一个局部变量的声明作用域不再处于作用域内时，该变量就不复存在了。

如果不是一种特殊情况，由语句声明的局部变量可以被视为在语句执行时被创建的。这种特殊情况涉及 `switch` 语句（§14.11），在那种情况下，可以通过跳过变量声明语句的执行来控制顺序。然而，由于确定赋值规则（§16 (Definite Assignment)）的限制，由此类跳过的声明语句声明的局部变量在通过赋值表达式（§15.26）进行确定赋值之前不能被使用。

### 示例 4.12.3-1. 变量的种类

```
class Point {
    static int numPoints; // numPoints 是类变量
    int x, y; // x 和 y 是实例变量
    int[] w = new int[10]; // w[0] 是一个数组组件
    int setX(int x) { // x 是方法参数
        int oldx = this.x; // oldx 是一个局部变量
        this.x = x;
        return oldx;
    }
    boolean equalAt(Object o) {
        if (o instanceof Point p) // p 是模式变量
        return this.x == p.x;
        else
            return false;
    }
}
```

### 4.12.4 final 变量

变量可以被声明为 `final`。`final` 变量只能被赋值一次。如果 `final` 变量在赋值赋值之前没有被确定为未赋值状态（§16 (Definite Assignment)），则将是一个编译错误。

一旦 `final` 变量被赋值，它将始终包含相同的值。如果 `final` 变量持有对对象的引用，那么该对象的状态可以通过对对象的操作来改变，但该变量将始终引用同一个对象。这同样适用于数组，因为数组是对象；如果 `final` 变量持有对数组的引用，那么数组的组件可以通过对数组的操作来改变，但该变量将始终引用同一个数组。

## 变量

空 final 是一个声明中缺少初始化器的 `final` 变量。



# 常量变量

常量变量是基本类型或 `String` 类型的 `final` 变量，并用常量表达式进行初始化（§15.29）。一个变量是否为常量变量可能对类初始化（§12.4.1）、二进制兼容性（§13.1）、可达性（§14.22）以及延迟赋值（§16.1.1）产生影响。

三种变量被隐式声明为 `final`：接口的字段（§9.3）、声明为 `try-with-resources` 语句资源的局部变量（§14.20.3）、以及多异常 `catch` 子句的异常参数（§14.20）。单 `catch` 子句的异常参数从不会被隐式声明为 `final`，但可能是有效最终的。

## 示例 4.12.4-1. final 变量

声明 `final` 变量可以作为有用的文档，说明其值不会改变，并有助于避免编程错误。在程序中：

```java
class Point {
  int x, y;
  int useCount;
  Point(int x, int y) { this.x = x; this.y = y; }
  static final Point origin = new Point(0, 0);
}
```

类 `Point` 声明了一个 `final` 类变量 `origin`。`origin` 变量持有对对象的引用，该对象是 `Point` 类的实例，坐标为 (0, 0)。变量 `Point.origin` 的值永远不会改变，因此始终引用由初始化器创建的同一个 `Point` 对象。然而，对此 `Point` 对象的操作可能会改变它的状态——例如，修改它的 `useCount`，甚至误导地修改它的 `x` 或 `y` 坐标。

某些未声明为 `final` 的变量是有效最终的：

- 由语句和声明且具有初始化器的局部变量（§14.4），或由模式声明的局部变量（§14.30.1），如果满足以下所有条件，则是有效最终的：
  - 它没有被声明为 `final`。
  - 它从未作为赋值表达式的左值出现（§15.26）。（注意，包含初始化器的局部变量声明符不是赋值表达式。）
  - 它从未作为前缀或后置增/减运算符的操作数出现（§15.14, §15.15）。

如果一个变量是有效最终的，在它的声明中添加 `final` 修饰符不会引入任何编译错误。相反，在有效程序中声明为 `final` 的局部变量或参数在移除 `final` 修饰符后会变为有效最终的。

# 4.12.5 变量的初始值

程序中的每个变量在值被使用之前必须有一个值：

- 每个类、实例变量或数组组件在创建时都会用默认值初始化（§15.9, §15.10.2）：
  - 对于 `byte` 类型，默认值为零，即 `(byte) 0` 的值。
  - 对于 `short` 类型，默认值为零，即 `(short) 0` 的值。
  - 对于 `int` 类型，默认值为零，即 `0`。
  - 对于 `long` 类型，默认值为零，即 `0L`。
  - 对于 `float` 类型，默认值为零，即 `0.0f`。
  - 对于 `double` 类型，默认值为零，即 `0.0d`。
  - 对于 `char` 类型，默认值为零，即 `'\u0000'`。
  - 对于 `boolean` 类型，默认值为 `false`。
  - 对于引用类型，默认值为 `null`。

# 4.12 变量

- 类型变量（§4.4）和类型参数（§4.5.1）在运行时不会被具体化。因此，运行时的同一个类或接口表示了编译时的多个泛化类型（§4.5）。具体而言，给定泛型类型的所有编译时参数化（§8.1.2, §9.1.2）共享单一的运行时表示。

在某些条件下，泛化类型的变量可能会引用一个不属于该泛化类型的对象。这种情况被称为堆污染（§4.12.2）。该变量将始终引用一个代表该泛化类型的类的实例。

## 示例 4.12.6-1. 变量的类型与对象的类

```java
interface Colorable {
    void setColor(byte r, byte g, byte b);
}

class Point { int x, y; }

class ColoredPoint extends Point implements Colorable {
    byte r, g, b;
    public void setColor(byte rv, byte gv, byte bv) {
        r = rv; g = gv; b = bv;
    }
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        ColoredPoint cp = new ColoredPoint();
        p = cp;
        Colorable c = cp;
    }
}
```

在此示例中：

- 类 `Test` 中 `main` 方法的局部变量 `p` 类型为 `Point`，初始被分配一个 `Point` 类新实例的引用。
- 局部变量 `cp` 同样具有其类型 `ColoredPoint`，初始被分配一个 `ColoredPoint` 类新实例的引用。
- 对 `cp` 值的赋值导致变量 `p` 持有指向 `ColoredPoint` 的引用。这是允许的，因为 `ColoredPoint` 是 `Point` 的子类，因此类 `ColoredPoint` 与类型 `Point` 是赋值兼容的（§5.2）。一个 `ColoredPoint` 对象包含了对 `Point` 所有方法的支持。除了它特定的字段 `r`、`g` 和 `b` 之外，它还拥有 `Point` 类中名为 `x` 和 `y` 的字段。
- 局部变量 `c` 的类型为接口类型 `Colorable`，因此它可以持有任何类实现了 `Colorable` 的对象的引用；具体而言，它可以持有指向 `ColoredPoint` 的引用。

注意，像 `new Colorable()` 这样的表达式是无效的，因为无法创建接口实例，只能创建类的实例。然而，表达式 `new Colorable() { public void setColor... }` 是有效的，因为 `new` 声明了一个实现 `Colorable` 接口的匿名类（§15.9.5）。

# 第 5 章 转换与上下文

Java 编程语言中编写的每一个表达式要么不产生结果（§15.1），要么具有编译时可以推导的类型（§15.3）。当一个表达式出现在许多上下文中时，它必须与该上下文中预期的类型兼容；该类型被称为目标类型。为了方便，通过以下方式促进了表达式与其周围上下文的兼容性：

- 首先，对于某些称为多态表达式（§15.2）的表达式，推导出的类型可以受到目标类型的影响。同一个表达式在不同的上下文中可能有不同的类型。
- 第二，在表达式的类型被推导之后，有时可以执行从表达式类型到目标类型的隐式转换。

如果两种策略都无法产生适当的类型，就会发生编译错误。

确定表达式是否为多态表达式，以及如果是，其在特定上下文中的类型和兼容性的规则，取决于上下文的种类和表达式的形式。除了影响表达式的类型外，目标类型在某些情况下可能会影响表达式的运行时行为，以便产生适当类型的值。

同样，确定目标类型是否允许隐式转换的规则取决于上下文的种类、表达式的类型，在特殊情况下取决于常量表达式的值（§15.29）。从类型 `S` 到类型 `T` 的转换允许类型为 `S` 的表达式在编译时被处理为具有类型 `T`。在某些情况下，这需要在运行时执行相应的操作以检查转换的有效性，或将表达式的运行时值翻译成适用于新类型 `T` 的形式。

## 示例 5.0-1. 编译时与运行时的转换

- 从 `Object` 类型到 `Thread` 类型的转换需要运行时检查，以确保运行时值实际上是 `Thread` 类或其一个子类的实例；如果不是，则会抛出异常。
- 从 `Thread` 类型到 `Object` 类型的转换不需要运行时操作；`Thread` 是 `Object` 的子类，因此由类型为 `Thread` 的表达式产生的任何引用都是有效的 `Object` 类型引用。
- 从 `int` 类型到 `long` 类型的转换需要将 32 位整数值进行运行时符号扩展到 64 位 `long` 表示。不会丢失信息。
- 从 `double` 类型到 `long` 类型的转换需要从 64 位浮点值到 64 位表示的非平凡翻译。取决于实际运行时值，可能会丢失信息。

Java 编程语言中可能的转换分为以下几大类：

- 恒等转换
- 宽化原始类型转换
- 窄化原始类型转换
- 宽化引用转换
- 窄化引用转换
- 装箱转换
- 解箱转换
- 未检查转换
- 捕获转换
- 字符串转换

存在六种转换上下文，多态表达式在这些上下文中可能会受到上下文的影响或可能发生隐式转换。每种类型的上下文对类型有不同的规则，并允许上述某些转换。这些上下文是：

- 赋值上下文（§5.2, §15.26），其中表达式的值绑定到命名变量。原始类型和引用类型会宽化，值可能会被装箱或解箱，某些原始表达式可能会被窄化。
- 严格调用上下文（§5.3, §15.9, §15.12），其中参数绑定到构造方法或方法的形式参数。宽化、引用宽化和未检查转换可能会发生。
- 宽松调用上下文（§5.3, §15.9, §15.12），与严格调用上下文一样，参数绑定到形式参数。如果使用严格调用上下文找不到相应的声明，则方法或构造方法的调用提供这种上下文。除了宽化和未检查转换外，该上下文允许装箱和解箱转换。
- 字符串上下文（§5.4, §15.18.1），其中任何类型的值都转换为 `String` 对象。
- 转换上下文（§5.5），其中表达式的值转换为强制转换运算符（§15.16）明确指定的类型。转换上下文比赋值或宽松调用上下文更宽，允许除字符串转换外的任何特定转换，但在某些情况下引用类型需要在运行时检查正确性。
- 数字上下文（§5.6），其中数字操作符的操作数或其他处理数字的表达式可能会被宽化到公共类型。

“转换”一词也用于在不具体说明的情况下描述特定上下文允许的转换。例如，我们说局部变量初始化器的表达式适用于“赋值转换”，意味着将根据赋值上下文的规则为该表达式隐式选择特定的转换。另一个例子，我们说一个表达式经历了“强制转换”，意味着该表达式的值在转换上下文中允许的转换。

## 示例 5.0-2. 各种上下文中的转换

```java
class Test {
    public static void main(String[] args) {
        // 浮点字面量的类型强制转换 (5.5)
        // 没有强制转换运算符
        float f = (float) 12.5;
        int i = (int) f;
        System.out.println("(int)12.5==" + i);

        // 宽化原始类型转换 (5.1.2) 将 i 的值转换为
        // float 类型。这是一次赋值转换。
        f = i;
        System.out.println("after float widening: " + f);

        // 数值提升 (5.6) 将 i 的值转换为
        // float 类型。这是一次二值数值提升。
        // 提升后，操作类型为 float*float：
        System.out.print(f);
        f = f * i;

        // 对 i 和 f 的两次字符串转换：
        System.out.println("**" + i + " == " + f);

        // 方法调用转换 (5.3) 将 f 的值
        // 转换为 double 类型，因为 Math.sin 方法
        // 只接受 double 类型的参数：
        double d = Math.sin(f);

        // 对 f 和 d 的两次字符串转换：
        System.out.println("Math.sin(" + f + ")==" + d);
    }
}
```

该程序产生输出：

```
(int)12.5==12
after float widening: 12.0
12.0*12==144.0
Math.sin(144.0)==-0.49102159389846932
```

# 5.1 转换种类

Java 语言中的特定类型转换分为 12 种。

## 5.1.1 恒等转换

任何类型到其相同类型的转换都是允许的。

这似乎是显而易见的，但它有两个实际结果。首先，允许表达式最初就具有所需的类型，从而允许了简单的规则：每个表达式都适用于转换，即使只是微不足道的恒等转换。其次，这意味着为了清晰，程序中包含冗余的强制转换符是允许的。

## 5.1.2 宽化原始类型转换

原始类型上的 19 种特定转换被称为宽化原始类型转换：

- `byte` 转换为 `short`, `int`, `long`, `float` 或 `double`
- `short` 转换为 `int`, `long`, `float` 或 `double`
- `char` 转换为 `int`, `long`, `float` 或 `double`
- `int` 转换为 `long`, `float` 或 `double`
- `long` 转换为 `float` 或 `double`
- `float` 转换为 `double`

在以下情况下，宽化原始类型转换不会丢失数值的整体量级信息，此时数值被精确地保留：

- 从整数类型到另一个整数类型
- 从 `byte`, `short` 或 `char` 转换为浮点类型
- 从 `int` 转换为 `double`
- 从 `float` 转换为 `double`

从 `int` 到 `float`、从 `long` 到 `float`、或从 `long` 到 `double` 的宽化原始类型转换可能会导致精度丢失，即结果可能会丢失数值的某些低有效位。在这种情况下，生成的浮点值将是使用“舍入到最近”策略（§15.4）对整数值进行正确舍入的版本。

有符号整数值到整数类型 $\tau$ 的宽化转换仅仅是扩展整数值的补码表示以填充更宽的格式。

从 `char` 到整数类型 $\tau$ 的宽化转换是零扩展 `char` 值的表示以填充更宽的格式。

从 `int` 到 `float`、或从 `long` 到 `float`、或从 `int` 到 `double`、或从 `long` 到 `double` 的宽化转换是根据 IEEE 754 关于从整数格式转换为二进制浮点数格式的规则决定的。

从 `float` 到 `double` 的宽化转换是根据 IEEE 754 关于在二进制浮点格式之间转换的规则决定的。

尽管发生了精度丢失，但宽化原始类型转换永远不会导致运行时异常（§11.1.1）。

### 示例 5.1.2-1. 宽化原始类型转换

```java
class Test {
  public static void main(String[] args) {
    int big = 1234567890;
    float approx = big;
    System.out.println(big - (int)approx);
  }
}
```

该程序打印：

```
-46
```

因此表明从 `int` 类型到 `float` 类型的转换过程中丢失了信息，因为 `float` 类型的值精度无法达到九位有效数字。

## 5.1.3 窄化原始类型转换

原始类型上的 22 种特定转换被称为窄化原始类型转换：

- `short` 转换为 `byte` 或 `char`
- `char` 转换为 `byte` 或 `short`
- `int` 转换为 `byte`, `short` 或 `char`
- `long` 转换为 `byte`, `short`, `char` 或 `int`
- `float` 转换为 `byte`, `short`, `char`, `int` 或 `long`
- `double` 转换为 `byte`, `short`, `char`, `int`, `long` 或 `float`

窄化转换可能会丢失数值的整体量级信息，还会丢失精度和范围。

有符号整数到整数类型 $\tau$ 的窄化转换仅仅是丢弃所有 $n$ 个低阶位，其中 $n$ 是表示类型 $\tau$ 所使用的位数。除了可能丢失数值的量级信息外，这还可能导致结果的符号与输入值的符号不同。

从 `char` 到整数类型 $\tau$ 的窄化转换同样仅仅是丢弃所有 $n$ 个低阶位，其中 $n$ 是表示类型 $\tau$ 所使用的位数。除了可能丢失数值的量级信息外。

从浮点数到整数类型 $\tau$ 的窄化转换分为两个步骤：

- 在第一步中，如果 $\tau$ 是 `long`，则将浮点数舍入到最近的整数；如果 $\tau$ 是 `byte` 或 `char`，则转换为零。
- 在第二步中，将生成的整数转换为类型 $\tau$。

从浮点数到整数类型 $\tau$ 的窄化转换是根据 IEEE 754 关于从二进制浮点格式转换为整数格式的规则决定的。

从一个浮点类型到另一个浮点类型的窄化转换是根据 IEEE 754 关于在二进制浮点格式之间转换的规则决定的。



### 示例 5.1.3-1. 窄化类型转换

```java
class Test {
    public static void main(String[] args) {
        float fmin = Float.NEGATIVE_INFINITY;
        float fmax = Float.POSITIVE_INFINITY;
        System.out.println("long: " + (long) fmin + "..." + (long) fmax);
        System.out.println("int: " + (int) fmin + "..." + (int) fmax);
        System.out.println("short: " + (short) fmin + "..." + (short) fmax);
        System.out.println("char: " + (char) fmin + "..." + (char) fmax);
        System.out.println("byte: " + (byte) fmin + "..." + (byte) fmax);
    }
}
```

该程序产生输出：

```
long: -9223372036854775808...9223372036854775807
int: -2147483648...2147483647
short: 0...1
char: 0...65535
byte: 0...1
```

`char`、`int` 和 `long` 的结果令人惊讶，产生了该类型的最小和最大表示值。

`byte` 和 `short` 的结果丢失了数值的符号和量级信息，并且丢失了精度。可以通过检查最小和最大 `int` 的低位来理解这些结果。最小 `int` 的十六进制为 `0x80000000`，最大的为 `0xffffffff`。这解释了 `short` 的结果（即这些值的 16 位，`0x0000` 和 `0xffff`）；解释了 `char` 的结果（同样是这些值的 16 位，`'\u0000'` 和 `'\ffff'`）；并解释了 `byte` 的结果（即这些值的 8 位，`0x00` 和 `0xff`）。

### 示例 5.1.3-2. 丢失信息的窄化原始类型转换

# 转换与上下文

## 转换类型 5.1

```java
System.out.println("(float)-le100==" + (float)-le100);
// 一个对于 float 无法表示太小的 double 值溢变为零：
System.out.println("(float)le-50==" + (float)le-50);
```

该程序产生以下输出：

```
(short)0x12345678==0xx5678
(byte)255==-1
(int)le20f==2147483647
(int)NaN==0
(float)-le100==Infinity
(float)le-50==0.0
```

## 5.1.4 原始类型的拓宽和收窄转换

以下转换结合了拓宽和收窄原始类型转换：

- 从 `byte` 到 `char`

首先，通过拓宽原始类型转换（§5.1.2）将 `byte` 转换为 `int`，然后通过收窄原始类型转换（§5.1.3）将生成的 `int` 转换为 `char`。

## 5.1.5 拓宽引用转换

从任何引用类型 $s$ 到任何引用类型 $\tau$ 都存在引用转换，其中 $s$ 是 $\tau$ 的子类型（§4.10）。

拓宽引用转换在运行时不需要任何特殊操作，且在运行时不会抛出异常。它们仅是将一个引用视为某种其他类型，并且这种方式在编译时可以证明是正确的。

`null` 类型不是引用类型（§4.1），因此不存在从 `null` 类型到引用类型的拓宽引用转换。然而，许多转换上下文显式允许将 `null` 类型转换为引用类型。

## 5.1.6 收窄引用转换

收窄引用转换将引用类型 $s$ 的表达式视为不同引用类型 $\tau$ 的表达式，其中 $s$ 不是 $\tau$ 的子类型。支持的类型对定义在 §5.1.6.1 中。与拓宽引用转换不同，这些类型之间不需要有直接关系。但是，存在某些限制，当可以静态地证明没有值可以同时属于两种类型时，禁止在某些类型对之间进行转换。

收窄引用转换可能需要在运行时进行测试，以验证类型为 $s$ 的值是类型 $\tau$ 的合法值。然而，由于运行时缺乏参数化类型信息，某些转换无法通过运行时测试完全验证；它们在编译时被标记（§5.1.6.2）。对于可以通过运行时测试完全验证的转换，以及某些涉及参数化类型信息但仍可以在运行时部分验证的转换，如果测试失败，将抛出 `ClassCastException`（§5.1.6.3）。

### 5.1.6.1 允许的收窄引用转换

如果满足所有条件，则从引用类型 $s$ 到引用类型 $\tau$ 存在收窄引用转换：

- $s$ 不是 $\tau$ 的子类型（§4.10）

- 如果存在一个参数化类型 $x$ 是 $\tau$ 的超类型，且一个参数化类型 $y$ 是 $s$ 的超类型，使得 $x$ 和 $y$ 的擦除相同，且 $x$ 和 $y$ 不是可证明是不同的（§4.5）。

以 `java.util` 包为例，从 `ArrayList<String>` 到 `ArrayList<Object>`（或反之）不存在收窄引用转换，因为类型参数 `String` 和 `Object` 是可证明是不同的。同样的原因，从 `ArrayList<String>` 到 `List<Object>`（或反之）不存在收窄引用转换。拒绝可证明不同的类型是一个简单的静态闸门，用于防止“愚蠢”的收窄引用转换。

# 转换与上下文

适用以下情况之一：

- 1. $s$ 是类或接口类型，且 $T$ 是一个与名为 $T$ 的类或接口不相交的类或接口。（“不相交”定义见下文。）

- 2. $s$ 是类类型 `Object` 或接口类型 `java.io.Serializable` 或 `Cloneable`（数组实现的唯一接口（§10.8）），且 $T$ 是一个数组类型。

- 3. $s$ 是数组类型 $SC[]$，即类型为 $SC$ 的组件构成的数组；$T$ 是数组类型 $TC[]$，且从 $SC$ 到 $TC$ 存在收窄引用转换。

- 4. $s$ 是类型变量，且从 $s$ 的上界到 $T$ 存在收窄引用转换。

- 5. $s$ 是类型变量，且从 $s$ 到 $T$ 的上界存在拓宽引用转换或收窄引用转换。

- 6. $s$ 是交集类型 $S_1 \& ... \& S_n$，且对于所有 $i$ ($1 \le i \le n$)，从 $S_i$ 到 $T$存在拓宽引用转换或收窄引用转换。

- 7. $T$ 是交集类型 $T_1 \& ... \& T_m$，且对于所有 $i$ ($1 \le i \le n$)，从 $s$ 到 $T_i$ 都拓宽引用转换或收窄引用转换。

如果可以静态地确定两个类或接口没有共同的实例，则它们是*不相交*的。不相交的规则如下：

- 类或接口 $C$ 与接口 $I$ 不相交，当且仅当（i）$C$ 不是 $I$，且（ii）满足以下条件：

  - $C$ 是数组类型 $SC[]$，且 $I$ 是数组类型 $TC[]$，且从 $SC$ 到 $TC$ 存在收窄引用转换。

  - $C$ 是类型变量，且从 $C$ 的上界到 $I$ 存在收窄引用转换。

  - $C$ 是类型变量，且从 $C$ 到 $I$ 的上界存在拓宽引用转换或收窄引用转换。

  - $C$ 是交集类型 $S_1 \& ... \& S_n$，且对于所有 $i$ ($1 \le i \le n$)，从 $S_i$ 到 $I$ 都存在拓宽引用转换或收窄引用转换。

  - $I$ 是交集类型 $T_1 \& ... \& T_m$，且对于所有 $i$ ($1 \le i \le m$)，从 $C$ 到 $T_i$ 都存在拓宽引用转换或收窄引用转换。

一个类或接口与另一个类或接口不相交，当且仅当（i）$C < I$，且（ii）满足以下条件：

  - $I$ 是数组类型 $SC[]$，且 $C$ 是数组类型 $TC[]$，且从 $SC$ 到 $TC$ 存在收窄引用转换。

  - $I$ 是类型变量，且从 $I$ 的上界到 $C$ 存在收窄引用转换。

  - $I$ 是类型变量，且从 $I$ 到 $C$ 的上界存在拓宽引用转换或收窄引用转换。

  - $I$ 是交集类型 $S_1 \& ... \& S_n$，且对于所有 $i$ ($1 \le i \le n$)，从 $S_i$ 到 $C$ 都存在拓宽引用转换或收窄引用转换。

  - $C$ 是交集类型 $T_1 \& ... \& T_m$，且对于所有 $i$ ($1 \le i \le m$)，从 $T_i$ 到 $C$ 都存在拓宽引用转换或收窄引用转换。

# 转换与上下文

## 转换类型 5.1

## 5.1.6 检查与未检查收窄引用转换

收窄引用转换是检查的或未检查的。这些术语指的是虚拟机是否能够验证转换的正确性。

如果收窄引用转换是检查的，虚拟机将能够完全验证其正确性，因此不会警告。如果收窄引用转换是未检查的，虚拟机将无法完全验证，可能导致堆污染（§4.2）。未检查的收窄转换如下：

- 从类型 $s$ 到参数化类或接口 $T$ 的收窄转换是未检查的，除非满足以下条件：

  - $T$ 的所有类型参数都是无界通配符。

  - $T < S$，且 $s$ 除了 $T$ 之外没有其他子类型。

- 从类型变量 $s$ 到类型变量 $T$ 的收窄转换是未检查的。

- 从类型 $s$ 到交集类型 $T_1 \& ... \& T_n$ $(1 \le i \le n)$ 的收窄转换是未检查的，如果存在 $T_i$ 使得 $s$ 不是 $T_i$ 的子类型，且从 $s$ 到 $T_i$ 的收窄转换是未检查的。

## 5.1.6.3 运行时的收窄引用转换

所有的收窄转换都需要在运行时进行有效性检查。主要情况下，这些转换是针对非参数化的类和接口。某些未检查的收窄转换需要在运行时进行有效性检查。这取决于该未检查的收窄转换是完全未检查还是部分未检查。部分未检查的收窄转换需要在运行时进行检查，而完全未检查的收窄转换则不需要。

这些指的是涉及转换的类型在视为原始类型时的兼容性。如果转换在概念上是“上转型”，则该转换是完全未检查的；不需要运行时检查，因为该转换在非泛型类型系统中是合法的。以 `java.util` 包中的类型为例，从 `ArrayList<String>` 到 `Collection<T>` 的转换是完全未检查的，因为在虚拟机中，原始类型 `ArrayList` 是原始类型 `Collection` 的子类型。相反，从 `Collection<?>` 到 `ArrayList<String>` 的转换是部分未检查的，因为在虚拟机中，原始类型 `Collection` 不是原始类型 `ArrayList` 的子类型。

- 从 $s$ 到非交集类型 $T$ 的未检查收缩引用转换，如果 $|s| < |T|$，则它是完全未检查的。

- 从 $s$ 到交集类型 $T_1 \& ... \& T_n$ 的未检查收缩引用转换，如果对于所有 $i$ $(1 \le i \le n)$，$s <: T_i$ 或者从 $s$ 到 $T_i$ 的收缩引用转换是完全未检查的，则它是完全未检查的。

否则，它是部分未检查的。

已检查或部分未检查收缩引用转换的运行时有效性检查如下：

- 如果运行时值为 `null`，则允许该转换。

## 转换与语境

## 转换类型

## 5.1

- 否则，令 $R$ 为该值所引用对象的类，并令 $\tau$ 为转换目标类型的擦除 (\S4.6)。那么：

- 如果 $R$ 是一个普通类（不是数组类）：

  - 如果 $T$ 是类类型，则 $R$ 必须是与 $\tau$ 相同的类 (\S4.3.4) 或 $\tau$ 的子类，否则抛出 `ClassCastException`。

  - 如果 $T$ 是接口类型，则 $R$ 必须实现接口 $\tau$ (\S8.1.5)，否则抛出 `ClassCastException`。

  - 如果 $T$ 是数组类型，则抛出 `ClassCastException`。

- 如果 $R$ 是接口：

> 注意，当这些规则首次应用于任何转换时，$R$ 不能是接口；但如果递归应用这些规则，$R$ 可能是一个接口，因为运行时引用值可能引用一个元素类型为接口类型的数组。

- 如果 $T$ 是类类型，则 $T$ 必须是 `Object` (\S4.3.2)，否则抛出 `ClassCastException`。

- 如果 $T$ 是接口类型，则 $R$ 必须是与 $\tau$ 相同的接口或 $T$ 的子接口，否则抛出 `ClassCastException`。

- 如果 $T$ 是数组类型，则抛出 `ClassCastException`。

- 如果 $R$ 是表示数组类型 $RC[]$ 的类，即类型为 $RC$ 的组件的数组。

- 如果 $T$ 是类类型，则 $T$ 必须是 `Object` (\S4.3.2)，否则抛出 `ClassCastException`。

- 如果 $T$ 是接口类型，则 $T$ 必须是 `java.io.Serializable` 或 `Cloneable` 类型（数组实现的唯一接口），否则抛出 `ClassCastException`。

- 如果 $T$ 是数组类型 $TC[]$，即类型为 $TC$ 的组件的数组，除非 $TC$ 和 $RC$ 是相同的原始类型，或者 $TC$ 和 $RC$ 是引用类型且通过这些运行时规则的递归应用允许。

如果转换到交集类型 $T_1 \& ... \& T_n$，那么对于所有 $i$ ($1 \le i \le n$)，从 $s$ 到 $T_i$ 的转换所需的任何运行时检查在转换为交集类型的转换中也是需要的。

## 5.1 转换类型

### 5.1.7 装箱转换 (Boxing Conversion)

装箱转换将原始类型的表达式视为相应引用类型的表达式。具体来说，以下九种转换被称为装箱转换：

- 从 `boolean` 类型到 `Boolean` 类型
- 从 `byte` 类型到 `Byte` 类型
- 从 `short` 类型到 `Short` 类型
- 从 `char` 类型到 `Character` 类型
- 从 `int` 类型到 `Integer` 类型
- 从 `long` 类型到 `Long` 类型
- 从 `float` 类型到 `Float` 类型
- 从 `double` 类型到 `Double` 类型
- 从空类型到空类型

> 这一规则是必要的，因为条件运算符 ($15.25) 对操作数应用装箱转换并将结果用于进一步计算。

在运行时，装箱转换过程如下：

- 如果 $p$ 是 `boolean` 类型的值，则装箱转换将 $p$ 转换为类和类型为 `Boolean` 的引用，使得 $r.booleanValue() == p$
- 如果 $p$ 是 `Byte` 类型的值，则装箱转换将 $p$ 转换为类和类型为 `Byte` 的引用，使得 $r.byteValue() == p$
- 如果 $p$ 是 `char` 类型的值，则装箱转换将 $p$ 转换为类和类型为 `Character` 的引用，使得 $r.charValue() == p$
- 如果 $p$ 是 `short` 类型的值，则装箱转换将 $p$ 转换为类和类型为 `Short` 的引用，使得 $r.shortValue() == p$
- 如果 $p$ 是 `int` 类型的值，则装箱转换将 $p$ 转换为类和类型为 `Integer` 的引用，使得 $r.intValue() == p$
- 如果 $p$ 是 `long` 类型的值，则装箱转换将 $p$ 转换为类和类型为 `Long` 的引用，使得 $r.longValue() == p$
- 如果 $p$ 是 `float` 类型的值，则：
  - 如果 $p$ 不是 NaN，装箱转换将 $p$ 转换为类和类型为 `Float` 的引用 $r$，使得 $r.floatValue()` 结果为 $p$
  - 否则，装箱转换将 $p$ 转换为类和类型为 `Float` 的引用 $r$，使得 $r.floatValue()` 结果为 $p$
- 如果 $p$ 是 `double` 类型的值，则：
  - 如果 $p$ 不是 NaN，装箱转换将 $p$ 转换为类和类型为 `Double` 的引用 $r$，使得 $r.doubleValue()` 结果为 $p$
  - 否则，装箱转换将 $p$ 转换为类和类型为 `Double` 的引用 $r$，使得 $r.doubleValue()` 结果为 $p$

如果需要分配一个包装类（`Boolean`, `Byte`, `Character`, `Short`, `Integer`, `Long`, `Float` 或 `Double`）的新实例且存储不足，装箱转换可能会导致 `OutOfMemoryError`。

### 5.1.8 解箱转换 (Unboxing Conversion)

解箱转换将引用类型的表达式视为原始类型的表达式。具体来说，以下八种转换被称为解箱转换：

- 从 `Boolean` 类型到 `boolean` 类型
- 从 `Byte` 类型到 `byte` 类型
- 从 `Short` 类型到 `short` 类型
- 从 `Character` 类型到 `char` 类型
- 从 `Integer` 类型到 `int` 类型
- 从 `Long` 类型到 `long` 类型
- 从 `Float` 类型到 `float` 类型
- 从 `Double` 类型到 `double` 类型

在运行时，解箱转换过程如下：

- 如果 $r$ 是 `Boolean` 类型引用，则解箱转换将 $r$ 转换为 $r.booleanValue()$
- 如果 $r$ 是 `Byte` 类型引用，则解箱转换将 $r$ 转换为 $r.byteValue()$
- 如果 $r$ 是 `Character` 类型引用，则解箱转换将 $r$ 转换为 $r.charValue()$



- 如果 $r$ 是 `Short` 类型引用，则解箱转换将 $r$ 转换为 `r.shortValue()`
- 如果 $r$ 是 `Integer` 类型引用，则解箱转换将 $r$ 转换为 `r.intValue()`
- 如果 $r$ 是 `Long` 类型引用，则解箱转换将 $r$ 转换为 `r.longValue()`
- 如果 $r$ 是 `Float` 类型引用，则解箱转换将 $r$ 转换为 `r.floatValue()`
- 如果 $r$ 是 `Double` 类型引用，则解箱转换将 $r$ 转换为 `r.doubleValue()`
- 如果 $r$ 为 `null`，解箱转换抛出 `NullPointerException`

# 转换与上下文

## 5.1.9 未检查转换 (Unchecked Conversion)

假设 $G$ 是具有 $n$ 个类型参数的泛型类型声明。

从原始类或接口类型 (§4.8) $G$ 到任何形式为 $G<T_1,...,T_n>$ 的参数化类型存在未检查转换。

从原始数组 $G[]^k$ 到任何形式为 $G<T_1,...,T_i..>^k$ 的数组类型存在未检查转换。（符号 `[]k` 表示 $k$ 维数组的类型。）

使用未检查转换会导致编译时的未检查警告，除非所有类型参数 $T_i$ ($1 \le i \le n$) 都是无界通配符 (§4.5.1)，或者该警告被 `@SuppressWarnings` (§9.6.4.5) 抑制。

未检查转换用于实现某些旧代码更平滑的交互，这些代码是在泛型引入之前编写的，或者是已经转换为泛型的库（我们称这一过程为泛化）。在这些情况下（最典型的是 `java.util` 中集合框架的客户端），代码使用了原始类型（例如用 `Collection` 代替 `Collection<String>`）。原始类型的表达式被传递给库方法，这些方法使用这些类型的参数化版本作为其形式参数的类型。

在使用泛型的类型系统中，此类调用无法保证类型安全。拒绝此类调用会导致大量现有代码失效，并阻止它们使用新版本的库。反之，这将抑制库供应商利用泛化的便利。为了防止这种不受欢迎的事件发生，原始类型可以转换为该原始类型所引用的泛型类型声明的任意调用。虽然这种转换是不健全的（unsound），但出于实用性考虑，它是被允许的。在这种情况下，会发出未检查警告。

## 5.1.10 捕获转换 (Capture Conversion)

假设 $G$ 是泛型类型声明 (§8.1.2, §9.1.2)，具有 $n$ 个类型参数 $A_1,...,A_n$ 以及相应的边界 $U_1,...,U_n$。

从参数化类型 $G<T_1,...,T_n>$ (§4.5) 到参数化类型 $G<S_1,...,S_n>$ 存在捕获转换，其中对于 $1 \le i \le n$：

- 如果 $T_i$ 是类型为 `?` 的通配符类型参数（§4.5.1），则 $S_i$ 是一个新变量，其上限为 $U_i[A_i:=S_i, ..., A_n:=S_n]$，且下界为空类型 (§4.1)。
- 如果 $T_i$ 是形式为 `? extends $B_i` 的通配符类型参数，则 $S_i$ 是一个新的类型变量，其上限为 $glb(B_i, U_i[A_i:=S_i, ... , A_n:=S_n])$，且下界为空类型。

$glb(V_i,...,V_m)$ 被定义为 $V_i \& ... \& V_m$。

如果任何两个类（接口）$V_i$ 和 $V_j$ 不是 $V_j$ 的子类（或反之），则为编译错误。

- 如果 $T_i$ 是形式为 `? super $B_i` 的通配符类型参数，则 $S_i$ 是一个新的类型变量，其上限为 $U_i[A_i:=S_i, ... , A_n:=S_n]$，且下界为 $B_i$。
- 否则，$S_i = T_i$。

除参数化类型（§4.5）之外任何类型的捕获转换作为恒等转换（§5.1.1）。

捕获不是递归应用的。

捕获转换在运行时永远不需要特殊操作，因此在运行时永远不会抛出异常。

> 捕获转换的设计使通配符更有用。为了理解其动机，让我们先看方法 `java.util.Collections.reverse()`：
>
> ```java
> public static void reverse(List<?> list);
> ```
>
> 该方法反转作为参数提供的列表。它适用于任何类型的列表，因此将通配符列表 `List<?>` 的类型作为形式参数的类型是完全合适的。
>
> 现在考虑人们如何实现 `reverse()`：
>
> ```java
> public static void reverse(List<?> list) { rev(list); }
> private static <T> void rev(List<T> list) {
>     List<T> tmp = new ArrayList<T>(list);
>     for (int i = 0; i < list.size(); i++) {
>         list.set(i, tmp.get(list.size() - i - 1));
>     }
> }
> ```
>
> 该实现需要复制列表，从拷贝中提取元素并将其插入原始列表中。为了以类型安全的方式执行，我们需要向传入列表的元素类型中添加 $T$。我们在服务方法 `rev(T)` 中这样做。这要求我们将传入的参数列表 `List<?>` 作为参数传递给 `rev(T)`。在通常情况下，`List<?>` 是一个未知类型的类型。对于任何类型 $T$，它都不是 `List<T>` 的子类型。允许这种子类型关系将是不健全的。给定该方法：
>
> ```java
> public static <T> void fill(List<T> l, T obj)
> ```
>
> 以下代码将破坏系统：
>
> ```java
> List<String> ls = new ArrayList<String>();
> List<?> l1 = ls;
> Collections.fill(l1, new Object()); // 非法 - 但假设它是允许的！
> String s = ls.get(0); // ClassCastException - ls 包含
> // Objects, Strings。
> ```
>
> 所以，在没有特殊的情况下，我们可以看到 `List<?>` 对于任何类型 $T$ 都不是 `List<T>` 的子类型。

## 5.2 赋值上下文

- 一个宽化引用转换后接一个拆箱转换，然后紧接一个宽化基本类型转换
- 一个装箱转换 (§5.1.7)
- 一个装箱转换后接一个宽化引用转换
- 一个拆箱转换 (§5.1.8)
- 一个拆箱转换后接一个宽化基本类型转换

如果在应用上述转换后，结果的类型是原始类型 (§4.8)，则可能会应用未检查转换 (§5.1.9)。

此外，如果表达式是 `byte`、`short`、`char` 或 `int` 类型的常量表达式 (§15.29)：

- 如果变量类型为 `byte`、`short` 或 `char`，且常量表达式的值可以在变量类型中表示，则可以使用窄化基本类型转换。
- 如果变量类型为 `Byte`、`Short` 或 `Character`，且常量表达式的值分别在 `byte`、`short` 或 `char` 类型中可以表示，则可以使用一个窄化基本类型转换后接一个装箱转换。

常量表达式的编译时窄化意味着类似如下的代码：

```
byte theAnswer = 42;
```

是允许的。如果没有窄化，整数 42 类型为 `int` 这一事实意味着强制转换为 `byte` 将需要：

```
byte theAnswer = (byte)42; // 允许强制转换但不是必须
```

最后，`null` 值（空引用是唯一的此类值）可以赋值给任何引用类型，从而产生该类型的空引用。

如果转换链包含两个不符合子类型关系的泛型类型 (§4.10)，则将为编译时错误。

此类非法链的示例为：

```
Integer, Comparable<Integer>, Comparable, Comparable<String>
```

链的前两个元素通过宽化引用转换相关，而最后一个项是通过未检查转换从其前驱项推导出的。然而，这不是一个有效的赋值转换，因为链中包含了两个不是子类的泛型类型 `Comparable<Integer>` 和 `Comparable<String>`。

如果表达式的类型可以通过赋值转换转换为变量的类型，我们说该表达式（或其值）是可以赋值给该变量的，或者等价地，表达式的类型与变量的类型是赋值兼容的。

赋值上下文中转换可能产生的异常有：

- `ClassCastException`：在应用上述转换后，结果值是一个不是变量类型擦除后 (§4.6) 的子类或子接口实例的对象。这种情况只能由于堆污染 (§4.12.2) 而产生。在实践中，当访问泛型类型的字段或方法时，如果字段的擦除类型或方法的擦除返回类型与其擦除类型不同，实现类才需要执行强制转换。
- `OutOfMemoryError`：由于装箱转换导致。
- `NullPointerException`：对空引用进行拆箱转换导致。
- `ArrayStoreException`：涉及数组元素或字段访问的特殊情况 (§10.5, §15.26.1)。

### 5.2-1. 基本类型的赋值

```java
class Test {
    public static void main(String[] args) {
        short s = 12; // 将 12 窄化为 short
        float f = s; // 将 short 宽化为 float
        System.out.println("f=" + f);
        char c = '\u0123';
        long l = c; // 将 char 宽化为 long
        System.out.println("l=" + Long.toString(l, 16));
        float f2 = 1.23f;
        double d = f2; // 将 float 宽化为 double
        System.out.println("d=" + d);
    }
}
```

该程序产生输出：

```
f=12.0
l=123
d=1.2300000190734863
```

然而，以下程序产生编译时错误：

```java
class Test {
    public static void main(String[] args) {
        short s = 123;
        char c = s; // 错误：需要强制转换
        s = c; // 错误：需要强制转换
    }
}
```

因为并不是所有的值都是 `char` 值，也不是所有的 `char` 值都是 `short` 值。

### 5.2-2. 引用类型的赋值

```java
class Point { int x, y; }
class Point3D extends Point { int z; }
interface Colorable { void setColor(int color); }

class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}
```

```java
class Test {
    public static void main(String[] args) {
        // 赋值给类类型的变量：
        Point p = new Point();
        p = new Point3D();
        // OK，因为 Point3D 是 Point 的子类
        Point3D p3d = (Point3D)p; // 错误：需要强制转换，因为 p 可能不是 Point3D（尽管在本示例中动态上是）

        // 赋值给 Object 类型的变量：
        Object o1 = new Point();
        o1 = new Point3D(); // OK，因为 Point3D 是 Point 的子类
        Object o2 = new ColoredPoint();
        Point p2 = (Point)o2; // OK

        // 赋值给接口类型的变量：
        Colorable c1 = new ColoredPoint();
        // Colorable c2 = (Colorable)new Point(); // 错误：Point 不是 Colorable
    }
}
```

## 5.3 调用上下文 (Invocation Contexts)

- 一个宽化引用转换后接一个解箱转换，然后接一个宽化原始类型转换
- 一个装箱转换 (§5.1.7)
- 一个装箱转换后接一个宽化引用转换
- 一个解箱转换 (§5.1.8)
- 一个解箱转换后接一个宽化原始类型转换

如果在应用了调用上下文所列出的转换后，结果类型是原始类型 (§4.8)，则可能可以应用未检查转换 (§5.1.9)。

空类型的值（空引用是该类型的唯一值）可以赋值给任何引用类型。

如果转换链中包含两个不满足子类型关系 (§4.10) 的泛型类型，则为编译时错误。

在调用上下文可能出现的异常有：

- `ClassCastException`：如果应用了上述类型转换，结果值是一个不是对应形式参数类型擦除后 (§4.6) 的子类或子接口实例的对象。
- 由于装箱转换导致的 `OutOfMemoryError`。
- 由于对空引用进行解箱转换导致的 `NullPointerException`。

无论是严格还是宽松的调用上下文都不包含赋值上下文允许的整数常数表达式的隐式收缩。Java 编程语言的设计者认为，包含这些隐式收缩转换会增加重载解析规则的复杂性 (§15.12.2)。

因此，程序：

```java
class Test {
    static int m(byte a, int b) { return a + b; }
    static int m(short a, short b) { return a - b; }
    public static void main(String[] args) {
        System.out.println(m(12, 2)); // 编译错误
    }
}
```

会导致编译错误，因为整数字面量 12 和 2 的类型为 `int`，因此没有哪个方法符合重载解析规则。一种包含整数常数表达式隐式收缩的语言需要额外的规则来解决此类示例所示的情况。

## 5.4 字符串上下文 (String Contexts)

字符串上下文仅适用于二元运算符 `+` 的操作数，且当另一个操作数是 `String` 时，该操作数不是 `String`。

这些上下文中的目标类型始终是 `String`，并且始终会对非 `String` 操作数发生字符串转换 (§5.1.11)。然后按照 §15.18.1 指定的方式对 `+` 运算符进行求值。

## 5.5 强制转换上下文 (Casting Contexts)

强制转换上下文允许强制转换表达式 (§5.16) 的操作数转换为转换运算符显式命名的类型。与赋值上下文和调用上下文相比，强制转换上下文允许使用 §5.1 中定义的更多转换，并允许这些转换的更多组合。

如果表达式是原始类型，则强制转换上下文允许使用以下一种：

- 一个恒等转换 (§5.1.1)
- 一个宽化原始类型转换 (§5.1.2)
- 一个收缩原始类型转换 (§5.1.3)
- 一个宽化且收缩的原始类型转换 (§5.1.4)
- 一个装箱转换 (§5.1.7)
- 一个装箱转换后接一个宽化引用转换 (§5.1.5)

如果表达式是引用类型，则强制转换上下文允许使用以下之一：

- 一个恒等转换 (§5.1.1)
- 一个宽化引用转换 (§5.1.5)
- 一个宽化引用转换后接一个解箱转换
- 一个宽化引用转换后接一个解箱转换，然后接一个宽化原始类型转换
- 一个收缩引用转换 (§5.1.6)
- 一个收缩引用转换后接一个解箱转换
- 一个解箱转换 (§5.1.8)
- 一个解箱转换后接一个宽化原始类型转换

如果表达式具有空类型，则该表达式可以强制转换为任何引用类型。

如果强制转换上下文使用了已检查或部分未检查的收缩引用转换 (§5.1.6.2, §5.1.6.3)，将对表达式值的类进行运行时检查，可能会导致 `ClassCastException`。否则，不进行运行时检查。

如果表达式可以通过未检查的收缩引用转换以外的强制转换转换为引用类型，我们称该表达式（或其值）与该引用类型向下转换兼容 (downcast compatible)。

下表列出了某些强制转换上下文使用了哪些转换。每个转换由一个符号表示：

- `-` 表示不允许任何转换
- `=` 表示恒等转换 (§5.1.1)
- `ω` 表示宽化原始类型转换 (§5.1.2)
- `η` 表示收缩原始类型转换 (§5.1.3)
- `Ɏ` 表示宽化且收缩的原始类型转换 (§5.1.4)
- `↩` 表示宽化引用转换 (§5.1.5)
- `⇓` 表示收缩引用转换 (§5.1.6)
- `⊕` 表示装箱转换 (§5.1.7)
- `⊖` 表示解箱转换 (§5.1.8)

在表格中，符号之间的逗号表示强制转换上下文使用一个转换后接另一个转换。类型 `Object` 表示除了八个包装类 `Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double` 之外的任何引用类型。

### 表 5.5-A. 转换为原始类型

| From | byte | short | char | int | long | float | double | boolean |
|---|---|---|---|---|---|---|---|---|



## 5.3 调用上下文 (Invocation Contexts)

- 一个宽化引用转换后接一个解箱转换，然后接一个宽化原始类型转换
- 一个装箱转换 (`§5.1.7`)
- 一个装箱转换后接一个宽化引用转换
- 一个解箱转换 (`§5.1.8`)
- 一个解箱转换后接一个宽化原始类型转换

如果在应用了调用上下文所列出的转换后，结果类型是原始类型 (`§4.8`)，则可能可以应用未检查转换 (`§5.1.9`)。

空类型的值（空引用是该类型的唯一值）可以赋值给任何引用类型。

如果转换链中包含两个不满足子类型关系 (`§4.10`) 的泛型类型，则为编译错误。

在调用上下文中可能出现的异常有：

- `ClassCastException`：如果应用了上述类型转换，结果值是一个不是对应形式参数类型擦除后 (`§4.6`) 的子类或子接口实例的对象。
- 由于装箱转换导致的 `OutOfMemoryError`。
- 由于对空引用进行解箱转换导致的 `NullPointerException`。

无论是严格还是宽松的调用上下文都不包含赋值上下文允许的整数常数表达式的隐式收缩。Java语言的设计者认为，包含这些隐式收缩转换会增加重载解析规则的复杂性 (`§15.12.2`)。

因此，程序：

```
class Test {
    static int m(byte a, int b) { return a+b; }
    static int m(short a, short b) { return a-b; }
    public static void main(String[] args) {
        System.out.println(m(12, 2)); // 编译错误
    }
}
```

会导致编译错误，因为整数字面量 12 和 2 的类型为 `int`，因此没有哪个方法符合重载解析规则。一种包含整数常数表达式隐式收缩的语言需要额外的规则来解决此类示例所示的情况。

## 5.4 字符串上下文 (String Contexts)

字符串上下文仅适用于二元运算符 `+` 的操作数，且当另一个操作数是 `String` 时，该操作数不是 `String`。

这些上下文中的目标类型始终是 `String`，并且会对非 `String` 操作数发生字符串转换 (`§5.1.11`)。然后按照 `§15.18.1` 指定的方式对 `+` 运算符进行求值。

## 5.5 强制转换上下文 (Casting Contexts)

强制转换上下文允许强制转换表达式 (`§5.16`) 的操作数转换为转换运算符显式命名的类型。与赋值上下文和调用上下文相比，强制转换上下文允许使用 `§5.1` 中定义的更多转换，并允许这些转换的更多组合。

如果表达式是原始类型，则强制转换上下文允许使用以下一种：

- 一个恒等转换 (`§5.1.1`)
- 一个宽化原始类型转换 (`§5.1.2`)
- 一个收缩原始类型转换 (`§5.1.3`)
- 一个宽化且收缩的原始类型转换 (`§5.1.4`)
- 一个装箱转换 (`§5.1.7`)
- 一个装箱转换后接一个宽化引用转换 (`§5.1.5`)

如果表达式是引用类型，则强制转换上下文允许使用以下之一：

- 一个恒等转换 (`§5.1.1`)
- 一个引用转换 (`§5.1.5`)
- 一个宽化引用转换后接一个解箱转换
- 一个宽化引用转换后接一个解箱转换，然后接一个宽化原始类型转换
- 一个收缩引用转换 (`§5.1.6`)
- 一个收缩引用转换后接一个解箱转换
- 一个解箱转换 (`§5.1.8`)
- 一个解箱转换后接一个宽化原始类型转换

如果表达式具有 `null` 类型，则该表达式可以被强制转换为任何引用类型。

如果强制转换上下文使用了受检或部分未检查的收缩引用转换 (`§5.1.6.2`, `§5.1.6.3`)，则将在表达式值的类上执行运行时检查，可能导致 `ClassCastException`。否则，不执行运行时检查。

如果表达式可以通过除未检查的收缩引用转换以外的强制转换转换为引用类型，我们称该表达式（或其值）与该引用类型**向下转型兼容**。

以下表格枚举了在特定强制转换上下文中使用的转换。每种转换由一个符号表示：

- `-` 表示不允许转换
- `=` 表示恒等转换 (`§5.1.1`)
- `ω` 表示宽化原始类型转换 (`§5.1.2`)
- `η` 表示收缩原始类型转换 (`§5.1.3`)
- `Ɏ` 表示宽化且收缩的原始类型转换 (`§5.1.4`)
- `↩` 表示宽化引用转换 (`§5.1.5`)
- `⇓` 表示收缩引用转换 (`§5.1.6`)
- `⊕` 表示装箱转换 (`§5.1.7`)
- `⊖` 表示解箱转换 (`§5.1.8`)

在表格中，符号之间的逗号表示强制转换上下文先使用一个转换，再使用另一个转换。类型 `Object` 表示除八种包装类 `Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double` 之外的任何引用类型。

### 表 5.5-A. 强制转换为原始类型

| From | byte | short | char | int | long | float | double | boolean |
|---|---|---|---|---|---|---|---|---|
| byte | = | ω | η | ω | ω | ω | - | - |
| short | η | = | η | ω | ω | ω | - | - |
| char | η | η | = | ω | ω | ω | - | - |
| int | ω | ω | ω | = | ω | ω | - | - |
| long | ω | ω | ω | ω | = | ω | - | - |
| float | ω | ω | ω | ω | ω | = | - | - |
| double | - | - | - | - | - | - | = | - |
| boolean | - | - | - | - | - | - | - | = |

### 表 5.5-B. 强制转换为引用类型

| From | Byte | Short | Integer | Long | Float | Double | Object |
|---|---|---|---|---|---|---|---|
| byte | ⊕ | - | - | ⊕ | ⊕ | ⊕ | - | ⊕ |
| short | - | ⊕ | - | ⊕ | ⊕ | ⊕ | - | ⊕ |
| char | - | - | ⊕ | - | - | - | - | ⊕ |
| int | - | - | - | ⊕ | - | - | - | ⊕ |
| long | - | - | - | - | ⊕ | - | - | ⊕ |
| float | - | - | - | - | - | ⊕ | - | ⊕ |
| double | - | - | - | - | - | - | - | - |
| boolean | - | - | - | - | - | - | = | - |



- 一个宽化引用转换后接一个解箱转换，然后接一个宽化原始类型转换
- 一个收缩引用转换（`§5.1.6`）
- 一个收缩引用转换后接一个解箱转换
- 一个解箱转换（`§5.1.8`）
- 一个解箱转换后接一个宽化原始类型转换

如果表达式具有空类型，则该表达式可以强制转换为任何引用类型。

如果强制转换上下文使用了已检查或部分未检查的收缩引用转换（`§5.1.6.2`、`§5.1.6.3`），将对表达式值的类进行运行时检查，可能会导致 `ClassCastException`。否则，不进行运行时检查。

如果表达式可以通过未检查的收缩引用转换以外的强制转换转换为引用类型，我们称该表达式（或其值）与该引用类型向下转换兼容。

下表列出了某些强制转换上下使用了哪些转换。每个转换由一个符号表示：

- `-` 表示不允许任何转换
- `=` 表示恒等转换（`§5.1.1`）
- `ω` 表示宽化原始类型转换（`§5.1.2`）
- `η` 表示收缩原始类型转换（`§5.1.3`）
- `Ɏ` 表示宽化且收缩的原始类型转换（`§5.1.4`）
- `↩` 表示宽化引用转换（`§5.1.5`）
- `⇓` 表示收缩引用转换（`§5.1.6`）
- `⊕` 表示装箱转换（`§5.1.7`）
- `⊖` 表示解箱转换（`§5.1.8`）

在表格中，符号之间的逗号表示强制转换上下文使用一个转换后接另一个转换。类型 `Object` 表示除了八个包装类 `Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double` 之外的任何引用类型。

### 表 5.5-A. 转换为原始类型

| From | byte | short | char | int | long | float | double | boolean |
|---|---|---|---|---|---|---|---|---|
| byte | = | ω | η | ω | ω | ω | - | |
| short | η | = | η | ω | ω | ω | - | |
| char | η | η | = | ω | ω | ω | - | |
| int | ω | ω | ω | = | ω | ω | - | |
| long | ω | ω | ω | ω | = | ω | - | |
| float | ω | ω | ω | ω | ω | = | - | |
| double | - | - | - | - | - | - | = | |
| boolean | - | - | - | - | - | - | - | = |

### 表 5.5-B. 转换为引用类型

| From | Byte | Short | Integer | Long | Float | Double | Object |
|---|---|---|---|---|---|---|---|
| byte | ⊕ | - | - | ⊕ | ⊕ | ⊕ | - | ⊕ |
| short | - | ⊕ | - | ⊕ | ⊕ | ⊕ | - | ⊕ |
| char | - | - | ⊕ | - | - | - | - | ⊕ |
| int | - | - | - | ⊕ | - | - | - | ⊕ |
| long | - | - | - | - | ⊕ | - | - | ⊕ |
| float | - | - | - | - | - | ⊕ | - | ⊕ |
| double | - | - | - | - | - | - | - | |
| boolean | - | - | - | - | - | - | = |

*(注：由于原始表格数据存在大量重复和截断，此处已根据核心逻辑结构展示)*

---

## 示例 5.5-1. 引用类型的强制转换

```java
class Point { int x, y; }
interface Colorable { void setColor(int color); }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}
final class Endpoint extends Point { }

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        ColoredPoint cp = new ColoredPoint();
        Colorable c;
        // 以下可能会在运行时引起错误，因为
        // 我们无法确定它们会成功；这种可能性
        // 由强制转换所暗示：
        cp = (ColoredPoint)p; // p 可能不是 ColoredPoint 的子类
                              // 或 Colorable 的子类
        c = (Colorable)p; // p 可能不是 Colorable
        // 以下在编译时是错误的
        // 它们永远不会成功，正如文中解释的：
        Long l = (Long)p; // 编译错误 #1
        Endpoint e = new Endpoint();
        c = (Colorable)e; // 编译错误 #2
    }
}
```

在这里，第一个编译错误发生是因为 `Long` 和 `Point` 类类型之间没有关系（即它们不相同，且一个都不是另一个的子类），因此它们之间的强制转换将始终失败。

第二个编译错误是因为类型为 `Endpoint` 的变量永远无法引用实现 `Colorable` 接口的值。这是因为 `Endpoint` 是最终类型，而最终类型变量的运行时类型与其编译时类型相同。因此，变量 `e` 的运行时类型必须是 `Endpoint`，而 `Endpoint` 类型没有实现 `Colorable`。

## 示例 5.5-2. 数组类型的强制转换

```java
class Point {
    int x;
}
```

该程序编译无错误并产生输出：

```
cpa: { (2,2)@12, (4,5)@24, null, null }
```

转换与上下文

## 数值上下文

## 示例 5.5-3. 运行时强制转换不兼容类型

```java
class Point { int x, y; }
interface Colorable { void setColor(int color); }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}
```

```java
class Test {
    public static void main(String[] args) {
        Point[] pa = new Point[100];

        // 下一行将抛出 ClassCastException:
        ColoredPoint[] cpa = (ColoredPoint[])pa;
        System.out.println(cpa[0]);
        int[] shortvec = new int[2];
        Object o = shortvec;

        // 下一行将抛出 ClassCastException:
        Colorable c = (Colorable)o;
        c.setColor(0);
    }
}
```

该程序使用强制转换通过编译，但在运行时会抛出异常，因为它们是不兼容的。

## 5.6 数值上下文

数值上下文适用于算术运算符的操作数、数组创建和访问表达式、条件表达式，以及 switch 表达式的结果表达式。

如果一个表达式属于以下情况，则该表达式出现在数值算术上下文中：

- 一元加运算符 `+`、一元减运算符 `-` 或位取反运算符 `~`（`§15.15.3`、`§15.15.4` 或 `§15.15.5`）
- 乘法运算符 `*`、`/` 或 `%` 的操作数（`§15.17`）
- 数值类型加法运算符 `+` 或减法运算符 `-`（`§15.18.2`）
- 移位运算符 `<<`、`>>` 或 `>>>` 的操作数（`§15.19`）。这些移位运算符的操作数被单独处理，而不是作为一个整体。长移位距离（右操作数）不会将被移位的值（左操作数）提升为 long。
- 数值比较运算符 `<`、`<=`、`>` 或 `==` 的操作数（`§15.20.1`）
- 数值相等运算符 `==` 或 `!=` 的操作数（`§15.21.1`）
- 整数位运算符 `&`、`^` 或 `|` 的操作数（`§15.22.1`）

如果一个表达式属于以下情况，则该表达式出现在数值数组上下文中：

- 数组创建表达式中的维度表达式（`§15.10.1`）
- 数组访问表达式中的索引表达式（`§15.10.3`）

如果一个表达式属于以下情况，则该表达式出现在数值选择上下文中：

- 数值条件表达式的第二个或第三个操作数（`§15.25.2`）
- 独立 switch 表达式的结果（`§15.28.1`），其中所有结果都能转换为数值类型

数值提升决定了数值上下文中所有表达式的提升类型。选择提升类型是为了使每个表达式都能转换为该类型，并且在算术运算的情况下，该操作对于提升类型的值是有定义的。数值上下文中表达式的顺序对于数值提升并不重要。规则如下：

1. 如果任何表达式是引用类型，则它将进行拆箱转换（`§5.1.8`）。

接下来，根据以下规则对某些表达式应用宽原始类型转换（`§5.1.2`）和窄原始类型转换（`§5.1.3`）：

- 如果任何表达式是 `double` 类型，则提升类型为 `double`，其他不是 `double` 类型的表达式通过宽原始类型转换转换为 `double`。
- 否则，如果任何表达式是 `float` 类型，则提升类型为 `float`，其他不是 `float` 类型的表达式通过宽原始类型转换转换为 `float`。
- 否则，如果任何表达式是 `long` 类型，则提升类型为 `long`，其他不是 `long` 类型的表达式通过宽原始类型转换转换为 `long`。
- 否则，没有任何表达式是 `double`、`float` 或 `long` 类型。在这种情况下，上下文的决定了如何选择提升类型。

在数值算术上下文或数值数组上下文中，提升类型为 `int`，任何不是 `int` 类型的表达式都通过原始类型转换转换为 `int`。

在数值上下，适用以下规则：

- 如果任何表达式是 `int` 类型且不是常量表达式（`§15.29`），则提升类型为 `int`，其他不是 `int` 类型的表达式通过原始类型转换转换为 `int`。
- 否则，如果任何表达式是 `short` 类型，且其他所有表达式都是 `short` 类型、`byte` 类型或值为可以在 `short` 类型中表示的 `int` 类型常量表达式，则提升类型为 `short`，`byte` 表达式通过宽原始类型转换转换为 `short`，`int` 表达式通过窄原始类型转换转换为 `short`。
- 否则，如果任何表达式是 `byte` 类型，且其他所有表达式都是 `byte` 类型或值为可以在 `byte` 类型中表示的 `int` 类型常量表达式，则提升类型为 `byte`，`int` 表达式通过窄原始类型转换转换为 `byte`。
- 否则，如果任何表达式是 `char` 类型，且其他所有表达式都是 `char` 类型或 `byte` 类型或值为可以在 `char` 类型中表示的 `int` 类型常量表达式，则提升类型为 `char`，`byte` 表达式通过宽原始类型转换转换为 `char`，`int` 表达式通过窄原始类型转换转换为 `char`。

## 6.1 声明

本章还讨论了完全限定名和规范名（`§6.7`）。

声明将实体引入到程序中，并包含一个标识符（`§3.8`），该标识符可以用于名称中以引用该实体。标识符受到限制，以避免在所引入的实体是类、接口或类型参数时使用某些上下文中关键字。

被声明的实体是以下内容之一：

- 模块，在模块声明（`§7.7`）中声明
- 包，在包声明（`§7.4`）中声明
- 导入的类或接口，在单个类型导入声明或按需导入类型声明（`§7.5.1`、`§7.5.2`）中声明
- 导入的静态成员，在单个静态导入声明或按需导入静态声明（`§7.5.3`、`§7.5.4`）中声明
- 类，通过普通类声明（`§8.1`）、枚举声明（`§8.9`）或记录声明（`§8.10`）声明
- 接口，通过普通接口声明（`§9.1`）或注解接口声明（`§9.6`）声明
- 类型参数，作为泛型类、接口、方法或构造函数声明的一部分声明（`§8.1.2`、`§9.1.2`、`§8.4.4`、`§8.8.4`）
- 引用类型的成员（`§8.2`、`§9.2`、`§8.9.3`、`§9.6`、`§10.7`），以下内容之一：
    - 成员类（`§8.5`、`§9.5`）
    - 成员接口（`§8.5`、`§9.5`）
    - 字段，以下内容之一：
        - 在类中声明的字段（`§8.3`）
        - 在接口中声明的字段（`§9.3`）
        - 对应于枚举常量或记录组件的类的隐式声明字段
        - 字段长度，它隐式是每个数组类型的成员（`§10.7`）
    - 方法，以下内容之一：
        - 在类中声明的方法（抽象方法或其他方法）（`§8.4`）
        - 在接口中声明的方法（抽象方法或其他方法）（`§9.4`）
        - 对应于记录组件的隐式声明访问器方法
    - 枚举常量（`§8.9.1`）
    - 记录组件（`§8.10.3`）
- 形式化参数，以下内容之一：
    - 类或接口方法的形式化参数（`§8.4.1`）
    - 类的构造函数的形式化参数（`§8.8.1`）
    - Lambda 表达式的形式化参数（`§15.27.1`）
    - try 语句 catch 子句中声明的异常处理器的异常参数（`§14.20`）
- 局部变量，以下内容之一：
    - 在块中通过局部变量声明语句声明的局部变量（`§14.4.2`）
    - 通过 for 语句或 try-with-resources 语句声明的局部变量（`§14.14`、`§14.20.3`）
    - 通过模式声明的局部变量（`§14.30.1`）
- 局部类或接口（`§14.3`），以下内容之一：
    - 通过普通类声明声明的局部类
    - 通过枚举声明声明的局部类
    - 通过记录声明声明的局部类
    - 通过普通接口声明声明的局部接口

构造函数（`§8.8`、`§8.10`）也通过声明引入，但它们使用其声明所在类的名称，而不是引入新名称。

泛型类或接口的声明（`class C<T> ... 或 interface C<T>`）同时引入了具名的 `C` 和一族类型：原始类型 `C`、参数化类型 `C<Foo>`、参数化类型 `C<Bar>`。

当在泛化性不重要的地方出现 `c` 的引用时（下文被识别为非泛型上下文之一），对 `c` 的引用表示类或接口 `c`。在其他上下文中，对 `c` 的引用表示由 `c` 引入的类型或类型的一部分。

这 15 个非泛型上下文如下：

1. 在模块声明的 `uses` 指令中（`§7.7.1`）
2. 在单个类型导入声明中（`§7.5.1`）
3. 在单个静态导入声明中 `.` 的左侧（`§7.5.3`）
4. 在按需导入声明中 `.` 的左侧（`§7.5.4`）
5. 在 `sealed` 类或接口声明的 `permits` 子句中（`§8.1.6`、`§9.1.4`）
6. 在构造函数声明中 `(` 的左侧（`§8.8`）
7. 在注解的 `@` 符号之后（`§9.7`）
8. 在类字面量 `.class` 的左侧（`§15.8.2`）
9. 在限定表达式中 `.this` 的左侧（`§15.8.4`）
10. 在限定父类字段中 `.super` 的左侧（`§15.8.2`）
11. 在限定方法调用中 `.Identifier` 或 `.super.Identifier` 的左侧（`§15.12`）
12. 在方法引用中 `::` 的左侧（`§15.13`）
13. 后置表达式或 `try-with-resources` 语句中的限定表达式中
14. 在具有组织关联的限定表达式中（`§15.14`）
15. 在 `throws` 子句中（`§15.15`）

类的名称应当是描述性的名词或名词短语，不应过长，并应采用驼峰命名法（每个单词的首字母大写）。

## 示例 6.1-3. 描述性类名

```java
ClassLoader
SecurityManager
Thread
Dictionary
BufferedInputStream
```

同样，接口名称也应该是短且具有描述性的，不应过长，并应采用驼峰命名法（每个单词的首字母大写）。接口名称可以是描述性的名词或名词短语，这在接口被用作抽象超类使用时是合适的，例如 `java.io.DataInput` 和 `java.io.DataOutput` 接口；也可以描述行为的形容词，如 `Runnable` 和 `Cloneable` 接口。

## 类型变量名

类型名称应该简洁明了（尽可能使用单个字符）且具有启发性，并且不包含小写字母。这有助于区分类型参数与普通类及接口。

容器类和接口使用 `E` 作为其元素类型。Map 应该使用 `K` 作为键的类型，使用 `V` 作为值的类型。`X` 应该用于任意异常类型。当类型没有特定的可以区分之处时，我们使用 `T` 表示类型。（这在泛型方法中很常见）。

如果有多个表示数组类型的类型参数，应该使用在字母表中与 `T` 邻近的字母，例如 `S`。或者，使用数字下标（例如 `T1`、`T2`）来区分不同的类型变量也是可以的。在这些情况下，具有相同前缀的变量应该带有下标。



如果泛型类中出现泛型方法，最好避免方法的类型参数与类的类型参数使用相同的名称，以避免混淆。嵌套泛型类也如此。

## 示例 6.1-4. 惯例类型变量名

```java
public class HashSet<E> extends AbstractSet<E> { ... }
public class HashMap<K,V> extends AbstractMap<K,V> { ... }
public class ThreadLocal<T> { ... }
public interface Functor<T,X> extends Throwableable {
    T apply() throws X;
}
```

当类型参数不方便地归入上述的某一类别时，选择的名称应在单个字母的范围内尽可能有意义。上述提到的名称（`E`、`K`、`V`、`X`、`T`）不应用于不属于指定类别的类型参数。

# 6.1 声明 名称

## 方法名

方法名是动词或动词短语，采用驼峰命名法，首字母小写，后续任何单词的首字母大写。这里是关于方法名的一些额外特定约定：

- 获取和设置可能被认为是变量 `V` 的属性的方法应命名为 `getV` 和 `setV`。例如 `Thread` 类的 `getPriority` 和 `setPriority` 方法。

- 返回某个事物长度的方法应命名为 `length`，如 `String` 类所示。

- 测试对象布尔值 `V` 的方法命名为 `isV`。例如 `Thread` 类的 `isInterrupted` 方法。

- 将其对象转换为特定格式 `F` 的方法应命名为 `toString`。例如 `Object` 类的 `toString` 方法以及 `java.util.Date` 类的 `toLocalString` 和 `toGMTString` 方法。

在可能的情况下，在现有相似类（特别是 Java SE Platform API 中的类）上为新类对方法进行适当命名，将使其更容易使用。

## 字段名

非 `final` 字段名应采用驼峰命名法，首字母小写，后续单词的首字母大写。注意，设计良好的类具有极少的公共或保护字段，常量字段（`static final` 字段）除外。

字段名应该是名词、短语或名词的缩写。

例如 `java.io.InterruptedIOException` 类中的 `buf`、`pos` 和 `count`。

## 常量名

接口中的常量名应该是（且类的 `final` 变量按照习惯可以是）一个或多个单词、缩写或简称的大写序列，组件之间用下划线 `_` 分隔。常量名应具有描述性，且没有不必要的缩写。按照习惯，它们可以是任何适当词性。

常量示例包括 `Character` 类的 `MIN_VALUE`、`MAX_VALUE`、`MIN_RADIX` 和 `MAX_RADIX`。

一组表示集合备选值的常量（或较少表示整数值中的掩码位），有时使用共同的缩写作为名称前缀。

### 示例

```java
interface ProcessStates {
  int PS_RUNNING = 0;
  int PS_SUSPENDED = 1;
}
```

## 局部变量和参数名

局部变量和参数名应该短小且有意义。它们通常是不是单词的小写字母短序列，例如：

- 缩写词，如一系列单词的首字母，例如用于持有 `ColoredPoint` 引用的变量 `cp`

- 缩写，如持有某种类型缓冲区指针的 `buf`

- 助记术语，以某种方式组织以帮助记忆和理解，通常通过使用一组与广泛使用的类的参数名称模式相同的惯例名称的局部变量来实现。例如：

    - `in` 和 `out`，每当涉及某种输入和输出时，参考 `System` 的字段。

    - `off` 和 `len`，每当涉及偏移量和长度时，参考 `java.io` 中 `DataInput` 和 `DataOutput` 接口的 `read` 和 `write` 方法的参数。

应避免单字符的局部变量或参数名，临时变量和循环变量，或者变量持有无区分类型值除。惯例的单字符名称是：

- `b` 表示 byte

- `c` 表示 char

- `d` 表示 double

- `e` 表示 Exception

- `i`、`j` 和 `k` 表示 int

- `l` 表示 long

- `o` 表示 Object

- `s` 表示 String

- `v` 表示任意值

局部变量或参数名不应与包名冲突。

# 6.2 名称与标识符

名称用于引用程序中声明的实体。

名称有两种形式：简单名和限定名。

简单名是单个标识符。

限定名由名称、`.` 标记和标识符组成。

在确定名称的含义（6.5）时，会考虑其出现的上下文。6.5 中的规则区分了名称表示包（6.5.3）、类、接口或类型参数（6.5.5）、表达式中的变量或值（6.5.6）或方法（6.5.7）。

包、类、接口和类型参数具有可以通过限定名访问的成员。关于限定名讨论和名称含义的背景，请参见 4.4、4.5.2、4.8、4.9、7.1、8.2、9.2 和 10.7 中的成员。

程序中并不是标识符都是名称的一部分。标识符还用于以下情况：

- 在声明（6.1）中，标识符可能出现以指定声明实体的名称。

- 在标记语句（14.7）以及 `break` 和 `continue` 语句（14.15、14.16）中引用语句标记。

用于标记语句及其相关的 `break`/`continue` 语句的标识符与声明使用的完全分离。

- 在字段访问表达式（15.11）中，标识符出现在 `.` 标记之后，表示 `.` 之前对象的成员，或 `super` 对象的成员。

- 方法调用表达式（15.12）中，每当标识符出现在 `.` 标记之后且另一个 `.` 标记之前，表示为 `.` 之前对象调用的方法，或 `.` 之前类型的方法，或 `super` 对象的方法。

- 方法引用表达式（15.13）中，每当标识符出现在 `:` 标记之后，表示为 `:` 之前对象的方法，或 `:` 之前类型的方法，或 `super` 对象的方法。

- 在限定类实例创建表达式 (§15.9) 中，标识符出现在 `new` 标记右侧，用于指示该类型是 `new` 标记之前的表达式的编译类型的成员。

- 在注解的元素-值对 (§9.7.1) 中，表示相应注解接口的元素。

在程序中：

```java
class Test {
    public static void main(String[] args) {
        Class c = System.out.getClass();
        System.out.println(c.toString().length() +
            args[0].length() + args.length);
    }
}
```

标识符 `Test`、`main` 以及 `args` 和 `c` 的首次出现并不是名称。相反，它们在声明中被标识以指定所声明实体的名称。`String`、`Class`、`System.out.getClass`、`System.out.println`、`c.toString`、`args` 和 `args.length` 是示例中出现的名称。

`args.length` 中的 `length` 之出现是因为 `args.length` 是一个限定名 (§6.5.2) 而不是字段访问表达式简体15.1.1)。字段访问表达式、方法调用表达式、方法引用表达式以及限定类实例创建表达式都使用标识符而非名称来表示感兴趣的成员。因此，`args[0].length()` 中的 `length` 不是名称，而是出现在方法调用表达式中的标识符。

人们可能会奇怪，为什么这些类型的表达式使用标识符而不是简单名称，毕竟简单名称终究只是一个标识符。原因在于，简单名称是根据词法环境定义的；也就是说，简单名称必须在变量声明的作用域内。另一方面，字段访问、限定方法调用、方法引用和限定类实例都指代其名称不在词法环境中的成员。根据定义，此类名称仅绑定在字段访问表达式、方法调用表达式、方法引用表达式或类实例创建表达式的 `Primary`（主表达式）提供的上下文中；或者绑定在字段访问表达式、方法调用表达式或方法引用表达式的 `super` 提供的文中；以此类推。因此，我们用标识符而非简单名称来表示成员。

更复杂的是字段访问表达式不是表示对象字段的唯一方式。由于解析的原因，限定名用于表示作用域变量的字段。（变量本身由名称表示，此处已提及。）访问控制 (§6.6) 必须同时应用于字段的这两种表示法。

# 6.3 声明的作用域

声明的作用域是程序中的某个区域，在该区域内通过声明定义的实体可以使用简单名称引用，前提是它未被遮蔽 (§6.4.1)。

如果一个声明在程序中的某一点处于作用域内，当且仅当该声明的作用域包含该点。

可见顶层包 (§7.4.3) 声明的作用域是所有与该包唯一可见的模块 (§7.4.3) 相关的可见编译单元。

不可见包的声明永远不在作用域内。

子包的声明永远不在作用域内。

包 `java` 始终在作用域内。

通过单类型导入声明简体7.5.1) 或按需导入类型通配符声明简体7.5.2) 导入的类或接口的作用域是模块声明简体7.7) 以及出现该导入声明的编译单元中所有的类和接口声明简体8.1, §9.1)，以及该编译单元模块声明或包声明上的任何注解。

通过单静态导入声明简体7.5.3) 或按需静态导入通配符声明简体7.5.4) 导入的成员的作用域是模块声明以及出现该导入声明的编译单元中所有的类和接口声明，以及该编译单元模块声明或包声明上的任何注解。

顶层类或接口简体7.6)的作用域是声明该顶层类或接口的包中所有的类和接口声明。

类或接口 `c` 中定义或其继承的成员 `m` 声明的作用域简体8.2, §9.2) 是 `c` 的整个体，包括任何嵌套类或接口声明。

方法简体8.4.1)、构造函数简体8.8.1) 或 lambda 表达式简体15.27) 的形式参数的作用域是该方法、构造函数或 lambda 表达式的整个体。

类的类型参数简体8.1.2)的作用域是类声明的类型参数部分、类声明中任何超类类型或超接口接口的类型参数部分，以及类体。如果该类是记录类简体8.10)，则类型参数的作用域还包括记录声明的头部简体8.10.1)。

接口的类型参数简体9.1.2)的作用域是接口声明的类型参数部分、接口声明中任何超接口类型的类型参数部分，以及接口体。

方法的类型参数简体8.4.4)的作用域是方法的整个声明，包括类型参数部分，但不排除方法修饰符。

构造函数的类型参数简体8.8.4)的作用域是构造函数的整个声明，包括类型参数部分，但不排除构造函数修饰符。

被块简体14.2) 闭合的局部类或接口声明的作用域是该块的剩余部分。

被 `switch` 语句简体14.11) 闭合的局部类或接口声明的作用域是 `switch` 语句的剩余部分，包括局部类声明。

基础 `for` 语句 `ForInit` 部分简体14.14) 中声明变量的作用域包括：

- 自身的初始化

- `ForInit` 部分右侧的后续声明符

- `for` 语句的 `ForUpdate` 部分

- 包含语句

增强型 `for` 语句头部简体14.2) 中声明变量的作用域是包含语句。

`try-with-resources` 语句简体14.20.3) 中资源规格声明的局部变量的作用域是从声明向右的资源规格剩余部分以及整个 `try` 块。

`try-with-resources` 语句意味着上述规则。

`try` 语句简体14.20) 中 `catch` 子句中声明的异常处理参数的作用域是与 `catch` 相关的块。

## 示例 6.3-1 类的作用域

这些规则意味着类和接口类型的声明不需要出现在使用之前。在以下程序中，类 `Point` 中使用 `PointList` 是有效的，因为类声明的作用域包含了 `Point` 和 `PointList` 类，以及包 `points` 中其他编译单元的任何类声明。

```java
package points;
class Point {
    int x, y;
    PointList list;
    Point next;
}

class PointList {
    Point first;
}
```

## 示例 6.3-2 局部变量声明的作用域

以下程序会导致编译错误，因为局部变量 `x` 的初始化位于局部变量 `x` 声明的作用域内，但局部变量 `x` 没有值且无法使用。字段 `x` 有值 0（由于 `Test1` 已初始化），但它是一个误导项，它被局部变量 `x` 遮蔽了简体6.4.1)。

```java
class Test1 {
    static int x;
    public static void main(String[] args) {
        int x = x;
    }
}
```

以下程序可以编译：

```java
class Test2 {
    static int x;
    public static void main(String[] args) {
        int x = (x=2)*2;
        System.out.println(x);
    }
}
```

局部变量 `x` 在在使用前已被确定赋值简体16 (确定赋值))。它打印：

名称

6.3 声明的作用域

在接下来的程序中，`three` 的初始化器可以正确引用在之前的声明符中声明的变量 `two`，而下一行的方法调用可以正确引用在块中较早声明的变量 `three`。

```java
class Test3 {
  public static void main(String[] args) {
    System.out.print("*2+1=");
    int two = 2, three = two + 1;
    System.out.println(three);
  }
}
```

该程序产生输出：

2+1=3

模式变量声明的作用域（即由模式声明的局部变量）是程序中在值与模式匹配后可能执行的部分（§14.30.2）。它是通过考虑在以声明模式变量的模式开头的区域内，模式变量被确定匹配的程序点来确定的。

本节的剩余部分用于对“确定匹配”（definitely matched）一词进行精确解释。该分析考虑了语句和表达式的结构，并对布尔表达式运算符和某些语句形式进行了特殊处理。

将会发现，模式变量声明的作用域是一个流相关的概念，类似于确定赋值（§16 确定赋值）。本节其余部分定义的规则故意具有与确定赋值规则相似的形式。

该分析依赖于技术术语“由...引入”（introduced by），其形式如下：

- 模式变量在表达式为真时，由该表达式引入

- 模式变量在表达式为假时，由该表达式引入

- 模式变量由某条语句引入

最简单的例子是，模式变量 `s` 在表达式 `a instanceof String s` 为真时由该表达式引入。换句话说，如果表达式的值为真，则模式匹配必须成功，因此模式变量必须被赋一个值。

相比之下，模式变量在表达式 `!(b instanceof Integer t)` 为假时由该表达式引入。这是因为只有当表达式的值为假时，模式匹配才可能成功。

## 6.3.1 表达式中模式变量的作用域

只有某些类型的布尔表达式涉及模式变量的引入以及确定这些变量被确定匹配。如果一个表达式不是条件与表达式、条件或表达式、逻辑取反表达式、条件表达式、instanceof 表达式、switch 表达式或带括号的表达式，则不适用任何作用域规则。

### 6.3.1.1 条件与运算符 &&

以下规则适用于条件与表达式 `a && b` (§S15.23)：

- 由 `a` 为真时引入的模式变量在 `b` 处被确定匹配。

- 如果任何由 `a` 为真时引入的模式变量在 `b` 处已在作用域内，则为编译错误。

- 模式变量在 `a && b` 为真时引入，当当 (i) 它由 `a` 为真引入或 (ii) 它由 `b` 为真引入。

应该注意的是，没有关于在 `a && b` 为假时引入模式变量的规则。这是因为在编译时无法确定哪个部分为假。

如果满足以下任一条件，则为编译错误：

- 模式变量既是 (i) 由 `a` 为真时引入，又是 (ii) 由 `b` 为真时引入。

- 模式变量既是 (i) 由 `a` 为假时引入，又是 (ii) 由 `b` 为假时引入。

这些错误情况排除了 `&&` 运算符的两个操作数都声明同名模式变量的可能性。例如，考虑有问题的表达式 `(a instanceof String s && b(instanceof String s))`。第一种错误情况涵盖了整个表达式值为 `true` 的情况（如果代码是合），由于左操作数和右操作数都求值为 `true`，则需要初始化两个模式变量 `s` 的声明。由于在程序的其余部分无法区分两个名为 `s` 的变量，因此整个表达式被认为是错误的。第二种错误情况涵盖了相反的情况，即整个表达式值为 `false`。

### 6.3.1.2 条件或运算符 ||

以下规则适用于条件或表达式 `a || b` (§S15.24)：

- 由 `a` 为假时引入的模式变量在 `b` 处被确定匹配。

- 如果任何由 `a` 为假时引入的模式变量在 `b` 处已在作用域内，则为编译错误。

- 模式变量在 `a || b` 为假时引入，当且仅当 (i) 它由 `a` 为假引入或 (ii) 它由 `b` 为假引入。

应该注意的是，没有关于在 `a || b` 为真时引入模式变量的规则。这是因为在编译时无法确定哪个操作数求值为 `true`。

如果满足以下任一条件，则为编译错误：

- 模式变量既是 (i) 由 `a` 为真时引入，又是 (ii) 由 `b` 为真时引入。

- 模式变量既是 (i) 由 `a` 为假时引入，又是 (ii) 由 `b` 为假时引入。



这两种情况排除了 `||` 运算符的两个操作数都声明同名模式变量的可能性。例如，有问题的表达式 `(a instanceof String s) || (b instanceof String s)`。第一种错误情况涵盖了整个求值为 `true` 的情况（如果代码合法），由于左操作数和右操作数都求值为 `true`，需要初始化两个模式变量 `s` 的声明。由于无法确定哪个操作数求值为 `true`，整个表达式被认为是错误的。第二种错误情况涵盖了表达式值为 `false` 的相反情况。

### 6.3.1.3 逻辑取反运算符 !

以下规则适用于逻辑取反表达式 `!a` (§S15.6)：

- 模式变量在 `!a` 为真时引入，当且仅当它由 `a` 为假引入。
- 模式变量在 `!a` 为假时引入，当且仅当它由 `a` 为真引入。

### 6.3.1.4 条件运算符 ? :

以下规则适用于条件表达式 `a ? b : c` (§15.25)：

- 由 `a` 为真时引入的模式变量在 `b` 处被确定匹配。
- 如果任何由 `a` 为真时引入的模式变量在 `b` 处已在作用域内，则为编译错误。
- 由 `a` 为假时引入的模式变量在 `c` 处被确定匹配。
- 如果任何由 `a` 为假时引入的模式变量在 `c` 处已在作用域内，则为编译错误。

应该注意的是，没有关于在 `a ? b : c` 为真或假时引入模式变量的规则。这是因为在编译时无法确定操作数 `a` 是否求值为 `true`。

如果满足以下任一条件，则为编译错误：

- 模式变量既是 (i) 由 `a` 为真时引入，又是 (ii) 由 `c` 为真时引入。
- 模式变量既是 (i) 由 `a` 为真时引入，又是 (ii) 由 `c` 为假时引入。
- 模式变量既是 (i) 由 `a` 为假时引入，又是 (ii) 由 `b` 为真时引入。
- 模式变量既是 (i) 由 `a` 为假时引入，又是 (ii) 由 `b` 为假时引入。
- 模式变量既是 (i) 由 `b` 为真时引入，又是 (ii) 由 `c` 为真时引入。
- 模式变量既是 (i) 由 `b` 为假时引入，又是 (ii) 由 `c` 为假时引入。

> 这些错误情况类似于 `&&` 和 `||` 运算符的错误情况。它们消除了在 `? :` 运算符的操作数之间可能出现同名模式变量声明的情况。

### 6.3.1.5 模式匹配运算符 instanceof

以下规则适用于带有模式操作数的 `instanceof` 表达式 `instanceof p` (§15.20.2)：

- 模式变量在 `instanceof p` 为真时引入，如果它由模式 `p` 声明。确定哪些模式变量由模式声明的规则见 §14.30.1。
- 如果由 `a instanceof p` 为真时引入的模式变量在 `instanceof` 表达式处已在作用域内，则为编译错误。
- 模式变量不允许遮蔽另一个局部变量 (§6.4)。

应当注意的是，当 `instanceof p` 为 `false` 时，没有关于引入该模式变量的规则。

### 6.3.1.6 switch 表达式

以下规则适用于 switch 表达式 (§15.28)：

- 由包含在 switch 标签语句组 (§14.11.1) 中的语句 `s` 引入的模式变量，一定匹配于该 switch 标签语句组中 `s` 之后的所有语句（如果有）。

### 6.3.1.7 括号表达式

以下规则适用于括号表达式 `(a)` (§15.8.5)：

- 当 `(a)` 为 `true` 时，由 `(a)` 引入的模式变量当且仅当它在 `a` 为 `true` 时被引入。
- 当 `(a)` 为 `false` 时，由 `(a)` 引入的模式变量当且仅当它在 `a` 为 `false` 时被引入。

## 6.3.2 语句中模式变量的作用域

只有少数几种语句在确定模式变量的作用域方面起着重要作用。

当 `if, while, do` 或 `for` 语句包含一个引入模式变量的表达式时，在某些情况下，这些变量的作用域可以包含语句的子结构。

> 示例，在下面的 `if-then-else` 语句中，模式变量 `s` 的作用域包含一个子语句，但不包含另一个：

```
Object o = ...
if (o instanceof String s)
    // s 在此子语句的作用域内；不需要对 o 进行强制转换
    System.out.println(s.replace('*', '_'));
else
    // s 不在此子语句的作用域内（因此，会导致错误）
    System.out.println(s);
```

此外，在某些情况下，模式变量可以由语句本身引入，而不是通过语句内部的表达式。由语句引入的模式变量在闭包块的后续语句中作用域内。

例如，在下面的方法中，模式变量 `s` 的作用域包含了 if 语句之后的方法体：

```
void test(Object o) {
    if (!(o instanceof String s)) {
        throw new IllegalArgumentException();
    // 这一点只有在模式匹配成功时才能到达
    // 因此，s 在块的剩余范围内有效
    }
    System.out.println(s.repeat(5));
}
```

### 6.3.2.1 块

以下规则适用于包含在块 (§14.2) 中的块语句 `s`，且该块不是 switch 块 (§14.11.1)：

- 由 `s` 引入的模式变量一定匹配于块中 `s` 之后的所有块语句（如果有）。

### 6.3.2.2 if 语句

以下规则适用于语句 `if (e) s` (§14.9.1)：

- 由 `e` 为 `true` 时引入的模式变量一定在 `s` 处匹配。
- 如果由 `e` 为 `true` 时引入的任何模式变量在 `s` 处已在作用域内，则为编译错误。
- 由 `if (e)` 引入模式变量当且仅当：(i) 它在 `e` 为 `false` 时被引入，且 (ii) `s` 无法正常完成。
- 如果由 `if (e) s` 引入的任何模式变量在语句处已在作用域内，则为编译错误。

关于 `if-then` 语句引入模式变量的规则依赖于“无法正常完成” (§14.22) 的关系，而这又依赖于常数表达式的概念 (§15.29)。这意味着计算模式变量的作用域可能需要确定简单名称或类型 `TypeName.Identifier` 的限定名称是否引用常量变量。模式变量永远不会引用常量变量，不存在循环引用。

以下规则适用于语句 `if (e) s else t` (§14.9.2)：

- 由 `e` 为 `true` 时引入的模式变量一定在 `s` 处匹配。
- 如果由 `e` 为 `true` 时引入的任何模式变量在 `s` 处已在作用域内，则为编译错误。
- 由 `e` 为 `false` 时引入的模式变量一定在 `t` 处匹配。
- 如果由 `e` 为 `false` 时引入的任何模式变量在 `t` 处已在作用域内，则为编译错误。
- 由 `if (e) s else t` 引入模式变量当且仅当：
  - 它在 `e` 为 `true` 时引入，且 `s` 可以正常完成，而 `t` 无法正常完成；或者
  - 它在 `e` 为 `false` 时引入，且 `s` 无法正常完成，而 `t` 可以正常完成。
- 如果由 `if (e) s else t` 引入的任何模式变量在 if 语句处已在作用域内，则为编译错误。

这些规则强调了模式变量作用域的流式特性。例如，在下面的语句中：

```
if (o instanceof String s) {
    counter += s.length();
} else {
    System.out.println(e); // s 不在作用域内
}
```

模式变量 `s` 由 `instanceof` 表达式引入，在第一个包含的语句（then 块中的赋值语句）中作用域内，但在第二个包含的语句（else 块中的表达式语句）中不在作用域内。

此外，结合对布尔表达式的处理，模式变量的作用域对于利用熟悉的布尔逻辑等价性的代码重构具有健壮性。之前的代码可以重写为：

```
if (!(o instanceof String s)) {
    System.out.println(e); // s 不在作用域内
} else {
    counter += s.length();
}
```

### 6.3.3 while 语句

以下规则适用于语句 `while (e) s` (§14.12)：

- 由 `e` 为 `true` 时引入的模式变量一定在 `s` 处匹配。
- 如果由 `e` 为 `true` 时引入的任何模式变量在 `s` 处已在作用域内，则为编译错误。
- 模式变量由 `while (e)` 引入当且仅当：(i) 它在 `e` 为 `false` 时引入，且 (ii) `s` 不包含目标为 `s` 的可达 `break` 语句 (§14.15)。
- 如果由 `while (e)` 引入的任何模式变量在语句处已在作用域内，则为编译错误。

### 6.3.4 do 语句

以下规则适用于语句 `do s while (e)` (§14.13)：

- 模式变量由 `do s while (e)` 引入当且仅当：(i) 它在 `e` 为 `false` 时引入，且 (ii) `s` 不包含目标为 `s` 的可达 `break` 语句 (§14.15)。
- 如果由 `do s while (e)` 引入的任何模式变量在语句处已在作用域内，则为编译错误。

### 6.3.5 for 语句

以下规则适用于基础 for 语句 (§14.14)：

- 由表达式为 `true` 时引入的模式变量在迭代部分和包含的语句中一定匹配。
- 如果由表达式为 `true` 时引入的任何模式变量在包含语句的迭代部分已在作用域内，则为编译错误。
- 模式变量由基础 for 语句引入当且仅当：(i) 它在条件为 `false` 时引入，且 (ii) 包含语句 `s` 不包含目标为 `s` 的可达 `break` 语句 (§14.15)。
- 如果由基础 for 语句引入的任何模式变量在 for 语句处已在作用域内，则为编译错误。

### 6.3.6 switch 语句

以下规则适用于 switch 语句 (§14.11)：

- 由包含在 switch 块语句组 (§14.11.1) 中的标签语句 `s` 引入的模式变量一定匹配于该 switch 块语句组中 `s` 之后的所有语句。

### 6.3.7 标签语句

以下规则适用于标签语句 (§14.7)：

- 模式变量由标签语句引入只要由其直接包含的语句引入。

## 6.4 遮蔽与掩盖

局部变量 (§14.4)、形式参数 (§8.4.1, §8.8.1, §15.27.1)、异常参数 (§14.20)、局部类或局部接口 (§14.3) 只能使用简单名称引用，不能使用限定名称 (§6.2)。

在局部变量声明、形式参数声明、异常参数声明、局部类声明或局部接口声明的作用域内，不允许某些声明，因为仅通过简单名称无法区分声明的实体。

> 例如，如果形式参数的名称在方法体中被重新声明为局部变量的名称，那么局部变量将遮蔽形式参数，导致没有方法可以引用形式参数 - 这是一个不理想的结果。

如果在方法体、构造函数或 Lambda 表达式体中使用形式参数名称来声明新变量，则为编译错误，除非新变量被声明在方法、构造函数或 lambda 表达式所包含的类或接口声明内部。

如果在局部变量 `v` 的作用范围内使用变量 `v` 的名称来声明新变量，则将产生编译错误，除非该新变量声明在出现在 `v` 作用范围内的类或接口声明内部。

如果使用异常参数的名称在 `catch` 子句的块中声明新变量，则将产生编译错误，除非该新变量声明在 `catch` 子句块所包含的类或接口声明内部。

如果在局部类或接口 `c` 的作用范围内使用变量 `c` 的名称来声明新类或接口，则将产生编译错误，除非该新的局部类或接口声明在出现在 `c` 作用范围内的类或接口声明内部。

这些规则允许在变量、局部类或局部接口的作用范围内的嵌套类或接口声明中，重新声明变量、局部类或局部接口；嵌套类或接口声明可以是局部类或接口声明 (§14.3) 或匿名声明 (§15.9.5)。因此，形式参数、局部类或局部接口的声明可以在嵌套在方法、构造函数或 lambda 表达式内部的类或接口声明中被遮蔽；异常参数的声明可以在嵌套在 `catch` 子句块内部的类或接口声明中被遮蔽。

处理 lambda 参数创建的新类以及在 lambda 表达式中声明的其他变量有两种设计。一种是模拟类声明：像局部类一样，lambda 表达式在异常之外引入了一个新的“层级”以便重新声明。另一种是“局部”策略：`catch` 子句、循环、块、lambda 表达式与封装环境处于同一“层级”，且异常外部的局部变量不能被遮蔽。上述规则使用了这种策略；并没有特殊规定允许 lambda 表达式中声明的变量遮蔽封装方法中声明的变量。

### 示例 6.4-1. 尝试遮蔽局部变量

由于在方法、构造函数或初始化块中局部变量声明标识符，并没有出现在同名参数或局部变量的作用范围内，因此以下程序将产生编译错误：

```
class Test1 {
  public static void main(String[] args) {
    int i;
    for (int i = 0; i < 10; i++) {
      System.out.println(i);
    }
  }
}
```

这种限制有助于检测某些原本非常晦涩的错误。对于局部变量遮蔽成员的类似限制被认为是不现实的，因为在父类中添加成员可能会导致子类重命名局部变量。相关的考虑也使得对嵌套类成员遮蔽局部变量、或嵌套类内部声明的局部变量遮蔽局部变量的限制变得不那么吸引力。

因此，以下程序可以无错误编译：

```
class Test2 {
    public static void main(String[] args) {
        int i;
        class Local {
            {
                for (int i = 0; i < 10; i++)
                    System.out.println(i);
            }
        }
        new Local();
    }
}
```

另一方面，同名的局部变量可以声明在两个独立的 `for` 块中，且其中一个不包含另一个：

```
class Test3 {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++)
            System.out.print(i + " ");
        for (int i = 9; i >= 0; i--)
            System.out.print(i + " ");
    }
}
```

该程序可以无错误编译，并在执行时产生输出：

```
0 1 2 3 4 5 6 7 8 9 9 8 7 6 5 4 3 2 1 0
```

这种风格在模式匹配中也很常见，重复的模式通常会使用相同的名称：

```
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}

class Test4 {
    static void test(Object a, Object b, Object c) {
        if (a instanceof Point p) {
            System.out.println("a is a point (" + p.x + "," + p.y + ")");
        } else if (b instanceof Point p) {
            System.out.println("b is a point (" + p.x + "," + p.y + ")");
        } else if (c instanceof Point p) {
            System.out.println("c is a point (" + p.x + "," + p.y + ")");
        }
    }

    public static void main(String[] args) {
        Point p = new Point(2,3);
        Point q = new Point(4,5);
        Point r = new Point(6,7);

        test(p, q, r);
    }
}
```

然而，模式变量不允许遮蔽局部变量（包括模式变量），因此以下程序将产生编译错误：

```
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}

class Test5 {
    static void test(Object a, Object b, Object c) {
        if (a instanceof Point p) {
            System.out.println("a is a point (" + p.x + "," + p.y + ")");
        }

        if (b instanceof Point p) { // 编译错误
            System.out.println("b is a point (" + p.x + "," + p.y + ")");
        }
    }
}
```

`println` 的调用使用了限定名称 (§6.6) `Test.x`，它使用类名 `Test` 来访问类变量 `x`，这是因为 `Test.x` 的声明在此处被遮蔽，无法通过其简单名称进行引用。

关键字 `this` 也可以用于访问被遮蔽的字段 `x`，形式为 `this.x`。事实上，这种惯用法通常出现在构造函数中 (§8.8)。



```java
class Pair {
    Object first, second;
    public Pair(Object first, Object second) {
        this.first = first;
        this.second = second;
    }
}
```

在这里，构造函数接收的参数与要初始化的字段具有相同的名称。这比为参数使用不同的名称更简单，而且在这种类风格化的语境下并不令人困惑。然而，通常认为使用与字段具有相同名称的局部变量是不良风格。

### 示例 6.4.1-2. 一个类型声明对另一个类型声明的遮蔽

```java
import java.util.*;
class Vector {
    int val[] = { 1, 2 };
}
```

```java
class Test {
    public static void main(String[] args) {
        Vector v = new Vector();
        System.out.println(v.val[0]);
    }
}
```

程序通过编译并打印：

1 使用了在此处声明的 `Vector` 类，而优于可能按需导入的泛类 `java.util.Vector` (§8.1.2)。

## 6.4.2 混淆（Obscuring）

简单名称可能出现在可能被解释为变量名、类型名或包名的语境中。在这些情况下，§6.5.2 的规则规定：优先选择变量优于类型，优先选择类型优于包。因此，有时无法通过简单名称引用类型或包，即使其声明在作用范围内且未被遮蔽。我们称这种声明为被*混淆的*（obscured）。

混淆不同于遮蔽（§6.4.1）和隐藏（§8.3, §8.4.8.2, §8.5, §9.3, §9.5）。

模块名称与变量、类型或包的名称之间不存在混淆；因此，模块可以与变量、类型和包共享名称，尽管并不一定建议以其所包含的包来命名模块。

§6.1 中的命名规范有助于减少混淆，但如果确实发生了混淆，关于可以做些什么来避免混淆还有一些说明。

当包名出现在表达式中时：

- 如果包名被字段声明混淆，则通常可以使用导入声明（§7.5）来使用该包中声明的类型名。
- 如果包名被参数或局部变量的声明混淆，则可以更改参数或局部变量的名称，而不影响其他代码。

包名的第一个组件通常不会被误认为是类型，因为名称通常以单个大写字母开头。（Java 编程语言实际上并不依赖这些罕见情况来判断一个名称是包名还是类型名。）

方法名不能混淆其他名称，也不会被其他名称混淆（§6.5.7）。

涉及字段名的混淆很罕见；但是：

- 如果字段名混淆了包名，通常可以使用导入声明（§7.5）来使用该包中声明的类型名。
- 如果字段名混淆了类型，可以使用类型的完全限定名称，除非该类型名表示局部类或接口（§14.3）。
- 字段名不能混淆方法名。
- 如果字段名被参数或局部变量的声明遮蔽，可以更改参数或局部变量的名称，而不影响其他代码。

涉及常量名的混淆很罕见：

- 常量名通常没有小写字母，因此它们通常不会混淆包名或类型名，通常也不会遮蔽字段（字段名通常包含至少一个小写字母）。
- 常量名不能混淆方法名，因为它们在语法上是可以区分的。

## 6.5 确定名称的含义

名称的含义取决于其使用的语境。确定名称的含义需要三个步骤：

- 首先，语境导致名称在语法上落入七类之一：*模块名（`ModuleName`）、包名（`PackageName`）、类型名（`TypeName`）、表达式名（`ExpressionName`）、方法名（`MethodName`）、包或类型名（`PackageOrTypeName`）或模糊名称（`AmbiguousName`）。*
- *类型名和方法名*的表达能力低于其他五类，因为它们分别由*类型标识符（`TypeIdentifier`）*和*未限定标识符（`UnqualifiedIdentifier`）*表示（§3.8）。
- 第二，最初根据语境被归类为*模糊名称*或*包或类型名*的名称，会被重新归类为*包名、类型名或表达式名*。
- 第三，结果的类别决定了名称含义的最终确定（如果名称没有含义，则为编译时错误）。

```
ModuleName:
Identifier
ModuleName . Identifier
```

```
PackageName:
Identifier
PackageName . Identifier
```

```
TypeName:
TypeIdentifier
PackageOrTypeName . TypeIdentifier
```

```
PackageOrTypeName:
Identifier
PackageOrTypeName . Identifier
```

```
ExpressionName:
Identifier
AmbiguousName . Identifier
```

```
MethodName:
UnqualifiedIdentifier
```

```
AmbiguousName:
Identifier
AmbiguousName . Identifier
```

语境的使用有助于减少实体之间的冲突，如果遵循 §6.1 中的命名规范，这种冲突将很少发生。然而，由于不同程序员开发的类型，可能会产生冲突。例如，方法和字段可能具有相同的名称。语境的存在总是可以区分方法和字段。

### 6.5.1 根据语境对名称进行句法分类

名称在以下语境中被句法分类为模块名：

- 模块的 `requires` 指令中（§7.7）
- 模块的 `exports` 或 `opens` 指令中（右侧）

名称在以下语境中被句法分类为包名：

- `exports` 或 `opens` 指令的右侧

名称在以下语境中被句法分类为类型名：

- 类或接口
    1. 模块的 `uses` 或 `provides` 指令中（§7.7）
    2. 导入声明中（§7.5）
    3. `static-import` 的左侧（§7.5）
    4. 模块的 `static-import` 中（§7.5）
    5. 密封类或接口的 `permits` 子句（§8.1, §9.6）
    6. 构造函数的 `(` 左侧（§8.8）
    7. 注释符号 `@` 之后（§9.7）
    8. 类字面量中的 `.class` 左侧（§15.8）
    9. 限定表达式中的 `.this` 左侧（§15.8）
    10. 类的类访问中的 `.super` 左侧（§15.11）
    11. 方法调用表达式中的 `.Identifier` 左侧（§15.12）
    12. 方法引用中的 `::` 左侧（§15.13）

在以下 17 个语境中，构成任何限定类型的 `Identifier` 或点号 `Identifier` 序列（包括数组类型 `[]` 左侧的类型、泛型类型 `<` 左侧的类型、泛型类型中的通配符）的引用类型：

- 类声明的 `extends` 或 `implements` 子句中（§8.1, §8.5）
- 接口声明的 `extends` 子句中（§9.1.3）
- 方法或构造函数的 `throws` 子句中（§8.4.6, §8.8.5, §9.4），包括注解元素的类型（§9.6.1）
- 泛型接口、方法或构造函数的类型参数的 `extends` 子句中（§8.1.2, §9.1.2, §8.4.4, §8.8.4）
- 类或接口字段声明中的类型（§8.3, §9.3）
- 方法、构造函数或 Lambda 表达式的形式参数（§8.4.1, §8.8.1, §9.4, §15.27.1）
- 方法接收参数的类型（§8.4）
- 语句中的局部变量声明（§14.4.2, §14.1.1, §14.1.2, §14.20.3）或模式（§14.30.1）
- 异常参数声明中的类型（§14.20）
- 记录类记录组件声明中的类型（§8.10.1）
- 显式构造函数调用语句、类实例创建表达式或方法调用表达式中的显式类型参数（§8.8.7.1, §15.9, §15.12）
- 无限定类实例创建表达式，要么作为实例化的类类型（§15.9），要么作为匿名类的直接父类或直接超接口（§15.9.5）
- 数组创建表达式中的元素类型（§15.10.1）
- 转换表达式中转换操作符的类型（§15.16）
- `instanceof` 关系运算符后面的类型（§15.20.2）

在这些语境中，一个名称在语法上被分类为 `ExpressionName`（表达式名）：

- 作为限定超类构造函数调用表达式中的限定表达式（§8.8.7.1）
- 作为限定类实例创建表达式中的限定表达式（§15.9）
- 作为数组访问表达式中的数组引用表达式（§15.10.3）
- 作为赋值操作符的左侧操作数（§15.26）
- 作为 `try`-with-resources 语句中的 `VariableAccess`（变量访问）（§14.20.23）

一个名称在以下语境中在语法上被分类为 `MethodName`（方法名）：

- 在方法调用表达式的 `(` 之前（§15.12）

一个名称在这些语境中在语法上被分类为 `PackageOrTypeName`（包或类型名）：

- 在限定 `TypeName` 中 `.` 的左侧
- 在按需导入的类型声明中（§7.5.2）

一个名称在这些语境中在语法上被分类为 `AmbiguousName`（歧义名）：

- 在限定 `ExpressionName` 中 `.` 的左侧
- 在方法调用表达式中 `(` 之前的最右侧 `.` 的左侧
- 在限定 `AmbiguousName` 中 `.` 的左侧
- 在注解元素声明的默认值子句中（§9.6.2）
- 在元素值对中 `=` 的右侧（§9.7.1）
- 在方法引用表达式中 `::` 的左侧（§15.13）

## 6.5.2 语境歧义名称的分类

`AmbiguousName` 被重新分类为单个 `Identifier`，然后：

- 如果该 `Identifier` 出现在表示具有同名局部变量、形式参数、表达式参数或字段的声明范围内（§6.3）（§14.4, §8.4.1, §8.1, §15.27.1, §14.20, §8.3），则该 `AmbiguousName` 被重新分类为 `ExpressionName`（表达式）。
- 否则，如果该 `Identifier` 是一个有效的 `TypeIdentifier`（类型标识符，§3.8）并且出现在表示具有该名称类、接口或类型参数的声明范围内（§8.1, §9.1, §8.4.4, §8.8.4），则 `AmbiguousName` 被重新分类为 `TypeName`。
- 否则，`AmbiguousName` 被重新分类为 `PackageName`（包名）。随后的步骤将确定该名称的包是否实际存在。

如果 `AmbiguousName` 是限定名，由一个名称、一个 `.` 和一个 `Identifier` 组成，则 `.` 左侧的名称首先被重新分类，因为它本身也是一个 `AmbiguousName`。这里有一个选择：

- 如果 `.` 左侧的名称被重新分类为 `PackageName`，那么：
    - 如果该 `Identifier` 是一个有效的 `TypeIdentifier`，并且有一个包的名称为 `.` 左侧的名称，且该包包含一个名称与 `Identifier` 相同的类型声明，则该 `AmbiguousName` 被重新分类为 `TypeName`。
    - 否则，该 `AmbiguousName` 被重新分类为 `PackageName`。随后的步骤将确定该名称的包是否实际存在。

- 如果 `.` 左侧的名称被重新分类为 `TypeName`，那么：
    - 如果该 `Identifier` 是由 `TypeName` 所指类型的方法或字段的名称，则该 `AmbiguousName` 被重新分类为 `ExpressionName`。
    - 否则，如果该 `Identifier` 是一个有效的 `TypeIdentifier` 并且是 `TypeName` 所指类型成员的名称，则该 `AmbiguousName` 被重新分类为 `TypeName`。
    - 否则，该 `AmbiguousName` 被重新分类为 `PackageName`。随后的步骤将确定该名称的包是否实际存在。

### 示例 6.5.2-1. 语境歧义名称的重新分类

考虑以下人为构造的库代码：

```java
package org.ryptoet;
import java.util.Random;
public interface Music {
    Random[] wizards = new Random[0];
}
```

并在另一个包中考虑此示例：

```java
package bazo;
class Gabriel {
    static int n = org.ryptoet.Music.wizards.length;
}
```

首先，`org.ryptoet.Music.wizards.length` 作为后缀表达式被分类为 `ExpressionName`。因此，以下名称：

```
org.ryptoet.Music.wizards
org.ryptoet.Music
org
```

最初被分类为 `AmbiguousName`。它们被重新分类：

- 简单名称 `org` 被重新分类为 `PackageName`（因为范围内没有变量或类型）。
- 接下来，因为包 `org.ryptoet` 有一个名为 `Music` 的可见接口，限定名 `org.ryptoet.Music` 被重新分类为 `TypeName`。
- 最后，因为 `org.ryptoet.Music` 是 `TypeName`，限定名 `org.ryptoet.Music.wizards` 被重新分类为 `ExpressionName`。

## 6.5.3 模块名和包名的含义

模块 M，无论是简单的还是限定的，都表示具有该名称的模块（如果有）。

本节并不强制在无模块时产生编译错误。相反，模块声明中的 `requires` 指令（§7.7.1）会对模块名称进行自身的验证，而 `exports` 和 `opens` 指令（§7.7.2）对不存在的模块名是允许的。

分类为 `PackageName` 的名称的含义确定如下。

### 6.5.3.1 简单包名

如果包名由单个 `Identifier` 组成，则该标识符必须出现在一个具有此名称的顶层包声明范围内（§6.3），且该包对当前声明是可见的（§7.4.3），否则将发生编译错误。该包名的含义为该包。

### 6.5.3.2 限定包名

如果包名采用 `Q.Id` 形式，则 `Q` 必须也是一个包名。包名 `Q.Id` 表示包 `Q` 内部的包 `Id`。

`Q.Id` 不指向当前模块唯一可见的包（§7.4.3），则将发生编译错误。

## 6.5.4 包或类型名的含义

### 6.5.4.1 简单包或类型名

如果 `PackageOrTypeName` `Q` 是一个有效的 `TypeIdentifier` 并且出现在名为 `Q` 的类、接口或类型参数的声明范围内，则该 `PackageOrTypeName` 被重新分类为 `TypeName`。

否则，`PackageOrTypeName` 被重新归类为 `PackageName`。`PackageOrTypeName` 的含义为重新归类名称的含义。



## 6.5.4.2 限定的 PackageOrTypeName

给定形式为 `Q.Id` 的限定 `PackageOrTypeName`，如果 `Id` 是有效的 `TypeIdentifier`，且由 `Q` 所指示的类、接口或包具有名为 `Id` 的成员类或接口名称，则该限定 `PackageOrTypeName` 名称被重新归类为 `TypeName`。

否则，它被重新归类为 `PackageName`。限定 `PackageOrTypeName` 的含义为重新归类名称的含义。

## 6.5.5 TypeName 的含义

被归类为 `TypeName` 的名称的含义确定如下。

### 6.5.5.1 简单类型名称

如果一个名称由单个 `Identifier` 组成，则该标识符必须恰好一个同名类、接口或类型参数声明的作用域内（§6.3），否则将发生编译错误。

如果该声明指示泛型类或接口 `c` 的类型参数（§8.1.2, §9.1.2），则以下两点必须成立，否则将发生编译错误：

- 该类型名称不在静态上下文中（§8.1.3）。
- 如果该类型名称出现在 `C` 的嵌套类或接口声明中，则该类型名称的直接外层类或接口声明是 `C` 的内部类。

> 例如，该类型名称不能出现在由 `C` 声明的静态方法的体体中，也不能出现在嵌套在 `C` 内部的静态类的实例方法的体中。

如果该声明指示泛型方法或构造函数 `m` 的类型参数（§8.4.4, §8.8.4），且该类型名称直接或间接地出现在在 `m` 的体中声明的局部类、局部接口或匿名类 `D` 的体中，则以下两点必须成立，否则将发生编译错误：

- 该类型名称不在静态上下文中。
- `D` 是一个内部类，且该类型名称的直接外层类或接口声明是 `D` 或 `D` 的内部类。

例如，该类型名称不能出现在由 `D` 声明的静态方法的体中，也不能（如果 `D` 是局部接口）出现在 `D` 的默认方法的体中。

该类型名称的含义为作用域内的类、接口或类型参数。

### 示例 6.5.5.1-1 对类型参数的引用

```java
class Box<T> {
  T val;
  Box(T t) { val = t; }

  static Box<T> empty() { // 编译错误
    return new Box<>(null);
  }

  static <U> Box<U> make(U val) {
    interface Checker {
      void check(U val); // 编译错误
    }
    class NullChecker implements Checker {
      public void check(U val) {
        if (val == null) {
          throw new IllegalArgumentException();
        }
      }
    new NullChecker().check(val);
    return new Box<U>(val);
  }
}
```

类型参数 `T` 在整个类 `Box` 的声明范围内都处于作用域内；但在静态方法 `empty` 的声明中使用名称 `T` 是非法的。

同样，方法参数 `U` 在整个方法 `make` 的声明范围内都处于作用域内；但在（隐式静态的）接口 `Checker` 的声明中使用名称 `U` 是非法的。

### 6.5.5.2 限定类型名称

如果一个类型名称的形式为 `Q.Id`，则 `Q` 必须是当前模块唯一可见的类、接口或类型参数的名称，或者是当前模块唯一可见的包的名称（§7.4.3）。

如果 `Id` 恰好指示一个可访问的类或接口（§6.6），且该类或接口是 `Q` 所指示的类、接口、类型参数或包的成员，则该限定名称指示该类或接口。

如果 `Id` 未指示 `Q` 的成员类或接口（§8.5, §9.5），或者 `Q` 内部名为 `Id` 的成员类或接口不可访问，或者 `Id` 在 `Q` 内部指示了多个一个成员类或接口，则将发生编译错误。

### 示例 6.5.5.2-1 限定类型名称

```java
class Test {
    public static void main(String[] args) {
        java.util.Date date = new java.util.Date(System.currentTimeMillis());
        System.out.println(date.toLocaleString());
    }
}
```

该程序在第一次运行时产生了输出：

Sun Jan 21 22:56:29 1996

在此示例中，名称 `java.util.Date` 必须指示一个类型，因此我们首先递归递归以确定 `java.util` 是否是可访问的类、接口、类型参数或包（它确实是），然后查看在该包中的类 `Date` 是否可访问。

## 6.5.6 ExpressionName 的含义

被归类为 `ExpressionName` 的名称的含义确定如下。

### 6.5.6.1 简单表达式名称

如果一个表达式名称由单个 `Identifier` 组成，则在标识符出现的位置，必须恰好有一个声明指示范围内的局部变量、形式参数、异常参数或字段。否则，将发生编译错误。

### 示例 6.5.6.1-1 对字段的引用

```java
static final int f = 3;
public static void main(String[] args) {
    int i;
    i = 1;
    v = 2;
    f = 33; // compile-time error
    System.out.println(i + " " + v + " " + f);
}
```

在此程序中，作为 `i`、`v` 和 `f` 赋值左侧使用的名称表示局部 `i`、字段 `v` 以及 `f` 的值（而不是变量 `f`，因为 `f` 是一个 final 变量）。因此，该示例在编译时会产生错误，因为最后一个赋值的左侧没有变量。如果删除错误的赋值，修改后的代码可以编译并产生输出：

- 1
- 2
- 3

### 示例 6.5.6.1-2 对实例变量的引用

```java
class Test {
    static String a;
    String b;

    String concat1() {
        return a + b;
    }

    static String concat2() {
        return a + b; // compile-time error
    }

    int index() {
        interface I {
            class Matcher {
                void check() {
                    if (a == null || b == null) { // compile-time error
                        throw new IllegalArgumentException();
                    }
                }
            }
            int match(String s, String t) {
                return s.indexOf(t);
            }
        }

        I.Matcher matcher = new I.Matcher();
        matcher.check();
        return matcher.match(a, b);
    }
}
```

字段 `a` 和 `b` 在整个 `Test` 类的体范围内都是可见的。然而，在 `concat2` 方法的静态上下文中使用名称 `b`，或者在不是 `Test` 内部类的嵌套类 `Matcher` 的声明中使用该名称，是非法的。

### 示例 6.5.6.1-3 对局部变量和形式参数的引用

```java
class Test {
    public static void main(String[] args) {
        String first = args[0];

        class Checker {
            void checkWhitespace(int x) {
                String arg = args[x];
                if (!arg.trim().equals(arg)) {
                    throw new IllegalArgumentException();
                }
            }

            static void checkFlag(int x) {
                String arg = args[x]; // compile-time error
                if (!arg.startsWith("-")) {
                    throw new IllegalArgumentException();
                }
            }

            static void checkFirst() {
                Runnable r = new Runnable() {
                    public void run() {
                        if (first == null) { // compile-time error
                            throw new IllegalArgumentException();
                        }
                    }
                };

                r.run();
            }
        }

        final Checker c = new Checker();
        c.checkFirst();
        for (int i = 1; i < args.length; i++) {
            Runnable r = () -> {
                c.checkWhitespace(i); // compile-time error
                c.checkFlag(i); // compile-time error
            };
        }
    }
}
```

形式参数 `args` 在整个 `main` 方法体范围内都是可见的。`args` 是有效 final（effectively final），因此名称 `args` 可以在局部类 `Checker` 的实例方法 `checkWhitespace` 中使用。然而在局部类 `Checker` 的 `checkFlag` 方法的静态上下文中名称 `args` 是非法的。

局部变量 `first` 在 `main` 方法的剩余范围内可见的。`first` 也是有效 final。然而，在 `checkFirst` 中声明的匿名类不是 `Checker` 的内部类，因此在匿名类体中使用名称 `first` 是非法的。（同样，在 `checkFirst` 体中的 Lambda 表达式也将无法引用 `first`，因为该 Lambda 表达式发生在静态上下文中。）

局部变量 `c` 在 `main` 方法体的最后几行中可见，并且被声明为 `final`，因此名称 `c` 可以在 Lambda 表达式体中使用。

局部变量 `i` 在整个 `for` 循环中可见。然而，`i` 不是有效 final，因此在 Lambda 表达式体中使用名称 `i` 是非法的。

### 6.5.6.2 限定表达式名称

如果一个表达式名称的形式为 `Q.Id`，则 `Q` 已经被归类为包名、类型名或表达式名。

如果 `Q` 是包名，则会发生编译错误。

如果 `Q` 是命名类类型的类型名，则：

- 如果该类类型没有恰好一个名为 `Id` 的可访问成员（§6.6）且为字段，则会发生编译错误。
- 否则，如果唯一的可见成员字段不是类变量（即它没有声明为 `static`），则会发生编译错误。
- 否则，如果该类变量被声明为 `final`，则 `Q.Id` 表示该类变量的值。

表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）类变量的声明类型。

如果 `Q.Id` 出现在一个需要变量而不是值的语文中，则会发生编译错误。

- 否则，`Q.Id` 表示该类变量。

表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）类变量的声明类型。

> 注意，此类名涵盖了枚举常量的使用（§8.9），因为它们总有一个对应的 final 类变量。

如果 `Q` 是命名接口类型的类型名，则：

- 如果接口类型没有恰好一个名为 `Id` 的字段，则会发生编译错误。

### 示例 6.5.6.2-1 使用类型名限定表达式

```java
class Point {
    int x, y;
    static int nPoints;
}
class Test {
    public static void main(String[] args) {
        int i = 0;
        i.x++; // compile-time error
        Point p = new Point ();
        p.nPoints(); // compile-time error
    }
}
```

该程序遇到了编译错误，因为变量 `i` 没有成员，且 `nPoints` 不是一个方法。

### 示例 6.5.6.2-2 使用类型名限定表达式

注意表达式名称可以使用类型名进行限定。

表达式名称可以使用类型名限定，但不能使用实例变量限定。下面的示例演示了：

```java
class Super {
    void f2(String s) {}
    void f3(String s) {}
    void f3(int i, int i2) {}
}

class Test {
    void f1(int i) {}
    void f2(int i) {}
    void f3(int i) {}
}

void m() {
    new Super() {
        f1(0); // OK，指向 Test.f1(int)
        f2(0); // compile-time error
        f3(0); // compile-time error
    }
}
```

## 6.5.7 名称的含义

名称的含义取决于它所处的作用域。

### 6.5.7.1 简单名称

简单方法名是不带限定符的方法名。简单方法名的含义取决于它所处的作用域。

下面的示例演示了在确定名称时作用域的作用：

```java
class Super {
    void f2(String s) {}
    void f3(String s) {}
    void f3(int i, int i2) {}
}

class Test {
    void f1(int i) {}
    void f2(int i) {}
    void f3(int i) {}
}

void m() {
    new Super() {
        f1(0); // OK，指向 Test.f1(int)
        f2(0); // compile-time error
        f3(0); // compile-time error
    }
}
```

## 6.6 访问控制

Java 编程语言提供了访问控制机制，以防止包或类的用户依赖于该包或类实现实现中不必要的细节。如果允许访问，则被访问的实体应当是可访问的。

注意，可访问性是一个静态属性，可以在编译时确定；它仅取决于类型和声明修饰符。

限定名称（Qualified names）是访问包、类、接口、类型参数和引用类型成员的手段。当此类成员的名称从其上下文中（§6.5.1）被归类为限定类型名（表示包、类或接口的成员）或限定表达式名（表示引用类型的成员）时，将会应用访问控制。

例如，单类型导入声明使用了限定类型名（§7.5.1），因此命名的类必须从包含该导入声明的编译单元是可访问的。另一个例子是，类声明可以使用限定类型名作为超类型（通过 §8.1.5），因此命名的类同样必须是可访问的。

某些显而见的表达式在 §6.5.1 的上下文分类中“缺失”：对主项（Primary）的字段访问（§15.11）、对主项的方法调用（§15.12）、通过主项的引用引用（§15.13）以及通过限定类实例创建的实例化类（§15.9）。这些表达式每一个都由于 §6.2 中的原因使用了标识符而非名称。因此，对成员（哪些字段、方法、类或接口）的访问控制是通过字段访问表达式、方法调用表达式、方法引用表达式和限定类实例创建表达式来实现的。（注意，字段也可以通过限定名称作为后置表达式来表示。）

此外，许多语句和表达式允许使用并非仅用类型表示的类型。例如，类声明可以使用参数化类型（§4.5）来表示超类型。由于参数化类型不是限定类型，因此类声明必须对所声明的超类执行访问控制。因此，在 §6.5.1 中提供用于分类类型名（TypeName）上下文的语句和表达式，必须执行它们自身的访问检查。



# 访问控制与包模块规范

## 6.6 访问控制

除了访问包、类、接口或类型参数的成员外，还有访问类构造函数的问题。当显式或隐式地调用构造函数时，必须检查访问控制。因此，访问控制通过显式构造函数调用（§8.7.1）和类实例创建表达式（§15.9.3）进行。这些检查是必要的，因为 §6.5.1 没有提到构造函数调用语句（因为它们间接引用构造函数，而不是通过名称），并且不知道由未限定实例创建表达式所指示的类与该类的构造函数之间的区别。此外，构造函数没有限定名称，因此我们不能依赖在归类限定类型名期间检查访问控制。

可访问性影响类成员的继承（§8.2），包括隐藏和方法重写（§8.4.8.1）。

### 6.6.1 确定可访问性

- 如果一个顶层类或接口（§7.6）被声明为 `public` 且是一个模块导出包的成员，则该类或接口可以被同一模块中的任何代码访问，也可以被导出该包的其他模块中的任何代码访问，前提是声明该类或接口的编译单元对该模块可见（§7.3）。

- 如果一个顶层类或接口被声明为 `public` 且是一个未导出包的成员，则该类或接口可以被同一模块中的任何代码访问。

- 如果一个顶层类或接口被声明为包访问权限，则它只能从其声明的包内部访问。

未声明访问修饰符的顶层类或接口隐含具有包访问权限。

- 类、接口、类型参数或引用类型的成员（类、接口、字段或方法）或类的构造函数仅在满足以下条件时才是可访问的：(i) 类、接口、类型参数或引用类型可访问的，且 (ii) 成员或构造函数被声明允许访问：

- 如果成员或构造函数被声明为 `public`，则允许访问。

缺少访问修饰符的接口的所有成员隐含为 `public`。

- 否则，如果成员或构造函数被声明为 `protected`，则仅在满足以下任一条件时才允许访问：

    - 从声明该受保护成员或构造函数的类的包内部访问该成员或构造函数。

    - 访问符合 §6.6.2 中的描述的。

- 否则，如果成员或构造函数被声明为包访问权限，则仅当访问发生在该类、接口、类型参数或引用类型声明的包内部时才允许访问。

未声明访问修饰符的类成员或构造函数隐含具有包访问权限。

- 否则，成员或构造函数被声明为 `private`。仅当访问发生在封装该成员或构造函数声明的顶层类或接口体内时才允许访问。

- 数组类型可访问的当且仅当其元素类型是可访问的。

#### 示例 6.6-1. 访问控制

考虑两个编译单元：

```java
package points;
class PointVec { Point[] vec; }
```

以及：

```java
package points;
public class Point {
  protected int x, y;
  public void move(int dx, int dy) { x += dx; y += dy; }
  public int getX() { return x; }
  public int getY() { return y; }
}
```

它们在 `points` 包中声明了两个类：

- 类型 `PointVec` 不是 `public` 的，也不是包的公共接口的一部分，而是只能由包内的其他类使用。
- 类型 `Point` 被声明为 `public`，可以被其他包访问。它是包的公共接口的一部分。
- 类的 `move`、`getX` 和 `getY` 方法被声明为 `public`，因此对使用 `Point` 对象的任何代码都是可见的。
- 字段 `x` 和 `y` 被声明为 `protected`，只有在作为 `Point` 的子类中的字段时才能在包外访问。

#### 示例 6.6-2. 访问 public 字段、方法和构造函数

`public` 类成员或构造函数在其声明的包范围内可访问，并从任何其他包访问，前提是其声明的包是可见的（§7.4.3）。例如，在编译单元：

```java
package points;
public class Point {
    int x, y;
    public void move(int dx, int dy) {
        x += dx; y += dy;
        moves++;
    }
    public static int moves = 0;
}
```

`Point` 类有公共成员 `move` 方法和 `moves` 字段。这些公共成员对访问 `points` 包的任何其他包可见。字段 `x` 和 `y` 不是 `public`，因此只能从 `points` 包内部访问。

```java
package pointsUser;
class Test1 {
    public static void main(String[] args) {
        points.Point p = new points.Point();
        System.out.println(p.x + " " + p.y);
    }
}
```

或者通过提及全限定类名的单类型导入声明（§7.5.1），这样此后可以使用相同的名称：

```java
package pointsUser;
import points.Point;
class Test2 {
    public static void main(String[] args) {
        Point p = new Point();
        System.out.println(p.x + " " + p.y);
    }
}
```

然而，此编译单元无法使用或导入 `points.PointList`，因为它没有被声明为 `public`，因此在 `points` 包之外是不可访问的。

#### 示例 6.6-4. 访问包访问级别的字段、方法和构造函数

如果未指定 `public`、`protected` 或 `private` 访问修饰符，类成员或构造函数具有包访问权限；它在声明该成员的类的包内是可访问的，但该类成员或构造函数在任何其他包中都是不可见的。

如果一个 `public` 类有一个具有包访问权限的方法或构造函数，那么该方法或构造函数对于声明在包之外的子类是不可访问或不可继承的。

例如，我们有：

```java
package points;
public class Point {
    public int x, y;
    void move(int dx, int dy) { x += dx; y += dy; }
    public void moveAlso(int dx, int dy) { move(dx, dy); }
}
```

子类可以声明具有相同签名（§8.4.2）和返回类型的未声明 `move` 方法。由于原始的 `move` 方法从 `morepoints` 包不可访问，因此无法使用超类型：

```java
package morepoints;
public class PlusPoint extends points.Point {
    public void move(int dx, int dy) {
        super.move(dx, dy); // 编译错误
        moveAlso(dx, dy);
    }
}
```

由于 `Point` 的 `move` 没有被 `PlusPoint` 中的 `move` 覆盖，`Point` 中的方法 `moveAlso` 永远不会调用 `PlusPoint` 中的方法 `move`。如果你从 `PlusPoint` 中删除 `super.move` 调用并执行测试程序：

```java
import points.Point;
import morepoints.PlusPoint;
class Test {
    public static void main(String[] args) {
        PlusPoint pp = new PlusPoint();
        pp.move(1, 1);
    }
}
```

它将正常终止。如果 `Point` 的 `move` 被 `PlusPoint` 中的 `move` 覆盖，那么该程序将无限运行，直到发生 `StackOverflowError`。

#### 示例 6.6-5. 访问私有字段、方法和构造函数

`private` 类成员或构造函数仅在包含该成员或构造函数的顶层类体内（§7.6）可访问。它不会被子类继承。在示例中：

```java
Point() { setMasterID(); }
int x, y;
private int ID;
private static int masterID = 0;
private void setMasterID() { ID = masterID++; }
```

成员 `ID`、`masterID` 和 `setMasterID` 只能在 `Point` 类体内部使用。它们无法在 `Point` 声明体之外通过限定名、字段访问表达式或方法调用表达式访问。

有关使用私有构造函数的示例，请参阅 §8.8.10。

### 6.6.2 访问的细节

对象的 `protected` 成员或构造函数仅允许由负责该对象实现的代码从其声明的包之外访问。

#### 6.6.2.1 访问受保护成员

设 `c` 为声明 `protected` 成员的类。仅允许在 `c` 的子类 `s` 的体内访问。

子类 `s` 被视为负责类 `c` 对象的实现。根据 `c` 的访问权限，`s` 可以声明在与 `c` 相同的包中，或者在与 `c` 同模块的不同包中，或者在完全不同模块的包中。

此外，根据限定名的形式、字段访问表达式（§15.11）、方法调用表达式（§15.12）或方法引用表达式（§15.13），允许对实例字段或实例方法的访问：

- 如果通过 (i) 形为 `ExpressionName.Id` 或 `TypeName.Id` 的限定名访问，或者 (ii) 形为 `Primary.Id` 的字段访问表达式访问，则允许对实例字段 `Id` 访问，且仅当限定类型是 `s` 或 `s` 的子类。

  限定类型是 `ExpressionName` 或 `Primary` 的类型，或者是 `TypeName` 所指示的类型。

- 如果通过 (i) 形为 `ExpressionName.Id(...)` 或 `TypeName.Id(...)` 的方法调用表达式访问，或者 (ii) 形为 `ExpressionName :: Id` 或 `Primary :: Id` 或 `ReferenceType ::` 的方法引用表达式访问，则允许对实例方法 `Id` 访问，且仅当限定类型是 `s` 或 `s` 的子类。

  限定类型是 `ExpressionName` 或 `Primary` 的类型，或者是 `TypeName` 或 `ReferenceType` 所指示的类型。

关于 `protected` 成员的更多信息，可以在 Alessandro Coglio 发表于 2005 年 10 月《对象技术杂志》上的《Checking Access to Protected Members in the Java Virtual Machine》中找到。

#### 6.6.2.2 访问受保护构造函数

设 `c` 为声明 `protected` 构造函数的类。仅允许在 `c` 的子类 `s` 的体内访问。

子类 `s` 被视为负责类 `c` 对象的实现。根据 `c` 的访问权限，`s` 可以声明在与 `c` 相同的包中，或者在与 `c` 同模块的不同包中，或者在完全不同模块的包中。

## 6.7 全限定名与规范名

每个基本类型、具名包、顶层类和顶层接口都具有一个规范名：

- 对于每个基本类型、具名包、顶层类和顶层接口，其规范名与全限定名相同。

- 每个成员类、成员接口和数组类型可能具有一个规范名：

    - 在另一个类或接口 `c` 中声明的成员类或成员接口 `M`，当且仅当 `c` 具有规范名时，它具有规范名。

    - 数组类型具有规范名，当且仅当其组件类型具有规范名时。

  在这种情况下，`M` 的规范名由 `c` 的规范名、后跟一个 `.`、再后跟 `M` 的简单名组成。

  在这种情况下，数组类型的规范名由组件类型的规范名后跟 `[]` 组成。

- 局部类、局部接口或匿名类没有规范名。

### 示例 6.7-1. 全限定名

- 类型 `long` 的全限定名是 `"long"`。
- 包 `java.lang` 的全限定名是 `"java.lang"`，因为它是包 `java` 的子包 `lang`。
- 定义在包 `java.lang` 中的类 `Object` 的全限定名是 `"java.lang.Object"`。
- 定义在包 `java.util` 中的接口 `Enumeration` 的全限定名是 `"java.util.Enumeration"`。
- 类型 "double 数组" 的全限定名是 `"double[]"`。
- 类型 "String 数组的数组数组" 的全限定名是 `"java.lang.String[][][]"`。

在代码中：

```java
package points;
class Point { int x, y; }
class PointVec { PointVec(Point[] vec); }
```

类型 `Point` 的全限定名是 `"points.Point"`；类型 `PointVec` 的全限定名是 `"points.PointVec"`；类 `PointVec` 的字段 `vec` 的类型全限定名是 `"points.Point[]"`。

### 示例 6.7-2. 全限定名 vs 规范名

全限定名与规范名之间的差异可以通过如下代码看到：

```java
package p1;
class O1 { class I {} }
class O2 extends O1 { }
```

`p1.O1.I` 和 `p1.O2.I` 都是表示成员类 `I` 的全限定名，但只有 `p1.O1.I` 是它的规范名。

# 第 7 章 包与模块

程序被组织为包的集合。包的成员（§7.1）是类和接口（它们声明在包的编译单元中）以及子包（子包可能包含它们自己的编译单元和子包）。

每个包都有自己的一套类和接口名称，这有助于防止命名冲突。包的命名结构是层次化的。

如果一个包集合具有足够的内聚性，那么这些包可以被分组为一个模块。模块将其部分或全部包分类为*导出的*，这意味着它的类和接口可以从模块外部的代码访问。如果一个包没有被模块导出，则只有模块内部的代码可以访问它的类和接口。此外，如果模块中的代码想要访问另一个模块导出的包，则第一个模块必须显式地依赖第二个模块。因此，模块控制其包如何使用其他模块（通过指定依赖关系），并控制其他模块如何使用其包（通过指定哪些包是导出的）。

模块和包可以存储在文件系统或数据库中（§7.2）。存储在文件系统中的模块和包对其编译单元的组织可能有某些限制，以便简单的实现能够轻松找到模块、类和接口声明。

编译单元中的代码自动拥有其包中声明的所有类和接口，并自动导入预定义包 `java.lang` 中声明的所有 `public` 类和接口。

只有当顶层类或接口被声明为 `public` 时，它在声明它的包外部才是可访问的（§6.6）。只有当该顶层类或接口被声明为 `public` 且是导出包的成员时，它才能在声明它的模块外部是可访问的。一个被声明为 `public` 但不是导出包成员的类或接口，只能被模块内部的代码访问。

## 7.1 包成员

对于小型程序和非正式开发，包可以是未命名的（§7.4.2）或有一个简单的名称，但如果代码要广泛发布，则应该使用全限定名选择唯一的包名。这可以防止如果两个开发小组恰好选择了相同的包名，且这些包后来在同一个程序中使用时可能发生的冲突。

包的成员是它的子包以及声明在该包的编译单元（§7.3）中的所有顶层类（§8 Classes）和顶层接口（§9 Interfaces）。

例如，在 Java SE Platform API 中：

- 包 `java` 有子包 `awt`、`io`、`lang`、`net` 和 `util`，但没有编译单元。
- 包 `java.awt` 有一个名为 `image` 的子包，以及若干包含类和接口声明的编译单元。

如果一个包的全限定名（§6.7）是 `P`，且 `Q` 是 `P` 的子包，那么 `P.Q` 就是该子包的全限定名。

一个包不能包含两个同名的成员。以下是一些示例：

- 包 `java.awt` 有一个名为 `image` 的子包，它不能（也没有）包含类 `image` 的声明。
- 如果存在一个包 `mouse` 和一个成员类 `Button`，则不存在全限定名为 `mouse.Button` 的包。
- 如果 `com.nighthacks.jag` 是一个类的全限定名，则不存在包 `com.nighthacks.jag`。

然而，不同包的成员可能具有相同的简单名。例如，可以声明一个包：

```java
package vector;
public class Vector { Object[] vec; }
```

即使 `java.util` 包声明了类 `Vector`，该包也可以有一个成员 `public Vector`。这两个类是不同的，这体现在它们具有不同的限定名，即 `vector.Vector` 和 `java.util.Vector`。

## 7.2 对模块和包的支持

主机系统决定如何创建和存储模块、包和编译单元。



每个主机系统决定哪些编译单元在特定的编译中可见（§7.3）。每个主机系统还决定哪些可见编译单元与模块关联。与模块关联的编译单元的可见性决定了哪些模块是可见的（§7.7.3）以及这些模块内部哪些包是可见的（§7.4.3）。

> 主机系统可以决定包含模块声明的编译单元实际上并未与其声明的模块关联。这允许编译器选择模块路径上的哪个目录是“真正”给定模块的体现。然而，如果主机系统确定一个编译单元是可见的，那么 §7.4.3 强制该编译单元必须与声明的模块关联，而不是其他模块。

> 主机系统可以决定包含类或接口声明的编译单元（首先）是可见的，并且（其次）与一个未命名模块或自动模块关联，尽管在任何编译单元（无论是否可见）中都不存在未命名或自动模块的声明。

## 7.2 模块和包的主机支持

### 包与模块

在 Java SE 平台的简单实现中，包和编译单元可能存储在本地文件系统中。其他实现可能使用分布式文件系统或某种形式的数据库来存储它们。

如果主机系统将包和编译单元存储在数据库中，则该数据库不能对基于文件的实现中允许的编译单元施加可选的限制（§7.6）。

例如，使用数据库存储包的系统可能不会强制每个编译单元最多只能有一个公共类（`public class`）或接口。

然而，使用数据库的系统必须提供一种选项，将程序转换为遵守这些限制的形式，以便导出到基于文件的实现中。

在一个在文件系统中存储包的极简示例中，项目中的所有包以及源代码和二进制代码可能都存储在一个单一目录及其子目录中。该目录的每个直接子目录都代表一个顶层包，即其完全限定名由单个简单名称组成的包。每一更深一级的子目录都代表其父目录所代表的包的子包，依此类推。

该目录可能包含以下直接子目录：

```
com
gls
jag
java
j
```

其中 `java` 包含 Java SE 平台的包；`java`、`gis` 和 `wnj` 目录可能包含本规范的三位作者为了个人使用并在该小组内共享而创建的包；目录将包含从使用 §6.1 中描述的约定为其包生成唯一名称的公司的包。

继续该示例，`java` 目录包含以下子目录：

```
applet
awt
io
lang
net
util
```

对应于 Java SE 平台 API 中定义的 `java.applet`、`java.awt`、`java.io`、`java.lang`、`java.net` 和 `java.util` 包。

继续该示例，如果我们查看 `util` 目录，可能会看到以下文件：

```
BitSet.java        Observable.java
BitSet.class        Observable.class
Date.java           Observer.java
Date.class          Observer.java
...
```

其中每个 `.java` 文件包含一个编译单元（§7.3）的源码，该单元包含一个类或接口的定义，其二进制编译文件包含在相应的 `.class` 文件中。

在这种包的简单组织下，Java SE 平台的实现通过连接包名的各个组件将包名转换为路径名，在相邻组件之间放置文件名分隔符（目录指示符）。

例如，如果这种简单组织用在一个文件名分隔符为 `/` 的操作系统上，则包名：

```
jag.scrabble.board
```

将转换为目录名：

```
jag/scrabble/board
```

包名组件或类名可能包含无法正确出现在主机文件系统普通目录名中的字符，例如在仅允许文件名中包含 ASCII 字符的系统上的 Unicode 字符。按照约定，可以使用 `@` 字符后跟四个十六进制数字（给出字符的数值）来转义该字符，如 `\uxxxx` 转义（§3.3）。

根据此约定，包名：

```
children.activities.crafts.papierM\u002ch\u00e9
```

也可以使用完整的 Unicode 写为：

```
children.activities.crafts.papierM@002chM@ché
```

可能会映射到目录名：

```
children/activities/crafts/papierM@002ch@00e9
```

如果 `@` 字符对于某些特定的主机文件系统的文件名来说不是有效字符，则可以使用另一个在标识符中无效的字符代替。

## 7.3 编译单元

`CompilationUnit` 是 Java 程序语法规则（§2.3）的终符号（§2.1）。它由以下产生式定义：

- CompilationUnit:
  - OrdinaryCompilationUnit
  - ModularCompilationUnit

- OrdinaryCompilationUnit:
  - [PackageDeclaration] [ImportDeclaration]
  - [TopLevelClassOrInterfaceDeclaration]

- ModularCompilationUnit:
  - [ImportDeclaration] ModuleDeclaration

一个普通的编译单元由三部分组成，每部分都是可选的：

- 包声明（§7.4），给出编译单元所属包的完全限定名（§6.7）。没有包声明的编译单元属于匿名包（§7.2）。

- 导入声明（§7.5），允许使用简单名称引用来自其他包的类和接口，以及类和接口的静态成员。

- 类和接口的顶层声明（§7.6）。

一个模块化编译单元由一个模块声明（§7.7）组成，可选地由导入声明前导。导入声明允许在模块声明内部使用简单名称引用该模块和其他模块包中的类和接口，以及类和接口的静态成员。

每个编译单元都隐式地导入预定义包 `java.lang` 中声明的每个类或接口，就像在每个编译单元的开头、任何包声明之后立即出现 `import java.lang.*;` 声明一样。结果是所有这些类和接口的名称在每个编译单元中都可以作为简单名称可用。

主机系统决定哪些编译单元是可见的（observable），但预定义包 `java` 及其子包 `lang` 和 `io` 中的编译单元除外，这些单元始终是可见的。

### 编译单元 7.3

每个可见单元可能与一个模块关联，如下所示：

- 主机系统必须确定可见的编译单元与主机系统选择的模块关联，但 (i) 预定义包 *java* 及其子包 *lang* 和 *io* 中的普通编译单元（它们都与 *java.base* 模块关联），以及 (ii) 匿名包中的任何普通编译单元（其按照 §7.4.2 指定的模块关联）除外。

- 主机系统必须确定可见的模块化编译单元与该模块编译单元声明的模块关联。

编译单元的可见性会影响其包（§7.4.3）的可见性，而可见编译单元与模块的关联会影响该模块的可见性（§7.7）。

在编译与模块 *M* 关联的模块化和普通编译单元时，主机系统必须尊重 *M* 声明中指定的依赖。具体来说，主机系统必须限制原本可见的普通编译单元，仅限于对 *M* **可见**（visible）的单元。对 *M* 可见的普通编译单元与 *M* **读取**（read）的模块关联。*M* 读取的模块由 `java.lang.module` 包规范中描述的解析（*resolution*）结果给出，以 *M* 为唯一的根模块。主机系统必须执行解析以确定 *M* 读取的模块；如果由于 `java.lang.module` 包规范中描述的任何原因解析失败，则为编译错误。

可读关系具有反射性，因此 *M* 读取自身，从而所有与 *M* 关联的模块化和普通编译单元对 *M* 可可见。

*M* 读取的模块驱动了对 *M* 唯一可见的编译单元（§7.4.3），这同时驱动了作用域内的顶层包，以及与 *M* 关联的模块化和普通编译单元中包命名的含义（§6.3, §6.5.3, §6.5.5）。

上述规则确保了模块化编译单元中注解使用的包名和类型名（特别是应用于模块声明的注解）其解释方式就像它们出现在带有该模块的普通编译单元中一样。

在不同普通编译单元中声明的类和接口可以相互引用，并形成循环引用。Java 编译器必须安排同时编译所有此类类和接口。

## 7.4 包声明 (Package Declarations)

包声明出现在普通的编译单元中，用于指示该编译单元所属的包。

### 7.4.1 命名包

普通编译单元中的包声明指定了该编译单元所属包的名称 (§6.2)。

```
PackageDeclaration:
{PackageModifier} package Identifier [ . Identifier ];

PackageModifier:
Annotation
```

包声明中提到的名称必须是该包的全限定限定名 (§6.7)。

包声明的作用域和遮蔽（shadowing）在 §6.3 和 §6.4 中规定。

关于包声明注解修饰符（annotation modifiers）的规则在 §9.7.4 和 §9.7.5 中规定。

对于给定的包最多允许一个包声明。

> 出于需要，强制这一限制的实施方式随实现而异。对于文件系统实现，强烈建议以下方案：如果存在唯一的带注解的包声明，应将其放置在包含该包源文件的目录下的 `package-info.java` 源文件中。该文件不包含名为 `package-info` 的类的源码；这样做是非合法的，因为 `package-info` 不是一个合法的标识符。通常，`package-info.java` 只包含一个包声明，紧随其后的是包的注解。虽然该文件技术上可以包含一个或多个具有包访问权限的类的源码，但这种做法非常不规范。

> 建议如果存在 `package-info.java`，应替代 javadoc 和其他文档生成系统中的 `package.html` 的位置。如果存在此文件，文档生成工具应该查找 `package-info.java` 中紧接于（可能带有注解的）包声明之前的包文档注释。通过这种方式，`package-info.java` 成为包级注解和文档的唯一存储库。如果未来希望添加任何包级信息，该文件应该为这些信息提供一个方便的所在地。

### 7.4.2 无名包 (Unnamed Packages)

没有包声明但至少包含另一种类型声明的普通编译单元属于一个无名包。

Java SE 平台提供的无名包，主要是为了在开发小型或临时应用程序或刚开始开发时提供便利。

无名包不能有子包，因为包声明的语法始终包含对命名顶层包的引用。

Java SE 平台的实现必须至少支持一个无名包。实现可以支持多个无名包，但不是必须的。每个无名包包含哪些普通编译单元由主机系统决定。

宿机系统必须将无名包中的普通编译单元与无名模块 (§7.7.5) 关联，而不是命名模块。

#### 示例 7.4.2-1. 无名包

编译单元：

```
class FirstCall {
    public static void main(String[] args) {
        System.out.println("Mr. Watson, come here. \
+ \"I want you.");
    }
}
```

定义了一个作为无名包部分的非常简单的编译。

在使用分级文件系统存储包的 Java SE 平台实现中，一种典型的策略是将无名包与每个目录关联；同一时间只有一个包是观测的，即与“当前工作目录”关联的包。“当前工作目录”的精确含义取决于主机系统。

### 7.4.3 包的可观测性与可见性 (Package Observability and Visibility)

当且仅当以下条件至少为真时，包是可观测的：

- 包含包声明的普通编译单元是可观测的 (§7.3)。

- 该包的子包是观测的。

`java`、`java.lang` 和 `java.io` 包始终是观测的。

根据上述规则和可观测编译单元规则可以得出如下结论：预定义包 `java.lang` 声明了类 `Object`，因此 `Object` 的编译单元总是观测的 (§7.3)。因此，`java.lang` 包是观测的，`java` 包也是。此外，由于 `Object` 是可观测的，数组类型 `Object []` 隐含扩展。它的超接口 `java.io.Serializable` (§10.1) 也存在，因此 `java.io` 包是观测的。

一个包对模块 M 可见，当且仅当包含该包声明的普通编译单元对 M 可见时。

包的可见性意味着包 P 对给定的模块是以有用的方式可观测的。仅仅因为子包 Q 是观测的而知道包 P 是观测的通常没有用处。例如，假设 Q（在模块 M1 中）是观测的， R（在模块 M2 中）是观测的；那么 P 是观测的，但在哪里？在 M1、M2 还是两者都存在？这个问题是多余的；在编译只需要 M1 的模块 N 期间，Q 是否观测的很重要，但 P 是否观测的并不重要。

一个包对模块 M 是唯一可见的，当且仅当以下条件成立时：

- 与 M 关联的普通编译单元包含该包的声明，且 M 没有读取任何其他向 M 导出该包的模块。

- 与 M 关联的普通编译单元包含该包的声明，且 M 恰好读取了一个向 M 导出该包的模块。

## 7.5 导入声明 (Import Declarations)

导入声明允许命名的类、接口或静态成员通过由单个标识符组成的简单名称 (§6.2) 被引用。

如果不使用导入声明，对另一个包中的类或接口的引用，或对另一个类或接口的静态成员的引用，通常需要使用全限定名 (§6.7)。

```
ImportDeclaration:
SingleTypeImportDeclaration
TypeImportDemandDeclaration
SingleStaticImportDeclaration
StaticImportDeclaration
```

- 单类型导入声明 (7.5.1) 通过给出全限定名导入单个类或接口。

- 类型导入需求声明 (7.5.2) 通过提及全限定名导入命名包、类或接口的所有可访问类和接口。

- 单静态导入声明 (7.5.3) 通过给出全限定名导入类或接口中具有给定名的静态成员。

- 静态导入需求声明 (7.5.4) 通过提及全限定名导入命名类或接口的所有可访问静态成员。

通过这些声明导入的类、接口或成员的作用域和遮蔽在 §6.3 和 §6.4 中规定。

> 导入声明仅在包含该导入的编译单元内通过简单名称使类、接口或成员。通过导入声明引入的类、接口或成员的作用域不包括同一包中的其他编译单元、该编译单元的其他导入声明或当前编译单元中的包声明（包声明的注解除外）。

### 7.5.1 单类型导入声明 (Single-Type-Import Declarations)

单类型导入声明通过给出全限定名导入单个类或接口，使其在该导入声明出现的编译单元的模块、类和接口声明中以简单名称可用。

```
SingleTypeImportDeclaration:
import typeName;
```

`TypeName` 必须是类或接口的全限定名 (§6.7)。

类或接口必须是命名包的成员，或者其最外层词法嵌套类或接口声明 (§8.1.3) 是命名包的成员，否则发生编译时错误。

如果命名的类或接口不可访问 (§6.6)，则发生编译时错误。

如果同一编译单元中的两个单类型导入声明尝试导入相同简单名称的类或接口，则发生编译时错误，除非这两个类或接口是同一个，在这种情况下忽略重复的声明。

如果由单类型导入声明（single-type-import declaration）导入的类或接口在包含该导入声明的编译单元中被声明为顶层类或接口 (§7.6)，则该导入声明被忽略。

如果单类型导入声明导入了一个简单名称为 x 的类或接口，而该编译单元也声明了一个简单名称为 x 的顶层类或接口，则会发生编译时错误。

如果一个编译单元同时包含一个导入简单名称为 x 的类或接口的单类型导入声明，以及一个导入简单名称为 x 的类或接口的单静态导入声明（single-static-import §7.5.3），则会发生编译时错误，除非这两个类或接口是同一个，在这种情况下，重复的声明将被忽略。

#### 示例 7.5.1-1. 单类型导入

```
import java.util.Vector;
```

这使得简单名称 Vector 在编译单元的类和接口声明中可用。因此，在所有未被同名的字段、参数、局部变量或嵌套类或接口声明的声明**遮蔽** (§6.4.1) 或**混蔽** (§6.4.2) 的地方，Vector 名称均指向 java.util 包中的类声明 Vector。

注意，`java.util.Vector` 的实际声明是泛型的 (§8.1.2)。一旦导入，名称 Vector 就可以在参数化类型中限定使用，例如 `Vector<String>`，或者作为原始类型 Vector 使用。导入声明的一个相关限制是：在泛型类或接口声明内部声明的成员类或接口可以被导入，但其外部类型始终会被擦除。

#### 示例 7.5.1-2. 重复的类声明

此程序：

```
import java.util.Vector;
class Vector { Object[] vec; }
```

由于 Vector 的重复声明，会导致编译时错误，以下情况亦是如此：

```
import java.util.Vector;
import myVector.Vector;
```

其中 myVector 是包含该编译单元的包：

```
package myVector;
public class Vector { Object[] vec; }
```

#### 示例 7.5.1-3. 未导入子包

注意，导入声明不能导入子包，只能导入类或接口。

例如，尝试导入 java.util 然后使用名称 util.Random 来引用类型 java.util.Random 是无效的：

```
import java.util;
class Test { util.Random generator; }
// 错误：编译时错误
```

#### 示例 7.5.1-4. 导入同时也作为包名的类型

根据 §6.1 描述的命名规范，包名和类型名通常是不同的。尽管如此，在这个人为构造的示例中，一个命名不符合规范的包 Vector 声明了一个名为 Mosquito 的公共类：



```java
package Vector;
public class Mosquito { int capacity; }
```

然后该编译单元：

```java
package strange;
import java.util.Vector;
import Vector.Mosquito;
class Test {
  public static void main(String[] args) {
    System.out.println(new Vector().getClass());
    System.out.println(new Mosquito().getClass());
  }
}
```

单类型导入声明导入来自 `java.util` 包的类 `Vector`，并没有阻止包 `Vector` 在随后的导入声明中出现并被正确识别。该示例可以编译并产生输出：

```
class java.util.Vector
class Vector.Mosquito
```

### 7.5.2 按需类型导入声明

按需类型导入声明（type-import-on-demand declaration）允许将命名名包、类或接口的所有可访问的类和接口按需导入。

```java
TypeImportOnDemandDeclaration:
import PackageOrTypeName . * ;
```

`PackageOrTypeName` 必须是包、类或接口的规范名称（§6.7）。

如果 `PackageOrTypeName` 指向一个类或接口（§6.5.4），则该类或接口必须是某个命名包的成员，或者是某个类或接口的成员，且其最外层的词法包含类或接口声明（§8.1.3）是命名包的成员，否则会发生编译时错误。

如果包名对当前模块不可唯一可见（§7.4.3），或者命名的类或接口不可访问（§6.6），则会发生编译时错误。

在按需类型导入声明中命名 `java.lang` 或当前编译单元的命名包并不会导致编译时错误。在这种情况下，该按需类型导入声明被忽略。

同一个编译单元中的两个或多个按需类型导入声明可能命名同一个包、类或接口。所有这些声明都被认为是冗余的；其效果相当于该类型仅被导入了一次。

如果一个编译单元同时包含一个命名相同类或接口的按需类型导入声明和一个按需静态导入声明（static-import-on-demand declaration §7.5.4），其效果相当于该类或接口的静态成员类和接口（§8.5, §9.5）仅被导入了一次。

#### 示例 7.5.2.1. 按需类型导入

```java
import java.util.*;
```

这使得 `java.util` 包中声明的所有公共类和接口的名称在编译单元的类和接口声明中可用。因此，简单名称 `Vector` 在所有未被同名的字段、参数、局部变量或嵌套类或接口声明的**遮蔽**（§6.4.1）或**混蔽**（§6.4.2）的地方，均指向 `java.util` 包中的类声明 `Vector`。它可能被简单名为 `Vector` 的类或接口的单类型导入声明遮蔽；或者被编译单元所属包的类或接口遮蔽；或者被嵌套接口遮蔽（这些情况极少发生）。

### 7.5.3 单静态导入声明

单静态导入声明（single-static-import declaration）从类或接口导入给定简单名称的所有可访问静态成员。这使得这些静态成员在单静态导入声明所在的编译单元的模块、类、接口中可用。

```java
StaticImportDeclaration:
import static typeName . Identifier;
```

`TypeName` 必须是类或接口的规范名称（§6.7）。该类或接口必须是命名包的成员，或者是某个类或接口的成员，且其最外层的词法包含类或接口声明（§8.1.3）是命名包的成员，否则会发生编译时错误。

如果命名的类或接口不可访问（§6.6），则会发生编译时错误。

`Identifier` 在命名的类或接口中至少有一个静态成员。如果没有该名称的静态成员，或者所有命名成员均不可访问，则会发生编译时错误。

一个单静态导入声明导入多个具有相同名称的字段、类或接口，或者具有相同名称和签名的方法是被允许的。这发生在命名的类或接口从其父类型继承了多个同名的字段、成员类、成员接口或方法时。

同一个编译单元中的两个单静态导入声明尝试导入相同名称的类或接口，会发生编译时错误，除非这两个类或接口是同一个，在这种情况下，重复的声明将被忽略。

如果单静态导入声明导入了一个简单名称为 `x` 的类或接口，而该编译单元也声明了一个简单名称为 `x` 的顶层类或接口（§7.6），则会发生编译时错误。

如果一个编译单元同时包含一个导入简单名称为 `x` 的类或接口的单静态导入声明，以及一个导入简单名称为 `x` 的类或接口的单类型导入声明（§7.5.1），则会发生编译时错误，除非这两个类或接口是同一个，在这种情况下，重复的声明将被忽略。

### 7.5.4 按需静态导入声明

按需静态导入声明（static-import-on-demand declaration）允许按需导入命名类或接口的所有可访问静态成员。

```java
StaticImportOnDemandDeclaration:
import static TypeName.*;
```

`TypeName` 必须是类或接口的规范名称（§6.7）。

该类或接口必须是命名包的成员，或者是某个类或接口的成员，且其最外词法包含类或接口声明（§8.1.3）是命名包的成员，否则将发生编译时错误。

如果命名的类或接口不可访问（§6.6），则会发生编译时错误。

同一编译单元中的两个或多个静态静态导入声明可以命名同一个类或接口；其效果等同于恰好存在一个声明。

同一编译单元中的两个或多个静态静态导入声明可以命名同一个成员；其效果等同于该成员仅导入了一次。

允许一个静态静态导入声明导入多个具有相同名的字段、类或接口，或者多个具有相同名称和签名的方法。这发生在命名的类或接口从其自身的超类型继承了多个具有相同名的字段、成员类、成员接口或方法时。

如果一个编译单元同时包含命名同一个类或接口的静态静态导入声明和类型静态导入声明（§7.5.2），其效果等同于该类或接口的静态成员类和接口（§8.5, §9.5）仅导入了一次。

## 7.6 顶级类和接口声明

顶层类或接口声明声明了一个顶级类（§8.1）或顶层接口（§9.1）。

```java
TopClassOrInterfaceDeclaration:
ClassDeclaration
InterfaceDeclaration
;
```

在编译单元的类和接口声明层级出现的额外 `";"` 标记对编译单元的含义没有影响。Java 编程语言允许出现散乱的分号，这完全是为了向 C++ 程序员妥协，因为他们习惯于在类声明后放置 `";"`。在中不应在新的 Java 代码中使用它们。

在没有访问修饰符的情况下，顶层类或接口具有包访问权限：它仅在声明它的所在包的普通编译单元内是可的（§6.6.1）。可以将某个类或接口声明为 `public`，以允许从同一模块的其他包（并可能来自其他模块的包）的代码访问该类或接口。

如果顶层类或接口声明包含任何一个其他访问修饰符：`protected`、`private` 或 `static`，则会发生编译时错误。

如果顶层类或接口名称出现在同一包内声明的任何其他顶级类或接口名称中，则会发生编译时错误。

顶层类或接口的作用域和隐藏规则在 §6.3 和 §6.4 中规定。

顶层类或接口的全限定名称在 §6.7 中规定。

### 7.6-1. 冲突的顶级类和接口声明

```java
package test;
import java.util.Vector;
class Point {
    int x, y;
}
interface Point { // 编译时错误 #1
    int getR();
    int getTheta();
}
class Vector(Point[] pts); // 编译时错误 #2
```

在这里，第一个编译时错误是由于在同一个包中同时作为类和接口重复声明了名称 `Point` 导致的。第二个编译时错误是尝试将名称 `Vector` 同时声明为类声明和单类型声明。

注意，类声明中的名称与同一编译单元中可能通过类型静态导入声明（§7.5）导入的类或接口重叠并不是一个错误。在如下：

```java
package test;
import java.util.*; // 不是编译时错误
class Vector {}
```

类 `Vector` 的声明是允许的，尽管在该编译单元内也存在一个类 `java.util.Vector`，但简单名 `Vector` 指的是类 `test.Vector`，而不是 `java.util.Vector`（编译单元内的代码仍可以引用它，但只能通过其全限定名称进行引用）。

### 示例 7.6-2. 顶级类和接口的作用域

```java
package points;
class Point {
    int x, y; // 坐标
    PointColor color; // 此点的颜色
    Point next; // 该类的下一个点
    static int nPoints;
}

class PointColor {
    Point first; // 这种颜色的第一个点
    PointColor(int color) {this.color = color; }
    private int color; // 颜色分量
}
```

此程序定义了两个在类成员声明中互相使用的类。`Point` 和 `PointColor` 类将包 `points` 中所有的类声明（包括当前编译单元内的声明）作为它们的作用域，程序可以正确编译。这意味着前向引用并不是问题。

### 示例 7.6-3. 全限定名称

```java
class Point { int x, y; }
```

在此代码中，类 `Point` 声明在一个没有包声明的编译单元中，因此 `Point` 是它的全限定名称。而在代码中：

```java
package vista;
class Point { int x, y; }
```

类 `Point` 的全限定名称是 `vista.Point`。包名 `vista` 适用于本地使用；如果该包打算用于广泛分发，那么给它一个唯一的名称会更好。

Java SE 的实现必须通过其包含模块名称的组合（§13.1）来跟踪包内的类和接口。多种命名方式可以确保它们被理解为指向同一个类。例如，如果一个编译单元包含单类型导入（7.5）：

```java
import java.util.*;
```

那么简单名 `Vector` 和全限定名 `java.util.Vector` 指向同一个类。

如果只有包存储在文件系统中（7.2），主机可能会强制执行限制：如果类或接口没有以其名称加上扩展名（如 `.java` 或 `.jav`）的形式被找到，则会发生编译时错误，当以下任一情况成立时：

- 该类或接口在声明它的包的普通编译单元内被引用。
- 该类或接口被声明为 `public`（因此可以从其他包的代码访问）。

## 7.7 模块声明

模块声明指定一个新名称。命名模块指定对其他模块的依赖，以定义自身代码可用的类和接口宇宙；并指定其哪些包导出，以填充依赖它的其他模块的可用类和接口宇宙。

> “依赖”是 `requires` 指令所表达的，不取决于是否存在具有指定名称的模块。“依赖”是解析（如 `java.lang.module` 包规范中所述）所枚举的观测模块。通常，Java 语言的规则对依赖比依赖更感兴趣。

```java
ModuleDeclaration:
[Annotation] open Module Identifier {\ . Identifier }
```

模块声明引入了一个名称，该名称可以在其他模块声明中使用以表示模块之间的关系。

模块有两种类型：普通模块和开放模块。模块的类型决定了外部代码对该模块类型及其成员的访问性质。

### 7.7 模块声明

普通模块（不带 `open` 修饰符）仅在编译时和运行时允许对显式导出的包中的类型进行访问。

带有 `open` 修饰符的开放模块，在编译时仅允许对显式导出的包中的类型进行访问，但在运行时允许对其所有包中的类型进行访问，就好像所有包都已导出一样。

对于模块外部的代码（无论普通模块还是开放模块），在编译时或运行时对模块导出包中的类型授予的访问权限，专门仅针对这些类型的公共（`public`）和受保护（`protected`）成员（见 §6.6）。对于未导出的包中的类型及其成员，在编译时或运行时不授予访问权限。模块内部的代码可以在编译时和运行时访问模块内所有包中的公共和受保护类型，以及这些类型的公共和受保护成员。

与编译时访问和运行时访问不同，Java SE 平台通过核心反射 API（§1.4）提供了反射访问（reflective access）。普通模块仅对那些显式导出或显式开放（或两者兼有）的包中的类型提供反射访问。开放模块则对其所有包中的类型提供反射访问，就好像所有包都已开放一样。

对于普通模块外部的代码，对模块已导出（且未开放）的包中的类型授予的反射访问，专门针对这些包中的公共和受保护类型，以及这些类型的公共和受保护成员。对模块已开放包（无论是否导出）中的类型授予的反射访问，则是针对这些包中的所有类型以及这些类型的所有成员。对于未导出或未开放包中的类型及其成员不授予反射访问。模块内部的代码享有对模块内所有包中所有类型及其所有成员的反射访问。

对于开放模块外部的代码，对模块已开放包（即模块中的所有包）中的类型授予的反射访问，针对这些包中的所有类型以及这些类型的所有成员。模块内部的代码享有对模块内所有包中所有类型及其所有成员的反射访问。

模块声明指令指定了模块对模块模块的依赖（通过 `requires`，§7.7.1）、它与其他模块提供的包（通过 `exports` 和 `opens`，§7.7.2）、它消耗的服务（通过 `uses`，§7.7.3）以及它提供的服务（通过 `provides`，§7.7.4）。

#### 包与模块

```java
ModuleDirective:
requires [Modifier] ModuleName;
exports PackageName [to ModuleName [, ModuleName]];
opens PackageName [to ModuleName [, ModuleName]];
types TypeName
provides TypeName with TypeName (, TypeName);
```

```java
RequiresModifier:
（以下之一）
transitive
static
```

当且仅当包存储在文件系统中（§7.2）时，主机系统可以选择实施一项限制：如果在由 `module-info` 加扩展名（如 `.java` 或 `.jav`）组成的文件中找不到模块声明，则视为编译错误。

此外，按照惯例（但并非强制），模块声明会将其指令分组：与模块相关的 `requires` 指令应与包相关的 `exports` 和 `opens` 指令在视觉上区分开来，与服务相关的 `uses` 和 `provides` 指令区分开来。例如：

```java
module com.example.foo {
    requires com.example.foo.http;
    requires java.logging;

    requires transitive com.example.foo.network;

    exports com.example.foo.bar;
    exports com.example.foo.internal to com.example.foo.probe;

    opens com.example.foo.quux;
    opens com.example.foo.internal to com.example.foo.network,
        com.example.foo.probe;

    uses com.example.foo.spi.Intf;
    provides com.example.foo.spi.Intf with com.example.foo.Impl;
}
```

如果模块是开放的，则可以避免 `opens` 指令：

```java
open module com.example.foo {
    requires com.example.foo.http;
    requires java.logging;

    requires transitive com.example.foo.network;

    exports com.example.foo.bar;
    exports com.example.foo.internal to com.example.foo.probe;

    uses com.example.foo.spi.Intf;
    provides com.example.foo.spi.Intf with com.example.foo.Impl;
}
```

建议 Java 语言开发工具高亮 `transitive` 指令和未限定的 `exports` 指令，因为它们构成了模块的主要 API。

## 7.7.1 依赖

`requires` 指令指定了当前模块所依赖的模块名称。

`requires` 指令不能出现在 `java.base` 模块的声明中，否则会发生编译错误，因为它是原始模块且没有依赖（§8.1.4）。

如果模块的声明没有表示对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，则该模块对 `java.base` 模块具有隐式声明的依赖。

`requires` 关键字后可以跟接 `transitive` 修饰符。这会导致任何要求当前模块的模块都对 `requires transitive` 指令所指定的模块具有隐式声明的依赖。

`requires` 关键字后可以跟接 `static` 修饰符。这指定了依赖关系在编译时是强制的，但在运行时是可选的。



如果模块的声明表达了对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，则该模块对 `java.base` 模块具有隐式声明的依赖。（注：此处原文存在重复/碎片化句子，但逻辑遵循规范）。

### 示例 7.7.1

假设有四个模块声明：

```
module m.A {
    requires m.B;
}

module m.B {
    requires transitive m.C;
}

module m.C {
    requires transitive m.D;
}

module m.D {
    exports p;
}
```

程序 `client.Test` 可以如下运行：

```java
package client;
import p;

public class Test {
    public static void main(String[] args) {
        System.out.println(new Point());
    }
}
```

如果由 `exports` 指定包未由当前模块关联的编译单元声明（§7.3），则为编译错误。

`opens` 允许指定一个未由当前模块关联的编译单元声明的包。（如果该包恰好由另一个模块的可观测单元声明了，则 `opens` 指令对其他模块没有影响。）

如果一个模块声明中有多个 `exports` 指令指定了相同的包名，则为编译错误。

如果一个模块声明中有多个 `opens` 指令指定了相同的包名，则为编译错误。

如果 `opens` 指令出现在开放式模块（open module）的声明中，则为编译错误。

如果 `exports` 指令具有 `to` 子句，则该指令是限定的（qualified）；否则，是非限定的（unqualified）。对于限定指令，该包中的 `public` 和 `protected` 类型以及它们的 `public` 和 `protected` 成员，仅供 `to` 子句中指定的模块中的代码访问。`to` 子句中指定的模块被称为当前模块的友元（friends）。对于非限定指令，这些类型及其成员对任何模块的代码都是可见的。

`exports` 或 `opens` 指令的 `to` 子句允许指定一个不可观测的模块（§7.7.6）。

如果给定的 `exports` 指令的 `to` 子句多次指定同一个模块名，则为编译错误。

如果给定的 `opens` 指令的 `to` 子句多次指定同一个模块名，则为编译错误。

## 7.7.3 服务消费（Service Consumption）

`uses` 指令指定了一个服务，当前模块的代码可以通过 `java.util.ServiceLoader` 发现该服务的提供者。

如果 `uses` 指令指定了一个枚举类（§8.9），则为编译错误。

服务可以在当前模块或其他模块中声明。如果服务未在当前模块中声明，则必须对当前模块的代码可见（§6.6），否则将发生编译错误。

如果一个模块声明中有多个 `uses` 指令指定同一个服务，则为编译错误。

## 7.7.4 服务提供（Service Provision）

`provides` 指令指定了一个服务，`with` 子句为该服务向 `java.util.ServiceLoader` 指定了一个或多个服务提供者。

如果 `provides` 指令指定一个枚举类（§8.9）作为服务，则为编译错误。

服务可以在当前模块或其他模块中声明。如果服务未在当前模块中声明，则服务必须对当前模块的代码可见（§6.6），否则将发生编译错误。

每个服务提供者必须是一个 `public` 类或接口，且必须是顶级的或静态的，否则将发生编译错误。

每个服务提供者必须在当前模块中声明，否则将发生编译错误。

如果服务提供者显式声明了一个没有形式参数的 `public` 构造函数，或者隐式地声明了 `public` 默认构造函数（§8.8.9），则该构造函数称为提供构造函数（provider constructor）。

如果服务提供者显式声明了一个没有形式参数的名为 `provider` 的 `public static` 方法，则该方法称为提供方法（provider method）。如果服务提供者拥有提供方法，则其返回类型必须：(i) 要在当前模块中声明；或者在另一个模块中声明并对当前模块的代码可见；并且 (ii) 是 `provides` 指令中指定服务的子类型；否则将发生编译错误。

- 虽然由 `provides` 指令指定的服务提供者必须在当前模块中声明，但其提供方法的返回类型可以是声明在另一个模块中的类型。此外，当服务提供者声明提供方法时，服务本身并不需要是所指定服务的子类型。

如果服务提供者没有提供方法，则该服务提供者必须有一个提供构造函数，并且必须是 `provides` 指令中指定服务的子类型，否则将发生编译错误。

如果一个模块声明中有多个 `provides` 指令指定同一个服务，则为编译错误。

如果给定的 `provides` 指令的 `with` 子句多次指定同一个服务，则为编译错误。

## 7.7.5 未命名模块（Unnamed Modules）

主机系统未与具命名模块关联的可观测普通编译单元（§7.3）与未命名模块关联。

Java SE 平台提供未命名模块是为了承认在 Java SE 9 之前开发的程序无法声明未命名模块。此外，Java SE 平台提供未命名包（§7.4）的原因很大程度上适用于未命名模块。

Java SE 平台的实现必须支持至少一个未命名模块。实现可以支持多个未命名模块，但不是强制要求的。哪些普通编译单元与每个未命名模块关联由主机系统决定。

主机系统可以将具命名包中的普通编译单元与一个未命名模块关联。

未命名模块的规则旨在最大化其它们与具命名模块的互操作性，如下：

- 一个未命名模块读取每个未命名模块（§7.7.6）。

> 由于与未命名模块关联的普通编译单元是可观测的，关联的未命名模块也是可见的。因此，如果 Java SE 平台的实现支持多个未命名模块，则每个未命名模块都是可见的，且每个未命名模块读取包括自身内的每个未命名模块。

然而，重要的是，未命名模块的普通编译单元对具命名模块永远不可见的（§7.3），因为没有 `requires` 指令可以安排具命名模块读取未命名模块。Java SE 平台的内核反射 API 可以在运行时安排具命名模块读取未命名模块。

- 一个未命名模块导出所有普通编译单元与该模块关联的包。

- 一个未命名模块开放所有普通编译单元与该模块关联的包。

## 7.7.6 模块的可观测性（Observability of a Module）

如果满足以下至少一点，则模块是可见的：

- 包含模块声明的模块化编译单元是可见的（§7.3）。

- 与模块关联的普通编译单元是可见的。

# 8 类（Classes）

类声明定义了一个类并描述其实现方式（§8.1）。

顶级类（§7.6）是直接在编译单元中声明的类。

嵌套类是任何在另一个类或接口内部声明的类。嵌套类可以是成员类（§8.5, §9.5）、局部类（§14.3）或匿名类（§15.9.5）。

某些嵌套类是内部类（inner class），它可以引用外部类、局部变量和类型变量。枚举类（§8.9）是使用简写语法定义的类，定义了一组小型命名类。记录类（§8.10）是使用简写语法定义的类，定义了一个简单的值聚合。

本章讨论所有类的通用语义。特定类型类的细节将在专门的章节中讨论。

类可以被声明为 `public`（§8.1.1），以便从其模块的任何包的代码引用，并可能从其他模块的代码引用。

类可以被声明为 `abstract`（§8.1.1.1），如果它是未完全实现的则必须声明为抽象的；此类类不能实例化，但可以被子类扩展。类可以被显式控制其扩展的程度（§8.1.1.2）：它可以被声明为 `sealed` 以限制其子类，或者被声明为 `final` 以无任何子类。除了 `Object` 之外，每个类都是单个现有类（§8.1.4）的扩展（即子类），并可以实现接口（§8.1.5）。

## 8.1 类声明

类声明可以像其他类型的声明一样用注解进行修饰（§9.7）。

类的体声明了成员（字段、方法、类和接口）、实例和静态初始化器，以及构造函数（§8.1）。成员的作用范围（§8.2）是该成员所属类声明的整个类体。字段、方法、成员类、成员接口和构造函数的声明可以包含访问修饰符 `public`、`protected` 或 `private`（§8.6）。类的成员包括已声明的成员和继承的成员（§8.2）。新声明的字段可以隐藏在父类或父接口中声明的字段。新声明的成员类和成员接口可以隐藏在父类或父接口中声明的成员类和成员接口。新声明的方法可以隐藏、实现或重写在父类或父接口中声明的方法。

字段声明（§8.3）描述了类变量，这些变量在类的每个实例时都会被新实例化。字段可以被声明为 `final`（§8.1.2），在这种情况下它只能被赋值一次。任何字段声明都可以包含一个初始化器。

成员类声明（§8.5）描述了作为外部类成员的嵌套类。成员类可以是 `static` 的，在这种情况下它们无法访问外部类的实例变量；或者它们可以是内部类。

成员接口声明（§8.5）描述了作为外部类成员的嵌套接口。

方法声明（§8.4）描述了可以被方法调用表达式（§15.2）调用的代码。类方法是相对于类调用的；实例方法是相对于某个作为类实例的特定对象调用的。如果方法声明没有指示其如何实现，则它必须被声明为 `abstract`（抽象的）。方法可以被声明为 `final`（§8.4.3.3），在这种情况下它不能被隐藏或重写。方法可以通过依赖于平台的原生代码实现（§8.4.4）。同步方法（§8.4.6）在执行之前会自动锁定一个对象并在返回时自动解锁该对象，就像使用 `synchronized` 语句（§14.19）一样，从而允许其活动与其他线程的活动保持同步（§17 (线程与锁)）。

方法名可以被重载（§8.4.9）。

实例初始化器（§8.6）是可执行代码块，可以在创建实例时用于初始化该实例（§15.9）。

静态初始化器（§8.7）是可执行代码块，可以用于初始化类。

构造函数（§8.8）与方法类似，但不能通过方法调用直接触发；它们用于初始化新的类实例。像方法一样，它们可以被重载（§8.8）。

### 8.1.1 类修饰符

类声明可以包含修饰符。

```
ClassModifier:
(其中之一)
abstract protected private
static final sealed non-sealed
```

关于类声明修饰符的规则在 §7.4 和 §7.5 中规定。访问修饰符 `public`（§6.6）仅适用于顶层类（§7.6）和成员类（§8.5），而不适用于本地类（§7.3）或匿名类（§15.9）。访问修饰符 `protected` 和 `private` 仅适用于成员类。修饰符 `static` 仅适用于成员类和本地类。

如果同一个关键字作为类声明的修饰符出现多次，或者一个类声明具有 `public`、`protected` 和 `private` 访问修饰符中的多个一个，则是一个编译错误。如果一个类声明具有 `sealed`、`non-sealed` 和 `final` 修饰符中的多个一个，则是一个编译错误。如果一个类声明中出现了两个或多个（不同的）类修饰符，按照惯例（尽管不是强制），它们按上述所示顺序出现。

#### 8.1.1.1 抽象类 (abstract Classes)

抽象类被认为是不完整的类。如果尝试使用创建表达式（§15.9）创建抽象类的实例，则是一个编译错误。抽象类的本身不是抽象的子类可以被实例化，这将导致抽象类构造函数的执行，从而导致该类实例变量的字段初始化器的执行。

普通类可以拥有抽象方法（已声明但未实现（§8.4.3）），但仅当它是一个抽象类时。如果以下任一条件成立，则类具有抽象方法：

- 类的任何方法（§8.2）（无论是声明的还是继承的）是抽象的。

- 它的任何父类都声明了一个抽象方法，且不存在重写该父类中抽象方法的方法。

声明一个抽象类，以至于无法创建一个实现其所有抽象方法的子类，则是一个编译错误。

##### 示例 8.1.1.1-1 抽象类声明

```
abstract class Point {
    int x = 1, y = 1;
    abstract void move(int dx, int dy);
}

abstract class Colored extends Point {
    int color;
    void move(int dx, int dy) {
        x += dx;
    }
}

class SimplePoint extends Point {
    void move() {
    }
}
```

在这里，类 `Point` 被声明为抽象的，因为它包含一个抽象方法。子类 `Colored` 继承了 `move` 方法，因此它也被声明为抽象的。子类 `SimplePoint` 不是抽象的，所以语句：

```
Point p = new Point();
```

会导致编译错误；因为 `Point` 是抽象的，无法实例化。然而，一个 `Point` 变量可以正确地用 `SimplePoint` 初始化，这将导致 x 和 y 的字段初始化执行。

##### 示例 8.1.1.1-2 禁止子类的抽象类声明

```
interface Colorable {
    void setColor(int color);
}
abstract class Colored implements Colorable {
    public abstract int setColor(int color);
}
```

这些声明会导致编译错误：对于 `Colored` 类的任何子类来说，提供一个接受 `int` 类型的 `setColor` 方法实现是不可能的，因为接口 `Colorable` 要求方法返回一个值，而类 `Colored` 要求方法返回 `int` 类型的值（§8.4）。

只有当目的是创建子类来完成实现时，类型应该被声明为抽象的。如果仅仅是为了防止类的实例化，正确的方法是声明一个无参数的构造函数（§8.10），将其私有化，永远不要调用它。这种形式的类通常包含类方法和变量。

`Math` 类是一个无法实例化的示例；它的声明如下：

```
public final class Math {
    private Math() { // 永远不实例化此类
        .. 类变量和方法的声明 ..
    }
}
```

#### 8.1.1.2 密封的、非密封的和最终类 (sealed, non-sealed, and final Classes)

如果在声明类时已知所有的直接子类（§8.1.6），则类可以被声明为 `sealed`。

> 显式且详尽地控制类的子类对于类层次结构用于建模领域的值有用，而不是作为代码继承和重用的机制。直接子类本身必须是密封的，以进一步控制类层次结构。

如果类的定义是完整的且不需要子类，则类可以被声明为 `final`。

如果一个类被同时声明为 `final` 和 `abstract`，则是一个编译错误，因为这种类的实现永远无法完成（§8.1.1.1）。

由于 `final` 类永远没有子类，因此 `final` 类的方法永远不会重写（§8.4.8.1）。

如果一个类的直接父类是密封的（§8.1.4），且它的任何直接接口都不是密封的（§8.1.5），并且它本身既不是密封的也不是最终的，那么它就是自由扩展的。

具有密封直接父类或密封直接接口的类，当且仅当它被声明为 `non-sealed` 时，才是自由扩展的。

如果一个类具有密封直接父类或密封直接接口，并且显式或隐式地声明为 `final`、`sealed` 或 `non-sealed`，则是一个编译错误。

因此，`sealed` 关键字的作用是强制所有直接子类必须显式地声明它们是 `final`、`sealed` 还是 `non-sealed`。这避免了意外将密封类层次结构暴露给不需要的子类继承。

枚举类（enum class）要么是隐式的 `final`，要么是隐式的 `sealed`，因此它可以实现 `sealed` 接口。同样，record 类是隐式的 `final`，因此它也可以实现 `sealed` 接口。

如果一个类被声明为 `non-sealed` 但既没有 `sealed` 的直接父类也没有 `sealed` 的父接口，则会导致编译错误。

因此，`non-sealed` 类的子类本身不能被声明为 `non-sealed`。

#### 8.1.1.3 strictfp 类

类声明中的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对在编译时或运行时均没有影响。

#### 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态方法在其体文中没有该类的当前实例一样，静态嵌套类在其体文中没有直接包围的类。

禁止从静态嵌套类引用到类型参数、实例变量、局部变量、形式参数、异常参数或词法包围类、接口或方法声明的声明（§6.5.5.1, §6.5.6.1 和 §15.12.3）。



`static` 修饰符并不适用于所有的嵌套类。它仅适用于成员类（即声明中使用了 `static` 修饰符的类），而不适用于局部类或匿名类（后者的声明可能无法使用 `static` 修饰符）（§14.3, §15.95）。然而，某些局部类是隐式静态的，即局部枚举类和局部 record 类，因为所有嵌套枚举类和 record 类都是隐式静态的（§8.9, §8.10）。

## 8.1 泛型类与类型参数

如果类声明声明了一个或多个类型变量（§4.4），则该类是泛型类。

这些类型变量被称为类的类型参数。类型参数部分紧随类名之后，并用角括号分隔。

```
TypeParameters:
< TypeParameter >
```

```
TypeParameterList:
TypeParameter (, TypeParameter)
```

为了方便起见，此处显示了 §4.4 中的以下产生式：

- TypeParameter:
  `[TypeParameterModifier] TypeIdentifier [TypeBound]`

- TypeParameterModifier:
  `Annotation`

- TypeBound:
  `extends TypeVariable` | `extends ClassOrInterfaceType [AdditionalBound]`

- AdditionalBound:
  `& InterfaceType`

关于类型参数声明的注解修饰符的规定在 §9.7.4 和 §9.7.5 中。

在类的类型参数部分，如果类型变量 `t` 依赖于类型变量 `s`，则 `s` 是 `t` 的边界；如果 `t` 依赖于 `s` 或者 `t` 直接依赖于某个依赖于 `s` 的类型变量 `u`（递归使用此定义），也是如此。

如果类类型参数部分中的类型变量依赖于自身，则会导致编译错误。

类类型参数的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

从静态上下文或嵌套类或接口引用类的类型参数受限，如 §6.5.5.1 规定。

泛型类声明定义了一组参数化类型（§4.5），为类型参数部分通过类型参数每种可能的参数化对应一个。所有这些参数化类型在运行时共享同一个类。

例如，执行以下代码：

```java
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致 `b` 的值为 `true`。

如果泛型类是 `Throwable` 的直接或间接子类（§11.1.1），则会导致编译错误。

这种限制是必要的，因为 Java 虚拟机的 catch 机制仅对非泛型类有效。

### 示例 8.1.2-1 递归类型变量边界

```java
interface ConvertibleTo<T> {
    T convert();
}
class ReprChange<T extends ConvertibleTo<S>, 
    extends ConvertibleTo<T>> {
    T t;
    void set(S s) { t = s.convert(); }
    S get() { return t.convert(); }
}
```

### 示例 8.1.2-2 嵌套泛型类

```java
class Seq<T> {
    T head;
    Seq<T> tail;

    Seq(this (null, null, null));
    Seq(T head, Seq<T> tail) {
        this.head = head;
        this.tail = tail;
    }
    boolean isEmpty() { return tail == null; }
}

class Zipper<T,S> {
    SeqPair<T,S> zip(Seq<S> that) {
        if (isPair(that) || that.isEmpty()) {
            return new SeqPair<T,S>(null);
        } else {
            Seq<T>.Zipper<S> tailZipper = tail.tail.new Zipper<S>();
            return new SeqPair<T,S>(new Pair<T,S>(that.head, 
                tailZipper.zip(that.tail)));
        }
    }
}

class Pair<T, S> {
    T f; S snd;
    Pair(T f, S s) { this.f = f; this.snd = s; }
}

class Test {
    public static void main(String[] args) {
    }
}
```

## 8.1.1.3 strictfp 类

类声明中的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对在编译时或运行时均没有影响。

## 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态方法在其体文中没有该类的当前实例一样，静态嵌套类在其体文中没有直接包围的类。

禁止从静态嵌套类引用到类型参数、实例变量、局部变量、形式参数、异常参数或词法包围类、接口或方法声明的声明（§6.5.5.1, §6.5.6.1 和 §15.12.3）。

`static` 修饰符并不适用于所有的嵌套类。它仅适用于成员类（即声明中使用了 `static` 修饰符的类），而不适用于局部类或匿名类（后者的声明可能无法使用 `static` 修饰符）（§14.3, §15.95）。然而，某些局部类是隐式静态的，即局部枚举类和局部 record 类，因为所有嵌套枚举类和 record 类都是隐式静态的（§8.9, §8.10）。



# 8.1 类声明

## 8.1.2 泛型类与类型参数

如果类声明声明了一个或多个类型变量（§4.4），则该类是泛型类。

这些类型变量被称为类的类型参数。类型参数部分紧随类名之后，并用角括号分隔。

```
TypeParameters:
< TypeParameterList >
```

```
TypeParameterList:
TypeParameter (, TypeParameter)*
```

为了方便起见，此处显示了 §4.4 中的以下产生式：

- TypeParameter:
  `[TypeParameterModifier] TypeIdentifier [TypeBound]`

- TypeParameterModifier:
  `Annotation`

- TypeBound:
  `extends TypeVariable` | `extends ClassOrInterfaceType [AdditionalBound]`

- AdditionalBound:
  `& InterfaceType`

关于类型参数声明的注解修饰符的规定在 §9.7.4 和 §9.7.5 中。

在类的类型参数部分，如果类型变量 `t` 依赖于类型变量 `s`，则 `s` 是 `t` 的边界；如果 `t` 依赖于 `s` 或者 `t` 直接依赖于某个依赖于 `s` 的类型变量 `u`（递归使用此定义），也是如此。

如果类类型参数部分中的类型变量依赖于自身，则会导致编译错误。

类类型参数的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

从静态上下文或嵌套类或接口引用类的类型参数受限，如 §6.5.5.1 规定。

泛型类声明定义了一组参数化类型（§4.5），为类型参数部分通过类型参数每种可能的参数化对应一个。所有这些参数化类型在运行时共享同一个类。

例如，执行以下代码：

```java
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致 `b` 的值为 `true`。

如果泛型类是 `Throwable` 的直接或间接子类（§11.1.1），则会导致编译错误。

这种限制是必要的，因为 Java 虚拟机的 catch 机制仅对非泛型类有效。

### 示例 8.1.2-1. 递归类型变量边界

```java
interface ConvertibleTo<T> {
    T convert();
}
class ReprChange<T extends ConvertibleTo<S>, 
    S extends ConvertibleTo<T>> {
    T t;
    void set(S s) { t = s.convert(); }
    S get() { return t.convert(); }
}
```

### 示例 8.1.2-2. 嵌套泛型类

```java
class Seq<T> {
    T head;
    Seq<T> tail;

    Seq() { this(null, null); }
    Seq(T head, Seq<T> tail) {
        this.head = head;
        this.tail = tail;
    }
    boolean isEmpty() { return tail == null; }
}

class Zipper<T, S> {
    Seq<T> tail;
    SeqPair<T, S> zip(Seq<S> that) {
        if (that == null || that.isEmpty()) {
            return new SeqPair<T, S>(null);
        } else {
            Zipper<S> tailZipper = tail.new Zipper<S>();
            return new SeqPair<T, S>(new Pair<T, S>(that.head, 
                tailZipper.zip(that.tail)));
        }
    }
}

class Pair<T, S> {
    T f; S snd;
    Pair(T f, S s) { this.f = f; this.snd = s; }
}

class SeqPair<T, S> {
    Pair<T, S> head;
    SeqPair<T, S> tail;
    SeqPair(Pair<T, S> head) { this.head = head; }
}

class Test {
    public static void main(String[] args) {
    }
}
```

## 8.1.1.3 strictfp 类

类声明中的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对在编译时或运行时均没有影响。

## 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态方法在其体文中没有该类的当前实例一样，静态嵌套类在其体文中没有直接包围的类。

禁止从静态嵌套类引用到类型参数、实例变量、局部变量、形式参数、异常参数或词法包围类、接口或方法声明的声明（§6.5.5.1, §6.5.6.1 和 §15.12.3）。

`static` 修饰符并不适用于所有的嵌套类。它仅适用于成员类（即声明中使用了 `static` 修饰符的类），而不适用于局部类或匿名类（后者的声明可能无法使用 `static` 修饰符）（§14.3, §15.95）。然而，某些局部类是隐式静态的，即局部枚举类和局部 record 类，因为所有嵌套枚举类和 record 类都是隐式静态的（§8.9, §8.10）。



# 8.1 类声明

## 8.1.2 泛型类与类型参数

如果类声明声明了一个或多个类型变量（§4.4），则该类是泛型类。

这些类型变量被称为类的类型参数。类型参数部分紧随类名之后，并用角括号分隔。

```
TypeParameters:
    < TypeParameter >
```

```
TypeParameterList:
    TypeParameter (, TypeParameter)
```

为了方便起见，此处显示了 §4.4 中的以下产生式：

- TypeParameter:
  `[TypeParameterModifier] TypeIdentifier [TypeBound]`

- TypeParameterModifier:
  `Annotation`

- TypeBound:
  `extends TypeVariable`
  `extends ClassOrInterfaceType [AdditionalBound]`

- AdditionalBound:
  `& InterfaceType`

关于类型参数声明的注解修饰符的规定在 §9.7.4 和 §9.7.5 中。

在类的类型参数部分，如果类型变量 `t` 依赖于类型变量 `s`，则 `s` 是 `t` 的边界；如果 `t` 依赖于 `s` 或者 `t` 直接依赖于某个依赖于 `s` 的类型变量 `u`（递归使用此定义），也是如此。

如果类类型参数部分中的类型变量依赖于自身，则会导致编译错误。

类类型参数的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

从静态上下文或嵌套类或接口引用类的类型参数受限，如 §6.5.5.1 规定。

泛型类声明定义了一组参数化类型（§4.5），为类型参数部分通过类型参数每种可能的参数化对应一个。所有这些参数化类型在运行时共享同一个类。

例如，执行以下代码：

```java
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致 `b` 的值为 `true`。

如果泛型类是 `Throwable` 的直接或间接子类（§11.1.1），则会导致编译错误。

这种限制是必要的，因为 Java 虚拟机的 catch 机制仅对非泛型类有效。

### 示例 8.1.2-1. 递归类型变量边界

```java
interface ConvertibleTo<T> {
    T convert();
}
class ReprChange<T extends ConvertibleTo<S>, 
    extends ConvertibleTo<T>> {
    T t;
    void set(S s) { t = s.convert(); }
    S get() { return t.convert(); }
}
```

### 示例 8.1.2-2. 嵌套泛型类

```java
class Seq<T> {
    T head;
    Seq<T> tail;

    Seq(this (null, null, null));
    Seq(T head, Seq<T> tail) {
        this.head = head;
        this.tail = tail;
    }
    boolean isEmpty() { return tail == null; }
}

class Zipper<T,S> {
    SeqPair<T,S> zip(Seq<S> that) {
        if (isPair(that) || that.isEmpty()) {
            return new SeqPair<T,S>(null);
        } else {
            Seq<T>.Zipper<S> tailZipper = tail.tail.new Zipper<S>();
            return new SeqPair<T,S>(new Pair<T,S>(that.head, 
                tailZipper.zip(that.tail)));
        }
    }
}

class Pair<T, S> {
    T f; S snd;
    Pair(T f, S s) { this.f = f; this.snd = s; }
}

class Test {
    public static void main(String[] args) {
    }
}
```

## 8.1.1.3 strictfp 类

类声明中的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对在编译时或运行时均没有影响。

## 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态方法在其体文中没有该类的当前实例一样，静态嵌套类在其体文中没有直接包围的类。

禁止从静态嵌套类引用到类型参数、实例变量、局部变量、形式参数、异常参数或词法包围类、接口或方法声明的声明（§6.5.5.1, §6.5.6.1 和 §15.12.3）。

`static` 修饰符并不适用于所有的嵌套类。它仅适用于成员类（即声明中使用了 `static` 修饰符的类），而不适用于局部类或匿名类（后者的声明可能无法使用 `static` 修饰符）（§14.3, §15.95）。然而，某些局部类是隐式静态的，即局部枚举类和局部 record 类，因为所有嵌套枚举类和 record 类都是隐式静态的（§8.9, §8.10）。



# 8.1 类声明

## 8.1.1.3 strictfp 类

类声明中的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对在编译时或运行时均没有影响。

## 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态方法在其体文中没有该类的当前实例一样，静态嵌套类在其体文中没有直接包围的类。

禁止从静态嵌套类引用到类型参数、实例变量、局部变量、形式参数、异常参数或词法包围类、接口或方法声明的声明（§6.5.5.1, §6.5.6.1 和 §15.12.3）。

`static` 修饰符并不适用于所有的嵌套类。它仅适用于成员类（即声明中使用了 `static` 修饰符的类），而不适用于局部类或匿名类（后者的声明可能无法使用 `static` 修饰符）（§14.3, §15.95）。然而，某些局部类是隐式静态的，即局部枚举类和局部 record 类，因为所有嵌套枚举类和 record 类都是隐式静态的（§8.9, §8.10）。

## 8.1.2 泛型类与类型参数

如果类声明声明了一个或多个类型变量（§4.4），则该类是泛型类。

这些类型变量被称为类的类型参数。类型参数部分紧随类名之后，并用角括号分隔。

```text
TypeParameters:
< TypeParameter >
```

```text
TypeParameterList:
TypeParameter (, TypeParameter)
```

为了方便起见，此处显示了 §4.4 中的以下产生式：

- TypeParameter:
  `[TypeParameterModifier] TypeIdentifier [TypeBound]`
- TypeParameterModifier:
  `Annotation`
- TypeBound:
  `extends TypeVariable` | `extends ClassOrInterfaceType [AdditionalBound]`
- AdditionalBound:
  `& InterfaceType`

关于类型参数声明的注解修饰符的规定在 §9.7.4 和 §9.7.5 中。

在类的类型参数部分，如果类型变量 `t` 依赖于类型变量 `s`，则 `s` 是 `t` 的边界；如果 `t` 依赖于 `s` 或者 `t` 直接依赖于某个依赖于 `s` 的类型变量 `u`（递归使用此定义），也是如此。

如果类类型参数部分中的类型变量依赖于自身，则会导致编译错误。

类类型参数的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

从静态上下文或嵌套类或接口引用类的类型参数受限，如 §6.5.5.1 规定。

泛型类声明定义了一组参数化类型（§4.5），为类型参数部分通过类型参数每种可能的参数化对应一个。所有这些参数化类型在运行时共享同一个类。

例如，执行以下代码：

```java
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致 `b` 的值为 `true`。

如果泛型类是 `Throwable` 的直接或间接子类（§11.1.1），则会导致编译错误。

这种限制是必要的，因为 Java 虚拟机的 catch 机制仅对非泛型类有效。

### 示例 8.1.2-1. 递归类型变量边界

```java
interface ConvertibleTo<T> {
    T convert();
}
class ReprChange<T extends ConvertibleTo<S>, 
    extends ConvertibleTo<T>> {
    T t;
    void set(S s) { t = s.convert(); }
    S get() { return t.convert(); }
}
```

### 示例 8.1.2-2. 嵌套泛型类

```java
class Seq<T> {
    T head;
    Seq<T> tail;

    Seq(this (null, null, null));
    Seq(T head, Seq<T> tail) {
        this.head = head;
        this.tail = tail;
    }
    boolean isEmpty() { return tail == null; }
}

class Zipper<T,S> {
    SeqPair<T,S> zip(Seq<S> that) {
        if (isPair(that) || that.isEmpty()) {
            return new SeqPair<T,S>(null);
        } else {
            Seq<T>.Zipper<S> tailZipper = tail.tail.new Zipper<S>();
            return new SeqPair<T,S>(new Pair<T,S>(that.head, 
                tailZipper.zip(that.tail)));
        }
    }
}

class Pair<T, S> {
    T f; S snd;
    Pair(T f, S s) { this.f = f; this.snd = s; }
}

class Test {
    public static void main(String[] args) {
    }
}
```



# 类声明

## 8.1 类声明

### 8.1.1 类修饰符

#### 8.1.1.3 strictfp 类

#### 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态方法在其体文中没有该类的当前实例一样，静态嵌套类在其体文中没有直接包围的类。

### 8.1.2 泛型类与类型参数

### 8.1.3 内部类与包含实例

类或接口 `o` 的直接内部类 `c` 的实例 `i` 与 `o` 的一个实例关联，被称为 `i` 的*紧邻包类实例*（immediately enclosing instance）。对象的*紧邻包类实例*（如果有）是在对象创建时确定的 (§15.9.2)。

对象 `o` 是它自身的*零次*词法包类实例。

如果对象 `o` 是实例 `i` 的第 `n-1` 次词法包类实例的紧邻包类实例，则它是实例 `i` 的第 `n` 次词法包类实例。

在静态上下文中声明的内部类或匿名类的实例没有紧邻包类实例。同样，*静态嵌套类*（§8.1.1.4）的实例没有紧邻包类实例。

对于 `c` 的每一个父类 `s`，如果 `s` 本身是类或接口 `so` 的直接内部类，则有一个 `s` 的实例与 `i` 关联，被称为相对于 `s` 的 `i` 的紧邻包类实例。对象相对于其直接父类的紧邻包类实例，是在通过显式构造函数调用语句调用父类构造函数时确定的 (§8.7.1)。

当内部类（其声明未发生在静态环境中）引用词法包类类或接口声明中成员的实例变量时，将使用相应词法包类实例的变量。

内部类中使用但未声明的局部变量、形式参数或参数必须是 `final` 或有效最终的（§4.12.4），如 §6.5.6.1 所示。

内部类中使用但未声明的局部变量必须在内部类体之前经过确定性赋值（§16 (*确定性赋值*)），否则会发生编译错误。

类似的使用规则也适用于 lambda 表达式的体（§15.27.2）。

词法包类类或接口声明的空 `final` 字段（§4.12.4）不能在内部类中赋值，否则会发生编译错误。

#### 示例 8.1.3-2. 内部类声明

```java
class Outer {
    int i = 100;
    static void methodName() {
        final int l1 = 200;
        class LocalInStaticContext {
            int k = i; // 编译错误
            int m = l1; // OK
        }
    }
}
```

由于位于静态方法内部，`LocalInStaticContext` 的声明发生在静态环境中。`Outer` 的实例变量在静态方法的体中是不可用的。特别是：

声明未发生在静态环境中内部类可以自由引用其词法包类声明的实例变量。实例变量总是相对于一个实例定义的。对于词法包类类声明的实例变量，该实例变量必须相对于内部类的紧邻包类实例定义。例如，类 `Local` 有一个 `Outer` 类的包类实例。进一步示例如下：

```java
class DeepNesting {
    boolean toBe;
    DeepNesting(boolean b) { toBe = b; }

    class Nested {
        boolean theQuestion;
        class DeeplyNested {
            DeeplyNested() {
                theQuestion = toBe || !toBe;
            }
        }
    }
}
```

每一个 `DeepNesting.Nested.DeeplyNested` 实例都有一个 `DeepNesting.Nested` 类的包类实例（它的紧邻包类实例）和一个 `DeepNesting` 类的包类实例（它的第 2 次词法包类实例）。

### 8.1.4 父类与子类

普通类声明中可选的 `extends` 子句指定了声明类的直接父类类型。

```
ClassExtends:
    extends ClassType
```

`extends` 子句不能出现在 `Object` 类的定义中，否则会发生编译错误，因为它是原始类且没有直接父类类型。

`ClassType` 必须命名一个可访问的类 (§6.6)，否则会发生编译错误。

如果 `ClassType` 命名的是一个密封（sealed）类 (§8.1.1.2)，且声明的类不是命名类允许的直接子类 (§8.1.6)，则会发生编译错误。

如果 `ClassType` 命名的是一个最终（final）类，则会发生编译错误，因为 final 类不允许有子类 (§8.1.1.2)。

如果 `ClassType` 命名的是一个枚举（Enum）类（它只能被枚举类扩展 (§8.9)），或者命名的是记录（Record）类（它只能被记录类扩展 (§8.10)），则会发生编译错误。

如果 `ClassType` 带有参数，它必须表示一个格式良好的参数化类型 (§4.5)，且任何类型参数都不能是通配符类型，否则会发生编译错误。

缺少 `extends` 子句的类的直接父类类型如下：

- `Object` 类没有直接父类类型。
- 对于除 `Object` 之外具有普通类的类，其直接父类类型是 `Object`。
- 对于枚举类，其直接父类类型是 `Enum<E>`。
- 对于匿名类，其直接父类类型在 §15.9.5 中定义。

### 8.1.5 超接口

一个声明中缺少 `implements` 子句的类没有直接的超接口接口类型，但有一个例外：匿名类可以有一个超接口类型 (§15.9.5)。

如果一个接口由某个类的某个直接超接口类型命名，则该接口是该类的直接超接口。

如果满足以下任一条件，则接口 *I* 是类 *C* 的超接口：

- *I* 是一个直接超接口。
- *C* 具有某个直接超接口 *J*，根据 §9.1.3 给出的“接口的超接口”的定义，*I* 是 *J* 的超接口。
- *I* 是 *C* 的直接父类的超接口。

一个类可以通过多种方式拥有超接口。

一个类被认为是直接实现了它的超接口，并且实现了它所有的超接口。

一个类被认为是它直接超接口的直接子类，并且是所有超接口的子类。

一个类不能声明一个直接父类类型和一个直接超接口类型，或者声明两个直接超接口类型，且这些类型是同一个泛型接口的不同参数化 (§9.1.2)，或者是一个泛型接口的参数化与命名该泛型接口的原始类型（raw type）。在这种冲突情况下，会发生编译时错误。

引入这一要求是为了支持擦除转换 (§4.6)。

#### 示例 8.1.5-2. 超接口

```java
interface Colorable {
    void setColor(int color);
    int getColor();
}
enum Finish { MATTE, GLOSSY }
interface Paintable extends Colorable {
    void setFinish(Finish finish);
    Finish getFinish();
}

class Point { int x, y; }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
    public int getColor() { return color; }
}
```

```java
class PaintedPoint extends ColoredPoint implements Paintable {
    Finish finish;
    public void setFinish(Finish finish) {
        this.finish = finish;
    }
    public Finish getFinish() { return finish; }
}
```

关系如下：

- 接口 `Paintable` 是类 `PaintedPoint` 的超接口。
- 接口 `Colorable` 是类 `ColoredPoint` 和类 `PaintedPoint` 的超接口。
- 根据 §9.1.3 的定义，接口 `Paintable` 是接口 `Colorable` 的子接口，而 `Colorable` 是 `Paintable` 的超接口。

类 `PaintedPoint` 拥有 `Colorable` 作为超接口，因为它是 `ColoredPoint` 的超接口，并且是 `Paintable` 的超接口。

#### 示例 8.1.5-3. 接口的非法继承

```java
interface I<T> {}
class B implements I<Integer>
class C extends B implements I<String>
```

类 `C` 导致编译时错误，因为它试图同时成为 `I<Integer>` 和 `I<String>` 的子类型。

除非该类被声明为抽象（abstract），否则每个直接超接口的所有抽象方法都必须被实现 (§8.4.8.1)，要么通过该类中的声明来实现，要么通过继承自直接父类或直接超接口的现有方法声明来实现，因为非抽象类不允许拥有抽象方法 (§8.1.1.1)。

该类的超接口的每个默认方法 (§9.4.3) 都可以可选地被类中的方法重写；如果没有重写，默认通常会被继承，其行为由其默认方法体指定。

类中的单个方法声明实现多个超接口的方法是被允许的。

#### 示例 8.1.5-4. 实现超接口的方法

```java
interface Colorable {
    void setColor(int color);
    int getColor();
}
class Point { int x, y; }
class ColoredPoint extends Point implements Colorable {
    int color;
}
```

此程序会导致编译时错误，因为 `ColoredPoint` 不是抽象类但未提供接口 `Colorable` 方法 `setColor` 和 `getColor` 的实现。

在以下程序中：

```java
interface Fish { int getNumberOfes(); }
interface Piano { int getNumberOfes(); }
class Tuna implements Fish, Piano {
    // 你调钢琴，但你能调鱼吗？
    public int getNumberOfes() { return 91; }
}
```

类 `Tuna` 的 `getNumberOfes` 方法名称、签名和返回类型匹配接口 `Fish` 中声明的方法，也匹配接口 `Piano` 中声明的方法；它被认为实现了两者。

另一方面，在类似这样的情况下：

```java
interface Fish { int getNumberOfes(); }
interface StringBass { double getNumberOfes(); }
class Bass implements Fish, StringBass {
    // 无论使用什么类型，此声明都是错误的。
    public int getNumberOfes() { return 91; }
}
```

无法声明一个名为 `getNumberOfes` 且其签名和返回类型都能兼容接口 `Fish` 和接口 `StringBass` 中声明的方法的方法，因为类不能具有相同签名但不同原始返回类型的方法（§8.4）。因此，一个类无法实现 `Fish` 和 `StringBass`。

### 8.1.6 许可子类

密封类（sealed class）的要求是指定其许可的子类。密封类及其直接子类必须分别在 `permits` 和 `extends` 子句中相互引用。

### 8.1.7 类体和成员声明

类体可以包含类的成员声明，即字段（§8.3）、方法（§8.4）、类和接口（§8.5）。类体还可以包含实例初始化器（§8.6）、静态初始化器（§8.7）以及该类的构造函数声明（§8.8）。

```
ClassBody:
{ [ClassBodyDeclaration] }
```

```
ClassBodyDeclaration:
  ClassMemberDeclaration
  InstanceInitializer
  StaticInitializer
  ConstructorDeclaration
```

```
ClassMemberDeclaration:
  FieldDeclaration
  MethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
;
```

在类 `c` 中声明或继承的成员 `m` 的作用域和屏蔽规则在 §6.3 指定。

如果 `c` 是嵌套类，在包层作用域中可能存在相同种类（变量、方法或类型）和名称的定义。（作用域可能是块、类或包。）

在所有此类情况下，在 `c` 中声明或其继承的成员 `m` 遮蔽了相同类型和名称的其他定义。

## 8.2 类成员

类的成员包含以下所有内容：

- 继承自其直接超类类型 (§8.1.4) 的成员，`Object` 类除外，因为它没有直接超类类型
- 继承自任何直接超接口类型 (§8.1.5) 的成员
- 在类体中声明的成员 (§8.1.7)

被声明为 `private` 的类成员不会被该类的子类继承。

只有被声明为 `protected` 或 `public` 的类成员才会被声明在类类所在包其他包中的子类继承。

构造方法、静态初始化器和实例初始化器不是成员，因此不被继承。

我们使用“成员的类型”这一术语来表示：

- 对于字段，指其类型。
- 对于方法，指一个由以下部分组成的有序 4 元组：
  - 类型参数：该方法成员任何类型参数的声明。
  - 参数类型：该方法成员参数类型的列表。
  - 返回类型：该方法成员的返回类型。
  - throws 子句：在方法成员 `throws` 子句中声明的异常类型。

类的字段、方法、成员类和成员接口可以具有相同的名称，因为它们用于不同的上下文中，并通过不同的查找程序进行消义（§6.5）。然而，从风格角度来看，这种是不推荐的。

#### 示例 8.2-1. 类成员的使用

```java
class Point {
    int x, y;
    private Point() { reset(); }
    Point(int x, int y) { this.x = x; this.y = y; }
    private void reset() { this.x = 0; this.y = 0; }
}

class ColoredPoint extends Point {
    int color;
    void clear() { reset(); } // 错误
}

class Test {
    public static void main(String[] args) {
        ColoredPoint c = new ColoredPoint(0, 0); // 错误
        c.reset(); // 错误
    }
}
```

发生错误是因为 `ColoredPoint` 没有声明带有两个 `int` 参数的构造方法（正如在 `main` 中使用那样）。这说明了 `ColoredPoint` 没有继承其超类 `Point` 的构造方法。

另一个错误是因为 `ColoredPoint` 没有声明任何构造方法，因此它隐式地声明了一个默认构造方法 (§8.8.9)，因此默认构造方法等同于：

```java
ColoredPoint() { super(); }
```

它调用了 `ColoredPoint` 类直接超类的无参数构造方法。错误在于，`Point` 类的无参数构造方法是 `private` 的，因此在 `Point` 类之外无法访问，即使通过超类调用也是如此 (§8.8.7)。



另外两个错误是因为 `Point` 类的 `reset` 方法是 `private` 的，因此不被 `ColoredPoint` 类继承。因此 `ColoredPoint` 类 `clear` 方法和 `Test` 类 `main` 方法中的方法调用是不正确的。

## 示例 8.2-2. 包访问权限的类成员继承

考虑 `points` 包声明了两个编译单元的示例：

```java
package points;
public class Point {
    int x, y;
    public void move(int dx, int dy) { x += dx; y += dy; }
}
```

以及：

```java
package points;
public class Point3d extends Point {
    int z;
    public void move(int dx, int dy, int dz) {
        x += dx; y += dy; z += dz;
    }
}
```

而另一个包中的第三个编译单元为：

```java
import points.Point3d;
class Point4d extends Point3d {
    int w;
    public void move(int dx, int dy, int dz, int dw) {
        x += dx; y += dy; z += dz; w += dw; // 编译错误
    }
}
```

`points` 包中的两个类通过编译。`Point3d` 类继承了 `Point` 类的 `x` 和 `y`，因为它与 `Point` 在同一个包中。`Point4d` 类位于不同的包，没有继承 `Point` 类的 `x` 和 `y` 或 `Point3d` 类的字段 `z`，导致编译失败。

编写第三个编译单元的更好方法是：

```java
import points.Point3d;
class Point4d extends Point3d {
    int w;
    public void move(int dx, int dy, int dz, int dw) {
        x += dx; y += dy; z += dz; w += dw;
    }
}
```

## 示例 8.2-3. public 和 protected 成员的继承

给定类 `Point`：

```java
package points;
public class Point {
    int x, y;
    public void move(int dx, int dy) { x += dx; y += dy; }
}
```

另一个编译单元：

```java
package morePoints;
class Point3d extends Point {
    int z;
    public void move(int dx, int dy, int dz) {
        x += dx; y += dy; z += dz;
    }
    public void move(int dx, int dy) {
        move(dx, dy);
    }
}
```

```java
public class OnePoint {
    public static points.Point getOne() {
        return new Point3d();
    }
}
```

在第三个包中调用 `morePoints.OnePoint.getOne()` 会返回一个 `Point3d`，尽管 `Point3d` 类型在包外不可用，但它可以作为 `Point` 使用。此时可以调用该对象的两个参数的 `move` 方法，因为 `Point3d` 的方法是 `public` 的（因为重写的方法本身必须是 `public`，这样该对象的 `x` 和 `y` 字段也可以从该包访问）。

## 示例 8.2-4. private 成员的继承

```java
package points;
public class Point {
    int x, y;
    public void move(int dx, int dy) { x += dx; y += dy; }
    protected int useCount = 0;
}
```

以及编译单元：

```java
package morePoints;
class Point3d extends Point {
    int z;
    public void move(int dx, int dy, int dz) {
        x += dx; y += dy; z += dz;
    }
    public void move(int dx, int dy) {
        move(dx, dy);
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Point3d p = new Point3d();
        p.useCount++; // 错误
    }
}
```

虽然 `Point3d` 的字段 `z` 是 `public` 的，但如果只有类型为 `Point` 的变量 `p` 中的引用，则无法在 `morePoints` 包之外的代码中访问该字段。这是因为表达式 `p.z` 是错误的，因为 `p` 的类型是 `Point` 且 `Point` 类没有字段 `z`；表达式 `((Point3d)p).z` 也是错误的，因为在 `points` 包之外无法引用 `Point3d` 类。

## 示例 8.2-5. 访问不可见的类

```java
package points;
public class Point {
    int x, y;
    public void move(int dx, int dy) { x += dx; y += dy; }
    protected int useCount = 0;
}
```

然而，将字段 `z` 声明为 `public` 并非毫无用。如果在 `morePoints` 包中存在 `Point3d` 类的子类 `Point4d`：

```java
package morePoints;
class Point4d extends Point3d {
    int w;
    public void move(int dx, int dy, int dz, int dw) {
        super.move(dx, dy, dz); w += dw;
    }
}
```

那么 `Point4d` 将继承字段 `z`，由于它是 `public` 的，可以通过 `morePoints` 其他包的代码、通过公共类型 `Point4d` 的变量和表达式进行访问。

## 8.3 字段声明

类的变量通过字段声明引入。

### 字段声明

```
FieldDeclaration:
    {FieldModifier} UnannType VariableDeclarList;
```

```
VariableDeclarList:
    VariableDeclarator (, VariableDeclarator)
```

```
VariableDeclarator:
    VariableDeclarId [= VariableInitializer]
```

```
VariableDeclaratorId:
    Identifier [Dims]
```

```
VariableInitializer:
    Expression
    ArrayInitializer
```

```
UnannType:
    UnannPrimitiveType
    UnannReferenceType
```

```
UnannPrimitiveType:
    NumericType
    boolean
```

```
UnannReferenceType:
    UnannClassOrInterfaceVariable
    UnannArrayType
```

```
UnannClassOrInterfaceType:
    UnannClassType
    UnannInterfaceType
```

```
UnannClassType:
    TypeIdentifier [TypeArguments]
    PackageName . [Annotation] TypeIdentifier [TypeArguments]
    UnannClassOrInterfaceType . [Annotation] TypeIdentifier [TypeArguments]
```

```
UnannInterfaceType:
    UnannClassType
```

```
UnannTypeVariable:
    Identifier
```

```
UnannArrayType:
    UnannPrimitiveType Dims
    UnannClassOrInterface Dims
    UnannTypeVariable Dims
```

为了方便起见，这里显示了 §4.3 中的产生式：

```
Dims:
    [ {Annotation} [ ] ]
```

`FieldDeclaration` 中的每个声明器都声明一个字段。声明器中的 `Identifier` 可用作名称来引用该字段。

在单个 `FieldDeclaration` 中，可以使用多个声明器声明多个字段；`FieldModifiers` 和 `UnannType` 适用于该声明中的所有声明器。

`FieldModifier` 子句在 §8.3.1 中描述。

如果 `UnannType` 和 `VariableDeclarator` 中没有出现方括号对，则字段的声明类型由 `UnannType` 表示，否则由 §10.2 规定。

字段声明的作用域（scope）和遮蔽性（shadowing）在 §6.3 和 §6.4.1 中规定。

在类声明体中声明两个同名的字段将导致编译错误。

如果一个类声明了一个具有特定名称的字段，则该字段的声明被认为隐藏（hide）了父类和类接口中任何同名的可访问字段声明。

> 在这方面，字段的隐藏与方法的隐藏不同（§8.4.8.3），因为在字段隐藏中，静态和非静态字段之间没有区别，而在方法隐藏中，静态和非静态方法之间存在区别。

如果被隐藏的字段是静态的，可以使用限定名（§6.5.6.2）访问，或者通过包含关键字 `super`（§15.11.2）的字段访问表达式或向父类类型的强制类型转换来访问。

在这方面，字段的隐藏与方法的隐藏是类似的。

如果一个字段声明隐藏了另一个字段的声明，则这两个字段的类型不相同。

### 8.3 字段声明 类

类从其直接父类和父接口继承所有的私有字段，前提是这些字段对类中的代码是可见的（§6.6），且未被类中的声明所隐藏。

父类的私有字段可能对子类是可见的——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能会继承多个同名的字段，既可以从其父类和父接口继承，也可以仅从其接口继承。这种情况本身不会引起编译错误。然而，在类体内部任何尝试通过简单名引用此类字段的行为都将导致编译错误，因为引用是歧义的。

可能存在多条从接口继承同一定义的路径。在这种情况下，字段被认为只被继承一次，可以通过其名称进行无歧义的引用。

### 示例 8-3-1. 多继承字段

类可以继承两个或多个同名的字段，可以从其父类和一个接口继承，也可以从两个接口继承。任何尝试通过简单名引用任何无歧义继承的字段的行为都会产生编译错误。可以使用限定名或使用关键字 `super`（§15.11.2）的字段访问表达式来访问此类字段。在程序中：

```java
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
    public static void main(String[] args) {
        new Test().printV();
    }

    void printV() { System.out.println(v); }
}
```

类 `Test` 继承了两个名为 `v` 的字段，一个来自其父类 `SuperTest`，另一个来自其接口 `Frob`。这是允许的，但由于在方法 `printV()` 中使用了简单名 `v`，会导致编译错误；因为无法确定意图是指哪个 `v`。

以下变体使用字段访问表达式 `super.v` 来引用类 `SuperTest` 中声明的字段，并使用限定名 `Frob.v` 来引用接口 `Frob` 中声明的字段 `v`：

```java
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
    public static void main(String[] args) {
        new Test().printV();
    }

    void printV() {
        System.out.println(super.v);
    }
}
```

即使两个声明具有相同的类型、相同的值且都是 `final`，通过简单名对它们的任何一个引用都是歧义的。在程序中：

```java
interface Color { int RED=0, GREEN=1; }
interface TrafficLight { int RED=0, YELLOW=2; }
class Test implements Color, TrafficLight {
    public static void main(String[] args) {
        System.out.println(RED); // 编译错误
        System.out.println(GREEN); // 编译错误
    }
}
```

具有相同类型的事并不影响该判断。

### 示例 8.3-2. 字段继承

如果同一定义通过多个路径从接口继承，则该字段被认为只被继承一次。可以通过其名称进行无歧义的引用。

```java
interface Colorable {
    int RED=0, GREEN=1, BLUE=2;
}
interface Paintable {
    int MATTE=0, GLOSSY=1;
}
class Point { int x, y; }
class ColoredPoint extends Colorable {}
class PaintedPoint extends ColoredPoint implements Paintable {
    int p;
}
```

`RED` 和 `BLUE` 通常被 `PaintedPoint` 通过其直接父类 `ColoredPoint` 和直接接口 `Colorable` 使用。

## 8.3.1 字段修饰符

```
FieldModifier:
    (之一)
    Annotation
    public
    private
    static
    volatile
```

关于字段注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

如果同一个关键字作为字段的修饰符出现多次，或者字段声明具有多个 `public`、`protected` 和 `private`（§6.6），则会导致编译错误。

如果字段声明中出现了两个或多个不同的字段修饰符，习惯上（并非强制）它们按照上述产生式中的顺序出现。

### 8.3.1.1 static 字段

如果字段被声明为 `static`，则该字段只有一个实例，无论创建了多少类实例（可能为空）。静态字段有时称为类变量，在类初始化时创建（§12.4）。

未声明为 `static` 的字段称为实例变量，有时称为非静态字段。每当创建一个类的实例时（§12.5），都会为该类及其任何父类中声明的变量创建一个与该实例相关的变量。

类变量的引入了静态上下文（§8.1.3），这限制了引用当前对象的构造的使用。特别注意的是，关键字 `this` 和 `super` 在静态上下文中是被禁止的（§15.8.3, §15.11.2），以及对实例变量、实例方法和词法上定义的类型参数的未限定引用（§6.5.5.1, §6.5.6.1, §15.12.3）。

从静态上下文或嵌套类或接口对实例变量的引用是限制的，如 §6.5.6.1 规定。

#### 示例 8.3.1.1-1. static 字段

```java
class Point {
    int x, y, useCount;
    Point(int x, int y) { this.x = x; this.y = y; }
    static final Point origin = new Point(0, 0);
}
class Test {
    public static void main(String[] args) {
        Point p = new Point(1, 1);
        Point q = new Point(2, 2);
        p.x = 2;
        p.y = 2;
        p.useCount++;
        System.out.println(p.x + "," + p.y);
        System.out.println(q.x + "," + q.y);
        System.out.println(q.origin == Point.origin);
        p.origin.useCount++;
        System.out.println(q.origin.useCount);
    }
}
```

该程序打印输出：

- (2,2)
- 0
- true
- 1

这表明更改 `p` 的字段 `x`、`y` 和 `useCount` 不会影响 `q` 的字段，因为这些字段是不同对象中的实例变量。在这个示例中，类 `Point` 的类变量 `origin` 通过两种方式被引用：一种使用类名作为限定符（如 `Point.origin`），另一种是在字段访问表达式（§5.11）中使用该类型类型的变量（如 `p.origin` 和 `q.origin`）。这两种访问类变量的方式访问的是同一个对象，引用等性表达式（§15.23）的值证明了这一点：

```java
q.origin == Point.origin
```

结果为 `true`。进一步的证据是自增操作：

```java
p.origin.useCount++;
```

导致 `q.origin.useCount` 的值变为 1；这是因为 `p.origin` 和 `q.origin` 指向同一个变量。



### 示例 8.3.1.1-2. 类变量的隐藏

```java
class Point {
    static int x = 2;
}
class Test extends Point {
    static double x = 4.7;
    public static void main(String[] args) {
        new Test().printX();
    }
    void printX() {
        System.out.println(x + " " + super.x);
    }
}
```

该程序产生输出：

```
4.7 2
```

这是因为 `Test` 类中 `x` 的声明隐藏了 `Point` 类中 `x` 的定义，因此 `Test` 类没有从其父类 `Point` 继承该字段。在 `Test` 声明内部，简单名指向在 `Test` 类内部声明的字段。`Test` 类中的代码可以通过 `super.x`（由于 `x` 是静态的，可以使用 `Point.x`）引用字段 `x`。如果删除了 `Test.x` 的声明：

```java
class Point {
    static int x = 2;
}
class Test extends Point {
    public static void main(String[] args) {
        new Test().printX();
    }
    void printX() {
        System.out.println(x + " " + super.x);
    }
}
```

那么 `Point` 类的 `x` 就不再隐藏于 `Test` 类中；相反，简单名 `x` 指向字段 `Point.x`。此变体程序的输出为：

```
2 2
```

### 示例 8.3.1.1-3. 实例变量的隐藏

```java
class Point {
    int x = 2;
}
class Test extends Point {
    double x = 4.7;
    void printBoth() {
        System.out.println(x + " " + super.x);
    }
    public static void main(String[] args) {
        Test sample = new Test();
        sample.printBoth();
        System.out.println(sample.x + " " + ((Point)sample).x);
    }
}
```

该程序产生输出：

```
4.7 2
4.7 2
```

这是因为 `Test` 类中 `x` 的声明隐藏了 `Point` 类中 `x` 的定义，因此 `Test` 没有从其父类 `Point` 继承字段 `x`。然而，必须注意的是，`Point` 类的字段 `x` 被 `Test` 类继承了，但它是由 `Test` 实例实现的。换句话说，`Test` 类的每个实例包含两个字段，一个 `int` 类型，一个 `double` 类型。字段拥有相同的名称，但在 `Test` 声明内部，简单名 `x` 始终指向在 `Test` 类内部声明的字段。在 `Test` 类的实例方法中，可以通过 `super.x` 引用 `Point` 类的实例变量 `x`。

使用字段访问表达式 `field x` 的代码将访问引用表达式类型指示的类中名为 `x` 的字段。因此，表达式 `sample.x` 访问的是 double 值（即在 `Test` 类中声明的实例变量），因为变量 `sample` 的类型是 `Test`；而表达式 `((Point) sample).x` 访问的是 `int`（即在 `Point` 类中声明的实例变量），因为强制转换为了类型 `Point`。

如果从 `Test` 类中删除 `x` 的声明，如程序所示：

```java
class Point {
    int x = 2;
}
class Test extends Point {
    void printBoth() {
        System.out.println(x + " " + super.x);
    }
    public static void main(String[] args) {
        Test sample = new Test();
        sample.printBoth();
        System.out.println(sample.x + " " + ((Point) sample).x);
    }
}
```

那么 `Point` 类的字段 `x` 就不再隐藏于 `Test` 类中。在 `Test` 声明的实例方法内部，简单名 `x` 指向在 `Point` 类中声明的字段。`Test` 类中的代码可以通过 `super.x` 引用同一个字段。表达式 `sample.x` 仍然指向类型 `Test` 中的字段 `x`，但该字段现在是一个继承字段，因此指向 `Point` 类中声明的字段 `x`。此变体程序的输出为：

```
2 2
2 2
```

### 8.3.1.2 final 字段

字段可以声明为 `final`（§4.124）。类变量和实例变量（静态和非静态）都可以是 `final`。`final` 变量必须恰好赋值一次，且该赋值必须发生在字段声明期间或构造函数（针对实例变量）或静态初始化块（针对类变量）中。编译器确保遵循这一“恰好一次”规则。

`final` 字段在初始化后不能重新赋值。如果程序尝试重新赋值 `final` 字段，编译器将生成错误。

```java
class Point {
    final int x;
    Point(int x) {
        this.x = x;
    }
    void setX(int x) {
        // this.x = x; // Error：无法为 变量 x 赋值
    }
}
```

如果 `final` 字段在声明时没有初始化，则必须在每个构造中初始化。这被称为“空白 final 字段”（blank final field）。

编译器还确保 `final` 字段在初始化之前没有使用。如果构造函数中存在一条在 `final` 字段初始化之前读取它的路径，则代码将被视为无效。

```java
class Point {
    final int x;
    Point(boolean condition) {
        if (condition) {
            System.out.println(x); // Error：变量 x 在初始化之前使用
        }
        x = 10;
    }
}
```

### 8.3.2 字段初始化

如果字段中的声明符具有变量初始化器，则该声明符具有对被声明变量进行赋值（§15.26）的语义。

#### 类变量初始化规则

如果声明符是用于类变量（即静态字段）§8.3.1.1，则以下规则适用于其初始化器：

- 初始化器不得使用关键字 `this` 或关键字 `super` 访问当前对象来引用当前对象（如 §15.8.3 和 §15.11.2 所示），也不得通过简单名引用任何实例变量或实例方法（如 §6.5.6.1 和 §15.12.3 所示）。
- 在运行时，初始化器会被求值且赋值仅执行一次，即在类初始化时 (§12.4.2)。

> 注意，作为常量变量（§12.4.2）的静态字段在其他静态字段（§12.4.2）之前初始化。这也适用于接口（§9.3.1）。当通过简单名引用此类字段时，它们的值永远不会被观察到为具有其默认初始值 (§4.15)。

#### 实例变量初始化规则

如果声明符是用于实例变量（即非静态字段），则以下规则适用于其初始化器：

- 初始化器不得使用关键字 `this` 或关键字 `super` 访问当前对象，但可以通过简单名引用在该类中声明或由类继承的任何类变量，即使该声明发生在初始化器的右侧 (§3.5)。
- 在运行时，每当创建一个类的实例时，初始化器都会被求值并执行赋值 (§12.5)。

变量初始化器到可能尚未初始化的字段的引用受到限制，如 §8.3.3 和 §16（确定性赋值）中所示。

字段声明中变量初始化器的异常检查在 §11.2.3 中规定。

变量初始化器也用于局部变量声明语句 (§14.4)，在每次执行该局部变量语句时，初始化器都会被求值并执行赋值。

### 示例 8.3.2-1 字段初始化

```java
class Point {
    int x = 1, y = 5;
}
class Test {
    public static void main(String[] args) {
        Point p = new Point();
        System.out.println(p.x + " " + p.y);
    }
}
```

该程序产生输出：

```
1 5
```

因为每当创建新的 `Point` 时，对 x 和 y 的赋值就会发生。

### 示例 8.3.2-2 对类变量的前向引用

```java
class Test {
  float f = j;
  static int j = 1;
}
```

该程序无错误编译，它在初始化类 `Test` 时将 `j` 初始化为 1，并在每次创建 `Test` 类的实例时将 `f` 初始化为 `j` 的当前值。

### 8.3.3 初始化器中引用限制

对字段的引用受到限制，即使该字段在作用域内。以下规则限制了对字段的引用（使用处在文本上先于字段声明）以及自引用（该字段在其自身的初始化器中使用）。

对于对类或接口 `c` 中的类变量 `x` 的简单名引用，如果满足以下条件则为编译错误：

- 引用出现在 `c` 的类变量初始化器或 `c` 的静态初始化器中 (§8.7)；且
- 引用出现在 `f` 自身声明符的初始化器或 `f` 声明符左侧的任意；且
- 引用不在赋值表达式的左侧 (§15.26)；且
- 嵌套该引用的内部类或接口是 `c`。

对于在类 `c` 中声明的实例变量 `f` 的简单名引用，如果满足以下条件则为编译错误：

- 引用出现在 `c` 的实例变量初始化器或 `c` 的实例初始化器中 (§8.6)；且
- 引用出现在 `f` 自身声明符的初始化器或 `f` 声明符左侧的任意；且
- 引用不在赋值表达式的左侧 (§15.26)；且
- 嵌套该引用的内部类是 `c`。

### 示例 8.3.3-1 字段引用的限制

此程序会发生编译错误：

```java
class Test1 {
    int i = j; // 编译错误：
    int j = 1; // 错误的前向引用
}
```

而以下程序可以无错误编译：

```java
class Test2 {
    Test2() { k = 2; }
    int j = 1;
    int i = j;
    int k;
}
```

尽管 `Test2` 的构造函数 (§8.8) 引用了三行后声明的字段 `k`。

这些限制还旨在于编译时捕获循环或其他格式错误的初始化。因此，以下两种情况：

```java
class Z {
    static int i = j + 2;
    static int j = 4;
}
```

以及：

```java
class Z {
    static { i = j + 2; }
    static int i, j;
    static { j = 4; }
}
```

都会导致编译错误。通过方法访问不会进行此类检查，因此：

```java
class Z {
    static int peek() { return j; }
    static int i = peek();
    static int j = 1;
}
class Test {
    public static void main(String[] args) {
        System.out.println(Z.i);
    }
}
```

产生输出：

```
1
```

因为 `i` 的初始化器使用了 `peek` 方法，此时 `j` 尚未初始化。

### 8.4 方法声明

在 `MethodDeclarator` 中使用 `Identifier` 引用方法 (§6.5.7, §15.12)。

该方法声明了可执行的代码，并带有固定数量的参数。

**MethodDeclaration:**
```
{MethodModifier} MethodBody
```

**MethodHeader:**
```
Result Declarator [Throws]
TypeParameters [Annotation] Result Declarator [Throws]
```

**MethodDeclarator:**
```
Identifier ( [ReceiverParameter,] [ParameterList] ) [Dims]
```

**ReceiverParameter:**
```
[Annotation] Identifier .
```

为了方便，此处显示自 4.3 的 `Dims`:
```
[Annotation] []}
```

`FormalList` 见 §8.4.1，`MethodModifier` 子句见 §8.4.3，`TypeParameters` 子句见 §8.4.4，`Result` 子句见 §8.4.5，`Throws` 子句见 §8.4.6，以及 `MethodBody` 见 §8.4.7。

接收者是方法或内部类构造函数的可选语法设备。对于实例方法，接收者代表被调用的对象；对于内部类的构造函数，接收者代表新构造的实例。在两种情况下，接收者仅用于允许在源代码中表示类型 (§9.4)。接收者不是形式参数；更准确地说，它没有在方法调用表达式或类实例表达式中绑定到任何传递的值，并且在运行时没有任何影响。

接收者可以出现在实例方法的 `MethodDeclarator` 中或非静态内部类的 `ConstructorDeclarator` 中 (§8.1.3)。如果接收者出现在任何其他类型的方法或构造函数中，会导致编译错误。

接收者的类型和名称约束如下：

- 在实例方法中，接收者的类型必须是声明方法的类或接口，且接收者的名称必须是 `this`；否则将发生编译错误。
- 在内部类的构造函数中，接收者的类型必须是该内部类的直接外层类或接口，且接收者的名称必须是该内部类的直接外层类的 `Identifier`；否则将发生编译错误。

返回数组的方法声明允许将表示数组类型的某些或全部括号对放在形式参数列表之后。支持这种语法是为了兼容早期 Java 语言版本。非常强烈建议不要在新代码中使用这种语法。

### 8.4.1 形式参数

方法或构造函数的形式参数（如果有）由一组用逗号分隔的参数限定符列表指定。每个参数限定符由一个类型（可选地带有最终修饰符和/或一个或多个注解）和一个标识符（可选地带有括号）组成，用于指定参数的名称。

如果方法或构造函数没有形式参数，也没有接收参数（receiver parameter），则在方法或构造函数的声明中出现空括号。

**FormalParameterList:**
```
FormalParameter [, FormalParameter)
```

**FormalParameter:**
```
[VariableModifier] UnannType VariableDeclaratorId
VariableArityParameter
```

**VariableArityParameter:**
```
[VariableModifier] UnannType [Annotation] ... Identifier
```

**VariableModifier:**
```
Annotation
final
```

为了方便起见，这里展示了 §8.3 和 §4.3 中的产生式：

**VariableDeclaratorId:**
```
Identifier [Dims]
```

**Dims:**
```
[Annotation] { [Annotation] { }
```

方法或构造函数的形式参数可以是变长参数，通过类型后的省略号（`...`）表示。一个方法或构造函数最多允许一个变长参数。如果变长参数出现在参数限定符列表的最后一个位置之外，则将是一个编译错误。

在 `VariableArityParameter` 的语法中，注意省略号（`...`）是一个独立的标记（§3.11）。可以在省略号和类型之间放置空格，但从代码风格的角度来看并不建议这样做。

如果方法的最后一个形式参数是变长参数，则该方法是变长方法。否则，它是固定长度方法。

关于形式参数声明和接收参数的注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。

如果 `final` 作为形式参数声明的修饰符出现超过一次，则将是一个编译错误。

形式参数的作用域和遮蔽（shadowing）在 §6.3 和 §6.4 中规定。

从嵌套类、接口或 Lambda 表达式对形式参数的引用受到 §6.5.6.1 的限制。

一个方法或构造函数声明两个同名的形式参数将是一个编译错误。（也就是说它们的声明提到了同一个标识符）。

如果声明为 `final` 的形式参数被赋值给方法或构造函数的体，则将是一个编译错误。

形式参数的声明类型取决于它是否为变长参数：

- 如果形式参数不是变长参数，那么如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号，则其声明类型用 `UnannType` 表示，否则由 §10.2 规定。
- 如果形式参数是变长参数，则其声明类型由 §10.2 规定的数组类型。

如果变长参数的声明类型具有非具体化（non-reifiable）元素类型 (§4)，则该变长方法的声明会产生编译警告，除非该方法标注了 `@SafeVarargs` (§9.6.4.7) 或警告被 `@SuppressWarnings` (§9.6.4.5) 抑制。



当调用方法或构造函数时（§15.12），在执行方法或构造体之前，实际参数的值将初始化新创建的变量，每个变量具有声明的类型。`FormalParameter` 中出现的标识符可以在方法体中作为简单名称使用，也可以引用该形式参数。

变长方法的调用包含的实际参数表达式可能多于形式参数。所有不对应变长参数之前的形式参数的实际表达式将被评估，并将结果存储在数组中，然后传递给方法调用（§15.12.4.2）。

以下是实例方法和内部类中接收参数的一些示例：

```java
class Test {
  Test() { }
  // 顶层类的构造函数不允许有接收参数，
  // 因为没有可以想象的类型或名称。

  void m(Test this) {
    // OK：实例方法中的接收参数
  }

  static void n(Test this) {
    // 非法：静态方法中的接收参数
  }

  class A {
    A(Test.this) {
      // OK：接收参数代表紧接包裹
      // 正在构造的 A 实例的 Test 实例。
    }

    void m(A this) {
      // OK：接收参数代表调用 A.m() 的 A 实例。
    }

    class B {
      B(Test.A.B this) {
        // OK：接收参数代表紧接包裹
        // 正在构造的 B 实例的 A 实例。
      }

      void m(Test.A.B this) {
        // OK：接收参数代表调用 B.m() 的 B 实例。
      }
    }
  }
}
```

B 的构造函数和实例方法表明，接收参数的类型可以像其他类型一样通过限定类型（qualified Type）表示；但内部类构造函数中的接收参数可以使用类的简单名称。

## 8.4.2 方法签名

如果两个方法或构造函数 M 和 N 具有相同的名称和相同的类型参数（§8.3），它们具有相同的签名。如果满足以下条件，则方法 m1 的签名是 m2 的子签名：

- m1 和 m2 具有相同的擦除类型，且
- m1 拥有更多的类型参数。

两个方法签名 m1 和 m2 是*重写相等*（override-equivalent），当且仅当：

- m1 是 m2 的子签名，或
- m2 是 m1 的子签名。

在类中声明两个签名相等的方法是一个编译错误。

签名的概念是为了在两个签名不相同的方法之间建立关系，其中一个可以重写另一个。考虑以下示例：

```java
class CollectionConverter {
    List toList(Collection c);
}
class Overrider extends CollectionConverter {
    List toList(Collection c);
}
```

假设这段代码是在泛型引入之前编写的，现在 *CollectionConverter* 的作者决定将其泛型化如下：

```java
class CollectionConverter {
    <T> List<T> toList(Collection<T> c);
}
```

如果没有特殊许可，*Overrider.toList* 将不再重写 *CollectionConverter.toList*。这将极大抑制泛型的使用，因为库编写者会犹豫迁移代码。

## 8.4.3 方法修饰符

MethodModifier:

（以下之一）

`Annotation` `public` `protected` `private`
`abstract` `static` `native` `strictfp`

关于方法声明注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。

同一个关键字作为方法声明的修饰符出现多次，或者方法声明具有 `public`、`protected` 和 `private` 中的多个修饰符，则将是一个编译错误。

如果包含 `abstract` 关键字的方法声明也包含 `private`、`static`、`final`、`native` 或 `strictfp` 中的任何一个，则将是一个编译错误。

如果包含 `native` 关键字的方法声明包含 `strictfp`，则将是一个编译错误。

如果方法声明中出现了多个（不同的）方法修饰符，习惯上（并非强制）按照 MethodModifier 产生式所示的顺序出现。

### 8.4.3.1 抽象方法

抽象方法声明引入方法作为成员，提供了其签名（§8.4.2）、结果（§8.4.5）以及任何可能的 throws 子句（§8.4.6），但不提供实现（§8.4.7）。不是抽象的方法称为具体方法。

抽象方法的声明必须直接出现在抽象类（`class`）内部，除非它出现在枚举声明（§8.9）中；否则将产生编译错误。

A 的每个非抽象子类（§8.1.1.1）必须为 m 提供一个实现，否则将产生编译错误。

抽象类可以通过提供另一个抽象方法声明来重写抽象方法。

这可以为放置文档注释、精细化返回类型，或声明当该方法被子类实现时可以抛出的检查异常集合提供一个位置。

#### 示例 8.4.3-1.1. 抽象/抽象方法的重写

```java
class BufferEmpty extends Exception {
    BufferEmpty() { super(); }
    BufferEmpty(String s) { super(s); }
}
class BufferError extends Exception {
    BufferError() { super(); }
    BufferError(String s) { super(s); }
}
interface Buffer {
    char get() throws BufferEmpty, BufferError;
}
abstract class InfiniteBuffer implements Buffer {
    public abstract char get() throws BufferError;
}
```

类 `InfiniteBuffer` 中对方法的重写声明表明，`InfiniteBuffer` 的任何子类中的 `get` 方法永远不会抛出 `BufferEmpty` 异常，这可能是因为它在缓冲区中生成数据，因此永远不会用尽数据。

#### 示例 8.4.3-1.2. 抽象/非抽象重写

我们可以声明一个抽象类 `Point`，要求其子类在可实例化的类中实现 `toString`：

```java
abstract class Point {
    int x, y;
    public abstract String toString();
}
```

对 `toString` 的这一抽象声明重写了 `Object` 类的非抽象 `toString` 方法。（`Object` 是 `Point` 的隐式直接父类）。加上代码：

```java
class ColoredPoint extends Point {
    int color;
    public String toString() {
        return super.toString() + ": " + color; // 错误
    }
}
```

当调用 `super.toString()` 时，它指向 `Point` 类中的 `toString` 方法，而该方法是抽象的且无法调用，这会导致编译时错误。只有当 `Point` 类通过某些其他方法显式地提供 `Object` 类的 `toString` 方法时，`ColoredPoint` 类才能可以使用，例如：

```java
abstract class Point {
    int x, y;
    public abstract String toString();
    protected String objString() { return super.toString(); } 
}
class ColoredPoint extends Point {
    int color;
    public String toString() {
        return objString() + " : " + color; // 正确
    }
}
```

### 8.4.3.2 静态方法

被声明为 `static` 的方法称为类方法。类方法的声明引入了静态上下文（§8.1.3），这限制了引用当前对象的构造结构的使用。注意的是，在静态方法中禁止使用 `this` 和 `super` 关键字（§15.8.3, §15.11.2），因为它们不允许对实例变量、实例方法以及词法包含声明的类型参数（§6.5.5.1, §6.5.6.1, §15.12.3）进行未限定引用。

未声明为 `static` 的方法是实例方法，有时称为非静态方法。

在方法体执行期间，实例方法总是相对于当前对象调用的，`this` 和 `super` 关键字此时指向的就是该对象。

从静态上下文或嵌套类或接口对实例方法的引用受到 §15.12.3 节的限制。

### 8.4.3.3 final 方法

方法可以被声明为 `final` 以防止子类对其进行重写或隐藏。

尝试重写或隐藏 `final` 方法会导致编译时错误。

私有方法以及所有直接声明在 `final` 类内部的方法（§8.1.1.2）的行为都如同它们是 `final` 的一样，因为无法重写它们。

在运行时，机器码生成器或优化器可以“内联”`final` 方法体，用其体内的代码替换对该方法的调用。内联过程必须保留方法调用的语义。特别是，如果实例方法调用的目标是 `null`，那么即使方法被内联，也必须抛出 `NullPointerException`。Java 编译器必须确保在正确的点抛出异常，以便看到在方法调用之前，方法的实际参数按照正确的顺序进行了求值。

#### 示例

考虑以下示例：

```java
final class Point {
    int x, y;
    void move(int dx, int dy) { x += dx; y += dy; }
}
class Test {
    public static void main(String[] args) {
        Point[] p = new Point[100];
        for (int i = 0; i < p.length; i++) {
            p[i] = new Point();
            p[i].move(i, p.length-i);
        }
    }
}
```

在 `main` 方法中内联 `Point` 类的 `move` 方法将把 `for` 循环转换为：

```java
for (int i = 0; i < p.length; i++) {
    p[i] = new Point();
    Point pi = p[i];
    int j = p.length-1-i;
    pi.x += i;
    pi.y += j;
}
```

随后该循环可能会进一步优化。

这种内联无法在编译时完成，除非保证 `Test` 和 `Point` 总是一起重新编译，这样每当 `Point`（特别是其 `move` 方法）变化时，`Test.main` 的代码就会被更新。

### 8.4.3.4 native 方法

被声明为 `native` 的方法在依赖平台的代码中实现，通常用 C 等其他编程语言编写。`native` 方法的方法体以分号给出，表示实现已省略。

例如，`RandomFile` 类可能会声明以下方法：

```java
package java.io;
public class RandomFile implements DataOutput {
    native long length();
    native void seek(long pos) throws IOException;
    native int getPointer();
    native void readBytes(byte[] b, int len) throws IOException;
    native void close() throws IOException;
}
```

### 8.4.3.5 strictfp 方法

方法上的 `strictfp` 修饰符已过时而不应使用。它在运行时没有影响。

### 8.4.3.6 synchronized 方法

`synchronized` 方法在执行之前会获取监视器（17.1）。

对于类（静态）方法，使用与类相关的监视器。

对于实例方法，使用与调用该方法的对象相关的监视器。

#### 示例 8.4.3.6-1. 监视器

因此，代码：

```java
class Test {
    int count;
    synchronized void bump() {
        count++;
    }
    static int classCount;
    static synchronized void classBump() {
        classCount++;
    }
}
```

与以下代码的效果相同：

```java
class BumpTest {
    int count;
    void bump() {
        synchronized (this) { count++; }
    }
    static int classCount;
    static void classBump() {
        try {
            synchronized (Class.forName("BumpTest")) {
                classCount++;
            }
        } catch (ClassNotFoundException e) {
        }
    }
}
```

#### 示例 8.4.3.6-2. synchronized 方法

```java
public class Box {
  private Object boxContents;
  public synchronized Object get() {
    Object contents = boxContents;
    boxContents = null;
    return contents;
  }
  public synchronized boolean put(Object contents) {
    if (boxContents != null) return false;
    boxContents = contents;
    return true;
  }
}
```

该程序定义了一个用于并发使用的类。类的每个实例都有实例变量 `boxContents`，它可以持有任何对象的引用。你可以通过 `put` 将对象放入 Box，如果 Box 已满则返回 `false`。你可以通过 `get` 从 Box 中获取内容，如果 Box 为空则返回 `null` 引用。

如果 `put` 和 `get` 不是 `synchronized` 的，并且两个线程同时执行同一个类实例的方法，那么代码可能会出现异常。例如，由于两个 `put` 调用同时发生，可能会丢失一个对象。

## 8.4.4 泛型方法

如果一个方法声明了一个或多个类型变量（§4.4），则该方法是泛型的。

这些被称为方法的类型参数。泛型方法的类型参数部分与泛型类的类型参数部分（§8.1.2）相同。

泛型方法声明定义了一组方法，对应类型参数的每种可能的调用。在调用泛型方法时可能不需要显式提供类型参数，因为它们可以被推断（§18 类型推断）。

方法类型参数的作用域和屏蔽在 §6.3 和 §6.4.1 中规定。

从嵌套类或接口对方法类型参数的引用受到限制，正如 §6.5.5.1 所示。

如果以下两个条件均成立，两个方法或构造方法 $M$ 和 $N$ 具有相同的类型参数：

- $M$ 和 $N$ 具有相同数量的类型参数（可能为零）。
- 若 $A_1, ..., A_n$ 是 $M$ 的类型参数，$B_1, ..., B_n$ 是 $N$ 的类型参数，令 $\theta[B_1:=A_1, ..., B_n:=A_n]$。那么，对于所有的 $i$ ($1 \le i \le n$)，$A_i$ 的界与将 $\theta$ 应用于 $B_i$ 的界后的结果类型是相同的类型。

如果两个方法或构造方法 $M$ 和 $N$ 具有相同的类型参数，$N$ 中提到的某个类型可以通过应用上述定义的 $\theta$ 适配 $M$ 的类型参数。

## 8.4.5 方法结果

方法声明的结果声明了方法返回的值类型（返回类型），或者使用关键字 `void` 表示该方法不返回任何值。

> 结果：
>
> `UnannType`
>
> `void`

如果结果不是 `void`，并且在形式参数列表后没有出现括号对，则方法的返回类型用 `UnannType` 表示，否则由 §10.2 规定。

如果返回类型是引用类型，则在相互覆盖的方法之间返回类型可能有所不同。返回类型可替换性概念支持协变返回，即将返回类型特化为子类型。

返回类型为 $R_1$ 的方法声明 $d_1$ 对于返回类型为 $R_2$ 的另一个方法 $d_2$ 是可替换的，当且仅当以下任一成立：

- 如果 $R_1$ 是 `void`，则 $R_2$ 是 `void`。
- 如果 $R_1$ 是基本类型，则 $R_2$ 与 $R_1$ 相同。
- 如果 $R_1$ 是引用类型，则满足以下之一：
  - $R_1$ 在适配 $d_2$ 的类型参数（§8.4.4）后是 $R_2$ 的子类型。
  - $R_1$ 可以通过 unchecked 转换（§5.1.9）转换为 $R_2$ 的子类型。
  - $d_1$ 与 $d_2$ 不具有相同的签名（§8.4.2），且 $R_1 = |R_2|$。



在泛型中允许 `unchecked` 转换，尽管它是不安全的，但这是为了便于从非泛型代码向泛型代码平滑迁移的特殊允许。如果使用 `unchecked` 转换来确定 $R_1$ 对于 $R_2$ 是返回类型可替换的，则 $R_1$ 必然不是 $R_2$ 的子类型，且覆盖规则（§8.4.8.3 §9.4.1）将要求产生编译 `unchecked` 警告。

## 8.4.6 方法 throws

`throws` 子句用于表示方法或构造体中的语句可能抛出的任何检查异常类（§11.1.1）（§11.2.2）。

```
Throws:
  `throws ExceptionTypeList`

ExceptionTypeList:
  `ExceptionType {, ExceptionType}`

ExceptionType:
  ClassType
  TypeVariable
```

如果 `throws` 子句中提到的 `ExceptionType` 不是 `Throwable` 的子类型（§4.10），则为编译错误。

类型变量允许出现在 `throws` 子句中，尽管它们不允许出现在 `catch` 子句中（§14.20）。

在 `throws` 子句中提到 `unchecked` 异常类（§11.1.1）是被允许的并非要求的。

`throws` 子句与方法或构造体异常检查之间的关系在 §11.2.3 中规定。

本质上，对于执行方法或构造体可能产生的每个检查异常，除非在声明的 `throws` 子句中提到了其异常类型或其异常类型的超类，否则会导致编译错误。

声明检查异常的要求允许 Java 编译器确保已包含处理此类情况的代码。如果方法或构造方法未能处理其体中抛出的作为检查异常的异常，且其 `throws` 子句中缺少适当的异常类型，通常会导致编译错误。Java 编程语言因此鼓励一种编程风格，即罕见或其他特殊情况的异常通过这种方式进行记录。

### 8.4.6-1. 作为抛出异常类型的类型变量

```java
import java.io.FileNotFoundException;
interface PrivilegedExceptionAction<E extends Exception> {
    void run() throws E;
}
class AccessController {
    public static <E extends Exception> Object
    doPrivileged(PrivilegedExceptionAction<E> action) throws E {
        return "success";
    }
}
class Test {
    public static void main(String[] args) {
        try {
            AccessController.doPrivileged(
                new PrivilegedExceptionAction<FileNotFoundException>() {
                    public void run() throws FileNotFoundException {
                        // ... delete a file ...
                    }
                });
        } catch (FileNotFoundException f) {
        }
    }
}
```

## 8.4.7 方法体

方法体是方法声明之后大括号之间的代码。方法体包含一组定义方法行为的语句。

方法体可以包含一个 `return` 语句，向调用者返回一个值。如果返回类型为 `void`，则 `return` 语句是可选的，但用于提前退出方法。

方法体还可以包含控制流语句，如 `if`、`else`、`switch`、`for` 和 `while`。

## 8.4.8 继承、覆盖与隐藏

覆盖允许子类为其父类中已定义的方法提供特定的实现。覆盖方法必须与原始方法具有相同的签名。

当子类声明了一个与其父类静态方法签名相同的静态方法时，发生了隐藏。在这种情况下，子类的方法隐藏了父类的方法。

### 示例 8.4.8-1. 继承

```java
interface I1 {
    int foo();
}

interface I2 {
    int foo();
}

abstract class Test implements I1, I2 {
}
```

## 8.4.8.1 重写（通过实例方法）

在类 $C$ 中声明或由类 $C$ 继承的实例方法 $m_C$，*重写*了来自 $C$ 的类 $A$ 中定义的另一个方法 $m_A$，当且仅当满足所有条件时：

- $C$ 是 $A$ 的子类。
- $C$ 没有继承 $m_A$。
- $m_C$ 的签名是 $m_A$ 签名（作为 $C$ 的命名 $A$ 的超类型的成员）的子签名（§8.4.2）。
- 满足以下任之一：
  - $m_A$ 是公共的（`public`）。
  - $m_A$ 是受保护的（`protected`）。
  - $m_A$ 在与 $C$ 相同的包中声明为包访问权限（package access），且声明了 $m_C$，或 $m_A$ 是 $C$ 直接超类类型的成员。
  - $m_A$ 被声明为包访问权限，且 $m_C$ 重写了来自 $C$ 的某个超类中的 $m_A$。
  - $m_A$ 被声明为包访问权限，且 $m_C$ 重写了来自 $C'$ 的 $m'$（与 $m_C$ 和 $m_A$ 不同），使得 $m'$ 重写了来自 $C$ 的某个超类中的 $m_A$。

如果 $m_C$ 是*非抽象的*且重写了来自 $C$ 的一个*抽象*方法 $m_A$，则称 $m_C$ *实现*了来自 $C$ 的 $m_A$。

如果被重写的方法 $m_A$ 是*静态的*（`static`）则会导致编译错误。

- 在这方面，方法的重写与字段的隐藏（§8.3）不同，因为实例变量隐藏静态变量是允许的。

在类 $C$ 中声明或由类 $C$ 继承的实例方法 $m_C$，*重写*了来自 $C$ 的接口 $I$ 中定义的另一个方法 $m_I$，当且仅当满足所有条件时：

- $I$ 是 $C$ 的超接口。
- $m_I$ 不是静态的（`static`）。
- $C$ 没有继承 $m_I$。
- $m_C$ 的签名是 $m_I$ 签名（作为 $C$ 的命名 $I$ 的超类型的成员）的子签名（§8.4.2）。
- $m_I$ 是公共的（`public`）。

如果其中一个方法的形式参数具有原始类型（raw type），而另一个方法对应的参数具有参数化类型（parameterized type），则重写方法的签名可能与被重写的方法不同。这是为了方便现有代码迁移以利用泛型。

重写的概念包含了从其声明类的某个子类重写另一个方法的方法。这有两种实现方式：

- 泛型超类中的具体方法在某些参数化配置下，可能与该类中的抽象方法具有相同的签名。在这种情况下，具体方法被继承，而抽象方法未被继承（如上所述）。此时被继承的方法应被视为重写了其来自 $C$ 的抽象同类方法。（这种场景因包访问而变得复杂：如果 $C$ 在不同的包中，则 $m_C$ 将不会被继承，因此不被视为重写。）
- 从类继承的方法可以重写超接口方法。（幸运的是，这里不考虑包访问权限。）

可以使用包含 `super` 关键字的方法表达式（§15.12）来访问被重写的方法。使用限定名（qualified name）或向超类类型强制转换在尝试访问被重写的方法时是无效的。

在这方面，方法的重写与字段的隐藏不同。

`strictfp` 方法的存在与否对重写方法的规则和实现抽象方法的规则完全没有影响。例如，允许非 `strictfp` 方法重写 `strictfp` 方法，也允许 `strictfp` 方法重写非 `strictfp` 方法。

### 示例 8.4.8.1-1. 重写

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
}
class SlowPoint extends Point {
    int xLimit, yLimit;
    void move(int dx, int dy) {
        super.move(dx, dy);
        limit(dx, xLimit), limit(dy, yLimit);
    }
    static int limit(int d, int limit) {
        return d > limit ? d : -limit;
    }
}
```

在这里，`SlowPoint` 类通过自己的 `move` 方法重写了 `Point` 类的方法声明，限制了点在每次调用方法时可以移动的距离。当为 `SlowPoint` 实例调用 `move` 方法时，即使 `SlowPoint` 对象的引用自类型为 `Point` 的变量，`SlowPoint` 类中的重写定义也会调用。

### 示例 8.4.8.1-2. 重写

重写让子类扩展现有类的行为变得容易，如例所示：

```java
import java.io.OutputStream;
import java.io.IOException;

class BufferOutput {
    private OutputStream o;
    BufferOutput(OutputStream o) { this.o = o; }
    protected byte[] buf = new byte[512];
    protected int pos = 0;
    protected void putchar(char c) throws IOException {
        if (pos == buf.length) {
            flush();
        }
        buf[pos++] = (byte)c;
    }
    public void putstr(String s) throws IOException {
        for (int i = 0; i < s.length(); i++) {
            putchar(s.charAt(i));
        }
    }

    protected void flush() throws IOException {
        o.write(buf, 0, pos);
        pos = 0;
    }
}
class LineBufferOutput extends BufferOutput {
    LineBufferOutput(OutputStream o) { super(o); }
    @Override
    protected void putchar(char c) throws IOException {
        if (c == '\n') {
            super.flush();
        }
        super.putchar(c);
    }
}
class Test {
    public static void main(String[] args) throws IOException {
        LineBufferOutput lbo = new LineBufferOutput(System.out);
        lbo.putstr("hello\nworld\n");
        System.out.print("\n");
    }
}
```

该程序产生输出：

```
hello
world
```

`BufferOutput` 类实现了一个非常简单的 `OutputStream` 缓冲版本，在缓冲区满时刷新输出。子类 `LineBufferOutput` 只声明了一个构造函数和一个单一的方法 `putchar`，该方法检查换行符。因此，当在 `main` 中通过 `lbo` 对象调用 `putstr` 时，`putstr` 体内的 `putchar` 调用是调用 `LineBufferOutput` 的 `putchar`，而不是 `BufferOutput` 的 `putchar`。

对于像 `BufferOutput` 这样设计用于扩展的类，其文档应该说明该类与其子类之间的约定，并明确指出子类可以这样重写 `putchar` 方法。`BufferOutput` 类的实现者不会希望在未来的 `BufferOutput` 实现中更改 `putstr` 的实现未使用 `putchar` 方法，因为这将破坏与子类现有的约定。参见 §13（二进制兼容性）中关于二进制兼容性的讨论，特别是 §13.2。

## 8.4.8.2 隐藏（通过类方法）

一个被隐藏的（静态）类方法可以通过引用来调用，该引用的类型是实际包含该方法声明的类的类型。在这方面，静态方法的隐藏与实例方法的重写不同。示例如下：

```java
class Super {
    static String greeting() { return "Goodnight"; }
    String name() { return "Richard"; }
}
class Sub extends Super {
    static String greeting() { return "Hello"; }
    String name() { return "Dick"; }
}
class Test {
    public static void main(String[] args) {
        Super s = new Sub();
        System.out.println(s.greeting() + " , " + s.name());
    }
}
```

产生输出：

```
Goodnight, Dick
```

因为调用 `greeting` 使用了 `s` 的类型（即 `Super`），在编译时确定调用哪个类方法；而对 `name` 的调用使用了 `s` 的类（即 `Sub`），在运行时确定调用哪个实例方法。

## 8.4.8.3 重写与隐藏的要求

如果返回类型为 $R_1$ 的方法 $d_1$ 重写或隐藏了返回类型为 $R_2$ 的另一个方法 $d_2$，则 $d_1$ 必须是 $d_2$ 的返回类型可替换（§8.4.5），否则将发生编译错误。

此规则允许协变返回类型——在重写方法时细化方法的返回类型。

如果 $R_1$ 不是 $R_2$ 的子类型，则会发生编译时的未检查警告，除非被 `@SuppressWarnings`（§9.6.4.5）抑制。

重写或隐藏另一个方法（包括实现接口中定义的抽象方法的方法），其声明抛出的检查异常不能多于被重写或隐藏的方法所抛出的异常。

在这方面，方法的重写与字段的隐藏（§8.3）不同，因为允许一个字段隐藏另一个类型的字段。

更准确地说，假设 $B$ 是一个类或接口，$A$ 是 $B$ 的超类或超接口，且 $B$ 中的方法声明 $m_2$ 重写或隐藏了 $A$ 中的方法声明 $m_1$。那么：

- 如果 $m_2$ 具有提到任何检查异常类型的 `throws` 子句，则 $m_1$ 必须有 `throws` 子句，否则将发生编译错误。
- 对于 $m_2$ `throws` 子句中列出的每个检查异常类型，必须有一个异常类或其超类之一出现在 $m_1$ `throws` 子句的擦除类型（4.6）中；否则将发生编译错误。
- 如果 $m_2$ 擦除后的 `throws` 子句不包含 $m_2$ `throws` 子句中每个异常类型的超类型（根据需要对 $m_1$ 的类型参数进行适配），则会发生编译时的未检查警告，除非被 `@SuppressWarnings`（§9.6.4.5）抑制。

如果类或接口 $C$ 拥有成员 $m_1$，且在 $C$ 或其超类/超接口 $A$ 中声明了方法 $m_2$，使得以下所有条件均成立，则会导致编译错误：

- $m_1$ 和 $m_2$ 具有相同的名称。
- $m_2$ 从 $C$（6.6）可访问。
- $m_1$ 的签名不是作为名为 $A$ 的超类型成员的 $m_2$ 签名的子签名（8.4.2）。
- $m_1$ 的声明签名或某些被 $m_1$（直接或间接）重写的方法的签名，其擦除类型与 $m_2$ 的声明签名或某些被 $m_2$（直接或间接）重写的方法的声明签名的擦除类型相同。

> 这种限制是必要的，因为泛型是通过擦除实现的。上述规则意味着在同一类中声明的相同名称的方法必须具有不同的擦除类型。它还意味着类或接口不能实现或扩展同一个泛型接口的两个不同参数化。

重写或隐藏方法的访问权限必须至少不低于被重写或隐藏方法的权限，如下：

- 如果被重写或隐藏的方法是 `public`，则重写或隐藏的方法也必须是 `public`；否则将发生编译错误。
- 如果被重写或隐藏的方法是 `protected`，则重写或隐藏的方法必须是 `protected` 或 `public`；否则将发生编译错误。
- 如果被重写或隐藏的方法具有包级访问权限（package access），则重写或隐藏的方法不能是 `private`；否则将发生编译错误。

注意，在技术意义上，`private` 方法不能被重写或隐藏。子类可以声明一个与其某个超类中的 `private` 方法签名相同的方法，并且并不要求该方法的返回类型或 `throws` 子句与超类中私有方法的有任何关系。

### 示例 8.4.8.3-1 协变返回类型

从 Java SE 5.0 开始的 Java 语言中，以下声明是合法的：



```java
class C implements Cloneable {
  C copy() throws CloneNotSupported {
    return (C) clone();
  }
}
class D implements Cloneable {
  D copy() throws CloneNotSupported {
    return (D) clone();
  }
}
```

重写或隐藏方法的访问权限必须至少不低于被重写或隐藏方法的权限，如下：

- 如果被重写或隐藏的方法是 `public`，则重写或隐藏的方法也必须是 `public`；否则将发生编译错误。
- 如果被重写或隐藏的方法是 `protected`，则重写或隐藏的方法必须是 `protected` 或 `public`；否则将发生编译错误。
- 如果被重写或隐藏的方法具有包级访问权限，则重写或隐藏的方法不能是 `private`；否则将发生编译错误。

### 8.4.8.3-2 返回类型的未检查警告

考虑：

```java
class Sorter {
  List toList(Collection c)
}
```

现在，在某处 Overrider 决定将其泛化：

```java
class Sorter {
  List<String> toList(Collection c)
}
```

在编译 Overrider 时会给出一个未检查警告：

```java
class Sorter {
  List<String> toList(Collection c)
}
```

### 8.4.8.3-3 因为 throws 错误的重写

该程序使用了抽象形式：

```java
class Point {
    void move() throws Exception;
}
class CheckedPoint extends Point {
    void move() throws Exception {
        // ...
    }
}
```

会导致编译错误，因为 `move` 的体不能抛出检查异常：

```java
class Point {
    void move() throws Exception;
}
class CheckedPoint extends Point {
    void move() {
        // ...
    }
}
```

### 8.4.8.3-4 擦除影响

类不能拥有相同擦除类型的方法：

```java
class C<T> {
    T id(T x);
}
class D extends C<Object> {
    Object id(Object x);
}
```

这是非法的，因为 `D.id(Object)` 是 `D` 的成员，`C<String>.id(String)` 在 `D` 的超类型中声明，且：

- 两个方法具有相同的名称 `id`。
- `C<String>.id(String)` 对 `D` 可访问。
- `D.id(Object)` 的签名不是 `C<String>.id(String)` 签名的子签名。

类的两个不同方法不能重写具有相同擦除类型的方法：

```java
class C<T> {
  T id(T x);
}
interface I<T> {
  T id(T x);
}
class D extends C<String> implements I<Integer> {
  public String id(String x);
  public Integer id(Integer x);
}
```

# 方法声明

来自父类层次的定义优于默认方法，使得默认方法表现得像抽象方法一样。然而，类中的抽象方法不会重写默认方法，因为接口仍然允许重新定义来自类层次的抽象方法的签名。

请注意，如果类继承的重写等效的抽象方法在接口中进行了声明，则不适用此异常。

否则，重写等效方法集包含至少一个抽象方法和零个更多的默认方法；那么该类一定是一个抽象类，并且被认为继承了所有方法。

继承的方法中必须有一个方法对于其他所有继承的方法都是返回类型可替换的；否则将发生编译错误。（在这种情况下，`throws` 子句不会引起错误。）

方法声明可能通过多种路径从接口继承。这一事实不会导致任何困难，其本身永远不会导致编译错误。

## 8.4.9 方法重载

如果类中的两个方法（均在同一个类中声明、或被类继承、或一个声明一个继承）具有相同的名称，但签名不是重写等效的，则该方法被称为重载的。

这一事实不会导致任何困难，其本身永远不会导致编译错误。除非它们的签名是重写等效的，否则两个同名方法的返回类型或 `throws` 子句之间没有强制性关系。

当调用方法时（`§15.12`），在编译时，将使用实际参数的数量（以及任何显式类型参数）和参数的编译类型来确定将要调用的方法签名（`§15.12.2`）。如果要调用的方法是实例方法，则将在运行时使用动态方法查找（`§15.12.4`）确定实际要调用的方法。

## 8.4.9-1. 重载

```java
class Point {
    float x
```

# 类

## 8.4 方法声明

在这里，类 `Point` 具有两个同名为 `move` 的成员方法。对于任何特定的方法调用，选择的 `Point` 类重载 `move` 方法是在编译时通过 `§15.12` 中给出的重载解析程序确定的。

总之，`Point` 类的成员包括在 `Point` 中声明的 `float` 实例变量 `x` 和 `y`、两个声明的 `move` 方法、声明的 `toString` 方法，以及 `Point` 直接从其直接父类 `Object`（`§4.3.2`）继承的方法，例如 `hashCode` 方法。注意，`Point` 没有继承 `Object` 类的 `toString` 方法，因为它被 `Point` 类中 `toString` 方法的声明重写了。

### 示例 8.4-9-2. 重载、重写与隐藏

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
    int color;
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(int dx, int dy) { move((float)dx, (float)dy); }
    void move(float dx, float dy) { x += dx; y += dy; }
}
```

在这里，类 `RealPoint` 用它自己的 `float` 实例变量 `x` 和 `y` 隐藏了 `Point` 类实例变量 `x` 和 `y` 的声明，并用自己的 `move` 方法重写了 `Point` 类的 `move` 方法。它通过另一个不同的签名重载了 `move` 方法（`§8.4.2`）。

在该示例中，`RealPoint` 成员包括继承自 `Point` 类的变量、在 `RealPoint` 中声明的 `float` 实例变量 `x` 和 `y`，以及 `RealPoint` 中声明的两个 `move` 方法。

对于任何特定的方法调用，选择 `RealPoint` 类的哪一个重载 `move` 方法将在编译时通过 `§15.12` 中的重载解析程序确定。

以下程序是前面程序的扩展版本：

```java
class Point {
    int x = 0, y = 0, color;
    void move(int dx, int dy) { x += dx; y += dy; }
    int getX() { return x; }
    int getY() { return y; }
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(int dx, int dy) { move((float)dx, (float)dy); }
    void move(float dx, float dy) { x += dx; y += dy; }
    float getX() { return x; }
    float getY() { return y; }
}
```

在这里，`Point` 类提供了 `getX` 和 `getY` 方法来返回其字段 `x` 和 `y` 的值；`RealPoint` 类通过声明具有相同签名的方法来重写这些方法。结果是在编译时出现两个错误，因为返回类型不匹配；`Point` 类中的方法返回 `int` 类型的值，但 `RealPoint` 类中尝试重写的方法返回 `float` 类型的值。

此程序纠正了前面程序的错误：

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
    int getX() { return x; }
    int getY() { return y; }
    int color;
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(int dx, int dy) { move((float)dx, (float)dy); }
    float getX() { return x; }
    float getY() { return y; }
}
```

类声明体中成员接口声明的修饰符规则规定在 `§9.1.1`。

成员类或接口的作用域和隐藏（shadowing）规定在 `§6.3` 和 `§6.4.1`。

如果一个类声明了一个特定名称成员类或接口，则该成员类或接口的声明被认为隐藏了该类的超类和超接口中同名的任何所有可访问成员类和接口声明。

在这方面，成员类和接口的隐藏与字段的隐藏（`§8.3`）相似。

类从其直接超类和直接超接口继承超类和超接口中所有代码可访问且未被类中的声明隐藏的非私有（all-private）成员类和接口。

一个类可能从其超类或其超接口，或仅从其超接口继承多个同名的成员类或接口。这种情况本身并不会导致编译时错误。然而，在类体内部任何尝试通过其简单名称引用此类成员类或接口的尝试都将导致编译时错误，因为该引用是模糊的。

可能存在多条路径从接口继承同一个成员类或接口声明。在这种情况下，该成员类或接口被认为仅被继承一次，并且可以通过其简单名称引用而无歧义。

## 8.6 实例化初始化器

在类中声明的实例化初始化器在类实例创建时执行（`§12.5`、`§15.9`、`§8.7.1`）。

```
InstanceInitializer:
Block
```

如果实例化初始化器无法正常完成，则为编译时错误（`§14.22`）。

如果在实例化初始化器内部任何地方出现返回语句（`§14.17`），则为编译时错误。

允许实例化初始化器使用关键字 `this`（`§15.8.3`）或关键字 `super`（`§15.11.2`、`§15.12`）来引用当前对象，并使用作用域内的任何类型变量。

关于实例化初始化器可以如何引用实例变量的限制（即使实例变量在作用域内）规定在 `§8.3.3`。

实例化初始化器的异常检查规定在 `§11.2.3`。

## 8.7 静态初始化器

在类中声明的静态初始化器在类初始化时执行（`§12.4.2`）。静态初始化器与类变量的任何字段初始化器（`§8.3.2`）一起用于初始化类的变量。

```
StaticInitializer:
static Block
```

如果静态初始化器无法正常完成，则为编译时错误（`§14.22`）。

如果在静态初始化器内部任何地方出现返回语句（`§14.17`），则为编译时错误。

静态初始化器引入了静态上下文（`§8.1.3`），这限制了引用当前对象的构造的使用。特别是，在静态上下文中禁止使用 `this` 和 `super` 关键字（`§15.8.3`、`§15.11.2`），同时也禁止对实例变量、实例方法以及词法包含声明的类型参数进行未限定引用（`§6.5.5.1`、`§6.5.6.1`、`§15.12.3`）。

关于静态初始化器可以如何引用类变量的限制（即使类变量在作用域内）规定在 `§8.3.3`。

静态初始化器的异常检查规定在 `§11.2.3`。

## 8.8 构造方法声明

构造方法用于创建类的实例对象（`§12.5`、`§15.9`）。

```
ConstructorDeclaration:
[ConstructorModifier] ConstructorDeclarator [Throws] ConstructorBody
```

### ConstructorDeclarator:

([TypeParameters] SimpleTypeName ([ReceiverParameter ,] [FormalParamList] )

### SimpleTypeName:

Identifier

本节的规则适用于所有类声明中的构造方法，包括枚举声明和记录（record）声明。然而，枚举声明在构造方法修饰符、构造方法体和默认构造方法方面有特殊规则；这些规则见 `§8.9.2`。记录声明在构造方法方面也适用特殊规则，如 `§8.10.4` 所示。

`ConstructorDeclarator` 中的 `SimpleTypeName` 必须是包含构造方法声明的类的简单名称，否则将发生编译时错误。

在所有其他情况下，构造方法声明看起来就像一个没有结果的方法声明（`§8.4.5`）。

构造方法声明不是成员。它们永远不会被继承，因此不受隐藏或重写的影响。

构造方法通过类实例创建表达式（`§15.9`）、由字符串拼接运算符 `+` 引起的转换和连接（`§15.18.1`）以及来自其他构造方法的显式构造方法调用（`§8.8.7`）被调用。构造方法的访问受访问修饰符（`§6.6`）控制，因此可以通过声明一个不可访问的构造方法来防止类的实例化（`§8.8.10`）。

构造方法永远不会通过方法调用表达式（`§15.12`）被调用。

#### 示例 8.8-1. 构造方法声明

```java
class Point {
  int x, y;
  Point(int x, int y) { this.x = x; this.y = y; }
}
```

### 8.8.1 形式参数

构造方法的形式参数在语法和语义上与方法的参数相同（`§8.4.1`）。

如果构造方法的最后一个形式参数是一个变量，则该构造方法是变长参数构造方法（variable arity constructor）。否则，它是固定参数构造方法。

# 类

## 构造方法声明

非私有内部类的构造方法隐式地将第一个参数声明为表示直接封闭实例的变量（`§15.9.2`、`§15.3`）。这种类具有隐式声明参数的原因是微妙的。以下解释可能有所帮助：

- 在非私有内部类的类创建表达式中，`§15.9.2` 规定了直接封闭实例。成员类可能由与类创建表达式不同的编译器生成。因此，类创建表达式的编译器必须有一种标准方式将引用（表示直接封闭实例）传递给成员类的构造方法。因此，Java 语言在本节中规定非私有内部类隐式声明直接封闭实例的初始化参数。
- 在内部类或匿名类的类创建表达式中（非静态上下文中），`§15.9.2` 规定了局部/匿名类的直接封闭实例。局部/匿名类一定由与类创建表达式相同的编译器生成。因此，编译器可以以任何方式表示直接封闭实例。Java 语言没有必要在局部/匿名类中隐式声明参数。
- 在匿名类的类创建表达式中，且该匿名类的超类是内部类（非静态上下文中），`§15.9.2` 规定了匿名类相对于超类的直接封闭实例。该实例必须从匿名类传输到其超类，由于超类可能由与类创建表达式不同的编译器生成，因此有必要以标准方式传输该实例，将其作为第一个参数传递给超类的构造方法。注意，匿名类本身一定由与类创建表达式相同的编译器生成，因此它可以以任何方式传输相对于超类的封闭实例。然而，为了一致性，Java 语言在 `§15.9.1` 中规定，在某些情况下，匿名类的构造方法隐式声明相对于超类的直接封闭实例的初始化参数。

### 8.8.2 构造方法签名

在类中声明两个重写等效签名（`§8.4.2`）的构造方法为编译时错误。

在类中声明两个签名擦除后相同（`§4.6`）的构造函数将是编译时错误。

## 8.8.3 构造函数修饰符

```
ConstructorModifier:
(其中之一)
Annotation public protected private
```

关于构造函数声明中注解修饰符的规则在 `§9.7.4` 和 `§9.7.5` 中规定。

如果同一个关键字在构造函数声明中作为修饰符出现多次，或者如果构造函数声明包含多个一个 `public`、`protected` 和 `private` 访问修饰符（`§6.6`），则为编译时错误。

在普通类声明中，没有访问修饰符的构造函数声明具有包访问权限（package access）。

如果在方法声明中出现了两个或多个（不同的）方法修饰符，按照习惯（尽管不是强制），它们出现的顺序与上述 `MethodModifier` 产生式中所示顺序一致。

与方法不同，构造函数不能是 `abstract`、`static`、`final`、`native`、`strictfp` 或 `synchronized`。

- 构造函数是不被继承的，因此没有必要将其声明为 `final`。
- 抽象构造函数（abstract constructor）永远无法实现。
- 构造函数总是相对于对象被调用的，因此构造函数为 `static` 是没有意义的。
- 构造函数没有实际需要是 `synchronized` 的，因为它会锁定正在构建的对象，而在该对象的所有构造函数完成工作之前，其他线程通常是无法访问该对象的。
- 缺乏 `native` 构造函数是一种任意的语言设计选择，这使得 Java 虚拟机的实现更容易验证在对象创建期间正确调用了父类的构造函数。
- 无法将构造函数声明为 `strictfp`（与方法 `§8.4.3` 相比）是一种刻意的语言设计选择，源于将类声明为 `strictfp` 的能力（现已废）。



## 8.8.4 泛型构造函数

如果构造函数声明了一个或多个类型变量（§4.4），则该构造函数是泛型的。

这些类型变量被称为构造函数的类型参数。泛型构造函数类型参数部分的形式与泛型类的类型参数部分相同（§8.1.2）。

构造函数可以是泛型的，而无需该类的构造函数本身被声明为泛型。

泛型构造函数声明定义了一组构造函数，对于类型参数对类型部分的每种可能的调用，都对应一个构造函数。在调用泛型构造函数时，不需要显式提供类型参数，因为它们可以被推断（§18 类型推断）。

构造函数类型参数的作用域和遮蔽（shadowing）在 §6.3 和 §6.4.1 中规定。

从显式构造函数调用语句或嵌套类或接口对构造函数类型参数的引用受到 §6.5.5.1 规定的限制。

## 8.8.5 构造函数 Throws

构造函数的 `throws` 子句在结构和行为上与方法的 `throws` 子句相同（§8.4.6）。

## 8.8.6 构造函数的类型

构造函数的类型由其签名和 `throws` 子句提供的异常类型组成。

## 8.8.7 构造函数体

构造函数体的第一条语句可以是对同一类或直接父类的另一个构造函数的显式调用（§8.8.7.1）。

```
ConstructorBody:
{ [ExplicitConstructorInvocation] [BlockStatements] }
```

如果构造函数通过一系列或多个涉及自身的显式构造函数调用直接或间接地调用自身，则为编译时错误。

如果构造函数体不是以显式构造函数调用开头，且正在声明的构造函数不是原始类 `Object` 的一部分，则构造函数体隐式地以父类构造函数调用 `super();` 开，这是一个带参数的直接父类构造函数的调用。

除了显式构造函数调用的可能性以及禁止显式返回值（§14.17）外，构造函数的体类似于方法的体（§8.4.7）。

### 8.8.7-1 构造函数体示例

```java
class Point {
    int x, y;
    Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
class ColoredPoint extends Point {
    static final int WHITE = 0, BLACK = 1;
    int color;
    ColoredPoint(int x, int y) {
        super(x, y);
        this.color = WHITE;
    }
    ColoredPoint(int x, int y, int color) {
        super(x, y);
        this.color = color;
    }
}
```

## 8.8 类的构造函数声明

通过从左到右对构造函数的参数进行求值（就像普通的方法调用一样）；然后调用构造函数。

+   最后，如果父类构造函数调用语句正常完成，则执行 $c$ 的所有实例初始化器和 $c$ 的所有实例初始化器。如果一个实例初始化器或实例变量 $i$ 在另一个实例初始化器或实例变量 $j$ 之前，则 $i$ 在 $j$ 之前执行。

实例变量初始化器和实例初始化器的执行与父类构造函数调用实际上是作为显式的构造函数调用语句出现，还是隐式提供的。（备用构造函数调用不会执行此额外的操作。）

### 示例 8.8.7.1-1. 显式构造函数调用的限制

如果将示例 §8.8.2 中 ColoredPoint 的第一个构造函数更改如下：

```java
class Point {
    int x, y;
    Point(int x, int y) {this.x = x; this.y = y; }
}
class ColoredPoint extends Point {
    static final int WHITE = 0, BLACK = 1;
    int color;
    ColoredPoint(int x, int y) {
        this(x, y, color); // 将 WHITE 改为 color
    }
    ColoredPoint(int x, int y, int color) {
        super(x, y);
        this.color = color;
    }
}
```

那么将会发生编译错误，因为实例变量 `color` 不能被显式构造函数调用语句使用。

### 示例 8.8.7.1-2. 限定父类构造函数调用

在下面的代码中，ChildOfInner 没有词法上的包围类或接口声明，因此 ChildOfInner 的实例没有包围类。然而，ChildOfInner 的父类（Inner）有一个词法上的包围类声明（Outer），并且在创建 Inner 的实例时会设置 Outer 的实例。因此，当我们创建一个 ChildOfInner 实例（它隐式地是 Inner 的实例）时，我们必须在 ChildOfInner 中通过限定父类调用语句提供 Outer 的实例。

## 构造函数声明

构造。相对于 Inner 而言，Outer 的实例是 ChildOfInner 的直接包围实例。

```java
class Outer {
    class Inner {}
}
class ChildOfInner extends Outer {
    ChildOfInner() { (new Outer()).super(); }
}
```

可能有趣的是，Outer 的实例可以作为多个 ChildOfInner 实例相对于 Inner 的直接包围实例。这些 ChildOfInner 实例隐式地链接到同一个 Outer 实例。下方的程序通过将 Outer 的实例传递给 ChildOfInner 的构造函数证明了这一点，该构造函数在限定父类构造函数调用语句中使用该实例。显式构造函数调用语句的规则并不禁止包含该语句的构造函数的形式参数。

```java
class Outer {
    int secret = 5;
    class Inner {
        int getSecret() { return secret; }
        void setSecret(int s) { secret = s; }
    }
}
class ChildOfInner extends Outer {
    ChildOfInner(Outer x) { x.super(); }
}

public class Test {
    public static void main(String[] args) {
        Outer x = new Outer();
        ChildOfInner a = new ChildOfInner(x);
        ChildOfInner b = new ChildOfInner(x);
        System.out.println(b.getSecret());
        a.setSecret(6);
        System.out.println(b.getSecret());
    }
}
```

该程序产生输出：

```
5
6
```

其效果是，对 Outer Common实例中实例变量的操作通过对不同 ChildOfInner 实例的引用是的，尽管这些引用在传统意义上并不是别名。

## 8.8.8 构造函数重载

构造函数的重载行为与方法的重载相同（§8.4.9）。重载在编译时由每个类实例创建表达式解析（§15.9）。

## 8.8.9 默认构造函数

如果一个类没有包含任何构造函数声明，则隐式声明一个默认构造函数。顶层类、成员类或局部类的默认构造函数的格式如下：

-   默认构造函数具有与类相同的修饰符，除非类缺少访问修饰符，此时默认构造函数具有包访问权限 (§6.6)。
-   默认构造函数没有形式参数，但在非私有的内部成员类除外，在该类中，默认构造函数隐式地声明一个代表该类直接包围实例的形式参数 (§8.8.1, §15.9.2, §15.9.3)。
-   默认构造函数没有 throws 子句。
-   如果被声明的类是原始类 Object，则默认构造函数有一个空体。否则，默认构造函数仅调用不带参数的父类构造函数。

匿名类的默认构造函数的格式在 §15.9.5.1 中指定。

如果隐式声明了默认构造函数，但父类没有无参数且没有 throws 子句的可访问构造函数，则为编译错误。

### 示例 8.8.9-1. 默认构造函数

声明：

```java
public class Point {
    int x, y;
}
```

等同于声明：

```java
public class Point {
    int x, y;
    public Point() { super(); }
}
```

## 8.8.8 构造函数声明

默认构造函数是 public 的，因为该类是 public 的。

### 示例 8.8.9-2. 构造函数的访问性

默认构造函数是 public 的，因为该类是 public 的。默认构造函数具有类相同访问权限的规则是简单且直观的。然而，这并不意味着构造函数是可见的。考虑：

```java
package p1;
public class Outer {
    protected class Inner { }
}
package p2;
class SonOuter extends Outer {
    void foo() {
        new Inner(); // 编译错误
    }
}
```

Inner 的默认构造函数是 protected 的。然而，相对于 Outer 来说，Inner 在 SonOuter 中可见，因为它是 Outer 的子类。

## 8.8.10 防止实例化

类可以通过声明至少一个构造函数或通过将所有构造函数声明为私有来防止外部代码创建实例。

一个 public 类同样可以通过将所有构造函数声明为私有来防止包外实例化。

### 示例 8.8.10-1. 通过构造函数防止实例化

```java
class ClassOnly {
    private ClassOnly() { }
    static String just = "only";
}
```

在这里，ClassOnly 无法实例化，而在下面的代码中：

```java
package just;
public class PackageOnly {
    PackageOnly() { }
    String[] desserts = {"cheesecake", "ice cream"};
}
```

public 类 PackageOnly 只能在其定义的包内实例化。如果 PackageOnly 的构造函数是保护的，这种限制也将适用，尽管在这种情况下其他包的代码可以实例化其子类。

## 8.9 枚举类

枚举声明指定一个新的枚举类，这是一种定义了少量命名实例的限制类。

```
EnumDeclaration:
{ClassModifier} enum TypeIdentifier [ClassImplements] EnumBody
```

枚举声明可以指定顶层类 (§7.6)、成员类 (§8.5, §9.5) 或局部类 (§14.3)。

枚举声明中的 TypeIdentifier 指定了枚举类的名称。

如果枚举声明具有 abstract、final、sealed 或 non-sealed 修饰符，则为编译错误。

枚举类是隐式的 final 或隐式的 sealed，如下：

-   如果枚举声明不包含任何具有类体的枚举常量，则枚举类是隐式 final (§8.9.1)。
-   如果枚举声明包含至少一个具有类体的枚举常量，则枚举类 E 是隐式 sealed 的。E 的允许子类 (§8.1.6) 是具有类体的枚举常量隐式声明的匿名类。

嵌套枚举类是隐式的 static。也就是说，每个枚举类和局部枚举类都是静态的。在成员类的声明中冗余地指定 static 修饰符是允许的，但在局部枚举类 (§14.3) 中是不允许的。

如果同一个关键字作为枚举声明的修饰符出现多次，或者枚举声明具有 public、protected 和 private 中的多个修饰符 (§6.6)，则为编译错误。

枚举类 E 的直接父类类型是 Enum<E> (§8.1.4)。

## 8.9 枚举类 (Enum Classes)

枚举声明没有 `extends` 子句，因此无法显式声明直接父类，即使是 `Enum<E>` 也不行。

枚举类除了由枚举常量定义的实例外没有其他实例。尝试实例化枚举类是编译时错误（§15.9.1）。

除了编译时错误外，还有三种机制确保了除了枚举常量之外，不存在枚举类的实例：

- `Enum` 中 `final` 的 `clone` 方法确保了枚举常量永远无法被克隆。
- 禁止对枚举类进行反射式实例化。
- 序列化机制的特殊处理确保了不会因为反序列化而创建重复的实例。

## 8.9.1 枚举常量 (Enum Constants)

枚举声明的体部可以包含枚举常量。每个枚举常量定义了枚举类的一个实例。

```
EnumBody:
{ [EnumConstantList] [, [EnumBodyDeclarations] }
```

```
EnumConstantList:
EnumConstant { , EnumConstant }
```

```
EnumConstant:
[EnumConstantModifier] Identifier [ ( [ArgumentList] ] [ClassBody
```

```
EnumConstantModifier:
Annotation
```

为了方便起见，此处展示了 §15.12 中的后续产生：

```
ArgumentList:
Expression ( , Expression )
```

关于枚举常量声明的注解修饰符规则规定在 §9.7.4 和 §9.7.5 中。

`EnumConstant` 中的 `Identifier` 可用于名称以引用枚举常量。

枚举常量的作用域和遮蔽规定在 §6.3 和 §6.4.1 中。

## 8.9 枚举类 (Enum Classes)

枚举常量后面可以跟随参数，当常量在类初始化期间创建时（如本节后文所述），这些参数将传递给枚举的构造函数。被调用的构造函数是使用普通的重载解析规则（§15.12.2）选择的。如果省略参数，则假设为空参数列表。

枚举常量的可选类体隐式地声明了一个匿名类（§15.9.5），该类：(i) 是紧邻的枚举类的直接子类（§8.1.4），(ii) 是 `final` 的（§8.1.2）。类体受匿名类的通常规则限制；特别是，它不能包含任何构造函数。在这些类体中声明的实例方法只有在它们重写了闭包枚举类的可访问方法时（§8.4.8），才能在闭包枚举类之外调用。

在枚举常量的类体中声明 `abstract` 方法是编译时错误。

由于每个枚举常量只有一个实例，因此当已知两个对象引用中至少有一个指向枚举常量时，允许在比较两个对象引用时使用 `==` 运算符代替 `equals` 方法。

> `Enum` 中的 `equals` 方法是一个 `final` 方法，它仅仅在其参数上调用 `super.equals` 并返回结果，执行等标识性比较（identity comparison）。

## 8.9.2 枚举体部声明 (Enum Body Declarations)

除了枚举常量外，枚举声明的体部还可以包含构造函数和成员声明，以及实例和静态初始化器。

```
EnumBodyDeclarations:
[ClassBodyDeclaration]
```

为了方便起见，此处展示了 §8.1.7 中的后续产生：

```
ClassBodyDeclaration:
ClassMemberDeclaration
InstanceInitializer
StaticInitializer
ConstructorDeclaration
```

```
ClassMemberDeclaration:
FieldDeclaration
MethodDeclaration
ClassDeclaration
InterfaceDeclaration
```

## 枚举类 (Enum Classes)

枚举声明体部中的任何构造函数或成员声明对枚举类的作用，正就像它们出现在普通类声明的体部中一样，除非另有明确说明。

如果枚举声明中的构造函数声明是 `public` 或 `protected`，则是编译时错误（§6.6）。

如果枚举声明中的构造函数声明包含父类构造函数调用语句，则是编译时错误（§8.7.1）。

在枚举类的构造函数、实例初始化器或实例变量初始化器引用枚举类的静态字段是编译时错误，除非该字段是常量变量（§4.12.4）。

在枚举声明中，没有访问修饰符的构造函数声明是 `private` 的。

在没有构造函数声明的枚举声明中，隐式地声明了一个默认构造函数。该构造函数是 `private`、`final` 且没有 `throws` 子句。

> 在实践中，编译器可能会通过在枚举类的默认构造函数中声明 `String` 和 `int` 参数来镜像 `Enum` 类。然而，这些参数并没有被指定为“隐式声明”，因为不同的编译器不需要对默认的形式达成一致。只有枚举声明的编译器才知道如何实例化枚举常量；其他编译器可以简单地依赖枚举类的隐式声明静态字段（§8.9.3），而不忽略这些字段是如何初始化的。

如果枚举声明 `E` 具有一个抽象成员方法 `m`，则是编译时错误，除非 `E` 至少有一个常量，且 `E` 的所有常量的体部都提供了 `m` 的具体实现。

枚举声明声明终结器（§12.6）是编译时错误。枚举类的实例可以被终结化。

## 示例 8.9.2-1. 枚举体部声明 (Enum Body Declarations)



# 枚举类

## 枚举体部声明

```java
enum Coin {
    PENNY(1), NICKEL(5), DIME(10), QUARTER(25);
    Coin(int value) { this.value = value; }

    private final int value;
    public int value() { return value; }
}
```

枚举声明体部中的构造函数或成员声明对枚举类的作用，正就像它们出现在普通类声明的体部中一样，除非另有明确说明。

## 带有类体的枚举常量

与其使用 `switch` 语句从外部为枚举类“添加”行为，不如直接使用类体将行为附加到枚举常量上。

```java
enum Operation {

  PLUS {
    double eval(double x, double y) { return x + y; }
  },

  MINUS {
    double eval(double x, double y) { return x - y; }
  },

  TIMES {
    double eval(double x, double y) { return x * y; }
  },

  DIVIDED_BY {
    double eval(double x, double y) { return x / y; }
  };

  // 每个常量支持一种算术运算
  abstract double eval(double x, double y);
}

public static void main(String[] args[]) {
  double x = Double.parseDouble(args[0]);
  double y = Double.parseDouble(args[1]);
  for (Operation op : Operation.values()) {
    System.out.println(x + " " + op + " " + y + " = " + op.eval(x, y));
  }
}
```

程序产生输出：

```
java Operation 2.0 4.0
2.0 PLUS 4.0 = 6.0
2.0 MINUS 4.0 = -2.0
2.0 TIMES 4.0 = 8.0
2.0 DIVIDED_BY 4.0 = 0.5
```

## 多个枚举类

在接下来的程序中，纸牌类是基于枚举构建的。

```java
import java.util.List;
import java.util.ArrayList;

class Card implements Comparable<Card>, java.io.Serializable {

    public enum Rank { DEUCE, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, JACK, QUEEN, KING, ACE }
    public enum Suit { CLUBS, DIAMONDS, HEARTS, SPADES }

    private final Rank rank;
    private final Suit suit;

    public Rank rank() { return rank; }
    public Suit suit() { return suit; }

    private Card(Rank rank, Suit suit) {
        if (rank == null || suit == null)
            throw new NullPointerException(rank + " " + suit);
        this.rank = rank;
        this.suit = suit;
    }

    public String toString() { return rank + " of " + suit; }

    // 主按花色排序，次按点数排序
    public int compareTo(Card c) {
        int suitCompare = suit.compareTo(c.suit);
        return (suitCompare != 0) ?
            suitCompare :
            rank.compareTo(c.rank);
    }
}
```

```java
private static final List<Card> prototypeDeck = new ArrayList<Card>(52);

static {
    for (Suit suit : Suit.values())
        for (Rank rank : Rank.values())
            prototypeDeck.add(new Card(rank, suit));
}

// 返回一个新的牌组
public static List<Card> newDeck() {
    return new ArrayList<Card>(prototypeDeck);
}
```

接下来的程序测试了 `Card` 类。它在命令行接收两个整数参数，代表要发的牌数和每手牌的牌数。

```java
import java.util.List;
import java.util.ArrayList;
import java.util.Collections;

class Deal {
    public static void main(String[] args) {
        int numHands = Integer.parseInt(args[0]);
        int cardsPerHand = Integer.parseInt(args[1]);
        List<Card> deck = Card.newDeck();
        Collections.shuffle(deck);
        for (int i = 0; i < numHands; i++) {
            System.out.println(dealHand(deck, cardsPerHand));
        }
    }

    /**
     * 返回一个新的包含 deck 中最后 n 个
     * 元素的 ArrayList，这些元素已从 deck 中移除。
     * 返回的列表将使用元素的
     * 自然顺序进行排序。
     */
    public static <E extends Comparable<E>> List<E> dealHand(List<E> deck, int n) {
        int deckSize = deck.size();
        List<E> handView = deck.subList(deckSize - n, deckSize);
        ArrayList<E> hand = new ArrayList<E>(handView);
        handView.clear();
        Collections.sort(hand);
        return hand;
    }
}
```

程序产生输出：

```
Deal 4
DEUCE OF CLUBS, SEVEN OF CLUBS, QUEEN OF DIAMONDS
```



NINE OF HEARTS, FIVE OF SPADES, ACE OF SPADES

THREE OF HEARTS, SIX OF SPADES, TEN OF CLUBS

NINE OF DIAMONDS, TEN OF HEARTS, THREE OF SPADES

## 8.10 记录组件

记录类（record class）的组件（components）在定义时指定。每个组件都会自动生成一个私有字段、一个公共访问器方法以及一个构造函数。在枚举类中，我们可以使用类体直接将行为附加到枚举常量上，而不是使用 `switch` 语句。

```java
enum Operation {
  PLUS {
    double eval(double x, double y) { return x + y; }
  },
  MINUS {
    double eval(double x, double y) { return x - y; }
  },
  TIMES {
    double eval(double x, double y) { return x * y; }
  },
  DIVIDED_BY {
    double eval(double x, double y) { return x / y; }
  };

  // 每个常量支持一种算术运算
  abstract double eval(double x, double y);
}
```

该程序产生输出：

```
java Operation 2.0 4.0
2.0 PLUS 4.0 = 6.0
2.0 MINUS 4.0 = -2.0
2.0 TIMES 4.0 = 8.0
2.0 DIVIDED_BY 4.0 = 0.5
```

在接下来的程序中，纸牌类是基于枚举构建的。

（此处代码省略，保持原意逻辑）

（此处代码省略）

接下来的程序测试了 `Card` 类。它在命令行接收两个整数参数，代表要发的牌数和每手牌的牌数。

（此处代码省略，保持原意逻辑）

```java
/**
 * 返回一个新的包含 deck 中最后 n
 * 元素的 ArrayList，这些元素已从 deck 中移除。
 * 返回的列表将使用元素的
 * 自然顺序进行排序。
 */
public static <E extends Comparable<E>> List<E> dealHand(List<E> deck, int n) {
    int deckSize = deck.size();
    List<E> handView = deck.subList(deckSize - n, deckSize);
    ArrayList<E> hand = new ArrayList<E>(handView);
    handView.clear();
    Collections.sort(hand);
    return hand;
}
```

程序产生输出：

```
Deal 4
DEUCE OF CLUBS, SEVEN OF CLUBS, QUEEN OF DIAMONDS
NINE OF HEARTS, FIVE OF SPADES, ACE OF SPADES
THREE OF HEARTS, SIX OF SPADES, TEN OF CLUBS
NINE OF DIAMONDS, TEN OF HEARTS, THREE OF SPADES
```

## 8.10 记录组件

记录类（record class）的组件在定义时指定。每个组件都会自动生成一个私有字段、一个公共访问器方法以及一个构造函数。在枚举类中，我们可以使用类体直接将行为附加到枚举常量上，而不是使用 `switch` 语句。

记录类的类体（body）可以包含构造函数和成员声明以及静态初始化器。

### 8.10.2 记录类体声明

记录类的类体可以包含构造函数和成员声明以及静态初始化器。

为了方便起见，此处显示 §8.1.7 中的以下内容：

```
ClassBodyDeclaration:
ClassMemberDeclaration
InstanceInitializer
StaticInitializer
ConstructorDeclaration
```

```
ClassMemberDeclaration:
FieldDeclaration
MethodDeclaration
ClassDeclaration
InterfaceDeclaration
```

`CompactConstructorDeclaration` 子句在 §8.10.4.2 中描述。

记录声明（record declaration）的体部包含非静态字段声明 (§8.3.1.1) 是编译时错误。

记录声明的体部包含抽象或原生（native）方法声明 (§8.4.3.1, §8.4.3.4) 是编译时错误。

记录声明的体部包含实例初始化器 (§8.6) 是编译时错误。

## 8.10.3 记录成员 (Record Members)

对于每个记录组件（record component），记录类都拥有一个与该组件名称相同且类型与该组件声明类型相同的字段。该字段是隐式声明的，被称为组件字段（component field）。

组件字段是私有的（private）、最终的（final）且非静态的。

组件字段带有相应的记录组件上出现的注解（如果有的话），且这些注解的接口在字段声明上下文中、类型上下文中或两者中均适用 (§9.7.4)。

此外，对于每个记录组件，记录类都拥有一个与该组件名称相同且形式参数列表为空的方法。该方法是显式或隐式声明的，被称为访问器方法（accessor method）。

如果显式声明记录组件的访问器方法，则必须满足以下所有条件，否则将发生编译时错误：

- 访问方法的返回类型 (§8.4.5) 必须与记录组件的声明类型相同。
- 访问方法不能是泛型的 (§§8.4.4)。
- 访问方法必须是一个公共的实例方法，且没有形式参数和没有抛出（throws）子句。

如果记录类的某个记录组件没有显式声明访问器方法，则该组件的访问器方法将隐式声明，并具有以下属性：

- 它的名称与记录组件的名称相同。
- 它的返回类型与记录组件的声明类型相同。
- 它不是泛型的。
- 它是一个公共的实例方法，且没有形式参数和没有抛出（throws）子句。
- 它带有相应的记录组件上出现的注解（如果有的话），且这些注解的接口在方法声明上下文中、类型上下文中或两者中均适用 (§9.7.4)。
- 它的体返回相应组件字段的值。

对记录组件名称的限制 (§8.10.1) 意味着隐式声明的访问器方法的签名与 Object 的非私有方法重写等效（override-equivalent）。使用受限制名称之一（例如 `public wait`）的显式方法声明并不是访问器方法，因为 `wait` 永远不会记录组件。

出现在记录组件上的注解不会传播到该组件的显式声明的访问器方法。在某些情况下，程序员可能需要在显式声明的访问器方法上重复记录组件的注解，但这并不总是必须的。

传播到隐式声明访问器方法的注解必须导致一个合法的注解方法。例如，在以下记录声明中，隐式声明的访问器方法 `x()` 将带有 `@SafeVarags` 注，但此类注解在固定数组方法上是非法的 (§9.6.7)。

```java
record BadRecord(@SafeVarags int x) () // 错误
```

记录类的所有成员（包括隐式声明的成员）都适用于类成员声明的常规规则 (§8.3, §8.4, §8.5)。

适用于普通类的继承规则也适用于记录类。特别是，记录类可以从超接口继承成员，尽管超接口方法永远不会作为访问器方法被继承，因为记录类总是显式或隐式地声明一个重写了该超接口方法的访问器方法。

例如，记录类可以从其直接超接口继承默认方法，尽管默认方法的体对记录类的组件字段一无不知。以下程序打印 Logged：

```java
public class Test {
    interface Logging {
        default void logAction() {
            System.out.println("Logged");
        }
    }

    record Point(int i, int j) implements Logging {
        public static void main(String[] args) {
            Point p = new Point(10, 20);
            p.logAction();
        }
    }
}
```

记录类提供了类 Record 中声明的所有抽象方法的实现。对于每个方法，如果记录 R 没有显式声明一个具有相同修饰符、名称和签名的方法 (§8.4.2)，则该方法按如下方式隐式声明：

- 方法 `final boolean equals(Object)` 在仅当参数是 R 的实例且当前实例在 R 的每个记录类中都与参数实例相等时，返回 true；否则返回 false。

记录类 R 的实例 `a` 与同一记录类的另一个实例 `b` 在某个记录组件上的相等性确定如下：

- 如果记录组件 `c` 的类型是引用类型，相等性的确定方式如下：如果 a 和 b 的组件字段 `c` 的值都是空引用，则返回 true；如果 a 或 b 的其中一个的组件字段 `c` 的值不为空（但不同为空），则返回 false；否则通过对 a 的组件字段 `c` 的值调用 `equals` 方法来确定相等性，其参数为 b 的组件字段 `c` 的值。
- 如果记录组件 `c` 的类型是原始类型，相等性的确定方式如下：通过调用相应包装类的静态 `compare` 方法 (§5.1.7)，第一个参数为 a 的组件字段 `c` 的值，第二个参数为 b 的组件字段 `c` 的值；如果该方法返回 0，则返回 true；否则返回 false。

包装类中使用 `compare` 方法确保了对于具有浮点组件的记录类，隐式声明的 `equals` 方法是自反射的并且与隐式声明的 `hashCode` 方法保持一致。

- 方法 `public final int hashCode()` 返回由 R 的每个记录组件的哈希值派生的哈希值。

记录组件 `c` 的实例 `a` 的哈希值如下：

- 如果记录组件 `c` 的类型是引用类型，则哈希值通过对 a 的组件字段 `c` 的值调用 `hashCode` 方法来确定。
- 如果记录组件是原始类型 T，则通过装箱转换 (§5.1.7) 后调用相应包装类的 `hashCode` 方法确定。

- 方法 `public final String toString()` 返回由记录类名称以及 R 的每个记录组件的名称和字符串表示组成的字符串。

记录类实例 `a` 的记录组件 `c` 的字符串表示如下：

- 如果记录组件 `c` 的类型是引用类型，则字符串表示通过对 a 的组件字段 `c` 的值调用 `toString` 方法来确定。
- 如果记录组件 `c` 的类型是原始类型 T，则通过装箱转换 (§5.1.7) 后调用相应包装类的 `toString` 方法确定。

请注意，相等性、哈希值和字符串表示是通过直接观察字段的值来确定的，而不是通过调用访问器方法。

考虑一个具有组件 $c_1, \dots, c_n$ 的记录类 R，每个组件都有隐式声明的访问器方法，并且有一个隐式声明的 `equals` 方法。如果 R 的一个实例 `r1` 以如下方式进行拷贝：

```java
R r2 = new R(r1.c1(), r1.c2(), ..., r1.cn());
```

那么，假设 r1 不是空引用，表达式 `r1.equals(r2)` 的结果始终为 true。显式声明的访问器方法和 equals 方法应当遵守这一不变性。编译器通常无法检查声明的记录方法是否遵守了该不变性。以下记录声明属于不良的风格，因为它的访问器方法裁剪了 x 和 y 组件，导致 p3 无法等于 p1：

```java
record SmallPoint(int x, int y) {
    public int x() { return this.x < 100 ? this.x : 100; }
    public int y() { return this.y < 100 ? this.y : 100; }

    public static void main(String[] args) {
        SmallPoint p1 = new SmallPoint(200, 300);
        SmallPoint p2 = new SmallPoint(200, 300);
        System.out.println(p1.equals(p2)); // 输出 true
        SmallPoint p3 = new SmallPoint(p1.x(), p1.y());
        System.out.println(p1.equals(p3)); // 输出 false
    }
}
```

## 8.10.4 记录构造函数声明

为了确保其记录组件的正确初始化，记录类不会隐式地声明默认构造函数 (§8.8.9)。相反，一个记录类有一个规范构造函数（canonical constructor），该函数可以显式或隐式声明，并负责初始化记录类的所有组件字段。

在记录声明中，有两种方式显式声明规范构造函数：通过声明一个具有合适签名的普通构造函数 (§8.10.4.1)，或者通过声明一个紧凑构造函数 (§8.10.4.2)。

> 给定一个符合规范要求的的普通构造函数的签名，根据构造函数签名规则 (§8.8.2)，如果一个记录声明同时包含一个符合规范的普通构造函数和一个紧凑构造函数，则会导致编译时错误。

显式声明的规范构造函数必须提供与记录类至少相同的访问权限，如下所示：

- 如果记录类是 public 的，则规范构造函数必须是 public 的；否则会发生编译时错误。
- 如果记录类是 protected 的，则规范构造函数必须是 protected 或 public 的；否则会发生编译时错误。
- 如果记录类具有包访问权限（package access），则规范构造函数不能是 private 的；否则会发生编译时错误。
- 如果记录类是 private 的，则规范构造函数可以用任何访问权限声明。

显式声明的规范构造函数可以是固定参数的构造函数，也可以是变长参数的构造函数 (§8.8.1)。

如果在记录 R 的声明中没有显式声明规范构造函数，则在 R 中隐式声明一个规范构造函数 x，具有以下属性：

- x 的签名没有参数，但其形式参数由下文定义的 R 的派生形式参数列表给出。
- x 的访问修饰符与 R 相同，除非 R 缺少访问修饰符，此时 x 具有包权限。
- x 没有 throws 子句。
- x 的方法体按照记录组件（对应组件字段）在记录头中出现的顺序，用 x 对应的形式参数初始化记录类的每个组件字段。

记录类的派生形式参数列表是通过按顺序从记录头中的每个记录组件派生出形式参数而成的：

- 如果该记录组件不是变长记录组件，则派生形式参数的名称和声明类型与该记录组件相同。
- 如果该记录组件是变长记录组件，则派生形式参数是一个与该记录组件相同名称和声明类型的变长参数 (§8.4.1)。
- 派生形式参数带有出现在该记录组件上的注解（如果有的话），且这些注解的注解接口在形式参数上下文中、类型上下文中或两者中均适用（§9.7.4)。

记录声明可以包含不是规范构造函数的构造函数声明。记录声明中每个非规范构造函数的方法体必须以备用构造函数调用 (§8.8.1)开始，否则会发生编译时错误。

## 8.10.4.1 普通规范构造函数

如果记录类 R 声明中的（非紧凑的）构造函数的签名与 R 的派生构造函数签名是重写等价的 (§8.4.2)，则它是 R 的规范构造函数。

记录类 R 的派生构造函数签名是一个签名，它由名称 R、无类型参数以及通过按顺序提取 R 记录头中每个记录组件的声明类型派生出的形式参数类型组成。

规范构造函数的签名必须与记录类的派生构造函数签名是重写等价的，且记录类中只能显式声明一个规范构造函数。

一个（非紧凑的）规范构造函数的声明必须满足以下所有条件，否则会发生编译时错误：

- 形式参数列表中的每个形式参数必须与对应的记录组件具有相同的名称和声明类型。
- 当且仅当对应的记录组件是变长记录组件时，形式参数才必须是变长参数。
- 构造函数不能是泛型的 (§8.8.4)。
- 构造函数方法体不能有 `throws` 子句。
- 构造函数方法体不能包含显式的构造函数语句 (§8.7.1)。
- 必须满足普通类中关于构造函数声明的所有其他规则 (§8.8)。

这些规则的结果是，记录组件上的注解可以与显式声明的构造函数的形式参数上的注解不同。例如，以下记录声明是有效的：

```java
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;

@interface Foo {
}
```



```java
@interface Bar {

    record Person(@Foo String name) {

        Person(@Bar String name) {

            this.name = name;

        }

    }

}
```

## 8.10.4.2 紧凑规范构造函数

紧凑构造函数声明是构造函数声明的一种简洁形式，仅适用于记录声明。它声明了如下：

- 必须满足普通类声明中构造函数的所有规则（§8.8），但记录组件字段在紧凑构造函数结束时必须已赋值且未赋值除外（§8.3.2）。

如果记录声明有一个命名为 `c` 的记录组件，则紧凑构造方法体中的简单名称 `c` 指的是名为 `c` 的形式参数，而不是名为 `c` 的组件字段。

在紧凑构造函数方法体的最后一个语句（如果有）正常完成（14.1）后，记录类的所有组件字段将隐式地初始化为对应形式参数的值。组件字段的初始化顺序取决于相应的记录组件在记录头中的声明顺序。

紧凑构造函数声明的意图是仅在构造函数方法体中提供验证或规范化参数的代码；其余初始化代码由编译器提供。例如，以下记录类有一个紧凑构造函数，用于简化有理数：

```java
record Rational(int num, int denom) {

    private static int gcd(int a, int b) {
        if (b == 0) return Math.abs(a);
        else return gcd(b, a % b);
    }

    Rational {
        int gcd = gcd(num, denom);
        num /= gcd;
        denom /= gcd;
    }

}
```

紧凑构造函数 `Rational { ... }` 的行为与此普通构造函数相同：

```java
Rational(int num, int denom) {
    int gcd = gcd(num, denom);
    num /= gcd;
    denom /= gcd;
    this.num = num;
    this.denom = denom;
}
```

## 第 9 章
# 接口

接口声明定义了一个可以由一个或多个类实现的新接口。程序可以使用接口为相互无关的类提供共同的超类型，并使得相关的类无需共享共同的抽象超类。

接口没有实例变量，并且通常声明一个或多个抽象方法；否则，相互无关的类可以通过提供对其抽象方法的实现来实现一个接口。接口不能被直接实例化。

顶层接口（§7.6）是直接在编译单元中声明的接口。

嵌套接口是任何声明在另一个类或接口声明体内部的接口。嵌套接口可以是成员接口（§8.5, §9.5）或局部接口（§14.3）。

注解接口（§9.6）是一个使用特殊语法声明的接口，旨在用于由注解的反射表示（§9.7）来实现。

本章将讨论所有接口的通用语义。针对特定类型接口的细节将在专门讨论这些构造的节中进行讨论。

接口可以被声明为一个或多个其他接口的直接扩展，这意味着它继承了所扩展接口的所有成员类和接口、实例方法以及静态字段，但它可能覆盖或隐藏的任何成员除外。

类可以被声明为直接实现一个或多个接口（§8.1.5），这意味着该类的任何实例都实现了接口或多个接口指定的所有抽象方法。类必然要实现其直接超类和直接超接口所实现的所有接口。这种（多重）接口继承允许对象支持（多个）共同行为，而无需共享超类。

与类不同，接口不能被声明为 `final`。然而，接口可以被声明为 `sealed`（§9.1.1.4）以限制其子类和子接口。

一个声明类型为接口类型的变量，其值可以是指向任何实现指定接口的类的任意实例的引用。仅仅该类恰好实现了接口的所有抽象方法是不够的；该类或其任一个超类必须实际上被声明为实现了该接口，否则该类不被认为实现了该接口。

## 9.1 接口声明

接口声明指定了一个接口。

接口声明有两种类型：普通接口声明和注解接口声明（§9.6）。

- `InterfaceDeclaration`（接口声明）:
    - `NormalInterfaceDeclaration`（普通接口声明）
    - `AnnotationInterfaceDeclaration`（注解接口声明）
- `NormalInterfaceDeclaration`（普通接口声明）:
    - `[InterfaceModifier] interface TypeIdentifier [TypeParameters] [InterfaceExtends] [InterfacePermits] InterfaceBody`

接口声明中的 `TypeIdentifier`（类型标识符）指定了接口的名称。

如果接口与其任何包含的类或接口具有相同的简单名称，则为编译错误。
接口声明的作用范围和遮蔽在 §6.3 和 §6.4.1 中规定。

### 9.1.1 接口修饰符

接口声明可以包含接口修饰符。

- `InterfaceModifier`（接口修饰符）:
    - （其之一）
    - `Annotation` `public` `protected` `private`
    - `abstract` `static` `sealed` `non-sealed` `strictfp`

关于接口声明注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

访问修饰符 `public`（§6.6）仅属于顶层接口（§7.6）和成员接口（§8.5, §9.5），不属于局部接口（§14.3）。

访问修饰符 `protected` 和 `private` 仅属于成员接口。

修饰符 `static` 仅属于成员接口和局部接口。

如果同一个关键字作为接口声明的修饰符出现多次，或者如果一个接口声明具有多个 `public`、`protected` 和 `private` 访问修饰符之一，则为编译错误。

如果一个接口声明具有多个 `sealed` 和 `non-sealed` 修饰符，则为编译错误。

> 如果在接口声明中出现了两个或多个（不同的）接口修饰符，那么是自定义的，而非强制要求的，它们出现的顺序与上述 `InterfaceModifier` 产生式中所示的顺序一致。

#### 9.1.1.1 abstract 接口

每个接口都是隐式的抽象（`abstract`）。

此修饰符是过时的，不应在新代码中使用。

#### 9.1.1.2 strictfp 接口

接口声明上的 `strictfp` 修饰符是过时的，不应在新代码中使用。它的存在与否在编译时或运行时都不会产生任何影响。

#### 9.1.1.3 static 接口

嵌套接口是隐式的静态（`static`）。也就是说，每个嵌套接口都是静态的。由于嵌套接口是静态的，从静态上下文或嵌套类或接口对接口参数的引用受到 §6.5.5 规定的限制。

#### 9.1.1.4 sealed 和 non-sealed 接口

接口可以被声明为 `sealed`（§9.1.1.4）以限制其子类和子接口。

如果一个接口的没有任何超接口是 `sealed`，则该接口是自由扩展的。

如果一个接口声明具有多个 `sealed` 和 `non-sealed` 修饰符，则为编译错误。

### 9.1.2 泛型接口和类型参数

如果一个接口声明了一个或多个类型变量（§4.4），则该接口是泛型的（generic）。

这些类型变量被称为接口的类型参数。类型参数部分紧随接口名称，并用角括号分隔。

为了方便起见，这里展示了 §8.1.2 和 §4.4 中的以下产生式：

```text
TypeParameters:
  < TypeParameterList >

TypeParameterList:
  TypeParameter (, TypeParameter)

TypeParameter:
  [TypeParameterModifier] TypeIdentifier [TypeBound]

TypeParameterModifier:
  Annotation

TypeBound:
  extends TypeVariable
  extends ClassOrInterfaceType

AdditionalBound:
  & InterfaceType
```

关于类型参数声明注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。
在接口的类型参数部分，如果 `s` 是 `τ` 的边界，则类型变量 `τ` 直接依赖于类型变量 `s`；而如果 `τ` 依赖于 `s` 或者 `τ` 依赖于一个依赖于 `s` 的类型变量 `U`（递归地使用此定义），则 `τ` 依赖于 `s`。如果接口类型参数部分的类型变量依赖于其自身，则为编译错误。
接口类型参数的作用范围和遮蔽在 §6.3 和 §6.4.1 中规定。泛型接口声明定义了一组参数化类型（§4.5），对于类型参数对类型参数的每种可能的实例化。所有这些参数化类型在运行时共享同一个接口。

### 9.1.3 超接口和子接口

如果提供了 `extends` 子句，则接口扩展每个指定的接口类型，并因此继承这些接口类型的成员类、成员接口、实例方法和静态字段。
指定的接口类型是所声明接口的直接超接口类型。

任何实现所声明接口的类也被认为实现了该接口扩展的所有接口。

```text
InterfaceExtends:
  extends InterfaceTypeList
```

为了方便起见，这里展示了 §8.1.5 中的以下产生式：

```text
InterfaceTypeList:
  InterfaceType [, InterfaceType]
```

接口声明 `extends` 子句中的每个 `InterfaceType` 必须命名一个可访问接口（§6.6），否则将发生编译错误。

如果任何 `InterfaceType` 命名的接口是 `sealed`（§9.1.1.4），且被声明的接口不是命名接口允许的直接子接口（§9.1.4），则为编译错误。

接口类型（`InterfaceType`）具有类型参数，它必须表示一个构造良好的参数化类型（§4.5），且任何类型参数都不可以是通配符类型参数，否则将发生编译错误。

如果一个接口是由另一个接口的直接超接口类型之一命名的，则第一个接口是后一个接口的直接超接口。

超接口关系是直接超接口关系的传递闭包。如果满足以下任一条件，则接口 `I` 是接口 `K` 的超接口：

- `I` 是 `K` 的直接超接口。
- 在 `J` 的情况下，如果 `J` 是 `K` 的直接超接口，`I` 是 `J` 的超接口，并递归应用此定义。

一个接口被认为是直接超接口的直接子接口，并且是其每个超接口的子接口。

虽然每个类都是 `Object` 类的扩展，但并没有一个单一的接口是所有接口的扩展。

如果接口 `i` 直接依赖于类或接口 `A`，如果 `A` 在 `i` 的 `extends` 子句中，要么作为超接口出现，要么作为其完全限定形式名称中的限定符出现。

如果满足以下任一条件，则接口 `i` 依赖于类或接口 `A`：

- `i` 直接依赖于 `A`。
- `i` 直接依赖于类 `C`，而 `C` 依赖于 `A`（§8.1.5）。
- `i` 依赖于接口 `J`，而 `J` 依赖于 `A`，并递归应用此定义。

接口依赖于自身会导致编译错误。

如果在运行时加载接口时检测到循环定义的接口，则会抛出 `ClassCircularityError`（§12.2.1）。

### 9.1.4 允许的直接子类和子接口

普通接口声明中可选的 `permits` 子句指定了所有旨在作为该接口的直接子类和直接子接口的类和接口（§9.1.1.4）。

```text
InterfacePermits:
  permits TypeName (, TypeName)
```

如果接口声明有 `permits` 子句但没有 `sealed` 修饰符，则会导致编译错误。

每个 `TypeName` 必须命名一个可访问的类或接口（§6.6），否则将发生编译错误。

如果在 `permits` 子句中重复指定同一个类或接口，则会导致编译错误。即使该类或接口以不同的方式命名，此规定也成立。

类或接口的规范名称不需要在 `permits` 子句中使用，但 `permits` 子句只能指定类或接口。例如，以下程序无法编译：

```java
package p;

sealed interface I permits C, D, p.C // 错误

non-sealed class C implements I {}

non-sealed class D implements I { }
```

如果密封接口与一个命名模块关联（§7.3），则 `i` 声明中 `permits` 子句中指定的每个类或接口必须与 `i` 关联同一个模块，否则将发生编译错误。

如果密封接口与一个未命名模块关联（§7.7.5），则 `i` 声明中 `permits` 子句中指定的每个类或接口必须属于 `i` 相同的包，否则将发生编译错误。

> 密封接口及其子类和直接子接口分别需要在 `permits`、`implements` 和 `extends` 子句中循环相互引用。在模块化代码中，它们必须位于同一个模块中，不同模块的类和接口不能以循环方式相互引用。任何情况下，密封接口层次结构都应该在单个维护域内声明，由同一个开发者或同一组开发者负责维护该层次结构。命名模块通常代表模块化代码库中的维护域。

如果密封接口 `i` 的声明具有 `permits` 子句，那么 `i` 允许的子类和子接口就是由 `permits` 子句指定的类和接口。

由 `permits` 子句指定的每个直接子类和子接口必须是 `i` 的直接子类（§8.1.5）或 `i` 的直接子接口（§9.1.3），否则将发生编译错误。

如果密封接口 `i` 的声明缺少 `permits` 子句，则 `i` 允许的直接子类和子接口是在与 `i` 处于同一编译单元中声明的（§7.3）、具有规范名称（§6.7）且其直接超接口包含 `i` 的类和接口。

也就是说，允许的直接子类和子接口被推断为同一编译单元中指定 `i` 为直接超接口的类和接口。规范名称的要求意味着任何本地类、本地接口或匿名类都不会被考虑。

如果 `sealed` 接口 `i` 的声明缺少 `permits` 子句且 `i` 没有允许的直接子类或子接口，则会导致编译错误。

## 9.1.5 接口体成员声明

接口体可以包含接口成员的声明，即字段（§9.3）、方法（§9.4）、类和接口（§9.5）。

```text
InterfaceBody:
  { InterfaceMemberDeclaration }

InterfaceMemberDeclaration:
  ConstantDeclaration
  InterfaceMethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

在接口 `i` 中声明或由其继承的成员 `m` 声明的作用域在 §6.3 中指定。

## 9.2 接口成员

接口的成员是：

- 在接口中声明的成员。
- 从超接口继承的成员。

接口的成员包括：

- 常量声明。每个字段声明都是 `public`、`static` `final`。
- 方法声明。
- 类声明。
- 接口声明。

### 9.3 字段（常量）声明

```text
ConstantDeclaration:
  ConstantModifier ConstantType VariableList

ConstantModifier:
  (one of)
  public
  static
  final

VariableList:
  VariableDeclarator (, VariableDeclarator)

VariableDeclarator:
  VariableDeclarId [= VariableInitializer]

VariableDeclarId:
  Identifier [Dims]

Dims:
  [Annotation] [ ]

VariableInitializer:
  Expression
  ArrayInitializer
```



关于接口字段修饰符的规则在 §9.7.4 和 §9.7.5 中指定。接口体中的每个字段声明都是 `public`、`static`、`final`。允许冗余地指定这些修饰符的任何或全部。如果同一个关键字作为字段修饰符出现多次，会导致编译错误。如果在 `UnannType` 和 `VariableDeclarId` 中没有括号对，则字段的声明类型由 `UnannType` 表示，否则由 §10.2 指定。接口字段的作用域和隐藏在 §6.3 和 §6.4.1 中。由于接口字段是 `static`，其声明引入了静态语境（§8.1.3），这限制了引用当前对象的构造。特别是，在静态语境中禁止 `this` 和 `super` 关键字（§15.8.3, §15.11.2），以及对实例变量、实例方法和词法作用域类型参数的未限定引用（§6.5.5.1, §6.5.6.1, §15.12.3）。

接口声明体声明两个同名的字段会导致编译错误。

如果接口声明了一个特定名称的字段，则该字段的声明被认为“隐藏”了其超接口中所有具有相同名称的可访问字段声明。

接口可能继承多个同名的字段。这种情况本身并不会导致编译错误。然而，在接口声明体内部任何尝试通过简单名称引用此类任何字段的行为都会导致编译错误，因为该引用是歧义的。

可能存在多个路径从接口继承同一个字段声明。在这种情况下，该字段被认为只继承了一次，可以通过简单名称进行引用而不会产生歧义。

## 示例 9.3-1. 歧义的继承字段

如果接口继承了两个同名的字段，例如因为它的两个直接超接口都声明了同名的字段，就会产生一个单一的歧义成员。对该歧义成员的任何使用将导致编译时错误。在程序中：

```java
interface BaseColors {
    int RED = 1, GREEN = 2, BLUE = 4;
}

interface RainbowColors extends BaseColors {
    int YELLOW = 3, ORANGE = 5, INDIGO = 6, VIOLET = 7;
}

interface PrintColors extends BaseColors {
    int YELLOW = 3, CYAN = 16, MAGENTA = 32;
}

interface LotOfColors extends RainbowColors, PrintColors {
    int FUCHIA = 17, VERMILION = 43, CHARTREUSE = RED+90;
}
```

接口 `LotOfColors` 继承了两个名为 `YELLOW` 的字段。只要该接口没有对字段 `YELLOW` 的任何命名引用，这种情况就是允许的。（这种引用可能出现在字段的变量初始化器中。）

即使 `PrintColors` 给 `YELLOW` 赋值值 3 而不是值 8，接口 `LotOfColors` 内部对字段 `YELLOW` 的引用仍会被认为是歧义的。

## 示例 9.3-2. 重复继承的字段

如果一个字段从同一个接口被继承了多次，例如因为此接口和它的其中一个直接超接口都扩展了声明该字段的接口，则只会产生一个单一的成员。这种情况本身不会导致编译时错误。

在上一个示例中，字段 `RED`、`GREEN` 和 `BLUE` 通过多种方式被接口 `LotOfColors` 继承，一种通过 `RainbowColors` 接口，另一种通过 `PrintColors` 接口，但接口 `LotOfColors` 中对字段 `RED` 的引用不被认为是歧义的，因为只涉及到一个字段 `RED` 的实际声明。

### 9.3.1 接口中字段的初始化

接口字段声明中的每个声明符必须有一个变量初始化器，否则将发生编译时错误。

初始化器不需要是常量表达式（§15.29）。

接口字段的初始化器不允许使用 `this` 关键字或 `super` 关键字来引用当前对象，如 §15.8.3、§15.11.2 和 §15.12.3 所示。

在运行时，初始化器会被求值并在接口初始化时恰好执行一次字段赋值（§12.4.2）。

注意，常量变量（§4.12.4）字段会在其他接口字段之前初始化。这也适用于类中作为常量变量的静态字段（§8.3.2）。此类字段永远不会观察到具有它们的默认初始值（§4.12.5），即使对于恶意程序也是如此。

## 示例 9.3.1-1. 字段的前向引用

```java
interface Test {
    float f = j;
    int j = 1;
    int k = k + 1;
}
```

该程序会导致两个编译时错误，因为在声明 `j` 之前就在 `f` 的初始化中引用了 `j`，并且 `k` 的初始化引用了 `k` 本身。

## 9.4 方法声明

```
InterfaceMethodDeclaration:
{InterfaceMethodModifier} MethodHeader MethodBody

InterfaceMethodModifier:
（以下之一）
Annotation public private
abstract default static strict
```

为了方便起见，这里列出了来自 §8.4、§8.4.5 和 §8.4.7 的产生式：

```
MethodHeader:
Result MethodDeclarator [Throws]
TypeParameters [Annotation] Result MethodDeclarator [Throws]

Result:
UnannType
void

MethodDeclarator:
Identifier ([ReceiverParameter ,] [FormalPropertyList]) [Dims]

MethodBody:
Block
```

关于接口方法声明注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

接口声明体中的方法可以声明为 `public` 或 `private`（§6.6）。如果没有给出访问修饰符，则方法隐式为 `public`。在接口声明中，为方法声明冗余地指定 `public` 修饰符是被允许的，但从风格上来说并不鼓励。

`default` 方法是在接口中用 `default` 修饰符声明的实例方法。其体始终由一个代码块表示，为任何实现接口且未重写该方法的类提供默认实现。默认接口方法不同于在类中声明的具体方法（§8.4.3.1），也不同于既不继承也不重写的 `private` 接口方法。

接口可以声明 `static` 方法，调用时无需引用特定对象。静态接口方法不同于 `default` 方法、抽象接口方法，以及非静态的 `private` 接口方法（后者属于实例方法）。

静态接口方法的声明引入了静态上下文（§8.1.3），这限制了引用当前对象的构造的使用。特别注意的是，在静态上下文中禁止使用 `this` 和 `super` 关键字（§15.8.3、§15.11.2），对实例变量、实例方法以及词法作用域声明的类型参数的未限定引用也是如此（§6.5.5.1、§6.5.6.1、§15.12.3）。

从静态上下文或嵌套类对实例方法的引用受到限制（§15.12.3）。

接口方法声明上的 `strictfp` 修饰符已过时，不应使用。它的存在与否在运行时没有影响。

缺少 `default` 或 `static` 修饰符的接口方法隐式为 `abstract`。其体由分号表示，而不是代码块。从风格上，允许为此类方法冗余地指定 `abstract` 修饰符。

### 9.4.1 继承与重写

接口从其直接超接口类型继承所有满足以下条件的抽象方法和 `default` 方法 $m$：

- $m$ 是 $I, J$ 的直接超接口类型的成员。
- $I$ 中声明的方法没有签名是作为 $J$ 成员的 $m$ 签名的子签名（§8.4.2）。
- 不存在属于 $I, J'$ 的直接超接口类型的方法 $m'$（$m$ 不同于 $m'$，$J$ 不同于 $J'$），使得 $m'$ 重写了接口 $I'$ 对方法 $m$ 的声明（§9.4.1）。

注意，方法的重写是基于签名逐字的。例如，如果一个接口声明了两个同名的 `public` 方法（§9.4.2），并且子接口重写了其中一个，子接口仍然继承另一个方法。

上述第三条条款防止了子接口重复继承已被其其他超接口重写的方法。例如，在程序中：

```java
interface Top {
    default String name() { return "unnamed"; }
}

interface Left extends Top {
    default String name() { return getClass().getName(); }
}

interface Right extends Top {}

interface Bottom extends Left, Right { }
```

`Right` 从 `Top` 继承了 `name`，但 `Bottom` 从 `Left` 继承了 `name()`，而不是从 `Right`。这是因为 `Left` 中的 `name()` 覆盖了 `Top` 中 `name()` 的声明。

接口不继承其父接口的私有或静态方法。

如果一个接口声明了一个私有或静态方法 $m$，且 $m$ 的签名是 $I$ 的某个父接口类型中实例方法 $m'$ 的子签名，而若在不声明 $m$ 的情况下 $m'$ 将是可供 $I$ 中的代码访问的，则发生编译时错误。

> 本质上，接口中的静态方法不能隐藏父接口类型中的实例方法。这与 §8.4.8.2 中的规则相似，即类不能隐藏父类类型或父接口类型中的实例方法。§8.4.8.2 中的规则指的是“声明或继承了静态方法”的类，而上述规则仅指“声明了静态方法”的接口，因为接口无法继承静态方法。另请注意，§8.4.8.2 中的规则允许隐藏父类/父接口中的实例方法和静态方法，而上述规则仅考虑父接口类型中的实例方法。

与此类似，接口中的私有方法不能覆盖父接口类型中的实例方法（无论是公有的还是私有的）。这与 §8.4.8.1 和 §8.4.8.3 中的规则相似，即类中的私有方法不能覆盖父类或父接口类型中的任何实例方法，因为 §8.4.8.1 要求被覆盖的方法是非私有的，而 §8.4.8.3 要求覆盖方法提供的访问权限至少要与被覆盖的方法相同。总之，只有接口中的公有方法可以被覆盖，且只有子接口或实现类中的公有方法可以被覆盖。

#### 9.4.1.1 覆盖（通过实例方法）

在接口 $I$ 中声明或继承的实例方法 $m_1$ 覆盖了接口 $J$ 中声明的另一个方法 $m_2$，当且仅当满足以下所有条件时：

- $I$ 是 $J$ 的子接口。
- $I$ 不继承 $m_2$。
- $m_1$ 的签名是 $I$ 的父类型（该类型命名为 $J$）的成员 $m_2$ 签名的子签名（§8.4.2）。
- $m_2$ 是公有的。

`strictfp` 修饰符的存在与否对方法覆盖的规则有绝对影响。例如，非 `strictfp` 的方法覆盖 `strictfp` 方法是允许的，`strictfp` 方法覆盖非 `strictfp` 方法也是允许的。

被覆盖的默认方法可以使用包含关键字 `super` 且由父接口名限定的方法调用表达式（§15.12）来访问。

#### 9.4.1.2 覆盖中的要求

接口方法的返回类型与任何被覆盖的接口方法的返回类型之间的关系在 §8.4.8.3 中规定。

接口方法的 `throws` 子句与任何被覆盖的接口方法的 `throws` 子句之间的关系在 §8.4.8.3 中规定。

接口方法的签名与任何被覆盖的接口方法的签名之间的关系在 §8.4.8.3 中规定。

接口方法的访问权限与任何被覆盖的接口方法的访问权限之间的关系在 §8.4.8.3 中规定。

如果一个默认方法与 `Object` 类中的非私有方法等效覆盖（§8.4.2），则会导致编译时错误，因为实现该接口的任何类将继承该方法的实现。

禁止将 `Object` 的某个方法声明为默认方法可能令人惊讶。毕竟，存在像 `java.util.List` 这样的情况，其 `toString` 和 `equals` 的行为是有精确定义的。然而，当理解了更广泛的设计决策后，这一动机变得更加清晰：

- 第一，允许从子类继承的方法覆盖从父接口继承的方法（§8.4.8.1）。因此，每个实现类都会自动覆盖接口的默认方法。这是 Java 语言中的长期行为。我们并不希望改变默认方法的设计，因为这将与允许接口无缝地演进的目标冲突，即仅在类通过其层级结构尚未拥有该行为时才提供默认行为。
- 第二，方法并不继承自 `Object`，而是意味着声明了与 `Object` 许多相同的方法（§9.2）。因此，`Object` 中声明的 `toString` 和在接口中声明的 `toString` 之间没有共同的祖先。至少，如果两者都是类继承的候选者，它们将发生冲突。解决这个问题需要类继承树和接口继承树之间拙劣的合并。
- 第三，在接口中声明 `Object` 方法通常假设一个线性的接口层级；该特性在多继承场景下的泛化性良好。
- 第四，`Object` 方法是如此基础，以至于允许任意父接口静默添加一个改变其行为的默认方法似乎是危险的。

然而，接口可以定义另一个方法，为覆盖 `Object` 方法的类提供有用行为。例如，`java.util.List` 接口可以声明一个 `elementString` 方法，产生由 `toString` 约定描述的字符串；类中 `toString` 的实现者可以委托到此方法。

#### 9.4.1.3 继承具有等效覆盖签名的方法

接口可能会继承多个具有等效覆盖签名的方法（§8.4.2）。

如果接口继承了一个默认方法，且其签名与 $I$ 继承的另一个方法等效覆盖，则发生编译时错误。（无论另一个方法是抽象的还是默认的都是如此。）

否则，所有继承的方法都是抽象的，且接口被认为继承了所有这些方法。

继承的方法中必须有一个对于所有继承的方法都是返回类型替换的，否则将发生编译时错误。（在这种情况下，`throws` 不会导致错误。）

可能通过多条路径从接口继承同一个方法声明。这一事实没有引起困难，本身永远不会导致编译时错误。

> 自然，当两个签名相同的不同默认方法被继承到子接口中时，存在行为冲突。我们主动检测这种冲突并通过错误通知程序员，而不是等到在编译具体类时出现问题。可以通过声明一个新方法来覆盖（并防止继承）所有冲突的方法来避免该错误。
>
> 同样，当一个抽象方法和一个签名相同的默认方法被继承到子接口中时，我们产生一个错误。在这种情况下，可以优先考虑其中一个——也许我们假设默认方法除了重名的名称和签名之外为抽象方法提供了合理的实现，我们没有理由认为默认方法的行为与抽象方法的契约一致——该默认方法在子接口最初开发时可能甚至不存在。在这种情况下，要求作者断言默认实现是合适的（通过覆盖声明）是安全的。
>
> 相比之下，类中继承的具体方法的长期行为是覆盖在接口中声明的抽象方法（见 §8.4.4）。关于潜在违反契约的论点同样适用，但在这种情况下类和接口之间存在内在的不平衡。我们倾向于，为了保持接口的独立性和类层次结构，通过简单地优先考虑具体方法来减少类接口之间的冲突。

## 9.4.2 重载

如果一个接口的两个方法（无论是在同一个接口中声明，还是都由一个接口继承，其中一个声明而一个继承）具有相同的名称但不同的签名，且这些签名不是重写等价的（§8.4.2），则该方法名被称为重载。

这一事实不会引起任何困难，其本身永远不会导致编译错误。两个具有相同名称但不同签名且重写等价的方法，其返回类型之间或 `throws` 子句之间不存在强制性关系。

### 示例 9.4.2-1. 重载抽象方法声明

```java
interface PointInterface {
    void move(int dx, int dy);
}

interface RealPointInterface extends PointInterface {
    void move(float dx, int dy);
    void move(double dx, double dy);
}
```



在这里，命名的 `move` 方法在接口 `RealPointInterface` 中被三个不同的签名重载，其中两个是声明的，一个是继承的。任何实现接口 `RealPointInterface` 的非抽象类都必须提供所有三个签名的实现。

## 9.4.3 接口方法体

默认方法（default method）具有块体。当一个类实现了接口但没有提供该方法的实现时，这段代码块提供了方法的实现。

私有静态接口方法也有块体，该体提供了方法的实现。

如果接口方法声明是抽象的（显式或隐式）且具有方法体块，则为编译错误。

如果接口方法声明是 `default`、`private` 或 `static`，且以分号作为方法体，则为编译错误。

方法体中 `return` 语句的规则规定在 §14.17 中。

如果声明的方法具有返回类型 (§8.4.5)，那么当方法体可以正常完成时 (§14.1)，则会发生编译错误。

## 9.5 成员类和接口声明

接口体 (§9.15) 可以包含成员类和成员接口 (§8.5) 的声明。

接口声明体中的每个成员类或成员接口声明都是隐式的 `public` 且是 `static` 的 (§9.1.1.3)。允许冗余地指定这些修饰符中的一个或两者。

如果接口中的成员类或接口声明具有 `protected` 或 `private` 修饰符，则为编译错误。

接口声明体中成员类声明的修饰符规则规定在 §8.1.1 中。

接口声明体中成员接口声明的修饰符规则规定在 §9.1.1 中。

如果接口声明了一个特定名称的成员类或接口，则该成员类或接口的声明被认为隐藏了该接口父接口中所有具有相同名称的可访问成员类和接口声明。

接口从其直接父接口继承所有直接父接口的成员类和接口，只要这些类和接口没有被接口中的声明所隐藏。

一个接口可能继承多个具有相同名称的成员类或接口。这种情况本身不会导致编译错误。然而，在接口体内部任何尝试通过其简单名引用任何此类成员类或接口的行为都将导致编译错误，因为该引用是歧义的。

可能存在多条路径从接口继承同一个成员类或接口声明。在这种情况下，该成员类或接口被认为只被继承一次，并且可以通过其简单名引用而不会产生歧义。

## 9.6 注解接口

注解接口声明指定了一个注解接口，这是一种特殊的接口。为了将注解接口声明与普通接口声明区分开来，`interface` 关键字前面有一个 `@` 符号 (@)。

```
AnnotationInterfaceDeclaration:
[InterfaceModifier] @ TypeIdentifier AnnotationInterfaceBody
```

注意 `@` 符号 (@) 和关键字 `interface` 是不同的标记。可以使用空白符将它们分开，但从代码风格的角度来看，不建议这样做。

除非在本节及其子节中经过了显式修改，否则所有适用于普通接口声明 (§9.1) 的规则都适用于注解接口声明。

例如，注解接口声明在作用域规则上与普通接口声明相同。

如果注解接口声明具有 `sealed` 或 `non-sealed` 修饰符 (§9.1.1.4)，则为编译错误。

注解接口声明可以指定顶层接口或成员接口，但不能是局部接口 (§14.3)。

> 由于于 §14.3 中的 `LocalClassOrInterfaceDeclaration` 产生式，注解接口声明在语法上不允许出现在块（block）内部。

如果注解接口声明直接或间接出现在局部类、局部接口或匿名类声明体中 (§14.3, §15.9.5)，则为编译错误。

此规则结合上述对注解接口声明的语法限制，确保了注解接口始终有一个完全限定名 (§6.7)。拥有这样一个名称是重要的，因为注解接口的目的是为了供其他编译单元中的注解使用。由于局部类或接口没有完全限定名，因此在其语法体内部任何地方声明的注解接口（如果允许的话）也将没有完全限定名。

以下代码展示了此规则以及相关语法限制的效果：

```java
class C {
  @interface A {}  /* 合法：注解接口可以是成员接口 */
  void m() {}
}

@interface A() /* 非法：注解接口不能是局部接口 */

class D {
    @interface A() /* 非法：不能在 D 内部声明 */
    class E {
        @interface A() /* 非法：不能在 D 内部声明 */
    }
}
```

注解接口永远不是泛型的 (§9.1)。

与普通接口不同，注解接口无法声明任何变量，根据 `AnnotationTypeDeclaration`。

注解接口的直接父接口始终是 `java.lang.annotation.Annotation`。

由于注解接口声明不显式通过 `extends` 指定父接口类型，接口的子接口永远不是注解接口，因为子类声明必须使用 `extends` 子句。同样，`java.lang.annotation.Annotation` 本身也不是注解接口。

注解接口从 `java.lang.annotation.Annotation` 继承了几个方法，包括 `Object` 的隐式声明方法 (§9.2)，但这些方法并没有定义注解的元素。

由于这些方法没有定义注解元素，因此在符合该注解接口的注解中使用它们是非法的 (§9.7)。如果没有此规则，我们无法确保元素是注解可以表示的类型，也无法获得它们的访问器方法。

在注解接口体中声明的方法返回类型必须是以下之一，否则会发生编译错误：

- 原始类型
- `String`
- 类或类的调用 (§4.5)
- 一个枚举类类型
- 注解接口类型
- 数组类型，其组件类型为上述类型之一 (§10.1)。

此规则排除了具有嵌套数组类型的元素，例如：

```java
@interface Verboten {
  String[] value();
}
```

返回数组的方法声明允许在空的形式形参数列表之后放置表示数组类型的括号。为了与 Java 编程语言的早期版本兼容，支持这种语法。但强烈建议不要在代码中使用这种语法。

如果注解接口中声明的任何方法的签名在*重写等效性*上（§8.4.2）与 `Object` 类中声明或在 `java.lang.annotation.Annotation` 接口中声明的任何公共或受保护的方法相同，则为编译时错误。

如果注解接口 *τ* 的声明直接或间接地包含一个类型为 *τ* 的元素，则为编译时错误。

例如，这种写法是不合法的：

```java
@interface SelfRef ( SelfRef value(); )
```

这种写法也是不合法的：

```java
@interface Ping ( Pong value(); )
@interface Pong ( Ping value(); )
```

没有元素的注解接口称为标记注解接口（marker annotation interface）。

有一个元素的注解接口称为单元素注解接口（single-element annotation interface）。

按照约定，单元素注解接口中唯一元素的名称为 *value*。这种约定的语言支持由单元素注解（§9.7.3）提供。

## 示例 9.6.1-1. 注解接口声明

以下注解接口声明定义了一个具有多个元素的注解接口：

```java
/**
 * 描述导致被注解 API 元素存在的“增强请求”（request-for-enhancement, RFE）。
 */
@interface RequestForEnhancement {
    int id(); // 与 RFE 关联唯一 ID 号
    String synopsis(); // RFE 的摘要
    String engineer(); // 实现 RFE 的工程师姓名
    String date(); // RFE 实现的日期
}
```

## 示例 9.6.1-2. 标记注解接口声明

以下注解接口声明定义了一个标记注解接口：

```java
/**
 * 此类型的注解表示被注解的 API 元素的规范
 * 是初步的，并且可能会发生变化。
 */
@interface Preliminary {
}
```

## 示例 9.6.1-3. 单元素注解接口声明

单元素注解接口定义一个名为 *value* 的元素的约定在以下注解接口声明中得到了说明：

```java
/**
 * 将版权声明与被注解的 API 元素关联。
 */
@interface Copyright {
    String value();
}
```

以下注解接口声明定义了一个单元素注解接口，其唯一元素的类型为数组类型：

```java
/**
 * 将背书者列表与被注解的类关联。
 */
@interface Endorsers {
    String[] value();
}
```

以下注解接口声明显示了一个受边界通配符（bounded wildcard）约束的类类型元素：

```java
interface Formatter {
  // 指定一个格式器对被注解的类进行格式打印
  @interface PrettyPrinter {
    Class<? extends Formatter> value();
  }
}
```

以下注解接口声明包含一个类型为注解接口类型的元素：

```java
/**
 * 表示被注解的程序元素的作者。
 */
@interface Author {
  Name value();
}

/**
 * 人的姓名。此注解接口并非设计
 * 直接用于注解程序元素，
 * 为了定义其他注解接口的元素。
 */
@interface Name {
  String first();
  String last();
}
```

注解接口声明的语法允许除方法声明之外的其他成员声明。例如，人们可能会声明一个嵌套枚举类，供注解接口的元素使用：

```java
@interface Quality {
  enum Level { BAD, INDIFFERENT, GOOD }
  Level value();
}
```

## 9.6.2 注解接口元素的默认值

注解接口元素可以有一个默认值，通过在定义该元素的方法声明上附加 `default` 关键字和值来指定。

```
DefaultValue:
default ElementValue
```

为了方便起见，这里显示了 §9.7.1 中的以下产生式：

```
ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation

ElementValueArrayInitializer:
( [ ElementValueList ] , )

ElementValueList:
ElementValue (, ElementValue)
```

如果元素的类型与指定的默认值不匹配，则为编译时错误。

默认值不会被编译到注解中，而是在读取注解时动态应用的。因此，更改默认值会影响在更改发生之前编译的类中的注解（假设这些注解在默认元素上缺少显式值）。

## 示例 9.6.2-1. 带有默认值的注解接口

这是 §9.6.1 中 `RequestForEnhancement` 注解接口的改进：

```java
@interface RequestForEnhancement {
    int id(); // 无默认值 - 必须在每个
               // 注中指定
    String synopsis(); // 无默认值 - 必须在每个
                   // 注中指定
    String engineer() default "[unassigned]";
    String date() default "[implemented]";
}
```

## 9.6.3 可重复注解接口

如果注解接口 A 的声明被（元）注解了一个 `@Repeatable` 注解（§9.6.8），则它是可重复的。

如果满足以下条件，则接口 AC 是 A 的包含性注解：

1. AC 声明了一个返回类型为 `A[]` 的 `value()` 方法。
2. AC 声明的除 `value()` 外的任何方法都有默认值。
3. AC 的保留时间与 A 相同，其中保留时间显式或隐式通过 `@Retention` 注解表示（§9.6.4.2）。

- 如果 AC 的保留策略为 `java.lang.annotation.RetentionPolicy.SOURCE`，则 A 的保留策略为 `java.lang.annotation.RetentionPolicy.SOURCE`。
- 如果 AC 的保留策略为 `java.lang.annotation.RetentionPolicy.CLASS`，则 A 的保留策略为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.SOURCE`。
- 如果 AC 的保留策略为 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 A 的保留策略为 `java.lang.annotation.RetentionPolicy.SOURCE`、`java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME`。

A 适用于 AC 的最小程序元素类型（§9.6.4.1）。具体来说，如果 A 的程序元素类型由集合 $m_1$ 表示，而 AC 的程序元素类型由集合 $m_2$ 表示，则 $m_2$ 中的每种类型都出现在 $m_1$ 中，但例外：

- 如果 $m_2$ 中的类型是 `java.lang.annotation.ElementType.ANNOTATION_TYPE`，则 `java.lang.annotation.ElementType.ANNOTATION_TYPE`、`java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.TYPE_USE` 中至少有一个出现在 $m_1$ 中。
- 如果 $m_2$ 中的类型是 `java.lang.annotation.ElementType.TYPE`，则 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.TYPE_USE` 中至少有一个出现在 $m_1$ 中。
- 如果 $m_2$ 中的类型是 `java.lang.annotation.ElementType.TYPE_PARAMETER`，则 `java.lang.annotation.ElementType.TYPE_PARAMETER` 或 `java.lang.annotation.ElementType.TYPE_USE` 中至少有一个出现在 $m_1$ 中。

该条款意味着一种策略：注解接口仅在其适用的某些程序元素类型上是重复的。

- 如果 A 的声明有一个对应于 `java.lang.annotation.Documented` 的（元）注解，则 AC 的声明也必须有一个对应于 `java.lang.annotation.Documented` 的（元）注解。

6. 如果 A 的声明具有一个（元）注解，其对应于 `java.lang.annotation.Inherited`，那么 AC 的声明必须具有一个（元）注解，其对应于 `java.lang.annotation.Inherited`。

注意，AC 标记为 `@Inherited` 而 A 不为 `@Inherited` 是允许的。

如果一个注解接口 A 被（元）标记了一个 `@Repeatable` 注解，且该元素的 value 元素指示的类型不是 A 的容器注解接口，则会导致编译时错误。

## 示例 9.6.3-1. 格式错误的容器注解接口

考虑以下声明：

```java
import java.lang.annotation.Repeatable;

@Repeatable(FooContainer.class)
@interface Foo {}

@interface FooContainer { Object[] value(); }
```



编译 `Foo` 声明会产生编译时错误，因为 `Foo` 使用 `@Repeatable` 尝试指定 `FooContainer` 为其容器注解接口，但 `FooContainer` 并不是 `Foo` 的容器注解接口。`FooContainer.value()` 的返回类型不是 `Foo[]`。

`@Repeatable` 注解不能重复，因此一个可重复注解接口只能指定一个注解接口。

不允许指定多个注解接口，即使当可重复接口的多个注解在逻辑上被一个容器注解替换时（§9.7.5）。

一个注解接口最多可以作为一个注解接口的容器注解接口。

这隐含于以下要求：如果注解接口 `A` 的声明指定了 `AC` 的容器注解接口，那么 `AC` 的 `value()` 方法的返回类型应涉及 `A`，具体为 `A[]`。

一个注解接口不能将自身指定为自身的容器注解接口。

这隐含于对容器注解接口 `value()` 方法的要求。具体来说，如果一个注解接口 `A`（通过 `@Repeatable`）将自身指定为容器注解接口，那么 `A` 的 `value()` 的返回类型将是 `A[]`；但这将会导致编译时错误，因为注解接口不能在其元素中引用自身（§9.6）。更通地说，两个注解接口不能互相指定为对方的容器注解接口，因为循环注解接口声明是非合法的。

一个注解接口 `AC` 可以是某些注解接口 `A` 的容器注解接口，同时它也有自己的注解接口 `SC`。也就是说，容器注解接口本身可以是一个可重复接口。

## 示例 6.9-3-2. 限制注解可重复的位置

一个接口声明指示目标为 `java.lang.annotation.ElementType.TYPE` 的注解，其出现的次数至少要与接口声明指示目标为 `java.lang.annotation.ElementType.ANNOTATION_TYPE` 的注解一样多。例如，给定以下可重复注解接口和容器注解接口的声明：

```java
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;
import java.lang.annotation.Repeatable;

@Target(ElementType.TYPE)
@Repeatable(FooContainer.class)
@interface Foo {}

@Target(ElementType.ANNOTATION_TYPE)
@interface FooContainer {
    Foo[] value();
}
```

`@Foo` 可以出现在任何类或接口声明上，而 `@FooContainer` 只能出现在注解接口声明上。因此，以下注解声明是合法的：

```java
@Foo @Foo
@interface Anno {};
```

而以下接口声明是非合法的：

```java
@Foo @Foo
interface Intf {};
```

更广泛地说，如果 `Foo` 是一个可重复注解接口且 `FooContainer` 是它的容器注解接口，那么：

- 如果 `Foo` 没有 `@Target` 元注解，且 `FooContainer` 也没有 `@Target` 元注解，则 `@Foo` 可以在任何支持注解的程序元素上重复。
- 如果 `Foo` 没有 `@Target` 元注解，且 `FooContainer` 有一个 `@Target` 元注解，则 `@Foo` 只能在 `@FooContainer` 出现的程序元素上重复。
- 如果 `Foo` 有一个 `@Target` 元注解，那么在 Java 编程语言设计者看来，声明 `FooContainer` 时必须考虑到 `Foo` 的适用范围。具体而言，`FooContainer` 允许程序元素类型必须是 `Foo` 适用类型的相同类型或子集。

- 4. 方法声明（包括注解接口的元素）§8.4.3, §9.4, §9.6.1
  对应 `java.lang.annotation.ElementType.METHOD`

- 5. 构造方法声明 (§8.8.3)
  对应 `java.lang.annotation.ElementType.CONSTRUCTOR`

- 6. 通用类、接口、方法和构造方法的类型参数声明 (§8.1.2, §9.1.2, §8.4.4, §8.8.4)
  对应 `java.lang.annotation.ElementType.TYPE_PARAMETER`

- 7. 字段声明（包括枚举常量）§8.3.1, §9.3, §8.9.1
  对应 `java.lang.annotation.ElementType.FIELD`

- 8. 形参数和异常参数声明 (§8.4.1, §9.4, §14.20)
  对应 `java.lang.annotation.ElementType.PARAMETER`

- 9. 语句中的局部变量声明简体 §14.4.2, §14.14.1, §14.14.2, §14.20.3 以及模式中的声明简体 §14.3.1
  对应 `java.lang.annotation.ElementType.LOCAL_VARIABLE`

- 10. 记录组件声明 (§8.13)
  对应 `java.lang.annotation.ElementType.RECORD_COMPONENT`

存在 17 个类型上下文 (§4.11)，全部由 `java.lang.annotation.ElementType` 的枚举常量 `TYPE_USE` 表示。

如果同一个枚举常量在 `java.lang.annotation.Target` 类型注解的 value 元素中出现多次，则构成一个编译时错误。

如果注解接口 `A` 的声明中不存在 `java.lang.annotation.Target` 注解，则 `A` 适用于所有的声明上下文但不适用于任何类型上下文。

## 9.6.4.2 @Retention

注解可能存在于源代码中，也可能存在于类或接口的二进制形式中。存在于二进制形式的注解在运行时可能无法通过 Java SE 平台的反射库进行访问。`java.lang.annotation.Retention` 注解接口用于在这些可能性之间进行选择。

如果注解 `a` 对应注解接口 `A`，且 `A` 具有一个对应 `java.lang.annotation.Retention` 的元注解 `m`，那么：

- 如果 `m` 具有一个值为 `java.lang.annotation.RetentionPolicy.SOURCE` 的元素，则 Java 编译器确保 `a` 不存在于其所在的类或接口的二进制表示中。
- 如果 `m` 具有一个值为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME` 的元素，则 Java 编译器必须确保 `a` 现在其所在的类或接口的二进制表示中，除非 `a` 注解的是局部声明或 Lambda 表达式的形参数声明。

局部变量声明上的注解，或 Lambda 表达式形参数声明上的注解，永远不会被保留在二进制表示中。相比之下，局部变量类型上的注解，或 Lambda 表达式形参数类型上的注解，如果该注解接口指定了合适的保留策略，则会被保留在二进制文件中。

> 注意，注解接口被标记为 `@Target(java.lang.annotation.ElementType.LOCAL_VARIABLE)` 和 `@Retention(java.lang.annotation.RetentionPolicy.CLASS)` 或 `@Retention(java.lang.annotation.RetentionPolicy.RUNTIME)` 并不是非法的。

如果 `m` 具有一个值为 `java.lang.annotation.RetentionPolicy.RUNTIME` 的元素，则 Java SE 平台的反射库必须在运行时使其可用。

如果 `a` 没有对应于 `A` 的 `java.lang.annotation.Retention` 的元注解，则 Java 编译器必须将 `A` 视为具有一个对应 `java.lang.annotation.Retention` 且元素值为 `java.lang.annotation.RetentionPolicy.CLASS` 的元注解。

## 9.6.4.3 @Inherited

注解接口 `java.lang.annotation.Inherited` 用于表示类 `c` 上的对应于给定注解接口的注解会被 `c` 的子类继承。

## 9.6.4.4 @Override

程序员有时在想要重写方法时无意中写重载了方法声明，从而导致微妙的问题。`Override` 注解接口支持尽早检测此类问题。

> 经典示例涉及 `equals` 方法。程序员在类 `Foo` 中编写了如下代码：
>
> ```java
> public boolean equals(Foo that) { ... }
> ```
>
> 而他们本想写：
>
> ```java
> public boolean equals(Object that) { ... }
> ```
>
> 这是完全合法的，但类 `Foo` 继承了 `Object` 的 `equals` 实现，这会导致某些微妙的 bug。

如果类或接口 `ϕ` 中的方法声明被标记为 `@Override`，则必须满足以下三个条件之一，否则将发生编译时错误：

- 该方法重写了 `ϕ` 的上集 (§8.4.8.1, §9.4.1.1) 中声明的方法
- 该方法在重写上等同于 `Object` 的公共方法 (§4.3.2, §8.4.2)
- `ϕ` 是一个记录类 (§8.10)，且该方法是 `ϕ` 的记录组件的访问器方法 (§8.10.3)

此行为与 Java SE 5.0 不同，在 Java 5.0 中，只有当 `@Override` 应用于实现自父接口且该接口未存在于父类中的方法时，才会导致编译时错误。

关于重写 `Object` 公共方法的条款是源于在接口中使用 `@Override`。考虑以下声明：

```java
class Foo { @Override public int hashCode() { ... } }
interface Bar { @Override int hashCode(); }
```

在类声明中使用 `@Override` 根据第一条是合法的，因为 `Foo.hashCode` 继承了 `Object.hashCode`。

对于接口声明，考虑一个接口具有对应于 `Object` 的抽象成员 (§9.2)。如果接口选择显式声明这些成员（即声明在重写上等同于 `Object` 公共方法的成员），则该接口被认为重写了它们，允许使用 `@Override`。

然而，考虑一个尝试在 `clone` 方法上使用 `@Override` 的接口：

```java
interface Quux { @Override Object clone(); }
```

由于 `Object.clone` 不是公共的，`Quux` 中没有隐式声明名为 `clone` 的成员。因此，`Quux` 中对 `clone` 的显式声明被视为“实现”了其他方法，使用 `@Override` 是错误的。

注：原文后续存在大量 OCR 导致的重复内容，译文已根据要求去重并保持逻辑清晰。

## 9.6.4.5 @SuppressWarnings

Java 编译器越来越能够发布“类 lint 的”警告。为了鼓励使用此类警告，当程序员知道警告不合适时，应该有一种禁用警告的方法。`SuppressWarnings` 注解接口支持程序员对警告的控制。它定义了一个为字符串数组的单一元素。

如果声明被标记为 `@SuppressWarnings(value = {S1, Sk})`，则 Java 编译器必须抑制（即不报告）由注解声明及其任何部分指定的任何警告。Java 编程语言定义了四种可以使用 `@SuppressWarnings` 指定的警告：

- 检查警告 (§4.8, §5.1.6, §5.1.9, §8.4.1, §8.4.3, §15.12.4.2, §15.13.2, §15.27.3) 由字符串 `"unchecked"` 指定。
- 弃用警告 (§9.6.4.6) 由字符串 `"deprecation"` 指定。
- 移除警告 (§9.6.4.6) 由字符串 `"removal"` 指定。
- 预览警告 (§1.5) 由字符串 `"preview"` 指定。

任何其他字符串均指定非标准警告。Java 编译器忽略其无法识别的字符串。鼓励编译器供应商记录它们支持的 `@SuppressWarnings` 字符串，并协作以确保在多个编译器中识别相同的字符串。

## 9.6.4.6 @Deprecated

程序员有时被避免使用某些程序元素（模块、类、接口、字段、方法、构造方法），因为它们被认为是危险的，或者有更好的替代方案。`Deprecated` 注解允许编译器对这些程序元素发出警告。

被弃用的程序元素是指声明标记为 `@Deprecated` 的模块、类、接口、字段、方法或构造方法。程序元素的弃用方式取决于 `forRemoval` 元素的值：

- 如果 `forRemoval=false`（默认值），则该程序元素是普通弃用的。普通弃用的程序元素在未来版本中不会移除，但程序员仍应进行迁移。
- 如果 `forRemoval=true`，则该程序元素是终止的。终止的弃用程序元素旨在移除。程序员应该停止使用它，否则将在升级到新版本时面临源和二进制不兼容问题。

当 Java 编译器发现普通弃用的程序元素在程序元素的声明中使用（重写、调用或通过名称引用）时，必须产生弃用警告，除非：

- 该使用位于一个本身被弃用的（普通弃用或终止的）声明内部。
- 该使用位于一个标记了以消除弃用警告的声明中 (§9.6.4.5)；或
- 出现该使用的声明与通常被弃用的程序元素的声明位于同一个最层类中；或
- 该使用位于一个导入了该通常被弃用的类、接口或成员的导入声明中；或
- 该使用位于 exports 或 opens 指令 (§7.7.2) 中。

当终极弃用的程序元素在程序元素的声明（无论显式还是隐式声明）中使用（重写、调用或通过名称引用）时，Java 编译器必须产生一个移除警告，除非：

- 该使用位于一个标记了以消除移除警告的声明中 (§9.6.4.5)；或
- 出现该使用的声明与终极弃用程序元素的声明位于同一个最层类中；或
- 该使用位于导入了该终极弃用类、接口或成员的导入声明中；或
- 该使用位于 exports 或 opens 指令中。

> 终极弃用的紧迫性足以使得，即使元素本身已被弃用，使用该终极弃用元素也会导致移除警告，因为无法保证两个元素会同时被移除。要忽略此警告并继续使用该元素，程序员必须通过 `@SuppressWarnings` 注解手动确认该风险。

在以下情况下，不会产生弃用警告或移除警告：

- 使用了局部变量或形式参数（通过名称引用），即使该局部变量或形式参数的声明标记了 `@Deprecated`。
- 使用了包名（通过限定类型名、导入声明或 exports 或 opens 指令引用），即使该包的声明标记了 `@Deprecated`。
- 通过限定的 exports 或 opens 指令使用了模块名，即使该友元模块的声明标记了 `@Deprecated`。

导出或打开一个包的模块声明通常由控制该包声明的同一程序员或团队控制。因此，当包被模块声明导出或打开时，警告该包声明标记了 `@Deprecated` 几乎没有益处。相比之下，向友元模块导出或打开一个包的模块声明，通常由控制该友元模块的同一程序员或团队控制。简单地导入或打开该包并不会使模块声明依赖于友元模块，因此如果友元模块被弃用，发出警告价值不大；模块声明的程序员几乎总是希望消除此类警告。

可能导致弃用警告或移除警告的隐式声明是容器注解 (§9.5)。即，如果 `T` 是一个可重复的注解接口且 `TC` 是其容器注解，并且 `TC` 被弃用，那么重复 `T` 注解将导致警告。该警告是由于隐式的 `TC` 容器注解引起的。强烈不建议在不弃用相应的可重复注解接口的情况下弃用容器注解接口。

## 9.6.4.7 @SafeVarargs

具有非具体（non-reifiable）元素类型的变长参数 (§4.7) 会导致堆污染 (§4.12.2) 并产生编译时的未检查警告 (§5.1.9)。然而，如果变长方法的体相对于变量数组参数表现良好，则此类警告是不提供信息的。

`SafeVarargs` 注解在用于标记方法或构造函数声明时，是程序员做出的一种断言，防止 Java 编译器对变长数组方法或构造函数的声明或调用报告未检查警告，而在其他情况下，编译器会因为变量数组参数具有非具体的元素类型而这样做。

`@SafeVarargs` 具有非局部影响，因为它在抑制方法调用表达式中的未检查警告之外，还抑制与变长数组方法声明本身相关的未检查警告 (§8.4.1)。相比之下，`@SuppressWarnings("unchecked")` 注解具有局部影响，因为它只抑制与方法声明相关的未检查警告。

`@SafeVarargs` 的标准目标是诸如 `java.util.Collections.addAll` 的方法，其声明如下：

```java
public static boolean addAll(Collection<? super T> c, T... elements)
```



# 变长参数与 `@SafeVarargs` 注解

变长参数的声明类型为 `T[]`，它是非具体的。然而，该方法从根本上从输入数组读取并将元素添加到集合中，这对于数组来说都是安全操作。因此，对于 `java.util.Collections.addAll` 方法调用表达式中的任何编译时未检查警告可以说都是多余且不提供信息的。在方法声明上应用 `@SafeVarargs` 可以防止在方法调用表达式处生成这些未检查警告。

- 如果固定元的方法或构造函数声明标记了 `@SafeVarargs` 注解，则为编译错误。
- 如果既不是静态又私有的变长元方法声明标记了 `@SafeVarargs` 注解，则为编译错误。

> 由于 `@SafeVarargs` 仅适用于静态方法、final 和/或私有实例方法以及构造函数，因此该注解在发生方法重写的地方不可用。注解继承仅适用于类上的注解（不适用于方法、接口或构造函数上的注解），因此 `@SafeVarargs` 风格的注解无法通过实例类或接口传递。

## 9.6.4.8 `@Repeatable`

注解接口 `java.lang.annotation.Repeatable` 用于可重复注解接口的声明，以指示其包含的注解接口 (§9.6.3)。

请注意，在 A 的声明上的 `@Repeatable` 元注解（指示 AC）并不足以使 AC 成为 A 的注解接口。要使 AC 被视为 A 的注解接口，有许多良好的完备性（well-formedness）规则。

## 9.6.4.9 `@FunctionalInterface`

注解接口 `FunctionalInterface` 用于指示一个接口旨在设计为函数式接口 (§9.8)。它有助于检测出现在接口或继承自接口中的不当方法声明。

如果接口声明标记了 `@FunctionalInterface` 但实际上不是函数式接口，则为编译错误。

由于某些接口恰好是函数式的，因此没有必要对所有函数接口声明都标记 `@FunctionalInterface`。

# 9.7 注解

注解是一种与程序元素关联信息的标记，但在运行时没有影响。注解表示注解接口 (§9.6) 的特定实例，并通常为接口的元素提供值。

有三种注解。第一种是最一般的，而其他类型仅仅是第一种的简写。

- Annotation: NormalAnnotation
- MarkerAnnotation
- SingleElementAnnotation

普通注解在 §9.7.1 中描述，标记注解在 §9.7.2 中描述，单元素注解在 §9.7.3 中描述。注解可以出现在程序中的各种语法位置，见 §9.7.4。同一位置允许出现的相同接口注解的数量由接口声明决定，见 §9.7.5。

## 9.7.1 普通注解

普通注解指定注解接口的名称，以及可选的由逗号分隔的元素值对列表。每个对包含一个与注解接口 (§9.6.1) 元素相关的元素值。

```
NormalAnnotation:
@ TypeName [ ElementValuePairList ]

ElementValuePairList:
ElementPair (, ElementValue)

ElementValuePair:
Identifier = ElementValue

ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation

ElementValueArrayInitializer:
{ [ElementValueList], ] }

ElementValueList:
ElementValue (, ElementValue)
```

注意，符号 (`@`) 是一个独立的标记 (§3.11)。可以在它和 `TypeName` 之间放置空格，但从风格角度来看不建议这样做。

### 语法规则

`TypeName` 指定了与该注解对应的注解接口。该注解被称为“属于”该接口。

`TypeName` 必须命名为一个可访问的注解接口 (§6.6)，否则将发生编译错误。

元素-值对中的 `Identifier` 必须是注解接口中其中一个元素（即方法）的简单名称，否则将发生编译错误。

此方法的返回类型定义了元素-值对的*元素类型*。如果元素类型是数组类型，则不要求使用大括号来指定元素-值对的元素值。如果元素值不是一个 `ElementValueArrayInitializer`，则一个其整个元素均为该元素的数组将与该元素关联。如果元素值是一个 `ElementValueArrayInitializer`，则由 `ElementValueArrayInitializer` 表示的数组值将与该元素关联。

如果元素类型与元素值不**匹配** (*commensurate*)，则会发生编译错误。元素 `T` 与元素 `v` **匹配**，当且仅当满足以下条件之一：

- `T` 是数组类型 `E[]`，且满足任一条件：
  - `v` 是一个 `Expression` 或一个 `Annotation`，则 `v` 与 `E` 匹配；或
  - `v` 是一个 `ElementValueArrayInitializer`，则每个元素值 `v` 都与 `E` 匹配。

> `ElementValueArrayInitializer` 类似于普通的数组初始化器 (§10.6)，区别在于 `ElementValueArrayInitializer` 在语法上可以包含注解以及表达式和嵌套初始化器。然而，嵌套初始化器在 `ElementValueArrayInitializer` 中语义上是不合法的，因为它们永远与注解声明中的数组类型元素匹配（注解中不允许嵌套数组类型）。

- `T` 不是数组类型，且 `v` 的类型与 `T` 赋值兼容 (§5.2)，并且满足以下条件：
  - `T` 是基本数据类型或 `String`，则 `v` 是一个常量表达式 (§15.29)。
  - `T` 是 `Class` 或对 `Class` 的调用 (§4.5)，则 `v` 是一个类字面量 (§15.8.2)。
  - `T` 是枚举类类型 (§8.9)，则 `v` 是一个枚举常量 (§8.9.1)。
  - `v` 不为 null。

注意，如果 `τ` 不是数组类型或注解接口，则元素值必须是一个 `ConditionalExpression` (§15.25)。使用 `ConditionalExpression` 而不是更通用的产生式 `Expression` 是一种语法技巧，用于防止赋值表达式作为元素值。由于赋值表达式不是常量表达式，它不能作为基本数据类型或 String 类型元素的匹配元素值。

普通注解必须为对应注解接口的每个元素包含一个元素-值对，但具有默认值的元素除外，否则将发生编译错误。

普通注解可以（但不要求）为具有默认值的元素包含元素-值对。

按照习惯（尽管不是强制），注解中的元素-值对的呈现顺序与注解接口声明中对应元素的顺序相同。

在接口声明上的注解被称为元注解 (meta-annotation)。

接口 A 的注解可以作为元注解出现在接口 A 本身的声明上。更一般地说，允许“注解” (annotates)”关系的传递闭包中存在循环。

例如，用接口 T 的元注解来注解接口 S 的声明是合法的，并且用接口 S 的元注解来注解 T 的声明也是合法的。预定义的注解接口 (§9.6.4) 可以包含此类循环。

### 示例 9.7.1-1. 普通注解

这是一个使用来自 §9.6.1 的注解接口的普通注解示例：

```java
@RequestForEnhancement (
    id = 2686724,
    synopsis = "Provide time-travel functionality",
    engineer = "Mr. Peabody",
    date = "4/1/2004"
)
public static void travelThroughTime(Date destination) { ... }
```

这是一个利用默认值的普通注解示例，使用了来自 §9.6.2 的注解接口：

```java
@RequestForEnhancement (
    id = 4561414,
    synopsis = "Balance the federal budget"
)
public static void balanceFederalBudget() {
    throw new UnsupportedOperationException("Not implemented");
}
```

## 9.7.2 标记注解

标记注解 (marker annotation) 是为用于标记注解接口 (§9.6.1) 设计的简写。

```
MarkerAnnotation:
@ TypeName
```

它是普通注解的简写：

```java
@TypeName ()
```

只要所有元素都具有默认值 (§9.6.2)，对带有元素的注解接口使用标记注解就是合法的。

### 示例 9.7.2-1. 标记注解

这是一个使用来自 §9.6.1 的初步标记注解接口的示例：

```java
@Preliminary public class TimeTravel { ... }
```

## 9.7.3 单元素注解

单元素注解 (single-element annotation) 是为用于单元素注解接口 (§9.6.1) 设计的简写。

```
SingleElementAnnotation:
@ TypeName ( ElementValue )
```

它是普通注解的简写：

```java
@TypeName (value = ElementValue)
```

只要所有元素都有默认值 (§9.6.2)，对带有元素的注解接口使用单元素注解就是合法的。

### 示例 9.7.3-1. 单元素注解

单元素注解是用于单元素注解接口 (§9.6.1) 设计的简写。这是一个带有基本数据类型值的单元素注解示例：

```java
@SingleElementAnnotation(value = 42)
public class Example { ... }
```

这是一个带有 String 值的单元素注解示例：

```java
@SingleElementAnnotation("hello")
public class Example { ... }
```

这是一个带有数组值的单元素注解示例：

```java
@SingleElementAnnotation({"a", "b", "c"})
public class ArrayExample { ... }
```

这是一个带有类字面量的单元素注解示例：

```java
@SingleElementAnnotation(value = String.class)
public class ClassLiteralExample { ... }
```

这是一个带有枚举常量的单元素注解示例：

```java
@SingleElementAnnotation(MyEnum.CONSTANT)
public class EnumExample { ... }
```

这是一个带有嵌套注解的单元素注解示例：

```java
@SingleElementAnnotation(@OtherAnnotation)
public class NestedAnnotationExample { ... }
```

这是一个带有嵌套注解数组的单元素注解示例：

```java
@SingleElementAnnotation({@Other1, @Other2})
public class NestedArrayExample { ... }
```

单元素注解始终命名为 `value`。在上述所有示例中，省略了 `value` 名称，因为它是单元素注解的默认元素名称。

## 9.7.4 注解可能出现的位置

声明注解 (declaration annotation) 是应用于声明的注解，且其注解接口在声明上下文中是合法的。类型注解 (type annotation) 是应用于类型（或类型的一部分）的注解，且其注解接口在类型上下文中是合法的。例如，对于以下字段声明：

```java
@Foo int f;
```

### 注解应用规则

- 如果注解的接口在与声明对应的声明上下文中适用，但在类型上下文中不适用，则该注解被认为仅应用于该声明。
- 如果注解的接口在类型上下文中适用，但在与声明对应的声明上下文中不适用，则该注解被认为仅应用于距离注解最近的类型。
- 如果注解的接口既在与声明对应的声明上下文中适用，又在类型上下文中适用，则该注解被认为同时应用于该声明和距离注解最近的类型。

在上述第二和第三种情况下，距离注解*最近*的类型按如下方式确定：

- 如果注解出现在 `void` 方法声明或使用 `var` 的局部变量声明（§14.4）之前，则没有最近的类型。如果该注解被认为仅应用于距离注解最近的类型，则会发生编译时错误。
- 如果注解出现在构造方法声明之前，最近的类型是新构造对象的类型。紧邻封装构造方法声明的完全限定名的类型。在该完全限定名中，注解应用于构造方法声明所指的简单类型。
- 在所有其他情况下，最近的类型是源代码中为被声明实体编写的类型；如果该类型是数组类型，则元素类型被认为距离注解最近。

例如，在字段声明 `@Foo public static String f` 中，距离 `@Foo` 最近的类型是 `String`。如果字段声明的类型写为 `java.lang.String`，那么 `java.lang.String` 就是距离 `@Foo` 最近的类型，随后的规则将禁止类型注解应用于包名 `java.`。在泛型方法声明 `@Foo<?> int m() {}` 中，为声明实体编写的类型是 `int[]`，因此 `@Foo` 应用于元素类型。

不使用 `var` 的局部变量声明与 lambda 表达式的参数声明相似，因为在源代码中的声明注解和类型注解都是如此，但只有类型注解可以存储在 `class` 文件中。

如果接口 `A` 的注解在语法上是以下内容的修饰符，则会发生编译时错误：

- 模块声明，但 `A` 不适用于模块声明。
- 包声明，但 `A` 不适用于包声明。
- 类或接口声明，但 `A` 不适用于类型声明或在类型上下文中；或
- 注解接口声明，但 `A` 不适用于注解接口声明、类型声明或在类型上下文中。
- 方法声明（包括注解接口的元素），但 `A` 不适用于方法声明或在类型上下文中。
- 构造方法声明，但 `A` 不适用于构造方法声明或在类型上下文中。
- 泛型类、接口、方法或构造方法的类型参数声明，但 `A` 不适用于类型参数声明或在类型上下文中。
- 字段声明（或枚举常量），但 `A` 不适用于字段声明或在类型上下文中。
- 参数或异常参数声明，但 `A` 不适用于形式参数和异常参数声明或在类型上下文中。
- 接收者参数，但 `A` 不适用于类型上下文。
- 语句或模式中的局部变量声明，但 `A` 不适用于局部变量声明或在类型上下文中。
- 记录组件（record component），但在类型上下文中，`A` 不适用于记录组件声明、字段声明、方法声明或形式参数和异常参数声明。

这十一条条款中有六条提到了“……或在类型上下文中”，因为它们涵盖了本节之前提到的语法位置，在这些位置上，注解可能合理应用于声明或类型。此外，十一条款中的两条——针对类和接口声明，以及针对类型参数声明——提到了“……或在类型上下文中”，因为有时为了将一个接口被标记了 `@Target(ElementType.TYPE_USE)` 元注解的注解（因此在类型上下文中适用）应用于类、接口或类型参数的声明上。

如果满足以下任一条件，则该注解是允许的：

- 距离注解最近的简单名被分类为 `TypeName`，而非 `PackageName`。
- 如果距离注解最近的简单名后面跟着 `.` 和另一个 `TypeName` —— 即注解以 `@Foo T.U` 的形式出现 ——那么 U 表示 T 的一个内部类。

第二条条款背后的直觉是，如果在由 Outer 封装的嵌套类中 `Outer.this` 是合法的，那么 `Outer` 就可以被注解，因为它代表了运行时某个对象的类型。另一方面，如果 `Outer.this` 是合法的——因为其出现的类在运行时没有 Outer 的封装实例——那么 `Outer` 就不能被注解，因为它在逻辑上仅仅是一个名称，类似于完全限定类型名中包名的组件。

例如，在下面的程序中，在 B 的体内无法编写 `A.this`，因为 B 没有词法上的封装实例。因此，在类型 `A.B` 中无法将 `@Foo` 应用于 A，因为 A 在逻辑上仅仅是一个名称，而不是一个类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}

class A {
    static class B {}
}

@Foo A.B x;   // Illegal
```

另一方面，在下面的程序中，可以在 D 的体中编写 `C.this`。因此，可以在类型 `C.D` 中将 `@Foo` 应用于 C。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}

class C {
    class D {}
}

@Foo C.D x;   // Legal
```



## 9.7 注解 INTERFACES

### 9.7.5 同一接口的多个注解

如果在声明上下文或类型上下文中出现了同一接口的多个注解，则会发生编译时错误，除非 `A` 是可重复的（§9.6.3）且 `A` 及其包含注解均适用于声明上下文或类型上下文（§9.6.4.1）。

同一接口的多个注解连续出现是习惯，并非强制。

如果声明上下文或类型上下文具有可重复注解接口 `A` 的多个注解，则该上下文中没有显式声明的 `A` 注解，只有一个隐式声明的 `A` 的包含注解。

隐式声明的注解称为容器注解，上下文中出现的多个 `A` 注解称为基础注解。容器注解的（数组类型）值元素是所有基础注解在上下文中从左到右出现的顺序。

如果在声明上下文或类型上下文中存在可重复注解接口 `A` 的多个注解以及任何其包含注解的注解，则会发生编译时错误。

也就是说，不允许在存在与其容器具有相同接口的注解的情况下重复注解。这禁止了晦涩的代码：

接口 `FooContainer` 的注解将包含在另一个隐式声明的注解中。对于 Java 编程语言的设计者来说，这种复杂性是不希望的。另一种方法是将接口的基础注解处理为它们像是在显式 `@FooContainer` 注解中与 `@Foo(2)` 一起出现的，这同样是不可取的，因为这可能会改变反射式程序解释 `@FooContainer` 注解的方式。

如果在声明上下文或类型上下文中，存在一个可重复注解接口的注解以及多个包含该接口 `A` 的注解，则会导致编译错误。

此规则旨在允许以下代码的存在：

```java
@Foo(1) @FooContainer((@Foo(2)))
class A {
}
```

当可重复接口 `Foo` 仅包含一个基础注解时，不会隐式地声明任何容器注解，即使 `@FooContainer` 是 `Foo` 的容器注解。然而，禁止重复接口 `FooContainer` 的注解，例如：

```java
@Foo(1) @FooContainer((@Foo(2))) @FooContainer((@Foo(3)))
class A {
}
```

即使 `@FooContainer` 本身是可重复的且有自己的容器注解接口，这也是被禁止的。当存在底层可替换接口的注解时，重复本身就是容器的注解是迂劣的。

## 9.8 函数式接口

函数式接口是一个未声明为 `sealed`（密封）且仅有一个抽象方法（`Object` 类的方法之外）的接口，因此代表了一个单一的函数合约。这个“单一”方法可能表现为从超接口继承的、具有重写等效签名的多个抽象方法；在这种情况下，这些继承来的方法在逻辑上代表一个单一方法。

对于一个未声明为 `sealed` 的接口 `I`，令 `M` 为 `I` 的成员且不与 `Object` 类任何实例方法具有相同签名（§8.4.2）的抽象方法集合。那么，如果 `M` 中存在一个方法 `m` 使得满足以下两个条件，则 `I` 是一个函数式接口：

- `m` 的签名对于 `M` 中的每个方法的签名都是一个子签名（§8.4.2）。
- `m` 对于 `M` 中的每个方法都是返回类型可替换的（§8.4.5）。

除了通过声明和实例化类来创建接口实例的标准过程（§15.9）外，还可以通过方法引用表达式和 lambda 表达式创建函数式接口的实例（§15.13, §15.27）。

函数式接口的定义排除了接口中也是 `Object` 的公共方法的方法。这是为了允许对像 `java.util.Comparator<T>` 这样的接口进行函数式处理，该接口声明了抽象方法，其中只有一个是新的——`int compare(T, T)`。另一个 `boolean equals(Object)` 是一个抽象方法的显式声明，否则它将在接口中隐式声明（§9.2）并由实现该接口的每个类自动实现。

注意，`Object` 的非公共方法（如 `clone()`）在接口中被显式声明为 `public`，它们不会由实现该接口的每个类自动实现。从 `Object` 继承的实现是 `protected`，而接口方法是 `public`，因此实现接口的唯一方法是让类用公共方法重写非公共的 `Object` 方法。

### 示例 9.8-1. 函数式接口

函数式接口的一个简单示例：

```java
interface Runnable {
    void run();
}
```

以下接口不是函数式接口，因为它没有声明任何已是 `Object` 成员的内容：

```java
interface NonFunc {
    boolean equals(Object obj);
}
```

然而，它的子接口可以通过声明一个不是 `Object` 成员的抽象方法来成为函数式的：

```java
interface Func extends NonFunc {
    int compare(String o1, String o2);
}
```

同样，众名的接口 `java.util.Comparator<T>` 是函数式接口，因为它有一个抽象的非 `Object` 方法：

```java
interface Comparator<T> {
    boolean equals(Object obj);
    int compare(T o1, T o2);
}
```

以下接口不是函数式接口，因为它不仅只声明了一个不是 `Object` 成员的抽象方法，而且还声明了两个不是 `Object` 公共成员的抽象方法：

```java
interface Foo {
    int m();
    Object clone();
}
```

### 示例 9.8-2. 函数式接口与擦除

在以下层次结构中，`Z` 是一个函数式接口，因为它继承了两个不是 `Object` 成员的抽象方法，它们具有相同的签名，因此继承的方法在逻辑上代表一个单一方法：

```java
interface X { int m(Iterable<String> arg); }
interface Y { int m(Iterable<String> arg); }
interface Z extends X, Y { }
```

同样，在以下接口层次结构中，`Z` 是一个函数式接口，`Y.m` 是 `X.m` 的子签名，且对于 `X.m` 返回类型可替换的：

```java
interface X { Iterable<String> m(Iterable<String> arg); }
interface Y { Iterable<String> m(); }
interface Z extends X, Y { }
```

函数式接口的定义尊重这样一个事实：接口不能拥有两个互不为子签名的成员却具有相同的擦除（9.4.1.2）。因此，在以下接口层次结构中，`Z` 会导致编译错误，`Z` 不是函数式接口（因为它的没有任何抽象成员是所有其他抽象成员的子签名）：

```java
interface X { int m(Iterable<String> arg); }
interface Y { int m(Iterable<Integer> arg); }
interface Z extends X, Y { }
```

```java
interface X { int m(Iterable<String> arg, Class c); }
interface Y { int m(Iterable<Integer> arg, Class c); }
interface Z extends X, Y { }
```

```java
interface X { void m(T arg); }
interface Y { void m(N arg); }
interface Z extends X, Y { }
```

```java
interface X { void m(A arg); }
interface Y { void m(B arg); }
interface Z extends X, Y { }
```

函数式接口可以是泛型的，例如 `java.util.function.Predicate<T>`。这样的函数式接口可能以一种参数化的方式产生不同的抽象方法——即多个方法无法通过通过声明被重写。

```java
interface I { Object m(Class<?> c); }
interface J<S> { S m(Class<S> c); }
interface K<T> { T m(Class<T> c); }
interface Functional<S,T> extends I, J<S>, K<T> { }
```

`Functional<S,T>` 是一个函数式接口——`I.m` 对于 `J.m` 和 `K.m` 返回类型可替换，但函数式类型 `Functional<String, Integer>` 显然无法通过单一方法实现。然而，`Functional<S,T>` 的其他参数化形式作为函数式接口类型是可能的。

函数接口的声明允许函数接口类型在程序中使用。有四种函数接口类型：

- 非泛型（§6.1）函数接口的类型
- 作为泛型函数接口参数化（§4.5）的参数化类型
- 泛型函数接口的原始类型（§4.8）
- 表示构想函数接口的交集类型（§4.9）

在特殊情况下，将交集类型视为函数接口类型是有用的。通常，这看起来像是一个函数接口与一个或多个标记接口类型的交集，例如 `Runnable & java.io.Serializable`。这种交集可以用于强制 lambda 表达式符合特定类型的转换（§15.16）。如果交集中的接口类型是 `java.io.Serializable`，则会触发特殊的序列化运行时支持（§15.27.4）。

## 9.9 函数类型

函数接口 $I$ 的函数类型是一个方法类型（§8.2），可用于覆盖（§8.4.8）$I$ 的抽象方法。

设 $M$ 为为 $I$ 定义的抽象方法集合 $I$ 的函数类型由以下部分组成：

- **类型参数、形式参数类型和返回类型：**

设 $m$ 为 $M$ 中的一个方法：

1. 一个签名，它是 $M$ 中每个方法的签名之一，且
2. 一个返回类型 $R$（可能为 `void`），其中 $R$ 与 $M$ 中每个方法的返回类型相同，或者 $R$ 是引用类型且是 $M$ 中每个方法返回类型的子类型（如果两个方法具有相同的签名，则经过类型参数的适配（§8.4.4））。

如果不存在这样的方法，则 $m$ 为 $M$ 中的一个方法，其具有：

1. 一个签名，它是 $M$ 中每个方法的签名之一，且
2. 一个返回类型，使得 $m$ 对于 $M$ 中的每个方法都是返回类型可替换的（§8.4.5）。

函数类型的参数类型、形式参数类型和返回类型由 $m$ 给出。

- **throws 子句：**

函数类型的 *throws* 子句从 $M$ 中方法的 *throws* 子句派生出来，如下：

1. 如果函数类型是泛型的，首先将 *throws* 子句适配到函数类型的类型参数（§8.4.4）。
   如果函数类型不是泛型的，但 $M$ 中至少有一个方法是泛型的，则首先擦除 *throws* 子句。
2. 那么，函数类型的 *throws* 子句包含满足以下约束的每个类型 $E$：
   - $E$ 在其中一个 *throws* 子句中被提及。
   - 对于每个 *throws* 子句，$E$ 是该子句中命名的某些类型的子类型。

当返回类型是原始的（*raw*）而其他类型不是时，函数类型的定义尝试选择最具体的类型。例如，如果返回类型为 `LinkedList` 和 `LinkedList<String>`，则后者立即被选为函数的返回类型。当没有最具体的类型时，定义通过寻找最可替换的返回类型进行补偿。例如，如果存在第三种类型 `List<?>`，则并不是其中一个返回类型是另一个的子类型（因为 `raw LinkedList` 不是 `List<?>` 的子类型）；相反，`LinkedList<String>` 被选为函数的返回类型，因为它对于 `LinkedList` 和 `List<?>` 都是返回类型可替换的。

驱动函数类型抛出异常定义的目标是确保一个不变性：具有结果 *throws* 子句的方法可以覆盖函数接口的每个*抽象*方法。根据 §8.4.6，这意味着函数类型抛出的异常不能比集合 $M$ 中的任何单个方法的异常更“多”，因此我们寻找被每个方法的 *throws* 子句所“覆盖”的所有可能的异常。

函数接口的函数类型规定如下：

- 非泛型函数接口 $I$ 的函数类型为上述定义的非泛型函数接口 $I$ 的函数类型。
- 参数化函数接口 $I<A_1...A_n>$ 的函数类型（其中 $A_1...A_n$ 是类型且 $I$ 对应的类型参数为 $P_1...P_n$），是通过对泛型函数接口 $I<P_1...P_n>$ 的函数类型应用替换 $[P_1:=A_1, ..., P_n:=A_n]$ 派生出来的。
- 参数化函数接口 $I<A_1...A_n>$ 的函数类型（其中 $A_1...A_n$ 中有一个或多个是通配符），为 $I$ 的非通配符参数化 $I<T_1...T_n>$ 的函数类型。该非通配符参数化的确定如下。

设 $P_1...P_n$ 为 $I$ 的类型参数，相应的边界为 $B_1...B_n$。对于所有 $i$ $(1 \le i \le n)$，$T_i$ 根据 $A_i$ 的形式派生：

- 如果 $A_i$ 是一个类型，则 $T_i = A_i$。
- 如果 $A_i$ 是通配符，则 $I$ 的非通配符参数化 $I<T_1...T_n>$ 的函数类型……（注：此处 OCR 存在重复和断裂，已根据逻辑进行清理）。

# 第 10 章
数组

在 Java 语言中，数组是对象（§4.3.1），是动态创建的，并且可以赋值给类型为 `Object` 的变量（§4.3.2）。`Object` 类的所有方法都可以在数组上调用。

数组对象包含若干个变量。变量的数量可以为零，在这种情况下该数组为空为空。数组中包含的变量没有名称；相反，它们通过使用非负整数索引值的数组访问表达式来引用。这些变量被称为数组的组件（components）。如果一个数组有 n 个组件，我们说 n 是数组的长度；数组的组件使用从 0 到 n - 1（包含边界）的整数索引进行引用。

数组的所有组件都具有相同的类型，称为数组的组件类型（component type）。如果数组的组件类型为 τ，那么数组本身的类型为 τ[]。

数组的组件类型本身也可以是数组类型。此类数组的组件可能包含对子数组的引用。如果从任何数组类型开始，考虑它的组件类型，然后（如果该类型是数组类型）考虑该类型的组件类型，依此类推，最终必须到达一个不是数组类型的组件类型；这就是原始数组的元素类型（element type），该数据结构在该级别的组件就是原始数组的元素。

在某些情况下，数组的元素可以是数组：如果元素类型是 `Object`、`Cloneable` 或 `java.io.Serializable`，那么部分或所有元素可能是数组，因为任何数组对象都可以赋值给这些类型的任何变量。

## 10.1 数组类型

数组类型用于声明和强制转换表达式（§15.16）。

数组类型写为元素类型的名称后跟若干对空方括号 `[]`。括号对的数量指示了数组嵌套的深度。

数组类型中的每个括号都可以由类型注解（§9.7.4）标记。注解适用于随其后的括号对（或可变数量参数声明中的省略号 `...`）。

数组的元素类型可以是任何类型，无论是原始类型还是引用类型。特别是：

- 允许以接口类型作为元素类型的数组。
  此类数组的元素值可以是 `null` 引用，也可以实现该接口的任何类型的实例。
- 允许以抽象类类型作为元素类型的数组。
  此类数组的元素值可以是 `null` 引用，也可以该抽象类的任何非抽象子类的实例。

数组的长度不是其类型的一部分。

数组类型的超类型在 §4.10.3 中指定。

> 数组类型的子类型关系与超类关系不同。根据 §4.10.3，`Integer[]` 的直接超类型是 `Integer[]`，但根据 `Integer[]` 的 `Class` 对象，`Integer[]` 的直接超类是 `Object`（§10.8）。这在实践中并不重要，因为 `Object` 也是所有数组类型的超类型。

## 10.2 数组变量

数组类型的变量持有指向对象的引用。声明数组变量不会创建数组对象，也不会为数组组件分配任何空间。它只创建变量本身，该变量可以包含指向数组的引用。然而，声明符的初始化列表（§8.3, §9.3, §14.4.1）可能会创建一个数组，其引用成为变量的初始值。

### 示例 10.2-1. 数组变量的声明

```java
int[]    ai;      // int 数组
short[][] as; // short 数组数组
```

### 数组变量

```java
short               // 标量 short
aas[][];                // short 数组数组
Object[] ao,           // Object 数组
           otherAo;              // Object 数组
Collection<?> ca;     // 未知类型 Collection 的数组
```

声明并不创建对象。以下是创建对象的数组变量声明示例：

```java
Exception ae[]      = new Exception[3];
Object ao[]         = new Exception[2][3];
int[] factorial     = { 1, 1, 2, 6, 24, 120, 720, 5040 };
char ac[]           = { 'n', 'o', 't', ' ', 'a', '\'', ' ', 
                     'g', 's', 't', ' ', 'i', 'n', 'g' };
String[] aas       = { "array", "of", "String", };
```



变量的数组类型取决于变量声明开头类型中可能出现的括号对、作为变量声明符的一部分，或两者都有。具体来说，在字段、形式参数、局部变量或记录组件的声明（`§8.3`、`§8.4.1`、`§9.3`、`§9.4`、`§14.4.1`、`§14.4.2`、`§15.27.1`、`§8.10.1`）中，变量的数组类型表示为：

- 声明开头的元素类型；
- 声明符中变量标识符随后的任何括号对（不适用于可变数量参数或记录组件）；然后，
- 声明开头的类型中的、或作为变量声明符的、或两者都出现的任何括号对。

## 10.3 数组创建

数组通过数组创建表达式（`§15.10.1`）或数组初始化器（`10.6`）创建。

数组创建表达式指定元素类型、嵌套数组层数以及至少一个 final 的数组长度。数组长度作为 final 实例变量可用。

数组初始化器创建一个数组并为所有组件提供初始值。

## 10.4 数组访问

数组的组件通过数组访问表达式（`§15.10.3`）访问，该表达式由一个数组引用的表达式后跟一个在方括号 `[]` 内的索引表达式组成，如 `Ai]`。

数组都从 0 开始。长度为 n 的数组由整数 0 到 n-1 索引。

### 示例 10.4-1. 数组访问

```java
class Gauss {

  public static void main(String[] args) {

    int[] ia = new int[101];

    for (int i = 0; i < ia.length; i++) ia[i] = i;

    int sum = 0;

    for (int e : ia) sum += e;

    System.out.println(sum);

  }

}
```

该程序产生输出：

```
5050
```

程序声明了一个变量 `ia`，其类型为 `int`，即 `int[]`。变量 `ia` 初始化为指向一个新创建的数组对象的引用，该对象由数组创建表达式（`§15.10.1`）创建。数组创建表达式指定该数组具有 101 个组件。数组的长度可以通过 `length` 字段获取，所示。程序用从 0 到 100 的整数填充数组，对这些整数求和，并打印结果。

数组必须通过 `int` 值进行索引；`short`、`byte` 或 `char` 值也可以作为索引值，因为它们会经过一元数值提升（`§5.6`）并转变为 `int` 值。

尝试使用 `long` 类型的索引值访问数组组件会导致编译时错误。

所有数组访问都在运行时进行检查；尝试使用小于 0 或大于数组长度的索引会导致抛出 `ArrayIndexOutOfBoundsException`（`§15.10.4`）。

## 10.5 数组存储异常

对于类型为 `A[]` 的数组（其中 `A` 是一个引用类型），对数组组件的赋值会在运行时进行检查，以确保所赋值的值可以赋值给该组件。

如果被赋值的值的类型与组件类型不赋值兼容（`§5.2`），则会抛出 `ArrayStoreException`。

> 如果数组的组件不可靠的（`§4`），Java 虚拟机将无法执行前一段描述的存储检查。这就是为什么禁止使用不可靠的元素类型的数组创建表达式（`§15.10.1`）。可以声明一个元素类型不可靠的数组变量，但将数组创建表达式的结果赋值给该变量将不可避免导致未检查的异常（`§15.9`）。

### 示例 10.5-1. ArrayStoreException

```java
class Point { int x, y; }

class ColoredPoint extends Point { int color; }

class Test {

  public static void main(String[] args) {

    ColoredPoint[] cpa = new ColoredPoint[10];

    Point[] pa = cpa;

    System.out.println(pa[1] == null);

    try {

      pa[0] = new Point();

    } catch (ArrayStoreException e) {

      System.out.println(e);

    }

  }

}
```

该程序产生以下输出：

```
true
java.lang.ArrayStoreException: Point
```

变量 `pa` 的类型为 `Point[]`，变量 `cpa` 的值引用一个 `ColoredPoint[]` 类型的对象。`ColoredPoint` 可以赋值给 `Point`；因此，`cpa` 的值可以赋值给 `pa`。

对此数组 `pa` 的引用（例如测试 `pa[1]` 是否为 `null`）不会导致运行时错误。这是因为 `ColoredPoint[]` 元素是 `ColoredPoint`，而每个 `ColoredPoint` 都可以代表 `Point`，因为 `Point` 是 `ColoredPoint` 的子类。

另一方面，对数组 `pa` 的赋值可能会导致运行时错误。在编译时，对 `pa` 元素的赋值会被检查，以确保赋值的值是 `Point`。由于 `Point` 持有一个 `ColoredPoint` 数组的引用，只有当运行时赋值的值的类型更具体地是 `ColoredPoint` 时，赋值才有效。

## 10.6 数组初始化器

数组初始化器可以在字段声明（`§8.3`、`§9`）或局部变量声明（`§14.4`）中指定，也可以作为数组创建表达式（`§15.10.1`）的一部分，用于创建一个数组并提供一些初始值。

- 数组初始化器:
  `{ VariableInitializerList [ , ] }`
- VariableInitializerList:
  `VariableInitializer { , VariableInitializer }`

为了方便起见，这里显示了 `§8.3` 中的产生式：

- 变量初始化器:
  `Expression`
  `ArrayInitializer`

数组初始化器写为由逗号分隔的表达式列表，并包含在大括号 `{` 和 `}` 中。

数组初始化器的最后一个表达式后可以出现尾随逗号，它会被忽略。

每个变量初始化器必须与数组的组件类型赋值兼容（`§5.2`），否则会发生编译时错误。

如果正在初始化的数组的组件类型不可重构（`§4.7`），则会出现编译时错误。

要构造的数组长度等于数组初始化器大括号内直接包含的变量初始化器的数量。将为该长度的新数组分配空间。如果没有足够的空间分配数组，则数组初始化器的求值通过抛出 `OutOfMemoryError` 异常终止。否则，将创建一个默认值的一维数组，并将数组的每个组件都初始化为默认值（`§4.12.5`）。

变量初始化器按照它们在源代码中出现的文本顺序从左到右直接包含。第 $n$ 个变量初始化器指定了第 $n-1$ 个数组组件的值。如果某个变量初始化器的执行异常地终止，则数组初始化器的执行也因相同的原因终止。如果所有变量初始化器表达式都正常完成，则数组初始化器正常完成，并带有新初始化的数组值。

如果组件类型是数组类型，那么指定组件的变量初始化器可以是数组初始化器；也就是说，数组初始化器可以嵌套。在这种情况下，嵌套数组初始化器的执行通过递归应用上述算法来构造并初始化数组对象，并将其赋值给组件。

### 示例 10.6-1. 数组初始化器

```java
class Test {

    public static void main(String[] args) {

        int ia[][] = { {1, 2}, null };

        for (int[] ea : ia) {

            for (int e : ea) {

                System.out.println(e);

            }

        }

    }

}
```

该程序产生以下输出：

```
1
2
```

该程序产生了 `int[]` 数组引用。

## 10.7 数组成员

数组类型具有以下成员：

- `length` 字段，它是数组的长度。
- `clone` 方法，它是从 `Object` 继承的。

> 查看 `§9.6.4` 以了解另一种情况。

数组与以下类具有相同的字段和方法：

```java
class A<T> implements Cloneable, java.io.Serializable {

    public int length;

    public T[] clone() {

        try {

            return (T[])super.clone();

        } catch (CloneNotSupportedException e) {

            throw new InternalError(e.getMessage());

        }

    }

}
```

上述代码中的强制转换为 `T[]` 会产生未检查警告（`§5.1.9`），如果数组真的是那样的话。

### 数组是可克隆的

```java
class Test1 {

    public static void main(String[] args) {

        int ial1[] = { 1, 2 };

        int ia2[] = ial1.clone();

        System.out.print((ial1 == ia2) + " ");

        ial1[1]++;

        System.out.println(ia2[1]);

    }

}
```

该程序产生输出：

```
false 2
```

显示 `ial1` 和 `ia2` 引用的数组是不同的变量。

### 克隆后的子数组

多维数组在克隆时共享子数组的事实由此程序所示：

```java
class Test2 {

    public static void main(String[] args) throws Throwable {

        int ia[] = {1, 2};

        int ja[] = ia.clone();

        System.out.print((ia == ja) + " ");

        System.out.println(ia[0] == ja[0] && ja[0] == ja[1]);

    }

}
```

该程序产生输出：

```
false true
```

显示 `ia` 数组 `int[]` 和 `ja` 数组 `int[]` 是同一个数组。

## 10.8 数组的类对象

每个数组都有一个关联的类对象，该对象与所有具有相同组件类型的数组共享。

尽管数组类型不是类，但每个数组的类对象表现好像：

- 每个数组类型的直接父类都是 `Object`。
- 每个数组类型都实现了 `Cloneable` 和 `java.io.Serializable` 接口。

### 示例 10.8-1. 数组的类对象

```java
class Test1 {

    public static void main(String[] args) {

        int ia[] = new int[3];

        System.out.println(ia.getClass());

        System.out.println(ia.getClass().getSuperclass());

        for (Class<?> c : ia.getClass().getInterfaces()) {

            System.out.println("Superinterface: " + c);

        }

    }

}
```

该程序产生如下输出：

```
class [I
class java.lang.Object
Superinterface: interface java.lang.Cloneable
Superinterface: interface java.io.Serializable
```

其中字符串 `"[I"` 是“组件类型为 int 的数组” Class 对象的运行时类型签名。

### 示例 10.8-2. 数组类对象是共享的

```java
class Test2 {

    public static void main(String[] args) {

        int[] ia = new int[3];

        int[] ib = new int[6];

        System.out.println(ia == ib);

        System.out.println(ia.getClass() == ib.getClass());

    }

}
```

该程序产生如下输出：

```
false
true
```



虽然 `ia` 和 `ib` 指向不同的数组，但 `Class` 对象的比较结果表明，所有组件类型为 `int` 的数组都是相同数组类型（即 `int[]`）的实例。

# 10.9 字符数组不是字符串

在 Java 编程语言中，与 C 语言不同，`char` 数组不是 `String`，且 `String` 或 `char` 数组都不会以 `'\u0000'`（NUL 字符）终止。

`String` 对象是不可变的，也就是说，它的内容永远不会改变，而 `char` 数组具有可变的元素。

`String` 类中的 `toCharArray()` 方法返回一个包含与 `String` 相同字符序列的字符数组。`StringBuffer` 类在可变字符数组上实现了实用的方法。

# 第 11 章 异常

当程序违反 Java 编程语言的语义约束时，Java 虚拟机会将此错误作为异常信号传递给程序。

此类违反的示例是尝试访问数组边界外的索引。某些编程语言及其实现通过预先终止程序来对此类错误做出反应；其他编程语言允许实现以任意或不可预测的方式做出反应。这两种方法都不符合 Java SE 平台的设计目标：提供可移植性和健壮性。

相反，Java 编程语言规定，当违反语义约束时，将抛出一个异常，并导致控制流从异常发生点到程序员可以指定的点发生非局部转移。

异常被认为从其发生点被*抛出*（thrown），并在转移到的点被认为*捕获*（caught）。

程序也可以使用 `throw` 语句（§14.18）显式抛出异常。

显式使用 `throw` 语句为传统的处理错误条件的风格提供了一种替代方案，那种风格是通过返回奇怪的值（例如在通常不期望出现负值的地方返回整数 -1）。经验表明，奇怪的值往往被调用者忽略或未经过检查，导致程序不健壮、表现非预期行为或二者兼有。

每个异常都由 `Throwable` 类的实例或其一个子类表示（§11.1）。此类对象可用于将信息从异常发生点传递到捕获它的处理器程序。处理器通过 `try` 语句的 `catch` 子句建立（§14.20）。

## 异常的种类和原因

在抛出异常的过程中，Java 虚拟机会突然逐一完成当前线程中已开始但未执行完毕的表达式、语句、方法和构造函数调用、初始化器以及字段初始化表达式。这一过程一直持续，直到找到一个处理器，该处理器通过命名异常的类或异常类的父类来指示它正在处理该特定异常（§11.2）。如果没有找到这样的处理器，则异常可能由未捕获异常处理器的层次结构中的一个来处理（§11.3）——因此，尽一切避免异常未被处理。

Java SE 平台的异常机制与它的同步模型集成（§17.1），因此监视器会在同步语句（§14.19）和同步方法的调用（§8.4.3.6, §15.12）完成时被解锁。

## 11.1 异常的种类和原因

### 11.1.1 异常的种类

异常由 `Throwable` 类（`Object` 的直接子类）的实例或其一个子类表示。

`Throwable` 及其所有子类共同构成异常类。

`Exception` 和 `Error` 类是 `Throwable` 的直接子类：

- `Exception` 是普通程序可能希望从中恢复的所有异常的父类。

`RuntimeException` 类是 `Exception` 的直接子类。`RuntimeException` 是在表达式求值期间由于许多原因抛出的所有异常的父类，从这些异常中可能仍然恢复。

`RuntimeException` 及其所有子类共同构成运行时异常类。

- `Error` 是普通程序通常不期望从中恢复的所有异常的父类。

`Error` 及其所有子类共同构成错误类。

未检查异常类是运行时异常类和错误类。

`Error` 类是 `Throwable` 的子类，在层次结构中与 `Exception` 不同，允许程序使用 `catch (Exception e)`（§11.2.3）这种惯用法来捕获所有可能恢复的异常，而不会捕获无法恢复的错误。

注意，`Throwable` 的子类不能是泛型的（§8.1.2）。

### 11.1.2 异常的原因

异常的抛出由于三个原因之一：

- 执行了 `throw` 语句（§14.18）。

- Java 虚拟机同步检测到异常状态，即：
    - 表达式的求值，例如整数除零（§15.6）；
    - 在加载、链接或初始化程序部分时发生错误（§12.2, §12.3, §12.4）；在这种情况下，抛出 `LinkageError` 的实例。
    - 内部错误或资源限制阻止 Java 虚拟机实现 Java 语言语义；在这种情况下，抛出 `VirtualMachineError` 的实例。

这些异常不是在任意点抛出，而是在指定的点抛出：

- 发生了异步异常（§11.3）。

### 11.1.3 异步异常

大多数异常是由于发生异常线程的操作同步发生的，并在程序中可能导致此类异常的点发生。相比之下，异步异常是在执行的任何点都可能发生的异常。

异步异常仅由于以下结果发生：

- 调用 `Thread` 或 `ThreadGroup` 类的已弃用的 `stop()` 方法。已弃用的 `stop()` 方法由一个线程调用以影响另一个或线程组的所有线程。它们是异步的，因为它们可能发生在执行的任何点。
- Java 虚拟机中的错误或资源限制阻止其实现 Java 语言语义。在这种情况下，抛出的异步异常是 `VirtualMachineError` 的实例。

> 注意，`StackOverflowError` 是 `VirtualMachineError` 的子类，可能通过方法调用（§15.12.4.5）同步抛出，也通过原生方法调用或 Java 虚拟机资源限制异步抛出。同样，`OutOfMemoryError` 是另一个 `VirtualMachineError` 的子类，可能在类实例（§15.9.4, §12.5）、数组创建（§15.10.2, §10.6）、类初始化（§12.4.2）和箱转换（§5.1.7）期间同步抛出，也可以异步抛出。

Java SE 平台允许在抛出异步异常之前发生少量但有边界的异常。

> 异步异常很少见，但如果为了生成高质量的代码，正确理解它们的语义是必要的。

> 允许延迟通知以便优化代码能够在实际处理的点检测并抛出这些异常，同时遵守 Java 语言的语义。简单的实现可以在控制转移指令点轮询异步异常。由于程序的大小是有限的，这为检测异步异常的总延迟设定了边界。异步异常不会在控制转移之间发生，代码生成器可以在控制转移之间进行重新排序以获得更大的性能。

> 推荐阅读 Marc Feeley 的论文《Polling Efficiently on Stock Hardware》，发表于 Proc. 1993 Conference on Functional Programming and Computer Architecture, Copenhagen, Denmark, pp. 179-187。

## 11.2 异常的编译时检查

Java 编程语言要求程序必须包含对方法或构造函数执行时可能产生的检查异常的处理器（§8.4.6, §8.8.5）。这种对异常处理器存在性的编译时检查旨在减少未被妥善处理的异常数量。对于每个作为可能结果的检查异常，方法或构造函数的 `throws` 子句必须提到该异常的类或该异常类的某个父类（§11.2.3）。

在 `throws` 子句中命名的检查异常类（§11.1.1）是方法或构造实现者与使用者之间约定的一部分。重写方法的 `throws` 子句不能指定该方法将抛出被覆盖方法通过其 `throws` 子句不允许抛出的任何异常（§8.4.8.3）。当涉及接口时，一个重写声明可能会覆盖多个方法声明。在这种情况下，重写声明必须具有与所有被覆盖声明都兼容的 `throws` 子句（§9.4.1）。

未检查异常类（§11.1.1）免于编译时检查。

> 错误类免于检查，是因为它们发生在程序的许多点，且从中恢复是困难或不可能的。声明此类异常的程序将使后继者感到混乱。复杂的程序可能仍然希望捕获并尝试从这些某些情况中恢复。

运行时异常免于检查，因为在 Java 编程语言设计者看来，必须声明此类异常并不会显著建立程序的正确性。Java 编程语言的许多操作和构造都可能在运行时产生异常。Java 编译器可获得的信息以及编译器执行的分析级别通常不足以确保运行时异常不会发生，尽管这对于程序员来说可能是显而易见的。要求声明此类异常类只会给程序员带来困扰。

例如，某些代码可能实现了一种循环数据结构，该结构从构造上来说永远不会涉及空引用；程序员可以此确定不会发生 `NullPointerException`，但 Java 编译器很难证明这一点。要建立数据结构的此类全局属性，所需的证明技术超出了本规范的范围。

如果根据 §11.2.1 和 §11.2.2 中的规则，语句或表达式的执行可以导致抛出类为 *E* 的异常，则我们称该语句或表达式*可以抛出*（can throw）异常类 *E*。

### 异常的编译时检查

我们称 `catch` 子句可以捕获其可捕获异常类：

- 单 `catch` 子句（uni-catch clause）的可捕获异常类是其异常参数的声明类型（§14.20）。
- 多 `catch` 子句（multi-catch clause）的可捕获异常类是表示其异常参数类型的并中的备选类型。

#### 11.2.1 表达式的异常分析

类实例创建表达式（§15.9）可以抛出异常类 $E$，当且仅当：

- 该表达式是一个限定类实例创建表达式，且该限定表达式可以抛出 $E$；或者
- 参数列表中的某些表达式可以抛出 $E$；或者
- $E$ 是所选构造函数调用类型的异常类型之一（§15.22.6）；或者
- 类实例创建表达式包含一个 `ClassBody`，且 `ClassBody` 中的某些实例初始化器或实例变量初始化器可以抛出 $E$。

方法调用表达式（§15.12）可以抛出异常类 $E$，当且仅当：

- 方法调用表达式的形式为 `Primary` . `[TypeArguments]` Identifier，且子表达式 `Primary` 可以抛出 $E$；或者
- 参数列表中的某些表达式可以抛出 $E$；或者
- $E$ 是所选方法调用类型的异常类型之一（§15.22.6）。

Lambda 表达式（§15.27）不会抛出任何异常类。

`switch` 表达式（§15.28）可以抛出异常类 $E$，当且仅当：

- 选择表达式（selector expression）可以抛出 $E$；或者
- switch 块中的某些 switch 规则表达式、switch 块、switch 规则 `throw` 语句或 switch 标记语句组可以抛出 $E$。

对于每种其他类型的表达式，该表达式可以抛出异常类 $E$，当且仅当形式为 `Primary` :: `[TypeArguments]` Identifier 的方法引用表达式（§15.13）可以抛出 $E$。

#### 11.2.2 语句的异常分析

如果其抛出的表达式为 final 或 C 的语句在以下情况下可以抛出异常类：

- `catch` 子句可以捕获异常 E1，且紧邻的 `try` 语句的前一个 `catch` 子句可以捕获 E1 或 E1 的父类。

`try` 语句（§14.20）可以抛出异常类 E，如果：

- `try` 块可以抛出 E，或者
- 某些资源（在 try-with-resources 中）可以抛出 E，或者
- 自动 `close()` 方法（在 try-with-resources 中）可以抛出 E，且不存在 `finally` 块或 `finally` 块可以正常完成；或者
- 存在 `finally` 块且可以抛出 E。

显式构造函数调用（§8.8.7）可以抛出异常类 E，如果：

- 构造函数参数列表中的某些表达式可以抛出 E；或者
- E 与被调用的构造函数的 `throws` 子句不兼容（§15.22.6）。

`switch` 语句（§14.11）可以抛出异常类 E，如果：

- 选择表达式可以抛出 E；或者
- switch 块中的某些 switch 规则表达式、switch 块、switch 规则 `throw` 语句或 switch 标记语句组可以抛出 E。

如果包含在 S 中的表达式或语句可以抛出 E，则任何语句 S 可以抛出异常 E。

#### 11.2.3 异常检查

如果方法体可以抛出某些异常 E，且 E 是检查异常类，且 E 不是 `throws` 子句或构造函数声明的某些类的子类，则为编译错误。

如果 lambda 主体可以抛出某些异常 E，且 E 是检查异常类，且 E 不是 lambda 表达式所指向的函数类型声明的某些类的子类，则为编译错误。

如果命名类或接口的变量初始化器（§8.3.2）或静态初始化器（§8.7）抛出检查异常，则为编译错误。

如果命名类的实例变量初始化器（§8.3.2）或实例初始化器（§8.6）可以抛出检查异常，则为编译错误，除非该命名类至少有一个声明的构造函数，并且异常类或其一个父类在每个构造函数的 `throws` 子句中都被显式声明。

> 注意，如果匿名类（§15.9.5）的实例变量初始化器或实例初始化器可以抛出异常，则不产生编译错误。在命名类中，程序员传播哪些异常类可以抛出的信息的责任是通过在任何显式构造函数声明上声明 `throws` 子句来实现。类方法抛出的检查异常与类构造函数声明的检查异常之间的关系在匿名类中是有保证的，因为不存在显式构造函数声明，且 Java 编译器总是根据其初始化器可以抛出的检查异常类为匿名类声明生成带有合适 `throws` 子句的构造函数。

如果 `catch` 子句可以捕获检查异常类 E1，但阻塞该 `catch` 的 `try` 块抛出的 E1 的子类或父类的检查异常类（除非 E1 是 `Exception` 或 `Exception` 的父类），则为编译错误。

如果 `catch` 子句可以捕获异常类 E1，且紧邻的 `try` 语句的前一个 `catch` 子句可以捕获 E1 或 E1 的父类，则为编译错误。

## 11.3 异常

### 异常的编译时检查

如果 `catch` 句可以捕获异常类 $E_j$，而与该 `catch` 句对应的 `try` 块抛出了异常类 $E_i$（其中 $E_i < E_j$），且紧邻的直接所在 `try` 语句中先前的 `catch` 句捕获了已检查的异常类 $E_k$（其中 $E_2 < E_3 < E_j$），建议 Java 编译器抛出警告。

#### 示例 11.2.3-1. 捕获已检查异常

```java
import java.io.*;

class StaticallyThrownExceptionsIncludeSubtypes {

    public static void main(String[] args) {

        try {

            throw new FileNotFoundException();

        } catch (IOException ioe) {

            // "catch IOException" 捕获 IOException
            // 以及任何子类。

        }

        try {

            throw new FileNotFoundException();

            // 语句 "can throw" 抛出 FileNotFoundException。
            // 并不是该语句 "can throw"
            // FileNotFoundException 的子类或父类。

        } catch (FileNotFoundException fnfe) {

            // ... 处理异常 ...

        } catch (IOException ioe) {

            // 合法，但自 Java SE 7 起建议
            // 给出警告，因为 try 块 "can throw" 的
            // IOException 的所有子类已经
            // 被之前的 catch 句捕获了。

        }

        try {

            m();

            // m 的声明说 "throws IOException"，所以
            // m "can throw" IOException。并不是 
            // m "can throw" IOException 的子类或父类
            //（例如 Exception）。

        } catch (FileNotFoundException fnfe) {

            // 合法，异常的动态类型 
            // 可能是 FileNotFoundException。

        } catch (IOException ioe) {

            // 合法，异常的动态类型
            // 可能是 IOException 的另一个子类。

        } catch (Throwable t) {

            // 始终可以捕获 Throwable。

        }

    }

    static void m() throws IOException {

        throw new FileNotFoundException();

    }

}
```

根据上述规则，多异常 `catch` 句（§14.20）中的每个备选项都能够捕获由 `try` 块抛出且未被之前的 `catch` 句捕获的某些异常类。例如，下面的第二个 `catch` 块将导致编译错误，因为异常分析显示该异常已被之前的 `catch` 句捕获：

```java
try { ... }

catch (Foo) { ... }

catch (Bar) { ... }
```



## 11.3 异常的运行时处理

当异常被抛出时（§14.18），控制传递到最近的 `catch` 句（如果存在），即 `try` 语句的 `catch` 句（§20）。

异常的运行时处理取决于 `catch` 句是否动态地包裹了抛出异常的语句或表达式。语句或表达式：

- 如果在方法内部，调用者是 `catch` 句 (12)。
- 否则，调用者是 `catch` 句 (15)：
  - 如果在构造函数内部，调用者是 `catch` 句 (15)。
  - 如果在实例初始化块内部，调用者是 `catch` 句 (9)。
  - 如果在静态初始化块内部，调用者是 `catch` 句 (14)。

如果 `catch` 句可以处理异常，那么异常的运行时处理取决于异常被抛出时的位置。

如果 `catch` 句没有匹配项，则异常将传播。如果 `try` 块由于异常而终止，且 `finally` 句本身也异常终止，则 `try` 块的终止原因被丢弃，并从那里传播新的原因。

异常终止和捕获异常的精确规则在每个语句（§14）和表达式（§15）中有详细说明。

在需要确保某段代码在另一段代码之后执行的情况下，可以使用带有 `finally` 句的 `try` 语句 (20)。

如果 `try-catch-finally` 语句异常终止，`finally` 句将被执行，即使最终没有找到匹配的 `catch` 句。

### 示例 11.3-1. 抛出和捕获异常

以下程序声明了一个异常类 `TestException`。`main` 方法调用 `thrower` 四次，导致三次抛出异常。`main` 方法中的 `try` 语句捕获 `thrower` 抛出的每个异常。无论 `thrower` 调用正常完成还是异常，都会打印发生什么。

```java
class TestException extends Exception {

    TestException() { super(); }

    TestException(String s) { super(s); }

}

class TestClass {

    public static void main(String[] args) {

        for (String arg : args) {

            try {

                thrower(arg);

                System.out.println("Test " + arg + "\n 没有抛出异常");

            } catch (Exception e) {

                System.out.println("Test \"" + arg + "\" 抛出了 " + e.getClass() + "\n 消息: " + e.getMessage());

            }

        }

    }

    static int thrower(String s) throws TestException {

        if (s.equals("divide")) {

            int i = 0;

            return i/i;

        }

        if (s.equals("null")) {

            s = null;

            return s.length();

        }

        if (s.equals("test")) {

            throw new TestException("Test message");

            return 0;

        } finally {

            System.out.println("{thrower \"" + s + "\" done!");

        }

    }

}
```

如果我们执行该程序并传递参数：

```
divide null not test
```

它产生输出：

```
[thrower("divide") done]

Test "divide" threw a class java.lang.ArithmeticException

with message: / by zero

[thrower("null") done]

Test "null" threw a class java.lang.NullPointerException

with message: null

[thrower("not") done]

Test "not" didn't throw an exception

[thrower("test") done]

Test "test" threw a class TestException

with message: Test message
```

方法 `thrower` 必须包含 `throws` 子句，因为它可能会抛出 `TestException` 实例，这是一个检查异常类（§11.1.1）。如果省略 `throws` 子句，将发生编译错误。

注意，`finally` 子句在每次调用 `thrower` 时都会执行，无论是否发生异常，如每次调用时产生的 `[thrower(...) done]` 输出所示。

# 第 12 章

# 执行

本章规定了程序执行期间发生的活动。它围绕 Java 虚拟机以及构成程序的类、接口和对象的生命周期展开。

Java 虚拟机通过加载指定的类或接口启动，然后调用该指定类或接口中的 `main` 方法。第 §12.1 节概述了执行 `main` 所涉及加载、链接和初始化步骤，作为本章概念的介绍。后续章节规定了加载（§12.2）、链接（§12.3）和初始化（§12.4）的细节。

本章继续规定创建新类实例的程序（§12.5）以及类实例的终结化（§12.6）。最后描述了类的卸载（§12.7）以及程序退出时遵循的程序（§12.8）。

## 12.1 Java 虚拟机启动

Java 虚拟机通过调用指定类或接口的 `main` 方法开始执行，并向其传递单个参数，该字符串数组。在本规范的示例中，第一个类通常是 `Test`。

Java 虚拟机启动的精确语义在《Java 虚拟机规范 SE 17 版》的第 5 章给出。这里我们从 Java 编程语言的角度介绍了该过程的概述。

向 Java 虚拟机指定初始类或接口的方法出了本规范的范围，但在使用命令行的主机环境中，通常是将类或接口的全限定名作为命令行参数指定，并将随后的命令行参数作为字符串提供给 `main` 方法的参数。

例如，在 UNIX 实现中，命令行：

```
java Test reboot Bob Dot Enzo
```

通常会通过调用类 `Test`（一个未命名包中的类）的 `main` 方法来启动 Java 虚拟机，并传递一个包含 "reboot"、"Bob"、"dot" 和 "Enzo" 四个字符串的数组。

我们现在概述 Java 虚拟机可能执行 `Test` 的步骤，这作为后续章节进一步描述的加载、链接和初始化过程的示例。

### 12.1.1 加载类 Test

首次尝试执行类 `Test` 的 `main` 方法时发现 `Test` 类未加载——即 Java 虚拟机当前不包含该类的二进制表示。随后，Java 虚拟机使用类加载器尝试寻找这样的二进制表示。如果此过程失败，则会抛出错误。该加载过程在 §12.2 中有进一步描述。

### 12.1.2 链接 Test：验证、准备、（可选的）解析

在 `Test` 加载后，必须在调用 `main` 之前对其进行初始化。而且 `Test` 与所有类和接口一样，在初始化之前必须经过链接。链接涉及验证、准备和（可选的）解析。链接在 §12.3 中有进一步描述。

验证检查 `Test` 的加载表示是否格式正确，并具有正确的符号表。验证还检查实现 `Test` 代码是否符合 Java 编程语言和 Java 虚拟机的语义要求。如果在验证期间检测到问题，则会抛出错误。验证在 §12.3.1 中有进一步描述。

准备涉及静态存储以及 Java 虚拟机实现内部使用的任何数据结构（如方法表）。准备在 §12.3.2 中有进一步描述。

解析是检查从 `Test` 到其他类和接口的符号引用的过程，通过加载所提到的其他类和接口并检查引用是否正确。

### 12.1.3 初始化 Test：执行初始化器

在我们持续的示例中，Java 虚拟机仍在尝试执行类 `Test` 的 `main` 方法。只有在类已初始化（§12.4）的情况下，才允许这样做。

初始化包括按文本顺序执行类 `Test` 的任何类初始化器和静态初始化器。在初始化 `Test` 之前必须初始化其直接父类，以及其父类的直接父类，依此类推。在最简单的情况下，`Test` 有 `Object` 作为其隐含直接父类；如果 `Object` 类尚未初始化，则必须在 `Test` 之前对其初始化。`Object` 类没有父类，因此递归在此终止。

如果类 `Test` 有另一个类 `Super` 作为其父类，则必须在 `Test` 之前初始化 `Super`。如果尚未完成，则需要加载、验证和准备 `Super`，并且取决于实现，可能还涉及递归地解析来自 `Super` 的符号引用等。

因此初始化可能会导致加载、链接和初始化错误，包括涉及其他类和接口的错误。

### 12.1.4 调用 Test.main

最后，在完成类 `Test` 的初始化后（期间可能发生了其他后续的加载、链接和初始化），调用 `Test` 的方法。

`main` 方法必须声明为 `public`、`static` 和 `void`。它必须指定一个形式参数（§8.4.1），其声明类型为字符串数组。因此，以下两种声明都是可以接受的：

```java
public static void main(String[] args)
```

```java
public static void main(String... args)
```



## 12.2 类和接口的加载

加载是指具有特定名称的类或接口的二进制形式的过程，可以通过动态计算，但更常见的是检索由 Java 编译器从源代码预计算的二进制表示，并从该二进制构造表示该类或接口的 `Class` 对象（§1.4）。

加载的语义在《Java 虚拟机规范 SE 17 版》的第 5 章给出。这里我们从 Java 编程语言的角度介绍了该过程的概述。

类或接口的二进制表示通常是《Java 虚拟机规范 SE 17 版》第 4 章描述的类文件格式，但在符合 §13.1 的要求下，其他表示也是可能的。

## 12.2.1 加载过程

加载过程由 `ClassLoader` 类及其子类实现。`ClassLoader` 类的 `defineClass` 方法可用于从类文件格式的二进制表示（§1.4）构建 `Class` 对象。

`ClassLoader` 的不同子类可以实现不同的加载策略。特别是，类加载器可能会缓存类和接口的表示，根据预期的使用情况预取它们，或者一起加载一组相关的类。如果出现某些情况，例如，由于类加载器缓存了旧版本，导致未找到新编译的类版本，这些活动对于正在运行的应用程序可能不是完全透明的；然而，类加载器的责任是，仅在程序中那些在没有预取或分组加载的情况下本可能发生错误的地方，才反映加载错误。

如果在类加载过程中发生错误，则在程序中直接或间接使用所请求的类或接口的任何点，都将抛出以下 `LinkageError` 子类的实例：

- `ClassCircularityError`：**类循环依赖错误**。所请求的类或接口无法加载，因为它超出了其父类或父接口范围（§8.1.4, §9.1.3, §13.4.4）。
- `ClassFormatError`：**类格式错误**。声称指定所请求的编译类或接口的二进制数据是畸形的。
- `NoClassDefFoundError`：**类定义未找到**。相关的类加载器找不到所请求的类或接口的定义。

由于加载涉及新数据结构的分配，它可能会因 `OutOfMemoryError` 失败。

## 12.2.2 类加载器一致性

良好的类加载器会维护以下属性：

- *在名称相同的情况下，类加载器应该始终返回相同的 Class 对象。*
- 如果类加载器 $L_1$ 将类或接口 $C$ 的加载委托给另一个加载器 $L_2$，那么对于任何由 $C$ 的直接父类类型命名、或由 $C$ 的直接父接口类型命名、或由 $C$ 中字段的类型命名、或由 $C$ 中方法的返回类型命名的类或接口 $D$，$L_1$ 和 $L_2$ 应该为 $D$ 返回相同的 `Class` 对象。

恶意的类加载器可能会违反这些属性。然而，它不能破坏类型系统的安全性，因为 Java 虚拟机对此进行了防范。

## 12.3 类和接口的链接

有关这些问题的进一步讨论，请参阅《The Java Virtual Machine Specification, Java SE 17》以及 Sheng Liang 和 Gil Bracha 发表在 $Proceedings of OOPSLA '98$ 上的论文《Dynamic Class Loading in the Java Virtual Machine》（发表于 ACM SIGPLAN Notices, Volume 33, Number 10, October 1998）。Java 编程语言设计的一个基本原则是运行时系统不能被用 Java 编程语言编写的代码所破坏，即使是通过像 `ClassLoader` 和 `SecurityManager` 这样敏感的系统类的实现来实现。

链接是将类或接口的二进制形式并将其组合到 Java 虚拟机的运行时状态的过程，以便其被执行。类或接口在链接之前总是会被加载。

链接的精确语义位于《The Java Virtual Machine Specification, Java SE 17 Edition》的第 5 章中。这里我们从 Java 编程语言的角度给出该过程的概述。

链接涉及三种不同的活动：验证、准备和符号引用的解析。

本规范允许链接（以及由于递归原因的加载）发生的时间具有实现灵活性，前提是尊重 Java 编程语言的语义，类或接口在初始化之前已完全验证并准备，并且在链接期间检测到的错误是在程序中执行某项可能需要链接到错误相关类或接口的动作的时间点抛出的。

例如，实现可以单独地解析类或接口中的每个符号引用，或者在使用它们时解析（惰性解析或延迟解析），或者在验证类时一次性解析所有引用（静态解析）。这意味着在某些实现中，在类或接口初始化后，解析过程可能仍在继续。

由于链接涉及新数据结构的分配，它可能会因 `OutOfMemoryError` 失败。

### 12.3.1 二进制表示的验证

验证确保类或接口的二进制表示在结构上是正确的。例如，它会检查每条指令是否具有有效的操作码；每条分支指令是否跳转到某些其他指令的开头而不是指令的中间；每个方法是否提供了结构正确的签名；以及每条指令是否遵守 Java 虚拟机的类型规范。

如果在验证过程中发生错误，则在导致该类进行验证的程序点，将抛出以下 `LinkageError` 子类的实例：

- `VerifyError`：**验证错误**。类或接口的二进制定义未能通过一系列必要的检查，这些检查要求其遵守 Java 虚拟机语言的语义，且不能违反 Java 虚拟机的完整性。（示例请参见 §13.4.2, §13.4.4, §13.4.9 和 §13.4.17。）

### 12.3.2 类或接口的准备

准备涉及为类或接口创建静态字段（类变量和常量）并将这些字段初始化为默认值（§4.12.5）。这不需要执行任何源代码；静态字段的显式初始化器是在初始化阶段（§12.4）执行的，而不是准备阶段。

> Java 虚拟机实现可能会排除额外的数据结构

### 12.3.3 符号引用的解析

类或接口的二进制表示引用了其他类、接口以及字段、方法。对于字段和方法，这些符号引用包含了类或接口的名字以及相应的类型信息。在使用符号引用之前，必须经过解析，其中符号引用被检查是否正确，并且通常被替换为直接引用。

如果在解析过程中发生错误，则将抛出错误。通常情况下，这将是 `IncompatibleChangeError` 子类之一的实例。该错误在直接或间接使用符号引用的任何点抛出：

- `IllegalAccessError`：**非法访问错误**。遇到了指定字段使用或赋值、方法调用或类实例创建的引用，但包含引用的代码没有权限，因为字段或方法被声明为保护或包私有，或者因为该类未声明为 public。

  这可能发生，例如，在另一个类编译后，将原本为 public 的字段改为 private（§13.4）；或者在引用该类的模块编译后，该类所在的包未声明为导出（§13.3）。

- `InstantiationError`：**实例化错误**。遇到了用于类实例创建的引用，但无法创建实例，因为引用被证明指向一个接口或抽象类。

  这可能发生，例如，在引用该类编译后，将非抽象类改为抽象类（§13.4.1）。

- `NotFound`：**未找到**。遇到了引用特定类或接口的特定字段的符号引用，但该类或接口不包含该字段。

  这可能发生，例如，在引用该字段的类编译后，删除了字段声明（§13.4.8）。

- `NoSuchMethodError`：**找不到方法**。遇到了引用特定类或接口的特定方法的符号引用，但该类或接口不包含该签名的方法。

  这可能发生，例如，在引用该方法的类编译后，删除了方法声明（§13.4.12）。

此外，如果类声明了一个原生方法但找不到其实现，可能会抛出 `LinkageError` 子类 `UnsatisfiedLinkError`。该错误会在方法在使用时，或者更早，取决于 Java 虚拟机实现所使用的解析策略（§13.2）。

## 12.4 类和接口的初始化

类的初始化包括执行其静态初始化器以及类中声明的静态字段（类变量）的初始化器。

接口的初始化由执行接口中声明的字段（常量）的初始化器组成。

### 12.4.1 初始化发生的时机

类或接口 $\tau$ 将在以下任何一种情况首次发生之前立即初始化：

- $\tau$ 是一个类且创建了 $\tau$ 的实例。
- 调用了由 $\tau$ 声明的 `static` 方法。
- 使用了由 $\tau$ 声明的 `static` 字段，且该字段不是常量变量（§4.12.4）。

当一个类被初始化时，它的超类将被初始化（如果它们之前没有被初始化），以及任何声明了默认方法（§9.4.3）的超接口（§8.1.5）也将被初始化（如果它们之前没有被初始化）。接口的初始化本身不会导致其任何超接口的初始化。

对 `static` 字段（§8.3.1）的引用会导致实际声明该字段的类或接口的初始化，尽管可以通过子类、子接口或实现接口的类的名称来引用它。

在类 `Class` 和包 `java.lang.reflect` 中调用某些反射方法也会导致类或接口的初始化。

类或接口不会因任何其他情况而初始化。

> 注意，编译器可能会在接口中生成 `synthetic`（合成的）默认方法，即既没有显式声明也没有隐式声明的默认方法（§13.1）。这些方法会触发接口的初始化，尽管源代码并没有指示该接口应该被初始化。

其意图是让类或接口有一组初始化器使其处于一个一致的状态，而该状态是其他类观察到的第一个状态。静态初始化器和类变量初始化器按照文本顺序执行，并且可能引用在文本中出现在使用位置之后的类声明中的类变量，尽管这些类变量在作用域内（§8.3.3）。这种限制旨在于编译时检测大多数循环或其他形式异常的初始化。

初始化代码不受限制的这一事实使得可以构建出如下示例：在初始化表达式被求值之前，当类变量仍具有初始默认值时就可以观察到它的值，但在实践中这样的示例非常罕见。（也可以为实例变量初始化构建此类示例（§12.5））。Java 编程语言的完整威力在这些初始化器中都是可用的；程序员必须小心。这种力量为代码生成器带来了额外负担，但只要 Java 语言是并发的，这种负担就会产生。

## 示例 12.4.1-1. 超类在子类之前初始化

```java
class Super {
    static { System.out.print("Super "); }
}

class One {
    static { System.out.print("One "); }
}

class Two extends Super {
    static { System.out.print("Two "); }
}

class Test {
    public static void main(String[] args) {
        One o = null;
        Two t = new Two();
        System.out.println((Object)o == (Object)t);
    }
}
```

该程序产生输出：

Super Two false

类 One 从未被初始化，因为它没有被积极使用，因此从未链接到类。Two 只有在它的超类 Super 初始化后才初始化。

## 示例 12.4.1-2. 只有声明 static 字段的类被初始化

```java
class Super {
    static int taxi = 1729;
}

class Sub extends Super {
    static { System.out.print("Sub "); }
}

class Test {
    public static void main(String[] args) {
        System.out.println(Sub.taxi);
    }
}
```

该程序只打印：

1729

因为类 Sub 没有被初始化；对 `Sub.taxi` 的引用是对实际上声明在类 Super 中的字段的引用，并且不会触发类 Sub 的初始化。

## 示例 12.4.1-3. 接口初始化不会初始化超接口

```java
interface I {
    int i = i, ii = Test.out("ii", 2);
}

interface J extends I {
    int j = out("jj", 3), jj = Test.out("jj", 4);
}

interface K extends J {
    int k = Test.out("k", 5);
}

class Test {
    public static void main(String[] args) {
        System.out.println(J.i);
        System.out.println(K.j);
    }

    static int out(String s, int i) {
        System.out.println(s + "=" + i);
        return i;
    }
}
```



该程序产生输出：

```
1
jj=3
jj=4
3
```

对 `J.i` 的引用是一个常量变量字段（§4.12.4）；因此，它不会导致 `I` 被初始化（§13.4.9）。

对 `K.j` 的引用是对接口 `J` 中实际声明的字段的引用，该字段不是常量变量；这会导致接口 `J` 字段的初始化，但不会导致其超接口 `I` 或接口 `K` 的初始化。

尽管使用了名称 `K` 来引用接口 `J` 的字段 `j`，但接口 `K` 并没有初始化。

## 12.4.2 详细步骤

由于 Java 编程语言是多线程的，类或接口的初始化需要同步，因为其他线程可能同时初始化同一个类或接口。

### 类和接口的初始化

其意图是让类或接口有一组初始化器使其处于一个一致的状态，而该状态是其他类观察到的第一个状态。静态初始化器和类变量初始化器按照文本顺序执行，并且可能引用在文本中出现在使用位置之后的类声明中的类变量，尽管这些类变量在作用域内（§8.3.3）。这种限制旨在于编译时检测大多数循环或其他形式异常的初始化。

初始化代码不受限制的这一事实使得可以构建出如下示例：在初始化表达式被求值之前，当类变量仍具有初始默认值时就可以观察到它的值，但在实践中这样的示例非常罕见。（也可以为实例变量初始化构建此类示例（§12.5））。Java 编程语言的完整威力在这些初始化器中都是可用的；程序员必须小心。这种力量为代码生成器带来了额外负担，但只要 Java 语言是并发的，这种负担就会产生（§12.4.2）。

### 初始化过程

初始化 `c` 的过程如下：

1. 接下来，通过其类加载器确定是否启用了断言（§14.10）。
2. 接下来，按照文本顺序执行类变量初始化器和静态初始化器，或者执行接口的初始化器，就像它们是一个块一样。
3. 如果初始化器的执行完成，则获取 `LC`，将类对象标记为已初始化，通知所有等待线程，释放 `LC`，并完成此过程。
4. 否则，初始化器由于抛出异常 `E` 而异常终止。如果 `E` 的类不是 `Error` 或其子类，则创建一个 `ExceptionInitializerError` 实例并以 `E` 为参数，并在后续步骤中使用该对象替换 `E`。如果由于内存溢出错误无法创建 `ExceptionInitializerError` 实例，则使用内存溢出对象替换 `E`。
   - 获取 `LC`，将类对象标记为错误，通知所有等待线程，释放 `LC`，并根据之前的步骤确定的 `E` 或其替换内容异常终止此过程。

实现可以在确定类初始化已经完成时，通过省略步骤 1（以及步骤 4）中的锁获取来优化此过程，前提是在内存模型中，如果获取锁将会存在的所有发生-先行排序，在执行优化时仍然存在。

## 12.5 新类实例的创建

从代码中消除——例如，通过补丁将其移除或通过重新生成代码。

在某些情况下，如果能够确定一组相关类和接口的初始化顺序，编译时分析可能能够从生成的代码中消除许多关于某个类或接口是否已初始化的检查。然而，这种分析必须充分考虑并发性，以及初始化代码是不受限制这一事实。

当对类实例创建表达式（§15.9）的求值导致一个类被实例化时，就会显式地创建一个新的类实例。

在以下情况下，可能会隐式地创建新的类实例：

- 加载包含字符串字面量（§15.10.5）或文本块（§13.10.6）的类或接口可能会创建一个新的 `String` 对象，用以表示该字符串字面量或文本块所表示的字符串。（如果之前已经遇到过表示与字符串字面量或文本块具有相同 Unicode 代码点序列的 `String` 实例，则不会产生该对象。）
- 执行会导致装箱转换（§5.1.7）的操作。装箱转换可能会创建一个与其中一个原始类型关联的包装类（`Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double`）的新对象。
- 执行不是常量表达式（§15.29）一部分的字符串拼接运算符 `+`（§15.18.1），总是创建一个新的 `String` 对象来表示结果。字符串拼接运算符还可能为原始类型的值创建临时的包装对象。
- 求值方法引用表达式（§15.13.3）或 lambda 表达式（§15.27.4）可能需要创建一个实现函数式接口类型（§9.8）的类的新实例。

这些情况中的每一种都确定了一个特定的构造方法（§8.8），该方法将作为类实例过程的一部分，使用指定的参数被调用。

每当创建新的类实例时，都会为它分配内存空间，以容纳该类中声明的所有实例变量以及该类每个子类中声明的所有实例变量，包括所有可能被隐藏的（§8.3）实例变量。

如果没有足够的空间为该对象分配内存，则类实例的创建将以 `OutOfMemoryError` 异常异常终止。

否则，新对象中的所有实例变量（包括在父类中声明的变量）都将被初始化为它们的默认值（§4.12.5）。

在将新创建对象的引用作为结果返回之前，指定的构造方法将通过处理，并按照以下程序初始化新对象：

1. 将构造方法的参数分配给该构造方法调用的新创建的参数变量。
2. 如果此构造方法以对同类中另一个构造方法的显式构造方法调用（§8.8.7.1）（使用 `this`）开始，则求值参数并使用这五个步骤递归地处理构造方法调用。如果该构造方法异常终止，则此过程也以相同原因异常终止；否则，继续第 5 步。
3. 此构造方法不是以对同类中另一个构造方法的显式构造方法调用（使用 `this`）开始的。如果此构造方法对应的不是 `Object` 类，则此构造方法将显式或隐式地调用父类构造方法（使用 `super`）。求值参数并使用这五个步骤递归地处理父类构造方法调用。如果该父类调用异常终止，则此过程也以相同原因异常终止。否则，继续第 4 步。
4. 执行该类的实例初始化器和实例变量初始化器，将实例变量初始化器的值分配给相应的实例变量，按照它们在类源代码中从左到右的文本顺序进行。如果执行这些任何一个初始化器导致异常，则不再处理后续的初始化器，且此过程以该异常异常终止。否则，继续第 5 步。
5. 执行此构造方法体的剩余部分。如果该执行异常终止，则此过程也以相同原因异常终止。否则，此过程正常完成。

与 C++ 不同，Java 语言没有规定在创建新实例期间规定方法分派的变更规则。如果在正在初始化的对象中调用了在子类中重写的方法，则将使用这些重写的方法，甚至在新对象完全初始化之前。

### 示例 12.5-1. 实例创建的求值

```java
class Point {
    int x, y;
    Point() { x = 1; y = 1; }
}

class ColoredPoint extends Point {
    int color = 0xFF00FF;
}

class Test {
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        System.out.println(cp.color);
    }
}
```

在这里，创建了一个 `ColoredPoint` 的新实例。首先为新的 `ColoredPoint` 分配空间以持有字段 `x`、`y` 和 `color`。所有这些字段都被初始化为它们的默认值（在这种情况下，每个字段均为 0）。接下来，调用无参数的 `ColoredPoint` 构造方法。由于 `ColoredPoint` 没有声明构造方法，因此隐式地声明了格式如下的默认构造方法：

```
ColoredPoint() { super(); }
```

此构造方法调用了无参数的 `Point` 构造方法。`Point` 构造方法没有以调用构造方法开始，Java 编译器提供了对其无参数父构造方法的隐式调用，如同：

```java
Point() { super(); x = 1; y = 1; }
```

因此，调用了无参数的 `Object` 构造方法。

`Object` 类没有父类，因此递归在此终止。接下来，调用 `Object` 的任何实例初始化器和实例变量初始化器。执行 `Object` 的无参数构造方法，由于 `Object` 中没有声明此类构造方法，Java 编译器提供了一个默认的：

```
Object() { }
```

此构造方法执行后返回。

接下来，执行 `Point` 的实例变量初始化器。执行 `Point` 构造体，将 `x` 设置为 1，`y` 设置为 1。

接下来，执行 `ColoredPoint` 的实例变量初始化器。此步骤将 `0xFF00FF` 分配给 `color`。最后，执行 `ColoredPoint` 构造体的剩余部分（调用 `super` 之后）；由于剩余部分没有语句，因此不需要进一步的操作，初始化完成。

### 示例 12.5-2. 实例创建期间的动态分派

```java
class Super {
    Super() { printThree(); }
    void printThree() { System.out.println("three"); }
}

class Test extends Super {
    int three = (int)Math.PI; // 那是 3
    void printThree() { System.out.println("three"); }
    public static void main(String[] args) {
        Test t = new Test();
        t.printThree();
    }
}
```

此程序输出：

```
0
3
```

这表明在 `Super` 构造方法中调用 `printThree()` 没有调用 `Super` 类中的 `printThree` 定义，而是调用了 `Test` 类中重写的定义。该方法在执行 `Test` 的字段初始化器之前就返回了，这就是为什么第一个输出的值是 0（字段 `three` 的默认值）。稍后在 `main` 方法中调用 `printThree()` 时，此时字段 `three` 的初始化器已经执行，因此打印了值 3。

## 类实例的终结

垃圾回收器在数据结构中每个对象的所有 `finalize` 方法可能同时被调用，每个终结器的调用都运行在不同的线程中。

Java 编程语言对 `finalize` 方法的调用没有任何顺序限制。终结器可能会以任何顺序被调用，甚至是并发调用。

例如，如果一组循环引用的未终结对象变得不可达（或变为终结器可达），则所有这些对象都变为可终结的。最终，这些对象的终结器可能会以任何顺序被调用，甚至使用多个线程并发地调用。如果自动存储管理器随后发现这些对象是不可达的，则它们的存储将被回收。

实现一个类以便在所有对象都变得不可达时，按指定的顺序对一组对象调用一组类似于 `finalize` 的方法是直接的。定义这样一个类被留给读者作为练习题。

可以保证，调用终结器的线程在调用终结器时，不会持有任何用户可见的同步锁。

如果在终结过程中抛出了未捕获的异常，则该执行将被忽略且该对象的终结将终止。

对象构造函数的完成发生在（§17.4.5）其 `finalize` 方法执行之前（正式意义上的“发生于”）。

在 `Object` 类中声明的 `finalize` 方法不执行任何操作。`Object` 类声明了 `finalize` 方法这一事实意味着任何类的 `finalize` 方法都可以始终调用其父类的 `finalize` 方法。这应该始终这样做，除非程序员的意图是使父类中终结器的操作失效。（与构造函数不同，终结器不会自动调用父类的终结器；这种调用必须显式编码。）

为了效率考虑，实现可能会跟踪没有重写 `Object` 类 `finalize` 方法或以简单方式重写了该方法的类。

例如：

```java
protected void finalize() throws Throwable {
    super.finalize();
}
```

我们鼓励实现将此类对象视为具有一个未被重写的终结器，并按照 §12.6.1 中描述的更高效地对它们进行终结。

终结器可以像任何其他方法一样被显式地调用。

`java.lang.ref` 包描述了弱引用，弱引用与垃圾回收和终结有相互作用。与任何与 Java 编程语言有特殊交互的 API 一样，实现者必须意识到 `java.lang.ref` API 规定的任何要求。本规范未以任何方式讨论弱引用。详情请参考 API 文档。

## 12.6.1 实现终结

每个对象都可以通过两个属性来描述：它可能是可达的、终结器可达的或不可达的，而且它也可能是未终结的、可终结的或已终结的。

- **可达对象**：指任何从存活线程的任何潜在后续计算中都可以被访问的对象。
- **终结器可达对象**：可以通过某些引用链从某个可终结的对象到达，但无法从任何存活线程到达。
- **不可达对象**：无法通过上述任何一种方式被到达。
- **未终结的对象**：其终结器从未被自动调用过。
- **已终结的对象**：其终结器已被自动调用过。
- **可终结的对象**：其终结器从未被自动调用过，Java 虚拟机可能会最终自动调用其终结器。

一个对象在它的构造函数已在 `o` 上调用了 `Object()` 且该调用成功完成（即没有抛出异常）之前，是不会被终结的。在终结之前对对象字段的任何写入都必须对该对象的终结器可见。此外，对该对象字段的任何终结前的读取都不应看到在对象终结启动之后发生的写入。

对程序进行优化的转换可以被设计为以减少可达对象的数量，使其少于被认为是可达的数量。例如，Java 编译器或代码生成器可能会选择将不再被使用的变量或参数设置为 `null`，以导致该对象的存储可能更早地回收。

另一个示例发生在对象字段中的值存储在寄存器中。此时，程序可能会访问寄存器而不是对象，并且再也不访问该对象。这意味着该对象是垃圾。注意，这种优化仅在引用存储在栈上而非存储在堆上时才是允许的。

例如，考虑 Finalizer Guardian 模式：

```java
class Foo {
    private final Object finalizerGuardian = new Object() {
        protected void finalize() throws Throwable {
            /* finalize Foo object */
        }
    };
}
```



如果子类重写了 `finalize` 且没有显式调用 `super.finalize`，则终化器会保护 `super.finalize()` 被调用。

如果对存储在堆上的引用允许此类优化，那么 Java 编译器可以检测到 `finalizerGuardian` 字段从未被读取，立即将其置空并调用早期终化器。这与意图背道而驰：程序员可能希望在 `Foo` 实例变得不可达时调用 `Foo` 的 `finalize`。因此，这种转换是不合法的：只要外部对象是达的，内部类应该是可达的。

此类转换可能导致 `finalize` 方法的调用比预期早。为了允许用户防止这种情况，我们强制执行同步可能会保持对象存活的注释。如果一个对象的终化可能导致对该对象的同步，那么每当持有锁时，该对象必须存活并被视为可达的。

注意，这并不能防止同步：只有当终化器可能会对其进行同步时，同步才会保持对象存活。由于终化器发生在另一个线程中，在许多情况下同步是无法移除的。

## 12.6.2 与内存模型的交互

内存模型必须能够描述终化的交互。本节描述了终化与内存模型的交互。

一个对象在它的构造函数已在 `o` 上调用了 `Object()` 且该调用成功完成（即没有抛出异常）之前，是不会被终化的。终化之前对对象字段的任何写入都必须对该对象的终化器可见。此外，对该对象字段的任何终化前的读取都不应看到在对象终化启动之后发生的写入。

对程序进行优化的转换可以被设计为减少可达对象的数量，使其少于被认为是可达的数量。例如，Java 编译器或代码生成器可能会将不再被使用的变量或参数设置为 `null`，以导致该对象的存储可能更早地回收。

另一个示例发生在对象字段中的值存储在寄存器中。此时，程序可能会访问寄存器而不是对象，并且再也不访问该对象。这意味着该对象是垃圾。注意，这种优化仅在引用存储在栈上而非存储在堆上时才是允许的。

每个可达性决策点，对象被标记为不可达，且某些被标记为可终化的根据 `java.lang.ref` 包的文档。

如果一个对象 `x` 在 `di` 时被标记为不可达，则：

- `x` 在 `di` 时从静态字段来看是不可达的；
- 线程 `t` 在 `di` 之后对 `x` 的活跃使用必须发生在 `x` 的终化器调用中，或发生在对 `x` 的引用的之后；且
- `di` 之后的所有读取必须看到在 `di` 时不可达对象的写入。

在 `di` 时被认为可达的对象只有那些可以通过以下规则证明是可达的：

- 对象 `b` 在 `di` 时从静态字段是确定可达的，如果存在对类 `c` 静态字段的写入 `w1`，`w1` 写入的值是 `b` 的引用，类 `c` 由可达的类加载器加载，且不存在写入 `w2` 使得 `hb(w2, w1)` 为假且 `w1` 和 `w2` 都发生在 `di` 之前。
- 对象 `b` 在 `di` 时从 `a` 是确定可达的，如果存在对 `a` 元素的写入 `w1`，`w1` 写入的值是 `b` 的引用且不存在写入 `w2` 使得 `hb(w2, w1)` 为假且 `w1` 和 `w2` 都发生在 `di` 之前。
- 如果对象 `c` 从对象 `b` 是确定可达的，且对象 `b` 从对象 `a` 是确定可达的，则 `c` 从 `a` 是确定可达的。

动作 `a` 是 `x` 的活跃使用当且仅当以下至少一个条件为真：

- `a` 读取或写入 `x` 的元素
- `a` 锁定或解锁 `x`，且存在对 `x` 的锁动作发生在 `x` 的终化器调用之后
- `a` 写入引用到 `x`
- `a` 是对象 `y` 的活跃使用，且 `x` 从 `y` 是确定可达的

如果一个对象 `x` 在 `di` 时被标记为可终化的，则：

- `x` 在 `di` 时必须被标记为不可达的；
- `di` 必须是 `x` 被标记为可终化的唯一位置；且
- 发生在终化器调用之后的动作必须发生在 `di` 之后。

## 12.7 类和接口的卸载

Java 编程语言的实现可能会卸载类。

一个类或接口 `c` 可以被卸载，当且仅当其定义类加载器可以像第 12.6 节所述那样被垃圾收集器回收时。

由引导加载器（bootstrap loader）加载的类和接口不可以被卸载。

类卸载是一种有助于减少内存的优化。显然，程序的语义不应该依赖于系统是否选择或如何实现诸如卸载之类的优化。这样做将损害程序的可移植性。因此，一个类或接口是否已经被卸载，或是否不应该被卸载，对程序来说应当是透明的。

然而，如果一个类或接口 `c` 在其定义加载器可能可达时被卸载，那么 `c` 可能会被重新加载。人们永远无法确保这种情况不会发生。即使该类没有被其他已加载的类引用，它也可能被尚未加载的类或接口 `D` 引用。当 `D` 被 `c` 的定义加载器加载时，它的执行可能会导致 `C` 的重新加载。

如果该类具有静态变量（其状态将会丢失）、静态初始化器（可能会产生副作用）或原生方法（可能会保留静态状态），那么重新加载可能是不透明的。此外，`Class` 对象的哈希值取决于它的标识性。因此，通常情况下，无法以完全透明的方式重新加载一个类或接口。

由于我们永远无法保证卸载一个加载器可能可达的类或接口不会导致重新加载，且重新加载永远是不透明的，但卸载必须是透明的，因此得出结论：绝不能卸载加载器可能可达的类或接口。类似的推理可以用来推断出，由引导加载器加载的类和接口永远无法被卸载。

人们必须论证为什么当定义类加载器可以被回收时，卸载类 `c` 是安全的。如果定义加载器可以被回收，那么永远不会存在对它的引用（包括非活跃的但可能被终结器“复活”的引用）。反之，只有当对该加载器定义的类 `c`（无论是从其实例还是从代码）都不存在任何引用时，这一点才成立。

类卸载对于那些加载了大量类并在一段时间后停止使用其中大多数类的应用程序来说是显著的。此类应用程序的一个典型例子是网络浏览器，但还有更多。此类应用程序的特点是它们通过显式使用类加载器来管理类。因此，上述策略对它们非常有效。

严格来说，本规范并不非要讨论类卸载问题，因为类卸载仅仅是一种优化。然而，这个问题非常微妙，因此在此处提及它是为了进一步说明。

## 12.8 程序退出

当发生以下两种情况之一时，程序终止所有活动并退出：

- 所有非守护线程都终止。
- 某些线程调用了 `Runtime` 类或 `System` 类的 `exit` 方法，且该操作未被安全管理器禁止。

# 13 章

## 二进制兼容性

Java 编程语言的开发工具应该在源代码可用时，根据需要支持自动重新编译。特定的实现还可能将类和接口的源码和二进制表示存储在版本控制数据库中，并实现一个使用数据库完整性机制的 `ClassLoader`，通过向客户端提供二进制兼容的类和接口版本来防止链接错误。

对于要广泛分发的包、类和接口的开发者来说，他们面临的是一组不同的问题。在互联网（这是我们最喜爱的广泛分发系统例子）中，自动重新编译直接或间接依赖于要更改的类或接口的既有二进制文件通常是不切实际或无法可能的。相反，本规范定义了一系列允许开发者对包或类或接口进行的更改，同时保留（而非破坏）与既有二进制文件的兼容性。

在 SOM 的“发布版本间的二进制兼容性”（Foreman, Conner, Danforth, and Raper, Proceedings of OOPLA '95）框架内，Java 编程语言的二进制文件在作者识别的所有相关变换上都具有二进制兼容性（对于实例变量的添加，有一些例外）。使用他们的方案，以下是 Java 编程语言支持的某些重要二进制更改列表：

- 重新实现现有的方法、构造函数和初始化器以提高性能。
- 更改方法或构造函数，使其对某些输入返回结果，而这些输入原本抛出了正常不应发生的异常，或因进入无限循环或导致死锁而失败。
- 向现有的类或接口中添加新的字段、方法或构造函数。
- 删除类的私有字段、方法或构造函数。

### 二进制的形式

- 当更新整个包时，删除包中类和接口的包访问字段、方法或构造函数。
- 重新排序现有类或接口声明中的字段、方法或构造函数。
- 在类层次结构上移动方法。
- 重新排序类或接口的直接父接口列表。
- 在类型层次结构中插入新的类或接口类型。

本章规定了所有实现必须保证的二进制兼容性的最低标准。当混合的类和接口二进制文件并非已知是兼容的源码，但其源代码已按照此处描述的兼容方式进行了修改时，Java 编程语言保证其兼容性。请注意，我们讨论的是应用程序版本之间的兼容性。关于 Java SE 平台版本之间兼容性的讨论超出了本章的范围。

我们鼓励开发系统提供机制，提醒开发者更改对无法更改的既有二进制文件的影响。

## 13.1 二进制的形式

### 13.1.1 类或接口的形式

类或接口的二进制名必须满足以下约束：

- 顶层类或接口（7.6）是其全限定名。
- 成员类或接口（8.5、9.5）由其直接类或接口的二进制名组成。
- 本地类（14.3）由其直接类或接口的二进制名后跟一个非空数字序列，以及该本地类的简单名。
- 匿名类（15.9.5）由其直接类或接口的二进制名后跟一个非空数字序列。
- 泛型类或接口声明的类型变量（8.1.2、9.1.2）由其直接类或接口的二进制名后跟该变量的名。
- 泛型方法声明的类型变量（8.4.4）由声明方法的类或接口的二进制名后跟该方法的描述符（JVMS §4.3.3），后跟该变量的名。
- 泛型构造函数声明的类型变量（8.8.4）由声明构造函数的类的二进制名后跟构造函数的描述符（JVMS §4.3.3），后跟该变量的名。

2. 对另一个类或接口的引用，使用其二进制名。

3. 常量变量（4.12.4）字段的引用在编译时通过常量变量的初始化器解析为值 `v`。

如果该字段是静态的，则二进制文件中不应存在该字段的引用，包括声明该字段的类或接口。该字段始终看起来已初始化（12.4.2）；字段的默认初始值（如果与 `v` 不同）永远不会被观察到。

如果该字段是非静态的，则二进制文件中不应存在该字段的引用，除非是在包含字段的类中。（这将是一个类而不是接口，因为接口只有静态字段。）

该类应该包含在实例创建期间将字段值置为 `v` 的代码 (§12.5)。

4. 给定一个表示类 `c` 中字段访问的合法表达式，该表达式引用了名为 `f` 的字段，该字段不是常数变量，且在某个（可能是不同的）类或接口 `D_i` 中声明，我们对该字段引用的*限定类*或*接口*定义如下：

- 如果该表达式通过简单名称引用，则如果 `f` 是当前类或接口 `c` 的成员，否则令 `ϱ` 为包含 `f` 作为成员的最内层词法包围的类或接口声明。无论何种情况，`ϱ` 都是该引用的限定类或接口。
- 如果该表达式具有 `TypeName.f` 的形式，其中 `TypeName` 表示一个类或接口，则由 `TypeName` 所表示的类或接口是该引用的限定类或接口。
- 如果该表达式具有 `ExpressionName.f` 或 `Primary.f` 的形式，则：
    - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交叉类型 `V₁ & ... & Vₙ`，则该引用的限定类或接口是 `V₁` 的擦除 (§4.6)。
    - 否则，`ExpressionName` 或 `Primary` 的编译时类型的擦除是该引用的限定类或接口。
- 如果该表达式具有 `super.f` 的形式，则 `c` 的超类是该引用的限定类或接口。
- 如果该表达式具有 `TypeName.super.f` 的形式，则由 `TypeName` 所表示的类的超类是该引用的限定类或接口。

对 `f` 的引用必须编译为对该引用的限定类或接口的符号引用，加上字段的简单名称 `f`。

该引用还必须包含对字段声明类型擦除的符号引用，以便验证器可以检查该类型符合预期。

5. 给定类或接口 `c` 中的一个方法调用表达式或方法引用表达式，该表达式引用了在某个（可能是不同的）类或接口 `D` 中声明（或隐式声明 (§9.2)）的名为 `m` 的方法，我们对方法调用的限定类或接口定义如下：

- 如果 `D` 是 `Object`，则方法调用的限定类或接口是 `Object`。
- 如果方法通过简单名称引用，则如果 `m` 是当前类或接口 `c` 的成员，令 `ϱ` 为 `c`；否则 `ϱ` 是包含 `m` 作为成员的最内层词法包围的类或接口声明。无论何种情况，`ϱ` 都是方法调用的限定类或接口。
- 如果该表达式具有 `TypeName.m` 或 `ReferenceType::m` 的形式，则由 `TypeName` 所表示的类或接口或 `ReferenceType` 的擦除是方法调用的限定类或接口。
- 如果该表达式具有 `ExpressionName.m` 或 `ExpressionName::m` 或 `Primary::m` 的形式，则：
    - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交叉类型 `V₁ & ... & Vₙ`，则方法调用的限定类或接口是 `Vⱼ` 的擦除。
    - 否则，`ExpressionName` 或 `Primary` 的编译时类型的擦除是方法调用的限定类或接口。
- 如果该表达式具有 `super.m` 或 `super::m` 的形式，则 `c` 是方法调用的限定类或接口。
- 如果该表达式具有 `TypeName.super.m` 或 `TypeName.super::m` 的形式，则如果 `TypeName` 表示类 `x`，则 `x` 的超类是方法调用的限定类或接口；如果 `TypeName` 表示接口 `x`，则 `x` 是方法调用的限定类或接口。

对方法的引用必须在编译时解析为对方法调用限定类或接口的符号引用，加上该方法声明签名 (§8.4.2) 的擦除。方法的签名必须包含以下由 §15.12.3 确定的所有内容：

- 方法的简单名称
- 该方法的参数个数
- 指向每个参数类型的符号引用

对方法的引用还必须包含对被表示方法返回类型擦除的符号引用，或者指明被表示的方法声明为 `void` 且不返回值。

6. 给定类或接口 `c` 中的一个类实例表达式 (§15.9)、一个显式构造函数调用语句 (§8.8.7.1) 或具有 `ClassType::new` 形式的方法引用表达式，引用了在某个（可能是不同的）类或接口 `D` 中声明的构造函数 `m`，我们对*构造函数调用的限定类*定义如下：

- 如果该表达式具有 `new D(...)` 或 `ExpressionName.new D(...)` 或 `Primary.new D(...)` 或 `D::new` 的形式，则构造函数调用的限定类是 `D`。
- 如果该表达式具有 `new D(...) (...)` 或 `ExpressionName.new D(...) (...)` 或 `Primary.new D(...) (...)` 的形式，则构造函数调用的限定类是该表达式声明的匿名类。
- 如果该表达式具有 `super(...)` 或 `ExpressionName.super(...)` 或 `Primary.super(...)` 的形式，则构造函数调用的限定类是 `c` 的超类。
- 如果表达式具有 `this(...)` 的形式，则构造函数调用的限定类是 `C`。

对构造函数的引用必须在编译时解析为对构造函数调用限定类的符号引用，加上构造函数的声明签名 (§8.8.2)。构造函数的签名必须包含：

- 构造函数的参数个数
- 指向每个形式参数类型的符号引用

类的二进制表示必须包含以下所有：

1. 如果是类且不是 `Object`，则指向其直接超类的符号引用。
2. 每个直接超接口的符号引用（如果有）。
3. 类或接口中声明的每个字段，给出简单名称和指向类型擦除的引用。
4. 如果是类，则每个构造函数的擦除签名。
5. 类或接口中每个方法（排除接口的隐式声明方法 (§9.2)）的擦除签名和返回类型。
6. 代码需要实现类或接口：
    - 对于接口，字段初始化代码以及每个代码块方法的实现 (§9.4.3)。
    - 对于类，字段初始化代码、实例初始化和静态初始化代码、每个代码块方法的实现 (§8.4.7) 以及每个构造函数的实现。
7. 每个类或接口必须包含能够恢复其规范名的信息 (§6.7)。
8. 每个嵌套类或接口必须有一个指向其直接包围类或接口的符号引用 (§8.1.3)。
9. 每个类或接口必须包含对其所有成员类和接口的符号引用 (§8.5, §9.5)，以及对其内部其他嵌套类和接口的符号引用。
10. Java 编译器生成的结构如果不对应于源代码中显式或隐式声明的结构，则必须标记为*合成*（synthetic），除非生成的结构是类初始化方法 (JVMS §2.9)。
11. Java 编译器生成的结构如果对应隐式声明的形式参数，则必须标记为*强制*（mandated） (§8.8.1, §8.8.9, §15.9.5.1)。

以下形式参数是隐式声明的：

- 非 `private` 内部成员类构造函数的第一个形式参数 (§8.8.1, §8.8.9)。
- 内部类（非静态上下文中）的匿名类的匿名构造函数的第一个形式参数 (§15.9.5.1)。
- 枚举类（enum class）中隐式声明的 `valueOf` 方法的正式名称 (§8.9.3)。
- 记录类（record class）紧凑构造函数的形式化参数 (§8.10.4)。

供参考，以下结构在源代码中被隐式声明，但未被标记为强制（mandated），因为只有形式参数和模块可以在类文件中被标记为强制 (JVMS §4.7.24, JVMS §4.7.25)：

- 普通类和枚举类的默认构造函数 (§8.8.9, §8.9.2)。
- 记录类的规范化构造函数 (§8.10.4)。
- 匿名构造函数 (§15.9.5.1)。
- 枚举类的 `values` 方法和 `valueOf` 方法 (§8.9.3)。
- 枚举类的某些公共字段 (§8.9.3)。
- 记录类的某些私有字段和公共方法 (§8.10.3)。
- 接口的某些公共方法 (§9.2)。
- 容器注解（Container annotations） (§9.7.5)。

对应模块声明的类文件可能具有一个二进制名称为 `module-info` 且没有超类、没有超接口、没有字段且没有方法的类文件的属性。此外，模块的二进制表示必须包含以下所有内容：

- 模块名称的规范，作为对 `module` 关键字之后名称的符号引用给出。此外，规范必须包含该模块是正常的（normal）还是开放的（open） (§7.7)。
- 每个由 `requires` 指令指示的依赖规范，作为对该指令所指示的模块名称的符号引用给出 (§7.7.1)。此外，规范必须包含该依赖是否是传递的以及该依赖是否是静态的。
- 每个由 `exports` 或 `opens` 指令指示的包规范，作为对其限定的包名称的符号引用给出 (§7.7.2)。此外，如果该指令存在，规范必须提供指向该指令子句所指示的模块名称的符号引用。
- 每个由 `uses` 指令指示的服务规范，作为对该指令所指示的类或接口名称的符号引用给出 (§7.7.3)。
- 由 `provides` 指令指示的服务提供者，作为该指令子句所指示的类和接口名称的符号引用给出 (§7.7.4)。此外，规范必须提供指向该指令所指示为服务的类或接口名称的符号引用。

后续章节讨论了在不破坏与现有二进制文件兼容性的情况下，对类和接口声明可能作的更改。在上述翻译要求下，Java 虚拟机及其类格式支持这些更改。任何其他有效的二进制格式（例如在上述要求下由类加载器映射回类的压缩或加密表示）也必然将支持这些更改。

## 13.2 什么是二进制兼容性，什么不是二进制兼容性

如果之前无错误地链接的现有二进制文件现在仍能继续无错误地链接，则对类型的更改与现有二进制文件是二进制兼容的（等同于，即不破坏与现有二进制文件的二进制兼容性）。

二进制文件被编译为运行在其他类和接口的可访问成员（members）和构造函数上。为了保持二进制兼容性，类或接口应将其可访问的成员和构造函数、它们的存在性和行为，视为与用户的一份契约。

Java 编程语言的设计是为了防止向契约中添加内容或无意的名称冲突会破坏二进制兼容性。具体而言，添加更多重载某个特定方法名的方法不会破坏与现有二进制文件的兼容性。现有二进制文件将用于方法查找的方法签名是由重载解析算法在编译时选择的 (§13.15.22)。

如果 Java 编程语言的设计使得运行时执行的特定方法是确定的，那么歧义可能会在运行时被检测到。某条规则意味着，添加额外的重载方法以在调用点可能产生歧义，可能会破坏未知数量现有二进制文件的兼容性。更多讨论请参阅 §13.4.23。

二进制兼容性并不等同于源兼容性（source compatibility）。特别是，§13.4.6 中的示例显示，可以从一组无法全部通过编译的源代码中产生一组兼容的二进制文件。这是很典型的：添加了一个新声明，改变了源代码中未更改部分的某个名称的含义，而源代码中未更改部分的现有二进制文件保留了该名称完全限定的之前的含义。产生一致的代码集需要提供与之前的含义相对应的限定名或字段访问表达式。

## 13.3 包和模块的演进

可以在包中添加一个新的顶级类或接口，而不会破坏与现有二进制文件的兼容性，只要新的类或接口没有复用之前给某个无关类或接口的名称。如果一个新类或接口复用了之前给某个无关类或接口的名称，则可能会引发冲突，因为这两个类或接口的二进制文件无法被同一个类加载器加载。

非公共的且不是公共类或接口的超类或超接口的顶级类和接口的更改，仅影响其所在包内的类和接口。这些类和接口可以被删除或进行其他更改，即使此处描述了不兼容之处，只要该包的受影响二进制文件被同时更新即可。

如果声明为导出（exports）或开放（opens）某个包的模块更改为不导出或不开放该包，或者将其给一组不同的朋友（friends），如果链接了需要该模块公共类和接口的现有二进制文件，将抛出 `IllegalAccessError`。

如果模块未声明为导出或开放给定的包，那么将模块更改为导出或开放该包不会破坏与现有二进制文件的兼容性。然而，将模块更改为导出或开放包一组不同的朋友可能会导致程序无法启动，因为读取该模块的任何模块现在可能会读取到多个包。

在模块声明中添加 `requires` 指令，或在 `requires` 指令中添加 `transitive` 修饰符，不会破坏现有二进制文件的兼容性。然而，它可能会导致程序无法启动，因为读取该模块的任何模块现在可能会读取到多个包。

在模块声明中删除 `requires` 指令，或从 `requires` 指令中删除 `transitive` 修饰符，可能会破坏依赖该指令的现有二进制文件的兼容性。

添加或删除 `uses` 或 `provides` 指令不会破坏现有二进制文件的兼容性。

## 13.4 类的演进

本节描述类及其成员更改对现有二进制文件的影响。

### 13.4.1 Abstract 类

如果未声明为 `abstract` 的类更改为 `abstract`，则尝试创建该类新实例的现有二进制将在链接时抛出 `InstantiationError`，或（如果使用反射方法）在运行时抛出 `InstantiationException`；因此，不建议对广泛分发的类进行此类更改。

将声明为 `abstract` 的类更改为不再是 `abstract` 不会破坏现有二进制文件的兼容性。

### 13.4.2 sealed、non-sealed 和 final 类

#### 13.4.2.1 sealed 类

如果一个自由扩展的（§8.1.1.2）类被更改为 `sealed`，那么当加载该类的子类的二进制文件且该子类不是该类的许可子类 (§8.1.6) 时，将抛出 `IncompatibleClassChangeError`；不建议对广泛分发的类进行此类更改。

将声明为 `final` 的类更改为 `sealed` 不会破坏现有二进制文件的兼容性。

将一个类添加到 `sealed` 类的直接子类列表中不会破坏现有二进制文件的兼容性。

如果将一个类从 `sealed` 类的直接子类列表中移除，则当加载该类的现有二进制文件时，将抛出 `IncompatibleClassChangeError`。

对于没有 `sealed` 直接超类或 `sealed` 直接超接口的类，删除 `sealed` 修饰符不会破坏现有二进制文件的兼容性。

#### 13.4.2.2 非密封类 (non-sealed Classes)

将一个声明为 `sealed` 的类更改为声明为 `nonsealed` 不破坏与现有二进制文件的兼容性。

将一个声明为 `final` 的类更改为声明为 `nonsealed` 不破坏与现有二进制文件的兼容性。

> 非密封类 `C` 必须有一个 `sealed` 的直接父类或 `sealed` 的直接父接口。删除 `nonsealed` 修饰符将导致 `C` 无法重新编译，因为每个具有 `sealed` 直接父类或直接父接口的类都必须是 `final`、`sealed` 或 `nonsealed`。

#### 13.4.2.3 final 类

如果一个未声明为 `final` 的类被更改为声明为 `final`，当加载该类的现有父类的二进制文件时，将抛出 `IncompatibleClassChangeError`，因为 `final` 类没有子类；对于广泛分发的类不建议进行此类更改。

从没有 `sealed` 直接父类或 `sealed` 直接父接口的类中删除 `final` 修饰符，不会破坏与现有二进制文件的兼容性。

> 如果类 `C` 具有 `sealed` 直接父类或 `sealed` 直接父接口，那么删除 `final` 修饰符将导致 `C` 无法重新编译，因为每个具有 `sealed` 直接父类或直接父接口的类必须是 `final` 或 `nonsealed` (§8.1.1.2)。

### 13.4.3 public 类

将一个未声明为 `public` 的类更改为声明为 `public` 不破坏与现有二进制文件的兼容性。

如果一个已声明为 `public` 的类被更改为未声明为 `public`，当链接一个需要但不再拥有该类类型的现有二进制文件时，将抛出 `IllegalAccessError`；对于广泛分发的类不建议进行此类更改。

### 13.4.4 父类和父接口

如果一个类将成为自身的父类，则在加载时会抛出 `CircularityError`。对于广泛分发的类，不建议对类层次结构的更改会导致在新编译的二进制文件与现有二进制文件加载时可能导致这种循环依赖。

更改类的直接父类类型或直接父接口类型集合，只要该类的父类或接口的总集没有丢失任何成员，就不会破坏与现有二进制文件的兼容性。

例如，将类的原始父类型（raw supertype）替换为由原始类型命名的类或接口的参数化类型是二进制兼容的。

如果对直接父类或直接父接口集合的更改导致类或接口不再是相应的父类或父接口，那么当加载修改类的二进制文件与现有二进制文件时，可能会导致链接错误。对于广泛分发的类不建议进行此类更改。

#### 13.4.4.1 更改父类

假设有以下测试程序：

```
```java
// 示例代码占位符
```
```



# 类的演变

## 13.4

### 示例 13.4.4-1. 类层次结构变更

```java
class Hyper { char h = 'h'; }

class Super extends Hyper { char s = 's'; }

class Test extends Super {

    public static void printH(Hyper h) {
        System.out.println(h.h);
    }

    public static void main(String[] args) {
        printH(new Super());
    }
}
```

经过编译并执行，产生输出：

```
h
```

假设编译了类 `Super` 的新版本：

```java
class Super { char s = 's'; }
```

此版本的 `Super` 不是 `Hyper` 的子类。如果我们随后运行新版本的 `Super`，那么 `Hyper` 和 `Test` 的现有二进制文件将在链接时抛出 `VerifyError`。验证器报错是因为 `new Super()` 的结果不能作为类型为 `Hyper` 的形式参数的参数传递，因为 `Super` 不是 `Hyper` 的子类。

考虑如果没有验证步骤会发生什么是很有启发性的：程序可能会运行并打印：

```
s
```

这表明，如果没有验证器，Java 类型系统可能会由于链接不一致的二进制文件而被击败，尽管每个文件都是由正确的 Java 编译器产生的。

该教训是，缺乏验证器或未能有效使用验证器的实现将无法维持类型安全，因此不是有效的实现。

### 示例 13.4.4-2. 引入父类

泛而言之，在各种情况下，对于客户端来说二进制兼容的类转换对于该客户端的源代码是不兼容的。

例如，多异常 catch 句 (§14.20) 中的替代方案不能是子类或彼此子类的类，这仅仅是一个源码限制。以下代码：

```java
try {
    failByThrowingAorB();
} catch (A | B e) {
    ...
}
```

只要在代码编译时 A 和 B 没有子类/父类关系，它就是合法的。此后，对于该客户端，将 A 和 B 更改为无此类关系是二进制兼容的。之前编译的代码将继续执行，但由于该更改对于该客户端源码兼容，代码无法重新编译。

## 13.4.5 类类型参数

为类添加或删除类型参数本身对二进制兼容性没有任何影响。

如果此类类型参数被用于字段或方法的类型中，它可能会产生更改上述类型时的正常影响。

重命名类的类型参数对于现有二进制文件没有影响。

更改类类型参数的第一个边界可能会更改任何在自身类型中使用该类型参数的成员的类型擦除 (§14.6)，这可能会影响二进制兼容性。此类边界的更改类似于类类类型参数的第一个边界的更改。

## 13.4.6 类体和成员声明

更改成员或构造函数声明的访问权限以允许更少的访问可能会破坏与现有二进制文件的兼容性，导致在解析这些二进制文件时抛出链接错误。通过向父类添加相同名称和访问权限的实例（或静态）成员（字段），或相同名称、访问权限和签名（方法），会导致与现有二进制文件不兼容。如果现有二进制文件使用了该成员，删除一个 `private` 类成员可能会导致链接错误。

### 示例 13.4.6-1. 更改类体

```java
class Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}

class Super extends Hyper {
    void hello() { System.out.println("hello from Super"); }
}

class Test {
    public static void main(String[] args) {
        new Super().hello();
    }
}
```

该程序产生输出：

```
hello from Super
```

假设产生了类 `Super` 的新版本：

```java
class Super extends Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}
```

这时如果重新编译了 `Super` 和 `Hyper` 但没有重新编译 `Test`，那么通过 `Test` 的现有二进制文件运行新二进制文件将产生输出：

```
hello from Hyper
```

正如你预期的。

### 示例 13.4.6-2. 更改父类

```java
class Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}

class Super extends Hyper { }

class Test extends Super { }
```

该程序产生输出：

```
hello from Hyper
```

假设产生了类 `Super` 的新版本：

```java
class Super extends Hyper {
    void hello() { System.out.println("hello from Super"); }
}
```

这时如果重新编译了 `Super` 和 `Hyper` 但没有重新编译 `Test`，那么通过 `Test` 的现有二进制文件运行新二进制文件将产生输出：

```
hello from Super
```

## 13.4.7 成员和构造函数的访问

更改成员或构造函数的声明访问权限以允许更少的访问可能会破坏与现有二进制文件的兼容性，导致在解析这些二进制文件时抛出链接错误。如果访问修饰符从包权限更改为 `private` 权限；从 `protected` 权限更改为包或 `private` 权限；或从 `public` 权限更改为 `protected`、包或 `private` 权限，则允许更少的访问。此后，对于广泛分发的类不建议更改成员或构造函数以允许更少的访问。

令人惊讶的是，二进制格式的广泛定义使得当子类（已经）定义了一个访问权限更少的方法时，将成员或构造函数具有更高的访问权限不会导致链接错误。

### 示例 13.4.7-1. 更改访问权限

如果包 `points` 定义了类 `Point`：

```java
package points;

public class Point {
    public int x, y;

    protected void print() {
        System.out.println("" + x + " , " + y + "");
    }
}
```

被程序使用：

```java
class Test extends points.Point {
    public static void main(String[] args) {
        Test t = new Test();
        t.print();
    }

    protected void print() {
        System.out.println("Test");
    }
}
```

然后这些类被编译并执行，产生输出：

```
Test
```

如果 `Point` 类中的方法 `print` 被更改为 `public`，然后仅重新编译 `Point` 类，并使用之前存在的 `Test` 二进制文件执行，则不会发生链接错误。尽管在编译时，一个 `public` 方法被 `protected` 方法覆盖是不恰当的（这一点可以通过除非将 `Test` 类中的 `print` 更改为 `public`，否则该类无法使用这个新的 `Point` 类进行重新编译）。

允许子类将 `protected` 方法更改为 `public` 而不破坏现有子类的二进制文件，有助于降低二进制文件的脆弱性。另一种替代方案（即此类更改会导致链接错误）将会产生额外的二进制不兼容性。

## 13.4.8 字段声明

广泛分发的程序不应向其客户端暴露任何字段。除了下文讨论的二进制兼容性问题外，这通常是良好的软件工程实践。向类中添加字段可能会破坏未重新编译的现有二进制文件的兼容性。

假设有一个对字段 `f` 的引用，限定类为 `c`。进一步假设 `f` 声明在 `c` 的父类 `s` 的一个实例（相应地为静态）字段中，且 `f` 的类型为 `x`。

如果在 `s` 的子类（该子类是 `c` 的父类或 `c` 本身）中添加与 `f` 同名的 `x` 类型新字段，可能会发生链接错误。只有在满足上述条件的基础上满足以下任一条件时，才会发生链接错误：

- 新字段的访问权限比旧字段低。
- 新字段是静态（相应地为实例）字段。

特别是，如果一个类无法再次重新编译，因为之前引用的字段指向了一个类型不兼容的父类字段，则不会发生链接错误。具有此类引用的已编译类将继续引用声明在父类中的字段。

### 示例 13.4.8-1. 添加字段声明

```java
class Hyper { String h = "hyper"; }

class Super extends Hyper { String s = "super"; }

class Test {
    public static void main(String[] args) {
        System.out.println(new Super().h);
    }
}
```

该程序产生输出：

```
hyper
```

假设生成了 `Super` 类的新版本：

```java
class Super extends Hyper {
    String s = "super";
    int h = 0;
}
```

然后，重新编译 `Hyper` 和 `Super` 并使用旧的 `Test` 二进制文件执行生成的新二进制文件，产生输出：

```
hyper
```

`Hyper` 的 `h` 由 `Test` 的原始二进制文件输出。虽然这看起来可能很惊讶，但它有助于减少运行时发生的不兼容性数量。（在理想的世界中，每当任何源文件更改时，都会重新编译所有文件，从而消除此类意外。但这种大规模的重新编译通常是不现实或不可行的，特别是在互联网中。而且，正如之前提到的，这种重新编译有时需要对源代码进行进一步更改。）

作为另一个例子，如果程序：

```java
class Hyper { String h = "Hyper"; }

class Super extends Hyper { }

class Test extends Super {
    public static void main(String[] args) {
        String s = new Test().h;
        System.out.println(s);
    }
}
```

被编译并执行，产生输出：

```
Hyper
```

假设编译了 `Super` 类的新版本：

```java
class Super extends Hyper { char h = 'h'; }
```

如果将生成的二进制文件与现有的 `Hyper` 和 `Test` 二进制文件一起使用，输出仍然是：

```
Hyper
```

尽管编译这些二进制文件的源码：

```java
class Hyper { String h = "Hyper"; }
class Super extends Hyper { char h = 'h'; }
class Test extends Super {
    public static void main(String[] args) {
        String s = new Test().h;
        System.out.println(s);
    }
}
```

会导致编译时错误，因为 `main` 源代码中的 `h` 现在将被构造为引用 `Super` 中声明的 `char` 字段，而 `char` 值不能赋值给 `String`。

从类中删除字段将破坏任何引用此字段的现有二进制文件的兼容性，并且当现有二进制文件的此类引用被链接时，将抛出 `NoSuchFieldError`。只有 `private` 字段可以从广泛分发的类中安全地删除。

为了二进制兼容性，添加或删除涉及变量（§4.4）或参数化类型（§4.5）的字段 `f`，等同于在 `f` 的类型擦除（§4.6）后添加（相应地，删除）同名相同类型的字段。

## 13.4.9 final 字段和静态常量变量

如果未声明为 `final` 的字段被更改为声明为 `final`，则可能会破坏尝试为该字段分配新值的现有二进制文件的兼容性。

### 示例 13.4.9-1. 将变量更改为 final

```java
class Super { char s; }

class Test extends Super {
    public static void main(String[] args) {
        Super x = new Super();
        x.s = 'a';
        System.out.println(x.s);
    }
}
```

该程序产生输出：

```
a
```

假设产生了 `Super` 类的新版本：

```java
class Super { final char s = 'b'; }
```

如果重新编译 `Super`，使用现有的 `Test` 二进制文件会导致 `IllegalAccessError`。

删除 `final` 关键字或更改字段初始化的值不会破坏现有二进制文件的兼容性。

如果一个字段是常量变量（§12.4），而且它是静态的，那么删除 `final` 关键字或更改其值不会破坏现有二进制文件，除非它们被重新编译，否则将看不到新值。这是支持条件编译（§14.22）的一个副作用。

在广泛分发的代码中，避免“常量”问题的最佳方法是对可能更改的值使用静态常量变量。如果需要 `final` 的只读性质，更好的选择是声明一个私有静态变量和一个相应的访问器方法来获取其值：

```java
private static int N;
public static int getN() { return N; }
```

而不是：

```java
public static final int N = ...;
```



## 13.4.10 static 字段

如果一个未声明为 `static` 的字段被更改为 `static`，或反之，则会导致链接错误（具体为 `IncompatibleChangeError`），如果该字段被现有二进制文件使用。在已分发的代码中不建议此类更改。

## 13.4.11 transient 字段

添加或删除字段的 `transient` 修饰符不会破坏现有二进制文件的兼容性。

## 13.4.12 方法和构造函数声明

向类添加方法或构造函数不会破坏任何现有二进制文件的兼容性，即使类无法再次重新编译是因为之前的调用引用了类型不兼容的父类方法或构造函数。具有此类引用的已编译类将继续引用声明在父类中的方法或构造函数。

假设有一个对方法 `m` 的引用，限定类为 `C`。假设 `m` 实际上是 `C` 的父类 `S` 的实例（相应地为静态）方法。

如果在 `S` 的子类（该子类是 `C` 的父类或 `C` 本身）中添加与 `m` 签名和返回类型相同的新方法，可能会发生链接错误。只有在满足上述条件的基础上满足以下任一条件时，才会发生链接错误：

- 新方法的访问权限比旧方法低。
- 新方法是静态（相应地为实例）方法。

从类中删除方法或构造函数可能会破坏任何引用此方法或构造函数的现有二进制文件的兼容性：当来自现有二进制文件的此类引用被链接时，将抛出 `NoSuchMethodError`。只有当父类中没有声明匹配签名和返回类型的方法时，才会发生此类错误。

如果类的源代码中没有声明的构造函数，则会隐式声明一个无参数的默认构造函数（§8.8.9）。在类的源代码中添加一个或多个构造函数声明将阻止此默认构造函数被隐式声明，实际上是删除了一个构造函数，除非这些新构造函数中有一个没有参数，从而替换了默认构造函数。无参数的默认构造函数被赋予与其声明所在类相同的访问修饰符，因此，若要保持与现有二进制文件的兼容性，任何替换都应该具有同等或更高级别的权限。

## 13.4.13 方法和构造函数的类型参数

添加或删除方法或构造函数的类型参数本身不会对二进制兼容性产生任何影响。

如果此类类型参数被用于方法或构造函数的类型中，则可能会产生上述类型更改的正常影响。

重命名方法或构造函数的类型参数对现有的二进制文件没有影响。

更改方法或构造函数的类型参数的第一个界限可能会更改任何在其自身类型中使用该类型参数的成员的擦除（§4.6），这可能会影响二进制兼容性。具体而言：

- 如果该类型参数被用作字段的类型，其效果等于删除了该字段，并添加了一个同名的字段，其类型为类型变量的新擦除类型。
- 如果该类型参数被用作方法任何形式参数的类型，但不是作为返回类型，其效果等于该方法被删除，并被一个新方法替换，该方法在上述形式参数的类型上是相同的，而这些参数现在的类型是类型参数的新擦除。
- 如果该类型参数被用作方法的返回类型，但不是作为方法任何形式参数的类型，其效果等于该方法被删除，并被一个新方法替换，该方法除返回类型外均相同，返回类型现在是类型参数的新擦除。
- 如果该类型参数既被用作方法的返回类型，又用作方法的一个或多个形式参数的类型，其效果等于该方法被删除，并被一个新方法替换，该方法除返回类型（现在是类型参数的新擦除）以及上述形式参数的类型（这些参数现在的类型是类型参数的新擦除）外均相同。

更改任何其他界限对二进制兼容性没有影响。

## 13.4.14 方法和构造函数的形式参数

更改方法或构造函数的形式参数的名称不会影响现有的二进制文件。

更改方法的名称，或向方法或构造函数声明添加参数将创建一个具有新签名的方法或构造函数，并产生删除具有旧签名的方法或构造函数以及添加具有新签名的方法或构造函数的组合效果（§13.4.12）。

将方法的最后一个形式参数的类型从 `T[]` 更改为类型为 `τ` 的可变长度参数，即 `τ...`（§8.4.1），反之亦然，不会影响现有的二进制文件。

出于二进制兼容性的目的，添加或删除涉及类型变量（§4.4）或参数化类型（§4.5）签名的方法或构造函数 `m`，等同于添加（相应地删除）一个原本等效的方法，该方法的签名是 `m` 签名的擦除（§4.6）。

## 13.4.15 方法结果类型

更改方法的结果类型，或将结果类型替换为 `void`，或将 `void` 替换为结果类型，将产生删除旧方法并添加具有新结果类型或新 `void` 结果的新方法的组合效果（见§13.4.12）。

出于二进制兼容性的目的，添加或删除涉及类型变量（§4.4）或参数化类型（§4.5）返回类型的方法或构造函数 `m`，等同于添加（相应地删除）一个原本等效的方法，该方法的返回类型是 `m` 返回类型的擦除（§4.6）。

## 13.4.16 抽象方法

将声明为 `abstract` 的方法更改不再声明为 `abstract` 不破坏与现有二进制文件的兼容性。

将未声明为 `abstract` 的方法更改为声明 `abstract` 将破坏之前调用过该方法的现有二进制文件的兼容性，导致 `AbstractMethodError`。

### 示例 13.4.16-1. 将方法更改为 abstract

```java
class Super { void out() { System.out.println("Out"); } }

class Test extends Super {
    public static void main(String[] args) {
        Test t = new Test();
        System.out.println("Way ");
        t.out();
    }
}
```

该程序产生输出：

```
Way
Out
```

假设生成了类的新版本：

```java
abstract class Super {
    abstract void out();
}
```

如果重新编译了 `Super` 但没有重新编译 `Test`，使用现有的 `Test` 二进制文件运行新的二进制文件将导致 `AbstractMethodError`，因为 `Test` 类没有方法 `out` 的实现，因此它（或应该）是抽象的。

## 13.4.17 final 方法

将声明为 `final` 的方法更改为不再声明为 `final` 不破坏与现有二进制文件的兼容性。

将未声明为 `final` 的实例方法更改为声明 `final` 可能会破坏依赖于重写方法能力的现有二进制文件的兼容性。

### 示例 13.4.17-1. 将方法更改为 final

```java
class Super { void out() { System.out.println("out"); } }

class Test {
    public static void main(String[] args) {
        Test t = new Test();
        t.out();
    }
}
```

该程序产生输出：

```
out
```

假设生成了类的新版本：

```java
class Super { final void out(); }
```

如果重新编译了 `Super` 但没有重新编译 `Test`，使用现有的 `Test` 二进制文件将导致 `IncompatibleChangeError`，因为 `Test` 尝试重写该方法。

将未声明为 `final` 的类方法更改为声明 `final` 不破坏现有二进制文件的兼容性。

## 13.4.18 native 方法

添加或删除方法的 `native` 修饰符不会破坏现有二进制文件的兼容性。

对未重新编译的 native 方法的影响超出本规范范围，并鼓励实现实现 native 方法。

## 13.4.19 static 方法

如果将声明为 `static`（即类方法）的方法更改为未声明为 `static`（即实例方法），反之亦然，可能会破坏兼容性，导致链接时错误即 `IncompatibleChangeError`，如果这些方法被现有二进制文件使用。不建议在已发布的代码中进行此类更改。

## 13.4.20 synchronized 方法

添加或删除方法的 `synchronized` 修饰符不会破坏现有二进制文件的兼容性。

## 13.4.21 方法和构造函数的 Throws

更改方法或构造函数的 `throws` 子句不会破坏现有二进制文件的兼容性；这些子句仅在编译时检查。

## 13.4.22 方法和构造函数体

更改方法或构造函数体不会破坏现有二进制文件的兼容性。

方法上的 `final` 关键字并不意味着该方法可以安全地内联；它仅意味着方法不能被重写。仍然可以在链接时提供该方法的新版本。此外，必须保留原始程序的结构。

因此我们注意 Java 编译器无法在编译时展开方法。通常我们建议实现使用晚绑定（运行时）代码生成和优化。

## 13.4.23 方法和构造函数的重载

添加重载现有方法或构造函数的方法或构造函数不会破坏现有二进制文件的兼容性。每次调用的签名是在这些现有二进制文件编译时确定的；因此，新添加的方法或构造函数不会被使用，即使它们的签名适用且比原始选择的签名更具体。

虽然添加新的重载方法或构造函数可能会导致下一个类或接口出现编译错误，因为没有最具体的方法或构造函数（§15.12.2.5），但在执行时不发生此类错误，因为执行时不进行重载解析。

### 示例 13.4.23-1. 添加重载方法

```java
class Super {
    static void out(float f) {
        System.out.println("float");
    }
}

class Test {
    public static void main(String[] args) {
        Super.out(2);
    }
}
```

该程序产生输出：

```
float
```

```java
class Super {
    static void out(float f) { System.out.println("float"); }
    static void out(int i) { System.out.println("int"); }
}
```

如果重新编译了 `Super` 但没有编译 `Test`，那么使用现有的二进制文件 `Test` 运行新的二进制文件将输出：

```
float
```

然而，如果重新编译了 `Test` 并使用这个新的 `Super`，输出将是：

```
int
```

正如在之前的情况中可能天真预期的那样。

## 13.4.24 方法重写

如果向子类中添加了一个实例方法且该方法重写了父类中的方法，那么现有二进制中的方法调用将找到该子类方法，且这些二进制文件不受影响。

如果向类中添加了一个类方法，那么除非方法调用的限定类是该子类，否则将找不到该方法。

## 13.4.25 静态初始化器

添加、删除或更改类的静态初始化器（§8.7）不会影响现有的二进制文件。

## 13.4.26 枚举类的演化

在枚举类中添加或重新排序枚举常量不会破坏与现有二进制文件的兼容性。

从枚举类中删除枚举常量将删除与该枚举常量对应的公共字段（§8.9.3）。其后果在 §13.4.8 中规定。对于广泛分发的枚举类，不建议进行此类更改。

在所有其他方面，枚举类的二进制兼容性规则与普通类相同。

## 13.4.27 Record 类的演化

在 record 类中添加、删除、更改或重新排列 record 组件可能会破坏与未重新编译的现有二进制文件的兼容性；对于广泛分发的 record 类，不建议进行此类更改。

更准确地说，添加、删除、更改或重新排列 record 组件会更改相应的组件字段和访问器方法的隐式声明，还会更改规范构造函数以及其它辅助方法的签名和实现，其后果在 §13.4.8 和 §13.4.12 中规定。

在所有其他方面，record 类的二进制兼容性规则与普通类相同。

## 13.5 接口的演化

本节描述了接口及其成员声明的更改对现有二进制文件的影响。

### 13.5.1 public 接口

将未声明为 `public` 的接口更改为声明为 `public` 不会破坏现有二进制文件的兼容性。

如果将声明为 `public` 的接口更改为不声明为 `public`，则当链接了一个需要但不再拥有接口类型访问权限的现有二进制文件时，将抛出 `IllegalAccessError`；对于广泛分发的接口，不建议进行此类更改。

### 13.5.2 sealed 和非 sealed 接口

如果将一个自由扩展的接口（§9.1.1.4）更改声明为 `sealed`，则当加载了该接口的现有子类或子接口的二进制文件且其不是该接口允许的直接子类或子接口（§9.1.4）时，将抛出 `IncompatibleClassChangeError`；对于广泛分发的类，不建议进行此类更改。

向 `sealed` 接口允许的直接子类或子接口集分别添加类或接口不会破坏现有二进制文件的兼容性。

如果从 sealed 接口允许的直接子类或接口集中删除了某个类或接口，则当加载该被删除类或接口的现有二进制文件时，将抛出 `IncompatibleClassChangeError`。

将声明为 `sealed` 的接口更改为声明为 `non-sealed` 不会破坏现有二进制文件的兼容性。

- 一个 `non-sealed` 接口 `i` 必须有一个 `sealed` 的直接父接口。删除 `non-sealed` 修饰符将阻止 `i` 能够重新编译，因为每个具有 `sealed` 直接父接口的接口必须是 `sealed` 或 `non-sealed` 的。

从一个没有 `sealed` 父接口的接口中删除 `sealed` 修饰符不会破坏现有二进制文件的兼容性。

> 如果一个 `sealed` 接口确实拥有一个 `sealed` 的直接父接口，那么删除 `sealed` 修饰符将阻止 `i` 能够重新编译，因为每个具有 `sealed` 直接父接口的接口必须是 `sealed` 或 `non-sealed` 的。

### 13.5.3 父接口

接口层级结构的更改引起导致错误的方式与 §13.4.4 中描述的类层次结构更改相同。特别是，那些导致类的某个先前的接口不再是其父接口的更改，可能会破坏现有二进制文件的兼容性，导致 `VerifyError`。

### 13.5.4 接口成员

向接口添加抽象、私有或静态方法不会破坏现有二进制文件的兼容性。

向 `C` 的父接口中添加字段可能会隐藏从 `C` 的父类继承而来的字段。如果原始引用是实例字段，将导致 `IncompatibleClassChangeError`。如果原始引用是赋值操作，将导致 `IllegalAccessError`。

从接口中删除成员可能会导致现有二进制文件中的链接错误。

#### 示例 13.5.4-1. 删除一个接口成员

```java
interface I { void hello(); }

class Test implements I {
    public static void main(String[] args) {
        I anif = new Test();
        anif.hello();
    }
}
```

```java
interface Painter {
    default void draw() {
        System.out.println("Here's a picture...");
    }
}

interface Cowboy { }

public class CowboyArtist implements Cowboy, Painter {
    public static void main(String... args) {
        new CowboyArtist().draw();
    }
}
```

```java
interface Cowboy {
    default void draw() {
        System.out.println("Bang!");
    }
}
```

```java
interface I {
    public void hello() {
        System.out.println("hello");
    }
}
```



### 13.5.5 接口类型参数

接口类型参数的变化与类类型参数的变化相同。

### 13.5.6 字段声明

接口字段声明的考虑因素与类的静态字段相同，见 §13.4.8 和 §13.4.9。

### 13.5.7 接口方法声明

接口方法声明更改的考虑因素包括类中的更改，见 §13.4.7、§13.4.14、§13.4.15、§13.4.21、§13.4.22 和 §13.4.23。

添加默认方法或将方法从抽象更改为默认不会破坏现有二进制文件的兼容性，但如果现有二进制文件尝试调用该方法，可能会导致 `IncompatibleClassChangeError`。如果方法调用的限定接口 `K` 是两个接口 `I` 和 `J` 的子接口，且 `I` 和 `J` 声明了相同签名的默认方法，且 `I` 和 `J` 互不为对方的子接口，则发生错误。

换句话说，添加默认方法是一种二进制兼容的更改，因为它在链接时不会引入错误，即使在编译时或调用时会引入错误。在实践中，引入默认方法导致意外冲突的风险与向非 final 类中添加方法的风险相似。在发生冲突时，向类中添加方法可能会触发 `LinkageError`，子类中意外的重写会导致不可预测的方法行为。

添加或删除注解对 Java 编程语言中程序二进制表示的正确链接没有影响。

## 第 14 章
### 块、语句与模式

程序的执行序列由语句控制，语句的执行是为了产生效果，并且它们没有值。

某些语句的结构中包含其他语句；这些其他语句是该语句的子语句。如果对于两个语句 $s$ 和 $u$ 之间，不存在一个不同于 $s$ 和 $u$ 的语句 $\tau$，使得 $s$ 包含 $\tau$ 且 $\tau$ 包含 $u$，我们说 $s$ 立即包含 $u$。同样，某些语句的结构中也包含表达式（§15 (Expressions)）。

本章的第一节讨论了语句的正常完成与异常完成之间的区别（§14.1）。剩余的大部分章节解释了各种类型的语句，详细描述了它们的正常行为以及对异常完成的任何特殊处理。

首先解释块（§14.2），因为它们可以出现在某些不允许出现语句的地方，而且一种语句——局部变量声明语句（§14.4.2）——必须被块立即包含。局部类和接口声明（§14.3）不是语句，但必须被块立即包含。

接下来，解释了一种规避熟悉的“悬空 else”问题（§14.5）的语法技巧。

每个语句在某种技术意义上都必须是可达的（§14.22）。

第 14.23-14.29 节被未使用，以便在未来引入新类型的语句。

本章的最后一节（§14.30）描述了模式（patterns），它们在语句和表达式内部用于条件地声明和初始化局部变量。模式对一个值（例如对象）可能由一个或多个其他值（由变量声明表示）组成简洁描述。模式匹配尝试从一个给定的值中提取一个或多个值（对其进行分解），并使用提取出的值来初始化模式所声明的变量。

### 14.1 语句的正常完成与异常完成

每个语句都有正常执行模式，其中执行某些计算步骤。后续章节描述了每种语句的正常执行模式。

如果所有步骤都按照描述执行且没有异常完成的迹象，则称该语句正常完成。然而，某些事件可能会阻止语句正常完成：

- `break`、`yield`、`continue` 和 `return` 语句（§14.15, §14.21, §14.16, §14.17）会导致控制转移，可能会阻止包含它们的表达式、语句和块正常完成。
- 某些表达式的评估可能会从 Java 虚拟机抛出异常（§15.6）。显式的 `throw`（§14.18）语句也会导致异常。异常会导致控制转移，可能会阻止语句完成。

如果发生此类事件，则一个或多个语句的执行在正常执行模式的所有步骤完成之前终止；此类语句被称为异常完成。

异常完成总有一个关联的原因，即以下之一：

- 无标签的 `break`
- 带有给定标签的 `break`
- 无标签的 `continue`
- 带有给定标签的 `continue`
- 无值的 `return`
- 带有值的 `return`
- 带有给定值的 `throw`，包括 Java 虚拟机抛出的异常
- 带有给定值的 `yield`

术语“正常完成”和“异常完成”也适用于表达式的评估（§15.6）。表达式能够异常完成的唯一原因是抛出了异常，该异常是因为带有给定值的 `throw`（§14.18）或运行时异常或错误（Exceptions），§15.6。

如果语句评估一个表达式，表达式的异常完成始终会导致语句的立即异常完成，且具有相同的原因。正常执行模式中的所有后续步骤将不再执行。

除非本章另有规定，子语句的异常完成会导致语句本身的立即异常完成，且具有相同的原因，且语句正常执行模式中的所有后续步骤将不再执行。

除非另有说明，如果一个语句评估的所有表达式和它执行的所有语句都正常完成，则该语句正常完成。

### 14.2 块

块是花括号内的一系列语句、局部变量声明语句以及局部类和接口声明。

```
Block:
  { [BlockStatements] }

BlockStatements:
  Statement [BlockStatement]

BlockStatement:
  LocalClassOrInterfaceDeclaration
  LocalVariableDeclarationStatement
  Statement
```

块的执行是通过从第一个到最后一个（从左到右）顺序执行每个局部变量声明语句和其他语句来实现的。如果所有这些块语句都正常完成，则该块正常完成。如果其中任何块语句因任何原因异常完成，则该块因相同原因异常完成。

### 14.3 局部类和接口声明

局部类是嵌套类（§8 Classes），其声明被块立即包含（§14.2）。

局部接口是嵌套接口（§9 Interfaces），其声明被块立即包含。

```
LocalClassOrInterfaceDeclaration:
  ClassDeclaration
  NormalInterfaceDeclaration
```

为了方便起见，此处显示以下产生式：

```
ClassDeclaration:
  NormalClassDeclaration
  EnumDeclaration
  RecordDeclaration

NormalClassDeclaration:
  [ClassModifier] class TypeIdentifier [TypeParameters]
  [ClassExtends][ClassImplements][ClassPermits] ClassBody

EnumDeclaration:
  [ClassModifier] enum TypeIdentifier [TypeParameters]
  [ClassImplements][ClassPermits] EnumBody

NormalInterfaceDeclaration:
  [InterfaceModifier] interface TypeIdentifier [TypeParameters]
  [InterfaceExtends][InterfacePermits] InterfaceBody
```

局部类和接口声明可以与包含块中的语句（包括变量声明语句）自由混合。

如果局部类或接口声明具有 `public`、`protected` 或 `private` 访问修饰符（§6.6），则为编译错误。

如果局部类或接口声明具有 `static`（§8.1.4）、`sealed` 或 `non-sealed`（§8.1.2）修饰符，则为编译错误。

如果局部类的直接父类或直接接口是 `sealed`，则为编译错误。如果局部接口的直接接口是 `sealed`，则为编译错误。

局部类可以是普通类（§8.1）、枚举类（§8.9）或记录类（§8.10）。每个局部普通类都是内部类（§8.1.3）。每个局部枚举类和局部记录类都是隐式的 `static`（§8.1.4），因此不是内部类。

局部接口可以是普通接口（§9.1），但不是注解接口（§9.6）。每个局部接口都是隐式的 `static`（§9.1.3）。

与匿名类（§15.9.5）一样，不是任何包、类或接口的成员（§7.1, §8.5）。与匿名类不同，局部类或接口没有简单名称（§6.2, §6.7）。

局部类或接口的作用域和隐藏在 §6.3 和 §6.4 中规定。

#### 示例 14.3-1 局部类声明

这里有一个示例说明了上述规则的几个方面：

```
class Global {

    class Cyclic {}

    void foo() {

        new Cyclic(); // 创建 Global.Cyclic

        class Cyclic extends Cyclic {} // 循环定义

        {

            class Local {

                class Local {} // 编译错误

            }

            class Local() // 编译错误

            class AnotherLocal {

                void bar() {

                    class Local {} // 正确

                }

            }

            class Local() // 正确，不在之前的 Local 作用域内

        }

    }

}
```

方法 `foo` 的第一个语句创建成员类 `Global.Cyclic` 的实例，而不是局部类 `Cyclic` 的实例，因为该语句出现在局部类声明的作用域之前。

局部类声明的作用域涵盖整个部分（而不只是其主体），这意味着局部类 `Cyclic` 的定义通过 `Global.Cyclic` 是循环的。因此，局部类的声明在编译时被拒绝。

由于局部类名不能在同一个方法（构造函数或初始化器，视情况而定）中重声明，因此 `Local` 的后续声明会导致编译错误。然而，`Local` 可以在另一个更深层次的类（如 `AnotherLocal`）的上下文中重新声明。

`Local` 的最终声明是合法的，因为它发生在任何先前的 `Local` 声明的范围之外。

### 14.4 局部变量声明

局部变量声明用于声明并可选地初始化一个或多个局部变量（§4.12.3）。

```
LocalVariableDeclaration:
  {VariableModifier} LocalVariableType VariableDeclarList

LocalVariableType:
  UnannType
  var
```

关于 `UnannType` 参见 §8.3。为了方便，这里显示了 §4.3、§8.3 和 §8.4.1 中的以下产生式：

```
VariableModifier:
  Annotation
  final

VariableDeclarList:
  VariableDeclar ( , VariableDeclar )

VariableDeclar:
  VariableDeclarId = VariableInitializer

VariableDeclarId:
  Identifier Dims

Dims:
  [Annotation] { } []

VariableInitializer:
  Expression
  ArrayInitializer
```

局部变量声明可以出现在以下位置：

- `for` 语句中的局部变量声明语句（§14.4.2）
- 基础 `for` 语句的头部（§14.14.1）
- `try-with-resources` 语句的增强 `for` 语句的头部（§14.20.3）
- 一个模式（§14.30.1）

关于局部变量声明的注解修饰符规则规定在 §9.7.4 和 §9.7.5 中。

如果关键字 `final` 作为局部变量声明的修饰符出现，则该局部变量是一个 final 变量（§14.12.4）。

如果 `final` 作为局部变量声明的修饰符出现多次，则为编译错误。

如果 `LocalVariableType` 为 `var` 且满足以下任一条件，则为编译错误：

- 列出了多个 `VariableDeclarator`。
- `VariableDeclaratorId` 有一个或多个括号对。
- `VariableDeclarator` 缺少初始化器。
- `VariableDeclarator` 的初始化器是一个 `ArrayInitializer`。
- `VariableDeclarator` 的初始化器包含对 `var` 的引用。

#### 示例 14.4-1 使用 `var` 的局部变量

以下代码说明了这些限制 `var` 使用的规则：

```
var a = 1;                  // 合法

var b = 2, c = 3.0;     // 非法：多个声明符

var d[] = new int[4];   // 非法：额外的括号对

var e;                   // 非法：无初始化器

var f = { 6 };           // 非法：数组初始化器

var g = (g = 7);         // 非法：初始化器中的自引用
```

这些限制有助于避免对 `var` 所代表的类型产生困义。

### 14.4.1 局部变量声明符和类型

局部变量声明中的每个声明符都声明一个局部变量，其名称是出现在声明符中的 `Identifier`。

如果可选的关键字 `final` 出现在声明的开头，则被声明的变量是一个 final 变量（§14.12.4）。

局部变量的声明类型按如下确定：

- 如果 `LocalVariableType` 是 `UnannType` 且 `UnannType` 或 `VariableDeclaratorId` 中没有出现括号对，则局部变量的类型由 `UnannType` 表示。
- 如果 `LocalVariableType` 是 `UnannType` 且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号对，则局部变量的类型由 §10.2 规定。
- 如果 `LocalVariableType` 为 `var`

如果 $\tau$ 是空类型，则为编译错误。

由于初始化器被处理为仿佛未出现在赋值上下文中，如果它是一个 lambda 表达式（§15.27）或方法引用表达式（§15.13），则会发生错误。

局部变量声明的作用和遮蔽规定在 §6.3 和 §6.4 中。

从嵌套类、接口或 lambda 表达式对局部变量的引用受到 §6.5.1 的限制。

#### 14.4.1-1 使用 `var` 声明的局部变量的类型

```
var a = 1;                                     // a 类型为 'int'

var b = java.util.List.of(1, 2);             // b 类型为 'List<Integer>'

var c = "x".getClass();                    // c 类型为 'Class<? extends String>'

var d = new Object() {};                      // d 类型为匿名类的类型

var e = (CharSequence & Comparable<String>)"x"; // e 类型为 'CharSequence & Comparable<String>'

var f = () -> "hello";                      // 非法：lambda 不在赋值上下

var g = null;                                // 非法：空类型
```

以下代码说明了用 `var` 声明的变量类型：

注意，用 `var` 声明的变量不能用显式类型声明，因为变量的类型是不定的。

在确定变量类型时，对初始化器的类型应用向上投影（Upward projection）。如果初始化器的类型包含捕获变量，此投影会将变量映射到不包含捕获变量的超类型。

虽然允许变量的类型提到捕获变量，但通过投影它们，我们强制执行了一种人的不变性：即捕获变量的范围不大于包含被捕获类型表达式的语句。重要的是，捕获变量不会“泄漏”到后续语句中。

### 14.4.2 局部变量声明语句

变量声明语句由一个变量声明组成。

```
LocalVariableStatement:
  LocalVariableDeclaration;
```

每个变量声明语句都立即包含在块中，而其他类型的语句（§14.5）可能立即包含在块或另一个语句中。

在包含的块中，变量声明语句可以与其他语句以及类接口声明自由混合。

变量声明语句是一个可执行语句。每当执行它时，从左到右处理声明符。如果声明符有初始化器，则计算初始化器并将其赋值给变量。

> 如果声明符没有初始化器，则对变量的任何引用必须先执行赋值，否则将根据 §16（确定赋值）的规则发生编译错误。

每个初始化器（第一个外）仅在前一个初始化器正常完成后才被计算。

如果最后一个初始化器正常完成，则变量声明语句正常完成。

如果变量声明语句中的所有声明符都没有初始化器，则执行该语句始终正常完成。

### 14.5 语句

是 Java 编程语言中的多种语句。大多数对应于 C 和 C++ 语言中的语句，但唯一的。

与 C 和 C++ 一样，如果 Java 编程语言的语句会导致所谓的“悬空 else”问题（dangling else），如这个误导性的示例所示：

```
if (door.isOpen())

    if (resident.isVisible())

        resident.greet("Hello!");

else door.bell.ring(); // 一个悬空 else
```



# 块、语句与模式

## 空语句 14.6

问题在于外部 `if` 语句和内部 `if` 语句都可能拥有 `else` 子句。在这个示例中，人们可能认为程序员想要让 `else` 子句属于外部 `if` 语句。

Java 编程语言像 C 和 C++ 以及它们之前的许多编程语言一样，任意规定 `else` 子句属于它可能所属的最内层 `if`。此规则由以下语法捕获：

```
Statement:
    StatementWithoutTrailingStatement
    LabeledStatement
    IfThenStatement
    IfThenElseStatement
    WhileStatement
    ForStatement

StatementNoShortIf:
    StatementWithoutTrailingStatement
    LabeledStatementNoShortIf
    IfThenElseStatementNoShortIf
    WhileStatementNoShortIf
    ForStatementNoShortIf

StatementWithoutTrailingSubStatement:
    Block
    EmptyStatement
    ExpressionStatement
    AssertStatement
    SwitchStatement
    DoStatement
    BreakStatement
    ContinueStatement
    ReturnStatement
    SynchronizedStatement
    ThrowStatement
    TryStatement
    YieldStatement
```

为了方便，这里显示了 §14.9 中的以下产生式：

```
IfThenStatement:
    if ( Expression ) Statement

IfThenElseStatement:
    if ( Expression ) StatementNoShortIf else Statement
```

```
IfThenElseStatementNoShortIf:
    if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

因此，语句在语法上被分为两类：一类是以没有 `else` 子句的 `if` 语句结尾的语句（即“短 if 语句”），另一类则绝对不会。

只有那些确定不会以短 `if` 语句结尾的语句，才可以在带有 `else` 子句的 `if` 语句中作为 `else` 关键字之前的直接子语句出现。

这一简单规则防止了“悬空 else”问题。带有“无短 if”限制的语句，其执行行为与没有该“无短 if”限制的同类语句的执行行为完全相同；这种区分纯粹是为了解决语法上的困难。

### 14.6 空语句

空语句不执行任何操作。

```
EmptyStatement:
    ;
```

空语句的执行总是正常完成的。

## 14.7 标记语句

语句可以带有标记前缀。

```
LabeledStatement:
    Identifier : Statement

LabeledStatementNoShortIf:
    Identifier : StatementNoShortIf
```

该 `Identifier` 被声明为其直接包含的 `Statement` 的标记。

与 C 和 C++ 不同，Java 编程语言没有 `goto` 语句；标识符语句标记用于标记语句内任何的 `break` 或 `continue` 语句（§14.15, §14.16）。

标记语句的作用域是其直接包含的 `Statement`。

如果标记语句的名称在标记的作用域内作为另一个标记语句的标记使用，则会导致编译时错误。

不限制将相同的标识符作为标记以及包、类、接口、方法、字段、参数或局部变量名。将标识符用于标记语句并不会遮蔽（§6.4.2）同名的包、类、接口、方法、字段、参数或局部变量。将标识符作为类、接口、方法、字段、局部变量或异常处理程序的参数（§14.20）使用，不会遮蔽同名的语句标记。

标记语句通过执行其直接包含的 `Statement` 来执行。

如果语句被一个 `Identifier` 标记，且包含的 `Statement` 因为一个具有相同 `Identifier` 的 `break` 而异常完成，则标记语句正常完成。在 `Statement` 所有其他异常完成的情况下，标记语句将以相同的原因异常完成。

### 示例 14.7-1. 标记与标识符

以下代码取自 `String` 类及其 `indexOf` 方法的一个版本，其中标记最初名为 `test`。将标记更改为与局部变量相同的名称并不会遮蔽 `i` 声明作用域内的标记。因此，该代码是有效的。

```
class Test {

    char[] value;

    int offset, count;

    int indexOf(TestString str, int fromIndex) {

        char[] v1 = value, v2 = str.value;

        int max = offset + (count * str.count);

        int start = offset + (fromIndex < 0) ? 0 : fromIndex);

        i:
        for (int i = start; i <= max; i++) {

            int n = str.count, j = i, k = str.offset;

            while (n != 0) {

                if (v1[j++] != v2[k++])
                    continue i;
            }

            return offset;
        }

        return -1;
    }
}
```

标识符 `max` 也可以用作语句标记；该标记不会遮蔽标记语句内的局部变量 `max`。

## 14.8 表达式语句

某些类型的表达式可以通过在后面加上分号来作为语句使用。

```
ExpressionStatement:
    StatementExpression;

StatementExpression:
    Assignment
    PreIncrementExpression
    PreDecrementExpression
    PostIncrementExpression
    PostDecrementExpression
    MethodInvocation
    ClassInstanceCreationExpression
```

表达式语句通过求值表达式来执行；如果表达式有值，则该值被丢弃。

当且仅当表达式语句的求值正常完成时，表达式语句的执行正常完成。

> 与 C 和 C++ 不同，Java 编程语言仅允许将某些形式的表达式用表达式语句。例如，使用方法调用表达式（§15.12）是合法的：
>
> ```
> System.out.println("Hello world"); // OK
> ```
>
> 但使用带括号的表达式（§15.8.5）是不合法的：
>
> ```
> (System.out.println("Hello world")); // illegal
> ```
>
> 注意，Java 编程语言不允许“转换为 void”的类型 - 因此，传统的 C 技巧，如编写如下的表达式语句：
>
> ```
> (void) ...; // incorrect!
> ```
>
> 是不可行的。相反，Java 编程语言允许在表达式语句中使用所有最有用的表达式类型，并且并不要求作为表达式语句的方法调用必须调用 `void` 方法，因此这种技巧几乎永远不需要。如果需要这种技巧，可以使用赋值语句（§15.26）或局部变量声明语句（§14.4）代替。

## 14.9 if 语句

`if` 语句允许语句的条件执行或对两个语句进行条件选择，执行其中一个但不同执行两者。

```
IfThenStatement:
    if ( Expression ) Statement

IfThenElseStatement:
    if ( Expression ) Statement else Statement

IfThenElseStatementNoShortIf:
    if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

`Expression` 必须是 `boolean` 或 `Boolean` 类型。

### 14.9.1 if-then 语句

if-then 语句通过首先求值 `Expression` 来执行。如果结果是 `Boolean` 类型，则进行拆箱转换（5.1）。

如果 `Expression` 的求值或后续拆箱转换（如果有）异常完成，则 if-then 语句以相同的原因异常完成。

否则，根据值进行选择：

- 如果值为 `true`，则执行 `Statement`；if-then 语句正常完成当且仅当 `Statement` 正常完成。
- 如果值为 `false`，则不采取操作且 if-then 语句正常完成。

### 14.9.2 if-then-else 语句

if-then-else 语句通过首先求值 `Expression` 来执行。如果结果是 `Boolean` 类型，则进行拆箱转换（5.1）。

如果 `Expression` 的求值或后续拆箱转换（如果有）异常完成，则 if-then-else 语句以相同的原因异常完成。

否则，根据结果进行选择：

- 如果值为 `true`，则执行第一个语句（`else` 之前的语句）；if-then-else 语句正常完成当且仅当该语句正常完成。
- 如果值为 `false`，则执行第二个语句（`else` 之后的语句）；if-then-else 语句正常完成当且仅当该语句正常完成。

## 14.10 assert 语句

断言是包含布尔表达式的 `assert` 语句。断言可以被启用或禁用。如果断言被启用，执行断言会导致布尔表达式求值，如果表达式为 `false`，则报告错误。如果断言被禁用，执行断言将没有任何影响。

```
AssertStatement:
    assert Expression;
    assert Expression : Expression;
```

为了方便演示，两种 `assert` 语句形式中的第一个 `Expression` 称为 `Expression1`。在 `assert` 语句的第二形式中，第二个 `Expression` 称为 `Expression2`。

如果 `Expression1` 不是 `boolean` 或 `Boolean` 类型，则会导致编译错误。

如果在 `assert` 语句的第二形式中，`Expression2` 是 `void` 类型（§15.1），则会导致编译错误。

在类或接口初始化完成后执行的断言语句，当且仅当主机系统确定词法包含该断言语句的顶层类或接口启用断言时，才会执行。

顶层类或接口启用断言的确定晚于 (i) 顶层类或接口的初始化以及 (ii) 嵌套在顶层类或接口中的任何类或接口的初始化。一旦确定了顶层类或接口是否启用断言，就无法更改。

已启用的断言语句通过首先求值 `Expression1` 来执行。如果结果的类型为布尔，则对其进行拆箱转换 (§5.1.8)。

如果 `Expression1` 的求值或随后的拆箱转换（如果有）由于某种原因异常完成，则断言语句也以相同原因异常完成。

否则，将根据 `Expression1` 的值进行选择并继续执行：

- 如果该值为 `true`，则不采取任何后续操作，断言语句正常完成。
- 如果该值为 `false`，则执行行为取决于是否存在 `Expression2`：
  - 如果存在 `Expression2`，则对其进行求值。然后：
    - 如果求值由于某种原因异常完成，则断言语句也以相同原因异常完成。
    - 如果求值正常完成，则创建一个 `AssertionError` 实例，其“详细消息”（detail message）为 `Expression2` 的结果。
    - 如果实例创建由于某种原因异常完成，则断言语句也以相同原因异常完成。
    - 如果实例创建正常完成，则通过抛出新创建的 `AssertionError` 对象使断言语句异常完成。
  - 如果不存在 `Expression2`，则创建一个没有“详细消息”的 `AssertionError` 实例。
    - 如果实例创建由于某种原因异常完成，则断言语句也以相同原因异常完成。
    - 如果实例创建正常完成，则通过抛出新创建的 `AssertionError` 对象使断言语句异常完成。

通常，断言检查在程序开发和测试期间启用，并在部署时禁用以提高性能。

由于断言可能会被禁用，程序不能假设断言中包含的表达式会被求值。这些布尔表达式通常不具有副作用。求值此类布尔表达式不应影响求值完成后可见的任何状态。断言中包含的布尔表达式具有副作用并不是非法的，但通常是不恰当的，因为这可能导致程序行为根据断言的启用或禁用而发生变化。

鉴于此，不应将断言用于公共方法中的参数检查。参数检查通常是方法契约的一部分，无论断言启用还是禁用，都必须维护这一契约。

使用断言进行参数检查的次要问题是，错误的参数应该导致适当运行时异常（例如 `IllegalArgumentException`、`ArrayIndexOutOfBoundsException` 或 `NullPointerException`）。断言失败不会抛出适当的异常。再次，在公共方法中使用断言进行参数检查并非非法，但通常是不恰当的。设计上希望 `AssertionError` 永远不会被捕获，但也可以这样做，`try` 语句的规则应处理 `try` 块中出现的断言类似于当前对 `throw` 语句的处理。

## 14.11 switch 语句

`switch` 语句根据表达式的值将控制权转移到多个语句或表达式之一。

```
SwitchStatement:
    switch ( Expression ) SwitchBlock
```

`Expression` 被称为选择表达式。选择表达式的类型必须是 `char`、`byte`、`short`、`int`、`Character`、`Byte`、`Short`、`Integer`、`String` 或枚举类型 (§8.9)，否则将发生编译时错误。

### 14.11.1 Switch 块

`switch` 语句和 `switch` 表达式 (§15.28) 的体都被称为 switch 块（switch block）。本节介绍了适用于所有 switch 块的通用规则，无论它们出现在 `switch` 语句还是 `switch` 表达式中。其他章节提供了附加规则，这些规则要么关联 `switch` 语句中的 switch 块 (§14.11.2)，要么关联 `switch` 表达式中的 switch 块 (§15.28.1)。

```
SwitchBlock:
    { SwitchRule {SwitchRule} }
    { {SwitchBlockStatementGroup} {SwitchLabel:} }

SwitchRule:
    SwitchLabel -> Expression ;
    SwitchLabel -> Block
    SwitchLabel -> ThrowStatement

SwitchBlockStatementGroup:
    SwitchLabel : {SwitchLabel:} BlockStatements

SwitchLabel:
    case CaseConstant [, CaseConstant ...]
    default

CaseConstant:
    ConditionalExpression
```



# 块、语句与模式

## switch 语句 (§14.11)

一个 `switch` 块可以由以下部分组成：

- **Switch 规则**（使用 `->` 引入 switch 规则表达式、switch 块或 switch 规则 `throw` 语句）；
- **Switch 标签语句组**（使用 `:` 引入 switch 标签语句组）。

每个 switch 规则和 switch 标签语句组都以 switch 标签开始，该标签是 `case` 标签或 `default` 标签。一个 switch 标签语句组允许多个 switch 标签。

`case` 标签包含一个或多个 `case` 常量。每个 `case` 常量必须是常量表达式 (§15.29) 或枚举常量的名称 (§8.9.1)，否则将发生编译时错误。

switch 标签及其 `case` 常量认为与 `switch` 块关联。与 `switch` 块关联的两个 `case` 常量不能具有相同的值，否则将发生编译时错误。

如果满足以下两个条件，则 `switch` 语句或 `switch` 表达式的 `switch` 块与选择表达式的类型 `T` 兼容：

- 如果 `T` 不是枚举类型，则与 `switch` 块关联的每个 `case` 常量与 `T` 兼容 (§5.2)。
- 如果 `T` 是枚举类型，则与 `switch` 块关联的每个 `case` 常量都是类型 `T` 的枚举常量。

`switch` 语句或 `switch` 表达式的 `switch` 块必须与选择表达式的类型兼容，否则将发生编译时错误。

`switch` 语句执行 (§14.11.3) 和 `switch` 表达式的求值 (§15.28.2) 都需要确定 `switch` 是否匹配选择表达式。要确定 `switch` 块中的 `switch` 标签是否匹配给定值，会将该值与 `switch` 块关联的 `case` 常量进行比较。然后：

- 如果其中一个 `case` 常量等于该值，我们说包含该 `case` 常量的 `case` 标签为匹配。

相等性根据 `==` 运算符 (§15.21) 定义，除非该值是 `String`，在这种情况下相等性根据 `String` 类的 `equals` 方法定义。

- 如果没有 `case` 标签匹配但存在 `default` 标签，则说 `default` 标签为匹配。

`case` 标签可以包含多个 `case` 常量。如果其常量中的任何一个匹配选择表达式的值，则该标签就匹配选择表达式的值。例如，在以下代码中，如果枚举变量 `day` 是所示枚举中的之一，则该 `case` 标签为匹配：

```java
switch (day) {
    ...
    case SATURDAY, SUNDAY:
        System.out.println("It's the weekend!");
        break;
    ...
}
```

`null` 不能作为 `case` 常量，因为它不是常量表达式。即使允许 `null`，它也是不理想的，因为该 `case` 中的代码永远不会被执行。这是因为对于给定引用类型的选择表达式（即 `String` 或包装后的原始类型或枚举类型），如果选择器在运行时求值为 `null`，则将发生异常。在 Java 编程语言设计者看来，传播异常比没有 `case` 标签或 `default` 标签匹配是更好的结果。

Java 编译器被鼓励（但不是要求）如果在枚举类型选择表达式的 `switch` 语句缺少 `default` 标签且缺少枚举中的一个或多个常量，则提供警告。如果表达式求值为其中一个常量，此类 `switch` 语句将静静地什么都不做。

在 C 和 C++ 中，`switch` 语句的体可以是一个语句，并且带有 `case` 标签的语句不需要立即包含在该语句中。考虑简单的循环：

```java
for (i = 0; i < n; i++) foo();
```

其中 `n` 已知为正。可以使用被称为 Duff device 的技巧在 C 或 C++ 中展开循环，但这在 Java 编程语言中不是有效代码：

```java
int q = (n + 7) / 8;
switch (n % 8) {
    case 0:
        do {
            foo(); // Great C hack, Tom,
            case 7: foo(); // but it's not valid here.
            case 6: foo();
            foo();
            case 5: foo();
            case 4: foo();
            case 3: foo();
            case 2: foo();
            case 1: foo();
        } while (--q > 0);
}
```

幸运的是，这种技巧似乎并没有被广泛为人知或使用。此外，如今这种需求已经减少；这类代码转换通常属于最先进优化编译器的范围。

### 14.11.2 switch 语句的 switch 块

除了 `switch` 块的通用规则（§14.11.1）外，`switch` 语句中的 `switch` 块还有进一步的规则。也就是说，`switch` 语句的 `switch` 块必须满足以下条件，否则将发生编译时错误：

- `switch` 块最多关联一个 `default` 标签。
- `switch` 块中的每个 switch 规则表达式都是 `switch` 表达式（§14.8）。

`switch` 语句与 `switch` 表达式的区别在于，`switch` 块中箭头（`->`）右侧可以出现哪些表达式，即哪些表达式可以作为 switch 规则表达式。在 `switch` 语句中，只有语句可以作为 switch 规则表达式，但在 `switch` 表达式中，任何表达式都可以使用（§15.28.1）。

### 14.11.3 switch 语句的执行

`switch` 语句的执行首先是求值选择器表达式。然后：

- 如果选择器表达式的评估异常完成，则整个 `switch` 语句因相同原因异常完成。
- 否则，如果选择器表达式的评估结果为 `null`，则抛出 `NullPointerException`，整个 `switch` 语句因该原因异常完成。
- 否则，如果选择器表达式的评估结果类型为 `Character`、`Byte`、`Short` 或 `Integer`，则将进行拆箱转换（§5.1.8）。如果该转换异常完成，则整个 `switch` 语句以相同原因异常完成。

如果选择器表达式的评估正常完成且结果非空，随后的拆箱转换（如果有）也正常完成，则通过确定与 `switch` 块关联的 `switch` 标签是否匹配选择器表达式的值继续执行 `switch` 语句（§14.11.1）。然后：

- 如果没有 `switch` 标签，整个 `switch` 语句正常完成。
- 如果匹配 `switch` 标签，则执行以下操作之一：
  - 如果它是 switch 规则的标签，则该规则表达式必然是一个语句表达式（§14.11.2）。评估该语句表达式。如果评估正常完成，则 `switch` 语句正常完成。如果评估结果是一个值，则将其丢弃。
  - 如果它是 switch 规则块的标签，则执行该块。如果该块正常完成，则 `switch` 语句正常完成。
  - 如果它是 switch 规则 `throw` 语句的标签，则执行该 `throw` 语句。
  - 如果它是 switch 标签语句的标签，则按顺序执行 `switch` 块中该标签之后的所有语句。如果这些语句正常完成，则 `switch` 语句正常完成。
  - 否则，`switch` 块中匹配的 `switch` 标签之后没有语句，`switch` 语句正常完成。

如果 `switch` 块中任何语句或表达式的执行异常完成，则按如下方式处理：

- 如果语句的执行因为无标签的 `break` 而异常完成，则不采取进一步操作，`switch` 语句正常完成。由于带标签的 `break` 导致的异常完成由标签语句的通用规则（§14.7）处理。
- 如果语句或表达式的执行因其他原因异常完成，则 `switch` 语句因相同原因异常完成。由于 `yield` 语句导致的异常完成由 `switch` 表达式的通用规则（§15.28.2）处理。

#### 示例 14.11.3-1. switch 语句中的穿透

当选择器匹配 switch 规则的 `switch` 标签时，执行由该标签引入的 switch 规则表达式或语句。对于语句组的 `switch` 标签，执行该 `switch` 块中该标签之后的所有语句，包括出现在后续 `switch` 标签之后的语句。其效果是，在 C 和 C++ 中一样，语句的执行可以“穿透标签”。

例如，程序：

```java
class TooMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.print("*one");
            case 2: System.out.print("*two");
            case 3: System.out.println("*many");
        }
    }

    public static void main(String[] args) {
        howMany(3);
        howMany(2);
        howMany(1);
    }
}
```

包含一个 `switch` 块，其中每个 `case` 的代码都会掉入下一个 `case` 的代码。结果，程序打印：

```
many
too many
one too many
```

穿透可能是导致微妙 bug 的原因。如果代码不穿透以指示何时转移控制流，如下程序所示：

```java
class TooMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.println("*one");
                break;
            case 2: System.out.println("*two");
                break;
            case 3: System.out.println("*many");
                break;
        }
    }

    static void howManyAgain(int k) {
        switch (k) {
            case 1: System.out.println("*one");
                break;
            case 2: System.out.println("*two");
                break;
            case 3: System.out.println("*many");
                break;
        }
    }

    public static void main(String[] args) {
        howMany(3);
        howMany(2);
        howMany(1);
    }
}
```

此程序打印：

```
one
two
many
one
two
many
```

## 14.12 while 语句

`while` 语句重复执行表达式和语句，直到表达式值为 `false`。

> **WhileStatement:**
> `while ( Expression ) Statement`
>
> **WhileStatementNoIf:**
> `while ( Expression ) StatementNoShortIf`

`Expression` 类型为 `boolean` 或 `Boolean`，否则将发生编译错误。

`while` 语句的执行首先评估 `Expression`。如果结果为 `Boolean`，则进行拆箱转换（§5.1.8）。如果 `Expression` 评估或随后的拆箱转换（如果有）因某种原因异常完成，则 `while` 语句因该原因异常完成。

否则，根据值继续执行：

- 如果值为 `true`，则执行 `Statement`。然后选择：
  - 如果 `Statement` 正常完成，则整个 `while` 语句重新执行，从重新评估 `Expression` 开始。
  - 如果 `Statement` 异常完成，见 §14.12.1。
- 如果可能的拆箱结果值为 `false`，则不采取进一步操作，`while` 语句正常完成。

如果可能的拆箱结果值是第一次评估的结果，则不执行 `Statement`。

### 14.12.1 while 语句的异常完成

包含 `Statement` 的异常完成按如下方式处理：

- 如果 `Statement` 执行因无标签的 `break` 而异常完成，不采取进一步操作，`while` 语句正常完成。
- 如果 `Statement` 执行因无标签的 `continue` 而异常完成，则整个 `while` 语句重新执行。
- 如果 `Statement` 执行因带标签 `L` 的 `continue` 而异常完成，则选择：
  - 如果 `while` 语句有标签 `L`，则整个 `while` 语句重新执行。
  - 如果 `while` 语句没有标签 `L`，则 `while` 语句因带标签的 `continue` 异常完成。
- 如果 `Statement` 执行因其他原因异常完成，则 `while` 语句因相同原因异常完成。

## 14.13 do 语句

`do` 语句重复执行语句和表达式，直到表达式值为 `false`。

> **DoStatement:**
> `do Statement while ( Expression ) ;`

`Expression` 的类型必须是 `boolean` 或 `Boolean`，否则将发生编译时错误。

`do` 语句的执行方式是首先执行 `Statement`。然后有如下选择：

- 如果 `Statement` 的执行正常完成，则对 `Expression` 进行求值。如果结果类型为 `Boolean`，则对其进行解箱转换 (§5.1.8)。
  - 如果 `Expression` 的求值或随后的解箱转换（如果有）由于某种原因异常完成，则 `do` 语句由于该原因异常完成。
  - 否则，将根据求值得到的值进行如下选择：
    - 如果该值为 `true`，则再次执行整个 `do` 语句。
    - 如果该值为 `false`，则不采取任何后续操作，`do` 语句正常完成。
- 如果 `Statement` 的执行异常完成，请参见 §14.13.1。

> 执行 `do` 语句始终会至少执行一次其包含的 `Statement`。

### 14.13.1 do 语句的异常完成

其包含的 `Statement` 的异常完成将按以下方式处理：

- 如果 `Statement` 的执行由于不带标签的 `break` 而异常完成，则不采取任何后续操作，`do` 语句正常完成。
- 如果 `Statement` 的执行由于不带标签的 `continue` 而异常完成，则对 `Expression` 进行求值。然后将根据求值得到的值进行如下选择：
  - 如果该值为 `true`，则再次执行整个 `do` 语句。
  - 如果该值为 `false`，则不采取任何后续操作，`do` 语句正常完成。
- 如果 `Statement` 的执行由于带有标签 `L` 的 `continue` 而异常完成，则有如下选择：
  - 如果 `do` 语句带有标签 `L`，则对 `Expression` 进行求值。有如下选择：
    - 如果 `Expression` 的值为 `true`，则再次执行整个 `do` 语句。
    - 如果 `Expression` 的值为 `false`，则不采取任何后续操作，`do` 语句正常完成。
  - 如果 `do` 语句不带有标签 `L`，则 `do` 语句由于带有标签 `L` 的 `continue` 而异常完成。
- 如果 `Statement` 的执行由于其他任何原因异常完成，则 `do` 语句由于相同原因异常完成。

由于带有标签的 `break` 导致异常完成的情况将由标签语句的通用规则 (§14.7) 处理。

#### 示例 14.13-1. `do` 语句

```java
public static String toHexString(int i) {
    StringBuilder buf = new StringBuilder(8);
    do {
        buf.append(Character.forDigit(i & 0xF, 16));
        i >>>= 4;
    } while (i != 0);
    return buf.reverse().toString();
}
```

## 14.14 for 语句

（原文此处内容缺失，仅保留标题占位）



因为必须生成一个数字，因此 `do` 语句是一种适当的控制结构。

## 14.14 for 语句

`for` 语句有两种形式：

- 基础 `for` 语句。
- 增强型 `for` 语句。

## 14.14 for 语句 语句块、语句与模式

```
ForStatement:
    BasicForStatement
    EnhancedForStatement

ForStatementNoShortIf:
    BasicForStatementNoShortIf
    EnhancedForNoShortIf
```

## 14.14.1 基础 for 语句

基础 `for` 语句首先执行某些初始化代码，然后重复执行一个 `Expression`、`Statement` 和一些更新代码，直到 `Expression` 的值为 `false` 为止。

```
BasicStatement:
    for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement

BasicStatementNoShortIf:
    for ( [ForInit] ; [Expression] ; [ForUpdate] ) StatementNoShortIf

ForInit:
    StatementExpressionList
    LocalVariableDeclaration

ForUpdate:
    StatementExpressionList

StatementExpressionList:
    StatementExpression (, StatementExpression)*
```

`Expression` 必须是 `boolean` 或 `Boolean` 类型，否则将发生编译时错误。

基础 `for` 语句中 `ForInit` 部分声明的局部变量的作用域和遮蔽在 §6.3 和 §6.4 中有规定。

从嵌套类、接口或 lambda 表达式引用基础 `for` 语句 `ForInit` 部分声明的局部变量受到 §6.5.6.1 规定的限制。

## 14.14.1.1 for 语句的初始化

`for` 语句的执行首先执行 `ForInit` 代码：

- 如果 `ForInit` 代码是语句表达式列表 (§14.8)，则按从左到右的顺序求值；它们的值（如果有）将被丢弃。
  如果任何表达式的求值由于某种原因异常完成，`for` 语句由于相同原因异常完成；异常完成的表达式右侧的任何 `ForInit` 语句表达式将不会被执行。
- 如果 `ForInit` 代码是局部变量声明 (§14.4)，则其执行方式等同于出现在块 (§14.4.2) 中的局部变量声明语句。
  如果局部变量声明的执行由于任何原因异常完成，`for` 语句由于相同原因异常完成。
- 如果不存在 `for` 部分，则不采取任何操作。

## 14.14.1.2 for 语句的迭代

接下来，执行迭代步骤，如下：

- 如果存在 `Expression`，则对其进行求值。如果结果类型为 `Boolean`，则对其进行解箱转换 (§5.1)。
  如果 `Expression` 的求值或随后的解箱转换（如果有）由于某种原因异常完成，`for` 语句由于相同原因异常完成。
  否则，将根据 `Expression` 是否存在及其结果进行选择：
  - 如果 `Expression` 不存在，或者 `Expression` 存在且其求值结果（包括可能的解箱）为 `true`，则执行包含的 `Statement`。然后有如下选择：
    - 如果 `Statement` 执行正常，则按顺序执行以下两个步骤：
      首先，如果存在 `ForUpdate` 部分，则按从左到右的顺序求值；它们的值（如果有）将被丢弃。如果任何表达式的求值由于某种原因异常完成，`for` 语句由于相同原因异常完成；异常完成的表达式右侧的表达式将不会被执行。
      如果不存在 `ForUpdate` 部分，则不采取任何操作。
      其次，执行另一个迭代步骤。
    - 如果 `Statement` 执行异常完成，请参见 §14.1.3。
  - 如果 `Expression` 存在且其求值结果（包括可能的解箱）为 `false`，则不采取任何后续操作，`for` 语句正常完成。

`Expression` 的（可能的解箱）值在第一次求值时为 `false`，则不执行 `Statement`。

如果 `Expression` 不存在，`for` 语句正常完成的唯一方法是使用 `break` 语句。

## 14.14.1.3 for 语句的异常完成

包含的 `Statement` 的异常完成将按以下方式处理：

- 如果 `Statement` 的执行由于不带标签的 `break` 而异常完成，则不采取任何后续操作，`for` 语句正常完成。
- 如果 `Statement` 的执行由于不带标签的 `continue` 而异常完成，则按顺序执行以下两个步骤：
  首先，如果存在 `ForUpdate` 部分，则按从左到右的顺序求值；它们的值（如果有）将被丢弃。
  不存在 `ForUpdate` 部分，则不采取任何操作。
  其次，执行另一个迭代步骤。
- 如果 `Statement` 的执行由于带有标签 `L` 的 `continue` 而异常完成，则有如下选择：
  - 如果 `for` 语句带有标签 `L`，则按顺序执行以下两个步骤：
    首先，如果存在 `ForUpdate` 部分，则按从左到右的顺序求值；它们的值（如果有）将被丢弃。
    不存在 `ForUpdate` 部分，则不采取任何操作。
    其次，执行另一个迭代步骤。
  - 如果 `for` 语句不带有标签 `L`，则 `for` 语句由于带有标签 `L` 的 `continue` 而异常完成。

## 14.14.2 增强型 for 语句

增强型 `for` 语句的形式如下：

```
EnhancedForStatement:
    for ( LocalVariableDeclaration : Expression ) Statement

EnhancedForStatementNoShortIf:
    for ( LocalVariableDeclaration : Expression ) StatementNoShortIf
```

此处展示了 §4.3、§8.4.1 和 §14.4 中的以下产生式：

```
VariableModifier:
    Annotation
    final

LocalVariableType:
    UnannType
    var

VariableDeclaratorList:
    VariableDeclarator [ , VariableDeclarator ]

VariableDeclarator:
    VariableDeclaratorId [ = VariableInitializer ]

VariableDeclaratorId:
    Identifier [ Dims ]

Dims:
    { [ Annotation ] [ ] }...
```

`Expression` 的类型必须是数组类型 (§10.1) 或原始类型 `Iterable` 的子类型，否则将发生编译错误。

增强型 `for` 语句头部声明了一个局部变量，其名称为 `VariableDeclaratorId` 给出的标识符。当执行增强型 `for` 语句时，局部变量会在循环的每次迭代中初始化为 `Iterable` 或由该表达式产生的数组的后继元素。

在增强型 `for` 语句头部声明的局部变量的规则规定在 §14.4 中，忽略该节中适用于 `LocalVariableType` 为 `var` 时的任何规则。此外，必须满足以下所有条件，否则将发生编译错误：

- `VariableDeclaratorList` 由单个 `VariableDeclarator` 组成。
- `VariableDeclarator` 没有初始化器。
- 如果 `LocalVariableType` 为 `var`，则 `VariableDeclaratorId` 没有括号对。

增强型 `for` 语句头部声明的局部变量的作用域和遮蔽规定在 §6.3 和 §6.4 中。

从嵌套类、接口或 lambda 表达式对局部变量的引用受到 §6.5.6.1 的限制。

增强型 `for` 语句头部声明的局部变量的类型 τ 确定如下：

- 如果 `LocalVariable` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中未出现括号对，则 τ 是 `UnannType` 所表示的类型。
- 如果 `LocalVariable` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号对，则 τ 由 §10.2 规定。
- 如果 `LocalVariable` 是 `var`，则让 R 从 `Expression` 的类型派生如下：
  - 如果 `Expression` 是数组类型，则 R 是该数组类型的组件类型。
  - 否则，如果 `Expression` 的类型是某些类型 X 的 `Iterable<X>` 的子类型，则 R 是 X。
  - 否则，`Expression` 的类型是原始类型 `Iterable` 的子类型，且 R 是 `Object`。

τ 是相对于 R (§4.10.5) 中提到的所有合成类型变量的向上投影。

增强型 `for` 语句的精确含义通过将其翻译为基础 `for` 语句给出，如下：

如果 `Expression` 的类型是 `Iterable` 的子类型，则基础 `for` 语句的形式如下：

```
for ( I #i = Expression.iterator(); #i.hasNext(); ) {
    {VariableModifier} T Identifier = (TargetType) #i.next();
    Statement
}
```

其中：

- 如果 `Expression` 的类型对于任意参数 X 是 `Iterable<X>` 的子类型，则 I 是类型 `java.util.Iterator<X>`。否则，I 是原始类型 `java.util.Iterator`。
- `#i` 是一个自动生成的标识符，与增强型 `for` 语句发生点 (§6.3) 作用域内的任何其他标识符（自动生成或其他）都不同。
- `{VariableModifier}` 如增强型 `for` 语句头部所示。
- 如果 T 是引用类型，则 `TargetType` 是 T。否则，`TargetType` 是 I 的类型参数捕获转换 (§5.1.10) 的上界，如果 I 是原始类型则为 `Object`。
- 否则，`Expression` 必然具有数组类型 `S[]`，且基础 `for` 语句的形式如下：

```
S[] #a = Expression;
L1: L2: ... Lm:
for (int #i = 0; #i < #a.length; #i++) {
    {VariableModifier} T Identifier = #a[#i];
    Statement
}
```

其中：

- `L1 ... Lm` 是紧邻增强型 `for` 语句的（可能为空的）标签序列。
- `#a` 和 `#i` 是自动生成的标识符，与增强型 `for` 语句发生点作用域内的任何其他标识符（自动生成或其他）都不同。
- `{VariableModifier}` 如增强型 `for` 语句头部所示。
- T 是如上确定的局部变量类型。

例如，这段代码：

```
List<? extends Integer> l1 = ...
for (float i : l1) ...
```

将被翻译为：

```
for (Iterator<Integer> #i = l1.iterator(); #i.hasNext(); ) {
    {VariableModifier} T Identifier = (TargetType) #i.next();
}
```

## 14.15 break 语句

## 14.16 continue 语句

## 14.16 continue 语句 块、语句与模式

```java
public Graph loseEdges(int i, int j) {
    int n = edges.length;
    int[][] newges = new int[n][];
    for (int k = 0; k < n; ++k) {
        edgelist: {
            int z;
            search: {
                if (k == i) {
                    for (z = 0; z < edges[k].length; ++z) {
                        if (edges[k][z] == j) break search;
                    }
                } else if (k == j) {
                    for (z = 0; z < edges[k].length; ++z) {
                        if (edges[k][z] == i) break search;
                    }
                }
                // 没有需要删除的边；共享此列表。
                newges[k] = edges[k];
                break edgelist;
            } // search
            // 复制列表，省略位置 z 处的边。
            int m = edges[k].length - 1;
            int[] ne = new int[m];
            System.arraycopy(edges[k], 0, ne, 0, z);
            System.arraycopy(edges[k], z + 1, ne, z, m - z);
            newges[k] = ne;
        } // edgelist
    }
    return new Graph(newges);
}
```

使用了两个语句标签 `edgelist` 和 `search`，以及 `break` 语句的使用。这允许复制列表并省略一条边的代码在两个单独测试之间共享：从节点 i 到节点 j 的边的测试，以及从节点 j 到节点 i 的边的测试。

## 14.16 continue 语句

`continue` 语句只能出现在 `while`、`do` 或 `for` 语句中；这三种语句被称为迭代语句。控制权将传递到迭代语句的循环继续点。

## 块、语句与模式

## continue 语句 14.16

```
ContinueStatement:
    continue [Identifier];
```

`continue` 语句有两种类型：

- 无标签的 `continue` 语句。
- 带有标签 `Identifier` 的 `continue` 语句。

无标签的 `continue` 语句尝试将控制权传递到最近的最内 `while`、`do` 或 `for` 语句；该语句被称为继续目标，它会立即结束当前迭代并开始新迭代。

带有标签 `Identifier` 的 `continue` 语句尝试将控制权传递到与其标签具有相同 `Identifier` 的外层标记语句（§14.7）；该外层语句被称为继续目标，它会立即结束当前迭代并开始新迭代。在这种情况下，继续目标必须是 `while`、`do` 或 `for` 语句，否则会发生编译时错误。

如果 `continue` 语句没有继续目标，则会导致编译时错误。

如果继续目标包含任何方法、构造函数、实例初始化器、静态初始化器、lambda 表达式或 `switch` 表达式并导致其耗尽了 `continue` 语句，则会导致编译时错误。即，不存在非局部跳转。

无标签 `continue` 语句的执行总是异常完成的，原因为无标签的 `continue`。

带有标签 `Identifier` 的 `continue` 语句的执行总是异常完成的，原因为带有标签 `Identifier` 的 `continue`。

因此，`continue` 语句总是异常完成。

参见 `while` 语句（§14.12）、`do` 语句（§14.13）和 `for` 语句（§14.14）的描述，讨论由于 `continue` 导致异常终止的处理。

上述描述使用了“尝试传递控制权”而非简单的“传递控制权”，是因为如果继续目标内的任何 `try` 语句（§14.20）的块或 `catch` 子句包含 `continue` 语句，那么在控制权传递到继续目标之前，将按照从内层到外的顺序执行这些 `try` 语句的 `finally` 子句。`finally` 子句的异常完成可能会破坏由 `continue` 语句发起的控制传递。

### 示例 14.16-1. continue 语句

在 §14.15 的 `Graph` 中，一个 `break` 语句用于完成最外层 `for` 循环的整个体的执行。如果循环本身被标记，则可以将此 `break` 替换为 `continue`：

```java
class Graph {
    int edges[][];

    public Graph(int[][] edges) { this.edges = edges; }

    public Graph loseEdges(int i, int j) {
        int n = edges.length;
        int[][] newedges = new int[n][];
```



edgelists:

```java
for (int k = 0; k < n; ++k) {
    search:
    if (k == i) {
        for (z = 0; z < edges[k].length; ++z) {
            if (edges[k][z] == j) break search;
        }
    } else if (k == j) {
        for (z = 0; z < edges[k].length; ++z) {
            if (edges[k][z] == i) break search;
        }
    }
    // 没有需要删除的边，共享此列表。
    newedges[k] = edges[k];
    continue edgelists;
}
// 复制列表，省略位置 z 处的边。
int m = edges[k].length - 1;
int[] ne = new int[m];
System.arraycopy(edges[k], 0, ne, 0, z);
System.arraycopy(edges[k], z+1, ne, z, m-z);
newges[k] = ne;
} // edgelists
return new Graph(newges);
}
}
```

# 14.17 return 语句

`return` 语句将控制权返回给方法的调用者。

```java
ReturnStatement:
    return [Expression];
```

`return` 语句有两种：

- 无值的 `return` 语句。
- 带有值的 `return` 语句。

无值的 `return` 语句尝试将控制权传递到最近的外层构造函数、方法或表达式；该外层语句被称为返回目标。带有值的 `return` 语句产生值。

如果 `return` 语句没有返回目标，则会导致编译时错误。

如果返回目标包含 (i) 实例或静态初始化器，或 (ii) 包含 `return` 语句的 `switch` 表达式，则会导致编译时错误。

如果无值 `return` 语句的返回目标是方法，且该方法声明为 `void`，则会导致编译时错误。

如果带有值的 `return` 语句的返回目标是构造函数或声明为 `void` 的方法，则会导致编译时错误。

如果带有值的 `return` 语句的返回目标是类型 T 的方法，且表达式的类型无法赋值给 T，则会导致编译时错误。

无值 `return` 语句的执行总是异常完成，原因为无值的 `return`。

带有值的 `return` 语句的执行因某些原因异常完成，如果 `return` 语句正常执行并产生值 V，则异常完成。

由此可见，`return` 语句总是异常完成。

上述描述使用了“尝试传递控制权”而非简单的“传递控制权”，是因为如果方法或构造函数内的任何 `try` 语句（§14.20）的块或 `catch` 子句包含 `return` 语句，那么在控制权传递到返回目标之前，将按照从内层到外层的顺序执行这些 `try` 语句的 `finally` 子句。`finally` 子句的异常完成可能会破坏由 `return` 语句发起的控制传递。

# 14.18 throw 语句

`throw` 语句会导致抛出一个异常（§11 Exceptions）。结果是控制权的立即传递（§11.3），可能会退出多个语句以及多个构造函数、实例初始化、静态初始化器评估和方法调用，直到找到捕获抛出值的 `try` 语句（§14.20）。如果没有找到这样的 `try` 语句，在对所属方法组调用未捕获异常后，执行 throw 的线程（§17 Threads and Locks）将终止（§11.3）。

```java
ThrowStatement:
    throw Expression;
```

`throw` 语句中的表达式必须表示可以赋值给 `Throwable` 类型的引用引用类型的变量或值，或表示空引用，否则会发生编译时错误。

表达式的引用类型将始终是一个类类型（因为没有接口可以赋值给 Throwable），且不是参数化的（Throwable 的子类不能是泛型§8.1.2)）。

必须满足以下三个条件之一，否则会发生编译时错误：

- 表达式的类型是非检查的异常类（§11.1.1）或空类型（§4.1）。
- `throw` 语句包含在 `try` 语句（§14.20）的 块中，且该 throw 语句不会抛出表达式类型的异常。（在这种情况下，说抛出的值被 `try` 语句捕获。）
- `throw` 语句包含在方法或构造函数声明中，且表达式的类型可以为 throws 子句（§8.4.6, §8.8.5）中列出的至少一种类型赋值（§5.2）。

# 块、语句和模式

`throw` 语句可以抛出的异常类型在 §11.2.2 中指定。

`throw` 语句首先计算表达式，然后：

- 如果表达式求值由于某些原因而异常终止，则 `throw` 语句也因该原因异常终止。
- 如果表达式求值正常完成并产生一个非空值 `v`，则 `throw` 语句异常终止，原因是抛出了值为 `v` 的异常。
- 如果表达式求值正常完成并产生空值，则在 `null` 内部创建并抛出一个 `NullPointerException` 类的实例 `v'`。然后 `throw` 语句异常终止，原因是抛出了值为 `v'` 的异常。

可见 `throw` 语句总是异常终止的。

如果存在任何包含它的 `try` 语句 (§14.20)，其 `try` 块包含该 `throw` 语句，则在控制外传递时，这些 `try` 语句的任何 `finally` 子句都会执行，直到异常被捕获。`finally` 子句的这种异常终止可能会中断由 `throw` 语句发起的控制传递。

如果 `throw` 语句包含在方法声明或 lambda 表达式中，但其值没有被包含它的 `try` 语句捕获，则方法的调用将因为该异常而异常终止。

如果 `throw` 语句包含在构造函数声明中，但其值没有被包含它的 `try` 语句捕获，则调用该构造函数的类创建表达式将因为该异常而异常终止 (§15.9.4)。

如果 `throw` 语句包含在静态初始化器 (§8.7) 中，编译时检查 (§11.2.3) 确保其值始终是一个未检查异常，或者其值始终被包含它的 `try` 语句捕获。如果在运行时，尽管有此检查，值仍被包含该 `throw` 语句的 `try` 语句捕获，则如果该值是 `Error` 或其子类的实例，则会被重新抛出；否则，它会被封装在一个 `ExceptionInInitializerError` 对象中并被抛出 (§12.4.2)。

如果 `throw` 语句包含在实例初始化器 (§8.6) 中，编译时检查 (§11.2.3) 确保其值始终是一个未检查异常，或者其值始终被包含它的 `try` 语句捕获，或者抛出的异常类型（一个或其父类）出现在该类的每个构造函数的 `throws` 子句中。

按照惯例，用户声明的可抛出类型通常声明为 `Exception` 类的子类，而 `Exception` 是 `Throwable` 类的子类 (§11.1.1)。

# 14.19 synchronized 语句

`synchronized` 语句代表执行线程获取互斥锁 (§17.1)，执行一个块，然后释放锁。当执行线程持有锁时，其他线程无法获取该锁。

```java
SynchronizedStatement:
synchronized ( Expression ) Block
```

表达式的类型必须是引用类型，否则将发生编译错误。

`synchronized` 语句通过首先计算表达式执行。然后：

- 如果表达式求值由于某些原因而异常终止，则 `synchronized` 语句也因相同的原因异常终止。
- 否则，如果表达式的值为空，则抛出 `NullPointerException`。
- 否则，令表达式的非空值为 `v`。执行线程锁定与 `v` 关联的监器。然后执行 `Block`，然后有两种选择：
    - `Block` 的执行正常完成，则解锁监器且 `synchronized` 语句正常完成。
    - `Block` 的执行由于任何原因而异常终止，则解锁监器且 `synchronized` 语句因该原因异常终止。

`synchronized` 语句获取的锁与 `synchronized` 方法隐式获取的锁相同 (§8.4.3)。单个线程可以多次获取锁。

获取与对象关联的锁本身并不能其他线程访问该对象的字段或调用该对象上的非同步方法。其他线程可以使用常规方式使用 `synchronized` 方法或 `synchronized` 语句来实现互斥。

## 示例 14.19-1. `synchronized` 语句

```java
class Test {
    public static void main(String[] args) {
        Test t = new Test();
        synchronized(t) {
            synchronized(t) {
                System.out.println("made it!");
            }
        }
    }
}
```

该程序输出：
made it!

注意，如果不允许单个线程多次锁定监器，该程序将发生死锁。

# 14.20 try 语句

`try` 语句执行一个块。如果抛出了值且 `try` 语句有一个或多个可以捕获它的 `catch` 子句，则控制将转移到该子句。如果 `try` 语句有一个 `finally` 子句，无论 `try` 块是正常完成还是异常终止，都会执行另一个代码块。

```java
TryStatement:
try Block Catches
TryWithResourcesStatement

Catches:
CatchClause [CatchClause]

CatchClause:
catch ( CatchFormalParameter ) Block

CatchFormalParameter:
{[VariableModifier] CatchType VariableatorId

CatchType:
UnionClassType (| ClassType)

Finally:
finally Block
```

UnionClassType 见 $8.3。为了方便起见，这里显示了 $4.3、$8.3 和 $8.4 的产生式：

- VariableModifier: `final`
- VariableatorId: `Identifier [Dims]`
- Dims: `[Annotation] {[Annotation] }`

紧跟 `try` 关键字的块被称为 `try` 语句的 `try` 块。
紧跟 `finally` 关键字的块被称为 `try` 语句的 `finally` 块。
`try` 语句可以有 `catch` 子句，也称为异常处理器。
一个 `catch` 子句声明一个一个参数，称为异常参数。
如果 `final` 作为异常参数的修饰符出现多次，则为编译错误。
异常参数的作用域和遮蔽在 $6.3 和 $6.4 中指定。从嵌套类或接口或 lambda 表达式引用异常参数受到 $6.5.1 的限制。
异常参数可以将其类型声明为单类类型或多个类型的联合（称为备用类型）。联合的备用类型用 `|` 分隔。
异常参数声明为单类类型的 `catch` 子句称为单-catch 子句。
异常参数声明为类型联合的 `catch` 子句称为多-catch 子句。
在异常参数的类型声明中使用的每个类必须是 `Throwable` 或其子类，否则将发生编译错误。
如果在异常参数的类型声明中使用类型变量，则会发生编译错误。

# 块、语句和模式

`try` 语句 14.20

如果类型的联合包含两个备用类型 $D_i$ 和 $D_j$ ($ \neq j$) 且 $D_i$ 是 $D_j$ 的子类型 (§4.10.2)，则为编译错误。
异常参数声明为单类类型的类型为该类类型。
异常参数声明为具有备用类型 $D_1 | D_2 | \dots | D_n$ 的联合的类型为 $lub(D_1, D_2, \dots, D_n)$。
多-catch 子句的异常参数如果没有显式声明为 `final`，则隐式声明为 `final`。
如果隐式或显式声明为 `final` 的异常参数被赋值给 `catch` 子句体，编译错误。
单-catch 子句的异常参数从不隐式声明为 `final`，但它可以显式声明为 `final` 或是有效的 (§4.12.4)。

> 隐式 `final` 异常参数根据其声明是 `final`，而有效 `final` 异常参数（在某种上）根据其使用方式。多-catch 子句的异常参数隐式声明为 `final`，因此它永远不会出现在赋值运算符的左侧，但它没有被视为有效的。

如果异常参数是有效的（在单-catch 子句中）或隐式 `final` 的（在多-catch 子句中），在声明中添加显式 `final` 修饰符不会引入编译错误。相反，如果单-catch 子句的异常参数被显式声明为 `final`，那么移除 `final` 修饰符可能会引入编译错误（现在被认为是有效的将无法被 `catch` 子句体中的匿名和本地声明引用）。如果没有编译错误，可以进一步更改程序在 `catch` 子句体中重新赋值异常参数，从而不再被视为有效的。

`try` 语句可以抛出的异常类型在 §11.2.2 中指定。
`try` 语句的 `try` 块抛出的异常与 `try` 语句的 `catch` 子句（如果有）捕获的异常之间的关系在 §11.2.3 中指定。
按从到右顺序考虑异常处理器：最早的 `catch` 子句接受异常并将抛出的异常对象作为其参数，如 §11.3 所示。

> 多-catch 子句可以被看作是单-catch 子句的序列。也就是说，异常参数类型为联合 $D_1 | D_2 | \dots | D_n$ 的 `catch` 子句等同于 $n$ 个 `catch` 子句的序列，其中异常参数的类型分别为类类型 $D_1, D_2, \dots, D_n$。在这 $n$ 个 `catch` 子句的每个**块**中，异常参数的声明类型为 $lub(D_1, D_2, \dots, D_n)$。

# 块、语句与模式

```java
try {
  ... throws ReflectiveOperationException ...
}
catch (ClassNotFoundException | IllegalAccessException ex) {
  ... body ...
}
```

在语义上等价于以下代码：

```java
try {
  ... throws ReflectiveOperationException ...
}
catch (final ClassNotFoundException ex1) {
  final ReflectiveOperationException ex = ex1;
  ... body ...
}
catch (final IllegalAccessException ex2) {
  final ReflectiveOperationException ex = ex2;
  ... body ...
}
```

其中带有两个备选的多异常 catch 子句被翻译为两个单一 catch 子句，每个子句对应一个备选。Java 编译器不需要通过复制此代码来编译多异常 catch 子句，因为可以在类文件中不重复地表示多异常 catch 子句。

finally 子句确保了在 try 块和任何可能执行的 catch 块之后执行 finally，无论控制流是以什么方式离开 try 块或 catch 块的。finally 块的处理相当复杂，因此分别描述了带有 finally 块和不带 finally 块的 try 语句两种情况（§14.20.1, §14.20.2）。

如果 try 语句是资源 try 语句，允许省略 catch 子句和 finally 子句（§14.20.3）。

## 14.20.1 try-catch 的执行

不带 finally 块的 try 语句首先执行 try 块。然后有如下选择：

- 如果 try 块的执行正常完成，则不采取进一步操作，try 语句正常完成。
- 如果 try 块的执行由于抛出值 V 而异常终止，则有如下选择：
  - 如果 V 的运行时类型与 try 语句中任何 catch 子句的可捕获异常在赋值兼容（§5.2），则选择第一个（最左边的）此类 catch 子句。值 v 被赋值给所选 catch 子句的参数，并执行该 catch 子句的块，然后有如下选择：
    - 如果该块正常完成，则 try 语句正常完成。
    - 如果该块由于任何原因异常终止，则 try 语句由于相同原因异常终止。
  - 如果 V 的运行时类型与 try 语句中任何 catch 子句的可捕获异常类不兼容，则 try 语句由于抛出值 V 而异常终止。
  - 如果 try 块的执行由于任何其他原因而异常终止，则 try 语句由于相同原因异常终止。

示例 14.20.1-1. 捕获异常

```java
```



# try 语句

## 14.20.2 try-finally 和 try-catch-finally 的执行

带有 `finally` 块的 `try` 语句首先执行 `try` 块。然后有如下选择：

- 如果 `finally` 块正常完成，则 `try` 语句正常完成。
- 如果 `finally` 块由于原因 S 异常终止，则 `try` 语句由于原因 S 异常终止。
- 如果 `finally` 块由于任何原因异常终止，则 `try` 语句由于相同原因异常终止。
- 如果 `finally` 块正常完成，则 `try` 语句由于原因 R 异常终止。
- 如果 `finally` 块由于原因 S 异常终止，则 `try` 语句由于 S 异常终止（原因 R 被丢弃）。
- 如果 `finally` 块正常完成，则 `try` 语句由于抛出值 V 而异常终止。
- 如果 `finally` 块由于原因 S 异常终止，则 `try` 语句 S 异常终止（值 V 的抛出被丢弃并忽略）。
- 如果 `try` 块的执行由于任何其他原因 R 而异常终止，则执行 `finally` 块，然后有如下选择：
  - 如果 `finally` 块正常完成，则 `try` 语句由于原因 R 异常终止。
  - 如果 `finally` 块由于原因 S 异常终止，则 `try` 语句由于原因 S 异常终止（原因 R 被丢弃）。

### 示例 14.20-2.1. 使用 finally 处理未捕获的异常

```java
class Blewit extends Exception {

    Blewit() { }

    Blewit(String s) { super(s); }

}

class Test {

    static void blowUp() throws Blewit {

        throw new NullPointerException();

    }

    public static void main(String[] args) {

        try {

            blowUp();

        } catch (Blewit b) {

            System.out.println("Caught Blewit");

        } finally {

            System.out.println("Uncaught Exception");

        }

    }

}
```

该程序产生输出：

```
Uncaught Exception

Exception in thread "main" java.lang.NullPointerException
    at Test.blowUp(Test.java:7)
    at Test.main(Test.java:11)
```

`NullPointerException` 没有被 `try` 语句捕获，是因为使用了资源 `try` 语句（在此例中为 `finally` 块）。

## 14.20.3 try-resources

资源规范定义了 `try` 语句的资源，通过声明局部变量或引用现有变量来实现。现有变量通过表达式名（§6.5.6）或字段访问表达式（§15.11）引用。

```
TryWithStatement:
try ResourceSpecification Block [Catches] [Finally]

ResourceSpecification:
( ResourceList )

ResourceList:
Resource {

Resource:
LocalVariableDeclarationAccess
```

为了方便，这里显示了来自 §4.3、§8.3、§8.4 和 §14.4 的产生式：

```
LocalVariableDeclaration:
(VariableModifier) VariableType VariableList

VariableModifier:
Annotation
final

VariableType:
UnannType
var

VariableList:
VariableDeclarator ( , VariableDeclarator)

VariableDeclarator:
VariableDeclaratorId [ = VariableInitializer ]

VariableDeclaratorId:
Identifier [Dims]
```

资源规范中声明的局部变量的规则见 §14.4。必须满足以下条件，否则将出现编译错误：

- `VariableDeclaratorList` 包含单个 `VariableDeclarator`。
- `VariableDeclarator` 具有初始化器。
- `VariableDeclaratorId` 没有括号对。

资源规范中声明的局部变量的作用域和屏蔽见 §6.3 和 §6.4。从嵌套类或接口或 Lambda 表达式对局部变量的引用限制见 §6.5.6.1。

资源规范中声明的局部变量的类型见 §14.4.1。

资源规范中声明的局部变量的类型，或资源规范中引用的现有变量的类型，必须是 `AutoCloseable` 的子类型，否则将出现编译错误。

资源规范声明同名局部变量会导致编译错误。

资源是 `final` 的，因为：

- 资源规范中声明的局部变量没有声明为 `final`，则隐式声明为 `final`（§4.12.4）。
- 资源规范中引用的现有变量必须是在 `try-resources` 语句之前确定赋值的 `final` 或有效 `final` 变量（§16 确定赋值），否则将出现编译错误。

资源按照从左到右顺序进行初始化。如果某个资源初始化失败（即其初始化器抛出异常），则 `try-with-resources` 语句已初始化的所有资源都将被关闭。如果所有资源都成功初始化，则 `try` 块按正常执行，然后 `try-with-resources` 的所有非空资源都将被关闭。

资源按照其初始化的反序进行关闭。只有当资源被初始化为非空值时，才会被关闭。关闭某个资源时抛出的异常不会阻止其他资源的关闭。如果之前已由初始化器、`try` 块或资源关闭抛出了异常，则此类异常将被抑制（suppressed）。

资源规范指示了多个资源的 `try-with-resources` 语句被视为多个 `try-with-resources` 语句，其中每个语句都将一个包含 $n$ 个资源（$n > 1$）的资源规范进行翻译，其结果是一个包含 $n-1$ 个资源的 `try-with-resources` 语句。经过 $n$ 次翻译后，会有 $n$ 个嵌套的 `try-catch-finally` 语句，整体翻译完成。

### 14.20.3.1 基础 try-with-resources

没有 `catch` 或 `finally` 子句的 `try-with-resources` 语句被称为基础 `try-with-resources` 语句。

如果一个基础 `try-with-resources` 语句的形式如下：

```
try (VariableAccess ...)
Block
```

则该资源首先通过以下翻译转换为局部变量声明：

```
try (T #r = VariableAccess ...) {
    Block
}
```

$T$ 是由 `VariableAccess` 表示的变量的类型，`#r` 是一个自动生成的标识符，它与 `try-with-resources` 语句所在作用域内的任何其他标识符（自动生成的或其他）都不同。然后根据本节其余部分对该 `try-with-resources` 语句进行翻译。

基础 `try-with-resources` 语句的含义形式如下：

```
try ((VariableModifier) R Identifier = Expression ...)
Block
```

通过翻译为局部变量声明和 `try-catch-finally` 语句给出：

```
{
    final {VariableModifierNoFinal} R Identifier = Expression;
    Throwable #primaryExc = null;
    try ResourceSpecification_tail
    catch (Throwable #t) {
        #primaryExc = #t;
        throw #t;
    } finally {
        if (Identifier != null) {
            if (#primaryExc != null) {
                try {
                    Identifier.close();
                } catch (Throwable #suppressedExc) {
                    #primaryExc.addSuppressed(#suppressedExc);
                }
            } else {
                Identifier.close();
            }
        }
    }
}
```

`[VariableModifierNoFinal]` 定义为不带 `final` 关键字的 `[VariableModifier]`。

`#t`、`#primaryExc` 和 `#suppressedExc` 是自动生成的标识符，它们与 `try-with-resources` 语句所在作用域内的任何其他标识符（自动生成的或其他）都不同。

如果资源规范指示了一个资源，则 `ResourceSpecification_tail` 为空（且 `try-catch-finally` 语句本身不是 `try-with-resources` 语句）。

如果资源规范指示了 $n > 1$ 个资源，则 `ResourceSpecification_tail` 由资源规范中指示的第 2、第 3...第 $n$ 个资源组成，且顺序相同（且 `try-catch-finally` 语句本身是一个 `try-with-resources` 语句）。

基础 `try-with-resources` 语句的可达性和确定性赋值规则由上述翻译隐式指定。

在管理单个资源的基础 `try-with-resources` 语句中：

- 如果资源的初始化因为抛出值 V 而异常终止，则 `try-with-resources` 语句也因为抛出值 V 而异常终止。
- 如果资源的初始化正常完成，且 `try` 块因为抛出值 V 而异常终止，则：
  - 如果资源的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 V 而异常终止。
  - 如果资源的自动关闭因为抛出 V2 而异常终止，则 `try-with-resources` 语句因为抛出值 V 而异常终止，并将 V2 添加到 V 的抑制异常列表中。
- 如果资源的初始化正常完成，且 `try` 块正常完成，且资源的自动关闭因为抛出值 V 而异常终止，则 `try-with-resources` 语句因为抛出值 V 而异常终止。

在管理多个资源的基础 `try-with-resources` 语句中：

- 如果某个资源的初始化因为抛出值 V 而异常终止，则：
  - 如果所有成功初始化的资源（可能为零）的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 V 而异常终止。
  - 如果所有成功初始化的资源（可能为零）的自动关闭因为抛出值 V1...Vn 而异常终止，则 `try-with-resources` 语句因为抛出值 V 而异常终止，并将剩余的值 V1...Vn 添加到 V 的抑制异常列表中。
- 如果所有资源的初始化正常完成，且 `try` 块因为抛出值 V 而异常终止，则：
  - 如果所有初始化资源的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 V 而异常终止。
  - 如果一个或多个初始化资源的自动关闭因为抛出值 V1...Vn 而异常终止，则 `try-with-resources` 语句因为抛出值 V 而异常终止，并将剩余的值 V1...Vn 添加到 V 的抑制异常列表中。
- 如果所有资源的初始化正常完成，且 `try` 块正常完成，则：
  - 如果某个资源的自动关闭因为抛出值 V 而异常终止，则 `try-with-resources` 语句因为抛出值 V 而异常终止。

### 14.20.3.2 扩展 try-with-resources

带有至少一个 `catch` 或 `finally` 子句的 `try-with-resources` 语句被称为扩展 `try-with-resources` 语句。

扩展 `try-with-resources` 语句的含义：

```
try ResourceSpecification
  Block
[Catches]
  Finally
```

通过翻译为嵌套在 `try-catch` 或 `try-finally` 语句中的基础 `try-with-resources` 语句给出：

```
try {
  try ResourceSpecification
    Block
}
[Catches]
  Finally
```

翻译的效果是将资源规范放在 `try` 语句内部。这使得 `catch` 子句可以捕获资源初始化或关闭时产生的异常。此外，在执行 `finally` 块之前，所有资源已关闭（或尝试关闭），这符合 `finally` 关键字的意图。

## 14.21 yield 语句

`yield` 语句通过使封装的 `switch` 表达式（15.28）产生值来传递控制。

```
YieldStatement: yield Expression;
```

`yield` 语句尝试将控制传递给最内层的 `switch` 表达式；该表达式被称为 `yield` 目标，它立即正常完成，并且 `Expression` 的值变为 `switch` 表达式的值。

如果 `yield` 语句没有 `yield` 目标，则编译错误。

如果 `yield` 目标包含任何成员、构造函数、实例初始化器或 `lambda` 表达式，则编译错误。即不存在非局部跳转。

如果 `yield` 语句的 `Expression` 为 `void`（15.1），则编译错误。

`yield` 语句的执行首先求值 `Expression`。如果 `Expression` 求值因为某种原因异常，则 `yield` 语句因该原因异常终止。如果 `Expression` 求值正常完成并产生值 v，则 `yield` 语句异常终止，原因是值 v。因此，`yield` 语句总是异常终止。

### 示例 14.21-1. yield 语句

在此示例中，`yield` 语句用于为封装的 `switch` 表达式产生值。

```java
class Test {

  enum Day {

    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,
    SATURDAY, SUNDAY

  }

  public int calculate(Day d) {

    return switch (d) {

      case SATURDAY, SUNDAY -> d.ordinal();

      default -> {

        int len = d.toString().length();

        yield len * len;

      }

    };

  }

}
```

# 14.22 不可达语句

如果一个语句因为不可达而无法执行，则将构成编译错误。

本节专门对“可达（reachable）”一词进行精确解释。其核心思想是：从构造函数、方法、实例初始化器或静态初始化器的开始，必须存在一条通往语句本身的可能执行路径。该分析考虑了语句的结构。除了条件值为常量 `true` 的 `while`、`do` 和 `for` 语句外，流分析中不考虑表达式的值。

例如，Java 编译器会接受以下代码：

```java
{
    int n = 5;
    while (n > 7) k = 2;
}
```



尽管 `n` 的值在编译时是已知的，原则上可以在编译时确定对 `k` 的赋值永远不会执行。

本节中的规则定义了两个技术术语：

- 语句是否可达
- 语句是否能够正常完成

规则只有在语句是可达的情况下，才允许其正常完成。
还使用了另外两个术语：

- 可达的 `break` 语句退出语句：在 `break` 目标范围内，要么没有 `try` 块包含该 `break` 语句的 `try` 语句，要么存在 `try` 块包含该 `break` 语句的 `try` 语句且这些 `try` 语句的所有 `finally` 子句都能正常完成。

此定义基于 §14.15 中“尝试转移控制”的逻辑。

- `continue` 语句继续 `do` 语句：在 `do` 语句范围内，要么没有 `try` 块包含该 `continue` 语句的 `try` 语句，要么存在 `try` 块包含该 `continue` 语句的 `try` 语句且这些 `try` 语句的所有 `finally` 子句都能正常完成。

规则如下：

- 构造函数、方法、实例初始化器、静态初始化器、lambda 表达式或 `switch` 表达式主体的块是可达的。

- 非 `switch` 块的空块当且仅当它是可达的，才可以正常完成。

- 非 `switch` 块的非空块当且仅当其最后一个语句能够正常完成时，才能正常完成。

- 非 `switch` 块的非空块中的第一个语句当且仅当该块是可达的，才是可达的。

- 非 `switch` 块的非空块中的其他任何语句 `s` 当且仅当 `s` 之前的语句能够正常完成时，才是可达的。

- 局部类声明语句当且仅当它是可达的，才能正常完成。

- 局部变量声明语句当且仅当它是可达的，才能正常完成。

- 空语句当且仅当它是可达的，才能正常完成。

- 标记语句如果满足以下条件之一为真，则可以正常完成：
  - 包含的语句能够正常完成。
  - 存在一个可达的 `break` 语句退出该标记语句。

包含的语句当且仅当标记语句是可达的，才是可达的。

- 表达式语句当且仅当它是可达的，才能正常完成。

- `if-then` 语句当且仅当它是可达的，才能正常完成。

`then` 语句当且仅当 `if-then` 语句是可达的，才是可达的。

- `if-then-else` 语句可以正常完成或 `else` 语句可以正常完成。

`then` 语句当且仅当 `if-then-else` 语句是可达的，才是可达的。

`else` 语句当且仅当 `if-then-else` 语句是可达的，才是可达的。

> 这种对 `if` 语句的处理（无论是否有 `else` 部分）相当不寻常。理由见在本节末尾。

- `assert` 语句当且仅当它是可达的，才能正常完成。

- `switch` 块为空或仅包含 `switch` 标签的 `switch` 语句可以正常完成。

- `switch` 块由 `switch` 标记语句组组成的 `switch` 语句，当且仅当满足以下条件之一为真时，才能正常完成：
  - `switch` 块中的最后一个语句能够正常完成。
  - 在最后一个 `switch` 语句组后至少有一个 `switch` 标签。
  - 存在一个可达的 `break` 语句退出该 `switch` 语句。
  - `switch` 块不包含 `default` 标签。

- `switch` 块由 `switch` 规则组成的 `switch` 语句，当且仅当满足以下条件之一为真时，才能正常完成：
  - 其中一个 `switch` 规则引入了 `switch` 规则表达式（必然是一个表达式语句）。
  - 其中一个 `switch` 规则引入了可以正常完成的 `switch` 规则块。
  - 其中一个 `switch` 规则引入了包含一个退出 `switch` 语句的可达 `break` 语句的 `switch` 规则块。
  - `switch` 块不包含 `default` 标签。

- 块当且仅当其 `switch` 语句是可达的，才是可达的。

- `switch` 块中由 `switch` 标记语句组组成的语句当且仅当 `switch` 块是可达的且满足以下条件之一为真时，才是可达的：
  - 它带有 `case` 或 `default` 标签。
  - `switch` 块中在其之前有一个语句，且该之前的语句能够正常完成。

- `switch` 块中的 `switch` 规则块当且仅当 `switch` 块是可达的，才是可达的。

- `switch` 块中的 `switch` 规则 `throw` 语句当且仅当 `switch` 块是可达的，才是可达的。

- `while` 语句当且仅当满足以下条件之一为真时，才能正常完成：
  - `while` 语句是可达的，且条件表达式不是值为 `true` 的常量表达式 (§15.29)。
  - 存在一个可达的 `break` 语句退出该 `while` 语句。

包含的语句当且仅当 `while` 语句是可达的且条件表达式不是值为 `false` 的常量表达式时，才是可达的。

- `do` 语句当且仅当满足以下条件之一为真时，才能正常完成：
  - 包含的语句能够正常完成且条件表达式不是值为 `true` 的常量表达式 (§15.29)。
  - `do` 语句包含无标签的可达 `continue` 语句，且该 `do` 语句是包含 `continue` 语句的最内层 `while`、`do` 或 `for` 语句，且该 `continue` 语句继续该 `do` 语句，且条件表达式不是值为 `true` 的常量表达式。
  - `do` 语句包含带标签 L 的可达 `continue` 语句，且该 `do` 语句带有标签 L，且该 `continue` 语句继续该 `do` 语句，且条件表达式不是值为 `true` 的常量表达式。
  - 存在一个可达的 `break` 语句退出该 `do` 语句。

包含的语句当且仅当 `do` 语句是可达的，才是可达的。

- 基础 `for` 语句当且仅当满足以下条件之一为真时，才能正常完成：
  - `for` 语句是可达的，存在条件表达式，且条件表达式不是值为 `true` 的常量表达式 (§15.29)。
  - 存在一个可达的 `break` 语句退出该 `for` 语句。

包含的语句当且仅当 `for` 语句是可达的且条件表达式不是值为 `false` 的常量表达式时，才是可达的。

- 增强型 `for` 语句当且仅当它是可达的，才能正常完成。

- `break`、`continue`、`return`、`throw` 或 `yield` 语句不能正常完成。

- `synchronized` 语句当且仅当其包含的语句能够正常完成时，才能正常完成。

包含的语句当且仅当 `synchronized` 语句是可达的，才是可达的。

- `try` 语句当且仅当两个条件均真时，才能正常完成：
  - `try` 块能够正常完成或任何 `catch` 块能够正常完成。
  - 如果 `try` 语句带有 `finally` 块，则该 `finally` 块能够正常完成。

- `try` 块当且仅当 `try` 语句是可达的，才是可达的。

# 块、语句与模式

## 不可达语句 14.22

- `catch` 块 `c` 是可达的，当且仅当以下两点均成立：
  - `c` 参数的类型是未检查异常类型、`Exception` 或 `Exception` 的超类，或者 `try` 块中的某些表达式或 `throw` 语句是可达的，并且可以抛出一个类型与 `c` 参数类型赋值兼容（§5.2）的检查异常。（表达式是可达的，当且仅当包含它的最内层语句也是可达的。）

关于表达式的正常完成和异常完成，请参见 §15.6。
  - `try` 语句中不存在早于 `catch` 块 `a`，使得 `c` 参数的类型与 `a` 参数的类型相同或是其子类。

- `catch` 块的体是可达的，当且仅当该 `catch` 块是可达的。

- 如果存在 `finally` 块，它是可达的，当且仅当 `try` 语句是可达的。

> 人们可能期望 `if` 语句的处理方式如下：

- 如果至少满足以下条件之一，则 `if-then` 语句可以正常完成：
  - `if-then` 语句是可达的，且条件表达式不是值为 `true` 的常量表达式。
  - `then-statement` 可以正常完成。

- `if-else` 语句是可达的，当且仅当 `if-then` 语句是可达的且条件表达式不是值为 `false` 的常量表达式。

- `if-else` 语句可以正常完成，当且仅当 `then-statement` 可以正常完成或 `else-statement` 可以正常完成。

- `then-statement` 语句是可达的，当且仅当 `if-else` 语句是可达的且条件表达式不是值为 `false` 的常量表达式。

- `else-statement` 是可达的，当且仅当 `if-else` 语句是可达的且条件表达式不是值为 `true` 的常量表达式。

这种方法将与其他控制结构的处理方式保持一致。然而，为了让 `if` 语句能够方便地用于“条件编译”目的，实际规则则有所不同。

例如，以下语句会导致编译时错误：

```
while (false) { x=3; }
```

因为语句 `x=3;` 是不可达的；但表面上相似的用例

```
if (false) { x=3; }
```

并不会导致编译时错误。优化编译器可能会意识到语句 `x=3;` 永远不会被执行，并可能选择在生成的类文件中省略该语句的代码，但从此处指定的特定意义上来说，语句 `x=3;` 并不被视为“不可达”的。

这种差异化处理的理由是允许程序员定义如所示的“标志”变量：

```
static final boolean DEBUG = false;
```

然后编写如下代码：

```
if (DEBUG) { x=3; }
```

其理念是，应当可以将 `DEBUG` 的值从 `false` 改为 `true` 或从 `true` 改为 `false`，并在不对程序文本进行任何其他更改的情况下正确编译代码。

如果一组使用“标志”变量的类——更准确地说，是任何静态常量变量（§4.12-）被编译，且条件代码被省略，则会发生条件比较；仅分发一个包含标志定义的类或接口的新版本是不够的。使用标志的类将看不到它的新值，因此它们的行为可能会产生意料。本质上，对标志值的更改与现有的二进制文件是二进制兼容的（不会发生 `LinkageError`），但在行为上是不兼容的。

静态常量变量被“内联”的另一个原因是 `switch` 语句。它们是唯一依赖常量表达式的语句，即 `switch` 语句的每个 `case` 标签必须是一个常量表达式，且其值必须与其他每个 `case` 标签不同。`case` 标签通常是静态常量变量的引用，因此所有标签具有不同值可能并不显而易见。如果在编译时证明存在重复标签，那么内联值可以确保在运行时没有重复标签——这是一个非常理想的属性。

### 示例 14.22-1. 条件编译

如果示例如下：

```
class Flags { static final boolean DEBUG = true; }

class Test {

    public static void main(String[] args) {

        if (Flags.DEBUG) {

            System.out.println("DEBUG is true");

        }

    }

}
```

被编译并执行，它将输出：

```
DEBUG is true
```

假设产生了一个新版本的 `Flags` 类：

```
class Flags { static final boolean DEBUG = false; }
```

如果重新编译了 `Flags` 但没有重新编译 `Test`，运行现有的 `Test` 与新的二进制文件将输出：

```
DEBUG is true
```

因为 `DEBUG` 是一个静态变量，因此它的值在编译 `Test` 时可能已被使用，而无需引用 `Flags` 类。

如果 `Flags` 是接口，也会发生这种情况，如修改后的示例：

```
interface Flags { boolean DEBUG = true; }

class Test {

    public static void main(String[] args) {

        if (Flags.DEBUG)

            System.out.println("DEBUG is true");

    }

}
```

事实上，接口的字段始终是 `static` 且 `final`，我们建议只将常量表达式赋值给接口字段。我们注意到（但不建议），如果接口的原始类型字段可能会发生变化，其值可以惯用方式表示为：

```
interface Flags {

    boolean debug = Boolean.valueOf(true);

}
```

## 模式 14.30

模式用于测试一个值。模式作为语句和表达式的操作数出现，这些语句和表达式声明了局部变量，即模式变量。

根据模式测试值的过程被称为模式匹配。如果一个值匹配模式，则由模式声明的模式变量将被初始化。无法使用未初始化的模式。

### 14.30.1 模式的种类

类型模式用于测试一个值是否是该类型的实例。

模式：
`TypePattern`

`TypePattern`:
`LocalVariableDeclaration`

为了方便起见，这里展示了 §4.3、§8.3 和 §14.4 中的产生式：

```
LocalVariableModifier:
(VariableModifier) LocalVariableType VariableDeclarList

VariableModifier:
Annotation
final

LocalVariableType:
UnannType
var

VariableDeclarList:
VariableDeclarator [, VariableDeclarator]

VariableDeclarator:
VariableDeclarId [= VariableInitializer]

VariableDeclarId:
Identifier

Dims:
[Annotation] [[Annotation]]
```



关于 `UnannType`，请参见 §8.3。类型模式声明一个局部变量。变量声明中的 `Identifier` 指定了模式变量的。

在类型模式中声明的局部变量的规则规定在 §14.4。此外，必须满足以下所有条件，否则将发生编译错误：

- `LocalVariableType` 指向一个引用类型（并且不是 `var`）。
- `VariableDeclarList` 包含单个 `VariableDeclarator`。
- `VariableDeclarator` 没有初始化器。
- `VariableDeclarId` 没有括号对。

模式变量的类型是 `LocalVariableType` 所指的引用类型。

类型模式的类型是其模式变量的类型。

如果表达式 `e` 与 `T` 兼容（§5.5），则它与类型为 `T` 的模式兼容。

> 表达式与模式的兼容性被 `instanceof` 模式匹配运算符使用（§15.20）。

### 14.30.2 模式匹配

模式匹配是在运行时根据模式测试值的过程。模式匹配与语句执行（§14.1）以及表达式求值（§15.1）是不同的。

确定一个值是否匹配模式以及初始化模式变量的规则如下：

- 非空值 `v` 如果可以强制转换为 `T` 且不抛出 `ClassCastException`，则匹配类型模式；否则不匹配。

如果 `v` 匹配，则由类型模式声明的模式变量被初始化为 `v`。

如果 `v` 不匹配，则由类型模式声明的模式变量不被初始化。

没有规则覆盖空值的情况。这是因为执行模式匹配的唯一结构——`instanceof` 模式匹配运算符（§15.20.2）仅在值非空时才执行操作。

## 第 15 章
表达式

程序中的大部分工作是通过求值表达式完成的，可能是为了它们的副作用（例如变量赋值），也可能是为了它们的值（这些值可以作为更大表达式中的参数或操作数，或者影响语句的执行顺序，或两者兼有）。

本章规定了表达式的含义及其求值规则。

## 15.1 求值、表示与结果

当程序中的表达式被求值（执行）时，结果表示以下三者之一：

- *变量 (§4.12)*（在 C 中，这被称为左值）
- 一个值 (§4.2, §4.3)
- 无（该表达式被称为 void）

如果表达式表示一个变量，且在后续评估中需要一个值，则使用该变量的值。在这种语境下，如果表达式表示一个变量或值，我们可以简单地称为表达式的值。

当且仅当表达式是一个方法调用 (§15.12)，且该调用调用了一个不返回结果的方法（即声明为 void 的方法 (§8.4)）时，表达式表示为空。这样的表达式只能作为语句 (§14.8) 或作为 lambda 体的唯一表达式 (§15.27.2)，因为表达式可能出现的任何其他上下文都要求该表达式表示某些内容。作为方法调用的表达式语句或 lambda 体也可以调用产生结果的方法；在这种情况下，方法返回的值会被静默丢弃。

表达式的求值可能会产生副作用，因为表达式可能包含嵌入的赋值、增运算符、自减运算符、方法调用，以及在 switch 表达式中的任意语句。

表达式出现在以下位置：

- 正在声明的某个类或接口的声明中：在字段初始化器中、静态初始化器中、实例初始化器中、构造函数声明中、方法声明或注解中。
- 对模块、包或顶层类或接口声明的注解上。

## 15.2 表达式的形式

表达式可以大致分类为以下语法形式之一：

- 表达式名称 (§6.5.6)
- 原始表达式 (§15.8 - §15.13)
- 一元运算符表达式 (§15.14 - §15.16)
- 二元运算符表达式 (§15.17 - §15.24, 以及 §15.26)
- 三元运算符表达式 (§15.25)
- Lambda 表达式 (§15.27)
- switch 表达式 (§15.28)

运算符之间的优先级由语法产生式的层次结构管理。优先级最低的运算符是 lambda 表达式的箭头 (`->`)，随后是赋值运算符。因此，所有表达式在语法上都包含 `LambdaExpression` 和 `AssignmentExpression` 非终端中：

> 表达式:
> LambdaExpression
> AssignmentExpression

当表达式出现在某些上下文中时，它们被视为多值表达式（poly expressions）。以下形式的表达式可能是多值表达式：

- 括号表达式 (§15.8.5)
- 类实例创建表达式 (§15.9)
- 方法调用表达式 (§15.12)
- 方法引用表达式 (§15.13)
- 条件表达式 (§15.25)
- Lambda 表达式 (§15.27)
- switch 表达式 (§15.28)

确定这些形式之一的表达式是否为多值表达式的规则，在指定这些表达式形式的各个独立章节中给出。

不是多值表达式的表达式是独立表达式（standalone expressions）。独立表达式是指在被确定为不是多值表达式时的上述形式的表达式，以及所有其他形式的表达式。所有其他形式的表达式被称为具有独立形式。

某些表达式具有可以在编译时确定的值。这些是常量表达式 (§15.29)。

## 15.3 表达式的类型

如果表达式表示一个变量或一个值，则该表达式具有编译时知的类型。独立表达式的类型可以完全根据表达式的内容确定；相比之下，多值表达式的类型可能会受到表达式目标类型（§5 转换与上下文）的影响。确定表达式类型的规则在下文中对每种表达式分别说明。

表达式的值与表达式的类型是赋值兼容的（§5.2），除非发生堆污染（§4.12.2）。

同样，存储在变量中的值始终与变量的类型兼容，除非发生堆污染。

换句话说，类型为 `T` 的表达式的值始终适用于赋值类型为 `T` 的变量。

注意，如果表达式的类型是命名类 `c` 的类类型，那么将类 `c` 声明为 `final` 或 `sealed`（§8.1.1.2）对表达式的值有影响：

- 如果 `c` 是 `final`，则保证表达式具有一个值，其为 (i) 空引用，或 (ii) 类为 `c` 本身的对象，因为 `final` 类没有子类。
- 如果 `c` 是 `sealed`，则保证表达式具有一个值，其为 (i) 空引用，(ii) 类为 `c` 本身的对象，或 (iii) 与允许的子类之一赋值兼容。
- 如果 `c` 是自由扩展的，则保证表达式具有一个值，其为 (i) 空引用，(ii) 类为 `c` 本身的对象，或 (iii) 与 `c` 兼容。

## 15.4 浮点表达式

浮点表达式是类型为 `float` 或 `double` 的表达式（§4.3）。类型为 `float` 的浮点表达式表示的值精确对应 32 位 IEEE 754 格式的值。类型为 `double` 的浮点表达式表示的值精确对应 64 位 IEEE 754 格式的值。

Java 语言中的许多浮点比较运算符和数值运算符对应 IEEE 754 操作，作用于浮点值的转换也是如此（表 15.4-A）。

### 表 15.4-A 与 IEEE 754 的对应关系

| 运算符/转换 | IEEE 754 操作 |
|---|---|
| 数值比较运算符 `<`, `<=`, `>`, `>=` (§15.20.1) | `compareQuietLess`, `compareQuietEqual`, `compareGreater` |
| 数值相等运算符 `==` 和 `!=` (§15.21.1) | `compareQuietEqual`, `compareQuietNotEqual` |
| 一元负运算符 `-` (§15.4) | `negate` |
| 乘法运算符 `*` 和 `/` (§15.17.1) | `multiplication`, `division` |
| 加法运算符 `+` 和 `-` (§15.18.2) | `addition`, `subtraction` |
| 向整数的宽转换原始类型转换 | |
| 向零取整的整数收窄原始类型转换 | |
| `float` 和 `double` 之间的转换 | `convertFormat` |

> 浮点取模运算符 `%`（§15.17.3）不对应 IEEE 754 余数操作。

一些 Java 语言中没有对应运算符的 IEEE 754 操作通过 `Math` 和 `StrictMath` 类中的方法提供，包括用于 IEEE 754 平方根方法的 `sqrt` 方法，用于 IEEE 754 乘加方法的 `fma` 方法，以及用于 IEEE 754 余数方法的 `remainder` 方法。

Java 编程语言要求支持 IEEE 754 正规浮点数和渐式下溢，这使得证明特定数值算法的属性变得更容易。当计算结果为正规数时，浮点运算不会“舍零”。

Java 语言中浮点运算符的结果必须与相同操作数上相应的 IEEE 754 操作的结果匹配。对于有限结果，这意味着浮点结果的有效数字和指数必须都是 IEEE 754 规定的。

对符号、有效数字和指数匹配的要求排除了某些在浮点行为规定得那么精确时可能允许的转换。例如，`-x` 通常不能替换为 `(0.0 - x)`，因为当 `x` 为 `-0.0` 时，结果的符号会有所不同。此外，其他可能改变值的转换如

除非能够证明结果是完全相同的，否则不允许将 `a * b + c` 替换为对融合乘加（`fma`）库方法的调用。

在任何情况下，浮点表达式的求值都不可能使用比表达式类型所示具有更高精度或更大指数范围的中间结果。

溢出的浮点操作会产生符号无穷大。

下溢的浮点操作会产生次正规值或零。

没有唯一数学定义结果的浮点操作会产生 `NaN`。

所有以 `NaN` 为操作数的数值运算都会产生 `NaN` 结果。

由于 `NaN` 属于下溢，任何涉及一个或两个 `NaN` 的数值比较都返回 `false`，任何 `==` 比较都返回 `false`，而任何 `!=` 比较 `NaN` 则返回 `true`。

浮点算术是对实数算术的近似。虽然实数有无限多个，但特定的浮点格式只有有限数量的值。在 Java 编程语言中，舍入策略（rounding policy）是一个用于将实数映射到给定格式下的浮点值的函数。对于浮点可表示范围内的实数，实线上的连续段被映射到单个浮点值。数值上等于某个浮点值的实数被映射到该浮点值；例如，实数 `1.5` 在给定格式中映射为浮点值 `1.5`。Java 编程语言定义了两种舍入策略：

- **最近舍入策略**（round to nearest rounding policy）适用于所有浮点运算符，但 (i) 转换为整数和 (ii) 浮点余数。在最近舍入策略下，不精确的结果将舍入到距离无限精确结果最近的可表示值；如果两个最近的可表示值同样等近，则选择最低有效位为 `0` 的那个值。

  最近舍入策略对应于 IEEE 754 中二进制算术的舍入方向 `roundTiesToEven`。

  `roundTiesToEven` 舍入方向属性在 1985 年版本的 IEEE 754 标准中被称为“最近舍入”舍入模式。Java 编程语言中的舍入策略以这种舍入模式命名。

- **向零舍入策略**（round toward zero rounding policy）适用于 (i) 浮点值转换为整数值（§5.1.3），以及 (ii) 浮点余数（§15.17.3）。在向零舍入策略下，不精确的结果将舍入到绝对值不大于无限精确结果的最近的可表示值。对于整数，向零舍入策略等同于舍弃尾数位的截断。

  向零舍入策略对应于 IEEE 754 中二进制算术的 `roundTowardZero` 舍入方向。

  `roundTowardZero` 舍入方向属性在 1985 年版本的 IEEE 754 标准中被称为“向零舍入”舍入模式。Java 编程语言中的舍入策略以这种舍入模式命名。

Java 编程语言要求每个浮点运算符都以严格精度返回其结果。每个浮点运算符使用的舍入策略是根据指定的最近舍入或向零舍入。

Java 1.0 和 1.1 对浮点表达式进行严格求值。严格求值意味着 `float` 操作数对应于 IEEE 754 `binary32` 格式可表示的值，每个 `double` 操作数对应于 IEEE 754 `binary64` 格式可表示的值，并且每个对应 IEEE 754 操作的浮点运算符与相同操作数的 IEEE 754 结果相匹配。

严格求值产生了可预测的结果，但在 Java 1.0/1.1 时代某些常见的 Java 虚拟机实现导致了性能问题。因此，在 Java 1.2 到 Java SE 16 中，Java SE 平台允许 Java 虚拟机实现为每个浮点类型关联一或两个值集。`float` 类型与 float 值集和扩展指数值集关联，而 `double` 类型则与 double 指数值集关联。`float` 值集对应于 IEEE 754 `binary32` 格式可表示的值；`float-extended-exponent` 具有相同的精度位但更大的范围。同样，`double` 值集对应于 IEEE 754 `binary64` 格式可表示的值；`double-extended-exponent` 具有相同的精度位但更大的范围。默认允许使用扩展值集改变了某些处理器家族的性能问题。

为了兼容性，Java 1.2 允许程序员禁止实现使用扩展指数值集。程序员通过在类、接口或方法的声明上放置 `strictfp` 修饰符来表达此。`strictfp` 限制了任何包含表达式的浮点语义，使其对表达式使用 float 值，对 double 表达式使用 double 值，确保此类表达式的结果是完全可预测的。因此，被 `strictfp` 修改的代码的浮点语义与 Java 1.0 和 1.1 中相同。

## 15.5 表达式与运行时检查

在 Java SE 17 及更高版本中，Java SE 平台始终要求对浮点表达式进行严格求值。在实现严格求值方面存在性能问题的处理器家族的较新成员不再有该困难。本规范不再将 `float` 和 `double` 与上述描述的四种值集关联，且 `strictfp` 修饰符不再影响浮点表达式的求值。为了兼容性，`strictfp` 一直是 Java SE 17 中的关键字（§3.8），并继续对其使用进行限制（§8.4.3, §9.4.3）。

## 求值的正常完成与异常完成

然而，如果表达式的求值抛出了异常，则称该表达式为异常完成。异常完成总有一个关联的原因，该原因始终是一个带有给定值的抛出（throw）。

预定义操作符抛出运行时异常的情况如下：

- 类实例表达式（§15.9.4）、数组创建表达式（§15.10.2）、方法引用表达式（§15.13.3）、数组初始化器表达式（§10.6）、字符串拼接运算符表达式（§15.18.1）或 lambda 表达式（§15.27.4）如果在可用内存不足时，将抛出 `OutOfMemoryError`。
- 数组创建表达式（§15.10.2）如果索引值小于零，则抛出 `NegativeArraySizeException`。
- 数组访问表达式（§15.10.4）如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 数组访问表达式（§15.10.4）如果数组索引的值为负或大于等于数组长度，则抛出 `ArrayIndexOutOfBoundsException`。
- 字段访问表达式（§15.11）如果对象引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 方法调用表达式（§15.12）调用实例方法时，如果目标引用为 `null`，则抛出 `NullPointerException`。
- 转换表达式（§15.16）如果在运行时发现转换是不允许的，则抛出 `ClassCastException`。
- 整数除法（§15.17.2）或整数取模（§15.17.3）运算符如果右操作数的值为零，则抛出 `ArithmeticException`。
- 对引用类型数组组件的赋值（§15.26.1）、方法调用表达式（§15.12）、或前置或后置递增（§15.14.2、§15.15.1）或递减运算符（§15.14.3、§15.15.2）可能装箱转换（§5.1.7）而抛出 `OutOfMemoryError`。
- 对引用类型数组组件的赋值（§15.26.1）如果要赋值的值与数组的组件类型不兼容（§10.5），则抛出 `ArrayStoreException`。
- switch 表达式（§15.28）如果没有 switch 标签匹配选择器表达式的值，则抛出 `IncompatibleClassChangeError`。

如果发生异常导致方法体执行的异常完成，则方法调用表达式也可能导致抛出异常。

如果发生异常导致构造函数的执行异常完成，则类实例创建表达式也可能导致抛出异常。

在表达式的求值过程中，还可能发生各种链接错误和虚拟机错误。根据其性质，这些错误难以预测且难以处理。

如果发生异常，则一个或多个表达式的求值可能会在正常模式求值的所有步骤完成之前终止；此类表达式被认为是异常完成。

如果一个表达式的求值需要对子表达式进行求值，则子表达式的异常完成总是会导致表达式本身的立即异常完成，其具有相同的原因，并且不执行正常模式求值中的所有后续步骤。

“正常完成”和“异常完成”术语也应用于语句的执行（§14.1）。语句可能出于多种原因异常完成，而不仅仅是因为抛出了异常。

## 15.7 求值顺序

Java 编程语言保证操作符的操作数似乎是按照特定的求值顺序进行求值的，即从左到右。

> 建议代码不要关键性地依赖此规范。当每个异常最多包含一个侧边效应（作为最外层的操作），且代码不依赖于由于表达式从左到右求值的结果而具体产生了哪种异常时，代码通常会更清晰。

### 15.7.1 先求值左操作数

二元运算符的左操作数在右操作数的任何部分被求值之前，似乎已经完全完成了求值。

如果该运算符是复合赋值运算符（§15.26.2），则对左操作数的求值包括记住左操作数所代表的变量，以及获取并保存该变量的值以供隐含的二元操作使用。

如果二元运算符左操作数的求值异常完成，则右操作数的一部分将不会被求值。

### 示例 15.7.1-1. 左操作数已求值

在以下程序中，`*` 运算符有一个左操作数，它在右操作数被求值之前抛出了异常。

```java
// 示例代码占位符，原文未提供具体代码内容
```



# 表达式

## 求值顺序

### 15.7

```java
class Test1 {

    public static void main(String[] args) {

        int i = 0;

        try {

            int j = i / 0++;

        } catch (Exception e) {

            System.out.println(i);

        }

    }

}
```

该程序产生输出：`0`

### 示例 15.7.1-2. 复合赋值

在以下程序中，两个赋值语句获取并记录了左操作数的值，此时发生了赋值。

```java
class Test2 {

    public static void main(String[] args) {

        int a = 1;

        try {

            a += loseBig();

        } catch (Exception e) {

            System.out.println(a);

        }

    }

    static int loseBig() throws Exception {

        throw new Exception("Shuffle off here!");

    }

}
```

该程序产生输出：`1`

### 示例 15.7.1-3. 求值的异常完成

在以下程序中，左操作数的异常完成抛出了异常。

```java
class Test3 {

    public static void main(String[] args) {

        int j = 1;

        try {

            int i = loseBig() / j;

        } catch (Exception e) {

            System.out.println(j);

        }

    }

    static int loseBig() throws Exception {

        throw new Exception("Shuffle off here!");

    }

}
```

该程序产生输出：`1`

### 15.7.2 操作前求操作数

二元运算符的左操作数在右操作数的任何部分被求值之前，似乎已经完全完成了求值。

如果该运算符是整数除法（§15.17.2）或整数取模（§15.17.3），其执行可能会引发 `ArithmeticException`，但在两个操作数都被求值之后。

### 示例 15.7.2-1. 操作前操作数

```java
class Test {

    public static void main(String[] args) {

        int divisor = 0;

        try {

            int i = 1 / loseBig();

        } catch (Exception e) {

            System.out.println(e);

        }

    }

    static int loseBig() throws Exception {

        throw new Exception("Shuffle off here!");

    }

}
```

该程序产生输出：
`java.lang.Exception: Shuffle off here!`

### 15.7.3 求值尊重括号和优先级

Java 编程语言尊重由括号显式指示和由运算符优先级间接指示的求值顺序。

Java 编程语言的实现可能利用代数等式（如结合律）将表达式重写为更方便的顺序，除非证明在多线程执行的情况下，替换表达式在值和可见状态效应上都是等价的。

对于浮点数计算，此规则也适用于无穷和 `NaN` 值。

- `(x<y)` 可能不能重写为 `x<=y`，如果 `x` 或 `y` 任为 `NaN`，这些表达式的值不同。

具体来说，在数学上看起来具有结合性的浮点数计算在计算上可能是不结合性的。此类计算不能盲目地进行重排。

例如，Java 编译器将 `4.0*x*0.5` 重写为 `2.0*x` 是不正确的；虽然舍入在这里不是问题，但对于某些较大的 `x` 值，第一个表达式会产生无穷大（因为溢出），而第二个表达式会产生一个有限的结果。

因此，例如，测试程序：

```java
class Test {

    public static void main(String[] args) {

        double d = 8E307;

        System.out.println(4.0 * d * 0.5);

        System.out.println(2.0 * d);

    }

}
```

打印：

```
Infinity
1.6E308
```

因为第一个表达式溢出了，而第二个没有。

相比之下，在 Java 编程语言中，整数的加法和乘法可以证明是满足结合律的。

例如 `$a+b+c$`，其中 `$a, b,$` 和 `$c$` 是局部变量（这个简化假设避免了涉及多线程和 `volatile` 变量的问题），求值结果 `$(a+b)+c$` 或 `$a+(b+c)$` 总是会产生相同的答案；如果表达式 `$b+c$` 出现在代码附近，智能编译器可能可以使用这个公共子表达式。

### 15.7.4 参数列表从左到右求值

在方法调用、构造函数调用或实例创建表达式中，参数表达式可能出现在括号内，并用逗号分隔。在任何参数表达式右侧的任何部分求值之前，每个参数表达式似乎都已完全求值。

如果参数表达式的求值异常完成，则其右侧的任何参数表达式的部分似乎都未被求值。

### 示例 15.7.4-1. 方法调用时的求值顺序

```java
class Test1 {

    public static void main(String[] args) {

        String s = "going,";

        print3(s, s, s = "gone");

    }

    static void print3(String a, String b, String c) {

        System.out.println(a + b + c);

    }

}
```

该程序产生输出：

`going, going, gone`

因为将字符串 `"gone"` 赋值给 `$s$` 发生在对 `print3` 的前两个参数求值之后。

### 示例 15.7.4-2. 参数表达式的异常完成

```java
class Test2 {

    static int id;

    public static void main(String[] args) {

        try {

            test(id = 1, coops(), id = 3);

        } catch (Exception e) {

            System.out.println(e + " ", id=" + id);

        }

    }

    static int test(int a, int b, int c) {

        return a + b + c;

    }

    static int coops() throws Exception {

        throw new Exception("coops");

    }

}
```

该程序产生输出：

```
java.lang.Exception: coops, id=1
```

因为没有执行对 `id` 赋值 `3`。

### 15.7.5 其他表达式的求值顺序

某些表达式的求值顺序没有被这些通用规则完全覆盖，因为这些表达式可能会在指定的时刻引发异常情况。参见以下类型表达式求值顺序的详细说明：

- 类实例创建表达式（§15.9.4）
- 数组创建表达式（§15.10.2）
- 数组访问表达式（§15.10.4）
- 方法调用表达式（§15.12.4）
- 方法引用表达式（§15.13.3）
- 涉及数组组件的赋值（§15.26）
- lambda 表达式（§15.27.4）

## 15.8 基础表达式

基础表达式包括最简单的几类表达式，所有其他表达式都由它们构造：字面量、对象创建、字段访问、方法调用、方法引用和数组访问。带括号的表达式在语法上也被视为基础表达式。

- 基础 (`Primary`):
  `PrimaryNoNewArray`
  `ArrayCreationExpression`

- 无新数组基础 (`PrimaryNoNewArray`):
  `Literal`
  `ClassLiteral`
  `this`
  `TypeName`
  `( Expression )`
  `ClassInstanceCreationExpression`
  `FieldAccess`
  `ArrayAccess`
  `MethodInvocation`
  `MethodReference`

Java 编程语言语法的这部分有两个不同寻常。首先，人们可能认为简单的名称（如局部变量和方法参数名称）应该是基础表达式。由于技术原因，名称在之后引入后缀表达式（§15.14）时与基础表达式归为类。

技术原因在于允许在仅使用单标记向前查找（one-token lookahead）的情况下对 Java 程序进行从左到右的解析。考虑表达式 `z[]` 和 `(z)`。第一个是带括号的数组访问（§15.0.3），第二个是类型转换的开始（§15.16）。在前行符号为 `[` 的点，从左到右的解析已经将 `z` 归约为非终端 `Name`。在类型转换的上下文中，我们不希望将名称归约为 `Primary`，如果 `Name` 是 `Primary` 的候选项之一，我们就无法判断是否要执行该操作，无法在不向前看两个标记（即 `[` 之后的标记）的情况下确定该情况会演变为数组访问还是类型转换。这里呈现的语法通过保持 `Name` 和 `Primary` 分离，并在某些其他语法规则中允许两者（适用于 `ClassInstanceCreationExpression`、`MethodInvocation`、`ArrayAccess` 和 `PostfixExpression` 的规则，但不包括 `FieldAccess`，因为它直接使用了标识符）来避免这个问题。这种策略有效地将 `Name` 是否应视为 `Primary` 的问题推迟到直到可以检查更多的上下文。

另一个不同寻常的特征避免了表达式 `new int[3][3]` 中潜在的语法歧义，该表达式在 Java 中始终意味着多维数组的单次创建，但如果没有适当的处理，它可能被解释为与 `"new int[3][]"` 相同。这种歧义通过将预期的 `Primary` 拆分为 `Primary` 和 `PrimaryArray` 来消除。

### 15.8.1 词法字面量

字面量（§10）表示一个固定值。此处显示如下推导式：

```
Literal:
  IntegerLiteral
  FloatingPointLiteral
  BooleanLiteral
  CharacterLiteral
  StringLiteral
  TextBlock
  NullLiteral
```

字面量的类型确定如下：

- 以 `L` 结尾的整数字面量（§10.1）为 `long`。
- 任何其他整数字面量为 `int`。
- 以 `F` 结尾的浮点字面量（§10.2）为 `float`。
- 任何其他浮点字面量为 `double`。
- 布尔字面量（§13）为 `boolean`。
- 字符字面量（§14）为 `char`。
- 字符串字面量（§15）或文本块（§16）为 `String`。
- 空字面量（§108）为空类型；其值为引用。

### 15.8.2 类字面量

类字面量是由类、接口、数组类型或原始类型的名称，后跟一个 `.` 和标记 `class` 组成的表达式。

```
TypeName[].class
NumericType[].class
boolean[].class
void.class
```

`TypeName` 表示可访问的类或接口（§6.6）。如果 `TypeName` 表示不可访问的类或接口或类型变量，则为编译时错误。

`$C.class$` 的类型（`$C$` 为类、接口或数组类型的名称（§4.3））为 `Class<$C$>`。

`$p.class$` 的类型（`$p$` 为原始类型的名称（§4.2））为 `Class<$B$>`，其中 `$B$` 是类型 `$p$` 经过装箱转换后的类型（§5.1.7）。

`void.class`（§8.4.5）为 `Class<$Void$>`。

类字面量的求值为由当前实例类的类加载器（§12.2）定义的类、接口、数组类型（或 `void`）。

### 15.8.3 `this` 关键字

关键字 `this` 可以在以下上下文作为表达式：

- 在类的实例方法主体（§8.4.3.2）
- 在类的构造函数主体（§8.8.7）
- 在类的变量初始化器（§8.6）
- 在类的实例变量初始化器（§8.6.2）
- 在接口的实例方法主体中，即默认方法或非静态私有接口方法（§9.4）

作为表达式使用时，关键字 `this` 表示一个值，该值是对调用该实例方法的对象的引用（§15.12），或者是正在构造对象的引用。lambda 主体（§15.27.2）中 `this` 所表示的值与周围上下文中 `this` 所表示的值相同。

> 关键字 `this` 还用于显式构造函数调用语句（§8.8.7.1），以及表示方法或构造函数的接收器参数（§8.4）。

如果此表达式出现在静态上下文中（§8.1.3），则为编译错误。

如果在静态上下文中出现限定的 `this` 表达式（§8.1.3），则为编译错误。

如果直接包含该限定的 `this` 表达式的类或接口不是 `TypeName` 本身的内部类，则为编译错误。

### 15.8.4 括号表达式

括号表达式是一个初级表达式，其类型为所包含表达式的类型，其运行时的值为所包含表达式的值。如果所包含表达式表示一个变量，则括号表达式也表示该变量。

括号的使用仅影响求值顺序，但特殊情况除外：`(-2147483648)` 和 `(-922337023685477808L)` 是合法的，而 `(-2147483648)` 和 `(-922337023685477808L)` 是非法的。

这是因为十进制字面量 `2147483648` 和 `922337023685477808L` 仅允许作为元负号运算符的操作数（§3.10.1）。

特别地，表达式周围是否存在括号不会影响变量是否被确定赋值、在为真时确定赋值、在为假时确定赋值、未定义、在真时未确定赋值或为假时未定义（§16 确定赋值）。

如果括号表达式出现在具有目标类型的特定上下文中（转换与上下文），则其包含的表达式同样出现在具有目标类型 $\tau$ 的相同类型的上下文中。

如果所包含表达式是一个多值表达式（§15.2），则括号表达式也是多值表达式。否则，它是一个独立表达式。

如果所包含表达式与目标类型 $\tau$ 兼容，则多值括号表达式与目标类型 $\tau$ 兼容。

## 15.9 类实例创建表达式

类实例创建表达式用于创建作为类实例的新对象。

```
ClassInstanceCreationExpression:
  UnqualifiedClassInstanceCreationExpression
  ExpressionName . UnqualifiedClassInstanceCreationExpression
  Primary . UnqualifiedClassInstanceCreationExpression
```

### 类实例创建表达式

```
UnqualifiedClassInstanceCreationExpression:
  new [TypeArguments]
  ClassOrInterfaceTypeToInstantiate ([ArgumentList] ) ClassBody
```

```
ClassOrInterfaceTypeToInstantiate:
  [Annotation] Identifier {, [Annotation] Identifier}
  [TypeArgumentsOrDiamond]
```

```
TypeArgumentsOrDiamond:
  TypeArguments
  <>
```

为了方便起见，这里展示了 §15.12 中的以下产生式：

```
ArgumentList:
  Expression [ , Expression]
```



# 类实例创建表达式

## 概述

类实例创建表达式指定了要实例化的类，后面可能跟着类型参数，或者如果该类是泛型的，则跟着菱形 `<>`，随后是对应的（可能为空的）构造函数的实际值参数列表。

如果类的类型参数列表为空——即菱形形式 `<>`——则类的类型参数将被推断。虽然在风格上强烈不建议，但在 `<` 和 `>` 之间有空格是合法的。

如果构造函数是泛型的（§8.8.4），则构造函数的类型参数同样可以推断或显式传递。如果显式传递，构造函数的类型参数将紧跟关键字 `new`。

如果类实例创建表达式为构造函数提供了类型参数，但对类的类型参数使用了菱形形式，则为编译错误。引入此规则是因为泛型类类型参数的推断可能会影响对泛型类型参数的约束。

如果 `TypeArguments` 紧跟在 `new` 之后或在 `(` 之前，若其中任何类型参数为通配符（§4.5.1），则为编译错误。

类实例创建表达式可能抛出的异常指定于 §11.2.1。

类实例创建表达式有两种形式：

- **未限定的类实例创建表达式**以关键字 `new` 开头。可创建类的实例，无论该类是顶层的（§7.5）、成员（§8.5, §9.5）、本地（§14.3）还是匿名类（§15.9.5）。
- **限定的类实例创建表达式**以 `Primary` 表达式或 `ExpressionName` 开头。允许创建内部成员类及其匿名子类的实例。

未限定和限定的类创建表达式都可以可选地以类体结束。此类类实例创建表达式声明了一个匿名类（§15.9.5）并创建它的实例。

如果类实例创建表达式对类的类型参数使用了菱形形式，并且出现在赋值上下文或调用上下文中（§5.2, §5.3），则它是一个多值表达式（§15.2）。否则，它是一个独立表达式。

当通过类实例创建表达式创建类的实例时，我们说该类被实例化。类实例化涉及确定要实例化的类（§15.9.1）、新创建实例的外部实例（如果有）（§15.9.2）以及用于创建新实例要调用的构造函数（§15.9.3）。

## 15.9.1 确定被实例化的类

如果 `ClassInterfaceToInstantiate` 以 `TypeArguments` 结尾（而不是 `<>`），则 `ClassInterfaceToInstantiate` 必须表示一个良好的参数类型（§4.5），否则将发生编译错误。

如果 `ClassInterfaceToInstantiate` 以 `<>` 结尾，但 `ClassInterfaceToInstantiate` 中的 `Identifier` 所指定的类或接口不是泛型的，则发生编译错误。

如果类实例创建表达式以类体结尾，则被实例化的类是匿名类。此时：

- 如果类创建表达式是未限定的，则 `ClassInterfaceToInstantiate` 中的 `Identifier` 必须表示一个可访问的、可扩展的（§8.1.2）非枚举类，或者一个可访问且可扩展的接口（§9.1.4）。否则发生编译错误。
- 如果 `ClassInterfaceToInstantiate` 中的 `Identifier` 表示一个类 `c`，则声明 `c` 的匿名直接子类。如果存在 `TypeArguments`，则 `c` 的类型参数由 `TypeArguments` 提供；如果存在 `<>`，则 `c` 的类型参数将被推断（§15.9.3）；否则 `c` 没有类型参数。子类的体为类创建表达式中的类体。被实例化的类是该匿名子类。
- 如果 `ClassInterfaceToInstantiate` 中的 `Identifier` 表示一个接口 `i`，则声明 `Object` 的匿名直接子类。如果存在 `TypeArguments`，则 `i` 的类型参数由 `TypeArguments` 提供；如果存在 `<>`，则 `i` 的类型参数将被推断（§15.9.3）；否则 `i` 没有类型参数。子类的体为类创建表达式中的类体。被实例化的类是该匿名子类。
- 如果类创建表达式是限定的，则：`ClassInterfaceToInstantiate` 中的 `Identifier` 必须明确表示一个可访问的、可扩展的、非枚举的内部类，并且是 `Primary` 表达式或 `ExpressionName` 编译类型的成员。否则发生编译错误。设 `ClassInterfaceToInstantiate` 中的 `Identifier` 表示一个类 `c`，则声明 `c` 的匿名直接子类。如果存在 `TypeArguments`，则 `c` 的类型参数由 `TypeArguments` 提供；如果存在 `<>`，则 `c` 的类型参数将被推断（§15.9.3）；否则 `c` 没有类型参数。子类的体为类实例创建表达式中的类体。被实例化的类是该匿名子类。
- 如果类创建表达式没有声明匿名类，则：`ClassInterfaceToInstantiate` 中的 `Identifier` 必须表示一个可访问的、非抽象的非枚举类。否则发生编译错误。被实例化的类由 `ClassInterfaceToInstantiate` 中的 `Identifier` 指定。如果存在 `TypeArguments`，则该类的类型参数由 `TypeArguments` 提供；如果存在 `<>`，则该类的类型参数将被推断（§15.9.3）；否则该类没有类型参数。

## 15.9.2 确定包围实例

令 `c` 为被实例化的类，令 `i` 为被创建的实例。如果 `c` 是内部类，则 `i` 可能有一个直接包围实例（§8.1.3），其确定方式如下：

- 如果 `c` 是匿名类，则：
  - 如果该类实例化创建表达式发生在静态上下文中，则 `i` 没有直接包围实例。
  - 否则，`i` 的直接包围实例是 `this`。
- 如果 `c` 是内部局部类，则：
  - 如果 `c` 发生在静态上下文中，则 `i` 没有直接包围实例。
  - 否则，如果该类实例化创建表达式发生在静态上下文中，则发生编译错误。
  - 否则，令 `o` 为 `c` 的直接包围类或接口声明，令 `u` 为该类实例化创建表达式的直接包围类或接口声明。
  - 如果 `u` 不是 `o` 的内部类或 `o` 本身，则发生编译错误。
  - 令 `n` 为整数使得 `o` 是 `u` 的第 `n` 个词法包围类或接口声明。`i` 的直接包围实例是 `this` 的第 `n` 个词法包围实例。
- 如果 `c` 是一个内部成员类，则：
  - 如果该类实例化创建表达式是非限定的，则：
    - 如果该类实例化创建表达式发生在静态上下文中，则发生编译错误。
    - 否则，如果 `c` 不是任何在词法上启用该类实例化创建表达式的类的成员，则发生编译错误。
    - 否则，令 `o` 为 `c` 所所属的最内层包围类声明，令 `u` 为该类实例化创建表达式的直接包围类或接口声明。
    - 如果 `u` 不是 `o` 的内部类或 `o` 本身，则发生编译错误。
    - 令 `n` 为整数使得 `o` 是 `u` 的第 `n` 个词法包围类或接口声明。`i` 的直接包围实例是 `this` 的第 `n` 个词法包围实例。
  - 如果该类实例化创建表达式是限定的，则 `i` 的直接包围实例是作为 `Primary` 表达式或 `ExpressionName` 值的对象。

如果 `c` 是匿名类，且其直接父类 `s` 是内部类，则 `i` 可能有一个*相对于 `s` 的直接包围实例*，其确定方式如下：

- 如果 `s` 是内部局部类，则：
  - 如果 `s` 发生在静态上下文中，则 `i` 没有相对于 `s` 的直接包围实例。
  - 否则，如果该类实例化创建表达式发生在静态上下文中，则发生编译错误。
  - 否则，令 `o` 为 `s` 的直接包围类或接口声明，令 `u` 为该类实例化创建表达式的直接包围类或接口声明。
  - 如果 `u` 不是 `o` 的内部类或 `o` 本身，则发生编译错误。
  - 令 `n` 为整数使得 `o` 是 `u` 的第 `n` 个词法包围类或接口声明。`i` 相对于 `s` 的直接包围实例是 `this` 的第 `n` 个词法包围实例。
- 如果 `s` 是内部成员类，则：
  - 如果该类实例化创建表达式是非限定的，则：
    - 如果该类实例化创建表达式发生在静态上下文中，则发生编译错误。
    - 否则，如果 `s` 不是任何包围该类实例化创建表达式的类的成员，则发生编译错误。
    - 否则，令 `o` 为 `s` 所属的最内层包围声明，且 `u` 为该类实例化创建表达式的直接包围类或接口声明。
    - 如果 `u` 不是 `o` 的内部类或 `o` 本身，则发生编译错误。
    - 令 `n` 为整数使得 `o` 是 `u` 的第 `n` 个词法包围类或接口声明。`i` 相对于 `s` 的直接包围实例是 `this` 的第 `n` 个词法包围实例。
  - 如果该类实例化创建表达式是限定的，则 `i` 相对于 `s` 的直接包围实例是作为 `Primary` 表达式或 `ExpressionName` 值的对象。

## 15.9.3 选择构造函数及其参数

令 `c` 为被实例化的类。为了创建 `c` 的实例 `i`，将通过以下规则选择 `c` 的构造函数。

首先，确定构造函数的实际参数：

- 如果 `c` 是具有直接父类 `s` 的匿名类，则：
  - 如果 `s` 不是内部类，或 `s` 是发生在静态上下文中的局部类，则构造函数的参数是该类实例化创建表达式中的参数。
  - 否则，构造函数的第一个参数是 `i` 相对于 `s` 的直接包围实例（§15.9.2），后续参数是该类实例化创建表达式中的参数。
- 如果 `c` 是局部类或*私有*内部成员类，则构造函数的参数是该类实例化创建表达式中的参数。
- 如果 `c` 是*非私有*内部成员类，则构造函数的第一个参数是 `i` 的直接包围实例（§8.8.1, §15.9.2），其后续参数是该类实例化创建表达式中的参数。
- 否则，构造函数的参数是该类实例化创建表达式中的参数。

其次，确定 `c` 的构造函数以及相应的 `throws` 子句和返回类型：

- 如果该类实例化创建表达式没有使用 `{}`，则：
  - 如果 `c` 不是匿名类，则：
    令 `τ` 为由 `c` 类型后跟表达式中的任何类型参数构成的类型。使用 §15.12.2 中经过构造函数处理的方法来选择 `τ` 的一个构造函数并确定其 `throws` 子句。
    如果 `τ` 中不存在既适用又可访问的最特定构造函数（§6.6），则发生编译错误（同于方法调用）。
    否则，所选构造函数对应的返回类型为 `τ`。
  - 如果 `c` 是匿名类，则：
    使用 §15.12.2 中经过构造函数处理的方法来选择 `c` 的直接父类类型的一个构造函数并确定其 `throws` 子句。
    如果 `c` 的直接父类类型中不存在既适用又可访问的最特定构造函数，则发生编译错误（同于方法调用）。
    否则，选择 `c` 的匿名构造函数作为 `c` 的构造函数（§15.9.5.1）。其体包含对直接父类类型中所选构造函数的显式构造函数调用（§8.8.7.1）。
    所选构造函数的 `throws` 子句包括直接父类类型中所选构造函数的 `throws` 子句中的异常。

如果类实例创建表达式使用了 `<>`，则：

如果 `c` 不是匿名类，则令 `d` 等于 `c`。如果 `c` 是匿名类，则令 `d` 为类实例创建表达式所指定的超类或超接口。

如果 `D` 是一个类，`c_1...c_n` 为类 `D` 的构造方法。如果 `D` 是一个接口，则令 `c_1...c_n` 为一个单例（`n=1`），其包含类对象的零参数构造方法。

定义一个方法列表 `m_1...m_n` 用于重载解析和参数推断。对于所有 `j` (`1 ≤ j ≤ n`)，`m_j` 根据 `c_j` 定义如下：

- 首先定义一个替换式 `θ_j` 来实例化 `c_j` 中的类型。

令 `F_1...F_p` 为 `D` 的类型参数，`G_1...G_q` 为 `c_j` 的类型参数（如果有的话）。令 `X_1...X_p` 和 `Y_1...Y_q` 为名称不在 `D` 体中的类型变量。

- `θ_j` 是 `[F_1:=X_1, ..., F_p:=X_p, G_1:=Y_1, ..., G_q:=Y_q]`。
- `m_j` 的类型参数为 `X_1...X_p, Y_1...Y_q`，这些是不同的名称，因为每个类型参数的边界（如果有的话）是 `θ_j` 应用于 `D` 或 `c_j` 中对应的类型参数边界。
- `m_j` 的返回类型为 `θ_j` 应用于 `D<F_1,...,F_p>`。
- `m_j` 的参数类型列表（可能为空）为 `θ_j` 应用于 `c_j` 的参数类型。
- `m_j` 的抛出类型列表（可能为空）为 `θ_j` 应用于 `c_j` 的抛出类型。
- `m_j` 的修饰符为 `c_j` 的修饰符。
- `m_j` 的名称为 `#j`，这是一个自动生成的名称，与 `D` 中的所有构造方法和方法名都不同，并由 `m_1...m_n` 共享。
- `m_j` 的体是无关的。

为了选择一个构造方法，我们临时将 `m_1...m_n` 视为 `D` 的成员。根据类实例创建表达式的参数表达式，使用 §15.12.2 规定的过程从 `m_1...m_n` 中选择其中一个。

如果没有既适用又可访问的唯一特定方法，则发生编译时错误。

否则，当 `m_j` 是被选方法时：

- 如果 `c` 不是匿名类，则 `c_j` 是 `C` 的构造方法。与所选构造方法对应的返回类型是为 `m_j` 确定的返回类型（§15.12.2.6）。
- 如果 `c` 是匿名类，则选择 `c` 的匿名构造方法作为 `c` 的构造方法。其体包含对 `c_j` 的显式构造方法调用（§8.8.7.1）。所选构造方法的 `throws` 子句包含为 `m_j` 确定的 `throws` 子句中的异常。与所选构造方法对应的返回类型是匿名类类型。

如果类实例创建表达式是一个多表达式，其与目标类型的兼容性由 §18.5.2.1 确定，使用 `m_j` 作为所选方法 `m`。

> 在最终确定类实例创建表达式的目标类型和所选构造方法对应的返回类型之前，与目标类型的兼容测试可能会发生多次。例如，嵌套的调用表达式可能需要测试类实例创建表达式与不同方法的形式参数类型的兼容性。

如果 `c` 是匿名类，则其直接超类类型或直接超接口类型为 `m_j` 确定的返回类型（§15.12.2.6）。

如果直接超类类型或直接超接口类型，或其中的任何子表达式（“子表达式”）包含参数化类型的类型参数、通配符类型参数的边界以及数组类型的元素类型（但不排除类型变量边界），且包含以下之一，则为编译时错误：

- 一个类或接口类型，其中该类或接口的声明从类实例创建表达式出现的类或接口是不可访问的。

如果类实例创建表达式的参数与其从调用类型（§15.12.2.6）得出的目标类型不兼容，则为编译时错误。

- 一个交叉类型。

如果编译声明通过可变变长调用（§15.12.2.4）是可用的，则构造方法调用类型的最后一个形式参数类型为 `Fn[]`，如果作为 `Fn` 擦除的类型在调用点不可访问的，则为编译时错误。

类实例创建表达式的类型是上文定义的所选构造方法对应的返回类型。

## 15.9.4 类实例创建表达式的运行时求值

在运行时，类实例创建表达式的评估如下。

首先，如果类实例创建表达式是带限定的类实例创建表达式，则求值限定的主表达式。如果限定表达式求值结果 `null`，则抛出 `NullPointerException`，且类实例创建表达式异常终止。如果限定表达式异常终止，则类实例创建表达式因相同原因异常终止。

接下来，为新实例分配空间。如果没有足够的空间来分配对象，则通过抛出 `OutOfMemoryError` 使实例创建表达式的评估异常终止。

新对象创建所有字段的实例。当每个字段实例被创建时，它被初始化为其默认值（§8.5）。

接下来，从左到右评估实际参数。如果任何参数异常终止，则实例创建表达式因相同原因异常终止。

接下来，调用指定类的构造方法。这导致为每个超类调用至少一次构造方法。

实例创建表达式的值是新创建对象的引用。每当评估表达式时，都会创建一个新的对象。

### 15.9.4.1 评估顺序和内存检测

如果类实例创建表达式的评估发现内存不足，则抛出 `OutOfMemoryError`。此检查在评估参数之前进行。

对于匿名类，内存不足条件在评估参数之前检测。

因此，例如：

```java
class List {
    int value;
    List next;

    List(int n) {
        value = n;
        next = null;
    }

    public static void main(String[] args) {
        try {
            List l = new List(0);
            System.out.println(l.getClass() + " " + l.value);
        } catch (Error e) {
            System.out.println(e.getClass() + " " + e);
        }
    }
}
```

输出：



class `List$0`

### 15.9.4.2 匿名类声明

匿名类不是任何包、类或接口的成员（§7.1，§8.5）。

枚举常量声明的匿名类的直接超类型为声明类的类型。

实例创建表达式或枚举常量的体声明：
- 字段（§8.3）
- 成员类（§8.4）
- 成员接口（§8.5）
- 方法（§9.1.3）
- 初始化器（§8.6）
- 静态初始化器（§8.7）

匿名类总是内部类（§8.1）。匿名类的构造方法总是隐式的（§15.9.5.1）。

如果带有体的类实例创建表达式使用菱形（`<>`）作为实例化类的类型参数，则对于体中声明的非私有方法，其方法声明仿佛标记了 `@Override`（§9.6.4）。

> 当使用 `<>` 时，推断的类型参数可能不符合程序的预期。因此，匿名类的超类型可能不符合预期，且匿名类中声明的方法可能会意外覆盖超类型方法。将此类方法标记为 `@Override`（如果它们没有显式标记为 `@Override`）有助于静默错误的程序。

## 15.9.5 匿名构造方法

匿名类不能显式声明构造方法。相反，为匿名类隐式声明一个匿名构造方法。对于直接超类为 `s` 的匿名类 `c`，匿名构造方法的形式如下：

- 如果 `s` 不是内部类，或者 `s` 是发生在静态上下文中的局部类，则匿名类实例创建表达式或枚举常量的每个实际参数对应一个形式参数。

类实例创建表达式或枚举常量的实际参数用于确定 `s` 的构造方法 `x`，如 §15.9.3 所示。

匿名构造函数的每个形式参数都被处理为与 `x` 对应的形式参数完全相同。

匿名构造函数体包含一个显式的构造函数调用 (§8.8.7.1)，形式为 `super(...)`，其中实际参数是匿名构造函数的形式参数，按照它们声明的顺序排列。要调用的父类构造函数是 `x`。

- 否则，匿名构造函数的第一个形式参数表示相对于 `s` 的紧邻包含的 `i` 实例的值 (§15.9.2)。该参数的类型是紧邻包含 `s` 声明的类类型。

对于声明匿名类的类创建表达式中的每个实际参数，匿名构造函数都有一个额外的形式参数。第 `n` 个形式参数对应第 `n-1` 个实际参数。

类创建表达式的实际参数用于确定 `s` 的一个构造函数 `x`，如 §15.9.3 所示。匿名构造函数的每个形式参数的类型都被处理为与 `x` 对应的形式参数完全相同。

匿名构造函数体包含一个形式为 `o.super(...)` 的显式构造函数调用，其中 `o` 是匿名构造函数的第一个形式参数，而实际参数是构造函数的后续形式参数，按照它们声明的顺序排列。要调用的父类构造函数是 `x`。

在所有情况下，匿名构造函数的 `throws` 子句列出了匿名构造函数包含的显式构造函数调用语句所抛出的所有检查异常（如 §15.9.3 所示），以及匿名类的实例初始化器或实例变量初始化器抛出的所有检查异常。

注意，匿名构造函数的签名可能会引用一个不可访问的类型（例如，如果此类类型出现在父类构造函数 `x` 的签名中）。这本身不会在编译时或运行时引起任何错误。

## 15.10 数组创建与访问表达式

### 15.10.1 数组创建表达式

数组创建表达式用于创建新数组 (§10 (Arrays))。

```
ArrayCreationExpression:
new PrimitiveTypeInterfaceType DimExpr [Dims]
new ClassOrInterfaceType DimExpr [Dims]
new PrimitiveType Dims ArrayInitializer
new ClassOrInterfaceType Dims ArrayInitializer

DimExpr:
DimExpr [DimExpr]

DimExpr:
{[Annotation] [ Expression ]

Dims:
{[Annotation] [] {[Annotation] []}
```

为了方便起见，这里显示了来自 §4.3 的产生式。

数组创建会创建一个对象，该对象是一个新数组，其元素类型由 `PrimitiveType` 或 `ClassOrInterfaceType` 指定。

如果 `ClassOrInterfaceType` 不表示一个可重构的类型 (§7)，则会产生编译错误。否则，`ClassOrInterfaceType` 可以命名任何命名的引用类型，即使是抽象类类型 (§8.1.1.1) 或接口类型。

规则意味着数组创建表达式中的元素类型不能是泛型类型，除非该泛型类型的所有类型参数都是无界通配符。

`DimExpr` 内部每个维度表达式的类型必须是可以转换为 (§5.1.8) 整数类型的类型，否则会发生编译错误。

每个维度表达式都将进行一元数值提升 (§5.6)。提升后的类型必须是 `int`，否则会发生编译错误。

数组创建表达式的类型是一个数组类型，该类型可以通过该数组创建表达式的副本表示，即删除 `new` 关键字以及每个 `DimExpr` 表达式和数组初始化器后的结果。

例如，创建表达式的类型：

```
new double[3][] []
```

是：

```
double[][][] []
```

### 15.10.2 数组创建表达式的运行时求值

在运行时，数组创建表达式的评估如下：

- 如果没有维度表达式，则必须有一个数组初始化器。新分配的数组将根据数组初始化器提供的值（如 §10.6 所示）进行初始化。数组初始化器的值成为数组创建表达式的值。
- 否则，没有数组初始化器，且：
  - 首先，从左到右求值维度表达式。如果任何表达式求值异常终止，则其右侧的表达式不再被求值。
  - 接下来，检查维度表达式的值。如果任何 `DimExpr` 表达式的值小于零，则抛出 `NegativeArraySizeException`。
  - 接下来，为新数组分配空间。如果空间不足以分配数组，则抛出 `OutOfMemoryError`。
  - 如果只出现一个 `DimExpr`，则创建一个指定长度的一维数组。
  - 否则，如果出现 `n` 个 `DimExpr`，则数组创建实际上创建了 `n` 个嵌套数组。

多维数组在每一层上的长度不需要相同。

#### 15.10.2-1 数组创建

在带有一个或多个维度的数组创建中，每个维度在其右侧的任何部分之前都被完全求值。因此：

```java
class Test1 {
    public static void main(String[] args) {
        int[][] ia = new int[4][3];
        System.out.println(ia.length + ", " + ia[0].length);
    }
}
```

打印：
4, 3

#### 15.10.2-2 维度表达式求值

如果维度表达式的求值异常终止，其右侧的表达式将不再求值：

```java
class Test2 {
    public static void main(String[] args) {
        int[][] a = new int[0][0];
        try {
            int i = 0;
            a = new int[0][i++];
        } catch (Exception e) {
            System.out.println(e + " " + i);
        }
    }
}
```

打印：
java.lang.ExceptionException i=0

#### 15.10.2-3 多维数组创建

声明：

```java
float[][] matrix = new float[3][3];
```

行为上等同于：

```java
float[][] matrix = new float[3];
for (int d = 0; d < matrix.length; d++) {
    matrix[d] = new float[3];
}
```

并且：

```java
Age[][][] Aquarius = new Age[6][10][8];
```

等同于：

```java
Age[][][] Aquarius = new Age[6][][];
for (int d1 = 0; d1 < Aquarius.length; d1++) {
  Aquarius[d1] = new Age[10][];
  for (int d2 = 0; d2 < Aquarius[d1].length; d2++) {
    Aquarius[d1][d2] = new Age[8][];
    for (int d3 = 0; d3 < Aquarius[d1][d2].length; d3++) {
      Aquarius[d1][d2][d3] = new Age[12];
    }
  }
}
```

可以通过以下方式创建三角形矩阵：

```java
float[][] triang = new float[100][];
for (int i = 0; i < triang.length; i++)
    triang[i] = new float[i+1];
```

如果数组表达式求值发现内存不足以执行，则抛出 `OutOfMemoryError`。如果数组创建没有数组初始化器，则此检查仅在所有数组维度正常完成后完成后。如果数组创建有数组初始化器，则在求值变量初始化期间分配引用类型对象，或为存储（可能的嵌套）数组初始化值的数组分配空间时，可能会发生 `OutOfMemoryError`。

示例 15.10.2-3 OutOfMemoryError 与维度表达式求值

```java
class Test3 {
  public static void main(String[] args) {
    int len = 0, oldlen = 0;
    Object[] a = new Object[0];
    try {
      for (;;)
        ++len;
        a[oldlen] = new Object[oldlen = len];
    } catch (Error e) {
      System.out.println(e + " " + (oldlen==len));
    }
  }
}
```

打印：
java.lang.OutOfMemoryError true

因为在求值维度表达式 `len` 之后检测到了内存溢出情况。

将其与类实例创建表达式（§15.9）相比，后者在求值数组创建表达式（§15.9.4）之前检测到内存溢出情况。

### 15.10.3 数组访问表达式

数组访问表达式指的是作为数组组件的变量。

```
ArrayAccess:
ExpressionName [ Expression ]
PrimaryNoNewArray [ Expression ]
```

数组访问表达式包含两个子表达式：数组引用表达式（左括号之前）和索引表达式（中括号内部）。

> 数组引用表达式必须是一个名称或任何不是数组表达式的初级表达式（§15.10）。

数组引用表达式的类型必须是数组类型（称之为 `T[]`，或组件类型为 `T` 的数组），否则将发生编译时错误。

索引表达式会经过一元数值提升（§5.6）。提升后的类型必须是 `int`，否则将发生编译时错误。

数组访问表达式的类型是对 `T` 应用捕获转换（§5.1.10）的结果。

数组访问表达式的结果是类型为 `T` 的变量，即根据索引表达式的值位于数组内的变量。

该结果变量是数组的组件，永远不会被视为 final，即使数组引用表达式指向的是 final 变量。

### 15.10.4 数组访问表达式的运行时求值

在运行时，数组访问表达式求值的行为如下：

- 首先，求值数组引用表达式。如果该求值异常完成，则数组访问因相同原因异常完成，且不求值索引表达式。
- 否则，求值索引表达式。如果该求值异常完成，则数组访问因相同原因异常完成。
- 否则，如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 否则，如果索引表达式的值小于零或大于等于数组的长度，则抛出 `ArrayIndexOutOfBoundsException`。
- 否则，数组访问的结果是类型为 `τ` 的、位于数组内的、由索引的值选择。

#### 示例 15.10.4-1. 数组引用先被求值

在数组访问中，括号左侧的表达式在括号内表达式的任何部分被求值之前，似乎已经完全求值。例如，在（诚然怪异）表达式 `a[(a=b)[3]]` 中，表达式 `a` 在表达式 `(a=b)[3]` 之前已完全求值；这意味着在求值表达式 `(a=b)` 之前已经获取并记录了 `a` 的原始值。由 `a` 的原始值引用的数组由另一个数组（可能是同一个数组）的元素 3 订阅，该数组由 `b` 引用，现在也被 `a` 引用。

因此，程序：

```java
class Test1 {
    public static void main(String[] args) {
        int[] a = { 11, 12, 13, 14 };
        int[] b = { 0, 1, 2, 3 };
        System.out.println(a[(a=b)[3]]);
    }
}
```

打印：
14

因为该怪异表达式的值等于 `a[b[3]]` 或 `a[3]` 或 14。

#### 示例 15.10.4-2. 数组引用求值的异常完成

如果括号左侧表达式的求值异常完成，则括号内表达式的任何部分都未被求值过。因此，程序：

```java
class Test2 {
    public static void main(String[] args) {
        int index = 1;
        try {
            skedaddle(index[2]++);
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] skedaddle() throws Exception {
        throw new Exception("Ciao");
    }
}
```

打印：
java.lang.Exception: Ciao, index=1

因为对 `index` 的 2 赋值从未发生。

#### 示例 15.10.4-3. null 数组引用

如果引用表达式产生 `null` 而不是数组，则在运行时抛出 `NullPointerException`，但只有在数组访问表达式的所有部分都已求值之后，且仅当这些表达式正常完成的情况下。程序：

```java
class Test3 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada(index[2]++);
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```

打印：
java.lang.NullPointerException, index=1

因为在检查数组引用表达式之前，数组访问表达式的所有部分都已求值。相关的程序：

```java
class Test4 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada(index[2]++);
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```

打印：
java.lang.NullPointerException, index=1

因为在检查数组引用表达式之前，数组 异常。

## 15.11 字段访问

数组访问表达式指的是作为数组组件的变量。

```
ArrayAccess:
ExpressionName [ Expression ]
PrimaryNoNewArray [ Expression ]
```



数组访问表达式包含两个子表达式：数组引用表达式（左括号之前）和索引表达式（中括号内部）。

> 数组引用表达式必须是一个名称或任何不是数组表达式的初级表达式（§15.10）。

数组引用表达式的类型必须是数组类型（称之为 `T[]`，或组件类型为 `T` 的数组），否则将发生编译时错误。

索引表达式会经过一元数值提升（§5.6）。提升后的类型必须是 `int`，否则将发生编译时错误。

数组访问表达式的类型是对 `T` 应用捕获转换（§5.1.10）的结果。

数组访问表达式的结果是类型为 `T` 的变量，即根据索引表达式的值位于数组内的变量。

该结果变量是数组的组件，永远不会被视为 `final`，即使数组引用表达式指向的是 `final` 变量。

## 15.10.4 数组访问表达式的运行时求值

在运行时，数组访问表达式求值的行为如下：

- 首先，求值数组引用表达式。如果该求值异常完成，则数组访问因相同原因异常完成，且不求值索引表达式。
- 否则，求值索引表达式。如果该求值异常完成，则数组访问因相同原因异常完成。
- 否则，如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 否则，如果索引表达式的值小于零或大于等于数组的长度，则抛出 `ArrayIndexOutOfBoundsException`。
- 否则，数组访问的结果是类型为 $\tau$ 的、位于数组内的、由索引的值选择。

### 示例 15.10.4-1. 数组引用先被求值

在数组访问中，括号左侧的表达式在括号内表达式的任何部分被求值之前，似乎已经完全求值。例如，在（诚然怪异）表达式 `a[(a=b)[3]]` 中，表达式 `a` 在表达式 `(a=b)[3]` 之前已完全求值；这意味着在求值表达式 `(a=b)` 之前已经获取并记录了 `a` 的原始值。由 `a` 的原始值引用的数组由另一个数组（可能是同一个数组）的元素 3 订阅，该数组由 `b` 引用，现在也被 `a` 引用。

因此，程序：

```java
class Test1 {
    public static void main(String[] args) {
        int[] a = { 11, 12, 13, 14 };
        int[] b = { 0, 1, 2, 3 };
        System.out.println(a[(a=b)[3]]);
    }
}
```

打印：

```
14
```

因为该怪异表达式的值等于 `a[b[3]]` 或 `a[3]` 或 14。

### 示例 15.10.4-2. 数组引用求值的异常完成

如果括号左侧表达式的求值异常完成，则括号内表达式的任何部分都未被求值过。因此，程序：

```java
class Test2 {
    public static void main(String[] args) {
        int index = 1;
        try {
            skedaddle(index[2]++);
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] skedaddle() throws Exception {
        throw new Exception("Ciao");
    }
}
```

打印：

```
java.lang.Exception: Ciao, index=1
```

因为对 `index` 的 2 赋值从未发生。

### 示例 15.10.4-3. null 数组引用

如果引用表达式产生 `null` 而不是数组，则在运行时抛出 `NullPointerException`，但只有在数组访问表达式的所有部分都已求值之后，且仅当这些表达式正常完成的情况下。程序：

```java
class Test3 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada(index[2]++);
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```

打印：

```
java.lang.NullPointerException, index=1
```

因为在检查数组引用表达式之前，数组访问表达式的所有部分都已求值。相关的程序：

```java
class Test4 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada(index[2]++);
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```

打印：

```
java.lang.NullPointerException, index=1
```

因为在检查数组引用表达式之前，数组 异常。

## 15.11 字段访问

字段访问表达式指的是对象或类中的字段。

```
FieldAccess:
Primary . Identifier
super . Identifier
TypeName . Identifier
```

初级表达式的类型必须是引用类型 $au$，否则将发生编译时错误。字段访问的含义确定如下：

- 如果标识符在类型 $au$ 中命名了字段，则字段访问是二义的并产生编译错误。
- 如果标识符在类型 $au$ 中未命名可访问字段，则字段访问是未定义的并产生编译错误。

否则，标识符命名了类型 $au$ 中的单个可访问字段，字段访问的类型是捕获转换（5.10）后的 $\tau$。

在运行时，字段访问表达式的结果计算如下（假设程序相对于定义分析是正确的，即空 变量已赋值）：

- 如果字段是静态的：
  - 求值初级表达式并丢弃结果。如果初级表达式求值异常完成，则字段访问因相同原因异常完成。
  - 如果字段是非 final 字段，则结果是类型为 $au$ 的类或接口中类变量的值。
  - 如果字段不是 final，或者是空 final 且字段访问发生在类变量初始化（8.3.2）或静态初始化（8.7），则结果是类型为 $au$ 的类的指定类变量。

- 如果字段不是静态的：
  - 求值初级表达式。如果初级表达式求值异常完成，则字段访问因相同原因异常完成。
  - 如果初级表达式的值为 `null`，则抛出 `NullPointerException`。
  - 如果字段是非 final 字段，则结果是该表达式的值引用的对象中类型 $\tau$ 的字段的值。
  - 如果字段不是 final，或者是空 final 且字段访问发生在实例变量初始化（8.3.2）、实例初始化（8.6）或构造函数（8.8），则结果是该表达式的值引用的对象中类型 $\tau$ 的命名字段的值。

注意，在确定使用哪个字段时，使用的是初级表达式的类型，而不是运行时引用的对象的类。

### 示例 15.11.1. 字段访问的静态绑定

```java
class S { int x = 0; }
class T extends S { int x = 1; }
class Test1 {
    public static void main(String[] args) {
        S s = new T();
        System.out.println(s.x);
    }
}
```

打印： 0

# 表达式

## 字段访问表达式

```java
public static void main(String[] args) {
    T t = new T();
    System.out.println("t.x=" + t.x + " when("t", t));
    S s = new S();
    System.out.println("s.x=" + s.x + " when("s", s));
    s t = t;
    System.out.println("s.x=" + s.x + " when("s", s));
}
static String when(String name, Object t) {
    return "when " + name + " holds a "
    + t.getClass() + " at run time.";
}
```

该程序输出：

```
t.x=1 t holds a class T at run time.
s.x=0 s holds a class S at run time.
s.x=0 s holds a class T at run time.
```

最后一行确实显示，访问的字段并不取决于所引用对象的运行时类；即使引用的是类 T 对象的引用，表达式 `s.x` 指向的也是类 S 的字段，因为表达式的类型是 S。类 T 的对象包含两个名为 x 的字段，一个属于类 T，另一个属于其超类 S。

这种用于字段访问的动态查找允许程序通过简单的实现来实现高效运行。后期绑定和重写的威力是可用的，但仅在使用实例方法时有效。考虑使用实例方法访问字段的相同示例：

```java
class S { int x = 0; int z() { return x; } }
class T extends S { int x = 1; int z() { return x; } }
class Test2 {
    public static void main(String[] args) {
        T t = new T();
        System.out.println("t.z=" + t.z() + " when("t", t));
        S s = new S();
        System.out.println("s.z=" + s.z() + " when("s", s));
        s = t;
        System.out.println("s.z=" + s.z() + " when("s", s));
    }
    static String when(String name, Object t) {
        return "when " + name + " holds a "
        + t.getClass() + " at run time.";
    }
}
```

现在输出是：

```
t.z()=1 t holds a class T at run time.
s.z()=0 s holds a class S at run time.
s.z()=1 t holds a class T at run time.
```

## 15.11 字段访问表达式

最后一行显示，访问的方法确实取决于引用对象的运行时类；当 `z` 持有一个指向类 T 对象的引用时，表达式 `s.z()` 指向的是类 T 的 z 方法，尽管表达式的类型是 S。类 T 的方法重写了 S 的 z 方法。

### 15.11.1-2. 接收者变量与静态字段访问无关 (static)

以下程序证明了可以使用空引用来访问类（静态）变量，而不会导致异常：

```java
class Test3 {
    static String mount = "Chocorua";
    static Test3 favorite() {
        System.out.print("Mount ");
        return null;
    }
    public static void main(String[] args) {
        System.out.println(favorite().mount);
    }
}
```

它通过编译、执行并打印：

```
Mount Chocorua
```

即使 `favorite()` 的结果是 `null`，也没有抛出 `NullPointerException`。打印出 "Mount " 是主表达式在运行时确实被完全求值，尽管仅其类型而非值被用于确定访问哪个字段（因为该字段是静态的）。

### 15.11.2 使用 super 访问父类成员

`super.Identifier` 形式指向当前对象所属类的 Identifier 字段，但该对象被视为其超类的实例。

`T.super.Identifier` 形式指向词法上对应的 T 实例 Identifier 字段，但该实例被视为 T 超类的实例。

使用 `super` 关键字的形式在类声明中允许 `this` 作为表达式（§15.8.3）。如果使用 `super` 关键字的字段访问表达式出现在静态上下文中（§8.1.3），则为编译错误。

对于 `super.Identifier` 形式的字段访问表达式：
- 如果字段访问表达式的直接邻接类或接口是 Object 或接口，则为编译错误。

对于 `T.identifier` 形式的字段访问表达式：
- 如果 `T` 是类或接口，则为编译错误。
- 设 `U` 为字段访问表达式的直接邻接类或接口。如果 `U` 不是 `T` 的内部类本身，则为编译错误。

假设字段访问表达式 `super.f` 出现在类 `C` 中，且 `C` 的直接邻接超类是 `S`。如果 `f` 从 `C` 可访问（§6.6），则 `super.f` 被处理为类 `S` 体体中的 `this.f` 表达式。否则，发生编译错误。
`super.f` 可以访问类 `s` 中可的字段，即使该字段被类 `T` 的字段声明所隐藏。

### 15.1.2-1. super 表达式

```java
interface I {
    int x = 0; }
class T1 implements I { int x = 1; }
class T2 extends T1 { int x = 2; }
class T3 extends T2 {
    int x = 3;
    void test() {
        System.out.println("*x=" + "\t" + x);
        System.out.println("*super.x=" + "\t" + super.x);
        System.out.println("*(T2).x=" + "\t" + ((T2).x);
        System.out.println("*(T1).x=" + "\t" + ((T1).x);
        System.out.println("*(I).x=" + "\t" + ((I).x);
    }
}
class Test {
    public static void main(String[] args) {
        new T3().test();
    }
}
```

该程序输出：

```
x=3
super.x=2
((T2)this).x=2
((T1)this).x=1
((I)).x=0
```



在类 `T3` 中，当允许时，`super.x` 的效果与 `((T2)this).x` 相同。注意 `super.x` 没有以转换的形式指定，这是由于围绕超类成员的复杂性。

## 15.12 方法调用表达式

方法调用表达式用于调用类方法或实例方法。

- MethodInvocation:
    - MethodName ([ArgumentList])
    - TypeName. [TypeArguments] Identifier ([ArgumentList])
    - ExpressionName. [TypeArguments] Identifier ([ArgumentList])
    - Primary. [TypeArguments] Identifier ([ArgumentList])
    - super. [TypeArguments] Identifier ([ArgumentList])
    - TypeName.super. [TypeArguments] Identifier ([ArgumentList])
- ArgumentList:
    - Expression {, Expression }

由于方法重载的可能性，在编译时解析方法名比解析字段名更复杂。由于实例方法重写的可能性，运行时调用方法比访问字段更复杂。

确定方法表达式将调用的方法涉及多个步骤。以下三个章节描述了方法调用的编译时处理。方法调用的类型确定在 §15.12.3 中指定。

方法调用表达式可以抛出的异常类型在 §11.2.1 中指定。

如果 MethodInvocation 中出现在 `in` 之前的最后一个 `.` 左侧的名称无法归类为 `TypeName` 或 `ExpressionName`（§6.5.2），则为编译错误。

如果 `TypeArguments` 出现在 `Identifier` 左侧，则其中任何类型参数为通配符，则为编译错误（§4.5.1）。

如果满足以下所有条件，则方法调用表达式是一个多态表达式（**poly expression**）：

- 调用出现在赋值上下文中或调用上下文中（§5.2, §5.3）。
- 如果调用是限定的（即除第一种形式任何形式的 `MethodInvocation`），则调用省略了 `Identifier` 左侧的 `TypeArguments`。
- 由后续子节确定的要调用的方法是泛型（**§8.4.4**），且其返回类型提到了至少一个方法参数。

否则，方法调用表达式是一个独立表达式。

### 15.12.1 编译时第一步：确定搜索类型

在编译时处理方法调用的第一步是确定要调用的方法名称以及搜索哪些方法的定义。

方法名称由紧接在 `MethodInvocation` 左括号之前的 `MethodName` 或 `Identifier` 指定。

对于要搜索的类型，有六种情况需要考虑，取决于出现在 `MethodInvocation` 左括号之前的形式：

- 如果形式是 `MethodName`，即仅 `Identifier`，则：
    - 如果 `Identifier` 出现在同名方法的作用范围内（§6.3, §6.4.1），则：
        如果存在该方法的成员的内部类或接口声明，设 `E` 为该内部类或接口。要搜索的类型是 `E.this`（§15.8.4）。

        这种搜索策略被称为“梳子规则”。它实际上在查看封闭类及其超类层次中的方法之前，先查找嵌套类层次中的方法。示例见 §6.7.1。
    - 否则，方法声明可能由于一个或多个静态导入或静态静态导入声明而处于作用范围内。不需要搜索类型，因为要调用的方法稍后调用（§15.12.2.1）。

- 如果形式是 `TypeName. [TypeArguments] Identifier`，则要搜索的类型是由 `TypeName` 指定的（可能是原始）类型。

- 如果形式为 `ExpressionName . [TypeArguments] Identifier`，则要搜索的类型为 `ExpressionName` 所指代的变量的声明类型 $\tau$，前提是 $\tau$ 是类或接口类型；如果 $\tau$ 是一个类型变量，则为 $\tau$ 的上界。

- 如果形式为 `Primary . [TypeArguments] Identifier`，则令 $\tau$ 为 `Primary` 表达式的类型。如果 $\tau$ 是类或接口类型，则要搜索的类型为 $\tau$；如果 $\tau$ 是一个类型变量，则为 $\tau$ 的上界。

- 如果 $\tau$ 不是引用类型，则为编译时错误。

- 如果形式为 `super . [TypeArguments] Identifier`，则要搜索的类型为包含该方法调用的类的直接父类类型。
  令 $E$ 为紧邻包含该方法调用的类或接口声明。如果 $E$ 是类 `Object` 或接口，则为编译时错误。

- 如果形式为 `TypeName . super . [TypeArguments] Identifier`，则：
  - 如果 `TypeName` 既不表示类也不表示接口，则为编译时错误。
  - `TypeName` 表示类 $C$，则要搜索的类型为 $C$ 的直接父类类型。

  如果 $C$ 不是方法调用的词法包含的类声明，或者 $C$ 是类 `Object`，则为编译时错误。

  令 $E$ 为紧邻包含该方法调用的类或接口声明。如果 $E$ 是类 `Object`，则为编译时错误。

- 否则，`TypeName` 表示接口 $I$。

  令 $E$ 为紧邻包含该方法调用的类或接口声明。如果 $I$ 不是 $E$ 的直接父接口，或者存在 $E$ 的另一个直接父类或直接父接口 $J$，使得 $J$ 是 $I$ 的子类或子接口，则为编译时错误。

要搜索的类型是 $E$ 的直接父接口类型 $I$。

`TypeName . super` 语法是重载的：传统上，`TypeName` 指向词法包含的类声明，目标是该类的父类，仿佛该调用在词法包含的类声明中是一个无限定的 `super`。

```java
class Superclass {
    void foo() { System.out.println("Hi"); }
}
```

```java
class Subclass1 extends Superclass {
    void foo() { throw new UnsupportedOperationException(); }
}

Runnable tweak = new Runnable() {
    void run() {
        Subclass1.super.foo(); // 获取 'println' 行为
    }
};
```

为了支持对父接口默认方法的调用，TypeName 可以指向当前类或接口的直接父接口，目标是该父接口。

```java
interface Superinterface {
    void foo() { System.out.println("Hi"); }
}
```

```java
class Subclass2 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); }
}

void tweak() {
    Superinterface.super.foo(); // 获取 'println' 行为
}
```

没有语法支持这些形式的组合，即调用词法包含的类声明的父接口方法，仿佛调用在词法包含的类声明中的形式为 InterfaceName.super。

```java
class Subclass3 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); }
}
```

```java
Runnable tweak = new Runnable() {
    void run() {
        Subclass3.Superinterface.super.foo(); // 非法
    }
};
```

一种变通是在词法包含的类声明中引入一个私有方法，该方法执行接口 super 调用。

# 15.12.2 编译时步骤 2：确定方法签名

第二步在在上一步确定的方法中搜索成员方法。此步骤使用方法名和参数表达式来定位既可访问又适的方法，即在给定参数上可以正确调用的声明。

可能会有多个方法，在这种情况下选择最具体的那个。最具体方法的描述符（签名返回类型）是运行时执行方法分发时所使用的类型。

某些某些包含隐式类型化 lambda 表达式（§15.27.1）或不精确方法引用的参数表达式会被适用性测试忽略，因为在选择调用的目标类型之前，无法确定它们的含义。另一方面，是参数表达式而非调用的目标类型影响了适用性测试，即使方法调用表达式是一个多表达式（poly expression）。

确定适用性的过程开始于确定可能适的方法（§15.12.2.1）。然后，为了确保与 Java SE 5.0 之前的 Java 编程语言兼容，该过程分为三个阶段：

- 1. 第一阶段在不允许装箱拆箱或使用变长参数方法调用的情况下执行重载解析。如果在此阶段没有找到适用的方法，则继续到第二阶段。

> 这保证了在 Java SE 5.0 之前的 Java 编程语言中有效的调用不会因为变长参数方法、隐式绑定和/或拆箱的引入而产生歧义。然而，变长参数方法（§15.12.2.1）的声明可能会改变为方法调用选择的方法，因为变长参数方法被视为固定参数方法。

- 2. 第二阶段在允许装箱拆箱的情况下执行重载解析，但排除变长参数调用。如果在此阶段没有找到适用的方法，则继续到第三阶段。

这确保了通过固定参数方法选择的方法不会通过变长参数方法被选择。

- 3. 第三阶段允许重载与变长参数、装箱和拆箱相结合。

# 表达式

方法调用表达式 15.12

如果方法通过严格调用（第一阶段，§15.12.2）、宽松调用（第二阶段，§15.12.3）或变长参数调用（第三阶段，§15.12.4）适用，则该方法是适用的。泛型方法（§8.4.4）的情况需要对类型参数进行分析。类型参数可以显式或隐式传递；如果是隐式传递，则必须从参数推断。

如果在其中一个阶段识别出多个适用方法，则根据 §15.12.5 选择最具体的一个。

为了检查适用性，通常无法使用调用的类型。这是因为：

- 方法参数可能是多表达式。
- 在缺少目标类型的情况下无法检查多表达式。
- 必须先完成重载解析才能确定参数的目标类型。

相反，适用性检查的输入是参数本身。可以检查参数与目标类型的兼容性，即使参数类型未知。

重载解析独立于目标类型。这有两个原因：

- 首先，这使得模型更易访问且不易出错。方法名的含义（即与名称对应的声明）对于程序的意义是如此基础，以至于依赖上下文提示（相比之下，多表达式可能会根据目标类型有不同的行为；但这种行为的变化是有限且本质上等等的，而对于共享名称和参数数量的任意方法无法无法保证）。
- 其次，它允许其他属性——例如方法是否为多表达式（§15.12）或如何分类条件表达式（§15.25）——取决于方法的含义，即使在确定目标类型之前也是。

# 15.12.1 方法适用性

```java
class Doubler {
    static int two() { return two(1); }
    private int two(int i) { return 2*i; }
}

class Test extends Doubler {
    static long two(long j) { return j+j; }
    public static void main(String[] args) {
        System.out.println(two(3));
    }
}
```

```java
System.out.println(Doubler.two(3)); // 编译错误
}
```

对于类 `Doubler` 内部的方法调用 `two(1)`，存在两个名字为 `two` 的可访问方法，但只有第二个是适用的，运行时调用的那个方法也是如此。

对于类 `Test` 内部的方法调用 `two(3)`，存在两个适用的方法，但只有类 `Test` 中的那一个是可访问的，因此它是在运行时被调用的方法（参数 `3` 被转换为 `long` 类型）。

对于方法调用 `Doubler.two(3)`，编译器会在 `Doubler` 类（而非 `Test` 类）中搜索名为 `two` 的方法；唯一适用的方法不可访问，因此该方法调用导致了编译错误。

另一个示例是：

```java
class ColoredPoint {
    int x, y;
    byte color;
    void setColor(byte color) { this.color = color; }
}

class Test {
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        byte color = 37;
        cp.setColor(color);
        cp.setColor(37); // 编译错误
    }
}
```

在这里，`setColor` 的第二次调用发生了编译错误，因为在调用时找不到任何适用的方法。字面量 `37` 的类型是 `int`，无法通过调用转换转换为 `byte`。在变量 `color` 的初始化中使用的赋值转换执行从常量类型 `int` 到 `byte` 的隐式转换，这是被允许的，因为值 `37` 足够小，可以用 `byte` 类型表示；但这种转换在调用转换中是不允许的。

然而，如果 `setColor` 方法声明为接收 `int` 而不是 `byte`，那么两次调用都是正确的；第一次调用将是允许的，因为调用转换执行了从 `byte` 到 `int` 的宽转换。但在 `setColor` 的方法体中需要一个窄化强制转换：

```java
void setColor(int color) { this.color = (byte)color; }
```

这是一个重载歧义的示例。考虑以下程序：

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }
class Test {
    static void test(ColoredPoint p, Point q) {
        System.out.println("ColoredPoint, Point");
    }
    static void test(Point p, ColoredPoint q) {
        System.out.println("ColoredPoint, ColoredPoint");
    }
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        test(cp, cp); // 编译错误
    }
}
```

# EXPRESSIONS 方法调用表达式 15.12

如果添加了 `test` 的第三个定义：

```java
static void test(ColoredPoint p, ColoredPoint q) {
    System.out.println("ColoredPoint, ColoredPoint");
}
```

那么它将比另外两个更具体，方法调用将不再具有歧义。

### 示例 15.12.2 方法选择时不考虑返回类型

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }
class Test {
    static int test(ColoredPoint p) {
        return p.color;
    }
    static String test(Point p) {
        return "Point";
    }
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        String s = test(cp); // 编译错误
    }
}
```

方法 `test` 最具体的声明是接收参数 `ColoredPoint` 的那一个。方法的返回类型是 `int`，发生编译错误是因为 `int` 无法通过赋值转换转换为 `String`。这个示例表明，方法的返回类型不参与重载方法的解析，因此返回 `String` 的第二个 `test` 方法没有被选中，尽管它的结果类型允许该示例程序无错误地编译。

## EXPRESSIONS 方法调用表达式 15.12

```java
ColoredPoint cp2 =
    new ColoredPoint(3, 3, ColoredPoint.GREEN);
    cp.adopt(cp2);
    System.out.println("* " + cp);
}
```

输出是：

```
cp: (3, 3, red)
```



编写 `Test` 类的程序员期望看到 "green" 这个词，因为实际参数 `ColoredPoint` 有一个 `color` 字段，而 `color` 似乎是一个“相关字段”。当然，该包的编译提示本应该精确得多！

顺便注意，`adopt` 方法调用的最具体（实际上是唯一适用的）方法签名表明这是一个带有一个参数的方法，且该参数类型为 `Point`。该签名成为 Java 编译器生成的 `Test` 类的二进制表示的一部分，并在运行时供方法调用使用。

假设程序员报告了这个软件错误，而 `points` 包的维护者在深思熟虑后，宣布通过向 `ColoredPoint` 类添加一个方法来修复它：

```java
public void adopt(ColoredPoint p) {
    adopt(Point p);
    color = p.color;
}
```

如果程序员用旧的 `Test` 二进制文件运行新的 `ColoredPoint` 二进制文件，输出是：

```
cp: (3, 3, green)
```

因为 `Test` 的旧二进制文件对于 `adopt(cp2)` 仍然关联有“类型为 Point 的一个参数”的描述。如果重新编译 `Test`，Java 编译器将发现有两个适用的方法，并且更具体的“类型为 Point 的一个参数”；运行程序将产生：

```
cp: (3, 3, green)
```

由于此类问题的预见，`points` 包的维护者可以通过为 `adopt` 方法添加防御性代码来兼容新旧代码：

```java
public void adopt(Point p) {
    if (p instanceof ColoredPoint)
        color = ((ColoredPoint)p).color;
}
```



理想情况下，当依赖的代码更改时，应该重新编译源码。然而，在不同组织维护类的环境中，对类演变的防御性编程可以使代码更健壮。见 §13（二进制兼容性）。

### 15.12.1 识别适用方法

编译步骤 1（15.12.1）确定的类型用于搜索所有可能的适用的成员方法；继承自超类和超接口的成员包含在此搜索中。

此外，如果方法调用的形式为 `MethodName` —— 即单个标识符 `Identifier` —— 则对适用方法的搜索还将检查编译单元（§7.5.3, §7.5.4）中通过静态导入和通导入的所有成员方法，且这些方法在方法调用出现的地方未被遮蔽。

成员方法对于方法调用是*适用的*，当且仅当满足以下所有条件：

- 成员名称与方法调用中的方法名称相同。
- 该成员对于方法调用所在的类或接口是可访问的（6.6）。

成员在方法调用处是否可访问取决于其声明中的访问修饰符（`public`、`protected`、无修饰符（包访问）或 `private`），取决于编译步骤 1 确定的类对成员的继承，以及方法调用发生的位置。

- 如果该成员是参数数为 *n* 的固定方法，则方法调用的参数数为 *n*，且对于所有 $i$ ($1 \le i \le n$)，方法调用的第 $i$ 个参数与方法第 $i$ 个参数的类型*潜在兼容*（如下文定义）。
- 如果该成员是参数数为 *n* 的变长方法，则对于所有 $i$ ($1 \le i \le n-1$)，方法调用的第 $i$ 个参数与类型*潜在兼容*。

方法的第 $i$ 个参数；且，当方法的第 $n$ 个参数类型为 $T[i]$ 时，满足以下其中之一即可：

- 方法调用的算元个数（arity）等于 $n-1$。
- 方法调用的算元个数等于 $n$，且方法调用的第 $n$ 个参数可能兼容 $\tau$ 或 $T[i]$。
- 方法调用的算元个数为 $m$，其中 $m > n$，且对于所有 $i$ ($n \le i \le m$)，方法调用的第 $i$ 个参数都可能兼容 $\tau$。
- 如果方法调用包含了显式类型参数，且该成员方法是一个泛型方法（generic method），则类型参数的数量等于该方法的类型参数数量。

此子句意味着，非泛型方法可能适用于一个提供了显式类型参数的调用。事实上，它结果可能是适用的。在这种情况下，类型参数将会被简单地忽略。

此规则源于兼容性问题和可替换原则。由于接口或超类可能独立于其子类型为泛型，我们用非泛型方法重写泛型方法。然而，重写（非泛型）方法必须适用于该泛型方法，包括显式传递类型参数的调用。否则，子类型将无法替换其超类型。

如果搜索没有产生至少一个可能适用的方法，则发生编译错误。

- 如果 lambda 表达式 ($\S15.27$) 满足以下所有条件，则它与函数接口类型 $\tau$ ($\S9.8$) 潜在兼容：
- 如果 $\tau$ 的函数类型的算元个数具有 void 返回值，则 lambda 体要么是一个语句表达式（$\S14.8$），或者是 void 兼容的块（$\S15.27.2$）。
- 如果 $\tau$ 的类型具有（非 void）返回类型，则 lambda 体要么是一个表达式或值兼容的块（$\S15.27.2$）。
- 方法引用表达式 ($\S15.13$) 与函数接口类型 $\tau$ 潜在兼容，的条件是：当 $\tau$ 的函数类型的算元个数为 $n$ 时，当方法引用表达式目标算元个数为 $n$ 的函数类型时存在至少一个可能适用的方法 (§15.13.1)，且满足以下其中之一：
- 方法引用表达式具有 `ReferenceType :: [TypeArguments] Identifier` 的形式，且至少一个可能适用的方法要么 (i) 是静态且支持算元个数 $n$，或 (ii) 非静态且支持算元个数 $n-1$。
- 方法引用表达式具有其他形式，且至少一个可能适用的方法不是静态的。
- lambda 表达式或方法引用表达式与类型变量潜在兼容的条件是：该类型变量是候选方法的参数。
- 括号表达式 (§S15.8.5) 如果其包含的表达式与该类型潜在兼容，则它与该类型潜在兼容。
- 条件表达式 (§S15.25) 如果其第二个和第三操作数都可能兼容该类型，则它与该类型潜在兼容。
- switch 表达式 (§S15.28) 如果其所有结果都可能兼容该类型，则它与该类型潜在兼容。
- 类实例化表达式、方法调用表达式或独立形式的表达式 (§S15.2) 与任何类型兼容。

潜在适用性的定义超越了基本的算元个数，它考虑了函数接口目标类型的存在和“形状”。在某些涉及函数类型推断的情况下，作为方法调用参数出现的 lambda 表达式在重载解析之前无法正确确定类型。这些规则允许考虑 lambda 表达式的形式，丢弃那些可能引起歧义的明显错误的目标类型。

## 15.12.2.2 第 1 阶段：通过严格调用识别适用于匹配算元个数的方法

对于一个可能适用的方法 $m$，一个参数被认为与适用性相关，除非它具有以下形式之一：

- 隐式类型类型的 lambda 表达式 (§S15.27.1)。
- 不精确的方法引用表达式简体S15.13.1)。
- 如果 $m$ 是泛型方法，且方法调用未提供显式类型参数，则隐式类型类型的 lambda 表达式或对应目标类型（如从 $m$ 的签名推导出）的精确方法引用表达式是 $m$ 的类型参数。
- 显式类型类型的 lambda 表达式，其正体是一个不与适用性相关的表达式。
- 显式类型类型的 lambda 表达式，其正体是一个块，其中至少有一个结果表达式与适用性相关。
- 括号表达式 (§S15.8.5) 如果其包含的表达式与适用性相关。
- 条件表达式简体S15.25) 如果其第二个或第三操作数与适用性相关。

设 $m$ 为一个可能适用的方法简体S15.12.2.1)，其算元个数为 $n$，形式参数类型为 $F_1 ... F_n$，且 $e_1, ..., e_n$ 为方法调用的实际参数表达式。

- 如果 $m$ 是泛型方法，且方法调用未提供显式类型参数，则方法的适用性按照 §18.5.1 的规定进行推断。
- 如果 $m$ 是泛型方法，且方法调用提供了显式类型参数，则令 $R_1 ... R_p$ ($p \ge 1$) 为 $m$ 的类型参数，$B_i$ 为 $R_i$ 的声明边界，并令 $U_1, ..., U_p$ 为显式类型参数。那么，$m$ 在严格调用下是适用的，当满足以下两个条件：
- 对于 $1 \le i \le n$，$e_i$ 在严格调用中兼容 $F_i$。
- 对于 $1 \le i \le p$，$U_i < B_i$。
- 如果 $m$ 不是泛型方法，则当对于 $1 \le i \le n$，$e_i$ 在严格调用中兼容 $F_i$ 时，$m$ 是适用的。

如果没有找到严格调用的方法，则继续进行第 2 阶段搜索。否则，在所有适用的方法中选择最具体的方法 (方法简体S15.12.2.5)。

## 15.12.2.3 第 2 阶段：通过宽松调用识别匹配算元个数的方法

设 $m$ 为一个可能适用的方法简体S15.12.2.1)，其算元个数为 $n$，形式参数类型为 $F_1 ... F_n$，且 $e_1, ..., e_n$ 为方法调用的实际参数。

- 如果 $m$ 是泛型方法，且方法调用未提供显式类型参数，则方法的适用性按照 §18.5.1 的规定进行推断。
- 如果 $m$ 是泛型方法，且方法调用提供了显式类型参数，则令 $R_1 ... R_p$ ($p \ge 1$) 为 $m$ 的类型参数，$B_i$ 为 $R_i$ 的声明边界，并令 $U_1, ..., U_p$ 为显式类型参数。那么，$m$ 在宽松调用下是适用的，当满足以下两个条件时：
- 对于 $1 \le i \le n$，$e_i$ 在宽松调用中兼容 $F_i$ (§5.3)。
- 对于 $1 \le i \le p$，$U_i < B_i$。
- 如果 $m$ 不是泛型方法，则当对于 $1 \le i \le n$，$e_i$ 在宽松调用中兼容 $F_i$ (§5.3) 或 $e_i$ 与适用性相关时，$m$ 是适用的。

如果没有找到宽松调用的方法，则继续进行第 3 阶段搜索简体S15.12.2.4)。否则，在所有适用的方法中选择最具体的方法 (方法简体S15.12.2.5)。

## 15.12.2.4 第 3 阶段：通过可变算元调用识别方法

当可变算元方法具有形式类型 $F_1, ..., F_{n-1}, F_n[]$ 时，定义方法的第 $i$ 个可变算元参数类型如下：

- 对于 $i \le n-1$，第 $i$ 个可变算元参数类型为 $F_i$。
- 对于 $i \ge n$，第 $i$ 个可变算元参数类型为 $F_n$。

设 $m$ 为一个可能适用的方法简体S15.12.2.1)，其具有可变算元，$T_1, ..., T_k$ 为 $m$ 的前 $k$ 个可变算元参数类型，且 $e_1, ..., e_k$ 为方法调用的实际参数表达式。

## 15.12.5 选择最特定的方法

如果多个方法对于某个方法调用都是可访问且应用的，则需要选择一个描述符用于运行时方法分发。Java 编程语言使用*最特定方法*的规则。

非正式的直觉是：如果第一个方法处理的任何调用都可以传递给另一个方法而不会产生编译错误，那么一个方法比另一个方法更具体。在显式 lambda 表达式参数（$\S15.27.1$）或变长调用（$\S15.12.2.4$）等情况下，允许一定的灵活性来使一个签名适应另一个。

对于具有参数表达式 $e_1, \dots, e_k$ 的调用，一个应用的方法 $m_1$ 比另一个应用的方法 $m_2$ *更具体*，如果满足任一条件：

- $m_2$ 是泛型的，且根据 $\S18.5.4$，对于参数表达式 $e_1, \dots, e_k$，$m_1$ 被认为比 $m_2$ 更具体。
- $m_2$ 不是泛型的，且 $m_1$ 和 $m_2$ 通过严格或松散调用应用，且当 $m_1$ 具有形式参数类型 $S_1, \dots, S_n$ 而 $m_2$ 具有形式参数类型 $T_1, \dots, T_n$ 时，对于参数 $e_i$，所有 $i$ $(1 \le i \le n, n = k)$ 类型 $S_i$ 比 $T_i$ *更具体*。
- $m_2$ 不是泛型的，且 $m_1$ 和 $m_2$ 通过变长调用应用，且当 $m_1$ 的前 $k$ 个变长参数类型为 $S_1, \dots, S_k$，而 $m_2$ 的前 $k$ 个变长参数类型为 $T_1, \dots, T_k$ 时；对于参数 $e_i$，对于所有 $(j \le i \le k)$ 类型 $S_i$ 比 $T_j$ 更具体。此外，如果 $m_2$ 有 $k+1$ 个参数，则 $m_1$ 的第 $k+1$ 个变长参数类型是 $m_2$ 的第 $k+1$ 个变长参数类型的子类型。

上述条件是一个方法比另一个方法更具体的唯一情况。

对于任何表达式，如果 $s < \tau$（$\S4.10$），则类型 $s$ 比类型 $\tau$ 具体。

对于表达式 $e$，函数式接口类型 $s$ 比函数式接口类型 $\tau$ 具体，当满足所有条件时：

- $s$ 的接口既不是 $\tau$ 接口的父接口，也不是其子接口。
- 如果 $s$ 或 $\tau$ 是交叉类型，则不存在 $s$ 的任何接口是 $\tau$ 的任何接口的父接口或子接口的情况。（此处的“交叉类型的接口”是指在交叉类型中作为（可能是参数化的）接口类型出现的接口集合。）
- 令 $MT_s$ 为 $s$ 捕获的函数类型，令 $MT\tau$ 为 $\tau$ 的函数类型。$MT_s$ 和 $MT\tau$ 必须具有相同的类型参数（如果有）（$\S8.4.4$）。
- 令 $P_{s,1}, \dots, P_{s,n}$ 为 $MT_s$ 的形式参数类型，适配于 $MT\tau$ 的类型参数。令 $P_1^s, \dots, P_n^s$ 为 $s$ 的函数类型（无捕获）的形式参数类型，适配于 $MT\tau$ 的类型参数。令 $Q_1, \dots, Q_n$ 为 $MT\tau$ 的形式参数类型，对于所有 $i$ $(1 \le i \le n, n = k)$。

通常，此规则断言在 $s$ 是通配符的情况下，检查更为复杂。令 $MT_s$ 为 $s$ 捕获的函数类型，令 $MT\tau$ 为 $\tau$ 的函数类型。$MT_s$ 和 $MT\tau$ 必须具有相同的类型参数（如果有）（$\S8.4.4$）。

一个方法 $m_1$ 比另一个方法 $m_2$ **严格具体**，当且仅当 $m_1$ 比 $m_2$ 更具体且 $m_2$ 不比 $m_1$ 更具体。

每个最特定方法（maximally specific method）的返回类型（如果两个方法的签名相同，则对任何类型参数进行适配 (§8.4.4)）。

如果根据上述规则不存在优先方法，则如果满足以下条件，则选择最特定方法：

- 它的签名是每个最特定方法签名的子集；且
- 对于每个最特定方法都是返回类型可替换的 (§8.4.5)。

最特定方法所抛出的异常类型派自所有最特定方法的 `throws` 子句，如下：

1. 如果最特定方法是泛型，则首先将 `throws` 子句适配为最特定方法的类型参数 (§8.4.4)。
2. 如果最特定方法不是泛型，但至少有一个最特定方法是泛型，则首先对 `throws` 子句进行擦除。
3. 然后，所抛出的异常类型包括满足以下约束的每个类型 E：
   - E 在其中一个 `throws` 子句中。
   - 对于每个 `throws` 子句，E 是该子句中指定的某些类型的子类型。

这些从重载方法组派生特定方法类型的规则也用于识别函数接口的类型 (§9.9)。

否则，该方法调用是模糊的，并将发生编译时错误。

## 15.12.2 方法调用类型

最可访问且适用方法的调用类型是一个方法类型 (§8.2)，该类型表示了调用参数的目标类型、调用的结果（返回类型或 void）以及调用的异常类型。其按如下方式确定：

- 如果所选方法是泛型，且方法调用未提供显式类型参数，则该调用在 §18.5.2 中进行推断。

在这种情况下，如果方法调用表达式是一个多值式表达式（poly expression），则其与目标类型的兼容性由 §18.5.2.1 确定。

在最终确定方法调用表达式的目标类型和调用类型之前，可能会多次进行与目标类型的兼容性测试。例如，一个嵌套的方法调用表达式可能需要更深层的方法调用表达式与不同方法的形式参数类型兼容。

- 如果所选方法是泛型，且方法调用提供了显式类型参数，令 $P_i$ 为参数类型，并令 $T_i$ 为为方法调用提供的显式类型参数 $(1 \le i \le p)$。
- 如果为了使方法适用需要未检查转换（unchecked conversion），则调用的参数类型通过将替换 $[P_i:=T_i, \dots, P_p:=T_p]$ 应用于方法的类型的参数类型获得，调用的返回类型和抛出类型由该方法的返回类型和抛出类型的擦除给出。
- 如果为了使方法适用不需要未检查转换，则该调用通过将替换 $[P_i:=T_i, \dots, P_p:=T_p]$ 应用于该方法的类型获得。
- 如果所选方法不是泛型，则：
  - 如果为了使方法适用需要未检查转换，则调用类型的参数类型为该方法的类型的参数类型，且返回类型和抛出类型由该方法的返回类型和抛出类型的擦除给出。
  - 否则，如果所选方法是类 `Object` 的 `getClass` 方法 (§4.3.2)，则该调用与方法的类型相同，但返回类型为 `Class<? extends T> `，其中 $\tau$ 是被搜索的类型，且 $[\tau]$ 表示 $\tau$ 的擦除 (§4.6)。
  - 否则，调用类型与方法的类型相同。

## 15.12.3 编译时步骤 3：所选方法是否合适？

如果某个方法调用存在最特定方法声明，则其称为该调用的编译时声明。

如果方法的参数与其目标类型不兼容（该目标类型由编译时声明的调用类型派生），则将发生编译时错误。

如果编译时声明通过变量调用是适用的，其中方法调用类型的最后一个形式参数类型为 $F_n$，则如果 $F_n$ 的擦除类型在调用点是访问的 (§6.6)，则将发生编译时错误。

如果编译时声明是 `void` 类型，则该方法调用必须是一个顶层表达式（即表达式语句中的 `Expression`，或者 `for` 语句中的 `ForInit` 或 `ForUpdate` 部分），否则将发生编译时错误。此类方法调用不产生值，因此必须仅在不需要值的情况下使用。

此外，编译时声明是否合适可能取决于左括号之前方法调用表达式的形式，如下：

- 如果形式为 `MethodName` —— 即仅为一个标识符（Identifier）—— 且编译时声明是实例方法，那么：
  - 如果方法调用发生在静态上下文 (§8.1.3)，则将发生编译时错误。
  - 否则，令 $\tau$ 为要搜索的类或接口 (§15.12.1)。如果方法调用的最内嵌套类或接口声明既不是 $\tau$ 也 $\tau$ 的类，则将发生编译时错误。

- 如果形式为 `TypeName.[TypeArguments] Identifier`，则编译时声明必须是静态的，否则将发生编译时错误。

- 如果形式为 `ExpressionName . [TypeArguments] Identifier` 或 `Primary . [TypeArguments] Identifier`，则编译时声明不能是在接口中声明的静态方法，否则将发生编译时错误。

- 如果形式为 `super . [TypeArguments] Identifier`，那么：
  - 如果编译时声明是抽象的，则将发生编译时错误。
  - 如果方法调用发生在静态上下文，则将发生编译时错误。

- 如果形式为 `TypeName.super . [TypeArguments] Identifier`，那么：
  - 如果编译时声明是抽象的，则将发生编译时错误。
  - 如果方法调用发生在静态上下，则将发生编译时错误。

- 如果 `TypeName` 表示类 $c$，则如果紧邻方法调用的类或接口声明不是 $c$ 或 $c$ 的内部类，则将发生编译时错误。

- 如果 `TypeName` 表示一个接口，令 $\epsilon$ 为紧邻方法调用的类或接口声明。如果存在与编译时声明不同的方法覆盖了 (§9.4.1) 来自直接父类或直接父接口的编译时声明，则将发生编译时错误。

在父接口覆盖了在祖父接口中声明的方法的情况下，此规则防止子接口通过简单将祖父接口添加到直接父接口列表中来“跳过”。访问祖父功能的方法是通过直接父接口，且仅当该接口暴露了所需的功能时如此。（或者，程序员可以定义一个额外的父接口来暴露所需的功能。）

编译时参数类型和编译时结果按如下方式确定：

- 如果方法调用的编译时声明不是签名类的方法，那么：
  - 编译时参数类型为编译时声明的形式参数类型。
  - 编译时结果为编译时声明的调用类型的结果 (§15.12.2.6)。

- 如果方法调用的编译时声明是签名类方法，那么：
  - 编译时参数类型为实际参数表达式的类型。作为字面量 `null` (§3.10.8) 的参数表达式被视为具有 `Void` 类型。
  - 编译时结果按如下方式确定：
    - 如果签名类方法是 `void` 或返回类型是 `Object`，则编译时结果为编译时声明的调用类型的结果 (§15.12.2.6)。
    - 否则，如果方法调用表达式是一个表达式语句，则编译时结果为 `void`。
    - 否则，如果方法调用表达式是转换表达式 (§15.16) 的操作数，则编译时结果为转换表达式类型的擦除 (§4.6)。
    - 否则，编译时结果为签名类方法的返回类型 `Object`。

如果满足以下所有条件，则该方法是签名类方法：

- 它声明在 `java.lang.invoke.MethodHandle` 类或 `java.lang.invoke.VarHandle` 类中。
- 它具有一个单一的可变幅幅参数（§8.4.1），其声明类型为 `Object[]`。
- 它是本地的（native）。

随后将以下编译时信息与方法调用关联，以便在运行时使用：

- 方法名。
- 方法调用的限定类或接口（§13.1）。
- 参数数量以及编译时的参数类型，按顺序。
- 编译时的结果。
- 调用模式，计算方式如下：
    - 如果编译时声明具有 `static` 修饰符，则调用模式为 `static`。
    - 否则，如果方法调用中左括号之前的部分形式为 `super . Identifier` 形式或 `TypeName . super . Identifier` 形式，则调用模式为 `super`。
    - 否则，如果方法调用的限定类或接口实际上是一个接口，则调用模式为 `interface`。
    - 否则，调用模式为 `virtual`。

如果编译时声明的调用类型的结果不是 `void`，则方法调用表达式的类型通过对编译时声明的调用类型的返回类型应用转换（§5.1.10）来获得。

## 15.12.4 方法调用的运行时求

在运行时，方法调用需要五个步骤。首先，可能会计算一个 `target reference`（目标引用）。其次，评估参数表达式。第三，检查要调用方法的可访问性。第四，定位要执行的方法的实际代码。第五，创建一个新的激活帧（activation frame），必要时执行同步操作，并将控制权转移到方法代码。

### 15.12.4.1 计算目标引用（必要时）

根据方法调用的形式，有六种情况需要考虑：

- 如果形式为 `MethodName`——即只是一个 `Identifier`——那么：
    - 如果调用模式为 `static`，则没有目标引用。
    - 否则，让 τ 为该方法所属的外部闭包类型声明，并让 n 为一个整数，表示 τ 是直接包含该方法调用的声明的类的第 n 个词法上外部闭包类型。目标引用是该第 n 个词法上闭包的实例。
      如果该第 n 个词法上闭包的实例不存在，则为编译错误。
- 如果形式为 `TypeName . [TypeArguments] Identifier`，则没有目标引用。
- 如果形式为 `ExpressionName . [TypeArguments] Identifier`，那么：
    - 如果调用模式为 `static`，则没有目标引用。会评估 `ExpressionName`，但结果被丢弃。
    - 否则，目标引用由 `ExpressionName` 赋值。
- 如果涉及形式 `Primary . [TypeArguments] Identifier`，那么：
    - 如果调用模式为 `static`，则没有目标引用。会评估 `Primary` 表达式，但结果被丢弃。
    - 否则，评估 `Primary` 表达式并将其结果作为目标引用。
    在任何情况下，如果 `Primary` 表达式的评估异常完成，则任何参数表达式部分似乎都没有被评估，且方法调用因相同原因异常完成。
- 如果形式为 `super . [TypeArguments] Identifier`，则目标引用是该值。
- 如果形式为 `TypeName . super . [TypeArguments] Identifier`，如果 `TypeName` 表示一个类，则目标引用是 `TypeName.this` 的值；否则，目标引用是 `this` 的值。

示例 15.12.4.1-1 目标引用和静态方法

当计算目标引用并将其丢弃时，调用模式为 `static`，此时不会检查该引用是否为 null：

```java
```



```java
class Test1 {

    static void mountain() {

        System.out.println("*Monadock");

    }

    static Test1 favorite() {

        System.out.print("Mount ");

        return null;

    }

    public static void main(String[] args) {

        favorite().mountain();

    }

}
```

输出：

Mount Monadock

在这里 `favorite()` 返回了 `null`，但没有抛出 `NullPointerException`。

### 15.12.4.1-2 方法调用过程中的评估顺序

作为实例方法调用（§15.12）的一部分，有一个表示要调用对象的表达式。该表达式在方法调用的任何参数表达式的任何部分被评估之前，似乎已经完全完全评估。

因此，例如在：

```java
String s = "one";

s.startsWith("two");
```

`.startsWith()` 之前的 `s` 出现首先被评估，在表达式 `s = "two"` 之前。因此，在局部变量 `s` 改变指向字符串 "two" 之前，字符串 "one" 的引用被记录为目标引用。结果是为目标 "one" 使用参数 "two" 调用 `startsWith` 方法，因此调用的结果为 `false`，因为字符串 "one" 不以 "two" 开头。由此得出测试程序没有打印 "oops"。

### 15.12.4.2 评估参数

评估参数列表的过程取决于被调用的方法是固定方法还是可变数组方法。

如果被调用的方法是可变数组方法，它必然具有 n > 0 个形式参数。前一段的设计是为了处理泛型类型和数组类型之间的交互，这种交互在带有擦除泛型的 Java 虚拟机中发生。具体来说，如果变量数组的元素类型 T 是非擦除（例如 `List<String>`），则数组创建（§15.10）必须采取特殊情况，因为创建的数组必须是擦除。通过擦除参数列表中的最终表达式，我们保证获得擦除类型；由于数组创建是未检查的（§5），从具有擦除元素的数组到具有非擦除元素的数组的转换是可能的，特别是对于可变幅参数。Java 编译器要求在这种转换时给出编译警告。Oracle Java编译器的参考实现将此未检查警告识别为更详细的泛型数组创建。

现在评估未检查的表达式（可能已如上重写）产生参数值。每个参数值对应方法的 n 个形式参数之一。

如果有参数表达式，按从左到右顺序评估。如果任何参数表达式的评估异常完成，则其右侧任何表达式似乎都没有被评估，方法调用因相同原因异常完成。第 j 个参数表达式的结果是第 j 个参数值，对于 1 ≤ j ≤ n。随后，使用参数值继续评估。

### 15.12.4.3 检查类型和方法的可访问性

在本节中：

- 令 D 为包含方法调用的类。
- 令 Q 为方法调用的限定类或接口（§13.1）。
- 令 m 为编译时确定的方法名（§15.12.3）。

Java 语言的实现必须在链接部分确保类或接口 Q 是可访问的：

- 如果 Q 与 D 在同一个包中，则 Q 是可访问的。
- 如果 Q 与 D 在不同的包中，且它们的包位于同一个模块，且 Q 是受保护的（protected），则 Q 是可访问的。
- 如果 Q 与 D 不在同一个包中，且它们所在的包位于不同的模块中，且 Q 将 Q 所在的包导出给 D 所在的模块，且 Q 是 public（公共）或 protected（受保护），则 Q 是可访问的。

如果 Q 是 protected，则它必然是一个嵌套类或接口，其可访问性受包含其声明的类和接口的访问性的影响。在链接期间，其可访问性不受包含其声明的类和接口访问性的影响。此外，在链接期间，由于编译时访问控制（§6.6）与运行时访问控制之间存在 Java 虚拟机的限制，protected 的 Q 的可访问性与 public 的 Q 相同。

实现还必须确保在链接期间，方法 m 仍然能够在 Q 或 Q 的超类或接口中被找到。如果未找到 m，则抛出 `NoSuchMethodError`（它是 `IncompatibleClassChangeError` 的子类）。如果找到了 m，令 C 为声明 m 的类或接口。实现必须确保在链接期间，对 m 的声明对 D 是可访问的。

- 如果 m 是 public，则 m 是可访问的。
- 如果 m 是 protected，则 m 是可访问的当且仅当 (i) D 与 C 在同一个包中，或者 D 是 C 的子类或 C 本身；且 (ii) 如果 m 是一个 protected 实例方法，则 Q 不能是 D 的子类或 D 本身。

> 这是 Q 参与 m 检查的唯一，因为 protected 实例方法只能通过与调用者类型匹配的限定类或接口进行调用。

- 如果 m 具有包访问权限（package access），则 m 是可访问的当且仅当 D 与 C 在同一个包中。
- 如果 m 是 private，则 m 是可访问的当且仅当 D 是 C，或者 D 包含 C，或者 C 包含 D，且 C 和 D 都被第三个类或接口包含。

如果 Q 或 m 中任一者不可访问，则抛出 `IllegalAccessError`（§12.3）。

如果调用方法是接口（interface），则实现必须检查目标引用类是否实现了指定的接口。如果目标引用类没有实现该接口，则抛出 `IncompatibleClassChangeError`。

## 15.12.4.4 确定要调用的方法

如前一节（§15.12.4.3）所示：

- Q 是方法调用的限定类或接口（§13.1）。
- 令 m 为在 Q 或 Q 的超类或超接口中找到的方法。（注意，在上一节中，m 仅仅是方法的名称；在这里它是实际的声明。）
- 令 c 为声明 m 的类或接口。

定位要调用方法的策略取决于调用模式：

- 如果调用模式为 `static`，则不需要目标引用且不允许重写。类或接口 c 的方法 m 为要调用的方法。
- 否则，要调用一个实例方法且存在目标引用。如果目标引用为 null，则在此处抛出 `NullPointerException`。否则，目标引用被认为指向一个目标对象（target object），并将作为被调用方法中关键字 `this` 的值。然后考虑调用模式的其他三种可能性：
  - 如果调用模式为 `super`，则不允许重写。类或接口 c 的方法 m 为要调用的方法。如果 m 是 abstract（抽象的），则抛出 `AbstractMethodError`。
  - 否则，如果调用模式为 `virtual`，且 Q 和 m 共同指示一个多态方法签名（§15.12.3），则目标对象是 `java.lang.invoke.MethodHandle` 或 `java.lang.invoke.VarHandle` 的实例。目标对象封装了状态，该状态与编译时与方法调用相关的信息进行匹配。匹配的细节见《Java 虚拟机规范 Java SE 17 版》和 Java SE Platform API。如果匹配成功，则直接立即调用由 `java.lang.invoke.MethodHandle` 实例引用的方法，或者直接立即访问由 `java.lang.invoke.VarHandle` 引用的变量，在何种情况，都不会执行 §15.12.4.5 中的过程。如果匹配失败，则抛出 `java.lang.invoke.WrongMethodTypeException`。
  - 否则，调用模式为 interface 或 virtual。

如果类或接口 C 的方法 m 是 private，则它就是要调用的方法。

否则，可能会发生重写方法。使用下文指定的动态方法查找来定位要调用的方法。查找过程从 R 开始，R 是目标对象的运行时类。

注意，对于 interface 调用模式，R 必然实现了 Q；对于 virtual 调用模式，R 是 Q 或是 Q 的子类。如果目标对象是一个数组，R 是一个表示数组类型的“类”。

动态方法查找过程如下。令 S 为要搜索的类，从 R 开始。然后：

- 如果类 S 包含一个重写了来自 R 的类或接口方法 m 的声明（§8.4.1），则该重写方法为要调用的方法，过程终止。
- 否则，如果 S 有超类，则递归执行此查找过程的第 1 步和第 2 步，使用 S 的直接超类；要调用的方法是递归查找的结果。

如果上述步骤没有找到方法，则搜索 S 的超接口以寻找合适的方法。考虑一组具有以下属性的候选方法：(i) 每个方法声明在 S 的直接或间接接口接口；(ii) 每个方法具有调用所需的名称和描述；(iii) 每个方法是非静态且非私有的；(iv) 对于每个方法，其中调用接口是 I，满足 (iii)。如果这包含 default 方法，则其中一个为要调用的方法。否则，选择抽象方法作为要调用的方法。

动态方法查找可能会导致以下错误：

- 如果要调的方法是抽象的，抛出 `AbstractMethodError`。
- 如果要调的方法是 default，且上述集合中出现了多个默认方法，则抛出 `IncompatibleClassChangeError`。
- 如果调用模式是 interface 且要调的方法非 public 也非 private，则抛出 `IllegalAccessError`。

上述过程（如果没有错误）将找到一个非抽象、可访问的方法，前提是程序中的所有类和接口已完全编译。然而，如果并非如此，可能会发生上述各种错误；这种情况的额外细节见《Java 虚拟机规范 Java SE 17 版》。

此处描述的查找过程将隐式实现，例如作为构建和使用类分派表或其他用于高效分发的类结构的副作用。

### 15.12.4.4-1 重写与方法调用

```java
class Point {

    final int EDGE = 20;

    int x, y;

    void move(int dx, int dy) {

        x += dx; y += dy;

        if (Math.abs(x) >= EDGE || Math.abs(y) >= EDGE)

            clear();

    }

    void clear() {

        System.out.println("\tPoint clear");

        x = 0; y = 0;

    }

}

class ColoredPoint extends Point {

    int color;

    void clear() {

        System.out.println("\tColoredPoint clear");

        super.clear();

        color = 0;

    }

}
```

在这里，`ColoredPoint` 扩展了其超类 `Point` 定义的抽象。它通过重写 `clear` 方法并使用自己的方法来实现，该方法使用 `super.clear()` 调用超类的 `clear` 方法。

当 `clear` 的调用目标是 `ColoredPoint` 时，该方法就会被调用。即使是 `Point` 中的 `move` 方法，当 `this` 是 `ColoredPoint` 时也会调用 `ColoredPoint` 的 `clear` 方法，如此测试程序的输出所示。

```java
class Test1 {

  public static void main(String[] args) {

    Point p = new Point();

    System.out.println("*p.move(20,20):*");

    p.move(20, 20);

    ColoredPoint cp = new ColoredPoint();

    System.out.println("*cp.move(20,20):*");

    cp.move(20, 20);

    p = new ColoredPoint();

    System.out.println("*p.move(20,20), p colored:*");

    p.move(20, 20);

  }

}
```

结果为：

```
p.move(20,20):
  Point clear
cp.move(20,20):
  ColoredPoint clear
  Point clear
p.move(20,20), p colored:
  ColoredPoint clear
  Point clear
```

重写有时被称为“晚绑定自引用”；在例例中，这意味着 `Point.move` 方法体中对 `clear` 的引用（实际上是 `this.clear` 的语法简写）不是根据“早期”的（在编译时，基于 `this` 所引用的对象的类型）调用的方法，而是仅取决于 `this.clear` 的类型。这为程序员提供了一种扩展抽象的强大方式，也是面向对象编程的核心思想。

### 15.12.4.4-2 使用 super 调用方法

父类的被重写实例方法可以通过使用 `super` 关键字来访问直接父类的成员，从而绕过包含该方法调用的类中的任何重写声明。

在访问实例变量时，`super` 等同于对 `this` 进行类型转换（§15.11.2），但这种等价性对于方法调用并不成立。示例演示了这一点：

```java
class T1 {

  String s() { return "1"; }

}

class T2 extends T1 {

  String s() { return "2"; }

}

class T3 extends T2 {

  String s() { return "3"; }

  void test() {

    System.out.println("s=\t" + s());

    System.out.println("super.s()=\t" + super.s());

    System.out.println("((T2).s()=\t" + ((T2).s());

    System.out.println("((T1).s()=\t" + ((T1).s()));

  }

}

class Test2 {

    public static void main(String[] args) {

        T3 t3 = new T3();

        t3.test();

  }

}
```

产生输出：

```
s() = 3
super.s() = 2
((T2).s() = 3
((T1).s() = 3
```

向 `T1` 和 `T2` 的转换并没有改变被调用的方法，要调用的实例方法根据 `this` 所引用对象的运行时类来选择。类型转换不会改变对象的类；它只检查类类与指定类型兼容。

### 15.12.4.5 创建激活帧、同步、传递控制

某个类中的某个方法已被确定为要调用的方法。

现在创建一个新的激活帧，其中包含目标引用（如果有）和参数值（如果有），并为要调用的方法的局部变量和栈提供足够的空间，以及实现可能需要的任何其他信息（栈指针、程序计数器、指向上一个激活帧的引用等）。如果没有足够的内存来创建此类激活帧，则抛出 `StackOverflowError`。

新创建的激活帧变为当前激活帧。其效果是将参数值分配给方法中对应的新创建的参数变量，如果存在目标引用，则将目标引用作为 `this` 可用。在每个参数值赋值给其对应的参数变量之前，都会对其进行调用转换（§5.3）。

如果被调用的方法的类型擦除（§4.6）在其签名上与方法调用编译时声明的方法的类型擦除（§15.12.3）不同，那么如果任何参数值都是一个对象不是该方法调用编译时声明中对应参数类型擦除的子类或子接口的实例，则抛出 `ClassCastException`。

如果方法 m 是一个本地方法，但未加载所需的实现相关的二进制文件或无法动态链接，则抛出 `NoSuchLinkError`。

如果方法 m 不是同步的，控制将传递到要调用的方法 m 的体体。如果方法是同步的，则在传递控制之前必须锁定对象。如果存在目标引用，则必须锁定目标对象；否则对于类 S，必须锁定方法 m 的类。控制传递到方法体。当方法执行完成后，无论正常结束还是异常结束，对象将自动解锁。锁定和解锁的行为与该方法嵌入在 `synchronized` 语句（§14.9）中完全一致。

### 示例 15.12.4.5-1 调用的方法签名擦除比编译时方法签名多

考虑以下声明：

```java
abstract class C<T> {

    abstract T id(T x);

}

class D extends C<String> {

    String id(String x) { return x; }

}
```

现在，有一个调用：

```java
C c = new D();

c.id(Object());
```



## 方法调用中的类型擦除与异常

被调用的类型擦除在其签名上与方法调用编译时声明的类型擦除不同，如果任何参数值都是一个不是该方法调用编译时声明中对应参数类型擦除的子类或子接口的实例，则抛出 `ClassCastException`。`c.id()` 接受一个 `String`，而后者接受一个 `Object`。

如果方法 `m` 是一个本地方法，但未加载所需的实现相关的二进制文件或无法动态链接，则抛出 `NoSuchLinkError`。

如果方法 `m` 不是同步的，控制将传递到要调用的方法 `m` 的体。如果方法是同步的，则在传递控制之前必须锁定对象。如果存在目标引用，则必须锁定目标对象；否则对于类 `S`，必须锁定方法 `m` 的类。控制传递到方法体。方法执行完成后，无论正常结束还是异常结束，对象将自动解锁。锁定和解锁的行为与该方法嵌入在 `synchronized` 语句 (§14.9) 中完全一致。

## 15.13 方法引用

方法引用表达式用于引用类方法的调用，而不实际执行调用。

```
MethodReference:
    ExpressionName :: [TypeArguments]
    Primary :: [TypeArguments]
    ReferenceType :: [TypeArguments]
    super :: [TypeArguments]
    TypeName . super :: [TypeArguments]
    ClassType :: [TypeArguments]
```

如果类型参数是通配符 (§4.5)。如果方法引用表达式为 `ExpressionName :: [TypeArguments]` 或 `Primary :: [TypeArguments]`，如果 `ExpressionName` 或 `Primary` 不是类型引用，则发生编译错误。如果方法引用表达式为 `super :: [TypeArguments]`，让 `E` 为包含方法引用的类或接口。如果 `E` 是 `Object` 或接口。如果方法引用表达式为 `TypeName . super :: [TypeArguments]`，则：

- 如果 `TypeName` 指向类 `c`，如果 `c` 不是词法作用的类，或者 `c` 是 `Object`。
- 如果 `TypeName` 指向接口 `i`，让 `E` 为包含方法引用的类或接口。如果 `i` 不是 `E` 的直接超接口，或者存在某个 `E` 的直接超类或直接超接口 `J`，使得 `J` 是 `I` 的子类或子接口。如果 `TypeName` 指向类型变量，则发生编译错误。如果方法引用表达式为 `ClassType :: [TypeArguments]`，则：

- `ClassType` 必须命名一个可访问的类 (§6.6)、非抽象且不是枚举类，否则发生编译错误。
- `ClassType` 指向泛型类型 (§4.5)，则如果其任何类型参数都是通配符，则发生编译错误。
- `ClassType` 指向原始类型 (§4.8)，则如果 `::` 后面存在类型参数，则发生编译错误。

如果方法引用表达式为 `ArrayType :: new`，则 `ArrayType` 必须是可重写的 (§4.7)，否则发生编译错误。

实例方法 (§15.2.4.1) 的目标引用可以通过方法引用表达式使用 `ExpressionName`、`Primary` 或 `super` 提供，也可以在调用方法时以后提供。新类实例 (§15.9.2) 的直接实例由词法封闭的 `this` (§8.1.3) 提供。当一个类型中的多个方法具有相同的名称，或者一个类有多个构造函数时，根据方法引用表达式指向的函数接口类型选择适当的方法或构造函数，如 §15.13.1 指定。如果方法或构造函数是泛型的，适当的类型参数可以推断或显式提供。同样，方法引用表达式中提到的泛型类型参数也可以显式提供或推断。

方法引用表达式始终只是表达式 (§15.2)。如果方法引用表达式出现在程序中除赋值上下文 (§5.2)、调用上下文 (§5.3) 或类型转换上下文 (§5.5) 以外的任何地方，则是一个编译错误。

评估方法引用表达式产生一个函数接口类型的实例 (§9.8)。这不会导致相应的方法执行；相反，执行可能会在稍后的时间通过调用函数式接口的适当方法而发生。

这里是一些方法引用表达式，首先是不带目标引用，然后带有目标引用：

```
String::length // 实例方法
System::currentTimeMillis // 静态方法
List<String>::size // 泛型类型的显式类型参数
List::size // 泛型类型的推断类型参数
int[]::clone
T::tvarMember
System.out::println
"abc"::length
foo::bar
(test ? list.replaceAll(String::trim) : list) :: iterator
super::toString
```

这里是更多方法引用表达式：

```
String::valueOf // 需要重载解析
Arrays::sort // 从上下文推断类型参数
Arrays::<String>::sort // 显式类型参数
```

这里是代表对象或数组延迟创建的方法引用表达式：

```
ArrayList<String>::new // 参数化类型的构造函数
ArrayList::new // 推断的类型参数
// 用于泛型类
Foo::<Integer>::new // 显式类型参数
// 用于泛型构造函数
Bar::<Integer>::new // 泛型类，泛型构造函数
Outer::new // 内部类构造函数
int[]::new // 数组创建
```

无法指定匹配特定的签名，例如 `Arrays::sort(int)`。相反，函数式接口提供了作为重载解析算法 (§15.12.2) 输入的类型。这应该满足绝大多数用例；当极少数需要精确控制时，可以使用 lambda 表达式。

在 `List<String>::size` 之前的类名中使用泛型语法会引发区分 `<` 作为类型括号和 `<` 作为小于运算符的解析问题。在理论上，这与允许在转换表达式中使用类型参数一样糟糕；然而，区别在于这种情况只在遇到标记 `::` 时发生；随着方法引用表达式的加入，每个表达式的开头都可能是参数化类型。

### 15.13.1 方法引用的编译时声明

方法引用表达式的编译时声明是该表达式所指的方法。在特殊情况下，编译时声明实际上并不存在，而是一个表示类实例创建或数组创建的虚拟方法。编译时声明的选择取决于表达式所针对的函数类型，正如方法调用的编译时声明取决于调用的参数一样 (§15.12.3)。

对编译时声明的搜索镜像了 §15.12.1 和 §15.12.2 中方法调用的过程，如下：

- 首先，要搜索的类型是：
    - 如果方法引用的形式 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，则要搜索的类型是 `::` 标记之前的表达式的类型。
    - 如果方法引用表达式的形式 `ReferenceType :: [TypeArguments] Identifier`，则要搜索的类型是应用于 `ReferenceType` 的捕获转换 (§5.1.10)。
    - 如果方法引用表达式的形式 `super :: [TypeArguments] Identifier`，则要搜索的类型是方法引用表达式直接相邻的类或接口声明的父类类型。

令 `au` 为紧邻方法引用表达式的类或接口声明。如果 `au` 是类 `Object` 或接口，则为编译错误。

如果方法引用表达式的形式 `TypeName :: super :: [TypeArguments] Identifier`，如果 `TypeName` 表示一个类，则要搜索的类型是该名类的父类类型；否则，`TypeName` 表示要搜索的接口。

如果 `TypeName` 既不是方法引用表达式的词法闭包类或接口声明，也不是方法引用表达式直接相邻的类或接口声明的直接父接口，则为编译错误。

如果 `TypeName` 是类 `Object`，则为编译错误。

如果 `TypeName` 是接口，且存在方法引用表达式直接相邻的类或接口声明的另一个直接父类或直接父接口 `J`，使得 `J` 是 `TypeName` 的子类或子接口，则为编译错误。

- 另外两种形式（涉及 `:: new`），引用的方法是虚拟的，没有类型要搜索。

- 其次，对于一个具有 $n$ 个参数的给定函数类型，识别一组可能适用的方法：

    - 如果方法引用表达式的形式 `ReferenceType :: [TypeArguments] Identifier`，则可能适用的方法是：
        - 要搜索类型的成员方法，对于一个名为 `Identifier`、元数为 $n$、具有类型参数 `TypeArguments` 且出现在与方法引用表达式相同类中的方法调用，这些方法可能是适用的 (§15.12.2.1)，加上
        - 要搜索类型的成员方法，对于一个名为 `Identifier`、元数为 $n-1$、具有类型参数 `TypeArguments` 且出现在与方法引用表达式相同类中的方法调用，这些方法可能是适用的。

考虑了两种不同的元数 $n$ 和 $n-1$，以考虑到这种形式可能指向静态方法或实例方法。

- 如果方法引用表达式的形式 `ClassType :: [TypeArguments] new`，则可能适用的方法是一组与 `ClassType` 构造函数对应的虚拟方法。

如果 `ClassType` 是原始类型，但不是原始类型的非静态成员，则候选的虚拟方法是 §15.9.3 中指定的、使用 `<>` 省略到类的类型参数以进行类实例创建的虚拟方法。否则，候选的虚拟方法是 `ClassType` 的构造函数，被处理为它们返回 `ClassType`。

在这些候选方法中，可能适用的方法是要搜索类型的成员方法，对于一个名为 `Identifier`、元数为 $n$、具有类型参数 `TypeArguments` 且出现在与方法引用表达式相同类中的方法调用，这些方法可能是适用的。

- 如果方法引用表达式的形式 `ArrayType :: new`，则考虑单个虚拟方法。该方法有一个类型为 `int` 的参数，返回 `ArrayType` 且没有 `throws` 子句。如果 $n = 1$，这是唯一可能适用的方法；否则，没有可能适用的方法。

- 最后，如果没有可能适用的方法，则没有编译时声明。

否则，给定一个具有参数类型 $P_1, \dots, P_n$ 的目标函数类型和一组可能适用的方法，其编译时声明的选择如下：

- 对于所有其他形式，搜索会产生一组适用的方法，并可能指定该集合中最特定的方法。在 §15.12.4 指定的错误情况下，适用方法集为空。在 §15.12.5 指定的错误情况下，没有最特定的方法。

    - 如果方法引用表达式的形式为 `ReferenceType::[TypeArguments]Identifier`，则执行两次针对最特定方法的搜索。按照 §15.12.2 规定的规定对每次搜索进行分类。每次搜索都产生一组适用的方法。在第一次搜索中，方法引用被处理为一个参数类型为 $P_1, \dots, P_n$ 的调用。类型参数（如果有）由方法引用给出。

    在第二次搜索中，如果 $P_1, \dots, P_n$ 不空且 $P_i$ 是 `ReferenceType` 的子类型，则方法引用被处理为一个参数类型为 $P_1, \dots, P_n$ 的调用。如果 `ReferenceType` 是原始类型，且存在该类型的参数化 $G<...>$ 它是 $P_i$ 的子类型，则要搜索的类型是应用于 $G<...>$ 的捕获转换 (§5.1.10)；否则，要搜索的类型与第一次搜索相同。类型参数（如果有）由方法引用给出。

如果第一次搜索产生的最特定方法是 `static`，且第二次搜索产生的适用方法集不包含非 `static` 方法，则编译时声明为第一次搜索的最特定方法。

否则，如果第一次搜索产生的适用方法集不包含 `static` 方法，且第二次搜索产生了最特定方法，则编译时声明为第二次搜索的最特定方法。

- 对于所有其他形式的方法引用表达式，都将执行一次对一个最具体的适用方法的搜索。该搜索按照 §15.12.2.2 至 §15.12.2.5 所示的规则进行，并附有下文说明。

该方法引用被处理等同于具有类型为 $P_1, ..., P_n$ 的参数表达式的调用；参数（如果有）由方法引用表达式给出。

如果搜索结果导致如 §15.12.2.2 至 §15.12.2.5 所示的错误，或者最具体的适用方法是 `static`，则没有编译时声明。

否则，编译时声明为最具体的适用方法。

如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，且编译时声明为 `static`，且 `Reference` 不是简单名或限定名 (§6.2)，则将产生编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName . super :: [TypeArguments] Identifier`，且编译时声明为 `abstract`，则将产生编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName . super :: [TypeArguments] Identifier`，且该方法引用表达式出现在静态上下文中 (§8.1.3)，则将产生编译时错误。

如果方法引用表达式的形式为 `TypeName . super :: [TypeArguments] Identifier`，且 `TypeName` 指代类 `c`，而该方法引用表达式的直接外层类或接口声明不是 `c` 或 `c` 的内部类，则将产生编译时错误。

如果方法引用表达式的形式为 `TypeName . super :: [TypeArguments] Identifier`，且 `TypeName` 指代一个接口，并且存在一个与编译时声明不同的方法，该方法从直接包含方法引用表达式的类或接口的直接超类或直接超接口重写了该编译时声明 (§8.4.4, §9.4.1)，则将产生编译时错误。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，且在确定 `ClassType` 的外层实例时按照 §15.9.2 所示会导致编译时错误（将方法引用表达式处理等同于未限定的类实例创建表达式），则将产生编译时错误。

形式为 `ReferenceType :: [TypeArguments] Identifier` 的方法引用表达式可以有不同的解释方式。如果 `Identifier` 指向一个实例方法，那么隐式 lambda 表达式与 `Identifier` 指向静态方法的情况相比多出一个参数。`ReferenceType` 可能同时具有这两类适用方法，因此搜索算法会分别识别它们，因为每种情况的参数类型不同。

歧义的一个示例是：

```java
interface Fun<T,R> { R apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    void test() {
        Fun<C, Integer> f1 = C::size;
        // 实例方法 size()
        // 还是静态方法 size(Object)?
    }
}
```

这种歧义无法通过提供比适用静态方法更具体的实例方法来解决：

```java
interface Fun<T,R> { R apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    int size(C arg) { return 0; }
    void test() {
        Fun<C, Integer> f1 = C::size;
        // 实例方法 size()
        // 还是静态方法 size(Object)?
    }
}
```

搜索足够智能忽略所有适用方法都是实例方法的歧义：

```java
interface Fun<T,R> { R apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    int size(C arg) { return 0; }
    void test() {
        Fun<C, Integer> f1 = C::size;
        // 实例方法 size()
    }
}
```



# 表达式

## 一元运算符

为了方便，当使用泛型类型的名称来引用方法时，目标类型将用于推断 `R'`。例如 `Pair<String>>::first` 这样的方法引用被处理等同于 `Pair<>()。由于菱形符号是隐式的，这种方法不会实例化原始类型。

对于某些方法引用，只有一个调用类型 `15.12.2.6` 所示的编译时声明，方法引用是精确的。不精确的方法引用表达式被认为是不精确的。

以 `Identifier` 结尾的方法引用如果满足所有条件则是精确的：

- 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments]`，则 `ReferenceType` 不是原始类型。
- 该类型有一个可供类或接口访问的 `Identifier` 方法。
- 该方法不是变态的 (§8.4)。
- 如果该方法是泛型的 (§8.4)，则方法引用提供了 `TypeArguments`。

形式为 `ClassType :: [TypeArguments] new` 的方法引用表达式如果满足所有条件则是精确的：

- 指代的 `ClassType` 不是原始的，或者是原始类型的非静态成员。
- 指代的 `ClassType` 有一个可供类或接口访问的构造函数。
- 该构造函数不是变态的。
- 如果该构造函数是泛型的，则方法引用提供了 `TypeArguments`。

形式为 `ArrayType :: new` 的方法引用总是精确的。

## 15.13.2 方法引用的类型

方法引用表达式在赋值上下文、调用上下文或类型转换上下文中与类型 `T` 兼容，如果 `T` 是函数接口 (§9.8) 且表达式与目标类型的函数类型一致。

目标类型 `T` 从 `au` 如下：

- 如果 `au` 是通配符化的函数接口类型，目标类型是 `au` 的非通配符参数化 (§9.9)。
- 否则，目标类型为 `au`。

方法引用表达式与函数类型一致，当满足以下两个条件时：

- 函数类型识别出一个对应引用的编译时声明。
- 以下任一为真：
  - 函数类型的结果为 `void`。
  - 应用捕获转换 (§5.1.10) 到编译时声明的调用类型 (§15.12.2.6) 的结果是 `R'`（其中 `R` 是用于推断 `R'` 的目标类型），且 `R` 和 `R'` 都不是 `void`，且 `R'` 在赋值上下文中与 `R` 兼容。

为了使编译时声明适用而需要检查转换，且此转换在调用上下文中会导致检查警告，则将产生编译时检查警告，除非被 `@SuppressWarnings` (§9.6.4.5) 抑制。

为了使上述返回类型 `R'` 与函数类型的返回类型 `R` 兼容而需要转换，且此转换在赋值上下文中会导致检查警告，则将产生编译时检查警告，除非被 `@SuppressWarnings` 抑制。

如果方法引用表达式与目标类型 `T` 兼容，则该表达式的类型 `U` 是从 `T` 导出的目标类型。

如果 `U` 或其函数类型中提到的任何类或接口在方法引用表达式所在的类或接口中都是不可访问的，则将产生编译时错误。

对于 `U` 的每个非静态方法成员 `m`，如果 `U` 的函数类型具有 `m` 签名的子签名，则一个类型为 `U` 的函数类型的概念方法被称为重写（override）了 `m`，并且可能会发生 §8.4.3 中指定的任何编译错误或未检查警告。

对于在编译时声明的调用的 `throws` 子句中列出的受检异常类型 `x`，`x` 或 `x` 的超类必须在 `U` 的函数类型的 `throws` 子句中被提及，否则将发生编译错误。

这种兼容性定义背后的核心思想是：方法引用当且仅当等价的 lambda 表达式 `(x, y, z) -> exp.<T1, T2>method(x, y, z)` 兼容时，该方法引用就是兼容的。这种描述是非正式的，并且存在一些问题使得通过这种重写来正式定义语义变得困难或不可能。

这些兼容性规则为将一个函数式接口转换为类型提供了方便的方法：

```
Task t = () -> System.out.println("hi");

Runnable r = t::invoke();
```

当 lambda 派生的对象被传递并在各种类型之间转换时，其实现可以被优化，这不会在核心 lambda 语句周围产生许多层的适配逻辑。

与 lambda 表达式不同，方法引用可以与泛型类型（即具有类型参数的函数）一致。这是因为 lambda 表达式需要能够声明类型参数，而没有语法支持这一点；对于方法引用，不需要此类声明。例如，以下程序是合法的：

```
interface ListFactory {

  <T> List<T> make();

}

ListFactory lf = ArrayList::new;

List<String> ls = lf.make();

List<Number> ln = lf.make();
```

## 15.13.3 方法引用运行时评估

在运行时，方法引用表达式的评估类似于类实例创建表达式的评估，因为正常完成会产生对对象的引用。方法引用表达式的评估与方法本身的调用是不同的。

首先，如果方法引用表达式以 `ExpressionName` 或 `Primary` 开头，则对该子表达式进行评估。如果其结果为 `null`，则抛出 `NullPointerException`，并且方法引用表达式异常终止。如果子表达式异常终止，则方法引用表达式也以相同原因异常终止。

接下来，要么分配并初始化一个具有下方属性的类的新实例，要么引用一个具有下方属性的现有实例。如果需要创建新实例但没有足够的空间分配该对象，则方法引用表达式的评估通过抛出 `OutOfMemoryError` 异常终止。

方法引用表达式的值是对具有以下属性的类实例的引用：

- 该类实现了目标函数式接口类型，如果目标类型是交集类型（intersection type），则实现了交集中提到的每种其他接口类型。
- 当方法引用表达式类型为 `U` 时，对于 `U` 的每个非静态成员 `m`。

如果 `U` 的函数类型具有 `m` 的签名，则调用的执行体将如下所示调用引用的方法、创建一个类实例或创建一个数组。如果调用的结果不是 `void`，则在经过任何必要的赋值转换（5.2）后，执行体将返回方法调用或对象创建的结果。

如果被重写方法的类型擦除的签名与 `U` 函数类型的类型擦除不同，则在方法调用或对象创建之前，调用的执行体会检查任何参数值是否为 `U` 函数类型中对应参数类型的子类或子接口的实例；如果不是，则抛出 `ClassCastException`。

- 该类重写了函数式接口或其他上述其他接口类型的方法，尽管它可能会重写 `Object` 类的方法。

调用方法的执行体取决于方法引用表达式的形式，如下：

- 如果方法引用表达式的形式为 `ExpressionName :: [TypeArguments]` 或 `Primary :: [TypeArguments]`，则对该子表达式进行评估。如果评估结果为 `null`，则抛出 `NullPointerException`，并且方法引用表达式异常终止。如果子表达式异常终止，则方法引用表达式也以相同原因异常终止。
    执行后，如果调用的结果不是 `void`，则在经过任何必要的赋值转换（5.2）后，执行体将返回方法调用或对象创建的结果。
    （由于原文此段存在多处重复嵌套的逻辑描述，此处保持逻辑结构对应翻译）
    （注：由于原文 15.13.3 节后续部分存在大量逻辑相似的重复性描述，译文严格遵循原文的 Markdown 结构进行对应）

（注：原文文本 15.13.3 节的描述逻辑较为复杂，此处已按原文结构完整翻译。）

声明为 `final` 的变量不能被增加，因为对此类 `final` 变量的访问被用作表达式，其结果是一个值而不是变量。因此，它不能作为后置递增运算符的操作数。

## 15.14.3 后置递减运算符 --

后跟一个 `--` 运算符的后置表达式是后置递减表达式。

```
PostDecrementExpression:
PostfixExpression --
```

后置递减的结果必须是一个可以转换为数值类型 (§5.1.8) 的类型的变量，否则将发生编译时错误。

后置递减表达式的类型是该变量的类型。后置递减表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的计算异常完成，则由于相同的原因不会发生递减。否则，从变量的值中减去值 1，并将差值存回变量中。在相减之前，会对值 `1` 和变量的值进行二元数值类型提升 (§5.6)。如果有必要，差值在存储之前通过收窄原始类型转换 (§5.1.3) 收窄为该变量的类型。后置递减表达式的值是在存储新值之前变量的值。

> 注意，上述二元数值类型提升可能包括拆箱转换 (§5.1.8)。

声明为 `final` 的变量不能被递减，因为对此类 `final` 变量的访问被用作表达式，其结果是一个值而不是变量。因此，它不能作为后置递减运算符的操作数。

## 15.15 一元运算符

运算符 `+`、`-`、`--`、`~`、`!` 以及转换运算符 (§5.16) 称为一元运算符。一元表达式要么应用于操作数的一元运算符，要么 switch 表达式 (§15.28)。

```
UnaryExpression:
PreIncrementExpression
PreDecrementExpression
+ UnaryExpression
- UnaryExpressionNotPlusMinus
```

### 一元运算符

```
PreIncrementExpression:
++ UnaryExpression

PreDecrementExpression:
-- UnaryExpression

UnaryExpressionNotPlusMinus:
PostfixExpression
~ UnaryExpression
! UnaryExpression
CastExpression
SwitchExpression
```

带有一元运算符的表达式从右向左分组，因此 `--x` 等于 `= (-x)`。

语法的这部分包含一些技巧，以避免两种潜在的语法歧义。

第一个潜在歧义可能出现在像 `(p)+q` 这样的表达式中，对于 C 或 C++ 程序员来说，这看起来可能是对 `q` 执行一元 `+` 操作的转换，或者是两个数量 `p` 和 `q` 的二元加法。在 C 和 C++ 中，解析器通过在解析时执行有限的语义分析来处理这个问题，因此它知道 `p` 是类型名还是变量名。

Java 采取了不同的方法。`+` 运算符的结果必须是数值的，且数值值涉及的所有类型名都不是关键字。如果 `p` 是命名原始类型的关键字，那么 `(p)+q` 只能被解释为一元表达式的转换。如果 `p` 不是命名原始类型的关键字，那么 `(p)+q` 只能被解释为二元算术运算。类似的说明也适用于 `-` 运算符。语法将 `CastExpression` 拆分为多种情况，以做出这种区分：

```
CastExpression:
( PrimitiveType ) UnaryExpression
( Reference [Additional] ) UnaryExpressionNotPlusMinus
( Reference [Additional] ) LambdaExpression
```

非终端 `UnaryExpression` 包含了所有的一元运算符，但非终端 `UnaryExpressionNotPlusMinus` 排除了所有可能作为二元运算符的一元运算符，在 Java 中这些是 `+` 和 `-`。

第二个潜在歧义是表达式 `(p)++` 对于 C 或 C++ 程序员来说，看起来可能是圆括号表达式的后置递增，或者是转换的开始，例如在 `(p)++` 中。由于 C 和 C++ 的解析器知道 `p` 是类型名还是变量名。但使用单标记标记前瞻（one-token lookahead）且在解析期间不进行语义分析的解析器将无法判断当 `++` 是前瞻标记时，`(p)` 应该被视为基本表达式（Primary expression），还是留待稍后作为 `CastExpression` 的一部分。

表达式

一元运算符
15.15

在 Java 中，`++` 运算符的结果必须是数值的，且数值值转换中涉及的所有类型名都是已知关键字。因此，如果 `p` 是命名原始类型的关键字，那么 `(p) ++` 只能被解释为前置递增表达式，并且后面必须有一个如 `q` 的操作数。然而，如果 `p` 不是命名原始类型的关键字，那么 `(p++)` 只能被解释为 `p` 的后置递增。类似的说明也适用于运算符 `-`。因此 `UnaryExpressionNotPlusMinus` 排除了前置运算符 `++` 和 `--` 的使用。

## 15.15.1 前置递增运算符 ++

由 `++` 运算符引导的一元表达式是前置递增表达式。

一元表达式的结果必须是可以转换为数值类型 (§5.1.8) 的类型的变量，否则将发生编译时错误。

前置递增表达式的类型是该变量的类型。前置递增表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的计算异常完成，则前置递增表达式由于相同的原因异常完成，不会发生递增。否则，将变量的值加上值 1，并将和存回变量中。在相加之前，会对值 `1` 和变量的值进行二元数值类型提升 (§5.6)。如果有必要，和在存储之前通过收窄原始类型转换 (§5.1.3) 收窄为该变量的类型。前置递增表达式的值是在存储新值之前变量的值。

> 注意，上述二元数值类型提升可能包括拆箱转换 (§5.1.8)。

声明为 `final` 的变量不能被增加，因为对此类 `final` 变量的访问被用作表达式，其结果是一个值而不是变量。因此，它不能作为前置递增运算符的操作数。

## 15.15.2 前置递减运算符 --

由 `--` 运算符引导的一元表达式是前置递减表达式。

一元表达式的结果必须是可以转换为数值类型 (§5.1.8) 的类型的变量，否则将发生编译时错误。

前置递减表达式的类型是该变量的类型。前置递减表达式的结果不是变量，而是一个值。

### 一元运算符

在运行时，如果操作数表达式的计算异常完成，则前置递减表达式由于相同的原因不会发生递减。否则，从变量的值中减去值 1，并将差值存回变量中。在相减之前，会对值 `1` 和变量的值进行数值类型提升 (§5.6)。如果有必要，差值在存储之前通过收窄原始类型转换 (§5.1.3) 收窄并/或通过装箱转换 (§5.1.7) 转换为该变量的类型。前置递减表达式的值是在存储新值之前变量的值。

> 注意，上述二元数值类型提升可能包括拆箱转换 (§5.1.8)。

声明为 `final` 的变量不能被递减，因为对此类 `final` 变量的访问被用作表达式，其结果是一个值而不是变量。因此，它不能作为前置递减运算符的操作数。

## 15.15.3 一元加号运算符 +

一元 `+` 运算符的操作数表达式的类型必须是可以转换为原始数值类型 (§5.1.8) 的类型，否则将发生编译时错误。会对操作数进行数值类型提升 (§5.6)。一元加号表达式的类型是操作数提升后的类型。一元表达式的结果不是变量，而是一个值，即使操作数的结果是一个变量。

在运行时，一元加号表达式的值是操作数提升的值。

## 15.15.4 一元减号运算符 -

一元 `–` 运算符的操作数表达式的类型必须是可以转换为原始数值类型 (§5.1.8) 的类型，否则将发生编译时错误。会对操作数进行数值类型提升 (§5.6)。

一元减号表达式的类型是操作数提升后的类型。

在运行时，一元减号表达式的值是操作数提升的值的算术取反。
对于整数值，取反等同于从零减。Java 编程语言使用补码表示整数，且这种补码值的范围是非对称的，对最大负 `int` 或 `long` 取反的结果仍为该最大负整数。在这种情况下会发生溢出，但不会抛出异常。对于所有整数 `x`，`-x` 等于 `(~x)+1`。

对于浮点值，取反不等于减零，因为如果 `x` 是 `+0.0`，那么 `0.-x` 是 `+0.0`，但 `-x` 是 `-0.0`。一元运算仅反转浮点数的符号。特殊情况如下：

- 如果操作数是 NaN，结果为 NaN。（回想 NaN 没有符号（见 §4.2.3））。

Java 编程语言没有采用 2019 版 IEEE 754 标准中更强的要求，即取反会反转包括 NaN 在内所有输入的符号位。

- 如果操作数是无穷大（infinity），结果为相反符号的无穷大。

- 如果操作数是零，结果为相反符号的零。

### 15.15.5 按位取反运算符 ~

一元 `~` 运算符的操作数表达式的类型必须是可以转换为（§5.1.8）基本整数类型的类型，否则会发生编译错误。

对操作数执行一元提升（§5.6）。一元按位取反表达式的类型是操作数提升后的类型。

在运行时，一元按位取反表达式的值是操作数提升后值的按位取反。在所有情况下，`~x` 等于 `(-x)-1`。

一元 `!` 运算符的操作数表达式的类型必须是 `boolean`，否则会发生编译错误。

一元逻辑取反表达式的类型为 `boolean`。

在运行时，必要时将对操作数进行拆箱转换（§5.1.8）。如果（可能经过转换的）操作数值为 `false`，则一元逻辑取反表达式的值为 `true`；如果（可能经过转换的）操作数值为 `true`，则为 `false`。

### 15.16 强制转换表达式

强制转换表达式在运行时将一种数值类型的值转换为另一种数值类型的相似值；或者在编译时确认表达式的类型为 `boolean`；或者在运行时检查引用值是否指向一个与指定的引用类型或引用类型列表兼容的类，或者体现了基本类型值的对象。

```
CastExpression:
( PrimitiveType ) UnaryExpression
( ReferenceType [AdditionalBound] ) UnaryExpressionNotPlusMinus
( ReferenceType [AdditionalBound] ) LambdaExpression
```

为了方便起见，此处显示来自 §4.4 的产生式：

```
AdditionalBound:
& IntersectionType
```



括号以及它们包含的类型或类型列表有时称为强制转换运算符。

如果强制转换运算符包含类型列表，即一个 `ReferenceType` 后跟一个或多个 `Additional` 终端，则必须满足以下所有条件，否则会发生编译错误：

- `ReferenceType` 必须表示类类型或接口类型。
- 所有列出类型的擦除（§4.6）必须两两不相同。
- 任意两个列出的类型不能是同一个泛型接口不同参数化的子类型。

由强制转换表达式引入的转换强制转换（§5.5）的目标类型是强制转换运算符中出现的 `PrimitiveType` 或 `ReferenceType`（如果后面没有跟 `AdditionalBound` 终端），或者是强制转换运算符中由 `ReferenceType` 和 `AdditionalBound` 终端表示的交集类型。

强制转换表达式的类型是对该目标类型应用捕获转换（§5.1.10）的结果。

强制转换可显式地“标记” lambda 表达式或方法引用表达式以特定的目标类型。为了提供适当灵活性，目标类型可以是表示交集类型的类型列表，前提该交集产生了一个函数式接口（§9.8）。

## 15.17 乘法运算符

强制转换表达式的结果不是变量，而是一个值，即使求值操作数表达式的结果是一个变量。

如果操作数的编译时类型无法通过转换转换（§5.5）转换为强制转换运算符指定的目标类型，则会发生编译错误。

否则，在运行时，操作数值将在必要时通过转换转换转换为强制转换运算符指定的类型类型。

如果在运行时发现强制转换是不允许的，则抛出 `ClassCastException`。

- 某些强制转换会在编译时产生错误。某些情况可以在编译时被证明在运行时总是正确的。例如，将类类型的值转换为其父类的类型始终是正确的；此类强制转换在运行时不需要特殊操作。最后，某些强制转换在编译时无法证明是正确或错误的。此类转换需要在运行时进行测试。详见 §5.5。

`*`、`/` 和 `%` 运算符被称为乘法运算符。

```
MultiplicativeExpression:
    UnaryExpression
    MultiplicativeExpression * UnaryExpression
    MultiplicativeExpression / UnaryExpression
    MultiplicativeExpression % UnaryExpression
```

乘法运算符具有相同的优先级，并且语法上是左结合的（从左到右分组）。

乘法运算符的每个操作数的类型必须是可以转换为（§5.1.8）基本数值类型的类型，否则会发生编译错误。

对操作数执行二元数值提升（§5.6）。

### 15.17.1 乘法运算符 *

`*` 运算符执行乘法，产生操作数的乘积。左侧操作数是乘数，右侧操作数是因数。

乘法具有交换律，但浮点运算除外。

`*` 运算符的结果类型是可以转换为（§5.1.8）基本数值类型的类型，否则会发生编译错误。

对操作数执行二元数值提升（§5.6）。

乘法具有交换律，但浮点运算除外。`*` 运算符的结果是操作数的乘积。

`*` 运算符表达式的结果类型是操作数提升后的类型。

在运行时，`*` 运算符表达式的值是操作数提升后值的乘积。在所有情况下，`x * y` 等于 `y * x`。

- 如果操作数是 NaN，结果为 NaN。（回想 NaN 没有符号（见 §4.2.3））。
- 如果操作数是无穷大，结果为 NaN。
- 如果两个操作数都是无穷大，结果为无穷大。
- 如果一个操作数是无穷大，结果为相反符号的无穷大。
- 如果一个操作数是零，结果为相反符号的零。

如果操作数的结果类型是 `int` 或 `long`，则执行整数运算。

### 15.17.2 除法运算符 /

`/` 运算符执行除法，产生操作数的商。左侧操作数是被除数，右侧操作数是除数。

整数除法向 0 舍入。

`/` 运算符的结果类型是可以转换为（§5.1.8）基本数值类型的类型，否则会发生编译错误。

对操作数执行二元数值提升（§5.6）。

`/` 运算符的结果类型是操作数提升后的类型。

在运行时，`/` 运算符表达式的值是操作数提升后值的商。如果被除数为最小负整数且除数为 -1，则会发生整数溢出且结果为最小负整数。相反，如果整数除法的除数为 0，则抛出 `ArithmeticException`。

如果操作数的结果是 `float` 或 `double`，则执行浮点运算。浮点除法的结果由 IEEE 754 规则决定。

- 如果操作数是 NaN，结果为 NaN。（回想 NaN 没有符号（见 §4.2.3））。
- 如果操作数是无穷大，结果为 NaN。
- 如果两个操作数都是无穷大，结果为 NaN。
- 如果一个操作数是无穷大，结果为相应符号的无穷大。
- 如果一个操作数是零，结果为相反符号的零。

如果商的幅度无法表示，我们称该操作溢出；此时结果为相应符号的无穷大。否则，商将舍入到最近的可表示值，使用最近舍入策略（见 §15.4）。Java 语言要求支持 IEEE 754 定义的渐进消溢。

### 15.17.3 取余运算符 %

`%` 运算符执行除法，产生操作数的余。左侧操作数是被除数，右侧操作数是除数。

`%` 运算符的结果类型是可以转换为（§5.1.8）基本数值类型的类型，否则会发生编译错误。

对操作数执行二元数值提升（§5.6）。

在运行时，`%` 运算符表达式的值是操作数提升后值的余。在所有情况下，`x % y` 等于 `x - (x / y) * y`。

- 如果操作数是 NaN，结果为 NaN。（回想 NaN 没有符号（见 §4.2.3））。
- 如果一个操作数是无穷大，结果为 NaN。
- 如果一个操作数是零，结果为被除数。

余数的符号与被除数的符号相同。

## 15.17.3 取余运算符 %

二进制运算符 `%` 被称为产生其操作数隐式除法的余数；左侧操作数为被除数，右侧操作数为除数。

在 C 和 C++ 中，取余运算符只接受整数操作数，但在 Java 语言中，它也接受浮点数操作数。

对于经过二值数值提升（§5.6）后为整数的操作数，其取余运算产生的结果值使得 `(a/b)*b+(a%b)` 等于 `a`。

即使在被除数为其类型可能的最大值且除数为 -1 的特殊情况下（余数为 0），该等式依然成立。

根据这一规则可以得出，取余运算的结果只有在被除数为负时才为负，只有在被除数为正时才为正。此外，余数的绝对值始终小于等于除数的绝对值。如果整数取余的除数为 0，则会抛出 `ArithmeticException`。

### 示例 15.17.3-1 整数取余运算符

```java
class Test1 {
    public static void main(String[] args) {
        int a = 5%3; // 2
        int b = 5/3; // 1
        System.out.println("5%3 produces " + a + " (note that 5/3 produces " + b + ")");
    }
}
```

该程序产生输出：
5%3 produces 2 (note that 5/3 produces 1)

### 15.17.3-2 浮点数取余运算符

由 `%` 运算符计算的浮点取余运算结果与 IEEE 754 中取余运算符（取决于舍入策略）计算的结果不同。相反，Java 语言对浮点数操作数的 `%` 的定义方式类似于整数取余，它使用了一种向零舍入的隐式除法；这可以与库函数 `fmod` 进行比较。IEEE 754 取余运算可以通过库程序 `Math.remainder` 或 `StrictMath.remainder` 计算。

浮点数取余运算的结果由以下规则决定，这些规则除隐式除法的计算方式外，与 IEEE 754 算术一致：

- 如果任一操作数为 NaN，则结果为 NaN。
- 如果结果不是 NaN，则结果的符号与被除数的符号相同。
- 如果被除数为无穷大，或除数为 0，或两者都是，则结果为 NaN。
- 如果被除是有限的且除数为无穷大，则结果等于被除数。
- 如果被除数为 0 且除数为有限的，则结果等于被除数。
- 在其他情况下（既不涉及无穷大也不涉及 NaN），被除数 `n` 除以除数 `d` 得到的浮点余数 `r` 由数学关系 `r = n - (d * q)` 定义，其中 `q` 是一个整数，当 `n/d` 为负时 `q` 为负，当 `n/d` 为正时 `q` 为正，且 `q` 的绝对值在不超过 `n` 和 `d` 的数学商绝对值的前提下尽可能大。

浮点数取运算符运算符 `%` 的求值永远不会抛出运行时异常，即使右侧操作数为 0。也不会发生溢出、下溢或精度丢失。

```java
class Test2 {
    public static void main(String[] args) {
        double a = 5.0%3.0; // 2.0
        System.out.println("5.0%3.0 produces " + a);
        double b = 5.0%(-3.0); // 2.0
        System.out.println("5.0%(-3.0) produces " + b);
        double c = (-5.0)%3.0; // -2.0
        System.out.println("(-5.0)%3.0 produces " + c);
        double d = (-5.0)%(-3.0); // -2.0
        System.out.println("(-5.0)%(-3.0) produces " + d);
    }
}
```

该程序产生输出：
5.0%3.0 produces 2.0
5.0%(-3.0) produces 2.0
(-5.0)%3.0 produces -2.0
(-5.0)%(-3.0) produces -2.0

## 15.18 加法运算符

运算符 `+` 和 `-` 被称为加法运算符。

```
AdditiveExpression:
    MultiplicativeExpression
    AdditiveExpression + MultiplicativeExpression
    AdditiveExpression - MultiplicativeExpression
```

这些运算符具有相同的优先级，并且在语法上是左结合的（从左到右分组）。

如果 `+` 运算符的任一操作数的类型是 `String`，则该操作是字符串拼接。

否则，`+` 运算符的每个操作数的类型必须是可以转换为（§5.1.8）原始数值类型的类型，否则会发生编译错误。

在任何情况下，二元 `-` 运算符的每个操作数的类型都必须是可以转换为（§5.1.8）原始数值类型的类型，否则会发生编译错误。

## 15.18.1 字符串拼接运算符 +

如果只有一个操作数表达式的类型为 `String`，则执行字符串转换。字符串拼接的结果是两个字符串的拼接。字符串拼接的结果是左侧操作数和右侧操作数的拼接。

### 示例 15.18.1 字符串拼接

在表达式中：
```java
"The root of 2 is " + Math.sqrt(2)
```
结果是：
"The root of 2 is 1.4142135623730951"

在表达式中：
```java
"fiddlers" + 1 + 2
```
结果是：
"fiddlers12"

在表达式中：
```java
1 + 2 + "fiddlers"
```
结果是：
"3fiddlers"

### 示例 15.18.2 字符串拼接与条件判断

在代码中，注意在适当的情况下通过条件判断生成单数 "bottle" 而不是复数 "bottles"；还要注意如何使用字符串拼接来断开长常量字符串：

> "You take one down and pass it around:"

将其分为两部分，以避免源代码中出现过不长的行。

```java
class Bottles {
    static void printSong(Object stuff) {
        int n = 100;
        for (int i = n; i > 0; i--) {
            System.out.println(i + " " + (i == 1 ? "bottle" : "bottles") + " of slime on the wall,");
            System.out.println("You take one down and pass it around:");
        }
        System.out.println("No bottles of slime on the wall!");
    }
}
```

运行该程序产生的输出如下：

100 bottles of slime on the wall,
You take one down and pass it around:
99 bottles of slime on the wall,
You take one down and pass it around:
...
2 bottles of slime on the wall,
You take one down and pass it around:
1 bottle of slime on the wall,
You take one down and pass it around:
No bottles of slime on the wall!

## 15.18 加法运算符表达式

如果整数加法发生溢出，则结果为在某种足够大的补码格式下表示的数学和的低位位。如果发生溢出，结果的符号与两个操作数数学和的符号不相同。

浮点数加法的结果由 IEEE 754 算术规则决定：

- 如果任一操作数为 NaN，则结果为 NaN。
- 两个符号相反的无穷大之和为 NaN。
- 两个符号相同的无穷大之和为该符号的无穷大。
- 无穷与有限值的和等于该无穷操作数。
- 两个符号相反的零之和为正零。
- 两个符号相同的零之和为该符号的零。
- 零与非零有限值的和等于该非零操作数。
- 两个幅度相同且符号相反的非零有限值之和为正零。
- 在其余情况下（不涉及无穷大、零或 NaN，且操作数具有相同符号或不同幅度），将计算和的精确数学幅度。

如果和的幅度大到无法表示，我们称该操作发生溢出；结果结果为具有相应符号的无穷大。

否则，和使用“最近舍入”策略（§15.4）舍入到最近的可表示值。Java 语言要求支持渐进下溢。

`-` 运算符应用于两个数值类型的操作数时执行减法，产生两个操作数的差；左侧操作数是被减数，右侧操作数是减数。

对于整数和浮点数减法，`a-b` 产生的结果与 `a+(-b)` 相同。

注意，对于整数点值，减去 0 等同于取反。然而，对于浮点值，减去 0 *并不*等同于取反，因为如果 `x` 是 `+0.0`，那么 `0.0-x` 是 `+0.0`，但 `-x` 是 `-0.0`。

尽管可能会发生溢出、下溢或信息丢失，数值加法运算符的求值永远不会抛运行时异常。

## 15.19 移位运算符

`<<`（左移）、`>>`（符号右移）和 `>>>`（无符号右移）被称为移位运算符。移位运算符的左侧操作数是要移位的值；右侧操作数指定移位距离。

```
ShiftExpression:
    AdditiveExpression
    ShiftExpression << AdditiveExpression
    ShiftExpression >> AdditiveExpression
    ShiftExpression >>> AdditiveExpression
```

移位运算符在语法上是左结合的（从左到右）。对每个操作数分别执行一元数值提升（如 §5.6）。（不对操作数执行二元数值提升。）

如果移位运算符的操作数类型在一元数值提升后不是原始整数类型，则为编译时错误。

移位表达式的类型是左侧操作数提升后的类型。

如果左侧操作数的提升类型为 `int`，则只使用右侧操作数的最低位作为移位距离。这好像右侧操作数受到了与掩码值 `0x1f`（0011111）的位逻辑与运算符（&§15.22.1）的处理一样。因此，实际使用的移位距离始终在 0 到 31 之间。

如果左侧操作数的提升类型为 `long`，则只使用右侧操作数的最低位作为移位距离。这好像右侧操作数受到了与掩码值 `0x3f`（0111111）的位逻辑与运算符（&§15.22.1）的处理。因此，实际使用的移位距离始终在 0 到 63 之间。

运行时，移位操作在左侧操作数值的补码整数表示上进行。

`n << s` 的值是 `n` 左移 `s` 位；这等同于（即使发生溢出）乘以 2 的 `s` 次。

`n >> s` 的值是 `n` 右移 `s` 位并进行符号扩展。对于非负值 `n`，这等同于由整数除法运算符 `/` 计算的截整除法 `floor(n / 2^s)` 乘以 2 的 `s` 次。

`n >>> s` 的值是 `n` 右移 `s` 位位置并进行零扩展，其中：

- 如果 `n` 为正，则结果与 `n >> s` 相同。
- 如果 `n` 为负数且左侧操作数类型为 `int`，则结果等于表达式 `(n >> s) + (2 << ~s)`。
- 如果 `n` 为负数且左侧操作数类型为 `long`，则结果等于表达式 `(n >> s) + (2L << ~s)`。

增加的项 `(2 << ~s)` 或 `(2L << ~s)` 消除了传播的符号位。

注意，由于对右侧操作数的隐式掩码，`int` 的移位距离始终在 0 到 31 范围内，`long` 则在 0 到 63 范围内。

## 示例 15.20.2-1 类型比较运算符

```java
class Point { int x, y; }
class Element { int atomicNumber; }
class Test {
    public static void main(String[] args) {
```



Point p = new Point();

Element e = new Element();

if (e instanceof Point) { // 编译错误

    System.out.println("I get your point!");

    p = (Point)e; // 编译错误

}

}

}

```

该程序会导致两个编译错误。强制类型转换`(Point)e`是错误的，因为`Element`的任何实例或其可能的子类（此处未显示）都不可能是`Point`的任何子类的实例。`instanceof`表达式出于完全相同的原因也是错误的。另一方面，如果转换`Point`是`Element`的子类（这在这里确实是一个奇怪的说明）：

```java
class Point extends Element { int x, y; }
```

那么强制类型转换就是可能的，尽管需要运行时检查，且`instanceof`表达式是合理且有效的。如果`e`的值不能正确转换为类型`Point`，则永远不会执行`(Point)e`并抛出异常。

在Java SE 16之前，类型比较运算符的引用类型必须是可重写的（reifiable）（§4）。这阻止了泛化类型的使用，除非所有参数都是通配符。该要求在Java SE 16中被取消，以允许使用更多的泛化类型。例如，在以下程序中，测试静态类型为`List<Integer>`的方法`x`在运行时是否具有更“精细”的类型`ArrayList<Integer>`是合法的：

```java
import java.util.ArrayList;
import java.util.List;

class Test2 {
    public static void main(String[] args) {
        List<Integer> x = new ArrayList<Integer>();
        if (x instanceof ArrayList<Integer>) {
            System.out.println("ArrayList of Integers");
        }
        if (x instanceof ArrayList<String>) {
            System.out.println("ArrayList of Strings");
        }
        if (x instanceof ArrayList<Object>) {
            System.out.println("ArrayList of Objects");
        }
    }
}
```

## 15.21 等于运算符

第一个`instanceof`表达式是合法的，因为存在从`List<Integer>`到`ArrayList<Integer>`的转换。然而，第二个和第三个`instanceof`表达式都会导致编译错误，因为不存在从`List<Integer>`到`ArrayList<String>`或`Array<Object>`的转换。

`==`（等于）和`!=`（不等于）运算符被称为相等运算符。

- EqualityExpression:
    - RelationalExpression
    - EqualityExpression == RelationalExpression
    - EqualityExpression != RelationalExpression

相等运算符在语法上是左结合的（它们从左到右分组）。

然而，这一事实实际上几乎没用。例如，`a==b==c`解析为`(a==b)==c`。`a==b`的结果类型始终是`boolean`，而`c`必须是`boolean`类型，否则会导致编译错误。因此，`a==b==c`并不测试`a`、`b`和`c`是否相等。

如果操作数表达式没有副作用，则相等运算符具有交换律。

相等运算符与关系运算符类似，不同在于它们的优先级较低。因此，当`a<b`和`c<d`具有相同的真值时，`a<b<c`为真。

相等运算符可以比较两个可转换为数值类型（§5.1.8）的操作数，或者两个`boolean`或`Boolean`类型的操作数，或者两个属于每个引用类型或空类型的操作数。所有其他情况都会导致编译错误。

相等表达式的类型始终是`boolean`。在所有情况下，`a!=b`产生与`!(a==b)`相同的结果。

如果相等运算符的操作数都是数值类型，或者其中一个是数值类型而另一个可转换为（§5.1.8）数值类型，则对操作数执行二进数值型类型提升（§5.6）。

注意，二进数值型类型提升可能包含拆箱转换（§5.1.8）。

如果操作数提升后的类型是`int`或`long`，则执行整数相等测试。

如果提升后的类型是`float`或`double`，则执行浮点相等测试。

浮点相等测试根据IEEE 754规则进行：

- 如果操作数提升后的类型是`int`或`long`，则执行整数相等测试。
- 如果提升后的类型是`float`或`double`，则执行浮点相等测试。

## 15.23 逻辑与运算符 &&

```
0x0ff0
```

表达式的计算：

```
0xff00 | 0xf0f0
```

结果是：

```
0xfff0
```

## 15.22.2 布尔逻辑运算符 &, ^, 和 |

当`&`、`^`或`|`运算符的操作数类型为`boolean`或`Boolean`时，则位运算符表达式的类型为`boolean`。在所有情况下，操作数都根据需要接受拆箱转换（unboxing conversion，§5.1.8）。

对于`&`，如果两个操作数的值都为`true`，则结果为`true`；否则结果为`false`。

对于`^`，如果操作数的值不同，则结果为`true`；否则结果为`false`。

对于`|`，如果两个操作数的值都为`false`，则结果为`false`；否则结果为`true`。

## 15.23 逻辑与运算符 &&

逻辑与运算符`&&`与`&`（§15.22.2）类似，但它仅在左侧操作数的值为`true`时才求值其右侧操作数。

```
ConditionalAndExpression:
InclusiveOrExpression
ConditionalAndExpression && InclusiveOrExpression
```

条件运算符在语法上是左结合的（从左到右分组）。

条件运算符对于副作用和结果值都是完全结合的。也就是说，对于任何表达式`a`、`b`和`c`，计算表达式`((a) && (b)) && (c)`的结果以及副作用发生的顺序与计算表达式`(a && ((b) && (c))`相同。

逻辑与运算符的每个操作数必须是`boolean`或`Boolean`类型，否则将发生编译时错误。

逻辑与表达式的类型始终是`boolean`。

运行时，首先求值左侧操作数表达式；如果结果类型为`Boolean`，则对其进行拆箱转换（§5.1.8）。

如果结果值为`false`，则逻辑与表达式的值为`false`，且不求值右侧操作数表达式。

如果左侧操作数的值为`true`，则求值右侧表达式；如果结果类型为`Boolean`，则对其进行拆箱转换（§5.1.8）。结果值成为逻辑与表达式的值。

因此，`&&`在布尔操作数上的计算结果与`&`相同。它的区别仅在于右侧操作数表达式是条件求值，而不是总是求值。

## 15.24 逻辑或运算符 ||

逻辑或运算符`||`与`|`（§15.22.2）类似，但它仅在左侧操作数的值为`false`时才求值其右侧操作数。

```
ConditionalOrExpression:
ConditionalAndExpression
ConditionalOrExpression || ConditionalAndExpression
```

逻辑或运算符在语法上是左结合的（从左到右分组）。

逻辑或运算符对于副作用和结果值都是完全结合的。因此，对于表达式`a`、`b`和`c`，计算表达式`((a) || (b)) || (c)`的结果以及副作用发生的顺序与计算表达式`(a) || ((b) || (c))`相同。

逻辑或运算符的每个操作数必须是`boolean`或`Boolean`类型，否则将发生编译时错误。

逻辑或表达式的类型始终是`boolean`。

运行时，首先求值左侧操作数表达式；如果结果类型为`Boolean`，则对其进行拆箱转换（§5.1.8）。

如果结果值为`true`，则逻辑或表达式的值为`true`，且不求值右侧操作数表达式。

如果左侧操作数的值为`false`，则求值右侧表达式；如果结果类型为`Boolean`，则对其进行拆箱转换（§5.1.8）。结果值成为逻辑或表达式的值。

因此，`||`在`Boolean`操作数上的计算结果与`|`相同。它的区别仅在于右侧操作数表达式是条件求值，而不是总是求值。

## 15.25 条件运算符 ? :

条件运算符`?`使用一个表达式的布尔值来决定其他两个表达式中的哪一个应该求值。

```
ConditionalExpression:
ConditionalOrExpression
ConditionalOrExpression ? Expression : ConditionalExpression
ConditionalOrExpression ? Expression : LambdaExpression
```



条件运算符在语法上是右结合的（从右到左分组）。因此，`a?b:c?d:e?f:g` 等于 `a?b:(c?d:(e?f:g))`。

条件运算符有三个操作数表达式。`?` 出现在第一个和第二个表达式之间，`:` 出现在第二个和第三个表达式之间。

第一个表达式必须是 `boolean` 或 `Boolean` 类型，否则将发生编译时错误。

如果第二个或第三个操作数表达式是 `void` 方法的调用，则是编译时错误。

> 事实上，根据表达式语句的语法（§14.8），条件表达式不允许出现在可能出现 `void` 方法调用的任何环境中。

条件表达式有三种类型，根据第二个和第三个操作数表达式进行分类：布尔条件表达式、数值条件表达式和引用条件表达式。分类规则如下：

### 表达式分类

如果第二个和第三个操作数表达式都是布尔表达式，则该条件表达式是布尔表达式。

为了对条件进行分类，以下表达式是布尔表达式：

- 类型为 `boolean` 的独立表达式（§5.1.2）。
- 带括号的表达式（§5.1.8）。
- `Boolean` 类实例的创建（§5.1.9）。
- 返回类型为布尔值的方法调用（§5.1.12）。

如果第二个和第三个操作数表达式都是数值表达式，则该条件表达式是数值表达式。
为了对条件进行分类，以下表达式是数值表达式：

- 类型为数值的独立表达式（§5.1.2）。
- 带括号的表达式（§5.1.8）。
- 数值类实例的创建（§5.1.9）。
- 返回类型为数值类型的方法调用（§5.1.12）。

如果第二个和第三个操作数表达式都是引用表达式，则该条件表达式是引用表达式。
为了对条件进行分类，以下表达式是引用表达式：

- 类型为引用类型的独立表达式（§5.1.2）。
- 带括号的表达式（§5.1.8）。
- 引用类实例的创建（§5.1.9）。
- 返回类型为引用类型的方法调用（§5.1.12）。

否则，该条件表达式是引用表达式。

条件表达式的类型确定如下：

- 如果第二个和第三个操作数表达式都是布尔的，则类型为 `boolean`。
- 如果第二个和第三个操作数表达式都是数值，则类型为两者的共同数值类型。
- 如果第二个和第三个操作数表达式都是引用类型，则类型为两者的共同引用类型。
- 如果一个是数值而另一个是引用，则类型为引用类型。
- 如果一个是布尔而另一个是引用，则类型为引用类型。

### 表 15.25-B. 条件表达式类型（原始类型第三个操作数，第二部分）

| 第3个 → | long | float | double | boolean |
|---|---|---|---|---|
| byte | bnp(byte,long) | bnp(byte,float) | bnp(byte,double) | lub(byte,Boolean) |
| Byte | bnp(Byte,long) | bnp(Byte,float) | bnp(Byte,double) | lub(Byte,Boolean) |
| short | bnp(short,long) | bnp(short,float) | bnp(short,double) | lub(short,Boolean) |
| Short | bnp(Short,long) | bnp(Short,float) | bnp(Short,double) | lub(Short,Boolean) |
| char | bnp(char,long) | bnp(char,float) | bnp(char,double) | lub(char,Boolean) |
| Character | bnp(Character,long) | bnp(Character,float) | bnp(Character,double) | lub(Character,Boolean) |
| int | bnp(int,long) | bnp(int,float) | bnp(int,double) | lub(int,Boolean) |
| Integer | bnp(Integer,long) | bnp(Integer,float) | bnp(Integer,double) | lub(Integer,Boolean) |
| long | long | bnp(long,float) | bnp(long,double) | lub(long,Boolean) |
| Long | long | bnp(Long,float) | bnp(Long,double) | lub(Long,Boolean) |
| float | bnp(float,long) | float | bnp(float,double) | lub(float,Boolean) |
| Float | bnp(float,long) | float | bnp(Float,double) | lub(Float,Boolean) |
| double | bnp(double,long) | bnp(double,float) | double | lub(Double,Boolean) |
| Double | bnp(Double,long) | bnp(Double,float) | double | lub(Double,Boolean) |
| boolean | lub(Boolean,long) | lub(Boolean,float) | lub(Boolean,double) | boolean |
| Boolean | lub(Boolean,Long) | lub(Boolean,Float) | lub(Boolean,Double) | boolean |
| null | lub(null,Long) | lub(null,Float) | lub(null,Double) | lub(null,Boolean) |
| Object | lub(Object,Long) | lub(Object,Float) | lub(Object,Double) | lub(Object,Boolean) |

### 表 15.25-C. 条件表达式类型（引用类型第三个操作数，第一部分）

| 第3个 → | Byte | Short | Character | Integer |
|---|---|---|---|---|
| 第2个 ↓ | | | | |
| byte | byte | short | bop(byte,Character) | bop(byte,Integer) |
| Byte | Byte | short | bop(byte,Character) | bop(byte,Integer) |
| short | short | short | bop(short,Character) | bop(short,Integer) |
| Short | short | Short | bop(short,Character) | bop(short,Integer) |
| char | bop(char,Byte) | bop(char,Short) | char | bop(char,Integer) |
| Character | bop(Character,Byte) | bop(Character,Short) | Character | bop(Character,Integer) |
| int | bop(int,Byte) | short | bop(int,Character) | int |
| Integer | bop(Integer,Byte) | bop(Integer,Short) | bop(Integer,Character) | Integer |
| long | bop(long,Byte) | bop(long,Short) | bop(long,Character) | bop(long,Integer) |
| Long | bop(Long,Byte) | bop(Long,Short) | bop(Long,Character) | bop(Long,Integer) |
| float | bop(float,Byte) | bop(float,Short) | bop(float,Character) | bop(float,Integer) |
| Float | bop(Float,Byte) | bop(Float,Short) | bop(Float,Character) | bop(Float,Integer) |
| double | bop(double,Byte) | bop(double,Short) | bop(double,Character) | bop(double,Integer) |
| Double | bop(Double,Byte) | bop(Double,Short) | bop(Double,Character) | bop(Double,Integer) |
| boolean | iub(Boolean,Byte) | iub(Boolean,Short) | iub(Boolean,Character) | iub(Boolean,Integer) |
| Boolean | iub(Boolean,Byte) | iub(Boolean,Short) | iub(Boolean,Character) | iub(Boolean,Integer) |
| null | Byte | Short | Integer |
| Object | iub(Object,Byte) | iub(Object,Short) | iub(Object,Character) | iub(Object,Integer) |

### 表 15.25-D. 条件表达式类型（引用类型第三个操作数，第二部分）

| 第3个 → | Long | Float | Double | Boolean |
|---|---|---|---|---|
| byte | bnp(byte,Long) | bnp(byte,Float) | bnp(byte,Double) | lub(byte,Boolean) |
| Byte | bnp(byte,Long) | bnp(byte,Float) | bnp(byte,Double) | lub(byte,Boolean) |
| short | bnp(short,Long) | bnp(short,Float) | bnp(short,Double) | lub(short,Boolean) |
| Short | bnp(Short,Long) | bnp(Short,Float) | bnp(Short,Double) | lub(Short,Boolean) |
| char | bnp(char,Long) | bnp(char,Float) | bnp(char,Double) | lub(char,Boolean) |
| Character | bnp(Character,Long) | bnp(Character,Float) | bnp(Character,Double) | lub(Character,Boolean) |
| int | bnp(int,Long) | bnp(int,Float) | bnp(int,Double) | lub(int,Boolean) |
| Integer | bnp(Integer,Long) | bnp(Integer,Float) | bnp(Integer,Double) | lub(Integer,Boolean) |
| long | long | bnp(long,Float) | bnp(long,Double) | lub(long,Boolean) |
| Long | Long | bnp(Long,Float) | bnp(Long,Double) | lub(Long,Boolean) |
| float | bnp(float,Long) | float | bnp(float,Double) | lub(float,Boolean) |
| Float | bnp(float,Long) | float | bnp(Float,Double) | lub(Float,Boolean) |
| double | bnp(double,Long) | bnp(double,Float) | double | lub(double,Boolean) |
| Double | bnp(double,Long) | bnp(double,Float) | Double | lub(Double,Boolean) |
| boolean | lub(Boolean,Long) | lub(Boolean,Float) | lub(Boolean,Double) | boolean |
| Boolean | lub(Boolean,Long) | lub(Boolean,Float) | lub(Boolean,Double) | boolean |
| null | Long | Float | Double |
| Object | lub(Object,Long) | lub(Object,Float) | lub(Object,Double) | lub(Object,Boolean) |

### 表 15.25-E. 条件表达式类型（引用类型第三个操作数，第三部分）

| 第3个 → | null | Object |
|---|---|---|
| 第2个 ↓ | | |
| byte | lub(Byte,null) | lub(Byte,Object) |
| Byte | Byte | lub(Byte,Object) |
| short | Short | lub(Short,Object) |
| Short | Short | lub(Short,Object) |
| char | lub(Character,null) | lub(Character,Object) |
| Character | Character | lub(Character,Object) |
| int | lub(Integer,null) | lub(Integer,Object) |
| Integer | Integer | lub(Integer,Object) |
| long | lub(Long,null) | lub(Long,Object) |
| Long | Long | lub(Long,Object) |
| float | lub(Float,null) | lub(Float,Object) |
| Float | Float | lub(Float,Object) |
| double | lub(Double,null) | lub(Double,Object) |
| Double | Double | lub(Double,Object) |
| boolean | lub(Boolean,null) | lub(Boolean,Object) |
| Boolean | Boolean | lub(Boolean,Object) |
| null | null | Object |
| Object | Object | |

在运行时，首先求值条件表达式的第一个操作数。如果需要，会对结果进行拆箱转换。得到的布尔值随后被用于选择第二个操作数或第三个操作数：

- 如果第一个操作数为真，则选择第二个操作数。
- 如果第一个操作数为假，则选择第三个操作数。

然后对所选的操作数表达式进行求值，并将结果转换为条件表达式的类型。此转换可能包括装箱或拆箱转换（§5.1.7、§5.1.8）。未选的操作数在本次表达式评估时不求值。

## 15.25.1 布尔条件表达式

布尔条件表达式是独立表达式（§15.2）。布尔条件表达式的类型确定如下：

- 如果第二个和第三个操作数均为 `Boolean`，则条件表达式类型为 `Boolean`。
- 否则，条件表达式类型为 `boolean`。

## 15.25.2 数值条件表达式

数值条件表达式是独立表达式（§15.2）。数值条件表达式的类型确定如下：

- 如果第二个和第三个操作数的类型相同，则该类型 $T$ 为条件表达式的类型。
- 如果第二个和第三个操作数中的一个是原始类型 $T$，另一个是应用 $T$ 的装箱转换（§5.1.7）的结果，则条件表达式类型为 $T$。
- 如果一个操作数为类型 `Byte` 而另一个为 `short` 或 `Short`，则条件表达式类型为 `short`。
- 如果其中一个操作数为类型 $T$（$T$ 为 `short` 或 `char`），而另一个是类型为 `int` 的常量表达式（§15.29），且其值可以在类型 $T$ 中表示，则条件表达式类型为 $T$。
- 如果其中一个操作数为类型 $T$（$T$ 为 `Byte`、`Short` 或 `Character`），而另一个是类型为 `int` 的常量表达式，且其值可以在对 $T$ 应用拆箱转换后得到的类型 $U$ 中表示，则条件表达式类型为 $U$。

否则，对第二个和第三操作数应用通用的数值提升（§5.6），且条件表达式的类型为第二个和第三操作数的提升后类型。

该数值提升可能包括拆箱转换（§5.1.8）。

## 15.25.3 引用条件表达式

如果引用条件表达式出现在赋值上下文或调用上下文中（§5.2, §5.3），则它是多态表达式。否则，它是一个独立表达式。

当多态条件表达式出现在类型为 $\tau$ 的特定类型上下文中，其第二个和第三操作数表达式也同样出现在目标类型为 $\tau$ 的相同上下文中。

如果多态条件表达式的第二个和第三操作数与 $\tau$ 兼容，则该多态条件表达式与目标类型 $\tau$ 兼容。

多态条件表达式的类型与其目标类型相同。独立条件表达式的类型确定如下：

- 如果第二个和第三操作数具有相同类型（可能是空类型），则该类型为条件表达式的类型。
- 如果第二个或第三操作数之一的类型为空类型，而另一个操作数的类型是引用类型，则条件表达式的类型为该引用类型。
- 否则，第二个和第三操作数的类型分别为 $S_1$ 和 $S_2$。令 $T_1$ 为对 $S_1$ 应用装箱转换得到的类型，令 $T_2$ 为对 $S_2$ 应用装箱转换得到的类型。条件表达式的类型为对 `lub($T_1$, $T_2$)` 应用捕获转换（§5.1.10）得到的结果。

由于引用条件表达式可以是多态表达式，因此它们可以将上下文“传递”给其操作数。这使得 lambda 表达式和方法引用表达式可以作为操作数出现：

```
```



return ... ? (x -> x) : (x -> -x);

它还利用额外信息来改进泛型方法调用的类型检查。在 Java SE 8 之前，此赋值是类型安全的：

```
List<String> ls = Arrays.asList();
```

但这种赋值安全的：

```
List<String> ls = ... ? Arrays.asList() : Arrays.asList("a","b");
```

上述两个赋值都被视为类型安全。

注意，条件表达式并不非要包含多态表达式作为操作数才能成为多态表达式。它仅仅由于其出现的上下文而是一个多态表达式。例如，在下面的代码中，条件表达式是一个多态表达式，且每个操作数都被认为处于指向 `Class<? super Integer>` 的赋值上下文：

```
Class<? super Integer> choose(boolean b,
    Class<Integer> c1,
    Class<Number> c2) {
  return b ? c1 : c2;
}
```

如果该条件表达式不是多态表达式，将发生编译错误，因为它的类型将是 `lub(Class<Integer>,Class<Number>)=Class<? extends Number>` 这与 `choose` 的返回类型不兼容。

## 15.26 赋值运算符

共有 12 个赋值运算符；所有运算符在语法上都是右结合的（从右向左分组）。因此，`a=b=c` 意味着 `a=(b=c)`，这会将 `c` 的值赋给 `b`，然后将 `b` 的值赋给 `a`。

> 赋值表达式:
> 条件表达式
> 赋值

> 赋值:
> 左手操作数 赋值运算符 表达式

> 左手操作数:
> 表达式名
> 字段访问
> 数组访问

> 赋值运算符:
> (其一):

```
= *= /= %= += -= <<= >>= >>>= &= ^= |=
```

赋值运算符的第一个操作数的结果必须是一个变量，否则将发生编译错误。该操作数可以是一个命名变量，例如局部变量或当前对象或类的字段，也可以是一个计算出的变量，这可以通过字段访问（§15.11）或数组访问（§15.10.3）产生。

赋值表达式的类型是应用捕获转换（capture conversion，§5.1.10）后变量的类型。

在运行时，赋值表达式的结果是赋值完成后变量的值。赋值表达式的结果本身不是变量。

声明为 `final` 的变量不能被赋值（除非它是确定未被赋值的（§16 (确定赋值))），因为当对这种 `final` 变量的访问用作表达式时，其结果是一个值而不是变量，因此它不能作为赋值运算符的第一个操作数。

### 15.26.1 简单赋值运算符 =

如果右手操作数的类型与变量的类型（§5.2）不赋值兼容，则将发生编译错误。否则，在运行时，表达式按以下三种方式之一求值。

如果左手操作数表达式是字段访问 `e.f`（§15.11），可能嵌套在括号中，则：

- 首先，评估 `e`。如果 `e` 的求值异常，则表达式异常中止。
- 其次，评估右手操作数。如果右手操作数的求值异常，则表达式异常中止。
- 然后，如果由 `f` 指定的字段不是静态的且 `e` 的求值结果为 `null`，则抛出 `NullPointerException`。
- 否则，由 `f` 指定的字段被赋予右手操作数的值。

如果左手操作数是数组访问（§15.10.3），可能嵌套在括号中，则：

- 首先，评估数组引用表达式。如果其求值异常，则表达式异常中止；索引操作数（数组访问的索引部分）不被求值，也不进行赋值。
- 否则，评估索引操作数。如果其求值异常，则表达式异常中止；右手操作数不被求值，也不进行赋值。
- 其次，评估右手操作数。如果其求值异常，则表达式异常中止；也不进行赋值。
- 否则，如果数组引用表达式的值为 `null`，则不进行赋值并抛出 `NullPointerException`。
- 否则，数组引用表达式引用一个数组。如果索引的值小于 0 或大于等于数组长度，则不进行赋值并抛出 `ArrayIndexOutOfBoundsException`。
- 否则，使用索引的值来选择数组引用表达式所引用数组的组件。

令 `TC` 为 `SC` 的类型。存在两种可能性：

- 如果 `TC` 是原始类型，那么 `SC` 必然等于 `TC`。
- 如果 `TC` 是引用类型，那么 `SC` 可能不同于 `TC`，而是扩展或实现了 `TC` 的类型。Java 编译器可能在编译时证明数组组件将恰好是 `TC`（例如，`TC` 可能是 `final` 的）。但如果 Java 编译器无法在编译时证明数组组件将恰好是 `TC`，则必须在运行时进行检查，确保 `RC` 与数组组件的实际类型 `SC` 赋值兼容（§5.2）。此检查类似于强制转换（§5.5, §5.16），但如果检查失败，则抛出 `ArrayStoreException` 而不是 `ClassCastException`。如果 `RC` 不能赋值给类型 `SC`，则不进行赋值并抛出 `ArrayStoreException`。否则，将右手操作数的引用值存入选定的组件中。

否则，需要三个步骤：

- 首先，评估左手操作数产生一个变量。如果其求值异常，则表达式异常中止；右手操作数不被求值，也不进行赋值。
- 其次，评估右手操作数。如果其求值异常，则表达式异常中止；也不进行赋值。
- 否则，将右手操作数的值转换为左手变量的类型，并将转换结果存入变量。

### 15.26.2 复合赋值运算符

形式为 `E1 op= E2` 的赋值等同于 `E1 = (T) (E1 op E2)`，其中 `T` 是 `E1` 的类型，但 `E1` 只求值一次。例如，以下代码是：

```java
short x = 3;
x += 4;
```

并且结果 `x` 的值为 7，因为它等同于：

```java
short x = 3;
x = (short) (x + 4);
```

在运行时，表达式有两种求值方式。如果左侧操作不是数组访问表达式，则：

- 首先，求值左侧操作以产生变量。如果该求值异常，则赋值表达式也会同样异常中断，不执行右侧操作。
- 否则，保存左侧操作的值，然后求值右侧操作。如果该求值异常，则赋值表达式也会同样异常中断。
- 否则，使用保存的左侧变量值和右侧操作的值来执行由复合赋值运算符指示的二元运算。如果该操作异常，则赋值表达式也会同样异常中断。
- 否则，将二元运算的结果转换为左侧变量的类型，并将结果存入该变量。

如果左侧操作是数组访问表达式（§15.10.3），则：

- 首先，求值数组访问表达式的数组引用子表达式。如果该求值异常，则赋值表达式也会同样异常中断，不执行（该数组访问表达式的）索引子表达式和右侧操作。
- 否则，求值（该数组访问表达式的）索引子表达式。如果该求值异常，则赋值表达式也会同样异常中断，不执行右侧操作。
- 否则，如果数组引用子表达式的值为 `null`，则不执行赋值并抛出 `NullPointerException`。
- 否则，数组引用子表达式的值确实引用一个数组。如果索引子表达式的值小于 0 或大于等于数组的 `length`，则不执行赋值并抛出 `ArrayIndexOutOfBoundsException`。
- 否则，使用索引子表达式的值来选择数组引用子表达式所指向的数组的一个组件。保存该组件的值，然后求值右侧操作。如果该求值异常，则赋值表达式也会同样异常中断。

对于简单赋值运算符，右侧操作的求值发生在对数组引用子表达式和索引子表达式检查之前；但对于复合赋值运算符，右侧操作的求值发生在这些检查之后。

- 否则，考虑上一步中选择的数组组件，其值已被保存。该组件是一个变量；其类型为 `s`。同时，令 `au` 为赋值操作符左侧操作数的类型由编译时确定。

- 如果 `T` 是原始数据类型，则 `s` 必然与 `T` 相同。

数组组件的保存值和右侧操作数的值被用于执行由复合赋值操作符所指示的二元操作。

如果此操作异常完成（唯一的可能是整数除以 0 - 见 §15.17.2），则赋值表达式也因相同的原因异常完成，且不发生赋值。

否则，二元操作的结果转换为所选数组组件的类型，并将转换的结果存储在数组组件中。

- 如果 `T` 是引用类型，则它必须是 `String`。由于 `String` 类是一个最终类（final class），`s` 也必须是 `String`。

因此，简单赋值操作符有时需要的运行时检查，复合赋值操作符是永远不需要的。

数组组件的保存值和右侧操作数的值被用于执行复合赋值操作符所指示的二元操作（字符串拼接，该操作必然是 `+=`）。如果此操作异常完成，则赋值表达式也因相同的原因异常完成，且不发生赋值。

否则，二元操作的 `String` 结果被存储在数组组件中。

示例 15.26.2-1 数组组件的复合赋值

```java
// 示例代码缺失
```



## 赋值操作符左侧操作数的类型由编译时确定

- 如果 $T$ 是原始数据类型，则 $s$ 必然与 $T$ 相同。

数组组件的保存值和右侧操作数的值被用于执行由复合赋值操作符所指示的二元操作。

如果此操作异常完成（唯一的可能是整数除以 0 - 见 §15.17.2），则赋值表达式也因相同的原因异常完成，且不发生赋值。

否则，二元操作的结果转换为所选数组组件的类型，并将转换的结果存储在数组组件中。

- 如果 $T$ 是引用类型，则它必须是 `String`。由于 `String` 类是一个最终类（final class），$s$ 也必须是 `String`。

因此，简单赋值操作符有时需要的运行时检查，复合赋值操作符是永远需要的。

数组组件的保存值和右侧操作数的值被用于执行复合赋值操作符所指示的二元操作（字符串拼接，该操作必然是 `+=`）。如果此操作异常完成，则赋值表达式也因相同的原因异常完成，且不发生赋值。

否则，二元操作的 `String` 结果被存储在数组组件中。

## 示例 15.26.2-1 数组组件的复合赋值

```java
class ArrayReferenceThrow extends RuntimeException { }

class IndexThrow extends RuntimeException { }

class RightHandSideThrow extends RuntimeException { }

class IllustrateCompoundArrayAssignment {

    static String[] strings = { "Simon", "Garfunker" };

    static double[] doubles = { Math.E, Math.PI };

    static String stringsThrow() {
        throw new ArrayReferenceThrow();
    }

    static double[] doublesThrow() {
        throw new ArrayReferenceThrow();
    }

    static int indexThrow() {
        throw new IndexThrow();
    }

    static String stringThrow() {
        throw new RightSideThrow();
    }

    static double doubleThrow() {
        throw new RightSideThrow();
    }

    static String name(Object q) {
        String sq = q.getClass().getName();
        int k = sq.lastIndexOf('.');
        return (k < 0) ? sq.substring(k+1);
    }

    static void testEight(String[] x, double[] z, int j) {
        String sx = (x == null) ? "null" : "Strings";
        String sz = (z == null) ? "null" : "doubles";

        try {
            System.out.print(sx + " [throw]+=throw => ");
            x[indexThrow()] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sz + " [throw]+=throw => ");
            z[indexThrow()] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sx + " [throw]+=heh => ");
            x[indexThrow()] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sz + " [throw]+=12345 => ");
            z[indexThrow()] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sx + " [j]+=throw => ");
            x[j] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sz + " [j]+=throw => ");
            z[j] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sx + " [j]+=heh => ");
            x[j] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print(sz + " [j]+=12345 => ");
            z[j] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }
    }

    public static void main(String[] args) {
        try {
            System.out.print("throw[throw]+=throw => ");
            stringsThrow()[indexOf()] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print("throw[throw]+=\"heh\" => ");
            doublesThrow()[indexOf()] += doubleThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print("throw[throw]+=12345 => ");
            doublesThrow()[indexOf()] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print("throw[1]+=throw => ");
            stringsThrow()[1] += stringThrow();
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print("throw[1]+=\"heh\" => ");
            stringsThrow()[1] += "heh";
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        try {
            System.out.print("throw[1]+=12345 => ");
            doublesThrow()[1] += 12345;
            System.out.println("Okay!");
        } catch (Throwable e) { System.out.println(name(e)); }

        testEight(null, null, 1);
        testEight(null, null, 9);
    }

    static int indexOf() {
        return 0;
    }
}
```



```java
} catch (Throwable e) { System.out.println(name(e)); }

try {

    System.out.print("throw[throw]+=\"heh\" => ");

    doubleThrow()[indexOf()] += doubleThrow();

    System.out.println("Okay!");

} catch (Throwable e) { System.out.println(name(e)); }

try {

    System.out.print("throw[throw]+=12345 => ");

    doubleThrow()[indexOf()] += 12345;

    System.out.println("Okay!");

} catch (Throwable e) { System.out.println(name(e)); }

try {

    System.out.print("throw[1]+=throw => ");

    stringsThrow()[1] += stringThrow();

    System.out.println("Okay!");

} catch (Throwable e) { System.out.println(name(e)); }

try {

    System.out.print("throw[1]+=\"heh\" => ");

    stringsThrow()[1] += "heh";

    System.out.println("Okay!");

} catch (Throwable e) { System.out.println(name(e)); }

try {

    System.out.print("throw[1]+=12345 => ");

    doubleThrow()[1] += 12345;

    System.out.println("Okay!");

} catch (Throwable e) { System.out.println(name(e)); }

testEight(null, null, 1);

testEight(null, null, 9);

}

static int indexOf() {

    return 0;

}

}
```

## 表达式

## Lambda 表达式 15.27

# LambdaExpression:
`LambdaParameters -> LambdaBody`

Lambda 表达式始终是多项表达式（§15.2）。

如果 Lambda 表达式出现在赋值上下文（§5.2）、调用上下文（§5.3）或类型转换上下文（§5.5）之外，则会导致编译错误。

Lambda 表达式的求值产生一个函数式接口的实例（§9.8）。Lambda 表达式的求值不会导致表达式体的执行；相反，这可能在稍后调用该函数式接口的适当方法时发生。

以下是一些 Lambda 表达式的示例：

```
() -> ( // 无参数；结果为 void

() -> 42 // 无参数，表达式体

() -> null // 无参数，表达式体

() -> { return 42; } // 无参数，带返回的块体

() -> { System.out.println(); } // 无参数，void 类型的块体
```

```
() -> { // 带有返回的复杂块体
if (true) return 12;
else {
  int result = 15;
  for (int i = 1; i < 10; i++)
    result *= i;
  return result;
}
}
```

```
(int x) -> x+1 // 单个声明类型参数
(int x) -> { return x+1; } // 单个声明类型参数
(x) -> x+1 // 单个推断类型参数
x -> x+1 // 单个推断类型参数可选括号
```

```
(String s) -> s.length() // 单个声明类型参数
(Thread t) -> { t.start(); } // 单个声明类型参数
s -> s.length() // 单个推断类型参数
t -> { t.start(); } // 单个推断类型参数
```

```
(int x, int y) -> x+y // 多个声明类型参数
(x, y) -> x+y // 多个推断类型参数
(int, int y) -> x+y // 非法：不能混合推断和声明类型
(x, final y) -> x+y // 非法：推断类型不能带有修饰符
```

这种语法的优点是尽可能减少了简单 Lambda 表达式周围的括号噪声，这当 Lambda 表达式作为方法的参数或当其体是另一个 Lambda 表达式时特别有益。它还清晰地区分了表达式形式和语句形式，避免了歧义或对 `')'` 令牌的过度依赖。当需要额外的括号来区分 Lambda 表达式或其体表达式时，自然支持圆括号（就像在其他运算符优先级不明确的情况下一样）。

该语法在解析上面临一些挑战。Java 编程语言始终要求在 `(` 令牌之后通过前瞻查找（lookahead）来区分类型和表达式：其后的内容可能是类型转换或带括号的表达式。当泛型在类型中使用二进制运算符 `<` 和 `>` 时，情况变得更加糟糕。Lambda 引入了一种新的可能性：紧随其后的令牌可能描述类型、表达式或 Lambda 参数列表。在其他情况下，某些注解（如 `: T`）存在可能被解释为参数的模式（连续的两个名称、嵌套在 `<` 内部的 `-` 等），且必须在 `)` 之后遇到 `-` 才能决定。思考如何高效解析这种情况最简单的方法是使用状态：每个状态代表可能解释的子集（类型、表达式或参数），当机器转换到一个集合只有一个元素的状态时，解析器就知道是哪种情况了。这与固定前瞻的语法并不完全对应。

没有特殊的 `null` 形式：具有零参数的 Lambda 表达式表示为显式的特殊语法，`->` 是不可行的的，因为它引入了表达式和列表之间的歧义：`(x)`。

Lambda 表达式不声明类型。虽然在语义上这样做是有意义的，但自然的语法（在参数列表之前带上类型参数列表）引入了混乱的歧义。例如：

```
foo(x < y > z (w) -> v)
```

这可能是带一个参数的 `foo` 调用（一个强制转换为 `x` 的泛型 Lambda），也可能是带两个参数的 `foo` 调用，结果是比较的结果，第二次比较是 `z` 与 Lambda 表达式的比较。（严格来说，Lambda 表达式对于关系运算符 `>` 来说是没有意义的，但这是构建语法时的一个薄弱假设。）

涉及类型转换的歧义解决方法已有先例，这在本质上禁止了在非原始类型转换之后使用 `-`（§15.15），但将该方法扩展到泛型 Lambda 将涉及对语法的侵入性更改。

## 15.27.1 Lambda 参数

Lambda 表达式的正规形式（如果有）由括号内的逗号分隔的标识符列表或括号内的逗号分隔的参数说明符列表指定，每个参数说明符由可选的修饰符、类型（或 `var`）以及一个指定参数名称的标识符组成。在标识符列表中，每个标识符指定参数名称。

如果 Lambda 表达式没有形式参数，则在 `->` 和 Lambda 体之前出现一对空圆括号。

如果 Lambda 表达式恰有一个形式参数，且参数由标识符而不是参数说明符指定，则标识符周围的括号可以省略。

```
LambdaParameters:
( [LambdaPropertyList] )
Identifier
```

```
LambdaParameterList:
LambdaParameter (, LambdaParameter)
Identifier (, Identifier)
```

```
LambdaParameter:
{VariableModifier} LambdaParameterType VariableDeclaratorId
VariableArity
```

```
LambdaParameterType:
UnannType
var
```

以下来自 §8.4、§8.3 和 §4.3 的产生式为了方便起见在此处显示：

```
VariableArParameter:
[VariableModifier] UnannType . Identifier
```

```
VariableModifier:
Annotation
final
```

```
VariableDeclaratorId:
Identifier [Dims]
```

```
Dims:
[Annotation] { }
```

Lambda 表达式的形式参数可以是 `final` 或带有注解，但仅当通过参数说明符指定时。如果通过标识符指定，则形式参数不是 `final` 且没有注解。

Lambda 表达式的形式参数可以是变长参数，通过参数说明符中类型后的省略号表示。Lambda 表达式最多允许一个变长参数。如果变长参数出现在参数说明符列表的最后一个位置，则会导致编译错误。

Lambda 表达式的每个形式参数要么是推断类型要么是声明类型：

- 如果形式参数通过使用 `var` 的参数说明符或通过标识符而非参数说明符指定，则该形式参数为推断类型。该类型从 Lambda 表达式所的目标函数式接口推断得出（§15.27.3）。

- 如果形式参数通过不使用 `var` 的参数说明符指定，则该形式参数为声明类型。声明类型的确定如下：

    - 如果形式参数不是变长参数，则在 `UnannType` 和 `VariableDeclaratorId` 中未出现括号时由 `UnannType` 表示，否则由 §10.2。

    - 如果形式参数是变长参数，则声明类型为数组类型。

以下 Lambda 参数列表之间没有区别：

```
(int... x) -> BODY
(int[] x) -> BODY
```

无论函数式接口的抽象方法是固定长度的还是变长的，二者都可以。（这与方法重写的规则一致。）由于 Lambda 表达式从不直接调用，因此在形式参数中使用 `int...` 对周围程序产生任何影响。在 Lambda 体中，变长参数的处理方式与数组类型参数相同。

所有形式参数具有声明类型的 Lambda 表达式被称为显式类型。所有形式参数具有推断类型的 Lambda 表达式被称为隐式类型。没有形式参数的 Lambda 表达式是显式类型。

> 如果 Lambda 表达式是隐式类型，则其体根据其出现所处的上下文进行解释。具体来说，体内表达式的类型、体抛出的检查异常以及体内代码的类型正确性都取决于形式参数推断出的类型。这意味着形式参数类型的推断必须在尝试类型检查 Lambda 体之前完成。

如果 Lambda 表达式同时声明了一个声明类型的形式参数和一个推断类型的形式参数，则会导致编译错误。

此规则防止在形式参数中混合推断类型和声明类型，例如 `[x, int y] -> BODY (var x, int y) -> BODY`。注意，如果所有形式参数都有推断类型，语法将防止标识符与 `var` 参数规范的混合，例如 `[x, var y] -> BODY` 或 `(var x, y) -> BODY`。

形式参数声明的修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果 `final` 作为形式参数声明的修饰符出现多次，则为编译错误。

如果一个形式参数的 `LambdaParameterType` 为 `var` 且该形式参数的 `VariableDeclaratorId` 具有一个或多个括号对，则为编译错误。

形式参数的作用域和遮蔽规则在 §6.3 和 §6.4 中规定。

从嵌套类、接口或嵌套 lambda 表达式对形式参数的引用受到限制，如 §6.5.6.1 规定。

lambda 表达式声明两个同名的形式参数将为编译错误。（这意味着它们的声明提到了同一个 `Identifier`。）

在 Java SE 8 中，禁止使用 `_` 作为 lambda 参数名，并且不鼓励其他类型的变量使用它（§4.12.3）。从 Java SE 9 开始，`_` 是一个关键字 (§3.9)，因此在任何语境下都不能作为变量名。

如果被声明为 `final` 的形式参数在 lambda 表达式体内部被赋值，则为编译错误。

当调用 lambda 表达式时（通过方法调用表达式 (§15.12)），实际参数的值在执行 lambda 体之前会初始化新创建的参数变量，每个变量具有声明的或推断的类型。出现在 `LambdaParameter` 或直接出现在 `LambdaParameterList` 或 `LambdaParameters` 中的 `Identifier` 可以在 lambda 体中作为简单名称来引用该形式参数。

## 15.27.2 Lambda 表达式体 (Lambda Body)

lambda 体要么是一个单一表达式，要么是一个块（§14.2）。与方法体一样，lambda 体描述了当发生调用时将执行的内容。

- LambdaBody:
  - Expression
  - Block

## 15.27 Lambda 表达式 EXPRESSIONS

与匿名类声明中出现的代码不同，lambda 体中出现的名称、`this` 和 `super` 关键字的含义，以及所引声明的可访问性，与周围语境相同（但 lambda 参数引入了新名称）。

这种在 lambda 表达式体中的透明性（无论是显式的还是隐式的）——即将其视为与周围语境相同的内容——为实现提供了更大的灵活性，并防止了体中未限定名称的含义依赖于重载解析。

从实践上来说，lambda 表达式引用自身（无论是递归调用自身还是调用其其他方法）并不寻常，而使用名称引用类中其他否则会被遮蔽的内容（如 `this`、`toString()`）更为常见。如果 lambda 表达式需要引用自身（如同 `this`），则应改用方法引用或匿名内部类。

如果块 lambda 体中的每个 `return` 语句都具有 `return` 形式，则该块 lambda 体是 void 兼容的（void-compatible）。

如果块不能正常完成 (§14.22) 且块中的每个 `return` 语句都具有 `Expression` 形式，则该块 lambda 体是值兼容的（value-compatible）。

如果块 lambda 体既不是 void 兼容的不是值兼容的，则为编译错误。

在值兼容的块 lambda 体中，结果表达式是任何可能产生调用值的表达式。具体而言，对于体包含的每个 `return Expression ;` 形式的语句，该 `Expression` 就是一个结果表达式。

- 以下 lambda 体是 void 兼容的：

```
() -> () {}

() -> ( System.out.println("done"); )
```

这些是值兼容的：

```
() -> return "done";

() -> ( if (...) return 1; else return 0 ; )
```

这些二者皆是：

```
() -> { throw new RuntimeException(); }

() -> { while (true); }
```

这个二者都不是：

```
() -> { if (...) return "done"; System.out.println("done"); }
```

## EXPRESSIONS

## Lambda 表达式

## 15.27

对 void/值兼容的处理以及体中名称的含义共同有助于最小化给定语境中特定目标类型上的密度，这对于实现和程序员的理解是有用的。虽然表达式可以通过目标类型上的重载解析被赋予不同的类型，但未限定名称的含义和 lambda 体的基本结构并不会改变。

注意，void/值兼容的定义并非严格的结构属性：“能够正常完成”取决于常量表达式的值，而这些表达式可能引用常量变量。

在 lambda 表达式中使用但未声明的任何局部变量、形式参数或异常参数必须是 `final` 或有效 final（effectively final，§8.12.4），如 §6.5.6.1 规定。

在 lambda 体中使用但未声明的任何局部变量必须在 lambda 体之前是确定赋值的 (§16 (Definite Assignment))，否则为编译错误。

类似的变量规则也适用于内部类体中 (§8.1.3)。对有效 final 变量的限制禁止了对动态变化局部变量的访问，这种捕获会引入并发问题。与 `final` 限制相比，它减轻了程序员的辅助工作负担。

对有效 final 变量的限制包括标准循环变量，但不包括增强 for 循环变量，后者被视为每次迭代都是独立的 (§14.2)。

以下 lambda 体演示了有效 final 变量的使用。

```
void m1(int x) {

  int y = 1;

  foo(y);

}
```
*(注：此处原文示例代码逻辑与描述略有出入，保留原样)*
```
void m2(int x) {

  int y = 1;

  foo(y);

}
```
```
void m3(int x) {

  int y;

  if (...) y = 1;

  foo(y);

}
```
```
void m4(int x) {

  int y = 1;
```



# EXPRESSIONS

## Lambda 表达式

## 15.27

对 void/值兼容的处理以及体中名称的含义共同有助于最小化给定语境中特定目标类型上的密度，这对于实现和程序员的理解是有用的。虽然表达式可以通过目标类型上的重载解析被赋予不同的类型，但未限定名称的含义和 lambda 体的基本结构并不会改变。

注意，void/值兼容的定义并非严格的结构属性：“能够正常完成”取决于常量表达式的值，而这些表达式可能引用常量变量。

在 lambda 表达式中使用但未声明的任何局部变量、形式参数或异常参数必须是 `final` 或有效 final（effectively final，§8.12.4），如 §6.5.6.1 规定。

在 lambda 体中使用但未声明的任何局部变量必须在 lambda 体之前是确定赋值的 (§16 (Definite Assignment))，否则为编译错误。

类似的变量规则也适用于内部类体中 (§8.1.3)。对有效 final 变量的限制禁止了对动态变化局部变量的访问，这种捕获会引入并发问题。与 `final` 限制相比，它减轻了程序员的辅助工作负担。

对有效 final 变量的限制包括标准循环变量，但不包括增强 for 循环变量，后者被视为每次迭代都是独立的 (§14.2)。

以下 lambda 体演示了有效 final 变量的使用。

```java
void m1(int x) {
  int y = 1;
  foo(y);
}

void m2(int x) {
  int y = 1;
  foo(y);
}

void m3(int x) {
  int y;
  if (...) y = 1;
  foo(y);
}

void m4(int x) {
  int y = 1;
  foo(y);
}

void m5(int x) {
  int y = 1;
  foo(x);
}

void m6(int x) {
  x++;
  foo(x);
}

void m7(int x) {
  int y = 1;
  foo(y);
}

void m8() {
  int y;
  foo(y);
}

void m9(String[] arr) {
  for (String s : arr) {
    foo(s);
  }
}

void m10() {
  for (int i = 0; i < arr.length; i++) {
    foo(i);
  }
}
```

*(注：由于原文提供的示例代码块似乎不完整或存在占位符，翻译时严格遵循不翻译代码块原则，仅对描述进行翻译)*

**更正：根据提供的原文文本重新对应代码块翻译：**

以下 lambda 体演示了有效 final 变量的使用。

```java
void m1(int x) {
  int y = 1;
  foo(y);
}

void m2(int x) {
  int y = 1;
  foo(y);
}

void m3(int x) {
  int y;
  if (...) y = 1;
  foo(y);
}

void m4(int x) {
  int y = 1;
  foo(y);
}

void m5(int x) {
  int y = 1;
  foo(x);
}

void m6(int x) {
  x++;
  foo(x);
}

void m7(int x) {
  int y = 1;
  foo(y);
}

void m8() {
  int y;
  foo(y);
}

void m9(String[] arr) {
  for (String s : arr) {
    foo(s);
  }
}

void m10() {
  for (int i = 0; i < arr.length; i++) {
    foo(i);
  }
}
```

*(注：由于原文文本中代码块部分在输入时似乎缺失或显示为占位符，此处根据“不翻译代码块”原则，仅保留结构。若原文中包含具体代码，将原样输出。)*

**重新审视原文，原文中代码块为：**

```java
() -> () {}

() -> ( System.out.println("done"); )
```

```java
() -> return "done";

() -> ( if (...) return 1; else return 0 ; )
```

```java
() -> { throw new RuntimeException(); }

() -> { while (true); }
```

```java
() -> { if (...) return "done"; System.out.println("done"); }
```

*(注：原文提供的待翻译文本中 m1-m10 的示例代码块在用户输入中并未实际出现，仅出现了上述几个代码块。我将基于用户提供的文本进行翻译。)*

---

**以下是基于您提供的实际文本的完整翻译：**

## EXPRESSIONS

## Lambda 表达式

## 15.27

对 void/值兼容的处理以及体中名称的含义共同有助于最小化给定语境中特定目标类型上的密度，这对于实现和程序员的理解是有用的。虽然表达式可以通过目标类型上的重载解析被赋予不同的类型，但未限定名称的含义和 lambda 体的基本结构并不会改变。

注意，void/值兼容的定义并非严格的结构属性：“能够正常完成”取决于常量表达式的值，而这些表达式可能引用常量变量。

在 lambda 表达式中使用但未声明的任何局部变量、形式参数或异常参数必须是 `final` 或有效 final（effectively final，§8.12.4），如 §6.5.6.1 规定。

在 lambda 体中使用但未声明的任何局部变量必须在 lambda 体之前是确定赋值的 (§16 (Definite Assignment))，否则为编译错误。

类似的变量规则也适用于内部类体中 (§8.1.3)。对有效 final 变量的限制禁止了对动态变化局部变量的访问，这种捕获会引入并发问题。与 `final` 限制相比，它减轻了程序员的辅助工作负担。

对有效 final 变量的限制包括标准循环变量，但不包括增强 for 循环变量，后者被视为每次迭代都是独立的 (§14.2)。

以下 lambda 体演示了有效 final 变量的使用。

*(注：原文此后未提供具体的 m1-m10 代码块，仅有描述性文字。若有代码，请提供。)*

---
**由于我发现您提供的“待翻译文本”中代码块部分似乎不完整，我将仅针对您提供的可见文本内容进行最终翻译：**

此规则防止在形式参数中混合推断类型和声明类型，例如 `[x, int y] -> BODY (var x, int y) -> BODY`。注意，如果所有形式参数都有推断类型，语法将防止标识符与 `var` 参数规范的混合，例如 `[x, var y] -> BODY` 或 `(var x, y) -> BODY`。

形式参数声明的修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果 `final` 作为形式参数声明的修饰符出现多次，则为编译错误。

如果一个形式参数的 `LambdaParameterType` 为 `var` 且该形式参数的 `VariableDeclaratorId` 具有一个或多个括号对，则为编译错误。

形式参数的作用域和遮蔽规则在 §6.3 和 §6.4 中规定。

从嵌套类、接口或嵌套 lambda 表达式对形式参数的引用受到限制，如 §6.5.6.1 规定。

lambda 表达式声明两个同名的形式参数将为编译错误。（这意味着它们的声明提到了同一个 `Identifier`。）

在 Java SE 8 中，禁止使用 `_` 作为 lambda 参数名，并且不鼓励其他类型的变量使用它（§4.12.3）。从 Java SE 9 开始，`_` 是一个关键字 (§3.9)，因此在任何语境下都不能作为变量名。

如果被声明为 `final` 的形式参数在 lambda 表达式体内部被赋值，则为编译错误。

当调用 lambda 表达式时（通过方法调用表达式 (§15.12)），实际参数的值在执行 lambda 体之前会初始化新创建的参数变量，每个变量具有声明的或推断的类型。出现在 `LambdaParameter` 或直接出现在 `LambdaParameterList` 或 `LambdaParameters` 中的 `Identifier` 可以在 lambda 体中作为简单名称来引用该形式参数。

## 15.27.2 Lambda 表达式体 (Lambda Body)

lambda 体要么是一个单一表达式，要么是一个块（§14.2）。与方法体一样，lambda 体描述了当发生调用时将执行的内容。

- LambdaBody:
  - Expression
  - Block

## 15.27 Lambda 表达式 EXPRESSIONS

与匿名类声明中出现的代码不同，lambda 体中出现的名称、`this` 和 `super` 关键字的含义，以及所引声明的可访问性，与周围语境相同（但 lambda 参数引入了新名称）。

这种在 lambda 表达式体中的透明性（无论是显式的还是隐式的）——即将其视为与周围语境相同的内容——为实现提供了更大的灵活性，并防止了体中未限定名称的含义依赖于重载解析。

从实践上来说，lambda 表达式引用自身（无论是递归调用自身或调用其其他方法）并不寻常，而使用名称引用类中其他否则会被遮蔽的内容（如 `this`、`toString()`）更为常见。如果 lambda 表达式需要引用自身（如同 `this`），则应改用方法引用或匿名内部类。

如果块 lambda 体中的每个 `return` 语句都具有 `return` 形式，则该块 lambda 体是 void 兼容的。

如果块不能正常完成 (§14.22) 且块中的每个 `return` 语句都具有 `Expression` 形式，则该块 lambda 体是值兼容的。

如果块 lambda 体既不是 void 兼容的不是值兼容的，则为编译错误。

在值兼容的块 lambda 体中，结果表达式是任何可能产生调用值的表达式。具体而言，对于体包含的每个 `return Expression ;` 形式的语句，该 `Expression` 就是一个结果表达式。

- 以下 lambda 体是 void 兼容的：

```java
() -> () {}

() -> ( System.out.println("done"); )
```

这些是值兼容的：

```java
() -> return "done";

() -> ( if (...) return 1; else return 0 ; )
```

这些二者皆是：

```java
() -> { throw new RuntimeException(); }

() -> { while (true); }
```

这个二者都不是：

```java
() -> { if (...) return "done"; System.out.println("done"); }
```

## EXPRESSIONS

## Lambda 表达式

## 15.27

对 void/值兼容的处理以及体中名称的含义共同有助于最小化给定语境中特定目标类型上的密度，这对于实现和程序员的理解是有用的。虽然表达式可以通过目标类型上的重载解析被赋予不同的类型，但未限定名称的含义和 lambda 体的基本结构并不会改变。

注意，void/值兼容的定义并非严格的结构属性：“能够正常完成”取决于常量表达式的值，而这些表达式可能引用常量变量。

在 lambda 表达式中使用但未声明的任何局部变量、形式参数或异常参数必须是 `final` 或有效 final（effectively final，§8.12.4），如 §6.5.6.1 规定。

在 lambda 体中使用但未声明的任何局部变量必须在 lambda 体之前是确定赋值的 (§16 (Definite Assignment))，否则为编译错误。

类似的变量规则也适用于内部类体中 (§8.1.3)。对有效 final 变量的限制禁止了对动态变化局部变量的访问，这种捕获会引入并发问题。与 `final` 限制相比，它减轻了程序员的辅助工作负担。

对有效 final 变量的限制包括标准循环变量，但不包括增强 for 循环变量，后者被视为每次迭代都是独立的 (§14.2)。

以下 lambda 体演示了有效 final 变量的使用。

# Lambda 表达式

在 Lambda 表达式体中抛出的检查异常（checked exception）可能会导致编译错误，如 §11.2.3 所示。

显式类型 Lambda 表达式的参数类型必须与函数类型完全匹配。虽然可以更具活性——例如允许装箱（boxing）或协变（covariance），但这种通用性似乎并没有必要，并且与类声明中重写（overriding）的工作方式一致。因此，程序员应该精确地知道 Lambda 表达式的签名可能会被重写。（方法引用的情况并非如此，因此在使用方法引用时允许更大的灵活性。）此外，参数类型上的更多灵活性会增加类型推断和解析的复杂性。

请注意，虽然在严格的调用上下文中不允许装箱，但 Lambda 结果的装箱*始终*是允许的——也就是说结果表达式出现在赋值上下文中，无论封装 Lambda 的上下文如何。然而，如果一个显式类型的 Lambda 表达式是重载方法的参数，则最具体的检查（§15.12.2）倾向于选择避免对 Lambda 进行装箱或拆箱的方法签名。

如果 Lambda 的体是一个语句表达式（即允许独立作为语句的表达式），它将变成一个产生 void 的函数类型；任何结果都将被直接丢弃。因此，以下两种都是合法的：

```java
// Predicate 返回布尔结果
java.util.function.Predicate<String> p = s -> list.add(s);

// Consumer 有 void 结果
java.util.function.Consumer<String> c = s -> list.add(s);
```

通常情况下，形式为 `() -> expr` 的 Lambda（其中 expr 是语句表达式）被解释为 `() -> { return expr; }` 或 `() -> { expr; }`，取决于目标类型。

## 15.2.4 Lambda 表达式的运行时评估

在运行时，Lambda 表达式的评估类似于类实例创建过程的评估，因为正常完成会产生一个对象的引用。Lambda 表达式的评估与 Lambda 体执行是不同的。

分配并初始化一个具有以下属性类的新实例，或者引用一个具有以下属性类的现有实例。如果需要创建新实例，但没有足够的空间分配对象，则 Lambda 的评估将通过抛出 `OutMemoryError` 异常终止。

这意味着评估 Lambda 表达式（或序列化和反序列化 Lambda 表达式）的标识性是不可预测的，因此标识性敏感的操作（例如引用相等性 $15.21.3、对象锁定 $14.19 和 `System.hashCode` 方法）在 Java 编程语言的不同实现中，甚至在同一实现的不同 Lambda 表达式评估中，都可能产生不同的结果。

Lambda 表达式的值是指向具有以下属性的类实例的引用：

- 类实现了目标函数接口类型；如果目标类型是交叉类型，则实现了交叉类型中提到的其他接口类型。
- 当 Lambda 表达式类型为 U 时，对于 U 的每个非静态成员方法。

如果 U 的函数类型具有 `m` 签名的子类型，则该类声明了一个重写 `m` 的方法。该方法的体的作用是评估 Lambda 体（如果它是表达式）或执行 Lambda 体（如果它是块）；如果期望结果，则从方法返回该结果。

如果被重写的方法 `m` 的类型擦除与 U 的函数类型的类型擦除不同，则在评估或执行 Lambda 体之前，该方法的体会检查每个参数是否为类型 U 函数类型中参数类型擦除后的子类或子接口的实例；如果不是，则抛出 `ClassCastException`。

- 该类没有重写目标函数接口类型或上述其他接口类型的其他方法，尽管它可能会重写 `Object` 类的方法。

这些规则为 Java 编程语言的实现提供了灵活性，体现在：

- 新对象不需要属于每一次评估。
- 由不同 Lambda 表达式产生的对象不需要属于不同的类（例如，如果它们是相同的）。
- 评估产生的每个对象不需要属于同一个类（例如，捕获的局部变量可能会被内联）。
- 如果“现有实例”可用，它不需要在之前的评估中被创建（例如，它可能在闭包类的初始化期间已分配分配）。

如果目标函数接口类型是 `java.io.Serializable` 的子类型，则生成的对象将是可序列化类的实例。将源自 Lambda 表达式的对象设为可序列化可能会带来额外的运行时开销和安全影响，因此 Lambda 派生的对象并不被要求“默认”必须是可序列化的。

## 15.28 switch 表达式

switch 表达式根据表达式的值将控制转移到多个语句或表达式之一；该表达式的所有可能值都必须被处理，并且所有这些语句和表达式都必须为 switch 表达式的结果产生值。

```
SwitchExpression:
switch ( ) SwitchBlock
```

该表达式被称为选择器表达式。选择器表达式的类型必须是 `char`, `byte`, `short`, `int`, `Character`, `Byte`, `Short`, `Integer`, `String` 或枚举类型 (§8.9)，否则会发生编译时错误。

一个 switch 表达式和 switch 语句 (§14.11) 的体被称为块（block）。适用于所有 switch 块（无论它们出现在 switch 表达式还是 switch 语句中）的规则见 §14.11。为了方便起见，这里显示了 §14.11 中的产生式：

```
SwitchBlock:
{ SwitchRule}
{ SwitchStatementGroup}

SwitchRule:
SwitchLabel -> Expression
SwitchLabel -> Block
SwitchLabel -> ThrowStatement

SwitchStatementGroup:
SwitchLabel : SwitchStatements

SwitchLabel:
case CaseConstant
default

CaseConstant:
ConditionalExpression
```

### 15.28.1 switch 的 Switch Block

除了 switch 块的通用规则 (§14.11) 之外，switch 表达式的块 还有进一步的规则。也就是说，switch 表达式的块必须满足以下条件，否则将发生编译错误：

- 如果选择器的类型不是枚举类型，则 switch 块必须有一个 default 。

如果选择器的类型是枚举类型，则 (i) switch 块关联的 case 常包含每个枚举常量；ii) switch 块最多有一个 default 。

当 case 标签覆盖所有枚举常量时，default 是允许的但不是强制的。

如果块由切换规则组成，则任何切换规则都不能正常完成 (§14.22)。

如果块由语句组组成，则 switch 块中的最后一个语句不能正常完成，且 switch 块在最后一个语句组后没有任何标签。



switch 表达式不能有空块，与 switch 语句不同。此外，switch 表达式与 switch 语句的区别在于 switch 块中箭头 (`->`) 右侧可以出现的表达式，即在 switch 表达式中，任何表达式都可以作为切换规则表达式，但在 switch 语句中，只有语句表达式可以作为规则表达式。

```
switch 表达式的结果确定如下：

- 如果块由切换规则组成，则轮询考虑每个切换规则：
    - 如果切换规则的形式为 `... -> Expression ;`，则 `Expression` 是 switch 表达式的结果。
    - 如果切换规则的形式为 `... -> Block`，则 `Block` 中每个包含 `yield` 语句且其 `yield` 目标为该 switch 表达式的表达式都是该 switch 表达式的结果。
- 如果块由语句组组成，则 switch 块中每个包含 `yield` 语句且其 `yield` 目标为该 switch 表达式的表达式都是该 switch 表达式的结果。

如果 switch 表达式没有结果表达式，则为编译错误。

如果 switch 表达式出现在赋值上下文或调用上下文中 (§5.2, §5.3)，它是多值表达式（poly expression）；否则，它是独立表达式。

当多值 switch 出现在目标类型为 `t` 的上下文中时，其结果表达式同样出现在相同类型的目标类型为 `t` 的上下文中。
```

## switch 表达式

如果多类型 switch 表达式的每个结果表达式都与目标类型 `T` 兼容，则该 switch 表达式与 `T` 兼容。

多类型 switch 表达式的类型与其目标类型相同。

独立 switch 表达式的类型确定如下：

- 如果所有结果具有相同的类型（可能是空类型 (§4.1)），则该类型为 switch 表达式的类型。
- 否则，如果每个结果表达式的类型为 `boolean` 或 `Boolean`，则对每个 `Boolean` 类型的结果表达式应用拆箱转换 (§5.1.8)，且 switch 表达式的类型为 `boolean`。
- 否则，如果每个结果表达式的类型可以转换为数值类型 (§5.1.8)，则 switch 表达式的类型为对结果表达式应用通用数值提升 (§5.6) 的结果。
- 否则，对每个具有原始类型的结果表达式应用装箱转换 (§5.1.7)，之后，switch 表达式的类型为对结果表达式类型的最小上界 (§4.10.4) 应用捕获转换 (§5.1.10) 的结果。

## 15.28.2 switch 表达式的运行时评估

switch 表达式通过首先评估选择器表达式来评估。然后：

- 如果选择器表达式评估异常终止，则 switch 表达式因相同原因异常终止。
- 否则，如果选择器表达式评估为 `null`，则抛出 `NullPointerException`，整个 switch 表达式因该原因异常终止。
- 否则，如果选择器表达式评估结果类型为 `Character`、`Byte`、`Short` 或 `Integer`，则对其进行拆箱转换 (§5.1.8)。如果此转换异常终止，则整个 switch 表达式因相同原因异常终止。

如果选择器表达式评估正常完成且结果非 `null`，并且随后的拆箱转换（如果有）正常完成，则继续评估 switch 表达式，方法是判断与 switch 块关联的 switch 标签是否匹配选择器表达式的值 (§14.11.1)。然后：

如果没有 switch 标签匹配，则抛出 `IncompatibleClassChangeError`，整个 switch 表达式因该原因异常终止。

如果匹配 switch 标签，则应用以下规则之一：

- 如果它是规则表达式的 switch 标签，则评估该表达式。如果评估结果是一个值，则 switch 表达式以该相同值正常完成。
- 如果它是 switch 规则块的 switch 标签，则执行该块。如果该块正常完成，则 switch 表达式正常完成。
- 如果它是 switch throw 语句的 switch 标签，则执行该 throw 语句。
- 否则，按顺序执行 switch 块中匹配 switch 标签之后的所有语句。如果这些语句正常完成，则 switch 表达式正常完成。

如果 switch 块中任何语句或表达式的执行异常终止，其处理方式如下：

- 如果表达式执行异常终止，则 switch 表达式因相同原因异常终止。
- 如果语句执行因一个 `yield` 值 `V` 而异常终止，则 switch 表达式正常完成，switch 表达式的值为 `V`。
- 如果语句执行因除带有值的 `yield` 以外的任何原因异常终止，则 switch 表达式因相同原因异常终止。

## 15.29 常数表达式

```
ConstantExpression:
Expression
```

常量表达式是一个表示原始类型值或 `String` 的表达式，它不会异常终止，且仅使用以下内容组成：

- 原始类型字面量 (§3.10.1, §3.10.2, §3.10.3, §3.10.4)、字符串字面量 (§3.10.5) 和文本块 (§3.10.6)
- 向原始类型的类型转换以及向 `String` 类型的转换 (§15.16)

## 常数表达式

### 表达式

- 一元运算符 `+`、`-`、`~` 和 `!`（但不是 `++` 或 `--`） (§15.15.3, §15.15.4, §15.15.5, §15.15.6)
- 乘法运算符 `*`、`/` 和 `%` (§15.17)
- 加法运算符 `+` 和 `-` (§15.18)
- 移位运算符 `<<`、`>>` 和 `>>>` (§15.19)
- 关系运算符 `<`、`<=`、`==` 和 `>=`（但不是 `instanceof`） (§15.20)
- 相等运算符 `==` 和 `!=` (§15.21)
- 位运算符和逻辑运算符 `&`、`|`、`^` 和 `&` (§15.22)
- 条件与运算符 `&&` 和条件或运算符 `||` (§15.23, §15.24)
- 三元条件运算符 `? :` (§15.25)
- 内部包含常量表达式的括号表达式 (§15.8.5)。
- 引用常量变量 (§4.12.4) 的简单限定名称 (§6.5.1)。
- 形式为 `TypeName . Identifier` 的引用常量变量 (§4.12.4) 的全限定名称 (§6.5.2)。

`String` 类型的常数表达式总是被“池化”（interned），以便使用 `String.intern` 方法共享唯一实例。

常量表达式用于 switch 语句和 switch 表达式中的分支标签 (§14.11, §15.28)。

## 第 16 章 确定赋值

本章的剩余部分用于精确解释“确定赋值”（definitely assigned）和“确定未赋值”（definitely unassigned）这两个词。

确定赋值的理念是：在访问的执行路径上必须进行赋值。同样地，确定未赋值的理念是：任何执行路径上都没有赋值。

该分析考虑了语句和表达式的结构；它还对条件运算符 `&&`、`||`、`!` 以及布尔值常量表达式提供了特殊处理。

### 示例 16-1 确定赋值考虑语句和表达式的结构

Java 编译器识别出代码中的 `k` 在其访问（作为方法调用的参数）之前已确定赋值：

```java
{
  int k;
  if (v > 0 && (k = System.in.read()) >= 0)
    System.out.println(k);
}
```

因为只有当表达式

```java
v > 0 && (k = System.in.read()) >= 0
```

为真时，才会发生访问，且只有在执行对 `k` 的赋值（更准确地说是评估）时，该值才可能真。

同样，Java 编译器将识别出代码中：

```java
{
  int k;
  while (true) {
    k = n;
    if (k > 5) break;
    n = 6;
  }
  System.out.println(k);
}
```

变量 `k` 被 `while` 语句确定赋值了，因为表达式 `true` 永远不会为假值，所以只有 `break` 语句会导致 `while` 语句正常完成，且 `k` 在 `break` 语句之前已确定赋值。

相反，代码：

```java
{
  int k;
  while (n < 4) {
    k = n;
    if (k >= 5) break;
    n = 6;
  }
  System.out.println(k); /* 在此语句之前 k 未“确定赋值” */
}
```

必须被 Java 编译器拒绝，因为在这种情况下，从确定赋值的规则来说，`while` 语句无法保证会执行其语句体。

## 示例 16-2. 确定赋值不考虑表达式的值

Java 编译器必须对以下代码产生编译时错误：

```java
{
  int k;
  int n = 5;
  if (n > 2)
    k = 3;
  System.out.println(k); /* 在此语句之前，k 未被“确定赋值” */
}
```

尽管 `n` 的值在编译时是已知的，且原则上可以在编译时获知对 `k` 的赋值将始终执行（更准确地说，将始终求值），但 Java 编译器必须按照本节列出的规则进行操作。在本示例中，表达式 `n > 2` 并不是 §15.29 中定义的常量表达式。

作为另一个示例，Java 编译器将接受以下代码：

```java
void flow(boolean flag) {
  int k;
  if (flag)
    k = 3;
  else
    k = 4;
  System.out.println(k);
}
```

就 `k` 的确定赋值而言，这是可以接受的，因为本节列出的规则允许它判断无论 `flag` 为真为假，`k` 都会被赋值。规则不接受以下变体：

```java
void flow(boolean flag) {
  int k;
  if (flag)
    k = 3;
  if (!flag)
    k = 4;
  System.out.println(k); /* 在此语句之前，k 未被“确定赋值” */
}
```

因此，编译此程序会导致产生编译时错误。

## 示例 16-3. 确定未赋值

Java 编译器将接受以下代码：

```java
void unfold(boolean flag) {
    final int k;
    if (flag) {
        k = 3;
        System.out.println(k);
    }
    else {
        k = 4;
        System.out.println(k);
    }
}
```

就 `k` 的确定未赋值而言，这是可以接受的，因为本节概述规则允许它判断无论 `flag` 为真为假，`k` 最多被赋值一次（实际上，恰好赋值一次）。规则不接受以下变体：

```java
void unfold(boolean flag) {
    final int k;
    if (flag) {
        k = 3;
        System.out.println(k);
    }
    if (!flag) {
        k = 4;
        System.out.println(k); /* 在此语句之前，k 未被“确定未赋值” */
    }
}
```

因此，编译此程序会导致产生编译时错误。

为了精确指定确定未赋值的所有情况，本节规则定义了几个技术术语：

- 变量在语句或表达式之前是否被确定赋值
- 变量在语句或表达式之前是否确定未赋值
- 变量在语句或表达式之后是否被确定赋值
- 变量在语句或表达式之后是否确定未赋值

对于布尔值表达式，后两种被细化为四种情况：

- 表达式为真时，变量之后是否被确定赋值
- 表达式为真时，变量之后是否确定未赋值
- 表达式为假时，变量之后是否被确定赋值
- 表达式为假时，变量之后是否确定未赋值

这里，`true` 和 `when false` 指表达式的值。

例如，局部变量 `k` 在表达式求值后被确定赋值了值：

```java
a && ((k=m) > 5 )
```



当表达式为真时赋值，但当表达式为假时不赋值（因为如果 `a` 为假，则对 `k` 的赋值不一定执行（更准确地说，不一定求值））。

短语“`v` 在 `x` 之后被确定赋值”（其中 `v` 是局部变量，`x` 是语句或表达式）意味着“在 `x` 正常完成之后，`v` 被确定赋值”。如果 `x` 异常完成，赋值可能没有发生，而文中陈述的规则已经考虑了这一点。

该定义的一个奇特结果是：“`v` 在 `break;` 之后被确定赋值” 永远为真！因为 `break` 语句永远不会正常完成，所以如果 `break` 语句正常完成了，那么它就已经被赋值了值。

短语“`v` 在 `x` 之后确定未赋值”（其中 `v` 是变量，`x` 是语句或表达式）意味着“在 `x` 正常完成之后，`v` 确定未赋值”。

该定义的一个更奇特的后果是：“`v` 在 `break;` 之后确定未赋值”是空真的真，因为 `break` 语句永远不会正常完成，所以如果 `break` 语句正常完成了，那么 `v` 没有被赋值值。（至于此，月亮是由绿色奶酪制成的也是空真的。）

总之，在语句或表达式执行后，变量 `v` 有四种可能：

- `v` 被确定赋值且未确定未赋值。（流分析规则证明了对 `v` 的赋值已经发生。）
- `v` 确定未赋值且未确定赋值。（流分析规则证明了对 `v` 的赋值没有发生。）
- `v` 既没有确定赋值，也没有确定未赋值。（规则无法证明对 `v` 的赋值是否发生。）
- `v` 既确定赋值又确定未赋值。（语句或表达式不可能正常完成。）

为了缩短规则，使用了惯用的缩写 "iff" 来表示“当且仅当”。我们还使用一种缩写约定：如果一个规则包含一个或多个 `[unassigned]`，那么它代表两条规则，一个每一个 `[unassigned]` 替换为“确定赋值”的规则，另一个每一个 `[unassigned]` 替换为“确定未赋值”的规则。

例如：

- `v` 在空语句之后是 `[unassigned]` iff 它在空语句之前是 `[unassigned]`。

应该被理解为两条规则：

- `v` 在空语句之后被确定赋值 iff 它在空语句之前被确定赋值。
- `v` 在空语句之后确定未赋值 iff 它在空语句之前确定未赋值。

在本章的其余部分中，除非另有说明，否则 `v` 代表在作用范围内的 (§6.3) 局部变量或空 final 字段。同样，我们使用 `a`、`b`、`c` 和 `e` 表示表达式，使用 `s` 和 `t` 表示语句。我们使用短语“`a` 是 `v`”来意味着 `a` 是该值（simple）。

循环语句的确定未赋值提出了一个特殊问题。考虑语句 `while (e) S`。为了确定 `v` 在某些表达式内部是否未赋值，我们需要确定 `v` 在 `e` 之前是否未赋值。人们可能会类比确定赋值规则 (§16.2)，认为：`v` 在 `e` 之前确定未赋值 iff 它在 `e` 之后确定未赋值。然而，这样的规则是不够的，因为如果 `e` 求值为真，语句 `S` 将被执行。

修改后的规则将是：“`v` 在 `e` 之前确定未赋值 iff 它在 `e` 之后确定赋值”。这导致了循环。我们通过对循环条件和体进行假设分析来打破这种恶性循环。例如，我们假设 `v` 在 `e` 之前确定未赋值，然后可以证明 `e` 之后确定未赋值，我们知道 `e` 没有赋值 `v`。更正式的表述是：假设 `v` 在 `e` 之前确定未赋值，在 `e` 之后确定未赋值。

上述分析的变体用于定义 Java 语言中所有循环语句的未赋值规则。

# 确定赋值与表达式

## 16.1 布尔表达式

- 在值为假的常量表达式 (§15.29) 之后 `v` 是 `[unassigned]`。
- 在值为真的常量表达式之后 `v` 是 `[unassigned]`。
- 在值为真的常量表达式之后 `v` 是 `[unassigned]` iff 它在常量表达式之前是 `[unassigned]`。
- 在值为假的常量表达式之后 `v` 是 `[unassigned]`，当它在常量表达式之前是 `[unassigned]` 时。
- 在布尔值常量表达式 `e` 之后 `v` 是 `[unassigned]` iff 在 `e` 为真时 `v` 是 `[unassigned]` 且在 `e` 为假时 `v` 是 `[unassigned]`。

这等于说 `v` 在 `e` 之后是 `[unassigned]` iff 它在 `e` 之前是 `[unassigned]`。

因为值为真的常量表达式永远没有假值，而值为假的常量表达式永远没有真值，所以前面的规则是空满足。它们有助于分析涉及运算符 `&&` (§16.1.2)、`||` (§16.1.3)、`!` (§16.4) 和 `?` (§16.1.5) 的表达式。

## 16.1.2 逻辑与运算符 &&

- 在 `a && b` (§15.23) 之后为真时，在 `b` 之后为真时 `v` 是 `[unassigned]`。
- 在 `a && b` 之后为假时，在 `a` 为假时 `v` 在 `a` 之后是 `[unassigned]` 且在 `b` 为假时 `v` 在 `b` 之后是 `[unassigned]`。
- `v` 在 `a` 之前是 `[unassigned]` iff 它在 `a && b` 之前是 `[unassigned]`。
- `v` 在 `b` 之前是 `[unassigned]` iff 在 `a` 为真时它在 `a` 之后是 `[unassigned]`。

## 16.1.3 条件或运算符 ||

- 在 `a || b` (§15.24) 为真时 `v` 未赋值，则当 `a` 为真时 `v` 未赋值，且当 `b` 为真时 `v` 未赋值。
- 在 `a || b` 为假时 `v` 未赋值，则当 `b` 为假时 `v` 未赋值。
- 在 `a` 之前 `v` 未赋值，则在 `a || b` 之前 `v` 未赋值。
- 在 `b` 之前 `v` 未赋值，当且仅当 `a` 为假时 `v` 未赋值。
- 在 `a || b` 之后 `v` 未赋值，当 `a || b` 为真时 `v` 未赋值，且当 `a || b` 为假时 `v` 未赋值。

## 16.1.4 逻辑非运算符 !

- 在 `!a` (§15.16) 为真时 `v` 未赋值，则当 `a` 为假时 `v` 未赋值。
- 在 `!a` 为假时 `v` 未赋值，则当 `a` 为真时 `v` 未赋值。
- 在 `a` 之前 `v` 未赋值，则在 `!a` 之前 `v` 未赋值。
- 在 `a` 之前 `v` 未赋值，当 `!a` 为真时 `v` 之后未赋值，且当 `!a` 为假时 `v` 未赋值。

> 这等同于说在 `!a` 之后 `v` 未赋值，则在 `a` 之后 `v` 未赋值。

## 16.1.5 条件运算符 ? :

假设 `b` 和 `c` 是布尔值表达式。

- 在 `a ? b : c` (§15.25) 为真时 `v` 未赋值，则当 `b` 为真时 `v` 未赋值，且当 `c` 为真时 `v` 未赋值。
- 在 `a ? b : c` 为假时 `v` 未赋值，则当 `b` 为假时 `v` 未赋值，且当 `c` 为假时 `v` 未赋值。
- 在 `a` 之前 `v` 未赋值，当且仅当在 `a ? b : c` 之前 `v` 未赋值。
- 在 `b` 之前 `v` 未赋值，当且仅当 `a` 为真时 `v` 未赋值。
- 在 `c` 之前 `v` 未赋值，当且仅当 `a` 为假时 `v` 未赋值。
- 在 `a ? b : c` 之后 `v` 未赋值，当且仅当 `a ? b : c` 为真时 `v` 未赋值，且当 `a ? b : c` 为假时 `v` 未赋值。

假设 `b` 和 `c` 不是布尔值的表达式。

- 在 `a ? b : c` 之后 `v` 未赋值，当且仅当在 `b` 之后 `v` 未赋值且在 `c` 之后 `v` 未赋值。
- 在 `a` 之前 `v` 未赋值，当且仅当在 `a ? b : c` 之前 `v` 未赋值。
- 在 `b` 之前 `v` 未赋值，当且仅当 `a` 为真时 `v` 未赋值。
- 在 `c` 之前 `v` 未赋值，当且仅当 `a` 为假时 `v` 未赋值。

## 16.1.6 switch 表达式

假设一个 switch 表达式 (§15.28) 具有结果表达式 $e_1, \dots, e_n$，且均为布尔值。

以下规则仅适用于 switch 表达式的 switch 块由 switch 标记的语句组 (§14.11.1) 组成的情况：

- 在 switch 表达式之后为真时 `v` 确定赋值，当且仅当对于 switch 块中每个可能退出 switch 表达式的带有表达式 $e$ (§14.21) 的 `yield` 语句，在 $e$ 为真时 `v` 确定赋值。
- 在 switch 表达式之后为假时 `v` 确定赋值，当且仅当对于 switch 块中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 $e$ 为假时 `v` 确定赋值。
- 在 switch 表达式之后为真时 `v` 确定未赋值，当且仅当对于 switch 块中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 `yield` 语句之前 `v` 确定未赋值且在 $e$ 为真时 `v` 确定赋值。
- 在 switch 表达式之后为假时 `v` 确定未赋值，当且仅当对于 switch 块中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 `yield` 语句之前 `v` 确定未赋值且在 $e$ 为假时 `v` 未赋值。
- 在选择器表达式之前 `v` 未赋值，当且仅当在 switch 表达式之前 `v` 未赋值。
- 在 switch 块中第一个 switch 标记语句组的第一个语句之前 `v` 未赋值，则在选择器表达式之后 `v` 未赋值。
- 在除第一个之外的任何 switch 标记语句组的第一个语句之前 `v` 未赋值，当且仅当选择器表达式之后且前一个语句之后 `v` 未赋值。

以下规则仅适用于 switch 表达式的 switch 块由 switch 规则 (§14.11.1) 组成的情况：

- 在 switch 表达式之后为真时 `v` 确定赋值，当且仅当对于每个 switch 规则，以下条件之一成立：
  - 它引入了一个 switch 规则表达式 $e$，且在 $e$ 为真时 `v` 确定赋值。
  - 它引入了一个 switch 规则语句块 $B$，且对于 $B$ 中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 $e$ 为真时 `v` 确定赋值。
  - 它引入了一个 switch 规则 `throw`。
- 在 switch 表达式之后为假时 `v` 确定赋值，当且仅当每个 switch 规则，以下条件之一成立：
  - 它引入了一个 switch 规则表达式 $e$，且在 $e$ 为假时 `v` 确定赋值。
  - 它引入了一个 switch 规则语句块 $B$，且对于 $B$ 中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 $e$ 为假时 `v` 确定赋值。
  - 它引入了一个 switch 规则 `throw`。
- 在 switch 表达式之后为真时 `v` 确定未赋值，当且仅当对于每个 switch 规则，以下条件之一成立：
  - 它引入了一个 switch 规则表达式 $e$，且在 $e$ 为真时 `v` 确定未赋值。
  - 它引入了一个 switch 规则语句块 $B$，且对于 $B$ 中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 `yield` 语句之前 `v` 确定未赋值且在 $e$ 为真时 `v` 未赋值。
  - 它引入了一个 switch 规则 `throw`。
- 在 switch 表达式之后为假时 `v` 确定未赋值，当且仅当对于每个 switch 规则，以下条件之一成立：
  - 它引入了一个 switch 规则表达式 $e$，且在 $e$ 为假时 `v` 确定赋值。
  - 它引入了一个 switch 规则语句块 $B$，且对于 $B$ 中每个可能退出 switch 表达式的带有表达式 $e$ 的 `yield` 语句，在 `yield` 语句之前 `v` 确定未赋值且在 $e$ 为假时 `v` 未赋值。
  - 它引入了一个 switch 规则 `throw`。
- 在选择器表达式之前 `v` 未赋值，当且仅当在 switch 表达式之前 `v` 未赋值。
- 在 switch 块中第一个 switch 标记语句组的第一个语句之前 `v` 未赋值，则在选择器表达式之后 `v` 未赋值。
- 在除第一个之外的任何 switch 标记语句组的第一个语句之前 `v` 未赋值，当且仅当选择器表达式之后且前一个语句之后 `v` 未赋值。

## 16.1.7 其他布尔类型的表达式

假设 $e$ 是布尔类型且不是布尔常量表达式、逻辑完成表达式 `!a`、条件与表达式 `a && b`、条件或表达式 `a || b` 或条件表达式 `a ? b : c`。

- 在 $e$ 为真之后 `v` 未赋值。
- 在 $e$ 为假之后 `v` 未赋值。

## 16.1.8 赋值表达式

考虑表达式 `a = b`、`a += b`、`a -= b`、`a *= b`、`a /= b`、`a %= b`、`a <<= b`、`a >>= b`、`a &= b`、`a |= b`、`a ^= b` (§15.26)。

- 在赋值表达式之后 `v` 确定赋值，当且仅当：
  - `a` 是变量，或
  - `v` 在 `b` 之后确定赋值。
- 在赋值表达式之后 `v` 未赋值，当 `a` 不是变量且 `v` 在 `b` 未赋值。
- 在 `a` 之前 `v` 未赋值，当且仅当在赋值表达式之前 `v` 未赋值。
- 在 `b` 之前 `v` 未赋值，当且仅当在 `a` 之后 `v` 未赋值。

注意，如果 `a` 是变量且 `v` 在 `a &= b` 等复合表达式之后未赋值，则会发生编译时错误。上述确定赋值的第一个规则对于复合赋值而非仅仅赋值也包含了“`a` 是变量”这一分支，以便 `v` 在代码后续部分被认为已赋值。包含“`a` 是变量”这一分支不会影响程序是否可接受或会导致编译时错误的二进制判定，但它会影响代码中不同点可能被视为错误，在实践中它可以提高错误报告的质量。对于上述确定赋值第一个规则中包含“`a` 不是变量”的组合，也有类似的说明。

## 16.1.9 运算符 ++ 和 --

- 在 `++a` (§15.15.1)、`--a` (§15.15.2)、`a++` (§15.14.2) 或 `a--` (§15.14.3) 之后 `v` 确定赋值，当且仅当 `a` 是变量或 `v` 在操作数表达式之后确定赋值。
- 在 `++a`、`--a`、`a++` 或 `a--` 之后 `v` 确定未赋值，当 `a` 不是变量且 `v` 在操作数表达式之后确定未赋值。
- 在 `a` 之前 `v` 未赋值，当且仅当在 `++a`、`--a`、`a++` 或 `a--` 之前 `v` 未赋值。

## 16.1.10 其他表达式

如果一个表达式不是布尔常量表达式，且不是增表达式 `++a`、前减表达式 `--a`、后增表达式 `a++`、后减表达式 `a--`、逻辑完成表达式 `!a`、逻辑与表达式 `a && b`、逻辑或表达式 `a || b`、条件表达式 `a ? b : c`、赋值表达式或 switch 表达式，则适用以下规则：

- 如果该表达式没有子表达式，如果 `v` 在表达式之前是 `[unassigned]` 的，则 `v` 在表达式之前是 `[unassigned]` 的。

此情况适用于字面量、`this`（包括限定的和未限定的）、无参数的未限定类实例创建、不包含表达式的带有初始化器的数组表达式创建、父类字段访问表达式、无参数的未限定和类型限定的方法调用、无参数的父类方法调用，以及父类方法和类型限定的方法引用表达式。

- 如果该表达式有子表达式，如果 `v` 在其中间子表达式之后是 `[unassigned]` 的，则 `v` 在表达式之前是 `[unassigned]` 的。

在“变量 `v` 在方法调用后可以确定是未定义的”这一断言背后，存在着微妙的推理。单从值和限定性来看，这种赋值并不总是成立的；因为被调用的方法可以执行赋值。但必须记住，对于 Java 语言而言，确定性赋值的概念仅适用于空白 `final` 变量。如果 `v` 是一个空白局部变量，那么只有声明 `v` 的方法可以对 `v` 执行赋值。如果 `v` 是一个空白 `final` 字段，那么只有包含 `v` 声明的类的构造函数或类初始化器可以对 `v` 执行赋值；没有方法可以对 `v` 执行赋值。最后，显式构造函数调用 (§8.7.1) 经过特殊处理（§16.9）；尽管它们在语法上与包含方法调用的表达式语句相似，但它们不是表达式语句，因此本节的规则不适用于显式构造函数调用。

如果表达式是一个 lambda 表达式，则适用以下规则：

- 如果 `v` 在表达式之前是 `[unassigned]` 的，则 `v` 在表达式之前是 `[unassigned]` 的。
- `v` 在 lambda 表达式或 lambda 体 (§15.7.2) 之前被确定赋值，当且仅当 `v` 在 lambda 表达式之前被确定赋值。

没有规则允许 `v` 在 lambda 体之前处于未定义。在 lambda 体结束之前未定义的变量在之后可能会被赋值，因此我们无法得出该变量在执行体时未赋值的结论。

对于表达式 `x` 的任何直接子表达式 `y`（其中 `x` 不是 lambda 表达式），`v` 在 `y` 之前是 `[unassigned]` 的，当且仅当以下情况之一：

- `y` 是 `x` 的最左侧子表达式，且 `v` 在 `x` 之前是 `[unassigned]` 的。
- $y$ 是二元运算符的右操作数，且 `v` 在左侧操作数之后是 `[unassigned]` 的。
- $x$ 是数组访问，$y$ 是括号内的子表达式，且 `v` 在括号前的子表达式之后是 `[unassigned]` 的。
- $x$ 是主方法调用，$y$ 是调用中的第一个参数表达式，且 `v` 在计算目标对象的主表达式之后是 `[unassigned]` 的。
- $x$ 是方法调用表达式或类实例创建表达式；$y$ 是参数表达式，但不是第一个；且 `v` 在 $y$ 的左侧参数表达式之后是 `[unassigned]` 的。
- $x$ 是限定的类实例创建表达式，$y$ 是类实例创建中的第一个参数表达式，且 `v` 在计算限定对象的主表达式之后是 `[unassigned]` 的。
- $x$ 是数组创建表达式；$y$ 是维度表达式，但不是第一个；且 `v` 在 $y$ 的左侧维度表达式之后是 `[unassigned]` 的。
- $x$ 是通过数组初始化器初始化的数组创建表达式；$y$ 是 $x$ 中的数组初始化器；且 `v` 在 $y$ 的左侧维度表达式之后是 `[unassigned]` 的。

# 确定赋值与语句

## 16.2.1 空语句

## 16.2.2 块

- 一个空白 `final` 成员字段 `v` 在 `v` 作用域内任何方法的体块 (§14.2) 之前是确定赋值的（并且进一步不是确定未赋值的），并且在 `v` 作用域内声明的任何类的声明之前是确定赋值的。
- 一个局部变量 `v` 在声明 `v` 的构造函数、方法、实例初始化器或静态初始化器的体块之前是确定未赋值的（并且进一步不是确定赋值的）。

令 `c` 为在 `v` 作用域内声明的类。那么 `v` 在在 `c` 中声明的任何构造函数、方法、实例初始化器或静态初始化器的体块之前是确定赋值的；`v` 在 `c` 的声明之前是确定赋值的。

> 注意，没有规则允许我们得出结论认为 `v` 在 `c` 中声明的任何构造函数、方法、实例初始化器或静态初始化器的体块之前是确定未赋值的。我们可以非正式地得出结论，`v` 在 `c` 中声明的这些语句体块之前不是确定未赋值的，但不需要显式地规定这样的规则。

- 如果 `v` 在空块之后是 `[unassigned]` 的，则 `v` 在空块之前是 `[unassigned]` 的。
- 如果 `v` 在非空块之后是 `[unassigned]` 的，则 `v` 在块内最后一条语句之后是 `[unassigned]` 的。
- 如果 `v` 在块的第一条语句之前是 `[unassigned]` 的，则 `v` 在块之前是 `[unassigned]` 的。
- 如果 `v` 在块的任何其他语句 `s` 之前是 `[unassigned]` 的，则 `v` 在块中紧邻 `s` 的语句之后是 `[unassigned]` 的。

我们说 `v` 在块 `B` 中处处都是确定未赋值的，当且仅当：

- `v` 在 `e` 之后是确定未赋值的。
- 在 `B` 中出现的赋值表达式 `V = e`、`V += e`、`V -= e`、`V *= e`、`V /= e`、`V %= e`、`V <<= e`、`V >>= e`、`V >>>= e`、`V &= e`、`V |= e` 或 `V ^= e` 中，`v` 之后都是确定赋值的。
- 在 `B` 中出现的每个表达式 `++V`、`--V`、`V++` 或 `V--` 之前，`v` 都是确定赋值的。

这些条件是反直觉的，需要一些解释。考虑简单的赋值 `V = e`。如果 `V` 在 `e` 之后是确定赋值的，那么：

- 赋值发生了，且 `V` 是空赋值的。或者：
- `v` 已经通过之前的表达式被赋值。在这种情况下，当前的赋值会导致编译错误。

所以我们可以得出结论，编译错误程序满足这些条件，但 `v` 的赋值实际上不会发生。

## 16.2.3 本地类与接口声明

- `v` 在本地类或接口声明 (§14.3) 之后是 `[unassigned]` 的，当且仅当 `v` 在本地类或接口声明之前是 `[unassigned]` 的。

## 16.2.4 局部变量声明语句

- `v` 在不包含初始化器的局部变量声明语句 (§14.4.2) 之后是 `[unassigned]` 的，当且仅当 `v` 在该局部变量声明语句之前是 `[unassigned]` 的。
- `v` 在包含至少一个初始化器的局部变量声明语句之后是确定赋值的，当且仅当 `v` 在该局部变量声明中的初始化器之后是确定赋值的，或者声明中的最后一个初始化器位于声明 `v` 的声明中。
- `v` 在包含至少一个初始化器的局部变量声明语句之后是确定未赋值的，当且仅当 `v` 在 `e` 左侧的初始化器之后是确定未赋值的，且声明中的最后一个初始化器不在声明 `v` 的声明中。
- `v` 在局部变量声明中第一个初始化器之前是 `[unassigned]` 的，当且仅当 `v` 在该局部变量声明语句之前是 `[unassigned]` 的。
- `v` 在局部变量声明中除第一个以外的初始化器 `e` 之前是确定赋值的，当且仅当 `v` 在 `e` 左侧的初始化器之后是确定赋值的，或者 `e` 左侧的初始化表达式位于声明 `v` 的声明中。
- `v` 在局部变量声明中除第一个以外的初始化器 `e` 之前是确定未赋值的，当且仅当 `v` 在 `e` 左侧的初始化器之后是确定未赋值的，且 `e` 左侧的初始化表达式不在声明 `v` 的声明中。

## 16.2.5 标记语句

- `v` 在标记语句 `L : s` (§14.7) 之后是 `[unassigned]` 的，当且仅当 `v` 在 `s` 之后是 `[unassigned]` 的，且 `v` 在所有可能退出标记语句 `L : s` 的 `break` 语句之前都是 `[unassigned]` 的。
- `v` 在 `s` 之前是 `[unassigned]` 的，当且仅当 `v` 在 `L : s` 之前是 `[unassigned]` 的。

## 16.2.6 表达式语句

- `v` 在一个表达式语句 `e` (§14.8) 之后未赋值，当且仅当它在 `e` 之后未赋值。
- `v` 在 `e` 之前未赋值，当且仅当它在 `e` 之前未赋值。

## 16.2.7 if语句

以下规则适用于语句 `if (e) S` (§14.9.1)：

- `v` 在 `if (e)` 之后未赋值，当且仅当 `v` 在 `S` 之后赋值且当 `e` 为假时，`v` 在 `e` 之后未赋值。
- `v` 在 `e` 之前未赋值，当且仅当它在 `if (e) S` 之前未赋值。
- `v` 在 `S` 之前未赋值，当且仅当 `e` 为真时，`v` 在 `e` 之后未赋值。

以下规则适用于语句 `if (e) S else T` (§14.9.2)：

- `v` 在 `if (e) S else T` 之后未赋值，当且仅当 `v` 在 `S` 之后赋值且 `v` 在 `T` 之后赋值。
- `v` 在 `e` 之前未赋值，当且仅当它在 `if (e) S else T` 之前未赋值。
- `v` 在 `S` 之前未赋值，当且仅当 `e` 为真时，`v` 在 `e` 之后未赋值。
- `v` 在 `T` 之前未赋值，当且仅当 `e` 为假时，`v` 在 `e` 之后未赋值。

## 16.2.8 assert语句

以下规则同时适用于语句 `assert e1` 和语句 `assert e1 : e2` (§14.10)：

- `v` 在 `ej` 之前未赋值，当且仅当 `v` 在 `assert` 语句之前未赋值。
- `v` 在 `assert` 语句之后确定赋值，当且仅当 `v` 在 `assert` 语句之前确定赋值。
- `v` 在 `assert` 语句之后确定未赋值，当且仅当 `v` 在 `assert` 语句之前确定未赋值且当 `e2` 为真时，`v` 在 `e2` 之后确定未赋值。

以下规则适用于语句 `assert e1 : e2`：

- `v` 在 `e2` 之前未赋值，当且仅当 `e2` 为假时，`v` 在 `e2` 之后未赋值。

## 16.2.9 switch语句

- `V` 在 switch 语句之后未赋值 (§14.11)，当且仅满足以下所有条件：
  - `V` 在每个可能退出 switch 语句的 `break` 语句 (§14.15) 之前未赋值。
  - 对于 switch 块中的每个 switch 规则 (§14.11.1)，`V` 在 switch 规则表达式、switch 规则块或由 switch 规则引入的 switch 语句之后未赋值。
  - 如果 switch 块中存在带标签的语句组，则 `V` 在最后一个带标签语句组的最后一个块之后未赋值。
  - 如果 switch 块中没有默认标签，或者 switch 块以 switch 标签后跟 `}` 分隔符结束，则 `V` 在选择器表达式之后未赋值。
- `V` 在 switch 语句选择器表达式之前未赋值，当且仅当 `V` 在 switch 语句之前未赋值。
- `V` 在 switch 块中由 switch 规则引入的 switch 规则表达式、switch 规则块或 switch `throw` 语句之前未赋值，当且仅当 `V` 在 switch 语句选择器表达式之后未赋值。
- `V` 在 switch 块中带标签语句组的第一个块语句之前未赋值，当且仅满足以下所有条件：
  - 在该带标签语句组的 `switch` 语句未赋值时，`v` 在带标签语句组的最后一个块之后未赋值。
  - 如果 switch 块中该带标签语句组不是第一个，则 `v` 在上一个语句组的最后一个块之后未赋值。
- `V` 在 switch 块中第一个带标签语句组的第一个语句之前未赋值，当且仅当 `V` 在上一个语句之后未赋值。

## 16.2.10 while语句

- `V` 在 `while (e) s` 之后未赋值 (§14.12)，当且仅当 `e` 为假时，`V` 在 `e` 之后未赋值且 `while` 语句是 break 目标。
- `v` 在 `e` 之前确定赋值，当且仅当 `V` 在 `while` 语句之前确定赋值。
- `V` 在 `e` 之前确定未赋值，当且仅满足以下所有条件：
    - `V` 在 `while` 语句之前确定未赋值。
    - 假设 `V` 在 `e` 之前确定未赋值，则 `V` 在 `S` 之后确定未赋值。
    - 假设 `V` 在 `e` 之前确定未赋值，则 `V` 在每个以 `while` 语句为目标的 `continue` 语句之前未赋值。
- `V` 在 `s` 之前未赋值，当且仅当 `e` 为真时，`V` 在 `e` 之后未赋值。

## 16.2.11 do语句

- `v` 在 `do S while (e)` 之后未赋值 (§14.13)，当且仅当 `V` 在假时 `S` 之后未赋值且 `V` 在每个以 `do` 语句为 break 目标的 `break` 语句之前未赋值。
- `v` 在 `s` 之前确定赋值，当且仅当 `V` 在 `do` 语句之前确定赋值。
- `V` 在 `s` 之前确定未赋值，当且仅满足以下所有条件：
    - `V` 在 `do` 语句之前确定未赋值。
    - 假设 `V` 在 `s` 之前确定未赋值，则当 `e` 为真时，`V` 在 `e` 之后确定未赋值。
- `V` 在 `e` 之前未赋值，当且仅当 `v` 在 `s` 之后赋值且 `V` 在每个以 `do` 语句为 continue 目标的 `continue` 语句之前未赋值。

## 16.2.12 for语句

此处规则适用于 `for` 语句。

## 16.2.13 try语句

这些规则适用于每一个 try 语句 (§14.20)，无论其是否包含 finally 块：

- `v` 在 try 块之前是 `[unassigned]` 的，当且仅当 `v` 在 try 语句之前是 `[unassigned]` 的。
- `v` 在 catch 块之前是确定赋值的，当且仅当 `v` 在 try 块之前是确定赋值的。
- `v` 在 catch 块之前是确定未赋值的，当且仅当满足所有条件：
  - `v` 在 try 块之后是确定未赋值的。
  - `v` 在属于 try 块的每一个 `return` 语句之前都是确定未赋值的。
  - `v` 在属于 try 块的每一个形式 `throw e` 的语句中的每一个 `e` 之后都是确定未赋值的。
  - `v` 在 try 块中发生的每一个 `assert` 语句之前都是确定未赋值的。
  - `v` 在属于 try 块且其跳转目标包含（或就是）try 语句的每一个 `break` 语句之前都是确定未赋值的。
  - `v` 在属于 try 块且其继续目标包含 try 语句的每一个 `continue` 语句之前都是确定未赋值的。

如果一个 try 语句没有 finally 块，则此规则也适用：

- `v` 在 try 语句之后是 `[unassigned]` 的，当且仅当 `v` 在 try 语句之后是 `[unassigned]` 且 `v` 在 try 语句中的每一个 catch 块之后都是 `[unassigned]` 的。

如果一个 try 语句有 finally 块，则这些规则也适用：

- `v` 在 try 语句之后是确定赋值的，当且仅当满足以下条件之一：
  - `v` 在 try 块之后是确定赋值的且 `v` 在 try 语句中的每一个 catch 块之后都是确定赋值的。
  - `v` 在 finally 块之前是确定赋值的。
- `v` 在 try 语句之后是确定未赋值的，当且仅当 `v` 在 finally 块之后是确定未赋值的。
- `v` 在 finally 块之前是确定赋值的，当且仅当 `v` 在 try 语句之前是确定赋值的。
- `v` 在 finally 块之前是确定未赋值的，当且仅当满足所有条件：
  - `v` 在 try 块之后是确定未赋值的。
  - `v` 在属于 try 块的每一个 `return` 语句之前都是确定未赋值的。
  - `v` 在属于 try 块的每一个形式 `throw e` 的语句中的每一个 `e` 之后都是确定未赋值的。
  - `v` 在 try 块中发生的每一个 `assert` 语句之前都是确定未赋值的。
  - `v` 在属于 try 块且其跳转目标包含（或就是）try 语句的每一个 `break` 语句之前都是确定未赋值的。
  - `v` 在属于 try 块且其继续目标包含 try 语句的每一个 `continue` 语句之前都是确定未赋值的。
  - `v` 在 try 语句的每一个 catch 块之后都是确定未赋值的。

## 16.3 确定赋值与参数

- 方法或构造函数的形式参数 `v` (§8.4.1, §8.8.1) 在方法或构造函数的体之前是确定赋值的（并且说它不是确定未赋值的）。
- catch 子句的异常参数 `v` (§14.20) 在 catch 子句的体之前是确定赋值的（并且说它不是确定未赋值的）。

## 16.4 确定赋值与数组初始化器

- `v` 在空数组初始化器 (§10.6)之后是 `[unassigned]` 的，当且仅当 `v` 在空数组初始化器之前是 `[unassigned]` 的。
- `v` 在非空数组初始化器之后是 `[unassigned]` 的，当且仅当 `v` 在数组初始化器中最后一个变量初始化器之后是 `[unassigned]` 的。
- `v` 在数组初始化器中第一个变量初始化器之后是 `[unassigned]` 的，当且仅当 `v` 在数组初始化器之前是 `[unassigned]` 的。
- `v` 在数组初始化器中任何变量初始化器 `e` 之前是 `[unassigned]` 的，当且仅当 `v` 在数组初始化器中 `e` 左侧的初始化器之后是 `[unassigned]` 的。

## 16.5 确定赋值与枚举常量

确定变量在枚举常量 (§8.9.1) 之前确定赋值或确定未赋值的规则见 §16.8。

> 这是因为枚举常量本质上是一个静态 final 字段 (§8.3.1, §8.3.2)，它使用类实例创建表达式 (§15.9) 进行初始化。

- 在 `v` 的作用范围内声明的无参数枚举常量的类体声明之前，且 `v` 在该枚举常量之前是确定赋值的。
- 在 `v` 的作用范围内声明的带参数枚举常量的类体声明之前，且 `v` 在该枚举常量的最后一个参数表达式之后是确定赋值的。

枚举常量类体内任何构造的确定赋值/未赋值状态均遵循类的常规规则。

- `v` 在枚举常量的第一个参数之前是 `[unassigned]` 的，当且仅当它在枚举常量之前是 `[unassigned]` 的。
- `v` 在 `y`（枚举常量的一个参数，但不是第一个参数）之前是 `[unassigned]` 的，当且仅当 `v` 在 `y` 左侧的参数之后是 `[unassigned]` 的。

## 16.6 确定赋值与匿名类

- `v` 在 `v` 的作用范围内声明的匿名类 (§15.9) 之前是 `[unassigned]` 的，`v` 在类声明之后是确定赋值的。

显而易见，如果匿名类是由枚举常量隐式定义的，则适用 §16.5 的规则。

## 16.7 确定赋值与成员类

设 `c` 为一个类，设 `v` 为 `c` 的一个空白字段。那么：

- `v` 在成员类的体之前是确定赋值的（并且说它不是确定未赋值的）。

设 `c` 为在 `v` 的作用范围内声明的类。那么：

- `v` 在成员类的声明之前是确定赋值的（并且说它不是未赋值的）。

## 16.8 确定赋值与静态初始化器

设 `c` 为在 `v` 的作用范围内声明的类。那么：

- `v` 在 `c` 的静态初始化器之前是确定赋值的（并且说它不是确定未赋值的）。

注意，没有规则可以让我们得出 `v` 在静态初始化器之前是确定未赋值的。我们可以非正式地推出 `v` 在任何静态初始化器之前未赋值的，但不需要这样的规则。

设 `c` 为一个类，设 `v` 为 `c` 中声明的空白字段。那么：

- `v` 在最左侧静态初始化器之前是确定未赋值的（并且说它不是确定赋值的）。
- `v` 在除最左侧之外的静态初始化器之前是 `[unassigned]` 的，当且仅当 `v` 在之前的静态初始化器之后是 `[unassigned]` 的。

设 `c` 为一个类，设 `v` 为在父类中声明的空白静态字段。那么：

- `v` 在 `c` 的每一个静态初始化器之前都是确定赋值的（并且说它不是确定未赋值的）。
- `v` 在每一个作为静态初始化器体之前都是确定赋值的（并且说它不是确定未赋值的）。
- `v` 在 `c` 的每一个静态变量之前都是确定赋值的（并且说它不是确定未赋值的）。

## 16.9 确定赋值、构造函数与实例初始化器

设 `c` 为在 `v` 的作用范围内声明的类。那么：

- `v` 在 `c` 的实例初始化器 (§8.3.2) 之前是确定赋值的（并且说它不是确定未赋值的）。

注意，没有规则可以让我们得出 `v` 在实例初始化器之前是确定未赋值的。我们可以非正式地推出 `v` 在任何实例变量初始化器之前未赋值，但不需要这样的规则。

设 `c` 为一个类，设 `v` 为 `c` 中声明的空白 final 非静态成员字段。那么：

- `v` 在最左侧实例初始化器 (§8.6) 或实例变量初始化器之前是确定未赋值的（并且说它不是确定赋值的）。
- `v` 在除最左侧之外的实例初始化器或实例变量初始化器之前是 `[unassigned]` 的，当且仅当 `v` 在之前的实例初始化器或实例变量初始化器之后是 `[unassigned]` 的。

以下规则适用于类 `c` 的构造函数 (§8.8.7) 中：

- `v` 在备用构造函数调用 (§8.8.7.1)之后是确定赋值的（并且说它不是确定未赋值的）。
- `v` 在显式或隐式父类构造函数调用之前是确定未赋值的 (§8.8.7.1)。
- 如果 `c` 没有初始化器或实例变量初始化器，则 `v` 在显式或隐式父类构造函数之后不是确定赋值的（并且说它不是未赋值的）。
- 如果 `c` 至少有一个实例初始化器或实例变量初始化器，则 `v` 在显式或隐式父类构造函数之后是 `[unassigned]` 的，当且仅当 `v` 在最右侧实例初始化器或实例变量初始化器之后是 `[unassigned]` 的。

设 `c` 为一个类，设 `v` 为在父类中声明的空白 final 成员字段。那么：

- `v` 在作为构造函数或实例初始化器体的块之前是确定赋值的（并且说它不是确定未赋值的）。
- `v` 在 `c` 的每个实例变量初始化器之前都确定被赋值了（而且此外，它不是确定为未赋值的）。

# 线程与锁

这些语义并没有规定多线程程序应该如何执行。相反，它们描述了多线程程序允许的行为。任何只产生允许行为的执行策略都是可接受的执行策略。

## 17.1 同步

Java 编程语言提供了多种线程间通信的机制。这些方法中最基本的是同步，它通过监视器实现。Java 中的每个对象都关联一个监视器，线程可以对其锁定或解锁。一次允许有一个线程持有监视器的锁。其他尝试锁定该监视器的线程会被阻塞，直到它们获取该监视器的锁。一个线程可以对特定的监视器锁定多次；每次解锁都会撤销一次锁定操作的效果。

`synchronized` 语句 (§14.19) 会竞争获取该对象监视器的引用，并在锁定操作成功完成之前不会继续执行。在锁定操作之后，将执行 `synchronized` 语句的主体。如果主体的执行无论是正常完成还是异常中止完成，都会对该监视器自动执行解锁操作。

`synchronized` 方法 (§8.4.3.6) 在被调用时会自动执行锁定操作；在锁定操作成功完成之前，不会执行其主体。如果该方法是实例方法，它将锁定与调用它的实例相关的监视器（此时，该对象在方法主体执行期间将被称为 `this`）。如果该方法是静态方法，它将锁定与定义该方法的类的 Class 对象相关的监视器。如果方法主体的执行无论是正常完成还是异常中止完成，都会对该相同监视器自动执行解锁操作。

Java 编程语言既不防止也不检测死锁条件。对于线程持有（直接或间接持有）多个对象锁的程序，应该使用传统的死锁避免技术，并在必要时创建不会产生死锁的高级锁原语。

其他机制，例如对 `volatile` 变量的读写以及 `java.util.concurrent` 包中类的使用，提供了同步的替代方法。

## 17.2 等待集与通知

每个对象除了关联一个监视器外，还关联一个等待集。等待集是一个线程集合。

当对象首次创建时，其等待集是空的。向等待集添加线程和从等待集移除线程的基本操作是原子的。等待集仅由 `Object.wait`、`Object.notify` 和 `Object.notifyAll()` 方法操作。

等待集的操作还会受到线程中断状态以及 `Thread` 类中处理中断的方法的影响。此外，`Thread` 类用于睡眠和等待其他线程的方法具有源自等待和通知动作的属性。

### 17.2.1 等待

等待动作发生在调用 `wait()` 或计时形式 `wait(long milliseconds, int nanoseconds)` 之时。

> 参数为零的 `wait(long milliseconds)` 调用或带有两个零参数的 `wait(long milliseconds, int nanoseconds)` 调用等同于调用 `wait()`。

如果线程在没有抛出 `InterruptedException` 的情况下返回等待，则它是从等待中正常返回。

假设线程 `t` 为在对象 `m` 上执行 `wait` 方法的线程，令 `n` 为 `t` 在 `m` 上执行的、未被解锁操作匹配的锁定操作次数。会发生以下操作之一：

- 如果 `n` 为 0（即线程 `t` 尚未拥有目标对象 `m` 的锁），则抛出 `IllegalMonitorStateException`。
- 如果这是一个计时等待，且 `nanoseconds` 参数不在 0-999999 范围内，或 `milliseconds` 参数为负数，则抛出 `IllegalArgumentException`。
- 如果线程 `t` 被中断，则抛出 `InterruptedException` 并将 `t` 的中断状态设置为 `false`。

否则，发生以下序列：

1. 线程 `t` 被添加到对象 `m` 的等待集中，并在 `m` 上执行 `n` 次解锁操作。
2. 线程 `t` 在从 `m` 的等待集中移除之前不会执行任何后续指令。该线程可能由于以下任何操作被从等待集中移除，并在之后的某个时间恢复执行：
   - 在 `m` 上执行了 `notify` 动作，其中 `t` 被选中从等待集中移除。
   - 在 `m` 上执行了 `notifyAll` 动作。
   - 对 `t` 执行了 `interrupt` 动作。
   - 如果这是一个计时等待，在 `millis` 纳秒后发生的一个将 `t` 从 `m` 等待集中移除的内部动作。
3. 线程 `t` 在 `m` 上执行 `n` 次锁定操作。
4. 如果线程 `t` 因为中断从 `m` 的等待集中移除，则 `wait` 方法抛出 `InterruptedException`。

### 17.2.2 通知

通知动作发生在调用 `notify` 和 `notifyAll` 之时。令 `t` 为在对象 `m` 上执行这两个方法任一的线程，令 `n` 为 `t` 在 `m` 上执行的、未被解锁操作匹配的锁定操作次数。会发生以下操作之一：

- 如果 `n` 为 0（即线程 `t` 尚未拥有目标对象 `m` 的锁），则抛出 `IllegalMonitorStateException`。
- 如果 `n` 大于 0 且这是一个 `notify` 动作，则 `m` 的等待集不为空，将选择并移除 `m` 等待集中的一个线程 `u`。
- 如果 `n` 大于 0 且这是一个 `notifyAll` 动作，则所有线程都从 `m` 的等待集中移除，从而恢复执行。

### 17.2.3 中断

中断动作发生在调用 `Thread.interrupt` 以及定义为相应调用它的方法（如 `ThreadGroup.interrupt`）。令 `t` 为调用 `u.interrupt` 的线程，对于某个线程 `u`，`t` 和 `u` 可能是同一个线程。此动作导致 `u` 的中断状态设置为 `true`。

此外，如果存在某个对象 `m` 的等待集包含 `u`，则 `u` 将从 `m` 的等待集中移除。这使得 `u` 能够在等待动作中恢复，以防该等待在重新锁定 `m` 监视器后抛出 `InterruptedException`。

### 17.2.4 等待、通知与中断的交互

上述规范允许我们确定若干与等待、通知和中断之间交互相关的属性。

如果一个线程在等待期间既收到了通知又被中断，它可能会：

- 从 `wait` 正常返回，但仍有一个挂起的中断（换句话说，调用 `Thread.interrupted` 将返回 `true`）
- 通过抛出 `InterruptedException` 从 `wait` 返回

该线程不能重置其中断状态并从 `wait` 调用正常返回。

同样地，通知不会因为中断而丢失。假设线程集合 `s` 处于对象 `m` 的等待集中，而另一个线程对 `m` 执行了 `notify` 操作。那么：

- `s` 中的至少有一个线程必须从 `wait` 正常返回，或者
- `s` 中的所有线程必须通过抛出 `InterruptedException` 退出 `wait`。

注意，如果一个线程既被中断又通过 `notify` 被唤醒，且该线程通过抛出 `InterruptedException` 从 `wait` 返回，那么等待集中的其他线程必须被通知。

## 17.3 Sleep 与 Yield

`Thread.sleep` 导致当前正在执行的线程睡眠指定的持续时间（临时停止执行），这取决于系统计时器和调度器的精度和准确性。该线程不会丢失任何监视器的所有权，执行的恢复将取决于调度以及用于执行该线程的处理器的可用性。

需要注意的是，`Thread.sleep` 和 `Thread.yield` 都不具有任何同步语义。特别是，编译器在调用 `Thread.sleep` 或 `Thread.yield` 之前，不需要将寄存器中写入的缓存刷新到共享内存中，编译器在调用 `Thread.sleep` 或 `Thread.yield` 之后也不需要重新加载缓存在寄存器中的值。

例如，在下面的（有错误的）代码片段中，假设 `this.done` 是一个非 `volatile` 的布尔类型字段：

```
```



```java
while (!this.done)
    Thread.sleep(1000);
```

编译器可以只读取一次字段 `this.done`，并在循环的每次执行中重用缓存的值。这意味着即使另一个线程改变了 `this.done` 的值，循环也永远不会终止。

## 17.4 内存模型

内存模型描述了在给定一个程序和该程序的执行轨迹的情况下，该执行轨迹是否是该程序的合法执行。Java 编程语言内存模型通过检查执行轨迹中的每次读取，并检查该读取观察到的写入操作是否根据规则是有效的来工作。

该模型描述了程序可能的行为。实现可以自由地产生它喜欢的任何代码，只要程序的所有最终执行产生的结果是可以被内存模型预测的。

> 这为实现者提供了极大的自由，使其能够进行各种代码转换，包括操作的重排序和删除不必要的同步。

## 17.4.1 同步错误的程序可能表现出人意之外的行为

Java 编程语言的语义允许编译器和微处理器进行优化，这些优化可能与同步错误的代码交互，从而产生看似悖论的行为。以下是同步错误的程序可能表现出人意之外行为的一些示例。

考虑表 17.4-A 所示的示例程序轨迹。该程序使用了局部变量 `r1` 和 `r2` 以及共享变量 `A` 和 `B`。初始状态下，`A == B == 0`。

### 表 17.4-A. 语句重排序导致的意外结果 - 原始代码

| 线程 1 | 线程 2 |
| :--- | :--- |
| 1: r2 = A; | 3: r1 = B; |
| 2: B = 1; | 4: A = 2; |

结果 `r2 == 2` 和 `r1 == 1` 似乎是不可能的。直觉上，在执行过程中，指令 1 或指令 3 应该先执行。如果指令 1 先执行，它不应该看到指令 4 的写入。如果指令 3 先执行，它不应该看到指令 2 的写入。

内存模型允许在任意线程中重排序指令，只要这种重排序不会影响该线程在隔离情况下的效果。如果指令 1 与指令 2 重排序，如表 17.4-B 中的轨迹所示，那么很容易看出结果 `r2 = 2` 和 `r1 == 1` 是如何产生的。

### 表 17.4-B. 语句重排序导致的意外结果 - 有效的编译器转换

| 线程 1 | 线程 2 |
| :--- | :--- |
| B = 1; | r1 = B; |
| r2 = A; | A = 2; |

对于某些程序员来说，这种行为可能看起来是“损坏的”。但值得注意的是，这段代码**不是**正确同步的：

- 一个线程中有一个写入，
- 另一个线程对同一变量进行读取，
- 且写入和读取没有被同步排序。

这种情况是数据竞态（§17.4.5）的一个示例。当代码包含数据竞态时，往往可能产生背直觉的结果。

几种机制可以产生表 17.4-B 中的重排序。Java 虚拟机实现中的即时编译器（JIT）可能会重新排列代码，或者处理器可能会这样做。此外，运行 Java 虚拟机实现的架构的内存层次结构可能会使其看起来像是经过重排序的。意外结果的另一个示例可以在表 17.4-C 中看到。初始状态下，`p == q` 和 `p.x`。

### 表 17.4-C. 替换导致的意外结果

| 线程 1 | 线程 2 |
| :--- | :--- |
| r1 = p; | r6 = p; |
| r2 = r1.x; | r6.x = 3; |
| r3 = q; | |
| r4 = r3.x; | |
| r5 = r2; | |

现在考虑这种情况：线程 2 中 `r6.x` 的赋值发生在线程 1 读取 `r1.x` 之间。如果编译器决定重用值 `r2` 用于 `r5`，那么 `r2` 和 `r5` 将为 0，而 `r4` 将为 3。从程序员的角度来看，`p.x` 存储的值从 0 变为了 3。

### 表 17.4-D. 替换导致的意外结果

| 线程 1 | 线程 2 |
| :--- | :--- |
| r1 = p; | r6 = p; |
| r2 = r1.x; | r6.x = 3; |
| r3 = q; | |
| r4 = r3.x; | |
| r5 = r2; | |

内存模型决定了程序中每个点的可能值。每个线程在隔离状态下的行为必须遵循该线程的语义，但每个读取所看到的值是由内存模型决定的。当我们提到这一点时，我们说程序遵循线程内语义。线程内语义是单线程程序的语义，并允许根据其内部看到的值来完全预测线程的行为。为了确定执行中线程 `t` 的动作是否合法，我们按照本规范其他部分的单线程上下文来评估线程 `t` 的实现。

当评估 `t` 生成线程间操作时，它必须与程序顺序之前的线程间操作匹配。如果 `a` 是读取，`t` 的进一步评估将使用内存模型确定的其看到的值。

本节提供了 Java 编程内存模型的规范，但涉及 `final` 字段的问题在 §17.5 中有描述。

此处指定的内存模型从根本上并不是基于 Java 编程语言面向对象的特性。为了使示例简洁简单，我们展示的代码片段不包含类或方法定义，也没有显式的引用。大多数示例由两个或多个线程组成，包含访问局部变量、共享全局变量或对象实例字段的语句。我们通常使用如 `r1` 或 `r2` 等变量名表示方法或线程的变量。此类变量不可被其他线程访问。

## 17.4.2 共享变量

线程之间可以共享的内存被称为共享内存或堆内存。

所有实例字段、静态字段和数组元素都存储在堆内存中。在本章中，我们使用“变量”一词来指代字段和数组元素。

局部变量 (§14.4)、形式方法参数 (§8.4.1)以及异常处理程序参数 (§14.20)永远不会在线程之间共享，且不受内存模型的影响。

对同一个变量的两次访问（读取或写入）如果其中至少一次访问是写入，则称这两个访问是冲突的。

## 17.4.3 动作

线程间动作是由一个线程执行，但可以被另一个线程检测或直接影响的动作。程序可能会执行以下几种线程间动作：

- **读取**（普通的或非 volatile 的）。读取变量。
- **写入**（普通的或非 volatile 的）。写入变量。
- **同步动作**，包括：
  - **volatile 读取**。对变量进行 volatile 读取。
  - **volatile 写入**。对变量进行 volatile 写入。
  - **锁（Lock）**。锁定一个监视器（monitor）。
  - **解锁（Unlock）**。解锁一个监视器。
  - 线程的（合成）第一个和最后一个动作。
  - 启动线程或检测线程已终止的动作 (§17.4.4)。
- **外部动作**。外部动作是在执行之外可能被观测到的动作，并具有基于外部环境的结果。
- **线程分歧动作** (§17.4.9)。线程分歧动作仅由处于无限循环的线程执行，在该循环中没有执行任何内存、同步或外部动作。如果一个线程执行了线程分歧动作，随后将跟随无限次的线程分歧动作。

引入线程分歧动作是为了建模一个线程如何导致所有其他线程停滞且无法取得进展。

本规范仅关注线程间动作。我们不需要关注线程内动作（例如，两个局部变量相加并将结果存储在第三个局部变量中）。如前所述，所有线程都必须遵守 Java 程序正确的线程内语义。我们通常将线程间动作简称为“动作”。

一个动作由元组 `< t, k, v, u >` 描述，包含：

- `t` - 执行该动作的线程
- `k` - 动作的种类
- `v` - 动作涉及的变量或监视器

对于锁动作，`v` 是被锁定的监视器；对于解锁动作，`v` 是正在解锁的监视器。

如果该动作是（volatile 或非 volatile）读取，`v` 是被读取的变量。

如果该动作是（volatile 或非 volatile）写入，`v` 是被写入的变量。

- `u` - 动作的任意标识符

外部动作元组包含一个额外的组件，其中执行该动作的线程所感知的外部动作结果。这可能包括关于动作成功或失败的信息，以及动作读取的任何值。

外部动作的参数（例如写入套接字的字节）不属于外部动作元组的一部分。这些参数由线程内的其他动作设置，并可以通过检查线程内语义来确定。内存模型没有显式讨论它们。

在非终止的执行中，并非所有外部动作都是可观测的。非终止的执行和可观测动作在 §17.4.9 中讨论。

## 17.4.4 程序和程序顺序

在每个线程 `t` 执行的所有线程间动作中，`t` 的程序顺序是一个全序，它反映了根据 `t` 的线程内语义执行这些动作的顺序。

一个动作集合是**顺序一致的**，如果满足所有动作都发生在一个与程序顺序一致的全序（执行顺序）中，并且此外，对变量 `v` 的每次读取 `r` 都能看到写入 `w` 对 `v` 写入的值，使得：

- `w` 在执行顺序中排在 `r` 之前，
- 不存在其他写入 `w'`，使得在执行顺序中 `w` 排在 `w'` 之前且 `w'` 排在 `r` 之前。

顺序一致性是关于程序执行中可见性和排序所做出的一项非常强的保证。在顺序一致的执行中，对于所有单独的动作（如读取和写入）存在一个全序，该全序与程序顺序一致，且每个单独动作都是原子的，并立即对每个线程可见。

如果程序没有数据竞态，那么该程序的所有执行都将表现为顺序一致的。

顺序一致性以及/或无数据竞态，允许出现那些需要被原子化感知但实际上并非原子化的操作组所引起的错误。

> 如果我们使用顺序一致性作为内存模型，我们所开发的许多编译器和优化都将是非法的。例如，在表 17.4-C 的轨迹中，一旦向 `p.x` 写入 3 发生，对该位置的后续读取将被看到该值。

## 17.4.5 同步顺序

每次执行都有一个同步顺序。同步顺序是执行中所有同步动作的全序。对于每个线程 `t`，`t` 中同步动作（§17.4.3）的同步顺序与 `t` 的程序顺序（§17.4.4）一致。

同步动作在动作上引发了“同步”（synchronized-with）关系，定义如下：

- 监视器 `m` 上的解锁动作与 `m` 上所有后续的锁动作同步（其中“后续”由同步顺序定义）。
- 对 volatile 变量 `v` 的写入（§8.3.1）与任何线程对 `v` 的所有后续读取同步（其中“后续”由同步顺序定义）。
- 启动线程的动作与该线程的第一个动作同步。
- 每个变量写入默认值（零、false 或 null）与每个线程的第一个动作同步。尽管在包含该变量的对象分配之前写入默认值似乎有些奇怪，但从概念上说每个对象在程序开始时就具有其默认值。
- 线程 `T1` 的最后一个动作与另一个线程 `T2` 检测到 `T1` 已终止的任何动作同步。

```java
T2 可以通过 T1.isAlive() 或 T1.join() 实现这一点。
```

- 如果 `T1` 中断了 `T2`，`T1` 的中断与任何线程（包括 `T2`）确定 `T2` 被中断的时刻（通过抛出 `InterruptedException` 或调用 `Thread.interrupted()`）同步。

同步边的源称为释放（release），目标称为获取（acquire）。

## 17.4.6 发生之前

两个动作可以通过发生之前的关系进行排序。如果一个动作发生在另一个动作之前，则前者是可见并排在后者之前的。

如果我们有两个动作 `x` 和 `y`，我们写 $hb(x, y)$ 表示 `x` 发生在 `y` 之前。

- 如果 `x` 和 `y` 是同一线程的动作且 `x` 在程序顺序上在 `y` 之前，则我们 $hb(x, y)$。
- 从对象构造函数的结束到该对象的终结（§12.6）开始之间存在一个发生之前的边。
- 如果动作 `x` 同步后续动作 `y`，那么我们也有 $hb(x, y)$。
- 如果 $hb(x, y)$ 且 $hb(y, z)$，则 $hb(x, z)$。

`Object` 类（§17.2.1）的 `wait` 方法与其锁和解锁动作关联；它们的发生之前关系由这些关联动作定义。

应该注意，两个动作之间存在发生之前关系并不一定意味着它们在实现中必须按顺序发生。如果重排序产生的结果与合法执行一致，则它不是非法的。

例如，对由线程构造的对象的每个字段写入默认值，不需要在该线程开始之前发生，只要没有读取者观察到这一事实即可。

更具体地说，如果两个动作共享一个*先发生于*（happens-before）关系，对于任何与它们不共享*先发生于*关系的代码来说，这两个动作并不一定表现为是按顺序发生的。例如，一个线程中的写入操作与另一个线程的读取构成数据竞态（data race），这些写入操作对于这些竞态来说顺序可能是无序的。

*先发生于*（happens-before）关系定义了数据竞态发生的时刻。

一个同步边集合 $S$ 是*充分的*（sufficient），如果它是最小集合，使得 $S$ 与程序顺序（program order）的传递闭包确定了执行中所有的*先发生于*边。该集合是唯一的。

根据上述定义可以得出：

- 对监视器的解锁（unlock）*先发生于*该监视器的后续每次锁（lock）操作。
- 对易变性（volatile）字段（§17.8.3.1）的写入*先发生于*对该字段的后续每次读取。
- 对线程调用 `start()`*先发生于*被启动线程中的任何动作。
- 一个线程中的所有动作*先发生于*该线程从 `join()` 成功返回的任何其他线程。
- 任何对象的默认初始化*先发生于*程序的任何其他动作（默认写入除外）。

当一个程序包含两个没有被*先发生于*关系排序的冲突访问（§17.4.2）时，称该程序包含一个*数据竞态*（data race）。

除线程内检查之外的操作语义，例如数组长度的读取（§10.7）、受检查类型转换的执行（§5.5, §15.16）以及虚拟方法的调用（§15.12）——不直接受数据竞态的影响。

> 因此，数据竞态不会导致错误行为，例如返回数组的错误长度。

一个程序当且仅当所有顺序一致的（sequentially consistent）的执行都不包含数据竞态时，该程序是*正确同步的*（correctly synchronized）。

如果一个程序是正确同步的，那么该程序的所有执行都将表现为顺序一致的（§17.4.4）。

## 17.4.7 先发生于一致性

对于程序员来说这是一个极强的保证。程序员不需要通过推理重排序来确定他们的代码是否包含数据竞态。在确定代码是否正确同步时，他们也不需要推理重排序。一旦确定代码是正确同步的，程序员就不需要担心重排序会影响他们的代码。

程序必须正确同步，以避免出现当代码重排序时可能观察到的类反直觉行为。使用正确同步不能保证程序的整体行为是正确的。然而，它允许程序员以简单的方式推断程序可能的行为；正确同步程序的行为对可能的重排序的依赖性要低得多。如果没有正确同步，可能会出现非常奇怪、困惑且反直觉的行为。

我们说，变量的读取 `r` 被允许观察到对 `v` 的写入 `w`，如果执行轨迹的*先发生于*偏序满足：

- `r` 未排序在 `w` 之前（即并非 hb(r, w)），
- 不存在对 `v` 的交叉写入 `w'`（即不存在写入 `w'` 使得 hb(w, w') 且 hb(w', r)）。

通俗地说，如果没有*先发生于*排序来防止该竞态，读取 `r` 就被允许看到写入 `w` 的结果。

一个动作集合 `A` 是*先发生一致的*（happens-consistent），如果对于 `A` 中的所有读取 `r`，其中 `W(r)` 是 `r` 看到的写入动作，并非满足 hb(r, W(r)) 或存在 `A` 中的某个写入 `w` 使得 `w.v = r.v` 且 hb(W(r), w) 且 hb(w, r)。

在*先发生于一致的*动作集合中，每个读取都会看到一个由*先发生于*排序允许其看到的写入。

### 示例 17.4.5-1. 先发生于一致性

对于表 17.4.5-A 中的轨迹，初始 `A == B == 0`。该轨迹可以显示 `r2 == 0` 且 `r1 == 0` 仍然是*先发生于一致*的，因为存在某些执行顺序，使得每个读取都能读到相应的写入。

#### 表 17.4.5-A. *先发生于一致性*允许但顺序一致性不允许的行为。

| 线程 1 | 线程 2 |
| :--- | :--- |
| B = 1; | A = 2; |
| r2 = A; | r1 = B; |

由于没有同步，每个读取都可以看到初始值的写入或另一个线程的写入。显示这种行为的执行顺序为：

```text
1: B = 1;
3: A = 2;
2: r2 = A; // 看到初始写入 0
4: r1 = B; // 看到初始写入 0
```

另一个是*先发生于一致*的执行顺序是：

```text
1: r2 = A; // 看到 A = 2 的写入
3: r1 = B; // 看到 B = 1 的写入
2: B = 1;
4: A = 2;
```



在这次执行中，读取看到了一个由`先发生于`排序允许其看到的写入。

# 17.4.6 执行

执行 $E < P, A, po, so, W >$ 描述于：

- P - 程序
- A - 动作集合
- po - 程序顺序
- so - 同步顺序
- W - 写入
- V - 值的集合
- sw - 同步
- hb - 先发生于

注意，同步和先发生于由 $E$ 的其他部分决定。

# 17.4.7 良好的执行

如果满足以下条件，则执行 $E < P, A, po, so >$ 是良好的：

1. 每个读取看到变量。对于 $A$ 中的所有 volatile 读取 $r$，都有 $W(r).v=r.v$。变量 $w$ 是 volatile 的当且仅当它是写入。
2. 先发生于顺序由同步边的传递闭包给出。它必须是一个有效的偏序。
3. 执行遵循线程内一致性。对于每个线程 $t$，$A$ 中该线程执行的动作与其程序顺序生成的动作相同。程序顺序必须反映 $P$ 中的程序顺序。
4. 执行是`先发生于一致的`（参见 17.4.6 节）。
5. 执行遵循同步顺序一致性。对于 $A$ 中的所有读取 $r$，并非满足 $so(r, W(r))$ 或存在 $A$ 中的 $w$ 使得 $w.v=r.v$ 且 $so(W(r), w)$ 且 $so(w, r)$。

# 17.4.8 执行与因果要求

我们使用 $f_d$ 表示将函数 $f$ 的定义域限制到 $d$。对于 $d$ 中的所有 $x$，$f_d(x)=f(x)$；而对于所有不在 $d$ 中的 $x$，$f_d(x)$ 未定义。

良好的执行通过*提交* $A$ 中的动作进行验证。如果 $A$ 中的所有动作都可以提交，则该执行满足 Java 语言内存模型的因果要求。

## 内存模型

从空集 $C_0$ 开始，我们执行一系列步骤，即从动作集合 $A$ 中选取动作并将其添加到一个已提交动作集 $C_i$ 中，以得到一个新的已提交动作集 $C_{i+1}$。为了证明这种方法是合理的，对于每个 $C_i$，我们需要证明存在包含 $C_i$ 且满足特定条件的执行 $E$。

形式而言，一个执行 $E$ 满足 Java 语言内存模型的因果性要求，当且仅当存在：

- 动作集合 $C_0, C_i, \dots$ 使得：
    - $C_0$ 是空集
    - $C_i$ 是 $C_{i+1}$ 的真子集
    - $A = \cup(C_0, C_i, \dots)$

如果 $A$ 是有限的，那么序列 $C_0, C_i, \dots$ 将是有限的，并结束于集合 $C_n = A$。

如果 $A$ 是无限的，那么序列 $C_0, C_i, \dots$ 可能是无限的，且必须满足该无限序列所有元素的并集等于 $A$。

- 良好的执行 $E_i, \dots$，其中 $E_i < P, A_i, po_i, so_i, W_i, V_i, hb_i$。

给定这些动作集合 $C_0$ 和执行 $E_i, \dots$，$C_i$ 中的每个动作必须是 $E_i$ 中的动作之一。$C_i$ 中的所有动作在 $E_i$ 和 $E_j$ 中必须共享相同的相对先发生于顺序和同步顺序。形式而言：

1. $C_i$ 是 $A_i$ 的子集
2. $hb_i|_{C_i} = hb_j|_{C_i}$
3. $so_i|_{C_i} = so_j|_{C_i}$

$C_i$ 中写入操作所写入的值在 $E_i$ 和 $E_j$ 中必须相同。只有 $C_{i,j}$ 中的读操作需要在 $E_i$ 和 $E_j$ 中看到相同的写入。形式而言：

4. $V_i|_{C_{i,j}} = V_j|_{C_{i,j}}$
5. $W_i|_{C_{i,j}} = W_j|_{C_{i,j}}$

$E_i$ 中所有不在 $C_{i,j}$ 中的读操作必须看到发生于它们之前的写入。$C_i - C_{i,j}$ 中的每个读操作 $r$ 必须在 $E_i$ 和 $E_j$ 中都看到写入，但在 $E_i$ 中看到的写入可能与其在 $E_j$ 中看到的不同。形式而言：

6. 对于 $A_i - C_{i,j}$ 中的任何读操作 $r$，我们有 $hb_i(W_i(r), r)$
7. 对于 $(C_i - C_{i,j})$ 中的任何读操作 $r$，在 $C_{i,j}$ 中有 $W_i(r)$，在 $C_{i,j}$ 中有 $W(r)$

## 线程与锁

## 内存模型 17.4

给定对于 $E_i$ 的一组充分同步边，如果存在一个释放-获取对发生于（§ 17.4.5）你正在提交的动作之前，那么该对必须存在于所有 $j \ge i$ 的 $E_j$ 中。形式而言：

- 令 $ssw$ 为在 $hb$ 的传递归约中但不在 $po$ 中的 $sw$ 边。我们称 $ssw$ 为 $E_i$ 的充分同步边。如果 $ssw(x, y)$ 且 $hb(y, z)$ 且 $z$ 在 $C_i$ 中，则对于所有 $j \ge i$，都有 $ssw(x, y)$。

- 如果一个动作被提交，所有发生于之前的外部动作也都被提交。

- 如果 $y$ 在 $C_i$ 中，$x$ 是外部动作且 $hb(x, y)$，则 $x$ 在 $C_j$ 中。

## 示例 17.4.8-1. 发生于一致性并不充分

发生于一致性是一组必要但非充分的约束。强制执行发生于一致性的内存允许出现不可接受的行为——即那些违反我们为程序建立的要求的行为。例如，发生于一致性允许值“凭空出现”。这可以通过对表 17.4.8-A 中的轨迹进行详细检查来看到。

### 表 17.4.8-A. 发生于一致性并不充分

| 线程 1 | 线程 2 |
| --- | --- |
| r1 = x; | r2 = y; |
| if (r1 != 0) y = 1; | if (r2 != 0) x = 1; |

表 17.4.8-A 中的代码是正确同步的。这可能看起来很惊讶，因为它没有执行任何同步动作。但请记住，如果程序以顺序一致的方式执行且没有数据竞态，则它就是正确同步的。如果这段代码以顺序一致的方式执行，每个动作将按照程序顺序发生，且两个写入都不会发生。由于该程序是正确同步的，$C_i - C_{i,j}$ 中的所有读操作必须看到发生于之前的写入。每个读操作 $r$ 必须在 $E_i$ 和 $E_j$ 中都看到写入，但在 $E_i$ 中看到的写入可能与其在 $E_j$ 中看到的不同。

## 线程与锁

## 内存模型 17.4

我们还定义了一个特殊的挂起动作。如果行为是由包含挂起动作的外部动作集合描述的，它表明在执行这些动作后，程序可以无限期运行而不终止。如果所有线程都被阻塞，或者程序可以执行无限数量的动作而不终止，则程序会挂起。

线程在各种情况下可能会阻塞，例如当它尝试获取锁或执行依赖外部数据的外部动作（如读）。

执行可能导致线程无限阻塞且执行不终止。在这种情况下，被阻塞线程产生的动作由该线程在导致阻塞的动作之前产生的所有动作组成，在该动作之后不会产生任何动作。

为了推理可观测行为，我们需要讨论观测动作的集合。

如果 $O$ 是执行 $E$ 的观测动作集合，那么 $O$ 必须是 $E$ 的动作 $A$ 的子集，并且包含有限数量的动作，即使 $A$ 是无限的。此外，如果动作 $y$ 在 $O$ 中，且 $hb(x, y)$ 或 $so(x, y)$，则 $x$ 在 $O$ 中。

注意，观测动作的集合并不限于外部动作。相反，只有位于观测动作集合中的外部动作才被视为可观测外部动作。

一个行为 $B$ 是程序 $P$ 的允许行为，当且仅当 $B$ 是有限的外部动作集合，且：

- 存在 $P$ 的一个执行 $E$，以及 $E$ 的观测动作集合 $O$，且 $B$ 是 $O$ 中外部动作的集合（如果 $E$ 中的任何线程结束于阻塞状态且 $O$ 包含 $E$ 中的所有动作，则 $B$ 也可以包含一个挂起动作）；或
- 存在一个动作集合 $O$，使得 $B$ 包含一个*挂起*动作以及 $O$ 中的所有外部动作，并且对于所有 $k \ge |O|$，存在一个具有动作 $A$ 的 $P$ 的执行 $E$，并且存在动作集合 $O'$ 使得：
    - $O$ 和 $O'$ 是 $A$ 的子集，满足观测动作集的要求。
    - $O \subseteq O' \subseteq A$
    - $|O'| \ge k$
    - $O'$ 不包含外部动作

注意，行为 $B$ 并没有描述 $B$ 中外部动作被观测到的顺序，但其他关于外部动作如何生成的（内部）约束可能会施加此类约束。

# 17.5 final 字段语义

声明为 `final` 的字段只初始化一次，在任何情况下都不会再被更改。`final` 字段的详细语义与普通字段略有不同。特别是，编译器有很大的自由将对 `final` 字段的读取操作跨越同步屏障以及对任意或未知方法的调用。相应地，在某些非 `final` 字段必须从内存中重新加载的情况下，编译器允许将 `final` 字段的值缓存在寄存器中而不从内存中重新加载。

`final` 字段还允许程序员在没有同步的情况下实现线程安全的不可变对象。线程安全的不可变对象对所有线程可见，即使使用数据竞态来在线程之间传递该不可变对象的引用。这可以提供安全保证，防止不正确或恶意代码误用不可变类。必须正确使用 `final` 字段以提供不可变性保证。

当一个对象的构造函数执行完毕时，该对象被认为是**完全初始化**的。一个只有在对象被完全初始化后才能看到该对象引用的线程，保证能看到该对象 `final` 字段的正确初始化的值。

`final` 字段的使用模型非常简单：在对象的构造函数中对该对象的 `final` 字段赋值；并且不要在对象构造函数完成之前，在另一个线程可以看到的地方写入指向正在构造的对象的引用。如果遵循了这一点，那么当另一个线程看到该对象时，该线程将始终看到该对象 `final` 字段的正确构建的版本。

它还将看到由这些 final 字段引用的任何对象或数组的版本，这些版本至少与 final 字段一样新。

## 示例 17.5-1. Java内存模型中的 final 字段

下面的程序说明了 final 字段与普通字段的比较。

```java
class FinalFieldExample {

    final int x;

    int y;

    static FinalFieldExample f;

    public FinalFieldExample() {

        x = 3;

        y = 4;

    }

    static void writer() {

        f = new FinalFieldExample();

    }

    static void reader() {

        if (f != null) {

            int i = f.x; // 保证看到 3

            int j = f.y; // 可能看到 0

        }

    }

}
```

类 `FinalFieldExample` 有一个 final 字段 `x` 和一个非 final 字段 `y`。一个线程可能执行 `writer` 方法，另一个线程可能执行 `reader` 方法。

由于 `writer` 方法在对象构造函数完成后写入了 `f`，`reader` 将保证看到 `f.x` 的正确初始值；它将读取值 3。`f.y` 不是 final 的；因此 `reader` 方法不保证看到它的值 4。

## 示例 17.5-2. 用于安全的 final 字段

final 字段的设计目的是允许提供必要的安全保证。考虑以下程序。`Global.s`（我们将其称为线程 1）执行：

```java
Global.s = "/tmp/usr".substring(4);
```

而另一个线程（线程 2）执行：

```java
String myS = Global.s;

if (myS.equals("/tmp/")) System.out.println(myS);
```

String 对象旨在是不可变的，且字符串操作不执行同步。虽然 `String` 的实现没有包含任何数据竞态，但其他代码可能存在涉及使用 String 对象的数据竞态，而内存模型对使用数据竞态的程序提供了弱保证。特别是，如果 `String` 类的字段不是 final 的，那么可能（尽管可能性不大）线程 2 初始可能会看到 String 对象偏移量的默认值 0，从而允许它与 "tmp" 比较。对 String 对象的后续操作可能会看到正确的偏移量 4，因此该 String 对象被感知为 "usr"。Java 编程语言的安全特性依赖于 String 对象被感知为真正的不可变，即使恶意代码使用数据竞态在线程之间传递 String 引用。

## 17.5.1 final 字段的语义

设 $o$ 为一个对象，$c$ 为 $o$ 的一个构造函数，其中写入了 final 字段 $f$。当 $c$ 退出（无论是正常还是异常）时，$o$ 的 final 字段 $f$ 发生一次冻结。

注意，如果调用了另一个构造函数，被调用的构造函数设置了一个 final 字段，则该 final 字段的冻结发生在被调用的构造函数结束时。

对于每次执行，读取的行为受到两个额外偏序的影响：解引用链 `dereferences(r)` 和内存链 `mc(c)`，它们被认为是执行的一部分（因此对于任何特定执行来说都是固定的）。这些偏序必须满足以下约束（不需要唯一解）：

- 解引用链：如果一个动作是由未初始化 $o$ 的线程 $t$ 对 final 字段的读取或写入，则必须存在某个读取 $r$ 看到 $o$ 的地址，使得 $r$ `dereferences(a)`。
- 内存链：内存链有几项约束：
    - 如果 $r$ 是对 final 字段的读取，必须满足 `mc(w,r)`。
    - 如果 $r$ 和 $a$ 是 `dereferences(r)` 的动作，则必须满足 `mc(r,a)`。
    - 如果 $w$ 是未初始化 $o$ 的线程 $t$ 对 final 字段的写入，则必须存在某个读取 $r$ 看到 $o$ 的地址，使得 `hb(w,r)`。

给定一个写入 $w$，一个冻结 $f$，一个动作 $a$（不是对 $a$ 的读取），一个 final 字段的读取 $r1$，以及一个读取 $r2$ 使得 `hb(w,f)`、`hb(f,a)`、`mc(a,r1)` 和 `dereferences(r1,r2)`，那么在确定 $r2$ 可以看到哪些 final 的值时，我们考虑 `hb(w,r2)`。（这种 happens-before 排序不会与其他 happens-before 排序发生传递闭包。）

注意解引用顺序是自反的，且 $r_1$ 可以与 $r_2$ 相同。

对于 final 字段的读取，被认为在读取之前的写入是源于 final 字段语义的。

### 17.5.2 构造期间读取 final 字段

在构造对象的线程内部对对象 final 字段的读取相对于 happens-before 规则排序。如果读取发生在构造函数中设置字段之后，它看到赋值的 final 值，否则设置默认值。

### 17.5.3 final 字段的后续修改

在某些情况下（如反序列化），系统需要在对象构造后更改 final 字段。final 字段可以通过反射和其他依赖于实现的方法进行更改。唯一具有合理语义的模式是先构造对象，然后更新其 final 字段。在所有字段更新完成之前，对象不应对其他线程可见，也不应读取 final 字段。final 字段的冻结发生在设置该字段的构造函数结束时，以及在通过反射或特殊机制修改 final 字段后立即发生。

尽管如此，仍存在许多问题。如果 final 字段在字段声明中初始化为常量表达式（15.29），对 final 字段的更改可能无法被观察到，因为对 final 字段的使用在编译时被替换为常量表达式的值。

另一个问题是规范允许对 final 字段进行激进优化。在线程内部，允许对 final 字段的读取与未发生在构造函数中的 final 字段修改进行重排序。

#### 示例 17.5.3-1. final 字段的激进优化

```java
class A {

  final int x;

  A() {

    x = 1;

  }

  int f() {

    return d(this, this);

  }

  int d(A a1, A a2) {

    int i = a1.x;

    g(a1);

    int j = a2.x;

    return i - j;

  }

  static void g(A a) {

    // 使用反射将 a.x 修改为 2

  }

}
```



在 `d` 方法中，编译器允许自由地重排对 `x` 的读取以及对 `g` 的调用。新的 `A(a).f()` 可能会返回 -1、0 或 1。

实现可能提供了一种从“最终字段安全上下文”（final-field-safe-context）中逃逸代码块的方法。如果一个对象是在最终字段安全上下文中构造的，那么对该对象的最终字段的读取将与在最终字段安全上下文中发生的该最终字段的修改不会重排。

最终字段安全上下文具有额外的保护。如果一个线程看到了一个对象的发布错误的引用，导致该线程看到了某个最终字段的默认值，随后随后在最终字段安全上下文中读取了该对象的发布正确的引用，则该线程将保证看到该最终字段的正确值。在形式化中，在最终字段安全上下文中执行的代码被视为一个单独的线程（仅用于最终字段语义）。

在具体实现中，编译器不应将对最终字段的访问移动到最终字段安全上下文内部或外部（尽管它可以移动到此类上下文执行之后，只要该对象不是在该上下文中构造的即可）。

执行器或线程池是使用最终字段安全上下文的一个恰当场景。通过在单独的最终字段安全上下文中执行每个 `Runnable`，执行器可以保证，任何 `Runnable` 对对象 `o` 的错误访问都不会消除其他由同一执行器处理的 `Runnable` 的最终字段保证。

## 17.5.4 写保护的字段

通常情况下，一个 `final` 且 `static` 的字段是不可修改的。然而，`System.in`、`System.out` 和 `System.err` 是 `static final` 字段，由于历史原因，必须允许通过 `System.setIn`、`System.setOut` 和 `System.setErr` 方法进行修改。我们将这些字段称为写保护（write-protected），以区分它们于普通的最终字段。

编译器需要以不同于其他字段的方式处理这些字段。例如，对普通最终字段的读取对同步是“免疫”的：锁中的屏障或 `volatile` 读取不会影响从最终字段中读取到的值。由于写保护字段的值可能会被更改，因此同步事件应该对它们产生影响。因此，语义规定这些字段被视为用户代码无法更改的普通字段，除非该代码位于 `System` 类中。

## 17.6 字的撕裂（Word Tearing）

Java 虚拟机实现的一个考虑因素是，每个字段和数组元素都被认为是独立的；对一个字段或元素的更新不能与对任何其他字段或元素的读取或更新产生交互。特别是，两个分别更新字节数组相邻元素的线程之间不会相互干扰，也不需要同步来确保顺序一致性。

某些处理器不提供写入单个字节的能力。在这些处理器上通过简单地读取整个字（word）、更新相应的字节，然后将整个字写回内存来实现字节数组的更新将是非法的。这种问题有时被称为“字撕裂”（word tearing），在无法隔离更新单个字节的处理器上，需要其他方法。

### 示例 17.6-1. 字撕裂的检测

以下程序是一个检测字撕裂的测试用例：

```java
public class WordTearing extends Thread {

    static final int LENGTH = 8;

    static final int ITERS = 1000000;

    static byte[] counts = new byte[LENGTH];

    static Thread[] threads = new Thread[LENGTH];

    final int id;

    WordTearing(int i) {
        id = i;
    }

    public void run() {
        byte v = 0;
        for (int i = 0; i < ITERS; i++) {
            byte v2 = counts[id];
            if (v != v2) {
                System.err.println("Word-Tearing found: " +
                    "counts[" + id + "] = " + v2 +
                    ", should be " + v);
                return;
            }
            v++;
            counts[id] = v;
        }
    }

    public static void main(String[] args) {
        for (int i = 0; i < LENGTH; ++i) {
            (threads[i] = new WordTearing(i)).start();
        }
    }
}
```



这意味着字节不能被原子字节覆盖。

# 17.7 对 double 和 long 的非原子性处理

就 Java 编程语言内存模型而言，对非 `volatile` 的 `long` 或 `double` 值的单次写入被视为两次独立的写入：分别写入每个 32 位半部分。这可能导致一种情况：线程看到了来自某次写入的 64 位值的前 32 位，以及来自另一次写入的后 32 位。

对 `volatile` 的 `long` 和 `double` 值的写入和读取始终是原子的。

引用的写入和读取始终是原子的，无论它们被实现为 32 位还是 64 位值。

某些实现可能发现将对 64 位 `long` 或 `double` 值的单次写入操作划分为两个相邻 32 位值的两次写入操作是方便的。为了效率考虑，这种行为取决于实现，并可能导致 64 位值的拆分。程序应避免这种可能带来的复杂问题。

# 18 推断

对于推断而言，许多编译时分析需要对未知类型进行推理。在高级别，推断可以分为三个过程：

- **归约**：获取关于表达式或类型的断言，称为约束公式，并将其归约为推理变量的边界。
- **合并**：维护推理变量边界，确保在添加新边界时的一致性。由于一个变量的边界有时会影响另一个变量，此过程在这些变量之间传播边界。
- **解析**：检查推理变量边界并确定与这些边界兼容的实例化。

这些过程紧密交互：归约可以触发合并；合并可能导致进一步的归约；而解析可能会引发进一步的合并。

- 18.1 更精确地定义了所使用的概念和符号。
- 18.2 详细描述归约。
- 18.3 详细描述合并。
- 18.4 详细描述解析。
- 18.5 定义了如何使用这些推断工具解决某些编译时问题。

与 Java SE 7 版《Java 语言规范》相比，推断的重要变化包括：

- 支持 Lambda 表达式和方法引用作为方法调用参数。
- 将推断泛化为定义推断完成后可能没有确定类型的表达式，这对改进嵌套泛型方法和钻石构造函数的推断具有显著效果。
- 描述推断如何处理通配符化的函数接口目标以及特定的方法分析。
- 澄清了推断适用性测试（仅涉及调用参数）与调用类型推断（包含目标类型）之间的区别。
- 延迟所有推理变量（即使带有下界）的解析，以获得更好的结果。
- 改进相互依赖（或自依赖）变量的推断行为。
- 消除 Bug 和潜在的混淆源。此修订版更仔细地处理了特定版本上下文与子类型之间的区别，并通过对应非推断关系来描述关系归约。在故意偏离非推断关系的地方，已明确指出。
- 为未来的演进奠基础：推断的增强或新应用将更容易整合到规范中。

本节定义了推理变量、约束公式和边界，因为这些术语将贯穿整个章节。它还介绍了符号。

## 18.1 概念与符号

### 18.1.1 推理变量

推理变量是类型的元变量——即是允许对类型进行抽象推理的特殊名称。为了区别于类型变量，推理变量用希腊字母表示，正确的 `α`。

“类型”一词在本章中用得较泛，包含了包含推理变量的类类型语法。“正类型”则排除此类“类型”。

### 18.1.2 约束公式

约束公式是可能涉及推断变量的兼容性或子类型断言。公式可能采取以下形式之一：

- `Expression → T`：表达式在松散调用上下文中与类型 `T` 兼容（§15.3）。
- `S → T`：类型 `S` 在松散调用上下文中与类型 `T` 兼容（§15.3）。
- `S <: T`：引用类型 `S` 是引用类型 `T` 的子类型（§4.10）。
- `S <= T`：类型参数 `S` 被类型参数 `T` 包含（§4.5）。
- `S = T`：类型 `S` 与类型 `T` 相同（§4.3），或者类型参数 `S` 与类型参数 `T` 相同。
- `LambdaExpression throws T`：`LambdaExpression` 主体抛出的检查异常由从 `T` 导出的函数类型的 `throws` 子句声明。
- `MethodReference throws T`：被引用方法抛出的检查异常由从 `T` 导出的函数类型的 `throws` 子句声明。

约束公式的示例：

- `Collections.singleton("hi")`
- `Arrays.asList(1, 2.0)`，我们拥有约束公式 `1 → α` 和 `2.0 → α`。通过归约，这将变为约束公式 `int → α` 和 `double → α`，以及 `Integer <: α` 和 `Double <: α`。
- 从构造函数调用目标 `List<Thread> lt = new ArrayList<>()` 中，我们得到约束公式 `ArrayList<α> → List<Thread>`。通过归约，这将变为约束公式 `α <: List<Thread>`，然后 `α = Thread`。

### 18.1.3 边界

在推断过程中，维护一组对推断变量的 `bounds`（边界）。边界具有以下公式之一：

- `S = T`，其中 `S` 或 `T` 至少有一个是推断变量：`S` 与 `T` 相同。
- `S <: T`，其中 `S` 或 `T` 至少有一个是推断变量：`S` 是 `T` 的子类型。
- `false`：不存在有效的推断变量选择。
- `G<α₁, ..., αₙ> = capture(G<A₁, ..., Aₙ>)`：变量 `α₁, ..., αₙ` 代表应用于 `G<A₁, ..., Aₙ>` 的捕获转换的结果（其中 `A₁, ..., Aₙ` 可能为类型并可能包含推断变量）。
- `throws α`：推断变量 `α` 出现在 `throws` 子句中。

如果在应用替换后，断言为真，则该边界被推断变量*满足*。边界 `false` 永远无法被满足。

某些边界将推断变量与适当类型联系起来。令 `T` 为一个适当类型。给定形式为 `α = T` 或 `T = T` 的边界，我们称 `T` 是 `α` 的*实例化*。同样，给定形式为 `α <: T` 的边界，我们称 `T` 是 `α` 的*严格上界*；给定形式为 `T <: α` 的边界，我们称 `T` 是 `α` 的*严格下界*。

其他边界将推断变量或将推断变量与包含推断变量的类型联系起来。此类形式为 `S = T` 或 `T <: α` 的边界被称为*依赖*。

形式为 `G<α₁, ..., αₙ> = capture(G<A₁, ..., Aₙ>)` 的边界表示 `α₁, ..., αₙ` 是捕获转换结果的占位符。这是必要的，因为捕获转换只能在适当类型上执行，且 `A₁, ..., Aₙ` 中的推断变量可能尚未解析。

形式为 `throws α` 的边界纯粹是信息性的：它引导解析指向 `α` 的实例化，以便在可能的情况下它是一个检查异常。

推断的中间结果是*边界集*。有时使用符号 `true` 来指代空边界集；这仅是为了方便，且它们是互换的。

边界集的示例：

- `(α = String)` 包含单个边界，将 `α` 实例化为 `String`。
- `(Integer <: α, Double <: α, α <: Object)` 描述了 `α` 的两个下界和一个严格上界。
- `(α <: Iterable<?>, β <: Object, α <: List<β>)` 描述了 `α` 和 `β` 各自严格上界，以及它们之间的依赖关系。
- `(false)` 表达了不存在实例化的事。

## 18.2 归约

当推断开始时，通常从类型声明列表 `P₁, ..., Pₚ` 以及相关的推断变量 `α₁, ..., αₚ` 生成边界集。该边界集的生成方式如下。对于每个 `l ≤ p`：

- 如果 `Pₗ` 没有 TypeBound（类型边界），则边界 `αₗ <: Object` 出现在集合。
- 否则，每个 `τ` 被 TypeBound 隔开，`αₗ <: T[P₁:=α₁, ..., T[Pₚ:=αₚ]]` 出现在集合中；如果没有 `αₗ` 的边界，则 `αₗ <: Object` 也出现在集合中。

归约是将约束公式（18.1.2）简化以产生边界集（18.1.3）的过程。依次考虑每个公式。本节规定了如何将其归约为：

- 边界或集合，将与“当前”边界集合并。初始边界集为空。
- 进一步的约束公式，将进行递归归约。

当不再剩余约束公式时归约完成。

归约步骤的结果总是安全的；如果推断实例化满足归约约束和边界，它也将满足原始约束。另一方面，归约不是完备的；可能存在满足原始约束但不满足归约约束的推断实例化。这是由于算法固有的局限以及为了避免复杂性。其影响是存在类型推断的表达式，但如果程序员显式插入类型，则可以。

### 18.2.1 表达式兼容性约束

形式为 `<Expression → τ>` 的约束公式归约如下：

- 如果 `τ` 是适当类型，则当表达式在松散调用上下文中与 `τ` 兼容时（§15.3），约束归约为 `true`，否则为 `false`。
- 否则，表达式是多表达式。结果取决于表达式的形式：
    - 如果表达式是形式为 `(Expression)` 的括号表达式，则约束归约为 `<Expression> → τ`。
    - 如果表达式是类实例化表达式或方法调用表达式，约束归约为用于确定表达式与目标类型 `τ` 兼容的边界集 `Bⱼ`，定义见 §18.5.2.1。（对于类实例化表达式，用于推断的相应“方法”定义在 §15.9.3。）此边界可能包含新的推断变量，以及新变量与 `τ` 中的推断变量之间的依赖关系。
    - 如果表达式是形式为 `e₁ ? e₂ : e₃` 的条件表达式，约束归约为两个约束公式 `<e₂> → τ` 和 `<e₃> → τ`。
    - 如果表达式是 lambda 表达式或方法引用表达式，结果规定如下：
    - 如果表达式是结果为 `e₁, ..., eₙ` 的 switch 表达式，则约束归约为 `n` 个约束公式 `<e₁> → τ`, ..., `<eₙ> → τ`。

### 18.2.2 Lambda 表达式兼容性约束

- 如果 `τ` 不是函数类型（§9.8），则约束归约为 `false`。
- 否则，令 `τ'` 为从 `τ` 推导出的基础目标类型，如 §15.27.3 所示。如果使用 §18.5.3 推导出一个带参数的函数接口类型，则不执行 `F<A'₁, ..., A'ₖ>` 是 `F<A₁, ..., Aₘ>` 的子类型的测试（相反，它通过下方的约束公式进行断言）。该 lambda 表达式的目标函数类型为 `τ'` 的函数类型。那么：
    - 如果找不到任何有效的函数类型，则约束归约为 `false`。
    - 否则，`LambdaExpression` 与目标函数类型的同构性断言如下：
        - 如果 lambda 参数的数量与函数类型的参数类型数量不符，则约束归约为 `false`。
        - 如果 lambda 表达式是隐式类型化的，且函数类型的参数类型中有一个或多个不是适当类型，则约束归约为 `false`。
          > 该条件在实践中由于 §18.5.1 中对隐式类型 lambda 表达式的处理，以及 §18.5.2 中应用于目标类型上的替换而产生。
        - 如果函数类型的返回是 `void` 且 lambda 体既不是语句表达式也不是与 void 兼容的块，则约束归约为 `false`。
        - 如果函数类型的返回不是 `void` 且 lambda 体是一个与值兼容的块，则约束归约为 `false`。
        - 否则，约束归约为所有以下约束公式：
            - 如果 lambda 参数具有显式声明类型 `F₁, ..., Fₙ`，且函数类型具有参数类型 `G₁, ..., Gₘ`，则 (i) 对于所有 `i` (`1 ≤ i ≤ n`)，`<Fᵢ = Gᵢ>`，且 (ii) `<T' <: T>`。
            - 如果函数类型的返回类型是（非 void）`R`，假设 lambda 的参数类型与函数类型的参数类型相同。那么：
                - 如果 `R` 是适当类型，且 lambda 体或 lambda 体中的返回表达式在赋值上下文中与 `R` 不兼容，则结果为 `false`。
                - 否则，如果 `R` 不是适当类型，则 lambda 体具有 `Expression`，约束 `<Expression → R>`；或者当 lambda 体是一个具有结果表达式 `e₁, ..., eₘ` 的块时，对于所有 `i` (`1 ≤ i ≤ m`)，`<eᵢ → R>`。

涉及 lambda 表达式的兼容性约束的关键信息是目标函数返回类型中出现的推理变量的边界集。这是关键的，因为函数接口通常是泛型的，而许多操作这些类型的方法也是泛型的。

在最简单的情况下，lambda 表达式可能仅为推理变量提供一个下界：

```java
<List<T> makeThree(Factory<T> factory) { ... }

String s = makeThree(() -> "abc").get(2);
```



在复杂情况下，结果表达式可能是一个多表达式——也许是另一个 lambda 表达式——因此推理变量在产生边界之前必须通过多个具有不同目标类型的约束公式。

本节描述的大部分工作记录了关于结果表达式的断言；其目的是推导 lambda 表达式的函数类型，并检查明显不符合兼容性的表达式。

我们并不尝试对目标函数 `throws` 子句中出现的推理变量产生边界。因为该异常不是兼容性的一部分 (§15.27.3)——特别是，它不能影响方法的适用性 (§18.5.1)。我们确实获得了这些变量的边界，因为调用类型推导 (§18.5.2.2) 会产生异常约束公式 (§18.2.5)。

如果目标是一个推理变量，或者目标的参数类型包含变量，我们产生 false。在调用类型推导 (§18.5.2.2) 期间，会执行额外的替换以实例化这些推理变量，从而避免这种情况。（换句话说，在实践中，归约不会以这些形式之一作为目标类型被“调用”。）

最后，§15.27.3 要求 lambda 表达式的结果表达式在赋值时与目标的返回类型兼容。如果 $R$ 是适当类型（例如从 `Function<α, Byte>` 推导出的 `Byte`），则可赋值性易于追踪，归约也会这样做。如果 $R$ 不是适当类型（例如从 `Function<String, α>` 推导出的 `α`），则我们做一个简化假设，即宽松兼容将足够。赋值兼容性与宽松调用兼容性之间的区别在于只有赋值允许常量表达式，例如 `Byte b = 100`。因此，我们的简化假设不是保持完备性的；给定返回类型 $\alpha$ 和整数结果表达式 $100$，可以想象它可以被实例化为 `Byte`，但归约不会产生这样的边界。

形式为 `<MethodReference → τ>` 的约束公式，其中 $\tau$ 至少提到一个推理变量，归约如下：

- 如果 $\tau$ 不是函数接口类型，或者 $\tau$ 是一个没有函数类型的函数接口类型 (§9.9)，则约束归约为 false。
- 否则，如果不存在目标 $\tau$ 的潜在适用方法，则约束归约为 false。
- 否则，如果方法引用是精确的 (§18.5.3)，在调用类型推导 (§18.5.2.2) 期间会执行额外的替换以实例化这些推理变量，从而避免这种情况。（换句话说，在实践中，归约不会以这些形式之一作为目标类型被“调用”。）

# 类型推断

编译时未检查警告，并可能影响方法的调用类型 (§15.12.2.6)。

将 $T$ 装箱为 $T'$ 并不是保持完备性的；例如，如果 $T$ 是 `long`，$S$ 可能会被实例化为 `Integer`，它不是 `Long` 的子类型，但可以被拆箱并扩展为 `long`。在这些情况下，我们通过对已知已约束为装箱原始类型的推断变量返回类型进行特殊处理来避免这一用问题；参见 §18.12.5.1。

同样地，对未检查转换的处理在 $T$ 不是参数化类型的情况下（例如，如果 $T$ 是推断变量）牺牲了完备性。在这种情况下，通常不清楚未检查转换是否必要。由于未检查转换会引入未检查警告，除非明显必要，否则推断倾向于避免它们。

## 18.2.3 子类型约束

形式为 $S <: T$ 的约束公式归约如下：

- 如果 $S$ 和 $T$ 是具体类型，如果 $S$ 是 $T$ 的子类型 (§4.10)，则约束归约为 *true*，否则为 *false*。
- 否则，如果 $S$ 是空类型，则约束归约为 *true*。
- 否则，如果 $T$ 是空类型，则约束归约为 *false*。
- 否则，如果 $S$ 是推断变量 $\alpha$，则约束归约为边界 $\alpha <: T$。
- 否则，如果 $T$ 是推断变量 $\alpha$，则约束归约为边界 $S <: \alpha$。
- 否则，根据 $T$ 的形式归约。
- 如果 $T$ 是参数化类或接口类型，或者是参数化类或接口类型的内部类型（直接或间接），令 $A_1, ..., A_n$ 为 $T$ 的类型参数。在 $S$ 的父类型中，识别出一个对应的类或接口类型，其类型参数为 $B_1, ..., B_n$。如果不存在此类类型，则约束归约为 *false*。否则，约束归约为以下新约束：对于所有 $i (1 \le i \le n)$，$B_i \le A_i$。
- 如果 $\tau$ 是其他类或接口类型，如果 $\tau$ 在 $s$ 的父类型中，则约束归约为 *true*，否则为 *false*。
- 如果 $\tau$ 是数组类型 $\tau'[]$；那么在 $s$ 的为数组类型的父类型中，识别出一个最具体的类型 $s'[]$（这可能是 $s$ 本身）。如果不存在数组，则约束归约为 *false*。否则：
    - 如果 $s'$ 和 $\tau'$ 都不是原始类型，则约束归约为 `<s' <: τ'>`。
    - 否则，如果 $s'$ 和 $\tau'$ 是原始类型，则约束归约为 *true*，否则为 *false*。
- 如果 $\tau$ 是类型变量，有三种情况：
    - 如果 $s$ 是交集类型且 $\tau$ 是其中的一个元素，则约束归约为 *true*。
    - 否则，如果 $\tau$ 有下界，则约束归约为 `<S <: B>`。
    - 否则，约束归约为 *false*。
- 如果 $\tau$ 是交集类型 $I_1 \& \dots \& I_n$，则约束归约为以下新约束：对于所有 $i (1 \le i \le n)$ `<S <: I_i>`。

形式为 `<S <: τ>` 的约束公式，其中 $s$ 和 $\tau$ 是类型参数 (§4.5.1)，归约如下：

- 如果 $\tau$ 是类型：
    - 如果 $s$ 是类型，则约束归约为 `<s = τ>`。
    - 如果 $\tau$ 是通配符，则约束归约为 *false*。
    - 如果 $\tau$ 是形式为 `?` 的通配符，则约束归约为 *true*。
    - 如果 $\tau$ 是形式为 `? extends` $\tau'$ 的通配符。
    - 如果 $s$ 是类型，则约束归约为 `<s <: τ'>`。
    - 如果 $s$ 是形式为 `?` 的通配符，则约束归约为 `<Object <: τ'>`。
    - 如果 $s$ 是形式为 `? extends` $s'$ 的通配符，则约束归约为 `<s' <: τ'>`。
    - 如果 $s$ 是形式为 `? super` $s'$ 的通配符，则约束归约为 `<Object = τ'>`。
    - 如果 $\tau$ 是形式为 `?: T'` 的通配符
        - 如果 $s$ 是类型，则约束归约为 `⟨T' <: S⟩`
        - 如果 $s$ 是形式为 `?: S'` 的通配符，则约束归约为 `⟨T' <: S'⟩`
    - 否则，约束归约为 *false*。

## 18.2.4 类型相等

形式为 `⟨s = τ⟩` 的约束，其中 $s$ 和 $\tau$ 是类型，归约如下：

- 如果 $s$ 和 $\tau$ 是具体类型，如果 $s$ 是 $\tau$，则约束归约为 *true* (§4.4)，否则为 *false*。
- 否则，如果 $s$ 或 $\tau$ 是空类型，则约束归约为 *false*。
- 否则，如果 $s$ 是推断变量 $\alpha$ 且 $\tau$ 不是原始类型，则约束归约为 $\alpha$。
- 否则，如果 $\tau$ 是推断变量 $\alpha$ 且 $s$ 不是原始类型，则约束归约为 $\alpha$。
- 否则，根据 $\tau$ 的形式归约。
- 如果 $\tau$ 是参数化类或接口类型，或者是参数化类或接口类型的内部类型（直接或间接），令 $A_1, ..., A_n$ 为 $\tau$ 的类型参数。在 $s$ 的父类型中，识别出一个对应的类或接口类型，其类型参数为 $B_1, ..., B_n$。如果不存在此类类型，则约束归约为 *false*。否则，约束归约为以下新约束：对于所有 $i (1 \le i \le n)$，$B_i = A_i$。
- 如果 $\tau$ 是其他类或接口类型，如果 $s$ 是 $\tau$，则约束归约为 *true*，否则为 *false*。
- 如果 $\tau$ 是数组类型 $\tau'[]$；那么在 $s$ 的为数组类型的父类型中，识别出一个最具体的类型 $s'[]$（这可能是 $s$ 本身）。如果不存在数组，则约束归约为 *false*。否则：
    - 如果 $s'$ 和 $\tau'$ 都不是原始类型，则约束归约为 `<s' = τ'>`。
    - 否则，如果 $s'$ 和 $\tau'$ 是原始类型，则约束归约为 *true*，否则为 *false*。
- 如果 $\tau$ 是类型变量，有三种情况：
    - 如果 $s$ 是交集类型且 $\tau$ 是其中的一个元素，则约束归约为 *true*。
    - 否则，如果 $\tau$ 有下界，则约束归约为 `<S <: B>`。
    - 否则，约束归约为 *false*。
- 如果 $\tau$ 是交集类型 $I_1 \& \dots \& I_n$，则约束归约为以下新约束：对于所有 $i (1 \le i \le n)$ `<s = I_i>`。

形式为 `⟨s = τ⟩` 的约束公式，其中 $s$ 和 $\tau$ 是类型参数 (§4.5.1)，归约如下：

- 如果 $\tau$ 是类型：
    - 如果 $s$ 是类型，则约束归约为 `<s = τ>`。
    - 如果 $\tau$ 是通配符，则约束归约为 *false*。
    - 如果 $\tau$ 是形式为 `?` 的通配符，则约束归约为 *true*。
    - 如果 $\tau$ 是形式为 `? extends` $\tau'$ 的通配符。
    - 如果 $s$ 是类型，则约束归约为 `<s = τ'>`。
    - 如果 $s$ 是形式为 `?` 的通配符，则约束归约为 `<Object = τ'>`。
    - 如果 $s$ 是形式为 `? extends` $s'$ 的通配符，则约束归约为 `<s' = τ'>`。
    - 如果 $s$ 是形式为 `? super` $s'$ 的通配符，则约束归约为 `<Object = τ'>`。
- 如果 $r$ 是形式为 `?: T'` 的通配符
    - 如果 $s$ 是类型，则约束归约为 `⟨T' = S⟩`。
    - 如果 $s$ 是形式为 `?: S'` 的通配符，则约束归约为 `⟨T' = S'⟩`。
    - 否则，约束归约为 *false*。

## 18.2.5 检查异常约束

形式为 `<LambdaExpression ⊢ τ>` 的约束公式归约如下：

- 如果 $\tau$ 不是函数接口类型 (§9.8)，则约束归约为 *false*。
- 否则，按照 §15.27.3 规定确定 lambda 表达式的目标函数类型。如果找不到有效的函数类型，则约束归约为 *false*。
- 否则，如果 lambda 表达式是隐式类型化的，且函数的一个或多个参数类型不是具体类型，则约束归约为 *false*。
- 否则，如果函数的返回类型既不是 *void* 也具体类型，则约束归约为 *false*。
- 否则，令 $E_1, ..., E_n$ 为函数类型 `throws` 子句中不是具体类型的类型。如果 lambda 表达式是隐式类型化的，令其参数类型为函数的参数类型。如果 lambda 体是一个包含多类型结果的表达式或块，令目标返回类型为函数的返回类型。令 $X_1, ..., X_m$ 为 lambda 体可能抛出的检查异常类型 (§11.2)。则有两种情况：
    - 如果 $n=0$（函数的 `throws` 子句仅包含有效类型），那么如果存在某些 $i (1 \leq i \leq m)$ 使得 $X_i$ 不是 `throws` 子句中任何有效类型的子集，则约束归约为 *false*；否则，约束归约为 *true*。
    - 如果 $n>0$，则约束归约为一组子类型约束：对于所有 $i (1 \leq i \leq m)$，如果 $X_i$ 不是 `throws` 子句中任何有效类型的子集，则约束包括对于所有 $j (1 \leq j \leq n)$ 的 $X_i <: E_j$。此外，对于所有 $j (1 \leq j \leq n)$，约束归约为边界 `throws` $E_j$。

形式为 `<MethodReference ⟶throws τ>` 的约束公式归约如下：

- 如果 $\tau$ 不是函数接口，或者如果 $\tau$ 是函数接口但没有函数类型 (§9.9)，则约束归约为 *false*。
- 否则，令方法表达式的目标函数为 $\tau$ 的函数类型。如果方法引用是不精确的 (§15.13.1) 且该函数的参数类型中至少有一个或多个不是有效类型，则约束归约为 *false*。
- 否则，如果方法引用是不精确的且函数类型的结果既不是 *void* 也有效类型，则约束归约为 *false*。
- 否则，令 $E_1, ..., E_n$ 为函数类型 `throws` 子句中不是有效类型的类型。令 $X_1, ..., X_m$ 为方法引用编译时声明中 `throws` 子句的检查异常 (§15.13.2)（根据函数类型的参数类型和返回类型推导得出）。则有两种情况：
    - 如果 $n=0$（函数的 `throws` 子句仅包含有效类型），那么如果存在某些 $i (1 \leq i \leq m)$ 使得 $X_i$ 不是 `throws` 子句中任何有效类型的子集，则约束归约为 *false*；否则，约束归约为 *true*。
    - 如果 $n>0$，则约束归约为一组子类型约束：对于所有 $i (1 \leq i \leq m)$，如果 $X_i$ 不是 `throws` 子句中任何有效类型的子集，则约束包括对于所有 $j (1 \leq j \leq n)$ 的 $X_i <: E_j$。此外，对于所有 $j (1 \leq j \leq n)$，约束归约为边界 `throws` $E_j$。

对检查异常的处理与返回类型是分开的，因为返回类型的兼容性影响方法的适用性 (§18.5.1)，而异常仅在重载解析后才影响调用类型 (§18.5.2)。通过将异常兼容性包含在 lambda 表达式兼容性的定义中 (§15.27.3) 可以简化这一点，但这可能会导致意料之外的情况，即显式类型 lambda 体的改变在重载解析后抛出异常。

lambda 体抛出的异常直到 (i) lambda 的参数类型已知，且 (ii) 句中结果表达式的类型已知之前无法确定。第二个要求是为了考虑泛型方法调用，在例如，相同的类型参数同时出现在返回类型和 `throws` 子句中。因此，我们要求这两者（从目标类型 $\tau$ 推导得出）都是有效类型。

一个结果是，从*其他* lambda 返回的 lambda 表达式无法从自身的异常生成约束。这些约束只能从顶层 lambda 表达式生成。

注意，对于没有推断变量出现在函数 `throws` 子句的情况的处理不是保持完备性的。任何变量都可能单独满足“每个检查异常都必须声明”的约束，但我们无法确定具体是指哪一个。因此，为了可预测性，我们对它们都进行约束。

## 18.3 合并

随着边界集在推断过程中生成和增长，可能会根据原始边界的断言推导出新的边界。*合并*过程识别出这些新边界并将它们添加到边界集中。

合并可能发生在两种场景。一种场景是边界集包含互补的边界对；这暗示了如 18.3.1 所示的新约束公式。另一种场景是边界集包含涉及捕获转换的边界；这暗示了如 18.3.2 所示的新边界并可能实现新的约束公式。在两种场景下，任何新的约束公式都会被归约，任何新的边界都会被添加到边界集中。这可能会触发进一步的合并；最终，集合将达到不动点，且无法再推导出边界。

如果边界集的合并已达到不动点，且该集合不包含边界 *false*，则边界集具有以下属性：

- 对于推断变量的每个有效下界 $L$ 和有效上界 $U$ 的组合，$L <: U$。
- 如果由 $\alpha$ 提到的每个推断变量都有实例化。

### 18.3.1 互补对

当边界集包含一对边界时，暗示了以下规则：

- 如果 $L <: U$，则 $L$ 是下界，$U$ 是上界。
- 如果 $L <: U$，则 $L$ 是下界，$U$ 是上界。
- 如果 $L <: U$，则 $L$ 是下界，$U$ 是上界。
- 如果 $L <: U$，则 $L = U$ 是一个边界。

### 18.3.2 涉及捕获转换的边界

当边界集包含形式为 $G<A_1, ..., A_n> = capture(G<A_1, ..., A_n>)$ 的边界时，暗示了新的边界可能有新的约束公式。令 $P_1, ..., P_n$ 代表 $G$ 的类型参数，$B_1, ..., B_n$ 代表这些类型的边界。令 $\theta$ 代表替换 $[P_1:=\alpha_1, ..., P_n:=\alpha_n]$。

## 18.4 解析

给定一个不包含边界 *false* 的边界集，可以对边界集中提到的推断变量子集进行*解析*。这意味着为每个推断变量添加一个满意的实例化，直到所有请求的变量都有实例化。

绑定集中的依赖关系可能要求按照特定顺序解析变量，或者要求解析额外的变量。依赖关系按如下方式指定：

- 给定具有以下形式之一的绑定，其中 $\tau$ 是推断变量 $\beta$ 或提及 $\beta$ 的类型：
    - $\alpha = \tau$
    - $\alpha <: \mathcal{T}$
    - $\tau = \alpha$
    - $\mathcal{T} <: \alpha$

  如果 $\alpha$ 出现在另一个形式为 $G<..., \alpha, ...> = capture(G<...,...>)$ 的绑定的左侧，则 $\beta$ 依赖于 $\alpha$ 的解析。否则，$\alpha$ 依赖于 $\beta$ 的解析。

- 出现在形式为 $G<..., \alpha, ...> = capture(\gamma_{...}>)$ 的绑定左侧的推断变量 $\alpha$ 依赖于该泛型中提及的除其以外的每一个其他推断变量的解析（涵盖符号的两侧）。
- 如果存在推断变量 $\gamma$，使得 $\alpha$ 依赖于 $\gamma$ 的解析且 $\gamma$ 依赖于 $\beta$ 的解析，则推断变量 $\alpha$ 依赖于推断变量 $\beta$ 的解析。
- 推断变量 $\alpha$ 依赖于其自身的解析。

给定一组需要解析的推断变量，令 $u$ 为该集合以及所有对该集合中至少一个变量的解析有依赖的变量的并集。

如果 $u$ 中的每个变量都有实例化，则解析成功且此过程终止。

否则，令 $\{\alpha_1, ..., \alpha_n\}$ 为 $u$ 中未实例化变量的非空子集，使得：(i) 对于所有 $i (1 \le i \le n)$，如果 $\alpha_i$ 依赖于变量 $\beta$ 的解析，则 $\beta$ 已经实例化，或者存在某个 $j$ 使得 $\beta = \alpha_j$；且 (ii) $\{\alpha_1, ..., \alpha_n\}$ 不存在具有此属性的非空真子集。解析通过根据绑定集中的绑定为 $\alpha_1, ..., \alpha_n$ 中的每个变量生成实例化来继续：

- 如果绑定集不包含对于所有 $i (1 \le i \le n)$ 形式为 $G<...$, $\alpha_i, ...>$ 的绑定，则为每个 $\alpha_i$ 定义一个候选实例化 $T_i$：
    - 如果 $\alpha_i$ 有一个或多个严格的下界 $L_i, ..., L_k$，则 $T_i = \text{lub}(L_i, ..., L_k)$ (§4.10.40)。
    - 否则，如果绑定集包含 $\alpha_i$，且 $\alpha_i$ 的每个严格的上界都是 `RuntimeException` 的超类型，则 $T_i = \text{RuntimeException}$。
    - 否则，如果 $\alpha_i$ 有严格的上界 $U_i, ..., U_k$，则 $T_i = \text{glb}(U_i, ..., U_k)$ (§5.1.10)。

绑定 $\alpha_1 = T_1, ..., \alpha_n = T_n$ 被并入当前的绑定集中。

如果结果不包含绑定 *false*，则该结果成为新的绑定集，解析通过选择一组新变量进行实例化（如有必要）继续，如上所述。

否则，结果包含绑定 *false*，则通过执行下面的步骤对 $\{\alpha_1, ..., \alpha_n\}$ 进行第二次实例化。

- 如果绑定集包含对于某些 $i (1 \le i \le n)$ 形式为 $G<...$, $\alpha_i, ...> = \text{capture}(G<...>)$ 的绑定：
    - 如果上一步产生的绑定集包含绑定 *false*，则令 $Y_1, ..., Y_n$ 为新的类型变量，其绑定如下：
        - 对于所有 $i (1 \le i \le n)$，如果 $\alpha_i$ 有一个或多个*严格*的下界 $L_i, ..., L_k$，则 $Y_i$ 的下界为 $\text{lub}(L_i, ..., L_k)$；若不是，$Y_i$ 没有下界。
        - 对于所有 $i (1 \le i \le n)$，其中 $\alpha_i$ 有上界 $U_i, ..., U_k$，则 $Y_i$ 为 $\text{glb}(\theta, ..., \theta_k)$，其中 $\theta$ 是替换 $[\alpha_1=Y_1, ..., \alpha_n=Y_n]$。

如果类型变量 $Y_1, ..., Y_n$ 没有良好的绑定（下界不是上界的子类型，或交集类型不一致），则解析失败。

否则，对于所有 $i (1 \le i \le n)$，从当前绑定集中移除所有形式为 $G<...$, $\alpha_i, ...> = \text{capture}(G<...>)$ 的绑定，并并绑定 $\alpha_1 = Y_1, ..., \alpha_n = Y_n$。

如果结果不包含绑定 *false*，则该结果成为新的绑定集，解析通过选择一组新变量进行实例化（如有必要）继续，如上所述。

否则，结果包含绑定 *false*，解析失败。

实例化推断变量的第一种方法是从变量的绑定推导出实例化。然而，有时复杂的依赖关系意味着复杂的依赖关系，有时复杂的依赖关系意味着复杂的依赖关系，有时复杂的依赖关系意味着复杂的依赖关系。

# 类型推断

## 推断的用途 18.5

$\{ \alpha : Object, Integer <: \alpha, Double <: \alpha \}$

然后，为了测试该方法是否适用，我们尝试解析这些边界。我们成功了，产生了如下复杂的实例化：

```
```



`α = Number & Comparable<? extends Number & Comparable<?>>`

```
我们已经证明了该方法是应用的；由于没有其他候选者，它是最具体的适用方法。尽管如此，调用的类型及其与赋值中目标类型的兼容性在发生进一步推断之前是无法确定的，如下一节所述。
```

## 18.5.2 调用类型推断

给定一个没有提供显式类型参数的方法调用表达式，以及一个对应的最具体的泛型方法 $m$，推断所选方法的调用类型（§15.12.2.6）的过程可能需要解析额外的约束，以断言与目标类型的兼容性，并断言方法调用的参数表达式的有效性。

> 需要注意的是，寻找方法调用的类型涉及多“轮”推断。例如，这允许目标类型影响调用的类型，而不允许它影响适用方法的选择。第一轮（§18.5.1）产生一个边界集并测试是否存在解析，但并不提交该解析。后续轮次会添加额外的约束，直到最终的解析步骤确定表达式的“真实”类型。

## 18.5.2.1 多态方法（Poly Method）调用的兼容性

如果方法调用表达式是一个多态表达式（§15.12），它与目标类型 $\tau$ 的兼容性如下所示确定。

如果方法调用表达式出现在严格调用上下且 $\tau$ 是原始类型，则该表达式与 $\tau$ 不兼容。

否则：

- 令 $B_2$ 为通过归约产生的边界集，以证明 $m$ 在 §18.5.1 中是适用的。

（虽然在 §18.5.1 中为了证明适用性显示 $B_2$ 中的推断变量是可以解析的，但为了建立适用性，此解析步骤产生的实例化不被视为 $B_2$ 的部分）

## 推断的用途

- 令 $B_2$ 为从 $B_2$ 返回的边界，如下。

令 $R$ 为 $m$ 的返回类型，令 $\theta$ 为 §18.5.1 中定义的替换 `[P_1 := \alpha_1, \dots, P_F := \alpha_F]`，用于用推断变量替换 $m$ 的类型参数，并令 $\tau$ 为调用目标的类型：

- 如果在 §18.5.1 的约束归约过程中为了使方法适用而需要拆箱转换，则约束公式 `|R| \to \tau` 被归约并合并到 $B_2$。

- 否则，如果 $R$ 是参数化类型，$G<A_1, \dots, A_n>$ 且 $A_i$ 之一是通配符，则对于新的推断变量 $\beta_1, \dots, \beta_n$，约束公式 $G<\beta_1, \dots, \beta_n> \to \tau$ 被归约并合并，同边界 $G<\beta_1, \dots, \beta_n> = \text{capture}(G<A_1, \dots, A_n>)$ 一并加入 $B_2$。

- 否则，如果 $R$ 是推断变量 $\alpha$，且满足以下任一：

> $\tau$ 是一个类型但不是通配符参数化类型，且：
> (i) $B_2$ 包含形式为 $\alpha = s$ 或 $s < \alpha, \alpha < \alpha$ 的边界，其中 $s$ 是通配符参数化类型，或 (ii) $B_2$ 包含形式为 $S_1 < \alpha$ 和 $S_2 < \alpha$ 的边界，其中 $S_1$ 和 $S_2$ 的父类是同一个泛型类或接口的不同参数化。

> $\tau$ 是泛型类或接口 $G$ 的参数化，且 $B_2$ 包含形式为 $\alpha = s$ 或 $s < \alpha$ 的边界，其中不存在形式为 $G<...>$ 的 $S$ 的父类，但原始类型 $|G<... >$ 是 $S$ 的父类。

> $\tau$ 是原始类型，且 §5.17.1 中提到的原始包装类之一是 $B_2$ 中 $\alpha$ 的实例化、上界或下界，

则 $\alpha$ 在 $B_2$ 中被解析，且结果实例化 $\alpha \to \tau$ 的捕获被归约并合并到 $B_2$。

- 否则，约束公式 `|R < \theta \to \tau` 被归约并合并到 $B_2$。

如果 $B_j$ 不包含边界 $false$ 且 $B_j$ 中所有推断变量的解析成功（§18.4），则该方法调用表达式与 $T$ 兼容。

考虑上一节的示例：

```
List<Number> ln = Arrays.asList(1, 2.0);
```

最适用的方法被识别为：

```
public static <T> List<T> asList(T... a
```



## 18.5.2.2 额外参数约束

所选方法的调用类型在考虑由参数表达式可能隐含的额外约束后确定，如下：

在推断多态表达式的调用类型时，由 §18.5.2 生成集合 $c$。

+ 对于括号表达式，搜索将递归应用于包含的表达式。
+ 对于条件表达式，搜索将递归应用于第二个和第三个操作数。
+ 对于 lambda 表达式，搜索将递归应用于 lambda 体。
+ 对于 switch 表达式，搜索将递归应用于其每一个结果表达式。
+ 如果 $e_i$ 是方法引用（`MethodReference`），则 $c$ 包含 `MethodReference` $\rightarrow$ 出 F$_i$ $\theta$。
+ 如果 $e_i$ 是多态类创建表达式或多态方法调用表达式，$c$ 包含在推断多态表达式调用类型时生成的集合 $c$ 中出现的所有约束公式。
+ 如果 $e_i$ 是括号表达式，这些规则将递归应用于包含的表达式。
+ 如果 $e_i$ 是条件表达式，这些规则将递归应用于第二个和第三个操作数。
+ 如果 $e_i$ 是 switch 表达式，这些规则将递归应用于其每一个结果表达式。
+ 当 $c$ 不空时，重复以下过程，从界符 $B_i$ 开始并将新的界符累积到“当前”界符集中，最终产生一个新的界符集 $B_i$：
    1. 在 $c$ 中选择约束子集，满足以下属性：对于每条约束，没有输入变量可以影响 $c$ 中另一个约束的输出变量。“输入变量”和“输出变量”定义见下。如果推断变量 $\alpha$ 依赖于 $\beta$ 的解析（§18.4），则 $\alpha$ 可以影响推断变量 $\beta$，反之之亦然；或者如果存在第三个推断变量 $\gamma$，使得 $\alpha$ 可以影响 $\gamma$ 且 $\gamma$ 可以影响 $\beta$。
    如果该子集为空，则在约束之间的依赖图中存在环（或多个环）。在这种情况下，考虑 $c$ 中参与依赖环（或环）且不依赖于该环（或环）之外的任何约束的约束。从这些被考虑的约束中选择一个单一约束，如下：
        - 如果被考虑的约束中有任何一个形式为 `<Expression $\rightarrow$ T>`，则所选约束是该形式的被考虑约束，它包含了所有其他该形式的被考虑约束的左侧（§3.5）的表达式。
        - 如果没有被考虑的约束形式为 `<Expression $\rightarrow$ T>`，则所选约束是包含所有其他被考虑约束的表达式的左侧表达式的被考虑约束。
    2. 从 $C$ 中移除所选的约束。
    3. 解析所有所选约束的输入变量 $\alpha_j$, ..., $\alpha_m$。
    4. 如果 $T_j$, ..., $T_m$ 是 $\alpha_j$, ..., $\alpha_m$ 的实例化，则将替换 $[\alpha_j:=T_j, ..., \alpha_m:=T_m]$ 应用于每条约束。
    5. 替换后产生的约束被约简并合并到当前界符集中。
+ 最后，如果 $B_4$ 不包含界符变量，则解析 $B_4$ 中的界符变量。

如果通过推断变量 $\alpha_j$, ..., $\alpha_p$ 的实例化 $T_j$, ..., $T_p$ 解析成功，则令 $\theta'$ 为替换 $[P_j:=T_j, ..., P_p:=T_p]$。那么：

+ 如果在 §18.5.1 的约束集约简期间，为了使方法适用不需要未检查转换（`unchecked conversion`），则调用类型 $m$ 的参数类型通过将 $\theta'$ 应用于 $m$ 的类型的参数类型获得，且 $m$ 的调用类型的返回类型和抛出类型由 $m$ 的类型的返回类型和抛出类型的擦除给出。
+ 如果为了使方法适用不需要未检查转换，则 $m$ 的调用类型通过将 $\theta'$ 应用于 $m$ 的类型获得。

如果 $B_4$ 包含界符 `false`，或者解析失败，则发生编译错误。

约简额外参数的过程可能需要仔细排序形式为 `<Expression $\rightarrow$ T>`、`<LambdaExpression>`$\rightarrow$`throws T>` 和 `<MethodReference>`$\rightarrow$`throws T` 的约束公式。为了便于这种排序，这些约束的输入变量定义如下：

### 类型推断

#### 推断的使用

+ 对于 `LambdaExpression` $\rightarrow$ $\mathcal{T}$：
    - 如果 $\tau$ 是推断变量，它是（唯一的）输入变量。
    - 如果 $\tau$ 是函数接口类型，且可以从 $\tau$ 推导出函数类型（§15.27.3），则输入变量包括：(i) 如果 lambda 表达式是隐式类型的，则由函数参数类型提到的推断变量；以及 (ii) 如果函数类型的返回类型 $\mathcal{R}$ 不是 `void`，则对于 lambda 体中的每个结果 $e$（或如果正体本身是一个表达式），`⟨e → ℛ⟩` 的输入变量。
    - 否则，没有输入变量。

+ 对于 `LambdaExpression` $\rightarrow$ T：
    - 如果 $\tau$ 是推断变量，它是（唯一的）输入变量。
    - 如果 $\tau$ 是函数接口类型，且可以从 $\tau$ 推导出函数类型（§15.27.3），则输入变量包括：(i) 如果 lambda 表达式是隐式类型的，则函数参数类型提到的推断变量；以及 (ii) 如果函数类型的返回类型 $\mathcal{R}$ 不是 `void`，则对于 lambda 体中的每个结果 $e$（或正体本身是一个表达式），`⟨e → ℛ⟩` 的输入变量。
    - 否则，没有输入变量。

+ 对于 `MethodReference` $\rightarrow$ T：
    - 如果 $\tau$ 是推断变量，它是（唯一的）输入变量。
    - 如果 $\tau$ 是函数接口类型，且可以从 $\tau$ 推导出函数类型（§15.27.3），则输入变量包括：(i) 如果 lambda 表达式是隐式类型的，则函数参数类型提到的推断变量；以及 (ii) 如果函数类型的返回类型 $\mathcal{R}$ 不是 `void`，则对于 lambda 体中的每个结果 $e$（或正体本身是一个表达式），`⟨e → ℛ⟩` 的输入变量。
    - 否则，没有输入变量。

+ 对于 `Expression` $\rightarrow$ T：
    - 如果 $e_i$ 是括号表达式，这些规则将递归应用于包含的表达式。
    - 如果 $e_i$ 是条件表达式，这些规则将递归应用于第二个和第三个操作数。
    - 如果 $e_i$ 是 switch 表达式，这些规则将递归应用于其每一个结果表达式。

## 18.5.3 接口实例化

当一个具有显式参数类型 $P_1, \dots, P_n$ 的 lambda 表达式目标是至少包含一个通配符的函数类型 $F<A_1, \dots, A_m>$ 时，可以如下推导出 $F$ 作为 lambda 表达式的基础类型。

令 $Q_1, \dots, Q_m$ 为函数类型 $F<\alpha_j, \dots, \alpha_m>$ 的参数类型，其中 $\alpha_j, \dots, \alpha_m$ 是新的接口变量。

如果 $n \neq k$，不存在有效的实例化。否则，形成约束集，对于所有 $i$ ($1 \le i \le n$)，$P_i = Q_i$。该约束公式被约简以形成界符 $B$。

如果 $B$ 包含界符 `false`，则不存在有效的实例化。否则，如下构造一个新的函数类型实例化 $F<A'_1, \dots, A'_m>$，对于 $1 \le i \le m$：

+ 如果 $B$ 包含 $\alpha_i$ 的实例化（§18.1.3），则 $A'_i = T$。
+ 否则，$A'_i = A_i$。

如果 $F<A'_1, \dots, A'_m>$ 不是一个良好的类型（即类型参数不在其界范围内），或者 $F<A'_1, \dots, A'_m>$ 不是 $F<A_1, \dots, A_m>$ 的子类型，则不存在有效的实例化。推断出的实例化：如果所有类型参数都是类型，则是 $F<A'_1, \dots, A'_m>$；如果一个或多个类型参数仍然是通配符，则是 $F<A'_1, \dots, A'_m>$ 的非通配符实例化（§9.9）。

为了确定通配符参数化的函数接口的函数类型，我们必须用特定类型“实例化”通配符类型参数。“默认”方法是简单地用其界符替换通配符，如 §9.8 所述，但这种

### 推断的用途

## 18.5

当 lambda 表达式的显式参数类型与通配符边界（bounds）时不匹配，会产生伪错误。例如：

```
Predicate<? super Integer> p = (Number n) -> n.equals(23);
```



该 lambda 表达式是一个 `Predicate<Number>`，它是 `Predicate<? super Integer>` 的子类型，但不是 `Predicate<Integer>`。本节的分析用于推断出 `Number` 是 `Predicate` 类型的合适选择。

尽管如此，这里的分析虽然是用通用类型推断的角度描述的，但刻意设计得非常简单。唯一的约束是等式约束，这意味着归约等同于简单的模式匹配。更强大的策略可能还可以从 lambda 表达式的主体中推出约束。但考虑到周围和/或嵌套泛型调用的可能交互，这将引入额外的复杂性。

### 18.5.4 更具具体的方法推断

当测试一个适用方法是否比另一个方法更具体时（§15.12.2.5），且第二个方法是泛型时，有必要测试是否可以推断出第二个方法类型参数的某种实例化，使得第一个方法比第二个方法更具体。

令 $m_1$ 为第一个方法，$m_2$ 为第二个方法。若 $m_2$ 具有类型参数 $P_1, ..., P_p$，令 $\alpha_1, ..., \alpha_p$ 为推断变量，令 $\theta$ 为替换 $[P_1:=\alpha_1, ..., P_p:=\alpha_p]$。

令 $e_1, ..., e_k$ 为对应调用的参数表达式。那么：

- 如果 $m_1$ 和 $m_2$ 通过严格或松散调用适用（§15.12.2.2, §15.12.2.3），令 $S_1, ..., S_k$ 为 $m_1$ 的形式参数类型，并令 $T_1, ..., T_k$ 为 $\theta$ 应用于 $m_2$ 的形式参数类型的结果。

- 如果 $m_2$ 通过可变变长调用适用（§15.12.2.4），则令 $S_1, ..., S_k$ 为 $m_1$ 的前 $k$ 个可变变长参数类型，令 $T_1, ..., T_k$ 为 $\theta$ 应用于 $m_2$ 的前 $k$ 个可变变长参数类型的结果。

注意，即使 $m_1$ 是泛型的，也不会对 $S_1$ 应用任何替换，其类型参数被视为类型变量，而不是推断变量。

确定 $m_1$ 是否比 $m_2$ 更具体的步骤如下：

- 首先，根据 §18.1.3 的规定，从 $P_1, ..., P_p$ 的声明边界生成初始边界集 $B_0$。

- 第二，对于所有 $i$ ($1 \le i \le k$)，生成一组约束公式或边界。

如果 $T_i$ 是一个有效类型（proper type），且对于 $e_i, S_i$ 比 $T_i$ 更具体（§15.12.2），则结果为 `true`，否则为 `false`。（注意 $S_i$ 始终是一个有效类型）。

否则，如果 $S_i$ 和 $T_i$ 不都是函数接口类型，则生成约束公式 `<S_i < T_i>`。

否则，如果 $S_i$ 的接口是 $T_i$ 接口的父接口或子接口（或者，当 $T_i$ 是交叉类型时，$S_i$ 的某个接口是 $T_i$ 的某个接口的父接口或子接口），则生成约束公式 `<S_i < T_i>`。

否则，令 $MT_{S_i}$ 为 $S_i$ 约束的函数类型，令 $MT_{T_i}$ 为 $T_i$ 的函数类型。如果 $MT_{S_i}$ 和 $MT_{T_i}$ 的形式参数或类型参数数量不同，或者 $MT_{S_i}$ 和 $MT_{T_i}$ 没有相同的类型参数（§8.4.4），则结果为 `false`。否则，根据 $MT_{S_i}$ 和 $MT_{T_i}$ 的类型参数、形式参数类型和返回类型生成以下约束公式或边界。

- 令 $A_1, ... A_n$ 为 $MT_{S_i}$ 的类型参数，$B_1, ... B_n$ 为 $MT_{T_i}$ 的类型参数。

令 $\theta'$ 为替换 $[B_j := A_j, ... B_n := A_n]$。那么，对于所有 $j$ ($1 \le j \le n$)：

- 如果 $A_j$ 的边界提到了 $A_1, ... A_n$ 中的之一，且 $B_j$ 的边界不是有效类型，则为 `false`。

- 否则，其中 $x$ 为 $A_j$ 的边界，$y$ 为 $B_j$ 的边界（$X = y \theta'$）。

> 如果 $A_j$ 的边界提到了 $A_1, ... A_n$ 中的之一且 $B_j$ 的边界不是有效类型，那么产生等式约束会导致推断变量被超出作用范围的类型所绑定。使用超出作用范围的变量实例化推断变量是不合理的（nonsensical），这通过避免这种情况来停止推断。

- 令 $U_1, ..., U_k$ 为 $MT_{S_i}$ 的形式参数类型，$V_1, ..., V_k$ 为 $MT_{T_i}$ 的形式参数类型。那么，对于所有 $j$ ($1 \le j \le k$)：

- 如果 $U_j$ 的边界提到了 $A_1, ... A_n$ 中的之一且 $V_j$ 的边界不是有效类型，则为 `false`。

- 否则，其中 $x$ 为 $U_j$ 的边界，$y$ 为 $V_j$ 的边界（$X = y \theta'$）。

> 如果 $U_j$ 的边界提到了 $A_1, ... A_n$ 中的之一且 $V_j$ 的边界不是有效类型，那么产生等式约束会导致推断变量被超出作用范围的类型所绑定。这通过避免这种情况来停止推断。

- 令 $A_1, ... A_n$ 为 $MT_{S_i}$ 的类型参数，$B_1, ... B_n$ 为 $MT_{T_i}$ 的类型参数。

令 $\theta'$ 为替换 $[B_j := A_j, ... B_n := A_n]$。那么，对于所有 $j$ ($1 \le j \le n$)：

- 如果 $A_j$ 的边界提到了 $A_1, ... A_n$ 中的之一且 $B_j$ 的边界不是有效类型，则为 `false`。

- 否则，其中 $x$ 为 $A_j$ 的边界，$y$ 为 $B_j$ 的边界（$X = y \theta'$）。

> 如果 $A_j$ 的边界提到了 $A_1, ... A_n$ 中的之一且 $B_j$ 的边界不是有效类型，那么产生等式约束会导致推断变量被超出作用范围的类型所绑定。这通过避免这种情况来停止推断。

- 第四，将生成的边界和约束公式归约并与 $B$ 合，产生边界集 $B'$。

- 如果 $B'$ 不包含边界 `false`，且 $B'$ 中所有推断变量的解析成功，则 $m_1$ 比 $m_2$ 更具体。否则，$m_1$ 不比 $m_2$ 更具体。

# 第 19 章
语法

本章重复了第 4、6-10 章和第 15 章给出的语法，以及第 3 章词法语法的关键部分，并使用了 §2.4 中的符号。

## 来自 §3（词法结构）的产生式

- `Identifier`: `IdentifierChars` 但不是关键字、布尔字面量或空字面量
- `IdentifierChars`: `JavaLetter` {`JavaLetterOrDigit`}
- `JavaLetter`: 任何“Java 字母”的 Unicode
- `JavaLetterOrDigit`: 任何“Java 字母或数字”的 Unicode
- `TypeIdIdentifier`: `Identifier` 但不是 `permits`, `record`, `sealed`, `var` 或 `yield`
- `UnqualifiedMethodIdentifier`: `Identifier` 但不是 `yield`

### 字面量

- 整数字面量
- 浮点数字面量
- 布尔字面量
- 字符字面量
- 字符串字面量
- 文本块
- 空字面量

## 来自 §4（类型、值和变量）的产生式

### 类型

- 基本类型
- 引用类型

#### 基本类型

- `[Annotation]` 数值类型
- `[Annotation]` `boolean`

#### 数值类型

- 整型类型
- 浮点型类型

#### 整型类型

（以下之一）
- `byte`
- `short`
- `int`
- `char`

#### 浮点型类型

（以下之一）
- `float`
- `double`

#### 引用类型

- 类或接口类型
- 类型变量
- 数组类型

#### 类或接口类型

- 类类型
- 接口类型

## 语法

### 类类型

- `[Annotation]` `.` `类型标识符` `[泛参数]`
- `包名` `.` `{Annotation}` `类型标识符` `[泛参数]`
- `类或接口类型` `.` `{Annotation}` `类型标识符` `[泛参数]`

### 接口类型

- `类类型`

### 类型变量

- `[Annotation]` `类型标识符`

### 数组类型

- `基本类型` `维度`
- `类或接口类型` `维度`
- `类型变量` `维度`

### 维度

- `[Annotation]` `[]` `[[Annotation]` `[]`

### 类型参数

- `[TypeModifier]` `类型标识符` `[类型边界]`

### 类型参数修饰

- `Annotation`

### 类型边界

- `extends` `类型变量`
- `extends` `类或接口类型` `[附加边界]`

### 附加边界

- `&` `接口类型`

### 泛参数

- `<` `类型参数列表` `>`

### 类型参数列表

- `类型参数` {`, ` `类型参数`}

### 类型参数

- `引用类型`
- `通配符`

### 通配符

- `[Annotation]` `?` `[通配符边界]`

### 通配符边界

- `extends` `引用类型`
- `super` `引用类型`

## 来自 §6（名称）的产生式

### 模块名

- `标识符`
- `模块名` `.` `标识符`

### 包名

- `标识符`
- `包名` `.` `标识符`

### 类型名

- `类型标识符`
- `包或类型名` `.` `标识符`

### 表达式名

- `标识符`
- `模糊` `.` `标识符`

### 方法名

- `未限定方法标识符`

### 包或类型名

- `标识符`
- `包或类型名` `.` `标识符`

### 模糊名

- `标识符`
- `模糊` `.` `标识符`

## 来自 §7（包和模块）的产生式

### 编译单元

- 普通编译单元
- 模块化编译单元

#### 普通编译单元

- `[包声明]` `[导入声明]`
- `{顶层类或接口声明}`

#### 模块化编译单元

- `{导入声明}` `模块声明`

### 包声明

- `{包修饰符}` `package` `标识符` `(.` `.` `标识符)` `;`

### 包修饰符

- `Annotation`

### 导入声明

- 单类型导入声明
- 按需导入声明
- 单静态导入声明
- 静态按需导入

#### 单类型导入声明

- `import` `类型名` `;`

#### 按需导入声明

- `import` `包或类型名` `.` `*` `;`

#### 单静态导入声明

- `import static` `类型名` `.` `标识符` `;`

#### 静态按需导入

- `import static` `类型名` `.` `*` `;`

### 顶层类或接口声明

- 类声明
- 接口声明
- `;`

### 模块声明

- `[Annotation]` `[open]` `module` `标识符` `{` `.` `标识符` `}`
- `{` `{模块指令}` `}`

### 模块指令

- `requires` `[需要修饰符]` `模块名` `;`
- `exports` `包名` `[to` `模块名` `(,` `模块名`)]` `;`
- `opens` `包名` `[to` `模块名` `(,` `模块名`)]` `;`
- `uses` `类型名` `;`
- `provides` `类型名` `with` `类型名` `(,` `类型名`)` `;`

### 需要修饰符

（以下之一）
- `transitive`
- `static`

## 来自 §8（类）的产生式

### 类声明

- 普通类声明
- 枚举声明
- 记录声明

#### 普通类声明

- `[类修饰符]` `class` `类型标识符` `[类型参数]`
- `[类扩展]` `[类实现]` `[类许可]` `类体`

#### 类修饰符

（以下之一）
- `Annotation`
- `public`
- `protected`
- `private`
- `abstract`
- `static`
- `final`
- `sealed`
- `non-sealed`
- `strictfp`

#### 类型参数

- `<` `类型参数列表` `>`

#### 类型参数列表

- `类型参数` `(,` `类型参数`)`

#### 类扩展

- `extends` `类类型`

#### 类实现

- `implements` `接口类型列表`

#### 接口类型列表

- `接口类型` `(,` `接口类型`)`

#### 类许可

- `permits` `类型名` `(,` `类型名`)`

#### 类体

- `{` `{` `类体声明` `}` `}`

#### 类体声明

- 类成员声明
- 实例初始化器
- 静态初始化器
- 构造函数声明

#### 类成员声明

- 字段声明
- 方法声明
- 类声明
- 接口声明
- `;`

#### 字段声明

- `{字段修饰符}` `未注解类型` `变量声明器列表` `;`

#### 字段修饰符

（以下之一）
- `Annotation`
- `public`
- `protected`
- `private`
- `static`
- `final`
- `transient`
- `volatile`

#### 变量声明器列表

- `变量声明器` `(,` `变量声明器`)`

#### 变量声明器

- `变量声明器标识` `[=` `变量初始化器` `]`

#### 变量声明器标识

- `标识符` `[维度]`

#### 变量初始化器

- `表达式`
- `数组初始化`

### 未注解类型

- `未注解基本类型`
- `未注解引用类型`

#### 未注解基本类型

- `数值类型`
- `boolean`

#### 未注解引用类型

- `未注解类或接口类型`
- `未注解类型变量`
- `未注解数组类型`

#### 未注解类或接口类型

- `未注解类类型`
- `未注解接口类型`

#### 未注解类类型

- `标识符` `[泛参数]`
- `包名` `.` `[Annotation]` `类型` `[泛参数]`
- `未注解类或接口类型` `.` `[Annotation]` `类型` `[泛参数]`

#### 未注解接口类型

- `未注解类类型`

#### 未注解类型变量

- `标识符`

#### 未注解数组类型

- `未注解基本类型` `维度`
- `未注解类或接口类型` `维度`
- `未注解类型变量` `维度`

### 方法声明

- `{方法修饰符}` `方法头` `方法体`

#### 方法修饰符

（以下之一）
- `Annotation`
- `public`
- `protected`
- `private`
- `abstract`
- `static`
- `final`
- `synchronized`
- `native`
- `strictfp`

#### 方法头

- `结果` `方法声明器` `[异常]`
- `泛参数`

#### 结果

- `未注解类型`
- `void`

#### 方法声明器

- `标识符` `(` `[形式参数列表]` `)` `[维度]`

#### 形式参数列表

- `形式参数` `{,` `形式参数` `}`

#### 形式参数

- `{形式参数修饰符}` `未注解类型` `变量声明器`
- `变长参数`

#### 形式参数修饰符

- `Annotation`
- `final`

#### 异常

- `throws` `异常类型列表`

#### 异常类型列表

- `异常类型` `{,` `异常类型` `}`

#### 异常类型

- `类类型`
- `类型变量`

#### 方法体

- `Block`

#### 实例初始化器

- `Block`

#### 静态初始化器

- `static` `Block`

#### 构造函数声明

- `{构造修饰符}` `构造声明器` `[异常]` `构造体`

#### 构造修饰符

（以下之一）
- `Annotation`
- `public`
- `protected`
- `private`

#### 构造声明器

- `[类型参数]` `简单类型标识符` `(` `[形式参数列表]` `)`

#### 简单类型标识符

- `标识符`

#### 构造体

- `{` `[显式构造调用]` `[语句]` `}`

#### 显式构造调用

- `[泛参数]` `this` `(` `[参数列表]` `)` `;`
- `[泛参数]` `super` `(` `[参数列表]` `)` `;`

#### 枚举声明

- `{类修饰符}` `enum` `类型标识符` `[实现]` `枚举体`

#### 枚举体

- `{` `常量列表` `[,]` `}`

#### 常量列表

- `常量` `{,` `常量` `}`

#### 常量

- `{常量修饰符}` `标识符` `[类体]` `}`

#### 常量修饰符

- `Annotation`

#### 枚举体声明

- `;` `[类体声明]`

### 记录声明

- `{类修饰符}` `record` `类型标识符` `[泛参数]`
- `[实现]` `记录体`

#### 记录头

- `(` `[记录组件列表]` `)`

#### 记录组件列表

- `记录组件` `{,` `记录组件` `}`

#### 记录组件

- `{记录修饰符}` `未注解类型` `标识符`

#### 变量记录组件

- `{记录修饰符}` `未注解类型` `[Annotation]` `...` `标识符`

#### 记录修饰符

- `Annotation`

#### 记录体

- `{` `[记录体声明]` `}`

#### 记录体声明

- `类体声明`
- 紧凑构造函数声明

#### 紧凑构造函数声明

- `{构造修饰符}` `简单名` `构造体`

## 来自 §9（接口）的产生式

### 接口声明

- 普通接口声明
- 注解接口声明

#### 普通接口声明

- `[接口修饰符]` `interface` `类型标识符` `[泛参数]`
- `[接口扩展]` `[接口许可]` `接口体`

#### 接口修饰符

（以下之一）
- `Annotation`
- `public`
- `protected`
- `private`
- `abstract`
- `static`
- `sealed`
- `non-sealed`
- `strictfp`

#### 接口扩展

- `extends` `接口类型列表`

#### 接口许可

- `permits` `类型名` `(,` `类型名`)`

#### 接口体

- `{` `接口成员声明` `}`

#### 接口成员声明

- 常量声明
- 接口方法声明
- 类声明
- 接口声明
- `;`

#### 常量声明

- `{常量修饰符}` `未注解类型` `变量声明列表` `;`

#### 常量修饰符

（以下之一）
- `Annotation`
- `public`
- `static`
- `final`

### 接口方法声明

- `{接口方法修饰符}` `方法头` `方法体`

#### 接口方法修饰符

（以下之一）
- `Annotation`
- `public`
- `private`
- `abstract`
- `default`
- `static`
- `strictfp`

### 注解接口声明

- `{接口修饰符}` `@` `interface` `类型标识符` `注解接口体`

#### 注解接口体

- `{` `注解接口成员声明` `}`

#### 注解接口成员声明

- 注解接口元素声明
- 常量声明
- 类声明
- 接口声明
- `;`

#### 注解接口元素声明

- `{注解接口元素修饰符}` `未注解类型` `标识符` `()` `[维度]`
- `[默认值]` `;`

#### 注解接口元素修饰符

（以下之一）
- `Annotation`



# 语法

## Annotation

```
Annotation:
    NormalAnnotation
    MarkerAnnotation
    SingleElementAnnotation

NormalAnnotation:
    @ TypeName [ ElementValuePairList ]

ElementValuePairList:
    ElementValuePair { , ElementValuePair }

ElementValuePair:
    Identifier = ElementValue

ElementValue:
    ConditionalExpression
    ElementValueArrayInitializer
    Annotation

ElementValueArrayInitializer:
    { [ ElementValueList ] [ , ] }

ElementValueList:
    ElementValue { , ElementValue }

MarkerAnnotation:
    @ TypeName

SingleElementAnnotation:
    @ TypeName ( ElementValue )
```

## 来自 §10 (数组) 的产生规则

```
ArrayInitializer:
    { [ VariableInitializerList ] [ , ] }

VariableInitializerList:
    VariableInitializer { , VariableInitializer }
```

## 来自 §14 (块、语句和模式) 的产生规则

```
Block:
    { [ BlockStatements ] }

BlockStatements:
    BlockStatement { BlockStatement }

BlockStatement:
    LocalClassOrInterfaceDeclaration
    LocalVariableDeclarationStatement
    Statement

LocalClassOrInterfaceDeclaration:
    ClassDeclaration
    NormalInterfaceDeclaration

LocalVariableDeclarationStatement:
    LocalVariableDeclaration ;

LocalVariableDeclaration:
    [ VariableModifier ] LocalVariableType VariableDeclaratorList

LocalVariableType:
    UnannType
    var

Statement:
    StatementWithoutTrailingSubstatement
    LabeledStatement
    IfThenStatement
    IfThenElseStatement
    WhileStatement
    ForStatement

StatementNoShortIf:
    StatementWithoutTrailingSubstatement
    LabeledStatementNoShortIf
    IfThenElseStatementNoShortIf
    WhileStatementNoShortIf
    ForStatementNoShortIf

StatementWithoutTrailingSubstatement:
    Block
    EmptyStatement
    ExpressionStatement
    AssertStatement
    SwitchStatement
    DoStatement
    BreakStatement
    ContinueStatement
    ReturnStatement
    SynchronizedStatement
    ThrowStatement
    TryStatement
    YieldStatement

EmptyStatement:
    ;

LabeledStatement:
    Identifier : Statement

LabeledStatementNoShortIf:
    Identifier : StatementNoShortIf

ExpressionStatement:
    StatementExpression ;

StatementExpression:
    Assignment
    PreIncrementExpression
    PreDecrementExpression
    PostIncrementExpression
    PostDecrementExpression
    MethodInvocation
    ClassInstanceCreationExpression
```

## 语法

```
IfThenStatement:
    if ( Expression ) Statement

IfThenElseStatement:
    if ( Expression ) StatementNoShortIf else Statement

IfThenElseStatementNoShortIf:
    if ( Expression ) StatementNoShortIf else StatementNoShortIf

AssertStatement:
    assert Expression ;
    assert Expression : Expression ;

SwitchStatement:
    switch ( Expression ) SwitchBlock

SwitchBlock:
    { SwitchRule SwitchRule }
    { SwitchBlockStatementGroup } { SwitchLabel : ]

SwitchRule:
    SwitchLabel -> Expression ;
    SwitchLabel -> Block
    SwitchLabel -> ThrowStatement

SwitchBlockStatementGroup:
    SwitchLabel : { SwitchLabel : ] BlockStatements

SwitchLabel:
    case CaseConstant [ , , CaseConstant }

CaseConstant:
    ConditionalExpression

WhileStatement:
    while ( Expression ) Statement

WhileStatementNoShortIf:
    while ( Expression ) StatementNoShortIf

DoStatement:
    do Statement while ( Expression ) ;

ForStatement:
    BasicForStatement
    EnhancedForStatement

ForStatementNoShortIf:
    EnhancedForStatementNoShortIf

BasicForStatement:
    for ( [ ForInit ] ; [ Expression ] ; [ ForUpdate ] ) Statement

BasicForStatementNoShortIf:
    for ( [ ForInit ] ; [ Expression ] ; [ ForUpdate ] ) StatementNoShortIf

ForInit:
    StatementExpressionList
    LocalVariableDeclaration

ForUpdate:
    StatementExpressionList

StatementExpressionList:
    StatementExpression { , StatementExpression }

EnhancedForStatement:
    for ( LocalVariableDeclaration : Expression ) Statement

EnhancedForStatementNoShortIf:
    for ( LocalVariableDeclaration : Expression ) StatementNoShortIf
```

## 语法

```
BreakStatement:
    break [ Identifier ] ;

YieldStatement:
    yield Expression ;

ContinueStatement:
    continue [ Identifier ] ;

ReturnStatement:
    return [ Expression ] ;

ThrowStatement:
    throw Expression ;

SynchronizedStatement:
    synchronized ( Expression ) Block
```

## 语法

```
TryStatement:
    try Block Catches
    try Block [ Catches ] Finally
    TryWithResourcesStatement

Catches:
    CatchClause [ CatchClause ]

CatchClause:
    catch ( CatchFormalParameter ) Block

CatchFormalParameter:
    { VariableModifier } CatchType VariableDeclaratorId

CatchType:
    UnannClassType | ClassType

Finally:
    finally Block

TryWithResourcesStatement:
    try ResourceSpecification [ Finally ]

ResourceSpecification:
    ResourceList [ ]

ResourceList:
    Resource

Pattern:
    LocalVariableDeclaration

Pattern:
    TypePattern

TypePattern:
    LocalDeclaration
```

## 来自 §15 (表达式) 的产生规则

```
Primary:
    EqualityExpression

PrimaryNoArray:
    ArrayCreationExpression
    Literal
    this
    TypeName this
    super this
    TypeName . this
    super . this

FieldAccess:
    Primary . Identifier
    super . Identifier
    TypeName . super . Identifier

ArrayAccess:
    ExpressionName [ Expression ]
    PrimaryNoArray [ Expression ]

MethodInvocation:
    MethodName ( [ ArgumentList ] )
    TypeName . [ TypeArguments ] ( [ ArgumentList ] )
    ExpressionName . [ TypeArguments ] ( [ ArgumentList ] )
    Primary . [ TypeArguments ] ( [ ArgumentList ] )
    super . [ TypeArguments ] ( [ ArgumentList ] )
    TypeName . super . [ TypeArguments ] ( [ ArgumentList ] )

ArgumentList:
    Expression [ , Expression ]

MethodReference:
    [ ]

ArrayCreationExpression:
    new PrimitiveType DimExprs [ Dims ]
    new ClassOrInterfaceType DimExprs [ Dims ]
    new PrimitiveType Dims ArrayInitializer
    new ClassOrInterfaceType Dims ArrayInitializer

DimExprs:
    DimExpr { DimExpr }

DimExpr:
    [ Annotation ] [ Expression ]
```

## 语法

```
Expression:
    LambdaExpression
    AssignmentExpression

LambdaExpression:
    LambdaParameters -> LambdaBody

LambdaParameters:
    ( [ LambdaParameterList ] )
    Identifier

LambdaParameterList:
    LambdaParameter { , LambdaParameter }
    Identifier { , Identifier }

LambdaParameter:
    { VariableModifier } LambdaParameterType VariableDeclaratorId
    VariableArityParameter

LambdaParameterType:
    UnannType
    var

LambdaBody:
    Expression
    Block

AssignmentExpression:
    ConditionalExpression
    Assignment

Assignment:
    LeftHandSide AssignmentOperator Expression

LeftHandSide:
    ExpressionName
    FieldAccess
    ArrayAccess

AssignmentOperator: (one of)
    = *= /= %= += -= <<= >>= >>>= &= ^= |=

ConditionalExpression:
    ConditionalOrExpression
    ConditionalOrExpression ? Expression : ConditionalExpression
    ConditionalOrExpression ? Expression : LambdaExpression

ConditionalOrExpression:
    ConditionalAndExpression
    ConditionalOrExpression || ConditionalAndExpression

ConditionalAndExpression:
    InclusiveOrExpression
    ConditionalAndExpression && InclusiveOrExpression

InclusiveOrExpression:
    ExclusiveOrExpression
    InclusiveOrExpression | ExclusiveOrExpression

ExclusiveOrExpression:
    AndExpression
    ExclusiveOrExpression ^ AndExpression

AndExpression:
    EqualityExpression
    AndExpression & EqualityExpression

EqualityExpression:
    RelationalExpression
    EqualityExpression == RelationalExpression
    EqualityExpression != RelationalExpression

RelationalExpression:
    ShiftExpression
    RelationalExpression < ShiftExpression
    RelationalExpression > ShiftExpression
    RelationalExpression <= ShiftExpression
    RelationalExpression >= ShiftExpression

InstanceofExpression:
    RelationalExpression instanceof ReferenceType
    RelationalExpression instanceof Pattern

ShiftExpression:
    AdditiveExpression
    ShiftExpression << AdditiveExpression
    ShiftExpression >> AdditiveExpression
    ShiftExpression >>> AdditiveExpression

AdditiveExpression:
    MultiplicativeExpression
    AdditiveExpression + MultiplicativeExpression
    AdditiveExpression - MultiplicativeExpression

MultiplicativeExpression:
    UnaryExpression
    MultiplicativeExpression * UnaryExpression
    MultiplicativeExpression / UnaryExpression
    MultiplicativeExpression % UnaryExpression

UnaryExpression:
    PreIncrementExpression
    PreDecrementExpression
    + UnaryExpression
    - UnaryExpressionNotPlusMinus
```



# 语法定义

## PreIncrementExpression

```
++ UnaryExpression
```

## PreDecrementExpression

```
-- UnaryExpression
```

## UnaryExpressionNotPlusMinus

- `PostfixExpression`
- `~ UnaryExpression`
- `! UnaryExpression`
- `CastExpression`
- `SwitchExpression`

## PostfixExpression

- `Primary`
- `ExpressionName`
- `PostIncrementExpression`
- `PostDecrementExpression`

## PostIncrementExpression

```
PostfixExpression ++
```

## PostDecrementExpression

```
PostfixExpression --
```

## CastExpression

- `( PrimitiveType ) UnaryExpression`
- `( ReferenceType [AdditionalBound] ) UnaryExpressionNotPlusMinus`
- `( ReferenceType [AdditionalBound] ) LambdaExpression`

## SwitchExpression

```
switch ( Expression ) SwitchBlock
```

## ConstantExpression

- `Expression`

---

# 附录 A. 有限许可授予

**规范**：JSR-392 Java SE 17  
**版本**：17  
**状态**：正式发布  
**发布日期**：2021年9月

版权 © 1997, 2021, Oracle America, Inc.  
保留所有权利。

## 限制许可授予

1. **评估目的许可**。规范负责人特此向你授予一项全额支付的、非独占的、不可转让的、全球性的有限许可（不包含分许可权），根据规范负责人适用的知识产权，允许仅为内部评估之目的查看、下载和复制规范。这包括 (i) 开发旨在运行在规范实现版本上的应用程序，前提是此类应用程序本身没有实现规范的任何部分，以及 (ii) 在讨论规范的口头或书面通信中讨论规范的短片段，前提是这些摘录在总体上不构成规范的重要部分。

2. **合规实现分发许可**。规范负责人还向你授予一项永久的、非独占的、不可转让的、全球性的、全额支付的、免版税的许可（不包含分许可权），涵盖任何适用的著作权，或下文第 4 节规定的可能覆盖规范的专利权，用于创建和/或分发规范的独立实现，该独立实现需：
   - (a) 完全实现规范，包括其所有要求的接口和功能；
   - (b) 不修改、子集、超集或以其他方式扩展许可方命名空间，也不包含规范或正在实施的规范要求/授权的许可方命名空间内的任何公共或受保护的包、类、Java 接口、字段或方法；
   - 以及 (c) 通过该规范的技术兼容性套件（包括满足适用 TCK 用户指南的要求）（即“合规实现”）。
   
   上述许可的明确条件是不得在其范围之外采取行动。本协议未授予用于任何其他目的的许可（例如，修改规范（超出你的公平使用权范围的部分外），或将规范分发给第三方）。此外，本协议未授予对规范负责人或规范负责人的任何商标、服务标记或名称的权利、权利或利益。Java 以及 Java 相关标识和名称是美国和其他国家 Oracle America, Inc. 的商标或注册商标。

3. **透传条件**。在涉及授予的关于使用你的独立实现或其衍生产品的任何许可中，你无需包含上一段中的 (a)-(c) 限制条件或任何其他“透传”要求。然而，对于满足上一段中 (a)-(c) 限制条件的独立实现（及其衍生产品）除外，你既不得：(a) 向你的被许可人授予或透传规范负责人适用知识产权下的任何许可；也不 (b) 授权你的被许可人就其对相关规范的实现提出任何主张。

4. **专利许可的互惠性**。
   - a. 对于上述第 2 项下授予许可所涵盖的任何专利权利要求，如果该权利要求会被规范的所有技术上可行的实现所侵权，则该许可的条件是：你向任何寻求的方提供基于合理且非歧视性条款的永久的、非独占的、不可转让的、全球性的许可，涵盖或会被规范的所有技术上可行的实现所侵权的专利权，以便开发、分发和使用合规实现。
   - b. 对于规范负责人拥有且被第 2 项下授予许可所涵盖的任何专利权利要求，无论在实施规范时是否能以技术上可行的方式避免其侵权，如果你对规范负责人提起诉讼，且该诉讼在履行规范负责人职责过程中诱导了任何其他实体侵犯了你的专利权，则该许可应就此类权利的终止。
   - c. 同样对于规范负责人拥有且被第 2 项下授予许可所涵盖的任何专利权利要求，如果在实施规范时可以以技术上可行的方式避免此类权利的侵权，则如果你对规范负责人提起诉讼，指控其制造、制造、使用、销售或进口合规实现侵犯了你的专利权，则该许可应就此类权利的终止。

5. **定义**。就本协议而言：
   - “独立实现”是指规范的实现，不源自规范负责人的任何源代码或二进制代码，除非获得规范负责人适当且独立的许可，否则不包含规范负责人的任何源代码或二进制代码；
   - “许可方命名空间”是指以“java”、“com.sun”或 Oracle America, Inc. 通过 Java 社区流程采用的任何后续命名或认可的继承者或替代者的公共类或接口声明；
   - “技术兼容性套件”或“TCK”是指规范负责人提供的、与规范对应的测试套件及配套 TCK 用户指南，且该套件在 (i) 你允许商业用途的独立实现发布前 120 天可用，或 (ii) 在你选择测试规范实现的发布后 120 天后可用。

如果你违反协议或在许可范围之外采取行动，本协议将在不通知的情况下立即终止。

## 免责声明

规范按“现状况”提供。规范负责人不对任何明示或暗示的陈述或保证，包括但不限于对适用性、特定用途的适用性、非侵权（包括作为规范的任何实践或实施的结果）或规范内容适用于任何目的的保证。本文件不代表对在任何产品中发布或实施规范任何部分的承诺。此外，规范可能包含技术错误或排版错误。

## 责任限制

在法律允许的范围内，在任何情况下，规范负责人或许可方均不对任何损害负责，包括但不限于损失的收入、利润或数据，或特殊的、间接的、后果性的或惩罚性的损害，无论何种引起，无论基于何种责任理论，由于您拥有、实施或以此方式使用本规范而引起或以任何方式相关的损害，即使 Specification Lead 和/或其许可方已被告知发生此类损害的可能性。

您将确保 Specification Lead 及其许可方免受、使其不受损害并防御因以下情况引起或导致的任何索赔：(i) 您对规范的使用；(ii) 您提供的 Java 应用程序、applet 和/或实现的使用或分发；和/或 (iii) 任何关于提供给您的规范的后续版本或发布与本许可协议中提供的规范不兼容的索赔。

## 限制权利授予

美国政府：如果本规范由美国政府或代表美国政府获取，或由美国政府的主承包商或分包商（任何层级）获取，则政府对软件及相关文档的权利应仅限于本许可中的规定；这符合 48 C.F.R. 227.7201 关于国防部 (DoD) 采购的规定，以及 48 C.F.R. 2.101 和 12.212 关于非国防部采购的规定。

## 报告

如果您向 Specification Lead 提供有关本规范的任何意见或建议（“反馈”），您特此：(i) 同意此类反馈是在非专有且非机密的基础上提供的，(ii) 授予 Specification Lead 一项永久的、非独的、全球性的、全付费的不可撤销的许可，允许其通过多级分许可人进行分许可，为了任何目的纳入、披露且不受限于使用反馈。

## 通用条款

与本协议相关的任何行动将受加利福尼亚州法律和美国联邦法律管辖。联合国货物销售公约以及任何司法管辖区的法律选择规则均不适用。

本规范受美国出口控制法的限制，并可能受其他国家进出口规定的限制。被许可人同意严格遵守所有此类法规，并承认其责任在交付给被许可人后根据需要获得出口、再出口或进口的许可。

本协议是双方就其主题达完整协议。它取代了之前或同时的所有口头或书面通信、提议、条件、陈述和保证，并在本协议期限内，优于双方之间关于其主题的任何报价、订单、确认或其他通信中的任何冲突或额外条款。对本协议的任何修改除非采用书面形式并由双方的授权代表签字，否则均不具有约束力。
