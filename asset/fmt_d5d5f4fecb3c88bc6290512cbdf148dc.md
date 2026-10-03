
```javascript
import fs = require('fs');

// 一个不错的初始尝试……但并不正确
function loadJSON(filename: string, cb: (error: Error, data: any) => void) {
  fs.readFile(filename, function (err, data) {
    if (err) cb(err);
    else cb(null, JSON.parse(data));
  });
}

// 加载无效 json
loadJSON('invalid.json', function (err, data) {
  // 这段代码永远不会执行
  if (err) console.log('bad.json error', err.message);
  else console.log(data);
});
```

修复此问题的一种朴素尝试是在下面的示例所示将 `JSON.parse` 封装在 `try catch` 中：

```javascript
import fs = require('fs');

// 一个较好的尝试……但仍然不正确
function loadJSON(filename: string, cb: (error: Error) => void) {
  fs.readFile(filename, function (err, data) {
    if (err) {
      cb(err);
    }
    else {
      try {
        cb(null, JSON.parse(data));
      } catch (err) {
        cb(err);
      }
    }
  });
}

// 加载无效 json
loadJSON('invalid.json', function (err, data) {
  if (err) console.log('bad.json error', err.message);
  else console.log(data);
});
```

这段代码中存在一个微妙的 bug。如果回调函数 (`cb`) 而不是 `JSON.parse` 抛出错误，由于我们将其封装在 `try / catch` 中，`catch` 块会执行，我们再次调用了回调，即回调被调用了两次！这在下面的示例中得到了证明：

```javascript
import fs = require('fs');

function loadJSON(filename: string, cb: (error: Error) => void) {
  fs.readFile(filename, function (err, data) {
    if (err) {
      cb(err);
    } else {
      try {
        cb(null, JSON.parse(data));
      } catch (err) {
        cb(err);
      }
    }
  });
}

// 一个良好的文件但一个错误的回调……被再次调用！
loadJSON('good.json', function (err, data) {
  console.log('our callback called');

  if (err) {
    console.log('Error:', err.message);
  } else {
    // 通过尝试访问未定义变量的属性来模拟错误
    var foo;
    // 以下代码将抛出 'Error: Cannot read property 'bar' of undefined'
    console.log(foo);
  }
});
```

```javascript
Create a rejected promise
Promise.reject(new Error('something bad happened'))
  .then((res) => {
    console.log(res); // not called
    return 456;
  })
  .catch((err) => {
    console.log(err.message); // something bad happened
    return 123;
  })
  .then((res) => {
    console.log(res); // 123
  })
```

- 在 `then`（或 `catch`）中抛出的任何同步错误会导致返回的 promise 失败：

```javascript
Promise.resolve(123)
  .then((res) => {
    throw new Error('something bad happened'); // throw a synchronous error
    return 456;
  })
  .then((res) => {
    console.log(res); // never called
    return Promise.resolve(789);
  })
  .catch((err) => {
    console.log(err.message); // something bad happened
  })
```

- 对于给定的错误，只有相关的（最近的尾部）`catch` 会被调用（因为 `catch` 会启动一个新的 promise 链）。

```javascript
Promise.resolve(123)
.then((res) => {
    throw new Error('something bad happened'); // throw a synchronous error
    return 456;
})
.catch((err) => {
    console.log('first catch: ' + err.message); // something bad happened
    return 123;
})
.then((res) => {
    console.log(res); // 123
    return Promise.resolve(789);
})
.catch((err) => {
    console.log('second catch: ' + err.message); // never called
})
```

- 只有在前面的链中发生错误时，`catch` 才会被调用：

```javascript
Promise.resolve(123)
.then((res) => {
    return 456;
})
.catch((err) => {
    console.log("HERE"); // never called
})
```

事实是：

- 错误会跳转到尾部的 `catch`（并跳过任何中间的 `then` 调用）
- 同步错误也会被任何尾部的 `catch` 捕获

这实际上为我们提供了一种异步编程范式，比原始回调允许更好的错误处理。更多内容见下文。

## TypeScript 与 promises

TypeScript 的强大之处在于它理解值在 promise 链中的流转过程：

```typescript
Promise.resolve(123)
.then((res) => {
  // res 被推断为 `number` 类型
  return true;
})
.then((res) => {
  // res 被推断为 `boolean` 类型
});
```

当然，它也能理解可能返回 promise 的函数解包：

```typescript
function iReturnPromiseAfter1Second(): Promise<string> {
  return new Promise((resolve) => {
    setTimeout(() => resolve("Hello world!"), 1000);
  });
}

Promise.resolve(123)
.then((res) => {
  // res 被推断为 `number` 类型
  return iReturnPromiseAfter1Second(); // 我们返回了 `Promise<string>`
})
.then((res) => {
  // res 被推断为 `string` 类型
  console.log(res); // Hello world!
});
```

## 将回调样式转换为返回 promise

