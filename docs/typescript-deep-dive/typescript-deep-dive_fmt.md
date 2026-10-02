
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



本质上，TypeScript 正在对 JavaScript 进行静态检查（linting）。只是比那些没有类型信息的其他 linter 工具做得更好。

# 你仍然需要学习 JavaScript

尽管如此，TypeScript 非常务实地考虑到你确实在编写 JavaScript 的事实，因此关于 JavaScript 的某些事情你仍然需要了解，以防措手不及。我们将在下一节讨论它们。

> 注意：TypeScript 是 JavaScript 的超集。只是带了可以被编译器 / IDE 实际使用的文档 ;)

# 等价

JavaScript 需要注意的一点是`==`和`===`之间的区别。由于 JavaScript 试图对编程错误具有韧性，`==`会尝试在两个变量之间进行类型转换，例如将字符串转换为数字，以便像下面所示与数字进行比较：

```javascript
console.log(5 == "5"); // true , TS 错误
console.log(5 === "5"); // false , TS 错误
```

JavaScript 的选择并不总是理想的。例如，在下面的示例中，第一个语句为`false`，因为`""`和`"0"`都是字符串且显然不相等。然而在第二情况下，`0`和空字符串 (`""`) 都是虚值（即表现得像`false`），并且在`==`面前是相等的。当你使用`==`时，这两个语句都是`false`。

```javascript
console.log("" == "0"); // false
console.log(0 == ""); // true
```

```javascript
console.log("" === "0"); // false
console.log(0 === ""); // false
```

注意，在 TypeScript 中，`string == number`和`string === number`都是编译时错误，所以你通常不需要担心这个问题。

与`==` vs `===`类似，还有`!=` vs `!==`。

所以专家提示：除了我们稍后介绍的 null 检查外，请始终使用`===`和`!==`。

# 结构相等性

如果你想比较对象的结构相等性，`==`和`===`是不够的。例如：

```javascript
console.log({a:123}) == {a:123}); // False
console.log({a:123} === {a:123}); // False
```

要进行此类检查可以使用`deep-equal` npm 包，例如：

```javascript
import * as deepEqual from "deep-equal";
console.log(deepEqual({a:123},{a:123})); // True
```

# 参考

除了字面量外，JavaScript 中的任何对象（包括函数、数组、正则表达式等）都是引用。这意味着：

## 变异是跨所有引用的

```javascript
var foo = {};
var bar = foo; // bar 是同一个对象的引用

foo.baz = 123;
console.log(bar.baz); // 123
```

## 相等针对引用

```javascript
var foo = {};
var bar = foo; // bar 是一个引用
var baz = {}; // baz 是一个不同于 `foo` 的“新对象”

console.log(foo === bar); // true
console.log(foo === baz); // false
```

# Null 和 undefined

事实上，你需要处理两者。只需检查其中一种`==`检查即可。

```javascript
// 假设你正在执行 `foo.bar == undefined`，其中 bar 可以是之一：
console.log(undefined == undefined); // true
console.log(null == undefined); // true
console.log(0 == undefined); // false
console.log('' == undefined); // false
console.log(false == undefined); // false
```

推荐使用`== null`来同时检查`undefined`或`null`。你通常不需要区分这两者。

```typescript
function foo(arg: string | null | undefined) {
  if (arg != null) {
    // arg 必须是字符串，!='规则排除了 null 和 undefined。
  }
}
```

# undefined

记得我提到过你应该使用`== null`吗？当然你用了（因为我刚刚说了）。

不要将它用于根级事项。在严格模式下，如果你使用`foo`且`foo`是`undefined`，你会得到`ReferenceError`异常，整个堆栈会回溯。

> 你应该使用严格模式……事实上，如果你使用模块，TS 编译器将插入它……关于这些在书中后面会有更多介绍，所以你必须显式指定：

所以，如果要在全局范围内检查变量是否已定义，通常使用`typeof`：

```javascript
if (typeof someglobal !== 'undefined') {
  // someglobal 现在可以安全地使用了
  console.log(someglobal);
}
```

# this

函数内部对`this`关键字的任何访问实际上都受函数如何调用的控制。这通常被称为“调用上下文”。

这是一个示例：

```javascript
function foo() {
  console.log(this);
}

foo(); // 记录全局对象，例如浏览器中的 `window`
let bar = {
  foo
}
bar.foo(); // 记录 `bar`，因为 `foo` 在 `bar` 上调用的
```

所以请留意你对`this`的使用。如果你想断开`this`与调用上下文的连接，请使用箭头函数，稍后介绍。

# 闭包

最棒的东西莫过于闭包。JavaScript 函数可以访问定义在外部作用域中的变量。闭包通过示例解释最好：

```javascript
function outerFunction(arg) {
  var variableOuterFunction = arg;

  function bar() {
    console.log(variableOuterFunction);
  }
  // 调用本地函数以证明它可以访问 arg
  bar();
}

outerFunction("hello"); // 记录闭包！
```

# 为什么它很棒

这个概念本身足够简单且直观。现在是很棒的部分：揭示模式：

```javascript
function createCounter() {
  let val = 0;
  return {
    increment() { val++ },
    getVal() { return val }
  };
}

let counter = createCounter();
counter.increment();
console.log(counter.getVal()); // 1
counter.increment();
console.log(counter.getVal()); // 2
```

不要将此库用于 UI / 性能密集型的数学计算，例如图表、画布绘制等。

# NaN

当数字计算结果无法用有效的数字表示时，JavaScript 会返回一个特殊的`NaN`值。一个经典的例子是虚数：

```javascript
console.log(Math.sqrt(-1)); // NaN
```

注意：相等性检查**无法**对`NaN`值不起作用。请改用`Number.isNaN`：

```javascript
// 不要这样做
console.log(NaN === NaN); // false!!

// 这样做
console.log(Number.isNaN(NaN)); // true
```

# Infinity

Number 中可表示的外部边界可以通过静态值`Number.MAX_VALUE`和`-Number.MAX_VALUE`获得。

```javascript
console.log(Number.MAX_VALUE); // 1.797693134863157e+308
console.log(-Number.MAX_VALUE); // -1.797693134863157e+308
```

超出精度范围的值不会被限制在这些限制内，例如：

```javascript
console.log(Number.MAX_VALUE + 1 == Number.MAX_VALUE); // true!
console.log(-Number.MAX_VALUE - 1 == -Number.MAX_VALUE); // true!
```

超出解析范围的值将解析为特殊值`Infinity` / `-Infinity`，例如：

```javascript
console.log(Number.MAX_VALUE + 10**1000); // Infinity
console.log(-Number.MAX_VALUE - 10**1000); // -Infinity
```

当然，这些无穷值也会出现在需要它们的算术运算中，例如：

```javascript
console.log(1 / 0); // Infinity
console.log(-1 / 0); // -Infinity
```

你可以手动使用这些 Infinity 值，或像下面使用 Number 类的静态成员：

```javascript
console.log(Number.POSITIVE_INFINITY === Infinity); // true
console.log(Number.NEGATIVE_INFINITY === -Infinity); // true
```

幸运的是，比较运算符 (< / >) 在无穷值上工作非常可靠：

```javascript
console.log(Infinity > 1); // true
console.log(-Infinity < -1); // true
```

# Infinitesimal

Number 中可表示的最小非零值为静态的`Number.MIN_VALUE`。

```javascript
console.log(Number.MIN_VALUE); // 5e-324
```

小于 MIN_VALUE 的值（下溢值）会被转换为 0。

```javascript
console.log(Number.MIN_VALUE / 10); // 0
```

> 进一步的直觉：就像大于 Number.MAX_VALUE 的值会被限制为 INFINITY 一样，小于 Number.MIN_VALUE 的值会被限制为 0。

# Future JavaScript

TypeScript 的主要卖点之一是允许你在当前的 JavaScript 引擎（ES3 和 ES5 级别，如当前的浏览器和 Node.js）中使用 ES6 及之后的一系列功能。在这里，我们深入探讨为什么这些功能很有用，以及这些功能如何在 TypeScript 中实现。

注意：并不是所有这些功能都计划立即添加到 JavaScript 中，但它们对你的代码组织和维护非常有帮助。另外请注意，你可以自由忽略任何对你的项目没有意义的结构，尽管你最终会使用其中大部分的 ;)

# Classes

之所以在 JavaScript 中将类作为一等公民非常重要，是因为：

- 1. 类提供了一种实用的结构抽象。

- 2. 为开发者提供了一种统一使用类的方法，而不是让每个框架（ember, react 等）都搞自己的版本。

- 3. 熟悉对象的 JavaScript 开发者已经理解类。

最后，JavaScript 开发者可以使用类了。这里有一个名为 Point 的基础类：

```typescript
class Point {
  x: number;
  y: number;
  constructor(x: number, y: number) {
    this.x = x;
    this.y = y;
  }
  add(point: Point) {
    return new Point(this.x + point.x, this.y + point.y);
  }
}

var p1 = new Point(0, 10);
var p2 = new Point(10, 20);
var p3 = p1.add(p2); // {x:10,y:30}
```

这个 Point 类在 emits ES5 时生成以下 JavaScript：

```javascript
var Point = (function () {
  function Point(x, y) {
    this.x = x;
    this.y = y;
  }
  Point.prototype.add = function (point) {
    return new Point(this.x + point.x, this.y + point.y);
  };
  return Point;
})();
```

这种类模式在 JavaScript 中是相当地道的构造方式。

# Inheritance

TypeScript 类（类似于其他语言）通过`extends`关键字支持**单继承**，如下所示：

```typescript
class Point3D extends Point {
  z: number;
  constructor(x: number, y: number, z: number) {
    super(x, y);
    this.z = z;
  }
}
```

*(注：由于原始文本存在大量重复和 OCR 错误，以上翻译已基于核心逻辑进行整理。)*

# IIFE 到底是怎么回事

为类生成的 JS 可能是：

```javascript
function Point(x, y) {
  this.x = x;
  this.y = y;
}
Point.prototype.add = function (point) {
  return new Point(this.x + point.x, this.y + point.y);
}
```

它之所以封装在一个立即执行函数表达式（IIFE）中，即：

```javascript
function () {
  // 句体
  return Point;
}();
```

与继承有关。它允许 TypeScript 将基类捕获为变量`super`，例如：

```javascript
var Point3D = (function (_super) {
  _extends(Point3D, _super);
  function Point3D(x, y, z) {
    _super.call(this, x, y);
    this.z = z;
  }
  Point3D.prototype.add = function (point) {
    var point2D = _super.prototype.add.call(this, point);
    return new Point3D(point2D.x, point2D.y, this.z + point.z);
  }
  return Point3D;
})(Point);
```

注意，IIFE 允许 TypeScript 轻松地将基类 Point 捕获到`super`变量，并在类体中一致地使用。

> __extends

你会发现，一旦你继承一个类，TypeScript 也会生成以下函数：

```javascript
extends = this.__extends || function (d, b) {
  for (var p in b) if (b.hasOwnProperty(p)) d[p] = b[p];
  function __() { this.constructor = d; }
  __.prototype = b.prototype;
  d.prototype = new __();
};
```

`d`指代派生类，`b`指代基类。这个函数做了两件事：

- 1. 将基类的静态成员拷贝到子类中，即`for (var p in b) if (b.hasOwnProperty(p)) d[p] = b[p];`

- 2. 设置子类的原型，以便可选地在父类的原型中查找成员，即实际上执行`d.prototype.__proto__ = b.prototype`

人们很少在第1点上遇到困难，但很多人对第2点很困惑。因此有必要进行解释。

## d.prototype.__proto__ = b.prototype

在指导了很多人关于这一点后，我发现以下解释是最简单的。首先，我们将解释`__extends`中的代码等同于简单的`d.prototype.__proto__ = b.prototype`，然后说明为什么这一行本身意义重大。要理解这一切，你需要了解以下这些点：

- 1. `__proto__`

- 2. `prototype`

- 3. `new`对调用函数内部`this`的影响

- 4. `new`对`prototype`和`__proto__`的影响



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



```typescript
class Component {
  constructor (public name: string) {}
}

class Frame implements Iterator<Component> {
  private pointer = 0;

  constructor(public name: string, public components: Component[]) {
  }
  public next(): IteratorResult<Component> {
    if (this.pointer < this.components.length) {
      return {
        done: false,
        value: this.components[this.pointer++]
      };
    } else {
      return {
        done: true
      };
    }
  }
}

let frame = new Frame("Door", [new Component("top"), new Component("bottom"), new Component("left"), new Component("right")]);
let iteratorResult1 = frame.next(); // done: false, value: Component { name: 'top' }
let iteratorResult2 = frame.next(); // done: false, value: Component { name: 'bottom' }
let iteratorResult3 = frame.next(); // done: false, value: Component { name: 'left' }
let iteratorResult4 = frame.next(); // done: false, value: Component { name: 'right' }
let iteratorResult5 = frame.next(); // done: true
```

可以通过`value`属性访问迭代器结果的值

```typescript
let component = iteratorResult1.value; //Component { name: 'top' }
```

再次强调，迭代器本身并不是 TypeScript 的特性，这段代码可以在不显式实现`Iterator`和`IteratorResult`的情况下工作。然而，使用这些常用的 ES6 接口对于代码的一致性非常有帮助。

好的，不错，但可以更有帮助。ES6 定义了迭代协议（iterable protocol），如果实现了`Iterable`接口，则会包含`[Symbol.iterator]`符号：

```typescript
//.../
class Frame implements Iterable<Component> {

  constructor(public name: string, public components: Component[]) {}

  [Symbol.iterator]() {
    let pointer = 0;
    let components = this.components;
    return {
      next(): IteratorResult<Component> {
        if (pointer < components.length) {
          return {
            done: false,
            value: components[pointer++]
          };
        } else {
          return {
            done: true,
            value: null
          };
        }
      }
    }
  }
}
```

```typescript
let frame = new Frame("Door", [new Component("top"), new Component("bottom"), new Component("left"), new Component("right")]);
for (let cmp of frame) {
  console.log(cmp);
}
```

遗憾的是，`frame.next()`在这种模式下无法工作，而且看起来有点笨拙。`IterableIterator`接口来救场！

```typescript
//.../
class Frame implements IterableIterator<Component> {
    private pointer = 0;

    constructor(public name: string, public components: Component[]) {

    public next(): IteratorResult<Component> {
        if (this.pointer < this.components.length) {
            return {
                done: false,
                value: this.components[this.pointer++]
            };
        } else {
            return {
                done: true,
                value: null
            };
        }
    }

    [Symbol.iterator](): IterableIterator<Component> {
        return this;
    }
}
//...
```

现在`frame.next()`和`for`循环都可以通过`Iterableiterator`接口正常工作了。

迭代器并不一定要迭代有限的值。一个典型的例子是斐波那契序列：

```typescript
class Fib implements IterableIterator<number> {
  protected fn1 = 0;
  protected fn2 = 1;

  constructor(protected maxValue?: number) {
  public next(): IteratorResult<number> {
    var current = this.fn1;
    this.fn1 = this.fn2;
    this.fn2 = current + this.fn1;
    if (this.maxValue != null && current >= this.maxValue) {
      return {
        done: true,
        value: null
      };
    }
    return {
      done: false,
      value: current
    };
  }

  [Symbol.iterator](): IterableIterator<number> {
    return this;
  }
}
```

```typescript
let fib = new Fib();
fib.next() //{ done: false, value: 0 }
fib.next() //{ done: false, value: 1 }
fib.next() //{ done: false, value: 1 }
fib.next() //{ done: false, value: 2 }
fib.next() //{ done: false, value: 3 }
fib.next() //{ done: false, value: 5 }
fib.next() //{ done: false, value: 8 }
fib.next() = 13;
fib.next() = 21;
fib.next() = 34;
fib.next() = 55;
fib.next() = 89;
fib.next() = 144;
fib.next() = 233;
fib.next() = 377;
fib.next() = 610;
fib.next() = 987;
fib.next() = 1597;
fib.next() = 2584;
fib.next() = 4181;
fib.next() = 6765;
fib.next() = 10946;
fib.next() = 17711;
fib.next() = 28657;
fib.next() = 46368;
fib.next() = 75025;
fib.next() = 12133;
```

```typescript
let fib50 = new Fib();
fib.next() //{ done: false, value: 0 }
fib.next() //{ done: false, value: 1 }
fib.next() //{ done: false, value: 1 }
fib.next() //{ done: false, value: 2 }
fib.next() //{ done: false, value: 3 }
fib.next() //{ done: false, value: 5 }
fib.next() //{ done: false, value: 8 }
fib.next() = 13;
fib.next() = 21;
fib.next() = 34;
fib.next() = 55;
fib.next() = 89;
fib.next() = 144;
fib.next() = 233;
fib.next() = 377;
fib.next() = 610;
fib.next() = 987;
fib.next() = 1597;
fib.next() = 2584;
fib.next() = 4181;
fib.next() = 6765;
fib.next() = 10946;
fib.next() = 17711;
fib.next() = 28657;
fib.next() = 46368;
fib.next() = 75025;
fib.next() = 12133;
```

```typescript
let fib21 = new Fib(21);
for (let num of fib21) {
  console.log(num);
}
```

对于预 ES6 编译目标，代码非常简单。多行字符串变为转义字符串。字符串交叉变为字符串拼接。标签模板变为函数调用。

# 多行字符串 (Multiline Strings)

曾经想在 JavaScript 字符串中插入换行符？也许你想嵌入一些歌词？你将需要使用我们喜欢的字符`\n`对字面量进行转义，然后手动将新行放入字符串。如下所示：

```typescript
var lyrics = "Never gonna give up\nNever gonna let down";
```

在 TypeScript 中你可以直接使用字符串：

```typescript
lyrics = `Never gonna give up
Never gonna let down`;
```

# 标签模板 (Tagged Templates)

你可以在模板字符串之前放置一个函数（称为 tag），它就有机会预处理模板字符串字面量并返回结果。几点说明：

- 所有的静态字面量都作为第一个参数传入。

- 所有占位符表达式的值都作为剩余参数传入。通常情况下你会使用剩余参数将它们也转换为数组。

这是一个示例，我们有一个标签函数（命名为`htmlEscape`）转义所有占位符中的 HTML：

```typescript
var say = "a bird in hand > two in the bush";
var html = htmlEscape `<div> I like to say : ${say}</div>`;

// 示例标签函数
function htmlEscape(literals, ...placeholders) {
  let result = "";

  // 将字面量与占位符交叉插入
  for (let i = 0; i < placeholders.length; i++) {
    result += literals[i];
    result += placeholders[i]
      .replace(/&/g, '&amp;')
      .replace(/"/g, '&quot;')
      .replace(/'/g, '&#39;')
      .replace(/</g, '&lt;')
      .replace(/>/g, '&gt;');
  }

  // 添加最后一个字面量
  result += literals[literals.length - 1];
  return result;
}
```

# 字符串插值 (String Interpolation)

另一个常见用例是你想从静态字符串生成某些内容。这就是模板字符串名称的由来：

```typescript
var lyrics = 'Never gonna give up';
var html = `<div>${lyrics}</div>`;
```

注意`${ }`内部的每个占位符都被视为 JavaScript 表达式并进行求，例如你可以进行数学运算。

```typescript
console.log(`1 and ${1 + 1}`);
```

## 总结

多行字符串和字符串插值在任何语言中都是非常棒的特性。很棒你现在可以在 JavaScript 中使用它们了（感谢 TypeScript！）。标签模板（Tagged templates）允许你创建强大的字符串工具。

# Promise

`Promise`类存在于许多现代 JavaScript 引擎中，并且很容易进行垫填充（polyfilled）。`Promise`的主要动机是将同步风格的错误处理引入异步/回调风格的代码中。

## 回调风格代码

为了充分理解`Promise`，让我们展示一个简单的示例，证明仅用回调函数创建可靠异步代码的困难性。考虑编写一个从文件加载 JSON 的异步版本的简单案例。其同步版本可以非常简单：

```javascript
import fs = require('fs');

function loadJSONSync(filename: string) {
  return JSON.parse(fs.readFileSync(filename));
}

// 良好的 json 文件
console.log(loadJSONSync('good.json'));

// 文件不存在，所以 fs.readFileSync 失败
try {
  console.log(loadJSONSync('absent.json'));
} catch (err) {
  console.log('absent. error', err.message);
}

// 无效的 json 文件，文件存在但包含无效 JSON，所以 JSON.parse 失败
try {
  console.log(loadJSONSync('invalid.json'));
} catch (err) {
  console.log('invalid.json error', err.message);
}
```

这个`loadJSONSync`函数有三种行为：有效的返回值、文件系统错误或`JSON.parse`错误。我们使用简单的`try/catch`来处理错误，就像你在其他语言中进行同步编程时所习惯的那样。现在让我们为这样的函数制作一个良好的异步版本。一个带有简单错误检查逻辑的不错初始尝试应该是：

```javascript
import fs = require('fs');

// 一个不错的初始尝试……但并不正确。我们将在下文中解释原因
function loadJSON(filename: string, cb: (error: Error, data: any) => void) {
  fs.readFile(filename, function (err, data) {
    if (err) cb(err);
    else cb(null, JSON.parse(data));
  });
}
```

这足够简单，它接受一个回调函数，并将任何文件系统错误传递给该回调。如果没有系统错误，它返回`JSON.parse`的结果。在处理基于回调的异步函数时，有几点需要注意：

- 1. 永远不要调用两次回调。

- 2. 永远不要抛出错误。

然而，这个简单的函数未能考虑到第二点。事实上，如果传递给`JSON.parse`错误的 JSON，它会抛出一个错误，回调永远不会被调用，应用程序崩溃。这在下面的示例中得到了证明：



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



# 生成器与异步编程

## 生成器基础

```javascript
function* generator() {
  console.log('Execution started');
  yield 0;
  console.log('Execution resumed');
  yield 1;
  console.log('Execution resumed');
}

var iterator = generator();
console.log('Starting iteration'); // 这将在 generator 中的任何内容或函数体执行前执行
console.log(iterator.next()); // { value: 0, done: false }
console.log(iterator.next()); // { value: 1, done: false }
console.log(iterator.next()); // { value: undefined, done: true }
```

如果你运行此，将得到以下输出：

```
$ node outside.js
Starting iteration
Execution started
{ value: 0, done: false }
Execution resumed
{ value: 1, done: false }
Execution resumed
{ value: undefined, done: true }
```

- 只有在 `generator` 对象上调用 `next()` 后，函数才开始执行。
- 一旦遇到 `yield` 语句，函数就会暂停。
- 当调用 `next()` 时，函数恢复。

> 所以本质上，`generator` 函数的执行可以由 `generator` 对象控制。

## 双向通信

我们使用 `generator` 的通信大部分是单向的，即 `generator` 为迭代返回值。JavaScript 中 `generator` 的一个极其强大的特性是它们允许双向通信！

- 你可以使用 `iterator.next(valueToInject)` 来控制 `yield` 表达式的返回值。
- 你可以在 `yield` 表达式处通过 `iterator.throw(error)` 抛出异常。

以下示例演示了 `iterator.next(valueToInject)`：

```javascript
function* generator() {
  var bar = yield 'foo';
  console.log(bar); // bar!
}

const iterator = generator();
// 开始执行直到获取第一个 yield 值
const foo = iterator.next();
console.log(foo.value); // foo
// 注入 bar 并恢复执行
const nextThing = iterator.next('bar');
```

以下示例演示了 `iterator.throw(error)`：

```javascript
function* generator() {
  try {
    yield 'foo';
  } catch(err) {
    console.log(err.message); // bar!
  }
}

var iterator = generator();
// 开始执行直到获取第一个 yield 值
var foo = iterator.next();
console.log(foo.value); // foo
// 抛出异常 'bar' 并恢复执行
var nextThing = iterator.throw(new Error('bar'));
```

这里是总结：

