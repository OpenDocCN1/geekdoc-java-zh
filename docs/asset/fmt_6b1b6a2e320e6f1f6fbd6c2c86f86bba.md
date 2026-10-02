
# TypeScript 深度解析 (TypeScript Deep Dive)

Basarat Ali Syed

# 目录

- 引言 1.1
- 入门 1.2
- 为什么选择 TypeScript 1.2.1
- JavaScript 1.3
- 相等 1.3.1
- 引用 1.3.2
- Null vs Undefined 1.3.3
- this 1.3.4
- 闭包 1.3.5
- 数字 1.3.6
- 未来的 JavaScript 与现在 1.4
- 类 1.4.1
- 类的输出 1.4.1.1
- 箭头函数 1.4.2
- 剩余参数 1.4.3
- let 1.4.4
- const 1.4.5
- 解构 1.4.6
- 展开运算符 1.4.7
- for...of 1.4.8
- 迭代器 1.4.9
- 模板字符串 1.4.10
- Promise 1.4.11
- 生成器 1.4.12
- Async Wait 1.4.13
- 项目 1.5
- 编译上下文 1.5.1
- tsconfig.json 1.5.1.1
- 哪些文件？ 1.5.1.2
- 声明空间 1.5
- 模块 1.5.3
- 文件模块细节 1.5.3.1
- globals.d.ts 1.5.3.2
- 命名空间 1.5.4
- 动态导入表达式 1.5.5
- Node.js 快速上手 1.6
- 浏览器快速上手 1.7
- TypeScript 的类型系统 1.8
- JS 迁移指南 1.8.1
- @types 1.8.2
- 环境声明 1.8.3
- 声明文件 1.8.3.1
- 变量 1.8.3.2
- 接口 1.8.4
- 枚举 1.8.5
- lib.d.ts 1.8.6
- 函数 1.8.7
- 可调用 1.8.8
- 类型断言 1.8.9
- 新鲜度 1.8.10
- 类型守卫 1.8.11
- 字面量类型 1.8.12
- 只读 1.8.13
- 泛型 1.8.14
- 类型推断 1.8.15
- 类型兼容性 1.8.16
- Never 类型 1.8.17
- 辨析联合联合 1.8.18
- 索引签名 1.8.19
- 移动类型 1.8.20
- 异常处理 1.8.21
- 混入 (Mixins) 1.8.22
- JSX 1.9
- React 1.9.1
- 非 React JSX 1.9.2
- 选项 1.10
- noImplicitAny 1.10.1
- strictNullChecks 1.10.2
- 测试 1.11
- Jest 1.11.1
- 技巧 (TIPs) 1.12
- 基于字符串的枚举 1.12.1
- 命名类型 1.12.2
- 有状态函数 1.12.3
- Bind 是坏的 1.12.4
- 柯化 1.12.5
- 类型实例化 1.12.6
- 懒性对象字面量初始化 1.12.7
- 类是有用的 1.12.8
- 避免使用 Export Default 1.12.9
- 限制属性 Setter 1.12.10
- null 是坏的 1.12.11
- outFile 注意 1.12.12
- JQuery 技巧 1.12.13
- 静态构造函数 1.12.14
- 单例模式 1.12.15
- 函数参数 1.12.16
- 真值 (Truthy) 1.12.17
- 构建切换开关 1.12.18
- 桶导出 (Barrel) 1.12.19
- 创建数组 1.12.20
- 类型安全事件发射器 1.12.21
- 风格指南 1.13
- 常见错误 1.14
- TypeScript 编译器原理 1.15
- 程序 (Program) 1.15.1
- 抽象语法树 (AST) 1.15.2
- 技巧：访问子节点 1.15.2.1
- 技巧：SyntaxKind 枚举 1.15.2.2
- 杂项 (Trivia) 1.15.2.3
- 扫描器 (Scanner) 1.15.3
- 解析器 (Parser) 1.15.4
- 解析器函数 1.15.4.1
- 绑定器 (Binder) 1.15.5
- 绑定器函数 1.15.5.1
- 绑定器声明 1.15.5.2
- 绑定器容器 1.15.5.3
- 绑定器符号 1.15.5.4
- 绑定器错误报告 1.15.5.5
- 检查器 (Checker) 1.15.6
- 检查器错误报告 1.15.6.2
- 发射器 (Emitter) 1.15.1

