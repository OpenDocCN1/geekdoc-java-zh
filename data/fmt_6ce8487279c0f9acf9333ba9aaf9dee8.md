
TypeScript 编译器中还有几个额外文件，为这些许多关键部分提供了工具，我们接下来将介绍它们。

## 文件：Utilities

`core.ts` : `coreAllocator: ObjectAllocator` : 是定义为全局单例的变量。

- `let objectAllocator: ObjectAllocator` 提供了 `getNodeConstructor` 的定义（Nodes 在我们查看 parser / AST 时涵盖）、`getSymbolConstructor` 的定义（Symbols 在 binder 中涵盖）、`getConstructor` 的定义（Types 在 checker 中涵盖）、`getSignatureConstructor` 的定义（Signatures 是索引、调用和构造签名）。

## 文件：关键数据结构

`types.ts` 包含了整个编译器中使用的关键数据结构和接口。这里是几个键的示例：

- `SyntaxKind` AST 节点类型由 `SyntaxKind` 枚举标识。
- `TypeChecker` 这是由 `TypeChecker` 提供的接口。
- `CompilerHost` Program 用于与系统交互。
- `Node` 一个 AST 节点。

## 文件：System

`system.ts` TypeScript 编译器与操作系统的所有交互都通过一个系统接口进行。该接口及其实现（TypeScript 和 Node）都定义在 `system.ts` 中。你可以将其认为是**运行环境** (OE)。

现在你已经有了主要文件的概述，我们可以查看 Program 的概念

## Program

定义在 `program.ts` 中。编译上下文（我们之前涵盖过的概念）在 TypeScript 编译器中表示为 Program。它由 SourceFiles 和编译选项组成。

## CompilerHost 的用法

它与 OE 的交互机制：

```
Program -uses- -> CompilerHost -uses-> System
```

拥有 CompilerHost 作为间接点的原因是它允许针对 Program 的需求进行更精细的调整。

## SourceFile

程序提供了一个 API 来获取 `SourceFiles[]`; 每个 SourceFile 都是包含在 Program 中的顶层节点。

- `SyntaxKind.SourceFile`
- `interface SourceFile`

## Node

抽象语法树 (AST) 的基本构建模块。通常 Node 代表语言中的非终结符；然而，某些终结符保留在树中，例如标识符和字面量。

两个键构成了节点的文档。`SyntaxKind` 标识其类型，其接口：

- `TextRange` 成员标识节点的起始和结束位置。
- `parent?` Node 节点的父节点。

其他 Node 标记和修饰符。

## AST 提示：访问节点

有一个工具函数 `ts.forEach` 允许你访问 AST 中任何 Node 的子节点。

这里的源码片段演示了它是如何工作的：

```typescript
export function forChild<T>(node: Node, cbNode: (node: Node) => T, cbNodeArray?:

  nodes: Node[])) => T): T {

  if (!node) {

    return;

  }

  switch (node.kind) {

    case SyntaxKind.BinaryExpression:

      return visitNode(node, (<BinaryExpression>node).left) ||

             visitNode(cbNode, (<BinaryExpression>node).operatorToken) ||

             visitNode(cbNode, (<BinaryExpression>node).right);

    case SyntaxKind.IfStatement:

      return visitNode(cbNode, (<IfStatement>node).expression) ||

             visitNode(cbNode, (<IfStatement>node).thenStatement) ||

             visitNode(cbNode, (<IfStatement>node).elseStatement);

    // .... 更多
```

基本上它根据 `node.kind` 并据此假设节点提供的接口，并在子节点上调用 `cbNode`。请注意，此函数不会对所有节点执行 `visitNode`（例如 `SyntaxKind.SemicolonToken`）。如果你想访问 AST 中节点的所有子节点，使用 Node 的 `.getChildren` 成员函数。

例如，这里有一个打印节点详细 AST 的函数：