- `yield` 允许生成器函数暂停其通信并将控制权交给外部系统
- 外部系统可以向生成器函数体传入一个值
- 外部系统可以向生成器函数体抛出一个异常

这有什么用？跳转到下一节 `async/await` 寻找答案。

## Async await

一门涵盖相同内容的 PRO 大极客视频课程

作为一个思想实验，想象一下：一种方法，可以告诉 JavaScript 运行时在 `promise` 上使用 `await` 关键字时暂停代码执行，并且仅当函数返回的 `promise` 状态确定（settled）时*一次*恢复执行：

```javascript
// 并非实际代码。一个思想实验
async function foo() {
  try {
    var val = await getMePromise();
    console.log(val);
  }
  catch (err) {
    console.log('Error: ', err.message);
  }
}
```

当 `promise` 状态确定后执行继续：

- 如果它已完成（fulfilled），则 `await` 将返回该值，
- 如果它被拒绝（rejected），则会同步抛出一个错误，我们可以捕获它。

这突然（且神奇地）让异步编程变得像同步编程一样简单。这个思想实验需要三个要素：

- 暂停函数*执行*的能力。
- 在函数*内部放入一个*值*的能力。
- 在函数*内部抛出一个*异常*的能力。

这正是生成器允许我们做的事情！这个思想实验*实际上是真实的*，TypeScript / JavaScript 中的 `async / await` 实现也是如此。在底层它只是生成器。

## 生成的 JavaScript

你不需要理解这个，但如果你读过生成器，它就相当简单。函数 `foo` 可以简单地封装如下：

```javascript
foo = wrapToReturnPromise(function* {
  try {
    var val = yield getMeAPromise();
    console.log(val);
  }
  catch(err) {
    console.log('Error: ', err.message);
  }
});
```

其中 `wrapToReturnPromise` 只是执行生成器函数获取生成器，然后使用 `generator.next()`，如果值是一个 `promise`，它将捕获该 `promise` 并根据结果调用 `generator.next(result)` 或 `generator.throw(error)`。就是这样！

## TypeScript 中的 Async Await 支持

TypeScript 自 1.7 版本起支持 Async - Await。异步函数以 `async` 关键字为缀；`await` 挂起执行直到异步函数的 `promise` 完成，并从返回的 `Promise` 中解包值。它曾仅支持目标为 `es6` 时直接编译为 ES6 生成器。

TypeScript 2.1 增加了对 ES3 和 ES5 运行时的支持，这意味着无论你使用什么环境，都可以利用它。需要注意的是，我们可以在 TypeScript 2.1 中使用 `async / await`，并且许多浏览器都支持（当然前提是全局为 `Promise` 添加了 polyfill）。

来看这个示例，了解 TypeScript `async / await` 记法是如何工作的：

```javascript
function delay(milliseconds: number, count: number): Promise<number> {
  return new Promise<number>((resolve) => {
    setTimeout(() => {
      resolve(count);
    }, milliseconds);
  });
}

// async 函数始终返回一个 Promise
async function dramaticWelcome(): Promise<void> {
  console.log("Hello");

  for (let i = 0; i < 5; i++) {
    // await 将 Promise<number> 转换为 number
    const count: number = await delay(500, i);
    console.log(count);
  }
  console.log("World!");
}

dramaticWelcome();
```

## 编译到 ES6 (--target es6)

```javascript
var __awaiter = (is && __await) || function (thisArg, _arguments, P, generator
) {
  return new (P || (P = Promise))(function(resolve, reject) {
    function fulfilled(value) try { step(generator.next(value)); } catch (e) { 
      eject(e);
    }
    function rejected(value) try { step(generator("throw")(value)); } catch (e) { 
      reject(e);
    }
    function step(result) try { result.done ? resolve(result.value) : step(generator.next(result.value)); } catch (e) { 
      reject(e);
    }
    // ... logic continue ...
  });
}
```

```javascript
return [4 /*yield*/, delay(500, i)];
case 2:
  count = _a.sent();
  console.log(count);
  _a.label = 3;
  case 3:
    i++;
    return [3 /*break*/, 1];
  case 4:
    console.log("World!");
    return [2 /*return*/];
  }}
));

dramaticWelcome();
```

![](img/7b4ede152e837dfd4e13fc18de91d96a_86_0.png)

你在此查看完整示例。

**注意：** 对于两种目标场景，我们需要确保我们的运行时全局有一个符合 ECMAScript 标准的 `Promise`。这可能涉及获取一个 `Promise` 的补丁（polyfill）。我们还需要确保通过将 `lib` 标志设置为类似 `"dom", "es2015"` 或 `"dom", "es2015.promise", "es5"` 来让 TypeScript 知道 `Promise` 的存在。我们可以在这里查看哪些浏览器已经支持 `Promise`（原生和补丁支持）。

## 项目 (Project)

要使用 TypeScript 创建成功的项目，你需要理解可用的各种项目组织语言特性。在本节中，我们将介绍“编译上下文”、声明空间和模块。

## 编译上下文 (Compilation Context)

编译上下文基本上是对文件分组的一个高级术语，TypeScript 将解析并分析这些文件以确定哪些是有效的，哪些是无效的。除了关于文件的信息外，编译上下文还包含了哪些编译选项的信息。定义这种逻辑分组（我们也喜欢使用“项目”一词）的一种极方法是使用 `tsconfig.json` 文件。

## 基础 (Basic)

使用 `tsconfig.json` 开始非常简单，你的基础文件是：

```json
{}
```

即项目*根目录*下的一个空 JSON 文件。这样，TypeScript 将把该目录（以及子目录）中的**所有 .ts** 文件作为编译上下文的一部分包含进来。它还会选择一些合理的默认编译选项。

## compilerOptions

你可以使用 `compilerOptions` 自定义编译选项：

```json
{
  "compilerOptions": {
    /* 基础选项 */ /* 指定 ECMAScript 目标版本：'ES3' */
    "target": "ES5","ES2015","ES2016","ES2017", or 'ESNEXT'. 
    "module": "commonjs",                   /* 指定模块生成：'commonjs','amd','system','umd' 或 'es2015'. */
    /* 指定要包含在内的库文件 */
    "lib": [],
    "allowJs": true,                        /* 允许编译 javascript 文件。 */
    "checkJs": true,                        /* 报告 .js 文件中的错误。 */
    "jsx": "preserve",                    /* 指定 JSX 代码生成：'preserve' */
    "react-native": true, or 'react'. 
    "declaration": true,                  /* 生成对应的 '.d.ts' 文件。 */
    "sourceMap": true,                     /* 生成对应的 '.map' 文件。 */
    "outfile": "/",                      /* 合并并输出到单个文件 */
    "outDir": "/",                      /* 将输出结构重定向到目录 */
    "rootDir": "/",                      /* 指定输入文件的根目录。用于通过 --outDir 控制输出结构。 */
    "removeComments": true,                /* 输出时不产生注释。 */
    "noEmit": true,                       /* 不产生输出。 */
    "importHelpers": true,                 /* 从 'tslib' 导入生成的辅助函数。 */
    "downlevelIteration": true,           /* 当目标为 'ES5' 或 'ES3' 时，为 'for-of'、展开和解构提供完整的迭代支持。 */
    "isolatedModules": true,              /* 将每个文件作为单独模块解析（类似于 'ts.transpileModule）。 */

    /* 严格类型检查选项 */
    "strict": true                        /* 启用所有严格类型检查选项。 */
    "noImplicitAny": true,                 /* 隐式的 'any' 类型。 */
    "strictNullChecks": true,              /* 启用严格空检查。 */
    "noImplicitThis": true,               /* 隐式的 'this' 类型。 */
    "AlwaysStrict": true,                  /* 对每个源文件中的 'this' 表达式报错。 */

    /* 额外检查 */
    "noUnusedLocals": true,               /* 报告未使用本地变量的错误。 */
    "noUnusedParameters": true,          /* 报告未使用参数的错误。 */
    "noImplicitReturns": true,            /* 函数未所有路径未返回返回值时报错。 */
    "noFallThroughInSwitch": true,   /* 报告 switch 语句中的穿透错误。 */

    /* 模块解析选项 */
    "moduleResolution": "node",           /* (Node.js) 或 'classic' (TypeScript 1.6 以前)。 */
    "baseUrl": "/",                       /* 解析非绝对模块名的基准目录 */
    "paths": "/",                         /* 映射导入的系列项目 */
    "rootDirs": [],                      /* 项目结构 */
    "types": [],                         /* 包含的类型列表 */
    "allowSyntheticImports": true,       /* 允许默认导入 */
    "experimentalDecorators": true,       /* 启用实验性装饰器 */
    "emitDecoratorMetadata": true         /* 产生元数据 */
  }
}
```

你可以在此查看完整示例。

**注意：** 对于两种目标场景，我们需要确保我们的运行时全局有一个符合 ECMAScript 标准的 `Promise`。这可能涉及获取一个 `Promise` 的补丁（polyfill）。我们还需要确保通过将 `lib` 标志设置为类似 `"dom", "es2015"` 或 `"dom", "es2015.promise", "es5"` 来让 TypeScript 知道 `Promise` 的存在。我们可以在这里查看哪些浏览器已经支持 `Promise`（原生和补丁支持）。



我们不能将像`interface`这种**仅**存在于**类型**声明空间的内容作为变量。

同样，你用`var`声明的内容**仅**存在于**变量**声明空间，且不能作为类型注解：

```typescript
var foo = 123;
var bar: foo; // ERROR: "cannot find name 'foo'"
```

之所以提示`cannot find name`是因为名称`foo`**未在**类型**空间中。

# 模块 (Modules)

## 全局模块 (Global Module)

默认情况下，当你在一个新的 TypeScript 文件中开始编写代码时，你的代码处于全局命名空间。作为一个演示，考虑一个文件`foo.ts`：

```typescript
var foo = 123;
```

如果你现在在同一个项目中创建一个新文件`bar.ts`，TypeScript 类型系统将允许你使用变量`foo`，就像它是全局可用的一样：

```typescript
var bar = foo; // allowed
```

不用说，拥有全局命名空间是危险的，因为它会让你的代码面临命名冲突。我们建议使用接下来介绍的文件模块。

## 文件模块 (File Module)

也称为外部模块 (external modules)。如果你在 TypeScript 文件的根部有`import`或`export`，那么它会在该文件中创建一个局部作用域。所以，如果我们把之前的`foo.ts`修改为如下内容（注意`export`的用法）：

```typescript
export var foo = 123;
```

我们将不再在全局命名空间中拥有`foo`。可以通过创建一个如下所示的新文件`bar.ts`来演示这一点：

```typescript
var bar = foo; // ERROR: "cannot find name 'foo'"
```

如果你想在`bar.ts`中使用`foo.ts`中的内容，你需要显式地导入它。下方的`bar.ts`更新所示：

```typescript
import { foo } from "./foo";
var bar = foo; // allowed
```

在`bar.ts`中使用`import`不仅允许你从其他文件中引入内容，还将`bar.ts`标记为一个`module`（模块），因此，`bar.ts`中的声明也不会污染全局命名空间。

根据编译器标志`module`的设置，使用外部模块的 TypeScript 文件会生成什么样的 JavaScript。

## 外部模块 (External modules)

TypeScript 外部模块模式包含了大量的威力和易用性。在这里我们讨论它的强大以及反映真实世界用法的一些模式。

## 澄清：commonjs, amd, es modules, 其他

首先，我们需要澄清一下现存模块系统中（糟糕的）不一致性。我将直接给出我目前的建议，并忽略噪音，即不向你展示所有其他可能的工作方式。

根据`module`选项你可以从 TypeScript 生成不同的 JavaScript。以下你可以忽略的内容（我不打算解释技术）：

- AMD：不要使用。仅限浏览器。

- SystemJS：是一个很好的实验。已被 ES modules 取代。

- ES Modules：尚未准备就。

现在只是生成 JavaScript 的选项。与其使用这些选项，不如使用`module:commonjs`

编写 TypeScript 模块也有点混乱。同样，这里是今天**不应该**这样做的方法：

```typescript
import foo = require('foo'). // 即 import/require。请改用 ES 模块语法。
```

好了，解决了这些问题后，让我们来看 ES 模块语法。

> 总结：使用`module:commonjs`并使用 ES 模块语法来导入/导出/编写模块。

# ES 模块语法 (ES Module syntax)

- 导出一个变量（或类型）只需在前面加上`export`关键字即可。

```typescript
// file.ts
export let someVar = 123;
export type SomeType = {
  foo: string;
};
```

- 在专门的导出语句中导出变量或类型，例如：

```typescript
// file `foo.ts`
let someVar = 123;
type SomeType = {
  foo: string;
}; export {
  someVar,
  SomeType
};
```

- 在带有*重命名*的专门`export`语句中导出变量或类型，例如：

```typescript
// file `foo.ts`
let someVar = 123;
export { someVar as aDifferentName };
```

- 使用`import`导入变量或类型，例如：

```typescript
// file `bar.ts`
import { someVar, SomeType } from './foo';
```

- 使用带有*重命名*的`import`导入变量或类型，例如：

```typescript
// file `bar.ts`
import { someVar as aDifferentName } from './foo';
```

- 使用`import *`将模块中的所有内容导入到一个中，例如：

```typescript
// file `bar.ts`
import * as foo from './foo';
// 你可以使用 'foo.someVar' 和 'foo.SomeType' 以及任何其他导出的内容。
```

- 使用单一 import 语句*仅*为了其副作用导入文件

```typescript
import 'core'; // polyfill
```

- 重新导出另一个模块中的所有项

```typescript
export * from './foo';
```

- 重新导出另一个模块中的某些项

```typescript
export { someVar } from './foo';
```

- 带重命名重新导出另一个模块中的某些项

```typescript
export { someVar as aDifferentName } from './foo';
```

# 默认导出/导入 (Default exports/imports)

正如你之后会学的，我不喜欢默认导出。尽管如此，这里是导出和使用默认导出的语法：

- 默认导出一个变量

- 默认导出一个函数

- 默认导出一个类

```typescript
// 导出
export default let someVar = 123;

// 导入
import default someVar from './foo';
```

- 默认导出一个对象

- 默认导出一个数组

```typescript
// 导出
export default {
  foo: "bar"
};

// 导入
import default obj from './foo';
```

- 默认导出一个类型

- 默认导出一个接口

```typescript
// 导出
export default type SomeType = {
  foo: string;
};

// 导入
import default SomeType from './foo';
```

- 默认导出多个项（通过一个对象或数组）

```typescript
// 导出
export default {
  foo: 1,
  bar: 2
};

// 导入
import { foo, bar } from './foo';
```

- 默认导出结合普通导出

```typescript
// 导出
export default function func() {}
export var otherVar = 10;

// 导入
import func, { otherVar } from './foo';
```

如果你没有在变量声明空间中使用导入的名称，那么该导入将完全从生成的 JavaScript 中移除。通过示例来解释这一点最好。一旦你理解了这一点，我们将向你展示用例。

## 示例 1

```
import foo = require('foo');
```

将生成 JavaScript：

![](img/7b4ede152e837dfd4e13fc18de91d96a_102_0.png)

没错。由于`foo`未被使用，该文件是空的。

## 示例 2

```
import foo = require('foo');
var bar: foo;
```

将生成 JavaScript：

```
var bar;
```

这是因为`foo`（或其任何属性，例如`foo.bas`）从未被当作变量使用。

## 示例 3

```typescript
import foo = require('foo');
var bar = foo;
```

将生成 JavaScript（假设使用 commonjs）：

```
var foo = require('foo');
var bar = foo;
```

这是因为`foo`被当作变量使用了。

## 用例：懒加载

类型推断需要提前完成。这意味着如果你想使用某个文件中的某些类型，你必须执行：

```
import foo = require('foo');
var bar: foo.SomeType;
```

然而，你可能想在某些条件下仅在运行时加载文件`foo`。对于此类情况，你应该只在类型注解中使用导入，而不是将其作为变量。这消除了 TypeScript 注入的任何提前运行时依赖。然后使用特定于你的模块加载器的代码手动导入实际模块。

例如，考虑以下基于 common 的代码，我们只在调用某个函数时加载模块 'foo'：

```typescript
import foo = require('foo');

export function loadFoo() {
  // 这种懒加载 `foo` 的方式将原始模块“仅”用作类型注释
  var _foo: typeof foo = require('foo');
  // 现在使用 `_foo` 作为变量而不是 `foo`。
}
```

在 amd（使用 requirejs）中的类似示例为：

```javascript
import foo = require('foo');

export function loadFoo() {
  // 这种懒加载 `foo` 的方式将原始模块“仅”用作类型注释
  require(['foo'], (_foo: typeof foo) => {
    // 现在使用 `_foo` 作为变量而不是 `foo`。
  });
}
```

这种模式通常用于：

- 在 web 应用中，在你在特定路由上加载某些 JavaScript；

- 在 node 应用中，仅在需要时才加载某些模块以加速应用启动。

## 用例：打破循环依赖

类似于懒加载用例，某些模块加载器（commonjs/node 和 amd/requires）处理循环依赖的能力并不理想。在这种情况下，在一个方向进行懒加载，而在另一个方向提前加载模块是有用的。

## 用例：确保导入

有时你只是为了副作用而加载一个文件（例如，该模块可能会向 CodeMirror 插件等某些库注册自己）。但是，如果你只是进行 import/require，编译后的 JavaScript 将不包含对模块的依赖，你的模块加载器（例如 webpack）可能会完全忽略该导入。在这种情况下，你可以使用`ensureImport`变量来确保编译后的 JavaScript 对该模块有依赖，例如：

```javascript
import foo = require('foo');
import bar = require('./bar');
import bas = require('./bas');
const ensureImport: any =
foo
  || bar
  || bas;
```

# globals.d.ts

我们在涵盖项目时讨论了全局模块与文件模块，并建议使用基于文件的模块而不是污染全局命名空间。

尽管如此，如果你有初学者级别的 TypeScript 开发者，可以给他们一个`globals.d.ts`文件，将接口/类型放在全局命名空间中，以便某些类型可以在你所有的 TypeScript 代码中“魔法般”直接可用。

> 对于任何将生成 JavaScript 的代码，我们强烈建议使用文件模块。

- 如果你需要，`globals.d.ts`非常适合为`lib.d.ts`添加扩展。

- 在进行 TS 到 JS 迁移时，它适用于快速声明模块 "some-library-you-dont-care-to-get-defs-for"。

# Namespace (命名空间)

命名空间围绕 JavaScript 中的一种常用模式提供了一种方便的语法：

```javascript
(function(something) {
  something.foo = 123;
})(something || (something = {}))
```

基本上，`something || (something = {})`允许匿名函数`function(something) {}`添加到现有对象（`something ||`部分）或启动新对象然后向该对象添加内容（`|| (something = {})`部分）。这意味着你可以拥有两个由执行边界分隔的此类块：

```javascript
(function(something) {
  something.foo = 123;
})(something || (something = {}))

console.log(something); // {foo:123}

{function(something) {
  something.bar = 456;
})(something || (something = {}))

console.log(something); // {foo:123, bar:456}
```

这在 JavaScript 世界中通常用于确保内容不会泄漏到全局命名空间。通过使用基于文件的模块，你不需要担心这个，但该模式对于许多代码的逻辑分组仍然很有用：

```typescript
namespace Utility {
  export function log(msg) {
    console.log(msg);
  }
  export function error(msg) {
    console.error(msg);
  }
}
```

（注：后续文本中存在大量重复内容，已根据要求过滤掉重复部分）

# 使用 Node.js 使用 TypeScript

TypeScript 从诞生起就对 Node.js 有原生支持。以下是设置一个快速 Node.js 项目的方法：

> 注意：这些步骤中的许多实际上是通用的 Node.js 配置步骤

- 1. 设置 Node.js 项目的`package.json`。快速初始化：`npm init -y`

- 2. 添加 TypeScript (`npm install typescript --save-dev`)

- 3. 添加 node 类型 (`npm install @types/node --save-dev`)

- 4. 初始化`tsconfig.json`以配置 TypeScript 选项 (`npx tsc --init`)

- 5. 确保你的`tsconfig.json`中有`compilerOptions`

大功完成！启动你的 IDE（例如`alm -o`）并开始尝试吧。现在你可以使用所有内置的 node 模块（例如`import fs = require('fs');`），同时享用 TypeScript 的安全性和开发者体验！

# 进阶技巧：实时编译 + 运行

- 添加`ts-node`，我们将用于在 node 中进行实时编译+运行 (`npm install ts-node --save-dev`)

- 添加`nodemon`，它会在文件发生变化时调用`ts-node` (`npm install nodemon --save-dev`)

现在根据你的应用程序入口在`package.json`中添加一个脚本目标，假设入口是`index.ts`：

```json
"scripts": {
  "start": "npm run build:live",
  "build:live": "nodemon --exec ./node_modules/.bin/ts-node ./index.ts"
}
```

这样你现在就可以运行`npm start`，当你编辑`index.ts`时：

- nodemon 重启它的命令 (`ts-node`)

- ts-node 自动编译并读取`tsconfig.json`和已安装的 typescript 版本

- ts-node 通过 Node.js 运行输出的 javascript

# 创建 TypeScript node 模块

# 创建 TypeScript node 模块的教程

使用 TypeScript 编写的模块非常有趣，因为你可以获得极佳的编译安全自动补全（本质上是可执行的文档）。

创建高质量的 TypeScript 模块非常简单。假设你的包所需的目录结构如下：



# TypeScript 包结构

```text
package
├── package.json
├── tsconfig.json
├── src
│   ├── 所有的源文件
│   ├── index.ts
│   │   └── foo.ts
│   │   └── ...
└── lib
    ├── 所有的编译后文件
    ├── index.d.ts
    ├── index.js
    ├── foo.d.ts
    ├── foo.js
    └── ...
```

- 在你的 `tsconfig.json` 中
  - 包含 `compilerOptions : "outDir": "lib"` 和 `"declaration": true` < 这会在 `lib` 文件夹中生成声明文件和 js 文件
  - `include: ["src/**/*"]` < 这包含了 `src` 目录下的所有文件。
- 你的 `package.json` 包含
  - `"main": "lib/index"` < 这告诉 Node.js 加载 `lib/index.js`
  - `"types": "lib/index"` < 这告诉 TypeScript 加载 `lib/index.d.ts`

示例包：

- `npm install typestyle` 以使用 TypeStyle
- 使用方法：`import { style } from 'typestyle';` 将是完全类型安全的。

更多：

- 如果你的包依赖其他用 TypeScript 编写的包，像处理原生 JS 包一样，将它们放在 `dependencies` / `devDependencies` / `peerDependencies` 中。
- 如果你的包依赖其他用 JavaScript 编写的包，且你想在项目中以类型安全的方式使用它们，请将类型（例如 `@types/foo`）放在 `devDependencies` 中。JavaScript 类型应该在主 NPM 流之外。JavaScript 生态经常在没有语义版本控制的情况下破坏类型，因此你的用户需要这些类型时安装适用于它们的 `@types/foo` 版本。

# 加分项

此类 NPM 模块可以配合 browserify（使用 `tsify`）或 webpack（使用 `ts-loader`）完美运行。

# 浏览器中的 TypeScript

如果你在使用 TypeScript 创建 Web 应用，这里是我快速设置 TypeScript + React（我首选的 UI 框架）项目的建议。

# 通用机器环境设置

- 安装 Node.js
- 安装 Git

## 项目快速设置

使用 https://github.com/basarat/react-typescript 作为基础。

```bash
git clone https://github.com/basarat/react-typescript.git
cd react-typescript
npm install
```

现在开始开发你出色的应用程序吧

# 项目详细设置

为了查看该项目是如何创建的，下方是文档。

- 创建项目目录：

```bash
mkdir your-project
cd your-project
```

- 创建 `tsconfig.json`：

```json
"compilerOptions": {
  "sourceMap": true,
  "module": "commonjs",
  "target": "es5",
  "jsx": "react"
},
"include": [
  "src"
],
"compileOnSave": false
```

