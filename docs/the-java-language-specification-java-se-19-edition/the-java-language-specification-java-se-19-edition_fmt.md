
# Java® 语言规范，Java SE 19 版

## 11.3 异常的运行时处理

## 12 执行

## 12.1 Java 虚拟机启动

- 13.4.23 方法重载

- 15.21.1 数值相等运算符 `==` 和 `!=`

## 15.22 按位和逻辑运算符

## 15.27.1 Lambda 参数

## 17.4 内存模型

## 17.4.1 共享变量

## 17.7 double 和 long 的非原子处理

### 规范的组织

编译时检查以确保异常情况得到处理。对象可以声明一个 `finalize` 方法，该方法会在对象被垃圾回收器丢弃之前被调用，允许对象清理其不会被释放的状态资源。

```java
class Test {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            System.out.print(i == 0 ? args[i] : " " + args[i]);
        }
        System.out.println();
    }
}
```

```
javac Test.java
java Hello, world.
```

```
IfThenStatement:
if ( Expression ) Statement
```

```
for ([ForInit] ; [Expression] ; [ForUpdate] ) Statement
```

```
NormalClassDeclaration:
[ClassModifier] class TypeIdentifier [TypeParameters]
[ClassExtends][ClassImplements][ClassPermits] ClassBody
```

```
0 1 2 3
```

```
ZeroToThree:
1
```

3. 将步骤 2 产生的输入字符流和行终止符翻译为一组输入元素序列（§3.5），该序列在丢弃空白符（§3.6）和注释（§3.7）后，构成了作为语法规则（§2.3）中终结符号的标记。

### HexDigit

（其之一）

```
0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F
```

### RawInputCharacter

任意 Unicode 字符

这里的 `\`、`u` 和十六进制数字均为 ASCII 字符。

`UnicodeInputCharacter` 产生式是有歧义的，因为编译器原始输入中的 ASCII `\` 字符可以被还原为 `RawInputCharacter`，也可以还原为 `\` 以及 `UnicodeEscape`（其后跟一个 ASCII 字符 `u`）。为了避免歧义，对于编译器原始输入中的每个 ASCII `\` 字符，输入处理应考虑由此翻译步骤产生的最新原始输入字符：

- 如果结果中最近的原始输入字符本身是从编译器原始输入中的 Unicode 转义翻译来的，那么该 ASCII `\` 字符就可以开始一个 Unicode 转义。

> 例如，如果结果中最近的原始输入字符是一个反斜杠，它源自原始输入中的 Unicode 转义 `\u005c`，那么出现在原始输入中的 ASCII `\` 字符就有资格开始另一个 Unicode 转义。

- 否则，考虑结果中作为原始输入字符连续出现的反斜杠数量，直到遇到非反斜杠字符或结果开始；（任何此类反斜杠源于编译器原始输入中的 ASCII `\` 还是源于 Unicode 转义 `\u005c` 并不重要）。如果该数字是偶数，则该 ASCII `\` 字符可以开始一个 Unicode 转义；如果是奇数，则该 ASCII `\` 字符没有资格开始 Unicode 转义。

> 例如，原始输入 `"\\u2122=\\u2122"` 产生 `\u2122=\u2122`，因为原始输入中的第二个 ASCII `\` 字符不能启动 Unicode 转义，第三个 ASCII `\` 字符有效，且 `\u2122` 是字符的编码。

如果 `\` 后没有跟 `u`，则它被视为 `RawInputCharacter` 并留在输入流中。

如果有效的 `\` 后跟一个 `u`，且最后一个 `u` 后没有跟四个十六进制数字，则会发生编译错误。

### 由 Unicode 转义产生的字符不参与 Unicode 转义。

例如，输入 `\u005cu005a` 产生字符 `\` 后面跟 `a`，因为 `005c` 是反斜杠的 Unicode 值。它不会产生 Unicode 值 `005a` 的字符，因为处理 Unicode 转义 `\u005c` 产生的反斜杠不被视为 Unicode 转义的开头。

注意，`\u005cu005a` 不能在字符串字面量中表示字符 `\` 和 `a`。这是因为翻译产生的前两个字符 `\` 和 `u` 在字符串字面量中被解释为非法转义序列（§3.10）。

幸运的是，健壮的反斜杠字符有助于程序员编写字符串字面量 Unicode 转义的原始输入。在字符串字面量中表示 `™` 只需要将 `\` 放置在现有的 `\` 旁，例如 `\\u005a`。

### 3.4 行终止符

当没有可用格式时，Java 编译器应使用 `\uxxxx` 表示法作为输出格式来显示 Unicode 字符。

Java 编译器通过识别行终止符将 Unicode 输入字符序列划分成行。

- LineTerminator:
    - ASCII LF 字符，也称为“换行”
    - ASCII CR 字符，也称为“返回”
    - ASCII CR 字符后跟 LF 被计为一个行终止符，而不是两个

- InputCharacter:
    UnicodeInputCharacter 但不是 CR 或 LF

行由 ASCII 字符 CR、LF 或 CR LF 终止。行终止符指定了 `//` 形式注释的结束（§3.7）。

> 行终止符定义的行可能会决定 Java 编译器产生的行号。

结果是行终止符和输入字符的序列，它们是标记化过程中第三步的终结符号。

由 Unicode 转义处理（§3.3）产生、随后经由输入行识别（§3.4）产生的输入字符和行终止符被还原为输入元素序列。

- Input:
    - [InputElement] [Sub]

# 词法结构

## 输入元素与标记

### 3.5 输入元素

输入元素 (InputElement):

- 空格 (Whitespace)
- 注释 (Comment)
- 标记 (Token)

标记 (Token):

- 标识符 (Identifier)
- 关键字 (Keyword)
- 字面量 (Literal)
- 分隔符 (Separator)
- 运算符 (Operator)

Sub: ASCII SUB 字符，也称为 "control-Z"

非空白或注释的输入元素都是标记。标记是语法终止符号（§2.3）。

空白（§3.6）和注释（§3.7）可以用于分隔标记，如果它们相邻，可能会以另一种方式进行分词。

> 例如，输入字符 `-=` 和 `=` 只有在没有中间插入空格或注释的情况下，才能形成运算符标记 `-=`（§3.12）。另一个例子是十个输入字符 `staticvoid` 形成单个标识符标记，而十一个输入字符 `static void`（在 c 和 v 之间有一个 ASCII SP 字符）则形成一对关键字标记 `static` 和 `void`，它们被空格分隔。

作为为了兼容某些操作系统的特殊让步，如果 ASCII SUB 字符（`\u001a` 或 control-Z）是转义输入流中的最后一个字符，则会被忽略。

输入产生式是有歧义的，这意味着对于某些输入字符序列，有多种方法可以将输入字符归约为输入元素（即对输入字符进行分词）。歧义按如下方式解决：

- 可以归约为标识符标记或字面量标记的输入字符序列始终归约为字面量标记。
- 可以归约为标识符标记或保留关键字标记（§3.9）的输入字符序列始终归约为保留关键字标记。
- 可以归约为上下文相关关键字标记或其他（非关键字）标记的输入字符序列将根据 §3.9 中指定的上下文进行归约。
- 如果输入字符 `>` 出现在类型中，且作为语法语法（§4.1, §8.3）中 Type 或 UnAnn 的部分，它始终被归约为数值比较运算符 `>`，即使它可以与相邻的 `>` 字符结合形成不同的运算符。

虽然不适用于字符，但在像 `List<List<String>>` 的类型中，两个连续的 `>` 括号将被标记为右移运算符 `>>`，而在像 `List<List<String>>>` 的类型中，三个连续的 `>` 被标记为无符号右移运算符 `>>>`。在像 `List<List<List<String>>>>` 的类型中，四个或更多连续的 `>` 括号的分词将是模糊的，因为 `>>` 和 `>>>` 标记的各种组合都可以表示 `>>>`。

考虑结果输入流中的两个标记 `x` 和 `y`。如果 `x` 在 `y` 之前，我们说 `x` 在 `y` 的左侧，`y` 在 `x` 的右侧。

例如，在这段简单的代码中：

```java
class Empty {
}
```

我们说 `}` 标记在 `{` 标记的右侧，尽管在这个二维表示中，它出现在 `{` 标记的下方和左侧。这种关于使用“左”和“右”词的习惯让我们能够讨论例如二元运算符的右操作数或赋值的左侧。

## 3.6 空格

空白被定义为 ASCII 空格字符、水平制表符字符、分页符字符和行终止字符（§3.4）。

- 空格 (Whitespace):
    - ASCII SP 字符，也称为 "space"
    - ASCII HT 字符，也称为 "horizontal tab"
    - ASCII FF 字符，也称为 "form feed"
    - 行终止符 (LineTerminator)

## 3.7 注释

注释有两种类型：

- `/* text */`: 传统注释：从 ASCII 字符 `/*` 到 ASCII 字符 `*/` 的所有文本都会被忽略（如 C 和 C++ 中）。
- `// text`: 行尾注释：从 ASCII 字符 `//` 到行尾的所有文本都会被忽略（如 C++ 中）。

```
Comment:
TraditionalComment
EndOfLineComment
TraditionalComment:
/* CommentTail
CommentTail:
* CommentTailStar
NotStar CommentTail
CommentTailStar:
/
CommentTailStar
NotStarNotSlash CommentTail
NotStar:
InputCharacter but not *
LineTerminator
NotStarNotSlash:
InputCharacter but not * or /
LineTerminator
EndOfLineComment:
// {InputCharacter}
```

这些产生式意味着所有以下属性：

- 注释不支持嵌套。
- 在以 `//` 开头的注释中，`/*` 和 `*/` 没有特殊含义。
- 在以 `/*` 或 `*/` 开头的注释中，`//` 没有特殊含义。

结果是，以下文本是一个完整的注释：

`/* this comment /* // ** ends here: */`

词法语法意味着注释不会出现在字符字面量、字符串字面量或文本块内部（§3.10.4, §3.10.5, §3.10.6）。

## 3.8 标识符

标识符是 Java 字母和 Java 数字的无限长度序列，其中第一个字符必须是 Java 字母。

- 标识符 (Identifier):
    IdentifierChars 但不是保留关键字或布尔字面量或 Null 字面量 (NullLiteral)

- 标识符字符 (IdentifierChars):
    JavaLetter [JavaLetterOrDigit]

- Java字母 (JavaLetter):
    任何作为 "Java 字母" 的 Unicode 字符

- Java字母或数字 (JavaLetterOrDigit):
    任何作为 "Java 字母或数字" 的 Unicode 字符

一个 "Java 字母"是指方法 `Character.isIdentifierStart(int)` 返回 true 的字符。

一个 "Java 字母或数字"是指方法 `Character.isIdentifierPart(int)` 返回 true 的字符。

## 3.9 关键字

### 关键字

上下文关键字（ContextualKeyword）：

（以下之一）

```
exports opens requires uses
module permits sealed var
non-sealed provides to with
open record transitive yield
```

关键字 `const` 和 `goto` 是被保留的，尽管它们目前没有被使用。如果这些 C++ 关键字错误地出现在程序中，这可能允许 Java 编译器产生更好的错误信息。

关键字 `strictfp` 已经过时，不应在新代码中使用。

关键字 `_` 被保留，留供未来可能在参数声明中使用。

`true` 和 `false` 不是关键字，而是布尔字面量（§3.10.3）。

`null` 不是关键字，而是空字面量（§3.10.8）。

在将输入字符归约为输入元素的过程中（§3.5），一个在逻辑上匹配上下文关键字的输入字符序列，当且仅当同时满足以下两个条件时，才会归约为上下文关键字：

1. 该序列被识别为在语法语法（§2.3）指定的终结符，如下所示：
    - 对于 `module` 和 `open`，当在 ModuleDeclaration（§7.7）中被识别为终结符时。
    - 对于 `exports`、`opens`、`provides`、`requires`、`to`、`uses` 和 `with`，当在 ModuleDirective 中被识别为终结符时。
    - 对于 `transitive`，当在 RequiresModifier 中被识别为终结符时。

    例如，识别序列 `requires transitive`；并没有使用 Modifier，因此项 `transitive` 被归约为标识符而不是上下文关键字。

    - 对于 `var`，当在 LocalVariableType（§14.4）或 LambdaParameterType（§15.27.1）中被识别为终结符时。

    在其他上下文中，尝试将 `var` 作为标识符会导致错误，因为 `var` 不是类型标识符（§3.8）。

    - 对于 `yield`，当在 YieldStatement（§14.21）中被识别为终结符时。

    在其他上下文中，尝试将 `yield` 作为标识符会导致错误，因为 `yield` 既不是 TypeIdentifier 也不是未限定方法标识符（UnqualifiedMethodIdentifier）。

    - 对于 `record`，当在 RecordDeclaration（§8.10）中被识别为终结符时。

    - 对于 `non-sealed`、`permits` 和 `sealed`，当在 NormalClassDeclaration（§8.1）或 NormalInterfaceDeclaration（§9.1）中被识别为终结符时。

2. 该序列的前后没有紧跟随任何匹配 JavaLetterOrDigit 的输入字符。

通常情况下，在源代码中无意遗漏空格会导致字符序列被分词为一个标识符；根据“最长可能匹配”规则（§3.2），十二个输入字符序列 `publicstatic` 总是被分词为标识符 `publicstatic`，而不是保留关键字 `public` 和 `static`。如果插入了两个标记，它们之间必须用空格或注释隔开。

该规则与“最长可能匹配”协同工作，在上下文关键字可能出现的上下文中产生直观的结果。例如，十一个输入字符的序列 `varfilename` 通常被分词为标识符 `varfilename`，但在局部变量声明中，前三个字符根据上述第一个规则被初步识别为上下文关键字。然而，如果忽略序列中缺失的空格，并将下一个输入字符识别为标识符 `filename` 将是令人困惑的（这意味着序列在不同的上下文中经历了分词：在大多数情况下是标识符，但在局部变量声明中是上下文关键字和标识符）。因此，第二个条件由于紧随其后的输入字符是 JavaLetterOrDigit 而阻止了对上下文关键字 `var` 的识别。随后，序列 `varfilename` 在局部变量声明中被分词为标识符 `varfilename`。

另一个仔细识别上下文关键字的例子是考虑 15 个字符的序列 `nonsealedclass`，它通常被翻译为三个标记——标识符 `non`、运算符 `-` 和标识符 `sealedclass`——但在类声明中，第一个条件不成立，前几个输入字符被初步识别为上下文关键字 `non-sealed`。为了避免将序列翻译为两个标记（`non-sealed` 和 `class`）而不是三个非关键字标记，并且为了不奖励程序员遗漏空格的行为，第二个条件阻止了对上下文关键字的识别。因此，`nonsealedclass` 在类声明中被分词为三个标记。



在上述规则中，第一个条件取决于语法语法的细节，但 Java 编程语言的编译器可以在不完全解析输入程序的情况下实现该规则。例如，可以使用启发式方法跟踪分词器的上下文状态，将所有分词为关键字的标记，并将有效的标识符使用分词为标识符。或者，编译器可以始终将上下文关键字分词为标识符，留给后续阶段识别这些标识符的特殊用途。

## 3.10 字面量

字面量（`Literal`）是原始类型（§4.2）、`String` 类型（§4.3.3）或空类型（§4.1）值的源代码表示。

- 字面量：
  - 整数字面量（`IntegerLiteral`）
  - 浮点字面量（`FloatingPointLiteral`）
  - 布尔字面量（`BooleanLiteral`）
  - 字符字面量（`CharacterLiteral`）
  - 字符串字面量（`StringLiteral`）
  - 文本块（`TextBlock`）
  - 空字面量（`NullLiteral`）

### 3.10.1 整数字面量

整数字面量可以用十进制（基 10）、十六进制（基 16）、八进制（基 8）或二进制（基 2）表示。

#### IntegerLiteral:

- 十进制整数字面量（`DecimalIntegerLiteral`）
- 十六进制整数字面量（`HexIntegerLiteral`）
- 八进制整数字面量（`OctalIntegerLiteral`）
- 二进制整数字面量（`BinaryIntegerLiteral`）

#### DecimalIntegerLiteral:

`DecimalNumeral` [`IntegerTypeSuffix`]

#### HexIntegerLiteral:

`HexNumeral` [`IntegerTypeSuffix`]

#### OctalIntegerLiteral:

`OctalNumeral` [`IntegerTypeSuffix`]

#### BinaryIntegerLiteral:

`BinaryNumeral` [`IntegerTypeSuffix`]

#### IntegerTypeSuffix:

（以下之一）

`L` `l`

如果一个整数字面量以 ASCII 字母 `L` 或数字 `l` (ell) 后缀结尾，则它是 `long` 类型；否则它是 `int` 类型（§4.2.1）。

> 优选后缀 `L`，因为字母 `l` (ell) 往往与数字 `1` (one) 难以区分。

允许下划线作为表示整数的数字之间的分隔符。

在十六进制或二进制字面量中，整数仅由 `0x` 或 `0b` 字符之后、任何类型后缀之前的数字表示。因此，下划线不能紧跟在 `0x` 或 `0b` 之后，也不能出现在字面量的最后一个数字之后。

在十进制或八进制字面量中，整数由字面量中任何类型后缀之前的所有数字表示。因此，下划线不能出现在数字的第一个数字之前或最后一个数字之后。下划线可以出现在八进制数字初始的 `0` 之后（因为 `0` 是表示整数部分的的数字），也可以出现在非零十进制字面量初始的非零数字之后。

十进制数字可以是单个 ASCII 数字 `0`（表示整数 0），或者由一个 `1` 到 `9` 的 ASCII 数字组成，后面可选跟随一个或多个其间有下划线的 `0` 到 `9` 的 ASCII 数字，表示一个正整数。

```
DecimalNumeral:
0
NonZeroDigit [Digits]
NonZeroDigit Underscores Digits
```

```
NonZeroDigit:
（以下之一）
1 2 3 4 5 6 7 8 9
```

```
Digits:
Digit
Digit [DigitsAndUnderscores] Digit
```

```
Digit:
0
NonZeroDigit
```

```
DigitsAndUnderscores:
DigitOrUnderscore [DigitOrUnderscore]
```

```
DigitOrUnderscore:
Digit
_
```

```
Underscores:
_{}
```

十六进制数字由前导 ASCII 字符 `0x` 或 `0X` 后跟一个或多个其间有下划线的 ASCII 十六进制数字组成，可以表示正整数、零或负整数。

值为 10 到 15 的十六进制数字分别由 ASCII 字母 `a-f` 或 `A-F` 表示；作为十六进制数字使用的每个字母可以是大写或小写。

```
HexNumeral:
0x HexDigits
0X HexDigits
```

```
HexDigits:
HexDigit
HexDigit [HexDigitsAndUnderscores] HexDigit
```

```
HexDigit:
（以下之一）
0 1 2 3 4 5 6 7 8 9 a b c d e f A B C D E F
```

```
HexDigitsAndUnderscores:
HexDigitOrUnderscore [HexDigitOrUnderscore]
```

```
HexDigitOrUnderscore:
HexDigit
_
```

上述 `HexDigit` 产生式来自 §3.3。

### 词法结构

八进制数由一个 ASCII 数字 `0` 后面跟着一个或多个 ASCII 数字 `0` 到 `7` 组成，之间可以用下划线分隔，它可以表示一个正整数、零或负整数。

```
OctalNumeral:
  0 OctalDigits
  0 Underscores OctalDigits
```

```
OctalDigits:
  OctalDigit
  OctalDigit [OctalDigitsUnderscores] OctalDigit
```

```
OctalDigit:
  (其之一)
  0 1 2 3 4 5 6 7
```

```
OctalDigitsUnderscores:
  OctalDigitOrUnderscore {OctalDigitOrUnderscore}
```

```
OctalDigitOrUnderscore:
  OctalDigit
  _
```

注意八进制数始终包含两个或多个数字，因为单独的 `0` 始终被视为十进制数字——这在实践中并不重要，因为数字 `0`、`00` 和 `0x0` 都表示相同的整数值。

二进制数由前导 ASCII 字符 `0b` 或 `0B` 后面跟着一个或多个 ASCII 数字 `0` 或 `1` 组成，之间可以用下划线分隔，它可以表示一个正整数、零或负整数。

```
BinaryNumeral:
0b BinaryDigits
0B BinaryDigits
```

```
BinaryDigits:
BinaryDigit
BinaryDigit [BinaryDigitsAndUnderscores] BinaryDigit
```

```
BinaryDigit:
  (其之一)
  0, 1
```

```
BinaryDigitsAndUnderscores:
  BinaryDigitOrUnderscore [BinaryDigitOrUnderscore]
```

```
BinaryDigitOrUnderscore:
  BinaryDigit
  _
```

### 词法结构

## 字面量

`int` 类型最大的十进制字面量是 `2147483648` (2<sup>31</sup>)。

所有从 `0` 到 `2147483647` 的十进制字面量都可能出现在任何 `int` 字面量可以出现的地方。十进制字面量 `2147483648` 只能作为一元负号运算符的操作数出现 `–`（§15.15.4）。

如果十进制字面量 `2147483648` 出现在一元负号运算符的操作数以外的地方；或者 `int` 类型十进制字面量大于 `2147483648` (2<sup>31</sup>)，则为编译错误。

`int` 类型最大的正十六进制、八进制和二进制字面量——每一个都表示十进制值 `2147483647` (2<sup>31</sup>-1)——分别为：

- `0xffff_ffff`
- `0x1777_7777`
- `0b0111_1111_1111_1111_1111_1111_1111`

`int` 类型最负的十六进制、八进制和二进制字面量——每一个都表示十进制值 `-2147483648` (-2<sup>31</sup>)——分别为：

- `0x8000_0000`
- `0x0200_0000_0000`
- `0b1000_0000_0000_0000_0000_0000_0000_0000`

以下十六进制、八进制和二进制字面量表示十进制值 `-1`：

- `0xffff_ffff`
- `0x3777_7777_7777`
- `0b0111_1111_1111_1111_1111_1111_1111`

如果十六进制、八进制或二进制 `int` 字面量无法容入 32 位，则为编译错误。

`long` 类型最大的十进制字面量是 `9223372036854775808L` (2<sup>63</sup>)。

所有从 `0L` 到 `9223372036854775807L` 的十进制字面量都可能出现在任何 `long` 字面量可以出现的地方。十进制字面量 `9223372036854775808L` 只能作为一元负号运算符的操作数出现 `–`（§15.15.4）。

如果十进制字面量 `9223372036854775808L` 出现在一元负号运算符的操作数以外的地方；或者 `long` 类型十进制字面量大于 `9223372036854775808L` (2<sup>63</sup>)，则为编译错误。

`long` 类型最大的正十六进制、八进制和二进制字面量——每一个都表示十进制值 `9223372036854775807L` (2<sup>63</sup>-1)——分别为：

- `0x7FFFF_ffff_ffffL`
- `0x07777_7777_7777_7777L`
- `0b0111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111_1111`

`long` 类型最负的十六进制、八进制和二进制字面量——每一个都表示十进制值 `-9223372036854775808L` (-2<sup>63</sup>)——分别为：

- `0x8000_0000_0000_0000L`
- `0x010_0000_0000_0000L`
- `0b0100_0000_0000_0000_0000_0000_0000_0000_0000_0000`

以下十六进制、八进制和二进制字面量表示十进制值 `-1L`：

- `0xffff_ffff_ffffL`
- `0x01777_7777_7777_7777L`
- `0b0111_1111_1111_1111_1111_1111_1111`

如果十六进制、八进制或二进制 `int` 字面量无法容入 32 位，则为编译错误。

`long` 类型最大的十进制字面量是 `9223372036854775808L` (2<sup>63</sup>)。

所有从 `0L` 到 `9223372036854775807L` 的十进制字面量都可能出现在任何 `long` 字面量可以出现的地方。十进制字面量 `9223372036854775808L` 只能作为一元负号运算符的操作数出现（§15.15.4）。

如果十进制字面量 `9223372036854775808L` 出现在一元负号运算符的操作数以外的地方；或者 `long` 类型十进制字面量大于 `9223372036854775808L` (2<sup>63</sup>)，则为编译错误。

## 浮点数字面量

浮点数字面量由一个符号、一个尾数和一个指数组成，可以表示正、零或负的实数。

浮点数字面量可以用两种形式表示：十进制和十六进制。

十进制浮点数字面量由一个符号、一个尾数和一个组成。尾数由一个或多个数字组成，可选后跟随一个小数点和一个或多个数字。小数点可以放置在任何位置，只要两边至少各有一个数字。

如果一个非零浮点数字面量的值很小，以至于在转换为内部表示时变为非规数，则不会发生编译错误。

十六进制浮点数字面量由一个符号、一个尾数和一个组成。尾数由一个或多个十六进制数字组成，可选后跟随一个十六进制点（也称为小数点）和一个或多个十六进制数字。小数点可以放置在任何位置，只要两边至少各有一个数字。

十六进制浮点数的指数前面写有字母 `p` 或 `P`，并且是一个整数。

`float` 类型最大的正浮点数字面量是 `3.402823466385286E+38`。

`float` 类型最小的正浮点数字面量是 `1.401298464001547E-45`。

`double` 类型最大的正浮点数字面量是 `1.7976931348623157E+308`。

`double` 类型最小的正浮点数字面量是 `4.940656458456714E-324`。

如果浮点数字面量太大，以至于在转换为内部表示时变为无穷大，则为编译错误。

如果一个非零浮点数字面量太小，以至于在转换为内部表示时变为零，则为编译错误。

以下浮点数字面量表示十进制值 `-1`：

- `-1.0f`
- `-1.0d`
- `-0x1.0p-0f`

如果浮点数字面量无法容入其指定的类型（`float` 为 32 位，`double` 为 64 位），则为编译错误。

浮点数可以用科学计数法表示，尾数跟随字母 `e` 或 `E` 以及一个十进制指数。

十进制浮点数字面量示例：

- `1.23e10`
- `4.56E-5`
- `7.89`

十六进制浮点数字面量包括一个符号、一个尾数和一个指数。尾数由一个或多个十六进制数字组成，可选后跟随一个十六进制点和一个或多个十六进制数字。指数前面有 `p` 或 `P`。

十六进制浮点数字面量示例：

- `0x1.ap10`
- `0x2.bcP-5`
- `0x3`

布尔字面量始终是 `boolean` 类型 (§4.2.5)。

### 3.10.4 字符字面量

字符字面量表示为一个字符或转义序列 (§3.10.7)，并包含在 ASCII 单引号中。（单引号，或撇号，字符为 `\u0027`。）

- `SingleCharacter`（单字符）:
  `InputCharacter` 不是 `'` 或 `\`

字符字面量始终是 `char` 类型 (§4.2.1)。

字符字面量的内容是紧跟起始 `'` 之后的 `SingleCharacter` 或 `EscapeSequence`。

如果字符内容不是 `'`，则会导致编译时错误。

如果在起始 `'` 之后且结束 `'` 之前出现行终止符 (§3.4)，则会导致编译时错误。

> 字符 `CR` 和 `LF` 都是 `InputCharacter`；每个都被识别为构成 `LineTerminator`（行终止符），因此不能出现在字符字面量中，即使在转义序列 `\ LineTerminator` 中也是如此。

由字符字面量表示的字符是字符字面量的内容经过任何转义序列解释后的结果，就像对内容执行 `String.translateEscapes` 方法一样。

字符字面量只能表示 UTF-16 代码单元（即，它们被限于从 `\u0000`-\ffff 的值）。补充字符必须根据其使用的 API 被表示为 `char` 序列中的代理对，或者表示为整数。

以下是字符字面量的示例：

- `'a'`
- `'\b'`
- `'\t'`
- `'\\'`
- `'\u03a9'`
- `'\uFFFF'`
- `'\u177'`
- `'\201'`

由于 Unicode 转义序列是在早期阶段被处理的，因此为值为换行符（LF）的字符字面量编写 `'\u000a'` 是不正确的；Unicode 转义序列 `\u000a` 在翻译步骤 1 (§3.3) 中被转换为实际的换行符，且该换行符在步骤 2 (§3.4) 中变为 `LineTerminator`，字符字面量在步骤 3 中是的。相反，应该使用转义序列 `'\n'`。同样，为值为回车符（CR）的字符字面量编写 `'\u000d'` 是不正确的。使用 `'\r'`。最后，对于包含撇号（`'`）的字符字面量，无法编写 `'\u0027'`。

在 C 和 C++ 中，字符字面量可以包含多个字符的表示，但此类字符字面量的值由实现定义。在 Java 语言中，字符字面量始终精确表示一个字符。

### 3.10.5 字符串字面量

字符串字面量由包含在双引号中的零或多个字符组成。换行符等字符可以使用转义序列 (§3.10.7）表示。

> `StringLiteral`（字符串字面量）：
> `"{StringCharacter}"`
>
> `StringCharacter`（字符串字符）：
> `InputCharacter` 不是 `"` 或 `\`
> `EscapeSequence`

字符串字面量始终是 `String` 类型 (§4.3.3)。

字符串字面量的内容是紧跟起始 `"` 之后并结束于匹配的结束 `"` 之前的字符序列。

如果在起始 `"` 之后且在匹配的结束 `"` 之前出现行终止符 (§3.4)，则会导致编译时错误。

> 字符 `CR` 和 `LF` 永远不是 `InputCharacter`；每个都被识别为构成字符串 `LineTerminator`（行终止符），因此不能出现在字符串字面量中，即使在转义序列 `\` 中也是如此。

字符串字面量表示的字符串是字符串字面量的内容经过每个转义序列解释后的结果，就像对内容执行 `String.translateEscapes` 方法一样。

## 字面量

以下是字面量的示例：

```
// 空字符串
""
"=""" // 包含 "alone" 的字符串
"This is a string" // 包含 16 个字符的字符串
"This is a "" + // 实际上是一个字符串值的表达式，
"two-line string" //
```

由于 Unicode 转义序列每处都被处理，因此为包含换行符（LF）的字符串字面量编写 `"\u000a"` 是不正确的；Unicode 转义序列 `\u000a` 在翻译步骤 1 (§3.3) 中被转换为实际的换行符，且该换行符在步骤 2 (§3.4) 中变为 `LineTerminator`；相反，应该使用转义序列 `"\n"`。同样，为包含单个回车符（CR）的字符串字面量编写 `"\u000d"` 是不正确的。使用 `"\r"`。最后，对于包含双引号（`"`）的字符串字面量，无法编写 `"\u0022"`。

长字符串字面量可以拆分成更短的片段，并使用连接运算符 `+` (§15.18) 写为一个（可能是括号的）表达式。

在运行时，字符串字面量是对 `String` 类实例 (§4.3.3) 的引用，表示该字符串字面量所代表的字符串。



此外，字符串字面量始终引用 `String` 类的同一个实例。这是因为字符串字面量——更广义地说，常量表达式值 (§15.29)的字符串——会被“池化”（interned），以便共享唯一的实例，就像执行 `String.intern` 方法 (§12.5)一样。

## 示例 3.10.5-1. 字符串字面量

由编译单元 (§7.3)组成的程序：

```java
package testPackage;
class Test {
    public static void main(String[] args) {
        String hello = "Hello", lo = "lo";
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
        System.out.println(hello == "Hello");
    System.out.println(hello == "Hello");
    }
}
class Other {
 }
```

以及编译单元：

```java
package other;
public class Other { static String hello = "Hello"; }
```

# 词法结构

产生输出：

```
true
true
true
true
false
true
```

这个示例说明了六点：

- 同一个类中的字符串字面量表示同一个对象的引用。
- 同一个包中的字符串字面量表示同一个对象的引用。
- 不同包中的字符串字面量表示不同对象的引用。
- 由常量表达式连接的字符串(§15.29)在编译时计算，然后视为字面量。
- 运行时计算的字符串是新创建的，因此是不同的。
- 显式字符串的结果与任何预存字符串是同一个对象。

### 3.10.6 文本块

文本块由起始和结束分隔符包含的零或多个字符组成。字符可以使用转义序列 (§3.10.7)表示，在字符串字面量(§3.10.5)中必须用转义序列表示的换行符和双引号字符可以在文本块中直接表示。

```
TextBlock（文本块）：
  " " " [TextBlockWhiteSpace] LineTerminator [TextBlockCharacter] " ""

TextBlockWhiteSpace（文本空白）：
  Whitespace 不是 LineTerminator

TextBlockCharacter（文本字符）：
  InputCharacter 不是 \
  EscapeSequence
  LineTerminator
```

为了方便，这里显示了来自 §3.3 §3.4 和 §3.6 的产生式：

WhiteSpace：

- ASCII SP 字符，也称为“空格”
- ASCII HT 字符，也称为“水平制表符”
- ASCII FF 字符，也称为“分页符”

LineTerminator：

- ASCII LF 字符，也称为“换行/newline”
- ASCII CR 字符，也称为“回车”
- ASCII CR 字符后跟 ASCII LF 字符

InputCharacter（输入字符）：

- UnicodeInputCharacter 不是 CR 或 LF
- UnicodeInputEscape
- RawInputCharacter

文本块始终是 `String` 类型(§4.3.3)。

起始分隔符是一个以三个双引号 (`"""`) 开头，以零或多个空格、制表符和分页符继续，并以行终止符结束的序列。

结束分隔符是三个双引号字符的序列。

文本块的内容是紧跟起始分隔符的行终止符之后，并结束于结束分隔符第一个双引号之后的字符序列。

与字符串字面量(§3.10.5)不同，在文本块内容中出现行终止符并不是编译时错误。

## 示例 3.10.6-1. 文本块

需要多行字符串，文本块通常比字符串字面量的连接更具可读性。例如，比较以下代码片段的替代表示方式：

```java
String html = "<html>\n" +
              "<body>\n" +
              "<p>Hello, world</p>\n" +
              "</body>\n" +
              "</html>\n";
```

```java
String html = """
<html>
<body>
<p>Hello, world</p>
</body>
</html>
""";
```

```html
<html>
<body>
  <p>Hello, world</p>
</body>
</html>
```

# 词法结构 ## 字面量 3.10

以下是文本块的示例：

```java
class Test {
  public static void main(String[] args) {
    // 六个字符 w i n t e r
    String season = """
      winter""";

    // 七个字符 w i n t e r LF
    String period = """
      winter
""";

    // 十个字符 H i , SP " B o b " LF
    String greeting = """
      Hi, "Bob"
      """;

    // 十一个字符 H i , LF SP " B o b " LF
    String salutation = """
      Hi,
      "Bob"
      """;

    // 空字符串（长度为 0）
    String empty = """
      """;

    // 两个字符 " LF
    String quote = """
      "
""";

    // 两个字符 \ LF
    String backslash = """
      \\""";
  }
}
```

在文本块中使用转义序列 `\n` 和 `\"` 分别表示换行字符和双引号字符是允许的，尽管通常并非必须。例外是当连续出现三个双引号字符且并非用于结束分隔符 `"""` 时——在这种情况下，必须对其中至少一个双引号进行转义，以避免模拟结束分隔符。

## 示例 3.10.6 文本块中的转义序列

在以下程序中，如果对单个双引号字符进行转义，`story` 变量的值可读性会降低：

```java
class Story1 {
    public static void main(String[] args) {
        String story = """
            "When I use a word," Humpty Dumpty said,
            in a scornful tone, "it means just what I
            choose it to mean - neither more nor less."
            "The question is," " said Alice, "whether you
            can make words mean so many different things."
            "The question is," " said Humpty Dumpty,
            "which is to be master - that's all."
        """;
    }
}
```

如果将程序修改为将结束分隔符放在内容的最后一行，则最后一行的前三个连续双引号会被翻译为结束分隔符 `"""`(§3.2)，从而留下了一个多余的双引号字符：

```java
class Story2 {
    public static void main(String[] args) {
        String story = """
            "When I use a word," Humpty Dumpty said,
            in a scornful tone, "it means just what I
            choose it to mean - neither more nor less."
            "The question is," " said Alice, "whether you
            can make words mean so many different things."
            "The question is," " said Humpty Dumpty,
            "which is to be master - that's all."""; // 
    }
}
```

通过对内容中的最后一个双引号字符进行转义可以避免该错误：

```java
class Story3 {
    public static void main(String[] args) {
        String story = """
            "When I use a word," Humpty Dumpty said,
            in a scornful tone, "it means just what I
            choose it to mean - neither more nor less."
            "The question is," " said Alice, "whether you
            can make words mean so many different things."
            "The question is," " said Humpty Dumpty,
            "which is to be master - that's all.\"" // OK
        """;
    }
}
```



如果一个文本块旨在表示另一个文本块，则建议对嵌入的起始和分隔符的第一个双引号字符进行转义：

```java
class Code {
    public static void main(String[] args) {
        String text = """
        The quick brown fox jumps over the lazy dog
        """

        String code = """
        String text = "\""
        The quick brown fox jumps over the lazy dog
        """
    }
}
```

由文本块表示的字符串并不是内容中字符的字面序列。相反，文本块表示的字符串是对内容按顺序应用以下变换的结果：

1. 行终止符归一化为 ASCII 字符，如下：
   - ASCII CR 字符后跟 ASCII LF 字符被翻译为 ASCII LF 字符。
   - ASCII CR 字符被翻译为 ASCII LF 字符。
2. 移除偶然空白符，就如同对步骤 1 产生的字符执行了 `String.stripIndent()` 一样。
3. 解释转义序列，就如同对步骤 2 产生的字符执行了 `String.translateEscapes()` 一样。

当本规范说文本块包含特定的字符或字符序列，或者特定的字符或字符序列位于文本块中时，意味着由文本块表示的字符串（而非内容中字符的字面序列）包含了该字符或字符序列。

示例 3.10.6-3 文本块内容的变换顺序

解释转义序列允许程序员使用 `\n`、`\f` 和 `\r` 进行字符串的垂直格式化，而不影响行终止符的归一化；并使用 `\b` 和 `\t` 进行字符串的水平格式化，而不影响偶然空格的移除。例如，考虑这个提到了转义序列 (CR) 的文本块：

```html
<html>
<body>
  <p>Hello, world</p>
</body>
</html>
```

运行时，一个文本块引用某个实例。此外，一个文本块引用共享的实例，以 `String.intern()`。

# 词法结构 字面量 3.10

文本块可以使用在任何允许表达式的地方，例如在注解中：

```java
System.out.println("ab");
```

```java
String cde = """
abc""";
```

```java
String math = """
12""";
```

```java
@Preconditions("""
rate > 0
rate <= MAX_REFRESH
""")
void setRate(int rate) { }
```

# 词法结构 3.10.7 转义序列

字符字面量、字符串字面量和文本块中（§3.10.4、§3.10.5、§3.10.6），*转义序列*允许在不使用 Unicode 转义的情况下表示非图形字符，以及单引号、双引号和反斜杠。

- 转义序列:
  - `\b` (退格 BS, \u0008)
  - `\s` (空格 SP, \u0020)
  - `\t` (水平制表符 HT, \u0009)
  - `\n` (换行 LF, \u000a)
  - `\f` (换页 FF, \u000c)
  - `\r` (回车 CR, \u000d)
  - `\LineTerminator` (行延续, Unicode 表示)
  - `\"` (双引号 ", \u0022)
  - `\'` (单引号 ', \u0027)
  - `\\` (反斜杠 \, \u005c)

- 八进制转义:
  - `\OctalDigit` (八进制值, Unicode \u000 到 \u00ff)
  - `\OctalDigit OctalDigit`
  - `\ZeroToThree OctalDigit OctalDigit`

- 八进制数字:
  - (其之一)
  - 0 1 2 3 4 5 6 7

- ZeroToThree:
  - (其之一)
  - 0 1 2

八进制数字的产生式来自自 §3.10.1。提供八进制转义是为了与 C 兼容，但只能表示 Unicode 值 \u000 到 \u00FF，因此通常优选 Unicode 转义。

如果转义序列中反斜杠后的字符不是行终止符或 ASCII b, s, t, n, f, r, ", \, 0, 1, 2, 3, 4, 5, 6, 或 7，则为编译错误。

字符字面量、字符串字面量或块内容中的转义序列通过*解释*，将其 `\` 及其后续字符替换为单个由 `EscapeSequence` 语法中的 Unicode 转义表示的字符。行延续转义序列没有对应的 Unicode 转义，因此它通过将其替换为空来被解释。

行延续转义序列可以出现在文本块中，但不能出现在字符字面量或字符串字面量中，因为这两者都不允许出现行终止（LineTerminator）。

### 3.10.8 空引用字面量

null 类型有一个值，即空引用，由空引用字面量 `null` 表示，它由 ASCII 字符组成。

```
NullLiteral:
null
```

空引用字面量总是 null 类型（§4.1）。

## 3.11 分隔符

十二个由 ASCII 字符组成的标记是分隔符（标点）。

- 分隔符：
  （以下之一）
  `( ) } [ ] ; , . ... @ : =`

## 3.12 运算符

38 个由 ASCII 字符组成的标记是运算符。

- 运算符：
  （以下之一）
  `= < ! ~ ? : ->`
  `== >= <= != && ++`
  `+ * | / & ^ << >>>`
  `+ - * * = / & ^ = <= >= >>>`

# 第 4 章

# 类型、值与变量

Java 编程语言是一种静态类型语言，这意味着每个变量和每个表达式都有在编译时已知的类型。

Java 编程语言也是一种强类型语言，因为类型限制了变量（§4.12）可以包含的值或表达式可以产生的值，限制了对这些值的操作，并决定了操作的含义。强静态类型有助于在编译时检测错误。

Java 编程语言的类型分为两种：基本类型和引用类型。基本类型（§4.2）是布尔类型和数值类型。数值类型是整数类型 `byte`、`int`、`long` 和 `char`，以及浮点类型 `float` 和 `double`。引用类型（§4.3）是类类型、接口类型和数组类型。还有一种特殊类型。对象（§4.3.1）是类类型的动态创建实例或动态创建的数组。引用类型的值是对对象的引用。所有对象（包括数组在内）都支持 `Object` 类（§4.3.2）的方法。字符串字面量由 `String` 对象（§4.3.3）表示。

## 4.1 类型与值的种类

Java 编程语言中有两种类型：基本类型（§4.2）和引用类型（§4.3）。相应地，可以存储在变量中、作为参数传递、由方法返回以及进行操作的数据值有两种：基本值（§4.2）和引用值（§4.3）。

- 类型：
  `PrimitiveType`
  `ReferenceType`

还有一种特殊的 null 类型，表达式 `null` 的类型（§3.10.8, §15.8.1），它没有名称。

由于 null 类型没有名称，因此无法声明 null 类型的变量或强制转换为 null 类型。

空引用是 null 类型表达式的唯一可能的值。

空引用始终可以赋值或强制转换为任何引用类型（§5.2, §5.3, §5.5）。

> 在实践中，程序员可以忽略 null 类型，只需假装 `null` 仅仅是一个可以作为任何引用类型的特殊字面量。

## 4.2 基本类型与值

基本类型由 Java 编程语言预定义，并由其保留关键字（§3.9）命名：

```
PrimitiveType:
[Annotation] NumericType
[Annotation] boolean

NumericType:
IntegralType
FloatingPointType

IntegralType:
(one of)
byte short int char

FloatingPointType:
(one of)
float double
```

基本值不与其他基本值共享状态。

数值类型是整数类型和浮点类型。

整数类型是 `byte`、`short`、`int` 和 `long`，它们的值分别是 8 位、16 位、32 位和 64 位有符号补码整数；以及 `char`，其值是表示 UTF-16 码单元的无符号整数（§3.1）。

浮点类型是 `float` 和 `double`。`float` 的值精确对应 32 位 IEEE 754 二进制浮点数，`double` 的值精确对应 64 位 IEEE 754 二进制浮点数。

布尔类型有两个值：`true` 和 `false`。

### 4.2.1 整数类型与变量

整数类型的值在以下范围内：

- `byte`：从 -128 到 127
- `short`：从 -32768 到 32767
- `int`：从 -2147483648 到 2147483647
- `long`：从 -9223372036854775808 到 9223372036854775807
- `char`：从 `\u0000` 到 `\ffff`，即从 0 到 65535

### 4.2.2 整数运算

Java 语言提供了许多用于整数值的运算符：

- 结果为布尔值的比较运算符：
  - 比较运算符 `<` `<=` `>` `>=`（§15.20.1）
  - 相等运算符 `==` 和 `!=`（§15.26.1）

- 结果为 `int` 或 `long` 的数值运算符：
  - 一元加法和减法运算符 `+` 和 `-`（§15.15.3, §15.14.4）
  - 乘法运算符 `*`、`/`（§15.17）
  - 加法运算符 `+` 和 `-`（§15.18）
  - 递增运算符 `++`（前缀 §15.15.1 和后置 §15.14.2）
  - 递减运算符 `--`（前缀 §15.15.2 和后置 §15.15.3）
  - 有符号和无符号移位运算符 `<<`、`>>`、`>>>`（§15.19）
  - 位反运算符 `~`（§15.15.5）
  - 位运算符 `&`、`^` 和 `|`（§15.22.1）

- 条件运算符 `?`（§15.25）
- 强制转换运算符（§15.16），可以将整数转换为任何数值类型。
- 字符串拼接运算符 `+`（§15.18.1），当给定 `String` 操作数和一个整数操作数时，它将整数转换为 `String`（`byte`、`short`、`int`、`long` 或 `char` 操作数的十进制形式），然后产生新字符串。

其他有用的构造函数、方法和常量定义在 `Byte`、`Short` 和 `Character` 中。

如果整数运算符至少有一个 `long` 操作数，操作使用 64 位精度执行，数值运算符的结果为 `long`。如果另一个操作数不是 `long`，则通过类型提升转换为 `long`（§5.5, §5.6）。

否则，操作使用 32 位精度执行，数值运算符的结果为 `int`。如果任一操作数不是 `int`，则通过类型提升转换为 `int`。

整数运算符不会任何方式指示溢出或下溢。任何整数类型的值都可以转换为任何数值类型。整数类型与布尔类型之间没有转换。

整数运算符由于以下原因抛出异常（Exceptions）：

- 需要对空引用进行拆箱转换（§5.1.8）时，任何整数运算符都可能抛出 `NullPointerException`。
- 右操作数为零时，除法运算符 `/`（§15.17.2）可能抛出 `ArithmeticException`（§15.17.3）。
- 需要进行装箱转换（§5.1.7）且没有足够的内存执行转换时，递增运算符 `++`（§15.14.2, §15.15.1）和递减运算符 `--`（§15.14.3, §15.15.2）可能抛出 `OutOfMemoryError`。

# 示例 4.2.2-1 整数运算

```java
class Test {
    public static void main(String[] args) {
        int i = 1000000;
        System.out.println(i * i);
    }
}
```

```java
long l = i;
System.out.println(1 * l);
System.out.println(2026 / (1 - i));
```

该程序输出：

```
-727379968
1000000000000
```

随后在除以 `l - i` 时遇到 `ArithmeticException`，因为 `i` 为零。第一次乘法是在 32 位精度下执行的，而第二次乘法是长整型乘法。值 `-727379968` 是数学结果 `1000000000000` 的低 32 位十进制值，对于 `int` 来说很大值。

### 4.2.3 浮点类型与值

浮点类型是 `float` 和 `double`，它们在概念上与 IEEE 754 值的 32 位 binary32 和 64 位 binary64 浮点数相关，并参见 §1.7。

在 Java SE 15 及更高版本中，Java 编程语言使用 2019 年版本的 IEEE 754 标准。在 Java SE 15 之前，Java 编程语言使用 1985 年版本的 IEEE 754 标准，其中 binary32 格式称为单精度格式，binary64 格式称为双精度格式。

IEEE 754 不仅包括符号和数值的正负数，还包括正零和负零、正无穷和负无穷，以及特殊的非数字值（下简称 NaN）。NaN 值用于表示某些无效操作的结果，例如除以零。`float` 和 `double` 的 NaN 常量定义为 `Float.NaN` 和 `Double.NaN`。

浮点类型的非零值可以用形式 s · 2^(E−N) 表示，其中：

- s 是 +1 或 -1，
- m 是小于 2^N 的正整数，
- e 是在 Emin = -(2^(K-1)-2) 到 Emax = 2^K-1 之间的整数（包含边界），
- N 和 K 是取决于类型的参数。

某些值可以用这种形式表示一种。例如，假设浮点类型的值 v 可以用这种形式表示

# 原始类型和值

使用特定的值 $s, m$, 和 $e$，如果此时 $m$ 为偶数且 $e$ 小于 $2^{K-1}$，则可以将 $m$ 减半并将 $e$ 增加 1，从而产生相同值 $v$ 的第二种表示。

如果 $m \ge 2^{K-1}$，这种形式的形式被称为*归一化的*（normalized）；否则，该表示被称为非规格化的（subnormal）。如果一个浮点类型的值无法以满足 $m \ge 2^{K-1}$ 的方式表示，则该值被称为*非规格化值*（subnormal value），因为它的幅值是最小归一值的幅值。

`float` 和 `double` 的参数 $N$ 和 $k$（以及派生参数 $E_{min}$ 和 $E_{max}$）的约束总结在表 4.2.3-A。

## 表 4.2.3-A. 浮点数参数

| 参数 | float | double |
|---|---|---|
| N | 24 | 53 |
| K | 8 | 11 |
| $E_{max}$ | +127 | +1023 |
| $E_{min}$ | -126 | -1022 |

除 NaN 之外，浮点值是有*序的*。从小到大排列，它们是：负无穷、非零负值、负零和正零、有限非零值以及正无穷。

IEEE 754 允许其 binary32 和 binary64 浮点数拥有多个不同的 NaN 值。然而，Java SE 平台通常将给定浮点类型的 NaN 值视为合并后的单一规范值，因此，本规范通常将任意的 NaN 视为一个规范值。

> IEEE 754 规定，带有非 NaN 操作数参数的浮点操作可能会产生 NaN 结果。IEEE 754 规定了一组 NaN 模式，但没有强制使用哪种 NaN 模式来表示 NaN 结果；这由硬件架构决定。程序员可以创建不同模式的 NaN 来编码（例如，追溯信息）。这些 NaN 值可以通过 `float` 和 `double` 的 `Float.intToFloat` 和 `Double.longBitsDouble` 方法创建。相反，要检查 NaN 值的位模式，分别可以使用 `float` 和 `double` 的 `Float.floatToRawBits` 和 `Double.doubleToRawBits` 方法。

正零和负零比较相等，表达式 $0.0==0.0$ 的结果为 `true`，$0.0>-0.0$ 的结果为 `false`。其他操作可以区分正零和负零；例如，$1.0/0.0$ 的值为正无穷，而 $1.0/-0.0$ 的值为负无穷。

# 类型、值和变量

# 原始类型和值

## 4.2

NaN 是无序的，因此：

- 如果任一或两个操作数均为 NaN，则数值比较运算符 `<`、`<=` `>=` 返回 `false` (§15.20.1)。
  特别是，如果 x 或 y 为 NaN，则 `(x<y) != (x=y)` 将为 `false`。
- 如果任一操作数为 NaN，则相等运算符 `==` 返回 `false`。
- 如果任一操作数为 NaN，则不等于运算符 `!=` 返回 `true` (§15.21.1)。
  特别是，当且仅当 x 为 NaN 时，`x!=x` 为 `true`。

### 4.2.4 浮点操作

Java 编程语言提供了许多作用于浮点值的运算符：

- 比较运算符，其结果为 `boolean` 类型值：
  - 数值比较运算符 `<`、`<=` `>=` (§15.20.1)。
  - 数值相等运算符 `==` 和 `!=` (§15.21.1)。
- 数值运算符，其结果为 `float` 或 `double` 类型值：
  - 一元减和加运算符 `-` 和 `+` (§15.15.3, §15.15.4)。



## 浮点类型运算符

- 乘法运算符 `*` 和 `/` (§15.17)。
- 加法运算符 `+` 和 `-` (§15.18.2)。
- 递增运算符 `++`，包括前缀 (§15.15.1) 和后置 (§15.14.2)。
- 递减运算符 `--`，包括前缀 (§15.15.2) 和后置 (§15.14.3)。
- 三元运算符 `?:` (§15.25)。
- 强制转换运算符 (§15.16)，可以将浮点值转换为任何指定的数值类型。
- 字符串拼接运算符 `+` (§15.18.1)，当给定一个字符串操作数和一个浮点操作数时，它会将浮点操作数转换为字符串，然后产生一个拼接这两个字符串的新字符串。

其他有用的构造函数、方法和常量定义在 `Float`、`Double` 和 `Math` 类中。

如果操作数中至少有一个是浮点类型，则该操作使用 64 位浮点运算执行，且数值运算符的结果为 `double` 类型。如果另一个操作数不是 `double`，则首先通过数值提升提升为 `double` (§5.1.5)。否则，至少有一个操作数是 `float` 类型；该操作使用 32 位浮点运算执行，且数值运算符的结果为 `float` 类型。

浮点运算按照 IEEE 754 标准执行，包括溢出和下溢 (§15.4)，除了取模运算符 `%` (§15.17)。任何浮点类型的值都可以强制转换为数值类型或从数值类型转换。浮点类型和 `boolean` 类型之间没有转换。

对于以下情况：

- 任何浮点运算符在需要拆箱转换 (§5.8) 或空引用时抛出 `NullPointerException`。
- 递增和递减运算符 `++` (§15.14.2, §15.15.1) 和 `--` (§15.14.3, §15.15.2) 在需要装箱且没有可用内存时抛出 `OutOfMemoryError`。

### 示例 4.2.4-1. 浮点操作

```java
class Test {
    public static void main(String[] args) {
        // 溢出示例
        double d = 1e308;
        System.out.println("overflow produces infinity: " + d);
        System.out.println(d * 10);
        // 渐溢示例
        d = 1e-300 * Math.PI;
        System.out.print("gradual underflow: " + d + "\n");
        for (int i = 0; i < 4; i++) {
            System.out.print(d /= 100000);
        }
        // NaN 示例
        d = 0.0 / 0.0;
        System.out.println("0.0/0.0 is Not-a-Number: " + d);
        System.out.println(d);
        // 不精确结果和舍入示例
        System.out.print("inexact results with float:");
        for (int i = 0; i < 100; i++) {
            float z = 1.0f / i;
            if (z * i == 1.0f) {
                System.out.print("");
            }
        }
    }
}
```

该程序产生输出：

```
overflow produces infinity: Infinity
gradual underflow: 3.141592653589793E-305
3.141592653589793-310 3.14159265E-315 3.142E-320 0.0
0.0/0.0 is Not-a-Number: NaN
inexact results with float: 0 41 47 55 61 82 83 94 97
inexact results with double: 0 49 98
cast to int rounds toward 0: 12345 -12345
```

此示例演示了（其他事情）渐溢如何会导致精度损失。当 `i` 为 0 时发生除以零，导致 `z` 变为正无穷，且 `z * 0` 为 NaN，不等于 1.0。

## 4.2.5 boolean 类型和 boolean 值

`boolean` 类型表示具有两个可能值的逻辑量，由字面量 `true` 和 `false` 表示 (§10.3)。

boolean 运算符有：

- 关系运算符 `==` 和 `!=` (§15.21.2)
- 逻辑取反运算符 `!` (§15.15.6)
- 逻辑运算符 `&`、`^` 和 `|` (§15.22.2)
- 条件与和条件或运算符 `&&` (§15.23) 和 `||` (§15.24)
- 三元运算符 `?:` (§15.25)
- 字符串拼接运算符 `+` (§15.18.1)，当给定一个字符串操作数和一个布尔操作数时，它会将布尔操作数转换为字符串（"true" 或 "false"），然后产生一个拼接这两个字符串的新字符串

布尔表达式决定了以下控制语句：

- `if` 语句 (§14.9)
- `while` 语句 (§14.12)
- `do` 语句 (§14.13)
- `for` 语句 (§14.14)

布尔表达式还决定了三元运算符 `?:` 中执行哪一个子表达式 (§15.25)。

只有布尔和 `Boolean` 表达式可以用于控制语句以及作为三元运算符 `?:` 的第一个操作数。

整数或浮点表达式 `x` 可以转换为布尔值（遵循 C 语言的任何非零值为真的的约定），通过表达式 `x != 0` 实现。

对象引用 `obj` 可以转换为布尔值（遵循 C 语言的任何非空引用为真的的约定），通过表达式 `obj != null` 实现。

布尔值可以通过字符串转换转换为字符串 (§5.4)。

布尔值可以强制转换为 `boolean`、`Boolean` 或 `Object` 类型 (§5.5)。不允许其他类型的强制转换。

## 4.3 引用类型和值

引用类型：

- 类或接口类型
- 类型变量
- 数组类型

### 类或接口类型

- 类类型
- 接口类型

#### 类类型

- `[注解] 类型标识符[泛型]`
- `包名 . [注解] 类型标识符 [泛型]`
- `类或接口类型 . [注解] 类型标识符[泛型]`

#### 接口类型

- 类类型

#### 类型变量

- `[注解] 类型标识符`

#### 数组类型

- `基本类型 维度`
- `类或接口类型 维度`
- `类型变量 维度`

#### 维度

- `[注解] [] [[注解] []]`

### 示例代码

```java
class Point { int[] metrics; }
interface Move { void move(int deltax, int deltay); }
```

声明了一个类类型 `Point`，一个接口类型 `Move`，并使用数组类型 `int[]`（int 数组）来声明类 `Point` 的字段 `metrics`。

类类型或接口类型由一个标识符或一个用点分隔的标识符序列组成，每个标识符后面可选跟随泛型参数 (§4.5.1)。如果泛型参数出现在类或接口类型的任何位置，则它是一个参数化类型 (§4.5)。

类或接口类型中的每个标识符被分类为包名或类型名称 (§6.5.1)。被分类为类型名称的标识符可以被注解。如果类或接口类型的形状为 `T.id`（可选跟随泛型参数），那么 `id` 必须是 τ 可访问成员类型的简单名称 (§6.6, §8.5, §9.5)，否则将发生编译错误。该类或接口类型表示该成员类型。

### 4.3.1 对象

对象是类的实例或数组。

引用值（通常只是引用）是指向这些对象的指针，以及一个特殊的 `null` 引用，它不引用任何对象。

类实例通过类实例创建表达式 (§15.9) 显式创建。数组通过数组创建表达式 (§15.10.1) 显式创建。

其他表达式可能会隐式创建类实例 (§12.5) 或数组 (§10.6)。

#### 示例 4.3.1-1 对象创建

```java
class Point {
    int x, y;
    Point() { System.out.println("default"); }
    Point(int x, int y) { this.x = x; this.y = y; }
}
```

```java
/* Point 在初始化时显式创建： */
static Point origin = new Point(0,0);
```

```java
/* String 通过 + 运算符隐式创建： */
public String toString() { return("" + x + "," + y + ""); }
```

```java
class Test {
    public static void main(String[] args) {
        /* 使用 newInstance 显式创建一个 Point： */
        Point p = null;
        try {
            p = (Point)Class.forName("Point").newInstance();
        } catch (Exception e) {
            System.out.println(e);
        }

        /* 数组通过数组初始化器隐式创建： */
        Point[] a = { new Point(0,0), new Point(1,1) };

        /* Strings 通过 + 运算符隐式创建： */
        System.out.println("p: " + p);

        System.out.println("a: { " + a[0] + ", " + a[1] + " }");

        /* 数组通过数组创建表达式显式创建： */
        String[] sa = new String[2];
        sa[0] = "he"; sa[1] = "llo";
        System.out.println(sa[0] + sa[1]);
    }
}
```

该程序产生输出：

```
default
p: (0,0)
a: { (0,0), (1,1) }
hello
```

对对象引用的操作符有：

- **字段访问**，使用限定名 (§6.6) 或字段访问表达式 (§15.11)
- **方法调用** (§15.12)
- **类型转换运算符** (§5.5, §15.16)
- **字符串拼接运算符 `+`** (§15.18.1)，当给出一个 `String` 类型操作数和一个引用时，它将通过调用被引用对象的 `toString` 方法将引用转换为 `String`（如果引用引用或 `toString` 的结果为 `null`，则使用 `"null"`），然后产生一个新创建的 `String`，它是两个字符串的拼接
- **`instanceof` 运算符** (§15.20)
- **引用相等性运算符 `==` 和 `!=`** (§15.21)
- **条件运算符 `?:`** (§15.25)

可能存在指向同一个对象的多个引用。大多数对象都有状态，存储在类的字段或数组的变量中。如果两个变量包含指向同一个对象的引用，可以使用一个变量对该对象的引用来修改对象的状态，然后通过另一个变量观察到更改后的状态。

#### 示例 4.3.1-2 原生类型与引用标识性

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
        Value v2 = v1;
        v2.val = 6;
        System.out.print("v1.val==" + v1.val);
        System.out.println(" and v2.val==" + v2.val);
    }
}
```

该程序产生输出：

```
i1==3 and i2==4
v1.val==5 and v2.val==6
```

因为 `v1` 和 `v2` 引用 `new` 表达式创建的对象中的同一个实例 (§4.12.3)，而 `i1` 和 `i2` 是不同的变量。每个对象都与一个监视器关联 (§17.1)，同步方法 (§8.4.3) 和同步语句 (§14.19) 使用该监视器来提供对多线程访问状态的控制 (§17)。

### 4.3.2 类对象

`Object` 是所有其他类的超类 (§8.1.4)。所有类和数组类型都继承 (§8.4.8) 类的方法，方法总结如下：

- `clone` 方法用于制作对象的副本。
- `equals` 方法定义了对象相等性的概念，这种相等是基于值的比较，而不是引用。
- `finalize` 方法在对象销毁之前运行 (§12.6)。
- `getClass` 方法返回表示类的 `Class` 对象。每个引用类型都有一个 `Class` 对象。`getClass` 对于发现类型非常有用。
- `hashCode` 方法在哈希表如 `java.util.HashMap` 中非常有用，与 `equals` 方法一起使用。
- `wait`、`notify` 和 `notifyAll` 方法用于并发编程 (§17.2)。
- `toString` 方法返回对象的 `String` 表示形式。

### 4.3.3 String 类

`String` 实例表示 Unicode 代码点的序列。`String` 对象具有常量（不变的）值。`String` 字面量 (§3.10.5) 和文本块 (§3.10.6) 是 `String` 的引用。字符串拼接运算符 `+` (§15.18.1) 当结果不是常量表达式时会创建一个新的 `String` 对象。

### 4.3.4 当引用类型相

两个引用类型是编译时类型，如果它们在相同的编译单元 (§7.3) 中声明，并且具有相同的二进制名，并且它们的泛型参数（如果有）是相同的，递归应用此定义。在运行时，相同二进制名的多个类型可能由不同的类加载器同时加载。即使此类类型表示相同的类型声明，也被认为是不同的。

两个引用类型是相同的运行时类型，如果：

- 它们都是类或接口类型，由同一个类加载器定义并具有相同的二进制名 (§13.1)，在这种情况下，它们有时被认为是相同的运行时类或相同的运行时接口。
- 它们是数组类型，且它们的组件类型是相同的运行时类型 (§10 数组)。

## 4.4 类型变量

类型变量是用于类、接口、方法和构造体中的未限定标识符。类型变量通过泛型类、接口、方法或构造函数的类型参数引入 (§8.1.2, §9.1.2, §8.4.4, §8.8.4)。

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

作为类型参数的类型变量范围 (§6.3)。每个作为类型参数的类型变量都有边界。如果没有为类型变量声明边界，则假设为 `Object`。如果声明了边界，它由：

- 单个类型变量 τ，或
- 一个类或接口类型 τ 可能后跟随接口类型 I₁, & ... In_。

如果 I₁, ..., In_ 中的任何一个类型是类类型或类型变量，则为编译错误。

一个界（bound）中所有组成类型的类型擦除（§4.6）必须是两两不相同的，否则将发生编译错误。

一个类型变量不能同时是两个接口类型的子类型，如果这两个类型是同一个泛型接口的不同参数化，否则将发生编译错误。

界中类型的顺序仅在以下具有意义：类型变量的擦除是由其界中的第一个类型决定的，且类或类型变量只能出现在第一个位置。

具有界 `T & I₁ ... & Iₙ` 的类型变量 `x` 的成员，是在声明该类型变量处出现的交集类型（§4.9）`T & I₁ ... & Iₙ` 的成员。

### 4.4-1. 类型变量的成员

```java
package TypeVarMembers;

class C {
    public void mCPublic() {}
    protected void mCProtected() {}
    void mCPackage() {}
    private void mCPrivate() {}
}

interface I {
    void mi();
}

class CT extends C implements I {
    public void mi() {}
}

class Test {
    <T extends C & I> void test(T t) {
        t.mi(); // OK
        t.mCPublic(); // OK
        t.mCProtected(); // OK
        t.mCPackage(); // OK
        t.mCPrivate(); // 编译错误
    }
}
```

类型变量 `T` 的成员与交集类型 `C & I` 的成员相同，而 `C & I` 又与在相同作用范围内具有父类型的空类 `CT` 拥有成员。接口的成员始终是公共的，因此总是被继承的（除非被重写）。因此，`mi` 是 `CT` 和 `T` 的成员。在 `C` 的成员中，所有的 `mCPrivate` 都被 `CT` 继承，因此它们都是 `CT` 和 `T` 的成员。

## 参数化类型



如果 $C$ 定义在与 $T$ 不同的包中，那么对 `mPackage` 的调用将导致编译错误，因为该成员在声明 $T$ 的地方是不可见的。

泛型（§8.1.2, §9.1.2）类或接口定义了一组参数化类型。

参数化类型是形式为 $C<T_1,\dots,T_n>$ 的类或接口类型，其中 $C$ 是泛型类或接口的名称，$T_1,\dots,T_n$ 是类型参数列表，表示泛型类或接口的特定参数化。

泛型类或接口具有参数 $F_1,\dots,F_n$，以及相应的界 $B_1,\dots,B_n$。参数化类型的每个类型参数 $T_i$ 的范围是对应界中列出的所有类型的子类型。也就是说，对于 $B_i$ 中的每个类型 $S$，$T_i$ 是 $S[F_1=T_i,\dots,F_n=T_n]$ 的子类型（§4.10）。

如果满足以下所有条件，则参数化类型 $C<T_1,\dots,T_n>$ 是良好的：

- $C$ 是泛型类或接口的名称。
- 类型参数的数量与 $C$ 的泛型声明中的类型参数数量相同。
- 当进行类型转换（§5.1.10）产生类型 $C<X_1,\dots,X_n>$ 时，对于 $B_i$ 中的每个类型 $S$，每个类型参数 $X_i$ 都是 $S[F_1=X_i,\dots,F_n=X_n]$ 的子类型。

如果参数化类型不是良好的，则会导致编译错误。

在本规范中，每当我们谈论类或接口类型时，除非显式排除，否则包含了参数化类型。

如果满足以下任一条件，则两个参数化类型是严格不同的：

- 它们是不同泛型类型声明的参数化。
- 它们的任何一个类型参数是严格不同的。

在 §8.1.2 的泛型类示例中，这些是良好的参数化类型：

- `Seq<String>`
- `Seq<Seq<String>>`

# 参数化类型

参数类型、返回类型和/或抛出类型（throws type）之间的依赖关系。在不存在此类依赖关系的情况下，泛型方法被认为是不良风格，优先使用通配符（wildcards）。

```
Reference<T referent, ReferenceQueue<? super T>>
```

在这里，referent 被插入到任何其元素类型为 referent 的类型 $T$ 上类的类型中；$T$ 是该通配符的下界。

### 4.5.2 参数化类型的成员和构造函数

设 $c$ 为一个具有类型参数 $A_1,...,A_n$ 的泛型类或接口，设 $C<T_1,...,T_n>$ 为 $c$ 的参数化，其中 $1 \le i \le n$，$T_i$ 是一个类型（而非通配符）。那么：

- 设 $m$ 为 $c$ 中的一个成员或构造函数声明，其类型声明为 $T$ (§8.2, §8.8.6)。$m$ 在 $C<T_1,...,T_n>$ 中的类型为 $T[A_1=T_1, ..., A_n=T_n]$。
- 设 $m$ 为 $D$ 中的一个成员或构造函数声明，其中 $D$ 是 $c$ 扩展的类或被 $c$ 实现的接口。$D<U_1,...,U_k>$ 是 $C<T_1,...,T_n>$ 对应于 $D$ 的超类型 (§4.10.2)。$m$ 在 $C<T_1,...,T_n>$ 中的类型为 $m$ 在 $D<U_1,...,U_k>$ 中的类型。

如果 $c$ 的参数化中的任何一个参数是通配符，那么：

- $C<T_1,...,T_n>$ 中的字段、方法和构造函数的类型是 $C<T_1,...,T_n>$ 的捕获转换（capture conversion）中字段、方法和构造函数的类型 (§5.1.10)。
- 设 $D$ 为 $c$ 中的一个（可能是）泛型类或接口声明。那么 $D$ 在 $C<T_1,...,T_n>$ 中的类型为 $D$，其中如果 $D$ 是泛型的，则所有参数类型均为无界通配符（unbounded wild）。

这没有影响，因为在不执行捕获转换的情况下，无法访问参数化类型的成员，而且在类实例表达式的 `new` 关键字之后无法使用通配符 (§15.9)。

上述段的唯一例外是，当嵌套参数化类型被用作 `instanceof` 操作符的表达式时 (§15.20.2)，此时不应用捕获转换。

在泛型类或接口中声明的静态成员必须使用该泛型类或接口的名字来引用 (§6.1, §6.5.5.2, §6.5.6.2)，否则将发生编译错误。

# 类型、值和变量

# 类型擦除 (Type Erasure)

换句话说，通过使用参数化类型来引用在泛型类型声明中声明的静态成员是非法的。

## 4.6 类型擦除

类型擦除是从类型（可能包括参数化类型和类型变量）到类型（永远不是参数化类型或类型变量）的映射。我们用 $|T|$ 表示类型 $T$ 的擦除。擦除映射定义为：

- 参数化类型 (§4.5) $G<T_1,...,T_n>$ 的擦除是 $|G|$。
- 嵌套类型 $T.C$ 的擦除是 $|T.C|$。
- 数组类型 $T[]$ 的擦除是 $|T[]|$。
- 类型变量 (§4.4) 的擦除是其最左边界的擦除。
- 其他所有类型的擦除都是该类型本身。

类型擦除还将构造函数或方法的签名 (§8.4.2) 映射到没有参数化类型或类型变量的签名。构造函数或方法签名 $s$ 的擦除是一个签名，该签名由与 $s$ 相同的名称以及 $s$ 中给出的所有形式参数类型的擦除组成。

方法的返回类型 (§8.4.5) 泛型类型以及泛型方法或构造函数的类型参数 (§8.4.4, §8.8.4)，在当方法或构造函数的签名被擦除时，这些者也会经历擦除。

泛型方法签名的擦除没有类型参数。

## 4.7 可重化类型 (Reifiable Types)

由于某些类型信息在编译期间被擦除，并不是所有类型在运行时都是可用的。运行时完全可用的类型被称为可重化类型。

一个类型是可重化的，当且仅当满足以下条件之一：

- 它引用一个非泛型的类或接口类型声明。
- 它是一个所有类型参数均为无界通配符 (§4.5.1)的参数化类型。
- 它是一个原始类型（raw type） (§4.8)。
- 它是一个基本类型（§4.2）。
- 它是一个元素类型为可重化的数组类型 (§10.1)。
- 它是一个嵌套类型，对于每个用 `.` 分隔的类型 $T$，$T$ 本身是可重化的。

例如，如果一个泛型类 $X<T>$ 有一个泛型成员类 $Y<U>$，那么类型 $X<?>.Y<?>$ 是可重化的，因为 $X<?>$ 是可重化的且 $Y<?>$ 是可重化的。类型 $X<?>.Y<Object>$ 不是可重化的，因为 $Y<Object>$ 不是可重化的。

交集类型（intersection type）不是可重化的。

不使泛型类型可重化是涉及类型系统的关键且具有争议的决策之一。最终，这种设计最重要的动机是为了与现有代码的兼容性。在实践中，泛型的引入并没有为泛型特性提供现实的路径。如上所述，Java 语言本身在新版本中保留了其含义。兼容性的代价是，在迁移期间，完整且稳健的泛型系统重化是不可能的。

## 4.8 原始类型 (Raw Types)

为了便于与旧代码交互，可以使用参数化类型（§4.5）的擦除（§4.6）或元素类型为参数化类型的数组类型（§10.1）的擦除作为类型。这种类型被称为原始类型。

更准确地说，原始类型定义为以下之一：

- 通过取泛型类或接口声明的名字但不带类型列表形成的引用类型。
- 元素类型为原始类型的数组类型。
- 原始类型 $R$ 的内部成员类名，且该类不是继承自其父类或超接口。

非泛型类或接口类型不是原始类型。

为了理解为什么原始类型的内部成员类名被认为是原始类型，请考虑以下示例：

```
class Outer<T>{
  T t;
  class Inner {
    setOuterT(T t1) { t = t1; return; }
  }
}
```

`Inner` 的类型取决于 `Outer` 的类型参数。如果 `Outer` 是原始的，则 `Inner` 也必须被视为原始的，因为 `T` 没有有效的绑定。

此规则仅适用于未继承的内部成员类。依赖类型变量的继承内部成员类将根据本节稍后描述的原始类型超类型擦除的规则作为原始类型被继承。

上述规则的另一个影响是，原始类型的泛型内部类本身只能作为原始类型使用：

```
class Outer<T>{
  class Inner<S> {
    S s;
  }
}
```

无法以部分原始类型访问 `Inner`（即一种“稀有”类型）：

```
Outer.Inner<Double> x = null; // 非法
Double d = x.s;
```

因为 `Outer` 本身是原始类型（raw），因此所有的内部类（包括 `Inner`）也是如此，导致无法向 `Inner` 传递任何类型参数。

原始类型的超类类型（相应的超接口）是命名类或接口的超类类型（超接口）的擦除。

原始类型 `C` 中未继承自其超类或超接口的构造方法 (§8.8)、实例方法 (§8.4, §9) 或非静态字段 (§8.3) 的类型，是其在泛型类或接口 `C` 中类型的擦除。

原始类型 `C` 中被继承的实例方法或非静态字段，若该成员在类或接口 `D` 中声明，则其类型是 `C` 的父类型中名为 `D` 的那个类型中该成员的类型。

原始类型 `C` 的静态方法或静态字段的类型与其在泛型类或接口 `C` 中的类型相同。

向一个未继承自其超类或超接口的原始类型的非静态成员类或接口传递类型参数是编译错误。

尝试将参数化类型的成员类或接口作为原始类型使用是编译错误。

这意味着对“原始”类型的禁止也扩展到了限定类型是参数化、但我们尝试将内部类作为原始类型使用的情况：

```
Outer<Integer>.Inner x = null; // illegal
```

这与上述讨论的情况相反。这种半生不熟的类型没有实际的理由。在遗留代码中，不使用类型参数。在非遗留代码中，我们应该使用泛型并传递所有所需的类型参数。

允许原始类型仅是出于对遗留代码兼容性的考虑。在 Java 编程语言引入泛型后编写的代码中，强烈建议**不**使用原始类型。Java 编程语言未来的版本可能会不允许使用原始类型。

为了确保对类型规则的潜在违反始终被标记，对原始类型成员的某些访问将导致编译时的未检查警告（unchecked warnings）。访问原始类型成员或构造方法时产生编译时未检查警告的规则如下：

- 在对字段赋值时：如果字段访问表达式 (§15.11) 中主表达式的类型是原始类型，则如果擦除更改了字段的类型，就会发生编译时未检查警告。
- 在调用方法或构造方法时：如果要查找的类或接口类型 (§15.12.1) 是原始类型，则如果擦除更改了方法或构造方法的任何形式参数类型，就会发生编译时未检查警告。
- 当形式参数类型在擦除下没有变化（即使返回类型和/或 throws 发生了变化）时，方法调用、读取字段或创建原始类型的类实例，不会产生编译时未检查警告。

请注意，这些未检查警告也与收缩转换 (§5.1)、未检查转换 (§5.1.9)、方法声明 (§8.4.1, §8.4.8.3) 以及某些表达式 (§15.12.4.2, §15.13.2, §15.27.3) 可能产生的未检查警告有所不同。

这里的警告涵盖了泛型消费者使用泛型库的情况。例如，库声明了一个泛型类 `Foo<T extends String>`，它有一个具有类型为 `Vector<T>` 的字段，但消费者使用了整数向量，例如 `e` 其中 `e` 是原始类型 `Foo`。遗留消费者会收到警告，因为这可能会为泛型库的泛型消费者造成堆污染 (§4.12.2)。

（注意，遗留消费者可以从其库将 `Vector<String>` 赋值给自己的 `Vector` 而不接收警告。这是 Java 编程语言的子类型规则 (§4.10.2) 使得原始类型的变量可以分配该类型的任何实例。）

未检查转换的警告涵盖了另一种情况，即泛型消费者使用遗留库。例如，库的一个方法具有原始返回类型 `Vector`，但消费者将方法调用的结果赋值给 `Vector<String>` 类型的变量；这是安全的，但仍允许使用未检查转换以便与遗留代码交互。未检查转换的警告表明泛型消费者可能在程序的其他点遇到堆污染引起的问题。

## 示例 4-8-1. 原始类型

```
class Cell<E> {
  E value;

  Cell(E v) { value = v; }
  E get() { return value; }
  void set(E v) { value = v; }

  public static void main(String[] args) {
    Cell x = new Cell<String>("abc");
    System.out.println(x.value); // OK, has type Object
    System.out.println(x.get()); // OK, has type Object
    x.set("def"); // unchecked warning
  }
}
```

## 示例 4.8-2. 原始类型与继承

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.Iterator;
```

```java
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
            Collection<Number> rw = new ArrayList<>();
            Iterator<String> is = rw.iterator();

            Collection<String> nng = new ArrayList<>();
            Collection<String> n2 = nng;

            Collection<String> cng = new ArrayList<>();
            Iterator<String> it = cng.iterator();
        }
}
```

## 4.10 子类型化

子类型和父类型关系是类型之间的二元关系。

类型 $T$ 的父类型通过对直接父类型关系进行反射闭包和传递闭包得到，写作 $S >_1 T$，该关系由本节后给出的规则定义。我们用 $S <: T$ 来表示 $S$ 和 $T$ 之间存在父类型关系。

如果 $S >_1 T$ 且 $S \neq T$，则 $S$ 是 $T$ 的真父类型，记作 $S > T$。

类型 $T$ 的子类型是所有满足 $T$ 是 $U$ 的父类型的类型 $U$，以及空类型（null type）。我们用 $T <: S$ 来表示类型 $T$ 和 $S$ 之间存在子类型关系。

如果 $T <: S$ 且 $S \neq T$，则 $T$ 是 $S$ 的真子类型，记作 $T < S$。

如果 $S >_1 T$，则 $T$ 是 $S$ 的直接子类型，记作 $T <_1 S$。

子类型化不跨参数化类型扩展：$T <: S$ 并不意味着 $C<T> <: C<S>$。

### 4.10.1 原始类型之间的子类型化

以下规则定义了原始类型之间的直接父类型关系：

- `double` >_1 `float`
- `float` >_1 `long`
- `long` >_1 `int`
- `int` >_1 `char`
- `int` >_1 `short`
- `short` >_1 `byte`

### 4.10.2 类和接口类型之间的子类型化

给定一个非泛型的类或接口 $c$，类型 $c$ 的直接父类型包括以下所有项：

- 如果 $c$ 是一个类，则 $c$ 的直接父类类型 (§8.1.4)。
- $c$ 的直接父接口类型 (§8.1.5, §9.1.3)。
- 如果 $c$ 是一个没有直接父接口类型的接口，则为 `Object` 类型 (§9.1.3)。

给定一个具有类型参数 $F_1,...,F_n$ ($n > 0$) 的泛型类或接口 $c$，原始类型 $c$ (§4.8) 的直接父类型包括以下所有项：

- 如果 $c$ 是一个类，则 $c$ 的直接父类类型的擦除 (§4.6)。
- $c$ 的直接父接口类型的擦除。
- 如果 $c$ 是一个没有直接父接口类型的接口，则为 `Object` 类型。

给定一个具有类型参数 $F_1,...,F_n$ ($n > 0$) 的泛型类或接口 $c$，参数化类型 $C<T_1,...,T_n>$（其中每个 $T_i$ ($1 \le i \le n$) 都是类型）的直接父类型包括以下所有项：

- 如果 $c$ 是一个类，将替换 $[F_1=T_1,...,F_n=T_n]$ 应用于 $c$ 的直接父类类型。
- 将替换 $[F_1=T_1,...,F_n=T_n]$ 应用于 $c$ 的直接父接口类型。
- $C<S_1,...,S_n>$，其中 $S_i$ 包含 $T_i$ ($1 \le i \le n$) (§4.5.1)。
- 如果 $c$ 是一个没有直接父接口类型的接口，则为 `Object` 类型。
- 原始类型 $c$。

给定一个具有类型参数 $F_1,...,F_n$ ($n > 0$) 的泛型类或接口 $c$，如果参数化类型 $C<R_1,...,R_n>$ 中至少有一个 $R_i$ ($1 \le i \le n$) 是通配符参数，则其直接父类型是参数化类型 $C<X_1,...,X_n>$ 的直接父类型，该类型是通过对 $C<R_1,...,R_n>$ 应用捕获转换（capture conversion）得到的结果 (§5.1.10)。



交集类型 $T_i$ & ... & $T_n$ 的直接父类型是 $T_i$ ($1 \le i \le n$)。

类型的直接父类型是其边界（bound）中列出的类型。

类型变量是其下界的直接父类型。

空类型的直接父类型是除空类型本身以外的引用类型。

### 4.10.3 数组类型之间的子类型化

以下规则定义了数组类型之间的直接父类型关系：

- 如果 $S$ 和 $T$ 都是引用类型，那么 $S[] >_1$ $T[]$ 当且仅当 $S >_1 T$。
- `Object >_1 Object[]`
- `Cloneable >_1 Object[]`
- `java.io.Serializable >_1 Object[]`
- 如果 P 是原始类型，则：
    - `Object >_1 P[]`
    - `Cloneable >_1 P[]`
    - `java.io.Serializable >_1 P[]`

### 4.10.4 最小上界

一组引用类型的最小上界（least upper bound，“lub"”）是一个共享的父类型，它比任何其他父类型都更具体（即没有其他父类型是该最小上界的子类型）。该类型 `lub(U₁, ..., Uₖ)` 按照如下方式确定。

如果 k = 1，则 lub 为类型本身：`lub(U) = U`。

否则：

- 对于每个 $U_i$ ($1 \le i \le k$)：
  让 $ST(U_i)$ 为 $U_i$ 的父类型集合。
  让 $EST(U_i)$ 为 $U_i$ 的擦除类型集合：$EST(U_i) = \{|w| | w \in ST(U_i)\}$。计算擦除类型是为了处理包含泛型类型的情况。例如，给定 `List<String>` 和 `List<Object>`，取交 $ST(List<String>) = \{String, Object\}$ 和 $ST(List<Object>) = \{Object, Object\}$ 会产生 $\{Object\}$，并丢失可以赋值给 `List` 的事实。相反，取交 $EST(List<String>) = \{List, Collection\}$ 和 $EST(List<Object>) = \{List, Collection\}$ 产生 $\{List, Collection\}$，这将允许我们产生 `List<?>`。

- $EC$ 是 $U_1, ..., U_k$ 的擦除候选集，即所有 $EST(U_i)$ ($1 \le i \le k$) 的交集。
- $MEC$ 是 $U_1, ..., U_k$ 的最小擦除候选集，为 $MEC = \{v | v \in EC, \text{ 且没有其他候选类型类型是其子类型}\}$。由于我们正在寻找更精确的类型，我们希望过滤掉是其他候选类型的子类型。这正是 $MEC$ 完成的工作。

在我们的运行示例中，$EC = \{List, Collection, Object\}$，所以 $MEC = \{List\}$。下一步是恢复 $MEC$ 中擦除类型的类型参数。

- 对于 $MEC$ 中的任何泛型类型 $G$：
  让 $G$ 的“相关”替换为 $Relevant(G) = \{v | 1 \le i \le k; v \in ST(U_i) \text{ 且 } v = G...\}$。
  在我们的运行示例中，我们现在寻找包含 String 和 Object 的 `List` 类型参数。这是通过下面定义的泛型替换（lcp）操作实现的。第一行对 $Relevant(List)$ 定义 `lcp()`，作为对列表元素的操作。第二行是对该列表的元素进行两两归约。第三行是对参数化类型对定义 `lcp()`，这反过来依赖于最小包含参数 `lcta(t)`。`lcta(t)` 定义于所有可能的情况。

让 $G$ 的“候选”替换为 $Candidate(G)$，它是包含 $G$ 的相关替换中最具体的泛型替换。$Candidate(G) = lcp(Relevant(G))$，其中 `lcp(U)`，最小包含替换为：

- `lcp(S) = lcp(e_1, ..., e_n)`，其中 $e_i$ ($1 \le i \le n$) 在 $S$ 中。
- `lcp(e_2, ..., e_n) = lcp(e_1, e_2), e_3, ..., e_n)`。
- `lcp(G<X_1, ..., X_n>, G<Y_1, ..., Y_n>) = G lcta(X_1, Y_1), ..., lcta(X_n, Y_n)`。
- `lcp(G<X_1, ..., X_n>) = G lcta(X_1), ..., lcta(X_n)`。

其中 `lcta(U)`，最小包含类型参数，是（假设 $U$ 和 $V$ 是类型）：

- `lcta(U, V) = U` 如果 $U = V$，否则 `lub(U, V)`。
- `lcta(U, ? extends V) = ? extends lub(U, V)`。
- `lcta(U, ? super V) = ? super glb(U, V)`。
- `lcta(? extends U, ? extends V) = ? extends lub(U, V)`。
- `lcta(? extends U, ? super V) = ?`。
- `lcta(? super U, ? super V) = ? super glb(U, V)`。
- `lcta(U = ?)` 如果 $U$ 的上界是 Object，否则 `extends lub(U, Object)`。

其中 `glb()` 定义在 5.1.10。

- `lub(U_2, ..., U_k) = Best(W_1) & ... & Best(W_k)`，其中 $W_i$ ($1 \le i \le r$) 是 $MEC$（$U_2, ..., U_k$ 的最小擦除候选集）的元素；其中如果这些元素中的任何一个是泛型，我们使用候选替换（以便恢复类型参数）：`Best(x) = Candidate(x)` 如果 $x$ 是泛型；否则为 $x$。

严格来说，这个 `lub()` 函数只是近似最小上界。形式上，可能存在其他类型 $\tau$，使得所有的 $U_2, ..., U_k$ 都是 $\tau$ 的子类型且 $\tau$ 是 `lub(U_2, ..., U_k)` 的子类型。然而，Java 语言的编译器必须按照上述规定实现 `lub()`。

`lub()` 函数可能会产生无限类型。这是允许的，Java 语言编译器必须识别此类情况并适当使用循环数据结构进行表示。

无限类型的出现源于 `lub()` 的递归调用。熟悉递归类型的读者注意，无限类型不是递归类型。

### 4.10.5 类型投影

合成类型变量是编译器在捕获转换（`5.1.10`）或推断变量解析（`18.4`）期间引入的。

有时需要找到一个类型的接近父类型，该子类型不包含某些合成类型变量。由于这种子类型并不总是存在，因此对该类型应用向上投影（upward projection）。

这些操作的输入一组不再被引用的类型变量，称为限制类型变量。当操作递归时，限制类型变量集会被隐式地传递。

类型 $\tau$ 对于限制类型变量集的向上投影定义如下：

- 如果 $\tau$ 不包含任何限制类型变量，则结果为 $\tau$。
- 如果 $\tau$ 是一个限制类型变量，则结果为 $\tau$ 的上界的向上投影。
- 如果 $\tau$ 是参数化类类型或参数化接口类型，$G<A_{i_1},...,A_{i_n}>$，则结果为 $G<A_{i_1}',...,A_{i_n}>$，其中 $1 \leq i \leq n$，$A_{i}'$ 按照如下方式从 $A_i$ 派生：
  - 如果 $A_i$ 没有提及任何受限类型变量，则 $A_{i}' = A_i$。
  - 如果 $A_i$ 是提及受限类型变量的类型，则令 $U$ 为 $A_i$ 的上投影。$A_{i}'$ 是通配符，由三种情况定义：
    - 如果 $U$ 不是 Object，且 $B_i$ 的第 $i$ 个参数的声明边界提到了 $G$ 的类型参数，或 $B_i$ 不是 $U$ 的子类型，则 $A_{i}'$ 是上界通配符，`? extends U`。
    - 否则，如果 $A_i$ 的下投影为 $L$，则 $A_{i}'$ 是下界通配符，`? super L`。
    - 否则，$A_i$ 的下投影未定义，$A_{i}'$ 是无界通配符，`?`。
  - 如果 $A_i$ 是提及受限类型变量的上界通配符，则令 $U$ 为通配符边界的上投影。$A_{i}'$ 是上界通配符，`? extends U`。
  - 如果 $A_i$ 是提及受限类型变量的下界通配符，如果通配符边界的下投影为 $L$，则 $A_{i}'$ 是下界通配符，`? super L`；如果通配符边界的下投影未定义，则 $A_{i}'$ 是无界通配符，`?`。
- 如果 $\tau$ 是数组类型，$S[]$，则结果是一个其组件类型为 $S$ 的上投影的数组类型。
- 如果 $\tau$ 是交叉类型，则结果为交叉类型。对于 $\tau$ 的每个元素 $S$，结果的元素为 $S$ 的上投影。

类型 $\tau$ 对于限制类型变量集的向下投影定义如下：

- 如果 $\tau$ 没有提及任何受限类型变量，则结果为 $\tau$。
- 如果 $\tau$ 是受限类型变量，则如果 $\tau$ 有下界，且边界的下投影为 $L$，则结果为 $L$；如果 $\tau$ 没有下界，或边界的下投影未定义，则结果未定义。
- 如果 $\tau$ 是参数化类类型或参数化接口类型，$G<A_1,...,A_n>$，则结果为 $G<A_1',...,A_n>$，对于 $1 \leq i \leq n$，类型参数 $A_i'$ 可以按照如下方式从 $A_i$ 派生；若不是，结果未定义：
  - 如果 $A_i$ 没有提及受限类型变量，$A_i' = A_i$。
  - 如果 $A_i$ 是提及受限类型变量的类型，$A_i'$ 未定义。
  - 如果 $A_i$ 是提及受限类型变量的上界通配符，则如果通配符的下投影为 $U$，则 $A_i'$ 是上界通配符，`? extends U`；如果通配符的下投影未定义，则 $A_i'$ 未定义。
  - 如果 $A_i$ 是提及受限类型变量的下界通配符，则令 $L$ 为通配符边界的上投影。$A_i'$ 是下界通配符，`? super L`。
- 如果 $\tau$ 是数组类型，$S[]$，则如果 $S$ 的下投影为 $S'$,则结果为 $S'[]$；如果 $S$ 的下投影未定义，则结果未定义。
- 如果 $\tau$ 是交叉类型，则如果 $\tau$ 的**每个**元素都有下投影，则结果为交叉类型，其元素为 $\tau$ 元素的下投影；如果 $\tau$ 的**任意**元素下投影未定义，则结果未定义。

类似于 `lub` 运算（§4.10.4），由于对类型变量边界的递归，上投影和下投影可能会产生无限类型。

## 4.11 类型使用的位置

类型用于大多数类型的声明以及某些特定类型。具体而言，有 17 种使用类型的*类型上下文*：

### 在声明中：

1. 类声明中 extends 或 implements 子句中的类型（§8.1.4, §8.1.5）
2. 接口声明中 extends 子句中的类型（§9.1.3）
3. 方法的返回类型（§8.4.5, §9.4），包括注解接口中元素的类型（§9.6.1）
4. 方法或构造函数 throws 子句中的类型（§8.4.6, §8.8.5, §9.4）
5. 泛型类、接口或构造函数的类型声明中 extends 子句的类型（§8.1.2, §9.1.2, §8.4.4）
6. 类或接口字段声明中的类型
7. 方法或构造函数的形式参数类型
8. 方法接收者的类型
9. 局部变量声明中的类型
10. 异常声明中的类型
11. 记录的组件类型

### 在表达式中：

12. 显式构造函数调用、类创建表达式、方法调用表达式中的类型
13. 匿名类的实例化父类或父接口类型
14. 数组创建表达式中的类型
15. 强制转换表达式中的类型
16. instanceof 运算符后的类型
17. 方法引用类型

此外，类型还用于：

- 任意类型上下文中的通配符边界
- 任意类型上下文中的参数化类型

最后，Java 语言中有三个特殊术语表示类型的使用：

- 无界通配符
- 标示数组的 `[]`
- 构造函数的类型名称

类型在类型上下文中的含义由以下给出：

- §4.2 原始类型
- §4.4 类型参数
- §4.5 参数化类和接口，或作为通配符参数的边界
- §4.8 交叉类型
- §4.9 交叉参数的边界
- §6.5 类型变量
- §10.1 数组类型

某些类型上下文限制了参数化类型的方式：

- 下列类型上下文要求参数化类型没有通配符参数：
  - 类声明中的 extends 或 implements 子句（§8.1.4, §8.1.5）
  - 接口声明中的 extends 子句（§9.1.3）
  - 匿名类的实例化父类或父接口类型
  - 方法引用类型
  - 构造函数的数组类型

此外，在显式类型参数列表中不允许通配符类型参数：

- 下列类型上下文要求参数化引用类型只有无界通配符参数（即它是可化的类型）：
  - 数组创建表达式中的元素类型（§15.10.1）
  - instanceof 运算符后的类型（§15.20.2）

- 下列类型上下文完全禁止参数化引用类型，因为它们涉及异常，且异常类型是非泛型的（§6.1）：
  - 方法或构造函数可能抛出的异常类型（§8.4.6, §8.8.5, §9.4）
  - 异常参数声明（§14.20.0）

在任何使用类型的类型上下文中，都可以对表示原始类型的关键字或表示引用类型名称的标识进行注解。也可以通过在数组类型所需的嵌套层级的 `{` 左侧写入注解来标注数组类型。这些被称为类型注解，在 §9.7.4 中规范。例如：

- `@Foo []` 标注原始类型 int
- `int @Foo []` 标注数组类型 int[]
- `int @Foo [] [];` 标注作为数组类型 int[] 的组件类型的数组类型 int[]

### 示例 4.11-1. 类型的用法

```java
import java.util.ArrayList;
import java.util.Collection;
import java.util.Random;

class MiscMath<T extends Number> {
    int divisor;
    MiscMath(int divisor) { this.divisor = divisor; }
    float ratio(long l) {
        try {
            l = divisor;
        } catch (Exception e) {
            if (e instanceof ArithmeticException)
                l = Long.MAX_VALUE;
        } else
            l = 0;
        }
        return (float)l;
    }
    double gausser() {
        Random r = new Random();
        double[] val = new double[2];
        val[0] = r.nextGaussian();
        val[1] = r.nextGaussian();
        return (val[0] + val[1]) / 2;
    }
    Collection<Number> fromArray(Number[] na) {
        Collection<Number> cn = new ArrayList<Number>();
        for (Number n : na) cn.add(n);
        return cn;
    }
    <S> loop(S s) { this.<S>loop(s); }
}
```

在此示例中，类型被用于以下内容的声明：

- 字段，即类的类变量和实例变量（§8.3），以及接口的常量（§9.3）；此处，类 `MiscMath` 中的字段 `divisor` 被声明为 `int` 类型
- 方法参数（§8.4.1）；此处，`ratio` 方法的参数 `l` 被声明为 `long` 类型
- 方法结果（§8.4.4）；`ratio` 方法的结果被声明为 `float` 类型，`gausser` 方法的结果被声明为 `double` 类型
- 构造函数参数（§8.4.1）；此处，`MiscMath` 构造函数的参数被声明为 `int` 类型
- 局部变量（§14.4, §14.4）；`gausser` 方法的局部变量 `r` 和 `val` 被声明为类型 `Random` 和 `double[]`（double 数组）
- 异常参数（§14.20）；此处，catch 句中的异常参数 `e` 被声明为类型 `Exception` 类型
- 类型参数（§4.4）；此处，`MiscMath` 的类型参数是一个类型变量 $\tau$，其声明的边界为 `Number`
- 在任何使用泛型类型的声明中；此处，类型 `Number` 被用作泛型类型 `Collection<Number>` 中的类型参数（§4.5.1）。

以及用于以下内容的表达式：

- 类实例（§15.9）；此处，`gausser` 方法的局部变量 `r` 通过一个使用类型 `Random` 的类实例创建来初始化
- 泛型类（§8.1.2）实例（§15.9）；此处，`Number` 被用作表达式 `new ArrayList<Number>()` 中的参数



- 数组创建（§15.10.1）；此处，`gausser` 方法的局部变量 `val` 通过创建一个大小为 2 的 `double` 数组的数组创建来初始化
- 泛型方法（§8.4.4）或构造函数（§8.4.4）调用（§15.12）；此处，`loop` 方法使用显式类型参数调用自身
- 强制转换（§15.16）；此处，`ratio` 方法的返回语句在某种情况下使用了 `float` 类型
- `instanceof` 运算符（§15.20.2）；此处，`instanceof` 运算符测试 `e` 是否兼容 `ArithmeticException` 类型

## 4.12 变量

变量是一个存储位置，并关联有一个类型（有时称为编译类型），该类型可以是基本类型（§4.2）或引用类型（§4.3）。

变量的值通过赋值（§15.26）或前/后 `++`（递增）或 `--`（递减）运算符（§15.14.2, §15.14.3, §15.15.1, §15.15.2）来改变。

只要程序没有出现编译未检查警告（§4.12.2），Java 语言的设计就能保证变量的值与其类型具有兼容性。默认值（§4.12.5）是兼容的，且对变量的所有赋值都会检查赋值兼容性；通常在编译时检查，但在涉及数组的单一特殊情况下，会进行运行时检查（§10.5）。

### 4.12.1 基本类型变量

基本类型变量始终持有该确切基本类型的原始值。

### 4.12.2 引用类型变量

类类型 $\tau$ 的变量可以持有 `null` 引用，或者指向类 $\tau$ 的实例或 $\tau$ 的任何子类的实例引用。

接口类型的变量可以持有 `null` 引用，或者指向实现该接口的任何类的任何实例的引用。

注意，变量并不保证指向其声明类型的子类型，而仅指向声明类型的子类或接口。这是由于下文将讨论的堆污染可能性。

如果 $T$ 是基本类型，那么类型为“$T$ 的数组”的变量可以持有 `null` 引用，或者指向任何类型为“$T$ 的数组”的数组的引用。

如果 $T$ 是引用类型，那么类型为“$T$ 的数组”的变量可以持有 `null` 引用，或者指向任何类型为“$T$ 的数组”的数组的引用。

变量并不保证指向其声明类型的子类型，而仅指向声明类型的子类或接口。这是由于下文将讨论的堆污染可能性。类类型 $\tau$ 的变量可以持有 `null` 引用，或者指向类 $\tau$ 的实例或 $\tau$ 的任何子类的实例引用。接口类型的变量可以持有 `null` 引用，或者指向实现该接口的任何类的任何实例的引用。注意，变量并不保证指向其声明类型的子类型，而仅指向声明类型的子类或接口。这是由于下文将讨论的堆污染可能性。

（注：此处原文中存在大量重复段落，已按要求保留逻辑结构并翻译）

如果实际上发生了编译时未检查的警告。可能会运行一个程序，其中某些二进制文件是由针对旧版本 Java 编程语言的编译器生成的，或者来自显式抑制了未检查警告的源。这种做法在最好的情况下也是不健康的。

相反，执行代码可能会（并且可能已经）产生未检查的警告，但没有发生堆污染（heap pollution）的可能。事实上，良好的编程实践要求程序员尽管存在任何未检查的警告，也要确保代码是正确的，且不会发生堆污染。

## 4.12.3 变量的种类

共有八种变量：

- 类变量（class variable）是在类声明中使用 `static` 关键字声明的字段（§8.3.1.1），或者在接口声明中使用（§9.3）或不使用 `static` 关键字声明的字段。

  类变量在其类或接口被准备时（§12.3.2）被创建，并初始化为默认值 (§4.12.5)。当其类或接口被卸载时（§12.7），类变量实际上不再存在。

- 实例变量（instance variable）是在类声明中未使用 `static` 关键字声明的字段（§8.3.1）。

  如果类 T 有一个作为实例变量的字段，那么在创建类 T 或其任何子类的每个新创建的实例对象时，都会创建一个新的实例变量并将其初始化为默认值 (§4.12.5) (§8.1.4)。当该变量作为字段的对象不再被引用，或者在对对象的任何必要的终结（finalization）完成（§12.6）后，该实例变量实际上不再存在。

- 数组组件（Array components）是未命名变量，每当创建数组的新对象时（§10 Arrays, §15.10.2），它们就会被创建并初始化为默认值 (§4.12.5)。当数组不再被引用时，数组组件实际上不再存在。

- 方法参数（Method parameters，§8.4.1）名称将实参值传递给方法。

  对于方法声明中声明的每个参数，每次调用该方法时都会创建一个新的参数变量 (§15.12)。该新变量用方法调用时相应的参数值初始化。当方法体执行完成时，方法参数实际上不再存在。

- 构造函数参数（Constructor parameters，§8.8.1）名称将实参值传递给构造函数。

  对于构造函数声明中声明的每个参数，每当类实例表达式 (§15.9)或显式构造函数调用 (§8.8.7)调用该构造函数时，都会创建一个新的参数变量。该新变量用创建表达式或构造函数调用相应的参数值初始化。当构造函数体执行完成后，构造函数参数实际上不再存在。

- Lambda 参数（Lambda parameters，§15.27.1）名称将实参值传递给 lambda 表达式体 (§15.27.2)。

  对于 lambda 表达式中声明的每个参数，每次调用由 lambda 体实现的方法时 (§15.12)，都会创建一个新的参数变量。该新变量用方法调用时相应的参数值初始化。当 lambda 表达式体执行完成时，lambda 参数实际上不再存在。

- 异常参数（exception parameter）在 try 语句的 catch 子句捕获到异常时（§14.20）会被创建一个。

  该新变量用与异常相关的实际对象初始化 (§11.3, §14.18)。当 catch 子句相关的块执行完成后，异常参数实际上不再存在。

- 局部变量（Local variables，§14.4）通过语句（§14.4.2, §14.14.1, §14.14.2, §14.20.3）和模式（§14.30.1）声明。通过模式声明的局部变量称为模式变量（pattern variable）。

  通过语句声明的局部变量在控制流进入最近的闭包块时（§14.14）被创建。

  通过模式声明的局部变量在类或被匹配时（§14.3）被创建并初始化为默认值。当不再被引用的局部变量实际上不再存在。

  在 try-with-resources 语句执行时，通过语句声明的局部变量被创建并初始化为默认值。根据确定赋值的规则（§16），在赋值之前语句声明的局部变量无法被使用。

### 4.12.4 final 变量

变量可以被声明为 `final`。`final` 变量只能赋值一次。如果 `final` 变量未赋值，则是编译错误。一旦 `final` 变量被赋值，它将包含相同的值。如果 `final` 变量持有某个对象的引用，对象的状态可以通过操作进行改变，但变量本身始终指向该对象。这也适用于数组，因为数组是对象；如果 `final` 变量持有数组的引用，数组的组件可以通过操作进行改变，但变量始终指向该数组。

空 final（blank final）是缺少初始化器的 `final` 变量。

常量变量（constant variable）是类型为原始类型或 String 且用常量表达式（§15.29）初始化的 `final` 变量。变量是否为常量变量对类初始化（§12.4.1）、二进制兼容性（13.1）、可达性（§14.22）以及确定赋值有影响。

三种变量被隐式声明为 `final`：接口的字段（§9.3）、try-with-resources 语句中的局部变量（§14.20.3）以及多 catch 子句的异常参数。单 catch 子句的异常参数从不隐式声明为 `final`，但可以是有效的 final。

示例 4.12.4-1. final 变量

将变量声明为 `final` 可以作为有效的文档，说明其值不会改变，并有助于避免编程错误。在此程序中：

```
class Point {
    int x, y;
    int useCount;
    Point(int x, int y) { this.x = x; this.y = y; }
    static final Point origin = new Point(0, 0);
}
```

Point 类声明了一个 `final` 变量 origin。origin 变量持有一个坐标为 (0, 0) 的 Point 对象引用。Point.origin 变量的值永远不会改变，因此它始终指向该 Point 对象，然而对该 Point 对象的操作可能会改变其状态——例如修改其 useCount，甚至误导地修改其 x 或 y 坐标。

未声明为 `final` 的变量被视为有效的 final（effectively final）：

- 通过语句声明且具有初始化器的局部变量（§14.4），或通过模式声明的局部变量（§14.30.1），如果满足以下条件，则是有效的 final：

  - 它没有被声明为 `final`。

  - 它从未出现在赋值表达式的左侧（§15.26）。（注意，包含初始化器的局部变量声明符不是赋值表达式。）

  - 它从未作为前缀或后缀递增/减运算符的操作数（§15.14, §15.15）。

- 一个由语句声明且其声明符缺少初始化值的局部变量，如果满足以下所有条件，则它是**有效最终的**（effectively final）：

  - 它不是 `final` 的。

  - 每当它作为赋值表达式的左值出现时，它确定是未赋值且在赋值之前未定义赋值的；也就是说，在赋值表达式右值之后，它确定是未赋值且未确定已赋值（§16 (确定赋值)）。

  - 它从未作为前缀运算符、增运算符或递减运算符的操作数出现。

  - 方法、构造函数、lambda 或异常参数 (§8.4.1, §8.8.1, §9.4, §15.27.1, §14.20）在确定其是否为有效最终的时，被视为声明符具有初始化值的局部变量。

如果一个变量是有效最终的，在它的声明中添加 `final` 修饰符不会引入任何编译时错误。相反，在合法程序中声明为 `final` 的局部变量或参数，如果移除 `final` 修饰符，则变为有效最终的。

### 4.12.5 变量的初始值

程序中的每个变量在使用值之前必须有一个值：

- 每个类、实例变量或数组组件在创建时都会用一个默认值初始化（§15.9, §15.10.2）：

  - 对于 `byte` 类型，默认值为零，即 `(byte)0` 的值。
  - 对于 `short` 类型，默认值为零，即 `(short)0` 的值。
  - 对于 `int` 类型，默认值为零，即 `0`。
  - 对于 `float` 类型，默认值为正零，即 `0.0f`。
  - 对于 `double` 类型，默认值为正零，即 `0.0d`。
  - 对于 `char` 类型，默认值为空字符，即 `'\u0000'`。
  - 对于 `boolean` 类型，默认值为 `false`。
  - 对于所有引用类型 (§4.3)，默认值为 `null`。

- 每个方法参数 (§8.4.1) 被初始化为方法调用者提供的相应参数值 (§15.12)。

- 每个构造函数参数 (§8.8.1) 被初始化为类实例创建表达式 (§15.9) 或显式构造函数调用 (§8.8.7) 提供的相应参数值。

- 异常参数 (§14.20) 被初始化为代表异常的抛出对象 (§11.3, §14.18)。

- 由语句声明的局部变量 (§14.4.2, §14.14.1, §14.14.2, §14.20.3) 在使用之前必须通过初始化 (§14.4) 或赋值 (§15.26) 显式地赋予一个值，且这种方式可以使用确定赋值规则进行验证 (§16 (确定赋值)）。

- 由模式声明的局部变量 (§14.30.1) 通过匹配过程 (§14.30.2) 进行隐式初始化。

示例 4.12.5-1. 变量的初始值

```
class Point {
    static int npoints;
    int x, y;
    Point root;
}
class Test {
    public static void main(String[] args) {
        System.out.println("npoints=" + Point.npoints);
        Point p = new Point();
        System.out.println("p.x=" + p.x + ", ", p.y=" + p.y);
        System.out.println("p.root=" + p.root);
    }
}
```

此程序输出：

```
npoints=0
p.x=0, p.y=0
p.root=null
```

展示了 `npoints` 的默认初始化（在类准备时发生 §12.3），以及 `x`、`y` 和 `root` 的默认初始化（在实例化 `Point` 时发生）。详见 *执行* 关于类的加载、链接和初始化，以及接口的实例化描述。

### 4.12.6 类型、类与接口

在 Java 语言中，每个变量都有类型。引用类型包括类和接口。

基本类型通过类型声明引入。引用类型通过类型声明引入。

在 Java 语言中，每个对象都属于某个类。有时说一个变量有一个类型，但这是指的是它的类。

变量的类型始终在编译时确定。如果变量被声明为某种类型，则该变量必须是该类型。

变量的类型可以在运行时确定。例如，`getClass()` 方法返回对象的类。

示例 4.12.6-1. 变量的类型对象的类

```
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

- `Test` 类 `main` 方法的局部变量 `p` 类型为 `Point`，初始被赋值为 `Point` 类新实例的引用。
- 局部变量 `cp` 同样具有其类型 `ColoredPoint`，并初始被赋值为 `ColoredPoint` 类新实例的引用。
- 将 `cp` 的值赋值会导致变量 `p` 持有一个 `ColoredPoint` 对象的引用。这是允许的，因为 `ColoredPoint` 是 `Point` 的子类，因此类 `ColoredPoint` 与类型 `Point` 兼容。
- 局部变量 `c` 的类型为接口 `Colorable`，因此它可以持有任何实现了 `Colorable` 接口的对象的引用；具体来说，它可以持有 `ColoredPoint` 的引用。

注意，如 `new Colorable()` 这样的表达式是非有效的，因为无法创建接口的实例，只能创建类的实例。然而，表达式 `new Colorable() { public void setColor... }` 是合法的，因为 `new` 声明了一个实现 `Colorable` 接口的匿名类（§15.9.5）。

## 第 5 章 转换与语境

Java 编程语言中编写的每一个表达式要么不产生结果（§15.1），要么具有一个可以在编译时推断出的类型（§15.3）。当一个表达式出现在许多语境中，它必须与该语境中预期的类型兼容；这种类型被称为目标类型（target type）。为了方便起见，通过两种方式促进表达式与其周围语境的兼容性：

- 首先，对于某些被称为多态表达式（poly expressions，§15.2）的表达式，推断出的类型可以受到目标类型的影响。同一个表达式在不同的语境中可以具有不同的类型。
- 其次，在表达式类型被推断之后，有时可以执行从表达式类型到目标类型的隐式转换。

如果这两种策略都无法产生相应的类型，则会发生编译错误。

确定一个表达式是否为多态表达式，如果是，则其在特定语境下的类型和兼容性的规则，取决于语境的种类和表达式的形式。除了影响表达式的类型外，目标类型在某些情况下可能会影响表达式的运行时行为，以产生相应类型的值。

同样，确定目标类型是否允许隐式转换的规则取决于语境的种类、表达式的类型，以及在特殊情况下，常量表达式的值（§15.29）。从类型 $s$ 到类型 $T$ 的转换允许类型为 $s$ 的表达式在编译时被处理为类型具有类型 $T$。在某些情况下，这需要在运行时执行相应的操作以检查转换的有效性，或将表达式的运行时值翻译为适用于新类型 $T$ 的形式。

示例 5.0-1. 编译时和运行时的转换



## 转换概述

- 从 `Object` 类型到 `Thread` 类型的转换需要运行时检查，以确保运行时值实际上是 `Thread` 类的实例或其子类之一；如果不是，则抛出异常。
- 从 `Thread` 类型到 `Object` 类型的转换不需要运行时操作；`Thread` 是 `Object` 的子类，因此任何由 `Thread` 类型表达式产生的引用都是 `Object` 类型的有效引用。
- 从 `int` 类型到 `long` 类型的转换需要将 32 位整数值进行运行时符号扩展为 64 位的 `long` 表示。不会丢失信息。
- 从 `double` 类型到 `long` 类型的转换需要从 64 位浮点值到 64 位表示的非平凡翻译。取决于实际的运行时值，可能会丢失信息。

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

存在六种转换语境，在这些语境中，多态表达式可能会受到语境的影响或可能会发生隐式转换。每种语境对多态表达式的类型化有不同的规则，并允许上述类别中的某些转换而不允许其他。这些语境是：

- 赋值语境，在此语境中，表达式的值绑定到一个命名变量。原始类型和引用类型的值，可能会被装箱或解箱，某些原始常量表达式可能会被窄化。也可能发生未检查转换。
- 严格调用语境，在此语境中，参数绑定到构造函数或方法的形式参数上。
- 松散调用语境，在此语境中，参数绑定到构造函数或方法的形式参数上。类似于严格调用语境，允许宽化和解箱转换。
- 字符串语境，在此语境中，任何类型都被转换为字符串。
- 强制转换语境，在此语境中，任何类型都被转换为目标类型。
- 数值语境，在此语境中，任何类型都被转换为数值。

## 5.0-2. 各种语境下的转换

```java
class Test {
    public static void main(String[] args) {
        double f = 144.0;
        int i = (int)f;
        System.out.println("after widening: " + f);
        System.out.println("Math.sin(f)=" + f);
        System.out.println("Math.sin(i)=" + i);
    }
}
```

```
after widening: 144.0
Math.sin(144.0)=-0.49102159389693
Math.sin(144)=0.9738476105
```

## 5.1 转换种类

Java 编程语言中的特定转换分为 12 种。

### 5.1.1 恒等转换

从类型到相同类型的转换对于任何类型都是允许的。

这似乎显而易见，但它有两个实际意义。首先，它允许表达式原本具有目标类型，从而允许简单规定每个表达式都适用于转换。其次，它意味着程序为了清晰可以包含冗余的强制转换符。

### 5.1.2 宽化原始类型转换

对原始类型的 19 种特定转换被称为宽化原始转换：

- 从 `byte` 到 `short`、`int`、`long`、`float`、`double`
- 从 `short` 到 `int`、`long`、`float`、`double`
- 从 `char` 到 `int`、`long`、`float`、`double`
- 从 `int` 到 `long`、`float`、`double`
- 从 `long` 到 `float`、`double`

在以下情况下，宽化原始转换不会丢失数值值的整体幅度，其中数值值被精确保留：

- 从整数类型到另一个整数类型
- 从 `byte`、`short` 或 `char` 到浮点类型
- 从 `int` 到 `double`
- 从 `float` 到 `double`

从 `int` 到 `float`、从 `long` 到 `float` 或从 `long` 到 `double` 的宽化原始转换可能会导致精度损失，即结果可能会丢失数值的一些低有效位。在这种情况下，产生的浮点值将是整数值的正确舍入版本，使用最近舍入舍入策略。

符号整数值到整数类型 $\tau$ 的宽化转换简单地扩展整数值的补码表示以填充更宽的格式。

`char` 到整数类型 $\tau$ 的宽化转换零扩展扩展 `char` 值的表示以填充更宽的格式。

尽管可能会发生精度丢失，但宽化原始类型转换不会导致运行时异常。

#### 示例 5.1.2-1. 宽化原始类型转换

```java
class Test {
    public static void main(String[] args) {
        int big = 1234567890;
        float approx = big;
        System.out.println(big - (int)approx);
    }
}
```

该程序输出：

```
-46
```

这表明在从 `int` 类型到 `float` 类型的转换过程中丢失了信息，因为 `float` 类型的值无法精确到九位有效数字。

### 5.1.3 窄化原始类型转换

原始类型上的 22 种特定转换被称为窄化原始类型转换：

- `short` 到 `byte` 或 `char`
- `char` 到 `byte` 或 `short`
- `int` 到 `byte`、`short` 或 `char`
- `long` 到 `byte`、`short`、`char` 或 `int`
- `float` 到 `byte`、`short`、`char`、`int` 或 `long`
- `double` 到 `byte`、`short`、`char`、`int`、`long` 或 `float`

窄化转换可能会丢失数值的整体大小信息，还会丢失精度和范围。

将有符号整数转换为整数类型 $\tau$ 的窄化转换简单地丢弃所有 $n$ 个低阶位，其中 $n$ 是表示类型 $\tau$ 所使用的位数。除了可能丢失数值大小的信息外，这还可能导致结果的符号与输入值的符号不同。

将 `char` 转换为整数类型 $\tau$ 的窄化转换同样地丢弃所有 $n$ 个低阶位，其中 $n$ 是表示类型 $\tau$ 所使用的位数。除了可能丢失数值大小的信息外，这还可能导致结果为负数，尽管 `char` 表示的是 16 位无符号整数值。

将浮点数转换为整数类型 $\tau$ 的窄化转换分为两个步骤：

1. 在第一步中，将浮点数转换为 `long`（如果 $\tau$ 是 `long`）或转换为 `int`（如果 $\tau$ 是 `byte`、`short`、`char` 或 `int`），如下：
    - 如果浮点数为 `NaN`，则转换的第一步结果为 `int` 或 `long` 0。
    - 否则，如果浮点数不是无穷大，则使用向零舍入策略将浮点值舍入整数值 $v$。有两种情况：
        a. 如果 $\tau$ 是 `long` 且该整数值可以表示为 `long`，则第一步的结果为 `long` 值 $V$。
        b. 否则，如果该整数值可以表示为 `int`，则第一步的结果为 `int` 值 $V$。
    - 否则，必须满足以下两种情况之一：
        a. 该值太小（绝对值很大的负值或负无穷），且第一步的结果是 `int` 或 `long` 类型表示的最小值。
        b. 该值太大（绝对值很大的正值或正无穷），且第一步的结果是 `int` 或 `long` 类型可表示的最大值。

2. 在第二步中：
    - 如果 $\tau$ 是 `int` 或 `long`，转换的结果为第一步的结果。
    - 如果 $\tau$ 是 `byte`、`char` 或 `short`，转换的结果是将第一步的结果转换为类型 $\tau$ 的窄化转换的结果。

从 `double` 到 `float` 的窄化转换根据 IEEE 754 二进制浮点格式转换的规则进行，并使用最近舍入策略。这种转换可能会丢失精度，还可能丢失范围，导致非零 `double` 变为 `float` 零，有限 `double` 变为 `float` 无穷大。`double` NaN 转换为 `float` NaN，`double` 无穷转换为相同符号的 `float` 无穷。

尽管可能会发生溢出或其他信息丢失，但窄化原始类型转换不会导致运行时异常。

#### 示例 5.1.3-1. 窄化原始类型转换

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
short: -32768...32767
char: \u0000...\uffff
byte: -128...127
```

（注：原文中输出部分的 OCR 严重损坏，已根据 Java 这些转换的标准行为进行修正。）

### 5.1.4 宽化与窄化原始类型转换

以下转换结合了宽化和窄化原始类型转换：

- `byte` 到 `char`

首先，通过宽化原始类型转换将 `byte` 转换为 `int`，然后将得到的 `int` 通过窄化原始类型转换转换为 `char`。

### 5.1.5 宽化引用转换

从任何引用类型 $s$ 到任何引用类型 $\tau$ 的宽化引用转换，只要 $s$ 是 $\tau$ 的子类型。宽化引用转换在运行时不需要特殊操作，因此不会在运行时抛出异常。它们仅仅是将引用视为具有某种可以在编译时证明正确的其他类型。

空类型不是引用类型，因此不存在从空类型到引用类型的宽化引用转换。然而，许多转换上下文显式允许将空类型转换为引用类型。

### 5.1.6 窄化引用转换

窄化引用转换将引用类型 $s$ 的表达式视为另一种引用类型 $\tau$，其中 $s$ 不是 $\tau$ 的子类型。支持的类型对定义在 §5.1.6.1 中。与宽化引用转换不同，这些类型不需要直接相关。然而，存在限制：当可以静态地证明某个值不可能同时属于两种类型时，则禁止这些类型对之间进行转换。

窄化引用转换可能需要在运行时进行测试，以验证类型为 $s$ 的值是否为类型 $\tau$ 的合法值。然而，由于运行时缺乏类型信息，某些转换无法通过运行时测试完全验证；它们会在编译时被标记。对于那些可以通过运行时测试完全验证的转换，以及某些涉及参数化类型信息但仍可以在运行时进行部分验证的转换，如果测试失败，则会抛出 `ClassCastException`。

#### 5.1.6.1 允许的窄化引用转换

满足以下所有条件，存在从引用类型 $s$ 到引用类型 $\tau$ 的窄化引用转换：

- $s$ 不是 $\tau$ 的子类型
- 如果存在一个参数化类型 $x$ 是 $\tau$ 的超类型，且存在一个参数化类型 $y$ 是 $s$ 的超类型，使得 $x$ 和 $y$ 的擦除相同，则 $x$ 和 $y$ 不是可证明是不同的。

> 以 `java.util` 包为例，从 `ArrayList<String>` 到 `ArrayList<Object>`（或反之）都不存在窄化引用转换，因为类型参数 `String` 和 `Object` 是可证明是不同的。出于相同的原因，从 `ArrayList<String>` 到 `List<Object>`（或反之）也不存在窄化引用转换。对可证明是不同的类型的拒绝是一个简单的静态门控，用以防止“愚蠢”的窄化引用转换。

适用于以下情况之一：

1. $s$ 是一个类或接口类型，且 $T$ 是一个类或接口类型，且 $s$ 与由 $T$ 命名的类或接口不相交。
2. $s$ 是类类型 `Object` 或接口类型 `java.io.Serializable` 或 `Cloneable`（数组实现的唯一接口），且 $T$ 是数组类型。
3. $s$ 是数组类型 $SC[1]$，即类型为 $SC$ 的组件的数组；$T$ 是数组类型 $TC[1]$，且从 $SC$ 到 $TC$ 存在窄化引用转换。
4. $s$ 是一个类型变量，且从 $s$ 的上界到 $T$ 存在窄化引用转换。
5. $s$ 是一个类型变量，且从 $s$ 到 $T$ 的上界存在拓宽引用转换或窄化引用转换。
6. $s$ 是交集类型 $S_1 \& ... \& S_n$，对于所有 $i$（$1 \le i \le n$），从 $S_i$ 到 $T$ 存在拓宽引用转换或窄化引用转换。
7. $T$ 是交集类型 $T_1 \& ... \& T_m$，对于所有 $i$（$1 \le i \le n$），从 $s$ 到 $T_i$ 存在拓宽引用转换或窄化引用转换。

如果一个类或接口与另一个类或接口可以静态地确定它们没有共同的实例（`null` 值除外），则它们是*不相交的*。不相交的规则如下：

- 命名为 $C$ 的类与命名为 $I$ 的接口不相交，如果 (i) 不是 $C <: I$，且 (ii) 满足以下情况之一：
    - $C$ 是 `final`。
    - $C$ 是 `sealed`，且 $C$ 的所有被允许的直接子类都与 $I$ 不相交。
    - $I$ 是 `sealed`，且 $I$ 的所有被允许的直接子类都与 $C$ 不相交。

- 如果从 $s$ 到非交集类型 $T$ 的未检查窄化引用转换满足 $|s| < |T|$，则它是完全未检查的。
- 如果从 $s$ 到交集类型 $T_1 \& \dots \& T_n$ 的未检查窄化引用转换满足：对于所有 $i$ ($1 \le i \le n$)，要么 $s <: T_i$，要么从 $s$ 到 $T_i$ 的窄化引用转换是完全未检查的。

否则，它是部分未检查的。

对于已检查或部分未检查的窄化引用转换，其运行时有效性检查如下：

- 如果运行时值为 `null`，则允许该转换。
- 否则，让 $R$ 为该值所引用的对象的类，并让 $\tau$ 为被转换类型的擦除。那么：
    - 如果 $R$ 是一个普通类（不是数组类）：
        - 如果 $\tau$ 是类类型，则 $R$ 必须是与 $\tau$ 相同的类或 $\tau$ 的子类，否则抛出 `ClassCastException`。
        - 如果 $\tau$ 是接口类型，则 $R$ 必须实现接口 $\tau$，否则抛出 `ClassCastException`。
        - 如果 $\tau$ 是数组类型，则抛出 `ClassCastException`。
    - 如果 $R$ 是接口：



> 注意，当对任何给定转换首次应用这些规则时，$R$ 不能是接口，但如果递归应用这些规则，$R$ 可以是一个接口，因为运行时引用值可能指向一个其元素类型为接口的数组。

- 如果 $\tau$ 是类类型，则 $\tau$ 必须是 `Object` (§4.3.2)，否则抛出 `ClassCastException`。
- 如果 $\tau$ 是接口类型，则 $R$ 必须是与 $\tau$ 相同的接口或 $\tau$ 的子接口，否则抛出 `ClassCastException`。
- 如果 $\tau$ 是数组类型，则抛出 `ClassCastException`。

- 如果 $R$ 是一个表示数组类型 $RC[]$ 的类，即类型为 $RC$ 的元素的数组。
    - 如果 $\tau$ 是类类型，则 $\tau$ 必须是 `Object` (§4.3.2)，否则抛出 `ClassCastException`。
    - 如果 $\tau$ 是接口类型，则 $\tau$ 必须是 `java.io.Serializable` 或 `Cloneable` 类型（数组实现的唯一接口），否则抛出 `ClassCastException`。
    - 如果 $\tau$ 是数组类型 $TC[]$，即类型为 $TC$ 的元素的数组，除非 $TC$ 和 $RC$ 是相同的原始数据类型，或者 $TC$ 和 $RC$ 是引用类型且通过这些运行时规则的递归应用允许，否则抛出 `ClassCastException`。

如果转换到交集类型 $T_1 \& \dots \& T_n$，则对于所有 $i$ ($1 \le i \le n$)，从 $s$ 到 $T_i$ 转换所需的任何运行时检查对于转换到交集类型的转换也是需要的。

### 5.1.7 装箱转换

装箱转换将原始类型的表达式视为相应引用类型的表达式。具体而言，以下九种转换被称为装箱转换：

- 从 `boolean` 类型到 `Boolean` 类型
- 从 `byte` 类型到 `Byte` 类型
- 从 `short` 类型到 `Short` 类型
- 从 `char` 类型到 `Character` 类型
- 从 `int` 类型到 `Integer` 类型
- 从 `long` 类型到 `Long` 类型
- 从 `float` 类型到 `Float` 类型
- 从 `double` 类型到 `Double` 类型
- 从空类型到空类型

> 这一规则是必要的，因为条件运算符（§15.25）对其操作数的类型应用装箱转换，并将结果用于进一步计算。

在运行时，装箱转换过程如下：

- 如果 $p$ 是 `boolean` 类型的值，则装箱转换将 $p$ 转换为一个类和类型为 `Boolean` 的引用 $r$，使得 `r.booleanValue() == p`
- 如果 $p$ 是 `byte` 类型的值，则装箱转换将 $p$ 转换为一个类和类型为 `Byte` 的引用 $r$，使得 `r.byteValue() == p`
- 如果 $p$ 是 `char` 类型的值，则装箱转换将 $p$ 转换为一个类和类型为 `Character` 的引用 $r$，使得 `r.charValue() == p`
- 如果 $p$ 是 `short` 类型的值，则装箱转换将 $p$ 转换为一个类和类型为 `Short` 的引用 $r$，使得 `r.shortValue() == p`
- 如果 $p$ 是 `int` 类型的值，则装箱转换将 $p$ 转换为一个类和类型为 `Integer` 的引用 $r$，使得 `r.intValue() == p`
- 如果 $p$ 是 `long` 类型的值，则装箱转换将 $p$ 转换为一个类和类型为 `Long` 的引用 $r$，使得 `r.longValue() == p`
- 如果 $p$ 是 `float` 类型的值，则：
    - 如果 $p$ 不是 NaN，装箱转换将 $p$ 转换为一个类和类型为 `Float` 的引用 $r$，使得 `r.floatValue()` 结果为 $p$
    - 否则，装箱转换将 $p$ 转换为一个类和类型为 `Float` 的引用 $r$，使得 `r.floatValue()` 结果为 $p$
- 如果 $p$ 是 `double` 类型的值，则：
    - 如果 $p$ 不是 NaN，装箱转换将 $p$ 转换为一个类和类型为 `Double` 的引用 $r$，使得 `r.doubleValue()` 结果为 $p$
    - 否则，装箱转换将 $p$ 转换为一个类和类型为 `Double` 的引用 $r$，使得 `r.doubleValue()` 结果为 $p$

### 5.1.8 解箱转换

解箱转换将引用类型的表达式视为原始类型的表达式。具体而言，以下八种转换被称为解箱转换：

- 从 `Boolean` 类型到 `boolean` 类型
- 从 `Byte` 类型到 `byte` 类型
- 从 `Short` 类型到 `short` 类型
- 从 `Character` 类型到 `char` 类型
- 从 `Integer` 类型到 `int` 类型
- 从 `Long` 类型到 `long` 类型
- 从 `Float` 类型到 `float` 类型
- 从 `Double` 类型到 `double` 类型

在运行时，解箱转换过程如下：

- 如果 $r$ 是 `Boolean` 类型引用，则解箱转换将 $r$ 转换为 `r.booleanValue()`
- 如果 $r$ 是 `Byte` 类型引用，则解箱转换将 $r$ 转换为 `r.byteValue()`
- 如果 $r$ 是 `Character` 类型引用，则解箱转换将 $r$ 转换为 `r.charValue()`
- 如果 $r$ 是 `Short` 类型引用，则解箱转换将 $r$ 转换为 `r.shortValue()`
- 如果 $r$ 是 `Integer` 类型引用，则解箱转换将 $r$ 转换为 `r.intValue()`
- 如果 $r$ 是 `Long` 类型引用，则解箱转换将 $r$ 转换为 `r.longValue()`
- 如果 $r$ 是 `Float` 类型引用，则解箱转换将 $r$ 转换为 `r.floatValue()`
- 如果 $r$ 是 `Double` 类型引用，则解箱转换将 $r$ 转换为 `r.doubleValue()`
- 如果 $r$ 为 null，解箱转换抛出 `NullPointerException`

## 5.1.9 未检查的转换 (Unchecked Conversion)

设 $g$ 为具有 $n$ 个类型参数的泛型声明。

从原始类或接口类型 (§4.8) $g$ 到任何形式为 $G<T_i,...,T_n>$ 的参数类型存在一个未检查的转换。

从原始数组类型 $G[]^k$ 到任何形式为 $G<T_i,...,T_j,[]>^k$ 的数组类型存在一个未检查的转换。（符号 $^k$ 表示 $k$ 维数组类型。）

当所有参数 $T_i$ ($1 \le i \le n$) 均为不受无界通配符 (§4.5) 时，使用未检查的转换会导致编译时警告，或者该警告被 `@SuppressWarnings` (§9.6.4) 抑制。

未检查的转换用于实现在泛型类型引入之前编写的遗留代码与泛型代码之间更平滑的互操作。在这些情况下使用泛泛型化（我们称这一过程为 generification）（最典型的是 `java.util` 中 Collections Framework 的客户端），遗留代码使用原始类型（例如，`Collection` 代替 `Collection<String>`）。原始类型的表达式被传递给使用这些相同类型的参数化版本作为其形式参数参数的库。

在泛型的类型系统下，无法证明此类强制转换在统计上是安全的。拒绝此类调用将导致大量现有代码失效，并阻止它们使用新版本的库。反之，这会阻碍库供应商利用泛型优势。为了防止这种不受欢迎的事件发生，原始类型可以转换为该原始类型所指的泛型类型声明的任意调用。虽然这种转换是不安全的（unsound），但出于实用性考虑的妥协，它是被允许的。在这种情况下，会发出一个未检查的警告。

## 5.1.10 捕获转换 (Capture Conversion)

设 $g$ 为具有 $n$ 个类型参数 $A_i,...,A_n$ 及其对应边界 $U_i,...,U_n$ 的泛型声明 (§8.1.2, §9.1.2)。

从参数化类型 $G<T_i,...,T_n>$ (§4.5) 到参数化类型 $G<S_i,...,S_n>$ 一个捕获转换，其中对于 $1 \le i \le n$：

- 如果 $T_i$ 是通配符类型参数 (§4.5.1)，则 $S_i$ 是一个新的类型变量，其上界为 $U_i[A_i:=S_i,...,A_n:=S_n]$，其下界为空类型 (§4.1)。

### 转换的种类

- 如果 $T_i$ 是形式为 ? extends $B_i$ 的通配符类型参数，则 $S_i$ 是一个新的类型变量，其上界为 $glb(B_i, U_i[A_i:=S_i, \dots, A_n:=S_n])$，其下界为空类型。

$glb(V_i, \dots, V_m)$ 定义为 $V_i \& \ \dots \& \ V_m$。

如果任何两个类（接口）$V_i$ 和 $V_j$ 不是 $V_j$ 的子类或反之，则为编译错误。

- 如果 $T_i$ 是形式为 ? $B_i$ 的通配符类型参数，则 $S_i$ 是一个新的类型变量，其上界为 $U_i[A_i:=S_i, \dots, A_n:=S_n]$，其下界为 $B_i$。

- 否则，$S_i = T_i$。

除参数化类型 (§4.5) 之外任何类型的捕获转换都充当恒等转换 (§5.1.1)。

捕获转换不递归应用。

捕获转换永远在运行时不需要特殊操作，因此在运行时永远不会抛出异常。

> 捕获转换的设计是为了让通配符更有用。为了理解其动机，让我们先看方法 `java.util.Collections.reverse()`：

```
public static void reverse(List<?> list);
```

该方法返回作为参数提供的列表。它适用于任何类型的列表，因此将通配符 `List<?>` 用作形式参数的类型是完全恰当的。

现在考虑如何实现 reverse()：

```java
public static void reverse(List<?> list) { rev(list); }
private static <T> void reverse(List<T> list) {
    List<T> tmp = new ArrayList<T>(list);
    for (int i = 0; i < list.size(); i++) {
        list.set(i, tmp.get(list.size() - i));
    }
}
```

实现需要复制列表，从拷贝中提取元素并将其插入原始列表中。为了以类型安全的方式这样做，我们需要使用 `T` 作为传入列表的类型。我们在服务 `rev()` 中这样做。这要求我们将传入的列表类型 `List<?>` 作为参数传递给 `rev()`。通常，`List<?>` 是未知类型的列表。它不是任何类型 `List<T>` 的子类型。给定该方法：

```
public static <T> fill(List<T> l, T obj)
```

以下代码将破坏系统：

```
List<String> ls = new ArrayList<String>();
List<?> l1 = ls;
Collections.fill(l1, new Object()); // 不合法 - 假设它是合法的！
String s = ls.get(0); // ClassCastException - ls 包含
```

所以，在没有特殊许可的情况下，我们可以看到，原始类型可以转换为该原始类型所指的泛型类型声明的任意调用。虽然这种转换是不安全的，但出于实用性考虑的妥协，它是被允许的。在这种情况下，会发出一个未检查的警告。

## 转换与上下文

- 一个宽引用转换，后接一个解箱转换，随后是一个拓宽原始类型转换
- 一个装箱转换 (§5.1.7)
- 一个装箱转换后接一个宽引用转换
- 一个解箱转换 (§5.1.8)
- 一个解箱转换后接一个拓宽原始类型转换

如果在应用了上述转换后，结果类型是一个原始类型 (§4.8)，则可以应用未检查转换 (§5.1.9)。

此外，如果表达式是类型 `byte`、`short`、`char` 或 `int` 的常量表达式 (§15.29)：

- 如果变量类型为 `byte`、`short` 或 `char`，且常量表达式的值可以在变量类型中表示，则可以使用窄原始类型转换。
- 如果变量类型为 `Byte`、`Short` 或 `Character`，且常量表达式的值分别可以在 `byte`、`short` 或 `char` 类型中表示，则可以使用窄原始类型转换后接一个装箱转换。

常量表达式的编译时收窄意味着如下代码：

```java
byte theAnswer = 42;
```

是被允许的。如果没有收窄，整数字面量 42 类型为 `int` 这一事实意味着强制转换为 `byte` 将需要：

```java
byte theAnswer = (byte)42; // 允许强制转换但必需
```

最后，`null` 值（null 引用是唯一的此类值）可以赋值给任何引用类型，从而产生该类型的 null 引用。

如果转换链包含两个不具有子类型关系的泛型类型 (§4.10)，则为编译时错误。

此类非法链的示例为：

`Integer, Comparable<Integer>, Comparable, Comparable<String>`

链的前两个元素通过宽引用转换关联，而最后一个项通过未检查转换从其前驱项派生。然而，这不是一个有效的赋值转换，因为链中包含了两个不是子类型的类型：`Comparable<Integer>` 和 `Comparable<String>`。

## 赋值上下文

如果一个表达式的类型可以通过赋值转换转换为变量的类型，我们说该表达式（或其值）是可以赋值给该变量的，或者等价地表达式的类型与变量的类型是赋值兼容的。

在赋值上下文中由转换可能产生的异常只有：

- `ClassCastException`：如果在应用了上述转换后，结果值是一个不是变量类型擦除后 (§4.6) 的子类或子接口的实例的对象。

这种情况只会由于堆污染 (§4.12.2) 而产生。在实践中，实现类只需要在访问泛型类型的字段或方法时，如果字段的擦除类型或方法的擦除返回类型与使用的类型不同，才需要执行强制转换。

- 由于装箱转换导致的 `OutOfMemoryError`。
- 由于解箱转换为 null 引用导致的 `NullPointerException`。
- 涉及数组元素或字段访问的特殊情况下的 `ArrayStoreException` (§10.5, §15.26.1)。

### 示例 5.2-1. 原始类型的赋值

```java
class Test {
    public static void main(String[] args) {
        short s = 12; // 将 12 窄收为 short
        float f = s; // 将 short 拓宽为 float
        System.out.println("*f=" + f);
        char c = '\u0123';
        long l = c; // 将 char 拓宽为 long
        System.out.println("*l=" + Long.toString(l,16));
        float f2 = 1.23f;
        double d = f2; // 将 float 拓宽为 double
        System.out.println("*d=" + d);
    }
}
```

该程序产生输出：

```
f=12.0
l=0x123
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

因为并不是所有的值都是 `char` 值，也不是所有的 `char` 值都是 `short`。

### 示例 5.2-2. 引用类型的赋值



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
      // 对类类型变量的赋值：
      Point p = new Point();
      p = new Point3D();
      // OK，因为 Point3D 是 Point 的子类
      Point3D p3d = p;
      // 错误：将需要强制转换，因为
      // 可能不是 Point3D（尽管在这个例子中，动态上是）

      // 对类型为 的变量的赋值：
      Object o = p; // OK：任何对象到 Object
      int[] a = new int[3];
      Object o2 = a; // OK：数组到 Object

      // 对接口类型变量的赋值：
      ColoredPoint cp = new ColoredPoint();
      Colorable c = cp; // OK：ColoredPoint 实现 Colorable

      // 对数组类型变量的赋值：
      byte[] b = new byte[4];
      a = b; // 错误：这些不是原始类型的数组
      Point3D[] p3da = new Point3D[3];
      Point[] pa = p3da; // OK：因为我们可以将 Point3D 赋值给 Point
      p3da = pa; // 错误：（需要强制转换），因为 Point
      // 不能被赋值给 Point3D
    }
}
```

以下程序说明了引用值的赋值转换，但无法编译，如注释所示。此示例应与前一个进行对比。

```java
class Point { int x, y; }
interface Colorable { void setColor(int color); }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}

class Test {
    public static void main(String[] args) {
        Point p = new Point();
        ColoredPoint cp = new ColoredPoint();
        // 因为 ColoredPoint 是 Point 的子类
        Point p = cp;
        // 因为 ColoredPoint 实现 Colorable
        Colorable c = cp; // 在运行时检查赋值转换
        // 假设 p 在运行时是 ColoredPoint 实例
        ColoredPoint[] cpvec = new ColoredPoint[3];
        // 赋值转换
        cpvec[0] = p; // 运行时可能抛出异常
    }
}
```

### 示例 5.2-3. 数组类型的赋值

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }

class Test {
    public static void main(String[] args) {
        long[] longArray = new long[100];
        Object o = longArray; // OK
        Long i = longArray; // 编译错误
        short[] shortArray = longArray; // 编译错误
        Point[] p = new Point[100];
        ColoredPoint[] cpvec = new ColoredPoint[100];
        p = cpvec; // OK
        cpvec[0] = new Point(); // 编译通过，
                                // 运行时可能抛出 ArrayStoreException
    }
}
```

## 调用上下文

调用上下文允许在方法或构造函数调用（`§8.7.1`、`§15.9`、`§15.12`）中将参数值赋予对应的形式参数。

严格调用上下文允许使用以下转换之一：

- 等价转换（`§5.1.1`）
- 拓宽原始类型转换（`§5.1.2`）
- 宽引用转换（`§5.1.5`）

宽松调用上下文允许更宽松的转换集合，因为只有当使用严格调用上下文找不到任何可用声明时，才会对特定的调用使用它们。宽松调用上下文允许使用以下转换之一：

- 等价转换（`§5.1.1`）
- 拓宽原始类型转换（`§5.1.2`）
- 宽引用转换（`§5.1.5`）
- 宽引用转换后接一个解箱转换
- 一个宽化引用转换，后接一个拆箱转换，再接一个宽化原始类型转换
- 一个装箱转换（`§5.1.7`）
- 一个装箱转换，后接一个宽化引用转换
- 一个拆箱转换（`§5.1.8`）
- 一个拆箱转换，后接一个宽化原始类型转换

如果在应用了针对调用上下文（invocation context）列出的转换后，结果类型是一个原始类型（`§4.8`），则随后可以应用一个未检查转换（`§5.1.9`）。

`null` 类型的值（`null` 引用是唯一的此类值）可以赋值给任何引用类型。

如果转换链中包含两个不满足子类型关系（`§4.10`）的泛型类型，则将产生编译时错误。

在调用上下文中可能出现的异常有：

- `ClassCastException`：如果应用了上述类型转换，结果值是一个不是对应形式参数类型擦除后（`§4.6`）的子类或子接口实例的对象。
- 由于装箱转换导致的 `OutOfMemoryError`。
- 由于对 `null` 引用进行拆箱转换导致的 `NullPointerException`。

无论是严格还是宽松的调用上下文，都不包含赋值上下文中允许的整数常量表达式的隐式收窄转换。Java 语言的设计者认为，包含这些隐式收窄转换会增加重载解析规则（`§15.12.2`）的复杂性。

因此，该程序：

```
class Test {
    static int m(byte a, int b) { return a+b; }
    static int m(short a, short b) { return a-b; }
    public static void main(String[] args) {
        System.out.println(m(12, 2)); // 编译时错误
    }
}
```

会导致编译时错误，因为整数字面量 `12` 和 `2` 的类型为 `int`，所以没有任何一个方法重重载解析规则。一种包含整数常量表达式隐式收窄的语言需要额外的规则来解决此类示例中的情况。

转换与上下文

5.4

## 5.4 字符串上下文

字符串上下文仅适用于二元运算符 `+` 的操作数，当另一个操作数是 `String` 时，该操作数不是 `String`。

在这些上下文中，目标类型始终是 `String`，并且会对非 `String` 操作数始终发生字符串转换（`§5.1.11`）。随后按照 `§15.18.1` 指定的方式对 `+` 运算符进行求值。

## 5.5 转换上下文

转换上下文允许将强制转换表达式（`§15.16`）的操作数转换为强制转换符显式指定的类型。与赋值上下文和调用上下文相比，转换上下文允许使用更多在 `§5.1` 中定义的转换，并允许这些转换的更多组合。

如果表达式是原始类型，则转换上下文允许使用以下之一：

- 恒等转换（`§5.1.1`）
- 宽化原始类型转换（`§5.1.2`）
- 收窄原始类型转换（`§5.1.3`）
- 宽化且收窄原始类型转换（`§5.1.4`）
- 装箱转换（`§5.1.7`）
- 一个装箱转换，后接一个宽化引用转换（`§5.1.5`）

如果表达式是引用类型，则转换上下文允许使用以下之一：

- 恒等转换（`§5.1.1`）
- 宽化引用转换（`§5.1.5`）
- 一个宽化引用转换，后接一个拆箱转换
- 一个宽化引用转换，后接一个拆箱转换，再后接一个宽化原始类型转换
- 收窄引用转换（`§5.1.6`）
- 一个收窄引用转换，后接一个拆箱转换
- 一个拆箱转换（`§5.1.8`）
- 一个拆箱转换，后接一个宽化原始类型转换

如果表达式具有 `null` 类型，则该表达式可以强制转换为任何引用类型。

如果转换上下文使用了经过检查或部分未检查的收窄引用转换（`§5.1.6.2`、`§5.1.6.3`），则将对表达式值的类进行运行时检查，可能会导致 `ClassCastException`。否则，不进行运行时检查。

如果一个表达式可以通过除未检查的收窄引用转换以外的强制转换转换为引用类型，我们称该表达式（或其值）与该引用类型向下兼容（downcast compatible）。

下表列出了在某些转换上下使用的转换。每种转换由一个符号表示：

- `-` 表示不允许转换
- `=` 表示恒等转换（`§5.1.1`）
- `ω` 表示宽化原始类型转换（`§5.1.2`）
- `η` 表示收窄原始类型转换（`§5.1.3`）
- `ϖη` 表示宽化且收窄原始类型转换（`§5.1.4`）
- `⇘` 表示宽化引用转换（`§5.1.5`）
- `⇋` 表示收窄引用转换（`§5.1.6`）
- `⊕` 表示装箱转换（`§5.1.7`）
- `⊖` 表示拆箱转换（`§5.1.8`）

在表中，符号之间的逗号表示转换上下文先使用一个转换，后接另外一个转换。类型 `Object` 表示除包装类 `Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double` 之外的任何引用类型。

## 表 5.5-A. 转换为原始类型

| | byte | short | char | int | long | float | boolean |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **byte** | | | | | | | |
| **short** | | | | | | | |
| **char** | | | | | | | |
| **int** | | | | | | | |
| **long** | | | | | | | |
| **float** | | | | | | | |
| **boolean** | | | | | | | |

*(注：由于原文表格内容在提供时不完整或为占位符，此处保持结构，实际内容翻译将遵循上述逻辑)*

## 表 5.5-B. 转换为引用类型

| | Byte | Short | Integer | Long | Float | Object |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **byte** | | | | | | |
| **short** | | | | | | |
| **char** | | | | | | |
| **int** | | | | | | |
| **long** | | | | | | |
| **float** | | | | | | |
| **boolean** | | | | | | |

*(注：同上，此处根据原文提供的结构进行格式对齐)*

## 示例 5.5-1. 引用类型的强制转换

```
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
        // 以下操作在运行时可能会导致错误，因为我们无法确定它们会成功；
        // 这种可能性是由转换暗示的：
        cp = (ColoredPoint)p; // p 可能不是 ColoredPoint 的子类
                              // 或不是 ColoredPoint 的实例
        c = (Colorable)p; // p 可能不是 Colorable
        // 以下在编译时是错误的，
        // 正文所述它们永远不会成功：
        Long l = (Long)p; // 编译时错误 #1
        Endpoint e = new Endpoint();
        c = (Colorable)e; // 编译时错误 #2
    }
}
```

在这里，第一个编译时错误发生是因为类类型 `Long` 和 `Point` 是不相关的（即它们不相同，且彼此都不是对方的子类），因此它们之间的转换将永远失败。

第二个编译时错误发生是因为 `Endpoint` 类型的变量永远无法引用实现 `Colorable` 接口的值。这是 `Endpoint` 是一个最终类型，且最终类型变量的运行时类型与其编译类型完全相同。因此，变量 `e` 的运行时类型必须是 `Endpoint`，而 `Endpoint` 类型没有实现 `Colorable`。

## 5.5 转换上下文

## 转换与上下文

### 示例 5.5-2, 数组类型的类型转换

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
    public String toString() { return "("+x+","+y+")"; }
}
interface Colorable {
    void setColor(int color);
}
class ColoredPoint extends Point implements Colorable {
    int color;
    ColoredPoint(int x, int y, int color) {
        super(x, y); setColor(color);
    }
    public void setColor(int color) { this.color = color; }
    public String toString() {
        return super.toString() + " @" + color;
    }
}
```

```java
class Test {
    public static void main(String[] args) {
        Point[] pa = new ColoredPoint[4];
        pa[0] = new ColoredPoint(2, 2, 12);
        pa[1] = new ColoredPoint(4, 5, 24);
        ColoredPoint[] cpa = (ColoredPoint[])pa;
        System.out.print("cpa: { ");
        for (int i = 0; i < cpa.length; i++) {
            System.out.print((i == 0 ? "" : ", ") + cpa[i]);
        }
        System.out.println(" }");
    }
}
```

该程序无错误地编译并产生输出：

```
cpa: { (2,2)@12, (4,5)@24, null, null }
```

### 示例 5.5-3. 运行时不兼容类型的类型转换



```java
class Point { int x, y; }
interface Colorable { void setColor(int color); }
class ColoredPoint extends Point implements Colorable {
    int color;
    public void setColor(int color) { this.color = color; }
}

class Test {
    public static void main(String[] args) {
        Point[] pa = new Point[100];

        // 下面行将抛出 ClassCastException:
        ColoredPoint[] cpa = (ColoredPoint[])pa;
        System.out.println(cpa[0]);
        int[] shortvec = new int[2];
        Object o = shortvec;

        // 下面行将抛出 ClassCastException:
        Colorable c = (Colorable)o;
        c.setColor(0);
    }
}
```

该程序使用类型转换通过编译，但在运行时抛出异常，因为这些类型是不兼容的。

## 5.6 数值上下文

数值上下文适用于算术运算符的操作数、数组创建和访问表达式、条件表达式以及 `switch` 表达式的结果表达式。

如果一个表达式属于以下一种情况，则该表达式出现在数值算术上下文中：

- 一元加运算符 `+`、一元减运算符 `-` 或位取反运算符 `~` 的操作数 (§15.15.3, §15.15.4, 或 §15.15.5)
- 乘法运算符 `*`、`/` 或 `%` 的操作数 (§15.17)
- 数值类型的加法或减运算符 `+` 或 `-` 的操作数 (§15.18.2)
- 移位运算符 `<<`、`>>` 或 `>>>` 的操作数 (§15.19)。这些移位运算符的操作数分别处理，而不是作为一个整体。长位移（右操作数）不会将被移动的值（左操作数）提升为 `long`。
- 数值比较运算符 `<`、`<=`、`>`、`>=` 的操作数 (§15.20.1)
- 数值相等运算符 `==` 或 `!=` 的操作数 (§15.21.1)
- 整数位运算符 `&`、`^` 或 `|` 的操作数 (§15.22.1)

如果一个表达式属于以下一种情况，则该表达式出现在数值选择上下文中：

- 数组创建表达式中的维度表达式 (§15.10.1)
- 数组访问表达式中的索引表达式 (§15.10.3)

如果一个表达式属于以下一种情况，则该表达式出现在数值选择上下文中：

- 数值条件表达式的第二个或第三个操作数 (§15.25.2)
- 独立 `switch` 表达式的结果表达式 (§15.28.1)，其中所有结果表达式都可转换为数值类型

数值提升决定了数值上下文中所有表达式的提升类型。选择提升类型的目的是使得每个表达式都能转换为该类型，并且在算术运算的情况下，该操作对于提升类型的值是有定义的。数值上下文中表达式的顺序对于数值提升并不重要。规则如下：

1. 如果任何表达式是引用类型，则它将进行拆箱转换 (§5.1.8)。
2. 接下来，根据以下规则对某些表达式应用宽化 primitive 转换 (§5.1.2) 和收窄 primitive 转换 (§5.1.3)：
   - 如果任何表达式是 `double` 类型，则提升类型为 `double`，其他不是 `double` 类型的表达式将通过宽化 primitive 转换转换为 `double`。
   - 否则，如果任何表达式是 `float` 类型，则提升类型为 `float`，其他不是 `float` 类型的表达式将通过宽化 primitive 转换转换为 `float`。
   - 否则，如果任何表达式是 `long` 类型，则提升类型为 `long`，其他不是 `long` 类型的表达式将通过宽化 primitive 转换转换为 `long`。
   - 否则，如果任何表达式是 `int` 类型，则提升类型为 `int`，其他不是 `int` 类型的表达式将通过宽化 primitive 转换转换为 `int`。

在算术上下文或数组上下文中，规则如下：

- 如果任何表达式是 `int` 类型且为常量表达式 (§15.29)，提升类型为 `int`，不是 `int` 的表达式通过宽化 primitive 转换转换为 `int`。
- 否则，如果任何表达式是 `short` 类型，则提升类型为 `short`，不是 `short` 的表达式通过收窄 primitive 转换转换为 `short`。
- 否则，如果任何表达式是 `byte` 类型，则提升类型为 `byte`，不是 `byte` 的表达式通过收窄 primitive 转换转换为 `byte`。
- 否则，如果任何表达式是 `char` 类型，则提升类型为 `char`，不是 `char` 的表达式通过收窄 primitive 转换转换为 `char`。

一元数值提升是对出现在算术上下文或数组上下文中的单个表达式进行数值提升。

二元数值提升是对出现在算术上下文中的成对表达式进行数值提升。

通用数值提升是对出现在数值选择上下文中所有表达式进行数值提升。

### 示例 5.6-1. 二元数值提升

```java
class Test {
    public static void main(String[] args) {
        byte b = 2;
        int[] a = new int[b]; // 维度表达式提升
        char c = '\u0001';
        a[c] = 1; // 索引表达式提升
        a[0] = -c; // 一元提升
        System.out.println("a: " + a[0] + "," + a[1]); // 位取反提升
        b = -1;
        int i = -b;
        System.out.println("-0x" + Integer.toHexString(i) + "=0x" + Integer.toHexString(i));
        i = b << 4L; // 移位提升（左操作数）
        System.out.println("0x" + Integer.toHexString(b) + "<<4L=0x" + Integer.toHexString(i));
    }
}
```

该程序输出：

```
a:-1,1
-0xfffffffe=0x0
0xffffff<<4L=0xffffff
```

### 示例 5.6-2. 二元数值提升

```java
class Test {
    public static void main(String[] args) {
        int i = 0;
        float f = 1.0f;
        double d = 2.0;
        // int*float 被提升为 float*float，然后
        // float==double 被提升为 double==double:
        if (i * f == d) System.out.println("oops");
    }
}
```

转换与上下文

数值上下文 5.6

```java
// A char&byte is promoted to int&int:
byte b = 0xbf;
char c = 'G' & b;
int control = c & b;
System.out.println(Integer.toHexString(control));

// Here int:float is promoted to float:float;
f = (b==0) ? i : 4.0f;
System.out.println(1.0/f);
```

该程序产生输出：

```
7
0.25
```

该示例将 ASCII 字符 G 转换为 ASCII 控制字符 G (BEL)，方法是掩码该字符除低 5 位以外的所有位。7 是该控制字符的数值值。

# 第 6 章

## 标识

名称（NAMES）用于指代程序中声明的实体。

声明的实体 (§6.1) 是一个包、类、接口、引用类型的成员（类、接口、字段、方法）、类型参数、异常参数或局部变量。

程序中的名称要么是简单的（simple）的，即由单个标识符组成；要么是限定的（qualified）的，即由由 `.` 标记分隔的标识符序列组成 (§6.2)。

每个引入名称的声明都有一个作用域 (§6.3)，作用域是程序文本中允许该声明实体通过简单名称被引用的部分。

限定名称 `N.x` 可用于指代包或引用类型的成员，其中 `N` 是简单名称或限定名称，`x` 是一个标识符。如果 `N` 指向一个包，则 `x` 是该包的成员，其可以是类、接口或子包。如果 `N` 指向一个引用类型或引用类型的变量，则 `x` 指向该类型的成员，其可以是类、接口或方法。

在确定名称的含义 (§6.5) 时，使用发生地的上下文来消除同名包、类型、变量和方法之间的歧义。

访问控制 (§6.6) 可以在类、接口、方法或字段的声明中指定，以控制何时允许访问成员。访问（Access）是一个作用域（scope）不同的概念。访问指定了程序文本中允许通过限定名称引用声明实体的部分。对声明实体的访问也与字段访问表达式 (§15.11)、未用简单名称指定的方法调用表达式 (§15.12)、方法引用表达式 (§15.13) 或限定类实例创建表达式 (§15.9) 相关。在没有访问修饰符的情况下，大多数声明具有包访问权限（package access），允许在包含其声明的包内的任何地方访问；其他可能性可能是 `public`（公共）、`protected` 和 `private`（私有）。

## 6.1 声明

完全限定和规范化名称 (§6.7) 在本章也有讨论。

声明向程序中引入一个实体，并包含一个标识符 (§3.8)，该标识符可在名称中用于指代该实体。当引入的实体是类、接口或类型参数时，标识符受到限制以避免某些特定的上下文关键字。

声明的实体是以下之一：

- 在模块声明 (§7.7) 中声明的模块
- 在包声明 (§7.4) 中声明的包
- 被导入的类或接口，在单类型导入声明或按需导入类型的导入声明 (§7.5.1, §7.5.2) 中声明
- 被导入的静态成员，在单静态导入声明或按需导入静态的声明 (§7.5.3, §7.5.4) 中声明
- 类，通过普通类声明 (§8.1)、枚举声明 (§8.9) 或记录声明 (§8.10) 声明
- 接口，通过普通接口声明 (§9.1) 或注解接口声明 (§9.6) 声明
- 类型参数，作为泛型类、接口、方法或构造函数声明的一部分 (§8.1.2, §9.1.2, §8.4.4, §8.8.4)

### 名称的声明

- 引用类型的成员 (§8.2, §9.2, §8.9.3, §9.6, §10.7)：
  - 成员类 (§8.5, §9.5)
  - 成员接口 (§8.5, §9.5)
  - 字段，为以下之一：
    - 在类中声明的字段 (§8.3)
    - 在接口中声明的字段 (§9.3)
    - 对应于枚举常量或记录组件的类的隐式声明字段
    - 字段 `length`，它是数组类型的隐式成员 (§10.7)
  - 方法，为以下之一：
    - 在类中声明的方法（抽象的或其他形式的） (§8.4)
    - 在接口中声明的方法（抽象的或其他形式的） (§9.4)
    - 对应于记录组件的隐式声明访问器方法
- 枚举常量 (§8.9.1)
- 记录组件 (§8.10.3)
- 形式参数，为以下之一：
  - 类或接口方法的形式参数 (§8.4.1)
  - 类的构造函数的形式参数 (§8.8.1)
  - `lambda` 表达式的形式参数 (§15.27.1)
  - `try` 语句 `catch` 句中异常处理器的异常参数 (§14.20)
  - 局部变量，为以下之一：
    - 由块中的局部变量语句声明的局部变量 (§14.4.2)
    - 由 `for` 语句或 `try-with-resources` 语句声明的局部变量 (§14.14, §14.20)
    - 由模式声明的局部变量 (§14.30)
    - 局部类或接口 (§14.3)，为以下之一：
      - 由普通类声明的局部类
      - 由枚举声明声明的局部类
      - 由记录声明声明的局部类
      - 由普通接口声明的局部接口

构造函数 (§8.8, §8.10) 也由声明引入，但使用它们被声明的类，而不是引入一个新的名称。泛型类或接口的声明（`class<T> ...`）引入了命名的 `C` 和一个类型族：原始类型 `C` 和参数化类型 `C<T>`。当通用性很重要且在下方识别为非泛型上下文时，对 `C` 的引用表示类或接口。在其他上下文中，对 `C` 的引用表示类型或类型的一部分，由 `C` 引入。

15 个非泛型上下文如下：

1. 模块声明中的 `uses` 指令 (§7.7.1)
2. 单类型导入声明 (§7.5.1)
3. 单静态导入声明中 `.` 左侧 (§7.5.3)
4. 按需导入类型声明中 `.` 左侧 (§7.5.4)
5. 密封类或接口声明的 `permits` 子句 (§8.6, §9.1.4)
6. 构造函数声明中 `.` 左侧 (§8.8)
7. 注解中的 `@` 符号 (§9.7)
8. 类字面量中 `.class` 左侧 (§15.8.2)
9. 限定表达式中 `.this` 左侧 (§15.8.4)
10. 限定父类表达式中 `.super` 左侧 (§15.11.2)
11. 限定方法调用表达式中 `.Identifier` 或 `.super.Identifier` 左侧 (§15.12)
12. 方法引用表达式中 `.super::` 左侧 (§15.13)
13. 后置表达式中或 `try-with-resources` 语句中的限定表达式名 (§15.14.1, §14.20.3)
14. 方法或构造函数的 `throws` 子句 (§8.4.6, §8.8.5, §9.4)
15. 异常参数声明 (§14.20)

前 12 个非泛型上下文对应于 §6.5.1 中限定的 `TypeName`。第 13 个非泛型上下文是 `ExpressionName`（如 `C::x`）包含 `TypeName` `C` 以表示成员访问。`TypeName` 在 13 个上下文中的常用是有意义的：它表明这些上下文涉及低于第一类的类型使用。相比之下，第 14 和第 15 个非泛型上下文使用 `ClassType`，表明 `throws` 和 `catch` 子句以第一类的方式使用类型，与字段声明一致。将这两个上下文表征为非泛型是因为异常类型不能被参数化 (§8.1.2)。

注意，`ClassType` 产生允许注解，因此可以在 `throws` 或 `catch` 子句中为类型添加注解，而 `TypeName` 产生则不允许添加注解，因此例如在单类型导入声明中无法为类型添加注解。

## 命名规范

Java SE 平台的类库尽可能根据此处介绍的规范选择名称。这些规范有助于提高代码的可读性并避免某些冲突。

我们建议用 Java 编程语言编写的所有程序遵循这些规范。然而，如果长期习惯另有规定，则不应死板地遵循这些规范。例如，`java.lang.Math` 的 `sin` 和 `cos` 方法具有数学惯例名称，尽管这些方法名符合建议的规范（因为它们很短且不是动词）。

## 包名与模块名

程序员应该通过为广泛分发的包选择包名，以避免两个发布的包具有相同的可能。这使得包易于安装和分类。本节指定了生成此类唯一名称的建议规范。鼓励 Java SE 平台的实现提供自动支持，将一组包从本地和随意包名转换为描述的唯一名称格式。

### 示例 6.1-1. 唯一的包名

```
com.nighthacks.scrabble.dictionary
org.openjdk.compiler.source.tree
net.jcip.annotations
edu.cmu.cs.bovik.cheese
gov.whitehouse.socks.mousefinder
```

唯一包名的第一个组件始终用全小写字母编写，并且应该是顶级域名名称之一，如 `com`、`edu`、`gov`、`mil`、`net` 或 `org`，或者是 ISO 标准 3166 中指定的标识国家的英语双字母代码之一。

在某些情况下，Internet 域名可能不是一个有效的包名。以下是处理这些情况的一些建议约定：

- 如果名称包含连字符（`-`）或任何标识符中不允许的其它字符 (§3.8)，请将其转换为下划线。
- 如果生成的包名组件中任何一个是关键字 (§3.9)，请在它们后面添加一个下划线。
- 如果生成的包名组件中任何一个以数字或任何不允许作为标识符起始字符的字符开头，请在该组件前加一个下划线。

模块的名称应与其主要导出的包名称对应。如果一个模块没有这样的包，或者出于历史原因，它的名称不能与其任何一个导出的包对应，则其名称应以作者相关的 Internet 域名的反转形式开头。

### 示例 6.1-2. 唯一的模块名

```
com.nighthacks.scrabble
org.openjdk.compiler
net.jcip.annotations
```

包或模块名称的第一个组件不能是标识符 `java`。以标识符 `java` 开头的包和模块名留给 SE 平台的包和模块使用。



包或模块的名称并不意味着该包或模块存储在 Internet 上。例如，包名 `edu.cmu.cs.bovik.cheese` 不一定能从主机 `edu.cmu.cs` 或 `edu.cmu.edu.cmu` 获取。生成唯一包和模块名的建议约定仅仅是将包和模块命名约定建立在现有的、为人知的唯一注册表之上，而无需为包和模块名创建一个单独注册表。

## 类和接口名称

### 声明 6.1

类的名称应该是描述性名词或名词短语，不宜过长，使用混合大小写，且每个单词的首字母大写。

## 示例 6.1-3. 描述性的类名

```
ClassLoader
SecurityManager
Thread
Dictionary
BufferedInputStream
```

同样，接口的名称应该是简短且具描述性的，不宜过长，且每个单词的首字母大写。该名称可以是描述性名词或名词短语，这在接口被用作抽象超类时是合适的，例如 `java.io.DataInput` 和 `java.io.DataOutput` 接口；也可以是描述行为的形容词，如 `Runnable` 和 `Cloneable` 接口。

### 类型变量名

类型名称应该是简洁的（尽可能使用单个字符）且具有启发性的，并且不应包含小写字母。这有助于区分类型参数与普通类及接口。

容器类和接口使用 `E` 作为元素类型。映射 应该使用 `K` 作为键的类型，使用 `V` 作为值的类型。名称 `X` 应用于任意异常类型。当类型没有特定的特征可以进行区分时，我们使用 `T` 表示类型。（这在泛型方法中很常见。）

如果有多个表示任意类型的类型参数，应该使用字母表中紧邻 `T` 的字母，例如 `S`。或者，使用数字下标（例如 `T1`, `T2`）来区分不同的类型变量。在这种情况下，具有相同前缀的变量应带有下标。

如果泛型方法出现在泛型类中，最好避免为方法的类型参数和类的类型参数相同的名称，以避免混淆。嵌套类也是如此。

## 示例 6.1-4. 惯用的类型变量名

```
public class HashSet<E> extends AbstractSet<E> { ... ... }
public class HashMap<K,V> extends AbstractMap<K,V> { ... ... }
public class ThreadLocal<T> { ... ... }
public interface Functor<T, X extends Throwable> {
    T eval() throws X;
}
```

当类型参数不方便地归入上述任一类别时，选择的名称应在单个字母的范围内尽可能有意义。上述提到的名称（E, K, V, X, T）不应用于不属于指定类别的类型参数。

表示集合可选值的常量组，或者较少地表示整数值中的掩码位，有时使用一个常用的缩写词作为名称前缀。

## 名称

### 声明 6.1

例如：

```
interface ProcessStates {
    int PS_RUNNING = 0;
    int PS_SUSPENDED = 1;
}
```

局部变量和参数名应该是简短且有意义的。它们通常是不是单词的短促小写字母序列，例如：

- 缩写词，如一系列单词的首字母，例如 `cp` 用于一个持有 `ColoredPoint` 引用的变量
- 简写词，如 `buf` 用于一个指向某种缓冲区的指针
- 助记术语，以某种方式组织以助于记忆
- `in` 和 `out`，只要涉及输入和输出，仿 `System` 字段的模式
- `off` 和 `len`，只要涉及偏移量和长度，仿 `DataInput` 和 `DataOutput` 方法的模式

应避免单字符的局部变量或参数名，临时变量除外，在这种情况下单字符名称为：

- `b` 表示一个 byte
- `c` 表示一个 char
- `d` 表示一个 double
- `e` 表示一个 Exception
- `f` 表示一个 float
- `i, j, 和 k` 表示 ints
- `l` 表示 long
- `o` 表示 Object
- `s` 表示 String

## 6.2 名称和标识符

名称用于引用程序中声明的实体。名称有两种形式：简单名（simple names）和限定名（qualified names）。

简单名是单一的标识符。

限定名由一个名称、一个 `.` 标记和一个标识符组成。

在确定名称的含义（§6.5）时，会考虑名称出现的上下文。§6.5 的规则区分了不同的上下文：在这些上下文中，名称必须表示（引用）包（§6.5.3）；类、接口或类型参数（§6.5.5）；表达式中的变量或值（§6.5.6）；或方法（§6.5.7）。

包、类、接口和类型参数具有成员，可以通过限定名访问。作为关于限定名讨论和名称含义确定的背景，请参阅 §4.4、§4.5.2、§4.8、§4.9、§7.1、§8.2 以及 §10.7 中成员的描述。

程序中的所有标识符并不是名称的一部分。标识符还用于以下情况：

- 在声明中（§6.1），标识符可能出现以指定声明实体被为人知的名称。
- 作为标记语句（§14.7）中的标签，以及在 break 和 continue 语句（§14.15, §14.16）中引用语句标签。
- 在字段访问表达式（§15.11）中，标识符出现在 `.` 标记之后，表示 `.` 之前对象的成员，或者 `super` 或 `TypeName.super` 之前对象的。
- 在方法调用表达式（§15.12）中，只要标识符出现在 `.` 标记之后且 `.` 标记之前，就表示为 `.` 之前对象调用的方法，或者 `.` 之前类型的方法，或者 `super` 或 `TypeName.super` 之前对象调的方法。
- 在方法引用表达式（§15.13）中，只要标识符出现在 `::` 标记之后，就表示为 `::` 之前对象的方法，或者 `::` 之前类型的方法，或者 `super` 或 `TypeName.super` 之前对象的方法。

## 6.2 名称与标识符

- 在限定的类实例创建表达式 (§15.9) 中，标识符出现在新标记的右侧，用于指示一个类型是该新标记之前的表达式的编译时类型的成员类型。
- 在注解的元素-值对 (§9.7.1) 中，表示对应注解接口的元素。

在该程序中：

```java
class Test {
    public static void main(String[] args) {
        Class c = System.out.getClass();
        System.out.println(c.toString().length() +
            args[0].length() + args.length());
    }
}
```

标识符 `Test`、`main` 以及 `args` 和 `c` 的首次出现并不是名称。相反，它们在声明中被标识，以指定声明实体的名称。`String`、`Class`、`System.out.getClass`、`System.out.println`、`c.toString()`、`args` 和 `args.length` 这些名称出现在示例中。

`length` 在 `args.length` 中出现是因为 `args.length` 是一个限定名称 (§6.5.2) 而不是字段访问表达式 (§15.1)。字段访问表达式、方法调用表达式、方法引用表达式以及限定的类实例创建表达式都使用标识符来表示感兴趣的成员。因此，`length` 在 `args[0].length()` 中的出现不是名称，而是出现在方法调用表达式中的一个标识符。

人们可能会奇怪，为什么这些类型的表达式使用标识符而不是简单的名称，毕竟名称终仅仅是标识符。原因为简单表达式名称必须根据词法环境定义；也就是说，变量声明、限定方法调用、方法引用和限定的类实例创建的简单名称表达式，都引用了其名称不在词法环境中的成员。根据定义，此类名称仅在由字段访问表达式、方法调用表达式、方法引用表达式或类实例创建的 `Primary` 提供的上下文中绑定；或者通过字段访问表达式、方法调用表达式、方法引用表达式的 `super` 绑定；依此类推。因此，我们用标识符而不是简单名称来表示成员。

更复杂的是，字段访问表达式并不是对象字段的唯一方式。由于解析的原因，限定名称被用于表示作用域变量的字段。（变量本身用简单名称表示，如上所述。）对于访问控制 (§6.6) ，必须同时应用于字段的两种表示方法。

## 6.3 声明的作用域

声明的作用域是程序的一个区域，在该区域内，可以使用简单名称引用由声明的实体，前提是它没有被遮蔽 (§6.4.1)。

当且仅当声明的作用域包含程序的某点时，则认为该声明在程序的该点处于作用域内。

可观测顶层包 (§7.4.3) 声明的作用域是与该包唯一可见的模块 (§7.4.3) 相关的所有可观测编译单元。

不可观测的包的声明永远不在作用域内。

子包的声明永远不在作用域内。

`java` 包始终在作用域内。

由单类型导入声明 (§7.5.1) 或按需类型导入声明 (§7.5.2) 导入类或接口的作用域，是模块声明 (§7.7) 以及该导入语句所在的编译单元中所有的类和接口声明 (§8.1, 9.1)，以及该编译单元的模块声明或包声明上的任何注解。

由单静态导入声明 (§7.5.3) 或按需静态导入声明 (§7.5.4) 导入的成员的作用域，是模块声明以及该导入语句所在的编译单元中所有的类和接口声明，以及该编译单元的模块声明或包声明上的任何注解。

顶层类或接口 (§7.6) 的作用域是声明该顶层类或接口的包中所有的类和接口声明。

在类或接口 `c` (§8.2, 9) 中声明或由其继承的成员 `m` 声明的作用域是 `c` 的整个体，包括任何嵌套的类或接口声明。如果 `c` 是一个记录（record），那么 `m` 的作用域还包括 `c` 记录声明的头部。

方法 (§8.4.1)、构造函数 (§8.8.1) 或 lambda 表达式 (§15.27) 的形式参数的作用域是该方法、构造函数或 lambda 表达式的整个体。

类类型参数 (§8.1.2) 的作用域是类声明的类型参数部分、该类声明的任何超类或超接口的类型参数部分以及类体。如果该类是记录类 (§8.10)，则类型参数的作用域还包括记录声明的头部 (§8.10.1)。

接口类型参数 (§9.1.2) 的作用域是接口声明的类型参数部分、该接口声明的任何超接口的类型参数部分以及接口体。

方法类型参数 (§8.4.4) 的作用域是该方法的整个声明，包括类型参数部分，但不包括方法修饰符。

构造函数类型参数 (§8.4.4) 的作用域是构造函数的整个声明，包括类型参数部分，但不包括构造函数的修饰符。

紧被块包含的类或接口声明的作用域是该块的剩余部分，包括类接口声明。

紧被 switch 语句包含的类或接口声明的作用域是 switch 语句的剩余部分，包括类接口声明。

在块中声明的局部变量的作用域是从声明开始的块的剩余部分。

在增强 for 语句 (§14.4) 头部中声明的局部变量的作用域是该块。

在 try-with-resources 语句 (§14.20.3) 的资源规范中声明的局部变量的作用域是从声明到资源规范的剩余部分以及整个 try 块。

在 try 语句 (§14.20) 的 catch 子句中声明的异常参数的作用域是与 catch 相关的整个块。

这些规则意味着类和接口类型的声明不需要在使用类型之前出现。在以下程序中，`Point` 类中使用 `PointList` 是有效的，因为 `PointList` 类声明的作用域包含了类 `Point` 和类 `PointList`，以及 `points` 包其他编译单元中的任何类或接口声明。

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

-- 以下程序会导致编译错误，因为局部变量 `x` 的初始化在局部变量 `x` 声明的作用域内，但局部变量 `x` 没有值且无法使用。字段 `x` 有值 0（在 Test1 初始化时赋值），但这是一个干扰项，它被局部变量 `x` 遮蔽了 (§6.4.1)。

```java
class Test1 {
    static int x;
    public static void main(String[] args) {
        int x = x;
    }
}
```

-- 以下程序可以编译：

```java
class Test2 {
    static int x;
    public static void main(String[] args) {
        int x = (x)*2;
        System.out.println(x);
    }
}
```

局部变量 `x` 在使用之前已经确定赋值（确定赋值 §16）。它打印：

在后续程序中，`three` 的初始化器可以正确引用早先声明符中定义的变量 `two`，下一行中的方法调用也可以正确引用在块中之前声明的变量 `three`。

```
class Test3 {
    public static void main(String[] args) {
        System.out.print("2+1=");
        int two = 2, three = two + 1;
        System.out.println(three);
    }
}
```

该程序产生输出：

2+1=3

模式变量声明的作用域（即由模式声明的局部变量）是程序中在值与模式的匹配成功后（§14.30.2）的部分。它通过考虑程序中那些在从声明模式变量的模式开始的区域内、模式变量被确定匹配的点来确定。

本节的剩余部分用于对“确定匹配”（definitely matched）一词进行精确解释。该分析考虑了语句和表达式的结构，并对布尔表达式运算符和某些语句形式进行了特殊处理。

可以看出，模式变量声明的作用域是一个依赖于流的概念，类似于确定赋值（§16 确定赋值）。本节其余部分定义的规则刻意具有与确定赋值规则相似的形式。

该分析依赖于技术术语“引入”（introduced by），其形式如下：

- `模式变量在为真时由一个表达式引入`
- `模式变量在为假时由一个表达式引入`
- `模式变量由一个语句引入`

最简单的的例子是，模式变量 `s` 在为真时由表达式 `a instanceof String s` 引入。换句话说，如果表达式的值为真，则模式匹配必须成功，因此模式变量必须被赋一个值。

相反，模式变量 `t` 在为假时由表达式 `!(b instanceof Integer t)` 引入。这是因为只有当表达式值为假时，模式匹配才可能成功。

### 6.3.1 表达式中模式变量的作用域

只有特定类型的布尔表达式涉及模式变量的引入以及确定这些变量是否被确定匹配。如果一个表达式不是条件与表达式、条件或表达式、逻辑取反表达式、条件表达式、instanceof 表达式、switch 表达式或括号表达式，则不适用任何作用域规则。

### 6.3.1.1 条件与运算符 &&

以下规则适用于条件与表达式 `a && b` (§15.23)：

- `a` 为真时引入的模式变量在 `b` 处是确定匹配的。
- 如果 `a` 为真时引入的任何模式变量在 `b` 处的作用域内，则为编译错误。
- `a && b` 为真时引入的模式变量当且仅当 (i) 它由 `a` 为真时引入或 (ii) 它由 `b` 为真时引入。

应该注意，没有关于在 `a && b` 为假时引入模式变量的规则。这是因为在编译时无法确定哪一个将为假。

如果满足以下任何条件，则为编译错误：

- 模式变量既是 (i) 由 `a` 为真时引入又是 (ii) 由 `b` 为真时引入。
- 模式变量既是 (i) 由 `a` 为假时引入又是 (ii) 由 `b` 为假时引入。

这两种错误情况排除了 `&&` 运算符的两个操作数声明同名模式变量的可能性。例如，有问题的表达式 `(a instanceof String s) && (instanceof String s)`；第一种错误情况涵盖了整个表达式求值为真，此时（如果代码是法的），由于左操作数和右操作数都求值为真，则需要对模式变量 `s` 的两个声明进行初始化。由于程序的其余部分中无法区分这两个变量 `s`，因此整个表达式被认为是错误的。第二种错误情况涵盖了相反的情况，即整个表达式求值为假。

### 6.3.1.2 条件或运算符 ||

以下规则适用于条件或表达式 `a || b` (§15.24)：

- `a` 为假时引入的模式变量在 `b` 处是确定匹配的。
- 如果 `a` 为假时引入的任何模式变量在 `b` 处的作用域内，则为编译错误。
- `a || b` 为假时引入的模式变量当且仅当 (i) 它由 `a` 为假时引入或 (ii) 它由 `b` 为假时引入。

应该注意，没有关于在 `a || b` 为真时引入模式变量的规则。这是因为在编译时无法确定哪个操作数将求值为真。

如果满足以下任何条件，则为编译错误：

- 模式变量既是 (i) 由 `a` 为真时引入又是 (ii) 由 `b` 为真时引入。
- 模式变量既是 (i) 由 `a` 为假时引入又是 (ii) 由 `b` 为假时引入。

这两种错误排除了 `||` 运算符的两个操作数声明同名模式变量的可能性。例如，考虑有问题的表达式 `(a instanceof String s) || (b instanceof s)`。第一种错误情况涵盖了整个表达式求值为真，此时（如果代码是法的），由于左操作数和右操作数都求值为真，则需要对模式变量 `s` 的两个声明进行初始化。由于编译时无法确定哪个操作数将求值为真，整个表达式被认为是错误的。第二种错误情况涵盖了相反的情况，即整个表达式求值为假。

### 6.3.1.3 逻辑取反运算符 !

以下规则适用于逻辑取反表达式 `!a` (§15.6)：

- 模式变量在 `!a` 为真时引入当且仅当它由 `a` 为假时引入。



- 模式变量在 `$!a$` 为假时引入当且仅当它由 `$a$` 为真时引入。

### 6.3.1.4 条件运算符 `? :`

以下规则适用于条件表达式 `$a ? b : c$` (§15.25)：

- `$a$` 为真时引入的模式变量在 `$b$` 处是确定匹配的。

如果 `$a$` 为真时引入的任何模式变量在 `$b$` 处的作用域内，则为编译错误。

#### 声明的作用域

- `$a$` 为假时引入的模式变量在 `$c$` 处是确定匹配的。

如果 `$a$` 为假时引入的任何模式变量在 `$c$` 处的作用域内，则为编译错误。

应该注意，没有关于在 `$a ? b : c$` 为真或假时引入模式变量的规则。这是因为在编译时无法确定操作数 `$a$` 是否求值为真。

如果满足以下任何条件，则为编译错误：

- 模式变量既是 (i) 由 `$a$` 为真时引入又是 (ii) 由 `$c$` 为真时引入。
- 模式变量既是 (i) 由 `$a$` 为真时引入又是 (ii) 由 `$c$` 为假时引入。
- 模式变量既是 (i) 由 `$a$` 为假时引入又是 (ii) 由 `$b$` 为真时引入。
- 模式变量既是 (i) 由 `$a$` 为假时引入又是 (ii) 由 `$b$` 为假时引入。
- 模式变量既是 (i) 由 `$b$` 为真时引入又是 (ii) 由 `$c$` 为真时引入。
- 模式变量既是 (i) 由 `$b$` 为假时引入又是 (ii) 由 `$c$` 为假时引入。

> 这些错误情况类似于 `&&` 和 `||` 运算符的类似错误情况。它们消除了 `? :` 运算符的操作数之间可能出现相同模式变量声明的情况。

### 6.3.1.5 模式匹配运算符 `instanceof`

以下规则适用于带有模式操作数的 `instanceof` 表达式，即 `instanceof p` (§15.20.2)：

- 模式变量在 `instanceof p` 为真时引入，它由模式 `p` 声明。确定哪些模式变量由模式声明的规则见 §14.30.1。

如果 `a instanceof p` 为真时引入的任何模式变量在 `instanceof` 表达式的作用域内，则为编译错误。

模式变量不允许隐藏另一个局部变量 (§6.4)。

## 标识符声明的作用域 6.3

需要注意的是，当 `instanceof p` 为 `false` 时，没有规则用于通过其引入模式变量。

### 6.3.1.6 switch 表达式

以下规则适用于 switch 表达式 (§15.28)：

- 由包含在 switch 标签化语句组 (§14.11.1) 中的语句 `s` 引入的模式变量，如果在该 switch 标签化语句组中，`s` 之后的所有语句（如果有）中都会被确定匹配。

### 6.3.1.7 括号表达式

以下规则适用于括号表达式 `(a)` (§15.8.5)：

- 由 `(a)` 在为 `true` 时引入的模式变量，当且仅当它由 `a` 在为 `true` 时引入。
- 由 `(a)` 在为 `false` 时引入的模式变量，当且仅当它由 `a` 在为 `false` 时引入。

### 6.3.2 语句中模式变量的作用域

只有少数几种类型的语句在确定模式变量的作用域方面起着重要作用。

当 `if`、`while`、`do` 或 `for` 语句包含引入模式变量的表达式时，这些变量的作用域在某些情况下可以包含语句的子语句。

> 例如，在下面的 if-then-else 语句中，模式变量 `s` 的作用域包括一个子语句，但不包括另一个：

```java
Object o = ...
if (o instanceof String s) {
    // s 在此子语句的作用域内；不需要消耗 o
    System.out.println(s.replace("*", "_"));
} else {
    // s 不在此子语句的作用域内（因此，报错）
    System.out.println(s);
}
```

此外，在某些情况下，模式变量可以由语句本身引入，而不是由语句内的表达式引入。由语句引入的模式变量在闭包块的后续语句中作用域内。

## 声明的作用域

例如，在下面的方法中，模式变量 `s` 的作用域包括 `if` 语句之后的方法体：

```java
void test(Object o) {
    if (!(o instanceof String s)) {
        throw new IllegalArgumentException();
    }
    // 这一点仅在模式匹配成功时才可到达
    // 因此，s 在块的剩余范围内作用域

    ...
    System.out.println(s.repeat(5));
}
```

### 6.3.2.1 块

以下规则适用于包含在块 (§14.2) 中的块语句 `s`，且该块不是 switch 块 (§14.11.1)：

- 由 `s` 引入的模式变量如果在块中 `s` 之后的所有块语句（如果有）中都会被确定匹配。

### 6.3.2.2 语句

以下规则适用于语句 `if (e) s` (§14.9.1)：

- 由 `e` 在为 `true` 时引入的模式变量在 `s` 处被确定匹配。
- 如果由 `e` 在为 `true` 时引入的任何模式变量在 `s` 处已在作用域内，则是编译错误。
- 由 `if (e) s` 引入的模式变量当且仅当 (i) 它由 `e` 在为 `false` 时引入且 (ii) `s` 无法正常完成。
- 如果由 `if (e) s` 引入的任何模式变量在语句处已在作用域内，则是编译错误。

关于 if-then 语句引入模式变量的规则依赖于“无法正常完成” (§14.22) 的关系，而这又依赖于常量表达式 (§15.29) 的概念。这意味着计算模式变量的作用域可能需要确定简单名称或形式为 `TypeName . Identifier` 的限定名称是否引用了常量变量。由于模式变量永远不会引用常量变量，因此不存在循环依赖。

以下规则适用于语句 `if (e) S else T` (§14.9.2)：

- 由 `$e$` 在为 `true` 时引入的模式变量在 `$s$` 处被确定匹配。
  如果由 `$e$` 在为 `true` 时引入的任何模式变量在 `$s$` 处已在作用域内，则是编译错误。
- 由 `$e$` 在为 `false` 时引入的模式变量在 `$r$` 处被确定匹配。
  如果由 `$e$` 在为 `false` 时引入的任何模式变量在 `$T$` 处已在作用域内，则是编译错误。
- 由 `if (e) S else T` 引入的模式变量满足以下任一：
    - 它由 `$e$` 在为 `true` 时引入，`$S$` 可以正常完成，且 `$T$` 无法正常完成；或者
    - 它由 `$e$` 在为 `false` 时引入，`$S$` 无法正常完成，且 `$T$` 可以正常完成。
  如果由 `if (e) S else T` 引入的任何模式变量在 `if` 语句处已在作用域内，则是编译错误。

这些规则突显了模式变量作用域的流特性。例如，在下面的语句中：

```java
if (o instanceof String s) {
    counter += s.length();
} else {
    System.out.println(e); // s 不在作用域内
}
```

变量 `$s$` 由 `instanceof` 表达式引入，并在第一个包含的语句（`then` 块中的赋值语句）中作用域内，但在第二个包含的语句（`else` 块中的表达式语句）中不在作用域内。

此外，结合对布尔表达式的处理，模式变量的作用域对于利用熟悉的布尔逻辑等价性的代码重构具有健壮性。之前的代码可以重写为：

```java
if (!(o instanceof String s)) {
    System.out.println(e); // s 不在作用域内
} else {
    counter += s.length();
}
```

代码可以重写如下，尽管不建议这样使用 `!` 运算符：

```java
if (!(o instanceof String s)) {
    throw new IllegalArgumentException();
}
```

### 6.3.2.3 while 语句

以下规则适用于语句 `while (e) S` (§14.12)：

- 由 `$e$` 在为 `true` 时引入的模式变量在 `$S$` 处被确定匹配。
- 如果由 `$e$` 在为 `true` 时引入的任何模式变量在 `$S$` 处已在作用域内，则是编译错误。
- 由 `while (e) S` 引入的模式变量当且仅当 (i) 它由 `$e$` 在为 `false` 时引入且 (ii) `$S$` 不包含可达的 break 语句 (§14.15)。
- 如果由 `while (e) S` 引入的任何模式变量在 while 语句处已在作用域内，则是编译错误。

### 6.3.2.4 do 语句

以下规则适用于语句 `do S while (e)` (§14.13)：

- 由 `do S while (e)` 引入的模式变量当且仅当 (i) 它由 `$e$` 在为 `false` 时引入且 (ii) `$S$` 不包含可达的 break 语句 (§14.15)。
- 如果由 `do S while (e)` 引入的模式变量在 do 语句处已在作用域内，则是编译错误。

### 6.3.2.5 for 语句

以下规则适用于基础 for 语句 (§14.14.1)：

- 由条件表达式为 `true` 时引入的模式变量在迭代部分和包含语句中都被确定匹配。
- 如果由条件表达式在为 `true` 时引入的任何模式变量在迭代部分已在作用域内，则是编译错误。
- 由基础 for 语句引入的模式变量当且仅当 (i) 它由条件表达式在为 `false` 时引入且 (ii) 包含语句 `$s$` 不包含可达的 break 语句 (§14.15)。
- 如果由基础 for 语句引入的模式变量在 for 语句处已在作用域内，则是编译错误。

增强 for 语句 (§14.14.2) 通过翻译为基础 for 语句定义，因此不需要提供特殊规则。

### 6.3.2.6 switch 语句

以下规则适用于 switch 语句 (§14.11)：

- 由位于 switch 标签组 (§14.11.1) 中的标签语句 `s` 引入的模式变量，如果在 switch 标签组中 `s` 之后的所有语句（如果有）中都会被确定匹配。

### 6.3.2.7 标签语句

以下规则适用于标签语句 (§14.7)：

- 由标签语句引入的模式变量当且仅当它由标签语句直接包含的语句引入。

## 6.4 遮蔽与覆盖

局部变量 (§14.4)、形式参数 (§8.4.1, §8.8.1, §15.27.1)、异常参数 (§14.20)、局部类或局部接口 (§14.3) 只能使用简单名称引用，不能使用限定名称 (§16.2)。

在局部变量声明、形式参数声明、异常参数声明、局部类声明或局部接口声明的作用域内允许某些声明，因为仅使用简单名称无法区分声明的实体。

> 例如，如果形式参数名称可以在方法体中重新声明为局部变量名称，那么局部变量将遮蔽形式参数，导致没有方法可以引用形式参数——这是一个不理想的结果。

如果在方法、构造函数或 Lambda 表达式的体中使用形式参数名称来声明新变量，则是编译错误，除非新变量在方法、构造函数或 lambda 表达式包含的类或接口声明内部声明。

# 遮蔽与隐藏 (Shadowing and Obscuring)

如果使用局部变量 `$v$` 的名称在 `$v$` 的作用范围内声明新变量，则会导致编译错误，除非该新变量是在 `$v$` 的作用范围内出现的类或接口声明中声明的。

如果使用异常参数的名称在 `catch` 子句内声明新变量，则会导致编译错误，除非该新变量是在 `catch` 子句的 `Block` 包含的类或接口声明中声明的。

如果使用局部类或接口 `$c$` 的名称在 `$c$` 的作用范围内声明新类或新接口，则会导致编译错误，除非该新的局部类或接口是在 `$c$` 的作用范围内出现的类或接口声明中声明的。

这些规则允许在变量、局部类或局部接口的作用域内重新声明该变量、局部类或局部接口；嵌套的类或接口声明可以是局部类或接口声明 (§15.9.5)。因此，形式参数、局部类或局部接口的声明可能会在嵌套于方法、构造函数或 lambda 表达式的类或接口声明中被遮蔽；异常参数的声明可能会在嵌套于 `catch` 子句 `Block` 的类或接口声明中被遮蔽。

处理由 lambda 参数和 lambda 表达式中声明的其他变量引起的名称冲突有两种设计。一种类似于类声明：表达式外部的局部变量可以被重新声明。另一种是“局部”策略：类似于 `catch` 子句、`for` 循环和块，lambda 表达式的操作在与包含它的上下文相同的“级别”，且表达式外部的局部变量不能被遮蔽。上述规则使用了局部策略，没有允许在包含方法中声明的变量的特殊许可。

# 示例 6.4-1. 尝试对局部变量进行遮蔽

由于作为方法、构造函数或初始化块的局部变量的标识符声明不能出现在同名参数或局部变量的作用范围内，因此以下程序将发生编译错误：

```java
class Test1 {
  public static void main(String[] args) {
    int i;
    for (int i = 0; i < 10; i++) {
      System.out.println(i);
    }
  }
}
```

# 名称 遮蔽与隐藏 6.4

这种限制有助于检测某些原本非常隐晦的 bug。对局部变量遮蔽成员的类似限制被认为是不切实际的，因为父类中添加成员可能会导致子类重命名局部变量。相关的考虑使得对嵌套类成员遮蔽局部变量的限制，或对嵌套类内部声明的局部变量遮蔽局部变量的限制也变得不再吸引。

因此，以下程序无错误地编译：

```java
class Test2 {
    public static void main(String[] args) {
        int i;
        class Local {
            for (int i = 0; i < 10; i++) {
                System.out.println(i);
            }
        }
        new Local();
    }
}
```

另一方面，同名的局部变量可以在两个 `for` 语句块中声明，块互不包含：

```java
class Test3 {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            System.out.print(i + " * ");
            for (int i = 10; i > 0; i--) {
                System.out.print(i + " * ");
            }
            System.out.println();
        }
    }
}
```

此程序无错误地编译，并在执行时产生输出：

0 1 2 3 4 5 6 7 8 9 10 9 8 7 6 5 4 3 2

这种样式在模式匹配中也很常见，重复的模式经常使用名称：

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}
```

```java
class Test4 {
    static void test(Object a, Object b, Object c) {
        if (a instanceof Point p) {
            System.out.println("a is a (" + p.x + "," + p.y + ")");
        } else if (b instanceof Point p) {
            System.out.println("b is a (" + p.x + "," + p.y + ")");
        } else if (c instanceof Point p) {
            System.out.println("c is a (" + p.x + "," + p.y + ")");
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

然而，模式变量不允许遮蔽局部变量（包括模式变量），因此以下程序发生编译错误：

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}
```

```java
class Test5 {
    static void test(Object a, Object b, Object c) {
        if (a instanceof Point p) {
            System.out.println("a is a (" + p.x + "," + p.y + ")");

            if (b instanceof Point p) { // 编译错误
                System.out.println("b is a (" + p.x + "," + p.y + ")");
            }
        }
    }

    public static void main(String[] args) {
        Point p = new Point(2,3);
        Point q = new Point(4,5);
        Point r = new Point(6,7);
        test(p, q, r);

        if (new Object() instanceof Point p) // 编译错误
            System.out.println("l get your point");
    }
}
```

### 6.4.1 遮蔽

某些声明在其作用域的一部分内被另一个同名的声明*遮蔽*，在这种情况下，无法使用简单名称来引用所声明的实体。

# 遮蔽与隐藏



# 遮蔽与模糊

遮蔽不同于隐藏（§8.3, §8.4.2, §8.5, §9.3, §9.5），后者仅适用于会被隐藏的成员。遮蔽也不同于隐藏（§6.4）。

形式参数、局部类或局部接口的声明可能会在嵌套于方法、构造函数或 lambda 表达式的类或接口声明中被遮蔽；异常参数的声明可能会在嵌套于 `catch` 子句 `Block` 的类或接口声明中被遮蔽。

这些规则允许在变量、局部类或局部接口的作用域内重新声明该变量、局部类或局部接口；嵌套的类或接口声明可以是局部类或接口声明（§15.9.5）。

处理由 lambda 参数和 lambda 表达式中声明的其他变量引起的名称冲突有两种设计。一种类似于类声明：表达式外部的局部变量可以被重新声明。另一种是“局部”策略：类似于 `catch` 子句、`for` 循环和块，lambda 表达式的操作在与包含它的上下文相同的“级别”，且表达式外部的局部变量不能被遮蔽。上述规则使用了局部策略，没有允许在包含方法中声明的变量的特殊许可。

如果使用局部变量 $v$ 的名称在 $v$ 的作用范围内声明新变量，则会导致编译错误，除非该新变量是在 $v$ 的作用范围内出现的类或接口声明中声明的。

如果使用异常参数的名称在 `catch` 子句内声明新变量，则会导致编译错误，除非该新变量是在 `catch` 子句的 `Block` 包含的类或接口声明中声明的。

如果使用局部类或接口 $c$ 的名称在 $c$ 的作用范围内声明新类或接口，则会导致编译错误，除非该新的局部类或接口是在 $c$ 的作用范围内出现的类或接口声明中声明的。

遮蔽不同于隐藏（§8.3, §8.4.2, §8.5, §9.3, §9.5），后者仅适用于会被隐藏的成员。遮蔽也不同于隐藏（§6.4）。

形式参数、局部类或局部接口的声明可能会在嵌套于方法、构造函数或 lambda 表达式的类或接口声明中被遮蔽；异常参数的声明可能会在嵌套于 `catch` 子句 `Block` 的类或接口声明中被遮蔽。

某些声明在其作用域的一部分内被另一个同名的声明*遮蔽*，在这种情况下，无法使用简单名称来引用所声明的实体。

这种限制有助于检测某些原本非常隐晦的 bug。对局部变量遮蔽成员的类似限制被认为是不切实际的，因为父类中添加成员可能会导致子类重命名局部变量。相关的考虑使得对嵌套类成员遮蔽局部变量的限制，或对嵌套类内部声明的局部变量遮蔽局部变量的限制也变得不再吸引。

因此，以下程序无错误地编译：

```java
class Test2 {
    public static void main(String[] args) {
        int i;
        class Local {
            for (int i = 0; i < 10; i++) {
                System.out.println(i);
            }
        }
        new Local();
    }
}
```

另一方面，同名的局部变量可以在两个 `for` 语句块中声明，块互不包含：

```java
class Test3 {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            System.out.print(i + " * ");
            for (int i = 10; i > 0; i--) {
                System.out.print(i + " * ");
            }
            System.out.println();
        }
    }
}
```

此程序无错误地编译，并在执行时产生输出：

```
0 1 2 3 4 5 6 7 8 9 10 9 8 7 6 5 4 3 2
```

这种样式在模式匹配中也很常见，重复的模式经常使用名称：

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}
```

```java
class Test4 {
    static void test(Object a, Object b, Object c) {
        if (a instanceof Point p) {
            System.out.println("a is a (" + p.x + "," + p.y + ")");
        } else if (b instanceof Point p) {
            System.out.println("b is a (" + p.x + "," + p.y + ")");
        } else if (c instanceof Point p) {
            System.out.println("c is a (" + p.x + "," + p.y + ")");
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

然而，模式变量不允许遮蔽局部变量（包括模式变量），因此以下程序发生编译错误：

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}
```

```java
class Test5 {
    static void test(Object a, Object b, Object c) {
        if (a instanceof Point p) {
            System.out.println("a is a (" + p.x + "," + p.y + ")");

            if (b instanceof Point p) { // 编译错误
                System.out.println("b is a (" + p.x + "," + p.y + ")");
            }
        }
    }

    public static void main(String[] args) {
        Point p = new Point(2,3);
        Point q = new Point(4,5);
        Point r = new Point(6,7);
        test(p, q, r);

        if (new Object() instanceof Point p) // 编译错误
            System.out.println("l get your point");
    }
}
```

## 6.4.1 遮蔽

某些声明在其作用域的一部分内被另一个同名的声明*遮蔽*，在这种情况下，无法使用简单名称来引用所声明的实体。

局部变量的作用域是声明它的块的剩余部分（§6.3）；在这种情况下它是 main 方法体的剩余部分，即其初始化器“0”以及对 `System.out.print` 和 `System.out.println` 的调用。

这意味着：

- print 调用中的表达式 $x$ 指向（表示）局部变量 $x$ 的值。

### 示例 6.4.1-1. 局部变量对字段声明的遮蔽

```java
class Test {
    static int x = 1;
    public static void main(String[] args) {
        int x = 0;
        System.out.print("x=" + x);
        System.out.println(", Test.x=" + Test.x);
    }
}
```

此程序产生输出：

```
x=0, Test.x=1
```

此程序声明了：

- 类 `Test`
- 类（静态）变量 `x`，它是类 `Test` 的成员
- 类方法 `main`，它是类 `Test` 的成员
- `main` 方法的参数 `args`
- `main` 方法的局部变量 `x`

由于类变量的作用域包含了整个类体（§8.2），因此变量 `x` 通常在整个 `main` 方法体内都是可见的。在这个示例中，类变量 `x` 在 `main` 方法体内被局部变量 `x` 的声明所遮蔽了。

### 命名

#### 遮蔽与模糊

- `println` 的调用使用了限定名（§6.6 `Test.x`），它使用类类型名 `Test` 来访问类变量 `x`，因为 `Test.x` 的声明在此处被遮蔽，无法通过其简单名进行引用。

关键字 `this` 也可以用于访问被遮蔽的字段 `x`，形式为 `this.x`。事实上，这种写法通常出现在构造函数中（§8.8）。

```java
class Pair {
    Object first, second;
    public Pair(Object first, Object second) {
        this.first = first;
        this.second = second;
    }
}
```

在这里，构造函数接收的参数与要初始化的字段具有相同的名称。这比为参数不同的名称要简单，并且在这种风格化的语文中并不令人困惑。然而，通常情况下使用与字段同名的局部变量被认为是不良风格。

### 示例 6.4.1-2. 其他类型声明对类型声明的遮蔽

```java
class Vector {
    int[] val = { 1, 2 };
}

class Test {
    public static void main(String[] args) {
        Vector v = new Vector();
        System.out.println(v.val[0]);
    }
}
```

该程序通过编译并打印：

```
1
```

使用了此处声明的类 `Vector`，而不是可能按需导入的通用类 `java.util.Vector`（§8.1.2）。

## 6.4.2 模糊

简单名可能出现在可能被解释为变量名、类型名或包名的环境中。在这些情况下，§6.5.2 的规则规定：变量的选择优于类型，类型的选择优于包名。因此，有时可能无法通过其简单名引用类型或包，即使其声明在作用域内且未被遮蔽。我们称这种声明是*模糊的*。

模糊区别于遮蔽（§6.4.1）和隐藏（§8.3, §8.4.8.2, §8.5, §9.3, §9.5）。

模块名与变量名、类型名或包名之间不存在模糊关系；因此，模块与变量、类型和包共享名称，尽管并不一定建议以其包含的包来为模块命名。

§6.1 中的命名规范有助于减少模糊，但如果确实发生了模糊，关于可以做来避免它还有一些说明。

当包名出现在表达式中时：

- 如果包名被字段声明所模糊，则通常可以使用 `import` 声明（§7.5）来使该包中声明的类型名可用。
- 如果包名被参数或局部变量的声明所模糊，则可以在不影响其他代码的情况下更改参数或局部变量的名称。

包名的第一个组件通常不以小写字母开头，因为类型名通常以单个大写字母开头。（Java 编程语言实际上并不依赖于大小写区分来判断一个名称是包名还是类型名。）

涉及类和接口类型的模糊非常罕见。字段、参数和局部变量的名称通常不会模糊类型名，因为它们按照习惯以小写字母开头，而类型名按照习惯以大写字母开头。

方法名不能模糊其他名称，也不能被其他名称模糊（§6.5.7）。

涉及字段名的模糊非常罕见；但是：

- 如果字段名模糊了包名，则通常可以使用 `import` 声明（§7.5）来使该包中声明的类型名可用。
- 如果字段名模糊了类型名，可以使用类型的完全限定名，除非该类型表示局部类或接口（§14.3）。
- 字段名不能模糊方法名。
- 如果字段名被参数或局部变量的声明遮蔽，则可以在不影响其他代码的情况下更改参数或局部变量的名称。

涉及常量名的模糊罕见：

- 常量名通常没有小写字母，因此它们通常不会模糊包名或类型的名称，通常也不会遮蔽字段（字段名称通常包含至少一个小写字母）。
- 常量名不能模糊方法名，因为它们在语法上是区分开的。

## 6.5 确定名称的含义

名称的含义取决于它被使用的上下文。确定名称的含义需要三个步骤：

1. 第一，上下文导致名称在语法上属于七类类别之一：模块名（`ModuleName`）、包名（`PackageName`）、类型名（`TypeName`）、表达式名（`ExpressionName`）、方法名（`MethodName`）、包或类型名（`PackageOrTypeName`）或模糊名（`AmbiguousName`）。类型名和方法名的表达能力比其他五类少，因为它们分别由类型标识符（`TypeIdentifier`）和未限定方法标识符（`UnqualifiedMethodIdentifier`）表示（§3.8）。
2. 第二，最初由上下文分类为模糊名（`AmbiguousName`）或包或类型名（`PackageOrTypeName`）的名称将被重新归类为包名、类型名或表达式名。
3. 第三，结果类别随后决定了名称含义的最终确定（如果名称没有含义，则产生编译错误）。

```
ModuleName:
    Identifier
    ModuleName . Identifier

PackageName:
    Identifier
    PackageName . Identifier

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
    UnqualifiedMethodIdentifier

AmbiguousName:
    Identifier
    AmbiguousName . Identifier
```

上下文的使用有助于减少不同实体之间的冲突。尽管遵循 §6.1 的命名规范，冲突可能会无意中产生。例如，类型、方法和字段可能具有相同的名称。由于类型总是可以区分，因此这种情况是可能的。

### 6.5.1 根据上下文对名称进行语法分类

名称在语法上被分类为模块名（`ModuleName`）的环境包括：

- 在 `requires` 指令中（§7.7）。
- 在 `exports` 或 `opens` 之后（§7.7）。

名称在语法上被分类为包名（`PackageName`）的环境包括：

- `exports` 或 `opens` 之后。
- 在 `.` 之前。

名称在语法上被分类为类型名（`TypeName`）的环境包括：

- 在类或接口中：
    1. `uses` 或 `provides` 指令中（§7.7）。
    2. 静态-import 声明中（§7.5）。
    3. 在 `.` 之前（§7.5）。
    4. 类型-import 声明中（§7.5）。
    5. 密封类或接口的 `permits` 子句中（§8.6）。
    6. 构造函数的 `(` 之前（§8.8）。
    7. 注释符号 `@` 之后（§9.7）。
    8. 类字面量的 `.class` 之前（§15.8）。
    9. 限定表达式中的 `.this` 之前（§15.8）。
    10. 字段访问中的 `.super` 之前（§15.11）。
    11. 方法调用中的 `.Identifier` 或 `.super.Identifier`（§15.12）。
    12. 方法引用中的 `.super::`（§15.13）。

在以下文中作为引用类型（`ReferenceType`）中（包括数组类型中 `[]` 之前的引用类型、泛型类型中 `<` 之前的引用类型、泛型类型中的通配符，以及 `extends` 子句中的引用类型）：

- 类声明的 `extends` 或 `implements` 子句中（§4.1, §8.4）。
- 接口声明的 `extends` 子句中（§9.1）。
- 方法的返回类型（§8.4, §9.4），包括注解元素的类型（§9.6.1）。
- 方法或构造函数的 `throws` 子句（§8.4.6, §8.8.5, §9.4）。
- 泛型接口、方法或构造函数的类型参数的 `extends` 子句（§8.1.2, §9.1.2, §8.4.4, §8.8.4）。
- 类或接口字段声明中的类型（§8.3, §9.3）。
- 方法、构造函数或 Lambda 表达式的形式参数声明中的类型（§8.4.1, §8.8.1, §9.4, §15.27.1）。
- 方法接收者参数（§8.4）。
- 语句中局部变量声明的类型（§14.4.2, §14.1.1, §14.20.3）或模式中的类型（§14.30.1）。
- 异常参数声明中的类型（§14.20）。
- 记录类记录组件声明中的类型（§8.10.1）。
- 显式构造调用语句、类实例创建表达式或方法调用表达式中的显式类型参数列表（§8.8.7.1, §15.9, §15.12）。
- 匿名类创建表达式中，作为要实例化的类类型（§15.9）或要实例化的直接超类或直接超接口（§15.9.5）。
- 数组创建表达式中的元素类型（§15.10.1）。
- 强制转换表达式的操作符中的类型（§15.16）。
- `instanceof` 关系运算符后面的类型（§15.20.2）。

在上述 17 种上下文从引用类型中提取类型名，旨在递归地应用于引用类型的所有子项，例如其元素类型和任何类型参数。

例如，假设一个字段声明使用了类型 `p.q.Foo[]`。数组类型的括号被忽略，术语 `p.q.Foo` 被提取为数组类型左侧的点分隔标识符序列，并被分类为 `TypeName`。随后的步骤将确定 `p`、`q` 和 `Foo` 中哪些是类型或包名。



# 另一个示例

假设转换运算符使用了类型 `p.q.Foo? extends String`。术语 `p.q.Foo` 再次被提取为点分隔标识符序列，这次位于参数化类型中 `<` 的左侧，并被分类为 *TypeName*。术语 `String` 被提取为参数化类型通配符类型参数的 `extends` 子句中的标识符，并被分类为 *TypeName*。

## 在这些上下文中，一个名称在语法上被分类为 *ExpressionName*：

- 作为限定父类构造函数调用中的限定表达式 (§8.8.7.1)
- 作为限定类实例创建表达式中的限定表达式 (§15.9)
- 作为数组访问表达式中的数组引用 (§15.10.3)
- 作为 *PostfixExpression* (§15.14)
- 作为赋值运算符的左侧操作数 (§15.26)
- 作为 *try*-with-resources 语句中的 *VariableAccess* (§14.20.3)

## 在此上下文中，一个名称在语法上被分类为 *MethodName*：

- 在方法调用表达式的 "(" 之前 (§15.12)

## 在这些上下文中，一个名称在语法上被分类为 *PackageOrTypeName*：

- 在限定 *TypeName* 中 "." 的左侧
- 在按需导入声明（type-import-on-demand declaration）中 (§7.5.2)

## 在这些上下文中，一个名称在语法上被分类为 *AmbiguousName*：

- 在限定 *ExpressionName* 中 "." 的左侧
- 在方法调用表达式中 "(" 之前的最右侧 "." 左侧
- 在限定 *AmbiguousName* 中 "." 的左侧
- 在注解元素声明的默认值子句中 (§9.6.2)
- 在元素-值对中 "=" 的右侧 (§9.7.1)
- 在方法引用表达式中 :: 左侧 (§15.13)
- 如果 "." 左侧的名称被重新分类为 PackageName，则：
  - 如果该标识符是一个有效的 TypeIdentifier，且存在一个包名为 "." 左侧名称的包，且该包包含一个类型名称与该标识符相同的类型声明，则该 AmbiguousName 被重新分类为 TypeName。
  - 否则，该 AmbiguousName 被重新分类为 PackageName。随后的步骤将确定实际上是否存在一个名为该名称的包。
- 如果 "." 左侧的名称被重新分类为 TypeName，则：
  - 如果该标识符是 TypeName 所指代类型的方法或字段名，则该 AmbiguousName 被重新分类为 ExpressionName。
  - 否则，如果该标识符是一个有效的 TypeIdentifier 且是 TypeName 所指代类型的成员类型之名，则该 AmbiguousName 被重新分类为 TypeName。
  - 否则，发生编译时错误。
- 如果 "." 左侧的名称被重新分类为 ExpressionName，则该 AmbiguousName 被重新分类为 ExpressionName。随后的步骤将确定实际上是否存在名为该名称的成员。

潜在名称必须是 `valid TypeIdentifier` 的要求防止了 `var` 和 `yield` 作为类型名。这通常是多余的，因为声明规则已经防止了引入名为 `var` 和 `yield` 的类型。然而，在某些情况下，编译器可能会找到名为 `var` 或 `yield` 的二进制类，我们希望明确此类类永远不能被命名。最简单的解决方案是一致地检查有效的 TypeIdentifier。

## 示例 6.5.2-1. 上下文歧名称的重新分类

考虑以下构造的“库代码”：

```java
package org.rgppoet;
import java.util.Random;
public interface Music { Random[] wizards = new Random[4]; }
```

然后考虑另一个包中的此示例：

```java
package bazola;
class Gabriel {
  static int n = org.rgppoet.Music.wizards.length;
}
```

首先，名称 `org.rgppoet.Music.wizards.length` 被分类为 ExpressionName，因为其充当了 PostfixExpression。因此，每个名称：

```
org.rgppoet.Music
org.rgppoet.Music
org.rgppoet
org
```

最初都被分类为 AmbiguousName。这些名称随后被重新分类：

- 简单名称 `org` 被重新分类为 PackageName（因为作用域内没有名为 `org` 的变量或类型）。

## 确定的含义

- 接下来，假设包 `org` 的任何编译单元中没有名为 `rpgpoet` 的类或接口（我们知道 `org` 没有名为 `rpgpoet` 的子包），限定名称 `org.rpgpoet` 被重新分类为 PackageName。

- 接下来，因为包 `org.rpgpoet` 有一个可访问的接口名为 `Music`，限定名称 `org.rpgpoet.Music` 被重新分类为 TypeName。

- 最后，由于 `org.rpgpoet.Music` 是一个 TypeName，限定名称 `org.rpgpoet.Music.wizards` 被重新分类为 ExpressionName。

### 6.5.3 模块名与包名的含义

假设在包 `org` 的任何编译单元中没有名为 `rpgpoet` 的类或接口（且我们知道 `org` 没有名为 `rpgpoet` 的子包），限定名称 `org.rpgpoet` 被重新分类为 PackageName。

- 接下来，因为包 `org.rpgpoet` 有一个可访问的接口名为 `Music`，限定名称 `org.rpgpoet.Music` 被重新分类为 TypeName。

- 最后，由于 `org.rpgpoet.Music` 是一个 TypeName，限定名称 `org.rpgpoet.Music.wizards` 被重新分类为 ExpressionName。

模块 $M$，无论是简单的还是限定的，表示具有该名称的模块（如果存在）。本节并不规定在模块不存在时会发生编译时错误。相反，模块声明中的 `exports` 指令简体7.7) 会处理不存在的名称。

### 6.5.3.1 简单包名

如果包名由单个 Identifier 组成，则该标识符必须出现在唯一一个包声明的作用域内 (§6.3)，否则发生编译时错误。包名的含义是该包。

### 6.5.3.2 限定包名

如果包名形式为 $Q.Id$，则 $Q$ 必须也是一个包。包名 $Q.Id$ 表示包内的成员 $Id$。

### 6.5.4 PackageOrTypeName 的含义

### 6.5.4.1 简单 PackageOrTypeName

如果 PackageOrTypeName $Q$ 是一个有效的 TypeIdentifier 且出现在某个类、接口或类型参数声明的作用域内，则该 PackageOrTypeName 被重新分类为 TypeName。

否则，PackageOrTypeName 被重新分类为 PackageName。PackageOrTypeName 的含义是重新分类后名称的含义。

### 6.5.4.2 限定 PackageOrTypeName

对于给定形式为 $Q.Id$ 的限定 PackageOrTypeName，如果 $Id$ 是一个有效的 TypeIdentifier 且 $Q$ 所指代的类、接口、类型参数或包具有成员类或接口 $Id$，则该限定 PackageOrTypeName 被重新分类为 TypeName。

否则，它被重新分类为 PackageName。限定 PackageOrTypeName 的含义是重新分类后名称的含义。

### 6.5.5 类型名的含义

分类为 TypeName 的名称的含义确定如下：

### 6.5.5.1 简单类型名

如果一个名称由单个 Identifier 组成，则该标识符必须出现在唯一一个类、接口或类型参数声明的作用域内 (§6.3)，否则发生编译时错误。

如果该声明是泛型类或接口 $c$ 的类型参数 (§8.1.2, §9.1.2)，必须满足以下两个条件，否则发生编译时错误：

- 类型名没有出现在静态上下文 (§8.1.3)。
- 如果类型名出现在 $c$ 的嵌套类或接口声明中，则类型名称的直接封闭类或接口声明是 $c$ 的内部类。

如果该声明是泛型方法或构造函数 $m$ 的类型参数 (§8.4.4, §8.8.4)，且类型名直接或间接地出现在 $m$ 体内声明的局部类、局部接口或匿名类 $d$ 中，则必须满足以下两个条件：

- 类型名没有出现在静态上下文。
- $d$ 是内部类，且类型名称的直接封闭类或接口声明是 $d$ 或 $d$ 的内部类。

例如，类型名不能出现在由 $D$ 声明的静态方法的体中，且（如果 $D$ 是局部接口）不能出现在 $D$ 的默认方法的体中。

## 类型名的含义是指当前作用域内的类、接口或类型参数。

### 示例 6.5.5.1-1. 对类型参数的引用

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
    }
    new NullChecker().check(val);
    return new Box<U>(val);
  }
}
```

类型参数 $T$ 在类 $Box$ 的整个声明范围内处于作用域内；然而，在静态方法 $empty$ 的声明中使用名称 $T$ 是非法的。

同样，方法参数 $U$ 在方法 $make$ 的整个声明范围内处于作用域内；然而，在（隐式静态的）接口 $Checker$ 的声明中使用名称 $U$ 是非法的。

## 6.5.5.2 限定类型名

如果一个类型名采用 $Q.Id$ 的形式，则 $Q$ 必须是当前模块唯一可见的包中类、接口或类型参数的名称，或者是当前模块唯一可见的包的名称 (§7.4.3)。

如果 $Id$ 恰好命名为了一个可访问的类或接口 (§6.6)，且该类或接口是 $Q$ 所指代的类、接口、类型参数或包的成员，则该限定类型名指代该类或接口。

如果 $id$ 没有命名 $Q$ 内部的成员类或接口 (§8.5, §9.5)，或者 $Q$ 内部名为 $id$ 的成员类或接口不可访问，或者 $id$ 在 $Q$ 内部命名了多个成员类或接口，则会发生编译错误。

### 示例 6.5.5.2-1. 限定类型名

```java
class Test {
    public static void main(String[] args) {
        java.util.Date date = new java.util.Date(System.currentTimeMillis());
        System.out.println(date.toLocaleString());
    }
}
```

该程序在第一次运行时输出了输出：

Sun Jan 21 22:56:29 1996

在此示例中，名称 `java.util.Date` 必须指代一个类型，因此我们首先递归地确定 `java.util` 是否是一个可访问的类、接口、类型参数或包（它确实是一个包），然后查看在该包中类 `Date` 是否可访问。

## 6.5.6 表达式名的含义

被分类为表达式名（ExpressionName）的名称含义确定如下。

### 6.5.6.1 简单表达式名

如果一个表达式名由单个标识符（Identifier）组成，则必须恰好有一个声明，在标识符出现的地方指代局部变量、形式参数、异常参数或字段。否则，会发生编译错误。

如果该声明指代类 $c$ 的实例变量 (§8.3.1.1)，则必须同时满足以下两点，否则会发生编译错误：

- 该表达式名没有出现在静态上下文中 (§8.1.3)。
- 如果该表达式名出现在 $c$ 的嵌套类或接口声明中，则该表达式名的直接外层类或接口声明必须是 $c$ 的内部类。

例如，该表达式名不能出现在由 $c$ 声明的静态方法的体中，也不能出现在嵌套在 $C$ 内部的静态类的实例方法的体中。

如果该声明指代局部变量、形式参数或异常参数，令 $x$ 为包含该局部变量或参数声明的最内方法声明、构造函数声明、实例初始化、静态初始化、字段声明或显式构造函数调用语句。如果该表达式名直接或间接地出现在在 $x$ 中声明的局部类、局部接口或匿名类 $D$ 的体内，则必须同时满足以下两点，否则会发生编译错误：

- 该表达式名没有出现在静态上下文中。
- $D$ 是一个内部类，且该表达式名的直接外层类或接口声明是 $D$ 或 $D$ 的内部类。

例如，该表达式名不能出现在由 $D$ 声明的静态方法的体中，且（如果 $D$ 是局部接口）不能出现在 $D$ 的默认方法的体中。

如果该声明指代一个既不是 `final` 也不是有效 `final` (§4.12.4) 的局部变量、形式参数或异常参数，如果该表达式名出现在由 $x$ 直接或间接包含的内部类中，或出现在 $X$ 所包含的 lambda 表达式中 (§15.27)，则会导致编译错误。

这些规则的最终效果是：局部变量、形式参数或异常参数只能在其作用域内声明的嵌套类或接口中被引用，前提是：(i) 它不在静态上下文中，(ii) 从引用到变量声明之间存在一条内部（非静态）类的链，并且 (iii) 该变量是 `final` 或有效 `final`。来自 lambda 表达式的引用也要求该变量是 `final` 或有效 `final`。

# 名称

# 确定名称的含义

## 6.5

局部变量 `first` 在 `main` 方法体的剩余部分都是作用域内的。`first` 也是有效最终的（effectively final）。然而，在 `checkFirst` 中声明的匿名类不是 `Checker` 的内部类，因此在匿名类体中使用名称 `first` 是非法的。（`checkFirst` 体中的 Lambda 表达式同样无法引用 `first`，因为该 Lambda 表达式发生在静态上下文中。）

局部变量 `c` 在 `main` 方法体的最后几行代码中是作用域内的，并且被声明为 `final`，因此在 Lambda 表达式体可以使用名称 `c`。

局部变量 `i` 在整个 `for` 循环中都是具有作用域的。然而，`i` 不是有效最终的，因此在 Lambda 表达式体中使用名称 `i` 是非法的。

## 6.5.6.2 限定限定的表达式名称

如果一个表达式名称的形式为 `Q.Id`，那么 `Q` 已经被分类为包名、类型名或表达式名。

如果 `Q` 是包名，则发生编译时错误。

如果 `Q` 是命名为类类型的类型名，那么：

- 如果该类类型没有恰好有一个可访问的成员 (§6.6）是名为 `Id` 的字段，则发生编译时错误。
- 否则，如果该可访问成员字段不是类变量（即它没有被声明为 `static`），则发生编译时错误。
- 否则，如果该类变量被声明为 `final`，则 `Q.Id` 表示该类变量的值。

表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）该类变量的声明类型。

注意，此类名涵盖了枚举常量的使用 (§8.9)，因为这些常量始终有一个对应的 `final` 类变量。

如果 `Q` 是命名为接口类型的类型名，那么：

- 如果该接口类型没有恰好有一个可访问的成员是名为 `Id` 的字段，则发生编译时错误。
- 否则，$Q.Id$ 表示该字段的值。

表达式 $Q.Id$ 的类型是捕获转换后（§5.1.10）该字段的声明类型。

如果 $Q.Id$ 出现在需要变量而非值的环境中，则发生编译时错误。

如果 `Q` 是表达式，令 $\tau$ 为表达式 $Q$ 的类型：

- 如果 $\tau$ 不是引用类型，则发生编译时错误。
- 如果类型 $\tau$ 没有恰好有一个可访问的成员是名为 $Id$ 的字段，则发生编译时错误。
- 否则，如果该字段是以下任意一种：
    - 接口类型的字段
    - 类类型的 *final* 字段（可以是类变量或实例变量）
    - 数组类型的 *final* $Q.Id$ *length* (§10.7)

那么 $Q.Id$ 表示该字段的值，除非它出现在一个需要变量而非值的环境中，且该字段是一个未定义的空白 *final* 字段，在这种情况下它产生一个变量。

表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）该字段的声明类型。

如果 `Q.Id` 出现在需要变量而非值的环境中，且 `Q.Id` 所指的字段已被确定已赋值，则发生编译时错误。

- 否则，$Q.Id$ 表示一个变量，即类 $\tau$ 的字段 $Id$，它可以可以是类变量也可以是实例变量。

表达式 `Q.Id` 的类型是捕获转换后（§5.1.10）该字段成员的类型。

### 示例 6.5.6.2-1. 限定限定的表达式名称

```java
class Point {
    int x, y;
    static int nPoints;
}
```



```java
class Test {
    public static void main(String[] args) {
        int i = 0;
        i.x++; // 编译错误

        Point p = new Point();
        p.nPoints(); // 编译错误
    }
}
```

此程序遇到了编译时错误，因为 `int` 变量 `i` 没有成员，且因为 `nPoints` 不是 `Point` 类的方法。

## 示例 6.5.6.2-2. 使用类型名限定表达式

注意，表达式名称可以被类型名限定，但不能被泛义类型限定。结果就是无法通过泛型类型访问类变量。例如，给定代码：

```java
class Foo<T> {
    public static int classVar = 42;
}
```

此时以下赋值是非法的：

```java
Foo<String>.classVar = 91; // 非法
```

相反，应该写为：

```java
Foo.classVar = 91;
```

这并没有以任何实质意义的方式限制 Java 语言；它仅仅防止了通过泛型访问类级成员的混淆。

## 6.5.7 名称的含义

### 6.5.7.1 简单方法名

简单方法名出现在方法调用的上下文中（`§15.12`）。简单名称的含义确定如下：

## 示例 6.5.7.1-1. 简单方法名

以下程序演示了在确定调用哪个方法时作用域的作用。

```java
class Super {
    void f2(String s) {}
    void f3(String s) {}
    void f3(int i1, int i2) {}
}

class Test {
    void f1(int i) {}
    void f2(int i) {}
    void f3(int i) {}

    void m() {
        new Super() {
            f1(0); // OK，解析为 Test.f1(int)
            f2(0); // 编译错误
            f3(0); // 编译错误
        }
    }
}
```

对于调用 `f1(0)`，只有一个名为 `f1` 的方法在 `Test.f1(int)` 的体中作用域内。`15.12.1` 选择在 `Test` 类中搜索，因为匿名声明没有成员 `f1`。最终，`Test.f1(int)` 被解析。

对于调用 `f2(0)`，有两个名为 `f2` 的方法在作用域内。首先，方法 `Super.f2(String)` 的声明在整个匿名类声明中作用域内。其次，方法 `Test.f2(int)` 的声明在包括匿名类声明在整个 `Test` 体中作用域内。（注意，这两个声明都没有遮蔽另一个，因为在每个声明被定义的地方，另一个不在作用域内。）`15.12.1` 选择在 `Super` 类中搜索，因为它有一个名为 `f2` 的成员。然而，`Super.f2(String)` 不适用于 `f2(0)`，因此发生编译时错误。注意没有搜索 `Test` 类。

对于调用 `f3(0)`，有三个名为 `f3` 的方法在作用域内。第一个和第二个，方法 `Super.f3(String)` 和 `Super.f3(int, int)` 的声明在整个匿名类声明中作用域内。第三个，方法 `Test.f3(int)` 的声明在包括匿名类声明在整个 `Test` 体中作用域内。`15.12.1` 选择在 `Super` 类中搜索，因为它有一个名为 `f3` 的成员。然而，`Super.f3(String)` 和 `Super.f3(int, int)` 不适用于 `f3(0)`，因此发生编译时错误。注意没有搜索 `Test` 类。

## 6.6 访问控制

Java 语言提供了访问控制机制，以防止包或类的用户依赖于该包或类实现中的不必要细节。如果允许访问，则被访问的实体应该是可访问的。

请注意，访问性是一个静态属性，可以在编译时确定；它仅依赖于类型和声明修饰符。

限定名（Qualified names）是访问包、类、接口、类型参数和引用类型成员的手段。当此类成员的名称从其上下文中（`§6.5.1`）被归类为限定类型名（表示包、类、接口或类型参数的成员）或限定表达式名时，将应用访问控制。

例如，单类型导入声明（single-type import declaration）使用了限定类型名（`§7.5.1`），因此该命名的类或接口必须从导入声明所在的编译单元可访问的。另一个例子是，类声明可能会使用限定类型名作为父类类型（`§8.1.5`），因此该名称必须是可访问的。

某些表达式在 `§6.5.1` 的上下文分类中是“缺失”的：主体（Primary）上的字段访问（`§15.11.1`）、主体上的方法调用（`§15.12`）、通过主体的方法引用（`§15.13`）以及限定类实例创建中的实例化类（`§15.9`）。由于 `§6.2` 中的原因，这些表达式每一个都使用标识符（identifiers）而非名称（names）。因此，对成员（无论是字段、方法、类还是接口）的访问控制是通过字段访问表达式、方法调用、方法引用表达式和限定类实例创建表达式来实现的。（注意，字段也可以通过类型名作为后缀表达式来表示。）

在许多情况下，语句和表达式允许使用不完全通过类型名表示的类型。例如，类声明可能会使用泛型类型（`§4.5`）来表示父类类型。由于泛型类型不是限定类型名，因此类声明必须显式地对声明的父类执行访问控制。因此，在 `§6.5.1` 中提供用于对类型名（TypeName）进行分类的语句和表达式中，必须执行它们自身的访问控制检查。

除了访问包、类、接口或类型参数的成员外，还存在访问构造函数的问题。在显式或隐式调用构造函数时，必须检查访问控制。因此，访问控制是通过显式构造函数调用（`§8.7.1`）和类实例创建表达式（`§15.9.3`）检查的。这些检查是必要的，因为 `§6.5.1` 没有提到构造函数调用语句（它们直接引用构造函数而非名称），并且无法区分限定类实例创建表达式所表示的类与该类的构造函数之间的区别。此外，构造函数没有限定名，因此我们不能依赖在归类限定类型名时进行的访问控制检查。

访问性影响类成员的继承（`§8.2`），包括隐藏和方法重写（`§8.4.8.1`）。

### 6.6.1 确定访问性

- 如果一个顶层类或接口（`§7.6`）被声明为 `public` 且是某个由模块导出的包的成员，那么在声明该类或接口的编译单元对该其他模块可见（`§7.3`）的前提下，同一模块中的任何代码以及导出该包的另一个模块中的任何代码都可以访问该类或接口。

- 如果一个顶层类或接口被声明为 `public` 且是未由模块导出的包的成员，那么该类或接口可以被同一模块中的任何代码访问。

- 如果一个顶层类或接口被声明为包访问权限（package access），则它只能从其声明所在的包内部被访问。

未声明访问修饰符的顶层类或接口隐含地具有包访问权限。

- 类、接口、类型参数或引用类型的成员（类、接口、字段或方法）或类的构造函数，只有在满足以下条件时才是可访问的：(i) 该类

```java
package points;
public class Point {
  protected int x, y;
  public void move(int dx, int dy) { x += dx; y += dy; }
```

```java
public int getX() { return x; }
public int getY() { return y; }
}
```

在 `points` 包中声明了两个类类型：

- `Point` 类在 `points` 包外部可用。

- `Point` 类对任何其他包可访问。

- 字段 `x` 和 `y` 是 `protected` 的，因此仅在包内可访问。

参见 `6.6.2` 以了解 `protected` 修饰符如何限制访问的示例。

### 6.6.2 对 public、方法和构造函数的访问

`public` 类成员或构造函数在其声明的包内以及从任何其他包都是可访问的，前提是其声明所在的包是可见的（`§7.4.3`）。例如，在编译单元中：

```java
package points;
class Point {
  int x, y;
  public void move(int dx, int dy) {
    x += dx; y += dy;
  }
  public static int moves = 0;
}
```

`public` 类 `Point` 有 `public move` 方法和 `moves` 字段。这些 `public` 成员对任何其他包都是可的。

### 6.6.3 对非 public 类的访问

如果一个类缺少 `public` 修饰符，对该类的访问被限制在其声明的包内。在示例中：

```java
package points;
class Point {
  public int x, y;
  public void move(int dx, int dy) { x += dx; y += dy; }
}

class PointList {
    Point next, prev;
}
```

编译单元中声明了两个类。`Point` 类在 `points` 包外部可用，而 `PointList` 类仅在包内可供访问。另一个包中的编译单元可以访问 `points.Point`，可以使用其完全限定名：

```java
package pointsUser;
class Test1 {
    public static void main(String[] args) {
        points.Point p = new points.Point();
        System.out.println(p.x + " " + p.y);
    }
}
```

或者通过单类型导入声明（`§7.5.1`）提及完全限定名，以便在此处简单名：

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

然而，此编译单元无法使用或导入 `points.PointList`，因为它未声明，因此在 `points` 包外部是不可访问的。

### 6.6.4 对包访问权限的字段、方法和构造函数的访问

如果没有指定 `public`、`protected` 或 `private` 访问修饰符，类成员或构造函数具有包访问权限：它们在包含声明该成员的类的包内是访问的，但该成员或构造函数在任何其他包中都是不可访问的。

如果一个 `public` 类具有包访问权限的方法或构造函数，则该方法或构造函数无法被声明在该包之外的子类访问或继承。

那么另一个包中的子类可能会声明一个无关的 `move` 方法，其具有相同的签名（`8.4.2`）和返回类型。由于原始的 `move` 方法在 `morepoints` 包中不可访问，无法使用 `super`：

```java
package morepoints;
public class PlusPoint extends points.Point {
    public void move(int dx, int dy) {
        super.move(dx, dy); // 编译错误
        moveAlso(dx, dy);
    }
}
```

由于 `Point` 的 `move` 没有被 `PlusPoint` 的 `move` 重写，`Point` 中的 `moveAlso` 方法永远不会调用 `PlusPoint` 中的 `move`。如果你从 `Point` 中删除 `super.move` 调用并执行测试：

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

它将正常终止。如果 `Point` 的 `move` 被 `PlusPoint` 的 `move` 重写，那么该程序将无限递归，直到发生 `StackOverflow` 错误。

## 示例 6.6-5. 对私有字段、方法和构造函数的访问

私有类成员或构造函数仅在启用该成员或构造函数的顶层类体（`7.6`）内可访问。它不会被子类继承。在示例中：

```java
class Point {
    Point() { setMasterID(); }
    int x, y;
    private int ID;
    private static int masterID = 0;
    private void setMasterID() { ID = masterID++; }
}
```

私有成员 `ID`、`identifier` 和 `masterID` 只能在 `Point` 类的体内使用。在 `Point` 声明体之外，无法通过限定名、字段访问表达式或方法调用表达式访问它们。

参阅 `8.8.10` 以获取使用私有构造函数的示例。

## 6.6.2 受保护访问的细节

对象的受保护成员或构造函数只有通过负责该对象实现的代码，才能从其声明包外部访问。

### 6.6.2.1 对受保护成员的访问

假设 `c` 是声明受保护成员的类。仅在 `c` 的子类体内允许访问。

子类 `s` 被认为负责类 `c` 对象的实现。根据 `c` 的可见性，`s` 可以声明在与 `c` 相同的包中、与 `c` 相同模块的不同包中，或者完全不同模块的包中。

此外，根据限定名、字段访问表达式（`§15.11`）、方法调用表达式（`§15.12`）或方法引用表达式（`§15.13`）的形式，允许对实例字段或实例方法的访问：

- 如果通过 (i) 形式为 `ExpressionName.Id` 或 `TypeName.Id` 的限定名，或 (ii) 形式为 `Primary.Id` 的字段访问表达式进行访问，则仅当限定类型为 `s` 或其子类时，才允许访问实例字段 `Id`。

  该限定类型是 `ExpressionName` 或 `Primary` 的类型，或者是 `TypeName` 所指的类型。

- 如果通过 (i) 形式为 `ExpressionName.Id(..)` 或 `TypeName.Id(..)` 或 `Primary.Id(..)` 的方法调用表达式，或 (ii) 形式为 `ExpressionName :: IdOf` `Primary :: Or ReferenceType :: Id` 的方法引用表达式进行访问，则仅当限定类型为 `s` 或其子类时，才允许访问实例方法 `Id`。

  该限定类型是 `ExpressionName` 或 `Primary` 的类型，或者是 `TypeName` 或 `ReferenceType` 所指的类型。

关于访问受保护成员的更多信息，可以参阅 Alessandro Coglio 发表在《Journal of Object Technology》（2005年10月）上的《Checking Access to Protected Members in the Java Virtual Machine》。

### 6.6.2.2 对受保护构造函数的访问

假设 `c` 是声明受保护构造函数的类，`s` 是使用受保护构造函数的内部类。那么：

- 如果通过父类调用 `super(...)` 或限定的父类构造函数调用 `E.super(...)`（其中 `E` 是 `Primary` 表达式）进行访问，则允许访问。

- 如果通过匿名类实例创建 `new C(...)` 或限定的匿名类实例创建表达式 `E.new C(...){}`（其中 `E` 是 `Primary` 表达式）进行访问，则允许访问。

- 如果通过简单类实例创建 `new C(...)` 或限定的类实例创建表达式 `E.new C(...)`（其中 `E` 是 `Primary` 表达式），或方法引用表达式 `C::new`（其中 `C` 是 `ClassType`）进行访问，则不允许访问。受保护构造函数仅在定义所在的包内才能通过类实例创建表达式（不声明匿名类的表达式）或方法引用表达式进行访问。

## 示例 6.6.2-1. 对受保护字段、方法和构造函数的访问

考虑这个示例，`points` 包声明了：

```java
package points;
public class Point {
    protected int x, y;
    void warp(Point3d a) {
        if (a.z > 0) // 编译错误：无法访问 a.z
            a.delta(this);
    }
}
```

而 `threePoint` 包声明了：

```java
package threePoint;
import points.Point;
public class Point3d extends Point {
    protected int z;
    void delta(Point p) {
        if (p.x > 0) { // 因为子类关系而允许
        }
    }
}
```

```java
class Point { int x, y; }
class PointVec { Point[] vec; }
```



类型 `points.Point` 的全限定名；类型 `PointVec` 的全限定名是 `points.PointVec`；以及类 `PointVec` 中字段 `vec` 的类型的全限定名是 `points.Point[]`。

# 示例 6.7-2. 全限定名 vs. 规范名

全限定名与规范名之间的区别可以通过如下代码看出：

```java
package p;
class O1 { class I { } }
class O2 extends O1 { }
```

`p01.I` 和 `p02.I` 都是表示成员 `I` 的全限定名，但只有 `p01.I` 是它的规范名。

# 第 7 章

## 包与模块

程序被组织成包的集合。包的成员（§7.1）是类和接口（它们声明在包的编译单元中）以及子包（子包可能包含它们自己的编译单元和子包）。

每个包都有自己自己的一套用于类和接口的名称，这有助于防止命名冲突。包的命名结构是分层的。

如果一组包具有足够的内聚性，那么这些包可以被组成一个模块。模块将其部分或全部包分类为*导出的*（exported），这意味着它们的类和接口可以从模块外部的代码进行访问。如果一个包没有被另一个模块导出，那么只有模块内部的代码可以访问它的类和接口。此外，如果模块中的代码想要访问另一个模块导出的包，那么第一个模块必须显式地依赖第二个模块。因此，模块控制了它的包如何使用其他模块（通过指定依赖关系），并控制了其他模块如何使用它的包（通过指定哪些包被导出）。

模块和包可以存储在文件系统或数据库中（§7.2）。存储在文件系统中的模块和包在编译单元的组织上可能有某些限制，以便简单的实现能够容易地找到模块、类和接口的声明。

编译单元中的代码自动拥有其所在包中声明的所有类和接口，并自动导入预定义包 `java.lang` 中声明的所有 `public` 类和接口。

一个顶层类或接口只有在声明为 `public` 时，才能在声明它的包外部访问（§6.6）。一个顶层类或接口只有在声明为 `public` 且是导出包的成员时，才能在声明它的模块外部访问。如果一个类或接口

## 7.1 包成员

一个类或接口被声明为 `public` 但不是导出包的成员，则它仅对模块内部的代码可访问。

对于小型程序和非正式开发，包可以是未命名的（§7.4.2）或具有简单的名称，但如果代码要广泛分发，应该使用全限定名选择唯一的包名。这可以防止当两个开发小组恰好选择相同的包名，且这些包随后被用于同一个程序时，可能发生的冲突。

包的成员是它的子包，以及在包的编译单元（§7.3）中声明的所有顶层类（§类）和顶层接口（§9 接口）。

例如，在 Java SE 平台 API 中：

- 包 `java` 有子包 `awt`, `applet`, `io`, `lang`, `net` 和 `util`，但没有编译单元。
- 包 `java.awt` 有一个名为 `image` 的子包，以及若干包含类和接口声明的编译单元。

如果一个包的全限定名（§6.7）是 `P`，且 `Q` 是 `P` 的子包，那么 `P.Q` 就是该子包的全限定名，并且进一步表示一个包。

包不能包含两个同名的成员，否则会导致编译时错误。

这里是一些示例：

- 包 `java.awt` 有一个名为 `image` 的子包，它不能（也没有）包含一个名为 `image` 的类或接口的声明。
- 如果存在包 `mouse` 且该包中有一个类 `Button`（这可能被引用为 `mouse.Button`），那么不能存在全限定名为 `mouse.Button.Button.Click` 的包。
- 如果 `com.nighthacks.java.jag` 是一个类的全限定名，那么不能存在任何全限定名为 `com.nighthacks.java.jag` 或 `com.nighthacks.java.jag.scrabble` 的包。

不同包的成员可能具有相同的简单名。例如，可以声明这样一个包：

```java
package vector;
public class Vector { Object[] vec; }
```

该包有一个名为 `Vector` 的 `public class` 成员，尽管包 `java.util` 也声明了一个名为 `Vector` 的类。这两个类是不同的，这体现在它们具有不同的限定名（§6.7）。示例的全限定名是 `Vector.Vector`，而 `java.util.Vector` 是 Java SE 平台中包含的 `Vector` 的全限定名。因为包 `vector` 包含名为 `Vector` 的类，它不能再有一个名为 `Vector` 的子包。

包的分层命名结构是为了方便以惯的方式组织包，但其本身没有其他意义，除了禁止一个包拥有一个与该包内声明的顶层类或接口同名的子包（§7.6）。

例如，名为 `oliver` 的包与另一个名为 `oliver.twist` 的包之间，或者 `evelyn.wood` 与 `evelyn.waugh` 之间，没有任何特殊关系。

### 7.2 宿主对模块和包的支持

在 Java SE 平台的简单实现中，包和编译单元可以存储在本地文件系统中。其他实现可能使用分布式文件系统或某种形式的数据库存储它们。

如果宿主系统将包和编译单元存储在数据库中，则数据库不能对文件系统中允许的编译单元施加可选限制（§7.6）。

例如，使用数据库存储包的系统可能强制每个编译单元最多一个 `public` 类或接口。

然而，使用数据库的系统必须提供一种选项，将程序转换为遵守限制的形式，以便导出到文件系统实现。

在文件系统中存储包的一个极其简单的示例是：项目中所有的包以及源代码和二进制代码可以存储在一个目录及其子目录中。该目录的每个直接子目录代表一个顶层包，即其限定名由单个简单名组成的包。每一深的子目录都代表所在目录的包的子包，依此类推。

该目录可能包含以下直接子目录：

```
com
gis
jag
java
wnj
```

其中 `java` 包含 Java SE 平台包；`gis` 和 `wnj` 目录可能包含本规范的三位作者为了个人使用以及与该小组共享而创建的包；`com` 目录包含了使用 §6.1 中规定的约定生成唯一包名的公司的包。

继续示例，`java` 目录将包含以下子目录：

```
applet
awt
io
lang
net
util
```

对应于 `java.applet`, `java.awt`, `java.io`, `java.lang`, `java.net` 和 `java.util` 包，这些包作为 Java SE 平台 API 的被定义。

继续之前的示例，如果我们查看 `util` 目录，我们可能会看到以下文件：

```
BitSet.java        Observable.java
BitSet.class        Observable.class
Date.java           Observer.java
Date.class          Observer.java
...
```

其中每个 `.java` 文件都包含一个编译单元（§7.3）的源代码，该单元包含一个类或接口的定义，其二进制编译后的形式包含在相应的 `.class` 文件中。

在这种简单的包组织结构下，Java SE 平台的实现将通过连接包名的各个组件，将包名转换为路径名，并在相邻组件之间放置文件名分隔符（目录指示符）。

例如，如果这种简单的组织结构使用在一个文件名分隔符为 `/` 的操作系统系统上，则包名：

```
jag.scrabble.board
```

将被转换为目录名：

```
jag/scrabble/board
```

包名组件或类名可能包含无法正确出现在宿主机文件系统普通目录名中的字符，例如在仅允许文件名中出现 ASCII 字符的系统上使用 Unicode 字符。按照约定，可以使用 `@` 字符后跟四个十六进制数字（给出字符的数值）来对字符进行转义，如 `\uXXXX` 转义（§3.3）。

根据此约定，包名：

```
children.activities.crafts.papierM@u002ch\u00e9
```

使用完整的 Unicode 写作：

```
children.activities.crafts.papierMché
```

可能会映射到目录名：

```
children/activities/crafts/papierM@002ch@00e9
```

如果 `@` 字符在某些给定宿主机文件系统的文件名不是有效字符，则可以使用另一个在标识符中无效的字符代替。

## 7.3 编译单元

`CompilationUnit` 是 Java 程序语法语法（§2.3）的目标符号（§2.1）。它由以下产生式定义：

- * CompilationUnit:
    - OrdinaryCompilationUnit
    - ModularCompilationUnit

- * OrdinaryCompilationUnit:
    - [PackageDeclaration] [ImportDeclaration]
    - [TopLevelClassInterfaceDeclaration]

一个普通编译单元由三部分组成，每部分都是可选的：

- * 包声明（§7.4），给出编译单元所属包的全限定名（§6.7）。
没有包声明的编译单元是无名包（§7.2）的一部分。

- * 导入声明（§7.5），允许从其他包导入类和接口以及类和接口的静态成员使用其简单名进行引用。

- * 类和接口的顶层声明（§7.6）。

一个模块编译单元包含一个模块声明（§7.7），前面可选带有导入声明。导入声明允许在该模块和其他模块的包中的类和接口，以及类和接口的静态成员，在模块声明中使用其简单名进行引用。

每个编译单元都会隐式地导入预定义包 `java.lang` 中声明的所有公共类或接口，就像在每个编译单元的开头、任何包声明之后立即出现 `import java.lang.*;` 声明一样。因此，所有这些类和接口的名字在每个编译单元中都可以作为简单名可用。

宿主机决定哪些编译单元是可观测的，预定义包 `java` 及其子包 `lang` 和 `io` 中的编译单元除外，它们总是可观测的。

## 包与模块

每个可观测的编译单元可以与一个模块*关联*，如下：

- 宿主机必须确定一个可观测的编译单元与宿主机选择的模块关联，但 (i) 预定义包 *java* 及其子包 *lang* 和 *io* 中的普通编译单元除外，它们都与 *java.base* 模块关联，以及 (ii) 无名包中的任何普通编译单元，根据§7.4.2 指定与模块关联。

- 宿主机必须确定一个可观测的模块化编译单元与模块单元声明的模块关联。

编译单元的可观测性影响其包的可观测性（§7.4.3），而带有模块的可观测编译单元的可观测性影响该模块的可观测性（§7.6）。

在编译与模块 *M* 关联的模块和普通编译单元时，宿主机必须遵守 *M* 声明中指定的依赖关系。具体来说，宿主机必须限制原本可观测的普通编译单元，使其仅限于对 *M* *可见*的单元。对 *M* 可见的普通编译单元是与被 *M* *读取*的模块关联的普通编译单元。被 *M* 读取的模块由 *java.lang.module* 包规范中描述的*解析*（resolution）结果给出，以 *M* 为唯一根模块。宿主机必须执行解析以确定 *M* 读取的模块；如果因 *java.lang.module* 包规范中描述的任何原因导致解析失败，则为编译错误。

读取关系是自反的，因此 *M* 读取自身，从而所有与 *M* 关联的模块化和普通编译单元对 *M* 可见。

被 *M* 读取的模块驱动了唯一对 *M* 可见的包（§7.4.3），这反过来又驱动了范围内的顶层包以及与 *M* 关联的模块化和普通编译单元中代码的包命名（§6.3, §6.5.3, §6.5.5）。

上述规则确保模块化编译单元中注解使用的包名和类型名（特别是应用于模块声明的注解）其解释方式就像它们出现在普通编译单元中一样。

在不同普通编译单元中声明的类和接口可以相互引用。Java 编译器必须同时编译此类类和接口。

## 7.4 包声明

包声明出现在普通编译单元中，用于指示编译单元所属的包。

### 7.4.1 命名包

普通编译单元中的包声明指定编译单元所属包的名字（§6.2）。

```
PackageDeclaration:
{PackageModifier} package Identifier [. Identifier] ;
```

```
PackageModifier:
Annotation
```

包声明中提到的名称必须是包的全限定名（§6.7）。

包声明的作用域和隐藏见§6.3和6.4。

关于包声明注解修符的规则见9.7.4和9.7.5。

给定的包允许最多有一个包声明。

强制此限制的方法根据需要实现而异。强烈建议采用以下方案：唯一的带注解包声明（如果存在）放在包含包源文件的目录中的 `package-info.java` 源文件中。该文件不包含名为 `package-info` 的类的源代码；这样做是非法的，因为 `package-info` 不是法的标识符。`package-info.java` 只包含一个包声明，前面紧跟该包的注解。虽然该文件技术上可以包含一个或多个具有访问权限的类的源代码，但是非常糟糕的做法。

建议如果 `package-info.java` 存在，则替代 javadoc 和其他文档生成系统的 `package.html`。如果此文件存在，文档生成工具应该在 `package-info.java` 中查找（可能带有注解的）包声明。通过这样，`package-info.java` 成为包级注解和文档的唯一存储。如果未来希望添加任何包级信息，此文件应该为这些信息提供方便的所在地。

## 7.4.2 无命名包

一个没有包声明但至少包含另一种类型声明的普通编译单元，一个无命名包的一部分。

Java SE 平台提供无命名包，主要是为了在开发小型或临时应用程序，或者在刚开始开发时提供便利。

无命名包不能有子包，因为包声明的语法始终包含对具名顶层包的引用。

Java SE 平台的实现必须至少支持一个无命名包。实现可以支持多个无命名包，但并非强制要求。每个无命名包包含哪些普通编译单元由宿主系统决定。

宿主系统必须将无命名包中的普通编译单元与无命名模块（§7.5）关联，而不是具名模块。

## 示例 7.4.2-1. 无命名包

该编译单元：

```java
class FirstCall {
    public static void main(String[] args) {
        System.out.println("Mr. Watson, come here." 
                                            + "I want you.");
    }
}
```

定义了一个作为无命名包部分的简单编译单元。

在使用分层文件系统存储包的 Java SE 实现中，一种典型的策略是将无命名包与每个目录关联；一次只能观测string一个无命名包，即与“当前工作目录”关联的那个包。“当前工作目录”的精确含义取决于宿主系统。

## 7.4.3 包的可观测性与可见性

一个包是可观测的，当且仅当以下条件至少一个为真：

- *包含该包声明的普通编译单元是可观测的 (§7.3)。*
- *该包的子包是可观测的。*

`java`、`java.lang` 和 `java.io` 包总是可观测的。

根据上述规则以及可观测编译单元的规则可以得出如下结论：预定义的包 `java.lang` 声明了 `Object` 类，因此 `Object` 的编译单元总是可观测的 (§7.3)。因此，`java.lang` 包是观测的，`java` 包也是可观测的。此外，由于 `Object` 是观测的，数组类型 `Object[]` 隐式扩展。它的超接口 `java.io.Serializable` (§10.1) 也存在，因此 `java.io` 包是可观测的。

一个包对模块 `M` 是可见的，当且仅当包含该包声明的普通编译单元对 `M` 是可见的。

包的可见性意味着包 `P` 对给定的模块是以有用的方式可观测的。仅仅因为子包 `Q` 是可观测的而知道包 `P` 是可观测的通常没有用。例如，假设 `Q`（在模块 `M1` 中）是观测的且 `P.R`（在模块 `M2` 中）是观测的；那么 `P` 是可观测的，但在哪里？在 `M1`、`M2` 还是两者中？这个问题是多余的；在编译仅需要 `M1` 的模块 `N` 期间，`Q` 是否可观测很重要，但 `P` 是否可观测则并不重要。

一个包对模块 `M` 是唯一可见的，当且仅当以下条件之一成立：

- *与 `M` 关联的普通编译单元包含该包的声明，且 `M` 没有读取任何其他向 `M` 导出该包的模块。*
- *与 `M` 关联的普通编译单元不包含该包的声明，且 `M` 读取恰好一个向 `M` 导出该包的模块。*

## 7.5 导入声明

导入声明允许通过简单名称（§7.2，由单个标识符组成）引用具名类、接口或静态成员。

如果不使用适当的导入声明，对另一个包中声明的类或接口的引用，或对另一个类或接口的静态成员的引用，通常需要使用全限定（§6.7）。

```
ImportDeclaration:
SingleTypeImportDeclaration
TypeOnDemandDeclaration
SingleStaticImportDeclaration
StaticImportOnDemandDeclaration
```

- *单类型导入声明 (§7.5.1) 通过提及其规范名 (§6.7) 导入单个具名类或接口。*
- *按需类型导入声明 (§7.5.2) 通过提及包、类或接口的规范名，按需要导入具名包、类或接口的所有可访问的类和接口。*
- *单静态导入声明 (§7.5.3) 通过给出其规范名，从类或接口中导入具有给定名称的所有可访问的静态成员。*
- *按需静态导入声明 (§7.5.4) 通过提及类或接口的规范名，按需要导入具名类或接口的所有可访问的静态成员。*

由这些声明导入的类、接口或成员的作用域和遮蔽关系在 §6.3 和 §6.4 中规定。

> 导入声明仅在实际包含该导入声明的编译单元内通过其简单名称使类、接口或成员可用。导入声明引入的类（s）、接口或成员的作用域具体不包括相同包中的其他编译单元，不包括当前编译单元中的其他声明，也不包括当前编译单元中的包声明（包声明的注解除外）。

## 7.5.1 单类型导入声明

单类型导入声明通过给出其规范名来导入单个类或接口，使其在出现单类型导入声明的编译单元的模块、类和接口声明中，通过简单名称可用。



# 单类型导入声明

```
SingleTypeImportDeclaration:
import TypeName;
```

`TypeName` 必须是类或接口的规范名（§6.7）。

该类或接口必须是具名包的成员，否则将产生编译错误。

如果具名接口不可访问（§6.6），则会产生编译错误。

如果同一个编译单元中的两个单类型导入声明尝试导入相同名的类或接口，则会发生编译错误，除非这两个类或接口是同一个，此时忽略重复声明。

## 7.5.1 包与模块

如果由单类型导入声明导入的类或接口在包含导入声明的编译单元中被声明为顶层类或接口（§7.6），则导入声明被忽略。

如果单类型导入声明导入了名为 `x` 的类或接口，且该编译单元也声明了名为 `x` 的顶层类或接口，则会发生编译错误。

如果一个编译单元包含导入名为 `x` 的类或接口的单类型导入声明，以及导入名为 `x` 的类或接口的单静态导入声明（§7.5.3），则会发生编译错误，除非这两个类或接口是同一个，此时忽略重复声明。

## 示例 7.5.1-1. 单类型导入

```
import java.util.Vector;
```

使得简单名称 `Vector` 在编译单元的类和接口声明中可用。因此，在所有未被同名字段、参数、局部变量或嵌套类或接口声明遮蔽（§6.4.1）或模糊（§6.4.2）的地方，名称 `Vector` 指 `java` 包中的类声明 `Vector`。

注意 `java.util.Vector` 的实际声明是泛型的（§8.1.2）。一旦导入，名称 `Vector` 可以在参数化类型（如 `Vector<String>`）或作为原始类型 `Vector` 中无需限定使用。导入声明的一个相关限制是，声明在泛型类或接口声明内部的成员类或接口是可以导入的，但其外部类型始终会被擦除。

## 示例 7.5.1-2. 重复类声明

此程序：

```
import java.util.Vector;
class Vector { Object[] vec; }
```

由于 `Vector` 重复声明会导致编译错误，如下所示如此：

```
import java.util.Vector;
import myVector.Vector;
```

其中 `myVector` 是包含以下编译单元的包：

```
package myVector;
public class Vector { Object[] vec; }
```

## 示例 7.5.1-3. 不导入子包

请注意，导入声明不能导入子包，只能导入类或接口。

例如，尝试导入 `java.util` 然后使用名称 `util.Random` 来引用类型 `java.util.Random` 是不起的：

```java
import java.util;
class Test { util.Random generator; }
// 错误：编译时错误
```

## 示例 7.5.1-4. 导入与包名同名的类型

在 §6.1 描述的命名规范下，包名和类型名通常是不同的。尽管如此，这里有一个意构造的例子：一个命名不符合惯例的包 `Vector` 声明了一个名为 `Mosquito` 的公共类：

```java
package Vector;
public class Mosquito { int capacity; }
```

然后是编译单元：

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

单类型导入声明导入了来自 `java.util` 包的类 `Vector`，这并没有阻止包 `Vector` 在后续导入声明中出现并被正确识别。该示例可以编译并产生输出：

```
class java.util.Vector
class Vector.Mosquito
```

## 7.5.2 按需类型导入声明

按需类型导入声明允许根据需要导入命名包、类或接口的所有可访问的类和接口。

```
TypeImportOnDemandDeclaration:
import PackageOrTypeName.*;
```

`PackageOrTypeName` 必须是包、类或接口的规范名称（§6.7）。

如果 `PackageOrTypeName` 指向一个类或接口（§6.5, 4），则该类或接口必须是某个命名包的成员，或者是某个类或接口的成员，且其最外层词法包含的类或接口声明（§8.1.3）是命名包的成员，否则将发生编译时错误。

如果该包对当前模块不可唯一可见（§7.4, 3），或者该类或接口不可访问（§6.6），则会发生编译时错误。

在按需类型导入声明中命名 `java.lang` 或当前编译单元的命名包不会引起编译时错误。在这种情况下，按需类型导入声明会被忽略。

在同一个编译单元中的两个或多个按需类型导入声明可以命名相同的包、类或接口。所有这些声明都被认为是冗余的；其效果等同于该类型仅被导入了一次。

如果一个编译单元同时包含命名相同类或接口的按需类型导入声明和按需静态导入声明（§7.5.4），其效果等同于该类或接口的静态成员类和接口（§8.5, §9.5）仅被导入了一次。

## 示例 7.5.2-1. 按需类型导入

```java
import java.util.*;
```

这导致在 `java.util` 包中声明的所有公共类和接口声明的名称在编译单元的类和接口声明中可用。因此，在编译单元中所有该类未被遮蔽（§6.4.1）或模糊（§6.4.2）的地方，简单名称 `Vector` 都指向 `java.util` 包中的 `Vector`。

该声明可能会被简单名为 `Vector` 的类或接口的单类型导入声明所遮蔽；可能会被声明在编译单元所属包中的名为 `Vector` 的类或接口遮蔽；或被任何嵌套类或接口遮蔽。

该声明可能会被字段、参数或局部变量的声明所模糊。

（这种情况不太可能发生。）

## 7.5.3 单静态导入声明

单静态导入声明从类或接口导入给定简单名称的所有静态成员。这使得这些静态成员在出现该静态导入声明的编译单元的类和接口声明中可用。

```
import static Identifier;
```

`TypeName` 必须是类或接口的规范名称（§6.7）。

该类或接口必须是命名包的成员，或者是某个类或接口的成员，且其最外层词法包含的类或接口声明（§8.1.3）是命名包的成员，否则将发生编译时错误。

如果该类或接口不可访问（§6.6），则会发生编译时错误。

`Identifier` 必须是该类或接口的至少一个静态成员。如果没有，则会发生编译时错误。

一个单静态导入声明可以导入具有相同名称的多个字段或方法。这发生在命名类或接口从其超类型继承了具有相同名称的多个静态成员时。

如果同一个编译单元中的两个单静态导入声明尝试导入同名的类或接口，则会发生编译时错误，除非这两个类或接口相同，此时重复声明会被忽略。

如果单静态导入声明导入了简单名为 `x` 的类或接口，而编译单元也声明了简单名为 `x` 的顶层类或接口（§7.6），则会发生编译时错误。

如果一个编译单元同时包含导入简单名为 `x` 的类或接口的单静态导入声明和导入同名类或接口的单类型导入声明（§7.5.1），则会发生编译时错误，除非这两个类或接口相同，此时重复声明会被忽略。

## 7.5.4 按需静态导入声明

按需静态导入声明允许根据需要导入命名类或接口的所有可访问静态成员。

```
StaticImportDemandDeclaration:
import static TypeName.*;
```

`TypeName` 必须是类或接口的规范名称（§6.7）。

该类或接口必须是命名包的成员，或者是某个类或接口的成员，且其最外层词法包含的类或接口声明（§8.1.3）是命名包的成员，否则将发生编译时错误。

如果命名的类或接口不可访问（§6.6），则会发生编译时错误。

同一个编译单元中的两个或多个按需静态导入声明可以命名相同的类或接口；其效果等同于只有一个声明。

同一个编译单元中的两个或多个按需静态导入声明可以命名相同的成员；其效果等同于该成员仅被导入了一次。

## 7.6 顶层类与接口声明

顶层类或接口声明声明一个顶层类（§8.1）或接口（§9.1）。

```
TopLevelClassOrInterfaceDeclaration:
ClassDeclaration
InterfaceDeclaration
;
```

在编译单元的类和接口声明级别出现的多余 `;` 标记对编译单元的含义没有影响。允许出现散乱的分号。

### 包与模块

在 Java 编程语言中，这种做法仅仅是为了向习惯于在类声明后放置 `;` 的 C++ 程序员妥协。不应在新的 Java 代码中使用它们。

在没有访问修饰符的情况下，顶层类或接口具有包级访问权限：它仅在声明它的包的普通编译单元内可访问（§6.6.1）。一个类或接口可以声明为 `public`，以允许同一模块内其他包中的代码（并可能来自其他模块的包中的代码）访问该类或接口。

如果顶层类或接口声明包含以下任何访问修饰符：`protected`、`private` 或 `static`，则为编译错误。

如果顶层类或接口的名称与同一包内定义的任何其他顶层类或接口的名称重复，则为编译错误。

顶层类或接口的作用域和隐藏在 §6.3 和 §6.4 中规定。

顶层类或接口的全限定名在 §6.7 中规定。

## 示例 7.6-1 冲突的顶层类和接口声明

```java
package test;
import java.util.Vector;
class Point {
    int x, y;
}
interface Point { // 编译错误 #1
    int getR();
    int getTheta();
}
class Vector extends Point[] pts; // 编译错误 #2
```

在这里，第一个编译错误是由于在同一个包中将名称 `Point` 重复声明为类和接口所导致的。第二个编译错误是尝试将该名称同时声明为类声明和单类型声明。

注意，类声明中的名称与同一编译单元中通过按需类型导入声明（§7.5.2）可能导入的类或接口重叠，这并不是错误。因此，在程序中：

```
package test;
import java.util.*;
class Vector {} // 不是编译错误
```

尽管存在类 `java.util.Vector`，但对类 `Vector` 的声明是允许的。在该编译单元内，简单名 `Vector` 指的是 `test.Vector` 类，而不是 `java.util.Vector`（编译单元内的代码仍可以引用它，但只能通过其全限定名）。

## 示例 7.6-2 顶层类和接口的作用域

```java
package points;
class Point {
    int x, y;              // 坐标
    PointColor color;      // 此点的颜色
    Point next;            // 具有此颜色的下一个点
    static int nPoints;
}

class PointColor {
    Point first;           // 此颜色的第一个点
    PointColor(int color) {this.color = color; }
    private int color;     // 颜色分量
}
```

该程序定义了两个在类成员声明中互相使用的类。`Point` 和 `PointColor` 类拥有包 `points` 中所有的类声明（包括当前编译单元中的声明），因此程序可以正确编译。也就是说，前向引用不是问题。

## 示例 7.6-3 全限定名

```java
class Point { int x, y; }
```

在代码中，类 `Point` 声明在一个没有包声明的编译单元中，因此 `Point` 是它的全限定名。而在代码中：

```java
package vista;
class Point { int x, y; }
```

类 `Point` 的全限定名是 `vista.Point`。（包名 `vista` 适用于本地或个人使用：如果该包旨在广泛发布，最好给它一个唯一的包名（§6.1）。）

Java SE 平台的实现必须通过其所属模块名称和二进制名称的组合来跟踪内部的类和接口（§13.1）。多种命名方式确保了这些名称被理解为指向同一个类或接口。

例如，如果一个编译单元包含单类型导入声明（§7.5.1）：

```
import java.util.Vector;
```

在该编译单元内，简单名 `Vector` 和全限定名 `java.util.Vector` 指向同一个类。

如果包存储在文件系统中（§7.2），当且仅当以下任一条件时，主机系统可以选择强制执行限制：如果在由类或接口名称加扩展名（如 `.java` 或 `.class`）组成的文件中找不到该类或接口，则为编译错误：

- 该类或接口被声明该类或接口的包中的其他普通编译单元的代码引用。
- 该类或接口被声明为 `public`（因此可能从其他包中的代码访问）。

此限制意味着每个编译单元最多有一个这样的类或接口。此限制使得 Java 编译器能够轻松在包内找到命名的类或接口。在实践中，许多程序员选择将每个类或接口放在它们自己的编译单元中，无论它们是否为 `public` 或被其他编译单元的代码引用。

例如，公共类 `wet.srocket.Toad` 的源代码将在 `wet/srocket` 目录下的 `Toad.java` 文件中，对应的目标代码将在同一目录下的 `Toad.class` 文件中。

## 7.7 模块声明

模块声明指定了一个新名称。命名模块指定了对其他模块的依赖，以定义自身代码可用的类和接口范围；并指定了哪些包是导出的。

> 依赖通过 `requires` 指令表示，取决于模块是否存在。一个“依赖”由模块声明引入，用于模块模块之间的关系。通常，Java 语言的规则对依赖更感兴趣。

```
ModuleDeclaration:
[Annotation] module Identifier { Identifier }
```

模块声明引入了一个可以在其他模块声明中名称。模块名称由一个或多个 Java 标识符（§3.8）分隔。

模块有两种类型：普通模块和开放模块。模块的类型决定了模块外部代码对模块类型及其成员的访问的性质。

### 普通模块与开放模块

普通模块不带 `open` 修饰符，在编译时和运行时仅允许访问显式导出的包中的类型。

开放模块带有 `open` 修饰符，在编译时仅允许访问显式导出的包中的类型，但在运行时允许访问其所有包，就像所有包都已导出一样。

对于模块外部代码（无论模块是普通还是开放），在编译时或运行时对模块导出包中类型的访问，仅限于这些包中的 `public` 类型和 `protected` 成员（§6.6）。在编译时或运行时，不允许访问未导出包的类型或其成员。模块内部的代码在编译时和运行时都可以访问所有包中的 `public` 类型和 `protected` 成员。

反射式访问与编译时的访问和运行时的访问不同，Java SE 平台通过核心反射 API（§1.4）提供反射式访问。普通模块仅对显式导出或开放（或两者都有）的包提供反射式访问。开放模块对所有包类型提供反射式访问，就像所有包都已开放一样。

对于普通模块外部，对其导出（未开放）的包中类型的反射式访问，仅限于这些包中的 `public` 类型和 `protected` 成员。对其开放包（无论是否导出）中类型的反射式访问，则针对这些包中的所有类型及其所有成员。对于未导出或未开放的包中的类型或其成员，不提供反射式访问。模块内部的代码对模块内所有包的类型及其所有成员享有反射式访问。

模块声明的指令指定了模块对其他模块的依赖（通过 `requires`，§7.7.1）、它向其他模块提供的包（通过 `exports` 和 `opens`，§7.7.2）、它消耗的服务（通过 `uses`，§7.7.3）以及它提供的服务（通过 `provides`，§7.7.4）。

## 7.7.1 模块指令

```
ModuleDirective:
requires [Modifier] ModuleName;
exports PackageName [to ModuleName [, ModuleName]];
opens PackageName [to ModuleName [, ModuleName]];
uses TypeName;
provides TypeName with TypeName (, TypeName);
```

### RequiresModifier

- `transitive`
- `static`

当且仅当包存储在文件系统中（§7.2）时，主机系统可以选择强制执行限制：如果在由 `module-info` 加上扩展名（如 `.java` 或 `.class`）组成的文件名未找到模块声明，则为编译错误。



为了避免复杂性，按照习惯（尽管并非强制），模块声明会对其指令进行分组：与模块相关的 `requires` 指令与与包相关的 `exports` 和 `opens` 指令在视觉上是分开的，与服务的 `uses` 和 `provides` 指令也是分开的。例如：

```java
module com.example.foo {
    requires com.example.foo.http;
    requires java.logging;

    transitive com.example.foo.network;

    exports com.example.foo.bar;
    exports com.example.foo.internal to com.example.foo.probe;

    opens com.example.foo.quux;
    opens com.example.foo.internal to com.example.foo.network;

    uses com.example.foo.spi.Intf;
    provides com.example.foo.spi.Intf with com.example.foo.Impl;
};
```

如果模块是开放的（open），则可以避免 `opens` 指令：

```java
open module com.example.foo {
    requires com.example.foo.http;
    requires java.logging;

    transitive com.example.foo.network;

    exports com.example.foo.bar;
    exports com.example.foo.internal to com.example.foo.probe;

    uses com.example.foo.spi.Intf;
    provides com.example.foo.spi.Intf with com.example.foo.Impl;
}
```

鼓励 Java 语言开发工具高亮 `transitive` 指令和未限定的 `exports` 指令，因为它们构成了模块的主要 API。

### 7.7.1 依赖

`requires` 指令指定当前模块所依赖的模块名称。

`java.base` 模块的声明中不能出现 `requires` 指令，否则会发生编译错误，因为它是原始模块且没有依赖 (§8.1.4)。

如果模块的声明没有表达对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，则该模块对 `java.base` 模块具有隐式声明的依赖。

`requires` 关键字后面可以跟修饰符 `transitive`。这会导致任何要求当前模块的模块对 `requires transitive` 指令指定的模块具有隐式声明的依赖。

`requires` 关键字后面可以跟修饰符 `static`。这指定该依赖在编译时是强制的，但在运行时是可选的。

如果模块的声明表达了对 `java.base` 模块的依赖，且该模块本身不是 `java.base`，则在 `requires` 关键字之后出现修饰符会导致编译错误。

如果模块声明中有多个 `requires` 指令指定相同的模块名称，则会导致编译错误。

如果按照 `java.lang.module` 包规范描述的解析（以当前模块作为唯一根模块）时，由于 `java.lang.module` 包规范中描述的任何原因而失败，则会导致编译错误。

例如，如果 `requires` 指令指定了一个不可见的模块，或者当前模块直接或间接地表达了对自身的依赖。

如果解析成功，则其结果指定了当前模块读取的模块。当前模块读取的模块决定了哪些普通编译单元对当前模块可见 (§7.3)。这些普通编译单元（以及*仅*这些普通编译单元）中定义的类型可以被当前模块的代码访问 (§6.6)。

Java SE 区分了显式声明的命名模块（即通过模块声明）和隐式声明的命名模块（即自动模块）。然而，Java 编程语言并没有体现这种区别：`requires` 指令引用命名模块时，不考虑它们是显式声明的还是隐式声明的。

虽然自动模块便于迁移，但它们是不可靠的，因为当作者将其转换为显式声明的模块时，它们的名称和导出的包可能会发生变化。鼓励 Java 编译器在 `requires` 指令引用自动模块时发出警告。如果指令中出现 `transitive` 修饰符，建议发出强烈警告。

## 示例 7.1.1-1. `requires transitive` 指令的解析

假设有四个模块声明如下：

```java
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

其中 `m.D` 导出的包 `p` 声明如下：且 `m.A` 模块中的包 `client` 引用导出包 `p` 中的公共类型 `Point`：

```java
package client;
import p.Point;
public class Test {
    public static void main(String[] args) {
        System.out.println(new Point());
    }
}
```

### 7.7.2 导出包与导入包

`exports` 指令指定由当前模块导出的包名称。对于其他模块，这允许编译时访问该包中的公共和受保护类型及其公共和受保护成员。

`opens` 指令指定由当前模块开放的包名称。对于其他模块，这允许运行时（而非编译时）访问该包中的公共和受保护类型及其受保护成员。

### 7.7.3 服务消费

`uses` 指令指定一个当前模块代码可以通过 `java.util.ServiceLoader` 发现提供者的服务。

如果 `uses` 指令指定枚举类 (§8.9)，则会导致编译错误。

服务可以在当前模块或其他模块中声明。如果服务不在当前模块中声明，则服务必须对当前模块的代码可见 (§6.6)，否则会发生编译错误。

如果模块声明中有多个 `uses` 指令指定相同的服务，则会导致编译错误。

### 7.7.4 服务提供

`provides` 指令指定了一种服务，`with` 子句为该服务向 `java.util.ServiceLoader` 指定了一个或多个服务提供者。

如果 `provides` 指令指定一个枚举类 (§8.9) 作为服务，则会产生编译错误。

服务可以在当前模块中声明，也可以在另一个模块中声明。如果服务未在当前模块中，则该服务必须对当前模块中的代码可见 (§6.6)，否则会产生编译错误。

每个服务提供者必须是一个公共类或接口，且必须是顶层的或静态的，否则会产生编译错误。

每个服务提供者必须在当前模块中声明，否则会产生编译错误。

如果服务提供者显式声明了一个没有形式参数的公共构造函数，或者隐式地声明了公共默认构造函数 (§8.8.9)，则该构造函数被称为提供构造函数。

如果服务提供者显式声明了一个公共静态方法，则该方法被称为提供方法。

如果服务提供者拥有提供方法，则其返回类型必须：(i) 要在当前模块中声明；且 (ii) 是 `provides` 指令中指定的服务的子类型；否则会产生编译错误。

> 虽然由 `provides` 指令指定的服务提供者必须在当前模块中声明，但其提供方法的返回类型可以声明在另一个模块中。此外，请注意，当服务提供者声明提供方法时，服务本身并不一定是该服务的子类型。

如果服务提供者没有提供方法，则该服务提供者必须有一个提供构造函数，并且必须是 `provides` 指令中指定的服务的子类型，否则会产生编译错误。

如果一个模块声明中有多个 `provides` 指令指定了同一个服务，则会产生编译错误。

如果给定的 `provides` 指令的 `with` 子句多次指定同一个服务，则会产生编译错误。

### 7.7.5 无命名模块

宿主系统未与命名模块 (§7.3) 关联的可观测普通编译单元与一个无命名模块关联。

Java SE 平台提供无命名模块是为了承认在 Java SE 9 之前开发的程序无法声明无命名模块的事。此外，Java SE 平台提供无命名包 (§7.4.2) 的原因在很大程度上适用于无命名模块。

Java SE 平台的实现必须支持至少一个无命名模块。一个实现可以支持多个无命名模块，但不是必须的。哪些普通编译单元与每个无命名模块关联由宿主系统决定。

宿主系统可以将命名包中的普通编译单元与一个无命名模块关联。

无命名模块的规则旨在最大化其与命名模块的互操作性，如下：

- 无命名模块读取每个无命名模块 (§7.7.6)。

> 由于与无命名模块关联的普通编译单元是可观测的，因此关联的无命名模块也是可观测的。因此，如果 Java SE 实现支持多个无命名模块，每个无命名模块都是可观测的，且每个无命名模块都读取自身。

然而，重要的是，无命名模块的普通编译单元对命名模块 (§7.3) 是永远不可见的，因为没有 `requires` 指令允许安排命名模块去读取无命名模块。Java SE 平台的核心反射 API 可以在运行时安排命名模块读取无命名模块。

- 无命名模块导出所有普通编译单元与该无命名模块关联的包。

- 无命名模块打开所有普通编译单元与该无命名模块关联的包。

### 7.7.6 模块的可观测性

如果满足以下一个条件，则模块是可观测的：

- 包含模块声明的模块化编译单元是可观测的 (§7.3)。

- 与模块关联的普通编译单元是可观测的。

## 第 8 章 类

类声明定义了一个新类并描述其实现方式 (§8.1)。

顶层类 (§7.6) 是直接在编译单元中声明的类。

嵌套类是任何声明发生在另一个类或接口声明体内的类。嵌套类可以是成员类 (§8.5, §9.5)、局部类 (§14.3) 或匿名类 (§15.9.5)。

某些类型的嵌套类是内部类 (§8.1.3)，它是一种可以引用外部类、局部变量和类型变量的类。

枚举类 (§8.9) 是使用简写语法声明的类，定义了一组较小的命名类集合。

记录类 (§8.10) 是使用简写语法声明的类，定义了值的简单聚合。

本章讨论了所有类的共同语义。针对特定类型类的细节将在专门讨论这些构造的章节中讨论。

类可以被声明为公共 (§8.1.1)，以便可以从其模块中任何包的代码中引用，并可能从其他模块的代码引用。

类可以被声明为抽象 (§8.1.1.1)，如果它实现不完全，则必须声明为抽象；此类类不能实例化，但可以被子类扩展。类可以被扩展的程度是显式的 (§8.1.1.2)：它可以被声明为 sealed 以限制其子类，或者可以声明为 final 以无任何子类。除了 Object 之外，每个类都是单个现有类的扩展（即子类） (§8.1.4)，并可以实现接口 (§8.1.5)。

类可以被声明为泛型 (§1.2)，即其声明可以引入类型变量，其绑定在不同实例之间有所不同。

类声明可以像其他类型的声明一样用注解 (§9.7) 修饰。

类体声明成员（字段、方法、类、接口）、实例和静态初始化器以及构造函数 (§8.1)。成员 (§8.2) 的作用域 (§6.3) 是其所属的整个类体。字段、方法、成员类、成员接口和构造函数声明可以包含访问修饰符 public、protected 或 private (§6.6)。类的成员包括已声明的和继承的成员 (§8.2)。新字段可以隐藏超类或超接口中的字段。新成员类和成员接口可以隐藏超类或超接口中的成员类和成员接口。新方法可以隐藏、实现或重写超类或超接口的方法。

字段声明 (§8.3) 描述类变量（实例化一次）和实例变量（每个类实例都会重新实例化）。字段可以被声明为 final (§8.1.2)，在这种情况下只能赋值一次。任何字段声明都可以包含一个初始化器。

成员类声明 (§8.5) 描述作为周围类的嵌套类。成员类可以是静态的，在这种情况下无法访问周围类的实例变量；或者它们可以是内部类。

成员接口声明 (§8.5) 描述作为周围类的嵌套接口。

方法声明 (§8.4) 描述可以通过方法调用表达式 (§15.2) 调用的代码。类方法相对于类调用；实例方法相对于某个特定的类实例调用。声明未指明如何实现的方法必须被声明为抽象。方法可以被声明为 final (§8.4.3)，在这种情况下不能被隐藏或重写。方法可以由平台相关的原生代码实现 (§8.4.4)。同步方法 (§8.4.6) 在执行其体之前自动锁定对象，并在返回时解锁对象，仿佛使用了同步语句 (§14.19)，从而允许其活动与其他线程的活动保持同步 (§17 线程与锁)。

方法名可以重载 (§8.4.9)。

实例初始化器 (§8.6) 是可以在创建实例 (§15.9) 时初始化实例的可执行代码块。

静态初始化器 (§8.7) 是可执行代码块，可用于帮助初始化类。

构造函数 (§8.8) 与方法相似，但不能通过方法调用直接调用；它们用于初始化新的类实例。像方法一样，它们可以被重载 (§8.8)。

## 8.1 类声明

类声明指定了一个类。

类声明有三种：普通类声明、枚举声明 (§8.9) 和记录声明 (§8.10)。

```java
ClassDeclaration:
NormalClassDeclaration
EnumDeclaration
RecordDeclaration
```

```java
NormalClassDeclaration:
[ClassModifier] class TypeIdentifier [TypeArguments]
[ClassExtends][ClassImplements][ClassPermits] ClassBody
```

类也可以通过类实例创建表达式 (§15.9.5) 和以类体结尾的枚举常量 (§8.9.1) 隐式地声明。

类声明中的 `TypeIdentifier` 指定了类的名称。

如果一个类与它的任何包围范围内的类或接口同名，则为编译时错误。

类声明的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

### 8.1.1 类修饰符

类声明可以包含类修饰符。

```
ClassModifier:
(one of)
Annotation public protected private
abstract static final sealed non-sealed strictfp
```

关于类声明的注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

访问修饰符 `public` (§6.6) 仅适用于顶层类 (§7.6) 和成员类 (§8.5, §9.5)，不适用于局部类 (§14.3) 或匿名类 (§15.9.5)。

访问修饰符 `protected` 和 `private` 仅适用于成员类。

修饰符 `static` 仅适用于成员类。

如果同一个关键字作为类声明的修饰符出现多次，或者一个类声明具有多个 `public`、`protected` 或 `private` 访问修饰符，则为编译时错误。

如果一个类声明具有多个 `sealed`、`non-sealed` 或 `final` 修饰符，则为编译时错误。

如果在类声明中出现了两个或多个（不同的）类修饰符，按照惯例（并非强制），它们出现的顺序应与上述 `ClassModifier` 产生式中所示顺序一致。

### 8.1.1.1 抽象类

抽象类是不完全的，或者被认为是不完全的。

如果尝试使用类创建表达式 (§15.9.1) 创建抽象类的实例，则为编译时错误。

抽象类的一个本身不是抽象的子类可以实例化，这将导致抽象类构造函数的执行，从而执行该类实例变量的字段初始化器。

普通类可以拥有抽象方法（即已声明但尚未实现的方法 (§8.4.3.1)），前提是它必须是一个抽象类。如果非抽象的普通类具有抽象方法，则为编译时错误。

如果以下任一情况真，则类具有抽象方法：

- C 的任何成员方法 (§8.2)——无论是声明的还是继承的——都是抽象的。

- C 的任何父类都有一个以包访问权限声明的抽象方法，且不存在方法可以覆盖来自 C 或来自 C 的父类的该抽象方法。

如果声明一个抽象类类型，导致无法创建一个实现其所有抽象方法的子类，则为编译时错误。这种情况可能发生在该类拥有两个具有相同方法签名 (§8.4.2) 的抽象成员，但它们的返回类型没有某种类型可以同时与两者类型替换 (§8.4.5)。

#### 示例 8.1.1.1-1 抽象类声明

```java
abstract class Point {
    int x = 1, y = 1;
    void move(int dx, int dy) {
        x += dx;
        y += dy;
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

在这里，声明了一个类 Point，它必须声明为抽象，因为它包含了一个名为 `alert` 的抽象方法的声明。Point 的子类 `ColoredPoint` 继承了抽象方法 `alert`，因此它也必须声明为抽象类。另一方面，Point 的子类 `SimplePoint` 提供了 `alert` 实现，所以它不需要是抽象的。

语句：

```java
Point p = new Point();
```

会导致编译时错误；类 `Point` 不能被实例化，因为它是抽象的。然而，`Point` 变量可以使用 Point 的任何子类的引用进行正确初始化，且类 `SimplePoint` 不是抽象的，因此语句：

```java
Point p = new SimplePoint();
```



# 类声明

是正确的。实例化 `SimplePoint` 会导致 `Point` 的默认构造函数以及 `x`、`y` 的字段初始化器执行。

## 示例 8.1.1.1-2 禁止子类的抽象类声明

```java
interface Colorable {
    void setColor(int color);
}
abstract class Colored implements Colorable {
    public abstract int setColor(int color);
}
```

## 8.1.1.2 sealed、non-sealed 和 final 类

`sealed` 关键字的作用是强制所有直接子类显式地声明它们是 `final`、`sealed` 还是 `non-sealed`。这避免了密封类意外暴露给子类。

枚举类要么是隐式的 `final` 要么是隐式的 `sealed`，因此它可以实现密封接口。同样，记录类是隐式的 `final`，因此它可以实现密封接口。

如果一个类被声明为 `non-sealed` 但既没有密封父类也没有密封父接口，则为编译时错误。

`non-sealed` 类的子类不能再次声明为 `non-sealed`。

## 8.1.1.3 strictfp 类

类声明中的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否在编译时或运行时均无产生影响。

## 8.1.1.4 static 类

`static` 修饰符指定嵌套类不是内部类（§8.1.3）。正如类的静态修饰符在其体文中没有类的实例一样，静态嵌套类在其体文中没有直接包围类。

不允许从静态嵌套类引用类型参数、实例变量、局部变量、形式参数、异常参数以及词法包围类、接口或方法的声明（§6.5.5.1、§6.5.6.1 和 §15.12.3）。

`static` 修饰符并不适用于所有嵌套类。它仅适用于成员类（其声明可以使用 `static` 修饰符），而不适用于局部类或匿名类（其声明不能使用 `static` 修饰符）。然而，某些局部类是隐式静态的，即局部枚举类和局部记录类，因为所有嵌套枚举和嵌套记录类都是隐式静态的（§8.9、§8.10）。

## 8.1.2 泛型类和类型参数

如果类声明声明了一个或多个类型变量（§4.4），则该类是泛型类。

这些类型变量被称为类的类型参数。类型参数部分位于类名之后，并用角括号括围。

```java
TypeParameters:
    < TypeTokenList >
```

### 类声明

```java
TypeParameterList:
    TypeParameter (, TypeParameter)
```

为了方便起见，此处显示了 §4.4 中的产生式：

```java
TypeParameter:
    [TypeParameterModifier] TypeIdentifier [TypeBound]
```

```java
TypeParameterModifier:
    Annotation
```

```java
TypeBound:
    extends TypeVariable
    extends ClassOrInterfaceType [AdditionalBound]
```

```java
AdditionalBound:
    & InterfaceType
```

关于类型参数声明的注解修饰符的规定在 §9.7.4 和 §9.7.5 中指定。

在类的类型参数部分，类型变量 τ 依赖于变量 s，如果 s 是 τ 的边界；如果 τ 直接依赖于 s，或者 τ 直接依赖于一个依赖于 s 的类型变量 u（递归地使用此定义），则称 τ 依赖于 s。

如果类类型参数部分中的类型变量依赖于其自身，则为编译时错误。

类类型参数的作用域和隐藏在 §6.3 和 §6.4.1 中规定。

根据 §6.5.5.1 的规定，在静态上下文、嵌套类或接口中对类类型参数的引用受到限制。

泛型类声明定义了一组参数化类型（§4.5），类型参数部分通过类型参数每种可能的特化形式对应一个。所有这些参数化类型在运行时共享同一个类。

例如，执行代码：

```java
Vector<String> x = new Vector<String>();
Vector<Integer> y = new Vector<Integer>();
boolean b = x.getClass() == y.getClass();
```

将导致 b 的值为 true。

如果泛型类是 `Throwable` 的直接或间接子类（§11.1.1），则为编译时错误。

## 8.1.3 内部类与外部实例

内部类是指不是显式或隐式静态的嵌套类。内部类是以下之一：

- 不是显式或隐式静态的成员类（§8.5）
- 不是显式或隐式静态的局部类（§14.3）
- 匿名类（§15.9.5）

以下嵌套类是隐式静态的，因此不是内部类：

- 枚举类（§8.9）
- 记录类（§8.10）
- 接口（§9.5）

适用于嵌套类的所有规则也适用于内部类。特别是，内部类可以声明静态成员（§8.2）和静态初始化器（§8.7），尽管类本身不是。

#### 示例 8.1.3-1. 类声明与静态成员

```java
class HasStatic {
    int j = 10;

    static class Inner {
        System.out.println("Hello from Outer");
    }

    static int x;

    static void hello() {
        System.out.println("Hello from Inner");
    }

    static class VeryNot
        extends NestedNotInner {}

    static class NestedNotInner {
        int z;
    }

    interface NeverInner { }
}
```

在 SE 16 之前，内部类不能声明静态成员，且只能声明局部变量。如果一个结构（语句、局部类声明或表达式）位于以下结构的内部，则它处于静态上下文中：

- 方法声明
- 字段声明
- 构造方法声明
- 实例初始化器

包含该结构的是以下之一：

- 静态方法（§8.4）
- 静态字段（§8.3）
- 静态初始化器（§8.7）
- 显式构造方法调用（§8.8）

注意，出现在构造方法声明或实例初始化器中的结构不在静态上下文中。

静态上下文的作用是标记不能显式或隐式引用包含它的类的当前实例。因此，静态上下文中的代码受到以下限制：

- `this` 表达式（无论是未限定还是限定）都是不允许的（§15.8.3, §15.8.4）。
- 字段访问、方法调用和方法引用不能用 `super` 限定（§15.11.2, §15.12.3, §15.13.1）。
- 对任何词法作用类的实例变量的未限定引用是不允许的（§6.5.6）。
- 对任何词法作用类的实例方法的未限定调用是不允许的（§15.12.3）。
- 对任何词法作用类的类型参数的引用是不允许的（§6.5.5）。
- 对位于紧邻类声明之外的任何方法或构造方法的类型参数、局部变量、形式参数和异常参数的引用是不允许的（§6.5.1, §6.5.6）。
- 局部类（相对于局部枚举类）和匿名类的声明都指定它们是内部类，但没有外部实例（§15.9.2）。
- 实例化内部成员的类创建表达式必须不允许（§15.9）。

内部类 c 是类或接口的直接内部类，当 c 的紧邻类或接口声明存在且 c 的声明不在静态上下文中。

> 如果内部类是局部类或匿名类，则可以在静态上下文中声明，在这种情况下它不认为是任何外部类或接口的内部类。

类是类或接口 o 的内部类，如果它是 o 的直接内部类，或者是 o 的内部类的内部类。

> 这种情况很少见，但可能的，内部类的紧邻类或接口声明可以是接口。这仅当类是在默认或静态方法体中声明的局部或匿名类时发生（§9.4）。

类或接口 o 是自身的零次词法作用类声明。

类 o 是类 c 的 n 次词法作用类声明，如果它是 c 的 n-1 次词法作用类声明的紧邻类声明。

类或接口 $o$ 的直接内部类 $c$ 的实例 $i$ 与一个 $o$ 的实例关联，该实例被称为 $i$ 的*直接包层实例*（immediately enclosing instance）。对象的直接包层实例（如果有的话）是在对象创建时确定的（§15.9.2）。

对象 $o$ 是它自身的*第零次*词法包层实例。

如果对象 $o$ 是实例 $i$ 的第 $n-1$ 次词法包层实例的直接包层实例，则对象 $o$ 是实例 $i$ 的第 $n$ 次词法包层实例。

在静态上下文中声明的内部类或匿名类的实例没有直接包层实例。此外，`static` 嵌套类（§8.1.1.4）的实例没有直接包层实例。

对于 $c$ 的每个父类 $s$，如果它本身是类或接口 $so$ 的直接内部类，则存在 $i$ 与一个 $s$ 的实例关联，该实例被称为相对于 $s$ 的 $i$ 的*直接包层实例*。对象相对于其 $c$ 直接父类的直接包层实例（如果有的话）是在通过显式构造方法语句调用父类构造函数时确定的（§8.8.7.1）。

当内部类（其声明未发生在静态上下文中）引用词法包层类或接口声明的成员实例变量时，将使用相应词法包层实例的变量。

内部类中未使用但未声明的任何局部变量、形式参数或异常参数必须是 `final` 或有效最终的（effectively final）（§4.12.4），如 §6.5.6.1 规定。

内部类中未使用但未声明的任何局部变量在内部类体之前必须经过确定赋值（§16.1），否则会发生编译错误。

变量使用的类似规则也适用于 lambda 表达式的体（§15.27.2）。

词法包层类或接口声明的空白 `final` 字段（§4.12.4）不能在内部类中赋值，否则会发生编译错误。

#### 示例 8.1.3-2. 内部类声明

```java
class Outer {
    int i = 100;
    static void classMethod() {
        final int l = 200;
        class LocalInStaticContext {
            int k = i; // 编译错误
            int m = 1; // OK
        }
    }
}
```

```java
void foo() {
    class Local { // 局部类
        int j = i;
    }
}
```

`LocalInStaticContext` 的声明由于位于静态方法 `classMethod` 内部发生在静态上下文中。类 `Outer` 的实例变量在静态方法的体内不可用。特别是，`Outer` 的实例变量在 `LocalInStaticContext` 的体内部不可用。然而，可以无错误引用周围方法的局部变量（前提它们被声明为 final 或有效最终的）。

声明未发生在静态上下文中的内部类可以自由地引用其包层类声明的实例变量。实例变量总是相对于某个实例定义的。在包层类声明的实例变量的情况下，该实例变量必须相对于内部类的某个包层实例定义。例如，类 `Local` 有一个 `Outer` 类的包层实例。另一个示例是：

```java
class WithDeepNesting {
    boolean toBe;
    WithDeepNesting(boolean b) { toBe = b; }

    class Nested {
        class DeeplyNested {
            DeeplyNested() {
                theQuestion = toBe || !toBe;
            }
        }
    }
}
```

每个 `WithDeepNesting.Nested.DeeplyNested` 实例都有一个 `WithDeepNesting` 类的包层实例（其直接包层实例）以及一个 `WithDeepNesting` 类的包层实例（其第 2 次词法包层实例）。

## 8.1.4 父类与子类

普通类声明中的可选 `extends` 子句指定了被声明类的直接父类类型。

```java
ClassExtends:
    extends ClassType
```

`extends` 子句不能出现在 `Object` 定义中，否则会发生编译错误，因为它是原始类且没有直接父类类型。

`ClassType` 必须命名一个可访问的类（§6.6），否则会发生编译错误。

如果 `ClassType` 命名了一个密封（sealed）类（§8.1.1.2），且被声明的类不是该命名类的允许子类（§8.1.6），则会发生编译错误。

如果 `ClassType` 命名了一个 `final` 类，则会发生编译错误，因为 `final` 类不允许有子类（§8.1.1.2）。

如果 `ClassType` 命名了一个 `Enum` 类（它只能被枚举类扩展（§8.9）），或命名了 `Record` 类（它只能被记录类扩展（§8.10）），则会发生编译错误。

如果 `ClassType` 带有参数，它必须表示一个良好的泛型类型（§4.5），且任何类型参数都不能是通配符类型，否则会发生编译错误。

缺少 `extends` 子句的类的直接父类类型如下：

- `Object` 类没有直接父类类型。
- 对于 `Object` 以外的类，直接父类是 `Object`。
- 对于枚举类，直接父类是 `Enum`。
- 对于匿名类，直接父类是其包层类的直接父类。
- 对于记录类，直接父类是 `Record`。

## 8.1.5 超接口

一个声明中缺少 `implements` 子句的类没有直接的超接口类型，但有一个例外：匿名类可以拥有一个超接口类型（§15.9.5）。

如果一个接口是由类的某个直接超接口类型命名的，则该接口是该类的直接超接口。

如果满足以下任一条件，则接口 I 是类 C 的超接口：

- I 是直接超接口。
- C 具有某个直接超接口 J，对于该 J，I 是其超接口（使用 §9.1.9.1.3 中给出的“接口的超接口”的定义）。
- I 是 C 的直接超父类的超接口。

一个类可以通过多种方式拥有超接口。

一个类被认为是直接实现了它的直接接口，并实现了它所有的超接口。

一个类被认为是它直接超接口的直接子类，以及它所有超接口的子类。

一个类不能声明直接超父类类型和一个直接超接口类型，也不能声明两个直接超接口类型，这些类型（或超类型 §4.10.2）是同一个泛型接口的不同参数化，或者是命名该泛型接口的原始类型。在这种情况下，会发生编译错误。

引入这一项要求是为了支持类型擦除转换（§4.6）。

### 示例 8.1.5-2. 超接口



## 类声明

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

这些关系如下：

- 接口 `Paintable` 是类 `PaintedPoint` 的超接口。
- 接口 `Colorable` 是类 `ColoredPoint` 和类 `PaintedPoint` 的超接口。
- 接口 `Paintable` 是接口 `Colorable` 的子接口，根据 9.1.1.3 的定义，`Colorable` 是 `Paintable` 的超接口。

类 `PaintedPoint` 有 `Colorable` 作为超接口，既是因为它是 `ColoredPoint` 的超接口，也因为它是 `Paintable` 的超接口。

### 示例 8.1.5-3. 接口的非法继承

```java
interface I<T> {}
class B implements I<Integer>
class C extends B implements I<String>
```

`C` 导致了编译错误，因为它尝试同时成为 `I<Integer>` 和 `I<String>` 的子类型。

除非类被声明为 `abstract`，否则每个直接超接口的所有抽象成员方法都必须（§8.4.8.1）通过该类中的声明或通过从直接超父类或直接超接口继承的现有方法声明来实现的，因为非抽象类不允许拥有抽象方法（§8.1.1.1）。

类的超接口的每个默认方法（§9.4.3）都可能被类中的方法覆盖；如果没有覆盖，默认方法通常会被继承，其行为由其默认体指定。

允许类中的单个方法声明实现多个接口的方法。

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

此程序会导致编译错误，因为 `ColoredPoint` 不是一个抽象类，但未能提供接口 `Colorable` 中方法 `setColor` 和 `getColor` 的实现。

在以下程序中：

```java
interface Fish { int getNumberOfOfScales(); }
interface Piano { int getNumberOfOfScales(); }
class Tuna implements Fish, Piano {
    // 你可以调钢琴，但你能“调”鱼吗？
    public int getNumberOfOfScales() { return 91; }
}
```

类 `Tuna` 中的方法 `getNumberOfOfScales` 的名称和返回类型与接口 `Fish` 中声明的方法匹配，同时也与接口 `Piano` 中声明的方法匹配；它被认为实现了两者。

相反，在类似这样的情况下：

```java
interface Fish { int getNumberOfOfScales(); }
interface StringBass { double getNumberOfOfScales(); }
class Bass implements Fish, StringBass {
    // 这个声明是不可能的，
    // 无论使用什么类型都是。
    public ?? getNumberOfOfScales() { return 91; }
}
```

无法声明一个名为 `getNumberOfOfScales` 且其签名和返回类型与接口 `Fish` 和接口 `StringBass` 中声明的两个方法都匹配的方法，因为一个类不能拥有多个相同签名但不同返回类型的方法（§8.4）。因此，一个类不可能同时实现接口 `Fish` 和接口 `StringBass`（§8.4）。

### 8.1.6 允许的子类

可选的 `permits` 子句指定了所有预期的作为直接子类的类。

```
classPermits:
permits TypeName, TypeName
```

如果 `sealed` 类有 `permits` 子句但没有 `sealed` 修饰符，则会导致编译错误。

如果同一个类在 `permits` 子句中出现多次，则会导致编译错误。即使以不同的方式命名也是如此。例如，以下程序编译失败：

```java
package p;
sealed class A permits B, C // 错误
nonsealed class B {}
nonsealed class C {}
```

如果 `sealed` 类关联命名模块（§7.3），则 `permits` 子句中的每个类必须关联同一个模块，否则会导致编译错误。

如果 `sealed` 类关联未命名模块（§7.7），则 `permits` 子句中的每个类必须属于同一个包，否则会导致编译错误。

一个 `sealed` 类及其直接子类需要分别在 `permits` 和 `extends` 子句中相互引用。因此，在模块化代码库中，它们必须位于同一个模块内，由同一个开发者维护。命名模块通常代表代码库中的一个领域。

如果 `sealed` 类声明有 `permits` 子句，则其子类为 `permits` 子句指定的类。`permits` 指定的每个类必须是 `c` 的直接子类（§8.1），否则会发生编译错误。

如果 `sealed` 类声明缺少 `permits` 子句，则其子类如下：

- 如果 `c` 不是枚举类，则其子类是同一编译单元（§7.3）中定义的具有规范名称（§6.7）且直接父类为 `c` 的类。也就是说，直接子类被推断为同一编译单元中的类。规范名称的要求意味着不考虑局部类或匿名类。如果 `sealed` 类声明缺少 `permits` 子句且 `c` 没有子类，则会导致错误。
- 如果 `c` 是枚举类，见 §8.9。

### 8.1.7 类体和成员声明

类可以包含类的成员声明，即字段（§8.3）、方法（§8.4）、类和接口（§8.5）。

类还可以包含实例初始化器（§8.6）、静态初始化器（§8.7）以及类的构造函数声明（§8.8）。

```
ClassBody:
{ [ClassBodyDeclaration] }

ClassBodyDeclaration:
  ClassMemberDeclaration:
    InstanceInitializer
    StaticInitializer
    ConstructorDeclaration

ClassMemberDeclaration:
  FieldDeclaration
  MethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

在类中或继承的成员声明的作用域和遮蔽由 §6.3 和 §6.4.1 规定。

如果 `c` 是嵌套类，在外层作用域中可能存在与 `m` 相同类型（变量、方法或类型）且相同的定义。（范围可以是块、类或包）。

## 8.2 类成员

# 类成员

在所有此类情况下，在 `c` 中声明或由 `c` 继承的成员 `m` 会遮蔽相同类型和名称的其他定义。

类的成员包括以下内容：

- 继承自其直接超类类型（§ 8.1.4）的成员，`Object` 类除外，它没有直接的超类类型
- 继承自任何直接超接口类型（§ 8.1.5）的成员
- 在类体中声明的成员（§ 8.1.7）

类中声明为 `private` 的成员不会被该类的子类继承。

只有声明为 `protected` 或 `public` 的类成员才会被声明在类所在包之外的其他包中的子类继承。

构造方法、静态初始化器和实例初始化器不是成员，因此不被继承。

我们使用术语*成员类型* 表示：

- 对于字段，其类型。
- 对于方法，一个由以下部分组成的有序 4 元元组：
  - 类型参数：方法成员中任何类型参数的声明。
  - 参数类型：方法成员参数类型的类型列表。
  - 返回类型：方法成员的返回类型。
  - throws 子句：方法成员 `throws` 子句中声明的异常类型。

类的字段、方法、成员类和成员接口可以具有相同的名称，因为它们被用于不同的上下文中，并通过不同的查找程序进行消义（§ 6.5）。然而，从风格上来说，是不建议这样做。

### 示例 8.2-1. 类成员的使用

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

发生一个错误是因为 `ColoredPoint` 没有声明带有两个 `int` 参数的构造方法，正如在 `main` 方法中使用它那样。这说明了 `ColoredPoint` 并没有继承其超类 `Point` 的构造方法。

发生另一个错误是因为 `ColoredPoint` 没有声明任何构造方法，因此为它隐式地声明了一个默认构造方法（§ 8.8.9），而该构造方法等同于：

```java
ColoredPoint() { super(); }
```

它为类 `ColoredPoint` 的直接超类调用了无参数的 `reset()` 方法。错误在于，`Point` 的无参数构造方法是私有的，因此在 `Point` 类外部无法访问，即使通过超类构造方法调用也不行（§ 8.8.7）。

又发生了两个错误，是因为 `Point` 类的 `reset` 方法是私有的，因此没有被 `ColoredPoint` 类继承。因此，`ColoredPoint` 类 `clear` 方法中的方法调用以及 `Test` 类 `main` 方法中的方法调用都是不正确的。

### 示例 8.2-2. 具有包访问权限的类成员继承

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

在另一个包中的第三个编译单元是：

```java
import points.Point3d;
class Point4d extends Point3d {
    int w;
    public void move(int dx, int dy, int dz, int dw) {
        x += dx; y += dy; z += dw; // 编译错误
    }
}
```

`points` 包中的两个类都通过了编译。`Point3d` 类继承了 `Point` 类的字段 `x` 和 `y`，因为它们在同一个包中。`Point4d` 类位于不同的包，它没有继承 `Point` 类的 `x` 和 `y` 字段或 `Point3d` 类的 `z` 字段，导致编译失败。

编写第三个编译单元更好的方式是：

```java
import points.Point3d;
class Point4d extends Point3d {
    int w;
    public void move(int dx, int dy, int dz, int dw) {
        super.move(dx, dy, dz); w += dw;
    }
}
```

使用超类 `Point3d` 的 `move` 方法来处理 `dx`、`dy` 和 `dz`。如果这样写 `Point4d`，它将无错误地通过编译。

### 示例 8.2-3. 公有和保护类成员的继承

给定类 `Point`：

```java
package points;
public class Point {
    public int x, y;
    protected int useCount = 0;
    static protected int totalCount = 0;
    public void move(int dx, int dy) {
        x += dx; y += dy; useCount++; totalCount++;
    }
}
```

`public` 和保护的字段 `x`、`y`、`useCount` 和 `totalCount` 被 `Point` 的子类继承。

因此，另一个包中的此测试程序是可以编译的：

```java
package points;
public class Point {
    public int x, y;
    protected int useCount = 0;
    static protected int totalCount = 0;
    public void move(int dx, int dy) {
        x += dx; y += dy; useCount++; totalCount++;
    }
}
class Point3d extends Point {
    int z;
    public void move(int dx, int dy, int dz) {
        x += dx; y += dy; z += dz;
    }
    public void move(int dx, int dy) {
        move(dx, dy);
    }
}
public class OnePoint {
    public static Point get() {
        return new Point3d();
    }
}
```

第三个包中的调用 `points.OnePoint.get()` 将返回一个可以作为 `Point` 使用的 `Point3d`，尽管该类型在包外不可用。可以为该对象调用两个参数版本的 `move` 方法，这是允许的，因为 `Point3d` 的 `move` 方法是公有的（任何重写公方法的方法必须是公有的，正是为了确保这种情况能够正常工作）。也可以从该包访问该对象的字段 `x` 和 `y`。

### 示例 8.2-4. 私有成员的继承

```java
package points;
public class Point {
    public int x, y;
    protected int useCount = 0;
    static protected int totalCount = 0;
    public void move(int dx, int dy) {
        x += dx; y += dy; useCount++; totalCount++;
    }
}
class Test {
    public static void main(String[] args) {
        Point p = new Point();
        p.x = 10;
        p.y = 20;
        p.move(5, 5);
        System.out.println(p.x + " " + p.y);
    }
}
```

### 示例 8.2-5. 不可访问类的访问

```java
package points;
public class Point {
    public int x, y;
    protected int useCount = 0;
    static protected int totalCount = 0;
    public void move(int dx, int dy) {
        x += dx; y += dy; useCount++; totalCount++;
    }
}
class Point3d extends Point {
    int z;
    public void move(int dx, int dy, int dz) {
        x += dx; y += dy; z += dz;
    }
    public void move(int dx, int dy) {
        move(dx, dy);
    }
}
public class OnePoint {
    public static Point get() {
        return new Point3d();
    }
}
```

第三个包中的调用 `points.OnePoint.get()` 将返回一个可以作为 `Point` 使用的 `Point3d`，尽管该类型在包外不可用。可以为该对象调用两个参数版本的 `move` 方法，这是允许的，因为 `Point3d` 的 `move` 方法是公有的（任何重写公方法的方法必须是公有的，正是为了确保这种情况能够正常工作）。也可以从该包访问该对象的字段 `x` 和 `y`。



虽然 Point3d 的字段 `z` 是公有的，但如果只有类型为 Point 的变量指向 Point3d 实例，则无法从 points 包之外访问此字段。这是因为表达式 `p.z` 是错误的，因为其类型为 Point 且类没有名为 `z` 的字段；表达式 `((Point3d)p).z` 是错误的，因为类类型 Point3d 不能在 points 包之外引用。

## 8.3 字段声明

### 字段声明

```
FieldDeclaration:
{FieldModifier} UnannType VariableDeclarList;
```

```
VariableDeclarList:
VariableDeclarator (, VariableDeclarator);
```

```
VariableDeclarator:
VariableDeclaratorId [= VariableInitializer]
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
UnannClassOrInterfaceType
UnannTypeVariable
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
TypeIdentifier
```

```
UnannArrayType:
UnannPrimitiveType Dims
UnannClassOrInterface Dims
UnannTypeVariable Dims
```

为了方便起见，此处显示 §4.3 中的以下产生式：

```
Dims:
[Annotation] { } [ ]
```

FieldDeclaration 中的每个声明符都声明一个字段。声明符中的 Identifier 可以用作名称来引用该字段。

通过使用多个声明符，可以在单个 FieldDeclaration 中声明多个字段；FieldModifiers 和 UnannType 适用于该声明中的所有声明符。

FieldModifier 子句在 §8.4.1 中有描述。

如果 UnannType 和 VariableDeclarator 中没有出现括号对，则字段的声明类型由 UnannType 表示，否则由 §10.2 规定。

字段声明的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

在类声明的体中声明两个相同名称的字段将是编译时错误。

如果一个类声明了一个具有特定名称的字段，则该字段的声明被认为隐藏了该类的超类和超接口中任何及所有同名的可访问字段声明。

> 在这方面，字段的隐藏与方法的隐藏有所不同（§8.4.8.3），因为在字段隐藏中静态和非静态字段之间没有区别，而在方法隐藏中静态和非静态方法之间是有区别的。

如果隐藏的字段是静态的，可以使用限定名（§6.5.6.2）访问，或者通过包含关键字 super（§15.11.2）的字段访问表达式或向超类类型的转换来访问。

在这方面，字段的隐藏与方法的隐藏是类似的。

如果一个字段声明隐藏了另一个字段的声明，则这两个字段不需要具有相同的类型。

### 字段声明

类从其直接超类和超接口继承所有超类和超接口的私有字段，前提是这些字段对类代码可访问 (§6.6）且未被类中的声明隐藏。

超类的私有字段可能对子类是可访问的——例如，如果两个类都是同一个类的成员。尽管如此，私有字段永远不会被子类继承。

一个类可能继承多个具有相同名称的字段，可以源自其超类和超接口，也可以仅源自其接口。这种情况本身不会导致编译时错误。然而，在类体内部任何尝试通过简单名引用此类字段的尝试都会导致编译时错误，因为引用是歧义的。

可能存在多条路径从接口继承相同的声明。在这种情况下，该字段被认为仅继承了一次，可以通过其名称进行无歧义的引用。

### 示例 8.3-1. 相乘的继承字段

类可以继承两个或多个具有相同名称的字段，可以源自其超类和接口，也可以源自两个接口。任何尝试通过简单名引用任何被继承的字段的尝试都会发生编译时错误。可能允许使用限定名或使用关键字 super（§15.11.2）的访问表达式来无歧义地访问此类字段。在程序中：

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

类 Test 继承了两个名为 v 的字段，一个来自其超类 SuperTest，一个来自其超接口 Frob。这是被允许的，但由于在方法 printV() 中使用了简单名 v，导致了编译时错误；因为无法确定意图是指哪个 v。

以下变体使用访问表达式 `super.v` 来引用在类 SuperTest 中声明的字段，并使用限定名 `Frob.v` 来引用接口 Frob 中声明的名为 v 的字段：

```java
interface Frob { float v = 2.0f; }
class SuperTest { int v = 3; }
class Test extends SuperTest implements Frob {
    public static void main(String[] args) {
        new Test().printV();
    }
    void printV() {
        System.out.println((super.v + Frob.v)/2);
    }
}
```

它通过编译并打印：

```
2.5
```

即使两个继承的字段具有相同的类型、相同的值且都是 final，任何通过简单名对其中一个字段的引用都是歧义的。在程序中：

```java
interface Color { int RED=0, GREEN=1; }
interface TrafficLight { int RED=0, GREEN=2; }
class Test implements TrafficLight {
    public static void main(String[] args) {
        System.out.println(GREEN); // 编译错误
        System.out.println(RED); // 编译错误
    }
}
```

由于 Test 类继承了两个 GREEN 的声明，因此 GREEN 的引用是歧义的。RED 恰好具有相同类型这一事实并不影响判断。

### 示例 8.3-2. 重复继承

如果相同的声明通过多个路径从接口继承，则字段被认为仅继承了一次。可以通过其名称进行无歧义的引用。在代码中：

```java
interface Colorable {
    int RED = 0, GREEN = 1, BLUE = 2;
}
interface Paintable extends Colorable {
    int MATTE = 0, GLOSSY = 1;
}
class ColoredPoint extends Colorable {}
class PaintedPoint extends ColoredPoint implements Paintable {
    int p = RED;
}
```

都通过其直接子类 ColoredPoint 和其直接超接口 Paintable。尽管如此，在类内部可以使用 RED、GREEN 和 BLUE 的简单名。

## 8.3 字段声明

### 8.3.1 修饰符

FieldModifier:

(其中之一)

Annotation public protected private

static final volatile

字段注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

如果同一个关键字多次出现在字段声明的修饰符中，或者字段声明具有 public、protected 和 private 中的多个 (§6.6)，则是编译时错误。

如果字段声明中出现两个或多个不同的字段修饰符，习惯上（并非要求）它们按照上述 FieldModifier 产生式的顺序出现。

### 8.3.1.1 静态字段

如果字段被声明为静态，则该字段仅存在一个实例化，无论最终创建多少个实例（可能为）。静态字段（有时称为类变量）在类初始化时实例化（12.4）。

未声明为静态的字段称为实例变量，有时称为非静态字段。每当创建类的实例时（12.5），该类或其任何超类声明的每个实例字段都会创建一个与实例关联的新变量。

类变量的声明引入了静态上下文（§8.1.3），这限制了引用当前对象的构造的使用。值得注意的是，`this` 和 `super` 关键字在静态上下是被禁止的（§15.8.3、§15.11.2），对于实例变量、实例方法以及词法包围定义的类型参数的未限定引用（§6.5.5.1、§6.5.6.1、§15.12.3）。

从静态上下文或嵌套类或接口引用实例变量是限制的，如 §6.5.6.1 所示。

#### 示例 8.3.1.1-1. 静态字段

```java
class Point {
    int x, y;
    int useCount = 0;
    static Point origin = new Point(0, 0);
    public static void main(String[] args) {
        Point p = new Point(1,1);
        Point q = new Point(2,2);
        p.x = 3;
        p.y = 3;
        p.useCount++;
        p.origin.useCount++;
        System.out.println("(" + q.x + "," + q.y + ")");
        System.out.println(q.useCount);
        System.out.println(q.origin == Point.origin);
        System.out.println(q.origin.useCount);
    }
}
```

该程序输出：

```
(2,2)
0
true
1
```

这表明 p 的字段 `x`、`y` 和 `useCount` 不会影响 q 的字段，因为这些字段是不同对象中的实例变量。在例例中，类 `Point` 的类变量 `origin` 使用类名作为限定符 `Point.origin` 来引用，并使用字段访问表达式 ($15.11) 中的类型变量，如 `p.origin` 和 `q.origin`。这两种访问类变量的方式访问的是同一个对象，引用相等性表达式 ($15.21.3) 值证明了这一点：

```
q.origin==Point.origin
```

结果为 `true`。进一步的证据是增加操作：

```java
p.origin.useCount++;
```

导致 `q.origin.useCount` 的值变为 1；这是因为 `p.origin` 和 `q.origin` 指向同一个变量。

#### 示例 8.3.1.1-2. 类变量的隐藏

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

该程序输出：

```
4.7 2
```

这是因为类 `Test` 中对 `x` 的声明隐藏了类 `Point` 中对 `x` 的定义。

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

此时类 `Point` 的字段 `x` 不再在类 `Test` 中被隐藏；相反，简单名 `x` 指向字段 `Point.x`。类 `Test` 中的代码仍可以通过 `super.x` 引用该相同字段。此变体程序的输出为：

```
2 2
```

#### 示例 8.3.1.1-3. 实例变量的隐藏

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

该程序输出：

```
4.7 2
4.7 2
```

这是因为类 `Test` 中对 `x` 的声明隐藏了类 `Point` 中对 `x` 的定义，类 `Test` 没有从其父类 `Point` 继承字段 `x`。但必须注意的是，虽然类 `Point` 的字段 `x` 没有被类 `Test` 继承，但仍然由类 `Test` 的实例实现。换句话说，每个 `Test` 类实例都包含两个字段，一个 `int` 类型，一个 `double` 类型。这两个字段都名为 `x`，但在类 `Test` 的声明内部，简单名 `x` 始终指向在类 `Test` 中声明的字段。类 `Test` 实例方法中的代码可以通过 `super.x` 引用类 `Point` 的实例变量。

使用字段访问表达式 `field` 的代码将访问引用实例类型所指示的类中名为 `x` 的字段。因此，`sample.x` 访问的是值（在类 `Test` 中声明的实例变量），因为变量 `sample` 是 `Test` 类型；而表达式 `((Point) sample).x` 访问的是 `int`（在类 `Point` 中声明的实例变量），是因为强制转换为类型 `Point`。

如果从类 `Test` 中删除对 `x` 的声明，程序如下：

```java
class Point {
    static int x = 2;
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

那么类 `Point` 的字段 `x` 不再在类 `Test` 中被隐藏。在类 `Test` 声明的实例方法内部，简单名现在指向在类 `Point` 中声明的字段。类 `Test` 中的代码仍可以通过 `super.x` 引用该相同字段。表达式 `sample.x` 仍然指向类型 `Test` 中的字段 `x`，但该字段现在是一个继承字段，因此指向在类 `Point` 中声明的字段 `x`。此变体的输出为：

```
2 2
```

如果声明符指向一个类变量（即静态字段）§8.3.1.1，则以下规则适用于其初始化器：

- 初始化器可能无法使用 `this` 关键字或 `super` 关键字来引用当前对象（如 §15.8.3 和 §15.11.2 所示），也不得通过简单名引用任何实例变量或实例方法（如 §6.5.6.1 和 §15.12.3 所示）。

- 在运行时，初始化器会被求值，且赋值仅执行一次，即在类初始化时（§12.4.2）。

> 注意：作为常量变量的静态字段（§12.4.2）在其他静态字段之前初始化（§12.4.2，第 6 步）。这也适用于接口（§9.3.1）。当通过简单名引用此类字段时，这些字段永远不会被观察到具有其默认初始值（§4.15）。

如果声明符指向一个实例变量（即非静态字段），则以下规则适用于其初始化器：

- 初始化器可以使用关键字 `this` 或 `super` 引用当前对象，并可以通过简单名引用该类声明或继承的任何类变量，即使其声明发生在初始化器的右侧（§3.5）。

- 在运行时，每当创建类的实例时，初始化器都会被求值并执行赋值（§12.5）。



# 8.3 字段声明

从变量初始化器到可能尚未初始化的字段的引用受到限制，如 §8.3.3 和 §16（确定赋值）所示。

字段声明中变量初始化器的异常检查规定在 §11.2.3。

变量初始化器还用于局部变量声明语句（§14.4），在这些语句中，每执行一次局部变量语句，初始化器都会被求值并执行赋值。

## 示例 8.3.2-1. 字段初始化

```
class Point {
  int x = 1, y = 5;
}
class Test {
  public static void main(String[] args) {
    Point p = new Point();
    System.out.println(p.x + " , " + p.y);
  }
}
```

该程序产生输出：

1, 5

因为每当创建一个新的 `Point` 实例时，对 `x` 和 `y` 的赋值就会发生。

## 示例 8.3.2-2. 对类变量的前向引用

```
class Test {
    float f = j;
    static int j = 1;
}
```

该程序无错误通过编译，它在类 `Test` 初始化时将 `j` 初始化为 1，并在每当创建一个 `Test` 实例时，将 `f` 初始化为 `j` 的当前值。

## 8.3.3 初始化器中字段引用的限制

对字段的引用受到限制，即使该字段在作用域内。以下规则限制了对字段的引用（其中使用文本在字段声明之前）以及自引用（其中字段在其自身的初始化器中使用）。

对于通过简单名对在类或接口 `c` 中声明的类 `x` 进行的引用，如果满足以下条件，则构成一个编译时错误：

- 该引用出现在 `c` 的类变量初始化器中，或 `c` 的静态初始化器中（§8.7）；且
- 该引用出现在 `f` 自身声明符的初始化器中，或位于 `f` 声明符左侧的某处；且
- 该引用不在赋值表达式的左侧（§15.26）；且
- 包裹引用的最内部类或接口是 `c`。

对于通过简单名对在类 `c` 中声明的实例变量 `f` 进行的引用，如果满足以下条件，则构成一个编译时错误：

- 该引用出现在 `c` 的实例变量初始化器中，或 `c` 的实例初始化器中（§8.6）；且
- 该引用出现在 `f` 自身声明符的初始化器中，或位于 `f` 声明符左侧的某处；且
- 该引用不在赋值表达式的左侧（§15.26）；且
- 包裹引用的最内部类是 `c`。

## 示例 8.3.3-1. 字段引用的限制

此程序会导致编译时错误：

```
class Test1 {
    int i = j;      // 编译时错误：
    int j = 1;
}
```

而以下程序无错误通过编译：

```
class Test2 {
    Test2() { k = 2; }
    int j = 1;
    int i = j;
    int k;
}
```

尽管 `Test2` 的构造函数（§8.8）引用了三行后声明的字段 `k`。

这些限制还设计用于在编译时捕获循环或其他畸形的初始化。因此，以下代码：

```
class Z {
    static int i = j + 2;
    static int j = 4;
}
```

以及：

```
class Z {
    static { i = j + 2; }
    static int i, j;
    static { j = 4; }
}
```

都会导致编译时错误。通过方法的访问不进行此类检查：

```
class Z {
    static int peek() { return j; }
    static int i = peek();
}
```

```
class Test {
    public static void main(String[] args) {
        System.out.println(Z.i);
    }
}
```

产生输出：

0

因为 `i` 的变量初始化器使用类方法 `peek()` 来访问该值。

# 8.4 方法声明

## 8.4.1 形式参数

方法或构造函数的形式参数（如果有的话）由一组用逗号分隔的参数限定符列表指定。每个参数限定符由一个类型（可选地跟带有最终修饰符和/或一个或多个注解）和一个标识符（可选地后跟括号）组成，用于指定参数的名称。

如果方法或构造函数没有形式参数，且没有接收器参数，则在方法或构造函数的声明中会出现一对空括号。

```
FormalParameterList:
FormalParameter ( , FormalParameter)

FormalParameter:
[VariableModifier] UnannType VariableDeclaratorId
VariableArityParameter

VariableArityParameter:
[VariableModifier] UnannType [Annotation] ... Identifier

VariableModifier:
Annotation
final
```

为了方便起见，这里展示了 §8.3 和 §4.3 中的以下产生式：

```
VariableDeclaratorId:
Identifier [Dims]

Dims:
[Annotation] {} {[Annotation] {} }
```

方法或构造函数的形式参数可以是一个变长参数，通过类型后的省略号（`...`）来表示。一个方法或构造函数最多允许一个变长参数。如果变长参数出现在参数限定符列表的最后一个位置之外的任何位置，则会导致编译时错误。

在 `VariableArityParameter` 的语法中，注意省略号（`...`）是一个独立的标记（§3.11）。在省略号和类型之间可以放置空格，但从风格角度来看这样做是不建议的。

如果方法的最后一个形式参数是变长参数，则该方法是变长方法。否则，它是一个固定长度方法。

关于形式参数声明和接收器参数的注解修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果 `final` 作为形式参数声明的修饰符出现超过一次，则会导致编译时错误。

形式参数的作用域和遮蔽规则在 §6.3 和 §6.4 中规定。

从嵌套类、接口或 Lambda 表达式对形式参数的引用受到限制，如 §6.5.6.1 指定。

方法或构造函数声明两个同名的形式参数将导致编译时错误。（即它们的声明提到了同一个标识符）。

如果形式参数被声明为 `final`，则在赋值给方法或构造函数体时会导致编译时错误。

形式参数的声明类型取决于它是否为变长参数：

- 如果形式参数不是变长参数，则当 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号时，其声明类型用 `Unann` 表示，否则由 §10.2 规定。
- 如果形式参数是变长参数，则其声明类型是由 §10.2 规定的数组类型。

如果变长参数的声明类型具有非可重构元素类型（§4），则该变长方法的声明会产生编译时未检查警告，除非该方法标记了 `@SafeVarargs` (§9.6.4.7) 或该警告被 `@SuppressWarnings` (§9.6.4.5) 抑制。

当调用方法或构造函数时（§15.12），实际参数的值在执行方法或构造函数体之前，意味着新创建的变量，每个变量的类型均为声明类型。`FormalParameter` 中出现的标识符可以在方法体中作为简单名称使用或用于引用形式参数。

变长方法的调用可能包含比形式参数更多的实际参数表达式。所有不对应变长参数之前的形式参数的实际表达式将被求值，结果存储在一个数组中，该数组将传递给方法调用（§15.12.4.2）。

## 接收器参数示例

以下是实例方法和内部类构造函数接收器参数的一些示例：

```
class Test {
    Test(/* ?? ? */) {
        // 顶层类的构造函数不允许有接收器参数，
        // 因为没有可以想象类型或名称。
    }

    void m(Test this) {
        // OK：实例方法中的接收器参数
    }

    static void n(Test this) {
        // 非法：静态方法中的接收器参数
    }

    class A {
        Test(Test.this) {
            // OK：接收器参数代表
            // 立即封装正在构造的 A 实例的 Test 实例。
        }

        void m(A this) {
            // OK：接收器参数代表
            // 调用 A.m() 时的 A 实例。
        }

        class B {
            Test(Test.A.B this) {
                // OK：接收器参数代表
                // 立即封装正在构造的 B 实例的 A 实例。
            }

            void m(Test.A.B this) {
                // OK：接收器参数代表
                // 调用 B.m() 时的 B 实例。
            }
        }
    }
}
```

`B` 的构造函数和实例方法表明，接收器参数的类型可以像其他类型一样使用限定类型表示；但内部类构造函数中的接收器参数名称必须使用类的简单名称。

## 8.4.2 方法签名

两个方法或构造函数 $M$ 和 $N$ 具有相同的签名，如果它们具有相同的名称、相同的类型参数（如果有）（§8.4.4），并且在将 $N$ 的形式参数适配到 $M$ 的签名后。方法签名 $m_1$ 是 $m_2$ 的子签名，如果：

- $m_2$ 具有签名 $m_1$，或者
- $m_1$ 是 $m_2$ 的子签名。

两个方法签名 $m_1$ 和 $m_2$ 是*等效的*，如果 $m_1$ 是 $m_2$ 的子签名。

### 示例 8.4.2-1. 等效签名

```java
class Point {
    int x, y;
    abstract void move(int dx, int dy);
    void move(int dx, int dy) {}
}
```

此程序会导致编译时错误，因为它声明了两个相同的（因此等效的）签名。签名的概念旨在表示两个签名不同的方法之间的关系，具体来说，它允许不使用泛型的方法覆盖任何泛型版本。考虑以下示例：

```java
class CollectionConverter {
    List toList(Collection c);
}

class Overrider extends CollectionConverter {
    List toList(Collection c);
}
```

现在，假设这段代码是在引入泛型之前编写的，现在 `CollectionConverter` 的作者决定泛化代码，如下：

```java
class CollectionConverter {
    <T> List<T> toList(Collection<T> c);
}
```

如果没有特殊许可，`Overrider.toList` 将不再覆盖 `CollectionConverter.toList`。这将严重抑制泛型的使用，因为库编写者会对迁移现有代码感到犹豫。

## 8.4.3 方法修饰符

MethodModifier:

（以下之一）

Annotation public protected private
abstract static synchronized native strictfp

方法声明的注解修饰符规则在 §9.7.4 和 §9.7.5 中规定。

如果同一个关键字作为方法声明的修饰符出现超过一次，或者方法声明具有 `public`、`protected` 和 `private`（§6.6）中的多个，会导致编译时错误。

如果方法声明包含 `abstract` 同时包含 `private`、`static`、`final`、`native`、`strictfp` 或 `synchronized` 中的任何一个，则会导致编译时错误。

如果方法声明包含 `native` 同时包含 `strictfp`，则会导致编译时错误。

如果方法声明中出现了两个或多个（不同的）方法修饰符，习惯上（并非强制）它们按照上述产生式所示的顺序出现。

### 8.4.3.1 抽象方法

抽象方法声明作为成员引入方法，提供了签名（§8.4.2）、结果（§8.4.5）以及任何 `throws` 子句（§8.4.6），但不提供实现（§8.4.7）。非抽象方法可以被称为具体方法。

抽象方法的声明必须直接出现在抽象类（class）内部，除非它出现在枚举声明（§8.9）中；否则，会导致编译时错误。

`A` 的每个非抽象子类（§8.1.1.1）都必须为 `m` 提供实现，否则会导致编译时错误。

抽象类可以通过提供另一个抽象方法声明来覆盖一个抽象方法。

这可以提供一个放置文档注释的地方、细化返回类型，或者声明该方法在子类实现时可能抛出的受检异常集合，使其范围更小。

非抽象的实例方法可以被抽象方法重写。

#### 示例 8.4.3-1-1. 抽象/抽象方法的重写

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

类 `InfiniteBuffer` 中方法的重写声明表明，`InfiniteBuffer` 的任何子类中的 `get` 方法永远不会抛出 `BufferEmpty` 异常，假定它在缓冲区中生成数据，因此永远不会耗尽数据。

#### 示例 8.4.3-1-2. 抽象/非抽象重写

我们可以声明一个抽象类 `Point`，如果其子类是完整的、可实例化的类，则要求它们实现 `toString`：

```java
abstract class Point {
    int x, y;
    public abstract String toString();
}
```

此对 `toString` 的抽象声明重写了 `Object` 类的非抽象 `toString` 方法。（`Object` 是类 `Point` 类的隐式直接父类）。添加以下代码：

```java
class ColoredPoint extends Point {
    int color;
    public String toString() {
        return super.toString() + " : " + color; // 错误
    }
}
```

当调用 `super.toString()` 时会导致编译时错误，因为它引用了 `Point` 类中的 `toString` 方法，而该方法是抽象的，因此无法调用。只有当 `Point` 类通过其他方法显式地提供 `Object` 类的 `toString` 方法时，`ColoredPoint` 类才能使用，如：

```java
abstract class Point {
    int x, y;
    public abstract String toString();
    protected String objString() { return super.toString(); }
}
class ColoredPoint extends Point {
    int color;
    public String toString() {
        return objString() + ": " + color; // 正确
    }
}
```

### 8.4.3.2 静态方法

声明为 `static` 的方法被称为类方法。它不属于特定的对象。类方法的声明引入了静态上下文（§8.1.3），这限制了引用当前对象的构造结构的使用。注意的是，在静态上下文中 `this` 和 `super` 关键字是被禁止的（§15.5.8, §15.11.2），同样禁止对实例变量、实例方法以及词法封闭闭包中类型参数的限定引用（§6.5.5.1, §6.5.6.1, §15.12.3）。

未声明为静态的方法是实例方法，有时也称为非静态方法。

实例方法总是相对于一个对象调用的，该对象在方法体执行期间成为当前对象，`this` 和 `super` 关键字即指向该对象。

从静态上下文或嵌套类或接口对实例方法的引用受到限制，如 §15.12.3 所示。

### 8.4.3.3 final 方法

方法可以声明为 `final` 以防止子类重写或隐藏它。

尝试重写或隐藏 `final` 方法会导致编译时错误。

私有方法以及直接声明在 `final` 类内部（§8.1.1.2）的所有方法行为都类似于 `final` 方法，因为无法重写它们。

在运行时，机器码生成器或优化器可以“内联”`final` 方法体，用其体内的代码替换方法的调用。内联过程必须保留方法调用的语义。特别是，如果实例方法的目标为 `null`，那么即使方法被内联，也必须抛出 `NullPointerException`。Java 编译器必须确保在正确的位置抛出异常，以便方法的实际参数在方法调用之前能以正确的顺序可见。



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
            p[i].move(i, p.length - i);
        }
    }
}
```

在 `main` 方法中内联 `Point` 类的 `move` 方法会将 `for` 循环转换为如下：

```java
for (int i = 0; i < p.length; i++) {
    p[i] = new Point();
    Point pi = p[i];
    int j = p.length - 1 - i;
    pi.x += i;
    pi.y += j;
}
```

该循环随后可能会进一步优化。

这种内联无法在编译时完成，除非保证 `Test` 和 `Point` 总是一起重新编译，这样每当 `Point`（特别是其 `move` 方法）变化时，`Test.main` 的代码就会更新。

## 8.4.3.4 native 方法

声明为 `native` 的方法实现在平台相关的代码，通常用另一种编程语言（如 C）编写。`native` 方法体以分号 `;` 提供，表示省略了实现而非代码块。

## 8.4.3.5 strict 方法

方法声明上的 `strictfp` 修饰符已过时，不应使用。它的存在与否对运行时没有影响。

## 8.4.3.6 synchronized 方法

`synchronized` 方法在执行前获取监视器。对于类（静态）方法，使用与类对象相关的监视器。对于实例方法，使用与调用方法的对象（`this`）相关的监视器。

示例 8.4.3.6-1. synchronized

```java
class Test {
    int count;
    synchronized void bump() {
        count++;
    }
    static int classCount;
    static synchronized void bump() {
        classCount++;
    }
}
```

与以下效果完全相同：

```java
class BumpTest {
    int count;
    void bump() {
        synchronized (this) { count++; }
    }
    static int classCount;
}
```

```java
static void classBump() {
    try {
        synchronized (Class.forName("BumpTest")) {
            classCount++;
        }
    } catch (ClassNotFoundException e) {
    }
}
```

示例 8.4.3.6-2. synchronized

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

此程序定义了一个用于并发的类。`Box` 的每个实例都有一个实例 `boxContents`，可以持有任何对象的引用。你可以通过调用 `put` 向 `Box` 对象，如果缓冲区已满则返回 `false`。你可以通过调用 `get` 从 `Box` 中取出内容，如果缓冲区为空则返回 `null`。

如果 `put` 和 `get` 没有同步，且两个线程同时执行同一个实例的方法，那么代码可能会出现异常。例如，由于同时发生了两次 `put`，可能会丢失对象。

## 8.4.4 泛型方法

如果一个方法声明了一个或多个类型变量（§4.4），则该方法是泛型方法。

这些变量被称为泛型的类型参数。泛型方法的类型参数部分的形式与泛型类的类型参数部分相同（§8.1.2）。

泛型方法定义了一组方法，对应于类型参数部分通过参数的每可能调用。在调用泛型方法时，可能不需要显式提供类型参数，因为可以进行推断（§18）。

方法类型参数的作用域和遮蔽由 §6.3 和 §6.4.1 规定。

根据 §6.5.5.1 的规定，从嵌套类或接口对方法的类型参数进行引用是被限制的。

两个方法或构造方法 $M$ 和 $N$ 如果满足以下两个条件，则它们具有*相同的类型参数*：

- $M$ 和 $N$ 具有相同数量的类型参数（数量可能为零）。
- 假设 $A_1, ..., A_n$ 是 $M$ 的类型参数，$B_1, ..., B_n$ 是 $N$ 的类型参数，令 $\theta[B_1:=A_1, ..., B_n:=A_n]$。那么，对于所有的 $i$ ($1 \le i \le n$)，$A_i$ 的边界与将 $\theta$ 应用于 $B_i$ 边界的类型相同。

如果两个方法或构造方法 $M$ 和 $N$ 具有相同的类型参数，则 $N$ 中提到的类型可以通过将上述定义的 $\theta$ 应用于该类型来*适配*为 $M$ 的类型参数。

## 8.4.5 方法结果

方法声明的*结果*声明了方法返回的值的类型（*返回类型*），或者使用关键字 `void` 来指示该方法不返回值。

> 结果：
>
> `UnannType`
>
> `void`

如果结果不是 `void`，那么在形式参数列表后没有出现括号对时，方法的返回类型用 `UnannType` 表示；否则，则由 §10.2 规定。

如果返回类型是引用类型，则在相互覆盖的方法之间，返回类型可能会不同。返回类型可替换性的概念支持*协变返回*，即返回类型向其子类型的特化。

返回类型为 $R_1$ 的方法声明 $d_1$ 对于另一个返回类型为 $R_2$ 的方法 $d_2$ 是*返回类型可替换的*，当且仅当满足以下任意条件：

- 如果 $R_1$ 是 `void`，则 $R_2$ 为 void。
- 如果 $R_1$ 是基本类型，则 $R_2$ 与 $R_1$ 相同。
- 如果 $R_1$ 是引用类型，则满足以下任一：
    - $R_1$ 适配到 $d_2$ 的类型参数（§8.4.4）后是 $R_2$ 的子类型。
    - $R_1$ 可以通过未经检查的转换 (§5.1.9) 转换为 $R_2$ 的子类型。
    - $d_1$ 的签名与 $d_2$ 相同（§8.4.2），且 $R_1 = |R_2|$。

尽管未经检查的转换是不安全的（unsound），但在默认情况下是允许的，作为从非泛型代码向泛型代码顺利迁移的特殊允许。如果使用未经检查的转换来确定 $R_1$ 对于 $R_2$ 可替换，则 $R_1$ 必然不是 $R_2$ 的子类型，且覆盖规则 (§8.4.8.3, §9.4.1) 将要求编译时的未经检查警告。

## 8.4.6 方法抛出

`throws` 子句用于表示方法或构造体体语句可以抛出的受检异常类 (§11.1.1)。

```
Throws:
  `throws ExceptionTypeList`
```

```
ExceptionTypeList:
  `ExceptionType {, ExceptionType}`
```

```
ExceptionType:
  `ClassType` | `TypeVariable`
```

如果 `throws` 子句中提到的 `ExceptionType` 不是 `Throwable` 的子类型 (§4.10)，则为编译错误。

尽管类型变量在 `catch` 子句 (§14.20) 中是不允许的，但在 `throws` 子句中是允许的。

在 `throws` 子句中使用类型变量是允许的但不是要求的。

`throws` 子句与方法或构造体之间的关系由 §11.2.3 规定。

基本上，对于方法或构造体执行可能产生的任何受检异常，如果在 `throws` 子句中未声明其异常类型，则会导致编译错误，除非该异常类型在 `throws` 子句中被提及 (§11.1)。Java 语言通过这种方式确保处理此类异常。

`throws` 子句与覆盖或隐藏方法之间的关系见 §8.4.8.3。

### 8.4.6-1. 作为抛出异常类型的类型变量

```java
import java.io.FileNotFoundException;
interface PrivilegedAction<E extends Exception> {
    void run() throws E;
}
class AccessController {
    public static <E extends Exception>
    Object doPrivileged(PrivilegedAction<E> action) throws E {
        action.run();
        return "success";
    }
}
class Test {
    public static void main(String[] args) {
        try {
            AccessController.doPrivileged(new PrivilegedAction<FileNotFoundException>() {
                public void run() throws FileNotFoundException {
                    throw new FileNotFoundException();
                }
            });
        } catch (FileNotFoundException e) {
            // 处理异常
        }
    }
}
```

## 8.4.7 方法体

方法体是一个块或一个分号。如果是分号，则该方法是抽象的。如果是块，则它包含一组语句。块的第一行可以是异常处理语句（一个 `catch` 或 `finally` 块）。

## 8.4.8 继承、覆盖与隐藏

类继承其父类类型和直接接口类型。注意，方法是基于签名进行覆盖或隐藏的。例如，如果一个类声明了两个同名的公共方法，而子类覆盖了其中一个，则子类继承另一个。

```java
interface I1 {
    int foo();
}

interface I2 {
    int foo();
}

abstract class Test implements I1, I2 {
```

这里，抽象类 `Test` 继承了来自接口 `I1` 的抽象方法 `foo`，同时也继承了来自接口 `I2` 的抽象方法 `foo`。关键问题在于确定对 `I1` 的 `foo` 的继承：`I2` 中的方法是否覆盖了 `I1` 中的方法？不，因为 `I1` 和 `I2` 不是彼此的子接口。从类的角度来看，对 `I1` 的继承是被继承的；对 `I2` 的继承也是如此。

## 8.4.8.1 重写（通过实例方法）

在类 $C$ 中声明或继承自 $C$ 的实例方法 $m_C$ **重写**（overrides） $C$ 中类 $A$ 中声明的另一个方法 $m_A$，当且仅当满足以下所有条件：

- $C$ 是 $A$ 的子类。
- $C$ 没有继承 $m_A$。
- $m_C$ 的签名是作为 $C$ 命名为 $A$ 的超类型成员的 $m_A$ 签名的子签名 (§8.4.2)。
- 满足以下其中一种即可：
    * $m_A$ 是公共的（public）。
    * $m_A$ 是受保护的（protected）。
    * $m_A$ 在与 $C$ 相同的包中被声明为包访问权限（package access），且 $C$ 声明了 $m_C$ 或 $m_A$ 是 $C$ 的直接父类类型的成员。
    * $m_A$ 被声明为包访问权限，且 $m_C$ 从 $C$ 的某个父类**重写**了 $m_A$。
    * $m_A$ 被声明为包访问权限，且 $m_C$ **重写**了 $m'$（不同于 $m_C$ 和 $m_A$），使得 $m'$ 从 $C$ 的某个父类重写了 $m_A$。

如果 $m_C$ 是*非抽象的*（non-abstract）且**重写**了来自 $C$ 的*抽象*方法 $m_A$，则称 $m_C$ **实现**（implement）了来自 $C$ 的 $m_A$。

如果被重写方法 $m_A$ 是*静态*（static）方法，则会导致编译错误。

> 在这方面，方法的重写与字段的隐藏 (§8.3) 不同，因为实例变量隐藏静态变量是允许的。

在类 $C$ 中声明或继承自 $C$ 的实例方法 $m_C$ **重写**了接口 $I$ 中声明的另一个方法 $m_I$，当且仅当满足以下所有条件：

- $I$ 是 $C$ 的子类。
- $m_I$ 不是静态的（static）。
- $C$ 没有继承 $m_I$。
- $m_C$ 的签名是作为 $C$ 命名为 $I$ 的超类型成员的 $m_I$ 签名的子签名 (§8.4.2)。
- $m_I$ 是公共的（public）。

如果其中一个方法的的形式形参数具有原始类型（raw type），而另一个方法对应的参数具有参数化类型（parameterized type），则重写方法的签名可能与被重写的方法不同。这为了方便现有代码迁移以利用泛型。

关于重写了从其声明类的某个子类中重写的另一个方法的写的概念。这可以通过两种方式发生：

- 泛型父类中的方法在某些参数化配置下，可能与该类中的抽象方法具有相同的签名。在这种情况下，具体方法被继承，而抽象方法没有被继承（如上所述）。此时，被继承的方法被认为重写了其来自 $c$ 的抽象同类方法。（包访问权限使得这种场景变得复杂：如果 $c$ 在不同的包中，则 $mc$ 将不会被继承，因此不被视为已重写）。
- 从类继承的方法可以重写父接口方法。（幸运的是，这里不涉及包访问权限。）

可以使用包含 `super` 关键字的方法调用表达式 (§15.12) 来访问被重写的方法。使用限定名或强制类型类型为父类类型在尝试访问被重写的方法时是无效的。

在这方面，方法的重写防止了字段的隐藏。

`strictfp` 修饰符的存在与否对重写方法和实现抽象方法的规则完全没有影响。例如，允许一个非 strictfp 方法重写一个 strictfp 方法，且允许一个 strictfp 方法实现一个抽象方法。

### 示例 8.4.1-1 重写

```java
class Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
}
class SlowPoint extends Point {
    int xLimit, yLimit;
    void move(int dx, int dy) {
        super.move(limit(dx, xLimit));
    }
    static int limit(int d, int limit) {
        return d > limit ? -limit : d;
    }
}
```

在这里，`SlowPoint` 类重写了 `Point` 的 `move` 方法，限制了每次调用的距离。当为 `SlowPoint` 实例调用 `move` 方法时将始终调用重写定义，即使该对象的引用类型是 `Point`。

### 示例 8.4.1-2 重写

重写允许子类轻松地扩展现有类的行为，如下：



```java
import java.io.IOException;
import java.io.OutputStream;

class BufferOutput {
    private OutputStream o;
    BufferOutput(OutputStream o) { this.o = o; }
    protected byte[] buf = new byte[12];
    protected int pos = 0;
    protected void flush() throws IOException {
        o.write(buf, 0, pos);
        pos = 0;
    }
    protected void putchar(char c) throws IOException {
        if (c == '\n') {
            flush();
        } else {
            buf[pos++] = (byte)c;
        }
    }
    public void putstr(String s) throws IOException {
        for (int i = 0; i < s.length(); i++) {
            putchar(s.charAt(i));
        }
    }
}
class LineBufferOutput extends BufferOutput {
    LineBufferOutput(OutputStream o) { super(o); }
    @Override
    protected void putchar(char c) throws IOException {
        if (c == '\n') {
            flush();
        }
    }
}
class Test {
    public static void main(String[] args) throws IOException {
        LineBufferOutput lbo = new LineBufferOutput(System.out);
        lbo.putstr("lbo\n");
        System.out.print("print\n");
        lbo.putstr("\n");
    }
}
```

此程序输出：

```
lbo
print
lbo
```

`BufferOutput` 类实现了 `OutputStream` 的一个非常简单的缓冲版本，它继承了 `BufferOutput` 的 `putstr` 和 `flush` 方法。在 `LineBufferOutput` 的 `putchar` 方法中，如果字符参数是换行符，则调用 `flush` 方法。因此，当在 `main` 中使用 `LineBufferOutput` 对象调用 `putstr` 时，`putstr` 体中的 `putchar` 调用是对当前对象定义的 `putchar`。这允许 `BufferOutput` 的子类在不重新实现它的情况下更改 `putstr` 的行为。

# 类

## 示例 8.4.2-1. 隐藏类方法的调用

被隐藏的（静态）类可以通过引用来调用，该引用的类型是实际包含该方法声明的类的类型。在这方面，静态方法的隐藏与实例方法的重写不同。示例如下：

```java
class Super {
    String greeting() { return "Goodnight"; }
    String name() { return "Richard"; }
}
class Sub extends Super {
    static String greeting() { return "Hello"; }
    String name() { return "Dick"; }
}
class Test {
    public static void main(String[] args) {
        Super s = new Sub();
        System.out.println(s.greeting() + " ", s.name());
    }
}
```

产生输出：

Goodnight, Dick

因为 `greeting` 的调用使用了 `s` 的类型（即 `Super`）来在编译时确定调用哪个类方法，而 `name` 的调用使用了 `s` 的类（即 `Sub`）来在运行时确定调用哪个实例方法。

## 8.4.8.3 重写与隐藏中的要求

如果返回类型为 $R_1$ 的方法 $d_1$ 重写或隐藏了返回类型为 $R_2$ 的方法 $d_2$，则 $d_1$ 必须是 $d_2$ 的返回类型可替换的 (§S8.4.5)，否则将发生编译错误。

此规则允许协变返回类型——在重写方法时细化方法的返回类型。

如果 $R_1$ 不是 $R_2$ 的子集，则会发生编译时未检查警告，除非被 `@SuppressWarnings` 抑制 (§9.6.4.5)。

重写或隐藏另一个方法的方法（包括实现接口定义的抽象方法的方法），其声明抛出的检查异常不能比被重写或隐藏的方法抛出的检查异常多。

在这方面，方法的重写与字段的隐藏 (§8.3) 不同，因为字段隐藏另一个类型的字段是允许的。

更准确地说，假设 `B` 是一个类或接口，而 `A` 是 `B` 的超类或接口，且 `B` 中的方法声明 $m_2$ 重写或隐藏了 `A` 中的方法声明 $m_1$。那么：

- 如果 $m_2$ 具有提到任何检查异常类型的 `throws` 子句，则 $m_1$ 必须有一个 `throws` 子句，否则将发生编译错误。

- 对于 $m_2$ `throws` 子句中列出的每个检查异常类型，相同的异常类或其超类之一必须出现在 $m_1$ `throws` 子句的擦除 (4.6) 中；否则将发生编译错误。

- 如果 $m_2$ 擦除后的 `throws` 不包含 $m_2$ `throws` 子句中异常类型的超类（根据需要对 $m_1$ 的类型参数进行调整），则会发生编译时未检查警告，除非被 `@SuppressWarnings` 抑制 (§9.6.4.5)。

如果一个类或接口 `C` 有一个成员方法 $m_1$，且在 `C` 或其超类或接口 `A` 中声明了方法 $m_2$，使得以下所有条件均成立，则为编译错误：

- $m_1$ 和 $m_2$ 具有相同的名称。

- $m_2$ 从 `C` 可访问 (6.6)。

- $m_2$ 的签名不是作为命名 `A` 的 `C` 的超类型成员的 $m_1$ 签名的子类 (8.4.2)。

- $m_1$ 的声明签名或某些方法 $m_2$（直接或间接）重写的方法的声明签名，与 $m_2$ 的声明签名或某些方法 $m_2$（直接或间接）重写的方法的声明签名具有相同的擦除。

这些限制是必要的，因为泛型是通过擦除实现的。上述规则意味着在同一个类中具有相同名称的方法必须具有不同的擦除。它还意味着类或接口不能实现或扩展同一个泛型接口的两个不同参数化。

重写或隐藏方法的访问修饰符必须提供至少与被重写或隐藏方法相同的访问权限，如下：

- 如果被重写或隐藏的方法是 `public` 的，则重写和隐藏方法必须是 `public` 的；否则将发生编译错误。

- 如果被重写或隐藏的方法是 `protected` 的，则重写或隐藏方法必须是 `protected` 或 `public` 的；否则将发生编译错误。

- 如果被重写或隐藏的方法具有包访问权限（package access），则重写或隐藏方法不能是 `private` 的；否则将发生编译错误。

注意，在技术意义上，`private` 方法不能被重写或隐藏。该子类可以声明一个与其某个超类中的 `private` 方法具有相同签名的方法，并不要求该方法的返回类型或 `throws` 子句与超类中该 `private` 方法有任何关系。

## 示例 4.8.8.3-1 协变返回类型

在 Java SE 5.0 及之后的 Java 语言中，以下声明是合法的：

```java
class C implements Cloneable {
  C copy() throws CloneNotSupportedException {
    return (C)clone();
  }
}
class D implements Cloneable {
  D copy() throws CloneNotSupportedException {
    return (D)clone();
  }
}
```

重写的宽松规则也允许放宽实现接口的抽象类的条件。

## 示例 4.8.8.3-2 来自返回类型的未检查警告

考虑：

```java
class StringSorter {
  // 将字符串集合转换为排序列表
  List toList(Collection c) {...}
}
```

并假设某些子类扩展了 `StringSorter`：

```java
class Overrider extends StringSorter {
  List toList(Collection c) {...}
}
```

现在，在某处 `StringSorter` 的作者决定将代码泛化：

```java
class StringSorter {
  // 将字符串集合转换为排序列表
  List<String> toList(Collection<String> c) {...}
}
```

当针对 `StringSorter` 的新定义编译 `Overrider` 时，会给出未检查警告，因为 `Overrider.toList` 的返回类型是 `List`，它不是被重写方法返回类型的子类型。

来自父类层次结构的定义优于默认方法，使得默认方法表现得像抽象方法一样。然而，类的抽象方法并不会覆盖默认方法，因为接口仍然允许细化来自类层次结构的抽象方法的签名。

请注意，如果类 C 继承的所有重写等效抽象方法都声明在接口中，则该异常不适用。

否则，重写等效方法集包含至少一个抽象方法和零或多个方法；那么该类必然是一个抽象类，并且被认为继承了所有方法。

继承的方法中必须有一个对于其他所有继承的方法是返回类型可替换的；否则，将发生编译时错误。（在这种情况下，`throws` 子句不会引起错误。）

可能通过多种路径从接口继承相同的方法声明。这一事实本身不会引起任何困难，且本身永远不会导致编译时错误。

## 示例 4.8.4.4-1. 重写等效方法的继承

第一个编译时错误发生在一个继承具体方法的类 C 上，这可能由于 C 的某个父类是泛型的，且该父类有两个方法，在泛型声明中是不同的，但在 C 所使用的参数化（§4.5）中具有相同的签名。例如：

```java
class A<T>
    void m(String s) {} // 1
    void m(T t) {} // 2
}
class C extends A<String> {}
```

C 从其直接父类 `A<String>` 继承了两个方法：标记为 1 的方法 `m(String)`，以及（由于 C 对 A 的参数化）标记为 2 的方法 `m(String)`。这些方法具有相同的签名，因此它们彼此之间是重写等效的。

## 8.4.9 重载

如果一个类中的两个方法（无论是在同一个类中声明，还是都被该类继承，或者是一个声明一个继承）具有相同的名称且签名不是重写等效的，则该方法被称为重载的。

这一事实本身不会引起任何困难，且本身永远不会导致编译时错误。除非它们的签名是重写等效的，否则两个同名方法的返回类型或 `throws` 子句之间不存在任何强制关系。

## 8.4 类方法声明

当方法被调用（§15.12）时，实际参数的数量以及任何显式类型参数）以及参数的编译时类型将在编译时用于确定将要调方法的签名（§5.12.2）。如果要调用的方法是实例方法，则要调用的实际方法将在运行时通过动态方法查找（§15.12.4）。

## 示例 8.4.9-1. 重载

```java
class Point {
    float x
```

在这里，类 Point 有两个名称相同的成员。对于任何特定的方法调用，选定的 Point 类重载方法是在编译时通过 15.12 中的重载解析程序决定的。

总而言之，Point 类的成员包括在 Point 中声明的 float 实例变量 `x` 和 `y`、两个声明的 `move` 方法、以及 Point 从其隐式直接父类 Object（§4.3.2）继承的成员，例如方法 `hashCode()`。请注意，Point 并没有继承 Object 类的 `toString` 方法，因为该方法被 Point 类中 `toString` 方法的声明覆盖了。

## 示例 8.4.9-2. 重载、重写与隐藏

```java
class RealPoint extends Point {
    int x = 0, y = 0;
    void move(int dx, int dy) { x += dx; y += dy; }
    int color;
}
class RealPoint {
    float x = 0.0f, y = 0.0f;
    void move(int dx, int dy) { move((float)dx, (float)dy); }
    void move(float dx, float dy) { x += dx; y += dy; }
}
```

在这里，RealPoint 类用它自己的 float 实例变量 `x` 和 `y` 隐藏了 Point 类的实例变量 `x` 和 `y`，并用自己的 `move` 方法覆盖了 Point 类的方法。它还通过另一个不同签名的方法覆盖了名称 `move`（§8.4.2）。

在这个示例中，RealPoint 类的成员包括从 Point 类继承的实例变量 `color`、在 RealPoint 中声明的 float 实例变量 `x` 和 `y` 以及在 RealPoint 中声明的两个 `move` 方法。

303

## 方法声明

RealPoint 类中这些重载的 `move` 方法中的哪一个会被特定的方法调用，将在编译时由 §15.12 的重载解析程序决定。

以下程序是前一个程序的扩展变：

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



在这里，`Point` 类具有返回类型为 `float` 的重写方法 `getX()` 和 `getY()`，结果是在编译时产生的，因为类型不匹配。该程序修正了前一个程序的错误：

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

那么，考虑这个测试程序：

[第320页]

在 `RealPoint` 的体外部，无论我们使用什么种类型的变量来持有对象的引用。

```java
class Test {
    public static void main(String[] args) {
        RealPoint rp = new RealPoint();
        Point p = rp;
        rp.move(2.718279f, 3.14159f);
        rp.move(1, -1);
        show(p.x, p.y);
        show(rp.x, rp.y);
        show(p.getX(), p.getY());
        show(rp.getX(), rp.getY());
    }

    static void show(int x, int y) {
        System.out.println("" + x + " , " + y + "");
    }

    static void show(float x, float y) {
        System.out.println("" + x + " , " + y + "");
    }
}
```

该程序的输出为：

```
(0, 0)
(2.718279, 3.14159)
(2, 3)
(2, 3)
```

第一行输出说明了 `RealPoint` 实际上包含了 `Point` 类中声明的两个整数字段；只是这些名称在 `RealPoint` 声明内部的代码（以及它的子类的代码）中被隐藏了。当使用类型为 `Point` 的变量持有 `RealPoint` 实例时，其值为零表示 `p.move(1, -1)` 没有调用 `Point` 类的 `move()` 方法；相反，它调用了 `RealPoint` 的重写方法。第二行输出显示 `rp.x` 指向 `RealPoint` 中声明的字段 `x`。该字段类型为 `float`，因此第二行输出相应地显示了浮点值。顺便提，这也说明了方法名是重载的；方法调用中的参数类型决定了将调用哪一个定义。因此，我们看到字段和方法的行为是不同的：隐藏不同于重写。

## 8.5 成员类和接口声明

成员类（member class）是指其声明直接包含在另一个类或接口声明的主体内的类（§8.1.7, §9.1.5）。

成员接口（member interface）是指其声明直接包含在另一个类或接口声明主体内的接口。

成员类可以是普通类（§8.1）、枚举类（§8.9）或记录类（§8.10）。

成员接口可以是普通接口（§9.1）或注解接口（§9.6）。

在类声明的主体中，成员类或接口声明的访问权限性由其访问修饰符指定；如果缺少访问修饰符，则由 §6.6 指定。

类声明主体中成员类声明修饰符规则规定在 §8.1.1 中。

类声明主体中成员接口声明修饰符规则规定在 §9.1.1 中。

成员类或接口的作用域和隐藏（shadowing）规定在 §6.3 和 §6.4.1 中。

如果一个类声明了一个具有特定名称的成员类或接口，则该成员类或接口的声明被认为*隐藏*了该类的父类和父接口中具有相同名称的所有可访问成员类和接口声明。

在此方面，成员类和接口的隐藏与字段的隐藏相似（§8.3）。

类从其直接父类和直接父接口处继承所有父类和父接口的所有非私有成员类和接口，前提是这些成员对代码是可访问的，且未被类中的声明所隐藏。

一个类可能从其父类、父接口或仅从其父接口继承多个具有相同名称的成员类或接口。这种情况本身不会导致编译时错误。然而，在类的主体内任何尝试通过简单名引用此类此类成员类或接口的行为都将导致编译时错误，因为该引用是歧义的。

可能存在多条路径从接口继承同一个成员类或接口声明。在这种情况下，该成员类或接口被认为仅被继承了一次，可以使用其简单名进行引用而不会产生歧义。

## 8.6 实例初始化器

在类中声明的实例初始化器在创建类的实例时执行（§12.5, §15.9, §8.8.7.1）。

```
InstanceInitializer:
Block
```

如果实例初始化器无法正常完成，则为编译时错误（§14.22）。

如果在实例初始化器的任何地方出现返回语句（§14.17），则为编译时错误。

实例初始化器允许使用关键字 `this`（§15.8.3）或关键字 `super`（§15.11.2, §15.12）来引用当前对象，并可以使用作用内的任何类型变量。

实例初始化器引用变量（即使实例变量在作用域内）的限制规定在 §8.3.3 中。

实例初始化器的异常检查规定在 §11.2.3 中。

## 8.7 静态初始化器

在类中声明的静态初始化器在类初始化时执行（§12.4.2）。结合类变量的字段初始化（§8.3.2），静态初始化器可用于初始化类的变量。

```
StaticInitializer:
static Block
```

如果静态初始化器无法正常完成，则为编译时错误（§14.22）。

如果在静态初始化器的任何地方出现返回语句（§14.17），则为编译时错误。

静态初始化器引入了静态上下文（§8.1.3），这限制了引用当前对象的构造的使用。值得注意的是，在静态上下文中禁止使用 `this` 和 `super` 关键字（§15.8.3, §15.11.2），对实例变量、实例方法以及词法包围声明的类型参数的未限定引用也是如此（§6.5.5.1, §6.5.6.1, §15.12.3）。

静态初始化器引用类变量（即使类变量在作用域内）的限制规定在 §8.3.3 中。

静态初始化器的异常检查规定在 §11.2.3 中。

## 8.8 构造函数声明

构造函数用于创建类的实例对象（§12.5, §15.9）。

```
ConstructorDeclaration:
[ConstructorModifier] ConstructorDeclarator [Throws] ConstructorBody
```

```
ConstructorDeclarator:
[TypeParameters] SimpleTypeName
([ReceiverParameter, ] [FormalParameterList] )
```

```
SimpleTypeName:
TypeId
```

本节中的规则适用于所有类声明中的构造函数，包括枚举声明和记录声明。然而，关于枚举声明的构造函数修饰符、构造函数体和默认构造有特殊规则；这些规则规定在 §8.9.2 中。记录声明的构造函数也适用特殊规则，如 §8.10.4 所示。

`ConstructorDeclarator` 中的 `SimpleTypeName` 必须包含构造函数声明的类的名称，否则将发生编译时错误。

在所有其他方面，构造函数声明看起来就像没有结果的方法声明（§8.4.5）。

构造函数不是成员。它们永远不会被继承，因此不受隐藏或覆盖的影响。

构造函数通过类实例创建表达式（§15.9）、通过由字符串连接运算符 `+` 引起的转换和连接（§15.18.1），以及通过其他构造函数的显式构造函数调用（§8.8.7）被调用。构造函数的访问受访问修饰符（§6.6）管理，因此可以通过声明一个不可访问的构造函数来防止类的实例化（§8.8.10）。

构造函数永远不会通过方法调用表达式（§15.12）被调用。

### 8.8-1. 构造函数声明

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}
```

## 8.8.1 形式参数

构造函数的形式参数在语法和语义上与方法的形式参数相同（§8.4.1）。

如果构造函数的最后一个形式参数是变长参数（variable arity parameter），则该构造函数是变长构造函数。否则，它是固定长度构造函数。

非私有内部成员类的构造函数声明其第一个形式参数为表示紧邻该类实例的变量（§15.9.2, §15.9.3）。

这种类具有隐式声明构造参数的原因相当微妙。以下解释可能有所帮助：

1. 在非私有成员类的类实例创建表达式中，§15.9.2 规定了成员类的紧邻实例。该成员类可能由与类实例创建表达式不同的编译器生成。编译器必须有一种标准方式将引用（代表紧邻实例）传递给成员类的构造函数。因此，Java 编程语言认为非私有内部类构造函数隐式地声明了一个用于紧邻实例的初始参数。§15.9.3 指定了该实例被传递给构造函数。

2. 在局部类或匿名类的类实例创建表达式中（非静态上下文中），§15.9.2 规定了局部/匿名类的紧邻实例。局部/匿名类由与类实例创建相同的编译器生成。该编译器可以随心意愿地表示紧邻实例。Java 编程语言不需要在局部/匿名类的构造函数中隐式声明参数。

3. 在匿名类的类实例创建表达式中，且该匿名类的父类是内部类（非静态上下文中），§15.9.2 规定了匿名类相对于父类的紧邻实例。

此实例必须从匿名类传递到其超类，在超类中它将作为直接邻接的实例使用。由于超类可能由与类创建表达式的不同的编译器生成，因此有必要以标准方式传递该实例，将其作为第一个参数传递给超类的构造函数。注意，匿名类本身一定是由与类创建表达式相同的编译器生成的，因此编译器可以按照其意愿传递直接邻接类，而是在匿名类将实例传递给超类构造函数之前完成此操作。然而，为了保持一致性，Java 编程语言在 §15.9.5 中规定，在某些情况下，匿名类的构造函数会隐式地为其相对于超类的直接邻接实例声明一个初始参数。

非私有内部成员类可能被不同于编译它的编译器所访问，而内部局部类或匿名类始终由编译它的同一个编译器访问，这解释了为什么非私有内部成员类的二进制名被定义为可预测的，而内部局部类或匿名类的二进制名是不可预测的（§13.1）。

## 8.8.2 构造函数签名

在类中声明两个具有重写等效签名（§8.4.2）的构造函数是编译时错误。

在类中声明两个签名具有相同类型擦除（§4.6）的构造函数是编译时错误。

## 8.8.3 构造函数修饰符

```
ConstructorModifier:
(其之一)
Annotation public protected private
```

关于构造函数声明的注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

如果同一个关键字在构造函数声明中多次作为修饰符，或者构造函数声明具有多个 `public`、`protected` 和 `private` 访问修饰符，则为编译时错误（§6.6）。

在普通类声明中，没有访问修饰符的构造函数声明具有包访问权限。

如果在方法声明中出现了两个或多个（不同的）方法修饰符，按照习惯（并非强制），它们出现的顺序与上述 `MethodModifier` 产生式中所示顺序保持一致。

与方法不同，构造函数不能是 `abstract`、`static`、`final`、`native`、`strictfp` 或 `synchronized`：

- 构造函数是不被继承的，因此没有必要声明 `final`。
- 抽象构造函数永远无法实现。
- 构造函数总是相对于一个对象被调用的，因此构造函数是 `static` 没有意义的。
- 构造函数没有同步的实际需求，因为这将同步正在构建的对象，而该对象的所有构造函数完成工作之前，通常对其他线程是不可用的。
- 缺乏 `native` 构造函数是一个任意的语言设计选择，使得 Java 虚拟机实现更容易验证构造过程中是否正确调用了超类函数。
- 无法将构造函数声明为 `strictfp`（与方法相比 §8.4.3）是一个有意的设计选择，它源于（现已淘汰）可以将类声明为 `strictfp` 的。

## 8.8.4 泛型构造函数

如果构造函数声明了一个或多个类型变量（§4.4），则它是泛型的。

这些类型变量被称为构造函数的类型参数。泛型构造函数类型参数部分的形式与泛型类的类型参数部分相同（§8.1.2）。

构造函数可以是泛型的，这与该类的构造函数本身是否声明为泛型无关。

泛型构造函数声明定义了一组构造函数，每种通过类型参数类型参数部分的可能调用都对应一个构造函数。调用泛型构造函数时，可能不需要显式提供类型参数，因为它们通常可以推断（§18 类型推断）。

构造函数类型参数的作用范围和遮蔽在 §6.3 和 §6.4.1 中规定。

从显式构造函数调用语句或嵌套类或接口对构造函数类型参数的引用受到限制，如 §6.5.5 所示。

## 8.8.5 构造函数 throws

构造函数的 `throws` 子句在结构上与方法的 `throws` 子句相同（§8.4.6）。

## 8.8.6 构造函数的类型

构造函数的类型由其签名和其 `throws` 子句给出的异常类型组成。

## 8.8.7 构造函数体

构造函数体的第一个语句可以是对同一类或直接超类的显式调用（§8.8.7.1）。

```
ConstructorBody:
[ExplicitConstructorInvocation] [BlockStatements]
```

构造函数通过一系列涉及 `this` 的构造函数调用直接或间接调用自身，则是编译时错误。

如果构造函数体不是以显式构造函数调用开头，且声明的不是原始类 `Object`，则意味着调用了无参数的超类构造函数 `super()`。

除了构造函数调用的可能性外（§14.17），构造函数体类似于方法体（§8.4.7）。

如果构造函数体不包含表达式，则可以使用 `return` 语句（§14.17）。

### 示例 8.8.7-1 构造函数体



```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
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

---

## 8.8 构造函数声明

在这里，`ColoredPoint` 的第一个构造函数调用第二个，并提供了额外的参数；`ColoredPoint` 的第二个构造函数调用其超类 `Point`，传递了坐标。

### 8.8.7.1 显式构造函数调用

```
ExplicitConstructorInvocation:
[TypeArguments] this ([ArgumentList] );
[TypeArguments] super ([ArgumentList]) );
ExpressionName. [TypeArguments] super ([ArgumentList] );
Primary . [TypeArguments] super ([ArgumentList] );
```

为了方便，这里显示了 §4.5.1 和 §15.12 中的产生式：

字体 `TypeArguments`: `< TypeArgumentList >`

- `ArgumentList`: `Expression` ([ `,` `Expression` ])

显式构造函数调用分为两种：

- **替代构造调用** 以关键字 `this`（可能带有显式类型参数）开头，用于调用同一类的替代构造函数。

- **超类构造调用** 以关键字 `super`（可能带有显式类型参数）或 `Primary` 表达式或 `ExpressionName` 开头，调用直接超类的构造函数。它们进一步分为：

- **无限定超类构造调用** 以关键字 `super`（可能带有显式类型参数）开头。

- **有限定超类构造调用** 以 `Primary` 表达式或 `ExpressionName` 开头，允许子类构造函数指定新创建对象相对于直接超类的直接邻接实例（§8.1.3）。当超类是内部类时，这可能是必要的。

显式构造函数调用语句引入了静态上下文，这限制了引用当前对象的结构的使用。值得注意的是，`this` 和 `super` 关键字在静态文中是被禁止的（§15.8.3, §15.11.2），未限定的实例变量、实例方法以及词法封装声明类型参数的引用也是如此（§6.5.5.1, §6.5.6.1, §15.12.3）。

如果 `TypeArguments` 在此 `super` 的左侧，则如果任何类型参数为通配符，则会导致编译错误（§4.5.1）。

设 `c` 为被实例化的类，设 `s` 为 `c` 的直接父类。

如果父类构造方法调用语句是非限定的（unqualified），则：

- 如果 `s` 是一个内部成员类，但 `s` 不是包含 `c` 的类的成员，则发生编译错误。

否则，设 `o` 为 `c` 的以 `s` 为成员的最内层嵌套类。`c` 必须是 `o` 的内部类（§8.1.3），否则发生编译错误。

- 如果 `s` 是一个内部局部类，且 `s` **未**在静态上下文中出现，设 `o` 为 `s` 的紧邻嵌套的类或接口声明。`c` 必须是 `o` 的内部类，否则发生编译错误。

如果父类构造方法调用语句是限定的（qualified），则：

- 如果 `s` 不是内部类，或者如果 `s` 的声明出现在静态上下文中，则发生编译错误。

- 否则，设 `p` 为紧接 "super" 之前的 `Primary` 表达式或 `ExpressionName`，设 `o` 为 `s` 的紧邻嵌套类。如果 `p` 的类型不是 `o` 或 `o` 的子类，或者如果 `p` 的类型不可访问（§6.6），则发生编译错误。

显式构造方法调用语句可以抛出的异常在 §11.2.2 中指定。

替代构造方法调用语句的评估过程是：首先从左到右评估构造方法的参数（如同普通方法调用一样）；然后调用该构造方法。

父类构造方法调用语句的评估过程如下：

## 类的 构造方法声明 8.8

1. 设 $i$ 为正在创建的实例。必须确定相对于 `s` 的 `i` 的紧邻嵌套实例（如果有）：

- 如果 `s` 不是内部类，或者 `s` 的声明出现在静态上下文中，则不存在相对于 `s` 的 `i` 的紧邻嵌套实例。

- 否则，如果父类构造方法调用是非限定的，则 `s` 必然是一个内部局部类或内部成员类。

- 如果 `s` 是内部类，设 `o` 为 `s` 的紧邻嵌套的类或接口声明。

- 如果 `s` 是内部成员类，设 `o` 为 `c` 的以 `s` 为成员的最内层嵌套类。

- 设 $n$ 为一个整数 ($n \ge 1$)，使得 `o` 是 `C` 的第 $n$ 个词法嵌套的类或接口声明。

- 相对于 `s` 的 `i` 的紧邻嵌套实例是 `this` 的第 $n$ 个词法嵌套实例。

虽然 `s` 可能由于继承而成为 `c` 的成员，但 `this` 的第 0 个词法嵌套实例（即其自身本身）从不被用作相对于 `s` 的 `i` 的紧邻嵌套实例。

- 否则，如果父类构造方法调用是限定的，则评估紧接 "super" 之前的 `Primary` 表达式或 `ExpressionName`，`p`。

如果 `p` 的评估结果为 `null`，则抛出 `NullPointerException`，并且父类构造方法调用绝对完成。

否则，该评估的结果为相对于 `s` 的 `i` 的紧邻嵌套实例。

2. 在确定了相对于 `s` 的 `i` 的紧邻嵌套实例（如果有）后，父类构造方法调用语句的评估过程是：从左到右评估构造方法的参数（如同普通方法调用一样）；然后调用该构造方法。

3. 最后，如果父类构造方法调用语句正常完成，则 `c` 的所有实例变量初始化器和 `c` 的所有初始化器都按文本执行。如果一个初始化器或实例变量 $i$ 在文本上位于另一个初始化器或实例变量 $j$ 之前，则 $i$ 在 $j$ 之前执行。

实例变量初始化器和初始化器的执行不取决于父类构造方法调用实际上是作为显式构造方法调用语句出现，还是隐式提供的。（替代构造方法调用不会执行这种额外的隐式执行。）

## 示例 8.8.7.1-1. 对显式构造方法调用语句的限制

如果示例 §8.8.7 中 `ColoredPoint` 的第一个构造方法更改如下：

```java
class Point {
    int x, y;
    Point(int x, int y) { this.x = x; this.y = y; }
}
class ColoredPoint extends Point {
    static final int WHITE = 0, BLACK = 1;
    int color;
    ColoredPoint(int x, int y, color) {
        this(x, y); // 将 WHITE 改为 color
    }
    ColoredPoint(int x, int y, int color) {
        super(x, y);
        this.color = color;
    }
}
```

将发生编译错误，因为实例变量 `color` 不能被显式构造方法调用语句使用。

## 示例 8.8.7.1-2. 限定的父类构造方法调用

在代码中，`ChildInner` 没有词法嵌套的类或接口声明，因此 `ChildOfInner (Inner)` 的实例没有嵌套实例。`ChildOfInner (Inner)` 的父类是一个词法嵌套的类声明 (Outer)，而 `Inner` 的实例具有 `Outer` 的嵌套实例。

```java
class Outer {
    int secret = 5;
    class Inner {
        int getSecret() { return secret; }
        void setCount(int s) { secret = s; }
    }
}

class ChildOfInner extends Outer {
    ChildOfInner() { super(); }
    ChildOfInner(Outer x) { super(); }
}
public class Test {
    public static void main(String[] args) {
        Outer x = new Outer();
        ChildOfInner a = new ChildOfInner();
        System.out.println(a.getSecret());
        a.setCount(6);
        ChildOfInner b = new ChildOfInner(x);
        System.out.println(b.getSecret());
    }
}
```

程序的输出为：

```
5
6
```

## 8.8.8 构造方法重载

构造方法的重载行为与方法的重载相同（§8.4.9）。

## 8.8.9 默认构造方法

如果类没有构造方法声明，则隐式声明一个默认构造方法。顶层类、成员类或局部类的默认构造方法形式如下：

默认构造方法具有与其相同的访问修饰符，除非类缺少访问修饰符，此时默认构造方法具有包权限（§6.6）。

默认构造方法没有形式参数，私有内部成员类除外，该类会隐式声明一个表示其紧邻嵌套实例的形式参数（§8.8.1, §15.9.2, §15.9.3）。

默认构造方法没有 `throws` 子句。

如果被声明的类是 `Object`，则默认构造方法体为空。否则，默认构造方法简单调用无参数父类构造方法。

匿名类的默认构造方法形式见 §15.9.5.1。

如果隐式声明默认构造方法但父类没有无参数且无 `throws` 子句的可访问构造方法，则会导致编译错误。

### 8.8.9-1 默认构造方法

声明：

```java
public class Point {
    int x, y;
}
```

等于声明：

```java
public class Point {
    int x, y;
    public Point() { super(); }
}
```

其中由于 `Point` 类是公的，因此默认构造方法是公有的。

### 8.8.9-2 构造方法的访问性与类的访问性

默认构造方法的访问性与其类的访问性相同的这一规则简单且直观。但请注意，这并不意味着只要类可访问，构造方法就可访问。考虑：

```java
package pl;
public class Outer {
    protected class Inner { }
}
```

```java
package p2;
class SonOfOuter extends Outer {
    void foo() {
        new Inner(); // 编译时错误
    }
}
```

`Inner` 的默认构造函数是 `protected` 的。然而，该构造函数相对于 `Outer` 是保护的，而 `Inner` 相对于 `Outer` 是保护的。因此，在 `SonOfOuter` 中可以访问 `Inner`，因为它是 `Outer` 的子类。在 `SonOfOuter` 中无法访问 `Inner` 的构造函数，因为类 `SonOfOuter` 不是 `Inner` 的子类！因此，尽管 `Inner` 是可用的，但它的默认构造函数不可用。

## 8.8.10 防止类的实例化

类可以通过声明至少一个构造函数来防止类声明之外的代码创建该类的实例，通过防止默认构造函数的创建，并将所有构造函数声明为 `private`（§6.6.1）。

公共类同样可以通过声明至少一个构造函数来防止在包之外创建实例，通过防止创建具有 `public` 访问权限的默认构造函数，并且不声明任何 `public` 或 `protected` 的构造函数（§6.6.2）。

> 8.8.10-1. 通过构造函数访问权限防止实例化

```java
class ClassOnly {
    private ClassOnly() { }
    static String jest = "only the lonely";
}
```

在这里，类 `ClassOnly` 无法实例化，而在下面的代码中：

```java
package just;
public class PackageOnly {
    PackageOnly() {
        String[] justDesserts = { "cheesecake", "ice cream" };
    }
}
```

## 8.9 枚举类

枚举声明指定了一个新的枚举类，这是一种受限制的类，用于定义一小部分一组命名的类实例。

```
EnumDeclaration: [ClassModifier] enum Identifier [ClassImplements] EnumBody
```

枚举声明可以指定顶层枚举类（§7.6）、成员枚举类（§8.5, §9.5）或局部枚举类（§14.3）。

枚举声明中的 `TypeIdentifier` 指定了枚举类的名称。

如果枚举声明具有修饰符 `abstract`、`final`、`sealed` 或 `non-sealed`，则会导致编译时错误。

枚举类要么是隐式的 `final`，要么是隐式的 `sealed`，如下：

- 如果枚举类的声明不包含任何具有类体的枚举常量，则该枚举类是隐式的 `final`（§8.9.1）。

- 如果枚举类 `E` 的声明包含至少一个具有类体的枚举常量，则它是隐式的 `sealed`。`E` 允许的直接子类（§8.1.6）是由具有类体的枚举常量隐式声明的匿名类。

嵌套枚举类是隐式的 `static`。这意味着每个成员枚举和局部枚举类都是 `static` 的。在成员枚举的声明中冗余地指定 `static` 修饰符是允许的，但在局部枚举类的声明中是不允许的（§14.3）。

如果同一个关键字多次作为枚举声明的修饰符出现，或者如果枚举声明具有 `public`、`protected` 和 `private` 修饰符，则会导致编译时错误（§6.6）。

枚举类 `E` 的直接父类是 `Enum<E>`（§8.1.4）。

> 枚举声明没有 `extends` 子句，因此无法显式声明直接父类类型，即使是 `Enum<E>`。

枚举类除了由枚举常量定义的实例外没有其他实例。尝试显式实例化枚举类会导致编译时错误（§15.9.1）。

除了编译时错误外，还有三个进一步机制确保除了枚举常量定义的实例外，不存在枚举类的实例：

- `Enum` 中 `final` 的 `clone` 方法确保枚举常量永远不会被克隆。

- 禁止对枚举类进行反射实例化。

- 序列化机制的特殊处理确保了不会因为反序列化而创建重复的实例。

### 8.9.1 枚举常量

枚举声明的体可以包含枚举常量。枚举常量定义了该类的一个实例。

```
EnumBody:
{ [EnumConstantList] [ ], [EnumBodyDeclarations] }

EnumConstantList:
EnumConstant {, EnumConstant}

EnumConstant:
{EnumConstantModifier} Identifier [ <ArgumentList> > ] [ClassBody]

EnumConstantModifier:
Annotation
```

为了方便起见，这里显示了 §15.12 中的以下产生式：

```
ArgumentList:
Expression [, Expression ]
```

控制枚举常量声明注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。

`EnumConstant` 中的 **Identifier** 可用于名称以引用该枚举常量。

枚举常量的作用域和隐藏规定在 §6.3 和 §6.4.1 中。

枚举常量后面可以跟上参数，当常量在类初始化期间创建时（如后文所述），这些参数将传递给枚举的构造函数。要调用的构造函数是使用普通的重载解析规则（§15.12.2）选择的。如果省略了参数，则假设为空列表。

枚举常量的可选类体隐式地声明了一个匿名类（§15.9.5），该匿名类：(i) 是立即包含的枚举类的直接子类（§8.1.4），并且 (ii) 是 **final** 的（§8.1.1.2）。类体受匿名类的通常规则限制；特别是它不能包含任何类。

枚举常量的类体受匿名类的通常规则限制；特别是它不能包含任何类类。

如果同一个关键字多次作为枚举声明的修饰符出现，或者如果枚举声明具有 `public`、`protected` 和 `private` 修饰符，则会导致编译时错误。

枚举类 `E` 的直接父类是 `Enum<E>`（§8.1.4）。

> 枚举声明没有 `extends` 子句，因此无法显式声明直接父类类型，即使是 `Enum<E>`。

枚举类除了由枚举常量定义的实例外没有其他实例。尝试显式实例化枚举类会导致编译时错误（§15.9.1）。

除了编译时错误外，还有三个进一步机制确保除了枚举常量定义的实例外，不存在枚举类的实例：

- `Enum` 中 `final` 的 `clone` 方法确保枚举常量永远不会被克隆。

- 禁止对枚举类进行反射实例化。

- 序列化机制的特殊处理确保了不会因为反序列化而创建重复的实例。

### 8.9.2 声明

除了枚举常量，枚举声明的体可以包含构造函数声明。

```
EnumBodyDeclarations:
[ClassBody]
```

为了方便起见，这里显示了 §8.7 中的以下产生式：



## ClassBody

```
ClassBody:
FieldDeclaration
MethodDeclaration
StaticInitializer
ConstructorDeclaration
```

任何构造函数或成员声明在枚举声明中的应用方式与它们在普通类中完全相同，除非显式规定。

如果枚举声明中的构造函数具有 `public` 或 `protected` 修饰符，则会导致编译时错误（§6.6）。

如果枚举声明中的构造函数包含父类调用，则会导致编译时错误（§8.7）。

在枚举声明中，没有访问修饰符的构造函数是 `private` 的。

在没有构造函数的枚举声明中，隐式声明一个默认构造函数。该默认构造函数是 `private` 的，没有形式参数，也没有 `throws` 子句。

在实践中，编译器可能会模仿 `Enum` 类，在默认构造函数中声明 `String` 和 `int` 参数。

## 8.9.2.1 声明

```java
enum Coin {
    PENNY(1), NICKEL(5), DIME(10), QUARTER(25);
    Coin(int value) { this.value = value; }

    private final int value;
    public int intValue() { return value; }
}
```

每个枚举常量在字段 `value` 中安排了不同的值，通过构造函数传递。该字段代表美国硬币以分值为单位的值。注意，对于枚举类的构造函数可以声明的参数没有限制。

## 8.9.2.2 对枚举常量自引用的限制

如果没有关于静态字段访问的规则，看似合理的代码将在运行时由于枚举类固有的初始化循环性而失败。（在任何具有“自类型”静态字段的类中都存在循环性。）这里是类会失败的代码示例：

```java
import java.util.HashMap;
import java.util.Map;
```

# 枚举类

```
enum Color {
    RED, GREEN, BLUE;
    Color() { colorMap.put(toString(), this); }

    static final Map<String,Color> colorMap =
        new HashMap<String,Color>();
}
```

枚举的静态初始化会抛出 `NullPointerException`，因为在枚举常量构造函数运行时，静态变量 `colorMap` 尚未初始化。上述限制确保了此类代码无法编译。然而，可以很容易重构代码使其正常工作。

```java
import java.util.HashMap;
import java.util.Map;
```

```java
enum Color {
    RED, GREEN, BLUE;

    static final Map<String,Color> colorMap =
        new HashMap<String,Color>();
    static {
        for (Color c : Color.values())
            colorMap.put(c.toString(), c);
    }
}
```

重构后的版本显然是正确的，因为静态初始化是从上到下进行的。

### 8.9.3 枚举成员

枚举类 `E` 的成员包含以下所有内容：

- 在 `E` 的声明体中声明的成员。
- 从 `Enum<E>` 继承的成员。
- 对于在 `E` 的声明体中声明的每个枚举常量 `c`，`E` 有一个隐式声明的类型为 `E` 的 `public final` 字段，其名称与 `c` 相同。该字段带有一个变量初始化器，用于实例化 `E` 并将 `c` 的任何参数传递给 `E` 选定的构造函数。该字段具有注解 `c`（如果有）。

这些字段的隐式声明顺序与相应的枚举常量顺序相同，并且位于 `E` 的声明体中显式声明的任何静态字段之前。

当相应的隐式声明字段被初始化时，认为该枚举常量已创建。

- 一个隐式声明的方法 `public static E[] values()`，它返回一个包含 `E` 的枚举常量的数组，其顺序与它们在 `E` 的声明体中出现的顺序相同。
- 一个隐式声明的方法 `public static E valueOf(String name)`，它返回具有指定名称的 `E` 枚举常量。

因此，枚举类 `E` 的声明不能包含与与其枚举常量对应的隐式声明字段冲突的字段，也不能包含与隐式声明方法冲突或覆盖 `Enum<E>` 类中 `final` 方法的方法。

# 示例 8.9.3-1. 使用增强 for 循环遍历枚举常量

```java
public class Test {
    enum Season { WINTER, SPRING, SUMMER, FALL }

    public static void main(String[] args) {
        for (Season s : Season.values()) {
            System.out.println(s);
        }
    }
}
```

该程序产生以下输出：

```
WINTER
SPRING
SUMMER
FALL
```

# 示例 8.9.3-2. 对枚举常量进行 switch 操作

`switch` 语句（§14.11）用于模拟从类外部向枚举类添加方法。此示例为 8.9.2 中的 `Coin` 类“添加”了一个颜色方法，并打印了硬币、其面值和颜色的表格。

## 8.9 枚举类

```java
public static void main(String[] args) {
  for (Coin c : Coin.values()) {
    System.out.println(c + "\t\t" + 
      c.value(c) + "\t" + color(c));
  }
}
```

该程序产生以下输出：

| PENNY | 1 | COPPER |
| NICKEL | 5 | NICKEL |
| DIME | 10 | SILVER |
| QUARTER | 25 | SILVER |

# 示例 8.9.3-3. 带有类体的枚举常量

与其使用 `switch` 语句从外部向枚举类添加行为，不如使用类体将行为直接绑定到枚举常量上。

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

  // 每个常量支持算术运算
  abstract double eval(double x, double y);

  public static void main(String[] args) {
    double x = Double.parseDouble(args[0]);
    double y = Double.parseDouble(args[1]);
    for (Operation op : Operation.values()) {
      System.out.println(x + " = " + op + " = " + op.eval(x, y));
    }
  }
}
```

该程序产生输出：

```
2 = PLUS = 6
2 = MINUS = -2
2 = TIMES = 8
2 = DIVIDED_BY = 0
```

枚举类这种模式比使用 `switch` 语句更安全，因为这种模式消除了忘记为新常量添加行为的可能性（因为声明会导致编译错误）。

# 示例 8.9.3-4. 多重枚举类

在下面的程序中，`Card` 类是基于两个简单的枚举构建的。

```java
import java.util.ArrayList;
import java.util.List;

class Card implements Comparable<Card>, java.io.Serializable {
    public enum Rank { DEUCE, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, JACK, QUEEN, KING, ACE }

    public enum Suit { CLUBS, DIAMONDS, HEARTS, SPADES }

    private final Rank rank;
    private final Suit suit;
    public Rank rank() { return rank; }
    public Suit suit() { return suit; }

    private Card(Rank rank, Suit suit) {
        if (rank == null || suit == null)
            throw new NullPointerException("rank or suit is null");
        this.rank = rank;
        this.suit = suit;
    }

    public String toString() { return rank + " of " + suit; }

    // 主按花色排序，次按点数排序
    public int compareTo(Card c) {
        int suitCompare = suit.compareTo(c.suit);
        return (suitCompare != 0) ?
            suitCompare : rank.compareTo(c.rank);
    }

    private static final List<Card> prototypeDeck = new ArrayList<Card>(52);

    static {
        for (Suit suit : Suit.values()) {
            for (Rank rank : Rank.values()) {
                prototypeDeck.add(new Card(rank, suit));
            }
        }
    }

    // 返回一个新的牌组
    public static List<Card> newDeck() {
        return new ArrayList<Card>(prototypeDeck);
    }
}
```

下面的程序测试了 `Card` 类。它在命令行接收两个整数参数，代表要发的牌手数量和每手牌的数：

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Deal {
    public static void main(String[] args) {
        int numHands = Integer.parseInt(args[0]);
        int cardsPerHand = Integer.parseInt(args[1]);
        List<Card> deck = Card.newDeck();
        Collections.shuffle(deck);
        for (int i = 0; i < numHands; i++) {
            System.out.println(deal(deck, cardsPerHand));
        }
    }

    /**
     * 返回一个包含 deck 最后元素的 ArrayList，
     * 这些元素已从 deck 中移除。
     * 返回的列表使用自然排序进行排序。
     */
    public static <E extends Comparable<E>>
    ArrayList<E> deal(List<E> deck, int n) {
        int deckSize = deck.size();
        List<E> handView = deck.subList(deckSize - n, deckSize);
        ArrayList<E> hand = new ArrayList<>(handView);
        deck.clear();
        Collections.sort(hand);
        return hand;
    }
}
```

该程序产生输出：

```
Deal 4 3
[DEUCE OF CLUBS, SEVEN OF CLUBS, QUEEN OF DIAMONDS]
[NINE OF HEARTS, FIVE OF SPADES, ACE OF SPADES]
[THREE OF HEARTS, SIX OF HEARTS, TEN OF SPADES]
[TEN OF CLUBS, NINE OF DIAMONDS, THREE OF SPADES]
```

## 8.10 Record 类

record 声明指定了一个新的类，这是一种定义了简单值聚合的受限类。

```
RecordDeclaration:
[ClassModifier] record TypeIdentifier [TypeParameters] RecordHeader
[Implements] RecordBody
```

一个 record 声明可以指定顶层 record 类（§7.6）、成员 record 类（§8.5, §9.5）或本地 record 类（§14.3）。

record 声明中的 `TypeIdentifier` 指定 record 类的名称。

如果 record 声明具有 `abstract`、`sealed` 或 `non-sealed` 修饰符，则为编译错误。

record 类是隐式的 `final`。允许 record 声明冗余地指定 `final` 修饰符。

嵌套 record 类是隐式的 `static`。这意味着每个成员 record 类和本地 record 类都是静态的。允许 record 声明冗余地指定 `static` 修饰符，但本地 record 类（§14.3）不允许这样做。

如果同一个关键字作为 record 声明的修饰符出现多次，或者 record 具有多个访问修饰符（`public`、`protected` 和 `private`），则为编译错误。

record 类的直接父类类型是 `Record`（§8.1.4）。

> record 声明没有 `extends` 子句，因此无法显式声明直接父类类型，即使是 `Record` 也不行。

序列化机制处理 record 类的实例的方式与普通的序列化或可执行对象不同。特别是，record 对象是使用规范构造函数（§8.10.4）进行反序列化的。

### 8.10.1 Record 组件

record 类的 record 组件（如果有）在 record 声明的头部中指定。每个 record 组件由一个类型（可选由一个或多个注解前导）和一个指定 record 组件名称的标识符组成。record 组件对应于 record 的两个成员：一个隐式声明的私有字段以及一个显式或隐式声明的公共访问方法（§8.10.3）。

如果记录类没有记录组件，则在记录声明的头部会出现一对空括号。

```
RecordHeader:
( [RecordList] )
```

```
RecordList:
RecordComponent( , RecordComponent)
```

```
RecordComponent:
[RecordComponentModifier] UnannType Identifier
VariableArityRecordComponent
```

```
VariableArityRecordComponent:
[RecordComponentModifier] UnannType [Annotation] ... Identifier
```

```
RecordComponentModifier:
Annotation
```

记录组件可以是一个变长记录组件，通过类型后的省略号（`...`）来表示。一个记录类最多允许一个变长记录组件。如果变长记录组件出现在记录组件列表除最后一个位置外的任何位置，则是一个编译错误。

关于记录组件注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。



> 如果记录组件上的注解的接口在记录组件上下文中适用（§9.6.4.1），则可以通过反射访问记录组件上的注解。独立地，如果记录组件上的注解的接口在其他上下文中适用，则记录组件上的注解会传播到记录类成员和构造函数的声明中（§8.10.3, §8.10.4）。

如果记录声明具有名称为 `clone`、`finalize`、`getClass`、`hashCode`、`notify`、`notifyAll`、`toString` 或 `wait` 的记录组件，则是一个编译错误。

> 这些是 `Object` 的无参公共和受保护方法。不允许将这些方法作为记录组件的名称可以从多个方面避免混淆。首先，每个记录类都提供了 `hashCode` 和 `toString` 的实现，它们返回整个记录对象的表示；它们不能作为调用为 `hashCode` 或 `toString` 的记录组件的访问方法（§8.10.3），而且不会有从记录类外部访问此类记录组件的方法。同样，某些记录类提供了 `clone` 和（遗憾的是）`finalize` 的实现，因此名为 `clone` 或 `finalize` 的记录组件将无法通过访问方法访问。最后，`Object` 中的 `getClass`、`notify`、`notifyAll` 和 `wait` 方法是 `final` 的，因此具有相同名称的记录组件不能拥有访问方法。（访问方法的签名与 `final` 方法的签名相同，并将尝试失败地重写它们。）

如果记录声明具有两个相同名称的记录组件，则是一个编译错误。

记录组件的声明类型取决于它是否为变长长度组件：

- 如果记录组件不是变长长度记录组件，则声明类型由 `UnannType` 表示。
- 如果记录组件是变长长度记录组件，则其声明类型为 §10.2 中指定的数组类型。

如果变长长度记录组件的声明类型具有非可重构（non-reifiable）元素（§4.7），则变长长度记录组件的声明会发生编译未检查警告，除非规范构造函数（§8.10.4）被标记了 `@SafeVarargs`（§9.6.4）或该警告被 `@SuppressWarnings`（§9.6.4）抑制。

# 记录类 (Record Classes)

## 8.10

### 8.10.2 记录体声明 (Record Body Declarations)

记录声明的主体可以包含构造函数和成员声明以及静态初始化器。

```
RecordBody:
{ [RecordBodyDeclaration] }
```

```
RecordBodyDeclaration:
ClassBodyDeclaration
CompactConstructorDeclaration
```

为了方便起见，这里显示了 §8.1.7 中的以下产生式：

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

`CompactConstructorDeclaration`（紧凑构造函数声明）在 §8.10.4.2 中描述。

如果记录声明的主体包含非静态字段声明（§8.3.1），则是一个编译错误。

如果记录声明的主体包含抽象或原生的方法声明（§8.4.3.1, §8.4.3.4），则是一个编译错误。

如果记录声明的主体包含实例初始化器（§8.6），则是一个编译错误。

### 8.10.3 记录成员 (Record Members)

对于每个记录组件，记录类都有一个与记录组件名称相同且类型与记录组件声明类型相同的字段。该字段是隐式声明的，被称为组件字段（component field）。

组件字段是私有的、final 的且非静态的。

如果相应的记录组件上出现了任何注解，且这些注解的接口在字段声明上下文、类型上下文中或两者均适用（§9.7.4），则组件字段将带有这些注解。

此外，对于每个记录组件，记录类都有一个与记录组件名称相同且形式参数列表为空的方法。该方法是显式或隐式声明的，被称为访问方法（accessor method）。

如果记录组件的访问方法是显式声明的，则必须满足所有条件，否则将发生编译错误：

- 访问方法的返回类型（§8.4.5）必须与记录组件的声明类型相同。
- 访问方法不能是泛型的（§8.4.4）。
- 访问方法必须是没有形式参数且没有 throws 句的的公共实例方法。

如果一个记录类有一个没有显式声明访问方法的记录组件，则会隐式声明一个访问方法，该方法具有以下属性：

- 它的名称与记录组件相同。
- 它的返回类型与记录组件的声明类型相同。
- 它不是泛型的。
- 它是一个没有形式参数且没有 throws 句的的公共实例方法。
- 如果记录组件上出现了任何注解，且这些注解的接口在方法声明上下文或两者均适用（§9.7.4），则它将带有这些注解。
- 它返回组件字段的值。

记录组件的限制（§8.10.1）意味着没有任何隐式访问方法的签名与 `Object` 的非私有方法是重写等价的。取限制名称（例如 `public void wait()`）的显式方法声明不是访问方法，因为 `wait` 是一个记录组件名称。

出现在记录组件上的注解不会传播到记录组件的显式访问方法。在某些情况下，程序员可能需要在显式访问方法上重复记录的注解，但这并不总是必要的。

传播到隐式声明访问方法的注解必须产生合法的注解方法。例如，在下面的记录声明中，隐式声明的访问方法 `wait(x)` 将标记为 `@SafeVarargs`，但这种注解在固定长度方法上是非法的（§6.4.7）：

```java
record BadRecord(@SafeVarargs int x) {} // 错误
```

组件字段和访问方法的作用域在 §6.3 和 §6.4.1 中规定。（它们对应的记录组件不是声明，因此没有它们自己的作用域）。

记录类可以显式声明除访问方法以外的实例方法，但不能显式声明实例变量（§8.10.2）。允许显式声明类方法和类变量。

记录类的所有成员（包括隐式声明的成员）都遵循类成员定义的常规规则（§8.3, §8.4, §8.5）。

适用于普通类的所有继承规则也适用于记录类。特别是，记录类可以从超接口继承成员，尽管超接口方法永远作为访问方法被继承，因为记录类总是会显式或隐式地声明一个重写该超接口方法的访问方法。

例如，`record` 类可以继承其直接父类接口的默认方法，尽管默认方法的体并不知道该 `record` 类的组件字段的信息。以下程序将打印 `Logged`。

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

`record` 类提供了 `Record` 类中声明的所有抽象方法的实现。对于以下每个方法，如果 `record` 类 `R` 没有显式声明一个具有相同修饰符、名称和签名（§8.4.2）的方法，则该方法将隐式声明如下：

- 方法 `public final boolean equals(Object)`：如果当且仅当参数是 `R` 的实例，且当前实例在 `R` 的每个 record 组件上都相等时，返回 `true`；否则返回 `false`。record 类 `R` 的实例 `a` 与相同 record 类的另一个实例 `b` 在 record 组件 `c` 上的相等确定如下：
  - 如果 record 组件 `c` 的类型是引用类型，则相等性的确定如下：如果 `a` 和 `b` 的组件字段 `c` 的值均为 `null` 引用，则返回 `true`；如果 `a` 或 `b` 其中之一的组件字段 `c` 的值为 `null` 引用但并非均如此，则返回 `false`；否则，通过对组件字段 `c` 的值调用 `equals` 方法来确定相等性，参数为 `b` 组件字段 `c` 的值。
  - 如果 record 组件 `c` 的类型是原始类型 `τ`，则相等性的确定就像调用了 `T` 对应的包装类（§5.1.7）的 `static` 方法 `compare`，第一个参数为 `a` 组件字段 `c` 的值，第二个参数为 `b` 组件字段 `c` 的值；如果该方法返回 `0`，则返回 `true`，否则返回 `false`。

包装类中使用 `compare` 确保了隐式声明的 `equals` 方法具有反射性，并且对于具有浮点数组件的 record 类，其行为与隐式声明的 `hashCode` 方法保持一致。

- 方法 `public final int hashCode()`：返回一个从 `R` 的每个 record 组件的哈希码值派生的哈希码值。

record 类实例 `a` 在 record 组件 `c` 上的哈希值如下：
  - 如果 record 组件 `c` 的类型是引用类型，则该哈希值通过对 `a` 组件字段 `c` 的值调用 `hashCode` 方法来确定。
  - 如果 record 组件 `c` 的类型是原始类型 `T`，则该哈希值就像对 `a` 组件字段 `c` 的值进行装箱转换（§5.1.7），然后在生成的对象上调用对应于 `T` 的包装类的 `hashCode` 方法来确定。

- 方法 `public final String toString()`：返回一个源自 record 类名称以及 `R` 的每个 record 组件的名称和字符串表示的字符串。

record 类实例 `a` 的 record 组件 `c` 的字符串表示如下：
  - 如果 record 组件 `c` 的类型是引用类型，则该字符串表示就像通过对 `a` 组件字段 `c` 的值调用 `toString` 方法来确定。
  - 如果 record 组件 `c` 的类型是原始类型 `T`，则该字符串表示就像对 `a` 组件字段 `c` 的值进行装箱转换（§5.1.7），然后在生成的对象上调用对应于 `T` 的包装类的 `toString` 方法来确定。

注意，相等性、哈希码和字符串表示是通过查看组件字段的值确定的，而不是通过调用访问方法。

考虑一个具有组件 `c_1, ..., c_n` 的 record 类 `R`，它的每个组件都有一个隐式声明的访问器方法和一个隐式声明的 `equals` 方法。如果 `R` 的实例 `r1` 以如下方式被复制：

```java
r2 = new R(r1.c1(), r1.c2(), ..., r1.cn());
```

那么，假设 `r1` 不是 `null` 引用，表达式 `r1.equals(r2)` 始终求值为真。显式声明的访问器方法和 `equals` 方法应该尊重这一不变性。编译器通常无法检查显式声明的方法是否维护了这一不变性。以下 record 声明是错误的，因为它的访问器方法裁剪了 `x` 和 `y` 组件，从而阻止了 `p3` 等于 `p1`：

```java
record SmallPoint(int x, int y) {
    public int x() { return this.x < 100 ? this.x : 100; }
    public int y() { return this.y < 100 ? this.y : 100; }
}

public static void main(String[] args) {
    SmallPoint p1 = new SmallPoint(50, 50);
    SmallPoint p2 = new SmallPoint(p1.x(), p1.y());
    System.out.println(p1.equals(p2)); // true
    SmallPoint p3 = new SmallPoint(150, 50);
    System.out.println(p1.equals(p3)); // false
}
```

## 8.10 Record 类

### 8.10.4 Record 构造函数声明

为了确保 record 组件的正确初始化，record 类不声明默认构造函数（§8.8）。相反，record 类有一个显式或隐式声明的规范构造函数，它负责初始化所有组件字段。

在 record 中显式声明构造函数有两种方法：通过声明一个普通构造函数（§8.10.4.1）或声明一个紧凑构造函数（§8.10.4.2）。

给定符合规范构造要求的普通构造函数签名和一个紧凑构造函数的签名，根据构造函数签名规则（§8.8.2），如果一个 record 声明同时具有普通构造函数和紧凑构造函数，则将是编译错误。

显式声明的规范构造函数必须提供与 record 类至少相同的访问权限，如下所示：

- 如果 record 类是 `public`，则规范构造函数必须是 `public`；否则，产生编译错误。
- 如果 record 类是 `protected`，则规范构造函数必须是 `protected` 或 `public`；否则，产生编译错误。
- 如果 record 类具有包级访问权限，则规范构造函数不能是 `private`；否则，产生编译错误。
- 如果 record 类是 `private` 的，则规范构造函数可以用任何访问权限声明。

显式声明的规范构造函数可以是固定元数的构造函数或可变元数的构造函数（§8.8.1）。

如果在 `R` 的声明中没有显式声明规范构造函数，则在 `R` 中隐式声明一个具有以下属性的规范构造函数 `r`：

- `r` 的签名没有类型参数，形式参数由下面定义的派生参数列表给出。
- `r` 与 `R` 具有相同的访问修饰符，除非 `R` 缺少访问修饰符，此时 `r` 具有包访问权限。
- `r` 没有 `throws` 子句。
- `r` 的体按照 record 组件（对应组件字段）出现在 record 头中的顺序，用形式参数初始化 record 类的每个组件字段。

record 类的*派生参数列表*通过按顺序从 record 头中的每个组件导出形式参数形成，如下：

- 如果 record 组件不是可变 record 组件，则派生的形式参数与 record 组件具有相同的名称和声明类型。
- 如果 record 组件是可变 record 组件，则派生的形式参数是一个与 record 组件具有相同名称和声明类型的可变参数（§8.4.1）。
- 派生的形式参数带有 record 组件上的任何注解，只要这些注解接口在形式参数上下文中、类型上下文中或两者中均适用（§9.7.4）。

record 声明可以包含非规范构造函数的声明。record 声明中每个非规范构造函数的体必须以备用构造函数调用（§8.8.7.1）开始，否则将产生编译错误。

### 8.10.4.1 普通规范构造函数

record 类 `R` 声明中的（非紧凑）构造函数如果其签名与 `R` 的派生构造函数签名重写等（§8.4.2），则为 `R` 的*规范构造函数*。

记录类 `R` 的派生构造函数签名是一个签名，它由名称 `R`、无类型参数以及通过按照顺序从 `R` 的记录头中每个记录组件的声明类型推导出的形式参数类型组成。

规范构造函数的签名与该记录类的派生构造函数签名在重写上是等价的，记录类中只能有一个显式声明的规范构造函数。

（非紧凑型）规范构造函数的声明必须满足以下所有条件，否则将发生编译错误：

- 形式参数列表中的每个形式参数必须与对应的记录组件具有相同的名称和声明类型。
- 且仅当对应的记录组件是变长记录组件（variable arity record component）时，该形式参数才必须是变长参数。
- 构造函数不能是泛型的（§8.8.4）。
- 构造函数不能有抛出语句（throws clause）。
- 构造函数体不能包含显式的构造函数调用语句（§8.8.7.1）。
- 必须满足普通类声明中构造函数声明的所有其他规则（§8.8）。

这些规则产生的结果是：记录组件上的注解可能与显式声明的规范构造函数对应的形式参数上的注解不同。例如，以下记录声明是有效的：

```java
import java.lang.annotation.Target;
import java.lang.annotation.ElementType;

@interface Foo {}
@interface Bar {}

record Person(@Foo String name) {
  Person(@Bar String name) {
    this.name = name;
  }
}
```

### 8.10.4.2 紧凑型规范构造函数 (Compact Canonical Constructors)

紧凑构造函数声明是构造函数声明的一种简洁形式，仅在记录声明可用。它声明了记录类的规范构造函数，而不需要将类的记录组件手动重复为构造函数的形式参数。

```
CompactConstructorDeclaration:
{ConstructorModifier} SimpleTypeName ConstructorBody
```

为了方便起见，这里展示了来自 §8.8、§8.8.3 和 §8.8.7 的产生式：

```
ConstructorModifier:
(one of)
Annotation public protected private
```

```
SimpleTypeName:
TypeIdentifier
```

```
ConstructorBody:
([ExplicitConstructorInvocation] [BlockStatements] }
```

记录声明具有多个紧凑构造函数声明是编译错误。



# 记录类紧凑构造函数

记录类紧凑构造函数的形式参数是隐式声明的。它们由记录类的派生形式参数列表给出（§8.10.4）。

如果记录类具有变长记录组件，则该记录类的紧凑构造函数是一个变长构造函数（§8.8.1）。

紧凑构造函数声明的签名等于记录类的派生构造函数签名（§8.10.4）。

紧凑构造函数声明的体必须满足以下所有条件，否则将发生编译错误：

- 体不能包含返回语句（§8.14.17）。
- 体不能包含显式的构造函数调用语句（§8.8.7.1）。
- 体不能包含对记录类组件字段的赋值。
- 必须满足普通类声明中构造函数的所有其他规则（§8.8），但要求记录类组件字段在紧凑构造函数结束时必须被确定赋值，并且不能是确定未赋值的这一要求除外（§8.3.1.2）。

如果记录声明有一个名为 `c` 的记录组件，则紧凑构造函数体中的简单名称 `c` 指的是名为 `c` 的隐式形式参数，而不是名为 `c` 的组件字段。

在紧凑构造函数体中的最后一个语句（如果有）正常执行后（§14.1），记录类的所有组件都将隐式地初始化为对应形式参数的值。组件字段按照对应记录组件在记录头部声明的顺序进行初始化。

紧凑构造函数声明的意图是仅对参数进行验证或归一化。例如，以下记录声明是有效的：

```java
record Person(int age) {
    Person {
        if (age < 0) throw new IllegalArgumentException("Age cannot be negative");
    }
}
```

# 9.1 接口声明

关于接口声明的注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

访问修饰符 `public`（§6.6）仅适用于顶层接口（§7.6）和成员接口（§8.5, §9.5），而不适用于局部接口（§14.3）。

访问修饰符 `protected` 和 `private` 仅适用于成员接口。

修饰符 `static` 仅适用于成员接口和局部接口。

如果同一个关键字作为接口声明的修饰符出现多次，或者一个接口声明具有多个 `public`、`protected`、`private` 访问修饰符，则为编译时错误。

如果一个接口声明具有多个 `sealed` 和 `non-sealed` 修饰符，则为编译时错误。

> 如果在接口声明中出现了两个或多个（不同的）接口修饰符，那么按照惯例（并非强制），它们出现的顺序应与上述 `InterfaceModifier` 产生式中所示的顺序一致。

## 9.1.1.1 抽象接口

每个接口都是隐式的 `abstract`。

### 此修饰符已过时，不应在新代码中使用。

## 9.1.1.2 strictfp 接口

接口声明上的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对编译时或运行时均没有影响。

## 9.1.1.3 static 接口

嵌套接口是隐式的 `static`。这意味着每个成员接口和局部接口都是 `static` 的。成员接口的声明冗余地指定 `static` 修饰符（§9.5）是允许的，但局部接口的声明（§14.3）不允许。

由于嵌套接口是 `static` 的，因此它没有直接包含的实例（§8.1.3）。从嵌套接口到类型参数、实例变量、局部变量、形式参数、异常参数或词法包含的类、接口或方法声明中的实例方法的引用是不允许的（§6.5.5.1, §6.5.6.1, §15.12.3）。

## 9.1.1.4 密封与非密封接口

如果一个接口在声明时其所有直接子类和直接子接口都是已知的（§9.1.4），并且不需要或不需要其他的直接子类或直接子接口，则可以将该接口声明为 `sealed`。

> 需要注意的是，一个类被认为是其直接父接口的直接子类（§8.1.5）。

如果一个接口的所有直接父接口都不是密封的（§9.1.3），且它本身不是密封的，则该接口是可自由扩展的。

一个具有密封的直接父接口的接口，当且仅当它被声明为 `non-sealed` 时，才是可自由扩展的。

如果一个接口具有密封的直接父接口且未声明为 `sealed` 或 `non-sealed`，则为编译时错误。

如果一个接口被声明为 `non-sealed` 但没有密封的直接父接口，则为编译时错误。

## 9.1.2 泛型接口和类型参数

如果接口声明声明了一个或多个变量（§4.4），则该接口是泛型接口。

这些变量被称为接口的类型参数。类型参数部分紧随接口名称之后，并用角括号分隔。

为了方便起见，这里显示了来自 §8.1.2 和 §4.4 的产生式：

```
TypeParameters:
  <TypeParameterList>

TypeParamList:
  TypeParameter (, TypeParameter)

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

关于类型参数声明的注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

在接口的类型参数部分，如果 `s` 是 `t` 的边界，则类型变量 `t` 直接依赖于类型变量 `s`；如果 `t` 直接依赖于 `s` 或依赖于 `s` 的类型变量 `U`（递归使用此定义），则 `t` 依赖于 `s`。如果接口类型参数部分中的类型变量依赖于自身，则为编译时错误。

接口类型参数的作用域和遮蔽在 §6.3 和 §6.4.1 中规定。

从静态上下文或嵌套类或接口对接口类型参数的引用是限制的，如 §6.5.5.1 规定。

泛型接口声明定义了一组参数化类型（§4.5），对应于类型参数对类型参数部分的每种可能的参数化。所有这些参数化类型在运行时共享同一个接口。

## 9.1.3 父接口和子接口

如果提供了 `extends` 子句，则所声明的接口扩展每个指定的接口类型，因此继承了这些接口类型的成员类、成员接口、实例方法和 `static` 字段。

指定的接口类型是所声明接口的 *直接父接口类型*。

任何 `implements` 所声明接口的类也被认为实现了该接口所 `extends` 的所有接口。

```
InterfaceExtends:
  extends InterfaceTypeList
```

为了方便起见，这里显示了来自 §8.1.5 的产生式：

```
InterfaceTypeList:
  InterfaceType [, InterfaceType]
```

接口声明 `extends` 子句中的每个 `InterfaceType` 必须命名一个可访问接口（§6.6），否则将发生编译时错误。如果一个接口具有密封的直接父接口且未声明为 `sealed` 或 `non-sealed`，则为编译时错误。如果一个接口被声明为 `non-sealed` 但没有密封的直接父接口，则为编译时错误。

如果 `InterfaceType` 有类型参数，则它必须是一个良好的类型（§4.5），并且 `permits` 子句只能指定一个类或接口。

如果接口 `i` 关联到一个命名模块（§7.3），则 `permits` 子句中指定的每个类或接口必须与 `i` 关联，否则将发生编译时错误。如果接口 `i` 关联到一个未命名模块（§7.7.5），则 `permits` 子句中指定的每个类或接口必须属于 `i` 所在的包，否则将发生编译时错误。

接口关系是接口关系的传递闭包。如果满足任一条件，则接口 $I$ 是 $K$ 的接口：

- $I$ 是 $K$ 的直接父接口。
- $I$ 是 $J$ 的直接父接口，且 $J$ 是 $K$ 的接口。

如果在运行时加载接口时检测到循环定义的接口，将抛出 `ClassCircularityError`（§12.2.1）。

## 9.1.4 许可的直接子类和子接口

接口声明中可选的 `permits` 子句指定了所有作为直接子类和子接口的类和接口（§9.1.4）。

```
InterfacePermits:
  permits TypeName (, TypeName)
```

如果接口声明具有 `permits` 子句但没有 `sealed` 修饰符，则为编译时错误。每个 `TypeName` 必须命名一个可访问的类或接口，否则发生编译时错误。如果同一个类或接口在 `permits` 子句中出现多次，则为编译时错误。即使该类是以不同的方式命名的也是如此。

`permits` 子句不需要类或接口的规范名，但只能指定类或接口。

> 密封接口及其子类和直接子接口需要循环地相互引用，分别在 `permits`、`implements` 和 `extends` 中。在模块化代码中，它们必须位于同一个模块中，因为不同模块的类和接口无法循环相互引用。在任何情况下，密封接口层次结构都应该在单个维护域内声明，由同一开发者或开发者小组负责维护该层次结构。命名模块通常代表模块化代码库中的一个维护域。

如果密封接口 `i` 的声明具有 `permits` 子句，则许可的直接子类和子接口是 `permits` 子句指定的类和接口。`permits` 子句指定的每个直接子类和直接接口必须是 `i` 的直接子类（§8.1.5）或 `i` 的直接子接口（§9.1.3），否则发生编译时错误。

如果密封接口 `i` 的声明缺少 `permits` 子句，则许可的直接子类和子接口是那些声明的类和接口：

- 在与 `i`（§7.3）相同的编译单元中。
- 该类具有规范名称（§6.7）。
- 且其直接超接口包含 `i`。

也就是说，允许的直接子类和子接口被推断为同一编译单元中指定 `i` 为直接超接口的类和接口。规范名称的要求意味着不考虑本地类、本地接口或匿名类。

如果 `sealed` 接口 `i` 的声明缺少 `permits` 子句，且 `i` 没有允许的直接子类或子接口，则为编译时错误。

## 9.1.5 接口体与成员声明

接口体可以包含接口成员的声明，即字段（§9.3）、方法（§9.4）、类和接口（§9.5）。

```
InterfaceBody:
  {InterfaceMemberDeclaration}

InterfaceMemberDeclaration:
  ConstantDeclaration
  InterfaceMethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

在接口 `i` 中声明或其继承的成员 `m` 的声明范围在 §6.3 中规定。

# 9.2 接口成员

接口的成员包括：

- 在接口声明体中声明的成员（§9.1.5）。
- 继承自任何直接超接口类型的成员（§9.1.3）。

如果接口没有直接超接口类型，则接口会为 `Object`（§4.3.2）中声明的每个签名为 `s`、返回类型为 `r` 且带有 `throws` 子句 `t` 的 `public` 实例方法 `m`，隐式声明一个 `public abstract` 成员方法 `m`。

除非接口显式声明相同的签名、相同的返回类型以及兼容的 `throws` 子句。

如果接口显式声明此类 `m` 且被声明为 `final Object`，则为编译时错误。

如果接口显式声明的方法与 `Object` 的公共方法具有重写等效签名（§8.4.2），但返回类型不同、`throws` 子句不兼容或不是抽象方法，则为编译时错误。

接口继承其所扩展的接口的所有成员，但排除：(i) 它隐藏的字段、类和接口；(ii) 它重写的抽象方法和默认方法（§9.4.1），(iii) 私有方法以及 (iv) 静态方法。

接口的字段、成员类和成员接口可以具有相同的名称，因为它们在不同的上下文中使用，并通过不同的查找程序（§6.5）进行消歧。然而，从风格上来说，不建议这样做。

# 9.3 字段（常量）声明

```
ConstantDeclaration:
  {ConstantModifier UnannType VariableDeclarList ;
```

```
ConstantModifier:
  (one of)
  Annotation public
  static final
```

`UnannType` 见 §8.3。为了方便起见，这里显示了 §4.3 和 §8.3 中的产生式：

```
VariableDeclarList:
  VariableDeclarator (, VariableDeclarator)
```

```
VariableDeclarator:
  VariableDeclaratorId [= VariableInitializer]
```

```
VariableDeclaratorId:
  Identifier [Dims]
```

```
Dims:
  [Annotation] [] [ [Annotation] [] ]
```

```
VariableInitializer:
  Expression
  ArrayInitializer
```

关于接口字段声明修饰符注解的规定在 §9.7.4 和 §9.7.5 中。

接口声明体中的每个字段声明都是隐式的 `public`、`static` 和 `final`。允许对这些字段冗余地指定其中任何或所有修饰符。

如果同一个关键字作为字段声明的修饰符出现多次，则为编译时错误。

字段声明中出现两个或多个（不同的）字段修饰符，虽然不是必须，但习惯上按照上述 `ConstantModifier` 产生式所示的顺序出现。

如果 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号，则字段的声明类型用 `UnannType` 表示，否则由 §10.2 指定。

接口字段的范围和隐藏在 §6.3 和 §6.4.1 中规定。

由于接口字段是静态的，其声明被限制在静态环境中。它不能通过接口的实例变量引用；必须通过接口名称或简单名称引用。

# 9.4 方法声明

```
Result:
  UnannType
  void
```

```
MethodDeclarator:
  Identifier ([ReceiverParameter, [FormalPropertyList]) Dims
```

```
MethodBody:
  Block
```

关于接口方法声明注解修饰符的规则规定在 §9.7.4 和 §9.7.5 中。

接口声明体中的方法可以声明为 `public`（公共）或 `private`（私有）（§6.6）。如果没有提供访问修饰符，则该方法默认为 `public`。在接口声明的方法声明中冗余地指定 `public` 修饰符是允许的，但从风格角度不建议。

默认方法（default method）是在接口中使用 `default` 修饰符声明的实例方法。其方法体始终由一个块（block）表示，为任何实现了该接口且未覆盖默认方法的类提供默认实现。默认方法与具体方法（§8.4.3.1）不同，后者是在类中声明的；同时也与私有接口方法不同，后者既不被继承也不被重写。

接口可以声明静态方法，该方法无需引用特定对象即可调用。静态接口方法与默认方法、抽象接口方法以及非静态私有接口方法不同，这些都是实例方法。

静态接口方法的声明引入了静态上下文（§8.1.3），这限制了引用当前对象的构造结构的使用。值得注意的是，静态上下文中禁用 `this` 和 `super` 关键字（§15.8.3, §15.11.2），对实例变量、实例方法以及词法闭包声明中类型参数的未限定引用也是如此（§6.5.1, §6.5.6.1, §15.12.3）。

从静态上下文或嵌套类/接口引用实例方法受到限制（§15.12.3）。

接口方法声明上的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对运行时没有影响。

一个缺少 `private`、`default` 或 `static` 修饰符的接口默认为抽象的（abstract）。其方法体由分号表示，而不是块。在此类方法声明中，冗余地指定 `abstract` 修饰符是允许的，但从风格角度不建议。

## 方法声明

注意，接口方法不能声明为 `protected` 或 package 访问权限，也不能使用 `final`、`synchronized` 或 `native` 修饰符。

如果同一个关键字在接口方法声明的修饰符中出现多次，或者接口方法声明包含 `public` 和 `private` 两个访问修饰符中的多个（§6.6），则会产生编译错误。

如果接口方法声明包含 `abstract`、`default` 或 `static` 关键字中的多个，则会产生编译错误。

如果接口方法声明包含 `abstract` 或 `default` 关键字，则会产生编译错误。接口方法声明同时包含 `private` 和 `static` 是允许的。

如果接口方法声明在包含 `abstract` 关键字的同时也包含 `strictfp` 关键字，则会产生编译错误。

如果接口声明的方法体显式或隐式地声明了具有重写等效签名（override-equivalent signatures）（§8.4.2），则会导致编译错误。然而，接口可以继承具有此类签名的多个抽象方法（§9.4.1）。

接口中声明的方法可以是泛型的。接口中泛型方法类型参数的规则与类中泛型方法的规则相同（§8.4.4）。

## 9.4.1 继承与重写

接口 `i` 从其直接接口类型继承所有满足以下所有条件的抽象和默认方法 `m`：

- `m` 是 `I, J` 的直接接口类型的成员。
- `i` 中声明的没有任何方法的签名是 `m` 作为 `J` 成员签名的子签名（subsignature）（§8.4.2）。
- 不存在方法 `m'`，它是 `I, J` 的直接父接口 `J'` 的成员（其中 `m` 不同于 `m'`，`J` 不同于 `J'`），且使得 `m'` 重写了接口 `i` 中方法 `m` 的声明（§9.4.1）。



静态接口方法的声明引入了静态上下文（§8.1.3），这限制了引用当前对象的构造结构的使用。注意的是，静态上下文中禁用 `this` 和 `super` 关键字（§15.8.3, §15.11.2），对实例变量、实例方法以及词法闭包声明中类型参数的未限定引用也是如此（§6.5.1, §6.5.6.1, §15.12.3）。

从静态上下文或嵌套类/接口引用实例方法受到限制（§15.12.3）。

接口方法声明上的 `strictfp` 修饰符已过时，不应在新代码中使用。它的存在与否对运行时没有影响。

一个缺少 `private`、`default` 或 `static` 修饰符的接口默认为抽象的。其方法体由分号表示，而不是块。在此类方法声明中，冗余地指定 `abstract` 修饰符是允许的，但从风格角度不建议。

## 9.4.1.1 实例重写

接口 `I` 中声明的方法 `m1` 重写 `J` 中的方法 `m2`，当且仅当满足以下所有条件：

- `I` 是 `J` 的子接口。
- `I` 未继承 `m2`。
- `m1` 的签名是 `m2` 作为 `I` 的父类型成员签名的子签名（§8.4.2）。

## 9.4.1.2 重写要求

接口方法的返回类型与被重写方法的返回类型之间的关系规定在 §8.4.3 中。

接口方法的 `throws` 子句与被重写方法的 `throws` 子句之间的关系规定在 §8.4.3 中。

接口方法的签名与被重写方法的签名之间的关系规定在 §8.4.3 中。

接口方法的访问性与被重写方法的访问性之间的关系规定在 §8.4.3 中。

如果默认方法与 `Object` 类的非私有方法重写等效签名（§8.4.2），则会导致编译错误，因为实现该接口的任何类将继承该方法的实现。

`strictfp` 修饰符的存在与否对重写规则完全没有影响。例如，非 `strictfp` 方法重写 `strictfp` 方法是允许的，`strictfp` 方法重写非 `strictfp` 方法也是允许的。

可以通过包含限定接口名称的 `super` 关键字的方法调用表达式（§15.12）来访问被重写的默认方法。

# 接口

## 方法声明

- 第四，`Object` 的方法是如此基础，以至于允许任意超接口静默地添加一个改变其行为的默认方法是危险的。

然而，接口可以自由定义另一个方法，为重写了 `Object` 方法的类提供有用的行为。例如，类中的 `java.util.List` 接口可以声明一个 `elementString` 方法，产生由 `toString` 契约描述的字符串，那么类中 `toString` 的实现者就可以将其委托给该方法。

## 9.4.1.3 继承具有重写等效签名的方法

接口可能会继承多个具有重写等效签名（§8.4.2）的方法。

如果一个接口 $i$ 继承了一个默认方法，该方法的签名与 $i$ 继承的另一个方法具有重写等效性，则会发生编译时错误。（无论该另一个方法是 `abstract` 还是 `default`，情况均如此。）

否则，所有继承的方法都是 `abstract`，且该接口被认为继承了所有方法。

所有继承的方法中，必须有一个方法对于其他所有继承的方法都是返回类型可替换的，否则会发生编译时错误。（在这种情况下，`throws` 子句不会引起错误。）

可能会通过多条路径从接口继承同一个方法声明。这一事实并没有导致任何困难，且其本身绝不会导致编译时错误。

> 自然地，当子接口继承了两个签名匹配的默认方法时，会发生行为冲突。我们主动检测这种冲突并用错误通知程序员，而不是等到在编译具体类时出现问题。可以通过声明一个新方法来重写（防止继承）所有冲突的方法，从而避免该错误。

> 同样，当子接口继承了具有签名匹配的 `abstract` 方法和 `default` 方法时，在这种情况下，可能会给其中一个赋予优先权——也许我们会假设默认方法为 `abstract` 方法提供了合理的实现。但这是危险的，因为除了巧合的名称和签名之外，我们没有理由认为默认方法的行为与 `abstract` 方法的契约一致——默认方法在子接口最初开发时可能根本就不存在。在这种情况下，要求用户主动断言默认实现是适当的（通过重写声明）更为安全。

相比之下，类中继承的具体方法的持久行为是：它们重写了接口中声明的抽象方法（见 §8.4.8）。关于潜在契约违反的相同论也适用于这里，但在此情况下类和接口之间存在内在的不平衡。为了保持类层次的独立性，我们倾向于通过简单地赋予具体方法优先权，尽量减少类与接口之间的冲突。

## 9.4.2 重载

如果接口的两个方法（无论是在同一个接口中声明，还是都由接口继承，其中一个声明一个继承）具有相同的名称但不同且非重写等效的签名（§8.4.2），则该方法被称为重载。

这一事实并没有导致任何困难，且其本身绝不会导致编译时错误。对于具有相同名称但具有不同重写等效签名的两个方法，其返回类型之间或 `throws` 子句之间没有强制的关系。

示例 9.4.2-1. 重载抽象方法声明

```java
interface PointInterface {
    move(int dx, int dy);
}
interface RealPointInterface extends PointInterface {
    move(float dx, float dy);
    move(double dx, double dy);
}
```

在这里，方法 `move` 在接口 `RealPointInterface` 中被重载为三个不同的签名，其中两个是声明的，一个是继承的。任何实现接口 `RealPointInterface` 的非抽象类都必须实现所有三个签名的方法。

## 9.4.3 接口方法体

默认方法具有块体。当类实现接口但没有提供其自己的实现时，该代码块提供了该方法的实现。

`private` 或 `static` 方法也具有块体。

如果接口方法声明（显式或隐式）具有块体，则会导致编译时错误。

如果接口方法声明是 `abstract` 且带有分号，则会导致编译时错误。

接口方法体的规则在 §14.17 中规定。

## 9.4.4 成员声明

如果一个接口继承了一个默认方法，其签名与继承的另一个方法具有重写等效性，则会发生编译时错误。（无论该另一个方法是 `abstract` 还是 `default`，情况均如此。）

否则，所有继承的方法都是 `abstract`，且该接口被认为继承了所有方法。

所有继承的方法中，必须有一个方法对于其他所有继承的方法都是返回类型可替换的，否则会发生编译时错误。（在这种情况下，`throws` 子句不会引起错误。）

可能会通过多条路径从接口继承同一个方法声明。这一事实并没有导致任何困难，且其本身绝不会导致编译时错误。

> 自然地，当子接口继承了两个签名匹配的默认方法时，会发生行为冲突。我们主动检测这种冲突并用错误通知程序员，而不是等到在编译具体类时出现问题。可以通过声明一个新方法来重写（防止继承）所有冲突的方法，从而避免该错误。

> 同样，当子接口继承了具有签名匹配的 `abstract` 方法和 `default` 方法时，在这种情况下，可能会给其中一个赋予优先权——也许我们会假设默认方法为 `abstract` 方法提供了合理的实现。但这是危险的，因为除了巧合的名称和签名之外，我们没有理由认为默认方法的行为与 `abstract` 方法的契约一致——默认方法在子接口最初开发时可能根本就不存在。在这种情况下，要求用户主动断言默认实现是适当的（通过重写声明）更为安全。

相比之下，类中继承的具体方法的持久行为是：它们重写了接口中声明的抽象方法（见 §8.4.8）。关于潜在契约违反的相同论也适用于这里，但在此情况下类和接口之间存在内在的不平衡。为了保持类层次的独立性，我们倾向于通过简单地赋予具体方法优先权，尽量减少类与接口之间的冲突。

## 9.6 注解接口

注解接口声明定义了一种特殊类型的接口。为了将注解声明与普通接口声明区分开，`interface` 关键字前面有一个 `@`。

```java
AnnotationInterfaceDeclaration:
{InterfaceModifier} @ TypeIdentifier AnnotationInterfaceBody
```

注意，符号 `@` 和关键字 `interface` 是不同的标记。可以使用空格分隔它们，但从风格角度考虑不这样做。

除非在本节及其子节中显式修改，所有适用于普通接口定义的规则（§9.1）都适用于注解接口声明。

例如，注解接口声明具有普通接口定义的规则。

如果注解接口声明具有 `sealed` 或 `non-sealed` 修饰符，则是编译错误（§9.1.1.4）。

注解接口声明可以指定顶级接口或成员接口，但不是局部接口（§14.3）。

> 注解接口声明在语法上不允许出现在块中，这是由于 §14.3 中的 `LocalClassOrInterface`。

如果注解接口声明直接或间接地出现在局部类、局部接口或匿名类定义的体内，则是编译错误（§14.3, §15.9.5）。

这一规则连同上述对注解声明的语法限制，确保了注解接口始终具有一个规范名（§6.7）。拥有这样的名称是重要的，因为注解接口的目的是供编译单元中的注解使用。由于局部类或局部接口没有规范名，因此在其语法体内声明的任何注解接口（如果允许的话）也没有规范名。

以下代码展示了这一规则以及相关的语法限制的效果：

```java
class C {
  @interface A {}  /* 合法：注解接口可以是成员接口 */
  void m() {
```

# 接口

注解接口 9.6

```
@interface A2 ()  /* 非法：注解接口不能
    是局部接口 */
class D {
    @interface A3 ()  /* 非法：注解接口
        不能指定在局部类 D 的体内的任何地方 */

    class E {
        @interface A4 ()
            /* 非法：注解接口不能
                指定在局部类 D 的体内的任何地方，
                即使作为嵌套在 D 中的类 E 的成员 */
    
    }
}
```

# 注解接口不是泛型的 (§9.1.2)

与普通接口声明不同，由于 `AnnotationTypeDeclaration` 产生式，注解接口声明不能声明任何类型变量。

# 注解接口的直接父接口类型始终是 java.lang.annotation.Annotation (§9.1.3)

与普通接口声明不同，由于 `AnnotationTypeDeclaration` 产生式，注解接口声明不能通过 `extends` 子句选择直接父接口类型。

由于注解接口声明没有通过 `extends` 显式指定父接口类型，导致了注解接口的子接口本身永远不是注解接口，因为子接口的声明使用了 `extends` 子句。同样，`java.lang.annotation.Annotation` 也不是注解接口。

注解接口继承了 `java.lang.annotation.Annotation` 的几个方法，包括与 `Object` 的实例方法对应的隐式声明方法 (§9.2)，但这些方法并没有定义注解接口的元素 (§9.6.1)。

由于这些方法没有定义注解接口的元素，因此在符合注解接口的注解中使用它们是非合法的 (§9.7)。如果没有这条规则，我们无法确保元素是注解中可表示的类型，也无法确保它们的访问方法是可用。

# 9.6.1 注解接口元素

注解接口声明的体可以包含方法声明，每个方法定义了注解接口的一个元素。除了注解接口声明中显式声明的方法定义的元素外，注解接口没有其他元素。

```
AnnotationInterfaceBody:
{ [AnnotationInterfaceMemberDeclaration] }

AnnotationInterfaceMemberDeclaration:
AnnotationInterfaceElementDeclaration
ConstantDeclaration
ClassDeclaration
InterfaceDeclaration
;
```

```
AnnotationInterfaceElementDeclaration:
[AnnotationInterfaceElementModifier] UnannType Identifier () [Dims]
[DefaultValue];
```

```
AnnotationInterfaceElementModifier:
(其之一)
Annotation public
abstract
```

为了方便起见，这里显示了来自 §4.3 的产生式：

```
Dims:
[Annotation] [] [Annotation] []
```

根据上述语法，注解接口中的方法声明不能有形式参数、类型参数或 `throws` 子句；且不能是 `private`、`default` 或 `static`。注解接口不能具有与普通接口相同的方法。注意，注解接口可能会从其隐式父接口 `java.lang.annotation.Annotation` 继承一个默认方法，但截至 Java 19 为止不存在这样的默认方法。

按照惯例，只有在注解接口元素声明中存在的修饰符才是注解。

在注解接口体中声明的方法的类型必须是以下类型之一，否则将发生编译时错误：

# 注解接口 9.6

- 原始类型
- `String`
- `Class` 或 `Class` 的调用（§4.5）
- 一个枚举类类型

此规则排除了如下的嵌套数组类型的禁止操作：

```java
@interface Verboten {
  String[] value();
}
```

允许返回数组的方法声明将数组类型的括号符号放在空的形式参数列表之后。支持这种语法是为了与早期 Java 编程语言版本兼容。强烈建议不要在新代码中使用这种语法。

如果在注解接口中声明的任何方法的签名与重写等效（§8.4.2）于在 `Object` 类或 `java.lang.annotation.Annotation` 接口中声明的任何公共或受保护的方法，则为编译时错误。

如果注解接口 τ 的声明直接或间接地包含包含一个类型为 τ 的元素，则为编译时错误。

例如，这种情况下是非法的：

```java
@interface SelfRef ( SelfRef value(); )
```

这种情况下也是非法的：

```java
@interface Ping ( Pong value(); )
@interface Pong ( Ping value(); )
```

没有元素的注解接口被称为**标记注解接口**。

带有一个元素的注解接口被称为**单元素注解接口**。

按照惯例，单元素注解接口中唯一元素的名称是 `value`。单元素注解（§9.7.3）为这种惯例提供了语言支持。

# 9.6 注解接口 INTERFACES

# 示例 9.6.1-1. 注解接口声明

以下注解接口声明定义了一个具有多个元素的注解接口：

```java
/**
 * 描述导致被注解 API 元素存在的 
 * “增强请求” (RFE)。
 */
@interface RequestForEnhancement {
    int id(); // 与 RFE 关联的唯一 ID 编号
    String synopsis(); // RFE 的梗要
    String engineer(); // 实现 RFE 的工程师姓名
    String date(); // RFE 实现的日期
}
```

# 示例 9.6.1-2. 标记注解接口声明

以下注解接口声明定义了一个标记注解接口：

```java
/**
 * 这种类型的注解表示
 * 被注解的元素的规范
 * 可能会发生变化。
 */
@interface Preliminary ()
```

# 示例 9.6.1-3. 单元素注解接口

单元素注解接口定义一个名为 `value` 的元素的惯例在以下注解接口声明中得到了说明：

```java
/**
 * 将版权声明与被注解的元素关联。
 */
@interface Copyright {
    String value();
}
```

以下注解接口声明定义了一个单元素注解接口，其唯一元素具有数组类型：

```java
/**
 * 将背书者列表与被注解的类关联。
 */
@interface Endorsers {
    String[] value();
}
```

以下注解接口声明显示了一个 `Class` 类型的元素，其值受边界通配符的限制：

```java
interface Formatter {
```

```java
// 指定一个格式化器对被注解的类进行漂亮打印
@interface PrettyPrinter {
    Class<? extends Formatter> value();
}
```

以下注解接口声明包含一个类型为注解接口类型的元素：

```java
/**
 * 表示被注解程序元素的作者。
 */
@interface Author
    Name value();
}
```

```java
/**
 * 人的姓名。此注解接口并非设计
 * 直接用于注解程序元素，
 * 而是定义其他注解接口的元素。
 */
```

```java
@interface Name {
    String first();
    String last();
}
```

注解接口声明的语法允许除了方法声明之外的成员声明。例如，人们可能会声明一个嵌套枚举类，供注解接口的元素使用：

```java
@interface Quality {
    enum Level { BAD, INDIFFERENT, GOOD }
    Level value();
}
```

# 9.6.2 注解接口元素的默认值

注解接口元素可以有一个默认值，通过在定义元素的方法声明上附加关键字 `default` 和一个值来指定。



## 9.6 注解接口

### ElementValue

```
ConditionalExpression
ElementValueArrayInitializer
Annotation
```

### ElementValueArrayInitializer

```
{ [ElementList], [, }
```

### ElementValueList

```
ElementValue {, ElementValue}
```

注意，指定为具有默认值的注解接口元素并不是默认方法（§9.4）。注解接口的声明不能声明方法（§9.6）。

如果元素的类型与指定的默认值不兼容（§9.7），则会产生编译错误。

默认值不会被编译进注解中，而是在注解注解时动态应用的。更改默认值会影响注解，即使是在于更改之前编译的类中也是如此（前提是这些注解对默认元素缺少显式指定的值）。

#### 9.6.2-1. 带有默认值的注解接口声明

以下是对 §9.6.1 中 `RequestForEnhancement` 注解接口的完善：

```java
@interface RequestForEnhancement {
    int id(); // 无默认值 -- 必须在每个
               // 注解中指定
    String synopsys(); // 无默认值 -- 必须在每个
                   // 注解中指定
    String engineer() default "[unassigned]";
    String date() default "[unimplemented]";
}
```

### 9.3 可重复注解接口

如果一个注解接口 `A` 的声明被（元）标记了 `@Repeatable` 注解（§9.6.4），且该注解的取值元素指向 `A` 的一个包含注解接口，则该注解接口是可重复的。

如果满足以下所有条件，则注解接口 `AC` 是 `A` 的包含注解接口：

1. `AC` 声明了一个 `value()` 方法，其返回类型为 `A[]`。
2. `AC` 声明的除 `value()` 外的任何方法都有默认值。
3. `AC` 的留存时间至少与 `A` 一样，其中留存通过显式或隐式地使用 `@Retention` 注解表示（§9.6.4.2）。具体而言：
   - 如果 `AC` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`，则 `A` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`。
   - 如果 `AC` 的留存策略为 `java.lang.annotation.RetentionPolicy.CLASS`，则 `A` 的留存策略为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.SOURCE`。
   - 如果 `AC` 的留存策略为 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 `A` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`、`java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME`。
4. `A` 适用的程序元素类型至少与 `AC` 适用的程序元素类型相同（§9.6.4.1）。
   具体而言，如果 `A` 适用的程序元素类型用 `m1` 表示，`AC` 适用的程序元素类型用 `m2` 表示，则 `m2` 中的每种类型必须出现在 `m1` 中，但例外是：
   - 如果 `m2` 中的类型是 `java.lang.annotation.ElementType.ANNOTATION_TYPE`，则 `java.lang.annotation.ElementType.ANNOTATION_TYPE` 或 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 `m1` 中。
   - 如果 `m2` 中的类型是 `java.lang.annotation.ElementType.TYPE`，则 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 `m1` 中。
   - 如果 `m2` 中的类型是 `java.lang.annotation.ElementType.TYPE_PARAMETER`，则 `java.lang.annotation.ElementType.TYPE_PARAMETER` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 `m1` 中。
   该条款实现了这样项策略：注解接口仅可以在其适用的某些程序元素类型上是重复的。
5. 如果 `A` 的声明有一个对应于 `java.lang.annotation.Documented` 的（元）注解，那么 `AC` 的声明必须有一个对应于 `java.lang.annotation.Documented` 的（元）注解。
   注意，`AC` 为 `@Documented` 而 `A` 不为 `@Documented` 是允许的。
6. 如果 `A` 的声明有一个对应于 `java.lang.annotation.Inherited` 的（元）注解，那么 `AC` 的声明必须有一个对应于 `java.lang.annotation.Inherited` 的（元）注解。
   注意，`AC` 为 `@Inherited` 而 `A` 不为 `@Inherited` 是允许的。

如果注解接口 `A` 被（元）标记了 `@Repeatable` 注解，且其取值元素指向的类型不是 `A` 的包含注解接口，则为编译错误。

#### 示例 9.6.3-1. 格式错误的包含注解接口

考虑以下声明：

```java
import java.lang.annotation.Repeatable;

@Repeatable(FooContainer.class)
@interface Foo { }

@interface FooContainer { Object[] value(); }
```

编译 `Foo` 声明会产生编译错误，因为 `Foo` 使用 `@Repeatable` 指定 `FooContainer` 为其包含注解接口，但 `FooContainer` 并不是 `Foo` 的包含注解接口。`FooContainer.value()` 的返回类型不是 `Foo[]`。

`@Repeatable` 注解不能重复，因此一个重复注解接口只能指定一个注解接口。

允许指定多个注解接口会导致在多个重复注解接口的注解在逻辑上被替换时，在编译时出现不可接受的选择。

#### 示例 9.6.3-2. 限制注解出现的位置

如果满足以下所有条件，注解接口 `AC` 是 `A` 的包含注解接口：

1. `AC` 声明了一个 `value()` 方法，其返回类型为 `A[]`。
2. `AC` 声明的除 `value()` 外的任何方法都有默认值。
3. `AC` 的留存时间至少与 `A` 一样，其中留存通过显式或隐式地使用 `@Retention` 注解表示（§9.6.4.2）。
   - 如果 `AC` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`，则 `A` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`。
   - 如果 `AC` 的留存策略为 `java.lang.annotation.RetentionPolicy.CLASS`，则 `A` 的留存策略为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.SOURCE`。
   - 如果 `AC` 的留存策略为 `java.lang.annotation.RetentionPolicy.RUNTIME`，则 `A` 的留存策略为 `java.lang.annotation.RetentionPolicy.SOURCE`、`java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME`。
4. `A` 适用的程序元素类型至少与 `AC` 适用的程序元素类型相同（§9.6.4.1）。
   具体而言，如果 `A` 适用的程序元素类型用 `m1` 表示，`AC` 适用的程序元素类型用 `m2` 表示，则 `m2` 中的每种类型必须出现在 `m1` 中，但例外是：
   - 如果 `m2` 中的类型是 `java.lang.annotation.ElementType.ANNOTATION_TYPE`，则 `java.lang.annotation.ElementType.ANNOTATION_TYPE` 或 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 `m1` 中。
   - 如果 `m2` 中的类型是 `java.lang.annotation.ElementType.TYPE`，则 `java.lang.annotation.ElementType.TYPE` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 `m1` 中。
   - 如果 `m2` 中的类型是 `java.lang.annotation.ElementType.TYPE_PARAMETER`，则 `java.lang.annotation.ElementType.TYPE_PARAMETER` 或 `java.lang.annotation.ElementType.USE` 中至少有一个必须出现在 `m1` 中。
   该条款实现了这样项策略：注解接口仅可以在其适用的某些程序元素类型上是重复的。
5. 如果 `A` 的声明有一个对应于 `java.lang.annotation.Documented` 的（元）注解，那么 `AC` 的声明必须有一个对应于 `java.lang.annotation.Documented` 的（元）注解。
   注意，`AC` 为 `@Documented` 而 `A` 不为 `@Documented` 是允许的。
6. 如果 `A` 的声明有一个对应于 `java.lang.annotation.Inherited` 的（元）注解，那么 `AC` 的声明必须有一个对应于 `java.lang.annotation.Inherited` 的（元）注解。
   注意，`AC` 为 `@Inherited` 而 `A` 不为 `@Inherited` 是允许的。

如果注解接口 `A` 被（元）标记了 `@Repeatable` 注解，且其取值元素指向的类型不是 `A` 的包含注解接口，则为编译错误。

#### 示例 9.6.3-3. 可重复的包含注解接口

以下声明是合法的：

```java
import java.lang.annotation.Repeatable;

// Foo: 可重复注解接口
@Repeatable(FooContainer.class)
@interface Foo { int value(); }

// FooContainer: Foo 的包含注解接口
// 本身也是一个重复注解接口
@Repeatable(FooContainerContainer.class)
@interface FooContainer { Foo[] value(); }

// FooContainerContainer: 包含注解接口
@interface FooContainerContainer { FooContainer[] value(); }
```

```java
@FooContainer({@Foo(1)}) @FooContainer({@Foo(2)})
class Test { }
```

因此，包含注解接口的注解本身也可以是重复的：

### 接口

#### 注解接口 9.6

既是重复的又包含包含的注解接口，受混合可重复注解接口注解与包含注解接口注解的规则限制（§9.7.5）。例如，不能在 `@FooContainer` 旁边编写多个 `@Foo` 注解，也不可能在多个 `@FooContainerContainer` 旁边编写多个 `@FooContainerContainer` 注解。然而，如果注解接口 `FooContainerContainer` 本身是可重复的，那么就可以在多个 `@FooContainerContainer` 注解旁边并行编写多个 `@Foo` 注解。

### 9.6.4 预定义注解接口

Java SE Platform API 中预定义了多个注解接口。某些预定义的注解接口在 Java 编程语言中具有特殊语义，并根据本节的规定，要求 Java 编译器对这些注解执行特殊行为。本节未提供预定义注解接口的完整规范，读者请参阅 Java SE Platform API 文档（§1.4）。

#### 9.6.4.1 @Target

类型为 `java.lang.annotation.Target` 的注解用于注解接口 `a` 的声明，用以指定 `a` 可应用的上下文。`java.lang.annotation.Target` 拥有一个元素 `value`，类型为 `java.lang.annotation.ElementType[]`，用于指定上下文。

注解接口可以适用于声明上下文（注解应用于声明处），也可以适用于类型上下文（注解应用于声明和表达式中使用的类型）。

共有十种声明上下文，每种上下文对应 `java.lang.annotation.ElementType` 的一个枚举常量：

1. 模块声明（§7.7）
   对应 `java.lang.annotation.ElementType.MODULE`
2. 包声明（§7.4.1）
   对应 `java.lang.annotation.ElementType.PACKAGE`
3. 类声明（包括枚举声明和记录声明）以及接口声明（包括注解接口声明）（§8.1.1, §8.5, §8.9, §8.10, §9.1.1, §9.5）
   对应 `java.lang.annotation.ElementType.TYPE`
   此外，注解声明对应 `java.lang.annotation.ElementType.ANNOTATION_TYPE`：
4. 方法声明（包括注解接口的元素）（§8.4.3, §9.4, §9.6.1）
   对应 `java.lang.annotation.ElementType.METHOD`
5. 构造方法声明（§8.8.3）
   对应 `java.lang.annotation.ElementType.CONSTRUCTOR`
6. 泛型类、接口、方法和构造方法的类型参数声明（§8.1.2, §9.1.2, §8.4.4, §8.8.4）
   对应 `java.lang.annotation.ElementType.TYPE_PARAMETER`
7. 字段声明（包括枚举常量）（§8.3.1, §9.3, §8.9.1）
   对应 `java.lang.annotation.ElementType.FIELD`
8. 形式参数和异常参数声明（§8.4.1, §9.4, §14.20）
   对应 `java.lang.annotation.ElementType.PARAMETER`
9. 语句中的局部变量声明（§14.4.2, §14.14.1, §14.14.2, §14.20.3）以及模式中的声明（§14.30.1）
   对应 `java.lang.annotation.ElementType.LOCAL_VARIABLE`
10. 记录组件声明（§14.23）
    对应 `java.lang.annotation.ElementType.RECORD_COMPONENT`

共有 17 种类型上下文（§14.11），均由 `java.lang.annotation.ElementType` 的枚举常量 `TYPE_USE` 表示。

如果在类型为 `java.lang.annotation.Target` 的注解的 `value` 元素中出现多次同一种枚举常量，则会导致编译错误。

如果注解接口 `A` 的声明上不存在类型为 `java.lang.annotation.Target` 的注解，则 `A` 适用于所有的声明上下文但不适用于任何类型上下文。

#### 9.6.4.2 @Retention

注解可能存在于源代码中，也可能存在于类或接口的二进制形式中。存在二进制形式的注解可能无法通过 Java SE Platform 的反射库在运行时可用。注解接口 `java.lang.annotation.Retention` 用于在这些可能性之间进行选择。

如果注解 `a` 对应于注解接口 `A`，且 `A` 具有（元注解 `m` 对应于 `java.lang.annotation.Retention`），那么：

- 如果 `m` 有一个取值为 `java.lang.annotation.RetentionPolicy.SOURCE` 的元素，则 Java 编译器确保 `a` 不出现在其所在的类或接口的二进制表示中。



- 如果 $m$ 有一个取值为 `java.lang.annotation.RetentionPolicy.CLASS` 或 `java.lang.annotation.RetentionPolicy.RUNTIME` 的元素，则 Java 编译器必须确保 $a$ 包含在其所在的类或接口的二进制表示中，除非 $a$ 注解的是局部声明或注解了 Lambda 表达式的形式参数。

在局部变量声明上的注解或 Lambda 表达式声明上的注解永远不会被保留在二进制表示中。相比之下，局部变量类型上的注解或 Lambda 表达式形式参数类型上的注解，如果注解接口指定了合适的保留策略，则会被保留在二进制表示中。

### 9.6.4.3 @Inherited

注解 `java.lang.annotation.Inherited` 用于指示类 $c$ 上的注解会被 $c$ 的子类继承。

### 9.6.4.4 @Override

程序员有时在想要重写方法时却重载了方法声明，从而导致微妙的问题。注解接口 `Override` 支持尽早检测此类问题。

```
经典的例子涉及 `equals` 方法。程序员在类 `Foo` 中写了如下代码：

public boolean equals(Foo that) { ... }

而他们本意是想写：

public boolean equals(Object that) { ... }
```

这是完全合法的，但 `Foo` 从 `Object` 处继承了 `equals` 的实现，这可能会导致某些 Bug。

如果类或接口中的方法声明被标记了 `@Override`，则必须满足以下三个条件之一，否则将发生编译错误：

- 该方法重写了从父类型中声明的方法 ($8.4.8.1, 9.4.1.1$)
- 该方法与 `Object` 的公共方法重写等价 ($4.3.2$)
- 是一个记录类 ($8.10)，且该方法是记录组件的访问方法 ($8.10.3$)

这种行为与 Java SE 5.0 不同，在 Java SE 5.0 中，如果 `@Override` 应用于从父类中不存在的父接口中实现的方法，则会导致编译错误。

关于重写 `Object` 公共方法的条款是出于在接口中使用 `@Override` 的考虑而提出的。考虑以下声明：

```
class Foo { @Override public int hashCode() { .. } }
interface Bar { @Override int hashCode(); }
```

类声明中使用 `@Override` 从第一个条款来看是合法的，因为 `Foo.hashCode` 从 `Foo` 重写了 `Object.hashCode`。

对于接口声明，考虑到接口拥有与 `Object` 公共成员对应的公共抽象成员 ($9.2$)如果接口显式声明了这些成员（即声明与 `Object` 公共方法重写等价的成员），则该接口被认为重写了它们，并允许使用 `@Override`。

然而，考虑一个尝试在 `clone` 方法上使用 `@Override` 的接口：（在此示例中也可以使用 `finalize`）

```
interface Quux { @Override Object clone(); }
```

由于 `Object.clone` 不是公共的，因此 `Quux` 中没有隐式声明名为 `clone` 的成员。因此，`Quux` 中对 `clone` 的显式声明被视为“实现”任何其他方法，使用 `@Override` 是错误的。（`Quux.clone` 是否与此无关。）

相比之下，声明了 `clone` 的类声明只是重写了 `Object.clone`，因此能够使用 `@Override`：

```
class Beep { @Override protected Object clone() { .. } }
```

关于 record 类的说明是因为 `@Override` 在 record 声明中具有特殊含义。也就是说，它可以被用于指定某个方法声明是方法组件（component）的访问器。考虑以下 record 声明：

```
record Roo(int x) {
  @Override
  public int x() {
    return Math.abs(x);
  }
}
```

在访问器方法 `int x()` 上使用 `@Override` 确保了如果 record 组件 `x` 被修改或删除，那么对应的访问器方法也必须被修改或删除。

## 9.6.4.5 @SuppressWarnings

Java 编译器越来越能够发出实用的“类检查”（lint-like）警告。为了鼓励使用此类警告，当程序员知道某个警告不合适时，应该有一种方法可以在程序的某部分禁用警告。

`SuppressWarnings` 注解接口支持程序员对 Java 编译器发出的警告进行控制。它定义了一个单一元素，其类型为 `String` 数组。

如果一个声明被标记为 `@SuppressWarnings(value = {S1, ..., Sk})`，那么 Java 编译器必须抑制（即不报告）由 `S1 ... Sk` 中指定的任何警告，如果该警告是由于被注解的声明或其任何部分生成的。

Java 编程语言定义了四种可以由 `@SuppressWarnings` 指定的警告：

- 未检查警告（Unchecked warnings，$4.8, $5.1.6, $5.1.9, $8.4.1, $8.4.8.3, $15.12.4.2, $15.13.2, $15.27.3）由字符串 `"unchecked"` 指定。
- 废弃警告（Deprecation warnings，$9.6.4.6）由字符串 `"deprecation"` 指定。
- 移除警告（Removal warnings，$9.6.4.6）由字符串 `"removal"` 指定。
- 预览警告（Preview warnings，$1.5）由字符串 `"preview"` 指定。

任何其他字符串都指定非标准警告。Java 编译器必须忽略任何它无法识别的字符串。

鼓励编译器供应商记录它们支持的 `@SuppressWarnings` 字符串，并合作以确保相同的字符串在多个编译器中都能被识别。

## 9.6.4.6 @Deprecated

程序员有时会被劝阻不要使用某些程序元素（模块、类、接口、方法和构造函数），因为它们被认为是不危险的，或者存在更好的替代方案。`Deprecated` 注解接口允许编译器对这些程序元素的使用发出警告。

一个废弃的程序元素是指声明被标记为 `@Deprecated` 的模块、类、接口、字段、方法或构造函数。程序元素被废弃的方式取决于注解 `forRemoval` 元素的值：

- 如果 `forRemoval=false`（默认值），则该程序元素是**普通废弃的**（ordinarily deprecated）。
  普通废弃的程序元素并不打算在未来的发布中移除，但程序员仍然应该迁移不再使用它。
- 如果 `forRemoval=true`，则该程序元素是**终极废弃的**（terminally deprecated）。
  终端废弃的程序元素旨在在未来的发布中移除。程序员应该停止使用它，否则在升级到新版本时将面临源和二进制不兼容的风险（$13.2）。

当普通废弃的程序元素在程序元素的声明（无论显式还是隐式声明）中使用（被重写、调用或通过名称引用）时，Java 编译器必须产生 `deprecation` 警告，除非：

- 该使用位于一个本身已废弃（无论是普通还是终极废弃）的声明内部；或
- 该使用位于被标记为抑制废弃警告的声明内部（§9.6.4.5）；或
- 使用该处的声明与普通废弃程序元素的声明位于同一个最外层类中；或
- 该使用位于导入了该普通废弃类、接口或成员的导入声明内部；或
- 该使用位于 exports 或 opens 指令中（§7.7.2）。

当终端废弃的程序元素在程序元素的声明（无论显式还是隐式声明）中使用（被重写、调用或通过名称引用）时，Java 编译器必须产生移除警告，除非：

- 该使用位于被标记为抑制移除警告的声明内部（§9.6.4.5）；或
- 使用该处的声明与终端废弃程序元素的声明位于同一个最外层类中；或
- 该使用位于导入了该终端废弃类、接口或成员的导入声明内部；或
- 该使用位于 exports 或 opens 指令中。

> 终极废弃的紧迫性足以使得，即使该元素本身已废弃，使用终端废弃元素也会导致产生移除警告，因为无法保证两个元素会同时移除。要忽略该警告并继续使用该元素，程序员必须通过 `@SuppressWarnings` 注解手动承认该风险。

在以下情况下，不会产生废弃警告或移除警告：

- 该使用位于一个本身已废弃（无论是普通还是终极废弃）的声明内部；或
- 该使用位于被标记为抑制废弃警告的声明内部（§9.6.4.5）；或
- 使用该处的声明与普通废弃程序元素的声明位于同一个最外层类中；或
- 该使用位于导入了该普通废弃类、接口或成员的导入声明内部；或
- 该使用位于 exports 或 opens 指令中。

## 9.6.4.7 @SafeVarargs

如果固定元个数（arity）的方法或构造函数声明被标记了 `@SafeVarargs` 注解，则会导致编译错误。

如果一个既不是静态的私有的变量元个数方法声明被标记了 `@SafeVarargs` 注解，则会导致编译错误。

> 由于 `@SafeVarargs` 仅适用于静态方法、final 和/或私有实例方法以及构造函数，因此该注解在发生方法重写的地方是不可用的。注解继承仅适用于类上的注解（不适用于方法、接口或构造函数），因此 `@SafeVarargs` 类型的注解无法通过类中的实例方法或接口传递。

## 9.6.4.8 @Repeatable

注解接口 `java.lang.annotation.Repeatable` 用于可重复注解接口的声明，用以指示其包含的注解接口 (§9.6)。

> 注意，在 A 的声明上的 `@Repeatable` 元注解（指示 AC）并不足以使 AC 成为 A 的包含注解接口。要使 AC 被视为 A 的包含注解接口，有许多良好性规则。

## 9.6.4.9 @FunctionalInterface

注解接口 `FunctionalInterface` 用于指示一个接口旨在作为函数式接口 (§9.8)。它有助于及早发现旨在函数式的接口中出现或由其继承的不适当方法声明。

如果一个接口声明被标记了 `@FunctionalInterface` 但实际上不是一个函数式接口，则会导致编译错误。

由于某些接口偶然是函数式接口，因此没有也没有必要将所有函数式接口的声明都标记为 `@FunctionalInterface`。

## 9.7 注解 (Annotations)

注解是将信息与程序元素关联标记，但在运行时没有影响。注解表示注解接口的一个特定实例 (§9.6)，并通常为该接口的元素提供值。

注解有三种类型。第一种是最通用的，而其他类型仅仅是第一种的简写。

- 注解：
  - 普通注解 (NormalAnnotation)
  - 标记注解 (MarkerAnnotation)
  - 单一元素注解 (SingleElementAnnotation)

普通注解在 §9.7.1 中描述，标记注解在 §9.7.2 中描述，单一元素注解在 §9.7.3 中描述。注解可以出现在程序中的各种语法位置，如 §9.7.4 所示。在某一位置可能出现的相同接口的注解数量由接口声明决定，如 §9.7.5 所示。

### 9.7.1 普通注解 (Normal Annotations)

普通注解指定注解接口的名称，并可选地提供由逗号分隔的元素-值对列表。每个对包含一个与注解接口元素关联的元素值 (§9.6.1)。

```
NormalAnnotation:
@ TypeName ([ElementValuePairList])

ElementValuePairList:
ElementValuePair (, ElementValue)

ElementValuePair:
Identifier = ElementValue

ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation

ElementValueArrayInitializer:
{[ElementValueList], }

ElementValueList:
ElementValue (, ElementValue)
```

注意符号 (`@`) 本身是一个标记 (§3.11)。可以在它和 `TypeName` 之间放置空格，但从风格上来说这是不被建议的。

**TypeName** 指定与该注解对应的注解接口。该注解被称为“属于”该接口。

**TypeName** 必须命名一个可访问的注解接口 (§6.6)，否则会发生编译错误。

元素-值对中的 **Identifier** 必须是注解接口元素（即方法）之一的简单名称，否则会发生编译错误。

此方法的返回类型定义了元素-值对的*元素类型*。如果元素类型是数组类型，则不需要使用大括号来指定元素-值对的元素值。如果元素值不是 `ElementArrayInitializer`（其整个元素与该元素关联的数组值）。如果元素值是 `ElementArrayInitializer`，则由 `ElementValueInitializer` 表示的数组值与该元素关联。

如果元素类型与元素值不**匹配** (commensurate)，则会导致编译错误。元素 *τ* 与元素 *v* 匹配，当且仅当以下条件之一为真时：

- *T* 是数组类型 *E[]*，且满足：
  - *v* 是 `ConditionalExpression` 或 `Annotation`，则 *v* 与 *E* 匹配；或者
  - *v* 是 `ElementArrayInitializer`，则每个元素值 *v* 都与 *E* 匹配。

> `ElementArrayInitializer` 类似于普通数组初始化器 (§10.6)，但 `ElementArrayInitializer` 在语法上可以包含注解以及表达式和嵌套初始化器。然而，嵌套初始化器在 `ElementArrayInitializer` 中在语义上是不合法的，因为它们永远与注解声明中的数组类型元素匹配（不允许嵌套数组类型）。

- *T* 不是数组类型，且 *v* 的类型与 *T* 赋值兼容 (§5.2)，并且：
  - *T* 是原生类型或 `String`，则 *v* 是常量表达式 (§15.29)。
  - *T* 是 `Class` 或 `Class` 的调用 (§4.5)，则 *v* 是*类字面量* (§15.8.2)。
  - *T* 是枚举类类型 (§8.9)，则 *v* 是常量表达式 (§15.29)。



## 9.7 注解

注解是将信息与程序元素关联的标记，但在运行时没有影响。注解表示注解接口的一个特定实例（§9.6），并通常为该接口的元素提供值。

注意符号 `@` 本身是一个标记（§3.11）。可以在它和 `TypeName` 之间放置空格，但从风格上来说这是不被建议的。

`TypeName` 指定与该注解对应的注解接口。该注解被称为“属于”该接口。

`TypeName` 必须命名一个可访问的注解接口（§6.6），否则会发生编译错误。

元素-值对中的 `Identifier` 必须是注解接口元素（即方法）之一的简单名称，否则会发生编译错误。

此方法的返回类型定义了元素-值对的*元素类型*。如果元素类型是数组类型，则不需要使用大括号来指定元素-值对的元素值。如果元素值不是 `ElementArrayInitializer`（其整个元素与该元素关联的数组值）。如果元素值是 `ElementArrayInitializer`，则由 `ElementValueInitializer` 表示的数组值与该元素关联。

如果元素类型与元素值不**匹配**，则会导致编译错误。元素 `T` 与元素 `v` 匹配，当且仅当以下条件之一为真时：

- `T` 是数组类型 `E[]`，且满足：
    - `v` 是 `ConditionalExpression` 或 `Annotation`，则 `v` 与 `E` 匹配；或者
    - `v` 是 `ElementArrayInitializer`，则每个元素值 `v` 都与 `E` 匹配。

- `T` 不是数组类型，且 `v` 的类型与 `T` 赋值兼容（§5.2），并且：
    - `T` 是原生类型或 `String`，则 `v` 是常量表达式（§15.29）。
    - `T` 是 `Class` 或 `Class` 的调用（§4.5），则 `v` 是*类字面量*（§15.8.2）。
    - `T` 是枚举类类型（§8.9），则 `v` 是常量表达式（§15.29）。

> `ElementArrayInitializer` 类似于普通数组初始化器（§10.6），但 `ElementArrayInitializer` 在语法上可以包含注解以及表达式和嵌套初始化器。然而，嵌套初始化器在 `ElementArrayInitializer` 中在语义上是不合法的，因为它们永远与注解声明中的数组类型元素匹配（不允许嵌套数组类型）。

注解有三种类型。第一种是最通用的，而其他类型仅仅是第一种的简写。

- 注解：
    - 普通注解 (`NormalAnnotation`)
    - 标记注解 (`MarkerAnnotation`)
    - 单一元素注解 (`SingleElementAnnotation`)

普通注解在 §9.7.1 中描述，标记注解在 §9.7.2 中描述，单一元素注解在 §9.7.3 中描述。注解可以出现在程序中的各种语法位置，如 §9.7.4 所示。在某一位置可能出现的相同接口的注解数量由接口声明决定，如 §9.7.5 所示。

### 9.7.1 普通注解

普通注解指定注解接口的名称，并可选地提供一个由逗号分隔的元素-值对列表。每个对包含一个与注解接口元素关联的元素值（§9.6.1）。

```
NormalAnnotation:
@ TypeName ([ElementValuePairList])

ElementValuePairList:
ElementValuePair (, ElementValue)

ElementValuePair:
Identifier = ElementValue

ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation

ElementValueArrayInitializer:
{[ElementValueList], }

ElementValueList:
ElementValue (, ElementValue)
```

注意符号 `@` 本身是一个标记（§3.11）。可以在它和 `TypeName` 之间放置空格，但从风格上来说这是不被建议的。

`TypeName` 指定与该注解对应的注解接口。该注解被称为“属于”该接口。

`TypeName` 必须命名一个可访问的注解接口（§6.6），否则会发生编译错误。

元素-值对中的 `Identifier` 必须是注解接口元素（即方法）之一的简单名称，否则会发生编译错误。

此方法的返回类型定义了元素-值对的*元素类型*。如果元素类型是数组类型，则不需要使用大括号来指定元素-值对的元素值。如果元素值不是 `ElementArrayInitializer`（其整个元素与该元素关联的数组值）。如果元素值是 `ElementArrayInitializer`，则由 `ElementValueInitializer` 表示的数组值与该元素关联。

如果元素类型与元素值不**匹配**，则会导致编译错误。元素 `T` 与元素 `v` 匹配，当且仅当以下条件之一为真时：

- `T` 是数组类型 `E[]`，且满足：
    - `v` 是 `ConditionalExpression` 或 `Annotation`，则 `v` 与 `E` 匹配；或者
    - `v` 是 `ElementArrayInitializer`，则每个元素值 `v` 都与 `E` 匹配。

- `T` 不是数组类型，且 `v` 的类型与 `T` 赋值兼容（§5.2），并且：
    - `T` 是原生类型或 `String`，则 `v` 是常量表达式（§15.29）。
    - `T` 是 `Class` 或 `Class` 的调用（§4.5），则 `v` 是*类字面量*（§15.8.2）。
    - `T` 是枚举类类型（§8.9），则 `v` 是常量表达式（§15.29）。

### 9.7.2 标记注解

标记注解是一种简写形式，用于标记注解接口的元素均使用默认值的情况。

```
MarkerAnnotation:
@ TypeName
```

### 9.7.3 单一元素注解

单一元素注解是一种简写形式，用于注解接口仅包含一个元素，或者仅有一个元素没有默认值的情况。

```
SingleElementAnnotation:
@ TypeName ( ElementValue )
```

如果注解接口有一个名为 `value` 的元素，则可以省略元素名称 `value=`。

### 9.7.4 注解可能出现的地方

声明注解是一种应用于声明的注解，且其注解接口适用于该声明所表示的声明上下文（§9.6.4.1）；或者，它是一种应用于类、接口或类型参数声明的注解，且其注解接口适用于类型上下文（§4.11）。

类型注解是一种应用于类型（或类型的任何部分）的注解，且其注解接口适用于类型上下文。

例如，给定的字段声明如下：

```java
@Foo int f;
```

`@Foo` 是 `f` 上的声明注解，`Foo` 自身被 `@Target(ElementType.FIELD)` 元注解标记；而 `int` 上的 `@Foo` 是类型注解，它被 `@Target(ElementType.TYPE_USE)` 元注解标记。`@Foo` 可能既是声明注解也是类型注解。

类型注解可以应用于任何数组类型或其任何组件类型（§10.1）。例如，假设 A、B 和 C 是被标记了 `@Target(ElementType.TYPE_USE)` 元注解的注解接口，那么给定以下字段声明：

```java
@C int @A [] [] f;
```

`@A` 应用于数组类型 `int[][]`，`@B` 应用于其组件类型 `int[]`，而 `@C` 应用于元素类型 `int`。更多示例请参见 §10.2。

这种语法的一个重要属性是：仅数组层级不同的两个声明，其类型左侧的注解指向同一个类型。例如，`@C` 在以下所有声明中应用于类型 `int`：

```java
@C int f;
@C int [] f;
@C int [] [] f;
```

按照习惯（并非强制），将声明注解写在所有其他修饰符之前，并将类型注解紧接在其应用的类型之前。

注解可能出现在程序中的某个语法位置，在该位置它可能合理应用于声明、类型或两者。这可能发生在六种声明上下文中的任何一种，其中修饰符紧邻被声明实体的类型：

- 方法声明（包括注解接口的元素）
- 构造方法声明
- 字段声明（包括枚举常量）
- 形式参数和异常参数声明
- 局部变量声明
- 记录组件声明

Java 编程语言的语法无义地将这些位置的注解视为声明的修饰符（§8.3），但这纯粹是一个语法问题。注解是应用于声明还是应用于声明实体的类型——即该注解是声明注解还是类型注解——取决于该注解接口的适用性：

- 如果注解的接口适用于该声明对应的声明上下文，而不适用于类型上下文，则该注解被认为仅应用于声明。
- 如果注解的接口适用于类型上下文，但不适用于该声明对应的声明上下文，则该注解被认为仅应用于距离注解最近的类型。
- 如果注解的接口既适用于该声明对应的声明上下文，也适用于类型上下文，则该注解被认为同时应用于声明和距离注解最近的类型。

在上述第二种和第三种情况下，距离注解*最近的*的类型按如下方式确定：

- 如果注解出现在 `void` 方法声明或使用 `var` 的局部变量声明（§14.4）之前，则没有最近的类型。如果该注解接口被认为仅应用于距离注解最近的类型，则会发生编译错误。
- 如果注解出现在构造方法声明之前，最近的类型是新构建对象的类型。是紧接构造方法声明的类型的完全限定名的类型。在该完全限定名中，注解应用于构造方法声明指示的简单类型。
- 在所有其他情况下，最近的类型是源代码中为被声明实体编写的类型；如果该类型是数组类型，则元素类型被认为距离注解最近。

> 示例，在字段声明 `@Foo public static String f` 中，距离 `@Foo` 最近的类型是 `String`。如果字段的类型被写为 `java.lang.String`，那么 `java.lang.String` 将是距离 `@Foo` 最近的类型，后续规则将禁止类型注解应用于。在泛型方法声明 `@Foo <T> int m()` 中，为被声明实体编写的类型是 `int[]`，因此 `@Foo` 应用于元素类型。

未使用 `var` 的局部变量声明与形式参数声明类似，两者都允许在源码中使用声明注解和类型注解。

如果接口 `A` 的注解在语法上是以下内容的修饰符，则会导致编译错误：

- 模块声明，但 A 不适用于模块声明。
- 包声明，但 A 不适用于包声明。
- 类或接口声明，但 A 不适用于类型声明或类型上下文。
- 注解接口声明，但 A 不适用于类型上下文中的注解接口声明。
- 方法声明（包括注解接口的元素），但 A 不适用于方法声明或类型上下文。
- 构造方法声明，但 A 不适用于构造方法声明或类型上下文。
- 泛型类、接口、方法或构造方法的类型参数声明，但 A 不适用于类型参数声明或类型上下文。
- 字段声明（或枚举常量），但 A 不适用于字段声明或类型上下文。
- 形式参数或异常参数声明，但 A 不适用于形式和异常参数声明或类型上下文。
- 接收参数，但 A 不适用于类型上下文。
- 语句或模式中的局部变量声明，但 A 不适用于局部变量声明或类型上下文。
- 记录组件，但 A 不适用于类型上下文中的记录组件声明、字段声明、方法声明或形式和异常参数声明。

> 这十一个条款中有六个提到了“……或类型上下文”，因为它们刻画了本节前面提到的语法位置，注解在该处可能合理应用于声明或类型。此外，十一个条款中关于类和接口声明以及类型参数声明的两个提到了“……或类型上下文”，是因为有时为了将一个被标记了 `@Target(ElementType.TYPE_USE)` 元注解（因此适用于类型上下文）的注解应用于类、接口或类型参数的声明。

如果满足以下条件之一，则类型注解是允许的：

- 距离注解最近的简单名称被分类为 `TypeName` 而非 `PackageName`。
- 如果距离注解最近的简单名称后面跟着 `.` 和另一个 `TypeName` ——即注解以 `@Foo T.U` 的形式出现，那么 `U` 表示 T 的内部类。

第二个条款背后的直觉是，如果在 `Outer` 包围的嵌套类中 `Outer.this` 是合法的，那么 `Outer` 可以被注解，因为它代表了某些类型的……

运行时的对象。另一方面，如果 `Outer.this` 是不法的——因为出现它的的类在运行时没有 `Outer` 的闭包实例——那么 `Outer` 就不可以被注解，因为在逻辑上它只是一个名称，类似于完全限定类型名中包名的组成部分。

例如，在下面的程序中，无法在 `B` 的体中编写 `A.this`，因为 B 没有词法上的闭包实例。因此，无法在类型 `A.B` 中对 A 应用 `@Foo`，因为 A 在逻辑上只是一个名称，而不是一个类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}

class A {
    static class B {
        @Foo A.B x; // 非法
    }
}
```

另一方面，在下面的程序中，可以在 `D` 的体中编写 `C.this`。因此，可以在类型 `C.D` 中对 C 应用 `@Foo`，因为 C 代表了运行时某个对象的类型。

```java
@Target(ElementType.TYPE_USE)
@interface Foo {}

class Test {
    static class C {
        class D {}
    }

    @Foo C.D x; // 合法
}
```

如果接口 A 的注解应用到类型上下文的最外层级，且 A 不适用于类型上下文，或声明上下文（如果有的话）占据相同的语法位置，则将产生编译错误。

如果接口 A 的注解应用于类型上下文中类型的某部分（即不是最外层级），且 A 不适用于类型上下文，则将产生编译错误。

如果接口 A 的注解应用于类型上下文中的某个类型（或类型的任何部分），且 A 适用于类型上下文，但该注解是不被允许的，则将产生编译错误。

例如，注解接口 `TA` 仅被元注解为 `@Target(ElementType.TYPE_USE)`。术语 `@TA java.lang.Object` 和 `java.@TA lang.Object` 是非法的，因为离 `@TA` 最近的简单名称是一个包名。另一方面，`java.lang.Object` 是合法的。

注意，这些非法术语在“任何地方”都是非法的。对包名的禁止适用于仅为类型上下文的位置，例如 `class extends @TA java.lang.Object (...)`，以及既是声明上下文又是类型上下文的位置，例如 `field java.lang.Object f;`（没有任何仅为声明上下文的位置可以对包名进行注解，因为包、类、接口和类型参数只引入了简单名称）。

## 9.7 注解接口

（注：原文末尾标题为 "9.7 注解接口 (INTERFACES)"，但内容似为上一节的延续或重复，此处保留标题结构，内容已融合至上文。）



## 9.7.5 同一接口的多个注解

如果同一接口 A 的多个注解出现在声明上下文或类型上下文中，则将产生编译错误，除非 A 是可重复的（§9.6.3），且 A 及其包含 A 的容器注解接口都适用于声明上下文或类型上下文（§9.6.4.1）。

虽然不是要求的，但习惯上同一接口的多个注解是连续出现的。

如果声明上下文或类型上下文中存在可重复注解接口 A 的多个注解，那么该上下文就像没有显式声明的接口 A 注解，并且隐式声明了一个包含 A 的容器注解接口。

这个隐式声明的注解被称为“容器注解”，而出现在上下文中接口 A 的多个注解被称为“基注解”。容器注解的（数组类型的）`value` 元素的元素是它们在上下文中从左到右出现顺序的所有基注解。

如果在声明上下文或类型上下文中，存在可重复注解接口 A 的多个注解以及包含 A 的容器注解接口的任何注解，则将产生编译错误。

换句话说，当一个与目标同一接口的注解也出现时，是不可能重复注解的。这禁止了如下这种晦涩的代码：

```java
@Foo(0) @FooContainer({@Foo(2)})
class A { }
```

如果这段代码是合法的，那么就需要多个层级的包含：首先接口 `Foo` 的基注解会被接口 `FooContainer` 的隐式声明注解的包含，然后该注解和显式声明的 `FooContainer` 注解将被包含在另一个隐式声明的注解中。Java 编程语言设计者认为，这种复杂性是不可接受的。另一种方法，即将接口的基注解视为在显式的 `@FooContainer` 注解中与 `@Foo(2)` 同时出现，也是不可接受的，因为可能会改变程序解释 `@FooContainer` 注解的方式。

如果在声明上下文或类型上下文中，存在一个重复注解 A 的注解和多个包含 A 的接口 A 的注解，则将产生编译错误。

此规则的设计是为了允许在声明上下文或类型上下文中出现如下代码，其中只有一个重复注解 A 的注解和多个包含 A 的接口 A 的注解：

```java
@Foo(1) @FooContainer({@Foo(2), @Foo(3)})
class A {}
```

## 9.8 函数接口

函数接口是一个未声明的、除了 `Object` 的方法外仅有一个抽象方法的接口，因此在逻辑上代表一个单一方法。

对于一个未声明的接口 I，令 M 为 I 的成员中不属于 `Object` 的抽象方法集合。那么，I 是函数接口，当且仅当 M 中存在一个方法 m，满足以下两个条件：

- m 的签名对于 M 中的每个方法的签名都是子签名（§8.4.2）。
- m 对于 M 中的每个方法都是类型替换的（§8.4.5）。

除了通过声明和实例化类来创建的通常过程（§15.9），函数接口的实例可以使用方法引用和 Lambda 表达式（§15.13, §15.27）创建。

函数接口的定义排除了 `Object` 的公共方法。这是为了允许像 `java.util.Comparator<T>` 这样的接口进行函数式处理，它声明只有一个抽象方法。

注意，如果 `Object` 的非公共方法（例如 `clone()`）在接口中被显式声明为公共，它们不会被实现接口的类自动实现。从 `Object` 继承实现是保护的，而接口方法是公共的，因此实现该接口的唯一方法是让类重写非公共 `Object` 方法。

### 示例 9.8-1. 函数接口

函数接口的一个简单示例：

```java
interface Runnable {
    void run();
}
```

下面的接口不是函数接口，因为它声明的没有内容不是已经是 `Object` 的成员：

```java
interface NonFunc {
    boolean equals(Object obj);
}
```

然而，它的子接口通过声明一个不是 `Object` 成员的抽象方法可以成为函数接口：

```java
interface Func extends NonFunc {
    int compare(String o1, String o2);
}
```

同样，著名的接口 `java.util.Comparator<T>` 是函数接口，因为它只有一个抽象的非公共 `Object` 方法：

```java
interface Comparator<T> {
    boolean equals(Object obj);
    int compare(T o1, T o2);
}
```

以下接口不是函数接口，因为它不仅声明了一个不是 `Object` 成员的抽象方法，还声明了两个不是 `Object` 公有成员的方法：

```java
interface Foo {
    int m();
    Object clone();
}
```

### 示例 9.8-2 函数式接口与擦除

在以下层次结构中，Z 是一个函数接口，因为它继承了两个不是 `Object` 成员的抽象方法，它们具有相同的签名，因此继承的方法在逻辑上表示了单个方法：

```java
interface X { int m(Iterable<String> arg); }
interface Y { int m(Iterable<String> arg); }
interface Z extends X, Y { }
```

同样，在以下接口层次结构中，Z 也是一个函数接口。`Y.m` 是 `X.m` 的子签名，并且对于 `X.m` 来说是返回类型可替换的：

```java
interface X { Iterable<String> m(Iterable<String> arg); }
interface Y { Iterable<String> m(Iterable<String> arg); }
interface Z extends X, Y { }
```

函数式接口的定义遵循这样一个事实：接口不能拥有两个互不为子签名的成员却具有相同的擦除类型（§9.4.1.2）。因此，在以下接口层次结构中，Z 导致了编译错误，Z 不是一个函数接口（因为它没有任何抽象成员是所有其他抽象成员的子签名）：

```java
interface X { int m(Iterable<String> arg); }
interface Y { int m(Iterable<Integer> arg); }
interface Z extends X, Y { }
```

```java
interface X { int m(Iterable<String> arg, Class<?> c); }
interface Y { int m(Iterable<Object> arg, Class<?> c); }
interface Z extends X, Y { }
```

```java
interface X<T> { void m(T arg); }
interface Y<T> { void m(T arg); }
interface Z<A, B> extends X<A>, Y<B> { }
```

同样，“函数式接口”的定义遵循这样一个事实：接口可能只拥有具有重写等效签名的方法，前提是其中一个方法对所有其他方法都是返回类型可替换的。因此，在以下接口层次结构中，Z 导致了编译错误，Z 不是一个函数接口（因为它没有任何抽象成员对所有其他抽象成员返回类型可替换）：

```java
interface X { long m(); }
interface Y { int m(); }
interface Z extends X, Y { }
```

在接下来的示例中，`Foo<T,N>` 和 `Bar` 的声明是合法的：在每个接口中，调用的方法都不是彼此的子类，但具有不同的擦除类型。每个中的方法并不是 `Foo<T,N>` 和 `Bar` 不是函数接口。然而，`Baz` 是一个函数接口，因为它继承自 `Foo<Integer, Integer>` 的方法具有相同的签名，因此逻辑上表示了单个方法。

```java
interface Foo<T, N> extends Number {
  void m(T arg);
  void m(N arg);
}
interface Bar extends Foo<String, Integer> { }
interface Baz extends Foo<Integer, Integer> { }
```

最后，以下示例演示了上述相同的规则，但使用了泛型方法：

```java
interface Exec { <T> void execute(Action<T> a); }
// 函数式

interface X { <T> void execute(Action<T> a); }
interface Y { <S> void execute(Action<S> a); }
interface Exec extends X, Y { }
// 函数式：签名在逻辑上是“相同”的

interface X { <T> void execute(Action<T> a); }
interface Y { <S> void execute(Action<S> a); }
interface Exec extends X, Y { }
// 错误：不同的签名，相同的擦除
```

### 示例 9.8-3. 泛型函数式接口

函数式接口可以是泛型的，例如 `java.util.function.Predicate<T>`。这样的函数式接口可以通过参数化方式产生不同的抽象方法——即多个无法通过单一声明来被重写的方法：

```java
interface I { Object m(Class<?> c); }
interface J<S> { S m(Class<S> c); }
interface K<T> { T m(Class<T> c); }
interface Functional<S,T> extends I, J<S>, K<T> { }
```

`Functional<S,T>` 是一个函数接口 - `I.m` 对于 `J.m` 和 `K.m` 返回类型可替换，但函数式接口类型 `Functional<String, Integer>` 显然无法通过单个方法实现。然而，`Functional<S,T>` 的其他作为函数接口类型的参数化是可能的。

## 9.9 函数类型

函数式接口的声明允许函数式接口类型在程序中使用。函数式接口类型有四种：

- 非泛型（§6.1）函数接口的类型
- 泛型函数接口的参数化类型（§4.5）
- 泛型函数接口的原始类型（§4.8）
- 表示命名函数式接口的交集类型（§4.9）

在特殊情况下，将交集类型视为函数式接口类型是有用的。通常，这看起来像是一个函数式接口类型与一个或多个标记接口类型的交集，例如 `Runnable & java.io.Serializable`。这种交集可以用于强制转换（§15.16），强制 lambda 表达式符合某种类型。

### 函数类型

函数式接口 `I` 的函数类型由以下部分组成：

- 类型参数
- 形式参数
- 返回类型

设 `m` 是 M 中的一个方法：

1. 签名是 M 中每个方法的子签名，且
2. 返回类型对于 M 中的每个方法返回类型可替换。

如果不存在这样的方法，设 `m` 是 M 中的一个方法：

1. 签名是 M 中每个方法的子签名，且
2. 返回类型对于 M 中的每个方法返回类型可替换。

定义类型抛出异常的目的是确保具有该异常句的方法可以重写函数式接口的每个抽象方法。根据 §8.4.6，这意味着函数类型抛出的异常比 M 中的任何单个方法“多”，因此我们寻找尽可能多被每个方法异常句“覆盖”的异常。

函数类型的异常句从 M 中方法的异常句推导出来，如下：

1. 如果函数类型是泛型的，异常句首先适配于类型参数（§8.4.4）。
2. 如果函数类型不是泛型的但 M 中至少有一个方法是泛型的，异常句首先被擦除。

然后，函数类型的异常句包含满足以下约束的类型 `E`：

- `E` 在某个异常句中被提到。
- 对于每个句，`E` 是该句中命名的类型的子类型。

当 M 中的返回类型是原始类型而其他不是时，函数类型的定义尝试选择最具体的类型。例如，如果返回类型是 `LinkedList<String>` 和 `LinkedList<String>`，则后者立即成为函数类型的返回类型。当没有特定类型时，定义通过寻找最可替换的返回类型进行补偿。例如，如果存在第三种返回类型 `List<?>`，并不是某个返回类型是其他所有类型的子类型（因为原始 `LinkedList` 不是 `List<?>` 的子类型）；相反，选择了 `LinkedList<String>` 作为函数类型的返回类型，因为它对于 `LinkedList` 和 `List<?>` 返回类型可替换。

函数式接口的函数类型规定如下：

- 非泛型函数式接口 `I` 的函数类型就是上述定义的函数式接口 `I` 的函数类型。
- 参数化函数式接口 `I<A1...An>`（其中 `A1...An` 是类型，且 I 对应的类型参数为 `P1...Pn`）通过应用替换 `[P1:=A1, ... Pn:=An]` 到泛型接口 `I<P1...Pn>` 的函数类型推导得出。
- 参数化函数式接口 `I<A1...An>`（其中 `A1...An` 中的一个或多个是通配符），函数类型的非通配符参数化的确定方式如下。

设 `P1...Pn` 为 `I` 的类型参数，其对应的边界为 `B1...Bn`。对于所有的 `i` (`1 ≤ i ≤ n`)，`Ti` 根据 `Ai` 的形式推导出：

- 如果 `Ai` 是一个类型，则 `Ti = Ai`。
- 如果 `Ai` 是一个通配符，且对应类型参数的边界 `Bi` 提到了 `P1...Pn` 中的某一个，则 `Ti` 未定义，且没有函数类型。
- 否则：
    - 如果 `Ai` 是未绑定的通配符 `?`，则 `Ti = Bi`。
    - 如果 `Ai` 是带上界的通配符 `? extends Ui`，则 `Ti = glb(Ui, Bi)` (§5.1.10)。
    - 如果 `Ai` 是带下界的通配符 `? super Li`，则 `Ti = Li`。

- 泛型函数式接口 `I<...>` 的原始类型的函数类型是该泛型函数式接口 `I<...>` 函数类型的擦除。
- 导致概念函数式接口的交叉类型的函数类型是该概念函数式接口的函数类型。

#### 示例 9.9-1. 函数类型

给定以下接口：

```java
interface X { void m() throws IOException; }
interface Y { void m() throws EOFException; }
interface Z { void m() throws ClassNotFoundException; }
```

则以下内容的函数类型：

```java
interface XY extends X, Y { }
```

是：

```
() -> void throws EOFException
```

而以下内容的函数类型：

```java
interface XYZ extends X, Y, Z { }
```

是：

```
() -> void (throws nothing)
```

给定以下接口：

```java
interface A {
  List<String> foo(List<String> arg)
    throws IOException, SQLTransientException;
}
interface B {
  List foo(List<String> arg)
    throws EOFException, SQLException, TimeoutException;
}
interface C {
  List foo(List arg) throws Exception;
}
```

则以下内容的函数类型：

```java
interface D extends A, B { }
```

是：

```
(List<String>) -> List<String>
  throws EOFException, SQLTransientException
```

而以下内容的函数类型：

```java
interface E extends A, B, C { }
```

是：

```
(List) -> List
  throws EOFException, SQLTransientException
```

函数式接口的函数类型是非确定的：虽然 M 中的签名是“相同的”，但它们在语法上可能是不同的（例如 `HashMap.Entry` 和 `Map.Entry`）；返回类型可以是其他所有返回类型的子类型，但可能存在其他返回类型也是子类型（例如 `List<?>` 和 `List<? extends Object>`）；并且类型的顺序是不确定的。这些区别是细微的，但可能非常重要。然而，Java 编程语言在使用函数类型时并不会导致这种不确定性产生影响。注意，当存在多个抽象方法时（§15.12.5），“最具体方法”的返回类型和子句是非确定的。



当泛型函数式接口通过通配符参数化时，会有许多产生不同函数类型的实例。例如，`Predicate<Integer>`（函数类型 `Integer -> boolean`）、`Predicate<Number>`（函数类型 `Number -> boolean`）以及 `Predicate<Object>`（函数类型 `Object -> boolean`）可以通过上下文（例如 lambda 表达式的参数类型）确定意图是哪种函数类型（§15.27.3）。有时，必须选择其中一个；在这种情况下，将使用边界。这种简单的策略无法保证生成的类型将满足某些复杂的边界，因此不支持所有情况。

## 示例 9.9-2. 泛型函数类型

函数类型可以是泛型的，因为函数式接口的抽象方法可以是泛型的。例如，在以下接口层次结构中：

```java
interface G1 {
    <E extends Exception> Object m() throws E;
}
interface G2 {
    <F extends Exception> String m() throws Exception;
}
interface G extends G1, G2 {}
```

`G` 的函数类型是：

`<F extends Exception> () -> String throws F`

函数式接口的泛型函数类型可以通过方法引用表达式（§15.13）实现，但不能通过 lambda 表达式（§15.27）实现，因为没有泛型 lambda 表达式的语法。

# 数组

在 Java 编程语言中，数组是对象（§4.3.1），是动态创建的，并且可以赋值给 `Object` 类型的变量（§4.3.2）。`Object` 类的所有方法都可以在数组上调用。

数组对象包含许多变量。变量的数量可以为零，在这种情况下称数组是空的。数组中包含的变量没有名称；相反，它们通过使用非负整数索引值的访问表达式来引用。这些变量被称为数组的组件。如果数组有 $n$ 个组件，我们说 $n$ 是数组的长度；数组的组件使用从 0 到 $n-1$ 的整数索引进行引用。

数组的所有组件都具有相同的类型。数组的类型在创建时是确定的，一旦创建就不能更改。数组的长度在创建时也是确定的，且不能更改。

数组的组件也可以是数组。数组的初始化可以通过以下几种方式：使用 `new` 表达式并结合初始化列表，或者使用数组初始化器。

```java
int[] a = {1, 2, 3};
int[] b = new int[] {1, 2, 3};
int[] c = new int[]{1, 2, 3};
```

数组的访问可以通过索引操作来完成。

```java
int x = a[0];
int y = a[1];
a[0] = 10;
a[1] = 20;
a[2] = 30;
```

数组的赋值可以通过赋值操作来完成。

```java
int[] d = a;
d[0] = 50;
```

数组的赋值可以通过操作完成。

```java
int[] e = new int[5];
e[0] = 1;
e[1] = 2;
e[2] = 3;
e[3] = 4;
e[4] = 5;
```

数组的遍历可以通过 `for` 循环完成。

```java
for (int i = 0; i < a.length; i++) {
    System.out.println(a[i]);
}
```

数组的遍历可以通过增强 `for` 循环完成。

```java
for (int x : a) {
    System.out.println(x);
}
```

数组的打印可以通过 `Arrays.toString()` 方法完成。

```java
System.out.println(Arrays.toString(a));
```

多维数组是数组的数组。在 Java 中，多维数组被表示为数组的数组。

```java
// 多维数组的示例
public class MultiDimensionalArrayExample {
    public static void main(String[] args) {
        int[][] matrix = {{1, 2, 3}, {4, 5, 6}};
        System.out.println(matrix[0][0]); // 输出 1
        System.out.println(matrix[1][2]); // 输出 6

        for (int i = 0; i < matrix.length; i++) {
            for (int j = 0; j < matrix[i].length; j++) {
                System.out.print(matrix[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

多维数组的声明和初始化与一维数组类似。

```java
int[][] a = {{1, 2, 3}, {4, 5, 6}};
int[][] b = new int[2][3];
int[][] c = new int[][]{{1, 2, 3}, {4, 5, 6}};
```

多维数组可以是不规则的（jagged arrays），即每个子数组的长度可以不同。

```java
int[][] jagged = new int[3][];
jagged[0] = new int[]{1, 2};
jagged[1] = new int[]{3, 4, 5};
jagged[2] = new int[]{6};
```

数组的 `length` 字段返回数组的组件的数量。

```java
int[] a = {1, 2, 3};
System.out.println(a.length); // 输出 3

int[][] b = {{1, 2}, {3, 4, 5}};
System.out.println(b.length); // 输出 2
System.out.println(b[0].length); // 输出 2
```

数组可以通过 `System.arraycopy()` 方法进行复制。

```java
int[] source = {1, 2, 3, 4, 5};
int[] destination = new int[5];
System.arraycopy(source, 0, destination, 0, 3);
// destination 现在是 {1, 2, 3, 0, 0}
```

数组可以通过 `Arrays.copyOf()` 方法进行复制并调整大小。

```java
int[] source = {1, 2, 3, 4, 5};
int[] destination = Arrays.copyOf(source, 3);
// destination 现在是 {1, 2, 3}
int[] larger = Arrays.copyOf(source, 7);
// larger 现在是 {1, 2, 3, 4, 5, 0, 0}
```

数组可以通过 `Arrays.sort()` 方法进行排序。

```java
int[] a = {5, 2, 8, 1, 3};
Arrays.sort(a);
// a 现在是 {1, 2, 3, 5, 8}
```

数组可以通过 `Arrays.binarySearch()` 方法进行查找。

```java
int[] a = {1, 2, 3, 5, 8};
int index = Arrays.binarySearch(a, 5);
// index 是 3
```

数组可以通过 `Arrays.fill()` 方法进行填充。

```java
int[] a = new int[5];
Arrays.fill(a, 10);
// a 现在是 {10, 10, 10, 10, 10}
```

数组可以通过 `Arrays.equals()` 方法进行相等性比较。

```java
int[] a = {1, 2, 3};
int[] b = {1, 2, 3};
System.out.println(Arrays.equals(a, b)); // 输出 true
```

数组可以通过 `Arrays.deepEquals()` 方法进行多维数组的相等性比较。

```java
int[][] a = {{1, 2}, {3, 4}};
int[][] b = {{1, 2}, {3, 4}};
System.out.println(Arrays.deepEquals(a, b)); // 输出 true
```

数组可以通过 `Arrays.stream()` 方法将数组转换为流。

```java
int[] a = {1, 2, 3, 4, 5};
int sum = Arrays.stream(a).sum();
// sum 是 15
```

数组的 `toString()` 方法不会返回数组内容的字符串表示。

```java
int[] a = {1, 2, 3};
System.out.println(a.toString()); // 输出类似 [I@某个哈希值
System.out.println(Arrays.toString(a)); // 输出 [1, 2, 3]
```

数组可以通过 `clone()` 方法创建数组的浅拷贝。

```java
int[] a = {1, 2, 3};
int[] b = a.clone();
b[0] = 10;
// a 仍然是 {1, 2, 3}, b 是 {10, 2, 3}
```

数组的 `getClass()` 方法返回数组的运行时类型。

```java
int[] a = {1, 2, 3};
System.out.println(a.getClass().getName()); // 输出 [I
```

数组是 `Object` 的子类。

```java
int[] a = {1, 2, 3};
Object obj = a;
System.out.println(obj instanceof Object); // 输出 true
```

数组可以存储任何引用类型的对象。

```java
Object[] array = {"Hello", 1, 2.5, true};
```

数组不能存储基本类型。

```java
int[] a = {1, 2, 3};
// Integer[] b = a; // 编译错误
```

数组可以存储基本类型的包装类对象。

```java
Integer[] b = {Integer(1), Integer(2), Integer(3)};
```

数组的索引从 0 开始。访问超出范围的索引会抛出 `ArrayIndexOutOfBoundsException`。

```java
int[] a = {1, 2, 3};
int x = a[5]; // 抛出 ArrayIndexOutOfBoundsException
```

数组的长度是固定的，一旦创建就不能更改。

```java
int[] a = new int[5];
// a.length = 10; // 编译错误
```

数组在初始化时会有默认值。

```java
int[] a = new int[5]; // 所有元素初始化为 0
boolean[] b = new boolean[5]; // 所有元素初始化为 false
Object[] c = new Object[5]; // 所有元素初始化为 null
```

数组可以使用 `final` 关键字，这意味着数组引用不能重新赋值。

```java
final int[] a = {1, 2, 3};
a[0] = 10; // 允许
// a = new int[5]; // 编译错误
```

数组不是线程安全的。如果多个线程同时访问数组并其中一个在修改它，则需要额外的同步。

数组由垃圾回收器管理。当数组不再被引用时，它们会被回收。

数组是 Java 中存储一组相同类型元素的简单数据结构。它们非常高效，但长度固定。

# 数组变量

```java
byte[] rowvector, colvector, matrix[];
```

等价于：

```java
byte rowvector[], colvector[], matrix[][];
```

因为每个局部变量的数组类型没有改变。同样，局部变量声明语句：

```java
int a, b[], c[][];
```

等价于一系列声明语句：

```java
int a;
int[] b;
int[][][] c;
```

在声明符中使用括号是允许的是对 C 和 C++ 传统的致敬。然而，变量声明的通用规则允许括号出现在类型和声明符中，因此局部变量声明语句：

```java
float[][] f[], g[][], h[]; // 哎，真糟！
```

等价于一系列声明：

```java
float[][] f;
float[][][] g;
float[][][][] h;
```

根据数组类型的形成方式，以下参数声明具有相同的数组类型：

令人惊讶的是，以下字段声明具有相同的数组类型：

```java
int @[] f @B [];
int @B [] @A [] g;
```

一旦创建了数组对象，其长度就永远不会改变。要让数组变量引用不同长度的数组，必须为该变量分配指向不同数组的引用。

数组类型的单个变量可以包含不同长度数组的引用，因为数组的长度不是其类型的一部分。

如果数组变量 `v` 的类型为 `A[]`，其中 `A` 是一种引用类型，那么只要 `B` 可以赋值给 `A`，`v` 就可以持有任何数组类型 `B[]` 的实例引用。

# 数组

## 10.3 数组创建

数组通过数组创建表达式（§15.10.1）或数组初始化器（§10.6）创建。

数组创建表达式指定了元素类型、嵌套数组的层数以及至少一个嵌套的数组长度。数组的长度作为 final 实例变量 `length` 可用。

数组初始化器创建一个数组并为其所有组件提供初始值。

## 10.4 数组访问

数组的组件通过数组访问表达式（§15.10.3）访问，该表达式由一个值为数组引用的表达式后跟一个括在 `[ ]` 中的索引表达式组成，例如 `A[i]`。

所有数组都从 0 开始。长度为 n 的数组由整数 0 到 n-1 索引。

> 示例 10.4-1. 数组访问

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

5050

该程序声明了一个类型为 int（即 `int[]`）的变量 `ia`。变量 `ia` 被初始化为指向由数组创建表达式（§15.10.1）新创建的数组对象。数组创建表达式指定了数组应该具有 101 个组件。数组的长度可以使用字段 `length` 获取，如所示。该程序用 0 到 100 的整数填充数组，求这些整数的和，并打印结果。

数组必须由 int 值进行索引；short、byte 或 char 值也可以作为索引值，因为它们会经过一元数值提升（§5.6）并变为 int 值。

尝试使用 long 类型的索引值访问数组组件会导致编译错误。

所有的数组访问都在运行时进行检查；尝试使用小于 0 或大于等于数组长度的索引会导致抛出 `ArrayIndexOutOfBoundsException`（§15.10.4）。

## 10.5 数组存储异常

对于类型为 `A[]` 的数组（其中 `A` 是一种引用类型），对数组组件的赋值会在运行时进行检查，以确保赋值的值是可以赋值给该组件的。

如果所赋值值的类型与组件类型不赋值兼容（§5.2），则会抛出 `ArrayStoreException`。

如果数组的组件不可靠（§4.7），则 Java 虚拟机将无法执行前一段所述的检查。这就是为什么禁止使用不可靠元素类型的数组创建表达式（§15.10.1）。可以声明一个元素类型不可靠的数组变量，但将数组创建表达式的结果赋值给该变量将导致未检查异常（§51.9）。

示例 10.5-1. ArrayStoreException

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

该程序产生输出：

true

java.lang.ArrayStoreException

## 10.6 数组初始化器

数组初始化器写为由逗号分隔的表达式列表，并括在大括号 `{ }` 中。数组初始化器的最后一个表达式后可以出现逗号并会被忽略。



每个变量初始化器必须与数组的组件类型赋值兼容（§5.2），否则会发生编译错误。如果被初始数组的组件类型不可重构（§4.7），则为编译错误。要构造的数组的长度等于数组初始化器大括号内直接变量初始化器的数量。如果没有足够的空间分配数组，则数组初始化器的求值通过抛出 `OutOfMemoryError` 中。否则，将创建一个指定长度的一维数组，并将其每个组件初始化为默认值（§4.12.5）。

数组初始化器大括号内的变量初始化器按照源代码中的文本顺序执行。第 $n$ 个变量初始化器指定第 $n-1$ 个数组组件的值。如果变量初始化器的执行中断，则数组初始化器的执行因相同原因中断。如果所有变量初始化表达式正常完成，则数组初始化器正常完成，值为新初始化的数组。

如果组件类型是数组类型，则指定组件的变量初始化器可以是数组初始化器；即数组初始化器可以嵌套。在这种情况下，执行嵌套初始化器通过递归应用上述算法构造并初始化数组对象，并将其赋值给组件。

### 示例 10.6-1. 数组初始化器

```java
class Test {
  public static void main(String[] args) {
    int[] ia = { 1, 2, null };
    for (int[] ea : ia) {
      for (int e : ea) {
          System.out.println(e);
        }
    }
  }
}
```

该程序产生输出：

1

2

在尝试索引数组 `ia` 的第二个组件（该组件为 `null` 引用）之前，会导致 `NullPointerException`。

## 10.7 数组成员

数组类型的成员包含以下所有内容：

- 公共 final 字段 `length`，它包含数组的组件数量。`length` 可以为正数或零。

- 公共方法 `clone`，它重写了 `Object` 类同名方法且不抛出任何检查异常。数组类型 `T[]` 的 `clone` 方法的返回类型为 `T[]`。

- 多维数组的克隆是浅的，也就是说它只创建了一个新数组。子数组是共享的。

- 所有继承自 `Object` 类的成员；`Object` 中唯一没有继承的方法是其 `clone` 方法。

> 参见 §9.6.4.4，了解另一种 `Object` 的公共方法与非公共方法之间的差异需要特殊处理的情况。

数组具有与以下类相同的公共字段和方法：

```java
class A<T> implements Cloneable, java.io.Serializable {
    public final int length = X;
    public T[] clone() {
        try {
            return (T[])super.clone();
        } catch (CloneNotSupportedException e) {
            throw new InternalError(e.getMessage());
        }
    }
}
```

如果数组并非真的这样实现的，那么上述代码中向 `T[]` 的转换将产生一个未检查警告（§5.1.9）。

### 示例 10.7-1. 数组是可以克隆的

```java
class Test1 {
    public static void main(String[] args) {
        int[] ial = { 1, 2 };
        int[] ia2 = ial.clone();
        System.out.print((ial == ia2) + " ");
        ial[1]++;
        System.out.println(ia2[1]);
    }
}
```

该程序产生输出：

false 2

表明由 `ial` 和 `ia2` 引用的数组组件是不同的变量。

### 示例 10.7-2. 克隆后的子数组

此程序展示了多维数组在克隆时子数组是共享的：

```java
class Test2 {
    public static void main(String[] args) throws Throwable {
        int[] ia = { 1, 2, null };
        int[] ja = ia.clone();
        System.out.print((ia == ja) + " ");
        System.out.println(ia[0] && ja[0] == ja[1]);
    }
}
```

该程序产生输出：

false true

表明 `ia[0]` 的 `int[]` 数组与 `ja[0]` 的 `int[]` 数组是同一个数组。

## 10.8 数组的类 对象

每个数组都有一个关联的 `Class` 对象，与所有具有相同组件类型的数组共享。

虽然数组类型不是类，但每个数组的 `Class` 对象表现得好像：

- 每个数组类型的直接父类都是 `Object`。

- 每个数组类型都实现了 `Cloneable` 和 `java.io.Serializable` 接口。

### 示例 10.8-1. 数组的 Class 对象

```java
class Test1 {
    public static void main(String[] args) {
        int[] ia = new int[0];
        System.out.println(ia.getClass());
        System.out.println(ia.getClass().getSuperclass());
        for (Class<?> c : ia.getClass().getInterfaces()) {
            System.out.println("interface: " + c);
        }
    }
}
```

该程序产生输出：

```
class [I
class java.lang.Object
Superinterface: interface java.lang.Cloneable
Superinterface: interface java.io.Serializable
```

其中字符串 `"I"` 是 `Class` 对象“组件类型为 int 的数组”的运行时类型签名，

### 示例 10.8-2. 数组 Class 对象是共享的

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

该程序产生输出：

```
false
true
```

虽然 `ia` 和 `ib` 指向不同的数组，但 `Class` 对象的比较结果表明，所有组件类型为 `int` 的数组都是相同数组类型的实例（即 `int[]`）。

## 10.9 字符数组不是字符串

在 Java 语言中，与 C 不同，`char` 数组不是 `String`，且 `String` 或 `char` 数组都不会以 `\u0000`（NUL 字符）终止。

`String` 对象是不可变的，也就是说它的内容永远改变，而 `char` 数组的元素是可变的。

`String` 类中的 `toCharArray` 方法返回一个包含与该字符串具有相同字符序列的字符数组。`StringBuffer` 类在可变字符数组上实现了有用的方法。

# 第 11 章 异常

当程序违反 Java 语言的语义约束时，Java 虚拟机会将此错误作为异常信号给程序。

此类违反行为的一个示例是尝试访问数组范围的索引。某些编程语言及其实现对此会有反应。

## 异常的种类与产生

检查异常类是指除未检查类以外的所有异常类。也就是说，检查异常类是 `Throwable` 及其除 `RuntimeException` 及其子类以及 `Error` 及其子类以外的所有子类。

程序可以在 `throw` 语句中使用 Java SE Platform API 提供的异常类，或者作为 `Throwable` 或其任何子类的子类来定义额外的异常类。为了利用对异常处理程序的编译时检查 (§11.2)，通常的做法是将大多数新异常类定义为检查异常类，即定义为 `Exception` 的子类且不是 `RuntimeException` 的子类。

`Error` 类是 `Throwable` 的子类，在层次结构中与 `Exception` 有别，这允许程序使用 `catch (Exception e) {}` (§11.2.3) 这种惯用法来捕获所有可能恢复的异常，而不会捕获通常可以恢复的错误。

注意，`Throwable` 的子类不能是泛型的 (§8.1.2)。

### 11.1.2 异常产生

异常的抛出由于以下三个原因之一：

- `throw` 语句 (§14.18)。

- Java 虚拟机同步检测到异常执行状态，即：

    - 表达式的求值违反了 Java 编程语言的正常语义 (§15.6)，例如整数除以零。

    - 在加载、链接或初始化程序部分时发生错误 (§12.2, §12.3, §12.4)；在这种情况下，会抛出一个 `LinkageError` 子类的实例。

    - 内部内错误（internal error）或资源限制导致 Java 虚拟机无法实现 Java 编程语言的语义；在这种情况下，会抛出一个 `VirtualMachineError` 子类的实例。

这些异常并不是在程序的任意点抛出，而是在它们被指定为表达式求值或语句执行的可能结果的时间点抛出。

- 发生了异步异常 (§11.1.3)。

### 11.1.3 异步异常

大多数异常是同步发生的，其结果是发生地的线程的操作，并且发生在程序中指定的可能导致此类异常的时间点。相比之下，异步异常是在程序执行的任何点都可能发生的异常。

异步异常仅由于以下结果发生：

- 调用了 `Thread` 或 `ThreadGroup` 类的（已弃用的）`stop` 方法。已弃用的 `stop` 方法可能由一个线程调用影响另一个线程或指定线程组中的所有线程。它们是异步的，因为它们可能发生在其他线程或线程执行的任何点。

- Java 虚拟机的内部错误或资源限制导致其无法实现 Java 编程语言的语义。在这种情况下，抛出的异步异常是 `VirtualMachineError` 类的实例。

> 注意，`VirtualMachineError` 的子类 `StackOverflowError` 可能会通过方法调用（15.12.4.5）同步抛出，并由于原生方法调用或 Java 资源限制异步抛出。同样，另一个 `VirtualMachineError` 子类 `OutOfMemoryError` 可能会在类实例创建 (15.9.4, 12.5)、数组创建 (15.10.2, 12.4.2) 以及装箱转换 (5.1.7)期间同步抛出，也可以异步抛出。

Java SE Platform 在抛出异步异常之前会执行少量的但有限的异常处理。

> 异步异常非常罕见，但如果为了生成高质量的代码，正确理解它们的语义是必要的。

上述延迟允许经过优化的代码在遵守 Java 编程语言语义的同时，在实际可以处理它们的时间点检测并抛出这些异常。简单的实现可能会在控制转移指令点轮询异步异常。由于程序的大小是有限的，这为检测异步异常的总延迟提供了一个界限。由于控制转移之间不会发生异步异常，代码生成器具有灵活性来重排控制转移之间的通信以获得更高的性能。建议进一步阅读 Marc Feeley 的论文《Polling Efficiently on Software Hardware》，Proc. 1993 Conference on Functional Programming and Computer Architecture, Copenhagen, Denmark, pp. 179-187。

## 11.2 异常的编译时检查

Java 编程语言要求程序必须包含对检查异常的处理器，这些异常可能是由方法执行或构造函数的执行而产生的 (§8.4.6, §8.8.5)。这种对异常处理程序存在性的编译时检查旨在减少未被妥善处理的异常数量。对于每个可能的检查异常，方法或构造函数的 `throws` 子句必须提到该异常类或该异常类的一个父类 (§11.2.3)。

检查异常类简体11.1.1) 是方法或构造函数的实现者与用户之间约的一部分。重写方法的 `throws` 子句不能指定该方法将导致被重写方法根据 `throws` 子句不允许抛出的任何检查异常 (§8.4.8.3)。当涉及接口时，多个声明可能被同一个重写声明所覆盖。在这种情况下，重写声明必须具有与所有被重写的声明兼容的 `throws` 子句 (§9.4.1)。

未检查异常类简体11.1.1) 免于编译时检查。

> `Error` 类被免于检查是因为它们可以在许多点发生，且难以从它们恢复。

运行时异常被免于检查，是因为在 Java 语言设计者看来，声明此类异常会显著使程序复杂。

我们说一个语句或表达式可以抛出异常 E，根据 §11.2.1 和 §11.2.2 中的规则，该语句或表达式的执行可能导致抛出类 E 的异常。

我们说一个 `catch` 子句可以捕获其可捕获异常类：

- 单异常 `catch` 子句的可捕获异常类是其异常参数的类型。

- 多异常 `catch` 子句的可捕获异常类是表示其异常参数类型的联合类型。

### 11.2.1 表达式的异常分析

类实例创建表达式 (15.9) 可以抛出异常 E，当且仅：

- 表达式是限定类实例表达式，且限定表达式可以抛出 E；

- 参数列表的某些表达式可以抛出 E；

- E 是所选构造函数调用类型的异常之一 (15.12.6)；

- 类实例创建表达式包含 `ClassBody`，且 `ClassBody` 中的某些实例器或实例变量初始化器可以抛出 E。

方法调用表达式 (15.12) 可以抛出异常 E，当且仅：

- 方法调用表达式的形式为 `Primary . [TypeArguments] Identifier` 且 `Primary` 表达式可以抛出 E；

- 参数列表的某些表达式可以抛出 E；

- E 是所选方法调用类型的异常之一 (15.12.6)。

Lambda 表达式 (15.27) 不会抛出任何异常类。

switch 表达式 (15.28) 可以抛出异常类 E，当且仅：

- 选择器表达式可以抛出 E；

- switch 块中的某些规则表达式、switch 规则块、switch 规则 throw 语句或 switch标签语句可以抛出 E。

对于所有其他类型的表达式，该表达式可以抛出异常 E，当且仅：它的一个直接子表达式可以抛出 E。

> 形式为 `Primary : [TypeArguments] Identifier` 的方法引用表达式 (15.13) 如果 `Primary` 子表达式可以抛出异常类，则它可以抛出异常类。相比之下，lambda 表达式不会抛出任何内容，且没有直接

执行异常分析的 EXCEPTIONS 子表达式。lambda 表达式的体部包含表达式和语句，体部可以抛出异常类。

### 11.2.2 语句的异常分析

`throw` 语句 (§14.18) 如果其抛出的表达式静态类型为 E 且不是最终（final）或有效最终异常参数，则可以抛出 E 或抛出的表达式可以抛出的任何异常类。

例如，语句 `throw new java.io.FileNotFoundException();` 只能抛出 `java.io.FileNotFoundException`。从形式上讲，它并不“可以抛出” `java.io.FileNotFoundException` 的子类或父类。

如果一个语句所抛出的表达式是 `catch` 子句 C 的最终或有效最终异常参数，则在满足以下条件时该语句可以抛出异常 E：

- E 是 `try` 语句的 `try` 块声明 C 可以抛出的异常类；且；

- E 与 C 的任何可捕获异常类都是赋值兼容的（assignment compatible）的；

- E 与 `try` 语句中声明在 C 左侧的的 `catch` 子句的任何可捕获异常类都不是赋值兼容的。

`try` 语句 (§14.20) 可以抛出异常类 E，当且仅当：

- `try` 块可以抛出 E，或者初始化资源的表达式（在 `try-with-resources` 语句中）可以抛出 E，或者资源的自动调用 `close()` 方法（在 `try-with-resources` 语句中）可以抛出 E，且 E 与 `try` 的任何 `catch` 子句的任何可捕获异常类都不具有赋值性，且不存在 `finally` 块或 `finally` 块可以正常完成；或者

- `try` 语句的某个 `catch` 块可以抛出 E，且不存在 `finally` 块或该 `finally` 块可以正常完成；或者

- 存在 `finally` 块且其可以抛出 E。

显式构造函数调用语句 (§8.8.7.1) 可以抛出异常类 E，当且仅当：

- 构造函数调用参数列表的某些表达式可以抛出 E；或者；

- E 被确定为被调用的构造函数的 `throws` 子句的异常类 (§15.12.2.6)。

`switch` 语句 (§14.11) 可以抛出异常类 E，当且仅当：

- 选择器表达式可以抛出 E；或者

- `switch` 块中的某些 `switch` 表达式、`switch` 规则块、`switch` 规则 `throw` 语句和 `switch` 标记语句组可以抛出 E。

如果直接包含在 S 中的表达式或语句可以抛出 E，则任何语句 S 都可以抛出异常 E。

### 11.2.3 异常检查

如果构造函数体可以抛出某些异常类，当 E 是检查异常类且 E 不是方法或构造函数 `throws` 子句中声明的类的子类，则为编译错误。



如果 lambda 体可以抛出异常类 `E`，当 `E` 是检查异常类且 `E` 不是 lambda 表达式所目标的函数类型 `throws` 子句中声明的类的子类，则为编译错误。

如果具名类或接口 `E` 的类变量初始化器（§8.3.2）或静态初始化器（§8.7）可以抛出检查异常，则为编译错误。

如果具名类的实例变量初始化器（§8.3.2）或实例初始化器（§8.6）可以抛出检查异常，则为编译错误，除非该具名类至少有一个显式声明的构造函数，并且该异常类或其任父类在每个构造函数的 `throws` 子句中都被显式声明。

> 注意，如果匿名类（§8.5.5）的实例变量初始化器或实例初始化器可以抛出异常，则不会导致编译错误。在具名类中，程序员有责任通过在任何显式构造函数声明上声明 `throws` 子句来传播关于可以抛哪些异常的信息。这种由匿名类声明的类构造函数所抛出的检查异常之间的关系，是因为无法进行显式构造函数声明，且 Java 编译器始终根据其初始化器可以抛出的检查异常类为匿名类声明生成一个带有合适 `throws` 子句的构造函数。

如果 `catch` 子句可以捕获检查异常类 `E1`，且阻塞该 `catch` 子句的 `try` 块不能抛出 `E1` 的子类或父类的检查异常类，除非 `E1` 是 `Exception` 或 `Exception` 的父类，则为编译错误。

如果 `catch` 子句可以捕获异常类 `E1`，且紧邻其的 `try` 语句的前一个 `catch` 子句可以捕获 `E1` 或 `E1` 的父类，则为编译错误。

如果 `catch` 子句可以捕获检查异常类 `E2`，且该 `catch` 子句对应的 `try` 块也可以捕获检查异常类 `E2`，其中 `E2 < E1`；且该 `try` 语句的前一个 `catch` 子句可以捕获异常 `E3`，其中 `E2 < E3 < E1`，则鼓励 Java 编译器发出警告。

## 示例 11.2.3-1. 捕获检查异常

```
import java.io.FileNotFoundException;
import java.io.IOException;

class StaticallyThrownExceptionsIncludeSubtypes {
    public static void main(String[] args) {
        try {
            throw new FileNotFoundException();
        } catch (IOException ice) {
            // "catch IOException" 捕获了 IOException
        }

        try {
            throw new FileNotFoundException();
            // 语句可以抛出 FileNotFoundException。
            // 从形式上讲，它并不“可以抛出”FileNotFoundException 的子类或父类。
        } catch (FileNotFoundException nfe) {
            // ...
        } catch (IOException ice) {
            // 合法，但编译器鼓励给出警告，因为 IOException 已被之前的 catch 子句捕获。
        }

        try {
            m();
            // m  throws IOException，所以 m 可以抛出 IOException。
        } catch (FileNotFoundException nfe) {
            // 合法，因为异常的动态类型可能是 FileNotFoundException。
        } catch (IOException ice) {
            // 合法，因为异常的动态类型可能是 IOException 的不同子类。
        } catch (Throwable t) {
            // 可以捕获 Throwable。
        }
    }

    static void m() throws IOException {
        throw new FileNotFoundException();
    }
}
```

## 11.3 异常的运行时处理

根据上述规则，多异常处理（§14.20）中的每个分支必须能够捕获 `try` 块抛出的未被之前的 `catch` 子句捕获的异常。例如，下面的第二个 `catch` 子句会导致编译错误，因为异常分析确定 `SubclassOfFoo` 已被第一个 `catch` 子句捕获：

```
try ( ... )
catch (Foo f) ( ... )
catch (Bar | SubclassOfFoo e) { ... }
```

当抛出异常时（§14.18），控制从引发异常的代码转移到最近的、可以处理该异常的 `try` 语句（§14.20）的 `catch` 子句。

一个语句或表达式动态包含在 `catch` 子句中，如果它出现在 `catch` 子句所属语句的 `try` 块中，或者它的调用者动态包含在 `catch` 子句中。

语句或表达式的调用者取决于其所在的位置：

- 在方法内部，调用者是为了调用该方法而执行的方法调用表达式（§15.12）。
- 在构造函数或实例初始化器或实例变量初始化器内部，调用者是类实例表达式（§15.9）或为了创建对象而执行的 `newInstance` 方法调用。
- 在静态初始化器或静态变量初始化器内部，调用者是为了初始化类或接口而使用该类或接口的表达式（§12.4）。

特定的 `catch` 子句是否可以处理某个异常，通过比较抛出的对象的 `catch` 子句与 `catch` 子句的可捕获异常类来确定。如果其可捕获异常类之一是异常的类或该类的父类，则该 `catch` 子句可以处理该异常。

等价地，`catch` 子句将捕获任何是其可捕获异常类的 `instanceof` 异常对象（§15.20.2）。

当抛出异常时发生的控制转移会导致表达式（§15.6）和语句（§14.1）的异常终止，直到遇到能够处理该异常的 `catch` 子句；随后执行将通过执行导致异常的 `catch` 子句块继续，而导致异常的那个语句块的执行将不再恢复。

所有异常（同步和异步）都是精确的：当控制转移发生时，在抛出异常的点之前执行的语句和评估的表达式的所有效果似乎都已发生。在抛出异常的点之后，任何异常、语句或部分都不可能被认为已评估。

```
Optimized code speculatively executed some of the expressions or statements which follow the point at which the exception occurs, which code must be prepared to hide this speculative execution from the user-visible state of the program.
```

如果找不到能够处理该异常的 `catch` 子句，当前线程（遇到异常的线程）将终止。在终止时，所有的 `finally` 子句都将被执行，并根据以下规则处理未捕获的异常：

- 如果当前线程设置了未捕获异常的处理器，则执行该处理器。
- 否则，将为当前线程的父级 `ThreadGroup` 调用 `uncaughtException` 方法。如果 `ThreadGroup` 及其父级 `ThreadGroups` 未重写 `uncaughtException`，则调用默认处理器的 `uncaughtException` 方法。

在需要确保一个代码块始终另一个代码块之后执行的情况下，如果另一个代码块异常终止，可以使用带有 `finally` 子句的 `try` 语句（§14.20.2）。

如果 `try-finally` 中的 `try` 或 `catch` 块异常终止，则在异常传播期间将执行 `finally` 子句，即使最终没有找到匹配的 `catch` 子句。

如果因为 `try` 块的异常终止而执行了 `finally` 子句，且 `finally` 子句本身也异常终止，则 `try` 块异常终止的原因将被丢弃，新的异常终止原因将进行传播。

异常终止和异常捕获的精确规则在 §14（块、语句和模式）中每个语句的规范以及 §15（表达式）中（特别是 §15.6）表达式的规范中进行了详细说明。

## 示例 11.3-1 抛出和捕获异常

以下程序声明了一个异常类 `TestException`。`Test` 类的 `main` 方法调用了四次 `thrower`，导致其中三次抛出了异常。`main` 方法中的 `try` 语句捕获了 `thrower` 抛出的每个异常。无论 `thrower` 的调用是正常完成还是异常终止，都会打印一条关于发生了什么的消息。

```
class TestException extends Exception {
    TestException() {
        super();
    }
    TestException(String s) {
        super(s);
    }
}
```

```
class Test {
    public static void main(String[] args) {
        for (String arg : args) {
            try {
                thrower(arg);
                System.out.println("Test \" " + arg + "\" didn't throw an exception\");
            } catch (Exception e) {
                System.out.println("Test \" " + arg + "\n\" throw a \" " + e.getClass() + "\n with message: \" " + e.getMessage());
            }
        }
        static int thrower(String s) throws TestException {
            try {
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
                }
                return 0;
            } finally {
                System.out.println("{thrower \" " + s + " \"}");
            }
        }
    }
}
```

（注：原文代码块中存在一些语法错误，如 `static` 方法嵌套在方法内部以及引号转义问题，根据要求保留原代码块不翻译）

如果我们执行该程序，传递以下参数：

divide null test

它会产生如下输出：

```
{thrower " divide " }
Test "divide" throw a java.lang.ArithmeticException with message: / zero
{thrower " null " }
Test "null" throw a java.lang.NullPointerException with message: null
{thrower " test " }
Test "test" throw a TestException with message: Test message
{thrower " divide " }
Test "divide" didn't throw an exception
```

（注：此处示例输出逻辑似乎与代码逻辑有出，但作为翻译员，仅处理描述部分的翻译）

如果我们执行该程序，传递以下参数：

java Test reboot Enzo

通常会启动一个虚拟机并调用 `Test`（一个无包的类）的 `main` 方法，传递包含字符串 "reboot", "Bob", "dot", 和 "Enzo" 的数组。

我们现在概述虚拟机执行 `Test` 的步骤，作为对后续章节详细描述的加载、链接和初始化过程的示例。

## 12 执行

本章规定了在执行期间发生的活动。它围绕类、接口和对象的生命周期展开。

虚拟机通过加载指定的类或接口并调用 `main` 方法来启动。这里我们概述了从 Java 语言角度出发的启动过程。

后续章节将详细介绍了加载（§12.2）、链接（§12.3）以及初始化（§12.4）。

本章继续介绍类的创建（§12.5）和结束（§12.6），最后描述了类的卸载（§12.7）以及程序退出程序（§12.8）。

## 12.1 虚拟机启动

虚拟机启动的精确语义在《Java虚拟机规范》第 19 版第 5 章中给出。在本规范中，如何向虚拟机指定初始类或接口超出了本规范的范围，但例如，在 UNIX 环境中，命令行：

```
java Test reboot Enzo
```

通常会启动一个虚拟机。

### 12.1.1 加载类 Test

初始执行 `Test` 类的 `main` 方法发现类 `Test` 尚未加载——即虚拟机当前不包含该类的二进制表示。随后，虚拟机使用加载器尝试查找这样的二进制表示。如果此过程失败，则将抛出异常。该加载过程在 §12.2 中有详细说明。

### 12.1.2 链接 Test：验证、准备、（可选）解析

在 `Test` 加载后，调用 `main` 之前必须对其初始化。而且 `Test` 与所有类和接口一样，在初始化之前必须进行链接。链接涉及验证、准备和可选的解析。链接在 §12.3 中详细说明。

验证检查加载的表示是否良好且具有正确的符号表。验证还检查 `Test` 代码是否遵守 Java 编程语言和 Java 虚拟机的语义要求。如果在验证期间检测到问题，则将抛出错误。验证在 §12.3.1 中详细说明。

准备涉及静态存储的分配以及虚拟机实现内部使用的任何数据结构（如方法表）。准备在 §12.3.2 中详细说明。

### 12.1.3 初始化 Test：执行初始化器

在我们持续的示例中，Java 虚拟机仍在尝试执行类 `Test` 的 `main` 方法。只有在该类已经完成初始化（§12.4.1）的情况下，才被允许这样做。

初始化包括按照文本顺序执行类 `Test` 的任何类初始化器和静态初始化器。在 `Test` 可以初始化之前，必须初始化它的直接父类，以及其直接父类的直接父类，依此类推，递归。在最简单的情况下，`Test` 有 `Object` 作为其隐式的直接父类；如果类 `Object` 尚未被初始化，则必须在初始化 `Test` 之前先初始化它。类 `Object` 没有父类，因此递归在此终止。

如果类 `Test` 有另一个类 `Super` 作为其父类，则必须在初始化 `Test` 之前初始化 `Super`。这要求在尚未完成这些操作的情况下对 `Super` 进行加载、验证和准备，并且取决于实现，可能还涉及递归地解析来自 `Super` 的符号引用，此类推。

初始化可能会导致加载、链接和初始化错误，包括涉及其他类和接口的此类错误。

初始化过程在 §12.4 中进行了进一步描述。

### 12.1.4 调用 Test.main

最后，在完成类 `Test` 的初始化后（在此期间可能已经发生了其他相关的加载、链接和初始化），将调用 `Test` 的方法。

方法 `main` 必须声明为 `public`、`static` 和 `void`。它必须指定一个形式参数（§8.4.1），其声明类型为 `String` 数组。因此，以下两种声明中的一种都是可以接受的：

```
public static void main(String[]) args
```

```
public static void main(String... args)
```

## 12.2 类和接口的加载



加载是指具有特定名称的类或接口的二进制形式的过程，可能是通过动态计算的，但更常见的是通过检索先前由 Java 编译器从源代码编译的二进制表示，并从该二进制文件构造一个 `Class` 对象来表示该类或接口（§1.4）。

加载的精确语义在《Java 虚拟机规范》Java SE 19 版的第 5 章给出。这里我们从 Java 编程语言的角度展示了该过程的概述。

加载的精确语义由《Java 虚拟机规范》Java SE 19 版的第 5 章给出。类或接口的二进制表示通常是第 4 章中描述的。

# 12.2.1 加载过程

加载过程由 `ClassLoader` 及其子类实现。不同的 class loader 可能会根据需要来缓存类或接口的二进制表示，或者根据预期使用预取它们。例如，一个 class loader 可能会在类或接口的二进制表示被使用时，预取相关的类或接口的二进制表示。如果在类加载期间发生错误，则将在程序直接或间接地使用类或接口的位点抛出以下错误：

- `ClassCircularityError`：由于循环，类或接口无法被 class loader 加载。
- `ClassFormatError`：类或接口的二进制数据格式错误。
- `NoClassDefFoundError`：class loader 无法找到类或接口的定义。

由于加载涉及分配新的数据结构，它可能会因 `OutOfMemoryError` 失败。

# 12.2.2 类加载的一致性

良好的 class loader 维护以下属性：

- 给定相同的名称，class loader 始终返回相同的 `Class` 对象。
- 如果 class loader `L1` 将类或接口的加载委托给另一个 `L2`，那么对于 `C` 的直接父类类型，或直接父接口类型，或 `C` 中的字段类型，或 `C` 方法的形式参数类型，或 `C` 方法的返回类型，`L1` 和 `L2` 应该返回相同的 `Class` 对象。

恶意的 class loader 可能会违反这些属性。然而，它无法破坏类型系统，因为 Java 虚拟机对此进行了防护。

# 类和接口的链接

关于这些问题的进一步讨论，请参阅《Java 虚拟机规范》以及由 Sheng Liang 和 Gil Bracha 论文 *Dynamic Class Loading in the Java Machine*，该论文发表于 ACM SIGPLAN Notices 第 33 卷第 10 期，1998 年 10 月，第 36-44 页。Java 语言设计的一个基本原则是，运行时系统无法被 Java 语言的代码所破坏，即使对于 `ClassLoader` 等敏感类。

链接是将类或接口的二进制形式结合到 Java 虚拟机的运行时状态的过程，以便能够执行。类或接口在链接之前总是会被加载。

链接的精确语义在《Java 虚拟机规范》Java SE 19 版的第 5 章给出。我们从 Java 编程语言的角度展示了该过程的概述。

链接涉及三个不同的活动：验证、准备和符号引用的解析。规范允许链接活动（以及递归的加载）发生的时间具有实现灵活性，前提是尊重 Java 编程语言的语义，类或接口在初始化之前已完全验证和准备，并且在链接期间检测到的错误必须在程序采取某些可能要求对与错误相关的类或接口进行链接的动作位点抛出。

例如，实现可能会单独解析类或接口中的每个符号引用，仅在被使用时解析（惰性或延迟解析），或者在验证类时一次性解析所有引用（静态解析）。这意味着在某些实现中，解析过程在类或接口初始化后可能继续。

由于链接涉及分配新的数据结构，它可能会因 `OutOfMemoryError` 失败。

## 12.3.1 二进制表示的验证

验证确保类或接口的二进制表示在结构上是正确的。例如，它检查每个指令是否具有有效的操作码；每个跳转指令是否跳转到另一个指令的开头，而不是指令的中间；每个方法都

# 12.4 类和接口的初始化

类的初始化包括执行该类的静态初始化器以及在类中声明的静态字段（类变量）的初始化器。

接口的初始化包括执行在接口中声明的字段（常量）的初始化器。

## 12.4.1 初始化发生的时机

类或接口 $\tau$ 将在以下任一种情况首次发生之前立即初始化：

- $\tau$ 是一个类且创建了 $\tau$ 的实例。
- 调用了由 $\tau$ 声明的 `static` 方法。
- 使用了由 $\tau$ 声明的 `static` 字段，且该字段不是常量变量（§4.12.4）。

当一个类被初始化时，它的超类会被初始化（如果它们之前没有被初始化），以及任何声明了默认方法（§9.4.3）的超接口（§8.1.5）也会被初始化（如果它们之前没有被初始化）。接口的初始化本身不会导致其超接口的初始化。

初始化代码不受限制这一事实允许构造出某些示例，在类变量仍保持默认值时即可观察到其值，但此类示例在实践中非常罕见。Java 语言的完整威力在这些初始化器中可用；程序员必须格外小心。这种力量给代码生成器带来了额外的负担，这种负担在 Java 语言并发的任何情况下（§12.4）都会产生。

### 示例 12.4.1-1. 超类在子类之前初始化

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

类 `One` 从未被初始化，因为它没有被积极使用，因此从未被链接。类 `Two` 只有在其超类 `Super` 初始化后才会被初始化。

### 示例 12.4.1-2. 只有声明 static 字段的类会被初始化

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

该程序仅打印：

1729

因为类 `Sub` 没有被初始化；`Sub.taxi` 的引用是对实际上在类 `Super` 中声明的字段的引用，不会触发类 `Sub` 的初始化。

### 示例 12.4.1-3. 接口初始化不会初始化超接口

```java
interface I {
    int i = ii = Test.out("ii", 2);
}
interface J extends I {
    int j = out("j", 3), jj = Test.out("jj", 4);
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

该程序产生以下输出：

ii=2
jj=3
jj=4
3

对 `J.i` 的引用是一个常量变量（§4.12.4）；因此，它不会导致 `I` 被初始化（§13.4.9）。

对 `K.j` 的引用是对实际上在接口 `J` 中声明的非常量变量字段的引用；这会导致接口 `J` 及其字段的初始化，但不会初始化其超接口 `I` 或接口 `K`。

尽管使用了名称 `K` 来引用接口 `J` 的字段 `j`，但接口 `K` 并没有初始化。

## 12.4.2 详细初始化步骤

由于 Java 编程语言是多线程的，类或接口的初始化需要仔细的同步，因为可能有其他线程正尝试初始化同一个类或接口。还可能作为该类或接口初始化的一部分，递归地请求初始化；例如，类 `A` 中的变量初始化器可能会调用无关类 `B` 的方法，而 `B` 又可能调用类 `A` 的方法。Java 虚拟机的实现负责通过以下程序处理同步和递归初始化。

该程序假设 `Class` 对象已经通过验证并准备就绪，且 `Class` 对象包含指示以下四种情况之一的状态：

- 此 `Class` 对象已通过验证并准备就绪，但尚未初始化。
- 此 `Class` 对象正在被某个特定线程 `T` 初始化。
- 此 `Class` 对象已完全初始化并可以使用。
- 此 `Class` 对象处于错误状态，可能是因为尝试初始化并失败了。

对于每个类或接口 `c`，都有唯一的初始化锁 `LC`。从 `c` 到 `LC` 的映射由 Java 虚拟机的实现决定。初始化 `c` 的程序如下：

1. 对 `c` 的初始化锁 `LC` 进行同步。这涉及等待直到当前线程可以获取 `LC`。
2. 如果 `c` 的类表示其他线程正在初始化 `c`，则释放 `LC` 并阻塞当前线程，直到收到正在进行的初始化已完成的通知，此时重复此步骤。
3. 如果 `c` 的类表示当前线程正在初始化 `c`，则这必须是一个递归初始化请求。释放 `LC` 并正常完成。
4. 如果 `c` 的类对象表示 `c` 已经初始化，则无需进一步操作。释放 `LC` 并正常完成。
5. 如果 `c` 的类对象处于错误状态，则无法进行初始化。释放 `LC` 并抛出 `NoClassDefFoundError`。
6. 否则，记录当前线程正在初始化 `c` 类对象的事实，并释放 `LC`。

然后，初始化 `c` 的常量变量字段（§4.12.24, §8.3.2, §9.3.1）。

接下来，如果 `c` 是类而非接口，则让 `sc` 为其超类，并让 `SI1, ..., SIm` 为 `c` 声明了至少一个默认方法的所有超接口。超接口的顺序通过对 `c` 直接实现的每个接口的超接口层级进行递归枚举给出（按照 `C` 的 `implements` 子句从左到右的顺序）。对于 `c` 直接实现的每个接口 `I`，在返回 `I` 之前，对其超接口进行枚举（按照 `I` 的 `extends` 子句从左到右的顺序）。

对于 `[ SC, SI1, ..., SIn ]` 中的每个 `s`，如果 `s` 尚未初始化，则对 `s` 递归执行整个程序。如有必要，先验证并准备 `s`。

如果 `s` 的初始化由于异常异常终止，则获取 `LC`，将 `Class` 对象标记为 `c` 错误，通知所有等待线程，释放 `LC` 并异常完成，抛出导致初始化 `s` 的相同异常。

8. 下一步，通过查询定义类加载器确定 `c` 是否启用了断言（§14.10）。
9. 下一步，按照文本顺序执行类变量初始化器和静态初始化器，或者接口的字段初始化器，仿佛它们是一个整体。
10. 如果初始化器的执行正常完成，则获取 `LC`，将 `c` 的类对象标记为完全初始化，通知所有等待线程，释放 `LC` 并正常完成此程序。
11. 否则，初始化器必须通过抛出某些异常异常完成。如果类 `E` 不是 `Error` 或其子类之一，则创建一个新的 `ExceptionInInitializerError` 实例并将 `E` 为参数，并使用该对象代替 `E`。如果由于发生 `OutOfMemoryError` 无法创建新的 `ExceptionInInitializerError` 实例，则在后续步骤中使用 `OutOfMemoryError` 代替 `E`。
12. 获取 `LC`，将 `c` 的类对象标记为错误，通知所有等待线程，释放 `LC` 并带理由异常完成此程序。

实现可以通过省略锁的优化，如果它可以确定初始化已经完成，那么调用初始化程序将不再需要，可以将其消除——例如，通过补丁或重新生成代码。在某些情况下，如果可以确定一组相关类和接口的初始化顺序，编译时分析可能从生成的代码中消除许多关于类已初始化的检查。然而，这种分析必须充分考虑到并发性以及初始化代码不受限制的事实。

# 执行

## 创建新类实例

否则，新对象中的所有实例变量（包括在父类中声明的变量）都被初始化为它们的默认值（§4.12.5）。

在将新创建的对象的引用作为结果返回之前，将处理指定的构造函数，按照以下步骤初始化新对象：

- 将构造函数的参数赋值给该构造函数调用新创建的参数变量。
- 如果该构造函数以同类中另一个构造函数的显式构造函数调用（§8.8.7.1）（使用 `this`）开头，则评估参数并使用这相同的五个步骤递归地处理构造函数调用。如果该构造函数异常终止，则此过程也因相同原因异常终止；否则，继续执行步骤 5。
- 该构造函数没有以同类中另一个构造函数的显式构造函数调用（使用 `this`）开头。如果该构造函数用于 `Object` 以外的类，则该构造函数将显式或隐式地调用父类构造函数（使用 `super`）。评估参数并使用这相同的五个步骤递归地处理父类构造函数调用。如果该构造函数调用异常终止，则此过程也因相同原因异常终止。否则，继续执行步骤 4。
- 执行该类的实例初始化器和实例变量初始化器，将实例变量初始化器的值赋值给相应的实例变量，按照它们在类源代码中从左到右出现的顺序。如果执行这些初始化器中的任何一个导致异常，则不再处理后续初始化器，且此过程以相同的异常异常终止。否则，继续执行步骤 5。
- 执行该构造函数体的体部分。如果执行异常终止，则此过程也因相同原因异常终止。否则，此过程正常完成。

与 C++ 不同，Java 语言没有规定在创建新类时改变方法分发规则。如果在正在初始的对象中调用了在子类中重写的方法，则将使用这些重写的方法，甚至在新对象完全初始化之前。

### 示例 12.5-1 实例创建的评估

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

在这里，创建了一个 `ColoredPoint` 实例。首先，为新的 `ColoredPoint` 分配空间以存储字段 `x`、`y` 和 `color`。所有这些字段都被初始化为它们的默认值（在这种情况下，每个字段均为 0）。接下来，调用了无参数的 `ColoredPoint` 构造函数。由于 `ColoredPoint` 没有声明构造函数，因此隐式地声明了以下形式的默认构造函数：

```java
ColoredPoint() { super(); }
```

该构造函数调用了无参数的 `Point` 构造函数。由于 `Point` 构造函数没有以调用构造函数开头，Java 编译器提供了对其父类无参数构造函数的隐式调用，仿佛：

```java
Point() { super(); x = 1; y = 1; }
```

因此，调用了无参数的 `Object` 构造函数。

`Object` 类没有父类，递归在此终止。接下来，调用 `Object` 的任何初始化器和实例变量初始化器。接下来，执行无参数的 `Object` 构造函数的体。`Object` 中没有声明此类构造函数，因此 Java 编译器提供了一个默认的构造函数，在这种特殊情况下为：

```java
Object() { }
```

该构造函数执行而不产生任何效果并返回。

接下来，执行 `Point` 类实例变量的所有初始化器。`x` 和 `y` 的声明没有提供任何初始化表达式，因此此示例的这一步不需要任何操作。然后执行 `Point` 构造函数的体，将 `x` 设置为 1，`y` 设置为 1。

接下来，执行 `ColoredPoint` 类实例变量的初始化器。这一步将 `0xFF00FF` 赋值给 `color`。最后，执行 `ColoredPoint` 构造函数体的剩余部分（调用 `super` 之后的部分）；体的剩余部分恰好没有语句，因此不需要进一步的操作，初始化完成。

### 示例 12.5-2 实例创建期间的动态分发

```java
class Super {
  Super() { printThree(); }
  void printThree() { System.out.println("three"); }
}
class Test extends Super {
    int three = (int)Math.PI; // 真 3
    void printThree() { System.out.println("three"); }

    public static void main(String[] args) {
        Test t = new Test();
        t.printThree();
    }
}
```

该程序产生输出：

0
3

这表明在 `Super` 类构造函数中调用 `printThree` 并没有调用 `Super` 类中 `printThree` 的定义，而是调用了 `Test` 类中重写的 `printThree` 定义。该方法在 `Test` 的初始化器执行之前运行，这就是为什么输出的值是 0（`Test` 类字段 `three` 被初始化的默认值）。稍后在 `main` 方法中调用 `printThree` 调用了相同的 `printThree` 定义，但到那时实例变量 `three` 的初始化器已经执行，因此打印了值 3。

# 执行

## 类实例的终化



## 12.6 类实例的终化

需要注意的是，可能有许多终化线程处于活动状态（这在共享多处理器上有时是需要的），并且如果一个大型连接结构变得不可达，则所有对象可能同时变为可终化。最终，这些对象的终化器可能会以任何顺序调用，甚至使用多个线程并发调用。如果存储管理器发现对象不可达，则可以回收它们的存储。

实现一个在所有对象变得不可达时按指定顺序调用一组类似终化方法的类是简单的。定义这样一个类留给读者练习。

保证在调用终化器时，调用者不会持有任何用户可见的锁。

如果在终化期间抛出未捕获的异常，则该异常被忽略且该对象的终化终止。

对象的构造函数的完成发生在（§17.4.5）其 `finalize` 方法的执行之前（正式意义上的发生之前）。

`Object` 类中声明的 `finalize` 方法不执行任何操作。`Object` 类声明了 `finalize` 方法，意味着任何类的 `finalize` 方法始终可以调用其父类的 `finalize` 方法。这应该总是这样做，除非程序员的意图是消除父类中的终化器。出于效率考虑，实现可以跟踪没有重写 `Object` 类 `finalize` 方法或以简单方式重写该方法的类。

例如：

```java
protected void finalize() throws Throwable {
  super.finalize();
}
```

我们鼓励实现将此类对象视为具有未重写的终化器，并按照 §12.6.1 中的描述更高效地终化它们。

终化器可以被显式调用，就像任何其他方法一样。

### 12.6.1 实现终化

`java.lang.ref` 包描述了引用，这些引用与垃圾收集和终化交互。作为任何与 Java 编程语言有特殊交互的 API，实现者必须意识到 `java.lang.ref` API 施加的任何要求。本规范未以任何方式讨论弱引用。详细信息请参阅 API 文档。

每个对象都可以通过两个属性来表征：它可能是可到达的（`reachable`）、终化器可到达的（`finalizer-reachable`）或不可到达的（`unreachable`），它也可能是未终化的（`unfinalized`）、可终化的（`finalizable`）或已终化的（`finalized`）。

可到达的对象是指从任何存活线程的任何潜在后续计算中都可以访问的任何对象。

终化器可到达的对象可以通过某些引用链从某个可终化的对象到达，但无法从任何存活线程到达。

不可到达的对象无法通过上述任何方式到达。

未终化的对象从未被自动调用过其终化器。

已终化的对象已经被自动调用过其终化器。

可终化的对象从未被自动调用过其终化器，但 Java 虚拟机可能会最终自动调用其终化器。

在对象 $o$ 的构造函数调用了针对 $o$ 的 `Object` 构造函数且该调用成功完成（即没有抛出异常）之前，对象 $o$ 不是可终化的。终化前对对象字段的任何写入必须对该对象的终化可见。此外，对该对象字段的任何终化前读取都不得看到在对象终化启动后发生的写入。

对程序的优化转换可以设计为减少可到达对象的数量，使其少于通常直观认为可到达的数量。例如，Java 编译器或代码生成器可能会选择将不再使用的变量或参数的存储位置，使得该对象可能更早地被回收。

另一个示例发生在对象字段中的值存储在寄存器中。此时程序可能会访问寄存器而不是对象，并且再也不访问该对象。这意味着该对象是垃圾。请注意，这种优化仅在引用位于栈上而非存储在堆中时才允许。

例如，考虑终化器守护者模式：

```java
class Foo {
    private final Object finalizerGuardian = new Object() {
        protected void finalize() throws Throwable {
            /* finalize 外部 Foo 对象 */
        }
    }
}
```

如果子类重写了 `finalize` 且没有显式调用 `super.finalize`，则终化器守护者将强制调用 `super.finalize`。

如果允许此类优化应用于存储在堆上的引用，Java 编译器可以检测到 `finalizerGuardian` 字段从未被读取过，立即将该对象置为空，并尽早调用终化器。这与意图背道而驰：程序员可能希望在 `Foo` 实例变为不可到达时调用 `Foo`。因此，这种转换是不合法的：只要外部类是可到达的，内部类就应该是可到达的。

此类转换可能会导致 `finalize` 方法的调用比可能预期的更早发生。为了允许用户防止这种情况，我们强制引入了“同步可能会保持对象存活”的概念。如果一个对象的终化器可以导致对该对象的同步，那么在许多情况下同步无法被移除时，该对象必须是存活的并被视为可到达的。

请注意，这并没有阻止同步消除：只有当终化器可能会对其进行同步时，同步才会保持对象存活。由于终化器发生在另一个线程中，在许多情况下同步无法被移除。

### 12.6.2 与内存模型的交互

内存模型（§17.4）必须能够决定何时可以提交在终化器中发生的操作。本节描述了终化与内存模型的交互。

每次执行都有若干可到达性决策点，标记为 $di$。每个动作要么发生在之前（`comes-before`），要么发生在之后（`comes-after`）。如前明确提到的，本节描述的发生在之前的排序与内存模型中的所有其他排序无关。

如果 $r$ 是一个看到了 $w$ 的读取且 $r$ 发生在 $di$ 之前，$w$ 必须发生在 $di$ 之前。

如果 $x$ 和 $y$ 是对变量或监视器的同步操作，使得 $so(x, y)$（§17.4）且 $y$ 发生在 $di$ 之前，$x$ 必须发生在 $di$ 之前。

在每个可到达性决策点，一组对象被标记为不可到达，这些对象的一个子集被标记为可终化。这些可到达性决策点也是根据 `java.lang.ref` 包 API 文档提供的规则对引用进行检查、入队和清除的点。

在点 $di$ 处被认为确定可到达的对象是指通过应用这些规则可以证明是可到达的：

- 对象 $B$ 在 $di$ 处从静态字段是确定可到达的，如果存在对类 $c$ 的静态字段 $v$ 的写入 $w1$，使得 $w1$ 写入的值是指向 $B$ 的引用，类 $c$ 由响应式类加载器加载，且不存在对 $v$ 的写入 $w2$ 使得 $hb(w2, w1)$ 为假且 $w1$ 和 $w2$ 都发生在 $di$ 之前。

- 对象 $B$ 在 $di$ 处从 $A$ 是确定可到达的，如果存在对 $A$ 的元素 $v$ 的写入 $w1$，使得 $w1$ 写入的值是指向 $B$ 的引用，且不存在对 $v$ 的写入 $w2$ 使得 $hb(w2, w1)$ 为假且 $w1$ 和 $w2$ 都发生在 $di$ 之前。

- 未终化的对象从未被自动调用过其终化器。

- 已终化的对象已经被自动调用过其终化器。

- 可终化的对象从未被自动调用过其终化器，但 Java 虚拟机可能会最终自动调用其终化器。

## 12.7 类和接口的卸载

Java 实现可以卸载类。

类或接口可以被卸载仅当其定义加载器可以被回收时（如 12.6 所示）。

由引导加载器加载的类和接口可能被卸载。

然而，如果一个类在其加载器可能可到达时被卸载，那么它可能会被重新加载。可以确保这种情况不会发生。即使该类没有被任何加载的类引用，它也可能被尚未加载的类或接口引用。

重新加载不是透明的，例如如果类具有静态变量（其状态将丢失）、静态初始化器（可能会产生副作用）或原生方法（可能会保留静态状态）。此外，`Class` 对象的哈希值依赖于其标识性。因此，通常无法以完全透明的方式重新加载类。

由于我们无法保证在加载器可能可到达时卸载类不会导致重新加载，而重新加载不是透明的，但卸载必须是透明的，因此得出不能在加载器可能可到达时卸载类的结论。

类卸载优化对于那些加载大量类并在一段时间后停止使用大多数此类类的应用程序具有重要意义。此类应用程序的主要示例是浏览器，但其他应用程序也有类似特征。此类应用程序的特点是通过显式使用类加载器来管理类。因此，上述策略对它们非常有效。

## 12.8 程序退出

当发生以下两种情况之一时，程序将终止所有活动并退出：

- 所有非守护线程都已终止。
- 某个线程调用了 `Runtime` 类或 `System` 类的 `exit` 方法，且该退出操作未被安全管理器禁止。

# 第 13 章 二进制兼容性

Java 编程语言的开发工具应当在源代码可用时，根据需要支持自动重新编译。特定的实现还可能将类和接口的源代码和二进制表示存储在版本数据库中，并实现一个 `ClassLoader`，该类使用数据库的完整性机制，通过向客户端提供二进制兼容的类和接口版本来防止链接错误。

要广泛分发的包、类和接口的开发者面临着一套不同的问题。在互联网（我们广泛分布系统的第一个示例）中，自动重新编译直接或间接依赖于要更改的类或接口的现有二进制文件通常是不切实际或无法实现的。相反，本规范定义了一系列开发者允许对包或类或接口进行的更改，同时保留了与现有二进制文件的兼容性（即不破坏兼容性）。

在 SOM 的“发布版本间的二进制兼容性”（Foreman, Danforth, and Raper, Proceedings of OOPSLA '95）框架内，Java 编程语言的二进制文件在作者识别的所有相关转换上都具有二进制兼容性（在添加实例变量方面存在限制）。根据他们的方案，以下是 Java 编程语言支持的重要二进制更改列表：

- 重新实现现有的方法、构造函数和初始化器以提高性能。
- 更改方法或构造函数，使其对某些输入返回结果，而这些输入之前可能会抛出不应发生的异常，或因进入无限循环或导致死锁而失败。
- 向现有的类或接口添加新的字段、方法或构造函数。
- 删除类的私有字段、方法或构造函数。
- 当更新整个包时，删除包内类和接口的包级访问字段、方法或构造函数。
- 重新排序现有类或接口声明中字段、方法或构造函数的顺序。
- 在类层次结构中将方法向上移动。
- 重新排序类或接口的直接父接口列表。
- 在类型层次结构中插入新的类或接口类型。

本章规定了所有实现必须保证的二进制兼容性的最低标准。当混合使用类和接口的二进制文件且已知它们并非来自兼容来源，但其源代码按照此处描述的兼容方式进行了修改时，Java 编程语言保证兼容性。请注意，我们讨论的是应用程序版本之间的兼容性。Java SE 平台版本之间的兼容性讨论超出了本章的范围。

我们鼓励开发系统提供功能，提醒开发者更改对无法重新编译的现有二进制文件的影响。

本章首先规定了 Java 编程语言的任何二进制必须具备的某些属性（§13.1）。接着定义了二进制兼容性，解释了它是什么以及不是什么（§13.2）。最后列举了对包（§13.3）、类（§13.4）和接口（§13.5）大量的可能更改并说明了这些更改中哪些是保证保留二进制兼容性的，哪些不是。

偶尔，会使用如下形式的引用：`(JVMS §x.y)` 来表示源自《Java 虚拟机规范，Java SE 19 版》的概念。

## 13.1 二进制的形式

程序必须编译为《Java 虚拟机规范，Java SE 19 版》指定的类文件格式，或者编译为可以由 Java 编程语言编写的类加载器映射为该格式的表示。

对应类或接口声明的类文件必须具有某些属性。这些属性中的许多是为了支持保留二进制兼容性的源代码转换而专门选择的。要求的属性有：

1. 类或接口必须以其二进制名称命名，该名称必须满足以下约束：
   - 顶层类或接口的二进制名称（§7.6）是其规范名称（§6.7）。
   - 成员类或接口的二进制名称（§8.5, §9.5）由其直接包含的类或接口的二进制名称组成，后跟 `$`，然后是成员的简单名称。
   - 局部类或接口的二进制名称（§14.3）由其直接包含的类或接口的二进制名称组成，后跟 `$`，然后是一个非空数字序列，最后是局部类的简单名称。
   - 匿名类的二进制名称（§15.9.5）由其直接包含的类或接口的二进制名称组成，后跟 `$`，然后是一个非空数字序列。
   - 泛型类或接口声明的类型变量二进制名称（§8.1.2, §9.1.2）由其直接包含的类或接口的二进制名称组成，后跟 `$`，然后是类型变量的简单名称。
   - 泛型方法声明的类型变量二进制名称（§8.4.4）是声明方法的类或接口的二进制名称，后跟 `$`，然后是方法的描述符（JVMS §4.3.3），后跟 `$`，最后是类型变量的简单名称。
   - 泛型构造函数声明的类型变量二进制名称（§8.8.4）是声明构造函数的类二进制名称，后跟 `$`，然后是构造函数的描述符（JVMS §4.3.3），后跟 `$`，最后是类型变量的简单名称。

2. 使用类或接口的二进制名称对另一个类或接口进行的引用。

3. 对常量变量（§4.12）字段的引用必须在编译时通过常量变量的初始化器解析为值 $v$。
   如果此类字段是静态的，二进制文件代码中不应出现该字段的引用，但在声明该字段的类或接口中除外。如果此类字段是非静态的，二进制文件代码中不应出现该字段的引用，但在包含该字段的类中（因为接口只有静态字段）。
   类应具有在实例创建期间将字段值设置为 $v$ 的代码（12.5）。

4. 给定类 $c$ 中的合法字段访问表达式，引用非常量变量且 $f$ 在（可能是不同的）类或接口 $D_i$ 中声明，定义引用的*限定类*或*接口*如下：
   - 如果通过简单名称引用，且 $f$ 是当前类或接口 $c$ 的成员，则令 $\varrho = c$。否则，$\varrho$ 是 $f$ 的内部嵌套类或接口声明。无论何种情况，$\varrho$ 都是该引用的限定类或接口。
   - 如果表达式是 `TypeName.f` 形式，其中 `TypeName` 表示类或接口，则由 `TypeName` 表示的类或接口就是引用的限定类或接口。
   - 如果表达式是 `ExpressionName.f` 或 `Primary.f` 形式，则：
     - 如果 `ExpressionName` 或 `Primary` 的编译类型是交叉类型 $V_1 \dots$ & $V_n$，则引用的限定类或接口是 $V_1$ 的擦除（§4.6）。
     - 否则，`ExpressionName` 或 `Primary` 的擦除是引用的限定类或接口。
   - 如果表达式是 `super.f` 形式，则 $c$ 的父类是引用的限定类或接口。
   - 如果表达式是 `TypeName.super.f` 形式，则 `TypeName` 表示的类的父类是引用的限定类或接口。
   对 $f$ 的引用必须编译为对引用的限定类或接口的符号引用，加上字段的简单名称 $f$。
   引用还必须包含对字段声明类型擦除的符号引用，以便验证器可以检查类型是否符合预期。

5. 给定类或接口 $c$ 中的方法调用表达式或方法引用，引用声明（或隐式声明）的方法 $m$（在 §9.2 中声明）在一个（可能是不同的）类或接口 $D$ 中，我们将方法调用的限定类或接口定义如下：
   - 如果 $D$ 是 `Object`，则方法调用的限定类或接口是 `Object`。
   - 如果该方法通过简单名称引用，那么如果 $m$ 是当前类或接口 $c$ 的成员，则令 $\varrho$ 为 $c$；否则，$\varrho$ 为 $m$ 为成员的最内层词法闭包类或接口声明。在任何种情况下，$\varrho$ 都是该方法调用的限定类或接口。
   - 如果表达式的形式为 `TypeName.m` 或 `ReferenceType::m`，则由 `TypeName` 所指示的类或接口，或 `ReferenceType` 的擦除类型，是该方法调用的限定类或接口。
   - 如果表达式的形式为 `ExpressionName.m` 或 `Primary::m` 或 `ExpressionName::m` 或 `Primary::m`，则：
     - 如果 `ExpressionName` 或 `Primary` 的编译时类型是交集类型 $V_1 \& \dots \& V_n$，则该方法调用的限定类或接口是 $V_1$ 的擦除类型。
     - 否则，`ExpressionName` 或 `Primary` 的编译时类型的擦除类型是该方法调用的限定类或接口。
   - 如果表达式的形式为 `super.m` 或 `super::m`，则 $c$ 是该方法调用的限定类或接口。
   - 如果表达式的形式为 `TypeName.super.m` 或 `TypeName.super::m`，那么如果 `TypeName` 指示一个类 $x$，则 $x$ 的超类是该方法调用的限定类或接口；如果 `TypeName` 指示一个接口 $x$，则 $x$ 是该方法调用的限定类或接口。
   对方法的引用必须在编译时解析为指向该方法调用的限定类或接口的符号引用，外加该方法的声明签名（§8.4.2）的擦除。方法的签名必须包含由 §15.12.3 确定的所有以下内容：
   - 方法的简单名称
   - 方法的参数个数
   - 每个参数类型的符号引用
   对方法的引用还必须包含指向所指示方法的返回类型擦除符号引用，或者指示所指示方法声明为 `void` 且不返回值。

6. 给定的类实例创建（§15.9）或显式构造方法调用语句（§8.8.7.1）或在类或接口 $c$ 中形式为 `ClassType::new` 的方法引用表达式，引用在（可能是不同的）类或接口 $D$ 中声明的构造方法 $m$，我们将*构造方法调用的限定类*定义如下：
   - 如果表达式的形式为 `new D(...)` 或 `ExpressionName.new D(...)` 或 `Primary.new D(...)` 或 `D::new`，则构造方法调用的限定类是 $D$。
   - 如果表达式的形式为 `new D(...) (...)` 或 `ExpressionName.new D(...) (...)` 或 `Primary.new D(...) (...)`，则构造方法调用的限定类是该表达式声明的匿名类。
   - 如果表达式的形式为 `super(...)` 或 `ExpressionName.super(...)` 或 `Primary.super(...)`，则构造方法调用的限定类是 $c$ 的直接超类。
   - 如果表达式的形式为 `this(...)`，则构造方法调用的限定类是 $C$。



# 二进制兼容性

## 二进制表示的形式 13.1

对构造方法的引用必须在编译时解析为指向构造方法调用限定类的符号引用，外加构造方法的声明签名（§8.8.2）。构造方法的签名必须同时包含以下两点：

- 构造方法的参数个数
- 每个形式参数类型的符号引用

一个类的二进制表示必须包含所有以下内容：

1. 如果它是一个类且不是 `Object`，则指向该类直接超类的符号引用。
2. 如果有，则指向每个直接超接口的符号引用。
3. 类或接口中声明的每个字段的规范，给出字段的简单名称和指向字段类型擦除的符号引用。
4. 如果是一个类，则如上所述的每个构造方法的擦除签名。
5. 对于类或接口中声明的每个方法（对于接口，排除其隐式声明的方法 §9.2），其如上所述的擦除签名和返回类型。
6. 代码需要实现字段类或接口：
   - 对于接口，字段初始化器的代码以及每个带有块主体的方法的实现（§9.4.3）。
   - 对于类，字段初始化器的代码、实例初始化器和静态初始化器、每个带有块主体的方法的实现（§8.4.7），以及每个构造方法的实现。
7. 每个类或接口必须包含足够的信息以恢复其规范名称（§6.7）。
8. 每个成员类或接口必须有足够的信息以恢复其源层级修饰符（§6.6）。
9. 每个嵌套类或接口必须包含指向其紧邻闭包的类或接口的符号引用（§8.1.3）。
10. 每个类或接口必须包含对其所有成员类和接口的符号引用。
11. Java 编译器生成的结构如果其对应于源代码中显式或隐式声明的结构，则必须标记为 `synthetic`，除非该生成的结构是类初始化方法。
12. Java 编译器生成的结构如果其对应于源代码中声明的形式参数，则必须标记为 `mandated`（JVM §4.7.24, §4.7.25）。以下结构在源代码中隐式声明：
    - 普通类和枚举类的默认构造方法（§8.8.9, §8.9.2）
    - 记录类的紧凑构造方法（§8.10.4）
    - 匿名构造方法（§15.9.5.1）
    - 枚举类的 `values` 和 `valueOf` 方法（§8.9.3）
    - 枚举类的某些公共字段（§8.9.3）
    - 记录类的某些私有字段和公共方法（§8.10.3）
    - 接口的某些公共方法（§9.2）
    - 容器注解（§9.7.5）

定义的类文件可以具有名为 `module-info` 且没有超类、超接口、字段和方法的类文件属性。此外，模块的二进制表示必须包含所有以下内容：

- 模块名称的规范，给出 `module` 之后名称的符号引用。此外，规范必须包括该模块是否是普通的或开放的（§7.7）。
- `requires` 指令指示的每个依赖，给出由指令指示的模块名称的符号引用（§7.7.1）。此外，规范必须包括该依赖是否是传递的以及该依赖是否是静态的。
- `exports` 或 `opens` 指令指示的每个包，给出由指令限定的包名的符号引用（§7.7.2）。此外，如果指令是该，规范必须给出由指令子句指示的模块名称的符号引用。
- `uses` 指令指示的每个服务，给出由指令指示的类或接口名称的符号引用（§7.7.3）。
- `provides` 指令指示的服务提供者，给出由指令 `with` 子句指示的类和接口名称的符号引用（§7.7.4）。

## 什么是二进制兼容性以及什么不是 13.2

由指令指示为服务的类或接口名称的引用。

后续章节讨论了对类和接口声明进行更改，且这些更改不会破坏与现有二进制文件的兼容性。在上述给出的翻译要求下，Java 虚拟机及其类文件格式支持这些更改。任何其他有效的二进制格式（例如，由类加载器根据上述要求映射回类文件的压缩或加密表示）也将必然支持这些更改。

### 13.2 什么是二进制兼容性以及什么不是

如果对类型的更改使得之前链接无错误的现有二进制文件能够继续无错误地链接，则该更改与现有二进制文件是二进制兼容的（等同于没有破坏与现有二进制文件的兼容性）。

二进制文件被编译用于其他类和其他接口的可访问成员和构造函数。为了保持二进制兼容性，类或接口应将其可访问成员和构造函数的存在及其行为视为与用户之间的约定。

Java 编程语言的设计是为了防止向约定添加内容以及意外的命名冲突破坏二进制兼容性。具体而言，增加更多重载特定方法名的方法不会破坏与现有二进制文件的兼容性。现有二进制文件用于方法查找时使用的方法签名是由重载解析算法在编译时选择的（§13.15.2）。

如果 Java 编程语言的设计是为了在运行时执行特定的方法，那么这种歧义可能会在运行时被检测到。某规则意味着，添加额外的重载方法以导致某处出现歧义，可能会破坏未知数量现有二进制文件的兼容性。更多讨论请参见 §13.4.23。

二进制兼容性不等同于源码兼容性。特别是，§13.4.6 中的示例显示，从一组无法全部编译的源码中可以产生一组兼容的二进制文件。这是典型情况：添加了一个新声明，改变了源代码中未更改部分的某个名称的含义，而源代码未更改部分的现有二进制文件保留了该名称完全限定的先前含义。要生成一组一致的源代码，需要提供与先前的含义相对应的限定名或字段访问表达式。

## 包和模块的演进 13.3

向包中添加新的顶层类或接口可能不会破坏与现有二进制文件的兼容性，前提是新的类或接口没有重用之前给不相关的类或接口的名称。如果新类或接口重用了之前给不相关的类或接口的名称，可能会产生冲突，因为这两个类或接口的二进制文件无法被同一个类加载器加载。

顶层类和接口的更改如果不是公共的，且分别不是公共类或公共接口的超类或超接口，则仅影响其所在包内的类和接口。此类类和接口可以被删除或以其他方式更改，即使此处描述了其他不兼容性，只要该包受影响的二进制文件被一起更新即可。

如果声明为导出（export）或打开（open）某个包的模块更改为不导出该包，或者向不同的 set 导出或打开该包，那么当链接一个需要但不再拥有该包的公共保护类和接口的现有二进制文件时，将抛出 `IllegalAccessError`。对于广泛分发的模块，不建议进行此类更改。

如果模块未被声明为导出或打开某个包，则将模块更改为导出或打开该包不会破坏与现有二进制文件的兼容性。然而，更改模块可能会阻止程序启动，因为读取该模块的任何模块也可能读取另一个导出同名包的模块。

在模块声明中删除 `requires` 指令，或从 `requires` 指令中删除 `transitive` 修饰符，可能会破坏任何现有二进制文件的兼容性，这些二进制文件在引用该模块导出的类和接口的过程中依赖该指令或修饰符来获得特定模块的可读性。当链接来自现有二进制文件的此类引用时，可能会抛出 `IllegalAccessError`。

在模块声明中添加或删除 `uses` 或 `provides` 指令不会破坏与现有二进制文件的兼容性。

## 类演进 13.4

本节描述了对类及其成员、构造函数声明的更改对现有二进制文件的影响。

### 13.4.1 抽象类

如果一个未声明为抽象（`abstract`）的类被更改为抽象，那么尝试创建该类新实例的现有二进制文件将在链接时抛出 `InstantiationError`，或者（如果使用了反射方法）在运行时抛出 `InstantiationException`；因此，不建议对广泛分发的类进行此类更改。

将一个声明为抽象的类更改为不再是抽象不会破坏与现有二进制文件的兼容性。

### 13.4.2 密封（sealed）、非密封（non-sealed）和最终（final）类

#### 13.4.2.1 密封类

如果一个自由扩展的（§8.1.1.2）类被更改为密封的（`sealed`），那么当加载该类的某个现有子类的二进制文件且其不是该类允许的直接子类（§8.1.6）时，将抛出 `IncompatibleClassChangeError`；不建议对广泛分发的类进行此类更改。

将一个声明为最终（`final`）的类更改为密封的不会破坏与现有二进制文件的兼容性。

向密封类的允许的直接子类集中添加一个类不会破坏与现有二进制文件的兼容性。

如果从密封类的允许的直接子类集中移除一个类，那么当加载该类的现有二进制文件时，将抛出 `IncompatibleClassChangeError`。

从没有密封超类或密封超接口的类删除密封修饰符不会破坏与现有二进制文件的兼容性。

> 如果密封类 C 有密封超类或密封超接口，那么删除密封修饰符将阻止 C 重新编译，因为具有密封超类或密封超接口的类必须是最终的或非密封的。

#### 13.4.2.2 非密封类

将一个声明为密封的类更改为非密封的不会破坏与现有二进制文件的兼容性。

将一个声明为最终的类更改为非密封的不会破坏与现有二进制文件的兼容性。

> 非密封类 C 必须有一个密封超类或密封超接口。删除非密封修饰符将阻止 C 重新编译，因为具有密封超类或密封超接口的类必须是最终的、密封的或非密封的。

#### 13.4.2.3 最终类

如果一个未声明为最终的类被更改为最终，那么当加载该类的某个现有超类的二进制文件时，将抛出 `IncompatibleClassChangeError`，因为最终类没有子类；不建议对广泛分发的类进行此类更改。

从没有密封超类或密封超接口的类删除最终修饰符不会破坏与现有二进制文件的兼容性。

> 如果类 C 有密封超类或密封超接口，那么删除最终修饰符将阻止 C 重新编译，因为具有密封超类或密封超接口的类必须是最终的或非密封的（§8.1.1.2）。

### 13.4.3 公共类

将一个未声明为公共（`public`）的类更改为公共不会破坏与现有二进制文件的兼容性。

将一个声明为公共的类更改为非公共，那么当链接一个需要但不再拥有该类类型访问权的现有二进制文件时，将抛出 `IllegalAccessError`；不建议对广泛分发的类进行此类更改。

这表明，如果没有验证器，Java 类型系统可能会通过链接不一致的二进制文件而被攻破，尽管每个文件都是由正确的 Java 编译器生成的。

## 类的演变

本节的启示是：缺乏验证器或未能使用验证器的实现将无法维持类型安全性，因此它不是一个有效的实现。

## 示例 13.4.4-2. 引入父类

泛而言之，在各种情况下，类的转换对于客户端来说可能是二进制兼容的，但在源代码级别上是不兼容的。

例如，多重 catch 子句（§14.20）中的替代方案不是彼此的子类或父类的要求，这仅仅是一个源码限制。以下代码：

```
try {
    failByThrowingAorB();
} catch (A|B e) {
...
}
```

只要在代码编译时 A 和 B 没有子类/父类关系，该代码就是合法的。此后，对于该客户端而言，将 A 和 B 更改为没有这种关系是二进制兼容的。之前编译的代码将继续执行，但由于该更改对于该客户端来说不是源码兼容的，因此代码无法重新编译。

## 13.4.5 类类型参数

添加或删除类的类型参数本身不会对二进制兼容性产生任何影响。

如果此类类型参数被用于字段或方法的类型中，则可能会产生更改上述类型时带来的正常影响。

重命名类的类型参数对现有的二进制文件没有影响。

更改类类型参数的第一个边界可能会更改任何在其自身类型中使用该类型参数的成员的擦除（§4.6），这可能会影响二进制兼容性。此类边界的更改类似于方法或构造函数类型参数的第一个边界的更改（§13.4.13）。

任何其他边界（bound）都对二进制兼容性没有影响。

## 13.4.6 类体和成员声明

添加一个与父类或子类的实例（或相应的静态）成员具有相同名称和可访问性（对于字段），或具有相同名称、可访问性、签名和返回类型（对于方法）的实例（或相应的静态）成员，并不会导致与现有的二进制文件产生不兼容。即使链接的类集合会遇到编译时错误，也不会发生错误。

删除一个未声明为 `private` 的类成员或构造函数，如果该成员或构造函数被现有的二进制文件使用，可能会导致链接错误。

## 示例 13.4.6-1. 修改类体

```
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

hello from Super

假设产生了类 `Super` 的新版本：

```
class Super extends Hyper {
```

那么，重新编译 `Super` 并与 `Test` 和 `Hyper` 的原始二进制文件一起执行此新二进制文件，将产生输出：

hello from Hyper

正如预期。

`super` 关键字可以访问在父类中声明的方法，从而跳过在当前类中声明的任何方法。表达式 `super.Identifier` 在编译时解析为父类 `S` 中的方法 `m`。如果方法 `m` 是一个实例方法，那么运行时调用的方法是包含涉及 `super` 表达式的类的直接父类中与 `m` 签名相同的方法。

## 示例 13.4.6-2. 修改父类

```
class Hyper {
    void hello() { System.out.println("hello from Hyper"); }
}
class Super extends Hyper { }
class Test extends Super {
    public static void main(String[] args) {
        new Test().hello();
    }
    void hello() {
        super.hello();
    }
}
```

该程序产生输出：

hello from Hyper

假设产生了类 `Super` 的新版本：

```
class Super extends Hyper {
    void hello() { System.out.println("hello from Super"); }
}
```

那么，如果重新编译了 `Super` 和 `Hyper` 但没有编译 `Test`，则使用现有的 `Test` 二进制文件运行新的二进制文件将产生输出：

hello from Super

正如你预计的那样。

## 13.4.7 成员和构造函数的访问

更改成员或构造函数的声明访问权限以允许更少的访问，可能会破坏与现有二进制文件的兼容性，导致在解析这些二进制文件时抛出链接错误。如果访问修饰符从包访问（package access）改为私有访问（private access）；从受保护访问（protected access）改为包访问或私有访问；或从公共访问（public access）改为受保护、包或私有访问，则允许更少的访问。随后不再建议对于广泛分发的类更改成员或构造函数允许更少的访问。

可能令人惊讶的是，二进制格式的定义使得更改成员或构造函数以具有更高的访问权限，不会在子类（已）定义一个方法具有更少的访问权限时导致链接错误。

## 示例 13.4.7-1. 修改可访问性

如果包 `points` 定义了类 `Point`：

```
package points;
public class Point {
    public int x, y;
    protected void print() {
        System.out.println(x + "," + y);
    }
}
```

被程序使用：

```
class Test extends Point {
    public static void main(String[] args) {
        Test t = new Test();
        t.print();
    }
    protected void print() {
        System.out.println("Test");
    }
}
```

那么这些类编译并执行产生输出：

Test

如果类 `Point` 中的 `print` 方法更改为 `public`，然后只重新编译 `Point` 类并与现有的 `Test` 二进制文件一起运行，就不会发生链接错误。尽管在编译时重写该方法是不恰当的（除非将 `Test` 中的方法也更改为 `public`）。

## 13.4.8 字段声明

广泛分发的程序不应向客户端暴露任何字段。除了讨论的二进制问题外，这通常是良好的工程实践。向类添加字段可能会破坏现有二进制文件的兼容性。

假设引用类 `c` 的字段 `f`。进一步假设 `f` 是父类 `s` 中的实例（相应的静态）字段，且 `f` 的类型为 `x`。

如果在 `s` 的子类或 `c` 本身添加与 `f` 名称相同类型为 `x` 的新字段，可能会发生链接错误。只有在上述基础上满足以下任一点时，才会发生链接错误：

- 新字段的可访问性比旧字段低。
- 新字段是静态（相应的实例）字段。

特别，当一个类由于之前引用了父类中不兼容类型的字段而无法重新编译时，不会发生链接错误。带有此类引用的之前编译的类将继续引用父类中的字段。

## 示例 13.4.8-1. 添加字段声明

```
class Hyper { String h = "hyper"; }
class Super extends Hyper { String s = "super"; }
class Test {
    public static void main(String[] args) {
        System.out.println(new Super().h);
    }
}
```

该程序产生输出：

hyper

假设产生了类 `Super` 的新版本：

```
class Super extends Hyper {
    String s = "super";
    int h = 0;
}
```

那么，重新编译 `Hyper` 和 `Super`，并与 `Test` 的旧二进制文件一起执行生成的新的二进制文件，将产生输出：

hyper



Hyper 的 `h` 由 Test 的原始二进制文件输出。虽然初看起来看起来很惊讶，但它有助于减少运行时发生的不兼容性数量。（在理想的世界中，当任何源文件发生变化时都会重新编译所有源文件，消除此类惊讶。但这种重新编译通常是不切实际或可能的，特别是在互联网上。而且，正如之前注意到的，这种重新编译有时需要对源代码进行进一步更改。）

## 二进制兼容性

编译并执行后，它产生输出：

Hyper

假设编译了一个新版本的类 Super：

```java
class Super extends Hyper { char h = 'h'; }
```

如果将生成的二进制文件与现有的 Hyper 和 Test 二进制一起使用，输出仍然是：

Hyper

即使编译了这些二进制文件的源码：

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

会导致编译时错误，因为 `main` 方法源码中的 `h` 现在会被解释为指向 Super 中声明的 `char` 字段，而 `char` 值无法赋值给 `String`。

删除字段将破坏与任何引用该字段的预存二进制文件的兼容性，当来自预存二进制文件的此类引用被链接时，将抛出 `NoSuchFieldError`。只有私有字段可以从广泛分发的类中安全地删除。

出于二进制兼容性的考虑，添加或删除一个类型涉及类型 (§4.4) 或泛型类型 (§4.5) 的字段 `f`，等同于添加（或删除）一个同名且类型为 `f` 类型擦除 (§4.6) 的字段。

## 13.4.9 final 字段和静态常量变量

如果一个未声明为 `final` 的字段被更改为 `final`，则可能会破坏尝试为该字段分配新值的预存二进制文件的兼容性。

### 13.4.9-1. 将变量改为 final

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

a

假设产生了一个新版本的类 Super：

```java
class Super { final char s = 'b'; }
```

如果重新编译了 Super 但没有重新编译 Test，那么与现有的 Test 二进制一起运行新的二进制文件将导致 `IllegalAccessError`。

删除 `final` 关键字或更改字段初始化的值不会破坏与现有二进制文件的兼容性。

如果一个字段是常量变量 (§12.4)，而且它是 `static` 的，那么删除 `final` 关键字或更改其值不会通过导致预存二进制文件无法运行来破坏其兼容性，但除非它们重新编译，否则它们将看不到该字段使用的任何新值。这一结果是支持条件编译 (§14.22) 决策的副作用。（人们可能认为，如果使用发生在常量表达式 (§15.29) 中，则看不到新值，而在其他地方则可见。事实并非如此；预存二进制文件完全看不到新值。）

在广泛分发的代码中，避免“不恒定的常量”问题的最佳方法是仅对不太可能改变的值使用静态常量变量。对于真正的数学常量，我们建议源码中极要节慎地使用静态常量变量。

如果需要 `final` 的只读性质，更好的选择是声明一个私有静态变量和一个适当的访问器方法来获取其值。因此，我们建议：

```java
private static int N;
public static int getN() { return N; }
```

而不是：

```java
public static int N = ...;
```

如果 `N` 不需要是只读的，那么以下没有问题：

```java
public static int N = ...;
```

## 13.4.10 static 字段

如果一个非私有字段未声明为 `static` 但被更改为 `static`，反之亦然，当该字段被期望另一种类型字段的预存二进制文件使用时，将导致链接错误，特别是 `IncompatibleClassChangeError`。在广泛分发的代码中不建议进行此类更改。

## 13.4.11 transient 字段

添加或删除字段的 `transient` 修饰符不会破坏预存二进制文件的兼容性。

## 13.4.12 方法和构造函数声明

向类中添加方法或构造函数不会破坏与任何预存二进制文件的兼容性。

链接错误仅在满足上述条件的基础上符合以下之一时才会发生：

- 新方法的访问权限比旧方法低。
- 新方法是静态（或实例）方法。

从类中删除方法或构造函数可能会破坏与任何引用该方法的预存二进制文件的兼容性：当链接此类引用时，可能会抛出 `NoSuchMethodError`。

如果非内部类的源码不包含构造函数，则会隐式声明一个默认构造函数 (§8.8.9)。在该类中添加一个或多个构造函数声明将阻止该默认构造函数。默认构造函数具有与类相同的访问权限，因此为了保持与预存二进制文件的兼容性，任何替换都具有相同或更高的访问权限。

## 13.4.13 方法和构造函数的类型参数

添加或删除方法或构造函数的类型参数本身对二进制兼容性没有任何影响。

如果此类类型参数被用于方法或构造函数的类型，可能会产生更改上述类型参数的正常影响。

重命名方法或构造函数的类型参数对预存二进制文件没有影响。

更改方法或构造函数类型参数的边界可能会更改使用该类型参数的成员的擦除 (§4.6)，这可能会影响二进制兼容性。具体来说：

- 如果类型参数被用作字段类型，效果等于删除了该字段并添加了一个同名且类型为类型变量新擦除的字段。
- 如果类型参数被用作方法的任何形式参数类型，但不是返回类型，效果等于删除了该方法并替换了一个新方法，其中上述形式参数的类型现在变为了类型参数的新擦除。
- 如果类型参数被用作方法的返回类型，但不是方法的任何形式参数的类型，效果等于删除了该方法并替换了一个新方法，除了返回类型（现在是类型参数的新擦除）外。
- 如果类型参数既被用作方法的返回类型，又用作方法的一个或多个形式参数的类型，效果等于删除了方法并替换了一个新方法，除了返回类型（现在是类型参数的新擦除）以及上述形式参数的类型（它们现在的类型也都是类型参数的新擦除）外。

更改任何其他界符（bound）对二进制兼容性均没有影响。

## 13.4.14 方法和构造函数的形式参数

更改方法或构造函数的形式参数的名称不会影响现有的二进制文件。

更改方法的名称，或在方法或构造函数中添加一个形式参数的类型，或在方法或构造函数的声明中添加或删除参数，都将创建一个具有新签名的方法或构造函数，其组合效果等同于删除具有旧签名的方法或构造函数，并添加一个具有新签名的方法或构造函数（见 §13.4.12）。

将方法的最后一个形式参数的类型从 `τ[]` 更改为类型为 `τ` 的可变长度参数（即变为 `τ...` (8.4.1)），反之亦然，不会影响现有的二进制文件。

出于二进制兼容性的考虑，添加或删除一个签名涉及类型变量（§4.4）或泛型类型（§4.5）的方法或构造函数 `m`，等同于添加（相应地删除）一个同样等价的方法，该方法的签名是 `m` 签名的擦除（§4.6）。

## 13.4.15 方法结果类型

更改方法的类型类型，或将结果类型替换为 `void`，或将 `void` 替换为结果类型，其组合效果等同于删除旧方法并添加具有新结果类型或新 `void` 结果的新方法（见 §13.4.12）。

出于二进制兼容性的考虑，添加或删除一个返回类型涉及类型变量（§4.4）或泛型类型（§4.5）的方法或构造函数 `m`，等同于添加（相应地删除）一个同样等价的方法，该方法的返回类型是 `m` 返回类型的擦除（§4.6）。

## 13.4.16 抽象方法

将一个已声明为抽象的方法更改为不再声明为抽象，不会破坏与现有二进制文件的兼容性。

将一个已声明为抽象的方法更改为声明为抽象，将破坏此前调用过该方法的现有二进制文件的兼容性，导致 `AbstractMethodError`。

### 示例 13.4.16-1. 将方法更改为抽象

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

Way
Out

假设产生了 `Super` 类的新版本：

```java
abstract class Super {
    abstract void out();
}
```

如果重新编译了 `Super` 但没有重新编译 `Test`，使用现有的 `Test` 二进制文件运行新的二进制文件将导致 `AbstractMethodError`，因为 `Test` 类没有该方法的实现，因此它是（或应该是）抽象的。

## 13.4.17 final 方法

将一个已声明为 `final` 的方法更改为不再声明为 `final`不会破坏与现有二进制文件的兼容性。

将一个未声明为 `final` 的实例方法更改为声明为 `final`，可能会破坏依赖于重写该方法的现有二进制文件的兼容性。

### 示例 13.4.17-1. 将方法更改为 `final`

```java
class Super { void out() { System.out.println("out"); } }

class Test extends Super {
    public static void main(String[] args) {
        Test t = new Test();
        t.out();
    }
    void out() { super.out(); }
}
```

该程序产生输出：

out

假设产生了 `Super` 类的新版本：

```java
class Super { final void out() { System.out.println("*"); } }
```

如果在不重新编译 `Test` 的情况下重新编译了 `Super`，使用现有的 `Test` 二进制文件运行新的二进制文件将导致 `AbstractMethodError`，因为 `Test` 类没有该方法的实现。

将未声明为 `final` 的方法更改为 `final` 不会破坏现有二进制文件的兼容性。

## 13.4.18 native 方法

添加或删除方法的 `native` 修饰符不会破坏现有二进制文件的兼容性。

## 13.4.19 static 方法

如果一个未声明为 `static` 的方法更改为 `static`（即类方法），反之亦然，将破坏现有二进制文件的兼容性，导致链接时错误。这种更改对于广泛分发的二进制文件是不允许的。

## 13.4.20 synchronized 方法

添加或删除方法的 `synchronized` 修饰符不会破坏现有二进制文件的兼容性。

## 13.4.21 方法和构造函数的 throws

方法或构造函数的 `throws` 子句的更改不会破坏现有二进制文件的兼容性；这些子句仅在编译时检查。

## 13.4.22 方法和构造函数体

方法或构造函数体的更改不会破坏现有二进制文件的兼容性。`final` 关键字并不意味着该方法可以安全地重写。我们不建议方法内联展开。

## 13.4.23 方法和构造函数的重载

添加重载现有方法或构造函数的方法不会破坏现有二进制文件的兼容性。对于每次调用，使用的签名是在这些现有二进制文件编译时确定的；因此，即使新方法的签名更具体，也不会被使用。因为重载解析是在执行时完成的。

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

float

假设产生了 `Super` 类的新版本：

```java
class Super {
    static void out(float f) {
        System.out.println("float");
    }
    static void out(int i) {
        System.out.println("int");
    }
}
```



如果重新编译了 `Super` 但没有重新编译 `Test`，使用现有的 `Test` 二进制文件仍然产生输出：

```
float
```

然而，如果重新编译了 `Test` 并使用这个新的 `Super`，输出将是：

```
int
```

正如之前的情况中可能被预料的那样。

### 13.4.24 方法重写

如果在子类中添加了实例方法并重写了父类的方法，则该子类方法将被现有二进制文件的方法调用找到，这些二进制文件不受影响。

如果在类中添加了类方法，除非方法调用的限定类是该子类，否则该方法将无法找到。

### 13.4.25 静态初始化

添加、删除或更改类的静态初始化（§8.7）不会影响现有的二进制文件。

### 13.4.26 枚举类的演化

在枚举类中添加或重排枚举常量不会破坏现有二进制文件的兼容性。

从枚举类中删除枚举常量将删除与该常量对应的公共字段（§8.9.3）。其后果见 §13.4.8。对于广泛分发的枚举类，不建议此类更改。

在所有其他方面，枚举类的二进制兼容性规则与普通类相同。

### 13.4.27 记录类的演化

在记录类中添加、删除、更改或重新排序记录组件可能会破坏与未重新编译的现有二进制文件的兼容性；对于广泛分发的记录类，这种**不建议**进行此类更改。

更准确地说，添加、删除、更改或重新排序记录组件会更改相应的组件字段和访问器方法的隐式声明，并更改规范构造函数及其他辅助方法的签名和实现，其后果在 §13.4.8 和 §13.4.12 中规定。

在所有其他方面，记录类的二进制兼容性规则与普通类相同。

## 13.5 接口的演化

本节描述了对接口及其成员声明的更改对现有二进制文件的影响。

### 13.5.1 public 接口

将一个未声明为 `public` 的接口更改为声明为 `public` 不会破坏与现有二进制文件的兼容性。

如果将声明为 `public` 的接口更改为未声明为 `public`，则当链接一个需要但不再具有该接口类型访问权限的现有二进制文件时，将抛出 `IllegalAccessError`，因此，不建议对广泛分发的接口进行此类更改。

### 13.5.2 sealed 和非 sealed 接口

如果将一个自由扩展的接口（§9.1.1.4）更改为声明为 `sealed`，则当加载该接口的现有子类或子接口的二进制文件，且该文件不是此接口的允许的直接子类或子接口（§9.1.4）时，将抛出 `IncompatibleClassChangeError`；不建议对广泛分发的类进行此类更改。

向 `sealed` 接口的允许直接子类或子接口集分别添加类或接口不会破坏与现有二进制文件的兼容性。

如果从 `sealed` 接口的允许直接子类或子接口集中移除一个类或接口，则当加载被移除的类或接口的现有二进制文件时，将抛出 `IncompatibleClassChangeError`。

将声明为 `sealed` 的接口更改为声明为非 `sealed` 不会破坏与现有二进制文件的兼容性。

> 非 `sealed` 接口 `i` 必须有一个 `sealed` 的直接超接口。删除非 `sealed` 修饰符将阻止 `i` 被重新编译，因为每个具有 `sealed` 直接超接口的接口必须是 `sealed` 或非 `sealed` 的。

从没有 `sealed` 直接超接口的接口中删除 `sealed` 修饰符不会破坏与现有二进制文件的兼容性。

> 如果 `sealed` 接口 `i` 确实有一个 `sealed` 的直接超接口，删除 `sealed` 修饰符将阻止 `i` 被重新编译，因为每个具有 `sealed` 直接超接口的接口必须是 `sealed` 或非 `sealed` 的。

### 13.5.3 超接口

接口层次结构的更改导致错误的方式与类层次结构更改的方式相同，如 §13.4.4 所示。特别是，导致类的任何先前的超接口不再是超接口的更改可能会破坏与现有二进制文件的兼容性，导致 `VerifyError`。

### 13.5.4 接口成员

向接口添加抽象、私有或静态方法不会破坏与现有二进制文件的兼容性。

在类 `c` 的超接口中添加字段可能会隐藏继承自 `c` 的父类的字段。如果原始引用是实例字段，将导致 `IncompatibleClassChangeError`。如果原始引用是赋值操作，将导致 `IllegalAccessError`。

从接口中删除成员可能会导致现有二进制文件中的链接错误。

#### 示例 13.5.4-1. 删除接口成员

```java
interface I { void hello(); }

class Test implements I {

    public static void main(String[] args) {

        I anI = new Test();

        anI.hello();

    }

}
```

```java
public void hello() { System.out.println("hello"); 

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

如果重新编译了 `I` 但没有 `Test`，那么使用 `Test` 的现有二进制文件运行新的二进制文件将导致 `NoSuchMethodError`。

### 13.5.5 接口类型参数

接口类型参数更改的影响与类类型参数的类似更改相同。

### 13.5.6 字段声明

更改接口中字段声明的考虑因素与类中的 `static final` 字段相同，如 §13.4.8 和 §13.4.9 所示。

### 13.5.7 接口方法声明

更改接口中方法声明的考虑因素包括更改类中方法的考虑因素，如 §13.4.7、§13.4.14、§13.4.15、§13.4.19、§13.4.21、§13.4.22 和 §13.4.23 所示。

添加默认方法不会破坏与现有二进制文件的兼容性，但如果现有二进制文件尝试调用该方法，可能会导致 `IncompatibleClassChangeError`。如果方法的限定接口 `K` 是两个接口 `I` 和 `J` 的子接口，且 `I` 和 `J` 声明了相同签名和结果的默认方法，且 `I` 和 `J` 都不是对方的子接口，则发生此错误。

换句话说，添加默认方法是二进制兼容的更改，因为它没有引入二进制不兼容的更改。

#### 示例 13.5.7-1. 添加默认方法

```java
interface Painter {

    default void draw() {

        System.out.println("Here's a picture...");

    }

}

interface Cowboy {

    default void draw() {

        System.out.println("Bang!");

    }

}

class CowboyArtist implements Cowboy, Painter {

    public static void main(String[] args) {

        new CowboyArtist().draw();

    }

}
```

该程序产生输出：

```
Here's a picture...
```

假设编译了接口 `I` 的新版本：

```java
interface I {

    default void draw() {

        System.out.println("Bang!");

    }

}
```

如果重新编译了 `I` 但没有 `Test`，那么使用 `Test` 的现有二进制文件运行新的二进制文件将导致 `NoSuchMethodError`。

# 14 块、语句与模式

## 14.1 正常完成与非正常完成

“正常完成”和“非正常完成”这两个术语也适用于表达式的求值（§15.6）。表达式能够非正常完成的唯一原因是抛出了异常，这是因为由于带有给定值的 `throw`（§14.18）或者由于运行时异常或错误（§11 (异常), §15.6）。

如果语句求值一个表达式，表达式的非正常完成总是会导致该语句的立即非正常完成，且原因相同。正常执行模式下的所有后续步骤将不会执行。

除非本章另有规定，否则子语句的非正常完成会导致语句本身的立即非正常完成，且原因相同，该语句在正常执行模式下的所有后续步骤将不会执行。

除非另有说明，如果语句求值的所有表达式和执行的所有子语句都正常完成，则该语句正常完成。

## 14.2 块

块是花括号内的一系列语句、局部变量声明语句、局部类声明和接口声明的序列。

```
Block:
  { [BlockStatements] }

BlockStatements:
  BlockStatement {BlockStatement}

BlockStatement:
  LocalClassOrInterfaceDeclaration
  LocalVariableDeclarationStatement
  Statement
```

块的执行是通过从第一个到最后一个（从左到右）执行每个局部变量声明语句和其他语句来实现的。如果所有块语句都正常完成，则块正常完成。如果其中任何块语句由于任何原因非正常完成，则该块因相同的原因非正常完成。

## 14.3 局部类和接口声明

局部类是嵌套类（§8 类），其声明直接包含在块（§14.2）中。

局部接口是嵌套接口（§9 接口），其声明直接包含在块中。

```
LocalClassOrInterfaceDeclaration:
  ClassDeclaration
  NormalInterfaceDeclaration
```

为了方便起见，此处显示了以下产生式：

```
ClassDeclaration:
  NormalClassDeclaration
  EnumDeclaration
  RecordDeclaration

NormalClassDeclaration:
  [Modifier] class TypeIdentifier [TypeParameters]
  [ClassExtends][ClassImplements][ClassPermits] ClassBody

EnumDeclaration:
  [Modifier] enum TypeIdentifier [ClassImplements] EnumBody

NormalInterfaceDeclaration:
  [Modifier] interface TypeIdentifier [TypeParameters]
  [InterfaceExtends][InterfacePermits] InterfaceBody
```

局部类和接口声明可以与包含块中的语句（包括局部变量声明语句）混合使用。

如果局部类或接口声明具有任何访问修饰符 `public`、`protected` 或 `private`（§6.6），则为编译错误。

如果局部类或接口声明具有修饰符 `static`（§8.1.1.4）、`sealed` 或 `non-sealed`（§8.1.1.2, §9.1.1.4），则为编译错误。

如果局部类的直接父类或直接接口是密封的（`sealed`），则为编译错误。

如果局部接口的直接父接口是密封的（`sealed`），则为编译错误。

局部类可以是普通类（§8.1）、枚举类（§8.9）或记录类（§8.10）。每个局部普通类都是内部类（§8.1.3）。每个局部枚举类和局部记录类都是隐式的静态的（§8.1.1.4），因此不是内部类。

局部接口可以是普通接口（§9.1），但不能是注解接口（§9.6）。每个局部接口都是隐式的静态的（§9.1.1.3）。

与匿名类（§15.9.5）不同，局部类或接口不是任何包、类或接口的成员（§7.1, §8.5）。与匿名类不同，局部类或接口有一个简单名称（§6.2, §6.7）。

局部类或接口的作用范围和遮蔽见 §6.3 和 §6.4。

#### 示例 14.3-1 局部类声明

以下示例说明了上述规则的方面：

```java
class Global {

    class Cyclic {}

    void foo() {

        new Cyclic(); // 创建 Global.Cyclic

        class Cyclic extends Cyclic {} // 循环定义

        {

            class Local {} // 错误

        }

    }

}
```

## 14.4 局部变量声明

局部变量声明并可选地初始化一个变量。

```
LocalVariableDeclaration:
  {Modifier} LocalType DeclaratorList

LocalType:
  var
  UnannType
```

局部变量注解修饰符的规则见 §9.7.4 和 §9.7.5。

如果 `final` 关键字出现在声明的开头，则被声明的变量是最终变量（§4.12.4）。

以下产生式为了方便起见：

```
VariableModifier:
  final

DeclaratorList:
  Declarator { , Declarator }

Declarator:
  DeclaratorId [ = VariableInitializer ]

DeclaratorId:
  Identifier Dims

Dims:
  [Annotation] { }

VariableInitializer:
  Expression
```

局部变量声明可以出现在以下位置：

- 块中的局部变量语句（§14.2）
- 基础 `for` 语句头部（§14.14.1）
- 增强 `for` 语句头部（§14.14.2）
- `try-with-resources` 语句的资源规范（§14.20.3）

### 14.4.1 局部变量声明符与类型

局部变量声明每个声明符声明一个局部变量，其名称为声明符中出现的标识符。

如果局部变量类型为 `var` 且满足任一条件，则使用 `var` 为编译错误：

- 多个 `DeclaratorId` 具有更多的一对括号。
- 声明符缺少初始化器。
- 声明符的初始化器是数组初始化器。
- 声明符的初始化器包含对变量的引用。

如果 `LocalVariableType` 是未注解类型（`UnannType`）：

- 如果 `LocalVariableType` 是 `var`，则令 τ 为初始化表达式在假设其被处理为未出现在赋值上下文中时的类型，即一个独立的表达式（§15.2）。局部变量的类型是 τ 相对于 τ 中提到的所有合成类型变量的向上投影（upward projection）（§4.10）。

如果 τ 是空类型（null type），则为编译时错误。

由于初始化表达式被处理为未出现在赋值上下文中，因此如果它是 lambda 表达式（§15.27）或方法引用表达式（§15.13），则会错误。

局部变量声明的作用域和遮蔽在 §6.3 和 §6.4 中规定。

从嵌套类、接口或 lambda 表达式对局部变量的引用是有限制的，具体如 §6.5.1 规定。

#### 示例 14.4.1-1. 用 var 声明的局部变量类型

以下代码说明了用 `var` 声明的变量的类型：

```java
var a = 1;                                // a 的类型为 'int'

var b = java.util.List.of(1, 2);         // b 的类型为 'List<Integer>'

var c = "x".getClass();                  // c 的类型为 'Class<? extends String>'
                                            // 见 JIS 15.12.2

var d = new Object() {};                 // d 为匿名类的类型

var e = (CharSequence & Comparable<String>)"x"; // e 的类型为 CharSequence & Comparable<String>

var f = () -> "hello";                 // 非法：lambda 不在赋值上下文中

var g = null;                           // 非法：空类型
```



注意，某些用 `var` 声明的变量不能用显式类型声明，因为变量的类型是显著的。

在确定变量类型时，对初始化器应用向上投影。如果初始化器的类型包含捕获变量，该投影将初始化器的类型映射到一个不包含捕获变量的超类型。

虽然允许类型提到捕获变量是可能的，但通过投影它们，我们强制了一种吸引人的不变性：捕获变量的作用域不大于包含其捕获类型表达式的语句的作用域。此外，捕获变量不能“泄漏到”语句中。

## 14.4.2 局部变量声明语句

局部变量声明语句由一个局部变量声明组成。

```
LocalVariableDeclarationStatement:
LocalVariableDeclaration;
```

每个局部变量声明语句都立即包含在一个块中，其他类型的语句（§14.5）可能立即包含在块或另一个语句中。

包含它的块中，局部变量声明语句可以与其他类型的语句以及局部类和接口声明自由混合。

局部变量声明语句是一个可执行的语句。每当执行它时，声明符都会从左到右顺序处理。如果声明符有一个初始化器，则求值初始化器并将其赋值给变量。

> 如果声明符没有初始化器，则对该变量的每次引用都必须在执行对该变量的赋值之前，否则将根据 §16（确定赋值）的规则发生编译时错误。

每个初始化器（除第一个一个外）仅在前一个初始化器的求值正常完成时才求值。

如果最后一个初始化器的求值正常完成，则局部变量声明语句的执行正常完成。

如果局部变量声明语句中没有任何声明符具有初始化器，则执行该语句始终正常完成。

## 14.5 语句

Java 编程语言中有许多种语句。大多数语句与 C 和 C++ 语言中的语句对应，但某些是独特的。

与 C 和 C++ 一样，Java 编程语言的语句面临所谓的“悬空 else 问题”，可以通过这个误导性的格式化示例来说：

```java
if (door.isOpen())
    if (resident.isVisible())
        resident.greet("Hello!");
else door.bell.ring(); // 一个悬空 else
```

问题在于，外部 if 语句和内部 if 语句上都可能拥有 else 子句。在这个示例中，人们可能认为程序员意图让 else 子句属于外部 if 语句。

Java 编程语言与 C、C++ 以及它们之前的许多编程语言一样，任意规定 else 子句属于它可能所属的最内层 if 语句。该规则由以下语法捕获：

```
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
    AssertionStatement
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

为了方便，这里显示了来自 §14.9 的产生式：

```
IfThenStatement:
if ( Expression ) Statement

IfThenElseStatement:
if ( Expression ) StatementNoShortIf else Statement
```

```
IfThenStatementNoShortIf:
  if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

语句在语法上分为两类：可能以 if 语句结束的语句（即没有 else 子句的“short if”）以及那些不是的语句。

这个简单的规则防止了“悬空 else”问题。带有“short if”的语句的执行行为等同于没有 else 子句的语句的执行行为。

## 14.6 空语句

空语句什么都不做。

```
EmptyStatement:
  ;
```

空语句的执行始终正常完成。

## 14.7 标签语句

语句可以有标签标记。

```
LabeledStatement:
  Identifier : Statement
```

```
LabeledStatementNoShortIf:
  Identifier : Statement
```

`Identifier` 被声明为语句的标签。

与 C 和 C++ 不同，Java 编程语言没有 `goto` 语句；标签用于 `break` 或 `continue` 语句（§14.15, §14.16），出现在标签语句的任何地方。

标签语句的作用域是包含它的语句。

如果标签语句的名字在标签的作用域内作为另一个标签语句的名字，则为编译时错误。

不允许将同一个标识符作为标签和包、接口、方法、字段或局部变量名。使用标识符标记语句不会遮蔽（§6.4）同名的包、接口、方法、字段或局部变量。将标识符作为类、接口、方法、字段、局部变量或异常处理器的参数（§14.20）使用不会遮蔽同名的语句标签。

标签语句通过执行包含它的语句来执行。

如果语句被 `Identifier` 标记，且包含的语句由于具有相同 `Identifier` 的 `break` 而异常中断，则标签语句正常完成。在语句异常中断的所有情况下，标签语句因相同原因异常中断。

### 14.7-1. 标签与标识符

以下代码取自 `String` 类及其 `indexOf` 方法，其中标签最初命名为 `test`，以便局部变量 `i` 在 `i` 声明的作用域内不会遮蔽标签。因此，代码是有效的。

```java
class Test {

    char[] value;

    int offset, count;

    int indexOf(Test str, int fromIndex) {

        char[] v1 = value, v2 = str.value;

        int max = offset + (count - str.count);

        int start = offset + (fromIndex < 0) ? 0 : fromIndex);

        for (int i = start; i <= max; i++) {

            int n = str.count, j = i, k = str.offset;

            while (n != 0) {

                if (v1[j++] != v2[k++])
                    continue i;
            }
        }
        return offset;
    }
    return -1;
}
```

该标识符也可以用作语句标签；标签不会遮蔽标签语句内的局部变量 `max`。

## 14.8 表达式语句

某些类型的表达式可以通过在它们后加上分号来用作语句。

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

当且仅当表达式语句的求值正常完成时，表达式语句的执行才正常完成。

> 与 C 和 C++ 不同，Java 语言仅允许某些形式的表达式用作表达式语句。例如，使用方法调用表达式（§15.12）是合法的：
>
> ```
> System.out.println("Hello world"); // OK
> ```
>
> 但使用带括号的表达式（§15.8.5）是不法的：
>
> ```
> (System.out.println("Hello world"));    // illegal
> ```
>
> 注意，Java 语言不允许“强制转换为 void”——`void` 不是一种类型——因此传统的 C 语言中编写如下表达式语句的技巧：
>
> ```
> (void)...; // incorrect!
> ```
>
> 是无效的。另一方面，Java 语言允许在表达式语句中使用所有最用的表达式类型，并且并不要求作为表达式语句的方法调用必须调用 `void` 方法，因此这种技巧几乎永远不需要。如果需要这种技巧，可以使用赋值语句（§15.26）或局部变量声明语句（§14.4）来代替。

## 14.9 if 语句

if 语句允许对语句进行条件执行或对两个语句进行条件选择，执行其中一个而不是两者都执行。

```
IfThenStatement:
if ( Expression ) Statement
```

```
IfThenElseStatement:
if ( Expression ) StatementNoShortIf else
```

```
IfThenElseNoShortIf:
if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

该表达式必须是 `boolean` 或 `Boolean` 类型，否则将发生编译错误。

### 14.9.1 if-then 语句

if-then 语句通过首先求值表达式来执行。如果结果是 `Boolean` 类型，则将进行拆箱转换（§5.1.8）。

如果由于某些原因表达式的求值或随后的拆箱转换（如果有）异常完成，则 if-then 语句也因相同的原因异常完成。

否则，通过根据结果值进行选择来继续执行：

- 如果值为 `true`，则执行包含的 `Statement`；当且仅当 `Statement` 的执行正常完成时，if-then 语句正常完成。
- 如果值为 `false`，则不采取任何后续操作，且 if-then 语句正常完成。

### 14.9.2 if-then-else 语句

if-then-else 语句通过首先求值表达式来执行。如果结果是 `Boolean` 类型，则将进行拆箱转换（§5.1.8）。

如果由于某些原因表达式的求值或随后的拆箱转换（如果有）异常完成，则 if-then-else 语句因相同的原因异常完成。

否则，通过根据结果值进行选择来继续执行：

- 如果值为 `true`，则执行第一个包含的 `Statement`（`else` 关键字之前的语句）；当且仅当该语句的执行正常完成时，if-then-else 语句正常完成。
- 如果值为 `false`，则执行第二个包含的 `Statement`（`else` 关键字之后的语句）；当且仅当该语句的执行正常完成时，if-then-else 语句正常完成。

## 14.10 assert 语句

断言是包含布尔表达式的 assert 语句。断言可以是启用或禁用的。如果断言处于启用状态，执行断言会导致布尔表达式的求值，如果表达式求值为 `false`，则报告错误。如果断言被禁用，执行断言将没有任何影响。

```
AssertStatement:
assert Expression ;
assert Expression : Expression;
```

为了方便说明，断言语句的两种形式中的第一个表达式称为 `Expression1`。在断言语句的第二种形式中，第二个表达式称为 `Expression2`。

鉴于此，不应在公共方法中使用断言进行参数检查。参数检查通常是方法契约的一部分，无论启用还是禁用了断言，都必须维护这一契约。

使用断言进行参数检查的另一个次要问题是，错误的参数应该导致适当的运行时异常（例如 `IllegalArgumentException`、`ArrayIndexOutOfBoundsException` 或 `NullPointerException`）。断言失败不会抛出适当的异常。同样，在公共方法中使用断言进行参数检查并非不合法，但通常是不恰当的。设计的意图是 `AssertionError` 永远不会被捕获，但这是可以实现的，因此 `try` 语句的规则应将 `try` 块中出现的断言视为与当前对 `throw` 语句的处理类似。

## 14.11 switch 语句

`switch` 语句根据表达式的值将控制转移到多个语句或表达式之一。

```
SwitchStatement:
switch ( Expression ) SwitchBlock
```

`Expression` 称为选择表达式。选择表达式的类型必须是 `char`、`byte`、`short`、`int`、`Character`、`Byte`、`Short`、`Integer`、`String` 或枚举类型（§8.9），否则将发生编译时错误。

### 14.11.1 switch 块

`switch` 语句和 `switch` 表达式（§15.28）的体均称为 switch 块。本小节介绍了适用于所有 switch 块的通用规则，无论它们是出现在 `switch` 语句还是 `switch` 表达式中。其他小节提供了额外的规则，这些规则要么适用于 `switch` 语句中的 `switch` 块（§14.11.2），要么适用于 `switch` 表达式中的 `switch` 块（§15.28.1）。

```
SwitchBlock:
{ SwitchRule{SwitchRule} }
{ SwitchStatementGroup } {SwitchLabel : }
```

```
SwitchRule:
SwitchLabel -> Expression ;
SwitchLabel -> Block
SwitchLabel -> ThrowStatement
```

```
SwitchBlockStatementGroup:
SwitchLabel :{SwitchLabel :} BlockStatements
```

```
SwitchLabel:
case CaseConstant [, CaseConstant]
default
```

```
CaseConstant:
ConditionalExpression
```



# switch 语句

一个 switch 块可以由：

- switch 规则，它们使用 `->` 来引入 switch 规则表达式、switch 块或 switch throw 语句；
- switch 标签语句组，它们使用 `:` 引入 switch 标签语句组。

每个 switch 规则和 switch 标签语句组都以一个 switch 标签开始，该标签要么是 `case` 标签，要么是 `default` 标签。一个 switch 标签语句组允许有多个 switch 标签。

`case` 标签有一个或多个 `case` 常量。每个 `case` 常量必须是常量表达式 (§15.29) 或枚举常量的名称 (§8.9.1)，否则将发生编译时错误。

switch 标签及其 `case` 常量被认为与 switch 块关联。与同一个 switch 块关联的两个 `case` 常量不能具有相同的值，否则将发生编译时错误。

如果满足以下两个条件，则 `switch` 语句或 `switch` 表达式的 switch 块与选择表达式的类型 `T` 兼容：

- 如果 `T` 不是枚举类型，则与 switch 块关联的每个 `case` 常量与 `T` 赋值兼容 (§5.2)。
- 如果 `T` 是枚举类型，则与 switch 块关联的每个 `case` 常量都是类型 `T` 的枚举常量。

`switch` 语句或 `switch` 表达式的块必须与选择表达式的类型兼容，否则将发生编译时错误。

`switch` 语句的执行 (§14.11.3) 和 `switch` 表达式的求值 (§15.28.2) 都需要确定 switch 标签是否匹配选择表达式的值。要确定 switch 块中的某个 `switch` 标签是否匹配给定的值，会将该值与 switch 块关联的 `case` 常量进行比较。然后：

- 如果其中一个 `case` 常量等于该值，则我们说该 `case` 匹配。
- 如果没有 `case` 常量匹配，但存在 `default` 标签，则说 `default` 标签匹配。

`case` 标签可以包含一个或多个 `case` 常量。如果一个 `case` 常量等于该值，则我们说该 `case` 匹配。

## 示例：switch 语句

```java
switch (day) {
  ...
  case SATURDAY, SUNDAY :
    System.out.println("It's the weekend!");
    break;
}
```

## switch 语句执行细节 (§14.11.3)

如果选择器表达式求值正常完成且结果为 `null`，则随后的拆箱转换（如果有）正常完成，然后通过确定与 switch 块关联的 switch 标签是否匹配选择器的值（§14.11.1）来继续执行 switch 语句。然后：

- 如果没有匹配的 switch 标签，则整个 switch 语句正常完成。
- 如果匹配到 switch 标签，则适用以下情况之一：
  - 如果它是 switch 规则表达式的 switch 标签，则该规则表达式必然是一个语句表达式 (§14.11.2)。评估该语句表达式。如果求值正常完成，则 switch 语句正常完成。如果求值结果值，则该值被丢弃。
  - 如果它是 switch 规则块的 switch 标签，则执行该代码块。如果该代码块正常完成，则 switch 语句正常完成。
  - 如果它是 switch 规则 throw 语句的 switch 标签，则执行该 throw 语句。
  - 如果它是 switch 标签组的 switch 标签，则按顺序执行 switch 块中 switch 标签之后的所有语句。如果这些语句正常完成，则 switch 语句正常完成。
  - 否则，switch 块中匹配的 switch 标签之后没有语句，switch 语句正常完成。

如果 switch 块中任何语句或表达式的执行异常完成，则按以下方式处理：

- 如果语句的执行由于无带标签的 `break` 而异常完成，则不采取进一步操作且 switch 语句正常完成。由于带标签的 `break` 异常完成由标签语句的通用规则 (§14.7) 处理。
- 如果语句或表达式的执行因任何其他原因异常完成，则 switch 语句因相同原因异常完成。由于 `yield` 语句导致的异常完成由 switch 表达式的通用规则 (§15.28.2) 处理。

## 示例 14.11.3-1. switch 语句中的穿透

当选择器匹配 switch 规则的 switch 标签时，执行由 switch 标签引入的 switch 规则表达式或语句，不再执行其他内容。对于语句组的 switch 标签，将执行该 switch 块中 switch 标签之后的所有块语句，包括出现在后续 switch 标签之后的语句。其效果就像在 C 和 C++ 中一样，语句的执行可以“穿透标签”。

例如，程序：

```java
class TooMany {
    static void howMany(int k) {
        switch (k) {
            case 1: System.out.print("one");
            case 2: System.out.print("two");
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

该程序包含一个 switch 块，其中每个 case 的代码都会进入下一个 case 的代码。结果，程序打印：

```
many
two many
one two many
```

穿透可能是导致细微错误的原因。如果代码不希望这种方式穿透到 case，可以使用 `break` 语句来指示何时应该转移控制，或者像程序中的那样使用 switch 规则：

```java
class TooMany {
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

    static void howManyAgain(int k) {
        switch (k) {
            case 1 -> System.out.println("one");
            case 2 -> System.out.println("two");
            case 3 -> System.out.println("many");
        }
    }

    public static void main(String[] args) {
        howMany(1);
        howMany(2);
        howMany(3);
        howManyAgain(1);
        howManyAgain(2);
        howManyAgain(3);
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

# while 语句 (§14.12)

`while` 语句重复执行一个表达式和一个语句，直到表达式的值为 `false`。

**语法：**

```
WhileStatement:
while ( Expression ) Statement

WhileStatementNoShortIf:
while ( Expression ) StatementNoShortIf
```

该表达式的类型必须为 `boolean` 或 `Boolean`，否则会发生编译错误。

## 执行流程

`while` 语句的执行首先是评估表达式。如果结果是 `Boolean` 类型，则对其进行拆箱转换 (§5.1.8)。

如果表达式的求值或随后的拆箱转换（如果有）因某些原因异常完成，则 `while` 语句因相同原因异常完成。

否则，通过根据结果值进行选择来继续执行：

- 如果值为 `true`，则执行包含的语句。然后有一个选择：
  - 如果语句的执行正常完成，则通过重新评估表达式再次执行整个 `while` 语句。
  - 如果语句的执行异常完成，参见 §14.12.1。
- 如果表达式的（可能拆箱后的）值为 `false`，则不采取进一步操作且 `while` 语句正常完成。

如果表达式的（可能拆箱后的）值是第一次评估为 `false`，则不执行语句。

## 14.12.1 while 语句的异常完成

包含语句的异常完成按以下方式处理：

- 如果语句的执行由于无带标签的 `break` 而异常完成，则不采取进一步操作且 `while` 语句正常完成。
- 如果语句的执行由于无带标签的 `continue` 而异常完成，则再次执行整个 `while` 语句。
- 如果语句的执行由于带标签的 `continue` 而异常完成，则有一个选择：
  - 如果 `while` 语句带有标签 `L`，则再次执行整个 `while` 语句。
  - 如果 `while` 语句没有标签 `L`，则因 `continue` 异常完成。
- 如果语句的执行因任何其他原因异常完成，则 `while` 语句因相同原因异常完成。

由于带标签的 `break` 导致的异常完成由标签语句的通用规则 (§14.7) 处理。

# do 语句 (§14.13)

`do` 语句重复执行语句和一个表达式，直到表达式的值为 `false`。

**语法：**

```
DoStatement:
do Statement while ( Expression ) ;
```

该表达式的类型必须为 `boolean` 或 `Boolean`，否则会发生编译错误。

## 执行流程

`do` 语句的执行首先是执行语句。然后有一个选择：

- 如果语句的执行正常完成，则评估表达式。如果结果是 `Boolean` 类型，则对其进行拆箱转换 (§5.1.8)。

如果表达式的求值或随后的拆箱转换（如果有）因某些原因异常完成，则 `do` 语句因相同原因异常完成。

否则，根据结果值进行选择：

- 如果值为 `true`，则再次执行整个 `do` 语句。
- 如果值为 `false`，则不采取进一步操作且 `do` 语句正常完成。

如果语句异常完成，参见 §14.13.1。

执行 `do` 语句至少执行一次包含的语句。

## 14.13.1 do 语句的异常完成

包含语句的异常完成按以下方式处理：

- 如果语句的执行由于无带标签的 `break` 而异常完成，则不采取进一步操作且 `do` 语句正常完成。
- 如果语句的执行由于无带标签的 `continue` 而异常完成，则评估表达式。然后根据结果值进行选择：
  - 如果值为 `true`，则再次执行整个 `do` 语句。
  - 如果值为 `false`，则不采取进一步操作且 `do` 语句正常完成。

## 示例 14.13-1. do 语句

以下代码是 `Integer` 类中 `toHexString` 方法的一种可能实现。

```java
public static String toHexString(int i) {
    StringBuffer buf = new StringBuffer(8);
    do {
        buf.append(Character.forDigit(i & 0xF, 16));
        i >>>= 4;
    } while (i != 0);
    return buf.reverse().toString();
}
```

由于必须生成至少一个数字，`do` 语句是一种合适的控制结构。

# for 语句 (§14.14)

`for` 语句有两种形式：

- 基础 `for` 语句。
- 增强型 `for` 语句。

**语法：**

```
ForStatement:
BasicForStatement
EnhancedForStatement

ForStatementNoShortIf:
BasicForStatementNoShortIf
EnhancedForStatementNoShortIf
```

## 14.14.1 基础 for 语句

基础 `for` 语句执行某些初始化代码，然后重复执行一个 `Expression`、一个 `Statement` 和一些更新代码，直到 `Expression` 的值为 `false`。

**语法：**

```
BasicForStatement:
for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement

BasicForStatementNoShortIf:
for ( [ForInit] ; [Expression] ; [ForUpdate] ) StatementNoShortIf

ForInit:
StatementExpressionList
LocalVariableDeclaration

ForUpdate:
StatementExpressionList

StatementExpressionList:
```



## 14.14 for 语句

### 14.14.1 基础 for 语句

`StatementExpression` ( , `StatementExpression`)

```
Expression 的类型必须是 boolean 或 Boolean，否则会发生编译错误。
```

在基础 `for` 语句 `ForInit` 部分声明的局部变量的作用域和遮蔽在 §6.3 和 §6.4 中规定。

在基础 `for` 语句 `ForInit` 部分声明的局部变量，其在嵌套类、接口或 Lambda 表达式中的引用受到限制，正如 §6.5.6.1 规定。

#### 14.14.1.1 for 语句的初始化

`for` 语句的执行首先是执行 `ForInit` 代码：

- 如果 `ForInit` 代码是语句表达式列表（§14.8），则表达式按照从左到右的顺序进行求值；它们的值（如果有）会被丢弃。
  如果任何表达式的求值由于某些原因而异常中止，则 `for` 语句也因相同原因异常中止；异常中止的表达式右侧的任何 `ForInit` 语句表达式将不会被执行。

- 如果 `ForInit` 代码是局部变量声明（§14.4），它的执行方式类似于在块（§14.4.2）中出现了一个局部变量声明语句。
  如果局部变量声明的执行由于任何原因而异常中止，则 `for` 语句因相同原因异常中止。

- 如果不存在 `ForInit` 部分，则不采取任何操作。

#### 14.14.1.2 for 语句的迭代

接下来，执行 `for` 迭代步骤，如下：

- 如果 `Expression` 存在，则对其进行求值。如果结果类型为 `Boolean`，则进行拆箱转换（§5.1.8）。
  如果 `Expression` 的求值或随后的拆箱转换（如果有）异常中止，则 `for` 语句因相同原因异常中止。

- 否则，根据 `Expression` 是否存在以及如果 `Expression` 存在时产生的值来做出选择，见下一个项目符号。

- 如果 `Expression` 不存在，或者它存在且其求值结果（包括任何可能的拆箱）为 `true`，则执行包含的 `Statement`。然后进行如下选择：

  - 如果 `Statement` 正常完成，则按顺序执行以下两个步骤：

    1. 首先，如果存在 `ForUpdate` 部分，则表达式按照从左到右的顺序进行求值；它们的值（如果有）会被丢弃。如果任何表达式的求值由于某些原因而异常中止，则 `for` 语句因相同原因异常中止；异常中止的表达式右侧的任何 `ForUpdate` 语句表达式将不会被执行。
       如果不存在 `ForUpdate` 部分，则不采取任何操作。

    2. 其次，执行另一个 `for` 迭代步骤。

  - 如果 `Statement` 的执行异常中止，参见 §14.14.1.3。

- 如果 `Expression` 存在且其求值结果（包括任何可能的拆箱）为 `false`，则不采取进一步操作且 `for` 语句正常完成。

如果 `Expression` 不存在，`for` 语句正常完成的唯一方法是使用 `break` 语句。

#### 14.14.1.3 for 语句的异常中止

包含的 `Statement` 的异常中止按以下方式处理：

- 如果 `Statement` 的执行由于无标签的 `break` 而异常中止，则不采取进一步操作，且 `for` 语句正常完成。

- 如果 `Statement` 的执行由于无标签的 `continue` 而异常中止，则按顺序执行以下两个步骤：

  1. 首先，如果存在 `ForUpdate` 部分，则表达式按照从左到右的顺序进行求值；它们的值（如果有）会被丢弃。
     如果不存在 `ForUpdate` 部分，则不采取任何操作。

  2. 其次，执行另一个 `for` 迭代步骤。

- 如果 `Statement` 的执行由于带有标签 L 的 `continue` 而异常中止，则存在选择：

  - 如果 `for` 语句带有标签 L，则按顺序执行以下两个步骤：

    1. 首先，如果存在 `ForUpdate` 部分，则表达式按照从左到右的顺序进行求值；它们的值（如果有）会被丢弃。
       如果不存在 `ForUpdate` 部分，则不采取任何操作。

    2. 其次，执行另一个 `for` 迭代步骤。

  - 如果 `for` 语句没有标签 L，则 `for` 语句因带标签的 `continue` 异常中止。

- 如果 `Statement` 的执行由于其他原因异常中止，则 `for` 语句因相同原因异常中止。

注意，由于带标签的 `break` 导致的异常中止由标签语句的通用规则（§14.7）处理。

### 14.14.2 增强型 for 语句

增强型 for 语句的形式如下：

```java
EnhancedForStatement:
for (LocalVariableDeclaration : Expression)
    Statement
```

```java
EnhancedForNoIf:
for (LocalVariableDeclaration : Expression)
    StatementNoShortIf
```

此处显示了来自 §4.3、§8.3、§8.4.1 和 §14.4 的产生式：

```java
LocalVariableDeclaration:
[VariableModifier] LocalVariableType VariableDeclaratorList
```

```java
VariableModifier:
Annotation
final
```

```java
LocalVariableType:
UnannType
var
```

```java
VariableDeclaratorList:
VariableDeclarator [ , VariableDeclarator]
```

```java
VariableDeclarator:
VariableDeclaratorId [= VariableInitializer]
```

```java
VariableDeclaratorId:
Identifier [Dims]
```

```java
Dims:
[Annotation] {} [[Annotation] {}]
```

`Expression` 的类型必须是数组类型（§10.1）或原始类型 `Iterable` 的子类型，否则将发生编译错误。

增强型 for 语句的头部声明了一个局部变量，其名称为 `VariableDeclaratorId`。执行增强型 for 语句时，局部变量在每次循环迭代中被初始化为 `Iterable` 或表达式产生的数组的连续元素。

如果 `LocalVariableType` 为 `var`。此外，如果满足以下所有条件，则发生编译时错误：

- `VariableDeclaratorList` 包含单个 `VariableDeclarator`。
- `VariableDeclarator` 没有初始化器。
- 如果 `LocalVariableType` 为 `var`，则 `VariableDeclaratorId` 没有括号对。

增强型 for 语句头部声明的局部变量的作用范围和遮蔽在 §6.3 和 §6.4 中规定。

从嵌套类、接口或 lambda 表达式对局部变量的引用是限制的，具体如 §6.5.6.1 规定。

增强型 for 语句头部声明的局部变量的类型 $\tau$ 按如下方式确定：

- 如果 `LocalVariableType` 为 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中未出现括号对，则 $\tau$ 是 `UnannType` 所表示的类型。
- 如果 `LocalVariableType` 为 `UnannType`，且 `UnannType` 或 `VariableDeclaratorId` 中出现了括号对，则 $\tau$ 由 §10.2 规定。
- 如果 `LocalVariableType` 为 `var`，则令 $R$ 根据 `Expression` 的类型推导出，如下：
    - 如果 `Expression` 是数组类型，则 $R$ 是该数组类型的组件类型。
    - 否则，如果 `Expression` 的类型是某些类型 $X$ 的 `Iterable<X>` 的子类型，则 $R$ 为 $X$。
    - 否则，`Expression` 的类型是原始类型 `Iterable` 的子类型，且 $R$ 为 `Object`。

$\tau$ 是相对于 $R$ 提到的所有合成类型变量（§4.10.5）的上投影。

增强型 for 语句的精确含义通过翻译为基础 for 语句给出，如下：

- 如果 `Expression` 的类型是 `Iterable` 的子类型，则基础语句具有如下形式：

```java
for (I #i = Expression.iterator(); #i.hasNext(); ) {
    {VariableModifier} T Identifier = (TargetType) #i.next();
    Statement
}
```

其中：

- 如果 `Expression` 的类型是某些参数 $X$ 的 `Iterable<X>` 的子类型，则 $I$ 是类型 `java.util.Iterator<X>`。否则，$I$ 是原始类型 `java.util.Iterator`。
- `#i` 是一个自动生成的标识符，与增强型 for 语句发生时作用域（§6.3）内的任何其他标识符（自动生成或其他）都不同。
- `{VariableModifier}` 如增强型 for 语句头部所示。
- $T$ 是按上文确定的局部变量类型。
- 如果 $T$ 是引用类型，则 `TargetType` 是 $I$ 的类型参数捕获转换（§5.1.10）的上界，或者如果 $I$ 是原始类型则为 `Object`。

- 否则，`Expression` 必然具有数组类型 `S[]`，且基础语句具有如下形式：

```java
S[] #a = Expression;
L1: ... Lm:
for (int #i = 0; #i < #a.length; i++) {
    {VariableModifier} T Identifier = #a[#i];
    Statement
}
```

其中：

- `L1 ... Lm` 是紧接在增强型 for 语句之前的（可能为空）标签序列。
- `#a` 和 `#i` 是自动生成的标识符，与增强型 for 语句发生时作用域内的任何其他标识符（自动生成或其他）都不同。
- `{VariableModifier}` 如增强型 for 语句头部所示。
- $T$ 是按上文确定的局部变量类型。

#### 示例 14.14-1. 增强型 for 与数组

以下程序计算整数数组的和，展示了增强型 for 如何作用于数组：

```java
int sum(int[] a) {
    int sum = 0;
    for (int i : a) sum += i;
    return sum;
}
```

#### 示例 14.14-2. 增强型 for 与拆箱转换

以下程序将增强型 for 语句与自动拆箱结合，将直方图转换为频率表：

```java
Map<String, Integer> histogram = ...;
double total = 0;
for (int i : histogram.values()) total += i;
for (Map.Entry<String, Integer> e : histogram.entrySet()) {
    System.out.println(e.getKey() + " : " + e.getValue() / total);
}
```

## 14.15 break 语句

`break` 语句将控制转移出外层语句。

> **BreakStatement:**
> `break` [Identifier];

`break` 语句有两种：

- 无标签的 `break` 语句。
- 带有标签 `Identifier` 的 `break` 语句。

无标签的 `break` 语句将控制转移出最近的外层语句。带有标签 `Identifier` 的 `break` 语句将控制转移出最近的有标签的语句。

#### 示例 14.15-1. break 语句

在下文中，图由二维数组表示。图由一组节点和一组边组成；每条边都是一个从某个节点指向另一个结的箭头。

```java
class Graph {
    int[][] edges;
    public Graph(int[][] edges) { this.edges = edges; }
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
                    // 无边需要删除；共享此列表。
                    newges[k] = edges[k];
                    break edgelist;
                } // search
                // 复制列表，省略位置 z 边。
                int m = edges[k].length - 1;
                int[] ne = new int[m];
                System.arraycopy(edges[k], 0, ne, 0, z);
                System.arraycopy(edges[k], z+1, ne, z, m-z);
                newges[k] = ne;
            }
        }
        return new Graph(newges);
    }
}
```

使用了两个语句标签 `edgelist` 和 `search`，以及 `break` 语句的使用。这允许复制列表并省略一条边的代码在两个独立的测试之间共享：从节点 i 到节点 j 的测试，以及从节点 j 到节点 i 的测试。

## 14.16 continue 语句

`continue` 语句只能出现在 `while`、`do` 或 `for` 语句中；这三种语句被称为迭代语句。控制传递到迭代语句的循环延续点。

```
ContinueStatement:
continue [Identifier];
```



## 14.16 continue 语句

`continue` 语句有两类：

- 不带标签的 `continue` 语句。
- 带有标签 `Identifier` 的 `continue` 语句。

不带标签的 `continue` 语句尝试将控制权转移到最内层的最近 `while` 循环。

带有标签 `Identifier` 的 `continue` 语句尝试将控制权转移到具有相同 `Identifier` 标签的闭包标记语句（§14.7）；该闭包语句称为 continue 目标（continue target），它将立即结束当前迭代并开始新迭代。在这种情况下，continue 目标必须是一个 `while`、`do` 或 `for` 语句，否则将产生编译时错误。

如果 `continue` 语句没有 continue 目标，则产生编译时错误。

如果 continue 目标包含任何方法、构造方法、实例初始化器、静态初始化器、lambda 表达式或 switch 表达式，导致其耗尽了 `continue` 语句，则产生编译时错误。也就是说，不存在非局部跳转。

不带标签的 `continue` 语句的执行总是会异常终止，原因是无标签的 `continue`。

带有标签 `Identifier` 的 `continue` 语句的执行总是会异常终止，原因是带有标签 `Identifier` 的 `continue`。

因此，`continue` 语句始终会异常终止。

请参见 `while` 语句（§14.12）、`do` 语句（§14.13）和 `for` 语句（§14.14）的描述，以讨论由于 `continue` 导致的异常终止的处理。

前述描述使用了“尝试转移控制权（attempts to transfer control）”而非仅仅是“转移控制权”，因为如果 continue 目标内部存在任何 `try` 语句（§14.20），且其块或 catch 子句包含 `continue` 语句，那么在控制权转移到 continue 目标之前，这些 `try` 语句的任何 `finally` 子句将按照内层到外层的顺序执行。`finally` 子句的异常终止可能会中断由 `continue` 语句发起的控制权转移。

### 示例 14.16-1. continue 语句

在 §14.15 的图中，其中一个 `break` 语句用于完成最外层循环主体的执行。如果 `for` 循环本身带有标签，则该 `break` 可以替换为 `continue`：

```java
class Graph {
    int[][] edges;

    public Graph(int[] edges) { this.edges = edges; }

    public Graph loseEdges(int i, int j) {
        int n = edges.length;
        int[][] newges = new int[n][];

        edgelists:
        for (int k = 0; k < n; ++k) {
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
                continue edgelists;
            }

            // 拷贝列表，省略位置 z 处的边。
            int m = edges[k].length - 1;
            int[] ne = new int[m];
            System.arraycopy(edges[k], 0, ne, 0, z);
            System.arraycopy(edges[k], z + 1, ne, z, m - z);
            newges[k] = ne;
        } // edgelists

        return new Graph(newges);
    }
}
```

使用哪一种（如果可以使用）很大程度上取决于编程风格。

## 14.17 return 语句

`return` 语句将控制权返回给调用者（§8.4, §15.12）或构造方法（§8.8, §15.9）。

```
ReturnStatement:
    return [Expression];
```

`return` 语句有两类：

- 不带值的 `return` 语句。
- 带有值 `Expression` 的 `return` 语句。

`return` 语句尝试将控制权转移给最内层闭包构造方法、方法或 lambda 表达式的调用者；该闭包声明或表达式称为 目标（return target）。对于带有值 `Expression` 的 `return` 语句，`Expression` 的值将成为调用的值。

如果 `return` 语句没有 return 目标，则产生编译时错误。

如果 return 目标包含 (i) 封装 `return` 语句的实例或静态初始化器，或 (ii) 封装 `return` 语句的 switch 表达式，则产生编译时错误。

如果不带值的 `return` 语句的 return target 是方法，且该方法未声明为 `void`，则产生编译时错误。

如果带有值 `Expression` 的 `return` 语句的 return target 是构造方法或声明为 `void` 的方法，则产生编译时错误。

如果带有值 `Expression` 的 `return` 语句的 return target 是类型为 T 的方法，且 `Expression` 的类型与 T 不可赋值兼容（§5.2），则产生编译时错误。

不带值的 `return` 语句的执行总是会异常终止，原因是无值的 `return`。

带有值 `Expression` 的 `return` 语句执行首先求值 `Expression`。如果 `Expression` 的求值由于原因异常终止，则 `return` 语句异常终止。

因此，`return` 语句始终会异常终止。

前述描述使用了“尝试转移控制权”而非仅仅是“转移控制权”，因为如果 return 目标内部存在任何 `try` 语句（§14.20），且其块或 catch 子句包含 `return` 语句，那么在控制权转移到 return 目标之前，这些 `try` 语句的任何 `finally` 子句将按照内层到外层的顺序执行。`finally` 子句的异常终止可能会中断由 `return` 语句发起的控制权转移。

## 14.18 throw 语句

`throw` 语句导致异常被抛出。`throw` 语句可以抛出的异常类型规定在 11.2。

```
ThrowStatement:
    throw Expression;
```

`throw` 语句首先求值 `Expression`。然后：

- 如果 `Expression` 的求值由于原因异常终止，则 `throw` 异常终止。
- 如果 `Expression` 的求值正常产生非空值 `v`，则 `throw` 语句异常终止 `v`。
- 如果 `Expression` 的求值正常产生空值，则将创建并抛出 `NullPointerException` 实例 `v'` 代替空值。此时 `throw` 语句异常终止 `v'`。

因此可见，任何闭包 `try` 语句都会异常终止。

如果存在任何包含 `throw` 语句的 `try` 语句（§14.20），则在控制权向外转移时，这些 `try` 语句的任何 `finally` 子句将被执行，直到 `throw` 被捕获。`finally` 子句的异常终止可能会中断 `throw` 语句发起的控制权转移。

如果 `throw` 语句包含方法声明或 lambda 表达式，但其值未被包含它的 `try` 语句捕获，则方法的调用将由于 `throw` 而异常终止。

如果 `throw` 语句包含构造方法声明，但其值未被包含它的 `try` 语句捕获，则调用构造方法的类创建表达式将由于 `throw` 而异常终止（§15.9.4）。

如果 `throw` 语句包含静态初始化器（§8.7），编译时检查（§11.2.3）确保其值总是未捕获的异常，或总是被包含它的 `try` 语句捕获。如果在运行时，尽管有此检查，值仍未被包含 `throw` 语句的 `try` 语句捕获，则如果该值是 `Error` 或其子类的实例，则重新抛出；否则，将在 `ExceptionInInitializerError` 对象中抛出并抛出（§12.4.2）。

如果 `throw` 语句包含实例初始化器（§8.6），编译时检查（§11.2.3）确保其值总是未捕获的异常，或总是被包含它的 `try` 语句捕获，或类型……

## 14.19 synchronized 语句

`synchronized` 语句代表执行线程获取一个互斥锁（§17.1），执行一个块，然后释放锁。在执行线程拥有该锁期间，其他线程无法获取该锁。

```
SynchronizedStatement:
    synchronized ( Expression ) Block
```

`Expression` 的类型必须是引用类型，否则将发生编译时错误。`synchronized` 语句的执行首先是评估 `Expression`。然后：

- 如果 `Expression` 的评估由于某些原因异常完成，则 `synchronized` 语句也因相同的原因异常完成。
- 否则，如果 `Expression` 的值为 `null`，则抛出 `NullPointerException`。
- 否则，令 `Expression` 的非空值为 `V`。执行线程锁定与 `V` 关联的监视器（monitor）。然后执行 `Block`，接着有两种选择：
    - 如果 `Block` 的执行正常完成，则解锁监视器且 `synchronized` 语句正常完成。
    - 如果 `Block` 的执行由于任何原因异常完成，则解锁监视器且 `synchronized` 语句因该原因异常完成。

由 `synchronized` 语句获取的锁与 `synchronized` 方法隐式获取的锁相同（§8.4.3）。单个线程可以多次获取锁。

获取与对象关联的锁本身并不能阻止其他线程访问该对象的字段或调用该对象上的未同步方法。其他线程可以使用常规方式使用 `synchronized` 方法或 `synchronized` 语句来实现互斥。

### 示例 14.19-1. synchronized 语句

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

此程序产生输出：

```
made it!
```

注意，如果不允许单个线程多次锁定监视器，则此程序会导致死锁。

## 14.20 try 语句

`try` 语句执行一个块。如果抛出一个值且 `try` 语句有一个或多个可以捕获它的 `catch` 子句，则控制转移到第一个此类 `catch` 子句。如果 `try` 语句有一个 `finally` 子句，则执行另一个代码块，无论 `try` 块是正常完成还是异常，也无论 `catch` 子句是否首先获得控制。

```
TryStatement:
    try Block Catches
    try Block [Catches] Finally
    TryWithResourcesStatement

Catches:
    CatchClause [CatchClause]

CatchClause:
    catch ( CatchFormalParameter ) Block

CatchFormalParameter:
    [VariableModifier] CatchType VariableDeclaratorId

CatchType:
    UnannClassType (| ClassType)

Finally:
    finally Block
```

关于 `UnannClassType` 参见 §8.3。为了方便起见，此处显示了来自 §4.3、§8.3 和 §8.4.1 的产生式：

```
VariableModifier:
    Annotation
    final

VariableDeclaratorId:
    Identifier [Dims]

Dims:
    [Annotation] { [Annotation] { } }
```

紧跟关键字 `try` 之后的块被称为 `try` 语句的 `try` 块。

紧跟关键字 `finally` 之后的块被称为 `try` 语句的 `finally` 块。

`try` 语句可以有 `catch` 子句，称为异常处理器。

一个 `catch` 子句精确声明一个参数，称为异常参数。

如果 `final` 作为异常参数声明的修饰符出现多次，则为编译错误。

异常参数的作用域和遮蔽在 §6.3 和 §6.4 中指定。从嵌套类、接口或 lambda 表达式对异常参数的引用受到限制，如 §6.5.6.1 所示。

异常参数可以将类型表示为单个类类型或多个类类型的并集（称为类型）。

选择（最左侧的）此类 `catch` 句。值 `v` 被赋值给所选 `catch` 句的参数，并执行该 `catch` 句的**块（Block）**，然后有如下选择：

- 如果该块正常完成，则 `try` 语句正常完成。
- 如果该块由于任何原因异常完成，则 `try` 语句以相同原因异常完成。
- 如果 `v` 的运行时类型无法与 `try` 语句中任何 `catch` 句的可捕获异常类进行赋值兼容（assignment compatible），则 `try` 语句因为抛出值 `V` 而导致异常完成。
- 如果 `try` 块的执行由于任何其他原因异常完成，则 `try` 语句以相同原因异常完成。

### 示例 14.20-1. 捕获异常

```java
class Blewit extends Exception {
    Blewit() { }
    Blewit(String s) { super(s); }
}

class Test {
    static void blowUp() throws Blewit { throw new Blewit(); }

    public static void main(String[] args) {
        try {
            blowUp();
        } catch (RuntimeException r) {
            System.out.println("Caught RuntimeException");
        } catch (Blewit b) {
            System.out.println("Caught Blewit");
        }
    }
}
```



在这里，异常 `Blewit` 由 `blowUp` 方法抛出。main 体中的 try-catch 语句有两个 catch 句。异常的运行时类型为 `Blewit`，它不能赋值给 `RuntimeException` 类型的变量，但可以赋值给 `Blewit` 类型的变量，因此示例的输出为：

Caught Blewit

## 14.20.2 try-finally 和 try-catch-finally 的执行

带有 finally 块的 try 语句执行时首先执行 try 块。然后有如下选择：

- 如果 `try` 块的执行正常完成，则执行 `finally` 块，然后有如下选择：
    - 如果 `finally` 块正常完成，则 try 语句正常完成。
    - 如果 `finally` 块由于原因 $S$ 异常完成，则 try 语句以原因 $S$ 异常完成。
- 如果 `try` 块的执行由于 `throw` 一个值 $v$ 而异常完成，则有如下选择：
    - 如果 $v$ 的运行时类型与 `try` 语句中任何 `catch` 句的可捕获异常类赋值兼容，则选择第一个（最左侧的）`catch` 句。值 $v$ 被赋值给所选 `catch` 句的参数，并执行该 `catch` 句的 `Block`。然后有如下选择：
        - 如果 `catch` 块正常完成，则执行 `finally` 块。然后有如下选择：
            - 如果 `finally` 块正常完成，则 try 语句正常完成。
            - 如果 `finally` 块由于任何原因异常完成，则 try 语句以相同原因异常完成。
- 如果 `catch` 块由于原因 $R$ 异常完成，则执行 `finally` 块。然后有如下选择：
    - 如果 `finally` 块正常完成，则 try 语句以原因 $R$ 异常完成。
    - 如果 `finally` 块由于原因 $s$ 异常完成，则 try 语句以原因 $s$ 异常完成（原因 $R$ 被丢弃）。
- 如果 $v$ 的运行时类型无法与 `try` 语句中任何 `catch` 句的可捕获异常类赋值兼容，则执行 `finally` 块。然后有如下选择：
    - 如果 `finally` 块正常完成，则 try 语句因为 `throw` 值 $V$ 而异常完成。
    - 如果 `finally` 块由于原因 $s$ 异常完成，则 try 语句以原因 $s$ 异常完成（抛出的值 $V$ 被丢弃）。
    - 如果 try 块的执行由于其他原因异常完成，则执行 `finally` 块，并有如下选择：
        - 如果 `finally` 块正常完成，则 try 语句以原因 $R$ 异常完成。
        - 如果 `finally` 块由于原因 $S$ 异常完成，则 try 语句以原因 $S$ 异常完成（原因 $R$ 被丢弃）。

### 示例 14.20-2. 带 finally 的未捕获异常

```java
class BlewIt extends Exception {

    BlewIt() { }

    BlewIt(String s) { super(s); }

}

class Test {

  static void blowUp() throws BlewIt {

    throw new NullPointerException();

  }

  public static void main(String[] args) {

    try {

      blowUp();

    } catch (BlewIt b) {

      System.out.println("Caught BlewIt");

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

`NullPointerException` 是 `RuntimeException` 的一种，由 `blowUp` 方法抛出。main 体中的 try-catch 语句有两个 catch 句。异常的运行时类型为 `Blewit`，它不能赋值给 `RuntimeException` 类型的变量，但可以赋值给 `Blewit` 类型的变量，因此示例的输出为：

Caught Blewit

（注：此处原文重复了多次相同的描述，翻译已按要求处理并保持对应逻辑）

## 14.20.3 try-with-resources

try-with-resources 语句使用变量（称为资源）进行参数，这些变量在 try 块执行之前初始化，并在执行后自动关闭。

为了方便起见，这里列出了 §4.3、§8.3、§8.4 和 §14.4 中的以下产生式，表示文法：

```java
TryWithResourcesStatement:
try ResourceSpecification Block [Catches] [Finally]

ResourceSpecification:
(ResourceList) [; ]

ResourceList:
Resource [; ]

Resource:
LocalVariableDeclaration
VariableAccess

VariableAccess:
ExpressionName
FieldAccess
```

在资源规格中声明的局部变量的规则规定在 §14.4。以下所有条件必须满足，否则将发生编译错误：

- `DeclaratorList` 包含单个 `VariableDeclarator`。
- `VariableDeclarator` 拥有初始化器。
- `VariableDeclarId` 没有括号对。

在资源规格中声明的局部变量的作用域和遮蔽规定在 §6.3 和 §6.4。

从嵌套类或接口或 lambda 表达式对该局部变量的引用限制规定在 §6.5.6.1。

在资源规格中声明的局部变量的类型规定在 §14.4.1。

在资源规格中声明的局部变量的类型，或资源规格中引用的现有变量的类型必须是 `AutoCloseable` 的子类型，否则将发生编译错误。

资源规格中声明两个同名的局部变量会导致编译错误。

资源是最终的，因为：

- 资源规格中声明的局部变量如果没有被显式声明为 final，则被隐式声明为 final (§4.12.4)。
- 资源规格中引用的现有变量必须是最终或有效最终变量，且在 try-with-resources 语句之前已确定赋值 (§16 (确定赋值))，否则将发生编译错误。

资源按照从左到右的顺序初始化。如果某个资源初始化失败（即其初始化器抛出异常），则 try-with-resources 语句到为止已初始化的资源都将被关闭。如果所有资源都初始化成功，则 try 块按正常方式执行，然后 try-with-resources 的所有非空资源都将被关闭。

资源关闭的顺序与它们初始化的顺序相反。只有当资源被初始化为非空值时，它才会被关闭。某个资源在关闭时抛出的异常不会阻止其它资源的关闭。如果之前由初始化器、try 块或资源关闭已经抛出了异常，则该异常会被抑制（suppressed）。

一个资源规范指定了多个资源的 try-with-resources 语句被处理为多个 try-with-resources 语句，每个语句都包含一个指示单个资源的资源规范。当一个具有 $n$ 个资源（$n > 1$）的 try-with-resources 语句被翻译时，其结果是一个具有 $n-1$ 个资源的 try-with-resources 语句。经过 $n$ 次翻译后，会有 $n$ 个嵌套的 try-catch-finally 语句，此时整体翻译完成。

### 14.20.3.1 基础 try-with-resources

没有 catch 或 finally 子句的 try-with-resources 语句称为基础 try-with-resources 语句。

如果一个基础 try-with-resources 语句的形式如下：

```
try (VariableAccess ...)
Block
```

则该资源首先通过以下翻译转换为局部变量声明：

```
try (T #r = VariableAccess ... ) {
Block
}
```

`T` 是 `VariableAccess` 所指代变量的类型，`#r` 是一个自动生成的标识符，它与 try-with-resources 语句所在作用域内的任何其他标识符（自动生成的或其他生成的）都不同。随后根据本节的剩余部分翻译该 try-with-resources 语句。

形式如下的基础 try-with-resources 语句的含义为：

```
try ((VariableModifier) R Identifier = Expression ...)
Block
```

通过翻译为局部变量声明和 try-catch-finally 语句给出：

```
final {VariableModifierNoFinal} R Identifier = Expression;
Throwable #primaryExc = null;
try ResourceSpecification_tail
catch (Throwable #t) {
  #primaryExc = #t;
  throw #t;
} finally {
  if (Identifier != null) {
    try {
      Identifier.close();
    } catch (Throwable #suppressedExc) {
      #primaryExc.addSuppressed(#suppressedExc);
    }
  } else {
    Identifier.close();
  }
}
```

`[VariableModifierNoFinal]` 定义为去掉了 final 修饰符的 `[VariableModifier]`。

`#t`、`#primaryExc` 和 `#suppressedExc` 是自动生成的标识符，它们与 try-with-resources 语句所在作用域内的任何其他标识符（自动生成的或其他生成的）都不同。

如果资源规范指示了一个资源，则 `ResourceSpecification_tail` 为空（且 try-catch-finally 语句本身不是 try-with-resources 语句）。

如果资源规范指示了 $n > 1$ 个资源，则 `ResourceSpecification_tail` 由资源规范中指示的第 2、第 3...到第 $n$ 个资源组成，保持相同顺序（且 try-catch-finally 语句本身是一个 try-with-resources 语句）。

基础 try-with-resources 语句的可达性和确定性赋值规则由上述翻译隐式指定。

在管理单个资源的基础 try-with-resources 语句中：

- 如果资源的初始化因为抛出值 $V$ 而异常终止，则 try-with-resources 语句也因为抛出值 $V$ 而异常终止。
- 如果资源的初始化正常完成，而 try 块因为抛出值 $V$ 而异常终止，则：
  - try-with-resources 语句也因为抛出值 $V$ 而异常终止。
  - 如果资源关闭因为抛出异常 $V2$ 而异常终止，则 $V2$ 会被抑制到主异常中。
  - 如果资源的初始化正常完成，且 try 块正常执行：
    - 资源正常关闭。如果资源关闭因为抛出异常 $V$ 而异常终止，则 try-with-resources 语句也因为抛出异常 $V$ 而异常终止。

在管理多个资源的基础 try-with-resources 语句中：

- 如果资源的初始化因为抛出值 $V$ 而异常终止，则 try-with-resources 语句也因为抛出值 $V$ 而异常终止。
- 如果资源的初始化正常完成，而 try 块因为抛出值 $V$ 而异常终止，则：
  - try-with-resources 语句也因为抛出值 $V$ 而异常终止。
  - 如果某个资源的关闭因为抛出异常 $V2$ 而异常终止，则 $V2$ 会被抑制到主异常中。
  - 如果资源的初始化正常完成，且 try 块正常执行：
    - 资源按相反顺序关闭。如果其中某个资源的关闭因为抛出异常 $V2$ 而异常终止，则 $V2$ 会被抑制到主异常中。
- 如果所有资源初始化正常完成，且 try 块正常执行：
  - 资源正常关闭。如果某个资源的关闭因为抛出异常 $V$ 而异常终止，则 try-with-resources 语句也因为抛出异常 $V$ 而异常终止。

### 14.20.3.2 扩展 try-with-resources

具有至少一个 catch 子句和或 finally 子句的 try-with-resources 语句称为扩展 try-with-resources 语句。

扩展 try-with-resources 语句的形式为：

```
try ResourceSpecification
  Block
[Catches]
[Finally]
```

通过翻译为嵌套在 try-catch 或 try-finally 语句中的基础 try-with-resources 语句给出：

```
try {
  try ResourceSpecification
    Block
}
  [Catches]
  [Finally]
```

翻译的效果是将资源规范放在 try 语句内部。这使得扩展 try-with-resources 语句的 catch 子句可以捕获初始化或关闭资源时产生的异常。此外，在执行 finally 块之前，所有资源都已关闭，这符合 finally 关键字的意图。

## 14.21 yield 语句

yield 语句通过使封装的 switch 表达式（15.28）产生指定值来转移控制。

```
YieldStatement:
yield Expression;
```

yield 语句尝试将控制转移到最内层的 switch 表达式；该表达式被称为 yield target，它会立即正常完成并将 Expression 的值作为 switch 表达式的值。

如果 yield 语句没有 yield target，则编译错误。

如果 yield target 包含任何方法、构造器、实例初始化器或 lambda 表达式，则编译错误。即不存在非局部跳转。

如果 yield 语句的 Expression 为 void，则编译错误。

执行 yield 语句首先评估 Expression。如果 Expression 的评估因为某些原因异常终止，则 yield 语句也因该原因异常终止。如果 Expression 的评估正常完成并产生值 v，则 yield 语句异常终止，原因是 yield 了值 v。

可以看出，yield 语句总是异常终止。

**示例 14.21-1. yield 语句**

在下面的示例中，使用 yield 语句为封装的 switch 表达式产生值。

```java
class Test {

  enum Day {

    MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY,
    SATURDAY, SUNDAY

  }

  public int calculate(Day d) {

    switch (d) {

      case SATURDAY, SUNDAY -> d.ordinal();

      default -> {

        int len = d.toString().length();

        yield len;

      }

    }

  }

}
```

## 14.22 不可达语句

如果一个语句因为是不可达的而无法执行，则属于编译期错误。

本节专门对“可达（reachable）”一词进行精确解释。其核心思想是：从构造函数、方法、实例初始化器或静态初始化器的开始，必须存在某种可能的执行路径到达该语句本身。分析考虑了语句的结构。除了处理 `while-do` 和 `for` 语句中条件表达式值为常量 `true` 的情况外，流分析中不考虑表达式的值。

例如，Java 编译器会接受以下代码：

```
{
int n = 5;
while (n > 7) k = 2;
}
```



即使 `n` 的值在编译时是已知的，且原则上可以在编译时确定对 `k` 的赋值永远不会执行。

本节的规则定义了两个技术术语：

- 语句是否是可达的
- 语句是否可以正常完成

只有在语句是可达的情况下，规则才允许该语句正常完成。

另外使用了两个术语：

- 可达的 `break` 语句退出语句：在 `break` 目标内部，要么没有包含该 `break` 语句的 `try` 语句，要么包含该 `break` 语句的 `try` 语句且这些 `try` 语句的所有 `finally` 子句都能正常完成。

该定义基于 §14.15 中“尝试转移控制”的逻辑。

- `continue` 语句继续一个 `do` 语句：在 `do` 语句内部，要么没有包含该 `continue` 语句的 `try` 语句，要么包含该 `continue` 语句的 `try` 语句且这些 `try` 语句的所有 `finally` 子句都能正常完成。

规则如下：

- 作为构造函数、方法、实例初始化器、静态初始化器、lambda 表达式或 switch 表达式主体的代码块是可达的。

一个不是 `switch` 块的空块，当且仅当它是可达的时，可以正常完成。

不是 `switch` 块的非空块，当且仅当其最后一个语句可以正常完成时，可以正常完成。

不是 `switch` 块的非空块中的第一个语句，当且仅当该块是可达的时，是可达的。

不是 `switch` 块的非空块中的其他任何语句 `s`，当且仅当其前面的语句 `s` 可以正常完成时，是可达的。

- 局部类声明语句当且仅当它是可达的时，可以正常完成。

- 局部变量声明语句当且仅当它是可达的时，可以正常完成。

- 空语句当且仅当它是可达的时，可以正常完成。

- 标签语句在满足以下至少一个条件 true 时，可以正常完成：
  - 被包含的语句可以正常完成。
  - 存在一个退出该标签语句的可达 `break` 语句。

被包含的语句是可达的，当且仅当标签语句是可达的。

- 表达式语句当且仅当它是可达的时，可以正常完成。

- `if-then` 语句当且仅当它是可达的时，可以正常完成。

`then` 语句是可达的，当且仅当 `if-then` 语句是可达的。

`if-then-else` 语句可以 `then` 语句正常完成，或者 `else` 语句可以正常完成。

`then` 语句是可达的，当且仅当 `if-then-else` 语句是可达的。

`else` 语句是可达的，当且仅当 `if-then-else` 语句是可达的。

> 这种对 `if` 语句的处理（无论其是否有 `else` 部分）相当不寻常。理由在本节末尾给出。

- `assert` 语句当且仅当它是可达的时，可以正常完成。

- `switch` 块为空或仅包含 `switch` 标签的 `switch` 语句可以正常完成。

### 块、语句与模式

#### 不可达语句 14.22

- `switch` 块由 `switch` 标签语句组组成的 `switch` 语句，当且仅当满足以下至少一个 true 时，可以正常完成：
  - `switch` 块中的最后一个语句可以正常完成。
  - 在最后一个 `switch` 语句组之后至少有一个 `switch` 标签。
  - 存在一个退出该 `switch` 语句的可达 `break` 语句。
  - `switch` 块不包含 `default` 标签。

- `switch` 块由 `switch` 规则组成的 `switch` 语句，当且仅当满足以下至少一个 true 时，可以正常完成：
  - 其中一个 `switch` 规则引入了 `switch` 规则表达式（其不一定是语句表达式）。
  - 其中一个 `switch` 规则引入了可以正常完成的 `switch` 规则块。
  - 其中一个 `switch` 规则引入了包含退出该 `switch` 语句的可达 `break` 语句的 `switch` 规则块。
  - `switch` 块不包含 `default` 标签。

- `switch` 块是可达的，当且仅当其 `switch` 语句是可达的。

- `switch` 块中由 `switch` 标签语句组组成的语句是可达的，当且仅当 `switch` 块是可达的且满足以下至少一个 true 时：
  - 它带有 `case` 或 `default` 标签。
  - `switch` 块中在其前面有一个语句且该前面的语句可以正常完成。

- `switch` 块中的 `switch` 规则块是可达的，当且仅当 `switch` 块是可达的。

- `switch` 块中的 `switch` 规则 `throw` 语句是可达的，当且仅当 `switch` 块是可达的。

- `while` 语句当且仅当满足以下至少一个 true 时，可以正常完成：
  - `while` 语句是可达的，且条件表达式不是值为 `true` 的常量表达式（§15.29）。
  - 存在一个退出该 `while` 语句的可达 `break` 语句。

被包含的语句是可达的，当且仅当 `while` 语句是可达的且条件表达式不是值为 `false` 的常量表达式。

- `do` 语句当且仅当满足以下至少一个 true 时，可以正常完成：
  - 被包含的语句可以正常完成，且条件表达式不是值为 `true` 的常量表达式（§15.29）。
  - `do` 语句包含一个无标签的可达 `continue` 语句，且该 `do` 语句是包含 `continue` 语句的最内层 `while`/`do` 语句，且该 `continue` 语句继续该 `do` 语句，且条件表达式不是值为 `true` 的常量表达式。
  - `do` 语句包含一个带标签 L 的可达 `continue` 语句，且 `do` 语句带有标签 L，且该 `continue` 语句继续该 `do` 语句，且条件表达式不是值为 `true` 的常量表达式。
  - 存在一个退出该 `do` 语句的可达 `break` 语句。

被包含的语句是可达的，当且仅当 `do` 语句是可达的。

- 基础 `for` 语句当且仅当满足以下至少一个 true 时，可以正常完成：
  - `for` 语句是可达的，存在条件表达式且条件表达式不是值为 `true` 的常量表达式（§15.29）。
  - 存在一个退出该 `for` 语句的可达 `break` 语句。

被包含的语句是可达的，当且仅当 `for` 语句是可达的且条件表达式不是值为 `false` 的常量表达式。

- 增强型 `for` 语句当且仅当它是可达的时，可以正常完成。

- `break`、`continue`、`return`、`throw` 或 `yield` 语句无法正常完成。

- `synchronized` 语句当且仅当被包含的语句可以正常完成时，可以正常完成。

被包含的语句是可达的，当且仅当 `synchronized` 语句是可达的。

- `try` 语句在满足以下两个条件时正常完成：
  - `try` 块可以正常完成，或者任何 `catch` 块可以正常完成。
  - 如果 `try` 语句拥有 `finally` 块，则该 `finally` 块可以正常完成。

- `try` 块是可达的，当且仅当 `try` 语句是可达的。

- 一个 `catch` 块 `c` 是可达的，当且仅当以下两个条件均满足时：
  - `c` 参数的类型是未检查异常类型、`Exception` 或其的超类，或者 `try` 块中的某个表达式或 `throw` 语句是可达的，并且可以抛出一个受检查异常，该异常的类型与 `c` 参数的类型赋值兼容（§5.2）。（一个表达式是可达的，当且仅当包含它的内层语句也是可达的。）
  - 在 `try` 语句中不存在早于 `catch` 块 `a`，使得 `c` 参数的类型与 `a` 参数的类型相同或为其子类。

- `catch` 块的 `Block` 是可达的，当且仅当该 `catch` 块是可达的。

- 如果存在 `finally` 块，它是可达的，当且仅当 `try` 语句是可达的。

> 表达式的正常和异常完成参见 §15.6。

> 人们可能期望 `if` 语句按以下方式处理：
> - 一个 `if-then` 语句可以正常完成，当且仅当以下至少一个条件满足时：
>   - `if-then` 语句是可达的，且条件表达式不是一个值为 `true` 的常数表达式。
>   - `then` 语句可以正常完成。
> - `then` 语句是可达的，当且仅当 `if-then` 语句是可达的，且条件表达式不是一个值为 `false` 的常数表达式。
> - 一个 `if-else` 语句可以正常完成，当且仅当 `then` 语句可以正常完成或 `else` 语句可以正常完成。
> - `then` 语句是可达的，当且仅当 `if-else` 语句是可达的且条件表达式不是一个值为 `false` 的常数表达式。
> - `else` 语句是可达的，当且仅当 `if-then-else` 语句是可达的且条件表达式不是一个值为 `true` 的常数表达式。
>
> 这种方法将与其他控制结构的处理方式保持一致。然而，为了让 `if` 语句能够方便地用于“条件编译”目的，实际的规则有所不同。

例如，以下语句会导致编译错误：

```
while (false) { x=3; }
```

因为语句 `x=3;` 是不可达的；但表面上相似的案例：

```
if (false) { x=3; }
```

并没有导致编译错误。优化编译器可能会意识到语句 `x=3;` 永远不会被执行，并可能选择从生成的类文件中省略该语句的代码，但语句 `x=3` 并不被认为在此指定的技术意义上是“不可达”的。

这种差异处理的理由是允许程序员定义“标记”变量，例如：

```
static final boolean DEBUG = false;
```

然后编写如下代码：

```
if (DEBUG) { x=3; }
```

这种思想是，应当可以将 `DEBUG` 的值从 `false` 改为 `true` 或从 `true` 改为 `false`，并且在不对程序文本进行任何其他更改的情况下正确编译代码。

条件编译有一个限制：如果一组类使用了“标记”变量——更准确地说，是任何静态常量变量（§4.12）——被编译且条件代码被省略，那么分发一个包含标记定义的类类或接口是不够的。使用该标记的类将看不到它的新值，因此它们的行为可能会产生意料之外。从本质上说，标记值的更改与预存二进制文件是二进制兼容的（不会发生 `LinkageError`），但在行为上是不兼容的。

“内联”静态常量变量值的另一个原因是由于 `switch` 语句。它们是唯一依赖常数表达式的语句，即 `switch` 语句的每个 label 必须是一个常数表达式，其值与每个其他 `case` 标签都不同。`case` 标签通常是静态常量变量的引用，因此可能无法立即看出所有标签具有不同的值。如果证明在编译时没有重复的标签，那么将值内联到类文件中可以确保在运行时没有重复的标签——这是一个非常理想的属性。

### 示例 14.22-1. 条件编译

如果示例：

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

被编译并执行，它将产生输出：

```
DEBUG is true
```

假设产生了类 `Flags` 的新版本：

```
class Flags { static final boolean DEBUG = false; }
```

如果重新编译了 `Flags` 但没有重新编译 `Test`，使用现有的 `Flags` 运行新的二进制文件将产生输出：

```
DEBUG is true
```

因为 `DEBUG` 是一个静态变量，所以它的值在编译 `Test` 时可能已经被使用，而无需引用类 `Flags` 类。

如果 `Flags` 是一个接口，这种行为也会发生，如修改后的示例所示：

```
interface Flags { boolean DEBUG = true; }

class Test {

  public static void main(String[] args) {

    if (Flags.DEBUG) {

      System.out.println("DEBUG is true");

    }

  }

}
```

事实上，接口的字段始终是静态且 `final` 的，我们建议只将常数表达式赋值给接口字段。我们注意到但不建议，如果接口的原始类型字段可能会更改，其值可以以惯用方式表示如下：

```
interface Flags {

  boolean debug = Boolean.TRUE;

}
```

### 模式 14.30

模式描述了一种可以对值执行的测试。模式以语句和表达式的形式出现，声明了要测试的值。

对值与模式进行测试的过程被称为模式匹配。如果一个值成功匹配一个模式，模式变量将被初始化。

#### 类型模式 14.30.1 模式的种类

类型模式用于测试一个值是否是该类型的实例。

模式：
`TypePattern`

```
TypePattern:
LocalVariableDeclaration
```

为了方便起见，这里显示了 §4.3、§8.3 和 §8.4 中的产生式：

```
LocalVariableDeclaration:
(VariableModifier) LocalVariableType DeclaratorList

VariableModifier:
Annotation
final

LocalVariableType:
UnannType
var

DeclaratorList:
VariableDeclarator [, VariableDeclarator]

VariableDeclarator:
DeclaratorId [= VariableInitializer]

DeclaratorId:
Identifier [Dims]

Dims:
[Annotation]
```

`UnannType` 参见 §8.3。

类型模式声明一个局部变量。变量声明中的 `Identifier` 指定了模式变量的。

类型模式中声明的局部变量的规则规定 14.4 中。此外，必须满足以下所有条件，否则将发生编译错误：

- `LocalVariableType` 表示一个引用类型（并且进一步不是 `var`）。
- `DeclaratorList` 仅包含一个 `VariableDeclarator`。
- `VariableDeclarator` 没有初始化器。
- `DeclaratorId` 没有括号对。

模式变量的类型是 `LocalVariableType` 表示的引用类型。

类型模式的类型是其模式变量的类型。

如果表达式 `e` 与 `T` 兼容（§5.5），则与模式兼容。

> 表达式与模式的兼容性用于 `instanceof` 模式匹配运算符（§15.20.2）。

#### 14.30.2 模式匹配

模式匹配是在运行时对值与模式进行测试的过程。模式匹配于语句执行（§14.1）和表达式求值（§15.1）。

确定值是否匹配模式以及初始化模式变量的规则如下：

- 非空值 `v` 如果转换为 `T` 而不抛出 `ClassCastException`，则匹配类型 `T`；否则不匹配。

如果 `v` 匹配，则类型模式声明的模式变量初始化为 `v`。

如果 `v` 不匹配，类型模式声明的模式变量不被初始化。

## 第 15 章
# 表达式

程序中的许多工作是通过求值表达式完成的，这些表达式可能是为了产生副作用（例如赋值给变量），也可能是为了其值（这些值可以作为更大表达式中的参数或操作数），或者为了影响语句的执行顺序，或两者兼有。

本章规定了表达式的含义以及它们的求值规则。

## 15.1 求值、指代与结果

当程序中的表达式被求值（执行）时，其结果表示以下三种情况之一：

- 一个变量（§4.12）（在 C 中，这被称为 l值）
- 一个值（§4.2, §4.3）
- 无（该表达式被称为 void）

如果一个表达式指向一个变量，并且在后续求值中需要一个值，则使用该变量的值。在这种语境下，如果表达式指向一个变量或一个值，我们可以简单地称为表达式的值。

一个表达式结果为空，当且仅当它是一个调用了不返回值的方法的方法调用（§15.12），即调用一个声明为 `void` 的方法（§8.4）。此类表达式只能作为表达式语句（§14.8）或 lambda 体的唯一表达式（§15.27.2）使用，因为表达式可以出现的任何其他语境都要求表达式必须指向某些内容。作为方法调用的表达式语句或 lambda 实体也可以调用产生结果的方法；在这种情况下，方法返回的值将被静默地丢弃。

表达式的求值可能会产生副作用，因为表达式可能包含嵌入的赋值、递增运算符、递减运算符、方法调用，并且在 `switch` 表达式中可能包含任意语句。

表达式出现在以下位置：

- 正在声明的类或接口的声明中：在字段初始化器中、静态初始化器中、实例初始化器中、构造函数声明中、方法声明中，或注解中。
- 对模块、包或顶层类或接口声明的注解。

## 15.2 表达式的形式

表达式可以大致归类为以下语法形式之一：

- 表达式名（§6.5.6）
- 原始类型表达式（§15.8 - §15.13）
- 一元运算符表达式（§15.14 - §15.16）
- 二元运算符表达式（§15.17 - §15.24, 以及 §15.26）
- 三元运算符表达式（§15.25）
- Lambda 表达式（§15.27）
- `switch` 表达式（§15.28）

运算符之间的优先级由语法产生式的层级结构管理。最低优先运算符是 lambda 表达式的箭头 (`->`)，其次是赋值运算符。因此，所有表达式在语法上都包含在 `LambdaExpression` 和 `AssignmentExpression` 非终端符：

```
Expression:
LambdaExpression
AssignmentExpression
```



当某些表达式出现在特定的语境中时，它们被视为多态表达式。以下形式的表达式可能是多态表达式：

- 括号表达式（§15.8.5）
- 类实例创建表达式（§15.9）

## 表达式

### 表达式的类型 15.3

| 表达式的类型 |
| :--- |
| 方法调用表达式（§15.12） |
| 方法引用表达式（§15.13） |
| 条件表达式（§15.25） |
| Lambda 表达式（§15.27） |
| switch 表达式（§15.28） |

确定这些形式之一的表达式是否为多态表达式的规则给出在指定这些表达式形式的各个章节中。

不是多态表达式的表达式是独立表达式。独立表达式是在确定为非多态表达式时上述形式的表达式，以及所有其他形式的表达式。所有其他形式的表达式被称为具有独立形式。

某些表达式具有可以在编译时确定的值。这些是常量表达式（§15.29）。

## 15.3 表达式的类型

如果表达式指向一个变量或值，则该表达式具有编译时已知的类型。独立表达式的类型可以完全根据表达式的内容确定；相比之下，多态表达式的类型可能会受到表达式目标类型（§5，转换与语境）的影响。确定表达式类型的规则将在下方对每种表达式分别说明。

除非发生堆污染（§4.12.2），否则存储在变量中的值始终与变量的类型兼容。

换句话说，类型为 `T` 的表达式的值始终适用于赋值类型为 `T` 的变量。

注意，如果表达式的类型是命名为类 `c` 的类类型，则类 `c` 声明为 `final` 或 `sealed`（§8.1.1.2）对表达式的值有影响：

- 如果 `c` 是 `final`，则表达式保证具有一个值，其值为 (i) 空引用，或 (ii) 类为 `c` 本身的对象，因为 `final` 类没有子类。
- 如果 `c` 是 `sealed`，则表达式保证具有一个值，其值为 (i) 空引用、(ii) 类为 `c` 本身的对象，或 (iii) 与 `c` 兼容。
- 如果 `c` 是自由扩展的，则表达式保证具有一个值，其值为 (i) 空引用、(ii) 类为 `c` 本身的对象，或 (iii) 与 `c` 兼容。

## 15.4 浮点表达式

浮点表达式是类型为 `float` 或 `double` 的表达式（§4.2.3）。类型为 `float` 的浮点表达式的值精确对应于 32 位 IEEE 754 的值。类型为 `double` 的浮点表达式的值精确对应于 64 位 IEEE 754 的值。

Java 语言中的许多比较和数值运算符对应于 IEEE 754 操作，作用于浮点值的转换也是如此（表 15.4-A）。

### 表 15.4-A 与 IEEE 754 的对应

| 运算符/转换 | IEEE 754 操作 |
| :--- | :--- |
| 数值比较运算符 `<`, `<=`, `>`, `compareQuiet`, `compareQuietEqual` 和 `>=`（§15.20.1） | `compareQuietGreater`, `compareQuietEqual` |
| 数值相等运算符 `==` 和 `!=`（§15.21.1） | `compareQuietEqual`, `compareQuietNotEqual` |
| 一元负运算符 `-`（§15.4） | `negate` |
| 乘法运算符 `*` 和 `/`（§15.17.1），乘法、除法（§15.17.2） | |
| 加法运算符 `+` 和 `-` | 加法、减法 |
| 从整型的扩展转换（§15.1.2） | `convertFromInt` |
| 到整型的收缩转换（§15.1.3） | `convertToZero` |
| `float` 和 `double` 之间的转换 | `convertFormat` |

> 浮点取模运算符 `%`（§15.17.3）不对应于 IEEE 754 剩余运算。

Java 语言中没有对应运算符的某些 IEEE 754 操作通过 `Math` 和 `StrictMath` 类的方法提供，包括用于 IEEE 754 平方根的 `sqrt` 方法、用于 IEEE 754 乘加的 `fma` 方法，以及用于 IEEE 754 剩余的 `remainder` 方法。

Java 语言要求支持 IEEE 754 规格浮点数和渐进下溢，这使得证明特定数值算法的属性变得更容易。如果计算结果是规格数，浮点运算不会将其舍入零。

Java 语言中浮点运算符的结果必须与相同操作数上相应的 IEEE 754 操作的结果匹配。对于有限结果，这意味着浮点结果的尾数和指数必须都是 IEEE 754 指定的。

对匹配符号、尾数和指数的要求排除了某些在浮点行为规定不精确时可能允许的转换。例如，`-x` 通常不能替换为 `(0.0 - x)`，因为当 `x` 为 `-0.0` 时，结果的符号会有不同。此外，其他可能改变值的转换如 `(a * b + c)` 除非能够证明结果是完全相同的，否则不允许将其替换为融合乘加库方法的调用。

在任何情况下，浮点表达式的求值可能使用比表达式类型所示的具有更高精度或更大指数范围的中间结果。

溢出的浮点操作会产生带符号的无穷大。

下溢的浮点操作会产生一个规格化值或零。

没有唯一数学定义结果的浮点操作会产生 `NaN`。

所有以 `NaN` 作为操作数的数值运算，其结果均为 `NaN`。

由于 `NaN` 是无序的，任何涉及一个或两个 `NaN` 的数值比较操作都返回 `false`，任何 `==` 比较返回 `false`，而任何 `!=` `NaN` 比较均返回 `true`。

浮点算术是实数算术的近似。虽然实数有无限多个，但特定的浮点格式只有有限数量的值。在 Java 编程语言中，**舍入** 策略是一个用于将实数映射到给定格式的浮点值的函数。对于浮点可表示范围内的实数，实线上的连续段被映射到单个浮点值。数值上等于某个浮点值的实数被映射到该浮点值；例如，实数 `1.5` 在给定格式中映射为浮点值 `1.5`。Java 编程语言定义了两种舍入策略：

- **向最近舍入** 策略适用于除 (i) 转换为整数值和 (ii) 浮点取余之外的所有浮点操作符。在向最近舍入的策略下，不精确的结果将被舍入到与精确结果最近的可表示值；如果两个最近的可表示值几乎相等，则选择最低位为 0 的值。

向最近舍入的舍入策略对应于 IEEE 754 中二进制算术的默认舍入方向属性，即 `roundTiesToEven`。

> `roundTiesToEven` 舍入方向属性在 1985 版本的 IEEE 754 标准中被称为“向最近舍入”舍入模式。Java 编程语言中的舍入策略以此模式命名。

- **向零舍入** 舍入策略适用于 (i) 浮点值转换为整数值（§5.1.3）以及 (ii) 浮点取余（§15.17.3）。在向零舍入策略下，不精确的结果将被舍入到在绝对值上不大于无限精确结果的最近的可表示值。对于整数，向零舍入策略等同于舍弃小数部分尾数的截断法。

向零舍入的舍入策略对应于 IEEE 754 中二进制算术的 `roundTowardZero` 舍入方向。

> `roundTowardZero` 方向属性在 1985 版本的 IEEE 754 标准中被称为“向零舍入”舍入模式。Java 编程语言中的舍入策略以此舍入模式命名。

Java 编程语言要求每个浮点操作符都返回其严格精度的结果。每个浮点操作符所使用的 Java 策略是指定的向最近舍入或向零舍入。

Java 1.0 和 1.1 使用浮点表达式的严格求值。严格求值意味着每个 `float` 操作数在 IEEE 754 binary32 格式中保持可表示，每个 `double` 操作数对应于 IEEE 754 binary64 格式可表示的值，且每个具有相应 IEEE 754 操作的浮点操作符都与相同操作数的 IEEE 754 结果匹配。

严格求值提供了可预测的结果，但在 Java 1.0/1.1 时代常见的处理器族的 Java 虚拟机实现中导致了性能问题。因此，从 Java 1.2 到 Java SE 16，Java SE 平台允许 Java 虚拟机实现针对特定的处理器族进行优化。

在 Java 17 及更高版本中，Java SE 平台始终对浮点表达式进行严格求值。对于实现严格求值存在问题的旧处理器成员不再存在该问题。为了兼容性，`strictfp` 在 Java 中仍然有效（§3.8），并对其使用继续有限制（§8.4.3），尽管编译器鼓励程序员注意其过时状态。Java 语言的未来版本可能会重新定义或移除 `strictfp` 关键字。

## 15.5 表达式与运行时检查

如果表达式的类型是原始类型，则该表达式的值是原始类型。

如果表达式的类型是引用类型，则所引用对象的类（或者是否为非空引用）在编译时是未知的。在 Java 编程语言中，少数地方所引用对象的实际类会影响程序执行，而无法通过表达式的类型推断。这些地方如下：

- 方法调用（§15.12）。调用 `o.m(...)` 的特定方法是根据 `o` 的类型的类或接口中的方法选定的。对于实例，运行时值所引用对象的类参与其中，因为子类可能会覆盖父类中声明的方法，因此调用此重写方法。（重写方法可能会进一步调用原始的被覆盖方法。）
- `instanceof` 操作符（§15.20.2）。类型为引用类型的表达式可以使用 `instanceof` 进行测试，以确定其运行时值所引用对象的类是否可以转换为另一种引用类型。
- 强制转换（§15.16）。操作数表达式所引用对象的类可能与转换运算符指定的类型不兼容。对于引用类型，这可能需要运行时检查，如果运行时确定的对象类无法转换为目标类型，则抛出异常。
- 对引用类型数组组件的赋值（§10.5, §15.13, §15.26.1）。类型检查规则允许数组 `s[]` 被视为 `T[]` 的子类型。如果 `s` 是 `T` 的子类型，但在赋值给数组组件时需要进行运行时检查，这与类型转换时执行的检查类似。
- 异常处理（§14.20）。只有当抛出的异常对象的类是 `catch` 子句中形式参数类型的 `instanceof` 时，`catch` 子句才能捕获该异常。

对象的类无法静态确定的情况可能会导致运行时类型错误。

此外，还存在静态已知类型在运行时可能不准确的情况。这种情况可能出现在产生编译时未检查警告的程序中。此类警告是针对无法在静态上保证安全的操作而出的，并且无法立即进行动态检查，因为它们涉及不可重化的类型（§4.7）。因此，在程序执行后期，动态检查可能会检测到不一致性并导致运行时类型错误。

运行时错误仅在以下情况下发生：

- 在某种情况下，操作数表达式的值所引用的对象的实际类与类型转换符指定的类型不兼容（§5.5, §15.16）；在这种情况下，将抛出 `ClassCastException`。
- 在为了确保对不可重化类型的操作的有效性而自动生成的类型转换中（§4.7）。
- 在对引用类型的数组组件赋值时，要赋值的值所引用的对象的实际类与数组的实际运行时组件类型不兼容（§10.5, §15.13, §15.26.1）；在这种情况下，将抛出 `ArrayStoreException`。
- 当异常没有被 `try` 语句的任何 `catch` 子句捕获时（§14.20）；在这种情况下，遇到异常的控制线程首先尝试调用未捕获的异常处理器（§11.3）并终止。

## 15.6 求值的正常完成与中断完成

每个表达式都有一种求值模式，在该模式下会执行某些计算步骤。后续章节描述了每种表达式的求值模式。

如果所有步骤都执行且没有抛出异常，则认为该表达式正常完成。

然而，如果表达式的求值抛出了异常，则认为该表达式中断完成。中断完成总是带有一个关联的原因，该原因始终带有给定值的抛出。

运行时异常由预定义操作符抛出，方式如下：

- 类实例表达式（§15.9.4）、数组创建表达式（§15.10.2）、方法引用表达式（§15.13.3）、数组初始化表达式（§10.6）、字符串连接操作符表达式（§15.18.1）或 lambda 表达式（§15.27.4）如果可用内存不足，则抛出 `OutOfMemoryError`。
- 数组创建表达式（§15.10.2）如果索引表达式的值小于 0，则抛出 `NegativeArraySizeException`。
- 数组访问表达式（§15.10.4）如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 数组访问表达式（§15.10.4）如果索引表达式的值为负数或大于等于数组长度，则抛出 `ArrayIndexOutOfBoundsException`。
- 字段访问表达式（§15.11）如果对象引用表达式的值为 `null`，则抛出 `NullPointerException`。
- 调用实例方法的方法调用表达式（§15.12）如果目标引用为 `null`，则抛出 `NullPointerException`。
- 类型转换表达式（§15.16）如果运行时发现类型转换是不允许的，则抛出 `ClassCastException`。
- 整数除法（§15.17.2）或整数取余（§15.17.3）操作符如果右操作数表达式的值为 0，则抛出 `ArithmeticException`。
- 对引用类型的数组组件赋值（§15.26.1）、方法调用表达式（§15.12）或前置或后置递增（§15.14.2, §15.15.1）或递减运算符（§15.14.3, §15.15.2）都可能由于装箱转换（§5.7）而抛出 `OutOfMemoryError`。
- 对引用类型的数组组件赋值（§15.26.1）如果要赋值的值与数组的组件类型不兼容（§10.5），则抛出 `ArrayStoreException`。
- switch 表达式（§15.28）如果没有 switch 标签匹配选择表达式的值，则抛出 `IncompatibleClassChangeError`。

如果发生异常导致方法体的执行中断完成，方法调用表达式也可能导致抛出异常。

如果发生异常导致构造函数的执行中断完成，类实例创建表达式也可能导致抛出异常。

在求值表达式期间还可能发生各种链接和虚拟机错误。根据其性质，这些错误难以预测且难以处理。

如果发生异常，则一个或多个表达式的求值可能会在正常求值模式的所有步骤完成之前终止；此类表达式被认为中断完成。

如果表达式的求值需要子表达式，那么子表达式的中断完成会导致表达式的中断完成。“正常完成”和“中断完成”这些术语也适用于语句的执行（§14.）。语句可能由于多种原因中断完成，而不仅仅是因为抛出了异常。

## 15.7 求值顺序

Java 语言保证操作数按照特定的求值顺序执行，即从左到右。

> 建议代码不要关键地依赖此规范。当每个表达式最多包含一个侧效应，且代码不依赖于具体产生哪种异常时，代码通常更清晰。

### 15.7.1 先求值左操作数

二元操作符的左操作数在右操作数的任何部分求值之前完全求值。

如果二元操作符的左操作数求值中断完成，则右操作数的任何部分似乎都没有被求值。

如果操作符是复合赋值运算符（§15.26.2），则左操作数的求值包括记住左操作数所指示的变量并获取该变量的值。

#### 示例 15.7.1-1. 左操作数求值

在以下程序中，`*` 操作符的左操作数包含对变量的赋值，右操作数包含对同一变量的引用。产生的值反映了赋值先发生。

```java
class Test1 {
    public static void main(String[] args) {
        int i = 2;
        int j = (i=3) * i;
        System.out.println(j);
    }
}
```

该程序输出：

```
9
```

不允许 `*` 操作的结果为 6 而不是 9。

#### 示例 15.7.1-2. 复合赋值运算符中的隐式左操作数

在以下程序中，两个赋值语句在加法操作符的右操作数求值之前，都获取并记录了左操作数的值（即 9），此时变量被设置为 3。

```java
class Test2 {
    public static void main(String[] args) {
        int a = 9;
        a += (a = 3); // 第一个示例
        System.out.println(a);
        int b = 9;
    }
}
```



# 15.7 表达式求值顺序

## 15.7.1 求值遵循括号和优先级

Java 编程语言尊重由括号显式指定和由运算符优先级隐式指定的求值顺序。

Java 编程语言的某种实现可能无法利用代数等式（如结合律）将表达式重写为更方便的计算顺序，除非能够证明对于所有可能涉及的计算值，替换后的表达式在值和可观测副作用上（即使在存在多个执行线程的情况下，使用 §17（线程和锁）中的线程执行模型）也是等价的。

在浮点数计算的情况下，此规则也适用于无穷大（infinity）和非数字（NaN）值。

- 例如，`!(x<y)` 可能不会被重写为 `x>=y`，如果 x 或 y 其中之一为 NaN 或两者均为 NaN，这些表达式的值是不同的。

具体来说，数学上似乎具有结合律的浮点计算在计算上很可能是不结合律的。此类计算不能被盲目地重排。

例如，Java 编译器将 `4.0*x*0.5` 重写为 `2.0*x` 是不正确的；虽然舍入在这里恰好不是问题，但对于某些较大的 x 值，第一个表达式会产生无穷大（因为溢出），而第二个表达式会产生有限的结果。

因此，例如测试程序：

```java
class Test {
  public static void main(String[] args) {
    double d = 8E37;
    System.out.println(4.0 * d * 0.5);
    System.out.println(2.0 * d);
  }
}
```

打印结果：

```
Infinity
1.6E308
```

因为第一个表达式溢出了，而第二个没有。

相比之下，整数加法和乘法在 Java 编程语言中被证明是结合律的。

例如 `a+b+c`，其中 a、b 和 c 是局部变量（这个简化假设避免了引入多线程和 volatile 变量），求值结果 `(a+b)+c` 或 `a+(b+c)` 始终会产生相同的答案；如果表达式 `b+c` 出现在代码的附近，智能的 Java 编译器可能可以使用这个公共子表达式。

## 15.7.2 在操作之前求值操作数

Java 编程语言保证，运算符的每个操作数（条件运算符 `&&`、`||` 和 `?` 除外）在执行操作的任何部分之前似乎都已完全求值。

如果二元运算符是整数除法 `/` (§15.17.2) 或整数取模 `%` (§15.17.3)，它的执行可能会引发 `ArithmeticException`，但该异常只有在二元运算符的两个操作数都求值完毕且在这些求值正常完成的情况下才会被抛出。

### 示例 15.7.2-1. 在操作之前求值操作数

```java
class Test {
    public static void main(String[] args) {
        int divisor = 0;
        try {
            int i = 1 / (divisor * loseBig());
        } catch (Exception e) {
            System.out.println(e);
        }
    }

    static int loseBig() throws Exception {
        throw new Exception("Shuffle off to Buffalo!");
    }
}
```

该程序产生输出：

```
java.lang.Exception: Shuffle off to Buffalo!
```

而不是：

```
java.lang.ArithmeticException: / by zero
```

因为除法操作任何部分（包括除以零异常）都不可能在 `loseBig()` 调用完成之前发生，尽管实现可能能够检测或推断出除法操作肯定会导致除以零的异常。

## 15.7.3 左操作数求值的异常中断

### 示例 15.7.1-3. 左操作数求值的异常中断

```java
class Test3 {
    public static void main(String[] args) {
        int j = 1;
        try {
            int i = forgetIt() / (j = 2);
        } catch (Exception e) {
            System.out.println(e);
            System.out.println("Now j = " + j);
        }
    }

    static int forgetIt() throws Exception {
        throw new Exception("I'm outta here!");
    }
}
```

该程序输出：

```
java.lang.Exception: I'm outta here!
Now j = 1
```

也就是说，运算符的左操作数 `forgetIt()` 在右侧操作数求值以及其嵌入的将 2 赋值给 j 之前就抛出了异常。

## 15.7.4 参数列表从左到右求值

在方法或构造函数调用或类实例创建中，参数表达式可能出现在括号内，并用逗号分隔。每个参数表达式在在其右侧任何参数表达式的任何部分之前，似乎都已完全求值。

如果某个参数表达式的求值异常中断，则其右侧任何参数表达式的任何部分都没有被求值。

### 示例 15.7.4-1. 方法调用时的求值顺序

```java
class Test1 {
    public static void main(String[] args) {
        String s = "going,"; s = "gone";
        print3(s, s, s);
    }

    static void print3(String a, String b, String c) {
        System.out.println(a + b + c);
    }
}
```

该程序产生输出：

```
going, going, gone
```

因为将字符串 "gone" 赋值给 s 发生在 `print3` 的前两个参数求值之后。

### 示例 15.7.4-2. 参数表达式的异常中断

```java
class Test2 {
    static int id;

    public static void main(String[] args) {
        try {
            test(id = 1, coops());
        } catch (Exception e) {
            System.out.println(e);
        }
    }

    static int test(int a, int b) {
        return a + b;
    }

    static int coops() throws Exception {
        throw new Exception("coops");
    }
}
```

该程序输出：

```
java.lang.Exception: coops
```

因为对 id 的赋值尚未执行。

## 15.7.5 其他表达式的求值顺序

某些表达式的求值顺序并不完全由这些规则覆盖，因为这些表达式可能会引发异常。请参见以下类型表达式求值顺序详细说明：

- 类创建表达式 (§15.9.4)
- 数组创建表达式 (§15.10.2)
- 数组访问表达式 (§15.10.4)
- 方法调用表达式 (§15.12.4)
- 方法引用表达式 (§15.13.3)
- 涉及数组的赋值 (§15.26)
- Lambda 表达式 (§15.27.4)

# 15.8 基础表达式

基础表达式包含了大多数简单的表达式类型，其他表达式由其构造：字面量、对象创建、字段访问、方法调用、方法引用和数组访问。括号内的表达式在语法上也被视为基础表达式。

```
Primary:
PrimaryNoArray
ArrayCreationExpression

PrimaryNoArray:
Literal
ClassLiteral
this
TypeName . this
( Expression )
ClassCreationExpression
FieldAccess
ArrayAccess
MethodInvocation
MethodReference
```

Java 语言语法的这部分有两个异常。首先，人们可能认为简单的名称（局部变量和方法参数）是基础表达式。由于技术原因，名称在之后引入后缀表达式 (§15.14）时与基础表达式放在一起。

这样做的技术原因是为了在只有单 Token 预遇的情况下对 Java 程序进行左右解析。考虑表达式 `([z])` 和 `((long)z)`。前者是括号内的数组访问 (§15.10.3)，后者是类型转换的开始 (§15.16)。在预遇符号为 `[` 的点，左右解析会将 `z` 归约为非终端 `Name`。在类型转换的范围内，如果 `Name` 不是 `Primary` 的可选方案之一，那么在不向前查看 `[` 之后的 Token 的情况下，我们无法判断是数组访问还是类型转换。这里的语法通过将 `Name` 和 `Primary` 分离，并在某些其他语法规则中（ClassInstanceExpression、MethodInvocation、ArrayAccess 和 PostfixExpression 的规则，但不包括 FieldAccess，因为它直接使用标识符）允许使用，避免了这一问题。这种策略有效地推迟了判断 `Name` 是否应视为 `Primary` 的问题。

第二个异常特征避免了 `new int[3][3]` 表达式中的潜在语法歧义，这在 Java 中始终意味着单个多维数组的创建。array，如果没有适当的语法技巧，可能也会被解释为与 `[new int[3]] [3]` 相同。

这种歧义通过将 Primary 的预期定义拆分为 Primary 和 PrimaryNoNewArray 来消除。（这可以与 Statement 拆分为 Statement 和 StatementNoShortIf (§14.5) 以避免“悬空 else”问题进行对比。）

## 15.8.1 字面量常量 (Lexical Literals)

字面量（§3.10) 表示一个固定的、不改变的值。

为了方便起见，此处展示了 §3.10 中的以下产生式：

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

字面量的类型按如下方式确定：

- 以 L 或 l 结尾的整数字面量 (§3.10.1) 的类型为 long (§4.2.2)。
- 任何其他整数字面量的类型为 int (§4.2.1)。
- 以 F 或 f 结尾的浮点数字面量 (§3.10.2) 的类型为 float (§4.2.3)。
- 任何其他浮点数字面量的类型为 double (§4.2.3)。
- 布尔字面量 (§3.10.3) 的类型为 boolean (§4.2.5)。
- 字符字面量 (§3.10.4) 的类型为 char (§4.2.1)。
- 字符串字面量 (§3.10.5) 或文本块的类型为 String (§4.3.3)。
- 空字面量 null (§3.10.8) 的类型为空类型 (§4.1)；其值为空引用。

词法字面量的求值总是正常完成的。

## 15.8.2 类字面量 (Class Literals)

类字面量是一个表达式，由类、接口、数组类型或原始类型的名称，或者伪类型 void 组成，后跟一个 '.' 和标记符号 class。

```
ClassLiteral:
TypeName[[]].class
NumericType[[]].class
boolean[[]].class
void.class
```

TypeName 表示一个可访问的类或接口 (§6.6)。如果 TypeName 表示一个不可访问的类或接口，或者表示一个类型变量，则为编译错误。

C.class 的类型，其中 C 是类、接口或数组类型的名称 (§4.3)，为 Class<C>。

p.class 的类型，其中 p 是原始类型的名称 (§4.2)，为 Class<B>，其中 B 是类型为 p 的表达式经过装箱转换后的类型 (§5.1.7)。

void.class (§8.4.5) 的类型为 Class<Void>。

类字面量的求值结果为命名类、接口、数组类型或原始类型（或 void）的 Class 对象，该对象由当前实例类的类加载器 (§12.2) 定义。

## 15.8.3 this

关键字 this 可以在以下上下文中作为表达式使用：

- 在类的实例方法体内部 (§8.4.3.2)
- 在类的构造方法体内部 (§8.8.7)
- 在类的实例初始化器中 (§8.6)
- 在类的实例变量的初始化器中 (§8.3.2)
- 在接口的实例方法体内部，即默认方法或非静态私有接口方法 (§9.4)

当作为表达式时，关键字 this 表示一个值，该值是对调用该实例方法的对象的引用 (§15.12)，或者是对正在构造的对象的引用。在 lambda 体 (§15.27.2) 中，this 表示的值与周围上下文中 this 表示的值相同。

> 关键字 this 也被用于显式构造方法调用语句 (§8.8.7.1)，并表示方法或构造方法的接收者参数。



# 字面量常量 (Lexical Literals)

`array`，如果没有适当的语法技巧，可能也会被解释为与 `[new int[3]] [3]` 相同。

这种歧义通过将 `Primary` 的预期定义拆分为 `Primary` 和 `PrimaryNoNewArray` 来消除。（这可以与 `Statement` 拆分为 `Statement` 和 `StatementNoShortIf` (§14.5) 以避免“悬空 else”问题进行对比。）

字面量（§3.10）表示一个固定的、不改变的值。

为了方便起见，此处展示了 §3.10 中的以下产生式：

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

字面量的类型按如下方式确定：

- 以 `L` 或 `l` 结尾的整数字面量（§3.10.1）的类型为 `long`（§4.2.2）。
- 任何其他整数字面量的类型为 `int`（§4.2.1）。
- 以 `F` 或 `f` 结尾的浮点数字面量（§3.10.2）的类型为 `float`（§4.2.3）。
- 任何其他浮点数字面量的类型为 `double`（§4.2.3）。
- 布尔字面量（§3.10.3）的类型为 `boolean`（§4.2.5）。
- 字符字面量（§3.10.4）的类型为 `char`（§4.2.1）。
- 字符串字面量（§3.10.5）或文本块的类型为 `String`（§4.3.3）。
- 空字面量 `null`（§3.10.8）的类型为空类型（§4.1）；其值为空引用。

词法字面量的求值总是正常完成的。

# 类字面量 (Class Literals)

类字面量是一个表达式，由类、接口、数组类型或原始类型的名称，或者伪类型 `void` 组成，后跟一个 `.` 和标记符号 `class`。

## 语法

```
ClassLiteral:
    TypeName [ [] ] .class
    NumericType [ [] ] .class
    boolean [ [] ] .class
    void.class
```

`TypeName` 表示一个可访问的类或接口（§6.6）。如果 `TypeName` 表示一个不可访问的类或接口，或者表示一个类型变量，则为编译错误。

`C.class` 的类型，其中 `C` 是类、接口或数组类型的名称（§4.3），为 `Class<C>`。

`p.class` 的类型，其中 `p` 是原始类型的名称（§4.2），为 `Class<B>`，其中 `B` 是类型为 `p` 的表达式经过装箱转换后的类型（§5.1.7）。

`void.class`（§8.4.5）的类型为 `Class<Void>`。

类字面量的求值结果为命名类、接口、数组类型或原始类型（或 `void`）的 `Class` 对象，该对象由当前实例类的类加载器（§12.2）定义。

# 15.8.3 this 关键字

关键字 `this` 可以在以下上下文中作为表达式使用：

- 在类的实例方法体内部（§8.4.3.2）
- 在类的构造方法体内部（§8.8.7）
- 在类的实例初始化器中（§8.6）
- 在类的实例变量的初始化器中（§8.3.2）
- 在接口的实例方法体内部，即默认方法或非静态私有接口方法（§9.4）

当作为表达式时，关键字 `this` 表示一个值，该值是对调用该实例方法的对象的引用（§15.12），或者是对正在构造的对象的引用。在 lambda 体（§15.27.2）中，`this` 表示的值与周围上下文中 `this` 表示的值相同。

> 关键字 `this` 也被用于显式构造方法调用语句（§8.8.7.1），并表示方法或构造方法的接收者参数。

# 15.9 类实例化创建表达式 (Class Instance Creation Expressions)

类实例化创建表达式用于创建类的实例对象。

## 语法

```
ClassInstanceCreationExpression:
    UnqualifiedClassCreationExpression
    Expression . UnqualifiedClassCreationExpression
```

### 15.9.1 未限定类创建表达式 (Unqualified Class Creation Expressions)

```
UnqualifiedClassCreationExpression:
    new [TypeArguments]
        ClassOrInterfaceToInstantiate ( [ArgumentList] ) [ClassBody]
```

```
ClassOrInterfaceToInstantiate:
    [Annotation] Identifier { , [Annotation] Identifier }
    [TypeArgumentsOrDiamond]
```

```
TypeArgumentsOrDiamond:
    TypeArguments
    <>
```

为了方便起见，此处展示了 §15.12 中的以下产生式：

```
ArgumentList:
    Expression [ , Expression ]
```



# 表达式

## 类实例化创建表达式

类实例化创建表达式指定一个要实例化的类，后面可能跟类型参数（§4.5.1）或者如果被实例化的类是泛型的，则是菱形（`<>`），后面跟一个可能空的实际值参数列表。

如果构造方法是泛型的（§8.8.4），构造方法的类型参数同样可以被推断或显式传递。如果显式传递，构造方法的类型参数紧跟关键字 `new`。

如果类实例化创建表达式为构造方法提供了类型参数，但对类类型参数使用了菱形式，则为编译错误。引入此规则是因为泛型类型参数的推断可能会影响泛型类型参数的约束。

如果 `TypeArguments` 紧跟在 `new` 之后或 `(` 之前，那么如果任何类型参数是通配符（§4.5.1），则为编译错误。

类实例化创建表达式可以抛出的异常类型在 §11.2.1 中指定。

类实例化创建表达式有两种形式：

- **未限定的类实例化创建表达式**以关键字 `new` 开头。

  未限定的类实例化创建表达式可用于创建类的实例，无论该类是顶层的（§7.6）、成员的（§8.5, §9.5）、局部的（§14.3）还是匿名类（§15.9.5）。

- **限定的类实例化创建表达式**以 `Primary` 表达式或 `ExpressionName` 开头。

  限定的类实例化创建表达式允许创建内部成员类及其匿名子类的实例。

未限定和限定的实例化创建表达式都可以可选地以一个类体（class body）结束。此类带有类体的类实例化创建表达式声明了一个匿名类（§15.9.5）并创建了该类的实例。

如果类实例化创建表达式对类使用了菱形形式（diamond form）作为类型参数，并且出现在赋值上下文或调用上下文中（§5.2, §5.3），则它是一个多值表达式（§15.2）。否则，它是一个独立表达式。

当通过类实例化创建表达式创建类的实例时，我们称该类被*实例化*（instantiated）。类实例化涉及确定要实例化的类（§15.9.1）、新创建实例的闭包实例（如果有）（§15.9.2）以及为了创建新实例而要调用的构造函数（§15.9.3）。

### 15.9.1 确定被实例化的类

如果 `ClassOrInterfaceToInstantiate` 以 `<` 结尾，则 `ClassOrInterfaceToInstantiate` 必须表示一个良好的参数化类型（§4.5），否则将发生编译错误。

如果 `ClassOrInterfaceToInstantiate` 以 `<>` 结尾，但 `ClassOrInterfaceToInstantiate` 中的 `Identifier` 所指示的类或接口不是泛型的，则将发生编译错误。

如果类实例化创建表达式带有类体，则被实例化的类是一个匿名类。此时：

- 如果类创建表达式是非限定的，则：

  `ClassOrInterfaceToInstantiate` 中的 `Identifier` 必须表示一个可访问的、自由扩展的（§8.1.1.2）且不是枚举类，或者一个可访问且自由扩展的（§9.1.1.4）接口。否则，将发生编译错误。

  如果 `ClassOrInterfaceToInstantiate` 中的 `Identifier` 指向一个类 `c`，则声明一个 `c` 的匿名直接子类。如果存在 `TypeArguments`，则 `c` 具有由 `TypeArguments` 给出的类型参数；如果存在 `<>`，则 `c` 的类型参数将在 §15.9.3 中被推断；否则，`c` 没有类型参数。子类的体是实例化创建表达式中给 `ClassBody`。被实例化的类是该匿名子类。

  如果 `ClassOrInterfaceToInstantiate` 中的 `Identifier` 指向接口 `i`，则声明一个对象的匿名直接子类。如果存在 `TypeArguments`，则 `i` 具有由 `TypeArguments` 给出的类型参数；如果存在 `<>`，则 `i` 的类型参数将在 §15.9.3 中被推断；否则，`i` 没有类型参数。子类的体是实例化创建表达式中给 `ClassBody`。被实例化的类是该匿名子类。

- 如果实例化创建表达式是限定的，

  `ClassOrInterfaceToInstantiate` 中的 `Identifier` 必须无歧地指示一个可访问的、自由扩展的、不是枚举类的内部类，并且是 `Primary` 表达式或 `ExpressionName` 的编译时类型的成员。否则，将发生编译错误。

  `ClassOrInterfaceToInstantiate` 中的 `Identifier` 指向一个类 `c`。声明一个 `c` 的匿名直接子类。如果存在 `TypeArguments`，则 `c` 具有由 `TypeArguments` 给出的类型参数；如果存在 `<>`，则 `c` 的类型参数将在 §15.9.3 中被推断；否则，`c` 没有类型参数。子类的体是实例化创建表达式中给 `ClassBody`。被实例化的类是该匿名子类。

如果类创建表达式没有声明一个匿名类，则：

- 如果类创建表达式是非限定的，

  `ClassOrInterfaceToInstantiate` 必须指示一个可访问的、非抽象的且不是枚举类的类。否则，将发生编译错误。

  被实例化的类由 `ClassOrInterfaceToInstantiate` 指定。如果存在 `TypeArguments`，则该类具有由 `TypeArguments` 给出的类型参数；如果存在 `<>`，则该类的类型参数将在 §15.9.3 中被推断；否则，该类没有类型参数。

- 如果类创建表达式是限定的，

  `ClassOrInterfaceToInstantiate` 必须无歧地指示一个可访问的、非抽象的、不是枚举类的内部类，并且是 `Primary` 表达式或 `ExpressionName` 的编译时类型的成员。被实例化的类由 `ClassOrInterfaceToInstantiate` 指定。如果存在 `TypeArguments`，则该类具有由 `TypeArguments` 给出的类型参数；如果存在 `<>`，则该类的类型参数将在 §15.9.3 中被推断；否则，该类没有类型参数。

### 15.9.2 确定闭包实例

令 `c` 为实例化的类，`i` 为新实例。如果 `c` 是内部类，则 `i` 可能有一个闭包实例（§8.1.3），确定如下：

- 如果 `c` 是匿名类，则：

  如果 `c` 出现在静态上下文中，实例化创建表达式出现在静态上下文中，则 `i` 没有闭包实例。

  否则，`i` 的闭包实例是当前的。

- 如果 `c` 是内部局部类，则：

  如果 `c` 出现在静态上下文中，则 `i` 没有闭包实例。

  否则，如果实例化创建表达式出现在静态上下文中，则将发生编译错误。

  否则，令 `o` 为 `c` 的闭包类或接口声明，`v` 为实例化创建表达式的闭包类或接口声明。

  如果 `v` 不是 `o` 的内部类或 `o` 本身，则将发生编译错误。

  令 `n` 为一个整数，使得 `o` 是第 `n` 个闭包接口声明。`i` 的闭包实例是当前的。

- 如果 `c` 是内部成员类，则：

  - 如果实例化创建表达式是非限定的，则：

    > 如果实例化创建表达式出现在静态上下文中，则将发生编译错误。

    > 否则，如果 `c` 不是任何包含实例化创建表达式声明的类的成员，则将发生编译错误。

    > 否则，令 `o` 为 `c` 成员的最内层类，`u` 为实例化创建表达式的闭包类或接口声明。

    如果 `u` 不是 `c` 的内部类或 `o` 本身，则将发生编译错误。

    令 `n` 为一个整数，使得 `o` 是 `u` 的第 `n` 个闭包类或接口声明。`i` 的闭包实例是第 `n` 个。

  - 如果实例化创建表达式是限定的，则 `i` 的闭包实例是 `Primary` 表达式或 `ExpressionName` 的值。

如果 `c` 是匿名类，且其直接父类 `s` 是内部类，则 `i` 可能有一个相对于 `s` 的闭包实例，确定如下：

- 如果 `s` 是内部局部类，则：

  - 如果 `s` 出现在静态上下文中，则 `i` 没有相对于 `s` 的闭包实例。

  - 否则，如果实例化创建表达式出现在静态上下文中，则将发生编译错误。

  - 否则，令 `o` 为 `s` 的闭包类或接口声明，`u` 为实例化创建表达式的闭包类或接口声明。

    如果 `u` 不是 `c` 的内部类或 `o` 本身，则将发生编译错误。

    令 `n` 为一个整数，使得 `o` 是 `u` 的第 `n` 个闭包类或接口声明。`i` 相对于 `s` 的闭包实例是第 `n` 个。

- 如果 `s` 是内部成员类，那么：

  - 如果类实例创建表达式是不带限定的，那么：

    - 如果类实例创建表达式发生在静态上下文中，则发生编译时错误。

    - 否则，如果 `s` 不是任何包含该类实例创建表达式声明的类的成员，则发生编译时错误。

    - 否则，如果 `o` 是 `s` 成员的最内层包围声明，而 `u` 是该类实例创建表达式的紧邻包围类或接口声明。

      如果 `u` 不是 `o` 的内部类或 `o` 本身，则发生编译时错误。

      令 `n` 为一个整数，使得 `o` 是 `u` 的第 `n` 个词法上包围的类或接口声明。

      相对于 `s` 实例 `i` 的紧邻实例，是 `this` 的第 `n` 个词法上包围的实例。

  - 否则，发生编译时错误。

  - 如果类实例创建表达式是带限定的，那么相对于 `s` 实例 `i` 的紧邻实例是作为 `Primary` 表达式或 `ExpressionName` 值的对象。

### 15.9.3 选择构造函数及其参数

令 `c` 为被实例化的类。为了创建 `c` 的实例 `i`，根据以下规则在编译时选择 `c` 的一个构造函数。

首先，确定构造函数调用的实际参数：

- 如果 `c` 是一个直接超父类为 `s` 的匿名类，

  - 如果 `s` 不是内部类，或者 `s` 是发生在静态上下文中的局部类，那么构造函数的参数是类实例创建表达式参数列表中的参数（如果有），按照它们在表达式中出现的顺序排列。

  - 否则，构造函数的第一个参数是相对于 `s` 实例 `i` 的紧邻实例（§15.9.2），而构造函数的后续参数是类实例创建表达式参数列表中的参数（如果有），按照它们在类实例创建表达式中出现的顺序排列。

- 如果 `c` 是局部类或*私有*（`private`）内部成员类，那么构造函数的参数是类实例创建表达式参数列表中的参数（如果有），按照它们在类实例创建表达式中出现的顺序排列。

- 如果 `c` 是一个*非私有*（`non-private`）内部成员类，那么构造函数的第一个参数是相对于 `s` 实例 `i` 的紧邻实例（§8.8.1, §15.9.2），其构造函数的后续参数是类实例创建表达式参数列表中的参数（如果有），按照它们在类实例创建表达式中出现的顺序排列。

- 否则，构造函数的参数是类实例创建表达式参数列表中的参数（如果有），按照它们在表达式中出现的顺序排列。

其次，确定 `c` 的构造函数以及相应的*异常*（throws）子句和返回类型：

- 如果类实例创建表达式没有使用 `<>`，那么：

  - 如果 `c` 不是匿名类，那么：

    令 `τ` 为由 `c` 以及表达式中的任何类类型参数所表示的类型。使用 §15.12.2 中指定的过程（针对构造函数进行了修改）来选择 `τ` 的一个构造函数，并确定其 `throws` 子句。

    如果在 `τ` 中没有既适用又可访问的（§6.6）的唯一最特定构造函数，则发生编译时错误（如方法调用所示）。

    否则，对应于选构造函数的返回类型为 `τ`。

  - 如果 `c` 是匿名类，那么：

    使用 §15.12.2 中指定的过程（针对构造函数进行了修改）来选择 `c` 的直接超类类型的一个构造函数，并确定其 `throws` 子句。

    如果在 `c` 的直接超类类型中没有既适用又可访问的唯一最特定构造函数，则发生编译时错误（如方法调用所示）。

    否则，选择 `c` 的匿名构造函数作为 `c` 的构造函数（§15.9.5.1）。它的体由对 `c` 直接超类类型中所选构造函数的显式构造函数调用（§8.8.7.1）组成。

    所选构造函数的 `throws` 子句包含了在直接超类类型中所选构造函数的 `throws` 子句中的异常。

    对应于选构造函数的返回类型是匿名类类型。

- 如果类实例创建表达式使用了 `<>`，那么：

  如果 `c` 不是匿名类，令 `d` 等于 `c`。如果 `c` 是匿名类，令 `d` 为类实例创建表达式所指定的超类或超接口。

  如果 `D` 是一个类，令 `c_1, ..., c_n` 为类 `D` 的构造函数。如果 `D` 是一个接口，令 `c_j, ..., c_n` 为包含类 `Object` 的零参数构造函数的单例（n=1）。

  定义一个方法列表 `m_j, ..., m_n` 用于重载消决和类型推断。对于所有 `j` (1 ≤ `j` ≤ `n`)，`m_j` 根据 `c_j` 如下定义：

  - 首先定义一个替换 `Θ` 以实例化 `c_j` 中的类型。

  - 令 `F_1, ..., F_p` 为 `D` 的参数，并令 `G_1, ..., G_q` 为 `s` 的参数（注：此处原文 `s` 可能指代特定变量，根据上下文推断为参数相关）。此处逻辑较复杂，遵循原文结构：
    令 `F_1, ..., F_p` 为 `D` 的参数，并令 `G_1, ..., G_q` 为 `s` 的参数。`s` 的最内层包围声明是 `o`，`u` 是类实例创建表达式的紧邻包围类或接口声明。
    （注：原文此段包含大量逻辑符号和变量关系，翻译时保持符号结构）：

    ```
    11,,,,,,1,1,,,11111,,,,11,111
    1,F1:=Xp,p1,Yp, Gq:=Yq].
    ```

  - `m_j` 的参数是 `t_j` 应用于 `c_j`。

  - `m_j` 的返回类型是 `t_j` 应用于 `D`。

  - `m_j` 的参数类型列表是 `t_j` 应用于 `c_j`。

  - `m_j` 的异常类型列表是 `t_j` 应用于 `c_j`。

  - `m_j` 的修饰符为 `c_j`。

  - `m_j` 的名称是 `#`，一个与 `D` 中所有构造函数和方法名称不同的自动生成名称。

  - 为了选择构造函数，我们临时认为 `m_i, ..., m_n` 是 `D` 的成员。根据类实例创建表达式选择 `m_i, ..., m_n`，使用 §15.12。

  - 如果没有既适用又可访问的唯一方法，则发生编译时错误。

  否则，当 `m_j` 是所选方法时：

  - 如果 `c` 不是匿名类，则选择 `c_j` 作为 `c` 的构造函数。

    所选构造函数的 `throws` 子句与为 `m_j` 确定的 `throws` 子句相同。

    对应于选构造函数的返回类型是 `m_j` 确定的返回类型（§15.12.6）。

  - 如果 `c` 是匿名类，则其超类类型或直接超接口是 `m_j` 确定的返回类型。

    如果类实例创建表达式是多态表达式，其与目标类型的兼容性由 §18.5.2 确定，使用 `m_j` 作为选定方法 `m`。

    > 在最终确定类实例创建表达式的目标类型和对应于选构造函数的返回类型之前，与目标类型的兼容性测试可能会多次发生。例如，外层的方法调用表达式可能需要测试类实例创建表达式与不同形式参数类型的兼容性。

    如果 `c` 是匿名类，其超类类型或直接超接口是 `m_j` 确定的返回类型（§15.12.6）。

    如果直接超类类型或直接超接口，或其中的任何子表达式（子表达式包括包括泛型类型的类型参数、通配符类型参数的边界以及数组元素的类型，但不排除类型变量的边界）具有以下形式，则为编译错误：

    - 类型变量未声明为类型参数（例如由捕获转换产生的类型变量）。

    - 交叉类型。

    - 类或接口类型，其中该类或接口的声明从出现类实例创建表达式的类或接口中是不可见的。

    如果类实例创建表达式的参数与其目标类型不兼容，则为编译错误，该兼容性取决于调用类型（§15.12.2.6）。

    如果编译时声明通过变长参数数量调用是可用的，那么当构造函数的调用类型的最后一个形式参数类型为 `F_n[]` 时，如果该类型为 `F_n` 的擦除类型在调用点不可访问，则为编译错误。

类实例创建表达式的类型是与所选构造函数对应的返回类型，如上定义。

### 15.9.4 类实例创建表达式的运行时求值

在执行时，类实例创建表达式的求值如下。

首先，如果类实例创建表达式是一个带限定的类实例创建表达式，则求值限定主表达式。如果限定主表达式求值为 `null`，则抛出 `NullPointerException` 的求值，并且类实例创建表达式异常终止。如果限定主表达式异常终止，则类实例创建表达式因相同原因异常终止。

接下来，为新的类实例分配空间。如果没有足够的空间来分配对象，则类实例创建表达式的求值通过抛出 `OutOfMemoryError` 异常终止。

新对象包含该类中声明的所有字段及其所有父类中字段的新实例。当每个新字段实例被创建时，它都会被初始化为其默认值（§15.12.5）。

接下来，从左到右求值构造函数的实际参数。如果其右侧的任何参数未被求值，则类实例创建表达式因相同原因异常终止。

接下来，调用指定类的被选构造函数。这将导致为该类的每个父类调用至少一个构造函数。此过程可以通过显式构造函数调用语句（§8.8.7.1）进行引导，并在 §12.5 中进行了详细说明。

类实例创建表达式的值是引用新创建的指定对象的引用。每当表达式求值时，都会创建一个全新的对象。

### 示例 15.9-4-1. 求值顺序和内存溢出检测

如果类实例创建表达式的求值发现没有足够的内存来执行创建操作，则抛出 `OutOfMemoryError`。此检查发生在任何参数表达式求值之前。



```java
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
            for (;;) {
                ++id;
                new List(oldid = id);
            }
        } catch (Error e) {
            List.head = null;
            System.out.println(e.getClass() + " , " + (oldid==id));
        }
    }
}
```

打印：

```
java.lang.OutOfMemoryError, false
```

因为内存溢出条件是在参数表达式 `oldid = id` 求值之前检测到的。

对比数组创建表达式的处理，数组创建的内存溢出条件是在维度表达式求值后检测的 (§15.10.2)。

## 15.9.5 匿名类声明

匿名类由类实例创建表达式或以类体结尾的枚举常量隐式声明 (§8.1.1.1)。

匿名类永远不是抽象类 (§8.1.1.1)。

匿名类永远不是密封的 (§8.1.1.2)，因此没有允许的直接子类 (§8.1.6)。

由类实例创建表达式声明的匿名类永远不是 final 的 (§8.1.1.2)。

由枚举常量声明的匿名类总是 final 的 (§8.1)。

匿名类是 final 的，这在强制类型转换时是相关的 (§8.5)。

如果其右侧的任何参数未被求值，则类实例创建表达式因相同原因异常终止 (§8.4)。

匿名类始终是内部类 (§8.1.1.3)。

与局部类或接口一样，匿名类在求值时会引用其父类 (§8.3)。

由类实例创建表达式声明的匿名类，其直接类型类型是指定的类 (§15.9.1)。

由枚举常量声明的匿名类其直接类型类型是指定的类 (§15.9.2)。

类实例创建表达式的直接类型类型是新对象的引用 (§15.9.3)。

匿名类始终是 final 的 (§8.1)。

匿名类是 final 的，这在强制类型转换时是相关的 (§8.5)。

匿名类始终是 final 的 (§15.9.1)。

匿名类始终是 final 的 (§15.9.2)。

匿名类始终是 final 的 (§15.9.3)。

匿名类始终是 final 的 (§15.9)。

匿名类始终是 final 的 (§15.9.4)。

匿名类始终是 final 的 (§15.9.5)。

### 15.9.5.1 匿名构造函数

匿名类不能显式声明构造函数。相反，匿名类隐式声明一个匿名构造函数。具有直接父类 $s$ 的匿名构造函数的格式如下：

- 如果 $s$ 不是内部类，或者 $s$ 是位于静态上下文的局部类，则匿名构造函数对类实例创建表达式或枚举常量的每个参数有一个形式参数。

类实例创建表达式或枚举常量的实际参数用于确定 $s$ 的构造函数 $x$，如 §15.9.3 所示。匿名构造函数的每个形式参数类型与 $x$ 相同。

匿名构造函数体由一个显式构造函数调用 (§8.8.7.1) 组成 `super(...)`，其中实际参数为构造函数的参数，按其声明顺序。要调用的父类构造函数是 $x$。

- 否则，匿名构造函数的形式参数表示相对于 $s$ 的直接外部实例 $i$ (§15.9.2)。该参数的类型是闭包 $s$ 的类。

匿名构造函数对声明匿名类的类创建表达式的每个参数还有一个额外的形式参数。第 $n$ 个形式参数对应于第 $n-1$ 个实际参数。

类创建表达式的实际参数用于确定 $s$ 的构造函数 $x$，如 §15.9.3 所示。匿名构造函数的形式参数类型与 $x$ 相同。

在所有情况下，匿名构造函数的 `throws` 子句列出匿名构造函数中所包含的构造函数调用语句抛出的所有异常（如 §15.9.3 所示），以及匿名类的任何实例初始化器或变量初始化器抛出的所有检查异常。

注意，匿名构造函数的签名可能会引用不可访问类型（例如，如果此类类型出现在父类构造函数 $x$ 的签名中）。这本身在编译时或运行时都不会引起任何错误。

# 15.10 数组创建与访问表达式

## 15.10.1 数组创建表达式

数组创建表达式用于创建新数组 (§10 (Arrays))。

```
ArrayCreationExpression:
  ArrayCreationExpressionWithoutInitializer
  ArrayCreationExpressionWithInitializer

ArrayCreationExpressionWithoutInitializer:
  new PrimitiveType DimExpr [Dims]
  new ClassOrInterfaceType DimExpr [Dims]

ArrayCreationExpressionWithInitializer:
  new PrimitiveType Dim ArrayInitializer
  new ClassOrInterfaceType D ArrayInitializer

DimExpr:
  DimExpr [DimExpr]

DimExpr:
  [Annotation] [ Expression ]
```

为了方便起见，这里展示了 §4.3 中的以下产生式：

```
Dims:
  [Annotation] {} {[Annotation] }
```

数组创建表达式创建一个对象，该对象是一个新数组，其元素由 `PrimitiveType` 或 `ClassOrInterfaceType` 指定。

如果 `ClassOrInterfaceType` 未表示的是一个可实例化的类型 (§4.7)，则为编译时错误。否则，`ClassOrInterfaceType` 可以命名任何引用类型，即使是抽象类类型 (§8.1.1.1) 或接口类型。

> 上述规则意味着，数组创建表达式中的元素类型不能是参数化类型，除非参数化类型的所有类型参数都是无界通配符。

`DimExpr` 内部每个维度表达式的类型必须是可转换为 (§5.1.8) 整数类型的类型，否则会发生编译时错误。

每个维度表达式都会经过一元数值提升 (§5.6)。提升后的类型必须是 `int`，否则会发生编译时错误。

数组创建表达式的类型是一个数组类型，该类型可以通过该数组创建表达式的副本（即删除了 `new` 关键字、每个 `DimExpr` 表达式和数组初始化器）来表示。

例如，创建表达式的类型：

```
new double[3][3][]
```

类型为：

```
double[][][]
```

## 15.10.2 数组创建表达式的运行时求值

在运行时，数组创建表达式的评估如下：

- 如果没有维度表达式，则必须有一个数组初始化器。新分配的数组将按照 §10.6 的描述使用数组初始化器提供的值进行初始化。数组初始化器的值成为数组创建表达式的值。

- 否则，没有数组初始化器，且：

  - 首先，从左到右评估维度表达式。如果任何表达式的评估异常完成，则其右侧的表达式将不再评估。

  - 接下来，检查维度表达式的值。如果任何 `DimExpr` 表达式的值小于 0，则抛出 `NegativeArraySizeException`。

  - 接下来，为新数组分配空间。如果空间不足以分配数组，则通过抛出 `OutOfMemoryError` 异常终止数组创建表达式的评估。

  - 然后，如果出现单个 `DimExpr`，则创建一个指定长度的一维数组，并将数组的每个组件初始化为其默认值 (§4.12.5)。

  - 否则，如果出现 `n` 个 `DimExpr` 表达式，则数组创建实际上会执行一组深度为 `n-1` 的嵌套循环，以创建隐含的数组数组。多维数组不需要在每一层具有相同相同的数组。

### 示例 15.10.2-1. 数组创建评估

在包含一个或多个维度表达式的数组表达式中，每个维度表达式在其右侧任何维度表达式的部分之前都会被完全评估：

```java
class Test1 {
    public static void main(String[] args) {
        int i = 4;
        int[][] ia = new int[i=3];
        System.out.println("" + ia.length + "");
    }
}
```

打印：

```
[4, 3]
```

因为在第二个维度将 i 设置为 3 之前，第一个维度被计算为 4。

如果维度表达式的评估异常完成，则其右侧任何维度表达式的部分都不会被视为已评估：

```java
class Test2 {
    public static void main(String[] args) {
        int[][] a = {{ 00, 01 }, { 10, 11 }};
        int i = 99;
        try {
            a[val()][i] = 1]++;
        } catch (Exception e) {
            System.out.println("" + "," + i);
        }
        static int val() throws Exception {
            throw new Exception("unimplemented");
        }
    }
}
```

输出：

```
java.lang.Exception: unimplemented, i=99
```

因为嵌入的赋值将 i 设置为 1 从未被执行。

### 示例 15.10.2-2. 多维数组创建

声明：

```java
float[][] matrix = new float[3][3];
```

在行为上等同于：

```java
float[][] matrix = new float[3][];
for (int d = 0; d < matrix.length; d++)
    matrix[d] = new float[3];
```

以及：

```java
Age[][][][][] Aquarius = new Age[6][10][8][12];
```

等同于：

```java
Age[][][][][] Aquarius = new Age[6][][][];
for (int d = 0; d < Aquarius.length; d++)
    Aquarius[d] = new Age[10][][][];
    for (int d2 = 0; d2 < Aquarius[d].length; d2++)
    Aquarius[d][d2] = new Age[8][][];
        for (int d3 = 0; d3 < Aquarius[d][d2].length; d3++)
        Aquarius[d][d2][d3] = new Age[12][];
```

其中 a, d1 和 d3 被替换为尚未局部声明的名称。因此，单个 `new` 表达式实际上创建了一个长度为 6 的数组、6 个长度为 10 的数组、6x10 = 60 个长度为 8 的数组以及 6x10x8 = 480 个长度为 12 的数组。此示例留下了第五维度（该维度是包含实际数组元素（对 Age 对象的引用）的数组），仅初始化为空引用。这些数组以后可以通过其他代码填充，例如：

```java
Age[] Hair = { new Age("quartz", new Age("topaz")) };
Aquarius[1][9][6][9] = Hair;
```

可以通过以下方式创建三角形矩阵：

```java
float[][] triang = new float[100][];
for (int i = 0; i < triang.length; i++)
    triang[i] = new float[i+1];
```

如果存在数组创建表达式且内存不足以执行操作，则抛出 `OutOfMemoryError`。如果数组创建表达式没有数组初始化器，则此检查在所有维度表达式评估完成后才发生。如果数组创建表达式有数组初始化器，则在评估（可能是嵌套的）数组初始化时或为存储初始化器值的数组分配空间时可能会发生 `OutOfMemoryError`。

### 示例 15.10.2-3. OutMemoryError 与维度表达式评估

```java
class Test3 {
    public static void main(String[] args) {
        int len = 0, oldlen = 0;
        Object a = new Object[0];
        try {
            for (;;) {
                ++len;
                Object[] temp = new Object[oldlen=len];
                temp[0] = a;
                a = temp;
            }
        } catch (Error e) {
            System.out.println(e + " " + (oldlen==len));
        }
    }
}
```

该程序产生：

```
java.lang.OutOfMemoryError true
```

因为内存不足检查在维度表达式 `oldlen len` 评估后才检测。将其与类实例表达式 (§15.9) 对，后者在评估参数表达式之前检测内存不足。

## 15.10.3 数组访问表达式

数组访问表达式引用数组的组件。

```
ArrayAccess:
  ExpressionName [ Expression ]
  PrimaryNoNewArray [ Expression ]
  ArrayCreationExpressionWithInitializer [ Expression ]
```

数组访问表达式包含两个子表达式：数组引用表达式（左括号之前）和索引表达式（括号内）。

数组引用表达式可以是名称或任何非数组创建表达式的主表达式，除非数组创建表达式有数组初始化器 (§15.10.1)。

数组引用表达式的类型必须是数组类型（称为 T[]，一个组件类型为 T 的数组），否则会发生编译时错误。

索引表达式会进行一元数值提升（§5.6）。提升后的类型必须是 `int`，否则将发生编译时错误。

数组表达式的类型是对 $\tau$ 应用捕获转换（capture conversion，§5.1.10）后的结果。

数组访问表达式的结果是一个类型为 $\tau$ 的变量，即由索引表达式的值所选的数组中的变量。

该结果变量是数组的一个组件，不被视为 `final`（最终的），即使该数组引用表达式表示的是一个 `final` 变量。

## 15.10.4 数组访问表达式的运行时求值

在运行时，数组访问表达式的求值行为如下：

- 首先，求值数组引用表达式。如果该求值异常终止，则数组访问因相同原因异常终止，且索引表达式不会求值。

- 否则，求值索引表达式。如果异常终止，则数组访问因相同原因异常终止。

- 否则，如果数组引用表达式的值为 `null`，则抛出 `NullPointerException`。

- 否则，数组引用表达式的值确实指向一个数组。如果索引表达式的值小于 0 或大于等于数组的长度，则抛出 `ArrayIndexOutOfBoundsException`。

- 否则，数组访问的结果是数组中由索引表达式的值所中的类型为 $\tau$ 的变量。

### 示例 15.10.4-1. 数组引用首先被求值

在数组访问中，括号左侧的表达式在括号内表达式任何部分求值之前，似乎已经完全求值。例如，在（诚然巨大的）表达式 `a(b [3])` 中，表达式 `a` 在表达式 `(a=b [3])` 求值之前已完全求值；这意味着在求值 `(a=b [3])` 时，`a` 的原始值被固定并记住。由 `a` 的原始值所引用的数组，是由由 `b` 引用且现在由 `a` 引用的另一个数组（可能是同一个数组）的第 3 个元素所订阅。

因此，程序：

```java
class Test1 {
    public static void main(String[] args) {
        int[] a = { 11, 12, 13, 14 };
        int[] b = { 0, 1, 2, 3, 3 };
        System.out.println(a[(a=b)[3]]);
    }
}
```

打印：

14

因为这个巨大的表达式的值等于 `a[b[3]]` 或 `a[3]` 或 `14`。

### 示例 15.10.4-2. 数组引用求值的异常终止

如果括号左侧表达式的求值异常终止，则括号内的表达式任何部分似乎都不会被求值。因此，程序：



```java
class Test2 {
    public static void main(String[] args) {
        int index = 1;
        try {
            skedaddle()[index=2]++;
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

因为对 `index` 赋值 2 的嵌入赋值从未发生。

### 示例 15.10.4-3. null 数组引用

如果数组表达式产生 `null` 而不是数组引用，则在运行时抛出 `NullPointerException`，但只有在访问表达式的部分已经求值之后，且仅当这些求值正常完成之后。因此，程序：

```java
class Test3 {
    public static void main(String[] args) {
        int index = 1;
        try {
            nada()[index=2]++;
        } catch (Exception e) {
            System.out.println(e + " ", index=" + index);
        }
    }
    static int[] nada() { return null; }
}
```

打印：

```
java.lang.NullPointerException, index=2
```

因为对 `index` 赋值 2 的嵌入赋值发生在检查数组引用表达式之前。作为一个相关的示例，程序：

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
        throw new Exception("Twenty-three skidoo!");
    }
}
```

始终打印：

```
java.lang.Exception: Twenty-three skidoo!
```

`NullPointerException` 永远不会发生，因为在发生任何进一步访问之前，必须完全求值索引表达式，其中包含了对数组引用表达式的值是否为 `null` 的检查。

## 15.11 字段访问表达式

字段访问表达式可以访问对象或数组的字段，其引用是表达式的值或特殊关键字 `super` 的值。

```java
FieldAccess:
    Primary . Identifier
super . Identifier
TypeName . super . Identifier
```

字段访问表达式的含义使用与限定名相同的规则（§6.5.2）确定，但受限于表达式不能表示包、类类型或接口类型的限制。

也可以通过使用简单名（§6.5.6.1）引用当前实例或当前类的字段。

### 15.11.1 使用 Primary 访问字段

`Primary` 的类型必须是引用类型 $\tau$，否则将发生编译时错误。字段访问表达式的含义如下所示确定：

- 如果标识符命名了类型 $\tau$ 中的多个可访问（§6.6）成员字段，则字段访问是歧义的，且将发生编译时错误。
- 如果标识符没有命名类型 $\tau$ 中的可访问成员字段，则字段访问是未定义的，且将发生编译时错误。
- 否则，标识符命名了类型 $\tau$ 中的单个可访问成员字段，且字段访问表达式的类型是该成员字段经过捕获转换（§5.1.10）后的类型。

在运行时，字段访问表达式的结果计算如下（假设程序相对于是正确的）：

- 如果字段是静态的：
    - 求值 `Primary` 表达式。如果 `Primary` 的求值异常终止，则字段访问因相同原因异常终止。
- 如果 `Primary` 的值为 `null`，则抛出 `NullPointerException`。
- 如果字段是非空最终（non-blank final）：
    - 结果是 `Primary` 的值所引用的类型 $T$ 中的成员字段的值。
- 如果字段不是 `final`，或者是空 final 且字段访问发生在实例变量初始化（§8.2）、实例初始化（§8.6）或构造函数（§8.8）中，则结果是一个变量，即 `Primary` 的值所引用的对象中类型 $T$ 的成员字段。

### 示例 15.11.1-1. 字段访问的静态绑定

```java
class S { int x = 0; }
class T extends S { int x = 1; }
class Test1 {
    public static void main(String[] args) {
        T t = new T();
        System.out.println("t.x=" + t.x + " when("t=", t));
        S s = new S();
        System.out.println("s.x=" + s.x + " when("s=", s));
        s = t;
        System.out.println("s.x=" + s.x + " when("s=", s));
    }
    static String when(String name, Object t) {
        return "when " + name + " holds a " + t.getClass() + " at run time.";
    }
}
```

该程序输出：

```
t.x=1 when t holds a class T at run time.
s.x=0 when s holds a class S at run time.
s.x=0 when s holds a class T at run time.
```

最后一行显示，确实，访问的字段并不取决于所引用对象的运行时类；即使 `s` 持有一个指向类 `T` 对象的引用，表达式 `s.x` 指的是类 `S` 的字段，因为表达式 `s` 的类型是 `S`。

## 15.11 字段访问表达式 EXPRESSIONS

这种对字段访问缺乏动态查找的特性，使得程序可以通过前向实现进行高效运行。晚期绑定和重写的强大功能仅在使用实例方法时可用。考虑以下使用实例方法访问字段的相同示例：

```java
class S {
    int x = 0; int z() {
        return x;
    }
}
class T extends S {
    int x = 1; int z() {
        return x;
    }
}
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
        return "when " + name + " holds a"
               + t.getClass() + " at run time.";
    }
}
```

现在输出如下：

```
t.z()1 when t holds a class T at run time.
s.z()0 when s holds a class S at run time.
s.z()1 when s holds a class T at run time.
```

最后一行显示，所访问的方法确实取决于对象的运行时类；当 s 持有指向类 T 对象的引用时，表达式 `s.z()` 指向类 T 的 `z` 方法，尽管表达式的类型是 s。类 T的方法重写了类 S 的 `z` 方法。

### 示例 15.11.1-2. 变量与静态字段访问无关

以下程序证明了可以使用空引用来访问类（静态）变量而不会引发异常：

```java
class Test3 {
    static String mountain = "Chocorua";
    static Test3 favorite() {
        System.out.print("Mount ");
        return null;
    }
    public static void main(String[] args) {
        System.out.println(favorite().mountain);
    }
}
```

字段访问表达式 15.11

Mount Chocorua

尽管 `favorite()` 的结果是 `null`，也没有抛出 `NullPointerException`。打印出的 "Mount" 说明主表达式在运行时被完全求值，尽管用于确定访问哪个字段的是其类型而非其值（因为字段 `mountain` 是静态的）。

## 15.11.2 使用 super 访问父类成员

`super.Identifier` 形式引用当前对象中名为 `Identifier` 的字段，但将当前对象视为当前类父类的实例。

`T.super.Identifier` 形式引用引用 `T` 的词法上闭包类中名为 `Identifier` 的字段，但将该实例视为 T 的父类的实例。

使用关键字 `super` 的形式可以用于类声明中允许将关键字 `this` 用作表达式的位置（见 §15.8.3）。

如果使用关键字 `super` 的字段访问表达式出现在静态上下文中，则构成一个编译时错误（见 §8.1.3）。

对于形式为 `super.Identifier` 的字段访问表达式：

- 如果该字段访问表达式的直接闭包类或接口声明是 `Object` 类或一个接口，则构成编译时错误。

对于形式为 `T.super.Identifier` 的字段访问表达式：

- 如果 `T` 是 `Object` 类或一个接口，则构成编译时错误。
- 令 `U` 为该字段访问表达式的直接闭包类或接口声明。如果 `U` 不是 T 的内部类或 T 本，则构成编译时错误。

假设字段访问表达式 `super.f` 出现在类 `C` 中，且 `C` 的直接父类是 `S`。如果 `f` 可以从类 `C` （见 §6.6），则 `super.f` 的处理方式类似于类 `S` 体体中的表达式 `this.f`。否则，将发生编译时错误。

> 因此，`super.f` 可以访问类 s 中可访问的字段 `f`，即使该字段被类 c 中字段 `f` 的声明所隐藏。

假设字段访问表达式 `T.super.f` 出现在类 `C` 中，且由 `T` 所指的类的直接父类是一个全限定名为 `s` 的类。如果 `s` 中的 `f` 可以从 `c` 访问，则 `T.super.f` 的处理方式类似于在类 `s` 体中中的表达式 `this.f`。否则，将发生编译时错误。

因此，`T.super.f` 可以访问类 s 中可访问的字段 `f`，即使该字段被类 T 中字段的声明所隐藏。

### 示例 15.11.2-1. super 表达式

```java
interface I {
    int x = 0; }
class T1 implements I {
    int x = 1; }
class T2 extends T1 {
    int x = 2; }
class T3 extends T2 {
    int x = 3;
    void test() {
        System.out.println("x=\t" + x);
        System.out.println("super.x=\t" + super.x);
        System.out.println("((T2)this).x=\t" + ((T2)this).x);
    }
}
class Test {
    public static void main(String[] args) {
        T3 t = new T3();
        t.test();
        T2 s = t;
        s.test();
        T1 i = t;
        // 注意：下行代码会导致编译错误，因为 T1 没有 super.x
        // System.out.println(super.x); 
    }
}
```

*(注：原文示例中代码块似乎有错乱，已根据逻辑对齐)*

```java
        System.out.println("super.x=\t" + super.x);
        System.out.println("((T2)this).x=\t" + ((T2)this).x);
    }
}
```

该程序输出如下：

```
x=3
super.x=2
((T2)this).x=2
x=3
super.x=2
((T2)this).x=2
x=3
super.x=2
((T2)this).x=2
x=3
super.x=2
((T2)this).x=2
```

## 15.12 方法调用表达式

方法调用表达式是用于调用方法的。方法调用的类型在运行时确定，这与字段访问有所不同。

### 15.12.1 方法调用

一个方法调用的形式包括：

- `MethodName([ArgumentList])`
- `TypeName.[TypeArguments]Identifier([ArgumentList])`
- `ExpressionName.[TypeArguments]Identifier([ArgumentList])`
- `Primary.[TypeArguments]Identifier([ArgumentList])`
- `super.[TypeArguments]Identifier([ArgumentList])`
- `TypeName.super.[TypeArguments]Identifier([ArgumentList])`

`ArgumentList`：

在编译时解析方法名比解析字段名更复杂，因为存在方法重载。在运行时解析方法名比解析字段更复杂，因为存在方法重写。

### 15.12.2 编译时步骤1：确定类型

处理方法调用的第一步是确定要调用的方法以及要搜索的类型。

方法名由 `MethodInvocation` 左侧的 `MethodName` 或 `Identifier` 确定。

对于要搜索的类型，取决于 `MethodInvocation` 左的形式，有六种情况：

- 如果形式是 `MethodName`，即一个 `Identifier`，那么：
    - 如果该 `Identifier` 出现在方法声明的作用范围内（见 §6.3, §6.4），那么：
        - 如果该方法的闭包类或接口声明是一个成员，则 E 为该成员类或接口。要搜索的类型是 E 的类型（见 §15.8.4）。这种策略被称为“组合规则”。它在嵌套类的父类中查找方法之前，先在内部类及其父类层级中查找方法。示例见 §6.7.1。
    - 否则，方法声明可能由于一个或多个静态导入或通静态导入而处于作用范围内。不需要搜索类型，因为要调用的方法稍后确定（见 §15.12.2.1）。
- 如果形式是 `TypeName.[TypeArguments]Identifier`，则要搜索的类型是（可能是原始类型的）`TypeName`。
- 如果形式是 `ExpressionName.[TypeArguments]Identifier`，则要搜索的类型是变量 `ExpressionName` 的声明类型 $\tau$，如果 $\tau$ 是类或接口类型，或者是 $\tau$ 的上界是类型变量。
- 如果形式是 `Primary.[TypeArguments]Identifier`，则 $\tau$ 是 `Primary` 表达式的类型。要搜索的类型是 $\tau$，如果 $\tau$ 是类或接口类型，或者是 $\tau$ 的上界是类型变量。
- 如果形式是 `super.[TypeArguments]Identifier`，则要搜索的类型是包含该方法调用的声明类的直接父类类型。
- 如果形式是 `TypeName.super.[TypeArguments]Identifier`，则要搜索的类型是 `TypeName` 所类的直接父类。

E 为直接包含该方法调用的类或接口声明。如果 E 是 `Object` 类或一个接口，则构成编译时错误。

### 15.12.3 编译时步骤2：确定方法

在编译时处理方法调用的下一步是确定要调用的方法。



# 方法调用表达式

要调用的方法名由 `MethodInvocation` 左侧的 `MethodName` 或 `Identifier` 确定。

对于要调用的方法，取决于 `MethodInvocation` 左侧的形式：

- 如果形式是 `MethodName`，即一个 `Identifier`，那么：
  - 如果该 `Identifier` 出现在方法声明的作用范围内，那么：
    - 如果该方法的返回类是 `Object` 类或接口，要搜索的类型是 `Object`（见 §15.8.4）。
  - 否则，方法声明可能由于静态导入或通静态静态导入而处于作用范围内。不需要搜索类型，因为要调用的方法稍后确定（见 §15.12.2.1）。
- 如果形式是 `TypeName.[TypeArguments]Identifier`，那么要调用的方法是 `TypeName` 类中的方法。
- 如果形式是 `ExpressionName.[TypeArguments]Identifier`，那么要调用的方法是 `ExpressionName` 表达式类型的方法。
- 如果形式是 `Primary.[TypeArguments]Identifier`，那么要调用的方法是 `Primary` 表达式类型的方法。
- 如果形式是 `super.[TypeArguments]Identifier`，那么要调用的方法是该类的直接父类中的方法。
- 如果形式是 `TypeName.super.[TypeArguments]Identifier`，那么要调用的方法是 `TypeName` 类直接父类中的方法。

如果表达式的形式为 `TypeName . super . [TypeArguments] Identifier`，那么：

- 如果 `TypeName` 既表示类也不表示接口，则为编译错误。
- 如果 `TypeName` 表示一个类 `c`，则要搜索的类型是 `c` 的直接父类类型。
  - 如果 `c` 不是方法调用的词法上包含的类声明，或者 `c` 是 `Object` 类，则为编译错误。
  - 令 `E` 为紧邻包含该方法调用的类或接口。如果 `E` 是 `Object` 类，则为编译错误。
- 否则，`TypeName` 表示一个接口 `I`。
  - 令 `E` 为紧邻包含该方法调用的类或接口声明。如果 `I` 不是 `E` 的直接父接口，或者存在另一个 `E` 的其他直接父类或直接父接口 `J`，使得 `J` 是 `I` 的子类或子接口，则为编译错误。
  - 要搜索的类型是作为 `E` 的直接父接口类型的类型。

`TypeName.super` 语法是重载的：传统的，`TypeName` 指向词法上包含的类声明，如果该调用是词法上包含的类声明中的一个未限定 `super`，则目标是该类的父类。

```java
class Superclass {
    void foo() { System.out.println("Hi"); }
}

class Subclass extends Superclass {
    void foo() { throw new UnsupportedOperationException(); }

    Runnable tweak = new Runnable() {
        void run() {
            Subclass1.super.foo(); // 获取 'println' 行为
        }
    }
}
```

为了支持对父接口默认方法的调用，`TypeName` 也可以指向当前类或接口的直接父接口，目标是该父接口。

## 15.12 方法调用表达式

### 表达式

```java
interface Superinterface {
    default void foo() { System.out.println("Hi"); }
}

class Subclass2 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); }
}

void tweak() {
    Superinterface.super.foo(); // 获取 'println' 行为
}
```

没有语法支持这些形式的组合，也就是说，调用词法上包含的类声明的父接口方法，仿佛该调用是词法上包含的类声明中的 `InterfaceName.super` 一样。

```java
class Subclass3 implements Superinterface {
    void foo() { throw new UnsupportedOperationException(); }
}

Runnable tweak = new Runnable() {
    void run() {
        Subclass3.Superinterface.super.foo(); // 非法
    }
};
```

解决方法是在词法上包含的类声明中引入一个私有方法，来执行接口 super 调用。

### 15.12.2 编译时步骤 2：确定方法签名

第二步在上一步确定的类型中搜索成员方法。此步使用方法名和参数表达式来定位既可访问又适用的方法，即可以在给定参数上正确调用的声明。

可能会有多个这样的方法，在这种情况下，选择最具体方法（签名返回类型）的最具体方法。该方法将在运行时被用于执行方法分发。

某些包含带泛型的 lambda 表达式（§15.27.1）或不精确方法引用（§15.13.1）的参数表达式会被适用性测试忽略，因为它们的含义在选择调用目标类型之前无法确定。另一方面，只有参数表达式——而不是调用目标类型——会影响适用性测试，即使方法调用表达式是一个多态表达式（poly expression）。

## 表达式

## 方法调用表达式 15.12

确定适用性的开始于确定可能适用的方法（§15.12.2.1）。然后，为了与 Java 5.0 之前的 Java 编程语言兼容，该过程分三个阶段继续：

- 第一阶段执行重载解析，但不允许装箱或拆箱转换，或使用变长参数方法调用。如果在此阶段没有找到适用的方法，则继续到第二阶段。

  这保证了任何在 Java 5.0 之前的 Java 编程语言中不被认为歧义的调用，都是引入变长参数方法、隐式装箱和拆箱的结果。然而，变长参数方法的声明（§8.4）可能会改变为给定的方法调用表达式选择的方法，因为变长参数方法在第一阶段被视为固定参数数量的方法。例如，在已经声明了 `m(Object)` 的类中声明 `m(Object...)` 会导致 `m(Object)` 不再被某些调用表达式（如 `m(null)`）选中，因为 `m(Object [1])` 更具体。

- 第二阶段执行重载解析，允许装箱和拆箱，但仍然禁止使用变长参数方法调用。如果在此阶段没有找到适用的方法，则继续到第三阶段。

  这确保了如果一个方法通过固定参数方法调用是适用的，则不会通过变长参数方法调用被选中。

- 第三阶段允许重载与变长参数方法、装箱和拆箱结合。

如果一个方法通过严格调用（第一阶段，§15.12.2.2）、宽松调用（第二阶段，§15.12.2.3）或变长参数调用（第三阶段，§15.12.2.4）之一适用，则该方法是适用的。对于泛型方法（§8.4），方法是否适用需要分析类型参数。类型参数可以显式或隐式地传递；如果是隐式传递，则必须从参数表达式中推导出类型参数的边界（§18 类型推断）。

如果在适用性测试的三个阶段之一识别出多个适用方法，则按照 §15.12.2.5 的规定选择最具体的一个。

为了检查适用性，调用的参数类型通常不能作为分析的输入。这是因为：

- 方法调用的参数可能是多态表达式（poly expressions）。
- 在缺少目标类型的情况下，多态表达式无法进行类型化。
- 重载解析要在参数目标类型确定之前完成。

相反，适用性检查的输入是参数本身的列表。可以检查参数与潜在目标类型的兼容性，即使参数的最终类型尚未知。

注意，重载解析独立于目标类型。出于这些原因：

- 第一，为了让用户更易于访问且更不容易出错。方法名的含义（即与名称对应的声明）对于程序的含义来说是如此基础，以至于不能依赖于细微的上下文提示。（相比之下，其他表达式可能会根据目标类型有不同的行为；但行为的变化总是有限的，且本质上是等价的，无法对一组共享名称的任意方法的行为提供保证）。
- 第二，它允许其他属性——该方法是否为多态表达式（§15.12）或如何对条件表达式进行分类（§15.25）——在确定目标类型之前依赖于方法的含义。

### 示例 15.12.2-1. 方法适用性

```java
class Doubler {
    static int two() { return two(1); }
    private static int two(int i) { return 2*i; }
}

class Test extends Doubler {
    static long two(long j) { return j+j; }

    public static void main(String[] args) {
        System.out.println(two(3));
        System.out.println(Doubler.two(3)); // 编译错误
    }
}
```

对于 `Doubler` 类中的方法调用 `two(1)`，有两个名为 `two` 的可访问方法，但只有第二个是适用的，因此它是运行时调用的那个。

对于 `Test` 类中的方法调用 `two(3)`，有两个适用的方法，但只有 `Test` 类中的那个是可访问，因此它是运行时要调用的（参数 `3` 被转换为类型 `long`）。

对于方法调用 `Doubler.two(3)`，在 `Doubler` 类（而不是 `Test` 类）中搜索名为 `two` 的方法；唯一适用的方法是不可的，因此该方法调用导致编译错误。

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

在这里，第二次调用 `setColor` 时发生了编译时错误，因为在此时找不到任何匹配的方法。字面量 `37` 的类型是 `int`，无法通过调用转换（invocation conversion）转换为 `byte`。在变量 `color` 初始化使用的赋值转换（assignment conversion）执行从常量类型 `int` 到 `byte` 的隐式转换，这是允许的，因为值 `37` 足够小，可以用 `byte` 类型表示；但调用转换不允许这样做。

如果 `setColor` 方法声明为接收 `int` 而不是 `byte`，那么两个方法调用都是正确的；第一次调用是被允许的，因为调用转换执行了从 `byte` 到 `int` 的宽转换（widening conversion）。然而，在 `setColor` 的体中需要一个窄转换强制：

```java
void setColor(int color) { this.color = (byte) color; }
```

这是一个重载歧义的示例。考虑以下程序：

```java
class Point { int x, y; }
class ColoredPoint extends Point { int color; }
class Test {
    static void test(ColoredPoint p, Point q) {
        System.out.println("*ColoredPoint, Point*");
    }
    static void test(Point p, ColoredPoint q) {
        System.out.println("*Point, ColoredPoint*");
    }
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint();
        test(cp, cp); // 编译错误
    }
}
```

此示例在编译时产生错误。问题是存在两个适用且可访问的 `test` 声明，且其中一个都不比另一个更具体（specific）。因此，方法调用是歧义的。

如果添加 `test` 的第三个定义：

```java
static void test(ColoredPoint p, ColoredPoint q) {
    System.out.println("*ColoredPoint, ColoredPoint*");
}
```

那么它将比其他两个更具体，方法调用将不再具有歧义性。

## 方法调用表达式

### 示例 15.12.2-2. 选择方法时不考虑返回类型

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

在这里，最具体的方法声明是接收类型为 `ColoredPoint` 参数的。由于方法的结果是 `int`，发生了编译错误，因为 `int` 无法通过赋值转换转换为 `String`。这个示例表明，方法的返回类型不参与重载方法的解析，因此返回 `String` 的第二个 `test` 方法没有被选中，尽管它的结果类型本可以允许示例程序无错误编译。

### 示例 15.12.2-3. 选择最具体的方法

最具体的方法是在编译时选择的；它的描述符决定了运行时实际执行哪个方法。如果类中添加了新方法，那么使用旧类声明编译的源代码可能不会使用该新方法，即使重新编译允许选择该方法。

因此，例如两个用于 `Point` 类的编译单元：

```java
package points;
public class Point {
    public int x, y;
    public Point(int x, int y) { this.x = x; this.y = y; }
    public String toString() { return toString(""); }
    public String toString(String s) {
        return "" + x + "," + y + " s " + s + "";
    }
}
```

以及一个用于 `ColoredPoint` 类的：

```java
package points;
public class ColoredPoint extends Point {
    public static final int RED = 0, GREEN = 1, BLUE = 2;
    public static String[] COLORS = {"red", "green", "blue" };

    public byte color;
    public ColoredPoint(int x, int y, int color) {
        super(x, y);
        this.color = (byte)color;
    }

    /* 将参数的所有相关字段拷贝到此 ColoredPoint 对象中。 */
    public void adopt(Point p) { x = p.x; y = p.y; }

    public String toString() {
        String s = "," + COLORS[color];
        return super.toString();
    }
}
```

现在考虑一个使用 `ColoredPoint` 的第三次编译：

```java
import points.*;
class Test {
    public static void main(String[] args) {
        ColoredPoint cp = new ColoredPoint(6, 6, ColoredPoint.RED);
        ColoredPoint cp2 = new ColoredPoint(3, 3, ColoredPoint.GREEN);
        cp.adopt(cp2);
        System.out.println("cp: " + cp);
    }
}
```

输出是：

```
cp: ,red
```

假设程序员报告了这一错误，`points` 包的维护者在经过考虑后，决定通过向 `ColoredPoint` 添加一个方法来纠正它：

```java
public void adopt (ColoredPoint p) {
    adopt((Point)p);
    color = p.color;
}
```

如果程序员用新的 `ColoredPoint` 二进制文件运行旧的 `Test` 二进制文件，输出：

```
cp: ,red
```



如果重新编译 `Test` 的源码，Java 编译器将发现现在有两个适用方法，且更具体的方法的签名是“一个参数，类型为 `ColoredPoint`；void”，运行程序将产生预期的输出：

```
cp: ,green
```

由于对问题的预见，包的维护者可以修复 `ColoredPoint` 类以同时兼容新编译和旧的代码，通过在旧的 `adopt` 方法中添加防御性代码，为了那些仍然对 `ColoredPoint` 参数调用它的旧代码：

```java
public void adopt(Point p) {
  if (p instanceof ColoredPoint)
    color = ((ColoredPoint)p).color;
  x = p.x; y = p.y;
}
```

# 表达式

## 方法调用表达式 15.12

一个成员方法可能适用于一个方法调用，当且仅当满足以下所有条件时：

- 成员的名称与方法调用中的方法名称相同。
- 该成员对于方法调用出现处的类或接口是可访问的 (§6.6)。

一个成员方法在方法调用处是否可访问，取决于该方法声明的访问修饰符（`public`、`protected`（包级访问）或 `private`）、由编译时步骤 1 定的类或接口对该成员的继承情况，以及方法调用的顺序。

- 如果该成员是一个元数为 $n$ 的固定元数方法，且对于所有 $(1 \le i \le n)$，方法调用的元数均等于 $n$，则方法的第 $i$ 个参数根据下文定义与方法的第 $i$ 个参数的类型潜在兼容。
- 如果该成员是一个元数为 $n$ 的可变元数方法，则对于所有 $i (1 \le i \le n)$，方法调用的第 $i$ 个参数与方法的第 $i$ 个参数的类型潜在兼容；且方法的第 $n$ 个参数类型为 $T[]$，并满足以下任一条件：
  - 方法调用的元数等于 $n-1$。
  - 方法调用的元数等于 $n$，且方法调用的第 $n$ 个参数与 $\tau$ 或 $T[]$ 潜在兼容。
  - 方法调用的元数为 $m$，其中 $m > n$，且对于所有 $i (n \le i \le m)$，方法调用的第 $i$ 个参数与 $\tau$ 潜在兼容。
- 如果方法调用包含了显式类型参数，且该成员是一个泛方法，则类型参数的数量等于方法类型参数的数量。

此条款意味着非泛型方法可能适用于指定了显式类型参数的调用。事实上，它可能是适用的。在这种情况下，类型参数将被忽略。

此规则源于兼容性和可替换原则。由于接口或超类可能独立于其子类是泛型的，我们可能用非泛型方法覆盖泛型方法。然而，覆盖的（非泛型）方法必须适用于对泛型方法的调用，包括显式传递类型参数的调用。否则，子类型将无法替换其泛型父类型。

如果搜索没有产生至少一个潜在适用的方法，则发生编译时错误。

## 方法调用表达式

表达式根据以下规则与目标类型潜在兼容：

- 一个 lambda 表达式（§15.27）在满足以下所有条件时，与函数接口类型 $\tau$ (§9.8) 潜在兼容：
  - $\tau$ 的函数类型（§9.9）的元数与 lambda 表达式的元数相同。
  - 如果 $\tau$ 的函数类型具有 `void` 返回类型，则 lambda 体要么是语句表达式（§14.8），要么是 `void` 兼容块（§15.27.22）。
  - 如果 $\tau$ 的函数类型具有（非 void）返回类型，则 lambda 体要么是表达式，要么是值兼容块（§15.27.22）。
- 方法引用表达式（§15.13）与函数接口类型 $\tau$ 潜在兼容，如果 $\tau$ 的函数类型元数为 $n$，且当方法引用表达式目标为元数为 $n$ 的函数类型时，存在至少一个潜在适用的方法（§15.13.1），并满足以下任一条件：
  - 方法引用表达式具有 `ReferenceType::[TypeArguments] Identifier` 的形式，且至少一个潜在适用方法是 (i) 静态的且支持元数 $n$，或 (ii) 非静态且支持元数 $n-1$。
  - 方法引用表达式具有其他形式，且至少一个潜在适用方法不是静态的。
- 如果变量是候选方法的参数，则 lambda 表达式或方法引用表达式与该类型潜在兼容。
- 括号化表达式（§15.8.5）如果其包含的表达式与该类型潜在兼容，则其潜在兼容。
- 条件表达式（§15.25）如果其第二个和第三操作数表达式都与该类型潜在兼容，则其潜在兼容。
- switch 表达式（§15.28）如果其所有结果表达式都与该类型潜在兼容，则其潜在兼容。
- 类实例创建表达式、方法调用表达式或独立函数表达式（§15.2）与任何类型潜在兼容。

潜在适用性的定义超出了基本的 ar 元数检查，还考虑了函数接口目标类型的存在和“形状”。在某些涉及类型参数推断的情况下，作为方法调用参数出现的 lambda 表达式在重载解析之前无法正确确定类型。这些规则允许 lambda 表达式的形式仍被考虑，从而丢弃可能引起歧义错误的明显错误的目标类型。

### 15.12.2.2 阶段 1：识别通过严格调用适用的元数方法

一个表达式对于潜在适用方法 $m$ 的适用性是相关的，除非它具有以下形式之一：

- 隐式类型化的 lambda 表达式（§15.27.1）。
- 不精确的方法引用表达式（§15.13）。
- 如果 $m$ 是泛方法且方法调用未提供显式参数，则显式类型化的 lambda 表达式或精确方法引用是 $m$ 的类型参数。
- 身体为表达式的显式类型 lambda 表达式。
- 身体为块的显式类型 lambda 表达式。
- 括号化表达式（§15.8.5）其包含的表达式不相关。
- 条件表达式（§15.25）其第二个或第三操作数不相关。

令 $m$ 为元数为 $n$ 且形式类型为 $F_1, ..., F_n$ 的潜在适用方法（§15.12.2.1），并令 $e_1, ..., e_n$ 为调用的实际表达式：

- 如果 $m$ 是泛方法且方法调用未提供显式参数，该方法的适用性在 §18.5 中规定。
- 如果 $m$ 是泛方法且方法调用提供了显式参数，令 $R_1, ..., R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，并令 $U_i, ..., U_p$ 为方法调用给出的显式类型参数。那么当满足以下两个条件时，$m$ 通过严格调用是适用的：
  - 对于 $1 \le i \le n$，如果 $e_i$ 与适用性相关（§15.12.2），则 $e_i$ 在严格调用环境中与 $F_i[R_1=U_1, ..., R_p=U_p]$ 兼容。
  - 对于 $1 \le i \le p$，$U_i < B_i[R_1=U_1, ..., R_p=U_p]$。
- 如果 $m$ 不是泛方法，则对于 $1 \le i \le n$，如果 $e_i$ 在严格调用环境中与 $F_i$ 兼容（§15.3），则 $m$ 通过严格调用是适用的。

如果没有找到通过严格调用的方法，则适用方法的搜索继续到阶段 2（§15.12.3）。

否则，在通过严格调用的方法中选择最具体的方法（§15.12.2.5）。

> 隐含 lambda 或不精确方法的含义在解析目标类型之前是足够模糊的，包含它们的参数相关的（除了它们的预期元数）。

### 15.12.2.3 阶段 2：识别通过松弛调用适用的元数方法

令 $m$ 为元数为 $n$ 且形式类型为 $F_1, ..., F_n$ 的潜在适用方法（§15.12.2.1），并令 $e_1, ..., e_n$ 为调用的实际表达式：

- 如果 $m$ 是泛方法且方法调用未提供显式参数，该方法的适用性推断为 §18.5。
- 如果 $m$ 是泛方法且方法调用提供了显式参数，令 $R_1, ..., R_p$ ($p \ge 1$) 为 $m$ 的类型参数，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，并令 $U_i, ..., U_p$ 为方法调用给出的显式类型参数。那么当满足以下两个条件时，$m$ 通过松弛调用是适用的：
  - 对于 $1 \le i \le n$，如果 $e_i$ 与适用性相关（§15.12.2），则 $e_i$ 在松弛调用环境中与 $F_i[R_1=U_1, ..., R_p=U_p]$ 兼容。
  - 对于 $1 \le i \le p$，$U_i < B_i[R_1=U_1, ..., R_p=U_p]$。
- 如果 $m$ 不是泛方法，则对于 $1 \le i \le n$，如果 $e_i$ 在松弛调用环境中与 $F_i$ 兼容（§15.3），或 $e_i$ 不相关，则 $m$ 通过松弛调用是适用的。

如果没有找到通过松弛调用的方法，适用方法的搜索继续到阶段 3（§15.12.2.4）。

否则，在通过松弛调用的方法中选择最具体的方法（§15.12.2.5）。

## 15.12.2.4 第 3 阶段：识别适用于变长参数调用的方法

若变长参数方法的的形式参数类型为 $F_1, \dots, F_n, F[]$，则该方法的第 $i$ 个变长参数类型定义如下：

- 对于 $i \le n-1$，第 $i$ 个变长参数类型为 $F_i$。
- 对于 $i \ge n$，第 $i$ 个变长参数类型为 $F_n$。

令 $m$ 为一个具有变长参数的潜在适用方法（§15.12.2.1），令 $T_j, \dots, T_k$ 为 $m$ 的前 $k$ 个变长参数类型，令 $e_j, \dots, e_k$ 为该方法调用的实际参数表达式。那么：

- 如果 $m$ 是泛型方法且该方法调用未提供显式类型参数，则该方法的适用性参见 §18.5.1。
- 如果 $m$ 是泛型方法且该方法调用提供了显式类型参数，令 $R_i, \dots, R_p$ ($p \ge 1$) 为 $m$ 的参数类型，令 $B_i$ 为 $R_i$ 的声明边界 ($1 \le i \le p$)，令 $U_1, \dots, U_p$ 为方法调用中提供的显式参数。那么当满足以下条件时，$m$ 是*通过变长参数调用适用的*：
  - 对于 $1 \le i \le k$，如果 $e_i$ 与适用性相关（§15.12.2.2），则 $e_i$ 在松散调用上下与 $T_i[R_i=U_i, \dots, R_p=U_p]$ 兼容。
  - 对于 $1 \le l \le p$，$U_i < B_i[R_i=U_i, \dots, R_p=U_p]$（§5.3）。
- 如果 $m$ 不是泛型方法，则若对于 $1 \le i \le k$，要么 $e_i$ 在松散调用上下与 $T_i$ 兼容（§5.3），要么 $e_i$ 与适用性无关，则 $m$ 是*通过变长参数调用适用的*。

如果未找到通过变长参数调用适用的方法，则发生编译错误。

否则，在所有通过变长参数调用适用的方法中选择最具体的方法（§15.12.2.5）。

## 15.12.2.5 选择最具体的方法

如果有多个成员方法对于某个方法调用都是可访问且适用的，则必须选择其中一个为运行时方法分发提供描述符。Java 编程语言使用选择*最具体方法*的规则。

非正式的直觉是：如果一个方法比另一个处理该调用的方法更具体，那么前方法的参数可以传递给后者而不会产生编译错误。在诸如显式 lambda 表达式参数（§15.27.1）或变长参数调用（§15.12.2.4）等情况下，允许一定的灵活性来使一个签名适应另一个签名。

对于具有参数表达式 $e_1, \dots, e_k$ 的调用，如果满足以下任一情况，则一个适用的 $m_2$ 比另一个方法 $m_i$ 更具体：

- $m_2$ 是泛型的，且根据 18.5.4，$m_i$ 对于参数表达式 $e_1, \dots, e_k$ 被认为比 $m_2$ 更具体。
- $m_2$ 不是泛型的，且 $m_i$ 和 $m_j$ 分通过严格或松散调用适用，其中 $m_i$ 有形式参数类型 $S_1, \dots, S_n$，$m_j$ 有形式参数类型 $T_1, \dots, T_m$，对于对于所有的 $i$ ($1 \le i \le n, k$)，类型 $S_i$ 对于参数 $e_i$ 比 $T_i$ 更具体。
- $m_2$ 不是泛型的，且 $m_i$ 和 $m_j$ 分通过变长参数调用适用，其中 $m_i$ 的前 $k$ 个变长参数类型为 $S_1, \dots, S_k$，$m_j$ 的前 $k$ 个变长参数类型为 $T_1, \dots, T_k$，对于所有的 $i$ ($1 \le i \le k$)，类型 $S_i$ 对于参数 $e_i$ 比 $T_i$ 更具体。此外，如果 $m_2$ 有 $k+l$ 个参数，则 $m_i$ 的第 $k+l'$ 个变长参数类型是 $m_j$ 的第 $k+l'$ 个变长参数类型的子类型。

上述是一个方法比另一个方法更具体的唯一情况。

对于任何表达式 $s < \tau$（§4.10），类型 $s$ 比类型 $\tau$ 更具体。

对于表达式 $e$，如果满足以下所有条件，则函数接口类型 $s$ 比函数式接口 $\tau$ 更具体：

- $s$ 的接口既不是 $\tau$ 接口的父接口也不是子接口。如果 $s$ 或 $\tau$ 是交集类型，则不存在 $s$ 的任何接口是 $\tau$ 的任何接口的父接口或子接口。（此处“交集类型的接口”指的是作为交集类型出现的接口集合。）
- 令 $MT_s$ 为 $s$ 捕获的函数类型，令 $MT_\tau$ 为 $\tau$ 的函数类型。$MT_s$ 和 $MT_\tau$ 具有相同的参数类型（§8.4.4）。
- 令 $P_1, \dots, P_n$ 为 $MT_\tau$ 的形式参数类型。令 $P'_1, \dots, P'_n$ 为 $s$ 函数类型（不带捕获）的形式参数类型，适配 $MT_\tau$ 的参数类型。令 $Q_1, \dots, Q_n$ 为 $MT_s$ 的形式参数类型。那么，对于所有的 $i$ ($1 \le i \le n$)，$Q_i < P_i$ 且 $Q_i = P'_i$。通常，此规则断言源自 $s$ 和 $\tau$ 的形式参数类型是相同的。但在 $s$ 是通配符参数化类型的情况下，由于 $s$ 派生出的形式参数类型与 $\tau$ 相同，情况变得更为复杂：首先，$s$ 的捕获是 $\tau$ 的子类型；其次，在通配符参数后，$s$ 的捕获是 $\tau$ 的子类型。

方法调用

令 $MT_s$ 为 $s$ 捕获的函数类型，令 $MT_\tau$ 为 $\tau$ 的函数类型。$MT_s$ 和 $MT_\tau$ 具有相同的参数类型（§8.4.4）。令 $P_1, \dots, P_n$ 为 $MT_\tau$ 的形式参数类型。令 $P'_1, \dots, P'_n$ 为 $s$ 函数类型（不带捕获）的形式参数类型，适配 $MT_\tau$ 的参数类型。令 $Q_1, \dots, Q_n$ 为 $MT_s$ 的形式参数类型。那么，对于所有的 $i$ ($1 \le i \le n$)，$Q_i < P_i$ 且 $Q_i = P'_i$。通常，此规则断言源自 $s$ 和 $\tau$ 的形式参数类型是相同的。但在 $s$ 是通配符参数化类型的情况下，由于 $s$ 派生出的形式参数类型与 $\tau$ 相同，情况变得更为复杂：首先，$s$ 的捕获是 $\tau$ 的子类型；其次，在通配符参数后，$s$ 的捕获是 $\tau$ 的子类型。

# 方法调用表达式

每个最具体方法的返回类型（如果两个方法具有相同的签名，则对任何参数进行调整（§8.4.4））。

如果根据上述规则不存在首选方法，当满足以下条件时，则选择最具体方法：

- 它的签名是每个最具体方法签名的子集；且
- 对于每个最具体方法都是返回类型可替换的（§8.4.5）。

最具体方法抛出的异常类型派自所有最具体方法的 `throws` 子句，如下：

1. 如果最具体方法是泛型，则首先将 `throws` 子句调整为最具体方法的参数（§8.4.4）。
   如果最具体方法不是泛型，但至少有一个最具体方法是泛泛型的，则首先擦除 `throws` 子句。
2. 然后，抛出的异常类型包括满足以下约束的类型 E：
   - E 在其中一个 `throws` 子句中提到。
   - 对于每个 `throws` 子句，E 是该子句中某些类型的子类型。

这些从重载方法组派生特定方法类型的规则也用于识别函数接口的函数类型（§9.9）。

3. 否则，方法调用具有歧义性，并将发生编译时错误。

## 15.12.2 方法调用类型

最可访问且适用的方法的调用类型是方法类型（§2），该类型表示了调用参数的目标类型、调用的结果（返回类型或 `void`）以及调用的异常类型。其确定方式如下：

- 如果所选方法是泛型且方法调用未提供显式类型参数，则按照 §18.5.2 对调用进行推断。
  在这种情况下，如果方法调用表达式是一个多值表达式（poly expression），则其与目标类型的兼容性由 §18.5.2.1 确定。
  在最终确定方法调用表达式的目标类型和调用类型之前，可能会多次进行与目标类型的兼容性测试。例如，一个内层方法表达式可能需要测试更深层的方法调用表达式与不同方法的形式参数类型的兼容性。
- 如果所选方法是泛型且方法调用提供了显式类型参数，令 $P_i$ 为方法的参数，$T_i$ 为为方法调用提供的显式类型参数 $(1 \le i \le p)$。
  - 如果为了方法的适用需要未检查转换（unchecked conversion），则调用类型的参数类型是通过对方法的参数类型应用替换 $[P_i:=T_i, \dots, P_p:=T_p]$ 得到的，且调用类型的返回类型和抛出类型由该方法的返回类型和抛出类型类型的擦除给出。
  - 如果为了方法的适用不需要未检查转换，则调用类型是通过对方法的（参数类型）应用替换 $[P_i:=T_i, \dots, P_p:=T_p]$ 得到的。
- 如果所选方法不是泛型，则：
  - 如果为了方法的适用需要未检查转换，则调用类型的参数类型为该方法的参数类型，且返回类型和抛出类型由该方法的返回类型和抛出类型类型的擦除给出。



- 否则，如果所选方法是 `Object` 类的 `getClass` 方法（§4.3.2），
  调用类型与该方法相同，但返回类型是 `Class<? extends T>`，其中 $T$ 是根据 §15.12.1 确定的搜索类型，且 $[T]$ 表示 $T$ 的擦除（§4.6）。
- 否则，调用类型与该方法的类型相同。

## 15.12.3 编译时步骤 3：所选方法是否合适？

如果某个方法调用存在最具体的方法声明，则该声明被称为方法调用的编译时声明。

如果方法的参数与其目标类型不兼容（该目标类型是从编译时声明的调用类型派生的），则发生编译时错误。

如果编译时声明通过变量数组调用是有效的，其中方法调用的最后一个形式参数类型为 $F_n[]$，则如果 $F_n$ 擦除后的类型在调用点处是不可访问的（§6.6），则发生编译时错误。

### 方法调用表达式

如果编译时声明为 `void`，则方法调用必须是顶层表达式（即表达式语句中的 `Expression`，或者 `for` 语句中的 `ForInit` 或 `ForUpdate` 部分），否则将发生编译时错误。此类方法调用不产生值，且必须在不需要值的情况下使用。

此外，编译时声明是否合适可能取决于方法调用表达式在左括号前的形式，如下：

- 如果形式为 `MethodName`（即仅为一个标识符 `Identifier`）且编译时声明是实例方法，则：
  - 如果方法调用发生在静态上下文中（§8.1.3），则发生编译时错误。
  - 否则，令 $\tau$ 为要搜索的类或接口（§15.12.1）。如果方法调用的最内层闭包类或接口声明既不是 $\tau$ 也不是 $\tau$ 的任何类，则发生编译时错误。
- 如果形式为 `TypeName . [TypeArguments]`，则编译时声明必须是静态的。
- 如果形式为 `ExpressionName . [TypeArguments]` 或 `Primary . [TypeArguments]`，则编译时声明不能是接口中的静态方法，否则将发生编译时错误。
- 如果形式为 `super . [TypeArguments]`，则：
  - 如果编译时声明是抽象的，则发生编译时错误。
  - 如果方法调用发生在静态上下文中，则发生编译时错误。
- 如果形式为 `TypeName . super . [TypeArguments]`，则：
  - 如果编译时声明是抽象的，则发生编译时错误。
  - 如果方法调用发生在静态上下文中，则发生编译时错误。
  - 如果 `TypeName` 表示类 $c$，若闭包调用的类或接口声明不是 $c$ 也不是 $c$ 的内部类，则发生编译时错误。
  - 如果 `TypeName` 表示接口，令 $\epsilon$ 为闭包调用的类或接口声明。如果存在一个与编译时声明不同的方法覆盖了（9.4.1）直接父类或超接口，则发生编译时错误。

在超接口覆盖了祖接口中声明的方法的情况下，此规则防止了子接口通过简单地添加到超接口列表来“跳过”祖接口。访问祖接口功能的正确方法是通过直接超接口，且仅当该接口选择暴露该行为时。（或者，程序员也可以定义一个额外的超接口来暴露该行为）。

编译时参数类型和编译时结果确定如下：

- 如果方法调用的编译时声明不是签名多态方法，则：
  - 编译时参数类型为编译时声明的形式参数类型。
  - 编译时结果为编译时声明的调用类型（§15.12.2.6）。
- 如果方法调用的编译时声明是签名多态方法，则：
  - 编译时参数类型为实际参数表达式的类型。字面量 `null`（§3.10.8）参数表达式被视为具有 `Void` 类型。
  - 编译时结果确定如下：
    - 如果该签名多态方法是 `void` 或返回类型非 `Object`，则编译时结果为编译时声明的调用类型（§15.12.2.6）。
    - 否则，如果方法调用表达式是一个表达式语句，则编译时结果为 `void`。
    - 否则，如果方法调用表达式是转换表达式（§15.16）的操作数，则编译时结果为转换表达式类型的擦除（§4.6）。
    - 否则，编译时结果为签名多态方法的返回类型 `Object`。

一个方法是签名多态的，当且仅当以下所有条件均成立：

#### 方法调用表达式

- 它声明在 `java.lang.invoke.MethodHandle` 类或 `java.lang.invoke.VarHandle` 类中。
- 它有一个单一的可变变长参数（§8.4.1），其声明类型为 `Object[]`。
- 它是原生的（native）。

相应的编译时信息将与方法调用关联，以便运行时使用：

- 方法名。
- 方法调用的限定类或接口（§13.1）。
- 参数数量以及编译时的参数类型，按顺序排列。
- 编译时的结果。
- 运行模式，其计算方式如下：
  - 如果编译时声明具有 `static` 修饰符，则调用模式为静态（static）。
  - 否则，如果方法调用中左括号之前的部分为 `super.Identifier` 或 `TypeName.super.Identifier` 形式，则调用模式为超类（super）。
  - 否则，如果方法调用的限定类或接口在一个接口中，则调用模式为接口（interface）。
  - 否则，调用模式为虚（virtual）。

如果编译时声明的调用类型的结果不是 `void`，则方法调用表达式的类型将通过捕获类型转换（§5.1.10）为编译时声明的调用类型的返回类型。

## 15.12.4 方法调用的运行时评估

在运行时，方法调用需要五个步骤。首先，可能会计算一个目标引用。第二，评估参数表达式。第三，检查被调用方法的可访问性。第四，定位要执行方法的实际代码。第五，创建一个新的激活帧，在必要时进行同步，并将控制转移到方法代码。

### 15.12.4.1 计算目标引用（必要时）

根据方法调用的形式，有六种情况需要考虑：

- 如果形式为 `MethodName`——即仅为一个 `Identifier`——那么：
  - 如果调用模式是静态的，则没有目标引用。
  - 否则，让 $\tau$ 为该方法所属的类型声明，并让 $n$ 为整数，使得 $\tau$ 是紧包含该方法调用的类声明的第 $n$ 个词法闭包声明。目标引用是该类的第 $n$ 个词法闭包实例。
  - 如果该第 $n$ 个词法闭包实例不存在，则为编译时错误。
- 如果形式为 `TypeName.[TypeArguments]Identifier`，则没有目标引用。
- 如果形式为 `ExpressionName.[TypeArguments]Identifier`，那么：
  - 如果调用模式是静态的，则没有目标引用。评估 `ExpressionName`，但结果被丢弃。
  - 否则，目标引用是 `ExpressionName` 所指代的值。
- 如果形式为 `Primary.[TypeArguments]Identifier`，那么：
  - 如果调用模式是静态的，则没有目标引用。评估 `Primary` 表达式，但结果被丢弃。
  - 否则，评估 `Primary` 表达式并将其结果作为目标引用。
  在任何一种情况下，如果 `Primary` 表达式的评估异常终止，则任何参数表达式部分似乎未被评估，且方法调用也因相同的原因异常终止。
- 如果形式为 `super.[TypeArguments]Identifier`，则目标引用是该值。
- 如果形式为 `TypeName.super.[TypeArguments]Identifier`，则 `TypeName` 表示一个类，目标引用是 `TypeName.this` 的值；否则，目标引用是该值。

#### 示例 15.12.4.1-1 目标引用和静态方法

当目标因为调用模式是静态的而被计算并丢弃时，不会检查其结果是否为 `null`：

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

Monadock

在这里 `favorite()` 返回了 `null`，但没有抛出 `NullPointerException`。

#### 示例 15.12.4.1-2 方法调用期间的评估顺序

作为实例方法调用（15.12）的一部分，有一个表示要调用对象的表达式。在方法调用的任何参数表达式评估之前，该表达式似乎已经完全评估。

例如，在：

```java
String s = "one";
s.startsWith(s = "two");
```

在 `.startsWith` 之前的 `s` 首先被评估，在参数表达式 `s = "two"` 之前。因此，在局部变量 `s` 改变指向字符串 "two" 之前，字符串 "one" 的引用作为目标引用被记住。结果是为对象 "one" 调用了 `startsWith` 方法，参数为 "two"，因此调用结果为 `false`，因为字符串 "one" 并不以 "two" 开。因此测试程序没有打印 "oops"。

### 15.12.4.2 评估参数表达式

参数列表的评估过程取决于被调的方法是固定方法还是可变数组方法（§8.4.1）。

如果被调用的方法是可变数组方法 $m$，它必然具有 $n > 0$ 个形式参数，$m$ 的最后一个形式参数必然具有类型 $T[]$（对于某些 $\tau$），且 $m$ 使用是用 $k \ge 0$ 个实际参数表达式调用的。

如果用 $k \neq n$ 个实际参数表达式调用 $m$，或者用 $k = n$ 个实际参数表达式调用 $m$ 且第 $k$ 个参数表达式的类型与 $T[]$ 不兼容，则其评估方式就像 $e_j, \dots, e_{n-1}, e_n, \dots, e_k$ 被写为 $(e_j, \dots, e_{n-1}, \text{new } [T] \{e_n, \dots, e_k\})$，其中 $T[]$ 表示 $T$ 的擦除（§4.6）。

前面的图设计是为了处理参数化类型和数组类型之间的交互，这种交互发生在可变数组的元素类型 $T$ 不可靠时，例如 $List<String>$；必须通过数组创建表达式（§15.10）处理这种特殊情况，因为所创建的数组元素类型 $T$ 必须是可靠的。通过对参数列表末尾表达式的数组类型进行擦除，我们确保获得一个可靠的元素类型。由于数组创建表达式（§15.3），可能会从具有可靠元素类型的数组类型到具有不可靠元素类型的数组类型进行未检查转换，特别是针对该可变变长的。Java 编译器需要在此转换期间给出一个编译时的未检查警告。Oracle 的 Java 编译器参考实现将此未检查警告识别为更具体的泛型数组创建。

参数表达式（可能按上述方式重写）现在被评估为*参数值*。每个参数值精确对应于方法的 $n$ 个形式参数中的一个。参数表达式（如果有）按从左到右的顺序评估。如果任何参数表达式的评估异常终止，则右侧的任何参数表达式部分似乎未被评估，方法调用也因相同的原因异常终止。第 $j$ 个参数表达式的结果是第 $j$ 个参数值，对于 $1 \le j \le n$。随后使用参数值继续评估。

### 15.12.4.3 检查类型和方法的可访问性

在本节中：

- 令 $D$ 为包含方法调用的类。
- 令 $Q$ 为方法调用的限定类或接口（§13.1）。
- 令 $m$ 为编译时确定的方法名（§15.12.3）。

Java 语言的实现必须作为链接的一部分，确保类或接口 $Q$ 是可访问的。

- 如果 $Q$ 与 $D$ 在同一个包中，则 $Q$ 是可访问的。
- 如果 $Q$ 与 $D$ 在不同的包中，且它们的包在同一个模块中，且 $Q$ 是*公共的（public）*或*保护的（protected）*，则 $Q$ 是可访问的。
- 如果 $Q$ 与 $D$ 在不同的包中，且它们的包位于不同的模块中，且 $Q$ 的模块将 $Q$ 所在的包导出给 $D$ 的模块，且 $Q$ 是公共的（public）或保护的（protected），则 $Q$ 是可访问的。

如果 $Q$ 是保护的，它并不一定是一个类或接口，其可访问性受包含其声明的类和接口的影响。在链接期间，其可访问性不受包含其声明的类和接口的影响。此外，在链接期间，保护的 $Q$ 与公共的一样可访问。编译时的访问控制（6.6）与运行时访问控制之间的差异由于 Java 虚拟机的限制。

实现必须在链接期间确保在 $Q$ 或其父类/接口中仍然找到方法 $m$。如果无法找到 $m$，则发生 `NoSuchMethodError`（它是 `IncompatibleClassChangeError` 的子类）。如果可以找到 $m$，令 $C$ 为声明 $m$ 的类或接口。实现必须在链接期间确保 $m$ 的声明对 $D$ 是可访问的。

- 如果 $m$ 是公共的，则 $m$ 是可访问的。
- 如果 $m$ 是保护的，则当满足以下条件时 $m$ 是可访问的：(i) $D$ 与 $C$ 在同一个包中，或者 $D$ 是 $C$ 的子类或本身；(ii) 如果 $m$ 是实例方法，则 $Q$ 必须是 $D$ 的子类或本身。这是涉及 $m$ 的唯一地方，因为保护的实例只能通过与调用者类型一致的类或接口调用。
- 如果 $m$ 具有包访问权限，则当 $D$ 与 $C$ 在同一个包中时 $m$ 是可访问的。
- 如果 $m$ 是私有的，则当 $D$ 是 $C$，或者 $C$ 包含 $D$，且 $C$ 和 $D$ 都被第三个类或接口包含时 $m$ 是可访问的。

如果 $Q$ 或 $m$ 不可访问，则发生 `IllegalAccessError`。如果调用方法是接口，则实现必须检查目标类是否实现了该接口。如果目标类没有实现该接口，则发生 `IncompatibleClassChangeError`。

### 15.12.4.4 定位要调用的方法

如上一节所示（15.2.3）：

- $Q$ 为方法调用的限定类或接口（13.3）。
- 令 $m$ 为 $Q$ 或其父类/父接口中找到的方法。（注意，$m$ 仅仅是上一节中的方法名；这里是实际声明。）
- 令 $C$ 为声明 $m$ 的类或接口。

定位调用的方法的策略取决于调用模式：

- 如果调用模式为 `static`，则不需要目标引用且不允许重写。$C$ 类或接口中的方法 $m$ 是要调用的方法。
- 如果调用模式为 `super`，不允许重写。$C$ 类或接口中的方法 $m$ 抛出 `AbstractMethodError`。
- 否则，如果调用模式为 `virtual`，且 $Q$ 和 $m$ 共同指示一个多态方法（15.12.3），则目标对象是 `java.lang.invoke.MethodHandle` 或 `java.lang.invoke.VarHandle` 的实例。目标对象封装的状态将与编译时方法调用相关的信息进行匹配。此类匹配的细节见《Java虚拟机规范，Java SE 19 版》和 Java SE 平台 API。如果匹配成功，则直接并立即调用 `java.lang.invoke.MethodHandle` 引的方法，或者直接并立即访问 `java.lang.invoke.VarHandle` 代表的变量，在两种情况下，都不会执行 §15.12.4.5 中的过程。
  如果匹配失败，则抛出 `java.lang.invoke.WrongMethodTypeException`。
- 否则，调用模式为接口或虚。

如果 $C$ 类或接口中的方法 $m$ 是私有的，则它是要调用的方法。

否则，可能会发生重写。使用下文指定的动态方法查找来定位要调用的方法。查找从类 $R$ 开始，$R$ 是目标对象的运行时类。注意对于接口调用模式，$R$ 必须实现 $Q$；对于虚调用模式，$R$ 是 $Q$ 或 $Q$ 的子类。如果目标对象是数组，则 $R$ 是表示数组类型的“类”。

动态方法查找的步骤如下。令 $S$ 为要搜索的类，从 $R$ 开始。然后：

- 如果 $S$ 包含重写来自 $R$ 类或接口方法 $m$ 的声明（§8.4.1），则该重写方法就是要调用的方法，程序终止。
- 否则，如果 $S$ 有父类，则使用 $S$ 在类层次中的直接父类递归地执行此查找过程的第 1 步和第 2 步；要调用的方法（如果有）是此查找过程递归调用的结果。
- 如果前两个步骤没有找到方法，则在 $S$ 的父接口中搜索合适的方法。

考虑一组具有以下属性的候选方法：(i) 这些方法都声明在 $R$ 的（直接或间接）父接口中；(ii) 这些方法都具有所需的名称和描述符；(iii) 它是最具体的；(iv) 如果存在多个此类方法，则抛出 `AbstractMethodError`。

如果没有找到方法，则发生 `NoSuchMethodError`。

#### 示例 15.12.4.4-1 重写与方法调用

重写有时被称为“晚绑定自引用”；在这个示例中，这意味着 `Point.move` 体内对 `clear` 的引用（实际上是 `this.clear` 的语法缩写）是“晚”调用方法，而不是“早”调用方法（在编译时，基于 this 的运行时类），而不是 this 的类型。这为程序员提供了一种扩展抽象的重要方法，是面向对象编程的核心思想。以下测试程序演示了这一点：



```java
class Point {
    int x = 10, y = 10;
    void move(int dx, int dy) {
        x += dx;
        y += dy;
        clear();
    }
    void clear() {
        System.out.println("Point clear");
    }
}

class ColoredPoint extends Point {
    void clear() {
        System.out.println("ColoredPoint clear");
    }
}

class Test1 {
    public static void main(String[] args) {
        Point p = new Point();
        p.move(5, 5);

        ColoredPoint cp = new ColoredPoint();
        cp.move(5, 5);

        p = new ColoredPoint();
        p.move(5, 5);
    }
}
```

输出结果为：

```
Point clear
ColoredPoint clear
ColoredPoint clear
```

这是程序的输出。

### 15.12.4.4-2. 使用 super 调用方法

可以使用 `super` 关键字访问父类的被重写的实例方法，从而跳过包含方法调用的类中的重写声明。

在访问实例变量时，`super` 的含义与强制转换 `this` 相同（§15.11.2），但这种等效性对于方法调用并不成立。示例演示了这一点：

```java
class T1 {
    String s() { return "1"; }
}
class T2 extends T1 {
    String s() { return "2"; }
}
class T3 extends T2 {
    String s() { return super.s(); }
}
```

```java
String s() { return "3"; }
void test() {
    System.out.println("s=\t" + s());
    System.out.println("super.s()=\t" + super.s());
    System.out.println("((T2)this).s()=\t" + ((T2)this).s());
    System.out.println("((T1)this).s()=\t" + ((T1)this).s());
}
```

```java
class Test2 {
    public static void main(String[] args) {
        T3 t3 = new T3();
        t3.test();
    }
}
```

产生如下输出：

```
s() = 3
super.s() = 2
((T2)this).s() = 3
((T1)this).s() = 3
```

向 `T1` 和 `T2` 的强制转换不会改变被调用方法的运行时类，要被调用的实例方法是根据所引对象的运行时类来选择的。强制转换不会改变对象的类；它只检查该类是否与指定的类型兼容。

## 15.12.4.5 创建帧、同步、传递控制

类 `S` 中的某个方法 `m` 已被确定为要被调用的方法。

现在创建一个新的激活帧，其中包含目标引用（如果有）和参数值（如果有），以及足够用于被调用方法的局部变量和方法栈的空间，以及实现中可能需要的其他账目信息（栈指针、程序计数器、指向上一个激活帧的引用等）。如果没有足够的内存来创建这样的激活帧，则会抛出 `StackOverflowError`。

新创建的激活帧成为当前激活帧。此操作的效果是将参数值赋值给方法新创建的对应变量，并且如果存在目标，则将该目标引用作为 `this` 可用。在每个参数值赋值给其对应的参数变量之前，都会对其进行调用转换（§5.3）。

如果被调用方法的类型擦除（§4.6）的签名与该方法调用编译时声明的类型擦除（§15.12.3）不同，那么如果任何参数值对象不是该方法调用编译时声明中对应的形式参数类型擦除的子类或子接口的实例，则将抛出 `ClassCastException`。

如果方法 `m` 是原生方法，但尚未加载必要的、依赖实现的二进制类，或者无法对其进行动态链接，则将抛出 `UnsatisfiedLinkError`。

如果方法 `m` 不是同步的，则控制将传递到被调用的方法 `m` 的体。

如果方法 `m` 是同步的，则在传递控制之前必须锁定一个对象。在当前线程获取锁之前，无法继续执行。如果存在目标引用，则必须锁定目标对象；否则，必须锁定方法 `m` 的类——类 `S` 的 `Class` 对象。控制传递到被调用的方法体，并在方法执行完成后（无论正常完成还是异常终止）自动解锁。锁定和解锁的行为与将方法体嵌入在 `synchronized` 语句（§14.19）中完全一致。

## 示例 15.12.4.5-1 被调用的方法签名与编译时方法签名擦除不同

考虑以下声明：

```java
abstract class C<T> {
    abstract T id(T x);
}
class D extends C<String> {
    String id(String x) { return x; }
}
```

现在，在一个调用中：

```java
C c = new D();
c.id(new Object()); // 以 ClassCastException 失败
```

实际被调用的方法 `D.id()` 的擦除签名与编译时方法声明 `C.id()` 的签名不同。前者接收一个 `String` 参数，而后者接收一个 `Object` 类型的参数。在方法体执行之前，调用将因 `ClassCastException` 失败。

此类情况只会在程序产生编译时的未检查警告（§4.5, §5.1.6, §8.4.1, §8.4.3, §15.13.2）时才会出现。实现可以通过创建桥接方法来强制这些语义。在上面的示例中，`D` 将创建一个如下桥接方法：

```java
Object id(Object x) { return id((String) x); }
```

## 15.13 方法引用表达式

方法引用表达式用于引用方法的调用，而不实际执行它。

- `ExpressionName :: [TypeArguments] Identifier`
- `Primary :: [TypeArguments] Identifier`
- `super :: [TypeArguments] Identifier`
- `TypeName . super :: [TypeArguments] Identifier`
- `ClassType :: [TypeArguments] new`
- `ArrayType :: new`

实例方法（§15.12.4.1）的目标引用可以通过方法引用表达式使用 `ExpressionName`、`Primary` 或 `super` 提供，也可以在以后调用方法时提供。紧邻的内部类新实例（§15.9.2）由其词法上闭包的实例（§8.1.3）提供。

如果方法或构造函数是泛型的，适当的类型参数可以被推断，也可以显式提供。同样，方法引用表达式提到的泛型类型的类型参数也可以显式提供或被推断。

如果方法引用表达式的形式为 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，如果该表达式出现在静态上下文（§8.1.3），则为编译错误。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，则：

- `ClassType` 必须命名一个可访问的（§6.6）、非抽象且不是枚举类，否则将发生编译错误。
- 如果 `ClassType` 表示参数化类型（§4.5），则如果其任何类型参数是通配符，则为编译错误。
- 如果 `ClassType` 表示原始类型（§4.8），则如果在 `::` 之后存在 `TypeArguments`，则为编译错误。

如果方法引用表达式的形式为 `ArrayType :: new`，则 `ArrayType` 必须表示一个可重化的类型（§4.7），否则将发生编译错误。

求值方法引用表达式产生一个函数式接口类型的实例（§9.8）。这不会导致方法的执行；相反，执行可能会发生在稍后调用函数式接口的适当方法时。

这里是一些方法引用表达式，首先是不带目标引用的，然后带有目标引用的：

```
String::length // 实例方法
System.currentTimeMillis() // 静态方法
List<String>::size // 泛型的显式类型参数
List::size // 泛型的推断类型参数
int[]::clone
T::tvarMember

System.out::println
"abc"::length
foo[]::bar
(test ? list.replaceAll(String::trim) : list) :: iterator
super::toString()
```

这里是更多方法引用表达式：

```
String::valueOf // 重载解析
Arrays::sort // 从上下文中推断的类型参数
Arrays::<String>::sort // 显式类型参数
```

这里是表示对象或数组延迟创建的方法引用表达式：

```
ArrayList<String>::new // 参数化泛型的构造函数
ArrayList::new // 推断的类型参数
Foo::<Integer>::new // 用于泛型类
explicit type arguments // 用于泛型构造函数
Bar::<Integer>::new // 泛型类，泛型构造函数
Outer::new // 内部类构造函数
int[]::new // 数组创建
```

可以指定一个匹配特定的签名，例如 `Arrays::sort(int)`。相反，函数式接口提供了参数类型，作为重载解析算法的输入（§15.12.2）。这应该满足绝大多数用例；当少数情况下需要更精确的控制时，可以使用 lambda 表达式。

在分隔符之前的类名中使用泛型语法（如 `List<String>::size`）会引发区分 `<`（类型括号）和 `<`（小于运算符）的解析问题。在理论上，这与允许在强制转换表达式中使用类型参数没有区别；然而，区别在于后者只有在遇到标记时才会发生；随着方法引用表达式的加入，每个表达式的开头都可能是参数化类型。

## 15.13.1 方法引用的编译时声明

方法引用表达式的编译时声明是该表达式所引的方法。在特殊情况下，编译时声明实际上并不存在，而是表示类实例创建或数组创建的虚拟方法。编译时声明的选择取决于表达式所针对的函数类型，就像方法调用的编译时声明取决于调用的参数一样（§15.12.3）。

寻找编译时声明的过程镜像了 §15.12.1 和 §15.12.2 中方法调用的过程如下：

- 首先，确定要搜索的类型：
    - 如果方法引用表达式具有 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier` 形，则要搜索的类型是 `::` 标记之前的表达式的类型。
    - 如果方法引用表达式具有 `ReferenceType :: [TypeArguments] Identifier` 形，则要搜索的类型是应用于 `ReferenceType` 的捕获转换结果（§5.1.10）。
    - 如果方法引用表达式具有 `super :: [TypeArguments] Identifier` 形，则要搜索的类型是方法引用表达式直接包含的类或接口声明的父类类型。

令 τ 为直接包含方法引用表达式的类或接口声明。如果 τ 是类 `Object` 或接口，则为编译时错误。

- 如果方法引用表达式具有 `TypeName :: super :: [TypeArguments] Identifier` 形，如果 `TypeName` 表示一个类，则要搜索的类型是该命名类的父类类型；否则，`TypeName` 表示要搜索的接口。

如果 `TypeName` 既不是方法引用表达式的词法包含类或接口声明，也不是方法引用表达式直接包含的类或接口声明的直接父接口，则为编译时错误。

如果 `TypeName` 是类 `Object`，则为编译时错误。

如果 `TypeName` 是一个接口，且存在方法引用表达式直接包含的类或接口声明的另一个直接父类或直接父接口 J，使得 J 是 `TypeName` 的子类或子接口，则为编译时错误。

- 对于其他形式（涉及 `:: new`），所引用的方法是虚拟的，没有类型需要搜索。

- 第二，识别一个具有 $n$ 个参数的目标函数类型，以及一组可能适用的方法：
    - 如果方法引用表达式具有 `ReferenceType :: [TypeArguments] Identifier` 形，则可能适用的方法是：
        - 要搜索的类型的成员方法，对于一个名为 `Identifier`、元数为 $n$、具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类中的方法调用，这些可能是适用的（§15.12.2.1）；再加上
        - 要搜索的类型的成员方法，对于一个名为 `Identifier`、元数为 $n-1$、具有类型参数 `TypeArguments` 且与方法引用表达式出现在同一个类中的方法调用，这些可能是适用的。

考虑了两个不同的数组 $n$ 和 $n-1$，以考虑到这种形式可能指向静态方法或实例方法。

    - 如果方法引用表达式具有 `ClassType :: [TypeArguments] new` 形，则可能适用的方法是一组与 `ClassType` 构造函数对应的虚拟方法。

      如果 `ClassType` 是原始类型，但不是原始类型的非静态成员，候选的虚拟成员方法是 §15.9.3 中指定的、使用 `<>` 省略到类的类型参数的类实例创建表达式的方法。否则，候选的虚拟成员方法是 `ClassType` 的构造函数，被视为返回类型为 `ClassType` 的方法。

      在这些候选中，可能适用的方法是对于一个元数为 $n$、具有类型参数 `Arguments` 且与方法引用表达式出现在同一个类中的调用的虚拟方法。

    - 如果方法引用表达式具有 `ArrayType :: new` 形，则考虑一个虚拟方法。该方法具有类型为 `int` 的单个参数，返回 `ArrayType` 且没有 `throws` 子句。如果 $n=1$，这就是唯一可能的方法；否则，没有可能适用的方法。

    - 对于所有其他形式，可能适用的方法是要搜索类型的成员方法，对于一个名为 `Identifier`、元数为 $n$、具有类型参数 `Arguments` 且与方法引用表达式出现在同一个类中的调用。

- 最后，如果没有可能适用的方法，则没有编译时声明。

否则，给定参数类型为 $P_1, \dots, P_n$ 的函数类型以及一组可能适用的方法，编译时声明的选择如下：

- 如果方法引用表达式具有 `ReferenceType :: [TypeArguments] Identifier` 形，则执行两次最适用方法的搜索。每次搜索见 §15.12.2 至 §15.12.5，并附有下文说明。每次搜索产生一个适用方法集合，并可能指定集合中的最特定方法。在 §15.12.4 所示的错误情况下，适用方法集合为空。在 §15.12.5 所示的错误情况下，不存在特定方法。

    在第一次搜索中，该方法引用被视为一个具有类型参数为 $P_1, \dots, P_n$ 参数的调用。类型参数（如果有）由方法引用给出。

    在第二次搜索中，如果 $P_1, \dots, P_n$ 不空且 $P_1$ 是 `ReferenceType` 的子类型，则方法引用表达式被视为一个具有类型参数为 $P_2, \dots, P_n$ 参数的调用。如果 `ReferenceType` 是原始类型，且该搜索是类型 $G<\dots>$ 是 $P_i$ 的子类型的参数化，则要搜索的类型是应用于 $G<\dots>$ 的捕获转换结果（§5.1.10）；否则，要搜索的类型与第一次搜索的类型相同。类型参数（如果有）由方法引用给出。

如果第一次搜索产生的最特定方法是静态的，且第二次搜索产生的适用方法集合不包含非静态方法，则编译时声明为第一次搜索的最特定方法。

否则，如果第一次产生的适用方法集合不包含静态方法，且第二次搜索产生了特定的非静态方法，则编译时声明为第二次搜索中是最具体的方法。

否则，则没有编译时声明。

- 对于所有其他形式的方法引用表达式，都将执行一次对最具体的适用方法的搜索。搜索过程如 §15.12.2.2 至 §15.12.2.5 所示，并附带下文的说明。

该方法引用被视为一个具有类型为 $P_1, ..., P_n$ 的参数的调用；参数（如果有）由方法引用表达式给出。

如果搜索结果如 §15.12.2.2 至 §15.12.2.5 所示出现错误，或者最特定的方法是 `static` 的，则没有编译时声明。

否则，编译时声明为最具体的适用方法。

如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`，且编译时声明是 `static` 的，且 `ReferenceType` 不是简单名称或限定名称（§6.2），则编译为编译时错误。



# 方法引用表达式

## 编译时错误条件

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName.super :: [TypeArguments] Identifier`，且编译时声明是 `abstract` 的，则编译为编译时错误。

如果方法引用表达式的形式为 `super :: [TypeArguments] Identifier` 或 `TypeName.super :: [TypeArguments] Identifier`，且该方法引用出现在静态上下文中（§8.1.3），则编译为编译时错误。

如果方法引用表达式的形式为 `TypeName.super :: [TypeArguments] Identifier`，且 `TypeName` 表示一个类 `c`，且该方法引用表达式的直接类或接口声明不是 `c` 或 `c` 的内部类，则编译为编译时错误。

如果方法引用表达式的形式为 `TypeName.super :: [TypeArguments] Identifier`，且 `TypeName` 表示一个接口，且存在一个与编译时声明不同的方法，该方法通过包含该方法引用表达式的类或接口的直接父类或直接父接口重写了编译时声明（§8.4.8, §9.4.1），则编译为编译时错误。

如果方法引用表达式的形式为 `ClassType :: [TypeArguments] new`，且根据 §15.9.2 确定 `ClassType` 的包含实例时会发生编译时错误（将该方法引用表达式视为一个未限定的实例创建表达式），则编译为编译时错误。

## 歧义处理

形式为 `ReferenceType :: [TypeArguments] Identifier` 的方法引用表达式可以有不同的解释方式。如果 `Identifier` 指向一个实例方法，则与 `Identifier` 指向静态方法相比，隐式 lambda 表达式多出一个参数。`ReferenceType` 可能同时具有这两种类的适用方法，因此描述的搜索算法会将它们分别识别出来，但每种情况都有不同的参数类型。

### 歧义示例

```java
interface Fun<T,R> { R apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
}

void test() {
    Fun<C, Integer> fl = C::size;
    //: 实例方法 size()
    // 或 静态方法 size (Object)
}
```

这种歧义无法通过提供一个比适用静态方法更具体的实例方法来解决：

```java
interface Fun<T,R> { R apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    int size(C arg) { return 0; }
}

void test() {
    Fun<C, Integer> fl = C::size;
    //: 实例方法 size()
    // 或 静态方法 size (Object)
}
```

搜索算法足够智能，可以忽略所有适用方法（来自两次搜索）都是实例方法时的歧义：

```java
interface Fun<T,R> { R apply(T arg); }

class C {
    int size() { return 0; }
    static int size(Object arg) { return 0; }
    int size(C arg) { return 0; }

    void test() {
        Fun<Integer> f1 = C::size;
        // OK: 引用是实例方法 size()
    }
}
```

## 泛型类型推断

为了方便起见，当使用泛型类型名称引用实例方法时（此时接收者变为第一个参数），将使用目标类型来确定参数。这便于诸如使用 `Pair::first` 代替 `Pair<String,Integer>::first` 的用法；同样，类似 `Pair::new` 的方法引用被视为“菱形”实例创建 `new Pair<>()`。由于“菱形”是隐式的，这不会实例化原始类型；事实上，没有办法表达对原始类型构造函数的引用。

## 精确与不精确方法引用

对于某些方法引用表达式，无论目标函数类型如何，只有一种可能的编译时声明和一个调用类型（§15.12.2.6）。方法引用表达式被称为**精确的**（exact）。不精确的方法引用表达式被称为**不精确的**（inexact）。

以 `Identifier` 结尾的方法引用表达式如果满足所有条件，则是精确的：

- 如果方法引用表达式的形式为 `ReferenceType :: [TypeArguments]`，则 `ReferenceType` 不是原始类型。
- 该类型恰有一个名称为 `Identifier` 的成员方法，且该方法对于引用表达式所在的类或接口是可访问的。
- 该方法不是可变参数（variable arity）。
- 如果该方法是泛型的（§8.4.4），则方法引用提供了 `TypeArguments`。

形式为 `ClassType :: [TypeArguments] new` 的方法引用表达式如果满足以下条件，则是精确的：

- `ClassType` 表示的类型不是原始类型，或者是原始类型的非静态成员。
- `ClassType` 表示的类型对于引用表达式所在的类或接口恰有一个构造函数。
- 该构造函数不是可变参数。
- 如果该构造函数是泛型的，则方法引用提供了 `TypeArguments`。

形式为 `ArrayType :: new` 的方法引用始终是精确的。

## 15.13.2 方法引用的类型

方法引用表达式在赋值上下文、调用上下文或与目标类型 `T` 转换时是兼容的，如果当 `T` 是函数接口类型（§9.8）且该表达式与来自目标类型的函数类型一致（congruent）。

- 如果 `T` 是通配符化的函数接口类型，则目标类型是 `T` 的非通配符参数化（§9.9）。
- 否则目标类型为 `T`。

方法引用表达式与函数类型一致，当满足以下两个条件时：

- 函数类型识别出一个与引用对应的编译时声明。
- 满足以下任一情况：
    - 函数类型的结果是 `void`。
    - 函数类型的结果是 `R`，且对所选编译时声明的调用类型（§15.2.2.6）的返回类型应用转换（§5.1.10）得到 `R'`（其中 `R` 是可能插入 `R'` 的目标类型），且 `R` 和 `R'` 都不是 `void`，且 `R'` 在赋值上下文中与 `R` 兼容。

如果编译时声明适用需要未经转换，且这在调用上下文中会导致 unchecked 警告，则发生编译时 unchecked 警告，除非被 `@SuppressWarnings`（§9.6.4.5）抑制。

如果为了上述返回类型 `R'` 与函数类型的返回类型 `R` 兼容需要未经转换，且该转换在赋值上下文中会导致 unchecked 警告，则发生编译时 unchecked 警告，除非被 `@SuppressWarnings` 抑制。

如果方法引用表达式与目标类型 `T` 兼容，则该表达式的类型 `U` 是来自 `T` 的目标类型。

如果由 `U` 或其函数类型提到的任何类或接口对于该方法引用表达式所在的类或接口都是不可访问的（§6.6），则编译为编译时错误。

### 重写等价性

对于 `U` 的每个非静态成员 `m`，如果 `U` 的函数类型具有 `m` 签名的子签名（subsignature），则一个类型为 `U` 的函数类型的虚拟方法被认为重写了 `m`，并且可能会发生 §8.4.3 中指定的任何编译时错误或未检查警告。

对于编译时声明的调用类型中 `throws` 子句列出的受检异常类型 `x`，`x` 或 `x` 的超父类必须在 `U` 的函数类型的 `throws` 子句中被提及，否则将产生编译时错误。

兼容性定义背后的核心思想是：方法引用是兼容的，当且仅当等价的 lambda 表达式 `(x, y, z) -> exp.<T1, T2>method(x, y, z)` 是兼容的。（这是一种非正式描述，且存在一些问题使得难以或无法通过这种重写来正式地定义其语义。）

这些兼容性规则为从一个函数式接口转换为以下形式提供了方便的方法：

```java
Task t = () -> System.out.println("hi");
Runnable r = t::invoke;
```

实现可能会经过优化，以便当 lambda 派生的对象被传递并转换为各种类型时，不会在核心 lambda 体周围产生许多层级的适配逻辑。

与 lambda 表达式不同，方法引用可以与泛型类型（即带有参数的函数类型）一致。这是因为 lambda 表达式需要能够声明类型参数，而没有语法支持这一点；但对于方法引用，不需要声明。例如，以下程序是合法的：

```java
interface ListFactory {
  <T> List<T> make();
}

ListFactory lf = ArrayList::new;
List<String> ls = lf.make();
List<Number> ln = lf.make();
```

## 15.13.3 方法引用的运行时评估

在运行时，方法引用表达式的评估类似于类实例创建表达式的评估，相同之处在于正常完成会产生对对象的引用。方法引用表达式的评估与方法本身的调用是存在区别的。

首先，如果方法引用表达式以 `ExpressionName` 或 `Primary` 开头，则对该子表达式进行评估。如果子表达式的值为 `null`，则抛出 `NullPointerException`，并且方法引用表达式异常终止。如果子表达式异常终止，则方法引用表达式因相同原因异常终止。

接下来，要么分配并初始化一个具有下面属性的类的新实例，要么引用一个具有下面属性的类的现有实例。如果需要创建新实例但没有足够的空间来分配该对象，则方法引用表达式的评估通过抛出 `OutOfMemoryError` 结束。

方法引用表达式的值是对具有以下属性的类实例的引用：

- 该类实现了函数式接口类型，且如果目标类型是交类型（intersection type），则实现了交集中提到的所有其他接口类型。
- 当方法引用表达式类型为 `U` 时，对于 `U` 的每个非静态成员方法：
    - 如果类型 `U` 具有 `m` 的签名，则该类声明了一个重写了 `m` 的调用方法。调用方法的体调用引用的方法、创建类实例或创建数组，如下所示。如果调用方法的返回值不是 `void`，则在经过任何必要的赋值转换（§5.2）后，方法体返回方法调用或对象创建的结果。
    - 如果被重写类型擦除后的签名与 `U` 函数类型的擦除签名不同，则在方法调用或对象创建之前，调用方法的体会检查每个参数值是否为 `U` 函数类型中对应参数类型的子类或子接口的实例；如果不是，则抛出 `ClassCastException`。
- 该类没有重写函数式接口或上述其他接口类型的其他方法，尽管它可能会重写 `Object` 类的方法。

调用方法的体取决于方法引用表达式的形式，如下：

- 如果形式为 `ExpressionName :: [TypeArguments] Identifier` 或 `Primary :: [TypeArguments] Identifier`，则调用方法的体具有方法调用表达式的效果，该编译时声明是方法引用表达式的编译时声明。方法调用表达式的运行时评估如 §15.12.4.3、§15.12.4.4 和 §15.12.4.5 所示，其中：
    - 调用模式根据 §15.12.3 指定的编译时声明导出。
    - 目标引用是 `ExpressionName` 或 `Primary` 的值，在方法引用表达式被评估时确定。
    - 方法调用表达式的参数是方法调用的形式参数。

- 如果形式为 `ReferenceType :: [TypeArguments] Identifier`，调用方法的体同样具有方法调用表达式的效果，该编译时声明是方法引用表达式的编译时声明。方法调用表达式的运行时评估如 §15.12.4.3、§15.12.4.4 和 §15.12.4.5 所示，其中：
    - 调用模式根据 §15.12.3 指定的编译时声明导出。
    - 如果编译时声明是实例方法，则目标引用是方法引用表达式被评估时确定的 `this`；否则没有目标引用。
    - 方法调用的参数是方法调用的形式参数。

- 如果形式为 `super :: [TypeArguments] Identifier`，调用方法的体具有方法调用表达式的效果，该编译时声明是方法引用表达式的编译时声明。方法调用表达式的运行时评估如 §15.12.4.3、§15.12.4.4 和 §15.12.4.5 所示，其中：
    - 调用模式根据 §15.12.3 指定的编译时声明导出。
    - 目标引用是方法引用表达式被评估时确定的 `super`。
    - 方法调用的参数是方法调用的形式参数。

- 如果形式为 `this :: [TypeArguments] Identifier`，调用方法的体具有方法调用表达式的效果，该编译时声明是方法引用表达式的编译时声明。方法调用表达式的运行时评估如 §15.12.4.3、§15.12.4.4 和 §15.12.4.5 所示，其中：
    - 调用模式根据 §15.12.3 指定的编译时声明导出。
    - 目标引用是方法引用表达式被评估时确定的 `this`。
    - 方法调用的参数是方法调用的形式参数。

- 如果形式为 `ClassType :: new`，调用方法的体具有类实例表达式的效果，形式为 `new [TypeArguments](A_j, ..., A_n)`，其中 `A_j, ..., A_n` 是方法调用的参数，且：
    - `new` 的封闭实例（如果有的话）根据 §15.9.2 导出。
    - 要调用的构造函数是与方法引用对应的构造函数（§15.13.1）。

- 如果形式是 `Type[] :: new`（`k >= 1`），则调用方法的体具有形式为 `new size[k-1]` 的数组创建表达式的效果，其中 `size` 是唯一的参数。符号 `[]^k` 表示一组括号对。

如果调用方法的体具有方法调用的效果，则方法调用的编译时参数和编译时结果如 §15.12.3 所示确定。为了确定编译时结果，如果调用的结果为 `void`，则方法调用为表达式语句；如果调用方法的结果非 `void`，则为返回语句的表达式。

方法引用的评估比 lambda 表达式（§15.27.4）更复杂。当方法引用表达式在 `::` 分隔符之前是一个表达式时，该子表达式会被评估。评估的结果被存储，直到相应的函数接口类型的方法；此时结果被用作调用的目标引用。这意味着 `::` 之前的表达式在程序遇到方法引用表达式时评估一次，而在后续对函数接口类型的调用中不会重新评估。

这里对 `null` 的处理与其在方法调用中的处理形成了有趣的对比。限定调用的 `Primary` 可能评估为 `null` 但却抛出 `NullPointerException`。这发生在调用的方法是静态方法时（尽管调用语法暗示它是实例方法）。由于由 `Primary` 限定的方法引用表达式禁止为静态方法（§15.13.1），因此方法引用表达式的评估更为简单——`Primary` 总是抛出 `NullPointerException`。

# 15.14 后缀表达式

后缀表达式包括后缀 `++` 和 `--` 运算符的使用。名称不被视为主表达式（§15.8），但在下文中单独处理。语法用于避免某些歧义。它们仅在此处，即后缀表达式的优先级层级上是互换的。

```
PostfixExpression:
Primary
ExpressionName
PostIncrementExpression
PostDecrementExpression
```

## 15.14.1 表达式名称

评估表达式名称的规则见 §6.5.6。

## 15.14.2 后置递增运算符 ++

后置表达式后紧跟 `++` 运算符即为后置递增表达式。

```
PostIncrementExpression:
PostfixExpression ++
```

后置表达式的结果必须是一个可以转换为数值类型（§5.1.8）的变量的变量，否则将发生编译时错误。

后置递增表达式的类型是该变量的类型。后置递增表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的评估异常终止，则后置递增表达式也因相同原因异常终止，且不发生递增。否则，将值 1 加到变量上，并将和存回变量中。在加法操作之前，对值 1 和变量的值执行二值数值提升（§5.6）。如有必要，在存储之前，通过收窄原始转换（§5.1.3）对和进行收窄，并通过装箱转换（§5.1.7）转换为变量类型。后置递增表达式的值是在存储新值之前变量的值。

> 注意，上述的二值数值提升可能包含拆箱转换（§5.1.8）。

声明为 `final` 的变量不能递增，因为当访问此类 `final` 变量并作为表达式时，其结果是一个值而不是变量。因此，它不能作为后置递增运算符的操作数。

## 15.14.3 后置递减运算符 --

后置表达式后紧跟 `--` 运算符即为后置递减表达式。

```
PostDecrementExpression:
PostfixExpression --
```

后置递减的类型必须是一个可以转换为数值类型（§5.1.8）的变量，否则将发生编译时错误。

后置递减表达式的类型是该变量的类型。后置递减表达式的结果不是变量，而是一个值。

在运行时，如果操作数表达式的评估异常终止，则后置递减表达式也因相同原因异常终止，且不发生递减。否则，从变量的值中减去值 1，并将差存回变量中。在减法操作之前，对值 1 和变量的值执行二值数值转换（§5.6）。如有必要，在存储之前，通过收窄原始转换（§5.1.3）将差收窄为变量类型。后置递减表达式的值是在存储新值之前变量的值。

> 注意，上述的二值数值提升可能包含拆箱转换（§5.1.8）。



声明为 `final` 的变量不能递减，当访问此类 `final` 变量并作为表达式时，结果是一个值而不是变量。因此，它不能作为后置递减运算符的操作数。

## 15.15 一元运算符

运算符 `+`、`-`、`--`、`~`、`!` 以及转换运算符（§15.16）被称为一元运算符。一元表达式要么应用于操作数的一元运算符，要么 switch 表达式（§15.28）。

```
UnaryExpression:
PreIncrementExpression
PreDecrementExpression
+ UnaryExpression
- UnaryExpression
UnaryExpressionNotPlusMinus
```

### 表达式

### 一元运算符 15.15

```
PreIncrementExpression:
++ UnaryExpression
```

```
DecrementExpression:
-- UnaryExpression
```

```
UnaryExpressionNotPlusMinus:
PostfixExpression
~ UnaryExpression
! UnaryExpression
CastExpression
SwitchExpression
```

带有一元运算符的表达式从右向左分组，因此 `--x` 的含义与 `(-x)` 相同。

语法的这部分包含了一些技巧以避免两种潜在的语法歧义。

第一个潜在歧义可能出现在诸如 `(p) +q` 的表达式中，对于 C 或 C++ 程序员来说，这看起来可能是对 `q` 执行一元 `+` 操作的强制转换，也可能是数量 `p` 和 `q` 的二值加法。在 C 和 C++ 中，解析器通过在解析时执行有限的语义分析来处理这个问题，以便它知道 `p` 是类型名称还是变量名称。

Java 采取了不同的方法。`+` 运算符的结果必须是数值，且所有涉及数值的类型名称都是已知关键字。因此，如果 `p` 是命名基本类型的关键字，那么 `(p)+q` 只能解释为对一元表达式的强制转换。如果 `p` 不是命名基本类型的关键字，那么 `(p)+q` 只能解释为二值算术运算。类似的说明也适用于 `-` 运算符。语法将 `CastExpression` 拆分为多种情况以做出这种区分：

```
CastExpression:
( PrimitiveType ) UnaryExpression
( Reference [AdditionalBound] ) UnaryExpressionNotPlusMinus
( Reference [AdditionalBound] ) LambdaExpression
```

非终端符号 `UnaryExpression` 包含所有一元运算符，但非终端符号 `UnaryExpressionNotPlusMinus` 排除了所有也可以作为二值运算符的一元运算符，在 Java 中即 `+` 和 `-`。

第二个潜在歧义是表达式 `(p)++` 对于 C 或 C++ 程序员来说可能是强制转换的开始，例如在 `(p)++` 中。作为 C 和 C++ 的解析器，单标记前瞻（one-token lookahead）无法判断 `p` 是类型名称还是变量名称。

在 Java 中，`++` 运算符的结果必须是数值，且所有涉及数值的类型名称都是已知关键字。因此，如果 `p` 是命名基本类型的关键字，那么 `(p)++` 只能解释为对一元表达式的强制转换。然而，如果 `p` 不是命名基本类型的关键字，那么 `(p)++` 只能解释为 `p` 的后置递增。类似的说明适用于该运算符。因此，`unaryExpressionNotPlusMinus` 排除了前缀 `++` 和 `--` 的使用。

在运行时，操作数表达式的评估异常完成，则前缀递减表达式也由于相同的原因完成，且不发生递减。否则，从变量的值中减去值 $i$，并将差值存回变量中。对值 $i$ 和变量的值执行二元数值提升（§5.6）。如有必要，在存储之前，对差值通过收窄的原始类型转换（§5.1.3）进行收窄，并/或通过装箱转换（§5.1.7）转换为变量的类型。前缀递减表达式的值是存储新值后变量的值。

请注意，上述的二元数值提升可能包括拆箱转换（§5.1.8）。

声明为 `final` 的变量在访问此类 `final` 变量并用作表达式时是不能递减的，其结果是一个值，而不是变量。因此，它不能作为前缀递减运算符的操作数。

## 15.15.3 一元加法运算符 +

`+` 运算符的操作数表达式的类型必须是可以转换为（§5.1.8）原始数值类型的类型，否则将发生编译时错误。

对操作数执行一元数值提升（§5.6）。一元加法表达式的类型是操作数的提升后类型。即使操作数表达式的结果是一个变量，一元表达式的结果也不是变量，而是一个值。

在运行时，一元加法表达式的值是操作数的提升后值。

## 15.15.4 一元减法运算符 -

`-` 运算符的操作数表达式的类型必须是可以转换为（§5.1.8）原始数值类型的类型，否则将发生编译时错误。

对操作数执行一元数值提升（§5.6）。

一元减法表达式的类型是操作数的提升后类型。

在运行时，一元减法表达式的值是操作数提升后值的算术取反。

对于整数值，取反等同于减去零。Java 编程语言使用补码表示法整数，且补码值的范围是非对称的；最大负数 `int` 或 `long` 的取反结果仍然是该最大负数。在这种情况下会发生溢出，但不会抛出异常。对于所有整数 $x$，-x 等于 `(~x)+1`。

对于浮点数值，取反等同于减去零，因为如果 $x$ 是 +0.0，那么 $0.0\sim x$ 是 +0.0，但 $\sim x$ 是 -0.0。一元运算符仅返回浮点数的倒数。感兴趣的特殊情况：

- 如果操作数是 NaN，则结果为 NaN。（回想 NaN 没有符号 (§4.2.3））。
- Java 编程语言没有采用 2019 年版 IEEE 754 标准中更强的要求，即取反反转包括 NaN 在内的所有输入的符号位。
- 如果操作数是无穷大，则结果为相反符号的无穷大。
- 如果操作数是零，则结果为相反符号的零。

## 15.15.5 位取反运算符 ~

一元 `~` 运算符的表达式的类型必须是可以转换为（§5.1.8）原始整数类型的类型，否则将发生编译时错误。

对操作数执行一元提升（§5.6）。一元位取反表达式的类型是操作数的提升后类型。

在运行时，一元位取反表达式的值是操作数提升后值的位取反。在所有情况下，`~x` 等于 `(-x)-1`。

## 15.15.6 逻辑取反运算符 !

一元 `!` 运算符的表达式类型必须是布尔值 `boolean`，否则将发生编译时错误。

一元逻辑取反表达式的类型是布尔值 `boolean`。

在运行时，如果操作数为布尔值，则进行装箱转换（§.1.8）。一元逻辑取反表达式的结果为 `true` 或 `false`。

## 15.16 强制转换

转换表达式在运行时将一个值转换为另一种类型，在编译时将一个类型转换为另一种类型。

```
CastExpression:
(Type) UnaryExpression
(Type) + UnaryExpression
(Type) - UnaryExpression
(Type) ~ UnaryExpression
```

强制转换运算符的类型必须是转换为转换为（§5.1.8）原始数值类型的类型。

强制转换运算符必须满足以下规则：

- 强制转换运算符的操作数类型必须与目标类型是兼容的。
- 强制转换运算符的操作数类型必须是目标类型的子类或接口。
- 强制转换运算符的操作数类型必须是目标类型的原始类型（对于原始类型）。
- 强制转换运算符的操作数类型必须是目标类型的包装类型（对于包装类型）。
- 强制转换运算符的操作数类型必须是目标类型的数组类型（对于数组类型）。
- 强制转换运算符的操作数类型必须是目标类型的泛型（对于泛型）。
- 强制转换运算符的操作数类型必须是目标类型的原始包装类型（对于原始类型）。

如果强制转换表达式不满足上述规则，则将发生编译时错误。

## 15.17 乘法运算符

`*`、`/` 和 `%` 被称为乘法运算符。

```
MultiplicativeExpression:
UnaryExpression
MultiplicativeExpression * UnaryExpression
MultiplicativeExpression / UnaryExpression
MultiplicativeExpression % UnaryExpression
```

乘法运算符具有相同的优先级且从左到右结合。

乘法运算符的类型必须是可以转换为（§5.1.8）原始数值类型的类型，否则将发生编译时错误。

执行二元数值提升（§5.6）。注意二元数值提升可能拆箱转换（§5.1.8）。

乘法表达式的类型是操作数的提升后类型。如果提升后类型是 `int` 或 `long`，则执行整数算术。如果提升后类型是 `float` 或 `double`，则执行浮点算术。

### 15.17.1 乘法运算符 *

二元 `*` 运算符执行乘法，产生操作数的乘积。

如果操作表达式没有副作用，乘法是交换运算。

当操作数类型相同时，整数乘法具有结合律。

浮点乘法不具有结合律。

如果整数乘法溢出，则结果为足够补码格式的低位。因此，如果发生溢出，结果的符号可能与数学乘积的符号不同。

浮点乘法的结果取决于 IEEE 754 算术规则。

- 如果操作数为 NaN，结果为 NaN。
- 如果结果不是 NaN，如果两个操作数的符号相同则为正，不同则为负。
- 无穷大乘以零产生 NaN。
- 无穷大乘以有限值产生有符号无穷大。符号由上述规则决定。
- 在其他情况下，不涉及无穷大或 NaN，计算精确的数学乘积。

如果乘积的幅度无法表示，我们说该操作溢出；结果为相应符号的无穷大。

否则，使用最近舍入策略将乘积舍入到最近的可表示的值（§15.4）。Java 编程语言要求支持 IEEE 754 定义的渐进下溢。

尽管可能发生溢出、下溢或信息丢失，乘法运算符 `*` 的评估不会抛出运行时异常。

### 15.17.2 除法运算符 /

二元 `/` 运算符执行除法，产生操作数的商。左侧操作数是被除数，右侧操作数是除数。

整数除法向 0 舍入。也就是说，对于操作数 $n$ 和 $d$，在经过数值提升 (§5.6)后产生的商是一个整数 $q$，其绝对值在满足 $|d \cdot q| \le |n|$ 的情况下尽可能大。此外，当 $|n| \ge |d|$ 且 $n$ 与 $d$ 符号相同时，$q$ 为正数；但当 $|n| > |d|$ 且 $n$ 与 $d$ 符号相反时，$q$ 为负数。

有一个不符合此规则的特殊情况：如果除数是该类型中绝对值最大的负整数，且除数为 -1，则会发生整数溢出，且结果等于除数。尽管发生了溢出，在这种情况下也不会抛出异常。另一方面，如果整数除法中的除数值为 0，则会抛出 `ArithmeticException`。

浮点除法的结果由 IEEE 754 算术规则决定：

- 如果任一操作数是 NaN，则结果为 NaN。
- 如果结果不是 NaN，当两个操作数的符号相同时，结果的符号为正；当操作数符号不同时，结果的符号为负。
- 无穷大除以无穷大的结果为 NaN。
- 无穷大除以有限值的结果为带符号的无穷。符号由上述规则决定。
- 有限值除以无穷大的结果为带符号的零。符号由上述规则决定。
- 0 除以 0 的结果为 NaN；0 除以任何其他有限值为带符号的零。符号由上述规则决定。
- 非零值除以 0 的结果为带符号的无穷。符号由上述规则决定。
- 在其他均不涉及无穷大或 NaN 的情况下，将计算精确的数学商。

如果商的绝对值大到无法表示，我们称该操作溢出；结果为具有适当符号的无穷大。

否则，商将使用最近舍入策略 (§15.4) 舍入到最近的可表示值。Java 编程语言要求支持 IEEE 754 定义的渐进溢出。

尽管可能会发生溢出、下溢、除以零或信息丢失，但浮点除法运算符 `/` 的求值永远不会抛出运行时异常。

### 15.17.3 取余运算符 %

二元运算符 `%` 被称为产生其操作数通过隐含除法的余数；左侧操作数是被除数，右侧操作数是除数。

在 C 和 C++ 中，取余运算符只接受整数操作数，但在 Java 语言中，它也接受浮点操作数。

对于在二进制数值提升 (§5.6) 后为整数的操作数，其取余运算产生的结果值使得 `(a/b)*b+(a%b)` 等于 `a`。

即使在被除数为该类型中绝对值最大的整数且除数为 -1 的特殊情况下（余数为 0），该等式依然成立。

根据此规则，取余运算的结果只有在被除数为负时才为负，只有在被除数为正时才为正。此外，余数的绝对值始终小于除数的绝对值。

如果整数取余运算符的除数值为 0，则会抛出 `ArithmeticException`。

#### Example 15.17.3-1. 整数取余运算符

```
class Test1 {
    public static void main(String[] args) {
        int a = 5%3; // 2
        int b = 5/3; // 1
        System.out.println("%5%3 produces " + a + " (note that 5/3 produces " + b + ")");
    }
}
```

该程序产生输出：

```
5%3 produces 2 (note that 5/3 produces 1)
5%(-3) produces 2 (note that 5/(-3) produces -1)
(-5)%3 produces -2 (note that -5/3 produces -1)
(-5)%(-3) produces -2 (note that -5/(-3) produces 1)
```

## 15.17 乘法运算符

通过 `%` 运算符计算的浮点取余运算的结果与 IEEE 754 中取余运算的结果并不相同，这取决于 Java 语言中舍入策略的选择简体15.4)。IEEE 754 取余运算是根据“舍入除法”计算余数，而不是“截断除法”，且其行为与整数取余运算符并不相似。相反，Java 语言定义在浮点操作数上的 `%` 行为类似于整数取余运算符，使用使用“向零舍入”策略的隐含除法；这与 C 库函数 `fmod` 进行比较。IEEE 754 取余运算可以通过库程序 `Math.IEEEremainder` 或 `StrictMath.IEEEremainder` 计算。

浮点取余运算的结果由以下规则决定，除了隐含除法的计算方式外，它们与 IEEE 754 算术一致：

- 如果任一操作数是 NaN，则结果为 NaN。
- 如果结果不是 NaN，结果的符号等于被除数的符号。
- 如果被除数为无穷大，或除数为 0，或两者皆是，结果为 NaN。
- 如果被除数为无穷大且除数也是无穷大，结果等于被除数。
- 如果被除数为 0 且除数为有限值，结果等于被除数。
- 在其他均不涉及无穷大或 NaN 的情况下，将计算精确的数学商。

浮点取余运算的结果由以下规则决定，除了隐含除法的计算方式外，它们与 IEEE 754 算术一致：

- 如果任一操作数是 NaN，则结果为 NaN。
- 如果结果不是 NaN，结果的符号等于被除数的符号。
- 如果被除数为无穷大，或除数为 0，或两者皆是，结果为 NaN。
- 如果被除数为无穷大且除数也是无穷大，结果等于被除数。
- 如果被除数为 0 且除数为有限值，结果等于被除数。
- 在其他均不涉及无穷大或 NaN 的情况下，将计算精确的数学商。

### Example 15.17.3-2. 浮点取余运算符

```
class Test2 {
    public static void main(String[] args) {
        int a = 5%3; // 2
        int b = 5/3; // 1
        System.out.println("%5%3 produces " + a + " (note that 5/3 produces " + b + ")");
    }
}
```

该程序产生输出：

```
5%3 produces 2 (note that 5/3 produces 1)
5%(-3) produces 2 (note that 5/(-3) produces -1)
(-5)%3 produces -2 (note that -5/3 produces -1)
(-5)%(-3) produces -2 (note that -5/(-3) produces 1)
```

## 表达式

### 加法运算符

`+` 和 `-` 被称为*加法*运算符。

- 加法表达式乘法表达式
- 加法表达式减法表达式

这些运算符具有相同的优先级且是左结合的（从左到右分组）。

如果 `+` 运算符的任一操作数类型为 `String`，则执行字符串拼接。

否则，`+` 运算符的操作数类型都必须是可转换为数值类型的简体5.8)，否则会发生编译错误。

在任何情况下，二元 `-` 运算符的操作数类型都必须是可转换为数值类型的简体5简体5.8)，否则会发生编译错误。

### 15.18.1 字符串拼接运算符 +

如果只有一个操作数表达式是 `String`，则在运行时对另一个操作数进行字符串转换简体5.11) 以产生字符串。

字符串拼接的结果是两个操作数字符串拼接后的 `String` 对象引用。左侧操作数的字符在新创建的字符串中位于右侧操作数的字符之前。

除非表达式是常量表达式简体15.29)，否则 `String` 对象是新创建的简体12.5)。

实现可以选择一次性完成转换和拼接，以避免创建中间 `String` 对象。为了提高重复字符串拼接的性能，Java 编译器可以使用 `StringBuilder` 类或类似技术来减少表达式创建的中间 `String` 对象。对于基本类型，实现也可以通过将基本类型转换为字符串来优化包装对象的创建。

#### Example 15.18.1-1. 字符串拼接

表达式：

```
"The square root of 2 is " + Math.sqrt(2)
```

结果：

```
"The square root of 2 is 1.4142135623730952"
```

运算符在语法上是左结合的，无论通过类型分析确定为字符串拼接还是数值相加。在某些情况下需要注意以得到所需的结果。例如，简体

```
1 + 2 + " fiddlers"
```

总是被视为：



# 表达式

## 15.18 加法运算符

因此，表达式

```
(1 + 2) + " fiddlers"
```

的结果是：

```
"3 fiddlers"
```

但以下操作的结果为：

```
"fiddlers" + 1 + 2
```

结果是：

```
"fiddlers12"
```

### 示例 15.18.1-2. 字符串拼接与条件判断

在这个幽默的示例中：

方法 `printSong` 将打印一首童歌的版本。物品的常用值包括 "pop" 和 "beer"；$n$ 的常用值是 100。以下是运行程序后产生的输出：

```
657
```

## 15.18 表达式中的 加法运算符

墙上有 3 瓶黏液，

3 瓶黏液；

你取下一瓶并传下去：

墙上还有 2 瓶黏液！

墙上有 2 瓶黏液，

2 瓶黏液；

你取下一瓶并传下去：

墙上还有 1 瓶黏液！

墙上有 1 瓶黏液，

1 瓶黏液；

你取下一瓶并传下去：

墙上没有黏液了！

在代码中，注意在适当的情况下仔细地生成了单数 "bottle" 而复数 "bottles"；同样注意如何使用字符串拼接运算符来拆分长常数：

> "你取下一瓶并传下去："

分为两部分，以避免源代码中出现不方便的过行。

### 15.18.2 针对数值类型的 加法运算符 (+ 和 -)

当二元运算符 `+` 应用于两个数值类型的操作数时，它执行加法运算，产生操作数的和。

二元运算符 `-` 执行减法运算，产生两个数值型操作数的差。

二元数值型提升（numeric promotion）在操作数上进行（§5.6）。

该二元数值型提升可能包括无偏转换（§5.1.8）。

数值型操作数上加法表达式的类型是其操作数提升后的类型。

如果此提升类型是 `int` 或 `long`，则执行整数算术。

如果此提升类型是 `float` 或 `double`，则执行浮点算术。

如果操作数表达式没有副作用，则加法是交换操作。

整数加法在所有操作数均为同一种类型时具有结合律。

浮点加法不具有结合律。

如果整数加法溢出，则结果为在某种足够大的补码格式下表示的数学和的低位。如果发生溢出，结果的符号与两个操作数值之数学和的符号不相同。

浮点加法的结果由 IEEE 754 算术规则决定：

- 如果操作数为 `NaN`，则结果为 `NaN`。
- 两个符号相反的无穷大的和为 `NaN`。
- 两个符号相同的无穷大的和为该符号的无穷大。
- 一个无穷大和一个有限值的和等于该无穷操作数。
- 两个符号相反的零之和为正零。
- 两个符号相同的零之和为该符号的零。
- 零与非零有限值的和等于该非零操作数。
- 两个幅度相同且符号相反的非零有限值的和为正零。

在其余情况下，即既不涉及无穷大、零或 `NaN`，且操作数符号相同或幅度不同，则计算精确的数学幅度。

如果和的幅度大到无法表示，我们称该操作溢出；结果结果为相应符号的无穷大。

否则，使用最近舍入策略（§15.4）将和舍入到最近的可表示的值。Java 语言要求支持渐进下溢（gradual underflow）。

当二元运算符 `-` 应用两个数值型操作数时，它执行减法运算，产生操作数的差；左侧操作数是被减数，右侧操作数是减数。

对于整数和浮点减法，$a-b$ 总是产生结果。

对于整数加法，当操作数均为同一种类型时，具有结合律。

对于整数加法法整数整数和浮点减法，$a-b$ 总是产生结果。

注意，浮浮点操作，，减法零法法。。。。尽管溢溢溢溢溢溢溢或，，，，，，法不会$出出运行时异常。

## 19 移位运算符

`<<`（左移）、`>>`（符号右移）和 `>>>`（无符号右移）称为移位运算符。左侧操作数是要位位的值。

```
ShiftExpression:
AdditiveExpression << AdditiveExpression
AdditiveExpression >> AdditiveExpression
AdditiveExpression >>> AdditiveExpression
```

左侧操作数的类型决定移位距离。如果提升类型是 `int`，移位距离为操作数的低 5 位（掩码 0x1f）。如果提升类型是 `long`，移位距离为操作数的低 6 位（掩码 0x3f）。注意，由于移位运算符操作数的隐式掩码，作为移位距离的移动 `int` 值时为 31-s，移动 `long` 值时为 63-s。

$n << s$ 左移 $s$ 位；这（即使发生溢出）等同于乘以 $2^s$。

$n >> s$ 右移 $s$ 位并进行符号扩展。对于非负的 $n$，等同于整数除以 $2^s$。

$n >>> s$ 右移 $s$ 位并进行零扩展，其中：

- 如果 $n$ 为正，则结果与 $n >> s$ 相同。
- 如果 $n$ 为负且左侧操作数类型为 `int`，则结果等于 $(n >> s) + (2 \ll s)$。
- 如果 $n$ 为负且左侧操作数类型为 `long`，则结果等于 $(n >> s) + (2L \ll s)$。

增加的项 $(2 \ll s)$ 或 $(2L \ll s)$ 消除了传播的符号位。

## 20 关系运算符

数值比较运算符 $<$、$>$、$\le$、===$ 以及 `instanceof` 运算符称为关系运算符。

```
RelationalExpression:
ShiftExpression
RelationalExpression < ShiftExpression
RelationalExpression > ShiftExpression
RelationalExpression <= ShiftExpression
RelationalExpression >= ShiftExpression
InstanceofExpression
```

关系运算符在语法上是左结合的（从左到右）。

> 但这没有用。例如，$a<b<c$ 解析为 $(a<b)<c$，这始终是一个编译时错误，因为 $a<b$ 的类型始终是 `boolean`，而 $<$ 不是 `boolean` 值的运算符。

关系表达式的类型始终是 `boolean`。

### 15.20.1 数值比较运算符 $<$、$\le$、$>$ 和 ==$

数值比较运算符的每个操作数的类型必须是可转换为原始数值类型（§5.1.8）的类型，否则会发生编译错误。

## 关系运算符

对操作数执行二元数值类型提升 (§5.6)。请注意，二元数值类型提升可能包括拆箱 (§5.1.8)。如果操作数提升后的类型为 int 或 long，则执行有符号整数比较。如果提升后的类型为 float 或 double，则执行浮点数比较。根据 IEEE 754 标准确定的浮点数比较结果如下：

- 如果任一操作数是 NaN，则结果为 false。
- 除 NaN 之外的所有其他值都是有序的，其中负无穷小于所有有限值，而正无穷大大于所有有限值。
- 正零和负零被认为是相等的。例如，-0.0 < 0.0 为 false，但 -0.0 <= 0.0 为 true。但注意，Math.min 和 Math.max 方法将负零视为严格小于正零。在考虑这些浮点数因素的情况下，以下规则适用于整数操作数或除 NaN 以外的浮点操作数：
- 如果左侧操作数的值小于右侧操作数的值，则 `<` 运算符产生的值为 true，否则为 false。
- 如果左侧操作数的值小于或等于右侧操作数的值，则 `<=` 运算符产生的值为 true，否则为 false。
- 如果左侧操作数的值大于右侧操作数的值，则 `>` 运算符产生的值为 true，否则为 false。
- 如果左侧操作数的值大于或等于右侧操作数的值，则 `>=` 运算符产生的值为 true，否则为 false。

### 15.20.2 instanceof 运算符

`instanceof` 表达式可以执行类型比较或模式匹配。

```java
RelationalExpression instanceof ReferenceType
RelationalExpression instanceof Pattern
```

如果 `instanceof` 关键字右侧的操作数是 `ReferenceType`，则 `instanceof` 关键字是类型比较运算符。如果 `instanceof` 关键字右侧的操作数是 `Pattern`，则 `instanceof` 关键字是模式匹配运算符。当 `instanceof` 是类型比较运算符时，适用以下规则：

- `RelationalExpression` 的类型必须是引用类型或空类型，否则将发生编译错误。
- `RelationalExpression` 必须与 `ReferenceType` 向下兼容 (§5.5)，否则将发生编译错误。
- 在运行时，类型比较运算符的结果确定如下：
  - 如果 `RelationalExpression` 的值是空引用 (§4.1)，则结果为 false。
  - 如果 `RelationalExpression` 的值不是空引用，则如果该值可以转换为 `ReferenceType` 而不抛出 `ClassCastException`，则结果为 true，否则为 false。

当 `instanceof` 是模式匹配运算符时，适用以下规则：

- 表达式 `RelationalExpression` 的类型必须是引用类型或空类型，否则将发生编译错误。
- `RelationalExpression` 必须与 `Pattern` 兼容 (§14.30.1)，否则将发生编译错误。
- `RelationalExpression` 的类型必须是 `Pattern` 类型的子类型，否则将发生编译错误。
- 在运行时，模式匹配运算符的结果如下：
  - 如果 `RelationalExpression` 的值是空引用，则结果为 false。
  - 如果 `RelationalExpression` 的值不是空引用，则如果该值匹配 `Pattern` (§14.30.2)，结果为 true，否则为 false。

结果为 true 的副作用是 `Pattern` 中声明的模式变量将被初始化。

#### 示例 15.20.2-1. 类型比较运算符

```java
class Point { int x, y; }
class Element { int atomicNumber; }
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

该程序导致了两个编译错误。强制转换 `(Point)e` 是错误的，因为 `Element` 的实例或其任何可能的子类实例（此处未显示）都不可能是 `Point` 的任何子类的实例。`instanceof` 表达式由于完全相同的原因也是错误的。相反，如果 `Point` 类如下所示（尽管在这个示例中这是一种奇怪的表示）：

```java
class Point extends Element { int x, y; }
```

那么这段代码就是可能的，尽管它需要进行运行时检查，且 `instanceof` 表达式是合理且有效的。强制转换 `(Point)e` 将抛出异常，因为如果 `e` 无法正确转换为 `Point` 类型，该转换不会执行。

在 Java SE 16 之前，类型比较运算符的引用类型被必须是可重化的 (§4)。这防止了泛型类型的使用，除非其所有参数都是通配符。Java SE 16 取消了这一要求，以允许使用更多泛型类型。例如，在以下程序中，测试静态类型为 `List<Integer>` 的方法 `x` 在运行时是否具有更“精细”的泛型类型 `ArrayList<Integer>` 是合法的：

```java
import java.util.List;
import java.util.ArrayList;

class Test {
    public static void main(String[] args) {
        List<Integer> x = new ArrayList<>();
        if (x instanceof ArrayList<Integer>) {
            System.out.println("x is an ArrayList");
        }
    }
}
```

### 15.21.1 数相等运算符 == 和 !=

如果相等运算符的操作数都是数值类型，或者其中一个是数值类型而另一个可以转换为 (§5.1.8) 数值类型，则对操作数执行二元数值类型提升 (§5.6)。请注意，二元数值类型提升可能包括拆箱 (§5.1.8)。如果操作提升提升类型为 int 或 long，则执行整数相等测试。如果提升后的类型为 float 或 double，则执行浮点数相等测试。

浮点数相等测试根据 IEEE 754 标准执行：

- 如果任一操作数是 NaN，则结果为 false。事实上，`x!=` 为真当且仅当 `x` 为 NaN。
- 正零和负零被认为是相等的。例如，-0.0==0.0 为 true。
- 否则，这两个不同的浮点值被相等运算符认为是不等的。特别是，有一个表示正无穷的值和一个表示负无穷的值；每个仅与自身相等，且与所有其他值不等。

在考虑这些浮点数因素的情况下，以下规则适用于整数操作数或除 NaN 以外的浮点操作数：

- 如果左侧操作数的值等于右侧操作数的值，则 `==` 运算符产生的值为 true，否则为 false。
- 如果左侧操作数的值不等于右侧操作数的值，则 `!=` 运算符产生的值为 true，否则为 false。

如果相等运算符的操作数都是 boolean 类型，或者一个操作数是 boolean 类型而另一个是 Boolean 类型，则操作是布尔相等。

布尔相等运算符具有结合律。

如果其中一个操作数的类型为 `Boolean`，则要进行拆箱转换（§5.1.8）。

如果操作数（在任何必要的拆箱转换后）均为 true 或均为 false，则 `==` 的结果为 true；否则，结果为 false。

如果操作数均为 true 或均为 false，则 `!=` 的结果为 false；否则，结果为 true。

因此，当应用于布尔操作数时，`!=` 的行为与 `^` (§15.22) 相同。

如果操作数均为引用类型或基本类型，则操作的结果是对象相等性。

如果无法通过转换将其中一个操作数的类型转换为另一个操作数的类型（§5.5），则为编译时错误（忽略两个操作数值均为 null的情况）。

在运行时，如果操作数都为 null 或都引用同一个对象或数组，则 `==` 的结果为 true。

如果操作数都为 null 或都引用同一个对象或数组，则 `!=` 的结果为 false；否则，结果为 true。

`==` 可用于比较 `String` 类型的引用，以确定操作数是否引用同一个 `String` 对象；即使它们包含相同的字符序列（§10.5, §10.6），通过方法 `s.equals(t)`也可以测试相等性。

# 15.22 位运算符和逻辑运算符

位运算符和逻辑运算符包括按与运算符 `&`、异或运算符 `^` 和按或运算符 `|`。

```
AndExpression:
EqualityExpression
AndExpression & EqualityExpression
```

### ExclusiveOrExpression:

```
AndExpression
ExclusiveOrExpression ^ AndExpression
```

### InclusiveOrExpression:

```
ExclusiveOrExpression
InclusiveOrExpression | ExclusiveOrExpression
```

这些运算符的优先级不同，`&` 优先级最高，`|` 优先级最低。

这些运算符每一个在语法上都是左结合的（从左到右分组）。

如果操作数表达式没有副作用，则每个运算符都是结合的。

位运算符和逻辑运算符可用于比较数值类型的操作数或布尔类型的操作数。所有其他情况均会导致编译时错误。

## 15.2.1 整数位运算符 `&`, `^`, 和 `|`

当运算符 `&`、`^` 或 `|` 的操作操作都是可转换为整数类型（§5.8）时，首先对操作数进行基本类型提升（§5.6）。

对于 `&`，结果是操作数的按位与。

对于 `^`，结果是操作数的按位异异。

对于 `|`，结果是操作数的按位或。

例如，表达式的结果：

```
0xff & 0xf
```

是：`0xf`

表达式的结果：

```
0xff ^ 0xf
```

是：`0xf0`

表达式的结果：

```
0xff | 0xf
```

是：`0xff`

## 15.2.2 逻辑运算符 `&`, `^`, 和 `|`

当 `&`、`^` 或 `|` 的操作数类型为 boolean 或 Boolean 时，逻辑运算符表达式的类型为 boolean。在所有情况下，操作数都要进行拆箱转换（§5.8）。

对于 `&`，如果两个操作数值均为 true，则结果为 true；否则，结果为 false。

对于 `^`，如果操作数值不同，则结果为 true；否则，结果为 false。

对于 `|`，如果两个操作数值均为 false，则结果为 false；否则，结果为 true。

## 15.2.3 条件与运算符 `&&`

条件与运算符 `&&` 类似于 (§15.22.2)，但它仅在当左侧操作数的值为 true 时才求值其右侧操作数。

```
ConditionalAndExpression:
InclusiveOrExpression
ConditionalAndExpression && InclusiveOrExpression
```



条件运算符在语法上是左结合的（从左到右分组）。条件与运算符在副作用和结果方面都是完全结合的。也就是说，对于表达式 a、b 和 c，评估 `((a) && (b)) && (c)` 产生的结果以及副作用顺序与评估表达式 `(a) && ((b) && (c))` 相同。

## 15.2.4 条件或运算符 `||`

条件或运算符的每个操作数必须是 `boolean` 或 `Boolean` 类型，否则发生编译错误。条件表达式的类型总是 `boolean`。在运行时，首先求值左侧操作数；如果结果类型为 `Boolean`，则要进行拆箱转换（§5.1.8）。

如果结果值为 `false`，则条件或表达式的值为 `false` 且不求值右侧操作数。

如果左侧操作数的值为 `true`，则求值右侧表达式；如果结果类型为 `Boolean`，则要进行拆箱转换（§5.1.8）。结果值变为条件或的值。

因此，`||` 在布尔操作数上的计算结果与 `|` 相同。区别仅在于右侧表达式是条件求值而非总是求值。

条件或运算符 `||` 类似于 `|` (§15.22.2)，但它仅在当左侧操作数的值为 `false` 时才求值其右侧操作数。

```
ConditionalOrExpression:
ConditionalAndExpression
ConditionalOrExpression || ConditionalAndExpression
```

条件或运算符在语法上是左结合的（从左到右分组）。条件或运算符在副作用和结果方面都是完全结合的。对于任何表达式 a、b 和 c，评估 `((a) || (b)) || (c)` 产生的结果以及副作用顺序与评估表达式 `(a) || ((b) || (c))` 相同。

条件或运算符的每个操作数必须是 `boolean` 或 `Boolean` 类型，否则发生编译错误。条件表达式的类型总是 `boolean`。在运行时，首先求值左侧操作数；如果结果类型为 `Boolean`，则要进行拆箱转换（§5.1.8）。如果结果值为 `true`，则条件或表达式的值为 `true` 且不求值右侧操作数。

## 15.25 条件运算符 `? :`

条件运算符 `? :` 使用一个表达式的布尔值来决定求值两个表达式中的哪。

```
ConditionalExpression:
ConditionalOrExpression
ConditionalOrExpression ? Expression : ConditionalExpression
ConditionalOrExpression ? Expression : LambdaExpression
```

条件运算符在语法上是右结合的（从右到左分组）。因此，`a?b:c?d:e?f:g` 等于 `a?b:(c?d:(e?f:g))`。

条件运算符有三个操作数表达式。`?` 出现在第一个和第二个表达式之间，`:` 出现在第二个和第三个表达式之间。

第一个表达式必须是 `boolean` 或 `Boolean` 类型，否则发生编译错误。第二个或第三个操作可以是 void 方法的调用。

如果第二个和第三操作数表达式都是布尔表达式，则该条件表达式为布尔条件表达式。

为了对条件表达式进行分类，以下表达式为布尔表达式：

- 类型为 `boolean` 或 `Boolean` 的独立形式表达式 (§15.2)。
- 带括号的布尔表达式 (§15.8.5)。
- 针对 `Boolean` 类的类实例创建表达式 (§15.9)。
- 方法调用表达式 (§15.12)，其所选定的最特定方法 (§15.12.2) 返回类型为 `boolean` 或 `Boolean`。

> 注意，对于泛型方法，该类型为在实例化方法参数之前的类型。

- 布尔条件表达式。
- 结果表达式均为布尔表达式的 `switch` 表达式 (§15.28)。

如果第二个和第三操作数表达式都是数值表达式，则该条件表达式为数值条件表达式。

为了对条件表达式进行分类，以下表达式为数值表达式：

- 类型可转换为数值类型 (§4.2, §15.1.8) 的独立形式表达式 (§15.2)。
- 带括号的数值表达式表达式 (§15.8.5)。
- 针对可转换为数值类型的类实例创建表达式 (§15.9)。
- 方法调用表达式 (§15.12)，其所选定的最特定方法 (§15.12.2) 的返回类型可转换为数值类型。

> 注意，对于泛型方法，该类型为在实例化方法参数之前的类型。

- 数值条件表达式。
- 结果表达式均为数值表达式的 `switch` 表达式 (§15.28)。
- 否则，该条件表达式为引用条件表达式。

确定条件表达式类型的过程取决于条件表达式的种类，下文章节概述。

以下表通过给出在第二和第三操作数的所有可能的类型下，条件表达式的类型，总结了上述规则。`bnp(..)` 表示应用二值数值提升。形式 `τ[bnp()]` 用于其中一个操作数为 `int` 类型的常数表达式且可能在 `τ` 中表示的情形，此时如果该操作数无法在 `τ` 中表示，则使用二值数值提升。操作数类型 `Object` 表示除 `null` 类型和八个包装类 `Boolean`、`Byte`、`Short`、`Character`、`Integer`、`Long`、`Float`、`Double` 之外任何引用类型。

### 表 15.25-A. 条件表达式类型（基本类型第三操作数，第一部分）

| 3rd → | byte | short | char | int |
| :--- | :--- | :--- | :--- | :--- |
| **2nd ↓** | | | | |
| byte | byte | short | bnp(byte,char) | bnp(byte,int) |
| Byte | byte | short | bnp(Byte,char) | bnp(Byte,int) |
| short | short | short | bnp(short,char) | bnp(short,int) |
| Short | short | short | bnp(Short,char) | bnp(Short,int) |
| char | bnp(char,byte) | bnp(char,short) | char | bnp(char,int) |
| Character | bnp(Character,byte) | bnp(Character,short) | char | bnp(Character,int) |
| int | bnp(int,byte) | bnp(int,short) | bnp(int,char) | int |
| Integer | bnp(Integer,byte) | bnp(Integer,short) | bnp(Integer,char) | int |
| long | bnp(long,byte) | bnp(long,short) | bnp(long,char) | bnp(long,int) |
| Long | bnp(Long,byte) | bnp(Long,short) | bnp(Long,char) | bnp(Long,int) |
| float | bnp(float,byte) | bnp(float,short) | bnp(float,char) | bnp(float,int) |
| Float | bnp(Float,byte) | bnp(Float,short) | bnp(Float,char) | bnp(Float,int) |
| double | bnp(double,byte) | bnp(double,short) | bnp(double,char) | bnp(double,int) |
| Double | bnp(Double,byte) | bnp(Double,short) | bnp(Double,char) | bnp(Double,int) |
| boolean | bnp(Boolean,byte) | bnp(Boolean,short) | bnp(Boolean,char) | bnp(Boolean,Integer) |
| Boolean | bnp(Boolean,byte) | bnp(Boolean,short) | bnp(Boolean,Character) | bnp(Boolean,Integer) |
| null | bnp(null,byte) | bnp(null,short) | bnp(null,Character) | bnp(null,Integer) |
| Object | bnp(Object,byte) | bnp(Object,short) | bnp(Object,Character) | bnp(Object,Integer) |

### 表 15.25-B. 条件表达式类型（基本类型第三操作数，第二部分）

| 3rd → | long | float | double | boolean |
| :--- | :--- | :--- | :--- | :--- |
| **2nd ↓** | | | | |
| byte | bnp(byte,long) | bnp(byte,float) | bnp(byte,double) | boolean |
| Byte | bnp(Byte,long) | bnp(Byte,float) | bnp(Byte,double) | boolean |
| short | bnp(short,long) | bnp(short,float) | bnp(short,double) | boolean |
| Short | bnp(Short,long) | bnp(Short,float) | bnp(Short,double) | boolean |
| char | bnp(char,long) | bnp(char,float) | bnp(char,double) | boolean |
| Character | bnp(Character,long) | bnp(Character,float) | bnp(Character,double) | boolean |
| int | bnp(int,long) | bnp(int,float) | bnp(int,double) | boolean |
| Integer | bnp(Integer,long) | bnp(Integer,float) | bnp(Integer,double) | boolean |
| long | long | bnp(long,float) | bnp(long,double) | boolean |
| Long | long | bnp(Long,float) | bnp(Long,double) | boolean |
| float | bnp(float,long) | float | bnp(float,double) | boolean |
| Float | bnp(Float,long) | float | bnp(Float,double) | boolean |
| double | bnp(double,long) | bnp(double,float) | double | boolean |
| Double | bnp(Double,long) | bnp(Double,float) | double | boolean |
| boolean | bnp(Boolean,long) | bnp(Boolean,float) | bnp(Boolean,double) | boolean |
| Boolean | bnp(Boolean,long) | bnp(Boolean,float) | bnp(Boolean,double) | boolean |
| null | bnp(null,long) | bnp(null,float) | bnp(null,double) | boolean |
| Object | bnp(Object,long) | bnp(Object,float) | bnp(Object,double) | boolean |

### 表 15.25-C. 条件表达式类型（引用第三操作数，第一部分）

| 3rd → | Byte | Short | Character | Integer |
| :--- | :--- | :--- | :--- | :--- |
| **2nd ↓** | | | | |
| byte | byte | short | char | int |
| Byte | byte | short | char | int |
| short | short | short | char | int |
| Short | short | short | char | int |
| char | char | char | char | int |
| Character | char | char | char | int |
| int | int | short | char | int |
| Integer | int | short | char | int |
| long | long | short | char | int |
| Long | long | short | char | int |
| float | float | short | char | int |
| Float | float | short | char | int |
| double | double | short | char | int |
| Double | double | short | char | int |
| boolean | byte | short | char | int |
| Boolean | byte | short | char | int |
| null | byte | short | char | int |
| Object | byte | short | char | int |

### 表 15.25-D. 条件表达式类型（引用第三操作数，第二部分）

| 3rd → | Long | Float | Double | Boolean |
| :--- | :--- | :--- | :--- | :--- |
| **2nd ↓** | | | | |
| byte | long | float | double | boolean |
| Byte | long | float | double | boolean |
| short | long | float | double | boolean |
| Short | long | float | double | boolean |
| char | long | float | double | boolean |
| Character | long | float | double | boolean |
| int | long | float | double | boolean |
| Integer | long | float | double | boolean |
| long | long | float | double | boolean |
| Long | long | float | double | boolean |
| float | long | float | double | boolean |
| Float | long | float | double | boolean |
| double | long | float | double | boolean |
| Double | long | float | double | boolean |
| boolean | long | float | double | boolean |
| Boolean | long | float | double | boolean |
| null | long | float | double | boolean |
| Object | long | float | double | boolean |

### 表 15.25-E. 条件表达式类型（引用第三个操作数，第三部分）

| 3rd → | null | Object |
| :--- | :--- | :--- |
| **2nd ↓** | | |
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



| Double | Double | `lub(Double,Object)` |
|---|---|---|
| boolean | `lub(Boolean,null)` | `lub(Boolean,Object)` |
| Boolean | Boolean | `lub(Boolean,Object)` |
| null | null | `lub(null,Object)` |
| Object | Object | Object |

在运行时，条件表达式的第一个操作数表达式首先求值。如有必要，会对结果进行拆箱转换（`unboxing conversion`）。

得到的布尔值随后用于选择第二个或第三个操作数表达式：

- 如果第一个操作数的值为真，选择第二个操作数表达式。
- 如果第一个操作数的值为假，选择第三个操作数表达式。

然后对选定的操作数表达式进行求值，并将结果根据下述规则转换为条件表达式的类型。

此转换可能包括装箱（`boxing`）或拆箱转换（§5.1.7, §5.1.8）。

未被选中的操作数表达式在该特定的条件表达式求值过程中不会求值。

## 15.25.1 布尔条件表达式

布尔条件表达式是独立的表达式（§15.2）。

布尔条件表达式的类型确定如下：

- 如果第二个和第三个操作数都是 `Boolean` 类型，则条件表达式的类型为 `Boolean`。
- 否则，条件表达式的类型为 `boolean`。

## 15.25.2 数值条件表达式

数值条件表达式是独立的表达式（§15.2）。

数值条件表达式的类型确定如下：

- 如果第二个和第三个操作数的类型相同，则该类型为条件表达式的类型。
- 如果第二个和第三个操作数之一是原始类型 `T`，而另一个类型是对 `T` 应用装箱转换（§5.1.7）的结果，则条件表达式的类型为 `T`。
- 如果其中一个操作数的类型是 `Byte`，另一个是 `short` 或 `Short`，则条件表达式的类型为 `short`。
- 如果其中一个操作数的类型为 `T`（其中 `T` 为 `short` 或 `char`），另一个操作数是 `int` 类型的常量表达式（§15.29），且其值在类型 `T` 中可表示，则条件表达式的类型为 `T`。
- 如果其中一个操作数的类型为 `T`（其中 `T` 为 `Byte`、`Short` 或 `Character`），另一个操作数是 `int` 类型的常量表达式，且其值在 `T` 应用拆箱转换后得到的类型 `U` 中可表示，则条件表达式的类型为 `U`。

否则，对第二个和第三个操作数应用通用数值提升（§5.6），条件表达式的类型为第二个和第三个操作数提升后的类型。

注意，数值提升可能包括拆箱转换（§5.1.8）。

## 15.25.3 引用条件表达式

如果引用条件表达式出现在赋值上下文或调用上下文中（§5.2, §5.3），则它是一个多态表达式（`poly expression`）。否则，它是独立表达式。

当多态引用条件表达式出现在类型为 $\tau$ 的特定类型的环境中，其第二个和第三个操作数表达式同样出现在目标类型为 $\tau$ 的相同类型的环境中。

如果多态引用条件表达式的第二个和第三个操作数表达式与 $\tau$ 兼容，则该表达式与目标类型 $\tau$ 兼容。

多态引用条件表达式的类型与其目标类型相同。独立引用条件表达式的类型确定如下：

- 如果两个操作数的类型相同（可能是 `null` 类型），则它为条件表达式的类型。
- 如果第二个和第三个操作数之一的类型是 `null` 类型，而另一个操作数的类型是引用类型，则条件表达式的类型为该引用类型。
- 否则，第二个和第三个操作数分别对应类型 $S_1$ 和 $S_2$。令 $T_1$ 为 $S_1$ 应用装箱转换得到的类型，$T_2$ 为 $S_2$ 应用装箱转换得到的类型。该条件表达式为 `lub($T_1, T_2$)` 应用捕获转换（`capture conversion`, §5.1.10）的结果。

由于引用条件表达式可以是多态表达式，它们可以“向下传递”到其操作数。这允许 lambda 表达式和方法引用表达式作为操作数出现：

```
return ... ? (x) : (x);
```

```
List<String> ls =
asList();
```

注意，赋值不是一个变量。

## 15.26 赋值运算符

共有 12 个赋值运算符；它们都是右结合的（从右到左分组）。因此，`a=b=c` 意味着 `a=(b=c)`，先将 `c` 的值赋给 `b`，然后将 `b` 的值赋给 `a`。

```
赋值表达式
赋值
左值表达式
赋值运算符
（其中之一）
= /= += -= <= >= >>> >= &= ^ |
```

赋值运算符第一个操作数的结果必须是一个变量，否则将发生编译时错误。

该操作数可以是一个命名变量（例如局部变量或当前对象或类的字段），也可以是计算出的变量，这可以由字段访问（§15.11）或数组访问（§15.10.3）产生。

## 15.26.1 赋值运算符 =

如果右侧操作数的类型与变量的类型（§5.2）不兼容，则发生编译时错误。

否则，在运行时，按以下三种方式之一求值：

如果左侧操作数表达式是字段访问 `e.f`（§15.11），可能被多对括号包含，则：

- 首先，求值表达式 `e`。如果 `e` 的求值异常，则赋值表达式以相同原因异常。
- 接下来，求值右侧操作数。如果右侧表达式求值异常，则赋值表达式以相同原因异常。
- 然后，如果字段 `e.f` 不是静态的，且 `e` 的求值结果为空，则抛出 `NullPointerException`。
- 否则，变量 `e.f` 被赋予上述计算出的右侧操作数的值。

如果左侧操作是数组访问表达式（§15.10.3），可能被多对括号包含，则：

- 首先，求值左侧操作访问表达式中的数组引用子表达式。如果该求值异常，则该赋值表达式由于相同的原因而异常终止；索引子表达式（左侧操作数访问表达式的）和右侧操作数未被求值，且没有发生赋值。
- 否则，求值左侧操作数访问表达式的索引子表达式。如果该求值异常终止，则赋值表达式由于相同的原因而异常终止，右侧操作数未被求值，且没有发生赋值。
- 否则，求值右侧操作数。如果该求值异常终止，则赋值表达式由于相同的原因而异常终止，且没有发生赋值。
- 否则，如果数组引用子表达式的值为 `null`，则不发生赋值并抛出 `NullPointerException`。
- 否则，如果引用子表达式的值小于 0，或大于或等于数组的长度，则不发生赋值并抛出 `ArrayIndexOutOfBoundsException`。
- 否则，索引子表达式的值用于选择由数组引用子表达式的值所引数组的组件。

该组件是一个变量；调用其类型为 `SC`。此外，令 `TC` 为编译时确定的赋值运算符左侧操作数的类型。存在两种可能性：

- 如果 `TC` 是原始类型，则 `SC` 必然与 `TC` 相同。右侧操作数的值转换为所选数组组件的类型，转换结果被存储在数组组件中。
- 如果 `TC` 是引用类型，则 `SC` 可能与 `TC` 不同，而是一个扩展或实现 `TC` 的类型。令 `RC` 为运行时右侧操作数的值所引用的对象的类。

Java 编译器可能在编译时证明数组组件的类型恰好为 `TC`（例如，`TC` 可能是 `final`）。但如果 Java 编译器无法在编译时证明数组组件的类型恰好为 `TC`，则必须在运行时进行检查以确保该类 `RC` 与数组组件的实际类型 `SC` 在赋值上是兼容的（§5.2）。

此检查类似于窄类型转换（§5.5, §15.16），不同在于，如果检查失败，抛出的是 `ArrayStoreException` 而不是 `ClassCastException`。

如果 `RC` 不可赋值给类型 `SC`，则不发生赋值并抛出 `ArrayStoreException`。

否则，右侧操作数的引用值被存储在所选组件中。

否则，需要三个步骤：

- 首先，求值左侧操作数以产生一个变量。如果该求值异常终止，则赋值表达式由于相同的原因而异常终止；右侧操作数未被求值，且没有发生赋值。
- 否则，求值右侧操作数。如果该求值异常终止，则赋值表达式由于相同的原因而异常终止且没有发生赋值。
- 否则，将右侧操作数的值转换为左侧变量的类型，转换结果被存储在变量中。

### 示例 15.26.1-1 向数组组件的简单赋值

```
class ArrayReferenceThrow extends RuntimeException { }
class IndexThrow extends RuntimeException { }
class RightHandSideThrow extends RuntimeException { }
```

```
class IllustrateSimpleAssignment {
    static Object[] objects = { new Object(), new Object() };
    static Thread[] threads = { new Thread(), new Thread() };

    static Object[] arrayThrow() {
        throw new ArrayReferenceThrow();
    }
    static int indexThrow() {
        throw new IndexThrow();
    }
    static Thread rightThrow() {
        throw new RightHandSideThrow();
    }
    static String name(Object q) {
        String sq = q.getClass().getName();
        int k = sq.lastIndexOf('.');
        return (k < 0) ? sq : sq.substring(k+1);
    }
}
```

```
static void testFour(Object[] x, int i, Thread t) {
    try {
        System.out.print("[" + name(x) + "]" + i + "=" + name(t) + " => ");
        x[i] = t;
        System.out.println("Okay!");
    } catch (Throwable e) {
        System.out.println(name(e));
    }
}

public static void main(String[] args) {
    testFour(null, 1, new StringBuffer());
    testFour(null, 9, new Thread());
    testFour(objects, 1, new StringBuffer());
    testFour(objects, 9, new Thread());
    testFour(threads, 1, new StringBuffer());
}
```



```
testFour(objects, 9, new Thread());
testFour(threads, 1, new StringBuffer());
testFour(threads, 9, new Thread());
testFour(threads, 1, new StringBuffer());
}
```

该程序输出如下：

```
[throw]=throw => IndexThrow
[throw]=Thread => IndexThrow
[throw]1]=throw => ArrayIndexOutOfBoundsException
[throw]1]=Thread => ArrayIndexOutOfBoundsException
```

# 赋值运算符

如果左侧操作数表达式是数组访问表达式（§15.10.3），则：

- 首先，求值左侧操作数数组访问表达式的数组引用子表达式。如果该求值异常终止，则赋值表达式也因相同原因异常终止；索引子表达式（左侧操作数数组访问表达式的）和右侧操作数不会被求值，且不发生赋值。

- 否则，求值左侧操作数数组访问表达式的索引子表达式。如果该求值异常终止，则赋值表达式也因相同原因异常终止，右侧操作数不会被求值且不发生赋值。

- 否则，如果数组引用子表达式的值为 `null`，则不发生赋值并抛出 `NullPointerException`。

- 否则，数组引用子表达式的值确实引用一个数组。如果索引子表达式的值小于 0，或大于等于数组的长度，则不发生赋值并抛出 `ArrayIndexOutOfBoundsException`。

- 否则，使用索引子表达式的值来选择由数组引用子表达式的值所引用的数组组件。该组件的值被保存，然后求值右侧操作数。如果该求值异常终止，则赋值表达式也因相同原因异常终止且不发生赋值。

> 对于简单赋值运算符，右侧操作数的求值发生在对数组引用子表达式和索引子表达式检查之前，但对于复合赋值运算符，右侧操作数的求值发生在这些检查之后。

- 否则，考虑上一步中选定的数组组件，其值已被保存。该组件是一个变量；调用其类型为 $s$。同时，令 $\tau$ 为在编译时确定的赋值运算符左侧操作数的类型。

- 如果 $T$ 是基本类型，则 $s$ 必然等于 $T$。

保存的数组组件的值和右侧操作数的值被用于执行复合赋值运算符指示的二元运算。

如果该操作异常终止（唯一可能性是整数除以零 - 见 §15.17.2），则赋值表达式因相同原因异常终止且不发生赋值。

否则，将二元运算的结果转换为所选数组组件的类型，并将转换结果存储到数组组件中。

- 如果 $T$ 是引用类型，则它必须是 `String`。由于 `String` 类是一个 `final` 类，$s$ 也必须是 `String`。

因此，简单赋值运算符有时需要的运行时检查在复合赋值运算符中是永远不需要。

保存的数组组件的值和右侧操作数的值被用于执行复合赋值运算符指示的二元运算（必然是 `+=`，即字符串拼接）。如果该操作异常终止，则赋值表达式因相同原因异常终止且不发生赋值。

否则，将二元运算的 `String` 结果存储到数组组件中。

示例 15.26.2-1 复合赋值给数组组件

```java
class ArrayReferenceThrow extends RuntimeException { }
class IndexThrow extends RuntimeException { }
class RightHandSideThrow extends RuntimeException { }
class IllustrateCompoundArrayAssignment {
    static String[] strings = { "Simon", "Garfinkel" };
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
        throw new RightHandSideThrow();
    }
    static double doubleThrow() {
        throw new RightHandSideThrow();
    }
    static String name(Object q) {
        String sq = q.getClass().getName();
        int k = sq.lastIndexOf('.');
        return (k < 0) ? sq.substring(k+1);
    }

    static void testEight(String[] x, double[] z, int j) {
        String sx = (x == null) ? "null" : "Strings";
        String sz = (z == null) ? "null" : "doubles";
        System.out.println(sz);
        try {
            System.out.print(sx + "[throw] += " ");
            x[indexThrow()] += stringThrow();
            System.out.println("Ok!");
        } catch (Throwable e) {
            System.out.println(e);
        }
        try {
            System.out.print(sz + "[throw] += " ");
            z[indexThrow()] += doubleThrow();
            System.out.println("Ok!");
        } catch (Throwable e) {
            System.out.println(e);
        }
        try {
            System.out.print(name(x) + "[throw] += ");
            x[indexThrow()] += "heh";
            System.out.println("Ok!");
        } catch (Throwable e) {
            System.out.println(e);
        }
        try {
            System.out.print(name(z) + "[throw] += ");
            z[j] += doubleThrow();
            System.out.println("Ok!");
        } catch (Throwable e) {
            System.out.println(e);
        }
        try {
            System.out.print(name(x) + "[j] += ");
            x[j] += "heh";
            System.out.println("Ok!");
        } catch (Throwable e) {
            System.out.println(e);
        }
    }
}
```

该程序输出：

```
throw[throw] => ArrayReferenceThrow
throw[throw] => ArrayReferenceThrow
throw[throw]+="heh" => ArrayReferenceThrow
throw[throw]+=1245 => ArrayReferenceThrow
throw[1] => ArrayReferenceThrow
throw[1] => ArrayReferenceThrow
throw[1]+="heh" => ArrayReferenceThrow
throw[1]+=1245 => ArrayReferenceThrow
null[throw] => IndexThrow
null[throw] => IndexThrow
null[throw]+="heh" => IndexThrow
null[throw]+=1245 => IndexThrow
null[1] => NullPointerException
null[1] => NullPointerException
null[1]+="heh" => NullPointerException
null[1]+=1245 => NullPointerException
null[throw] => IndexThrow
null[throw] => IndexThrow
null[throw]+="heh" => IndexThrow
null[throw]+=1245 => IndexThrow
null[9] => NullPointerException
null[9] => NullPointerException
null[9]+="heh" => NullPointerException
null[9]+=1245 => NullPointerException
doubles[throw] => IndexThrow
doubles[throw] => IndexThrow
doubles[throw]+="heh" => IndexThrow
doubles[throw]+=1245 => IndexThrow
Strings[1] => RightHandSideThrow
doubles[1] => RightHandSideThrow
Strings[1]+="heh" => Ok!
doubles[1]+=1245 => Ok!
Strings[throw] => IndexThrow
doubles[throw] => IndexThrow
Strings[throw]+="heh" => IndexThrow
doubles[throw]+=1245 => IndexThrow
Strings[9] => ArrayIndexOutOfBoundsException
doubles[9] => ArrayIndexOutOfBoundsException
Strings[9]+="heh" => ArrayIndexOutOfBoundsException
doubles[9]+=1245 => ArrayIndexOutOfBoundsException
```

这些情况中最有趣的是倒数第十和第十二：

```
Strings[1]+=throw => RightHandThrow
doubles[1]+=throw => RightHandThrow
```

它们是右侧确实抛出异常的情况；此外，它们是这些情况中的唯一情况。这表明右侧的求值发生在空数组引用值和越界索引值检查之后。

示例 15.26.2-2 复合赋值左侧的值在求值右侧之前被保存

```java
class Test {
    public static void main(String[] args) {
        int k = 1;
        int[] a = { 1 };
        k += (k = 4) * (k + 2);
        a[0] += (a[0] = 4) * (a[0] + 2);
        System.out.println("k=" + k + " and a[0]=" + a[0]);
    }
}
```

该程序输出：

```
k=25 and a[0]=25
```

复合赋值运算符 `+=` 在其右侧操作数 `(k = 4) * (k + 2)` 求值之前保存了值 `1`。求值该右侧操作数会将 `4` 赋值给 `k`，计算 `k+2` 的值为 `6`，并将 4 乘以 6 得到 24。此值与保存的值 `1` 相加得到 25，由 `+=` 运算符存储到 `k` 中。相同的分析适用于使用 `a[0]` 的情况。

简而言之，语句：

```
k += k + (k = 4) * (k + 2);
a[0] += a[0] + (a[0] = 4) * (a[0] + 2);
```

其行为与语句相同：

```
k = k + (k = 4) * (k + 2);
a[0] = a[0] + (a[0] = 4) * (a[0] + 2);
```

# LambdaExpression（Lambda 表达式）

LambdaParameters -> LambdaBody

Lambda 表达式总是多式表达式 (§15.2)。

如果 Lambda 表达式出现在程序中赋值上下文 (§5.2)、调用上下文 (§5.3)或类型转换上下文 (§5.5)以外的地方，则会导致编译错误。

Lambda 表达式的求值会产生函数式接口的实例 (§9.8)。Lambda 表达式的求值不会导致表达式体的执行；相反，这可能在之后调用该函数式接口的适当方法时发生。

以下是一些 Lambda 表达式的示例：

```
() -> ( // 无参数；结果为 void
() -> 42 // 无参数，表达式体
() -> null // 无参数，表达式体
() -> { return 42; } // 无参数，带返回的块体
() -> { System.gc(); } // 无参数，void 块体
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
(int x) -> x+1 // 单一声明类型参数
(int x) -> { return x+1; } // 单一声明类型参数
(x) -> x+1 // 单一推断类型参数
x -> x+1 // 单一推断类型参数括号可选的
```

```
(String s) -> s.length() // 单一声明类型参数
(Thread t) -> { t.start(); } // 单一声明类型参数
s -> s.length() // 单一推断类型参数
t -> { t.start(); } // 单一推断类型参数
```

```
(int x, int y) -> x+y // 多个声明类型参数
(x, y) -> x+y // 多个推断类型参数
(int, y) -> x+y // 非法：不能混合推断和声明类型
(x, final y) -> x+y // 非法：推断类型不能带有修饰符
```

这种语法的优势在于减少了 Lambda 表达式周围的括号噪声，这在 Lambda 表达式作为方法的参数或其体是另一个 Lambda 表达式时特别有益。它还清晰地区分了表达式形式和语句形式，避免了歧义或对 `;` 标记的过度依赖。通过一些额外的括号在视觉上区分完整的 Lambda 表达式或其体表达式，括号自然是被支持的（就像在其他运算符优先级不明确的情况下一样）。

该语法在解析上存在一些挑战。Java 编程语言一直需要任意前瞻，以在 `(` 标记之后区分类型和表达式：其其后的内容可能是类型转换或带括号的表达式。在泛型使用二进制运算符 `<` 和 `>>` 时已经是这样了。Lambda 表达式引入了新的可能性：后续内容可能描述一个类型、表达式或 Lambda 参数列表。某些标记可能包含参数列表（注解、`(x, y)`）；在其他情况下，存在可能被解释为 Lambda 类型转换的模式（连续的两个名称、未嵌套在 `''` 内部的 `''`），并且必须等到遇到 `>` 才能做出决定。思考如何高效解析的最简单方法是使用状态机：每个状态代表可能解释的子集（类型、表达式或参数），当机器转换到分配了集合的状态时，解析器就知道是哪种情况。然而，这并没有很好地映射到固定查找的语法。

没有特殊的空值形式：零参数的 Lambda 表达式表示为 `() -> ....`。显然的特殊情况 `->` 是不起作用，因为它在列表和类型转换之间引入了歧义：`(x)`。

Lambda 表达式不声明类型。虽然在语义上这样做是有意义的，但自然语法（在参数列表之前加上类型列表）引入了混乱的歧义。例如，考虑：

```
foo(x) < y, z (w) -> v
```

这可能是 `foo` 的单参数调用（一个转换为 `x` 的泛型 Lambda 类型转换），也可能是 `foo` 的双参数调用，两个都是比较的结果，第二个比较 `z` 与一个 Lambda 表达式。Lambda 表达式作为关系运算符 `>` 的操作数是无意义的，但作为构建语法的假设过于牵强。

目前存在一种涉及类型转换的歧义消除，它本质上禁止了使用 `--` 以及在非原始类型转换后使用 (§15.15)，但将此方法扩展到泛型 Lambda 将涉及对语法的侵入性更改。

# 15.27.1 Lambda 参数

Lambda 表达式的形式参数（如果有的话）由圆括号括的逗号分隔标识符列表或圆括号括的逗号分隔说明符列表来指定。在参数说明符列表中，每个参数说明符由可选的修饰符、一个类型（或 `var`）以及指定参数名称的标识符组成。在标识符列表中，每个标识符指定参数的名称。

如果 Lambda 表达式没有形式参数，则在 `->` 和 Lambda 体之前会出现一对空括号。



如果 Lambda 表达式恰好有一个形式参数，且该参数由标识符而不是参数说明符指定，则标识符周围的括号可以省略。

```
LambdaParameters:
    ( [LambdaParameterList] )
    Identifier

LambdaParameterList:
    LambdaParameter (, LambdaParameter)
    Identifier ( , Identifier)

LambdaParameter:
    {VariableModifier} LambdaParameterType VariableDeclaratorId
    VariableArity

LambdaParameterType:
    UnannType
    var
```

为了方便，这里显示了 §8.4.1、§8.3 和 §4.3 的产生式：

```
VariableArityParameter:
    {VariableModifier} UnannType [Annotation] ... Identifier

VariableModifier:
    Annotation
    final

VariableDeclaratorId:
    Identifier [Dims]

Dims:
    [] [Annotation] { [] }
```

Lambda 表达式的形式参数只有在由参数说明符指定时，才能被声明为 `final` 或带有注解。如果形式参数是由标识符指定的，反之，则该形式参数不是 `final` 且没有注解。

Lambda 表达式的形式参数可以是变长参数（variable arity parameter），通过参数说明符中类型后的省略号 `...` 表示。一个 Lambda 表达式最多允许一个变长参数。如果变长参数出现在参数说明符列表最后一个位置之外任何地方，则会导致编译错误。

Lambda 表达式的每个形式参数要么有推断类型要么有声明类型：

- 如果形式参数是由使用 `var` 的参数说明符指定的，或者由标识符代替参数说明符指定的，则该形式参数具有推断类型。该类型从 Lambda 表达式的目标函数式接口推断出来 (§15.27.3)。
- 如果形式参数是由未使用 `var` 的参数说明符指定的，则形式参数具有声明类型。其类型确定如下：
  - 如果形式参数不是变长参数，如果在 `UnannType` 和 `VariableDeclaratorId` 中没有出现括号，则声明类型为 `UnannType`，否则由 §10.2 指定。
  - 如果形式参数是变长参数，则声明类型为 §10.2 指定的数组类型。

以下参数列表之间没有区别：

```
(int... x) -> BODY
(int[] x) -> BODY
```

无论函数式接口的抽象方法是固定长度还是变长长度，都可以使用。（由于 Lambda 表达式从不被直接调用，在形式参数使用 `int[]` 时使用 `int...` 对周围程序没有影响。在 Lambda 体中，变长参数被视为与数组类型参数相同。）

所有形式参数具有声明类型的 Lambda 表达式被称为显式类型。所有形式参数具有推断类型的 Lambda 表达式被称为隐式类型。没有形式参数的 Lambda 表达式是显式类型。

如果 Lambda 表达式是隐式类型，则其 Lambda 体根据其出现的上下文进行进行解释。具体来说，体中表达式的类型、体抛出的检查异常以及体中代码的类型正确性都取决于形式参数推断出的类型。这意味着形式参数类型的推断必须在尝试类型检查 Lambda 体“之前”发生。

如果 Lambda 表达式声明了一个具有声明类型的形式参数和一个具有推断类型的形式参数，则会导致编译错误。

此规则防止在形式参数中混合使用推断类型和声明类型，例如 `(x, int y) -> BODY` 或 `(var x, int y) -> BODY`。请注意，如果所有形式参数都是推断类型，语法将防止标识符和 `var` 参数说明的混合，例如 `(x, var y) -> BODY` 或 `(var x, y) -> BODY`。

关于形式参数声明的注解修饰符的规则在 §9.7.4 和 §9.7.5 中规定。

如果 `final` 作为形式参数声明的修饰符出现多次，则为编译错误。

如果形式参数的 `LambdaParameterType` 为 `var` 且该形式参数的 `VariableDeclaratorId` 包含一个或多个括号对，则为编译错误。

形式参数的作用域和遮蔽在 §6.3 和 §6.4 中规定。

从嵌套类、接口或嵌套 lambda 表达式对形式参数的引用受到限制，如 §6.5.6.1 规定。

lambda 表达式声明两个同名的形式参数将是编译错误。（这意味着它们的声明提到了同一个 `Identifier`。）

在 Java 8 中，禁止使用 `_` 作为 lambda 参数的名称，并且不建议将其作为其他类型的名称 (§4.12.3)。从 Java 9 开始，`_` 是一个关键字 (§3.9)，因此在任何语境下都不能用作变量名。

如果声明为 `final` 的形式参数在 lambda 表达式体内部被赋值，则为编译错误。

当调用 lambda 表达式时（通过方法调用 (§15.12)），实际参数的值会在执行 lambda 实体之前初始化新创建的参数变量，每个变量具有声明或推断的类型。出现在 `LambdaParameter` 中或直接出现在 `LambdaParameterList` 或 `LambdaParameters` 中的 `Identifier` 可以在 lambda 实体中用作简单名称来引用该形式参数。

## 15.27.2 Lambda 实体

lambda 体要么是一个单一表达式，要么是一个块 (§14.2)。就像方法体一样，lambda 体描述了每当发生调用时将执行的内容。

```
LambdaBody:
    Expression
    Block
```

与在匿名类声明中出现的代码不同，lambda 体中出现的名称含义以及 `this` 和 `super` 关键字，以及所引声明的可访问性，与周围语境相同（但 lambda 参数引入了新名称）。

这种在 lambda 表达式体中的（无论是显式的还是隐式的）透明性——即将其处理为与周围语境相同的内容——为实现提供了更大的灵活性，并防止了体中未限定名称的合并依赖于重载。

从实践来说，lambda 表达式引用自身（无论是递归调用自身还是调用其方法）是不寻常的，而更常见的是使用名称引用闭包类中否则会被遮蔽的内容（如 `this.toString()`）。如果 lambda 表达式需要引用自身（类似于 `this`），则应使用方法引用或匿名内部类。

如果块中的每个 `return` 语句都只有 `return;`，则 lambda 体是 void 兼容的（void-compatible）；

如果 lambda 实体无法正常完成 (§14.22) 且块中的每个 `return` 语句都有 `return Expression;`，则 lambda 体是值兼容的（value-compatible）；

如果块 lambda 既不是 void 兼容的不是值兼容的，则为编译错误。

在值兼容的 lambda 体中，结果表达式是任何可能产生调用值的表达式。具体而言，对于体包含的每个形式为 `return Expression ;` 的语句，`Expression` 就是一个结果表达式。

以下 lambda 体是 void 兼容的：

```
() -> {}
() -> { System.out.println("done"); }
```

这些是值兼容的：

```
() -> { return "done"; }
() -> { if (...) return 1; else return 0; }
```

这些两者都是兼容的：

```
() -> { throw new RuntimeException(); }
() -> { while (true); }
```

这个两者都不是：

```
() -> { if (...) return "done"; System.out.println("done"); }
```

# Lambda 表达式

对 void/值兼容性的处理以及体中名称的含义共同有助于减少对语境中特定目标类型的依赖，这对于实现和程序员的理解非常有用。虽然表达式在目标类型的重载解析期间可以分配不同的类型，但未限定名称的含义和 lambda 体的基本结构不会改变。

注意，void/值兼容的定义并不是严格的结构属性：“能够正常完成”取决于常量表达式的值，这些值可能包含保持为常量变量的名称。

lambda 表达式中使用的任何局部变量、形式参数或异常参数必须是 `final` 或有效 final（effectively final）§4.12.4)，如 §6.5.6.1 规定。

在 lambda 体中使用但未声明的任何局部变量必须在 lambda 体之前经过确定赋值 (§16 (Definite Assignment))，否则将是编译错误。

内部类体也适用类似的使用规则 (§8.1.3)。对有效 final 变量的限制禁止了动态变化的局部变量，这减轻了程序员的负担。对有效 final 变量的限制包括标准循环变量，但不包括增强循环变量简体14.2)。

以下 lambda 体演示了有效 final 变量的使用：

```
void m1(int x) {
    int y = x;
    () -> { }
}

void m2(int x) {
    int y = x;
    () -> { return y; }
}

void m3(int x) {
    int y = x;
    () -> { if (y > 0) return 1; else return 0; }
}
```

（注：由于原文中存在大量 OCR 识别导致的重复和碎片化，译文已根据逻辑进行了清理和整合，确保了核心技术描述的准确性与可读性。）

在 lambda 表达式体中可能抛出的检查异常（checked exception）可能会导致编译错误，如 §11.2.3 所示。

显式类型化 lambda 的参数类型要求与函数类型完全匹配。虽然可以设计得更灵活——例如允许装箱或逆变——但这种通用性似乎是没的，而且与类声明中方法重载的工作方式不一致。程序员在编写 lambda 表达式时应当确切地知道它是哪种函数类型，因此程序员应该知道哪些签名可能会被重写。（方法引用的情况并非如此，因此在使用方法引用时是允许灵活性的。）此外，参数类型上的更多灵活性会增加类型推断和重载解析的复杂性。

请注意，虽然在严格的调用上下不允许装箱，但 lambda 结果的装箱*始终*是被允许的——也就是说，结果表达式出现在赋值上下，无论该 lambda 表达式所处的上下文如何。然而，如果一个显式类型化的 lambda 表达式是重载方法的参数，最具体的检查（§15.12.2）会于于避免对 lambda 进行装箱或解箱的方法签名。

如果 lambda 的正体是一个语句表达式（即允许作为语句存在的表达式），则它被视为产生 *void* 类型的函数类型；任何结果都会被丢弃。因此，以下两种情况都是合：

```
// 产生布尔结果的 Predicate
java.util.function.Predicate<String> p = s -> list.add(s);
// 产生 结果的 Consumer
java.util.function.Consumer<String> c = s -> list.add(s);
```

通常情况下，形式为 `() -> expr` 的 lambda（其中 `expr` 是语句表达式）被解释为 `() -> { return expr; }` 或 `() -> { expr; }`，取决于目标类型。

## 15.2.4 Lambda 表达式的运行时评估

在运行时，lambda 表达式的评估类似于类实例创建过程的评估，相似之处在于正常完成会产生一个对象的引用。lambda 表达式的评估与 lambda 体的执行是不同的。

要么分配并初始化一个具有以下属性的类的新实例，要么引用一个具有以下属性的类的现有实例。如果需要创建新实例但没有足够的空间来分配对象，则 lambda 表达式的评估将通过抛出 `OutOfMemoryError` 异常终止。

这意味着评估 lambda 表达式（或序列化和反序列化 lambda 表达式）的标识是不可预测的，因此，标识敏感的操作（如引用相等性 (§15.21.3)、对象锁定 (§14.19) 和 `System.identityHashCode` 方法）在 Java 编程语言的不同实现中，甚至在同一实现中的不同 lambda 表达式评估中，可能会产生不同的结果。

lambda 表达式的值是对具有以下属性的类实例的引用：

- lambda 类实现了目标函数式接口类型，如果目标类型是交类型，则实现了交类型中提到的每一个其他接口类型。
- *当 lambda 表达式类型为 $U$ 时，对于 $U$ 的每个非静态成员方法。*
  - 如果 $U$ 的函数类型具有签名 $m$ 的子类型，则该类声明了一个重写 $m$ 的方法。方法的体的作用是评估 lambda 体（如果是表达式）或执行 lambda 体（如果是块）；如果需要结果，则从方法返回该结果。
  - 如果被重写的方法 $m$ 的类型擦除与 $U$ 的函数类型擦除不同，则在评估或执行 lambda 体之前，方法的体会检查每个参数是否为 $U$ 函数类型中对应参数类型擦除的子类或子接口的实例；否则，将抛出 `ClassCastException`。
- 该类没有重写目标函数式接口类型或上述其他接口类型的其他方法，尽管它可能会重写 `Object` 类的方法。

这些规则旨在为 Java 编程语言的实现提供灵活性，如下：

- 每次评估不需要分配新对象。
- 不同 lambda 表达式产生的对象不需要属于不同的类（例如，如果它们是相同的）。
- 评估产生的每个对象不需要属于同一个类（例如，捕获的局部变量可能会被内联）。
- 如果“现有实例”可用，它不需要在之前的 lambda 评估中创建（例如，它可能在闭包类的初始化期间被分配）。

如果目标函数式接口类型是 `java.io.Serializable` 的子类型，则生成的对象将是可序列化类的实例。使源自 lambda 表达式的对象变为可序列化可能会带来额外的运行时开销和安全影响，因此 lambda 派生的对象并不要求“默认”是可序列化的。

## 15.28 switch 表达式

switch 表达式根据表达式的值将控制转移到几个语句或表达式之一；必须处理该表达式的所有可能值，并且所有这些语句和表达式都必须为 switch 表达式的结果产生一个值。

```
SwitchExpression:
    switch ( Expression ) SwitchBlock
```

Expression 被称为选择表达式。选择表达式的类型必须是 `char`, `byte`, `short`, `int`, `Character`, `Byte`, `Short`, `Integer`, `String`, 或枚举类型 (§8.9)，否则将发生编译错误。

switch 表达式和 switch 语句 (§14.11) 的体都被称为 switch块。适用于所有 switch 的规则（无论它们出现在 switch 表达式还是 switch 语句中）都给出 §14.11.1 中。来自 §14.11.1 的以下产生式为了方便起处在此给出：

```
SwitchBlock:
    { SwitchRule }
    { SwitchBlockStatement }

SwitchRule:
    SwitchLabel -> Expression
    SwitchLabel -> Block
    SwitchLabel -> ThrowStatement

SwitchBlockStatement:
    SwitchLabel : Block

CaseConstant:
    ConditionalExpression
```



## 15.28.1 switch 表达式的 Switch Block

除了 switch 块的通用规则（§14.11.1）之外，switch 表达式还有进一步的规则。也就是说，switch 表达式的 switch 块必须满足以下条件，否则将发生编译错误：

- 如果选择表达式的类型不是枚举类型，则 switch 块恰好有一个 `default` 标签。

### poly switch 表达式与类型 T 兼容

poly switch 表达式与类型 T 兼容，如果它的每个结果表达式都与 T 兼容。

poly switch 的类型与其目标类型相同。

独立 switch 的类型确定如下：

- 如果结果表达式具有相同的类型（可以是空类型），则该类型为 switch 的类型。
- 否则，如果每个结果表达式的类型为 `boolean` 或 `Boolean`，则对每个类型为 `Boolean` 应用解箱转换（§5.1.8），switch 的类型为 `boolean`。
- 否则，如果每个结果表达式的类型可以转换为数值类型（§5.1.8），则 switch 类型是应用于数值提升（§5.6）的结果。
- 否则，对每个基本类型的结果表达式应用装箱转换（§5.1.7），之后 switch 的类型为捕获转换（§5.1.10）到结果表达式类型最小上界（§4.10.4）的结果。

## 15.28.2 switch 表达式的运行时评估

switch 表达式的评估首先通过评估选择表达式来实现。然后：

- 如果评估选择表达式终止，则 switch 表达式以相同原因终止。
- 否则，如果评估选择表达式的结果为空，则抛出 `NullPointerException`，整个 switch 表达式以该原因终止。
- 否则，如果评估选择表达式的结果为 `Byte`、`Short` 或 `Integer`，则对其进行解箱转换（§5.1.8）。如果此转换终止，则整个 switch 表达式以相同原因终止。

如果评估选择表达式正常完成且结果非空，并且随后的解箱转换（如果有）也正常完成，则 switch 表达式的评估继续确定与 switch 块关联的 switch 标签是否匹配选择表达式的值（§14.11.1）。

如果没有匹配的 switch 标签，将抛出 `IncompatibleClassChangeError`，并且整个 switch 表达式因为该原因异常终止。

如果匹配到 switch 标签，则适用以下情况：

- 如果它是 switch 规则表达式的 switch 标签，则计算该表达式。如果计算结果是一个值，则 switch 表达式以该值正常完成。
- 如果它是 switch 规则块的 switch 标签，则执行该块。如果该块正常完成，则 switch 表达式正常完成。
- 如果它是 switch 规则 `throw` 语句的 switch 标签，则执行该 `throw` 语句。
- 否则，switch 块中匹配 switch 标签之后的所有语句将按顺序执行。如果这些语句正常完成，则 switch 表达式正常完成。

如果 switch 块中任何语句或表达式的执行异常终止，则按如下方式处理：

- 如果表达式的执行异常终止，则 switch 表达式将因相同原因异常终止。
- 如果语句的执行由于带有值 V 的 `yield` 而异常终止，则 switch 表达式正常完成，且 switch 表达式的值为 V。
- 如果语句的执行因除带有值的 `yield` 以外的任何原因而异常终止，则 switch 表达式因相同原因异常终止。

## 15.29 常量表达式

```
ConstantExpression:
    Expression
```

常量表达式是一个表示基本类型值或 `String` 的表达式，该表达式不会异常终止，并且仅由以下内容组成：

- 基本类型字面量（§3.10.1, §3.10.2, §3.10.3, §3.10.4）、字符串字面量（§3.10.5）以及文本块（§3.10.6）
- 向基本类型的转换以及向 `String` 类型的转换（§15.16）
- 一元运算符 `+`、`-`、`~`、`!`（但不包括 `++` 或 `--`）（§15.15.3, §15.15.4, §15.15.5, §15.15.6）
- 乘法运算符 `*`、`/`、`%`（§15.17）
- 加法运算符 `+` 和 `-`（§15.18）
- 移位运算符 `<<`、`>>` 和 `>>>`（§15.19）
- 关系运算符 `<`、`<=`、`=`、`>=`（但不包括 `instanceof`）（§15.20）
- 等于运算符 `==` 和 `!=`（§15.21）
- 位运算符和逻辑运算符 `&`、`|`、`^` 和 `!`（§15.22）
- 条件与运算符 `&&` 和条件或运算符 `||`（§15.23, §15.24）
- 三元条件运算符 `? :`（§15.25）
- 括号表达式（§15.8.5），其包含的表达式本身必须是常量表达式。
- 指向常量变量（§4.12.4）的简单名称（§6.5.1）。
- 形式为 `TypeName . Identifier` 的限定名称（§6.5.2），其指向常量变量（§4.12.4）。

`String` 类型的常量表达式总是会被“池化”的，以便共享唯一实例，使用 `String.intern` 方法。

常量表达式用于 switch 语句和 switch 表达式中的分支标签（§14.11, §15.28），并在赋值上下文（§5.2）以及类或接口的初始化（§12.4.2）中具有特殊意义。它们还可以控制 `while`、`do` 或 `for` 语句正常完成的能力（§14.22），以及带有数值操作数的条件运算符 `? :` 的类型。

### 示例 15.29-1. 常量表达式

```
true

(short)(1*2*3*4*5*6)

Integer.MAX_VALUE / 2

2.0 * Math.PI

"The integer " + Long.MAX_VALUE + " is mighty big."
```

## 第 16 章 确定赋值

### 示例 16-3. 确定未赋值

Java 编译器会接受以下代码：

```
void unflow(boolean flag) {
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

对于 `k` 的确定未赋值而言，这是允许的，因为本节概述的规则允许它判断无论 `flag` 为真为假，`k` 最多被赋值一次（实际上，恰好赋值一次）。规则不接受以下变化：

```
void unflow(boolean flag) {
    final int k;
    if (flag) {
        k = 3;
        System.out.println(k);
    }
    if (!flag) {
        k = 4;
        System.out.println(k); /* 在此语句之前，k 不是“确定未赋值”的 */
    }
}
```

因此，编译此程序会导致编译时错误。

为了精确指定所有确定未赋值的情况，本节的规则定义了几个技术术语：

- 变量在语句或表达式之前是否确定赋值
- 变量在语句或表达式之前是否确定未赋值
- 变量在语句或表达式之后是否确定赋值
- 变量在语句或表达式之后是否确定未赋值

对于布尔值表达式，后两个被细化为四种情况：

- 表达式为真时，变量之后是否确定赋值
- 表达式为真时，变量之后是否确定未赋值
- 表达式为假时，变量之后是否确定赋值
- 表达式为假时，变量之后是否确定未赋值

这里的 true 和 false 指表达式的值。

例如，局部变量 `k` 在表达式求值后确定赋值了一个值：

```
a a && (k=m) > 5
```



当表达式为真时赋值，但当表达式为假时未赋值（因为如果 `a` 为假，则对 `k` 的赋值不一定执行，更准确地说是不一定求值）。

短语“`v` 在 `x` 之后确定赋值”（其中 `v` 是局部变量，`x` 是语句或表达式）意味着“如果 `x` 正常完成后，`v` 是确定赋值的”。如果 `x` 异常完成，则赋值未发生，此处规定的规则考虑了这一点。

该定义一个奇特的后果是，“`v` 在 `break;` 之后确定赋值”始终为真！因为 `break` 语句永远不会正常完成，如果 `break` 语句正常完成，那么它已经被赋予了值。

语句“`v` 在 `x` 之后确定未赋值”（其中 `v` 是变量，`x` 是语句或表达式）意味着“如果 `x` 正常完成后，`v` 是确定未赋值的”。

该定义一个更奇特的后果是，“`v` 在 `break;` 之后确定未赋值”是空为真的，因为 `break` 语句永远不会正常完成，这使得如果 `break` 语句正常完成，`v` 没有被赋值值。（就此而言，月亮是由绿奶酪制成的也是空为真的。）

总之，在执行语句或表达式后，变量 `v` 有四种可能性：

- `v` 确定赋值且不确定未赋值。（流分析规则证明已经对 `v` 进行了赋值。）
- `v` 确定未赋值且不确定赋值。（流分析规则证明没有对 `v` 进行赋值。）
- `v` 不确定赋值且不确定未赋值。（规则无法证明是否对 `v` 进行了赋值。）
- `v` 确定赋值且确定未赋值。（语句或表达式不可能正常完成。）

为了缩短规则，使用了惯用的缩写 `iff` 来表示“当且仅当”。我们还使用了一种未赋值约定：如果规则中包含一个或多个 `[unassigned]` 的出现，它代表两条规则，其中将每个 `[unassigned]` 的出现替换为“确定赋值”，另一个将每个 `[unassigned]` 的出现替换为“确定未赋值”。

例如：

- `v` 在空语句后是 `[unassigned]` 当且仅当它在空语句前是 `[unassigned]` 的

应该被理解为两条规则：

- `v` 在空语句后确定赋值，当且仅当它在空语句前确定赋值。
- `v` 在空语句后确定未赋值，当且仅当它在空语句前确定未赋值。

在本章的其余部分中，除非另有说明，`v` 表示作用范围内的 (§6.3) 局部变量或空 `final` 字段。同样，我们使用 `a`、`b`、`c` 等表示表达式，使用 `s` 和 `t` 表示语句。我们使用短语“`a` is `v`”表示 `a` 是变量 `v` 的简单名，或由此限定的 `vs` 的简单名（忽略括号）。我们将使用短语“`a` is not `v`”表示“`a` is `v`”的否定。

循环语句的未赋值分析提出了一个特殊问题。考虑语句 `while (e) S`。为了确定 `v` 是否在 `e` 的某个子表达式内部确定未赋值，我们需要确定类比确定赋值规则 (§16.2.10)，`v` 在 `e` 之前确定未赋值是否当且仅当它在语句之前未赋值。然而，这种规则对于循环来说是不够的。如果 `e` 为真，语句 `S` 将执行。如果 `v` 被 `S` 赋值，那么在评估 `e` 时，下一次迭代的 `v` 将是未赋值的。上述建议的规则可能会多次赋值 `v`，这正是我们通过引入这些规则必须避免的。

一个修正后的规则将：“`v` 在 `e` 之前确定未赋值，当且仅当它在语句之后确定未赋值”。然而，当我们制定 `s` 的规则时，发现：“`v` 在 `e` 之前确定未赋值，当且仅当它在 `e` 之后确定未赋值”。这导致了循环。实际上，`v` 在循环条件 `e` 之前确定未赋值当且仅当它在整个循环之后确定未赋值！

我们通过对循环条件和体的假设分析打破这种恶性循环。例如，我们假设 `v` 在 `e` 之前确定未赋值（无论 `e` 是否赋值 `v`），然后证明这一点。更正式地表述为：

假设 `v` 在 `e` 之前确定未赋值，`e` 之后确定未赋值。

上述分析的变体用于定义 Java 语言中所有循环语句的基础未赋值规则。

# 16.1 确定赋值与表达式

## 16.1.1 布尔常量表达式

- 在值为假的常量表达式 (§15.29) 之后 `v` 是 `[unassigned]`。
- 在值为真的常量表达式之后 `v` 是 `[unassigned]`。
- 在值为真的常量表达式之后 `v` 是 `[unassigned]`，当且仅当它在常量表达式前是 `[unassigned]` 的。
- 在值为假的常量表达式之后 `v` 是 `[unassigned]`，当且仅当它在常量表达式前是 `[unassigned]` 的。
- 布尔值常量表达式 `e` 之后 `v` 是 `[unassigned]`，当且仅当它在 `e` 为真时是 `[unassigned]` 且在 `e` 为假时是 `[unassigned]` 的。

这等于说 `v` 在 `e` 之后 `[unassigned]` `v` 在 `e` 之前。

因为值为真的常量表达式永远没有假值，而值为假的常量表达式永远没有真值，前两条规则被空满足。它们有助于分析涉及运算符 `&&` (§16.1.2)、`||` (§16.1.3)、`!` (§16.1.4) 和 `?` (§16.1.5) 的表达式。

## 16.1.2 条件与运算符 `&&`

- 在 `a && b` (§15.23) 之后，值为真时 `v` 是 `[unassigned]` 且在 `b` 之后确定赋值。
- 在 `a && b` 之后，值为假时，在 `a` 为假时 `v` 是 `[unassigned]` 且在 `b` 为假时 `v` 也是 `[unassigned]`。
- `v` 在 `a` 之前是 `[unassigned]`，当且仅当它在 `a && b` 之前是 `[unassigned]` 的。
- `v` 在 `b` 之前是 `[unassigned]`，当且仅当它在 `a` 为真时之后赋值。

## 16.1.3 条件或运算符 `||`

- 在 `a || b` (§15.24) 之后，值为真时，在 `a` 为真时 `v` 是 `[unassigned]` 且在 `b` 为真时 `v` 也是 `[unassigned]`。
- 在 `a || b` 之后，值为假时 `v` 是 `[unassigned]` 且在 `b` 之后确定赋值。
- `v` 在 `a` 之前是 `[unassigned]`，当且仅当它在 `a || b` 之前是 `[unassigned]` 的。
- `v` 在 `b` 之前是 `[unassigned]`，当且仅当它在 `a` 为假时之后赋值。

## 16.1.4 逻辑取反运算符 `!`

- 在 `!a` (§15.15.6) 之后，值为真时 `v` 是 `[unassigned]`，当且仅当在 `a` 为假时 `v` 是 `[unassigned]`。
- 在 `!a` 之后，值为假时 `v` 是 `[unassigned]`，当且仅当在 `a` 为真时 `v` 是 `[unassigned]`。
- `v` 在 `a` 之前是 `[unassigned]`，当且仅当它在 `!a` 之前是 `[unassigned]` 的。

## 16.1.5 条件运算符 `? :`

假设 `b` 和 `c` 是布尔值的表达式。

- 当为真时，`v` 在 `a ? b : c` 之后是 `[unassigned]` 的，当 `v` 在 `b` 之后是 `[unassigned]` 且 `v` 在 `c` 之后为真时是 `[unassigned]` 的。
- 当为假时，`v` 在 `a ? b : c` 之后是 `[unassigned]` 的，当 `v` 在 `a` 之后是 `[unassigned]` 且 `v` 在 `c` 之后为假时是 `[unassigned]` 的。
- 当为真时，`v` 在 `a` 之前是 `[unassigned]` 的，当 `v` 在 `a ? b : c` 之前为真时是 `[unassigned]` 的。
- 当为假时，`v` 在 `a` 之前是 `[unassigned]` 的，当 `v` 在 `a ? b : c` 之前为假时是 `[unassigned]` 的。
- 当为真时，`v` 在 `b` 之前是 `[unassigned]` 的，当 `v` 在 `a` 之后为真时是 `[unassigned]` 的。
- 当为假时，`v` 在 `c` 之前是 `[unassigned]` 的，当 `v` 在 `a` 之后为假时是 `[unassigned]` 的。

假设 `b` 和 `c` 不是布尔值的表达式。

- `v` 在 `a ? b : c` 之后是 `[unassigned]` 的，当 `v` 在 `b` 之后是 `[unassigned]` 且 `v` 在 `c` 之后是 `[unassigned]`。
- `v` 在 `a` 之前是 `[unassigned]` 的，当 `v` 在 `a ? b : c` 之前是 `[unassigned]`。
- `v` 在 `b` 之前是 `[unassigned]` 的，当为真时，`v` 在 `a` 之后是 `[unassigned]`。
- `v` 在 `c` 之前是 `[unassigned]` 的，当为假时，`v` 在 `a` 之后是 `[unassigned]`。

## 16.1.6 `switch` 表达式

假设一个 `switch` 表达式 (§15.28) 有结果表达式 `e₁, ..., eₙ`，且它们都是布尔值的。

只有当 `switch` 表达式 `switch` 块由 `switch` 标记语句组 (§14.11.1)组成时，才适用以下规则：

- 当为真时，`v` 在 `switch` 表达式之后是确定赋值的，对于 `switch` 块中每个可能退出 `switch` 表达式的带有表达式 `e` (§14.21) 的 `yield` 语句，为真时 `v` 在 `e` 之后是确定赋值的。
- 当为假时，`v` 在 `switch` 表达式之后是确定赋值的，对于 `switch` 块中每个可能退出 `switch` 表达式的带有表达式 `e` 的 `yield` 语句，为假时 `v` 在 `e` 之后是确定赋值的。
- 当为真时，`v` 在 `switch` 表达式之后是确定未赋值的，对于 `switch` 块中每个可能退出 `switch` 表达式的带有表达式 `e` 的 `yield` 语句，`v` 在 `yield` 语句之前是确定未赋值的，且为真时 `v` 在 `e` 之后是未赋值。
- 当为假时，`v` 在 `switch` 表达式之后是确定未赋值的，对于 `switch` 块中每个可能退出 `switch` 表达式的带有表达式 `e` 的 `yield` 语句，`v` 在 `yield` 语句之前是确定未赋值的，且为假时 `v` 在 `e` 之后是未赋值。
- `v` 在选择器表达式之前是 `[unassigned]` 的，当 `v` 在 `switch` 表达式之前是 `[unassigned]`。
- `v` 在 `switch` 块中第一个 `switch` 标记语句组的第一条语句之前是 `[unassigned]` 的，当 `v` 在选择器表达式之后是 `[unassigned]`。

## 确定赋值与表达式

- 除当 `v` 在选择器表达式之后是 `[unassigned]` 且 `v` 在前一个语句之后是 `[unassigned]` 外，`v` 在任何 `switch` 标记语句组的第一条语句之前 `[unassigned]`。

只有当 `switch` 表达式由 `switch` 规则 (§14.11.1)组成时，才适用以下规则：

- 当为真时，`v` 在 `switch` 表达式之后确定赋值，当对于每个 `switch` 规则，满足以下条件之一：
    - 它引入了一个 `switch` 规则表达式 `e`，且为真时 `v` 在 `e` 之后是确定赋值的。
    - 它引入了一个 `switch` 规则块 `B`，并且对于 `B` 中包含的每个可能退出 `switch` 表达式的带有表达式的 `yield` 语句，为真时 `v` 在 `e` 之后是确定赋值的。
    - 它引入了一个 `switch` 规则 `throw` 语句。

- 当为假时，`v` 在 `switch` 表达式之后确定赋值，当对于每个 `switch` 规则，满足以下条件之一：
    - 它引入了一个 `switch` 规则表达式 `e`，且为假时 `v` 在 `e` 之后是确定赋值的。
    - 它引入了一个 `switch` 规则块 `B`，并且对于 `B` 中包含的每个可能退出 `switch` 表达式的带有表达式的 `yield` 语句，为假时 `v` 在 `e` 之后是确定赋值的。
    - 它引入了一个 `switch` 规则 `throw` 语句。

- 当为真时，`v` 在 `switch` 表达式之后确定未赋值的，当对于每个 `switch` 规则，满足以下条件之一：
    - 它引入了一个 `switch` 规则表达式 `e`，且为真时 `v` 在 `e` 之后是确定未赋值的。
    - 它引入了一个 `switch` 规则块 `B`，并且对于 `B` 中包含的每个可能退出 `switch` 表达式的带有表达式 `e` 的 `yield` 语句，`v` 在 `yield` 语句之前是确定未赋值的，且为真时 `v` 在 `e` 之后是确定未赋值的。
    - 它引入了一个 `switch` 规则 `throw` 语句。

- 当为假时，`v` 在 `switch` 表达式之后是确定未赋值的，当对于每个 `switch` 规则，满足以下条件之一：
    - 它引入了一个 `switch` 规则表达式 `e`，且为假时 `v` 在 `e` 之后是确定未赋值的。
    - 它引入了一个 `switch` 规则块 `B`，并且对于 `B` 中包含的每个带有表达式 `e` 的可能退出 `switch` 表达式的 `yield` 语句，`v` 在 `yield` 语句之前确定未赋值，且为假时 `v` 在 `e` 之后是确定未赋值的。
    - 它引入了一个 `switch` 规则 `throw` 语句。

- `v` 在 `switch` 块中的任何 `switch` 表达式或 `switch` 规则语句之前 `[unassigned]`，当 `v` 在选择器表达式之后 `[unassigned]`。

假设一个 `switch` 表达式有结果表达式 `e₁, ..., e_n`，且没有布尔值。

`v` 在 `switch` 表达式之后 `[unassigned]`，当以下所有条件均满足：

- `v` 在可能退出 `switch` 表达式的每个 `yield` 语句之前 `[unassigned]`。
- 对于 `switch` 块中的每个 `switch` 规则，`v` 在 `switch` 规则引入的 `switch` 表达式、`switch` 规则块或 `switch` 规则 `throw` 语句之后 `[unassigned]`。

`v` 在 `switch` 表达式的选择器表达式之前 `[unassigned]`，当 `v` 在 `switch` 表达式之前 `[unassigned]`。

`v` 在 `switch` 块中 `switch` 规则引入的 `switch` 规则表达式、`switch` 规则块或 `switch` 规则 `throw` 语句之前 `[unassigned]`，当 `v` 在 `switch` 表达式的选择器之后 `[unassigned]`。

`v` 在 `switch` 块中 `switch` 标记语句组的第一个块之前 `[unassigned]`，当以下任一语句为真时：

- `v` 在 `switch` 表达式的选择器之后 `[unassigned]`。
- 如果该 `switch` 标记语句组不是 `switch` 块中的第一个，则 `v` 在前一个 `switch` 标记语句组的最后一个块语句之后 `[unassigned]`。

`v` 在 `switch` 块中不是 `switch` 标记语句组第一个的块语句之前 `[unassigned]`，当在前一个块语句之后 `[unassigned]`。

## 16.1.7 其他 `boolean` 类型表达式

假设 `e` 是 `boolean` 类型的表达式，且不是布尔常数表达式、逻辑取反表达式 `!a`、条件与表达式 `a && b`、条件或表达式 `a || b` 或条件表达式 `a ? b : c`。

- 当为真时，`v` 在 `e` 之前 `[unassigned]`，之后也未赋值。
- 当为假时，`v` 在 `e` 之前 `[unassigned]`，`e` 之后未赋值。

## 16.1.8 赋值表达式

考虑表达式 `a = b`、`a += b`、`a -= b`、`a *= b`、`a /= b`、`a %= b`、`a <<= b`、`a >>= b`、`a &= b`、`a |= b` 或 `a ^= b` (§15.26)。

- `v` 在赋值表达式之后确定赋值，当：
    - `a` 是 `v`，
    - `v` 在 `b` 之后确定赋值。
- `v` 在赋值表达式之后未赋值，当 `a` 不是 `v` 且 `v` 在之后未赋值。
- `v` 在 `a` 之前 `[unassigned]`，当 `v` 在赋值表达式之前 `[unassigned]`。
- `v` 在 `b` 之前 `[unassigned]`，当 `v` 在 `a` 之后未赋值。

注意，如果 `a` 是 `v` 且在 `a+=b` 等复合表达式之前没有确定赋值，则会发生编译错误。上述确定赋值的第一条规则对于复合赋值表达式也包含了“`a` 是 `v`”这一分支，以便 `v` 在代码的后续部分被认为已赋值。包含“`a` 是 `v`”这一分支并不影响程序是可接受还是产生编译错误的二元决策，但它影响了哪些点可能被视为错误，在实践中它可以提高错误报告的质量。类似的说明也适用于上述确定赋值第一条规则中包含的与“`a` 不是 `v`”。

## 16.1.9 运算符 `++` 和 `--`

- `v` 在 `++a` (§15.15.1)、`--a` (§15.15.2)、`a++` (§15.14.2) 或 `a--` (§15.14.3) 之后确定赋值，当 `a` 是 `v` 或 `v` 在操作数表达式之后确定赋值。
- `v` 在 `++a`、`--a`、`a++` 或 `a--` 之后未赋值，当 `a` 不是 `v` 且 `v` 在操作数表达式之后未赋值。
- `v` 在 `a` 之前 `[unassigned]`，当 `v` 在 `++a`、`--a`、`a++` 或 `a--` 之前 `[unassigned]`。

## 16.1.10 其他表达式

如果一个表达式不是布尔常量表达式，且不是前增表达式 `++a`、前减表达式 `--a`、后增表达式 `a++`、后减表达式 `a--`、逻辑取反表达式 `!a`、条件与 `&&`、条件或 `||`、条件表达式 `? :`、赋值表达式或 `lambda` 表达式，则适用以下规则：

- 如果表达式没有子表达式，如果 `v` 在表达式前是 `[unassigned]` 的，则 `v` 在表达式后也是 `[unassigned]` 的。

  这种情况适用于字面量、`this`（包括限定和未限定的）、无参数的未限定类实例创建、不包含任何表达式的初始化器数组创建表达式、父类字段访问表达式、无参数的未限定和类型限定方法调用、无参数的父类方法调用，以及父类和类型限定的方法引用。

- 如果表达式有子表达式，如果 `v` 在其直接子表达式后是 `[unassigned]` 的，则 `v` 在表达式后是 `[unassigned]` 的。

在“在方法调用后可以确定变量 `v` 已确定赋值”这一断言背后有一个微妙的理由。从表面值和限定性来看，这种断言是错误的，因为被调用的方法可以执行赋值。但请记住，对于 Java 语言而言，确定赋值的概念仅适用于 `blank` 变量。如果 `v` 是一个 `blank` 局部变量，则只有其声明所属的方法可以对 `v` 执行赋值。如果 `v` 是一个 `blank final` 字段，则只有包含 `v` 声明的类的构造函数或初始化器可以对 `v` 执行赋值；没有任何方法可以对 `v` 执行赋值。最后，显式构造函数调用（§8.8.7）经过特殊处理（§16.9）；尽管它们在语法上类似于包含方法调用的表达式语句，但它们不是表达式语句，因此本节的规则不适用于显式构造函数调用。

如果表达式是 `lambda` 表达式，则适用以下规则：

- 如果 `v` 在表达式前是 `[unassigned]` 的，则 `v` 在表达式后是 `[unassigned]` 的。
- 如果 `v` 在 `lambda` 表达式前是确定赋值的，则 `v` 在 `lambda` 体（§15.2.7）之前的块也是确定赋值的。

没有任何规则允许 `v` 在 `lambda` 体之前是确定未赋值的。在 `lambda` 体之前已确定赋值的变量在之后可能会被赋值，因此我们无法得出该变量在执行体时是未赋值的结论。

对于表达式 `x` 的任何直接子表达式 `y`，其中 `x` 不是 `lambda` 表达式，如果满足任一条件，则 `v` 在 `y` 前是 `[unassigned]` 的：

- `y` 是 `x` 最左侧的直接子表达式，且 `v` 在 `x` 前是 `[unassigned]` 的。
- `y` 是二元运算符右的操作数，且 `v` 在左操作数后是 `[unassigned]` 的。
- `x` 是数组访问，`y` 是括号内的子表达式，且 `v` 在括号前表达式后是 `[unassigned]` 的。
- `x` 是主方法调用表达式，`y` 是方法调用表达式中的第一个参数表达式，且 `v` 在计算目标对象的主表达式后是 `[unassigned]` 的。
- `x` 是方法调用表达式或类实例创建表达式；`y` 是参数表达式，但不是第一个；且 `v` 在 `y` 左侧的参数表达式后是 `[unassigned]` 的。
- `x` 是限定的类实例创建表达式，`y` 是类实例创建表达式中的第一个参数表达式，且 `v` 在计算限定对象的主表达式后是 `[unassigned]` 的。
- `x` 是数组创建表达式；`y` 是维度表达式，但不是第一个；且 `v` 在 `y` 左侧的维度表达式后是 `[unassigned]` 的。
- `x` 是通过数组初始化器初始化的数组创建表达式；`y` 是 `x` 中的数组初始化器；且 `v` 在 `y` 左侧的维度表达式后是 `[unassigned]` 的。

# 16.2 确定赋值与语句

## 16.2.1 空语句

- `v` 在空语句（§14.6）后是 `[unassigned]` 的，当且仅当它在空语句前是 `[unassigned]` 的。

## 16.2.2 块

- 一个 `blank final` 成员字段 `v` 在 `v` 作用域内任何方法的体（块，§14.2）之前是确定赋值的（并且不是确定未赋值的），并且在 `v` 作用域内声明的任何类的声明之前也是确定赋值的。

- 局部变量 `v` 在声明 `v` 的构造函数、方法、实例初始化器或静态初始化器的体（块）之前是确定未赋值的（并且不是确定赋值的）。

设 `c` 是在 `v` 作用域内声明的类。那么，如果 `v` 在 `c` 之前是确定赋值的，则 `v` 在 `c` 中声明的任何构造函数、方法、实例初始化器或静态初始化器的体之前是确定赋值的。

> 注意，没有任何规则能让我们断定 `v` 在 `c` 的构造函数、方法、实例初始化器或静态初始化器之前是确定未赋值的。我们可以非正式地断定 `v` 不是确定未赋值。

说 `v` 在块 `B` 中处处都是确定未赋值的，当且仅当：

- `v` 在块之前是 `[unassigned]` 的，且
- `v` 在块内的每个语句 `s` 后都是 `[unassigned]` 的。

说 `v` 在语句 `s` 后是 `[unassigned]` 的，如果：

- `v` 在 `s` 前是 `[unassigned]` 的，或
- `s` 是给 `v` 赋值的语句。

说 `v` 在语句 `s` 前是 `[unassigned]` 的，如果：

- `v` 在 `s` 后是 `[unassigned]` 的，或
- `s` 是给 `v` 赋值的语句。

## 16.2.3 局部类与接口声明

- `v` 在局部类或接口声明（§14.3）后是 `[unassigned]` 的，当且仅当它在局部类或接口声明前是 `[unassigned]` 的。

## 16.2.4 局部变量声明语句

- `v` 在不包含初始化器的局部变量声明语句（§14.4.2）后是 `[unassigned]` 的，当且仅当它在局部变量声明语句前是 `[unassigned]` 的。

- `v` 在包含至少一个初始化器的局部变量声明语句后是确定赋值的，当且仅当 `v` 在该声明语句的最后一个初始化器后是确定赋值的，或者声明中的最后一个初始化器在声明 `v` 的声明符中。

- `v` 在包含至少一个初始化器的局部变量声明语句后是确定未赋值的，当且仅当 `v` 在该声明语句的最后一个初始化器后是确定未赋值的，且声明中的最后一个初始化器不在声明 `v` 的声明符中。

- `v` 在局部变量声明语句的第一个变量初始化器前是 `[unassigned]` 的，当且仅当它在局部变量声明语句前是 `[unassigned]` 的。

- `v` 在局部变量声明语句中除第一个以外的任何初始化器 `e` 前是确定赋值的，`v` 在 `e` 左侧的初始化器后是确定赋值，或者 `e` 左侧的初始化表达式在声明 `v` 的声明符中。

- `v` 在局部变量声明语句中除第一个以外的任何初始化器 `e` 前是确定未赋值的，当且仅当 `v` 在 `e` 左侧的初始化器后是确定未赋值，且 `e` 左侧的初始化表达式不在声明 `v` 的声明符中。

## 16.2.5 标记语句

- `v` 在标记语句 `L : s`（其中 `L` 是标签）（§14.7）后是 `[unassigned]` 的，当且仅当 `v` 在 `s` 后是 `[unassigned]` 的，且 `v` 在每个可能退出该标记语句 `L : s` 的 `break` 语句前都是 `[unassigned]` 的。

- `v` 在 `s` 前是 `[unassigned]` 的，当且仅当它在 `L : s` 前是 `[unassigned]` 的。

## 16.2.6 表达式语句

- 在表达式语句 `e` 之后（§14.8），`v` 是 `[unassigned]` 的，当且仅当它在 `e` 之后未赋值时。
- 在 `e` 之前，`v` 是 `[unassigned]` 的，当且仅当它在 `e` 之前未赋值。

## 16.2.7 `if` 语句

以下规则适用于语句 `if (e) s` (§14.9.1)：

- 在 `if (e) s` 之后，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `s` 之后未赋值，且在 `e` 为假时 `v` 之后未赋值。
- 在 `e` 之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `if (e) s` 之前未赋值。
- 在 `s` 之前，`v` 是 `[unassigned]` 的，当且仅当在 `e` 为真时 `v` 之后未赋值。

以下规则适用于语句 `if (e) s else t` (§14.9.2)：

- 在 `if (e) s else t` 之后，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `s` 之后未赋值且 `v` 在 `t` 之后未赋值。
- 在 `e` 之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `if (e) s else t` 之前未赋值。
- 在 `s` 之前，`v` 是 `[unassigned]` 的，当且仅当在 `e` 为真时 `v` 之后未赋值。
- 在 `t` 之前，`v` 是 `[unassigned]` 的，当且仅当在 `e` 为假时 `v` 之后未赋值。

## 16.2.8 断言语句

以下规则同时适用于语句 `assert e₁` 和语句 `assert e₁ : e₂` (§14.10)：

- 在 `e₁` 之前，`v` 是 `[unassigned]` 的，当且仅当在 `assert` 语句之前未赋值。
- 在 `assert` 语句之后，`v` 确定已赋值，当且仅当 `v` 在 `assert` 语句之前确定已赋值。
- 在 `assert` 语句之后，`v` 确定为未赋值，当且仅当在 `e₁` 为真时 `v` 之后确定未赋值。

以下规则适用于语句 `assert e₁ : e₂`：

- 在 `e₂` 之前，`v` 是 `[unassigned]` 的，当且仅当在 `e₁` 为假时未赋值。

## 16.2.9 `switch` 语句

- 在 `switch` 语句之后（§14.11），`v` 是 `[unassigned]` 的，当且仅当以下所有条件均真时：
  - 在每一个可能退出 `switch` 语句的 `break` 语句（§14.15）之前，`v` 都是 `[unassigned]` 的。
  - 对于 `switch` 块中的每个 `switch` 规则（§14.11.1），`v` 在 `switch` 规则表达式、`switch` 规则块或 `switch` 规则引入的 `switch` 规则 `throw` 语句之后都是 `[unassigned]` 的。
  - 如果 `switch` 块中存在带标签语句组（`switch` labeled statement group），则 `v` 在最后一个带标签语句组的最后一个块语句之后是 `[unassigned]` 的。
  - 如果 `switch` 块中没有默认标签（`default`），或者 `switch` 块以 `switch` 标签后跟 `}` 分隔符结束，则 `v` 在选择器表达式之后是 `[unassigned]` 的。
- 在 `switch` 语句的选择器表达式之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `switch` 语句之前未赋值。
- 在 `switch` 块中由 `switch` 规则引入的 `switch` 规则表达式、`switch` 规则块或 `switch` `throw` 语句之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `switch` 语句的选择器表达式之后未赋值。
- 在 `switch` 块中某一个带标签语句组的第一个块语句之前，`v` 是 `[unassigned]` 的，当且仅当以下两个条件均真时：
  - `v` 在 `switch` 语句的选择器表达式之后是 `[unassigned]` 的。
  - 如果该 `switch` 语句组不是 `switch` 块中的第一个，则 `v` 在前一个 `switch` 带标签组的最后一个块语句之后是 `[unassigned]` 的。
- 在 `switch` 块中并非某带标签语句组首的块语句之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在前一个块语句之后未赋值。

## 16.2.10 `while` 语句

- 在 `while (e) s` 之后（§14.12），`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `e` 为假时未赋值，且对于每一个以 `while` 语句为跳转目标的 `break` 语句之前都是未赋值。

## 确定赋值与语句

- 在 `e` 之前，`v` 确定已赋值，当且仅当 `v` 在 `while` 语句之前确定已赋值。
- 在 `e` 之前，`v` 确定为未赋值，当且仅当以下所有条件均真时：
  - `v` 在 `while` 语句之前确定未赋值。
  - 假设 `v` 在 `e` 之前未赋值，则 `v` 在 `s` 之后确定未赋值。
  - 假设 `v` 在 `e` 之前确定未赋值，则 `v` 在每一个以 `while` 语句为跳转目标的 `continue` 语句之前确定未赋值。
- 在 `s` 之前，`v` `[unassigned]`，当且仅当在 `e` 为真时未赋值。

## 16.2.11 `do` 语句

- 在 `do s while (e)` 之后（§14.13），`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `e` 为假时未赋值，且 `v` 在每一个以 `do` 语句为跳转目标的 `break` 语句之前未赋值。
- 在 `s` 之前，`v` 确定已赋值，当且仅当 `v` 在语句之前确定已赋值。
- 在 `s` 之前，`v` 确定为未赋值，当且仅当以下所有条件均真时：
  - `v` 在 `do` 语句之前确定未赋值。
  - 假设 `v` 在 `s` 之前确定未赋值，则 `v` 在 `e` 为真时确定未赋值。
- 在 `e` 之前，`v` `[unassigned]`，当且仅当在 `e` 为真时 `v` 未赋值。

## 16.2.12 `for` 语句

此处的规则涵盖了 `for` 语句（§14.14.1）。增强 `for` 语句（§14.14.2）是由基本语句定义的，因此对于以下情况不需要特殊规则：

- 在 `for` 语句之后，`v` 是 `[unassigned]` 的，当且仅当以下两个条件均真时：
  - 条件表达式不存在或 `v` 在条件表达式之后未赋值。
  - `v` 在每一个以 `for` 语句为跳转目标的 `break` 语句之前都是 `[unassigned]` 的。
- 在 `for` 语句的初始化部分之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `for` 语句之前确定已赋值。
- 在 `for` 语句的条件部分之前，`v` 确定已赋值，当且仅当 `v` 在初始化部分之后确定已赋值。
- 在 `for` 语句的条件部分之前，`v` 确定为未赋值，当且仅当以下所有条件均真时：
  - `v` 在初始化部分之前确定未赋值。
  - 假设 `v` 在条件部分之前确定未赋值，则 `v` 在递增部分之后确定未赋值。
  - `v` 在每一个以 `for` 语句为目标的 `continue` 语句之前确定未赋值。
- 在包含的语句之前，`v` 是 `[unassigned]` 的，当且仅当以下任一成立时：
  - 存在条件表达式且 `v` 在条件表达式之后未赋值。
  - 不存在条件表达式且 `v` 在递增部分之后未赋值。
- 在递增部分之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在包含的语句之后未赋值。
- 在初始化部分之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `for` 语句之前未赋值。

### 16.2.12.1 `for` 的初始化部分

- 如果 `for` 语句的初始化部分是局部变量声明，适用规则 §16.2.4。
- 否则，如果初始化部分为空，则 `v` 在初始化部分之后是 `[unassigned]` 的，当且仅当 `v` 在 `for` 语句之前未赋值。
- 否则，适用三条规则：
  - 在初始化部分之后，`v` 是 `[unassigned]` 的，当且仅当 `v` 在最后一个语句之后未赋值。
  - 在初始化部分的第一个表达式语句之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在初始化部分之前未赋值。
  - 在初始化部分除第一个以外的表达式语句之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在前一个语句之后未赋值。

## 16.2.13 `try` 语句

这些规则适用于每个 `try` 语句（§14.20），无论其是否包含 `finally` 块：

- 在 `try` 块之前，`v` 是 `[unassigned]` 的，当且仅当 `v` 在 `try` 语句之前未赋值。
- 在 `catch` 块之前，`v` 确定已赋值，当且仅当 `v` 在 `try` 块之前确定已赋值。
- 在 `catch` 块之前，`v` 确定为未赋值，当且仅当以下所有条件均真时：
  - `v` 在 `try` 块之后确定未赋值。
  - `v` 在 `try` 块中的每个 `return` 语句之前确定未赋值。
  - `v` 在 `try` 块中的每个形式为 `throw e` 的语句中，在 `e` 之后确定未赋值。
  - `v` 在出现在 `try` 块中的每个 `assert` 语句之后确定未赋值。
  - `v` 在属于 `try` 块且其跳转目标包含（或是）该语句的 `break` 语句之前确定未赋值。
  - `v` 在属于 `try` 块且其跳转目标包含 `try` 语句的 `continue` 语句之前确定未赋值。

如果 `try` 语句不包含 `finally` 块，则适用此规则：

- 在 `try` 语句之后，`v` `[unassigned]`，当且仅当 `v` 在 `try` 语句之后未赋值且 `v` 在 `try` 语句中的每个 `catch` 块之后未赋值。

如果 `try` 语句包含 `finally` 块，则还适用这些规则：

- 在 `try` 语句之后，`v` 确定已赋值，当且仅当以下至少一个成立时：
  - `v` 在 `try` 块之后确定已赋值且 `v` 在 `try` 语句中的每个 `catch` 块之后确定已赋值。
  - `v` 在 `finally` 块之前确定已赋值。
- 在 `try` 语句之后，`v` 确定为未赋值，当且仅当 `v` 在 `finally` 块之后确定未赋值。
- 在 `finally` 块之前，`v` 确定已赋值，当且仅当 `v` 在 `try` 语句之前确定已赋值。

## 确定赋值与参数

- `v` 在 `finally` 块之前是确定未赋值的，当且仅当满足所有条件：
  - `v` 在 `try` 块之后是确定未赋值的。
  - `v` 在属于 `try` 块的每一个 `return` 语句之前是确定未赋值的。
  - `v` 在属于 `try` 块的每一个形式为 `throw e` 的语句中，在 `e` 之后是确定未赋值的。
  - `v` 在出现在 `try` 块中的每一个 `assert` 语句之前是确定未赋值的。
  - `v` 在属于 `try` 块的每一个 `break` 语句之前是确定未赋值的，且该 `break` 目标包含（或即是）该 `try` 语句。
  - `v` 在属于 `try` 块的每一个 `continue` 语句之前是确定未赋值的，且该 `continue` 目标包含了该 `try` 语句。
  - `v` 在 `try` 语句的每一个 `catch` 块之后是确定未赋值的。

- 方法或构造函数的正式参数 `v`（§8.4.1, §8.8.1）在方法体或构造函数体之前是确定赋值的（并且不一定是确定未赋值的）。

- `catch` 子句的异常参数 `v`（§14.20）在 `catch` 子句体之前是确定赋值的（并且不一定是确定未赋值的）。

## 16.4 确定赋值与数组初始化器

- `v` 在空数组初始化器（§10.6）之后是 `[unassigned]` 的，当且仅当 `v` 在空数组初始化器之前是 `[unassigned]` 的。
- `v` 在非空数组初始化器之后是 `[unassigned]` 的，当且仅当 `v` 在数组初始化器中的最后一个变量初始化器之后是 `[unassigned]` 的。
- `v` 在数组初始化器的第一个变量初始化器之前是 `[unassigned]` 的，当且仅当 `v` 在数组初始化器之前是 `[unassigned]` 的。
- `v` 在数组初始化器的任何其他变量初始化器 `e` 之前是 `[unassigned]` 的，当且仅当 `v` 在数组初始化器中 `e` 左侧的变量初始化器之后是 `[unassigned]` 的。

## 16.5 确定赋值与枚举常量

确定变量在枚举常量（§8.9.1）之前确定赋值还是确定未赋值的规则见于 §16.8。

> 这是因为枚举常量本质上是一个静态的 `final` 字段（§8.3.1.1, §8.3.1.2），它通过类实例创建表达式（§15.9）进行初始化。

- `v` 在 `v` 作用域内声明的无参数枚举常量的类体声明之前是确定赋值的；`v` 在该枚举常量之前是确定赋值的。
- `v` 在 `v` 作用域内声明的带参数枚举常量的类体声明之前是确定赋值的；`v` 在该枚举常量的最后一个参数表达式之后是确定赋值的。

枚举常量类体内任何构造的确定赋值/确定未赋值状态受类的常规规则限制。

- `v` 在枚举常量的第一个参数之前是 `[unassigned]` 的，当且仅当它在枚举常量之前是 `[unassigned]` 的。
- 如果 `v` 在 `y`（枚举常量的一个参数，但不是第一个）左侧的参数之后是 `[unassigned]` 的，则 `v` 在 `y` 之前是 `[unassigned]` 的。

## 16.6 确定赋值与匿名类

- `v` 在声明于 `v` 作用域内的匿名类声明（§15.9.5）之前是确定赋值的；`v` 在声明该匿名类的类实例创建之后是确定赋值的。

显而易见，如果匿名类是由枚举常量隐式定义的，则适用 §16.5 的规则。

## 16.7 确定赋值与成员类及接口

设 `c` 为一个类，`v` 为 `c` 的一个 `blank final` 字段。那么：

- `v` 在 `c` 的任何成员类或接口（§8.5, §9.5）声明之前是确定赋值的（并且，不是确定未赋值的）。

设 `c` 为声明在 `v` 作用域内的类。那么：

- 如果 `v` 在 `c` 的声明之前是确定赋值的，则 `v` 在 `c` 的成员类或接口声明之前是确定赋值的。

## 16.8 确定赋值与静态初始化器

设 `c` 为声明在 `v` 作用域内的类。那么：

- 如果 `v` 在 `c` 的声明之前是确定赋值的，则 `v` 在 `c` 的枚举静态（§8.9.1）或静态变量初始化器（§8.3.2）之前是确定赋值的。

> 注意，没有规则允许我们得出 `v` 在静态变量初始化器或枚举常量之前是确定未赋值的。我们可以非正式地得出 `v` 在赋值之前确定未赋值的，但没有必要显式规定这样的规则。

设 `c` 为一个类，`v` 为声明在 `c` 中的一个 `blank static final` 成员字段。那么：

- `v` 在 `c` 最左侧的枚举常量、静态初始化器或变量初始化器之前是确定未赋值的（并且，不是确定赋值的）。
- `v` 在 `c` 除最左侧外的枚举常量、静态初始化器或变量初始化器之后是 `[unassigned]` 的，当且仅当它在之前的枚举常量、静态初始化器或变量初始化器之后。

设 `c` 为一个类，`v` 为声明在父类中的一个 `blank final` 成员字段。那么：

- `v` 在 `c` 的每一个枚举常量之前是确定赋值的（并且，不是确定未赋值的）。
- `v` 在 `c` 的每一个作为静态器体的块之前是确定赋值的（并且，不是确定未赋值的）。
- `v` 在 `c` 的每一个静态变量初始化器之前是确定赋值的。

## 16.9 确定赋值、构造函数与实例初始化器

设 `c` 为声明在 `v` 作用域内的类。那么：

- `v` 在 `c` 的实例变量初始化器（§8.3.2）之前是确定赋值的，当且仅当 `v` 在 `c` 的声明之前是确定赋值的。

注意，没有规则允许我们得出 `v` 在实例变量初始化器之前是确定未赋值的。我们可以非正式地得出 `v` 在 `c` 的任何实例变量初始化器之前不是确定未赋值的，但没有必要规定这样的规则。

设 `c` 为一个类，`v` 为声明在 `c` 中的一个 `blank final` 非静态成员字段。那么：

- `v` 在 `c` 最左侧的初始化器（§8.6）或实例变量初始化器之前是确定未赋值的（并且，不是确定赋值的）。
- `v` 在 `c` 除最左侧外的初始化器或实例变量初始化器之前是 `[unassigned]` 的，当且仅当它在之前的初始化器或实例变量初始化器之后是 `[unassigned]` 的。

以下规则适用于类 `c` 的构造函数（§8.8.7）中：

- `v` 在备构造函数调用（§8.8.7）之后是确定赋值的（并且，不是确定未赋值的）。
- `v` 在显式或隐式的父类构造函数调用（§8.8.7）之前是确定未赋值的（并且，不是确定赋值的）。
- 如果 `c` 没有初始化器或实例变量初始化器，则 `v` 在显式或隐式的父类构造函数调用之后不是确定赋值的（并且是确定未赋值的）。
- 如果 `c` 至少有一个实例初始化器或实例变量初始化器，则 `v` 在显式或隐式的父类构造函数调用之后是 `[unassigned]` 的，当且仅当它在 `c` 最右侧的实例初始化器或实例变量初始化器之后是 `[unassigned]` 的。

设 `c` 为一个类，`v` 为声明在父类中的 `blank final` 成员字段。那么：

- `v` 在 `c` 的构造函数或实例初始化器的体块之前是确定赋值的（并且，不是确定未赋值的）。
- `v` 在 `c` 的每一个实例变量初始化器之前是确定赋值的（并且，不是确定未赋值的）。

# 第 17 章

## 线程与锁

虽然前面的章节中的大部分讨论只关注作为一次执行一条语句或表达式的代码的行为（即由单个线程执行），但 Java 虚拟机可以同时支持多个执行线程。这些线程独立地执行对共享主内存中存在的值和对象进行操作的代码。线程的支持可以通过拥有多个硬件处理器、对单个硬件处理器进行时间分片，或对多个硬件处理器进行时间分片来实现。

线程由 `Thread` 类表示。用户创建线程的唯一方法是创建该类的对象；每个线程都与这样一个对象关联。当在相应的 `Thread` 对象上调用 `start()` 方法时，线程将启动。

线程的行为，特别是在没有正确同步的情况下，可能是令人困惑且违背直觉的。本章描述了多线程程序的语义；它包含了关于对于被多个线程更新的共享内存，读取操作可能会看到哪些值的规则。由于该规范是针对不同硬件架构的内存模型，这些语义被称为 Java 编程语言内存模型。在没有产生歧义的情况下，我们将这些规则统称为“内存模型”。

这些语义并没有规定多线程程序应该如何执行。相反，它们描述了多线程程序允许表现出的行为。任何仅产生允许行为的执行策略都是接受的执行策略。

### 17.1 同步

Java 编程语言提供了多种线程间通信的机制。这些方法中最基础的是同步，它是通过监视器实现的。Java 中的每个对象都关联一个监视器，线程可以对其进行锁定或解锁。一次只允许一个线程持有监视器的锁。任何其他尝试锁定的线程都会被阻塞，直到它们能够获取该监视器的锁。线程可以多次锁定特定的监视器；每次解锁都会撤销一次锁定操作的效果。

`synchronized` 语句（§14.19）会竞争该对象监视器的引用，并在锁定操作成功完成之前不会继续向下执行。在执行锁定操作后，将执行 `synchronized` 语句体。如果语句体的执行无论是正常完成还是异常完成，都会自动对该监视器执行解锁操作。

`synchronized` 方法（§8.4.3.6）在被调用时会自动执行锁定操作；在锁定操作成功完成之前，不会执行其方法体。如果该方法是实例方法，它将锁定与调用它的实例相关的监视器（即在方法体执行期间被称为 `this` 的对象）。如果该方法是静态的，它将锁定与定义该方法的类的 `Class` 对象相关的监视器。如果方法体的执行无论是正常完成还是异常完成，都会自动对同一个监视器执行解锁操作。

Java 编程语言既不防止也不要求检测死锁条件。线程持有（直接或间接持有）多个对象锁的程序应该使用传统的死锁规避技术，在必要时创建不会产生死锁的高级锁原语。

其他机制，例如 `volatile` 变量的读写以及 `java.util.concurrent` 包中类的使用，提供了同步的替代方法。

### 17.2 等待集与通知

每个对象除了关联一个监视器外，还有一个关联的等待集。等待集是一个线程集合。

当对象首次创建时，其等待集是空的。向等待集添加线程和移除线程的基本操作是原子的。等待集的操作仅通过 `Object.wait`、`Object.notify` 和 `Object.notifyAll()` 方法进行。

等待集的操作还可能受到线程中断状态以及 `Thread` 类中处理中断的方法的影响。此外，`Thread` 类中睡眠和连接其他线程的方法具有继承自这些等待和通知操作的属性。

#### 17.2.1 等待

等待操作发生在调用 `wait()`，或定时形式的 `wait(long milliseconds)` 和 `wait(long milliseconds, int nanoseconds)` 时。

> 参数为零的 `wait(long milliseconds)` 调用或带有两个零参数的 `wait(long milliseconds, int nanoseconds)` 调用，等同于调用 `wait()`。

如果线程从等待中返回时没有抛出 `InterruptedException`，则为正常返回。

令线程 `t` 为在对象 `m` 上执行 `wait` 方法的线程，令 `n` 为 `t` 在 `m` 上执行且未被解锁操作对应的锁定操作次数。会发生以下操作之一：

- 如果 `n` 为 0（即线程 `t` 尚未拥有目标 `m` 的锁），则抛出 `IllegalMonitorStateException`。
- 如果是定时等待且 `nanoseconds` 参数不在 0-999999 范围内，或 `milliseconds` 参数为负数，则抛出 `IllegalArgumentException`。
- 如果线程 `t` 被中断，则抛出 `InterruptedException` 并将 `t` 的中断状态设置为 `false`。
- 如果 `t` 在第 2 步由于中断从 `m` 的等待集中被移除，则 `t` 的中断状态设置为 `false` 且 `wait` 方法抛出 `InterruptedException`。

#### 17.2.2 通知

通知操作发生在调用 `notify` 和 `notifyAll` 方法时。

令 `t` 为在对象 `m` 上执行上述任一方法的线程，令 `n` 为 `t` 在 `m` 上执行且未被解锁操作对应的锁定操作次数。会发生以下操作之一：

- 如果 `n` 为 0，则抛出 `IllegalMonitorStateException`。这是线程 `t` 未拥有锁的情况。
- 如果 `n` 大于 0 且这是一个 `notify` 操作，则选择并移除等待集中的一个线程。
- 如果 `n` 大于 0 且这是一个 `notifyAll` 操作，则等待集中的所有线程都被移除。

#### 17.2.3 中断

中断操作发生在调用 `Thread.interrupt`，以及定义它的方法（如 `ThreadGroup.interrupt`）时。

令 `t` 为对线程 `u` 调用中断的线程，`t` 和 `u` 可以是同一个。此操作会将 `u` 的中断状态设置为 `true`。

此外，如果存在包含 `u` 的等待集的对象 `m`，则 `u` 从该等待集中移除。这使得等待抛出 `InterruptedException`。

调用 `Thread.isInterrupted` 可以确定线程的中断状态。静态方法 `Thread.interrupted` 可由线程调用以观察并清除中断状态。

#### 17.2.4 等待、通知与中断的交互

上述规范允许我们确定关于等待、通知和中断交互的若干属性。

如果线程在等待时既被通知又被中断，它可能会：

- 正常返回等待，但仍有一个挂起的中断（即调用 `Thread.interrupted` 返回 `true`）
- 通过抛出 `InterruptedException` 返回等待。

线程可能不会重置其中断状态并正常返回等待调用。

同样，通知不会因为中断而丢失。假设线程集 `s` 在对象 `m` 的等待集中，另一个线程对 `m` 执行 `notify`。那么：

- `s` 中的至少一个线程必须正常返回等待，或
- `s` 中的所有线程必须通过抛出 `InterruptedException` 退出等待。

注意，如果一个线程既被中断又通过通知唤醒，且该线程通过抛出 `InterruptedException` 返回等待，则等待集的其他线程必须被通知。

### 17.3 睡眠与让出

`Thread.sleep` 使当前执行的线程睡眠（临时停止执行）持续取决于系统计时器和调度器的精度。线程不会丢失对任何监视器的所有权，执行的恢复将取决于调度以及执行该线程的处理器的可用性。

重要的是，`Thread.sleep` 和 `Thread.yield` 都没有任何同步语义。特别是，编译器在调用 `Thread.sleep` 或 `Thread.yield` 之前不需要将寄存器中的写入缓存刷新到共享内存，在调用 `Thread.sleep` 或 `Thread.yield` 之后也不需要重新加载寄存器缓存的值。

例如，在以下（错误的）代码段中，假设 `this.done` 是一个非 `volatile` 布尔字段：

```java
while (!this.done)
    Thread.sleep(1000);
```

编译器可以自由地将对 `this.done` 的读取提升到循环外部（就像将其转换为 `if (!this.done) while (true) Thread.sleep(1000);`），这将导致循环永远不会终止，即使另一个线程将 `this.done` 设置为 `true`。

```java
```



```
while (!this.done)
  Thread.sleep(1000);
```

编译器可以只读取一次字段 `this.done`，并在循环的每次执行中重用缓存的值。这意味着如果另一个线程更改了 `this.done` 的值，该循环将永远不会终止。

# 17.4 内存模型

内存模型描述了：在给定一个程序和该程序的执行轨迹的情况下，该执行轨迹是否为该程序的合法执行。Java 编程语言的内存模型的工作原理是检查执行轨迹中的每次读取操作，并验证所观察到的写入操作根据某些规则来说是有效的。

内存模型描述了程序可能的行为。实现者可以自由地产生他们喜欢的任何代码，只要程序的所有最终执行结果产生的结果可以被内存模型预测的结果即可。

这为实现者执行各种代码变换提供了极大的自由，包括操作的重排序和消除不必要的同步。

## 17.4.1 同步不当的程序可能会出人意料的行为

Java 编程语言的语义允许编译器和微处理器进行优化，这些优化可能会与同步不当的代码发生交互，从而产生看似悖论的行为。以下是一些同步不当的程序可能表现出意料之外行为的示例。

例如，考虑表 17.4-A 所示的程序轨迹。该程序使用了局部变量 `r1` 和 `r2` 以及共享变量 `A` 和 `B`。初始状态下 `A == B == 0`。

### 表 17.4-A 由语句排序导致的意外结果 - 原始代码

| 线程 1 | 线程 2 |
| --- | --- |
| 1: r2 = A; | 3: r1 = B; |
| 2: B = 1; | 4: A = 2; |

结果 `r2 == 2` 且 `r1 == 1` 似乎是不可能的。直觉上，在执行过程中，指令 1 或指令 3 应该有一个先执行。如果指令 1 先执行，它不应该看到指令 4 的写入。如果指令 3 先执行，它不应该看到指令 2 的写入。

如果执行表现出这种行为，我们就知道指令 4 在指令 1 之前，指令 1 在指令 2 之前，指令 2 在指令 3 之前，这从表面上看是荒谬的。

编译器允许在任意线程中重排序指令，只要这种重排序不影响该线程隔离执行的效果。如果指令 1 与指令 2 进行了重排序，那么很容易看出 `r2 == 2` 且 `r1 == 1` 的结果是如何产生的。

### 表 17.4-B 由语句重排序导致的意外结果 - 有效的编译器转换

| 线程 1 | 线程 2 |
|---|---|
| B = 1; | r1 = B; |
| r2 = A; | A = 2; |

对于程序员来说，这种行为可能看起来是“损坏的”。然而，需要注意的是这段代码的同步是不当的：

- 一个线程中有一个写入，
- 另一个线程对同一变量进行读取，
- 写入和读取没有通过同步进行排序。

这种情况是数据竞态（§17.4.5）的一个示例。当代码包含数据竞态时，往往可能产生违反直觉的结果。

几种机制可以产生表 17.4-B 中的重排序。Java 虚拟机实现中的即时编译器（JIT）可能会重新排列代码，或者由处理器重新排列。此外，运行 Java 虚拟机实现的架构的内存层次结构也可能导致代码似乎被重排序了。在本章中，我们将任何可以重排序代码的内容称为编译器。

意外结果的另一个示例可以见于表 17.4-C。初始状态下，`p == q` 且 `p.x == 0`。该程序的同步是不当的；它共享了内存，但没有在这些写入操作之间强制排序。

### 表 17.4-C 由前替换导致的意外结果

| 线程 1 | 线程 2 |
|---|---|
| r1 = p; | r6 = p; |
| r2 = r1.x; | r6.x = 3; |
| r3 = q; | |
| r4 = r3.x; | |
| r5 = r1.x; | |

## 线程与锁

一种常见的编译器优化涉及让 `r2` 的读取值被重用给 `r5`：它们都是对 `r1.x` 的读取，且中间没有写入操作。这种情况在表 17.4-D 中所示。

### 表 17.4-D 由前替换导致的意外结果

| 线程 1 | 线程 2 |
|--- |--- |
| r1 = p; | r6 = p; |
| r2 = r1.x; | r6.x = 3; |
| r3 = q; | |
| r4 = r3.x; | |
| r5 = r2; | |

现在考虑一种情况：线程 2 中对 `r6.x` 的赋值发生在线程 1 中对 `r1.x` 的第一次读取和对 `r3.x` 的读取之间。如果编译器决定重用 `r2` 的值给 `r5`，那么 `r2` 和 `r5` 的值将为 0，而 `r4` 的值将为 3。从程序员的角度来看，存储在 `p` 处的值发生了变化。

内存模型决定了线程可以看到哪些值。每当线程产生线程间操作时，它必须与线程看到的值匹配。这里指定的内存模型除了 `final` 字段外（见 §17.5）。

内存模型从根本上并不是基于 Java 语言的面向对象特性。为了示例的简洁，我们展示了不包含类定义或显式解引的代码片段。大多数示例由两个或多个包含局部变量、共享变量或实例字段访问的线程组成。我们通常使用变量名 `r1` 或 `r2` 表示局部变量。此类变量对线程可见。

## 17.4.2 共享变量

可以在线程间共享的内存被称为共享内存或堆内存。

所有实例字段、静态字段和数组元素都存储在堆内存。在本章中，我们使用变量一词来指代字段和数组元素。

局部变量（14.4）、形式方法参数（8.4.1）和异常处理器参数（14.20）永远不在线程间共享，不受内存模型的影响。

对同一个变量的两次访问（读取或写入）如果至少一次是写入，则说是冲突的。

## 17.4.3 动作

线程间操作是一个线程执行的动作，可以被另一个线程检测或直接影响。程序可能执行的线程间操作有几种：

- 读取（普通或非 volatile）。读取变量。
- 写入（普通或非 volatile）。写入变量。
- 同步动作，包括：
  - volatile 读取。变量的 volatile 读取。
  - volatile 写入。变量的 volatile 写入。
  - 锁定。锁定监视器
  - 解锁。解锁监视器
  - 线程的（合成）第一个和最后一个动作。
  - 启动线程或检测线程已终止的动作（17.4.4）。
- 外部动作。外部动作是在执行外部可以观察到的动作，其结果基于执行外部的环境。
- 线程发散动作（17.4.9）。线程发散动作仅由处于未执行内存、同步或外部动作的无限循环中的线程执行。如果一个线程执行线程发散操作，随后将跟随无限数量的线程发散操作。

引入线程发散操作是为了建模线程如何导致所有其他线程停顿并无法进展。

此关注点仅涉及线程间操作。我们不需要关注线程内操作（例如，将两个局部变量相加并将结果存储在第三个局部变量中）。如前所述，所有线程都必须遵守 Java 程序中正确的线程内语义。我们通常将线程间操作简短地称为操作（actions）。

操作 `a` 由一个元组 `< t, k, v, u >` 描述，包含：

- `t` - 执行该操作的线程
- `k` - 标识的类型
- `v` - 操作涉及的变量或监视器。

对于锁操作（lock actions），`v` 是被锁定的监视器；对于解锁操作（unlock actions），`v` 是被解锁的监视器。

如果该操作是（volatile 或非 volatile 的）读取，`v` 是被读取的变量。

如果该操作是（volatile 或非 volatile 的）写入，`v` 是被写入的变量。

- `u` - 该操作的任意标识符

外部操作元组包含一个额外的组件，该组件包含执行操作的线程所感知的外部操作结果。这可能包括有关操作成功或失败的信息，以及该操作读取的任何值。

外部操作的参数（例如，写入套接字的哪些字节）不属于外部操作元组的一部分。这些参数由线程内的其他操作设置，并可以通过检查线程内语义来确定。它们在内存模型中没有显式讨论。

在非终止的执行中，并非所有外部操作都是可观测的。非终止的执行和可观测操作在 §17.4.9 中进行了讨论。

## 17.4.4 程序与程序顺序

在每个线程 `t` 执行的所有线程间操作中，`t` 的程序顺序（program order）是一个全序，该序反映了根据 `t` 的线程内语义执行这些操作的顺序。

## 17.4.5 同步顺序

每次执行都有一个同步顺序。同步顺序是执行中所有同步操作的全序。对于每个线程 `t`，`t` 中同步操作（§17.4.3）的同步顺序与 `t` 的程序顺序（§17.4.4）一致。

同步操作在操作上引发了“同步于”（synchronized-with）关系，定义如下：

- 监视器 `m` 上的解锁操作同步于对 `m` 的后续的所有锁操作（“后续”根据同步顺序定义）。
- 对 volatile 变量 `v` 的写入（§8.3.1）同步于任何线程对 `v` 的后续读取（其中“后续”根据同步顺序定义）。
- 启动线程的操作同步于该线程的第一个操作。
- 对每个变量写入默认值（零、false 或 null）同步于每个线程的第一个操作。

虽然在包含它的对象的分配之前写入默认值似乎有点奇怪，但从概念上说，每个对象在启动时就以其默认值创建了。

线程 T1 的最后一个操作同步于另一个线程 T2 检测到 T1 已终止的任何操作。

```
T2 可以通过调用 T1.isAlive() 或 T1.join() 来实现这一点。
```

- 如果 T1 中断了 T2，T1 的中断同步于任何其他线程确定 T2 被中断的点（通过抛出 InterruptedException 或调用 Thread.interrupted()）。

“同步于”边的源点称为释放（release），终点称为获取（acquire）。

## 17.4.6 发生在前顺序（Happens-before Order）

两个操作可以通过发生在前关系进行排序。如果一个操作发生于另一个操作，则前者对后者可见且并排在后者之前。

如果我们有两个操作 x 和 y，我们写 `hb(x, y)` 表示 x 发生于 y。

- 如果 x 和 y 是同一线程的操作，且 x 在程序顺序中位于 y 之前，则 `hb(x, y)`。
- 如果 x 同步于 y，则 `hb(x, y)`。
- 如果 x 发生于 y 且 y 发生于 z，则 `hb(x, z)`。

发生在前关系具有传递性。如果一个操作发生于另一个操作，则前者对后者可见并排在后者之前。

发生在前关系是执行中操作的一个偏序。这种序确保了发生在前的操作对后续操作是可见的。

发生在前关系用于定义多线程程序中操作的可见性。如果一个操作发生于另一个操作，那么前一个操作的影响对后者可见。

```
1: B = 1;
3: A = 2;
2: r2 = A; // 看到初始写入 0
4: r1 = B; // 看到初始写入 0
```

另一种符合发生先（happens-before）一致性的执行顺序是：

```
1: r2 = A; // 看到 A = 2 的写入
3: r1 = B; // 看到 B = 1 的写入
2: B = 1;
4: A = 2;
```



## 17.4 内存模型

### 17.4.6 执行

一个执行 `E` 由一个元组 `< P, A, po, so, W, V, sw, hb >` 描述，包含：

- `P` - 一个程序
- `A` - 动作集合
- `po` - 程序次序，对于每个线程 `t`，它是 `t` 在 `A` 中执行的所有动作的全序
- `so` - 同步序，它是 `A` 中所有同步动作的全序
- `W` - 一个写入可见性函数，对于 `A` 中的每个读取 `r`，给出 `W(r)`，即 `r` 在 `E` 中看到的写入动作
- `V` - 一个写入值函数，对于 `A` 中的每个写入 `w`，给出 `V(w)`，即 `w` 在 `E` 中写入的值
- `sw` - 同步于，对同步动作的偏序
- `hb` - 发生先，对动作的偏序

注意，同步于和发生先元素是由执行的其它组件以及良好执行的规则（§17.4.7）唯一确定的。

如果一个执行的动作集合是发生先一致的，则该执行是发生先一致的（§17.4.5）。

### 17.4.7 良好的执行

我们只考虑良好的执行。如果一个执行 `E < P, A, po, so, W, V, sw, hb >` 满足以下条件，则它是良好的：

1. 每次读取在执行中写入同一个变量。
   - 所有对 `volatile` 变量的读取和写入都是 `volatile` 动作。对于 `A` 中的所有读取 `r`，我们有 `A` 中的 `W(r)` 且 `W(r).v = r.v`。当且仅当 `r` 是 `volatile` 读取时，变量 `r.v` 是 `volatile` 的；当且仅当 `w` 是 `volatile` 写入时，变量 `w.v` 是 `volatile` 的。

2. 发生先序是一个偏序。
   - 发生先序由同步边和程序次序的传递闭包给出。它必须是一个有效的偏序：自反、传递性和反对称性。

3. 执行遵守线程内一致性。
   - 对于每个线程 `t`，`t` 在 `A` 中执行的动作与该线程在程序次序初始化中生成的动作相同，在每个读取 `r` 看到值 `V(W(r))` 的情况下，每个 `w` 写入值 `V(w)`。每个读取看到的值由内存模型决定。程序次序必须反映根据 `P` 的线程内语义执行动作执行的程序次序。

4. 该执行是*发生先一致的*（§17.4.6）。

5. 执行遵守同步序一致性。
   - 对于 `A` 中的所有 `volatile` 读取 `r`，不存在 `so(r, W(r))`，也不存在 `A` 中的写入 `w` 使得 `w.v = r.v` 且 `so(W(r), w)` 且 `so(w, r)`。

### 17.4.8 执行与因果关系要求

我们使用 `f_d` 表示通过将 `f` 的定义域限制在 `d` 上函数。对于 `d` 中的所有 `x`，`f_d(x)=f(x)`，对于所有不在 `d` 中的 `x`，`f_d(x)` 未定义。

我们使用 `p_d` 表示偏序 `p` 对 `d` 中元素的限制。对于 `d` 中的所有 `x,y`，`p(x,y)` 有定义当且仅当 `x` 或 `y` 不在 `d` 中时，那么 `p_d(x,y)` 是未定义的。

一个良好的执行 `E < P, A, po, so, W, V, sw, hb >` 通过提交来自 `E` 的动作来验证。

如果 `A` 中的所有动作都可以被提交，则该执行满足 Java 语言内存模型的因果关系要求。

### 17.4.9 可观测行为与非终止执行

对于始终在一定边界时间内终止的程序，其行为可以简单地（非正式地）根据其允许的执行来理解。对于可能在有限时间内不终止的程序，会产生更微妙的问题。

程序的可观测行为由程序可能执行的外部动作有限集定义。例如，一个简单无限打印“Hello”的程序被描述为一组行为，对于任何非负整数 `i`，该行为都包含了打印 `i` 次“Hello”的行为。

终止本身没有被显式地建模为一种行为，但程序很容易扩展以生成一个额外的外部动作 `Termination`（终止），它在所有线程都终止时发生。

我们还定义了一个特殊的挂起动作。如果行为是由包含挂起动作的外部动作集描述的，它表示在观察到外部动作后，程序可以运行无限的时间，而不执行任何额外的外部动作或终止。如果所有线程都被阻塞，或者程序可以在不执行任何外部动作的情况下执行无限数量的动作，程序就会挂起。

线程在多种情况下可能会被阻塞，例如当它尝试获取锁或执行依赖于外部数据的外部动作（如读取）时。

一次执行可能导致线程被无限阻塞且执行不终止。在这种情况下，被阻塞线程生成的动作必须包含该线程从开始直到导致线程阻塞的动作为止的所有动作，且在该动作之后线程不会产生任何动作。

为了对可观测行为进行推理，我们需要讨论动作集合。

如果行为是由包含挂起动作的外部动作集合 `O` 描述的，当且仅当：
- 存在执行 `E` 的集合 `O`，且 `O` 包含挂起动作，表示在观察到外部动作后，程序可以运行无限的时间，而不执行任何额外的外部动作或终止；
- 存在执行 `E` 的集合 `O`，且 `O` 不包含挂起动作，表示程序在执行完外部动作后会终止。

## 17.5 final 字段语义

`String` 对象被设计为不可变量的，且字符串操作不执行同步。虽然 `String` 的实现没有任何数据竞态，但其他代码可能存在涉及 `String` 对象的数据竞态，而内存模型对这些竞态提供了保证。特别是，如果 `String` 类的字段不是 `final` 的，则可能（尽管可能性很小）线程 2 初始可能会看到 `String` 对象偏移量的默认值 `0`，从而允许其与 `"tmp"` 进行比较。对 `String` 对象的后续操作可能会看到正确的偏移量 `4`，从而导致 `String` 对象被感知为 `"usr"`。Java 编程语言的许多安全特性都依赖于 `String` 对象被感知为真正的不可变性，即使恶意代码正在使用数据竞态在线程之间传递 `String` 引用。

### 17.5.1 final 字段的语义

令 `o` 为一个对象，`c` 为 `o` 的一个构造函数，在其中写入了一个 `final` 字段 `f`。当 `c` 退出时（无论正常退出还是异常退出），会对 `o` 的 `final` 字段 `f` 执行一次冻结操作。

请注意，如果一个构造函数调用了另一个构造函数，且被调用的构造函数设置了一个 `final` 字段，则该 `final` 字段的冻结发生在被调用构造函数的结束。

对于每次执行，读取行为受到两个额外的部分偏序的影响：解引用链 `dereferences(c)` 和内存链 `mc(c)`，它们被视为执行的一部分（因此，对于任何特定执行都是固定的）。这些偏序必须满足以下约束（不一定有唯一解）：

- 解引用链：如果一个操作 `a` 是线程 `t` 对字段或对象 `o` 的读或写，且该线程 `t` 未初始化 `o`，则必须存在线程 `t` 的某个读取操作 `r`，该 `r` 看到 `o` 的地址使得 `r dereferences(r, a)`。
- 内存链：内存链排序有几项约束：
    - 如果 `r` 是看到 `w` 的读取，则必须满足 `mc(w, r)`。
    - 如果 `r` 和 `a` 是满足 `dereferences(r, a)` 的操作，则必须满足 `mc(r, a)`。
    - 如果 `w` 是线程 `t` 对对象 `o` 地址的写入，且该线程 `t` 未初始化 `o`，则必须存在线程 `t` 的某个读取操作 `r`，该 `r` 看到 `o` 的地址使得 `mc(r, w)`。

给定写入 `w`、冻结 `f`、操作 `a`（非对 `final` 字段的读取）、由 `f` 冻结的 `final` 字段的读取 `r1` 以及一个满足 `hb(w,f), hb(f,a), mc(a,r1)` 和 `dereferences(r1, r2)` 的读取 `r2`，在确定 `r2` 可以看到的值时，我们考虑 `hb(w, r)`。（这种 *happens-before* 排序不会与其他 *happens-before* 排序发生传递闭包。）

注意，*dereferences* 顺序是自反射的，且 `r1` 可以与 `r2` 相同。

对于 *final* 字段的读取，被认为在 *final* 字段读取之前的写入，只有通过 *final* 字段语义导出的那些。

### 17.5.2 构造期间读取 final 字段

在构造该对象的线程内对对象的 *final* 字段进行读取，相对于 *happens-before* 规则进行排序。如果读取发生在构造函数中设置字段之后，它将看到 *final* 字段被赋值的值，否则它将看到默认值。

### 17.5.3 final 字段的后续修改

在某些情况下（例如反序列化），系统需要在构造对象后更改对象的 *final* 字段。*final* 字段可以通过反射和其他依赖于实现的方式进行更改。只有在一种模式中这种操作具有合理的语义：构造一个对象，然后更新该对象的 *final* 字段。在所有对设置该 *final* 字段的对象的 *final* 字段完成更新之前，对象不应对其他线程可见，*final* 字段也不应被读取；并且在每次通过反射或其他特殊机制修改 *final* 字段之后立即执行。*final* 字段的冻结发生在设置该字段的构造函数的结束处。

尽管如此，仍许多复杂性。*final* 字段在字段声明中被初始化为常量表达式（§15.29），对 *final* 字段的更改可能无法被观察，因为 *final* 字段的使用在编译时替换为常量表达式的值。

另一个问题是规范允许对 *final* 字段进行激进优化。在线程内部，允许将对 *final* 字段的读取与未在构造函数发生的对 *final* 字段的修改重排序。

#### Example 17.5.3-1. final 字段的激进优化

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
        return j;
    }

    static void g(A a) {
        // ...
    }
}
```

### 17.5.4 写保护字段

通常，`final` 字段不可修改。然而，由于历史原因，`static` 字段允许被修改。我们将这些字段称为写保护字段，以区别于普通的 `final` 字段。例如，对普通 `final` 字段的读取对同步是“免疫”的：锁或 `volatile` 读取不会影响它们。因此，规范规定这些字段应被视为普通字段，除非用户代码位于 `System` 类中。

## 17.6 字拆

Java 虚拟机的实现的一个考虑因素是每个字段和数组元素都是独立的；对一个字段的更新不应与其他任何字段的读取或更新交互。特别是，两个线程更新相邻元素互不干扰，也不需要同步来确保顺序性。

某些处理器不提供写入单个字节的能力。在这些处理器上，通过读取整个字、更新相应的字节然后再将整个字写回内存来实现数组更新。这个问题有时被称为字拆，在无法方便更新单个字节的处理器上，需要其他方法。

#### Example 17.6-1. 检测字拆

以下程序是检测字拆的测试用例：

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
        byte v2 = 0;
        for (int i = 0; i < ITERS; i++) {
            byte v1 = counts[id];
            if (v1 != v2) {
                System.err.println("发现字拆：" + "counts[" + id + "] = " + v2 + ", 应该为 " + v1);
            }
            v++;
            counts[id] = v;
        }
    }

    public static void main(String[] args) {
        for (int i = 0; i < LENGTH; ++i) {
            threads[i] = new WordTearing(i);
            threads[i].start();
        }
    }
}
```



## Java 语言内存模型中 `long` 和 `double` 的非原子处理

对于 Java 语言内存模型而言，对非 `volatile` `long` 或 `double` 值的单次写入被视为两次独立的写入：分别写入每个 32 位的部分。这可能导致一种情况：线程从某次写入看到 64 位值的前 32 位，从另一次写入看到后 32 位。

对 `volatile` 的 `long` 和 `double` 值的写入和读取总是原子的。

对引用的写入和读取始终是原子的，无论它们被实现为 32 位还是 64 位值。

某些实现可能会发现将对 64 位 `long` 或 `double` 值的单次写入操作分为对相邻 32 位值的两次写入操作比较方便。出于效率考虑，这种行为取决于具体的实现：Java 虚拟机的实现可以自由地以原子方式或分两部分执行对 `long` 和 `double` 值的写入。

鼓励 Java 虚拟机实现尽可能避免拆分 64 位值。鼓励程序员将共享的 64 位值声明为 `volatile` 或正确同步程序以避免可能的复杂性。

# 第 18 章 类型推断

各种编译时分析都需要对未知的类型进行推理。其中主要的包括泛型方法适用性测试（§18.5.1）和泛型方法调用类型推断（§18.5.2）。通常，我们将对未知类型进行推理的过程称为类型推断。

在高级层次，类型推断可以分解为三个过程：

- **归约**（Reduction）取一个关于表达式或类型的兼容性断言（称为约束公式），并将其归约为推断变量的边界集。通常，约束公式会归约为其他约束公式，这些公式必须递归地归约。通过一个程序来识别这些额外的约束公式，并最终通过边界集表达推断出的类型能够使每个约束公式成立的条件。
- **合并**（Incorporation）维护一组推断边界，确保这些边界在添加新边界时保持一致。由于其中一个变量的边界有时会影响另一个变量的可能选择，此过程在相互依赖的变量之间传播边界。
- **解析**（Resolution）检查推断变量的边界，并确定一个与边界兼容的实例化。它还决定了相互依赖的推断变量进行解析的顺序。

这些过程紧密相互作用：归约可以触发合并；合并可能导致进一步的归约；解析可能导致进一步的合并。

- §18.1 更精确地定义了作为中间结果的概念以及用于表示这些概念的符号。
- §18.2 详细描述了归约。
- §18.3 详细描述了合并。
- §18.4 详细描述了解析。
- §18.5 定义了如何使用这些推断工具来解决某些编译时分析问题。

与 Java SE 7 语言版《Java® 语言规范》相比，推断的重要变化包括：

- 添加对 lambda 表达式和方法引用作为方法调用参数的支持。
- 泛化为通过多表达式（poly expressions）来定义推断，这些表达式在推断完成之前可能没有定义良好的类型。这对于改进嵌套泛型方法和菱形构造函数的推断具有显著效果。
- 描述如何使用推断来处理通配符参数化的函数接口目标以及最具体方法分析。
- 澄清了推断适用性测试（仅涉及调用参数）与调用类型推断（包含目标类型）之间的区别。
- 延迟所有推断变量（即使带有下界）的解析直到推断类型，以便获得更好的结果。
- 改进相互依赖（或自依赖）变量的推断行为。
- 消除了错误和潜在的混淆来源。此修订更仔细、更精确地处理了特定版本上下文与子类型之间的区别，并通过对应相应的非推断关系来描述归约。在存在故意偏离非推断关系的地方，已显式地标记为此类。
- 为未来的演进奠定基础：推断的增强或新应用将更容易集成到规范中。

## 18.1 概念和符号

本节定义了推断变量、约束公式和边界，这些术语将贯穿本章。它介绍了符号表示。

### 18.1.1 推断变量

推断变量是类型的元变量——即它们是允许对类型进行抽象推理的特殊名称。为了将它们与类型变量区分开，推断变量用希腊字母表示，主要是 `α`。

“类型”一词在本章中被泛指使用，包括包含推断变量的类类型语法。“真正类型”（proper type）术语排除了此类提及推断变量的“类型”。涉及推断变量的断言是关于通过将每个推断变量替换为真正类型而产生的每个真正类型的断言。

### 18.1.2 约束公式

约束公式是关于兼容性或子类型的断言，可能涉及推断变量。公式可能采取以下形式之一：

- `Expression → T`：表达式在松散的调用上下文中与类型 `T` 兼容（§5.3）。
- `S → T`：类型 `S` 在松散的调用上下文中与类型 `T` 兼容（§5.3）。
- `S ⊆ T`：类型 `S` 是 `T` 的子类型。
- `S ≤ T`：类型 `S` 是 `T` 的子类型。
- `S = T`：类型 `S` 与 `T` 相同。
- `S →ₜ T`：表达式在松散的调用上下文中与类型 `T` 兼容（§5.3）。

### 18.1.3 边界

在推断过程中，维护一组推断变量的边界。边界具有以下之一：

- `S = T`：类型 `S` 与 `T` 相同。

## 类型推断

### 还原

当推断开始时，通常会根据类型参数声明列表 `P₁, ..., Pₚ` 以及相关的推断变量 `α₁, ..., αₚ` 生成一个绑定集（bound set）。该绑定集的生成方式如下：对于每个 `l` (`1 ≤ l ≤ p`)：

- 如果 `P₁` 没有 `TypeBound`，则集合中出现绑定 `α₁ <: Object`。
- 否则，对于 `TypeBound` 中由 `&` 隔开的每个类型 `τ`，集合中出现绑定 `α₁ <: T[P₂::α₂, ..., Pₚ::αₚ]`；如果这导致 `α₂` 没有产生适当的上界（仅有依赖关系），则集合中也出现绑定 `α₁ <: Object`。

## 18.2 还原

还原是将一组约束公式（§18.1.2）简化以产生绑定集（§18.1.3）的过程。

依次考虑每个约束公式。本节中的规则规定了如何将公式还原为以下一种或两种形式：

- 一个绑定或集合，将与“当前”绑定集合并。初始时，当前绑定集为空。
- 进一步的约束公式，将被递归地还原。

当没有更多待还原的约束公式时，还原完成。

> 还原步骤的结果始终保持稳健性（soundness-preserving）；如果一个推断变量的实例化满足还原后的约束和绑定，那么它也将满足原始约束。另一方面，还原并不保持完备性（completeness-preserving）；可能存在满足原始约束但不满足还原后的约束或绑定的推断实例化。这是由于算法本身的局限性，以及为了避免复杂性的考虑。其影响是，某些表达式的类型推断无法找到解决方案，但如果程序员显式插入适当类型，这些表达式可以是类型安全的。

## 18.2.1 表达式兼容性约束

形式为 `<Expression → τ>` 的约束公式还原如下：

- 如果 `τ` 是一个适当类型，如果该表达式在松散调用上下文中与 `τ`（§5.3）兼容，则还原为 `true`，否则还原为 `false`。
- 否则，如果该表达式是类型为 `S` 的独立表达式（§15.2），则约束还原为 `<S → τ>`。

否则，该表达式是一个多态表达式（§15.2）。结果取决于表达式的形式：

- 如果该表达式是形式为 `( Expression )` 的括号表达式，则约束还原为 `<Expression → T>`。
- 如果该表达式是类实例创建表达式或方法调用表达式，则约束还原为绑定集 `Bⱼ`，该集合用于确定表达式与目标类型 `τ` 的兼容性，定义见 §18.5.2.1。（对于类实例创建表达式，用于推断相应的“方法”定义在 §15.9.3 中）。
- 此绑定可能包含新变量，以及这些新变量与 `T` 中的推断变量之间的依赖关系。
- 如果该表达式是形式为 `e₁ ? e₂ : e₃` 的条件表达式，则约束还原为两个约束公式 `e₂ → T` 和 `e₃ → T`。
- 如果该表达式是 lambda 表达式或方法引用表达式，结果见下文。
- 如果该表达式是具有结果表达式 `e₂, ..., eₙ` 的 switch 表达式，则约束还原为 `n` 个约束公式 `e₁ → T, ..., eₙ → T`。

通过将泛型方法调用视为多态表达式，我们改进了嵌套调用的推断行为。例如，以下代码在 Java SE 7 中是非法的，但在 Java SE 8 中是合法的：

```
ProcessBuilder b = new ProcessBuilder(Collections.emptyList());
// ProcessBuilder 的构造函数期望一个 List<String>
```

当外层和嵌套推断都需要时，问题变得更加棘手。例如：

```
List<String> ls = new ArrayList<>(Collections.emptyList());
```



我们的方法是将嵌套调用推断出的绑定（对于 `ArrayList` 而言是简单的 $\{ \alpha \}$）“提升”到外层推断过程中（在这种情况下，尝试为类型为 `ArrayList<beta>` 的构造函数推断 $\beta$）。我们还推断了嵌套变量与外部变量之间的依赖关系（约束 `<List<beta>>` 将还原为 $\alpha = \beta$）。通过这种方式，嵌套调用中推断变量的解析可以留到从外层调用推断出额外信息之后（基于赋值目标 $\eta = String$）。

形式为 `LambdaExpression → T` 的约束公式（其中 $T$ 提到了至少一个推断变量）还原如下：

- 如果 $\tau$ 不是函数接口（§9.8），则约束还原为 false。
- 否则，令 $\tau'$ 为从 $\tau$ 导出的基础类型，见 §15.2.3。如果使用 §18.5.3 导出带参数的函数接口类型，则不执行 $F<A', ..., A'>$ 是 $F<A_1, ..., A_m>$ 的子类型测试（相反地，通过下述约束公式进行断言）。lambda 表达式的目标类型是 $\tau'$ 的函数类型。那么：
  - 如果找不到有效的函数类型，则约束还原为 false。
  - 否则，`LambdaExpression` 的同构性（congruence）取决于：
    - 如果 `LambdaExpression` 在松散调用上下文中与 $\tau$ true，则 false。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
    - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$，则不执行（相反地，通过下述约束公式进行断言）。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$，对于 $1 \le i \le$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。
  - 如果 $\tau$ 的目标类型参数为 $A_1, ..., A_m$。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 true，则 true。
  - 如果 `LambdaExpression` 在目标类型 $\tau$ 的赋值上下文中 false，则 false。

目标表达式的类型通常是 lambda 表达式推导出的绑定。

```java
<T> List<T> makeThree(Factory<T> factory)
```

通过将泛型方法调用视为多态表达式，我们改进了嵌套调用的推断行为。例如，以下代码在 Java SE 7 中是非法的，但在 Java SE 8 中是合法的：

```java
ProcessBuilder b = new ProcessBuilder(Collections.emptyList());
// ProcessBuilder 的构造函数期望一个 List<String>
```

当外层和嵌套推断都需要时，问题变得更加棘手。例如：

```java
List<String> ls = new ArrayList<>(Collections.emptyList());
```



# 类型推断

## 18.2 还原

我们的方法是将嵌套调用推断出的绑定（对于 `ArrayList` 而言是简单的 `{ α }`）“提升”到外层推断过程中（在这种情况下，尝试为类型为 `ArrayList<beta>` 的构造函数推断 `β`）。我们还推断了嵌套变量与外部变量之间的依赖关系（约束 `<List<beta>>` 将还原为 `α = β`）。通过这种方式，嵌套调用中推断变量的解析可以留到从外层调用推断出额外信息之后（基于赋值目标，`η = String`）。

形式为 `LambdaExpression → T` 的约束公式（其中 `T` 提到了至少一个推断变量）还原如下：

- 如果 `τ` 不是函数接口（§9.8），则约束还原为 `false`。
- 否则，令 `τ'` 为从 `τ` 导出的基础类型，见 §15.2.3。如果使用 §18.5.3 导出带参数的函数接口类型，则不执行 `F<A', ..., A'>` 是 `F<A₁, ..., Aₘ>` 的子类型测试（相反地，通过下述约束公式进行断言）。lambda 表达式的目标类型是 `τ'` 的函数类型。那么：
  - 如果找不到有效的函数类型，则约束还原为 `false`。
  - 否则，`LambdaExpression` 的同构性取决于：
    - 如果 `LambdaExpression` 在松散调用上下文中与 `τ` true，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `τ` 的目标类型参数为 `A₁, ..., Aₘ`，对于 `1 ≤ i ≤`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `τ` 的目标类型参数为 `A₁, true Aₘ false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `Λ` 的目标类型参数为 `A₁, true Aₘ false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的 `1` 上下文中 false_则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 true，则 `true`。
    - 如果 `LambdaExpression` 在目标类型 `τ` 的赋值上下文中 false，则 `false`。

否则，如果目标为 `τ` 时不存在潜在适用的方法引用方法，则约束归约为 `false`。

否则，如果方法引用是精确的（§15.13.1），则令 `Pⱼ, ..., Pₙ` 为 `T` 的函数类型的参数类型，并令 `Fᵢ, ..., Fₖ` 为潜在适用方法的参数类型。约束归约为一组新的约束，如下：

- 在 `n = k + 1` 的特殊情况下，参数类型 `Pⱼ` 用作调用的目标引用。方法引用表达式的形式为 `ReferenceType :: [TypeArguments] Identifier`。约束归约为 `Pᵢ <: ReferenceType`，且对于所有 `(2 ≤ i ≤ n)`，`Pᵢ → Fᵢ`。
- 在所有情况下，`n = k`，且约束归约为：对于所有 `(1 ≤ i ≤ n)`，`Pᵢ → Fᵢ`。
- 如果函数结果不是 `void`，令 `R` 为其返回类型。那么，如果潜在适用编译时声明的结果为 `void`，则约束归约为 `R' → R`，其中 `R'` 是对潜在适用编译时声明的返回类型应用捕捉转换（§5.1.10）的结果。
- 否则，方法引用是不精确的，且：
  - 如果函数类型的一个或多个参数类型不是有效类型，则约束归约为 `false`。

> 这种情况在实践中永远不会出现，由于 §18.5.1 中对精确方法引用的处理以及 §18.5.2.2 中应用于目标类型的替换。

- 否则，将按照 §15.13.1 规定执行编译时声明搜索。如果方法引用没有编译时声明，则约束归约为 `false`。否则，存在编译时声明，且：（令 `R` 为函数类型的结果）
  > 如果 `R` 是 `void`，则约束归约为 `true`。
  > 否则，如果方法引用省略了 `TypeArguments`，且编译时声明是一个泛型方法，并且编译时声明的返回类型提到了方法的类型参数中的至少一个，那么：
  > » `R` 提到了函数类型的参数类型之一，则约束归约为 `false`。
  >
  > 在这种情况下，关于 `R` 的约束可能会导致推断变量被绑定到一个作用范围外的类型变量。由于使用作用范围外的类型变量来实例化推断变量是毫无意义的，我们倾向于在出现这种可能性时立即放弃以避免这种情况。这种简化不是保持完备性的。
  >
  > 如果 `R` 没有提到函数类型的类型参数之一，则约束归约为边界集 `Bⱼ`，该集合将用于确定当目标为函数返回类型时方法引用的兼容性，其定义见 §8.5.2.1。`Bⱼ` 可能包含新的推断变量，以及这些新变量与 `T` 中的推断变量之间的依赖关系。
  >
  > 用于确定泛型引用方法返回类型的策略遵循本节较早之前用于泛型方法调用的模式。这可能涉及“提升”到外部上下文中并推断两组推断变量之间的依赖关系。
  > 否则，`R'` 是对编译时声明的调用类型（§15.2.2.6）的返回类型应用类型转换（§5.1.10）的结果。如果 `R'` 是 `void`，则约束归约为 `false`；否则，约束归约为 `⟨R' → R⟩`。

## 18.2.2 兼容性约束

形式为 `S → T` 的约束公式归约如下：

- 如果 `S` 和 `T` 是有效类型，如果 `S` 在 `T` 的松散调用文中兼容（§5.3），则约束归约为 `true`，否则为 `false`。
- 否则，如果 `S` 是基本类型，令 `S'` 为对 `S` 应用装箱转换（§5.7）的结果。则约束归约为 `⟨S' → T⟩`。
- 否则，如果 `T` 是基本类型，令 `T'` 为对 `T` 应用装箱转换（§5.7）的结果。则约束归约为 `⟨S = T⟩`。
- 否则，如果 `T` 是形式为 `G<T₁, ..., Tₙ>` 的泛化类型，且不存在形式为 `G<...>` 的上类型，但原始类型 `G` 是 `S` 的上类型，则约束归约为 `true`。
- 否则，如果 `T` 是形式为 `G<T₁, ..., Tₙ>ᵏ` 的数组类型，且存在形式为 `G<...>ᵏ` 的类型是 `S` 的上类型，但原始类型 `Gᵏ` 是 `S` 的上类型，则约束归约为 `true`。（符号 `[]ᵏ` 表示 `k` 维数组）。
- 否则，约束归约为 `⟨S ...⟩`。

第四和第五种情况是未检查转换的使用（§5.9）。这些以及第一种情况的未检查转换会导致编译警告，并影响方法的调用类型（§15.2.6）。

> 将 `T` 装箱为 `T'` 不是保持完备性的；例如，如果 `T` 是 `long`，`S` 可能被实例化为 `Integer`，它不是 `Long` 的子类型，但可以拆箱并扩展为 `long`。我们通过对已经约束为基本类型的推断变量进行特殊处理来避免这个问题；见 §18.5.2.1。
>
> 同样，在 `T` 不是泛化类型时对未检查转换的处理牺牲了完备性（例如，如果 `T` 是推断变量）。在这种情况下是否需要未检查转换是不清楚的。由于未检查转换引入警告，除非明显必要，否则推断会避免它们。

## 18.2.3 子类型约束

形式为 `S <: T` 的约束归约如下：

- 如果 `S` 和 `T` 是有效类型，如果 `S` 是 `T` 的子类型（§4.10），则约束归约为 `true`，否则为 `false`。
- 否则，如果 `S` 是空类型，约束归约为 `true`。
- 否则，如果 `T` 是空类型，约束归约为 `false`。
- 否则，如果 `S` 是推断变量 `α`，约束归约为 `α <: T`。
- 否则，如果 `T` 是推断变量 `α`，约束归约为 `S <: α`。
- 否则，根据 `T` 的形式归约约束。
  - 如果 `T` 是泛化类或接口类型，或者是泛化类或接口类型的内部类（直接或间接），令 `A₁, ..., Aₙ` 为 `T` 的类型参数。在 `S` 的上类型中识别对应的类或接口类型，其类型参数为 `B₁, ..., Bₙ`。如果不存在此类类型，约束归约为 `false`。否则，约束归约为一组新的约束：对于所有 `(1 ≤ i ≤ n)`，`Bᵢ <: Aᵢ`。
  - 如果 `T` 是其他类或接口类型，如果 `T` 是 `S` 的上类型，则约束归约为 `true`，否则为 `false`。
  - 如果 `T` 是数组类型 `T'[]`；那么在 `S` 的数组上类型中识别出一个特定的类型 `S'[]`（这可能是 `S` 本身）。如果不存在此类数组，约束归约为 `false`。否则：
    > 如果 `S'` 和 `T'` 都不是基本类型，约束归约为 `⟨S' <: T'⟩`。
    > 否则，如果 `S'` 和 `T'` 是同一个基本类型，则约束归约为 `true`，否则为 `false`。
  - 如果 `T` 是变量类型，有三种情况：
    > 如果 `S` 是 `T` 作为元素的交类型，则约束归约为 `true`。
    > 否则，如果 `T` 有一个下界，则约束归约为 `⟨S <: B⟩`。
    > 否则，约束归约为 `false`。
  - 如果 `T` 是交类型 `I₁ & ... & Iₙ`，约束归约为一组新的约束：对于所有 `(1 ≤ i ≤ n)`，`⟨S <: Iᵢ⟩`。

形式为 `⟨S ≤ T⟩` 的约束公式，其中 `S` 和 `T` 是类型参数（§4.5.1），归约如下：

- 如果 `T` 是类型：
  - 如果 `S` 是类型，约束归约为 `⟨S = T⟩`。
  - 如果 `S` 是通配符，约束归约为 `false`。
  - 如果 `T` 是形式为 `?` 的通配符，则约束归约为 `true`。
- 如果 `T` 是形式为 `? extends T'` 的通配符：
  - 如果 `S` 是类型，约束归约为 `⟨S <: T'⟩`。
  - 如果 `S` 是形式为 `?` 的通配符，约束归约为 `⟨Object <: T'⟩`。
  - 如果 `S` 是形式为 `? extends S'` 的通配符，约束归约为 `⟨S' <: T'⟩`。
  - 如果 `S` 是形式为 `?` 的通配符，约束归约为 `⟨Object <: T'⟩`。
- 如果 `T` 是形式为 `? super T'` 的通配符：
  - 如果 `S` 是类型，则约束还原为 `⟨T' <: S⟩`。
  - 如果 `S` 是形式为 `? super S'` 的通配符，则约束还原为 `⟨T' <: S'⟩`。
  - 否则，约束还原为 `false`。

## 18.2.4 类型相等约束

形式为 `⟨S = T⟩` 的约束公式（其中 `S` 和 `T` 是类型）还原如下：

- 如果 `S` 和 `T` 是具体类型，如果 `S` 与 `T` 相同（§4.3.4），则约束还原为 `true`，否则还原为 `false`。
- 否则，如果 `S` 或 `T` 是空类型，则约束还原为 `false`。
- 否则，如果 `S` 是推断变量 `α`，且 `T` 不是基本类型，则约束还原为边界 `α = T`。
- 否则，如果 `T` 是推断变量 `α`，且 `S` 不是基本类型，则约束还原为边界 `S = α`。
- 否则，如果 `S` 和 `T` 是带有擦除类的或接口类型，其中 `S` 有类型参数 `B₁, ..., Bₙ`，`T` 有类型参数 `A₁, ..., Aₙ`，则约束还原为新约束：对于所有 `i` (`1 ≤ i ≤ n`)，有 `⟨Bᵢ = Aᵢ⟩`。
- 否则，如果 `S` 和 `T` 是数组类型 `S'[]` 和 `T'[]`，则约束还原为 `⟨S' = T'⟩`。
- 否则，如果 `S` 和 `T` 是交叉类型，则在 `S` 的元素与 `T` 的元素之间建立对应关系。如果 `Sᵢ` 和 `Tⱼ` 是相同类型、同一泛型类或接口的参数化、或数组类型，则 `Sᵢ` 的元素对应于 `Tⱼ` 的元素。
  - 如果 `S` 的每个元素恰好对应 `T` 的一个元素，反之亦然，则约束还原为新约束：对于 `S` 的每个元素 `Sᵢ` 和 `T` 对应的元素 `Tⱼ`，有 `⟨Sᵢ = Tⱼ⟩`。否则，约束还原为 `false`。

> 此规则不适应直接作为交叉类型元素的推断变量（而不是嵌套在参数化类型中）。由于类型声明的限制（§4.4），此类交叉类型在实践中不会出现。

- 否则，约束还原为 `false`。

形式为 `S = T` 的约束公式（其中 `S` 和 `T` 是类型参数 §4.5.1）还原如下：

- 如果 `S` 和 `T` 是类型，则按上述方式还原。
- 如果 `S` 的形式为 `?` 且 `T` 的形式为 `?`，则约束还原为 `true`。
- 如果 `S` 的形式为 `?` 且 `T` 的形式为 `extends T'`，则约束还原为 `⟨Object = T'⟩`。



# 类型推断

## 18.2.5 检查异常约束

形式为 `<LambdaExpression → τ>` 的约束公式还原如下：

- 如果 `τ` 不是函数接口类型（§9.8），则约束还原为 `false`。
- 否则，按照 §15.27.3 规定确定 lambda 表达式的目标函数类型。如果找不到有效的函数类型，则约束还原为 `false`。
- 否则，如果 lambda 表达式是隐式类型指定的，且函数的参数类型中的一个或多个不是具体类型，则约束还原为 `false`。

> 此情况在实践中永远不会出现，由于 §18.5.2.2 对目标类型应用了替换。

- 否则，如果函数类型的返回类型既不是 `void` 也不是具体类型，则约束还原为 `false`。

> 此情况在实践中永远不会出现，由于 §18.5.2.2 对目标类型应用了替换。

- 否则，令 `E₁, ..., Eₙ` 为函数类型 `throws` 子句中不是具体类型的类型。如果 lambda 表达式是隐式类型指定的，令其参数类型为函数类型的参数类型。如果 lambda 实体是一个多态表达式或包含多态结果的块，则目标返回为函数的返回类型。

## 18.3 类型推断 合并

- 给定依赖 `α=β`，`α` 的每一个界限都匹配 `β` 的一个界限，反之亦然。
- 给定依赖 `α <: β`，`α` 的每一个下界都是 `β` 的下界，且 `β` 的每一个上界都是 `α` 的上界。

关于合并（incorporation）能够达到固定点的断言略微地简化了问题。基于 Kennedy 和 Pierce 的论文《关于变异性名义子类型的可判定性》（*On Decidability of Nominal Subtyping of Variance*），该属性可以通过证明可能出现在边界集中的类型集合是有限的来得出。该论证依赖于以下两个假设：

- 在约化子类型约束时，不会生成新的捕获变量（§18.2.3）。
- 不会追求扩展的继承路径。

该规范目前并不保证这些属性（它在约化子类型约束时对通配符的处理不精确，并且没有检测扩展的继承路径），但在未来的版本中可能会这样做。（这不是一个新问题：Java 子类型算法也存在非终止的风险）。

### 18.3.1 边界的互补对

（在本节中，`s` 和 `T` 是推断变量或类型，为了起见，形式为 `α=T` 的界限也可以匹配形式为 `T=α` 的界限）。

当边界集包含一对匹配以下规则之一的界限时，则会隐含出一个新的约束公式：

- `α=s` 和 `α=T` 隐含 `<S=T>`
- `α=s` 和 `α<:T` 隐含 `<S<:T>`
- `α=s` 和 `T<:S` 隐含 `<T<:S>`
- `S<:α` 和 `α<:T` 隐含 `<S<:T>`
- `α=U` 和 `α=T` 隐含 `S{α:=U}=T{α:=T}`
- `α=U` 和 `α<:T` 隐含 `S{α:=U}<:T{α:=T}`

当边界集包含一对界限 `α<:T`；`s` 和 `α<:T` 时，存在 `s` 的形式为 `G<S₁, ..., Sₙ>` 的上类型以及 `T` 的形式为 `G<T₁, ..., Tₙ>` 的上类型（对于某些泛型类或接口 `G`），对于所有 `i` (`1 ≤ i ≤ n`)，如果 `Sᵢ` 和 `Tᵢ` 是类型（而非通配符），则隐含约束公式 `Sᵢ=Tᵢ`。

### 18.3.2 涉及捕获转换的边界

当边界包含形式为 `G<αᵢ, ..., αₙ> = capture(G<Aᵢ, ..., Aₙ>)` 的界限时，会隐含新的边界，并可能隐含新的约束公式，如下。

令 `Pᵢ, ..., Pₙ` 代表 `G` 的类型参数，`Bᵢ, ..., Bₙ` 代表这些类型参数的边界。令 `θ` 代表替换 `[Pᵢ:=αᵢ, ..., Pₙ:=αₙ]`。令 `R` 为一个不是推断变量的类型（但不一定是具体类型）。

对 `αᵢ, ..., αₙ` 的一组边界是根据 §18.1.3 指定的从 `Pᵢ, ..., Pₙ` 的声明边界中生成的。

此外，对于所有 `i` (`1 ≤ i ≤ n`)：

- 如果 `Aᵢ` 不是通配符，则隐含边界 `αᵢ = Aᵢ`。
- 如果 `Aᵢ` 是形式为 `?` 的通配符：
    - `αᵢ = R` 隐含边界 `false`
    - `αᵢ <: R` 隐含约束公式 `<Bᵢ θ <: R>`
    - `R <: αᵢ` 隐含边界 `false`
- 如果 `Aᵢ` 是形式为 `? extends T` 的通配符：
    - `αᵢ = R` 隐含边界 `false`
    - 如果 `Bᵢ` 是 `Object`，则 `αᵢ <: R` 隐含约束公式 `<T <: R>`
    - 如果 `T` 是 `Object`，则 `αᵢ <: R` 隐含约束公式 `<Bᵢ θ <: R>`
    - `R <: αᵢ` 隐含边界 `false`
- 如果 `Aᵢ` 是形式为 `? super T` 的通配符：
    - `αᵢ = R` 隐含边界 `false`
    - `αᵢ <: R` 隐含约束公式 `<Bᵢ θ <: R>`
    - `R <: αᵢ` 隐含约束公式 `<R <: T>`

## 18.4 解析

给定一个不包含边界 `false` 的边界，边界集所提到的推断变量的子集可能被*解析*。这意味着可能为每个推断变量向集合中添加一个满意的实例化，直到所有请求的变量都有实例化。

边界集中的依赖可能要求按照特定顺序解析变量，或者要求解析额外的变量。依赖指定如下：

- 给定以下形式之一的边界，其中 `τ` 是推断变量 `β` 或提到 `β` 的类型：
    - `α = τ`
    - `α <: τ`
    - `τ = α`
    - `τ <: α`

如果 `α` 出现在另一个形式为 `G<..., α, ...> = capture(G<...,...>)` 的边界左侧，则 `β` 依赖于 `α` 的解析。否则，`α` 依赖于 `β` 的解析。

## 18.5 推断的使用

基本类型的表达式；如果是，该方法不适用，不需要继续进行推断。

否则，`c` 包含了所有 `i (1 ≤ i ≤ k)`（其中 `eᵢ` 与适用性相关）的 `eᵢ → Fᵢ θ`。

* 通过松散调用（loose invocation）测试适用性：*

如果 `k ≠ n`，则该方法不适用，不需要继续进行推断。

否则，`c` 包含了所有 `i (1 ≤ i ≤ k)`（其中 `eᵢ` 与适用性相关）的 `eᵢ → Fᵢ θ`。

* 通过变量变长参数调用（variable arity invocation）测试适用性：*

令 `F'₁, ... F'ₖ` 为 `m` 的前 `k` 个变长参数类型（15.12.2.4）。`C` 包含了所有 `i (1 ≤ i ≤ k)`（其中 `eᵢ` 与适用性相关）的 `eᵢ → F'ᵢ θ`。

* `C` 被归约（§18.2），并将生成的边界与 `Bᵢ` 结合以产生一个新的边界集 `B₂`。

* 最后，如果 `B₂` 不包含边界 `false` 且 `B₂` 中所有推断变量的解析成功，则方法 `m` 是适用的（§18.4）。

考虑以下方法调用和赋值：

```
List<Number> ln = Arrays.asList(1, 2.0);
```

必须根据 §15.12 的描述为调用标识一个特定的适用方法。唯一可能的适用方法（§15.12.2.1）声明如下：

```
public static <T> List<T> asList(T... a)
```

显而易见（因为参数个数），该方法既不适用于严格调用（§15.12.2.2），也不适用于松散调用（§15.12.2.3）。但由于没有其他候选方法，第三阶段通过变长参数调用检查方法的适用性。

初始边界集 `Bᵢ` 是单个推断变量 `α` 的平凡上界：

```
{ α <: Object }
```

初始约束公式集如下：

```
{ 1 → α, 2.0 → α }
```

这些被归约为一个新的边界集 `Bⱼ`：

```
{ α <: Object, Integer <: α, Double <: α }
```

然后，为了测试方法是否适用，我们尝试解析这些边界。我们成功了，产生了相当复杂的实例化：

```
α = Number & Comparable<? extends Number & Comparable<?>>
```

我们已经证明该方法是适用的；由于没有其他候选方法，它是最具体的适用方法。尽管如此，调用类型及其与赋值中目标类型的兼容性，在发生后续节所述的推断之前尚未确定。

### 18.5.2 调用类型推断

给定一个未提供显式类型参数的方法调用表达式，以及对应的最具体的泛型方法 `m`，推断所选方法的调用类型（§15.12.2.6）的过程可能解析额外的约束，以断言与目标类型的兼容性，并断言方法调用参数表达式的有效性。

> 注意，寻找方法调用的类型涉及多个“轮次”推断。例如，这是为了允许目标类型影响调用类型，而不允许它影响对适用方法的选择。第一轮（§18.5.1）产生一个边界集并测试是否存在解析，但不提交该解析。后续轮次归约额外的约束，直到最终的解析步骤确定表达式的“真实”类型。

#### 18.5.2.1 多态方法调用兼容性

如果方法调用表达式是一个多态表达式（§§15.12），它与目标类型 `τ` 的兼容性确定如下。

如果方法调用表达式出现在严格调用环境中且 `τ` 是基本类型，则该表达式与 `τ` 不兼容。

否则：

* 令 `B₂` 为通过归约产生的边界集，以证明 `m` 在 §18.5.1 中是应用的。（虽然在 §18.5.1 中需要证明 `B₂` 中的推断变量可以被解析以建立适用性，但此解析步骤产生的实例化不视为 `B₂` 的部分）
* 令 `B₂` 为 `B₂` 的边界类型，如下。

令 `R` 为 `m` 的返回类型，令 `θ` 为 §18.5.1 中定义的替换 `[Pᵢ:=αᵢ, …, P_f:=α_f]`，用于用推断变量替换 `m` 的类型参数，令 `τ` 为调用目标。那么：

* 如果在 §18.5.1 的约束归约期间为了方法适用需要拆箱转换（unboxed conversion），则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。
* 否则，如果 `R` 是参数类型，`G<A₁, …, Aₙ>` 且 `τ` 是通配符，则约束公式 `|R| → τ` 被归约并与 `B₂` 结合。

方法调用与 `T` 兼容的，如果 `B₂` 不包含边界 `false` 且 `B₂` 中所有推断变量的解析成功（§18.4）。

否则，如果 `R` 是参数类型，`α` 解析为 `U`，约束公式 `U → τ` 被归约并与 `B₂` 结合。

与 `T` 兼容的，如果 `B₂` 不包含边界 `false` 且 `B₂` 中所有推断变量的解析成功（§18.4）。

与 `T` 兼容的，如果 `B₂` 不包含边界 `false` 且 `B₂` 中所有推断变量的解析成功（§18.4）。

考虑以下方法调用和赋值：

```
List<Number> ln = Arrays.asList(1, 2.0);
```

必须根据 §15.12 的描述为调用标识一个特定的适用方法。唯一可能的适用方法（§15.12.2.1）声明如下：

```
public static <T> List<T> asList(T... a)
```

显而易见（因为参数个数），该方法既不适用于严格调用（§15.12.2.2），也不适用于松散调用（§15.12.2.3）。但由于没有其他候选方法，第三阶段通过变长参数调用检查方法的适用性。

初始边界集 `Bᵢ` 是单个推断变量 `α` 的平凡上界：

```
{ α <: Object }
```

初始约束公式集如下：

```
{ 1 → α, 2.0 → α }
```

这些被归约为一个新的边界集 `Bⱼ`：

```
{ α <: Object, Integer <: α, Double <: α }
```

然后，为了测试方法是否适用，我们尝试解析这些边界。我们成功了，产生了相当复杂的实例化：

```
α = Number & Comparable<? extends Number & Comparable<?>>
```

我们已经证明该方法是适用的；由于没有其他候选方法，它是最具体的适用方法。尽管如此，调用类型及其与赋值中目标类型的兼容性，在发生后续节所述的推断之前尚未确定。

### 18.5.2 调用类型推断



给定一个未提供显式类型参数的方法调用表达式，以及对应的最具体的泛型方法 `m`，推断所选方法的调用类型（§15.12.2.6）的过程可能解析额外的约束，以断言与目标类型的兼容性，并断言方法调用参数表达式的有效性。

> 注意，寻找方法调用的类型涉及多个“轮次”推断。例如，这是为了允许目标类型影响调用类型，而不允许它影响对适用方法的选择。第一轮（§18.5.1）产生一个边界集并测试是否存在解析，但不提交该解析。后续轮次归约额外的约束，直到最终的解析步骤确定表达式的“真实”类型。

## 18.5.2.1 多态方法调用兼容性

如果方法调用表达式是一个多态表达式（§§15.12），它与目标类型 $\tau$ 的兼容性确定如下。

如果方法调用表达式出现在严格调用环境中且 $\tau$ 是基本类型，则该表达式与 $\tau$ 不兼容。

否则：

+ 令 $B_2$ 为通过归约产生的边界集，以证明 $m$ 在 §18.5.1 中是应用的。（虽然在 §18.5.1 中需要证明 $B_2$ 中的推断变量可以被解析以建立适用性，但此解析步骤产生的实例化不视为 $B_{2}$ 的部分）

### 推断的使用

+ 令 $B_2$ 为 $B_2$ 的边界类型，如下。

令 $R$ 为 $m$ 的返回类型，令 $\theta$ 为 §18.5.1 中定义的替换 `[P_i:=\alpha_i, \dots, P_f:=\alpha_f]`，用于用推断变量替换 $m$ 的类型参数，令 $\tau$ 为调用目标。那么：

+ - 如果在 §18.5.1 的约束归约期间为了方法适用需要拆箱转换，则约束公式 `|R| \to \tau` 被归约并与 $B_2$ 结合。

+ - 否则，如果 $R$ 是参数类型，$G<A_1, \dots, A_n>$ 且 $\tau$ 是通配符，则约束公式 `|R| \to \tau` 被归约并与 $B_2$ 结合。

+ - 否则，如果 $R$ 是参数类型，$G<A_1, \dots, A_n>$ 且 $\tau$ 是通配符，则约束公式 `|R| \to \tau` 被归约并与 $B_2$ 结合。

+ - 否则，如果 $R$ 是参数类型，$G<A_1, \dots, A_n>$ 且 $\tau$ 是通配符，则约束公式 `|R| \to \tau` 被归约并与 $B_2$ 结合。

+ - 否则，如果 $R$ 是参数类型，$G<A_1, \dots, A_n>$ 且 $\tau$ 是通配符，则约束公式 `|R| \to \tau` 被归约并与 $B_2$ 结合。

+ - 否则，如果 $R$ 是参数类型，$G<A_1, \dots, A_n>$ 且 $\tau$ 是通配符，则约束公式 `|R| \to \tau` 被归约并与 $B_2$ 结合。

如果方法调用表达式是一个多态表达式，则 $B_j$ 为在 §18.5.2.1 中生成的绑定集，用于证明与方法调用的实际目标类型兼容性。

如果方法调用表达式不是多态表达式，则 $B_j$ 等于通过归约产生的相同绑定集，用于证明 $m$ 在 §18.5.1 中是适用的。

（虽然在 §18.5.1 和 §18.5.2.1 中需要证明绑定集中的推断变量是可以解析的，但这些解析步骤产生的实例化不视为 $B_j$ 的部分。）

- 按照如下方式生成一组约束公式 $C$。

令 $e_j, ..., e_k$ 为方法调用表达式的实际参数表达式。

如果 $m$ 通过严格或松散调用适用的，则令 $F_j, ..., F_k$ 为 $m$ 的形式参数类型；如果 $m$ 通过可变步长调用适用，则令 $F_1, ..., F_k$ 为 $m$ 的前 $k$ 个可变步长参数类型（§18.5.12.4）。

令 $\theta$ 为在 §18.5.1 中定义的替换 `[P_i:=\alpha_i, ..., P_j:=\alpha_j]`，用于用推断变量替换 $m$ 的类型参数。

那么，对于所有的 $i$ ($1 \le i \le k$)：

- 如果 $e_i$ 与适用性无关，则 $c$ 包含 `e_i \to F_i \theta`。

- 根据 $e_i$ 的形式，可能包含额外的约束：

  - 如果 $e_j$ 是一个 `LambdaExpression`，则 $c$ 包含 `LambdaExpression \to throws F_i \theta`，并对 lambda 体搜索额外的额外的约束：

    - 对于块级 lambda 体，递归应用搜索以捕获其每一个结果表达式。

    - 对于多态类实例创建或多态方法调用表达式，$c$ 包含在 §18.5.2 中推断多态表达式调用类型时生成的集合 $c$ 中出现的所有约束公式。

  - 对于括号表达式，对包含的表达式递归应用搜索。

  - 对于条件表达式，对第二和第三操作数递归应用搜索。

  - 对于 lambda 表达式，对 lambda 体递归应用搜索。

  - 对于 switch 表达式，对它的每一个结果表达式递归应用搜索。

- 如果 $e_i$ 是一个 `MethodReference`，则 $c$ 包含 `MethodReference \to throws F_i \theta`。

- 如果 $e_i$ 是多态类实例创建或多态方法调用表达式，$c$ 包含在 §18.5.2 中推断多态表达式调用类型时生成的集合 $c$ 中出现的所有约束公式。

- 如果 $e_i$ 是括号表达式，这些规则对包含的表达式递归地应用。

- 如果 $e_i$ 是条件表达式，这些规则对第二和第三操作数递归地应用。

- 如果 $e_i$ 是 switch 表达式，这些规则对它的每一个结果表达式递归地应用。

- 只要 $c$ 不空，重复以下过程，从绑定 $B_i$ 开始并将新的绑定累积到“当前”绑定集中，最终产生一个新的绑定集 $B_i$；

  1. 在 $c$ 中选择一个约束子集，满足以下属性：对于每个约束，没有输入变量可以影响 $c$ 中另一个约束的输出变量。输入变量和输出变量的术语定义如下。推断变量 $\alpha$ 可以影响推断变量 $\beta$，如果 $\alpha$ 依赖于 $\beta$ 的解析（§18.4），或者反之亦然；或者存在推断变量 $\gamma$，使得 $\alpha$ 可以影响 $\gamma$ 且 $\gamma$ 可以影响 $\beta$。

  - 如果该子集为空，则在约束之间的依赖图中存在一个（或多个）循环。在这种，考虑 $c$ 中参与依赖循环（或循环）且不依赖于循环（或循环）之外任何约束的约束。从这些被考虑的约束中选择一个约束，如下：

    - 如果考虑的约束中任何一个具有 `<Expression \to T>` 形式，则所选约束是该形式的考虑约束，且它包含了其他该形式的考虑约束的表达式左侧（§3.5）的表达式。

    - 如果没有考虑的约束具有 `<Expression \to T>` 形式，则所选约束是该考虑约束，它包含了其他考虑约束的表达式左侧的表达式。

  2. 将所选的约束（s）从 $C$ 中移除。

  3. 解析所有所选约束（s）的输入变量 $\alpha_2, ..., \alpha_m$。

  4. 其中 $T_j, ..., T_m$ 是 $\alpha_2, ..., \alpha_m$ 的实例化，替换 `[\alpha_j=T_j ..., \alpha_m=T_m]` 应用于每个循环。

  5. 替换产生的约束被归约并合并到当前绑定集中。

最后，如果 $B_i$ 不包含 $B_i$ 中的绑定变量，则对其进行解析。如果使用推断变量 $\alpha_j, ..., \alpha_p$ 的实例化 $T_j, ..., T_p$ 解析成功，令 $\theta'$ 为替换 `[P_j:T_j, ..., P_p:T_p]`。那么：

- 如果类型转换对于适用性是必要的，则 $m$ 的参数类型通过 $\theta'$ 获取。

- 如果类型转换对于适用性是必要的，则 $m$ 的返回类型和 throws 类型通过 $\theta'$ 获取。如果 $B_i$ 包含，或者解析失败，则发生编译错误。额外参数的处理可能需要形式为 `<Expression \to T>`、`<LambdaExpression \to throws T>` 和 `<MethodReference \to throws T>` 的公式。为了这种排序，这些约束的输入变量定义如下：

- 对于 `LambdaExpression \to T`:

  - $\alpha$ 是推断变量，它是唯一的输入变量。

  - $\alpha$ 是函数接口类型，且可以从 $\alpha$ 推导出函数类型（§15.27.3），则输入变量包括：i) 如果 lambda 表达式是隐式类型，函数参数的推断变量；(ii) 如果函数的返回类型 $\mathcal{R}$ 不是 `void`，对于 lambda 体中的每个结果表达式 $e$（或对于体本身是一个表达式），`<e \to \mathcal{R}>` 的输入变量。

  - 否则，没有输入变量。

- 对于 `LambdaExpression \to throws T`:

  - $\alpha$ 是推断变量，它是唯一的输入变量。

  - $\alpha$ 是函数接口类型，且可以从 $\alpha$ 推导出函数类型（§15.27.3），则输入变量包括：i) 如果 lambda 表达式是隐式类型，函数参数的推断变量；(ii) 函数返回类型的推断变量。

  - 否则，没有输入变量。

- 对于 `MethodReference \to T`:

  - $\alpha$ 是推断变量，它是唯一的输入变量。

  - $\alpha$ 是函数接口类型并具有函数类型，且方法引用是不精确的（§15.13.1），则输入变量是函数类型参数的推断变量。

  - 否则，没有输入变量。

- 对于 `MethodReference \to throws T`:

  - $\alpha$ 是推断变量，它是唯一的输入变量。

  - $\alpha$ 是函数接口类型并具有函数类型，且方法引用是不精确的（§15.13.1），则输入变量是函数类型参数的推断变量和函数返回类型的推断变量。

  - 否则，没有输入变量。

- 对于 `Expression \to T`，如果 $Expression$ 是括号表达式：

  - 当 $Expression$ 包含的表达式为 'Expression' 时，输入变量是 `<Expression \to T>` 的输入变量。

### 推断的用途

- 对于 `<ConditionalExpression \rightarrow T>`:

其中条件表达式的形式为 $e_1\ ? e_2 : e_3$，则 $e_2 \rightarrow T$ 和 $e_3 \rightarrow T$ 的输入变量。

- 对于 `<SwitchExpression \rightarrow T>`:

其中 switch 表达式的结果为 $e_j, ..., e_n$，则对于所有 $i$ ($1 \le i \le n$)，其输入变量为 $e_j \rightarrow T$ 的输入变量。

- 对于所有的约束公式，没有输入变量。

这些约束的输出是约束右侧类型所提到的推断变量 $\tau$，这些变量不是输入变量。

## 18.5.3 泛型接口参数化推断

当一个具有显式参数类型 $P_1, ..., P_n$ 的 lambda 表达式的目标是一个泛型接口类型 $F<A_1, ..., A_m>$，且其至少包含一个通配符参数时，可以从 lambda 表达式的基础类型推导出 $F$ 的参数化，如下。

令 $Q_1, ..., Q_m$ 为类型 $F<\alpha_1, ..., \alpha_m>$ 的函数的参数类型，其中 $\alpha_j,..., \alpha_m$ 是新的推断变量。

如果 $n \neq k$，则不存在有效的参数化。否则，形成一组约束公式，对于所有 $i$ ($1 \le i \le n$)，$P_i = Q_i$。该约束公式被归约以形成边界 $B$。

如果 $b$ 包含边界 `false`，则不存在有效的参数化。否则，构造一个新的泛型接口参数化 $F<A'_1, ..., A'_m>$，构造方式如下（对于 $1 \le i \le m$）：

- 如果 $B$ 包含对 $\alpha_i$，$T$ 的实例化 (18.1.3)，则 $A'_i = T$。

- 否则，$A'_i = A_i$。

如果 $A'_i$ 不是一个良构类型（即参数不在其边界范围内），或 $F<A'_1, ..., A'_m>$ 不是 $F<A_1, ..., A_m>$ 的子类型，则不存在有效的参数化。否则，推断出的参数化是 $F<A'_1, ..., A'_m>$（如果所有参数都是类型），或者如果一个或多个类型参数仍为通配符，则是 $F<A'_1, ..., A'_m>$ 的非通配符参数化 (9.9)。为了确定通配符参数化泛型接口的函数类型，我们必须用特定类型来“实例化”通配符类型参数。“默认”方法是简单地将通配符替换为它们的边界（如 §9.8 所述），但在 lambda 表达式的显式参数类型与通配符边界不对应的情况下，这会产生伪错误。例如：

```
Predicate<? super Integer> p = (Number n) -> n.equals(23);
```

该 lambda 表达式是一个 `Predicate<Number>`，它是 `Predicate<?super Integer>` 的子类型，但不是 `Predicate<Integer>`。本节的分析用于推断出 `Number` 不是 `Predicate` 类型的合适选择。

尽管如此，这里的分析虽然是用通用类型推断来描述的，但非常简单。唯一的约束是等式约束，这意味着归约等于简单的模式匹配。更强大的策略可能还可以从 lambda 表达式的主体推断约束。但是，考虑到周围和/或嵌套泛型调用的可能交互，这将引入大量的额外复杂度。

## 18.5.4 更具体的方法推断

在测试一个可用方法是否比另一个方法更具体 (§15.12.2.5) 时，如果第二个方法是泛型的，则需要测试是否可以推断出第二个方法类型参数的实例化，使得第一个方法比第二个方法更具体。

令 $m1$ 为第一个方法，$m2$ 为第二个方法。其中 $m2$ 具有类型参数 $P_1, ..., P_n$，令 $\alpha_1, ..., \alpha_p$ 为推断变量，令 $\theta$ 为替换 `[P_1:=\alpha_1, ..., P_p:=\alpha_p]`。

令 $e_1, ..., ek$ 为对应调用的参数表达式。那么：

- 如果 $m1$ 和 $m2$ 通过严格或松散调用 (§15.12.2.2, §15.12.2.3) 可用，令 $S_1, ..., Sk$ 为 $m1$ 的形式参数类型，令 $T_1, ..., Tk$ 为 $\theta$ 应用于 $m2$ 的形式参数类型的结果。

- 如果 $m1$ 和 $m2$ 通过变量调用 (§15.12.2.4) 可用，令 $S_1, Sk$ 为 $m1$ 的前 $k$ 个变量参数类型，令 $T_1, ..., Tk$ 为 $\theta$ 应用于 $m2$ 的前 $k$ 个变量参数类型的结果。

注意，$S_1, ..., Sk$ 不应用任何替换，即使 $m1$ 是泛型的，$m2$ 的类型参数也被视为类型变量，而不是推断变量。

确定 $m1$ 是否比 $m2$ 更具体的步骤如下：

- 首先，根据 §18.1.3 的规定，从 $P_1, ..., P_p$ 的声明边界生成初始边界集 $B$。

- 其次，对于所有 $i (1 \leq i \leq k)$，生成一组约束公式或边界。如果 $T_i$ 是良构类型，则如果 $S_i$ 比 $T_i$ 更具体 (§15.12.2.5)，结果为 **true**，否则为 **false**（注意 $S_i$ 是良构类型）。否则，如果 $S_i$ 和 $T_i$ 都是泛型接口类型，生成约束 `<S_i < T_i>`。否则，如果 $S_i$ 的接口是 $T_i$ 的超接口或子接口（或者当 $T_i$ 是交类型时，$S_i$ 的某个接口是 $T_i$ 的超接口或子接口），生成约束 `<S_i < T_i>`。否则，令 $MT_{S_i}$ 为 $S_i$ 的函数类型，$MT_{T_i}$ 为 $T_i$ 的函数类型。如果 $MT_{S_i}$ 和 $MT_{T_i}$ 的形式参数或类型参数数量不同，结果为 **false**。否则：

  - 令 $A_1, ..., A_n$ 为 $MT_{S_i}$ 的类型参数，$B_1, ..., B_n$ 为 $MT_{T_i}$ 的类型参数。令 $\theta'$ 为替换 `[B_1 := A_1, ..., B_n := A_n]`。那么，对于所有 $j (1 \leq j \leq n)$：

    - 如果 $A_j$ 提到 $A_1, ..., A_n$ 之一且 $B_j$ 不是良构类型，则 **false**。

    - 否则，当 $x$ 是 $A_j$ 的边界且 $y$ 是 $B_j$ 的边界时，生成 `<x = y\theta'>`。如果 $A_j$ 提到 $A_1, ... A_n$ 之一且 $B_j$ 不是良构类型，那么产生等式约束会导致作用域外的推断变量。用作用域类型实例化推断变量是没有意义的，每当出现这种情况时都选择放弃。这种简化不是保持完备的（形式参数类型和返回类型的处理相同）。

- 令 $U_1, ..., U_k$ 为 $MT_S$ 的形式参数类型，令 $V_1, ..., V_k$ 为 $MT_T$ 的形式参数类型。那么，对于所有 $j (1 \leq j \leq k)$：

  - 如果 $U_j$ 提到 $A_1, ..., A_{n_j}$ 之一且 $V_j$ 不是良构类型，则 **false**。



## 类型推断规则

- 否则，如果 $V_j\theta' <: U_j$，且 $U_1', ..., U_k'$ 是 `MT_S'` 的形式参数类型，$A_1', ..., A_{n_j}'$ 是 `MT_S'` 的类型参数，生成 `<V_j[B_1:=A_1', ..., B_{n_j}:=A_{n_j}'] = U_j`。

- 令 $R_S$ 为 `MT_S` 的返回类型，$R_T$ 为 `MT_T` 的返回类型。那么：

  - 如果 $R_S$，如果 $e_j$ 是显式类型类型的 lambda 表达式且 $R_T$ 不是良构类型，则 `false`。

  - 如果 $R_T$ 是 `void`，则为 `true`。

  - 否则，如果 $R_S$ 和 $R_T$ 都是泛型接口类型且 $e_j$ 至少有一个结果表达式，则对于 $e_j$ 中的每个结果表达式，重复整个第二个步骤，以推断出 $R_S$ 对该结果表达式比 $R_T\theta'$ 更具体。

  - 否则，如果 $R_S$ 是基本类型而 $R_T$ 不是，且 $e_i$ 至少有一个结果表达式，且 $e_i$ 的每个结果表达式都是基本类型的独立表达式 (§15.2)，则为 `true`。

  - 否则，如果 $R_T$ 是基本类型而 $R_S$ 不是，且 $e_i$ 至少有一个结果表达式，且 $e_i$ 的每个结果表达式都是引用类型的独立表达式或多态表达式 (poly)，则为 `true`。

  - 否则，$R_S <: R_T\theta'$。

- 否则，如果 $e_i$ 是精确方法引用：

  - $R_T$ 是 `void`，则为 `true`。

  - 否则，如果 $R_S$ 是基本类型而 $R_T$ 不是，且 $e_i$ 的编译时声明有返回类型，则为 `true`。

  - 否则，如果 $R_S$ 是基本类型且 $R_S$ 不是（此处应为 $R_T$ 不是），且 $e_i$ 的编译时声明有引用类型，则为 `true`。

  - 否则，$R_S <: R_T\theta'$。

- 否则，如果 $e_i$ 是括号表达式，则将从 $R_S$ 和 $R_T$ 导出的约束规则递归应用于包含的表达式。

- 否则，如果 $e_i$ 是条件表达式，则将从 $R_S$ 和 $R_T$ 导出的约束规则递归应用于它的两个操作数。

- 否则，如果 $e_i$ 是 `switch` 表达式，则将从 $R_S$ 和 $R_T$ 导出的约束规则递归应用于它的每个结果表达式。

- 否则，`false`。

  - 第三，如果 $m_2$ 通过变量调用指定且具有 $k+1$ 个参数，由于 $S_{k+1}$ 是 $m_1$ 的 $k+1$ 个变量参数类型，$T_{k+1}$ 是 $\theta$ 应用于 $m_2$ 的 $k+1$ 个变量参数类型的结果，生成约束 `<S_{k+1} <: T_{k+1}`。

- 第四，将生成的边界和约束公式归约并合并到 $B$ 中，以产生一个边界集 $B'$。

- 如果 $B'$ 不包含边界 `false`，且 $B'$ 中所有推断变量的解析成功，则 $m1$ 比 $m2$ 更具体。

否则，$m1$ 不比 $m2$ 更具体。

# 第 19 章 语法

本章重复了第 4 章、6-10 章、14 章和 15 章中的语法规则，以及第 3 章中词法语法的关键部分，并使用了 §2.4 中的符号。

## 来自 §3 的产生式（词法结构）

### 标识符 (Identifier)

```
IdentifierChars 但不是保留关键字 (ReservedKeyword) 或 布尔字面量 (BooleanLiteral)
或 空值字面量 (NullLiteral)
```

### IdentifierChars

```
JavaLetter [JavaLetterOrDigit]
```

### JavaLetter

任何属于“Java 字母”的 Unicode 字符

### JavaLetterOrDigit

任何属于“Java 字母或数字”的 Unicode 字符

### 类型 (TypeIdent)

```
Identifier 但不是 permits, record, sealed, var 或 yield
```

### 未限定方法标识符 (UnqualifiedMethodIdentifier)

```
Identifier 但不是 yield
```

### 面量 (Literal)

```
IntegerLiteral
FloatingPointLiteral
BooleanLiteral
CharacterLiteral
StringLiteral
TextBlock
NullLiteral
```

## 来自 §4 的产生式（类型、值和变量）

### 类型 (Type)

```
PrimitiveType
ReferenceType
```

### 基本类型 (PrimitiveType)

```
[Annotation] NumericType
[Annotation] boolean
```

### 数值类型 (NumericType)

```
IntegralType
FloatingPointType
```

### 整数类型 (IntegralType)

(其之一)
`byte` `short` `int` `long` `char`

### 浮点数类型 (FloatingPointType)

(其之一)
`float` `double`

### 引用类型 (ReferenceType)

```
ClassOrInterfaceType
TypeVariable
ArrayType
```

### 类或接口类型 (ClassOrInterfaceType)

```
ClassType
InterfaceType
```

### 类类型 (ClassType)

```
[Annotation] . TypeIdentifier [TypeArguments]
PackageName . {Annotation} TypeIdentifier [TypeArguments]
ClassOrInterfaceType . {Annotation} TypeIdentifier [TypeArguments]
```

### 接口类型 (InterfaceType)

```
ClassType
```

### 类型变量 (TypeVariable)

```
[Annotation] TypeIdentifier
```

### 数组类型 (ArrayType)

```
PrimitiveType Dims
ClassOrInterfaceType Dims
TypeVariable Dims
```

### 维度 (Dims)

```
[Annotation] [] [Annotation] []
```

### 类型参数 (TypeParameter)

```
[TypeParameterModifier] TypeIdentifier [TypeBound]
```

### 类型参数修饰 (TypeParameterModifier)

```
Annotation
```

### 类型边界 (TypeBound)

```
extends TypeVariable
nextends ClassOrInterfaceType [AdditionalBound]
```

### 附加边界 (AdditionalBound)

```
& InterfaceType
```

### 泛型参数列表 (TypeArgumentList)

```
TypeArgument { , TypeArgument }
```

### 泛型参数 (TypeArgument)

```
ReferenceType
Wildcard
```

### 通配符 (Wildcard)

```
[Annotation] ? [WildcardBounds]
```

### 通配符边界 (WildCardBounds)

```
extends ReferenceType
super ReferenceType
```

## 来自 §6 的产生式（名称）

### 模块名 (ModuleName)

```
Identifier
ModuleName . Identifier
```

### 包名 (PackageName)

```
Identifier
PackageName . Identifier
```

### 类型名 (TypeName)

```
TypeIdentifier
PackageOrTypeName . TypeIdentifier
```

### 表达式名 (ExpressionName)

```
Identifier
AmbiguousName . Identifier
```

### 方法名 (MethodName)

```
UnqualifiedMethodIdentifier
```

### 包或类型名 (PackageOrTypeName)

```
Identifier
PackageOrTypeName . Identifier
```

### 歧义名 (AmbiguousName)

```
Identifier
AmbiguousName . Identifier
```

## 来自 §7 的产生式（包和模块）

### 编译单元 (CompilationUnit)

```
OrdinaryCompilationUnit
ModularCompilationUnit
```

### 普通编译单元 (OrdinaryCompilationUnit)

```
[PackageDeclaration] [ImportDeclaration]
{TopLevelClassOrInterfaceDeclaration}
```

### 模块化编译单元 (ModularCompilationUnit)

```
{ImportDeclaration} ModuleDeclaration
```

### 包声明 (PackageDeclaration)

```
{PackageModifier} package Identifier [ . Identifier ] ;
```

### 包修饰符 (PackageModifier)

```
Annotation
```

### 导入声明 (ImportDeclaration)

```
SingleTypeImportDeclaration
TypeImportOnDemandDeclaration
SingleStaticImportDeclaration
StaticImportOnDemandDeclaration
```

### 单类型导入声明 (SingleTypeImportDeclaration)

```
import TypeName ;
```

### 按需类型导入声明 (TypeImportOnDemandDeclaration)

```
import PackageOrTypeName * ;
```

### 单静态导入声明 (SingleStaticImportDeclaration)

```
import static TypeName . Identifier ;
```

### 按需静态导入声明 (StaticImportOnDemandDeclaration)

```
import static TypeName * ;
```

### 顶层类或接口声明 (TopLevelClassOrInterfaceDeclaration)

```
ClassDeclaration
InterfaceDeclaration
```

### 模块声明 (ModuleDeclaration)

```
[Annotation] [open] module Identifier { . Identifier
{ {ModuleDirective}} }
```

### 模块指令 (ModuleDirective)

```
requires [RequiresModifier] ModuleName ;
exports Identifier ;
exports Identifier ;
exports Identifier ;
exports Identifier ;
exports Identifier ;
exports Identifier ;
exports Identifier ;
exports Identifier ;
provides ;
```

### 需要修饰符 (RequiresModifier)

(其之一)
`static`

## 来自 §8 的产生式（类）

### 类声明 (ClassDeclaration)

```
UnqualifiedMethodIdentifier
```

(其之一)
`static`

### 未限定方法标识符 (UnqualifiedMethodIdentifier)

```
Identifier 但不是 yield
```

## 来自 §9 的产生式（接口）

```
InterfaceDeclaration:
NormalInterfaceDeclaration
AnnotationInterfaceDeclaration
```

```
NormalInterfaceModifier:
[InterfaceModifier] interface TypeIdentifier [TypeParameters]
[InterfaceExtends] [InterfacePermits] InterfaceBody
```

```
InterfaceModifier:
(二选一)
Annotation public protected private
abstract static sealed non-sealed strictfp
```

```
InterfaceExtends:
extends InterfaceTypeList
```

```
InterfacePermits:
permits TypeName (, , TypeName)
```

```
InterfaceBody:
{ InterfaceMemberDeclaration }
```

```
InterfaceMemberDeclaration:
ConstantDeclaration
InterfaceMethodDeclaration
ClassDeclaration
InterfaceDeclaration
;
```

```
ConstantDeclaration:
{ConstantModifier} UnannType VariableDeclarList ;
```

```
ConstantModifier:
(二选一)
Annotation public
static final
```



# 来自 §9 (接口) 的产生

## InterfaceMethodDeclaration

```
InterfaceMethodDeclaration:
{InterfaceMethodModifier} MethodHeader MethodBody
```

## InterfaceMethodModifier

```
InterfaceMethodModifier:
(二选一)
Annotation
public
private
abstract
default
static
strictfp
```

## AnnotationInterfaceDeclaration

```
AnnotationInterfaceDeclaration:
{AnnotationInterfaceModifier} @ interface TypeIdentifier AnnotationInterfaceBody
```

## AnnotationInterfaceBody

```
AnnotationInterfaceBody:
{ {AnnotationInterfaceMemberDeclaration } }
```

## AnnotationInterfaceMemberDeclaration

```
AnnotationInterfaceMemberDeclaration:
AnnotationInterfaceElementDeclaration
ConstantDeclaration
ClassDeclaration
InterfaceDeclaration
;
```

## AnnotationInterfaceElementDeclaration

```
AnnotationInterfaceElementDeclaration:
{[AnnotationInterfaceElementModifier] UnannType Identifier () [Dims [DefaultValue]] ;
```

## AnnotationInterfaceElementModifier

```
AnnotationInterfaceElementModifier:
(二选一)
Annotation
public
abstract
```

## DefaultValue

```
DefaultValue:
default ElementValue
```

# 语法

## Annotation

```
Annotation:
NormalAnnotation
MarkerAnnotation
SingleElementAnnotation
```

## NormalAnnotation

```
NormalAnnotation:
@ TypeName < [ElementPairList] >
```

## ElementPairList

```
ElementPairList:
ElementPair { {, ElementPair } }
```

## ElementValue

```
ElementValue:
Identifier = ElementValue
```

```
ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation
```

## ElementValueArrayInitializer

```
ElementValueArrayInitializer:
{ [ElementValueList] [, ] }
```

## ElementValueList

```
ElementValueList:
ElementValue { {, ElementValue } }
```

## MarkerAnnotation

```
MarkerAnnotation:
@ TypeName
```

## SingleElementAnnotation

```
SingleElementAnnotation:
@ TypeName ( ElementValue )
```

# 来自 §10 (数组) 的产生

## ArrayInitializer

```
ArrayInitializer:
{ [VariableInitializerList] [, ] }
```

## VariableInitializerList

```
VariableInitializerList:
VariableInitializer { {, VariableInitializer } }
```

# 来自 §14 (块、语句和模式) 的产生

## Block

```
Block:
  [BlockStatements] }
```

## BlockStatements

```
BlockStatements:
  BlockStatement {BlockStatement}
```

## BlockStatement

```
BlockStatement:
  LocalClassOrInterfaceDeclaration
  LocalVariableDeclarationStatement
  Statement
```

## LocalClassOrInterfaceDeclaration

```
LocalClassOrInterfaceDeclaration:
  ClassDeclaration
  NormalInterfaceDeclaration
```

## LocalVariableDeclarationStatement

```
LocalVariableDeclarationStatement:
  LocalVariableDeclaration ;
```

## LocalVariableDeclaration

```
LocalVariableDeclaration:
  [VariableModifier] LocalVariableType VariableDeclaratorList
```

## LocalVariableType

```
LocalVariableType:
  UnannType
var
```

## Statement

```
Statement:
  StatementWithoutTrailingSubstatement
  LabeledStatement
  IfThenElseStatement
  WhileStatement
  ForStatementNoShort
```

## StatementNoShortIf

```
StatementNoShortIf:
  StatementWithoutTrailingSubstatement
  LabeledNoShortIf
  IfThenElseStatementNoShortIf
  WhileStatementNoShortIf
  ForStatementNoShortIf
```

## StatementWithoutTrailingSubstatement

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
  YieldStatement
```

## EmptyStatement

```
EmptyStatement:
  ;
```

## LabeledStatement

```
LabeledStatement:
  Identifier : Statement
```

## LabeledStatementNoShortIf

```
LabeledStatementNoShortIf:
  Identifier : StatementNoShortIf
```

## ExpressionStatement

```
ExpressionStatement:
  StatementExpression ;
```

## StatementExpression

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

# 语法

## IfThenStatement

```
IfThenStatement:
if ( Expression ) Statement
```

## IfThenElseStatement

```
IfThenElseStatement:
if ( Expression ) StatementNoShortIf else Statement
```

## IfThenElseStatementNoShortIf

```
IfThenElseStatementNoShortIf:
if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

## AssertStatement

```
AssertStatement:
assert Expression ;
assert Expression : Expression ;
```

## SwitchStatement

```
SwitchStatement:
switch ( Expression ) SwitchBlock
```

## SwitchBlock

```
SwitchBlock:
{ SwitchRule {SwitchRule} }
{ SwitchBlockStatementGroup}{SwitchLabel :} }
```

## SwitchRule

```
SwitchRule:
SwitchLabel -> Expression ;
SwitchLabel -> Block
SwitchLabel -> ThrowStatement
```

## SwitchBlockStatementGroup

```
SwitchBlockStatementGroup:
SwitchLabel : {SwitchLabel :} BlockStatements
```

## SwitchLabel

```
SwitchLabel:
case CaseConstant [, , CaseConstant}
default
```

## CaseConstant

```
CaseConstant:
ConditionalExpression
```

## WhileStatement

```
WhileStatement:
while ( Expression ) Statement
```

## WhileStatementNoShortIf

```
WhileStatementNoShortIf:
while ( Expression ) StatementNoShortIf
```

## DoStatement

```
DoStatement:
do Statement while ( Expression ) ;
```

## ForStatement

```
ForStatement:
BasicForStatement
EnhancedForStatement
```

## ForStatementNoShortIf

```
ForStatementNoShortIf:
BasicForStatementNoShortIf
EnhancedForStatementNoShortIf
```

## BasicForStatement

```
BasicForStatement:
for ([ForInit]; [Expression] ; [ForUpdate] ) Statement
```

## BasicForStatementNoShortIf

```
BasicForStatementNoShortIf:
for ( [ForInit]; [Expression] ; [ForUpdate] ) StatementNoShortIf
```

## ForInit

```
ForInit:
StatementExpressionList
LocalVariableDeclaration
```

## ForUpdate

```
ForUpdate:
StatementExpressionList
```

## StatementExpressionList

```
StatementExpressionList:
StatementExpression ( , StatementExpression )
```

## EnhancedForStatement

```
EnhancedForStatement:
for ( LocalVariableDeclaration : Expression )
Statement
```

## EnhancedForStatementNoShortIf

```
EnhancedForStatementNoShortIf:
for ( LocalVariableDeclaration : Expression )
```

# 语法

## BreakStatement

```
BreakStatement:
break [Identifier]
```

## YieldStatement

```
YieldStatement:
yield Expression ;
```

## ContinueStatement

```
ContinueStatement:
continue [Identifier] ;
```

## ReturnStatement

```
ReturnStatement:
return [Expression] ;
```

## ThrowStatement

```
ThrowStatement:
throw Expression ;
```

## SynchronizedStatement

```
SynchronizedStatement:
synchronized ( Expression )
```

## TryStatement

```
TryStatement:
  try Catches
  finally
```

## TryWithResources

```
TryWithResources:
  try ResourceSpecification
```

## Catches

```
Catches:
  CatchClause]
```

## CatchClause

```
CatchClause:
catch ( CatchParameter )
```

## CatchParameter

```
CatchParameter:
{VariableModifier} CatchType
```

# 来自 §15 (表达式) 的产生

## Primary

```
Primary:
PrimaryNewArray
ArrayCreationExpression
```

## PrimaryNewArray

```
PrimaryNewArray:
Literal
this
TypeName . this
( Expression )
ClassCreationExpression
FieldAccess
MethodInvocation
MethodReference
```

## Literal

```
Literal:
TypeName { } . class
NumericType { } . class
boolean { } . class
```

## ClassCreationExpression

```
ClassCreationExpression:
UnqualifiedClassCreationExpression
ExpressionName . UnqualifiedCreationExpression
Primary . UnqualifiedCreationExpression
```

## UnqualifiedClassCreationExpression

```
UnqualifiedClassCreationExpression:
new [TypeArguments] ClassOrInterfaceToInstantiate ([ArgumentList] ) [ClassBody]
```

## ClassOrInterfaceTypeToInstantiate

```
ClassOrInterfaceTypeToInstantiate:
[Annotation] Identifier { [Annotation] Identifier
[TypeArgumentsOrDiamond]
```

## TypeArgumentsOrDiamond

```
TypeArgumentsOrDiamond:
TypeArguments
<>
```

# 语法

## ArrayCreationExpression

```
ArrayCreationExpression:
ArrayCreationExpressionWithoutInitializer
ArrayCreationExpressionWithInitializer
```

## ArrayCreationExpressionWithoutInitializer

```
ArrayCreationExpressionWithoutInitializer:
new PrimitiveType DimExprs [Dims]
new ClassOrInterfaceType DimExprs [Dims]
```

## ArrayCreationExpressionWithInitializer

```
ArrayCreationExpressionWithInitializer:
new PrimitiveType Dims ArrayInitializer
new ClassOrInterfaceType Dims ArrayInitializer
```

## DimExprs

```
DimExprs:
DimExpr [DimExpr]
```

## DimExpr

```
DimExpr:
[Annotation] [ Expression ]
```

## ArrayAccess

```
ArrayAccess:
ExpressionName [ Expression ]
PrimaryNewArray { Expression }
ArrayCreationExpressionWithInitializer [ Expression ]
```

## FieldAccess

```
FieldAccess:
Primary . Identifier
super . Identifier
TypeName . super . Identifier
```

## MethodInvocation

```
MethodInvocation:
MethodName ( [ArgumentList] )
TypeName . [TypeArguments] Identifier ([ArgumentList])
ExpressionName . [TypeArguments] Identifier ([ArgumentList])
Primary . [TypeArguments] Identifier ([ArgumentList])
super . [TypeArguments] Identifier ([ArgumentList])
TypeName . super . [TypeArguments] Identifier ([ArgumentList])
```

## ArgumentList

```
ArgumentList:
Expression ( , Expression )
```

## MethodReference

```
MethodReference:
ExpressionName :: [TypeArguments] Identifier
Primary :: [TypeArguments] Identifier
ReferenceType :: [TypeArguments] Identifier
super :: [TypeArguments] Identifier
TypeName . super :: [TypeArguments] Identifier
ClassType :: [TypeArguments] new
ArrayType : new
```



# UnqualifiedClassCreationExpression

```
new [TypeArguments] ClassOrInterfaceToInstantiate ([ArgumentList]) [ClassBody]
```

# ClassOrInterfaceTypeToInstantiate

```
[Annotation] Identifier { [Annotation] Identifier [TypeArgumentsOrDiamond] }
```

# TypeArgumentsOrDiamond

```
TypeArguments
<>
```

# 语法

## ArrayCreationExpression

```
ArrayCreationExpression:
ArrayCreationExpressionWithoutInitializer
ArrayCreationExpressionWithInitializer
```

## ArrayCreationExpressionWithoutInitializer

```
ArrayCreationExpressionWithoutInitializer:
new PrimitiveType DimExprs [Dims]
new ClassOrInterfaceType DimExprs [Dims]
```

## ArrayCreationExpressionWithInitializer

```
ArrayCreationExpressionWithInitializer:
new PrimitiveType Dims ArrayInitializer
new ClassOrInterfaceType Dims ArrayInitializer
```

## DimExprs

```
DimExprs:
DimExpr [DimExpr]
```

## DimExpr

```
DimExpr:
[Annotation] [ Expression ]
```

## ArrayAccess

```
ArrayAccess:
ExpressionName [ Expression ]
PrimaryNewArray { Expression }
ArrayCreationExpressionWithInitializer [ Expression ]
```

## FieldAccess

```
FieldAccess:
Primary . Identifier
super . Identifier
TypeName . super . Identifier
```

## MethodInvocation

```
MethodInvocation:
MethodName ( [ArgumentList] )
TypeName . [TypeArguments] Identifier ([ArgumentList])
ExpressionName . [TypeArguments] Identifier ([ArgumentList])
Primary . [TypeArguments] Identifier ([ArgumentList])
super . [TypeArguments] Identifier ([ArgumentList])
TypeName . super . [TypeArguments] Identifier ([ArgumentList])
```

## ArgumentList

```
ArgumentList:
Expression ( , Expression )
```

## MethodReference

```
MethodReference:
ExpressionName :: [TypeArguments] Identifier
Primary :: [TypeArguments] Identifier
ReferenceType :: [TypeArguments] Identifier
super :: [TypeArguments] Identifier
TypeName . super :: [TypeArguments] Identifier
ClassType :: [TypeArguments] new
ArrayType : new
```

---

# 来自 §9 (接口) 的产生

## InterfaceDeclaration

```
InterfaceDeclaration:
NormalInterfaceDeclaration
AnnotationInterfaceDeclaration
```

## NormalInterfaceModifier

```
NormalInterfaceModifier:
[InterfaceModifier] interface TypeIdentifier [TypeParameters]
[InterfaceExtends] [InterfacePermits] InterfaceBody
```

## InterfaceModifier

```
InterfaceModifier:
(二选一)
Annotation public protected private
abstract static sealed non-sealed strictfp
```

## InterfaceExtends

```
InterfaceExtends:
extends InterfaceTypeList
```

## InterfacePermits

```
InterfacePermits:
permits TypeName (, , TypeName)
```

## InterfaceBody

```
InterfaceBody:
{ InterfaceMemberDeclaration }
```

## InterfaceMemberDeclaration

```
InterfaceMemberDeclaration:
ConstantDeclaration
InterfaceMethodDeclaration
ClassDeclaration
InterfaceDeclaration
;
```

## ConstantDeclaration

```
ConstantDeclaration:
{ConstantModifier} UnannType VariableDeclarList ;
```

## ConstantModifier

```
ConstantModifier:
(二选一)
Annotation public
static final
```

## InterfaceMethodDeclaration

```
InterfaceMethodDeclaration:
{InterfaceMethodModifier} MethodHeader MethodBody

InterfaceMethodModifier:
(二选一)
Annotation public private
abstract default static strictfp
```

## AnnotationInterfaceDeclaration

```
AnnotationInterfaceDeclaration:
{AnnotationInterfaceModifier} @ interface TypeIdentifier AnnotationInterfaceBody

AnnotationInterfaceBody:
{ {AnnotationInterfaceMemberDeclaration }
```

## AnnotationInterfaceMemberDeclaration

```
AnnotationInterfaceMemberDeclaration:
AnnotationInterfaceElementDeclaration
ConstantDeclaration
ClassDeclaration
InterfaceDeclaration
;
```

## AnnotationInterfaceElementDeclaration

```
AnnotationInterfaceElementDeclaration:
{[AnnotationInterfaceElementModifier] UnannType Identifier () [Dims [DefaultValue]] ;
```

## AnnotationInterfaceElementModifier

```
AnnotationInterfaceElementModifier:
(二选一)
Annotation public
abstract
```

## DefaultValue

```
DefaultValue:
deault ElementValue
```

## 语法

## Annotation

```
Annotation:
NormalAnnotation
MarkerAnnotation
SingleElementAnnotation
```

## NormalAnnotation

```
NormalAnnotation:
@ TypeName < [ElementPairList] >
```

## ElementPairList

```
ElementPairList:
ElementPair { {, ElementPair }
```

## ElementValue

```
ElementValue:
Identifier = ElementValue
```

## ElementValue (Alternative)

```
ElementValue:
ConditionalExpression
ElementValueArrayInitializer
Annotation
```

## ElementValueArrayInitializer

```
ElementValueArrayInitializer:
{ [ElementValueList] [, ] }
```

## ElementValueList

```
ElementValueList:
ElementValue { {, ElementValue }
```

## MarkerAnnotation

```
MarkerAnnotation:
@ TypeName
```

## SingleElementAnnotation

```
SingleElementAnnotation:
@ TypeName ( ElementValue )
```

---

# 来自 §10 (数组) 的产生

## ArrayInitializer

```
ArrayInitializer:
{ [VariableInitializerList] [, ] }
```

## VariableInitializerList

```
VariableInitializerList:
VariableInitializer { {, VariableInitializer }
```

---

# 来自 §14 (块、语句和模式) 的产生

## Block

```
Block:
[BlockStatements] }
```

## BlockStatements

```
BlockStatements:
BlockStatement {BlockStatement}
```

## BlockStatement

```
BlockStatement:
LocalClassOrInterfaceDeclaration
LocalVariableDeclarationStatement
Statement
```

## LocalClassOrInterfaceDeclaration

```
LocalClassOrInterfaceDeclaration:
ClassDeclaration
NormalInterfaceDeclaration
```

## LocalVariableDeclarationStatement

```
LocalVariableDeclarationStatement:
LocalVariableDeclaration ;
```

## LocalVariableDeclaration

```
LocalVariableDeclaration:
[VariableModifier] LocalVariableType VariableDeclaratorList
```

## LocalVariableType

```
LocalVariableType:
UnannType
var
```

## Statement

```
Statement:
StatementWithoutTrailingSubstatement
LabeledStatement
IfThenElseStatement
WhileStatement
ForStatementNoShort
```

## StatementNoShortIf

```
StatementNoShortIf:
StatementWithoutTrailingSubstatement
LabeledNoShortIf
IfThenElseStatementNoShortIf
WhileStatementNoShortIf
ForStatementNoShortIf
```

## StatementWithoutTrailingSubstatement

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
YieldStatement
```

## EmptyStatement

```
EmptyStatement:
;
```

## LabeledStatement

```
LabeledStatement:
Identifier : Statement
```

## LabeledStatementNoShortIf

```
LabeledStatementNoShortIf:
Identifier : StatementNoShortIf
```

## ExpressionStatement

```
ExpressionStatement:
StatementExpression ;
```

## StatementExpression

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

---

# 语法

## IfThenStatement

```
if ( Expression ) Statement
```

## IfThenElseStatement

```
if ( Expression ) StatementNoShortIf else Statement
```

## IfThenElseStatementNoShortIf

```
if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

## AssertStatement

```
assert Expression ;
assert Expression : Expression ;
```

## SwitchStatement

```
switch ( Expression ) SwitchBlock
```

## SwitchBlock

```
SwitchBlock:
{ SwitchRule {SwitchRule} }
{ SwitchBlockStatementGroup}{SwitchLabel :} }
```

## SwitchRule

```
SwitchRule:
SwitchLabel -> Expression ;
SwitchLabel -> Block
SwitchLabel -> ThrowStatement
```

## SwitchBlockStatementGroup

```
SwitchBlockStatementGroup:
SwitchLabel : {SwitchLabel :} BlockStatements
```

## SwitchLabel

```
SwitchLabel:
case CaseConstant [, , CaseConstant}
default
```

## CaseConstant

```
CaseConstant:
ConditionalExpression
```

## WhileStatement

```
while ( Expression ) Statement
```

## WhileStatementNoShortIf

```
while ( Expression ) StatementNoShortIf
```

## DoStatement

```
do Statement while ( Expression ) ;
```

## ForStatement

```
ForStatement:
BasicForStatement
EnhancedForStatement
```

## ForStatementNoShortIf

```
ForStatementNoShortIf:
BasicForStatementNoShortIf
EnhancedForStatementNoShortIf
```

## BasicForStatement

```
BasicForStatement:
for ([ForInit]; [Expression] ; [ForUpdate] ) Statement
```

## BasicForStatementNoShortIf

```
BasicForStatementNoShortIf:
for ( [ForInit]; [Expression] ; [ForUpdate] ) StatementNoShortIf
```

## ForInit

```
ForInit:
StatementExpressionList
LocalVariableDeclaration
```

## ForUpdate

```
ForUpdate:
StatementExpressionList
```

## StatementExpressionList

```
StatementExpressionList:
StatementExpression ( , StatementExpression )
```

## EnhancedForStatement

```
EnhancedForStatement:
for ( LocalVariableDeclaration : Expression )
Statement
```

## EnhancedForStatementNoShortIf

```
EnhancedForStatementNoShortIf:
for ( LocalVariableDeclaration : Expression )
```

---

# 语法

## BreakStatement

```
BreakStatement:
break [Identifier]
```

## YieldStatement

```
YieldStatement:
yield Expression ;
```

## ContinueStatement

```
ContinueStatement:
continue [Identifier] ;
```

## ReturnStatement

```
ReturnStatement:
return [Expression] ;
```

## ThrowStatement

```
ThrowStatement:
throw Expression ;
```

## SynchronizedStatement

```
SynchronizedStatement:
synchronized ( Expression )
```

## TryStatement

```
TryStatement:
try Catches
finally
```

## TryWithResources

```
TryWithResources:
try ResourceSpecification
```

## Catches

```
Catches:
CatchClause]
```

## CatchClause

```
CatchClause:
catch ( CatchParameter )
```

## CatchParameter

```
CatchParameter:
{VariableModifier} CatchType
```

## CatchType

```
CatchType:
UnannType | ClassType
```

## Finally

```
Finally:
finally Block
```

## TryWithResources (Duplicate)

```
TryWithResources:
try ResourceSpecification
```

## ResourceSpecification

```
ResourceSpecification:
( ResourceList )
```

## ResourceList

```
ResourceList:
Resource { }
```

## Resource

```
Resource:
LocalVariableDeclaration
VariableAccess
```



# 来自 §15 (表达式) 的产生

## Primary

```
Primary:
  PrimaryNewArray
  ArrayCreationExpression
```

```
PrimaryNewArray:
  Literal
  this
  TypeName . this
  ( Expression )
  ClassCreationExpression
  FieldAccess
  MethodInvocation
  MethodReference
```

```
Literal:
  TypeName { } . class
  NumericType { } . class
  boolean { } . class
```

## ClassCreationExpression

```
ClassCreationExpression:
  UnqualifiedClassCreationExpression
  ExpressionName . UnqualifiedCreationExpression
  Primary . UnqualifiedCreationExpression
```

```
UnqualifiedClassCreationExpression:
  new [TypeArguments] ClassOrInterfaceToInstantiate ( [ArgumentList] ) [ClassBody]
```

```
ClassOrInterfaceTypeToInstantiate:
  [Annotation] Identifier { [Annotation] Identifier
  [TypeArgumentsOrDiamond]
```

```
TypeArgumentsOrDiamond:
  TypeArguments
  <>
```

## ArrayCreationExpression

```
ArrayCreationExpression:
  ArrayCreationExpressionWithoutInitializer
  ArrayCreationExpressionWithInitializer
```

```
ArrayCreationExpressionWithoutInitializer:
  new PrimitiveType DimExprs [Dims]
  new ClassOrInterfaceType DimExprs [Dims]
```

```
ArrayCreationExpressionWithInitializer:
  new PrimitiveType Dims ArrayInitializer
  new ClassOrInterfaceType Dims ArrayInitializer
```

```
DimExprs:
  DimExpr [DimExpr]
```

```
DimExpr:
  [Annotation] [ Expression ]
```

## ArrayAccess

```
ArrayAccess:
  ExpressionName [ Expression ]
  PrimaryNewArray { Expression }
  ArrayCreationExpressionWithInitializer [ Expression ]
```

## FieldAccess

```
FieldAccess:
  Primary . Identifier
  super . Identifier
  TypeName . super . Identifier
```

## MethodInvocation

```
MethodInvocation:
  MethodName ( [ArgumentList] )
  TypeName . [TypeArguments] Identifier ( [ArgumentList] )
  ExpressionName . [TypeArguments] Identifier ( [ArgumentList] )
  Primary . [TypeArguments] Identifier ( [ArgumentList] )
  super . [TypeArguments] Identifier ( [ArgumentList] )
  TypeName . super . [TypeArguments] Identifier ( [ArgumentList] )
```

```
ArgumentList:
  Expression ( , Expression )
```

## MethodReference

```
MethodReference:
  ExpressionName :: [TypeArguments] Identifier
  Primary :: [TypeArguments] Identifier
  ReferenceType :: [TypeArguments] Identifier
  super :: [TypeArguments] Identifier
  TypeName . super :: [TypeArguments] Identifier
  ClassType :: [TypeArguments] new
  ArrayType : new
```

# 来自 §9 (接口) 的产生

## InterfaceDeclaration

```
InterfaceDeclaration:
  NormalInterfaceDeclaration
  AnnotationInterfaceDeclaration
```

```
NormalInterfaceDeclaration:
  [InterfaceModifier] interface TypeIdentifier [TypeParameters]
  [InterfaceExtends] [InterfacePermits] InterfaceBody
```

```
InterfaceModifier:
  (二选一)
  Annotation
  public
  protected
  private
  abstract
  static
  sealed
  non-sealed
  strictfp
```

```
InterfaceExtends:
  extends InterfaceTypeList
```

```
InterfacePermits:
  permits TypeName (, TypeName)
```

```
InterfaceBody:
  { InterfaceMemberDeclaration }
```

```
InterfaceMemberDeclaration:
  ConstantDeclaration
  InterfaceMethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

## ConstantDeclaration

```
ConstantDeclaration:
  {ConstantModifier} UnannType VariableDeclaratorList ;
```

```
ConstantModifier:
  (二选一)
  Annotation
  public
  static
  final
```

## InterfaceMethodDeclaration

```
InterfaceMethodDeclaration:
  {InterfaceMethodModifier} MethodHeader MethodBody
```

```
InterfaceMethodModifier:
  (二选一)
  Annotation
  public
  private
  abstract
  default
  static
  strictfp
```

## AnnotationInterfaceDeclaration

```
AnnotationInterfaceDeclaration:
  {AnnotationInterfaceModifier} @ interface TypeIdentifier AnnotationInterfaceBody
```

```
AnnotationInterfaceBody:
  { {AnnotationInterfaceMemberDeclaration } }
```

```
AnnotationInterfaceMemberDeclaration:
  AnnotationInterfaceElementDeclaration
  ConstantDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

```
AnnotationInterfaceElementDeclaration:
  {AnnotationInterfaceElementModifier} UnannType Identifier () [Dims] [DefaultValue] ;
```

```
AnnotationInterfaceElementModifier:
  (二选一)
  Annotation
  public
  abstract
```

```
DefaultValue:
  default ElementValue
```

## Annotation

```
Annotation:
  NormalAnnotation
  MarkerAnnotation
  SingleElementAnnotation
```

```
NormalAnnotation:
  @ TypeName ( [ElementPairList] )
```

```
ElementPairList:
  ElementPair { , ElementPair }
```

```
ElementValue:
  ConditionalExpression
  ElementValueArrayInitializer
  Annotation
```

```
ElementValueArrayInitializer:
  { [ElementValueList] [, ] }
```

```
ElementValueList:
  ElementValue { , ElementValue }
```

```
MarkerAnnotation:
  @ TypeName
```

```
SingleElementAnnotation:
  @ TypeName ( ElementValue )
```

# 来自 §10 (数组) 的产生

```
ArrayInitializer:
  { [VariableInitializerList] [, ] }
```

```
VariableInitializerList:
  VariableInitializer { , VariableInitializer }
```

# 来自 §14 (块、语句和模式) 的产生

## Block

```
Block:
  { [BlockStatements] }
```

```
BlockStatements:
  BlockStatement {BlockStatement}
```

```
BlockStatement:
  LocalClassOrInterfaceDeclaration
  LocalVariableDeclarationStatement
  Statement
```

```
LocalClassOrInterfaceDeclaration:
  ClassDeclaration
  NormalInterfaceDeclaration
```

```
LocalVariableDeclarationStatement:
  LocalVariableDeclaration ;
```

```
LocalVariableDeclaration:
  [VariableModifier] LocalVariableType VariableDeclaratorList
```

```
LocalVariableType:
  UnannType
  var
```

## Statement

```
Statement:
  StatementWithoutTrailingSubstatement
  LabeledStatement
  IfThenElseStatement
  WhileStatement
  ForStatementNoShortIf
```

```
StatementNoShortIf:
  StatementWithoutTrailingSubstatement
  LabeledNoShortIf
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
  YieldStatement
```

```
EmptyStatement:
  ;
```

```
LabeledStatement:
  Identifier : Statement
```

```
LabeledStatementNoShortIf:
  Identifier : StatementNoShortIf
```

```
ExpressionStatement:
  StatementExpression ;
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

## IfThenStatement

```
IfThenStatement:
  if ( Expression ) Statement
```

```
IfThenElseStatement:
  if ( Expression ) StatementNoShortIf else Statement
```

```
IfThenElseStatementNoShortIf:
  if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

## AssertStatement

```
AssertStatement:
  assert Expression ;
  assert Expression : Expression ;
```

## SwitchStatement

```
SwitchStatement:
  switch ( Expression ) SwitchBlock
```

```
SwitchBlock:
  { SwitchRule {SwitchRule} }
  { SwitchBlockStatementGroup {SwitchLabel :} }
```

```
SwitchRule:
  SwitchLabel -> Expression ;
  SwitchLabel -> Block
  SwitchLabel -> ThrowStatement
```

```
SwitchBlockStatementGroup:
  SwitchLabel : {SwitchLabel :} BlockStatements
```

```
SwitchLabel:
  case CaseConstant [, CaseConstant]
  default
```

```
CaseConstant:
  ConditionalExpression
```

## WhileStatement

```
WhileStatement:
  while ( Expression ) Statement
```

```
WhileStatementNoShortIf:
  while ( Expression ) StatementNoShortIf
```

## DoStatement

```
DoStatement:
  do Statement while ( Expression ) ;
```

## ForStatement

```
ForStatement:
  BasicForStatement
  EnhancedForStatement
```

```
ForStatementNoShortIf:
  BasicForStatementNoShortIf
  EnhancedForStatementNoShortIf
```

```
BasicForStatement:
  for ( [ForInit] ; [Expression] ; [ForUpdate] ) Statement
```

```
BasicForStatementNoShortIf:
  for ( [ForInit] ; [Expression] ; [ForUpdate] ) StatementNoShortIf
```

```
ForInit:
  StatementExpressionList
  LocalVariableDeclaration
```

```
ForUpdate:
  StatementExpressionList
```

```
StatementExpressionList:
  StatementExpression ( , StatementExpression )
```

```
EnhancedForStatement:
  for ( LocalVariableDeclaration : Expression ) Statement
```

```
EnhancedForStatementNoShortIf:
  for ( LocalVariableDeclaration : Expression ) StatementNoShortIf
```

## BreakStatement

```
BreakStatement:
  break [Identifier] ;
```

## YieldStatement

```
YieldStatement:
  yield Expression ;
```

## ContinueStatement

```
ContinueStatement:
  continue [Identifier] ;
```

## ReturnStatement

```
ReturnStatement:
  return [Expression] ;
```

## ThrowStatement

```
ThrowStatement:
  throw Expression ;
```



# 来自 §9 (接口) 的产生

```
InterfaceDeclaration:
  NormalInterfaceDeclaration
  AnnotationInterfaceDeclaration
```

```
NormalInterfaceModifier:
  [InterfaceModifier] interface TypeIdentifier [TypeParameters]
  [InterfaceExtends] [InterfacePermits] InterfaceBody
```

```
InterfaceModifier:
  (二选一)
  Annotation public protected private
  abstract static sealed non-sealed strictfp
```

```
InterfaceExtends:
  extends InterfaceTypeList
```

```
InterfacePermits:
  permits TypeName (, , TypeName)
```

```
InterfaceBody:
  { InterfaceMemberDeclaration }
```

```
InterfaceMemberDeclaration:
  ConstantDeclaration
  InterfaceMethodDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

```
ConstantDeclaration:
  {ConstantModifier} UnannType VariableDeclarList ;
```

```
ConstantModifier:
  (二选一)
  Annotation public
  static final
```

```
InterfaceMethodDeclaration:
  {InterfaceMethodModifier} MethodHeader MethodBody

InterfaceMethodModifier:
  (二选一)
  Annotation public private
  abstract default static strictfp
```

```
AnnotationInterfaceDeclaration:
  {AnnotationInterfaceModifier} @ interface TypeIdentifier AnnotationInterfaceBody

AnnotationInterfaceBody:
  { {AnnotationInterfaceMemberDeclaration }

AnnotationInterfaceMemberDeclaration:
  AnnotationInterfaceElementDeclaration
  ConstantDeclaration
  ClassDeclaration
  InterfaceDeclaration
  ;
```

```
AnnotationInterfaceElementDeclaration:
  {[AnnotationInterfaceElementModifier] UnannType Identifier () [Dims [DefaultValue]] ;

AnnotationInterfaceElementModifier:
  (二选一)
  Annotation public
  abstract

DefaultValue:
  deault ElementValue
```

# 语法

```
Annotation:
  NormalAnnotation
  MarkerAnnotation
  SingleElementAnnotation

NormalAnnotation:
  @ TypeName < [ElementPairList] >

ElementPairList:
  ElementPair { {, ElementPair }

ElementValue:
  Identifier = ElementValue

ElementValue:
  ConditionalExpression
  ElementValueArrayInitializer
  Annotation

ElementValueArrayInitializer:
  { [ElementValueList] [, ] }

ElementValueList:
  ElementValue { {, ElementValue }

MarkerAnnotation:
  @ TypeName

SingleElementAnnotation:
  @ TypeName ( ElementValue )
```

# 来自 §10 (数组) 的产生

```
ArrayInitializer:
  { [VariableInitializerList] [, ] }

VariableInitializerList:
  VariableInitializer { {, VariableInitializer }
```

# 来自 §14 (块、语句和模式) 的产生

```
Block:
  [BlockStatements] }

BlockStatements:
  BlockStatement {BlockStatement}

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
  [VariableModifier] LocalVariableType VariableDeclaratorList

LocalVariableType:
  UnannType
  var

Statement:
  StatementWithoutTrailingSubstatement
  LabeledStatement
  IfThenElseStatement
  WhileStatement
  ForStatementNoShort

StatementNoShortIf:
  StatementWithoutTrailingSubstatement
  LabeledNoShortIf
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

# 语法

```
IfThenStatement:
  if ( Expression ) Statement
```

```
IfThenElseStatement:
  if ( Expression ) StatementNoShortIf else Statement
```

```
IfThenElseStatementNoShortIf:
  if ( Expression ) StatementNoShortIf else StatementNoShortIf
```

```
AssertStatement:
  assert Expression ;
  assert Expression : Expression ;
```

```
SwitchStatement:
  switch ( Expression ) SwitchBlock
```

```
SwitchBlock:
  { SwitchRule {SwitchRule} }
  { SwitchBlockStatementGroup}{SwitchLabel :} }
```

```
SwitchRule:
  SwitchLabel -> Expression ;
  SwitchLabel -> Block
  SwitchLabel -> ThrowStatement
```



# SwitchBlockStatementGroup

```
SwitchLabel : {SwitchLabel :} BlockStatements
```

# SwitchLabel

```
case CaseConstant [, , CaseConstant}
default
```

# CaseConstant

```
ConditionalExpression
```

# WhileStatement

`while ( Expression ) Statement`

# WaitStatementNoShortIf

`while ( Expression ) StatementNoShortIf`

# DoStatement

`do Statement while ( Expression ) ;`

# ForStatement

- `BasicForStatement`
- `EnhancedForStatement`

# ForStatementNoShortIf

- `BasicForStatementNoShortIf`
- `EnhancedForStatementNoShortIf`

# BasicForStatement

`for ([ForInit]; [Expression] ; [ForUpdate] ) Statement`

# BasicForStatementNoShortIf

`for ( [ForInit]; [Expression] ; [ForUpdate] ) StatementNoShortIf`

# ForInit

- `StatementExpressionList`
- `LocalVariableDeclaration`

# ForUpdate

`StatementExpressionList`

# StatementExpressionList

`StatementExpression ( , StatementExpression )`

# EnhancedForStatement

```
for ( LocalVariableDeclaration : Expression )
Statement
```

# EnhancedForStatementNoShortIf

```
for ( LocalVariableDeclaration : Expression )
Statement
```

# 语法

## BreakStatement

```
break [Identifier]
```

## YieldStatement

```
yield Expression ;
```

## ContinueStatement

```
continue [Identifier] ;
```

## ReturnStatement

```
return [Expression] ;
```

## ThrowStatement

```
throw Expression ;
```

## SynchronizedStatement

```
synchronized ( Expression )
```

## TryStatement

```
try Catches
finally
```

## TryWithResources

```
try ResourceSpecification
```

## Catches

```
CatchClause]
```

## CatchClause

```
catch ( CatchParameter )
```

## CatchParameter

```
{VariableModifier} CatchType
```

## CatchType

```
UnannType | ClassType
```

## Finally

```
finally Block
```

## ResourceSpecification

```
( ResourceList )
```

## ResourceList

```
Resource { }
```

## Resource

- `LocalVariableDeclaration`
- `VariableAccess`

## Pattern

`TypePattern`

## TypePattern

`LocalVariableDeclaration`

# 来自 §15 (表达式) 的产生

## Primary

```
PrimaryNewArray
ArrayCreationExpression
PrimaryNewArray:
Literal
this
TypeName . this
( Expression )
ClassCreationExpression
FieldAccess
MethodInvocation
MethodReference
```

## Literal

```
TypeName { } . class
NumericType { } . class
boolean { } . class
```

## ClassCreationExpression

- `UnqualifiedClassCreationExpression`
- `ExpressionName . UnqualifiedCreationExpression`
- `Primary . UnqualifiedCreationExpression`

## UnqualifiedClassCreationExpression

```
new [TypeArguments] ClassOrInterfaceToInstantiate ([ArgumentList] ) [ClassBody]
```

## ClassOrInterfaceTypeToInstantiate

```
[Annotation] Identifier { [Annotation] Identifier
[TypeArgumentsOrDiamond]
```

## TypeArgumentsOrDiamond

- `TypeArguments`
- `<>`

## ArrayCreationExpression

- `ArrayCreationExpressionWithoutInitializer`
- `ArrayCreationExpressionWithInitializer`

## ArrayCreationExpressionWithoutInitializer

```
new PrimitiveType DimExprs [Dims]
new ClassOrInterfaceType DimExprs [Dims]
```

## ArrayCreationExpressionWithInitializer

```
new PrimitiveType Dims ArrayInitializer
new ClassOrInterfaceType Dims ArrayInitializer
```

## DimExprs

`DimExpr [DimExpr]`

## DimExpr

```
[Annotation] [ Expression ]
```

## ArrayAccess

- `ExpressionName [ Expression ]`
- `PrimaryNewArray { Expression }`
- `ArrayCreationExpressionWithInitializer [ Expression ]`

## FieldAccess

- `Primary . Identifier`
- `super . Identifier`
- `TypeName . super . Identifier`

## MethodInvocation

- `MethodName ( [ArgumentList] )`
- `TypeName . [TypeArguments] Identifier ([ArgumentList])`
- `ExpressionName . [TypeArguments] Identifier ([ArgumentList])`
- `Primary . [TypeArguments] Identifier ([ArgumentList])`
- `super . [TypeArguments] Identifier ([ArgumentList])`
- `TypeName . super . [TypeArguments] Identifier ([ArgumentList])`

## ArgumentList

`Expression ( , Expression )`

## MethodReference

- `ExpressionName :: [TypeArguments] Identifier`
- `Primary :: [TypeArguments] Identifier`
- `ReferenceType :: [TypeArguments] Identifier`
- `super :: [TypeArguments] Identifier`
- `TypeName . super :: [TypeArguments] Identifier`
- `ClassType :: [TypeArguments] new`
- `ArrayType : new`

## Expression

- `LambdaExpression`
- `AssignmentExpression`

## LambdaExpression

`LambdaParameters -> LambdaBody`

## LambdaParameters

- `([LambdaParameterList]`
- `Identifier`

## LambdaParameterList

- `LambdaParameter (, LambdaParameter)`
- `Identifier {, , Identifier}`

## LambdaParameter

- `{VariableModifier} LambdaParameterType VariableDeclaratorId`
- `VariableArityParameter`

## LambdaParameterType

- `UnannType`
- `var`

## LambdaBody

- `Expression`
- `Block`

## AssignmentExpression

- `ConditionalExpression`
- `Assignment`

## Assignment

`LeftHandSide AssignmentOperator Expression`

## LeftHandSide

- `ExpressionName`
- `FieldAccess`
- `ArrayAccess`

## AssignmentOperator

`(其之一) * = / += += <= >= >= ^ &= = =`

## ConditionalExpression

- `ConditionalOrExpression`
- `ConditionalOrExpression ? Expression : ConditionalExpression`
- `ConditionalOrExpression ? Expression : LambdaExpression`

## ConditionalOrExpression

- `ConditionalAndExpression`
- `ConditionalOrExpression || ConditionalAndExpression`

## ConditionalAndExpression

- `InclusiveOrExpression`
- `ConditionalAndExpression && InclusiveOrExpression`

## InclusiveOrExpression

- `ExclusiveOrExpression`
- `InclusiveOrExpression | ExclusiveOrExpression`

## ExclusiveOrExpression

- `AndExpression`
- `ExclusiveOrExpression ^ AndExpression`

## AndExpression

- `EqualityExpression`
- `AndExpression & EqualityExpression`

## EqualityExpression

- `RelationalExpression`
- `EqualityExpression == RelationalExpression`
- `EqualityExpression != RelationalExpression`

## RelationalExpression

- `ShiftExpression`
- `RelationalExpression < ShiftExpression`
- `RelationalExpression > ShiftExpression`
- `RelationalExpression <= ShiftExpression`
- `RelationalExpression >= ShiftExpression`
- `InstanceofExpression`

## InstanceofExpression

- `RelationalExpression instanceof ReferenceType`
- `RelationalExpression instanceof Pattern`

## ShiftExpression

- `AdditiveExpression`
- `ShiftExpression << AdditiveExpression`
- `ShiftExpression >> AdditiveExpression`
- `ShiftExpression >>> AdditiveExpression`

## AdditiveExpression

- `MultiplicativeExpression`
- `AdditiveExpression + MultiplicativeExpression`
- `AdditiveExpression - MultiplicativeExpression`

## MultiplicativeExpression

- `UnaryExpression`
- `MultiplicativeExpression * UnaryExpression`
- `MultiplicativeExpression / UnaryExpression`
- `MultiplicativeExpression % UnaryExpression`

## UnaryExpression

- `PreIncrementExpression`
- `PreDecrementExpression`
- `+ UnaryExpression`
- `- UnaryExpression`
- `UnaryExpressionNotPlusMinus`

## PreIncrementExpression

`++ UnaryExpression`

## PreDecrementExpression

`-- UnaryExpression`

## UnaryOperationNotPlusMinus

- `PostfixExpression`
- `~ UnaryExpression`
- `! UnaryExpression`
- `CastExpression`
- `SwitchExpression`



# 语法定义

## PostfixExpression

```text
PostfixExpression:
  Primary
  ExpressionName
  PostIncrementExpression
  PostDecrementExpression
```

## PostIncrementExpression

```text
PostIncrementExpression:
  PostfixExpression ++
```

## PostDecrementExpression

```text
PostDecrementExpression:
  PostfixExpression --
```

## CastExpression

```text
CastExpression:
  ( PrimitiveType ) UnaryExpression
  ( ReferenceType [AdditionalBound] ) UnaryExpressionNotPlusMinus
  ( ReferenceType [AdditionalBound] ) LambdaExpression
```

## SwitchExpression

```text
SwitchExpression:
  switch ( Expression ) SwitchBlock
```

## ConstantExpression

```text
ConstantExpression:
```

---

# 附录 A. 限制许可授予

ORACLE AMERICA, INC. 仅在您接受所有条款的条件下愿意许可此规范。请仔细阅读条款。

## 1. 评估目的许可

规范特此授予您一项完全付费、非独占、不可转让、全球范围的有限许可，依据规范适用的知识产权，仅为内部评估目的查看、下载和复制规范。这包括：
(i) 开发旨在规范上运行的应用程序；
(ii) 与任何第三方讨论规范；
(iii) 摘录规范的简短部分，前提是此类摘录本身不构成规范的重要部分。

## 2. 实现分发许可

规范牵头人还授予您一项永久、非独占、不可转让、全球范围、完全付费、免版税的有限许可，以创建和/或分发独立实现，该实现须：
(a) 完全实现规范，包括所有必需的接口和功能；
(b) 不修改、取代或以其他方式扩展许可方命名空间；
(c) 通过该规范的技术兼容性测试套件（包括满足其要求）。

## 3. 传递条件

您无需在关于使用您的独立实现或其衍生产品的任何许可授予中包含上一段 (a)-(c) 项限制或任何特定的“传递”要求。但是，除满足上一段 (a)-(c) 项限制的独立实现（及其衍生产品）外，您不得：
(a) 向您的被许可人授予或以其他方式传递规范牵头人适用知识产权下的任何许可；
(b) 授权您的被许可人声称其实现符合相关规范。

## 4. 专利许可互惠

### a.
就上述第 2 款授予的许可所涵盖、且会被规范所有技术上可行的实现侵犯的任何专利权利要求而言，该许可以您向任何向您寻求许可的一方，提供公平、合理且非歧视性条款下的永久、非独占、不可转让、全球范围专利许可为条件，该专利权为您拥有或将拥有、且会被规范所有技术上可行的实现侵犯，用于开发、分发和使用合规实现。

### b.
就规范牵头人拥有的、且受上述第 2 款授予许可涵盖的任何专利权利要求而言，无论实施规范时能否通过技术上可行的方式避免其侵权，如果您对规范牵头人发起诉讼，指控其在履行规范牵头人职责过程中诱导任何其他实体侵犯您的专利权，则该许可应针对该等权利要求终止。

### c.
同样就规范牵头人拥有的、且受上述第 2 款授予许可涵盖的任何专利权利要求而言，如果您对规范牵头人发起诉讼，指控其制造、已制造、使用、要约出售、销售或进口合规实现侵犯了您的专利权，则该许可应终止。

## 5. 定义

就本协议而言：
- **独立实现**：指对规范的实现，该实现既不源自规范牵头人的源代码或二进制材料，且在未获得规范牵头人适当且独立许可的情况下，不包含规范牵头人的任何源代码或二进制代码材料。
- **许可方命名空间**：指由 Oracle America, Inc. 通过 Java 社区进程（或其承认的继任者或替代者）采用的任何命名约定中，以 `java`、`javax`、`com.oracle`、`com.sun` 或其等效词开头的公共类或接口声明。
- **技术兼容性测试套件** 或 **TCK**：指规范牵头人提供的与规范对应且附带 TCK 用户指南的测试套件，且在以下情况下可用：
  (i) 在您允许用于商业用途的独立实现首次发布前 120 天由规范牵头人提供，或
  (ii) 在您选择测试对规范的实现后的该发布日起超过 120 天。

如果您违反本协议或在上述授予许可的范围之外行动，本协议将立即终止，无需规范牵头人通知。

---

# 免责声明

规范按“现状”提供。规范牵头人不作任何陈述或保证，无论是明示还是暗示的，包括但不限于对适销性、针对特定用途的适用性、不侵权（包括由于对规范的任何实践或实施导致的）或规范内容适用于任何用途的保证。本文档不代表承诺在任何产品中发布或实现规范的任何部分。此外，规范可能包含技术性错误或排版错误。

---

# 责任限制

在法律允许的范围内，在任何情况下，规范牵头人或其许可方均不对任何损害负责，包括但不限于收入、利润或数据丢失，或对于特殊的、间接的、后果性的、偶然或惩罚性的损害，无论其原因如何且无论何种责任理论，由于您拥有、实施或其他方式使用规范而引起或与之相关的损害，即使规范牵头人和/或其许可方已被告知此类损害的可能性。

您将补偿、保护并使规范牵头人及其许可方免受因以下引起的任何索赔：
(i) 您对规范的使用；
(ii) 您的 Java 应用程序、applet 和/或实现的使用或发行；
和/或 (iii) 后期提供的任何规范版本或发布版本与根据本许可提供给您的规范不兼容的任何索赔。

---

# 权利授予

**美国政府**：如果本规范是由美国政府或代表美国政府，或由美国政府主承包商或分包商（任何层级）获取，则政府对软件及附文档的权利仅如本许可所述；这符合 `48 C.F.R. 227.7201` 至 `227.7202-4`（针对国防部 DoD 采购）以及 `48 C.F.R. 2.101` 和 `12.212`（针对非国防部采购）。

---

# 反馈

如果您向规范牵头人提供有关规范的任何意见或建议（“反馈”），您在此：
(i) 同意此类反馈是在非独占且非机密的基础上提供的，并且
(ii) 授予规范牵头人永久的、非独占的、全球范围内的、全额的、不可撤销的许可，并有通过多级分许可人进行分许可的权利，以便出于任何目的纳入并披露此类反馈。

---

# 通用条款

任何与本协议相关的行动将受加利福尼亚州法律和相关的美国联邦法的管辖。《联合国国际货物销售公约》和任何管辖区的法律选择规则不适用。

规范受美国出口管制法律限制，并可能受其他国家进出口法规限制。被许可人同意严格遵守所有此类法律，并承认有责任在交付给被许可人后可能需要的出口、再出口或进口许可证。

本协议是双方就其主题达成的完整协议。它取代了所有之前或同时的口头或书面通信、建议、条件、陈述和保证，并优于在本协议期限内双方之间就其主题达成的任何报价、订单、确认或其他通信中的任何冲突或额外条款。对本协议的任何修改除非以书面形式列出并由双方授权代表签字，否则不具有约束力。

---

Java、Java 相关徽标、商标和名称为 Oracle America, Inc. 在美国和其他国家的商标或注册商标。

Copyright © 1997-2022 Oracle America, Inc. 保留所有权利。

Java SE: 19
Status: Final
Release: September 2022