```javascript
function printAllChildren(node: ts.Node, depth = 0) {

  console.log(new Array(depth+1).join('----')), ts.syntaxKindName(node.kind), node.pos, node.end);

  depth++;

  node.getChildren().forEach(c=> printAllChildren(c, depth));

}
```

当我们进一步讨论解析器时，我们将看到该函数的示例用法。

# AST 技巧：SyntaxKind

`SyntaxKind` 被定义为一个 `const enum`，这是一个示例：

```typescript
export const enum SyntaxKind {

  Unknown,

  EndOfFileToken,

  SingleLineCommentTrivia,

  // ... 还有更多

}
```

它是一个 `const enum`（一个我们之前涵盖过的概念），这样它就会被`内联`（例如，`ts.SyntaxKind.EndOfFileToken` 变成 `1`），当我们在处理 AST 时就不会产生解引用的开销。然而，编译器使用 `--preserveConstEnums` 标志进行编译，以确保该枚举`在运行时仍然是可用的`。在 JavaScript 中，如果你需要，仍然可以使用 `ts.SyntaxKind.EndOfFileToken`。此外，你还可以使用以下函数将这些枚举成员转换为显示字符串：

```typescript
export function syntaxKindName(kind: ts.SyntaxKind) {

  return (<any>).SyntaxKind[kind];

}
```

# Trivia（元数据）

Trivia（被称为重要信息，尽管它是微不足道的）代表源文本中对于理解代码逻辑大部分不重要的部分。例如：空白字符、注释，甚至是冲突标记。Trivia 不存储在 AST 中（以保持其轻量级）。但是，可以使用一些 `ts.*` APIs 按需获取它们。

在向你展示它们之前，你需要理解以下内容：

# Trivia 所有权

- 一个 token 拥有它在同一行内、紧随其后的下一个 token 之前的所有 trivia。
- 该行之后的任何注释都与随后的 token 关联。

对于文件中的前导和后缀注释：

- 源文件中的第一个 token 获得所有的初始 trivia。
- 文件中的最后一段 trivia 被附加到文件结束 token（end-of-file token）上，该 token 否则宽度为零。

# Trivia APIs

对于大多数基础用途，注释是最“有趣的”的 Trivia。属于某个 Node 的注释可以通过以下函数获取：

| 函数 |  |
| :--- | :--- |
| `ts.getLeadingCommentRanges` | 给定源文本和该文本中的位置，返回给定位置后第一个换行符到该 token 之间的注释范围（可能配合 `ts.Node.getFullStart` 使用最有效）。 |
| `ts.getTrailingCommentRanges` | 给定源文本和该文本中的位置，返回直到给定位置后第一个换行符的注释范围（可能配合 `ts.Node.getEnd` 使用最有效）。 |

作为一个示例，源文件的这部分：

```typescript
debugger;//hello"

//bye

/*hi*/function
```

`leadingCommentRanges` 函数将返回 `//bye` 和 `/*hi*/`。相应地，在 `debugger` 语句末尾调用 `trailingCommentRanges` 将提取 `/*hello*/` 注释。

# Token Start / Full Start

节点存有所谓的“token start”和“full start”。

- Token Start：更自然的版本，即 token 开始所在的位置。
- Full Start：扫描器自上一个重要 token 开始扫描的点。

AST 节点拥有 `getStart` 和 `getFullStart` 的 API。在以下示例中：

```typescript
debugger;/*hello*/

//bye

/*hi*/function
```

对于函数，token start 在这里，而 full start 在 `/*hello*/`。注意，full start 包含了之前的节点所拥有的 trivia。

# Scanner

TypeScript 扫描器的源代码完全位于 `scanner.ts`。解析器内部控制它将源代码转换为 AST。这是预期的结果：

```
源代码 -- 扫描器 -> Token 流 -> AST
```

# 解析器的用法

在 `parser.ts` 中创建了一个单例扫描器以避免重复创建扫描器的开销。该扫描器由解析器通过 `initState` 函数初始化。这是解析器中实际代码的简化版本，演示了这一概念：

