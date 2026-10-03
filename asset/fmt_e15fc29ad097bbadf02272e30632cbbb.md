
```typescript
type Adder = (a: number, b: number) => number;
let foo: Adder = (a, b) => {
  a = "hello"; // Error：不能将 `string` 赋值给 `number`
  return a + b;
}
```

这是一个类型从左到右的示例。

如果你为回调参数创建一个函数，相同的赋值风格类型推断也有效。毕竟，一个参数 -> 参数只是变量赋值的另一种形式。

```typescript
type Adder = (a: number, b: number) => number;
function iTakeAdder(adder: Adder) {
  return adder(1, 2);
}
takeAdder((a, b) => {
  // a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
  return a + b;
})
```

## 结构化

这些简单的规则在存在结构化（对象字面量创建）时也有效。例如在在情况下，`foo` 的类型被推断为 `{a:number, b:number}`

```typescript
let foo = {
  a: 123,
  b: 456
};
// foo.a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

同样对于数组：

```typescript
const bar = [1,2,3];
// bar[0] = "hello"; // Would error：不能将 `string` 赋值给 `number`
```

当然，还有任何嵌套：

```typescript
let foo = {
  bar: [1, 3, 4]
}
foo.bar[0] = 'hello'; // Would error：不能将 `string` 赋值给 `number`
```

## 解构

当然，它们也适用于解构，包括对象：

```typescript
let foo = {
  a: 123,
  b: 456
}
let {a} = foo;
// a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

以及数组：

```typescript
const bar = [1,2,3];
let [a, b] = bar;
// a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

注意，你仍然需要显式地标注你想要，但 `getJSON<T>` 的签名 `(config) => Promise<T>` 为你节省了一些击键：

```typescript
type LoadUsersResponse = {
  users: {
    name: string;
    email: string;
  }[];
}

function loadUsers() {
  return getJSON<LoadUsersResponse>({ url: 'https://example.com/users' });
}
```

```typescript
declare function require(name: string): any;
const something = require('something') as TypeOfSomething;
```

这只是一个示例；如果你正在考虑使用这些 `require` 类型定义，你不需要，因为：

- 1. 它已经存在于 `node.d.ts` 中：你可以使用 `npm install @types/node --save-dev` 进行安装。

- 2. 你应该考虑为你的库使用类型定义，例如对于 jquery 使用 `npm install @types/jquery --save-dev` 而不是使用 `require`。

## 设计模式：便利性泛型

之前的 `require<T>` 示例是有意为了说明一个事实：在类型安全方面，使用*一次*的泛型并不比类型断言更好。尽管如此，它们为你的 API 提供了`便利性`。

示例是一个加载 JSON 响应的函数。它返回一个*你传入的任何类型*的 Promise：

```typescript
const getJSON = <T>(config: {
  url: string,
  headers?: { [key: string]: string },
}):Promise<T> => {
  const fetchConfig = {
    method: 'GET',
    'Accept': 'application/json',
    'Content-Type': 'application/json',
    ...(config.headers || {})
  };
  return fetch(config.url, fetchConfig)
    .then<T>(response => response.json());
}
```

注意，你仍然需要显式地标注你想要，但 `getJSON<T>` 的签名 `(config) => Promise<T>` 为你节省了一些击键：

```typescript
type LoadUsersResponse = {
  users: {
    name: string;
    email: string;
  }[];
}

function loadUsers() {
  return getJSON<LoadUsersResponse>({ url: 'https://example.com/users' });
}
```

此外，将 `Promise<T>` 作为返回值绝对比 `Promise<any>` 等替代方案更好。

## TypeScript 中的类型推断

TypeScript 可以根据几个简单的规则推断（然后检查）变量的类型。因为这些规则很简单，你可以训练你的大脑来识别安全/不安全的代码（这和我我的同事发生得很快）。

> “类型流”只是我在脑海中想象类型信息流的方式。

## 定义

变量的类型是通过定义推断的。

```typescript
let foo = 123; // foo 是一个 `number`
let bar = "Hello"; // bar 是一个 `string`
foo = bar; // Error：不能将 `string` 赋值给 `number`
```

这是一个类型从右向左的示例。

## 返回

返回类型通过 `return` 语句推断，例如，以下函数被推断为返回数字。

```typescript
function add(a: number, b: number) {
  return a + b;
}
```

这是一个类型流到底部的示例。

## 赋值

函数参数/返回的类型也可以通过赋值推断，例如，在这里说 `foo` 是一个 `Adder`，这使得 `a` 和 `b` 的类型推断为 `number`。

```typescript
type Adder = (a: number, b: number) => number;
let foo: Adder = (a, b) => a + b;
```

这一事实可以通过下面的代码得到证明，它会像你预期的那样抛出错误：

```typescript
type Adder = (a: number, b: number) => number;
let foo: Adder = (a, b) => {
  a = "hello"; // Error：不能将 `string` 赋值给 `number`
  return a + b;
}
```

这是一个类型从左到右的示例。

如果你为回调参数创建一个函数，相同的赋值风格类型推断也有效。毕竟，一个参数 -> 参数只是变量赋值的另一种形式。

```typescript
type Adder = (a: number, b: number) => number;
function iTakeAdder(adder: Adder) {
  return adder(1, 2);
}
takeAdder((a, b) => {
  // a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
  return a + b;
})
```

## 结构化

这些简单的规则在存在结构化（对象字面量创建）时也有效。例如在在情况下，`foo` 的类型被推断为 `{a:number, b:number}`

```typescript
let foo = {
  a: 123,
  b: 456
};
// foo.a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