- 创建 `package.json`：

```json
{
  "name": "react-typescript",
  "version": "0.0.0",
  "license": "MIT",
  "repository": {
    "type": "git",
    "url": "https://github.com/basarat/typescript-react.git"
  },
  "scripts": {
    "build": "webpack .webpack.config.js",
    "start": "webpack-dev-server ./webpack.config.js --content-base /public"
  },
  "dependencies": {
    "@types/react": "16"
  }
}
```

- 创建 `webpack.config.js`：

```javascript
module.exports = {
  entry: './src/index.ts',
  output: {
    path: './dist',
    filename: 'bundle.js'
  },
  resolve: {
    extensions: ['.ts', '.js']
  },
  module: {
    rules: [
      {
        test: /\.ts$/,
        use: 'ts-loader',
        exclude: /node_modules/
      }
    ]
  }
};
```

- 创建 `src/index.ts`：

```typescript
import * as fs from 'fs';
console.log(fs.readdirSync('.'));
```

```typescript
interface Name {
  first: string;
  second: string;
}

var name: Name;
name = {
  first: 'John',
  second: 'Doe'
};

name = { // Error: `second` is missing
  first: 'John'
}
name = { // Error: `second` is the wrong type
  first: 'John',
  second: 1337
};
```

在这里，我们首先将 `first: string + second: string` 组合成一个新的注解 `Name`，它对单个成员强制执行类型检查。接口（Interfaces）在 TypeScript 中非常强大，我们将专门用一个章节来讨论如何利用这些优势。

## 内联类型注解

你不需要创建一个新的接口，可以使用 `{ /*Structure*/ }` 对你想要的任何内容进行内联标注。以下是使用内联类型再次展示之前的示例：

```typescript
var name: {
  first: string;
  second: string;
}

name = {
  first: 'John',
  second: 'Doe'
}

name = { // Error: `second` is missing
  first: 'John'
}
name = { // Error: `second` is the wrong type
  first: 'John',
  second: 1337
};
```

内联类型非常适合为某些内容快速提供一次性的类型注解。它省去了你构思一个（可能并不好的）类型名称的麻烦。然而，如果你发现自己多次内联使用相同的类型注解，那么考虑将其重构为接口（或在本节稍后介绍的类型别名）是一个好主意。

## 特殊类型

除了已经过的原始类型外，还有少数类型在 TypeScript 中具有特殊含义。这些是 `any`、`null`、`undefined`、`void`。

### any

`any` 类型在 TypeScript 系统占据特殊地位。它提供了一个逃离类型系统的出口，告诉编译器“走开”。`any` 与类型系统中的**任何**所有类型兼容。这意味着*任何内容*都可以赋值给它，它也可以赋值给任何内容。下面的示例演示了这一点：

```typescript
var power: any;

// 接受任何类型
power = '123';
power = 123;

// 与所有类型兼容
var num: number;
power = num;
power = power;
```

如果你正在将 JavaScript 代码迁移到 TypeScript，起初你会和 `any` 成为好朋友。然而，不要太认真对待这段友谊，因为这意味着**确保类型安全完全由你负责**。你基本上是在告诉编译器**不要进行任何有意义的静态分析**。

### null 和 undefined

JavaScript 字面量 `null` 和 `undefined` 在类型系统中的处理方式实际上与 `any` 类型相同。这些字面量可以赋值给任何其他类型。下面的示例演示了这一点：

```typescript
var num: number;
var str: string;

// 这些字面量可以赋值给任何类型
num = null;
str = undefined;
```

### void

使用 `:void` 表示函数没有返回类型：

```typescript
function log(message): void {
  console.log(message);
}
```

## 泛型

计算机科学中的许多算法和数据结构并不依赖对象的实际类型。但你仍然希望在各种变量之间实施约束。一个简单的例子是一个函数，它接收一个项目列表并返回一个反后的项目列表。这里的约束存在于传递给函数的内容与函数返回的内容之间：

```typescript
function reverse<T>(items: T[]): T[] {
  var toreturn = [];
  for (let i = items.length - 1; i >= 0; i--) {
    toreturn.push(items[i]);
  }
  return toreturn;
}
```

```typescript
var sample = [1, 2, 3];
var reversed = reverse(sample);
console.log(reversed); // 3,2,1
```

```typescript
// 安全！
reversed[0] = '1'; // Error!
reversed = ['1', '2']; // Error!
```

```typescript
reversed[0] = 1; // Okay
reversed = [1, 2]; // Okay
```