- 如果发生错误，则 `reject`；
- 如果一切正常，则 `resolve`。

例如，让我们封装 `fs.readFile`：

```typescript
import fs = require('fs');
function readFileAsync(filename: string): Promise<any> {
  return new Promise((resolve, reject) => {
    fs.readFile(filename, (err,result) => {
      if (err) reject(err);
      else resolve(result);
    });
  });
}
```

## 重新审视 JSON 示例

现在让我们重新审视 `loadJSON` 示例，并重写一个使用 promises 的异步版本。我们做的只是将文件内容读取为 promise，然后将其解析为 JSON 即可。下面的示例所示：

```typescript
function loadJSONAsync(filename: string): Promise<any> {
  return readFileSync(filename) // 使用我们刚刚写的函数
  .then(function (res) {
    return JSON.parse(res);
  });
}
```

用法（注意它与本节开头介绍的原始同步版本有多相似）：

```javascript
// 良好的文件
loadJSONAsync('good.json')
  .then(function (val) { console.log(val); })
  .catch(function (err) {
    console.log('good.json error', err.message); // never called
  })

// 不存在的 json 文件
.then(function () {
  return loadJSONAsync('absent.json');
})
  .then(function (val) { console.log(val); }) // never called
  .catch(function (err) {
    console.log('absent.json error', err.message);
  })

// 无效的 json 文件
.then(function () {
  return loadJSONAsync('invalid.json');
})
  .then(function (val) { console.log(val); }) // never called
  .catch(function (err) {
    console.log('bad.json error', err.message);
  })
```

该函数之所以更简单，是因为由于 `readFile` (异步) + `JSON.parse` (同步) 的整合是由 promise 链完成的。我们没有机会在 `try/catch` 中封装它。

## 控制流

我们已经见过通过 promises 执行一系列异步任务。然而，你可能想运行一系列异步任务并对这些任务的结果进行操作。Promise 提供了 `all` 函数来编写这些任务的解析值数组。下面展示了链式调用以及并行执行：

```javascript
// 从服务器加载某些数据的异步函数
function loadItem(id: number): Promise<void> {
  return new Promise((resolve) => {
    console.log('loading', id);
    setTimeout(() => resolve({ id }), 1000);
  });
}

// 链式调用
let item1, item2;
loadItem(1)
  .then((res) => {
    item1 = res;
    return loadItem(2);
  })
  .then((res) => {
    item2 = res;
    console.log('done');
  }); // 总耗约 2s

// 并行
Promise.all([loadItem(1), loadItem(2)])
  .then((res) => {
    [item1, item2] = res;
    console.log('done');
  }); // 总耗约 1s
```

有时，你想运行一系列异步任务，但只要其中任何一个任务完成，你就获得你需要的结果。`Promise.race` 为这种场景提供了一个函数：

```javascript
task1 = new Promise(resolve, reject) {
  setTimeout(() => resolve('one'), 1000);
});
task2 = new Promise(resolve, reject) {
  setTimeout(() => resolve('two'), 2000);
});

Promise.race([task1, task2]).then(function(value) {
  console.log(value); // "one"
});
```

## 将回调函数转换为 promise

最可靠的方法是手动处理。例如，将 `setTimeout` 转换为 promisified 函数非常简单：

```javascript
const delay = (ms: number) => new Promise(res => setTimeout(() => res(ms), ms));
```

注意 NodeJS 中有一个方便的函数可以这一点：

```javascript
/* 示例 */
import fs = require('fs');
import util = require('util');
const readFile = util.promisify(fs.readFile);
```

## Generators

> 注意：你无法以有意义的方式在 TypeScript 中使用 generators（ES5 正在中）。但这很快就会改变。

`function*` 是创建 *generator 函数* 的语法。调用 generator 函数返回一个 *generator 对象*。generator 对象遵循 *iterator* 接口（即 `next`、`return` 和 `throw` 函数）。generator 函数背后的两个动机：

## 懒性迭代器

Generator 函数可以创建懒性迭代器，例如，以下函数按需返回无限整数列表：

```javascript
function* infiniteSequence() {
  var i = 0;
  while (true) {
    yield i++;
  }
}

var iterator = infiniteSequence();
while (true) {
  console.log(iterator.next()); // { value: xxxx, done: false } 永远
}
```

当然，如果迭代器结束，你会得到 `{ done: true }` 的结果，如下：

```javascript
function* idMaker() {
  let index = 0;
  while(index < 3) {
    yield index++;
  }
}

let gen = idMaker();

console.log(gen.next()); // { value: 0, done: false }
console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { done: true }
```

## 外部控制执行

这是 generators 真正令人兴奋的部分。它本质上允许函数暂停执行，并将剩余执行的控制权（命运）交给调用者。

generator 函数在调用它时并不执行。它只是创建了一个 generator 对象。考虑以下带有示例执行的例子：