同样对于数组：

```typescript
const bar = [1,2,3];
// bar[0] = "hello"; // Would error：不能将 `string` 赋值给 `number`
```

当然，还有任何嵌套：

```typescript
let foo = {
  bar: [1, 3, 4]
}
foo.bar[0] = 'hello'; // Would error：不能将 `string` 赋值给 `number`
```

## 解构

当然，它们也适用于解构，包括对象：

```typescript
let foo = {
  a: 123,
  b: 456
}
let {a} = foo;
// a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

以及数组：

```typescript
const bar = [1,2,3];
let [a, b] = bar;
// a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

由此类 `Base` 和 `Child` 组成的复杂类型的兼容性，取决于 `Base` 和 `Child` 在相似场景下的位置，这由变性（variance）驱动。

- 协变（covariant）：仅在相同方向。

- 逆变（contravariant）：仅在相反方向。

- 双变（bivariant，也称为 both）：同时是协变和逆变。

- 不变（Invariant）：如果类型不完全相同，则不兼容。

> 注意：在存在可变数据的 JavaScript 中，对于完全微妙的系统类型，不变是唯一的有效选项。但正如前面提到的，便利性迫使我们做出未知的选择。

# Functions

在比较两个函数时，有一些细微之处需要考虑。

# Return 类型

协变：返回类型必须包含足够的数据。

```typescript
/** Type Hierarchy */
interface Point2D { x: number; y: number; }
interface Point3D { x: number; y: number; z: number; }

/** Two sample functions */
let iMakePoint2D = (): Point2D => ({ x: 0, y: 0 });
let iMakePoint3D = (): Point3D => ({ x: 0, y: 0, z: 0 });

/** Assignment */
let iMakePoint2D = iMakePoint3D; // Okay
let iMakePoint3D = iMakePoint2D; // ERROR: Point2D is not assignable to Point3D
```

# Number of arguments

参数较少是可以接受的（即：函数可以选择忽略额外的参数）。毕竟，你被保证在调用时至少有足够数量参数。

```typescript
iTakeSomethingAndPassITANErr
    = (x: Error, data: any) => void => { /* do something */ };
```

```typescript
iTakeSomethingAndPassITANErr() => null // Okay
iTakeSomethingAndPassITANErr(err) => null // Okay
iTakeSomethingAndPassITANErr(err, data) => null // Okay
```

```typescript
// ERROR: function may be called with `more` not being passed in
iTakeSomethingAndPassITANErr(err, data, more) => null; // ERROR
```

# Optional and Rest Parameters

可选参数（预定义数量）和剩余参数（任意数量的参数）是兼容的，同样：是为了便利性。

```typescript
let foo = (x:number, y: number) => { /* do something */ }
let bar = (x?, y?: number) => { /* do something */ }
let bas = (...args: number[]) => { /* do something */ }
```

```typescript
foo = bar = bas;
bas = bar = foo;
```

> 注意：可选（在我们的示例 `bar` 中）和非可选（在我们的示例 `foo` 中）只有在 `strictNullChecks` 为 false 时才兼容。

# Types of arguments

双变（bivari）：设计用于支持常见的事件处理场景。

```typescript
/** Event Hierarchy */
interface Event { timestamp: number; }
interface MouseEvent extends Event { x: number; y: number }
interface KeyEvent extends Event { keyCode: number }
```

```typescript
/** Sample event listener */
enum EventType { Mouse, Keyboard }
function addEventListener(eventType: EventType, handler: (n: Event) => void) {
  /* ... */
}
```

```typescript
// Unsound, but useful and common. 由于函数参数比较是双变的，所以可以工作
addEventListener(EventType.Mouse, (e: MouseEvent) => console.log(e.x + " , " + e.y));
```

```typescript
// 在存在健全性时不理想的替代方案
addEventListener(EventType.Mouse, (e: Event) => console.log((e as MouseEvent).x + " , " + e.y));
addEventListener(EventType.Mouse, (<e: Event) => void)((e: MouseEvent) => console.log(e.x + " , " + e.y)));
```

```typescript
// 仍然不允许（清晰的错误）。对完全不兼容的类型强制类型安全
addEventListener(EventType.Mouse, (e: number) => console.log(e));
```

`Array` 使 `Array<Child>` 可赋值给 `ArrayBase`（协变），因为函数是兼容的。`Array` 协变要求所有 `Array<Child>` 函数都能赋值给 `ArrayBase`，例如 `push(t:child)` 可以赋值给 `push(t:Base)`，这是通过函数参数的变性实现的。

这对于来自其他语言的人来说可能会令人困惑，他们可能期望以下代码报错，但在 TypeScript 中不会：

```typescript
/** Type Hierarchy */
interface Point2D { x: number; y: number; }
interface Point3D { x: number; y: number; z: number; }
```

```typescript
/** Two sample functions */
let iTakePoint2D = (point: Point2D) => { /* do something */ }
let iTakePoint3D = (point: Point3D) => { /* do something */ };
```
