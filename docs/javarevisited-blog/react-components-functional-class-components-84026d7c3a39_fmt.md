
# React：组件、功能和类组件

> 原文：<https://medium.com/javarevisited/react-components-functional-class-components-84026d7c3a39?source=collection_archive---------1----------------------->

当我们研究`React`时，首先出现在画面中的是组件。当我开始主要学习`React`时，我温习了我的基础知识`JavaScript`，当我们听到`React`时，它感觉有些诱人，所以我浏览了一些文档，观看了一些`YouTube`教程，并尝试开始学习`React`。我接触的第一样东西是组件，让我们来看看组件的细节。

[![](img/0de2befe2bb35d9e86fb167b596a2a0e.png)](https://javarevisited.blogspot.com/2020/10/top-5-websites-to-learn-react-for-free.html#axzz6nTA4tfFM)

[杰克逊·苏](https://unsplash.com/@jacksonsophat?utm_source=medium&utm_medium=referral)在 [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral) 上的照片

## 真正的分量是什么意思？

组件是独立的、可重用的代码。它们的作用与`JavaScript`函数相同，但是独立工作并返回`HTML`。它们接受任意输入（称为“道具”），并返回描述屏幕上应该出现什么的`React`元素。

它们是可重用的，可以嵌套在其他组件中。因此，它创建了树状结构，其中您的主组件与一个小的独立组件相连接，并将所有组件组合在一起，我们得到最终的输出，并且在我们的默认`React`应用`index.js`中，我们导入`app.js`作为主节点。

### 有一件重要的事情要记住，那就是：

组件名必须以大写字母开头。例如`<Component>`、`<Instance>`等。原因：小写用于`<div>`、`<body>`、`<h1>`等标签。

**在`React`中，我们主要有两种类型的组件：**

1. 功能组件。
2. 类组件。

## 功能组件

在`React`中工作时更经常使用功能组件。这些只是简单的`JavaScript`函数。我们可以通过编写一个`JavaScript`函数在`React`中创建一个功能组件。在功能组件中，返回值是呈现（显示）到`DOM`树的`JSX`代码。

**例如：**

1.

```
function Democomponent() {
  return <h2>This is function!</h2>;
}
export default Democomponent;
```

2.

```
const Democomponent=()=>
{
    return <h1>This is function!</h1>;
}
export default Democomponent;
```

## 类组件

类组件比功能组件稍微复杂一些。类组件可以相互协作。我们可以将数据从一个类组件传递到其他类组件。我们可以使用`JavaScript ES6`类在`React`中创建基于类的组件。

**例如：**

```
import React from "react"; 
class App extends React.Component {
  render() {
    return <h1>This is component</h1>;
  }
}
export default App;
```

> 在旧的`React`代码库中，通常主要使用类组件。但是在引入了钩子之后，现在建议和钩子一起使用函数组件，这是在`React 16.8`中添加的。

## 功能组件与类组件

- 一个功能组件接受`props`作为参数并返回一个`React`元素，而一个类组件需要你从`React.Component`扩展并创建一个呈现函数，该函数返回一个`React`元素。

- 功能组件是无状态组件，因为它们只是接受数据并以某种形式显示它们，它们主要负责呈现`UI`；而类组件也称为有状态组件，因为它们实现逻辑和状态。

在这里，我让你熟悉了`React`和如何安装。

> 谢谢！对于阅读，我希望你已经学到了新的东西，并喜欢它。关注更多此类信息丰富的博客，并给予👏并做评论，它给了我写更多博客的鼓励，快乐学习！！祝你愉快！！！