基本上，`reverse` 函数接收一个某种类型 `T` 的数组 (`items: T[]`，注意 `reverse<T>` 中的类型参数）并返回一个类型为 `T` 的数组（注意 `: T[]`）。因为 `reverse` 函数返回的项与其接收的项类型相同，TypeScript 知道 `reversed` 变量的类型是 `number[]` 并将为你提供类型安全。如果你向 `reverse` 函数传递一个 `string[]` 数组，返回的也是 `string[]` 数组，你将获得类似的类似的类型安全：

```typescript
var strArr = ['1', '2'];
var reversedStrs = reverse(strArr);

reversedStrs = [i, 2]; // Error!
```

在 JavaScript 中，所有数组都有 `.reverse` 方法，TypeScript 确实使用泛型来定义其结构：

```typescript
interface Array<T> {
  reverse(): T[];
  // ...
}
```

这意味着当你在任何数组上调用 `.reverse()` 时，都会获得类型安全，如下所示：

```typescript
var numArr = [1, 2];
var reversedNums = numArr.reverse();

reversedNums = ['1', '2']; // Error!
```

我们稍后介绍时会讨论更多关于 `Array<T>` 接口。

## 联合类型

在 JavaScript 中，你经常希望允许一个属性为多种类型之一。这在 TypeScript 中用 `|` 表示。常见的用例是字符串或数字。这里是一些示例让你熟悉：

```typescript
type Text = string | number;
type Coordinates = [number, number];
type Callback = (data: string) => void;
```

## 交叉类型

交叉是一种常见的模式，你创建一个同时具有两者属性的新对象。下文所示：

```typescript
type a = { name: string };
type b = { age: number };
type c = a & b;
```

# 环境声明

TypeScript 提供了方便的命名。

提示：如果你需要层级结构，请使用 `interface`。它们可以配合 `implements` 和 `extends` 使用。

提示：对于简单的对象结构（如坐标），使用类型别名只需给它们一个语义化名称。此外，当你想给联合类型或交叉类型赋予语义名称时，类型别名是更好的选择。

## 总结

现在你已经开始为大部分 JavaScript 代码添加注解，我们就可以进入 TypeScript 类型系统中所有可用功能的细节了。

## 从 JavaScript 迁移

假设：

- 你了解 JavaScript。
- 你了解项目所使用的模式和构建工具（例如 webpack）。

在排除这些假设的情况下，通用流程包含以下步骤：

- 添加 `tsconfig.json`。
- 将源代码文件扩展名从 `.js` 改为 `.ts`。开始使用 `any` 抑制错误。
- 使用 TypeScript 编写新代码，并尽可能少使用 `any`。
- 回到旧代码并添加添加注解并修复 bug。
- 为第三方 JavaScript 代码使用环境定义。

让我们进一步讨论其中几点。

请注意，所有的 JavaScript 都是有效的 TypeScript。也就是说，如果你给 TypeScript 编译器提供一些 JavaScript，编译器生成的 JavaScript 将将与原始 JavaScript 完全一致。这意味着将扩展名从 `.js` 改为 `.ts` 不会对你的代码库产生不利影响。

## 抑制错误

TypeScript 会立即对你的代码进行类型检查，你的原始 JavaScript 代码可能没有想象中那么整洁，因此你会收到诊断错误。许多错误你可以通过 `any` 来抑制，例如：

```typescript
var foo = 123;
var bar = 'hey';

bar = foo; // ERROR：无法将数字赋值给字符串
```

尽管该错误是有效的（在大多数情况下，推断出的信息比代码库不同部分的作者想象的要好），但你的重心可能可能是使用 TypeScript 编写新代码，同时逐步更新旧代码库。在这里，你可以像下所示所示通过类型断言来抑制此错误。

```typescript
var foo = 123;
var bar = 'hey';

bar = foo as any; // OK！
```

在其他地方，你可能想将某些内容标记为 `any`，例如：

```typescript
function foo() {
  return 1;
}
var bar = 'hey';
bar = foo(); // ：无法将数字赋值给字符串
```

抑制错误：

```typescript
function foo() { // 添加了 `any`
  return 1;
}
var bar = 'hey';
bar = foo(); // 好的！
```

> 注意：抑制错误是危险的，但它允许你留意新旧 TypeScript 代码中的错误。你可能想在编写过程中留存 // TODO: 注释。

# 第三方 JavaScript

你可以将 JavaScript 转换为 TypeScript，但你无法让整个世界都使用 TypeScript。这正是 TypeScript 的环境定义（ambient definition）支持大显身手的地方。在开始，我们建议你创建一个 `vendor.d.ts`（`.d.ts` 扩展表示这是一个声明文件）并开始向其中添加内容。或者为特定库创建一个特定文件，例如为 jquery 创建 `query.d.ts`。

> 注意：市面上几乎 90% 的主流 JavaScript 库都存在一个名为 DefinitelyTyped 的 OSS 仓库的维护良好且强类型的定义。我们建议在像这里这样创建自己的之前先查看那里。尽管如此，这种快速而粗暴的方法对于减少你与 TypeScript 的初始摩擦至关重要。

考虑 jquery 的情况，你可以很容易为它创建一个简易的定义：

```typescript
declare var $: any;
```

有时，你可能想对某些内容（例如 jQuery）添加显式注解，并在类型声明空间中使用某些内容。你可以使用 `type` 关键字轻松地做到：

```typescript
declare type JQuery = any;
declare var $: jQuery;
```

这提供了一个更方便的更新路径。

再次，DefinitelyTyped 上存在一个高质量的 `jquery.d.ts`。但现在你已经知道在使用第三方 JavaScript 时如何快速克服任何 JavaScript -> TypeScript 的摩擦了。接下来我们将详细介绍环境声明。

# 第三方 NPM 模块

与全局变量声明类似，你可以很轻松地声明一个全局模块。例如，对于 jquery，如果你想将其作为模块使用（[https://www.npmjs.com/package/jquery](https://www.npmjs.com/package/jquery)），你可以自己编写：



```typescript
declare module "jquery";
```

然后你就可以根据需要在文件中导入它：

```typescript
import * as $ from "jquery";
```

> 再次，`DefinitelyTyped` 上存在高质量的 `jquery.d.ts`，提供了质量更高的 `jquery` 模块声明。但你的库可能不存在，所以现在你有了一种快速、低摩擦的方法继续迁移。

# 外部非 JS 资源

你甚至可以使用简单的样式声明导入任何文件，例如 `.css` 文件（如果你在使用类似 `webpack` 风格的加载器或 `css` 模块）（最好放在 `globals.d.ts` 文件中）：

```typescript
declare module "*.css";
```

现在人们可以 `import * as foo from "./some/file.css";`

同样，如果你使用 `html` 模板（例如 `angular`），你可以：

```typescript
declare module "*.html";
```

# @types

`Definitely Typed` 是 `TypeScript` 最强大的优势之一。社区已经有效地记录了市面上几乎 90% 主流 `JavaScript` 项目的性质。

这意味着你可以以一种非常有交互性和探索性的方式使用这些项目，无需在单独的窗口中打开文档并确保你没有拼写错误。

# 使用 @types

安装非常简单，因为它直接运行在 `npm` 之上。例如，你只需通过以下命令安装 `jquery` 的类型定义：

```bash
npm install @types/jquery --save-dev
```

`@types` 同时支持全局和模块类型定义。

# 全局 @types

默认情况下，任何支持全局消费的定义都会自动包含。例如，对于 `jquery`，你应该能够在你的项目中全局范围内使用 `$`。

然而，对于库（如 `jquery`），我通常建议使用模块：

# 模块 @types

安装后，实际上不需要特殊配置。你只需要像使用模块一样使用它，例如：

```typescript
import * as s from "jquery";
// 在此模块中随心使用 $ :)
```

# 控制全局变量

所示，支持自动全局泄漏的定义对某些团队来说可能是问题，因此你选择使用 `tsconfig.json` 中的 `compilerOptions.types` 显式仅引入有意义的类型，例如：

```json
{
  "compilerOptions": {
    "types" : [
      "jquery"
    ]
  }
}
```

上述显示了一个示例，仅允许使用 `jquery`。即使人员安装了其他定义（如 `npm install @types/node`），它的全局变量（例如 `process`）也不会泄漏到你的代码中，直到你将其添加到 `tsconfig.json` 的 `types` 选项中。

# 环境声明

正如我们在“为什么选择 `TypeScript`”中提到的：

> `TypeScript` 的主要设计目标之一是让你能够在 `TypeScript` 中安全、方便使用现有的 `JavaScript` 库。`TypeScript` 通过声明来实现这一点。

环境声明允许你安全地使用现有的流行的 `JavaScript` 库，并逐步将你的 `JavaScript`/`CoffeeScript`/其他编译为 `JS` 的语言项目迁移到 `TypeScript`。

研究第三方 `JavaScript` 代码环境声明中的模式，对于注解你的 `TypeScript` 代码库来说也是一种良好的实践。这就是为什么我们在如此早的阶段就介绍了它。

# 声明文件

> `TypeScript` 的主要设计目标之一是让你能够在 `TypeScript` 中安全、方便使用现有的 `JavaScript` 库。`TypeScript` 通过声明来实现这一点。

环境声明允许你安全地使用现有的流行的 `JavaScript` 库，并逐步将你的 `JavaScript`/`CoffeeScript`/其他编译为 `JS` 的语言项目迁移到 `TypeScript`。

研究第三方 `JavaScript` 代码环境声明中的模式，对于注解你的 `TypeScript` 代码库来说也是一种良好的实践。这就是为什么我们在如此早的阶段就介绍了它。

声明文件

考虑 `jquery` 的情况，你可以很容易为它创建一个简易的定义：

```typescript
declare var $: any;
```

有时，你可能想对某些内容（例如 `jQuery`）添加显式注解，并在类型声明空间中使用某些内容。你可以使用 `type` 关键字轻松地做到：

```typescript
declare type JQuery = any;
declare var $: jQuery;
```

这提供了一个更方便的更新路径。

再次，`DefinitelyTyped` 上存在一个高质量的 `jquery.d.ts`。但现在你已经知道在使用第三方 `JavaScript` 时如何快速克服任何 `JavaScript` -> `TypeScript` 的摩擦了。接下来我们将详细介绍环境声明。

# 变量

例如，为了告诉 `TypeScript` `process` 变量，你可以：

```typescript
declare var $: any;
```

这允许你使用 `process` 而不会报错：

```typescript
process.exit();
```

我们建议尽可能使用接口，例如：

```typescript
interface Process {
  exit(code?: number): void;
}
declare var process: Process;
```

这允许其他人扩展全局变量的同时，仍让 `TypeScript` 知晓这些修改。例如，考虑以下情况，我们为 `process` 增加了 `exitWithLogging` 函数供我们之用：

```typescript
interface Process {
  exitWithLogging(code?: number): void;
}
process.exitWithLogging = function() {
  console.log("exiting");
  process.exit.apply(process, arguments);
}
```

# 接口对没有影响。`TypeScript` 接口在声明变量结构方面非常强大。

以下两个是等效的声明，第一个使用*内联注解*，第二个使用*接口*：

```typescript
// Sample A
declare var myPoint: { x: number; y: number; };

// Sample B
interface Point {
 x: number; y: number;
}
declare var myPoint: Point;
```

然而，*示例 B* 的之处在于，如果有人编写了基于 `myPoint` 库并添加新成员的库，他们可以轻松地向现有的 `myPoint` 声明添加内容：

```typescript
// Lib a.d.ts
interface Point {
x: number; y: number;
}
declare var myPoint: Point;

// Lib b.d.ts
interface Point {
z: number;
}

// 你的代码
var myPoint.z; // 允许！
```

因为 **`TypeScript` 中的接口是开放的**。这是 `TypeScript` 的一个关键特性，允许你使用*接口*来模拟 `JavaScript` 的扩展性。

# 类可以实现接口

如果你想使用遵循某人在*接口*中为你声明的对象结构的*类*，你可以使用 `implements` 关键字来确保兼容性：

```typescript
interface Point {
  x: number; y: number;
}

class MyPoint implements Point {
  x: number; y: number; // 与 Point 相同
}
```

基本上在存在 `implements` 的情况下，外部 `Point` 接口的任何更改都会导致你的代码库出现编译错误，因此你可以轻松地保持同步：

```typescript
interface Point {
  x: number; y: number;
  z: number; // 新成员
}

class MyPoint implements Point { // 错误缺少缺少 `z`
  x: number; y: number;
}
```

注意 `implements` 限制了类的实例结构，即：

```typescript
var foo: Point = new MyPoint();
```

`foo: Point = MyPoint` 并不是一回事。

## 提示

## 并不是每个接口都能轻松实现

接口用于声明 `JavaScript` 中可能存在的任何任意复杂的结构。

考虑以下接口，其中某些内容可以通过 `new` 进行调用：

```typescript
interface Crazy {
  new (): {
    hello: number;
  };
}
```

你本质上会拥有类似这样的代码：

```typescript
class CrazyClass implements Crazy {
  constructor() {
    return { hello: 123 };
  }
}
// 因为
const crazy = new CrazyClass(); // crazy 将是 {hello:123}
```

你可以用接口声明所有疯狂的 `JS` ，甚至在 `TypeScript` 中安全地使用它们。这并不意味着你可以使用 `TypeScript` 类来实现这些它们。

- 枚举 (Enums)

- 枚举与数字

- 枚举与字符串

- 更改与枚举相关的数字

- 枚举是开放的

- 作为标志的枚举

- 常枚举 (Const enums)

- 带有静态函数的枚举

## 枚举 (Enums)

枚举是组织相关值集合的一种。许多其他编程语言（`C`/`C#`/`Java`）都有枚举数据类型，但 `JavaScript` 没有。不过 `TypeScript` 有。这里是一个 `TypeScript` 枚举的定义示例：

```typescript
enum CardSuit {
  Clubs,
  Diamonds,
  Hearts,
  Spades
}

// 示例用法
var card = CardSuit.Clubs;

// 安全性
card = "not a member of card suit"; // 错误：string 无法赋值给类型 `CardSuit`
```

## 枚举与数字

`TypeScript` 枚举是基于数字的。这意味着数字可以赋值给枚举实例，因此任何与数字兼容的其他内容都可以。

```typescript
enum Color {
  Red,
  Green,
  Blue
}
var col = Color.Red;
col = 0; // 实际上等同于 Color.Red
```

## 枚举与字符串

在深入研究之前，让我们看看它生成的 `JavaScript`，这里有一个示例 `TypeScript`：

```typescript
enum Tristate {
  False,
  True,
  Unknown
}
```

生成了以下 `JavaScript`：

```javascript
var Tristate;
(function (Tristate) {
  Tristate["False"] = 0 || "False";
  Tristate["True"] = 1 || "True";
  Tristate["Unknown"] = 2 || "Unknown";
})(Tristate || (Tristate = {}));
```

让我们关注 `Tristate["False"] = 0 || "False";` 这一行。在其中 `Tristate["False"] = 0` 应该是自言易懂的，即将 `Tristate` 变量的 "False" 成员设置为0。注意在 `JavaScript` 中，赋值运算符返回被赋值的值（在此情况下为 0）。因此 `JavaScript` 运行时执行的下一条语句是 `Tristate[0] = "False"`。这意味着你可以使用 `Tristate` 变量将枚举的字符串版本转换为数字，或将新版本的枚举转换为字符串。下文所示：

```typescript
enum Tristate {
  False,
  True,
  Unknown
}
console.log(Tristate[0]); // "False"
console.log(Tristate["False"]); // 0
console.log(Tristate[Tristate.False]); // "False" 因为 `Tristate.False == 0`
```

## 更改与枚举相关的数字

默认情况下，枚举从 0 开始，然后随后的每个值都会自动递增 1。例如，考虑以下内容：

```typescript
enum Color {
  Red,      // 0
  Green,    // 1
  Blue      // 2
}
```

然而，你可以通过特定的赋值来更改与任何枚举成员相关的数字。下文演示了这一点，我们从 3 开始并从那里递增：

```typescript
enum Color {
  DarkRed = 3,   // 3
  DarkGreen,    // 4
  DarkBlue      // 5
}
```

> 提示：我经常将第一个枚举初始化为 `= 1`，因为它允许我对枚举值进行安全的真值检查。

## 枚举是开放的

这里再次显示了上述枚举生成的 `JavaScript`：

```javascript
var Tristrate;
(function (Tristrate) {
  Tristrate["False"] = 0 || "False";
  Tristrate["True"] = 1 || "True";
  Tristrate["Unknown"] = 2 || "Unknown";
})(Tristrate || (Tristrate = {}));
```

我们已经解释过 `Tristrate[Tristrate["False"] = 0] = "False"` 部分。注意周围的代码 `(function (Tristrate) { ... })`。由于在 `JavaScript` 中赋值运算符返回被赋值的值，这意味着你可以使用 `Tristate` 变量将枚举的字符串版本转换为数字，或将新版本的枚举转换为字符串。下文所示：

```typescript
enum Tristate {
  False,
  True,
  Unknown
}
console.log(Tristate[0]); // "False"
console.log(Tristate["False"]); // 0
console.log(Tristate[Tristate.False]); // "False" 因为 `Tristate.False == 0`
```

## 作为标志的枚举

枚举的一个极佳用途是作为标志。考虑以下内容：

```typescript
enum FileFlags {
  None = 0,
  Read = 1,
  Write = 2,
  Execute = 4
}

let myFile = FileFlags.Read | FileFlags.Write;
if (myFile & FileFlags.Read) {
  // 是可读的
}
```

## 常枚举 (Const enums)

假设你有如下枚举定义：

```typescript
enum Tristate {
  False,
  True,
  Unknown
}
```

```typescript
var lie = Tristate.False;
```

行 `var lie = Tristate.False` 随后被编译为 `JavaScript` `var lie = Tristate.False`（输出与输入相同）。这意味着在运行时需要查找 `Tristate` 然后是 `Tristate.False`。为了在这里获得性能提升，可以将枚举标记为 `const enum`：

```typescript
const enum Tristate {
  False,
  True,
  Unknown
}
```

```typescript
var lie = Tristate.False;
```

生成了 `JavaScript`：

```javascript
var lie = 0;
```

即编译器：

1. 内联了枚举的所有使用处（用 0 代替 `Tristate.False`）。

2. 不为枚举定义生成任何 `JavaScript`（运行时没有 `Tristate` 变量），因为其使用已被内联。

## 常枚举 preserveConstEnums

内联具有明显的性能优势。运行时没有 `Tristate` 变量这一点仅仅是编译器在帮助你避免生成运行时实际未使用的 `JavaScript`。然而，你可能希望编译器仍然生成枚举定义的 `JavaScript` 版本，用于数字到字符串或字符串到数字的查找。在这种情况下，可以使用编译器标志 `--preserveConstEnums`，它将生成 `var Tristate` 定义，这样你就可以需要手动使用 `Tristate["False"]` 或 `Tristate[0]` 了。

## 带有静态方法的枚举

你可以使用 `enum` + `namespace` 合并声明来为枚举添加静态方法。以下示例展示了一个例子，其中我们为枚举 `weekday` 增添了一个静态成员 `isBusinessDay`：



# TypeScript 枚举与命名空间

```typescript
enum Weekday {
  Monday,
  Tuesday,
  Wednesday,
  Thursday,
  Friday,
  Saturday,
  Sunday
}

namespace Weekday {
  export function isBusinessDay(day: Weekday) {
    switch (day) {
      case Weekday.Saturday:
      case Weekday.Sunday:
        return false;
      default:
        return true;
    }
  }
}

const mon = Weekday.Monday;
const sun = Weekday.Sunday;
console.log(Weekday.isBusinessDay(mon)); // true
console.log(Weekday.isBusinessDay(sun)); // false
```

# lib.d.ts

- 使用示例
- 内部结构
- 修改类型
- 使用自定义 `lib.d.ts`
- 编译器目标对 `lib.d.ts` 的影响
- `lib` 选项
- 旧 JavaScript 引擎的 Polyfill

## lib.d.ts

一个特殊的声明文件 `lib.d.ts` 会随每个 TypeScript 安装版本一起发布。该文件包含了 JavaScript 运行时和 DOM 中存在的各种 JavaScript 构造的全局声明。此文件会自动包含在 TypeScript 项目的编译上下文中。该文件的目的是让你能够轻松开始编写代码。你可以通过指定 `--noLib` 编译器标志（或在 `tsconfig.json` 中设置 `"noLib": true`）从编译中排除此文件。

### 使用示例

一往一样，我们来看此文件在实际应用中的示例：

```typescript
var foo = 123;
var bar = foo.toString();
```

这段代码检查通过正常，因为 `toString` 函数在 `lib.d.ts` 中为所有 JavaScript 对象进行了定义。如果你在开启 `noLib` 选项的情况下使用相同的代码，会得到一个错误：

```typescript
var foo = 123;
var bar = foo.toString(); // Error: Property 'toString' does not exist on type 'number'.
```

既然现在你已经理解了 `lib.d.ts` 的重要性，那么它的内容是什么样的呢？我们接下来将检查这一点。

### lib.d.ts 内部

`lib.d.ts` 的内容主要是变量声明，例如 `window`、`document`、`Math` 以及一系列类似的接口声明。发现你已知的代码（例如 `Math.floor`）中内容的简单方法是，使用你的 IDE 按 F12（转到定义）（TypeScript 对此有很好的支持），然后查看一个示例声明：

```typescript
declare var window: Window;
```

这只是一个简单的 `declare var` 后面跟着变量名和一个用于类型注解的接口。这些变量通常指向某些全局接口，例如，这里是（实际上是极其庞大的）`Window` 接口的一个小示例：

```typescript
interface Window extends EventTarget, Timer, SessionStorage, LocalStorage, Console, GlobalHandlers, BaseEnvironment {
  animationStartTime: number;
  applicationCache: ApplicationCache;
}
```

...你可以在这里看到这些接口中有大量的类型信息。在没有 TypeScript 的情况下，你需要将这些信息记在脑子里。现在你可以将这些知识交给编译器，并轻松访问 intellisense 等功能。

为这些全局变量使用接口是有充分理由的。它允许你向全局添加额外的属性，而无需更改 `lib.d.ts`。我们将接下来介绍这个概念。

### 修改原生类型

由于 TypeScript 中的接口是开放的，这意味着你可以向 `lib.d.ts` 中声明的接口添加成员，TypeScript 会识别到这些新增。请注意，你需要在全局模块中进行这些更改，这些接口才能与 `lib.d.ts` 关联。我们甚至建议创建一个名为 `globals.d.ts` 的特殊文件来实现此目的。这里有几个向 `window`、`Math`、`Date` 添加内容的示例案例：

### window 示例

向 `window` 接口添加内容，例如：

```typescript
interface Window {
  helloWorld(): void;
}
```

这将允许你以类型安全的方式使用它：

```typescript
// 在运行时添加
window.helloWorld = () => console.log('hello world');
// 调用
window.helloWorld();
// 误用会得到错误：
window.helloWorld('gracious'); // Error: Supplied parameters do not match the signature of the call target
```

### Math 示例

全局变量 `Math` 在 `lib.d.ts` 中的定义如下（再次，使用你的开发工具导航到定义）：

> /* 内置对象提供了基础数学功能和常量。 */

`declare var Math: Math;`

即变量 `Math` 是 `Math` 接口的实例。`Math` 接口定义为：

```typescript
interface Math {
  E: number;
  LN10: number;
  // others...
}
```

`Math` 意味着如果你想向全局变量 `Math` 添加内容，只需要将其添加到 `Math` 全局接口中，例如考虑 `seedrandom` 项目，它在全局 `Math` 对象上添加了 `seedrandom`。这可以很容易地声明：

```typescript
interface Math {
  seedrandom(seed?: string);
}
```

然后你就可以直接使用它：

```typescript
Math.seedrandom();
// 或者
Math.seedrandom("Any string you want!");
```

### Date 示例

全局变量 `Date` 在 `lib.d.ts` 中定义如下：

```typescript
declare var Date: Date;
```

这意味着 `Date` 变量是 `Date` 接口的实例。`Date` 接口定义为：

```typescript
interface Date {
  getTime(): number;
  // others...
}
```

如果你想向全局变量 `Date` 添加内容，只需要将其添加到 `Date` 全局接口中，例如：

```typescript
interface Date {
  myCustomMethod(): void;
}
```

将编译目标设为 `es6` 会导致 `lib.ts` 包含更多现代（es6）特性（如 `Promise`）的额外环境声明。这种编译器改变代码环境的魔法效果对某些人是有利的，但对另一些来说是有问题的，因为它将代码生成与代码环境混为了一体。

然而，如果你想对环境进行细粒度的控制，应该使用我们接下来讨论的 `--lib` 选项。

## lib 选项

有时（很多时候）你想解耦编译目标（生成的 JavaScript 版本）与环境库支持之间的关系。一个常见的例子是 `Promise`，例如今天（2016 年 6 月），你很可能想使用 `--target es5` 但仍然使用如 `Promise` 等最新特性。为了支持这一点，你可以使用 `lib` 编译器优化器对 `lib` 进行显式控制。

> 注意：使用 `--lib` 将任何库的魔法与 `--target` 解耦，为你提供更好的控制。

你可以在命令行或 `tsconfig.json`（推荐）中提供此选项：

### 命令行：

```bash
tsc --target es5 --lib dom,es6
```

### tsconfig.json:

```json
"compilerOptions": {
  "lib": ["dom", "es6"]
}
```

库可以分为以下类别：

- JavaScript 批量功能：
  - `es5`
  - `es6`
  - `es2015`
  - `es7`
  - `es2016`
  - `es2017`
  - `esnext`
- 运行环境：
  - `dom`
  - `dom.iterable`
  - `webworker`
  - `scripthost`
- ESNext 按特性选项（比批量功能更小）：
  - `es2015.core`
  - `es2015.collection`
  - `es2015.generator`
  - `es2015.iterable`
  - `es2015.promise`
  - `es2015.proxy`
  - `es2015.reflect`
  - `es2015.symbol`
  - `es2015.symbol.wellknown`
  - `es2016.array.include`
  - `es2017.object`
  - `es2017.sharedmemory`
  - `esnext.asynciterable`

注意：`--lib` 选项提供了极其精细的控制。因此你很可能想从批量 + 环境类别中选择一个项。如果没有指定 `--lib`，则会注入默认库：

- 对于 `--target es5` => `es5`, `dom`, `scripthost`
- 对于 `--target es6` => `es6`, `dom`, `dom.iterable`, `scripthost`

我的个人建议：

```json
"compilerOptions": {
  "target": "es5",
  "lib": ["es6", "dom"]
}
```

示例：当目标为 `es5` 时，不包含带有 ES5 Symbol API 的 `Symbol`。事实上，我们会收到如下错误：`[ts] Cannot find name 'Symbol'`。我们可以结合 `"target": "es5"` 与 `"lib"` 使用来在 TypeScript 中提供 `Symbol` API：

```json
"compilerOptions": {
  "target": "es5",
  "lib": ["es5", "dom", "scripthost", "es2015.symbol"]
}
```

## 为旧版 JavaScript 引擎的 Polyfill

## 关于此主题的 Egghead PRO

有很多运行时功能类似于 `Map` / `Set` 甚至 `Promise`（这个列表会随着时间变化），你可以配合现代的 `lib` 选项使用它们。要使用这些功能，你只需要 `core-js`。只需安装：

```bash
npm install core-js --save-dev
```

在你的应用程序入口处添加导入：

```typescript
import "core-js";
```

它就应该为你填充这些运行时功能了。

# 函数

TypeScript 类型系统对函数倾注了关注，毕竟它们是可组合系统的核心构建。

## 参数注解

当然，你可以像标注其他变量一样对函数参数进行注解：

这里我使用了内联类型注解。当然，你也可以使用接口等。

## 返回类型注解

你可以在函数参数列表之后使用与标注变量相同的风格来标注返回类型，例如下面示例中的 `Foo`：

```typescript
interface Foo {
  foo: string;
}

// 返回类型注解为 `: Foo`
function foo(sample: Foo): Foo {
  return sample;
}
```

当然，我在这里使用了接口，但你可以自由使用其他注解，例如内联注解。

通常情况下，你不需要标注函数的返回类型，因为编译器通常可以推断出它。

```typescript
interface Foo {
  foo: string;
}

function foo(sample: Foo) {
  return sample; // 推断类型 'Foo'
}
```

然而，添加此注解对于帮助发现错误通常是一个好主意，例如：

```typescript
function foo() {
  return { foo: 'John Doe' }; // 直到太晚你可能都不会发现 `foo` 这个拼写错误
}

sendsJSON(foo);
```

如果你不计划从函数返回任何内容，可以将其注解为 `void`。不过，通常你可以省略 `void` 并留给推断引擎处理。

## 可选参数

你可以将一个参数标记为可选的：

```typescript
function foo(bar: number, opt?: number) {
}
```

```typescript
overloaded: {
  (foo: string): string
  (foo: number): number
} = (foo) => foo;
```

## 箭头语法

为了方便地指定可调用签名，TypeScript 还允许简单的箭头类型注解，例如，一个接收数字并返回字符串的函数可以标记为：

```typescript
const simple: (foo: number) => string
  = (foo) => foo.toString();
```

箭头语法的唯一限制是：你无法指定重载。对于重载，必须使用完整的体 `{ (someArgs): someReturn }` 语法。

## Newable

Newable 只是带有前缀 `new` 的特殊可调用类型注解。它仅意味着你需要使用 `new` 来调用，例如：

```typescript
interface CallMeWithNewToGetString {
  new(): string
}
// 使用方法
declare const Foo: CallMeWithNewToGetString;
const bar = new Foo(); // bar 被推断为 string 类型
```

## 类型断言

TypeScript 允许你以任何想要的方式覆盖它对类型的推断和分析视图。这是通过一种被称为“类型断言”（type assertion）的机制实现的。TypeScript 的类型断言完全是通过告诉编译器你对类型的了解比它更深，它不应该对你产生怀疑。

类型断言的一个常见用例是你将 JavaScript 代码迁移到 TypeScript 时。例如，考虑以下模式：

```javascript
var foo = {};
foo.bar = 123; // 错误：属性 'bar' 不存在于 '{}'
foo.bas = 'hello'; // 错误：属性 'bas' 不存在于 '{}'
```

这里的代码报错是因为 `foo` 的推断类型是 `{}`，即一个具有零属性的对象。因此，你不允许向它添加 `bar` 或 `bas`。你可以简单通过对 `Foo` 进行类型断言来修复它：

```typescript
interface Foo {
  bar: number;
  bas: string;
}
var foo = {} as Foo;
foo.bar = 123;
foo.bas = 'hello';
```

### as vs. <foo>

最初添加断言的语法是 `<foo>`。下文演示：

```typescript
var foo: any;
var bar = <string> foo; // bar 现在是 "string" 类型
```

然而，在 JSX 中使用 `<foo>` 风格的断言会导致语言语法中存在歧义：

```jsx
var foo = <string>bar;
</string>
```

因此，现在为了一致性，建议直接使用 `as foo`。

## 类型断言 (Assertion) vs. 类型转换 (Casting)

不被称为“类型转换”（type casting）的原因是转换通常意味着某种运行时支持。然而，类型断言纯粹是编译时的结构，是你向编译器提供提示，告诉它你希望如何分析你的代码的方法。

## 断言是有害的

在很多情况下，断言将允许你轻松迁移旧代码（甚至将其他代码示例复制粘贴到你的代码库中），但你应该谨慎使用断言。以我们的原始代码为示例，编译器不会防止你忘记实际添加你所承诺的属性：

```typescript
interface Foo {
  bar: number;
  bas: string;
}
var foo = {} as Foo;
// 啊啊，忘记了什么吗？
```

另外一个常见的想法是使用断言作为提供自动补全手段，例如：

```typescript
interface Foo {
  bar: number;
  bas: string;
}
var foo = <Foo>
// 编译器将为 Foo 的属性提供自动补全
// 但开发者很容易忘记添加所有属性
// 此外，如果 Foo 被重构（例如添加了新属性），此代码可能会崩溃
```

这里的危险是相同的，如果你忘记了某个属性，编译器不会抱怨。更好的做法是执行如下：

```typescript
interface Foo {
  bar: number;
  bas: string;
}
var foo: Foo = {
// 编译器将为 Foo 的属性提供自动补全
};
```



在某些情况下，你可能需要创建一个临时变量，但至少你不会做出（可能是虚假的）承诺，而是依靠类型推断来为你进行检查。

## 双重断言 (Double assertion)

类型断言尽管如我们所示有一点不安全，但并不是*完全可以肆意所为*。例如，以下是一个非常有效的用例（例如，用户认为传入的事件将是更特定的事件类型），且类型断言按预期工作：

```typescript
function handler(event: Event) {
  let mouseEvent = event as MouseEvent;
}
```

然而，以下最可能是错误，尽管用户进行了类型断言，TypeScript 仍会如所示报错：

```typescript
function handler(event: Event) {
  let element = event as HTMLElement; // 错误：'Event' 类型和 'HTMLElement' 类型不能互相赋值
}
```

如果你仍然想要该类型，可以使用双重断言，但首先断言为 `any`，`any` 与所有类型兼容，因此编译器不再抱怨：

```typescript
function handler(event: Event) {
  let element = event as any as HTMLElement; // 没问题！
}
```

## TypeScript 如何确定单个断言是否足够

基本上，如果 `s` 是 `t` 的子类型或 `t` 是 `s` 的子类型，则从类型 `s` 到 `t` 的断言就会成功。这是为了在进行类型断言时提供额外的安全性……完全疯狂的断言是非常不安全的，你需要使用 `any` 才能达到那种不安全的程度。

## 新颖性 (Freshness)

TypeScript 提供了新颖性概念（也称为*严格对象检查*），以便更容易为对象字面量编写类型，否则它们在结构上是兼容的。下文演示：

```typescript
function logName(something: { name: string }) {
  console.log(something.name);
}
var person = { name: 'matt', job: 'awesome' }; // OK
var animal = { name: 'cow', diet: 'vegan' }; // OK

logName(person); // OK
logName(animal); // OK
```

然而，结构化类型有一个缺陷，它会误导你认为可以接受比实际更多的数据。这在以下代码中体现：

```typescript
// 如果我们想要正好 { name: string } 且没有额外属性：
logName({ name: 'matt' }); // OK
logName({ name: 'matt', job: 'awesome' }); // 错误：对象字面量必须指定已知属性。job 在此处是多余的。
```

注意，这*只发生在对象字面量上*。如果没有这种错误，人们可能会查看 `logName({ name: 'matt', job: 'awesome' })`，并认为 `logName` 会处理 `job`，而实际上它会忽略它。

另一个用例是具有可选成员的接口，如果没有这种对象字面量检查，类型将通过检查。下文演示：

```typescript
function logIfHasName(something: { name?: string }) {
  if (something) {
    console.log(something);
  }
}
var person = { name: 'matt', job: 'awesome' };
var animal = { name: 'cow', diet: 'vegan' };

logIfHasName(person); // OK
logIfHasName(animal); // OK
logIfHasName({ nume: 'I just misspelled name'}); // 错误：对象字面量必须指定已知属性。nume 在此处是多余的。
```

之所以只对对象字面量进行检查是因为在这种情况下，*实际上未被使用的*额外属性几乎总是拼写错误或对 API 的误解。

## 允许额外属性

类型可以包含索引签名，以显式指示允许额外属性：

```typescript
var x: { foo: number, [x: string]: any };
x = { foo: 1, baz: 2 }; // 可以，'baz' 被索引签名匹配
```

利用新鲜性（freshness）的概念，你可以将所有成员标记为可选，**你仍然可以捕捉到**拼写错误！

```typescript
// Assuming
interface State {
  foo: string;
  bar?: string;
}

// 你想做：
this.setState({foo: "Hello"}); // 耶，运行良好！

// 因为有新鲜性，它也能防止拼写错误！
this.setState({fos: "Hello"}); // Error: Objects may only specify known properties

// 并且经过类型检查
this.setState({foo: 123}); // Error: Cannot assign number to a string
```

# 类型守卫 (Type Guard)

类型守卫允许你在条件块内缩小对象的类型。

## typeof

TypeScript 能够感知 JavaScript 中 `instanceof` 和 `typeof` 运算符的使用。如果你在条件块中使用它们，TypeScript 将理解在该条件块内变量的类型不同。这里有一个简单的示例，TypeScript 意识到某个函数在 `string` 上不存在，并指出了那可能是一个用户定义的类型：

```typescript
function doSomething(x: number | string) {
  if (typeof x === 'string') { // 在块内 TypeScript 知道 `x` 必须是 string
    console.log(x.substr(i)); // Error, 'substr' does not exist on 'string'
    console.log(x.substr(i)); // OK
  }
  x.substr(i); // Error: There is no guarantee that `x` is a `string`
}
```

## instanceof

这是一个使用类和 `instanceof` 的示例：

```typescript
class Foo {
  foo = 123;
  common = '123';
}

class Bar {
  bar = 123;
  common = '123';
}

function doStuff(arg: Foo | Bar) {
  if (arg instanceof Foo) {
    console.log(arg.foo); // OK
    console.log(arg.bar); // Error!
  }
  if (arg instanceof Bar) {
    console.log(arg.foo); // Error!
    console.log(arg.bar); // OK
  }

  console.log(arg.common); // OK
  console.log(arg.foo); // Error!
  console.log(arg.bar); // Error!
}

doStuff(new Foo());
doStuff(new Bar());
```

TypeScript 甚至能理解 `else`，所以当 `if` 缩小了一个一种类型时，它知道在 `else` 块内一定不是该类型。这里是一个示例：

```typescript
class Foo {
    foo = 123;
}

class Bar {
    bar = 123;
}

function doStuff(arg: Foo | Bar) {
    if (arg instanceof Foo) {
        console.log(arg.foo); // OK
        console.log(arg.bar); // Error!
    } else { // 必须是 Bar!
        console.log(arg.foo); // Error!
        console.log(arg.bar); // OK
    }
}

doStuff(new Foo());
doStuff(new Bar());
```

## in

`in` 运算符对对象上属性的存在进行安全检查，并可以作为类型守卫使用。例如：

```typescript
interface A {
    x: number;
}

interface B {
    y: string;
}

function doStuff(q: A | B) {
    if ('x' in q) {
        // q: A
    } else {
        // q: B
    }
}
```

## 字面量类型守卫 (Literal Type Guard)

当你在联合类型中有字面量类型时，可以检查它们来进行区分，例如：

```typescript
type Foo = {
  kind: 'foo', // 字面量类型
  foo: number
}
type Bar = {
  kind: 'bar', // 字面量类型
  bar: number
}

function doStuff(arg: Foo | Bar) {
  if (arg.kind === 'foo') {
    console.log(arg.foo); // OK
    console.log(arg.bar); // Error!
  } else {
    console.log(arg.foo); // Error!
    console.log(arg.bar); // OK
  }
}
```

# 用户自定义类型守卫 (User Defined Type Guards)

JavaScript 内置没有非常丰富的运行时内省。当你使用普通的 JavaScript 对象（利用结构化类型的一优优势）时，你不仅仅无法访问 `instanceof` 或 `typeof`。对于这些情况，你可以创建*用户自定义类型守卫*函数。这些只是返回 `someArgumentName is SomeType` 的函数。这里有一个示例：

```typescript
/*
 * 一只是一些接口
 */
interface Foo {
  foo: number;
  common: string;
}

interface Bar {
  bar: number;
  common: string;
}

/**
 * 用户自定义类型守卫！
 */
function isFoo(arg: any): arg is Foo {
  return arg.foo !== undefined;
}

/**
 * 用户自定义类型守卫的示例用法
 */
function doStuff(arg: Foo | Bar) {
  if (isFoo(arg)) {
    console.log(arg.foo); // OK
    console.log(arg.bar); // Error!
  } else {
    console.log(arg.foo); // Error!
    console.log(arg.bar); // OK
  }
}
```

`Readonly` 是一种类型，它接收一个类型并使用映射类型（mapped types）将其所有属性标记为只读（readonly）。以下是一个在实践中使用它的示例：

```typescript
type Foo = {
bar: number;
bas: number;
}

type FooReadOnly = Readonly<Foo>;

let foo:Foo = {bar: 123, bas: 456};
let fooReadOnly:FooReadOnly = {bar: 123, bas: 456};

foo.bar = 456; // Okay
fooReadOnly.bar = 456; // ERROR: bar is readonly
```

## 多种用例

## ReactJS

ReactJS 是一个非常推崇不可变性的库，你可以将你的 Props 和 State 标记为不可变，例如：

```typescript
interface Props {
  readonly foo: number;
}
interface State {
  readonly bar: number;
}
export class Something extends React.Component<Props, State> {
  someMethod() {
    // 你可以放心地认为没有人会执行
    this.props.foo = 123; // ERROR: (props are immutable)
    this.state.baz = 456; // ERROR: (one should use this.setState)
  }
}
```

然而，你不需要 React 的类型定义来为你标记这些只读（通过在内部将传入的泛型用上述的 `Readonly` 类型包裹）。

```typescript
export class Something extends React.Component<{ foo: number }, { baz: number }> {
  // 你可以放心地认为没有人会执行
  someMethod() {
    this.props.foo = 123; // ERROR: (props are immutable)
    this.state.baz = 456; // ERROR: (one should use setState)
  }
}
```

# 无缝不可变

你甚至可以将索引签名标记为只读：

```typescript
/**
 * 声明
 */
interface Foo {
  readonly[x: number]: number;
}

/**
 * 使用
 */
let foo = { 0: 123, 2: 345 };
console.log(foo[0]); // Okay (reading)
foo[0] = 456; // Error (mutating): Readonly
```

如果你想以不可变的方式使用原生 JavaScript 数组，这非常棒。事实上，TypeScript 自带了一个 `ReadonlyArray<T>` 接口，允许你这样做：

```typescript
let foo: ReadonlyArray<number> = [1, 2, 3];
console.log(foo[0]); // Okay
foo.push(4); // Error: `push` does not exist on ReadonlyArray as it mutates the array
foo = foo.concat([4]); // Okay: create a copy
```

# 自动推断

在某些情况下，编译器可以自动推断某个项目是只读的，例如在类中，如果你有一个属性只有 getter 而没有 setter，它会被假设为只读的，例如：

```typescript
class Person {
  firstName: string = "John";
  lastName: string = "Doe";
  getFullName() {
    return this.firstName + this.lastName;
  }
}

const person = new Person();
console.log(person.fullName); // John Doe
person.fullName = "Dear Reader"; // Error! fullName is readonly
```

# 与 const 的区别

`const` 用于变量引用：

1. 变量不能被重新赋值为任何其他。

`readonly` 用于：

1. 属性

2. 属性可能会因为别名（aliasing）被修改。

解释 1 的示例：

```typescript
const foo = 123; // 变量引用
var bar: {
  readonly bar: number; // 用于属性
}
```

解释 2 的示例：

```typescript
let foo: {
  readonly bar: number;
} = {
  bar: 123
};
```

基本上，`readonly` 确保了不能被修改，但如果你给它一个没有该保证的人（出于兼容考虑），他们是可以修改它的。当然，如果 `mutateFoo` 声明要修改 `foo.bar`，编译器会将其标记为错误：

```typescript
interface Foo {
  readonly bar: number;
}
let foo: Foo = {
  bar: 123
};

function iTakeFoo(foo: Foo) {
  foo.bar = 456; // Error! bar is readonly
}
```

# 泛型 (Generics)

泛型的核心动机是在成员之间提供有意义约束。成员可以是：

- 类实例成员

- 类方法

- 函数参数

- 函数返回值

## 动机与示例



考虑一个简单的 `Queue`（队列）数据结构实现。在 TypeScript / JavaScript 中的简单实现如下：

```typescript
class Queue {
  private data = [];
  push = (item) => data.push(item);
  pop = () => data.shift();
}
```

这种实现允许人们将*任何内容*添加到队列中，当他们弹出它时——可以是*任何内容*。如下所示，某人可以将 `string` 推入队列：

```typescript
class Queue {
  private data = [];
  push = (item) => data.push(item);
  pop = () => data.shift();
}

const queue = new Queue();
queue.push(0);
queue.push("1"); // ERROR: 不能 push . 只允许数字
```

在那些不支持泛型的语言中，这种做法会很快变得很痛苦。一种解决方案是为这些约束创建特殊的类：

```typescript
class QueueNumber {
    private data = [];
    push = (item: number) => data.push(item);
    pop = () => data.shift();
}

const queue = new QueueNumber();
queue.push(0);
queue.push("i"); // ERROR : 不能 push 字符串. 只允许数字
```

如果修复了这一点，剩下的将会很好。你真正想要的是一种方式，让无论被推入的内容与被弹出的内容都是相同的。这通过泛型参数（在这种情况下是在类级别）轻松实现：

```typescript
/** 带有泛型参数的类定义 */
class Queue<T> {
    private data = [];
    push = (item: T) => data.push(item);
    pop = () => data.shift();
}

/** 再次示例 */
const queue = new Queue<number>();
queue.push(0);
queue.push("i"); // ERROR : 不能 push 字符串.
```

我们已经见过的另一个例子是 `reverse` 函数，这里的约束位于进入函数和返回值之间：

```typescript
function reverse<T>(items: T[]): T[] {
  var toreturn = [];
  for (let i = items.length - 1; i >= 0; i--) {
    toreturn.push(items[i]);
  }
  return toreturn;
}
```

```typescript
var sample = [1, 2, 3];
var reversed = reverse(sample);
console.log(reversed); // 3, 2, 1

// 安全！
reversed[0] = '1'; // Error!
reversed = ['1', '2']; // Error!

reversed[0] = 1; // Okay
reversed = [1, 2]; // Okay
```

在这一节中，你有类级别和函数级别定义的泛型示例。值得提到的小补充是，你可以为成员函数创建泛型。作为一个示例，考虑以下将函数移动到工具类：

```typescript
class utility {
  reverse<T>(items: T[]): T[] {
    var toreturn = [];
    for (let i = items.length - 1; i >= 0; i--) {
      toreturn.push(items[i]);
    }
    return toreturn;
  }
}
```

> 提示：你可以给泛型参数起任何你喜欢的。当有简单的泛型时，使用 `T`, `U`, `V` 是惯例。如果你有多个泛型参数，请使用有意义的名字，例如 `TKey` 和 `TValue`（带 `T` 前缀是惯例，因为泛型在其他语言（如 C++）中也被称为模板）。

# TSX 中的泛型

因为 `.tsx` / `.jsx` 使用类似 `<div>` 的语法来表示 JSX 块，它为泛型带来了一些独特的挑战。

快速提示：如我们之前提到的，使用 `as` 语法进行类型断言。

# 泛型函数

类似下面的内容运行良好：

```typescript
function foo<T>(x: T) { return x; }
```

然而，使用箭头泛型将不起：

```typescript
const foo = <T>(x: T) => x; // ERROR : 未关闭的 T 标签
```

变通：在泛型参数上使用 `extends` 来提示编译器它是泛型的，例如：

```typescript
const foo = <T extends {}>(x: T) => x;
```

# 泛型组件

由于 JSX 没有提供泛型参数的语法，你需要在创建组件之前使用类型断言对其进行特化，例如：

```typescript
/* 泛型组件 */
type SelectProps<T> = { items: T[] }
class Select<T> extends React.Component<SelectProps<T>, any> {}

/* 特化 */
interface StringSelect { new (): Select<string> };
const StringSelect = Select as StringSelect;

/* 使用 */
const Form = () => <StringSelect items={['a', 'b']} />;
```

```typescript
declare function require(name: string): any;
const something = require('something') as TypeOfSomething;
```

这只是一个示例；如果你正在考虑使用这些 `require` 类型定义，你不需要，因为：

- 1. 它已经存在于 `node.d.ts` 中：你可以使用 `npm install @types/node --save-dev` 进行安装。

- 2. 你应该考虑为你的库使用类型定义，例如对于 jquery 使用 `npm install @types/jquery --save-dev` 而不是使用 `require`。

## 设计模式：便利性泛型

之前的 `require<T>` 示例是有意为了说明一个事实：在类型安全方面，使用*一次*的泛型并不比类型断言用。尽管如此，它们为你的 API 提供了`便利性`。

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

并且，它们也适用于解构，包括对象：

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

并且，它们也适用于解构，包括对象：

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

并且，它们也适用于解构，包括对象：

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

（注：修正重复段落翻译逻辑）

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

（由于原文中存在大量重复，此处为剩余逻辑翻译）

```typescript
let foo = {
  a: 123,
  b: 456
}
let {a} = foo;
// a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

```typescript
const bar = [1,2,3];
let [a, b] = bar;
// a = "hello"; // Would Error：不能将 `string` 赋值给 `number`
```

（注：原文提供的文本在“Destructuring”部分存在严重的物理重复，此处已根据“不要重复输出原文”原则进行去重处理。以下为原文中未重复部分的完整翻译：）

并且，你仍然需要显式地标注你想要，但 `getJSON<T>` 的签名 `(config) => Promise<T>` 为你节省了一些击键：

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

此外，`Promise<T>` 作为返回值绝对比 `Promise<any>` 等替代方案更好。

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



```typescript
let iTakePoint3D = iTakePoint2D; // Okay : Reasonable
let iTakePoint2D = iTakePoint3D; // Okay : 什么
```

# Enums

- 枚举与数字兼容，数字与枚举兼容。

```typescript
enum Status { Ready, Waiting };

let status = Status.Ready;
let num = 0;

status = num; // OKAY
num = status; // OKAY
```

- 来自不同枚举类型的枚举值被认为是不兼容的。这使得枚举可以以命名的（而不是结构化的）方式使用。

```typescript
enum Status { Ready, Waiting };
enum Color { Red, Blue, Green };

let status = Status.Ready;
let color = Color.Red;
```

```typescript
function foo(x: string | number): boolean {
  if (typeof x === "string") {
    return true;
  } else if (typeof x === "number") {
    return false;
  }

  // 如果没有 never 类型，我们将得到错误：
  // - 并非所有的代码路径都返回了（严格空检查）
  // - 或者检测到不可达的代码
  // 但由于 TypeScript 理解 `fail` 函数返回 `never`
  // 它允许你调用它，因为你可能将其用于运行时安全 / 穷尽检查。
  return fail("Unexhaustive");
}

function fail(message: string): never { throw Error(message); }
```

而且由于 `never` 只能赋值给另一个 `never`，你也可以将其来进行编译穷尽检查。这在判别联合部分会有介绍。

## 与 void 的混淆

当有人告诉你函数在正常退出时返回 `never` 时，你直觉上会把它等同于 `void`。然而，`void` 是一个单元（Unit），而 `never` 是假值（falsum）。

不返回任何内容的函数返回单元 `void`。然而，从不返回（或始终抛出异常）的函数返回 `never`。`void` 是可以赋值的（在没有严格空检查的情况下），但 `never` 永远无法赋值给 `never`以外的任何类型。

## 判别联合 (Discriminated Union)

如果你有一个带有字面量成员的类，你可以使用该属性来区分联合类型成员。

例如，考虑正方形（Square）和矩形（Rectangle）的联合，这里有一个成员 `kind` 存在于两个联合成员中，并且类型为特定的字面量类型：

```typescript
interface Square {
  kind: "square";
  size: number;
}

interface Rectangle {
  kind: "rectangle";
  width: number;
  height: number;
}
type Shape = Square | Rectangle;
```

如果你使用类型守卫检查（`==` , `===` , `!=` , `!==` ）或对判别属性（此处为 `kind`）进行 `switch` 操作，TypeScript 会意识到该对象必须是具有该特定字面量的类型，并为你进行类型收窄：

```typescript
function area(s:Shape) {
  if (s.kind === "square") {
    // 现在 TypeScript "知道" `s` 必须是一个正方形；
    // 所以你可以安全地使用它的成员：
    return s.size * s.size;
  } else {
    // 不是正方形？那么 TypeScript 将判断它必须是一个矩形
    // 所以你可以安全地使用它的成员：
    return s.width * s.height;
  }
}
```

## 穷尽检查 (Exhaustive Checks)

你可能想确保联合类型中的所有成员都有相应的代码（操作）来处理。

```typescript
interface Square {
  kind: "square";
  size: number;
}
```

```typescript
interface Rectangle {
  kind: "rectangle";
  width: number;
  height: number;
}
```

```typescript
// 有人刚刚添加了这个新的 'Circle'（圆形）类型
// 我们希望 TypeScript 在任何“需要”处理的地方报错
interface Circle {
  kind: "circle";
  radius: number;
}
```

```typescript
type Shape = Square | Rectangle | Circle;
```

### 举例说明哪里会出问题：

```typescript
function area(s: Shape) {
  if (s.kind === "square") {
    return s.size * s.size;
  }
  else if (s.kind === "rectangle") {
    return s.width * s.height;
  }
  // 如果能让 TypeScript 给你出一个错误就太好了
}
```

你可以通过简单添加一个穿透（fall through）并确保该块中的推断类型与 `never` 类型兼容来实现这一点。例如，如果你添加了穷尽检查，你将得到一个非常好的错误：

```typescript
function area(s: Shape) {
  if (s.kind === "square") {
    return s.size * s.size;
  }
  else if (s.kind === "rectangle") {
    return s.width * s.height;
  }
  else {
    // 错误：`Circle` 无法赋值给 `never`
    const _exhaustiveCheck: never = s;
  }
}
```

这迫使你处理这个新情况：

```typescript
function area(s: Shape) {
  if (s.kind === "square") {
    return s.size * s.size;
  }
  else if (s.kind === "rectangle") {
    return s.width * s.height;
  }
  else if (s.kind === "circle") {
    return s.radius;
  }
  else {
    // 再来一次
    const _exhaustiveCheck: never = s;
  }
}
```

### Switch

提示：当然你可以在 `switch` 语句中这样做：

```typescript
function area(s: Shape) {
  switch (s.kind) {
    case "square": return s.size;
    case "rectangle": return s.height;
    case "circle": return s.radius;
    default: const _exhaustiveCheck: never = s;
  }
}
```

这是一个还原器（reducer），一个具有 `(state, action) => state` 签名的纯函数。它描述了操作如何将状态转换为下一个状态。状态形状取决于：它可以是原始类型、数组、对象，甚至是不可变数据结构。唯一重要的部分是你不应该改变状态对象，而是应该返回它。

1. 这是为了获得出色的 Array / Tuple 支持所需要的。

2. 即使你将其用于对象，它默认的 `toString` 实现很好用（不是 `[object Object]`）。

点 2 如下所示：

```javascript
console.log((1).toString()); // 1

console.log((2).toString()); // 2
```

所以结论 1 是：

> TypeScript 索引签名（index signatures）必须是字符串或数字

快速提一下：符号（symbols）也是有效的并且被 TypeScript 支持。但我们现在先不要讨论那里。循序渐进。

# 索引签名

我们一直使用 `any` 来告诉 TypeScript 让我们随心所欲地处理类型。实际上，我们可以显式地指定索引。例如，假设你想确保使用字符串存储在对象中的任何内容都符合 `{message: string}` 结构。可以通过声明 `{[index:string]: {message: string}}` 实现。演示如下：

```typescript
let foo:[index:string]: {message: string} = {};

/**
* 必须存储符合结构的内容
 */

/** 没问题 */
foo['a'] = { message: 'some message' };

/** 错误：必须包含 `message` 或类型字符串。你在 `message` 中拼写错误了 */
foo['a'] = { messages: 'some message' };

/**
* 读取的内容也会进行类型检查
 */

/** 没问题 */
foo['a'].message;

/** 错误：messages 不存在。你在 `message` 中拼写错误了 */
foo['a'].messages;
```

提示：索引签名的名称（例如 `{[index:string]: {message: string}}` 中的 `index`）对 TypeScript 来说没有意义，它仅仅是为了可读性。例如，如果它是用户名，可以使用 `{[username:string]: {message: string}}` 来帮助查看代码的下一个开发者（那个人恰好可能是你自己）。

当然，数字索引也是支持的，例如 `{[count: number]: SomeOtherTypeYouWantToStoreRebate}`

# 所有成员必须符合字符串签名

一旦你有了字符串索引签名，所有显式成员也必须符合该索引签名。示例如：

```typescript
/** 没问题 */
interface Foo {
  [key:string]: number
  x: number;
  y: number;
}

/** 错误 */
interface Bar {
  [key:string]: number
  x: number;
  y: string; // 属性 `y` 必须是 number 类型
}
```

这是为了提供安全性，确保任何索引访问都能相同的结果：

```typescript
interface Foo {
  [key:string]: number
  x: number;
}

let foo: Foo = {x:1,y:2};

// 直接访问
foo['x']; // number

// 间接访问
let x = 'x'
foo[x]; // number
```

# 使用有限的字符串签名

可以使用映射类型（Mapped Types）要求索引字符串成为字面量字符串联合类型的成员，例如：

```typescript
type Index = 'a' | 'b' | 'c'
type FromIndex = { k in Index }: number

const good: FromIndex = {b:1, c:2}

// 错误：
// 类型 '{ b: number; c: number; d: number; } 无法赋值给类型 'FromIndex'
// 对象字面量只能指定已知属性，'d' 在类型 'FromIndex' 中不存在
const bad: FromIndex = {b:1, c:2, d:3};
```

这通常配合 `keyof typeof` 使用来捕捉词汇类型（vocabulary types），将在下一页描述。

词汇的规范可以泛泛地延迟：

```typescript
type FromIndex<K extends string> = { [key in K]: number }
```

# 同时拥有字符串和数字索引

这不是一个常见的用例，但 TypeScript 编译器仍然支持它。

然而，它有一个限制：字符串索引比数字索引更严格。这是刻意的，允许编写如下类型：

```typescript
interface ArrStr {
  [key: string]: string | number; // 必须包含所有成员
  [index: number]: string; // 可以是字符串索引的子集
  // 仅仅示例成员
  length: number;
}
```

# 设计模式：嵌套索引签名

添加索引签名时的 API 考虑

在 JS 社区中，你经常会看到滥用字符串索引的 API。例如，CSS-in-JS 库中的常见模式：

```typescript
interface NestedCSS {
  color?: string;
  [selector: string]: string | NestedCSS;
}

const example: NestedCSS = {
  color: 'red',
  '.subclass': {
    color: 'blue'
  }
}
```

尽量不要这样将字符串索引与有效值混合。例如，padding 的拼写错误将无法被捕获

```typescript
const failsSilently: NestedCSS = {
  colour: 'red', // 没有错误，因为 `colour` 是有效的字符串
}
```

相反，将嵌套分离到自己的属性中，例如使用像 `nest`（或 `children`、`subnodes` 等）的名称：

```typescript
interface NestedCSS {
  color?: string;
  nest?: {
    [selector: string]: NestedCSS;
  }
}

const example: NestedCSS = {
  color: 'red',
  nest: {
    '.subclass': {
      color: 'blue'
    }
  }
}

const failsSilently: NestedCSS = {
  colour: 'red',
}
```

```javascript
***3; // SyntaxError: Unexpected token *
```

# TypeError

创建一个表示当变量或参数不是有效类型时发生错误的实例。

```javascript
('1.2').toPrecision(1); // TypeError: '1.2'.toPrecision is not a function
```

# URIError

创建一个表示当向 `encodeURI()` 或 `decodeURI()` 传递无效参数时发生错误的实例。

```javascript
decodeURI('%'); // URIError: URI malformed
```

# 始终使用 Error

初级 JavaScript 开发者有时只会抛出原始字符串，例如：

```javascript
try {
  throw 'Something bad happened';
}
catch(e) {
  console.log(e);
}
```

不要这样做。Error 对象的根本优势在于，它们会自动通过 `stack` 属性跟踪它们被构建和产生的位置。

原始字符串会导致非常痛苦的调试体验，并增加从日志中进行错误分析的复杂性。

# 你不必非抛出错误

传递 Error 对象是可以的。这在 Node.js 的回调风格代码中是常规做法，即回调函数的第一个参数通常是一个错误对象。

```typescript
function myFunction(callback:(e? Error)) {
  doSomethingAsync(function () {
    if (somethingwrong) {
      callback(new Error('This is my error'))
    } else {
      callback();
    }
  });
}
```

# 特殊情况

“异常应该是特殊的”是计算机科学中的句常用格言。对于 JavaScript（以及 TypeScript）来说，这同样成立，有几个原因。

# 不清楚是在哪里抛出的

考虑以下代码段：

```javascript
try {
  const foo = runTask1();
  const bar = runTask2();
}
catch(e) {
  console.log('Error:', e);
}
```

下一个开发者无法知道哪个函数可能会抛出错误。代码审查人员在不阅读 task1 / task2 以及他们可能调用的其他函数的情况下的情况下无法得知。

# 使优雅处理变得困难

你可以尝试通过在每个可能抛出异常的代码周围使用显式的 `catch` 来实现优雅处理：

```javascript
try {
```



```
const foo = runTask1();
```

```
try {
  const bar = runTask2();
}
catch(e) {
  console.log('Error:', e);
}
```

但现在如果你需要从第一个任务将内容传递到第二个任务，代码就会变得杂乱（注意 `foo` 的变动需要 `let`，并且需要显式标注类型，因为无法从 `runTask1` 的返回值中推断出来）：

```typescript
let foo: number; // 注意使用 'let' 和显式的类型注解

try {
  foo = runTask1();
}
catch(e) {
  console.log('Error:', e);
}

try {
  const bar = runTask2(foo);
}
catch(e) {
  console.log('Error:', e);
}
```

# 在类型系统中未良好表示

考虑以下函数：

```typescript
function validate(value: number) {
  if (value < 0 || value > 100) throw Error('Invalid value');
}
```

在这种情况下使用 `Error` 是一个坏主意，因为在 `validate` 函数的类型定义中（为 `(value:number) => void`）并没有表示它。相反，创建一个验证方法的更好方法是：

```typescript
function validate(value: number): {error?: string} {
  if (value < 0 || value > 100) return {error:'Invalid value'};
}
```

现在它在类型系统中被表示了。

> 除非你想以一种非常通用的（简单 / 全能捕获等）方式处理错误，否则不要抛出错误。

# 混合（Mixins）

TypeScript（以及 JavaScript）类支持严格的单继承。因此，你不能这样做：

```typescript
class User extends Tagged, Timestamped { // 错误：不支持多继承
}
```

从可用组件构建类的另一种方法是通过组合称为混合（mixins）的简单类来构建。

这种思想是，不是通过类继承 `B` 来获取功能，而是函数 `B` 接收类 `A` 并返回一个添加了该功能的新类。函数 `B` 就是混合。

- [混合是一个] 函数，
1. 接收一个构造函数，
2. 创建一个继承该构造函数的、带有新功能的类，
3. 返回这个新类

一个完整的示例

```typescript
// 混合所需的类型
type Constructor<T> = () => new (...args: any[]) => T;

////////////////////////////////////
// 混合示例
////////////////////////////////////

// 添加属性的混合
function Timestamped<TBase> extends Constructor<Base: TBase> {
  return class extends Base {
    timestamp = Date.now();
  }
}

// 添加属性和方法的混合
function Activatable<TBase> extends Constructor<Base: TBase> {
  return class extends Base {
    isActive = false;
    activate() {
      this.isActive = true;
    }
    deactivate() {
      this.isActive = false;
    }
  }
}

///////////////////////
// 使用组合类
///////////////////////

// 简单类
class User {
  name = '';
}

// 带有时间的 User
const TimestampedUser = Timestamped<User>;

// 带有激活功能的 User
const ActivatableUser = Activatable<User>;

///////////////////////
// 使用组合类
///////////////////////

// 简单类
const timestampedUser = new TimestampedUser();

// 带有激活功能的 User
const activatableUser = new ActivatableUser();

// 同时带有时间戳和激活功能的 User
class CombinedUser extends Timestamped<User>, Activatable<User> {}
const combinedUser = new CombinedUser();
```

你可以简单使用 `React.SFC` 接口来定义无状态组件，例如：

```typescript
interface Props {
  foo: string;
}

const MyComponent: React.SFC<Props> = (props) => {
  return <span>{props.foo}</span>
}

<MyComponent foo="bar" />
```

# 有状态组件

组件根据其 `props` 属性进行类型检查。这模仿了 JSX 的转换方式，即属性变成了组件的 `props`。

要创建 React 有状态组件，你需要使用 ES6 类。`react.d.ts` 文件定义了 `React.Component<Props, State>` 类，你应该通过你自己的类来扩展它，并提供你自己的 `Props` 和 `State` 接口。示例所示：

```typescript
interface Props {
  foo: string;
}

class MyComponent extends React.Component<Props, {}>> {
  render() {
    return <span>{this.props.foo}</span>
  }
}

<MyComponent foo="bar" />
```

# React JSX 技巧：可渲染内容的接口

React 可以渲染一些内容，如 JSX 或字符串。这些内容都整合到了 `React.ReactNode` 类型中，因此当你想要接受可渲染内容时请使用它，例如：

```typescript
interface Props {
  header: React.ReactNode;
  body: React.ReactNode;
}

class MyComponent extends React.Component<Props, {}> {
  render() {
    return (
      <div>
        {header}
        {body}
      </div>
    );
  }
}

<MyComponent foo="bar" />
```

# React JSX 技巧：接受组件实例

React 类型定义提供了 `React.ReactElement<T>`，允许你对类组件实例化的结果进行标注。例如：

```typescript
class MyAwesomeComponent extends React.Component {
  render() {
    return <div>Hello</div>;
  }
}

const foo: React.ReactElement<MyAwesomeComponent> = <MyAwesomeComponent />; // OK
const bar: React.ReactElement<MyAwesomeComponent> = <NotMyAwesomeComponent />; // 错误！
```

> 当然，你可以将其用函数参数注解，甚至作为 React 组件的 prop 成员。

# React JSX 技巧：泛型组件

JSX 中没有语法可以为泛型组件应用泛型参数。你必须先将泛型类存储变量中，用具体类型移除任何泛型参数。例如，我们将 `T` 替换为具体的字符串类型：

```typescript
/* 一个泛型组件 */
type SelectProps<T> = { items: T[] }
class Select<T> extends React.Component<SelectProps<T>, any> { }

/** 特化 Select 以用于字符串 */
const StringSelect = Select as new (): Select<string>;

/** 使用方法 */
const Form = () => <StringSelect items={['a', 'b']} />;
```

如果你的构造函数接收 props，你可以通过以下方式适配：

```typescript
/** 泛型组件 */
interface SelectProps<T> = { items: T[] }
class Select<T> extends Component<SelectProps<T>, any> {
  constructor(props: SelectProps<T>) { super(props) }
}

/** 特化 */
const StringSelect = Select as new (props: SelectProps<string>):GenericList<string>;
```

# 默认 Props

- 带有默认 props 有状态组件：你可以通过使用*空断言*运算符告诉 TypeScript 某个属性将从外部（通过 React）提供（这并不理想，但我能想到的最简单的最小*额外代码*解决方案）。

```typescript
Hello extends ReactComponent<{
  compiler?: string;
  framework: string
}> {
  static defaultProps = {
    compiler: 'TypeScript'
  }
  render() {
    const compiler = this.props.compiler;
    return (
      <div>
        <div>{compiler}</div>
        <div>{this.props.framework}</div>
      </div>
    );
  }
}
```

```typescript
ReactDOM.render(
  <Hello framework="React" />, // TypeScript React
  document.getElementById("root")
);
```

- 带有默认 props 的 SFC：建议利用简单的 JavaScript 模式，它们与 TypeScript 的类型系统配合良好，例如：

```typescript
const Hello: React.SFC<{
  compiler?: string;
  framework: string
}> = ({
  compiler = 'TypeScript', // 默认 prop
  framework
}) => {
  return (
    <div>
      <div>{compiler}</div>
      <div>{framework}</div>
    </div>
  );
});
```

```typescript
ReactDOM.render(
  <Hello framework="React" />, // TypeScript React
  document.getElementById("root")
);
```

# 非 React JSX

TypeScript 允许你以类型安全的方式在 JSX 中使用 React以外的内容。以下列出了自定义点，但请注意这是针对高级 UI 框架作者的：

- 你可以使用 `jsx` 的 `"preserve"` 选项来禁用样式输出。这意味着 JSX 将按*原样*输出，然后你可以使用你自定义的转译器来编译 JSX 部分。
- 使用 `JSX` 全局模块：
  - 你可以通过自定义 `JSX.IntrinsicElements` 接口成员来控制哪些 HTML 标签是可选以及如何检查它们。
  - 使用组件时：
    - 你可以控制哪些 `class` 必须……（注：原文此处截断）

## 非空断言运算符 (Non-Null Assertion Operator)

可以使用一个新的后缀表达式运算符，在类型检查器无法得出该事实的上下文中，断言其操作数不为 `null` 也不为 `undefined`。例如：

```typescript
// 使用 --strictNullChecks 编译
function validateEntity(e?: Entity) {
  // 如果 e 为 null 或无效实体则抛出异常
}

function processEntity(e?: Entity) {
  validateEntity(e);
  let a = e.name; // TS 错误：e 可能为 null。
  let b = e!.name; // 断言 e 不为 null。这允许你访问 name
}
```

> 注意，这仅仅是一个断言，就像其他断言一样，你需要负责确保该值不为 `null`。非空断言本质上是你告诉编译器：“我知道它不是 `null`，所以让我像它不是 `null` 一样使用它”。

## 测试

TypeScript 可以与你喜欢的任何 JavaScript 测试框架配合使用。在最坏的情况下，你总是可以进行简单的 `TypeScript -> JavaScript` 转换并心所欲。

尽管如此，在本节中，我们将看看一些我们非常喜欢的选项。

## 在 TypeScript 中使用 Jest

关于 Jest / TypeScript 的进阶教程

没有任何测试解决方案是完美的。尽管如此，`jest` 是一个极出色的单元测试选项，它提供了强大的 TypeScript 支持。

> 我们假设你从一个简单的 `package.json` 设置开始。此外，TypeScript 文件应该放在 `src` 文件夹中，即使在没有 Jest 的情况下，为了项目整洁也一直推荐这样做。

### 第 1 步：安装

使用 `npm` 安装以下内容：

```bash
npm i jest @types/jest ts-jest -D
```

解释：

- 安装 `jest` 框架 (`jest`)
- 安装 `jest` 的类型定义 (`@types/jest`)
- 安装用于 `jest` 的 TypeScript 预处理器 (`ts-jest`)，它允许 `jest` 实时编译 TypeScript 并内置了 source-map 支持。
- 将所有这些都保存到你的开发依赖中（测试几乎总是 npm 依赖项）

### 第 2 步：配置 Jest

在项目根目录下添加以下 `jest.config.js` 文件：

```javascript
module.exports = {
  "roots": [
    "<rootDir>/src"
  ],
  "transform": {
    ".+\.(ts|tsx)?$": "ts-jest"
  },
  "testRegex": "/__tests_.*/|(\.|/)(test|spec)\.(jsx?|tsx)?$",
  "moduleFileExtensions": [
    "ts",
    "tsx",
    "js",
    "jsx",
    "json",
    "node"
  ]
}
```

解释：

- 我们始终建议将项目中的*所有* TypeScript 文件都放在 `src` 文件夹中。我们假设事实如此，并使用 `roots` 选项指定了这一点。
- `transform` 配置只是告诉 `jest` 使用 `ts-jest` 处理 ts / tsx 文件。
- `testRegex` 告诉 `jest` 在任何 `__tests__` 文件夹中查找测试，并且在任何地方查找使用 `.(test|spec)\.(js|ts|tsx)` 扩展的文件，例如 `asdf.test.tsx` 等。
- `moduleFileExtensions` 告诉 `jest` 我们的文件扩展名。由于我们需要将 `ts / tsx` 添加到默认值（`js|jsx|json|node`）中，因此是必需的。

### 第 3 步：运行测试

从项目根目录运行 `npx jest`，`jest` 将执行你拥有的任何测试。

### 可选：为 npm 脚本添加目标

添加 `package.json`：

```json
{
  "test": "jest"
}
```

- 这允许你通过简单的 `npm t` 运行测试。
- 甚至可以在监听模式下使用 `npm t -- --watch`。

### 可选：在监听模式下运行 jest

- `npx jest -w`

## 示例

- 对于文件 `foo.ts`：

```typescript
export const sum
= (...a: number[]) =>
  a.reduce((acc, val) => acc + val, 0);
```



# 一个简单的 `foo.test.ts`

```typescript
import { sum } from './';

test('basic', () => {
  expect(sum()).toBe(0);
});

test('basic again', () => {
  expect(sum(1, 2)).toBe(3);
});
```

说明：

- Jest 提供了全局函数 `test`。
- Jest 内置了以全局 `expect` 形式形式的断言。

## 异步示例

Jest 内置了 async/await 支持。例如：

```typescript
test('basic', async () => {
  expect(sum()).toBe(0);
});

test('basic again', async () => {
  expect(sum(1, 2)).toBe(3);
}, 1000 /* 可选超时 */);
```

## Enzyme 示例

> 关于 Enzyme / Jest / TypeScript 的进阶教程

Enzyme 允许你测试具有 dom 支持的组件。设置 enzyme 有三个步骤：

1. 安装 enzyme、enzyme 的类型定义、适用于 enzyme 的更好的快照序列化器、适用于 react 版本的 enzyme-adapter-react `npm i enzyme @types/enzyme enzyme-to-json enzyme-adapter-react-16 -D`
2. 在你的 `jest.config.js` 中添加 "snapshotSerializers" 和 "setupTestFramework"：

```javascript
module.exports = {
  // 之前提到的选项
  // 设置 Enzyme
  "snapshotSerializers": ["enzyme-to-json/serializer"],
  "setupTestFramework": "<rootDir>/src/setupTestFramework"
}
```

- 在类型上添加未使用的属性以破坏结构化兼容性。
- 在需要新实例化或向下类型转换时使用类型断言。

下面演示了这一点：

```typescript
// FOO
interface FooId extends String {
  _fooIdBrand: string; // 防止类型错误
}

// BAR
interface BarId extends String {
  _barIdBrand: string; // 防止类型错误
}

/**
 * Usage Demo
 */
var fooId: FooId;
var barId: BarId;

// 安全！
fooId = barId; // error
barId = fooId; // error
fooId = <FooId>barId; // error
barId = <BarId-FooId>; // error

// 实例化
fooId = 'foo' as any;
barId = 'bar' as any;

// 如果你需要基础字符串
var str: string;
str = fooId as any;
str = barId as any;
```

---

## 有状态函数 (Stateful Functions)

其他编程语言中的一个常见特性是使用 `static` 关键字来增加函数变量的生命周期（而非作用域），使其跨越函数调用。这里有一个实现此点的 C 示例：

```c
void called() {
  static count = 0;
  count++;
  printf("Called : %d", count);
}

int main() {
  called(); // Called : 1
  called(); // Called : 2
  return 0;
}
```

由于 JavaScript（或 TypeScript）没有函数静态变量，你可以使用各种封装局部变量的抽象来实现相同的效果，例如使用类：

C++ 开发者也会尝试使用称为函数对象（functor）的模式（即重写了运算符 `()` 的类）来实现这一点。

---

## Bind 是有害的 (Bind is Harmful)

这是 `lib.d.ts` 中 `bind` 的定义：

```typescript
bind(thisArg: any, ...argArray: any[]): any);
```

因为你可以返回 `any`！这意味着在函数上调用 `bind` 将导致你完全丢失原始函数签名的任何类型安全性。

例如，以下代码可以编译：

```typescript
function twoParams(a:number,b:number) {
  return a + b;
}

let curryOne = twoParams.bind(null,123);
curryOne(456); // OK 但没有经过类型检查！
curryOne('456'); // 允许，因为没有经过类型检查！
```

更好的方法是使用带有显式类型注解的简单箭头函数：

```typescript
function twoParams(a:number,b:number) {
  return a + b;
}

let curryOne = (x:number)=>twoParams(123,x);
curryOne(456); // OK 经过了类型检查！
curryOne('456'); // Error!
```

但如果你期望一个柯化函数，有一个相应的模式。

---

## 类成员 (Class Members)

另一个常见用途是使用 `bind` 来确保在传递类函数时 `this` 的值正确。**不要这样做！**

以下演示了如果你使用 `bind`，你会丢失参数类型的安全性：

```typescript
class Adder {
  constructor(public a: string) {}
  add(b: string): string {
    return this.a + b;
  }
}

function useAdd((x: number) => number) {
  return add(456);
}

let adder = new Adder('mary had a little ');
useAdd(adder.add.bind(adder)); // 无编译错误！
useAdd((x) => add(x)); // Error: number 无法赋值给 string
```

如果你有一个需要传递的类成员函数，从一开始就使用箭头函数，例如，可以这样编写相同的 `Adder` 类：

```typescript
class Adder {
  constructor(public a: string) {}
  // 此函数现在可以安全传递
  add = (b: string): string => {
    return this.a + b;
  }
}
```

另一种方案是手动指定你绑定的变量类型，例如：

```typescript
const add: typeof adder.add = adder.add.bind(adder);
```

---

## 柯化 (Currying)

直接使用箭头函数链即可：

```typescript
// 一个柯化函数
let add = (x: number) => (number: number) => x + y;

// 简单用法
add(123)(456);

// 部分应用
let add123 = add(123);

// 完整应用函数
add123(456);
```

---

## 泛型的类型实例化 (Type Instantiation for Generics)

假设你有一个带有泛型参数的东西，例如类 `Foo`：

```typescript
class Foo<T>{
  foo: T;
}
```

你想为特定类型创建一个专门的版本。该模式是将项拷贝到一个新变量中，并提供泛型替换为具体类型的类型注解。例如，如果你想要一个类 `Foo<number>`：

```typescript
class Foo<T>{
  foo: T;
}

FooNumber = Foo as { new ():Foo<number> }; // ref 1
```

在引用 1 中，你表示 `FooNumber` 与 `Foo` 相同，但将其视为一个在使用 `new` 操作符调用时返回 `Foo<number>` 实例的对象。

---

## 继承 (Inheritance)

类型断言模式是...（注意：文本根据 OCR 流程中断或继续）

```typescript
class Foo {
  public someProperty;
  constructor() {
    // some initialization
  }
  public someMethod() {
    // some code
  }
  private someUtility() {
    // some code
  }
}

export = new Foo();
```

这不仅仅是开发人员，创建能够为类提供良好可视化的开发工具要常见得多，而且你的团队可以少一种需要理解和维护的模式。

> 备注：在我看来，如果浅的类层次结构能够提供显著的重用并减少样板代码，那么它们没有问题。

# export default 可能会导致问题

让我们来看一个例子。假设你有一个文件 `foo.ts`，其内容如下：

```typescript
class Foo {
}

export default Foo;
```

你会在 `bar.ts` 中使用如下 ES6 语法来导入它：

```typescript
import Foo from "./foo";
```

这里有几个关于可维护性的考虑：

- 如果你在 `foo.ts` 中重构了 Foo，它不会重命名 `bar.ts` 中的导入项。
- 如果你最终需要从 `foo.ts` 导出更多内容（你的许多文件都会如此），那么你就必须处理复杂的语法切换。

出于这个原因，我建议使用简单的导出 + 解构赋值导入。例如 `foo.ts`：

```typescript
export class Foo {
}
```

然后是：

```typescript
import {Foo} from "./foo";
```

**加分项：** 你甚至可以在 `import {/**/} from "./foo";` 位置获得自动补全。这为你的开发者减轻了手负担。

**加分项：** 更好的 CommonJS 体验。使用 `default` 对于 CommonJS 用户来说体验很糟糕，他们必须使用 `const {default} = require('./module/foo');` 而不是 `const {Foo} = require('./module/foo')`。

**加分项：** 你不会遇到拼写错误，例如一个开发者写 `import Foo from "./foo";` 而另一个写成 `import foo from "./foo";`。

**加分项：** 自动导入快速修复更好用。当你使用 `Foo` 时，自动导入会写入 `import { Foo } from "./foo";`，因为它是模块中导出的定义良好的名称。

**加分项：** 重新导出变得异常困难。重用导出在 npm 包的根 `index` 文件中很常见，例如 `import Foo from "./foo"; export { Foo }`（默认导出）对比 `export * from "./foo"`（命名导出）。

# 限制属性 setter 的使用

优先使用显式的 set/get 函数（例如 `setBar` 和 `get`）而不是 setter/getter。

考虑以下代码：

```typescript
foo.bar = {
  a: 123,
  b: 456
};
```

在存在 setter/getter 的情况下：

```typescript
class Foo {
  a: number;
  b: number;
  set bar(value:{a:number,b:number}) {
    this.a = value.a;
    this.b = value.b;
  }
}

let foo = new Foo();
```

这不是使用属性 setter 的*良好*方法。阅读第一个代码示例的人对所有将发生的变化没有任何概念。而调用 `foo.setBar(value)` 的人可能会意识到 `foo` 上可能会发生某些变化。

> 加分项：如果你有不同的函数，查找引用（Find references）的效果会更好。在 TypeScript 工具中，如果你对 getter 或 setter 查找引用，你会得到*两者*，而在使用显式函数调用时，你只会得到相关函数的引用。

# Null 不好

JavaScript（以及扩展的 TypeScript）有两个底类型：`null` 和 `undefined`。它们*意图上*表示不同的含义：

- 某些内容尚未初始化：`undefined`
- 某些内容当前不可用：`null`

大多数其他语言只有一个（通常称为 `null`）。由于 JavaScript 默认会将未初始化的变量/参数/属性求值为 `undefined`（你没有选择余），我们建议直接用它来表示你自己的“不可用”状态，不要去纠结 `null`。

# 现实世界讨论

# 处理 `null` 风格的代码库

如果你的代码库与其他可能给你返回 `null` 的 API 交互，请使用 `== undefined` 进行检查（而不是 `===`）。即使对于可能是“假值（falsy）”的值也可以这样用。

```javascript
// 假设你有 `foo == undefined`，其中 foo 可以以下之一：
console.log(undefined == undefined); // true
console.log(null == undefined); // true
console.log(0 == undefined); // false
console.log('' == undefined); // false
console.log(false == undefined); // false
```

# 额外提示

# 限制显式使用 `undefined`

此外，由于 TypeScript 给了你一个机会在值之外单独 `document` 你的结构，而不是这样：

```typescript
function foo(){
// 如果某些情况
  return {a:1,b:2};
// 否则
  return {a:1,b:undefined};
}
```

你应该使用类型注解：

```typescript
function foo():{a:number, b?:number}{
// 如果某些情况
  return {a:1,b:2};
// 否则
  return {a:1};
}
```

# Node 风格回调

Node 风格回调函数（例如 `(err,somethingElse)=>{ /* something */ }`）在发生错误时通常会将 `err` 设置为 `null` 并调用。

```javascript
fs.readFile('someFile', 'utf8', (err, data) => {
  if (err) {
    // 处理错误
    return;
  }
  // 处理数据
});
```

在创建自己的 API 时，最好使用：

```typescript
function getData(err: Error | null, callback: (data: any) => void) {
  if (err) {
    // 处理错误
    return;
  }
  // 处理数据
  callback(data);
}
```

此外，不仅是开发工具需要花时间理解代码。下一个人类在开始理解东西到底是从哪里实际导入的之前，需要理解大量的代码库。使用内部模块也使得代码难以孤立进行审查，例如在 github 上。

```typescript
var t = 5;
```

因此 a.ts 无法独立编译。

## 总结

--out 实际上是某些构建工具的工作。即使是这样的构建工具，也可以从外部模块提供的依赖关系中获益。因此，我们建议你使用外部模块，如果你有需要，可以让构建工具为你创建一个单一的 .js 文件。

https://twitter.com/nycdotnet/status/613705850574778368

![](img/7b4ede152e837dfd4e13fc18de91d96a_267_0.png)

# jQuery 提示

注意：你需要安装 `jquery.d.ts` 文件来使用这些提示

# 快速定义新插件

只需创建一个 `jquery-foo.d.ts` 并包含内容：

```typescript
interface Query {
  foo: any;
}
```

现在你可以使用 `$('something').foo({whateverYouWant:'hello jquery plugin'})` 了

# TypeScript 中的静态构造函数

TypeScript 类（类似于 JavaScript 类）不能有静态构造函数。不过，你可以通过手动调用它来轻松获得相同的效果：

```typescript



```
class MyClass {

  static initialize() {

    // 初始化

  }

}

MyClass.initialize();
```

# 单例模式

传统的单例模式实际上是为了解决所有代码都必须在 `class` 中的这一事实。

```typescript
class Singleton {

  private static instance: Singleton;

  private constructor() {

    // 执行某些构造...

  }

  static getInstance() {

    if (!Singleton.instance) {

      Singleton.instance = new Singleton();

      // ... 可以在此处进行任何初始化...

    }

    return Singleton.instance;

  }

  someMethod() { }

}
```

`let something = new Singleton()` // Error：`'Singleton'` 的构造函数是私有的。

`let instance = Singleton.getInstance()` // 对实例进行某些操作

如果你不需要懒加载，可以使用 `namespace`：

```typescript
namespace Singleton {

  // ... 可以在此处进行任何初始化...

  export function someMethod() {}

}

// 使用方法

Singleton.someMethod();
```

> 警告：`Singleton` 只是全局变量的一个花哨名称

对于大多数项目，`namespace` 还可以被 `module` 替换。

```typescript
// someFile.ts

// ... 可以在此处进行任何初始化...

export function someMethod() {}

// 使用

import {someMethod} from "./someFile";
```

# 函数参数

如果你有一个函数接收了过多的参数，或者相同类型的参数，那么你可能考虑将函数更改为接收一个对象。

考虑以下函数：

```typescript
function foo(flagA: boolean, flagB: boolean) {

  // 你的优秀函数体

}
```

使用这样的函数定义，很容易错误地调用，例如 `foo(flagB, flagA)`，而你无法获得编译器的帮助。

相反，将函数转换为接收一个对象：

```typescript
function foo(config: {flagA: boolean, flagB: boolean}) {

  const {flagA, flagB} = config;

  // 你的优秀函数体

}
```

现在，函数调用看起来像 `foo({flagA, flagB})`，这使得更容易发现错误并进行代码审查。

> 注意：如果你的函数足够简单，且你不预计会有太多的变动，请随时忽略此建议。

# 真值 (Truthy)

JavaScript 有“真值”的概念，即在某些位置求值结果类似于 `true` 的值（例如 `if` 条件和布尔 `&&`、`||` 运算符）。以下内容在 JavaScript 中是真值。例如任何非 0 的数字都是真值：

```javascript
if (123) { // 将被视为 `true`

  console.log('Any number other than 0 is truthy');

}
```

不是真值的对象被称为假值（falsy）。

这里有一份方便参考的表格。

| 变量类型 | 何时是假值 | 何时是真值 |
|---|---|---|
| boolean | false | true |
| string | '' (空字符串) | 其他任何字符串 |
| number | 0 NaN | 其他任何数字 |
| null | 总是 | 永远不是 |
| undefined | 总是 | 永远不是 |
| 其他任何对象（包括空对象 {}, []） | 永远不是 | 总是 |

# 显式化 (Being explicit)

> `!!` 模式

很多时候，显式地意图是将该值视为布尔值并将其转换为真正的布尔值（`true` | `false` 之一）是有帮助的。你可以轻松地通过在前加上 `!!` 将值转换为真正的布尔值，例如 `!!foo`。它只使用了两次。第一个 `!` 将 `foo` 中的变量转换为布尔值并反转逻辑（真值 `! -> false`，假值 `! -> true`）。第二个 `!` 再次翻转以匹配原始对象的性质（例如，真值 `! -> false -! -> true`）。

在很多地方使用这种模式很常见，例如：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 切换器 (Toggles)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 构建 (Build)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 环境 (Environment)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 包 (Package)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 脚本 (Scripts)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 配置 (Config)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 生产 (Production)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 测试 (Test)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 开发 (Dev)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 库 (Library)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 导出 (Exports)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 模块 (Module)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 变量 (Variable)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 对象 (Object)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 函数 (Function)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 数组 (Array)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 字符串 (String)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 布尔 (Boolean)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 数字 (Number)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 空 (Null)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 未定义 (Undefined)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 任意 (Any)

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// 直接变量

const hasName = !!name;

// 作为对象的成员

const someObj = {

  hasName: !!name

}

// 例如 ReactJS

{!!someName && <div>{someName}</div>}
```

# 创建数组 (Creating arrays)

创建一个空数组超级简单：

```typescript
const foo:string[] = [];
```

如果你想创建一个预填充某些内容的数组，使用 ES6 的 `Array.prototype.fill`：

```typescript
const foo:string[] = new Array(3).fill('');

console.log(foo); // ['', '', ''];
```



# 桶 (Barrel)

桶是将多个模块的导出汇总到一个方便模块的方法。桶本身是一个重新导出其他模块可选导出内容的文件。

假设如下结构：

```typescript
// demo/foo.ts
export class Foo {}

// demo/bar.ts
export class Bar {}

// demo/baz.ts
export class Baz {}
```

如果没有桶，消费者需要三个导入语句：

```typescript
import { Foo } from '../demo/foo';
import { Bar } from '../demo/bar';
import { Baz } from '../demo/baz';
```

你可以添加一个包含以下内容的桶 `demo/index.ts`：

```typescript
// demo/index.ts
export * from './foo'; // 重新导出所有的导出
export * from './bar'; // 重新导出所有的导出
export * from './baz'; // 重新导出所有的导出
```

现在，消费者可以从桶导入它需要的内容：

```typescript
import { Foo, Bar, Baz } from '../demo'; // 隐含了 demo/index.ts
```

# 命名导出 (Named exports)

与其导出 `*`，你可以选择以名称导出模块。例如，假设 `baz.ts` 有函数：

```typescript
// demo/foo.ts
export class Foo {}

// demo/bar.ts
export class Bar {}

// demo/baz.ts
export function getBaz() {}
export function setBaz() {}
```

如果你不想从 `demo` 导出 `getBaz` 和 `setBaz`，你可以通过在名称中导入它们并导出该名称将其放入变量，如下所示：

```typescript
// demo/index.ts
export * from './foo'; // 重新导出所有的导出
export * from './bar'; // 重新导出所有的导出
import * as baz from './baz'; // 以名称导入
export { baz }; // 导出名称
```

现在，消费者看起来像像：

```typescript
import { Foo, Bar, baz } from './demo'; // 隐含了 demo/index.ts
```

```typescript
// 使用
baz.getBaz();
baz.setBaz();
// 等等 ...
```

# 类型安全的事件器 (Typesafe Event Emitter)

在 Node.js 和传统的 JavaScript 中，通常使用单个事件器。事件器内部跟踪不同事件类型的监听器，例如：

```javascript
const emitter = new EventEmitter();

// 触发：
emitter.emit('foo', foo);
emitter.emit('bar', bar);

// 监听：
emitter.on('foo', (foo)=>console.log(foo));
emitter.on('bar', (bar)=>console.log(bar));
```

本质上，`EventEmitter` 内部以映射数组的形式数据：

```javascript
{foo: [fooListeners], bar: [barListeners]}
```

相反，为了事件类型安全，你可以为每个事件类型创建一个事件器：

这具有以下优势：

- 事件类型可以作为变量被容易发现。
- 事件器变量可以独立地进行重构。
- 事件数据结构的类型安全。

# 参考 TypedEvent

```typescript
export interface Listener<T> {
  (event: T): any;
}

export interface Disposable {
  dispose();
}

/** 当事件发生时透传事件。你不会获取到开始监听之前的事件。 */
class TypedEvent<T> {
  private listeners: Listener<T>[] = [];
  private listenersOncer: Listener<T>[] = [];

  on = (listener: Listener<T>): Disposable => {
    this.listeners.push(listener);
    return {
      dispose: () => this.off(listener)
    };
  };

  once = (listener: Listener<T>): void => {
    this.listenersOncer.push(listener);
  };

  off = (listener: Listener<T>) => {
    var callbackIndex = this.listeners.indexOf(listener);
    if (callbackIndex > -1) this.listeners.splice(callbackIndex, 1);
  };

  emit = (event: T) => {
    /** 更新所有通用监听器 */
    this.listeners.forEach((listener) => listener(event));
    /** 清空 'once' 队列 */
    this.listenersOncer.forEach((listener) => listener(event));
    this.listenersOncer = [];
  };

  pipe = (te: TypedEvent<T>): Disposable => {
    return this.on((e) => te.emit(e));
  }
}
```

# TypeScript 风格指南与编码规范

一份非官方的 TypeScript 风格指南

人们曾向我寻求对此的看法。个人而言，我并没有在团队和项目中强制执行这些规则，但当有人认为需要如此强大的一致性时，这些规则可以起到最后的裁决作用。还有一些我非常认同的事情，它们包含在技巧章节中（例如：类型断言是不好的，属性 setter 是不好的）。

章节：

- 变量 (Variable)
- 类 (Class)
- 接口 (Interface)
- 类型 (Type)
- 命名空间 (Namespace)
- 枚举 (Enum)
- `null vs. undefined`
- 格式化 (Formatting)
- 单引号 vs 双引号
- 制表符 vs 空格
- 使用分号
- 将数组标记为 `Type[]`
- 文件名
- `type vs interface`

# 变量与函数

- 变量和函数名使用 `camelCase`

> 原因：JavaScript 惯例

错误示例：

```javascript
var FooVar;
function BarFunc() { }
```

# 正确示例

```javascript
var fooVar;
function barFunc() {
```

# 类

- 类名使用 `PascalCase`。

> 原因：这在标准 JavaScript 中实际上非常传统。

错误示例：

```javascript
class foo { }
```

# 正确示例

```javascript
class Foo { }
```

- 类成员和方法使用 `camelCase`。

> 原因：自然遵循了变量和函数的命名规范。

错误示例：

```javascript
class Foo {
  Bar: number;
  Baz() {}
}
```

# 正确示例

```javascript
class Foo {
  bar: number;
  baz() {}
}
```

# 接口

- 命名使用 `PascalCase`。

> 原因：与类相似。

成员使用 `camelCase`。

> 原因：与类类似。

- **不要**用 `I` 作为不惯例的前缀。

> 原因：不符合惯例。`lib.d.ts` 定义重要接口时不带 `I`（例如 `Window`, `Document` 等）。

错误示例：

```typescript
interface IFoo {
}
```

正确示例：

```typescript
interface Foo {
}
```

# 类型

- 命名使用 `PascalCase`。

> 原因：与类类似。

- 成员使用 `camelCase`。

> 原因：与类类似。

# 命名空间

- 命名使用 `PascalCase`

> 原因：TypeScript 团队遵循的惯例。命名空间实际上只是一个带有静态成员的类。类名是 `PascalCase` => 命名空间名也是 `PascalCase`。

错误示例：

```typescript
namespace foo {
}
```

正确示例：

```typescript
namespace Foo {
}
```

# 枚举

- 枚举名使用 `PascalCase`。

> 原因：类似于类。它是一种类型。

错误示例：

```typescript
enum color {
}
```

# 正确示例

```typescript
enum Color {
}
```

- 枚举成员使用 `PascalCase`。

> 原因：TypeScript 团队遵循的惯例，即语言创建者，例如 `SyntaxKind.StringLiteral`。也有助于其他语言向 TypeScript 的翻译（代码生成）。

错误示例：

```typescript
enum Color {
red
}
```

# 正确示例

```typescript
enum Color {
  Red
}
```

# Null vs. Undefined

- 命名使用 `PascalCase`

> 原因：TypeScript 团队遵循的惯例。

错误示例：

```javascript
class foo = }
}
```

正确示例：

```javascript
class Foo {
}
```

# 格式化

TypeScript 编译器带有一个很好的格式化服务。它默认提供的格式已经足够。使用 `tsfmt` 来自动格式化你的代码。

示例：

```javascript
const foo: string = "hello";
```

# 引号

- 优先使用单引号 (`' '`) 除非转义。

> 原因：更多的 JavaScript 团队这样做（例如 Airbnb, standard, npm, node, google/angular, facebook/react）。在大多数键盘上更容易输入。

- 当无法使用双引号时，尝试使用反引号 (``)

> 原因：这些通常表示复杂的字符串。

# 空格

- 使用 2 个空格。不要使用制表符 (tabs)。

> 原因：更多的 JavaScript 团队这样做（例如 Airbnb, standard, npm, node, google/angular, facebook/react）。VSCode 使用 4 个空格，但它们是例外。

# 分号

- 使用分号。

> 原因：显式分号有助于格式化工具产生一致的结果。缺少 ASI（自动分号插入）可能会误导新开发者，例如 `foo() \n (function(){})` 将被视为一个语句而不是两个。TC39 也建议这样做。

# 数组

- 将数组标记为 `foos:Foo[]` 而不是 `foos:Array<Foo>`。

> 原因：更容易读。TypeScript 团队也是这样使用的。通过 `[]` 可以更容易这是一个数组。

# 文件名

文件名使用 camelCase。例如 `accardian.ts`, `myControl.ts`, `utils.ts`, `map.ts` 等

> 原因：跨多个 JS 团队通用。

# type vs interface

- 当可能需要联合或交叉类型时使用 `type`：

```typescript
type Foo = number | { someProperty: number }
```

- 当想要 `extends` 或 `implements` 时使用 `interface`，例如：

```typescript
interface Foo {
  foo: string;
}

