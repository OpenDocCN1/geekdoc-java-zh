
# JavaScript 原型与继承

JavaScript 中的所有对象都包含一个`__proto__`成员。这个成员在旧浏览器中通常无法访问（有时文档将这个魔法属性称为`[[prototype]]`）。它的目标是：如果在查找过程中在对象上未找到属性（例如`obj.property`），则会在`obj.__proto__.property`中查找。如果仍然找不到，则继续查找`obj.__proto__.__proto__.property`，直到找到它或最后一个`__proto__`本身为`null`。这解释了为什么说 JavaScript 原生支持原型继承。如下所示，你可以在 Chrome 控制台或 Node.js 中运行：

```javascript
foo = {}

// 在 foo 及其 foo.__proto__ 上设置
foo.bar = 123;
foo.__proto__.bar = 456;

console.log(foo.bar); // 123
delete foo.bar; // 从对象中移除
console.log(foo.bar); // 456
delete foo.__proto__.bar; // 从 __proto__ 中移除
console.log(foo.bar); // undefined
```

很好你理解了`__proto__`。另一个有用信息是，JavaScript 中的所有函数都有一个名为`prototype`的属性，它包含一个指向函数的`constructor`成员。如下所示：

```javascript
function Foo() {}
console.log(Foo.prototype); // {} 即它存在且未定义
console.log(Foo.prototype.constructor === Foo); // 包含一个指向函数的 'constructor' 成员
```

现在让我们看看`new`对调用函数内部`this`的影响。基本上，调用函数内部的`this`将指向函数返回的新创建的对象。如果你在函数内部修改了属性，很容易看到：

```javascript
function Foo() {
  this.bar = 123;
}

// 使用 new 运算符调用
var newFoo = new Foo();
console.log(newFoo.bar); // 123
```

你需要知道的另一点是，对函数调用`new`会将函数的原型赋值给返回的新创建对象的`__proto__`。这是你可以运行以完全理解的代码：

```javascript
function Foo() {}
var foo = new Foo();
console.log(foo.__proto__ === Foo.prototype); // True!
```

# 箭头函数

除了简洁的语法外，只有当你打算将函数交给别人调用时，你才需要使用箭头函数（fat arrow）。效果如下：

```javascript
var growOld = person.growOld;
// 然后之后其他人调用了它：
growOld();
```

如果你是自己调用它，即：

```javascript
person.growOld();
```

那么这将是正确的调用上下文（在本例中为`person`）。

## 提示：箭头函数的危险

事实上，如果你希望将`this`作为调用上下文，你不应该使用箭头函数。在像 jquery、underscore、mocha 等库的回调中就是这种情况。如果文档中提到了关于`this`的函数，那么你可能应该使用普通函数而不是箭头函数。同样地，如果你计划使用参数，请不要使用箭头函数。

## 提示：在某些使用该库中使用箭头函数