# 为什么选择 TypeScript

TypeScript 有两个主要目标：

- 为 JavaScript 提供可选的类型系统。
- 将未来 JavaScript 版本的计划特性引入当前的 JavaScript 引擎中。

下面将阐述实现这些目标的动机。

# TypeScript 类型系统

你可能在想**“为什么要给 JavaScript 添加类型呢”**。

类型已被证明能够提高代码质量和可读性。大型团队（Google、Microsoft、Facebook）不断得出这一结论。具体来说：

- 类型可以增加你在重构时的敏捷性。*让编译器捕获错误比在运行时失败要好。*
- 类型是你可以拥有的最佳文档形式之一。*函数签名是一个定理，而函数体是证明。*

然而，类型往往会显得不必要的繁琐。TypeScript 非常注重尽可能地降低入门门槛。以下是实现方式：

## 你的 JavaScript 就是 TypeScript

TypeScript 为你的 JavaScript 代码提供编译时安全保障。考虑到它的名字，这并不意外。棒的地方在于类型是完全可选的。你的 JavaScript 代码 `.js` 文件可以重命名为 `.ts` 文件，TypeScript 仍然会返回与原始 JavaScript 文件等效的有效 `.js` 文件。TypeScript *刻意* 严格作为 JavaScript 的超集，并带有可选的类型检查。

## 类型可以是隐式的

TypeScript 会尝试尽可能推断类型信息，以便在代码开发过程中以最小的生产力代价为你提供安全性。例如，在下面的示例中，TypeScript 将知道 `foo` 的类型为 `number`，并在第二行所示报错：

```typescript
foo = 123;
foo = '456'; // Error: 不能将 `string` 赋值给 `number`

// foo 是数字还是字符串？
```

这种类型推断是有充分理由的。如果你像示例中那样操作，那么在代码的其他部分，你无法确定 `foo` 是数字还是字符串。这类问题在大型多文件库中经常出现。我们稍后将深入探讨推断规则。

## 类型可以是显式的

正如我们之前提到的，TypeScript 会尽可能安全地进行推断，但你仍然可以使用注解来：

1. 帮助编译器，更重要的是为阅读你代码的下一个开发者（那可能是未来的你！）编写文档。
2. 强制让编译器看到的正是你所认为它应该看到的。也就是说，你对代码的理解与对代码的算法分析（由编译器完成）相匹配。

TypeScript 使用了其他可选注解语言中流行的后置类型注解（例如 ActionScript 和 F#）。

```typescript
var foo: number = 123;
```

所以如果你执行了错误操作，编译器会报错，例如：

```typescript
var foo: number = '123'; // Error: 不能将 `string` 赋值给 `number`
```

我们将在后面的章节中详细讨论 TypeScript 支持的所有注解语法的细节。

## 类型是结构化的

在某些语言中（特别是基于命名的语言）中，静态类型会导致不必要的繁琐，因为你你知道代码会运行良好，但语言语义迫使你复制内容。这就是为什么像 C# 的 automapper 对 C# 至关重要的原因。在 TypeScript 中，因为我们真的想让 JavaScript 开发者轻松上手且认知负担最小化，类型是结构化的。这意味着鸭子类型（duck typing）是一种原生语言结构。考虑以下示例。`itPoint2D` 函数将接受任何包含它预期的所有内容（`x` 和 `y`）的对象：

```typescript
interface Point2D {
  x: number;
  y: number;
}
interface Point3D {
  x: number;
  y: number;
  z: number;
}
var point2D: Point2D = { x: 0, y: 10 };
var point3D: Point3D = { x: 0, y: 10, z: 20 };
function itPoint2D(point: Point2D) { /* 做一些什么 */ }
itPoint2D(point2D); // 匹配允许
itPoint2D(point3D); // 额外信息允许
itPoint2D({ x: 0 }); // Error: 缺少信息 'y'
```