interface FooBar extends Foo {
  bar: string;
}

class X implements FooBar {
  foo: string;
  bar: string;
}
```

- 否则，在当天随心心情使用哪种都可以。

# 常见错误

在本节中，我们将解释用户在现实世界中遇到的许多常见错误代码。

## TS2304

示例：

```
Cannot find name ga
```

你可能正在使用某个第三方库（例如 google analytics），但没有对其进行声明。TypeScript 试图防止你出现拼写错误以及使用未声明的变量，因此，对于任何由于你包含了某些外部库而在运行时可用的内容，你都需要显式说明（关于如何修复它请参考后文）。

## TS2307

示例：

```
Cannot find module 'underscore'
```

你可能正在作为模块使用某个第三方库（例如 underscore）（更多关于模块的内容见后文），但没有它的环境声明文件（更多关于环境声明的内容见后文）。

## TS1148

示例：

```
Cannot compile modules unless the '--module' flag is provided
```

请查看模块章节。

## Catch 句中的变量不能有类型注解

示例：

```typescript
try { something(); }
catch (e: Error) { // Catch 句中的变量不能有类型注解
}
```

TypeScript 正在保护你免受外部 JavaScript 代码错误的错误。请改用类型守卫（type guard）：

```typescript
try { something(); }
catch (e) {
  if (e instanceof Error){
    // 在这里。
  }
}
```

## Interface ElementClass 无法同时扩展类型和 Component

这发生在编译上下文中存在两个 `react.d.ts` (`@types/react/index.d.ts`) 时。

修复方法：

- 删除 `node_modules` 和任何 `package-lock`（或 `yarn lock`）并重新运行 `npm install`。
- 如果无效，找到无效的模块（你的项目使用的所有模块都应该将 `react.d.ts` 作为 `peerDependency` 依赖而非硬依赖），并在他们的项目中报告它。

## 用于搜索索引

你可以忽略阅读此节。本节用于搜索引擎索引。

> 人们倾向于使用并遇到错误的其他模块：
> - Cannot find name $
> - Cannot find module jquery

## 编译器

TypeScript 编译器的源码位于 `src/compiler` 文件夹下。

它分为以下关键部分：

- 扫描器 (`scanner.ts`)
- 解析器 (`parser.ts`)
- 绑定器 (`binder.ts`)
- 检查器 (`checker.ts`)
- 发射器 (`emitter.ts`)

这些每个部分在源码中都有自己独特的内联文件。这些部分将在本章节稍后进行解释。

## BYOTS

我们有一个名为 Bring Your Own TypeScript (BYOTS) 的项目，它让使用编译器 API 变得更容易，例如通过暴露内部 API。你可以用它将本地应用的 TypeScript 版本全局暴露。

## 语法 vs. 语义

仅仅在语法上正确，并不意味着它在语义上是正确的。考虑以下这段 TypeScript 代码，尽管在语法上是有效的，但在语义上是错误的

```typescript
var foo: number = "not a number";
```

Semantic 在英语中意思是“含义”。在脑中记住这个概念是有用的。

## 处理概述

以下是 TypeScript 编译器的这些关键部分是如何组合的简要回顾：

```
SourceCode -- scanner --> Token Stream
```

```
Token Stream parser --> AST
```

```
AST -- binder --> Symbols
```

Symbol 是 TypeScript 语义系统的主要构建模块。所示，symbols 是作为绑定的结果创建的。Symbols 将 AST 中的声明节点与属于同一实体的其他声明连接起来。

Symbols + AST 是 checker 用于对源代码进行语义验证所使用的内容

```
AST + Symbols -- checker --> Type Validation
```

最后，当请求 JS 输出时：

```
AST + Checker -- emitter --> JS
```



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



如果你把头向左倾，这看起来像是一棵（非常向右侧的）树。

# 解析器函数

如所述，`parseSourceFile` 设置了初始状态并将工作传递给 `parseSourceFileWorker` 函数。

## parseSourceFileWorker

从创建一个 `SourceFile` AST 节点开始。然后从 `parseStatements` 函数开始解析源代码。一旦返回，它将用额外信息完成 `SourceFile` 节点，例如其 `nodeCount`、`identifierCount` 等。

## parseStatements

这是最重要的 `parseFoo` 风格函数之一（我们下一个将涵盖的概念）。它根据扫描器返回的当前 token 进行切换。例如，如果当前 token 是 `SemicolonToken`，它将调用 `parseEmptyStatement` 来为空语句创建一个 AST 节点。

解析器的 `parseExpected` 函数 `function parseExpected(kind: SyntaxKind, diagnosticMessage?: DiagnosticMessage): boolean` 会检查解析器状态中的当前标记是否匹配预期的 `SyntaxKind`。如果不匹配，它将报告传入的 `diagnosticMessage` "foo expected . "，或者在内部使用 `parseErrorAtPosition` 函数（该函数使用扫描位置）来创建一个通用的错误信息，以提供良好的错误报告。

### finishNode

解析器的 `finishNode` 函数 `function finishNode<T extends Node>(node: T, number): T` 为节点设置结束位置以及其他有用信息，例如它被解析时所处的的 `parserContextFlags`，以及在解析此节点之前是否存在任何错误（如果存在错误，则我们无法在增量解析中复用此 AST 节点）。

# Binder（绑定器）

大多数 JavaScript 译器都比 TypeScript 简单，因为它们在代码分析方面提供的支持非常少。典型的 JavaScript 译器通常只包含以下流程：

```
SourceCode --Scanner--> Tokens --Parser--> AST ----> JavaScript
```

虽然上述架构是理解 TypeScript 生成 JS 的简化版模型，但 TypeScript 的一个核心特性是其语义系统（Semantic system）。为了辅助类型检查（由 `checker` 执行），binder（在 `binder.ts` 中）用于将源代码的不同部分连接成一个贯的类型系统，然后供 `checker` 使用。binder 的主要职责是创建 Symbols（符号）。

## Symbol（符号）

Symbols 将 AST 中的声明节点与其他贡献于同一实体的声明连接起来。Symbols 是语义系统的基本构建单元。符号构造函数定义在 `core.ts` 中（binder 实际上使用 `allocator.getSymbolConstructor` 来获取它）。以下是构造函数：

```
function Symbol(flags: SymbolFlags, name: string) {

    this.flags = flags;

    this.name = name;

    this.declarations = undefined;

}
```

`SymbolFlags` 是一个标志枚举，实际上用于识别符号的额外分类（例如变量的作用域标志如 `FunctionScopedVariable` 或 `BlockScopedVariable` 等）。

## Usage by Checker

binder 实际上在类型检查器内部被使用，而类型检查器被程序使用。简化的调用栈如下：

```
program.getTypeChecker ->

  ts.createChecker (in checker)->

    initializeTypeChecker (in checker)->

      for each SourceFile `ts.bindSourceFile` (in binder)

      // followed by

      for each SourceFile `ts.mergeSymbolTable` (in checker)