```typescript
code/compiler/scanner/runScanner.ts

import * as ts from "typescript";

// TypeScript 是一个单例扫描器

const scanner = ts.createScanner(ts.ScriptTarget.Latest, true);

// 使用 initState() 初始化

function initializeState(text: string) {

  scanner.setText(text);

  scanner.onError((message: ts.Diagnostic, length: number) => {

    console.error(message);

  });

  scanner.setScriptTarget(ts.ScriptTarget.ES5);

  scanner.setLanguageVariant(ts.LanguageVariant.Standard);

}

// 使用示例

initializeState(`

var foo = 123;`);

// 开始扫描

var token = scanner.scan();

while (token != ts.SyntaxKind.EndOfFileToken) {

  console.log(ts.formatSyntaxKind(token));

  token = scanner.scan();

}
```

这将打印：

```
VarKeyword

Identifier

FirstLiteralToken

SemicolonToken
```

# Scanner 状态

在调用 `scan` 后，扫描器更新其本地状态（扫描中的位置、当前 token）。扫描器提供了一系列实用函数来获取当前状态。在下面的示例中，我们创建一个扫描器并使用它来识别 token 及其在代码中的位置。

```typescript
code/compiler/scanner/runScannerWithPosition.ts

// 使用示例

initializeState(`

var foo = 123;`);

// 开始扫描

var token = scanner.scan();

while (token != ts.SyntaxKind.EndOfFileToken) {

  let currentToken = ts.formatSyntaxKind(token);

  let tokenStart = scanner.getStart();

  token = scanner.scan();

  let tokenEnd = scanner.getStart();

  console.log(currentToken, tokenStart, tokenEnd);

}
```

这将打印：

```
VarKeyword 0 3

Identifier 3 7

FirstAssignment 7 9

FirstLiteralToken 9 13

SemicolonToken 13 14
```

# 独立扫描器

尽管 TypeScript 解析器有一个单例扫描器，你仍然可以使用 `createScanner` 创建一个独立的扫描器并使用其 `setText` 来扫描文件中的不同点。

# 解析器

TypeScript 解析器的源代码完全位于 `parser.ts`。解析器内部控制它将源代码转换为 AST。这是预期的结果回顾：

```
源代码扫描器 -> Token 流 -> AST
```

解析器被实现为单例（类似于扫描器，不需要重新创建它）。它实际上被实现为命名空间 `Parser`，包含了解析器的状态变量以及单例扫描器。如前所述，它包含了 `const scanner`。解析器函数管理这个扫描器。

# Program 的用法

解析器由 Program 直接驱动（间接地通过我们之前提到的 `CompilerHost`）。基本上这是简化的调用栈：

```
Program ->

CompilerHost.getSourceFile ->

(global parser.ts).createSourceFile ->

Parser.parseSourceFile
```

# 示例用法

在我们深入解析器内部之前，有一个示例代码使用 TypeScript 解析器获取源文件的 AST（使用 `ts.createSourceFile`），然后打印它。

```typescript
code/compiler/parser/runParser.ts
```

```typescript
import * as ts from "typescript";

function printAllChildren(node: ts.Node, depth = 0) {

  console.log(new Array(depth + 1).join('-'), ts.formatSyntaxKind(node.kind), node.pos, node.end);

  depth++;

  node.getChildren().forEach(c => printAllChildren(c, depth));

}

var sourceCode = `

var foo = 123;`;

var sourceFile = ts.createSourceFile('foo.ts', sourceCode, ts.ScriptTarget.ES5, true);

printAllChildren(sourceFile);
```

这将打印以下内容：

```
SourceFile 0 14

--- SyntaxList 0 14

---- VariableDeclarationList 0 14

----- VariableDeclaration 0 13

------VarKeyword 0 3

------SyntaxList 3 13

-------VariableDeclaration 3 13

--------Identifier 3 7

----------FirstAssignment 7 9

----------FirstLiteralToken 9 13

---- SemicolonToken 13 14

--- EndOfFileToken 14 14
```