许多库都会这样做，例如 jQuery 迭代器（一个示例 [http://api.jquery.com/jquery.each/)）将使用`this`来向你传递当前正在迭代的对象。在这种情况下，如果你想访问库传递的`this`以及周围上下文，只需像在没有箭头函数的情况下那样使用临时变量`_self`即可。

```javascript
let _self = this;
something.each(function() {
  console.log(_self); // 词作用域的值
  console.log(this); // 库传递的值
});
```

## 提示：箭头函数与继承

如果你将实例方法作为箭头函数，那么它将位于`this`上。由于只有一个`this`，此类函数无法参与对`super`的调用（`super`仅对原型成员有效）。你可以通过在子类中重写它之前创建一个该方法的副本来轻松绕过这个问题。

```typescript
Adder {
  constructor(public a: number) {
    // 这个函数现在可以安全地传递
    add = (b: number): number => {
      return this.a + b;
    }
  }
}
class ExtendedAdder extends Adder {
  // 在创建自己的方法之前创建一个父类方法的副本
  private superAdd = this.add;
  // 现在创建我们的重写方法
  add = (b: number): number => {
    return this.superAdd(b);
  }
}
```

## 提示：快速对象返回

有时，你需要一个仅返回简单对象字面量的函数。然而，像这样的：

```javascript
// 错误的实现方法
var foo = () => {
bar: 123
};
```

在 JavaScript 运行时会被解析为包含一个 JavaScript 标签（Label）的块（由于 JavaScript 规范的原因）。

> 如果这听起来不通，你也会从 TypeScript 得到“unused label”（未使用的标签）的编译错误。标签是一个旧的（且大多不再使用的）JavaScript 特性，作为一名经验丰富的开发者，你可以忽略这种糟糕的 GOTO。

你可以通过用`()`包围对象字面量来修复它：

```javascript
// 正确
var foo = () => ({
  bar: 123
});
```

# 剩余参数 (Rest Parameters)

剩余参数（最后一个参数用`...argumentName`表示）允许你在函数中快速接受多个参数并以数组的形式获取它们。下面的示例所示：

```javascript
function iTakeAll(first, second, ...allOthers) {
  console.log(allOthers);
}
iTakeAll('foo', 'bar'); // []
iTakeAll('foo', 'bar', 'bas', 'qux'); // ['bas','qux']
```

剩余参数可用于任何函数，无论是函数、箭头函数还是类成员。

# JavaScript 中的变量是函数作用域的

这与许多语言（C# / Java 等）不同，在那些语言中变量是块作用域的。如果你将块作用域思维带入 JavaScript，你会预期下面的代码打印`123`，但实际上它会打印`456`：

```javascript
var foo = 123;
if (true) {
    var foo = 456;
}
console.log(foo); // 456
```

这是因为这没有创建一个新的变量作用域。变量`foo`在`if`块内部和外部是同一个变量。这是 JavaScript 编程中常见的错误来源。这就是为什么 TypeScript (以及 ES6 引入) 引入了`let`关键字，允许你定义具有真正块作用域的变量。如果你使用`let`代替`var`，你将获得一个与作用域外定义的可能不同的唯一元素。相同的示例使用`let`演示如下：

```javascript
let foo = 123;
if (true) {
    let foo = 456;
}
console.log(foo); // 123
```

`let`另一个可以让你避免错误的地方是循环。

```javascript
var index = 0;
var array = [1, 2, 3];
for (let index = 0; index < array.length; index++) {
    console.log(array[index]);
}
console.log(index); // 0
```

诚恳地说，我们认为尽可能使用`let`更好，因为它能为新开发者和现有的多语言开发者带来更少的意外。

既然提到了它，我们想演示函数在 JavaScript 中创建一个新的变量作用域。考虑以下：

```javascript
var foo = 123;
function test() {
  var foo = 456;
}
test();
console.log(foo); // 123
```

这种行为正如你预期的。如果没有这一点，在 JavaScript 中编写代码将非常困难。

# 生成的 JS

生成的 JS 是转译器的输出。（注意：此部分的 OCR 文本是重复且格式奇怪的，我已根据提供的代码片段清理了逻辑流）。

## Switch

`switch`语句用于处理多个条件。

```javascript
foo = 123;
if (true) {
  const foo = 456; // 允许，因为它是新变量限于此 `if` 块
}
```

# 深度不可变性

在保护变量引用的方面，`const`配合对象字面量也同样有效：

```javascript
const foo = { bar: 123 };
foo = { bar: 456 }; // 错误：赋值表达式的左侧可以是常量
```

然而，它仍然允许对对象的子属性进行修改，如下所示：

```javascript
const foo = { bar: 123 };
foo.bar = 456; // 允许！
console.log(foo); // { bar: 456 }
```

出于这个原因，我建议将`const`与原始类型或不可变数据结构配合。

# 解构

TypeScript 支持以下形式的解构（Destructuring，字面意思命名为 de-structuring，即拆分结构）：

- 对象解构
- 数组解构

很容易将解构想成是结构化的逆过程。JavaScript 中的结构化方法是对象字面量：

```javascript
var foo = {
  bar: {
    bas: 123
  }
};
```

如果没有 JavaScript 内置的优秀结构化支持，动态创建新对象确实会非常繁琐。解构为从结构中提取数据带来了同样水平的便利性。

## 对象解构

解构之所以有用，是因为它允许你在单行代码中完成原本需要多行代码的操作。考虑以下情况：

```javascript
var rect = { x: 10, y: 0, width: 15, height: 20 };

// 解构赋值
var {x, y, width, height} = rect;
console.log(x, y, width, height); // 0,10,15,20

rect.x = 10;
({x, y, width, height} = rect); // 使用圆括号赋值给现有变量

console.log(x, y, width, height); // 10,10,15,20
```

在这里，在没有解构的情况下，你必须从`rect`中一个一个地取出`x`,`y`,`width`,`height`。

要将提取的变量赋值给新的变量名，你可以这样做如下：

```javascript
const obj = {"some property": "some value"};
```

```javascript
// 解构
const {"some property": someProperty} = obj;
console.log(someProperty === "some value"); // true
```

此外，你还可以使用解构从结构中获取深层数据。如下例所示：

```javascript
var foo = { bar: { bas: 123 } };
var {bar: {bas}} = foo; // 实际上相当于 var bar = foo.bar.bas;
```

## 带有剩余参数的对象解构

你可以使用带有剩余参数的解构从对象中提取任意数量的元素，并获取剩余元素的*对象*。

```javascript
var {w, ...remaining} = {w: 1, x: 2, y: 3, z: 4};
console.log(w, remaining); // 1, 2, {y:3,z:4}
```

另一种常见情况也是忽略某些属性。例如：

```javascript
// 示例函数
function goto(point2D: {x: number, y: number}) {
// 想象某些可能会导致崩溃的代码
// 如果你传入了一个
// 更多所需项的对象
}
// 从某处获取某些 point3D
const point3D = {x: 1, y: 2, z: 3};
/** 使用剩余参数移除额外属性的巧妙用法 */
const {z, ...point2D} = point3D;
goto(point2D);
```

## 数组解构

一个常见的编程问题：“如何在不使用第三方变量的情况下交换两个变量？” TypeScript 的解决方案是：

```javascript
var x = 1, y = 2;
[x, y] = [y, x];
console.log(x, y); // 2, 1
```

注意，数组解构实际上是编译器为你执行了`[]`, `[1]`, 等操作。无法保证这些值一定存在。

## 带有剩余参数的数组解构

你可以使用带有剩余参数的数组解构从数组中提取任意数量的元素，并获取剩余元素的数组。

```javascript
var [x, y, ...remaining] = [1, 2, 3, 4];
console.log(x, y, remaining); // 1, 2, [3,4]
```

## 带有忽略的数组解构

你可以通过简单地在赋值的左侧留空（即`,`）来忽略任何索引。例如：

```javascript
var [x, , ...remaining] = [1, 2, 3, 4];
console.log(x, remaining); // 1, [3,4]
```

## JS 生成

针对非 ES6 目标的 JavaScript 生成仅涉及创建临时变量，就像你在没有原生语言支持解构的情况下必须自己做的那样，例如：

```javascript
var x = 1, y = 2;
[x, y] = [y, x];
console.log(x, y); // 2, 1

// 变为 /
var x = 1, y = 2;
_a = y;
y = x;
x = _a;
```

## 总结

解构让从结构中获取数据变得非常方便。

# 迭代器 (Iterators)

迭代器本身并不是 TypeScript 的 ES6 特性，它是面向对象编程语言中常用的行为设计模式。通常，它是实现以下接口的对象：

```typescript
interface Iterator<T> {
  next(value?: any): IteratorResult<T>;
  return(value?: any): IteratorResult<T>;
  throw(value?: any): IteratorResult<T>;
}
```

该接口允许从属于对象的某个集合或序列中检索值。

`IteratorResult`仅仅是一个值 + 完成状态的对：

```typescript
interface IteratorResult<T> {
  done: boolean;
  value: T;
}
```

假设有一个帧的对象，它包含了该帧由哪些组件列表。通过`Iterator`接口，可以如下所示从该帧对象获取组件：