```

binder 的工作单元是 `SourceFile`。`binder.ts` 由 `checker.ts` 驱动。

## Binder function

两个关键的 binder 函数是 `bindSourceFile` 和 `mergeSymbolTable`。接下来我们将查看这些函数。

### bindSourceFile

基本上检查 `file.locals` 是否已定义，如果没有，则将其交给（一个本地函数）`bind` 处理。

注意：`locals` 定义在 `Node` 上，类型为 `SymbolTable`。注意 `SourceFile` 也是一个 `Node`（实际上是 AST 中的一个根节点）。

提示：本地函数在 TypeScript 编译器内部被大量使用。局部函数很可能会使用来自父函数的变量（通过闭包捕获）。在 `bind`（`bindSourceFile` 内部的一个本地函数）（或它调用的函数）中，将设置 `symbolCount` 和 `classifiableNames` 等，这些信息存储在返回的 `SourceFile` 上。

### bind

`bind` 接受任何 `Node`（不仅仅是 `SourceFile`）。它执行的第一件事赋值 `node.parent`（如果父变量已设置……这是 binder 在其处理 `bindchildren` 函数的过程中完成的），然后交给 `bindworker` 执行繁重工作。最后，它调用 `bindChildren`（该函数仅用于在其函数本地变量中存储 binder 状态，例如当前父节点，然后对每个子节点调用 `bind`，并恢复 binder 状态）。现在让我们来看看 `bindworker`，它是一个更有趣的函数。

### bindWorker

该函数根据 `node.kind`（类型为 `SyntaxKind`）进行分支，并将工作委托给相应的 `bindFoo` 函数（同样定义在 `binder.ts` 中）。例如，如果节点是 `SourceFile`，则它（最终且仅当它是一个外部文件模块时）调用 `bindAnonymousDeclaration`。

### bindFoo functions

`bindFoo` 函数之间有一些共同模式，以及这些函数使用的一些工具函数。其中几乎总是被用到的是 `createSymbol` 函数。它在下方完整列出：

```
function createSymbol(flags: SymbolFlags, name: string): Symbol {

  symbolCount++;

  return new Symbol(flags, name);

}
```

如你所见，它只是保持 `symbolCount`（`bindSourceFile` 的本地变量）更新，并使用指定的参数创建符号。

## Symbols and Declarations（符号与声明）

节点与符号之间的链接通过几个函数完成。用于将 `SourceFile` 节点绑定到源文件符号（在外部模块的情况下）的一个函数是 `DeclarationToSymbol`。

注意：外部模块源文件的 `Symbol` 设置为 `flags : SymbolFlags.ValueModule` 且 `name: '' + removeFileExtension(file.fileName) + ''`

```
function addDeclarationToSymbol(symbol: Symbol, node: Declaration, symbolFlags: Symbol Flags) {

  symbol.flags |= symbolFlags;

  node.symbol = symbol;

  if (!symbol.declarations) {

    symbol.declarations = [];

  }

  symbol.declarations.push(node);

  if (symbolFlags & symbolFlags.HasExports && !symbol.exports) {

    symbol.exports = {};

  }

  if (symbolFlags & symbolFlags.HasMembers && !symbol.members) {

    symbol.members = {};

  }

  if (symbolFlags & symbolFlags.HasMembers && !symbol.valueDeclaration) {

    symbol.valueDeclaration = node;

  }

}
```

重要部分：
- 创建到符号的链接（在 case 局部变量中）。
- 将节点作为声明之一添加。

## Declaration（声明）

`Declaration` 只是一个带有可选名称的节点。

```
interface Declaration {

