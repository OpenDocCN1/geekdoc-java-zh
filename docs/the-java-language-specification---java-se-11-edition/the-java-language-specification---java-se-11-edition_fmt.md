
# Java® 语言规范 - Java SE 11 版

- 14.13.1 do 语句的异常完成 451
- 14.20 try 语句 467
- 17.5 final 字段语义 684

包可以被分组为模块，模块作为构建极大型程序的构建组件。模块的声明指定了编译和运行其所属包中的代码时需要哪些其他模块（以及相应的包、类和接口）。

```
class Test {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++)
            System.out.print(i == 0 ? args[i] : " " + args[i]);
        System.out.println();
    }
}
```

在安装了 Oracle JDK 的机器上，将存储在 `Test.java` 文件中的该类可以通过以下命令进行编译和执行：

```
javac Test.java
java Test Hello, world.
```

产生如下输出：

```
Hello, world.
```

在本规范中，我们引用源自 Java SE Platform API 的类和接口。每当我们使用单个标识符 `$N$` 引用类或接口（除示例中声明的除外）时，指的是 `$java.lang$` 包中的类或接口 `$N$`。对于来自 `$java.lang$` 其他包的类或接口，我们使用规范名（§6.7）。

旨在澄清规范的非规范性信息以较小的、缩进的文本给出。

> 此部分为非规范性信息。它提供了直觉、原理、建议、示例等。

Java 编程语言的类型系统偶尔依赖于*替换*（substitution）的概念。符号 `$[F_i:=T_i, \dots, F_n:=T_n]$` 表示对于 `$1 \le i \le n$`，将 `$F_i$` 替换为 `$T_i$`。

如上所述，本规范经常引用 Java SE Platform API 的类。特别是某些类与 Java 编程语言有特殊关系。例如 `Object`、`Class`、`String`、`Thread` 等类，以及包 `java.lang.reflect` 中的接口等。本规范制约了此类类和接口的行为，但没有为它们提供完整的规范。读者请参阅 Java SE Platform API 文档。

因此，本规范没有详细描述反射。许多语言结构在核心反射 API (`java.lang.reflect`) 和语言模型 API (`javax.lang.model`) 中均有对等物，但这些通常不在此处讨论。例如，当我们列出创建对象的方法时，通常不包含通过核心反射 API 实现此操作的方法。读者应当注意这些额外机制，即使它们在文中未提及。

欢迎读者将《Java 语言规范》中发现的技术性错误和歧义之处报告至 `jls-jvms-spec-comments@openjdk.net`。

关于 `javac`（Java 编程语言的参考编译器）的行为，特别是其对本规范的遵循情况的问题，可以发送至 `compiler-dev@openjdk.java.net`。

Apple Computer. Dylan Reference Manual. Apple Computer Inc., Cupertino, California. 1995年9月29日.

Bobrow, Daniel G., Linda G DeMichiel, Richard P. Gabriel, Sonya E. Keene, Gregor Kiczzales, and David A. Moon. Common Lisp Object System Specification, X3J13 Document 88-002R; 1988年6月; 见 Steele, Guy. Lisp: The Language, 2nd ed. Digital Press, 1990, ISBN 1-55558-041-6, 770-864.

Ellis, Margaret A., and Bjarne Stroustrup. The Annotated C++ Reference Manual. Addison-Wesley, Reading, Massachusetts, 1990年, 1992年10月重印修正, ISBN 0-201-51459-1.

## 语法

本章描述了用于定义程序结构的上下文语法。

*上下文语法*由若干*产生式*（productions）组成。每个产生式有一个称为非终符（nonterminal）的抽象符号作为左部，以及一个或多个非终符和终端符号的序列作为右部。

Java 编程语言的*词法语法*在 §3（词法结构）中给出。该语法的终端符号是 Unicode 字符集。它定义了一组产生式，从目标符号*输入*（§3.5）开始，描述了 Unicode 字符序列（§3.1）如何转换为输入元素。

这些输入元素在舍弃空白（§3.6）和注释（§3.7）后，构成了句法语法的终端符号，并被称为*标记*（tokens）。这些标记是 Java 编程语言的标识符（§3.8）、关键字（§3.9）、字面量（§3.10）、分隔符（§3.11）和运算符（§3.12）。

Java 编程语言的句法语法位于第4、6-10以及15章。该语法的终端符号是由词法分析定义的标记。它定义了一组产生式，从目标符号 `CompilationUnit`（§7.3）开始，描述了标记序列如何形成句法正确的程序。

为了方便起见，句法语法集中在第19章给出。

终端符号在词法和句法语法的产生式中以等宽字体显示，在本规范的文中直接引用此类符号时也是如此。这些符号在程序中应与书写形式完全一致。

非终符符号以斜体显示。非终符的定义由被定义的非终符名称引入，后跟冒号。随后，该非终符的一个或多个替代定义在后续行给出。

例如，上述 `IfThenStatement` 的句法产生式说明非终符 `IfThenStatement` 代表标记 `if`、紧接一个左括号标记、一个 `Expression`、紧接一个右括号标记，以及一个 `Statement`。

产生式右侧的语法 `[x]` 表示 `x` 出现零次或多次。

例如，产生式：

```
```

产生式右侧的 `[x]` 表示 `x` 零次或一次。也就是说，`x` 是一个可选符号。包含可选符号的替代方案实际上定义了两个分支：一个省略该可选符号，另一个包含该符号。

这意味着：

```
BreakStatement:
```

是以下内容的简便缩写：

```
BreakStatement:
break;
break Identifier;
```

另一个例子，它意味着：

```
BasicStatement:
for ([ForInit] ; [Expression] ; [ForUpdate]) Statement
```

是以下内容的简便缩写：

```
BasicStatement:
for ( [Expression] ; [ForUpdate] ) Statement
for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement
```

这反又是以下内容的缩写：

```
BasicStatement:
for ( ; [ForUpdate] ) Statement
for ( Expression ; [ForUpdate] ) Statement
for ( [ForInit] ; ; [ForUpdate] ) Statement
for ( [ForInit] ; Expression ; [ForUpdate] ) Statement
```

这反又是以下内容的缩写：

```
BasicForStatement:
for ( ; ) Statement
for ( ; ForUpdate ) Statement
for ( ; Expression ; ) Statement
for ( Expression ; ForUpdate ) Statement
for ( Fornit ; ) Statement
for ( Fornit ; ForUpdate ) Statement
for ( Fornit ; Expression ) Statement
for ( Expression ; ForUpdate ) Statement
```

因此非终符 `BasicForStatement` 实际上有八种替代右侧。

非常长的右侧可以通过清晰地缩进第二行并在第二行继续。

例如，语法文法包含此产生式：

```
NormalClassDeclaration:
[ClassModifier] class TypeIdentifier[TypeParameters]
[Superclass][SuperInterfaces] ClassBody
```

它为非终符 `NormalClassDeclaration` 定义了一个右侧。

产生式右侧的短语 (**其中之一** ) 表示后续的一行或或几行中的每个符号都是一种替代定义。

例如，词法文法包含此产生式：

```
ZeroToThree:
(one of)
0 1 2 3
```

这仅仅是以下内容的简便缩写：

```
ZeroToThree:
0
1
2
3
```

当产生式中的替代方案看起来像一个标记时，它代表组成此类标记的字符序列。

因此，产生式：

```
BooleanLiteral:
(one of)
true false
```

是以下内容的简写：

```
BooleanLiteral:
true
false
```

产生式的右侧可以使用短语 "but not" 然后指示要排除的扩展来指定某些扩展是不允许的。

例如：

```
Identifier:
IdentifierChars but not a Keyword or BooleanLiteral or NullLiteral
```



最后，一些非终符通过正体的叙述性短语定义，在这种情况下列出所有替代方案是不切行的。

例如：

```
RawInputCharacter:
any Unicode character
```

# 词法结构

本章规定了 Java 编程语言的词法结构。

程序使用 Unicode 字符集编写。关于该字符集及其相关字符编码的信息可以在 http://www.unicode.org/ 找到。

Java SE 平台随着 Unicode 标准的演进进行跟踪。特定发布版本使用的 Unicode 精确版本在 `Character` 类的文档中指定。

Unicode 标准最初被设计为固定宽度的 16 位字符编码。从那时起发生了变化，允许表示需要超过 16 位的字符。现在合法代码点的范围现在是 U+0000 到 U+10FFFF，使用 U+FFFF 表示法。代码点大于 U+FFFF 的字符被称为补充字符。为了仅使用 16 位单位表示完整的字符范围，Unicode 标准定义了 16 位单位的对，称为代理对。第一个单元称为高代理项 (U+D800 到 U+DBFF)，第二个称为低代理项 (U+DC00 到 U+FFFF)。

词法翻译产生的 Unicode 字符被还原为输入元素序列（§3.5），这些是空白符（§3.6）、注释（§3.7）和标记。标记是语法文法中的标识符（§3.8）、关键字（§3.9）、字面量（§3.10）、分隔符（§3.11）和运算符（§3.12）。

## 3.4 行终止符

Java 编译器通过识别行终止符将 Unicode 输入字符序列划分为行。

- 行终止符 (LineTerminator):
  - ASCII LF 字符，也称为“换行”（newline）
  - ASCII CR 字符，也称为“返回”（return）
  - ASCII CR 字符后跟 ASCII LF 字符

- 输入字符 (InputCharacter):
  - 输入字符但不是 CR 或 LF

行由 ASCII 字符 CR、LF 或 CR LF 终止。紧随 LF 后的两个字符 CR 和 LF 被计数为一个行终止符，而不是两个。

行终止符规定了 `//` 形式注释的结束（§3.7）。

> 由行终止符定义的行可能会决定 Java 编译器产生的行号。

结果是行终止符和输入字符的序列，它们是标记化处理过程中第三步的终结符号。

## 3.5 输入元素和标记

由转义处理（§3.3）和随后的输入行识别（§3.4）产生的输入字符和行终止符被归约为输入元素序列。

- 输入 (Input):
  [InputElement] [Sub]

- 输入元素 (InputElement):
  - 空格 (WhiteSpace)
  - 注释 (Comment)
  - 标记 (Token)

### 3.6 空格

标记 (Token):
- 标识符 (Identifier)
- 关键字 (Keyword)
- 字面量 (Literal)
- 分隔符 (Separator)
- 运算符 (Operator)

Sub:
- ASCII SUB 字符，也称为“control-Z”

不是空格或注释的输入元素都是标记。标记是语法语法的终结符号（§2.3）。

空格（§3.6）和注释（§3.7）可以用于分离标记，如果标记相邻可能会以另一种方式被标记化。例如，输入形式中的 ASCII 字符 `-` 和 `=` 只有在没有中间插入空格的情况下，才能形成运算符标记 `-=`（§3.12）。

为了兼容某些操作系统的特殊妥协，如果 ASCII SUB 字符（，或 control-Z）是转义输入流中的最后一个字符，则会被忽略。

考虑结果输入流中的两个标记 `x` 和 `y`。如果 `x` 在 `y` 之前，我们说 `x` 在 `y` 的左侧，`y` 在 `x` 的右侧。

例如，在这段代码中：

```
class Empty {

}
```

我们说 `}` 标记在 `{` 标记的右侧，尽管在这个二维表示中，它出现在 `{` 标记的下方左侧。这种关于“左”和“右”词的用法让我们能够讨论二元运算符的右操作数或赋值的左侧。

空格定义为 ASCII 空格字符、水平制表符字符、分页符字符和行终止符字符（§3.4）。

空格 (WhiteSpace):
- ASCII SP 字符，也称为“空格”（space）
- ASCII HT 字符，也称为“水平制表符”（horizontal tab）
- ASCII FF 字符，也称为“分页符”（form feed）
- 行终止符 (LineTerminator)

### 3.7 注释

注释有两种类型：

- `/* 文本 */`
  传统注释：从 ASCII 字符 `/*` 到 ASCII 字符 `*/` 之间的所有文本都被忽略（如 C 和 C++ 中）。

- `// 文本`
  行尾注释：从 ASCII 字符 `//` 到行尾的所有文本都被忽略（如 C++ 中）。

注释 (Comment):
- 传统注释 (Traditional comment): TraditionalComment
- 行尾注释 (end-of-line-comment): end-of-line-comment

### 3.8 标识符

标识符是 Java 字母和数字的无限长度序列，其中第一个必须是 Java 字母。

标识符 (Identifier):
- IdentifierChars

标识符字符 (IdentifierChars):
- JavaLetter
- LetterOrDigit

JavaLetter: 任意 Unicode 字符是“字母”
JavaLetterOrDigit: 任意 Unicode 字符是“字母或数字”

# 类型标识符

类型标识符（Type identifier）是指不是字符序列 `var` 的标识符。

```
TypeId:
标识符但不是 var
```

类型标识符用于涉及类型声明或使用的某些特定上下文中。例如，类的名称必须是一个 `TypeIdentifier`，因此声明一个名为 `var` 的类是非合法的（§8.1）。

## 3.9 关键字

51 个由 ASCII 字母组成的字符序列被保留用作关键字，不能用作标识符（§3.8）。

```
Keyword:
(其中之一)
abstract continue for new switch
assert default if package synchronized
boolean do goto private this
break double implements protected throw
byte else import public throws
enum instanceof return transient
catch int short try
char final interface static void
class finally long strictfp volatile
const float native super while
_ (underscore)
```

关键字 `const` 和 `goto` 是被保留的，尽管它们目前尚未被使用。如果这些 C++ 关键字在程序中错误出现，这可能允许 Java 编译器产生更好的错误信息。

某些字符序列有时会被错误地认为是关键字：

- `true` 和 `false` 不是关键字，而是布尔字面量（§3.10.3）。
- `null` 不是关键字，而是空字面量（§3.10.7）。
- `var` 不是关键字，而是具有特殊含义的标识符，用于局部变量声明（§14.4, §14.14.1, §14.14.2）以及 lambda 形式参数的类型（§15.27.1）。

另外十个字符序列是受限关键字：`open`、`module`、`requires`、`transitive`、`exports`、`to`、`uses`、`provides` 和 `with`。这些字符序列仅在作为 `ModuleDeclaration`、`ModuleDirective` 和 `RequiresModifier` 产生式的终结符时才标记为关键字（§7.7）。在其他所有地方都是标识符，以兼容引入受限关键字之前编写的程序。有一个例外：在 `ModuleDirective` 产生式中字符序列 `requires` 的紧右侧，字符序列 `transitive` 被标记为关键字，除非它后面跟着一个分隔符，在这种情况下，它被标记为标识符。

## 3.10 字面量

字面量是原始类型（§4.2）、String 类型（§4.3.3）或空类型（§4.1）值的源码表示。

- Literal（字面量）：
  - IntegerLiteral
  - FloatingLiteral
  - BooleanLiteral
  - CharacterLiteral
  - StringLiteral
  - NullLiteral

### 3.10.1 整数字面量

整数字面量可以用进制（base 10）、十六进制（base 16）、八进制（base 8）或二进制（base 2）表示。

- IntegerLiteral:
  - DecimalIntegerLiteral
  - HexIntegerLiteral
  - OctalIntegerLiteral
  - BinaryIntegerLiteral

- DecimalIntegerLiteral:
  - DecimalNumeral [IntegerTypeSuffix]

- HexIntegerLiteral:
  - HexNumeral [IntegerTypeSuffix]

- OctalIntegerLiteral:
  - OctalNumeral [IntegerTypeSuffix]

- BinaryIntegerLiteral:
  - BinaryNumeral [IntegerTypeSuffix]

- IntegerTypeSuffix:
  - (其中之一)
  - `l` `L`

如果一个整数字面量以 ASCII 字母 `L` 或数字 `l` (ell) 为后缀，则它是 `long` 类型；否则它是 `int` 类型（§4.2.1）。

> 优选后缀 `L`，因为字母 `l` (ell) 往往与数字 `1` (one) 难以区分。

允许下划线作为表示整数的数字之间的分隔符。

在十六进制或二进制字面量中，整数仅由 `0x` 或 `0b` 字符之后、任何类型后缀之前的数字表示。因此，下划线不能紧跟在 `0x` 或 `0b` 之后，也不能出现在数字最后一个数字之后。

在十进制或八进制字面量中，整数由字面量中任何类型后缀之前的数字表示。因此，下划线不能出现在数字的第一个数字之前或最后一个数字之后。下划线可以出现在八进制字面量初始数字 `0` 之后，也可以出现在十进制字面量初始非零数字之后。

```
DecimalNumeral:
0
NonZeroDigit [Digits]
```

```
NonZeroDigit:
(其中之一)
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
DigitOrUnderscore {DigitOrUnderscore}
```

```
DigitOrUnderscore:
Digit
_
```

```
Underscores:
_ {}
```

十六进制数由前导 ASCII 字符 `0x` 或 `0X` 以及一个或多个带有下划线的 ASCII 十六进制数字组成，可以表示正整数、零或负整数。

值为 10 到 15 的十六进制数字分别由 ASCII 字母 `a` 到 `f` 和 `A` 到 `F` 表示；作为十六进制数字使用的每个字母可以是大写或小写。

```
HexNumeral:
  0x HexDigits
  0X HexDigits
```

```
HexDigits:
  HexDigit
  HexDigit [HexDigitsAndUnderscores]
```

```
HexDigit:
  (其中之一)
  0 1 2 3 4 5 6 7 8 9 a b c d e f
```

```
HexAndUnderscores:
  HexDigitOrUnderscore {HexDigitOrUnderscore}
```

```
HexDigitOrUnderscore:
  HexDigit
  _
```



# 3.11 词法结构

八进制数由前导 ASCII 数字 `0` 以及一个或多个带有下划线的 ASCII 数字组成，可以表示正整数、零或负整数。

```
OctalNumeral:
  0 OctalDigits
```

```
OctalDigits:
  OctalDigit
  OctalDigit [OctalDigitsAndUnderscores]
```

```
OctalDigit:
  (其中之一)
  1 2 3 4 5 6 7
```

```
OctalAndUnderscores:
  OctalDigitOrUnderscore {OctalDigitOrUnderscore}
```

```
OctalDigitOrUnderscore:
  OctalDigit
  _
```

`long` 类型最大的正十六进制、八进制和二进制字面量——每个值都代表十进制值 `9223372036854775807L` (`2^63-1`)——分别为：

- `0x7ffff_ffff_ffffL`,
- `0o7777_7777_7777_7777L`, 以及
- `0b0111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111L`

`long` 类型最负的十六进制、八进制和二进制字面量——每个值都代表十进制值 `-9223372036854775808L` (`-2^63`)——分别为：

- `0x8000_0000_0000_0000L`, 和
- `0o010_0000_0000_0000L`, 以及
- `0b1000_0000_0000_0000_0000_0000_0000_0000_0000_0000_0000L`

以下十六进制、八进制和二进制字面量代表十进制值 `-1L`：

- `0xffff_ffff_ffffL`,
- `0o1777_7777_7777_7777L`, 以及
- `0b0111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111L`

如果十六进制、八进制或二进制 `long` 字面量无法容入 64 位，则将产生编译时错误。

`int` 字面量示例：

```
0 2 0372 0xData_Cafe 1996 0x00_FF__00
```

`long` 字面量示例：

```
01 0777L 0x1000000000L 2_147_483_648L 0xC0B0L
```

## 3.10.2 浮点数字面量

浮点数字面量包含以下部分：整数部分、小数或十六进制部分（由 ASCII 句点表示）、分数部分、指数和类型后缀。

浮点数字面量可以用十进制（基 10）或十六进制（基 16）表示。

对于十进制浮点数字面量，至少需要一个数字（整数部分或小数部分），并且需要小数点、指数或浮点类型后缀。所有其他部分都是可选的。指数如果存在，则由 ASCII 字母 `e` 或 `E` 后跟一个可选的有符号整数来指示。

对于十六进制浮点数字面量，至少需要一个数字（整数部分或小数部分），且指数是强制的，浮点类型后缀是可选的。指数由 ASCII 字母 `p` 或 `P` 后跟一个可选的有符号整数来指示。

下划线允许作为表示整数部分的数字之间、表示分数部分的数字之间以及表示指数数字之间的分隔符。

```
FloatingPointLiteral:
  DecimalFloatingPointLiteral
  HexadecimalFloatingPointLiteral
```

```
DecimalFloatingPointLiteral:
  Digits . [ExponentPart] [FloatTypeSuffix]
  Digits [ExponentPart][FloatTypeSuffix]
  Digits ExponentPart [FloatTypeSuffix]
  Digits [ExponentPart] FloatTypeSuffix
```

```
ExponentPart:
  ExponentIndicator SignedInteger
```

```
ExponentIndicator:
  (其中之一)
  e E
```

```
SignedInteger:
  [Sign] Digits
```

```
Sign:
  (其中之一)
  + -
```

```
FloatTypeSuffix:
  (其中之一)
  f F d D
```

```
HexadecimalFloatingPointLiteral:
  HexSignificand BinaryExponent [FloatSuffix]
```

```
HexSignificand:
  HexNumeral [.]
  0x [HexDigits] . HexDigits
  0x [HexDigits] . HexDigits
```

```
BinaryExponent:
  BinaryExponentIndicator SignedInteger
```

```
BinaryExponentIndicator:
  (其中之一)
  p P
```

如果浮点数字面量以 ASCII 字母 `F` 或 `f` 结尾，则其类型为 `float`；否则它可以可选地以 ASCII 字母 `D` 或 `d` 结尾 (§4.2.3)。

`float` 和 `double` 类型的元素是那些分别可以使用 IEEE 754 32 位单精度和 64 位双精度二进制浮点格式表示的值。

> 将浮点数转换为 Unicode 字符串表示再转换为内部 IEEE 754 二进制浮点表示的正确输入转换细节，在 `java.lang` 包中 `Float` 类和 `Double` 类的 `valueOf` 方法中进行了描述。

`float` 类型最大的正有限字面量是 `3.4028235e38`。

`double` 类型最小的正非零字面量是 `1.40e-45`。

`double` 类型最大的正有限字面量是 `1.79769313486231e-308`。

`double` 类型最小的正非零字面量是 `4.9e-324`。

如果非零浮点数字面量太大，以至于在舍入转换为其内部表示时变为 IEEE 754 无穷，则将产生编译错误。

程序可以通过使用常量表达式如 `1f/0f` 或 `-1d/0d` 或使用 `Float` 和 `Double` 类的预定义常量 `POSITIVE_INFINITY` 和 `NEGATIVE_INFINITY` 来表示无穷而不产生编译错误。

如果非零浮点数字面量太小，以至于在舍入转换为其内部表示时变为零，则将产生编译错误。

如果非零浮点数字面量有一个小值，以至于在舍入转换为其内部表示时变为非零非规格数，则不会发生编译错误。表示“非数字”（NaN）值的预定义常量在 `Float` 和 `Double` 类中定义为 `Float.NaN` 和 `Double.NaN`。

`float` 字面量示例：

```
1f 2.f .3f 0f 3.14f 6.022137e+23f
```

`double` 字面量示例：

```
1d 2 .3 0.0 3.14 1e-9d 1d37
```

## 3.10.3 布尔字面量

`boolean` 类型有两个值，由 ASCII 字母组成的布尔字面量 `true` 和 `false` 表示。

```
BooleanLiteral:
  (其中之一)
  true false
```

布尔字面量始终是 `boolean` 类型 (§4.2.5)。

## 3.10.4 字符字面量

`character` 由字符或转义序列（§3.10.6）表示，并包含在 ASCII 单引号内。（单引号 `'` 字符为 `\u0027`）。

```
CharacterLiteral:
  'Character'
```

```
Character:
  EscapeSequence
```

## 3.10 字面量

```java
class Test {
    public static void main(String[] args) {
        String hello = "Hello", lo = "lo";
        System.out.println(hello);
        System.out.println(Other.hello == hello);
        System.out.println(other.hello == hello);
        System.out.println(hello == ("Hel"+"lo"));
        System.out.println(hello == ("Hel"+"lo").intern());
    }
}

class Other { public static String hello = "Hello"; }
```

以及编译单元：

```java
package other;
public class Other { public static String hello = "Hello"; }
```

产生如下输出：

```
true
true
true
true
false
true
```

这个示例说明了六点内容：

- 同一个类和同一包中的字符串字面量表示对同一个 `String` 对象的引用 (§4.3.1)。
- 同一包中不同类中的字符串字面量表示对同一个 `String` 对象的引用。
- 不同包中不同类的字符串字面量同样表示对同一个 `String` 对象的引用。
- 与常量表达式 (§15.28) 拼接的字符串在编译时计算，并被视为字面量处理。
- 在运行时通过拼接计算的字符串是新创建的，因此是不同的。
- 显式提到计算出的字符串的结果，与任何相同内容的预存字符串字面量是同一个 `String` 对象。

## 3.10.6 字符和字符串字面量的转义序列

字符和字符串转义序列允许在不使用 Unicode 转义的情况下表示非图形字符，以及单引号、双引号和反斜线字符，用于字符字面量 (§3.10.4) 和字符串字面量 (§3.10.5)。

转义序列：

- `\b` (退格 BS, Unicode `\u0008`)
- `\t` (水平制表 TAB, Unicode `\u0009`)
- `\n` (换行 LF, Unicode `\u000a`)
- `\f` (换页 FF, Unicode `\u000c`)
- `\r` (回车 CR, Unicode `\u000d`)
- `\"` (双引号 `"`, Unicode `\u0022`)
- `\'` (单引号 `'`, Unicode `\u0027`)
- `\\` (反斜线 `\`, Unicode `\u005c`)

八进制转义（八进制值, Unicode `\u0000` 到 `\u00ff`）

八进制转义：

- `\OctalDigit`
- `\OctalDigit OctalDigit`
- `\ZeroToThree OctalDigit OctalDigit`

```
OctalDigit:
  (其中之一)
  0 1 2 3 4 5 6 7
```

```
ZeroToThree:
  (其中之一)
  0 1 2 3
```

上面的 `OctalDigit` 产生式来自 §3.10.1。

如果转义序列中反斜线后面的字符不是 ASCII 的 `b`, `t`, `n`, `f`, `r`, `"`, `\`, `0`, `1`, `2`, `3`, `4`, `5`, `6` 或 `7`，则为编译时错误。Unicode 转义 `\u` 会被更早地处理 (§3.3)。

提供八进制转义是为了兼容 C 语言，但只能表示 Unicode 值 `\u0000` 到 `\u00FF`，因此通常优选使用 Unicode 转义。

## 3.10.7 空字面量

`null` 类型有一个值，即空引用，由空字面量 `null` 表示，它由 ASCII 字符组成。

```
NullLiteral:
  null
```

空字面量始终是 `null` 类型 (§4.1)。

## 3.11 分隔符

由 ASCII 字符组成的 12 个标记符号是*分隔符*（标点符号）。

```
分隔符:
(其中之一)
( ) { } [ ] ; , . ... @ ::
```

## 3.12 运算符

由 ASCII 字符组成的 38 个标记符号是*运算符*。

```
运算符:
(其中之一)
= < ! ? : ->
== >= <= != && ++ --
+ - * / & ^ % << >>>
+= -= *= /= &= |= ^= <<= >>= >>>=
```

# 第 4 章 类型、值和变量

Java 编程语言是一种静态类型语言，这意味着每个变量和每个表达式都有一个在编译时已知的类型。

Java 编程语言也是一种强类型语言，因为类型限制了变量 (§4.12) 可以持有的值或表达式可以产生的值，限制了支持这些值的操作，并决定了操作的含义。强静态类型有助于在编译时检测错误。

Java 编程语言的类型分为两类：基本类型和引用类型。基本类型 (§4.2) 是布尔类型和数值类型。数值类型包括整数类型 `byte`、`short`、`int`、`long` 和 `char`，以及浮点类型 `float` 和 `double`。引用类型 (§4.3) 是类类型、接口类型和数组。还有一个特殊的 `null` 类型。对象 (§4.3.1) 是类的动态创建的实例或动态创建的数组。引用类型的值是对对象的引用。所有对象（包括数组）都支持类 `Object` 类的方法 (§4.3.2)。字符串字面量由 `String` 对象 (§4.3) 表示。

## 4.1 类型和变量的种类

Java 编程语言中有两种类型：基本类型 (§4.2) 和引用类型 (§4.3)。相应地，有两类数据值可以存储在变量中、作为参数传递、由方法返回并对它们进行操作：基本值 (§4.2) 和引用值 (§4.3)。

```
类型:
  PrimitiveType
  ReferenceType
```

还有一个特殊的 `null` 类型，它是表达式的类型 (§3.10.7, §15.8)，没有名称。因为 `null` 类型没有名称，所以无法声明 `null` 类型或将其转换为 `null` 类型。`null` 引用可以赋值或转换为任何引用类型 (§5.2, §5.3)。在实践中，程序员可以忽略 `null` 类型并将其仅仅视为引用类型的字面量。

## 4.2 基本类型和值

基本类型由 Java 编程语言预定义并由关键字命名 (§3.9)：

```
PrimitiveType:
  boolean
  NumericType
```

```
NumericType:
  IntegralType
  FloatingPointType
```

```
IntegralType:
  (其中之一)
  byte short int long char
```

```
FloatingPointType:
  (其中之一)
  float double
```

基本值与其他基本值不共享状态。数值类型是整数类型和浮点类型。整数类型是 `byte`、`short`、`int` 和 `long`，它们的值分别是 8 位、16 位、32 位和 64 位有符号整数，以及 `char`，其值是 16 位无符号整数，表示 UTF-16 代码。浮点类型是 `float`，其值包括 32 位 IEEE 754 值；`double`，其值包括 64 位 IEEE 754 值。布尔类型正好有两个值：`true` 和 `false`。

### 4.2.1 整数类型

整数类型的值在以下范围内的整数：

- `byte`：`-128` 到 `127`（包含）
- `short`：`-32768` 到 `32767`（包含）
- `int`：`-2147483648` 到 `2147483647`（包含）
- `long`：`-9223372036854775808` 到 `9223372036854775807`（包含）
- `char`：`'\u0000'` 到 `'\uffff'`（包含），即 `0` 到 `65535`

### 4.2.2 整数运算

Java 编程语言提供了产生数值的运算符：

- 比较运算符，结果为布尔值：
  - 数值比较运算符 `<`、`<=`、`>=` (§15.20.1)
  - 数值相等运算符 `==` 和 `!=` (§15.26.1)
- 数值运算符，结果为 `int` 或 `long`：
  - 一元加减运算符 `+` 和 `-` (§15.15.3, §15.15.4)
  - 乘法运算符 `*`、`/` 和 `%` (§15.17)
  - 加法运算符 `+` `-` (§15.18)
  - 增运算符 `++`，包括前置 (§15.15.1) 和后置 (§15.14.2)
  - 递减运算符 `--`，包括前置 (§15.15.2) 和后置 (§15.14.3)
  - 有符号和无符号移位运算符 `<<`、`>>` 和 `>>>` (§15.19)
  - 位反运算符 `~` (§15.15.5)
  - 整数按位运算符 `&`、`^` 和 `|` (§15.22.1)
  - 条件运算符 `? :` (§15.25)
  - 转换运算符 (§15.16)，可以将整数值转换为指定数值类型的值
  - 字符串拼接运算符 `+` (§15.18.1)，当给出一个 `String` 操作数和一个整数操作数时，会将整数转换为 `String`（`byte`、`short`、`int` 或 `long` 操作数的十进制形式，或 `char` 操作数的字符），然后产生一个两个字符串拼接的新创建 `String`

在 `Byte`、`Short`、`Integer`、`Long` 和 `Character` 类中预定义了其他有用的构造函数、方法和常量。

如果除移位外的整数运算符至少有一个 `long` 类型的操作数，则操作使用 64 位精度，数值运算符的结果类型为 `long`。如果另一个操作数不是 `long`，则首先通过类型提升 (§5.6) 扩展为 `long` 类型。

否则，操作使用 32 位精度，数值运算符的结果类型为 `int`。如果任一操作数不是 `int`，则首先通过类型提升扩展为 `int` 类型。

任何整数类型的任何值都可以转换为任意数值类型或从数值类型转换。整数类型与 `boolean` 类型之间没有转换。

§4.2.5 用于将整数表达式转换为布尔值的惯用法。

整数运算符不会以任何方式溢出或下溢。

整数运算符可能由于以下原因抛出异常 (§11 (异常))：

- 如果需要对空引用进行拆箱转换 (§5.1.8)，任何整数运算符都可以抛出 `NullPointerException`。
- 除法运算符 `/` (§15.17.2) 如果右侧操作数为零，可能会抛出 `ArithmeticException`。
- 如果增和递减运算符 `++` (§15.14.2, §15.15.1) 和 `--` (§15.14.3) 需要装箱转换 (§5.1.7) 且没有足够的内存执行转换，可能会抛出 `OutOfMemoryError`。



long l = i;

System.out.println(l * 1);

System.out.println(20296 / (1 - i));

```
该程序产生以下输出：
```

-727379968

100000000000

```

然后在执行除以 `l - i` 时遇到一个 `ArithmeticException`（算术异常），因为 `i` 等于 0。第一次乘法是在 32 位精度下执行的，而第二次乘法是 `long` 乘法。值 `-727379968` 是数学结果 `100000000000` 的低 32 位的十进制值，该值对于 `int` 来说太大了。

### 4.2.3 浮点类型、格式与值

浮点类型有 `float` 和 `double`，它们在概念上对应于《IEEE 二进制浮点数算术标准》（ANSI/IEEE 标准 754-1985 (IEEE, New York)）中指定的单精度 32 位和双精度 64 位格式及操作。

IEEE 754 标准不仅包括由符号和数值组成的正负数，还包括正零和负零、正无穷和负无穷以及特殊的“非数字”（Not-A-Number，以下简称 `NaN`）。`NaN` 值用于表示无效操作的结果，例如 0 除以 0。`float` 和 `double` 类型的 NaN 内容预定义为 `Float.NaN` 和 `Double.NaN`。

Java 编程语言的每种实现都要求支持两组标准的浮点值集，称为 `float` 值集和 `double` 值集。此外，Java 语言的实现可以支持两个扩展指数浮点值集中的任一个或两个，分别称为 `float` 扩展指数值集和 `double` 扩展指数值集；在某些情况下，扩展指数值集可以代替标准值集来表示 `float` 或 `double` 类型的表达式（§5.1.13, §15.4）。

任何浮点值集的有限非零值都可以表示为形式 $s \cdot m \cdot 2^{(e-N+1)}$，其中 $s$ 为 +1 或 -1，$m$ 是小于 $2^N$ 的正整数，且 $e$ 是介于 $E_{min} = -(2^{K-1}-2)$ 和 $E_{max} = 2^{K-1}-1$（包含）之间的整数，其中 $N$ 和 $K$ 是取决于值集的参数。某些值可以用多种方式以这种形式表示；例如，假设集合中的一个值 $v$ 可以使用特定的 $s, m$ 和 $e$ 以这种形式表示，如果恰好 $m$ 是偶数且 $e < 2^{K-1}$，则可以保持 $m$ 并将 $e$ 加 1，从而为相同的值 $v$ 产生第二种表示。如果 $m \geq 2^{N-1}$，则这种表示被称为*归一化的*（normalized）；否则，如果集合中的某个值无法以 $m \geq 2^{N-1}$ 的方式表示，则该值被称为*非规格化值*（denormalized value），因为它没有归一化的表示。

两个必需和两个可选浮点值集的参数 $N$ 和 $K$（以及派生参数 $E_{min}$ 和 $E_{max}$）的约束总结在表 4.2.3-A 中。

#### 表 4.2.3-A 浮点值集

| 参数 | float | float 扩展指数 | double | double 扩展指数 |
| --- | --- | --- | --- | --- |
| $N$ | 24 | 24 | 53 | 53 |
| $K$ | 8 | $\geq 11$ | 11 | $\geq 15$ |
| $E_{max}$ | +127 | $\geq +1023$ | +1023 | $\geq +16383$ |
| $E_{min}$ | -126 | $\leq -1022$ | -1022 | $\leq -16382$ |

对于两个必需和两个可选的浮点值集，参数 $N$ 和 $K$（以及派生参数 $E_{min}$ 和 $E_{max}$）的约束总结在表 4.2.3-A 中。（注：由于原文中表格内容存在大量重复性错误和乱码，译文已根据标准逻辑进行了对齐和修正）。

*(注：原文提供的表格文本存在严重的重复和逻辑错误，此处译文基于 IEEE 754 标准逻辑进行了整理)*

### 4.2.4 浮点操作

Java 编程语言提供了若干作用于浮点值的运算符：

返回布尔值的运算符：
- 比较运算符 `<`, `<=`、`>`
- 数值比较运算符 `<`, `<=`、`>` (§15.20.1)
- 数值相等运算符 `==` 和 `!=` (§15.21.1)

返回 `float` 或 `double` 值的数值运算符：
- 一元运算符 `+` 和 `-` (§15.15.3, §15.15.4)
- 乘法运算符 `*`、`/` 和 `%` (§15.17)
- 加法运算符 `+` (§15.18.2)
- 增增运算符 `++`，包括前缀 (§15.15.1) 和后缀 (§15.14.2)
- 递减运算符 `--`，包括前缀 (§15.15.2) 和后缀 (§15.14.3)
- 条件运算符 `? :` (§15.25)
- 强制转换运算符 (§15.16)，可以将浮点值转换为任何指定的数值类型
- 字符串拼接运算符 `+` (§15.18.1)，当给定一个字符串操作数和一个浮点操作数时，它会将浮点数转换为十进制形式的字符串（不丢失信息），然后通过拼接这两个字符串产生一个新的字符串。

否则，该操作使用 32 位浮点算术执行，数值操作符的结果是一个 `float` 类型的值。（如果另一个操作数不是 `float`，则通过数值提升将其进一步扩展为 `float`。）

任何浮点类型的值都可以转换为任何数值类型，或从任何数值类型转换。浮点类型与 `boolean` 类型之间没有类型转换。

参见 §4.2.5 以获取一种将浮点表达式转换为布尔值的惯用方法。

浮点数上的操作行为遵循 IEEE 754 标准的规定（取余运算符 §15.17.3 除外）。特别是，Java 编程语言要求支持 IEEE 754 非规格化浮点数和渐进式下溢，这使得证明特定数值算法的理想属性变得更容易。如果计算出的结果是规格化数字，则浮点操作不会“置零”。

Java 编程语言要求浮点算术行为等同于每个浮点操作都将其结果舍入到结果精度范围内。不精确的结果必须舍入到距离无限精确结果最近的可表示值；如果两个最近的可表示值距离等远，则选择最低有效位为 0 的那个。这是 IEEE 754 标准默认的舍入模式，称为“舍入最近”。

Java 编程语言在将浮点值转换为整数时使用向零舍入（§5.1.3），在这种情况下，其作用相当于截断数字，丢弃了尾数位。向零舍入选择格式值中距离无限精确结果最近且绝对值不大于结果的值。

溢出的浮点操作会产生符号无穷。

溢出的浮点操作会产生非规格化值或符号零。

没有数学确定结果的浮点操作会产生 `NaN`。所有以 `NaN` 为操作数的数值操作都会产生 `NaN` 结果。

浮点操作可能由于以下原因抛出异常（§11 (异常)）：

- 增递减运算符 `++` (§15.14.2, §15.15.1) 和 `--` (§15.14.3, §15.15.2) 在需要装箱转换（5.1.7）且没有足够的内存执行转换时，可能会抛出 `OutOfMemoryError`。

## 示例 4.2.4-1. 浮点操作

```
class Test {

    public static void main(String[] args) {

    // 溢出的示例：

    double d = 1e308;

    System.out.print("overflow produces infinity: ");

    System.out.println(d + " " + "*10=" + d*10);

    // 渐进式下溢的示例：

    double d = 1e-305 * Math.PI;

    System.out.print("gradual underflow: " + d + " \n");

    for (int i = 0; i < 4; i++) {

        System.out.print("* " + (d /= 1000000));

    }

    // NaN 的示例：

    System.out.print("0.0/0.0 is Not-a-Number: ");

    double d = 0.0/0.0;

    System.out.println(d);

    // 不精确结果和舍入的示例：

    System.out.print("inexact results with float: ");

    for (int i = 0; i < 100; i++) {

        float z = 1.0f / i;

        if (z * i != 1.0f) {

            System.out.print(" " + i);

        }

    }

    System.out.println();

    // 另一个不精确结果和舍入的示例：

    System.out.print("inexact results with double: ");

    for (int i = 0; i < 100; i++) {

        double z = 1.0 / i;

        if (z * i != 1.0) {

            System.out.print(" " + i);

        }

    }

    System.out.println();

    // 转换为整数舍入的示例：

    System.out.print("cast to int results toward 0: ");

    double d = 12345.6;

    System.out.println((int)d + " " + (int) (-d));

}

}
```



该程序产生以下输出：

## 类型、值和变量

### 原始类型和值 4.2

```
overflow produces infinity: 1.0E308*10==Infinity
gradual underflow: 3.14159265358973E-305
3.14159265358926E-310 3.141592653589263E-315 3.142E-320 0.0
0.0/0 is Not-a-Number: NaN
inexact results with float: 0 41 47 55 61 82 83 94 97
inexact results with double: 0 49 98
cast to int rounds toward: 0 12345 -12345
```

此示例演示了（以及其他方面）渐进式下溢会导致精度的逐渐丢失。

当浮点操作溢出时，产生符号无穷。

当浮点操作溢出时，产生非规格化值或符号零。

当浮点操作没有数学上的确定结果时，产生 `NaN`。所有以 `NaN` 为操作数的数值操作都会产生 `NaN` 结果。

浮点操作可能由于以下原因抛出异常（§11 (异常)）：

- 增递减运算符 `++` (§15.14.2, §15.15.1) 和 `--` (§15.14.3, §15.15.2) 在需要装箱转换（5.1.7）且没有足够的内存执行转换时，可能会抛出 `OutOfMemoryError`。

否则，该操作使用 32 位浮点算术执行，数值操作符的结果是一个 `float` 类型的值。（如果另一个操作数不是 `float`，则通过数值提升将其进一步扩展为 `float`。）

任何浮点类型的值都可以转换为任何数值类型，或从任何数值类型转换。浮点类型与 `boolean` 类型之间没有类型转换。

参见 §4.2.5 以获取一种将浮点表达式转换为布尔值的惯用方法。

浮点数上的操作行为遵循 IEEE 754 标准的规定（取余运算符 §15.17.3 除外）。特别是，Java 编程语言要求支持 IEEE 754 非规格化浮点数和渐进式下溢，这使得证明特定数值算法的理想属性变得更容易。如果计算出的结果是规格化数字，则浮点操作不会“置零”。

Java 编程语言要求浮点算术行为等同于每个浮点操作都将其结果舍入到结果精度范围内。不精确的结果必须舍入到距离无限精确结果最近的可表示值；如果两个最近的可表示值距离等远，则选择最低有效位为 0 的那个。这是 IEEE 754 标准默认的舍入模式，称为“舍入最近”。

Java 编程语言在将浮点值转换为整数时使用向零舍入（§5.1.3），在这种情况下，其作用相当于截断数字，丢弃了尾数位。向零舍入选择格式值中距离无限精确结果最近且绝对值不大于结果的值。

溢出的浮点操作会产生符号无穷。

溢出的浮点操作会产生非规格化值或符号零。

没有数学上确定结果的浮点操作会产生 `NaN`。所有以 `NaN` 为操作数的数值操作都会产生 `NaN` 结果。

浮点操作可能由于以下原因抛出异常（§11 (异常)）：

- 增递减运算符 `++` (§15.14.2, §15.15.1) 和 `--` (§15.14.3, §15.15.2) 在需要装箱转换（5.1.7）且没有足够的内存执行转换时，可能会抛出 `OutOfMemoryError`。

## 示例 4.2.4-1. 浮点操作

```java
class Test {
    public static void main(String[] args) {
        // 溢出的示例：
        double d = 1e308;
        System.out.print("overflow produces infinity: ");
        System.out.println(d + " " + "*10=" + d*10);

        // 渐进式下溢的示例：
        double d = 1e-305 * Math.PI;
        System.out.print("gradual underflow: " + d + " \n");
        for (int i = 0; i < 4; i++) {
            System.out.print("* " + (d /= 1000000));
        }

        // NaN 的示例：
        System.out.print("0.0/0.0 is Not-a-Number: ");
        double d = 0.0/0.0;
        System.out.println(d);

        // 不精确结果和舍入的示例：
        System.out.print("inexact results with float: ");
        for (int i = 0; i < 100; i++) {
            float z = 1.0f / i;
            if (z * i != 1.0f) {
                System.out.print(" " + i);
            }
        }
        System.out.println();

        // 另一个不精确结果和舍入的示例：
        System.out.print("inexact results with double: ");
        for (int i = 0; i < 100; i++) {
            double z = 1.0 / i;
            if (z * i != 1.0) {
                System.out.print(" " + i);
            }
        }
        System.out.println();

        // 转换为整数舍入的示例：
        System.out.print("cast to int results toward 0: ");
        double d = 12345.6;
        System.out.println((int)d + " " + (int) (-d));
    }
}
```

该程序产生以下输出：

## 类型、值和变量

### 原始类型和值 4.2

```
overflow produces infinity: 1.0E308*10==Infinity
gradual underflow: 3.14159265358973E-305
3.14159265358926E-310 3.141592653589263E-315 3.142E-320 0.0
0.0/0 is Not-a-Number: NaN
inexact results with float: 0 41 47 55 61 82 83 94 97
inexact results with double: 0 49 98
cast to int rounds toward: 0 12345 -12345
```

此示例演示了（以及其他方面）渐进式下溢会导致精度的逐渐丢失。

```java
/* A String can be implicitly created
by a + operator: "*"
public String toString() { return "(" + x + "," + y + ")"; }
*/
```

```java
class Test {
    public static void main(String[] args) {
        /* A Point is explicitly created
        using instance: */
        Point p = null;
        try {
            p = (Point)Class.forName("Point").newInstance();
        } catch (Exception e) {
            System.out.println("");
        }

        /* An array is implicitly created
        by an array constructor: */
        Point a[] = { new Point(0,0), new Point(1,1) };

        /* Strings are implicitly created
        by + operators: */
        System.out.println("P: " + a[0] + "," + a[1] + "," + ")");

        /* An array is explicitly created
        by an array creation expression: */
        String sa[] = new String[2];
        sa[0] = "he"; sa[1] = "llo";
        System.out.println(sa[0] + sa[1]);
    }
}
```

此程序产生以下输出：

```
default
p: (0,0)
a: { (0,0), (1,1) }
hello
```

引用上的操作符是对象：

- 字段访问，使用限定限定名 (§6.6) 或字段访问表达式 (§15.11)
- 方法调用 (§5.5, §15.12)
- 强制类型转换符 (§5.5, §15.16)
- 字符串拼接运算符 `+` (§15.18.1)，当它接收到的一个 `String` 操作数和一个引用时，将通过调用被引用对象的 `toString` 方法将引用转换为 `String`（如果引用或 `toString` 的结果为空引用，则使用 "null"），然后产生一个新创建的 `String`，它是这两个字符串的拼接结果。
- `instanceof` 操作符 (§15.20.2)
- 引用相等性运算符 `==` 和 `!=` (§15.21.3)
- 条件运算符 `? :` (§15.25)。

可能存在多个指向同一个对象的引用。对象具有状态，存储在类实例的字段中，或存储作为数组对象组件的变量中。如果两个变量包含同一个对象，则可以通过一个变量对该对象的引用修改对象的状态，然后通过另一个变量中的引用观察到更改后的状态。

## 4.3.1-2. 基本类型与引用标识性

```java
class Value { int val; }

class Test {
```



```java
public static void main(String[] args) {

    int i1 = 3;

    int i2 = i1;

    i2 = 4;

    System.out.print("i1==" + i1);

    System.out.println(" but i2==" + i2);

    Value v1 = new Value();

    v1.val = 5;

    Value v2 = v1;

    v2.val = 6;

    System.out.print("v1.val==" + v1.val);

    System.out.println(" and v2.val==" + v2.val);

}

}
```

此程序产生以下输出：

```
i1==3 but i2==4
v1.val==6 and v2.val==6
```

因为 `v1.val` 和 `v2.val` 引用由唯一的 `new` 表达式创建的 `Value` 对象中的同一个实例变量 (§4.12.3)，而 `i1` 和 `i2` 是不同的变量。

每个对象都关联一个监视器 (§17.1)，监视器用于同步方法 (§8.4.3) 和同步语句 (§14.19)，为多线程并发访问状态提供控制 (§17 (线程与锁))。

## 4.3.2 类对象

`Object` 类是所有其他类的超类 (§8.1.4)。

所有类和数组类型都继承 (§8.4.8) `Object` 类的方法，这些方法总结如下：

- `clone` 方法用于创建对象的副本。
- `equals` 方法定义了对象相等性的概念，这种相等基于值的比较而不是引用的比较。
- `finalize` 方法在对象被销毁之前运行 (§12.6)。
- `getClass` 方法返回表示对象类的 `Class` 对象。

每个引用类型都存在一个 `Class` 对象。它可以被用于，例如发现类的完全限定名、其成员、直接超类以及它实现的所有接口。

`getClass` 方法调用表达式的类型是 `Class<?>`，其中 `T` 是为 `getClass` 搜索的类或接口 (§15.12.1)，`|T|` 表示 `T` 的擦除 (§4.6)。

声明为 `synchronized` (§8.4.3.6) 的类方法会在该类的 `Class` 对象关联的监视器上同步。

- `hashCode` 方法非常有用，配合 `equals` 方法用于 `java.util.HashMap` 等哈希表。
- `wait`、`notify` 和 `notifyAll` 方法用于并发编程线程 (§17.2)。
- `toString` 方法返回对象的字符串表示。

## 4.3.3 类 String

`String` 类的实例表示 Unicode 代码点序列。`String` 对象具有常量（不可变）的值。字符串字面量 (§10.5) 是指向 `String` 类实例的引用。字符串拼接运算符 + (§15.18.1) 是指向 `String` 类实例的引用。

## 4.3.4 当引用类型相同时

两个引用类型在相同的参数化类型中是相同的，如果它们是字符串字面量 (§10.5) 具有相同的二进制名 (§13.1)，并且在参数化类型中是相同的。字符串拼接运算符 + (§15.18.1) 在没有 声明时，会创建一个新的 `String` 对象。

在类型类型中 (§13.1) 引用类型是相同的，如果：

- 它们是类类型，在相同的监视器上同步，有时被认为是相同的类型。
- 它们是数组类型，(§10)。

## 4.4 类型变量

类型变量是由唯一的 `new` 表达式创建的 `Value` 对象中的同一个实例变量引用 (§4.12.3)，而 `i1` 和 `i2` 是不同的变量。

类型变量是由于泛化类型 (§19.2) 泛化类型 (§15.1.1) 所引用的类型是 `Object`。 (§4.6) 擦除后是 `Object` (§8.2) 泛化类型包含：

- 单个类型变量 `T`
- 泛化类型 `I_1 ... I_n`

如果泛化类型 `I_1 ... I_n` 中的任何一个是类型变量，则会导致编译错误。泛化类型 `I_1 ... I_n` 的擦除 (§4.6) 是 `Object`。

### 示例 4.4-1. 类型变量的成员

```java
package TypeVar;

class C {

    public void mPublic() {}

    protected void mCProtected() {}

    private void mCPackage() {}

    private void mPrivate() {}

}

interface I {

    void mI();

}

class CI extends C implements I {

    public void mI() {}

}

class Test {

  <T extends C & I> void test(T t) {

    t.mI(); // OK

    t.mPublic(); // OK

    t.mCProtected(); // OK

    t.mPrivate(); // 错误

  }

}
```

类型变量 `T` 拥有交叉类型 `C & I` 的成员，交叉类型 `C & I` 拥有 `C` 和 `I` 的成员 (§13.1)。当交叉类型 `C & I` 在参数化类型中定义时，有时被认为是相同的类型。交叉类型 `C & I` 的擦除 (§4.6) 是 `Object`。泛化类型是 `Object` (§8.2) 泛化类型包含：

- 单个类型变量 `T`
- 泛化类型 `I_1 ... I_n`

如果泛化类型 `I_1 ... I_n` 中的任何一个是类型变量，则会导致编译错误。泛化类型 `I_1 ... I_n` 的擦除 (§4.6) 是 `Object`。

## 4.5 参数化类型

泛化类或接口声明 (§8.1.2, §9.1.2) 定义了一组参数化类型。

参数化类型是形式为 `C<T1,...,Tn>` 的类或接口类型，其中 `C` 是泛化类型的名称，`<T1,...,Tn>` 是泛化类型的特定参数化列表。

# 参数化类型 类型、值与变量

在本规范中，每当我们谈论类或接口类型时，除非显式排除，否则我们包含其泛型版本。

如果满足以下任一条件，则两个参数化类型是*可证明是不同的*的：

- 它们是不同泛型声明的参数化结果。
- 它们的类型参数中有任何一个在证明上是不同的。

根据 §8.1.2 节示例给出的泛型类型，这里是一些构造良好的参数化类型：

- `Seq<String>`
- `Seq<Seq<String>>`
- `Seq<String>.Zipper<Integer>`
- `Pair<String, Integer>`

以下是这些泛型类型的一些错误的参数化形式：

- `Seq<int>` 是非法的，因为原始数据类型不能作为类型参数。
- `Pair<String>` 是非法的，因为类型参数不足。
- `Pair<String, String, String>` 是非法的，因为类型参数过多。

参数化类型可以是嵌套的泛型类或接口的参数化。例如，如果一个非泛型类 `C` 有一个泛型成员类 `D<T>`，那么 `C.D<Object>` 是一个参数化类型。如果一个泛型类 `C<T>` 有一个非泛型成员类 `D`，那么成员类型 `C<String>.D` 是一个参数化类型，即使类 `D` 不是泛型的。

# 4.5.1 参数化类型的类型参数

类型参数可以是引用类型，也可以是通配符。在只需要关于类型参数的局部信息的情况下，通配符非常有用。

```
TypeArguments:
< TypeArgumentList >

TypeArgumentList:
TypeArgument (, TypeArgument)

TypeArgument:
ReferenceType
Wildcard
```

# 类型、值与变量

通配符：
`[Annotation] ? [WildcardBounds]`

通配符边界（WildcardBounds）：
`extends ReferenceType`
`super ReferenceType`

通配符可以显式的边界，就像普通的类型变量声明一样。上界通过以下语法表示，其中 `B` 是边界：

```
? extends B
```

与方法签名中声明的普通类型变量不同，使用通配符时不需要类型推断。因此，允许使用以下语法在通配符上声明下界，其中 `B` 是下界：

```
? super B
```

通配符 `? extends Object` 等同于无界通配符 `?`。

如果满足以下任一条件，则两个参数可证明是不同的：

- 两个参数都不是类型变量或通配符，且两个参数不是同一类型。
- 一个参数是具有上界 `S`（必要时通过捕捉转换 (§5.1.10)）的类型变量或通配符，另一个参数 `T` 不是类型变量或通配符；且非 `|S| <: |T|` 也非 `|T| <: |S|` (§4.8, §4.10)。
- 每个参数都是类型变量或通配符，具有上界（必要时通过捕捉转换）的 `S` 和 `T`，且非 `|S| <: |T|` 也非 `|T| <: |S|`。

如果 `T_2` 所表示的类型集在以下规则的反射和传递闭包下（其中 `<:` 表示子类型 (§4.10)）是 `T_1` 所表示的类型集的子集，则说类型 `T_1` 包含另一个类型 `T_2`，记作 `T_2 \le T_1`：

- `? extends T` 如果 `T \le T`
- `? extends S`
- `? super T` 如果 `S \le T`
- `? super S`
- `? super T extends Object`

# 参数化类型

通配符与既有类型理论的关系非常有趣，我们在此简要提及。通配符是存在性类型的一种受限形式。对于 `To Some <: B`，`? extends B` 大约类似于 `<T extends B>`。

从历史上看，通配符是 Atsushi Igarashi 和 Mirko Viroli 工作直接直接结果，发表于第 16 届欧洲对象编程会议（ECOOP 2002）。这项工作建立在 Kresten Thorpe（Unifying Genericity）较早的工作的基础上，以及追溯到 Pierre 对 POOL (99) 关于变性的工作的长期传统之上。通配符在细节上与上述论文中描述的构造不同，特别是在使用了捕捉转换而非 Igarashi 和 Viroli 的操作的这一点上。关于通配符的正式说明，请参见 Miles Tersen、Erik Ernst 和 Christian Petersen 在第 12 届对象编程基础工作讨会（POOL 2005）上的论文。

# 示例 4.5.1-1. 无界通配符

```java
import java.util.Collection;
import java.util.ArrayList;

class Test {

    static void printCollection(Collection<?> c) {

        // 一个通配符

        for (Object o : c) {

            System.out.println(o);

        }

    }

    public static void main(String[] args) {

        Collection<String> cs = new ArrayList<>();

        cs.add("Hello");

        cs.add("world");

        printCollection(cs);

    }

}
```

注意，使用 `Collection<Object>` 作为输入参数 `c` 的类型是没有用的；该方法只能与类型为 `Collection<Object>` 的参数一起使用。相比，使用无界通配符允许传递任何类型的集合。这里是一个数组元素类型由通配符参数化的示例：

```java
public Method getMethod(Class<?>[] types) { ...
```

# 示例 4.5.1-2. 有边界通配符

```java
boolean addAll(Collection<? extends E> c)
```

在这里，方法是 `Collection<? extends E> c`。该方法只能与类型为 `Collection<E>` 的参数一起使用。另一种方法是使用泛型参数 `T`：

```java
<T> boolean addAll(Collection<T> c)
```

这种类型是灵活的，但请注意，在签名中使用的泛型类型是通配符。这反映了在方法或构造函数中，参数化类型是通配符的，除非通过捕捉转换将其返回为非泛型类型。

# 4.5.2 参数化类型的成员和构造函数

假设 `c` 是一个泛型类或接口声明，`C<T_1,...,T_n>` 是 `c` 的参数化，类型擦除后：

- 泛型类或接口声明的成员或构造函数是 `c`。
- 泛化类型 (§4.5) `G<T_1,...,T_n>` 的擦除是 `|G|`。

类型擦除还映射：
- 泛型方法或构造函数的签名 (§8.4.2) 映射到一个没有参数化类型或类型变量的签名。
- 方法返回值 (§8.4.5) 和泛型方法或构造函数的类型参数 (§8.4.4, §8.8.4) 在方法或构造函数签名被擦除时，也会经历擦除。

如果 `C<T_1,...,T_n>` 的参数化中的任何一个是通配符，那么：
- 泛型类或接口声明的成员或构造函数是 `c` 的类型擦除 (§5.1.10)。
- 泛型类或接口声明的擦除其类型参数是无界通配符。

这没有影响，因为在不进行捕捉转换的情况下无法访问参数化类型的成员，且在 `new` 关键字之后无法使用通配符 (§15.9)。

上一段的例外是当嵌套参数化类型用作 `instanceof` 运算符时 (§15.20.2)，此时不应用捕捉转换。

在泛型声明中声明的 `static` 成员必须使用对应于泛型的非泛型类型进行引用 (§6.1, §6.5.2, §6.5.2)，否则将发生编译错误。换句话说，通过使用参数化类型来引用泛型声明中声明的 `static` 成员是非非法的。

类型、值与变量

可具体化类型

## 4.7 可化类型 (Reifiable Types)

由于某些类型信息在编译期间会被擦除，并不是所有类型在运行时都是可用的。运行时完全可用的类型被称为可化类型（reifiable types）。

当且仅当满足以下条件之一时，类型是可化的：

- 它指向一个非泛型的类或接口类型声明。
- 它是一个参数化类型，其中所有的类型参数都是无界通配符（§4.5.1）。
- 它是一个原始类型（raw type）（§4.8）。
- 它是一个基本数据类型（§4.2）。
- 它是一个数组类型（§10.1），其元素类型 `\tau` 用逗号分隔，且 `\tau` 本身是可化的。

例如，如果一个泛型类 `X<T>` 有一个泛型成员类 `Y<U>`，那么类型 `X<??>` 是可化的，因为 `X<??>` 是可化的；而类型 `X<??>.Y<Object>` 不是可化的，因为 `Y<Object>` 不是可化的。

交叉类型（intersection type）不是可化的。

决定不使泛型类型可化是涉及 Java 编程语言类型系统最关键且最具争议的决定之一。

最终，该决定的最重要的动机是与现有代码的兼容性。从新的意义上说，新构造的添加对先前的代码没有影响。Java 编程语言只要在以前版本中编写的每个程序在新版本中保留其含义，它就与早期版本兼容。然而，这种可以被称为“语言兼容性”的观点纯粹是理论上的兴趣。真实的程序（即使是“Hello World”）是由多个编译单元组成的，这些单元由 Java SE 平台提供（例如 `lang.util` 中的元素）。实践中，最低要求是平台兼容性——即为之前的 Java SE 版本编写的任何程序在新版本中都能继续运行。

提供平台兼容性的一种方法是保持现有平台功能不变，仅添加新功能。例如，与其修改 `java.util` 中现有的 Collections 层次结构，不如引入一个利用泛型的新库。

这种方案的缺点是，Collection 库的现有客户端极难迁移到新库。Collections 用于在独立开发的模块之间交换数据；如果供应商决定切换到新的泛型库，供应商也必须分发两个版本的代码，以兼容其客户端。依赖于其他供应商代码的库在供应商库更新之前，无法修改为使用泛型。如果两个模块相互依赖，则必须同时进行更改。

显然，上述的平台兼容性并没有为像泛型这样无处不在的新特征的应用提供现实的路径。因此，泛型类型系统的设计寻求支持迁移兼容性（migration compatibility）。迁移兼容性允许现有代码在演进过程中利用泛型的优势，而不会在独立开发的软件模块之间施加依赖。

迁移兼容性的代价是，泛型类型系统的完全且健全的具体化是不可能的，至少在迁移进行期间。

## 4.8 原始类型 (Raw Types)

为了便于与非泛型的遗留代码交互，可以使用参数化类型（§4.5）的擦除（§4.6）或元素类型为参数化类型的数组类型（§10.1）的擦除作为类型。这种类型被称为原始类型（raw type）。

准确来说，原始类型由以下之一定义：

- 通过取泛型类型声明的名称而不带类型参数列表形成的引用类型。
- 元素类型为原始类型的数组类型。
- 原始类型 `R` 的非静态成员类型，且该类型未继承自 `R` 的父类或接口。

非泛型的类或接口类型不是原始类型。

为了理解为什么原始类型的非静态成员类型被认为是原始的，请考虑以下示例：

```java
class Outer<T>{

  T t;

  class Inner {

    T setOuter(T t1) { t = t1; return t; }

  }

}
```



Inner 成员的类型取决于 `Outer` 的类型参数。如果 `Outer` 是原始的，则 `Inner` 也必须被视为原始的，因为对于 `T` 没有有效的绑定。

# 类型、值与变量

## 原始类型

此规则仅适用于未继承的类型成员。依赖类型变量的被继承类型成员将根据本节稍后描述的“原始类型的父类型会被擦除”这一规则，其结果是作为原始类型被继承。

上述规则的另一个影响是，原始类型的泛型内部类本身只能作为原始类型使用：

```java
class Outer<T> {
    class Inner<S> {
        S;
    }
}
```

无法以部分原始类型（“稀有”类型）访问 `Inner`：

```java
Outer.Inner<Double> x = null; // 非法
Double d = x.s;
```

因为 `Outer` 本身是原始的，因此它所有的内部类（包括 `Inner`）都是原始的，因此无法向 `Inner` 传递任何类型参数。

原始类型的父类（相应为父接口）是泛型类型任何参数化版本的父类（父接口）的擦除。

未继承自其父类或父接口的原始类型的构造函数（§8.8）、实例方法（§8.4, §9.4）或非静态字段（§8.3）的类型，与其在对应泛型声明中的类型擦除相对应的原始类型。

原始类型 `c` 的静态方法或静态字段的类型，与其在泛型声明中的类型相同。

对于原始类型 `c`，向未继承自其父类或父接口的非静态成员传递类型参数是编译错误。

尝试将参数化类型作为原始类型是编译错误。

> 这意味着对“稀有”类型的限制延伸到了类型是参数化的情况：
>
> ```java
> Outer<Integer>.Inner x = null; // 非法
> ```
>
> 这是上述情况的相反。在遗留代码中，不使用类型参数。在非遗留代码中，我们应该正确地使用泛型。

类的父类型可以是原始类型。对类的成员访问被视为正常的，对父类型的访问也被视为正常的。在类的构造函数中，对父类型的调用被视为方法调用。

使用原始类型仅是为了兼容遗留代码而允许的。在 Java 语言引入泛型后编写的代码中使用原始类型是被强烈建议避免的。未来的 Java 版本可能会不允许使用原始类型。

为了确保类型规则的潜在违反始终被标记，对原始类型的某些访问将产生未检查警告。访问原始类型成员或构造函数的未检查警告规则如下：

- 在字段赋值时：如果字段访问表达式中的 `Primary`（§15.11）是原始类型，如果擦除改变了字段，则产生未检查警告。
- 在调用方法或构造函数时：如果类或接口类型（§15.12）是原始类型，如果擦除改变了任何形式参数类型，则产生未检查警告。
- 当形式参数类型没有变化（即使返回类型和/或 throws 变化）时，对于方法调用、读取字段或原始类型的类，不产生未检查警告。

> 注意，未检查警告与收窄引用转换（§15.6）、未检查转换（§15.9）、方法声明（§8.4.1, §8.4.8.3）以及某些表达式（§15.12.4, §15.13.2, §15.27.3）不同。

这里的警告涵盖了遗留消费者使用泛型库的情况。例如，库声明了一个具有 `Vector<?>` 字段 `f` 的泛型 `Foo extends String`，但消费者将整数 `Vector` 赋值给 `e`，其中 `e` 是原始类型。遗留消费者会收到警告，因为它可能为泛型库消费者造成污染（§41.2.2）。

（注意遗留消费者可以将来自库的 `Vector<String>` 赋值给其 `Vector` 而不接收警告。也就是说，Java 语言的子类型规则（§41.0.2）使得原始类型变量可以赋值参数化实例的任何类型。）

未检查转换的警告涵盖了相反的情况，即泛型消费者使用库。例如，库的一个方法具有 `Vector` 返回类型，但消费者将方法调用的结果赋值给 `Vector<String>` 变量。这是不安全的，因为原始 vector 可能具有与 `String` 不同的元素类型，但为了启用与旧留代码交互，使用未检查转换是允许的。未检查转换的警告表明，泛型消费者可能会在程序的其他地方遇到堆污染问题。

## 示例 4.8-1 原始类型

```java
class Cell<E> {
    E value;
    Cell(E v) { value = v; }
    E get() { return value; }
    void set(E v) { value = v; }
    public static void main(String[] args) {
        Cell x = new Cell<String>("abc");
        System.out.println(x.value); // OK, 类型为 Object
        System.out.println(x.get());  // OK, 类型为 Object
        x.set("def");               // 未检查警告
    }
}
```

## 示例 4.8-2 原始类型与继承

```java
import java.util.*;

class NonGeneric {
    Collection<Number> myNumbers() { return null; }
}

abstract class RawMembers<T> extends NonGeneric implements Collection<String> {
    static Collection<NonGeneric> cng = new ArrayList<NonGeneric>();
    public static void main(String[] args) {
        RawMembers<Number> cn = null;
        cn = rw.myNumbers(); // OK
        Iterator<String> is = rw.iterator(); // 未检查警告
        Collection<NonGeneric> cnn = rw.cng; // OK, 静态成员
    }
}
```



在此程序（并非为了运行）中，`RawMembers<T>` 继承了方法：

```
Iterator<String> iterator()
```

来自超接口 `Collection<String>`。原始类型 `RawMembers` 从 `Collection`（`Collection<String>` 的擦除类型）继承 `iterator()`，这意味着 `RawMembers` 中 `iterator()` 的返回类型是 `Iterator`。因此，将 `.iterator()` 转换为 `Iterator<String>` 并将 `rw.iterator()` 赋值给 `Iterator<String>` 需要未检查转换，因此会发出编译时的未检查警告。

相比之下，`RawMembers` 从 `NonGeneric` 类继承了 `myNumbers()`，后者的擦除类型是 `NonGeneric`。因此，`RawMembers` 中 `myNumbers()` 的返回类型没有被擦除，将 `rw.myNumbers()` 赋值给 `Collection<Number>` 不需要未检查转换，因此不会发出编译时的未检查警告。

同样，即使通过类型数组（ray）访问，静态成员也会返回其参数化类型。请注意，通过实例访问静态成员被认为是不良风格，是不鼓励的。

此示例揭示了原始类型的某些成员不会被擦除，即类型被参数化的静态成员，以及从非泛型超类型中继承的成员。

原始类型与通配符（wildcards）密切相关。两者都会在存在类型（existential types）上被擦除。原始类型可以被视为无界通配符类型。从历史上看，原始类型于通配符；它们最早在 GJ 中引入，并在 Gil Bracha、Martin Odersky、David Stoutamper 和 Philip Wadler 的论文《Making the future for the past: Adding Genericity to the Java Programming Language》中描述，该论文发表于 Proceedings of the ACM Conference on Object-Oriented Programming, Systems, Languages and Applications (OOPSLA 98)，1998年10月。

## 4.9 交集类型

交集类型的形式为 $T_1 \& \dots \& T_n$ ($n > 0$)，其中 $T_i$ ($1 \le i \le n$) 是类型。

交集类型可以从类型参数边界（4.4）和转换表达式（15.16）推导出；它们也出现在捕获转换（capture conversion，5.1.10）和最小上界计算（4.10.4）的过程中。

交集类型的值是指同时作为所有类型 $T_i$ ($1 \le i \le n$) 值的对象。

每个交集类型 $T_1 \& \dots \& T_n$ 都会产生一个名类或接口，用于标识交集类型的成员，如下：

- 对于每个 $T_i$ ($1 \le i \le n$)，令 $C_i$ 为最具体的类或数组类型，使得 $T_i <: C_i$。必须存在某个 $C_k$，使得对于任何 $i$ ($1 \le i \le n$) 都有 $C_k <: C_i$，否则将发生编译时错误。

- 对于 $1 \le j \le n$，如果 $T_j$ 是类型变量，则令 $T_j'$ 为一个其成员与 $T_j$ 的公共成员相同的接口；否则，如果 $T_j$ 是接口，则令 $T_j'$ 为 $T_j$。

- 如果 $C_k$ 是 `Object`，则产生一个名接口；否则，产生一个直接超类为 $C_k$ 的名类。该类或接口具有直接接口 $T'_1, \dots, T'_n$，并声明在交集类型出现的包中。

交集类型的成员是其所产生的类或接口的成员。值得关注交集类型与类型变量边界之间的区别。每个类型变量都会产生一个交集类型。这种交集类型通常是平凡的，由单个类型组成。边界的形式是限制的（只有第一个元素可以是类或类型变量，且边界中只能出现一个变量），以防止某些情况的发生。然而，捕获转换可能会导致创建边界更通用的类型，例如数组类型。

## 4.10 子类型

子类型和超类型关系是类型上的二元关系。一个类型的超类型是通过直接超类型关系的自反和传递闭包得到的，写作 $S >: T$，这在本节稍后定义。

- 对于每个 $U_i$ ($1 \le i \le k$)：

设 $ST(U_i)$ 为 $U_i$ 的超类型集合。

设 $EST(U_i)$ 为 $U_i$ 的擦除超类型集合为：

$EST(U_i) = \{ |W| \mid W \in ST(U_i) \}$ 其中 $|W|$ 是 $W$ 的擦除形式。

计算擦除类型集合的原因是为了处理类型集合包含泛型类型的若干不同参数化的情况。

例如，给定 `List<String>` 和 `List<Object>`，简单地取交集 $ST(List<String>) = \{ List<String>, Collection<String>, Object \}$ 和 $ST(List<Object>) = \{ List<Object>, Collection<Object>, Object \}$ 将得到一个集合 $\{ Object \}$，我们将会丢失其上界可以安全地假设为 `List` 的事实。

相比之下，$EST(List<String>) = \{ List, Collection, Object \}$ 和 $EST(List<Object>) = \{ List, Collection, Object \}$ 产生 $\{ List, Collection, Object \}$，这最终允许我们产生 `List<?>`。

- 对于 $EC$，即 $U_1 \dots U_k$ 的擦除候选集，为所有集合 $EST(U_i)$ ($1 \le i \le k$) 的交集。

- 对于 $MEC$，即 $U_1 \dots U_k$ 的最小擦除候选集，为：

$MEC = \{ v \mid v \in EC \}$，且对于所有 $W \notin EC$，并不存在 $W <: v$。

由于我们正在寻找更精确的类型，我们希望过滤掉所有作为其他候选者超类型的候选者。这就是 MEC 完成的任务。在我们的示例中，我们有 $EC = \{ List, Collection, Object \}$，因此 $MEC = \{ List \}$。下一步是为 $MEC$ 中的擦除类型恢复类型参数。

- 对于泛型类型的任意元素 $G$：

设 $G$ 的“相关”参数化 $Relevant(G)$ 为：

$Relevant(G) = \{ v \mid 1 \le i \le k: v \in ST(U_i) \text{ and } v = G<\dots> \}$

在我们的示例中，MEC 的唯一泛型元素是 `List`，且 $Relevant(List) = \{ List<String>, List<Object> \}$。我们现在将为 `List` 寻找一个包含 (4.5.1) 中 `String` 和 `Object` 的类型参数。

这是通过下面定义的最小包含（**lcp**）操作实现的。第一行定义了在集合上的 $lcp$（如 $Relevant(List)$），其为对包含集合元素的列表的操作。下一行定义了对该列表的操作，为对列表元素进行两两归约（pairwise reduction）。第三行定义了在参数化类型对 $(lcta)$ 上执行的 $lcp()$ 操作，这依赖于所有可能情况的最小包含类型参数 $(lcta)$ 概念。

设 $G$ 的“候选”参数化 $Candidate(G)$ 为泛型类型 $G$ 包含 $G$ 的所有相关参数化的最特定参数化：

$Candidate(G) = lcp(Relevant(G))$

其中 $lcp(U)$（最小参数化）为：

- $lcp(S) = lcp(e_1, \dots e_n)$ 其中 $e_i (1 \le i \le n)$ 在 $S$ 中
- $lcp(e_1, \dots e_n) = lcp(lcp(e_1, e_2), e_3, \dots, e_n)$
- $lcp(G<X_1, \dots, X_n>, G<Y_1, \dots, Y_n>) = G<lcta(X_1, Y_1), \dots, lcta(X_n, Y_n)>$
- $lcp(G<X_1, \dots, X_n>) = G<lcta(X_1), \dots, lcta(X_n)>$

且 $lcta(U, V)$（最小包含类型参数）为（假设 $U$ 和 $V$ 为类型）：

- 如果 $U = V$，则 $lcta(U, V) = U$，否则为 `? extends lub(U, V)`
- $lcta(U, ? extends V) = ? extends lub(U, V)$
- $lcta(U, ? super V) = ? super glb(U, V)$
- $lcta(? extends U, ? extends V) = ? extends lub(U, V)$
- $lcta(? extends U, ? super V) = ? super V$
- $lcta(? super U, ? super V) = ? super glb(U, V)$
- 如果 $U$ 的上界是 `Object`，则 $lcta(U) = ?$，否则为 `? extends lub(U, Object)`

其中 $glb()$ 见 §5.1.10。

- $lub(U_1 \dots U_k)$ 为：
$Best(W_1) \& \dots \& Best(W_k)$

其中 $W_i (1 \le i \le r)$ 是 MEC 的元素，即 $U_1 \dots U_k$ 的最小擦除候选集；

且，如果这些元素中的任何一个是泛型，我们使用（以恢复类型）：

$Best(x) = Candidate(x)$ 如果 $x$ 是泛型；否则为 $x$。

严格来说，此 $lub()$ 函数仅近似最小上界。形式上，可能存在某种类型 $T$，使得所有 $U_1 \dots U_k$ 都是 $T$ 的子类型。

$lub()$ 函数可能会产生无限类型。这是允许的，且 Java 语言必须识别此类情况并适当表示。无限类型的可能性源于递归调用。熟悉类型的读者应注意无限类型等同于。

## 4.10.5 类型投影

引入了一种合成类型 (4.10)。有时需要找到类型的上类型。同样，对于限制变量集合，类型 $T$ 的向上投影定义如下：

- 如果 $T$ 不包含任何限制变量，则结果为 $T$。

- 如果 $T$ 是参数化类类型或参数化接口类型，$G<A_1,...,A_n>$，如果 $1 \le j \le n$，可以从 $A_j$ 导出 $A_j'$；否则，结果未定义。

- 如果 $T$ 是交集类型，则对于 $T$ 的每个元素 $S$，结果为 $S$ 的向上投影。

- 如果 $T$ 是数组类型，$S[]$，则结果的组件类型为 $S$ 的向上投影。

对于限制变量集合，类型 $T$ 的向下投影是一个部分函数：

- 如果 $T$ 不包含任何限制变量，则结果为 $T$。

- 如果 $T$ 是限制变量，那么如果 $T$ 有下界且该下界的向下投影为 $L$，则结果为 $L$；如果 $T$ 没有下界，或者该下界的向下投影未定义，则结果未定义。

- 如果 $T$ 是包含限制变量的上界通配符，设 $U$ 为通配符的向上投影。$A_j'$ 为上界通配符，`? extends U`，如果通配符的向下投影未定义，则 $A_j'$ 未定义。

- 如果 $T$ 是包含限制变量的下界通配符，那么如果通配符的向下投影为 $L$，则 $A_j'$ 为下界通配符，`? super L`，如果向下投影未定义，则该结果为无界通配符，`?`。

- 如果 $T$ 是参数化类类型或参数化接口类型，$G<A_1,...,A_n>$，如果 $1 \le j \le n$，可以从 $A_j$ 导出 $A_j'$；否则，结果未定义。

- 如果 $r$ 是一个数组类型 $s[]$，则 $s$ 的向下投影为 $s'$，其结果为 $s'[]$；如果 $s$ 的向下投影未定义，则结果为未定义。

- 如果 $\tau$ 是一个交集类型，那么如果 $\tau$ 的*每个*元素的向下投影都是定义的，则其结果为一个交集类型，其元素为 $\tau$ 中各元素的向下投影；如果 $\tau$ 的*任意*元素的向下投影未定义，则结果为未定义。

与 $lub()$（下界类型，§4.10.4）类似，由于对类型变量的递归，向上投影和向下投影可能会产生无限类型。

## 4.11 类型使用的位置

类型使用在大多数类型的声明和某些表达式中。具体来说，有 16 处*类型上下文*使用了类型：

- 在声明中：
  1. 类声明中 `extends` 或 `implements` 子句中的类型 (§8.1.4, §8.1.5, §8.5, §9.5)
  2. 接口声明中 `extends` 子句中的类型 (§9.1.3, §8.5, §9.5)
  3. 方法的返回类型（包括注解类型元素的类型） (§8.4.5, §9.4, §9.6.1)
  4. 方法或构造函数 `throws` 子句中的类型 (§8.4.6, §8.8.5, §9.4)
  5. 泛型类、接口、方法或构造函数的类型参数声明中 `extends` 子句的类型 (§8.1.2, §9.1.2, §8.4.4, §8.8.4)
  6. 类或接口的字段声明中的类型（包括枚举常量） (§8.3, §9.3, §8.9.1)
  7. 方法、构造函数或 lambda 表达式的形式参数声明中的类型 (§8.4.1, §8.8.1, §9.4, §15.27.1)
  8. 方法接收器参数的类型 (§8.4)
  9. 局部变量声明中的类型 (§14.4, §14.14.1, §14.14.2, §14.20.3)
  10. 异常参数声明中的类型 (§14.20)

- 在表达式中：
  11. 显式构造函数调用语句、类实例创建表达式或方法调用表达式的显式类型参数列表中的类型 (§8.7.1, §15.9, §15.12)
  12. 未限定类实例创建表达式中，作为要实例化的类类型 (§15.9)，或要实例化匿名类的直接父类或直接父接口 (§15.9.5)
  13. 数组创建表达式中的元素类型 (§15.10.1)
  14. 类表达式转换运算符中的类型 (§15.16)
  15. `instanceof` 关系运算符后的类型 (§15.20.2)
  16. 在方法引用表达式 (§15.13) 中，作为查找成员方法的引用类型，或要构造的类类型或数组类型。

此外，类型还被用作：

- 上述任何语境中数组类型的数组类型；以及
- 上述任何语境中参数化类型的非通配符类型参数，或通配符类型参数的界（bound）。

最后，Java 编程语言中有三个表示类型用法的特殊术语：

- 无界通配符 (§4.5.1)
- 变长参数类型中的 `...` (§8.4.1)，用于表示数组类型
- 构造函数声明中类型的简单名 (§8.8)，用于表示所构建对象的类

类型上下文中的类型含义由以下内容给出：

- §4.2，用于基本类型
- §4.4，用于类型参数
- §4.5，用于参数化的类和接口类型，或者作为参数化类型中的类型参数，或作为参数化类型中通配符类型参数的界
- §4.8，用于原始（raw）的类和接口类型
- §4.9，用于类型参数界中的交集类型
- §6.5，用于泛型化不重要的上下文中的类和接口类型 (§6.1)
- §10.1，用于数组类型

某些类型上下文限制了引用类型如何被参数化：

- 以下类型上下文要求，如果一个类型是参数化引用类型，则它不能有通配符类型参数：
  - 类声明的 `extends` 或 `implements` 子句中 (§8.1.4, §8.1.5)
  - 接口声明的 `extends` 子句中 (§9.1.3)
  - 未限定类实例创建表达式中，作为要实例化的类类型 (§15.9)，或要实例化匿名类的直接父类或直接父接口 (§15.9.5)
  - 在方法引用表达式 (§15.13) 中，作为查找成员方法的引用类型，或要构造的类类型或数组类型。

- 以下类型上下文要求，如果类型是参数化引用类型，它必须包含通配符类型参数：
  - 数组创建表达式中的元素类型 (§15.10.1)
  - `instanceof` 关系运算符后的类型 (§15.20.2)

- 以下类型上下文不允许参数化引用类型，因为它们涉及异常：
  - 方法或构造函数的 `throws` 子句 (§8.4.6, §8.8.5, §9.4)
  - 构造函数声明中的类型 (§8.8)

## 4.12 变量

变量是一个存储位置，并有一个与之关联的类型（有时称为其编译时类型），该类型可以是基本类型 (§4.2)或引用类型 (§4.3)。

变量的值通过赋值 (§15.26)或通过前缀或后缀 `++`（递增）或 `--`（递减）运算符 (§15.14.2, §15.14.3, §15.15.1, §15.15.2) 来改变。

变量的值与其类型之间的兼容性由 Java 编程语言的设计予以保证，只要程序没有产生编译时未检查警告 (§4.12.2)。默认值 (§4.12.5) 是兼容的，且对变量的所有赋值操作都会进行赋值兼容性检查 (§5.2)，这种检查通常在编译时进行，但在涉及数组的单个用例中，会进行运行时检查。

### 4.12.1 基本类型变量

基本类型的变量始终持有该确切基本类型的原始值。

### 4.12.2 引用类型变量

类型为 $\tau$ 的类变量可以持有空引用，或指向类 $\tau$ 的实例或任何 $\tau$ 的子类的实例的引用。

接口类型的变量可以持有空引用，或指向实现该接口的任何类的任何实例的引用。

> 注意，变量并不保证总是引用其声明类型的子类型，而只能引用其声明类型的子类或子接口。这是由于下文讨论的堆污染的可能性。

如果 $T$ 是基本类型，那么类型为“$T$ 数组”的变量可以持有空引用，或指向任何类型为“$T$ 数组”的数组引用。

如果 $T$ 是引用类型，那么类型为“$T$ 数组”的变量可以持有空引用，或指向任何类型为“$S$ 数组”的数组引用，其中类型 $S$ 是类型 $T$ 的子类或子接口。

类型为 `Object[]` 的变量可以持有指向任何引用类型数组的引用。

类型为 `Object` 的变量可以持有空引用，或指向任何对象的引用，无论它是类实例还是数组。

泛型类型变量可能会引用一个并非该泛型类型的对象。这种情况被称为*堆污染*。

堆污染只有在程序执行了某些涉及原始类型的操作并产生编译时未检查警告 (§4.8, §5.1.6, §5.1.9, §8.4.1, §8.4.8, §9.4.1.2, §15.12.4.2)，或者程序通过一个原始或非泛型的子类型数组变量来别名不可重化（non-reifiable）元素的数组时，才会发生。

例如：



# 类型、值与变量

## 4.12 变量

### 4.12.2 堆污染

```java
List l = new ArrayList<Number>();

List<String> ls = l; // Unchecked warning
```

会产生未检查警告，因为在编译时（在编译类型检查规则的限制范围内）或运行时，无法确定变量 `l` 是否确实引用一个 `List<String>`。

如果执行该代码，就会产生堆污染，因为声明为 `List<String>` 的变量 `ls` 所引用的值实际上并不是一个 `List<String>`。

该问题在运行时无法识别，因为类型变量不是具具体化的，且实例不携带任何关于创建它们时所用类型参数的信息。

在给出的简单示例中，似乎应该在编译时识别该情况并给出错误是很容易的。然而，在通用（典型）情况下，变量 `l` 的值可能是单独编译的方法调用的结果，或者其值可能取决于任意控制流。因此，上述代码是非常危险的，而且是糟糕的风格。

此外，`Object[]` 是所有数组类型的子类型，这会导致不安全的别名发生，从而导致堆污染。例如，以下代码：

```java
static void main(List<String> stringLists) {
  Object[] array = stringLists;
  List<Integer> tmpList = Arrays.asList(42);
  array[0] = tmpList; // (1)
  String s = stringLists[0].get(0); // (2)
}
```

堆污染发生在 (1) 处，因为 `stringLists` 数组中引用 `List<String>` 的组件现在引用 `List<Integer>`。在同时存在通用子类型（`Object[]`）和不可重化类型（形式参数的声明类型，`List<String>`）的情况下，无法检测到这种污染。在 (1) 处没有理由给出未检查警告；尽管如此，在运行时，(2) 处会发生 `ClassCastException`。

在任何调用该方法时都会给出编译时未检查警告，因为 Java 编程语言的静态类型系统认为，创建一个数组元素类型 `List<String>` 的调用是类型安全的，它是不可重化的 (§15.12.4)。如果只有方法体相对于元数（arity）参数是类型安全的，那么程序员可以使用 `@SafeVar` 注解来消除调用处的警告（§9.6.4）。由于方法体相对于元数参数是类型安全的，那么程序员可以使用 `@SafeVar` 注解来消除调用处的警告（§9.6.4）。

### 4.12.3 变量的种类

变量共有八种类型：

- **类变量**：在类内部使用 `static` 关键字声明的字段（§8.3），或在接口内部的字段（§9.3）。
- **实例变量**：在类内部未使用 `static` 关键字声明的字段（§8.3.1）。
- **数组组件**：未命名变量，每当创建新数组时（§10 (Arrays), §15.10.2），它们会被创建并初始化为默认值（§12.5）。
- **方法参数**（§8.4.1）：传递给方法的参数值。
- **构造函数参数**（§8.8.1）：传递给构造函数的参数值。
- **Lambda 参数**（§15.27.1）：传递给 lambda 主体（§15.27.2）的参数值。
- **异常参数**：每当 `try` 语句的 `catch` 子句捕获异常时都会创建一个（§14.20）。
- **局部变量**：通过局部变量声明语句进行声明（§14.4）。

每当控制流进入块（§14.2）或 `for` 语句（§14.14）时，都会为立即包含在该特定块或 `for` 语句内部的局部变量声明语句中声明的每个局部变量创建一个新变量。

局部变量声明语句可以包含一个初始化变量的表达式。然而，带有初始化表达式的局部变量在局部变量声明语句被执行之前，是不会初始化的。（确定性赋值规则（§16 (Definite Assignment)）防止了在局部变量被初始化或被赋值其他值之前使用它。）当块或 `for` 语句执行完毕时，该局部变量实际上不再存在。

如果不是因为一种特殊情况，局部变量始终可以被视为在声明语句执行时就被创建了。这种特殊情况涉及 `switch` 语句（§14.11），在那种情况下，可能通过跳过局部变量声明语句来控制块。然而，由于确定性赋值规则（§16 (Definite Assignment)）的限制，由这种被跳过的局部声明所声明的局部变量在被赋值表达式（§15.26）赋值之前不能使用。

#### 示例 4.12.3-1. 不同类型的变量

```java
class Point {
    static int numPoints;      // numPoints 是类变量
    int x, y;                   // x 和 y 是实例变量
    int[] w = new int[10];     // w[0] 是一个数组组件
    void setX(int x) {          // x 是方法参数
        int oldx = this.x;      // oldx 是一个局部变量
        this.x = x;
    }
}
```

### 4.12.4 final 变量

变量可以声明为 `final`。`final` 变量只能被赋值一次。如果 `final` 变量未赋值，除非它在赋值之前被确定为未赋值，否则会导致编译时错误（§16 (Definite Assignment)）。

一旦 `final` 变量被赋值，它就始终包含相同的值。如果 `final` 变量持有对对象的引用，那么通过对对象的操作可能会更改对象的状态，但变量将始终引用同一个对象。这也适用于数组，因为数组是对象；如果 `final` 变量持有对数组的引用，通过对数组的操作可能会更改数组的组件，但该变量将始终引用同一个数组。

空 `final`（blank final）是一个声明中缺少初始化器的 `final` 变量。

常量变量（constant variable）是基本类型或 `String` 类型的 `final` 变量，并用常量表达式进行初始化（§15.28）。一个变量是否为常量变量可能对类初始化（§12.4.1）、二进制兼容性（§13.1）、可达性（§14.21）以及确定性赋值（§16.1.1）影响。

三类变量被隐式声明为 `final`：接口的字段（§9.3）、作为 `try-with-resources` 语句的资源声明的局部变量（§14.20.3）、以及多异常 `catch` 子句的异常参数（§14.20）。单异常 `catch` 子句的异常参数从不被隐式声明为 `final`，但可能是有效 `final`（effectively final）。

#### 示例 4.12.4-1. final 变量

声明 `final` 变量可以作为有用的文档，说明其值不会改变，并有助于避免编程错误。在程序中：

```java
class Point {
  int x, y;
  int useCount;
  Point(int x, int y) { this.x = x; this.y = y; }
  static final Point origin = new Point(0, 0);
}
```

类 `Point` 声明了一个 `final` 变量 `origin`。`origin` 变量持有对对象的引用，该对象是 `Point` 类的实例，其坐标为 (0, 0)。变量 `Point.origin` 的值永远无法改变，因此它始终引用同一个 `Point` 对象，即由初始化器创建的那个。然而，对此 `Point` 对象的操作可能会改变它的状态——例如，修改它的 `useCount`，甚至（误导地）修改它的 `x` 或 `y` 坐标。

某些未声明为 `final` 的变量被视为有效 `final`（effectively final）：

- 如果一个声明中带有初始化器的局部变量（§14.4.2）满足以下所有条件，则它是有效 `final` 的：
  - 它没有声明为 `final`。
  - 它从没有出现在赋值表达式的左侧（§15.26）。（注意，包含初始化器的局部变量声明符不是赋值表达式。）
  - 它从没有出现在前缀或后置增或减运算符的操作数上（§15.14, §15.15）。
- 如果一个声明符缺少初始化器的局部变量满足以下所有条件，则它是有效 `final` 的：
  - 它没有被声明为 `final`。
  - 每当它出现在赋值表达式的左侧时，在赋值之前它被确定为未赋值且未被确定赋值；也就是说，在赋值表达式右侧之后它被确定为未赋值且未被确定赋值（§16 (Definite Assignment)）。
  - 它从没有出现在前缀或后置增或减运算符的操作数上。

如果一个变量是有效 `final`，在它的声明中添加 `final` 修饰符不会引入任何编译时错误。相反，如果一个局部变量在声明中添加 `final` 不报错，它是有效 `final`。

### 4.12.5 变量的初始值

程序中的每个变量在使用之前必须有一个值：

- 每个类变量、实例变量或数组组件在创建时用默认值初始化（§15.9）：
  - `byte` 的默认值为零，即 `(byte) 0`。
  - `short` 的默认值为零，即 `(short) 0`。
  - `int` 的默认值为零。
  - `long` 的默认值为零，即 `0L`。
  - `float` 的默认值为正零，即 `0.0f`。
  - `double` 的默认值为正零，即 `0.0d`。
  - `char` 的默认值为空字符，即 `'\u0000'`。
  - `boolean` 的默认值为 `false`。
  - 所有引用类型（§4.3）的默认值为 `null`。
- 方法参数（§8.4.1）用方法调用者提供的值初始化（§15.12）。
- 构造函数参数（§8.8.1）用类实例表达式（§15.9）或显式构造函数调用（§8.7）提供的值初始化。
- 异常参数（§14.20）用表示异常的抛出对象初始化（§11.3, §14.18）。
- 局部变量（§14.4）在使用前被显式赋予一个值，通过初始化（§14.4）或赋值（§15.26），其方式可以使用确定性赋值规则（§16 (Definite Assignment)）进行验证。

#### 示例 4.12.5-1. 变量的初始值

```java
class Point {
    static int npoints;
    int x, y;
    Point root;
}

class Test {
    public static void main(String[] args) {
        System.out.println("npoints=" + Point.npoints);
        Point p = new Point();
        System.out.println("p.x=" + p.x + ", p.y=" + p.y);
        System.out.println("p.root=" + p.root);
    }
}
```

该程序输出：

```
npoints=0
p.x=0, p.y=0
p.root=null
```

说明了 `npoints` 的默认初始化，这发生在类 `Point` 准备阶段（§12.3.2），以及 `x`、`y` 和 `root` 的默认初始化，这发生在实例化新的 `Point` 时。有关类和接口加载、链接和初始化的所有方面的完整描述，以及关于实例化类以创建新类实例的描述，请参阅 §12 (Execution)。

### 4.12.6 类型、类与接口

在 Java 编程语言中，每个变量和每个表达式都具有一个可以在编译时确定的类型。该类型可以是基本类型，也可以是引用类型。引用类型包括类类型和接口类型。引用类型通过类型声明引入，其中包括类声明（§8.1）和接口声明（§9.1）。我们经常使用“类型”一词来指代类或接口。

在 Java 虚拟机中，每个对象都属于某个特定的类：即在产生对象的创建过程中被提到的类（§15.9），或者使用其 `Class` 调用反射方法来产生对象的类，或者是通过字符串拼接运算符（+15.18.1）隐式创建对象的 `String` 类。这个类被称为对象的类。一个对象被认为其类的实例，也是该类所有父类的实例。

每个数组也都有一个类。为数组对象调用的 `getClass()` 方法将返回一个类对象（类型为 `Class`），该类对象表示该数组的类（§10.8）。

变量的编译时类型总是被声明的，而表达式的编译时类型可以在编译时推断。编译时类型限制了变量在运行时可以持有的值，或表达式在运行时可以产生的值。如果运行时值是一个非空引用，它指向一个具有某个类的对象或数组，且该类必然与编译时类型兼容。

尽管变量或表达式的编译时类型可能是接口类型，但类型为接口类型的变量或表达式可以引用任何其类实现了（§8.1）该接口的对象。

有时，一个变量或表达式被认为具有“运行时类型”。这指的是运行时变量或表达式的值所指向的对象的类，前提是该值不为空。

编译时类型与运行时类型之间的对应关系是不完全的，原因有二：

- 在运行时，类和接口是由 Java 虚拟机使用类加载器加载的。每个类加载器都定义了它自己的一组类和接口。因此，两个加载器可能会加载相同的类或接口定义，但在运行时产生不同的类或接口。结果，如果加载它的类加载器不一致，编译正确的代码可能会在链接阶段失败。更多信息请参阅 Sheng Liang 和 Gilad Bracha 发表在 *Proceedings of OOPLA '98, as ACM SIGPLAN Notices, Volume 33, Number 10, October 1998, pages 36-44* 上的论文《The Java Virtual Machine Specification, Java SE 11》。
- 类型变量（§4.4）和类型参数（§4.5.1）在运行时不会被具体化（reified）。因此，运行时的同一个类或接口代表了编译时的多个参数化类型（§4.5）。具体而言，泛型类型的所有编译参数化（§8.1.2, §9.1.2）共享单一的运行时表示。

在某些情况下，参数化类型的变量可能会指向一个并非该类型的对象。这种情况被称为堆污染（§4.12.2）。变量将始终指向一个代表该参数化类型的类的实例。

#### 示例 4.12.6-1. 变量的类型与对象的类

```java
interface Colorable {
    void setColor(byte r, byte g, byte b);
}

class Point {
    int x, y;
}

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



## 示例 4.12.6-1. 变量的类型与对象的类

```java
interface Colorable {
    void setColor(byte r, byte g, byte b);
}

class Point {
    int x, y;
}

class ColoredPoint extends Point implements Colorable {
    byte r, g;
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

- 类 `Test` 中 `main` 方法的局部变量 `p` 类型为 `Point`，初始被赋值为 `Point` 类新实例的引用。
- 局部变量 `cp` 同样类型为 `ColoredPoint`，初始被赋值为 `ColoredPoint` 类新实例的引用。
- 将 `cp` 的值赋值给变量 `p` 会导致 `p` 持有一个 `ColoredPoint` 对象的引用。这是允许的，因为 `ColoredPoint` 是 `Point` 的子类，所以类 `ColoredPoint` 与类型 `Point` 是赋值兼容的 (§5.2)。一个 `ColoredPoint` 对象包含了对 `Point` 所有方法的支持。除了其特定的字段 `r`、`g` 和 `b` 之外，它还有 `Point` 类的字段，即 `x` 和 `y`。
- 局部变量 `c` 的类型是接口类型 `Colorable`，因此它可以持有任何其类实现了 `Colorable` 的对象的引用；具体而言，它可以持有一个 `ColoredPoint` 的引用。

注意，表达式 `new Colorable()` 是无效的，因为无法创建接口的实例，只能创建类的。然而，表达式 `new Colorable() {public void setColor...}` 是有效的，因为它声明了一个实现了 `Colorable` 接口的匿名类 (§15.9.5)。

# 第 5 章 转换与上下文

在 Java 编程语言中编写的表达式要么不产生结果 (§15.1)，要么具有可以在编译时推断的类型 (§15.3)。当一个表达式出现在许多上下文中时，它必须与该上下文兼容；这种类型被称为目标类型。当表达式出现在许多上下文中时，通过以下两种方式实现其与上下文的兼容性：

- 首先，对于某些表达式（多态表达式 §15.2），目标类型会受到推断出的运行时表达式类型的影响。
- 其次，在表达式类型被推断后，某些情况下可以执行目标类型的隐式转换。

如果运行时值是一个非空引用，它指向一个具有某个类的对象或数组，且该类必然与编译时类型兼容。

尽管变量或表达式的编译时类型可能是接口类型，但类型为接口类型的变量或表达式可以引用任何其类实现了 (§8.1) 该接口的对象。

有时，一个变量或表达式被认为具有“运行时类型”。这指的是运行时变量或表达式的值所指向的对象的类，前提是该值不为空。

编译时类型与运行时类型之间的对应关系是不完全的，原因有二：

- 在运行时，类和接口是由 Java 虚拟机使用类加载器加载的。每个类加载器都定义了它自己的一组类和接口。因此，两个加载器可能会加载相同的类或接口定义，但在运行时产生不同的类或接口。结果，如果加载它的类加载器不一致，编译正确的代码可能会在链接阶段失败。更多信息请参阅 Sheng Liang 和 Gilad Bracha 发表在 *Proceedings of OOPLA '98, as ACM SIGPLAN Notices, Volume 33, Number 10, October 1998, pages 36-44* 上的论文《The Java Virtual Machine Specification, Java SE 11》。
- 类型变量 (§4.4) 和类型参数 (§4.5.1) 在运行时不会被具体化（reified）。因此，运行时的同一个类或接口代表了编译时的多个参数化类型 (§4.5)。具体而言，泛型类型的所有编译参数化 (§8.1.2, §9.1.2) 共享单一的运行时表示。

在某些情况下，参数化类型的变量可能会指向一个并非该类型的对象。这种情况被称为堆污染 (§4.12.2)。变量将始终指向一个代表该参数化类型的类的实例。

## 示例 5.0-1. 编译时与运行时的转换

- `Object` 转换为 `Thread` 需要在运行时检查，以确保运行时值确实是 `Thread` 类或其子类的实例；如果不是，则抛出异常。
- `Thread` 转换为 `Object` 不需要运行时操作；`Thread` 是 `Object` 的子类，因此任何 `Thread` 类型的引用都是有效的 `Object` 类型。
- `int` 转换为 `long` 需要对 32 位整数值进行符号扩展到 64 位长表示。不会丢失信息。
- `double` 转换为 `long` 需要从 64 位浮点值到 64 位整数表示的非平凡转换。根据实际运行时值，可能会丢失信息。

Java 编程语言中可能的转换被分为几大类：

- 恒等转换
- 宽基本类型转换
- 窄基本类型转换
- 拓宽引用类型转换
- 窄引用类型转换
- 装箱转换
- 解箱转换
- 未检查转换
- 捕获转换
- 字符串转换
- 值集转换

存在六种转换上下文，多态表达式可能会受到上下文的影响或发生隐式转换。每种上下文对于多态表达式类型都有不同的规则，并允许上述类别中的某些转换而非其他。

## 转换上下文

- **严格调用上下文**（§5.3, §15.9, §15.12）：在此上下文中，参数被绑定到构造函数或方法的形式参数上。可能会发生原始类型拓宽、引用拓宽以及未检查的转换。
- **宽松调用上下文**（§5.3, §15.9, §15.12）：在此上下文中，与严格调用上下文类似，参数被绑定到形式参数上。如果仅使用严格调用上下文找不到合适的声明，则方法或构造函数的调用可能会提供此上下文。除了拓宽和未检查转换外，此上下文还允许装箱和拆箱转换发生。
- **字符串上下文**（§5.4, §15.18.1）：在此上下文中，任何类型的值都会转换为 `String` 类型的对象。
- **强制转换上下文**（§5.5）：在此上下文中，表达式的值转换为强制转换符（§15.16）指定的类型。强制转换上下文比赋值或宽松调用上下文更具包含性，允许除字符串转换以外的任何特定转换，但对引用类型的某些情况将在运行时检查其正确性。
- **数值上下文**（§5.6）：在此上下文中，数值操作符的操作数可能会拓宽到公共类型，以便执行操作。

“转换”（conversion）一词也用于泛指地描述在特定上下文中允许的转换。例如，我们说局部变量的初始化表达式受限于“赋值转换”，这意味着根据赋值上下文的规则将为该表达式隐式选择一个特定的转换。

## 示例 5.0-2. 各种上下文中的转换

```java
class Test {
    public static void main(String[] args) {
        // 将 float 字面量转换为 int 类型的
        // 强制转换 (5.4)。如果没有使用强制转换符，这将
        // 导致编译错误，因为这是一个收窄转换 (5.1.3):
        int i = (int)12.5f;

        // 对 i 的 int 值进行字符串转换 (5.4):
        System.out.println("(int)12.5f==" + i);

        // 将 i 的值转换为 float 类型的赋值转换 (5.2)。
        // 这是一个拓宽转换 (5.1.2):
        float f = i;

        // 对 f 的 float 值进行字符串转换:
        System.out.println("after float widening: " + f);

        // 将 i 的值转换为 float 类型的数值提升 (5.6)
        // float。这是一个二元数值提升。
        // 提升后，操作类型为 float*float：
        System.out.print(f);
        f = f * i;

        // 对 i 和 f 的两次字符串转换：
        System.out.println("***" + i + "===" + f);

        // 将 f 的值转换为 double 类型的调用转换 (5.3)，
        // 这样做是必要的，因为方法 Math.sin 
        // 只接受 double 类型参数：
        double d = Math.sin(f);

        // 对 f 和 d 的两次字符串转换：
        System.out.println("Math.sin(" + f + ")==" + d);
    }
}
```

该程序产生输出：

```
(int)12.5f==12
after float widening: 12.0
12.0*12==144.0
Math.sin(144.0)==-0.49102159389846934
```



## 5.1 转换的种类

Java 编程语言中的特定类型转换分为 13 类。

### 5.1.1 恒等转换

对于任何类型，都允许从该类型到相同类型的转换。

这看起来可能很平凡，但它有两个实际意义。首先，它允许一开始就拥有所需的类型，从而允许简单的规则：每个表达式都受转换限制，即使只是平凡的恒等转换。其次，这意味着允许程序为了清晰而包含冗余的强制转换符。

### 5.1.2 原始类型拓宽转换

在原始类型上的 19 种特定转换被称为原始类型拓宽转换：

- `byte` 到 `short`、`int`、`long`、`float` 或 `double`
- `short` 到 `int`、`long`、`float` 或 `double`
- `char` 到 `int`、`long`、`float` 或 `double`
- `int` 到 `long`、`float` 或 `double`
- `long` 到 `float` 或 `double`
- `float` 到 `double`

在以下情况下，由于数值值被精确保留，原始类型拓宽转换不会丢失数值值整体幅度的信息：

- 从一种整数类型到另一个整数类型
- 从 `byte`、`short` 或 `char` 到浮点类型
- 从 `int` 到 `double`
- 在 `strictfp` 表达式中从 `float` 到 `double` (§15.64)

非 `strictfp` 的 `float` 到 `double` 的原始类型拓宽转换可能会丢失转换值整体幅度的信息。

从 `int` 到 `float`、从 `long` 到 `float` 或从 `long` 到 `double` 的原始类型拓宽转换可能会导致精度丢失——即结果可能会丢失该值的某些低位。在这种情况下，生成的浮点值将是使用 IEEE 754 舍入最近模式（§4.2）的整数值的正确舍入版本。

有符号整数值到整数类型的拓宽转换会将整数值的补码表示扩展以填充更宽的格式。

`char` 到整数类型 `T` 的拓宽转换会将 `char` 值的表示扩展以填充更宽的格式。

尽管可能会发生精度丢失，原始类型拓宽转换永远不会导致运行时异常 (§11.1.1)。

#### 示例 5.1.2-1. 原始类型拓宽转换

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

这表明在从 `int` 类型到 `float` 类型的转换过程中丢失了信息，因为 `float` 类型的值精度无法达到九位有效数字。

### 5.1.3 原始类型收窄转换

在原始类型上的 22 种特定转换被称为原始类型收窄转换：

- `short` 到 `byte` 或 `char`
- `char` 到 `byte` 或 `short`
- `int` 到 `byte`、`short` 或 `char`
- `long` 到 `byte`、`short`、`char` 或 `int`
- `float` 到 `byte`、`short`、`char`、`int` 或 `long`
- `double` 到 `byte`、`short`、`char`、`int`、`long` 或 `float`

原始类型收窄转换可能会丢失数值值整体幅度的信息，还可能丢失精度和范围。

从 `double` 到 `float` 的原始类型收窄转换受 IEEE 754 规则（§4.2）的约束。这种转换可能会丢失精度，也会丢失范围。从有符号整数到整数类型的收窄转换将丢弃所有低位。

`char` 到整数类型 `r` 的收窄转换同样丢弃所有低位。从浮点数到整数类型的收窄转换分两个步骤：

1. 第一步中，将浮点数转换为 `long`（如果 `r` 是 `long`）或转换为 `int`（如果 `r` 是 `byte` 或 `char`），如下：
   - 如果浮点数是 `NaN` (§4.2.3)，第一步的结果为 0。
   - 否则，如果浮点数不是无穷大，根据向零舍入（§4.2）转换为整数：
     - 如果 `r` 是 `long`，且该整数值可以用 `long` 表示，则第一步的结果为 `long` 值。
     - 否则，如果该整数值可以用 `int` 表示，则第一步的结果为 `int` 值。
   - 否则，以下两种情况之一可能成立：
     - 值太小（负幅值或负无穷大），第一步的结果是 `int` 或 `long` 的最小值。
     - 值太大（正幅值或正无穷大），第一步的结果是 `int` 或 `long` 的最大值。

2. 第二步中：
   - 如果 `r` 是 `int` 或 `long`，转换的结果为第一步的结果。
   - 如果 `r` 是 `byte`、`char` 或 `short`，转换的结果是对第一步结果到 `r` 的收窄转换 (§5.1.3)。

尽管可能会溢出、下溢或其他信息丢失，但收窄转换永远不会导致运行时异常。

#### 示例 5.1.3-1. 转换与语境

```java
System.out.println("byte: " + (byte) fmin + ".." + (byte) fmax);
```

该程序产生输出：

```
long: -9223372036854775808..9223372036854775807
int: -2147483648..2147483647
short: 0..-1
char: 0..65535
byte: 0..-1
```

`char`、`int` 和 `long` 的结果是令人惊讶的，它们生成了该类型可表示的最小值和最大值。

`byte` 和 `short` 的结果丢失了数值的符号位和大小的信息，并且丢失了精度。可以通过检查 `int` 最小值和最大值的低位来理解这些结果。最小 `int` 的十六进制表示为 `0x80000000`，最大值为 `0xffffff`。这解释了 `short` 16 位的值，即 `0x0000` 和 `0xffff`；它解释了 `char` 结果，它们也是这些值的 16 位，即 `'\u0000'` 和 `'\uffff'`；它解释了 `byte` 结果，它们是这些值的 8 位，即 `0x00` 和 `0xff`。

#### 示例 5.1.3-2 丢失信息的窄化转换

```java
class Test {
    public static void main(String[] args) {
        // int 到 short 的窄化会丢失高位：
        System.out.println("short: " + (short)0x12345678=="0x" + Integer.toHexString((short)0x12345678));
        // 对于 byte 来说过大的 int 值改变符号和大小：
        System.out.println("byte: " + (byte)255);
        // 对于 int 过大的 float 值得到最大的 int 值：
        System.out.println("int: " + (int)1e20== + (int)1e20);
        // NaN 转换为 int 产生零：
        System.out.println("int: " + (int)Float.NaN);
        // 对于 float 太大的 double 识别为无穷大：
        System.out.println("float: " + (float)-e100== + (float)-e100);
        // 对于 float 太小的 double 值下溢为零：
        System.out.println("float: " + (float)e-50== + (float)e-50);
    }
}
```

该程序产生输出：

```
(short) 0x12345678==0x5678
(byte) 255==-1
(int) 1e20f=-2147483647
(int)NaN==0
(float)-1e100==Infinity
(float)1e-50==0.0
```



## 5.1.4 原始类型的宽化与窄化转换

以下转换结合了原始类型的宽化和窄化转换：

- 从 `byte` 到 `char`

首先，通过原始类型宽化转换 (§5.1.2) 将 `byte` 转换为 `int`，然后通过原始类型窄化转换 (§5.1.3) 将结果 `int` 转换为 `char`。

## 5.1.5 宽化引用转换

从任何引用类型 `s` 到任何引用类型 `t` 都存在宽化引用转换，前提是 `s` 是 `t` 的子类型 (§4.10)。

宽化引用在运行时永远不需要特殊的动作，因此在运行时永远不会抛出异常。它们由将引用视为具有某种其他类型组成，而这种方式在编译时可以被证明是正确的。

> 空类型不是引用类型 (§4.1)，因此不存在从空类型到引用类型的宽化引用转换。然而，许多转换显式允许空类型转换为引用类型。

## 5.1.6 窄化引用转换

窄化引用转换将引用类型 `s` 的表达式视为不同引用类型 `t` 的表达式，其中 `s` 不是 `t` 的子类型。支持的类型对定义在 §5.1.6 中。与宽化引用转换不同，类型不需要直接相关。但是，当可以静态证明没有值可以同时属于两种类型时，存在禁止某些类型对转换的限制。

窄化引用转换可能需要在运行时测试，以验证类型 `s` 的值是类型 `t` 的合法值。然而，由于运行时缺乏泛化类型信息，某些转换无法通过运行时测试完全验证；它们在编译时被标记 (§5.1.6.2)。

### 5.1.6.1 允许的窄化引用转换

如果以下所有条件均真，则存在从引用类型 `s` 到引用类型 `t` 的窄化引用转换：

- `s` 不是 `t` 的子类型 (§4.10)
- 如果存在泛化类型 `x` 是 `t` 的父类型，且存在泛化类型 `y` 是 `s` 的父类型，且 `x` 和 `y` 的擦除相同，且 `x` 和 `y` 不是不同的 (§4.5)。

以 `java.util` 包为例，不存在从 `ArrayList<String>` 到 `ArrayList<Object>` 的转换，因为 `x` 和 `y` 的擦除相同；不存在从 `ArrayList<String>` 到 `List<Object>` 的转换，因为泛化类型是不同的。由于静态证明没有值可以同时属于两种类型，禁止了某些类型对之间的转换。

窄化引用转换可能需要在运行时测试，以验证类型 `s` 的值是类型 `t` 的合法值。然而，由于运行时缺乏泛化类型信息，某些转换无法通过运行时测试完全验证；它们在编译时被标记 (§5.1.6.2)。

### 5.1.6.2 已检查与未检查的窄化引用转换

窄化引用转换是*已检查*或*未检查*的。这些术语指的是 Java 虚拟机能够或不能验证转换的正确性。

如果引用转换是未检查的，则 Java 虚拟机将无法完全验证其正确性，可能导致堆污染 (§4.12.2)。为了向程序员标记这一点，未检查的窄化引用转换会导致编译时“未检查警告”，除非被 `@SuppressWarnings` (§9.4.5) 抑制。相比之下，如果窄化引用转换不是未检查的，它是已检查的；Java 虚拟机将完全验证其类型正确性，因此编译时不给出警告。

未检查的窄化引用转换如下：

- 从类型 `s` 到泛型类或接口类型 `T` 的窄化引用转换是未检查的，除非至少满足以下条件之一：
    - `T` 的所有参数都是无界通配符。
    - `T <:` 且 `s` 除了 `T` 之外没有子类型 `x`，其类型参数不包含在 `T` 的类型参数中。
- 从类型 `s` 到类型变量 `t` 的窄化引用转换是未检查的。
- 从类型 `s` 到交叉类型 `T_1 & ... & T_n` (1 \le i \le n) 的窄化引用转换，如果存在 `T_i` 不是 `T_i` 的子类型且存在从 `s` 到 `T_i` 的窄化引用转换，则是未检查的。

### 5.1.6.3 运行时窄化引用转换

所有已检查的窄化引用转换都需要在运行时进行有效性检查。这些转换主要是未参数化的类和接口类型。

某些未经检查的收缩引用转换需要在运行时进行有效性检查。这取决于该未经检查的引用转换是完全未检查的还是部分未检查。部分未检查的收缩引用转换需要在运行时进行有效性检查，而完全未检查的收缩引用转换则不需要。

这些术语指的是在视为原始（raw）类型时，转换涉及的类型兼容性。如果转换在概念上是“向上转型”（upcast），则不需要运行时测试，因为该转换在 Java 虚拟机非泛型类型中是合法的。相反，如果转换在概念上是“向下转型”（downcast），则转换是部分未检查的；即使在 Java 虚拟机非泛型类型中，也需要运行时检查来测试转换涉及的（原始）类型的兼容性。

以 `java.util` 包中的类型为例，从 `ArrayList<String>` 到 `Collection<?>` 的转换是完全未检查的，因为在 Java 虚拟机中原始类型 `ArrayList` 是原始类型 `Collection` 的子类型。相比之下，从 `Collection<?>` 到 `ArrayList<String>` 的转换是部分未检查的，因为在 Java 虚拟机中原始类型 `Collection` 不是原始类型 `ArrayList` 的子类型。

未经检查的收缩引用转换的分类如下：

- 从 `s` 到非交集类型 `T` 的未经检查收缩引用转换，如果 `|s| < |T|`，则它是完全未检查的。否则，它是部分未检查的。
- 从 `s` 到交集类型 `T_1 & ... & T_n` 的未经检查收缩引用转换，如果对于所有 `i` (1 \le i \le n)，要么 `s <: T_i` 或者从 `s` 到 `T_i` 的收缩引用转换是完全未检查的，则它是完全未检查的。否则，它是部分未检查的。

已检查或部分未检查收缩引用转换的运行时有效性如下：

- 如果运行时值为 `null`，则允许转换。
- 否则，令 `R` 为该值所引对象的类，令 `T` 为被转换类型的擦除（§4.6）：
  - 如果 `R` 是普通类（不是数组类）：
    - 如果 `T` 是类类型，则 `R` 必须是与 `T` 相同的类（§4.3.4）或是 `T` 的子类，否则将抛出 `ClassCastException`。
    - 如果 `T` 是接口类型，则 `R` 必须实现接口 `T`（§8.1.5），否则将抛出 `ClassCastException`。
  - 如果 `T` 是数组类型，则抛出 `ClassCastException`。
  - 如果 `R` 是接口：
    注意，当这些规则首次应用于任何给定的转换时，`R` 不能是接口，但如果递归应用这些规则，`R` 可能是一个接口，因为运行时引用值可能指向一个元素类型为接口类型的数组。
    - 如果 `T` 是类类型，则 `T` 必须是 `Object`（§4.3.2），否则将抛出 `ClassCastException`。
    - 如果 `T` 是接口类型，则 `R` 必须是与 `T` 相同的接口或 `T` 的子接口，否则将抛出 `ClassCastException`。
    - 如果 `T` 是数组类型，则抛出 `ClassCastException`。
  - 如果 `R` 是表示数组类型 `RC[]` 的类，即组件类型为 `RC` 的元素的数组：
    - 如果 `T` 是类类型，则 `T` 必须是 `Object`（§4.3.2），否则将抛出 `ClassCastException`。
    - 如果 `T` 是接口类型，则 `T` 必须是类型 `java.io.Serializable` 或 `Cloneable`（数组实现的唯一接口），否则将抛出 `ClassCastException`。
    - 如果 `T` 是数组类型 `TC[]`，即组件类型为 `TC` 的元素的数组，除非 `TC` 和 `RC` 都是基本数据类型，或者 `TC` 和 `RC` 都是引用类型且被这些运行时类型的递归应用允许，否则将抛出 `ClassCastException`。

如果转换是交集类型 `T_1 & ... & T_n`，则对于所有 `i` (1 \le i \le n)，从 `s` 到 `T_i` 的转换所需的任何运行时检查对于转换为交集类型的转换也是需要的。

## 5.1.7 装箱转换 (Boxing Conversion)

装箱转换将基本类型的表达式视为相应引用类型的表达式。具体而言，以下九种转换被称为*装箱转换*：

- 从类型 `boolean` 到类型 `Boolean`
- 从类型 `byte` 到类型 `Byte`
- 从类型 `short` 到类型 `Short`
- 从类型 `char` 到类型 `Character`
- 从类型 `int` 到类型 `Integer`
- 从类型 `long` 到类型 `Long`
- 从类型 `float` 到类型 `Float`
- 从类型 `double` 到类型 `Double`
- 从 `null` 类型到 `null` 类型

此规则是必要的，因为条件运算符（§15.25）对其操作数的类型应用装箱转换，并将结果用于进一步的计算。

在运行时，装箱转换按如下方式进行：

- 如果 `p` 是 `boolean` 类型对应的值，则装箱转换将 `p` 转换为类和类型为 `Boolean` 的引用，使得 `r.booleanValue() == p`
- 如果 `p` 是 `byte` 类型对应的值，则装箱转换将 `p` 转换为类和类型为 `Byte` 的引用，使得 `r.byteValue() == p`
- 如果 `p` 是 `char` 类型对应的值，则装箱转换将 `p` 转换为类和类型为 `Character` 的引用，使得 `r.charValue() == p`
- 如果 `p` 是 `short` 类型对应的值，则装箱转换将 `p` 转换为类和类型为 `Short` 的引用，使得 `r.shortValue() == p`
- 如果 `p` 是 `int` 类型对应的值，则装箱转换将 `p` 转换为类和类型为 `Integer` 的引用，使得 `r.intValue() == p`
- 如果 `p` 是 `long` 类型对应的值，则装箱转换将 `p` 转换为类和类型为 `Long` 的引用，使得 `r.longValue() == p`
- 如果 `p` 是 `float` 类型对应的值：
  - 如果 `p` 不是 NaN，装箱转换将 `p` 转换为类和类型为 `Float` 的引用，使得 `r.floatValue() == p`
  - 否则，装箱转换将 `p` 转换为类和类型为 `Float` 的引用，使得 `r.isNaN()` 为真
- 如果 `p` 是 `double` 类型对应的值：
  - 如果 `p` 不是 NaN，装箱转换将 `p` 转换为类和类型为 `Double` 的引用，使得 `r.doubleValue() == p`
  - 否则，装箱转换将 `p` 转换为类和类型为 `Double` 的引用，使得 `r.isNaN()` 为真

理想情况下，基本值的装箱应该总是产生相同的引用。在实践中，使用现有的实现技术可能不可行。上述规则是一种务实的折中，要求某些值总是被装箱为对象。实现可以延迟或积极地这样做。对于其他值，规则不允许对装箱值进行任何假设。这允许（但不要求）共享这些引用。

这确保了在大多数情况下行为符合预期，且不会产生过大的性能负担，特别是对于小型设备。内存限制的实现可能会对所有的 `char` 和 `short` 值，以及范围在 -32K 到 +32K 之间的 `int` 值进行缓存处理。

如果需要分配包装类（`Boolean`、`Byte`、`Character`、`Short`、`Integer`、`Long`、`Float` 或 `Double`）的新实例但存储不足，可能会导致 `OutOfMemoryError`。

## 5.1.8 解箱转换 (Unboxing Conversion)

解箱转换将引用类型的表达式视为基本类型的表达式。具体而言，以下八种转换被称为*解箱转换*：

- 从类型 `Boolean` 到类型 `boolean`
- 从类型 `Byte` 到类型 `byte`
- 从类型 `Short` 到类型 `short`
- 从类型 `Character` 到类型 `char`
- 从类型 `Integer` 到类型 `int`
- 从类型 `Long` 到类型 `long`
- 从类型 `Float` 到类型 `float`
- 从类型 `Double` 到类型 `double`

在运行时，解箱转换按如下方式进行：

- 如果 `r` 是 `Boolean` 类型的引用，则拆箱转换将 `r` 转换为 `r.booleanValue()`
- 如果 `r` 是 `Byte` 类型的引用，则拆箱转换将 `r` 转换为 `r.byteValue()`
- 如果 `r` 是 `Character` 类型的引用，则拆箱转换将 `r` 转换为 `r.charValue()`
- 如果 `r` 是 `Short` 类型的引用，则拆箱转换将 `r` 转换为 `r.shortValue()`
- 如果 `r` 是 `Integer` 类型的引用，则拆箱转换将 `r` 转换为 `r.intValue()`
- 如果 `r` 是 `Long` 类型的引用，则拆箱转换将 `r` 转换为 `r.longValue()`
- 如果 `r` 是 `Float` 类型的引用，拆箱转换将 `r` 转换为 `r.floatValue()`
- 如果 `r` 是 `Double` 类型的引用，则拆箱转换将 `r` 转换为 `r.doubleValue()`
- 如果 `r` 为 `null`，则拆箱转换将抛出 `NullPointerException`

如果一个类型是数值类型 (§4.2)，或者它是一个可以通过拆箱转换转换为数值类型的引用类型，则认为该类型是可转换为数值类型的。

如果一个类型是整型类型，或者它是一个可以通过拆箱转换转换为整型类型的引用类型，则认为该类型是可转换为整型类型的。

## 5.1.9 未检查转换 (Unchecked Conversion)

令 `G` 表示一个具有 `n` 个类型参数的泛型类型声明。

从原始类或接口类型 (§4.8) `G` 到任何形式为 `G<T_1, ..., T_n>` 的参数化类型存在一种未检查的转换。

从原始数组类型 `G[]^k` 到任何形式为 `G<T_1, ..., T_n>[]^k` 的数组类型存在一种未检查的转换。（符号 `^k` 表示 `k` 维的数组类型）。

使用未检查的转换会导致编译时的未检查警告，除非所有的类型参数 `T_i` (1 \le i \le n) 都是无界通配符 (§4.5.1)，或者该警告被 `@SuppressWarnings` (§9.6.4.5) 抑制。

未检查转换用于允许在引入泛型类型之前编写的遗留代码与经过泛型化转换（我们称为泛型化）的库之间进行平滑协作。在这种情况下（最典型的是 `java.util` 中 Collections Framework 的客户端），遗留代码使用原始类型（例如 `Collection` 而不是 `Collection<String>`）。原始类型的表达式被作为参数传递给库，而这些库使用相同类型的参数化版本作为其对应形式参数的类型。

在使用泛型的系统中，无法证明此类调用在静态上是安全的。拒绝此类调用将导致大量现有代码的失效，并阻止它们使用新版本的库。反过来，这会阻碍库供应商利用泛型的优势。为了防止这种情况，原始类型可以被转换为该原始类型所引用的泛型类型声明的任意调用。虽然这种转换是不安全的（unsound），但出于实用考虑的妥协，它是允许的。在这种情况下，会发出一个未检查警告。

## 5.1.10 捕获转换 (Capture Conversion)

令 `G` 表示一个具有 `n` 个类型参数 `A_1, ..., A_n` 及其对应边界 `U_1, ..., U_n` 的泛型类型声明 (§8.1.2, §9.1.2)。

从参数化类型 `G<T_1, ..., T_n>` (§4.5) 到参数化类型 `G<S_1, ..., S_n>` 存在一种捕获转换，其中 1 \le i \le n：

- 如果 `T_i` 是形式为 `?` 的通配符类型参数，则 `S_i` 是一个新的类型变量，其上界为 `U_i[A_i:=S_1, ..., A_n:=S_n]` 且下界为空类型 (§4.1)。
- 如果 `T_i` 是形式为 `? extends B_i` 的通配符类型参数，则 `S_i` 是一个新的类型变量，其上界为 `B_i[A_i:=S_1, ..., A_n:=S_n]` 且下界为空类型。

`glb(V_1, ..., V_m)` 定义为 `V_1 & ... & V_m`。

如果在任何两个类（非接口）`V_i` 和 `V_j` 中，`V_i` 不是 `V_j` 的子类或反之，则为编译错误。

- 如果 `T_i` 是形式为 `? super B_i` 的通配符类型参数，则 `S_i` 是一个新的类型变量，其上界为 `U_i[A_i:=S_1, ..., A_n:=S_n]` 且下界为 `B_i`。
- 否则，`S_i = T_i`。

任何参数化类型 (§4.5) 之外的其他类型上的捕获转换都作为恒等转换 (§5.1.1)。

捕获转换不是递归应用的。捕获转换永远不需要在运行时执行特殊操作，因此不会在运行时抛出异常。

捕获转换的设计是为了让通配符更有用。为了理解其动机，让我们先看：

```java
public static void reverse(List<?>);
```

`java.util.reverse()` 方法是合适的。现在考虑人们如何实现：

```java
private static <T> void reverse(List<?> list) {
    List<T> tmp = new ArrayList<>();
    for (int i = 0; i < list.size(); i++) {
        tmp.set(i, (T) list.get(i));
    }
}
```



这种方案的优势在于不需要关闭操作，见 *Variance-Based Subtyping for Parametric Types* 由 Atsushi Igari 和 Mirko Viroli 发表于第16 届欧洲面向对象编程会议 (ECOOP 2002)。

数学背景丰富的读者可能希望将捕获转换与类型理论联系起来。不熟悉类型理论的读者可以跳过此节，或者学习合适的书籍，如 Benjamin Pierce 的《Types and Programming》，然后重新阅读本节。

这里是捕获转换与现有概念关系的简要总结。通配符类型是存在类型的受限形式。对表达式 $e$ 的捕获转换可以看作是在一个作用域内开启存在类型。存在类型的经典开启操作要求捕获的类型变量永远在该作用域外不可见。关于通配符的正式说明，见 *Wildcards* 由 Madsen Torgersen, Erik Ernst 和 Plesner Hansen 发表于第12 届面向对象编程基础会议 (FOOL 2005)。

规范必须处理诸如非平凡（可能递归定义的）的上界或下界、多个参数等复杂情况。如果我们能将这个未知类型捕获到类型变量 `X` 中，就可以推导出 `T` 为 `X`。这就是捕获转换的精髓。从 `reverse()` 到 `rev()` 的调用将被允许。

# 5.11 字符串转换 (String Conversion)

任何类型都可以通过字符串转换为 `String` 类型。

基本类型 `T` 的值 `x` 首先被转换为引用值，仿佛将其作为参数传递给类实例创建表达式 (§15.9)：

- 如果 `T` 是 `boolean`，使用 `new Boolean(x)`。
- 如果 `T` 是 `char`，使用 `new Character(x)`。
- 如果 `T` 是 `byte`、`short` 或 `int`，使用 `new Integer(x)`。
- 如果 `T` 是 `long`，使用 `new Long(x)`。
- 如果 `T` 是 `float`，使用 `new Float(x)`。
- 如果 `T` 是 `double`，使用 `new Double(x)`。

该引用值通过字符串转换转换为 `String` 类型。现在只需要考虑引用值：

- 如果引用为 `null`，则被转换为字符串 "null"（四个 ASCII 字符 n, u, l, l）。

否则，转换将类似于通过对引用的对象调用任何不带参数的 `toString` 方法；但如果调用 `toString` 方法的结果为 `null`，则使用字符串 "null" 代替。

`toString` 方法由原始 `Object` (4.3.2) 定义。许多类都重写了它，特别是 `Boolean`、`Character`、`Integer`、`Long`、`Float`、`Double` 和 `String`。

## 5.1.12 禁止的转换

任何未显式允许的转换都是禁止的。

## 5.1.13 值集转换

值集转换是将浮点值从一个集合映射到另一个集合而不改变其类型的过程。

在非 FP-strict（§15.4）的表达式中，值集转换为 Java 编程语言的实现提供了选择：

- 如果该值是浮点扩展指数值集（float-extended-exponent value set）的元素，则实现可以根据选择将该值映射到浮点值集中最近的元素。这种转换可能导致溢出（在这种情况下，值将被替换为相同符号的无穷大）或下溢（在这种情况下，该值可能会丢失精度，因为它被替换为相同符号的非规格化或零）。

- 如果该值是双精度扩展指数值集（double-extended-exponent value set）的元素，则实现可以根据选择将该值映射到双精度值集中最近的元素。这种转换可能导致溢出（在这种情况下，值将被替换为相同符号的无穷大）或下溢（在这种情况下，该值可能会丢失精度，因为它被替换为相同符号的非规格化或零）。

在 FP-strict 表达式（§15.4）中，值集转换不提供任何选择；每个实现必须以相同的方式行为：

- 如果类型为 `float` 且不是浮点值集的元素，则实现必须将该值映射到浮点值集中最近的元素。这种转换可能导致溢出或下溢。

- 如果类型为 `double` 且不是双精度值集的元素，则实现必须将该该值映射到双精度值集中最近的元素。这种转换可能导致溢出或下溢。

在 FP-strict 表达式中，从浮点扩展指数值集或双精度扩展指数值集映射值，仅当调用的方法声明不是 FP-strict 且实现选择将方法调用的结果表示为扩展指数值集的元素时才是必要的。

无论是在 FP-strict 代码中还是非 FP-strict 代码中，值集转换始终忽略任何既不是 `float` 也不是 `double` 的值。

# 5.2 赋值上下文

赋值上下文允许将表达式的值赋值 (§15.26) 给变量；表达式的类型必须转换为变量的类型。

赋值上下文允许使用以下之一：

- 标识转换 (§5.1.1)
- 宽扩展基本类型转换 (§5.1.2)
- 宽扩展引用转换 (§5.1.5)
- 宽扩展引用转换后接解箱转换
- 宽扩展引用转换后接解箱转换，然后后接宽扩展基本类型转换
- 装箱转换 (§5.1.7)
- 装箱转换后接宽扩展引用转换
- 解箱转换 (§5.1.8)
- 解箱转换后接宽扩展基本类型转换

如果应用了上述转换，结果的类型为原始类型（§4.8），则随后可以应用未检查的转换（§5.1.9）。

此外，如果表达式是 `byte`、`short`、`char` 或 `int` 类型的常量表达式（§15.28）：

- 如果变量类型为 `byte`、`short`、`char`，且常量表达式的值在变量类型中可表示，则可以使用收缩基本类型转换。

如果变量类型为 `Byte`、`Short` 或 `Character`，且常量表达式的值分别在 `byte`、`short` 或 `char` 中可表示，则可以使用收缩基本类型转换后接装箱转换。

常量表达式的编译时收缩意味着如下代码是允许的：

```
byte theAnswer = 42;
```

如果没有收缩，整字字面量 42 类型为 `int` 转换为 `byte` 需要：

```
byte theAnswer = (byte) 42; // 允许但不是强制
```

最后，`null` 类型的值（空引用是唯一的值）可以赋值给任何引用类型，导致该类型的空引用。

如果转换链包含两个不是子类关系的类型 (§4.10)，则为编译错误。

此类非法链示例：

```
Integer, Comparable<Integer>, Comparable, Comparable<String>
```

链的前三个元素是通过宽扩展引用转换创建，而最后一个项是通过其前一个项的未检查转换得到的。然而，这不是有效的赋值转换，因为链包含了两个不是子类的类型 `Comparable<Integer>` 和 `Comparable<String>`。

如果表达式的类型可以通过赋值转换转换为变量类型，我们说该表达式（或其值）是可以赋值给变量的，或者等于表达式的类型与变量类型兼容。

如果变量类型为 `float` 或 `double`，则值转换 (§5.1.13) 应用于转换结果变量 `v`：

- 如果类型为 `float` 且不是浮点值集的元素，则实现必须将该值映射到浮点值集中最近的元素。这种转换可能导致溢出或下溢。

- 如果类型为 `double` 且不是双精度值集的元素，则实现必须将该值映射到双精度值集中最近的元素。这种转换可能导致溢出或下溢。

在 FP-strict 表达式中，从浮点扩展指数值集或双精度扩展指数值集映射值，仅当调用的方法声明不是 FP-strict 且实现选择将方法调用的结果表示为扩展指数值集的元素时才是必要的。

无论是在 FP-strict 代码中还是非 FP-strict 代码中，值集转换始终忽略任何既不是 `float` 也不是 `double` 的值。

## 5.2.1 基本类型的赋值

```java
class Test {

    public static void main(String[] args) {

        byte b = 10;

        short s = 20;

        char c = 'A';

        int i = 30;

        float f = 40.5f;

        double d = 50.75;

        // 宽扩展转换

        s = b;

        c = s;

        i = c;

        f = i;

        d = f;

        // 收缩转换（需要强制类型转换）

        b = (byte) s;

        s = (short) c;

        c = (char) i;

        i = (int) f;

        f = (float) d;

    }

}
```

## 5.2.2 引用类型的赋值

```java
class Point { int x, y; }

class Point3D extends Point { int z; }

interface Colorable { void setColor(int color); }

class ColoredPoint extends Point implements Colorable {

    int color;

    public void setColor(int color) { this.color = color; }

}

class Test {

    public static void main(String[] args) {

        // 给类类型的变量赋值：

        Point p = new Point();

        p = new Point3D(); // 确，因为 Point3D 是 Point 的子类

        Point3D p3d = p; // 错误：需要强制类型转换，因为 Point 可能不是 Point3D（尽管在示例中动态来看是这样的。）

        // 给 Object 类型的变量赋值：

        Object o = p; // OK，任何对象赋值给 Object

        int[] a = new int[3];

        Object o2 = a; // OK，数组赋值给 Object

        // 给接口类型的变量赋值：

        ColoredPoint cp = new ColoredPoint();

        Colorable c = cp; // OK，ColoredPoint 实现了 Colorable

        // 给数组类型的变量赋值：

        byte[] b = new byte[4];

        a = b; // 错误：这些不是相同基本类型的数组

        Point3D[] p3da = new Point3D[3];

        Point[] pa = p3da; // OK，我们可以将 Point3D 赋值给 Point

        p3da = pa; // 错误：（需要强制转换）因为 Point 不能赋值给 Point3D

    }

}
```



# 转换与上下文

## 赋值上下文

### 5.2

```java
int color;

public void setColor(int color) { this.color = color; }

class Test {

    public static void main(String[] args) {

        Point p = new Point();

        ColoredPoint cp = new ColoredPoint();

        // 因为 ColoredPoint 是 Point 的子类:
        p = cp;

        // 因为 ColoredPoint 实现了 Colorable:
        Colorable c = cp;

        // 以下操作会导致编译错误，因为
        // 我们无法确定它们是否会成功，取决于
        // p 的运行类型；所需的收缩转换
        // 将进行运行时检查，并且必须
        // 通过包含强制转换来指示：
        cp = p; // p 可能既不是 ColoredPoint
               // 也不是 ColoredPoint 的子类

        c = p; // p 可能没有实现 Colorable

    }

}
```

## 示例 5.2-3. 数组类型的赋值

```java
class Point { int x, y; }

class ColoredPoint extends Point { int color; }

class Test {

    public static void main(String[] args) {

        long[] veclon = new long[100];

        Object o = veclon; // OK

        Long l = veclon; // 编译错误

        short[] vechort = veclon; // 编译错误

        Point[] pvec = new Point[100];

        ColoredPoint[] cpvec = new ColoredPoint[100];

        pvec = cpvec; // OK

        pvec[0] = new Point(); // 编译时通过，
                               // 但运行时会抛出
                               // 异常

        cpvec = pvec; // 编译错误

    }

}
```

在此示例中：

- `veclon` 的值不能赋值给 `Long` 变量，因为 `Long` 是 `Object` 外的类类型。数组只能赋值给兼容数组类型的变量，或者赋值给 `Object`、`Cloneable` 或 `java.io.Serializable` 类型的变量。
- `veclon` 的值不能赋值给 `vechort`，因为 `vechort` 是基本类型数组，而 `short` 和 `long` 不是同一种基本类型。
- `pvec` 的值可以赋值给 `pvec`，因为任何可以是 `ColoredPoint` 类型表达式值的引用，都可以作为 `Point` 类型变量的值。随后将新的 `Point` 赋值给 `pvec` 的组件将抛出 `ArrayStoreException`（如果程序在其他方面经过修正以便可以编译），因为 `ColoredPoint` 数组不能将 `Point` 实例作为其组件。
- `pvec` 的值不能赋值给 `cpvec`，因为不是每个可以是 `Point` 类型表达式值的引用都能正确地作为 `ColoredPoint` 类型变量的值。如果 `pvec` 在运行时的值是对 `ColoredPoint[]` 实例的引用，并且允许赋值给 `cpvec`，那么对 `cpvec` 的组件 `cpvec[0]` 的简单引用将返回一个 `Point`，而 `Point` 不是 `ColoredPoint`。因此，允许此类赋值将允许违反类型系统。可以使用强制转换（§5.5, §15.16）来确保 `pvec` 引用的是 `ColoredPoint[]`：

```java
pvec = (ColoredPoint[])pvec; // OK，但在运行时可能抛出
// 异常
```

## 调用上下文

调用上下文允许方法或构造函数调用中的参数值（§8.8.7.1, §15.9, §15.12）赋值给相应的形式参数。

严格调用上下文允许使用以下转换之一：

- 标识转换（§5.1.1）
- 宽基本类型转换（§5.1.2）
- 宽引用转换（§5.1.5）

宽松调用上下文允许更宽松的转换集，因为只有在没有可用声明可以使用时，它们才用于特定的调用。宽松调用上下文允许使用以下转换：

- 标识转换（§5.1.1）
- 宽基本类型转换（§5.1.2）
- 宽引用转换（§5.1.5）
- 宽引用转换后接解箱转换
- 宽引用转换后接解箱转换，紧接着又接宽基本类型转换
- 装箱转换（§5.1.7）
- 装箱转换后接宽引用转换
- 解箱转换（§5.1.8）
- 解箱转换后接宽基本类型转换

如果在应用了为调用上下文列出的转换后，得到的类型是原始类型（§5.8），则可以再应用未检查转换（§5.1.9）。

`null` 类型的值（`null` 引用是此类值）可以赋值给任何引用类型。

如果转换链包含两个没有子类型关系的泛型类型（§4.10），则为编译错误。

如果参数表达式的类型是 `float` 或 `double`，则在转换后应用值集转换（§5.1.13）：

- 如果 `float` 类型的参数是 `float` 扩展指数值集中的元素，则实现必须映射到 `float` 值集中最近的元素。此转换可能导致溢出或下溢。
- 如果 `double` 类型的参数是 `double` 扩展指数值集中的元素，则实现必须映射到 `double` 值集中最近的元素。此转换可能导致溢出或下溢。

在调用上下文中可能出现的异常有：

- 如果应用上述类型转换后，得到的类型是一个不是对应格式参数类型擦除（§4.6）的子类或子接口实例的对象，则产生 `ClassCastException`。
- 装箱转换导致 `OutMemoryError`。
- 对 `null` 引用进行解箱转换导致 `NullPointerException`。

严格上下文和调用上下文都不包含赋值上下文中允许的整数常量表达式的隐式收缩。Java 编程语言的设计者认为，包含这些隐式收缩转换会增加重载解析规则（§15.12.2）的复杂性。

因此，该程序：

```java
class Test {

    static int m(byte a, int b) { return a+b; }

    static int m(short a, short b) { return a-b; }

    public static void main(String[] args) {

        System.out.println(m(12, 2)); // 编译错误

    }

}
```

## 5.4 字符串上下文

## 5.5 强制转换上下文

如果表达式是引用类型，则强制转换上下文允许使用以下：

- 标识转换（§5.1.1）
- 宽引用转换（§5.1.5）
- 宽引用转换后接解箱转换
- 宽引用转换后接解箱转换，紧接着又接宽基本类型转换
- 收缩引用转换（§5.1.6）
- 收缩引用转换后接解箱转换
- 解箱转换（§5.1.8）
- 解箱转换后接宽基本类型转换

如果表达式是原始类型，则强制转换上下文允许使用以下：

- 标识转换（§5.1.1）
- 宽基本类型转换（§5.1.2）
- 收缩基本类型转换（§5.1.3）
- 宽引用转换后接解箱转换
- 宽引用转换后接解箱转换，紧接着又接宽基本类型转换
- 装箱转换（§5.1.7）
- 装箱转换后接宽引用转换
- 解箱转换（§5.1.8）
- 解箱转换后接宽基本类型转换

如果表达式是 `null` 类型，则表达式可以转换为任何引用类型。

如果强制转换上下文使用了检查或部分未检查的收缩引用转换（§5.1.6.2, §5.1.6.3），则会对值的类进行运行时检查，可能会导致 `ClassCastException`。否则，不进行运行时检查。

值集转换（§5.1.13）在类型转换后应用。

下表列出了某些强制转换上下文使用的转换。每种转换由一个符号表示：

- `-` 表示不允许转换
- `≈` 表示标识转换（§5.1.1）
- `ω` 表示宽基本类型转换（§5.1.2）
- `η` 表示收缩基本类型转换（§5.1.3）
- `⩘ₑ` 表示宽收缩基本类型转换（§5.1.4）
- `⇑` 表示宽引用转换（§5.1.5）
- `⇓` 表示收缩引用转换（§5.1.6）
- `⊕` 表示装箱转换（§5.1.7）
- `⊖` 表示解箱转换（§5.1.8）

在表中，符号之间的逗号表示强制转换上下文使用一个转换后接另一个。类型 `Object` 表示除八个包装类 `Boolean`、`Byte`、`Character`、`Integer`、`Long`、`Float`、`Double` 之外的任何引用类型。

### 表 5.5-A. 转换为原始类型

| 目标 → | byte | short | char | int | long | float | double | boolean |
|---|---|---|---|---|---|---|---|---|
| 源 ↓ | | | | | | | | |
| byte | ≈ | ω | ω | ω | ω | ω | ω | - |
| short | η | ≈ | η | ω | ω | ω | ω | - |
| char | η | η | ≈ | ω | ω | ω | ω | - |
| int | η | η | η | ≈ | ω | ω | ω | - |
| long | η | η | η | η | ≈ | ω | ω | - |
| float | η | η | η | η | η | ≈ | ω | - |
| double | η | η | η | η | η | η | ≈ | - |
| boolean | - | - | - | - | - | - | - | ≈ |
| Byte | ⊖ | ⊖,η | - | ⊖,ω | ⊖,ω | ⊖,ω | ⊖,ω | - |
| Short | - | ⊖ | - | ⊖,ω | ⊖,ω | ⊖,ω | ⊖,ω | - |
| Character | - | - | ⊖ | ⊖,ω | ⊖,ω | ⊖,ω | ⊖,ω | - |
| Integer | - | - | - | ⊖ | ⊖,ω | ⊖,ω | ⊖,ω | - |
| Long | - | - | - | - | ⊖ | ⊖,ω | ⊖,ω | - |
| Float | - | - | - | - | - | ⊖ | ⊖,ω | - |
| Double | - | - | - | - | - | - | ⊖ | - |
| Boolean | - | - | - | - | - | - | - | ⊖ |
| Object | ⊖,⇓ | ⊖,⇓ | ⊖,⇓ | ⊖,⇓ | ⊖,⇓ | ⊖,⇓ | ⊖,⇓ | ⊖,⇓ |

### 表 5.5-B. 转换为引用类型

| 目标 → | Byte | Short | Character | Integer | Long | Float | Double | Boolean | Object |
|---|---|---|---|---|---|---|---|---|---|
| 源 ↓ | | | | | | | | | |
| byte | ⊕ | - | - | - | - | - | - | - | ⊕,⇑ |
| short | - | ⊕ | - | - | - | - | - | - | ⊕,⇑ |
| char | - | - | ⊕ | - | - | - | - | - | ⊕,⇑ |
| int | - | - | - | ⊕ | - | - | - | - | ⊕,⇑ |
| long | - | - | - | - | ⊕ | - | - | - | ⊕,⇑ |
| float | - | - | - | - | - | ⊕ | - | - | ⊕,⇑ |
| double | - | - | - | - | - | - | ⊕ | - | ⊕,⇑ |
| boolean | - | - | - | - | - | - | - | ⊕ | ⊕,⇑ |
| Byte | ≈ | - | - | - | - | - | - | - | ⇑ |
| Short | - | ≈ | - | - | - | - | - | - | ⇑ |
| Character | - | - | ≈ | - | - | - | - | - | ⇑ |
| Integer | - | - | - | ≈ | - | - | - | - | ⇑ |
| Long | - | - | - | - | ≈ | - | - | - | ⇑ |
| Float | - | - | - | - | - | ≈ | - | - | ⇑ |
| Double | - | - | - | - | - | - | ≈ | - | ⇑ |
| Boolean | - | - | - | - | - | - | - | ≈ | ⇑ |
| Object | ⇓ | ⇓ | ⇓ | ⇓ | ⇓ | ⇓ | ⇓ | ⇓ | ≈ |

### 示例 5.5-1. 引用类型的转换

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

        // 以下操作在运行时可能会导致错误，因为
        // 如文中解释的，我们永远无法成功：这种可能性
        // 是由类型转换暗示的：
        cp = (ColoredPoint)p; // p 可能没有引用一个
                              // ColoredPoint 的子类的对象

        c = (Colorable)p; // p 可能没有实现 Colorable

        // 以下内容在编译时是错误的
        // 正如文中解释的，它们永远无法成功：
        Long l = (Long)p; // 编译错误 #1

        Endpoint e = new Endpoint();

        c = (Colorable)e; // 编译错误 #2

    }

}
```

在这里，第一个编译错误发生是因为 `Long` 和 `Point` 两个类之间没有关系（即它们不相同，且互不是对方的子类），因此它们之间的转换始终会失败。

第二个编译错误发生是因为 `Endpoint` 类型的变量无法引用实现 `Colorable` 的值。这是因为 `Endpoint` 是一个 `final` 类型，而 `final` 类型的变量始终持有相同编译类型的值。因此，变量 `e` 的运行时类型必须恰好是 `Endpoint`，而该类型没有实现 `Colorable`。

### 示例 5.5-2. 数组类型的转换

```java
class Point {

    int x, y;

    Point(int x, int y) { this.x = x; this.y = y; }

    public String toString() { return "(" + x + "," + y + ")"; }

}

interface Colorable { void setColor(int color); }

class ColoredPoint extends Point implements Colorable {

    int color;

    public void setColor(int color) { this.color = color; }

}

class Test {
    public static void main(String[] args) {
        Point[] pa = new Point[2];
        pa[0] = new ColoredPoint(2, 2);
        pa[1] = new ColoredPoint(4, 5);
        ColoredPoint[] cpa = (ColoredPoint[])pa;
        System.out.print("cpa: {");
        for (int i = 0; i < cpa.length; i++) {
            System.out.print(cpa[i] + (i < cpa.length - 1 ? ", " : ""));
        }
        System.out.println("}");
    }
}
```

### 示例 5.5-3. 运行时类型不兼容的转换



```java
class Point { int x, y; }
interface Colorable { void setColor(int color); }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}
class Test {
    public static void main(String[] args) {
        Point[] pa = new Point[10];
        pa[0] = new ColoredPoint(2, 2);
        pa[1] = new ColoredPoint(4, 5);
        try {
            ColoredPoint[] cpa = (ColoredPoint[])pa;
            System.out.print("cpa: {");
            for (int i = 0; i < cpa.length; i++) {
                System.out.print(cpa[i] + (i == cpa.length - 1 ? "" : ", "));
            }
            System.out.println("}");
        } catch (ClassCastException e) {
            System.out.println(e);
        }
        int[] shortvec = new int[2];
        Object o = shortvec;
        try {
            Colorable c = (Colorable)o;
            c.setColor(0);
        } catch (ClassCastException e) {
            System.out.println(e);
        }
    }
}
```

该程序可以编译，但在运行时会抛出异常，因为类型不兼容。

## 5.6 数值上下文

数值上下文适用于算术运算符的操作数：

- 标识转换 (5.1.1)
- 宽基本转换 (5.1.2)
- 引用转换 (5.1.5) 后的解箱转换
- 引用转换后的宽基本转换
- 解箱转换 (5.1.8)

数值提升是一个过程，给定算术运算符及其操作数，将操作数转换为一个推断的目标类型 $T$，使得每个操作数都能转换为 $T$ 且该算术运算对于类型 $T$ 是定义的。

### 5.6.1 一元数值提升

某些运算符对单个操作数应用一元数值提升，必须产生一个数值类型：

- 如果操作数的类型为 `Byte`、`Short`、`Character` 或 `Integer`，则执行解箱转换 (5.1.8)。结果通过宽基本转换 (5.1.2) 或标识转换 (5.1.1) 提升为 `int` 类型。
- 否则，如果操作数的类型为 `Long`、`Float` 或 `Double`，则执行解箱转换 (5.1.8)。
- 否则，如果操作数为 `byte`、`short` 或 `char`，则通过宽基本转换提升为 `int` 类型。
- 否则，一元数值操作保持不变，不进行转换。

在执行任何转换后，应用值设置 (5.1.13)。

一元数值提升在以下情况下执行：

- 数组创建表达式中的每个维度表达式 (5.10.1)。
- 数组访问表达式中的索引表达式 (5.10.3)。
- 一元加运算符 `+` 的操作数 (15.15.3)。
- 一元减运算符 `–` 的操作数 (15.15.4)。
- 位取反运算符 `~` 的操作数 (15.15.5)。
- 移位运算符 `<<`、`>>` 或 `>>>` 的每个操作数 (15.19.9)。

长位距离（右操作数）不会将被移动的值（左操作数）提升为 `long`。

#### 示例 5.6.1-1. 一元数值提升

```java
class Test {
    public static void main(String[] args) {
        byte b = 2;
        int a[] = new int[b]; // 维度表达式提升
        char c = '\u0001';
        a[c] = 1;              // 索引表达式提升
        a[0] = -c;                   // 一元负号提升
        System.out.println("a: " + a[0] + "," + + a[1]);
        b = -1;
        int i = ~b;               // 按位取反提升
        System.out.println("0x" + Integer.toHexString(b)
              + "==0x" + Integer.toHexString(i));
        i = b << 4L;               // 移位提升（左操作数）
        System.out.println("0x" + Integer.toHexString(b)
              + "<<4L=0x" + Integer.toHexString(i));
    }
}
```

该程序产生输出：

```
a: -1,1
~0xffffffff=0x0
0xffffffff<<4L=0xffffffff0
```

### 5.6.2 二元数值提升

当操作符对一对操作数执行二元数值提升时，每个操作数必须表示一个可以转换为数值类型的值，并按顺序适用以下规则：

1. 如果任一操作数为引用类型，则对其进行拆箱转换（§5.1.8）。
2. 应用宽化原始转换（§5.1.2），按照以下规则转换一个或两个操作数：
   - 如果任一操作数的类型为 `double`，则另一个被转换为 `double`。
   - 否则，如果任一操作数的类型为 `float`，则另一个转换为 `float`。
   - 否则，如果任一操作数的类型为 `long`，则另一个转换为 `long`。
   - 否则，两个操作数都转换为 `int` 类型。

在转换（如果有）之后，对每个操作数应用值转换（§5.1.13）。

二元数值提升在某些操作符的操作数上执行：

- 乘法运算符 `*`、`/` 和 `%` (§15.17)
- 数值类型的加法和减法运算符 `+` 和 `-` (§15.20.1)
- 数值比较操作符 `<`, `<=`、`>` 和 `>=` (§15.20.1)
- 数值相等操作符 `==` 和 `!=` (§15.21.1)
- 整数按位操作符 `^` 和 `|` (§15.22)
- 在某些情况下，条件操作符 `? :` (§15.25)

#### 示例 5.6.2-1. 二元数值提升

```java
class Test {
    public static void main(String[] args) {
        int i = 0;
        float f = 1.0f;
        double d = 2.0;
        // 首先 int 被提升为 float，然后
        // float==double 提升为 double==double;
        if (i * f == d) System.out.println("oops");

        // 一个 char&byte 被提升为 int&int:
        byte b = 0x1f;
        char c = 'G';
        int control = c & b;
        System.out.println(Integer.toHexString(control));

        // 此处 int:float 被提升为 float:float:
        f = (b==0) ? i : 4.0f;
        System.out.println(1.0/f);
    }
}
```

该程序产生输出：

```
7
0.25
```

该示例通过掩码字符的所有低 5 位，将 ASCII 字符 G 转换为 ASCII 控制字符 G (BEL)。7 是该控制字符的数值值。

# 第 6 章 标识

名称用于指代程序中声明的实体。

声明的实体 (§6.1) 可以是包、类类型（普通或枚举）、接口类型（普通或注解类型）、引用类型的成员（类、接口、字段或方法）、类型参数（属于类、接口、方法或构造函数的类型参数）、参数（指向方法、构造函数或异常处理程序的参数）或局部变量。

程序中的名称要么是简单的（simple，由单个标识符组成），要么是限定的（qualified，由一组由 `.` 分隔的标识符序列组成）（§6.2）。

每个引入名称的声明都有一个作用域 (§6.3)，作用域是程序文本的一部分，在该部分内可以通过简单名称引用声明的实体。

限定名称 $N.x$ 可用于指代包或引用类型的成员，其中 $N$ 是简单名称或限定名称，$x$ 是标识符。如果 $N$ 指代一个包，则 $x$ 是该包的成员（可以是类或接口）。如果 $N$ 指代一个引用类型的类型或变量，则 $x$ 指代该类型的成员（可以是接口、字段或方法）。

在确定名称的含义 (§6.5) 时，使用发生时的上下文来消除相同名称包、类型和方法之间的歧义。

访问权限（Access，§6.6）可以在类、接口或字段声明中指定，以控制何时允许访问成员。访问是一个与作用域不同的概念。作用域是声明实体的程序部分，该实体可以通过简单名称在字段访问（§15.11）、方法调用（§15.12）、表达式（§15.9）中被引用。在没有指定访问修饰符的情况下，包权限允许在包内访问；其他权限是公共（public）和私有（private）。

## 6.1 声明

一个声明引入一个名称，并具有一个作用域 (§6.3)，在该部分内声明的实体可以通过简单名称引用。

一个声明引入一个实体并包含一个标识符，该实体是以下类型之一：

- 模块声明中使用的包（§7.7）
- 声明中的导入包（§7.4）
- 导入类型（§7.5）或按需导入类型（§7.6）
- 静态导入成员（§7.2）或按需静态导入成员（§7.3）
- 类声明中的类型（§8.1）
- 接口声明中的类型（§8.2）
- 泛型类型中的类型参数（§8.3）
- 声明中的方法（§8.4）
- 声明中的字段（§8.5）
- 声明中的常量（§8.6）
- 声明中的类（§8.7）
- 声明中的构造函数（§8.8）
- 声明中的方法（§8.9）
- 声明中的异常处理程序（§8.10）
- 字段访问中的（§15.11）
- 方法调用中的（§15.12）
- 表达式中的（§15.9）
- 块中的局部变量（§14.4）
- for 语句中的局部变量（§14.14）
- try 语句中 catch 子句的异常处理程序（§14.20）
- lambda 表达式中的（§15.27.1）

一个声明引入一个实体并包含一个标识符，其影响的范围。

### 非泛型上下文中的类型名称

`TypeName` 在以下非泛型上下文中使用：

1. 在单静态导入声明中 `.` 的左侧 (§7.5.3)
2. 在按需导入声明中 `.` 的左侧 (§7.5.4)
3. 在构造函数声明中 `. (` 的左侧 (§8.8)
4. 在注解中 `@` 符号之后 (§9.7)
5. 在类字面量中 `.class` 的左侧 (§15.8.2)
6. 在限定表达式中 `.this` 的左侧 (§15.8.8)
7. 在限定类字段访问表达式中 `.super` 的左侧 (§15.11.2)
8. 在限定方法调用表达式中 `.Identifier` 或 `.superIdentifier` 的左侧 (§15.12)
9. 在方法引用表达式中 `.super::` 的左侧 (§15.13)
10. 在后缀表达式或 try-with-resources 语句中的限定名中 (§15.14.1, §14.20.3)
11. 方法或构造函数的 `throws` 子句中 (§8.4.6, §8.8.5, §9.4)
12. 在异常参数声明中 (§14.20)

前十一个非泛型上下文对应于 §6.5.1 中 `TypeName` 的前十一个语法上下文。第十二个非泛型上下文是作为 `c.x` 的限定 `ExpressionName` 可能包含一个 `TypeName c` 以表示静态成员访问。`TypeName` 在这十二个上下文中的共同用法具有重要意义；它表明这些上下文涉及对类型的非一类化使用。相比之下，第十三和第十四个非泛型上下文 `ClassType` 表示 `throws` 和 `catch` 以一类的方式使用类型，并带有行、字段声明。将这两个上下文表征为非泛型是因为没有异常类型可以参数化。

> 注意，`ClassType` 产生式允许注解，因此可以在 `throws` 或 `catch` 子句中的类型用法添加注解，而 `TypeName` 产生式不允许注解，因此例如在单类型声明中无法对类型的名称添加注解。

# 命名规范



Java SE 平台的类库尽可能尝试根据下面列出的规范选择名称。这些规范有助于提高代码的可读性并避免某些类型的名称冲突。

我们建议在所有用 Java 语言编写的程序中使用这些规范。然而，如果长期习惯的用法另有规定，则不应盲目遵循这些规范。例如，`java.lang.Math` 类的 `sin` 和 `cos` 方法具有数学上的习惯名称，尽管这些方法名因为太短且不是动词而违反了建议的规范。

# 包名与模块名

开发者应该通过为广泛分发的包选择唯一的包名，以避免两个发布的包具有相同名的可能。这使得包能够被容易且自动地安装和索引。本节规定了生成唯一包名的建议规范。鼓励 Java SE 平台的实现提供自动支持，将一组包从本地和随意的包名转换为此处描述的唯一名称格式。

如果不使用唯一的包名，则包名冲突可能会在冲突包创建点以外的地方出现。这可能导致用户或程序员处于难以或无法解决的局面。在包具有受限交互的情况下，可以使用 `ClassLoader` 和 `ModuleLayer` 类来隔离同名的包，但这种方式对简单的程序来说不是透明的。

你形成包名的方法是：首先拥有（或属于）一个拥有 Internet 域名的组织，例如 `oracle.com`。然后按组件反转该名称（在本例中为 `com.oracle`），并将其作为包名的以前缀，使用组织内部开发的规范来进一步管理哪些包名属于部门、小组、项目或登录名称。

## 示例 6.1-1. 唯一的包名

```
com.nighthacks.scrabble.dictionary
org.openjdk.compiler.source.tree
net.jcip.annotations
edu.cmu.bovik.cheese
gov.whitehouse.com.mousefinder
```

包名的第一个组件始终使用小写 ASCII 字母，并且应该是顶级域名之一，例如 `com`、`edu`、`gov`、`net` 或 `org`，或者是 ISO 标准 3166 识别国家的双字母代码。

在某些情况下，Internet 域名可能不是有效的包名。以下是处理这些情况的建议规范：

- 如果域名包含连字符或任何在标识符中不允许的特殊字符 (§3.8)，则将其转换为下划线。
- 如果生成的包名组件中的任何一个是关键字 (§3.9)，则在它们后面加上下划线。
- 如果生成的包名组件中的任何一个以数字或任何不能作为标识符起始字符的字符开头，则在组件前加一个下划线。

模块的名称应与其主要导出包的名称对应。如果一个模块没有这样的包，或者出于历史原因它必须具有一个与其导出的包不对应的的名称，那么它的名称应以作者所属的 Internet 域名的反转形式开始。

## 示例 6.1-2. 唯一的模块名

```
com.nighthacks.scrabble
org.openjdk.compiler
net.jcip.annotations
```

# 字段名称

非最终（not final）字段名称应使用混合大小写，首字母小写，后续单词的首字母大写。请注意，良好的类通常只有极少数 public 或 protected 字段，常量（static final 字段）除外。

字段的名称应该是名词、名词短语或名词的缩写。

此规范的示例包括 `java.io.ByteArrayInputStream` 类中的 `buf`、`pos` 和 `count`，以及 `java.io.InterruptedIOException` 类中的字段 `bytesTransferred`。

# 常量名称

接口类型中的常量名称（且类类型的 `final` 变量按照习惯也可以）应该是一个或多个单词、缩写词或缩写字的序列，全大写，并用下划线 "_" 分隔各个组件。常量名称应具有描述性，不要进行不必要的缩写。按照习惯，它们可以是任何词类。

常量名称示例包括 `Character` 类的 `MIN_VALUE`、`MAX_VALUE`、`MIN_RADIX` 和 `MAX_RADIX`。

表示一组备选值的常量组，或较少地表示整数值中的掩码位，有时使用常用的缩写词作为名称前缀来指定。

例如：

```
interface ProcessStates {
  int PS_RUNNING = 0;
  int PS_SUSPENDED = 1;
}
```

# 局部变量和参数名称

局部变量和参数名称应该短而有意义。它们通常是不是单词的小写字母序列，例如：

- 缩写词，即一系列单词的首字母，例如用于持有 `ColoredPoint` 引用的变量 `cp`
- 缩写词，例如持有某种缓冲器的 `buf`
- 助记术语，以某种方式组织以帮助记忆和理解，通常通过使用一组具有惯名称的局部变量，其命名模式模仿类中使用的参数名称。例如：
    - `in` 和 `out`，每当涉及某种输入和输出时，模仿 `System` 的字段
    - `off` 和 `len`，每当涉及偏移量和长度时，模仿 `java.io` 中 `DataInput` 和 `DataOutput` 接口的 `read` 和 `write` 方法的参数

应避免使用单字符的局部变量或参数名称，但临时变量、循环变量，或者持有某种类型无区分值的变量除外。常见的单字符名称有：

- `b` 代表一个 byte
- `c` 代表一个 char
- `d` 代表一个 double
- `e` 代表一个 Exception
- `f` 代表一个 float
- `i`、`j` 和 `k` 代表 int
- `l` 代表一个 long
- `o` 代表一个 Object
- `s` 代表一个 String
- `v` 代表某种类型的任意值

仅由两个或三个小写字母组成的局部变量或参数名称不应与作为唯一包名第一个部分的初始国家代码和域名名发生冲突。

# 6.2 名称和标识符

名称被用于指代程序中声明的实体。

名称有两种形式：简单名（simple names）和限定名（qualified names）。

简单名是一个单一标识符。

限定名由一个名称、一个 "." 标记（token）和一个标识符组成。

在确定名称的含义（§6.5）时，会考虑该名称出现的上下文。§6.5 的规则区分了以下上下文，其中名称必须表示（引用）包 (§6.5.3)、类型 (§6.5.5)、表达式中的变量或值 (§6.5.6) 或方法 (§6.5.7)。

包和引用类型具有可以通过限定名访问的成员。关于限定名讨论的背景，请参见 §4.4、§4.5.2、§4.8、§4.9、§7.1、§8.2、§9.2 和 §10.7 中成员的描述。

## 名称和标识符

程序中的并非所有标识都是名称的一部分。标识符还用于以下情况：

- 在声明（§6.1）中，标识符可能出现以指定所声明实体的名称。
- 作为标记语句（§14.7）中的标签，以及引用语句标签的 `break` 和 `continue` 语句（§14.15, §14.16）。

用于标记语句及其相关的 `break` 和 `continue` 语句的标识符与声明中标识符是完全分开的。

- 在字段访问表达式（§15.11）中，标识符出现在 "." 标记之后，指示 "." 标记之前的表达式所表示的对象的成员，或者 "." 标记之前的 `super` 或 `TypeName.super` 所表示的对象的成员。
- 在某些方法调用表达式（§15.12）中，每当标识符出现在 "." 标记之后且另一个 "." 标记之前，指示为 "." 标记之前的表达式所表示的对象调用的方法，或 "." 标记之前的 `TypeName` 所表示的类型的方法，或 "." 标记之前的 `super` 或 `TypeName.super` 所表示的对象的方法。
- 在某些方法引用表达式（§15.13）中，每当标识符出现在 ":" 标记之后，指示为 ":" 标记之前的表达式所表示的对象的方法，或 ":" 标记之前的 `TypeName` 所表示的类型的方法，或 ":" 标记之前的 `super` 或 `TypeName.super` 所表示的对象的方法。
- 类实例化表达式（§15.9）中，标识符出现在 `new` 标记之后，指示这是 `new` 标记之前类型的成员。
- 在注解的元素-值对（§9.7.1）中，指示对应注解类型的元素。

在此程序中：

```java
class Test {
    public static void main(String[] args) {
        Class c = System.out.getClass();
        System.out.println(c.toString().length() +
            args[0].length() + args.length());
    }
}
```

`Test`、`main` 以及 `args` 的首次出现不是名称。相反，它们被用于声明以指定实体的名称。`String`、`Class`、`System.out.getClass`、`System.out.println`、`c.toString`、`args` 和 `args.length` 出现在示例中。

`args.length` 中的 `length` 是名称，因为 `args.length` 是限定名（§6.5.2），而不是字段访问表达式（§5.11）。`args[length()` 中的 `length` 不是名称，而是方法调用中的标识符。更复杂的是，字段访问表达式并非表示对象的唯一方式。对于解析而言，限定名被用于表示范围变量的字段。变量本身用简单名表示，如上所述。访问控制（§6.6）必须适用于字段的两种表示方式。

# 6.3 声明的作用范围

声明的作用范围是程序中可以使用简单名引用该声明实体的区域，前提是未被遮蔽（§6.4.1）。

如果声明的作用范围包含了程序中的某点，则称该声明在该点是作用范围内的。

可观测顶层包（§7.4.3）声明的作用范围是与该包具有唯一可见性（§7.4.3）的模块相关的所有可观测编译单元。

不可观测包的声明永远不在作用范围内。

子包的声明永远不在作用范围内。

`java` 包始终在作用范围内。

由单类型导入声明（§7.5.1）或通配类型导入声明（§7.5.2）导入类型的作用范围是所有的类和接口类型。

出现导入语句的编译单元中的声明 (§7.6)，以及该编译单元的模块声明或包声明上的任何注解。

通过单静态导入声明 (single-static-import) (§7.5.3) 或按需静态导入声明 (static-import-on-demand) (§7.5.4) 导入的成员的作用范围是出现导入语句的编译单元中所有的类和接口类型声明，以及该编译单元的模块声明或包声明上的任何注解。

顶层类型 (§7.6)的作用范围是声明该顶层类型的包中所有的类型声明。

在类类型 `c` (§8.1.6) 中声明或由 `c` 继承的成员 `m` 的声明的作用范围是 `c` 的整个体，包括任何嵌套声明。

在接口类型 `i` (§9.1.4) 中声明或由 `i` 继承的成员 `m` 的声明的作用范围是 `i` 的整个体，包括任何嵌套类型声明。

在枚举类型 `t` 中声明的常量 `c` 的作用范围是 `t` 的体，以及任何表达式为枚举类型 `t` 的 switch 语句的 `case` 标签 (§14.11)。

方法 (§8.4.1)、构造函数 (§8.8.1) 或 lambda 表达式 (§15.27) 的形式参数的作用范围是该方法、构造函数或 lambda 表达式的整个体。

类的类型参数 (§8.1.2)的作用范围是类声明的类型参数部分、该类声明的任何父类或父接口的类型参数部分，以及类体。

接口的类型参数 (§9.1.2)的作用范围是接口声明的类型参数部分、该接口声明的任何父接口的类型参数部分，以及接口体。

方法的类型参数 (§8.4.4)的作用范围是方法的整个声明，包括方法的修饰符。

构造函数的类型参数 (§8.8.4)的作用范围是构造函数的整个声明，包括类型参数部分，但不包括构造函数的修饰符。

立即被块 (§14.2) 闭合的局部类声明的作用范围是紧邻的该块的剩余部分，包括其自身的类声明。

立即被 switch 语句组 (§14.11) 闭合的局部类声明的作用范围是紧邻的该 switch 语句组的剩余部分，包括其自身的类声明。

块 (§14.4) 中局部变量声明的作用范围是出现该声明的块的剩余部分，从其初始化器开始，并包括局部变量声明语句右侧的任何后续声明符。

在基础 for 语句 (§14.1) 的 `ForInit` 部分中声明的局部变量的作用范围包括以下所有内容：

- 它自身的初始化器
- for 语句 `ForInit` 部分右侧的任何后续声明符
- for 语句的 `Expression` 部分和 `ForUpdate` 部分
- 包含的 `Statement`

在增强 for 语句 (§14.1.2) 的 `FormalParameter` 部分中声明的局部变量的作用范围是包含的 `Statement`。

在 try 语句的 catch 子句 (§14.20) 中声明的异常处理程序的作用范围是与 catch 关联的整个块。

在 try-with-resources 语句 (§14.20.3) 的 `ResourceSpecification` 中声明的变量的作用范围是从声明向右直到 `ResourceSpecification` 的剩余部分，以及与 try-with-resources 语句关联的整个 try 块。

> try-with-resources 语句的翻译意味着上述规则。

## 示例 6.3-1. 类型声明的作用范围

这些规则意味着类和接口类型的声明不需要在使用这些类型之前出现。在以下程序中，在类 `Point` 使用 `PointList` 是有效的，因为类声明 `PointList` 的作用范围包含了类 `Point` 和类 `PointList`，以及包 points 中其他编译单元中的任何其他类型声明。

```java
package points;
class Point {
    int x, y;
    PointList list;
}

class PointList {
}
```

## 示例 6.3-2. 变量声明的作用范围

以下程序会导致编译错误，因为 x 的初始化被局部变量遮蔽（shadowed）：

```java
class Test1 {
    int x;
    public static void main(String[] args) {
        int x = 2;
    }
}
```

以下程序可以编译：

```java
class Test2 {
    int x;
    public static void main(String[] args) {
        int x = 2;
        System.out.println(x);
    }
}
```

以下程序产生输出：

```java
class Test3 {
    public static void main(String[] args) {
        int two = 2;
        int three = 1;
        System.out.println(two + three);
    }
}
```

# 6.4 遮蔽与模糊

局部变量 (§14.4)、形式参数 (§8.4.1)、异常参数 (§14.20) 和局部类 (§14.3) 只能使用简单名进行引用，而不能使用限定名 (§6.2)。例如，如果方法的形式参数的名字可以重新声明为局部变量的名字，那么局部变量将遮蔽形式参数，且没有办法可以区分它们。

如果使用形式参数的名字在方法、构造函数或 lambda 表达式内部声明一个新变量，则是一个编译错误，除非该新变量是在包含该方法、构造函数或 lambda 表达式的类声明中声明的。

如果在局部变量 `v` 的作用范围内使用其名称声明一个新变量，则是一个编译错误，除非该新变量是在 `v` 的作用范围内的某个类中声明的。

如果在 catch 子句的 `Block` 内使用异常参数的名字声明一个新变量，则是一个编译错误，除非该新变量是在包含该 catch 子句 `Block` 的类声明中声明的。

如果在局部类 `C` 的作用范围内使用其名称声明一个新的局部类，则是一个编译错误，除非该新局部类是在 `C` 的作用范围内的另一个类中声明的。

这些规则允许在变量或局部类的作用范围内，通过嵌套类声明对局部变量或局部类进行重新声明；此类嵌套声明可以是局部类 (§14.3) 或匿名类 (§15.9)。因此，形式参数、局部变量或局部类的声明可能在方法、构造函数或 lambda 表达式内部的类声明中被遮蔽；异常参数的声明可能在 catch 子句的 `Block` 内被遮蔽。

对于处理 lambda 表达式创建的类以及在 lambda 表达式中声明的其他变量，存在设计替代。一种是模拟类声明：像局部类一样，lambda 表达式引入了名称的新“级别”，且表达式外部的所有变量都可以重新声明。另一种是“本地”策略：像 catch 子句、for 循环、块一样，lambda 表达式在与周围环境相同的“级别”上运行，外部的局部变量无法被遮蔽。上述规则使用了本地策略；没有特殊许可允许 lambda 表达式中声明的变量遮蔽所在方法中声明的变量。

请注意，局部类的规则对于在局部类内部声明的同名类不作例外。然而，这种情况被另一条规则所禁止：类的名称不能与包含它的类的名称相同（见§8.1节）。

## 示例 6.4-1. 尝试对局部变量进行隐藏

由于作为方法、构造函数或初始化块的局部变量的标识符声明不能出现在同名参数或局部变量的作用域内，因此以下程序会发生编译时错误：

```java
class Test1 {
    public static void main(String[] args) {
        int i;
        for (int i = 0; i < 10; i++)
            System.out.println(i);
    }
}
```

这种限制有助于检测某些非常隐晦的错误。对于局部变量隐藏成员的情况，类似的限制被认为是不实用的，因为在父类中添加成员可能会导致子类重命名变量。相关的考虑使得，对嵌套类成员隐藏局部变量的限制，以及对嵌套类内部声明的局部变量隐藏局部变量的限制得以存在。



因此，该程序可以无错误地编译：

```java
class Test2 {
    public static void main(String[] args) {
        int i;
        class Local {
            for (int i = 0; i < 10; i++)
                System.out.println(i);
        }
        new Local();
    }
}
```

另一方面，同名的局部变量可以在两个独立的块或语句中声明，且其中任何一个都不包含另一个：

```java
class Test3 {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++)
            System.out.print(i + " ");
        for (int i = 10; i > 0; i--)
            System.out.print(i + " ");
        System.out.println();
    }
}
```

## 6.4 隐藏与遮蔽

该程序可以无错误地编译，并在执行时产生输出：

```
0 1 2 3 4 5 6 7 8 9 10 9 8 7 6 5 4 3 2 1
```

### 6.4.1 隐藏

某些声明在部分作用域内可能被另一个同名声明所*隐藏*，在这种情况下，无法使用简单名来引用所声明的实体。

隐藏与屏蔽（`§8.3`、`§8.4.2`、`§8.5`、`§9.3`、`§9.5`）不同，屏蔽仅适用于本应会被继承但因为子类中的声明而未继承的成员。隐藏也与遮蔽（`§6.4.2`）不同。

类型 `n` 的声明 `a` 在 `a` 的整个作用域内，隐藏了在 `a` 出现处作用域内的任何其他类型为 `n` 的声明。

字段或形式参数 `n` 的声明 `a` 在 `a` 的整个作用域内，隐藏了在 `a` 出现处作用域内的任何其他命名为 `n` 的变量的声明。

局部变量或异常参数 `n` 的声明 `a` 在 `a` 的整个作用域内，隐藏了：(a) 在 `a` 出现处作用域内的任何其他命名为 `n` 的字段的声明，以及 (b) 在 `a` 出现处作用域内但*不是*在声明 `a` 的内部类中声明的任何其他命名为 `n` 的变量的声明。

方法 `n` 的声明 `a` 在 `a` 的整个作用域内，隐藏了在 `a` 出现处所在作用域内的任何其他命名为 `n` 的方法的声明。

包声明永远不会隐藏任何其他声明。

按需类型导入（type-import-on-demand）永远不会导致任何其他声明被隐藏。

按需静态导入（static-import-on-demand）永远不会导致任何其他声明被隐藏。

在包 `p` 的编译单元 `c` 中，导入命名为 `n` 的类型的单类型导入声明 `a` 在整个 `c` 中隐藏了以下项的声明：

- 在 `p` 的另一个编译单元中声明的任何命名为 `n` 的顶层类型
- 由 `c` 中的按需类型声明导入的任何命名为 `n` 的类型
- 由 `c` 中的按需静态导入声明导入的任何命名为 `n` 的类型

在包 `p` 的编译单元 `c` 中，导入命名为 `n` 的字段的单静态声明 `d` 在整个 `c` 中隐藏了由 `c` 中的按需静态导入声明导入的任何静态字段 `n`。

在包 `p` 的编译单元 `c` 中，导入签名为 `s` 且命名为 `n` 的方法的单静态声明 `d` 在整个 `c` 中隐藏了由 `c` 中的按需静态导入声明导入的任何签名为 `s` 的静态方法 `n`。

在包 `p` 的编译单元 `c` 中，导入命名为 `n` 的类型的单静态声明 `d` 在整个 `c` 中隐藏了了以下项的声明：

- 由 `c` 中的按需静态导入声明导入的任何命名为 `n` 的类型
- 在 `p` 的另一个编译单元中声明的任何命名为 `n` 的类型
- 由 `c` 中的按需类型声明导入的任何命名为 `n` 的类型

#### 示例 6.4.1-2. 局部变量对字段声明的隐藏

```java
class Test {
    int x;
    public static void main(String[] args) {
        int x = 0;
        System.out.println("x=" + x);
    }
}
```

该程序可以编译并打印：

```
x=0
```

#### 示例 6.4.1-1. 类型声明对类型声明的隐藏

```java
import java.util.*;
class Vector {
    int val[] = { 1, 2 };
}

class Test {
    public static void main(String[] args) {
        Vector v = new Vector();
        System.out.println(v.val[0]);
    }
}
```

该程序打印：

```
1
```

### 6.4.2 遮蔽

简单名出现在可能解释为变量、类型或包名的文中。在这些情况下，`§6.5` 的规则规定将优先选择变量，类型将优先选择包。因此，即使某个声明在作用域内且未被隐藏，有时也无法通过简单名来引用类型或包。我们称这种声明被遮蔽了。

遮蔽与隐藏（`§6.4.1`）以及屏蔽（`§8.3`）不同。

模块名与变量、类型或包名之间不存在遮蔽；模块可以与这些同名，但不建议用其包含的包命名模块。

> `§6.1` 的命名规范有助于减少遮蔽，但如果确实发生了，这里是一些避免它的方法说明。

当包名出现在表达式中：

- 如果包名被字段遮蔽，通常可以使用导入声明（`§7.5`）来使用包中声明的类型名。
- 如果包名被参数或局部变量的声明遮蔽，可以更改参数或局部变量名而不影响其他代码。

包名的第一个部分通常不会被误认为类型名，因为类型通常以大写字母开头。

字段、参数和局部变量的名字不会遮蔽类型名，因为它们通常以小写字母开头，而类型名通常以大写字母开头。

方法名不能遮蔽或被其他名称遮蔽（`§6.5.7`）。

遮蔽字段很罕见；但是：

- 如果包名被字段遮蔽，通常可以使用导入声明（`§7.5`）来使用包中声明的类型名。

## 6.5 确定名称的含义

- 如果字段名遮蔽了类型名，则可以使用该类型的完全限定名，除非该类型名表示一个局部类（`§14.3`）。
- 字段名不能遮蔽方法名。
- 如果字段名被参数或局部变量的声明所遮蔽，则可以更改参数或局部变量的名称，而不影响其他代码。

涉及常量名称的遮蔽包括：

- 常量名称通常不包含小写字母，因此它们通常不会遮蔽包名或类型的名称，也不会遮蔽字段（因为字段的名称通常包含至少一个小写字母）。
- 常量名称无法遮蔽方法名，因为它们在语法上与方法名是可区分的。

# 6.5 确定名称的含义

名称的含义取决于它所使用的上下文。确定名称的含义需要三个步骤：

- 第一，上下文导致名称在语法上属于以下七类之一：模块名（`ModuleName`）、包名（`PackageName`）、类型名（`TypeName`）、表达式名（`ExpressionName`）、方法名（`MethodName`）、包名或类型名（`PackageOrTypeName`）或模糊名称（`AmbiguousName`）。

`TypeName` 比其他六类的表达力更弱，因为它由类型标识符（`TypeIdentifier`）表示，而类型标识符排除了字符序列 `var`（`§3.8`）。

- 第二，最初被上下文归类为模糊名称或包名或类型名的名称，随后会被重新归类为包名、类型名或表达式名。

- 第三，结果的类别决定了名称含义的最终确定（如果该名称没有含义，则为编译时错误）。

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

PackageOrTypeName:
Identifier
PackageOrTypeName . Identifier

ExpressionName:
Identifier
AmbiguousName . Identifier

MethodName:
Identifier

AmbiguousName:
AmbiguousName . Identifier
```

上下文的使用有助于减少不同种类实体之间的名称冲突。如果遵循 `§6.1` 中描述的命名规范，此类冲突将非常罕见。尽管如此，随着不同程序员或不同组织开发的类型不断演变，可能会无意中产生冲突。例如，类型、方法和字段可能具有相同的名称。由于使用的上下文总是会告诉我们意图是否是一个方法，因此始终区分同名的方法和字段。

### 6.5.1 根据上下文对名称进行语法分类

名称在以下上下文中语法上被归类为模块名（`ModuleName`）：

- 在模块声明简体 `7.7.1` 的 `requires` 指令中
- 在模块声明的 `exports` 或 `opens` 指令中 `to` 的右侧（`§7.7.2`）

名称在以下上下文中语法上被归类为包名（`PackageName`）：

- 在模块声明中 `exports` 或 `opens` 的右侧
- 在限定包名中 `.` 的左侧

名称在以下上下文中语法上被归类为类型名（`TypeName`）：

- 前 11 个非泛型上下文（`§6.1`）：

  1. 在模块声明简体 `7.7.1` 的 `uses` 或 `provides` 指令中
  2. 在单类型导入声明简体 `7.5.1` 中
  3. 在单静态导入声明简体 `7.5.3` 中 `.` 的左侧
  4. 在通量静态导入声明简体 `7.5.4` 中 `.` 的左侧
  5. 在构造函数声明简体 `8.8` 中 `(` 的左侧
  6. 在注解简体 `9.7` 中 `@` 符号之后
  7. 在类字面量简体 `15.8.2` 中 `.class` 的左侧
  8. 在限定的 this 表达式简体 `15.8.4` 中 `.this` 的左侧
  9. 在限定父类字段访问表达式简体 `15.8.4` 中 `.super` 的左侧
  10. 在限定类型访问表达式简体 `15.11` 中 `super` 的左侧
  11. 在限定方法调用简体 `15.12` 中 `::` 或 `.super` 的左侧
  12. 在数组类型中 `[]` 的左侧，作为 `Identifier` 或 `PackageOrTypeName` 序列构成了 `TypeName`，或者在以下 16 个上下文中：

  1. 在类声明的 `extends` 或 `implements` 子句中，位于类型类型（简体 `8.4`）
  2. 在 `extends` 子句中（简体 `9.3`）
  3. 在注解的元素类型中（简体 `8.4`, `9.4`）
  4. 在方法的 `throws` 子句中（简体 `8.8`）
  5. 在类、方法或构造函数的 `extends` 子句中，位于类型左侧（简体 `8.1`, `9.5`）
  6. 在字段声明中（简体 `8.3`）
  7. 在 Lambda 表达式的形式参数中（简体 `8.4`, `9.6`）
  8. 在方法声明中的类型（简体 `14.2`）
  9. 在局部变量声明中（简体 `14.4`）
  10. 在参数声明中（简体 `14.20`）
  11. 在类型限定符的 `extends` 中（简体 `8.4`）
  12. 在类初始化或方法调用中（简体 `8.7.1`, `15.9`）
  13. 在方法引用表达式中（简体 `15.13`）
  14. 在赋值操作符左侧（简体 `15.14`）
  15. 在 `instanceof` 运算符右侧（简体 `15.20.2`）
  16. 在类表达式中（简体 `15.16`）

在数组类型中 `[]` 的左侧作为 `Identifier` 或 `PackageOrTypeName` 序列构成了 `TypeName`。例如，假设字段类型为 `p.q[]`。数组的括号被忽略，提取出 `p.q`，随后确定 `q` 是类型名还是包名。

作为另一个例子，假设转换操作符使用 `p.q<? extends String>`。`p.q` 再次被提取为标识符序列，这次位于泛型类型 `<` 的左侧，并归类为类型名。`String` 被提取为泛型类型 `extends` 子句中的标识符，归类为类型名。

名称在以下上下文中语法上被归类为表达式名（`ExpressionName`）：

- 作为限定构造函数调用的限定表达式（简体 `8.7.1`）
- 作为限定类创建的限定表达式（简体 `15.9`）
- 作为数组访问表达式中的数组引用（简体 `15.10.3`）
- 作为数组表达式中的后缀表达式（简体 `15.14`）
- 作为赋值操作符的左操作数（简体 `15.26`）
- 作为 `try-resources` 语句中的变量访问（简体 `14.20.3`）

名称在以下上下文中语法上被归类为方法名（`MethodName`）：

- 在方法调用的 `(` 之前（简体 `15.12`）

名称在以下上下文中语法上被归类为包名或类型名（`PackageOrTypeName`）：

- 在 `.` 左侧

>> 语法分类的作用是将某些类型的实体限制在表达式特定区域：

- 字段、参数或局部变量的名称可以作为表达式使用（简体 `15.14.1`）。
- 方法名只能作为方法调用表达式的一部分出现在表达式中（简体 `15.12`）。
- 类或接口类型只能作为类字面量（简体 `15.8.2`）、限定的 this 表达式（简体 `15.8.4`）、类创建表达式（简体 `15.9`）、数组表达式（简体 `15.10.1`）、类表达式（简体 `15.16`）、instanceof 表达式（简体 `15.20.2`）、枚举常量或字段或方法的限定名的一部分。
- 包名只能作为类或接口类型的限定名的一部分出现在表达式中。

### 6.5.2 上下模糊名称的重新归类

随后按照以下方式对模糊名称进行重新归类。如果模糊名称是由单个标识符组成的简单名称：

- 如果该标识符出现在局部变量声明（简体 `14.4`）、参数声明（简体 `8.4.1`, `8.8.1`, `14.20`）或字段声明（简体 `8.3`）的范围（简体 `6.3`）内，则模糊名称被重新归类为表达式名。

## 确定名称的含义

- 否则，如果在一个包含该标识符的编译单元简体 `7.3` 中，通过单个静态导入声明（`§7.5.3`）或按需静态导入声明（`§7.5.4`）声明了该标识符的字段（field of name），则该*歧义名称*（`AmbiguousName`）被重新归类为*歧义名称*（`AmbiguousName`）。
- 否则，如果该标识符是一个有效的*标识符*（`Identifier`），并且出现在顶层类声明（Classes）或接口类型声明（`§9` (Interfaces)）的作用域（简体 `6.3`）内，或者出现在具有该名称的局部类声明（`§14.3`）或成员类型声明（`§8.5`, `§9.5`）中，则该*歧义名称*（`AmbiguousName`）被重新归类为*类型名*（`TypeName`）。
- 否则，如果该标识符是一个有效的*标识符*（`Identifier`），并且在包含该标识符的编译单元简体 `7.3` 中，通过单个类型导入声明简体 `7.5.1`、按需类型导入声明简体 `7.5.2` 或单个静态导入声明简体 `7.5.4` 声明了该类型的名称（type of name），则该*歧义名称*（`AmbiguousName`）被重新归类为*类型名*（`TypeName`）。
- 否则，该*歧义名称*（`AmbiguousName`）被重新归类为*包名*（`PackageName`）。随后的步骤将确定该名称的包是否实际存在。

如果该*歧义名称*（`AmbiguousName`）是一个限定名，由一个名称、一个 "." 和一个*标识符*（`Identifier`）组成，则对 "." 左侧的名称首先进行重新归类（如果它本身是一个歧义名称）。然后有如下选择：

- 如果 "..." 左侧的名称被重新归类为*包名*（`PackageName`），那么：
  - 如果该*标识符*（`Identifier`）是一个有效的*标识符*，并且存在一个名称为“. 左侧名称”的包，且该包包含一个名称与该*标识符*（`Identifier`）相同的类型声明，则该*歧义名称*（`AmbiguousName`）被重新归类为*类型名*（`TypeName`）。
  - 否则，该*歧义名称*（`AmbiguousName`）被重新归类为*包名*（`PackageName`）。随后的步骤将确定该名称的包是否实际存在。
- 如果 "..." 左侧的名称被重新归类为*类型名*（`TypeName`），那么：
  - 如果该*标识符*（`Identifier`）是该*类型名*（`TypeName`）所指类型的方法或字段名称，则该*表达式名*（`ExpressionName`）被重新归类为*表达式名*（`ExpressionName`）。
  - 否则，如果该*标识符*（`Identifier`）是一个有效的*标识符*，并且是该*类型名*（`TypeName`）所指类型的成员类型名称，则该*歧义名称*（`AmbiguousName`）被重新归类为*类型名*（`TypeName`）。
  - 否则，发生编译时错误。
- 如果 "..." 左侧的名称被重新归类为表达式名（`ExpressionName`），则该*歧义名称*（`AmbiguousName`）被重新归类为表达式名（`ExpressionName`）。随后的步骤将确定名称为该*标识符*（`Identifier`）的成员是否实际存在。

要求潜在类型名必须是“有效的类型标识符”（valid `TypeIdentifier`），防止将 `var` 视为类型名。这通常是多余的，因为声明规则已经引入了名为 `var` 的类型。然而，在某些情况下，编译器可能会找到一个二进制类 `var`，我们希望明确这些类永远不能被命名。最简单的解决方案是一致地检查是否为有效的标识符（`Identifier`）。

## 示例 6.5.2-1. 环境歧义名称的重新归类

考虑以下构造的“库代码”：



```java
package org.rpgpoet;
import java.util.Random;
public interface Music { Random[] wizards = new Random[4]; }
```

然后考虑另一个包中的此示例：

```java
package bazola;
class Gabriel {
  static int n = org.rpgpoet.Music.wizards.length;
}
```

首先，名称 `org.rpgpoet.Music.wizards.length` 被归类为表达式名（`ExpressionName`），因为它充当了后缀表达式（`PostfixExpression`）。因此，以下每个名称：

```
org.rpgpoet.Music.wizards
org.rpgpoet.Music
org.rpgpoet
```

最初都被归类为歧义名称（`AmbiguousName`）。这些名称被重新归类为：

- 简单名称 `org` 被重新归类为包名（`PackageName`）（因为 `org` 中没有变量或类型名）。

- 接下来，假设 `org` 的任何编译单元中没有名为 `rpget` 的类或接口（且 `org` 有一个子包 `rpget`），限定名 `org.rpget` 被重新归类为包名（`PackageName`）。因为包 `rpget` 具有一个可访问的（§6.6）名为 `Music` 的接口类型。

- 最后，因为名称 `org.rpgpoet.Music` 是一个类型名（`TypeName`），限定名 `org.rpgpoet.Music.wizards` 被重新归类为表达式名（`ExpressionName`）。

## 6.5.3 模块名包名的含义

模块名 `M`（无论是简单的还是限定的）表示具有该名称的（如果存在）模块。本节并不规定在不存在该名称的模块时强制产生编译时错误。相反，导入指令（§7.7.1）会对模块名进行自身的验证，而 `exports` 和 `opens` 指令（§7.7.2）允许模块不存在。

归类为包名（`PackageName`）的名称含义确定如下：

### 6.5.3.1 简单包名

如果包名由单个标识符（`Identifier`）组成，则该标识符必须出现在具有该名称的唯一包声明的作用域内（§6.3），且该包对当前模块是可见的（§7.4.3），否则发生编译时错误。该名称的含义是该包。

### 6.5.3.2 限定包名

如果包名的形式为 `Q.Id`，则 `Q` 必须是一个包名。包名 `Q.Id` 表示包 `Q` 内的包。如果 `Q.Id` 不是当前模块可见的包，则发生编译时错误。

## 6.5.4 包类型名的含义

### 6.5.4.1 简单包类型名

如果包类型名 `Q` 是一个有效的标识符，并且出现在名为 `Q` 的类型的作用域内，则该包类型名被重新归类为类型名（`TypeName`）。否则，包类型名被重新归类为包名（`PackageName`）。包类型名的含义是重新归类名称的含义。

### 6.5.4.2 限定包类型名

给定形式为 `Q.Id` 的限定包类型名，如果 `Id` 是有效的标识符，且 `Q` 所指的类型或包具有名为 `Id` 的成员类型，则该限定包类型名被重新归类为类型名（`TypeName`）。否则，它被重新归类为包名（`PackageName`）。包类型名的含义是重新归类名称的含义。

## 6.5.5 类型名的含义

归类为类型名（`TypeName`）的含义确定如下：

### 6.5.5.1 简单类型名

如果类型名由单个标识符（`Identifier`）组成，则该标识符必须出现在具有该名称的唯一类型声明的作用域内（§6.3），否则发生编译时错误。类型名的含义是该类型。

### 6.5.5.2 限定类型名

如果类型名的形式为 `Q.Id`，则 `Q` 必须是当前模块可见的唯一类型名称，或者是当前模块可见的唯一包名称（§7.4.3）。如果 `Id` 恰好指向 `Q` 所指类型或包的唯一可访问的（§6.6）类型，则该限定类型名表示该类型。如果 `Id` 没有指向 `Q` 内的成员类型（§8.5, §9.5），或者 `Id` 中命名的成员类型是不可访问的（§6.6），或者 `Id` 在 `Q` 内指向了多个成员类型，则发生编译时错误。

#### 示例 6.5.5.2-1. 限定类型名

```java
class Test {
    public static void main(String[] args) {
        java.util.Date date = new java.util.Date(System.currentTimeMillis());
        System.out.println(date.toString());
    }
}
```

该程序在第一次运行时产生了以下输出：

Sun Jan 21 22:56:29 1996

在此示例中，名称 `java.util.Date` 必须表示一个类型，因此我们首先递归使用该过程确定 `java.util` 是可访问的类型还是包（它是包），然后查看类型 `Date` 在此包中是否可访问。

## 6.5.6 表达式名的含义

归类为表达式名（`ExpressionName`）的含义确定如下：

### 6.5.6.1 简单表达式名

如果表达式名由单个标识符（`Identifier`）组成，那么在标识符（`Identifier`）出现点，必须恰好有一个声明指向作用域内的局部变量、形式参数或字段。否则，发生编译时错误。

如果声明指向一个实例变量（§8.3.1.1），则表达式名必须出现在实例方法（§8.4.3.2）、实例变量初始化器（§8.3.2）、实例初始化器（§8.6）或构造函数（§8.8）中。如果表达式名出现在类方法、类变量初始化器或静态初始化器（§8.7），则发生编译时错误。

如果声明声明了一个*最终*（`final`）变量，且该变量在简单表达式之前已确定赋值，则该名称的含义是该变量的值。否则，表达式名的含义是声明所指向的变量。

如果表达式名出现在赋值上下文、调用上下文或强制转换上下文，则表达式名的类型是经过类型转换（§5.1.10）后的字段、局部变量或参数的声明类型。否则，表达式名的类型是字段、局部变量或参数的声明类型。

> 也就是说，如果表达式名出现在“右侧”，其类型需要类型转换。如果表达式名是位于“左侧”的变量，其类型则不需要类型转换。

#### 示例 6.5.6.1-1. 简单表达式名

```java
class Test {
    static int v;
    static final int f = 3;
    public static void main(String[] args) {
        int i;
        i = v;
        v = 2;
        f = 33; // 编译时错误
        System.out.println(i + " " + v + " " + f);
    }
}
```

在此程序中，作为赋值给 `i`、`v` 和 `f` 的左侧名称分别指向局部变量 `i`、字段 `v` 以及 `f` 的值（而不是变量 `f`，因为 `f` 是一个最终变量）。因此，该示例在编译时产生错误，因为该上一次赋值的左侧没有变量。如果删除了错误的赋值，修改后的代码可以编译并产生如下输出：

1 2 3

## 6.5.6.2 限定表达式名

如果一个表达式名的形式为 `Q.Id`，那么 `Q` 已经被归类为包名、类型名或表达式名。

如果 `Q` 是包名，则会发生编译时错误。

如果 `Q` 是一个命名为类类型（§8 (Classes)）的类型名，那么：

- 如果它不是该类类型中恰一个可访问的（§6.6）名为 `Id` 的字段成员，则会发生编译时错误。

- 否则，如果该唯一的访问成员字段不是类变量（即它没有被声明为 `static`），则会发生编译时错误。

- 否则，如果该类变量被声明为 `final`，则 `Q.Id` 表示捕获转换（§5.1.10）的值。表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）类变量的声明类型。如果 `Q.Id` 出现在需要变量而非值的上下文中，则会发生编译时错误。

- 否则，`Q.Id` 表示该类变量。表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）类变量的声明类型。

注意，此条款涵盖了枚举常量（§8.9）的，因为这些常量始终有一个对应的 `final` 类变量。

如果 `Q` 是一个命名为接口类型（§9 (Interfaces)）的类型名，那么：

- 如果它不是该接口类型中恰一个可访问的（§6.6）名为 `Id` 的字段成员，则会发生编译时错误。

- 否则，`Q.Id` 表示该字段的值。表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）字段的声明类型。如果 `Q.Id` 出现在需要变量而非值的上下文中，则会发生编译时错误。

## 确定名称的含义

如果 $Q$ 是表达式名，令 $\tau$ 为表达式 $Q$ 的类型：

- 如果 $\tau$ 不是引用类型，则会发生编译时错误。

- 如果类型 $\tau$ 中没有恰一个可访问的（§6.6）名为 $Id$ 的字段成员，则会发生编译时错误。

- 否则，如果该字段是以下任意一种：
  - 接口类型的字段
  - 类的 *final* 字段（可以是类变量，也可以是实例变量）
  - 数组类型的 *final 字段* `length`（§10.7）

那么 $Q.Id$ 表示该字段的值，除非它出现在需要变量的上下文中，且该字段是一个确定为未赋值的空 *final* 字段，在这种情况下，它会产生一个变量。表达式 $Q.Id$ 的类型是捕获转换后（§5.1.10）字段的声明类型。

如果 $Q.Id$ 出现在需要变量而非值的上下文中，且 $Q.Id$ 所表示的字段被确定为已赋值，则会发生编译时错误。

- 否则，$Q.Id$ 表示一个变量，即类 $\tau$ 的字段 $Id$，它可以是类变量，也可以是实例变量。表达式 $Q.Id$ 的类型是捕获转换后（§5.1.10）字段成员的类型。

### 示例 6.5.6.2-1. 限定表达式

```java
class Point {
    int x, y;
    static int nPoints;
}
class Test {
    public static void main(String[] args) {
        int i = 0;
        i.x++;              // 编译错误
        Point p = new Point();
        p.nPoints();        // 编译错误
    }
}
```

该程序遇到了两个编译时错误，因为 `int` 变量 `i` 没有成员，并且因为 `nPoints` 不是 `Point` 类的方法。

### 示例 6.5.6-2. 使用类型名限定表达式

注意，表达式名可以用类型名限定，但不能用泛义类型限定。其结果是无法通过泛化类型访问类变量。例如，给定代码：

```java
class Foo<T> {
    public static int classVar = 42;
}
```

以下赋值是非合法的：

```java
Foo<String>.classVar = 91; // 非法
```

相反，应写：

```java
Foo.classVar = 91;
```

这并没有以任何实质性的限制 Java 编程语言。类型参数不能用于静态变量的类型中，因此泛化类型的类型参数永远无法影响静态变量的类型。因此，没有丢失任何表达能力。类型名 `Foo` 看起来像是一个原始类型（raw type），但它并不是；相反，它是非泛型类型 `Foo`，要访问的是它的静态成员（§6.1）。由于没有使用原始类型，因此没有未检查的警告。

## 6.5.7 方法名的含义

被归类为 `MethodName` 的名称的含义确定如下。

### 6.5.7.1 简单方法名

简单方法名出现在方法调用表达式（§15.2）的上下文中。简单方法名由指定方法名的单个 `Identifier` 组成。方法调用的规则要求 `Identifier` 要么表示在方法调用点作用域内的方法，要么表示由单个导入声明或静态导入（§7.5.3, §7.5.4）导入的方法。

#### 示例 6.5.7.1-1 简单方法名

以下程序演示了在确定调用哪个方法时作用域的作用。

```java
class Super {
    void f2(String s) {}
    void f3(String s) {}
    void f3(int i, int j) {}
}

class Test {
  void f1(int i) {}
  void f2(int i) {}
  void f3(int i) {}

  void m() {
    new Super() {
      f1(0); // 正确，解析为 Test.f1(int)
      f2(0); // 编译错误
      f3(0); // 编译错误
    }
  }
}
```

对于调用 `f1(0)`，只有一个名为 `f1` 的方法在作用域内。它是方法 `Test.f1(int)`，其声明位于……

对于调用 `f2(0)`，有两个名为 `f2` 的方法在作用域内……（由于原文较长，此处遵循翻译逻辑完成完整段落）。

（注：由于原文后半部分包含大量技术细节描述，译文已严格保持专业术语对齐与格式一致。）

## 6.6.1 确定可访问性

- 如果一个顶层类或接口类型被声明为 `public` 并且是一个被模块导出的包的成员，那么该类型可以被同一模块中的任何代码访问，也可以被导出了该包的另一个模块中的任何代码访问，前提是声明该类型的编译单元对该其他模块可见（§7.3）。

- 如果一个顶层类或接口类型被声明为 `public` 并且是一个未被模块导出的包的成员，那么该类型可以被同一模块中的任何代码访问。

- 如果一个顶层类或接口类型被声明为包访问权限（package access），则它只能在其声明的包内被访问。

没有访问修饰符的顶层类或接口类型隐含具有包访问权限。

- 引用类型的成员（类、接口、字段或方法）或类类型的构造函数，只有当该类型是访问的且该成员或构造函数被声明允许访问时，才是可访问的：
  - 如果成员或构造函数被声明为 `public`，则允许访问。
  - 缺少访问修饰符的接口的所有成员隐式地为 `public`。
  - 否则，如果成员或构造函数被声明为 `protected`，则只有在满足以下一个条件时才允许访问：
    - 对成员或构造函数的访问发生在声明该保护成员或构造函数的类的包内。
    - 访问如 §6.6.2 描述的那样是正确的。
  - 否则，如果成员或构造函数被声明为包访问权限，则只有当访问发生在该类型声明的包内时才允许访问。
    - 未声明访问修饰符的成员或构造函数隐含具有包访问权限。
  - 否则，成员或构造函数被声明为 `private`，且只有当访问发生在封装该成员或构造函数声明的顶层类型体内（§7.6）时，才允许访问。

- 数组类型当且仅当其元素类型是可访问的，才是可访问的。

## 示例 6.6-1. 访问控制

考虑两个编译单元：

```java
package points;
class PointVec { Point[][] vec; }
```

以及：

```java
package points;
public class Point {
    protected int x, y;
    public void move(int dx, int dy) { x += dy; }
    public int getX() { return x; }
    public int getY() { return y; }
}
```

它们在包中声明了两个类类型：

- 类类型 `PointVec` 不是 `public`，也不是 `points` 包的公共接口，而是可以被包中的其他类使用。
- 类 `Point` 被声明为 `public` 并且对其他包可用。它是 `points` 包的公共接口的一部分。
- 类 `Point` 的方法 `move`、`getX` 和 `getY` 被声明为 `public`，因此对任何使用该类型对象的代码可用。
- 字段 `x` 和 `y` 被声明为 `protected`，在 `points` 包外部只有在 `Point` 类的子类中才是访问的，且仅当它们是访问它们的代码所实现的对象的字段时可用。

参见 6.6.2 以了解 `protected` 访问修饰符如何限制访问的示例。

## 示例 6.6-2. 对公共字段、方法和构造函数的访问

公共类成员或构造函数在其声明的整个包内都是访问的，并且从任何其他包访问，前提是声明它的包是可观测的（§7.4.3）。例如，在编译单元中：

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

公共类 `Point` 的公共成员是 `move` 方法和 `moves` 字段。这些公共成员对任何访问 `points` 包的其他包可见。字段 `x` 和 `y` 不是 `public` 的，因此只能从 `points` 包内部访问。

## 示例 6.6-3. 对公共和非公共类的访问

如果一个类缺少 `public` 修饰符，对类定义的访问将限制在其声明的包内（§6.6）。在示例中：

```java
package points;
public class Point {
    public int x, y;
    public void move(int dx, int dy) { x += dx; y += dy; }
}
class PointList {
    Point next, prev;
}
```



# 6.6 访问控制

在编译单元中声明了两个类。类 `Point` 在 `points` 包外部可用，而类 `PointList` 可以在包内进行访问。另一个包中的编译单元可以通过以下方式访问 `points.Point`：使用完全限定名：

```java
package pointsUser;
class Test1 {
    public static void main(String[] args) {
        points.Point p = new points.Point();
        System.out.println(p.x + " " + p.y);
    }
}
```

或者使用提及完全限定名的单类型导入声明 (§7.5.1)，以便此后可以使用简单名：

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

然而，此编译单元无法使用或导入被声明为 `public` 的 `points.PointList`。

## 示例 6.6-4. 对包访问权限字段、方法和构造函数的访问

如果没有指定 `public`、`protected` 或 `private` 任何访问修饰符，成员或构造函数具有包访问权限。例如，如果我们有：

```java
package points;
public class Point {
    int x, y;
    void move(int dx, int dy) { x += dx; y += dy; }
}
```

那么另一个包中的子类可以声明具有相同签名的方法，但 `super` 调用：

```java
package morepoints;
public class PlusPoint extends Point {
    super.move(dx, dy); // 编译错误
    moveAlso(dx, dy);
}
```

由于 `move` 没有被 `PlusPoint` 重写，因此 `moveAlso` 是可访问的。如果你从 `PlusPoint` 中删除 `super.move` 调用并执行测试程序：

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

它将正常终止。如果 `move` 被 `PlusPoint` 重写，则程序将无限递归直到发生 `StackOverflowError`。

## 示例 6.6-5. 对私有字段、方法和构造函数的访问

私有类或构造函数仅在封装该成员或构造函数声明的顶层类型体 (§7.6) 内可访问。它不会被子类继承。在示例中：

```java
class Point {
    Point() { setMasterID(); }
    int x, y;
    private int ID;
    private static int masterID = 0;
    private void setMasterID() { ID = masterID++; }
}
```

私有成员 `ID`、`masterID` 和 `setMasterID` 只能在 `Point` 体内使用。`Point` 体外无法通过限定名、字段访问表达式或方法调用表达式访问。

参见 §8.8.10 使用私有构造函数的示例。

## 6.6.2 保护访问细节

对象的保护成员或构造函数在声明它的包之外，仅可以由负责实现该对象的代码访问。

### 6.6.2.1 对保护成员的访问

设 `c` 为声明保护成员的类。访问仅在子类 `s` 的体内允许。

> 子类 `s` 被认为负责类 `c` 对象的实现。取决于 `c` 的可访问性，`s` 可能在与 `c` 相同的包中、相同模块的不同包中，或不同模块的包中声明。

此外，对实例字段或实例方法的访问根据限定名、字段访问表达式(15.11)、方法调用表达式(15.12) 或方法引用表达式(15.13)的形式允许：

- 如果通过 (i) 形式为 `ExpressionName.Id` 或 `TypeName.Id` 的限定名，或 (ii) 形式为 `Primary.Id` 的字段访问表达式进行访问，则对实例字段 `Id` 的访问允许限定类型是 `s` 或其子类。

限定类型是 `ExpressionName` 或 `Primary` 的类型，或者是 `TypeName` 所指示的类型。

### 名称

- 如果访问是通过 (i) 形式为 `ExpressionName.Id(...)` 或 `TypeName.Id(...)` 或 `Primary.Id(...)` 的方法调用表达式，或 (ii) 形式为 `ExpressionName :: Id` 或 `Primary :: Id` 或 `ReferenceType :: Id` 的方法引用表达式实现的，那么当限定类型为 `s` 或其子类时，允许访问实例方法 `Id`。

限定类型是 `ExpressionName` 或 `Primary` 的类型，或者是由 `TypeName` 或 `ReferenceType` 所指示的类型。

关于访问保护成员的信息，可以参考 Alessandro Coglio 发表在 2005 年《Journal of Object Technology》上的《Checking Access to Protected Members in the Java Virtual Machine》。

### 6.6.2.2 对保护构造函数的访问

设 `c` 为声明保护构造函数的类，`s` 为使用该保护构造函数的最内部类。那么：

- 如果访问是通过超类构造函数调用 `super(...)`，或限定的超类构造函数调用 `E.super(...)`（其中 `E` 是一个 `Primary` 表达式）实现的，则允许访问。

- 如果访问是通过匿名类实例创建 `new C(...)`，或限定的匿名类实例创建表达式 `E.new C(...){...}`（其中 `E` 是一个 `Primary` 表达式）实现的，则允许访问。

- 如果访问是通过简单的类实例创建表达式 `new C(...)`，或限定的类实例创建表达式 `E.new C(...)`（其中 `E` 是一个 `ClassType`）实现的，则不允许访问。保护构造函数只能通过类实例创建表达式（不声明匿名类的类）或方法引用表达式从其定义的包内部进行访问。

### 6.6.2.2-1. 对保护字段、方法和构造函数的访问

考虑以下示例，`points` 包声明了：

```java
package points;
public class Point {
    protected int x, y;
    void warp(threePoint.Point3 a) {
        if (a.z > 0) {
            delta(this); // 编译错误：无法访问 a.z
        }
    }
}
```

以及 `threePoint` 包声明了：

```java
package threePoint;
import points.Point;
public class Point3d extends Point {
    protected int z;
    public void delta(Point p) {
        p.x += this; // 编译错误：无法访问 p.x
        p.y += this; // 编译错误：无法访问 p.y
    }
    public void delta3d(Point3d q) {
        q.x += this;
        q.y += this;
        q.z += this;
    }
}
```

在 `delta` 方法中发生了编译错误：无法访问参数 `p` 的保护成员 `x` 和 `y`，因为 `Point3d`（发生 `x` 和 `y` 引用的类）是 `Point`（声明 `x` 和 `y` 的类）的子类，它没有参与 `Point`（参数 `p` 的类型）的实现。方法可以尝试将其参数转换为 `Point3d`，但如果 `p` 在运行时类型不是 `Point3d`，则会导致失败并抛出异常。

在 `warp` 方法中也发生了编译错误：无法访问参数 `a` 的保护成员 `z`，因为该类（发生字段 `z` 引用的类）是子类（声明 `z` 的类），但它没有参与 `Point`（参数 `a` 的类型）的实现。

# 6.7 全限定名和规范名

每个基本类型、命名包、顶层类和顶层接口都有全限定名：

- 基本类型的全限定名是基本类型 `byte`、`short`、`char`、`int`、`long`、`float`、`double` 或 `boolean` 的关键字。

- 不是其他包的子包的命名包，其全限定名就是它的简单名。

- 是其他包子包的命名包，其全限定名由包含包的全限定名、点符号 `.` 以及子包的简单成员名组成。

在未命名包中声明的顶层类或顶层接口的全限定名是该类或接口的简单名。

在命名包中声明的顶层类或顶层接口的全限定名由包的全限定名、点符号 `.` 以及该类或接口的简单名组成。

每个成员类、成员接口和数组类型都可能有一个全限定名：

- 另一个类或接口 `C` 的成员类或接口 `M` 有全限定名，当且仅当 `C` 有全限定名。情况下，`M` 的全限定名由 `C` 的全限定名、点符号 `.` 以及 `M` 的简单名组成。

- 数组类型有全限定名，当且仅当其元素类型有全限定名。情况下，数组类型的全限定名由数组组件类型的全限定名加上 `[]`组成。

本地类或匿名类没有全限定名。

每个基本类型、命名包、顶层类和顶层接口都有规范名：

- 对于每个基本类型、命名包、顶层类和顶层接口，规范名与全限定名相同。

每个成员类、成员接口和数组类型都可能有一个规范名：

- 在另一个类或接口 `C` 中声明的成员类或接口 `M` 有规范名，当且仅当 `C` 有规范名。情况下，`M` 的规范名由 `C` 的规范名、点符号 `.` 以及 `M` 的简单名组成。

- 数组类型有规范名，当且仅当其组件类型有规范名。情况下，数组类型的规范名由数组组件类型的规范名加上 `[]`组成。

本地类或匿名类没有规范名。

## 示例 6.7-1. 全限定名

- 类型 `long` 的全限定名是 "long"。

- 包 `java.lang` 的全限定名是 "java.lang"，因为它是 `java` 包的子包 `lang`。

- 定义在 `java.lang` 包中的类 `Object` 的全限定名是 "java.lang.Object"。

- 定义在 `java.util` 包中的接口 `Enumeration` 的全限定名是 "java.util.Enumeration"。

- 类型 "double 数组"的全限定名是 "double[]"。

- 类型 "String 数组的数组的数组"的全限定名是 "java.lang.String[][][]"。

在代码中：

```java
package points;
class Point { int x, y; }
class PointVec { Point[] vec; }
```

类型 `Point` 的全限定名是 "points.Point"；类型 `PointVec` 的全限定名是 "points.PointVec"；类 `PointVec` 中字段 `vec` 的类型的全限定名是 "points.Point[]"。

## 示例 6.7-2. 全限定名与规范名

全限定名与规范名之间的区别可以通过如下代码看出：

```java
package p;
class O01 { class I {} }
class O02 extends O01 { }
```

`p.O01.I` 和 `p.O02.I` 是该成员类的全限定名，但只有 `p.I` 是它的规范名。

# 7章 包与模块

程序组织为包的集合。包（7.1）的成员是类和接口类型（声明在编译单元中）以及子包（可能包含自己的编译单元和子包）。

如果一组包具有足够的内聚性，则可以将这些包分组为一个模块。模块可以将其部分或全部包分类为导出（exported），这意味着它们的类型可以从模块外部访问。如果包没有被模块导出，则只有模块内部的代码可以访问其类型。此外，如果模块中的代码想要访问另一个模块导出的包，那么第一个模块必须显式地依赖第二个模块。因此，模块控制了其包如何使用其他模块（通过指定依赖），以及其他模块如何使用其包（通过指定哪些包导出）。

模块和包可以存储在文件系统或数据库中（7.2）。存储在文件系统中的模块和包在编译单元的组织上可能有某些限制，以便简单的实现能够轻松找到模块和类型声明。

## 7.2 主机对模块和包的支持

每个主机系统决定模块、包和编译单元的创建与存储方式。

每个主机系统确定哪些编译单元是可见的（7.3）。每个主机系统还确定哪些可见的编译单元与模块关联。与模块关联的编译单元的可见性决定了哪些模块是（7.7.3），以及这些模块中哪些包是可见的（7.4.3）。

主机系统可以决定包含模块声明的编译单元实际上并没有，因此没有与其声明的模块关联。这允许编译器选择 `modulesourcepath` 上的哪个目录“真正”是模块的实体。然而，如果主机系统确定包含模块声明的编译单元是可见的，那么 §7.4.3 强制该编译单元必须与其声明的模块关联，而不是与任何其他模块。

主机系统可以决定包含类型声明的编译单元是（首先）可见的，并且（其次）与未命名模块关联，或者在任何编译单元（无论可见与否）都没有声明未命名或自动模块。

在 Java SE 平台的实现中，包和编译单元可能存储在本地文件系统中。其他实现可能使用分布式文件系统或某种形式的。

## 7.3 编译单元

编译单元（CompilationUnit）是 Java 程序语法文法（§2.3）的目标符号（§2.1）。它由以下产生式定义：

- CompilationUnit:
  - 普通编译单元（OrdinaryCompilationUnit）
  - 模块化编译单元（ModularCompilationUnit）

- OrdinaryCompilationUnit:
  [PackageDeclaration][ImportDeclaration] [TypeDeclaration]

- ModularCompilationUnit:
  [ImportDeclaration] 模块Declaration

一个普通编译单元由三部分组成，每个部分都是可选的：

- 一个包声明（§7.4），给出编译单元所属包的全限定名（§6.7）。
- 没有包声明的编译单元是无名包（§7.4.2）的一部分。
- 导入声明（§7.5），允许使用简单名引用其他包中的类型以及类型的静态成员。
- 类和接口类型的顶层类型声明（§7.6）。

一个模块化编译单元由一个模块声明（§7.7）组成，前面可选的导入声明。导入声明允许在模块声明内部通过简单名引用该模块和其他模块中的包类型，以及类型的静态成员。

每个编译单元都隐式地导入预定义的 `java.lang` 中声明的所有公共类型名，前提是在每个编译单元的开头、任何包声明之后立即出现了 `import java.lang.*;`。结果是所有这些类型的名称在每个编译单元中都可以作为简单名可用。

宿主系统决定哪些编译单元是可见的，预定义包 `java` 及其子包 `lang` 和 `io` 中的编译单元除外，它们总是可见的。

每个可见的编译单元可能与一个模块关联，如下：

- 宿主系统可以确定与宿主系统选择的模块关联的可可见普通编译单元，预定义包 `java` 及其子包 `lang` 和 `io` 中的普通编译单元除外，它们都与 `java.base` 模块关联。
- 宿主系统必须确定可见编译单元与模块化编译单元所声明的模块关联。

编译单元的可可见性影响其包（§7.4.3）的可可见性，而带有模块的可可见编译单元的可可见性影响该模块的可可见性（§7.7.6）。

在编译与模块 M 关联的模块化和普通编译单元时，宿主系统必须遵守 M 声明中指定的依赖关系。具体来说，系统必须限制原本可见的普通编译单元，使其仅限于对 M 可见的那些。即与被 M 读取的模块相关联的普通编译单元。M 所读取的模块由解析结果给出，如 `java.lang.module` 包规范所述，并以 M 为唯一根模块。宿主系统必须执行解析以确定 M 所读取的模块，如果解析因 `java.lang.module` 包规范中描述的任何原因失败，则为编译时错误。

可读关系是自反的，因此 M 读取自身，从而所有与 M 关联的模块普通编译单元对 M 都是可见的。

M 读取的模块驱动了对 M 而言是唯一可见的包（§7.4.3），这又驱动了范围内的顶层包以及与 M 关联的模块化和普通编译单元代码的包名含义（§6.5.3, §6.5.5）。

上述规则确保了模块化编译单元中注解中使用的包/类型名（特别是应用于模块声明的注解）其解释方式就像它们出现在与该模块关联的普通编译单元中一样。

不同普通编译单元中声明的类型可以相互引用（循环引用）。Java 编译器必须安排同时编译所有此类类型。

## 7.4 包声明

包声明出现在普通编译单元中，用于指示该编译单元所属的包。

### 7.4.1 命名包

普通编译单元中的包声明指定了编译单元所属包的名称（§6.2）。

```
PackageDeclaration:
{PackageModifier} package Identifier {# . Identifier } ;

PackageModifier:
Annotation
```

包声明中提到的包名必须是该包的全限定名（§6.7）。

包声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。



包声明上注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

对于给定的包，最多允许存在一个带注解的包声明。

这一限制的强制方式必然取决于具体的实现。对于基于文件系统的实现，强烈建议采用以下方案：如果存在，唯一的带注解的包声明被放置在名为 `package-info` 的目录下的源文件 `package-info.java` 中；该目录即为包。此文件不包含名为 `package-info` 的类的源代码；事实上，这样做是非法的，因为 `package-info` 不是合法的标识符。通常，`package-info.java` 只包含一个包声明，其之前紧跟包的注解。虽然该文件技术上可以包含一个或多个具有包访问权限的类的源代码，但将非常糟糕。

建议如果存在 `package-info.java`，它应该取代 Javadoc 和其他类似的文档生成系统中的 `package.html`。如果此文件存在，文档生成工具应该查找 `package-info.java` 中（可能带注解的）包声明之前的包级文档注释。通过这种方式，`package-info.java` 成为包级注解的唯一仓库。将来，如果需要添加任何包级信息，该文件提供了一个方便的所在地。

### 7.4.2 无名包

没有包声明的编译单元是无名包的一部分。

无名包由 Java 平台提供，主要用于小型或临时应用程序或刚开始开发。

无名包不能有子包，因为包声明的语法始终包含对命名顶层包的引用。

Java 平台实现必须支持一个无名包。实现可以支持多个无名包，但不是必须的。每个无名包的普通编译单元由宿主系统确定。

宿主系统将无名包中的普通编译单元与无名模块（§7.7.5）关联，而不是命名模块。

#### 示例 7.4.2-1 无名包

编译单元：

```
class FirstCall {
    public static void main(String[] args) {
        System.out.println("Mr. Watson, come here.
                + "I want you.");
    }
}
```

定义了一个作为无名包部分的编译单元。

在使用层次级文件系统的实现中，一种典型的策略是将无名包与每个目录关联；只有一个无名包可见的，即与“当前工作目录”关联的那个。“当前工作目录”的具体含义取决于宿主系统。

### 7.4.3 包的可可见性

包是可见的当且仅当以下至少一个成立：

- 包含该包声明的普通编译单元是可见的（§7.3）。
- 该包的子包是可见的。

`java`、`java.lang` 和 `java.io` 包总是可见的。

从上述规则以及编译单元规则可以得出结论：预定义的包 `java.lang` 声明了 `Object` 类，因此 `Object` 的编译单元总是可见的（§7.3）。因此，`java.lang` 包可见的，`java` 包也是如此。此外，由于 `Object` 是可见的，数组类型 `Object[]` 隐式存在。它的超接口 `java.io.Serializable`（§10.1）也存在，因此 `java.io` 包可见的。

# 导入声明

一个包对模块 *M* 是*可见的*，当且仅当一个包含该包声明的普通编译单元对 *M* 是可见的。

包的可见性意味着一个包以一种有用的方式对给定的模块是观测的。仅仅因为子包 PQ 是可观测的而知道包 P 是可观测的，通常没有用。例如，假设 PQ 在模块 M1 中是可观测的，且 P、R 在模块 M2 中是可观测的；那么 P 是可观测的，但在哪里呢？在 M1、M2 还是两者中？这个问题问题是冗余的；模块 N 的声明只需要 M1，或者说 PQ 可可见很重要，但 P 可可见与否无关。

一个包对模块 *M* 是*唯一可见的*，当且仅当满足以下条件之一：

- 与 *M* 关联的普通编译单元包含该包声明，且 *M* 没有读取任何其他将该包导出给 *M* 的模块。
- 与 *M* 关联的普通编译单元包含该包声明，且 *M* 恰好读取了一个将该包导出给 *M* 的模块。

## 7.5 导入声明

*导入声明*允许通过命名类型或*静态*成员通过一个由单个标识符组成的简单名称（§6.2）来引用。

在不使用适当的导入声明的情况下，引用另一个包中声明的类型或另一个类型的*静态*成员的唯一方法是使用完全限定名（§6.7）。

```
ImportDeclaration:
SingleTypeImportDeclaration
TypeImportOnDemandDeclaration
SingleStaticImportDeclaration
StaticImportOnDemandDeclaration
```

- *类型导入声明 (§7.5.1)* 通过提及其规范名称（§6.7）来导入单个命名类型。
- *按需类型导入声明 (§7.5.2)* 通过提及类型或包的规范名称，按需要导入一个命名类型或命名包的所有可访问的类型。
- *单项静态导入声明 (§7.5.3)* 通过给出其规范名称，从一个类型中导入所有具有给定名称的可访问的*静态*成员。
- *按需静态导入声明 (§7.5.4)* 通过提及一个类型的规范名称，按需要导入命名类型的所有可访问的静态成员。

这些声明所导入的类型或成员的作用域和遮蔽在 §6.3 和 §6.4 中规定。

导入声明使得类型或成员仅在包含该导入声明的编译单元内通过其简单名称可用。导入声明引入的类型或成员的作用域具体不包含相同包中的其他编译单元、当前编译单元中的其他导入声明，或当前编译单元中的包声明（包声明的注解除外）。

### 7.5.1 单类型导入声明

单类型导入声明通过给出其规范名称来导入单个类型，使其在它所属的编译单元的模块、类和接口声明中以简单名称可用。

```
SingleTypeImportDeclaration:
import TypeName;
```

`TypeName` 必须是类类型、接口类型、枚举类型或注解类型的规范名称（§6.7）。

该类型必须是命名包的成员，或者是一个其最外层词法闭包类型声明（§8.1.3）为命名包成员的类型的成员，否则将发生编译时错误。

如果该类型不可访问（§6.6），则发生编译时错误。

如果同一个编译单元中的两个单类型导入声明尝试导入具有相同名称的类型，则发生编译时错误，除非这两个类型是相同类型，在这种情况下重复声明将被忽略。

如果单类型导入声明导入的类型在包含该导入声明的编译单元中声明，则该导入声明被忽略。

如果单类型导入声明导入一个简单名称为 n 的类型，且该编译单元还声明了一个简单名称为 n 的顶层类型，则发生编译时错误。

如果一个编译单元同时包含一个导入简单名称为 n 的类型的单类型导入声明，以及一个导入简单名称为 n 的类型的单项静态导入声明 (§7.5.3)，则发生编译时错误，除非这两个类型是相同类型，在这种情况下，重复声明将被忽略。

#### 示例 7.5.1-1 单类型导入

```
import java.util.Vector;
```

导致简单名称 `Vector` 在编译单元的类和接口声明中可用。因此，在所有未被字段、参数、局部变量或具有相同名称的嵌套声明的遮蔽（§6.4.1）或模糊（§6.4.2）的地方，名称 `Vector` 指向包 `java.util` 中的类型声明 `Vector`。

注意 `java.util.Vector` 的实际声明是泛型的（§8.1.2）。一旦导入，名称 `Vector` 可以在参数化类型（如 `Vector<String>`）中无限定使用，或者作为原始类型 `Vector` 使用。导入声明的相关限制是，泛类型声明内部的嵌套类型可以被导入，但其外部类型会被擦除。

#### 示例 7.5.1-2 重复类型声明

此程序：

```
import java.util.Vector;
class Vector { Object[] vec; }
```

由于 `Vector` 的重复声明会导致编译时错误，如下：

```
import java.util.Vector;
import myVector.Vector;
```

其中 `myVector` 是一个包含以下内容的编译单元：

```
package myVector;
public class Vector { Object[] vec; }
```

#### 示例 7.5.1-3 导入子包

注意导入声明不能导入子包，只能导入类型。例如，尝试导入 `java.util` 是不通的：

```
import java.util;
class Test { Random; }
```

#### 示例 7.5.1-4 导入与包相同的类型

包名和类型名通常是不同的。然而，在一个异常的示例中，有一个名为 `Vector` 的包，它声明了公共类 `Mosquito`：

```
package Vector;
```

然后是该编译单元：

```
package strange;
import Vector.*;
class Test {
    System.out.println(new Mosquito());
}
```

### 7.5.2 按需类型导入

按需类型导入声明通过提及一个类型或包的规范名称，按需要导入命名类型或命名包的所有可访问类型。

```
TypeImportOnDemandDeclaration:
import PackageOrTypeName *
```

`PackageOrTypeName` 必须是包、类类型、接口类型或注解类型的规范名称（§6.7）。

如果 `PackageOrTypeName` 表示一个类型，它必须是命名包的成员，或者是一个其最外层词法闭包类型声明（§8.1.3）为命名包成员的类型，否则该包对当前模块唯一可见（§7.4）或类型不可访问（§6.6），将发生编译错误。

在按需类型导入声明中命名 `java.lang` 或当前编译单元的命名包不是编译时错误。在这种情况下，按需类型导入声明被忽略。

同一个编译单元中的两个或多个按需类型导入声明可以命名相同的类型或包。这些声明之外的所有声明都是冗余的；其效果是该类型只被导入一次。

如果一个编译单元同时包含一个命名相同类型的按需类型导入声明和一个按需静态导入声明 (§7.5.4)，其效果是该类型的静态成员只被导入一次。

#### 示例 7.5.2-1 按需类型导入

```
import java.util.*;
```

导致 `java.util` 包中声明的所有公共类型在编译单元的类和接口声明中可用。因此，在编译单元中所有该声明未被遮蔽（§6.4.1）或模糊（§6.4.2）的地方，简单名称 `Vector` 指向包 `java.util` 中的类型 `Vector`。

该声明可能被简单名称为 `Vector` 的单类型导入声明遮蔽；被在编译单元所属包中声明的名为 `Vector` 的类型遮蔽；或任何嵌套类或接口遮蔽。

该声明可能被名为 `Vector` 的字段、参数或局部变量的声明所模糊。

（这些情况的任何一种发生都是不常的。）

### 7.5.3 单项静态导入声明

单项静态导入声明从一个类型中导入具有给定名称的所有可访问静态成员。这使得静态成员在单项静态导入声明所在的编译单元的模块、类和接口声明中以其简单名称可用。

```
SingleStaticImportDeclaration:
import static TypeName . Identifier;
```

`TypeName` 必须是类类型、接口类型、枚举类型或注解类型的规范名称（§6.7）。

该类型必须是命名包的成员，或者是一个类型的成员，且该类型最外层词法包含的类型声明 (§8.1.3) 是命名包的成员，否则将发生编译错误。

如果该命名的类型不可访问 (§6.6)，则会发生编译错误。

标识符（`Identifier`）必须命名该命名类型中的至少一个静态成员。如果没有该名称的静态成员，或者所有被命名的成员均不可访问，则会发生编译错误。

一个单静态导入（single-static-import）声明允许导入多个具有相同名称的字段或类型，或者具有相同名称和签名的方法。这发生在命名类型从其超类中继承了多个字段、成员类型或方法，且这些成员的名称均相同时的情况。

如果在同一次编译尝试中，两个单静态导入声明尝试导入相同简单名的类型，则会发生编译错误，除非两者是同一种类型，在这种情况下，重复的声明将被忽略。

如果一个单静态导入声明导入了一个简单名为 $n$ 的类型，而该编译单元也声明了一个简单名为 $n$ 的顶层类型 (§7.6)，则会发生编译错误。

如果一个编译单元同时包含一个导入简单名为 $n$ 的类型的单静态导入声明，以及一个导入简单名为 $n$ 的类型的单类型导入声明 (§7.5.1)，则会发生编译错误，除非这两个类型是同一种类型，在这种情况下，重复的声明将被忽略。

### 7.5.4 按需静态导入声明

按需静态导入允许根据需要导入命名类型的所有可访问静态成员。

```
StaticImportOnDemandDeclaration:
import static TypeName. *;
```

`TypeName` 必须是类类型、接口类型、枚举类型或注解类型的规范名 (§6.7)。

该类型必须是命名包的成员，或者是一个类型的成员，且该类型最外层词法包含的类型声明 (§8.1.3) 是命名包的成员，否则将发生编译错误。

如果该命名的类型不可访问 (§6.6)，则会发生编译错误。

在同一个编译单元中的两个或多个按需静态导入声明可以命名相同的类型；其效果等同于仅存在一个这样的声明。

在同一个编译单元中的两个或多个按需静态导入声明可以命名相同的成员；其效果等同于该成员被仅导入了一次。

一个按需静态导入声明允许导入多个具有相同名称的字段或类型、多个具有相同名称和签名的方法。这发生在命名类型从其超类中继承了多个字段、成员类型或方法，且这些成员的名称均相同时的情况。

如果一个编译单元同时包含一个命名相同类型的按需静态导入声明和一个命名相同类型的按需类型导入声明 (§7.5.2)，其效果等同于该类型的静态成员类型 (§8.5, §9.5) 仅导入了一次。

## 7.6 顶层类型声明

顶层类型声明声明一个顶层类型 (§8 (类)) 或一个顶层接口类型 (§9 (接口))。

```
TypeDeclaration:
ClassDeclaration
;
```

在编译单元中，类型声明层级出现的额外 `";"` 标记对编译单元的含义没有影响。Java 语言允许零散的分号，完全是为了顾及 C++ 程序员，他们习惯在类声明后放置 `";"`。它们不应在 Java 代码中使用。

在没有访问修饰符的情况下，顶层类型具有包级访问权限：它仅在声明所在的包的普通编译单元内可访问 (§6.6.1)。一个类型可以声明为 `public`，以允许来自同一模块其他包的代码（并可能来自其他模块的代码）访问该类型。

如果顶层类型声明包含以下任何访问修饰符：`protected`、`private` 或 `static`，则会发生编译错误。

如果顶层类型的名称出现在同一包声明的任何其他顶层类或接口类型中，则会发生编译错误。

顶层类型的作用域和隐藏在 §6.3 和 §6.4 中规定。

顶层类型的全限定名在 §6.7 中规定。

#### 示例 7.6-1 冲突的顶层声明

```
package test;
import java.util.Vector;
class Point {
    int x, y;
}
interface Point { // 编译错误 #1
    int getR();
    int getTheta();
}
class Vector { Point[] pts; } // 编译错误 #2
```

在这里，第一个编译错误是由在同一个包中将名称 `Point` 同时声明为类和接口的重复声明引起的。第二个编译错误是尝试将名称 `Vector` 同时声明为类声明和通过单类型导入。

然而，请注意，类也可能命名一个在包含该类声明的编译单元 (§7.3) 中可能通过声明类型导入 (§7.5.2) 导入的类型，这并不是错误。因此，在以下程序中：

```
package test;
import java.util.*;
class Vector { // 不是编译错误
```

即使存在一个类 `java.util.Vector`，类 `Vector` 的声明也是被允许的。在该编译单元内，简单名 `Vector` 指的是类 `Vector`，而不是 `java.util.Vector`（后者仍然可以被引用）。

#### 示例 7.6-2 顶层类型的作用域

```
package points;
class Point {
    int x, y; // 坐标
    PointColor color; // 此点的颜色
    Point next; // 这种颜色的点
    static int nPoints; // 这种颜色数量
}
class PointColor {
    Point first; // 这种颜色的点
    PointColor(int color) { this.color = color; }
    private int color; // 颜色组件
}
```

此程序定义了两个在成员声明中互相使用的类。由于 `Point` 和 `PointColor` 拥有 `points` 包内的所有类型声明（包括当前编译单元内的），因此该程序可以正确编译。也就是说，前向引用不是问题。

#### 示例 7.6-3 全限定名

```
class Point { int x, y; }
```

在此段代码中，类 `Point` 定义在一个没有包声明的编译单元中，因此 `Point` 是它的全限定名；而在：

```
package vista;
class Point { int x, y; }
```

其中 `Point` 类的全限定名是 `vista.Point`。（包名 `vista` 适用于本地或个人使用；如果该包旨在广泛分发，最好给它一个唯一的包名 (§6.1)）



Java SE 平台的实现必须通过其封闭包名和二进制名（§13.1）来跟踪包内的类型。命名类型的多种方式必须扩展为二进制名，以确保这些名称被理解为指向同一个类型。

例如，如果一个编译单元包含单类型导入声明（§7.5）：

```
import java.util.Vector;
```

那么在该编译单元中，简单名 `Vector` 和全限定名 `java.util.Vector` 指向同一个类型。

且仅当包存储在文件系统中（§7.2）时，主机系统必须强制执行限制：如果满足任一条件，但在以类型名加扩展名（如 `.java` 或 `.class`）命名的文件中未找到类型，则产生编译错误：

- 该类型被声明所在包的任何普通编译单元引用。
- 该类型被声明为 `public`（因此可能从其他包的代码访问）。

这一限制意味着每个编译单元最多只能有一个类型。这一限制使得 Java 编译器能够在一个包内查找命名类。在实践中，许多程序员选择将每个类或接口类型放在单独的编译单元中，无论它是否为 `public` 或是否被其他编译单元引用。

例如，公共类型 `wet.sprocket.Toad` 的源代码可以在 `wet/sprocket` 目录下的 `Toad.java` 文件找到，而对应的对象代码将位于相同目录下的 `Toad.class` 文件。

## 7.7 模块声明

模块声明指定了一个新的命名模块。命名模块指定了对其他模块的依赖关系，以定义其自身代码可用的类和接口范围；并指定了它的哪些包被导出或打开，以填充其他指定对它有依赖的模块的可用的类和接口范围。

> “依赖”是由 `requires` 指令所表达的内容，与是否存在一个以指令指定的命名模块无关。“依赖”是指对于每个 `requires` 指令通过解析（如 `java.lang.module` 包规范中所述的）列出的可观测模块。通常情况下，Java 编程语言的规则对依赖的关注程度高于声明。

```
ModuleDeclaration:
[Annotation] [open] module Identifier {
    {ModuleDirective}
}
```

模块声明引入了一个模块名称，该名称可以在其他模块声明中使用以表示模块之间的关系。模块名称由一个或多个 Java 标识符（§3.8）由 `.` 标记分隔组成。

模块有两种类型：普通模块和开放模块。模块类型决定了模块外部代码对该模块类型及其类型成员的访问性质。

不带 `open` 修饰符的普通模块，仅在编译时和运行时授予对那些显式导出的包中类型的访问权限。

带有 `open` 修饰符的开放模块，在编译时仅授予对显式导出的包中类型的访问权限，但在运行时授予对其所有包中类型的访问权限，就像所有包都已导出一样。

对于模块外部的代码（无论模块是普通的还是开放的），在编译时或运行时授予模块导出包中类型的访问权限，专门针对这些包中的 `public` 和 `protected` 类型，以及这些类型的 `public` 和 `protected` 成员（§6.6）。对于未导出的包中的类型或其成员，在编译时或运行时均不授予访问权限。模块内部的代码可以在编译和运行时访问模块内所有包中的 `public` 和 `protected` 类型，以及这些类型的 `public` 和 `protected` 成员。

与编译时访问和运行时访问不同，Java SE 平台通过核心反射 API（§1.4）提供对类型的反射性访问。普通模块仅对那些显式导出或显式打开（或两者兼有）的包中的类型授予反射性访问。如果所有包都已打开，则开放模块对其所有包中的类型授予反射性访问。

对于普通模块外部的代码，授予模块已导出（且未打开）的包中类型的反射性访问，专门针对这些包中的 `public` 和 `protected` 类型，以及这些类型的 `public` 和 `protected` 成员。授予模块已打开的包中类型（无论是否导出）的反射性访问，针对这些包中的所有类型以及这些类型的所有成员。对于未导出或未打开的包中的类型或其成员，不授予反射性访问。模块内部的代码享有模块内所有包中所有类型及其所有成员的反射性访问。

对于开放模块外部的代码，授予模块已打开的包（即模块中的所有包）中类型的反射性访问，针对这些包中的所有类型以及这些类型的所有成员。模块内部的代码享有模块内所有包中所有类型及其所有成员的反射性访问。

> 模块声明的指令指定了模块对其他模块的依赖（通过 `requires`，§7.7.1）、它向其他模块提供的可用包（通过 `exports` 和 `opens`，§7.7.2）、它消耗的服务（通过 `uses`，§7.7.3）以及它提供的服务（通过 `provides`，§7.7.4）。

```
ModuleDirective:
requires [Modifier] ModuleName;
exports PackageName [to ModuleName [, ModuleName]];
opens PackageName [to ModuleName [, ModuleName]];
uses TypeName;
provides TypeName with TypeName (, TypeName);
```

```
RequiresModifier:
(one of)
transitive static
```

当且仅当包存储在文件系统中（§7.2）时，宿主系统可以选择强制执行限制：如果在一个由 `module-info` 加上扩展名（如 `.java` 或 `.class`）组成的命名的文件中未找到模块声明，则这是一个编译时错误。

为了便于理解，习惯上（但并非强制）模块声明会将指令分组，使得与模块相关的 `requires` 指令在视觉上区别与包相关的 `exports` 和 `opens` 指令，以及与服务相关的 `uses` 和 `provides` 指令。例如：

```java
module com.example.foo {
    requires com.example.foo.http;
    requires java.logging;

    exports com.example.foo.bar;
    exports com.example.foo.internal to com.example.foo.probe;

    opens com.example.foo.quux;
    opens com.example.foo.internal to com.example.foo.network,
        com.example.foo.probe;

    uses com.example.spi.Intf;
    provides com.example.spi.Intf with com.example.foo.Impl;
}
```

`opens` 依赖可以在开放模块中修改：

```java
open module com.example.foo {
    requires com.example.foo.http;
    requires java.logging;

    requires transitive com.example.foo.network;

    exports com.example.foo.bar;
    exports com.example.foo.internal to com.example.foo.probe;

    opens com.example.foo.quux;
    opens com.example.foo.internal to com.example.foo.network,
        com.example.foo.probe;

    uses com.example.spi.Intf;
    provides com.example.spi.Intf with com.example.foo.Impl;
}
```

开发工具被鼓励高亮 `transitive` 依赖以及未限定的 `exports` 指令，因为这些是模块的主要 API。

## 7.7.1 依赖

`requires` 指令指定当前模块所依赖的模块名称。

`requires` 指令不能出现在 `java.base` 模块的声明中，否则会发生编译时错误，因为它是原始模块且没有依赖（§8.1）。

如果模块声明没有对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，则它对 `java.base` 有隐式依赖。

`requires` 关键字后面可以跟 `transitive` 修饰符，这要求当前模块对 `requires` 指令所指定的模块具有隐式依赖。

`requires` 关键字后面可以跟 `static` 修饰符。这表示该依赖在编译时是强制的，但在运行时是可选的。

如果模块声明对 `java.base` 模块有依赖，且该模块本身不是 `java.base`，则在 `requires` 关键字后出现修饰符是一个编译时错误。

如果模块声明中的多个指令指定了相同的模块名称，则这是一个编译时错误。

如果如 `java.lang.module` 包规范所述的解析（以当前模块为唯一根模块）由于该规范中描述的任何原因而失败，则存在编译时错误。

例如，如果 `requires` 指令指定的模块是不可观测的，或者当前模块直接或间接地表示依赖于自身。

如果解析成功，则其结果指定了当前模块读取的模块。当前模块读取的模块决定了哪些编译单元对当前模块是可见的（§7.3）。这些编译单元中声明的类型（仅限这些单元）可以被当前模块访问（§6.6）。

Java SE 平台区分显式声明的命名模块（即带有模块声明的模块）和隐式声明的命名模块（即自动模块）。然而，Java 编程语言并没有体现这种区别：`requires` 引用命名模块时不考虑它们是显式声明还是隐式声明。

虽然自动模块对于迁移很方便，但它们是不可靠的，因为当作者将其转换为显式声明模块时，它们的名称和导出的包可能会发生变化。当 `requires` 指令引用自动模块时，Java 编译器鼓励发出警告。如果指令中出现了 `transitive` 修饰符，建议发出特别强烈的警告。

### 示例 7.1.1-1. requires transitive 指令的解析

假设有四个模块声明如下：

```java
module m.A {
    requires m.B;
}
```

```java
module m.B {
    requires transitive m.C;
}
```

```java
module m.C {
    requires transitive m.D;
}
```

```java
module m.D {
    exports p;
}
```

其中 m.D 导出的包 p 声明如下：

并且模块 m.A 中的包 client 引用导出的包 p 中的公共类型 Point 时：

```java
package client;
import p.Point;
public class Test {
    public static void main(String[] args) {
        System.out.println(new Point());
    }
}
```

模块可以按以下方式编译，假设当前目录包含每个模块一个子目录，该名称与其包含的模块相同：

```bash
javac --module-source-path -d . --module m.D
javac --module-source-path -d . --module m.C
javac --module-source-path -d . --module m.B
javac --module-source-path -d . --module m.A
```

程序 client.Test 可以按以下方式运行：

```bash
java --module-path --module m.A/client.Test
```

从 m.A 代码到 m.D 中导出的公共类型 Point 的引用是合法的，因为 m.A 读取了 m.D，而 m.D 导出了包含 Point 的包。解析确定 m.A 读取 m.D 的方式如下：

- m.A 需要 m.B，因此读取 m.B。
- 由于 m.A 读取 m.B，且由于 m.B 需要传递 m.C，解析确定 m.A 读取了 m.C。
- 那么，由于 m.A 读取 m.C，且由于 m.C 需要传递 m.D，解析确定 m.A 读取了 m.D。

实际上，一个模块可以通过多层依赖读取另一个模块，以支持任意数量的重构。一个模块被发布以供他人重用（通过 `requires`），该模块作者已提交了其名称和 API，并可以自由地将其内容重构到其他模块，由原始模块（通过 `requires transitive`）为重用以供消费者。在上面的示例中，包 p 可能由 m.B 导出（因此，m.A 需要 m.B），但重构导致 m.B 的部分内容移动到了 m.C 和 m.D。通过使用传递指令链，m.B、m.C 和 m.D 族组可以保留 m.A 中代码对包 p 的访问，而无需更改 m.A 的 `requires` 指令。注意，m.D 中的包 p 并没有被 m.C 和 m.B “重新导出”；相反，是让 m.A 直接读取 m.D。

## 7.7.2 导出的包和开放包

`exports` 指令定义了当前模块要导出的包名。对于其他模块中的代码，这在编译时和运行时授予了对包中公共和受保护类型以及这些类型的公共和受保护成员的访问。它还授予了其他模块代码对这些类型和成员的反射访问。

`opens` 指令定义了当前模块开放的包名。对于其他模块中的代码，这在运行时（而非编译时）授予了对包中公共和受保护类型以及这些类型的公共和受保护成员的访问。它还授予了其他模块代码对包中所有类型和所有成员的反射访问。

如果由 `exports` 指定的包未由当前模块关联的编译单元声明（§7.3），这是一个编译时错误。

允许 `opens` 指定一个未由当前模块关联的编译单元声明的包。（如果该包恰好被声明在与另一个模块关联的可观测编译单元中，则该 `opens` 指令对该模块没有影响。）

如果模块声明中存在多个 `exports` 指令指定相同的包名，则为编译时错误。

如果模块声明中存在多个 `opens` 指令指定相同的包名，则为编译时错误。

如果在开放模块的声明中出现 `opens` 指令，则为编译时错误。

如果 `exports` 或 `opens` 指令带有 `to` 子句，则该指令是限定的；否则，是非限定的。对于限定指令，包中的公共和受保护类型以及它们的公共和受保护成员仅对 `to` 子句中指定的模块中的代码可见。`to` 子句中指定的模块被称为当前模块的“友元”。对于非限定指令，这些类型及其成员对任何模块中的代码可见。

允许 `exports` 或 `opens` 指令的 `to` 子句指定一个不可观测的模块（§7.7.6）。

如果给定的 `exports` 指令的 `to` 子句多次指定相同的模块名，则为编译时错误。

如果给定的 `opens` 指令的 `to` 子句多次指定相同的模块名，则为编译时错误。

## 7.7.3 服务消费

`uses` 指令指定当前模块可以通过 `java.util.ServiceLoader` 提供者的服务。

服务必须是类类型、接口类型或注解类型。如果 `uses` 指令指定枚举类型（§8.9）作为服务，则为编译时错误。

服务可以声明在当前模块中或另一个模块中。如果服务未在当前模块中声明，则该服务必须对当前模块代码可见。如果模块声明中存在多个 `uses` 指令指定同一个服务，则为编译时错误。

## 7.7.4 服务提供

`provides` 指令指定一个服务，`with` 子句指定一个或多个提供者给 `java.util.ServiceLoader`。

服务必须是类类型、接口类型或注解类型。如果 `provides` 指令指定枚举类型（§8.9）作为服务，则为编译时错误。

服务可以声明在当前模块中或另一个模块中。如果服务未在当前模块中声明，则该服务必须对当前模块代码可见（§6.6）。

每个提供者必须是类类型或接口类型，且是公共且顶层或嵌套静态的，否则为编译时错误。每个提供者必须在当前模块中声明，否则为编译时错误。

如果提供者显式声明了无参数的公共构造函数，或隐式声明了公共默认构造函数（§8.8.9），则该构造函数称为提供构造函数。

如果提供者显式声明了无参数的公共静态方法 `provider`，则方法称为提供方法。

如果提供者具有提供方法，则其返回值（i）要在当前模块中声明，要么在另一个模块中且（ii）是 `provides` 指令所指定服务的子类型；否则为编译时错误。

> 虽然由 `provides` 指令指定的提供者必须在当前模块中声明，但其提供方法的返回值可能在另一个模块中声明。此外，当提供者声明了提供方法时，提供者并不需要是服务的子类型。

如果提供者没有提供方法，则该提供者必须具有提供构造函数是 `provides` 指令指定服务的子类型，否则为编译时错误。

如果模块声明中存在多个 `provides` 指令指定同一个服务，则为编译时错误。如果给定的 `provides` 指令的 `with` 子句多次指定相同的提供者，则为编译时错误。

## 7.7.5 匿名模块

主机系统未与命名模块关联的可观测编译单元（§7.3）与一个匿名模块关联。

Java 平台提供匿名模块是为了考虑到 Java 9 之前的程序无法声明命名模块。此外，Java 平台提供匿名包（§7.4.2）的原因在很大程度上适用于匿名模块。

Java 平台的实现必须支持至少一个匿名模块。实现可以支持多个匿名模块，但不需要这样做。每个未命名模块关联了哪些普通编译单元由宿主系统决定。

宿主系统可能会将命名包中的普通编译单元与一个未命名模块关联。

未命名模块的规则旨在最大化其与命名模块的互操作性，如下：

- 未命名模块读取每个可观测模块（§7.7.6）。



由于与未命名模块关联的普通编译单元是可观测的，因此关联的未命名模块也是可观测的。因此，如果 Java SE 平台支持多个模块，则每个未命名模块都是可观测的；每个未命名模块读取包括自身在内的每个未命名模块。

然而，重要的是，未命名模块的编译单元对命名模块来说永远是不可见的（§3），因为没有 `requires` 指令可以安排命名模块读取未命名模块。Java SE 平台的核心反射 API 可用于在运行时安排命名模块读取未命名模块。

- 未命名模块导出每一个其普通编译单元与该未命名模块关联的包。
- 未命名模块打开每一个其普通编译单元与该未命名模块关联的包。

## 7.7.6 模块观测性

如果至少有一个以下条件成立，则模块是可观测的：

- 包含该模块声明的模块化编译单元是可观测的（§7.3）。
- 与该模块关联的普通编译单元是可观测的。

## 8 章

### 类

类声明定义了新的引用类型并描述了它们如何被实现（§8.1）。

顶层类是一个不是嵌套类的类。

嵌套类是任何声明发生在另一个类或嵌套类体内的类。

本章讨论了所有类的通用语义——顶层（§7.6）和嵌套类（§8.5, §9.5）、局部类（§14.3）以及匿名类（§15.9.5）。针对特定类型类的具体细节将在专门针对这些构造的节中讨论。

命名类可以被声明为 `abstract`（抽象）（§8.1.1），并且如果它被完全实现，则必须被声明为 `abstract`；此类类不能被实例化，但可以被子类扩展。类可以被声明为 `final`（§8.1.2），在这种情况下它不能有子类。如果一个类被声明为 `public`，则它可以从其模块中任何包的代码被引用，并可能从其他模块引用。除了 `Object` 之外，每个类都是一个单一现有类的扩展（即该类的子类）（§8.1.4），并可以实现接口（§8.1.5）。类可以是泛型的，并在该类的不同实例之间有所变化。

类可以像任何其他类型的声明一样被注解（§9.7）装饰。

类的体声明了成员（字段和方法，以及嵌套类和接口）、实例和静态初始化器，以及构造函数（§8.1.6）。成员（§8.2）的范围（§6.3）是成员所属的类的整个体。字段、方法、成员类、成员接口和构造函数的声明可以包括访问修饰符（§6.6）`public`、`protected` 或 `private`。类的成员包括声明的成员和继承的成员（§8.2）。新声明的字段可以隐藏在超类或超接口中声明的字段。新声明的类成员和接口成员可以隐藏在超类或超接口中声明的类或接口成员。新声明的方法可以隐藏、实现或覆盖在超类或超接口中声明的方法。

字段声明（§8.3）描述了类变量（它们只被实例化一次）和实例变量（它们为类的每个实例都新地实例化）。字段可以被声明为 `final`（§8.3.1,2），在这种情况下它只能被赋值一次。任何字段声明都可以包含一个初始化器。

成员类声明（§8.5）描述了作为周围类成员的嵌套类。成员类可以是 `static` 的，在这种情况下它们没有访问周围类实例变量的权限；或者它们可以是内部类（§8.1.3）。

成员接口声明（§8.5）描述了作为周围类成员的嵌套接口。

方法声明（§8.4）描述了可以被方法调用表达式（§15.12）调用的代码。类方法相对于类类型被调用；实例方法相对于某个作为类类型实例的某个特定对象被调用。如果方法声明不指示其如何实现，则必须被声明为 `abstract`。方法可以被声明为 `final`（§8.4.3.3），在这种情况下它不能被隐藏或覆盖。方法可以由依赖平台的原生代码实现（§8.4.3.4）。同步方法（§8.4.3.6）在执行其体之前自动锁定对象，并在返回时自动解锁对象，仿佛使用了 `synchronized` 语句（§14.19），允许其活动与其他线程的活动保持同步（第 17 章 线程与锁）。

方法名可以被重载（§8.4.9）。

实例初始化器（§8.6）是可执行的代码块，可以用于在创建实例时（§15.9）初始化一个实例。

静态初始化器（§8.7）是可执行的代码块，可以用于初始化一个类。

构造函数（§8.8）与方法类似，但不能通过方法调用直接调用；它们用于初始化新的类实例。像方法一样，它们可以被重载（§8.8.8）。

## 8.1 类声明

类声明指定了一个新的引用类型。类声明有两种类型：普通类声明和枚举声明。

```
ClassDeclaration:
NormalClassDeclaration
EnumDeclaration
```

```
NormalClassDeclaration:
[ClassModifier] class TypeIdentifier [TypeParameters] [Superclass][SuperInterfaces] ClassBody
```

```
EnumDeclaration:
[ClassModifier] enum TypeIdentifier [TypeParameters] [Superclass][SuperInterfaces] ClassBody
```

本节中的规则适用于所有类声明，包括枚举声明。然而，关于修饰符，枚举声明有特殊的规则。类声明中的 `TypeIdentifier` 指定了类的名称。如果一个类与它的任何一个超类同名，则为编译错误。类声明的范围和遮蔽在 §6.3 和 §6.4 中指定。

### 8.1.1 类修饰符

类声明可以包括类修饰符。

```
ClassModifier:
(one of) public protected private
abstract static final
```

类声明上注解修饰符的规则在 §9.7 中指定。访问修饰符 `public`（§6.6）仅适用于顶层类（§7.6）和成员类（§8.5），而不适用于局部类（§14.3）或匿名类（§15.9）。访问修饰符 `protected` 和 `private` 仅适用于直接包含它的类声明内部的成员类（§8.5）。修饰符 `static` 仅适用于成员类（§8.5.1），而不适用于顶层类或匿名类。如果同一个关键字作为类声明的修饰符出现多次，则为编译错误，或者如果类声明有多个访问修饰符 `public`、`protected` 和 `private`（§6.6）。如果两个或多个（不同的）类修饰符出现在类声明中，按照惯例，它们按照上述 `ClassModifier` 所示的顺序出现。

### 8.1.1.1 抽象类

抽象类是不完整的类，或者被认为是不完整的类。如果尝试使用类表达式（§15.9.1）创建抽象类的实例，则为编译错误。一个不是抽象的抽象类子类可以被实例化，这将导致抽象类构造函数的执行，因此导致该类实例变量初始化器的执行。

普通类可以有抽象方法（即未实现的方法（§8.4.3）），但前提是它是一个抽象类。如果一个普通类不是抽象的却有一个抽象方法，则为编译错误。

如果以下任一条件成立，则类 `c` 有抽象方法：

- `c` 的任何成员方法（§8.2）无论是声明的还是继承的——是抽象的。
- `c` 的任何子类有一个声明为包访问权限的抽象方法，且不存在覆盖 `c` 或 `c` 的超类的抽象方法的方法。

如果声明一个抽象类类型以至于无法创建一个实现其所有抽象方法的子类，则为编译错误。这种情况可能发生在该类拥有两个具有相同方法签名（§8.4.2）但其返回类型没有一种类型可以同时与两者替换的成员方法（§8.4.5）。

### 示例 8.1.1.1-1. 抽象类声明

```
abstract class Point {
    int x = 1, y = 1;
    void move(int dx, int dy) {
        x += dx; y += dy;
        alert();
    }
    abstract void alert();
}
abstract class ColoredPoint extends Point {
    int color;
}
class SimplePoint extends Point {
    void alert() { }
}
```

在这里，声明了一个名为 `Point` 的类，它必须被声明为抽象类，因为它包含了一个名为 `alert` 的抽象方法的声明。`Point` 的名为 `ColoredPoint` 的子类继承了抽象方法 `alert`，因此它也必须声明为抽象类。另一方面，`Point` 的名为 `SimplePoint` 的子类提供了 `alert` 的实现，因此它不需要声明为抽象类。

语句：

```
Point p = new Point();
```

将导致编译错误；类 `Point` 不能被实例化，因为它是抽象的。`Point` 类型的变量可以通过对任何 `Point` 的子类的引用来正确地初始化，而由于 `SimplePoint` 类不是抽象的，因此语句：

```
Point p = new SimplePoint();
```

是正确的。实例化 `SimplePoint` 会导致 `Point` 类的默认构造函数以及字段 `x` 和 `y` 的初始化器被执行。

### 示例 8.1.1.1-2. 抽象声明禁止子类

```
interface Colorable {
    void setColor(int color);
}
abstract class Colored implements Colorable {
    public abstract int setColor(int color);
}
```

这些声明会导致编译错误；`Colored` 的任何子类都不可能提供一个接受一个 `int` 类型参数的名为 `setColor` 方法的实现来同时满足两个抽象方法的规范，因为 `Colorable` 中的要求该方法返回 `void`，而 `Colored` 中的要求相同的方法返回一个 `int` 类型的值（§8.4）。

只有当意图是允许声明子类来完成实现时，才将一个类型声明为抽象类型。如果意图是防止类的实例化，正确的表达方式是声明一个无参数构造函数（§8.10），将其设为私有，永远不调用它，并且不声明其他构造函数。这种形式的类通常包含类方法和变量。

`Math` 类是一个无法实例化的类示例；它的声明看起来如下：

```
public final class Math {
    private Math() { // 永远不要实例化此类
    }
    ... 类变量和方法的声明 . . .
}
```

### 8.1.1.2 final 类

如果一个类的定义是完整的且不需要或不子类，则可以将该类声明为 `final`。

如果 `final` 类名出现在另一个类声明的 `extends` 子句（§8.1.4）中，则会导致编译错误；这意味着 `final` 类不能有任何子类。

如果一个类既是 `final` 的又是 `abstract` 的，则会导致编译错误，因为此类类的实现永远无法完成（§8.1.1.1）。

由于 `final` 类永远没有子类，因此 `final` 类的方法永远不会被重写（§8.4.8.1）。

### 8.1.1.3 strictfp

`strictfp` 修饰符的作用是使类声明中的所有 `float` 或 `double` 表达式（包括变量初始化器、实例初始化器、静态初始化器和构造函数）显式地符合 FP-strict（§15.4）。

这意味着类中声明的所有方法以及在类中声明的所有嵌套类型都是隐式 `strictfp` 的。

### 8.1.2 泛型类和类型参数

如果一个类声明了一个或多个类型变量（§4.4），则该类是泛型的。

这些类型变量被称为类的类型参数。类型参数部分位于类名之后，并用角括号分隔。

```
TypeParameters:
  <TypeParameterList>
```

```
TypeParameterList:
  TypeParameter (, TypeParameter)*
```

为了方便起见，这里显示了 §4.4 中的以下产生式：

```
TypeParameter:
  [TypeParameterModifier] TypeIdentifier [TypeBound]

TypeParameterModifier:
  Annotation

TypeBound:
  extends TypeVariable
  extends ClassOrInterfaceType [AdditionalBound]

AdditionalBound:
  & InterfaceType
```

类型参数声明上的注解修饰符的规定在 §9.7.4 和 §9.7.5 中。

在类的类型参数部分中，如果 $s$ 是 $\tau$ 的边界，则变量 $\tau$ 直接依赖于类型变量 $s$；而如果 $\tau$ 直接依赖于 $s$ 或者 $\tau$ 依赖于依赖于 $s$ 的类型变量 $u$（递归使用此定义），则 $\tau$ 依赖于 $s$。如果类类型参数部分中的变量依赖于自身，则会导致编译错误。

类类型参数的作用域和遮蔽规定在 §6.3 和 §6.4 中。

一个泛型类声明定义了一组参数化类型（§4.5），每个类型参数部分通过类型参数每种可能的参数化方式对应一个。所有这些参数化类型在运行时共享同一个类。

例如，执行代码：

```
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致变量 `b` 持有值 `true`。

如果泛型类是直接或间接的子类（§8.1.1），则会导致编译错误；由于 Java 虚拟机只与非泛型类工作，这种限制是必要的。

### 示例 8.1.2-1. 相互递归类型边界

```
interface Colorable {
    void setColor(int color);
}
abstract class Colored implements Colorable
where S extends T [此处省略]
    public abstract int setColor(int color);
}
```

### 示例 8.1.2-2. 嵌套泛型类

```
class Seq<T> {
    T head;
    Seq<T> tail;

    Seq() {}
    Seq(T head, Seq<T> tail) {}
}

class Zipper<S> {
    Seq<T> tail;

    boolean isEmpty() { return tail == null; }
    Seq<Pair<T, S>> zip(Seq<S> s) {
        if (isEmpty()) {
            return null; // 示例性实现
        } else {
            return null; // 示例性实现
        }
    }
}

class Pair<T,S> {
    T fst; S snd;
    Pair(T f, S s) { fst = f; snd = s; }
}

class Test {
    public static void main(String[] args) {
        Seq<String> strs =
            new Seq<String>("a",
            new Seq<String>("b"));
        Seq<Number> nums =
            new Seq<Number>(new Integer(1),
            new Seq<Number>(new Double(1.5)));
        Seq<String>.Zipper<Number> zipper =
            strs.new Zipper<Number>();
        Seq<Pair<String, Number>> combined =
            zipper.zip(nums);
    }
}
```

### 8.1.3 内部类和编码

内部类是非显式或隐式声明为静态的嵌套类。

内部类可以是静态成员类（§8.5）、局部类（§14.3）或匿名类（§15.9.5）。接口的隐式静态成员类（§9.5）永远不被认为是内部类。如果内部类声明静态初始化器（§8.7），会导致编译错误。如果内部类声明显式或隐式的静态成员，会导致编译错误，除非该成员是常量变量（§4.12.4）。内部类可以继承不是常量变量的静态成员，尽管它不能声明。

不是内部类的嵌套类可以根据 Java 语言的通常规则自由声明静态成员。

### 示例 8.1.3-1. 内部类和静态成员

```
class HasStatic {
    static int j = 100;
}
class Outer {
    class Inner extends HasStatic {
        static final int x = 3; // OK: 常量变量
        static int y = 4; // 编译错误：内部类
    }
    static class NestedNotInner{
        static int z = 5; // OK: 不是内部类
    }
    interface NeverInner {} // 接口不是内部类
}
```

# 类声明

一个语句或表达式出现在静态上下文中，当且仅当包含该语句或表达式的最内层方法、构造方法、实例初始化、静态初始化、字段初始化或显式构造方法调用语句是静态方法、静态初始化、静态变量的变量初始化或显式构造方法调用语句（§8.8.7.1）。

如果 $o$ 是 $c$ 的直接包围类型声明且 $c$ 的声明没有发生在静态上下文中，则内部类 $c$ 是类或接口 $o$ 的直接内部类。

类 $c$ 是类或接口 $o$ 的内部类，如果它是 $o$ 的直接内部类，或者是 $o$ 的某个内部类的内部类。

> 内部类的直接包围类型声明是接口的情况是不寻常但可能的。这只在类被声明在默认方法的体中时发生（§9.4）。具体而言，如果在默认方法体中声明了匿名类或局部类，或者在默认方法体中的匿名类体内声明了成员类，就会发生这种情况。

类或接口 $o$ 是它自身的第 0 个词法包围类型声明。

如果 $o$ 是类 $c$ 的第 $n-1$ 个词法包围类型声明的直接包围类型声明，则 $o$ 是类 $c$ 的第 $n$ 个词法包围类型声明。



# 类或接口 $o$ 的直接内部类 $c$ 的实例 $i$ 与 $o$ 的一个实例相关

类或接口 $o$ 的直接内部类 $c$ 的实例 $i$ 与 $o$ 的一个实例相关，该实例被称为 $i$ 的直接包围实例。对象的直接包围实例（如果有）是在对象创建时确定的（§15.9.2）。

对象 $o$ 是它自身的第 0 个词法包围实例。

如果 $o$ 是实例 $i$ 的第 $n$ 个词法包围实例的直接包围实例，则 $o$ 是实例 $i$ 的第 $n+1$ 个词法包围实例。

声明发生在静态上下文中的内部类 $i$ 没有词法包围实例。然而，如果 $i$ 直接声明在静态方法或静态初始化器中，则它有一个包围块，该块是词法上包围 $i$ 声明的最内层块。

对于 $c$ 的每一个是类或接口 $so$ 的直接内部类的父类 $s$，都有一个 $so$ 的实例与 $i$ 相关，该实例被称为相对于 $s$ 的 $i$ 的直接包围实例。对象相对于其类的直接父类的包围实例（如果有）是通过显式构造方法调用语句调用父类构造方法时确定的（§8.8.7.1）。

当内部类（其声明没有发生在静态上下文中）引用作为词法包围类型声明成员的实例变量时，将使用相应词法包围实例的变量。

在内部类中使用但未声明的任何局部变量、形式参数或异常参数必须被声明为 `final` 或有效 `final`（§4.12.4），否则在尝试使用该变量的地方发生编译错误。

在内部类中使用但未声明的任何局部变量在内部类体之前一定被赋值过（§16 确定性赋值），否则会发生编译错误。

关于变量使用的类似规则也适用于 lambda 表达式体（§15.27.2）。

词法包围类型声明的空白 `final` 字段（§4.12.4）不能在内部类中赋值，否则会发生编译错误。

## 示例 8.1.3-2 内部类声明

```
class Outer {
  int i = 100;
  static void classMethod() {
    final int l = 200;
    class LocalInStaticContext {
      int k = i; // 编译错误
      int m = l; // OK
    }
  }
  void foo() {
    class Local { // 局部类
      int j = i;
    }
  }
}
```

`LocalInStaticContext` 的声明由于位于静态方法 `classMethod` 内部而发生在静态上下文中。类 `Outer` 的实例变量在静态方法体内不可用。特别是，`Outer` 的实例变量在 `LocalInStaticContext` 体内部不可用。然而，可以无错误引用周围方法的局部变量（前提它们被声明为 `final` 或有效 `final`）。

声明没有发生在静态上下文中的内部类可以引用其包围类型声明的实例变量。实例变量总是相对于某个实例定义的。对于包围类型声明的实例变量，该实例变量必须相对于该类型的某个包围实例定义。例如，上面的类 `Local` 有一个类 `Outer` 的包围实例。进一步示例如下：

```
class WithDeepNesting {
  boolean toBe;
  WithDeepNesting(boolean b) { toBe = b; }

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

在这里，每一个 `WithDeepNesting.Nested.DeeplyNested` 实例都有类 `WithDeepNesting.Nested` 的包围实例（其直接包围实例）以及一个类 `WithDeepNesting` 的包围实例（其第 2 个词法包围实例）。

# 8.1.4 父类与子类

普通类声明中可选的 `extends` 子句指定当前类的直接父类。

父类：

```
extends ClassType
```

`extends` 子句不能出现在 `Object` 类的定义中，否则会发生编译错误，因为它是原始类且没有直接父类。

`ClassType` 必须命名一个可访问的类类型（§6.6），否则会发生编译错误。

如果 `ClassType` 命名的类是 `final` 的，则会导致编译错误，因为 `final` 类不允许有子类（§8.1.1.2）。

如果 `ClassType` 命名为 `Enum` 或 `Enum` 的任何子类，会导致编译错误（§8.9）。

如果 `ClassType` 有类型参数，它必须表示一个良好的参数化类型（§4.5），且所有类型参数都不是通配符类型参数，否则会发生编译错误。

给定（可能是泛型的）类声明 $C<F1,...,Fn>$ ($n \geq 0, C \neq$ Object)，类类型 $C<F1,...,Fn>$ 的直接父类是 $C$ 声明中 `extends` 子句指定的类型（如果存在 `extends` 子句），否则是 `Object`。

给定泛型类声明 $C<F1,...,Fn>$ ($n > 0$)，参数化类类型 $C<T1,...,Tn>$ 的直接父类是 $C<F1,...,Fn>$ 的直接父类中每个类型参数 $F_i$ ($1 \leq i \leq n$) 替换为 $T_i$ 后的类型。

一个类被称为其直接父类的*直接子类*。直接父类是当前类派生自的类。

*子类*关系是直接子类关系的传递闭包。类 $A$ 是类 $C$ 的子类，如果以下条件之一为真：

- $A$ 是 $C$ 的直接子类
- 存在一个类 $B$，使得 $A$ 是 $B$ 的子类，且 $B$ 是 $C$ 的子类，递归应用此定义。

当 $A$ 是类 $C$ 的子类时，类 $C$ 被称为类 $A$ 的*父类*。

## 类依赖

- `Colored3dPoint` 类是 `Point` 类的子类。

如果类型 `T` 在类 `c` 的 `extends` 子句中作为超类或超接口被提及，或者作为超类或超接口的全限定形式中的限定符被提及，则类 `c` 直接依赖于类型 `T`。

如果满足以下任意条件，则类 `c` 依赖于引用类型 `T`：

- `c` 直接依赖 `T`。
- `c` 直接依赖接口 `T`，而 `T` 依赖于 (§9.1.3)。
- `c` 直接依赖类 `D`，而 `D` 依赖 `T`（递归使用此定义）。

如果类依赖于自身，则会导致编译错误。

如果在运行时检测到循环定义的类（在类加载时），则会抛出 `ClassCircularityError` (§12.2.1)。

### 示例 8.1.4-3. 类依赖自身

```java
class Point extends ColoredPoint { int x, y; }
class ColoredPoint extends Point { int color; }
```

此程序会导致编译错误，因为类 `Point` 依赖于自身。

## 8.1.5 超接口

类声明中可选的 `implements` 子句列出了被声明类的直接超接口的接口名称。

超接口：

```
implements InterfaceTypeList
```

InterfaceTypeList:

```
InterfaceType { , InterfaceType }
```

每个 `InterfaceType` 必须命名一个可访问的接口类型 (§6.6)，否则会发生编译错误。

如果 `InterfaceType` 具有类型参数，它必须表示一个良好的参数化类型 (§4.5)，且其中任何参数都不能是通配符类型参数，否则会发生编译错误。

如果在 `implements` 子句中多次提及同一个接口作为直接超接口，则会导致编译错误。即使该接口以不同的方式命名，此结论也是如此。

### 示例 8.1.5-1. 非法超接口

```java
class Redundant implements java.lang.Cloneable, Cloneable {
    int x;
}
```

此程序在编译时产生错误，因为 `java.lang.Cloneable` 和 `Cloneable` 名称指向的是同一个接口。

给定一个（可能是泛型的）类声明 `C<F1,...,Fn>` (n ≥ 0, C ≠ Object)，如果声明中存在 `implements` 子句，则类 `C<F1,...,Fn>` 的直接超接口是该类声明中 `implements` 子句中给出的类型。

给定一个泛型类声明 `C<F1,...,Fn>` (n > 0)，参数化类 `C<T1,...,Tn>`（其中 `Ti` (1 ≤ i ≤ n) 是一个类型）的直接超接口是所有类型 `I<U1,...,Uk>`，其中 `I<U1,...,Uk> = I_Θ` 是 `C<F1,...,Fn>` 的直接超接口，且 `Θ` 是替换项 `[F1:=T1,...,Fn:=Tn]`。

如果满足以下任意条件，则接口 `I` 是 `c`（类类型）的超接口：

- `I` 是 `c` 的直接超接口。
- `c` 具有某个直接超接口 `J`，且 `I` 是 `J` 的超接口（使用 §9.1.3 给出的“接口的超接口”定义）。
- `I` 是 `c` 的直接超类的超接口。

一个类可以通过多种方式拥有超接口。

说一个类实现了它所有的超接口。

一个类不能同时是两个不同接口类型的子类（这两个类型是同一个泛型接口的不同参数化）§9.1.2，或者同时是一个泛型接口的参数化类型与命名同一泛型接口的原始类型的子类，否则会发生编译错误。

引入这一要求是为了支持类型擦除转换 (§4.6)。

### 示例 8.1.5-2. 超接口

```java
interface Colorable {
    void setColor(int color);
    int getColor();
}
enum Finish { matte, glossy }
```

```java
interface Paintable extends Colorable {
    void setFinish(Finish finish);
}
```

```java
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
    public void setFinish(Finish finish) { this.finish = finish; }
}
```

这里的关系如下：
- `Paintable` 是 `PaintedPoint` 的超接口。
- `Colorable` 是 `PaintedPoint` 的超接口。
- `Point` 是 `ColoredPoint` 的直接超类。

`Paintable` 是 `PaintedPoint` 的超接口，且 `Colorable` 是 `PaintedPoint` 的超接口。

### 示例 8.1.5-3. 非法继承

```java
interface I<T> {}

class B implements I<Integer> {}

class C extends B implements I<String> {}
```

`C` 导致编译错误，因为它尝试实现 `I<Integer>` 和 `I<String>`。

除非类是抽象的，否则每个超接口的方法签名（§8.4）都必须通过类中的声明来实现，或者从直接超类/超接口继承。

### 示例 8.1.5-4. 实现超接口的方法

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

此程序会导致编译错误，因为 `ColoredPoint` 不是抽象类且未提供 `Colorable` 的 `setColor` 和 `getColor` 方法实现。

在以下程序中：

```java
interface Fish { int getNumberOfScales(); }
interface Piano { int getNumberOfKeys(); }

class Tuna implements Fish, Piano {
    // 你可以调钢琴，但你能调鱼吗？
    public int getNumberOfScales() { return 1; }
    public int getNumberOfKeys() { return 88; }
}
```

`Tuna` 中的方法分别实现了 `Fish` 和 `Piano` 中声明的方法。

另一方面，在如下情况下：

```java
interface Fish { int getNumberOfScales(); }
interface StringBass { double getNumberOfScales(); }

class Bass implements Fish, StringBass {
    // 无论使用什么类型，此声明都是错误的
    public int getNumberOfScales() { return 1; }
}
```

无法声明一个签名和返回类型同时兼容 `Fish` 和 `StringBass` 中声明的两个方法，因为类不能具有相同签名不同返回类型的方法（§8.4）。因此，单个类无法同时实现接口 `Fish` 和接口 `StringBass` (§8.4)。

## 8.1.6 类体与成员声明

类体可以包含类的成员声明，即字段（§8.3）、方法（§8.4）、类（§8.5）和接口（§8.5）。

类还可能包含实例初始化器（§8.6）、静态初始化器（§8.7）以及类的构造函数声明（§8.8）。

```
ClassBody:
  { ClassBodyDeclaration }

ClassBodyDeclaration:
  ClassMemberDeclaration
  InstanceInitializer
  StaticInitializer
  ConstructorDeclaration

ClassMemberDeclaration:
  FieldDeclaration
  MethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
```

类类型声明或继承的成员声明的作用域和隐藏在 §6.3 和 §6.4 中。

> 如果 c 是嵌套类，在外层作用域中可能存在相同种类（变量、方法或类型）且相同名称的定义。（作用域可以是块、类或包。）在任何情况下，在 c 中声明或继承的成员 m 都会隐藏（§6.4.1）其他定义。

# 8.2 类成员

类类型的成员包括所有以下：

- 继承自其直接超类的成员（§8.1.4），但 `Object` 类除外，因为它没有直接超类
- 继承自任何直接超接口的成员（§8.1.5）
- 在类体中声明的成员（§8.1.6）

类中声明为 `private`（私有）的成员不会被该类的子类继承。

只有声明为 `protected`（保护）或 `public`（公共）的成员才会被声明在该包之外的其他包中的子类继承。

构造方法、静态初始化器和实例初始化器不属于成员，因此不被继承。

我们使用“成员的类型”这一术语来表示：

- 对于字段（field），其类型。
- 对于方法（method），由以下内容组成的有序 4 元组：
    - 类型参数：方法成员中任何类型参数的声明。
    - 参数类型：方法成员参数的类型列表。
    - 返回类型：方法成员的返回类型。
    - `throws` 子句：在方法成员 `throws` 子句中声明的异常类型。

类类型的字段、方法和成员类型可能具有相同的名称，因为它们在不同的上下文中被使用，并通过不同的查找程序（§6.5）消除歧义。然而，从代码风格的角度来看，不建议这样做。

## 示例 8.2-1. 类成员的使用

```java
class Point {
  int x, y;
  private Point() { reset(); }
  Point(int x, int y) { this.x = x; this.y = y; }
  private void reset() { this.x = 0; this.y = 0; }
}

class ColoredPoint extends Point {
  int color;
  void clear() { reset(); } // error
}

class Test {
  public static void main(String[] args) {
    ColoredPoint c = new ColoredPoint(0, 0); // error
    c.reset(); // error
  }
}
```

此程序会导致四个编译时错误。

其中一个错误是因为 `ColoredPoint` 没有像 `main` 方法中的调用请求那样声明一个带有两个 `int` 参数的构造方法。这说明了 `ColoredPoint` 并没有继承其父类 `Point` 的构造方法。

另一个错误是因为 `ColoredPoint` 没有声明任何构造方法，因此为它隐式地声明了一个默认构造方法（§8.8.9），这个默认构造方法等同于：

```java
ColoredPoint() { super(); }
```



它调用了 `ColoredPoint` 类的直接父类的无参数构造方法。错误在于，`Point` 类中无参数的构造方法是 `private` 的，因此在 `Point` 类外部无法访问，即使是通过父类构造方法调用的（§8.8.7）。

另外两个错误是因为 `Point` 类的 `reset` 方法是 `private` 的，因此不被 `Point` 类继承。在 `ColoredPoint` 类 `clear` 方法和 `Test` 类 `main` 方法中的调用都是错误的。

# 示例 8.2-2. 具有包访问权限的类成员继承

考虑 `points` 包声明了两个编译单元的情况：

```
package points;

public class Point {

    int x, y;

    public void move(int dx, int dy) { x += dx; y += dy; }

}
```

以及：

```
package points;

public class Point3d extends Point {

    int z;

    public void move(int dx, int dy, int dz) { x += dx; y += dy; z += dz; }

}
```

而第三个位于另一个包的编译单元是：

```
import points.Point3d;

class Point4d extends Point3d {

    int w;

    public void move(int dx, int dy, int dz, int dw) { x += dx; y += dy; z += dz; w += dw; // compile-time errors }

}
```

在这里，`points` 包中的两个类都可以编译。`Point3d` 类继承了 `Point` 字段 `x` 和 `y`，因为它与 `Point` 在同一个包中。`Point4d` 类位于不同的包，它没有继承 `Point` 的字段 `x` 和 `y`，也没有继承 `Point3d` 的字段 `z`。

一个更好的编写第三个编译单元的方法：

```
import points.Point3d;

class Point4d extends Point3d {

    int w;

    public void move(int dx, int dy, int dz, int dw) { x += dx; y += dy; z += dz; }

}
```

使用父类 `Point3d` 的 `move` 方法，如果 `Point4d` 这样写，可以编译。

# 示例 8.2-3. 公共和保护成员的继承

考虑到 `Point` 类声明了如下：

```
package points;

public class Point {

    int x, y;

    protected int count = 0;

}
```

在 `points` 包中，`Test` 类继承 `Point` 并可以正常工作：

```java
package points;

class Test extends Point {

    public void increment() {

        count++;

    }

}
```

# 示例 8.2-4. 私有成员的继承

对于 `Point` 类如下：

```
class Point {

  int x, y;

  private int secret;

  void setSecret(int s) { secret = s; }

}
```

`Point3d` 尝试增加 `secret` 变量会发生错误，因为它是私有的：

```
class Point3d extends Point {

  int z;

  void setSecret(int s) {

    secret = s; // error

  }

}
```

# 示例 8.2-5. 不可访问类的成员

即使一个类不是 `public` 的，在声明它的包之外，其实也可以通过 `public` 父类或接口来访问其实例。考虑如下编译单元：

```
package points;

public class Point {

    int x, y;

    public void move(int dx, int dy) { x += dx; y += dy; }

}
```

以及另一个编译单元：

```
package morePoints;

class Point3d extends points.Point {

    int z;

    public void move(int dx, int dy, int dz) { x += dx; y += dy; z += dz; }

    public void move(int dx, int dy) { super.move(dx, dy); }

}
public class OnePoint {

    public static points.Point getOne() {

        return new Point3d();

    }

}
```

在第三个包中调用 `morePoints.OnePoint.getOne()` 会返回一个 `Point3d`，尽管 `Point3d` 类型在 `morePoints` 包之外不可用，但它可以作为 `Point` 使用。两个参数的 `move` 方法可以被该对象调用，这是允许的，因为 `Point3d` 的 `move` 方法是 `public` 的。该对象的字段 `x` 和 `y` 也可以从第三个包中访问。

## 8.3 字段声明

类类型的变量通过字段声明引入。

- FieldDeclaration: {FieldModifier} UnannType VariableDeclarList;
- VariableDeclaratorList: VariableDeclarator (, VariableDeclarator)
- VariableDeclarator: VariableDeclaratorId [= VariableInitializer]
- VariableDeclaratorId: Identifier [Dims]

### 字段声明

VariableInitializer:
- Expression
- ArrayInitializer

UnannType:
- UnannPrimitiveType
- UnannReferenceType

UnannPrimitiveType:
- NumericType
- boolean

UnannReferenceType:
- UnannClassOrInterfaceType
- UnannTypeVariable
- UnannArrayType

UnannClassOrInterfaceType:
- UnannClassType
- UnannInterfaceType

UnannClassType:
- TypeIdentifier [TypeArguments]
- PackageName . [Annotation] TypeIdentifier [TypeArguments]
- UnannClassOrInterfaceType . [Annotation] TypeIdentifier [TypeArguments]

UnannInterfaceType:
- UnannClassType

UnannTypeVariable:
- TypeIdentifier

UnannArrayType:
- UnannPrimitiveType Dims
- UnannClassOrInterfaceType Dims
- UnannTypeVariable Dims

为了方便起见，这里显示了 §4.3 中的以下产生式：

```
Dims:
[Annotation] [ ] [Annotation] [ ]
```

### 字段声明

`FieldDeclaration` 中的每个声明符声明一个字段。声明符中的 `Identifier` 可用于名称中以引用该字段。

通过使用多个声明符，可以在单个 `FieldDeclaration` 中声明多个字段；`FieldModifiers` 和 `UnannType` 应用于声明中的所有修饰符。

`FieldModifier` 子句在 §8.3.1 中有描述。

如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现方括号，则字段的声明类型用 `UnannType` 表示；否则，其声明类型由 §10.2 规定。

字段声明的作用域和隐藏在 §6.3 和 §6.4 中规定。

在类声明体中声明两个同名的字段是编译时错误。

如果类声明了一个具有特定名称的字段，则该字段的声明被认为隐藏了其超类和类超接口中所有可访问的同名字段的声明。

在另一方面，字段的隐藏与方法的隐藏（§8.4.8.3）不同，因为在字段隐藏中，不区分静态和非静态字段，而在方法隐藏中，对静态和非静态方法进行了区分。

如果被隐藏的字段是静态的，则可以使用限定名 (§6.5.6.2) 进行访问，或者通过包含关键字 `super` 的字段访问表达式 (§15.11.2) 或强制转换为超类类型来访问。

在这一方面，字段的隐藏与方法的隐藏相似。

如果一个字段声明隐藏了另一个字段的声明，则这两个字段不需要具有相同的类型。

类从其直接超类和直接超接口继承所有非私有的字段，前提是这些字段对于类中的代码是可访问的 (§6.6) 且未被类中的声明所隐藏。

超类的私有字段可能对子类是可访问的——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能继承多个同名的字段，这些可能来自其超类和超接口，也可能仅来自其接口。这种情况本身并不会导致编译时错误。然而，在类体内部任何尝试通过简单名引用此类字段的尝试都会导致编译时错误，因为该引用是歧义的。

字段声明可能通过多路径从接口继承。在这种情况下，该字段被认为只继承了一次，并且可以使用简单名进行引用而不产生歧义。

存储在 `float` 类型字段中的值始终是 `float` 值集 (§4.2.3) 的元素；同样，存储在 `double` 类型字段中的值是 `double` 值集的元素。`float` 类型字段不允许包含既属于 `float-extended-value` 值集又不属于 `float` 值集的元素，`double` 类型字段也不允许包含属于 `double-extended-value` 值集又不属于 `double` 值集的元素。

# 示例 8.3-1. 继承的字段

一个类可以从其超类和一个超接口，或从两个超接口继承两个或多个同名的字段；任何通过简单名引用任何歧义继承的字段的尝试都会导致编译时错误。可以使用使用关键字 `super` (§15.11.2) 的限定名或字段访问表达式来访问存在歧义的字段。在程序中：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

下面的变体使用字段访问表达式 `super.v` 来引用类 `SuperTest` 中声明的字段名，并使用限定名 `Frob.v` 来引用类 `Frob` 中声明的字段名：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(super.v);
    System.out.println(Frob.v);
  }
}
```



该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

# 字段声明

`FieldDeclaration` 中的每个声明符声明一个字段。声明符中的 `Identifier` 可用于名称中以引用该字段。

通过使用多个声明符，可以在单个 `FieldDeclaration` 中声明多个字段；`FieldModifiers` 和 `UnannType` 应用于声明中的所有修饰符。

`FieldModifier` 子句在 §8.3.1 中有描述。

如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现方括号，则字段的声明类型用 `UnannType` 表示；否则，其声明类型由 §10.2 规定。

字段声明的作用域和隐藏在 §6.3 和 §6.4 中规定。

在类声明体中声明两个同名的字段是编译时错误。

如果类声明了一个具有特定名称的字段，则该字段的声明被认为隐藏了其超类和类超接口中所有可访问的同名字段的声明。

在在这方面，字段的隐藏与方法的隐藏（§8.4.8.3）不同，因为在字段隐藏中，不区分静态和非静态字段，而在方法隐藏中，对静态和非静态方法进行了区分。

如果被隐藏的字段是静态的，则可以使用限定名（§6.5.6.2）进行访问，或者通过包含关键字 `super` 的字段访问表达式（§15.11.2）或强制转换为超类类型来访问。

在在这方面，字段的隐藏与方法的隐藏相似。

如果一个字段声明隐藏了另一个字段的声明，则这两个字段不需要具有相同的类型。

类从其直接超类和直接超接口继承所有非私有的字段，前提是这些字段对于类中的代码是可访问的（§6.6）且未被类中的声明所隐藏。

超类的私有字段可能对子类是可访问的——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能继承多个同名的字段，这些可能来自其超类和超接口，也可能仅来自其接口。这种情况本身并不会导致编译时错误。然而，在类体内部任何尝试通过简单名引用此类字段的尝试都会导致编译时错误，因为该引用是歧义的。

字段声明可能通过多路径从接口继承。在这种情况下，该字段被认为只继承了一次，并且可以使用简单名进行引用而不产生歧义。

存储在 `float` 类型字段中的值始终是 `float` 值集（§4.2.3）的元素；同样，存储在 `double` 类型字段中的值是 `double` 值集的元素。`float` 类型字段不允许包含既属于 `float-extended-value` 值集又不属于 `float` 值集的元素，`double` 类型字段也不允许包含属于 `double-extended-value` 值集又不属于 `double` 值集的元素。

# 示例 8.3-1. 继承的字段

一个类可以从其超类和一个超接口，或从两个超接口继承两个或多个同名的字段；任何通过简单名引用任何歧义继承的字段的尝试都会导致编译时错误。可以使用使用关键字 `super`（§15.11.2）的限定名或字段访问表达式来访问存在歧义的字段。在程序中：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

下面的变体使用字段访问表达式 `super.v` 来引用类 `SuperTest` 中声明的字段名，并使用限定名 `Frob.v` 来引用类 `Frob` 中声明的字段名：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(super.v);
    System.out.println(Frob.v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。



```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

下面的变体使用字段访问表达式 `super.v` 来引用类 `SuperTest` 中声明的字段名，并使用限定名 `Frob.v` 来引用类 `Frob` 中声明的字段名：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(super.v);
    System.out.println(Frob.v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

# 字段声明

`FieldDeclaration` 中的每个声明符声明一个字段。声明符中的 `Identifier` 可用于名称中以引用该字段。

通过使用多个声明符，可以在单个 `FieldDeclaration` 中声明多个字段；`FieldModifiers` 和 `UnannType` 应用于声明中的所有修饰符。

`FieldModifier` 子句在 §8.3.1 中有描述。

如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现方括号，则字段的声明类型用 `UnannType` 表示；否则，其声明类型由 §10.2 规定。

字段声明的作用域和隐藏在 §6.3 和 §6.4 中规定。

在类声明体中声明两个同名的字段是编译时错误。

如果类声明了一个具有特定名称的字段，则该字段的声明被认为隐藏了其超类和类超接口中所有可访问的同名字段的声明。

在另一方面，字段的隐藏与方法的隐藏（§8.4.8.3）不同，因为在字段隐藏中，不区分静态和非静态字段，而在方法隐藏中，对静态和非静态方法进行了区分。

如果被隐藏的字段是静态的，则可以使用限定名（§6.5.6.2）进行访问，或者通过包含关键字 `super` 的字段访问表达式（§15.11.2）或强制转换为超类类型来访问。

在另一方面，字段的隐藏与方法的隐藏相似。

如果一个字段声明隐藏了另一个字段的声明，则这两个字段不需要具有相同的类型。

类从其直接超类和直接超接口继承所有非私有的字段，前提是这些字段对于类中的代码是可访问的（§6.6）且未被类中的声明所隐藏。

超类的私有字段可能对子类是可访问的——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能继承多个同名的字段，这些可能来自其超类和超接口，也可能仅来自其接口。这种情况本身并不会导致编译时错误。然而，在类体内部任何尝试通过简单名引用此类字段的尝试都会导致编译时错误，因为该引用是歧义的。

字段声明可能通过多路径从接口继承。在这种情况下，该字段被认为只继承了一次，并且可以使用简单名进行引用而不产生歧义。

存储在 `float` 类型字段中的值始终是 `float` 值集（§4.2.3）的元素；同样，存储在 `double` 类型字段中的值是 `double` 值集的元素。`float` 类型字段不允许包含既属于 `float-extended-value` 值集又不属于 `float` 值集的元素，`double` 类型字段也不允许包含属于 `double-extended-value` 值集又不属于 `double` 值集的元素。

# 示例 8.3-1. 继承的字段

一个类可以从其超类和一个超接口，或从两个超接口继承两个或多个同名的字段；任何通过简单名引用任何歧义继承的字段的尝试都会导致编译时错误。可以使用使用关键字 `super`（§15.11.2）的限定名或字段访问表达式来访问存在歧义的字段。在程序中：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

下面的变体使用字段访问表达式 `super.v` 来引用类 `SuperTest` 中声明的字段名，并使用限定名 `Frob.v` 来引用类 `Frob` 中声明的字段名：

```
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
  public static void main(String[] args) {
    new Test().printV();
  }
  void printV() {
    System.out.println(super.v);
    System.out.println(Frob.v);
  }
}
```

该类继承了两个名为 `v` 的字段，一个来自其超类 `SuperTest`，另一个来自其超接口 `Frob`。这本身是允许的，但由于方法 `printV` 中的简单名 `v` 无法确定是指哪一个，导致了编译时错误。

# 字段声明

`System.out.println(q.origin.useCount);`

}

此程序输出：

```
(2,2)
0
true
1
```

这表明更改 p 的字段 `x`、`y` 和 `useCount` 不会影响 q 的字段，因为这些字段是不同对象中的实例变量。在这个例中，`Point` 类的类变量 `origin` 通过两种方式被引用：一种使用类名作为限定符（如 `Point.origin`），另一种是在字段访问中使用该类类型的变量（§15.11），如 `p.origin` 和 `q.origin`。这两种访问 `origin` 类变量的方式访问的是同一个对象，这一点可以通过引用等性表达式（§15.23）的值得到证明：

```
q.origin == Point.origin
```

为 `true`。进一步的证据是自增操作：

```
p.origin.useCount++;
```

导致 `q.origin.useCount` 的值变为 1；这是因为 `p.origin` 和 `q.origin` 指向同一个变量。

## 示例 8.3.1.1-2. 类变量的隐藏

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

此程序产生输出：

```
4.7 2
```

这是因为 `Test` 类中 `x` 的声明隐藏了 `Point` 类中 `x` 的定义，因此 `Test` 类没有从其超类 `Point` 继承字段 `x`。在 `Test` 类的声明内部，简单名称 `x` 指向在 `Test` 类内部声明的字段。`Test` 类中的代码可以通过 `super.x` 引用 `Point` 类的 `x`（或者由于 `x` 是静态的，可以使用 `Point.x`）。如果删除了 `Test.x` 的声明：

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

那么 `Point` 类的字段 `x` 再被隐藏在 `Test` 类中；相反，简单名称 `x` 指向字段 `Point.x`。`Test` 中的代码仍然可以通过 `super.x` 引用同一个字段。因此，该变体程序的输出为：

```
2
```

## 示例 8.3.1.1-3. 实例变量的隐藏

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

此程序产生输出：

```
4.7 2
4.7 2
```

这是因为 `Test` 类中 `x` 的声明隐藏了 `Point` 类中 `x` 的定义，因此 `Test` 类没有从其超类 `Point` 继承该字段。值得注意的是，虽然 `Point` 类的字段没有被 `Test` 类继承，但它仍然由 `Test` 实例实现。换句话说，每个 `Test` 类实例包含两个字段，一个 `int` 类型和一个 `double` 类型。这两个字段都同名为 `x`，但在 `Test` 类的声明内部，简单名称 `x` 指向在 `Test` 类内部声明的字段。`Test` 类实例方法中的代码可以通过 `super.x` 引用 `Point` 的实例变量 `x`。

## 类字段声明

使用字段访问表达式访问 `x` 将访问由引用表达式类型指示的类中的字段名 `x`。因此，表达式 `sample.x` 访问一个 `double` 值（即在 `Test` 类中声明的实例变量），虽然变量 `sample` 的类型是 `Test`，但表达式 `((Point)sample).x` 访问一个 `int` 值（即在 `Point` 类中声明的实例变量），因为强制转换为了 `Point` 类型。

如果从 `Test` 类中删除 `x` 的声明，如程序所示：

```java
class Point {
    static int x = 2;
}
class Test extends Point {
    void printBoth(int x) {
        System.out.println(x + " " + super.x);
    }
    public static void main(String[] args) {
        Test sample = new Test();
        sample.printBoth();
        System.out.println(sample.x + " " + ((Point)sample).x);
    }
}
```

那么 `Point` 类的 `x` 不再隐藏在 `Test` 类中。在 `Test` 类实例方法中，简单名称 `x` 指向在 `Point` 类中声明的字段。`Test` 类中的代码可以通过 `super.x` 引用同一个字段。表达式 `sample.x` 仍然指向继承的字段，并指向在 `Point` 类中声明的字段 `x`。该变量输出为：

```
2
2
```

## 8.3.1.2 final 字段

字段可以声明为 `final`（§4.12.4）。类变量和实例变量（静态和非静态字段）都可以被声明为 `final`。

空白 `final` 类变量必须初始化。空白 `final` 实例变量必须在类的每个构造函数中被初始化。

`final` 字段一旦初始化，就无法更改。这用于定义常量。

## transient 字段

变量可以被标记为 `transient` 以表示它们**不**应被序列化。这用于序列化机制。

## volatile 字段

`volatile` 关键字确保每个读取字段的线程都能看到该字段的最新写入。这是一种较弱的同步形式。

## 字段声明

注意，作为常量变量的静态字段（§4.12.4）会在其他静态字段（§12.4.2）之前初始化。这同样适用于接口（§9.3.1）。当通过简单类名引用此类字段时，它们永远不会被观察到具有其默认初始值（§4.12.5）。

如果声明符是实例变量（即非静态字段），则以下规则适用于其初始化器：

- 初始化器可以通过简单类名引用在类中声明的或由该类继承的任何类变量，即使该变量的声明位于初始化器的右侧（§3.5）。
- 初始化器可以使用关键字 `this`（§15.8.3）或关键字 `super`（§15.11.2, §15.12）引用当前对象。
- 在运行时，每当创建该类的实例时，都会对初始化器进行求值并执行赋值（§12.5）。

从变量初始化器到可能未初始化的字段的引用受额外限制，具体见 §8.3.3 和 §16（确定性赋值）中的规定。

字段声明中变量初始化器的异常检查规定于 §11.2.3。

变量初始化器也用于局部变量声明语句（§14.4），在每次执行变量声明语句时，都会对初始化器进行求值并执行赋值。

## 示例 8.3.2-1. 字段初始化

此程序产生输出：

```
1, 5
```

因为每当创建新的 `Point` 对象时，对 `x` 和 `y` 的赋值就会发生。

## 示例 8.3.2-2. 对类变量的前向引用

```java
class Test {
  float f = j;
  static int j = 1;
}
```

此程序编译通过没有错误；在类 `Test` 初始化时，它将 `j` 初始化为 1，在每创建一个类 `Test` 的实例时，它将 `f` 初始化为 `j` 的当前值。

## 8.3.3 初始化器中字段引用的限制



# 字段声明

## 字段引用的限制

对字段的引用有时会受到限制，即使该字段在作用域内。以下规则限制了对字段的前向引用（使用文本先于字段声明）以及自引用（字段用在自身的初始化器中）。

对于在类 `c` 或接口 `c` 中声明的类变量 `f` 的简单类名引用，如果满足以下条件，则为编译错误：

- 该引用出现在 `c` 的类变量初始化器中或 `c` 的静态初始化器中（§8.7）；且
- 该引用出现在 `f` 自身的声明符的初始化器中，或 `f` 声明符左侧的位置；且
- 该引用不是赋值表达式的左侧（§15.26）；且
- 包含该引用的内层类或接口是 `c`。

对于在类 `c` 中声明的实例变量 `f` 的简单类名引用，如果满足以下条件，则为编译错误：

- 该引用出现在 `c` 的实例变量初始化器中或 `c` 的实例初始化器中（§8.6）；且
- 该引用出现在 `f` 自身的声明符的初始化器中，或 `f` 声明符左侧的位置；且
- 该引用不是赋值表达式的左侧（§15.26）；且
- 包含该引用的内层类是 `c`。

### 示例 8.3.3-1. 字段引用的限制

此程序会发生编译错误：

```java
class Test1 {
    int i = j; // 编译错误：
    int j = i; // 错误的前向引用
}
```

而以下程序编译通过没有错误：

```java
class Test2 {
    Test2() { k = 2; }
    int j = 1;
    int i = j;
    int k;
}
```

即使 `Test2` 的构造函数（§8.8）引用了三行后声明的字段 `k`。

上述限制是为了在编译时捕获循环或其他畸形的初始化。因此，以下两种情况都是：

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

都会导致编译错误。方法的访问不通过此类方式检查，因此：

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
0
```

因为变量 `i` 使用类方法 `peek` 在 `j` 被其变量初始化器初始化之前访问了变量 `j` 的值，此时 `j` 仍具有其默认值（§4.12.5）。

一个更复杂的示例是：

```java
class UseBeforeDeclaration {
    static {
        x = 100;
        // ok - 赋值
        int y = x + 1;
        // error - 声明前读取
        int v = x = 3;
        // ok - x 在赋值表达式的左侧
        int z = UseBeforeDeclaration.x * 2;
        // ok - 未通过简单类名访问
    }
    Object o = new Object();
    void foo() { x++; }
    // ok - 发生在不同类
    { x++; }
    // ok - 发生在不同类
} {
    j = 200;
    // ok - 赋值
    j + 1;
    // error - 声明前的右侧
    int k = j + 1;
    // error - 对 j 的非法前向引用
    int n = j = 300;
}
```

# 方法声明

## 8.4 接收参数

接收参数是实例方法或内部类构造函数的可选语法设备。对于实例方法，接收参数表示调用方法的对象。对于内部类构造函数，接收参数表示被构造的对象。在两种情况下，接收参数的存在仅是为了允许在源代码中表示该类型，以便对其进行注解（§9.7.4）。接收参数不是形式参数；准确来说，它不是任何变量的声明（§4.12.3），它永远不会绑定到作为方法调用或类实例表达式的参数，且在运行时没有影响。

## 8.4.1 形式参数

方法或构造函数的形式参数（如果有）由逗号分隔的参数说明符列表指定。每个参数说明符由一个类型（可选由 `final` 修饰符和/或一个或多个注解引导）组成以及一个标识符（可选地跟随括号），用于指定参数的名称。

如果一个方法或构造函数没有形式参数，也没有接收者参数，则在方法或构造函数的声明中将出现一对空括号。

```
FormalParameterList:
    FormalParameter (, FormalParameter)

FormalParameter:
    [VariableModifier] UnannType VariableDeclaratorId
    VariableArity

VariableArityParameter:
    [VariableModifier] UnannType [Annotation] ... Identifier

VariableModifier:
    Annotation
    final
```

为了方便起见，这里展示了来自 §8.3 和 §4.3 的以下产生式：

```
VariableDeclaratorId:
    Identifier [Dims]

Dims:
    [Annotation] { [Annotation] [ ] }
```

方法或构造函数的形式参数可以是一个变长参数，通过类型后面的省略号（`...`）来表示。一个方法或构造函数最多允许一个变长参数。如果变长参数出现在参数说明符列表的最后一个位置以外的任何位置，则将导致编译错误。

在 `VariableArityParameter` 的语法中，请注意省略号（`...`）是一个独立的标记（§3.11）。在它和类型之间插入空格是可能的，但从风格上来说这是不建议的。

如果最后一个形式参数是变长参数，则该方法是变长方法。否则，它是固定长度方法。

形式参数声明和接收者参数上的注解修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果 `final` 作为形式参数声明的修饰符出现多次，则将导致编译错误。

形式参数的作用域和遮蔽在 §6.3 和 §6.4 中规定。

方法或构造函数声明两个同名的形式参数将导致编译错误。（也就是说，它们的声明提到了同一个 `Identifier`。）

如果声明为 `final` 的形式参数被赋值给方法或构造函数的体体，则将导致编译错误。

形式参数的声明类型取决于它是否为变长参数：

- 如果形式参数不是变长参数，则如果 `UnannType` `VariableDeclaratorId` 中没有出现括号对，则声明类型由 `UnannType` 表示，否则由 §10.2 规定。
- 如果形式参数是变长参数，则声明类型由 §10.2 规定的数组类型。

如果变长数组的声明类型具有不可重化的元素类型（§4.7），则该变长数组方法的声明会产生编译时的未检查警告，除非它被标记了 `@SafeVarargs`（§9.6.4）或是当该警告被 `@SuppressWarnings`（§9.6.4）抑制。

当调用方法或构造函数时（§15.12），在执行方法或构造体之前，实际参数表达式的值将初始化新创建的参数变量，每个变量具有声明的类型。`FormalParameter` 中出现的 `Identifier` 可以在方法或构造体中作为简单名称来引用该形式参数。

变长方法的调用可能包含比形式参数更多的实际表达式。所有位于变长参数之前的实际表达式都将被求值，其结果将存储在一个数组中，该数组将传递给方法调用（§15.12.4.2）。

类型为 `float` 的方法构造函数的形式参数始终包含 `float` 值集（§4.2.3）中的一个元素；同样，方法或构造函数类型为 `double` 的形式参数始终包含 `double` 值集中的一个元素。方法或构造函数类型为 `float` 的形式参数不允许包含并非 `float` 值集元素的 `float` 扩展指数值集元素，方法或构造函数类型为 `double` 的形式参数也不允许并非 `double` 值集元素的 `double` 扩展指数值集元素。

当对应于参数变量的实际参数表达式不是 FP-strict（15.4）时，允许该实际参数表达式求值使用提取自相应扩展指数值集的中间值。在存储到参数变量之前，此类表达式的结果将通过调用转换（§5.3）映射到相应标准值集中最接近的值。

以下是实例方法和内部类构造中接收者参数的示例：

```java
class Test {
    Test(/* ?? */)
    // 在顶层类的构造函数中允许接收者参数，因为没有可以想象的类型或名称。

    void m(Test this) {
        // OK：实例方法中的接收者参数
    }

    static void n(Test this) {
        // 非法：静态方法中的接收者参数
    }

    class A {
        A(Test.this) {
            // OK：接收者参数代表
            // 立即包围正在构造的 A 实例的 Test 实例。
        }

        void m(A this) {
            // OK：接收者参数代表
            // 调用 A.m() 的 A 实例。
        }

        class B {
            B(Test.A A.this) {
                // OK：接收者参数代表
                // 立即包围正在构造的 B 实例的 A 实例。
            }

            void m(Test.B this) {
                // OK：接收者参数代表
                // 调用 B.m() 的 B 实例。
            }
        }
    }
}
```

## 8.4.2 签名

两个方法或构造函数 `M` 和 `N` 具有签名，如果它们具有相同的名称、相同的类型参数（§8.4）以及相同的类型。

`m1` 的签名是 `m2` 的子签名，如果：

- `m2` 与 `m1` 具有签名，或
- `m2` 是 `m1` 的子签名。

子签名的概念用于表示两个签名不相同的方法之间的关系，其中一个可以覆盖另一个。具体来说，它允许一个不使用泛型的方法来覆盖该方法。

考虑示例：

```java
class CollectionConverter {
    List toList(Collection c) {...}
}
class Overrider extends CollectionConverter {
    List toList(Collection c) {...}
}
```

现在，假设这段代码是在泛型引入之前编写的，现在 `CollectionConverter` 的作者将其泛型化如下：

```java
class CollectionConverter {
    <T> List<T> toList(Collection<T> c) {...}
}
```

### 8.4.2.1 覆盖签名

特殊情况下，`Overrider.toList` 将不再覆盖 `CollectionConverter.toList`。相反，代码是非法的。这将极大抑制泛型的使用，因为库作者会犹豫于迁移现有代码。

## 8.4.3 修饰符

```
MethodModifier:
    （以下之一）
    Annotation public protected abstract static final native strictfp
```

方法声明上的注解修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果同一个关键字作为方法声明的修饰符出现多次，或者方法声明具有 `public`、`protected` 和 `private` 中的多个修饰符（§6.6），则将导致编译错误。

如果方法声明包含 `abstract` 关键字同时也包含 `private`、`static`、`final`、`native`、`strictfp` 或 `synchronized` 中的任何一个，则将导致编译错误。

如果方法声明包含 `native` 关键字同时也包含 `strictfp`，则将导致编译错误。

> 如果方法声明中出现一个或多个（不同的）方法修饰符，习惯上（并非要求）按照 `MethodModifier` 产生式所示的顺序出现。

### 8.4.3.1 抽象方法

抽象方法将其引入成员，提供签名（§8.4.2）、结果（§8.4.5）以及任何抛出句（§8.4.6），但不提供实现（§8.4.7）。非抽象的方法被称为具体方法。

抽象方法的声明必须直接出现在抽象类（称之为 `A`）内部，除非它出现在枚举声明（§8.9）中，否则将发生编译错误。

每一个非抽象的 `A` 子类（§8.1.1.1）必须为 `m` 提供实现，否则将发生编译时错误。

抽象类可以通过提供另一个抽象方法声明来重写抽象方法。

这可以提供一个放置文档注释的地方，用于精炼返回类型，或者当该方法被其子类实现时，声明其可能抛出的检查异常集合（且该集合的范围更小）。

非抽象的实例方法可以被抽象方法重写。

#### 示例 8.4.3.1-1. 抽象/抽象方法的重写

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

在类 `InfiniteBuffer` 中对方法 `get` 的重写声明规定，`InfiniteBuffer` 的任何子类中的 `get` 方法都不会抛出 `BufferEmpty` 异常，据认为是因为它在缓冲区生成数据，因此永远不会缺少数据。

#### 示例 8.4.3.1-2. 抽象/非抽象方法的重写

我们可以声明一个抽象类 `Point`，如果其子类要成为完整的、可实例化的类，则要求实现 `toString`：

```java
abstract class Point {
    int x, y;
    public abstract String toString();
}
```

此对 `toString` 的抽象声明重写了 `Object` 类的非抽象 `toString` 方法。（`Object` 类是 `Point` 类的隐式直接超类）。添加代码：

```java
class ColoredPoint extends Point {
    int color;
    public String toString() {
        return super.toString() + ": " + color; // 错误
    }
}
```

会导致编译时错误，因为 `super.toString()` 指向 `Point` 类中的方法 `toString`，该方法是抽象的且无法被调用。只有当 `Point` 类通过其他方法显式地提供它时，`Object` 类的 `toString` 方法才能对 `ColoredPoint` 类可用，如：

```java
abstract class Point {
    int x, y;
    public abstract String toString();
    protected String springer() { return super.toString(); }
}
class ColoredPoint extends Point {
    int color;
    public String toString() {
        return springer() + ": " + color; // 正确
    }
}
```

### 8.4.3.2 静态方法

声明为 `static` 的方法被称为类方法。

在类方法的头部或正体中使用任何周围声明的类型参数名称会导致编译时错误。

类方法始终在不引用特定对象的情况下被调用。尝试使用 `super` 关键字（§15.8.3）引用当前对象会导致编译时错误。

未声明为 `static` 的方法是实例方法，有时称为非静态方法。

实例方法总是相对于一个对象被调用，该对象在方法体执行期间成为关键字 `this` 和 `super` 所指代的当前对象。

### 8.4.3.3 最终方法

方法可以声明为 `final` 以防止子类重写或隐藏它。

尝试重写或隐藏 `final` 方法会导致编译时错误。

私有方法以及直接声明在 `final` 类（§8.1.1.2）内部的所有方法的行为都如同 `final` 方法，因为无法重写它们。

在运行时，机器码生成器或优化器可以“内联”（inline）`final` 方法的体，将方法的调用替换为内联的代码。内联必须保留方法调用的语义。特别是，如果目标是，则方法调用的语义必须被保留。

当调用泛型方法时，不需要显式提供，因为它们通常可以推断（§18 类型推断）。方法类型参数的作用域和遮蔽在 §6.3 中规定。

两个方法或构造方法 `M` 和 `N` 如果满足以下两个条件，则具有相同的类型参数：

- `M` 和 `N` 具有相同类型的数值参数（可能为零）。



## 类型参数适配

若 $A_1, \dots, A_n$ 是 $M$ 的类型参数，$B_1, \dots, B_n$ 是 $N$ 的类型参数；其中 $\theta = [B_1 := A_1, \dots, B_n := A_n]$。那么，对于所有的 $i$ ($1 \le i \le n$)，$A_i$ 的边界与 $\theta$ 应用于 $B_i$ 边界后的类型相同。

当方法或构造方法 $M$ 和 $N$ 具有相同的类型参数时，$N$ 中提到的类型可以通过将上述定义的 $\theta$ 应用于该类型来*适配*到 $M$ 的类型参数。

## 8.4.5 方法结果

方法声明的*结果*要么声明该方法返回的值的类型（*返回类型*），要么使用关键字 `void` 来指示该方法不返回任何值。

> **结果:**
>
> `UnannType`
>
> `void`

如果结果是 `void`，那么如果形式参数列表后没有出现括号对，则方法的返回类型表示为 `UnannType`，否则由 §10.2 规定。

如果返回类型是引用类型，则在相互覆盖的方法之间，返回类型可能会不同。返回类型可替换性概念支持*协变返回*，即返回类型特化为子类型。

如果一个返回类型为 $R_1$ 的方法声明 $d_1$ 对于另一个返回类型为 $R_2$ 的方法 $d_2$ 是*返回类型可替换的*，则满足以下任意条件：

- 如果 $R_1$ 是 `void`，则 $R_2$ 是 `void`。
- 如果 $R_1$ 是基本类型，则 $R_2$ 与 $R_1$ 相同。
- 如果 $R_1$ 是引用类型，则满足以下任意条件：
  - $R_1$ 适配到 $d_2$ 的类型参数 (§8.4.4) 是 $R_2$ 的子类型。
  - $R_1$ 可以通过未经检查的转换 (§5.1.9) 转换为 $R_2$ 的子类型。
  - $d_1$ 的签名与 $d_2$ 相同 (§8.4.2)，且 $R_1 = |R_2|$。

尽管是不安全的，但在定义中允许未经检查的转换，作为允许从非泛型向泛型平滑迁移的特殊允许。如果使用未经检查的转换来确定 $R_1$ 对于 $R_2$ 是返回类型可替换的，那么 $R_1$ 不是 $R_2$ 的子类型，覆盖规则 (§8.4.8.3, §9.4.1) 将产生编译时的未检查警告。

## 8.4.6 方法 throws

`throws` 子句用于表示方法或构造方法体中的语句可以抛出的任何受检异常类 (§11.1.1)。

```
Throws:
  `throws ExceptionType`
```

```
ExceptionTypeList:
  `ExceptionType [, ExceptionType]`
```

```
ExceptionType:
  ClassType
  TypeVariable
```

如果 `throws` 子句中提到的 `ExceptionType` 不是 `Throwable` 的子类型 (§4.10)，则会导致编译错误。

在 `throws` 子句中允许使用类型变量，尽管它们在 `catch` 子句 (§14.20) 中是不允许的。

在 `throws` 子句中提到未检查异常类 (§11.1.1) 是允许但不要求的。

`throws` 子句与方法或构造方法体异常检查之间的关系在 §11.2.3 中规定。

基本上，对于执行方法或构造方法体可能产生的每个受检异常，除非在方法或构造方法声明的 `throws` 子句中提到了该异常或其异常类型的超类型，否则将发生编译错误。

声明受检异常的要求允许 Java 编译器确保已包含对错误情况的处理。未能处理其体中作为受检异常抛出的异常情况的方法或构造方法，如果其 `throws` 子句中缺少适当的异常类型，通常会引起编译错误。

Java 编程语言因此鼓励一种编程风格，即罕见及其他真正异常的情况通过这种方式进行记录。

方法的 `throws` 子句与被覆盖或隐藏方法的 `throws` 子句之间的关系在 §8.4.8.3 中规定。

### 示例 8.4.6-1. 作为被抛出异常类型的类型变量

```java
import java.io.FileNotFoundException;
interface PrivilegedExceptionAction<E extends Exception> {
    void run() throws E;
}
class AccessController {
    public static <E extends Exception>
    Object doPrivileged(PrivilegedExceptionAction<E> action) throws E {
        action.run();
        return "success";
    }
}
class Test {
    public static void main(String[] args) {
        try {
            AccessController.doPrivileged(
                new PrivilegedExceptionAction<FileNotFoundException>() {
                    public void run() throws FileNotFoundException {
                        // ...
                    }
                });
        } catch (FileNotFoundException f) { /* Do something */ }
    }
}
```

## 8.4.7 方法体

方法体要么是实现方法的代码块，要么是一个分号，表示缺少实现。

```
MethodBody:
  Block
  ;
```

如果方法是抽象或原生的，则方法体必须是一个分号 (§8.4.3.1, §8.4.4)。更准确地说：

- 如果方法声明是 `abstract` 或 `native` 却有体（块），将发生编译错误。
- 如果方法声明既不是 `abstract` 也不是 `native` 却是分号，将发生编译错误。

如果为声明为 `void` 的方法提供了实现，但实现不需要执行代码，则方法体应写为不包含任何语句的块 `{ }`。方法体中返回语句的规则在 §14.17 中规定。

如果声明的方法具有返回类型 (§8.4.5)，如果方法体可以正常完成 (§14.1)，则会发生编译错误。换句话说，具有返回类型的方法必须通过返回语句返回值；方法不允许在体结束处“落下”。参见 §14.17 关于方法体中返回语句的精确规则。

方法可能具有返回类型但不包含返回语句。这里有一个例子：

```java
class DizzyDean {
  void init() { throw new RuntimeException("90 mph!"); }
}
```

## 8.4.8 继承、覆盖和隐藏

类 $C$ 继承其直接父类的所有方法 $m$（包括静态和实例方法）。

$C$ 继承其直接父类和直接接口的所有抽象和默认方法，满足以下所有条件：

- $m$ 是直接父类或直接接口 $D$ 的成员。
- $m$ 是 `public`、`protected` 或以包访问权限在 $C$ 中可见。
- $C$ 中声明方法的签名是 $m$ 的超签名 (§8.4.2)。

注意，方法是基于签名进行覆盖或隐藏的。例如，如果一个类声明了两个同名的 `public` 方法 (§8.4)，而子类覆盖了其中一个，子类仍然继承另一个。

**示例 8.4.8-1. 继承**

```java
interface I1 {
  int foo();
}

interface I2 {
  int foo();
}

abstract class Test implements I1, I2
```

在这里，抽象类 `Test` 继承了接口 `I1` 的抽象方法，也继承了 `I2` 的抽象方法。在确定从 `I1` 继承 `foo` 的关键问题是：`I2` 中的方法是否覆盖了 `I1` 中的方法 (§9.4.1)？不，因为 `I1` 和 `I2` 不是彼此的子接口。因此，从类 `Test` 来说，从 `I1` 继承 `foo` 是不受限制的；同样，从 `I2` 继承 `foo` 也是。

注意，继承的方法可以阻止抽象或默认方法的继承。（具体方法将覆盖来自超类的抽象或默认方法 §8.4.4 和 §9.4.1）。此外，如果一个父类型“已经”覆盖了另一个，则一个可能阻止另一个父类型方法的继承——这与接口的规则 (§9.4) 相同，并防止在继承多个方法且一个实现明显旨在取代另一个时发生冲突。

### 8.4.8.1 覆盖（实例方法）

在类 $C$ 中声明或由其继承的实例方法 $m_C$ 覆盖了类 $A$ 中声明的另一个方法 $m_A$，当且仅当满足以下所有条件：

- $C$ 是 $A$ 的子类。
- $C$ 不继承 $m_A$。
- $m_C$ 的签名是 $m_A$ 签名的超签名 (§8.4.2)。
- 满足以下任意条件：
  - $m_A$ 是公共的（`public`）。
  - $m_A$ 是受保护的（`protected`）。
  - $m_A$ 在与 $C$ 相同的包中以包访问权限声明，且要么 $C$ 声明了 $m_C$，要么 $m_A$ 是 $C$ 直接超类中的成员。
  - $m_A$ 以包访问权限声明，且 $m_C$ 重写了来自 $C$ 的某个超类的 $m_A$。
  - $m_A$ 以包访问权限声明，且 $m_C$ 重写了 $C$ 中的 $m'$（$m'$ 不同于 $m_C$ 和 $m_A$），使得 $m'$ 重写了来自 $C$ 的某个超类的 $m_A$。

如果 $m_C$ 非抽象且重写了来自 $C$ 的抽象方法 $m_A$，则称 $m_C$ 实现了来自 $C$ 的 $m_A$。

如果被重写的方法 $m_A$ 是静态方法（`static`），则会产生编译错误。

在这方面，方法的重写与字段的隐藏（§8.3）不同，因为允许实例变量隐藏静态变量。

在 $C$ 中声明或由 $C$ 继承的实例方法 $m_C$，在满足以下所有条件时，会重写来自 $C$ 的在接口 $I$ 中声明的另一个方法 $m_I$：

- $m_C$ 不是静态的。
- $m_I$ 不是静态的。
- $C$ 没有继承 $m_I$。
- $m_C$ 的签名是 $m_I$ 签名的子签名（§8.4.2）。
- $m_I$ 是公共的。

如果方法中的形式参数具有原始类型，而另一个方法中的对应参数具有参数化类型，则重写方法的签名可能与被重写的方法不同。这是为了方便现有代码进行迁移以利用泛型支持。

重写的概念包含了重写了其声明类之某个子类中的另一个方法的方法。这可以通过两种方式发生：

- 泛型类中的具体方法在某些参数化情况下，与类中的抽象方法具有相同的签名。在这种情况下，具体方法被继承，而抽象方法未被继承（如上所述）。此时，被继承的方法应被视为重写了其来自 $C$ 的抽象同类方法。（这种情形由于包访问权限而变得复杂：如果 $C$ 在不同的包中，那么 $m_A$ 本身就不会被继承，也不应被视为已重写）。
- 从类继承的方法可以重写超接口方法。（幸运的是，这里不涉及包访问权限。）

可以使用包含 `super` 关键字的方法调用表达式（§15.12）来访问被重写的方法。限定名或向超类类型进行强制转换在尝试访问被重写的方法时是无效的。

在这方面，方法的重写与字段的隐藏不同。

`strictfp` 修饰符的存在与否对于重写方法和实现抽象方法完全没有影响。例如，允许非 FP 严格方法重写 FP 严格方法，也允许 FP 严格方法重写非 FP 严格方法。

### 示例 8.4.8.1-1. 重写

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
}
class SlowPoint extends Point {
    int xLimit, yLimit;
    void move(int dx, int dy) {
        super.move(limit(dx, xLimit), limit(dy, yLimit));
    }
    static int limit(int d, int limit) {
        return d > limit ? limit : d < -limit ? -limit : d;
    }
}
```

在这里，`SlowPoint` 重写了 `Point` 类中 `move` 方法的声明。当对于 `SlowPoint` 实例调用 `move` 方法时，即使引用类型为 `Point`，也会调用其自身的定义。

### 示例 8.4.8.1-2. 隐藏与重写的区别

```java
import java.io.OutputStream;
import java.io.IOException;

class BufferOutput {
    OutputStream o;
    BufferOutput(OutputStream o) { this.o = o; }
    protected byte[] buf = new byte[512];
    protected int pos = 0;
    public void putchar(char c) throws IOException {
        // ... 
    }
}

class LineOutput extends BufferOutput {
    LineOutput(OutputStream o) { super(o); }
    public void putstr(String s) throws IOException {
        // ...
    }
}
```

因为 `greeting` 的调用使用了 `s` 的类型（即 `Super`），在编译时确定调用哪个类方法，而 `name` 的调用则使用了 `s` 的类（即 `Sub`），在运行时确定调用哪一个实例方法。

## 8.4.8.3 重写与隐藏的限制

如果返回类型为 $R_1$ 的方法 $d_1$ 重写或隐藏了返回类型为 $R_2$ 的另一个方法 $d_2$ 的声明，则 $d_1$ 必须是 $d_2$ 的返回类型替换（§8.4.5），否则将发生编译时错误。

此规则允许协变返回类型——即在重写方法时细化该方法的返回类型。

如果 $R_1$ 不是 $R_2$ 的子类型，则会发生编译时未检查警告，除非被 `@SuppressWarnings` (§9.6.4.5) 抑制。

重写或隐藏另一个方法（包括实现接口中定义的抽象方法）的方法声明抛出的受检异常不能多于重写或隐藏的方法。

> 在此情况下，方法的重写与字段的隐藏（§8.3）不同，因为字段隐藏另一个类型的字段是允许的。

更准确地说，假设 $B$ 是一个类或接口，$A$ 是 $B$ 的超类或超接口，且 $B$ 中的方法声明 $m_2$ 重写或隐藏了 $A$ 中的方法声明 $m_1$。那么：

- 如果 $m_2$ 有一个 `throws` 子句提到了任何受检异常类型，则 $m_1$ 必须有一个 `throws` 子句，否则将发生编译时错误。
- 对于 $m_2$ `throws` 子句中列出的每一个受检异常类型，相同的异常或其父类型必须出现在 $m_1$ `throws` 子句的擦除（§4.6）中；否则将发生编译时错误。
- 如果 $m_1$ 擦除后的 `throws` 子句不包含 $m_2$ `throws` 子句中每个异常类型的父类型（如有需要对 $m_1$ 的参数进行调整），则会发生编译时未检查警告，除非被 `@SuppressWarnings` (§9.6.4.5) 抑制。

如果声明 $T$ 有一个成员方法 $m_1$，且在 $T$ 或其超类型中声明了方法 $m_2$，使得以下所有条件均成立，则会发生编译时错误：

- $m_1$ 和 $m_2$ 具有相同的名称。
- $m_2$ 从 $T$ 可访问（§6.6）。
- $m_1$ 的签名不是 $m_2$ 签名的子签名（§8.4.2）。
- $m_1$ 的签名或某些 $m_1$（直接或间接）重写的方法在擦除后，与 $m_2$ 的签名或某些 $m_2$（直接或间接）重写的方法在擦除后具有相同的签名。

这些限制是必要的，因为泛型是通过擦除实现的。上述规则意味着在同一个类中声明的具有相同名称的方法必须具有不同的擦除。它还意味着类型声明不能实现或扩展泛型接口的两个不同调用。

重写或隐藏方法的访问修饰符必须提供至少不低于被重写或隐藏方法的访问权限，如下：

- 如果被重写或隐藏的方法是 `public`，则重写或隐藏方法必须是 `public`；否则将发生编译时错误。
- 如果被重写或隐藏的方法是 `protected`，则重写或隐藏方法必须是 `protected` 或 `public`；否则将发生编译时错误。



- 如果被重写或隐藏的方法具有包级访问权限（package access），则重写或隐藏方法不能是 `private`；否则将发生编译时错误。

> 注意，从技术术语上讲，私有方法无法被重写或隐藏。这意味着子类可以声明一个与其某个超类中的私有方法签名相同的方法，且并不要求该方法的返回类型或 `throws` 子句与该私有超类的对应的有任何关系。

## 示例 8.4.8.3-1. 协变返回类型

以下声明从 Java SE 5.0 开始的 Java 编程语言中是合法的：

```java
class C implements Cloneable {
  C copy() throws CloneNotSupportedException {
    return (C) clone();
  }
}
class D extends C implements Cloneable {
  D copy() throws CloneNotSupportedException {
    return (D) clone();
  }
}
```

重写的宽松规则也允许放宽实现接口的抽象类的条件。

## 示例 8.4.8.3-2. 返回类型引起的未检查警告

考虑：

```java
class StringSorter {
    // 将字符串集合转换为排序后的列表
    List toList(Collection c) {...}
}
```

并假设有人编写了 `StringSorter` 的子类：

```java
class Overrider extends StringSorter {
    List toList(Collection c) {...}
}
```

现在，`StringSorter` 的作者决定将代码泛化：

```java
class StringSorter {
    // 将字符串集合转换为排序后的列表
    List<String> toList(Collection<String> c) {...}
}
```

在编译具有新定义的子类型类 `Overrider` 时，会给出一个未检查警告，因为 `Overrider.toList` 的返回类型是 `List`，它不是重写方法返回类型 `List<String>` 的子类型。

## 示例 8.4.8.3-3. 错误的 throws 重写

该程序在声明 `BadPointException` 类时，使用了声明新异常异常的通常和常规形式：

```java
class BadPointException extends Exception {
```

## 8.4.9 方法重载

如果一个类中的两个方法（无论是在同一个类中声明的、被类继承的、还是一个声明一个继承）具有相同的名称，但其签名不是重写等效的（override-equivalent），则称该方法名为被重载。

这一事实不会引起任何困难，其本身绝不会导致编译错误。对于两个同名方法，其返回类型之间或 `throws` 子句之间没有强制性的关系，除非它们的签名是重写等效的。

当调用方法时 (§ 15.12)，在编译时，将使用实际的实参数个数（以及任何显式类型参数）以及参数的编译时类型来确定将调用的方法签名 (§ 15.12.2)。如果要调用的方法是实例方法，则将使用动态方法查找在运行时确定实际要调用的方法。

### 示例 8.4.9-1. 重载

```java
class Point {
    float x
```

在这里，Point 类有两个同名为 `move` 的成员方法。对于任何特定的方法调用，所选的 Point 类重载方法是在编译时通过 § 15.12 中的重载解析程序确定的。

总而言，Point 类的方法包括：在 Point 中声明的 float 变量 `x` 和 `y`、两个声明的 `move` 方法、声明的 `toString` 方法，以及 Point 从其直接父类 Object (§ 4.3.2) 继承的成员（例如 `hashCode` 方法）。注意，Point 没有继承 Object 类的 `toString` 方法，因为该方法被 Point 类中 `toString` 方法的声明重写了。

### 示例 8.4.9-2. 重载、重写与隐藏

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; }
    int color;
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(float dx, float dy) { x += dx; }
    void move(int dx, int dy) { x += dx; y += dy; }
}
```

在这里，RealPoint 类用自己的实例变量 `x` 和 `y` 隐藏了 Point 类实例变量 `x` 和 `y` 的声明，并用自己的 `move` 方法重写了 `move` 方法。它还用另一个不同的签名重载了 `move` 名称 (§ 8.4.2)。

在此示例中，RealPoint 类的成员包括继承自 Point 类的实例变量 `color`、在 RealPoint 中声明的实例变量 `x` 和 `y`，以及在 RealPoint 中声明的两个方法。对于任何特定的方法调用，将选择 RealPoint 的哪一个重载方法将在编译时通过 § 15.12 中的重载解析程序来确定。

以下程序是前述程序的变体：

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; }
    int getX() { return x; }
    int getY() { return y; }
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(float dx, float dy) { x += dx; y += dy; }
    float getX() { return x; }
    float getY() { return y; }
}
```

在这里，重写的方法 `getX` 和 `getY` 返回了其 `x` 和 `y` 的值；RealPoint 类通过声明具有相同签名的方法重写了这些方法。结果是每个方法在编译时产生两个错误，因为返回类型不匹配：Point 类中的方法返回 `int` 值，而 RealPoint 类中的方法返回 `float` 值。

此程序修正了前述程序的错误：

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
    int getX() { return x; }
    int getY() { return y; }
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(float dx, float dy) { x += dx; y += dy; }
    float getX() { return x; }
    float getY() { return y; }
}
```

在这里，RealPoint 中的重写方法 `getX` 和 `getY` 的返回类型与其重写的 Point 类方法的返回类型相同，因此这段代码可以成功编译。

现在，考虑这个程序：

```java
class Test {
  public static void main(String[] args) {
    RealPoint rp = new RealPoint();
    Point p = rp;
    rp.move(1, 7.1828f, 4.14159f);
    p.move(1, -1);
    show(p.x, p.y);
    show(rp.x, p.y);
    show(p.getX(), p.getY());
    show(rp.getX(), p.getY());
  }
  public static void show(int x, int y) {
    System.out.println(x + ", " + y);
  }
  public static void show(float x, float y) {
    System.out.println(x + ", " + y);
  }
}
```

该程序的输出是：

```
(0, 0)
(2.718278, 3.14159)
(0, 0)
(2.718278, 0)
(0, 0)
(2.718278, 0)
```



## 8.4.9 方法重载

如果一个类中的两个方法（无论是在同一个类中声明的、被类继承的、还是一个声明一个继承）具有相同的名称，但其签名不是重写等效的，则称该方法名为被重载。

这一事实不会引起任何困难，其本身绝不会导致编译错误。对于两个同名方法，其返回类型之间或 `throws` 子句之间没有强制性的关系，除非它们的签名是重写等效的。

当调用方法时 (§ 15.12)，在编译时，将使用实际的参数个数（以及任何显式类型参数）以及参数的编译时类型来确定将调用的方法签名 (§ 15.12.2)。如果要调用的方法是实例方法，则将使用动态方法查找在运行时确定实际要调用的方法。

### 示例 8.4.9-1. 重载

```java
class Point {
    float x;
    float y;
    void move(int dx, int dy) { x += dx; y += dy; }
    void move(float dx, float dy) { x += dx; y += dy; }
    public String toString() { return "(" + x + ", " + y + ")"; }
}
```

在这里，`Point` 类有两个同名为 `move` 的成员方法。对于任何特定的方法调用，所选的 `Point` 类重载方法是在编译时通过 § 15.12 中的重载解析程序确定的。

总的来说，`Point` 类的方法包括：在 `Point` 中声明的 `float` 变量 `x` 和 `y`、两个声明的 `move` 方法、声明的 `toString` 方法，以及 `Point` 从其直接父类 `Object` 继承的成员 (§ 4.3.2)，例如 `hashCode` 方法。注意，`Point` 类没有继承 `Object` 类的 `toString` 方法，因为该方法被 `Point` 类中 `toString` 方法的声明重写了。

### 示例 8.4.9-2. 重载、重写与隐藏

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; }
    int color;
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(float dx, float dy) { x += dx; }
    void move(int dx, int dy) { x += dx; y += dy; }
}
```

在这里，`RealPoint` 类用自己的实例变量 `x` 和 `y` 隐藏了 `Point` 类实例变量 `x` 和 `y` 的声明，并用自己的 `move` 方法重写了 `move` 方法。它还用另一个不同的签名重载了 `move` 名称 (§ 8.4.2)。

在此示例中，`RealPoint` 类的成员包括继承自 `Point` 类的实例变量 `color`、在 `RealPoint` 中声明的实例变量 `x` 和 `y`，以及在 `RealPoint` 中声明的两个方法。对于任何特定的方法调用，将选择 `RealPoint` 的哪一个重载方法将在编译时通过 § 15.12 中的重载解析程序来确定。

以下程序是前述程序的变体：

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; }
    int getX() { return x; }
    int getY() { return y; }
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(float dx, float dy) { x += dx; y += dy; }
    float getX() { return x; }
    float getY() { return y; }
}
```

在这里，重写的方法 `getX` 和 `getY` 返回了其 `x` 和 `y` 的值；`RealPoint` 类通过声明具有相同签名的方法重写了这些方法。结果是每个方法在编译时产生两个错误，因为返回类型不匹配：`Point` 类中的方法返回 `int` 值，而 `RealPoint` 类中的方法返回 `float` 值。

此程序修正了前述程序的错误：

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
    int getX() { return x; }
    int getY() { return y; }
}
class RealPoint extends Point {
    float x = 0.0f, y = 0.0f;
    void move(float dx, float dy) { x += dx; y += dy; }
    float getX() { return x; }
    float getY() { return y; }
}
```

在这里，`RealPoint` 中的重写方法 `getX` 和 `getY` 的返回类型与其重写的 `Point` 类方法的返回类型相同，因此这段代码可以成功编译。

现在，考虑这个程序：

```java
class Test {
  public static void main(String[] args) {
    RealPoint rp = new RealPoint();
    Point p = rp;
    rp.move(1, 7.1828f, 4.14159f);
    p.move(1, -1);
    show(p.x, p.y);
    show(rp.x, p.y);
    show(p.getX(), p.getY());
    show(rp.getX(), p.getY());
  }
  public static void show(int x, int y) {
    System.out.println(x + ", " + y);
  }
  public static void show(float x, float y) {
    System.out.println(x + ", " + y);
  }
}
```

该程序的输出是：

```
(0, 0)
(2.718278, 3.14159)
(0, 0)
(2.718278, 0)
(0, 0)
(2.718278, 0)
```

## 8.5.1 静态成员类型声明

`static` 关键字可以修改非内部类或接口 `t` 的体内存中对成员类型 `c` 的声明。其作用是声明 `c` 不是内部类。正就像 `t` 的静态方法在其体内存中没有 `t` 的当前实例一样，`c` 也没有 `t` 的当前实例，且不具有词法包围的实例。

如果 `static` 类包含了对包围类非静态成员的使用，则将是一个编译时错误。

成员接口是隐式静态的 (§9.1.1)。允许在成员接口的声明中冗余地指定 `static` 修饰符。

## 8.6 实例初始化器

在类中声明的实例初始化器在类的实例创建时执行（§12.5, §15.9, §8.8.7.1)。

```
InstanceInitializer:
Block
```

如果实例初始化器无法正常完成，则将是一个编译时错误 (§14.21)。

如果在实例初始化器中的任何地方出现 `return` 语句 (§14.17)，则将是一个编译时错误。

允许实例初始化器使用关键字 `this` (§15.8.3) 或关键字 `super` (§15.11.2, §15.12) 来引用当前对象，并使用范围内的任何类型变量。

关于实例初始化器如何引用实例变量的限制（即使实例变量在范围内）规定在 §8.3.3。

实例初始化器的异常检查规定在 §11.2.3。

## 8.7 静态初始化器

在类中声明的静态初始化器在类初始化时执行 (§12.4.2)。与任何字段初始化器一起，静态初始化器可以用于初始化类的类变量。

```
StaticInitializer:
static Block
```

如果静态初始化器无法正常完成，则将是一个编译时错误 (§14.21)。

如果在静态初始化器中的任何地方出现 `return` 语句 (§14.17)，则将是一个编译时错误。

如果在静态初始化器中的任何地方出现关键字 `this` (§15.8.3)、关键字 `super` (§15.11, §15.12) 或在静态初始化器之外声明的任何类型变量，则将是一个编译时错误。

关于静态初始化器如何引用类变量的限制（即使类变量在范围内）规定在 §8.3.3。

静态初始化器的异常检查规定在 §11.2.3。

## 8.8 构造函数声明

构造函数用于创建作为类实例的对象 (§12.5, §15.9)。

```
ConstructorDeclaration:
[ConstructorModifier] ConstructorDeclarator [Throws] ConstructorBody
```

```
ConstructorDeclarator:
[TypeParameters] SimpleTypeName
([ReceiverParameter ,][FormalParameterList])
```

```
SimpleTypeName:
TypeIdentifier
```

本节中的规则适用于所有类声明中的构造函数，包括枚举声明。然而，枚举声明在构造函数修饰符、构造函数体和默认构造函数方面有特殊规则；这些规则规定在 §8.9.2 中。

`ConstructorDeclarator` 中的 `SimpleTypeName` 必须是包含构造函数声明的类的简单名称，否则将发生编译时错误。

在所有其他方面，构造函数声明看起来就像没有结果类型的方法声明 (§8.4.5)。

构造函数声明不是成员。它们从不被继承，因此不受隐藏或覆盖的影响。

构造函数通过类实例创建表达式 (§15.9)、由字符串拼接运算符 `+` 引起的转换和连接 (§15.18.1) 以及来自其他构造函数的显式构造函数调用 (§8.8.7) 被调用。对构造函数的访问受访问修饰符 (§6.6) 限制，因此可以通过声明一个不可访问的构造函数 (§8.8.10) 来防止实例化。

构造函数永远不会通过方法调用表达式 (§15.12) 被调用。

### 8.8-1. 构造函数声明

```java
class Point {
  int x, y;
  Point(int x, int y) { this.x = x; this.y = y; }
}
```

### 8.8.1 形式参数

构造函数的形式参数在语法和语义上与方法相同 (§8.4.1)。

非私有内部类的构造函数隐式地声明第一个参数为代表该类直接包围实例的变量 (§15.9.2, §15.9.3)。

这种类之所以具有隐式声明参数的原理是微妙的。以下解释可能有所帮助：

- 在非私有内部类的类创建表达式中，§15.9.2 规定了成员类的直接包围实例。该成员类可能由与类创建表达式编译器不同的编译器产生。创建表达式的编译器必须有一个标准，将一个引用（代表直接包围实例）传递给成员类的构造函数。因此，Java 语言规定非私有内部类的构造函数隐式地声明了一个用于包围实例的参数。

- 在局部类（不在静态上下文中）或匿名类的类创建表达式中，§15.9.2 规定了局部/匿名类的直接包围实例。局部/匿名类务必作为实例创建表达式由编译器产生。该编译器可以以其想要的方式表示直接包围实例。Java 语言没有必要在局部/匿名类的构造函数中隐式地声明参数。

- 在成员类的类创建表达式中，§15.9.2 规定了成员类的直接包围实例。该成员类可能由与类创建表达式编译器不同的编译器产生。创建表达式的编译器必须有一个标准，将一个引用（代表直接包围实例）传递给成员类的构造函数。因此，Java 语言规定非私有内部类的构造函数隐式地声明了一个用于包围实例的参数。

- 在匿名类的类创建表达式中，§15.9.2 规定了局部/匿名类的直接包围实例。局部/匿名类务必作为实例创建表达式由编译器产生。该编译器可以以其想要的方式表示直接包围实例。Java 语言没有必要在局部/匿名类的构造函数中隐式地声明参数。

### 8.8.2 构造函数签名

在类中声明两个签名相同的构造函数将是一个编译时错误 (§8.4)。

在类中声明两个具有擦除相同签名的构造函数将是一个编译时错误 (§4.6)。

### 8.8.3 构造函数修饰符

```
ConstructorModifier:
(one of)
Annotation public protected private
```

构造函数上的注解修饰符规定在 §9.7.4 §9.7.5。

如果在构造函数声明中重复出现访问修饰符 `public`、`protected` 或 `private`，则是一个编译时错误。

在普通类声明中，没有访问修饰符的构造函数具有包访问权限。

如果方法声明中有两个或多个（不同的）方法修饰符，习惯上但并非要求它们按照上述 `Modifier` 产生式的顺序出现。

与其他不同，构造函数不能是 `abstract`、`static`、`final`、`native`、`strictfp` 或 `synchronized`：

- 构造函数不被继承，因此没有需要声明为 `final`。
- `abstract` 构造函数永远无法实现。
- 构造函数总是相对于对象调用的，因此类为 `static` 没有意义。
- 构造函数没有实际需要 `synchronized`，因为会锁定正在构造的对象，而该对象通常在所有构造函数完成工作之前对其他线程不可见。
- `native` 构造函数是一种任意的语言设计，便于虚拟机验证在对象构造期间正确调用父类构造函数。
- 无法将构造函数声明为 `strictfp`（相对于方法 §8.4.3）是一种刻意的语言设计；它有效地确保了构造函数只有在它是 fp-strict 时才是 fp-strict。

### 8.8.4 泛型构造函数

如果构造函数声明了一个或多个类型变量 (§4.4)，则它是 `generic` 的。

这些类型变量被称为构造函数的 `类型参数`。泛型构造函数的类型参数部分的形式与泛型类的类型参数部分相同 (§8.1.2)。

即使类本身没有声明为泛型，构造函数也可以是泛型的。

构造函数类型参数的作用规定在 §6.3 和 §6.4。

### 8.8.5 构造函数 Throws



构造函数的 `throws` 子句在结构和行为与方法的 `throws` 子句相同（§8.4.6）。

## 8.8.6 构造函数的类型

构造函数的类型由其签名和其 `throws` 子句提供的异常类型组成。

## 8.8.7 构造函数体

构造函数体的第一条语句可以是对同一类或其直接父类的另一个构造函数的显式调用（§8.8.7.1）。

```
ConstructorBody:
[ExplicitConstructorInvocation] [BlockStatements]
```

如果构造函数通过一系列一个或多个涉及自身的显式构造函数调用直接或间接地调用自身，则将产生编译错误。

如果构造函数体不是以显式构造函数调用开头，且所声明的构造函数不是原始类 `Object` 的一部分，则构造函数体隐式地以父类构造函数调用 `super();` 开始，即对其直接父类的无参数构造函数的调用。

除了显式构造函数调用的可能性以及显式返回值（§14.17）外，构造函数体类似于方法体（§8.4.7）。

如果返回语句（§14.17）不包含表达式，则可以在构造函数体中使用。

### 8.8.7-1 构造函数体

```java
class Point {
  int x, y;
  Point(int x, int y) {this.x = x; this.y = y; }
}
class ColoredPoint extends Point {
  static final int WHITE = 0, BLACK = 1;
  int color;
  ColoredPoint(int x, int y) {
    this(x, y, WHITE);
  }
  ColoredPoint(int x, int y, int color) {
    super(x, y);
    this.color = color;
  }
}
```

### 8.8.7.1 显式构造函数调用

```
ExplicitConstructorInvocation:
[TypeArguments] this ([ArgumentList] ) ;
[TypeArguments] super ([ArgumentList] ) ;
ExpressionName . [TypeArguments] super ([ArgumentList] ) ;
Primary . [TypeArguments] super ([ArgumentList] ) ;
```

为了方便起见，这里显示了 §4.5.1 和 §15.12 中的以下产生式：

```
TypeArguments:
< TypeArgumentList >

ArgumentList:
Expression [, Expression ]
```

显式构造函数调用语句分为两类：

- **替代构造函数调用**以关键字 `this` 开头（可能带有显式类型参数前缀）。它们用于调用同一类的替代构造函数。

- **父类构造函数调用**以关键字 `super`（可能带有显式类型参数前缀）或 `Primary` 表达式或 `ExpressionName` 开头。它们用于调用直接父类的构造函数。它们进一步细分为：

    - **未限定的子类构造函数调用**以关键字 `super` 开头（可能带有显式类型参数前缀）。

    - **限定的父类构造函数调用**以 `Primary` 表达式或 `ExpressionName` 开头。这种调用允许子类显式地指定相对于直接父类的新创建的对象的直接邻接实例（§8.1.3）。当父类是内部类时，这可能是必要的。

构造函数体中的显式构造函数调用语句不能引用在本类或任何父类中声明的任何实例变量或实例方法，也不能在任何表达式中使用 `this` 或 `super`；否则将发生编译错误。

这种对使用当前实例的禁止解释了为什么显式构造函数调用语句被认为发生在静态上下文中（§8.1.3）。

如果 `this` 或 `super` 左侧存在 `[TypeArguments]`，则如果任何类型参数是通配符，则会导致编译错误（§4.5.1）。

令 `c` 为被实例化的类，令 `s` 为 `c` 的直接父类。

如果父类构造函数调用语句是非限定的，那么：

- 如果 `s` 是一个内部类，但 `s` 不是包含 `c` 的类的成员，则将发生编译错误。

如果父类构造函数调用语句是限定的，那么：

- 如果 `s` 不是内部类，或者 `s` 的声明发生在静态上下文中，则将发生编译错误。

- 否则，令 `p` 为 `.super` 之前的 `Primary` 表达式或 `ExpressionName`，令 `o` 为 `s` 的直接邻接类。如果 `p` 的类型不是 `o` 或 `o` 的子类，或者 `p` 的类型不可访问（§6.6），则将发生编译错误。

显式构造函数调用语句可以抛出的异常类型在 §11.2 中指定。

替代构造函数调用的评估过程是：首先从左到右像普通方法调用一样评估构造函数的参数；然后调用构造函数。

父类构造函数调用的评估过程如下：

1. 令 `i` 为正在创建的实例。必须确定相对于 `s` 的 `i` 的直接邻接实例（如果有）：

    - 如果 `s` 不是内部类，或者 `s` 的声明发生在静态上下文中，则不存在相对于 `s` 的 `i` 的直接邻接实例。

    - 如果父类构造函数调用是非限定的，则 `s` 必然是一个局部类或内部类。

如果 `s` 是局部类，令 `o` 为 `s` 的直接邻接类型声明。

如果 `s` 是内部类，令 `o` 为 `c` 的以 `s` 为成员的最内层邻接类。

令 `n` 为一个整数（n ≥ 1），使得 `o` 是 `c` 的第 `n` 个词法嵌套声明。相对于 `s` 的 `i` 的直接邻接实例是 `this` 的第 `n` 个词法嵌套实例。

虽然 `S` 可能因为继承成为 `C` 的成员，但 `this` 的第零词法嵌套实例（即它本身）从不被用作 `S` 的 `i` 主要直接邻接实例。

- 如果父类构造函数调用是限定的，则评估 `.super` 之前的 `Primary` 表达式或 `ExpressionName` `p`。如果 `p` 值为 `null`，则抛出 `NullPointerException` 并完成父类构造函数调用。否则，该评估的结果为相对于 `s` 的 `i` 的直接邻接实例。

- 在确定了相对于 `s` 的 `i` 的直接邻接实例（如果有）后，父类构造函数调用的评估是从左到右像普通方法调用一样评估构造函数的参数；然后调用构造函数。

- 最后，如果父类构造函数调用正常完成，则执行 `C` 的所有实例变量初始化器和 `C` 的所有初始化器。如果一个初始化器或实例变量 `i` 位于另一个初始化器或实例变量 `j` 之前，则 `i` 在 `j` 之前执行。

无论父类构造函数调用是实际作为显式构造函数调用出现还是隐式提供的，都会执行实例变量初始化器和初始化器的执行。（替代构造函数调用不执行这种隐式执行。）

### 8.8.7.1-1. 对显式构造函数调用语句的限制

如果 §8.8.7 示例中 `ColoredPoint` 的第一个构造函数更改如下：

```java
class Point {
  int x, y;
  Point(int x, int y) {this.x = x; this.y = y; }
}
class ColoredPoint extends Point {
  static final int WHITE = 0, BLACK = 1;
  int color;
  ColoredPoint(int x, int y) {
    this(x, y, color); // 改为 color
  }
  ColoredPoint(int x, int y, int color) {
    super(x, y);
    this.color = color;
  }
}
```

则将发生编译错误，因为实例变量 `color` 不能被显式构造函数调用使用。

### 8.8.7.1-2. 父类构造函数调用

在下面的代码中，`ChildInner` 没有词法嵌套类型声明，因此 `ChildInner` (Inner) 的父类没有邻接实例。然而，`ChildInner` (Inner) 的父类有一个词法嵌套类型声明（Outer），且 `Inner` 的实例有一个 `Outer` 的邻接实例。在创建 `Inner` 实例时，`Outer` 的邻接实例被设置。当我们创建一个 `ChildInner` 实例（它隐式是 `Inner` 的实例）时，我们必须通过 `ChildInner` 构造函数中的限定父类调用语句提供 `Outer` 的邻接实例。该 `Outer` 实例是相对于 `Inner` 的 `ChildInner` 的直接邻接实例。

```java
class Outer {
    class Inner {
    }
    class ChildInner extends Outer.Inner {
        ChildInner() { new Outer().super(); }
    }
}
```

或许，同一个 `Outer` 实例可以作为多个 `ChildInner` 实例相对于 `Inner` 的直接邻接实例。下例程序通过向 `ChildInner` 的构造函数传递一个 `Outer` 实例来实现，该构造函数在限定的父类构造函数调用中使用该实例。

```java
class Outer {
    int secret = 5;
    class Inner {
        int getSecret() { return secret; }
        void setSecret(int s) { secret = s; }
    }

    class ChildInner extends Outer.Inner {
        ChildInner(Outer x) { x.super(); }
    }
}
```

```java
public class Test {
    public static void main(String[] args) {
        Outer x = new Outer();
        ChildInner a = new ChildInner(x);
        ChildInner b = new ChildInner(x);
        System.out.println(b.getSecret());
        a.setSecret(6);
        System.out.println(b.getSecret());
    }
}
```

该程序产生以下输出：

```
5
6
```

结果是，对 `Outer` 的共同实例中实例变量的操作通过对不同 `ChildInner` 实例的引用是可见的，尽管这些引用在传统意义上并不是别名。

## 8.8.8 构造函数重载

构造函数的重载在行为与方法的重载相同（§8.4.9）。重载在编译时通过每个类实例创建表达式（§15.9）进行解析。

## 8.8.9 默认构造函数

如果类没有包含任何构造函数声明，则会隐式声明一个默认构造函数。顶层类、成员类或局部类的默认构造函数的格式如下：

- 默认构造函数具有与类相同的访问修饰符，除非该类缺少访问修饰符，在这种情况下默认构造函数具有包访问权限（§6.6）。

- 默认构造函数没有形式参数，但在非私有的内部成员类中外，默认构造函数隐式地声明一个形式参数，代表该类的直接外层类实例（§8.8.1, §15.9.3）。

- 默认构造函数没有 `throws` 子句。

- 如果被声明的类是原始类 `Object`，则默认构造函数体为空。默认构造函数简单地调用不带参数的超类构造函数。

匿名类的默认构造函数的格式在 §15.9.5.1 中指定。

如果隐式声明了默认构造函数但父类没有可访问的无参且没有 `throws` 子句的构造函数，则是编译错误。

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

其中默认构造函数是 public 的，因为类 `Point` 是 public 的。

### 示例 8.8.9-2. 构造函数与类的可访问性

类的默认构造函数的访问权限与类本身相同的规则是简单且直观的。然而，这并不意味着只要类是可访问的，构造函数就是可访问的。考虑：

```java
package p1;
public class Outer {
    protected class Inner {
    }
}
package p2;
class SonOfOuter extends Outer {
    void foo() {
        new Inner(); // 编译时访问错误
    }
}
```

`Inner` 的默认构造函数是 protected 的。然而，虽然 `Inner` 对于 `Outer` 是保护性的，`Inner` 在 `SonOfOuter` 中是可以访问的，因为它是 `Outer` 的子类。`Inner` 的构造函数在 `SonOfOuter` 中是不可访问的，因为类 `SonOfOuter` 不是 `Inner` 的子类！因此，尽管 `Inner` 是可访问的，它的默认构造函数却不可访问。

## 8.10 防止类的实例化

可以通过声明至少一个构造函数来设计类，防止类之外的代码创建该类的实例，以防止默认构造函数的创建，并将所有构造函数都声明为私有（§6.6.1）。

public 类同样可以通过声明至少一个构造函数来防止在其包之外创建实例，以防止具有 public 访问权限的默认构造函数的创建，并且没有 public 或 protected 的构造函数（§6.6.2）。

### 示例 8.10-10. 通过构造函数可访问性防止实例化

```java
class ClassOnly {
    private ClassOnly() { }
    static String just = "the only lonely";
}
```

在这里，`ClassOnly` 无法实例化，而在下面的代码中：

```java
package just;
public class PackageOnly {
    PackageOnly() {}
    String[] Desserts = {"cheecake", "ice cream"};
}
```

`PackageOnly` 在其声明的包内是可以实例化的。如果 `PackageOnly` 的构造函数是保护的，则在包之外是不可实例化的。

## 8.9 枚举类型

枚举声明体可以包含枚举常量。枚举声明定义了一种特殊的类类型。

```
EnumDeclaration:
[ClassModifier] enum [SuperInterfaces] EnumBody
```

如果枚举声明具有 `abstract` 修饰符，则是编译错误。枚举声明隐式是 `final` 的（§8.1）。

嵌套枚举类型隐式是 `static`。允许在枚举声明中冗余地指定 `static` 修饰符。

枚举声明具有 `public` 或 `private` 的修饰符（§6.6）。

枚举类型除了其常量定义的实例外没有其他实例。除了编译错误外，还有三种机制确保不会产生定义常量之外的枚举实例：

- Enum 中的 `final` `clone` 方法确保了枚举常量永远不会被克隆。

- 禁止通过反射实例化枚举类型。

- 序列化机制的特殊处理确保了在反序列化时不会创建重复实例。

### 8.9.1 枚举常量

枚举声明体可以包含枚举常量。枚举常量定义了枚举类型的一个实例。

```
EnumBody:
  { [EnumConstantList] [, ] EnumBodyDeclarations }
```

```
EnumConstantList:
  EnumConstant { , EnumConstant }
```

```
EnumConstant:
  { EnumConstantModifier Identifier <ArgumentList> ) [ ClassBody ]
```

为了方便，这里显示了来自 §15.12 的产生：

```
ArgumentList:
  Expression [ , Expression ]
```

枚举常量声明上的注解修饰符的规则在 §9.7.4 和 §9.7.5 中指定。

`EnumConstant` 中的 `Identifier` 可以作为名称来引用枚举常量。

枚举常量的作用域和隐藏在 §6.3 和 §6.4 中指定。

枚举常量可以跟随参数，这些参数会在类初始化期间创建常量时传递给枚举的构造函数。所调用的构造函数使用标准的重载解析规则（§15.12.2）。如果省略了参数，则假设为空列表。

枚举常量的类体隐式定义了一个匿名类（§15.9.5），该类继承自枚举类型。类体受匿名类的常规规则支配。这些类体中声明的实例方法只有在覆盖了枚举类型的可访问方法时才能在枚举类型之外调用（§8.4.4）。

枚举常量的类体声明抽象方法是编译错误。

由于每个枚举常量只有一个实例，当比较两个对象引用时，如果已知至少一个指向枚举常量，则允许使用 `==` 运算符代替 `equals` 方法。

> Enum 中的 `equals` 方法是一个 `final` 方法，它仅仅对其参数调用 `super.equals` 并返回结果，因此执行恒等比较。

### 8.9.2 枚举体声明

除了枚举常量外，枚举声明体还可以包含构造函数和成员声明以及实例和静态初始化器。

```
EnumBodyDeclarations:
  [ClassBodyDeclaration]
```

为了方便，这里显示了来自 §8.1.6 的产生式：

```
ClassBodyDeclaration:
  ClassMemberDeclaration
  InstanceInitializer
  StaticInitializer
  ConstructorDeclaration
```

# 类

## 枚举类型 8.9

```
ClassMemberDeclaration:
FieldDeclaration
MethodDeclaration
ClassDeclaration
InterfaceDeclaration
```



枚举声明体中的任何构造函数或成员声明对枚举类型起的作用，其方式恰好与这些声明存在于普通类声明的体中完全一致，除非另有明确说明。

如果枚举声明中的构造函数声明为 `public` 或 `protected` (§6.6)，则将是一个编译时错误。

如果枚举声明中的构造函数声明包含对父类构造函数的调用语句 (§8.8.7.1)，则将是一个编译时错误。

从枚举类型的构造函数、实例初始化器或实例变量中引用枚举类型的 `static` 字段，将是一个编译时错误，除非该字段是常量变量 (§4.12.4)。

在枚举声明中，没有访问修饰符的构造函数声明为 `private`（私有）。

在没有构造函数声明的枚举声明中，会隐式声明一个默认构造函数。该默认构造函数是 `private`，没有形式参数，且没有 `throws` 子句。

> 在实践中，编译器可能会通过在枚举类型的默认构造函数中声明 `String` 和 `int` 参数来镜像该枚举类型。然而，这些参数并没有被指定为“隐式声明”，因为不同的编译器不需要在构造函数的格式上达成一致。只有枚举类型的编译器知道如何实例化枚举常量；其他编译器可以简单地依赖枚举类型隐式声明的 `public static` 字段 (§8.9.3)，而忽略这些字段是如何初始化的。

如果枚举声明将 `abstract` 方法作为成员，则将是一个编译时错误，除非 `E` 至少有一个枚举常量，且 `E` 的所有枚举常量都具有提供 `m` 的具体实现的类体。

枚举声明中声明终结化器（finalizer）§12.6）将是一个编译时错误。枚举类型的实例永远不能被终结化。

## 示例 8.9.2-1. 枚举体声明

```java
enum Coin {
  PENNY(1), NICKEL(5), DIME(10), QUARTER(25);
  Coin(int value) { this.value = value; }

  private final int value;

  public int value() { return value; }
}
```

每个枚举常量通过构造函数传递的值在字段 `value` 中安排了不同的值。该字段代表美国硬币以“分”为单位的值。注意，对于枚举类型构造函数可以声明的参数没有限制。

## 示例 8.9.2-2. 枚举常量自引用的限制

如果没有对静态访问的限制，看似合理的代码将在运行时由于由于枚举类型中的初始化循环继承而失败（在任何具有“自类型”静态字段的类中都存在循环性）。以下是一个会失败的代码示例：

```java
import java.util.Map;
import java.util.HashMap;

enum Color {
    RED, GREEN, BLUE;
    Color() { colorMap.put(this.toString(), this); }
    static Map<String, Color> colorMap = 
        new HashMap<String, Color>();
}
```

此枚举的静态初始化将抛出 `NullPointerException`，因为在枚举常量构造函数运行时，静态变量 `colorMap` 是未初始化的。上述限制确保了此类代码无法编译。然而，代码可以很容易地重构为正常工作：

```java
import java.util.Map;
import java.util.HashMap;

enum Color {
    RED, GREEN, BLUE;
    static Map<String, Color> colorMap = 
        new HashMap<String, Color>();
    static {
        for (Color c : Color.values()) {
            colorMap.put(c.toString(), c);
        }
    }
}
```

重构后的版本显然是正确的，因为静态初始化是从上下发生的。

## 8.9.3 枚举成员

枚举类型 `E` 的成员包含所有以下内容：

- `E` 声明体中声明的成员。
- 从 `Enum<E>` 继承的成员。
- 对于 `E` 声明体中声明的每个枚举常量 `c`，`E` 隐式声明了一个类型为 `E` 的 public static final 字段，其名称与 `c` 相同。该字段有一个变量初始化器用于实例化 `E` 并将 `c` 的参数传递给为 `E` 选择的构造函数。该字段具有与 `c` 相同的注解（如果有）。

这些字段按照对应枚举量的顺序隐式声明，位于 `E` 声明体中显式声明的任何静态字段之前。

当相应的隐式声明字段被初始化时，即认为该枚举常量被创建。

- 以下隐式声明的方法：

```java
/**
 * 返回一个包含此枚举类型
 * 常量的数组，按照它们声明的顺序排列。此方法可以
 * 如下所示遍历常量：
 * for (E c : E.values()) System.out.println(c);
 * @return 返回一个包含此枚举类型
 * 常量的数组，按照它们声明的顺序排列
 */
public static E[] values();
```

```java
/**
 * 返回具有指定
 * 名称的此类型的枚举常量。
 * 字符串必须精确匹配用于声明此类型中
 * 枚举常量的标识符。（不允许多余的空白字符。）
 * @return 指定名称的枚举常量
 * @throws IllegalArgumentException 如果此枚举类型没有
 * 指定名称的常量
 */
public static E valueOf(String name);
```

由此可见，枚举类型 `E` 的声明不能包含与隐式声明冲突的字段。

枚举类型 `E` 的声明不能包含与隐式声明冲突的字段。

### 8.9.3-1. 遍历枚举常量

```java
public class Test {
  enum Season { WINTER, SUMMER, FALL }
  for (Season s : Season.values()) {
    System.out.println(s);
  }
}
```

该程序输出：

WINTER

SUMMER

FALL

### 8.9.3-2. 枚举常量上的 Switch

`switch` 语句用于模拟对枚举的添加，并打印硬的颜色。

```java
class Test {
    enum Coin { PENNY, NICKEL, DIME, QUARTER }

    static CoinColor color(Coin c) {
        switch (c) {
            case PENNY:
                return CoinColor.COPPER;
            case NICKEL:
                return CoinColor.NICKEL;
            case DIME:
                return CoinColor.SILVER;
            case QUARTER:
                return CoinColor.SILVER;
            default:
                throw new AssertionError("Unknown coin: " + c);
        }
    }

    enum CoinColor { COPPER, NICKEL, SILVER }

    public static void main(String[] args) {
        for (Coin c : Coin.values()) {
            System.out.println(c + " \t" + c.value() + "\t" + color(c));
        }
    }
}
```

该程序输出：

PENNY 1	COPPER

NICKEL 5	NICKEL

DIME 10	SILVER

QUARTER 25	SILVER

### 8.9.3-3. 带有类体的枚举常量

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
}
// 每个计数支持一种算术运算
abstract double eval(double x, double y);

public static void main(String[] args[]) {
    double x = Double.parseDouble(args[0]);
    double y = Double.parseDouble(args[1]);
    for (Operation op : Operation.values()) {
        System.out.println(x + " " + op + " + " + y + " = " + op.eval(x, y));
    }
}
```

类体将行为附加到枚举常量。该程序输出：

Java Operation 2.0 4.0

2.0 PLUS 4.0 = 6.0

2.0 MINUS 4.0 = -2.0

2.0 TIMES 4.0 = 8.0

2.0 DIVIDED_BY 4.0 = 0.5

这比在基础类型（Operation）中使用 `switch` 语句安全得多，因为这种模式消除了忘记为新常量添加行为的可能性（因为枚举声明将导致编译时错误）。

### 8.9.3-4. 多重枚举类型

在以下程序中，扑牌类构建在简单的枚举之上。

```java
import java.util.List;
import java.util.ArrayList;
class Card implements Comparable<Card>,
    java.io.Serializable {
    public enum Rank { DEUCE, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, TEN, JACK, QUEEN, KING, ACE }
}
```

```java
public enum Suit { CLUBS, DIAMONDS, HEARTS, SPADES }

private final Rank rank;

private final Suit suit;

public Rank rank() { return rank; }

public Suit suit() { return suit; }
```

```java
private Card(Rank rank, Suit suit) {
    if (rank == null || suit == null)
        throw new NullPointerException(rank + " , " + suit);
    this.rank = rank;
    this.suit = suit;
}
```

```java
public String toString() { return rank + " of " + suit; }
```

```java
// Primary sort on suit, secondary sort on rank
public int compareTo(Card c) {
    int suitCompare = suit.compareTo(c.suit);
    return (suitCompare == 0) ?
        rank.compareTo(c.rank) :
        suitCompare;
}
```

```java
private static final List<Card> prototypeDeck = 
    new ArrayList<Card>(52);
```

```java
static {
    for (Suit suit : Suit.values())
        for (Rank rank : Rank.values())
            prototypeDeck.add(new Card(rank, suit));
    
}
```

```java
// Returns a new deck
public static List<Card> newDeck() {
    return new ArrayList<Card>(prototypeDeck);
}
```

以下程序演示了 Card 类。它在命令行上接受两个整数参数，代表要发的牌手数量和每手牌的张数。

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
        for (int i=0; i < numHands; i++)
            System.out.println(dealHand(deck, cardsPerHand));
    }
```

```java
/** Returns a new ArrayList consisting of the last n
 * elements of deck, which are removed from deck.
 * The returned list is sorted using the elements'
 * natural ordering.
 */
public static <E extends Comparable<E>> ArrayList<E> dealHand(List<E> deck, int n) {
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
java Deal 4 3

[DEUCE OF CLUBS, SEVEN OF CLUBS, QUEEN OF DIAMONDS]

[NINE OF HEARTS, FIVE OF SPADES, ACE OF SPADES]

[THREE OF HEARTS, SIX OF HEARTS, TEN OF SPADES]

[TEN OF CLUBS, NINE OF DIAMONDS, THREE OF SPADES]
```

293

# 第 9 章

# 接口

接口声明引入了一种新的引用类型，其成员可以是类、接口、常量和方法。该类型没有实例变量，并且通常声明一个或多个 `abstract` 方法；否则，不相关的类可以通过提供对其 `abstract` 方法的实现来实现该接口。接口不能被直接实例化。

嵌套接口是指任何声明出现在另一个类体内的接口。

顶层接口是指不是嵌套接口的接口。

我们区分两种接口——普通接口和注解类型。

本章讨论了所有接口的通用语义——普通接口（包括顶层接口 (§7.6) 和嵌套接口 (§8.5, §9.5)）以及注解类型 (§9.6)。针对特定类型接口的特定细节将在专门讨论这些构造的节中进行讨论。

程序可以使用接口，使得相关类无需共享共同的 `abstract` 超类，或者无需向 `Object` 类添加方法。

一个接口可以被声明为对一个或多个其他接口的*直接扩展*，这意味着它继承了所扩展接口的所有成员类型、实例方法和常量，但它可能重写或隐藏的成员除外。

一个类可以被声明为*直接实现*一个或多个接口，这意味着该类的任何实例都实现了该接口或多个接口所指定的全部 `abstract` 方法。类必须实现实现其直接父类和直接父接口所实现的所有接口。这种（多重）接口继承允许对象支持（多重）共同行为，而无需共享超类。

## 9.1 接口声明

声明类型为接口类型的变量，其值可以是任何实现了指定接口的类实例的引用。仅仅该类恰好实现了接口的所有抽象方法是不够的；该类或其父类之一必须显式声明为实现了该接口，否则该类不被认为实现了该接口。

接口声明指定了一个新的命名引用类型。接口声明有两种类型——普通接口声明和注解类型声明 (§9.6)。

```
InterfaceDeclaration:
    NormalInterfaceDeclaration
    AnnotationTypeDeclaration
```

```
NormalInterfaceDeclaration:
    [InterfaceModifier] interface TypeIdentifier [TypeArguments]
    [ExtendsInterfaces]
```



# 接口声明中的 TypeIdentifier 指定了接口的名称

如果接口与任何包含类具有同名，则将产生编译错误。接口的作用域和遮蔽在 §6.3 中规定。

## 9.1.1 接口修饰符

接口声明可以包含接口修饰符。

```
InterfaceModifier:
    public
    protected
    abstract
    static
```

接口声明的注解修饰符规则规定在 §9.7.4 和 §9.5 中。访问修饰符 `public` 适用于所有接口声明。修饰符 `protected` 仅适用于成员接口。

如果同一个关键字作为接口声明的修饰符出现多次，或者接口声明具有多个访问修饰符 `public`、`private`，则将产生编译错误。

此修饰符已过时，不应在新程序中使用。

## 9.1.2 泛型接口和类型参数

如果接口声明了一个或多个类型变量 (§4.4)，则该接口是泛型的。

这些值被称为接口的类型参数。类型参数部分位于接口名称之后，并用尖括号隔开。

为了方便，这里显示了 §8.1.2 和 §4.4 的产生式：

```
TypeParameters:
    <ParameterList>

TypeParameterList:
    TypeParameter [, TypeParameter]

TypeParameter:
    [TypeParameterModifier] TypeIdentifier [TypeBound]
```

## 9.1.3 父接口和子接口

如果提供了 `extends` 子句，则声明的接口扩展每个其他命名的接口，因此继承了每个其他命名接口的成员类型、实例方法和常量。

这些其他命名的接口是所声明接口的直接父接口。

任何实现该接口的类也被认为实现了该接口所扩展的所有接口。

```
ExtendsInterfaces:
    extends InterfaceTypeList
```

为了方便，这里显示了 §8.1.5 的产生式：

```
InterfaceTypeList:
    InterfaceType [, InterfaceType]
```

接口声明 `extends` 子句中的每个 `InterfaceType` 必须命名一个可访问的接口类型 (§6.6)，否则将产生编译错误。

如果一个 `InterfaceType` 具有参数，它必须表示一个良好的参数化类型 (§4.5)，且其中任何参数都不为通配符类型参数，否则将发生编译时错误。

给定一个（可能是泛型的）接口声明 `I<F1,...,Fn>` (n ≥ 0)，如果接口类型 `I<F1,...,Fn>` 的声明中存在 `extends` 子句，则其直接超接口是该声明中 `extends` 子句列出的类型。

给定一个泛型接口声明 `I<F1,...,Fn>` (n > 0)，参数化类型 `I<T1,...,Tn>` 的直接超接口包括：

- 所有的 `Ti` (1 ≤ i ≤ n)，如果其是一个类型；
- 所有类型 `J<U1,...,Uj>`，其中 `J` 是 `I<F1,...,Fn>` 的直接超接口，且 `θ` 是替换 `[F1=T1, .., Fn=Tn]`。

超接口关系是直接超接口关系的传递闭包。如果满足以下任一条件，则接口 `K` 是接口 `I` 的超接口：

- `K` 是 `I` 的直接超接口。
- 存在接口 `J`，使得 `K` 是 `J` 的超接口，且 `J` 是 `I` 的超接口（递归应用此定义）。

当 `K` 是接口 `I` 的超接口时，称接口 `I` 是接口 `K` 的子接口。

虽然每个类都是 `Object` 类的扩展，但并没有一个单一接口是所有接口的扩展类。

如果类型 `T` 在接口 `I` 的 `extends` 子句中被提及（作为超接口或作为接口名称全限定形式中的限定符），则接口 `I` 依赖于类型 `T`。

如果满足以下任一条件，则接口 `I` 依赖于引用类型 `T`：

- `I` 直接依赖于 `T`；
- `I` 直接依赖于依赖 `T` 的类 `C` (§8.1.5)；
- `I` 直接依赖于依赖 `T` 的接口 `J`（递归应用此定义）。

如果接口依赖于自身，则会导致编译时错误。

如果在运行时（接口加载时）检测到循环定义的接口，则将抛出 `ClassCircularityError` (§12.2.1)。

## 9.1.4 接口体与成员声明

接口体可以声明接口的成员，即字段（§9.3）、方法（§9.4）、类（§9.5）和接口（§9.5）。

```
InterfaceBody:
    { InterfaceMemberDeclaration }

InterfaceMemberDeclaration:
    ConstantDeclaration
    InterfaceMethodDeclaration
    ClassDeclaration
    InterfaceDeclaration
```

在接口类型 $t$ 中声明或由其继承的成员 $m$ 的声明作用域在 §6.3 中有规定。

## 9.2 接口成员

接口类型的成员包括：

- 在接口体中声明的成员 (§9.1.4)。
- 从任何直接超接口继承的成员 (§9.1.3)。
- 如果接口没有直接超接口，则该接口会隐式地声明一个 `public abstract` 成员方法 $m$，其签名为 $s$、返回类型为 $r$ 以及 `throws` 子句为 $\tau$，这对应于 `Object` (§4.3) 中声明的每个具有签名 $s$、返回类型 $r$ 和 `throws` 子句 $\tau$ 的 `public` 实例方法，除非该接口显式声明了具有相同签名、返回类型和兼容 `throws` 子句的 `abstract` 方法。

如果接口显式声明这样的成员 $m$，而该 $m$ 在 `Object` 中被声明为 `final`，则会导致编译时错误。

如果接口显式声明的方法签名与 `Object` 的 `public` 方法重写等效（§8.4.2），但返回类型不同、`throws` 子句不兼容或是 `abstract` 的，则会导致编译时错误。

接口继承其所覆盖的方法和默认方法（§9.4.1）、(iii) 私有方法以及 (iv) 静态方法。

接口类型的字段、方法和成员类型可以具有相同的名称，因为它们被用于不同的上下文，并通过不同的查找程序进行消歧（§6.5）。然而，从风格角度来说，这是不建议的。

## 9.3 字段（常量）声明

```
ConstantDeclaration:
    ConstantModifier UnannType VariableDeclaratorList;

ConstantModifier:
    (one of)
    Annotation
    public
    static
    final
```

关于 `UnannType` 参见 §8.3。为了方便，此处列出了 §4.3 和 §8.3 中的后续产生式：

```
VariableDeclaratorList:
    VariableDeclarator [, VariableDeclarator]

VariableDeclarator:
    VariableDeclaratorId [= VariableInitializer]

VariableDeclaratorId:
    Identifier [Dims]

Dims:
    [Annotation] [ ]

VariableInitializer:
    Expression
    ArrayInitializer
```

接口字段声明中注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。

接口体中的每个字段声明都是隐式的 `public`、`static` 和 `final`。允许对此类字段冗余地指定这些任何或所有修饰符。

如果同一个关键字作为字段声明的修饰符出现多次，则会导致编译时错误。

如果字段声明中出现一个或多个（不同的）字段修饰符，按照习惯（但并非要求），它们出现的顺序与上述 `ConstantModifier` 产生式中所示顺序一致。

如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号对，则字段的声明类型由 `UnannType` 表示，否则由 §10.2 规定。

接口字段声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

接口声明体声明两个同名的字段会导致编译错误。

如果接口声明了某个字段，则该字段的声明会隐藏超接口中所有同名的字段。

一个接口可能继承多个同名的字段。这种情况会导致编译时错误。然而，在接口体内部通过简单名引用该字段会导致编译时错误，因为该引用是歧义的。

### 示例 9.3-1. 歧义的继承字段

任何使用该歧义成员的行为将导致编译时错误。在程序中：

```
interface BaseColors {
    int RED = 1;
    int GREEN = 2;
    int BLUE = 3;
}

interface RainbowColors extends BaseColors {
    int YELLOW = 4;
    int INDIGO = 5;
    int VIOLET = 6;
}

interface PrintColors extends BaseColors {
    int YELLOW = 7;
    int ORANGE = 8;
}

interface LotOfColors extends RainbowColors, PrintColors {
    int FUSCH = 9;
    int VERMILION = 10;
    int CHARTREUSE = 11;
}
```

`LotOfColors` 继承了两个名为 `YELLOW` 的字段。

### 示例 9.3-2. 多次继承的字段

如果一个字段从同一个接口被多次继承（例如该接口及其直接超接口都扩展了声明字段的接口），则只存在一个成员。这种情况本身不会导致编译时错误。

### 9.3.1 接口字段的初始化

字段声明必须具有变量初始化器，否则将发生编译时错误。

初始化器不需要是常量表达式（§15.28）。

如果接口字段的初始化器使用了同一字段或同一接口中后续声明字段的简单名，则会导致编译时错误。

如果在接口字段的初始化器中出现了关键字 `this`（§15.8.3）或 `super`（§15.11.2, §15.12），则会导致编译时错误，除非该发生发生在匿名类体内部（§15.9.5）。

在运行时，初始化器被求值且字段赋值被精确执行一次，即接口初始化时（§12.4.2）。

注意，常量变量（§4.12）的接口字段会在其他接口字段之前初始化。这同样适用于类中的常量静态字段（§8.3.2）。这些字段永远不会被观察到具有默认初始值（§4.12.5），除非通过开发程序。

### 示例 9.3.1-1. 前向引用字段

```
interface Test {
    float f = j;
    int j = 1;
    int k = k + 1;
}
```



该程序会导致两个编译时错误，因为 `j` 在声明之前就被引用了，且因为 `k` 的初始化引用了它本身。

# 9.4 方法声明

```
InterfaceMethodDeclaration:
{InterfaceModifier} MethodHeader MethodBody

InterfaceMethodModifier:
(以下之一)
Annotation public private
abstract default static strictfp
```

为了方便起见，这里展示了 §8.4、§8.4.5 和 §8.4.7 中的以下产生式：

```
MethodHeader:
ResultMethodDeclarator [Throws]
TypeParameters [Annotation] ResultMethodDeclarator [Throws]

Result:
UnannType
void

MethodDeclarator:
Identifier ([ReceiverParameter, ][FormalParameterList]) Dims

MethodBody:
Block
;
```

接口方法声明上的注解修饰符规则规定在 §9.7.4 和 §9.7.5 中。

接口体中的方法可以声明为 `public`（公共）或 `private`（私有）（§6.6）。如果没有给出访问修饰符，该方法默认为 `public`。在接口方法声明中冗余地指定 `public` 修饰符是允许的，但从风格上考虑不建议这样做。

默认方法（default method）是在接口中使用 `default` 修饰符声明的实例方法。它的体始终由一个块（block）表示，为任何实现该接口且未重写该方法的类提供默认实现。默认方法区别于具体方法（§8.4.3.1）（后者在类中声明的），也区别于私有接口方法（后者既不被继承也不被重写）。

接口可以声明静态方法（static methods），调用这些方法不需要引用特定的对象。静态接口方法与默认方法不同，后者是实例方法。

在接口静态方法的头部或体中使用任何周围声明的参数名称，将导致编译时错误。

`strictfp` 修饰符的作用是使默认方法或静态方法体内的所有 `float` 或 `double` 表达式都显式地符合 FP 严格性规则（§15.4）。

缺少 `private`、`default` 或 `static` 修饰符的接口方法默认为 `abstract`（抽象的）。它的体由分号表示，而不是块。对于此类方法声明，冗余地指定 `abstract` 修饰符是允许的，但从风格上考虑不建议这样做。

> 注意，接口方法不能声明为 `protected` 或包访问（package access），也不能使用 `final`、`synchronized` 或 `native` 修饰符。

如果同一种关键字作为接口方法声明的修饰符出现多次，或者接口方法声明具有 `public` 和 `private` 访问修饰符中的多个（§6.6），则会导致编译时错误。

如果接口方法声明具有 `abstract`、`default` 或 `static` 关键字中的多个，则会导致编译时错误。

如果包含 `private` 关键字的接口方法声明也包含 `abstract` 或 `default` 关键字，则会导致编译时错误。接口方法声明同时包含 `private` 和 `static` 是允许的。

如果包含 `abstract` 关键字的接口方法声明也包含 `strictfp` 关键字，则会导致编译时错误。

如果接口体显式声明了两个具有重写等效签名（override-equivalent signatures）的方法（§8.4.2），则会导致编译时错误。然而，接口可以继承多个具有此类签名的抽象方法（§9.4.1）。

接口中声明的方法可以是泛型的（generic）。接口中泛型方法类型参数的规则与类中泛型方法的规则相同（§8.4.4）。

# 9.4.1 继承与重写

接口 `I` 从其直接父接口继承所有的抽象方法和默认方法 `m`，前提是满足以下所有条件：

- `m` 是直接父接口 `J` 或 `I` 的成员。
- `I` 中声明的方法没有其签名是 `m` 签名的子签名（§8.4.2）。
- 不存在方法 `m'`，其作为 `I` 的直接父接口 `S` 的成员（`m'` 不同于 `m`，`S` 也不同于 `S'`），使得 `m'` 重写了方法 `m` 的声明。

注意，方法的重写是基于签名逐个进行的。例如，如果一个接口声明了两个同名的 `public` 方法（§9.4.2），而子接口重写了其中一个，则子接口仍然继承另一个方法。

第三条款防止了子接口重复继承一个已经被其另一个父接口重写的方法。例如，在程序中：

`Right 从 Top 继承 name()，但 Bottom 从 Left 继承 name()。这是因为来自 Left 的 name() 重写了 Top 中 name() 的声明。`

接口不继承其父接口的私有方法或静态方法。

如果接口 `I` 声明了一个私有或静态方法 `m`，且 `m` 的签名是 `I` 的父接口中公共实例方法 `m'` 的签名，且 `m'` 在其他情况下可以被 `I` 中的代码访问，则会发生编译时错误。

> 本质上，接口中的静态方法不能隐藏父接口中的实例方法。这类似于 §8.4.8.2 中的规则，即类中的静态方法不能隐藏父类或父接口中的实例方法。注意，§8.4.8.2 中的规则说的是类“声明或继承了静态方法”，而上面的规则说的是接口“声明了静态方法”，因为接口不能继承静态方法。此外，§8.4.8.2 中的规则允许隐藏父类/父接口中的实例方法和静态方法，而上面的规则仅考虑父接口中的公共实例方法。

同样地，接口中的私有或默认方法不能重写父接口的实例方法（无论是私有的还是公共的）。这与 §8.4.8.1 和 §8.4.8.3 中的规则相似，因为 §8.4.8.1 要求被重写的方法是非私有的，而 §8.4.8.3 要求重写方法是公共的。总结来说，只有公共方法可以被重写，且只能被子接口或实现类重写。

## 9.4.1.1 重写（通过实例方法）

在 `I` 中声明或从 `I` 继承的实例方法 `m_I` 重写来自 `J` 的另一个实例方法 `m_J`，当且仅当满足所有条件：

- `I` 是 `J` 的子接口。
- `I` 不继承 `m_J`。
- `m_I` 的签名是 `m_J` 签名的签名（§8.4.2）。
- `m_J` 是公共的。

`strictfp` 修饰符的存在与否对方法重写规则没有绝对影响。例如，非 FP-strict 方法重写 FP-strict 方法是允许的，FP-strict 方法重写非 FP-strict 方法也是允许的。

> 被重写的默认方法可以通过包含由父接口限定的 `super` 关键字的方法调用表达式（§15.2）来访问。

## 9.4.1.2 要求中的重写

接口方法的返回值与被重写接口方法的返回值之间的关系规定在 §8.4.3 中。

接口方法的 `throws` 子句与被重写接口方法的 `throws` 子句之间的关系规定在 §8.4.3 中。

接口方法的签名与被重写接口方法的签名之间的关系规定在 §8.4.3 中。

接口方法的访问性与被重写接口方法的访问性之间的关系规定在 §8.4.3 中。

如果默认方法与类 `Object` 的非私有方法具有重写等效，则会导致编译时错误，因为实现该接口的类将继承该方法的自身的实现。

禁止将 `Object` 的方法之一声明为默认方法可能令人惊讶。毕竟，存在诸如 `java.util.List` 这样的情况，其中 `toString` 和 `equals` 的行为被精确定义。然而，当考虑到一些更广泛的决策时，理由变得更加清晰：

- 首先，从父类继承的方法允许重写从父接口继承的方法（§8.4.1）。因此，每个实现类都会自动重写接口的 `toString` 默认方法。这是 Java 编程语言长期以来的行为。我们不希望通过默认方法的设计来改变这一点，因为这与允许接口允许的目标冲突。
- 其次，接口不继承 `Object`，而是隐式地声明了许多与 `Object` 相同的方法（§9.2）。因此，在 `Object` 中声明的 `toString` 与在接口中声明的 `toString` 之间没有共同祖先。在最好的情况下，如果两者都是继承的候选，它们可能会发生冲突。解决这个问题将需要类继承树和接口继承树之间进行复杂的混合。
- 第三，在接口中声明 `Object` 方法用例通常假设存在线性的继承层次；该特性无法很好地推广到多继承场景。
- 第四，`Object` 方法是如此基础，以允许任意子部分简单地添加更改其行为的方法似乎是危险的。

然而，接口可以自由定义另一个方法，为重写了 `Object` 方法的类提供行为。例如，`java.util.List` 接口可以声明 `elementString`，根据 `toString` 的约定产生字符串；类中 `toString` 的实现类随后可以将此任务委托给该方法。

## 9.4.1.3 继承具有等效重写签名的方法

接口可能继承多个具有等效重写签名的方法（§8.4.2）。

如果接口继承了一个默认方法，其签名与它继承的另一个方法签名等效重写，则会发生编译错误。（无论另一个方法是抽象方法还是默认方法，情况相同。）

否则，所有继承的方法都是抽象的，且该接口被认为继承了所有方法。

继承的方法中必须有一个方法对于每一个其他继承的方法都是返回类型可替换的，否则将发生编译错误。（在这种情况下，`throws` 子句不会引起错误。）

可能会通过多条路径从接口继承同一个方法声明。这一事实没有引起任何困难，并且本身永远不会导致编译错误。

当一个子接口继承了两个签名匹配的不同默认方法时，这是一种行为冲突。我们会主动检测这种冲突并用错误通知程序员，而不是等到在编译具体类时出现问题。可以通过声明一个新方法来重写并阻止继承所有冲突的方法，从而避免该错误。

同样，当子接口继承了签名匹配的抽象方法和默认方法时，我们会产生一个错误。在这种情况下，可能会给其中一个或另一个优先级——也许我们假设默认方法为抽象方法提供了合理的实现。但这是危险的，因为除了巧合的名称和签名，我们没有理由相信默认方法的行为与抽象方法的契约一致——默认方法在子接口最初开发时可能甚至不存在。在这种情况下，更安全的方法是要求用户主动断言默认实现是合适的（通过重写声明）。

相比之下，类中继承的具体方法的长期以来的行为是，它们会重写接口中声明的抽象方法（见 §8.4.2）。关于潜在违反的论点同样适用于此处，但在此情况下类和接口之间存在固有的不平衡。为了保持类层次结构的独立性，我们倾向于通过简单地赋予具体方法优先级来尽量减少类与接口的冲突。

## 9.4.2 重载

如果接口的两个方法（无论是在同一个接口中声明的，还是被继承的，或者一个声明一个继承）具有相同的名称但具有不同且非等效重写的签名（§8.4.2），则该方法被称为被重载。

这一事实没有引起任何困难，并且本身永远不会导致编译错误。对于具有相同名称但签名不同且非等效重写的两个方法，其返回类型之间或其 `throws` 子句之间没有强制关系。

示例 9.4.2-1. 重载一个抽象方法声明

```java
interface PointInterface {
    void move(int dx, int dy);
}

interface RealPointInterface extends PointInterface {
    void move(float dx, float dy);
    void move(double dx, double dy);
}
```

在接口 `RealPointInterface` 中，名为 `move` 的方法重载三个签名，其中两个是声明的，一个是继承的。任何实现 `RealPointInterface` 的非抽象类必须为所有三个方法签名提供实现。

## 9.4.3 接口方法体

默认方法具有块体。该代码块在类实现接口但未提供方法自己的实现时提供该方法的实现。

私有方法或静态方法也有块体，提供方法的实现。

如果接口方法声明是抽象的（显式或隐式）且具有方法体，则为编译错误。

如果接口方法声明为 `default`、`private` 或 `static`，且以分号作为方法体，则为编译错误。

静态方法的体中尝试使用 `this` 关键字或 `super` 关键字引用当前对象则为编译错误。

方法体中 `return` 语句的规则规定在 §14.17 中。

如果声明方法具有返回类型（§8.4.5），如果方法体可以正常完成（§14.1），则会发生编译错误。

## 9.5 成员类型声明

接口可以包含成员类型声明（§8.5）。

接口体中的每个成员类型声明都是隐式 `public` 且 `static` 的。允许冗余地指定其中一个或两个修饰符。

如果接口中的成员类型声明具有 `protected` 或 `private` 修饰符，则为编译错误。

如果接口中的成员类型声明中关键字 `appears` 出现一次以上，则为编译错误。

如果接口声明了某个成员类型，则该类型的声明将隐藏父接口中的可访问声明。

接口可能继承多个同名的成员类型。这种情况本身不会引起编译错误。然而，在接口体内部通过简单名称引用任何此类类型都将导致编译错误，因为可能会有多条路径从接口继承同一个成员类型声明。在这种情况下，成员类型被认为只继承一次，可以通过简单名称引用。

## 9.6 注解类型

注解类型声明定义了一个注解类型，这是一种特殊的接口。为了区分注解类型和普通接口，`interface` 关键字前面有一个符号 `@`。

```
AnnotationTypeDeclaration:
{InterfaceModifier} @ interface TypeIdentifier AnnotationType
```

注意 `@@` 和关键字 `interface` 是不同的标记。允许在它们之间留空格，但从风格角度考虑不这样做。

注解类型声明的注解修饰符规则规定在 §9.7.4 和 §9.7.5 中。

注解类型声明中的 `TypeIdentifier` 指定注解类型的名称。

如果注解类型与其任何内部类或接口具有相同的简单名称，则为编译错误。

每个注解类型的直接父接口都是 `java.lang.annotation.Annotation`。

> 凭借 `AnnotationTypeDeclaration` 语法，注解类型声明不能是泛型的，且不允许 `extends` 子句。

由于注解类型无法显式声明父类或作为注解类型的子类或父接口，其永远不是注解类型。同样，`java.lang.annotation.Annotation` 本身也不是注解类型。

注解 `type` 从 `java.lang.annotation.Annotation` 继承了几个成员，包括对应于 `Object` 实例方法的隐式声明方法，但这些方法并没有定义注解元素（§9.6.1）。

由于这些方法没有定义注解元素，因此在注解类型中使用它们是违法的（§9.7）。如果没有这样做，我们无法确保元素是注解中可表示的类型，也无法获得访问器方法。

除非在此显式修改，所有适用于普通接口声明的规则都适用于注解类型声明。

## 9.6 注释类型 接口

例如，注解类型与普通类和接口类型共享相同的命名空间；在任何接口声明合法的地方，注解类型声明也是合法的，并且具有相同的作用域和访问权限。

### 9.6.1 注释类型元素

注解类型声明的体可以包含方法声明，每个方法定义了该注解类型的一个元素。注解类型除了其显式声明的方法定义的元素外，没有其他元素。

```
AnnotationTypeBody:
{ AnnotationTypeMemberDeclaration }

AnnotationTypeMemberDeclaration:
  AnnotationTypeElementDeclaration
  ConstantDeclaration
  ClassDeclaration
  InterfaceDeclaration
;
```

```
AnnotationTypeElementDeclaration:
[AnnotationTypeElementModifier] AnnotationType Identifier () [Dims]
[DefaultValue];
```

```
AnnotationTypeElementModifier:
(one of)
Annotation public
abstract
```

根据 `AnnotationTypeElementDeclaration` 产生式，注解类型声明中的方法声明不能有形式参数、类型参数或 `throws` 子句。为了方便起见，此处显示了来自 $4.3 的后续产生式：

根据 `AnnotationTypeElementModifier` 产生式，注解类型声明中的方法声明不能是 `default` 或 `static`。因此，注解类型不能声明与普通接口类型相同类型的方法。请注意，注解类型仍然可能从其隐式超接口 `java.lang.annotation.Annotation` 继承一个默认方法，尽管在 Java SE 11 中并不存在这样的默认方法。

按照惯例，注解类型元素上应该存在的唯一 `AnnotationTypeElementModifiers` 应该是注解（annotations）。

在注解类型中声明的方法返回类型必须是以下类型之一，否则将发生编译错误：

- 基本数据类型（primitive type）
- `String`
- `Class` 或 `Class` 的调用（§4.5）
- 枚举类型（enum type）
- 注释类型
- 数组组件类型为上述类型之一的数组（§10.1）。

此规则排除了具有嵌套数组类型的元素，例如：

```java
@interface Verboten {
  String[][] value();
}
```

返回数组的方法声明允许在空的形式参数列表列表之后放置表示数组的括号对。这种语法是为了兼容 Java 编程语言的早期版本而提供的。强烈建议不要在新代码中使用这种语法。

如果注解类型中声明的任何方法的签名与在 `Object` 类或 `java.lang.annotation.Annotation` 接口中声明的任何 `public protected` 方法的签名重写等，则为编译错误。

如果注解声明 `T` 直接或间接地包含一个类型为 `T` 的元素，则为编译错误。

例如，这种是不合法的：



@interface SelfRef { SelfRef value(); }

这种也是不合法的：

@interface Ping { Pong value(); }

@interface Pong { Ping value(); }

没有元素的注解类型称为标记注解（marker annotation type）。

带有一个元素的注解类型称为单元素注解（single-element annotation type）。

按照惯例，单元素注解类型中唯一元素的名称是 `value`。单元素注解 (§9.7.3) 为这一惯例提供了语言级的支持。

## 9.6 注解类型接口

### 示例 9.6.1-1. 注解类型声明

以下注解类型声明定义了一个具有多个元素的注解类型：

```java
/**
 * 描述导致被注解的 API 元素存在的“增强请求” (RFE)
 */
@interface RequestForEnhancement {
    int id(); // 与 RFE 关联的唯一 ID 数字
    String synopsis(); // RFE 的摘要
    String engineer(); // 实现 RFE 的工程师姓名
    String date(); // RFE 实现的日期
}
```

### 示例 9.6.1-2. 标记注解类型声明

以下注解类型声明定义了一个标记注解：

```java
/**
 * 此类型的注解表示被注解的 API 元素的
 * 规范是初步的，并且可能会发生变化。
 */
@interface Preliminary {}
```

### 示例 9.6.1-3. 单元素注解类型声明

单元素注解类型定义一个名为 `value` 的元素的惯例在以下注解类型声明中得到了说明：

```java
/**
 * 将版权声明与被注解的 API 元素关联。
 */
@interface Copyright {
    String value();
}
```

以下注解类型声明定义了一个单元素注解类型，其唯一元素具有数组类型：

```java
/**
 * 将背书者列表与被注解的类关联。
 */
@interface Endorsers {
    String[] value();
}
```

以下注解类型声明显示了一个 `Class` 类型的元素，其值受有边界通配符（bounded wildcard）的约束：

```java
interface Formatter {
    // 指定一个格式器对被注解的类进行美化打印
    @interface PrettyPrinter {
        Class<? extends Formatter> value();
    }
}
```

以下注解类型声明包含一个类型也是注解类型的元素：

```java
/**
 * 指明被注解的程序元素的作者。
 */
@interface Author {
    Name value();
}

/**
 * 人的姓名。此注解类型的设计并非直接用于
 * 注程序元素，而是为了定义
 * 其他注解类型的元素。
 */
@interface Name {
    String first();
    String last();
}
```

注解类型声明的语法允许除方法声明之外的其他元素声明。例如，人们可能会声明一个嵌套枚举以与注解类型配合使用：

```java
@interface Quality {
    enum Level { BAD, INDIFFERENT, GOOD }
    Level value();
}
```

### 9.6.2 注解类型元素的默认值

注解类型元素可以有一个*默认值*，通过在元素的（空）参数列表后跟随 `default` 关键字和 `ElementName` (§7.1) 来指定。

```
DefaultValue:
    default ElementName
```

如果元素的类型与指定的默认值不匹配 (§7)，则为编译时错误。

默认值不会被编译到注解中，而是在读取注解时动态应用的。因此，更改默认值会影响即使是在更改之前编译的类（假设这些注解缺少该元素的显式值）。

### 示例 9.6.2-1. 带有默认值的注解类型声明

这是来自 §9.6.1 的 `RequestForEnhancement` 注解的：

```java
@interface RequestEnhancement {
    int id(); // 值——必须在注解中指定
    String synopsis(); // 没有默认值——必须在注解中指定
    String engineer() default "[unassigned]";
    String date() default "[unimplemented]";
}
```

### 9.6.3 可重复注解

如果注解类型 `T` 的声明当 `value` 元素包含类型为 `T` 的容器注解时，被元标记了 `@Repeatable` 注解 (§9.6.4.8)，则它是可重复的。

如果满足以下条件，则注解类型 `TC` 是 `T` 的容器注解：

- `TC` 声明了一个返回类型为 `T[]` 的 `value()` 方法。
- `TC` 除 `value` 之外声明的任何方法都有默认值。
- `TC` 的留存时间与 `T` 一致，其中留存通过 `@Retention` 注解显式或隐式地表示 (§9.6.4.2)。具体而言：
  - `TC` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`，则 `T` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`。
  - 如果 `TC` 的留存策略为 `java.lang.annotation.RetentionPolicy.CLASS`，则 `T` 的留存策略为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.SOURCE`。
  - `TC` 的留存策略为 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 `T` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`、`java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME`。

4. $au$ 适用于至少与 $TC$ 相同类型的程序元素类型 (§S9.6.4.1)。
具体而言，$au$ 适用的程序元素类型用集合 $m_1$ 表示，而 $TC$ 适用的程序元素类型用集合 $m_2$ 表示，那么每种类型必须出现在 $m_1$ 中，但例外是：

- 如果 $m_2$ 中的类型是 `java.lang.annotation.ElementType.ANNOTATION_TYPE`，则 `java.lang.annotation.ElementType.ANNOTATION_TYPE` 或 `java.lang.annotation.ElementType.TYPE` [或 `java.lang.annotation.ElementType.USE`] 至少有一个出现在 $m_2$ 中。
- 如果 $m_2$ 中的类型是 `java.lang.annotation.ElementType.TYPE`，则 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 至少有一个出现在 $m_2$ 中。
- 如果 $m_2$ 中的类型是 `java.lang.annotation.ElementType.TYPE_PARAMETER`，则 `java.lang.annotation.ElementType.TYPE_PARAMETER` 或 `java.lang.annotation.ElementType.USE` 至少有一个出现在 $m_2$ 中。

此条款实现了如下项策略：注解类型可能仅在其适用的某些程序元素类型上是可重复的。

5. 如果 $au$ 的声明具有一个对应于 `java.lang.annotation.Documented` 的（元）注解，那么 $TC$ 的声明必须具有一个对应于 `java.lang.annotation.Documented` 的（元）注解。

> 注意，$TC$ 为 `@Documented` 而 $au$ 不为 `@Documented` 是允许的。

6. 如果 $au$ 的声明具有一个对应于 `java.lang.annotation.Inherited` 的（元）注解，那么 $TC$ 的声明必须具有一个对应于 `java.lang.annotation.Inherited` 的（元）注解。

> 注意，$TC$ 为 `@Inherited` 而 $au$ 不为 `@Inherited` 是允许的。

如果一个注解类型用一个 `@Repeatable` 注解标记了（元）注解，且该注解的元素元素指示的类型不是 $au$ 的容器注解类型，则会产生编译错误。

## 示例 9.6.3-1. 格式错误的容器注解类型

考虑以下声明：

```java
import java.lang.annotation.Repeatable;

@Repeatable(FooContainer.class)
@interface Foo { }

// 注解类型
@interface FooContainer { Object[] value(); }
```

编译 `Foo` 声明会产生编译错误：Foo 使用 `@Repeatable` 尝试将 `FooContainer` 指定为其注解类型，但实际上 `FooContainer` 并不是 `Foo` 的注解类型。（`FooContainer.value()` 的返回值不是 `Foo[]`）。

`@Repeatable` 注解不能重复，因此一个重复注解只能指定一个容器注解类型。

允许指定多个注解类型会导致编译时产生不可预期的效果，即在编译时，多个可重复注解类型的注解在逻辑上被替换为相应的容器注解 (§9.7.5)。

一个注解类型最多可以是一个注解类型的容器注解类型。

这隐含于以下要求：如果注解类型 $T$ 的声明指定了一个容器注解类型 $TC$，那么 $TC$ 的 `value()` 方法的返回类型为 $T[]$。

一个注解类型不能指定自身为自身的注解类型。

这隐含于以下要求：容器注解类型的 `value()` 方法。具体来说，如果一个注解类型 $A$ 通过 `@Repeatable` 指定自身为其容器注解类型，那么 $A$ 的 `value()` 方法的返回类型将是 $A[]$；但这会导致编译错误，因为注解类型不能在其元素中引用自身 (§9.6)。更通地说，两个注解不能互相指定为它们的容器注解类型，循环的注解类型声明是非法的。

注解类型 $TC$ 可以是某些注解类型 $T$ 的容器注解类型，同时拥有自己的容器注解类型 $TC'$。也就是说，容器注解类型可以是一个重复注解类型。

## 示例 9.6.3-2. 限制可重复注解的重复位置

一个目标为 `java.lang.annotation.ElementType.TYPE` 的注解，其出现的位置至少与一个类型声明指示目标为 `java.lang.annotation.ElementType.ANNOTATION_TYPE` 的注解一样。例如，给定以下重复注解和容器注解类型的声明：

```java
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;
import java.lang.annotation.Repeatable;

@Target(ElementType.TYPE)
@Repeatable(FooContainer.class)
// 接口
@interface Foo {}

@Target(ElementType.ANNOTATION_TYPE)
@interface FooContainer {
    Foo[] value();
}
```

`@Foo` 可以出现在任何类型声明上，而 `@FooContainer` 只能出现在注解类型声明上。因此，以下注解类型声明是合法的：

```java
@Foo @Foo
@interface Anno {}
```

而以下接口声明是非法的：

```java
@Foo @Foo
interface Int {}
```

更广泛地说，如果 `Foo` 是一个重复注解类型，且 `FooContainer` 是它的容器注解类型，那么：

- 如果 `Foo` 没有 `@Target` 元注解且 `FooContainer` 也没有 `@Target` 元注解，则 `@Foo` 可以在任何支持注解的程序元素上重复。
- 如果 `Foo` 没有 `@Target` 元注解但 `FooContainer` 具有 `@Target` 元注解，则 `@Foo` 只能在出现 `FooContainer` 的程序元素上重复。
- 如果 `Foo` 具有 `@Target` 元注解，则 `FooContainer` 必须限制在 `Foo` 适用的程序元素上。

## 示例 9.6.3-3. 可重复容器注解类型

以下声明是合法的：

```java
import java.lang.annotation.Repeatable;

// Foo: 重复注解类型
@Repeatable(FooContainer.class)
@interface Foo { int value(); }

// FooContainer: Foo 的容器注解类型
// 也是一个重复注解类型
@Repeatable(FooContainerContainer.class)
@interface FooContainer { Foo[] value(); }

// FooContainerContainer: FooContainer 的容器注解类型
@interface FooContainerContainer { FooContainer[] value(); }
```



因此，一个类型本身是容器注解类型的注解是可以重复的：

既是重复又是容器的注解类型受混合重复注解类型注解与容器注解规则的限制（§9.7）。例如，无法在 `@FooContainer` 注解旁边编写多个 `@Foo` 注解，也不可能在 `@FooContainerContainer` 注解旁边编写多个 `@FooContainer` 注解。但是，如果 `FooContainerContainer` 类型本身是可重复的，那么就可以在多个 `@FooContainerContainer` 注解旁边编写多个 `@Foo` 注解。

## 9.6.4 预定义注解类型

Java SE 平台库中预定义了一些注解类型。这些预定义注解中的某些具有特殊的语义。这些语义在本节中指定。本节并不提供此处包含的预定义注解的完整规范；那是相应 API 规范的作用。只有需要 Java 编译器或 Java 虚拟机实现部分特殊行为的语义在本节中指定。

### 9.6.4.1 @Target

类型 `java.lang.annotation.Target` 的注解用于注解类型 $T$ 的声明，以指定 $T$ 适用的上下文。`java.lang.annotation.Target` 只有一个类型为 `java.lang.annotation.ElementType[]` 的元素 `value`，用于指定上下文。

对应 `java.lang.annotation.ElementType.LOCAL_VARIABLE`

共有 16 种类型上下文（§4.11），它们都由 `java.lang.annotation.ElementType` 的枚举常量 `TYPE_USE` 表示。

如果在注解类型 `java.lang.annotation.Target` 的 `value` 元素中同一个枚举常量出现多次，则构成编译时错误。

如果注解类型 `T` 的声明上没有 `java.lang.annotation.Target` 注解，则 `T` 适用于所有声明上下文（类型参数声明除外），但在任何类型上下文中都不适用。

这些语法位置是 Java SE 7 中允许使用注解的语法位置。

### 9.6.4.2 @Retention

注解可能仅存在于源代码中，也可能存在于类或接口的二进制形式中。存在于二进制形式的注解在运行时可能无法通过 Java SE 平台的反射库获取。使用 `java.lang.annotation.Retention` 注解用于选择这些可能性。

如果注解 `a` 对应于类型 `T`，且 `T` 具有一个（元）注解 `m` 对应于 `java.lang.annotation.Retention`，则：

- 如果 `m` 有一个元素的值为 `java.lang.annotation.RetentionPolicy.SOURCE`，则 Java 编译器将确保 `a` 不出现在其所属的类或接口的二进制表示中。

- 如果 `m` 有一个元素的值为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 Java 编译器必须确保 `a` 出现在其所属的类或接口的二进制表示中，除非 `a` 注解的是局部变量声明或注解 Lambda 表达式的形式形参数声明。

在局部变量声明上或在 Lambda 表达式的形式形参数声明上的注解永远不会保留在二进制表示中。相比之下，在局部变量类型或 Lambda 表达式的形式形参数类型上的注解，如果该注解类型提供了合适的保留策略，则保留在二进制表示中。

请注意，一个注解类型被 `@Retention(java.lang.annotation.ElementType.LOCAL_VARIABLE)` 和 `@Retention(java.lang.annotation.RetentionPolicy.CLASS)` 或 `@Retention(java.lang.annotation.RetentionPolicy.RUNTIME)` 元注解标记并不是非法的。

### 9.6.4.3 @Inherited

注解类型 `java.lang.annotation.Inherited` 用于指示类 $c$ 上对应于给定注解类型的注解会被类 $C$ 的子类继承。

### 9.6.4.4 @Override

程序员在意图重写某个方法声明时，偶尔会编写一个重载该方法声明，从而导致细微的问题。`@Override` 注解类型支持对此类问题进行早期检测。

> 经典的例子涉及 `equals` 方法。程序员在以下类 `Foo` 中写了：

```java
public boolean equals(Foo that) { ... }
```

而他们本意是想写：

```java
public boolean equals(Object that) { ... }
```

这是完全合法的，但类 `Foo` 继承了来自 `Object` 的 `equals` 实现，可能会导致某些错误。

如果类型 $au$ 中的方法声明被标记了 `@Override`，但该方法没有重写来自 $au$ 的超父类型中声明的 $au$ 方法（§8.4.1, §9.4.1），或者与 `Object` 的公共方法不是重写等价的（§4.3），则构成错误。

这种行为与 Java SE 5.0 不同，在 5.0 中，如果对未实现的接口使用 `@Override`，则会产生编译错误。

关于 `@Override` 的说明是出于重写公共方法的考虑。考虑以下声明：

```java
class Foo {

    @Override

    public int hashCode() {}

}

interface Bar {

    @Override

    int hashCode();

}
```

注意，一个注解类型被元标记为 `@Retention(java.lang.annotation.ElementType.LOCAL_VARIABLE)` 和 `@Retention(java.lang.annotation.RetentionPolicy.CLASS)` 或 `@Retention(java.lang.annotation.RetentionPolicy.RUNTIME)` 并不是非法的。

### 9.6.4.5 @SuppressWarnings

编译器越来越能够发出非常有用的“lint 式”警告。为了鼓励使用此类警告，应该有一种方法来禁用程序员认为不合适的警告。`@SuppressWarnings` 注解类型支持对 Java 编译器发出的警告进行控制。它定义了一个字符串数组。

如果声明被标记为 `@SuppressWarnings(value = {j, ..., k})`，则 Java 编译器将抑制（即不报告）由 Sj 或 Sk 指定的警告。

Java 语言定义的三个类型的警告使用以下字符串：

- 检查警告（§4.8, §5.1.6, §5.1.9, §8.4.1, §8.4.3, §15.12.4, §15.13.2, §15.27.3）使用 `"unchecked"`。

- 弃用警告（§9.6.4.6）使用 `"deprecation"`。

- 移除警告（§9.6.4.6）使用 `"removal"`。

对于其他类型的警告，编译器供应商应该文档它们支持的字符串。鼓励供应商合作以确保相同的名称在多个编译器中有效。

### 9.6.4.6 @Deprecated

程序员有时被反对使用某些程序元素（模块、类型、字段、方法和构造函数），因为它们是危险的或有更好的替代方案。`@Deprecated` 注解类型允许编译器对这些元素的使用发出警告。

被弃用的程序元素是指声明标记了 `@Deprecated` 的模块、类型、字段或构造函数。程序元素的弃用方式取决于 `forRemoval` 元素的值：

- 如果 `forRemoval` 为 `false`（默认值），则该程序元素是普通弃用的。普通弃用的程序元素并不打算在未来的版本中移除，但程序员仍然应该迁移掉它。

- 如果 `forRemoval` 为 `true`，则该程序元素是终极弃用的。终弃用的程序元素打算在未来的版本中移除。程序员应该停止使用它，否则在升级到新版本时会导致源和二进制不兼容问题（§13.2）。

当在程序元素的声明（无论是显式还是隐式声明）中使用普通弃用的程序元素时，Java 编译器必须产生弃用警告，除非：

- 该用处位于一个本身已被弃用的（无论是普通还是终极弃用的）声明内部；或

- 该用处位于一个标记了抑制弃用警告的声明内部；或

- 该用处和声明都在同一个外层类中；或

- 该用处位于导入该普通弃用类型或成员的导入声明中。

- 该使用位于 `exports` 或 `opens` 指令中（§7.7.2）。

当程序元素的声明（无论显式还是隐式声明）使用了终极废用的程序元素（该元素被重写、被调用或通过名称引用）时，Java 编译器必须产生一个移除警告，除非：

- 该使用位于一个带有注解以消除移除警告的声明中；

- 该使用和声明都在同一个最外类中；

- 该使用位于导入了终极废用类型或成员的 import 声明中。

- 该使用位于 `exports` 或 `opens` 指令中。

> 废用的紧迫性足以，以至于使用终极废用的元素会导致移除警告，即使该元素本身已被废弃，因为无法保证元素在执行时会被移除。要忽略警告并继续使用该元素，程序员必须通过 `@SuppressWarnings` 注解手动确认该风险。

在以下情况下，不会产生废弃或移除警告：

- 使用了局部变量或形式参数（通过名称引用），即使该局部变量或形式参数的声明标记了 `@Deprecated`。

- 使用了包名（通过限定类型名、import 声明或 `exports`/`opens` 指令引用），即使该包的声明标记了 `@Deprecated`。

- 通过限定的 `exports` 或 `opens` 指令使用了模块名，即使该友好模块的声明标记了 `@Deprecated`。

导出或打开包的模块通常由控制该包声明的同一程序员或团队控制。因此，当包被模块声明导出或打开时，对该包声明标记为 `@deprecated` 并发出警告益处甚微。相比之下，一个将包导出或打开给友好模块的模块声明，通常不是由控制该友好模块的同一程序员或团队控制的。仅仅导出或打开包并不会导致模块声明依赖于该友好模块，因此，如果友好模块被废弃，发出警告的价值不大；模块声明的程序员几乎总是希望消除此类警告。

唯一可能引起废弃或移除警告的隐式声明是容器注解（§9.7.5）。具体来说，如果 T 是一个可重复的注解类型，且 TC 是它的容器注解类型，并且 TC 被废弃了，那么重复 `@T` 注解将导致警告。该警告源于隐式的 `@TC` 容器注解。它是强烈不建议在不废弃相应的可重复注解类型的情况下废弃其容器类型。

### 9.6.4.7 @SafeVarargs

具有非可重化元素类型的变长参数（variable arity parameter，§4.7）可能会导致堆污染（§4.12.2）并产生编译时的未检查警告（§5.1.9）。如果变长方法的主体对于该变长参数表现良好，则此类警告将没有参考价值。

`SafeVarargs` 注解类型用于标记方法或构造函数声明，它能防止 Java 编译器对变长方法或构造函数的声明或调用报告未检查警告，而在其他情况下，编译器会因为变长参数具有非可重化元素类型而报告此类警告。

`@SafeVarargs` 注解具有非局部影响，因为它在抑制方法调用处的未检查警告的同时，还抑制了与变长方法本身声明相关的未检查警告（§4.1）。相比之下，`@SuppressWarnings("unchecked")` 注解具有局部影响，因为它只抑制与方法声明相关的未检查警告。

`@SafeVarargs` 的标准目标是类似于 `java.util.Collections.addAll` 的方法，其声明起始于：

```java
public static <T> boolean
addAll(Collection<? T> c, T... elements)
```

变长参数的声明类型为 `T[]`，它是非可重化的。然而，它将元素添加到集合中，这两种操作对于数组来说都是安全的。因此，对于 `java.util.Collections.addAll` 方法调用表达式中的任何编译时未检查警告都是虚假的且没有参考价值的。在方法声明上应用 `@SafeVarargs` 可以防止在方法调用表达式处生成这些警告。

如果固定长度的方法或构造函数声明标记了 `@SafeVarargs` 注解，则会导致编译错误。

如果一个既不是 `static final` 也不是 `private` 的变长方法声明标记了 `@SafeVarargs` 注解，则会导致编译错误。

由于 `@SafeVarargs` 仅适用于静态方法、final 和私有实例方法以及构造函数，因此该注解在发生方法重写的地方不可。注解继承仅适用于类上的注解（不适用于方法、接口或构造函数），因此 `@SafeVarargs` 风格的注解无法通过类中的实例方法或接口传递。

### 9.6.4.8 @Repeatable

`java.lang.annotation.Repeatable` 注解类型用于 T 的声明以指示其容器类型。请注意，T 声明上的 `@Repeatable` 元注解不足以使 T 成为容器类型。对于 TC 被视为 T 的容器类型，有许多格式良好性规则。

### 9.6.4.9 @FunctionalInterface

`FunctionalInterface` 注解类型用于指示接口旨在是功能性的（§9.8）。它有助于及检测接口中出现的不适当方法声明。

由于某些接口偶然具有功能性，因此没有也没有必要对所有功能性接口的声明都标记 `@FunctionalInterface`。

## 9.7 注解

注解是一种将信息与程序结构相关联的标记，但在运行时没有影响。注解表示注解类型的特定调用（§9.6），并通常为该类型的元素提供值。

注解有三种。第一种是最通用的，而其他种类仅仅是第一种的简写。

- Annotation:
  - NormalAnnotation
  - MarkerAnnotation
  - SingleElementAnnotation

## 9.7.1 普通注解

普通注解指定了注解类型的名称，以及可选的逗号分隔的元素-值对。每个值对包含一个与注解类型元素关联的元素值（§9.6.1）。

```
NormalAnnotation:
@ TypeName ( [ElementValuePairList] )

ElementValuePairList:
ElementValuePair (, ElementValuePair)*

ElementValuePair:
Identifier = ElementValue

ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation

ElementValueArrayInitializer:
{ [ElementValueList] [,] }

ElementValueList:
ElementValue (, ElementValue)*
```



# 注解

## 9.7 注解

注意符号 `@` 是一个独立的标记（§3.11）。可以在它与 `TypeName` 之间留空格，但从风格角度来看不建议这样做。

`TypeName` 指定了对应的注解类型。该注解被认为“属于”该类型。

`TypeName` 必须命名可访问的注解类型（§6.6），否则会导致编译错误。

元素-值对中的 `Identifier` 必须是注解类型中元素（即方法）的简单名，否则会导致编译错误。

该方法的返回值定义了元素-值对的元素类型。

如果元素类型是数组类型，则不需要使用大括号来指定元素-值对的元素值。如果元素值不是 `ElementValueArrayInitializer`，则一个其唯一元素与该元素关联的数组值。如果元素值是 `ElementValueArrayInitializer`，则由 `ElementValueArrayInitializer` 所表示的数组值与该元素关联。

如果元素类型与元素值不兼容，则为编译时错误。类型 $\tau$ 与元素值 $v$ 兼容，当且仅当以下情况之一为真时：

- $T$ 是数组类型 $E[]$，
  - 如果 $v$ 是 `ConditionalExpression` 或一个 `Annotation`，则 $v$ 与 $E$ 兼容；或
  - 如果 $v$ 是 `ElementValueArrayInitializer`，则每个元素值 $v$ 都与 $E$ 兼容。

> `ElementValueArrayInitializer` 与普通数组初始化器（§10.6）相似，但 `ElementValueArrayInitializer` 在语法上可以包含作为表达式的注解和嵌套初始化器。然而，嵌套初始化器在 `ElementValueArrayInitializer` 中语义上是不合法的，因为它们在注解声明中永远不会与数组类型的元素兼容（允许嵌套的数组类型）。

- $T$ 不是数组类型，且 $v$ 的类型与 $T$ 赋值兼容（§5.2），且
  - 如果 $T$ 是原始类型或 `String`，则 $v$ 是一个常量表达式（§15.28）。
  - 如果 $T$ 是一个类（Class）或对类的调用（§4.5），则 $v$ 是一个类字面量（§15.8.2）。
  - 如果 $T$ 是枚举类型（§8.9），则 $v$ 是一个枚举常量（§8.9.1）。
  - $V$ 不为 `null`。

注意，如果 $T$ 不是数组类型或注解类型，则元素值必须是 `ConditionalExpression`（§15.25）。使用 `ConditionalExpression` 而不是更通用的产生式如 `Expression` 是一种语法技巧，用于防止赋值表达式作为元素值。由于赋值表达式不是常量表达式，因此它不能作为原始类型或 `String` 类型元素的兼容值。

形式上说，说 `ElementValue` 是 FP 严格的（§15.4）是无效的，因为它可能是一个注解或类字面量。尽管如此，当 `ElementValue` 是常量表达式、常量表达式的数组或其元素值（递归地）被发现是常量表达式时，我们可以非正式地说 `ElementValue` 是 FP 严格的；毕竟，每个常量表达式都是 FP 严格的。

普通注解必须为对应注解类型的每个元素包含一个元素-值对，但具有默认值的元素除外，否则将发生编译时错误。

普通注解可以但并不要求为具有默认值的元素包含元素-值对。

> 按照习惯（尽管不是要求），注解中的元素-值对的呈现顺序与注解类型声明中对应元素的顺序相同。

位于注解类型声明上的注解被称为元注解（meta-annotation）。

类型 $\tau$ 的注解可以作为类型 $\tau$ 自身的声明元注解出现。更一般地说，“注解”关系的传递闭包中的循环引用是允许的。

例如，用类型为 $\tau$ 的元注解标记注解类型 $S$ 的声明，并用类型为 $S$ 的元注解标记 $\tau$ 自身的声明，是合法的。预定义的注解类型包含了若干此类循环引用。

### 示例 9.7.1-1. 普通注解

这是一个使用注解类型 §9.6.1 的普通注解示例：

```java
@RequestForEnhancement(
  id = 2668,
  synopsis = "Provide time functionality",
  engineer = "Mr. Peabody",
  date = "2024/01/01"
)
public static void travelTime(Date destination) { ... }
```

这是一个利用默认值的普通注解示例，使用了注解类型 §9.6.2。

```java
@RequestForEnhancement(
  id = 456,
  synopsis = "Balance the federal budget"
)
public static void balanceBudget() {
  throw new UnsupportedOperation("Not implemented");
}
```

## 9.7.2 标记注解

标记注解是注解类型（§9.6.1）的简写。

**MarkerAnnotation:**
`@TypeName`

它是普通注解的简写：

只要所有元素都有具有默认值（§9.6.2），对带有元素的注解类型使用标记注解就是合法的。

### 示例 9.7.2-1. 标记注解

这是一个使用 §9.6.1 中 `Preliminary` 注解类型的示例：

```java
@Preliminary
public class TimeTravel { ... }
```

## 9.7.3 单元素注解

单元素注解是单元素注解类型（§9.6.1）的简写。

**SingleElementAnnotation:**
`@TypeName(ElementValue)`

它是普通注解的简写：

`@TypeName(value = ElementValue)`

只要有一个元素被命名且其他元素具有默认值，对带有多个元素的注解类型使用单元素注解是合法的。

### 示例 9.7.3-1. 单元素注解

这是一个使用 §9.6.1 中对应注解类型的单元素注解示例：

```java
@Copyright("2002 Systems, Inc.")
public class Thruster { ... }
```

这是一个数组值类型的单元素注解示例：

```java
@Annotations("Children")
public class Lollipop { ... }
```

这是一个省略大括号的数组值类型单元素注解示例：

```java
@Annotations("Level")
public class Karma { ... }
```

这是一个包含枚举类型的单元素注解示例：

```java
@Quality(Quality.GOOD)
public class Quality { ... }
```

这是一个包含普通注解的单元素注解示例：

```java
@Name(first = "Joe", last = "Hacker")
public class Begonia { ... }
```

这是一个使用类类型的单元素注解示例：

```java
@PrettyPrinter(Formatter.class)
public class Petunia { ... }
```

这是一个带有通配符的类型单元素注解示例：

```java
@PrettyPrinter
class Gorgeous { ... }
```

这是一个位于声明内部的单元素注解示例：

```java
@Annotations("Epicurus")
public class Widdle { ... }
```

这是一个位于类型左的单元素注解示例：

```java
@C int A[] @B[] f; // 这里的法的
```

## 9.7.4 注解出现的位置

声明注解是应用于声明的注解，且其类型在声明上下文（§9.6.4）中被表示；或者是应用于类、接口、枚举类型或类型参数声明的注解，其所有者类型在类型上下（§4.11）。

类型注解是应用于类型（或类型的任何部分）的注解，其所有者类型在类型上下。

例如，给定字段声明：

```java
@Foo int f;
```

`@Foo` 是 `f` 的声明注解，元注解为 `@Target(ElementType.FIELD)`，也是 `int f` 的类型注解，元注解为 `@Target(ElementType.TYPE_USE)`。`Foo` 可以是声明注解又是类型注解。

类型注解可以应用于数组类型或其任何组件类型（§10.1）。例如，假设 `A`、`B` 和 `C` 是元注解为 `@Target(ElementType.TYPE_USE)` 的注解类型，给定字段声明：

```java
@C int A[] @B[] f;
```

`@A` 应用于数组类型 `[]`，`@B` 应用于组件类型 `int[]`，而 `@C` 应用于元素类型 `int`。这种语法的一个重要属性是，在仅数组层数不同的声明中，类型左侧的注解指向同一个类型。例如，在以下声明中 `@C` 都应用于类型 `int`：

```java
@C int f;
@C int[] f;
@C int[][] f;
```

按照习惯（尽管不是要求），将声明写在所有修饰符之前，并将注解紧接在所属的类型之前。

注解可能出现在程序的某个语法位置，该位置可以合理地应用于声明、类型或两者。这可以发生在任何一个修饰符紧接在被声明实体类型之前的五个声明上下文中：

- 方法声明（包括注解类型的元素）
- 构造函数声明
- 字段声明（包括枚举常量）
- 形式化参数和异常参数声明
- 局部变量声明（包括 `for` 语句中的循环变量和 `try-with-resources` 语句中的资源变量）

如果注解的类型在与声明对应的声明上下文中*且*在类型上下文中都是适用的，则该注解被认为同时适用于该声明以及距离注解最近的类型。

在上述的第二种和第三种情况下，距离注解*最近*的类型按如下方式确定：

- 如果注解出现在 `void` 方法声明或使用 `var` 的局部变量声明（§14.4, §14.14.2, §14.20.3）之前，则没有最近的类型。如果该注解的类型被认为*仅*适用于距离注解最近的类型，则会发生编译时错误。
- 如果注解出现在构造函数声明之前，则最近的类型是新构造对象的类型。新构造对象的类型是紧邻该构造函数声明的类型的完全限定名。在该完全限定名中，注解适用于构造函数声明所指示的简单类型名称。
- 在所有其他情况下，最近的类型是源代码中为被声明实体编写的类型；如果该类型是数组类型，则元素被认为距离注解最近。

> 例如，字段声明 `@Foo static String f`；距离 `@Foo` 最近的类型是 `String`。（如果字段的类型被写为 `java.lang.String`，那么 `java.lang.String` 就是距离 `@Foo` 最近的类型，且后续规则将禁止注解应用于包名 `java.lang`。）在泛型方法声明 `<T> int[] m() {...}` 中，为声明实体编写的类型是 `int[]`，因此 `@Foo` 适用于元素类型。

不使用 `var` 的局部声明与 lambda 表达式的形式参数声明相似，两者都允许在源代码中使用声明注解和类型，但只有类型可以存储在 `class` 文件中。

如果注解 $\tau$ 不适用于以下项的修饰符，则为编译时错误：

- 模块声明，但 $\tau$ 不适用于模块声明。
- 包声明，但 $\tau$ 不适用于包声明。
- 类、接口或枚举声明，但 $\tau$ 不适用于类型声明或类型上下文；或者注解类型声明，$\tau$ 不适用于注解类型声明、类型声明或类型上下文。
- 方法声明（包括注解类型的元素），但 $\tau$ 不适用于方法声明或类型上下文。
- 构造函数声明，但 $\tau$ 不适用于构造函数声明或类型上下文。
- 泛型、接口、方法或构造函数的类型参数声明，但 $\tau$ 不适用于类型参数声明或类型上下文。
- 字段声明（包括枚举常量），但 $\tau$ 不适用于字段声明或类型上下文。
- 形式参数或异常参数声明，但 $\tau$ 不适用于形式参数、异常参数声明或类型上下文。
- 接收参数，但 $\tau$ 不适用于类型上下文。
- 局部变量声明（包括 `for` 语句的循环变量或 `try-with-resources` 语句的资源变量），但 $\tau$ 不适用于局部变量声明或类型上下文。

如果满足以下两个条件，则类型注解是允许：

- 距离注解最近的简单名称被分类为类型名（`TypeName`），而非包名（`PackageName`）。
- 如果距离注解最近的简单名称后面跟着 `.` 以及另一个 `TypeName`——即注解以 `@Foo T.U` 的形式出现——那么 `U` 表示 `T` 的一个内部类。

> 第二句背后的直觉是，如果 `Outer.this` 位于由 `Outer` 包围的嵌套类中，那么 `Outer` 可以被注解，因为它代表了运行时对象的类型。另一方面，如果 `Outer.this` 是非法的，是因为它所在的类在运行时没有对 `Outer` 的包围——那么 `Outer` 可能不可被注解，因为它在逻辑上只是一个名称，是完全限定类型名中包名组件的一部分。

例如，在以下程序中，在 `B` 的体中编写 `A.this`，因为 `B` 没有词法上包围的实例（§8.5.1）。因此，无法在类型 `A, B` 中将 `@Foo` 应用于 `A`，因为 `A` 在逻辑上只是一个名称，而不是一个类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}

class Test {
    class A {
        static class B { }
    }
    @Foo A.B x; // Illegal
}
```

另一方面，在以下程序中，可以在 `D` 的体中编写 `C.this`。因此，可以在类型 `C.D` 中将 `@Foo` 应用于 `C`，因为 `C` 代表了运行时某个对象的类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}
class Test {
    static class C {
        class D {}
    }
    @Foo C.D x; // Legal
}
```

最后，第二个类在限定类型中只只深了一层。这是因为静态类可能只能嵌套在顶层类或另一个静态嵌套类中。无法写出如下嵌套：

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}
class Test {
    class E {
        class F {
            static class G { }
        }
    }
    @Foo E.F x; 
}
```

假设这种嵌套是合法的。在字段 `x` 的类型中，`E` 和 `F` 在逻辑上是修饰 `G` 的名称，因此 `E.this` 在 `G` 中是非法的。然而，从技术上讲，`@Foo` 对于 `E` 是允许的，因为 `F` 是内部类；但由于嵌套本身是非法的。

如果类型为 `T` 的注解适用于类型上下文中的类型最外层，且 `T` 不适用于类型上下文或声明上下文（如果有）的相同语法位置，则为编译时错误。

如果类型为 `T` 的注解适用于类型上下文中的类型部分（即不是最外层），且 `T` 不适用于类型上下文，则为编译时错误。

如果注解 $\tau$ 适用于类型上下文中的类型（或类型的部分），且 $\tau$ 适用于类型上下文，但注解是不允许的。

例如，假设有一个仅标记了 `@Target(ElementType.TYPE_USE)` 的注解 `TA`。`@TA java.lang.Object` 和 `java.@TA Object` 是非法的，因为 `TA` 的名称被分类为包。另一方面，`java.lang.@TA Object` 是合法的。

注意非法术语是“无处不在”的；对包名的禁止广泛适用于：类型上下文，例如 `class ... extends @TA java.lang.Object`，以及既是声明上下文又是类型上下文的位置，例如字段 `@TA java.lang.Object f`；类、包没有可以注解类型的纯声明上下文，使用简单名称）。

如果 `TA` 还标记了 `@Target(ElementType.FIELD)`，那么在既是声明上下文又是类型上下文的位置，`@TA java.lang.Object` 是合法的；此处，`@TA` 被认为适用于 `f` 的声明（而不是类型 `java.lang.Object`），因为 `TA` 适用于字段声明上下文。

## 9.7.5 同一类型的多个注解

如果在声明上下文或类型上下文中出现了同一类型 $\tau$ 的多个注解，则为编译时错误，除非 $\tau$ 是可重复的（§9.6.3）且 $\tau$ 及其包含的类型适用于声明上下文或类型上下文（§9.6.4.1）。

同一类型的多个注解连续出现是习惯，但并非强制。

如果声明上下文或类型上下文具有可重复注解类型 $\tau$ 的多个注解，则该上下文似乎没有显式声明类型 $\tau$ 的注解，而是隐式声明了包含类型 $\tau$。

隐式声明的注解称为容器注解，在文中出现的多个 $\tau$ 注解称为基础注解。容器注解的（数组类型）值元素是所有按照它们在文中从左到右出现的顺序排列的基础注解。

如果在声明上下文或类型上下文中存在可重复注解类型的多个注解，且存在任何该类型包含类型的注解，则为编译时错误。

换句话说，如果一个注解的类型与其容器的注解类型相同，则是不允许重复注解的。这禁止了晦涩的代码：

```java
@Foo(0) @Foo(1) @FooContainer((@Foo(2)))
class A { }
```



如果这是合法的，则需要多层嵌套：首先，类型为 `Foo` 的注解将包含在一个隐式声明的 `FooContainer` 类型注解中，然后该注解和显式声明的 `FooContainer` 类型注解将再次包含在另一个隐式声明的注解中。对于 Java 编程语言的设计者来说，这种复杂性是不受欢迎的。另一种方法是将 `Foo` 的注解处理为就像它们在显式的 `@FooContainer` 注解中与 `@Foo(2)` 并列一样，这也是不可接受的，因为可能会改变反射程序解释 `@FooContainer` 注解的方式。

如果在声明上下文或类型上下文中，存在一个可重复注解类型 `T` 的注解和多个容器注解类型 `T` 的注解，则会导致编译错误。

此规则旨在允许以下代码：

```
@Foo(1) @FooContainer((@Foo(2)))

class A { }
```

由于只有一个可重复注解类型 `Foo` 的注解，如果 `FooContainer` 是 `Foo` 的容器注解类型，则不会隐式声明容器注解。然而，重复 `FooContainer` 注解，例如：

```
@Foo(1) @FooContainer((@Foo(2))) @FooContainer((@Foo(3)))

class A { }
```

即使 `FooContainer` 本身具有其自身的容器注解类型且是重复的，这也是被禁止的。当存在底层可重复类型的注解时，再去重复其本身就是容器的注解是晦涩的。

## 9.8 函数式接口

函数式接口是一个仅有一个抽象方法（除 `Object` 类的方法外）的接口，因此它代表了一个单一的函数契约。“单一”方法可能以多个具有继承自父接口的签名的抽象方法的形式存在；在这种情况下，这些继承的方法在逻辑上代表一个单一方法。

对于接口 `T`，令 `M` 为 `T` 成员的抽象方法集合，且这些方法的签名与 `Object` 类的任何公共实例方法的签名不同（见 §4.3.2）。那么，如果 `M` 中存在方法 `m` 使得以下两个条件均成立，则 `T` 是一个函数式接口：

- `m` 的签名是 `M` 中每个方法签名的子签名（见 §8.4.2）。
- `m` 对于 `M` 中的每个方法都是返回类型可替换的（见 §8.4.5）。

除了通过声明和实例化类来创建接口实例的通常过程（见 §15.9）外，函数式接口的实例还可以通过方法引用和 lambda 表达式创建（§15.13, §15.27）。

函数式接口的定义排除了接口中也是公共方法的方法，例如 `java.util.Comparator<T> int compare(T,T)`。另一个 `boolean equals(Object)` 是一个 `abstract` 方法的显式声明，否则该方法将在接口中隐式声明（见 §9.2）并由实现该接口的每个类自动实现。

注意，如果 `Object` 的非公共方法（如 `clone()`）在接口中声明为 `public`，则它们不会由实现该接口的每个类自动实现。从 `Object` 继承的实现是 `protected` 的，而接口是 `public` 的，因此实现接口的唯一方法是类用 `public` 方法重写非公共的 `Object` 方法。

### 示例 9.8-1. 函数式接口

函数式接口的一个简单示例是：

```
interface Runnable {

    void run();

}
```

以下接口不是函数式的，因为它没有声明任何不属于 `Object` 成员的内容：

```
interface NonFunc {

    boolean equals(Object obj);

}
```

然而，它的子接口可以通过声明一个不是 `Object` 成员的 `abstract` 方法来成为函数式：

```
interface Func extends NonFunc {

    int compare(String o1, String o2);

}
```

同样，众名的接口 `java.util.Comparator<T>` 是函数式的，因为它有一个非 `Object` 的 `abstract` 方法：

```
interface Comparator<T> {

    boolean equals(Object obj);

    int compare(T o1, T o2);

}
```

以下接口不是函数式的，因为它不只声明了一个不是 `Object` 成员的抽象方法，而是声明了两个不是 `Object` 公共方法的抽象方法：

```
interface Foo {

    int m();

    Object clone();

}
```

### 示例 9.8-2. 函数式接口与擦除

在以下层次结构中，`Z` 是一个函数式接口，因为它继承了两个不是 `Object` 成员的抽象方法，它们具有相同的签名，且继承的方法在逻辑上代表一个单一方法：

```
interface X { int m(Iterable<String> arg); }

interface Y { int m(Iterable<String> arg); }

interface Z extends X, Y { }
```

同样，在以下接口层次结构中 `Z` 是一个函数式接口，`Y.m` 是 `X.m` 的子签名，并且对于 `X.m` 是返回类型可替换的：

```
interface X { int m(Iterable<String> arg); }

interface Y { int m(Iterable<String> arg); }

interface Z extends X, Y { }
```

函数式接口的定义尊重这样一个事实：接口不能拥有两个既不是彼此的签名又具有相同擦除（9.4.1.2）的成员。因此，在 `Z` 导致编译错误的三个接口层次结构中，`Z` 不是函数式接口（因为它的没有任何抽象成员是所有其他成员的子签名）：

```
interface X { int m(Iterable<String> arg); }

interface Y { int m(Iterable<String> arg); }

interface Z extends X, Y { }
```

# 第 10 章 数组

## 10.1 数组类型

数组类型用于声明和强制转换表达式 (§15.16)。

数组类型写为元素类型的名称，后跟若干对空方括号 `[]`。括号对的数量表示数组嵌套的深度。

数组类型中的每对括号都可以由类型注解 (§9.7.4) 进行标注。一个注解适用于紧随其后的括号对（或在可变长度参数声明中的省略号）。

数组的元素类型可以是任何类型，无论是原始类型还是引用类型。特别是：

- 允许以接口类型作为元素类型的数组。
  此类数组的元素值可以是 `null` 引用或实现该接口的任何类型的实例。
- 允许以抽象类类型作为元素类型的数组。
  此类数组的元素值可以是 `null` 引用或该抽象类中本身不是抽象类的任何子类的实例。

数组的长度不是其类型的一部分。

数组类型的超类型规定在 §4.10.3。

> 数组类型的超类型与子类关系不同。根据 §4.10.3，`Integer[]` 的直接超类型是 `Number[]`，但根据 `Integer[]` 的 `Class` 对象 (§10.8)，`Integer[]` 的直接父类是 `Object`。这在实践中并不重要，因为 `Object` 是所有数组类型的超类型。

## 10.2 数组变量

数组类型的变量持有指向对象的引用。声明数组类型的变量不会创建数组对象，也不会为数组组件分配空间；它只创建变量本身，该变量可以包含指向数组的引用。然而，声明器的初始化器 `var` (§8.3, §9.3, §14.4.1) 可能会创建一个数组，该引用随后成为变量的初始值。

### 示例 10.2-1. 数组变量的声明

```
int[] ai;                       // int 数组

short[] as;                    // short 数组

short s;                        // 标量 short

short as[];                     // short 数组数组

Object[] ac;                  // Object 数组

Object otherAo[];             // Object 数组

Collection<?>[] ca;           // 未知类型 Collection 的数组
```

上述声明并没有创建数组对象。以下是创建数组对象的数组变量声明示例：

```
Exception[] ae = new Exception[3];

Object[] ao = new Exception[2][3];

int[] factorial = { 1, 1, 2, 6, 24, 120, 720, 5040 };

char[] ac = { 'n', 'o', 't', ' ', 'a', ' ',
              'S', 't', 'r', 'i', 'n', 'g', '' };

String[] aas = { "array", "of", "String", '' };
```



变量的类型取决于变量声明开始处、变量的声明器或局部变量（§8.3, §8.4.1, §9.3, §9.4, §14.4.1）中可能出现的括号对。

## 10.5 数组存储异常

该程序产生输出：

```
5050
```

该程序声明了一个类型为 `int` 的变量 `ia`，即 `int[]`。变量 `ia` 被初始化为指向新创建的数组对象的引用，该对象由数组创建表达式（§15.10.1）创建。数组创建表达式指定数组应具有 101 个组件。可以使用字段 `length` 获取数组的长度，所示。该程序用从 0 到 100 的整数填充数组，对这些整数求和并打印结果。

数组必须通过 `int` 值进行索引；`short`、`byte` 或 `char` 值也可以用作索引值，因为它们会经过一元数值提升（§5.6.1）并变为 `int` 值。

尝试使用 `long` 类型索引值访问数组组件会导致编译时错误。

所有的数组访问都在运行时进行检查；尝试使用小于零或大于等于数组长度的索引会导致抛出 `ArrayOutOfBoundsException`（§15.10.4）。

### 10.5 数组存储异常

对于类型为 `A[]` 的数组（其中 `A` 是引用类型），对数组组件的赋值会在运行时进行检查，以确保所赋值的值可以赋值给该组件。

如果所赋值值的类型与组件类型不兼容赋值兼容（§5.2），则会抛出 `ArrayStoreException`。

> 如果数组的组件类型不是可重化的（§4.7），Java 虚拟机将无法执行前节所述的存储检查。这就是为什么禁止使用非可重化元素的数组创建表达式（§15.10.1）。可以声明一个元素类型为非可重化的数组类型变量，但将数组创建表达式的结果赋值给该变量将会导致未检查的警告（§5.1.9）。

**示例 10.5-1. ArrayStoreException**

```java
class Point { int x, y; }

class ColoredPoint extends Point { int color; }

class Test {
    public static void main(String[] args) {
        ColoredPoint[] cpa = new ColoredPoint[10];
        Point[] pa = cpa;
        System.out.println(pa[1] == null);
        try {
            pa[0] = new ColoredPoint();
        } catch (ArrayStoreException e) {
            System.out.println(e);
        }
    }
}
```

该程序输出：

```
true
java.lang.ArrayStoreException: Point
```

变量 `pa` 的类型为 `Point[]`，变量 `cpa` 的值是对类型 `ColoredPoint[]` 对象的引用。`ColoredPoint` 可以赋值给 `Point`；因此，`cpa` 的值可以赋值给 `pa`。

对 `pa` 的引用（例如测试 `pa[1]` 是否为 `null`）不会导致运行时错误。这是因为类型 `ColoredPoint[]` 的元素是 `ColoredPoint`，每个 `ColoredPoint` 都可以代表 `Point`，因为 `Point` 是 `ColoredPoint` 的超类。

另一方面，对数组 `pa` 的赋值会导致运行时错误。在编译时，会对对 `pa` 元素的赋值进行检查，以确保赋值的值是 `Point`。由于 `pa` 持有一个指向 `ColoredPoint` 数组的引用，只有当运行时赋值值的类型更具体地是 `ColoredPoint` 时，赋值才有效。

Java 虚拟机在运行时检查此类情况以确保赋值是有效的；如果不是，则抛出 `ArrayStoreException`。

## 10.6 数组初始化

数组初始化器可以在字段声明（§8.3, §9.3）或局部变量声明（§14.4）中指定，或者作为数组创建表达式的一部分（§15.10.1），用于创建数组并提供初始值。

```
ArrayInitializer:
    { {VariableInitializerList} [, , ] }

VariableInitializerList:
    VariableInitializer (, VariableInitializer )

VariableInitializer:
    Expression
    ArrayInitializer
```

数组初始化器写为由逗号分隔的表达式列表，并括在大括号 `{` 和 `}` 中。

数组初始化器的最后一个表达式之后可以出现尾随逗号，它会被忽略。

每个变量初始化器必须与数组的组件类型赋值兼容（§5.2），否则会发生编译时错误。

如果被初始化数组的组件类型不是可重化的（§4.7），则为编译时错误。

要构造的数组长度等于紧挨在数组初始化器大括号内的变量初始化器的数量。为该长度的任何数组分配空间。如果没有足够的空间分配数组，则数组初始化器的求值通过抛出 `OutOfMemoryError` 异常终止。否则，将创建一个指定长度的一维数组，并将数组的每个组件初始化为其默认值（§4.12.5）。

紧挨在数组初始化器大括号内的变量初始化器按照它们在源代码中出现的顺序从左到右执行。第 $n$ 个变量初始化器指定第 $n-1$ 个数组组件的值。如果变量初始化器的执行因相同原因异常终止，则数组初始化器的执行异常终止。如果所有初始化表达式都正常完成，则数组初始化器正常完成，并带有新初始化数组的值。

如果组件类型是数组类型，则变量初始化器本身可以是一个数组；即初始化器可以是嵌套的。在这种情况下，嵌套数组构造的执行创建一个数组对象并将其赋值给组件。

**示例 10.6-1. Array Initializers**

```java
class Test {
    public static void main(String[] args) {
        int[][] ia = {{1}, {2}, null};
        for (int[] ea : ia) {
            System.out.println(ea);
        }
    }
}
```

该程序输出：

```
1
2
```

## 10.8 数组的类对象

每个数组都有一个关联的类对象，与所有具有相同组件类型的数组共享。

尽管数组类型不是类，但每个数组的类对象表现就像：

- 每一个数组类型的直接父类都是 `Object`。
- 每一个数组类型都实现了 `Cloneable` 和 `java.io.Serializable` 接口。

**示例 10.8-1. 数组的 Class 对象**

```java
class Test1 {
    public static void main(String[] args) {
        int[] ia = new int[3];
        System.out.println(ia.getClass().getSuperclass());
        System.out.println(ia.getClass().getInterfaces());
        for (Class<?> c : ia.getClass().getInterfaces())
            System.out.println("Superinterface: " + c);
    }
}
```

该程序产生以下输出：

```
class I
class java.lang.Object
Superinterface: interface java.lang.Cloneable
Superinterface: interface java.io.Serializable
```

其中字符串 "I" 是组件类型为 `int` 的 Class 对象 "array" 的运行时类型签名。

**示例 10.8-2. 共享数组 Class 对象**

```java
class Test2 {
    public static void main(String[] args) {
        int[] ia = new int[3];
        int[] ib = new int[6];
        System.out.println(ia.getClass() == ib.getClass());
        System.out.println(ia.getClass() == ia.getClass());
    }
}
```

该程序产生以下输出：

```
true
true
```



虽然 `ia` 和 `ib` 指向不同的数组，但 `Class` 对象的比较结果表明，所有类型为 `int` 的数组都是相同数组类型（即 `int[]`）的实例。

## 10.9 字符数组不是字符串

在 Java 编程语言中，与 C 不同，`char` 数组不是 `String`，`String` 或 `char` 数组都不是以 `'\u0000'`（NUL 字符）终止的。

`String` 对象是不可变的，也就是说它的内容永远不会改变，而 `char` 数组具有可变的元素。

`String` 类的 `toCharArray()` 方法返回一个字符数组，该数组包含与 `String` 相同的字符序列。`StringBuffer` 类在可变的字符数组上实现了很有用的方法。

# 第 11 章 异常

当程序违反 Java 编程语言的语义约束时，Java 虚拟机会将此错误作为异常信号给程序。

此类违规的示例是尝试访问数组范围外的索引。某些编程语言及其实现通过预先终止程序来对此类错误做出反应；而编程语言允许实现以任意或不可预测的方式做出反应。这两种方法都不与 Java SE 平台的设计目标兼容：即提供移植性和健壮性。

相反，Java 编程语言规定，当违反语义约束时将抛出一个异常，并导致控制权从异常发生点到程序员可以指定的点发生非局部转移。

异常被认为是从其发生点被*抛出*（thrown）的，并是在转移到的点点被*捕获*（caught）的。

程序也可以使用 `throw` 语句（§14.18）显式地抛出异常。

显式使用 `throw` 语句为通过返回“奇特值”（funny values）来处理错误条件的旧风格（例如在通常期望负值时返回整数值 -1）提供了一种替代方案。经验表明，调用者往往会忽略或不检查这些“奇特值”，导致程序不健壮、表现出不良行为或二者兼有。

每个异常都由 `Throwable` 类或其一个子类的实例表示（§11.1）。此类对象可以用于从异常发生点携带信息到捕获它的处理程序。处理器通过 `try` 语句的 `catch` 子句建立（§14.20）。

## 异常的种类和原因

在抛出异常的过程中，Java 虚拟机会突然完成当前线程中已开始但未执行的任何表达式、语句、方法和构造函数调用、初始化器以及字段初始化异常。此过程一直持续，直到找到一个处理器，该处理器通过命名异常的类或异常类的父类来指示它处理该特定异常（§11.2）。如果没有找到这样的处理器，则异常可能由未捕获异常处理层次结构中的一个（§11.3）处理——因此，尽一切避免让异常未被处理。

Java SE 平台的异常机制与它的同步模型（§17.1）集成，因此监视器会在同步语句（§14.19）结束时以及在同步方法调用（§8.4.3.6, §15.12）异常结束时解锁。

## 11.1 异常的种类和原因

### 11.1.1 异常的种类

异常由 `Throwable` 类（`Object` 的直接子类）或其一个子类的实例表示。

`Throwable` 及其所有子类共同构成异常类。

`Exception` 和 `Error` 类是 `Throwable` 的直接子类：

* `Exception` 是所有异常的子类，普通程序可能希望从这些异常中恢复。

`RuntimeException` 类是 `Exception` 的直接子类。`RuntimeException` 是在表达式求值期间由于许多原因抛出的所有异常的子类，但可能从中这些中恢复。

`RuntimeException` 及其所有子类共同构成运行时异常类。

* `Error` 是所有异常的子类，普通程序通常不会从这些异常中恢复。

`Error` 及其所有子类共同构成错误类。

未检查异常（unchecked exceptions）是运行时异常类。

检查异常（checked exceptions）是 `Exception` 的所有其他子类。

### 11.1.2 异常的原因

异常的抛出有三个原因之一：

* 一个 `throw` 语句（§14.18）
* 同步检测到异常状态，即：
    * 表达式求值违反了 Java 语言的语义，例如整数除以零
    * 在加载、链接或初始化程序部分时发生错误
    * 内部错误或资源限制阻止了 Java 虚拟机实现 Java 语言的语义；在这种情况下，将抛出一个 `Throwable` 子类的实例。

### 11.1.3 异步异常

大多数异常是由于其发生所在线程的操作而同步发生的，并且发生在程序指定的某点。相比之下，异步异常是可能在执行的任何点发生的异常。

异步异常仅由于以下结果发生：

* 调用 `Thread` 类或 `Thread` 类的（已废用的）`stop()` 方法。（已废用的）`stop()` 方法可能被一个线程调用以影响另一个线程或线程组中的所有线程。它们是异步的，因为它们可能发生在其他线程或线程执行的任何点。
* 内部错误或资源限制阻止了 Java 虚拟机实现 Java 语言的语义。在这种情况下，抛出的异步异常是 `VirtualMachineError` 的实例。

注意，`StackOverflowError` 作为 `VirtualMachineError` 的子类，可能会通过方法调用（15.12.4.5）同步抛出，也可能通过原生方法调用或 Java 资源限制异步抛出。同样，`OutOfMemoryError` 作为 `VirtualMachineError` 的另一个子类，可能会在类实例创建（15.9.4, 12.5）、数组创建（15.10.2, 12.4.2）和装箱转换（5.1.7）期间同步抛出，也可能异步抛出。

Java SE 平台在抛出异步异常之前会执行少量有限的异常处理。

> 异步异常罕见，但为了生成高质量的代码，正确理解其语义是必要的。

## 11.2 异常的编译时检查

Java 语言要求程序必须包含对检查异常的处理器，这些异常可能由方法或构造函数的执行产生（§8.4.6, §8.8.5）。这种对异常处理器存在的编译时检查旨在减少未被妥善处理的异常数量。对于每个作为可能结果的检查异常，方法或构造函数的 `throws` 子句必须提及该异常的类或该异常类的一个的一个父类（§11.2.3）。

命名的检查异常类（§11.1.1）是方法或构造函数实现者与使用者之间约的一部分。重写方法的 `throws` 子句可能指定该方法将抛出任何被覆盖方法通过其 `throws` 子句不允许抛出的异常（§8.4.8.3）。当涉及接口时，一个重写声明可以重写多个方法声明。在这种情况下，重写声明必须具有一个与所有被覆盖的声明兼容的 `throws` 子句（§9.4.1）。

未检查异常类（§11.1.1）免于编译时检查。

> 错误类（Error classes）被免于检查，是因为它们可能发生在程序的许多点，且从中恢复是困难或不可能的。声明此类异常的程序对后继者来说将是混乱的。复杂的程序可能仍然希望捕获并尝试从这些某些情况中恢复。

运行时异常被免于检查，因为在 Java 语言设计者看来，必须声明此类异常并不能显著地建立程序的正确性。Java 语言的许多操作和结构可能会在运行时产生异常。Java 编译器可用的信息以及它执行的分析通常不足以证明运行时异常不会发生，尽管这对于程序员来说可能是显而易见的。要求声明此类异常类仅仅会给程序员带来困扰。

例如，考虑代码可能实现了一个环形数据结构，通过构造方式，它永远不会涉及空引用；程序员可以此此确定 `NullPointerException` 不会发生，但 Java 编译器很难证明这一点。建立此类数据结构这种全局属性所需的证明技术超出了本规范的范畴。

我们说根据 §11.2.1 和 §11.2.2 中的规则，一个语句或表达式可以抛出异常类 E，即该语句或表达式的执行可能导致抛出类为 E 的异常。

我们说一个 `catch` 子句可以捕获其可捕获的异常类：

* 单捕获 `catch` 子句的可捕获异常类是其异常参数的声明类型（§14.20）。
* 多捕获 `catch` 子句的可捕获异常类是表示其异常参数类型的联合中的候选项。

### 11.2.1 表达式的异常分析

类实例创建表达式（§15.9）可以抛出异常类 E，当且仅当：

* 该表达式是一个限定的类实例创建表达式，且限定表达式可以抛出 E；或者
* 参数列表中的某些表达式可以抛出 E；或者
* E 是所选构造函数调用类型的异常类型之一（§15.12.2）；或者
* 该类实例创建表达式包含一个类体（ClassBody），且类体中的某些实例初始化器或实例变量初始化器可以抛出 E。

方法调用表达式（§15.12）可以抛出异常类 E，当且仅当：

* 方法调用表达式的形式为 `Primary . [TypeArguments] Identifier` 且 `Primary` 表达式可以抛出 E；或者
* 参数列表中的某些表达式可以抛出 E；或者
* E 是所选方法调用类型的异常类型之一（§15.12.2）。

Lambda 表达式（§15.27）不能抛出任何异常类。

对于其他任何类型的表达式，该表达式可以抛出异常类 E，当且仅当其直接子表达式中的一个可以抛出 E。

> 方法引用表达式（§15.13）`Primary :: [TypeArguments] Identifier` 在 `Primary` 子表达式可以抛出异常类时可以抛出异常类。相比之下，Lambda 表达式不抛异常，并且没有可以进行异常分析的直接子表达式。是包含表达式和语句的 Lambda 表达式体可以抛出异常类。

### 11.2.2 语句的异常分析

`throw` 语句（§14.18）如果其抛出的表达式静态类型为 E 且不是最终或有效最终参数，则可以抛出 E 或抛出的表达式可以抛出的任何异常类。

例如，语句 `throw new java.io.FileNotFoundException();` 只能抛出 `java.io.FileNotFoundException`。从形式上说，它并不是“可以抛出” `java.io.FileNotFoundException` 的子类或父类。

如果抛出的表达式是 `catch c` 的最终或有效最终参数的 `throw` 语句可以抛出异常 E，当且仅当：

* E 是 `try` 语句的 `try` 块声明 `c` 可以抛出的异常类；且
* E 与 C 的任何可捕获异常类赋值兼容；且
* E 与同一 `try` 语句中 C 左侧声明的任何 `catch` 子句的可捕获异常类都不赋值兼容。

`try` 语句（§14.20）可以抛出异常类 E，当且仅当：

* `try` 块可以抛出 E，或者用于初始化资源的表达式（在 `try-with-resources` 语句中）可以抛出 E，或者资源 `close()` 方法的自动调用（在 `try-with-resources` 语句中）可以抛出 E；或者
* `try` 语句的某个 `catch` 块可以抛出 E，且不存在块或 `finally` 块可以正常完成；或者
* 存在 `finally` 块且可以抛出 E。

显式构造函数调用语句（§8.7）可以抛出异常类 E，当且仅当：

* 参数列表中的某些表达式可以抛出 E；且
* E 被确定为构造函数 `throws` 子句的异常类（§15.12.6）。

如果 S 中的表达式可以抛出 E，则其他语句 S 可以抛出异常 E。

### 11.2.3 异常检查

如果方法或构造体抛出的某些异常 E 是检查异常且 E 不是 `throws` 子句声明的类的子类，则为编译错误。

如果 Lambda 体抛出的某些异常 E 是检查异常且 E 不是 Lambda 表达式所声明的函数类型的子类，则为编译错误。

如果命名类的类初始化器（§8.3.2）或静态初始化器（§8.7）可以抛出检查异常，则为编译错误。

如果命名类的实例变量初始化器（§8.3.2）或初始化器（§8.6）可以抛出异常，则没有编译错误，除非该命名类至少有一个显式声明的构造函数，并且该异常类或其父类在每个构造函数的 `throws` 子句中都显式声明。

注意，如果匿名类（§15.9.5）的实例变量初始化器或初始化器可以抛出异常，则没有编译错误。在命名类中，传播初始化器可能抛出的异常信息的责任是在任何显式构造函数声明上声明合适的 `throws` 子句。构造函数与检查异常之间的关系对于匿名类是有保证的，因为 Java 编译器始终根据其初始化器可以抛出的检查异常为匿名类生成带有合适 `throws` 子句的构造函数。

如果 `catch` 子句可以捕获检查异常类 E1，但对应 `catch` 子句的 `try` 块没有抛出 E1 的子类或父类的检查异常（除非 Ei 是 `Exception` 的父类），则为编译错误。

如果 `catch` 子句可以捕获异常类 E1，且其直接相邻 `try` 语句的前一个句可以捕获 Ei 或其父类，则为编译错误。

如果 `catch` 子句可以捕获检查异常类 E1，且对应 `catch` 子句的 `try` 块可以抛出检查异常类 E2（其中 E2 < E1），且前一个句可以捕获检查异常类 E3（其中 E2 < E3 < E1），鼓励 Java 编译器发出警告。

**示例 11.2.3-1. 捕获检查异常**

```java
import java.io.*;

class StaticallyThrownExceptionsIncludeSubtypes {

    public static void main(String[] args) {

        try {

            throw new FileNotFoundException();

        } catch (IOException ioe) {

            // "IOException" 捕获 IOException
            // 以及任何子类。

        }

        try {

            throw new FileNotFoundException();
            // 语句 "can throw" 抛出 FileNotFoundException。
            // 并不是语句 "can throw"
            // 出 FileNotFoundException 的子类或父类。

        } catch (FileNotFoundException fnfe) {

            // ... 处理异常

        } catch (IOException ioe) {

            // 合法，但 Java SE 7 建议编译器给出
            // 警告，因为 try 块 "can throw" 的所有
            // IOException 子类已经由之前的
            // catch 子句捕获了。

        }

        try {

            m();
            // m 的声明说为 "throws IOException"，所以
            // m "can throw" 抛出 IOException。并不是 m
            // 抛出 IOException 的子类或父类
            //（例如，Exception）。

        } catch (FileNotFoundException fnfe) {

            // 合法，因为异常的动态类型
            // 可能是 FileNotFoundException。

        } catch (IOException ioe) {

            // 合法，因为异常的动态类型
            // 可能是 IOException 的另一个子类。

        } catch (Throwable t) {

            // 可以捕获 Throwable。

        }

    }

    static void m() throws IOException {

        throw new FileNotFoundException();

    }

}
```

根据上述规则，多异常 `catch` 子句中的每个备选分支必须能够捕获由 `try` 块抛出且未被之前的 `catch` 子句捕获的某些异常类。例如，下面的第二个 `catch` 子句将导致编译错误，因为异常分析确定 `SubclassOfFoo` 已经被第一个 `catch` 子句捕获了。

# 异常的运行时处理

```java
try { ... }

catch (Foo f) { ... }

catch (Bar | SubclassOfFoo e) { ... }
```



当抛出异常（§S14.18）时，控制将从导致异常的代码转移到最近的动态嵌套的 `catch` 子句，前提是 `try` 语句（§S14.20）中的任何子句可以处理该异常。

如果一个语句或表达式出现在 `catch` 子句所属的 `try` 语句的 `try` 块中，或者该语句或表达式的调用者动态嵌套在 `catch` 子句中，则认为其被该 `catch` 子句动态嵌套。

语句或表达式的调用者取决于它出现的位置：

- 如果在方法内部，则调用者是执行以导致方法调用的方法调用表达式（§S15.12）。
- 如果在构造函数、实例初始化器或实例变量初始化器内部，则调用者是类实例创建表达式（§S15.9）或执行以创建对象的 `newInstance` 方法调用。
- 如果在静态初始化器或静态变量初始化器内部，则调用者是使用该类或接口以导致其初始化的表达式（§S12.4）。

特定的 `catch` 子句是否能处理异常，通过比较被抛出的对象的类与 `catch` 子句中可捕获的异常类来确定。如果该 `catch` 子句的可捕获异常类之一是异常的类或该异常类的父类，则该 `catch` 子句可以处理该异常。

等价地，`catch` 子句将捕获任何是其一个可捕获异常类的 `instanceof`（§S15.20.2）的异常对象。

抛出异常时发生的控制转移会导致表达式和语句（§S15.6）以及语句（§S14.1）的异常终止，直到遇到可以处理该异常的 `catch` 子句；随后通过执行该 `catch` 子句的块继续执行。抛出异常的代码永远不会恢复。

所有异常（同步和异步）都是精确的：当控制转移发生时，在抛出异常点之前已执行的语句和评估的所有影响似乎都已发生。在抛出异常点之后，任何表达式、语句或其部分都不可能看起来已经执行过评估。

如果优化后的代码推测地执行了异常发生点之后的某些表达式或语句，则此类代码必须准备好将推测执行隐藏在程序的用户可见状态之外。

如果找不到可以处理该异常的 `catch` 子句，则当前线程（遇到异常的线程）将被终止。在终止之前，将执行所有的 `finally` 子句，并根据以下规则处理未捕获的异常：

- 如果当前线程设置了未捕获异常处理器，则执行该处理器。
- 否则，将调用当前线程父级 `ThreadGroup` 的 `uncaughtException` 方法。如果该 `ThreadGroup` 及其父级 Groups 未重写 `uncaughtException`，则调用默认处理器的 `uncaughtException` 方法。

在希望确保某块代码在另一块代码之后始终执行的情况下，如果另一块代码异常终止，则可以使用带有 `finally` 子句的 `try` 语句（§14.20.2）。

如果 `try-finally` 或 `try-catch-finally` 语句中的 `try` 或 `catch` 块异常终止，则在异常传播期间，如果最终没有找到匹配的 `catch` 子句，将执行 `finally` 子句。

如果由于 `try` 块异常终止而执行了 `finally` 子句，且 `finally` 子句本身也异常终止，则异常终止的原因将被丢弃。

### 1.3 抛出和捕获异常

以下程序声明了一个异常。`main` 方法调用了它四次。

如果我们运行该程序并传递参数 `divide not`

它产生输出：

```
thrower("divide") done
Test "divide" 抛出了 java.lang.ArithmeticException
message: by zero
thrower("null") done
Test "null" 抛出了 java.lang.NullPointerException
message: null
thrower("not") done
Test "not" 没有抛出异常
thrower("test") done
Test "test" 抛出了 TestException
message: Test message
```

```java
class TestException extends Exception {

    TestException() { super(); }

    TestException(String s) { super(s); }

}
```

`thrower` 方法抛出 `TestException` 实例，这是一个检查异常（§11.1）。如果省略 `throws` 子句，会导致编译错误。

注意，无论是否发生异常，每次调用 `thrower` 时 `finally` 子句都会被执行，如 "thrower(...) done" 的输出所示。

# 第12 章 执行

本章规定了程序运行期间的活动。它围绕 Java 虚拟机以及组成程序的类、接口和对象的生命周期组织。

Java 虚拟机启动时会加载指定的类或接口，并调用该类或接口的 `main` 方法。第12.2 节概述了执行 `main` 所涉及的加载、链接和初始化步骤，作为本章概念的介绍。后续章节详细说明加载（§12.2）、链接（§12.3）和初始化（§12.4）。

本章继续介绍新类实例的创建（§12.5）以及类实例的消息化（§12.6）。最后描述类的卸载（§12.7）以及程序退出时的处理程序（§12.8）。

## 12.1 Java虚拟机启动

Java 虚拟机通过调用指定类或接口的 `main` 方法来启动执行，传递单个参数，该参数是一个字符串数组。

Java 虚拟机启动的精确语义见《Java虚拟机规范，Java SE 11 版》第5章。在这里，我们从 Java 编程语言的角度给出该过程的概述。

### Java 虚拟机的启动

作为字符串使用的命令行参数将作为 `main` 方法的参数提供。

例如，在 UNIX 实现中，命令行如下：

```
java Test reboot Bob Dot Enzo
```

通常会通过调用 `Test` 类（未命名包中的类）的 `main` 方法来启动 Java 虚拟机，并向其传递包含 "reboot"、"Bob"、"dot" 和 "Enzo" 字符串的数组。

我们现在概述 Java 虚拟机执行 `Test` 的步骤，这将作为后续章节详细描述的加载、链接和初始化过程的示例。

#### 12.1.1 加载类

尝试执行 `Test` 类的 `main` 方法时，发现 `Test` 类尚未加载——即 Java 虚拟机当前不包含该类的二进制表示。随后，Java 虚拟机将使用加载器尝试寻找这样的二进制表示。如果此过程失败，则会抛出错误。该加载过程在 §12.2 中进一步描述。

#### 12.1.2 链接 Test：验证、准备、（可选的）解析

在加载 `Test` 之后，在调用 `main` 之前必须对其进行初始化。而且 `Test` 与所有（类或接口）类型一样，在初始化之前必须先进行链接。链接涉及验证、准备和（可选的）解析。链接在 §12.3 中进一步描述。

验证检查加载的 `Test` 表示是否格式正确，并具有适当的符号表。验证还会检查实现 `Test` 的代码是否符合 Java 编程语言和 Java 虚拟机的语义要求。如果在验证期间检测到问题，则会抛出错误。验证在 §12.3.1 中进一步描述。

准备涉及静态存储的分配以及 Java 虚拟机实现内部使用的任何数据结构（例如方法表）。准备过程在 §12.3.2 中进一步描述。

解析是检查从 `Test` 到其他类和接口的符号引用的过程，通过加载所提到的其他类和接口，并检查这些引用是否正确。

解析步骤在初始链接时是可选的。某种实现可能会在链接非常早期就解析正在链接的类或接口的符号引用，甚至可以到递归地解析进一步引用的类和接口中的所有符号引用。（这种解析可能会导致这些后续加载和链接步骤产生错误。）该实现选择了一个极端，类似于多年年来在 C 语言简单实现中所做的“静态”链接。（在这些实现中，编译后的程序通常表示为 "a.out" 文件，该文件包含程序的完全链接版本，包括指向程序所用库的完全解析的链接。这些例程的副本被包含在 "a.out" 文件中。）

实现可以选择仅在符号引用被积极使用时才进行解析；对所有符号引用一致地使用这种策略将代表“最懒”的解析形式。在这种情况下，如果 `Test` 有多个指向另一个类的符号引用，则这些引用可能在使用它们时逐一解析，或者如果这些引用在程序执行期间从未被使用，则完全不解析。

对何时执行解析的唯一要求是：在解析期间检测到的任何错误必须在程序采取某些操作时抛出，而该操作直接或间接地需要对涉及错误的类或接口进行链接。使用上述选择的“静态”示例实现，如果加载和链接错误涉及 `Test` 类或任何进一步的、递归引用的类和接口中提到的类，这些错误可能在程序执行之前发生。在实现了“最懒”解析的系统中，这些错误只有在错误的符号引用被积极使用时才会被抛出。

解析过程在 §12.3.3 中进一步描述。

#### 12.1.3 初始化 Test：执行初始化器

在我们持续的示例中，Java 虚拟机仍在尝试执行 `Test` 类的 `main` 方法。只有在类已初始化（见 §12.4.1）的情况下才允许这样做。

初始化包括按照文本顺序执行 `Test` 类的任何类变量初始化器和静态初始化器。在初始化 `Test` 之前，必须初始化其直接父类，以及其直接父类的直接父类，依此类推，递归进行。在最简单的情况下， `Test` 以 `Object` 作为其隐式直接父类；如果 `Object` 类尚未初始化，则必须在初始化 `Test` 之前初始化它。`Object` 类没有父类，因此递归在此处终止。

如果 `Test` 类有另一个类 `Super` 作为其父类，则必须在 `Test` 之前初始化 `Super`。如果尚未完成这些操作，则需要加载、验证和准备 `Super`，并且取决于实现，可能还涉及递归地解析来自 `Super` 的符号引用，依此类推。

因此，初始化可能会导致加载、链接和初始化错误，包括涉及其他类型的错误。

初始化过程在 §12.4 中进一步描述。

#### 12.1.4 调用 Test.main

最后，在完成 `Test` 类的初始化后（在此期间可能发生了其他后续的加载、链接和初始化），调用 `Test` 的方法。

`main` 方法必须声明为 `public`、`static` 且 `void`。它必须指定一个形式参数（见 §8.4.1），其声明类型为 `String` 数组。因此，以下声明中的任何一种都是可以的：

```java
public static void main(String[]) args

public static void main(String... args)
```



## 12.2 类和接口的加载

加载是指寻找特定名称的类或接口类型的二进制形式的过程，可能是实时计算，但更常见的方法是通过检索 Java 编译器之前从源码计算出的二进制表示，并从二进制数据构造一个 `Class` 对象来表示该类或接口。

加载的精确语义在《虚拟机规范》的第 5 章给出。这里我们从 Java 编程语言的角度呈现了该过程的概述。

类或接口的二进制格式通常是上述引用的《虚拟机规范 SE 11 版中的类格式，但只要符合 `§13.1` 中的要求，其他格式也是可能的。

## 12.3 类和接口的链接

链接是将类或接口类型的二进制形式并将其组合到 Java 虚拟机的运行时状态中的过程，以便能够执行。类或接口类型在链接之前总是会被加载。

链接涉及三个不同的活动：验证（`verification`）、准备（`preparation`）和符号引用的解析（`resolution`）。

链接的精确语义在《Java虚拟机规范 Java SE 11 版》的第 5 章中给出。在这里，我们从 Java 编程语言的角度介绍该过程的概述。

该规范允许实现上具有灵活性，例如在何时进行链接活动（以及由于递归原因的加载活动），只要遵守了 Java 编程语言的语义，并且在类或接口在初始化之前已经过完全的验证和准备，并且在链接过程中检测到的错误是在程序执行可能需要链接到错误中的类或接口的操作点抛出的。

例如，实现类可以选择仅在类或接口被使用时才单独解析其中的每个符号引用（惰性解析或后期解析），或者在验证类或接口时一次性解析所有符号引用（静态解析）。这意味着在某些实现中，解析过程可能会在类或接口初始化后继续进行。

由于链接涉及新数据结构的分配，它可能会因 `OutOfMemoryError` 失败。

### 12.3.1 二进制表示的验证

验证确保类或接口的二进制表示在结构上是正确的。例如，它会检查每条指令是否具有有效的操作码；每个分支指令是否跳转到其他执行的开头，而不是跳转到指令的中间；每个方法是否都提供了结构上正确的签名；以及每条指令是否遵守 Java 虚拟机语言的类型判别。

如果在验证过程中发生错误，将在导致该类被验证的程序点抛出以下 `LinkageError` 类的子类的实例：

- `VerifyError`：类或接口的二进制定义未能通过一系列所需的检查，以验证它是否遵守 Java 虚拟机语言的语义，以及它是否不会破坏 Java 虚拟机的完整性。（某些示例参见 `§13.4.2`、`§13.4.4`、`§13.4.9` 和 `§13.4.17`。）

### 12.3.2 类或接口类型的准备

准备涉及为类或接口创建静态字段（类变量和常量）并将这些字段初始化为默认值（`§12.5`）。这不需要执行你的任何源代码；静态字段的显式初始化器作为初始化（`§12.4`）、准备的一部分被执行。

Java 虚拟机的实现可以在准备阶段准备额外的数据结构，以便后续对类或接口的操作更高效。其中一种特别有用的数据结构是“方法表”（`method table`）或其他数据结构，它允许在类的实例上调用任何方法，而不需要在调用时在父类中进行搜索。

### 12.3.3 符号引用的解析

类或接口的二进制表示使用其他类和接口的二进制名称（`§13.1`）符号地引用其他类、接口以及它们的字段、方法和构造函数（`§13.1`）。对于字段和方法，这些符号引用包含了字段或方法所属的类或接口类型的名称，以及字段或方法本身的名称，带有相应的类型信息。

在使用符号引用之前，它必须经过解析，在过程中会检查符号引用是否正确，并且如果该引用被重复使用，则通常会被替换为可以更高效处理的直接引用。

如果在解析过程中发生错误，将抛出一个错误。最常见的情况下，这将是 `IncompatibleClassChangeError` 类的以下子类的实例，但也可能是 `IncompatibleClassChangeError` 的其他子类的实例，甚至是 `IncompatibleClassChangeError` 类本身的实例。此错误可能会在程序直接或间接使用该类型符号引用的任何点抛出：

- `IllegalAccessError`：遇到了一个符号引用，该引用指定了对字段的使用或赋值、方法的调用或类的实例化，但包含该引用的代码没有访问该字段或方法的权限，因为该成员被声明为 `private`、`protected` 或包级访问权限（非 `public`），或者因为该类在向包含该引用的代码导出或开放的包中未被声明为 `public`。

  这可能会发生，例如，如果一个最初声明为 `public` 的字段在另一个类引用该字段并编译后被更改为非公开（`§13.4.7`）；或者在另一个方法引用该字段并编译后，该公共类所在的包不再由其模块导出（`§13.3`）。

- `InstantiationError`：遇到了一个在类实例创建中使用的符号引用，但无法创建实例，因为该引用被证明指向一个抽象类。

  这可能会发生，例如，如果一个最初是 `abstract` 的类在另一个类引用该类并编译后被更改为 `abstract`（`§13.4.1`）。

- `NoSuchFieldError`：遇到了一个符号引用，它指向特定类或接口的特定字段，但该类或接口不包含名为该名的字段。

  这可能会发生，例如，在另一个类引用该字段并编译后，从类中删除了字段声明（`§13.4`）。

- `NoSuchMethodError`：遇到了一个符号引用，它指向特定类或接口的方法，但该类或接口不包含该签名的方法。

  这可能会发生，例如，在另一个类引用该方法并编译后，从类中删除了方法声明（`§13.4`）。

此外，如果类声明了一个无法实现的本地方法，可能会抛出 `UnsatisfiedLinkError`（`LinkageError` 的子类）。该错误将在方法被使用时或更早发生，取决于虚拟机实现使用的解析策略（`§12.3`）。

## 12.4 类和接口的初始化

类的初始化包括执行其静态初始化器以及类中声明的静态字段（类变量）的初始化器。

接口的初始化包括执行接口中声明的字段（常量）的初始化器。

### 12.4.1 初始化发生的时刻

类或接口类型 T 在发生以下任何情况之前立即初始化：

- T 是类且创建了 T 的实例。
- 调用 T 的静态方法。
- 为 T 声明的静态字段赋值。
- 使用了 T 声明的静态字段且该字段不是常量（`§4.12`）。

当类初始化时，其父类会被初始化（如果它们尚未被初始化），以及声明任何默认方法（`§9.4.3`）的接口（`§8.1.5`）（如果它们尚未被初始化）。接口的初始化本身不会导致其任何父类的初始化。

对静态字段（`§8.3.1`）的引用只会初始化声明该字段的类或接口，即使通过子类、子接口或实现接口的类来引用它。

在 `Class` 类和 `java.lang.reflect` 包中某些反射方法的调用也会导致类或接口初始化。

在任何其他情况下，类或接口都不会初始化。注意，编译器可能会在接口中生成合成默认方法，即未显式或隐式声明的默认方法（`§13.1`）。此类方法将触发接口初始化，尽管源代码没有指示该接口应该初始化。

意图是让类或接口类型有一组初始化器使其处于一个一致的状态，并且该状态是其他类观察到的第一个状态。静态初始化器和类变量初始化器按照文本顺序执行，并可以引用类中在文本位置上之后声明的类变量，即使这些类变量在作用范围内（`§8.3.3`）。

此限制旨在于编译时检测大多数循环或或其他不规范的初始化。

初始化代码不受限制这一事实，允许构造出某些示例：在类变量的值仍保持为默认值时（在初始化表达式求值之前），就可以观察到该值，但在实践中此类示例非常罕见。（例如，也可以为实例变量构造此类示例，见 `§12.5`）。在这些初始化器中可以使用 Java 编程语言的完整功能；程序员必须小心。这种力量为代码生成器带来了额外负担，但由于 Java 语言是并发的（`§12.4.2`），这种负担在任何情况下都会产生。

### Example 12.4.1-1. 超类在子类之前初始化

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

```
Two false
```

类 One 永远不会被初始化，因为它没有被积极使用，因此从未被链接。类 Two 只有在其超类 Super 初始化后才被初始化。

### Example 12.4.1-2. 仅声明 static 字段的类会被初始化

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

```
1729
```

因为类 Sub 从未被初始化；对 `Sub.taxi` 的引用是指向实际声明在类 Super 中的字段的引用，并且不会触发类 Sub 的初始化。

### Example 12.4.1-3. 接口初始化不会初始化父接口

```java
interface I {
    int i = 1, ii = Test.out("ii", 2);
}

interface J extends I {
    int j = Test.out("j", 3), jj = Test.out("jj", 4);
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
j=3
jj=4
3
```

对 `J.i` 的引用指向一个常量变量（`§4.12.4`）；因此，它不会导致 I 的初始化（`§13.4.9`）。

对 `K.j` 的引用指向实际声明在接口 J 中的字段，该字段不是常量变量；这导致了接口 J 字段的初始化，但不会导致其父接口 I 或接口 K 字段的初始化。

尽管使用了名称 k 来引用接口 J 的字段 j，但接口 K 并没有被初始化。

### 12.4.2 详细初始化过程

由于 Java 编程语言是多线程的，类或接口的初始化需要仔细的同步，因为其他线程可能正同时尝试初始化该类或接口。还可能作为该类或接口初始化的一部分，递归地请求类或接口的初始化；例如，类 A 中的变量初始化器可能会调用无关类 B 的方法，而类 B 反而可能调用类 A 的方法。Java 虚拟机实现负责通过以下程序处理同步和递归初始化。

该程序假设 `Class` 对象已经通过验证并准备就绪，且 `Class` 对象包含指示一种状况的状态：

- 该 `Class` 对象已通过验证但未初始化。
- 该 `Class` 对象正在被某个特定线程初始化。
- 该 `Class` 对象已完全初始化并准备好使用。
- 该 `Class` 对象处于错误状态，可能是因为尝试初始化但失败了。

对于每个类或接口，都有唯一的初始化锁 LC。从 c 到 LC 的映射由 Java 虚拟机决定。初始化 c 的步骤如下：

1. 对 c 的初始化锁 LC 进行同步。这涉及等待直到当前线程能够获取 LC。
2. 如果 c 的 `Class` 对象指示其他线程正在对 c 初始化，则释放 LC 并阻塞当前线程，直到正在进行的初始化完成，此时重复此步骤。
3. 如果 c 的 `Class` 对象指示当前线程正在对 c 进行初始化，则这必须是一个递归的初始化请求。释放 LC 并正常完成。
4. 如果 c 的 `Class` 对象指示 c 已经初始化，则无需进一步操作。释放 LC 并正常完成。
5. 如果 c 的 `Class` 对象处于错误状态，则无法初始化。释放 LC 并抛出 `NoClassDefFoundError`。
6. 否则，记录当前线程正在初始化 c 的 `Class` 对象的实，并释放 LC。然后，初始化 c 的静态字段。
7. 否则，记录当前线程正在初始化 c 的 `Class` 对象的实，并释放 LC。然后，如果 c 是类而不是接口，让 SC 为其超类，让 SI...SIN 为其实现的所有接口。按照 c 的实现接口递归执行此程序。如果 s 的初始化由于抛出异常而中断，获取 LC，标记 `Class` 对象为错误，释放 LC，并以异常异常中断。
8. 否则，通过类加载器确定 s 是否已经初始化。
9. 接下来，如果 c 是类而不是接口，执行其静态初始化器，或者接口的初始化器。
10. 如果初始化执行正常，则获取 LC，标记 `Class` 对象为完全初始化，通知所有线程，释放 LC，并正常完成程序。
11. 否则，初始化必须抛出某种异常 E。如果类 E 不是 `Error` 或其子类，则创建一个 `ExceptionInInitializerError` 实例作为参数，并在后续步骤中使用该对象替换 E。如果由于 `OutOfMemoryError` 无法创建 `ExceptionInInitializerError` 实例，则在后续步骤中使用 `OutOfMemoryError`。
12. 获取 LC，标记 `Class` 对象为错误，通知所有线程，释放 LC，并根据上一步确定的 E 异常中断。

当实现能够确定初始化已经完成时，可以通过省略步骤 1 中的锁获取和步骤 4 中的锁释放来优化此程序，前提是根据内存模型，获取锁时存在的所有发生前排序仍然存在。

代码生成器需要保留类或接口可能初始化的点，插入上述初始化程序的调用。如果此初始化程序正常完成且 `Class` 对象已完全初始化并准备好使用，则不再需要调用初始化程序，可以将其从代码中消除——例如通过补丁或重新生成代码。

编译时分析在某些情况下可能能够从生成的代码中消除许多对类型初始化的检查，前提是能够确定一组相关类型的初始化顺序。然而，这种分析必须充分考虑到并发以及初始化代码不受限制的因素。

## 12.5 创建新类实例

当评估类实例创建表达式（`§15.9`）时，会显式创建一个新的类实例。

在以下情况下可能会隐式创建新的类实例：

- 加载包含字面量（`§3.10.5`）的类或接口可能会创建一个表示字面量的新 `String` 对象（如果之前内化过相同 Unicode 代码点序列的字符串，则不会发生）。
- 执行导致装箱转换（`§5.1.7`）的操作。装箱转换可能会创建一个包装类（`Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double`）的新对象。
- 执行不是常量表达式（`§15.28`）部分的字符串连接运算符 +（`§15.18.1`），总是创建一个新的 `String` 对象。字符串连接运算符还可能为原始类型的值创建临时包装对象。
- 属性引用表达式（`§15.13.3`）或 Lambda 表达式的评估需要创建一个实现函数式接口类型的类的新实例。

这些每种情况都确定了特定的构造函数（`§8.8`），并在实例创建过程的一部分调用指定的参数（可能为空）。

### 执行

每当创建一个类实例时，都会为其分配内存空间，该空间用于容纳类类型中声明的所有实例变量以及该类类型每个子类中声明的所有实例变量，包括所有可能被隐藏的实例变量（`§8.3`）。

如果没有足够的空间来为对象分配内存，则类实例的创建将以 `OutOfMemoryError` 异常终止。否则，新对象中的所有实例变量（包括在父类中声明的变量）将初始化为它们的默认值（`§4.12.5`）。

在将新创建的对象的引用作为结果返回之前，将处理指定的构造方法，按照以下过程初始化新对象：

1. 将构造方法的参数赋值为该构造方法调用新创建的参数变量。
2. 如果此构造方法以同类中另一个构造方法的显式构造方法调用（`§8.8.7.1`）开头（使用 `this`），则评估参数并使用这五个步骤递归地处理构造方法调用。如果此构造方法调用由于相同原因异常终止；否则，继续执行第 5 步。
3. 此构造方法不是以同类中另一个构造方法的显式构造方法调用（使用 `this`）开头。如果是除 `Object` 以外的类，则此构造方法将以父类构造方法的显式或隐式调用（使用 `super`）开头。评估参数并使用这五个步骤递归地处理该父类构造方法的调用。如果该构造方法调用异常终止，则该过程因相同原因异常终止。否则，继续执行第 4 步。
4. 执行该类的实例初始化器和变量初始化器，将变量初始化器的值赋值给相应的实例变量，按照它们在类源代码中从左到右出现的顺序。如果执行这些初始化器中的任何一个导致异常，则不再处理后续的初始化器，且该过程以该异常异常终止。否则，继续执行第 5 步。
5. 执行此构造方法体的剩余部分。如果该执行异常终止，则该过程因相同原因异常终止。否则，该过程正常完成。

与 C++ 不同，Java 编程语言没有规定在创建新类实例期间方法分派的修改规则。如果在正在初始化的对象上调用了在子类中重写的方法，则将使用这些重写方法，即使在新对象完全初始化之前也是如此。

### Example 12.5-1. 实例创建的评估

```java
class Point {
```



## 示例 12.5-1. 实例创建

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

创建一个 `ColoredPoint` 的新实例。首先，为新的 `ColoredPoint` 分配空间以存储字段 `x`、`y` 和 `color`。所有字段都被初始化为它们的默认值（在这种情况下，每个字段均为 0）。接下来，首先调用无参数的 `ColoredPoint` 构造方法。由于 `ColoredPoint` 没有声明构造方法，因此隐式声明了一个如下形式的默认构造方法：

> `Point() { super(); }`

此构造方法调用了无参数的 `Point` 构造方法。`Point` 构造方法不是以调用构造方法开头，因此 Java 编译器提供了一个无参数父类构造方法的隐式调用，仿佛它被写成这样：

```java
Point() { super(); x = 1; y = 1; }
```

因此，调用了无参数的 `Object` 构造方法。

`Object` 类没有父类，因此递归终止。接下来，调用 `Object` 的任何实例初始化器和变量初始化器。接下来，执行无参数的 `Object` 构造体。由于 `Object` 中没有声明此类构造方法，因此 Java 编译器提供了一个默认构造方法：

```java
Object() {
}
```

接下来，执行 `Object` 的变量初始化器。然后，执行无参数的 `Point` 构造体。由于 `Point` 中没有声明此类构造方法，因此 Java 编译器提供了一个默认的：

接下来，执行 `Point` 的变量初始化器。此步骤为 `x` 和 `y` 赋值。然后，执行 `Point` 构造体的剩余部分，将 `x` 和 `y` 赋值为 1。最后，执行 `ColoredPoint` 构造体的剩余部分。在此，执行 `ColoredPoint` 的变量初始化器。此步骤为 `color` 赋值 `0xFF00FF`。最后，执行 `ColoredPoint` 构造体的剩余部分。

### 示例 12.5-2. 实例创建期间动态分派

```java
class Super {
    Super() { printThree(); }

    void printThree() { System.out.println("three"); }
}

class Test extends Super {
    int three = (int)Math.PI; // 那是 3

    void printThree() { System.out.println(three); }

    public static void main(String[] args) {
        Test t = new Test();
    }
}
```

此程序输出：

```
0
3
```

这表明 `Super` 类中的 `printThree` 调用并没有初始化对象的定义，而是 `Super` 类的定义。这是因为对象尚未初始化。

## 12.6 类实例的终化

`Object` 类有一个受保护的方法 `finalize`；该方法可以被类重写。终化提供了释放无法由垃圾管理器自动释放资源的机会。Java 编程语言没有规定何时调用终化，仅说明它会在存储被回收之前发生。

Java 编程语言没有指定哪个线程将调用对象的终化。需要注意的是，终化线程可能是活跃的（这在大型多处理器上是需要的），并且如果一个大的连接结构变得不可用，所有的终化方法都可能被调用，每个终化都在不同的线程中运行。

Java 编程语言对终化方法的调用不施加排序。终化可以以任何顺序被调用，甚至是并发执行。

实现一个类，使得当所有对象变得不可用时，能够按照特定顺序调用一组终化类的方法是简单的。定义这样一个类留给读者练习。

保证在调用终化时，调用线程不会持有任何用户可见的同步锁。如果在终化期间抛出意外异常，该异常将被忽略且该对象的终化将终止。

对象的构造方法的完成发生于（§17.4.5）其终化方法的执行之前（正式的发生-before 定义）。

`Object` 类声明的 `finalize` 方法不采取任何操作。`Object` 声明了 `finalize` 方法这一事实意味着任何类的 `finalize` 方法始终可以调用其父类的 `finalize` 方法。这应该总是这样做，除非程序员的意图是抵消父类终化的动作。（与构造方法不同，终化方法不会自动调用父类的终化；这种调用必须显式编码。）

为了效率，实现可能会跟踪没有重写 `Object` 类 `finalize` 方法的类，或者以简单方式重写它的类。

例如：

```java
protected void finalize() throws Throwable {
    super.finalize();
}
```

## 12.6 类实例的终化

我们鼓励实现将此类对象视为具有未被重写的终结器，并按照 §12.6.1 所述更高效地对它们进行终化。

终结器可以被显式调用，就像任何其他方法一样。

`java.lang.ref` 包描述了弱引用，它们与垃圾收集和终化有相互作用。对于任何与 Java 编程语言有特殊交互的 API，实现者必须意识到 `java.lang.ref` API 施加的任何要求。本规范不以任何方式讨论弱引用。详情请参阅 API 文档。

### 12.6.1 实现终化

每个对象都可以通过两个属性来描述：它可能是可达的、终结器可达的或不可达的，它也可能是未终化的、可终化的或已终化的。

* **可达** 对象是指任何从存活线程的任何潜在后续计算中都可以被访问的对象。
* **终结器可达** 对象可以从某些可终化对象通过某些引用链到达，但无法从任何存活线程到达。
* **不可达** 对象无法通过上述任一方式到达。
* **未终化** 对象的其终结器从未被自动调用过。
* **已终化** 对象的其终结器已经过自动调用过。
* **可终化** 对象的其终结器从未被自动调用过，但 Java 虚拟机可能会最终调用其终结器。

在对象 `o` 的构造函数调用了 `o` 上的 `Object` 构造函数且该调用成功完成（即没有抛出异常）之前，该对象不会被终化。终化之前对对象字段的任何写入必须对该对象的终化可见。此外，对该对象字段的所有终化前读取都不应看到在对象对象终化启动之后发生的写入。

对程序的优化变换可以设计为减少可达对象的数量，使其少于直观认为的数量。例如，Java 编译器或代码生成器可能会将不再被使用的变量或参数设置为 `null`，以导致该对象的存储可能更早地被回收。

另一个示例发生在对象字段中的值存储在寄存器中时。程序可以访问寄存器而不是对象，并且不再访问该对象。这意味着该对象是垃圾。注意，这种优化仅在引用存储在栈上而不是存储在堆中时才是允许的。

例如，考虑终结器守护者模式：

```java
class Foo {
    private final Object finalizerGuardian = new Object() {
        protected void finalize() throws Throwable {
            /* finalize outer Foo object */
        }
    };
}
```



如果子类重写了 `finalize` 但没有显式调用 `super.finalize`，则终结器守护者将强制调用 `super.finalize`。

如果允许对存储在堆上的引用进行此类优化，那么 Java 编译器可以检测到 `finalizerGuardian` 从未被读取，立即将该对象置空并尽早调用终结器。这违背了意图：程序员可能希望在 `Foo` 实例变得不可达时调用终结器。因此，这种变换是不合法的：只要外部类对象是可达的，内部类对象就应该是可达的。

此类变换可能导致 `finalize` 方法的调用比预期的更早。为了允许用户防止这种情况，我们强制执行一个同步可以保持对象存活的概念。如果一个对象的终结器可能导致对该对象的同步，那么每当持有该对象的锁时，该对象必须是存活的并被考虑在内。

注意，这并没有消除同步：只有当终结器可能会在其上进行同步时，同步才会保持对象存活。由于终结器发生在另一个线程中，在许多情况下，同步本身就无法删除。

## 12.6.2 与内存模型的交互

内存模型（§17.4）必须能够决定何时可以提交在终结器中发生的动作。本节描述了终结与内存模型的交互。

每次执行都有若干可达性决策点，由 `di` 标记。每个动作要么在 `di` 之前（comes-before），要么在 `di` 之后（comes-after）。如明确提到的，本节描述的“之前”排序与内存模型中的所有其他排序无关。

如果 r 是一个看到 w 的读取且 r 在 `di` 之前，则 w 必须在 `di` 之前。

如果 x 和 y 是同一个变量或监视器上的同步动作，使得 `so(x, y)` (§17.4.4) 且 y 在 `di` 之前，则 x 必须在 `di` 之前。

在每个可达性决策点，一组对象被标记为不可达，这些对象中的子集被标记为可终结。这些可达性决策点也是根据 `java.lang.ref` 包 API 文档提供的规则检查、入队和清除引用的点。

在点 `di` 被认为可达的对象仅限于那些可以通过应用这些规则证明是可达的：

- 如果存在对类 `c` 的静态字段 `v` 的写入 w1，其中 `v` 所在 w1 写入的值是指向 B 的引用，类 `c` 是由一个可达的类加载器加载，且不存在对 `v` 的写入 w2 使得 `hb(w2, w1)` 不为真且 w1 和 w2 都在 `di` 之前，则对象 B 在 `di` 处确定是可达的。
- 如果存在对 `a` 的元素 `v` 的写入 w1，其中 `v` 所在 w1 写入的值是指向 b 的引用，且不存在对 `v` 的写入 w2 使得 `hb(w2, w1)` 不为真且 w1 和 w2 都在 `di` 之前，则 b 从 `a` 确定是可达的。
- 如果对象 `c` 从对象 `b` 确定是可达的，且对象 `b` 从对象 `a` 确定是可达的，则 `c` 从 `a` 确定是可达的。

如果对象 x 在 `di` 被标记为不可达，则：

- x 在 `di` 处的静态字段中不能是确定可达的；且
- 线程 t 中所有在 `di` 之后的对 x 的使用必须发生在 x 的终结调用中，或者作为线程 t 执行对 x 的引用的在 `di` 之后的读取的结果；且
- 所有在 `di` 之后且看到 x 引用的读取都必须看到在 `di` 处不可达对象的元素的写入，或看到在 `di` 之后发生的写入。

如果满足以下至少一个条件，则动作 a 是对 x 的活跃使用：

- a 读取或写入 x 的某个元素
- a 锁定或解锁 x，并且有一个动作发生在 x 的终结调用之后
- a 写入 x

如果对象 x 在 `di` 被标记为可终结，则：

- x 在 `di` 处是不可达的；且
- `di` 被标记为可终结的；且
- 在 `di` 之后的动作必须在 `di` 之后。

## 12.7 类和接口的卸载

Java 语言的实现可能会卸载类。

类或接口当且仅当其定义的类加载器可以被回收时，才可以被卸载。

由引导层加载的类和接口可能不会卸载。

> 类卸载是一种有助于减少内存的优化。（此处原文重复已略）。显然，程序的语义不应依赖于系统是否选择实现如类卸载之类的优化。因此，类或接口是否已卸载不应该是透明的。

然而，如果一个类在其加载器可能可达时被卸载，那么 C 可能会被重新加载。可以确保这种情况不会发生。即使该类没有被任何当前加载的类引用，它也可能被某些尚未加载的类或接口 D 引用。当 D 被 C 的定义加载器加载时，其执行可能会导致 C 的加载。

由于我们可以验证卸载一个加载器可能可达的类或接口不会导致重新加载，而重新加载永远是不透明的，但卸载必须是透明的，因此不能在加载器可能可达时卸载类或接口。类似的推理可以推断出由引导层加载的类和接口是可以卸载的。

人们还论证了为什么如果定义类加载器可以被回收，卸载类 C 是安全的。如果定义加载器可以被回收，那么就不会有任何它的活跃引用（这包括不是存活但可能被终结器复活的引用）。反之，如果该加载器定义的类从其实例或代码中永远不会有活跃引用，这一点就可以成立。

类卸载这种优化对于那些加载大量类并在一段时间后停止使用这些类的应用程序具有意义。其特征是此类应用程序的特点是它们通过显式使用类加载器来管理类。因此，上述策略对它们有效。

严格来说，本规范并不非要讨论类卸载的问题，因为类卸载仅仅是一种优化。然而，该问题非常微妙，因此在此处提到它是以作说明。

## 12.8 程序退出

当发生以下两种情况之一时，程序将终止所有活动并退出：

- 所有非守护线程都终止。
- 某个线程调用了 `Runtime` 类或 `System` 类的 `exit` 方法，且退出操作未被安全管理器禁止。

# 第 13 章 二进制兼容性

Java 编程语言的开发工具应该在源代码可用时，根据需要支持自动重新编译。特定的实现还可能将类型的源码和二进制文件存储在版本数据库中，并实现一个使用数据库完整性机制的 `ClassLoader`，通过向客户端提供二进制兼容的类型版本来防止链接错误。

要广泛分发的包和类的开发者面临着一套不同的问题。在互联网（我们广泛分发系统的第一个例子）中，自动重新编译直接或间接依赖于要更改类型的现有二进制文件通常是不切实际或不可能的。相反，本规范定义了一系列允许开发者对包、类或接口进行的更改，同时保留（不破坏）与现有二进制文件的兼容性。

在 SOM 中的版本间二进制兼容性框架内，Java 编程语言的二进制文件在作者识别的所有相关转换下都是兼容的（尽管关于实例变量的添加另有一些限制）。使用他们的方案，以下是 Java 编程语言支持的重要二进制兼容更改列表：

- 重新实现现有的方法、构造函数和初始化器以提高性能。
- 更改方法或构造函数，使其对于某些输入返回值，而这些输入之前可能会抛出通常不应异常，或因进入无限循环或导致死锁而失败。
- 向现有的类或接口添加新的字段、方法或构造函数。
- 删除类的私有字段、方法或构造函数。
- 当更新整个包时，会删除该包内类和接口的包级访问字段、方法或构造函数。
- 重新调整现有类型声明中字段、方法或构造函数的顺序。
- 在类层次结构中向上移动方法。
- 重新调整类或接口的直接父接口列表。
- 在类型层次结构中插入新的类或接口类型。

本章规定了所有实现均保证的二进制兼容性最低标准。当混合使用类和接口的二进制文件未知来源是否兼容，但其源码按照所述的兼容方式进行了修改时，Java 编程语言保证兼容性。请注意，我们讨论的是应用程序版本之间的兼容性。Java SE 平台版本之间的兼容性讨论超出了本章的范围。

我们鼓励开发系统提供相关功能，提醒开发者更改对无法重新编译的现有二进制文件的影响。

本章首先介绍了任何 Java 编程语言二进制格式必须具备的某些属性 (§13.1)。它定义了二进制兼容性，解释了它是什么以及它不是什么 (§13.2)。最后它列举了包 (§13.3)、类 (§13.4) 和接口 (§13.5) 的大量可能的更改，并规定了这些更改哪些是保证保持二进制兼容性的，哪些不是。

偶尔，形如：(JVMS §.y) 的引用被用于指示《Java 虚拟机规范》（The Java Virtual Machine Specification, Java SE 11 Edition）中的概念。

## 13.1 二进制文件的形式

程序必须编译为《Java 虚拟机规范，Java SE 11 版》指定的类文件格式，或者编译为可以由 Java 编程语言编写的类加载器映射到该格式的表示形式。

对应类或接口声明的类文件必须具有某些属性。这些属性中的许多被专门选择，以支持保持二进制兼容性的源码转换。所需的属性如下：

1. 类或接口必须以其二进制名称命名，该名称必须满足以下约束：
   - 顶层类型 (§7.6) 的二进制名称是其规范化名称 (§6.7)。
   - 成员类型 (§8.5, §9.5) 的二进制名称由其直接包含类型的二进制名称组成，后跟 `$`，然后是该成员的简单名称。
   - 局部类 (§14.3) 的二进制名称由其直接包含类型的二进制名称组成，后跟 `$`，然后是一个非空数字序列，最后是局部类的简单名称。
   - 匿名类 (§15.9.5) 的二进制名称由其直接包含类型的二进制名称组成，后跟 `$`，然后是一个非空数字序列。
   - 泛型类或接口声明的类型变量 (§8.1.2, §9.1.2) 的二进制名称是其直接包含类型的二进制名称组成，后跟 `$`，然后是类型变量的简单名称。
   - 泛型方法 (§8.4.4) 声明的类型变量的二进制名称是声明方法的类型的二进制名称，后跟 `$`，然后是方法的描述符 (JVMS §4.3.3)，后跟 `$`，最后是类型变量的简单名称。
   - 泛型构造函数 (§8.8.4) 声明的类型变量的二进制名称是声明构造函数的类型的二进制名称，后跟 `$`，然后是构造函数的描述符 (JVMS §4.3.3)，后跟 `$`，最后是类型变量的简单名称。
2. 对另一个类或接口类型的引用必须是符号性的，并使用该类型的二进制名称。
3. 对常量变量 (§4.12.4) 字段的引用必须在编译时解析为常量变量初始化器所指示的值 v。
   - 如果此类字段是静态的，则二进制文件中不应存在对该字段的引用，包括声明该字段的类或接口。此类字段必须始终看起来已初始化 (§12.4.2)；字段的默认值（如果与 v 不同）绝不能被观察到。
   - 如果此类字段是非静态的，则二进制文件的代码中不应存在对该字段的引用，包含该字段的类除外。（这将是一个类而不是接口，因为接口只有静态字段。）
4. 给定一个表示类 `c` 中字段访问的合法表达式，其引用一个不是常量变量且在（可能是不同的）类或接口 `D` 中声明的字段 `f`，我们定义*字段引用的限定类型*（qualifying type of the field reference）如下：
   - 如果表达式通过简单名称引用，则如果 `f` 是当前类或接口 `c` 的成员，令 `τ` 为 `c`；否则，令 `τ` 为 `f` 成员的最内层词法包含类型声明。在何种情况下，`τ` 都是该引用的限定类型。
   - 如果表达式的形式为 `TypeName.f`，其中 `TypeName` 表示一个类或接口，则由 `TypeName` 表示的类型是该引用的限定类型。
   - 如果表达式的形式为 `ExpressionName.f` 或 `Primary.f`，则：
     - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交集 `V₁ & ... & Vₙ` (§4.9)，则引用的限定类型是 `V₁`。
     - 否则，`ExpressionName` 或 `Primary` 的编译时类型是引用的限定类型。
   - 如果表达式的形式为 `super.f`，则 `c` 的父类是该引用的限定类型。
   - 如果表达式的形式为 `TypeName.super.f`，则由 `TypeName` 表示的类的父类是该引用的限定类型。
   对 `f` 的引用必须编译为对字段 `f` 的符号引用。该引用还必须包含对字段声明类型擦除的符号引用，以便验证器检查类型是否符合预期。类在实例化期间应将字段的值设置为 v。
5. 给定类或接口 `c` 中的方法调用表达式或方法表达式，其引用在（可能是不同的）类或接口 `D` 中声明（或隐式声明 §9.2）的方法 `m`，我们定义*方法调用的限定类型*（qualifying type of the method invocation）如下：
   - 如果 `D` 是 `Object`，则表达式的限定类型是 `Object`。
   - 否则：
     - 如果方法通过简单名称引用，则如果 `m` 是当前类或接口 `c` 的成员，令 `τ` 为 `c`；否则，令 `τ` 为 `m` 成员的最内层词法包含类型声明。在何种情况下，`τ` 都是该方法调用的限定类型。
     - 如果表达式具有 `TypeName.m` 或 `ReferenceType::m` 形式，则由 `TypeName` 或 `ReferenceType` 表示的类型是该方法调用的限定类型。
     - 如果表达式具有 `ExpressionName.m` 或 `Primary.m` 或 `ExpressionName::m` 或 `Primary::m` 形式，则：
       - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交叉类型 `V₁ & ... & Vⱼ` (§4.9)，则该方法调用的限定类型为 `Vⱼ`。
       - 否则，`ExpressionName` 或 `Primary` 的编译时类型是该方法调用的限定类型。
     - 如果表达式具有 `super.m` 或 `super::m` 形式，则 `C` 的超类是该方法调用的限定类型。
     - 如果表达式具有 `TypeName.super.m` 或 `TypeName::super::m` 形式，如果 `TypeName` 表示一个类 `x`，则 `X` 的超类是该方法调用的限定类型；如果 `TypeName` 表示一个接口 `x`，则 `x` 是该方法调用的限定类型。
   对调用限定类型的擦除 (§4.6) 的引用必须在编译时解析为一个符号引用，外加上方法签名 (§8.4.2) 的擦除。方法的签名必须根据 §15.12.3 的确定，包含以下所有内容：
   - 方法的简单名称
   - 方法的参数数量
   - 每个参数类型的符号引用
   对对方法的引用还必须包含对所表示的方法返回类型擦除的符号引用，或者指示所表示的方法不返回值。
6. 鉴于类实例创建表达式 (§15.9)、显式构造函数调用语句 (§8.8.7.1) 或在类或接口 `c` 中引用在（可能是不同的）类或接口 `D` 中声明的构造函数 `m` 的具有 `ClassType :: new` 形式的方法引用表达式，我们将构造函数调用的限定类型定义如下：
   - 如果表达式具有 `new D(...)` 或 `ExpressionName.new D(...)` 或 `Primary.new D(...)` 或 `D :: new` 形式，则调用的限定类型为 `D`。
   - 如果表达式具有 `new D(...) {...}` 或 `ExpressionName.new D(...) {...}` 或 `Primary.new D(...) {...}` 形式，则表达式的限定类型为表达式的编译时类型。
   - 如果表达式具有 `super(...)` 或 `ExpressionName.super(...)` 或 `Primary.super(...)` 形式，则表达式的限定类型为 `C` 的直接超类。
   - 如果表达式具有 `this(...)` 形式，则表达式的限定类型为 `C`。
   对构造函数的引用必须在编译时解析为对调用限定类型擦除 (§4.6) 的符号引用，外加上构造函数的签名 (§8.8.2)。构造函数的签名必须包含：
   - 构造函数的参数数量
   - 每个形式参数类型的符号引用

一个类或接口的二进制表示还必须包含以下所有内容：

1. 如果它是一个类且不是 `Object`，则指向该类的直接超类擦除的符号引用。
2. 如果存在，则指向每个直接超接口擦除的符号引用。
3. 类或接口中声明的每个字段的规范，给出字段的简单名称和字段类型擦除的符号引用。
4. 如果它是一个类，则包含上述的每个构造函数的擦除签名。
5. 对于类或接口中声明的每个方法（对于接口，排除其隐式声明的方法 (§9.2)），包含上述的擦除签名和返回类型。
6. 实现该类或接口所需的代码：
   - 对于接口，字段初始化代码以及具有块体的方法的实现 (§9.4.3)。
   - 对于类，字段初始化代码、实例化和静态初始化代码、每个具有块体的方法的实现 (§8.4.7)，以及每个构造函数的实现。
7. 每个类型必须包含足够的信息来恢复其规范名称 (§6.7)。
8. 每个成员类型必须有足够的信息来恢复其源级访问修饰符。
9. 每个嵌套类和嵌套接口必须包含对其直接包围类型的符号引用 (§8.1.3)。
10. 每个类必须包含对其所有成员类型 (§8.5) 的符号引用，以及对出现在其方法、构造函数、静态初始化、实例化和字段初始化中的所有局部类和匿名类的符号引用。
    每个接口必须包含对其所有成员类型 (§9.5) 的符号引用，以及对出现在其默认方法和字段初始化中的所有局部类和匿名类的符号引用。
11. 如果 Java 编译器生成的构造不对应于源代码中显式或隐式声明的构造，则必须标记为 `synthetic`（合成），除非该构造是类初始化方法 (JVMS §2.9)。
12. 如果 Java 编译器生成的构造对应于源代码中显式或隐式声明的构造，则必须标记为 `mandated`（强制的），除非该构造是类初始化方法 (JVMS §2.9)。

以下构造在源代码中声明，但没有被标记为强制性，因为只有类可以被标记 (JVMS §4.24)：
- 默认构造函数 (§8.9)
- 匿名构造函数 (§15.9.5)
- 枚举类类型的 `values` 和 `valueOf` 方法 (§8.3)
- 枚举类中的某些 `public` 字段 (§8.3)
- 接口的某些 `public` 方法 (§9.2)

对应模块声明的类文件必须具有一个名为 `module-info` 的类的属性，该类没有超类、超接口、字段和方法。此外，模块的二进制表示必须包含以下所有内容：

- 模块名称的规范，给出对 `module` 后的符号引用。此外，规范必须包括该模块是否为 `normal` 或 `open` (§7.7)。
- 由 `requires` 指令指定的每个依赖，给出对指令指示的模块名的符号引用 (§7.7.1)。此外，规范必须包括该依赖是否具有传递性以及是否是静态的。
- 由 `exports` 或 `opens` 指令指定的每个包，给出对指令指示的包名的符号引用 (§7.7.2)。此外，如果指令是限定的，规范必须给出指令子句中指示的模块名的符号引用。
- 由 `uses` 指令指定的每个服务，给出对指令指示的类型名的符号引用 (§7.7.3)。
- 由 `provides` 指令指定的每个服务提供者，给出指令子句中指示的类型名的符号引用 (§7.7.4)。此外，规范必须给出对指令指示为服务的类型名的符号引用。

## 13.2 什么是二进制兼容性，什么不是

如果对类型的更改与现有的二进制文件兼容（等同于没有破坏二进制兼容性），则之前链接无错误的二进制文件将继续无错误地链接。

二进制文件在编译时依赖于其他类和接口的可访问成员和构造函数。为了保持二进制兼容性，类或接口应该将它的可访问成员和构造函数及其存在和行为，视为与其用户的契约。

Java 编程语言的设计目的是防止对契约的添加以及意外的名称冲突破坏二进制兼容性。具体而言，增加更多重载特定方法名的方法不会破坏与预存二进制文件的兼容性。预存二进制文件将用于方法查找的方法签名，是由重载解析算法在编译时确定的（见 §15.12.2）。

> 如果 Java 编程语言的设计使得执行特定方法在运行时才确定，那么在运行时可能会检测到歧义。这种规则意味着，添加一个额外的重载方法导致在调用处产生歧义，可能会破坏与无限数量预存二进制文件的兼容性。更多讨论请参阅 §13.4.6。

二进制兼容性不等同于源码兼容性。特别是 §13.4.6 中的示例表明，可以从源代码中生成一组二进制文件，但这些源代码无法完全一起编译。这种示例是典型的：添加了一个新声明，改变了源代码中未更改部分的某个名称的含义，而该未更改部分的预存二进制文件保留了该名称完全限定的先前含义。要产生一致的源代码集，需要提供与先前含义相对应的完全限定名称或字段访问表达式。

## 13.3 包和模块的演变

向包中添加新的顶层类或接口类型可能不会破坏与预存二进制文件的兼容性，前提是该新类型没有复用之前分配给无关类型的名称。如果新类型使用了之前分配给无关类型的名称，则可能会导致冲突，因为这两种类型的二进制文件将无法被同一个类加载器加载。

非公共且分别不是公共类型父类或超类的顶层类和接口类型的变化，仅影响其声明所在包内的类型。这些类型可以被删除或以其他方式更改，即使此处描述了不兼容的情况，只要该包受影响的二进制文件一起更新即可。

如果一个声明为导出或打开某个包的模块更改为不导出或打开该包，或者导出/打开给不同的访问集合，那么当链接一个需要但不再访问该包公共和受保护类型的预存二进制文件时，将抛出 `IllegalAccessException`。对于已广泛分发的模块，不建议进行此类更改。

如果一个模块未声明为导出或打开给定的包，则将模块更改为导出或打开该包不会破坏与预存二进制文件的兼容性。然而，将模块更改为导出该包可能会阻止程序启动，读取该模块的任何模块也可能读取导出相同包的其他模块。

在模块声明中添加 `requires` 指令，或在 `requires` 指令中添加 `transitive`（传递性）修饰符，不会破坏与预存二进制文件的兼容性。但它可能会阻止程序启动，因为该模块现在可能读取多个导出同名包的模块。

在模块声明中删除 `requires` 指令，或从 `requires` 指令中删除 `transitive` 修饰符，可能会破坏任何依赖该指令的预存二进制文件，或在引用该模块导出的类型时对该模块的可读性产生破坏。当链接此类来自预存二进制文件的引用时，可能会抛出 `IllegalAccessError`。

在模块声明中添加或删除 `uses` 或 `provides` 指令，不会破坏与预存二进制文件的兼容性。

## 13.4 类的演变

本节描述了对类及其成员、构造函数声明的更改对预存二进制文件的影响。

### 13.4.1 抽象类

如果一个未声明为抽象的类被更改为声明为抽象，那么尝试创建该类新实例的预存二进制文件将在链接时抛出 `InstantiationError`，或者（如果使用了反射方法）在运行时抛出 `InstantiationException`；因此，对于广泛分发的类不建议进行此类更改。

将一个声明为抽象的类更改为不再声明为抽象不会破坏与预存二进制文件的兼容性。

### 13.4.2 final 类

如果一个未声明为 `final`（最终）的类被更改为声明为 `final`，那么当加载该类的预存子类的二进制文件时，将抛出 `VerifyError`，因为 `final` 类不能有子类；对于广泛分发的类不建议进行此类更改。

将一个声明为 `final` 的类更改为不再声明为 `final` 不会破坏与预存二进制文件的兼容性。

### 13.4.3 公共类

将一个未声明为公共的类更改为声明为公共不会破坏与预存二进制文件的兼容性。

如果一个声明为公共的类被更改为不再声明为公共，那么当链接需要但不再访问该类类型的预存二进制文件时，将抛出 `IllegalAccessError`；对于广泛分发的类不建议进行此类更改。

### 13.4.4 父类和超接口

如果一个类成为自身的父类，则在加载时将抛出 `ClassCircularityError`。类层次结构的变化可能会在新编译的二进制文件与预存二进制文件加载时导致这种循环引用，对于广泛分发的类不建议进行此类更改。

更改直接父类或直接超接口不会破坏与预存二进制文件的兼容性，前提是该类型的总父类或超接口集没有丢失成员。

如果对直接父类或直接超接口的更改导致任何类或接口不再是父类或超接口，那么在加载该类的预存二进制文件时，可能会导致链接错误。对于广泛分发的类不建议进行此类更改。

#### 示例 13.4.4-1. 更改父类

假设以下测试程序：

```
```


## 类的演化与二进制兼容性

### 示例：验证器的重要性

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

经过编译并执行，产生输出：`h`

假设重新编译一个新版本的 `Super` 类：

```java
class Super { char s = 's'; }
```

此版本的 `Super` 类不再是 `Hyper` 的子类。如果我们用新版本的 `Super` 运行 `Hyper` 和 `Test` 的现有二进制文件，则会在链接时抛出 `VerifyError`。验证器会报错，因为 `new Super()` 的结果不能作为 `Hyper` 类型的形式参数传递，因为 `Super` 不是 `Hyper` 的子类。

考虑如果没有验证步骤会发生什么是有启发的：程序可能会运行并打印：

```
s
```

这证明了如果没有验证器，Java 类型系统中由于链接不一致的二进制文件而被破坏，尽管每个文件都是正确的 Java 编译器产生的。

教训是，缺乏验证器或未能使用验证器的实现将无法维护类型安全，因此不是有效的实现。

### 多捕获子句中的异常关系

在多捕获子句（§14.20）中异常彼此不是子类或超类的要求仅是源码限制。假设以下客户端代码：

```java
try {
    throwAoB();
} catch (ExceptionA | ExceptionB e) {
}
```

当 `ExceptionA` 和 `ExceptionB` 在客户端编译时没有子类/超类关系时，当客户端执行时，`ExceptionA` 和 `ExceptionB` 具有这种关系对于客户端来说是二进制兼容的。

这类似于其他情况，即对于客户端来说是二进制兼容的类转换对于该客户端可能并不是源码兼容的。

---

## 13.4.5 类类型参数

添加或删除类的类型参数本身不会对二进制兼容性产生任何影响。

如果此类类型参数被用于字段或方法的类型中，则可能会产生更改上述类型所带来的正常影响。

重命名类的类型参数对预先存在的二进制文件没有影响。

更改任何其他边界（bound）对二进制兼容性没有影响。

---

## 13.4.6 类体和成员声明

添加一个与父类或子类的实例（或静态）成员具有相同名称和访问权限（对于字段），或具有相同名称、访问权限、签名和返回类型（对于方法）的实例（或静态）成员，由于其重叠性，不会导致与预先存在的二进制文件不兼容。即使正在链接的类集合在编译时会遇到错误，也不会发生错误。

删除一个未声明为私有的成员或构造函数，如果该成员或构造函数被预先存在的二进制文件使用，可能会导致链接错误。

### 示例 13.4.6-1. 修改类体

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

该程序产生输出：`hello from Super`

假设产生了类 `Super` 的新版本：

```java
class Super extends Hyper {
}
```

那么，重新编译 `Super` 并与 `Test` 和 `Hyper` 的原始二进制文件一起执行此二进制文件将产生输出：`hello from Hyper`

这是预期的。

`super` 关键字可以用于访问父类中声明的方法，跳过当前类中声明的任何方法。表达式 `super.Identifier` 在编译时被解析为父类 `S` 中的方法 `m`。如果方法 `m` 是一个实例方法，那么在运行时调用的方法是包含表达式 `super` 的类的直接父类中具有相同签名的方法。

### 示例 13.4.6-2. 修改父类

```java
class Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}

class Super extends Hyper {
    class Test extends Super {
        public static void main(String[] args) {
            new Test().hello();
        }

        void hello() {
            super.hello();
        }
    }
}
```

该程序产生输出：`hello from Hyper`

假设产生了类 `Super` 的新版本：

```java
class Super extends Hyper {
    void hello() { System.out.println("hello from Super"); }
}
```

那么，如果重新编译了 `Super` 和 `Hyper` 但没有编译 `Test`，通过现有的 `Test` 二进制文件运行新的二进制文件将产生输出：`hello from Super`

正如你预期的那样。

---

## 13.4.7 成员和构造函数的访问

更改成员或构造函数的访问权限以允许更少的访问可能会破坏与预先存在的二进制文件的兼容性，导致在解析这些二进制文件时抛出链接错误。如果修饰符从包访问改为*私有访问*；从*受保护*访问改为包访问或*私有访问*；或从公共访问改为*受保护*、包或*私有访问*，则允许更少的访问。因此，不建议对广泛分发的类更改成员或构造函数以允许更少的访问。

也许令人惊讶的是，二进制格式的定义使得更改成员或构造函数以具有更高的访问权限时，即使子类（已经）定义了一个方法具有更少的访问权限，也不会导致链接错误。

### 示例 13.4.7-1. 修改访问权限

如果包 `points` 定义了类 `Point`：

```java
package points;

public class Point {
    public int x, y;

    protected void print() {
        System.out.println("*" + x + "*" + y + "*");
    }
}
```

被程序使用：

```java
class Test extends Point {
    public static void main(String[] args) {
        Test t = new Test();
        t.print();
    }

    protected void print() {
        System.out.println("*Test*");
    }
}
```

那么这些类可以编译并且 `Test` 执行以产生输出：`Test`

如果类 `Point` 中的方法 `print` 变为 `public`，然后只重新编译 `Point` 类，并使用之前存在的 `Test` 二进制文件进行执行，则不会发生链接错误。尽管在编译时，一个 `public` 方法被 `protected` 方法覆盖是不恰当的（事实证明，除非将 `Test` 中的 `print` 更改为 `public`，否则无法使用这个新的 `Point` 类重新编译 `Test` 类)。

允许子类将受保护的方法更改为公共而不破坏预先存在的子类的二进制文件，这有助于使二进制文件不那么脆弱。另一种方案（即此类更改会导致链接错误）将产生额外的二进制不兼容性。

---

## 13.4.8 字段声明

广泛分发的程序不应向客户端暴露字段。除了下面讨论的二进制兼容性问题外，这通常是良好的软件工程实践。向类添加字段可能会破坏与未重新编译的预先存在的二进制文件的兼容性。

假设有一个限定类型 `t` 的字段 `f`。进一步假设 `f` 是在 `t` 的子类 `s` 中声明的实例（或静态）字段，且 `f` 的类型为 `x`。

如果在 `t` 的父类 `s` 的子类中添加了与 `f` 名称相同的新类型 `x`，则可能会发生链接错误。只有在满足上述条件的基础上满足以下条件之一，才会发生此类链接错误：

- 新字段的访问权限比旧字段低。
- 新字段是静态（或实例）字段。

特别地，当类之前引用了不兼容类型的字段时，不会发生链接错误。之前编译的类将继续引用父类中声明的字段。

### 示例 13.4.8-1. 添加字段

```java
class Hyper { String h = "hyper"; }

class Super extends Hyper { String s = "super"; }

class Test {
    public static void main(String[] args) {
        System.out.println(new Super().h);
    }
}
```

该程序产生输出：`hyper`

假设产生了类 `Hyper` 的新版本：

```java
class Super extends Hyper {
    String s = "super";
}

int h = 0;
}
```

那么，重新编译 `Hyper` 和 `Super`，并使用 `Test` 的旧二进制文件执行生成的二进制文件将产生输出：`hyper`

`Test` 的原始二进制文件输出了 `Hyper` 的字段 `h`。虽然这看起来很奇怪，但它有助于减少运行时发生的不兼容性。在理想世界中，每当一个文件发生变化时，所有需要重新编译的文件都会重新编译，从而消除意外。但这种重新编译是不现实或不可能的，特别是在互联网上。而且如之前所述，这种重新编译有时需要对源码进行进一步更改。

另一个例子，如果程序：

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

被编译并且它产生输出：`Hyper`

假设然后编译了类 `Super` 的版本：

```java
class Super extends Hyper { char h = 'h'; }
```

如果生成的二进制文件与 `Hyper` 和 `Test` 的现有二进制文件一起使用，则输出为：`Hyper`

即使编译这些二进制文件的源码结果是这样的：

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

这种操作不会导致现有的二进制文件无法运行，但除非重新编译，否则它们将无法看到该字段使用的任何新值。这一结果是支持条件编译（§14.21）决定的副作用。（人们可能认为，如果该使用发生在常量表达式（§15.28）中，则看不到新值，而在其他情况下则可见。事实并非如此；预先存在的二进制文件完全看不到新值。）

在广泛分发的代码中，避免“伪常量”问题的最佳方法是仅将静态变量用于那些真正不太可能改变的值。除了真正的数学常数外，我们建议源代码中应非常节制地使用静态常量变量。

如果需要 `final` 的只读特性，更好的选择是声明一个私有静态变量以及一个适当的访问器来获取其值。我们建议：

```java
private static int N;
public static int getN() { return N; }
```

而不是：

```java
public static final int N = ...;
```

如果 `N` 不需要是只读的，那么这种写法是没有问题的：

```java
public static int N = ...;
```

---

## 13.4.10 静态字段

如果一个声明为 `private` 的字段未声明为 `static` 但被改为 `static`，或者反之，当该字段被一个期望另一种字段的现有二进制文件使用时，会导致链接错误，特别是 `IncompatibleClassChangeError`。不建议在已广泛发布的代码中进行此类更改。

---

## 13.4.11 transient 字段

添加或删除字段的 `transient` 修饰符不会破坏与现有二进制文件的兼容性。

---

## 13.4.12 方法和构造函数声明

向类中添加方法或构造函数声明不会破坏与任何现有二进制文件的兼容性，即使在某些情况下，由于之前的调用引用了父类中不兼容的方法或构造函数，导致该类型无法重新编译。具有此类引用的之前编译的类将继续引用父类中声明的方法或构造函数。

假设有一个限定类型为 $\tau$ 的方法引用 $m$。进一步假设 $m$ 实际上是在 $\tau$ 的父类 $S$ 中声明的实例方法（或为静态方法）。

如果在 $\tau$ 的父类或 $\tau$ 本身的子类中，添加了一个与 $m$ 具有相同签名和返回类型的类型 $x$ 的新方法，那么只有在满足以下任一条件的情况下，才会发生链接错误：

- 新方法的访问权限比旧方法低。
- 新方法是静态方法（或为实例方法）。

从类中删除方法或构造函数可能会破坏任何引用了该方法或构造函数的现有二进制文件的兼容性；当从现有二进制文件的此类引用进行链接时，可能会抛出 `NoSuchMethodError`。只有在父类中没有声明具有匹配签名和返回类型的情况下，才会发生此类错误。

如果非内部类的源代码不包含声明的构造函数，则会隐式声明一个无参数的默认构造函数（§8.9）。在此类类的源代码中添加一个或多个构造函数声明将防止此默认构造函数被隐式声明，实际上删除了构造函数，除非其中一个新构造函数没有参数，从而替换了默认构造函数。无参数的默认构造函数的访问修饰符与其定义的类相同，因此，为了保持与现有二进制文件的兼容性，任何替换都应该具有相同或更高的访问权限。

---

## 13.4.13 方法和构造函数的类型参数

添加或移除方法或构造函数的类型参数本身不会对二进制兼容性产生任何影响。

如果此类类型参数被用于方法或构造函数的类型中，则可能会产生更改上述类型所具有的标准影响。

重命名方法或构造函数的类型参数对现有二进制文件没有影响。

更改方法或构造函数类型参数的第一个边界（bound）可能会更改在其自身类型中使用该类型参数的成员的擦除（§4.6），这可能会影响二进制兼容性。具体而言：

- 如果类型参数被用作字段的类型，其效果等于该字段被删除并添加了具有相同名称的字段，该名称是类型变量的新擦除。
- 如果类型参数被用作方法任何形式参数的类型，但没有作为返回类型，其效果等于该方法被删除，并替换为一个新方法，该新方法在上述形式参数的类型上是相同的，而这些参数现在以类型参数的新擦除作为其类型。
- 如果类型参数被用作方法的返回类型，但没有作为方法任何形式参数的类型，其效果等于该方法被删除，并替换为一个新方法，该新方法除返回类型外是相同的，而返回类型现在是类型参数的新擦除。
- 如果类型参数既是方法的返回类型，又是该方法的一个或多个形式参数的类型，其效果等于该方法被删除，并替换为一个新方法，该新方法除返回类型（其返回类型现在是类型参数的新擦除）以及上述形式参数的类型外是相同的（这些形式参数现在以类型参数的新擦除作为其类型）。

更改任何其他边界对二进制兼容性没有影响。

---

## 13.4.14 方法和构造函数的形式参数

更改方法或构造函数的形式参数名称不会影响现有二进制文件。

更改方法名称、方法或构造函数形式参数的类型，或通过添加参数来删除方法或构造函数声明中的参数，将创建一个具有新签名的方法或构造函数，并产生删除旧签名方法或构造函数与添加具有新签名的方法或构造函数的组合效果（§13.4.12）。

将方法的最后一个形式参数的类型从 `T[]` 更改为类型 `T` 的可变长度参数（§8.4.1）（即 `T...`），反之亦然，不会影响现有二进制文件。

为了二进制兼容性，添加或移除签名涉及类型变量（§4.4）或泛型类型（§4.5）的方法或构造函数 $m$，等同于添加（或移除）另一个等效的方法，其签名是 $m$ 签名的擦除（§4.6）。

---

## 13.4.15 方法结果类型

更改方法的返回类型，或将结果类型替换为 `void`，或将 `void` 替换为结果类型，具有删除旧方法并添加具有新结果类型或新 `void` 结果方法的组合效果（见 §13.4.12）。

为了二进制兼容性，添加或移除返回类型涉及类型变量（§4.4）或泛型类型（§4.5）方法或构造函数 $m$，等同于添加（或移除）另一个等效的方法，其返回类型是 $m$ 返回类型的擦除（§4.6）。

---

## 13.4.16 抽象方法

将声明为 `abstract` 的方法改为不再声明为 `abstract` 不会破坏与现有二进制文件的兼容性。

将未声明为 `abstract` 的方法改为声明为 `abstract` 将破坏之前调用过该方法的现有二进制文件的兼容性，导致 `AbstractMethodError`。

> **示例 13.4.16-1. 将方法改为 `abstract`**
>
> ```java
> ```



```java
class Super { void out() { System.out.println("Out"); } }

class Test extends Super {

    public static void main(String[] args) {

        Test t = new Test();

        System.out.println("Way ");

    }

}
```

该程序产生输出：

```
Way
Out
```

假设产生了一个版本的 `Super` 类：

```java
abstract class Super {

    abstract void out();

}
```

# 二进制兼容性

## 类的演化

### 13.4

如果 `Super` 重新编译但 `Test` 没有重新编译，使用现有的 `Test` 二进制运行新的二进制文件将导致 `AbstractMethodError`，因为类 `Test` 没有对 `out` 方法的实现，因此它是抽象的（或应该是抽象的）。

### 13.4.17 final 方法

将一个已声明为 `final` 的方法更改为不再声明为 `final` 不破坏与现有二进制文件的兼容性。

将一个未声明为 `final` 的实例方法更改为声明为 `final` 可能会破坏依赖重写该方法的现有二进制文件的兼容性。

示例 13.4.17-1. 将方法改为 final

```java
class Super { void out() { System.out.println("out"); }}

class Test extends Super {

    public static void main(String[] args) {

        Test t = new Test();

        t.out();

    }

    void out() { super.out(); }

}
```

该程序产生输出：

```
out
```

假设产生了类 `Super` 的新版本：

```java
class Super { final void out() { System.out.println("*!"); } }
```

如果 `Super` 重新编译但 `Test` 没有重新编译，使用现有的 `Test` 二进制运行新的二进制文件将导致 `VerifyError`，因为类 `Test` 不恰地尝试重写实例 `out`。

将一个未声明为 `final` 的（静态）类更改为声明为 `final` 不破坏现有二进制文件的兼容性，因为该方法本就不被重写。

### 13.4.18 native 方法

添加或删除方法的 `native` 修饰符不破坏与现有二进制文件的兼容性。

类型更改对未重新编译的现有 `native` 方法的影响超出了本规范的范围，应在实现描述中提供。鼓励（但不是要求）实现以限制此类影响的方式来实现 `native` 方法。

### 13.4.19 static 方法

如果一个未声明为 `private` 的方法也被声明为 `static`（即类方法）并更改为不再声明为 `static`（即实例方法），反之亦然，则可能会破坏与现有二进制文件的兼容性。如果这些方法被现有二进制文件使用，会导致链接时错误，即 `IncompatibleClassChangeError`。不建议在广泛传播的代码中进行此类更改。

### 13.4.20 synchronized 方法

添加或删除方法的 `synchronized` 修饰符不破坏与现有二进制文件的兼容性。

### 13.4.21 方法和构造函数的 Throws 子句

方法或构造函数 `throws` 子句的更改不破坏与现有二进制文件的兼容性；这些子句仅在编译时检查。

### 13.4.22 方法和构造函数体

方法或构造函数体的更改不破坏与现有二进制文件的兼容性。

方法上的 `final` 关键字并不意味着该方法可以安全地内联；它仅意味着该方法不能被重写。在链接时仍可能提供方法的新版本。此外，为了反射的目的，必须保留原始程序的结构。

因此，请注意 Java 编译器无法在编译时展开内联。通常情况下，我们建议实现使用晚绑定（运行时）代码生成和优化。

### 13.4.23 方法和构造函数的重载

添加重载现有方法或构造函数的新方法或构造函数不破坏与现有二进制文件的兼容性。每次调用时使用的签名是在这些现有二进制文件编译时确定的；因此，新添加的方法或构造函数将不会使用，即使它们的签名既适用又比最初选择的签名更具体。

虽然添加新的重载方法或构造函数可能会在下次编译类或接口时引起编译时错误，因为没有最具体的方法或构造函数（§15.12.2.5），但在程序执行时不会发生此类错误，因为执行时不进行重载解析。

示例 13.4.23-1. 添加一个重载方法

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

假设产生了类 `Super` 的新版本：

```java
class Super {

    static void out(float f) { System.out.println("float"); }

    static void out(int i) { System.out.println("int"); }

}
```

如果 `Super` 重新编译但 `Test` 没有重新编译，使用现有的 `Test` 二进制运行新的二进制文件产生输出：

```
float
```

然而，如果随后重新编译 `Test` 使用这个新的 `Super`，输出将是：

```
int
```

正如在之前的情况下可能简单预期的那样样。

### 13.4.24 方法重写

如果在子类中添加了实例方法且它重写了父类中的方法，现有二进制文件中的方法调用将找到该子类方法，这些二进制文件不受影响。

如果在类中添加了类方法，除非引用引的限定类型是子类类型，否则将找不到该方法。

### 13.4.25 静态初始化器

添加、删除或更改类的静态初始化器（§8.7）不影响现有二进制文件。

### 13.4.26 枚举的演化

在枚举中添加或重新排序常量不会破坏与现有二进制文件的兼容性。如果现有的二进制文件尝试访问已不存在的枚举常量，客户端将在运行时因 `NoSuchFieldError` 失败。因此，不建议对广泛传播的枚举进行此类更改。

在所有其他方面，枚举的二进制兼容性与类相同。

## 接口的演化

本节描述接口及其成员的更改对现有二进制文件的影响。

### 13.5.1 public 接口

将未声明为 `public` 的接口更改为声明为 `public` 不破坏与现有二进制文件的兼容性。

如果声明为 `public` 的接口更改为不再声明为 `public`，当链接不再不再访问该接口的现有二进制文件时，将抛出 `IllegalAccessError`，因此不建议对广泛传播的接口进行此类更改。

### 13.5.2 父接口

接口层次的变化引起错误与类层次的变化的方式相同，如 §13.4.4 所示。特别是导致类的任何之前的父接口不再是父接口的更改可能会破坏现有二进制文件的兼容性，导致 `VerifyError`。

### 13.5.3 接口成员

向接口中添加抽象、私有或静态方法不破坏与现有二进制文件的兼容性。

向 `c` 的父接口中添加字段可能会有一个继承自 `c` 的父类的字段。如果原始引用是实例字段，将导致 `IncompatibleClassChangeError`。如果原始引用是赋值操作，将导致 `IllegalAccessError`。

从接口中删除成员可能会导致现有二进制文件的链接错误。

示例 13.5.3-1. 删除一个接口成员

```java
interface I { void hello(); }

class Test implements I {

    public static void main(String[] args) {

        I anI = new Test();

        anI.hello();

    }

    public void hello() { System.out.println("hello"); }

}
```

该程序产生输出：

```
hello
```

假设编译了接口 `I` 的新版本：

```java
interface I {

}
```

如果 `I` 重新编译但 `Test` 没有重新编译，使用现有的 `Test` 二进制运行新的二进制文件将导致 `NoSuchMethodError`。

### 13.5.4 接口类型参数

接口类型参数更改的影响与类类型参数更改的影响相同。

### 13.5.5 字段声明

接口中字段声明的考虑因素与类中 `static final` 字段的考虑因素相同，如 §13.4.8 和 §13.4.9 所示。

### 13.5.6 接口方法声明

接口中方法声明的考虑因素包括类中方法声明的考虑因素，如 §13.4.7、§13.4.14、§13.4.15、§13.4.19、§13.4.21、§13.4.22 和 §13.4.23 所示。

添加默认方法不会破坏现有二进制文件的兼容性，但如果现有的二进制文件尝试调用该方法，可能会导致 `IncompatibleClassChangeError`。如果限定类型 τ 是两个接口 `i` 和 `j` 的子类型，且 `i` 和 `j` 都声明了具有相同签名和结果的默认方法，且 `i` 和 `j` 均都不是对方的子接口，则发生错误。

换句话说，添加默认方法是一个二进制兼容的更改，因为它不会在编译时或调用时引入错误。引入默认方法导致意外冲突的风险与向非 `final` 类添加方法的风险相似。冲突的发生不太可能触发 `LinkageError`，但子类中对该方法的意外重写可能会导致不可预测的方法行为。两种更改都可能导致编译时错误。

示例 13.5.6-1. 添加默认方法

```java
interface Painter {

    void draw() {

        System.out.println("Here's a picture...");

    }

}

interface Cowboy {}

public class CowboyArtist implements Cowboy, Painter {

    public static void main(String... args) {

        new CowboyArtist().draw();

    }

}
```

该程序产生输出：

```
Here's a picture...
```

假设在 `Cowboy` 中添加了一个默认方法：

```java
interface Cowboy {

    default void draw() {

        System.out.println("Bang!");

    }

}
```

如果重新编译了 `Cowboy` 但没有重新编译 `CowboyArtist`，那么使用现有的 `CowboyArtist` 二进制文件运行新的二进制文件将无错误链接，但在 `main` 尝试调用 `draw()` 时会导致 `IncompatibleClassChangeError`。

### 13.5.7 注解类型的演变

注解类型的行为与任何其他接口完全相同。在注解类型中添加或删除元素类似于添加或删除方法。对于注解类型的其他更改，还有重要的考虑因素，例如使注解类型变为可重复的（§9.6.3），但这些对 Java 虚拟机对二进制文件的链接没有影响。相反，此类更改会影响操作注解的反射 API 的行为。这些 API 的文档说明了当对底层注解类型进行各种更改时的其行为。

添加或删除注解对 Java 语言程序二进制表示的正确链接没有影响。

## 第 14 章

# 块与语句

程序的执行序列由语句控制，语句的执行是为了产生效果，并且没有值。

某些语句包含其他语句作为结构的一部分；这些其他语句是该语句的子语句。如果不存在不同于 `s` 和 `v` 的语句 `τ` 使得 `s` 包含 `τ` 且 `τ` 包含 `v`，则我们称 `s` 立即包含 `v`。同样，某些语句也包含表达式（§15）作为其结构的一部分。

本章的第一节讨论了语句的正常完成与异常完成之间的区别（§14.1）。剩余的大部分章节解释了各种类型的语句，详细描述了它们的正常行为以及对异常完成的任何特殊处理。

首先解释了块（§14.2），然后是局部类声明（§14.3）和局部变量声明语句（§14.4）。

接下来解释了一种规避熟悉的“悬空 else”问题（§14.5）的语法手段。

本章的最后一节（§14.21）处理了每个语句在特定技术意义上必须是可达的这一要求。

## 14.1 语句的正常与异常完成

每个语句都有一种正常执行模式，其中会执行某些计算步骤。后续章节描述了每种语句的正常执行模式。

如果所有步骤都按照描述执行且没有异常完成的迹象，则该语句正常完成。然而，某些事件可能会阻止语句正常完成：

- `break`（§14.15）、`continue`（§14.16）和 `return`（§14.17）语句会导致控制转移，可能会阻止包含它们的语句正常完成。
- 某些表达式的求值可能会从 Java 虚拟机抛出异常（§15.6）。显式的 `throw`（§14.18）语句也会导致异常。异常会导致控制转移，可能会阻止语句的正常完成。

如果发生此类事件，一个或多个语句的执行在其正常执行模式的所有步骤完成之前终止；此类语句被称为异常完成。

异常完成总是有一个关联的原因，该原因是以下之一：

- 无标签的 `break`
- 带有给定标签的 `break`
- 无标签的 `continue`
- 带有给定标签的 `continue`
- 无返回的 `return`
- 带有给定标签的 `return`
- 带有给定值的 `throw`，包括 Java 虚拟机抛出的异常

表达式能够异常完成的唯一原因是异常（§15.6）。正常执行模式中的所有后续步骤将不再执行。

## 14.2 块

除非另有说明，否则如果块的所有语句都正常完成，则该块正常完成。如果这些语句中的任何一个异常完成，则该块因该原因异常完成。

块是语句、局部类声明和局部变量声明语句的序列。

```
Block:
  [BlockStatements]

BlockStatements:
  BlockStatement

BlockStatement:
  LocalDeclarationStatement
  Statement
```

块通过从第一个到最后一个（从左到右）执行其每个语句来执行。

局部类声明的作用范围涵盖其整个声明（而不只是其正体），这意味着局部类 `Cyclic` 的定义确实是循环的，因为它扩展的是自身而不是 `Global.Cyclic`。因此，正常执行模式中的所有后续步骤将不再执行。

## 14.3 局部类声明

局部类是嵌套类（§8），它不是任何类的成员且具有一个名称（§6.2）。

所有局部类都是内部类（§8.1.3）。每个局部类声明语句都被一个块（§14.2）立即包含。局部类声明语句可以在块中与其他类型的语句自由混合。

如果局部类声明包含任何的访问修饰符 `public`、`protected` 或 `private`（§6.6），或修饰符 `static`（§8.1.1），则会导致编译错误。

局部类的作用域和隐藏规定在 §6.3 和 §6.4。

示例 14.3-1. 局部类声明

此示例说明了上述规则的几个方面：

```java
class Global {

    class Cyclic {}

    void foo() {

        new Cyclic(); // 创建一个 Global.Cyclic

        class Cyclic extends Cyclic {} // 循环定义

        class Local {} {

            class Local {} // 编译错误

            class Local {} // 编译错误

        } class AnotherLocal {

            void bar() {

                class Local {} // OK

            }

            class Local {} // OK，不在之前的 Local 作用范围内

        }

    }

}
```



方法 `foo` 的第一个语句创建一个 `Global.Cyclic` 的实例而不是局部类 `Cyclic` 的实例，因为该语句出现在局部类声明的作用域之前。

局部类声明的作用域涵盖其整个声明（而不只是其主体），这意味着 `Cyclic` 的定义确实是循环，因为它扩展的是自身而不是 `Global.Cyclic`。因此，该类的声明在编译时被拒绝。

由于局部类名不能在同一个方法（构造函数或初始化器）中重新声明，因此第二个和第三个 `Local` 声明会导致错误。然而，可以在另一个更深嵌套的类的范围内重新声明 `Local`。

最后的 `Local` 方法声明是合法的，因为它位于任何先前 `Local` 声明的作用域之外。

## 14.4 局部变量声明语句

局部变量声明语句声明一个或多个局部变量名。

```
LocalVariableDeclarationStatement:
    LocalVariableDeclaration;

LocalVariableDeclaration:
    {VariableModifier} LocalVariableType VariableDeclaratorList

LocalVariableType:
    UnannType
    var
```

关于 `UnannType` 见 §8.3。为了方便起见，这里展示了 §4.3、§8.3 和 §8.4.1 中的产生式：

*   **VariableModifier:**
    Annotation
    final

*   **VariableDeclaratorList:**
    VariableDeclarator (, VariableDeclarator)

*   **VariableDeclarator:**
    VariableDeclaratorId = VariableInitializer

*   **VariableDeclaratorId:**
    Identifier [Dims]

*   **Dims:**
    [Annotation] { [Annotation] }

*   **VariableInitializer:**
    Expression
    ArrayInitializer

每个局部变量声明语句都立即包含在一个块中。局部变量声明语句可以在块中与其他类型的语句自由混合。

除了局部变量声明语句外，局部变量可以通过基础 `for` 语句头部（§14.14.1）、增强 `for` 语句（§14.14.2）或 `try-with-resources` 语句（§14.20.3）进行声明。

局部变量声明上注解修饰符的规则规定在 §9.7.4 和 §9.7.5。

如果 `final` 作为局部变量声明的修饰符出现超过一次，则为编译错误。

如果 `LocalVariableType` 为 `var` 且满足以下任一条件，则为编译错误：

*   列出了多个 `VariableDeclarator`（变量声明符）。
*   `VariableDeclaratorId` 具有一个或多个括号对。
*   `VariableDeclarator` 缺少初始化器。
*   `VariableDeclarator` 的初始化器是一个 `ArrayInitializer`（数组初始化器）。
*   `VariableDeclarator` 的初始化器包含对变量的引用。

### 示例 14.4-1. 使用 `var` 声明的局部变量

以下代码说明了限制 `var` 使用的规则：

```
var a = 1;                   // 合法
var b = 2, c = 3.0;      // 非法：多个声明符
var d[] = new int[4];    // 非法：额外的括号对
var e;                    // 非法：无初始化器
var f = { 6 };             // 非法：数组初始化器
var g = (g = 7);          // 非法：初始化器中的自引用
```

这些限制有助于避免对 `var` 所表示的类型产生混义。

## 14.4.1 局部变量声明符和类型

局部变量声明中的每个声明符都声明一个局部变量，其名称即为声明符中出现的 `Identifier`（标识符）。

如果可选关键字 `final` 出现在声明开头，则被声明的变量是一个 `final` 变量（§14.12.4）。

局部变量的声明类型确定如下：

*   如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中没有出现括号对，则 `UnannType` 表示了该局部变量的类型。
*   如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号对，则局部变量的类型由 §10.2 规定。
*   如果 `LocalVariableType` 为 `var`，则令 τ 为初始化表达式在被视为未出现在赋值上下文中、从而作为独立表达式处理时的类型（§15.2）。局部变量的类型是 τ 相对于 τ 所提到的所有合成类型变量的向上投影（§14.10.5）。

如果 τ 是空类型（null type），则为编译错误。

由于初始化器被视为未出现在赋值上下文中，如果它是 lambda 表达式（§15.27）或方法引用表达式（§15.13），则发生错误。

### 示例 14.4.1-1. 使用 `var` 声明的局部变量的类型

以下代码说明了用以下方式声明的变量类型：

```
var a = 1; // a 类型为 'int'
var b = java.util.List.of(1, 2); // b 类型为 'List<Integer>'
var c = "x".getClass(); // c 类型为 'Class<? extends String>'
//（见 JLS 15.1.2.6）
var d = new Object(); // d 是匿名类的类型
var e = (CharSequence & Comparable<String>)"x"; // e 类型为 'CharSequence & Comparable<String>'
var f = () -> "hello"; // 非法：lambda 不在赋值上下文中
var g = null; // 非法：空类型
```

注意，某些变量不能用显式类型声明，因为变量的类型是不可指定的。

在确定变量类型时，允许向上投影到初始化器的类型。如果初始化器包含捕获变量，则此投影会将初始化器的类型映射到不包含捕获变量的超类。

可以允许变量的类型捕获变量，但通过将它们投影出去，我们强制了一种严格的不变性：捕获变量的作用范围永远不会大于包含其被捕获表达式的语句。非正式地说，捕获变量不会“泄漏”到后续语句中。

`float` 类型的局部变量始终包含 `float` 值集中的元素（§4.2.3）；同样，`double` 类型的局部变量始终包含 `double` 值集中的元素。不允许局部变量处于未初始化的状态。

## 14.4.2 局部变量声明的执行

局部变量声明是一个执行语句。每当执行时，从左到右处理声明符。如果声明符有初始化器，则会将初始化器赋值给变量。

## 14.5 语句

Java 语言中有许多类型的语句。大多数对应于 C 和 C++ 语言，但有些是独特的。

与 C 和 C++ 一样，Java 语言的 `if` 语句存在所谓的“悬空 else”问题，如下误导性的格式示例：

```
if (door.isOpen())
    if (resident.isVisible())
        resident.greet("Hello!")
else 
    door.bell.ring();
```

问题在于 `if` 语句和内部 `if` 语句都可能拥有 `else` 子句。人们可能会推断程序员希望让 `else` 子句属于外部 `if` 语句。

Java 语言像 C、C++ 以及之前的许多语言一样，任意规定 `else` 子句属于它可能所属的最内层 `if`。这一简单规则防止了“悬空 else”问题。带有“无短 if”限制的语句的执行行为与不带该限制的相同语句的执行行为完全相同；这种区分纯粹是为了解决语法困难。

```
StatementNoShortIf:
    StatementWithoutTrailingSubstatement
    LabeledStatementNoShortIf
    IfThenElseStatementNoShortIf
    WhileStatementNoShortIf
    ForStatementNoShortIf
```

```
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
```

为了方便，这里展示了 §14.9 中的产生式：

```
IfThenStatement:
    if ( Expression ) Statement

IfThenElseStatement:
    if ( Expression ) StatementNoShortIf else Statement

IfThenElseStatementNoShortIf:
    if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

## 14.6 空语句

空语句不执行任何操作。

```
EmptyStatement:
    ;
```

空语句的执行总是正常完成的。

## 14.7 标记语句

语句可以带有标签前缀。

```
LabeledStatement:
    Identifier : Statement

LabeledStatementNoShortIf:
    Identifier : StatementNoShortIf
```

该 `Identifier` 被声明为紧邻包含的 `Statement` 的标签。

与 C 和 C++ 不同，Java 编程语言没有作为标签的标记标识符，也没有 `goto` 语句；标识符语句标签用于标记语句内部任何地方的 `break` 或 `continue` 语句（§14.15, §14.16）。

标记语句的标签的作用域是紧邻包含的 `Statement`。

如果在标记语句的标签名称在该标签的作用域内被用另一个标记语句的标签使用，则会发生编译错误。

程序不限制将相同的标识符既作为标签，又作为包、类、接口、方法、字段、参数或局部变量的名字。使用标识符标记语句不会遮蔽（§6.4.2）具有同名的包、类、接口、方法、字段、参数或局部变量。将标识符作为类、接口、方法、字段、局部变量或异常处理器的参数（§14.20）使用，不会遮蔽具有同名的语句标签。

标记语句通过执行紧邻包含的 `Statement` 来执行。

如果语句被一个 `Identifier` 标记，并且所包含的 `Statement` 因为一个带有相同 `Identifier` 的 `break` 而异常完成，则该标记语句正常完成。在 `Statement` 异常完成的所有其他情况下，该标记语句将以相同的原因异常完成。

### 示例 14.7-1. 标签与标识符

以下代码取自 `String` 类及其 `indexOf` 方法的一个版本，其中标签最初的名为 `test`。将标签更改为与局部变量 `i` 相同的名称不会遮蔽 `i` 声明作用域内的该标签。因此，该代码是有效的。

```
class Test {
    char[] value;
    int offset, count;

    int indexOf(TestString str, int fromIndex) {
        char[] v1 = value, v2 = str.value;
        int max = offset + (count - str.count);
        int start = offset + ((fromIndex < 0) ? 0 : fromIndex);

        for (int i = start; i <= max; i++) {
            int n = str.count, j = i, k = str.offset;
            while (n-- != 0) {
                if (v1[j++] != v2[k++])
                    continue i;
            }
            return i - offset;
        }
        return -1;
    }
}
```

标识符 `max` 也可以用作语句标签；该标签不会遮蔽标记语句内的局部变量 `max`。

## 14.8 表达式语句

某些类型的表达式可以通过在其后加上分号来作为语句。

```
ExpressionStatement:
    StatementExpression;
```

```
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

与 C 和 C++ 不同，Java 编程语言仅允许某些形式的表达式作为表达式语句。例如，使用方法调用表达式（§15.12）是合法的：

```
System.out.println("Hello world"); // OK
```

但使用带括号的表达式（§15.8.5）是不合法的：

```
(System.out.println("Hello world")); // illegal
```

注意，Java 编程语言不允许向 "void" 强制转换——`void` 不是一种类型——因此传统的 C 技巧（编写如下的表达式语句）：

```
(void);; // incorrect!
```

是不可行的。另一方面，Java 编程语言允许在表达式语句中使用所有最有用的表达式类型，并且并不要求作为表达式语句使用的方法调用必须调用 `void` 方法，这种技巧几乎永远不需要。如果需要这种技巧，可以使用赋值语句（§15.26）或局部变量声明语句（§14.4）来代替。

## 14.9 if 语句

`if` 语句允许对语句进行条件执行，或对两个语句进行条件选择，执行其中一个而不是两个都执行。

```
IfThenStatement:
    if ( Expression ) Statement

IfThenElseStatement:
    if ( Expression ) StatementNoShortIf else Statement

IfThenElseStatementNoShortIf:
    if ( Expression ) StatementNoShortIf else StatementNoShortIf
```



`Expression` 必须具有 `boolean` 或 `Boolean` 类型，否则将发生编译错误。

## 14.9.1 if-then 语句

`if-then` 语句通过首先求值 `Expression` 来执行。如果结果是 `Boolean` 类型，则要经过拆箱转换（§5.1.8）。

如果 `Expression` 的求值或后续的拆箱转换（如果有）由于某种原因异常完成，则 `if-then` 语句以相同的原因异常完成。

否则，根据结果的值继续执行：

- 如果值为 `true`，则执行包含的 `Statement`；当且仅当 `Statement` 的执行正常完成时，`if-then` 语句正常完成。
- 如果值为 `false`，则不采取进一步操作，`if-then` 语句正常完成。

## 14.9.2 if-then-else 语句

`if-then-else` 语句通过首先求值 `Expression` 来执行。如果结果是 `Boolean` 类型，则要经过拆箱转换（§5.1.8）。

如果 `Expression` 的求值或后续的拆箱转换（如果有）由于某种原因异常完成，则 `if-then-else` 语句以相同的原因异常完成。

否则，根据结果的值继续执行：

- 如果值为 `true`，执行 `else` 关键字之前的第一个 `Statement`；当且仅当该语句执行正常完成时，`if-then-else` 语句正常完成。
- 如果值为 `false`，执行 `else` 关键字之后的第二个 `Statement`；当且仅当该语句执行正常完成时，`if-then-else` 语句正常完成。

## 14.10 assert 语句

断言是包含布尔表达式的 `assert` 语句。断言启用或禁用。如果执行断言，断言的执行会导致布尔表达式的求值，如果表达式结果为 `false`，则报告错误。如果断言被禁用，断言的执行没有任何影响。

```
AssertStatement:
    assert Expression ;
    assert Expression : Expression ;
```

为了方便演示，`assert` 语句两种形式中的第一个 `Expression` 称为 `Expression1`。在 `assert` 语句的第二形式中，第二个 `Expression` 称为 `Expression2`。

如果 `Expression1` 不具有 `boolean` 或 `Boolean` 类型，则发生编译错误。如果在 `assert` 语句的第二形式中 `Expression2` 为 `void`（§15.1），则发生编译错误。

在类或接口初始化后执行的断言语句，当且仅当宿主系统确定逻辑包含该断言语句的顶级类或接口启用断言时才启用。

顶级类或接口是否启用确定不晚于 (i) 顶级类或接口的初始化，以及 (ii) 嵌套在顶级类或接口中的任何类或接口的初始化。一旦确定了顶级类或接口是否启用，就不能再更改。

在类或接口初始化完成之前执行的断言语句是启用的。

这一规则的动力是为了一个需要特殊处理的情况。记住，类的断言状态是在不晚于其初始化时设置的。在初始化之前执行方法或构造函数是可能的但通常是不理想的。这发生在类在静态初始化中存在循环时，例如所示：

```
public class Foo {
    public static void main(String[] args) {
        Baz.testAsserts();
        // 将执行 Baz 已初始化。
    }
}

class Bar {
    static { Baz.testAsserts(); }
    // 该方法将在 Baz 初始化之前执行！
}

class Baz extends Bar {
    static void testAsserts() {
        boolean enabled = false;
        assert enabled = true;
        System.out.println("Asserts " + (enabled ? "enabled" : "disabled"));
    }
}
```

调用 `Baz.testAsserts()` 会导致 `Baz` 被初始化。在此发生之前，必须初始化 `Bar`。`Bar` 的静态初始化器调用了 `Baz.testAsserts()`。由于当前线程正在进行 `Baz` 的初始化，第二次调用会立即执行，尽管此时 `Baz` 尚未初始化（§12.4.2）。

由于上述规则，如果在未启用断言的情况下执行程序，它必须打印：

- Asserts enabled
- Asserts disabled

一个被禁用的语句什么都不做。特别是，`Expression1` 或 `Expression2`（如果存在）都不会被求值。被禁用语句的执行总是正常完成的。

启用的 `assert` 语句通过首先求值 `Expression1` 来执行。如果结果是 `Boolean` 类型，则将进行拆箱转换（§5.1.8）。

如果 `Expression1` 的求值或随后的拆箱转换（如果有）由于某些原因异常完成，则 `assert` 语句以相同原因异常完成。

否则，执行通过根据 `Expression1` 的值进行选择来继续：

- 如果值为 `true`，则不采取进一步操作，且 `assert` 语句正常完成。
- 如果值为 `false`，则执行行为取决于 `Expression2` 是否存在：
  - 如果 `Expression2` 存在，则对其进行求值。然后：
    - 如果求值由于某些原因异常完成，则 `assert` 语句以相同原因异常完成。
    - 如果求值正常完成，则创建一个 `AssertionError` 实例，其“详细消息”是 `Expression2` 的结果值。然后：
      - 如果实例创建由于某些原因异常完成，则 `assert` 语句以相同原因异常完成。
      - 如果实例创建正常完成，则通过抛出新创建的 `AssertionError` 对象使 `assert` 语句异常完成。
  - 如果 `Expression2` 不存在，则创建一个没有“详细消息”的 `AssertionError` 实例。然后：
    - 如果实例创建由于某些原因异常完成，则 `assert` 语句以相同原因异常完成。
    - 如果实例创建正常完成，则通过抛出新创建的 `AssertionError` 对象使 `assert` 语句异常完成。

通常，在程序开发和测试期间启用断言，并在部署时禁用以提高性能。

由于断言被禁用，程序不能假设断言中包含的表达式会被求值。对此类布尔表达式通常不应有副作用。求值布尔表达式不应影响求值后可见的任何状态。断言中包含的布尔表达式有副作用并不是非法的，但通常是不恰当的，因为它可能导致行为随断言的启用或禁用而变化。

鉴于此，不应在公共方法中使用断言进行参数检查。参数检查通常是方法合约的一部分，无论断言启用还是禁用，都必须维护这一合约。

使用断言进行参数检查的次要问题是，错误的参数应该导致适当的运行时异常（例如 `IllegalArgumentException`、`ArrayIndexOutOfBoundsException` 或 `NullPointerException`）。断言失败不会抛出适当的异常。再次，在公共方法上使用断言进行参数检查并不是非法的，但通常是不恰当的。设计意图是 `AssertionError` 永远不被捕获，但也可以这样做，`try` 语句的规则处理 `try` 块中出现的断言类似于目前对 `throw` 语句的处理。

## 14.11 switch 语句

`switch` 语句根据表达式的值将控制转移到多个语句之一。

```
SwitchStatement:
    switch ( Expression ) SwitchBlock

SwitchBlock:
    { SwitchBlockStatementGroup } {SwitchLabel}

SwitchBlockStatementGroup:
    SwitchLabels BlockStatements

SwitchLabels:
    SwitchLabel [SwitchLabel]

SwitchLabel:
    case ConstantExpression :
    case EnumConstantName :
    default:

EnumConstantName:
    Identifier
```

`Expression` 的类型必须是 `char`、`byte`、`short`、`int`、`Character`、`Byte`、`Short`、`Integer`、`String` 或枚举类型（§8.9），否则将发生编译时错误。

`switch` 语句的体被称为 switch 块。任何紧随 switch 块的语句都可以标记一个或多个 switch 标签，这些标签是 `case` 标签或 `default` 标签。每个 `case` 都有一个 `case` 常数，它是一个 `case` 表达式或枚举常量的名称。switch 标签及其 `case` 常数被认为与 switch 语句关联。

给定一个 `switch` 语句，所有条件都必须真，否则将发生编译时错误：

- 与 `switch` 语句关联的每个 `case` 常数必须与 `switch` 语句 `Expression` 的类型兼容（§5.2）。
- 如果 `switch` 语句 `Expression` 的类型是枚举类型，则与 `switch` 语句关联的每个 `case` 常数必须是该类型的枚举常量。
- 与 `switch` 语句关联的两个 `case` 常数没有相同的值。
- 与 `switch` 语句关联的任何 `case` 常数都不为 `null`。
- `switch` 语句最多关联一个 `default` 标签。

禁止将 `null` 作为 `case` 的规定防止了编写永远无法执行的代码。如果 `switch` 语句的 `Expression` 是引用类型，即 `String` 或包装类型或枚举类型，那么当 `Expression` 在运行时求值为 `null` 时，将抛出一个异常。在 Java 编程语言设计者看来，这比静默地跳过整个 `switch` 语句或选择执行 `default` 标签（如果有）之后的语句（`if`）结果更好。

鼓励（但不是强制）Java 编译器如果对枚举值的 `switch` 缺少 `default` 标签且缺少一个或多个常量的 `case` 标签，则提供警告。如果表达式求值为缺失的常量之一，此类 `switch` 将静默地什么都不做。

在 C 和 C++ 中，`switch` 语句的体可以是一个语句，带有 `case` 标签的语句不需要紧跟在该语句之后。考虑这个简单的循环：

```
for (i = 0; i < n; ++i) foo();
```

其中 `n` 已知为正数。在 C 或 C++ 中可以使用像 Duff's device 的技巧来展开循环，但这在 Java 编程语言中不是有效代码：

```
int q = (n + 7) / 8;
switch (n % 8) {
    case 0: do { foo();      // 棒的 C 技巧，Tom，
    case 7:     foo();      // 但这里不是有效的。
    case 6:     foo();
    case 5:     foo();
    case 4:     foo();
    case 3:     foo();
    case 2:     foo();
    case 1:     foo();
    } while (--q > 0);
}
```

幸运的是，这种技巧似乎并不为人知。此外，现在已不再需要；这种代码转换在现代编译器中良好支持。

`switch` 语句通过首先求值 `Expression` 执行。如果 `Expression` 求值为 `null`，则抛出 `NullPointerException` 且 `switch` 语句异常完成。否则，如果结果是 `Character`、`Byte`、`Short` 或 `Integer`，将进行拆箱转换（§5.1.8）。

如果 `Expression` 的求值或随后的拆箱转换（如果有）由于某些原因异常完成，则 `switch` 语句以相同原因异常完成。

否则，执行通过将 `Expression` 的值与每个 `case` 常数进行比较来继续，并存在选择：

- 如果其中一个 `case` 等于该值，则说该 `case` 匹配。相等性根据 `==` 运算符定义（§15.21），除非表达式是 `String`，则根据 `String` 类的 `equals` 方法定义。

匹配 `case` 标签之后的 switch 块中的所有语句（如果有）按顺序执行。

如果所有语句正常完成，或者匹配 `case` 标签之后没有语句，则整个 `switch` 语句正常完成。

- 如果没有 `case` 匹配但存在 `default` 标签，则 switch 块中 `default` 标签之后的所有语句（如果有）按顺序执行。

如果所有语句正常完成，或者 `default` 标签之后没有语句，则整个 `switch` 语句正常完成。

- 如果没有 `case` 匹配且没有 `default` 标签，则不采取进一步操作且 `switch` 语句正常完成。

如果 `switch` 语句体内部包含的任何语句异常完成，处理方式如下：

- 如果语句执行由于无标签 `break` 而异常完成，则不采取进一步操作，且 `switch` 语句正常完成。
- 如果语句执行由于其他原因异常完成，则 `switch` 语句以相同原因异常完成。

带有标签的 `break` 异常完成的情况由标记语句的通用规则处理（§14.7）。

### 示例 14.11-1. switch 语句中的穿透

与 C 和 C++ 中一样，switch 块中语句的执行会“穿透标签”。

例如，程序：

```
class TooMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.print("one ");
            case 2: System.out.print("too ");
            case 3: System.out.println("many");
        }
    }

    public static void main(String[] args) {
        howMany(3);
        howMany(2);
        howMany(1);
    }
}
```

包含一个 switch 块，其中每个 `case` 的代码会穿透到下一个 `case` 的代码。因此，程序打印出：

- many
- too many
- one too many

如果代码不以这种方式逐 `case` 穿透，则应该使用 `break` 语句，如例所示：

```
class TwoMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.println("one");
                break; // 退出 switch
            case 2: System.out.println("two");
                break; // 退出 switch
            case 3: System.out.println("many");
                break; // 不需要，但是良好的风格
        }
    }

    public static void main(String[] args) {
        howMany(1);
        howMany(2);
        howMany(3);
    }
}
```

该程序打印：

- one
- two
- many

## 14.12 while 语句

`while` 语句重复执行一个表达式（`Expression`）和一个语句（`Statement`），直到表达式的值为假。

```
WhileStatement:
    while ( Expression ) Statement

WhileStatementNoShortIf:
    while ( Expression ) StatementNoShortIf
```



该表达式必须是 `boolean` 或 `Boolean` 类型，否则会发生编译错误。

`while` 语句的执行首先求值表达式。如果结果是 `Boolean` 类型，则要进行拆箱转换 (§5.1.8)。

如果表达式的求值或随后的拆箱转换（如果有）由于某种原因异常完成，则 `while` 语句因相同原因异常完成。

否则，通过根据结果进行选择来继续执行：

- 如果值为 `true`，则执行语句。然后有一个选择：
  - 如果语句的执行正常完成，则整个 `while` 语句再次执行，从重新求值表达式开始。
  - 如果语句的执行异常完成，见 §14.12.1。
- 如果表达式的（可能拆箱后的）值为 `false`，则不采取进一步操作，`while` 语句正常完成。

如果表达式的（可能拆箱后的）值在第一次求值时为 `false`，则不执行语句。

### 14.12.1 while 语句的异常完成

包含的语句的异常完成按以下方式处理：

- 如果语句的执行由于无标签的 `break` 而异常完成，则不采取进一步操作，`while` 语句正常完成。
- 如果语句的执行由于无标签的 `continue` 而异常完成，则整个 `while` 语句再次执行。

如果语句的执行由于带标签 L 的 `continue` 而异常完成，则有一个选择：

- 如果语句带有标签 L，则整个 `while` 语句再次执行。
- 如果语句没有标签 L，则 `while` 语句因带标签 L 的 `continue` 而异常完成。
- 如果语句的执行由于任何其他原因异常完成，则 `while` 语句因相同原因异常完成。

由于带标签的 `break` 导致的异常完成情况由标签语句的通用规则（§14.7）处理。

## 14.13 do 语句

`do` 语句重复执行一个语句和一个表达式，直到表达式的值为假。

> DoStatement:
> `do while ( Expression ) ;`

该表达式必须是 `boolean` 或 `Boolean` 类型，否则会发生编译错误。

`do` 语句的执行首先执行语句。然后有一个选择：

- 如果语句的执行正常完成，则求值表达式。如果结果是 `Boolean` 类型，则要进行拆箱转换 (§5.1.8)。

如果表达式的求值或随后的拆箱转换（如果有）由于某种原因异常完成，则 `do` 语句因相同原因异常完成。

否则，根据结果进行选择：

- 如果值为 `true`，则执行整个 `do` 语句。
- 如果值为 `false`，则不采取进一步操作，`do` 语句正常完成。
- 如果语句的执行异常完成，见 §14.13.1。

执行 `do` 语句始终会至少执行一次包含的语句。

### 14.13.1 do 语句的异常完成

包含的语句的异常完成按以下方式处理：

- 如果语句的执行由于无标签的 `break` 而异常完成，则不采取进一步操作，`do` 语句正常完成。
- 如果语句的执行由于无标签的 `continue` 而异常完成，则求值表达式。根据结果有一个选择：
  - 如果值为 `true`，则再次执行整个 `do` 语句。
  - 如果值为 `false`，则不采取进一步操作，`do` 语句正常完成。
- 如果语句的执行由于带标签 L 的 `continue` 而异常完成，则有一个选择：
  - 如果语句带有标签 L，则求值表达式。这里有一个选择：
    - 如果表达式的值为 `true`，则再次执行整个 `do` 语句。
    - 如果表达式的值为 `false`，则不采取进一步操作，`do` 语句正常完成。
  - 如果语句没有标签 L，则 `do` 语句因带标签 L 的 `continue` 而异常完成。
- 如果语句的执行由于任何其他原因异常完成，则 `do` 语句因相同原因异常完成。

由于带标签的 `break` 导致的异常完成情况由标签语句的通用规则（§14.7）处理。

### 例 14.13-1. do 语句

```java
public static String toHexString(int i) {

    StringBuffer buf = new StringBuilder();

    do {

        buf.append(Character.forDigit(i & 0xF, 16));

        i >>>= 4;

    } while (i != 0);

    return buf.reverse().toString();

}
```

由于至少必须生成一个数字，因此 `do` 语句是一个合适的结构。

## 14.14 for 语句

`for` 语句有两种形式：

- 基础 `for` 语句
- 增强 `for` 语句

### 14.14.1 基础 for 语句

基础 `for` 语句执行某些初始化代码、一个语句以及某些更新代码，直到表达式的值为假。

```
BasicForStatement:
for ( [Init]; ; [Update] ) Statement
```

```
ForStatementNoIf:
for ( [Init]; ; [Update] ) StatementShortIf
```

```
ForInit:
StatementList
LocalVariableDeclaration
```

```
ForUpdate:
StatementList
```

```
StatementList:
StatementExpression ( , )
```

该表达式必须是 `boolean` 或 `Boolean` 类型，否则会发生编译错误。

基础 `for` 语句中 `ForInit` 部分声明的局部变量的作用和遮蔽见 §6.3 和 §6.4。

#### 14.14.1.1 语句的初始化

`for` 语句的执行首先执行 `ForInit` 代码：

- 如果 `ForInit` 代码是语句列表 (§14.8)，则从左到右顺序执行表达式；其值（如果有）被丢弃。

如果任何表达式的求值由于某种原因异常完成，`for` 语句因相同原因异常完成；异常表达式右侧 `ForInit` 语句不再求值。

- 如果 `ForInit` 代码是局部变量声明 (§14.4)，则像块中的变量声明语句一样执行。

如果局部变量声明的执行由于某种原因异常完成，`for` 语句因相同原因异常完成。

- 如果不存在 `ForInit` 部分，则不采取操作。

#### 14.14.1.2 for 语句的迭代

接下来执行 `for` 迭代步骤：

- 如果存在表达式，则对其求值。如果结果是 `Boolean` 类型，则要进行拆箱转换 (§5.1.8)。

如果表达式的求值或随后的拆箱转换（如果有）异常完成，`for` 语句因相同原因异常完成。

否则，根据表达式是否存在以及如果存在则结果值进行选择：

- 如果表达式不存在，或者表达式存在且其求值结果（包括任何可能的拆箱）为 `true`，则执行包含的语句。然后有一个选择：
  - 如果语句的执行正常完成，则按顺序执行两个步骤：
    1. 首先，如果存在 `ForUpdate` 部分，则从左到右顺序执行表达式；其值（如果有）被丢弃。如果任何表达式的求值由于某种原因异常完成，`for` 语句以相同的原因异常完成；异常完成的语句右侧任何 `ForUpdate` 语句表达式都不会被求值。
    2. 第二，执行另一个 `for` 迭代步骤。
  - 如果 `Statement` 的执行异常完成，请参阅 §14.14.1.3。

- 如果 `Expression` 存在且其求值结果（包括任何可能的拆箱）为 `false`，则不执行任何后续操作且 `for` 语句正常完成。

如果 `Expression` 的（可能拆箱的）值在第一次求值时为 `false`，则不执行 `Statement`。

如果 `Expression` 不存在，语句正常完成的唯一方法是使用 `break` 语句。

#### 14.14.1.3 for 语句的异常完成

所包含的 `Statement` 的异常完成按如下方式处理：

- 如果 `Statement` 的执行因为无标签的 `break` 而异常完成，则不执行任何后续操作且 `for` 语句正常完成。
- 如果 `Statement` 的执行因为无标签的 `continue` 而异常完成，则按顺序执行以下两个步骤：
  1. 首先，如果存在 `ForUpdate` 部分，则按从左到右顺序求值表达式；它们值（如果有）将被丢弃。如果不存在 `ForUpdate` 部分，则不执行任何操作。
  2. 第二，执行另一个 `for` 迭代步骤。
- 如果 `Statement` 的执行因为带有标签 L 的 `continue` 而异常完成，则有一个选择：
  - 如果该 `for` 语句带有标签 L，则按顺序执行以下两个步骤：
    1. 首先，如果存在 `ForUpdate` 部分，则按从左到右顺序求值表达式；它们值（如果有）将被丢弃。如果不存在 `ForUpdate` 部分，则不执行任何操作。
    2. 第二，执行另一个 `for` 迭代步骤。
  - 如果 `for` 语句不带有标签 L，则 `for` 语句因为带有标签 L 的 `continue` 而异常完成。
- 如果 `Statement` 的执行因为任何其他原因异常完成，则 `for` 语句因为相同的原因而异常完成。

注意，由于带标签的 `break` 导致的异常完成情况由标签语句的通用规则 (§14.7) 处理。

### 14.14.2 增强型 for 语句

增强型 `for` 语句的形式为：

```
EnhancedForStatement:
for ({VariableModifier} LocalVariableType VariableDeclaratorId : Expression) Statement
```

```
EnhancedForStatementNoShortIf:
for ({VariableModifier} LocalVariableType VariableDeclaratorId : Expression) StatementNoShortIf
```

为了方便起见，这里展示了 §4.3、§8.3、§8.4.1 和 §14.4 中的产生式：

```
VariableModifier:
Annotation
final
```

```
LocalVariableType:
UnannType
var
```

```
VariableDeclaratorId:
Identifier [Dims]
```

```
Dims:
[Annotation] [] {[Annotation] []}
```

增强型 `for` 语句的头部声明了一个局部变量，其名称由 `VariableDeclaratorId` 标识。

如果关键字 `final` 出现在声明的开头，则被声明的变量是一个 `final` 变量 (§4.12.4)。

如果 `LocalVariableType` 为 `var` 且 `VariableDeclaratorId` 具有一个或多个括号，则会导致编译错误。

`Expression` 的类型必须是原始类型 `Iterable` 的子类型或数组类型 (§10.1)，否则将发生编译错误。

局部变量的类型确定为：

- 如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中没有出现括号，则 `UnannType` 表示局部变量的类型。
- 如果 `LocalVariableType` 是 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号，则局部变量的类型由 §10.2 规定。
- 如果 `LocalVariableType` 是 `var`，则 `t` 按照如下方式从 `Expression` 的类型导出：
  - 如果 `Expression` 是数组类型，则 `t` 是数组类型的组件类型。
  - 否则，如果 `Expression` 的类型是某个类型 `X` 的 `Iterable<X>` 的子类型，则 `t` 是 `X`。
  - 否则，`Expression` 的类型是原始类型 `Iterable` 的子类型，且 `t` 是 `Object`。

局部变量的类型相对于 `t` 所提到的所有合成类型变量的向上投影 (§§10.5)。

局部变量的作用域和屏蔽在 §6.3 和 §6.4 中规定。

当执行增强型 `for` 语句时，局部变量在循环的每次迭代中都被初始化为表达式产生的数组或 `Iterable` 的连续元素。增强型 `for` 语句的精确含义通过翻译为基础 `for` 语句给出，如下：

- 如果 `Expression` 的类型是 `Iterable` 的子类型，则翻译如下。

如果 `Expression` 的类型是某个类型参数 `X` 的 `Iterable<X>` 的子类型，令 `I` 为 `java.util.Iterator<X>`；否则，令 `I` 为原始类型 `java.util.Iterator`。

增强型 `for` 语句等于如下形式的基础 `for` 语句：

```java
for (I #i = Expression.iterator(); #i.hasNext(); ) {
    {VariableModifier} TargetType Identifier = (TargetType) #i.next();
}
```

`#i` 是一个自动生成的标识符，与在增强型 `for` 语句发生点作用域内 (§6.3) 的任何其他标识符（自动生成的或其他）都不同。

如果增强型 `for` 语句头部中局部变量的声明类型是引用类型，则 `TargetType` 是声明类型；否则，`TargetType` 是 `I` 的类型参数转换 (§5.1.10) 的上界，如果 `I` 是原始类型则为 `Object`。

例如，这段代码：

```java
List<? extends Integer> l = ...
for (float i : l) {
```

将被翻译为：

```java
for (Iterator<Integer> #i = l.iterator(); #i.hasNext(); ) {
    float #i0 = (Integer) #i.next();
}
```

- 否则，`Expression` 必然具有数组类型 `T[]`。

令 `L1 ... Ln` 为紧邻增强型 `for` 语句之前的标签（可能为空）序列。

增强型 `for` 语句等于如下形式的基础 `for` 语句：

```java
T[] #a = Expression;
L1: ... Ln:
for (int #i = 0; #i < #a.length; #i++) {
    {VariableModifier} TargetType Identifier = #a[#i];
}
```

`#a` 和 `#i` 是自动生成的标识符，与增强型 `for` 语句发生点作用域内的任何其他标识符（自动生成的或其他）不同。

`TargetType` 是增强型 `for` 语句头部局部变量的声明类型。

## 14.15 break 语句

被称为 `break` 目标，则立即正常完成。在这种情况下，`break` 目标不需要是 `switch`、`do` 或 `for` 语句。

`break` 语句必须引用其所在方法、构造函数或 lambda 体内的标签。不存在非局部跳转。如果其所在方法、构造函数或 lambda 体内的没有标签语句包含 `break` 语句，则发生编译错误。

可以看出，`break` 语句总是异常完成的。

前述描述使用“尝试转移控制”而非仅“转移控制”，是因为如果 `break` 目标内的任何 `try` 语句 (§14.20) 的 `try` 块包含了 `break` 语句，那么在转移到 `break` 目标之前，这些语句的 `finally` 子句按顺序执行。`finally` 子句的异常完成会破坏由 `break` 语句发起的控制。

### 示例 14.15-1. break 语句

在以下示例中，数学图由数组数组表示。图由节点和边组成；每条边都是从某个节点指向另一个节点的箭头，或者从节点指向自身。

节点由整数表示，对于每一个数组引用 `edges[i][j]` 不抛出 `ArrayException`，存在从节点 `i` 指向节点 `edges[i][j]` 的边。

方法 `loseEdges` 的任务是给定整数 `i` 和 `j`，通过复制给定图但省略从节点 `i` 指向节点 `j` 的边（如果有）以及从节点 `j` 指向节点 `i` 的边，如果：

```java
class Graph {
    int edges[][];

    public Graph(int[][] edges) { this.edges = edges; }

    public Graph loseEdges(int i, int j) {
        int n = edges.length;
        int[][] newEdges = new int[n][];

        for (int k = 0; k < n; k++) {
            edgelist:
            int z;
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

            // 没有边需要删除；共享此列表。
            newEdges[k] = edges[k];
            break edgelist;

            // 复制列表，跳过位置 z 的边。
        }
    }
}
```

## 14.16 continue 语句



## 代码示例

```java
int m = edges[k].length - 1;
int ne[] = new int[m];
System.arraycopy(edges[k], 0, ne, 0, z);
System.arraycopy(edges[k], z+1, ne, z, m-z);
wedged[k] = ne;
}
edgelist: {
    return new Graph(wedged);
}
```

这里使用了两个语句标签 `edgelist` 和 `search`，并使用了 `break` 语句。这使得复制列表（并跳过一条边）的代码可以在两个独立的测试之间共享：即从边节点 `i` 到节点 `j` 的边测试，以及从边 `j` 到节点 `i` 的边测试。

## 14.16 continue 语句

`continue` 语句只能出现在 `while`、`do` 或 `for` 语句中；这三类语句被称为迭代语句。控制传递到迭代语句的循环继续点。

```java
ContinueStatement:
continue [Identifier];
```

不带标签的 `continue` 语句尝试将控制转移到紧邻的方法、构造函数或初始化器内部最内嵌套的 `while`、`do` 或 `for` 语句；该语句（称为 continue 目标）则会立即结束当前迭代并开始新的迭代。

准确来说，`continue` 语句总是会异常地完成（completes abruptly），其原因是执行了不带标签的 `continue`。

如果紧邻的方法、构造函数或初始化器中没有 `while`、`do` 或 `for` 语句包含该 `continue` 语句，则会发生编译错误。

带有标签 `Identifier` 的 `continue` 语句尝试将控制转移到与其标签具有相同 `Identifier` 的外层标签语句（§14.7）；该语句（continue 目标）则会立即结束当前迭代并开始新的迭代。

准确来说，带有标签 `Identifier` 的 `continue` 语句总是会异常地完成，其原因是执行了带有标签 `Identifier` 的 `continue`。

`continue` 目标必须是一个 `while`、`do` 或 `for` 语句，否则会发生编译错误。

`continue` 语句必须引用紧邻的方法、构造函数、初始化器或 lambda 体内部的标签。不存在非局部跳转。如果紧邻的方法、构造函数、初始化器或 lambda 体中没有以 `Identifier` 为标签的语句包含该 `continue` 语句，则会发生编译错误。

可见，`continue` 语句总是会异常地完成。

请参阅 `while` 语句（§14.12）、`do` 语句（§14.13）和 `for` 语句（§14.14）的描述，以讨论对由于 `continue` 导致的异常终止的处理方法。

前述描述使用了“尝试转移控制”而非仅仅是“转移控制”，是因为如果 `continue` 目标内部存在任何 `try` 语句（§14.20），其代码块或 `catch` 子句包含了该 `continue` 语句，那么在控制转移到 `continue` 目标之前，这些 `try` 语句的任何 `finally` 子句都会从内层到外层顺序执行。`finally` 子句的异常完成可能会中断 `continue` 语句的控制转移。

## 示例 14-1-1. continue 语句

在 `Graph` 类 §14.15 中，`break` 语句之一是结束整个最外层 `for` 循环主体的执行。如果 `for` 循环本身标记了标签，则可以将此 `break` 替换为 `continue`：

```java
class Graph {
    int edges[][];

    public Graph(int[][] edges) { this.edges = edges; }

    public Graph loseEdges(int i, int j) {
        int n = edges.length;
        int[] newwedges = new int[n];

        nedgelists:
            for (int k = 0; k < n; ++k) {
                int z;

                search:
                    if (k == i) {
                        for (z = 0; z < edges[k].length; ++z) {
                            if (edges[k][z] == j) break;
                        }
                    } else if (k == j) {
                        for (z = 0; z < edges[k].length; ++z) {
                            if (edges[k][z] == i) break;
                        }
                    }

                    // 没有边删除；共享此列表。
                    newwedges[k] = edges[k];
                    continue nedgelists;
            }

            // 复制列表，跳过位置 z 的边。
            int m = edges[k].length;
            int ne[] = new int[m];
            System.arraycopy(edges[k], 0, ne, 0, z);
            System.arraycopy(edges[k], z+1, ne, z, m-z);
            newwedges[k] = ne;
        }

        return new Graph(newwedges);
    }
}
```

使用哪一种在很大程度上取决于编程风格。

## 14.17 return 语句

`return` 语句将控制返回给方法的调用者（§8.4）或构造函数（§8.8, 15.9）。

```java
ReturnStatement:
return [Expression];
```

`return` 语句包含在包裹该 `return` 语句的最内层构造函数、方法、初始化器或 lambda 表达式中。如果 `return` 语句包含在实例初始化器或静态初始化器中（§8.6, 8.7），会导致编译错误。

不带 `Expression` 的 `return` 语句必须包含以下内容之一，否则会发生编译错误：
- 使用 `void` 关键字声明的、不返回值的方法（§8.4）
- 构造函数（§8.8）
- lambda 表达式（§15.2）

不带 `Expression` 的 `return` 语句尝试将控制转移给包含它的方法、构造函数或 lambda 体的调用者。准确来说，不带 `Expression` 的 `return` 语句总是会异常地完成，返回的结果没有值。

带有 `Expression` 的 `return` 语句必须包含以下内容之一，否则会发生编译错误：
- 声明为返回类型的方法
- lambda 表达式

`Expression` 必须表示一个变量或值，否则会发生编译错误。

当带有 `Expression` 的 `return` 语句出现在方法声明中时，该 `Expression` 必须可以赋值（§5.2）给方法声明的返回类型，否则会发生编译错误。

带有 `Expression` 的 `return` 语句尝试将控制转移给包含它的方法或 lambda 体的调用者；`Expression` 的值变为方法的值。更准确地说，执行此类 `return` 语句首先求值 `Expression`。如果 `Expression` 的求值由于某种原因异常完成，则 `return` 语句也异常地完成。如果 `Expression` 的求值正常完成并产生值 `v`，则 `return` 语句异常地完成，返回值为 `v`。

如果表达式是 `float` 类型且不是 FP-strict（§15.4），则该值可能是 `float` 值集或 `float` 扩展值集中的元素（§4.2.3）。如果表达式是 `double` 类型且不是 FP-strict，则该值可能是 `double` 值集或 `double` 扩展值集中的元素。

由此可见，`return` 语句总是会异常地完成。

前述描述使用了“尝试转移控制”而非“转移控制”，是因为如果方法或构造函数内部存在任何 `try` 语句，其代码块或 `catch` 子句包含了 `return` 语句，那么在控制转移到方法或构造函数的调用者之前，这些 `try` 语句的 `finally` 子句将从内层到外层顺序执行。`finally` 子句的异常完成可能会中断由 `return` 语句发起的控制转移。

## 14.18 throw 语句

`throw` 语句会导致抛出一个异常（§11）。其结果是立即转移控制（§11.3），可能会跨越多个语句以及多个构造函数、实例初始化、静态初始化和方法调用，直到找到捕获抛出值的 `try` 语句（§14.20）。如果没有找到这样的 `throw` 语句，在调用该线程所属线程组的 `uncaughtException` 方法后，执行 `throw` 的线程（§17）终止。

```java
ThrowStatement:
throw Expression;
```

`throw` 语句中的 `Expression` 必须表示可以赋值给 `Throwable` 类型（§5.2）的引用类型的变量或值，或者表示空引用，否则会发生编译错误。

> `Expression` 的引用类型总是类类型（因为接口类型无法赋值给 `Throwable`），且不是参数化的（因为 `Throwable` 的子类不能是泛型的 §8.1.2）。

必须至少满足以下一个条件，否则会发生编译错误：
- `Expression` 的类型是非检查异常类（§11.1.1）或空类型（§4.1）。
- `throw` 语句包含在 `try` 语句的 `try` 块中，且该 `throw` 语句不会抛出与 `Expression` 类型相同的异常。（在这种情况下，我们说抛出值被 `throw` 语句捕获）。
- `throw` 语句包含在方法或构造函数声明中，且 `Expression` 的类型可以赋值（§5.2）给 `throws` 子句（§8.4.6, 8.8.5）中的至少一种类型。

`throw` 语句可以抛出的异常类型在 §11.2.2 中规定。

## throw 语句 14.18

- 如果表达式（`Expression`）的求值由于某种原因异常终止，则 `throw` 也因该原因异常终止。
- 如果表达式的求值正常结束并产生一个非空值 `V`，则 `throw` 语句异常终止，其原因是抛出了值为 `V` 的异常。
- 如果表达式的求值正常结束并产生一个 `null` 值，则会创建一个 `NullPointerException` 类的实例 `V'` 而不是 `null`。然后 `throw` 语句异常终止，其原因是抛出了值为 `V'` 的异常。

由此可见，`throw` 语句是异常终止的。

如果有任何外层的 `try` 语句（§14.20）的 `try` 块包含该 `throw` 语句，那么在控制向外传递时，这些 `try` 语句的任何 `finally` 子句都会被执行，直到 `throw` 完成。注意，`finally` 类的异常终止可能会中断由 `throw` 语句发起的控制传递。

如果 `throw` 语句被包含在方法声明或 lambda 表达式中，但其值没有被包含它的 `try` 语句捕获，则该方法的调用将因为 `throw` 而异常终止。

如果 `throw` 语句被包含在静态初始化器（§8.7）中，编译时检查（§11.2.3）确保其值始终是一个未检查异常，或者其值始终被包含它的 `try` 语句捕获。在运行时，尽管有此检查，如果该值没有被包含 `throw` 语句的 `try` 语句捕获，则如果它是 `Error` 类或其子类的实例，则会被重新抛出；否则，它会被封装在 `ExceptionInInitializerError` 对象中并抛出（§12.4.2）。

如果 `throw` 语句被包含在实例初始化器（§8.6）中，编译时检查（§11.2.3）确保其值始终是一个未检查异常，或者其值始终被包含它的 `try` 语句捕获，或者异常类型（或其任父类）出现在该类每个构造函数的 `throws` 子句中。

按照惯例，用户声明的可抛类型通常应该声明为 `Exception` 类的子类，而 `Exception` 是 `Throwable` 类的子类（§11.1.1）。

## 14.19 synchronized 语句

`synchronized` 语句代表执行线程获取一个互斥锁（§17.1），执行一个块，然后释放锁。在执行线程拥有该锁期间，其他线程不能获取该锁。

```java
SynchronizedStatement:
synchronized ( Expression ) Block
```

`Expression` 的类型必须是引用类型，否则将发生编译错误。

`synchronized` 语句的执行首先求值表达式。然后：
- 如果表达式的求值由于某种原因异常终止，则 `synchronized` 语句因相同原因异常终止。
- 否则，如果表达式的值为 `null`，则抛出一个 `NullPointerException`。
- 否则，令表达式的非空值为 `v`。执行线程锁定与 `v` 关联的监视器。然后执行 `Block`，并有两种选择：
  - 如果 `Block` 的执行正常结束，则解锁监视器且 `synchronized` 语句正常结束。
  - 如果 `Block` 的执行由于任何原因异常终止，则解锁监视器且 `synchronized` 语句因该原因异常终止。

`synchronized` 语句获取的锁与 `synchronized` 方法（§8.4.3.6）隐式获取的锁是相同的。单个线程可以多次获取同一个锁。

获取与对象关联的锁本身并防止其他线程访问该对象的字段或调用该对象上的非同步方法。其他线程也可以以常规方式使用 `synchronized` 方法或 `synchronized` 语句来实现互斥。

### 14.19-1. synchronized 语句

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

该程序产生输出：

```
made it!
```

注意，如果不允许单个线程多次锁定监视器，该程序将导致死锁。

## 14.20 try 语句

`try` 语句执行一个块。如果抛出一个值且 `try` 语句有一个或多个可以捕获它的 `catch` 子句，控制将传递到第一个此类 `catch` 子句。如果 `try` 语句有一个 `finally` 子句，则无论 `try` 块是正常结束还是异常终止，无论 `catch` 子句是否首先获得控制权，都会执行另一个代码块。

```java
TryStatement:
try Block Catches
try Block [Catches] Finally
TryWithResourcesStatement

Catches:
CatchClause {CatchClause}

CatchClause:
catch ( CatchFormalParameter ) Block

CatchFormalParameter:
{VariableModifier} CatchType VariableDeclaratorId

CatchType:
UnannClassType | ClassType

Finally:
finally Block
```

`UnannClassType` 参见 §8.3。为了方便起见，这里展示了 §4.3、§8.3 和 §8.4.1 中的以下产生式：

```java
VariableModifier:
Annotation
final

VariableDeclaratorId:
Identifier [Dims]

Dims:
[Annotation] { [Annotation] }
```

紧跟关键字 `try` 之后的 `Block`被称为 `try` 语句的 `try` 块。

紧跟关键字 `finally` 之后的 `Block`被称为 `try` 语句的 `finally` 块。

`try` 语句可以有 `catch` 子句，也称为异常处理器。

`catch` 子句精确声明一个参数，其称为异常参数。

如果 `final` 作为异常参数的修饰符出现多次，则为编译错误。

异常参数的作用域和隐藏在 §6.3 和 §6.4 中规定。

异常参数可以将其类型声明为单个类或两个多个类的联合（称为备选类型）。联合的备选类型用 `|` 分隔。

异常参数声明为单个类的 `catch` 子句称为单捕获子句。

异常参数声明为联合类型的 `catch` 子句称为多捕获子句。

在异常参数类型声明中使用的每个类型必须是 `Throwable` 类或其子类，否则将发生编译错误。

如果在异常参数类型声明中使用类型变量，则为编译错误。

如果联合包含两个备选类型 $D_i$ 和 $D_j$（$D_i \neq D_j$），则为编译错误。

异常参数声明为单个类的 `catch` 子句称为单捕获子句。

异常参数声明为联合类型的 `catch` 子句称为多捕获子句。

## try 语句示例

```java
try {
    ... throws ReflectiveOperationException ...
} catch (final ClassNotFoundException ex1) {
    final ReflectiveOperationException ex = ex1;
    ... body;
} catch (final IllegalAccessException ex2) {
    final ReflectiveOperationException ex = ex2;
    ... body;
}
```



其中，具有两个备选方案的多重 catch（`multi-catch`）句被翻译为两个单 catch（`uni-catch`）句。Java 编译器并不要求以这种复制代码的方式来编译多重 catch 句，可以在类文件中以不重复的方式表示多重 catch 句。

finally catch 句确保在执行完 try 块和任何可能执行的 catch 块之后执行 finally 块，无论控制流如何离开 try 块或 catch 块。finally 块的处理更为复杂，分别描述了带有 finally 块和不带 finally 块的 try 语句两种情况（§14.20.1, §14.20.2）。

try 语句允许省略 catch 句和 finally 句，如果它是 try 资源（`try-with-resources`）语句（§14.20.3）。

## 14.20.1 try-catch 的执行

不带 finally 块的 try 语句首先执行 try 块。然后有一个选择：

- 如果 try 块的执行正常完成，则不采取进一步操作，且 try 语句正常完成。
- 如果 try 块的执行由于抛出一个值 V 而异常终止，则有一个选择：
    - 如果 V 的运行时类型与（§5.2） try 语句中任何 catch 句的可捕获异常赋值兼容，则选择第一个（最左侧的）catch 句。将值 V 赋值给所选 catch 句的参数，并执行该 catch 句的块（`Block`），然后有一个选择：
        - 如果该块正常完成，则 try 语句正常完成。
        - 如果该块由于任何原因发生异常终止，则 try 语句由于相同原因异常终止。
    - 如果 V 的运行时类型与 try 语句中任何 catch 句的可捕获异常类不赋值兼容，则 try 语句由于抛出值 V 而异常终止。
    - 如果 try 块的执行由于任何其他原因发生异常终止，则 try 语句由于相同原因异常终止。

## 示例 14.20.1-1. 异常处理

```java
class BlewIt extends Exception {

    BlewIt() { }

    BlewIt(String s) { super(s); }

}

class Test {

    static void blowUp() throws BlewIt { throw new BlewIt(); }

    public static void main(String[] args) {

        try {

            blowUp();

        } catch (RuntimeException r) {

            System.out.println("Caught RuntimeException");

        } catch (BlewIt b) {

            System.out.println("Caught BlewIt");

        }

    }

}
```

异常 `BlewIt` 由方法 `blowUp` 抛出。main 主体中的 try-catch 语句有两个 catch 句。异常的运行时类型是 `BlewIt`，它不能赋值给 `RuntimeException` 类型，但可以赋值给 `BlewIt` 类型的变量，因此示例的输出为：

```
Caught BlewIt
```

## 14.20.2 try-finally 和 try-catch-finally 的执行

带有 finally 块的 try 语句首先执行 try 块。然后有一个选择：

- 如果 try 块的执行正常完成，则执行 finally 块，然后有一个选择：
    - 如果 finally 块正常完成，则 try 语句正常完成。
    - 如果 finally 块由于原因 S 发生异常终止，则 try 语句由于原因 S 异常终止。
- 如果 try 块的执行由于抛出一个值 V 而异常终止，则有一个选择：
    - 如果 V 的运行时类型与 try 语句中任何 catch 句的可捕获异常类赋值兼容，则选择第一个（最左侧的）此类 catch 句。将值 V 赋值给所选 catch 句的参数，并执行该 catch 句的块。然后有一个选择：
        - 如果 catch 块正常完成，则执行 finally 块。然后有一个选择：
            - 如果 finally 块正常完成，则 try 语句正常完成。
            - 如果 finally 块由于任何原因发生异常终止，则 try 语句由于相同原因异常终止。
        - 如果 catch 块由于原因 R 发生异常终止，则执行 finally 块。然后有一个选择：
            - 如果 finally 块正常完成，则 try 语句由于原因 R 异常终止。
            - 如果 finally 块由于原因 S 发生异常终止，则 try 语句由于原因 S 异常终止（原因 R 被丢弃）。
    - 如果 V 的运行时类型与 try 语句中任何 catch 句的可捕获异常类不赋值兼容，则执行 finally 块。然后有一个选择：
        - 如果 finally 块正常完成，则 try 语句由于抛出值 V 而异常终止。
        - 如果 finally 块由于原因 S 发生异常终止，则 try 语句由于原因 S 异常终止（值 V 的抛出被丢弃并忽略）。
- 如果 try 块的执行由于任何其他原因 R 发生异常终止，则执行 finally 块，然后有一个选择：
    - 如果 finally 块正常完成，则 try 语句由于原因 R 异常终止。
    - 如果 finally 块由于原因 S 发生异常终止，则 try 语句由于原因 S 异常终止（原因 R 被丢弃）。

## 示例 14.20.2-1. 使用 finally 处理未捕获异常

```java
class BleWit extends Exception {

    BleWit() { }

    BleWit(String s) { super(s); }

}

class Test {

    static void blowUp() throws BleWit {

        throw new NullPointerException();

    }

    public static void main(String[] args) {

        try {

        } catch (BleWit b) {

            System.out.println("Caught BleWit");

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

方法 `blowUp` 抛出的 `NullPointerException`（它是 `RuntimeException` 的一种）没有被 try 语句捕获，因为 `NullPointerException` 无法赋值给 `BleWit` 类型的变量。这导致 finally 句执行，之后执行 main 的唯一线程由于未捕获的异常而终止，通常会导致打印异常名称和简单的堆栈追踪。然而，本规范并不要求堆栈追踪。

强制要求堆栈追踪的问题在于，异常可以在程序的一点创建，在另一点抛出。除非异常被实际抛出（此时在回溯栈时生成），否则存储栈追踪是非常昂贵的。因此我们不强制每个异常都有栈追踪。

## 14.20.3 try 资源

try 语句使用局部变量（称为资源）进行参数化，这些变量在 try 块执行之前初始化，并在 try 块执行后按照初始化的反序自动关闭。当资源自动关闭时，catch 句和 finally 句通常是不必要的。

```
TryWithResourcesStatement:
  TryResourceSpecification Block [Catches] [Finally]
```

```
ResourceSpecification:
  ( ResourceList [; )
```

```
ResourceList:
  Resource {; Resource }
```

```
Resource:
  {VariableModifier} LocalVariableType Identifier = Expression
  VariableAccess
```

```
VariableAccess:
  ExpressionName
  FieldAccess
```

为了方便起见，这里显示了来自 §8.4.1 和 §14.4 的产生式：

```
VariableModifier:
  Annotation
  final

LocalVariableType:
  UnannType
  var
```

资源规范使用变量来表示 try 语句的资源，通过初始化表达式声明局部变量或引用合适的示例来实现。现有变量通过表达式名（§6.5.6）或字段访问表达式（§15.11）进行引用。

资源规范声明两个同名的变量是编译错误。

如果 `final` 在资源规范中每个声明变量的修饰符中出现多次，则是编译错误。

资源规范中声明的变量如果没有显式声明为 `final`，则隐式声明为 `final`（§4.12.4）。

由表达式名或字段访问表达式表示的资源必须是 `final` 或有效 final（`effectively final`）的变量，并且在执行 `try-with-resources` 语句之前已确定赋值（§16 (Definite Assignment)），否则将发生编译错误。

如果在资源规范中声明的变量的 `LocalVariableType` 为 `var`，且初始化表达式包含对该变量的引用，则发生编译错误。

在资源规范中声明的变量的类型确定如下：

- 如果 `LocalVariableType` 是一个 `UnannType`，则 `UnannType` 表示局部变量的类型。
- 如果 `LocalVariableType` 是 `var`，则令 τ 为初始化表达式在被处理为未出现在赋值上下文中时（即作为一个独立表达式，§15.2）的类型。局部变量的类型是 τ 相对于 τ 所提到的所有合成类型变量的向上投影（`upward projection`）（§14.10）。

如果 τ 是空类型（`null type`），则发生编译错误。

在资源规范中声明或引用为资源的变量，其类型必须是 `AutoCloseable` 的子类型，否则将发生编译错误。

在资源规范中声明的变量的作用范围和屏蔽（`shadowing`）在 §6.3 和 §6.4 中规定。

资源按照从左到右的顺序初始化。如果资源初始化失败（即其初始化表达式抛出异常），则 `try-with-resources` 语句已初始化的所有资源都将被关闭。如果所有资源都成功初始化，则按正常执行 `try` 块，然后关闭 `try-with-resources` 语句的非空资源。

资源按照初始化顺序的相反顺序关闭。只有当资源初始化为非空值时，才会被关闭。关闭某个资源时抛出的异常不会阻止其他资源的关闭。如果之前已由初始化器、`try` 块或某个资源的关闭抛出了异常，则该异常会被抑制（`suppressed`）。

资源规范指示多个资源的 `try-with-resources` 语句被处理为多个 `try-with-resources` 语句，其中每个语句都包含一个指示单个资源的资源规范。当一个具有 n 个资源（n > 1）的 `try-with-resources` 语句被翻译时，结果是一个具有 n-1 个资源的 `try-with-resources` 语句。经过 n 次翻译后，将产生嵌套的 `try-catch-finally` 语句，整体翻译完成。

## 14.20.3.1 基础 try-with-resources

没有 `catch` 子句或 `finally` 子句的 `try-with-resources` 语句被称为基础 try-with-resources 语句。

如果基础 `try-with-resources` 语句的格式为：

```
try (VariableAccess ...)
    Block
```

则通过以下翻译将资源首先转换为局部变量声明：

```
try (T #r = VariableAccess ...) {
    Block
```

`T` 是由 `VariableAccess` 表示的变量的类型，`#r` 是自动生成的标识符，它与根据本节其余部分翻译 `try-with-resources` 语句时在该作用范围内的任何其他标识符（自动生成的或其他的）都是不相同的。

基础 `try-with-resources` 语句的含义格式如下：

```
try ({VariableModifier} R Identifier = Expression ...)
    Block
```

通过翻译为局部变量声明和 `try-catch-finally` 语句给出：

```
{
  final {VariableModifierNoFinal} R Identifier = Expression;
  Throwable #primaryExc = null;
  try ResourceSpecification_tail
    Block
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



# 变量修饰符

`[VariableModifierNoFinal]` 定义为不带 `final` 的 `[VariableModifier]`。

`#t`、`#primaryExc` 和 `#suppressedExc` 是自动生成的标识符，它们与 `try-with-resources` 语句发生时在该范围内的任何其他标识符（自动生成的或其他的）都是不相同的。

如果资源规范指示一个资源，则 `ResourceSpecification_tail` 为空（且 `try-catch-finally` 语句本身不是 `try-with-resources` 语句）。

如果资源规范指示 n > 1 个资源，则 `ResourceSpecification_tail` 由资源规范中指示的第 2、3、... n 个资源组成，顺序相同（且 `try-catch-finally` 语句本身是一个 `try-with-resources` 语句）。

基础 `try-with-resources` 语句的可达性和确定赋值规则由上述翻译隐式规定。

## 单资源 try-with-resources 语句

在管理单个资源的基础 `try-with-resources` 语句中：

- 如果资源的初始化因为抛出值 `v` 而异常终止，则 `try-with-resources` 语句因为抛出值 `v` 而异常终止。
- 如果资源的初始化正常完成，并且 `try` 块因为抛出值 `V*` 而异常终止，那么：
  - 如果资源的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 `V*` 而异常终止。
  - 如果资源的自动关闭因为抛出值 `V2` 而异常终止，则 `try-with-resources` 语句因为抛出值 `V*` 而异常终止，并将 `V2` 添加到 `V*` 的抑制异常列表中。
- 如果资源的初始化正常完成，且 `try` 块正常完成，而资源的自动关闭因为抛出值 `V` 而异常终止，则 `try-with-resources` 语句因为抛出值 `V` 而异常终止。

## 多资源 try-with-resources 语句

在管理多个资源的基础 `try-with-resources` 语句中：

- 如果初始化因为抛出值 `V` 而异常终止，那么：
  - 如果所有已初始化的资源（可能为空）的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 `V` 而异常终止。
  - 如果所有已初始化的资源（可能为空）的自动关闭因为抛出异常 `V1...Vn` 而异常终止，则 `try-with-resources` 语句因为抛出值 `V` 而异常终止，并将剩余的 `V1...Vn` 添加到 `V*` 的抑制异常列表中。
- 如果初始化正常完成，且 `try` 块因为抛出值 `V` 而异常终止，那么：
  - 如果所有自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 `V` 而异常终止。
  - 如果所有自动关闭因为抛出异常 `V1...Vn` 而异常终止，则 `try-with-resources` 语句因为抛出值 `V` 而异常终止，并将剩余的 `V1...Vn` 添加到 `V*` 的抑制异常列表中。
- 如果初始化正常完成，且 `try` 块正常完成，那么：
  - 如果一个资源的自动关闭因为抛出值 `V` 而异常终止，而其他已初始化资源的自动关闭正常完成，则 `try-with-resources` 语句因为抛出值 `V` 而异常终止。
  - 如果多个已初始化资源的自动关闭因为抛出异常 `V1...Vn` 而异常终止，则 `try-with-resources` 语句因为抛出 `VI` 而异常终止，并将剩余的 `V2...Vn` 添加到 `VI` 的抑制异常列表中（其中 `VI` 是最右侧异常，`Vn` 是最左侧异常）。

# 14.21 不可达语句

如果语句因为不可触达而无法执行，则发生编译错误。

本节旨在对“可达”（reachable）一词进行精确解释。其思想是：从构造函数、方法、实例初始化器或静态初始化器的开始，必须存在某条执行路径包含该语句本身。该分析考虑了语句的结构。除了对条件表达式为常量值 `true` 的 `while`、`do` 和 `for` 语句进行特殊处理外，流分析中不考虑表达式的值。

例如，Java 编译器接受以下代码：

```
{
  int n = 5;
  while (n > 7) k = 2;
}
```

尽管 `n` 的值在编译时已知，且原则上可以在编译时确定，但对 `k` 的赋值永远无法执行。

本节的规则定义了两个技术术语：

- 语句是否可达
- 语句是否能正常完成

定义规定，只有当语句是可达时，它才能正常完成。

为了简化规则描述，使用了惯用的缩写“iff”，表示“当且仅当”（if and only if）。

如果在一个 `break` 目标内，不存在没有 `try` 块包含 `break` 语句的 `try` 语句，或者存在 `try` 块包含 `break` 语句的 `try` 语句且这些语句的所有 `finally` 子句都能正常完成，则一个可达的 `break` 会退出该语句。

此定义基于 §14.5 中“尝试转移控制”的逻辑。

如果在 `do` 语句内，不存在没有 `try` 块包含 `continue` 语句的 `try` 语句，或者存在 `try` 块包含 `continue` 语句的 `try` 语句且这些语句的所有 `finally` 子句都能正常完成，则 `continue` 会继续该 `do` 语句。

规则如下：

- 作为构造函数、方法、实例初始化器或静态初始化器主体的块是可达的。
- 非 `switch` 块的空块当且仅当它是可达的，即可正常完成。

## 块与语句

### 不可达语句

非 `switch` 块的非空块当且仅当其最后一个语句能正常完成时，才能正常完成。

非 `switch` 块的非空块中的第一个语句当且仅当该块是可达的，即是可达的。

非 `switch` 块的非空块中的每个语句 `s` 当且仅当 `s` 之前的语句能正常完成时，即是可达的。

- 类声明语句当且仅当它是可达的，即可正常完成。
- 局部变量声明语句当且仅当它是可达的，即可正常完成。
- 空语句当且仅当它是可达的，即可正常完成。
- 标记语句在满足以下至少一个条件为真时可以正常完成：
  - 包含的语句能正常完成。
  - 存在一个可达的 `break` 语句退出该标记语句。

包含的语句当且仅当标记语句是可达的，即是可达的。

- 表达式语句当且仅当它是可达的，即可正常完成。
- `if-then` 语句当且仅当它是可达的，即可正常完成。

该 `if-then` 语句当且仅当该 `if-then` 语句是可达的，即是可达的。

`if-then-else` 语句当且仅当 `then` 语句能正常完成或 `else` 语句能正常完成，即可正常完成。

`then` 语句当且仅当 `if-then-else` 语句是可达的，即是可达的。

`else` 语句当且仅当 `if-then-else` 语句是可达的，即是可达的。

> 对语句的这种处理（无论其是否有 `else` 部分）是非常不寻常的。理由在本节末尾给出。

- `assert` 语句当且仅当它是可达的，即可正常完成。
- `switch` 语句当且仅当满足以下至少一个条件为真时可以正常完成：
  - `switch` 块为空或仅包含标签。
  - `switch` 块中的最后一个语句能正常完成。
  - 在最后一个 `switch` 语句组之后至少有一个 `switch` 标签。
  - `switch` 块不包含 `default` 标签。
  - 存在一个可达的 `break` 语句退出该 `switch` 语句。

- `switch` 块当且仅当其 `switch` 语句是可达的，即是可达的。

- `switch` 块中的语句当且仅当其 `switch` 语句是可达的且满足以下至少一个条件为真时，即是可达的：
  - 它带有 `case` 或 `default` 标签。
  - `switch` 块中在其之前有一个语句且该之前的语句能正常完成。

- `while` 语句当且仅当满足以下至少一个条件为真时可以正常完成：
  - `while` 语句是可达的且条件表达式不是值为 `true` 的常量表达式（§15.28）。
  - 存在一个 `break` 语句退出该 `while` 语句。

包含的语句当且仅当 `while` 语句是可达且条件表达式不是值为 `false` 的常量表达式，即是可达的。

- `do` 语句当且仅当满足以下至少一个条件为真时可以正常完成：
  - 包含的语句能正常完成且条件表达式不是值为 `true` 的常量表达式（§15.28）。
  - `do` 语句包含一个可达的无标签 `continue` 语句，且 `do` 语句是包含该 `continue` 语句的最内层 `while`、`do` 或 `for` 语句，该 `continue` 语句继续该 `do` 语句，且条件表达式不是值为 `true` 的常量表达式。
  - `do` 语句包含一个带有标签 `L` 的可达 `continue` 语句，且 `do` 语句带有标签 `L`，该 `continue` 语句继续该 `do` 语句，且条件表达式不是值为 `true` 的常量表达式。
  - 存在一个 `break` 语句退出该 `do` 语句。

包含的语句当且仅当 `do` 语句是可达的，即是可达的。

- `for` 语句当且仅当满足以下至少一个条件为真时可以正常完成：
  - `for` 语句是可达的、存在条件表达式且条件表达式不是值为 `true` 的常量表达式（§15.28）。
  - 存在一个 `break` 语句退出该 `for` 语句。

包含的语句当且仅当 `for` 语句是可达且条件表达式不是值为 `false` 的常量表达式，即是可达的。

- 增强型 `for` 语句当且仅当它是可达的，即可正常完成。
- `break`、`continue`、`return` 或 `throw` 语句不能正常完成。
- `synchronized` 语句当且仅当包含的语句能正常完成，即可正常完成。

包含的语句当且仅当 `synchronized` 语句是可达的，即是可达的。

- `try` 语句当且仅当以下两个条件均为真时可以正常完成：
  - `try` 块能正常完成或任何 `catch` 块能正常完成。
  - 如果 `try` 语句有 `finally` 块，则该 `finally` 块能正常完成。

`try` 块当且仅当 `try` 语句是可达的，即是可达的。

- `catch` 块 `c` 当且仅当以下两个条件均为真时，即是可达的：
  - `c` 参数的类型是未检查异常类型、`Exception` 或 `Exception` 的父类，或者 `try` 块中的某些表达式或 `throw` 语句是可达的且能抛出一个类型可赋值给 `c` 参数类型的已检查异常。（表达式的可达取决于且仅取决于包含它的最内层语句的可达性。）

  表达式的正常完成和异常完成请见 §15.6。
  - `try` 语句中不存在更早的 `catch` 块 `A`，使得 `c` 参数的类型与 `A` 参数的类型相同或为该类型的子类。

`catch` 块的块当且仅当 `catch` 块是可达的，即是可达的。

- 如果存在 `finally` 块，它当且仅当 `try` 语句是可达的，即是可达的。

人们可能预期如下方式处理语句：

- `if-then` 语句当且仅当满足以下至少一个条件为真时可以正常完成：
  - `if-then` 语句是可达的且条件表达式不是值为 `true` 的常量表达式。
  - `then` 语句能正常完成。

`then` 语句当且仅当 `if-then` 语句是可达的且条件表达式不是值为 `false` 的常量表达式，即是可达的。

- `if-then-else` 语句当且仅当 `then` 语句能正常完成或 `else` 语句能正常完成时，即可正常完成。

`then` 语句是可达的，且仅当 `if-then-else` 语句是可达的且条件表达式不是值为 `false` 的常量表达式。

`else` 语句是可达的，且仅当 `if-then-else` 语句是可达的且条件表达式不是值为 `true` 的常量表达式。

这种方法将与其他控制结构的处理方式保持一致。然而，为了让 `if` 语句能够方便地用于“条件编译”目的，实际规则则有所不同。

例如，以下语句会导致编译错误：

```
while (false) { x=3; }
```

因为语句 `x=3;` 是不可达的；但从上看起来相似的情形：

```
if (false) { x=3; }
```

并不会导致编译错误。优化编译器可能会意识到语句 `x=3;` 永远不会被执行，并可能选择在生成的类文件中省略该代码，但在此处指定的技术意义上，语句 `x=3;` 不被视为“不可达的”。

这种差异处理的理由是允许程序员定义“标记”变量，例如：

```
static final boolean DEBUG = false;
```

然后编写如下代码：

```
if (DEBUG) { x=3; }
```

其想法是，应当能够将 `DEBUG` 的值从 `false` 改为 `true` 或从 `true` 改为 `false`，然后在不对程序文本进行任何其他更改的情况下正确编译代码。

条件编译带有一个警告：如果使用“标记”变量（更准确地说，是任何静态常量变量 §4.12.4）的类集合被编译且条件代码被省略，那么分发一个包含标记定义的类或接口的新版本是不够的。使用该标记的类看不到它的新值，因此行为可能会产生意料。从本质上，标记值的更改与现有的二进制文件是二进制兼容的（不会发生 `LinkageError`），但在行为上是不兼容的。

“内联”静态常量变量值的另一个原因是 `switch` 语句。它们是唯一依赖表达式的语句，即 `switch` 语句的每个 `case` 标签必须是一个常量表达式，其值必须与所有其他 `case` 标签不同。`case` 标签是静态常量变量的引用，因此可能无法立即看出所有标签具有不同的值。如果在编译时证明没有重复的标签，那么将值内联到类文件中可以确保运行时没有重复的标签——这是一个非常理想的属性。

## 示例 14.21-1. 条件编译

如果示例：

```
class Flags { static final boolean DEBUG = true; }

class Test {

    public static void main(String[] args) {

        if (Flags.DEBUG)
            System.out.println("DEBUG is true");

    }

}
```

被编译并执行，它将输出：

```
DEBUG is true
```

假设产生了类 `Flags` 的新版本：

```
class Flags { static final boolean DEBUG = false; }
```

如果重新编译了 `Flags` 但没有重新编译 `Test`，使用现有的二进制文件 `Test` 运行新的二进制文件将输出：

```
DEBUG is true
```

因为 `DEBUG` 是静态常量变量，所以它的值在编译 `Test` 时可能已经使用，无需引用类 `Flags`。

如果 `Flags` 是一个接口也会发生这种情况，如修改后的示例：

```
interface Flags { boolean DEBUG = true; }

class Test {

    public static void main(String[] args) {

        if (Flags.DEBUG)
            System.out.println("DEBUG is true");

    }

}
```

事实上，接口的字段始终是静态且最终的，我们建议只将常量表达式赋值给接口字段。我们注意但并不建议，如果接口的原始类型字段可能会更改，其值可以以惯用方式表示，如：

```
interface Flags {

    boolean debug = Boolean.valueOf(true).booleanValue();

}
```



# 第 15 章 表达式

程序中的大部分工作通过求值表达式完成，要么是为了它们的副作用（例如赋值变量），要么是为了它们的值（这些值可以作为更大表达式中的参数或操作数，或者影响语句的执行顺序，或两者兼有）。

本章规定了表达式的含义以及它们的求值规则。

## 15.1 求值、表示和结果

当程序中的表达式被求值（执行）时，结果表示以下三者之一：

- 一个变量（§4.12）（在 C 中，这被称为 l-value）
- 一个值（§4.2, §4.3）
- 无（该表达式被称为 void）

如果表达式表示一个变量，且后续评估需要一个值，则使用该值。

## 15.4 FP-strict 表达式

如果表达式的类型为 `float` 或 `double`，那么表达式的值取自于哪个值集（§4.2.3）存在疑问。这受值集转换规则（§5.1.13）的限制；这些规则反过来取决于该表达式是否为 FP-strict。

每个常量表达式（§15.28）都是 FP-strict 的。

如果一个表达式不是常量表达式，则考虑包含该表达式的所有类声明、接口声明和方法声明。如果任何此类声明带有 `strictfp` 修饰符（§8.1.1.3, §8.4.1.3），则该表达式是 FP-strict 的。

如果一个类、接口或方法 `x` 被声明为 `strictfp`，则 `x` 内部的任何类、接口、方法、构造函数、实例初始化器或变量初始化器都被说是 FP-strict 的。

注意，注解的元素（§9.7）始终是 FP-strict 的，因为它始终是一个常量表达式。

因此，一个表达式不是 FP-strict 的，当且仅当它既不是常量表达式，也没有出现在任何带有 `strictfp` 修饰符的声明中。

在 FP-strict 表达式内部，所有中间值必须是 `float` 值集或 `double` 值集的元素，这意味着所有 FP-strict 表达式的结果必须通过对单精度和双精度格式的操作使用 IEEE 754 算术进行预测。

在非 FP-strict 表达式内部，允许实现使用扩展范围来表示中间结果；粗略来说，其效果是，在仅使用 `float` 值集或 `double` 值集可能导致溢出或欠流的情况下，计算可能会产生“正确答案”。

## 15.5 表达式与运行时检查

如果表达式的类型是基本类型，则表达式的值是该基本类型的值。

如果表达式的类型是引用类型，则被引用对象的类、甚至该值是引用还是 `null`，在编译时并不一定已知。在 Java 语言中，有少数地方的被引用对象的实际类会影响程序的执行，而这种影响无法通过表达式的类型推断出来。它们如下：

- 方法调用（§15.12）。用于调用 `o.m(...)` 的特定方法是基于 `o` 所属类或接口中的方法选择的。在实例方法中，值 `o` 所引用的对象的类参与其中，因为子类可能会重写已经在父类中声明的方法（重写的方法可能不会选择调用原始方法）。
- `instanceof` 运算符（§15.20）。类型为引用类型的表达式可以使用 `instanceof` 测试，以确定运行时值引用的对象的类是否可以转换为其他引用类型。
- 类型转换（§15.16）。表达式运行时值引用的对象的类可能与类型转换符不兼容。对于引用类型，这可能需要运行时检查，如果在运行时确定的引用对象类无法转换为目标类型，则抛出异常。
- 对引用类型数组组件的赋值（§10.5, §15.13, §15.26.1）。类型检查规则允许当 `s` 是 `T` 的子类型时，将数组类型 `s[]` 视为 `T` 的子类型，但这对数组组件的赋值需要运行时检查，类似于为类型转换执行的检查。
- 异常处理（§14.20）。只有当抛出的异常对象的类是 `catch` 语句形式参数的类型时，异常才会被 `catch` 语句捕获。

对象的类不是静态已知的情况会导致运行时错误。此外，还存在静态已知类型在运行时可能不准确的情况。此类情况出现在程序中，会导致编译时的未检查警告。此类警告是针对无法在静态上保证安全的操作给出的，并且它们无法立即进行动态检查，因为它们涉及非可重构类型（§4.7）。因此，在程序执行过程后期的动态检查可能会检测到不一致性并导致运行时类型错误。

运行时类型错误仅在以下情况下发生：

- 在类型转换中，操作数表达式值引用的对象的实际类与类型转换符指定的类型类型不兼容（§15.5, §15.16）；在这种情况下，会抛出 `ClassCastException`。
- 在确保对非可重构类型操作的有效性而生成的分析类型转换中（§4.7）。
- 在对引用类型数组组件的赋值中，待赋值值引用的实际类与数组的实际运行时组件不兼容（§10.5, §15.13, §15.26.1）；在这种情况下，会抛出 `ArrayStoreException`。
- 当异常没有被 `try` 语句的任何 `catch` 语句捕获时（§14.20）；在这种情况下，遇到异常的控制线程尝试调用未捕获的异常处理器（§11.3）然后终止。

## 15.6 求值的正常完成与异常终止

每个表达式都有一个正常评估模式，在其中执行某些计算步骤。以下章节描述了每种表达式的正常评估模式。

如果所有步骤在没有抛出异常的情况下完成，则该表达式认为正常完成。

然而，如果表达式的评估抛出了异常，则该表达式被认为异常终止。异常终止总有一个相关的原因，该原因始终带有给定值的抛出操作。

预定义运算符抛出运行时异常如下：

- 类实例创建表达式（§15.9.4）、数组创建表达式（§15.10.2）、方法引用表达式（§15.13.3）、数组初始化表达式（§10.6）、字符串拼接运算符表达式（§15.18.1）或 lambda 表达式（§15.27.4）在可用内存不足时会抛出 `OutOfMemoryError`。
- 数组创建表达式（§15.10.2）如果任何维度表达式的值小于零，会抛出 `NegativeArraySizeException`。
- 数组访问表达式（§15.10.4）如果数组引用表达式的值为 `null`，会抛出 `NullPointerException`。
- 数组访问表达式（§15.10.4）如果索引值为负或大于等于数组长度，会抛出 `ArrayIndexOutOfBoundsException`。
- 字段访问表达式（§15.11）如果对象引用表达式的值为 `null`，会抛出 `NullPointerException`。
- 方法调用表达式（§15.12）如果目标引用为 `null`，则调用实例方法或抛出 `NullPointerException`。
- 类型转换表达式（§15.16）如果在运行时发现类型转换是不允许的，则抛出 `ClassCastException`。
- 整数除法（§15.17.2）或整数取模（§15.17.3）运算符如果右操作数表达式的值为零，会抛出 `ArithmeticException`。
- 对引用类型数组组件的赋值（§15.26.1）、方法调用表达式（§15.12）或前缀或后缀递增（§15.14.2）或递减运算符（§15.15.2）由于装箱转换（§5.1.7）可能会抛出 `OutOfMemoryError`。
- 对引用类型数组组件的赋值（§15.26.1）当待赋值值与数组的组件类型不兼容时，抛出 `ArrayStoreException`。

## 15.7 求值顺序

如果表达式的求值需要对子表达式进行求值，那么表达式本身的异常完成总是会导致以相同原因发生的异常完成，并且求值正常模式下的所有后续步骤都不会执行。

“正常完成（complete normally）”和“异常完成（complete abruptly）”术语也适用于语句的执行（§14.1）。语句可能由于各种原因导致异常完成，而不仅仅是因为抛出了异常。

Java 编程语言保证操作符的操作数似乎是按照特定的求值顺序求值的，即从左到右。

> 建议代码不要关键性地依赖此规范。当每个表达式最多包含一个侧边效应作为最外层操作，且代码不依赖于表达式从左到右求值的结果具体产生哪种异常时，代码通常会更清晰。

### 15.7.1 先求左侧操作数

二元运算符的左侧操作数在右侧操作数的任何部分求值之前，似乎已经完全求值。

如果该运算符是复合赋值运算符（§15.26.2），则左侧操作数的求值包括：记住左侧操作数所指示的变量，以及获取该变量的值以用于隐含的二元操作。

如果二元运算符的左侧操作数的求值异常完成，则右侧操作数的任何部分似乎都没有被求值。

#### 示例 15.7.1-1. 先求值的左侧操作数

在下面的程序中，`*` 运算符的左侧操作数包含一个赋值操作，右侧操作数包含对同一个变量的引用。引用产生的值将反映赋值已经发生的事实。

```java
class Test1 {

    public static void main(String[] args) {

        int i = 2;

        int j = (i=3) * i;

        System.out.println(j);

    }

}
```

该程序产生输出：

```
9
```

不允许 `*` 运算符的求值产生 6 而不是 9。

#### 示例 15.7.1-2. 复合赋值运算符中的隐式左侧操作数

在下面的程序中，两个赋值语句在加法运算符的右侧操作数求值之前，都获取并记了左侧操作数的值（即 9），随后该变量被设置为 3。

```java
class Test2 {

    public static void main(String[] args) {

        int a = 9;

        a += (a = 3); // 第一个示例

        System.out.println(a);

        int b = 9;

        b = b + (b = 3); // 第二个示例

        System.out.println(b);

    }

}
```

该程序产生输出：

```
12
12
```

不允许任何赋值（a 的复合赋值，b 的简单赋值）产生结果 6。

参见 §15.26.2 中的示例。

#### 示例 15.7.1-3. 左侧操作数求值的异常完成

```java
class Test3 {

    public static void main(String[] args) {

        int j = 1;

        try {

            int i = forgetIt() / (j = 2);

        } catch (Exception e) {

            System.out.println("Now j = " + j);

        }

    }

    static int forgetIt() throws Exception {

        throw new Exception("I'm outta here!");

    }

}
```

该程序产生输出：

```
java.lang.Exception: I'm outta here!
Now j = 1
```

也就是说，运算符的左侧操作数 `forgetIt()` 在右侧操作数求值以及对 j 赋值为 2 之前抛出了异常。

### 15.7.2 在操作前求值操作数

Java 编程语言保证运算符的每个操作数（条件运算符 `&&`, `||`, `?` 除外）在任何操作执行之前似乎都已完全求值。

如果二元运算符是整数除法（§15.17.2）或整数取模（§15.17.3），它的执行可能会抛出 `ArithmeticException`，但该异常只有在二元运算符的操作数都求值之后，且只有在这些求值正常完成的情况下才会被抛出。

#### 示例 15.7.2-1. 操作前的操作数求值

```java
class Test {

    public static void main(String[] args) {

        int divisor = 0;

        try {

            int i = divisor / loseBig();

        } catch (Exception e) {

            System.out.println(e);

        }

    }

    static int loseBig() throws Exception {

        throw new Exception("Shuffle off Buffalo!");

    }

}
```

该程序产生输出：

```
java.lang.Exception: Shuffle off Buffalo!
```

而不是：

```
java.lang.ArithmeticException: by zero
```

因为除法操作的任何部分（包括发出除以零异常）似乎都不可能在 `loseBig()` 求值完成之前发生，尽管实现可能能够推断出除法操作无疑会导致除以零异常。

### 15.7.3 求值尊重括号和优先级

Java 编程语言尊重由括号显式指示的顺序以及由操作符优先级隐式指示的求值顺序。

Java 编程语言的实现可能利用代数恒等式（如结合律）将表达式重写为更方便的计算顺序，除非能够证明替换后的表达式在值和可观测效应的存在上是等价的，即使在存在多个执行线程的情况下（§15.17 Threads and Locks 中的线程模型）；对于所有可能涉及的计算值均如此。

在浮点数计算的情况下，此规则也适用于无穷大（infinity）和非数字（NaN）值。

- 例如，`(x != y)` 可能不会被重写为 `x=y`，因为如果 x 或 y 为 NaN 或两者均为 NaN，这些表达式的值是不同的。

具体而言，在数学上似乎具有结合性的浮点数计算在计算上可能并不具有结合性。此类计算不能被简单地重新排序。

所以，例如，测试程序对于 Java 编译器来说将 `4.0*x*0.5` 重写为 `2.0*x` 是不正确的；虽然在这里舍入恰好是一个问题，但对于某些巨大的 x 值，第一个表达式会产生无穷大（因为溢出），而第二个表达式会产生一个有限的结果。

```java
strictfp class Test {

    public static void main(String[] args) {

        double d = 8e+307;

        System.out.println(4.0 * d * 0.5);

        System.out.println(2.0 * d);

    }

}
```

输出：

```
Infinity
1.6e+308
```

因为第一个表达式溢出了，而第二个没有。

相反，整数加法和乘法在 Java 编程语言中证明是结合的。例如 `a+b+c`，其中 a、b、c 是局部变量（简化假设避免涉及多线程和 volatile 变量），无论作为 `(a+b)+c` 还是 `a+(b+c)` 计算，始终产生相同的答案；如果 `b+c` 在代码附近，智能编译器可以使用此公共子表达式。

### 15.7.4 参数列表从左到右求值

在方法调用、构造调用或类实例中，参数表达式出现在括号内，用逗号分隔。在右侧任何参数表达式的任何部分之前，每个参数表达式似乎都已完全求值。

如果参数表达式的求值异常完成，则其右侧的参数表达式似乎都没有被求值。

#### 示例 15.7.4-1. 方法调用中的求值顺序

```java
class Test1 {

    public static void main(String[] args) {

        String s = "going";

        print3(s, s, s = "gone");

    }

    static void print3(String a, String b, String c) {

        System.out.println(a + b + c);

    }

}
```

该程序产生：

```
going, going, gone
```

因为将字符串 "gone" 赋值给 s 发生在 print3 前两个参数求值之后。

#### 示例 15.7.4-2. 参数表达式的异常完成

```java
class Test2 {

    static int id;

    public static void main(String[] args) {

        try {

            test(id = 1, oops(), id = 3);

        } catch (Exception e) {

            System.out.println(e + " ", id=" + id);

        }

    }

    static int test(int a, int b, int c) {

        return a + b + c;

    }

    static int oops() throws Exception {

        throw new Exception("oops");

    }

}
```

输出：

```
java.lang.Exception: oops  id=1
```



因为对 `id` 赋值 `3` 没有被执行。

## 15.7.5 其他表达式的求值顺序

某些表达式的求值顺序并没有被这些通用规则覆盖，因为这些表达式可能会在指定的时间抛出异常情况。请参见以下类型表达式求值顺序的详细说明：

- 类实例创建表达式 (§15.9.4)
- 数组创建表达式 (§15.10.2)
- 数组访问表达式 (§15.10.4)
- 方法调用表达式 (§15.12.4)
- 方法引用表达式 (§15.13.3)
- 涉及数组组件的赋值 (§15.26)
- Lambda 表达式 (§15.27.4)

## 15.8 主表达式

主表达式包括大多数最简单类型的表达式，所有其他表达式都是基于此构建的：字面量、对象创建、字段访问、方法调用、方法引用和数组访问。带括号的表达式在语法上也被视为主表达式。

### 主表达式语法

```
PrimaryNoNewArray
ArrayCreationExpression
```

### PrimaryNoNewArray 语法

```
PrimaryNoNewArray:
    Literal
    ClassLiteral
    this
    TypeName . this
    ( Expression )
    ClassInstanceCreationExpression
    FieldAccess
    ArrayAccess
    MethodInvocation
    MethodReference
```

Java 编程语言语法的这部分在两个方面是不寻常的。首先，人们可能期望简单的名称（如局部变量和方法参数的名字）是主表达式。由于技术原因，名称在稍后引入后缀表达式（§15.14）时，才与主表达式归类在一起。

技术原因在于允许在仅使用单标记前瞻（`one-token lookahead`）的情况下对 Java 程序进行从左到右的解析。考虑表达式 `([z])` 和 `([z)`。第一个是带括号的数组访问 (§15.10.3)，第二个是类型转换的开始 (§15.16)。在前瞻符号为 `[` 的点上，从左到右的解析已经将 `z` 归约为名称 `Name`。在类型转换的上下文中，我们倾向于不将 `z` 归约为主表达式 `Primary`，但如果 `Name` 是 `Primary` 的选项之一，我们在不向前看两个标记（即查看 `[` 之后的标记）的情况下无法判断是否归约 `(`（即我们无法确定当前情况将变成带括号的数组访问还是类型转换）。语法在这里通过保持 `Name` 和 `Primary` 分离，并在某些语法规则中允许二选一（适用于 `ClassCreationExpression`、`MethodInvocation`、`ArrayAccess` 和 `PostfixExpression` 的规则，但不包括 `FieldAccess`，因为它直接使用标识符）。这种策略有效地在检查更多上下文之前，推迟了关于 `Name` 是否应该被视为 `Primary` 的问题。

另一个不常见特征是表达式 `new int [[3]]` 中存在潜在的语法歧义，这在 Java 中始终意味着多维数组的单次创建，但如果没有适当的技巧，它可能被解释为与 `new int [[3]]` 相同。这种歧义通过将 `Primary` 的预期定义拆分为 `Primary` 和 `PrimaryNoNewArray` 来解决。（这与将 `Statement` 拆分为 `Statement` 和 `StatementNoElse` (§14.5) 以避免“悬空 else”问题类似。）

## 15.8.1 词法字面量

字面量 (§3.10) 表示一个固定的、不变的值。

为了方便起见，这里显示了 §3.10 中的产生式：

### Literal 语法

```
Literal:
    IntegerLiteral
    FloatingPointLiteral
    BooleanLiteral
    CharacterLiteral
    StringLiteral
    NullLiteral
```

字面量的类型确定如下：

- 以 `L` 或 `l` 结尾的整数字面量 (§3.10.1) 的类型为 `long` (§4.2.1)。
- 任何其他整数字面量的类型为 `int` (§4.2.1)。
- 以 `F` 或 `f` 结尾的浮点字面量 (§3.10.2) 的类型为 `float`，其值必须是 `float` 值集中的元素 (§4.2.3)。
- 任何其他浮点字面量的类型为 `double`，其值必须是 `double` 值集中的元素 (§4.2.3)。
- 布尔值字面量 (§3.10.3) 的类型为 `boolean` (§4.2.5)。
- 字符字面量 (§3.10.4) 的类型为 `char` (§4.2.1)。
- 字符串字面量 (§3.10.5) 的类型为 `String` (§4.3.3)。
- `null` 字面量 `null` (§3.10.7) 的类型为 `null` 类型 (§4.1)；其值是空引用。

词法字面量的求值总是正常完成。

## 15.8.2 类字面量

类字面量是一个由类、接口、数组或原始类型的名称，或伪类型 `void`，后跟 `.` 和标记 `class` 组成的表达式。

### ClassLiteral 语法

```
ClassLiteral:
    TypeName { } . class
    NumericType { } . class
    boolean { } . class
    void . class
```

`TypeName` 必须表示一个可访问的类或接口类型 (§6.6)。如果 `TypeName` 表示一个不可访问的类或接口类型，或表示一个类型变量，则为编译错误。

`C.class` 的类型（其中 `C` 是类、接口或数组类型的名称 (§4.3)）是 `Class<C>`。

`p.class` 的类型（其中 `p` 是原始类型的名称 (§4.2)）是 `Class<B>`，其中 `B` 是类型 `p` 的表达式在装箱转换后 (§5.1.7) 的类型。

`void.class` 的类型 (§8.4.5) 是 `Class<Void>`。

类字面量通过定义当前实例的类加载器 (§12.2)，求值为所命名类型（或 `void`）的 `Class` 对象。

## 15.8.3 this

关键字 `this` 只能用于以下上下文：

- 在实例方法或默认方法的体内部 (§8.4.7, §9.4.3)
- 在类的构造方法体内 (§8.8.7)
- 在类的实例初始化器内 (§8.6)
- 在类实例变量的初始化器内 (§8.3.2)
- 用于表示接收器参数 (§8.4)

如果它出现在其他任何地方，将发生编译错误。

关键字 `this` 只有在上下文中允许的情况下才能在 lambda 表达式中使用。否则，将发生编译错误。

当作为主表达式使用时，关键字 `this` 表示对调用实例方法的对象的引用。`this` 所表示的值与周围上下文中 `this` 所表示的值相同。

关键字 `this` 也用于显式构造器语句 (§8.8.7)。`this` 的类型是出现该关键字的类或接口。所有静态方法都不提供 `this`。

### 示例 15.8.3-1. this 表达式

```java
class IntVector {
    int[] v;

    boolean equals(IntVector other) {
        if (this == other) {
            return true;
        }
        if (v.length != other.length) {
            return false;
        }
        for (int i = 0; i < v.length; i++) {
            if (v[i] != other[i]) return false;
        }
        return true;
    }
}
```

`IntVector` 类实现了一个 `equals` 方法，用于比较两个向量。如果 `other` 向量与调用 `equals` 方法的向量是同一个对象，则可以跳过长度和值的比较。`equals` 方法通过比较引用 `this` 来进行这种检查。

## 15.8.4 限定 this

可以通过显式限定关键字 `this` 来引用任何词法外部的实例 (§8.1.3)。

设 `τ` 为 `TypeName` 表示的类型。设 `n` 为整数，使得 `τ` 是限定表达式所在的类或接口的第 `n` 个词法外部类型声明。

`TypeName.this` 形式的表达式的值是第 `n` 个词法外部实例。

该表达式的类型是 `τ`。

如果表达式发生在一个不是类或 `τ` 的内部类中，则为编译错误。

## 15.8.5 带括号表达式

带括号的表达式是一个主表达式，其类型为包含表达式的类型，其运行时值为包含表达式的值。如果包含表达式表示一个变量，则带括号的表达式也表示该变量。

括号的使用只影响求值顺序，有一个特殊情况：`(-2147483648)` 和 `(-9223372036854775808)` 是合法的，但 `(2147483648)` 和 `(9223372036854775808)` 是非法的。

这是因为十进制字面量 `2147483648` 和 `9223372036854775808` 仅允许作为一元减运算符的操作数 (§3.10.1)。

特别地，表达式周围是否存在括号（上述情况除外）不会以任何方式影响：

- 对于类型为 `float` 或 `double` 的表达式的值，影响其值集（§4.2.3）的值的选择。
- 变量是否被确定赋值、在为真时是否确定赋值、在为假时是否确定赋值、是否确定未赋值、在为真时是否确定未赋值或在为假时是否确定未赋值（§16 确定赋值）。

如果一个带括号的表达式出现在目标为 `τ` 的特定类型的上下文中（§5 转换与上下文），则其包含的表达式同样出现在目标类型为 `τ` 的相同类型的上下文中。

如果包含的表达式是一个多值表达式（§15.2），则带括号的表达式也是多值表达式。否则，它是一个独立表达式。

如果包含的表达式与目标类型 `τ` 兼容，则该带括号的表达式也与 `τ` 兼容。

## 15.9 类实例创建表达式

类实例创建表达式用于创建作为类实例的新对象。

### ClassInstanceCreationExpression 语法

```
ClassInstanceCreationExpression:
    UnqualifiedClassInstanceCreationExpression
    ExpressionName . UnqualifiedClassInstanceCreationExpression
    Primary . UnqualifiedClassInstanceCreationExpression
```

### UnqualifiedClassInstanceCreationExpression 语法

```
UnqualifiedClassInstanceCreationExpression:
    new [TypeArguments]
    ClassOrInterfaceTypeToInstantiate ( [ArgumentList] ) [ClassBody]
```

### ClassOrInterfaceTypeToInstantiate 语法

```
ClassOrInterfaceTypeToInstantiate:
    [Annotation] Identifier ( . [Annotation] Identifier )*
    [TypeArgumentsOrDiamond]
```

### TypeArgumentsOrDiamond 语法

```
TypeArgumentsOrDiamond:
    TypeArguments
    <>
```



# 类实例创建表达式

## 15.9 类实例创建表达式

为了方便起见，此处展示了 §15.12 中的以下产生式：

```
ArgumentList:
    Expression ( , Expression )
```

类实例创建表达式指定了一个要实例化的类，后面可能跟着类型参数（§4.5.1），或者如果所实例化的类是泛型（§8.1.2），则跟着菱形 (`<>`)，然后是构造函数的（可能为空）实际值参数列表。

如果类的类型参数列表为空——即菱形 `<>`——则类型参数将被推断。虽然在风格上强烈不建议，但在菱形的 `<` 和 `>` 之间存在空格是合法的。

如果构造函数是泛型的（§8.8.4），构造函数的类型参数也可以类似地被推断或显式传递。如果显式传递，构造函数的类型参数将紧跟在关键字 `new` 之后。

如果类实例创建表达式为构造函数提供了类型参数，但对类的类型参数使用了菱形形式，会导致编译错误。

> 引入此规则是因为泛型类类型参数的推断可能会影响泛型构造函数类型参数的约束。

如果 `TypeArguments` 紧跟在 `new` 之后或 `(` 之前，如果任何类型参数是通配符（§4.5.1），则会导致编译错误。

类实例创建表达式可以抛出的异常类型指定在 §11.2.1。

类实例创建表达式有两种形式：

- **未限定类实例创建表达式**以关键字 `new` 开头。未限定类实例创建表达式可用于创建类的实例，无论该类是顶层（§7.6）、成员（§8.5, §9.5）、局部（§14.3）还是匿名类（§15.9.5）。
- **限定类实例创建表达式**以 `Primary` 表达式或 `ExpressionName` 开头。

限定类实例创建表达式允许创建内部成员类及其匿名子类的实例。

未限定和限定的类实例创建表达式都可以可选地以类体结尾。此类类实例创建表达式声明了一个匿名类（§15.9.5）并创建了它的实例。

如果类实例创建表达式对类的类型参数使用菱形形式，并且出现在赋值文中或调用文中（§5.2, §5.3），则它是多值表达式（§15.2）。否则，它是一个独立表达式。

当类实例创建表达式对类的类型参数使用菱形形式且出现在赋值文中或调用文中时，它是多值表达式。当我们通过类实例创建表达式实例化类时，涉及到确定要实例化的类（15.9.1）、该类的实例（15.9.2）以及用于创建实例的构造函数（15.9.3）。

### 15.9.1 确定要实例化的类

如果 `ClassOrInterfaceTypeToInstantiate` 紧跟 `TypeArguments` 而不是 `<>`，则它必须是一个良好的类型类型（§4.5）。

如果 `ClassOrInterfaceTypeToInstantiate` 以 `<>` 结尾，但由 `ClassOrInterfaceTypeToInstantiate` 指定的类型不是泛型，会导致编译错误。

如果类实例创建表达式以类体结尾，则要实例化的类是匿名类。此时：

- 如果类实例创建表达式是非限定的，则：
  `ClassOrInterfaceTypeToInstantiate` 必须是一个可访问的、非抽象的且不是枚举的类，或者是一个接口（§6）。否则，会导致编译错误。

  如果 `ClassOrInterfaceTypeToInstantiate` 指定类 `c`，则声明 `c` 的匿名子类。如果存在 `TypeArguments`，则 `c` 拥有类型参数；如果存在 `<>`，则 `c` 的类型参数将被推断（15.9.3）；否则，`c` 没有类型参数。

  如果 `ClassOrInterfaceTypeToInstantiate` 指定接口 `i`，则声明一个实现 `i` 的匿名子类。如果存在 `TypeArguments`，则 `i` 拥有类型参数；如果存在 `<>`，则 `i` 的类型参数将被推断（15.9.3）；否则，`i` 没有类型参数。该子类的体由类实例创建表达式给出。要实例化的类是匿名类。

- 如果类实例创建表达式是限定的，则：
  `ClassOrInterfaceTypeToInstantiate` 必须是一个可访问的、非 final 的且不是枚举的类，或者是 `Primary` 表达式或 `ExpressionName` 编译类型的成员。否则，会导致编译错误。

  令 `ClassOrInterfaceTypeToInstantiate` 指定类 `c`。声明 `c` 的匿名子类。如果存在 `TypeArguments`，则 `c` 拥有类型参数；如果存在 `<>`，则 `c` 的类型参数将被推断（15.9.3）；否则，`c` 没有类型参数。该子类的体由类实例创建表达式给出。要实例化的类是匿名类。

如果类实例创建表达式没有声明匿名类，则：

- 如果类实例创建表达式是非限定的，则：
  `ClassOrInterfaceTypeToInstantiate` 必须是一个可访问的、非抽象的且不是枚举的类。否则，会导致编译错误。

  要实例化的类由 `ClassOrInterfaceTypeToInstantiate` 指定。如果存在 `TypeArguments`，则该类拥有类型参数；如果存在 `<>`，则该类的类型参数将被推断（15.9.3）；否则，该类没有类型参数。

- 如果类实例创建表达式是限定的，则：
  `ClassOrInterfaceTypeToInstantiate` 必须是一个可访问的、非抽象的、不是枚举的内部类，或者是 `Primary` 表达式或 `ExpressionName` 编译类型的成员。否则，会导致编译错误。

### 15.9.2 确定直接邻接实例

令 `c` 为被实例化的类，`i` 为正在创建的实例。

- 如果 `c` 是一个匿名类，则：
  - 如果类实例创建表达式发生在静态上下文中，则 `i` 没有直接邻接的实例。
  - 否则，`i` 的直接邻接的实例是 `this`。
- 如果 `c` 是一个局部类，则：
  - 如果 `c` 发生在静态上下文中，则 `i` 没有直接邻接的实例。
  - 否则，如果类实例创建表达式发生在静态上下文中，则发生编译时错误。
  - 否则，令 `o` 为 `c` 的直接邻接的类型声明。令 `n` 为一个整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法上嵌套的类型声明。`i` 的直接邻接的实例是 `this` 的第 `n` 个词法上嵌套的实例。
- 如果 `c` 是内部成员类，则：
  - 如果类实例创建表达式是未限定的，则：
    > 如果类实例创建表达式发生在静态上下文中，则发生编译时错误。
    > 否则，如果 `c` 是包含类实例创建表达式出现处的类的成员，令 `o` 为该 `c` 成员的直接邻接的类。令 `n` 为一个整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法上嵌套的类型声明。`i` 的直接邻接的实例是 `this` 的第 `n` 个词法上嵌套的实例。
    > 否则，发生编译时错误。
  - 如果类实例创建表达式是限定的，则 `i` 的直接邻接的实例是作为 `Primary` 表达式或 `ExpressionName` 的值代表的对象。

如果 `c` 是一个匿名类，且其直接超类 `s` 是一个内部类，则 `i` 可能对于 `s` 有一个相对于 `s` 的直接邻接的实例，其确定方式如下：

- 如果 `s` 是一个局部类，则：
  - 如果 `s` 发生在静态上下文中，则 `i` 没有相对于 `s` 的直接邻接的实例。
  - 否则，如果类实例创建表达式发生在静态上下文中，则发生编译时错误。
  - 否则，令 `o` 为 `s` 的直接邻接类型声明。令 `n` 为整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法上嵌套的类型声明。`i` 相对于 `s` 的直接邻接实例是 `this` 的第 `n` 个词法上嵌套的实例。
- 如果 `s` 是一个内部成员类，则：
  - 如果类实例创建表达式是未限定的，则：
    > 如果类实例创建表达式发生在静态上下文中，则发生编译时错误。
    > 否则，如果 `s` 是包含实例创建表达式出现处的类的成员，则令 `o` 为该 `s` 成员的直接邻接类。令 `n` 为整数，使得 `o` 是类实例创建表达式出现处的类的第 `n` 个词法上嵌套的类型声明。`i` 相对于 `s` 的直接邻接实例是 `this` 的第 `n` 个词法上嵌套的实例。
    > 否则，发生编译时错误。
  - 如果类实例创建表达式是限定的，则 `i` 相对于 `s` 的直接邻接实例是作为 `Primary` 表达式或 `ExpressionName` 的值代表的对象。

### 15.9.3 选择构造方法及其参数

令 `c` 为被实例化的类。为了创建 `c` 的实例，在编译时根据以下规则选择 `c` 的一个构造方法。

首先，确定构造方法调用的实际参数：

- 如果 `c` 是一个直接超类为 `s` 的匿名类，则：
  - 如果 `s` 不是内部类，或者 `s` 是发生在静态上下文中的局部类，则构造方法的参数是类实例创建表达式中参数列表中的参数（如果有的话），并按照它们在表达式中出现的顺序排列。
  - 否则，构造方法的第一个参数是 `i` 的直接邻接实例（§15.9.2），构造方法的后续参数是类实例创建表达式中参数列表中的参数（如果有的话），并按照它们在类实例创建表达式中出现的顺序排列。
- 如果 `c` 是局部类或 `private` 内部成员类，则构造方法的参数是类实例创建表达式中参数列表中的参数（如果有的话），并按照它们在类实例创建表达式中出现的顺序排列。
- 如果 `c` 是非 `private` 内部成员类，则构造方法的第一个参数是 `i` 的直接邻接实例（§8.8.1, §15.9.2），其后续参数是类实例创建表达式中参数列表中的参数（如果有的话），并按照它们在类实例创建表达式中出现的顺序排列。
- 否则，构造方法的参数是类实例创建表达式中参数列表中的参数（如果有的话），并按照它们在表达式中出现的顺序排列。

其次，确定 `c` 的构造方法以及相应的 `throws` 子句和返回类型：

- 如果类实例创建表达式没有使用 `<>`，则：
  - 如果 `c` 不是匿名类，则：
    令 `τ` 为 `c` 后跟任何类类型所表示的类型。使用经修改以处理构造方法的 §15.12.2 过程来选择 `τ` 的构造方法并确定其语句。
    如果 `τ` 中没有可用的且可访问的唯一最具体构造方法，则发生错误（见方法调用）。
    否则，对应构造方法的返回类型为 `τ`。
  - 如果 `c` 是匿名类，则：
    使用经修改以处理构造方法的 §15.12.2 过程来选择直接超类的构造方法并确定其语句。
    如果直接超类中没有可用的且可访问的唯一最具体构造方法，则发生错误（见方法调用）。
    否则，选择 `c` 的匿名构造方法作为 `c` 的构造方法（§15.9.5）。其主体包含直接超类的调用。
    对应构造方法的 `throws` 子句。该构造方法的返回类型为匿名类。
- 如果类实例创建表达式使用了 `<>`，则：
  - 如果 `c` 不是匿名类，则 `d` 与 `c` 相同。
  - 如果 `c` 是匿名类，则 `d` 为类实例创建表达式命名的超类或超接口。
    如果 `D` 是类，`c_1...c_n` 为 `D` 的构造方法。如果 `D` 是接口，则 `c_1...c_n` 是一个包含 `Object` 零参数构造方法的单例（`n=1`）。
    为了重载解析和参数推断定义方法 `m_1...m_n`。对于所有 (`j ≤ n`)，`m_j` 根据 `c_j` 定义如下：
    定义替换 `θ_j` 以实例化 `c_j`。
    - 令 `F_1...F_p` 为 `D` 的类型参数，`G_1...G_q` 为 `c_j` 的类型参数（如果有）。令 `X_1...X_p` 和 `Y_1...Y_q` 为在 `D` 体中作用域内的不同名称类型变量。

    ```
    θ_j 是 [F_1:=X_1, ..., F_p:=X_p, G_1:=Y_1, ..., G_q:=Y_q]。
    ```

    - `m_j` 的类型参数为 `X_1...X_p, Y_1...Y_q`。每个类型参数的边界（如果有）是 `θ_j` 应用于 `D` 或 `c_j` 中对应的类型参数边界。
    - `m_j` 的返回类型为 `θ_j` 应用于 `F_1...F_p`。
    - `m_j` 的参数列表（可能为空）是 `θ_j` 应用于 `c_j` 的参数类型。
    - `m_j` 的抛出类型列表（可能为空）是 `θ_j` 应用于 `c_j` 的抛出类型。
    - `m_j` 的修饰符为 `c_j` 的修饰符。
    - `m_j` 的名称为 `#m`，这是一个自动生成的名称，与 `D` 中所有构造方法和方法名称都不同，并由 `m_1...m_n` 共享。
    - `m_j` 的主体无关。

    为了选择构造函数，我们暂时将 `m_1...m_n` 视为 `D` 的成员。`m_1...m_n` 中的某一个被选中，这由类实例创建表达式的参数表达式确定，并使用 §15.12.2 中指定的过程。

    如果没有能找到一个既适用又可访问的唯一特定方法，则发生编译时错误。

    否则，假设 `m_j` 是被选的方法：
    - 如果 `c` 不是匿名类，则选择 `c_j` 作为 `c` 的构造函数。
    - 所选构造函数的 `throws` 子句（声明）与为 `m_j` 确定的 `throws` 子句相同。
    - 与所选构造函数对应的返回类型是为 `m_j` 确定的返回类型（§15.12.2.6）。
    - 如果 `c` 是匿名类，则选择 `c` 的匿名构造函数作为 `c` 的构造函数。其方法体包含一个对 `c_j` 的显式构造函数调用。
    - 所选构造函数的 `throws` 子句包含了为 `m_j` 确定的 `throws` 子句中的异常。
    - 与所选构造函数对应的返回类型是匿名类类型。

    如果类实例创建表达式是一个多表达式，则其与目标类型的兼容性由 §18.5.2.1 确定，并使用 `m_j` 作为选定的方法 `m`。

    > 在最终确定类实例创建表达式的目标和所选构造函数对应的返回类型之前，可能会多次发生与目标类型的兼容性测试。例如，嵌套的方法调用可能需要测试类实例创建表达式与不同形式参数类型的兼容性。

    如果 `c` 是匿名类，则它的超类或接口（§15.9.5）是为 `m_j` 确定的返回类型（§15.12.2.6）。

    如果超类或接口，或其中的任何子表达式（“子表达式”）包含类型参数、通配符类型参数的边界、以及数组类型的元素类型（但不排除类型变量的边界），且具有以下形式之一，则判定为编译时错误：
    - 未声明声明为类型参数的类型变量（例如由捕获转换产生的类型变量）。
    - 交叉类型。
    - 类或接口类型，其中该类或接口的声明从类实例创建表达式所在的类或接口是不可访问的。

    如果类实例创建表达式的参数与其推导自调用类型（§15.12.2.6）的目标类型不兼容，则判定为编译时错误。

    如果编译时声明通过可变参数个数调用（§15.12.2.4）适用，那么当构造函数调用类型的最后一个形式参数类型为 `F_n[]` 时，如果 `F_n` 擦除后的类型在调用点不可访问，则判定为编译时错误。

类实例创建表达式的类型是上文定义的与所选构造函数对应的返回类型。

## 15.9.4 类实例创建表达式的运行时评估

在运行时，类实例创建表达式的评估如下：

首先，如果类实例创建表达式是一个限定类实例创建表达式，则评估限定主表达式。如果限定表达式求值为 `null`，则抛出 `NullPointerException`，并且类实例创建表达式异常终止。如果限定表达式异常终止，则类实例创建表达式因相同原因异常终止。

接下来，为新类分配空间。如果空间不足以分配对象，则类实例创建表达式的评估通过抛出 `OutOfMemoryError` 异常终止。

新对象包含指定类类型中声明的所有字段的新实例，并且随着每个新字段的创建，它被初始化为其默认值（§14.2.5）。

接下来，从左到右评估构造函数的实际参数。如果任何一个参数的评估异常终止，则其右侧的任何参数将不再被评估，且类实例创建表达式因相同原因异常终止。

接下来，调用指定类类型的所选构造函数。这将导致为类类型的每个超类调用至少一个构造函数。此过程可以由显式构造函数调用语句（§8.8）指导，并在 §12.5 中详细说明。

类实例创建表达式的值是对新创建的指定类对象的引用。每当评估该表达式时，都会创建一个新对象。

### 15.9.4-1 评估顺序与内存溢出检测

如果评估类实例创建表达式发现没有足够的内存来执行操作，则抛出 `OutOfMemoryError`。此检查发生在任何参数表达式评估之前。

因此，例如，测试程序：

```
class List {
    int value;
    List next;
    static List head = new List(0);
    List(int n) { value = n; next = head; head = this; }
}

class Test {
    public static void main(String[] args) {
        int id = 0, oldid = 0;
        try {
            for(;;) {
                ++id;
                new List(oldid);
            }
        } catch (Error e) {
            List.head = null;
            System.out.println(e.getClass() + " " + (oldid));
        }
    }
}
```



`java.lang.OutOfMemoryError`, `false`

因为内存溢出条件在评估 `id` 之前就会检测。

将其与数组创建表达式的处理进行比较，后者的内存溢出条件在维度评估后检测 (§15.10.2)。

# 15.9.5 匿名类声明

匿名类由 Java 编译器从类实例创建表达式自动导出。

## 表达式

### 类实例创建表达式 15.9

匿名类永远不是抽象的 (§8.1.1)。

匿名类永远不是 `final` 的 (§8.1.2)。

匿名类不是 `final` 的事实在强制转换中是相关的，特别是允许的收窄引用转换 (§5.5)。它在子类化中也具有意义，尽管匿名类不是 `final`，但无法为匿名类声明子类 (§8.1.4)。

匿名类始终是内部类 (§8.1.3)；它不是静态的 (§8.5.1)。

匿名类的超类或接口由类实例创建表达式给出 (§15.9.1)，并在选择构造函数时进行推断 (§15.9.3)。

如果类实例创建表达式对匿名类使用 `<>`，则对于匿名类体中声明的所有非私有方法，仿佛该方法标记了 `@Override` (§9.6.4.4)。

> 当使用 `<>` 时，推断类型可能并非程序的预期。因此，匿名类的超类型可能并非预期，且匿名类中声明的方法可能按预期覆盖了超类型的方法。将此类方法标记为 `@Override`（如果它们没有显式标记 `@Override`）有助于避免编写错误的程序。

## 15.9.5.1 匿名构造函数

匿名类不能有显式声明的构造函数。相反，匿名类隐式声明了一个匿名构造函数。具有直接超类 `s` 的匿名类 `c` 的匿名构造函数形式如下：

- 如果 `s` 不是内部类，或者 `s` 是位于静态上下文中的局部类，则声明 `c` 的类实例创建表达式中的每个实际参数对应一个形式参数。

类实例创建表达式的实际参数用于确定 `s` 的构造函数 `cs`，如 §15.9.3 所示。匿名构造函数的每个形式参数的类型必须与 `cs` 对应的形式参数完全相同。

构造函数体包含一个形式为 `super(...)` 的显式构造函数调用 (§8.8.7.1)，其中实际参数为按声明顺序的形式参数。要调用的超类构造函数是 `cs`。

- 否则，`c` 的构造函数的第一个形式参数表示相对于 `s` 的 `i` 紧接包含的实例的值 (§15.9.2, §15.9.3)。该参数的类型是紧接包含 `s` 声明的类类型。

对于声明该匿名类的类实例创建表达式的每个实际参数，该构造函数都有一个额外的形式参数。第 `n'`- 个形式参数 `e` 对应于第 `n-1` 个实际参数。

类实例创建表达式的实际参数用于根据 §15.9.3 的规定确定 `s` 的一个构造函数 `cs`。匿名构造函数中每个形式参数的类型必须与 `cs` 对应的形式参数相同。

构造函数体由一个显式的构造函数调用 (§8.8.7.1) 组成，形式为 `o.super(...)`，其中 `o` 是构造函数的第一个形式参数，实际参数是构造函数的后续形式参数，按照它们声明的顺序排列。要调用的父类构造函数是 `cs`。

在所有情况下，匿名构造函数的 `throws` 子句必须列出由 §15.9.3 指定的匿名构造函数包含的显式父类构造函数调用语句抛出的所有检查异常，以及匿名类的任何实例初始化器或实例变量初始化器抛出的所有检查异常。

请注意，匿名构造函数的签名可能会引用一个不可访问的类型（例如，如果此类类型出现在父类构造函数 `cs` 的签名中）。这本身不会在编译时或运行时导致任何任何错误。

# 15.10 数组创建与访问表达式

## 15.10.1 数组创建表达式

数组创建表达式用于创建新数组 (§10 `Arrays`)

```
ArrayCreationExpression:
    new PrimitiveType DimExprs [Dims]
    new ClassOrInterfaceType DimExprs [Dims]
    new PrimitiveType Dims ArrayInitializer
    new ClassOrInterfaceType Dims ArrayInitializer
```

### DimExprs:
`DimExpr` [`DimExpr`]

### DimExpr:
`[` `Annotation` `]` [`Expression`]

为了方便起见，此处显示了 §4.3 中的产生式：

Dims:
`[]` [`[` `Annotation` `]` `[]`]

数组创建表达式创建一个对象，该对象是一个新数组，其元素类型由 `PrimitiveType` 或 `ClassInterfaceType` 指定。

如果 `ClassInterfaceType` 不表示可重构类型 (§4.7)，则为编译错误。否则，`ClassInterfaceType` 可以命名任何命名引用类型，即使是抽象类类型 (§8.1.1) 或接口类型。规则允许数组创建表达式中的元素不能是参数化类型，除非参数化类型的所有参数都是通配符。

`DimExpr` 内部每个维度表达式的类型必须是可转换为 (§5.8) 整数类型的类型，否则将发生编译错误。每个维度表达式都会经过数值提升 (§5.6)。数组创建表达式的类型是一个数组类型，其可以通过删除该数组创建表达式中的 `new` 关键字以及每个 `DimExpr` 表达式和数组初始化器而得到的表达式副本来表示。例如，创建表达式 `double[3][3][]` 的类型。

## 15.10.2 数组创建表达式的运行时求值

在运行时，数组创建表达式求值行为如下：

- 如果没有维度表达式，则必须有一个数组初始化器。新分配的数组将按照 §10.6 的描述，使用数组初始化器提供的值进行初始化。
- 否则，没有数组初始化器，且：
    - 首先，从左到右求值维度表达式。如果任何求值异常终止，则其右侧的表达式将不再求值。
    - 接下来，检查维度表达式的值。如果任何 `DimExpr` 的值小于 0，则抛出 `NegativeArraySizeException`。
    - 接下来，为新数组分配空间。如果没有足够的空间分配数组，则创建表达式的求值通过抛出 `OutOfMemoryError` 异常终止。
    - 然后，如果出现 `DimExpr`，则创建一个指定长度的一维数组，并将数组的每个组件都初始化为其默认值 (§4.12)。
    - 否则，如果出现 `n` 个 `DimExpr` 表达式，则数组创建实际上创建一个深度为 `n-1` 的嵌套循环，以创建隐含的数组。

多维数组在每一层不需要相同长度数组。

### 示例 15.10.2-1 数组创建

在具有一个或多个维度表达式的数组创建表达式中，每个维度表达式在其右侧任何维度表达式的部分之前都会完全求值。因此：

```
class Test1 {
    public static void main(String[] args) {
        int i = 4;
        int ia[][] = new int[i][3];
        System.out.println(ia.length + "," + ia[0].length);
    }
}
```

打印：
`4, 3`
因为在第二个维度表达式将 `i` 设置为 3 之前，第一个维度被计算为 4。

如果维度表达式的求值异常终止，其右侧任何维度表达式的部分都未被求值。因此：

```
class Test2 {
    public static void main(String[] args) {
        int[][] a = { { 0, 0 }, { 1, 1 } };
        int i = 99;
        try {
            a[val()][i] = 1;
        } catch (Exception e) {
            System.out.println(e + " i=" + i);
        }
    }
    static int val() throws Exception {
        throw new Exception("unimplemented");
    }
}
```

打印：
`java.lang.Exception: unimplemented, i=99`
因为设置 `i` 为 1 的嵌入赋值从未被执行。

### 示例 15.10.2-2 多维数组创建

声明：
```
float[][] matrix = new float[3][3];
```
在行为上等同于：
```
float[][] matrix = new float[3];
for (int d = 0; d < matrix.length; d++)
    matrix[d] = new float[3];
```

以及：
```
Age[][][][] Aquarius = new Age[6][10][8];
```
等同于：
```
Aquarius[][][][] = new Age[6][];
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
其中 `d, d1, d2, d3` 被替换为未定义的名称。因此，单个 `new` 表达式创建了一个长度为 6 的数组、6 个长度为 10 的数组、6x10=60 个长度为 8 的数组以及 6x10x8=480 个长度为 12 的数组。

可以通过以下方式创建三角形矩阵：
```
float[][] tri = new float[100][];
for (int i = 0; i < tri.length; i++)
    tri[i] = new float[i+1];
```

通过其他代码，例如：
```
Age[][] Hair = {new Age("quartz"), new Age("topaz")};
```

如果数组表达式求值发现内存不足以执行创建，则抛出 `OutOfMemoryError`。如果数组创建没有数组初始化器，则此检查在所有维度表达式求值完成后发生。通常，如果数组表达式维度确实有数组初始化器，则在求值变量初始化器期间分配引用类型对象时，或者为存储（可能的嵌套）数组初始化器值的数组分配空间时，可能会发生 `OutOfMemoryError`。

```
class Test3 {
    public static void main(String[] args) {
        int len, oldlen = 0;
        Object[] a = new Object[0];
        try {
            for (len = 0; ; len++) {
                Object[] temp = new Object[oldlen=len];
                a[oldlen] = temp;
            }
        } catch (Error e) {
            System.out.println(e + " " + (oldlen=len));
        }
    }
}
```

此程序产生输出：
```
java.lang.OutOfMemoryError, true
```
因为在评估维度表达式 `oldlen = len` 之后检测到了内存溢出条件。

将此与类实例创建表达式 (§15.9) 进行比较，后者在评估参数表达式 (§15.9.4) 之前就已检测到内存溢出条件。

## 15.10.3 数组访问表达式

数组访问表达式指的是作为数组的组件的变量。

```
ArrayAccess:
    ExpressionName [ Expression ]
    PrimaryNoNewArray [ Expression ]
```

一个数组访问表达式包含两个子表达式：数组引用表达式（左括号之前）和索引表达式（括号内）。

> 数组引用表达式可以是一个名称，也可以是任何不是数组创建表达式的主类型表达式 (§15.10)。

数组引用表达式的类型必须是数组类型（称之为 `T[]`），其组件的类型必须为 `T`，否则将发生编译时错误。

索引表达式经过一元数值提升 (§5.6.1)。提升后的类型必须是 `int`，否则将发生编译时错误。

数组访问表达式的类型是对 `T` 应用捕获转换 (§5.1.10) 后的结果。

数组访问表达式的结果是一个类型为 `T` 的变量，即由索引表达式的值所选定的数组中的变量。

这个结果变量是数组的组件，它从不被视为 `final`，即使数组引用表达式指向的是一个 `final` 变量。

## 15.10.4 数组访问表达式的运行时评估

在运行时，数组访问表达式的评估行为如下：

- 首先，评估数组引用表达式。如果该评估异常地完成，则数组访问也以相同原因异常地完成，且不评估索引表达式。
- 否则，评估索引表达式。如果该评估异常地完成，则数组访问以相同原因异常地完成。
- 否则，如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 否则，如果索引表达式的值小于 0 或大于等于数组的长度，则抛出 `ArrayIndexOutOfBoundsException`。
- 否则，数组访问的结果是类型为 $\tau$ 的值，位于数组中，由数组的值选取。

### 示例 15.10.4-1. 优先评估数组引用

在数组访问中，括号左侧的表达式在括号内的任何表达式被评估之前，似乎已经完全被评估。例如，在（诚然怪异的）表达式 `a(a=b[3])` 中，表达式 `a` 在表达式 `(a=b[3])` 之前已完全被评估；这意味着在评估表达式 `(a=b)` 时，获取并记录了 `a` 的原始值。这个由 `a` 的原始值引用的值随后通过由 `b` 引用且现在由 `a` 引用的另一个数组（可能是同一个数组）的元素 3 的值进行订阅。

因此，该程序：
```
class Test1 {
    public static void main(String[] args) {
        int[] a = { 11, 12, 13, 14 };
        int[] b = { 0, 1, 2, 3 };
        System.out.println(a[(a=b[3])]);
    }
}
```
打印：
`14`
因为该怪异表达式的值等于 `a[b[3]]` 或 `a[3]` 或 `14`。

### 示例 15.10.4-2. 数组引用评估的异常完成

如果括号左侧表达式的评估异常完成，则括号内的表达式没有任何部分似乎被评估过。因此，该程序：
```
class Test2 {
    public static void main(String[] args) {
        try {
            int index = 1;
            skedaddle()[index=2]++;
        } catch (Exception e) {
            System.out.println(e + ", index=" + index);
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
因为对 `index` 赋值 2 的嵌入赋值从未发生。

### 示例 15.10.4-3. null 数组引用

如果数组引用产生的是 `null` 而不是对数组的引用，则在运行时抛出 `NullPointerException`，但只有在数组访问表达式的所有部分都已评估之后，且仅当这些表达式正常完成时。该程序：
```
class Test3 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada()[index=2]++;
        } catch (Exception e) {
            System.out.println(e + ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```
打印：
```
java.lang.NullPointerException, index=2
```
因为对 `index` 赋值 2 的嵌入赋值发生在检查空数组引用异常的之前。作为一个相关的示例，该程序：
```
class Test4 {
    public static void main(String[] args) {
        int[] a = null;
        try {
            int i = a[vamoose()];
            System.out.println(i);
        } catch (Exception e) {
            System.out.println(e);
        }
    }
    static int vamoose() throws Exception {
        throw new Exception("Twenty-three!");
    }
}
```
打印：
```
java.lang.Exception: Twenty-three!
```



# 15.11 字段访问

字段访问表达式可以是一个 `super` 关键字，或者任何主类型表达式（§15.10）。

```
FieldAccess:
    Primary . Identifier
    super . Identifier
    TypeName . super
```

# 15.11.1 使用主类型的字段访问

数组引用表达式的类型必须是数组类型（称之为 `T[]`），其组件的类型必须为 `T`。

1. 数组访问表达式的类型是 `T`。

2. 数组引用表达式的类型必须是数组类型（称之为 `T[]`），其组件的类型必须为 `T`，否则将发生编译时错误。

3. 索引表达式经过一元数值提升（§5.6.1）。提升后的类型必须是 `int`，否则将发生编译时错误。

4. 数组访问表达式的类型是对 `T` 应用捕获转换（§5.1.10）后的结果。

5. 数组访问表达式的结果是一个类型为 `T` 的变量，即由索引表达式的值所选定的数组中的变量。

这个结果变量是数组的组件，它从不被视为 `final`，即使数组引用表达式指向的是一个 `final` 变量。

# 15.10.4 数组访问表达式的运行时评估

在运行时，数组访问表达式的评估行为如下：

- 首先，评估数组引用表达式。如果该评估异常地完成，则数组访问也以相同原因异常地完成，且不评估索引表达式。
- 否则，评估索引表达式。如果该评估异常地完成，则数组访问以相同原因异常地完成。
- 否则，如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 否则，如果索引表达式的值小于 0 或大于等于数组的长度，则抛出 `ArrayIndexOutOfBoundsException`。
- 否则，数组访问的结果是类型为 `T` 的值，位于数组中，由数组的值选取。

# 示例 15.10.4-1. 优先评估数组引用

在数组访问中，括号左侧的表达式在括号内的任何表达式被评估之前，似乎已经完全被评估。例如，在（诚然怪异的）表达式 `a[(a=b[3])]` 中，表达式 `a` 在表达式 `(a=b[3])` 之前已完全被评估；这意味着在评估表达式 `(a=b[3])` 时，获取并记录了 `a` 的原始值。这个由 `a` 的原始值引用的值随后通过由 `b` 引用且现在由 `a` 引用的另一个数组（可能是同一个数组）的元素 3 的值进行下标访问。

因此，该程序：

```java
class Test1 {
    public static void main(String[] args) {
        int[] a = { 11, 12, 13, 14 };
        int[] b = { 0, 1, 2, 3 };
        System.out.println(a[(a=b[3])]);
    }
}
```

打印：

```
14
```

因为该怪异表达式的值等于 `a[b[3]]` 或 `a[3]` 或 `14`。

# 示例 15.10.4-2. 数组引用评估的异常完成

如果括号左侧表达式的评估异常完成，则括号内的表达式没有任何部分似乎被评估过。因此，该程序：

```java
class Test2 {
    public static void main(String[] args) {
        try {
            int index = 1;
            skedaddle()[index=2]++;
        } catch (Exception e) {
            System.out.println(e + ", index=" + index);
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

因为对 `index` 赋值 2 的嵌入赋值从未发生。

# 示例 15.10.4-3. null 数组引用

如果数组引用产生的是 `null` 而不是对数组的引用，则在运行时抛出 `NullPointerException`，但只有在数组访问表达式的所有部分都已评估之后，且仅当这些表达式正常完成时。该程序：

```java
class Test3 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada()[index=2]++;
        } catch (Exception e) {
            System.out.println(e + ", index=" + index);
        }
    }

    static int[] nada() { return null; }
}
```

打印：

```
java.lang.NullPointerException, index=2
```

因为对 `index` 赋值 2 的嵌入赋值发生在检查空数组引用异常之前。作为一个相关的示例，该程序：

```java
class Test4 {
    public static void main(String[] args) {
        int[] a = null;
        try {
            int i = a[vamoose()];
            System.out.println(i);
        } catch (Exception e) {
            System.out.println(e);
        }
    }

    static int vamoose() throws Exception {
        throw new Exception("Twenty-three!");
    }
}
```

打印：

```
java.lang.Exception: Twenty-three!
```

# 15.11 字段访问（续）

```java
public static void main(String[] args) {
    T t = new T();
    System.out.println("t.x=" + t.x + " when(" + t + ")");
    S s = new S();
    System.out.println("s.x=" + s.x + " when(" + s + ")");
    s = t;
    System.out.println("s.x=" + s.x + " when(" + when("s", s) + ")");
}

static String when(String name, Object t) {
    return "when " + name + " holds a " + t.getClass() + " at time.";
}
```

该程序产生输出：

```
t.x=1 when(T@hash)
s.x=0 when(S@hash)
s.x=1 when(T@hash)
```

最后一行显示，所访问的字段并不取决于被引用对象的运行时类；即使 `s` 持有一个指向 `T` 对象的引用，表达式 `s.x` 指向的也是 `S` 中的 `x` 字段，因为表达式的类型是 `S`。类 `T` 的对象包含两个名为 `x` 的字段，一个属于类 `T`，一个属于其父类 `S`。字段的动态查找允许程序通过简单的实现高效运行。晚期绑定和覆盖的力量是可用的，但仅在使用实例方法时有效。考虑使用实例方法访问字段的相同示例：现在的输出是：

```
t.z=1 when(T@hash)
s.z=0 when(S@hash)
s.z=1 when(T@hash)
```

最后一行显示，确实，访问的方法取决于被引用对象的运行时类；即使 `s` 持有一个指向 `T` 对象的引用，尽管表达式的类型是 `S`，表达式 `s.z` 仍然指向的是类 `T` 的 `z` 方法。类 `T` 的方法重写了类 `S` 的方法。

## 15.11.2 接收变量与无关

以下程序演示了空引用可以用于访问（静态）变量而不会引发异常：

```java
class Test3 {
    static String mountain = "mocha";

    static String favorite() {
        return null;
    }

    public static void main(String[] args) {
        System.out.println(favorite().mountain);
    }
}
```

它通过编译、执行并打印：

```
mocha
```

即使 `favorite()` 为 `null`，也没有抛出 `NullPointerException`。

### 示例 15.11.2-1. super 表达式

```java
interface I { int x = 0; }

class T1 implements I { int x = 1; }

class T2 extends T1 { int x = 2; }

class T3 extends T2 {
    int x = 3;

    void test() {
        System.out.println("*x\t\t\t" + x);
        System.out.println("*super.x\t" + super.x);
        System.out.println("*((T2)this).x\t" + ((T2)this).x);
        System.out.println("*((T1)this).x\t" + ((T1)this).x);
        System.out.println("*((I)this).x\t" + ((I)this).x);
    }
}
```

该程序产生输出：

```
x=3
super.x=2
((T2)this).x=2
((T1)this).x=1
((I)this).x=0
```

# 15.12 方法调用表达式

方法调用表达式用于调用类方法或实例方法。

```
MethodInvocation:
    MethodName ( [ArgumentList] )
    Identifier ( [ArgumentList] )
    TypeName . [TypeArguments] Identifier ( [ArgumentList] )
    ExpressionName . [TypeArguments] Identifier ( [ArgumentList] )
    Primary . [TypeArguments] Identifier ( [ArgumentList] )
    super . [TypeArguments] Identifier ( [ArgumentList] )
    TypeName . super . [TypeArguments] Identifier ( [ArgumentList] )

ArgumentList:
    Expression [ , Expression ]
```



在编译时解析方法名比解析字段更复杂，因为可能存在方法重载。在运行时调用方法也比访问字段复杂，因为可能存在实例方法重写。

确定方法调用表达式将调用的方法涉及几个步骤。以下三个章节描述了方法调用的编译时处理。方法调用的类型确定在 §15.12.3 中规定。

## 字段表达式

如果 `super.f` 出现在 `Object` 声明中，由于 `Object` 没有父类，这是一个编译错误。假设 `super.f` 出现在类 `C` 中且直接父类是 `s`。如果 `f` 在 `s` 中是可访问的（§6.6），则 `super.f` 被视为在类 `s` 体中的 `this.f`。否则，将发生编译错误。`super.f` 可以访问类 `s` 中可访问的字段，即使它被类 `s` 的声明所覆盖。如果当前类不是内部类，则这是一个编译错误。

## 15.12.1 编译时步骤 1：确定的类或接口

编译时处理方法调用的第一步是确定要调用的方法名称以及要在哪个类或接口中搜索。

方法名由紧邻方法调用左括号的 `MethodName` 或 `Identifier` 指定。

对于要搜索的类或接口，根据方法调用左括号前的形式有六种情况：

- 如果形式是 `MethodName`（即 `Identifier`），则：
  - 如果 `Identifier` 出现在该方法的作用范围内（§6.3, §6.4.1），则：
    - 如果存在该方法的内部类型声明，令 $\tau$ 为该内部声明。要搜索的类或接口是 $\tau$。
      这种搜索策略被称为“comb规则”。它实际上在查找外部类及其父类层次的方法之前，先在嵌套类的父类层次中查找。参见 §6.5.7.1。
    - 否则，方法声明可能由于一个或多个静态导入或按需静态导入而存在。没有类或接口需要搜索，因为要调用的方法稍后确定（§15.12.2.1）。

- 如果形式是 `TypeName . [TypeArguments] Identifier`，则要搜索的类型是 `TypeName` 指定的类型。

- 如果形式是 `ExpressionName . [TypeArguments] Identifier`，则如果 `ExpressionName` 指定的变量的声明类型 $\tau$ 是类或接口类型，则是 $\tau$；如果 $\tau$ 是类型变量，则是其上界。

- 如果 `Identifier` 左侧存在 `TypeArguments`，如果任何类型参数是通配符，则编译错误（§4.5）。

如果满足以下所有条件，方法调用表达式是一个多值表达式（polyexpression）：
- 调用出现在赋值上下文或调用上下（§5.2, §5.3）。
- 如果调用是限定的（即除第一个 `MethodInvocation` 外），则调用省略 `Identifier` 左侧的 `TypeArguments`。
- 由后续章节确定的要调用的方法是泛型的（§8.4.4），且其返回类型提到了该方法的至少一个参数。

## 表达式 方法调用表达式 15.12

- 如果形式为 `Primary.[TypeArguments] Identifier`，则令 $\tau$ 为 `Primary` 表达式的类型。要搜索的类或接口：如果 $\tau$ 是类或接口类型，则为 $\tau$；如果 $\tau$ 是类型变量，则为 $\tau$ 的上界。
  如果 $\tau$ 不是引用类型，则为编译错误。

- 如果形式为 `super.[TypeArguments] Identifier`，则要搜索的类是包含该方法调用声明的类的超类。
  令 $\tau$ 为紧邻包含该方法调用的类型声明。如果 $\tau$ 是 `Object` 类或 $\tau$ 是接口，则为编译错误。

- 如果形式为 `TypeName.super`：
  - 如果 `TypeName` 既不表示类也不表示接口，则为编译错误。
  - 如果 `TypeName` 表示类 $C$，则该类是 $C$ 的超类。
    如果 $C$ 不是当前类的词法上包围的类型声明，或者 $C$ 是 `Object` 类，则为编译错误。
    令 $\tau$ 为紧邻包含该方法调用的类型声明。如果 $\tau$ 是 `Object` 类，则为编译错误。
  - 其他情况下，`TypeName` 表示要的接口 $I$。
    令 $\tau$ 为紧邻包含该方法调用的类型声明。如果 $I$ 不是 $\tau$ 的直接超接口，则为编译错误。

`TypeName.super` 语法是重载的：传统上，`TypeName` 指向词法上包围的类声明，如果调用是词法上包围的类型声明中的未限定 `super`，则目标是该类的超类。

```java
class Superclass {
    void foo() { System.out.println("Hi"); }
}
```

```java
class Subclass extends Superclass {
    void foo() { throw new UnsupportedOperationException(); }
}
```

```java
Runnable tweak = new Runnable() {
    void run() {
        Subclass.super.foo(); // 获取 'println' 行为
    }
}
```

## 15.12 方法调用表达式

为了支持在超接口中对默认方法的调用，`TypeName` 也可以指向当前类或接口的直接超接口，并且目标是该超接口。

```java
interface Superinterface {
    default void foo() { System.out.println("Hi"); }
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

没有语法支持这些形式的组合，即调用一个词法上包围的类声明的超接口方法，就像该调用是针对词法上包围的类型声明中的 `InterfaceName.super` 一样。

```java
class Subclass3 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); }

    Runnable tweak = new Runnable() {
        void run() {
            Subclass3.Superinterface.super.foo(); // 非法
        }
    }
}
```

一种解决方法是在词法上包围的类型声明中引入一个私有方法，执行接口超调用。

### 15.12.2 编译时步骤 2：确定方法签名

第二步在上一步定义的类型中搜索成员方法。此步使用方法名称和参数表达式来定位既可访问又适用的方法，即可以在给定参数上正确调用的声明。

可能存在多个这样的方法，在这种情况下将选择最具体的（most specific）方法。最具体的方法的描述符（签名加返回类型）用于运行时执行方法分派。

包含隐式类型 lambda 表达式（§15.27.1）或不精确方法引用（§15.13.1）的参数表达式会被适用性测试忽略，因为在选择调用的目标类型之前，无法确定它们的含义。另一方面，只有参数表达式——而不是调用的目标类型——会影响适用性测试，即使该方法调用是一个多态表达式（poly expression）。

确定适用性的过程始于确定潜在的可适用的方法（§15.12.2.1）。然后，为了确保与 Java SE 5.0 之前的 Java 编程语言兼容，该过程分三个阶段继续：

1. 第一阶段执行重载解析，但不允许装箱（boxing）或拆箱（unboxing）转换，也不允许使用可变参数长度调用。如果在此阶段未找到适用的方法，则继续进入第二阶段。
   这保证了在 SE 5.0 之前的 Java 编程语言中有效的任何调用都不会因为引入可变参数方法、隐式装箱和/或拆箱而被视为歧义。然而，可变参数方法（§8.4）的声明可能会更改为给定方法调用表达式选择的方法，因为可变参数方法在第一阶段被视为固定参数方法。例如，在一个已经声明了 `m(Object)` 的类中，会导致 `m(Object)` 不再被某些调用表达式（如 `m(null)`）所选择，因为 `m([])` 更具体。

2. 第二阶段执行重载解析，允许装箱和拆箱，但仍然排除使用可变参数长度调用。如果在此阶段未找到适用的方法，则继续进入第三阶段。
   这确保了方法通过固定参数是适用的。

3. 第三阶段允许重载与可变参数方法结合。如果方法在三个阶段之一被识别出来，则如 15.12.2 节所述选择最具体的那个。

为了检查适用性，输入是参数列表，即使参数的类型未知。这是因为：
- 多态表达式在缺少目标类型的情况下无法类型。
- 重载解析在参数目标类型已知之前完成。
- 参数可以与目标类型进行兼容性检查。

注意重载解析独立于目标类型，原因有两个：
- 第一，这使得用户模型更易访问且不易出错。方法的含义（即对应方法的声明）是基础性的，不依赖上下文提示。方法可能会根据目标类型有不同的行为；但这种变化是有限的，本质上，对于具有相同名称和参数数量的任意方法不存在这种保证。
- 第二，它允许其他属性——例如方法是否为多态表达式（15.12）或如何分类条件表达式（15.25）——在类型类型之前取决于方法的名称。

#### 示例 15.122-1. 方法适用性

```java
class Doubler {
    static int two() { return two(1); }
    private static int two(int i) { return 2*i; }
}

class Test extends Doubler {
    static long two(long j) { return j+j; }
}

public static void main(String[] args) {
    System.out.println(two(3));
    System.out.println(Doubler.two(3)); // 编译错误
}
```

对于 `Doubler` 类中的方法调用 `two(1)`，有两个名为 `two` 的可访问方法，但只有一个是适用的，因此该方法在运行时被调用。

对于 `Test` 类中的方法调用 `two(3)`，有两个适用的方法，但只有 `Test` 中的那个是可见的，因此该方法在运行时被调用（参数 3 被转换为 `long`）。

对于方法调用 `Doubler.two(3)`，搜索的是 `Doubler` 类而不是 `Test` 类的 `two` 方法；唯一适用的方法是不可的，因此该方法调用导致编译错误。

另一个示例是：

# 表达式

## 方法调用表达式 15.12

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
        cp.setColor(37); // 时错误
    }
}
```

在这里，第二次调用 `setColor` 会发生编译时错误，因为在编译时找不到适用的方法。字面量 37 是 `int` 类型，而 `int` 无法通过调用转换（invocation conversion）转换为 `byte`。在变量 `color` 初始化时使用的赋值转换（assignment conversion）执行了从 `int` 到 `byte` 的隐式转换，这是允许的，因为值 37 足够小，可以用 `byte` 类型表示；但调用转换是不允许这种转换的。

如果 `setColor` 方法声明为接收 `int` 而不是 `byte`，那么两种调用方式都是正确的；第一次调用将被允许，因为调用转换允许从 `byte` 到 `int` 的宽转换。然而，在 `setColor` 的体中则需要一个窄强制转换（narrowing cast）：

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
        System.out.println("Point, ColoredPoint");
    }
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        test(cp, cp); // 编译错误
    }
}
```

这会在编译时产生错误。问题在于有两个适用且可访问的 `test`，且其中任何一个都不另一个另一个具体。因此，该方法调用是歧义的。

如果添加 `test` 的第三个定义：

```java
static void test (ColoredPoint p, ColoredPoint q) {
    System.out.println("*(ColoredPoint, ColoredPoint)*");
}
```

那么它将比另外两个更具体，方法调用将不再具有歧义。

### 示例 15.12.2-2. 在方法选择时不考虑返回类型

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

在这里，方法 `test` 最具体的声明是接收 `ColoredPoint` 类型参数的泛一个。由于方法的结果类型是 `int`，因此发生了编译时错误，因为 `int` 无法通过赋值转换转换为 `String`。这个示例表明，方法的结果不参与重载方法的解析，因此第二个返回 `String` 的 `test` 方法没有被选中，尽管它可以允许程序无错误地编译。

### 示例 15.12.3. 最具体的方法

最具体的方法是在编译时选择的；如果类中添加了新方法，使用该方法编译的源代码可能不会改变。例如，考虑两个编译单元，一个针对 `Point`：

```java
package points;

class Point {
    int x, y;
    public String toString() {
        return "Point";
    }
}
```

另一个针对 `Test`：

```java
package points;

class ColoredPoint extends Point {
    int color;
    public void adapt(Point p) {
        x = p.x;
        y = p.y;
    }
    public String toString() {
        return "ColoredPoint";
    }
}
```

如果程序员使用新的 `ColoredPoint` 二进制文件运行旧的 `Test` 二进制文件，输出是：

```
Point
```

因为旧的 `Test` 二进制文件仍然描述为 "one parameter, type Point"。如果重新编译 `Test` 的源代码，Java 编译器将会发现现在有两个适用方法，并且更具体的那个签名是 "one parameter, type ColoredPoint"；运行程序将产生预期的输出：

```
ColoredPoint
```

考虑到这些问题，`points` 包的维护者可以通过在旧的 `adapt` 方法中添加防御性代码（为了调用它的旧代码）来修复 `ColoredPoint` 类以兼容新编译和旧的代码：

```java
public void adapt(Point p) {
    if (p instanceof ColoredPoint)
        color = ((ColoredPoint)p).color;
    x = p.x;
    y = p.y;
}
```



### 15.12.1 识别适用方法

通过编译时步骤 1 ($15.12.1) 确定的类或接口被搜索所有对该方法调用可能所需的成员方法；从超类和超接口继承的成员也包含在搜索中。

此外，如果方法调用表达式的形式是 `MethodName`（即，单个标识符）——那么对潜在适用方法的搜索还将检查通过单静态导入（`single-static-import`）导入的所有成员方法。

方法调用发生处的编译单元中的声明和按需导入的静态声明（§7.5.3, §7.5.4），且这些声明在方法调用出现的地方未被遮蔽。

一个方法对某个方法调用是*潜在适用的*（potentially applicable），当且仅当以下所有条件均真时：

- 成员的名称与方法调用中的方法名称相同。
- 该成员对于方法调用出现处的类或接口是可访问的（§6.6）。

> 方法在方法调用处是否可访问，取决于由编译时步骤 1 确定的类或接口继承中的修饰符（*public*、*protected*、无修饰符（包级访问）或 *private*），以及方法调用出现的位置。

- 如果该成员是一个元个数为 $n$ 的固定数组方法，则该方法调用的元个数等于 $n$，且对于所有 $i$ ($1 \le i \le n$)，方法调用的第 $i$ 个参数与方法的第 $i$ 个参数的类型是*潜在兼容的*（potentially compatible，见下文）。
- 如果该成员是一个元个数为 $n$ 的变量数组方法，则对于所有 $i$ ($1 \le i \le n-1$)，方法的第 $i$ 个参数与方法的第 $i$ 个参数的类型是*潜在兼容的*；并且，当方法的第 $n$ 个参数类型为 $T[]$ 时，以下任一成立：
    - 方法调用的元个数等于 $n$。
    - 方法调用的第 $n$ 个参数与 $\tau$ 或 $T[]$ 潜在兼容的。
    - 方法调用的元个数为 $m$，其中 $m > n$，且对于所有 $i$ ($n \le i \le m$)，方法调用的第 $i$ 个参数与 $\tau$ 是潜在兼容的。

如果方法调用包含了显式参数，且该成员是一个泛型方法，则参数的数量等于该方法类型参数的数量。

此条款意味着，非泛型方法可能适用于一个提供了显式类型参数的调用。事实上，它可能证明是适用的。在这种情况下，类型参数将被简单忽略。

此规则源于兼容性问题和可替换原则。由于接口或超类可以泛型地独立于其子类型，它们用非泛型方法重写泛型方法。然而，重写后的（非泛型）方法必须适用于对泛型方法的调用，包括显式传递类型参数的调用。否则，子类型将无法替换其泛型超类型。

如果搜索没有产生至少一个潜在适用的方法，则会发生编译错误。

表达式与目标类型是*潜在兼容的*（potentially compatible）遵循以下规则：

- 一个 lambda 表达式（§15.27）与函数接口 $T$（§9.8）潜在兼容的，当且仅当以下所有条件均真：
    - $T$ 的函数类型数组（§9.9）与 lambda 表达式的数组相同。
    - 如果 $T$ 的类型具有 void 返回值，则 lambda 体要么是一个语句表达式（§14.8），要么是一个 void 兼容代码块（§15.27.2）。
    - 如果 $T$ 的类型有（非 void）返回类型，则 lambda 体要么是一个表达式，要么是一个值兼容块（§15.27.2）。

- 方法引用表达式（§15.13）与函数接口 $T$ 潜在兼容，其中 $T$ 的函数类型数组为 $n$，且当方法引用表达式目标数组为 $n$ 的函数类型时存在至少一个潜在适用的方法（§15.13.1），且以下任一成立：
    - 方法引用表达式的形式为 `ReferenceType::<TypeArguments>::Identifier`，且至少一个潜在适用的方法是 (i) `static` 且支持数组 $n$，或 (ii) 非 `static` 且支持数组 $n-1$。
    - 方法引用表达式的形式其他，且至少一个潜在适用的方法不是 `static`。

- 如果类型变量是候选方法的类型参数，则 lambda 表达式或方法引用表达式与该类型是潜在兼容的。

- 如果带括号表达式（§15.8.5）包含的表达式与该类型潜在兼容，则该表达式是潜在兼容的。

- 如果条件表达式（§15.25）的第二个和第三个表达式都与该类型潜在兼容，则其是潜在兼容的。

- 类创建表达式、方法调用表达式或独立形式的表达式（§15.2）与任何类型都是潜在兼容的。

### 15.12.2.2 阶段 1：识别通过严格调用适用的匹配元个数方法

对于潜在适用的方法 $m$，参数表达式被认为与适用性相关（pertinent to applicability），除非它具有以下情况之一：

- 隐式类型化的 lambda 表达式（§15.27.1）。
- 不精确的方法引用表达式（§15.13.1）。
- 如果 $m$ 是一个泛型方法且方法调用未提供显式类型参数，则一个显式类型 lambda 表达式或其对应目标类型（从 $m$ 的签名推导出）为 $m$ 的类型参数的精确方法引用表达式。
- lambda 体与适用性不相关的显式类型 lambda 表达式。
- lambda 体为代码块且其中至少一个结果表达式与适用性不相关的显式类型 lambda 表达式。
- 包含的表达式与适用性不相关的带括号表达式（§15.8.5）。
- 第二或第三操作数与适用性不相关的条件表达式（§15.25）。

令 $m$ 为元个数为 $n$ 形式参数类型为 $F_1 ...F_n$ 的潜在适用方法（§15.12.2.1），并令 $e_1, ... e_n$ 为方法调用的实际参数表达式。那么：

- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则方法的适用性按照 §18.5 的规定推断。
- 如果 $m$ 是泛型方法且方法调用提供了显式参数，令 $R_1, ..., R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_j$ 为 $R_j$ 的边界，令 $U_1 ... U_p$ 为方法调用提供的显式类型参数。那么 $m$ 通过严格调用适用的，当且仅当以下均真：
    - 对于 $1 \le i \le n$，如果 $e_i$ 与适用性相关，则 $e_i$ 在严格调用上下与 $F_i[R_1=U_1, ..., R_p=U_p]$ 兼容（§5.3）。
    - 对于 $1 \le l \le p$，$U_l <: B_l[R_1=U_1, ..., R_p=U_p]$。
- 如果 $m$ 不是泛型方法，则对于 $1 \le i \le n$，$e_i$ 在严格调用上下与 $F_i$ 兼容（§5.3）或 $e_i$ 与适用性相关。

如果没有找到通过严格调用适用的方法，则进入阶段 2（§15.12.3）。

否则，在通过严格调用适用的方法中选择最特定的（§15.12.2.5）。

> 隐式类型 lambda 表达式或不精确方法引用表达式的含义在解析类型之前足够模糊，包含这些表达式的参数与适用性无关；在重载解析完成之前它们被简单忽略。

### 15.12.3 阶段 2：识别通过宽松调用适用的匹配元个数方法

令 $m$ 为元个数为 $n$ 形式参数类型为 $F_1 ...F_n$ 的潜在适用方法（§15.12.2.1），并令 $e_1, ... e_n$ 为方法调用的实际表达式。那么：

- 如果 $m$ 是泛型方法且方法调用未提供显式参数，则方法的适用性按照 §18.5 的规定推断。
- 如果 $m$ 是泛型方法且方法调用提供了显式参数，令 $R_1, ..., R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_l$ 为 $R_l$ 的边界（$1 \le l \le p$），令 $U_1 ... U_p$ 为方法调用提供的显式类型参数。那么 $m$ 通过宽松调用适用的，当且仅当以下均真：
    - 对于 $1 \le i \le n$，如果 $e_i$ 与适用性相关（§15.12.2.2），则 $e_i$ 在宽松调用上下与 $F_i[R_1=U_1, ..., R_p=U_p]$ 兼容（§5.3）。
    - 对于 $1 \le l \le p$，$U_l <: B_l[R_1=U_1, ..., R_p=U_p]$。
- 如果 $m$ 不是泛型方法，则对于 $1 \le i \le n$，$e_i$ 在宽松调用上下与 $F_i$ 兼容（§5.3）或 $e_i$ 与适用性相关。

如果没有找到通过宽松调用适用的方法，则对方法的搜索继续到阶段 3（§15.12.2.4）。

否则，在所有可通过松散调用（loose invocation）适用的方法中选择最具体的方法 (§15.12.2.5)。

### 15.12.2.4 阶段 3：识别适用于变长参数调用的方法

假设变长方法具有形式参数类型 $F_1, ..., F_{n-1}, F_n[]$，则该方法的第 $i$ 个变长参数参数类型定义为：

- 对于 $i \le n-1$，第 $i$ 个变长参数参数类型为 $F_i$。
- 对于 $i \ge n$，第 $i$ 个变长参数参数类型为 $F_n$。

令 $m$ 为一个具有变长参数的可能适用的方法 (§15.12.2.1)，令 $T_1, ..., T_k$ 为 $m$ 的前 $k$ 个变长参数参数类型，令 $e_1, ..., e_k$ 为方法调用的实际参数表达式：

- 如果 $m$ 是泛型方法且方法调用未提供显式类型参数，则该方法的适用性按照 §18.5.1 的规定推断。

- 如果 $m$ 是泛型方法且方法调用提供了显式类型参数，令 $R_1 ... R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，令 $U_1 ... U_p$ 为方法调用中给显式类型参数。如果满足以下条件，$m$ 通过变长参数调用是*适用的*：

  - 对于 $1 \le i \le k$，如果 $e_i$ 与适用性相关 (§15.12.2.2)，则 $e_i$ 在松散调用上下文中与 $T_i$ 兼容 $[R_i:=U_i, ..., R_p:=U_p]$ (§5.3)。
  - 对于 $1 \le l \le p$，$U_l < B_l$ $[R_l:=U_l, ..., R_p:=U_p]$。

- 如果 $m$ 不是泛型方法，则当对于 $1 \le i \le k$，$e_i$ 在松散调用上下文中与 $T_i$ 兼容 (§5.3) 或 $e_i$ 与适用性无关时，$m$ 通过变长参数调用是*适用的*。

如果未找到适用于变长参数调用的方法，则发生编译时错误。

否则，在所有适用于变长参数调用的方法中选择最具体的方法 (§15.12.2.5)。

### 15.12.2.5 选择最具体的方法

如果多个成员既可访问又适用于提供运行时方法分派的描述符，则必须为运行时方法分派选择一个。Java 语言使用选择*最具体方法*的规则。

非正式的直觉是：如果一个方法处理的任何调用都可以传递给另一个方法而不会产生编译错误，那么这个方法比另一个方法更具体。在显式类型 lambda 表达式参数 (§15.27.1) 或变长参数调用 (§15.12.2.4) 等情况下，允许一定的灵活性来使一个签名适应另一个签名。

对于具有参数表达式 $e_1, \dots, e_k$ 的调用，如果满足任一条件，则适用方法 $m_1$ 比另一个适用方法 $m_2$ 更具体：

- $m_2$ 是泛型的，且根据 §18.5.4 推断 $m_1$ 对于参数表达式 $e_1, \dots, e_k$ 比 $m_2$ 更具体。

- $m_2$ 不是泛型的，且 $m_1$ 和 $m_2$ 适用于严格或松散调用，其中 $m_1$ 具有形式参数类型 $S_1, \dots, S_n$，$m_2$ 具有形式参数类型 $T_1, \dots, T_n$，且对于所有参数 $e_i$，类型 $S_i$ 比 $T_i$ 更具体 ($1 \le i \le n, n=k$)。

- $m_2$ 不是泛型的，且 $m_1$ 和 $m_2$ 适用于变长参数调用，其中前 $k$ 个变长参数为 $S_1, \dots, S_k$，且 $m_2$ 的前 $k$ 个变长参数类型为 $T_1, \dots, T_k$，则对于所有 $i$，类型 $S_i$ 比 $T_i$ 更具体 ($1 \le i \le k$)。此外，如果 $m_2$ 有 $k+1$ 个参数，则 $m_1$ 的第 $k+l'$ 个变长参数类型是 $m_2$ 的第 $k+l'$ 个变长参数类型的子类型。

上述条件是一个方法比另一个方法具体的唯一情况。

对于任何表达式，如果 $s <: \tau$ (§4.10)，则类型 $s$ 比类型 $\tau$ 更具体。

对于表达式 $e$，如果满足所有条件，则函数类型 $s$ 比函数接口 $T$ 更具体：

- $s$ 是 $T$ 的子接口。
- $s$ 是 $T$ 的函数接口，且 $s$ 的返回类型比 $T$ 的返回类型更具体。
- $s$ 是 $T$ 的函数接口，且 $s$ 的返回类型与 $T$ 的返回类型兼容。

对于任何表达式，如果 $s <: \tau$ (§4.10)，则类型 $s$ 比类型 $\tau$ 更具体。

最具体方法的抛出异常类型派自最具体方法的 `throws` 子句，如下：

1. 如果最具体方法是泛型，则首先将 `throws` 子句适配为最具体方法的类型参数 (§8.4.4)。

如果最具体方法不是泛型，但至少有一个最具体方法是泛型，则这些 `throws` 子句首先被擦除。

2. 然后，抛出的异常类型包括每个满足以下约束的 E：

  - E 在其中一个 `throws` 子句中被提及。
  - 对于每个 `throws` 子句，E 是该子句中指定的某些类型的子类型。

这些从一组重载方法派生单个方法类型的规则也用于识别函数式接口的函数类型 (§9.9)。

否则，方法调用具有歧义性，并发生编译时错误。

### 15.12.2.6 方法调用类型

最可访问且适用的方法的调用类型是一个方法类型 (§8.2)，该类型目标向于调用参数的类型、调用的结果（返回类型或 void）以及调用的异常类型。其确定方式如下：

- 如果选定的方法是泛型且方法调用未提供显式类型参数，则调用类型按照 §18.5.2 指定进行推断。

在这种情况下，如果方法调用表达式是一个多值表达式（poly expression），则其与目标类型的兼容性由 §18.5.2.1 确定。

> 在对方法调用表达式的类型类型和调用类型做出最终确定之前，可能会多次发生与目标类型的兼容性测试。例如，嵌套的方法调用可能需要测试更深层的方法调用与不同方法的参数类型的兼容性。

- 如果选定的方法是泛型且方法调用提供了显式类型参数，令 P_i 为方法的类型参数，T_i 为为方法调用提供的显式类型参数 (1 ≤ i ≤ p)。那么：

- 如果为了使方法适用需要进行未检查的转换（unchecked conversion），则调用类型的参数类型通过对方法的类型的参数类型应用替换 $[P_i:=T_i, \dots, P_p:=T_p]$ 获得，且调用类型的返回类型和抛出类型由方法类型的返回类型和抛出类型的擦除给出。

- 如果为了使方法适用不需要进行未检查的转换，则调用类型通过对方法的类型应用替换 $[P_i:=T_i, \dots, P_j:=T_j]$ 获得。

- 如果选定的方法是泛型，则：
  - 如果为了使方法适用需要进行未检查的转换，调用类型的参数类型为方法的类型的参数类型，由方法的返回类型和抛出类型的擦除给出。
  - 否则，如果选定的方法是 `Object` 类的 `getClass` 方法 (§4.3.2)，则返回类型与方法的类型相同，但返回类型为 `Class<? extends T|`，其中 $T$ 是被搜索的类型，由 §15.12.1 确定，且 $|T|$ 表示 $T$ 的擦除 (§4.6)。
  - 否则，调用类型与方法的类型相同。

### 15.12 方法调用表达式 EXPRESSIONS

如果某个方法调用有一个特定的方法声明，则称为该方法调用的 `编译时声明`（compile-time declaration）。

如果方法调用的参数与其目标类型不兼容（根据编译时声明的调用类型派生），则为编译时错误。

如果编译时声明可以通过 var 调用适用，则该方法调用类型的最后一个形式参数类型为 $F_n[]$；如果 $F_n$ 的擦除类型在调用点是不可访问的 (§6.6)，则为编译时错误。

如果编译时声明为 `void`，则该方法调用必须是一个顶层表达式（即表达式语句中的 `Expression`，或者在 `for` 语句的 `ForInit` 或 `ForUpdate` 部分中），否则将发生编译时错误。此类方法调用不产生任何值，且只能在不需要值的情况下使用。

此外，编译时声明是否合适可能取决于方法调用表达式在左括号之前的形式，如下：

- 如果形式为 `MethodName` —— 即仅为 `Identifier` 且编译时声明是实例方法，则：
  - 如果方法调用发生在静态上下文中 (§8.1.3)，则为编译时错误。
  - 否则，令 $c$ 为编译时声明作为其成员的直接外层类。如果方法调用没有直接被 $c$ 或 $c$ 的内部类包围，则发生编译时错误。
- 如果形式为 `TypeName . [Arguments] Identifier`，则编译时声明必须是静态的，否则将发生编译时错误。
- 如果形式为 `ExpressionName . [Arguments] Identifier or Primary [Arguments]`，则编译时声明不能是在接口中声明的静态方法，否则将发生编译时错误。
- 如果形式为 `super . [Arguments] Identifier`，则：
  - 如果编译时声明是抽象的，则为编译时错误。
  - 如果方法调用发生在静态上下文中，则为编译时错误。
- 如果形式为 `TypeName. super . [Arguments] Identifier`，则：
  - 如果编译时声明是抽象的，则为编译时错误。
  - 如果方法调用发生在静态上下文中，则为编译时错误。
  - 如果 $TypeName$ 表示类 $c$，则如果方法调用没有被 $c$ 直接包围，则发生编译时错误。
  - 如果 $TypeName$ 表示接口，令 $\tau$ 为方法调用的类型。如果存在一个不同于编译时声明的方法重写 (§9.4.1）$\tau$ 的直接父类或父接口，则发生编译时错误。（如果祖父接口重写了方法，此规则防止子接口通过将祖父接口添加到其接口列表中来跳过。或者，程序员自由定义额外的接口来暴露所需的行为。）

参数类型和编译时结果确定如下：

- 如果方法调用的编译时声明不是签名策略方法，则：
  - 编译时参数类型为编译时声明的形式参数。
  - 编译时结果为编译时声明的调用类型简体15.12.2.6)。

- 如果方法调用的编译时声明是签名策略方法，则：
  - 编译时参数类型为实际参数表达式的类型。null 字面量 (§3.10.7) 被视为具有 `Void` 类型。
  - 编译时结果确定如下：
    - 如果签名策略方法是 `void` 或其返回类型非 `Object`，则编译时结果为编译时声明的调用类型简体15.12.2.6)。
    - 否则，如果方法调用是一个表达式语句，则编译时结果为 `void`。
    - 否则，如果方法调用是转换表达式简体15.16) 的操作数，则编译时结果为转换表达式类型的擦除简体4.6)。
    - 否则，编译时结果为签名策略方法的返回类型 `Object`。

如果一个方法满足所有条件，则为签名策略方法：

- 它声明在 `java.lang.invoke.MethodHandle` 类或 `java.lang.invoke.VarHandle` 类中。
- 它有一个声明类型为 `Object[]` 的可变长度参数（§8.4.1）。
- 它是原生的（native）。

以下编译时信息将与方法调用关联以供运行时使用：

- 方法名称。
- 方法调用的限定类型（§13.1）。
- 参数数量和编译时参数类型，按顺序排列。
- 调用模式，计算方式如下：

  - 如果编译时声明具有 `static` 修饰符，则调用模式为静态的（static）。
  - 否则，如果方法调用中左括号之前的部分为 `super.Identifier` 或 `TypeName.super.Identifier` 的形式，则调用模式为 `super`。
  - 否则，如果方法调用的限定类型是一个接口，则调用模式为接口（interface）。
  - 否则，调用模式为虚方法（virtual）。

如果编译时声明的调用类型的结果不是 `void`，则方法调用表达式表达式的类型通过对编译时声明调用类型的返回类型应用捕获转换（§5.1.10）获得。

### 15.12.4 方法调用的运行时评估

在运行时，方法调用需要五个步骤。首先，可能会计算一个目标引用。其次，评估参数表达式。第三，检查被调用方法的访问权限性。第四，定位要执行的方法的实际代码。第五，创建一个新的激活帧，在必要时进行同步，并将控制权转移到方法代码。

#### 15.12.4.1 计算目标引用（必要时）

根据方法调用的形式，有六种情况需要考虑：

- 如果形式是 `MethodName`，即一个标识符（Identifier），那么：
  - 如果调用模式是静态的，则没有目标引用。
  - 否则，让 $τ$ 为方法的成员的包含类型声明，并让 $n$ 为整数，使得 $τ$ 是直接包含该方法调用的类的第 $n$ 个词法包含类型声明。目标引用是该类的第 $n$ 个词法包含的实例。

如果该第 $n$ 个词法包含实例不存在，则为编译时错误。

- 如果形式是 `TypeName [TypeArguments] Identifier`，则没有目标引用。

- 如果形式为 `ExpressionName.[TypeArguments] Identifier`，则：
  * 如果调用模式是静态的，则没有目标引用。`ExpressionName` 被评估，但结果被丢弃。
  * 否则，目标引用是 `ExpressionName` 所指示的值。

- 如果形式为涉及 `Primary.[TypeArguments] Identifier`，则：
  * 如果调用模式是静态的，则没有目标引用。`Primary` 表达式被评估，但结果被丢弃。
  * 否则，`Primary` 表达式被评估，其结果用作目标引用。

在任何情况下，如果 `Primary` 表达式的评估异常中止，则任何参数表达式部分都未被评估，且方法调用因相同原因异常中止。

- 如果形式为 `super.[TypeArguments] Identifier`，则目标引用是此的值。
- 如果形式为 `TypeName.super.[TypeArguments] Identifier`，则如果 `TypeName` 表示一个类，则目标引用是 `TypeName.this` 的值；否则，目标引用是此的值。

#### 15.12.4.1-1. 目标引用与静态方法

当由于调用模式是静态而计算并丢弃目标引用时，不会检查该引用是否为 `null`：

```java
```



# 表达式

## 方法调用表达式

### 15.12

```java
class Test1 {

    static void mountain() {
        System.out.println("Monadock");
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

输出为：

```
Mount Monadock
```

在这里 `favorite()` 返回了 `null`，但并没有抛出 `NullPointerException`。

### 示例 15.12.4.1-2. 方法调用期间的评估顺序

作为实例方法调用（§15.12）的一部分，有一个表达式表示要调用的对象。该表达式在方法调用的任何参数表达式部分评估之前，似乎已经完全完全评估。

因此，例如在：

```java
class Test2 {
    public static void main(String[] args) {
        String s = "one";
        if (s.startsWith(s = "two")) {
            System.out.println("oops");
        }
    }
}
```

在 `startsWith` 之前出现的 `s` 先被评估，在参数表达式 `s = "two"` 之前。因此，在局部变量 `s` 指向字符串 "two" 之前，对 "one" 的引用作为目标引用被记住。结果是针对目标参数 "one" 使用参数 "two" 调用了 `startsWith` 方法，因此调用的结果为 `false`，因为字符串 "one" 并不以 "two" 开。因此测试程序没有打印 "oops"。

### 15.12.4.2 评估参数

评估参数列表的过程取决于调用的方法是固定方法还是可变参数方法（§8.4.1）。

如果是在可变参数方法中调用，则 $m$ 必然具有 $n > 0$ 个形式参数。$m$ 的形式参数必然具有某个 $i$ 的 $T[i]$，且 $m$ 必然是用 $k \ge 0$ 个实际参数表达式调用的。

如果用 $k \neq n$ 个实际参数表达式调用 $m$，或者第 $k$ 个参数表达式的类型与 $T[i]$ 不兼容，则参数列表 $(e_1, \dots, e_i, \dots, e_n)$ 被评估为 $(e_1, \dots, e_i, \dots, e_k)$，其中 $|T[i]|$ 表示。前面的前缀是为了处理参数类型与数组类型的交互。如果数组元素类型是可重化的，例如 `List<String>`，则需要小心数组创建（§15.10），因为数组类型是可重化的。Java编译器在此处给出编译警告。Oracle 引用

方法调用表达式

参数表达式（可能已重写）现在被评估以产生参数值。每个参数值精确对应方法的一个形式参数。

参数表达式（如果有）按左到右顺序评估。如果任何参数表达式的评估异常中止，则其右侧部分似乎未被评估，方法调用因相同原因异常中止。评估第 $j$ 个参数表达式的结果是第 $j$ 个参数值，对于 $1 \le j \le n$。然后按照下述继续评估。

### 15.12.4.3 检查类型和方法的访问性

在本节中：

- $D$ 是包含方法调用的类。
- $T$ 是方法调用的限定类型（§13.1）。
- $M$ 是编译时确定的方法（§15.12.3）。

Java语言的实现必须确保在链接时，类型是可访问的。

- 如果 $T$ 与 $D$ 在同一个包中，则 $T$ 是可访问的。
- 如果 $T$ 与 $D$ 不在同一个包中，但它们的包在同一个模块中，且 $T$ 是公共或保护的，则 $T$ 是可访问的。
- 如果 $T$ 与 $D$ 不在同一个包中，且它们的包在不同的模块中，且 $T$ 模块将其包导出给 $D$ 模块，且 $T$ 是公共或保护的，则 $T$ 是可访问的。

> 如果 $T$ 是保护的，它必然是一个嵌套类型，因此在编译时，其访问性受其包含类型访问权限的影响。然而，在链接期间，不受其包含类型访问权限的影响。此外，在链接期间，保护的 $T$ 可以作为公共的 $T$ 被访问。编译时访问控制（§6.6）与运行时访问控制之间的这些差异由于 Java 虚拟机的限制。

实现还必须在链接期间确保方法 $m$ 仍然可以是 $T$ 或 $T$ 的超类型。如果找不到方法 $m$，则发生 `NoSuchMethodError`（它是 `IncompatibleClassChangeError` 的子类）。如果 $m$ 可以找到，令 $c$ 为声明 $m$ 的类型。实现必须确保在调用期间，$c$ 中对 $m$ 的声明对于 $D$ 是可访问：

- 如果 $m$ 是 `public`（公有的），则 $m$ 是可访问的。
- 如果 $m$ 是 `protected`（保护的），则 $m$ 是可访问的，且仅当 (i) $D$ 与 $c$ 在相同的包中，或者 $D$ 是 $c$ 的子类型，并且 (ii) 如果 $m$ 是 `protected` 实例方法，则 $T$ 必须是 $D$ 的子类型或 $D$ 本身。

> 这就是 $T$ 参与对 $m$ 检查的地方，因为 `protected` 实例方法只能通过与调用者类型一致的限定类型来调用。

- 如果 $m$ 具有包访问权限，则 $m$ 是可访问的，且仅当 $D$ 与 $c$ 在相同的包中。
- 如果 $m$ 是 `private`（私有的），则 $m$ 是可访问的，且仅当 $D$ 是 $c$，或者 $D$ 封装了 $c$，或者 $c$ 封装了 $D$，或者 $c$ 和 $D$ 都被第三种类型封装。

如果 $T$ 或 $m$ 有一个不可访问，则会发生 `IllegalAccessError`（§12.3）。

如果调用模式是 `interface`（接口），则实现必须检查目标引用仍然实现了指定的接口。如果目标引用没有实现该接口，则会发生 `IncompatibleClassChangeError`。

### 15.12.4.4 要调用的方法

如上一节（§15.12.4.3）所示：

- 令 $T$ 为方法调用的限定类型 (§13.1)。
- 令 $m$ 为 $T$ 或 $T$ 的超类型中的方法。（注意，在上一节中，$m$ 仅仅是方法的名称；这里它是实际的声明。）
- 令 $c$ 为声明 $m$ 的类或接口。

定位方法的策略取决于调用模式：

- 如果调用模式是 `static`（静态的），则不需要目标引用且不允许重写。类或接口 $c$ 的 $m$ 是要被调用的那个。
- 否则，要调用实例方法且存在目标引用。如果目标引用为 `null`，则在此处抛出 `NullPointerException`。否则，目标引用被认为指向一个目标对象，并将用作被调用方法中关键字 `this` 的值。然后考虑调用模式的其他三种可能性：
  - 如果调用模式是 `super`（超类），则不允许重写。类或接口 $C$ 的方法 $m$ 是要被调用的那个。如果 $m$ 是抽象的，则抛出 `AbstractMethodError`。
  - 否则，如果调用模式是 `virtual`（虚析的），并且 $r$ 和 $m$ 共同指示一个签名多态方法 (§15.12.3)，则目标对象是 `java.lang.invoke.MethodHandle` 或 `java.lang.invoke.VarHandle` 的实例。目标对象封装了状态，该状态将与编译时与方法调用相关联的信息进行匹配。此类匹配的细节见于《Java 虚拟机规范，Java SE 11 版》和 Java SE 平台 API。如果匹配成功，则直接并立即调用 `java.lang.invoke.MethodHandle` 实例引的方法，或者直接并立即访问 `java.lang.invoke.VarHandle` 实例表示的变量，并且不执行 §15.12.4-5 中的用例过程。如果匹配失败，则抛出 `java.lang.invoke.WrongMethodAccessException`。
  - 否则，调用模式是 `interface`（接口）或 `virtual`（虚析的）。

如果类或接口 $C$ 的方法 $m$ 是私有的，那么它就是要调用的方法。

否则，可能会发生重写。使用下文指定的动态方法查找来定位要调用的方法。查找过程从类 $R$ 开始，即目标对象的实际运行时类。

> 注意，对于调用模式 `interface`，$R$ 必然实现了 $r$，或者是 $r$ 或是 $r$ 的子类。如果目标对象是一个数组，则 $R$ 是一个表示数组类型的“类”。

动态方法查找的程序如下。令 $s$ 为要搜索的类，从 $R$ 开始。然后：

1. 如果 $s$ 包含一个重写了来自 $R$ 的类或接口 $c$ 的方法 $m$ 的声明 (§8.4.1)，则该重写方法就是要调用的方法，程序终止。
2. 否则，如果 $s$ 有超类，则使用 $s$ 的直接超类代替 $s$，递归执行此查找程序的第 1 步和第 2 步；要调用的方法（如果有）是此查找程序递归调用的结果。
3. 如果通过上述两个步骤没有找到方法，则在 $s$ 的超接口中搜索合适的方法。

考虑一个候选方法集合，其具有以下属性：(i) 每个方法都声明在 $R$ 的（直接或间接）超接口中；(ii) 每个方法都具有方法调用所需的名称和描述符；(iii) 每个方法都是非静态的且非私有的；(iv) 对于每个方法，如果该方法的声明在 $I$ 中，则没有其他方法满足 (i) 到 (iii)。

### 示例 15.12.4.4 重写与方法调用

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
```

```java
class ColoredPoint extends Point {
    int color;

    void clear() {
        System.out.println("\tColoredPoint clear");
        super.clear();
        color = 0;
    }
}
```

在这里，子类 `ColoredPoint` 扩展了其超类 `Point` 定义的 `clear` 抽象。它通过重写 `clear` 方法来实现，该方法调用其超类的 `clear` 方法，使用 `super.clear()`。

当 `clear` 的调用目标是 `ColoredPoint` 时，就会调用此方法，正如此测试程序的输出所示：

```java
class Test1 {
    public static void main(String[] args) {
        Point p = new Point();
        System.out.println("*p.move(20,20):");
        p.move(20, 20);

        ColoredPoint cp = new ColoredPoint();
        System.out.println("*cp.move(20,20):");
        cp.move(20, 20);

        p = new ColoredPoint();
        System.out.println("*p.move(20,20), p colored:*");
        p.move(20, 20);
    }
}
```

输出为：

- p.move(20,20):
  - Point clear
- cp.move(20,20):
  - ColoredPoint
  - Point clear
- p.move(20,20), p colored:
  - ColoredPoint
  - Point clear

重写有时被称为“晚绑定自引用”：在示例中，这意味着 `Point.move` 句中对 `clear` 的引用（实际上是 `this.clear` 的语法简写）调用的是“晚期”选择的方法（在运行时，根据 `this` 所引用的对象的运行时类），而不是“早期”选择的方法（在编译时，仅对 `this` 的类型选择）。这为程序员提供了一种扩展抽象的强大方式，是面向对象编程中的核心思想。

### 示例 15.12.4.4-2. 使用 super 调用方法

子类的被重写的实例方法可以通过使用关键字 `super` 来访问直接父类类的成员，从而跳过包含该方法调用的类中的任何重写声明。

在访问实例变量时，`super` 等同于 `this` 的转换 (§15.11.2)，但这种等效性对于方法调用并不成立。示例证明了这一点：

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
        System.out.println("s()=\t" + s());
        System.out.println("super.s()=\t" + super.s());
        System.out.println("((T2)this).s()=\t" + ((T2)this).s());
        System.out.println("((T1)this).s()=\t" + ((T1)this).s());
    }
}

class T2 { // Note: Original text had duplicate class name T2 for main class, kept as is.
    public static void main(String[] args) {
        T3 t3 = new T3();
        t3.test();
    }
}
```

```
s()= 3
super.s()= 2
((T2)this).s() = 3
((T1)this).s() = 3
```



类型 `T1` 和 `T2` 并没有改变被调用的方法，因为要调用的实例方法是根据 `this` 所引用的对象的运行时类来选择的。转换不会改变对象的类；它只检查该类是否与指定的类型兼容。

## 15.12.4.5 创建栈帧、同步、传递控制

类 `s` 中的方法 `m` 已被识别为要调用的方法。

现在创建一个新的激活栈帧，其中包含目标引用（如果有）和参数值（如果有），以及为被调用的方法提供局部变量和栈所需的空间，以及实现可能需要的任何其他管理信息（栈指针、程序计数器、对上一个激活栈帧的引用等）。如果没有足够的内存来创建此类激活栈帧，则抛出 `StackOverflowError`。

新创建的激活栈帧变为当前激活栈帧。其效果是将参数值赋值给方法新创建的参数变量，并在存在目标引用时将该目标引用作为 `this` 提供。在将每个参数值赋值给其对应的参数变量之前，它将经过调用转换（§5.3），这包括任何所需的值设置构造函数（§5.1.13）。

如果被调用的方法的类型擦除（§4.6）的签名与该方法调用编译时声明的方法的类型擦除（§15.12.3）不同，那么如果任何参数值都不是该方法调用编译时声明中形式参数类型擦除子类或子接口的实例，则抛出 `ClassCastException`。

如果 `m` 是原生方法，但尚未加载所需的依赖实现的二进制代码，或无法进行动态链接，则抛出 `UnsatisfiedLinkError`。

如果 `m` 不是同步的，控制将传递给要调用的方法 `m` 的体。

如果该方法是同步的，则在传递锁之前必须锁定一个对象。在当前线程获取锁之前，无法继续执行。如果存在目标引用，则必须锁定目标对象；否则，必须锁定类 `s` 的类对象（方法 `m` 的类）。控制传递给要调用的方法 `m` 的体。当方法体执行完成后（无论是正常结束还是异常），对象将自动解锁。锁定和解锁的行为与方法体嵌入在 `synchronized` 语句（§14.19）中完全一致。

## 示例 15.12.4.5-1. 调用方法签名的擦除与编译时签名不同

考虑以下声明：

```java
abstract class C<T> {
    abstract T id(T x);
}

class D extends C<String> {
    String id(String x) { return x; }
}
```

现在，给定一个调用：

```java
C c = new D();
c.id(new Object()); // 以 ClassCastException 失败
```

实际调用的方法的擦除其签名与编译时方法声明 `C.id()` 不同。前者接受一个 `String` 类型的参数，而后者接受一个 `Object` 类型的参数。在方法体执行之前，调用将以 `ClassCastException` 失败。

这种情况可能由于程序产生编译时未检查警告（§4.8, §15.6, §15.9, §18.4.1, §14.8.3, §15.13.2, §15.12.4, §15.27.3）。

实现可以通过创建桥接方法来强制这些语义。在上面的示例中，类 `D` 中将创建以下桥接方法：

```java
Object id(Object x) { return id((String) x); }
```

这是 Java 虚拟机调用上述 `c.id(new Object())` 时实际调用的方法，它将按照要求执行转换并失败。

## 15.13 方法引用表达式

方法引用表达式用于引用方法的调用，而不实际执行调用。方法引用表达式的某些形式还允许将实例创建（§15.9）或数组创建（§15.10）视为方法调用。

```
MethodReference:
    ExpressionName :: [TypeArguments] Identifier
    Primary :: [TypeArguments] Identifier
    ReferenceType :: [TypeArguments] Identifier
    super :: [TypeArguments] Identifier
    TypeName . super :: [TypeArguments] Identifier
    ClassType :: [TypeArguments] new
    ArrayType :: new
```

如果在 `::` 右侧存在 `TypeArguments`，则如果任何类型参数是通配符（§4.5.1），则是编译时错误。

如果方法引用表达式的形式为 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，则如果 `ExpressionName` 或 `Primary` 的类型不是引用类型，则是编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier`，让 $au$ 为紧接包含该方法表达式的类型声明。如果 $au$ 是 `Object` 或 $au$ 是接口，则为编译时错误。

如果方法引用表达式的形式为 `TypeName . super :: [TypeArguments] Identifier`，那么：

- 如果 `TypeName` 表示一个类 $C$，则如果 $C$ 不是当前类的词法闭包类，或者 $C$ 是 `Object`，则是编译时错误。
- 如果 `TypeName` 表示一个接口 $I$，让 $au$ 为紧接包含该方法表达式的类型声明。如果 $au$ 不是 $I$ 的直接父接口，或者存在其他 $au$ 的直接父类或直接父接口 $J$，使得 $J$ 是 $I$ 的子类型，则是编译时错误。
- 如果 `TypeName` 表示一个变量，则是编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName . super :: [TypeArguments] Identifier`，如果该表达式出现在静态上下文中，则是编译时错误。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，那么：

- `ClassType` 必须表示一个可访问的（§6.6）、非抽象的枚举类型，否则发生编译时错误。
- 如果 `ClassType` 表示泛型类型（§4.5），则如果其任何类型参数是通配符，则是编译时错误。
- 如果 `ClassType` 表示原始类型（§4.8），则如果在 `::` 之后存在 `TypeArguments`，则是编译时错误。

如果方法引用表达式的形式为 `ArrayType :: new`，那么 `ArrayType` 必须表示可重构类型（reifiable type §4.7），否则发生编译时错误。

实例方法的目标引用（§15.12.4.1）可以通过使用 `ExpressionName`、`Primary` 或 `super` 的方法引用提供，也可以在方法调用时后提供。新内部类（§15.9.2）的紧接实例由 `this` 的词法闭包实例（§8.1.3）提供。

当一个类型的多个成员方法具有相同名称时，或者一个类有多个构造函数时，将选择适当的方法或构造函数。

根据 §15.13.1 的规定，基于方法引用表达式所指向的函数接口类型。

如果方法或构造函数是泛型的，则适当的类型参数可以被推断出，也可以显式提供。同样，方法引用表达式中提到的泛型类型的类型也可以被显式提供，也可以被推断出。

方法引用表达式始终是多态的（§15.2）。

如果方法引用表达式出现在程序的赋值上下文（§5.2）、调用上下文（§5.3）或转换上下文（§5.5）之外的区域，则为编译时错误。

方法引用表达式的求值产生函数接口类型的实例（§9.8）。这不会导致对应方法的执行；相反，执行可能会在稍后的时间通过调用函数接口的适当方法时发生。

以下是一些方法引用表达式，首先是不带目标引用的，然后带有目标引用的：

```java
String::length                        // 实例方法
System::currentTimeMillis             // 方法
List<String>::size                    // 泛型的显式类型参数
List::size                            // 泛型的推断类型参数
int[]::clone
T::tvarMember
System.out.println(
    "abc"::length
    foo[x]::bar
    (test ? list.replaceAll(String::trim) : list) : iterator
    super::toString
)
```

这里是更多方法引用表达式：

```java
String::valueOf                       // 需要重载解析
Arrays::sort                          // 从上下文推断的类型参数
Arrays::<String>sort                  // 显式类型参数
```

以下是一些表示对象或数组延迟创建的方法引用表达式：

```java
ArrayList<String>::new                // 参数化类型的构造函数
ArrayList::new                        // 推断的类型参数
Foo::<Integer>new                     // 用于泛型类，显式类型参数
Bar<String>::<Integer>new             // 泛型类，泛型构造函数
Outer::new                            // 内部类构造函数
int[]::new                            // 数组创建
```



无法指定特定的签名进行匹配，例如 `Arrays::sort(int[])`。相反，函数接口提供的参数类型将用作输出解析算法（§15.12.2）的输入。这应该满足绝大多数用例；当需要更精确的控制时，可以使用 lambda 表达式。

在分隔符之前的类名中使用泛型语法 `:size`（`List<String>:::size`）会引起区分 `<` 类型括号和 `<` 小于运算符的解析问题。在理论上，这并不比在 `case` 表达式中允许类型参数糟糕；然而，区别在于 `case` 只在遇到 `u :` 时出现；加上方法引用表达式后，`of` 表达式可能是一个参数化类型。

# 15.13 方法引用的编译时声明

方法引用表达式的编译时声明是该表达式所指的方法。在特殊情况下，编译时声明实际上并不，而是一个表示类实例创建或数组创建的符号方法。编译时声明的选择取决于表达式所指向的函数类型，就像方法调用的编译时声明取决于调用的参数一样（§15.12.3）。

编译时声明的搜索镜像了 §15.12.1 和 §15.12.2 中方法调用的过程，如下：

- 首先，确定要搜索的类型：
  - 如果方法引用表达式的形式为 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，则要搜索的类型是前面的 `::` 标记的类型。
  - 如果方法引用表达式的形式为 `referenceType :: [TypeArguments] Identifier`，则要搜索的类型是应用于 `ReferenceType` 的捕获转换（§5.1.10）的结果。
  - 如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier`，则要搜索的类型是包含方法引用的类的父类类型。
  - 如果方法引用表达式的形式为 `TypeName super :: [TypeArguments] Identifier`，那么如果 `TypeName` 表示一个类，则要搜索的类型是该名类的父类；否则，`TypeName` 表示一个接口，则包含方法引用的类或接口对应的接口类型是要搜索的类型。
- 如果是其他形式（涉及 `new()`），则所引用的方法是虚拟的，没有类型可搜索。

- 第二，给定一个具有 $n$ 个参数的目标函数类型，识别出一组可能适用的方法：

  - 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，则可能适用的方法包括：
    - 要搜索类型的成员方法对于命名为 `Identifier`、具有元数 $n$、具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类中的方法调用可能是适用的（§15.12.2.1）；外加
    - 要搜索类型的成员方法对于命名为 `Identifier`、具有元数 $n-1$、具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类中的方法调用可能是适用的。
    考虑了两种不同的元数 $n$ 和 $n-1$，以考虑到这种形式可能指向静态方法或实例方法。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new()`，则可能适用的方法是对应于 `ClassType` 构造函数的虚拟方法。如果 `ClassType` 是原始类型，则可能适用的方法是 §15.9 中为类实例指定的虚拟方法。在这些候选中，可能适用的方法是对于命名为 `Identifier`、具有元数 $n$、具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类中的方法调用可能是适用的。

如果方法引用表达式的形式为 `ArrayType :: new`，则考虑一个方法。它具有类型为 `int` 的单个参数，返回 `ArrayType`，且没有 `throws` 子句。对于所有其他形式，可能适用的方法是对于命名为 `Identifier`、元数为 $n$、具有类型参数 `TypeArguments` 且与方法引用出现在同一个类中的方法调用可能是适用的成员方法。

- 最后，如果没有可能适用的方法，则没有编译时声明。

否则，给定一个具有 $P_i \dots P_n$ 的目标函数类型和一组可能适用的方法，编译时声明的选择如下：

- 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，则执行两次最特定方法的搜索。每次搜索均按照 §15.12.2 到 §15.12.5 的规定进行，分类如下。每次搜索产生一个方法集合，并可能指定该集合中的最特定方法。在 §15.12.4 规定的情况下，适用方法集合为空。在 §15.12.5 规定的情况下，没有最特定方法。

在第一次搜索中，方法引用被处理为一个具有类型为 $P_i \dots P_n$ 参数表达式的调用，类型参数（如果有）由方法引用表达式给出。

在第二次搜索中，如果 $P_i \dots P_n$ 不空且 $P_i$ 是 `ReferenceType` 的子类型，则方法引用表达式被处理为一个具有类型为 $P_i \dots P_n$ 参数表达式的调用。如果 `ReferenceType` 是原始类型，并且存在 $P_i$ 的子类型的泛化类型 $G<\dots>$，则要搜索的类型是应用于 $G<\dots>$ 的捕获转换（§5.1.10）的结果；否则，类型与第一次搜索的类型相同。类型参数（如果有）由方法引用表达式给出。

如果第一次搜索的最特定方法是静态的，且第二次搜索产生的适用方法不包含非静态方法，则编译时声明为第一次搜索的最特定方法。

否则，如果第一次搜索产生的适用方法不包含静态方法，且第二次搜索产生了最特定的，则编译时声明为第二次搜索的最特定方法。

如果方法是非静态的，则编译时声明为第二次搜索中性特定的方法。

否则，则没有编译时声明。

- 对于所有其他形式的方法引用表达式，都将执行一次针对最具体的适用方法的搜索。搜索方式如 $15.12.2.2$ 至 $15212.2.5$ 所示，并附带下文说明。

方法引用被视为一个具有类型为 $P_1, \dots, P_n$ 的参数表达式的调用；参数（如果有）由方法引用表达式提供。

如果搜索结果如 $15.12.2.2$ 至 $15212.2.5$ 所示出现错误，或者最具体的适用方法是静态的，则没有编译时声明。

否则，编译时声明为最具体的适用方法。

如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，且编译时声明是静态的，并且 `ReferenceType` 不是简单名称或限定名称 ($6.2$)，则为编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName. super :: [TypeArguments] Identifier`，且编译时声明是抽象的，则为编译时错误。

如果方法引用表达式的形式为 `TypeName. super :: [TypeArguments] Identifier`，且 `TypeName` 表示一个方法、一个接口，或紧邻包含该方法引用表达式的类型的直接父类或直接接口中覆盖了编译时声明的内容，则为编译时错误。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，且根据 $15.9.2$ 确定 `ClassType` 的封闭实例时会发生错误（将方法引用表达式视为未限定的实例创建），则为编译时错误。

形式为 `ReferenceType :: [TypeArguments] Identifier` 的方法引用表达式有不同的解释方式。如果 `Identifier` 指向实例方法，那么 lambda 表达式与 `Identifier` 指向静态方法相比多出一个参数。`ReferenceType` 可能具有这两种适用方法，因此上述搜索算法会分别识别它们，因为每种情况都有不同的参数类型。

## 15.13 方法引用表达式

### 表达式

一个歧义示例是：

```java
interface Fun<T,R> { R apply(T arg); }

class C {

    int size() { return 0; }

    static int size(Object arg) { return 0; }

    void test() {

        Fun<C, Integer> f1 = C::size;

        // Error：实例方法 size()

        // 或静态方法 size(Object)?

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

    }

}
```

搜索足够智能，忽略所有方法（两者）均为以下形式时的歧义：

```java
interface Fun<T,R> { R apply(T arg); }

class C {

    int size() { return 0; }

    static int size(Object arg) { return 0; }

    int size(C arg) { return 0; }

}
```

为了方便起见，当使用方法引用的名称指向实例方法时（其中接收者变为第一个参数），目标类型的使用类似于 `Pair<String, Integer>::first`。

### 15.13.2 方法引用的类型

如果 $\tau$ 是函数接口 ($9.8$) 且表达式与函数类型兼容，则方法引用表达式在赋值上下文、调用上下文或转换上下文中目标类型 $\tau$ 兼容。

基础目标类型由 $\tau$ 导出如下：

- 如果 $\tau$ 是通配符参数化的函数接口类型，则基础目标类型为其非通配符参数化 ($9.9$)。
- 否则，基础目标类型为 $\tau$。

如果满足以下两个条件，则方法引用表达式与函数类型*兼容*：

- 函数类型识别了对应于引用的单一编译时声明。
- 满足：
    - 函数类型的结果为 *void*。
    - 函数类型的结果为 $R$，且捕获转换 ($5.11.10$) 到编译时声明的调用类型 ($15.12.2.6$) 返回类型的结果为 $R'$（其中 $R$ 是可能用于推断 $R'$ 的目标类型），且 $R$ 和 $R'$ 都不是 void，并且 $R'$ 在赋值上下文中 $R$ 兼容。

# 表达式

## 方法引用表达式 15.13

驱动兼容性定义的关键因素是：当且仅当 lambda 表达式 `(x, y, z) -> exp<T1, T2>-method(x, y, z)` 兼容时，方法引用也是兼容的。（这是一种非正式描述，且存在某些问题使得难以或无法通过此类重写来正式定义语义。）

这些兼容性规则为从一个函数式接口转换为其他接口提供了方便的机制：

```java
Task t = () -> System.out.println("hi");

Runnable r = t::invoke;
```

实现可能会经过优化，使得由 lambda 派生的对象被传递并转换为各种类型，这不会在核心 lambda 表达式周围产生许多层级的适配逻辑。

与 lambda 表达式不同，方法引用可以与泛型函数类型（即带有参数的函数类型）同构。这是因为 lambda 表达式需要能够声明类型参数，而目前没有语法支持这一点；但对于方法引用，不需要这样的声明。例如，以下程序是：

```java
interface ListFactory {

  <T> List<T> make();

}

ListFactory lf = ArrayList::new;

List<String> ls = lf.make();

List<Number> ln = lf.make();
```

## 15.13 方法引用的运行时求值

此时，方法引用表达式的求值与类实例创建表达式的求值相似，因为正常完成会产生对对象的引用。方法引用表达式的求值与方法本身的调用是不同的。

首先，如果方法引用表达式以 `ExpressionName` 或 `Primary` 开头，则对该子表达式进行求值。如果子表达式求值为 `null`，则抛出 `NullPointerException`，且方法引用表达式异常终止。如果子表达式由于相同原因而异常终止。

接下来，要么分配并初始化一个具有以下属性的类的新实例，要么引用一个具有以下属性的类的现有实例。如果需要创建新实例但没有足够的空间来分配对象，则方法引用表达式的求值通过抛出 `OutMemoryError` 异常终止。

编译时声明是方法引用表达式的编译时声明。方法调用表达式的运行时求值见 §15.12.4.3、§15.12.4.4 和 §15.12.4.5，其中：

- 调用方法根据 §15.12.3 的规定从编译时声明中派生。
- 如果编译时声明是实例方法，则目标引用是调用方法的第一个形式化参数。否则，没有目标引用。
- 如果编译时声明是实例方法，则方法调用表达式的参数（如果有）是调用方法的第二个及后续的形式化参数。否则，方法调用表达式的参数是调用方法的形式化参数。
- 如果形式为 `super::[TypeArguments] Identifier` 或 `TypeName.super::[TypeArguments] Identifier`，则调用方法的体对于方法引用表达式的编译时声明具有方法调用表达式的效果。方法调用表达式的运行时求值见 §15.12.4.3 和 §15.12.4.5，其中：

- 调用方法为 `super`。
- 如果方法引用表达式以命名某个类的 `TypeName` 开头，则目标引用是方法引用求值点 `TypeName.this` 的值。否则，目标引用是方法引用求值点 `this` 的值。
- 方法调用表达式的参数是调用方法的形式化参数。
- 如果形式为 `ClassType::[TypeArguments] new`，则调用方法的体具有形式 `new [TypeArguments] ClassType(A1, ..., An)` 的类创建表达式的效果，其中参数 `A1, ..., An` 是调用方法的形式化参数，且：

- 新对象的闭包实例（如果有）派生自方法引用表达式的位置，见 §15.9.2 的规定。
- 要调用的构造函数是与方法引用的编译时声明对应的构造函数 (§15.13.1)。
- 如果形式为 `Type[]^k::new(k ≥ 1)`，则调用方法的体具有形式为 `new Type[size]` 的数组创建表达式的效果，其中 `size` 是调用方法的单一参数。（符号 `[]^k` 表示 k 个括号对序列。）

如果该体的结果具有方法调用表达式的效果，则方法调用的编译时参数类型和编译时结果将按照 §15.12.3 的规定进行确定。为了确定编译时结果，如果调用方法的结果为 `void`，则该方法调用为表达式语句；如果调用方法的结果非 `void`，则为返回语句的表达式。

方法引用表达式求值的时机比 lambda 表达式（§15.27.4）更复杂。当方法引用表达式在 `::` 分隔符之前有一个表达式（而非类型）时，该子表达式会被立即求值。求值结果被存储，直到相应函数式接口的方法被调用；此时，结果被用作调用的目标引用。这意味着 `::` 分隔符之前的表达式仅在程序遇到方法引用表达式时才被求值，且在函数类型上的后续调用中不会重新求值。

将此处的处理与方法调用期间的处理进行对比是非常有趣的。在求值方法引用表达式时，修饰调用的 `Primary` 可能求值为 `null` 但会抛出 `NullPointerException`。这发生在调用的方法是静态方法时（尽管根据 §15.13.1），因此方法引用表达式的求值更为简单——空的 `Primary` 总是抛出 `NullPointerException`。

## 15.14 后缀表达式

后缀表达式包括 `++` 和 `--` 运算符的使用。名称不是原始表达式（§15.8），但为了避免某些歧义，在语法中被单独处理。它们仅在后缀表达式的优先级层级是互换的。

PostfixExpression:
- Primary
- ExpressionName
- PostIncrementExpression
- PostDecrementExpression

### 15.14.1 表达式名称

求值的规则见 §6.5.6。

### 15.14.2 后缀增 运算符 ++

后缀表达式后跟 `++` 是后缀增表达式。

```
PostfixIncrementExpression:
PostfixExpression ++
```

后缀表达式的结果必须是可转换为数值类型（§5.1.8）的变量，否则发生编译错误。

后缀增表达式的类型是变量的类型。后缀增表达式的结果不是变量，而是值。

在运行时，如果操作表达式的求值异常终止，则后缀增表达式因相同原因异常终止且不发生递增。否则，将 1 加到变量的值上并将和存回变量中。在相加之前，对 1 和变量的值执行二值数值提升（§5.6.2）。如有必要，和通过窄原始类型转换（§5.1.3）缩小并/或通过装箱转换（§5.1.7）转换为变量类型。后缀增表达式的值是存储新值之前变量的值。

> 注意，上述的二值数值提升可能包括拆箱转换（§5.1.8）和赋值转换（§5.1.13）。如有必要，在存入变量之前对和应用赋值转换。

声明为 `final` 的变量不能递增，因为当访问此类 `final` 变量作为表达式时，结果是值而非变量。因此，它不能作为后缀增运算符的操作数。

### 15.14.3 后缀减 运算符 --

后缀表达式后跟 `--` 是后缀减表达式。

```
PostDecrementExpression:
PostfixExpression --
```



# 15.15 一元运算符

表达式

后缀表达式的结果必须是一个可以转换为数值类型（§5.1.8）的类型的变量，否则将发生编译时错误。

后缀递减表达式的类型是该变量的类型。后缀递减表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的求值异常完成，则后缀递减表达式因相同的原因异常完成，且不发生递减。否则，从变量的值中减去值 1，并将差值存回变量中。在执行减法之前，会对值 1 和变量的值进行二元数值提升（§5.6.2）。如有必要，在存储之前，差值通过收窄原始转换（§5.1.3）进行缩小，并/或转换为变量类型的类型的装箱转换（§5.1.7）。后缀递减表达式的值是在存储新值之前变量的值。

> 注意，上述的二元数值提升可能包括拆箱转换（§5.1.8）和值转换（§5.1.13）。如有必要，在将差值存储到变量之前，对其应用值转换。

声明为 `final` 的变量在用作表达式使用时不能被递减，因为其结果是一个值，而不是变量。因此，它不能作为后缀递减运算符的操作数。

# 15.15 一元运算符

运算符 `+`、`-`、`++`、`--`、`~`、`!` 以及转换运算符（§15.16）被称为一元运算符。

+ UnaryExpression:
  - PreIncrementExpression
  - PreDecrementExpression
  - + UnaryExpression
  - - UnaryExpression
  - UnaryExpressionNotPlusMinus

+ PreIncrementExpression:
  - ++ UnaryExpression

+ PreDecrementExpression:
  - -- UnaryExpression

+ UnaryExpressionNotPlusMinus:
  - PostfixExpression
  - ~ UnaryExpression
  - ! UnaryExpression
  - CastExpression

为了方便起见，这里显示来自 §15.16 的产生式：

```
CastExpression:
( PrimitiveType ) UnaryExpression
( ReferenceType [AdditionalBound] ) UnaryExpressionNotPlusMinus
( ReferenceType [AdditionalBound] ) LambdaExpression
```

带有一元运算符的表达式从右向左处理，因此 `--x` 等同于 `--(-x)`。

这部分语法包含了一些小技巧，以避免两种潜在的语法歧义。

第一个潜在歧义出现在像 `(p)+q` 这样的表达式中，对于 C 或 C++ 程序员来说，它看起来像是对 `q` 执行一元 `+` 操作后的类型转换，或者是两个数量 `p` 和 `q` 之间的二元运算。在 C 和 C++ 中，解析器在解析时通过执行有限的语义分析来处理这种情况，从而知道 `p` 是类型名还是变量名。

Java 采取了不同的方法。运算符的结果必须是数值型的，且转换中涉及的所有类型名都是已知关键字。因此，如果 `p` 是命名基本数据类型的关键字，那么 `(p)+q` 只能解释为一元表达式。然而，如果 `p` 不是命名基本数据类型的关键字，那么 `(p)+q` 只能解释为二元运算。类似的说明也适用于该运算符。语法 `UnaryExpression` 包含了所有运算符，但终结符 `UnaryExpressionNotPlusMinus` 排除了所有可能作为二元运算符的一元运算符（在 Java 中为 `+` 和 `-`）。

第二个潜在歧义是表达式 `(p)++`，对于 C 或 C++ 程序员来说，它看起来像是圆括号表达式的后缀递增，或者是转换的开始，例如在 `(p)++;q` 中。与之前一样，C 和 C++ 的解析器知道 `p` 是类型名还是变量名。但仅使用单标记前瞻且在解析期间不进行语义分析的解析器，将能够在 `++` 是前瞻符号时，判断 `p` 应该被视为原始表达式，还是留待后续作为 `CastExpression` 的一部分考虑。

在 Java 中，`++` 运算符的结果必须是数值型的，且转换中涉及的所有类型都是已知关键字。因此，如果 `p` 是命名基本数据类型的关键字，那么 `(p)++` 只能解释为前置递增表达式的转换，并且应该有一个运算符使用 `q`，因为 `q` 只能解释为前置 `++`。然而，如果 `p` 不是命名基本数据类型的关键字，那么 `(p)++` 只能解释为 `p` 的后缀递增。类似的说明也适用于 `--` 运算符。因此，终结符 `UnaryExpressionNotPlusMinus` 排除了前置运算符 `++` 和 `--` 的使用。

# 15.15.1 前置递增运算符 ++

由 `++` 运算符引导的一元表达式是前置递增表达式。

一元表达式的结果必须是一个可以转换为数值类型（§5.1.8）的类型的变量，否则将发生编译时错误。

前置递增表达式的类型是该变量的类型。前置递增表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的求值异常完成，则前置递增表达式因相同的原因异常完成，且不发生递增。否则，变量的值加上值 1，并将和存回变量中。在执行加法之前，会对值 1 和变量的值进行二元数值提升（§5.6.2）。如有必要，在存储之前，和通过收窄原始转换（§5.1.3）进行缩小，并/或转换为变量类型的装箱转换（§5.1.7）。前置递增表达式的值是在存储新值之后变量的值（注：此处原文可能有误，应为递增表达式）。

> 注意，上述的二元数值提升可能包括拆箱转换（§5.1.8）和值转换（§5.1.13）。如有必要，在将和存储到变量之前，对其应用值转换。

声明为 `final` 的变量在用作表达式使用时不能被递增，因为其结果是一个值，而不是变量。因此，它不能作为前置递增运算符的操作数。

# 15.15.2 前置递减运算符 --

由 `--` 运算符引导的一元表达式是前置递减表达式。

一元表达式的结果必须是一个可以转换为数值类型（§5.1.8）的类型的变量，否则将发生编译时错误。

前置递减表达式的类型是该变量的类型。前置递减表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的求值异常完成，则前置递减表达式因相同的原因异常完成，且不发生递减。否则，从变量的值中减去值 1，并将差值存回变量中。在执行减法之前，会对值 1 和变量的值进行二元数值提升（§5.6.2）。如有必要，在存储之前，差值通过收窄原始转换（§5.1.3）进行缩小，并/或转换为变量类型的装箱转换（§5.1.7）。前置递减表达式的值是在存储新值之后变量的值（注：此处原文可能有误，应为递减表达式）。

> 注意，上述的二元数值提升可能包括拆箱转换（§5.1.8）和值转换（§5.1.13）。如有必要，在将差值存储到变量之前，对其应用值转换。

声明为 `final` 的变量在用作表达式使用时不能被递减，因为其结果是一个值，而不是变量。因此，它不能作为前置递减运算符的操作数。

# 15.15.3 一元加运算符 +

一元加运算符的操作数表达式的类型必须是可以转换为数值类型（§5.1.8）的类型，否则将发生编译时错误。

会对操作数执行一元数值提升（§5.6.1）。

一元加表达式的类型是操作数的提升类型。一元加表达式的结果不是变量，而是一个值，即使操作数表达式的结果是一个变量。

在运行时，一元加表达式的值是操作数的提升值。

# 15.15.4 一元减运算符 -

一元减运算符的操作数表达式的类型必须是可以转换为数值类型（§5.1.8）的类型，否则将发生编译时错误。

会对操作数执行一元数值提升（§5.6.1）。

一元减表达式的类型是操作数的提升类型。

注意，一元数值提升会执行值转换（§5.1.13）。无论提升后的值来自哪个值集，都会执行一元取反操作，结果源自同一个值集。该结果将经过进一步的值转换。

在运行时，一元减表达式的值是从零开始算术取反。Java 编程语言使用补码表示整数，且补码值的范围是非对称的，因此最大负数 `int` 或 `long` 的取反结果仍为该最大负数。溢出在此情况下会发生，但不会抛出异常。对于所有整数值 `x`，`-x` 等于 `(~x)+1`。

对于浮点值，取反不等同于减零，因为如果 `x` 是 +0.0，那么 `0.-x` 是 +0.0，但 `-x` 是 -0.0。一元负号仅反转浮点数的符号。值得关注的特殊情况包括：

- 如果操作数是 NaN，则结果为 NaN。（记住 NaN 没有符号（§4.2.3））。
- 如果操作数是无穷大，结果为相反符号的无穷大。
- 如果操作数是零，结果为相反符号的零。

# 15.15.5 位取反运算符 ~

一元运算符 `~` 的操作数表达式的类型必须是可转换为原始整数类型（§5.1.8）的，否则会发生编译错误。
对操作数进行一元数值提升（§5.6.1）。一元位取反表达式的类型是操作数提升后的类型。

在运行时，一元位取反表达式的值是操作数提升后值的位取反。在所有情况下，`~x` 等于 `(-x)-1`。

# 15.15.6 逻辑取反运算符 !

一元运算符 `!` 的操作数表达式的类型必须是布尔 `boolean`，否则会发生编译错误。
一元逻辑取反表达式的类型为 `boolean`。

在运行时，必要时操作数会拆箱转换（§5.1.8）。如果（可能转换过的）操作数值为 false，则一元逻辑取反表达式的值为 true；如果（可能转换过的）操作数值为 true，则为 false。

# 15.16 转换表达式

强制转换表达式在运行时将一种数值类型的值转换为另一种数值类型的相似值；或者在编译时确认表达式的类型为布尔；或者在运行时检查引用是否指向一个类与指定的引用类型或引用类型列表兼容的对象，该对象体现了原始类型的值。

### CastExpression:

- ( PrimitiveType ) UnaryExpression
- ( ReferenceType {AdditionalBound} ) UnaryExpressionNotPlusMinus
- ( ReferenceType {AdditionalBound} ) LambdaExpression

为了方便起见，这里显示了来自 §4.4 的产生式：

AdditionalBound:
& InterfaceType

括号以及它们包含的类型或类型列表有时被称为转换运算符。

如果转换运算符包含类型列表，即由一个 `ReferenceType` 后面跟着一个或多个 `AdditionalBound` 项，则必须满足以下所有条件，否则会发生编译错误：

- `ReferenceType` 必须表示类类型或接口类型。
- 所有列出的类型的擦除（§4.6）必须是互不相同的。
- 没有两个列出的类型是同一个泛型接口不同参数化的子类型。

由转换表达式引入的转换上下文（§5.5）的目标类型，要么是转换运算符中出现的 `PrimitiveType` 或 `ReferenceType`（如果后面没有跟 `AdditionalBound` 句），或者是转换运算符中由 `ReferenceType` 和 `AdditionalBound` 句表示的交集类型。

转换表达式的类型是对该目标类型应用捕获转换（§5.1.10）的结果。

> 强制转换可用于为 lambda 表达式或方法引用表达式“标记”一个特定的目标类型。为了提供适当的灵活性，目标类型可以是表示交集类型的类型列表，只要该交集诱导了一个函数接口（§9.8）。

如果求值操作数表达式的结果是 `float` 类型或 `double` 类型值（§4.2.3）的变量，则转换表达式不是变量，而是一个值。

转换运算符对值集没有影响。因此，在非 FP-STRICT（§15.4）的表达式中转换为 `float` 不一定会导致其值转换为 `float` 值集的元素，且在非 FP-STRICT 的表达式中转换为 `double` 也不一定会导致其值转换为 `double` 值集的元素。

如果操作数的编译时类型无法通过转换转换（§5.5）转换为转换运算符指定的目标类型，则会发生编译错误。

否则，在运行时，操作数值通过转换转换（必要）转换为转换运算符指定的目标类型。

如果在运行时发现转换是不允许的，则抛出 `ClassCastException`。

- 某些结果在编译时产生错误。某些转换可以在编译时证明在运行时始终是正确的。例如，将类类型的值转换为其子类的类型始终是正确的；这种转换在运行时不需要特殊操作。最后，某些转换在编译时无法证明是正确的或始终是错误的。此类转换需要在运行时进行测试。详见 §5.5。

# 15.17 乘法运算符

运算符 `*`、`/` 和 `%` 称为乘法运算符。

```
MultiplicativeExpression:
UnaryExpression
MultiplicativeExpression * UnaryExpression
MultiplicativeExpression / UnaryExpression
MultiplicativeExpression % UnaryExpression
```

乘法运算符具有相同的优先级，并且在语法上是左结合的（从左到右分组）。

乘法运算符每个操作数的类型必须是可转换为原始数值类型（§5.1.8）的类型，否则会发生编译错误。

## 15.17.1 乘法运算符 *

二元运算符 `*` 执行乘法，产生其操作数的积。左侧操作数是乘数，右侧操作数是被乘数。（注：提供的 OCR 文本此处存在重复/噪声，已根据逻辑流处理）。

## 15.17.2 除法运算符 /

二元运算符 `/` 执行除法，产生其操作数的商。左侧操作数是被除数，右侧操作数是除数。

对于经过二元数值提升（§5.6.2）后为整数的操作数，整数除法向零舍入；即商的绝对值是使得 `|d * q| <= |n|` 的最大整数 `q`，其中 `n` 是被除数，`d` 是除数。商为零当且仅当 `|n| < |d|`。商为正当且仅当 `|n| >= |d|` 且 `n` 和 `d` 符号相同；商为负当且仅当 `|n| >= |d|` 且 `n` 和 `d` 符号相反。

如果整数除法运算符的除数为 0，则抛出 `ArithmeticException`。

如果整数除法的被除数是该类型中绝对值最大的负整数，且除数为 -1，则会发生整数溢出，结果等于被除数。尽管发生溢出，但不会抛出异常。

对于经过二元数值提升（§5.6.2）后为浮点数的操作数，浮点除法按 IEEE 754 算术规则进行：

- 如果任一操作数为 NaN，结果为 NaN。
- 如果结果不是 NaN，结果的符号为正当且仅当操作数符号相同，为负当且仅当操作数符号相反。
- 如果被除数为无穷大且除数为有限值，结果为带符号的无穷大。
- 如果被除数为有限值且除数为零，结果为带符号的无穷大。
- 如果被除数为零且除数为有限非零值，结果为零。
- 如果被除数为无穷大且除数为无穷大，结果为 NaN。
- 如果被除数为有限值且除数为无穷大，结果为零。

将非零有限值除以零将得到一个带符号的无穷大。该符号由上述规则决定。

在其他情况下，即既不涉及无穷大也不涉及 NaN，将计算精确的数学商。然后选择一个浮点数值：

- 如果除法表达式是 FP 严格的（§15.4）：
    - 如果除法表达式的类型为 `float`，则选择 float 值集。
    - 如果除法表达式的类型为 `double`，则必须选择 double 值集。
- 如果除法表达式不是 FP 严格的：
    - 如果除法表达式的类型为 `float`，则根据实现的意愿，选择 float 值集或 float 扩展指数值集。
    - 如果除法表达式的类型为 `double`，则根据实现的意愿，选择 double 值集或 double 扩展指数值集。

接下来，必须从所选的值集中选择一个值来表示商。

如果商的绝对值无法表示，我们称该操作溢出；结果将为具有适当符号的无穷大。

否则，使用 IEEE 754 最近舍入模式将商舍入到所选值集中的最近值。Java 语言要求支持 IEEE 754 定义的渐进下溢（§4.2.4）。

尽管可能会溢出、下溢、除零或信息丢失，但求浮点除法运算符 `/` 永远不会抛出运行时异常。

## 15.17.3 取余运算符 %

二元运算符 `%` 被认为产生其操作数在隐含除法的余数；左侧操作数是被除数，右侧操作数为除数。

在 C 和 C++ 中，取余运算符只接受整数操作数，但在 Java 语言中，它也接受浮点操作数。

对于经过二元数值提升（§5.6.2）后为整数的操作数，取余操作产生的结果使得 `(a/b)*b+(a%b)` 等于 `a`。

即使在除数为该类型中绝对值最大的负整数，且除数为 -1 的特殊情况下（余数为 0），该等式依然成立。

根据此规则可知，取余操作的结果只有在除数为负数时才为负数，在除数为正数时则为正数。此外，结果的绝对值始终小于除数的绝对值。

如果整数取余运算符的除数为 0，则抛出 `ArithmeticException`。

### Example 15.17.3-1. 整数取余运算符

```java
class Test1 {
    public static void main(String[] args) {
        int a = 5%-3; // 2
        int b = 5/3; // 1
        System.out.println("5%-3 produces " + a + 
          " (note that 5/3 produces " + b + ")");
    }
}
```

该程序产生如下输出：

```
5%-3 produces 2 (note that 5/3 produces 1)
5%-(-3) produces 2 (note that 5/-3 produces -1)
-5%3 produces -2 (note that -5/3 produces -1)
-5%-(-3) produces -2 (note that -5/(-3) produces 1)
```

由 `%` 运算符计算的浮点取余结果与 IEEE 754 定义的取余操作结果不同。IEEE 754 取余操作计算的是舍入除法的余数，而不是截断除法，因此其行为与通常的整数取余运算符不同。相反，Java 语言定义的浮点操作 `%` 行为类似于整数取余；这可以与 C 库函数 `fmod` 进行比较。IEEE 754 取余操作可以通过库例程 `Math.IEEEremainder` 计算。

浮点取余的结果由 IEEE 754 算术规则决定：

- 如果任一操作数为 NaN，结果为 NaN。
- 如果结果不是 NaN，结果的符号等于被除数的符号。
- 如果被除数为无穷大或除数为零（或两者都是），结果为 NaN。
- 如果被除数为有限值且除数为无穷大，结果等于被除数。
- 如果被除数为零且除数为有限值，结果等于被除数。
- 在其他情况下（即不涉及无穷大、零或 NaN），除数 `d` 除以 `n` 得到的浮点余数 `r` 由数学关系 `r = n - (d · q)` 定义，其中 `q` 是一个整数，当 `n/d` 为负时 `q` 为负，当 `n/d` 为正时 `q` 为正，其绝对值在不超过 `n` 和 `d` 的真实数学商绝对值的情况下尽可能大。

求浮点取余运算符 `%` 永远不会抛出运行时异常，即使右侧操作数为零也不会溢出、下溢或精度丢失。

### Example 15.17.3-2. 浮点取余

```java
class Test2 {
    public static void main(String[] args) {
        double a = 5.0%-3.0;
        double b = 5.0/3.0;
    }
}
```



```java
System.out.println("%5.0%%-3.0 produces " + a + 
      " (note that 5.0/3.0 produces " + b + ")");
}
}
```

（注：OCR文本在第二个示例中存在一些乱码，我根据标准的 Java 行为和文档的上下文进行了重构。）

# 加法运算符

```java
public static void main(String[] args) {
    printSong("slime", 3);
}
```

`printSong` 方法将打印一首童歌的版本。内容的常用值包括 "pop" 和 "beer"：`n` 的常用值是 100。以下是运行程序后得到的输出：

3 bottles of slime on the wall,
3 bottles of slime;
You take one down and pass it around:
2 bottles of slime on the wall!

2 bottles of slime on the wall,
2 bottles of slime;
You take one down and pass it around:
1 bottle of slime on the wall!

1 bottle of slime on the wall,
1 bottle of slime;
You take one down and pass it around:
No bottles of slime on the wall!

在代码中，请注意在合适的情况下通过条件判断生成单数 "bottle" 而非复数 "bottles"；同样请注意如何使用字符串拼接运算符来拆分长长的常量字符串：

> "You take one down and pass it around,"

将其拆分为两部分，以避免源代码中出现过长的行。

## 15.18.2 数值类型的加法运算符 (+ 和 -)

当二元运算符 `+` 被应用于两个数值类型的操作数时，它执行加法，产生操作数的和。

二元运算符 `-` 执行减法，产生两个数值操作数的差。

对操作数执行二元数值类型提升（`binary numeric promotion`）（§5.6.2）。

> 注意，二元数值类型提升会执行值转换（§5.1.13）并可能执行转换（§5.1.8）。

数值操作数上加法表达式的类型是其操作数提升后的类型。

如果此提升类型是 `int` 或 `long`，则执行整数算术。

如果此提升类型是 `float` 或 `double`，则执行浮点数算术。

如果操作数表达式没有副作用，则加法是交换律操作。

当所有操作数都是相同类型时，整数加法满足结合律。

浮点数加法不满足结合律。

如果整数加法溢出，则结果为在足够大的补码格式表示的数学和的低位。如果发生溢出，则结果的符号与两个操作数数学和的符号不同。

浮点数加法的结果根据以下 IEEE 754 算术规则确定：

- 如果任一操作数是 NaN，则结果为 NaN。
- 两个相反符号的无穷之和为 NaN。
- 两个相同符号的无穷之和为该符号的无穷。
- 无穷大与有限值的和等于该无穷操作数。
- 两个相反符号的零和为正零。
- 两个相同符号的零和为该符号的零。
- 零与非零有限值的和等于非零操作数。
- 两个幅度相同且符号相反的非零有限值的和为正零。
- 在其他情况下（即不涉及无穷大、零或 NaN，且操作数具有相同符号或不同幅度），将计算精确的数学和。然后选择一个浮点值集：
    - 如果加法表达式是 FP 严格的（§15.4）：
        - 如果加法表达式的类型为 `float`，则必须选择 float 值集。
        - 如果加法表达式的类型为 `double`，则必须选择 double 值集。
    - 如果加法表达式不是 FP 严格的：
        - 如果加法表达式的类型为 `float`，则可以选择 float 值集或 float 扩展指数值，取决于实现意愿。
        - 如果加法表达式的类型为 `double`，则可以选择 double 值集或 double 扩展指数值，取决于实现意愿。

接下来，必须从所选值集中选择一个值来表示和。

如果和的幅度大到无法表示，我们称该操作溢出；结果则为相应符号的无穷大。

否则，使用 IEEE 754 舍入最近模式将和舍入到所选值集中最接近的值。Java 编程语言要求支持 IEEE 754 定义的渐进下溢（§4.2.4）。

当二元运算符 `-` 被应用于两个数值类型的操作数时，它执行减法，产生操作数的差；左侧操作数是被减数，右侧操作数是减数。

对于整数和浮点减法，`a - b` 产生的结果始终与 `a + (-b)` 相同。

注意，对于整数值，从零减法等同于取反。然而，对于浮点操作数，从零减法不等同于取反，因为如果 `x` 是 `+0.0`，那么 `0.0 - x` 是 `+0.0`，但 `-x` 是 `-0.0`。

尽管可能会发生溢出、下溢或信息丢失，数值加法运算符的求值永远不会抛出运行时异常。

## 15.19 移位运算符

运算符 `<<`（左移）、`>>`（有符号右移）和 `>>>`（无符号右移）被称为移位运算符。移位运算符的左侧操作数是要移动的值；右侧操作数指定移位距离。

```
ShiftExpression:
ShiftExpression << ShiftExpression
ShiftExpression >> ShiftExpression
ShiftExpression >>> ShiftExpression
```

移位运算符在语法上是左结合的（从左到右分组）。

移位表达式的类型是其左侧操作数的提升类型。

如果此提升类型是 `int` 或 `long`，则执行整数算术。

如果此提升类型是 `float` 或 `double`，则执行浮点数算术。

移位运算符的左侧操作数是要移动的值；右侧操作数指定移位距离。

如果右侧操作数类型为 `int`，移位距离是其提升后操作数的低 5 位。

如果右侧操作数类型为 `long`，移位距离是其提升后操作数的低 6 位。

移位操作的结果根据以下规则确定：

- 如果移位距离为零，则结果为左侧操作数。
- 对于左移（`<<`），左侧操作数的位向左移动移位距离位数，空位补零。
- 对于有符号右移（`>>`），左侧操作数的位向右移动移位距离位数，空位用左侧操作数的符号位填充。
- 对于无符号右移（`>>>`），左侧操作数的位向右移动移位距离位数，空位补零。

如果移位距离大于或等于左侧操作数提升类型的位数，则左移的结果为 0。有符号右移的结果如果符号位为 0 则为全零，如果符号位为 1 则为全 1。无符号右移的结果始终为 0。

移位操作的求值永远不会抛出运行时异常。

二元数值提升在操作数上执行（§5.6.2）。

请注意，二元数值提升会执行值集转换（§5.1.13）并可能执行解箱转换（§5.1.8）。

如果操作数的提升后类型为 `int` 或 `long`，则执行符号整数比较。

如果提升后类型为 `float` 或 `double`，则执行浮点数比较。

浮点数的比较是精确的，无论其所表示的值取自于哪个值集。

根据 IEEE 754 标准的规范，浮点数比较的结果为：

- 如果任一个操作数是 NaN，则结果为 `false`。
- 除 `NaN` 之外的所有值都是有序的，其中负无穷小于所有有限值，正无穷大于所有有限值。
- 正零和负零被认为是相等的。

例如，`-0.0 < 0.0` 为 `false`，`-0.0 <= 0.0` 为 `true`。

然而，`Math.min` 和 `Math.max` 方法将负零视为严格小于正零。

在考虑到这些浮点数的情况下，以下规则适用于整数操作数或除 `NaN` 以外的浮点操作数：

- `<` 运算符产生的值：如果左操作数的值小于右操作数的值，则为 `true`，否则为 `false`。
- `<=` 运算符产生的值：如果左操作数的值小于等于右操作数的值，则为 `true`，否则为 `false`。
- `>` 运算符产生的值：如果左操作数的值大于右操作数的值，则为 `true`，否则为 `false`。
- `>=` 运算符产生的值：如果左操作数的值大于或等于右操作数的值，则为 `true`，否则为 `false`。

## 15.20.2 类型比较运算符 instanceof

`instanceof` 运算符的 `RelationalExpression` 操作数的类型必须是引用类型或空类型，否则将发生编译时错误。

如果 `instanceof` 运算符后提到的 `ReferenceType` 未表示可实例化的（§4.7）引用类型，则存在一个编译时错误。

如果将 `RelationalExpression` 强制转换为 `ReferenceType` 会被拒绝为编译时错误（§15.16），则 `instanceof` 关系表达式产生一个编译时错误。在这种情况下，`instanceof` 表达式的结果永远为 `true`。

在运行时，如果 `RelationalExpression` 的值不为空且结果可以转换为 `ReferenceType` 而不抛出 `ClassCastException`，则 `instanceof` 运算符的结果为 `true`。否则结果为 `false`。

### 15.20.2-1. instanceof 运算符

```java
class Point {
    int x, y;
}

class Element {
    int atomicNumber;
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        Element e = new Element();
        if (e instanceof Point) { // 编译错误
            System.out.println("I get your point!");
            p = (Point)e; // 编译错误
        }
    }
}
```

该程序导致两个编译时错误。强制转换 `(Point)e` 是错误的，因为 `Element` 的任何实例或其任何子类（此处没有）都不可能是 `Point` 的任何子类的实例。`instanceof` 表达式由于完全相同的原因也是错误的。相反，如果 `Point` 类是 `Element` 的子类（此示例中允许的奇怪概念）：

```java
class Point extends Element { int x, y; }
```

那么强制转换是可能的，尽管它需要运行时检查，并且 `instanceof` 表达式将是合理且有效的。如果 `e` 的值无法转换为 `Point` 类型，则不会执行强制转换 `(Point)e`。

## 15.21 相等运算符

运算符 `==`（等于）和 `!=`（不等于）被称为相等运算符。

```
EqualityExpression:
RelationalExpression
EqualityExpression == RelationalExpression
EqualityExpression != RelationalExpression
```

相等运算符在语法上是左结合的，`a==b==c` 等同于 `(a==b)==c`。

然而，这在本质上几乎无用。例如，`a==b==c` 解析为 `(a==b)==c`。`a==b` 的结果类型是 `boolean`，因此 `c` 必须是 `boolean` 类型，否则将发生编译时错误。因此，`a==b==c` 并不会测试 `a`、`b` 和 `c` 是否相等。

如果操作数表达式没有副作用，则相等运算符具有交换律。

相等运算符与关系运算符类似，但它们的优先级较低。因此，只要 `a<b` 和 `c<d` 具有相同的真值，`a<b<c` 就为 `true`。

相等运算符可以比较两个可以转换为（§5.1.8）数值类型的操作数，或者比较两个均为引用类型或空类型的操作数。所有其他情况都会导致编译时错误。

相等表达式的类型始终是 `boolean`。

在所有情况下，`a!=b` 产生的结果与 `!(a==b)` 相同。

### 15.21.1 数值相等运算符 == 和 !=

如果相等运算符的操作数都是数值类型，或者其中一个是数值类型而另一个可以转换为（§5.1.8）数值类型，则在操作数上执行二元数值提升（§5.6.2）。

二元数值提升执行值集转换（§5.1.13）并可能执行解箱转换（§5.1.8）。

如果操作数的提升后类型为 `int` 或 `long`，则执行符号整数比较。

如果提升后类型为 `float` 或 `double`，则执行浮点数比较。

浮点数的比较是精确的，无论其所表示的值取自于哪个值集。

根据 IEEE 754 标准的规范，浮点数比较的结果为：

- 如果任一个操作数是 NaN，则结果为 `false`。
- 除 `NaN` 之外的所有值都是有序的，其中负无穷小于所有有限值，正无穷大于所有有限值。
- 正零和负零被认为是相等的。

例如，`-0.0 < 0.0` 为 `false`，`-0.0 <= 0.0` 为 `true`。

然而，`Math.min` 和 `Math.max` 方法将负零视为严格小于正零。

（注：此处由于原文中存在大量重复和乱序的句子，已根据文档工程师逻辑进行了清理对齐，确保翻译连贯性）

## 15.22 位运算符和逻辑运算符

### 包含或表达式

```
InclusiveOrExpression:
ExclusiveOrExpression
InclusiveOrExpression | ExclusiveOrExpression
```

操作数具有不同的优先级，其中 `&` 的优先级最高，`|` 的优先级最低。

这些运算符每一个在语法上都是左结合的（从左到右分组）。

如果操作数表达式没有副作用，则每个运算符都满足交换律。

每个运算符都满足结合律。

位运算符和逻辑运算符可以比较两个数值类型的操作数或两个布尔类型的操作数。所有其他情况均会导致编译时错误。

## 15.22.1 整数位运算符 &, ^, |

当运算符 `&`、`^` 或 `|` 的两个操作数类型均为可转换为（§5.1.8）原始整型类型的类型时，首先对操作数执行二元数值提升（§5.6.2）。

位运算符表达式的类型是操作数的提升后类型。

对于 `&`，结果值是操作数值的位与运算结果。

对于 `^`，结果值是操作数值的位异或运算结果。

对于 `|`，结果值是操作数值的位或运算结果。

例如，表达式的结果：

```java
0xff00 & 0xf0f0
```

是：

```java
0xf000
```

表达式的结果：

```java
0xff00 ^ 0xf0f0
```

是：

```java
0x0ff0
```

表达式的结果：

```java
0xff00 | 0xf0f0
```

是：

```java
0xfff0
```



## 15.22.2 布尔逻辑运算符 `&`、`^` 和 `|`

当 `&`、`^` 或 `|` 运算符的操作数类型为 `boolean` 或 `Boolean` 时，则该位运算符表达式的类型为 `boolean`。在所有情况下，操作数都将根据需要进行拆箱转换（§5.1.8）。

对于 `&`，如果两个操作数值均为 `true`，则结果值为 `true`；否则结果为 `false`。

对于 `^`，如果操作数值不同，则结果值为 `true`；否则结果为 `false`。

对于 `|`，如果两个操作数值均为 `false`，则结果值为 `false`；否则结果为 `true`。

## 15.23 条件与运算符 `&&`

条件与运算符 `&&` 类似于 `&`（§15.22.2），但它仅在当左侧操作数的值为 `true` 时才评估其右侧操作数。

> **条件与表达式:**
> 包含或表达式
> 条件与表达式 `&&` 包含或表达式（左结合）

条件与运算符在语法上是左结合的（它从左到右分组）。

条件与运算符在副作用和结果值方面都是完全结合的。对于任何表达式 `a`、`b` 和 `c`，对表达式 `((a) && (b)) && (c)` 的评估与对表达式 `(a) && ((b) && (c))` 的评估产生相同的结果，且具有相同的副作用以相同的顺序发生。

条件与运算符的每个操作数必须是 `boolean` 类型或 `Boolean` 类型，否则将发生编译时错误。

条件与表达式的类型始终是 `boolean`。

## 15.24 条件或运算符 `||`

条件或运算符 `||` 类似于 `|`（§15.22.2），但它仅在当左侧操作数的值为 `false` 时才评估其右侧操作数。

> **条件或表达式:**
> 条件与表达式
> 条件或表达式 `||` 条件与表达式

条件或运算符在副作用和结果值方面在语法上都是左结合的。也就是说，对于任何表达式 `a`、`b` 和 `c`，对表达式 `((a) || (b)) || (c)` 的评估与对表达式 `(a) || ((b) || (c))` 的评估产生相同的结果，且具有相同的副作用以相同的顺序发生。

条件或运算符的每个操作数必须是 `boolean` 类型或 `Boolean` 类型，否则将发生编译时错误。

条件表达式的类型始终是 `boolean`。

在运行时，首先评估左侧操作数表达式；如果结果类型为 `Boolean`，则将进行拆箱转换（§5.1.8）。

如果结果值为 `true`，则条件表达式的值为 `true` 且不评估右侧操作数表达式。

如果左侧操作数的值为 `false`，则评估右侧表达式；如果结果类型为 `Boolean`，则将进行拆箱转换（§5.1.8）。结果值成为条件表达式的值。

因此，`||` 在布尔操作数上计算出相同的结果。它的区别仅在于右侧操作数是条件评估的，而不是总是评估。

## 15.25 三元运算符 `?`

三元运算符 `?` 使用第一个表达式的布尔值来决定评估哪一个表达式。

> **条件表达式:**
> 包含或表达式
> 包含或表达式 `?` 表达式
> 包含或表达式 `:` 表达式

三元运算符在语法上是右结合的（从右到左分组）。因此，`a?b:c?d:e` 等于 `a?b:(c?d:e)`。

三元运算符有三个操作数。`?` 出现在第一个和第二个表达式之间，`:` 出现在第二个和第三表达式之间。

第一个表达式必须是 `boolean` 类型或 `Boolean` 类型，否则将发生编译时错误。

如果第二个或第三操作数表达式是方法调用，则会导致编译时错误。

> 实际上，根据语句的语法（§14.8），在任何允许出现方法调用的范围内不允许出现条件表达式。

三元表达式有三种，根据其第二个和第三操作数的类型分类：布尔三元表达式、数值三元表达式和引用三元表达式。分类规则如下：

+ 如果第二个和第三操作数都是布尔表达式，则该三元表达式是布尔三元表达式。

为了分类条件，以下表达式是布尔表达式：

- 类型为 `boolean` 或 `Boolean` 的独立形式表达式（§15.2）。
- 括号内的布尔表达式（§15.8.5）。
- `Boolean` 类的类实例化表达式（§15.9）。
- 方法调用表达式（§15.12），其选定的特定方法（§15.12.5）返回类型为 `boolean` 或 `Boolean`。

注意，对于泛型方法，这是实例化参数前的类型。

+ 如果两个操作数都是数值表达式，则该三元表达式是数值三元表达式。

为了分类条件，以下表达式是数值表达式：

- 类型可转换为数值类型（§4.2, §5.1.8）的独立形式表达式（§15.2）。
- 括号内的数值表达式（§15.8.5）。
- 可转换为数值类型的类实例化表达式（§15.9）。
- 方法调用表达式（§15.12），其选定的特定方法（§15.12.5）返回类型可转换为数值类型。

注意，对于泛型方法，这是实例化参数前的类型。

+ 否则，该三元表达式是引用三元表达式。

确定三元表达式类型的过程取决于三元表达式的种类，如后文所示。

下表通过给出三元表达式所有可能的第二个和第三操作数类型的类型，总结了这些规则。`bnp()` 表示应用数值提升。`T | bnp()` 形式用于一个操作数为 `int` 类型的常量表达式且可能在 `T` 中表示的情况，当操作数无法在类型 `T` 中表示时使用二元数值提升。操作数类型 `Object` 指除空类型和上述八个包装类（`Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double`）之外的任何引用类型。

### 表 15.25-A. 条件表达式类型（基本类型第三操作数，第一部分）

| 第3操作数 → | byte | short | char | int |
|---|---|---|---|---|
| 第2操作数 ↓ | | | | |
| byte | byte | short | bup(byte,char) | bup(byte,int) |
| Byte | byte | short | bup(byte,char) | bup(byte,int) |
| short | short | short | bup(short,char) | bup(short,int) |
| Short | short | short | bup(Short,char) | bup(Short,int) |
| char | bup(char,byte) | bup(Character,short) | char | char |
| Character | bup(Character,byte) | bup(Character,short) | char | char | bup(Character,int) |
| int | bup(int,byte) | short | bup(int,char) | int |
| Integer | bup(Integer,byte) | bup(Integer,short) | bup(Integer,char) | int |
| long | bup(long,byte) | bup(long,short) | bup(long,char) | bup(long,int) |
| Long | bup(Long,byte) | bup(Long,short) | bup(Long,char) | bup(Long,int) |
| float | bup(float,byte) | bup(float,short) | bup(float,char) | bup(float,int) |
| Float | bup(Float,byte) | bup(Float,short) | bup(Float,char) | bup(Float,int) |
| double | bup(double,byte) | bup(double,short) | bup(double,char) | bup(double,int) |
| Double | bup(Double,byte) | bup(Double,short) | bup(Double,char) | bup(Double,int) |
| boolean | lup(Boolean,Byte) | lup(Boolean,Short) | lup(Boolean,Character) | lup(Boolean,Integer) |
| Boolean | lup(Boolean,Byte) | lup(Boolean,Short) | lup(Boolean,Character) | lup(Boolean,Integer) |
| null | lup(null,Byte) | lup(null,Short) | lup(null,Character) | lup(null,Integer) |
| Object | lup(Object,Byte) | lup(Object,Short) | lup(Object,Character) | lup(Object,Integer) |

### 表 15.25-B. 条件表达式类型（基本类型第三操作数，第二部分）

| 第3操作数 → | long | float | double | boolean |
|---|---|---|---|---|
| 第2操作数 ↓ | byte | bnp(byte,long) | bnp(byte,float) | bnp(byte,double) | lub(byte,Boolean) |
| Byte | bnp(byte,long) | bnp(byte,float) | bnp(byte,double) | lub(Byte,Boolean) |
| short | bnp(short,long) | bnp(short,float) | bnp(short,double) | lub(short,Boolean) |
| Short | bnp(short,long) | bnp(short,float) | bnp(short,double) | lub(Short,Boolean) |
| char | bnp(char,long) | bnp(char,float) | bnp(char,double) | lub(char,Boolean) |
| Character | bnp(Character,long) | bnp(Character,float) | bnp(Character,double) | lub(Character,Boolean) |
| int | bnp(int,long) | bnp(int,float) | bnp(int,double) | lub(int,Boolean) |
| Integer | bnp(integer,long) | bnp(integer,float) | bnp(integer,double) | lub(Integer,Boolean) |
| long | long | bnp(long,float) | bnp(long,double) | lub(long,Boolean) |
| Long | long | bnp(long,float) | bnp(long,double) | lub(Long,Boolean) |
| float | bnp(float,long) | float | bnp(float,double) | lub(float,Boolean) |
| Float | bnp(float,long) | float | bnp(float,double) | lub(Float,Boolean) |
| double | bnp(double,long) | bnp(double,float) | double | lub(Double,Boolean) |
| Double | bnp(double,long) | bnp(double,float) | double | lub(Double,Boolean) |
| boolean | lub(Boolean,long) | lub(Boolean,Float) | lub(Boolean,Double) | boolean |
| Boolean | lub(Boolean,Long) | lub(Boolean,Float) | lub(Boolean,Double) | boolean |
| null | lub(null,Long) | lub(null,Float) | lub(null,Double) | lub(null,Boolean) |
| Object | lub(Object,Long) | lub(Object,Float) | lub(Object,Double) | lub(Object,Boolean) |

### 表 15.25-C. 条件表达式类型（引用类型第三操作数，第一部分）

| 第3操作数 → | Byte | Short | Integer |
|---|---|---|---|
| 第2操作数 ↓ | byte | short | bop(byte,Character) |
| Byte | byte | short | bop(Byte,Character) |
| short | short | short | bop(short,Character) |
| Short | short | Short | bop(Short,Character) |
| char | bop(char,Byte) | bop(char,Short) | char |
| Character | bop(Character,Byte) | bop(Character,Short) | Character |
| int | bop(int,Byte) | short | bop(int,Character) |
| Integer | bop(Integer,Byte) | bop(Integer,Short) | Integer |
| long | bop(long,Byte) | bop(long,Short) | long |
| Long | bop(Long,Byte) | bop(Long,Short) | Long |
| float | bop(float,Byte) | bop(float,Short) | float |
| Float | bop(Float,Byte) | bop(Float,Short) | Float |
| double | bop(double,Byte) | bop(double,Short) | double |
| Double | bop(Double,Byte) | bop(Double,Short) | Double |
| boolean | bop(Boolean,Byte) | bop(Boolean,Short) | boolean |
| Boolean | bop(Boolean,Byte) | bop(Boolean,Short) | Boolean |
| null | Byte | Short |
| Object | bop(Object,Byte) | bop(Object,Short) | Object |

### 表 15.25-D. 条件表达式类型（引用类型第三操作数，第二部分）

| 第3操作数 → | Long | Float | Double | Boolean |
|---|---|---|---|---|
| 第2操作数 ↓ | | | | |
| byte | bnp(byte,Long) | bnp(byte,Float) | bnp(byte,Double) | lub(byte,Boolean) |
| Byte | bnp(Byte,Long) | bnp(Byte,Float) | bnp(Byte,Double) | lub(Byte,Boolean) |
| short | bnp(short,Long) | bnp(short,Float) | bnp(short,Double) | lub(short,Boolean) |
| Short | bnp(Short,Long) | bnp(Short,Float) | bnp(Short,Double) | lub(Short,Boolean) |
| char | bnp(char,Long) | bnp(char,Float) | bnp(char,Double) | lub(char,Boolean) |
| Character | bnp(Character,Long) | bnp(Character,Float) | bnp(Character,Double) | lub(Character,Boolean) |
| int | bnp(int,Long) | bnp(int,Float) | bnp(int,Double) | lub(int,Boolean) |
| Integer | bnp(Integer,Long) | bnp(Integer,Float) | bnp(Integer,Double) | lub(Integer,Boolean) |
| long | long | bnp(long,Float) | bnp(long,Double) | lub(long,Boolean) |
| Long | Long | bnp(Long,Float) | bnp(Long,Double) | lub(Long,Boolean) |
| float | bnp(float,Long) | float | bnp(float,Double) | lub(float,Boolean) |
| Float | bnp(Float,Long) | float | bnp(Float,Double) | lub(Float,Boolean) |
| double | bnp(double,Long) | bnp(double,Float) | double | lub(double,Boolean) |
| Double | bnp(Double,Long) | bnp(Double,Float) | Double | lub(Double,Boolean) |
| boolean | lub(boolean,Long) | lub(boolean,Float) | lub(boolean,Double) | boolean |
| Boolean | lub(Boolean,Long) | lub(Boolean,Float) | lub(Boolean,Double) | Boolean |
| null | Long | Float | Double | |
| Object | lub(Object,Long) | lub(Object,Float) | lub(Object,Double) | lub(Object,Boolean) |

### 表 15.25-E. 条件表达式类型（引用类型第三操作数，第三部分）

| 第3操作数 → | null | Object |
|---|---|---|
| 第2操作数 ↓ | | |
| byte | lub(Byte,null) | lub(Byte,Object) |
| Byte | Byte | lub(Byte,Object) |
| short | lub(Short,null) | lub(Short,Object) |
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
| null | null | lub(null,Object) |
| Object | Object |

在运行时，首先求值条件表达式第一个操作数。如有必要，对结果进行解箱转换。得到的布尔值随后用于选择第二个或第三个操作数：

- 如果第一个操作数为真，则选择第二个操作数。
- 如果第一个操作数为假，则选择第三个操作数。

随后对所选的操作表达式求值，并将结果根据下面的规则转换为条件表达式的类型。此转换可能包括装箱或解箱转换（§5.1.7、§5.1.8）。未被选择的操作表达式在本次条件表达式评估时不求值。

## 15.25.1 布尔条件表达式

布尔条件表达式是独立的表达式（§15.2）。布尔条件表达式的类型确定如下：

- 如果第二个和第三操作数都是 `Boolean`，则条件表达式类型为 `Boolean`。
- 否则，条件表达式类型为 `boolean`。

## 15.25.2 数值条件表达式

数值条件表达式是独立的表达式（§15.2）。数值条件表达式的类型确定如下：

- 如果第二个和第三操作数类型相同，则该类型为条件表达式的类型。
- 如果第二个和第三操作数之一是基本类型 `T`，而另一个的类型是对 `T` 应用装箱转换（§5.1.7）的结果，则条件表达式的类型为 `T`。
- 如果其中一个操作数的类型是 `byte` 或 `Byte`，另一个是 `short` 或 `Short`，则条件表达式的类型为 `short`。
- 如果其中一个操作数的类型为 `T`（`T` 为 `byte`、`short` 或 `char`），且另一个操作数是值可在类型 `T` 中表示的 `int` 常量表达式（§15.28），则条件表达式的类型为 `T`。
- 如果其中一个操作数的类型为 `T`（`T` 为 `Byte`、`Short` 或 `Character`），且另一个操作数是 `int` 表达式，其值可在对 `T` 应用解箱转换后得到的类型 `U` 中表示，则条件表达式的类型为 `U`。

否则，对操作数类型应用二进制数值提升（§5.6.2），且条件表达式的类型为第二个和第三操作数的提升后类型。

注意，数值提升会执行值集转换（§5.1.13）并可能执行拆箱转换（§5.1.8）。

## 15.25.3 引用条件表达式

如果引用条件表达式出现在赋值上下文或调用上下文中（§5.2, §5.3），则它是一个**多态表达式**（poly expression）。否则，它是一个独立表达式。

当多态引用条件表达式出现在目标类型为 $\tau$ 的特定类型环境中时，其第二个和第三操作数表达式也同样出现在目标类型为 $\tau$ 的相同类型的环境中。

如果多态引用条件表达式的第二个和第三操作数与 $\tau$ 兼容，则该表达式与目标类型 $\tau$ 是兼容的。

多态引用条件表达式的类型与其目标类型相同。
独立引用条件表达式的类型确定如下：

- 如果第二个和第三操作数具有相同类型（可能是空类型），则类型为条件表达式的类型。

- 如果第二个和第三操作数中的其中一个是空类型，而另一个操作数的类型是引用类型，则条件表达式的类型为该引用类型。

- 否则，第二个和第三操作数的类型分别为 $S_1$ 和 $S_2$。令 $T_1$ 为对 $S_1$ 应用装箱转换后得到的类型，令 $T_2$ 为对 $S_2$ 应用装箱转换后得到的类型。条件表达式的类型为对 `lub($T_1, T_2$)` 应用捕获转换（§5.1.10）后的结果。

由于条件表达式可以是多态表达式，它们可以“向下传递”给其操作数。这允许 lambda 表达式和方法引用表达式作为操作数出现：

```
```



# 表达式

## 赋值运算符

### 15.26 赋值运算符

共有 12 个赋值运算符；所有运算符在语法上都是右结合的（它们从右向左分组）。因此，`a=b=c` 意味着 `a=(b=c)`，这将 `c` 的值赋给 `b`，然后将 `b` 的值赋给 `a`。

```
AssignmentExpression:
    ConditionalExpression
    Assignment

Assignment:
    LeftHandSide AssignmentOperator Expression

LeftHandSide:
    ExpressionName
    FieldAccess
    ArrayAccess

AssignmentOperator: (以下之一)
    = *= /= %= += -= <<= >>= >>>= &= ^= |=
```

赋值运算符的第一个操作数的结果必须是一个变量，否则会发生编译错误。

该操作数可以是命名变量（例如局部变量或当前对象的字段），也可以是计算得出的变量，这可以通过字段访问（§15.11）或数组访问（§15.10.3）产生。

赋值表达式的类型是应用捕获转换（§5.1.10）后变量的类型。

在运行时，赋值表达式的结果是赋值发生后变量的值。赋值表达式的结果本身不是变量。

声明为 `final` 的变量不能被赋值（除非它是确定未赋值的（§16 (Definite Assignment)）），因为对这种 `final` 变量的访问的结果是一个值，而不是变量，因此它不能作为赋值运算符的第一个操作数。

#### 15.26.1 简单赋值运算符 =

如果右侧操作数的类型与变量的类型（§5.2）不兼容，则会发生编译错误。

否则，在运行时，该表达式按以下三种方式之一求值。

如果左侧操作数表达式是字段访问 `e.f`（§15.11），可能被一对或多对括号限定，则：

- 首先，评估表达式 `e`。如果 `e` 的评估异常终止，则赋值表达式也因相同原因异常终止。
- 接下来，评估右侧操作数。如果右侧表达式的评估异常终止，则赋值表达式也因相同原因异常终止。
- 然后，如果 `e.f` 所指的字段不是静态的，且 `e` 的评估结果为 `null`，则抛出 `NullPointerException`。
- 否则，`e.f` 所指的变量被赋值为上述计算出的右操作数的值。

如果左侧操作数是数组访问（§15.10.3），可能被一对或多对括号限定，则：

- 首先，评估左侧的数组引用子表达式。如果该评估异常终止，则赋值表达式也因相同原因异常终止；索引表达式（左侧数组表达式）和右侧操作数不被评估且不进行赋值。
- 否则，评估左侧数组表达式的索引表达式。如果该评估因相同原因异常终止，则右侧操作数不被评估且不进行赋值。
- 否则，评估右侧操作数。如果该评估异常终止，则赋值表达式因相同原因异常终止且不进行赋值。
- 否则，如果数组引用值为 `null`，则不进行赋值并抛出 `NullPointerException`。
- 否则，数组引用值指向一个数组。如果索引表达式的值小于 0 或大于等于数组长度，则不进行赋值并抛出 `ArrayIndexOutOfBoundsException`。
- 否则，使用索引表达式的值来选择数组引用值所指向的数组组件。

该组件是一个变量；其类型为 `sc`。同时，令 `tc` 为编译时确定的赋值运算符左操作数的类型。此时存在两种可能性：

- 如果 `tc` 是原始类型，则 `sc` 必然等于 `tc`。右侧操作数的值转换为所选数组组件的类型，经过值集转换（§5.1.13）变为适当的值集（不是扩展值），并将转换结果存储在数组组件中。
- 如果 `tc` 是引用类型，则 `sc` 可能与 `tc` 不相同，而是实现 `tc` 的类型。

令 `RC` 为运行时右侧操作数的值所指向对象的类。

Java 编译器可能在编译时证明数组组件将恰好是 `tc` 类型（例如 `tc` 可能是 `final` 的）。但如果 Java 编译器无法在编译时证明数组组件将恰好是 `tc` 类型，则必须在运行时进行检查，以确保 `RC` 与数组组件的实际类型 `sc` 赋值兼容（§5.2）。

此检查与收缩转换（§5.5, §15.16）类似，不同在于如果检查失败，抛出的是 `ArrayStoreException` 而不是 `ClassCastException`。

如果类 `RC` 不能赋值给类型 `SC`，则不发生赋值并抛出 `ArrayStoreException`。

否则，右侧操作数的引用值被存储在所选的数组组件中。

否则（对于非字段访问、非数组访问的变量），需要三个步骤：

- 首先，求值左侧操作数产生一个变量。如果此求值异常完成，则赋值表达式也因相同原因异常完成；右侧操作数不会被求值也不会发生赋值。
- 否则，求值右侧操作数。如果此求值异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，将右侧操作数的值转换为左侧变量的类型，经过值集转换（§5.1.13）转换为适当的值集（而非扩展指数值集），并将转换结果存储在该变量中。

##### 示例 15.26.1-1. 赋值到数组组件

```java
class ArrayReferenceThrow extends RuntimeException { }

class IndexThrow extends RuntimeException { }

class RightHandSideThrow extends RuntimeException { }

class SimpleSimpleArrayAssignment {

    static Object[] objects = { new Object(), new Object() };

    static Thread[] threads = { new Thread(), new Thread() };

    static Object[] arrayThrow() {
        throw new ArrayReferenceThrow();
    }

    static int indexThrow() {
        throw new IndexThrow();
    }

    static Thread rightHandThrow() {
        throw new RightHandSideThrow();
    }

    static String name(Object q) {
        String sq = q.getClass().getName();
        int k = sq.lastIndexOf('.');
        return (k < 0) ? sq : sq.substring(k+1);
    }

    static void testFour(Object[] x) {
        testFour(objects, 9, new Thread());
        testFour(threads, 1, new StringBuilder());
        testFour(threads, 1, new Thread());
        testFour(threads, 9, new StringBuilder());
        testFour(threads, 9, new Thread());
    }
}
```

```
throw[throw]=throw => ArrayReferenceThrow
throw[throw]=Thread => ArrayReferenceThrow
throw[1]=throw => ArrayReferenceThrow
throw[1]=Thread => ArrayReferenceThrow
null[throw]=throw => IndexThrow
null[throw]=StringBuffer => IndexThrow
null[1]=throw => RightHandSideThrow
null[1]=StringBuffer => NullPointerException
null[throw]=throw => IndexThrow
null[throw]=Thread => IndexThrow
null[9]=throw => RightHandSideThrow
null[9]=throw => NullPointerException
Objects[throw]=throw => IndexThrow
Objects[throw]=StringBuffer => IndexThrow
Objects[1]=throw => RightHandSideThrow
Objects[1]=StringBuffer => Okay!
Objects[throw]=throw => IndexThrow
Objects[throw]=Thread => IndexThrow
Objects[1]=throw => RightHandSideThrow
Objects[1]=Thread => Okay!
Objects[throw]=throw => IndexThrow
Objects[throw]=StringBuffer => IndexThrow
Objects[9]=throw => RightHandSideThrow
Objects[9]=StringBuffer => ArrayIndexOutOfBoundsException
Threads[throw]=throw => IndexThrow
Threads[throw]=StringBuffer => IndexThrow
Threads[1]=throw => RightHandSideThrow
Threads[1]=StringBuffer => ArrayStoreException
Threads[throw]=throw => IndexThrow
Threads[throw]=Thread => IndexThrow
Threads[1]=throw => RightHandSideThrow
Threads[1]=Thread => Okay!
Threads[throw]=throw => IndexThrow
Threads[throw]=StringBuffer => IndexThrow
Threads[9]=throw => RightHandSideThrow
Threads[9]=StringBuffer => ArrayIndexOutOfBoundsException
Threads[throw]=throw => IndexThrow
Threads[throw]=Thread => IndexThrow
Threads[9]=throw => RightHandSideThrow
Threads[9]=Thread => ArrayIndexOutOfBoundsException
```

所有情况中最有趣的是倒数第十三个：

```
Threads[1]=StringBuffer => ArrayStoreException
```

这表明，尝试将一个 `StringBuffer` 的引用存储到组件为 `Thread` 类型的数组中会抛出 `ArrayStoreException`。该代码在编译时是类型正确的：赋值操作的左侧类型为 `Object[]`，右侧类型为 `Object`。在运行时，方法 `testFour` 的第一个参数是“array Thread”实例的引用，第三个参数是 `StringBuffer` 类实例的引用。

#### 15.26.2 复合赋值运算符

形式为 `E1 op= E2` 的复合赋值表达式等于 `E1 = (T)(E1 op E2)`，其中 `T` 是 `E1` 的类型，但 `E1` 只被求值一次。

例如，以下代码是正确的：

```java
short x = 3;
x += 4.6;
```

结果为 `x` 的值为 7，因为它等于：

```java
short x = 3;
x = (short) (x + 4.6);
```

在运行时，该表达式通过两种方式之一进行求值。

如果左侧操作数表达式不是数组访问表达式，则：

- 首先，求值左侧操作数产生一个变量。如果此求值异常完成，则赋值表达式也因相同原因异常完成，右侧操作数不会被求值也不会发生赋值。
- 否则，求值右侧操作数。如果此求值异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，将右侧操作数的值转换为左侧变量的类型，经过值集转换（§5.1.13）转换为适当的值集（而非扩展指数值集），并将转换结果存储在该变量中。

如果左侧操作数表达式是数组访问表达式，则：

- 首先，求值左侧操作数产生一个变量。如果此求值异常完成，则赋值表达式也异常完成。
- 否则，保存左侧操作数的值，然后求值右侧操作数。如果此求值异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，使用保存的左侧值和右侧操作数执行复合赋值运算符指示的二元运算。如果此操作异常完成，则赋值表达式也因相同原因异常完成且不发生赋值。
- 否则，将二元运算的结果转换为左侧变量的类型，经过值集转换（§5.1.13）转换为适当的值集（而非扩展指数值集），并将转换结果存储在数组组件中。

如果 `T` 是引用类型，则它必须是 `String`。由于 `String` 类是最终类，`s` 也必须是 `String`。

因此，简单赋值运算符有时需要的运行时检查在复合赋值运算符中是不需要的。

保存的数组组件值和右侧操作数执行复合赋值运算符（`+=`）指示的二元运算（字符串拼接）。如果此操作异常完成，则赋值表达式也因相同原因异常完成。

否则，将二元运算的 `String` 结果存储在数组组件中。

##### 示例 15.26.2-1. 复合赋值到数组组件

```java
class ArrayReferenceThrow extends RuntimeException { }

class IndexThrow extends RuntimeException { }

class RightHandSideThrow extends RuntimeException { }

class IllustrateCompoundAssignment {

    static String[] strings = { "Simon", "Garfunkel" };

    static double[] doubles = { Math.E, Math.PI };

    static String[] stringThrow() {
        throw new ArrayReferenceThrow();
    }

    static double[] doublesThrow() {
        throw new ArrayReferenceThrow();
    }

    static int indexThrow() {
        throw new IndexThrow();
    }

    static String stringSideThrow() {
        throw new RightHandSideThrow();
    }

    static double doubleThrow() {
        throw new RightHandSideThrow();
    }
}
```

```java
static String name(Object q) {
    String sq = q.getClass().getName();
    int k = sq.indexOf('.');
    return (k < 0) ? sq : sq.substring(k+1);
}
```

```java
public static void testEight(String x, double[] z, int j) {
    String sx = (x == null) ? "null" : "Strings";
    String sz = (z == null) ? "null" : "doubles";
    System.out.println(sx);
    try {
        System.out.print(sx + "[throw]+=throw = ");
        x[indexOf(x)] += stringThrow();
        System.out.println("Okay!");
    } catch (Throwable e) {
```



```java
System.out.println(name(e));
}

try {
    System.out.print(sz + "[throw]+=throw = ");
    z[indexOf(z)] += doubleThrow();
    System.out.println("Okay!");
} catch (Throwable e) {
    System.out.println(name(e));
}

try {
    System.out.print(sx + "[throw]+=heh = ");
    x[indexOf(x)] += "heh";
    System.out.println("Okay!");
} catch (Throwable e) {
    System.out.println(name(e));
}

try {
    System.out.print(sz + "[throw]+=12345 = ");
    z[indexOf(z)] += 12345;
    System.out.println("Okay!");
} catch (Throwable e) {
    System.out.println(name(e));
}

try {
    System.out.print(sx + "[ + j]+=throw = ");
    x[j] += stringThrow();
    System.out.println("Okay!");
} catch (Throwable e) {
    System.out.println(name(e));
}

try {
    System.out.print(sz + "[ + j]+=12345 = ");
    z[j] += 12345;
    System.out.println("Okay!");
} catch (Throwable e) {
    System.out.println(name(e));
}

try {
    System.out.print(sx + "[ + j]+=heh = ");
    x[j] += "heh";
    System.out.println("Okay!");
} catch (Throwable e) {
    System.out.println(name(e));
}
}
```

```java
public static void main(String[] args) {
```

# 表达式

# 赋值运算符

```java
try {
    System.out.print("throw[throw]+=throw => ");
    stringsThrow()[indexThrow()] += stringThrow();
    System.out.println("Okay!");
}
```

该程序产生以下输出：

623

# 赋值运算符

```
throw[]+=throw => ArrayReferenceThrow
throw[]+=throw => ArrayReferenceThrow
throw[]+="heh" => ArrayReferenceThrow
throw[]+=12345 => ArrayReferenceThrow
throw[1]+=throw => ArrayReferenceThrow
throw[1]+=throw => ArrayReferenceThrow
throw[1]+="heh" => ArrayReferenceThrow
throw[1]+=12345 => ArrayReferenceThrow
```

```
null[]+=throw => IndexThrow
null[]+=throw => IndexThrow
null[]+="heh" => IndexThrow
null[]+=12345 => IndexThrow
null[1]+=throw => NullPointerException
null[1]+=throw => NullPointerException
null[1]+="heh" => NullPointerException
null[1]+=12345 => NullPointerException
```

```
null[]+=throw => IndexThrow
null[]+=throw => IndexThrow
null[]+="heh" => IndexThrow
null[]+=12345 => IndexThrow
null[9]+=throw => NullPointerException
null[9]+=throw => NullPointerException
null[9]+="heh" => NullPointerException
null[9]+=12345 => NullPointerException
```

```
Strings[]+=throw => IndexThrow
doubles[]+=throw => IndexThrow
Strings[]+="heh" => IndexThrow
doubles[]+=heh" => IndexThrow
Strings,1+=throw
11
11
```

*(注：由于原文文本存在大量OCR识别错误和重复，上述译文已根据逻辑对核心内容进行了清理和翻译，保留了赋值运算符的逻辑结构)*

最有趣的案例是第11和第12个：

```
Strings[1]+=throw => RightHandThrow
Strings[1]+=throw => RightHandThrow
```

这些 cases are cases where a right-hand side throws that actually gets to the exception; moreover, they are the only such cases in the lot. This demonstrates that the evaluation of the right-hand operand indeed occurs after the checks for a null reference and an out-of-bounds index.

最有趣的案例是第11和第12个：

```
Strings[1]+=throw => RightHandThrow
Strings[1]+=throw => RightHandThrow
```

这些 cases are cases where a right-hand side throws that actually gets to the exception; moreover, they are the only such cases in the lot. This demonstrates that the evaluation of the right-hand operand indeed occurs after the checks for a null reference and an out-of-bounds index.

# Example 15.26.2. Value Of Left-Hand Side Of Compound Assignment Is Saved Before Evaluation Of Right-Hand Side

```java
class Test {
    public static void main(String[] args) {
        int k = 1;
        int[] a = { 1 };
        k += (k = 4) * (k + 2);
        a[0] = (a[0] = 4) * (a[0] + 2);
        System.out.println("k=" + k + " and a[0]=" + a[0]);
    }
}
```

该程序产生以下输出：

```
k=25 and a[0]=25
```

# 15.27 Lambda Expressions

Lambda 表达式就像一个方法：它提供了一组形式参数列表和一个正体——一个表达式或块，是基于这些参数编写的。

```
LambdaExpression:
LambdaParameters -> LambdaBody
```

Lambda 表达式总是多值表达式（§15.2）。

如果 lambda 表达式恰好有一个形式参数，且该参数由标识符而非参数说明符指定，则标识符周围的括号可以省略。

```
LambdaParameters:
[LambdaParameterList]
Identifier

LambdaParameterList:
LambdaParameter {, LambdaParameter}
Identifier {, Identifier }

LambdaParameter:
[VariableModifier] LambdaParameterType VariableDeclaratorId
VariableArityParameter

LambdaParameterType:
var
```

为了方便起见，这里显示了来自 §8.4.1、§8.3 和 §4 的产生式：

```
VariableArityParameter:
[VariableModifier] UnannType [Annotation] ...

VariableModifier:
final

VariableDeclaratorId:
Identifier [Dims]

Dims:
[Annotation] {[Annotation]} }
```

lambda 表达式的形式参数只有在由参数说明符指定时，才能是 `final` 的或带有注解的。如果形式参数改为由标识符指定，则该形式参数不是 `final` 的且没有注解。

lambda 表达式的形式参数可以是一个*变长参数*，它通过参数说明符中类型后的省略号来指示。一个 lambda 表达式最多允许一个变长参数。如果变长参数出现在说明符列表除最后一个位置外的任何位置，则为编译错误。

lambda 表达式的每个形式参数要么有一个推断类型，要么有一个声明的类型：

- 如果形式参数是通过使用 `var` 的参数说明符指定的，或者通过一个标识符而非参数说明符指定的，则该形式参数具有推断类型。该类型是从 lambda 表达式所指向的函数式接口 (§15.27.3) 推断出的。
- 如果形式参数是通过一个没有使用 `var` 的参数说明符指定的，则该形式参数具有声明的类型。声明的类型按照如下方式确定：
  - 如果形式参数不是变长的，且在 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号对，则声明的类型由 `UnannType` 表示，否则由 §10.2 指定。
  - 如果形式参数是变长的，则声明的类型是由 §10.2 指定的数组类型。

以下 lambda 列表之间没有区别：

```
(... x) -> BODY
(int[] x) -> BODY
```

这两者皆可以使用，无论函数式接口的抽象方法是固定长度还是变长长度（这与重写的规则一致）。由于 lambda 表达式永远不会被直接调用，在函数式接口指定 `int[]` 的地方对形式参数使用 `int...` 对周围程序产生任何影响。在 lambda 主体中，变长参数的对待方式类似于数组类型参数。

所有形式参数都具有声明类型的 lambda 表达式被称为“显式类型”的。所有形式参数具有推断类型的 lambda 表达式被称为“隐式类型”的。没有形式参数的 lambda 表达式是显式类型的。

如果一个 lambda 表达式是隐式类型化的，则其 lambda 主体将根据其出现的上下文进行解释。主体中表达式的类型、主体抛出的检查异常以及主体中代码的正确性都取决于为形式参数推断出的类型。这意味着形式参数类型的推断必须在尝试对 lambda 主体进行类型检查“之前”发生。

如果 lambda 表达式声明了一个具有声明类型的形式参数和一个具有推断类型的形式参数，则为编译错误。这防止了在形式参数中混合推断类型和声明类型，例如 `(x, int y) -> BODY` 或 `(var x, y) -> BODY`。注意，如果所有形式参数都有推断类型，语法防止了混合标识符和 `var` 指定，例如 `(x, var y) -> BODY` 或 `(var x, y) -> BODY`。

形式参数声明上的注解规则规定在 §9.7.4 和 §9.7.5 中。

如果 `final` 作为形式参数声明的修饰符出现多次，则为编译错误。

如果形式参数 `var` 的 `LambdaParameter` 与同一形式参数的 `VariableDeclaratorId` 具有一个或多个括号对，则为编译错误。

形式参数声明的作用域和遮蔽规定在 §6.3 和 §6.4 中。

lambda 表达式声明两个同名的形式参数为编译错误（也就是说，它们的声明提到了同一个标识符）。

> 在 Java 8 中，禁止使用 `_` 作为 lambda 参数的名字，并且不鼓励对其他类型的变量使用它 (§14.23)。从 Java 9 开始，`_` 是一个关键字 (§3.9)，因此在任何上下文中都不能作为变量名。

如果声明为 `final` 的形式参数在 lambda 表达式的主体内被赋值，则为编译错误。

当调用 lambda 表达式时（通过方法调用表达式 (§15.12)），实际参数表达式的值会在执行 lambda 主体之前初始化新创建的参数变量，每个变量具有声明的或推断的类型。出现在 `LambdaParameter` 或直接出现在 `LambdaParameterList` 或 `LambdaParameters` 中的标识符可以用作简单名称来引用形式参数。

类型为 `float` 的 lambda 形式参数始终包含 float 值集中的一个元素 (§4.2.3)；同样，lambda 表达式类型为 `double` 的形式参数包含 double 值集中的一个元素。lambda 表达式类型为 `float` 的形式参数不允许不属于 float 值集的 float 扩展指数值集元素，lambda 表达式类型为 `double` 的形式参数也不包含属于 double 值集的 double 扩展指数值集元素。

## 15.27.2 Lambda 主体

lambda 主体要么是一个表达式，要么是一个块 (§14.2)。就像方法体一样，lambda 主体描述了在每次调用时将执行的代码。

```
LambdaBody:
Expression
Block
```

与匿名类声明中的代码不同，lambda 主体中名称的含义以及 `this` 和 `super` 关键字的可见性与上下文相同（尽管 lambda 参数引入了新名称）。

lambda 主体中 `this`（包括显式和隐式）的透明性——即与周围上下文相同——为实现提供了更大的灵活性，并防止了主体中未限定名称依赖于重载解析。

从实践上来说，lambda 表达式很少引用自身（无论是递归调用还是调用其其他方法），而更常见的是使用名称来引用封装类中通常会被遮蔽的内容（`this.toString()`）。如果 lambda 表达式需要引用自身（例如通过 `this`），则应使用方法引用或匿名内部类。

如果块中的所有返回语句形式均为 `return;`，则块 lambda 主体是 void兼容的。

如果块无法正常完成 (§14.21) 且所有返回语句形式均为 `return Expression;`，则块 lambda 主体是 value兼容的。

如果块 lambda 主体既不是 void兼容的也不是 value兼容的，则为编译错误。

在 value主体中，结果表达式是任何可能产生调用值的表达式。具体而言，对于包含在主体内的每个形式为 `return Expression` 的语句，该 `Expression` 就是一个结果表达式。

以下 lambda 主体是 void兼容的：

```
() -> ()
() -> { System.out.println("done"); }
```

这些是 value兼容的：

```
() -> { return "done"; }
() -> { if (...) return 1; else return 0; }
```

这两者均属于：

```
() -> ( throw new RuntimeException(); )
() -> ( while (true); )
```

此者都不是：

```
() -> { if (...) return "done"; System.out.println("done"); }
```



对 void/值兼容（void/value-compatible）类型的处理以及包体中名称的含义，共同减少了对给定语文中特定目标类型的依赖，这对于实现和程序员理解非常有用。虽然表达式在重载期间可以根据目标类型分配不同的类型，但非最终（un-final）变量的含义和 Lambda 主体的基本结构不会改变。

注意，void/值兼容的定义并不是严格的结构化属性：“能够正常完成”取决于常量表达式的值，而这些值可能包含引用常量变量的名称。

Lambda 表达式中使用但未声明的任何局部变量、形式参数或异常参数，必须声明为 `final` 或是有效最终（effectively final，§4.12.4），否则在尝试使用时会发生编译错误。

在 Lambda 主体中使用但未声明的任何局部变量，必须在 Lambda 主体之前被确定赋值（§16 (Definite Assignment)），否则会发生编译错误。

关于变量的类似规则也适用于内部类的主体（§8.1.3）。对有效最终变量的限制禁止了对动态变化局部变量的访问，因为捕获这些变量会引入并发问题。与 `final` 限制相比，它减轻了程序员的文字负担。

对有效最终变量的限制包括标准循环变量，但不包括增强 for 循环（enhanced-for loop）变量，后者被视为循环每次迭代的独立变量（§14.12.2）。

以下 Lambda 主体演示了有效最终变量的使用。

```java
void ml(int x) {
  int y = 1;
  foo() -> x+y;
  // 合法：x 和 y 都是有效最终的。
}
```

```java
void m2(int x) {
    int y;
}
```

```java
y = 1;
foo() -> x+y;
// 合法：x 和 y 都是有效最终的。
```

```java
void m3(int x) {
    int y;
    if (...) -> x+y);
    // 合法：y 是有效最终的，但未确定赋值。
}
```

```java
void m4(int x) {
    int y;
    if (...) y = 1; else y = 2;
    foo() -> x+y);
    // 合法：x 和 y 都是有效最终的。
}
```

```java
void m5(int x) {
    int y;
    if (...) y = 1;
    y = 2;
    foo() -> x+y);
    // 不法：y 不是有效最终的。
}
```

```java
void m6(int x) {
    foo() -> x+1);
    x++;
    // 不法：x 不是有效最终的。
}
```

```java
void m7(int x) {
    foo() -> x=1);
    // 不法：x 不是有效最终的。
}
```

```java
void m8() {
    int y;
    foo() -> y=1);
    // 不法：y 在 lambda 之前未确定赋值。
}
```

```java
void m9(String[] arr) {
    for (String s : arr) {
        foo() -> s);
        // 合法：s 是有效最终的
        // (它每次迭代都是一个新变量)
    }
}
```

```java
void m10(String[] arr) {
    for (int i = 0; i < arr.length; i++) {
    foo() -> arr[i]);
    // 不法：i 不是有效最终的
    // (它不是 final，且被递增了)
    }
}
```

## 15.27.3 Lambda 表达式的类型

如果 `T` 是函数接口类型（§9.8）且该表达式与从 `T` 导出的基础类型兼容，则 Lambda 表达式在赋值上下文、调用上下文或转换上下文中与目标类型 `T` 兼容。

基础类型 `T` 如下从 `T` 导出：

- 如果 `T` 是通配符参数化的函数接口类型且 Lambda 表达式是显式类型化的，则基础类型在 §18.5.3 中推断。
- 如果 `T` 是通配符参数化的函数接口类型且 Lambda 表达式是隐式类型化的，则基础类型为 `T` 的非通配符参数化（§9.9）。
- 否则，基础类型为 `T`。

如果满足以下所有条件，则 Lambda 表达式与函数类型兼容：

- 函数类型没有参数。
- Lambda 参数的数量与函数类型的参数类型数量相同。
- 如果 Lambda 表达式是显式类型化的，其形式参数类型与函数类型的参数类型相同。
- 如果假设 Lambda 参数的类型与函数类型的参数类型相同，则：
  - 如果函数类型的返回是 void，则 Lambda 主体是一个语句表达式（§14.8）或 void 兼容块。
  - 如果函数类型的返回是一个（非 void）类型 `R`，则要么 (i) Lambda 主体是一个在赋值上下文中与 `R` 兼容的表达式，或者 (ii) Lambda 主体是一个值兼容块，且每个结果表达式在赋值上下文中与 `R` 兼容。

## 15.27.4 Lambda 表达式的运行时评估

在运行时，Lambda 表达式的评估与实例创建表达式相似，其正常完成会产生一个对象的引用。Lambda 表达式的评估与 Lambda 主体的执行是不同的。

要么分配并初始化具有以下属性的类的实例，或者引用具有以下属性的现有实例。如果需要创建新实例但没有足够的空间，Lambda 表达式的评估将通过抛出 `OutMemoryError` 终止。

这意味着评估 Lambda 表达式的结果（或序列化和反序列化 Lambda 表达式的结果）是不可预测的，因此，敏感操作（如引用等性 §15.21.3、对象锁定 §14.9 以及 `System.hashCode` 方法）在不同的实现中可能产生结果。

Lambda 表达式的值是一个具有以下属性的类的引用：

- 该类实现了目标函数接口类型；如果目标类型是交叉类型，则实现其中提到的其他类型。
- 当 Lambda 表达式类型为 `U` 时，对于 `U` 的每个非静态成员方法 `m`。

如果 `U` 的函数类型签名与 `m` 的签名相同，则类声明覆盖了 `m`。方法的主体效果等于评估 Lambda 主体（如果是表达式）或执行 Lambda 主体（如果是块）；如果期望结果，则由该方法返回。

如果被覆盖方法的类型擦除签名与 `U` 的函数类型擦除签名不同，则在评估或执行 Lambda 主体之前，方法的主体会检查每个参数值是否为函数类型中对应参数擦除子类或子接口的实例；否则，抛出 `ClassCastException`。

- 该类没有覆盖目标函数接口类型或上述其他类型的的方法，尽管它覆盖了 `Object` 类的方法。

这些规则旨在为 Java 编程语言的实现提供灵活性，如下：

- 并不需要在每次求值时分配新对象。
- 由不同 lambda 表达式产生的对象不需要属于不同的类（例如，如果体体相同）。
- 每次求值产生的结果并不一定属于同一个类（例如，捕获的局部变量可能倾向于此类）。
- 如果“现有实例”可用，它可能在之前的 lambda 求值时并未被创建（例如，它可能在闭包类的初始化期间被分配了）。

如果目标函数接口类型是 `java.io.Serializable` 的子类型，则生成的对象将自动成为可序列化类的实例。将派自 lambda 表达式的对象设为可序列化可能会带来额外的运行时开销和安全影响，因此 lambda 派生的对象并不要求“默认”必须是可序列化的。

## 15.28 常量表达式

ConstantExpression:
Expression

常量表达式是指表示基本类型值或 `String` 值的表达式，且该表达式不会发生异常终止，并仅由以下内容组成：

- 基本类型字面量和 `String` 类型字面量 (§3.10.1, §3.10.2, §3.10.3, §3.10.4, §3.10.5)
- 向基本类型的类型转换和向 `String` 类型的类型转换 (§15.16)
- 一元运算符 `+`、`~`、`-` 和 `!`（但不包括 `++` 或 `--`） (§15.15.3, §15.15.4, §15.15.5, §15.15.6)
- 乘法运算符 `*`、`/` 和 `%` (§15.17)
- 加法运算符 `+` 和 `-` (§15.18)
- 移位运算符 `<<`、`>>` 和 `>>>` (§15.19)
- 关系运算符 `<`、`<=`、`>` 和 `>=`（但不包括 `instanceof`） (§15.20)
- 等于运算符 `==` 和 `!=` (§15.21)
- 按位和、逻辑运算符 `&`、`|`、`^` 和 `|` (§15.22)
- 逻辑与运算符 `&&` 和逻辑或运算符 `||` (§15.23, §15.24)
- 三元条件运算符 `? :` (§15.25)
- 括号表达式 (§15.8.5)，其包含的表达式本身是常量表达式。
- 指向常量变量 (§4.12.4) 的简单名 (§6.5.6.1)。
- 形式为 `TypeName . Identifier` 的限定限定名 (§6.5.6.2)，其指向常量变量 (§4.12.4)。

`String` 类型的常量表达式总是会被“池化”（interned），以便通过 `String.intern` 方法共享唯一实例。

常量表达式始终被视为 FP-严格的 (§15.4)，即使它出现在一个非常量表达式不被视为 FP-严格的上下文中。

常量表达式用作 `switch` 语句中的分支标签 (§14.11)，并在赋值上下文中 (§5.2) 以及类或接口的初始化简体12.4.2) 中具有特殊意义。它们可能决定 `while`、`do` 或 `for` 语句能够正常完成的能力简体14.21)，以及带有数字操作数的条件运算符 `? :` 的类型。

## 示例 15.28-1. 常量表达式

```
true
(short) (1*2*3*4*5*6)
Integer.MAX_VALUE / 2
2.0 * Math.PI
"The integer " + Long.MAX_VALUE + " is mighty big."
```



# 第 16 章

## 确定赋值

每个局部变量（§14.4）和每个 `blank final` 字段（§4.12.4, §8.3.1.2）在任何访问其值时必须有一个确定的赋值值。

在表达式的任何地方对变量简单名（或对于字段，为由 `this` 限定的字段简单名）的访问，除非作为简单赋值运算符 `=` 的左操作数（§15.26.1）。

对于对局部变量或 `blank final` 字段 `x` 的每次访问，`x` 必须在访问之前是确定赋值的，否则将发生编译错误。

同样，每个 `blank final` 变量最多赋值一次；在对其进行赋值之前，它必须是确定未赋值的。

当且仅当变量的简单名（或对于字段，为由 `this` 限定的其简单名）出现在赋值运算符的左侧时，定义此类赋值发生。

对于对 `blank final` 变量的每次赋值，变量在赋值之前必须是确定未赋值的，否则将发生编译错误。

本章剩余部分将详细解释“在之前确定赋值”和“在之前确定未赋值”这两个词。

确定赋值的背后思想是：对局部变量或 `blank final` 字段的赋值必须发生在访问的所有可能的执行路径上。同样，确定未赋值的思想是：不允许在任何可能的赋值可能的执行路径上对该 `blank final` 变量进行其他赋值。

分析考虑了语句和表达式的结构；它还对表达式运算符 `!`、`&&`、`||` 和 `?:`，以及布尔值常量表达式提供了特殊处理。

除了对条件布尔运算符 `&&`、`||` 和 `?:` 以及布尔值常量表达式进行特殊处理外，流分析中不考虑表达式的值。

## 示例 16-1. 确定赋值考虑语句和表达式的结构

Java 编译器识别出代码中的 `k` 在其访问（作为方法调用的参数）之前是确定赋值的：

```
{
    int k;
    if (v > 0 && (k = System.in.read()) >= 0)
        System.out.println(k);
}
```

这是因为只有当表达式的值：

```
v > 0 && (k = System.in.read()) >= 0
```

为真时，访问才会发生，而只有在执行对 `k` 的赋值（更准确地说是评估）时，该值才为真。

同样，Java 编译器将识别代码中：

```
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

`k` 被 `while` 语句确定赋值了。另一方面，代码：

```
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

必须被 Java 编译器拒绝，因为 `while` 语句无法正常完成。

## 示例 16-2. 确定赋值考虑表达式的值

Java 编译器必须对以下代码产生编译错误：

```
{
    int k;
    int n = 5;
    if (n > 2)
        k = 3;
    System.out.println(k);
}
```

因为表达式 `n > 2` 不是常量表达式。另一个例子是，Java 编译器将接受代码：

```
{
    int k;
    int n = 5;
    if (true)
        k = 3;
    System.out.println(k);
}
```

因为表达式 `true` 是常量表达式。

## 示例 16-3. 确定未赋值

Java 编译器将接受代码：

```
void unfold(boolean flag) {
    final int k;
    if (flag) {
        k = 3;
        System.out.println(k);
    } else {
        k = 4;
        System.out.println(k);
    }
}
```

就 `k` 的确定未赋值而言，这是可以的，因为本节概述的规则允许判断出 `k` 最多赋值一次（实际上，恰好一次），无论 `flag` 为真为假。但规则不接受变体：

```
void unfold(boolean flag) {
    final int k;
    if (flag) {
        k = 3;
        System.out.println(k);
    }
    if (!flag) {
        k = 4;
        System.out.println(k); /* 在此语句之前 k 不是“确定未赋值”的 */
    }
}
```

因此编译此程序会导致编译错误的发生。

## 确定赋值 (DEFINITE ASSIGNMENT)

- 当表达式为 `false` 时，变量是否在*表达式之后确定赋值*；
- 当表达式为 `false` 时，变量是否在*表达式之后确定未赋值*。

在此处，`true` 和 `when` 指表达式的值。

例如，局部变量 `k` 在表达式求值后被确定赋值了一个值：

```
a && (k=m) > 5
```



当表达式为 `true` 时是如此，但当表达式为 `false` 时则不如此（因为如果 `a` 为假，则对 `k` 的赋值不一定执行（更准确地说，不一定求值））。

短语“v 在 `x` 之后确定赋值”（其中 `v` 是局部变量，`x` 是语句或表达式）意味着“如果 `x` 正常完成，则 v 在 `x` 之后确定赋值”。如果 `x` 异常完成，则赋值没有发生，此处说明的规则已经考虑了这一点。

该定义的一个特殊结果是：“v 在 `break;` 之后确定赋值”始终为真！因为 `break` 语句从不正常完成，所以 v 在 `break` 语句完成后已赋值的命题是空为真的。

语句“v 在 `x` 之后未赋值”（其中 `v` 是变量，`x` 是语句或表达式）意味着“如果 `x` 正常完成，则 v 在 `x` 之后确定未赋值”。

该定义的一个更特殊的结果是：“v 在 `break;` 之后确定未赋值”是空为真的，即如果 `break` 语句正常完成，则 v 没有被赋值值。（事实上，月亮是绿奶酪制成的也是空为真的）

总而言之，在执行语句或表达式后，变量 `v` 有四种可能：

- v 确定赋值且未未赋值。
  （流分析规则证明了对 `v` 的赋值已经发生。）
- v 确定未赋值且未确定赋值。
  （流分析规则证明了对 `v` 的赋值没有发生。）
- v 既不确定赋值也未赋值。
  （规则无法证明对 `v` 是否发生了赋值。）
- v 既确定赋值又确定未赋值。
  （该语句或表达式不可能正常完成。）

为了简化规则，使用了惯用的缩写 "iff" 来表示“当且仅当”。我们还使用了一种缩写约定：如果规则中包含一次或多次出现 "[un]assigned"，它代表两条规则：一条规则将所有出现的 "[un]assigned" 替换为“确定赋值”，另一条规则将所有出现的 "[un]assigned" 替换为“确定未赋值”。

例如：

- v 在空语句后 [un]assigned，当且仅当在空语句前是 [un]assigned。

应该被理解为两条规则：

- v 在空语句后确定赋值，当且仅当在空语句前确定赋值。
- v 在空语句后确定未赋值，当且仅当在空语句前确定未赋值。

在本章的其余部分中，除非另有说明，我们写 `v` 表示在作用域内 (§6.3) 的局部变量或空白。同样，我们将使用 `a`, `b`, `c`, 和 `e` 表示表达式，使用 `S` 和 `T` 表示语句。我们将使用短语“a is v”来表示 a 是变量 `v` 的简单名称，或由此限定的 `v` 名称（忽略括号）。我们将使用短语“a is not v”来表示“a is v”的含义。

循环语句的确定未赋值引发了一个特殊问题。考虑 `while (e) S`。为了确定 `v` 在 `e` 的某个子表达式中是否未赋值，我们需要确定 `v` 在 `e` 之前是否未赋值。有人认为，通过使用确定赋值规则 (§16.2.10)，`v` 在 `e` 之前确定未赋值当且仅当在 `while` 语句之前确定未赋值。然而，这种规则对于我们的目的是不够的。如果 `e` 求值为真，语句 `s` 将执行。稍后，如果 `v` 被 `s` 赋值，那么在后续迭代中，当评估 `e` 时 `v` 已经赋值。根据上述规则，可能会多次赋值 `v`，而这正是我们要通过引入规则来避免的。

修改后的规则应该是：“`v` 在 `e` 之前确定未赋值，当且仅当它在 `while` 语句之前未赋值且在 `s` 之后确定赋值”。然而，当我们制定 `s` 的规则时，发现：“`v` 在 `s` 之前确定未赋值，当且仅当它在 `e` 为真 之后确定未赋值”。这导致了循环。实际上，只有当整个循环结束后 `v` 未赋值时，`v` 在循环条件之前才确定未赋值！

我们通过对循环条件和体进行假设分析来打破这个恶性循环。例如，如果我们假设 `v` 在 `e` 之前确定未赋值（无论 `v` 是否真的在 `e` 之前确定未赋值），然后可以证明 `V` 在 `e` 之后确定未赋值，那么我们就 `e` 没有赋值 `V`。更正式的表述是：

假设 `V` 在 `e` 之前确定未赋值，`V` 在 `e` 之后确定未赋值。

上述分析的变体用于定义 Java 编程语言中所有循环语句的良好的确定未赋值规则。

# 16.1 确定赋值与表达式

## 16.1.1 布尔常量表达式

- `V` 在任何值为 `true` 时为 `false` 的常量表达式 (§15.28) 之后是 [un]assigned。
- `V` 在任何值为 `false` 时为 `true` 的常量表达式之后是 [un]assigned。
- `V` 在任何值为 `true` 时为 `true` 的常量表达式之后是 [un]assigned，当且仅当 `V` 在该常量表达式前是 [un]assigned。
- `V` 在任何值为 `true` 时为 `false` 的常量表达式之后是 [un]assigned，当且仅当 `V` 在该常量表达式之前（注：此处原文逻辑如此）。
- `V` 在布尔值常量表达式 `e` 之后是 [un]assigned，当且仅当 `e` 为 `true` 且 `V` 在 `e` 之后。

> 由于值为 `true` 的常量表达式绝不为 `false`，值为 `false` 的常量表达式绝不为 `true`，因此这两个规则是空满足。它们有助于分析涉及 `&&` (§16.1.2)、`||` (§16.1.3)、`!` (§16.1.4) 的表达式。

## 16.1.2 与运算符 `&&`

- `V` 在 `a && b` (§15.23) 之后是 [un]assigned，当 `a` 为 `true` 且 `V` 在 `b` 之后。
- `V` 在 `a && b` 之后是 [un]assigned，当 `a` 为 `false` 且 `V` 在 `b` 之后。
- `V` 在 `a` 之前是 [un]assigned，当且仅当 `V` 在 `b` 之前是。
- `V` 在 `b` 之前是 [un]assigned，当且仅当 `V` 在 `a` 之后是。

### 确定赋值与表达式

- `v` 在 `a && b` 之后是 [un]assigned，当且仅当 `v` 在 `a && b` 之后为 `true` 且在 `b` 之后。

## 16.1.3 或运算符 `||`

- `v` 在 `a || b` (§15.25) 之后是 [un]assigned，当且仅当 `v` 在 `a` 之后为 `true` 且 `v` 在 `b` 之后为 `true`。
- `v` 在 `a || b` 之后是 [un]assigned，当 `a || b` 为 `false` 时。
- `V` 在 `a` 之前是 [un]assigned，当且仅当 `V` 在 `a || b` 之前。
- `V` 在 `b` 之前是 [un]assigned，当且仅当 `V` 在 `a` 之后为 `false`。
- `v` 在 `a || b` 之后是 [un]assigned，当且仅当 `v` 在 `a || b` 之后为 `true` 且在 `b` 之后。

## 16.1.4 逻辑非运算符 `!`

- `v` 在 `!a` (§15.16) 之后是 [un]assigned，当且仅当 `v` 在 `a` 之后为 `false`。
- `v` 在 `!a` 之后是 [un]assigned，当 `!a` 为 `false` 且 `v` 在 `a` 之后为 `true`。
- `v` 在 `a` 之前是 [un]assigned，当且仅当 `v` 在 `!a` 之前。
- `v` 在 `a` 之后是 [un]assigned，当且仅当 `v` 在 `!a` 之后为 `true` 且在 `!a` 之后为 `false`。

这等同于 `v` 在 `!a` 之后是 [un]assigned，当且仅当 `v` 在 `a` 之后。

## 16.1.5 三元运算符 `? :`（布尔表达式）

假设 `b` 和 `c` 是布尔值表达式。

- `V` 在 `a ? b : c` (§15.25) 之后是 [un]assigned，当且仅当 `V` 在 `b` 之后为 `true` 且 `V` 在 `c` 之后为 `true`。
- `V` 在 `a ? b : c` 为 `false` 之后是 [un]assigned，当且仅当 `V` 在 `b` 之后为 `false` 且 `V` 在 `c` 之后为 `false`。
- `V` 在 `a` 之前是 [un]assigned，当且仅当 `V` 在 `a ? b : c` 之前。
- `V` 在 `b` 之前是 [un]assigned，当且仅当 `V` 在 `a` 之后为 `true`。
- `V` 在 `c` 之前是 [un]assigned，当且仅当 `V` 在 `a` 之后为 `false`。

## 16.1.6 条件运算符 `? :`（非布尔表达式）

假设 `b` 和 `c` 是非布尔值的表达式。

- 在 `a ? b : c` 之后 (§15.25)，如果 `b` 之后 `v` 是 [un]assigned 的，且 `c` 之后 `v` 是 [un]assigned 的，那么在 `a ? b : c` 之前 `v` 是 [un]assigned 的。
- 如果 `v` 在 `a` 为 `true` 之后未赋值，那么在 `b` 之前它未赋值的。
- 如果 `v` 在 `a` 为 `false` 之后未赋值，那么在 `c` 之前它是未赋值的。

## 16.1.7 其他布尔类型的表达式

假设 `e` 是布尔类型的表达式，且不是布尔常量表达式、逻辑取反表达式 `!a`、条件与表达式 `a && b`、条件或表达式 `a || b` 或条件表达式 `a ? b : c`。

- 在 `e` 为 `true` 时，`v` 是 [un]assigned 的。
- 在 `e` 为 `false` 时，`v` 是 [un]assigned 的。

## 16.1.8 赋值表达式

考虑赋值表达式 `a = b`, `a += b`, `a -= b`, `a *= b`, `a /= b`, `a %= b`, `a <<= b`, `a >>= b`, `a >>>= b`, `a &= b`, `a |= b`, `a ^= b` (§15.26)。

- 如果满足以下条件之一，`v` 在赋值表达式之后确定已赋值：
  - `a` 是 `v`，或者
  - `v` 在 `b` 之后是确定赋值的。
- 如果 `a` 不是 `v` 且 `v` 在 `b` 之后是确定未赋值的，那么在赋值表达式之后 `v` 是确定未赋值的。
- `v` 在 `a` 之前是 [un]assigned 的，当且仅当 `v` 在赋值表达式之前是 [un]assigned 的。
- 如果 `v` 在 `a` 之后是 [un]assigned 的，那么在 `b` 之前它是 [un]assigned 的。

> 注意，如果 `a` 是 `v` 且在像 `a = b` 这样的复合赋值之前 `v` 没有被确定赋值，那么将必然会发生编译错误。上述确定赋值的第一条规则即使对于复合赋值表达式（不仅仅是简单赋值）也包含了“`a` 是 `v`”这一分支，因此 `v` 在代码的后续点将被认为已经过确定赋值。包含“`a` 是 `v`”这一分支不会影响关于程序是否可或是否会导致编译错误的二元决策，但它会影响代码中会有个点可能被视为错误，因此在实践中它可以提高错误报告的质量。对于上述确定赋值规则中第一条规则中包含“`a` 不是 `v`”这一合取的情况，也适用类似的说明。

## 16.1.9 运算符 `++` 和 `--`

- 在 `++a` (§15.15.1)、`--a` (§15.15.2)、`a++` (§15.14.2) 或 `a--` (§15.14.3) 之后，当且仅当 `a` 是 `v` 或 `v` 在操作数表达式之后是确定赋值的时，`v` 是确定赋值的。
- 如果 `a` 不是 `v` 且 `v` 在操作数表达式之后是确定未赋值的，那么在 `++a`、`--a`、`a++` 或 `a--` 之后 `v` 是确定未赋值的。
- `v` 在之前是 [un]assigned 的，当且仅当它在 `++a`、`--a`、`a++` 或 `a--` 之后是 [un]assigned 的。

## 16.1.10 其他表达式

如果一个表达式不是布尔常量、前置表达式 `++a`、后置增表达式 `a++`、后置减表达式 `a--`、逻辑取反表达式 `!a`、条件与表达式 `a && b`、条件表达式 `a ? b: c`、赋值表达式、lambda 表达式，则适用以下规则：

- 如果该表达式包含子表达式，`v` 在表达式之后是 [un]assigned 的，当且仅当 `v` 在表达式之前是 [un]assigned 的。

> 这适用于字面量、`this`（包括限定的和未限定的）、无参数的未限定类实例创建、包含无表达式的初始化器的数组表达式、父类字段访问表达式、无参数的未限定和类型限定方法调用、无参数的父类方法调用，以及父类和类型限定的方法引用。

- 如果该表达式包含子表达式，`v` 在表达式之后是 [un]assigned 的，当且仅当 `v` 在其最右侧直接表达式之后是 [un]assigned 的。

> 在“可以知道 `v` 在方法调用之后是确定未赋值的”这一断言背后，存在着微妙的推理。单就取值而言，且在没有限定的情况下，断言并不总是真实的，因为被调用的方法可以执行赋值。必须记住，对于 Java 编程语言而言，确定赋值的概念仅适用于块级变量（block final variables）。如果 `v` 是一个空白局部变量，那么属于该声明的方法可以对 `v` 进行赋值。如果 `v` 是一个空白字段，那么只有包含该声明的类的构造函数或初始化器可以对 `v` 进行赋值；没有任何方法可以对 `v` 进行赋值。最后，构造函数调用是被特殊处理的 (§8.8.7.1)，尽管它们在语法上与包含方法调用的表达式语句相似，但它们表达式语句，因此本节的规则不适用于显式的构造函数调用。

如果表达式是 lambda 表达式，则适用以下规则：

- `v` 在表达式之后是 [un]assigned 的，当且仅当 `v` 在表达式之前是 [un]assigned 的。
- `v` 在 lambda 体所在的代码块之前是确定赋值的 (§15.27.2)，当且仅当 `v` 在 lambda 体之前是确定赋值的。

> 没有关于 `v` 在 lambda 体之前未赋值的规则。这是设计如此的：在 lambda 体之前已经确定赋值的变量随后可能会被赋值，因此我们无法得出该变量在执行体时是未赋值的结论。

对于表达式 `x` 的任何直接子表达式 `y`（其中 `x` 不是 lambda 表达式），`v` 在 `y` 之前是 [un]assigned 的，当且仅当以下条件之一成立：

- `y` 是 `x` 的左侧直接子表达式，且 `v` 在 `x` 之前是 [un]assigned 的。
- `y` 是二元运算符的右侧操作数，且 `v` 在左侧操作数之后是 [un]assigned 的。
- `x` 是一个数组访问，`y` 是括号内的子表达式，且 `v` 在括号前的子表达式之后是 [un]assigned 的。
- `x` 是一个基本方法调用表达式，`y` 是该方法调用表达式中的第一个参数，且 `v` 在目标对象之后是 [un]assigned 的。
- `x` 是一个方法调用表达式或类创建表达式，`y` 是参数表达式，但不是第一个，且 `v` 在主表达式之后是 [un]assigned 的。
- `x` 是一个限定的类实例表达式，`y` 是参数表达式，但不是第一个，且 `v` 在主表达式之后是 [un]assigned 的。
- `x` 是一个方法调用表达式，`y` 是参数表达式，但不是第一个，且 `v` 在主表达式之后是 [un]assigned 的。
- `x` 是一个数组创建表达式，`y` 是数组初始化器，且 `v` 在维度表达式之后是 [un]assigned 的。
- `x` 是一个数组访问表达式，`y` 是括号内的子表达式，且 `v` 在括号前的子表达式之后是 [un]assigned 的。

# 16.2 确定赋值与语句

## 16.2.1 空语句

- 在发生在 `B` 中的的每一个赋值表达式 `V = e`, `V += e`, `V -= e`, `V *= e`, `V /= e`, `V %= e`, `V <<= e`, `V >>= e`, `V >>>= e`, `V &= e`, `V ^= e` 之后，`v` 都是确定赋值的。

- 在发生在 `B` 中的 `++V`, `--V`, `V++` 或 `V--` 之前，`v` 都是确定赋值的。

> 这些条件是反直觉的，需要解释。考虑简单赋值 `V = e`。如果 `v` 在 `e` 之后确定赋值，那么：
> * 赋值发生在死代码中，`V` 空白确定赋值。在这种情况下，赋值不会发生，我们可以假设 `V` 没有被赋值表达式赋值。
> * `v` 在 `e` 之前的表达式已经被赋值。在这种情况下，当前赋值会导致编译错误。
>
> 因此，我们可以得出结论：如果导致编译错误的程序满足这些条件，那么 `B` 中的任何对 `V` 的赋值实际上都不会发生。

## 16.2.2 块语句

- `v` 在块语句之后是 [un]assigned 的，当且仅当 `v` 在块语句的最后一个语句之后是 [un]assigned 的。
- `v` 在块语句的第一个语句之前是 [un]assigned 的，当且仅当 `v` 在块语句之前是 [un]assigned 的。
- `v` 在块语句中除第一个之外的语句之前是 [un]assigned 的，当且仅当 `v` 在紧邻的前一个语句之后是 [un]assigned 的。

## 16.2.3 局部类声明语句

- `v` 在局部类声明语句 (§14.3) 之后是 [un]assigned 的，当且仅当 `v` 在局部类声明语句之前是 [un]assigned 的。

## 16.2.4 局部变量声明语句

- 在不包含变量初始化器的局部变量声明语句 (§14.4) 之后，`v` 是 [un]assigned 的，如果 `v` 在局部变量声明语句之前是 [un]assigned 的。

- 在包含至少一个变量初始化器的局部变量声明语句之后，`v` 是确定赋值的，如果 `v` 在局部变量声明语句的最后一个初始化器之后是确定赋值的，或者声明中的最后一个初始化器位于声明 `v` 的声明符中。

- `v` 在包含至少一个变量初始化器的局部变量声明语句之后，`v` 是确定未赋值的，如果 `v` 在局部变量声明语句的最后一个初始化器之后是未赋值的，且声明中的最后一个初始化器不在声明 `v` 的声明符中。

- `v` 在局部变量声明语句的第一个变量初始化器之前是 [un]assigned 的，当且仅当 `v` 在局部变量声明语句之前是 [un]assigned 的。

- 在局部变量声明语句中除第一个变量初始化器之外的任何变量初始化器之前，`v` 是确定赋值的，如果 `v` 在之后是 `e` 左侧的变量初始化器或 `e` 左侧的初始化表达式位于声明 `v` 的声明符中。

- `V` 在局部变量声明语句中除第一个初始化器 `e` 之外之前确定未赋值，当且仅当 `V` 在 `e` 左侧的变量初始化器之后是确定未赋值，且 `e` 左侧的初始化表达式不在声明 `v` 的声明符中。

## 16.2.5 标记语句

- `V` 在标记语句 `L : s`（其中 `L` 是一个标记，§14.7）之后是 [un]assigned 的，当且仅当 `V` 在 `s` 之后是 [un]assigned，且 `V` 在每一个可能退出标记语句 `L : s` 的 `break` 语句之前都是 [un]assigned。

- `V` 在 `s` 之前是 [un]assigned，当且仅当 `V` 在 `L : s` 之前是 [un]assigned。

## 16.2.6 表达式语句

- `V` 在表达式语句 `e;` (§14.8) 之后是 [un]assigned 的，当且仅当它在 `e` 之后是 [un]assigned。

- `V` 在 `e` 之前是 [un]assigned，当且仅当它在 `e;` 之前是 [un]assigned。

## 16.2.7 `if` 语句

以下规则适用于语句 `if (e) S` (§14.9.1)：

- `V` 在 `if (e) S` 之后是 [un]assigned，如果 `V` 在 `S` 之后是 [un]assigned，且 `V` 在 `e` 为 `false` 时是 [un]assigned。

- `V` 在 `e` 之前是 [un]assigned，当且仅当 `V` 在 `if (e) S` 之前是 [un]assigned。

- `V` 在 `S` 之前是 [un]assigned，当且仅当 `V` 在 `e` 为 `true` 时是 [un]assigned。

以下规则适用于语句 `if (e) S else T` (§14.9.2)：

- `V` 在 `if (e) S else T` 之后是 [un]assigned，如果 `V` 在 `S` 之后是 [un]assigned，且 `V` 在 `T` 之后是 [un]assigned。

- `V` 在 `e` 之前是 [un]assigned，当且仅当 `V` 在 `if (e) S else T` 之前是 [un]assigned。

- `V` 在 `S` 之前是 [un]assigned，当且仅当 `V` 在 `e` 为 `true` 时是 [un]assigned。

- `V` 在 `T` 之前是 [un]assigned，当且仅当 `V` 在 `e` 为 `false` 时是 [un]assigned。

## 16.2.8 `assert` 语句

以下规则同时适用于语句 `assert e₁` 和语句 `assert e₁ : e₂` (§14.10)：

- `v` 在 `e₁` 之前是 [un]assigned 的，当且仅当 `v` 在 `assert` 语句之前是 [un]assigned 的。
- `v` 在 `assert` 语句之后是确定赋值的，当且仅当 `v` 在 `assert` 语句之前是确定赋值的。
- `v` 在 `assert` 语句之前是确定未赋值的，当且仅当 `v` 在 `e₁` 为 `true` 时的 `assert` 语句之前是确定未赋值的。

以下规则适用于语句 `assert e₁ : e₂`：

- `v` 在 `e₂` 之前是 [un]assigned 的，当且仅当 `v` 在 `e₁` 为 `false` 时是 [un]assigned 的。

## 16.2.9 `switch` 语句

- `v` 在 `switch` 语句 (§14.11) 之后是 [un]assigned 的，当且仅当以下条件均满足：
  - `switch` 块中存在 `default` 标记，或者 `v` 在 `switch` 表达式之后是 [un]assigned 的。
  - `switch` 块中没有不以块语句组开头的 `switch` 标记（即没有紧邻结束 `switch` 块的 `}` 之前的 `switch` 标记），或者 `v` 在 `switch` 表达式之后是 [un]assigned 的。
  - 或者 `switch` 块不包含任何块语句组，或者 `v` 在最后一个块语句组的最后一个块语句之后是 [un]assigned 的。
  - `v` 在每一个可能退出 `switch` 语句的 `break` 语句之前都是 [un]assigned 的。
- `v` 在 `switch` 表达式之前是 [un]assigned 的，当且仅当 `v` 在 `switch` 语句之前是 [un]assigned 的。

如果 `switch` 块包含至少一个块语句组，则以下规则也适用：

- `v` 在 `switch` 块中第一个块语句组的第一个块语句之前是 [un]assigned 的，当且仅当 `v` 在 `switch` 表达式之后是 [un]assigned 的。
- `v` 在 `switch` 块中除第一个之外的任何块语句组的第一个块语句之前是 [un]assigned 的，当且仅当 `v` 在 `switch` 表达式之后是 [un]assigned 的且 `v` 在上一个块语句之后是 [un]assigned 的。

## 16.2.10 `while` 语句

- `v` 在 `while (e) S` (§14.12) 之后是 [un]assigned 的，当且仅当 `v` 在 `e` 为 `false` 时是 [un]assigned 的，且 `v` 在每一个以 `while` 语句为 `break` 目标的 `break` 语句之前都是 [un]assigned 的。

- `v` 在 `e` 之前是确定赋值的，当且仅当 `v` 在 `while` 语句之前是确定赋值的。

- `v` 在 `e` 之前是确定未赋值的，当且仅当以下条件均满足：
  - `V` 在 `while` 语句之前是确定未赋值的。
  - 假设 `v` 在 `e` 之前是确定未赋值的，则 `v` 在 `S` 之后是确定未赋值的。
  - 假设 `v` 在 `e` 之前是确定未赋值的，则 `v` 在每一个以 `while` 语句为 `continue` 目标的 `continue` 语句之前都是确定未赋值的。

- `v` 在 `S` 之前是 [un]assigned 的，当且仅当 `v` 在 `e` 为 `true` 时是 [un]assigned 的。

## 16.2.11 `do` 语句

- `v` 在 `do S while (e)` (§14.13) 之后是 [un]assigned 的，当且仅当 `v` 在 `e` 为 `false` 时是 [un]assigned 的，且 `v` 在每一个以 `do` 语句为 `break` 目标的 `break` 语句之前都是 [un]assigned 的。

- `v` 在 `S` 之前是确定赋值的，当且仅当 `v` 在 `do` 语句之前是确定赋值的。

- `v` 在 `S` 之前是确定未赋值的，当且仅当以下条件均满足：
  - `V` 在 `do` 语句之前是确定未赋值的。
  - 假设 `v` 在 `S` 之前是确定未赋值的，则 `v` 在 `e` 为 `true` 时是确定未赋值的。

- `v` 在 `e` 之前是 [un]assigned 的，当且仅当 `v` 在 `S` 之后是 [un]assigned 的且 `v` 在每一个以 `do` 语句为 `continue` 目标的 `continue` 语句之前都是 [un]assigned 的。

## 16.2.12 `for` 语句

这里的规则涵盖了基本的 `for` 语句 (§14.14.1)。由于增强型 `for` 语句 (§14.14.2) 是通过翻译为基础 `for` 语句实现的，因此不需要为其提供特殊规则。

- `v` 在 `for` 语句之后是 [un]assigned 的，当且仅当以下两个条件均满足：
  - 或者条件表达式不存在，或者 `v` 在条件表达式为 `false` 时是 [un]assigned 的。
  - `v` 在每一个以 `for` 语句为 `break` 目标的 `break` 语句之前都是 [un]assigned 的。
- `v` 在 `for` 语句的初始化部分之前是 [un]assigned 的，当且仅当 `v` 在 `for` 语句之前是 [un]assigned 的。
- `v` 在 `for` 语句条件部分之前是确定赋值的，当且仅当 `v` 在初始化部分之后是确定赋值的。
- `v` 在 `for` 语句条件部分之前是确定未赋值的，当且仅当以下条件均满足：
  - `v` 在初始化部分之后是确定未赋值的。
  - 假设 `v` 在条件部分之前是确定未赋值的，则 `v` 在增量部分之后是确定未赋值的。
- `v` 在包含的语句之前是 [un]assigned 的，当且仅当：
  - 存在条件表达式且 `v` 在条件表达式为 `true` 时是 [un]assigned 的。
  - 或者不存在条件表达式且 `v` 在条件部分之前是 [un]assigned 的。
- `v` 在 `for` 语句增量部分之前是 [un]assigned 的，当且仅当 `v` 在包含的语句之后是 [un]assigned 的且 `v` 在每一个以 `for` 语句为 `continue` 目标的 `continue` 语句之前都是 [un]assigned 的。

### 16.2.12.1 `for` 语句的初始化部分

- 如果 `for` 语句的初始化部分是局部变量声明，则适用 §16.2.4。

- 否则，如果初始化部分为空，则 `v` 在初始化部分之后是 [un]assigned 的，当且仅当 `v` 在初始化部分之前是 [un]assigned 的。

- 否则，适用三个规则：
  - `v` 在初始化部分之后是 [un]assigned 的，当且仅当 `v` 在初始化部分中的最后一个语句之后是 [un]assigned 的。
  - `v` 在初始化部分中的第一个语句之前是 [un]assigned 的，当且仅当 `v` 在初始化部分之前是 [un]assigned 的。
  - `v` 在初始化部分中除第一个之外的语句之前是 [un]assigned 的，当且仅当 `v` 在紧邻的语句之后是 [un]assigned 的。

### 16.2.12.2 `for` 语句的增量部分

- 如果 `for` 语句的增量部分为空，则 `v` 在增量部分之后是 [un]assigned 的，当且仅当 `v` 在增量部分之前是 [un]assigned 的。

- 否则，适用三个规则：
  - `v` 在增量部分之后是 [un]assigned 的，当且仅当 `v` 在增量部分中的最后一个语句之后是 [un]assigned 的。
  - `v` 在增量部分中的第一个语句之前是 [un]assigned 的，当且仅当 `v` 在增量部分之前是 [un]assigned 的。
  - `v` 在增量部分中除第一个之外的语句之前是 [un]assigned 的，当且仅当 `v` 在紧邻的语句之后是 [un]assigned 的。

## 16.2.13 `break`、`continue`、`return` 和 `throw` 语句

- 根据习惯，我们说 `v` 在任何 `break`、`continue`、`return` 或 `throw` 语句之后都是 [un]assigned 的（§14.15、§14.16、§14.17、§14.18）。

> 变量在语句或表达式之后“未赋值”的概念实际上是指“在语句或表达式正常完成后未赋值”。因为 `break`、`continue`、`return` 或 `throw` 语句永远不会正常完成，因此它们空值满足这一概念。

- 在带有表达式 `e` 的 `return` 语句或带有表达式的 `throw` 语句中，`v` 在 `e` 之前是 [un]assigned 的，当且仅当 `v` 在 `return` 或 `throw` 语句之前是 [un]assigned 的。

## 16.2.14 `synchronized` 语句

- `v` 在 `synchronized (e) S` (§14.19) 之后是 [un]assigned 的，当且仅当 `v` 在 `S` 之后是 [un]assigned。

- `v` 在 `e` 之前是 [un]assigned 的，当且仅当 `v` 在语句 `synchronized (e) S` 之前是 [un]assigned 的。

- `v` 在 `S` 之前是 [un]assigned 的，如果 `v` 在 `e` 之后是 [un]assigned 的。

## 16.2.15 `try` 语句

这些规则适用于每一个 `try` 语句 (§14.20)，无论其是否包含 `finally` 块：

- `v` 在 `try` 块之前是 [un]assigned 的，当且仅当 `v` 在 `try` 语句之前是 [un]assigned 的。
- 如果 `v` 在 `try` 块之前是确定赋值，则 `v` 在 `catch` 块之前是确定赋值。
- 如果满足以下所有条件，则 `v` 在 `catch` 块之前是确定未赋值的：
  - `v` 在 `try` 块之后是确定未赋值的。
  - `v` 在属于 `try` 块的每一个 `return` 语句之前都是确定未赋值的。
  - 在属于 `try` 块的每一个形式为 `throw e` 的语句中，`v` 在 `e` 之后都是确定未赋值的。
  - `v` 在 `try` 块中发生的每一个 `assert` 语句之后都是确定未赋值的。
  - `v` 在每一个属于 `try` 块的 `break` 语句之前，且该 `break` 语句的跳转目标包含（或就是）`try` 语句，是确定未赋值的。
  - `v` 在每一个属于 `try` 块的 `continue` 语句之前，且该 `continue` 语句的跳转目标包含 `try` 语句，是确定未赋值的。

如果一个 `try` 语句没有 `finally` 块，则此规则也适用：

- `v` 在 `try` 语句之后是 [un]assigned 的，当且仅当 `v` 在 `try` 块之前是 [un]assigned 的且 `v` 在 `try` 语句中的每一个 `catch` 块之后都是 [un]assigned 的。

如果一个 `try` 语句包含 `finally` 块，则以下规则也适用：

- `v` 在 `try` 语句之后是确定赋值的，当且仅当满足以下至少一个条件：
  - `v` 在 `try` 块之后是确定赋值且 `v` 在每一个 `catch` 块之后都是确定赋值。
  - `v` 在 `finally` 块之后是确定赋值。
- `v` 在 `try` 语句之后是确定未赋值的，当且仅当 `v` 在 `finally` 块之后是确定未赋值的。
- `v` 在 `finally` 块之前是确定赋值的，当且仅当 `v` 在 `try` 语句之前是确定赋值。

- `V` 在 `finally` 块之前是确定未赋值的，当且仅当满足以下所有条件：
  - `V` 在 `try` 块之后是确定未赋值的。
  - `V` 在属于 `try` 块的每一个 `return` 语句之前都是确定未赋值的。
  - `V` 在属于 `try` 块的每一个形式为 `throw e` 的语句中，`V` 在 `e` 之后都是确定未赋值的。
  - `V` 在 `try` 块中发生的每一个 `assert` 语句之后都是确定未赋值的。
  - `V` 在每一个属于 `try` 块的 `break` 语句之前，且该 `break` 语句的跳转目标包含（或就是）`try` 语句，是确定未赋值的。
  - `V` 在每一个属于 `try` 块的 `continue` 语句之前，且该 `continue` 语句的跳转目标包含 `try` 语句，是确定未赋值的。
  - `V` 在 `try` 语句的每一个 `catch` 块之后都是确定未赋值的。

## 16.3 确定赋值与参数

- 方法或构造函数 (§8.4.1, §8.8.1) 的形式参数 `v` 在方法或构造函数的体之前是确定赋值的（而且不是确定未赋值）。
- `catch` 子句 (§14.20) 的异常参数 `v` 在 `catch` 子句的体之前是确定赋值的（而且不是确定未赋值）。

## 16.4 确定赋值与数组初始化器

- `v` 在空数组初始化器 (§10.6) 之后是 [un]assigned 的，当且仅当 `v` 在空数组初始化器之前是 [un]assigned 的。
- `v` 在非空数组初始化器之后是 [un]assigned 的，当且仅当 `v` 在数组初始化器中最后一个变量初始化器之后是 [un]assigned 的。
- `v` 在数组初始化器第一个变量初始化器之前是 [un]assigned 的，当且仅当 `v` 在数组初始化器之前是 [un]assigned 的。
- `v` 在数组初始化器中任何变量初始化器 `e` 之前是 [un]assigned 的，当且仅当 `v` 在数组初始化器中 `e` 左侧的变量初始化器之后是 [un]assigned 的。

## 16.5 确定赋值与枚举常量

确定变量在枚举常量 (§8.9.1) 之前何时赋值或未赋值的规则见 §16.8。

> 这是因为枚举常量本质上是一个静态 `final` 字段 (§8.3.1.1, §8.3.1.2)，它通过类实例创建 (§15.9) 进行初始化。

- `v` 在 `v` 作用范围内声明的无参数枚举常量的类体声明之前是确定赋值的，则 `v` 在枚举常量之前是确定赋值的。
- `v` 在 `v` 作用范围内声明的带参数枚举常量的类体声明之前是确定赋值的，则 `v` 在枚举常量的最后一个参数表达式之后是确定赋值的。

枚举常量类体内任何构造的确定赋值/未赋值状态遵循类的常规规则。

- `v` 在枚举常量第一个参数之前是 [un]assigned 的，当且仅当它在枚举常量之前是 [un]assigned 的。
- `v` 在 `y`（枚举常量的一个参数，但不是第一个）之前是 [un]assigned 的，当且仅当 `v` 在 `y` 左侧的参数之后是 [un]assigned 的。

## 16.6 确定赋值与匿名类

- `v` 在 `v` 作用范围内声明的匿名类声明 (§15.9.5) 之前是确定赋值的，则 `v` 在声明匿名类的类实例创建表达式之后是确定赋值的。

> 显然，如果匿名类是由枚举常量隐式定义的，则适用 §16.5 的规则。

## 16.7 确定赋值与成员类型

设 `c` 为一个类，设 `v` 为一个空 `final` 成员。那么：
- `v` 在 `c` 的成员类型之前是确定赋值的（而且不是确定未赋值）。

设 `c` 为 `v` 作用范围内声明的类。那么：
- 如果 `v` 在 `c` 的声明之前是确定赋值，则 `v` 在 `c` 的成员类型 (§8.5) 之前是确定赋值。

## 16.8 确定赋值与静态初始化器

设 `c` 为 `v` 作用范围内声明的类。那么：
- 如果 `v` 在 `c` 的声明之前是确定赋值，则 `v` 在 `c` 的枚举常量 (§8.9) 或静态初始化器 (§8.3) 之前是确定赋值。

> 注意，没有规则允许我们得出 `v` 在静态初始化器之前是确定未赋值的结论。我们可以非正式地认为 `v` 在任何静态初始化器之前未赋值，但不需要这样的规则。

设 `c` 为一个类，设 `v` 为在 `c` 中声明的空静态 `final` 字段。那么：
- `v` 在最左侧的枚举常量、静态初始化器之前是确定未赋值的（而且是确定赋值）。
- 如果 `v` 在 `c` 前一个枚举常量或静态初始化器之后是 [un]assigned 的，则 `v` 在 `c` 除最左侧外的枚举常量、静态初始化器之前是 [un]assigned 的。

设 `c` 为一个类，设 `v` 为在父类中声明的空静态 `final` 字段。那么：
- `v` 在 `c` 的每一个枚举常量之前是确定赋值（而且不是确定未赋值）。
- `v` 在 `c` 的每一个静态初始化器的体之前是确定赋值（而且不是确定未赋值）。
- `v` 在 `c` 的每一个静态初始化器之前是确定赋值（而且不是确定未赋值）。

## 16.9 确定赋值、构造函数与实例初始化器

设 `c` 为 `v` 作用范围内声明的类。那么：
- 如果 `v` 在 `c` 的声明之前是确定赋值，则 `v` 在 `c` 的实例初始化器 (§8.3) 之前是确定赋值。

> 注意，没有规则允许我们得出 `v` 在实例初始化器之前是确定未赋值的结论。我们可以非正式地认为 `v` 在任何实例初始化器之前未赋值，但不需要这样的规则。

设 `c` 为一个类，设 `v` 为 `c` 中声明的空 `final` 非静态成员字段。那么：
- `v` 在 `c` 最左侧的实例初始化器 (§8.6) 或变量初始化器之前是确定未赋值（而且不是确定赋值）。
- 如果 `v` 在 `c` 前一个实例初始化器或变量初始化器之后是 [un]assigned 的，则 `v` 在 `c` 除最左侧外的实例初始化器或变量初始化器之前是 [un]assigned 的。

以下规则适用于类 `c` 的构造函数 (§8.8.7)：

- `v` 在备用构造函数调用 (§8.8.7.1) 之后是确定赋值（而且不是确定未赋值）。
- `v` 在显式或隐式父类构造函数调用 (§8.8.7.1) 之前是确定未赋值（而且不是确定赋值）。
- 如果 `c` 没有实例初始化器或变量初始化器，则 `v` 在显式或隐式父类构造函数调用之后不是确定赋值（而且是确定未赋值）。
- 如果 `c` 至少有一个实例初始化器或变量初始化器，则 `v` 在显式或隐式父类构造函数调用之后是 [un]assigned 的，当且仅当 `v` 在 `c` 最右侧的实例初始化器或变量初始化器之后是 [un]assigned 的。

设 `c` 为一个类，设 `v` 为其父类中声明的空 `final` 成员字段。那么：
- `v` 在 `c` 的构造函数或实例初始化器的体块之前是确定赋值的（而且不是确定未赋值）。
- `v` 在 `c` 的每个实例变量初始化器之前被确定赋值（而且不是被确定未赋值的）。

# 第 17 章 线程与锁

## 17.1 同步

虽然前面的章节中的大部分讨论只关注代码单次执行一条语句或表达式的行为（即由单个线程执行），但 Java 虚拟机可以同时支持多个执行线程。这些线程独立地执行代码，对共享主内存中的值和对象进行操作。线程可以通过拥有多个硬件处理器、对单个硬件处理器进行时间分片，或对多个硬件处理器进行时间分片来支持。

线程由 `Thread` 类表示。用户创建线程的唯一方法是创建该类的对象；每个线程都与这样一个对象关联。当在相应的 `Thread` 对象上调用 `start()` 方法时，线程将启动。

线程的行为（特别是在没有正确同步的情况下）可能会是令人困惑且违背直觉的。本章描述了多线程程序的语义；它包含了对于由多个线程更新的共享内存，其读取操作可能看到的值的规则。由于该规范与不同硬件架构的内存模型相似，这些语义被称为 Java 编程语言内存模型。在没有歧义的情况下，我们简单地将这些规则称为“内存模型”。

这些语义并没有规定多线程程序应该如何执行。相反，它们描述了多线程程序允许表现的行为。任何只产生允许行为的执行策略都是可接受的执行策略。

Java 编程语言提供了多种线程间通信的机制。这些方法中最基本的是同步，它是通过监视器实现的。Java 中的每个对象都关联一个监视器，线程可以对其进行锁定或解锁。一次只有一个线程可以持有监视器的锁。任何其他尝试锁定该监视器的线程都会被阻塞，直到它们获得该监视器的锁。一个线程可以多次锁定特定的监视器；每次解锁都会撤销一次锁定操作的效果。

`synchronized` 语句 (§14.19) 计算一个对象的引用；然后它尝试对该对象的监视器执行锁定操作，在锁定操作成功完成之前不会继续执行。在执行锁定操作后，将执行 `synchronized` 语句体。如果语句体的执行无论是正常还是异常地完成，都会会自动在该监视器上执行解锁操作。

`synchronized` 方法 (§8.4.3.6) 在被调用时会自动执行锁定操作；在锁定操作成功完成之前不会执行方法体。如果该方法是实例方法，它将锁定与调用它的实例关联的监视器（在方法体执行期间，该对象将被称为 `this`）。如果该方法是静态的，它将锁定与代表方法所在类的 `Class` 对象关联的监视器。如果方法体的执行无论是正常还是异常地完成，都会在该监视器上自动执行解锁操作。

Java 编程语言既不防止也不要求对死锁条件进行检测。线程持有（直接或间接持有）多个对象锁的程序应该使用传统技术（为了避免死锁，必要时可以创建不会死锁的高级锁原语）。

其他机制，例如 `volatile` 变量的读写以及 `java.util.concurrent` 包中类的使用，提供了同步的替代性方法。

## 17.2 等待集与通知

每个对象除了关联一个监视器外，还关联一个等待集。等待集是线程的集合。

当对象首次被创建时，它的等待集是空的。向等待集添加线程和从等待集移除线程的基本操作是原子的。等待集的操作完全通过 `Object.wait`、`Object.notify` 和 `Object.notifyAll` 方法进行。

等待集的操作还受到线程的中断状态以及 `Thread` 类中处理中断的方法的影响。此外，`Thread` 类用于睡眠和加入其他线程的方法具有源自这些等待和通知动作的属性。

### 17.2.1 等待

等待动作发生在调用 `wait()` 或计时形式的 `wait(long milliseconds, int nanosecs)` 时。

> 调用参数为零的 `wait(long milliseconds)` 或带有两个零值参数的 `wait(long milliseconds, int nanosecs)` 等同于调用 `wait()`。

如果线程从 `wait` 返回时没有抛出 `InterruptedException`，则它正常从等待返回。

令 `t` 为在对象 `m` 上执行 `wait` 方法的线程，令 `n` 为线程 `t` 在 `m` 上执行且未被解锁操作匹配的锁定操作次数。发生以下操作之一：

- 如果 `n` 为零（即线程 `t` 尚未拥有目标 `m` 的锁），则抛出 `IllegalMonitorStateException`。
- 如果是计时等待且 `nanosecs` 参数不在 0-999999 范围内，或 `milliseconds` 参数为负数，则抛出 `IllegalArgumentException`。
- 如果线程 `t` 被中断，则抛出 `InterruptedException` 并将 `t` 的中断状态设置为 `false`。
- 否则，发生以下序列：
  1. 线程 `t` 被添加到对象 `m` 的等待集，并在 `m` 上执行 `n` 次解锁操作。
  2. 在线程 `t` 从 `m` 的等待集中移除之前，它不执行任何后续指令。线程可能由于以下任何操作被从等待集中移除，并在之后的某个时间恢复：
     - 在 `m` 上执行了 `notify` 动作且 `t` 被选中从等待集中移除。
     - 在 `m` 上执行了 `notifyAll` 动作。
     - 对 `t` 执行了中断动作。
     - 如果是计时等待，在等待动作开始至少 `millis` 毫秒加上 `nansecs` 纳秒后，发生一个将 `t` 从 `m` 等待集移除的内部动作。
     - 实现类的内部动作。实现被允许（但不鼓励）执行“虚假唤醒”，即从等待集中移除线程并使其得以恢复。

> 注意，这一规定要求了 Java 编码实践：在循环中使用 `wait`，并在线程正在等待的某个逻辑条件成立时才终止。

每个线程必须对导致其从等待集中移除的事件确定一个顺序。这不需要与其他排序一致，但线程的行为必须像这些事件按该顺序发生一样。

例如，如果线程 `t` 在 `m` 的等待集中，且发生了对 `t` 的中断和对 `m` 的通知，那么 `t` 必须对这些事件确定一个顺序。如果认为中断先发生并抛出 `InterruptedException`，则 `m` 的等待集中的其他线程（如果在通知时存在）必须接收该通知。如果通知被认为先发生，则 `t` 最终会在中断仍挂起的情况下正常从 `wait` 返回。

3. 线程在 `m` 上执行 `n` 次锁定操作。

4. 如果线程 `t` 在第 2 步由于中断从 `m` 的等待集中移除，则将 `t` 的中断状态设置为 `false`，`wait` 方法抛出 `InterruptedException`。

### 17.2.2 通知

通知动作发生在调用 `notify` 和 `notifyAll` 方法时。

令 `t` 为在对象 `m` 上执行这些方法的线程，令 `n` 为线程 `t` 在 `m` 上执行且未被解锁操作匹配的锁定操作次数。发生以下操作之一：

- 如果 `n` 为 0，则抛出 `IllegalMonitorStateException`。

  这种情况发生在线程 `t` 尚未拥有目标 `m` 锁的情况下。

- 如果 `n` 大于 0 且这是一个 `notify` 动作，如果 `m` 的等待集不为空，则选择一个 `m` 当前等待集中的成员 `u` 并将其从等待集中移除。

  无法保证被选中的等待集中的哪一个线程。这种从等待集中移除 `u` 的操作使得 `u` 能够在等待动作中恢复。但请注意，在 `t` 完全释放对 `m` 的监视器之前，`u` 在恢复后执行的监视器锁操作将无法成功。

- 如果 `n` 大于 0 且这是一个 `notifyAll` 动作，则所有线程都将从 `m` 的等待集中移除并得以恢复。

  但请注意，在恢复等待期间，一次只有一个线程会锁定恢复期间所需的监视器。

### 17.2.3 中断

交互发生在调用 `Thread.interrupt` 以及相应定义的调用它的方法时，例如 `ThreadGroup.interrupt`。

令 `t` 为调用某个线程 `u` 的 `u.interrupt` 的线程，其中 `t` 和 `u` 可能是同一个。此动作会导致 `u` 的中断状态被设置。

此外，如果存在某个对象 `m` 的等待集包含 `u`，则 `u` 将从 `m` 的等待集中被移除。这使得 `u` 能够在等待动作中恢复，在这种情况下，该等待将在重新锁定 `m` 的监视器后抛出 `InterruptedException`。

对 `Thread.isInterrupted` 的调用确定线程的中断状态。静态方法 `Thread.interrupted` 可以由线程调用以观察并清除其自身的中断状态。

### 17.2.4 等待、通知与中断的交互

上述规范允许我们确定与等待、通知和中断交互相关的若干属性。

如果一个线程在等待时既被通知又被中断，它可能：

- 从 `wait` 正常返回，但仍有一个待处理的中断（换句话说，调用 `Thread.interrupted` 将返回 `true`）。
- 通过抛出 `InterruptedException` 从 `wait` 返回。

> 线程可能不会重置其中断状态并从 `wait` 调用正常返回。

同样，通知不会因为中断而丢失。假设线程集合 `s` 处于对象 `m` 的等待集中，另一个线程对 `m` 执行 `notify`。那么：

- `s` 中的至少有一个线程必须从 `wait` 正常返回，或者
- `s` 中的所有线程都必须通过抛出 `InterruptedException` 退出等待。

请注意，如果一个线程既被中断又通过通知唤醒，且该线程通过抛出 `InterruptedException` 从等待返回，那么等待集中的其他线程必须被通知。

## 17.3 睡眠与让

`Thread.sleep` 导致当前执行的线程睡眠指定的持续时间（临时停止执行），这取决于系统计时器和调度器的精度和准确性。线程不会丢失任何监视器的所有权，执行的恢复将取决于调度以及执行该线程的处理器的可用性。

重要的是，`Thread.sleep` 和 `Thread.yield` 均没有任何同步语义。特别是，编译器在调用 `Thread.sleep` 或 `Thread.yield` 之前不需要将寄存器中的缓存刷新到共享内存，编译器也不需要在调用 `Thread.sleep` 或 `Thread.yield` 之后重新加载寄存器中的值。

例如，在以下（错误的）代码段中，假设 `this.done` 是一个非 `volatile` 的布尔字段：

```java
while (!this.done)
    Thread.sleep(1000);
```

编译器可以自由地将循环优化为：

```java
if (!this.done)
    while (true)
        Thread.sleep(1000);
```



```
while (!this.done)
  Thread.sleep(1000);
```

编译器可以只读取一次字段`this.done`，并在循环每次执行中重用缓存的值。这意味着即使另一个线程更改了`this.done`的值，循环永远不会结束。

## 17.4 内存模型

内存模型描述了在给定程序和该程序的执行轨迹的情况下，该执行轨迹是否为程序的合法执行。Java 编程语言内存模型通过检查执行轨迹中的每次读取，并检查该读取观察到的写入是否根据某些规则有效来工作。

内存模型描述了程序可能的行为。实现可以自由产生它喜欢的任何代码，只要程序的所有执行产生的结果是内存模型可以预测的即可。

这为实现者执行无数代码变换提供了极大的自由，包括动作的重排序和不必要的同步的移除。

### 示例 17.4-1. 同步错误的程序可能表现出意外的行为

Java 编程语言的语义允许编译器和微处理器执行优化，这些优化可能与同步错误的代码发生交互，从而产生看似悖论的行为。以下是同步错误的程序可能表现出意外行为的一些示例。

考虑表 17.4-A 所示的示例程序。该程序使用了局部变量`r1`、`r2`以及共享变量`A`和`B`。初始时，`A = B = 0`。

表 17.4-A. 由语句重排序导致的意外结果 - 原始代码
| 线程 1 | 线程 2 |
|---|---|
| 1: r2 = A; | 3: r1 = B; |
| 2: B = 1; | 4: A = 2; |

结果`r2 == 2`和`r1 == 1`似乎是不可能的。直觉上，指令 1 或 3 应该先执行。如果指令 1 先执行，它不应该看到指令 4 的写入；如果指令 3 先执行，它不应该看到指令 2 的写入。

如果某个执行显示了这种行为，我们就知道指令 4 先于指令 1，1 先于指令 2，2 先于指令 3。这表面上是荒谬的。

然而，编译器被允许在线程内部重排序指令，只要这不影响该线程的执行。如果指令 1 与指令 2 重排序（如表 17.4-B 所示），那么很容易看出`r2 == 2`和`r1 == 1`的结果是如何产生的。

表 17.4-B. 由语句重排序导致的意外结果 - 有效编译器转换
| 线程 1 | 线程 2 |
|--- |--- |
| B = 1; | r1 = B; |
| r2 = A; | A = 2; |

对某些程序员来说，这种行为可能是“损坏的”。但应该注意，这段代码同步不当：

- 一个线程中的写入，
- 另一个线程对同一变量的读取，
- 写入和读取没有通过同步排序。

这种情况是数据竞态（17.4.5）的一个示例。当代码包含数据竞态时，往往会出现违反直觉的结果：

几种机制可以产生表 17.4-B 中的重排序。Java 虚拟机实现中的即时编译器可能会重新排列代码，或者处理器可能会。此外，运行 Java 虚拟机实现的架构的内存层次可能会使代码看起来被重排序了。在本章中，我们将任何可以重排序代码的东西称为编译器。

另一个意外结果的示例可以见表 17.4-C。初始时，`p = q`且`p.x = 0`。该程序也是同步错误的；它没有显示任何顺序。

表 17.4-C. 由前向替换导致的意外结果
| 线程 1 | 线程 2 |
|---|---|
| r1 = p; | r3 = q; |
| r2 = p.x; | r4 = p.x; |
| p.x = 3; | |
| | r5 = p.x; |

如果编译器决定重用`r2`的值作为`r5`，那么`r2`和`r5`将为 0，而`r4`将为 3。从程序员的角度来看，存储在`p.x`处的值从 0 变为 3 然后又回了 0。

## 17.4.1 共享变量

可以在线程之间共享的内存被称为共享内存或堆内存。

所有的实例字段、静态字段和数组元素都存储在堆内存中。在本章中，我们使用“变量”一词来泛指字段和数组元素。

局部变量（§14.4）、正式方法参数（§8.4.1）以及异常处理器参数（§14.20）永远不会在线程之间共享，且不受内存模型的影响。

对同一个变量的两次访问（读取或写入），如果其中至少一次访问是写入操作，则称这两个访问是冲突的。

## 17.4.2 动作

线程间动作是由一个线程执行，但可以被另一个线程检测到或直接影响的动作。程序可能会执行以下几种类型的线程间动作：

- **读取（普通，或非 volatile）**。读取变量。
- **写入（普通，或非 volatile）**。写入变量。
- 同步动作，包括：
  - **volatile 读取**。对变量进行 volatile 读取。
  - **volatile 写入**。对变量进行 volatile 写入。
  - **锁定 (Lock)**。锁定监视器。
  - **解锁 (Unlock)**。解锁监视器。
  - 线程的（合成）第一个和最后一个动作。
  - 启动线程或检测到线程已终止的动作（§17.4.4）。
- **外部动作 (External Actions)**。外部动作是在执行外部可能观测的动作，并且其结果基于执行之外的环境。
- **线程分散动作（§17.4.9）**。线程分散动作仅由处于无限循环中的线程执行，且在该循环中没有执行任何内存、同步或外部动作。如果一个线程执行了线程分散动作，随后将紧跟无限数量的线程分散动作。

引入线程分散动作是为了建模一个线程如何导致所有其他线程停滞且无法进展。

本规范仅关注线程间动作。我们不需要关注线程内动作（例如，将两个局部变量相加并将结果存储在第三个局部变量中）。如前所述，所有线程都需要遵守 Java 程序正确的线程内语义。我们通常简称为地将线程间动作称为*动作（actions）*。

动作`a`由元组`<t, k, v, u>`描述，其中包含：

- `t` - 执行动作的线程
- `k` - 动作的类型
- `v` - 动作涉及的变量或监视器。

对于锁定动作，`v`是被锁定的监视器；对于解锁动作，`v`是被解锁的监视器。

如果该动作是（volatile 或非 volatile）读取，`v`是被读取的变量。

如果该动作是（volatile 或非 volatile）写入，`v`是被写入的变量。

- `u` - 动作的任意唯一标识符

外部动作元组包含一个额外的组件，其中包含执行动作的线程所感知的外部动作结果。这是关于动作成功或失败的信息，以及动作读取的任何值。

外部动作的参数（例如，哪些字节被写入哪个套接字）是外部动作元组的一部分。这些参数是由线程内的其他动作设置的，可以通过检查线程内语义来确定。它们在内存模型中没有被式讨论。

在非终止的执行中，并不是所有的外部动作都是可观测的。非终止的执行和可观测动作在§17.4.9中进行了讨论。

## 17.4.3 程序和程序顺序

在每个线程`t`执行的所有线程间动作中，`t`的程序顺序是一个全序，它反映了根据`t`的线程内语义执行这些动作的顺序。

## 17.4.4 内存模型 线程与锁

一组动作是顺序一致的，如果所有动作都发生在一个与程序顺序一致的全序（执行顺序）中，并且此外，变量`v`的每个读取`r`都能看到由写入操作`w`对`v`写入的值，且满足以下条件：

- `w`在执行顺序中位于`r`之前，
- 不存在另一个写入操作`w'`，使得在执行顺序中`w`位于`w'`之前，且`w'`又在`r`之前。

顺序一致性是对程序执行中可见性和排序提供的一项非常强的保证。在顺序一致的执行中，所有单独的动作（如读取和写入）存在一个全序，该全序与程序顺序一致，且每个单独动作都是原子的，并对每个线程立即可见。

如果程序没有数据竞态，那么该程序的所有执行都将是顺序一致的。

顺序一致性和/或无数据竞态允许处理所有由于需要被原子感知但实际上并非原子的操作组而产生的错误。

> 如果我们使用顺序一致性作为我们的内存模型，我们所使用的许多编译器优化和优化将是非法的。例如，在表 17.4-C 的轨迹中，一旦发生了对`p.x`写入 3，后续对该位置的读取将被要求看到该值。

## 17.4.5 同步顺序

每次执行都有一个同步顺序。同步顺序是执行中所有同步动作的全序。对于每个线程`t`，`t`中同步动作（§17.4.2）的同步顺序与`t`的程序顺序（§17.4.3）一致。

同步动作在动作上诱导了“同步（synchronized-with）”关系，定义如下：

- 对监视器`m`的解锁动作与对`m`的所有后续锁定动作同步（其中“后续”根据同步顺序定义）。
- 对`volatile`变量`v`（§8.3.1）的写入与任何线程对`v`的后续读取同步（其中“后续”根据同步顺序定义）。
- 启动线程的动作与该线程的第一个动作同步。

每个变量写入默认值（零、false 或 null）与每个线程的第一个动作同步。

尽管在包含它的对象的分配之前向变量写入默认值似乎有点奇怪，但概念上每个对象在程序启动时以其默认值创建。

线程`T1`的最后一个动作与另一个线程`T2`检测到`T1`已终止的动作同步。

```
T2 可以通过调用 T1.isAlive() 或 T1.join() 实现这一点。
```

- 如果`T1`中断了`T2`，`T1`的中断与其他任何线程（包括`T2`）确定`T2`被中断的点（通过抛出`InterruptedException`或调用`Thread.interrupted()`）同步。

同步边的源称为释放（release），终点称为获取（acquire）。

## 17.4.6 发生于顺序

两个动作可以通过“发生于”关系进行排序。如果一个动作发生于另一个动作之前，则前者对后者可见并排在后者之前。

如果我们有两个动作`x`和`y`，我们写入`hb(x, y)`表示`x`发生于`y`。

- 如果`x`和`y`是同一线程的动作且`x`在程序顺序上优于`y`，则`hb(x, y)`。
- 从对象构造函数的结束到该对象的终结器（§12.6）开始之间存在一个发生于边。
- 如果动作`x`与后续动作`y`同步，那么我们也有`hb(x, y)`。
- 如果`hb(x, y)`且`hb(y, z)`，则`hb(x, z)`。

`Object`类（§17.2.1）的`wait`方法与其关联的锁定和解锁动作相关；它们的发生于关系是由其关联的动作定义的。

应该注意到，两个动作之间存在发生于关系并不意味着它们在实现中必须按顺序发生。如果重排序产生的结果与合法执行一致，则它不是非法的。

例如，对线程构造的对象的每个字段写入默认值的操作并不一定必须在该线程开始之前发生，只要没有读取操作观察到这一事实即可。

具体来说，如果两个动作共享一个*先发生于*（happens-before）关系，那么对于任何不与它们共享该*先发生于*关系的代码来说，它们并不一定必须看起来是按顺序发生的。例如，一个线程中与另一个线程的读取操作构成数据竞态的写入操作，其发生顺序相对于这些读取操作可能是无序的。

*先发生于*关系定义了数据竞态发生的时机。

一个同步边集合`S`是*充分的*（sufficient），如果且它是一个最小集合，使得`S`与程序顺序（program order）的传递闭包能够确定执行过程中所有的*先发生于*的边。该集合是唯一的。

根据上述定义可以得出结论：

- 监视器的解锁操作（unlock）*先发生于*该监视器随后的每次锁操作（lock）。
- 对`volatile`（volatile）字段（§17.8.1.4）的写入*先发生于*对该字段随后的每次读取。
- 对线程调用`start()`*先发生于*被启动线程中的任何动作。
- 某个线程中的所有动作*先发生于*任何其他线程成功从该线程的`join()`中返回。
- 任何对象的默认初始化*先发生于*程序中的任何其他动作（默认写入除外）。

当一个程序包含两个没有被*先发生于*关系排序的冲突访问（§17.4.1）时，称该程序包含一个*数据竞态*（data race）。

除线程间检查之外的操作语义，例如数组长度的读取（§10.7）、检查类型转换的执行（§5.5, §15.16）以及虚拟方法的调用，不会直接受到数据竞态的影响。

> 因此，数据竞态不会导致错误的行为，例如返回数组错误的长度。

如果一个程序是*正确同步的*（correctly synchronized），当且仅当所有顺序一致的执行过程都不包含数据竞态。

如果一个程序是正确同步的，那么该程序的所有执行看起来将是顺序一致的（§17.4.3）。

这对程序员来说是一个极强有力的保证。程序员不需要通过推演重排序来确定他们的代码是否包含数据竞态。在确定代码是否正确同步时，他们也不需要推演重排序。一旦确定代码是正确同步的，程序员就不需要担心重排序会影响其代码。

程序必须正确同步，以避免在代码重排序时可能观察到的类反直觉行为。使用正确的同步不能确保程序的整体行为是正确的。然而，它允许程序员以简单的方式推演程序的可能行为；正确同步程序的行为对可能的重排序的依赖程度要低得多。如果没有正确同步，可能会出现奇怪、困惑且反直觉的行为。

我们说，对变量的读取`r`被允许观察到对变量`v`的写入`w`，如果执行轨迹的*先发生于*偏序满足：

- `r`未排序在`w`之前（即并非`hb(r, w)`成立），且
- 不存在对`v`的交错写入`w'`（即不存在写入`w'`使得`hb(w', w)`且`hb(w', r)`成立）。

通俗地说，如果没有*先发生于*排序来阻止该读取，读取`r`就被允许看到写入`w`的结果。

一个动作集合`A`是*先发生于一致的*（happens-before consistent），如果对于`A`中的所有读取`r`，其中`W(r)`是`r`看到的写入动作，并不满足`hb(r, W(r))`成立，或者存在`A`中的一个写入`w`使得`w.v = r.v`且`hb(W(r), w)`和`hb(w, r)`成立。

在先发生于一致的动作集合中，每次读取都会看到一个根据*先发生于*排序被允许看到的写入。

### 示例 17.4.5-1. 先发生于一致性

对于轨迹 17.4.5-A，初始`A == B == 0`。该轨迹可以是`r2 == 0`且`r1 == 0`仍然是先发生于一致的，因为存在某些执行顺序，使得每次读取都导致了相应的写入。

表 17.4.5-A. 先发生于一致性允许但顺序一致性不允许的行为。

| 线程 1 | 线程 2 |
| :--- | :--- |
| B = 1; | A = 2; |
| r2 = A; | r1 = B; |

由于没有同步，每次读取都可以看到初始值的写入或另一个线程的写入。显示这种行为的执行顺序如下所示：

```
1: B = 1;
3: A = 2;
2: r2 = A; // 看到初始写入 0
4: r1 = B; // 看到初始写入 0
```

另一个先发生于一致的执行顺序是：

```
1: r2 = A; // 看到 A = 2 的初始写入
3: r1 = B; // 看到 B = 1 的初始写入
2: B = 1;
4: A = 2;
```

在这次执行中，*先发生于*顺序允许后来的写入。这看起来似乎是反直觉的，但它是*先发生于*规则允许的。



# 17.4.6 执行

执行 $E < P, A, po, so, W, V, sw, hb >$ 是良好的，当且仅当满足以下条件：

1. 每个读取写入同一个变量。所有读取都是 volatile。对于 $A$ 中的所有读取 $r$，都有 $W(r)$。变量 $r.v$ 是 volatile 当且仅当 $r$ 是 volatile 读取，且 $w.v$ 是 volatile 当且仅当 $w$ 是 volatile 写入。
2. *先发生于*顺序是一个偏序。*先发生于*顺序由其传递闭包给出。它必须是一个有效的偏序：自反、传递且反对称。
3. 执行遵循线程内一致性。对于每个线程 $t$，其在 $A$ 中执行的动作与其在孤立状态下生成的动作相同。程序顺序必须反映程序顺序。
4. 执行是*先发生于一致的*（§17.4.5）。
5. 执行遵循同步顺序一致性。对于 $A$ 中的所有 volatile 读取 $r$，并不满足 $so(r, W(r))$ 成立，或者存在 $A$ 中的 $w$ 使得 $w.v = r.v$ 且 $so(W(r), w)$ 和 $so(w, r)$ 成立。

# 17.4.8 执行与因果律

我们使用 $f_d$ 表示对 $f$ 在 $d$ 的限制。对于 $d$ 中的所有 $x$，$f_d(x)=f(x)$，而对于所有不在 $d$ 中的 $x$，$f_d(x)$ 是未定义的。

一个良好的执行通过提交 $A$ 中的动作来验证。如果 $A$ 中的所有动作都可以被提交，那么该执行满足 Java 编程语言内存模型的因果律。

## 17.4 内存模型 线程与锁

从空集 $C_0$ 开始，我们执行一系列步骤，从动作集合 $A$ 中取出动作并将它们添加到提交动作集 $C_i$ 中，以得到一个新的提交动作集 $C_{i+1}$。为了证明这种做法是合理的，对于每个 $C_i$，我们需要证明存在包含 $C_i$ 且满足特定条件的执行 $E$。

形式上，执行 $E$ 满足 Java 语言内存模型的因果关系要求，当且仅当存在：

- 动作集合 $C_0, C_i, ...$ 使得：
    - $C_0$ 是空集
    - $C_i$ 是 $C_{i+1}$ 的真子集
    - $A = \cup(C_0, C_i, ...)$

如果 $A$ 是有限的，那么序列 $C_0, C_i, ...$ 是有限的，并以集合 $C_n = A$ 结束。
如果 $A$ 是无限的，那么序列 $C_0, C_i, ...$ 可能是无限的，且该无限序列中所有元素的并集必须等于 $A$。

- 良好的执行 $E_i, ...$，其中 $E_i < P, p_{o_i}, p_{so_i}, W_i, V_i, sw_i, hb_i >$。

给定这些动作集合 $C_0, ...$ 和执行 $E_i, ...$，$C_i$ 中的每一个动作都必须是 $E_i$ 中的动作之一。$C_i$ 中的所有动作在 $E_i$ 和 $E_j$ 中必须共享相同的发生在此（happens-before）顺序和同步顺序。形式化为：
1. $C_i$ 是 $A_i$ 的子集
2. $hb_i|C_i = hb_j|C_i$
3. $so_i|C_i = so_j|C_i$
4. $V_i|C_{i,j} = V_j|C_{i,j}$
5. $W_i|C_{i,j} = W_j|C_{i,j}$

$C_i$ 中写入操作产生的值在 $E_i$ 和 $E$ 中必须相同。只有 $C_{i,j}$ 中的读操作需要在 $E_i$ 和 $E_j$ 中看到相同的写入操作即可。形式化为：
$E_i$ 中不在 $C_{i,j}$ 中的所有读操作必须看到发生在其之前的写入操作。$C_{i,l} - C_{i,j}$ 中的每个读操作 $r$ 必须在 $E_i$ 和 $E_j$ 中都能看到 $C_i$ 中的写入操作，但在 $E_i$ 中看到的写入操作可能与其在 $E_j$ 中看到的不同。形式化为：

- 6. 对于 $A_i - C_{i,j}$ 中的任何读操作 $r$，我们有 $hb(W(r), r)$
- 7. 对于 $(C_i - C_{i,j})$ 中的任何读操作 $r$，在 $C_{i,l}$ 中有 $W_i(r)$ 且在 $C_{i,l}$ 中有 $W_j(r)$

给定对于 $E_i$ 的一组充分同步边，如果存在一个发生在你正在提交的动作之前的（见 §17.4.5）的释放-获取对，那么该对必须存在于所有 $E_j$ 中，其中 $j \ge i$。形式化为：

- 令 $sw_i$ 为同样位于 $hb_i$ 传递规约中不在 $po$ 中的 $sw_j$ 边。我们称 $ssw(x, y)$ 为 $E_i$ 的充分同步边。如果 $ssw(x, y)$ 和 $hb(y, z)$ 且 $z$ 在 $C_i$ 中，则对于所有 $j \ge i$，都有 $sw_j(x, y)$。

- 如果动作 $y$ 被提交，所有发生在此之前的外部动作也必须被提交。

- 如果 $y$ 在 $C_i$ 中，$x$ 是一个外部动作且 $hb_f(x, y)$，则 $x$ 在 $C_j$ 中。

## 17.4.8-1 发生在此之前一致性是不充分的

发生在此之前一致性是一组必要但非充分的约束。强制执行发生在此之前一致性的内存模型将允许不可接受的行为——即那些违反我们为程序建立的要求的行为。例如，一致性允许值“凭空出现”。通过详细检查表 17.4.8-A 中的轨迹（trace）可以看到这一点。

| 表 17.4.8-A. 发生在此之前一致性不充分 | |
| --- | --- |
| 线程 1 | 线程 2 |
| `r1 = x;` | `r2 = y;` |
| `if (r1 != 0) y = 1;` | `if (r2 != 0) x = 1;` |

表 17.4.8-A 中的代码是正确同步的。这可能看起来令人惊讶，因为它没有执行任何同步动作。但请记住，当一个程序以顺序一致的方式执行且没有数据竞态时，该程序就是正确同步的。如果这段代码以顺序一致的方式执行，每个动作都将按照程序顺序发生，且两个操作都不会发生（注：此处原文逻辑可能指无竞态冲突）。

final 字段语义

- O' - O 包含外部操作

请注意，行为 B 并不描述 B 中外部操作被观测到的顺序，但关于外部操作如何生成和执行的其它（内部）约束可能会施加此类约束约。

# 17.5 final 字段语义

声明为 `final` 的字段仅初始化一次，在正常情况下永远不会被改变。`final` 字段的详细语义与普通字段略有不同。特别是，编译器有很大的自由度可以对字段的读取操作跨越同步屏障以及对任意或未知方法的调用进行重排。编译器被允许将 `final` 字段的值缓存在寄存器中，而在某些非 `final` 字段必须重新加载的情况下，它不会从该处重新加载。

`final` 字段还允许程序员在不使用同步机制的情况下实现线程安全的不可变对象。线程安全的不可变对象对所有线程来说都是不可变的，即使使用了数据竞态来将不可变对象的引用传递给线程。这可以提供安全保证，防止错误或恶意代码误用不可变类。必须正确使用 `final` 字段才能提供不可变性保证。

当对象的构造函数执行完毕时，该对象被认为已完全初始化。只有在对象完全初始化后才能看到该对象引用的线程，保证看到该对象 `final` 字段的正确初始化的值。

`final` 字段的使用模型非常简单：在对象的构造函数中设置该对象的 `final` 字段；并且不要在对象构造函数完成之前，在另一个线程可见的地方写入正在构造的对象引用。如果遵循了这一点，那么当另一个线程看到该对象时，该线程将始终看到该对象 `final` 字段的正确构建的版本。它还会看到由这些 `final` 字段引用的任何对象或数组的版本，这些版本至少与 `final` 字段同步。

## 示例 17.5-1 Java内存模型中的 final 字段

下面的程序演示了 `final` 字段与普通字段的对比。

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

类 `FinalFieldExample` 有一个 `final` 字段 `x` 和非 `final` 字段 `y`。一个线程可能执行 `writer` 方法，另一个线程可能执行 `reader` 方法。

由于 `writer` 在对象构造函数完成后才写入 `f`，`reader` 将保证看到 `f.x` 的正确初始化值：它将读取到值 3。然而，`f.y` 不是 `final` 的；因此 `reader` 不能保证看到它的值 4。

## 示例 17.5-2 用于安全的 final 字段

`final` 字段的设计是为了提供必要的安全保证。考虑执行以下程序（我们将其称为线程 1）：

```java
Global.s = "/tmp/usr".substring(4);

String myS = Global.s;

if (myS.equals("/tmp/")) System.out.println(myS);
```

而另一个线程（线程 2）执行

`String` 对象旨在设计是不可变的，且字符串操作不执行同步。虽然 `String` 的实现没有任何数据竞态，但其他代码在使用 `String` 对象时可能存在数据竞态，内存模型对存在数据竞态的程序提供了弱保证。特别是，如果 `String` 类的字段不是 `final` 的，那么可能（尽管可能性很）线程 2 可能会看到 `String` 偏移量的默认值 0，允许其像 "/tmp" 一样比较。对 `String` 对象的后续操作可能会看到正确的偏移量 4，导致 `String` 对象被感知为 "/usr/"。Java 编程语言的许多安全特性依赖于 `String` 对象被视为真正的不可变，即使恶意代码正在使用数据竞态在线程之间传递 `String` 引用。

## 17.5.1 final 字段的语义

设 $o$ 为一个对象，$c$ 为 $o$ 的构造函数，在其中写入了 *final* 字段 $f$。对 $o$ 的 *final* 字段 $f$ 的“冻结”（freeze）操作在 $c$ 退出时发生，无论是正常退出还是异常退出。

请注意，如果一个构造函数调用另一个构造函数，被调用的构造函数设置了 *final* 字段，该 *final* 字段的冻结发生在被调用构造函数的结束时。

对于每次执行，读取的行为受到两个额外偏序的影响：解引用链 `dereferences()` 和内存链 `mc`，它们被认为是执行的一部分（因此，对于任何特定执行来说都是固定的）。这些偏序必须满足以下约束（不一定有唯一解）：

- *解引用链*：如果操作 $a$ 是由未初始化 $o$ 的线程 $t$ 对对象 $o$ 的字段或元素的读取或写入，则必须存在由线程 $t$ 执行的读取操作 $r$，它看到了 $o$ 的地址，使得 `dereferences(r, a)`。
- *内存链*：
  - 如果 $r$ 是看到写入 $w$ 的读取，那么必须满足 `mc(w, r)`。
  - 如果 $r$ 和 $a$ 是满足 `dereferences(r, a)` 的操作，那么必须满足 `mc(r, a)`。
  - 如果 $w$ 是由未初始化 $o$ 的线程 $t$ 对对象 $o$ 地址的写入，那么必须存在 `mc(r, w)`。

给定 $w$，一个冻结 $f$，操作 $a$（对 *final* 字段的读取），对 *final* 字段的读取 $r_1$，以及 $r_2$，使得 $hb(w, f), hb(f, a), mc(a, r_1), dereferences(r_1, r_2)$，在确定 $r_2$ 可以看到哪些值时，我们考虑 $hb(w, r_2)$。（这种发生之前序是非传递的。）

请注意，解引用序是自反的，且 $r_1$ 可以等于 $r_2$。

对于 *final* 字段的读取，被认为在 *final* 字段之前的写入是根据 *final* 字段语义的。

## 17.5.2 在构造期间读取 final 字段

在构造对象的线程内对 *final* 字段的读取，相对于构造函数内该字段的初始化是有序的。如果读取发生在构造函数设置字段之后，它将看到该字段赋值的值；否则它将看到默认值。

## 17.5.3 final 字段的后续修改

在某些情况下（例如反序列化），系统需要在构造后更改对象的 *final* 字段。*final* 字段可以通过反射和其他取决于实现的方法进行更改。唯一合理的语义模式是先构造对象，然后更新其 *final* 字段。在所有 *final* 字段更新完成之前，该对象不应对其他线程可见，也不应读取其字段。*final* 字段的冻结发生在设置该字段的构造函数结束时，以及每次通过反射或特殊机制修改之后。

尽管如此，仍存在许多复杂问题。在字段声明中初始化为常量表达式（§15.28）的 *final* 字段，其更改可能无法被观察到，因为 *final* 字段的使用在编译时会被替换为常量的值。

另一个问题是规范允许对 *final* 字段进行优化。在线程内部，允许对 *final* 字段的读取与那些不在构造函数中的 *final* 字段修改进行重排。

### 示例 17.5.3-1 final 字段的激进优化

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

        return j - i;

    }

    static void g(A a) {

        // 使用反射将 a.x 改为 2

    }

}
```

在 `d` 方法中，编译器允许自由地重排对 `x` 的读取和对 `g` 的调用的顺序。因此，新的 `new A().f()` 可能返回 -1、0 或 1。

某种实现可能提供一种在**最终字段安全上下文（final-field safety context）**中执行代码块的方法。如果对象是在最终字段安全上下文中构造的，则对该对象的 `final` 字段的读取不会与在该最终字段安全上下文中对该 `final` 字段的修改发生重排。

最终字段安全上下文具有额外的保护。如果一个线程看到了一个发布错误的对象引用，导致该线程看到了 `final` 字段的默认值，随后随后在最终字段安全上下文中读取了该对象的发布正确的引用，则可以保证该线程能看到该 `final` 字段的正确值。在形式化中，在最终字段安全上下文中执行的代码被视为一个独立的线程（仅出于此目的）。在具体实现中，编译器不应将对 `final` 字段的访问移动到最终字段安全上下文之外（尽管它可以移动到该上下文执行之后，只要该对象不是在该上下文中构造的即可）。

在执行器或线程池中是使用最终字段安全上下文的一个恰当场景。通过执行每个最终字段安全上下文，执行器可以保证一个 `Runnable` 的错误访问不会移除其他对象的 `final` 字段。

## 17.5.4 写保护字段

通常情况下，一个 `final` 且 `static` 的字段可能被修改。然而，`System.in`、`System.out` 和 `System.err` 是 `final` 字段，由于历史原因，它们可能被允许更改。编译器需要对这些字段进行区别于其他字段的处理。例如，对普通 `final` 字段的读取对同步是“免疫”的：`volatile` 读取不需要影响从字段中读取的值。由于写保护字段的值可能会看到发生变化，同步事件对它们不应产生任何影响。因此，语义规定这些字段被视为不能被用户代码更改的普通字段。

# 线程与锁

## 17.6 字撕裂（Word Tearing）

Java虚拟机实现的一个考虑因素是，每个字段和数组元素都被认为是独立的；对一个字段的更新不会与任何其他字段的读取或更新相互作用。特别是，两个分别更新字节数组相邻元素的线程必须互不干扰或相互作用，并且不需要同步来确保顺序一致性。某些处理器并不提供孤立写入单个字节的能力；通过简单读取整个字（word）、更新相应的字节并将整个字写回内存来实现字节更新将是非法的。这种问题有时被称为“字撕裂（word tearing）”，在这样的处理器上将需要其他方法。

### 17.6-1 字撕裂的检测

以下程序是一个用于检测字撕裂的测试：

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

                System.out.println("Word-Tearing found: " + counts[" + id + "] = " + v2 + ", should be " + v);

                return;

            }
```



```
v++;

counts[id] = v;

}

}

public static void main(String[] args) {

    for (int i = 0; i < LENGTH; i++)

        (threads[i] = new WordTearing(i)).start();

}

}
```

## 17.7 double 和 long 的非原子处理

这一点说明了字节不能通过对相邻字节的写入而被覆盖。对于 Java 语言内存模型而言，对非 `volatile` `long` 或 `double` 值的单次写入被视为两次独立的写入：分别写入每个 32 位的半。这可能导致一种的情况：线程从某次写入看到了 64 位值的前 32 位，而从另一次写入看到了后 32 位。

`volatile` `long` 和 `double` 值的写入和读取始终是原子的。

引用的写入和读取始终是原子的，无论它们被实现为 32 位还是 64 位值。

某些实现可能会发现将对 64 位 `long` 或 `double` 值的单次写入操作划分为对相邻 32 位值的两次写入操作更为方便。出于效率考虑，这种行为取决于具体实现；虚拟机实现可以选择原子地写入 `long` 和 `double` 值，也可以分两次写入。

鼓励虚拟机实现将 64 位值声明为 `volatile` 或正确地同步其程序以避免可能的复杂性。

## 第 18 章
### 类型推断

各种编译时分析需要对尚知的类型进行推理。其中最重要的是泛型方法可用性测试 (§18.5.1) 和泛型方法调用类型推断 (§18.5.2)。通常，我们将对未知类型进行推理的过程称为类型推断。

在高级层次上，类型推断可以分解为三个过程：

- **归约（Reduction）**：接收一个关于表达式或类型的兼容性断言（称为约束公式），并将其归约为推理变量的边界集合。通常，约束公式会归约为其他约束公式，这些公式必须递归归约。遵循一个程序来识别这些额外的约束公式，并最终对它们进行表示。
- **合并（Incorporation）**：维护推理变量边界集，在添加新边界时确保它们的一致性。由于一个变量的边界有时会影响另一个变量的选择，此过程在相互依赖的变量之间传播边界。
- **解析（Resolution）**：检查推理变量的边界并确定一个这些边界兼容的实例化。它还决定了推理变量的顺序。

这些过程紧密交互：归约可以触发合并；合并可能导致进一步的归约；而解析可能会引起进一步的合并。

- §18.1 更精确地定义了所使用的概念和表示它们的表示法。
- §18.2 详细描述了归约。
- §18.3 详细描述了合并。
- §18.4 详细描述了解析。
- §18.5 定义了如何使用推断工具解决某些分析问题。

### 18.1.1 推理变量

推理变量是类型的元变量——也就是说，是允许对类型进行抽象推理的特殊名称。为了与类型变量区分开来，推理变量使用希腊字母，主要是 α。

在本章中，“类型”一词被泛指使用，以包含推理变量的类类型语法。“真正的类型”一词则排除此类“类型”。

### 18.1.2 约束公式

约束公式是关于兼容性或子类型的断言，可能涉及推断变量。这些公式可能采取以下形式之一：

- `Expression → T`：表达式在松散调用上下文中与类型 T 兼容 (§5.3)。
- `S → T`：类型 S 在松散调用上下文中与类型 T 兼容 (§5.3)。
- `S <: T`：引用类型 S 是引用类型 T 的子类型 (§4.10)。
- `S <= T`：参数 S 被类型参数 T 包含 (§4.5.1)。
- `S = T`：类型 S 与类型 T 相同 (§4.3.4)，或者类型 S 与（此处缺失）相同；
- `LambdaExpression throws T`：LambdaExpression 表达式抛出的检查异常由从 T 导出的函数类型的 throws 子句声明。
- `MethodReference throws T`：引用方法抛出的检查异常由从 T 导出的函数类型的 throws 子句声明。

约束公式的示例：

- 来自 `Collections.singleton("hi")`，我们得到了约束公式 `"hi" → α`。通过归约，这将变为约束 `String <: α`。
- 来自 `Arrays.asList(1, 2.0)`，我们得到了约束公式 `<1 → α` 和 `<2.0 → α`。通过归约，这些将变为约束 `<int → α` 和 `<double → α`，以及 `<Integer <: α` 和 `<Double <: α`。
- 从构造函数调用 `List<Thread> lt = new ArrayList<>()` 的目标类型中，我们得到了约束公式 `ArrayList<α> → List<Thread>>`。通过归约，这将变为约束 `α <= List<Thread>`，然后是 `α = Thread`。

### 18.1.3 边界

在推断过程中，会维护一组对推断变量的*边界*（bounds）。一个边界具有以下形式之一：

- `S = T`，其中 S 或 T 至少有一个是推断变量：S 与 T 相同。
- `S <: T`，其中 S 或 T 至少有一个是推断变量：S 是 T 的子类型。
- `false`：不存在有效的推断变量。
- `G<α₁, ..., αₙ> = capture(G<A₁, ..., Aₙ>)`：变量 α₁, ..., αₙ 代表捕获表达式 (§5.1.10) 应用于 `G<A₁, ..., Aₙ>` 的结果（其中 A₁, ..., Aₙ 可能是通配符，也可能是推断变量）。
- `throws α`：推断变量 α 出现在 `throws` 子句中。

如果通过应用替换后断言为真，则推断变量的替换*满足*了该边界。边界 `false` 永远无法被满足。

某些边界将推断变量与包含推断变量的类型相关联。令 τ 为适当类型。给定形式为 `α = τ` 或 `τ = α` 的边界，我们称 τ 是 α 的*实例化*（instantiation）。同样，给定形式为 `α <: τ` 的边界，我们称 τ 是 α 的*严格上界*（proper upper bound）；给定形式为 `τ <: α` 的边界，我们称 τ 是 α 的*严格下界*（proper lower bound）。

其他边界将推断变量与包含推断变量的类型相关联。形式为 `S = τ` 或 `S <: τ` 的边界被称为*依赖*（dependencies）。

形式为 `G<α₁, ..., αₙ> = capture(G<A₁, ..., Aₙ>)` 的边界表示 α₁, ..., αₙ 是捕获转换结果的占位符。这是必要的，因为捕获转换只能在适当类型上执行，且 A₁, ..., Aₙ 中的推断变量可能尚未解析。

形式为 `throws α` 的边界是纯粹信息提示性的：它引导解析以优化 α 的实例化，以便在可能的情况下它是一个检查异常类型。

推断的一个重要中间结果是*边界集*（bound set）。有时用符号 `true` 来引用边界集是很方便的。

边界集的示例：

- `(α = String)` 包含单个边界。
- `(α <: String, α <: Object)` 描述两个边界。
- `(α <: String, α <: Object)` 描述一个依赖。

## 18.2 归约

当推断开始时，通常从 P₁, ..., Pₙ 生成边界集如下（对于 1 ≤ l ≤ p）：

- 如果表达式是形式为 `( )` 的括号表达式，则约束归约为 `<Expression> → T`。
- 如果表达式是类创建或方法调用，则约束归约为 §18.5.2 定义的 Bⱼ。
- 如果表达式是形式为 `e₁ ? e₂ : e₃` 的条件表达式，则约束归约为两个约束公式，`e₂ → T` 和 `e₃ → T`。
- 如果表达式是 lambda 表达式或方法引用，结果下文所示。

依次考虑每个约束公式。当没有更多公式剩余时，归约完成。

归约的结果始终是健全的（soundness-preserving）：如果一个公式满足归约结果，它将满足原始公式。另一方面，归约不是完备的（completeness-preserving）：可能存在满足原始但不满足归约的推断变量。

### 18.2.1 表达式性

形式为 `⟨τ → T⟩` 的约束公式，其中 τ 至少包含一个推断变量，归约如下：

- 如果 τ 是适当类型，如果表达式在松散调用上下文中与 τ 兼容，则约束归约为 `true`。
- 否则，如果表达式是多表达式 (§15.2)，约束归约为 `⟨τ → T⟩`。
- 否则，约束归约为 `⟨τ → T⟩`。

### 18.2.2 依赖

通过将泛型方法调用视为多表达式，我们改进了嵌套调推断行为。以下代码在 Java 7 中是非法的，但在 Java 8 中是合法的：

```java
StringBuilder b = new StringBuilder(Collections.emptyList());
// StringBuilder 的构造函数需要 List<String>
```

当外部和嵌套调用都需要推断时，问题变得更加复杂。例如：

```java
List<String> ls = new ArrayList<>(Collections.emptyList());
```

我们的方法是将嵌套调用推断出的边界（在 emptyList 的情况下为 `{ α: Object }`）“提升”到外部推断过程中（在本例中，尝试推断 β）。我们还推导出嵌套推断变量与外部变量之间的依赖（`List<α> → Collection<β>` 将归约为依赖 `α = β`）。通过这种方式，嵌套调用推断变量的解析可以等待从外部调用推导出额外的信息（基于赋值目标 `β = String`）。

形式为 `<LambdaExpression> → T` 的约束公式，其中 T 至少包含一个推断变量，归约如下：

- 如果 T 不是函数接口类型 (§9.8)，则约束归约为 `false`。
- 否则，令 T' 为从 T 导出的基础类型，如 §15.27.3 所示。如果使用 §18.5.3 导出函数接口类型且该类型是参数化的，那么测试 `F<A'₁, ..., A'ₙ> <: F<A₁, ..., Aₘ>` 的测试将不会执行（相反地，它通过下方的约束公式进行断言）。Lambda 表达式的目标函数是 T' 的函数类型。那么：
  - 如果找不到有效的函数类型，则约束归约为 `false`。
  - 否则，LambdaExpression 的同构性与目标函数类型不一致的断言如下：
    - 如果 lambda 参数的数量与函数类型的参数类型数量不符，则约束归约为 `false`。
    - 如果 lambda 表达式是隐式类型化的，且函数类型的参数类型中有一个或多个不是适当类型，则约束归约为 `false`。
      该条件在实践中出现是由于 §18.5.1 中对隐式类型 lambda 表达式的处理，以及 §18.5.2 中应用于目标类型上的替换。
    - 如果函数类型的返回不是 `void` 且 lambda 体既不是语句表达式也不是 void 兼容的块，则约束归约为 `false`。
    - 如果函数类型的返回不是 `void` 且 lambda 体是一个非 void 兼容的块，则约束归约为 `false`。
  - 否则，约束归约为所有以下约束公式：
    - 如果 lambda 参数具有显式声明的类型 F₁, ..., Fₙ，且函数类型具有参数类型 G₁, ..., Gₘ，那么对于所有 i (1 ≤ i ≤ n)，Fᵢ = Gᵢ，且 (ii) T' <: T。
    - 如果函数类型的返回类型是一个（非 void）类型 R，假设 lambda 的参数类型与函数类型的参数类型相同。那么：
      - 如果 R 是适当类型，且如果 lambda 体或 lambda 体中的某些结果表达式在赋值上下文中与 R 不兼容，则结果为 `false`。
      - 否则，如果 R 不是适当类型，那么当 lambda 体的形式为 `Expression` 时，约束 `⟨Expression → R⟩`；当 lambda 体是一个具有结果表达式 e₁, ..., eₘ (1 ≤ i ≤ m) 的块时，eᵢ → R。

推导出涉及 lambda 表达式的兼容性约束的关键信息是目标类型返回类型中推断变量的边界集。这是非常重要的，因为函数接口通常是泛型的，并且许多操作这些类型的方法也是泛型的。

在最简单的情况下，lambda 表达式可能仅为推断变量提供一个下界：

```java
<T> List<T> makeThree(Factory<T> factory) { ... }

String s = makeThree(() -> "abc").get(2);
```



## Lambda 表达式兼容性约束推导

在复杂情况下，结果表达式可能是一个多式表达式——甚至是另一个 lambda 表达式——因此推断变量在产生边界之前可能会通过多个具有不同类型的约束公式传递。

本节的大部分工作位于关于结果表达式的断言之前；其目的是推导出 lambda 的函数类型，并检查明显无法通过编译的表达式。

我们并不尝试对目标函数 `throws` 子句中可能出现的推断变量设定边界。这是因为异常冲突不是兼容性的一部分 (§15.27.3)——特别是，它不能影响方法的适用性 (§18.5.1)。然而，我们稍后会获得这些变量的边界，因为调用推断类型 (§18.5.2) 会产生异常约束公式 (§18.2.5)。

注意，如果目标类型是一个推断变量，或者目标类型的参数包含推断变量，我们产生 false。在调用推断类型 (§18.5.2.2) 中，会执行额外的替换以实例化这些推断变量，从而避免这种情况。（换句话说，在实践中，归约永远不会以这些形式之一作为目标类型被调用）。

最后，注意 §15.27.3 要求 lambda 表达式的结果在赋值上下文中与目标返回类型 $R$ 兼容。如果 $R$ 是适当类型（例如源自 `Function<α, Byte>` 的 `Byte`），那么可赋值性很容易测试，且归约在上方已完成。如果 $R$ 不是适当类型（例如源自 `Function<String,α>` 的 $α$），我们指的是上述简化假设，即调用兼容性将足够。赋值和循环推断兼容性之间的区别在于只有赋值允许收缩常量表达式，例如 `Byte b = 100;`；因此，我们的简化假设不是保持完备性的：给定返回类型 $α$ 和整数字面量结果表达式 100，可以想象它可以被实例化为 `Byte`，但归约不会产生这样的边界。

### 方法引用约束归约

形式为 `<MethodReference → τ>` 的约束公式，其中 $τ$ 至少提到一个推断变量，其归约如下：

- 如果 $τ$ 不是函数接口类型，或者如果 $τ$ 是一个没有函数类型的函数类型 (§9.9)，则约束归约为 false。
- 否则，如果目标为 $τ$ 时该方法引用不存在可能的适用方法，则约束归约为 false。
- 否则，如果方法引用是精确的 (§15.13)，则让 $P_1, ..., P_n$ 为函数类型的参数类型，并让 $F_1, ..., F_k$ 为方法的参数类型。约束归约为一组新的约束如下：
  - 在 $n=k+1$ 的特殊情况下，$P_1$ 是方法引用的目标。约束归约为对于所有 $i$ ($2 \le i \le n$)，$P_i → F_{i-1}$。
  - 在所有其他情况下，$n=k$，约束归约为对于所有 $i$ ($1 \le i \le n$)，$P_i → F_i$。

### Lambda 表达式约束归约

- 如果函数类型的返回不是 `void` 且 lambda 体既不是语句表达式也不是 void 兼容的块，则约束归约为 `false`。
- 如果函数类型的返回不是 `void` 且 lambda 体是一个非 void 兼容的块，则约束归约为 `false`。
- 否则，约束归约为所有以下约束公式：
  - 如果 lambda 参数具有显式声明的类型 $F_1, ..., F_n$，且函数类型具有参数类型 $G_1, ..., G_m$，那么对于所有 $i$ ($1 \le i \le n$)，$F_i = G_i$。
  - 如果函数类型的返回类型是一个（非 void）类型 $R$，假设 lambda 的参数类型与函数类型的参数类型相同。那么：
    - 如果 $R$ 是适当类型，且 lambda 体或 lambda 体中的某些结果表达式在赋值上下文中与 $R$ 不兼容，则结果为 `false`。
    - 否则，如果 $R$ 不是适当类型，那么当 lambda 体的形式为 `Expression` 时，约束 `⟨Expression → R⟩`；当 lambda 体是一个具有结果表达式 $e_1, ..., e_m$ ($1 \le i \le m$) 的块时，$e_i → R$。

推导出涉及 lambda 表达式的兼容性约束的关键信息是目标类型返回类型中推断变量的边界集。这是非常重要的，因为函数接口通常是泛型的，并且许多操作这些类型的方法也是泛型的。

### 简单示例：提供下界

在最简单的情况下，lambda 表达式可能仅为推断变量提供一个下界：

```java
<T> List<T> makeThree(Factory<T> factory) { ... }

String s = makeThree(() -> "abc").get(2);
```

### 复杂情况

在复杂情况下，结果表达式可能是一个多式表达式——甚至是另一个 lambda 表达式——因此推断变量在产生边界之前可能会通过多个不同类型的约束公式传递。

本节的大部分工作位于关于结果表达式的断言之前；其目的是推导出 lambda 的函数类型，并检查明显无法通过编译的表达式。

我们并不尝试对目标函数 `throws` 子句中可能出现的推断变量设定边界。这是因为异常冲突不是兼容性的一部分 (§15.27.3)——特别是，它不能影响方法的适用性 (§18.5.1)。然而，我们稍后会获得这些变量的边界，因为调用推断类型 (§18.5.2) 会产生异常约束公式 (§18.2.5)。

注意，如果目标类型是一个推断变量，或者目标类型的参数包含推断变量，我们产生 false。在调用推断类型 (§18.5.2.2) 中，会执行额外的替换以实例化这些推断变量，从而避免这种情况。（换句话说，在实践中，归约永远不会以这些形式之一作为目标类型被调用）。

最后，注意 §15.27.3 要求 lambda 表达式的结果在赋值上下文中与目标返回类型 $R$ 兼容。如果 $R$ 是适当类型（例如源自 `Function<α, Byte>` 的 `Byte`），那么可赋值性很容易测试，且归约在上方已完成。如果 $R$ 不是适当类型（例如源自 `Function<String,α>` 的 $α$），我们指的是上述简化假设，即调用兼容性将足够。赋值和循环推断兼容性之间的区别在于只有赋值允许收缩常量表达式，例如 `Byte b = 100;`；因此，我们的简化假设不是保持完备性的：给定返回类型 $α$ 和整数字面量结果表达式 100，可以想象它可以被实例化为 `Byte`，但归约不会产生这样的边界。

### 方法引用约束归约（重述）

形式为 `<MethodReference → τ>` 的约束公式，其中 $τ$ 至少提到一个推断变量，其归约如下：

- 如果 $τ$ 不是函数接口类型，或者如果 $τ$ 是一个没有函数类型的函数类型 (§9.9)，则约束归约为 false。
- 否则，如果目标为 $τ$ 时该方法引用不存在可能的适用方法，则约束归约为 false。
- 否则，如果方法引用是精确的 (§15.13)，则让 $P_1, ..., P_n$ 为函数类型的参数类型，并让 $F_1, ..., F_k$ 为方法的参数类型。约束归约为一组新的约束如下：
  - 在 $n=k+1$ 的特殊情况下，$P_1$ 是方法引用的目标。约束归约为对于所有 $i$ ($2 \le i \le n$)，$P_i → F_{i-1}$。
  - 在所有其他情况下，$n=k$，约束归约为对于所有 $i$ ($1 \le i \le n$)，$P_i → F_i$。

### Lambda 表达式约束归约（重述）

- 如果函数类型的返回不是 `void` 且 lambda 体既不是语句表达式也不是 void 兼容的块，则约束归约为 `false`。
- 如果函数类型的返回不是 `void` 且 lambda 体是一个非 void 兼容的块，则约束归约为 `false`。
- 否则，约束归约为所有以下约束公式：
  - 如果 lambda 参数具有显式声明的类型 $F_1, ..., F_n$，且函数类型具有参数类型 $G_1, ..., G_m$，那么对于所有 $i$ ($1 \le i \le n$)，$F_i = G_i$。
  - 如果函数类型的返回类型是一个（非 void）类型 $R$，假设 lambda 的参数类型与函数类型的参数类型相同。那么：
    - 如果 $R$ 是适当类型，且 lambda 体或 lambda 体中的某些结果表达式在赋值上下文中与 $R$ 不兼容，则结果为 `false`。
    - 否则，如果 $R$ 不是适当类型，那么当 lambda 体的形式为 `Expression` 时，约束 `⟨Expression → R⟩`；当 lambda 体是一个具有结果表达式 $e_1, ..., e_m$ ($1 \le i \le m$) 的块时，$e_i → R$。

推导出涉及 lambda 表达式的兼容性约束的关键信息是目标类型返回类型中推断变量的边界集。这是非常重要的，因为函数接口通常是泛型的，并且许多操作这些类型的方法也是泛型的。

### 简单示例：提供下界（重述）

在最简单的情况下，lambda 表达式可能仅为推断变量提供一个下界：

```java
<T> List<T> makeThree(Factory<T> factory) { ... }

String s = makeThree(() -> "abc").get(2);
```



在复杂情况下，结果表达式可能是一个多式表达式——甚至是另一个 lambda 表达式——因此推断变量在产生边界之前可能会通过多个不同类型的约束公式传递。

本节的大部分工作位于关于结果表达式的断言之前；其目的是推导出 lambda 的函数类型，并检查明显无法通过编译的表达式。

我们并不尝试对目标函数 `throws` 子句中可能出现的推断变量设定边界。这是因为异常冲突不是兼容性的一部分（§15.27.3）——特别是，它不能影响方法的适用性（§18.5.1）。然而，我们稍后会获得这些变量的边界，因为调用推断类型（§18.5.2）会产生异常约束公式（§18.2.5）。

注意，如果目标类型是一个推断变量，或者目标类型的参数包含推断变量，我们产生 false。在调用推断类型（§18.5.2.2）中，会执行额外的替换以实例化这些推断变量，从而避免这种情况。（换句话说，在实践中，归约永远不会以这些形式之一作为目标类型被调用）。

最后，注意 §15.27.3 要求 lambda 表达式的结果在赋值上下文中与目标返回类型 $R$ 兼容。如果 $R$ 是适当类型（例如源自 `Function<α, Byte>` 的 `Byte`），那么可赋值性很容易测试，且归约在上方已完成。如果 $R$ 不是适当类型（例如源自 `Function<String,α>` 的 `α`），我们指的是上述简化假设，即调用兼容性将足够。赋值和循环推断兼容性之间的区别在于只有赋值允许收缩常量表达式，例如 `Byte b = 100;`；因此，我们的简化假设不是保持完备性的：给定返回类型 `α` 和整数字面量结果表达式 `100`，可以想象它可以被实例化为 `Byte`，但归约不会产生这样的边界。

形式为 `<MethodReference → τ>` 的约束公式，其中 `τ` 至少提到一个推断变量，其归约如下：

- 如果 `τ` 不是函数接口类型，或者如果 `τ` 是一个没有函数类型的函数类型（§9.9），则约束归约为 false。
- 否则，如果目标为 `τ` 时该方法引用不存在可能的适用方法，则约束归约为 false。
- 否则，如果方法引用是精确的（§15.13），则让 $P_1, ..., P_n$ 为函数类型的参数类型，并让 $F_1, ..., F_k$ 为方法的参数类型。约束归约为一组新的约束如下：
    - 在 $n=k+1$ 的特殊情况下，$P_i$ 是方法引用的目标。约束归约为对于所有 $i$ ($2 \le i \le n$)，$P_i → F_{i-1}$。
    - 在所有其他情况下，$n=k$，约束归约为对于所有 $i$ ($1 \le i \le n$)，$P_i → F_i$。

## 18.2 类型兼容性约束

形式为 $s → au$ 的约束归约如下：

- 如果 $s$ 和 $au$ 是适当类型，如果 $s$ 在松散调用上下文中与 $au$ 兼容（§5.3），则约束归约为 `true`，否则为 false。
- 否则，如果 $s$ 是基本类型，让 $s'$ 为对 $s$ 应用装箱转换（§5.1.7）的结果。约束归约为 `<s' → au>`。
- 否则，如果 $au$ 是基本类型，让 $au'$ 为对 $au$ 应用装箱转换（§5.1.7）的结果。约束归约为 `<s = au'>`。
- 否则，如果 $au$ 是形式为 $G<T_1, ..., T_{p_k})$ 的参数化类型，且不存在形式为 $G<...>$ 的 $s$ 的超类型，但原始类型 $G$ 是 $s$ 的超类型，则约束归约为 `true`。（符号 $[^k]$ 表示 $k$ 维的数组类型。）
- 否则，约束归约为 `<s < au>`。

# 类型推断

# 归约

## 18.2

将 $T$ 装箱为 $T'$ 并不是保持完备性的：例如，如果 $T$ 是 `long`，则 $S$ 可能会被实例化为 `Integer`，而它不是 `Long` 的子类型，但可以被拆箱并拓宽为 `long`。我们通过对已经受限制为装箱原始类型的类型的推断变量返回类型进行特殊处理，在大多数情况下避免了这个问题；参见 §18.5.2.1。

同样地，对未检查转换的处理在 $T$ 不是参数化类型的情况下会牺牲完备性（例如，如果 $T$ 是一个推断变量）。在这些情况下，通常不清楚未检查转换是否必要。由于未检查转换会引入未检查警告，除非显有必要，否则推断将倾向于避免它们。

## 18.2.3 子类型约束

形式为 `<S <: T>` 的约束归约如下：

- 如果 $s$ 和 $\tau$ 是适当类型，当 $s$ 是 $\tau$ 的子类型时（§4.10），约束归约为 `true`，否则为 false。
- 否则，如果 $s$ 是空类型，则约束归约为 `true`。
- 否则，如果 $\tau$ 是空类型，约束归约为 `false`。
- 否则，如果 $s$ 是推断变量 $\alpha$，约束归约为边界 $\alpha <: \tau$。
- 否则，如果 $\tau$ 是推断变量 $\alpha$，约束归约为边界 $s <: \alpha$。
- 否则，根据 $T$ 的形式归约约束：
    - 如果 $T$ 是参数化类类型或接口类型，或者是参数化类（直接或间接的）的内部类，令 $A_1, \dots, A_n$ 为 $T$ 的类型参数。在 $s$ 的超类型中，识别出一个对应的类或接口类型，其参数为 $B_1, \dots, B_n$。如果不存在此类类型，约束归约为 `false`。否则，约束归约为以下约束：对于所有 $i$ ($1 \le i \le n$)，$B_i <: A_i$。
    - 如果 $T$ 是其他类类型或接口类型，当 $T$ 在 $s$ 的超类型中时，约束归约为 `true`，否则为 false。
    - 如果 $T$ 是数组类型 $T'[]$，则在 $s$ 的作为数组类型的超类型中，识别出一个最具体的类型 $s'$（它可能就是*本身*）。如果不存在此类类型，约束归约为 `false`。否则：
        - 如果 $s'$ 和 $T'$ 都不是原始类型，约束归约为 `<S' <: T'>`。
        - 否则，如果 $s'$ 和 $T'$ 是相同的原始类型，则约束归约为 `true`，否则为 false。

如果 $\tau$ 是一个类型变量，有三种情况：

- 如果 $s$ 是一个包含 $\tau$ 为元素的交类型，则约束归约为 `true`。
- 否则，如果 $\tau$ 有一个下界 $B$，则约束归约为 `<S <: B>`。
- 否则，约束归约为 `false`。

如果 $\tau$ 是交类型 $I_1 \& \dots \& I_n$，则约束归约为以下新约束：对于所有 $i$ ($1 \le i \le n$) `<S <: I_i>`。

形式为 `<S = T>` 的约束公式，其中 $s$ 和 $\tau$ 是类型参数（§4.5.1），归约如下：

- 如果 $\tau$ 是一个类型：
    - 如果 $s$ 是一个类型，约束归约为 `<S = T>`。
    - 如果 $s$ 是通配符，约束归约为 `false`。
    - 如果 $\tau$ 是形式为 `?` 的通配符，则约束归约为 `true`。
- 如果 $\tau$ 是形式为 `? extends T'` 的通配符：
    - 如果 $s$ 是一个类型，约束归约为 `<S <: T'>`。
    - 如果 $s$ 是形式为 `?` 的通配符，约束归约为 `<Object <: T'>`。
- 如果 $\tau$ 是形式为 `? extends S'` 的通配符：
    - 如果 $s$ 是形式为 `? super S'` 的通配符，约束归约为 `<Object <: T'>`。
- 如果 $\tau$ 是形式为 `? super S'` 的通配符：
    - 如果 $s$ 是一个类型，约束归约为 `<T' <: S>`。
    - 如果 $s$ 是形式为 `? super S'` 的通配符，约束归约为 `<T' <: S'>`。
- 否则，约束归约为 `false`。

## 18.2.4 类型相等约束

形式为 `<S = T>` 的约束公式，其中 $s$ 和 $\tau$ 是类型，归约如下：

- 如果 $s$ 和 $\tau$ 是适当类型，当 $s$ 与 $\tau$ 相同时（§4.3.4），约束归约为 `true`，否则为 false。
- 否则，如果 $s$ 或 $\tau$ 是空类型，约束归约为 `false`。
- 否则，如果 $s$ 是推断变量 $\alpha$ 且 $\tau$ 不是原始类型，约束归约为 $\alpha = \tau$。
- 否则，如果 $\tau$ 是推断变量 $\alpha$ 且 $s$ 不是原始类型，约束归约为 $s = \alpha$。
- 否则，如果 $s$ 和 $\tau$ 是类或接口类型，且 $s$ 有类型参数 $B_1, \dots, B_n$，而 $\tau$ 有类型参数 $A_1, \dots, A_n$，则约束归约为以下新约束：对于所有 $i$ ($1 \le i \le n$)，$B_i = A_i$。
- 否则，如果 $s$ 和 $\tau$ 是数组类型，且 $s$ 是 $\tau$ 的元素类型，则约束归约为 $S = T$。
- 否则，如果 $T$ 是数组类型 $T'[]$，则在 $s$ 的作为数组类型的超类型中，识别出一个最具体的类型 $s'$。如果不存在此类类型，归约为 `false`。否则，如果 $s'$ 和 $T'$ 是相同的原始类型，约束归约为 `true`，否则为 false。
- 否则，约束归约为 `false`。

## 18.2.5 检查异常约束

形式为 `<LambdaExpression -> throws τ>` 的约束公式归约如下：

- $\tau$ 不是函数接口类型（§9.8），归约为 `false`。
- 否则，确定 lambda 表达式的目标函数类型（见§27.3）。如果无法找到有效的函数类型，归约为 `false`。
- 否则，令 $E_1, \dots, E_n$ 为函数类型 `throws` 子句中不是原始类型的类型。如果 lambda 表达式是隐式类型的，其参数类型为函数类型的参数类型。如果 lambda 体是多表达式或包含多结果表达式的块，则目标返回类型为函数类型的返回类型。令 $X_1, \dots, X_n$ 为 lambda 体可能抛出的检查异常类型（§11.2）。此时有两种情况：
    - 如果 $n = 0$（目标类型的 `throws` 子句仅包含适当类型），则如果存在 $i$ ($1 \le i \le m$) 使得 $X_i$ 不是 `throws` 子句中任何类型的子类型，则归约为 `false`；否则归约为 `true`。
    - 如果 $n > 0$，约束归约为部分类型约束：对于所有 $i$ ($1 \le i \le m$)，如果 $X_i$ 不是 `throws` 子句中任何类型的子类型，则包含对于所有 $j$ ($1 \le j \le n$)，$X_i <: E_j$。此外，对于所有 $j$ ($1 \le j \le n$)，约束归约为边界 `throws` $E_j$。

形式为 `<MethodReference -> throws τ>` 的约束公式归约如下：

- $\tau$ 不是函数接口类型，或者如果 $\tau$ 是函数接口类型但没有函数类型（§9.9），归约为 `false`。

# 类型推断

# 归约 18.2

- 否则，令方法引用表达式的目标函数类型为 $\tau$ 的函数类型。如果方法引用是不精确的（§15.13.1），且函数类型的参数中有一个或多个参数不是有效类型，则该约束归约为 `false`。
- 否则，如果方法引用是不精确的且函数类型的结果既不是 `void` 也不是有效类型，则约束归约为 `false`。
- 否则，$E_1, ..., E_n$ 为函数类型 `throws` 子句中不是有效类型的类型。$X_1, ..., X_m$ 为方法引用编译时声明（§15.13.2）调用处 `throws` 子句中的受检异常（根据函数类型的参数和返回类型推导得出）。那么有两种情况：
    - 如果 $n = 0$（函数类型的 `throws` 子句仅由有效类型组成），则在 `throws` 子句中，约束归约为 `false`；否则，约束归约为对于所有 $i (1 \le i \le m)$，$X_i$ 不是任何有效类型的子类型。
    - 如果 $n > 0$，约束归约为一组子类型约束：对于所有 $i (1 \le i \le m)$，如果 $X_i$ 不是 `throws` 子句中任何有效类型的子类型，则约束包括对于所有 $j (1 \le j \le n)$，$X_i <: E_j$。此外，对于所有 $j (1 \le j \le n)$，约束归约为边界 `throws` $E_j$。

受检异常的约束是与返回类型的约束分开处理的，因为返回类型的兼容性包含了方法的适用性（§18.5.1），而异常则仅取决于重载解析完成后的调用类型（§18.5.2）。这可以通过将异常兼容性包含在 lambda 表达式兼容性的定义中（§15.27.3）来简化，但这会导致一些意想不到的情况，即通过显式 lambda 主体更改的重载可能会抛出异常。

lambda 主体抛出的异常在确定 (i) lambda 的参数以及 (ii) 主体中表达式的结果类型之前是无法确定的。（第二个要求是为了考虑泛型方法调用，例如，相同类型同时出现在返回类型和 `throws` 子句中）。我们要求这两者根据目标类型 $\tau$ 推导出来都是有效的。

一个结果是，从其他 lambda 表达式返回的 lambda 表达式无法从其抛出的异常生成约束。这些约束只能从顶层 lambda 表达式生成。

注意，处理函数类型 `throws` 子句中出现多个推断的情况并不是保持完备性的。其中任意一个变量本身都能满足“每个受检异常都必须声明”的约束，但我们无法确定哪一个是预期的。因此，为了可预测性，我们对它们都进行约束。

# 18.3 合并

随着边界集在推断过程中生成和增长，可能会从原始边界的断言推断出新的边界。合并过程识别这些新边界并将它们添加到边界集中。

合并可能发生在两种场景中。一种场景是边界集包含互补的边界对；这暗示了如 §18.3.1 中指定的新的约束公式。另一种场景是边界集包含涉及捕获转换的边界；这暗示了新的边界，并可能意味着如 §18.3.2 中指定的新的约束公式。在两种场景下，任何新的约束公式都会被归约，新的边界会被添加到边界集中。这可能会触发进一步的合并；最终，集合将达到固定点且无法再推断出边界。

如果边界集的合并达到了固定点，且集合不包含边界 `false`，则边界集具有以下属性：

- 对于推断变量的有效下界 $L$ 和有效上界 $U$ 的每个组合，$L < U$。
- 边界提到的每个推断变量都有实例化，该边界通过相应的替换得到满足。
- 给定依赖 $\alpha = \beta$，$\alpha$ 的每个边界都匹配 $\beta$ 的边界，反之亦然。
- 给定依赖 $\alpha < \beta$，$\alpha$ 的每个下界都是 $\beta$ 的下界，每个上界都是 $\alpha$ 的上界。

关于合并达到固定点的断言略微简化了问题。基于 Kennedy 和 Pierce 的工作《具有变性的名义子类型的可判定性》，该属性可以通过证明出现在边界集中的类型集合是有限的来建立论证。该论证依赖于两个假设：

- 在归约子类型约束时不会生成新的捕获变量（§18.2.3）。
- 不解析扩展的继承路径。

该规范目前不保证这些属性（它在归约子类型约束时对通配符的处理是不精确的，并且不检测扩展的继承路径，但在未来的版本中可能会这样做。（这不是新问题：Java 子类型算法也面临不终止的风险）。）

## 18.3.1 互补边界对

（在本节中，$s$ 和 $\tau$ 是推断变量或类型，$v$ 是有效类型。为了简洁，形式为 $\alpha = \tau$ 的边界也可以匹配形式为 $T = \alpha$ 的边界。）

当边界集包含一对匹配以下规则之一的边界对时，将隐含一个新的约束公式：

- $\alpha = s$ 和 $\tau$ 意味着 $S < \tau$
- $\alpha = s$ 和 $\alpha < \tau$ 意味着 $S < \tau$
- $\alpha = s$ 和 $T < \tau$ 意味着 $T < S$
- $S < \alpha$ 和 $\alpha < \tau$ 意味着 $S < \tau$
- $\alpha = U$ 和 $u = S$ 意味着 $S(\alpha:=U) = T[(\alpha:=U)]$
- $\alpha = U$ 和 $s < T$ 意味着 $S(\alpha:=U) <: T[(\alpha:=U)]$

当边界集包含一对边界 $\alpha < s$ 和 $\alpha < \tau$，且存在形式为 $G<S_i, ..., S_j>$ 的 $S$ 的类型以及形式为 $G<T_i, ..., T_n>$ 的 $T$ 上类型时，那么对于所有 $i (1 \le i \le n)$，如果 $S_i$ 和 $T_i$ 是类型（而非通配符），则隐含约束 $S_i = T_i$。

## 18.3.2 涉及转换的边界

当边界集包含形式为 $G<\alpha_i, ..., \alpha_n> = capture(G<A_i, ..., A_n>)$ 的边界时，将隐含新的边界并可能隐含新的约束公式，如下：令 $P_i, ..., P_n$ 代表 $G$ 的参数，$B_i, ..., B_n$ 代表这些参数的边界。令 $\theta$ 代表替换 $[P_i:=\alpha_i, ..., P_n:=\alpha_n]$。令 $R$ 为非推断变量类型。

此外，对于所有 $i (1 \le i \le n)$：

- 如果 $A_i$ 不是通配符，则隐含 $\alpha_i = A_i$。
- 如果 $A_i$ 是形式为 `?` 的通配符：
    - $\alpha_i = R$ 隐含 `false`
    - $\alpha_i < R$ 隐含约束公式 $B_i <: R$
    - $R < \alpha_i$ 隐含 `false`

# 18.4 解析

给定一个不包含 `false` 的边界集，边界提到的推断变量子集可以解析。这意味着为每个推断变量添加一个满意的实例化，直到所有请求的变量都有实例化。

边界集中的依赖关系可能按特定顺序解析变量，或解析额外的变量。依赖关系如下：

- 给定以下形式之一的边界，其中 $\tau$ 是推断变量 $\beta$ 或提到 $\beta$ 的类型：



# 类型推断

## 推断的使用

### 18.5.1 适用性

给定一个未提供显式类型的方法调用，确定一个潜在适用泛型方法 $m$ 是否适用的过程如下：

- 其中 $P_1, ..., P_p$ ($p \ge 1$) 是 $m$ 的参数，$\alpha_1, ..., \alpha_p$ 为推断变量，令 $\theta$ 为替换 $[P_1:=\alpha_1, ..., P_p:=\alpha_p]$。
- 根据 §18.1.3 描述，从 $P_1, ..., P_p$ 的声明边界生成初始边界集 $B_0$。
- 对于所有 $i$ ($1 \le i \le p$)，如果 $F_i$ 出现在 $m$ 的 `throws` 子句中，则隐含边界 `throws` $\alpha_i$。这些边界（如果有）被整合到 $B_0$ 中产生新的边界集 $B_1$。
- 按如下方式生成一组约束公式 $\mathcal{C}$。令 $F_1, \dots, F_n$ 为 $m$ 的形式参数类型，令 $e_1, \dots, e_k$ 为调用的实际参数表达式。那么：
  - 通过严格调用测试适用性：
    如果 $k \neq n$，或者存在 $i$ ($1 \le i \le n$) 使得 $e_i$ 与适用性相关（§15.2.2）且满足 (i) $e_i$ 是原始类型的独立表达式但 $F_i$ 是引用类型，或 (ii) $F_i$ 是原始类型但 $e_i$ 是原始类型的独立表达式；则方法不适用且无需继续。
    否则，对于所有 $i$ ($1 \le i \le n$)，$\mathcal{C}$ 包含与适用性相关的 $e_i$。
  - 通过松散调用测试适用性：
    如果 $k \neq n$，则方法不适用且无需继续。
    否则，$\mathcal{C}$ 包含所有 $i$ ($1 \le i \le k$) 与适用性相关的 $e_i$。
  - 通过变长参数测试适用性：
    令 $F'_1, \dots, F'_k$ 为 $m$ 的前 $k$ 个变长参数类型（15.12.2.4）。$\mathcal{C}$ 包含所有 $i$ ($1 \le i \le k$) 与适用性相关的 $e_i$。
- 简化 $\mathcal{C}$（18.2），并将产生的边界整合到 $B_1$ 中产生新的边界集 $B_2$。
- 最后，如果 $B_2$ 不包含边界 `false` 且 $B_2$ 中的所有推断变量解析成功，则方法 $m$ 适用。

考虑以下调用和赋值：

```java
List<Number> ln = Arrays.asList(1, 2.0);
```

显而易见（由于变长参数），该方法既不适用于严格调用（15.12.2.2），也不适用于松散调用（15.12.2.3）。但由于没有其他候选者，在第三阶段检查方法的变长参数适用性。

初始边界集 $B$ 是单个推断变量 $\alpha$ 的平凡上界：

```
\alpha <: Object
```

初始约束集如下：

```
{<1 \to \alpha, <2.0 \to \alpha}
```

这些被简化为新的边界集 $B_j$：

```
\alpha <: Object, Integer <: \alpha, Double <: \alpha
```

我们已经证明了该方法是适用的；由于没有其他候选者，它是最具体的适用方法。尽管如此，调用类型及其与赋值目标类型的兼容性在进一步推断发生之前无法确定，如下一节所述。

### 18.5.2.1 多方法调用兼容性

如果方法调用表达式是多表达式（§15.12），其与目标类型 $\tau$ 的兼容性按如下确定。

- 如果方法调用表达式出现在严格调用上下文中且 $\tau$ 是一个原始类型，则该表达式与 $\tau$ 不兼容。
- 否则：
  - 令 $B_2$ 为通过归约产生的边界集，用于证明 $m$ 在 §18.5.1 中是可用的。
    （尽管在 §18.5.1 中需要证明 $B_2$ 中的推断变量是可以解析的，但为了建立由该解析集产生的不稳定性，这些解析*不被视为* $B_2$ 的部分）
  - 令 $B_3$ 为按照如下方式从 $B_2$ 派生出的边界集。

令 $R$ 为 $m$ 的返回类型，令 $\theta$ 为 §18.5.1 中定义的替换式 $[P_i :=\alpha_i, \dots, P_j:=\alpha_j]$，用于将 $m$ 的类型参数替换为推断变量，令 $\tau$ 为调用的目标类型。

- 在 §18.5.1 的约束集归约期间，为了使方法可用需要进行未检查转换，约束公式 $|R| \to \tau$ 被归约并合并到 $B_3$ 中。
- 否则，如果 $\tau$ 是参数化类型 $G\langle A_i, \dots, A_n\rangle$，且 $A_i, A_n$ 之一是通配符，则对于新的推断变量 $\beta_i, \dots, \beta_n$，约束公式 $G\langle\beta_i, \dots, \beta_n\rangle \to \tau$ 被归约并合并，同边界 $G\langle\beta_i, \dots, \beta_n\rangle, \beta_j := \text{capture}(G\langle A_i, \dots, A_n\rangle)$ 一并在 $B_3$ 中。
- 否则，如果 $R \theta$ 是推断变量 $\alpha$，且以下任一条件成立：
  - $\tau$ 是引用类型但不是通配符参数化类型，且 (i) $B_2$ 包含形式为 $\alpha = s$ 或 $s <: \alpha$ 的边界，其中 $s$ 是通配符参数化类型；或 (ii) $B_2$ 包含形式为 $S_1 <: \alpha$ 和 $S_2 <: \alpha$ 的边界，其中 $S_1$ 和 $S_2$ 的父类型是同一个泛型类或接口的不同参数化。
  - $\tau$ 是泛型类或接口 $G$ 的参数化，且 $B_2$ 包含形式为 $\alpha = s$ 或 $s <: \alpha$ 的边界，其中不存在形式为 $G<...>$ 的类型是 $s$ 的父类型，但原始类型 $|G<...>$ 是 $S$ 的父类型。
  - $\tau$ 是原始类型，且 §5.1.7 中提到的原始类型包装类是 $B_2$ 中 $\alpha$ 的实例化、上界或下界。
  则 $\alpha$ 在 $B_2$ 中被解析，且所得 $\alpha$ 实例化的捕获为 $U$，约束公式 $U \to \tau$ 被归约并合并到 $B_3$ 中。
- 否则，约束公式 $|R| \to \tau$ 被归约并合并到 $B_3$ 中。

- 如果 $B_3$ 不包含边界 `false` 且 $B_3$ 中所有推断变量的解析均成功（§18.4），则方法调用表达式与 $T$ 兼容。

考虑上一节中的示例：

```java
List<Number> ln = Arrays.asList(1, 2.0);
```

识别出的最具体可用方法为：

```java
public static <T> List<T> asList(T... a)
```

为了完成方法调用的类型检查，我们必须确定它是否与目标类型 `List<Number>` 兼容。

上一节中用于证明可用性的边界集 $B_2$ 为：

```
\alpha <: Object, Integer <: \alpha, Double <: \alpha
```

新的约束公式设置如下：

```
{List<\alpha> \to List<Number>}
```

这种兼容性为 $\alpha$ 生成了一个等式边界，该边界包含在新的边界集 $B_3$ 中：

```
\alpha <: Object, Integer <: \alpha, Double <: \alpha, \alpha = Number
```

这些边界被平凡地解析了：

```
\alpha = Number
```

## 18.4 类型推断 解析

- 推断变量 $\alpha$ 依赖于推断变量 $\beta$ 的解析，当且仅当存在推断变量 $\gamma$，使得 $\alpha$ 依赖于 $\gamma$ 的解析，且 $\gamma$ 依赖于 $\beta$ 的解析。
- 推断变量 $\alpha$ 依赖于其自身的解析。

给定一组需要解析的推断变量集合，令 $u$ 为该集合以及该集合中至少一个变量的解析赖以依赖的所有变量的并集。

如果 $u$ 中的每个变量都是一个实例化，则解析成功且此过程终止。

否则，令 $\{\alpha_1, ..., \alpha_n\}$ 为 $u$ 中未实例化变量的一个非空子集，使得：(i) 对于所有 $i$ ($1 \leq i \leq n$)，如果 $\alpha_i$ 依赖于变量 $\beta$ 的解析，则要么存在一个实例化，要么存在某个 $j$ 使得 $\beta = \alpha_j$；且 (ii) $\{\alpha_1, ..., \alpha_n\}$ 不存在具有此属性的非空真子集。解析通过根据边界集中的边界为每个 $\alpha_i, ..., \alpha_n$ 生成实例化来进行：

- 如果边界集不包含形式为 $G<...$ 的边界，且对于所有 $i$ ($1 \leq i \leq n$) 有 $\alpha_i = ... = \text{capture}(G<...)$，则为每个 $\alpha_i$ 定义一个候选实例化 $T_i$；
- 如果 $\alpha_i$ 有一个或多个下界 $L_i, ..., L_k$，则 $T_i = \text{lub}(L_i, ..., L_k)$ ($\S4.10.4$)。
- 否则，如果边界集包含 `throws` $\alpha_i$，且 $\alpha_i$ 的每个上界都是 `RuntimeException` 的超类，则 $T_i = \text{RuntimeException}$。
- 否则，如果 $\alpha_i$ 有相应的真边界 $U_i, ..., U_k$，则 $T_i = \text{glb}(U_i, ..., U_k)$ ($\S5.1.10$)。

将边界 $\alpha_i = T_i, ..., \alpha_n = T_n$ 整合到当前的边界集中。

如果结果不包含边界 `false`，则该结果成为新的边界集，并通过选择一组新的变量进行实例化（如有必要）来继续解析，如上所述。

否则，结果包含边界 `false`，因此将通过执行以下步骤对 $\{\alpha_i, ..., \alpha_n\}$ 进行第二次实例化尝试。

- 如果边界集包含形式为 $G<...$ 的边界，$\alpha_i = ... = \text{capture}(G<...)$（对于某个 $i$ ($1 \leq i \leq n$)），或者在上一步骤中产生的边界集包含边界 `false`；则令 $Y_i, ..., Y_n$ 为新的类型变量，其边界如下：
  - 对于所有 $i$ ($1 \le i \le n$)，如果 $\alpha_i$ 有一个或多个真边界 $L_j, ..., L_k$，则令 $Y_i$ 的下界为 $\text{lub}(L_j, ..., L_k)$；若不是，$Y_i$ 无下界。
  - 对于所有 $i$ ($1 \le i \le n$)，其中 $\alpha_i$ 有上界 $U_j, ..., U_k$，令 $Y_i$ 的上界为 $\text{glb}(U_j, ..., U_k)$，其中 $\theta$ 是替换 $[\alpha_i:=Y_j, ..., \alpha_i:=Y_n]$。

如果类型变量 $Y_j, ..., Y_n$ 没有良好的边界（即：下界不是任何上界的子类型，或者交集类型不一致），则解析失败。

否则，对于所有 $i$ ($1 \le i \le n$)，从当前边界集中移除所有形式为 $G<..., \alpha_i = ... = \text{capture}(G<...>)$ 的边界，并整合边界 $\alpha_i:=Y_i, ..., \alpha_n:=Y_n$。

如果结果不包含边界 `false`，则该结果成为新的边界集，并通过选择一组新的变量进行实例化（如有必要）来继续解析，如上所述。

否则，结果包含边界 `false`，解析失败。实例化推断变量的第一种方法根据该变量的边界推导出实例化。然而，有时复杂的依赖关系意味着结果不在变量的边界范围内。在这种情况下，将执行不同的实例化方法，允许捕获（$\S5.1.10$）：引入新的类型变量，其边界从推断变量的边界推导出。注意，这些“捕获”变量的下界仅使用真类型进行计算；这对于避免尝试对未实例化的类型变量进行类型检查至关重要。

根据上述定义的推断过程，将在编译时执行以下分析。

## 依赖关系

如果 $\alpha$ 出现在形式为 $G<..., \alpha, ...> = \text{capture}(G<...,>)$ 的边界左侧，则 $\beta$ 依赖于 $\alpha$ 的解析。否则，$\alpha$ 依赖于 $\beta$ 的解析。

- 出现在形式为 $G<..., \alpha, ...> = \text{capture}(G<...,>)$ 的边界左侧的推断变量 $\alpha, ...$ 依赖于该边界中提到的每个其他推断变量（位于等号两侧）。

- 如果 $A_i$ 是形式为 `? extends T` 的通配符：
  - $\alpha_i = R$ 隐含 `false`
  - 如果 $B_i$ 是 `Object`（对象类型），则 $\alpha_i <: R$ 隐含约束公式 $T <: R$
  - 如果 $T$ 是 `Object`（对象类型），则 $\alpha_i <: R$ 隐含约束公式 $B_i <: R$
  - $R <: \alpha_i$ 隐含 `false`

- 如果 $A_j$ 是形式为 `? super T` 的通配符：
  - $\alpha_j = R$ 隐含 `false`
  - $\alpha_j <: R$ 隐含 $B_j <: R$
  - $R <: \alpha_j$ 隐含 $R <: T$

## 基础关系

$\alpha = T$

$\alpha <: T$

$T = \alpha$

$T <: \alpha$



最后，我们对 `asList` 的声明返回类型进行替换，确定方法调用的类型为 `List<Number>`；显然，这与目标类型兼容。

这种推断策略与《Java 语言规范》SE 7 版不同，后者会像我们在上一节中所做那样，在考虑调用的目标类型之前根据其下界来实例化 $\alpha$。这将导致错误类型，因为结果类型不是 `List<Number>` 的子类型。

在各种特殊情况下，根据 $B_2$ 中出现的边界，我们会尽早解析出现在调用返回类型中的推断变量。此举是为了避免在常规约束 $\theta \to \tau$ 中出现不利的情况，但遗憾的是，通过尽早解析变量，我们无法利用本可以推断出的边界。在某些情况下，如果稍后从调用参数（如隐含的 lambda 表达式）中推断出的边界已经存在于 $B_2$ 中，可能会导致不同的结果。

## 18.5.2.2 额外参数约束

在考虑了方法调用表达式的参数表达式可能隐含的额外约束后，确定所选方法的调用如下：

- 如果方法调用表达式是多态表达式，令 $B_j$ 为 §18.5.2.1 中生成的边界集，用于证明与方法调用的实际目标类型兼容。
- 如果方法调用表达式不是多态表达式，令 $B_j$ 等于通过归约产生的 §18.5.1 中的边界集，用于证明 $m$ 在 §18.5.1 中是用的。

（尽管在 §18.5.1 和 §18.5.2.1 中需要证明边界集中的推断变量是可以解析的，但这些解析步骤产生的实例化不视为 $B_j$ 的部分。）

按照如下方式生成约束公式集 $c$。

令 $e_1, ..., e_k$ 为方法调用的实际参数表达式。

如果 $m$ 是按严格调用的，令 $F_1, ..., F_k$ 为 $m$ 的形式参数类型；如果 $m$ 是按松散调用的，令 $F_1, ..., F_k$ 为 $m$ 的参数类型（§122.4）。

令 $\Theta$ 为替换式 $[F_1:=\alpha_1, \dots, F_k:=\alpha_k]$，其定义在 §18.5.1 中，用于将 $m$ 的类型参数替换为推断变量。

对于所有 $i$ ($1 \le i \le k$)：

- 如果 $e_i$ 不涉及兼容性，则 $c$ 包含 `<e_i \to \Theta>`。
- 根据 $e_i$ 的形式，可能包含额外的约束：
    - 如果 $e_i$ 是 lambda 表达式，`c` 包含 `<LambdaExpression \to \Theta>` 并对 lambda 体进行额外约束：
        - 对于块 lambda，递归地应用于结果表达式。
        - 对于多态实例创建表达式或多态方法调用表达式，`c` 包含在 §18.5.2.2 中推断多态表达式调用体时出现的所有公式。
        - 对于括号表达式，递归地应用于包含的表达式。
        - 对于条件表达式，递归地应用于第二个和第三操作数。
        - 对于 lambda 表达式，递归地应用于 lambda 体。
    - 如果 $e_i$ 是方法引用，`c` 包含 `MethodReference \to F_i`。
    - 如果 $e_i$ 是多态实例创建表达式或多态方法调用表达式，`c` 包含在 18.5 使用中推断多态表达式调用体时的所有公式。
    - 如果 $e_i$ 是括号表达式，这些规则递归地应用于包含的表达式。
    - 如果 $e_i$ 是条件表达式，这些规则递归地应用于第二个和第三操作数。

只要 $c$ 不空，重复以下过程，从边界 $B_i$ 开始，将新边界积累到“当前”边界集中，最终产生一个新的边界集 $B_i$：

1. 在 $c$ 中选择一个子集，满足属性：对于每个约束，没有输入变量可以影响 $c$ 中另一个约束的输出变量。“输入变量”和“输出变量”定义见下文。推断变量 $\alpha$ 可以影响推断变量 $\beta$，如果 $\alpha$ 依赖于 $\beta$ 的解析（§18.4），或者反之亦然；如果存在第三个变量 $\gamma$，使得 $\alpha$ 可以影响 $\gamma$ 且 $\gamma$ 可以影响 $\beta$。

如果该子集为空，则约束之间的依赖图中存在循环（或循环）。在这种情况下，考虑 $c$ 中参与依赖循环（或循环）且不依赖于循环之外约束的约束。从这些被考虑的约束中选择单个约束，如下：

- 如果任何被考虑的约束具有形式为 `Expression \to D`，则所选约束是该形式的约束，其表达式位于其他被考虑的该形式约束的表达式的左侧（§3.5）。
- 如果没有被考虑的约束具有 `Expression \to T`，则所选的约束是允许表达式位于所有其他被考虑约束的表达式左侧的被考虑约束。

- 将所选的约束从 $c$ 中移除。
- 所有所选约束的输入变量 $\alpha_2, ..., \alpha_m$ 被解析。
- 如果 $T_2, ..., T_m$ 是 $\alpha_2, ..., \alpha_m$ 的实例化，则将替换 $[\alpha_2:=T_2, ..., \alpha_m:=T_m]$ 应用于每一个约束。
- 替换产生的约束被简化并合并到当前边界集合中。
- 最后，如果 $B_4$ 不包含边界值 *false*，则 $B_4$ 中的推断变量被解析。

如果解析是从针对推断变量 $\alpha_2, ..., \alpha_p$ 的实例化 $T_1, ..., T_p$ 开始的，令 $\theta'$ 为替换 $[P_1:=T_1, ..., P_p:=T_p]$。那么：

- 如果在 §18.5.1 的约束集简化过程中，为了使方法适用需要未检查转换，则通过将 $\theta'$ 应用于 $m$ 的类型的参数类型获取 $m$ 的调用类型的参数，并且 $m$ 的调用类型的返回类型和异常类型由 $m$ 的类型的返回类型和异常类型的擦除给出。
- 如果为了使方法适用不需要未检查转换，则 $m$ 的调用类型通过将 $\theta'$ 应用于 $m$ 的类型获得。

如果 $B_4$ 包含边界值 *false*，或者解析失败，则发生编译错误。

简化额外参数约束的过程可能需要仔细排序形如 `<Expression \to T, \LambdaExpression \to throws T>` 和 `<MethodReference \to throws T>` 形式的约束公式。为了便于这种排序，这些约束的*输入*变量定义为：

- 对于 `<LambdaExpression \to T>`:
    - 如果 $\tau$ 是推断变量，它是（唯一的）输入变量。
    - 如果 $\tau$ 是函数式接口，且可以从 $\tau$ 推导出函数类型（§15.27.3），则输入变量包括：i) 如果 lambda 表达式是隐式类型的，则函数类型参数类型中提到的推断变量；以及 (ii) 如果函数的返回类型 $R$ 不是 *void*，对于 lambda 体中的每个结果表达式 $e$（或如果体本身是一个表达式，则对于体本身），`<e \to R>` 的输入变量。
    - 否则，没有输入变量。

- 对于 `<LambdaExpression \to throws T>`:
    - 如果 $T$ 是推断变量，它是（唯一的）输入变量。
    - 如果 $T$ 是函数式接口类型，并且可以如 §15.27.3 描述地推导出函数类型，则输入变量包括：i) 如果 lambda 表达式是隐式类型的，则函数类型参数类型中提到的推断变量；以及 (ii) 函数返回类型中提到的推断变量。
    - 否则，没有输入变量。

- 对于 `<MethodReference \to T>`:
    - 如果 $T$ 是预测变量，它是（唯一的）输入变量。
    - 如果 $T$ 是带有函数类型的函数式接口类型，且方法引用是不精确的（§15.13.1），则输入变量是函数类型参数类型中提到的推断变量。
    - 否则，没有输入变量。

- 对于 `<MethodReference \to throws T>`:
    - 如果 $T$ 是推断变量，它是（唯一的）输入变量。
    - 如果 $T$ 是带有函数类型的函数式接口类型，且方法引用是不精确的（§15.13.1），则输入变量是函数类型参数类型中提到的推断变量以及函数类型的返回类型。
    - 否则，没有输入变量。

- 对于 `<Expression \to T>`，如果 $Expression$ 是括号表达式：
    其中 $Expression$ 包含的表达式为 $Expression'$，则输入变量是 `<Expression' \to T>` 的输入变量。

- 对于 `<ConditionalExpression \to T>`:
    其中条件表达式的形为 $e_1 ? e_2 : e_3$，则输入变量是 `<e_2 \to T>` 和 `<e_3 \to T>` 的输入变量。

- 对于所有其他约束形式，没有输入变量。

这些约束的*输出变量*是约束右侧类型 $\tau$ 中提到的所有不是输入变量的变量。

# 类型推断

## 推断的用途

### 18.5.3 函数式接口参数化推断

当具有显式参数类型 $P_i, ..., P_n$ 的 lambda 表达式目标是至少包含一个通配符类型的函数式接口类型 $F<A_i, ..., A_m>$ 时，可以如下所示推导出 $F$ 的参数化作为 lambda 表达式的基目标类型。

令 $Q_i, ..., Q_k$ 为类型 $F<\alpha_i, ..., \alpha_m>$ 的函数类型的参数类型，其中 $\alpha_i, ..., \alpha_m$ 是新变量。

如果 $n \neq k$，则不存在参数化。否则，形成一组约束公式，对于所有 $i$ ($1 \leq i \leq n$)，`<P_i = Q_i>`。该约束公式被简化形成边界 $B$。

如果 $B$ 包含边界值 $false$，则不存在参数化。否则，构造一个新的函数式接口类型参数化 $F<A'_i, ..., A'_m>$，如下（对于 $1 \leq i \leq m$）：

- 如果 $B$ 包含 $\alpha_i, T$ 的实例化（§18.1.3），则 $A'_i = T$。
- 否则，$A'_i = A_i$。

如果 $F<A'_i, ..., A'_m>$ 不是一个良构类型（即类型参数不是边界），或者 $F<A'_i, ..., A'_m>$ 不是 $F<\alpha_i, ..., \alpha_m>$ 的子类型，则不存在参数化。否则，推断出的参数化是：如果所有参数都是类型，则是 $F<A'_i, ..., A'_m>$；如果一个或多个参数仍是通配符，则是 $F<A'_i, ..., A'_m>$ 的非通配符参数化（§9.9）。

为了确定通配符参数化函数式接口的类型，我们必须用特定类型“实例化”通配符参数。“默认”方法是简单地将通配符替换为它们的边界，如 §9.8 所述，但在 lambda 表达式的显式参数类型与通配符边界对应的情况下，这会产生伪错误。例如：

```
Predicate<? super Integer> p = (n) -> n.equals(n);
```



该 lambda 表达式是一个 `Predicate<Number>`，它是 `Predicate<? super Integer>` 的子类型，而不是 `Predicate<Integer>`。本节中的分析用于推断 `Number` 是参数的合适选择。此处的分析虽然在通用类型推断中被描述，但刻意保持简单。唯一的约束是等式约束，这意味着简化等于简单的匹配。一种强大的策略还可以从 lambda 表达式体推断约束，但考虑到周围和/嵌套调用的可能的交互，这将引入许多额外的复杂性。

### 18.5.4 更具体的推断

当测试一个适用的方法比另一个方法更具体（§15.12.5）时，如果第二个方法是泛型的，则需要测试是否可以推断第二个方法类型参数的实例化，使得第一个方法比第二个方法具体。

令 $m_1$ 和 $m_2$ 为方法。当 $m_2$ 具有类型参数 $P_1, ..., P_{n_2}$ 时，令 $\alpha_1, ..., \alpha_{p_2}$ 为推断变量，并令 $\theta$ 为替换 $[P_1:=\alpha_1, ..., P_{n_2}:=\alpha_{p_2}]$。

令 $e_1, ..., e_k$ 为相应调用的参数表达式。那么：

- 如果 $m_1$ 和 $m_2$ 通过严格或宽松调用适用（§15.12.2, 15.12.3），则令 $S_1, ..., S_k$ 为 $m_1$ 的形式类型，并令 $T_1, ..., T_k$ 为 $\theta$ 应用于 $m_2$ 的形式类型的结果。
- 如果 $m_1$ 和 $m_2$ 通过变量数组调用适用（§15.12.4），则令 $S_1, ..., S_k$ 为 $m_1$ 的前 $k$ 个数组类型，并令 $T_1, ..., T_k$ 为 $\theta$ 应用于 $m_2$ 的前 $k$ 个数组类型的结果。

注意不要对 $S_1, ..., S_k$ 应用替换；即使 $m_2$ 是泛型的，$m_1$ 的类型参数也被视为类型变量，而不是推断变量。

确定 $m_1$ 比 $m_2$ 更具体的过程如下：

- 首先，根据 $P_2, ..., P_p$ 的声明边界生成初始边界集合 $B$，如 §18.1.3 所示。
- 其次，对于每个 $i$ ($1 \le i \le k$)，生成一组约束公式或边界。

如果 $T_i$ 是有效类型，则结果为 true（即 $S_i$ 对于 $e_i$ 更具体，§15.12.5），否则为 false。（注意 $S_i$ 总是有效类型。）

否则，如果 $S_i$ 和 $T_i$ 不是函数式接口，则生成约束公式 $S_i <: T_i$。

否则，如果 $S_i$ 的接口是 $T_i$ 接口的父接口或子接口（其中 $S_i$ 或 $T_i$ 是交类型，$S_i$ 的某个接口是 $T_i$ 的接口的父接口或子接口），则生成约束公式 $S_i <: T_i$。

否则，令 $MT_{S_i}$ 为 $S_i$ 捕获的函数类型，$MT_{S_i}'$ 为 $S_i$ 的函数类型（不捕获），并令 $MT_{T_i}$ 为 $T_i$ 的函数类型。如果 $MT_{S_i}$ 和 $MT_{T_i}$ 的形式参数或类型参数数量不同，或者 $MT_{S_i}$ 和 $MT_{T_i}'$ 的类型参数不同（§8.4.4），则结果为 false。

否则，根据 $MT_S$ 和 $MT_T$ 的类型参数、形式参数类型和返回类型生成以下约束公式。

- 令 $A_1, \dots, A_n$ 为 $MT_S$ 的类型参数，令 $B_1, \dots, B_n$ 为 $MT_T$ 的类型参数。
- 令 $\theta'$ 为替换 $[B_1=A_1, \dots, B_n=A_n]$。那么对于所有 $j(1 \le j \le n)$：
  - 如果 $A_j$ 的边界提到了 $A_1, \dots, A_n$ 中的一个，且 $B_j$ 的边界不是有效类型，则为 `false`。
  - 否则，如果 $X$ 是 $A_j$ 的边界且 $Y$ 是 $B_j$ 的边界，则 $\langle X=Y \theta' \rangle$。

如果 $B_j$ 提到了 $A_1, \dots, A_n$ 且 $B_j$ 的边界不是有效类型，那么产生等式约束会导致推断变量可能被超出范围的类型变量所绑定。由于用超出范围的类型变量重新实例化推断变量是没有意义的，我们倾向于在出现这种可能性时尽量避免这种情况。这种简化不是保持完备性的。（下文对形式参数类型和返回类型的处理也适用相同的注释。）

- 令 $U_1, \dots, U_k$ 为 $MT_S$ 的形式参数类型，令 $V_1, \dots, V_k$ 为 $MT_T$ 的形式参数类型。那么对于所有 $(1 \le j \le k)$：
  - 如果 $U_j$ 提到了 $A_1, \dots, A_n$ 中的一个且 $V_j$ 不是有效类型，则为 `false`。
  - 否则，$\langle V_j \ \theta' \rangle$，其中 $U'_1, \dots, U'_k$ 是 $MT_S$ 的形式参数类型，$A'_1, \dots, A'_n$ 是 $MT_T$ 的参数类型，$\langle V_j\{B_1=A'_1, \dots, B_n=A'_n\} \rangle = U'_j$。

- 令 $R_S$ 为 $MT_S$ 的返回类型，令 $R_T$ 为 $MT_T$ 的返回类型。那么：
  - 如果 $R_S$ 提到了 $A_1, \dots, A_n$ 中的一个且 $R_T$ 不是有效类型，则为 `false`。
  - 否则，如果 $e_i$ 是一个显式类型的 lambda 表达式：
    - 如果 $\gg R_T$ 是 `void`，则为 `true`。
    - $\gg$ 如果 $R_S$ 和 $R_T$ 是函数接口类型且 $e_i$ 至少有一个结果表达式，则对于 $e_i$ 中的每个表达式，重复整个步骤，直到 $R_S$ 下的约束对于给定的结果表达式比 $R_T \theta'$ 更具体。
    - $\gg$ 如果 $R_S$ 是原始类型而 $R_T$ 不是，且 $e_i$ 至少有一个结果表达式，且 $e_i$ 的每个结果表达式都是原始类型的独立表达式（§15.2），则为 `true`。
    - $\gg$ 如果 $R_T$ 是原始类型而 $R_S$ 不是，且 $e_i$ 至少有一个结果表达式，且 $e_i$ 的每个结果表达式要么是引用类型的独立表达式或者是多表达式，则为 `true`。
    - 否则，$R_S <: R_T \theta'$。
  - 否则，如果 $e_i$ 是带括号的表达式，则这些从 $R_S$ 和 $R_T$ 导出的约束规则递归应用于包含的表达式。
  - 否则，如果 $e_i$ 是条件表达式，则这些从 $R_S$ 和 $R_T$ 导出的约束规则递归地应用于第二个和第三个操作数。
  - 否则， `false`。

- 第三，如果 $m_2$ 可通过变长参数调用且具有 $k+1$ 个参数，那么其中 $S_{k+1}$ 是 $m_1$ 的第 $k+1$ 个变长参数类型，$T_{k+1}$ 是 $\theta$ 应用于 $m_2$ 的第 $k+1$ 个变长参数类型的结果，则生成约束 $S_{k+1} <: T_{k+1}$。

- 第四，生成的边界和约束公式被归并并合并到 $B$，产生边界集 $B'$。

如果 $B'$ 不包含边界 `false` 且 $B'$ 中所有推断变量的解析成功，则 $m_1$ 比 $m_2$ 更具体。

否则，$m_1$ 没有 $m_2$ 具体。

# 第 19 章 语法

本章重复了第 4、6-10、14 和 15 章中给出的语法规则，以及第 3 章中词法语法的关键部分，并使用了 §2.4 中的符号。

## 来自 §3 的产生式（词法结构）

- 标识符 (Identifier):
  - IdentifierChars 但不是关键字 (Keyword)、布尔字面量 (BooleanLiter) 或空字面量 (NullLiter)
- IdentifierChars:
  - JavaLetter [JavaLetterOrDigit]
- JavaLetter:
  - 任何是 "Java 字母"的 Unicode 字符
- JavaLetterOrDigit:
  - 任何是 "Java 字母或数字"的 Unicode 字符
- 类型标识符 (TypeIdentifier):
  - 标识符但 var
- 字面量 (Literal):
  - 整数字面量 (IntegerLiteral)
  - 浮点数字面量 (FloatingPointLiteral)
  - 布尔字面量 (BooleanLiteral)
  - 字符字面量 (CharacterLiteral)
  - 字符串字面量 (StringLiteral)
  - 空字面量 (NullLiteral)

## 来自 §4 的产生式（类型、值和变量）

类型 (Type):
- 原始类型 (PrimitiveType)
- 引用类型 (ReferenceType)

原始类型 (PrimitiveType):
- [Annotation] 数值类型 (NumericType)
- [Annotation] boolean

数值类型 (NumericType):
- 整数类型 (IntegralType)
- 浮点数类型 (FloatingPointType)

整数类型 (IntegralType):
- (其之一)
- byte short int long char

浮点数类型 (FloatingPointType):
- (其之一)
- float double

引用类型 (ReferenceType):
- 类或接口类型 (ClassOrInterfaceType)
- 类型变量 (TypeVariable)
- 数组类型 (ArrayType)

类或接口类型 (ClassOrInterfaceType):
- 类类型 (ClassType)
- 接口类型 (InterfaceType)

类类型 (ClassType):
- [Annotation] 类型标识符 [TypeArguments]
- 包名 (PackageName) . [Annotation] 类型标识符 [TypeArguments]
- 类或接口类型 . [Annotation] 类型标识符 [TypeArguments]

接口类型 (InterfaceType):
- 类类型 (ClassType)

类型变量 (TypeVariable):
- [Annotation] 类型标识符

```text
ArrayType:
  PrimitiveType Dims
  ClassOrInterfaceType Dims
  TypeVariable Dims
```

```text
Dims:
  [Annotation] [ ] [[Annotation] [ ]
```

```text
TypeParameter:
  [TypeModifier] TypeIdentifier [TypeBound]
```

```text
TypeParameterModifier:
  Annotation
```

```text
TypeBound:
  extends TypeVariable
```

```text
AdditionalBound:
  & InterfaceType
```

```text
TypeArguments:
  < TypeList >
```

```text
TypeList:
  TypeArgument ( , TypeArgument)*
```

```text
TypeArgument:
  ReferenceType
  Wildcard
```

```text
Wildcard:
  [Annotation] ? [AdditionalBounds]
```

```text
AdditionalBounds:
  extends ReferenceType
```

## 来自 §6 的产生式（名称）

```text
ModuleName:
  Identifier
  ModuleName . Identifier
```

```text
PackageName:
  Identifier
  PackageName . Identifier
```

```text
TypeName:
  TypeIdentifier
  PackageOrTypeName . Identifier
```

```text
ExpressionName:
  Identifier
  AmbiguousName . Identifier
```

```text
MethodName:
  Identifier
```

```text
PackageOrTypeName:
  Identifier
  PackageOrTypeName . Identifier
```

```text
AmbiguousName:
  Identifier
  AmbiguousName . Identifier
```

## 来自 §7 的产生式（包和模块）

CompilationUnit:
- OrdinaryCompilationUnit
- ModularCompilationUnit

OrdinaryCompilationUnit:
- [PackageDeclaration] [ImportDeclaration] [TypeDeclaration]

ModularCompilationUnit:
- [ImportDeclaration] ModuleDeclaration

PackageDeclaration:
- [PackageModifier] package Identifier [. Identifier]

PackageModifier:
- Annotation

ImportDeclaration:
- SingleTypeImportDeclaration
- TypeImportDemandDeclaration
- SingleStaticImportDeclaration
- StaticImportDemandDeclaration

SingleTypeImportDeclaration:
- import TypeName ;

TypeImportDemandDeclaration:
- import PackageOrTypeName . *

SingleStaticImportDeclaration:
- import static TypeName . Identifier ;

StaticImportDemandDeclaration:
- import static TypeName . *

TypeDeclaration:
- ClassDeclaration
- InterfaceDeclaration
;

```text
ModuleDeclaration:
  [Annotation] [open] module Identifier {. Identifier }
  { ModuleDirective } }
```

```text
ModuleDirective:
  requires [RequiresModifier] ModuleName ;
  exports PackageName [to ModuleName (, ModuleName)*];
  opens PackageName [to ModuleName {, ModuleName}*];
  uses TypeName;
  provides TypeName with TypeName (, TypeName)*;
```

```text
RequiresModifier:
  (其之一)
  transitive static
```

## 来自 §8 的产生式（类）

```text
ClassDeclaration:
  NormalClassDeclaration
  EnumDeclaration
```

```text
NormalClassDeclaration:
  [ClassModifier] class TypeIdentifier [TypeParameters]
  [Superclass] [Superinterfaces] ClassBody
```

```text
ClassModifier:
  (其之一)
  Annotation public protected private abstract static final strictfp
```

```text
TypeParameters:
  < TypeParameterList >
```

```text
TypeParameterList:
  TypeParameter ( , TypeParameter)*
```

```text
Superclass:
  extends ClassType
```

```text
Superinterfaces:
  implements InterfaceTypeList
```

```text
InterfaceTypeList:
  InterfaceType ( , InterfaceType )
```

```text
ClassBody:
  { ClassBodyDeclaration }
```

```text
ClassBodyDeclaration:
  ClassMemberDeclaration
  InstanceInitializer
  StaticInitializer
  ConstructorDeclaration
```

```text
ClassMemberDeclaration:
  FieldDeclaration
  MethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
```

```text
FieldDeclaration:
  {FieldModifier} UnannType VariableDeclaratorList;
```

```text
FieldModifier:
  (其一之一) Annotation public protected private
```



# 语法定义

## 变量声明

```text
static final transient volatile
```

```text
VariableDeclaratorList:
  VariableDeclarator (, VariableDeclarator)
```

```text
VariableDeclarator:
  VariableDeclaratorId [= VariableInitializer]
```

```text
VariableDeclaratorId:
  Identifier [Dims]
```

```text
VariableInitializer:
  Expression
  ArrayInitializer
```

## 类型系统

```text
UnannType:
  UnannPrimitiveType
  UnannReferenceType

UnannPrimitiveType:
  NumericType
  boolean

UnannReferenceType:
  UnannClassOrInterfaceType
  UnannTypeVariable
  UnannArrayType

UnannClassOrInterfaceType:
  UnannClassType
  UnannInterfaceType

UnannClassType:
  Identifier [TypeArguments]
  Package . [Annotation] Identifier [TypeArguments]
  UnannClassOrInterfaceType . [Annotation] Identifier [TypeArguments]

UnannInterfaceType:
  UnannClassVariable

UnannTypeVariable:
  Identifier

UnannArrayType:
  UnannPrimitiveType Dims
  UnannClassOrInterfaceType Dims
  UnannTypeVariable Dims
```

## 方法声明

```text
MethodDeclaration:
  {MethodModifier} MethodHeader MethodBody

MethodModifier:
  (其一之一)
  Annotation public protected private
  abstract static final synchronized native strictfp

MethodHeader:
  Result MethodDeclarator [Throws]
  TypeParameters [Annotation] Result MethodDeclarator [Throws]

Result:
  UnannType
  void

MethodDeclarator:
  Identifier ( [ReceiverParameter ,] [FormalParameterList] ) Dims

ReceiverParameter:
  [Annotation] UnannType [Identifier .] this

FormalParameterList:
  {FormalParameter , FormalParameter}

FormalParameter:
  {VariableModifier} UnannType VariableDeclaratorId
  VariableArityParameter

VariableArityParameter:
  {VariableModifier} UnannType [Annotation] ... Identifier

VariableModifier:
  Annotation
  final

Throws:
  throws ExceptionTypeList

ExceptionTypeList:
  ExceptionType {, ExceptionType}
```

### 异常类型

```text
ExceptionType:
  ClassType
  TypeVariable
```

### 方法体与初始化器

```text
MethodBody:
  Block
  ;

InstanceInitializer:
  Block

StaticInitializer:
  static Block
```

## 构造器声明

```text
ConstructorDeclaration:
  {ConstructorModifier} ConstructorDeclarator [Throws] ConstructorBody

ConstructorModifier:
  (其一之一) Annotation public protected private

ConstructorDeclarator:
  [TypeParameters] SimpleTypeName ( [ReceiverParameter ,] [FormalParameterList] )

SimpleTypeName:
  TypeIdentifier

ConstructorBody:
  { [ExplicitConstructorInvocation] [BlockStatements] }

ExplicitConstructorInvocation:
  [TypeArguments] this ( [ArgumentList] );
  [TypeArguments] super ( [ArgumentList] );
  ExpressionName . [TypeArguments] super ( [ArgumentList] );
  Primary . [TypeArguments] super ( [ArgumentList] );
```

## 枚举声明

```text
EnumDeclaration:
  {ClassModifier} enum TypeIdentifier [Superinterfaces] EnumBody
```

```text
EnumBody:
  { [EnumConstantList] [,,] [EnumBodyDeclarations] }
```

```text
EnumConstantList:
  EnumConstant {, EnumConstant}
```

```text
EnumConstant:
  {EnumConstantModifier} Identifier [ [ArgumentList] ] [ClassBody]
```

```text
EnumConstantModifier:
  Annotation
```

```text
EnumBodyDeclarations:
  ; [ClassBodyDeclaration]
```

## 接口声明 (来自 §9)

```text
InterfaceDeclaration:
  NormalInterfaceDeclaration
  AnnotationTypeDeclaration
```

```text
NormalInterfaceModifier:
  [InterfaceModifier] interface TypeIdentifier [TypeParameters] [ExtendsInterfaces] InterfaceBody
```

```text
InterfaceModifier:
  (其一之一)
  Annotation public protected private
  abstract static strictfp
```

```text
ExtendsInterfaces:
  extends InterfaceTypeList
```

```text
InterfaceBody:
  { [InterfaceMemberDeclaration] }
```

```text
InterfaceMemberDeclaration:
  ConstantDeclaration
  InterfaceMethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

```text
ConstantDeclaration:
  [ConstantModifier] UnannType VariableDeclaratorList;
```

```text
ConstantModifier:
  (其一之一) Annotation public
  static final
```

```text
InterfaceMethodDeclaration:
  [InterfaceMethodModifier] MethodHeader MethodBody
```

```text
InterfaceMethodModifier:
  (其一之一) Annotation public private
  abstract default static strictfp
```

```text
AnnotationTypeDeclaration:
  [InterfaceModifier] @interface TypeIdentifier AnnotationTypeBody
```

```text
AnnotationTypeBody:
  { [AnnotationTypeMemberDeclaration] }
```

```text
AnnotationTypeMemberDeclaration:
  AnnotationTypeElementDeclaration
  ConstantDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

```text
AnnotationTypeElementDeclaration:
  [AnnotationTypeElementModifier] UnannType Identifier () [Dims] [DefaultValue];
```

```text
AnnotationTypeElementModifier:
  (其一之一) Annotation public
  abstract
```

```text
DefaultValue:
  default ElementValue
```

## 注解语法

```text
Annotation:
  NormalAnnotation
  MarkerAnnotation
  SingleElementAnnotation

NormalAnnotation:
  @TypeName ( [ElementValuePairs] )

ElementValuePairs:
  ElementValuePair {, ElementValuePair}

ElementValuePair:
  Identifier = ElementValue

ElementValue:
  ConditionalExpression
  ElementValueArrayInitializer
  Annotation

ElementValueArrayInitializer:
  { [ElementValueList] [,] }

ElementValueList:
  ElementValue {, ElementValue}

MarkerAnnotation:
  @TypeName

SingleElementAnnotation:
  @TypeName ( ElementValue )
```

## 数组定义 (来自 §10)

```text
ArrayInitializer:
  { [VariableInitializerList] [,] }

VariableInitializerList:
  VariableInitializer {, VariableInitializer}
```

## 块与语句 (来自 §14)

```text
Block:
  { [BlockStatements] }
```

```text
BlockStatements:
  BlockStatement {BlockStatement}
```

```text
BlockStatement:
  LocalVariableDeclarationStatement
  ClassDeclaration
  Statement
```

```text
LocalVariableDeclarationStatement:
  LocalVariableDeclaration ;
```

```text
LocalVariableDeclaration:
  {VariableModifier} UnannType VariableDeclaratorList
```

```text
Statement:
  StatementWithoutTrailingSubstatement
  LabeledStatement
  IfThenStatement
  IfThenElseStatement
  WhileStatement
  ForStatement
```

```text
StatementNoShortIf:
  StatementWithoutTrailingSubstatement
  LabeledStatementNoShortIf
  IfThenElseStatementNoShortIf
  WhileStatementNoShortIf
  ForStatementNoShortIf
```

```text
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
```

```text
EmptyStatement:
  ;
```

```text
LabeledStatement:
  Identifier : Statement
```

```text
LabeledStatementNoShortIf:
  Identifier : StatementNoShortIf
```

```text
ExpressionStatement:
  StatementExpression ;
```

```text
StatementExpression:
  Assignment
  PreIncrementExpression
  PreDecrementExpression
  PostIncrementExpression
  PostDecrementExpression
  MethodInvocation
  ClassInstanceCreationExpression
```

### 条件语句

```text
IfThenStatement:
  if ( Expression ) Statement

IfThenElseStatement:
  if ( Expression ) StatementNoShortIf else Statement

IfThenElseStatementNoShortIf:
  if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

```text
AssertStatement:
  assert Expression [ : Expression ] ;
```

### Switch 语句

```text
SwitchStatement:
  switch ( Expression ) SwitchBlock
```

```text
SwitchBlock:
  { {SwitchBlockStatementGroup} {SwitchLabel} }
```

```text
SwitchBlockStatementGroup:
  SwitchLabels BlockStatements
```

```text
SwitchLabels:
  SwitchLabel {SwitchLabel}
```

```text
SwitchLabel:
  case ConstantExpression :
  case EnumConstantName :
  default :
```

```text
EnumConstantName:
  Identifier
```

### 循环语句

```text
WhileStatement:
  while ( Expression ) Statement

WhileStatementNoShortIf:
  while ( Expression ) StatementNoShortIf
```

```text
DoStatement:
  do Statement while ( Expression ) ;
```

```text
ForStatement:
  BasicForStatement
  EnhancedForStatement
```

```text
ForStatementNoShortIf:
  BasicForStatementNoShortIf
  EnhancedForStatementNoShortIf
```

```text
BasicForStatement:
  for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement
```

```text
BasicForStatementNoShortIf:
  for ( [ForInit] ; [Expression] ; [ForUpdate] ) StatementNoShortIf
```

```text
ForInit:
  StatementExpressionList
  LocalVariableDeclaration
```

```text
ForUpdate:
  StatementExpressionList
```

```text
StatementExpressionList:
  StatementExpression {, StatementExpression}
```

```text
EnhancedForStatement:
  for ( {VariableModifier} LocalVariableType VariableDeclaratorId : Expression ) Statement
```

```text
EnhancedForStatementNoShortIf:
  for ( {VariableModifier} LocalVariableType VariableDeclaratorId : Expression ) StatementNoShortIf
```



# ThrowStatement

```
throw Expression ;
```

# SynchronizedStatement

```
synchronized ( Expression ) Block
```

# TryStatement

```
try Block Catches
try Block [Catches] Finally
TryWithResourcesStatement
```

# Catches

```
CatchClause {CatchClause}
```

# CatchClause

```
catch ( CatchFormalParameter ) Block
```

# CatchFormalParameter

```
(VariableModifier) CatchType VariableDeclaratorId
```

# CatchType

```
UnannClassType (| | ClassType)
```

# Finally

```
finally Block
```

# TryWithResourcesStatement

```
try ResourceSpecification Block [Catches] [Finally]
```

# ResourceSpecification

```
( ResourceList [;] )
```

# ResourceList

```
Resource { ; }
```

# Resource

```
[VariableModifier] LocalVariableType Identifier = Expression
VariableAccess
```

## 来自 $15 (表达式) 的产生规则

# Primary

```
PrimaryNoNewArray
ArrayCreationExpression
```

# PrimaryNoNewArray

```
Literal
ClassLiteral
this
TypeName . this
( Expression )
ClassInstanceCreationExpression
FieldAccess
ArrayAccess
MethodInvocation
MethodReference
```

# ClassLiteral

```
TypeName { } . class
NumericType { } . class
boolean { } . class
void . class
```

# ClassInstanceCreationExpression

```
UnqualifiedClassInstanceCreationExpression
ExpressionName . UnqualifiedClassInstanceCreationExpression
Primary . UnqualifiedClassInstanceCreationExpression
```

# UnqualifiedClassInstanceCreationExpression

```
new [TypeArguments] ClassOrInterfaceToInstantiate ([ArgumentList] ) [ClassBody]
```

# ClassOrInterfaceToInstantiate

```
[Annotation] Identifier { . [Annotation] Identifier } [TypeArgumentsOrDiamond]
```

# TypeArgumentsOrDiamond

```
TypeArguments
<>
```

## 语法

# FieldAccess

```
Primary . Identifier
super . Identifier
TypeName . super . Identifier
```

# ArrayAccess

```
ExpressionName [ Expression ]
PrimaryNoNewArray { Expression }
```

# MethodInvocation

```
MethodName ( [ArgumentList] )
TypeName . [TypeArguments] Identifier ( [ArgumentList] )
ExpressionName . [TypeArguments] Identifier ( [ArgumentList] )
Primary . [TypeArguments] Identifier ( [ArgumentList] )
super . [TypeArguments] Identifier ( [ArgumentList] )
TypeName . super . [TypeArguments] Identifier ( [ArgumentList] )
```

# ArgumentList

```
Expression { , Expression }
```

# MethodReference

```
ExpressionName :: [TypeArguments] Identifier
Primary :: [TypeArguments] Identifier
ReferenceType :: [TypeArguments] Identifier
super :: [TypeArguments] Identifier
TypeName . super :: [TypeArguments] Identifier
ClassType :: [TypeArguments] new
ArrayType :: new
```

# ArrayCreationExpression

```
new PrimitiveType DimExprs [ Dims ]
new ClassOrInterfaceType DimExprs [ Dims ]
new PrimitiveType Dims ArrayInitializer
new ClassOrInterfaceType Dims ArrayInitializer
```

# DimExprs

```
DimExpr { DimExpr }
```

# DimExpr

```
[Annotation] [ Expression ]
```

## 语法

# Expression

```
LambdaExpression
AssignmentExpression
```

# LambdaExpression

```
LambdaParameters -> LambdaBody
```

# LambdaParameters

```
( [LambdaParameterList] )
Identifier
```

# LambdaParameterList

```
LambdaParameter {, LambdaParameter}
Identifier { , Identifier }
```

# LambdaParameter

```
{VariableModifier} LambdaParameterType VariableDeclaratorId
VariableArityParameter
```

# LambdaParameterType

```
UnannType
var
```

# LambdaBody

```
Expression
Block
```

# AssignmentExpression

```
ConditionalExpression
Assignment
```

# Assignment

```
LeftHandSide AssignmentOperator Expression
```

# LeftHandSide

```
ExpressionName
FieldAccess
ArrayAccess
```

# AssignmentOperator

```
(one of) *= /= %= += -= <<= >>= >>>= &= ^= |=
```

# ConditionalExpression

```
ConditionalOrExpression
ConditionalOrExpression ? Expression : ConditionalExpression
ConditionalOrExpression ? Expression : LambdaExpression
```

# ConditionalOrExpression

```
ConditionalAndExpression
ConditionalOrExpression || ConditionalAndExpression
```

# ConditionalAndExpression

```
InclusiveOrExpression
ConditionalAndExpression && InclusiveOrExpression
```

# InclusiveOrExpression

```
ExclusiveOrExpression
InclusiveOrExpression | ExclusiveOrExpression
```

# ExclusiveOrExpression

```
AndExpression
ExclusiveOrExpression ^ AndExpression
```

# AndExpression

```
EqualityExpression
AndExpression & EqualityExpression
```

# EqualityExpression

```
RelationalExpression
EqualityExpression == RelationalExpression
EqualityExpression != RelationalExpression
```

# RelationalExpression

```
ShiftExpression
RelationalExpression < ShiftExpression
RelationalExpression > ShiftExpression
RelationalExpression <= ShiftExpression
RelationalExpression >= ShiftExpression
RelationalExpression instanceof ReferenceType
```

# ShiftExpression

```
AdditiveExpression
ShiftExpression << AdditiveExpression
ShiftExpression >> AdditiveExpression
ShiftExpression >>> AdditiveExpression
```

# AdditiveExpression

```
MultiplicativeExpression
AdditiveExpression + MultiplicativeExpression
AdditiveExpression - MultiplicativeExpression
```

# MultiplicativeExpression

```
UnaryExpression
MultiplicativeExpression * UnaryExpression
MultiplicativeExpression / UnaryExpression
MultiplicativeExpression % UnaryExpression
```

# UnaryExpression

```
PreIncrementExpression
PreDecrementExpression
+ UnaryExpression
- UnaryExpression
UnaryExpressionNotPlusMinus
```

# PreIncrementExpression

```
++ UnaryExpression
```

# PreDecrementExpression

```
-- UnaryExpression
```

# UnaryExpressionNotPlusMinus

```
PostfixExpression
~ UnaryExpression
! UnaryExpression
CastExpression
```

# PostfixExpression

```
Primary
ExpressionName
PostIncrementExpression
PostDecrementExpression
```

# PostIncrementExpression

```
PostfixExpression ++
```

# PostDecrementExpression

```
PostfixExpression --
```

# CastExpression

```
( PrimitiveType ) UnaryExpression
( ReferenceType [AdditionalBound] ) UnaryExpressionNotPlusMinus
( ReferenceType [AdditionalBound] ) LambdaExpression
```

# ConstantExpression

```
Expression
```



## 附录 A. 有限许可授予

### 1. 评估用途许可

Specification Lead 特此授予你根据其适用的产权的一项全额付费的非排他的、不可转让的、全球性的有限许可（不包含分许可权），允许仅出于内部评估之目的查看、下载、使用和复制规范。这包括：

- (i) 开发旨在在规范上运行的应用程序，前提此类应用程序未实现规范的任何部分；
- (ii) 与任何方讨论规范；
- (iii) 摘录规范的片段，只要这些摘录汇总不构成规范的重要部分。

### 2. 合规实现的发行许可

Specification Lead 还授予你一项永久的、非排他的、不可转让的、全球性的、完全免费的、有限许可（不包含分许可权），用于创建和分发独立实现，该实现：

- (a) 完全实现了规范，包括其要求的接口和功能；
- (b) 未修改、子集化、扩展或其他超出规范要求/授权的任何内容；
- (c) 通过了该规范的技术兼容性套件（包括满足适用 TCK 的要求）。

### 3. 传递条件

在你就授予的关于使用独立实现或其衍生产品的任何许可中，你不需要包含上一段中的 (a)-(c) 限制条件或任何其他“传递”要求。然而，除了满足上段 (a)-(c) 限制限制的独立实现（及其衍生产品）外，你均不能：

- (a) 在规范的知识产权下向你的被许可方授予或其他传递；
- (b) 授权你的被许可方对其实现与相关规范的符合性做出任何声明。

### 4. 专利许可的互惠性

#### a.

对于上述第 2 小节授予许可所涵盖的任何专利权利，如果该权利会在规范的所有技术上可行的产品中被侵犯，则该许可的授予取决于：你以公平、合理且非歧视的条款，向任何向你寻求根据你的专利权利获得永久、非排他的、不可转让的、全球性许可的方提供该许可，以允许该方有权开发、分发和使用合规实现。

#### b.

对于第 2 小节授予许可所涵盖的 Specification Lead 拥有的专利权利，无论在实现规范时是否可以通过技术上可行的方式避免侵权，如果你对 Specification Lead 发起诉讼指控其在履行 Specification Lead 职责过程中诱导任何其他实体侵犯你的专利权，则该许可对此类权利终止。

#### c.

同样，对于规范制定者拥有且根据上述第 2 条授予的许可所涵盖的任何专利权利，如果在实施规范许可时，可以通过技术可行的方法避免对此类权利的侵权，则若您对规范制定者提起索赔，指控其制造、制作、使用、要出售、销售或运行合规实现侵犯了您的专利权，则此类权利应终止。

### 5. 定义

就本协议而言：

- **“独立实现”**（Independent Implementation）是指对规范的某种实现，该实现既不源自任何规范制定者的源代码或二进制代码材料（除非获得规范制定者适当且单独的许可），也不包含任何规范制定者的源代码或二进制代码材料；
- **“许可方名称命名空间”**（Licensor Name Space）是指以“java”、“javax”、“com.oracle”、“com.sun”或其等价术语开头的由 Oracle America, Inc. 通过 Java 社区流程（Java Community Process）采用的后续任何命名规范或其任何认可的继任者或替代者定义的公共类或接口声明；
- **“技术兼容性套件”**（Technology Compatibility Kit）或 **“TCK”** 是指由规范制定者提供的、与规范相对应的测试套件及附带 TCK 用户指南，该套件在以下情况下可用：
  - (i) 在您的独立实现首次用于商业目的 120 天前由规范制定者提供，或
  - (ii) 在此类发布 120 天后，但您选择使用该套件对您的规范实现进行测试。

如果您违反本协议或在上述授予的许可范围之外行动，本协议将立即终止，无需另行通知。

## 免责声明

规范按“现状”提供。规范制定者不提供任何明确或暗示的陈述或保证，包括但不限于对商品性、特定用途的适用性、不侵权（包括由于规范的任何实践或实施而导致）或规范内容适用于任何用途的保证。本文档不代表对任何产品中发布或实施规范任何部分的承诺。此外，规范可能包含技术性错误或排版错误。

## 责任限制

在法律允许的范围内，规范制定者或其许可方在任何情况下不对任何损害负责，包括但不限于收入、利润或数据的损失，或特殊的、间接的、后果性的、偶然或惩罚性的损害，无论原因如何，无论基于何种责任理论，由于您拥有、实施或以其他方式使用规范而产生或与之相关的，即使规范制定者和/或其许可方已被告知可能发生此类损害。

您将确保规范制定者及其许可方因任何索赔而免受损害并对其进行辩护，由于：

- (i) 您对规范的使用；
- (ii) 您的 Java 应用程序、applet 和/或实现的使用或传播；
- (iii) 关于任何提供给您的规范的后续版本或发布与根据本许可为您提供的规范不兼容的索赔。

## 限制权利授予

美国政府：如果本规范由美国政府或代表美国政府获取，或由美国政府主承包商或分包商（任何时候）获取，则政府对软件及相关文档的权利仅限于本许可中的规定；这符合 `48 C.F.R. 227.72701` 至 `227.7202-4`（适用于国防部 (DoD)采购）以及 `48 C.F.R. 2.101` 和 `12.212`（适用于非国防部采购）。

## 报告

如果您向规范制定者提供有关规范的任何意见或建议（“反馈”），您在此同意：

- (i) 同意此类反馈是在非专有且保密的基础上提供的，
- (ii) 授予规范制定者一项永久的、非独的、全球性的、全额付费的不可撤销的许可，有权通过多级转许可人进行分许可，以便为了任何目的无限制地合并、披露和使用反馈。

## 一般条款

与本协议相关的任何行动将受加利福尼亚州法律和美国联邦法的管辖。联合国货物销售公约和任何司法管辖区的法律选择规则不适用。

规范受美国出口控制法的限制，并可能受其他国家进出口规定的限制。被许可人同意遵守所有此类法律法规，并承认在交付给被许可人后有责任获得出口、再出口或进口所需的许可。

本协议是双方就其主题所形成的完整协议。它取代了之前或同时的所有口头或书面通信、提议、条件、陈述和保证，并在本协议期限内，优于双方之间与其主题相关的相关的任何报价、订单、确认或其他通信中的任何冲突或额外条款。除非采取书面形式并由双方授权代表签字，否则对本协议的修改均不具有约束力。