## 类型错误不会阻止 JavaScript 的输出

为了方便你将 JavaScript 代码迁移到 TypeScript，即使存在编译错误，TypeScript 默认也会尽可能输出有效的 JavaScript（emit）。例如：

```typescript
var foo = 123;
fooo = '456'; // Error: 不能将 'string' 赋值给 'number'
```

将输出以下 js：

```javascript
var foo = 123;
fooo = '456';
```

你可以增量地将 JavaScript 代码升级为 TypeScript。这与许多其他语言编译器的做法完全不同，这也是迁移到 TypeScript 的另一个原因。

## 类型可以是环境的

TypeScript 的一个主要设计目标是让你能够在 TypeScript 中安全方便地使用现有的 JavaScript 库。TypeScript 通过声明（declaration）来实现这一点。TypeScript 提供了一个灵活的尺度，取决于你想在声明中投入多少精力，你投入的精力越多，获得的类型安全 + 代码智能性就越高。请注意，大多数流行的 JavaScript 库的定义已经由 DefinitelyTyped 社区为你写好了，因此对于大多数用途：

1. 定义文件已经存在。
2. 或者至少，你有一系列经过大量审查的 TypeScript 声明模板可用。

关于你如何编写自己的声明文件的快速示例，考虑一个简单的 jquery 例子。默认情况下（正如对良好的 JS 代码的预期），TypeScript 期望你在使用变量之前的某处声明它（即使用 `var`）：

```javascript
$('.awesome').show(); // Error: 找不到名称 '$'
```

作为快速修复，你可以告诉 TypeScript 确实有一个名为 `$` 的东西：

```typescript
declare var $: {
  (selector:string): any;
}
$('.awesome').show(); // 好的！
```

如果你想在这个基础定义的基础上提供更多信息以保护你免受错误：

```typescript
declare var $: {
  (selector:string): any;
}
$('.awesome').show(); // 好的！
$(123).show(); // Error: selector 需要是字符串
```

在你了解更多 TypeScript（例如 `interface` 和 `any`）之后，我们稍后详细讨论为现有 JavaScript 创建 TypeScript 定义的细节。

## 未来的 JavaScript => 现在

TypeScript 提供了若干计划在 ES6 中用于当前 JavaScript 引擎（目前仅支持 ES5 等）的功能。TypeScript 团队正在积极添加这些功能，这个列表将随着时间的推移变得越来越，我们将在专门的章节中介绍。但这里有一个类（class）的示例：

```typescript
class Point {
    constructor(public x: number, public y: number) {
    }
    add(point: Point) {
        return this.x + point.y;
    }
}

var p1 = new Point(0, 10);
var p2 = new Point(10, 20);
var p3 = p1.add(p2); // { x: 10, y: 30 }
```

以及可爱的箭头函数：

```javascript
var inc = x => x+1;
```

## 总结

在本节中，我们为你提供了 TypeScript 的动机和设计目标。现在我们可以进入具体的细节了。

# 让 JavaScript 更好

TypeScript 会尝试保护你免受 JavaScript 中从未生效的部分（所以你不需要记住这些内容）：

```javascript
[] + []; // JavaScript 会给你 ""（这没什么意义），TypeScript 会报错

// 其他在 JavaScript 中没有意义的内容
// 它们不会产生运行时错误（导致调试困难）
// 但 TypeScript 会产生编译错误（使调试变得必要）

{} + []; // JS : 0, TS Error
[] + {}; // JS : "[object Object]", TS Error
{} + {}; // JS : NaN 或 [object Object][object Object]，取决于浏览器，TS Error

"hello" - 1; // JS : NaN, TS Error

function add(a,b) {
  return
  a + b; // JS : undefined, TS Error 检测到不可达代码
}
```