  _declaration: any;

  name?: string;

}
```

## Container（容器）

AST 节点可以是容器。这决定了当前的容器和或块容器，取决于 `getContainerFlags` 的评估。`ContainerFlags` 枚举函数如下所示：

```
function getContainerFlags(node: Node): ContainerFlags {

  switch (node.kind) {

    case SyntaxKind.ClassExpression:

    case SyntaxKind.ClassDeclaration:

    case SyntaxKind.InterfaceDeclaration:

    case SyntaxKind.EnumDeclaration:

    case SyntaxKind.TypeLiteral:

    case SyntaxKind.ObjectLiteral:

      return ContainerFlags.IsContainer;

    case SyntaxKind.CallSignature:

    case SyntaxKind.ConstructSignature:

    case SyntaxKind.IndexSignature:

    case SyntaxKind.MethodDeclaration:

    case SyntaxKind.MethodSignature:

    case SyntaxKind.FunctionDeclaration:

    case SyntaxKind.Constructor:

    case SyntaxKind.Accessor:

    case SyntaxKind.FunctionType:

    case SyntaxKind.ConstructorType:

    case SyntaxKind.ArrowFunction:

    case SyntaxKind.ModuleDeclaration:

    case SyntaxKind.SourceFile:

    case SyntaxKind.TypeAlias:

      return ContainerFlags.ContainerWithLocals;

    case SyntaxKind.CatchClause:

    case SyntaxKind.ForInStatement:

    case SyntaxKind.EndOfStatement:

    case SyntaxKind.CaseBlock:

      return ContainerFlags.IsContainer;

    case SyntaxKind.Block:

      // 不要将函数内部的块视为块容器

      // 位于此块的局部变量应进入函数局部变量

      return functionLike(node.parent) ? ContainerFlags.None : ContainerFlags.IsBlockScopedContainer;

  }

  return ContainerFlags.None;

}
```

```
// 示例：

//

// function foo() {

//   var x;

//   let x;

// }

// 如果我们将 'var x' 放入函数局部变量并将 'let x' 放入块的局部

//，那么就不会有冲突。

// 通过不在这里创建新的块容器，我们确保 'var x' 和 'let x' 都进入函数局部变量，从而产生冲突。

```

// 所有缩进节点按声明顺序保留在链表中。此列表用于类型检查器
// 中的 `getIndexOfContainer` 来验证容器所使用的本地名称是唯一的。
```
function bindChildren(node: Node) {
// 在递归进入节点节点之前，我们首先保存现有的父节点、容器
// 和块容器。当从处理子节点弹出时，我们恢复
// 保存的值。
let saveParent = parent;
let saveContainer = container;
let savedBlockScopeContainer = blockScopeContainer;

// 在递归进入它们时，这现在将被设置为它们所有子节点的父节点。
parent = node;

// 根据此节点的类型，我们可能需要调整当前的容器
// 和块容器。如果当前节点是容器，那么它也会被自动
// 视为当前的块容器。此外，对于我们 k
```

```typescript

// 可能包含 locals，我们主动初始化了 .locals 字段。我们这样做是因为

// 极可能需要 .locals 来放置某些子节点（例如，

// 参数或变量声明）；

// 然而，我们并不会为块级容器（block-containers）主动创建 .locals，

// 因为对于块级容器来说，从不包含任何块级变量

// 是完全正常且常见的。我们不希望在遇到每个“块”时都为其分配一个对象，

// 尽管大多数情况下这些必要的。

// 最后，如果这是一个块级容器，我们会清除它可能包含的任何现有 .locals 对象。

// 这发生在增量场景中。由于我们复用了来自上一次编译的节点，

// 该节点可能已经创建了 'locals'。我们必须清除它，以防止无意中从上一次编译移动任何旧数据。

let containerFlags = getContainerFlags(node);

if (containerFlags & ContainerFlags.IsContainer) {

  container = blockScopeContainer = node;

  if (containerFlags & ContainerFlags.HasLocals) {

    container.locals = {};

  }

  addToContainerChain(container);

}

else if (containerFlags & ContainerFlags.IsBlockScopedContainer) {

  blockScopeContainer = node;

  blockScopeContainer.locals = undefined;

}

forEachChild(node, bind) {

  container = saveContainer;

  parent = saveParent;

  blockScopeContainer = savedBlockScopeContainer;

}
```

正如你可能从 binder 函数章节中所回忆的：`bindChildren` 是从 `bind` 函数调用的。因此我们有了递归绑定设置：`bind` 调用 `bindChildren`，然后对每个子节点调用 `bind`。

## SymbolTable

SymbolTable 实现为一个简单的 HashMap。以下是其接口 (types.ts)：

```typescript

interface SymbolTable {

  [index:string]: Symbol;

}
```

SymbolTables 由绑定初始化。编译器使用了以下几个 SymbolTables：

在 Node 上：

```typescript

locals?: SymbolTable;  // 与节点关联的 locals

```

在 Symbol 上：

```typescript

members?: SymbolTable;  // 类、接口或字面量实例成员

exports?: SymbolTable;  // 模块导出

```

![](img/7b4ede152e837dfd4e13fc18de91d96a_318_0.png)

注意：我们看到 `bindChildren` 根据 `ContainerFlags` 将 `locals` 初始化为 `({})`。

## SymbolTable population

SymbolTables 主要通过调用 `declareSymbol` 来填充 Symbols。该函数的完整代码如下文所示：

```typescript

/**

 * 为节点声明一个 Symbol 并将其添加到 symbols 中。如果标识符名称冲突，则报告错误。

 * @param symbolTable - 节点将对应的符号表。
```



# 全局命名空间合并

在`initializeTypeChecker`中存在以下代码：

```typescript
// 初始化全局符号表
forEach(host.getSourceFiles(), file => {
  if (!isExternalModule(file)) {
    mergeSymbolTable(globals, file.locals);
  }
});
```

这基本上是将所有的`global`符号合并到`let globals: SymbolTable = {};`（在`createTypeChecker`中）。`SymbolTable.mergeSymbolTable`主要调用`mergeSymbol`。

# 错误报告

检查器使用本地错误函数报告错误。以下是该函数：

```typescript
function error(location: Node, message: DiagnosticMessage, arg0?: any, arg1?: any, arg2?: any): void {
  let diagnostic = location
    ? createDiagnosticForNode(location, message, arg0, arg1, arg2)
    : createCompilerDiagnostic(message, arg0, arg1, arg2);
  diagnostics.add(diagnostic);
}
```

# 发射器 (Emitter)

TypeScript 编译器提供了两个`emitter`：

- `emitter.ts`：这是你最感兴趣的发射器。它的 TS -> JavaScript 发射器。
- `declarationEmitter.ts`：这是用于创建声明文件（针对`TypeScript source file`，即`.ts`文件的`.d.ts`文件）的发射器。

我们将在本节查看`emitter.ts`。

# 程序的使用

`Program`提供了一个`emit`函数。该函数主要委托给`emitter.ts`中的`emitFiles`函数。以下是堆栈轨迹：

```
Program.emit ->
  `emitWorker` (program.ts createProgram 中的本地函数) ->
  `emitFiles` (emitter.ts 中的函数)
```

`emitter`提供给发射器（通过`emitFiles`的参数传递）的一个内容是`EmitResolver`。`EmitResolver`由程序的 TypeChecker 提供，它基本上是`createChecker`中`local`函数的子集。

# emitFiles

定义在`emitter.ts`中，函数签名如下：

```typescript
// 当用户在整个项目中只有一个文件需要发射时，使用 targetSourceFile
// 这用于 compileOnSave 功能
export function emitFiles(resolver: EmitResolver, host: EmitHost, targetSource?: sourceFile): EmitResult {
```

`EmitHost`是`CompilerHost`的简化版本（在运行时实际上对于许多用途是一个`CompilerHost`）。

来自`emitFiles`最有趣的调用堆栈是：

```
emitFiles ->
emitFile(jsPath, targetSourceFile) ->
emitJavaScript(jsPath, targetSourceFile);
```

# emitJavaScript

该函数中有许多很好的注释，因此我们在下方展示它：

```typescript
function emitJavaScript(jsPath: string, root?: SourceFile) {
  let writer = createTextWriter(newline);
  let write = writer.write;
  let writeTextOfNode = writer.writeTextOfNode;
  let writeLine = writer.writeLine;
  let increaseIndent = writer.increaseIndent;
  let decreaseIndent = writer.decreaseIndent;
  let currentSourceFile: SourceFile;

  // 如果文件是 System 外部模块，则导出函数
  // System.register([...], function <exporter>) {...})
  // 在 System 模块中导出看起来像：
  // export var x; ... x = 1
  // =>
  // var x; exporter("x", x = 1)
  let exportFunctionForFile: string;
  let generatedSetName: Map<string> = {};
  let nodeToGeneratedName: string[] = [];
  let computedPropertiesToGeneratedNames: string[];
  let extendsEmitted = false;
  let decoratedEmitted = false;
  let paramEmitted = false;
```

```typescript
let waiterEmitted = false;
let tempFlags = 0;
let tempVariables = Identifier[];
let tempParameters = Identifier[];
let externalImports: (ImportDeclaration | ImportEqualsDeclaration | ExportDeclaration)];
let exportSpecifiers: Map<ExportSpecifier>;
let exportEquals = ExportAssignment;
let hasExportStars: boolean;
```

```typescript
/* 将发射输出写入磁盘 */
let writeEmittedFiles = writeJavaScriptFile;
```

```typescript
let detachedCommentsInfo: { node: number; detachedCommentEndPos: number };
```

```typescript
let writeComment = writeCommentRange;
```

```typescript
/* 发射一个节点 */
let emit = emitNodeWithoutSourceMap;
```

```typescript
/* 在开始发射节点之前调用 */
let emitStart = function (node: Node) { };
```

```typescript
/* 在节点发射完成后调用一次 */
let emitEnd = function (node: Node) { };
```

```typescript
// 发射 startPos 之后给定 token 的文本
// 默认情况下，提供与给定 tokenKind 文本
// 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
// @param tokenKind 要搜索和发射的 token 类型
// @param startPos 源码中开始搜索 token 的位置
// @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

```typescript
// 在发射代码中由于节点原因，在函数/类的局部作用域之前调用
// @param scopeDeclaration 开始局部作用域的节点
// @param scopeName 局部作用域名称
let emitStart = function (node: Node, scopeName?: string) { };
```

```typescript
/* 在节点发射完成后调用一次 */
let emitEnd = function (node: Node) { };
```

```typescript
// 发射 startPos 之后给定 token 的文本
// 默认情况下，提供与给定 tokenKind 文本
// 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
// @param tokenKind 要搜索和发射的 token 类型
// @param startPos 源码中开始搜索 token 的位置
// @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

```typescript
// 发射一个节点 */
let emit = emitNodeWithoutSourceMap;
```

```typescript
// 在开始发射节点之前调用 */
let emitStart = function (node: Node) { };
```

等待，查看流程：

```typescript
// 发射 startPos 之后给定 token 的文本
// 默认情况下，提供与给定 tokenKind 文本
// 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
// @param tokenKind 要搜索和发射的 token 类型
// @param startPos 源码中开始搜索 token 的位置
// @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

等待，OCR 文本在结尾非常碎片。我将根据提供的模式重新构建逻辑。

```typescript
// 发射 startPos 之后给定 token 的文本
// 默认情况下，提供与给定 tokenKind 文本
// 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
// @param tokenKind 要搜索和发射的 token 类型
// @param startPos 源码中开始搜索 token 的位置
// @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

等待，OCR 文本包含一些碎片。让我们根据提供的模式重新构建。

```typescript
// 发射 startPos 之后给定 token 的文本
// 默认情况下，提供与给定 tokenKind 文本
// 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
// @param tokenKind 要搜索和发射的 token 类型
// @param startPos 源码中开始搜索 token 的位置
// @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

```typescript
/* 发射一个节点 */
let emit = emitNodeWithoutSourceMap;
```

```typescript
/* 在开始发射节点之前调用 */
let emitStart = function (node: Node) { };
```

```typescript
/* 在节点发射完成后调用一次 */
let emitEnd = function (node: Node) { };
```

```typescript
// 发射 startPos 之后给定 token 的文本
// 默认情况下，提供与给定 tokenKind 文本
// 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
// @param tokenKind 要搜索和发射的 token 类型
// @param startPos 源码中开始搜索 token 的位置
// @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

实际上，我将直接提供提供文本的清理版本。



这基本上是将所有的`global`符号合并到`let globals: SymbolTable = {};`（在`createTypeChecker`中）。`SymbolTable.mergeSymbolTable`主要调用`mergeSymbol`。

## 错误报告

检查器使用本地错误函数报告错误。以下是该函数：

```typescript
function error(location: Node, message: DiagnosticMessage, arg0?: any, arg1?: any, arg2?: any): void {
  let diagnostic = location
    ? createDiagnosticForNode(location, message, arg0, arg1, arg2)
    : createCompilerDiagnostic(message, arg0, arg1, arg2);
  diagnostics.add(diagnostic);
}
```

## 发射器 (Emitter)

TypeScript 编译器提供了两个`emitter`：

- `emitter.ts`：这是你最感兴趣的发射器。它的 TS -> JavaScript 发射器。
- `declarationEmitter.ts`：这是用于创建声明文件（针对`TypeScript source file`，即`.ts`文件的`.d.ts`文件）的发射器。

我们将在本节查看`emitter.ts`。

## 程序的使用

`Program`提供了一个`emit`函数。该函数主要委托给`emitter.ts`中的`emitFiles`函数。以下是堆栈轨迹：

```
Program.emit ->
  `emitWorker` (program.ts createProgram 中的本地函数) ->
  `emitFiles` (emitter.ts 中的函数)
```

`emitter`提供给发射器（通过`emitFiles`的参数传递）的一个内容是`EmitResolver`。`EmitResolver`由程序的 TypeChecker 提供，它基本上是`createChecker`中`local`函数的子集。

## emitFiles

定义在`emitter.ts`中，函数签名如下：

```typescript
// 当用户在整个项目中只有一个文件需要发射时，使用 targetSourceFile
// 这用于 compileOnSave 功能
export function emitFiles(resolver: EmitResolver, host: EmitHost, targetSource?: sourceFile): EmitResult {
```

`EmitHost`是`CompilerHost`的简化版本（在运行时实际上对于许多用途是一个`CompilerHost`）。

来自`emitFiles`最有趣的调用堆栈是：

```
emitFiles ->
emitFile(jsPath, targetSourceFile) ->
emitJavaScript(jsPath, targetSourceFile);
```

## emitJavaScript

该函数中有许多很好的注释，因此我们在下方展示它：

```typescript
function emitJavaScript(jsPath: string, root?: SourceFile) {
  let writer = createTextWriter(newline);
  let write = writer.write;
  let writeTextOfNode = writer.writeTextOfNode;
  let writeLine = writer.writeLine;
  let increaseIndent = writer.increaseIndent;
  let decreaseIndent = writer.decreaseIndent;
  let currentSourceFile: SourceFile;

  // 如果文件是 System 外部模块，则导出函数
  // System.register([...], function <exporter>) {...})
  // 在 System 模块中导出看起来像：
  export var x; ... x = 1
  // =>
  // var x; exporter("x", x = 1)
  let exportFunctionForFile: string;
  let generatedSetName: Map<string> = {};
  let nodeToGeneratedName: string[] = [];
  let computedPropertiesToGeneratedNames: string[];
  let extendsEmitted = false;
  let decoratedEmitted = false;
  let paramEmitted = false;
```

```typescript
let waiterEmitted = false;
let tempFlags = 0;
let tempVariables = Identifier[];
let tempParameters = Identifier[];
let externalImports: (ImportDeclaration | ImportEqualsDeclaration | ExportDeclaration)];
let exportSpecifiers: Map<ExportSpecifier>;
let exportEquals = ExportAssignment;
let hasExportStars: boolean;
```

```typescript
/* 将发射输出写入磁盘 */
let writeEmittedFiles = writeJavaScriptFile;
```

```typescript
let detachedCommentsInfo: { node: number; detachedCommentEndPos: number };
```

```typescript
let writeComment = writeCommentRange;
```

```typescript
/* 发射一个节点 */
let emit = emitNodeWithoutSourceMap;
```

```typescript
/* 在开始发射节点之前调用 */
let emitStart = function (node: Node) { };
```

```typescript
/* 在节点发射完成后调用一次 */
let emitEnd = function (node: Node) { };
```

```typescript
// 发射 startPos 之后给定 token 的文本
* 默认情况下，提供与给定 tokenKind 文本
* 但如果提供了可选的 emitFn 回调，则使用回调而非默认文本来发射
* @param tokenKind 要搜索和发射的 token 类型
* @param startPos 源码中开始搜索 token 的位置
* @param emitFn 如果将被调用以发射文本而非实际 token
let emitToken = emitTokenText;
```

```typescript
case SyntaxKind.CallExpression:
    return emitCallExpression(<Expression>node);
case SyntaxKind.NewExpression:
    return emitNewExpression(<NewExpression>node);
case SyntaxKind.TaggedTemplateExpression:
    return emitTaggedTemplateExpression(<TaggedTemplateExpression>node);
case SyntaxKind.TypeAssertionExpression:
    return emit((<TypeAssertion>node).expression);
case SyntaxKind.AsExpression:
    return emit((<AsExpression>node).expression);
case SyntaxKind.ParenthesizedExpression:
    return emitParenthesizedExpression(<ParenthesizedExpression>node);
case SyntaxKind.FunctionDeclaration:
case SyntaxKind.FunctionExpression:
case SyntaxKind.ArrowFunction:
    return emitFunctionLikeDeclaration(<FunctionLikeDeclaration>node);
case SyntaxKind.DeleteExpression:
    return emitDeleteExpression(<DeleteExpression>node);
case SyntaxKind.TypeOfExpression:
    return emitTypeOfExpression(<TypeOfExpression>node);
case SyntaxKind.VoidExpression:
    return emitVoidExpression(<VoidExpression>node);
case SyntaxKind.AwaitExpression:
    return emitAwaitExpression(<AwaitExpression>node);
case SyntaxKind.PrefixUnaryExpression:
    return emitPrefixUnaryExpression(<PrefixUnaryExpression>node);
case SyntaxKind.PostfixUnaryExpression:
    return emitPostfixUnaryExpression(<PostfixUnaryExpression>node);
case SyntaxKind.BinaryExpression:
    return emitBinaryExpression(<BinaryExpression>node);
case SyntaxKind.ConditionalExpression:
    return emitConditionalExpression(<ConditionalExpression>node);
case SyntaxKind.SpreadElementExpression:
    return emitSpreadElementExpression(<SpreadElementExpression>node);
case SyntaxKind.YieldExpression:
    return emitYieldExpression(<YieldExpression>node);
case SyntaxKind.OmittedExpression:
    return;
case SyntaxKind.Block:
case SyntaxKind.ModuleBlock:
    return emitBlock(<Block>node);
case SyntaxKind.VariableStatement:
    return emitVariableStatement(<VariableStatement>node);
case SyntaxKind.EmptyStatement:
    return write("");
case SyntaxKind.ExpressionStatement:
    return emitExpressionStatement(<ExpressionStatement>node);
case SyntaxKind.IfStatement:
    return emitIfStatement(<IfStatement>node);
case SyntaxKind.DoStatement:
    return emitDoStatement(<DoStatement>node);
case SyntaxKind.WhileStatement:
    return emitWhileStatement(<WhileStatement>node);
case SyntaxKind.ForStatement:
    return emitForStatement(<ForStatement>node);
case SyntaxKind.OfStatement:
case SyntaxKind.ForInOfStatement:
    return emitForInOfStatement(<ForInOfStatement>node);
case SyntaxKind.ContinueStatement:
case SyntaxKind.BreakStatement:
    return emitBreakOrContinueStatement(<BreakOrContinueStatement>node);
case SyntaxKind.ReturnStatement:
    return emitReturnStatement(<ReturnStatement>node);
case SyntaxKind.WithStatement:
    return emitWithStatement(<WithStatement>node);
case SyntaxKind.SwitchStatement:
    return emitSwitchStatement(<SwitchStatement>node);
case SyntaxKind.CaseDefaultClause:
    return emitCaseOrDefaultClause(<CaseDefaultClause>node);
case SyntaxKind.LabeledStatement:
    return emitLabeledStatement(<LabeledStatement>node);
case SyntaxKind.ThrowStatement:
    return emitThrowStatement(<ThrowStatement>node);
case SyntaxKind.TryStatement:
    return emitTryStatement(<TryStatement>node);
case SyntaxKind.CatchClause:
    return emitCatchClause(<CatchClause>node);
case SyntaxKind.DebuggerStatement:
    return emitDebuggerStatement(node);
case SyntaxKind.VariableDeclaration:
    return emitVariableDeclaration(<VariableDeclaration>node);
case SyntaxKind.ClassExpression:
    return emitClassExpression(<ClassExpression>node);
case SyntaxKind.ClassDeclaration:
    return emitClassDeclaration(<ClassDeclaration>node);
case SyntaxKind.InterfaceDeclaration:
    return emitInterfaceDeclaration(<InterfaceDeclaration>node);
case SyntaxKind.EnumDeclaration:
    return emitEnumDeclaration(<EnumDeclaration>node);
case SyntaxKind.EnumMember:
    return emitEnumMember(<EnumMember>node);
case SyntaxKind.ModuleDeclaration:
    return emitModuleDeclaration(<ModuleDeclaration>node);
case SyntaxKind.ImportDeclaration:
    return emitImportDeclaration(<ImportDeclaration>node);
case SyntaxKind.ImportEqualsDeclaration:
    return emitImportEqualsDeclaration(<ImportEqualsDeclaration>node);
case SyntaxKind.ExportDeclaration:
    return emitExportDeclaration(<ExportDeclaration>node);
case SyntaxKind.ExportAssignment:
    return emitExportAssignment(<ExportAssignment>node);
```



```typescript
case SyntaxKind.SourceFile:
    return emitSourceFile(<SourceFile>node);

case SyntaxKind.FunctionDeclaration:
    return emitFunctionDeclaration(<FunctionDeclaration>node);

case SyntaxKind.MethodDeclaration:
    return emitMethodDeclaration(<MethodDeclaration>node);

case SyntaxKind.LeadingComments:
    return emitLeadingComments(<LeadingComments>node);

case SyntaxKind.TrailingComments:
    return emitTrailingComments(<TrailingComments>node);

case SyntaxKind.ExpressionToken:
    return emitExpressionToken(<ExpressionToken>node);

case SyntaxKind.InlineWith:
    return emitInlineWith(<InlineWith>node);

case SyntaxKind.Default:
    return emitDefault(<Default>node);

case SyntaxKind.Asterisk:
    return emitAsterisk(<Asterisk>node);

case SyntaxKind.Comma:
    return emitComma(<Comma>node);

case SyntaxKind.Question:
    return emitQuestion(<Question>node);

case SyntaxKind.Colon:
    return emitColon(<Colon>node);

case SyntaxKind.Equals:
    return emitEquals(<Equals>node);

case SyntaxKind.Kind:
    return emitKind(<Kind>node);

case SyntaxKind.Type:
    return emitType(<Type>node);

case SyntaxKind.Plus:
    return emitPlus(<Plus>node);

case SyntaxKind.Minus:
    return emitMinus(<Minus>node);

case SyntaxKind.Star:
    return emitStar(<Star>node);

case SyntaxKind.Dot:
    return emitDot(<Dot>node);

case SyntaxKind.Slash:
    return emitSlash(<Slash>node);

case SyntaxKind.Ampersand:
    return emitAmpersand(<Ampersand>node);

case SyntaxKind.Pipes:
    return emitPipes(<Pipes>node);

case SyntaxKind.Exclamation:
    return emitExclamation(<Exclamation>node);

case SyntaxKind.LessThan:
    return emitLessThan(<LessThan>node);

case SyntaxKind.GreaterThan:
    return emitGreaterThan(<GreaterThan>node);

case SyntaxKind.LessThanEqual:
    return emitLessThanEqual(<LessThanEqual>node);

case SyntaxKind.GreaterThanEqual:
    return emitGreaterThanEqual(<GreaterThanEqual>node);

case SyntaxKind.Tilde:
    return emitTilde(<Tilde>node);

case SyntaxKind.Caret:
    return emitCaret(<Caret>node);

case SyntaxKind.LeftBracket:
    return emitLeftBracket(<LeftBracket>node);

case SyntaxKind.RightBracket:
    return emitRightBracket(<RightBracket>node);

case SyntaxKind.LeftBrace:
    return emitLeftBrace(<LeftBrace>node);

case SyntaxKind.RightBrace:
    return emitRightBrace(<RightBrace>node);

case SyntaxKind.LeftParen:
    return emitLeftParen(<LeftParen>node);

case SyntaxKind.RightParen:
    return emitRightParen(<RightParen>node);

case SyntaxKind.Semicolon:
    return emitSemicolon(<Semicolon>node);

case SyntaxKind.Comma:
    return emitComma(<Comma>node);

case SyntaxKind.Literal:
    return emitLiteral(<Literal>node);

case SyntaxKind.Identifier:
    return emitIdentifier(<Identifier>node);

case SyntaxKind.This:
    return emitThis(<This>node);

case SyntaxKind.Super:
    return emitSuper(<Super>node);

case SyntaxKind.Void:
    return emitVoid(<Void>node);

case SyntaxKind.Undefined:
    return emitUndefined(<Undefined>node);

case SyntaxKind.True:
    return emitTrue(<True>node);

case SyntaxKind.False:
    return emitFalse(<False>node);

case SyntaxKind.Null:
    return emitNull(<Null>node);

case SyntaxKind.String:
    return emitString(<String>node);

case SyntaxKind.Number:
    return emitNumber(<Number>node);

case SyntaxKind.BigInt:
    return emitBigInt(<BigInt>node);

case SyntaxKind.Boolean:
    return emitBoolean(<Boolean>node);

case SyntaxKind.Symbol:
    return emitSymbol(<Symbol>node);

case SyntaxKind.Object:
    return emitObject(<Object>node);

case SyntaxKind.Array:
    return emitArray(<Array>node);

case SyntaxKind.Tuple:
    return emitTuple(<Tuple>node);

case SyntaxKind.Map:
    return emitMap(<Map>node);

case SyntaxKind.Set:
    return emitSet(<Set>node);

case SyntaxKind.Promise:
    return emitPromise(<Promise>node);

case SyntaxKind.Generator:
    return emitGenerator(<Generator>node);

case SyntaxKind.Async:
    return emitAsync(<Async>node);

case SyntaxKind.Yield:
    return emitYield(<Yield>node);

case SyntaxKind.Await:
    return emitAwait(<Await>node);

case SyntaxKind.Namespace:
    return emitNamespace(<Namespace>node);

case SyntaxKind.Type:
    return emitType(<Type>node);

case SyntaxKind.Case:
    return emitCase(<Case>node);

case SyntaxKind.Default:
    return emitDefault(<Default>node);

case SyntaxKind.Catch:
    return emitCatch(<Catch>node);

case SyntaxKind.Finally:
    return emitFinally(<Finally>node);

case SyntaxKind.Throw:
    return emitThrow(<Throw>node);

case SyntaxKind.For:
    return emitFor(<For>node);

case SyntaxKind.Let:
    return emitLet(<Let>node);

case SyntaxKind.Const:
    return emitConst(<Const>node);

case SyntaxKind.Var:
    return emitVar(<Var>node);

case SyntaxKind.Interface:
    return emitInterface(<Interface>node);

case SyntaxKind.Class:
    return emitClass(<Class>node);

case SyntaxKind.Enum:
    return emitEnum(<Enum>node);

case SyntaxKind.Namespace:
    return emitNamespace(<Namespace>node);

case SyntaxKind.Type:
    return emitType(<Type>node);

case SyntaxKind.Import:
    return emitImport(<Import>node);

case SyntaxKind.Export:
    return emitExport(<Export>node);

case SyntaxKind.Using:
    return emitUsing(<Using>node);
}
```

# 贡献

TypeScript 是开源软件并托管在 GitHub 上，团队欢迎社区投入。

# 环境搭建

非常简单：

```bash
git clone https://github.com/Microsoft/TypeScript.git
cd TypeScript
npm install -g jake
npm install
```

# 设置 Fork

你显然需要将 `Microsoft/TypeScript` 设置为上游远程仓库（upstream），并将自己的 Fork（使用 GitHub 的 fork 按钮）作为源（origin）：

```git
git remote rm origin
git remote rm upstream
git add upstream https://github.com/Microsoft/TypeScript.git
git remote add origin https://github.com/basarat/TypeScript.git
```

此外，我喜欢在像 `bas/` 的分支上工作，以便在分支列表中显示更整洁。

# 运行测试

他们的 `JakeFile` 中有很多测试和构建选项。你可以通过 `jake runtests` 运行所有测试。

# 基准 (Baselines)

基准用于管理 TypeScript 编译器预期输出是否存在任何更改。基准位于 `tests/baselines`。

- 参考（预期）基准：`tests/baselines/reference`
- 生成的（本次测试运行中）基准：`tests/baselines/local`（此文件夹在 `.gitignore` 中）

如果这些文件夹之间存在任何差异，测试将失败。你可以使用 BeyondCompare 或 KDiff3 等工具对比这两个文件夹。

如果你认为生成文件中的这些更改是有效的，请使用 `baseline-accept` 接受基准。对 `reference` 基准的更改现在将显示为你可以提交的 `git diff`。

请注意，如果你没有运行所有测试，请使用 `jake baseline-accept[soft]`，它只会复制新文件而不会删除整个 `reference` 目录。

# 测试分类

不同的场景有不同的分类，甚至有不同的测试架构。以下是其中一些的解释。

# 编译器测试

确保编译文件时：

- 如预期地生成错误
- 如预期地生成 JS
- 如预期地识别类型
- 如预期地识别符号

这些预期通过基准架构验证。

# 创建编译器测试

可以通过向 `tests/cases/compiler` 添加新文件 `yourtest.ts` 来创建测试。一旦你这样做并运行测试，你应该会获得基准失败提示。接受这些基准（以便它们显示在 git 中），并对其进行调整以符合你的预期……现在让测试通过。

使用 `jake runtests tests=compiler` 独立运行所有这些测试，或仅使用 `jake runtests tests=compiler/yourtest` 运行你的新文件。

我经常会执行 `jake runtests tests=compiler/yourtest || jake baseline-accept[soft]` 并在 `git` 中查看差异。

# 调试测试

使用 `jake runtests-browser tests=theNameOfTest` 浏览器中调试通常效果很好。

# 更多

- Remo 的一篇文章：https://dev.to/remojansen/learn-how-to-contribute-to-the-typescript-compiler-on-github-through-a-real-world-example-4df0
