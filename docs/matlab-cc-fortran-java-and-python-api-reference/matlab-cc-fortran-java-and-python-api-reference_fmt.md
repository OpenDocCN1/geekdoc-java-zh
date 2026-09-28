
# MATLAB C/C++, Fortran, Java 和 Python API 参考指南

![](img/6b00141eb48dd07643585de82d98355c_0_0.png)

# 修订历史

| 日期 | 类型 | 说明 |
| :--- | :--- | :--- |
| 1996年12月 | 第一次印刷 | MATLAB 5 (发布版本8) 新增内容 |
| 1997年5月 | 仅限在线 | 针对 MATLAB 5.1 (发布版本9) 修订 |
| 1998年1月 | 仅限在线 | 针对 MATLAB 5.2 (发布版本10) 修订 |
| 1999年1月 | 仅限在线 | 针对 MATLAB 5.3 (发布版本11) 修订 |
| 2000年9月 | 仅限在线 | 针对 MATLAB 6.0 (发布版本12) 修订 |
| 2001年6月 | 在线发布 | 针对 MATLAB 6.1 (发布版本12.1) 修订 |
| 2002年7月 | 仅限在线 | 针对 MATLAB 6.5 (发布版本13) 修订 |
| 2003年1月 | 仅限在线 | 针对 MATLAB 6.5 (发布版本13SP1) 修订 |
| 2004年6月 | 仅限在线 | 针对 MATLAB 7.0 (发布版本14) 修订 |
| 2004年10月 | 仅限在线 | 针对 MATLAB 7.0 (发布版本14SP1) 修订 |
| 2005年3月 | 仅限在线 | 针对 MATLAB 7.0 (发布版本14SP2) 修订 |
| 2006年3月 | 仅限在线 | 针对 MATLAB 7.1 (发布版本2006a) 修订 |
| 2006年9月 | 仅限在线 | 针对 MATLAB 7.2 (发布版本2006b) 修订 |
| 2007年3月 | 仅限在线 | 针对 MATLAB 7.4 (发布版本2007a) 修订并重命名 |
| 2007年9月 | | 针对 MATLAB 7.5 (发布版本2007b) 修订并重命名 |
| 2008年3月 | 仅限在线 | 针对 MATLAB 7.6 (发布版本2008a) 修订并重命名 |
| 2008年10月 | 仅限在线 | 针对 MATLAB 7.7 (发布版本2008b) 修订并重命名 |
| 2009年3月 | 仅限在线 | 针对 MATLAB 7.8 (发布版本2009a) 修订 |
| 2009年9月 | 仅限在线 | 针对 MATLAB 7.9 (发布版本2009b) 修订 |
| 2010年3月 | 仅限在线 | 针对 MATLAB 7.10 (发布版本2010a) 修订 |
| 2010年9月 | 仅限在线 | 针对 MATLAB 7.11 (发布版本2010b) 修订 |
| 2011年4月 | 仅限在线 | 针对 MATLAB 7.12 (发布版本2011a) 修订 |
| 2011年9月 | 仅限在线 | 针对 MATLAB 7.13 (发布版本2011b) 修订 |
| 2012年3月 | 仅限在线 | 针对 MATLAB 7.14 (发布版本2012a) 修订 |
| 2012年9月 | 仅限在线 | 针对 MATLAB 8.0 修订 |
| 2013年1月 | 仅限在线 | 针对 MATLAB 8.1 修订 |
| 2013年9月 | 仅限在线 | 针对 MATLAB 8.2 修订 |
| 2014年3月 | 仅限在线 | 针对 MATLAB 8.3 修订 |
| 2014年9月 | 仅限在线 | 针对 MATLAB 8.4 修订 |
| 2015年3月 | 仅限在线 | 针对 MATLAB 8.5 修订 |
| 2015年9月 | 仅限在线 | 针对 MATLAB 8.6 修订 |
| 2016年3月 | 仅限在线 | 针对 MATLAB 9.0 修订 |
| 2016年9月 | 仅限在线 | 针对 MATLAB 9.1 修订 |
| 2017年3月 | 仅限在线 | 针对 MATLAB 9.2 修订 |
| 2017年9月 | 仅限在线 | 针对 MATLAB 9.3 修订 |
| 2018年3月 | 仅限在线 | 针对 MATLAB 9.4 修订 |
| 2018年9月 | 仅限在线 | 针对 MATLAB 9.5 修订 |
| 2019年3月 | 仅限在线 | 针对 MATLAB 9.6 修订 |
| 2019年9月 | 仅限在线 | 针对 MATLAB 9.7 修订 |
| 2020年3月 | 仅限在线 | 针对 MATLAB 9.8 修订 |
| 2020年9月 | 仅限在线 | 针对 MATLAB 9.9 修订 |
| 2021年4月 | 仅限在线 | 针对 MATLAB R2022a 修订 |
| 2021年9月 | 仅限在线 | 针对 MATLAB R2022b 修订 |

## 异常

- `MathWorks.MATLAB.Exception` MATLAB 启动失败。
- `options.MATLABNotAvailableException`
- `System.ArgumentNull` Null字符串不是有效参数。

## C# 示例

使用一个启动选项启动新的 MATLAB 进程。完整的代码示例，请参见“使用 -nosplash 选项启动 MATLAB”。

```csharp
using (dynamic eng = MATLABEngine.StartMATLAB("-nosplash"))
{
  eng.disp(RunOptions(nargout: 0), "MATLAB started.");
}
```

## VB.NET 示例

使用默认选项启动新的 MATLAB 进程。

```vb
Option Strict Off
Using matlab = MATLABEngine.StartMATLAB()
matlab.disp(NewOptions(nargout=0), "Hello, world.")
End Using
```

# StartMATLABAsync

```csharp
static Task<MATLABEngine> StartMATLABAsync(string option);
static Task<MATLABEngine> StartMATLABAsync(string option1, ..., string optionN);
static Task<MATLABEngine> StartMATLABAsync(string[] options, System.Threading.CancellationToken token);
```

## 描述

在单独进程中异步启动 MATLAB，带有可选的 MATLAB 启动选项并连接到它。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `string[] options` | 用于启动 MATLAB 引擎的启动选项。您可以指定多个启动选项。引擎支持所有 MATLAB 启动选项，但第 1-2 页“不支持的启动”中列出的选项除外。有关选项列表，请查看特定平台的命令 `matlab` (Windows)、`matlab` (macOS) 或 `matlab` (Linux)。 |
| `CancellationToken token` | 用于取消异步任务的取消令牌。默认值为 `System.Threading.CancellationToken.None`。 |

## 返回值

当 `MATLABEngine` 实例化并连接到 MATLAB、接收到取消请求或发生异常时完成的 `Task`。

## 异常

- `MathWorks.MATLAB.Exception` MATLAB 启动失败。
- `options.MATLABNotAvailableException`
- `System.OperationCanceledException` 接收到已取消的 `System.Threading.CancellationToken` 的请求。
- `System.ArgumentNull` Null字符串不是有效参数。

## C# 示例

在后台启动两个 MATLAB 会话，在继续之前等待两者都启动。完整的代码示例，请参见“异步启动两个 MATLAB 会话”。

```csharp
try {
    Task<MATLABEngine> startMatlab1 = MATLABEngine.StartMATLABAsync();
    Task<MATLABEngine> startMatlab2 = MATLABEngine.StartMATLABAsync();

    Console.WriteLine("两个 MATLAB 会话正在后台启动.");
    Console.WriteLine("等待两者都启动后再继续...");
    await Task.WhenAll(startMatlab1, startMatlab2);
    Console.WriteLine("两个 MATLAB 会话已启动.");
} catch (MATLABNotAvailableException) {
    Console.WriteLine("无法启动或连接到 MATLAB 引擎.");
}
// 异步启动 MATLAB，但如果操作超过 10 秒则取消
// 创建取消令牌源，并将其设置为在 10 秒后取消
CancellationTokenSource src = new CancellationTokenSource();
src.CancelAfter(TimeSpan.FromSeconds(10));
try {
    // 等待令牌完成
    dynamic matlab = await MATLABEngine.StartMATLABAsync(src.Token);
    Console.WriteLine("MATLAB 已启动.");
} catch (MATLABNotAvailableException) {
    // 无法连接到 MATLAB
    Console.WriteLine("无法启动或连接到 MATLAB 引擎.")
} catch (OperationCanceledException) {
    // 任务在完成前被取消
    Console.WriteLine("任务在完成前已取消.")
} finally {
    src.Dispose();
}
```

# ConnectMATLAB

```csharp
static MATLABEngine ConnectMATLAB();
static MATLABEngine ConnectMATLAB(string name);
```

## 描述

同步连接到本地机器上的共享 MATLAB 会话，如果没有则启动新会话。

- 如果您指定了共享 MATLAB 会话的名称但引擎找不到该名称会话，引擎将抛出 `MathWorks.MATLAB.Exceptions.MATLABNotAvailableException`。
- 如果未指定名称且没有可用的共享 MATLAB 会话，引擎将使用默认选项启动新的共享会话。
- 如果未指定名称且有可用的共享 MATLAB 会话，引擎将连接到第一个可用会话。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `string name` | 共享 MATLAB 会话的名称。使用 `FindMATLAB` 获取共享 MATLAB 会话的名称。 |

## 返回值

`MATLABEngine` 实例

## 异常

- `MathWorks.MATLAB.Exception` MATLAB 启动失败。
- `options.MATLABNotAvailableException`
- `System.ArgumentNull` Null字符串不是有效参数。

## C# 示例

连接到特定的 MATLAB 会话。

```csharp
// 查找共享 MATLAB 会话
string[] names = MATLABEngine.FindMATLAB();
// ... 选择名称的逻辑
using (dynamic matlab = MATLABEngine.ConnectMATLAB(name))
{
    matlab.disp(RunOptions(nargout: 0), "Hello, shared MATLAB.");
}
```

## VB.NET 示例

连接到特定的 MATLAB 会话。

```vb
Option Strict Off
' 查找共享 MATLAB 会话
Dim names As String() = MATLABEngine.FindMATLAB()
If names.Length = 0 Then
    Console.WriteLine("未找到共享 MATLAB 会话.")
End If
Dim myMATLAB = names(0) ' 选取第一个
Using matlab = MATLABEngine.ConnectMATLAB(myMATLAB)
matlab.disp(NewOptions(nargout=0), "Hello, shared MATLAB.")
```

# ConnectMATLABAsync

```csharp
static Task<MATLABEngine> ConnectMATLABAsync();
static Task<MATLABEngine> ConnectMATLABAsync(string name);
static Task<MATLABEngine> ConnectMATLABAsync(string name, System.Threading.CancellationToken token);
```

## 描述

异步连接到本地机器上的共享 MATLAB 会话，如果没有则启动新会话。

- 如果您指定了共享 MATLAB 会话的名称但引擎找不到该名称会话，引擎将抛出 `MathWorks.MATLAB.Exceptions.MATLABNotAvailableException`。
- 如果未指定名称且没有可用的共享 MATLAB 会话，引擎将使用默认选项启动新的共享会话。
- 如果未指定名称且有可用的共享 MATLAB 会话，引擎将连接到第一个可用会话。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `string name` | 共享 MATLAB 会话的名称。使用 `FindMATLABAsync` 获取共享 MATLAB 会话的名称。 |
| `CancellationToken token` | 用于取消异步任务的取消令牌。默认值为 `System.Threading.CancellationToken.None`。 |

## 返回值

当 `MATLABEngine` 实例化并连接到 MATLAB、接收到取消请求或发生异常时完成的 `Task`。

## 异常

- `MathWorks.MATLAB.Exception` MATLAB 启动失败。
- `options.MATLABNotAvailableException`
- `System.OperationCanceledException` 接收到已取消的 `System.Threading.CancellationToken` 的请求。
- `System.ArgumentNull` Null字符串不是有效参数。

# FindMATLAB

```csharp
static string[] FindMATLAB();
```

## 描述

同步查找本地机器上所有的共享 MATLAB 会话。

## 参数

无

## 返回值

本地机器上共享 MATLAB 会话的名称数组，如果没有则返回空数组。

## C# 示例

连接到特定的 MATLAB 会话。

```csharp
// 查找共享 MATLAB 会话
string[] names = MATLABEngine.FindMATLAB();
if (names.Length == 0)
    Console.WriteLine("未找到共享 MATLAB 会话.")
var myMATLAB = names[0]; // 选取第一个
using (dynamic matlab = MATLABEngine.ConnectMATLAB(myMATLAB))
matlab.disp(RunOptions(nargout: 0), "Hello, shared MATLAB.")
```

## VB.NET 示例

连接到特定的 MATLAB 会话。

```vb
Option Strict Off
' 查找共享 MATLAB 会话
Dim names As String() = MATLABEngine.FindMATLAB()
If names.Length = 0 Then
    Console.WriteLine("未找到共享 MATLAB 会话.")
End If
Dim myMATLAB = names(0) ' 选取第一个
Using matlab = MATLABEngine.ConnectMATLAB(myMATLAB)
matlab.disp(NewOptions(nargout=0), "Hello, shared MATLAB.")
```

# FindMATLABAsync

```csharp
static Task<string[]> FindMATLABAsync(System.Threading.CancellationToken token);
```

## 描述

异步查找并返回本地机器上所有共享 MATLAB 会话的名称。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `CancellationToken token` | 用于取消异步任务的取消令牌。默认值为 `System.Threading.CancellationToken.None`。 |

## 返回值

返回本地机器上所有共享 MATLAB 会话名称数组的 `Task`。

## 抛出

`System.OperationCanceledException` 接收到来自 `System.Threading.CancellationToken` 的取消请求。

## C# 示例

连接到找到共享 MATLAB 会话。



```cs
static async void Main(string[] args) {
    string[] names = await MATLABEngine.FindMATLABAsync();
    if (names.Length == 0)
        Console.WriteLine("No MATLAB sessions available.");
    else {
        dynamic matlab = await MATLABEngine.ConnectMATLABAsync(names[0]);
        matlab.disp(new RunOptions(nargout:0), "Hello, shared MATLAB.");
    }
}
```

# 释放

```
static void Dispose();
```

## 描述

隐式调用以释放系统创建的资源。

## C# 示例

```cs
// 使用 using 块封装以确保不需要的资源正确释放。
using dynamic eng = MATLABEngine.StartMATLAB() {
    eng.disp(new RunOptions(nargout:0), "Hello, world.");
}// 当 "eng" 离开作用范围时，隐式调用 MATLABEngine.Dispose()。
```

## VB.NET 示例

```vb
' Option Strict Off
' 使用 using 块封装以确保不需要的资源正确释放。
Using eng As Object = MATLABEngine.StartMATLAB()
    eng.disp(new RunOptions(nargout:=0), "Hello, world.")
End Using
' 当 "eng" 离开作用范围时，隐式调用 MATLABEngine.Dispose()。
```

# 终止引擎客户端

```
static void TerminateEngineClient();
```

## 描述

运行时释放所有 MATLAB 资源。

## C# 示例

```cs
using (dynamic matlab = MATLABEngine.StartMATLAB()) {
    matlab.disp(new RunOptions(nargout: 0), "Hello, world.");
}
MATLABEngine.TerminateEngineClient();
```

## VB.NET 示例

```vb
' Option Strict Off
Using matlab As Object = MATLABEngine.StartMATLAB()
    matlab.disp(new RunOptions(nargout:=0), "Hello, world.")
End Using
MATLABEngine.TerminateEngineClient();
```

# 调用 MATLAB 函数

```cs
ret = MATLABEngine.matlabfunc(dynamic argl, ..., dynamic argN);
```

```cs
ret = MATLABEngine.matlabfunc(RunOptions options, __);
```

```cs
ret = MATLABEngine.matlabfunc(_, "Name": Value);
```

```cs
ret = MATLABEngine.matlabfunc(_, "Name", Value);
```

## 描述

调用 MATLAB 函数 `matlabfunc`。

## 参数

- `dynamic argl, ..., dynamic argN`：用于 MATLAB 函数的参数，带有默认执行选项。使用 `dynamic` 类型在运行时解析所需的、位置的、命名的和可选参数。由 MATLAB 函数确定 `argl, ..., argN` 的类型。
- `RunOptions options`：选项的执行选项，指定为 `MathWorks.MATLAB.Types.RunOptions` 对象。在函数参数之前指定执行选项。
- `Name and Value Pairs`：参数的键值对，可以使用以下格式之一进行指定：
  - `Name: Value`
  - `"Name", Value`
  其中 `Name` 是参数名，`Value` 是对应的值。在上述任何一种语法的所有参数之后指定名称-值参数。

## 返回

MATLAB 函数的输出。对于同步调用的函数，返回的值为：

- `null`，对于 MATLAB 命令
- 函数输出，对于具有单个输出的函数
- 每个输出的 `ValueTuple`，对于具有多个输出的函数

对于异步调用的函数，返回值是一个 `Task`，该任务在 MATLAB 函数完成、发生异常或任务取消时完成。`Task.Result` 属性包含函数的输出。

## 抛出

```
MathWorks.MATLAB.Exception Connection to MATLAB is lost.
options.MATLABNotAvailableException
```

```
MathWorks.MATLAB.Exception MATLAB run-time error occurred.
options.MATLABExecutionException
```

```
MathWorks.MATLAB.Exception A parameter to the MATLAB function cannot be converted to a native options.UnsupportedT MATLAB type.
```

```
System.InvalidCastException A return value from the MATLAB function cannot be cast to the given .NET type.
```

```
System.OperationCanceledException 接收到来自 System.Threading.CancellationToken 的取消请求。
```

## C# 示例

在引擎对象 `matlab` 上调用 MATLAB `linspace` 函数。完整的代码示例参见“从 .NET 传递变量到 MATLAB”。

```cs
double[] A = matlab.linspace(-5, 5, 10);
```

## 版本历史

在 R2022 中引入。

# 另请参阅

# MathWorks.Types.Array

表示数组的 .NET 类

## 描述

## 类详情

| 命名空间 | MathWorks.Types |
| :--- | :--- |

## 版本历史

在 R2022 中引入。

# 另请参阅

# MathWorks.Types.ScalarObject

表示标量实例的 .NET 类

## 描述

## 类详情

| 命名空间 | MathWorks.Types |
| :--- | :--- |

## 版本历史

在 R2022 中引入。

# 另请参阅

# MathWorks.Types.Workspace

与变量交互的 .NET 类

## 描述

## 类详情

| 命名空间 | MathWorks.Types |
| :--- | :--- |

## 版本历史

在 R2022 中引入。

# 另请参阅

# System.Collections.IReadOnlyDictionary

基类：`Dynamic`。

## 方法摘要

## 公共方法

- `int Count`：工作空间中的变量数量。
- `System.Collections.Generic<string> Keys`：工作空间的名称，指定为集合。
- `System.Collections.Generic<dynamic> Values`：工作空间的值，指定为集合。
- `bool ContainsKey(string key)`：判断工作空间是否包含该键。
- `bool TryGetValue(string key, out dynamic value)`：判断键是否存在并获取值。

## 异常

| 异常类型 | 说明 |
| :--- | :--- |
| `System.Collections.Generic.KeyNotFoundException` | 指定在 MATLAB 中 |
| `System.ArgumentNullException` | 空字符串不是有效参数。 |

## 版本历史

在 R2022 中引入。

# 另请参阅

# MathWorks.MATLAB.Types.RunOptions

指定函数执行选项的 .NET 类

## 描述

从 .Net 调用函数时使用 `RunOptions` 对象传递执行参数。这些选项指定了同步运行、输出流重定向位置以及如何返回参数。

## 类详情

命名空间：`MathWorks.Types`

## 创建

`RunOptions(output, error, nargout, async, cancelToken)`：创建一个通过相应属性设置的 `RunOptions` 实例。

## 属性

- **Output**：输出流，指定为：
  - `null`——使用默认 `Console.Out`。
  - `TextWriter.Null`——忽略标准输出。
  - `TextWriter`——将输出存储在 `TextWriter` 对象中。
  默认 `Console.Out`。
- **Error**：错误流，指定为：
  - `null`——使用默认 `Console.Error`。
  - `TextWriter.Null`——忽略错误消息。
  - `TextWriter`——将错误存储在 `TextWriter` 对象中。
  默认 `Console.Error`。
- **Nargout**：输出参数的数量，指定为 `int`。默认值为 1。
- **Async**：是否异步评估，指定为 `true` 或 `false`。默认值为 `false`。
- **CancelToken**：异步评估的取消标记，指定为 `CancellationToken`。默认值为 `None`。

## 版本历史

在 R2022b 中引入。

# 另请参阅

`Nargout`、`Async`、`CancelToken`、`Output`、`Error`

# matlab::data::ArrayFactory

用于创建数组的 C++ 类

## 描述

使用 `ArrayFactory` 创建 `matlab::data::Array` 对象。

## 类详情

- 命名空间：`matlab::data`
- 包含文件：`ArrayFactory.hpp`

## 构造函数

### 默认构造函数

`ArrayFactory()`

## 抛出

`matlab::data::FailedToLoad`：未加载具体实现类。`ibMatlabDataArrayException`

## 析构函数

`~ArrayFactory()`

## 成员函数

- 第 1-18 页的 `createArray`
- 第 1-20 页的 `createScalar`
- 第 1-20 页的 `createCellArray`
- 第 1-21 页的 `createCharArray`
- 第 1-22 页的 `createStructArray`
- 第 1-23 页的 `createEnumArray`
- 第 1-24 页的 `createSparseArray`
- 第 1-25 页的 `createEmptyArray`
- 第 1-25 页的 `createBuffer`
- 第 1-25 页的 `createFromArrayBuffer`

## createArray

```cpp
template <typename T>
TypedArray<T> createArray(ArrayDimensions dims)

template <typename Itype, typename T>
TypedArray<T> createArray(ArrayDimensions dims,
    ItType begin,
    ItType end,
    InputLayout inputLayout)

template <typename T>
TypedArray<T> createArray(ArrayDimensions dims,
    const T* const begin,
    const T* const end)

template <typename T>
TypedArray<T> createArray(ArrayDimensions dims,
    std::initializer_list<T> data)
```

## 描述

创建一个具有给定维度的 `TypedArray<T>`。如果指定，`createArray` 将用数据填充数组。默认按列优先拷贝数据。要指定数据布局，请使用 `inputLayout`。

## 模板参数

- `Iterator`：指定为 `std::iterator`。
- `T`：元素，指定为以下 C++ 数据类型之一。

| bool | int8_t | int16_t | int32_t | int64_t | uint8_t |
| :--- | :--- | :--- | :--- | :--- | :--- |
| uint16_t | uint32_t | uint64_t | float | double | char16_t |
| matlab::data | std::complete | std::complete | std::complete | std::complete | std::complete |
| matlab::String | x<double> | x<float> | x<int8_t> | x<uint8_t> | x<int16_t> |
| std::complete | std::complete | std::complete | std::complete | std::complete | matlab::data |
| x<uint16_t> | x<int32_t> | x<uint32_t> | x<int64_t> | x<uint64_t> | matlab::MATLABString |

要创建 `matlab::data::object` 元素的数组，请使用 `TypedArray<T> createArray(ArrayDimensions dims, ItType begin, ItType end)` 语法。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `ArrayDimensions dims` | 数组的维度。 |
| `ItType begin` | 提供数据的起始和结束。迭代器的 `value_type` 决定数据类型。 |
| `ItType end` | |
| `InputLayout inputLayout` | 数据的布局。`InputLayout` 为 `COLUMN_MAJOR`（列优先）或 `ROW_MAJOR`（行优先）。 |
| `const T* const begin` | 以 C 风格指针指定的提供数据的起始和结束。此语法支持所有基本类型、复合类型和字符串类型。 |
| `std::initializer_list<T>` | 包含数据的初始化列表。 |

## 抛出

- `matlab::OutOfMemoryException`：无法分配数组。
- `matlab::data::NumberOfElementsExceedsMaximum`：元素数量大于 `size_t`。
- `matlab::data::InvalidArrayType`：`matlab::data::ObjectArray` 的输入类型与 `TypedArray<T>` 不匹配。

## createScalar

```cpp
template <typename T>
TypedArray<T> createScalar(const T val)

TypedArray<String> createScalar(const String val)

TypedArray<String> createScalar(const std::string val)

ObjectArray createScalar(const Object& val);
```

## 描述

创建一个给定值的标量 `TypedArray<T>`。此方法支持算术类型、复合类型和字符串类型。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `const T val` | 标量。 |
| `const String val` | 对于 `std::string` 参数，如果 `val` 是 ASCII 数据，方法将其转换为 UTF16。 |
| `const std::string val` | |
| `const Object& val` | |

## 抛出

| 异常 | 说明 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::NonAsciiCharIn` | 输入的 `std::string` 包含非 ASCII 字符。 |

## 示例

```cpp
#include <MatlabDataArray.hpp>

int main() {
    matlab::data::ArrayFactory factory;

    // 创建包含标量值的向量
    std::vector<matlab::data::Array> args({
        factory.createScalar<int16_t>(100),
        factory.createScalar<int16_t>(60)
    });

    return 0;
}
```



## 相关主题

- 单参数调用函数

## `createCellArray`

```cpp
CellArray createCellArray(ArrayDimensions dims)

template <typename ...Targs>
CellArray createCellArray(ArrayDimensions dims, Targs... data)
```

### 描述

创建一个数据的 `CellArray`。数据按列优先排列。

### 模板参数

- `...Targs` 变参模板：
  - 算术类型
  - 复合类型
  - `matlab::data::String`
  - `std::string`
  - `matlab::data::Array`

### 参数

| 参数 | 描述 |
| :--- | :--- |
| `ArrayDimensions dims` | 数组的维度。 |
| `Targs... data` | 插入单元数组的元素，指定为类型、字符串或 `Array`。 |

### 抛出

| 异常 | 描述 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::NonAsciiCharInData` | 输入的 `std::string` 包含非 ASCII 字符。 |
| `matlab::data::NumberOfElementsExceedsMaximumException` | 元素数量大于 `size_t`。 |

### 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace matlab;
  ArrayFactory f;
  CellArray myArray = f.createCellArray({ 1, 2 },
    f.createCharArray("MATLAB Cell Array"),
    f.createArray<double>({ 2, 2 }, {1, 2, 3, 4}));
  return 0;
}
```

## `createCharArray`

```cpp
CharArray createCharArray(String str)
CharArray createCharArray(std::string str)
```

### 描述

从指定的输入创建一个 1xn `CharArray`，其中 n 是字符串长度。

### 参数

| 参数 | 描述 |
| :--- | :--- |
| `matlab::data::String str` | 填充到数组中的数据。 |
| `std::string str` | 填充到数组中的数据。 |

### 抛出

| 异常 | 描述 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::NonAsciiCharInData` | 输入的 `std::string` 包含非 ASCII 字符。 |
| `matlab::data::InputDataException` | 输入数据异常。 |

### 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace matlab;
  ArrayFactory factory;
  CharArray A = factory.createCharArray("This is a char array");
  return 0;
}
```

## `createStructArray`

```cpp
StructArray createStructArray(ArrayDimensions dims, std::vector<std::string> fieldNames)
```

### 描述

创建一个具有给定维度和字段名的 `StructArray`。

### 参数

| 参数 | 描述 |
| :--- | :--- |
| `ArrayDimensions dims` | 数组的维度。 |
| `std::vector<std::string> fieldNames` | 结构的字段名向量。 |

### 抛出

| 异常 | 描述 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::DuplicateFieldNameInStructException` | 指定了重复的字段名。 |
| `matlab::data::NumberOfElementsExceedsMaximumException` | 元素数量大于 `size_t`。 |

### 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace matlab;
  ArrayFactory f;
  // 创建等于 MATLAB 结构 s 的 CreateStruct:
  // s = struct('loc', {'east'}, 'data', {{1, 2, 3}, {14, 5, 6, 7, 8}});
  StructArray s = f.createStructArray({1, 2}, {"loc", "data"});
  s[0]["loc"] = f.createCharArray("east");
  s[0]["data"] = f.createArray<uint8_t>({1, 3}, {1, 2, 3});
  s[1]["loc"] = f.createCharArray("west");
  s[1]["data"] = f.createArray<double>({1, 5}, {4, 5, 6, 7, 8});
  // 获取由语句定义的值：
  // s(1).data
  Reference<Array> val = s[0]["data"];
  return 0;
}
```

## `createEnumArray`

```cpp
EnumArray createEnumArray(ArrayDimensions dims, std::string className, std::vector<std::string> enums)
EnumArray createEnumArray(ArrayDimensions dims, std::string className)
```

### 描述

创建一个类型为 `className` 的 `EnumArray`，这是一个定义的类。如果指定，该方法将使用枚举名称初始化数组。

### 参数

| 参数 | 描述 |
| :--- | :--- |
| `ArrayDimensions dims` | 数组的维度。 |
| `std::string className` | 枚举数组的类名。 |
| `std::vector<std::string> enums` | 枚举名称列表。 |

### 抛出

| 异常 | 描述 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::MustSpecifyClassNameException` | 未指定类名。 |
| `matlab::data::WrongNumberOfEnumsException` | 提供的枚举数量错误。 |
| `matlab::data::NumberOfElementsExceedsMaximumException` | 元素数量大于 `size_t`。 |

### 示例

为此类定义的 `TextColor.Blue` 枚举参数创建一个 `matlab::data::EnumArray` 对象。

```cpp
classdef TextColor
  enumeration
    Red
    Green
    Blue
  end
end
```

将值移动到参数向量。

```cpp
#include "MatlabData.hpp"
#include <vector>

int main() {
  using namespace matlab::data;
  ArrayFactory f;
  auto blue = f.createEnumArray({1, 1}, "Color", { "Blue" });
  // 创建一个参数向量
  std::vector<Array> args = { "My text", std::move(blue) };
  return 0;
}
```

更多示例，请参阅“从 C++ 向 MATLAB 传递枚举值”。

## `createSparseArray`

```cpp
template <typename T>
SparseArray<T> createSparseArray(ArrayDimensions dims, size_t nnz, buffer_ptr<T> data, buffer_ptr<size_t> rows, buffer_ptr<size_t> cols)
```

### 描述

创建一个具有行-列维度的 `SparseArray<T>`。稀疏数组只能有两个维度。该方法不会复制缓冲区，并且数组将获取内存的所有权。

### 模板参数

- `T`: 元素类型，如指定的 `double`、`bool` 或 `std::complex<double>`。

### 参数

| 参数 | 描述 |
| :--- | :--- |
| `ArrayDimensions dims` | 数组的维度。 |
| `size_t nnz` | 非零元素的数量。 |
| `buffer_ptr<T> data` | 包含非零元素的缓冲区。 |
| `buffer_ptr<size_t> rows` | 包含每个元素行值的缓冲区。 |
| `buffer_ptr<size_t> cols` | 包含每个元素列值的缓冲区。 |

### 异常

| 异常 | 描述 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::InvalidDimensionsException` | 指定的维度超过两个。 |
| `matlab::data::NumberOfElementsExceedsMaximumException` | 元素数量大于 `size_t`。 |

### 示例

```cpp
#include "MatlabDataArray.hpp"
#include <vector>

int main() {
    std::vector<double> data = {2.5, 2.9};
    std::vector<size_t> rows = {0, 1};
    std::vector<size_t> cols = {0, 4};
    size_t nnz = 2; // 修正：data/rows/cols 大小应一致

    matlab::ArrayFactory factory;
    auto data_ptr = factory.createBuffer<double>(nnz);
    auto rows_ptr = factory.createBuffer<size_t>(nnz);
    auto cols_ptr = factory.createBuffer<size_t>(nnz);

    double* dataPtr = data_ptr.get();
    size_t* rowsPtr = rows_ptr.get();
    size_t* colsPtr = cols_ptr.get();

    std::copy(data.begin(), data.end(), dataPtr);
    std::copy(rows.begin(), rows.end(), rowsPtr);
    std::copy(cols.begin(), cols.end(), colsPtr);

    matlab::data::SparseArray<double> arr = factory.createSparseArray({2, 9}, nnz, std::move(data_ptr), std::move(rows_ptr), std::move(cols_ptr));
    return 0;
}
```

## `matlab::data::ArrayFactory`

### `createEmptyArray`

```cpp
Array createEmptyArray()
```

#### 描述

创建一个不包含任何元素的空 `Array`。

#### 返回

- `Array`: 空数组。

#### 异常

- `matlab::OutOfMemoryException`: 无法分配数组。

### `createBuffer`

```cpp
template <typename T>
buffer_ptr<T> createBuffer(size_t numberOfElements)
```

#### 描述

创建一个未初始化的缓冲区，用于传递给 `createArrayFromBuffer` 方法。

#### 模板参数

- `T`: 原始类型。

#### 参数

- `size_t numberOfElements`: 元素数量，而非实际缓冲区大小。

#### 返回

- `buffer_ptr<T>`: 包含缓冲区的 `Unique_ptr`。

#### 异常

- `matlab::OutOfMemoryException`: 无法分配数组。

### `createArrayFromBuffer`

```cpp
template <typename T>
TypedArray<T> createArrayFromBuffer(ArrayDimensions dims, buffer_ptr<T> buffer, MemoryLayout memoryLayout = MemoryLayout::COLUMN_MAJOR)
```

#### 描述

使用给定的缓冲区创建一个 `TypedArray<T>`。

#### 模板参数

- `T`: 原始类型。

#### 参数

| 参数 | 描述 |
| :--- | :--- |
| `ArrayDimensions dims` | 数组的维度。 |
| `buffer_ptr<T> buffer` | 包含数据的缓冲区。缓冲区不会被拷贝。`TypedArray<T>` 对象获取缓冲区的所有权。 |
| `MemoryLayout memoryLayout` | 输入缓冲区和创建数组的内存布局，指定为 `MemoryLayout::COLUMN_MAJOR` 或 `MemoryLayout::ROW_MAJOR`。默认布局为 `COLUMN_MAJOR`。 |

在使用 `createArrayFromBuffer` 创建的数组上使用 `matlab::data::TypedIterator<T>` 时，`MemoryLayout` 会影响返回元素的顺序。此参数是可选的。

#### 异常

| 异常 | 描述 |
| :--- | :--- |
| `matlab::OutOfMemoryException` | 无法分配数组。 |
| `matlab::data::InvalidArrayTypeException` | 缓冲区类型无效。 |
| `matlab::data::InvalidMemoryLayoutException` | 无效的内存布局。 |
| `matlab::data::NumberOfElementsExceedsMaximumException` | 元素数量大于 `size_t`。 |

#### 版本历史

在 R2017 中引入。

#### 另见

- `matlab::data::Reference<Array>`

## `matlab::data::Reference<Array>`

### 描述

使用 `Reference<Array>` 类来获取结构或单元格数组的引用。 `ArrayRef` 定义如下：

```cpp
using ArrayRef = Reference<Array>;
```

### 类详情

| 特性 | 值 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含 | `ArrayReference.hpp` |

### 成员函数

- `getType`
- `getDimensions`
- `getNumberOfElements`
- `isEmpty`

### `getType`

```cpp
ArrayType getType() const
```

#### 返回

| 类型 | 描述 |
| :--- | :--- |
| `ArrayType` | 数组类型。 |

#### 异常

- `matlab::data::NotEnoughIndicesException`: 提供的索引不足。
- `matlab::data::InvalidArrayIndexException`: 对于该数组或其索引无效。

### `getDimensions`

```cpp
ArrayDimensions getDimensions() const
```

#### 返回

| 类型 | 描述 |
| :--- | :--- |
| `ArrayDimensions` | 数组维度。 |

#### 异常

- `matlab::data::NotEnoughIndicesException`: 提供的索引不足。
- `matlab::data::InvalidArrayIndexException`: 对于该数组或其索引无效。

### `getNumberOfElements`

```cpp
size_t getNumberOfElements() const
```



## 返回

| 类型 | 描述 |
| :--- | :--- |
| `size_t` | 数组元素数量。 |

## 异常

- `matlab::data::NotEnoughIndexException`: 提供的索引不足。
- `matlab::data::InvalidArrayIndexException`: 对于该数组或其索引无效。

## isEmpty

```cpp
bool isEmpty() const
```

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `bool` | 如果数组为空则返回 `true`，否则返回 `false`。 |

## 异常

- `matlab::data::NotEnoughIndexException`: 提供的索引不足。
- `matlab::data::InvalidArrayIndexException`: 对于该数组或其索引无效。

## 自由函数

- `getReadOnlyElements` 第 128 页
- `getWritableElements` 第 129 页

## getReadOnlyElements

```cpp
template<typename T>
Range<Iterator, T> const getReadOnlyElements(const Reference<Array>& ref)
```

## 描述

获取包含 `Array` 或 `Reference<Array>` 元素的范围。范围内的迭代器是 const。

## 参数

- `const Reference<Array>& ref`

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `Range<TypedIterator, T> const` | 包含输入 `Reference<Array>` 开始和结束迭代器的范围。 |

## 异常

- `matlab::data::InvalidArrayException`: 数组不包含类型 `T`。

## getWritableElements

```cpp
template <typename T>
Range<Iterator, T> getWritableElements(Reference<Array>& ref)
```

## 描述

获取包含 `Array` 或 `Reference<Array>` 元素的范围。范围内的迭代器是非 const。

## 参数

- `Reference<Array>& ref`

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `Range<TypedIterator, T>` | 包含输入 `Reference<Array>` 开始和结束迭代器的范围。 |

## 异常

- `matlab::data::InvalidArrayException`: 数组不包含类型 `T`。

## C++ 数据类型转换

| MATLAB ArrayType 值 | C++ 类型 | 说明 |
|---|---|---|
| `DOUBLE` | `double` | 双精度（64位）浮点数 |
| `SINGLE` | `float` | 单精度（32位）浮点数 |
| `INT8` | `int8_t` | 有符号 8 位整数 |
| `UINT8` | `uint8_t` | 无符号 8 位整数 |
| `INT16` | `int16_t` | 有符号 16 位整数 |
| `UINT16` | `uint16_t` | 无符号 16 位整数 |
| `INT32` | `int32_t` | 有符号 32 位整数 |
| `UINT32` | `uint32_t` | 无符号 32 位整数 |
| `INT64` | `int64_t` | 有符号 64 位整数 |
| `UINT64` | `uint64_t` | 无符号 64 位整数 |
| `CHAR` | `char16_t` | 16 字符 |
| `LOGICAL` | `bool` | 逻辑型 |
| `COMPLEX_DOUBLE` | `std::complex<double>` | 复数，双精度（64位）浮点数 |
| `COMPLEX_SINGLE` | `std::complex<float>` | 复数，单精度（32位）浮点数 |
| `COMPLEX_INT8` | `std::complex<int8_t>` | 复数，有符号 8 位整数 |
| `COMPLEX_UINT8` | `std::complex<uint8_t>` | 复数，无符号 8 位整数 |
| `COMPLEX_INT16` | `std::complex<int16_t>` | 复数，有符号 16 位整数 |
| `COMPLEX_UINT16` | `std::complex<uint16_t>` | 复数，无符号 16 位整数 |
| `COMPLEX_INT32` | `std::complex<int32_t>` | 复数，有符号 32 位整数 |
| `COMPLEX_UINT32` | `std::complex<uint32_t>` | 复数，无符号 32 位整数 |
| `COMPLEX_INT64` | `std::complex<int64_t>` | 复数，有符号 64 位整数 |
| `COMPLEX_UINT64` | `std::complex<uint64_t>` | 复数，无符号 64 位整数 |
| `CELL` | `matlab::data::Array` | 包含其他数组的数组 |
| `STRUCT` | `matlab::data::Struct` | 包含不同类型和大小命名字段的数组 |
| `VALUE_OBJECT` | `matlab::data::Object` | MATLAB 值对象 |
| `HANDLE_OBJECT_REF` | `matlab::data::Object` | MATLAB 中现有句对象的引用 |
| `ENUM` | `matlab::data::Enumer` | 枚举值数组 |

## API 参考

| MATLAB Array 值 | C++ 类型 | 说明 |
|---|---|---|
| `SPARSE LOGICAL` | `bool` | 逻辑型稀疏数组 |
| `SPARSE DOUBLE` | `double` | `double` 稀疏数组 |
| `SPARSE COMPLEX DOUBLE` | `std::complex<double>` | 复数 `double` 稀疏数组 |
| `MATLAB_STRING` | `matlab::data::MatlabString` | MATLAB 字符串 |

## 示例

### COMPLEX_DOUBLE 测试数组

假设你有一个如下声明的数组。

`matlab::data::TypedArray<double> const argArray`

在为 `argArray` 设置值后，调用 `sqrt` 函数。

```cpp
matlab::data::Array count results = matlab::pytr::eval(u'sqrt', argArray);
```

这些语句测试了类型 `COMPLEX_DOUBLE` 的结果并设置了数组类型。

```cpp
matlab::data::TypedArray<std::complex<double>> results = factory.createEmptyArray();

matlab::data::ArrayType type = results.getType();

if (type == matlab::data::ArrayType::COMPLEX_DOUBLE)
    results = (matlab::data::TypedArray<std::complex<double>>)results;
else
    std::cout << "ERROR: complex double array expected." << std::endl;
```

## 版本历史

引入于 R2017b

## 参阅

`matlab::data::apply_visitor`

## 话题

- "处理输入和输出"
- "Typed, Cell 和 Structure Arrays"

# matlab::data::CellArray

访问元胞数组的 C++ 类

## 说明

`CellArray` 是类型为 `Array` 的 `TypedArray`。使用 `CellArray` 对象访问元胞数组。要创建 `CellArray`，请在 `ArrayFactory` 类中调用 `createCellArray`。

```cpp
using CellArray = TypedArray<Array>;
```

## 类细节

- 命名空间：`mat::data`
- 包含：`TypedArray.hpp`

## 版本历史

引入于 R2017b

## 参阅

`createCellArray`

# matlab::data::CharArray

访问字符数组的 C++ 类

## 说明

使用 `CharArray` 对象处理字符数组。要创建 `CharArray`，请在 `ArrayFactory` 类中调用 `createCharArray`。

## 类细节

| 命名空间 | 基类 | 包含 |
| :--- | :--- | :--- |
| `matlab::data` | `TypedArray<char16_t>` | `CharArray.hpp` |

## 构造函数

- "拷贝构造函数" 第 34 页
- "赋值运算符" 第 35 页
- "移动构造函数" 第 35 页
- "赋值运算符" 第 36 页

## 拷贝构造函数

```cpp
CharArray(const CharArray& rhs)
CharArray(const Array& rhs)
```

## 说明

创建 `CharArray` 对象的共享拷贝。

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `const CharArray& rhs` | 要拷贝的值 |
| `const Array& rhs` | 指定的 `ArrayType::CHAR` 对象 |

## 抛出

`matlab::data::InvalidT` 输入 `Array` 不是 `ArrayType::CHAR`。

## 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace::data;
  ArrayFactory factory;
  CharArray A = factory.createCharArray("This is char array");
  CharArray(A);
  return 0;
}
```

## 相关话题

`createCharArray`

## 赋值运算符

```cpp
CharArray& operator=(const CharArray& rhs)
CharArray& operator=(Array& rhs)
```

## 说明

将拷贝赋值给 `CharArray` 对象。

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `const CharArray& rhs` | 要拷贝的值 |
| `const Array& rhs` | 指定的 `ArrayType::CHAR` 对象 |

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `CharArray&` | 更新的实例 |

## 抛出

`matlab::data::InvalidT` 输入 `Array` 不是 `ArrayType::CHAR`。

## 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace::data;
  ArrayFactory factory;
  CharArray A = factory.createCharArray("This is char array");
}
```

## 移动构造函数

```cpp
CharArray(CharArray&& rhs)
CharArray(Array&& rhs)
```

## 说明

移动 `CharArray` 对象的内容。

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `CharArray&& rhs` | 要移动的值 |
| `Array&& rhs` | 指定的 `ArrayType::CHAR` 对象 |

## 抛出

`matlab::data::InvalidT` 输入 `Array` 不是 `ArrayType::CHAR`。

## 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace::data;
  ArrayFactory factory;
  CharArray A = factory.createCharArray("This is char array");
  // 移动构造函数 - 移动数据。A 无效。
  CharArray B(std::move(A));
  return 0;
}
```

## 移动赋值运算符

```cpp
CharArray& operator=(CharArray&& rhs)
CharArray& operator=(Array&& rhs)
```

## 说明

将输入赋值给此 `CharArray` 对象。

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `CharArray&& rhs` | 要移动的值 |
| `Array&& rhs` | 指定的 `ArrayType::CHAR` 对象 |

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `CharArray&` | 更新的实例 |

## 抛出

`matlab::data::InvalidT` 输入 `Array` 不是 `ArrayType::CHAR`。

## 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace::data;
  ArrayFactory factory;
  CharArray A = factory.createCharArray("This is char array");
  // 移动赋值 - 移动数据。A 不可用。
  CharArray B;
  B = std::move(A);
  return 0;
}
```

## 成员函数

- `toUTF16` 第 1-37 页
- `toAscii` 第 1-37 页

## toUTF16

```cpp
String toUTF16() const
```

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `matlab::data::String` | `CharArray` 的内容作为 `matlab::data::String` 字符串 |

## 抛出

无

## toAscii

```cpp
std::string toAscii() const
```

## 返回

| 类型 | 描述 |
| :--- | :--- |
| `std::string` | `CharArray` 的内容作为 ASCII 字符串 |

## 抛出

| 异常 | 描述 |
| :--- | :--- |
| `matlab::data::NonAsciiChar` | 数据包含非 ASCII 字符。 |
| `RequestedAsciiOutputException` |  |

## 示例

```cpp
#include "MatlabDataArray.hpp"

int main() {
    using namespace::data;
    ArrayFactory f;
    auto arr = f.createCharArray("helloworld");
    std::string s = arr.toAscii();
    return 0;
}
```

## 相关话题

"在 MATLAB 中求数学函数"

## 版本历史

引入于 R2017b

## 参阅

`matlab::data::String` | `TypedArray` | "createCharArray" 第 1-21 页

# matlab::data::Reference<CharArray>

获取 `CharArray` 引用的 C++ 类

## 说明

`CharArrayExt` 扩展了用于 `CharArray` 引用的 API。

## 类细节

| 命名空间 | 基类 | 包含 |
| :--- | :--- | :--- |
| `matlab::data` | `Reference<Array>` | `TypedArrayRef.hpp` |

## 成员函数

- `toUTF16` 第 1-39 页
- `toAscii` 第 1-39 页

## 另见

`CharArray` | `Reference<TypedArray<T>>`

# matlab::data::ColumnMajor

用于创建按列优先顺序迭代的迭代器和范围的 C++ 类

## 描述

使用 `ColumnMajor` 类创建按列优先顺序访问数组元素的迭代器和范围。要确定数组的内存布局，请调用 `getMemoryLayout`。

## 类详情

| 命名空间 | 包含 |
| :--- | :--- |
| `matlab::data` | `ColumnMajorIterator.hpp` |

## 迭代器

- "起始迭代器" 第 1-41 页
- "结束迭代器" 第 1-42 页

## 起始迭代器

```cpp
template <typename T>
static ColumnMajorIterator<T> begin(Array& arr);

template <typename T>
static ColumnMajorIterator<T> begin(TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> begin(Reference<Array<T>>& ref);

template <typename T>
static ColumnMajorIterator<T> begin(TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const begin(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const begin(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const begin(const Reference<Array<T>>& ref);

template <typename T>
```



# ColumnMajorIterator API 参考

## begin

```cpp
template <typename T>
static ColumnMajorIterator<T> begin(Array& arr);

template <typename T>
static ColumnMajorIterator<T> begin(TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> begin(Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> begin(TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const begin(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const begin(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const begin(const Reference<Array<T>>& ref);

template <typename T>
static ColumnMajorIterator<T> const begin(const TypedArrayRef<T>& ref);
```

### 描述

创建一个指向输入数组开头的 `ColumnMajorIterator`。为了在从数组读取数据时获得最佳性能，请使用返回 `ColumnMajorIterator<T> const` 的函数。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 用于创建迭代器的数组。 |
| `TypedArray<T>& arr` | 用于创建迭代器的数组。 |
| `Reference<Array>& ref` | 用于创建迭代器的数组的引用。 |
| `TypedArrayRef<T>& ref` | 用于创建迭代器的数组的引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `ColumnMajorIterator<T>` | 指向数组开头的非常量迭代器。 |
| `ColumnMajorIterator<T> const` | 指向数组开头的常量迭代器。 |

### 抛出异常

`matlab::data::TypeMismatch` - 数组元素与 `<T>` 不匹配异常。

---

## end / cend

```cpp
template <typename T>
static ColumnMajorIterator<T> end(Array& arr);

template <typename T>
static ColumnMajorIterator<T> end(TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> end(Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> end(TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const end(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const end(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const end(const Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> const end(const TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const cend(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const cend(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const cend(const Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> const cend(const TypedArrayRef<T>& ref);
```

### 描述

创建一个指向输入数组末尾的 `ColumnMajorIterator`。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 用于创建迭代器的常量或非常量数组。 |
| `TypedArray<T>& arr` | 用于创建迭代器的常量或非常量数组。 |
| `Reference<Array>& ref` | 用于创建迭代器的常量或非常量数组引用。 |
| `TypedArrayRef<T>& ref` | 用于创建迭代器的常量或非常量数组引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `ColumnMajorIterator<T>` | 指向数组末尾的非常量迭代器。 |
| `ColumnMajorIterator<T> const` | 指向数组末尾的常量迭代器。 |

### 抛出异常

`matlab::data::TypeMismatch` - 数组元素与 `<T>` 不匹配异常。

---

## readOnlyElements

```cpp
template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const Array& arr);

template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const TypedArray<T>& arr);

template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const Reference<Array>& ref);

template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const TypedArrayRef<T>& ref);
```

### 描述

创建一个包含迭代器的范围。为了在从数组读取数据时获得最佳性能，请使用返回 `Range const` 的函数。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 输入数组。 |
| `TypedArray<T>& arr` | 输入数组。 |
| `Reference<Array>& ref` | 数组的引用。 |
| `TypedArrayRef<T>& ref` | 数组的引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `Range<ColumnMajorIterator<T> const>` | 常量迭代器范围。 |

---

## writableElements

```cpp
template <typename T>
static Range<ColumnMajorIterator<T>> writableElements(Array& arr);

template <typename T>
static Range<ColumnMajorIterator<T>> writableElements(TypedArray<T>& arr);

template <typename T>
static Range<ColumnMajorIterator<T>> writableElements(Reference<Array>& ref);

template <typename T>
static Range<ColumnMajorIterator<T>> writableElements(TypedArrayRef<T>& ref);
```

### 描述

创建一个包含迭代器的范围，用于写入数组数据。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 输入数组。 |
| `TypedArray<T>& arr` | 输入数组。 |
| `Reference<Array>& ref` | 数组的引用。 |
| `TypedArrayRef<T>& ref` | 数组的引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `Range<ColumnMajorIterator<T>>` | 非常量迭代器范围。 |



## 描述

创建一个包含迭代器的范围。为了在从数组读取数据时获得最佳性能，请使用返回 `Range const` 的函数。

## 参数

| `Array& arr` | 输入数组。 |
| `TypedArray<T>& arr` | 输入数组。 |
| `Reference<Array>& ref` | 数组的引用。 |
| `TypedArrayRef<T>& ref` | 数组的引用。 |

## 返回

| `Range<ColumnMajorIterator<T> const>` | 常量迭代器范围。 |

# matlab::data::ColumnMajorIterator<T>

用于提供列优先随机访问迭代器的模板 C++ 类。

## 描述

`ColumnMajorIterator` 按列优先顺序遍历数组中的元素。更多信息，请参见“MATLAB 随机访问迭代器”。

## 类详情

+ 命名空间: `matlab::data`
+ 包含: `ColumnMajorIterator.hpp`

## 模板参数

| T | 所引的元素类型。 |
|---|---|
| `double` | |
| `float` | |
| `int8_t` | |
| `uint8_t` | |
| `int16_t` | |
| `uint16_t` | |
| `int32_t` | |
| `uint32_t` | |
| `int64_t` | |
| `uint64_t` | |
| `bool` | |
| `std::complex<double>` | |
| `std::complex<float>` | |
| `std::complex<int8_t>` | |
| `std::complex<uint8_t>` | |
| `std::complex<int16_t>` | |
| `std::complex<uint16_t>` | |
| `std::complex<int32_t>` | |
| `std::complex<uint32_t>` | |
| `std::complex<int64_t>` | |
| `std::complex<uint64_t>` | |

## 模板实例化

```
matlab::data::Array
matlab::data::Struct
matlab::data::Enumeration
matlab::data::String
```

## 构造函数

+ [拷贝构造函数](#拷贝构造函数)
+ [拷贝赋值](#拷贝赋值)
+ [移动构造函数](#移动构造函数)
+ [移动赋值](#移动赋值)

## 拷贝构造函数

```
ColumnMajorIterator(const ColumnMajorIterator<T>& rhs)
```

## 描述

创建一个 `ColumnMajorIterator` 对象的拷贝。

## 参数

| `const ColumnMajorIterator<T>& rhs` | 要拷贝的值 |

## 抛出

None

## 拷贝赋值

```
ColumnMajorIterator<T>& operator=(const ColumnMajorIterator<T>& rhs)
```

## 描述

将新值赋给 `ColumnMajorIterator` 对象。

## 参数

| `const ColumnMajorIterator<T>& rhs` | 要赋值的值 |

## 返回

| `ColumnMajorIterator<T>&` | 更新的实例。 |

## 抛出

None

## 移动构造函数

```
ColumnMajorIterator(ColumnMajorIterator<T> &&rhs)
```

## 另见

`CharArray` | `Reference<TypedArray<T>>`

# matlab::data::ColumnMajor

用于创建按列优先顺序迭代的迭代器和范围的 C++ 类。

## 描述

使用 `ColumnMajor` 类创建按列优先顺序访问数组元素的迭代器和范围。要确定数组的内存布局，请调用 `getMemoryLayout`。

## 类详情

| 命名空间: | `matlab::data` |
| 包含: | `ColumnMajorIterator.hpp` |

## 迭代器

+ [开始迭代器](#开始迭代器)
+ [结束迭代器](#结束迭代器)

## 开始迭代器

```
template <typename T>
static ColumnMajorIterator<T> begin(Array& arr);

template <typename T>
static ColumnMajorIterator<T> begin(TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> begin(Reference<Array<T>>& ref);

template <typename T>
static ColumnMajorIterator<T> begin(TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const begin(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const begin(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const begin(const Reference<Array<T>>& ref);

template <typename T>
static ColumnMajorIterator<T> const begin(const TypedArrayRef<T>& ref);
```

## 描述

创建一个指向输入数组开头的 `ColumnMajorIterator`。为了在从数组读取数据时获得最佳性能，请使用返回 `ColumnMajorIterator<T> const` 的函数。

## 参数

| `Array& arr` | 用于创建迭代器的数组。 |
| `TypedArray<T>& arr` | 用于创建迭代器的数组。 |
| `Reference<Array>& ref` | 用于创建迭代器的数组引用。 |
| `TypedArrayRef<T>& ref` | 用于创建迭代器的数组引用。 |

## 返回

| `ColumnMajorIterator<T>` | 指向数组开头的非 const 迭代器。 |
| `ColumnMajorIterator<T> const` | 指向数组开头的 const 迭代器。 |

## 抛出

`matlab::data::TypeMismatch` 数组元素与 `<T>` 不匹配异常。

## 结束迭代器

```
template <typename T>
static ColumnMajorIterator<T> end(Array& arr);

template <typename T>
static ColumnMajorIterator<T> end(TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> end(Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> end(TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const end(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const end(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const end(const Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> const end(const TypedArrayRef<T>& ref);
```



# `ColumnMajorIterator` 静态成员函数

## `end` 重载

```cpp
template <typename T>
static ColumnMajorIterator<T> end(TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const end(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const end(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const end(const Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> const end(const TypedArrayRef<T>& ref);

template <typename T>
static ColumnMajorIterator<T> const cend(const TypedArray<T>& arr);

template <typename T>
static ColumnMajorIterator<T> const cend(const Array& arr);

template <typename T>
static ColumnMajorIterator<T> const cend(const Reference<Array>& ref);

template <typename T>
static ColumnMajorIterator<T> const cend(const TypedArrayRef<T>& ref);
```

### 描述

创建一个指向输入数组末尾的 `ColumnMajorIterator`。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 用于创建迭代器的常量或非常量数组。 |
| `TypedArray<T>& arr` | 用于创建迭代器的常量或非常量数组。 |
| `Reference<Array>& ref` | 用于创建迭代器的常量或非常量数组引用。 |
| `TypedArrayRef<T>& ref` | 用于创建迭代器的常量或非常量数组引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `ColumnMajorIterator<T>` | 指向数组末尾的非 const 迭代器。 |
| `ColumnMajorIterator<T> const` | 指向数组末尾的常量迭代器。 |

### 异常

- `matlab::data::TypeMismatch`：数组元素与 `<T>` 不匹配异常。

---

## `readOnlyElements` 重载

```cpp
template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const Array& arr);

template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const TypedArray<T>& arr);

template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const Reference<Array>& ref);

template <typename T>
static Range<ColumnMajorIterator<T> const> readOnlyElements(const TypedArrayRef<T>& ref);
```

### 描述

创建一个包含迭代器的范围。为了在从数组读取数据时获得最佳性能，请使用返回 `Range const` 的函数。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 输入数组。 |
| `TypedArray<T>& arr` | 输入数组。 |
| `Reference<Array>& ref` | 数组的引用。 |
| `TypedArrayRef<T>& ref` | 数组的引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `Range<ColumnMajorIterator<T> const>` | 常量迭代器范围。 |

---

## `writableElements` 重载

```cpp
template <typename T>
static Range<ColumnMajorIterator<T> const> writableElements(Array& arr);

template <typename T>
static Range<ColumnMajorIterator<T> const> writableElements(TypedArray<T>& arr);

template <typename T>
static Range<ColumnMajorIterator<T> const> writableElements(Reference<Array>& ref);

template <typename T>
static Range<ColumnMajorIterator<T> const> writableElements(TypedArrayRef<T>& ref);
```

### 描述

创建一个包含迭代器的范围。为了在从数组读取数据时获得最佳性能，请使用返回 `Range const` 的函数。

### 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 用于创建迭代器的数组。 |
| `TypedArray<T>& arr` | 用于创建迭代器的数组。 |
| `Reference<Array>& ref` | 用于创建迭代器的数组引用。 |
| `TypedArrayRef<T>& ref` | 用于创建迭代器的数组引用。 |

### 返回值

| 返回类型 | 说明 |
| :--- | :--- |
| `ColumnMajorIterator<T>` | 指向数组开头的非 const 迭代器。 |
| `ColumnMajorIterator<T> const` | 指向数组开头的迭代器。 |

### 异常

- `matlab::data::TypeMismatch`：数组元素与 `<T>` 不匹配异常。



# 描述

创建一个包含迭代器的范围。为了在从数组读取数据时获得最佳性能，请使用返回 `Range const` 的函数。

## 参数

| 参数 | 描述 |
|---|---|
| `Array& arr` | 输入数组。 |
| `TypedArray<T>& arr` | 输入数组。 |
| `Reference<Array>& ref` | 数组的引用。 |
| `TypedArrayRef<T>& ref` | 数组的引用。 |

## 返回

| 返回值 | 描述 |
|---|---|
| `Range<ColumnMajorIterator<T> const>` | 常量迭代器范围。 |

## 描述

将 `ColumnMajorIterator` 标识的内容移动到新实例中。

## 参数

| 参数 | 描述 |
|---|---|
| `ColumnMajorIterator<T>&& rhs` | 需要移动的值。 |

## 抛出

无

## 移动赋值运算符

`ColumnMajorIterator<T>& operator=(ColumnMajorIterator<T>&& rhs)`

## 描述

将输入转移到此 `ColumnMajorIterator` 对象。

## 参数

| 参数 | 描述 |
|---|---|
| `ColumnMajorIterator<T>&& rhs` | 需要转移的值。 |

## 返回

| 返回值 | 描述 |
|---|---|
| `ColumnMajorIterator<T>&` | 更新后的实例。 |

## 抛出

无

## 版本历史

在 R2022a 中引入

## 另见

`matlab::data::ColumnMajor`

# matlab::data::EnumArray

用于访问 MATLAB 枚举数组的 C++ 类

## 描述

使用 `EnumArray` 对象访问枚举数组。若要创建 `EnumArray`，请在 `ArrayFactory` 类中创建 `createEnumArray`。

## 类详情

| 属性 | 描述 |
|---|---|
| 命名空间 | `matlab::data` |
| 基类 | `TypedArray<Enumeration>` |
| 包含 | `EnumArray.hpp` |

## 构造函数

- [拷贝构造函数](#拷贝构造函数)
- [拷贝赋值运算符](#拷贝赋值运算符)
- [移动构造函数](#移动构造函数)
- [移动赋值运算符](#移动赋值运算符)

## 拷贝构造函数

```
EnumArray(const EnumArray& rhs)
EnumArray(const Array& rhs)
```

## 描述

创建一个 `EnumArray` 对象的共享数据拷贝。

## 参数

| 参数 | 描述 |
|---|---|
| `const EnumArray& rhs` | 需要拷贝的值。 |
| `const Array& rhs` | 指定为 `EnumArray` 对象的值。 |

## 抛出

```
matlab::data::InvalidArrayTypeException: Type of input Array is not ArrayType::ENUM
```

## 拷贝赋值运算符

```
EnumArray& operator=(const EnumArray& rhs)
EnumArray& operator=(const Array& rhs)
```

## 描述

将共享数据拷贝分配给 `EnumArray` 对象。

## 参数

| 参数 | 描述 |
|---|---|
| `const EnumArray& rhs` | 需要拷贝的值。 |
| `const Array& rhs` | 指定为 `ArrayType::ENUM` 对象的值。 |

## 返回

| 返回值 | 描述 |
|---|---|
| `EnumArray&` | 更新后的实例。 |

## 抛出

```
matlab::data::InvalidArrayTypeException: Type of input Array is not ArrayType::ENUM
```

## 移动构造函数

```
EnumArray(EnumArray&& rhs)
EnumArray(Array&& rhs)
```

## 描述

将 `EnumArray` 对象的内容移动到新实例中。

## 参数

| 参数 | 描述 |
|---|---|
| `EnumArray&& rhs` | 需要移动的值。 |
| `Array&& rhs` | 指定为 `ArrayType::ENUM` 对象的值。 |

## 抛出

```
matlab::data::InvalidArrayTypeException: Type of input Array is not ArrayType::ENUM
```

## 移动赋值运算符

```
EnumArray& operator=(EnumArray&& rhs)
EnumArray& operator=(Array&& rhs)
```

## 描述

将输入分配给此 `EnumArray` 对象。

## 参数

| 参数 | 描述 |
|---|---|
| `EnumArray&& rhs` | 需要移动的值。 |
| `Array&& rhs` | 指定为 `ArrayType::ENUM` 对象的值。 |

## 返回

| 返回值 | 描述 |
|---|---|
| `EnumArray&` | 更新后的实例。 |

## 抛出

```
matlab::data::InvalidArrayTypeException: Type of input Array is not ArrayType::ENUM
```

## 成员函数

### getClassName

```
std::string getClassName() const
```

## 描述

返回此 `EnumArray` 的类名。

## 返回

| 返回值 | 描述 |
|---|---|
| `std::string` | 类名。 |

## 抛出

无

## 示例

### 显示枚举值

定义一个枚举类：

```cpp
classdef MyClass
    enumeration
        A
        B
        C
    end
end
```

为 `MyClass.C` 枚举参数定义一个 `matlab::data::EnumArray` 对象并显示值。

```cpp
#include "MatlabDataArray.hpp"
#include "MatlabEngine.hpp"
#include <iostream>

int main() {
    using namespace matlab::data;
    ArrayFactory f;
    auto e = f.createEnumArray({1, 1}, "MyClass", "C");
    // 显示枚举值
    std::cout << "Property value: " << std::string(e[0]) << std::endl;
    return 0;
}
```

## 版本历史

在 R2017b 中引入

## 另见

`TypedArray` | `createEnumArray` | `Enumeration`

# 主题

从 C++ 将枚举值传递给 MATLAB

# matlab::data::Reference<EnumArray>

用于获取 `EnumArray` 引用的 C++ 类

## 描述

`EnumArray` 类扩展了引用可用的 API。

## 类详情

| 属性 | 描述 |
|---|---|
| 命名空间 | `matlab::data` |
| 基类 | `Reference<Array>` |
| 包含 | `TypedArray.hpp` |

## 成员函数

### getClassName

```
std::string getClassName() const
```



# 描述

返回此引用对象的类名。

## 返回

| 列 | 描述 |
|---|---|
| `std::string` | 类名。 |

## 抛出

无

## 版本历史

在 R2017b 中引入

## 另见

`EnumArray` | `Reference<TypedArray<T>>`

# matlab::data::Enumeration

MATLAB 枚举数组的元素类型

## 描述

`Enumeration` 是 `EnumArray` 对象的元素类型。

## 类详情

| 列 | 描述 |
|---|---|
| 命名空间 | `matlab::data` |
| 包含 | `Enumeration.hpp` |

## 版本历史

在 R2017b 中引入

## 另见

`EnumArray`

# 主题

“MATLAB 数据类型”

# Exception

异常的 C++ 基类

## 描述

所有 MATLAB C++ 异常都可以被捕获为 `matlab::Exception`。

## 类详情

| 列 | 描述 |
|---|---|
| 命名空间 | `matlab` |
| 包含 | `Exception.hpp` |

## 版本历史

在 R2017b 中引入

## 另见

主题
“MATLAB 数据异常”

# matlab::data::ForwardIterator<T>

用于为 `StructArray` 字段名提供迭代支持的模板 C++ 类

## 描述

使用 `ForwardIterator` 对象访问 `StructArray` 中字段元素的范围。

## 类详情

| 列 | 描述 |
|---|---|
| 命名空间 | `matlab::data` |
| 包含 | `ForwardIterator.hpp` |

## 模板参数

| 列 | 描述 |
|---|---|
| T | `data::FieldIdentifier` |

## 构造函数

- “拷贝构造函数”
- “拷贝赋值运算符”

## 拷贝构造函数

```cpp
ForwardIterator(const ForwardIterator& rhs)
```

## 描述

创建一个 `ForwardIterator` 对象的共享数据拷贝。

## 参数

| 列 | 描述 |
|---|---|
| `const ForwardIterator& rhs` | 需要拷贝的值。 |

## 返回

| 列 | 描述 |
|---|---|
| `ForwardIterator` | 新实例。 |

## 抛出

无

## 拷贝赋值运算符

```cpp
ForwardIterator& operator=(const ForwardIterator& rhs)
```

## 描述

将共享数据拷贝分配给此 `ForwardIterator` 对象。

## 参数

| 列 | 描述 |
|---|---|
| `const ForwardIterator& rhs` | 需要拷贝的值。 |

## 返回

| 列 | 描述 |
|---|---|
| `ForwardIterator` | 更新后的实例。 |

## 抛出

无

## 运算符

- “operator++”
- “operator--”
- “operator=”
- “operator!=”
- “operator*”
- “operator->”
- “operator[]”

```cpp
ForwardIterator<T>& operator++()
```

## 描述

前置增运算符。

## 返回

| 列 | 描述 |
|---|---|
| `ForwardIterator<T>&` | 更新值的引用。 |

## 抛出

无

```cpp
ForwardIterator<T> operator--(int)
```

## 描述

后置增运算符。

## 返回

| 列 | 描述 |
|---|---|
| `ForwardIterator<T>` | 新对象。 |

## 抛出

无

```cpp
bool operator==(const ForwardIterator& rhs) const
```

## 参数

| 列 | 描述 |
|---|---|
| `const ForwardIterator& rhs` | 需要比较的迭代器。 |

## 返回

| 列 | 描述 |
|---|---|
| `bool` | 如果迭代器指向相同的元素，则返回 true。否则返回 false。 |

## 抛出

无

```cpp
bool operator!=(const ForwardIterator& rhs) const
```

## 参数

| 列 | 描述 |
|---|---|
| `const ForwardIterator& rhs` | 需要比较的迭代器。 |

## 返回

| 列 | 描述 |
|---|---|
| `bool` | 如果此迭代器指向不同的元素，则返回 true。否则返回 false。 |

## 抛出

无

```cpp
reference operator*() const
```

## 描述

返回迭代器指向的元素的拷贝。

## 返回

| 列 | 描述 |
|---|---|
| `reference` | 迭代器指向的元素的拷贝，指定为：
* `T&` 对于算术类型。
* `Reference<T>` 对于非算术类型。 |

## 抛出

无

```cpp
pointer operator->()
```

## 描述

返回迭代器指向的元素的指针。

## 返回

| 列 | 描述 |
|---|---|
| `pointer` | 迭代器指向的元素的指针，指定为：
* `T*` 对于算术类型。
* `Reference<T>*` 对于非算术类型。 |

## 抛出

无

```cpp
reference operator[](const size_t& rhs) const
```

## 描述

使用线性索引获取引用。

## 返回

| 列 | 描述 |
|---|---|
| `reference` | 迭代器指向的元素，指定为 `typename iterator::reference`。 |

## 抛出

无

## 版本历史

在 R2017b 中引入

## 另见

`StructArray` | `MATLABFieldIdentifier`

# matlab::data::MATLABFieldIdentifier

用于识别 MATLAB struct 数组中字段名的 C++ 类

## 描述

## 类详情

| 列 | 描述 |
|---|---|
| 命名空间 | `matlab::data` |
| 包含 | `MATLABFieldIdentifier.hpp` |

## 构造函数

- “默认构造函数”
- “构造函数”
- “析构函数”
- “拷贝构造函数”
- “拷贝赋值运算符”
- “移动构造函数”
- “移动赋值运算符”

## 抛出

无

## 拷贝构造函数

```cpp
MATLABFieldIdentifier(const MATLABFieldIdentifier& rhs)
```

## 描述

创建一个 `MATLABFieldIdentifier` 对象的共享数据拷贝。

## 参数

| 列 | 描述 |
|---|---|
| `const MATLABFieldIdentifier& rhs` | 要拷贝的值。 |

## 抛出

None

## 拷贝赋值运算符

```cpp
MATLABFieldIdentifier& operator=(MATLABFieldIdentifier const& rhs)
```

## 描述

将共享数据拷贝赋值给 `MATLABFieldIdentifier` 对象。

## 参数

| 列 | 描述 |
|---|---|
| `MATLABFieldIdentifier const& rhs` | 要移动的值。 |

## 返回

| 列 | 描述 |
|---|---|
| `MATLABFieldIdentifier&` | 更新后的实例。 |

## 抛出

None

## 移动构造函数

```cpp
MATLABFieldIdentifier(MATLABFieldIdentifier&& rhs)
```

## 描述

将 `MATLABFieldIdentifier` 对象的的内容移动到新实例中。

## 参数

| 列 | 描述 |
|---|---|
| `MATLABFieldIdentifier&& rhs` | 要移动的值。 |

## 抛出

None

## 移动赋值运算符

```cpp
MATLABFieldIdentifier operator=(MATLABFieldIdentifier&& rhs)
```

## 参数

| 列 | 描述 |
|---|---|
| `MATLABFieldIdentifier&& rhs` | 要移动的值。 |

## 返回

| 列 | 描述 |
|---|---|
| `MATLABFieldIdentifier&` | 更新后的实例。 |

## 抛出

None

## 析构函数

```cpp
~MATLABFieldIdentifier()
```

## 描述

销毁一个 `MATLABFieldIdentifier`。

## 其他运算符

```cpp
operator std::string
```

```cpp
operator std::string() const
```

## 返回

`std::string` `MATLABFieldIdentifier` 对象的表示形式。

## 抛出

None

## 自由函数

```cpp
operator==
```

```cpp
bool operator==(const MATLABFieldIdentifier& rhs) const
```

## 描述

检查两个 `MATLABFieldIdentifier` 对象是否相同。

## 参数

| 列 | 描述 |
|---|---|
| `const MATLABFieldIdentifier& rhs` | 要比较的值。 |

## 返回

`bool`
如果对象相同则返回 true。否则，返回 false。

## 抛出

None

## 示例

### 获取结构体内容

使用结构体字段访问访问给 C++ MEX 函数或 C++ Engine 程序的 MATLAB 结构体中的数据。

这里有一个传递给 MEX 函数的结构体。`Date` 字段包含结构体创建时的日期，由 `datetime("today")` 返回。`Data` 字段包含一个数值。

```matlab
s = struct("Date", string(datetime("today")), "Data", 100);
```

在 MEX 函数中，将输入存储为 `StructArray`。使用 `GetFieldNames` 成员函数获取第二个元素，以从 `Data` 字段获取数值数据。将数值数据存储在元素为 `double` 的 `TypedArray` 中。

```cpp
matlab::data::StructArray struct(inputs[0]);
matlab::data::ForwardIterator iter = struct.getFieldNames();
matlab::data::MATLABFieldIdentifier const = iter.next();
fields = inStruct.get<TypedArray<double>> data = inStruct[0][fields.begin()[0]];
double output = data[0];
```

## 版本

在 R2017b 中引入

## 另见

`StructArray` | `ForwardIterator` | `TypedArray<T>`

# 主题

“类型、单元格和结构体数组中的数据访问”
“从 C++ 创建结构体数组”

# matlab::data::MATLABString

MATLAB 字符串数组的元素类型

## 描述

使用 `MATLABString` 在 C++ 中表示 MATLAB 字符串数组。为了能够表示缺失的字符串数组元素，`MATLABString` 定义为：

```cpp
using MATLABString = optional<String>;
```

有关关于 MATLAB 中字符串数组的更多信息，请参见“创建字符串数组”。

## 类细节

| 列 | 描述 |
|---|---|
| 命名空间 | `matlab::data` |
| 包含 | `String.hpp` |

## 示例

### 从 MATLAB 将字符串数组传递到 MEX 函数

在 MATLAB 中创建一个字符串数组并将其传递给 C++ MEX 函数：

```matlab
str(1) = "";
str(2) = "Gemini";
str(3) = string(missing);
result = myMexFcn(str);
```

在 MEX 函数中，将输入赋值为类型为 `matlab::data::MATLABString` 的数组。

```cpp
matlab::data::TypedArray<matlab::data::MATLABString> stringArray = inputs(0);
```

### 从 MEX 函数传递字符串数组到 MATLAB

在 MEX 函数中创建一个字符串数组并作为输出传递给 MATLAB。数组定义元素、空字符串和缺失元素。

```cpp
matlab::data::ArrayFactory factory;
output(0) = factory.createArray<matlab::data::MATLABString>({ 1, 3 });
matlab::data::MATLABString(output(1)) = "";
matlab::data::MATLABString(output(2)) = "Gemini";
matlab::data::MATLABString(output(3)) = missing;
```

返回到 MATLAB 的字符串数组。

```matlab
result = 1x3 string ["Gemini" missing]
```

## 版本历史

在 R2017b 中引入

## 另见

`matlab::data::String` | `matlab::data::optional<T>`

# 主题

“从 MATLAB (MEX 文件) C++ 函数”
“从 C++ 调用 MATLAB”

# matlab::data::Reference<MATLABString>

获取 `StringArray` 元素的 C++ 类

## 描述

当使用 `operator()` 解引用 `StringArray` 时创建 `Reference<MATLABString>` 对象。

## 类细节

| 命名空间 | 包含 |
|---|---|
| `matlab::data` | `MATLABExt.hpp` |

## 转换

```cpp
String operator() const
```

## 返回

`matlab::data::String` 将 `MATLABArray` 转换为 `String`。

## 抛出

| 异常 | 描述 |
|---|---|
| `matlab::data::NotEnoughException` | 未提供索引。 |
| `matlab::data::InvalidArrayIndex` | 提供的索引超出范围。 |
| `matlab::data::TooManyException` | 提供的索引过多。 |
| `std::runtime_error` | 没有值。 |

## 成员函数

- “bool”
- “has_value”

```cpp
operator bool() const
```

## 描述

检查字符串是否包含值。

## 返回

| 运算符 | 描述 |
|---|---|
| `operator` | 如果包含值则返回 true。 |

## 抛出

| 异常 | 描述 |
|---|---|
| `matlab::data::NotEnoughException` | 未提供索引。 |
| `matlab::data::InvalidArrayIndex` | 提供的索引超出范围。 |
| `matlab::data::TooManyException` | 提供的索引过多。 |

## has_value

```cpp
bool has_value() const
```

## 描述

检查字符串是否包含值。

## 返回

| 列 | 描述 |
|---|---|
| `bool` | 如果包含值则返回 true。 |

## 抛出

| 异常 | 描述 |
|---|---|
| `matlab::data::NotEnoughException` | 未提供索引。 |
| `matlab::data::InvalidArrayIndex` | 提供的索引超出范围。 |
| `matlab::data::TooManyException` | 提供的索引过多。 |

## 版本历史

在 R2017b 中引入

## 另见

# matlab::data::Array

所有数组类型的 C++ 基类

## 描述

使用 `Array` 对象表示单数组和多维数组。`Array` 类提供了获取所有数组通用信息的方法，例如维度和类型。该类具有创建深拷贝（克隆）和共享数据拷贝的方法，并支持写时复制。要构造 `Array` 对象，使用 `ArrayFactory` 方法。

## 类细节

| 命名空间 | 包含 |
|---|---|
| `matlab::data` | `Array.hpp` |

## 构造函数

- “默认构造函数”
- “拷贝构造函数”
- “拷贝赋值运算符”
- “移动构造函数”
- “移动赋值运算符”

## 默认构造函数

```cpp
Array()
```

## 抛出

无

## 拷贝构造函数

```cpp
Array(const Array& rhs)
```

## 描述

创建一个 `Array` 对象的共享数据拷贝。

## 参数

| 列 | 描述 |
|---|---|
| `const Array& rhs` | 要拷贝的值。 |

## 抛出

无

## 拷贝赋值运算符

```cpp
Array& operator=(const Array& rhs)
```



## 描述

将共享数据拷贝赋值给 `Array` 对象。

## 参数

| const Array& rhs | 要拷贝的值。 |

## 返回

| Array& | 更新后的实例。 |

## 抛出

无

## 移动构造函数

```cpp
Array(Array&& rhs)
```

## 描述

将 `Array` 对象的的内容移动到新实例中。

## 参数

| Array&& rhs | 要移动的值。 |

## 抛出

无

## 移动赋值运算符

```cpp
Array& operator=(Array&& rhs)
```

## 描述

将输入赋值给此 `Array` 对象。

## 参数

| Array&& rhs | 要移动的值。 |

## 返回

| Array& | 更新后的实例。 |

## 抛出

无

## 析构函数

```cpp
virtual ~Array()
```

## 索引运算符

```cpp
operator[]

ArrayElementRef<false> operator[](size_t idx)

ArrayElementRef<true> operator[](size_t idx) const
```

## 描述

允许在 const 和非 const 数组上使用 `[]` 索引。索引从 0 开始。

## 参数

| size_t idx | 第一个数组索引 |

## 返回

| ArrayElementRef<false> | 包含指定索引的临时对象。返回值允许修改或检索数组元素。 |
| ArrayElementRef<true> | 包含指定索引的临时对象。返回值允许检索数组元素，但不能修改。 |

## 抛出

无

## 成员函数

- `getType()` 第 1-69 页
- `getMemoryLayout()` 第 1-70 页
- `getDimensions()` 第 1-70 页
- `getNumberOfElements()` 第 1-70 页
- `isEmpty()` 第 1-70 页

## getType

```cpp
ArrayType getType() const
```

## 返回

| ArrayType | 数组类型。 |

## API 参考

## getMemoryLayout

```cpp
MemoryLayout getMemoryLayout() const
```

## 返回

| Type | Description |
| :--- | :--- |
| MemoryLayout | 数组的内存布局，指定为 `MemoryLayout::COLUMN_MAJOR`（列主）或 `MemoryLayout::ROW_MAJOR`（行主）。 |

## 抛出

| Exception | Description |
| :--- | :--- |
| matlab::data::FeatureNotSupportedPortedException | R2019a 之前创建的数组不支持不同的布局。内存布局始终为列主。 |

## getDimensions

```cpp
ArrayDimensions getDimensions() const
```

## 返回

| Type | Description |
| :--- | :--- |
| ArrayDimensions | 数组中每个维度的向量。 |

## 抛出

无

## getNumberOfElements

```cpp
size_t getNumberOfElements() const
```

## 返回

| Type | Description |
| :--- | :--- |
| size_t | 数组中的元素数量。 |

## 抛出

无

## isEmpty

```cpp
bool isEmpty() const
```

## 返回

| Type | Description |
| :--- | :--- |
| bool | 如果数组为空则返回 True。如果数组不为空则返回 False。 |

## 抛出

无

## 局函数

- 第 1-71 页的 `getReadOnlyElements`
- 第 1-71 页的 `getWritableElements`

## getReadOnlyElements

```cpp
template <typename T>
Range<TypedIterator, T const> getReadOnlyElements(const Array& arr)
```

## 描述

获取一个包含 `Array` 元素的范围。范围内包含的迭代器是 const 的。

## 参数

| Type | Description |
| :--- | :--- |
| const Array& arr | 数组 |

## 返回

| Type | Description |
| :--- | :--- |
| Range<TypedIterator, T const> | 包含输入 `Array` 起始结束迭代器的范围。 |

## 抛出

| Exception | Description |
| :--- | :--- |
| matlab::data::InvalidArrayType | 数组不包含类型 T。 |

## getWritableElements

```cpp
template <typename T>
Range<TypedIterator, T> getWritableElements(Array& arr)
```

## 描述

获取一个包含 `Array` 元素的范围。范围内包含的迭代器是非 const 的。

## 参数

| Type | Description |
| :--- | :--- |
| Array& arr | 数组 |

## 返回

| Type | Description |
| :--- | :--- |
| Range<TypedIterator, T> | 包含输入 `Array` 起始结束迭代器的范围。 |

## 抛出

| Exception | Description |
| :--- | :--- |
| matlab::data::InvalidArrayType | 数组不包含类型 T。 |

## 版本历史

在 R2017b 中引入

- 增加了对 `matlab::data::Array` 行主序迭代的支持
- 你可以按行主序或列主序创建并遍历 `matlab::data::Array` 的数据。
- 增加了对 N-D 行主内存布局的支持。

- 你可以创建一个具有行主内存布局的 `N-D matlab::data::Array` 对象。此前，`createArrayFromBuffer` 函数仅在 2-D 情况下创建行主数组。要创建一个具有行主内存布局的 `matlab::data::Array` 对象，请将 `createArrayFromBuffer` 的参数 `memoryLayout` 设置为 `MemoryLayout::ROW_MAJOR`。要确定现有 `matlab::data::Array` 对象的内存布局，请调用 `getMemoryLayout`。

## 增加了对行主内存布局的支持

创建一个内存布局指定为列主（默认）或行主的 `matlab::data::Array`。更多信息，请参阅 `createArrayFromBuffer` 中的 `memoryLayout` 参数。要确定现有 `matlab::data::Array` 的内存布局，请调用 `getMemoryLayout`。

## 另请

- `ArrayFactory`

# matlab::data::Object

MATLAB 数组的元素类型

## 描述

`Object` 是 `ObjectArray` 的元素类型。

## 类细节

命名空间：`matlab::data`
包含：`Object.hpp`

## 版本历史

在 R2017b 中引入

## 另请

`ObjectArray`

# matlab::data::ObjectArray

用于访问 MATLAB 对象数组的 C++ 类

## 描述

使用 `ObjectArray` 访问 MATLAB 对象数组。要创建 `ObjectArray`，请在 `ArrayFactory` 类中使用此语法调用 `createArray`：

```cpp
template <typename ItType, typename Tname>
TypedArray<T> createArray(ArrayDimensions dims,
ItType begin,
ItType end)
```

要创建一个标量对象，使用此语法调用 `createScalar`：

```cpp
ObjectArray createScalar(const Object& val);
```

`ObjectArray` 定义为：

```cpp
using ObjectArray = TypedArray<Object>;
```

## 类细节

命名空间：`matlab::data`
包含：`ObjectArray.hpp`

你不能将 `ObjectArray` 的元素组合成异构数组。

如果定义对象的类重写了 `subsref` 或 `subsasign`，则你无法访问 `ObjectArray` 的元素。

## MEX 和 C++ 应用中的对象

C++ MEX 和 C++ Engine 应用程序可以获取和设置 MATLAB 对象的属性值。有关如何在这些应用程序中访问 MATLAB 对象的信息，请参阅以下主题：

- "MATLAB Objects in MEX Functions" - 适用于 C++ MEX 应用
- "Get MATLAB Objects and Access Properties" - 适用于 C++ Engine 应用

## 版本历史

在 R2017b 中引入

## 另请

`Object` | `createArray` | `createScalar`

# matlab::data::optional<T>

表示可选值的模板 C++ 类

## 描述

使用 `optional` 对象表示可能存在也可能不存在的值。

## 类细节

命名空间：`matlab::data`
包含：`Optional.hpp`

## 模板参数

| Type | Description |
| :--- | :--- |
| T | 指定为 `matlab::data` 类型。 |

## 构造函数

- 第 75 页的默认构造函数
- 第 75 页的构造函数
- 第 76 页的赋值运算符

## 默认构造函数

```cpp
optional()
```

## 构造函数

```cpp
optional(const optional& other)
```

## 描述

拷贝构造。

## 参数

| Type | Description |
| :--- | :--- |
| const optional& other | |

## 赋值运算符

```cpp
optional& operator=(const optional& other)
```

## 描述

拷贝赋值。

## 参数

| Type | Description |
| :--- | :--- |
| const optional& other | |

## 移动构造函数

```cpp
optional(optional&& other)
```

## 描述

移动构造。

## 参数

| Type | Description |
| :--- | :--- |
| optional&& other | |

## 移动赋值运算符

```cpp
optional& operator=(optional&& other)
```

## 描述

移动赋值。

## 参数

| Type | Description |
| :--- | :--- |
| optional&& other | |

## bool

```cpp
explicit operator bool() const
```

## 描述

检查对象是否包含值。

## 返回

| Type | Description |
| :--- | :--- |
| bool | 如果包含值则返回 True。 |

## has_value

```cpp
bool has_value() const
```

## 描述

检查对象是否包含值。

## 返回

| Type | Description |
| :--- | :--- |
| bool | 如果包含值则返回 True。 |

## swap

```cpp
void swap(optional&& other)
```

## 描述

将此 `optional` 的值与参数中的值交换。

## 参数

| Type | Description |
| :--- | :--- |
| optional&& other | swap。 |

## reset

```cpp
void reset()
```

## 描述

将 `optional` 值重置为缺失

## operator->

```cpp
const T* operator->() const
```

## 描述

指向元素。

## 返回

| Type | Description |
| :--- | :--- |
| const T* | element。 |

## 抛出

| std::runtime_error | `optional` 对象不包含值。 |

## operator*

```cpp
T& operator*() const
```



## 描述

将 `optional<T>` 转换为 `T`。

## 返回

| Type | Description |
| :--- | :--- |
| T | 如果存在，则为 `optional<T>` 中的值。 |

## 抛出

| Type | Description |
| :--- | :--- |
| `std::runtime_error` | 没有值。 |

# matlab::data::Range<ItType, ElemType>

提供范围操作支持模板 C++ 类。

## 描述

`Range` 对象封装了边界函数以启用范围操作。

## 类细节

- **命名空间**：`matlab::data`
- **包含**：`Range.hpp`

## 模板参数

| Type | Description |
| :--- | :--- |
| `IteratorType` | 迭代器类型 |
| `ElementType` | 元素类型 |

## 构造函数

- [构造函数](#构造函数)
- [移动构造函数](#移动构造函数)
- [移动赋值运算符](#移动赋值运算符)

### 构造函数

`Range(IteratorType<ElementType> begin, IteratorType<ElementType> end)`

#### 描述

创建一个 `Range` 对象。

#### 参数

| Type | Description |
| :--- | :--- |
| `IteratorType<ElementType>` begin | 范围的起始元素。 |
| `IteratorType<ElementType>` end | 范围的结束元素。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `Range` | 新实例。 |

#### 抛出

无

### 移动构造函数

`Range(Range&& rhs)`

#### 说明

将 `Range` 对象的内容移动到新实例。

#### 参数

| Type | Description |
| :--- | :--- |
| `Range&&` rhs | 要移动的 `Range`。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `Range` | 新实例。 |

#### 抛出

无

### 移动赋值运算符

`Range&& operator=(Range&& rhs)`

#### 说明

将输入赋值给此 `Range` 对象。

#### 参数

| Type | Description |
| :--- | :--- |
| `Range&&` rhs | 要移动的 `Range`。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `Range&&` | 更新后的实例。 |

#### 抛出

无

## begin

`IteratorType<ElementType>& begin()`

### 返回

| Type | Description |
| :--- | :--- |
| `IteratorType<ElementType>&` | 范围中的第一个元素。 |

### 抛出

无

## end

`IteratorType<ElementType>& end()`

### 返回

| Type | Description |
| :--- | :--- |
| `IteratorType<ElementType>&` | 范围的结束。 |

### 抛出

无

## 版本历史

引入于 R2017b

## 参见

# matlab::data::Reference<T>

用于获取 `Array` 元素的引用模板 C++ 类。

## 说明

`Reference` 对象是 `Array` 元素的引用，且不产生拷贝。`Reference`：

- 不是共享拷贝
- 只要数组有效就是线程安全的

## 类细节

- **命名空间**：`matlab::data`
- **包含**：`Reference.hpp`

## 模板参数

| Type | Description |
| :--- | :--- |
| `T` | 所引元素的类型，指定为：`Array`、`Struct`、`Enumeration`、`MATLABString`、所有 `std::` 类型 |

## 构造函数

- [拷贝构造函数](#拷贝构造函数)
- [拷贝赋值运算符](#拷贝赋值运算符)
- [移动赋值运算符](#移动赋值运算符)
- [移动构造函数](#移动构造函数)

### 拷贝构造函数

`Reference(const Reference<T>& rhs)`

#### 参数

| Type | Description |
| :--- | :--- |
| `const Reference<T>&` rhs | 要拷贝的值。 |

### 拷贝赋值运算符

`Reference<T>& operator=(const Reference<T>& rhs)`

#### 参数

| Type | Description |
| :--- | :--- |
| `const Reference<T>&` rhs | 要拷贝的值。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `Reference<T>&` | 更新后的实例。 |

### 移动赋值运算符

`Reference<T>& operator=(Reference<T>&& rhs)`

#### 参数

| Type | Description |
| :--- | :--- |
| `Reference<T>&&` rhs | 要移动的值。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `Reference<T>&` | 更新后的实例。 |

#### 抛出

无

### 移动构造函数

`Reference(Reference<T>&& rhs)`

#### 说明

将 `Reference` 对象移动到新实例。

#### 参数

| Type | Description |
| :--- | :--- |
| `Reference<T>&&` rhs | 要移动的值。 |

#### 抛出

无

## 其他运算符

```cpp
Reference<T>& operator=(T rhs)
Reference<T>& operator=(std::string rhs)
Reference<T>& operator=(String rhs)
```

### 参数

| Type | Description |
| :--- | :--- |
| `T` rhs | 要赋值的值。数组必须是非 const。 |
| `std::string` rhs | 要赋值的值。数组必须是非 const 允许赋值。 |
| `String` rhs | 要赋值的 `StringArray`。数组必须是非 const。 |

### 返回

| Type | Description |
| :--- | :--- |
| `Reference<T>&` | 更新后的实例。 |

### 抛出

无

## operator<<

```cpp
std::ostream& operator<<(std::ostream& os, Reference<T> const& rhs)
```

### 参数

| Type | Description |
| :--- | :--- |
| `std::ostream&` os | 输出流。 |
| `Reference<T> const&` rhs | 要输出的引用。 |

### 返回

`std::ostream&`

## operator T()

`operator T() const`

### 说明

从数组转换。

### 返回

| Type | Description |
| :--- | :--- |
| `T` | 数组元素的共享拷贝。 |

### 抛出

无

## operator std::string()

```cpp
operator std::string() const
```

### 说明

将数组转换为 `std::string`，产生 `std::string` 的拷贝。此运算符适用于可以转换为 `std::string` 的类型。

### 返回

`std::string`

### 抛出

| Type | Description |
| :--- | :--- |
| `DataException` | Input 为 `std::string` 且包含非 ASCII 字符。 |
| `std::runtime_error` | `MATLABString` 缺失。 |

## 友元函数

## operator==

```cpp
inline bool operator==(Reference<MATLABString> const& lhs, std::string const& rhs)
inline bool operator==(std::string const& lhs, Reference<MATLABString> const& rhs)
inline bool operator==(Reference<MATLABString> const& lhs, String const& rhs)
inline bool operator==(String const& lhs, Reference<MATLABString> const& rhs)
inline bool operator==(Reference<MATLABString> const& lhs, MATLABString const& rhs)
inline bool operator==(MATLABString const& lhs, Reference<MATLABString> const& rhs)
inline bool operator==(Reference<MATLABString> const& lhs, Reference<MATLABString> const& rhs)
template<typename T> bool operator==(Reference<T> const& lhs, T const& rhs)
template<typename T> bool operator==(T const& lhs, Reference<T> const& rhs)
template<typename T> bool operator==(Reference<T> const& lhs, Reference<T> const& rhs)
```

### 参数

| Type | Description |
| :--- | :--- |
| `Reference<MATLABString> const&` lhs, `std::string const&` rhs | 要比较的值。 |
| `std::string const&` lhs, `Reference<MATLABString> const&` rhs | 要比较的值。 |
| `Reference<MATLABString> const&` lhs, `String const&` rhs | 要比较的值。 |
| `String const&` lhs, `Reference<MATLABString> const&` rhs | 要比较的值。 |
| `Reference<MATLABString> const&` lhs, `MATLABString const&` rhs | 要比较的值。 |
| `MATLABString const&` lhs, `Reference<MATLABString> const&` rhs | 要比较的值。 |
| `Reference<MATLABString> const&` lhs, `Reference<MATLABString> const&` rhs | 要比较的值。 |
| `Reference<T> const&` lhs, `T const&` rhs | 要比较的值。 |
| `T const&` lhs, `Reference<T> const&` rhs | 要比较的值。 |
| `Reference<T> const&` lhs, `Reference<T> const&` rhs | 要比较的值。 |

### 返回

如果值相等则返回 `true`。

### 抛出

`matlab::data::TypeMismatchException`

## 版本历史

引入于 R2017b

## 参见

# matlab::data::RowMajor

用于按行优先（row-major）顺序创建迭代器的 C++ 类。

## 说明

使用 `RowMajor` 类确定数组的布局。

## 类细节

- **命名空间**：`matlab::data`
- **包含**：`RowMajor.hpp`

## 迭代器

- [起始迭代器](#起始迭代器)
- [结束迭代器](#结束迭代器)

### 起始迭代器

```cpp
template <typename T>
static RowMajorIterator<T> begin(Array& arr)

template <typename T>
static RowMajorIterator<T> begin(TypedArray<T>& arr)

template <typename T>
static RowMajorIterator<T> begin(Reference<Array>& ref)

template <typename T>
static RowMajorIterator<T> begin(TypedArrayRef<T>& ref)

template <typename T>
static RowMajorIterator<T> begin(const Array& arr)

template <typename T>
static RowMajorIterator<T> begin(const TypedArray<T>& arr)

template <typename T>
static RowMajorIterator<T> begin(const Reference<Array>& ref)

template <typename T>
static RowMajorIterator<T> begin(const TypedArrayRef<T>& ref)
```

#### 说明

指向输入数组起始位置的 `RowMajorIterator`。为了读取数据时获得最佳性能，请使用返回 `RowMajorIterator<T>` 的函数。

#### 参数

| Type | Description |
| :--- | :--- |
| `Array&` arr | 创建迭代器，指定为 const 或非 const。 |
| `TypedArray<T>&` arr | 创建迭代器，指定为 const 或非 const。 |
| `Reference<Array>&` ref | 创建迭代器，指定为 const 或非 const。 |
| `TypedArrayRef<T>&` ref | 创建迭代器，指定为 const 或非 const。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `RowMajorIterator<T>` | 指向数组起始位置的非 const 迭代器。 |
| `RowMajorIterator<T> const` | 指向数组起始位置的 const 迭代器。 |

#### 抛出

`matlab::data::TypeMismatchException` 数组元素不匹配 `<T>`。

### 结束迭代器

```cpp
template <typename T>
static RowMajorIterator<T> end(Array& arr)

template <typename T>
static RowMajorIterator<T> end(TypedArray<T>& arr)

template <typename T>
static RowMajorIterator<T> end(Reference<Array>& ref)

template <typename T>
static RowMajorIterator<T> end(TypedArrayRef<T>& ref)

template <typename T>
static RowMajorIterator<T> end(const Array& arr)

template <typename T>
static RowMajorIterator<T> end(const TypedArray<T>& arr)

template <typename T>
static RowMajorIterator<T> end(const Reference<Array>& ref)

template <typename T>
static RowMajorIterator<T> end(const TypedArrayRef<T>& ref)

template <typename T>
static RowMajorIterator<T> cend(const TypedArrayRef<T>& ref)
```

#### 描述

创建一个指向输入数组末尾的行优先迭代器（`RowMajorIterator`）。

#### 参数

| Type | Description |
| :--- | :--- |
| `Array&` arr | 用于创建迭代器的数组，指定为 const 或非 const。 |
| `TypedArray<T>&` arr | 用于创建迭代器的数组。 |
| `Reference<Array>&` ref | 用于创建迭代器的数组的引用，指定为 const 或非 const。 |
| `TypedArrayRef<T>&` ref | 用于创建迭代器的数组的引用，指定为 const 或非 const。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `RowMajorIterator<T>` | 指向数组末尾的非 const 迭代器。 |
| `RowMajorIterator<T> const` | 指向数组末尾的 const 迭代器。 |

#### 异常

`matlab::data::TypeMismatchException` 数组元素与 `<T>` 不匹配。

## 成员函数

- [readOnlyElements](#readonlyelements)
- [writableElements](#writableelements)

### readOnlyElements

```cpp
template <typename T>
static RowMajorIterator<T> const readOnlyElements(const Array& arr)

template <typename T>
static RowMajorIterator<T> const readOnlyElements(const TypedArray<T>& arr)

template <typename T>
static RowMajorIterator<T> const readOnlyElements(const Reference<Array>& ref)

template <typename T>
static RowMajorIterator<T> const readOnlyElements(const TypedArrayRef<T>& ref)
```

#### 描述

创建一个包含迭代器的范围（`Range`）。在从数组读取数据时，使用它可获得最佳性能。

#### 参数

| Type | Description |
| :--- | :--- |
| `const Array&` arr | 用于创建迭代器的输入数组。 |
| `const TypedArray<T>&` arr | 用于创建迭代器的输入数组。 |
| `const Reference<Array>&` ref | 用于创建迭代器的输入数组的引用。 |
| `const TypedArrayRef<T>&` ref | 用于创建迭代器的输入数组的引用。 |

#### 返回

| Type | Description |
| :--- | :--- |
| `Range<RowMajorIterator<T const>>` | 包含数组开头和末尾的行优先迭代器的范围。 |

#### 异常

`matlab::data::TypeMismatchException` 数组元素与 `<T>` 不匹配。

### writableElements

```cpp
template <typename T>
static Range<RowMajorIterator<T>> writableElements(Array& arr)
```



# `writableElements`

```cpp
template <typename T>
static Range<RowMajorIterator<T>> writableElements(TypedArray<T>& ref)

template <typename T>
static Range<RowMajorIterator<T>> writableElements(Reference<T>& ref)

template <typename T>
static Range<RowMajorIterator<T>> writableElements(TypedArray<T>& ref)
```

## 描述

创建一个包含非 const 迭代器的范围。为了在从数组读取数据时获得更好的性能，请使用 `readOnlyElements`，它返回 `RowMajorIterator<T> const`。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `Array& arr` | 用于创建迭代器的数组。 |
| `TypedArray<T>& arr` | 用于创建迭代器的数组。 |
| `Reference<Array>& ref` | 用于创建迭代器的数组引用。 |
| `TypedArrayRef<T>& ref` | 用于创建迭代器的引用。 |

## 返回

| 类型 | 说明 |
| :--- | :--- |
| `Range<RowMajorIterator<T>>` | 包含指向数组开头和末尾的非 const 行为优先迭代器的范围。 |

## 异常

`matlab::data::TypeMismatch` 数组元素与 `<T>` 不匹配。

## 版本历史

引入于 R2022a

## 另见

`matlab::data::RowMajorIterator<T>` | `matlab::data::Range<ItType, ElemType>` | `matlab::data::Array` | `matlab::data::TypedArray<T>` | `matlab::data::TypedIterator<T>` | `matlab::data::Reference<T>` | `matlab::data::Reference<TypedArray<T>>`

---

# `matlab::data::RowMajorIterator<T>`

用于提供行优先随机访问迭代器的模板 C++ 类。

## 描述

`RowMajorIterator` 按照行优先顺序遍历数组中的元素。更多信息，请参阅“MATLAB Data API 随机访问迭代器”。

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含文件 | `RowMajorIterator.hpp` |

## 模板参数

| 参数 | 说明 |
| :--- | :--- |
| `T` | 所引元素的类型。 |

## 模板实例化

```cpp
double
float
int8_t
uint8_t
int16_t
uint16_t
int32_t
uint32_t
int64_t
uint64_t
char16_t
bool
std::complex<double>
std::complex<float>
std::complex<int8_t>
std::complex<uint8_t>
std::complex<int16_t>
std::complex<uint16_t>
std::complex<int32_t>
std::complex<uint32_t>
std::complex<int64_t>
std::complex<uint64_t>
```

```cpp
matlab::data::Array
matlab::data::Struct
matlab::data::Enumeration
matlab::data::MATLABString
```

## 构造函数

- [拷贝构造函数](#拷贝构造函数)
- [拷贝赋值运算符](#拷贝赋值运算符)
- [移动构造函数](#移动构造函数)
- [移动赋值运算符](#移动赋值运算符)

### 拷贝构造函数

```cpp
RowMajorIterator(const RowMajorIterator<T>& rhs)
```

#### 描述

创建 `RowMajorIterator` 的拷贝。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `const RowMajorIterator<T>& rhs` | 要拷贝的值。 |

#### 异常

无

### 拷贝赋值运算符

```cpp
RowMajorIterator& operator=(const RowMajorIterator<T>& rhs)
```

#### 描述

将一个值赋值给 `RowMajorIterator`。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `const RowMajorIterator<T>& rhs` | 要赋值的值。 |

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `RowMajorIterator&` | 更新后的实例。 |

#### 异常

无

### 移动构造函数

```cpp
RowMajorIterator(RowMajorIterator<T>&& rhs)
```

#### 描述

将 `RowMajorIterator` 的内容移动到新实例中。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `RowMajorIterator<T>&& rhs` | 要移动的值。 |

#### 异常

无

### 移动赋值运算符

```cpp
RowMajorIterator& operator=(RowMajorIterator<T>&& rhs)
```

#### 描述

将输入赋值给此 `RowMajorIterator`。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `RowMajorIterator<T>&& rhs` | 要移动的值。 |

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `RowMajorIterator&` | 更新后的实例。 |

#### 异常

无

## 版本历史

引入于 R2022a

## 另见

`matlab::data::RowMajorIterator<T>` | `matlab::data::TypedIterator<T>` | `matlab::data::Array<T>`

---

# `matlab::data::SparseArray<T>`

用于访问稀疏数据的模板 C++ 类。

## 描述

使用 `SparseArray` 来处理稀疏数组。要创建 `SparseArray`，请调用 `Array` 类中的 `createSparseArray`。

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 基类 | `matlab::data::Array` |
| 包含文件 | `SparseArray.hpp` |

## 模板参数

| 参数 | 说明 |
| :--- | :--- |
| `T` | 所引元素的类型，指定为：`bool`、`double`、`std::complex<double>`。 |

## 构造函数

- [拷贝构造函数](#拷贝构造函数-1)
- [拷贝赋值运算符](#拷贝赋值运算符-1)
- [移动构造函数](#移动构造函数-1)
- [移动赋值运算符](#移动赋值运算符-1)

### 拷贝构造函数

```cpp
SparseArray(const SparseArray<T>& rhs)
SparseArray(const Array& rhs)
```

#### 描述

创建 `SparseArray` 的共享数据拷贝。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `const SparseArray<T>& rhs` | 要拷贝的值。 |
| `const Array& rhs` | 指定为 `ArrayType::SPARSE_LOGICAL`、`double` 或 `std::complex<double>`。 |

#### 异常

无

### 拷贝赋值运算符

```cpp
SparseArray& operator=(const SparseArray<T>& rhs)
SparseArray& operator=(const Array& rhs)
```

#### 描述

将共享数据拷贝赋值给 `SparseArray`。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `const SparseArray<T>& rhs` | 要拷贝的值。 |
| `const Array& rhs` | 指定为 `ArrayType::SPARSE_LOGICAL`、`double` 或 `std::complex<double>`。 |

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `SparseArray&` | 更新后的实例。 |

#### 异常

无

### 移动构造函数

```cpp
SparseArray(SparseArray<T>&& rhs)
SparseArray(Array&& rhs)
```

#### 描述

将 `SparseArray` 的内容移动到新实例中。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `SparseArray<T>&& rhs` | 要移动的值。 |
| `Array&& rhs` | 指定为 `ArrayType::SPARSE_LOGICAL`、`double` 或 `std::complex<double>`。 |

#### 异常

无

### 移动赋值运算符

```cpp
SparseArray& operator=(SparseArray<T>&& rhs)
SparseArray& operator=(Array&& rhs)
```

#### 描述

将输入赋值给此 `SparseArray`。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `SparseArray<T>&& rhs` | 要移动的值。 |
| `Array&& rhs` | 指定为 `ArrayType::SPARSE_LOGICAL`、`double` 或 `std::complex<double>`。 |

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `SparseArray&` | 更新后的实例。 |

#### 异常

无

## 版本历史

引入于 R2022a

## 另见

`matlab::data::SparseArray<T>` | `matlab::data::TypedIterator<T>` | `matlab::data::Array<T>`

## 迭代器

- [开始迭代器](#开始迭代器)
- [结束迭代器](#结束迭代器)

### 开始迭代器

```cpp
iterator begin()
const_iterator begin() const
const_iterator cbegin() const
```

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `iterator` | 指向数组开头的迭代器，指定为 `TypedIterator<T>`。 |
| `const_iterator` | 迭代器，指定为 `TypedIterator<typename std::add_const<T>::type>`。 |

#### 异常

无

### 结束迭代器

```cpp
iterator end()
const_iterator end() const
const_iterator cend() const
```

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `iterator` | 指向数组结束的迭代器，指定为 `TypedIterator<T>`。 |
| `const_iterator` | 迭代器，指定为 `TypedIterator<typename std::add_const<T>::type>`。 |

#### 异常

无

## 成员函数

- [getNumberOfNonZeroElements](#getnumberofnonzeroelements)
- [getIndex](#getindex)

### `getNumberOfNonZeroElements`

```cpp
size_t getNumberOfNonZeroElements() const
```

#### 描述

返回数组中非零元素的数量。

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `size_t` | 数组中非零元素的数量。 |

#### 异常

无

### `getIndex`

```cpp
SparseIndex getIndex(const TypedIterator<T> const it)
```

#### 描述

返回迭代器指向的非零元素的行列坐标。

#### 参数

| 参数 | 说明 |
| :--- | :--- |
| `const TypedIterator<T> const& it` | 指向稀疏矩阵中当前条目的迭代器。 |

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `SparseIndex` | 迭代器指向的非零元素的行列坐标。`SparseIndex` 定义为 `std::pair<size_t, size_t>`。 |

#### 异常

无

## 版本历史

引入于 R2017b

## 另见

`Array` | `createSparseArray`

---

# `matlab::data::Reference<SparseArray<T>>`

用于获取 `SparseArray` 引用的 C++ 类。

## 描述

使用 `Reference<SparseArray>` 类来获取容器对象（如 MATLAB 结构体或单元数组）中 `SparseArray` 元素的引用。

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含文件 | `SparseArrayRef.hpp` |

## 模板参数

`SparseArray` 中元素的类型，指定为 `bool`、`double` 或 `std::complex<double>`。

## 迭代器

- [开始迭代器](#开始迭代器-1)
- [结束迭代器](#结束迭代器-1)

### 开始迭代器

```cpp
iterator begin()
const_iterator begin() const
const_iterator cbegin() const
```

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `iterator` | 指向数组开头的迭代器，指定为 `TypedIterator<T>`。 |
| `const_iterator` | 迭代器，指定为 `TypedIterator<typename std::add_const<T>::type>`。 |

#### 异常

无

### 结束迭代器

```cpp
iterator end()
const_iterator end() const
const_iterator cend() const
```

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `iterator` | 指向数组结束的迭代器，指定为 `TypedIterator<T>`。 |
| `const_iterator` | 迭代器，指定为 `TypedIterator<typename std::add_const<T>::type>`。 |

#### 异常

无

## 成员函数

### `getNumberOfNonZeroElements`

```cpp
size_t getNumberOfNonZeroElements() const
```

#### 描述

返回数组中非零元素的数量。由于稀疏数组只存储非零元素，此方法返回数组的实际大小。它与指定完整数组大小的维度不同。

#### 返回

| 类型 | 说明 |
| :--- | :--- |
| `size_t` | 数组中非零元素的数量。 |

#### 异常

无

## 版本历史

引入于 R2017b

## 另见

---

# `matlab::data::String`

表示为 `std::basic_string<char16_t>` 的字符串类型。

## 描述

`String` 类定义了 `StringArray` 的元素类型。`String` 定义为：

```cpp
using String = std::basic_string<char16_t>;
```

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含文件 | `String.hpp` |

## 版本历史

引入于 R2017b

## 另见

`matlab::data::MATLABString`

---

# `matlab::data::StringArray`

用于访问 MATLAB 字符串数组的 C++ 类。

## 描述

使用 `StringArray` 对象访问 MATLAB 字符串数组。要创建 `StringArray`，请调用 `ArrayFactory` 类中带有 `MATLABString` 模板的 `createArray`。

`StringArray` 定义为：

```cpp
using StringArray = TypedArray<MATLABString>;
```

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含文件 | `TypedArray.hpp` |

## 版本历史

引入于 R2017b

## 另见

`MATLABString`

---

# `matlab::data::StructArray`

用于访问 MATLAB 结构数组的 C++ 类。

## 描述

使用 `StructArray` 对象处理 MATLAB 结构数组。要访问数组中的单个字段，请使用字段名。要创建 `StructArray` 对象，请调用 `ArrayFactory` 中的 `createStructArray`。

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 基类 | `TypedArray<Struct>` |
| 包含文件 | `StructArray.hpp` |

## 构造函数

- [拷贝构造函数](#拷贝构造函数-2)
- [拷贝赋值运算符](#拷贝赋值运算符-2)
- [移动构造函数](#移动构造函数-2)
- [移动赋值运算符](#移动赋值运算符-2)

### 拷贝构造函数

```cpp
StructArray(const StructArray& rhs)
StructArray(const Array& rhs)
```



# 描述

创建 `StructArray` 对象的共享拷贝。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `const StructArray& rhs` | 要拷贝的值。 |
| `const Array& rhs` | 指定为 `ArrayType::STRUCT` 对象。 |

## 异常

`matlab::data::InvalidArrayTypeException`：输入类型不是 `ArrayType::STRUCT`。

# 拷贝赋值运算符

```cpp
StructArray& operator=(const StructArray& rhs)
StructArray& operator=(const Array& rhs)
```

## API 参考

## 描述

将共享拷贝赋值给 `StructArray` 对象。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `const StructArray& rhs` | 要拷贝的值。 |
| `const Array& rhs` | 指定为 `ArrayType::STRUCT` 对象。 |

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `StructArray&` | 更新后的实例。 |

## 异常

`matlab::data::InvalidArrayTypeException`：输入类型不是 `ArrayType::STRUCT`。

# 移动构造函数

```cpp
StructArray(StructArray&& rhs)
StructArray(Array&& rhs)
```

## 描述

将 `StructArray` 对象的内容移动到新实例。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `StructArray&& rhs` | 要移动的值。 |
| `Array&& rhs` | 指定为 `ArrayType::STRUCT` 对象。 |

## 异常

`matlab::data::InvalidArrayTypeException`：输入类型不是 `ArrayType::STRUCT`。

# 移动赋值运算符

```cpp
StructArray& operator=(StructArray&& rhs)
```

## 描述

将输入赋值给此 `StructArray` 对象。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `StructArray&& rhs` | 要移动的值。 |

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `StructArray&` | 更新后的实例。 |

## 异常

无

# 析构函数

```cpp
~StructArray()
```

## 描述

释放 `StructArray` 对象的内存。

# 成员函数

- [getFieldNames](#getfieldnames)
- [getNumberOfFields](#getnumberoffields)

## getFieldNames

```cpp
Range<ForwardIterator, MatlabIdentifier> const getFieldNames() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `Range<ForwardIterator, MatlabIdentifier> const` | 允许访问 `StructArray` 对象中所有字段的起始和结束迭代器。 |

## 异常

无

## getNumberOfFields

```cpp
size_t getNumberOfFields() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `size_t` | 字段数量。 |

## 异常

无

# 示例

## CreateStructArray

假设你有以下 MATLAB 结构体。

```cpp
#include "MatlabDataArray.hpp"

int main() {
  using namespace matlab::data;

  ArrayFactory factory;

  StructArray S = factory.createStructArray({ 1, 2 }, { "loc", "data" });

  S(0)["loc"] = factory.createCharArray('east');
  S(0)["data"] = factory.createArray<int8_t>({ 1, 3 }, { 1, 2, 3 });
  S(1)["loc"] = factory.createCharArray('east');
  S(1)["data"] = factory.createArray<double>({ 1, 5 }, { 4., 5., 6., 7., 8. });

  Reference<Array> val = S(0)["data"];

  return 0;
}
```

# 版本历史

引入于 R2017b

# 另见

`Range` | `createStructArray` | `MATLABFieldIdentifier` | `Struct`

# 主题

“创建结构体数组并发送到 MATLAB”

# matlab::data::Reference<StructArray>

用于获取 `StructArray` 引用的 C++ 类

## 描述

`StructArrayExt` 类扩展了用于 `StructArray` 引用的 API。

## 类细节

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 基类 | `Reference<Array>` |
| 包含文件 | `TypedArrayRef.hpp` |

## 成员函数

- [getFieldNames](#getfieldnames-1)
- [getNumberOfFields](#getnumberoffields-1)

# matlab::data::Struct

MATLAB struct 的元素类型

## 描述

`Struct` 是 `StructArray` 对象的元素类型。

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含文件 | `Struct.hpp` |

## 迭代器

- [开始迭代器](#开始迭代器)
- [结束迭代器](#结束迭代器)

## 开始迭代器

```cpp
const_iterator begin() const
const_iterator cbegin() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `const_iterator` | 指向数组起始的迭代器，指定类型为 `TypedIterator<typename std::add_const<T>::type>` |

## 抛出

None

## 结束迭代器

```cpp
const_iterator end() const
const_iterator cend() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `const_iterator` | 指向数组结束的迭代器，指定类型为 `TypedIterator<typename std::add_const<T>::type>` |

## 抛出

None

## 索引运算符

### operator[]

```cpp
Array operator[](std::string idx) const
```

## 描述

允许在 `StructArray` 对象上使用 `[]` 索引。索引基于 0 的。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `std::string idx` | 字段名。 |

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `Array` | 在指定字段处找到的 `Array` 的共享拷贝。 |

## 抛出

| 异常 | 说明 |
| :--- | :--- |
| `matlab::data::InvalidFieldNameException` | 此 `StructArray` 中不存在该字段。 |

## 版本历史

引入于 R2017b

# 另见

`StructArray` | `createStructArray`（第 1-22 页）

# matlab::data::Reference<Struct>

用于获取 `StructArray` 元素引用的 C++ 类

## 描述

使用 `Reference<Struct>` 类访问 `StructArray` 的元素。

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 包含文件 | `StructRef.hpp` |

## 索引运算符

### operator[]

```cpp
Reference<Array> operator[](std::string idx)
Array operator[](std::string idx) const
```

## 描述

通过字段名对 `Struct` 进行索引。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `std::string idx` | 字段名。 |

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `Reference<Array>` | 指向指定字段处找到的 `Array` 的引用。 |
| `Array` | 在指定字段处找到的 `Array` 的共享拷贝。 |

## 抛出

`matlab::data::InvalidFieldNameException`：struct 中不存在该字段。

## 迭代器

- [开始迭代器](#开始迭代器-1)
- [结束迭代器](#结束迭代器-1)

## 开始迭代器

```cpp
iterator begin()
const_iterator begin() const
const_iterator cbegin() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `iterator` | 指向字段列表起始位置的迭代器，指定类型为 `TypedIterator<T>`。 |
| `const_iterator` | 指定类型为 `TypedIterator<typename std::add_const<T>::type>`。 |

## 抛出

None

## 结束迭代器

```cpp
iterator end()
const_iterator end() const
const_iterator cend() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `iterator` | 指向字段列表结束的迭代器，指定类型为 `TypedIterator<T>`。 |
| `const_iterator` | 指定类型为 `TypedIterator<typename std::add_const<T>::type>`。 |

## 抛出

None

## 转换

```cpp
operator Struct() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `Struct` | `Struct` 的共享拷贝。 |

## 抛出

None

## 版本历史

引入于 R2017b

# 另见

# matlab::data::TypedArray<T>

访问数组数据的模板 C++ 类

## 描述

`TypedArray` 类提供了类型安全的 API 来处理所有 MATLAB 数组类型（稀疏数组除外）。要创建 `TypedArray`，请调用 `ArrayFactory` 类中第 1-14 页列出的模板实例化。

该类定义了以下迭代器：

```cpp
using iterator = TypedIterator<T>;
using const_iterator = TypedIterator<T const>;
```

## 类详情

| 项目 | 说明 |
| :--- | :--- |
| 命名空间 | `matlab::data` |
| 基类 | `data::Array` |
| 包含文件 | `TypedArray.hpp` |

## 模板参数

| 参数 | 说明 |
| :--- | :--- |
| `T` | 所引用的元素类型。 |

# 模板实例化

```cpp
double
float
int8_t
uint8_t
int16_t
uint16_t
int32_t
uint32_t
int64_t
uint64_t
char16_t
bool
std::complex<double>
std::complex<float>
std::complex<int8_t>
std::complex<uint8_t>
std::complex<int16_t>
std::complex<uint16_t>
std::complex<int32_t>
std::complex<uint32_t>
std::complex<int6_t>
matlab::data::Array
matlab::data::Struct
matlab::data::Enumeration
matlab::data::MATLABString
```

## 构造函数

- [拷贝构造函数](#拷贝构造函数)
- [拷贝赋值运算符](#拷贝赋值运算符)
- [移动构造函数](#移动构造函数)
- [移动赋值运算符](#移动赋值运算符)

## 拷贝构造函数

```cpp
TypedArray(const TypedArray<T>& rhs)
```

## 描述

创建输入的共享拷贝。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `const TypedArray<T>& rhs` | 要拷贝的值。 |

## 拷贝赋值运算符

```cpp
TypedArray& operator=(const TypedArray<T>& rhs)
```

## 描述

将输入的共享拷贝赋值给此实例。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `const TypedArray<T>& rhs` | 要拷贝的值。 |

## 移动构造函数

```cpp
TypedArray(TypedArray<T>&& rhs)
```

## 描述

将输入的内容移动到此实例。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `TypedArray<T>&& rhs` | 要移动的值。 |

## 移动赋值运算符

```cpp
TypedArray& operator=(TypedArray<T>&& rhs)
```

## 描述

将输入的内容移动到此实例。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `TypedArray<T>&& rhs` | 要移动的值。 |

## 析构函数

```cpp
virtual ~TypedArray()
```

## 迭代器

- [开始迭代器](#开始迭代器-2)
- [结束迭代器](#结束迭代器-2)

## 开始迭代器

```cpp
iterator begin()
const_iterator begin() const
const_iterator cbegin() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `iterator` | 指向数组起始的迭代器，指定类型为 `TypedIterator<T>`。 |
| `const_iterator` | 指定类型为 `TypedIterator<typename std::add_const<T>::type>`。 |

## 抛出

None

## 结束迭代器

```cpp
iterator end()
const_iterator end() const
const_iterator cend() const
```

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `iterator` | 指向数组结束的迭代器，指定类型为 `TypedIterator<T>`。 |
| `const_iterator` | 指定类型为 `TypedIterator<typename std::add_const<T>::type>`。 |

## 抛出

None

## 索引运算符

### operator[]

```cpp
Array operator[](size_t idx) const
```

## 描述

允许在 `TypedArray` 上使用 `[]` 索引。索引基于 0 的。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `size_t idx` | 第一个数组索引。 |

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `ArrayElementTypedRef<T, is_const<T>::value>` | 包含索引元素的临时对象。如果 `T` 是 `const`，则返回值允许检索数组但不允许修改。否则，元素可以被修改或检索。 |
| `ArrayElementTypedRef<T, true>` | 包含指定索引的临时对象。返回值允许检索数组元素但不允许修改。 |

## 抛出

None

## 成员函数

### release

```cpp
buffer_ptr<T> release()
```

## 描述

从 `Array` 中释放底层缓冲区。如果 `Array` 是共享的，则会制作缓冲区拷贝；否则，不拷贝。缓冲区释放后，数组不包含任何元素。

## 返回

| 返回值 | 说明 |
| :--- | :--- |
| `buffer_ptr<T>` | 包含数据指针的 `unique_ptr`。 |

## 抛出

| 异常 | 说明 |
| :--- | :--- |
| `matlab::data::InvalidArrayTypeException` | `TypedArray` 不释放缓冲区。 |

# 示例

## 给数组元素赋值

创建一个与 MATLAB 数组 `[1 2; 3 4]` 对应的数组，然后将数组的每个元素替换为单个值。

```cpp
#include "MatlabDataArray.hpp"

int main() {
    matlab::data::ArrayFactory factory;

    // 创建与 MATLAB 数组 [1 2; 3 4] 对应的数组。
    matlab::data::TypedArray<double> D = factory.createArray<double>({ 2, 2 }, { 1, 3, 2, 4 });

    // 修改值。
    for (auto elem : D) {
        elem = 5.5;
    }
    return 0;
}
```

## 版本历史

引入于 R2017b

# 另见

`Array` | `ArrayType`

# 主题

“将 MATLAB 计算结果引入 C++”

# matlab::data::Reference<TypedArray<T>>

用于获取 `TypedArray` 引用的模板化 C++ 类

## 描述

`Reference<TypedArray<T>>` 类扩展了用于 `Array` 引用的可用 API。它派生自 `Reference<Array>` 类，并提供了迭代器和类型安全的索引。`Reference<TypedArray<T>>` 不是线程安全的——不要在线程之间传递 `TypedArray` 对象的引用。

`TypedArrayRef` 在 `TypedArrayRef.hpp` 中定义为：

```cpp
template <typename T>
```



using `TypedArrayRef` = `Reference<TypedArray<T>>`;

## 类详情

- 命名空间：`matlab::data`
- 基类：`Reference<Array>`
- 包含文件：`TypedArrayRef.hpp`

## 构造函数

`Reference(const Reference<Array>& rhs)`

## 描述

从 `Reference<Array>` 对象创建 `Reference<TypedArray<T>>` 对象。

## 参数

`const Reference<Array>& rhs` 要拷贝的值。

## 抛出

`matlab::data::TypeMismatch` Array 中的元素与 `<T>` 不匹配。

## 迭代器

- `begin()`
- `end()`

## begin()

```cpp
iterator begin()
const_iterator begin() const
const_iterator cbegin() const
```

## 返回

| 类型 | 说明 |
| --- | --- |
| `iterator` | 指向数组开头的迭代器，指定为 `TypedIterator<T>`。 |
| `const_iterator` | 迭代器，指定为 `TypedIterator<typename std::add_const<T>::type>`。 |

## 抛出

无

## end()

```cpp
iterator end()
const_iterator end() const
const_iterator rend() const
```

## 返回

| 类型 | 说明 |
| --- | --- |
| `iterator` | 指向数组结尾的迭代器，指定为 `TypedIterator<T>`。 |
| `const_iterator` | 迭代器，指定为 `TypedIterator<typename std::add_const<T>::type>`。 |

## 抛出

无

## 索引运算符

```cpp
ArrayElementTypedRef<arr_elem_type, std::is_const<T>::value> operator[](size_t idx)
ArrayElementTypedRef<arr_elem_type, true> operator()(size_t idx) const
```

## 描述

允许对 Array 引用使用 `[]` 索引。索引从 0 开始。

## 参数

`size_t idx` 第一个数组索引。

## 返回

`ArrayElementTypedRef<arr_em_type>` 包含指定索引的临时对象。如果类型 `T` 是 `const`，则返回值允许检索数组元素，但不允许进行修改。否则，可以修改或检索元素。

`ArrayElementTypedRef<arr_em_type, true>` 包含指定索引的临时对象。返回值允许检索数组元素，但不允许进行修改。

## 抛出

| 异常 | 说明 |
| --- | --- |
| `matlab::data::InvalidFieldName` | 结构体的字段名无效。 |
| `matlabException` |  |

## 其他运算符

```cpp
Reference<TypedArray<T>>& operator=(TypedArray<T> rhs)
```

## 描述

将 TypedArray 分配给被引用 Array 的元素。被索引的 Array 必须是非 `const` 的。

## 参数

| 类型 | 说明 |
| --- | --- |
| `TypedArray<T> rhs` | 要赋值的值。 |

## 返回

| 类型 | 说明 |
| --- | --- |
| `Reference<TypedArray<T>>&` | 更新后的实例。 |

## 抛出

无

## 版本历史

引入于 R2017b

## 参见另

- `matlab::data::TypedIterator<T>`

---

# matlab::data::TypedIterator<T>

用于提供按内存顺序进行随机访问迭代器的模板化 C++ 类

## 描述

`TypedIterator` 按照计算机内存中的元素顺序进行迭代，这种顺序可能是列主序或行主序。要确定数组的内存布局，请调用 `getMemoryLayout`。更多信息请参阅“MATLAB 数据 API 随机访问迭代器”。

## 类详情

- 命名空间：`matlab::data`
- 包含文件：`TypedIterator.hpp`

## 模板参数

| 参数 | 说明 |
| --- | --- |
| `T` | 所引用元素的类型。 |

## 模板实例化

```cpp
double
float
int8_t
uint8_t
int16_t
uint16_t
int32_t
uint32_t
int64_t
uint64_t
char16_t
bool
std::complex<double>
std::complex<float>
std::complex<int8_t>
std::complex<uint8_t>
std::complex<int16_t>
std::complex<uint16_t>
std::complex<int32_t>
std::complex<uint32_t>
std::complex<int64_t>
std::complex<uint64_t>
```

```cpp
matlab::data::Array
matlab::data::Struct
matlab::data::Enumeration
matlab::data::MATLABString
```

## 构造函数

- 拷贝构造函数
- 拷贝赋值运算符
- 移动构造函数
- 移动赋值运算符

## 拷贝构造函数

`TypedIterator(const TypedIterator<T>& rhs)`

## 描述

创建 `TypedIterator` 对象的拷贝。

## 参数

`const TypedIterator<T>& rhs`

## 拷贝赋值运算符

`TypedIterator& operator=(const TypedIterator<T>& rhs)`

## 描述

赋值一个 `TypedIterator`。

## 参数

`const TypedIterator<T>& rhs` 要拷贝的值。

## 返回

`TypedIterator&` 更新后的实例。

## 移动构造函数

`TypedIterator(TypedIterator<T>&& rhs)`

## 描述

移动一个 `TypedIterator` 对象。

## 参数

`TypedIterator<T>&& rhs` 要移动的值。

## 移动赋值运算符

`TypedIterator& operator=(TypedIterator<T>&& rhs)`

## 描述

移动一个 `TypedIterator`。

## 参数

`TypedIterator<T>&& rhs` 要移动的值。

## 返回

`TypedIterator&` 更新后的实例。

## 版本历史

引入于 R2017b

## 参见另

- `matlab::data::TypedIterator<T>`

---

# matlab::engine::MATLABEngine

## getEngine

```cpp
std::shared_ptr<matlab::engine::MATLABEngine> getEngine()
```

## 返回

`std::shared_ptr<matlab::engine::MATLABEngine>` 指向 `matlab::engine::MATLABEngine` 对象的指针

## 示例

调用 MATLAB clear 函数。

```cpp
std::shared_ptr<MATLABEngine> matlabPtr = getEngine();
matlabPtr->eval(matlab::engine::convertUTF8StringToUTF16("clear"));
```

---

# mexLock

```cpp
void mexLock()
```

防止 MEX 文件从内存中被清除。不要从用户线程调用 `mexLock` 或 `mexUnlock`。

## 示例

锁定 MEX 文件。

```cpp
mexLock();
```

---

# mexUnlock

解锁 MEX 文件并允许从内存中清除该文件。不要从用户线程调用 `mexLock` 或 `mexUnlock`。

```cpp
void mexUnlock()
```

## 示例

解锁 MEX 文件。

```cpp
mexUnlock();
```

---

# getFunctionName

```cpp
std::u6string getFunctionName() const
```

返回 MEX 函数的名称，即源文件的名称。

## 示例

获取当前执行的 MEX 函数的文件名。

```cpp
std::u6string fileName = getFunctionName();
```

## 版本历史

在 R2018a 中引入

## 另请

- `matlab::mex::ArgumentList`

## 主题

- "C++ MEX API"
- "C++ MEX 函数的结构"

---

# matlab::mex::ArgumentList

用于 C++ MEX 函数输入和输出的容器

## 描述

C MEX 函数将包含在 `matlab::mex::ArgumentList` 对象中的 `matlab::data::Array` 对象传递输入和输出。`MexFunction::operator()` 接受两个参数，一个用于输入，一个用于输出，定义为 `matlab::mex::ArgumentList`。

`ArgumentList` 是一个包装器，允许对持有输入输出数据的底层集合进行迭代。

## 类细节

- 命名空间：`matlab::mex`
- 包含：`mex.hpp`

## 成员函数

- `operator[]`
- `begin()`
- `end()`
- `size()`
- `empty()`

## operator[]

```cpp
matlab::data::Array operator[](size_t idx)
```

允许对 `ArgumentList` 中的元素进行 `[]` 索引。

## 参数

| 参数 | 说明 |
| --- | --- |
| `size_t idx` | 输入数组中元素的索引，这些元素是 MEX 函数的输入参数 |

## 返回

| 类型 | 说明 |
| --- | --- |
| `matlab::data::Array` | 指向 `ArgumentList` 数组中第一个元素的迭代器 |

## 示例

从 MATLAB 调用 MEX 函数，并将数组、标量和字符向量作为输入，并获得单个输出：

```cpp
a = myMEXFunction(array, scalar, 'character vector')
```

将第一个输入参数赋值给 `TypedArray`，将第二个输入赋值给 `scalar const double`（假设两者在 MATLAB 中都是 double 类型），第三个输入作为 `matlab::data::CharArray`。

```cpp
void operator()(matlab::mex::ArgumentList outputs, matlab::mex::ArgumentList inputs) {
  matlab::data::TypedArray<double> inArray = inputs[0];
  const double inScalar = inputs[1][0];
  matlab::data::CharArray inChar = inputs[2];
  result = ...
  outputs[0] = result;
}
```

## begin()

### `iterator_type begin()`

返回指向 `ArgumentList` 数组中第一个元素的迭代器。

## 返回

| 类型 | 说明 |
| --- | --- |
| `iterator_type` | 指向 `ArgumentList` 数组中第一个元素的迭代器 |

## 示例

```cpp
void operator()(matlab::mex::ArgumentList outputs, matlab::mex::ArgumentList inputs) {
  std::vector<matlab::data::TypedArray<double>> vectorDoubles(inputs.begin(), inputs.end());
}
```

## end()

### `iterator_type end()`

返回指向 `ArgumentList` 数组中最后一个元素之后的迭代器。

## 返回

| 类型 | 说明 |
| --- | --- |
| `iterator_type` | 指向 `ArgumentList` 数组中最后一个元素之后的迭代器 |

## size()

### `size_t size()`

返回参数列表中的元素数量。用此来检查调用处指定的输入和输出数量。

## 返回

| 类型 | 说明 |
| --- | --- |
| `size_t` | `ArgumentList` 数组的大小 |

## 示例

确定 MEX 函数是带有三个输入参数被调用的。

```cpp
class MexFunction : public matlab::mex::Function {
public:
```



```cpp
void operator()(matlab::mex::ArgumentList outputs, matlab::mex::ArgumentList inputs) {
  if (inputs.size() == 3) {
    // MEX 函数带有三个输入参数被调用
  }
}
```

## empty

### `bool empty()`

返回指示参数列表是否为空的逻辑值。

## 返回

`bool` 如果参数列表为空（`size() == 0`）则返回真

## 示例

确定 MEX 函数是在没有输入参数的情况下被调用的。

```cpp
class MexFunction : public matlab::mex::Function {
public:
  void operator()(matlab::mex::ArgumentList outputs, matlab::mex::ArgumentList inputs) {
    if (inputs.empty()) {
      // MEX 函数在没有输入参数的情况下调用
    }
  }
};
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`matlab::mex::Function`

## 主题

- "C++ MEX API"
- "C++ MEX 函数的结构"

# `matlab::engine::MATLABEngine`

从 C++ 评估 MATLAB 函数

## 描述

`matlab::engine::MATLABEngine` 类用于 C++ 的 MATLAB。该类提供了 C++ 和 MATLAB 之间的接口，用于从程序评估函数。

## 类细节

命名空间：`matlab::engine`
包含：`matlab.hpp`

## 成员函数

- `feval` 位于第 135 页
- `feval` 位于第 138 页
- `eval` 位于第 139 页
- `eval` 位于第 140 页
- `getVariable` 位于第 141 页
- `getVariable` 位于第 142 页
- `getProperty` 位于第 143 页
- `getProperty` 位于第 144 页
- `setProperty` 位于第 145 页
- `setProperty` 位于第 146 页

## feval

```cpp
std::vector<matlab::data::Array> feval(const matlab::engine::MATLABEngine& engine, size_t numReturned, const std::vector<matlab::data::Array> &args, const matlab::data::Array arg, const std::shared_ptr<matlab::engine::StreamBuff> &output = std::(), const std::shared_ptr<matlab::engine::StreamBuff> &error = std::(), RhsArgs... args)
```

```cpp
ResultType feval(const matlab::engine::MATLABEngine& engine, std::string arg)
```

```cpp
std::vector<matlab::data::Array> feval(const matlab::engine::MATLABEngine& engine, const std::string arg, const std::shared_ptr<matlab::engine::StreamBuff> &output, const std::shared_ptr<matlab::engine::StreamBuff> &error = std::(), RhsArgs... args)
```

```cpp
ResultType feval(const matlab::engine::String &function, RhsArgs... args)
```

## 描述

带有输入参数评估 MATLAB 函数。使用 `feval` 从 C++ 传递参数并从 MATLAB 返回结果。

输入和输出可以是 MATLAB Data 定义，也可以是原生 C++ 类型。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `const matlab::engine::String &function` | 要执行的 MATLAB 函数或脚本名称。将名称指定为 `std::u16string`。您也可以将此参数指定为 `std::string` |
| `const size_t numReturned` | 返回的数量 |
| `const std::vector<matlab::data::Array> &args` | 传递给 MATLAB 函数的多个输入参数。向量被转换为 MATLAB 中的列数组 |
| `const matlab::data::Array arg` | 传递给 MATLAB 函数的单个输入参数 |
| `const std::shared_ptr<matlab::engine::StreamBuff> &output = std::()` | 用于存储 MATLAB 函数标准输出的缓冲区 |
| `const std::shared_ptr<matlab::engine::StreamBuff> &error = std::()` | 用于存储 MATLAB 函数错误信息的缓冲区 |
| `RhsArgs... args` | 可变参数 |

用于函数输入的原生 C++ 数据类型。`feval` 接受 C++ 数据类型的标量输入：`bool`、`int8_t`、`int16_t`、`int32_t`、`int64_t`、`uint8_t`、`uint16_t`、`uint32_t`、`uint64_t`、`float`、`double`。

## 返回值

| 类型 | 说明 |
| :--- | :--- |
| `std::vector<matlab::data::Array>` | 从 MATLAB 返回的输出 |
| `matlab::data::Array ResultType` | 从 MATLAB 返回的单个输出。用户指定的类型从 MATLAB 输出。如果返回多个参数，它可以是 `std::tuple` |

## 异常

- `matlab::engine::MATLABNotAvailableException` MATLAB 会话不可用。
- `matlab::engine::MATLABExecutionException` 函数中存在 MATLAB 运行时错误。
- `matlab::engine::TypeConversionException` MATLAB 函数的返回值可能无法转换为指定的类型。
- `matlab::engine::MATLABSyntaxException` MATLAB 函数中存在语法错误。

## 示例

此示例将一个包含数值的 `matlab::data::Array` 传递给 MATLAB 函数。代码执行了以下步骤：

- 从类型为 `double` 的数值向量创建一个维度为 2-3 的 `matlab::data::Array`。
- 启动一个共享的 MATLAB 会话。
- 将数据数组传递给 MATLAB `sqrt` 函数并将结果返回给 C++。

```cpp
#include "MatlabDataArray.hpp"
#include "MatlabEngine.hpp"

namespace matlab::engine;

std::vector<double> cppData = {4, 8, 12, 16, 20, 24};

matlab::data::ArrayFactory factory;

auto inputArray = factory.createArray({ 2, 3 }, cppData.begin(), cppData.end());

// Start MATLAB engine
std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

// Pass data array to MATLAB sqrt function
auto result = matlabPtr->feval(u"sqrt", inputArray);
```

当使用原生 C++ 类型时，输入参数被限制为标量值。例如，此代码返回标量值的平方根。

```cpp
#include "MatlabEngine.hpp"

namespace matlab::engine;

// Start MATLAB engine synchronously
std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

// Call sqrt function
double result = matlabPtr->feval<double>(u"sqrt", double(27));
```

对于返回多个输出的函数，您可以使用 MATLAB 数据 API，或者在使用 C++ 类型时（如 `std::tuple` 所示）：示例，请参阅“使用原生 C++ 类型调用函数”。

## 相关主题

- "从 C++ 调用 MATLAB 函数"
- "用于 C++ 的 MATLAB 数据 API"

# API 参考 异步

```cpp
fevalResult = std::vector<matlab::data::Array> fevalAsync(const matlab::engine::String function,
const size_t nReturned,
const std::vector<matlab::data::Array> &args,
const std::shared_ptr<matlab::engine::StreamBuffer> &output = std::shared_ptr<matlab::engine::StreamBuffer>(),
const std::shared_ptr<matlab::engine::StreamBuffer> &error = std::shared_ptr<matlab::engine::StreamBuffer>());

fevalResult = fevalAsync(const matlab::engine::String function,
const std::vector<matlab::data::Array> &args,
const std::shared_ptr<matlab::engine::StreamBuffer> &output = std::shared_ptr<matlab::engine::StreamBuffer>(),
const std::shared_ptr<matlab::engine::StreamBuffer> &error = std::shared_ptr<matlab::engine::StreamBuffer>());
```

## 描述

异步评估带有输入参数和返回值的 MATLAB 函数。

## 参数

- `const matlab::engine::String &function` - 要评估的 MATLAB 函数或脚本名称。以 `std::u16string` 指定名称。此外，您也可以用 `std::string` 指定此参数。
- `const size_t nReturned` - 返回值的数量。
- `const std::vector<matlab::data::Array> &args` - 以 `std::vector` 形式传递给 MATLAB 函数的多个输入参数。该向量在 MATLAB 中被转换为列数组。
- `const matlab::data::Array arg` - 传递给 MATLAB 函数的单个输入参数。
- `const std::shared_ptr<matlab::engine::StreamBuffer> &output` - 用于存储来自 MATLAB 函数标准输出的流缓冲区。
- `const std::shared_ptr<matlab::engine::StreamBuffer> &error` - 用于存储 MATLAB 函数错误信息的流缓冲区。
- `RhsArgs... args` - 用于输入的原生 C++ 数据类型，`feval` 接受这些数据类型的标量输入：`bool`, `int8_t`, `int16_t`, `int32_t`, `int64_t`, `uint8_t`, `uint16_t`, `uint32_t`, `uint64_t`, `float`, `double`。

## 返回值

| 类型 | 说明 |
| :--- | :--- |
| `FutureResult` | 用于获取调用 MATLAB 函数结果的 `FutureResult` 对象。 |

## 异常

无

## 示例

此示例异步地将标量 `double` 12.7 传递给 MATLAB 函数。然后使用 `FutureResult` 获取结果。

```cpp
#include "MatlabDataArray.hpp"
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

matlab::data::ArrayFactory factory;

matlab::data::Array argument = factory.createScalar<double>(12.7);

FutureResult future = matlabPtr->fevalAsync("sqrt", std::move(argument));

matlab::data::Array result = future.get();
```

# 相关主题

"异步调用函数"

### eval

```cpp
void eval(const matlab::engine::String &statement,
const std::shared_ptr<matlab::engine::StreamBuffer> &output = std::shared_ptr<matlab::engine::StreamBuffer>(),
const std::shared_ptr<matlab::engine::StreamBuffer> &error = std::shared_ptr<matlab::engine::StreamBuffer>());
```

## 描述

同步评估 MATLAB 语句。

## 参数

- `const matlab::engine::String &statement` - 要评估的 MATLAB 语句。
- `const std::shared_ptr<matlab::engine::StreamBuffer> &output` - 用于存储来自 MATLAB 函数标准输出的流缓冲区。
- `const std::shared_ptr<matlab::engine::StreamBuffer> &error` - 用于存储 MATLAB 函数错误信息的流缓冲区。

## 异常

- `matlab::engine::MATLABNotAvailableException` MATLAB 会话不可用。
- `matlab::engine::MATLABExecutionException` 语句中存在 MATLAB 运行时错误。
- `matlab::engine::MATLABSyntaxException` 语句中存在语法错误。

## 示例

此示例评估以下 MATLAB 语句。

```matlab
a = sqrt(12.7);
```

该语句在 MATLAB 工作区中创建了变量 a。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

matlabPtr->eval("a = sqrt(12.7)");
```

# 相关主题

从 C++ 调用 MATLAB

# evalAsync

```cpp
FutureResult evalAsync(const std::string &str,
const std::shared_ptr<matlab::engine::StreamBuffer> &output = std::shared_ptr<matlab::engine::StreamBuffer>(),
const std::shared_ptr<matlab::engine::StreamBuffer> &error = std::shared_ptr<matlab::engine::StreamBuffer>());
```



# 描述

异步评估 MATLAB 语句。

## 参数

- `const std::string &str` - 要评估的 MATLAB 语句。
- `const std::shared_ptr<matlab::engine::StreamBuffer> &output` - 用于存储来自 MATLAB 函数标准输出的流缓冲区。
- `const std::shared_ptr<matlab::engine::StreamBuffer> &error` - 用于存储 MATLAB 函数错误信息的流缓冲区。

## 返回值

| 类型 | 描述 |
| :--- | :--- |
| `FutureResult` | 用于等待 MATLAB 语句完成的 `FutureResult` 对象。 |

## 异常

无

## 示例

此示例异步评估以下 MATLAB 语句。

```matlab
a = sqrt(12.7);
```

该语句在 MATLAB 基工作区中创建了变量 `a`。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

FutureResult<void> future = matlabPtr->evalAsync("a = sqrt(12.7)");
```

# 相关主题

从 C++ 调用 MATLAB 语句

# getVariable

```cpp
matlab::data::Array getVariable(const matlab::engine::String &varName,
                                matlab::engine::WorkspaceType workspace = matlab::engine::WorkspaceType::BASE);
```

## 描述

从 MATLAB 基工作区或全局工作区获取变量。

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `const matlab::engine::String &varName` | MATLAB 工作区中的变量名称。以 `std::u16string` 指定名称。此外，您也可以用 `std::string` 指定此参数。 |
| `matlab::engine::WorkspaceType workspace` | 获取变量的 MATLAB 工作区（BASE 或 GLOBAL）。更多信息请参阅 `global`。 |

## 返回值

`matlab::data::Array` 从 MATLAB 基工作区或全局工作区获取的变量

## 异常

- `matlab::engine::MATLABNotAvailableException` - MATLAB 会话不可用。
- `matlab::engine::MATLABExecutionException` - 请求的变量在指定的 MATLAB 基或全局工作区中不存在。

## API 参考

```cpp
std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

matlab::data::Array varName = matlabPtr->getVariable(u"varName");
```

## 相关主题

将变量从 MATLAB 传递到 C++

# getVariableAsync

## 描述

异步从 MATLAB 基础或全局工作区获取变量。

## 参数

- `const matlab::engine::String varName` - MATLAB 工作区中的变量名称。类型为 `matlab::u16String` 的名称。你可以将其作为 `std::string` 类型的参数指定。
- `matlab::engine::WorkspaceType workspaceType` - 从中获取变量的工作区（BASE 或 GLOBAL）。更多信息，请参阅 `matlab::engine::WorkspaceType::BASE`。

## 返回值

一个 `FutureResult` 对象，可以使用它将从 MATLAB 工作区获取的变量转换为 `matlab::data::Array`。

## 异常

无

## 示例

此示例异步从 MATLAB 基础工作区获取变量 `varName`。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

FutureResult<matlab::data::Array> future = matlabPtr->getVariableAsync(u"varName");

matlab::data::Array varName = future.get();
```

## 相关主题

将变量从 MATLAB 传递到 C++

# setVariable

```cpp
void setVariable(const matlab::engine::String varName,
                 const matlab::data::Array var,
                 matlab::engine::WorkspaceType workspaceType = matlab::engine::WorkspaceType::BASE);
```

## 描述

将变量放入 MATLAB 基础或全局工作区。如果 MATLAB 工作区中存在同名变量，`setVariable` 将覆盖它。

## 参数

- `const std::u16string varName` - 在 MATLAB 工作区中创建的变量名称。请使用 `std::u16string` 指定 `matlab::engine::String` 名称。此外，你也可以将此参数指定为 `std::string`。
- `const matlab::data::Array var` - 在 MATLAB 工作区中创建的变量的值。
- `const matlab::engine::WorkspaceType workspaceType` - 将变量放入 MATLAB BASE 或 GLOBAL 工作区。有关 `workspaceType` 信息，请参阅 `matlab::engine::WorkspaceType::BASE`。

## 异常

- `matlab::engine::MATLABNotAvailableException` - MATLAB 会话不可用。

## 示例

此示例在 MATLAB 工作区中放入一个名为 `data` 的变量。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

matlab::data::Array data = factory::createArray<double>({{1, 3}, {4, 8, 6}});

matlabPtr->setVariable(u"data", data);
```

# setVariableAsync

```cpp
Future<void> setVariableAsync(const matlab::engine::String &varName,
                              const matlab::data::Array var,
                              matlab::engine::WorkspaceType workType = matlab::engine::WorkspaceType::BASE);
```

## 描述

异步将变量放入 MATLAB 基础或全局工作区。如果 MATLAB 基础工作区中存在同名变量，`setVariableAsync` 将覆盖它。

## 参数

- `const std::u16string varName` - 在 MATLAB 工作区中创建的变量名称。请使用 `std::u16string` 指定 `matlab::engine::String` 名称。此外，你也可以将此参数指定为 `std::string`。
- `const matlab::data::Array var` - 在 MATLAB 工作区中创建的变量的值。
- `const matlab::engine::WorkspaceType workType` - 将变量放入 MATLAB BASE 或 GLOBAL 工作区。有关 `workspaceType` 信息，请参阅 `matlab::engine::WorkspaceType::BASE`。

## 异常

无

## 示例

此示例在 MATLAB 基础工作区放入变量。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

matlab::data::Array data = factory::createArray<double>({{1, 3}, {4, 8, 6}});

matlabPtr->setVariable(u"data", data);
```

## 相关主题

将变量从 C++ 传递到 MATLAB

# getProperty

```cpp
matlab::data::Array getProperty(const matlab::data::Array& objectArray,
                                size_t index,
                                const matlab::engine::String &propertyName);

matlab::data::Array getProperty(const matlab::data::Array& object,
                                const matlab::engine::String &propertyName);
```

## 描述

获取对象的值。如果输入是对象数组，请指定对应所需属性对象的数组索引。

## 参数

- `const matlab::data::Array &objectArray` - MATLAB 对象数组。
- `const matlab::data::Array &object` - 标量 MATLAB 对象。
- `size_t index` - 从 0 开始的索引，用于指定返回属性的对象。
- `const matlab::engine::String &propertyName` - 属性名称。请使用 `std::u16string` 指定名称。你也可以将此参数指定为 `std::string`。

## 返回值

`matlab::data::Array` - 命名属性的值

## 异常

- `matlab::engine::MATLABNotAvailableException` - MATLAB 会话不可用。
- `matlab::engine::MATLABExecutionException` - 属性不存在。

## 示例

此示例在 `try/catch` 块中使用 `MATLABEngine::eval` 执行 MATLAB 语句。`MATLABEngine::getProperty` 成员函数返回异常对象。`getProperty` 返回 `matlab::data::CharArray` 类型的异常值。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

try {
    // code
} catch (const std::exception& e) {
    matlab::data::Array exception = matlabPtr->getVariable(u"me");
    matlab::data::CharArray messages = matlabPtr->getProperty(exception, u"message");
    std::cout << "messages: " << messages.toStdString() << std::endl;
}
```

## 相关主题

访问 MATLAB 对象和属性

# getPropertyAsync

```cpp
FutureResult<matlab::data::Array> getPropertyAsync(const matlab::data::Array& objectArray,
                                                   size_t index,
                                                   const matlab::engine::String& propertyName);

FutureResult<matlab::data::Array> getPropertyAsync(const matlab::data::Array& object,
                                                   const matlab::engine::String& propertyName);
```

## 描述

异步获取对象属性的值。如果输入是对象数组，请指定对应所需属性对象的数组索引。

## 参数

- `const matlab::data::Array &objectArray` - MATLAB 对象数组。
- `const matlab::data::Array &object` - 标量 MATLAB 对象。
- `size_t index` - 从 0 开始的索引，用于指定返回属性的对象。
- `const matlab::engine::String &propertyName` - 属性名称。请使用 `std::u16string` 指定名称。你也可以将此参数指定为 `std::string`。

## 返回值

`FutureResult` - 用于同步操作的 `FutureResult` 对象。

## 异常

无

## 示例

此示例在 `try/catch` 块中使用 `MATLABEngine::eval` 执行 MATLAB 语句。`MATLABEngine::getProperty` 成员函数返回异常对象。`getProperty` 返回一个 `FutureResult`，可以使用它来获取 `matlab::data::CharArray` 类型的异常消息。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

try {
    // code
} catch (const matlab::engine::MATLABException& mException) {
    FutureResult<matlab::data::Array> future = matlabPtr->getPropertyAsync(mException, u"message");
    matlab::data::CharArray messages = future.get();
    std::cout << "message is: " << messages.toStdString() << std::endl;
}
```

## 相关主题

访问 MATLAB 对象和属性

# setProperty

```cpp
void setProperty(matlab::data::Array& objectArray,
                 size_t index,
                 const matlab::engine::String &propertyName,
                 const matlab::data::Array& propertyValue);

void setProperty(matlab::data::Array& object,
                 const matlab::engine::String &propertyName,
                 const matlab::data::Array& propertyValue);
```



## 描述

设置对象属性的值。如果对象输入是对象数组，请指定对应要设置的属性值的数组索引。

## 参数

- `matlab::data::Array& objectArray`: MATLAB 对象数组。
- `matlab::data::Array& object`: 标量 MATLAB 对象。
- `size_t index`: 从 0 开始的索引，用于指定数组中设置属性值的对象。
- `const matlab::engine::String &propertyName`: 要设置的属性名称。请使用 `std::u16string` 指定名称。你也可以将此参数指定为 `std::string`。
- `const matlab::data::Array& propertyValue`: 赋值给属性的值。

## 异常

- `matlab::engine::MATLABNotAvailable`: MATLAB 会话不可用。
- `matlab::engine::MATLABExecution`: 属性不存在。

## 示例

此示例展示了如何设置 MATLAB 对象。将 `lineStyle` 属性的值设置为字符 `:` 会改变 MATLAB 中线段对象的属性值，并更新图表的线型。

```cpp
#include "MatlabEngine.hpp"

using namespace matlab::engine;

std::shared_ptr<MatlabEngine> matlabPtr = startMATLAB();

matlab::data::ArrayFactory factory;

matlab::data::Array ydata = factory.createArray<double>({1, 5}, {4.0, 11.0, 4.7, 36.2, 72.3});

matlab::data::Array lineHandle = matlabPtr->eval("plot", ydata);

matlab::data::Array uStyle = factory.createArray<char>(':-');

matlabPtr->setProperty(lineHandle, "LineStyle", uStyle);
```

## 相关主题

- 在 MATLAB 对象上设置属性

## setPropertyAsync

```cpp
FutureResult<void> setPropertyAsync(matlab::data::Array objectArray,
    size_t index,
    const matlab::engine::String& propertyName,
    const matlab::data::Array& propertyValue);

FutureResult<void> setPropertyAsync(matlab::data::Array object,
    const matlab::engine::String& propertyName,
    const matlab::data::Array& propertyValue);
```

## 描述

异步设置对象属性的值。如果输入参数是对象数组，请指定元素数组的索引，该索引对应你想要设置属性值的对象。

## 参数

- `matlab::data::Array objectArray`: MATLAB 对象数组。
- `matlab::data::Array object`: 标量 MATLAB 对象。
- `size_t index`: 指向对象数组的从 0 开始的索引，指定数组中要设置属性值的对象。
- `const matlab::engine::String& propertyName`: 要设置的属性名称。以 `std::u16string` 形式指定名称。此外，你也可以将此参数指定为 `std::string`。
- `const matlab::data::Array& propertyValue`: 赋值给属性的值。

## 异常

- `matlab::engine::MATLABNotAvailable`: MATLAB 会话不可用。
- `matlab::engine::MATLABExecution`: 属性不存在。

## 示例

此示例展示了如何异步设置 MATLAB 对象属性。它创建了一个 MATLAB 图形并返回线句柄对象。将 `LineStyle` 属性设置为字符 `:` 会改变 MATLAB 中对象的属性值，并更新图表的线型。

```cpp
#include "MatlabEngine.hpp"
using namespace matlab::engine;
std::unique_ptr<MatlabEngine> matlabPtr = startMATLAB();
matlab::data::ArrayFactory factory;
matlab::data::Array ydata = factory.createArray<double>({1, 5}, {4.0, 11.0, 4.7, 36.2, 72.23});
matlab::data::Array lineHandle = matlabPtr->feval(u"plot", ydata);
matlab::data::CharArray linestyle = factory.createCharArray(u":");
FutureResult<void> future = matlabPtr->setPropertyAsync(lineHandle, u"LineStyle", linestyle);
```

## 相关主题

- 在 MATLAB 对象上设置属性

## 版本历史

引入于 R2017b

## 参见

- `matlab::engine::connectMATLAB`

---

## matlab::engine::connectMATLAB

同步连接到共享的 MATLAB 会话

## 描述

```cpp
std::unique_ptr<MatlabEngine> connectMATLAB()
std::unique_ptr<MatlabEngine> connectMATLAB(const matlab::engine::String& name)
```

同步连接到本地机器上的共享 MATLAB 会话。

- 如果你指定了共享 MATLAB 会话的名称，但引擎找不到该名称的会话，引擎将抛出异常。
- 如果你没有指定名称且没有可用的共享 MATLAB 会话，引擎将启动一个新的共享 MATLAB 会话。不会启动 MATLAB 桌面。
- 如果你没有指定名称且存在可用的共享 MATLAB 会话，引擎将连接到第一个可用会话。

## 包含

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `const matlab::engine::String name` | 共享 MATLAB 会话的名称 |

## 返回值

`std::unique_ptr<MatlabEngine>`: 指向 `MatlabEngine` 对象的指针

## 异常

`matlab::engine::EngineException`: 如果函数连接到指定的 MATLAB 会话失败，则抛出异常。

## 示例

### 连接到共享 MATLAB 会话

连接到名为 `my_matlab` 的共享 MATLAB 会话。

```cpp
std::unique_ptr<MatlabEngine> matlabPtr = connectMATLAB(u"my_matlab");
```

## 版本历史

引入于 R2017b

## 参见

- `matlab::engine::connectMATLABAsync`

## 主题

- 从 C++ 启动 MATLAB 会话

---

## matlab::engine::connectMATLABAsync

异步连接到共享 MATLAB 会话

## 描述

```cpp
FutureResult<std::unique_ptr<MatlabEngine>> connectMATLABAsync()
FutureResult<std::unique_ptr<MatlabEngine>> connectMATLABAsync(const matlab::engine::String& name)
```

异步连接到本地机器上的共享 MATLAB 会话。

- 如果你指定了共享 MATLAB 会话的名称，但引擎找不到该名称的会话，则抛出异常。
- 如果你没有指定名称且没有可用的共享 MATLAB 会话，引擎将启动一个新的 MATLAB 会话。不会启动 MATLAB 桌面。
- 如果你没有指定名称且存在可用的共享 MATLAB 会话，引擎将连接到第一个可用会话。

## 包含

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `matlab::engine::String name` | 共享 MATLAB 会话的名称 |

## 返回值

`FutureResult<std::unique_ptr<MatlabEngine>>`: 你可以获取 `MatlabEngine` 指针的对象

## 示例

异步连接到名为 `my_matlab` 的共享 MATLAB 会话。使用 `FutureResult` 方法获取 `MatlabEngine` 指针。

```cpp
#include "MatlabEngine.hpp"
void asyncConnect() {
    using namespace matlab::engine;

    // 查找并连接到共享 MATLAB 会话
    FutureResult<std::unique_ptr<MatlabEngine>> future = connectMATLABAsync(u"my_matlab");

    std::unique_ptr<MatlabEngine> matlabPtr = future.get();
}
```

## 版本历史

引入于 R2017b

## 参见

- `matlab::engine::connectMATLAB`

## 主题

- C++ 连接到 MATLAB

---

## matlab::engine::convertUTF8StringTo16String

将 UTF-8 字符串转换为 UTF16 字符串

## 描述

```cpp
std::basic_string<char16_t> convertUTF8StringTo16String(const std::string& utf8string)
```

将 UTF-8 字符串转换为 UTF16 字符串。使用此函数将 ASCII 字符串转换为引擎函数使用的 `matlab::engine::String` 字符串。

## 包含

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `const std::string& utf8string` | UTF-8 字符串 |

## 返回值

| 返回值 | 描述 |
| :--- | :--- |
| `std::basic_string<char16_t>` | UTF16 字符串 |

## 异常

- `matlab::engine::OutOfException`: 函数分配内存失败。
- `matlab::engine::TypeConversionException`: 输入类型无法转换为 `std::basic_string<char16_t>`。

## 示例

### 转换

将 UTF-8 字符串转换为 `matlab::engine::String`（UTF16 字符串）。

```cpp
matlab::engine::String str = convertUTF8StringTo16String("sRoot = sqrt(12.7)");
```

## 另请参阅

- `matlab::engine::String`
- `matlab::engine::convertUTF8StringToUTF16String`

---

## matlab::engine::findMATLAB

同步查找共享的 MATLAB 会话

## 描述

```cpp
std::vector<String> findMATLAB()
```

查找本地机器上所有的共享 MATLAB 会话。

## 包含

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 参数

无

## 返回值

`std::vector<String>`: 包含本地机器上所有共享 MATLAB 会话名称的向量；如果没有可用的共享 MATLAB 会话，则返回空向量。

## 异常

- `matlab::engine::EngineException`: 当搜索共享 MATLAB 会话时调用失败，抛出异常。

## 示例

### 同步查找共享 MATLAB 会话

```cpp
std::vector<String> names = findMATLAB();
```

## 版本历史

引入于 R2017b

## 另请参阅

- `matlab::engine::findMATLABAsync`

---

## matlab::engine::findMATLABAsync

异步查找共享的 MATLAB 会话

## 描述

```cpp
FutureResult<std::vector<String>> findMATLABAsync()
```

异步查找本地机器上所有的共享 MATLAB 会话。

## 包含

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 参数

无

## 返回值

`FutureResult<std::vector<String>>`: 一个可以使用此获取本地机器上共享 MATLAB 会话名称的 `FutureResult` 对象。

## 示例

### 异步查找共享 MATLAB 会话

异步查找本地机器上所有共享 MATLAB 会话的名称。使用 `FutureResult::get` 获取名称。

```cpp
FutureResult<std::vector<String>> futureNames = findMATLABAsync();
std::vector<String> matlabSessions = futureNames.get();
```

## 版本历史

引入于 R2017b

## 另请参阅

- `matlab::engine::findMATLAB`

---

## matlab::engine::FutureResult

从异步操作检索结果

## 描述

`FutureResult` 是一个对象，您可以使用它来检索 MATLAB 函数或语句的结果。`FutureResult` 类提供了 C++ `std::future` 类的所有成员函数。

## 类详情

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 构造函数摘要

使用这些异步函数创建 `FutureResult` 对象：

- 由 `matlab::engine::MATLABEngine` 定义的异步成员函数
- `matlab::engine::startMATLABAsync`, `matlab::engine::connectMATLABAsync`, `matlab::engine::findMATLABAsync`

## 方法摘要

### 成员函数

- `cancel`: 取消 `FutureResult` 对象持有的操作。

### 委托给 std::future 的成员函数

- `operator=`, `share`, `get`, `wait`, `wait_for`, `wait_until`

## get 方法抛出的异常

- `matlab::engine::EngineException`: 无法启动或连接到 MATLAB 会话。
- `matlab::engine::CancelException`: 命令执行已取消。
- `matlab::engine::InterruptException`: 命令执行已中断。
- `matlab::engine::MATLABNotAvailableException`: MATLAB 会话不可用。
- `matlab::engine::MATLABSyntaxException`: MATLAB 函数中存在语法错误。
- `matlab::engine::MATLABException`: 函数中的 MATLAB 运行时错误。
- `matlab::engine::TypeConversionException`: 来自 MATLAB 函数的结果无法转换为指定的类型。

## 方法详情

### cancel

```cpp
bool FutureResult::cancel(bool allowInterrupt = true);
```

#### 描述

取消 MATLAB 函数或语句的评估。您无法取消使用以下函数的异步操作：`matlab::engine::startMATLABAsync`, `matlab::engine::connectMATLABAsync` 或 `matlab::engine::findMATLABAsync`。

#### 参数

- `bool allowInterrupt`: 如果为 false，如果执行已经开始，则不中断。

#### 返回值

| 类型 | 描述 |
| :--- | :--- |
| `bool` | 如果执行已经开始，命令是否已取消。 |

#### 示例

```cpp
bool flag = future.cancel();
```

#### 异常安全

无抛出异常

## 版本历史

引入于 R2017b

## 另请参阅

- 主题：异步调用函数

---

## matlab::engine::startMATLAB

同步启动 MATLAB

## 描述

```cpp
std::unique_ptr<MatlabEngine> startMATLAB(const std::vector<String>& options = std::vector<String>())
```

在单独进程中同步启动 MATLAB，并带有可选的 MATLAB 启动选项。

## 包含

| 命名空间 | 包含 |
| :--- | :--- |
| matlab::engine | MatlabEngine.hpp |

## 参数

| 参数 | 描述 |
| :--- | :--- |
| `const std::vector<String>& options` | MATLAB 启动选项（可选） |



# `matlab::engine::startMATLAB` (同步启动 MATLAB)

## 描述

`std::unique_ptr<MATLABEngine> startMATLAB(const std::vector<String>& options = std::vector<String>())`

在单独进程中同步启动 MATLAB，带有可选的 MATLAB 启动选项。

## 包含

- 命名空间: `matlab::engine`
- 包含: `MatlabEngine.hpp`

## 参数

`const std::vector<String>& options` 启动 MATLAB 的选项。您可以指定多个启动选项。引擎支持所有 MATLAB 启动选项，“不支持的启动选项”中列出的选项外。有关选项列表，请参见特定平台的命令 `matlab` (Windows), `matlab` (macOS) 或 `matlab` (Linux)。

## 返回值

`std::unique_ptr<MATLABEngine>` 指向 `MATLABEngine` 对象的指针

## 异常

`matlab::engine::EngineException` MATLAB 启动失败。

## 不支持的启动选项

引擎不支持这些 MATLAB 启动选项：

- `-h`
- `-help`
- `-?`
- `-n`
- `-e`
- `-softwareopengl`
- `-logfile`

有关 MATLAB 启动选项，请参见“常用的启动选项”。

## 示例

### 同步启动 MATLAB

同步启动 MATLAB 并返回一个指向 `MATLABEngine` 对象的唯一指针。

```cpp
std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();
```

### 带桌面环境启动 MATLAB

```cpp
auto matlabApplication = matlab::engine::startMATLAB({u"-desktop"});
```

### 带选项启动 MATLAB

使用 `-nojvm` 选项启动 MATLAB 并返回一个指向 `MATLABEngine` 对象的唯一指针。

```cpp
std::vector<String> optionVec;
optionVec.push_back(u"-nojvm");
std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB(optionVec);
```

## 版本历史

引入于 R2017b

## 另请

`matlab::engine::findMATLAB`

---

# `matlab::engine::FutureResult`

从异步操作检索结果

## 描述

结果是一个对象，您可以使用它来检索 MATLAB 函数或语句的结果。`FutureResult` 类提供了 C++ `std::future` 类的所有成员函数。

## 类详情

| 命名空间 | `matlab::engine` |
| --- | --- |
| 包含 | `MatlabEngine.hpp` |

## 构造函数摘要

使用这些异步函数创建 `FutureResult` 对象：

- 由 `matlab::engine::MATLABEngine` 定义的异步成员函数
- `matlab::engine::startMATLABAsync`, `matlab::engine::connectMATLABAsync`, `matlab::engine::findMATLABAsync`

## 方法摘要

### 成员函数

#### `cancel`

`bool FutureResult::cancel(bool allowInterrupt = true);`

##### 描述

取消 MATLAB 函数或语句的评估。您无法取消以下函数的异步操作：`matlab::engine::startMATLABAsync`, `matlab::engine::connectMATLABAsync` 或 `matlab::engine::findMATLABAsync`。

##### 参数

`bool allowInterrupt` 如果为 `false`，如果执行已经开始，则不中断。

##### 返回

| 类型 | 说明 |
| --- | --- |
| `bool` | 如果执行已经开始，命令是否已取消。 |

##### 示例

```cpp
bool flag = future.cancel();
```

##### 异常安全

无抛出异常

## 版本历史

引入于 R2017b

## 另请

**主题**

- “异步调用函数”

---

# `matlab::engine::startMATLABAsync`

异步启动 MATLAB

## 描述

`FutureResult<std::unique_ptr<MATLABEngine>> startMATLABAsync(const std::vector<String>& options = std::vector<String>())`

在单独进程中异步启动 MATLAB，带有可选的 MATLAB 启动选项。

## 包含

- 命名空间: `matlab::engine`
- 包含: `MatlabEngine.hpp`

## 参数

`const std::vector<String>& options` 启动 MATLAB 的选项。您可以指定多个启动选项。引擎支持所有 MATLAB 启动选项，“不支持的启动选项”中列出的选项外。有关选项列表，请参见特定平台的命令 `matlab` (Windows), `matlab` (macOS) 或 `matlab` (Linux)。

## 返回值

`FutureResult<std::unique_ptr<MATLABEngine>>` 一个可以使用此获取本地机器上共享 MATLAB 会话指针的 `FutureResult` 对象。

## 示例

### 异步启动 MATLAB

异步启动 MATLAB 并返回一个指向 `MATLABEngine` 对象的 `FutureResult` 对象。使用 `FutureResult::get` 获取指针。

```cpp
FutureResult<std::unique_ptr<MATLABEngine>> matlabFuture = startMATLABAsync();
std::unique_ptr<MATLABEngine> matlabPtr = matlabFuture.get();
```

## 版本历史

引入于 R2017b

## 另请

`matlab::engine::findMATLAB`

**主题**

- “指定启动选项”

---

# `matlab::engine::terminateEngine`

运行时释放引擎资源

## 描述

```cpp
void matlab::engine::terminateClient()
```

在不再需要引擎时释放所有 MATLAB 引擎资源。

> **注意** 调用 `terminateClient` 后程序无法启动新引擎或连接到共享会话。

## 包含

- 命名空间: `matlab::engine`
- 包含: `MatlabEngine.hpp`

## 示例

终止会话以释放资源。

```cpp
// 启动 MATLAB 会话
std::unique_ptr<MATLABEngine> matlabPtr = startMATLAB();

// 终止 MATLAB 会话
matlab::engine::terminateClient();
```

## 版本历史

引入于 R2017b

## 另请

`matlab::engine::MATLABEngine` | `matlab::data::ArrayFactory`

**主题**

- 从 C++ 将变量传递到 MATLAB
- 从 MATLAB 将变量传递到 C++

---

# `matlab::engine::String`

定义 UTF-16 字符串

## 描述

`std::basic_string<char16_t>` 的类型定义。

## 示例

此示例定义了一个包含共享 MATLAB 会话名称的变量。将此字符串传递给 `matlab::engine::connectMATLAB` 函数以连接到该命名的会话。

```cpp
matlab::engine::String session("myMatlabEngine");
std::unique_ptr<MATLABEngine> ptr_MATLABEngine = connectMATLAB(session);
```

## 版本历史

引入于 R2017b

## 另请

`matlab::engine::convertUTF8ToUTF16String` | `matlab::engine::convertUTF16ToUTF8String`

**主题**

- "从 C++ 运行 MATLAB"
- "将 C++ 连接到正在运行的 MATLAB 会话"

---

# `matlab::engine::StreamBuffer`

定义流缓冲区

## 描述

`std::basic_streambuf<char16_t>` 的类型定义。

## 示例

此示例定义了缓冲区用于通过 `MatlabEngine::member` 函数返回 MATLAB 函数的输出。该函数使用派自 `matlab::engine::StreamBuffer` 的缓冲区将 MATLAB 的输出返回到 C++。

```cpp
#include "MatlabEngine.hpp"
#include "MatlabArray.hpp"
#include <iostream>

using namespace matlab::engine;
using SBuf = std::basic_streambuf<char16_t>;

void printFromBuf(const std::shared_ptr<SBuf> buf) {
    // 从 buf 获取文本；
    auto text = buf->str();
    std::cout << "" << convertUTF16ToUTF8String(text) << std::endl;
}

int main() {
    // 创建数组工厂。
    matlab::data::ArrayFactory factory;
    // 连接到如下方式启动的命名共享 MATLAB 会话：
    // matlab::engine::shareEngine("myMatlabEngine");
    matlab::engine::String session("myMatlabEngine");
    std::unique_ptr<MATLABEngine> matlabPtr = connectMATLAB(session);

    auto outBuf = std::make_shared<SBuf>();
    auto errBuf = std::make_shared<SBuf>();

    matlabPtr->evaluate(u"matlab.engine.engineName", outBuf, errBuf);
    printFromBuf(outBuf);
    printFromBuf(errBuf);
    return 0;
}
```

## 版本历史

引入于 R2017b

## 另请

`matlab::engine::convertUTF16StringToUTF8String` | `matlab::engine::connectMATLAB`

**主题**

- "将 MATLAB 命令窗口输出重定向到 C++"

---

# `matlab::engine::SharedFutureResult`

作为共享未来（shared future）检索异步操作的结果

## 描述

共享未来结果是一个对象，您可以使用它来多次检索 MATLAB 函数或语句的结果。

## 类详细信息

| 命名空间 | `matlab::engine` |
| --- | --- |
| 包含 | `MatlabEngine.hpp` |

## 构造函数摘要

使用以下异步函数之一创建 `FutureResult` 对象：

- 由 `matlab::engine::MATLABEngine` 定义的异步成员函数。
- `matlab::engine::startMATLABAsync`, `matlab::engine::connectMATLABAsync`, `matlab::engine::findMATLABAsync`。

## 方法摘要

### 成员函数

- `cancel` - 通过 `FutureResult` 对象取消操作。

| 成员函数 | 委托给 `std::shared_future` |
| --- | --- |
| `operator=`, `get`, `valid`, `wait`, `wait_for`, `wait_until` | |

```cpp
get 方法抛出的异常：
matlab::engine::EngineException 无法启动或连接到 MATLAB 会话。
matlab::engine::CancelException 命令执行已取消。
matlab::engine::InterruptException 命令评估已中断。
matlab::engine::MATLABAvailableException MATLAB 会话不可用。
matlab::engine::MATLABSyntaxException MATLAB 函数中存在语法错误。
matlab::engine::MATLABExecutionException 函数中的 MATLAB 运行时错误。
```



```cpp
#include "MatlabEngine.hpp"
#include "MatlabArray.hpp"
#include <iostream>

using namespace matlab::;
using SBuf = std::basic_streambuf<char16_t>;

void printFromBuf(const std::shared_ptr<SBuf> buf) {
    // 从 buf 获取文本；
    auto text = buf->str();
    std::cout << "" << ConvertUTF16ToUTF8String(text) << std::endl;
}

int main() {
    // 创建数组工厂。
    matlab::data::ArrayFactory factory;
    // 连接到如下方式启动的命名共享 MATLAB 会话：
    // matlab::matlab::engine::shareEngine("myMatlabEngine");
    string session("myMatlabEngine");
    std::unique_ptr<MATLAB> matlabPtr = connectMATLAB(session);

    auto outBuf = std::make_shared<SBuf>();
    auto errBuf = std::make_shared<SBuf>();

    matlabPtr->evaluate(u"matlab.engine.engineName", outBuf, errBuf);
    printFromBuf(outBuf);
    printFromBuf(errBuf);
    return 0;
}
```

## 版本历史

引入于 R2017b

## 另请参阅

`matlab::engine::convertUTF16StringToUTF8String` | `matlab::engine::connectMATLAB`

## 主题

- "将 MATLAB 命令窗口输出重定向到 C++"

## `matlab::engine::SharedFutureResult`

作为共享未来检索异步操作的结果

## 描述

共享未来结果是一个对象，您可以使用它来多次检索 MATLAB 函数或语句的结果。

## 类详细信息

| 命名空间 | `matlab::engine` |
| --- | --- |
| 包含 | `MatlabEngine.hpp` |

## 构造函数摘要

使用以下异步函数之一创建 `FutureResult` 对象：

- 由 `matlab::engine::MATLABEngine` 定义的异步成员函数。
- `matlab::engine::startMATLABAsync`、`matlab::engine::connectMATLABAsync`、`matlab::engine::findMATLABAsync`。

## 方法摘要

## 成员函数

"cancel" - 通过 `FutureResult` 对象取消操作。

| 成员函数 | 委托给 `std::shared_future` |
| --- | --- |
| `operator=`、`get`、`valid`、`wait`、`wait_for`、`wait_until` | |

`get` 方法抛出的异常：
- `matlab::engine::EngineEx` 无法启动或连接到 MATLAB 会话。
- `matlab::engine::CancelEx` 命令执行已取消。
- `matlab::engine::InterruptException` 命令评估已中断。
- `matlab::engine::MATLABAvailableException` MATLAB 会话不可用。
- `matlab::engine::MATLABSyntaxException` MATLAB 函数中存在语法错误。
- `matlab::engine::MATLABExecutionException` 函数中的 MATLAB 运行时错误。

## `findMatlab`

```
static String[] findMatlab()
```

## 说明

同步查找本地机器上所有的共享 MATLAB 会话。

## 返回

本地机器上所有共享 MATLAB 会话名称的数组；如果本地机器没有可用的共享 MATLAB 会话，则返回空向量。

## 抛出

`com.mathworks.engine.EngineException` 在查找 MATLAB 会话期间发生故障。

## 示例

```
String[] engines = MatlabEngine.findMatlab();
```

## 另见

“Connect Java to Running MATLAB Session”

## `findMatlabAsync`

```
static Future<String[]> findMatlabAsync()
```

## 说明

查找本地机器上所有的共享 MATLAB 会话。

## 返回

`Future<String[]>` 实例

## 示例

```
Future<String[]> future = MatlabEngine.findMatlabAsync();
```

## 另见

“Connect Java to Running MATLAB Session”

## `connectMatlab`

```
static MatlabEngine connectMatlab(String name)
```

```
static MatlabEngine connectMatlab()
```

## 说明

同步连接到本地机器上的共享 MATLAB 会话。

- 如果指定了共享 MATLAB 会话的名称，但引擎找不到对应名称的会话，则引擎将抛出异常。
- 如果您没有指定名称且没有可用的共享 MATLAB 会话，引擎将使用默认选项启动一个新的 MATLAB 会话。
- 如果您没有指定名称且存在可用的共享 MATLAB 会话，引擎将连接到第一个可用的会话。

当从 MATLAB 环境调用时，请使用 `getCurrentMatlab` 连接当前的 MATLAB 会话。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `String name` | 共享 MATLAB 会话的名称。使用 1-175 页上的 "findMatlab" 获取共享 MATLAB 会话的名称。 |

## 返回

`MatlabEngine` 实例

## 抛出

`com.mathworks.engine.EngineException` MATLAB 启动或连接失败。

## 示例

```
MatlabEngine engine = MatlabEngine.connectMatlab();
```

## 另见

"Connect Java to Running MATLAB Session"

## `connectMatlabAsync`

```
static Future<MatlabEngine> connectMatlabAsync(String name)
```

```
static Future<MatlabEngine> connectMatlabAsync
```

## 说明

异步连接到本地机器上的共享 MATLAB 会话。其行为与 `matlabConnect` 相同，但机制是异步的。一旦连接到 MATLAB，您无法取消该方法。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `String name` | 共享 MATLAB 会话的名称。 |

## 返回

`Future<MatlabEngine>` 实例

## 示例

```
Future<MatlabEngine> future = MatlabEngine.connectMatlabAsync();
```

## 另见

"Connect Java to Running MATLAB Session"

## `getCurrentMatlab`

```
static MatlabEngine getCurrentMatlab()
```

## 说明

从 R2021b 开始，当从 MATLAB 环境调用时，连接到当前的 MATLAB 会话。

当从引擎应用程序调用以连接 MATLAB 会话时，请使用 `connectMatlab`。

## 返回

`MatlabEngine` 实例

## 抛出

```
com.mathworks.engine.EngineException Calling from user thread is not supported.
```

## 示例

```
MatlabEngine engine = MatlabEngine.getCurrentMatlab();
```

## 另见

“Call Back into MATLAB from Java”

## `feval`

```
<T> T feval(int nhls, String func, Writer output, Writer error, Object... args)
```

```
<T> T feval(int nhls, String func, Object... args)
```

```
<T> T feval(String func, Writer output, Writer error, Object... args)
```

```
<T> T feval(String func, Object... args)
```

## 说明

同步带输入参数评估 MATLAB 函数。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `String func` | MATLAB 函数名称和预期输出数量。默认值为 1。 |
| `int nhls` | 如果 `nhls` 大于 1，返回类型 `T` 必须为 `<Object>`。如果 `nhls` 为 0，返回类型 `T` 必须为 `<Void>` 或 `<?>`。如果 `nhls` 为 1，返回类型 `T` 可以是预期类型，或者在类型未知时为 `<Object>`。 |
| `Writer output` | 用于 MATLAB 函数标准输出的流。如果未指定 writer，输出将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的输出。 |
| `Writer error` | 用于存储 MATLAB 函数标准错误的流。如果未指定 writer，错误消息将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的错误消息。 |
| `Object... args` | 传递给 MATLAB 函数的参数。 |

## 返回

执行 MATLAB 函数的结果

## 抛出

- `java.util.concurrent.CancellationException` 对 MATLAB 函数的评估已取消。
- `java.lang.InterruptedException` 对 MATLAB 函数的评估被中断。
- `java.lang.IllegalStateException` MATLAB 会话不可用。
- `com.mathworks.engine.MatExecutionException` 函数中存在 MATLAB 运行时错误。
- `com.mathworks.engine.UnsupportedTypeException` 存在不支持的数据类型。
- `com.mathworks.engine.MatSyntaxException` MATLAB 函数中存在语法错误。

## 示例

```
double result = engine.feval("sqrt", 4);
```

## 另见

Execute MATLAB Functions

## `fevalAsync`

```
<Future<T>> fevalAsync(int nhls, String func, Writer output, Writer error, Object... args)
<Future<T>> fevalAsync(int nhls, String func, Object... args)
<Future<T>> fevalAsync(String func, Writer output, Writer error, Object... args)
<Future<T>> fevalAsync(String func, Object... args)
```

## 说明

异步评估 MATLAB 函数。

## 参数

- `String func`: MATLAB 函数名称。
- `int nhls`: 预期输出数量。如果 `nhls` 大于 1，返回类型 `T` 必须为 `<Object>`。如果 `nhls` 为 0，返回类型 `T` 必须为 `<Void>` 或 `<?>`。如果 `nhls` 为 1，返回类型 `T` 可以是预期类型，或者在类型未知时为 `<Object>`。默认 1。
- `Writer output`: 用于 MATLAB 函数标准输出的流。如果未指定 writer，输出将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的输出。
- `Writer error`: 用于存储 MATLAB 函数标准错误的流。如果未指定 writer，错误消息将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的错误消息。
- `Object... args`: 传递给 MATLAB 函数的参数。

## 返回

`Future` 实例

## 抛出

- `java.lang.IllegalStateException` MATLAB 会话不可用。

## 示例

```
Future<Double> future = engine.fevalAsync("sqrt", 4);
```

## 另见

Execute MATLAB Functions

## `eval`

```
void eval(String command, Writer output, Writer error)
```

```
void eval(String command)
```

## 说明

同步评估 MATLAB 语句。

## 参数

- `String command`: 要评估的 MATLAB 语句。
- `Writer output`: 用于 MATLAB 函数输出的流。如果未指定 writer，输出将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的输出。
- `Writer error`: 用于存储 MATLAB 函数标准错误的流。如果未指定 writer，错误消息将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的错误消息。

## 抛出

- `java.util.concurrent.CancellationException` 对 MATLAB 函数的评估已取消。
- `java.lang.InterruptedException` 对 MATLAB 函数的评估被中断。
- `java.lang.IllegalStateException` MATLAB 会话不可用。
- `com.mathworks.engine.MatExecutionException` MATLAB 语句在运行时存在错误。
- `com.mathworks.engine.MatSyntaxException` MATLAB 语句中存在语法错误。

## 示例

```
engine.eval("result = sqrt(4)");
```

## 另见

Evaluate MATLAB Statements from Java

## `evalAsync`

```
Future<Void> evalAsync(String command, Writer output, Writer error)
```

```
Future<Void> evalAsync(String command)
```

## 说明

异步评估 MATLAB 语句。

## 参数

- `String command`: 要评估的 MATLAB 语句。
- `Writer output`: 用于 MATLAB 函数输出的流。如果未指定 writer，输出将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的输出。
- `Writer error`: 用于存储 MATLAB 函数标准错误的流。如果未指定 writer，错误消息将写入命令行窗口或终端。使用 NULL WRITER 忽略 MATLAB 命令窗口的错误消息。

## 返回

`Future<Void>` 实例

## 抛出

- `java.lang.IllegalStateException` MATLAB 会话不可用。

## 示例

```
Future<Void> future = engine.evalAsync("result = sqrt(4)");
```

## 另见

Evaluate MATLAB Statements from Java

## 异常

`java.lang.IllegalStateException` MATLAB 会话可用。

## 示例

```
Future<Void> future = engine.evalAsync("sqrt(4)");
```

## 另请参阅

"从 Java 评估 MATLAB 语句"

## `getVariable`

```
<T> T getVariable(String varName)
```

## 描述

同步从 MATLAB 基础工作区获取变量。

## 参数

`String varName` MATLAB 基础工作区变量的名称。

## 返回

从 MATLAB 基础工作区传递的变量

## 异常

- `java.util.concurrent.CancellationException` 此函数的评估已取消。
- `java.lang.InterruptedException` 此函数的评估被中断。
- `java.lang.IllegalStateException` MATLAB 会话可用。

## 示例



# MATLAB Engine API for Java

## 示例

```
double myVar = engine.getVariable("myVar");
```

## 相关

"将变量从 MATLAB 传递到 Java"

## getVariableAsync

```java
<T> Future<T> getVariableAsync(String varName)
```

## 描述

异步从 MATLAB 基础工作区获取变量。

## 参数

`String varName` MATLAB 基础工作区变量的名称。

## 返回

`Future<T>` 实例

## 异常

```
java.lang.IllegalStateException MATLAB 会话可用。
```

## 示例

```
Future<Double> future = engine.getVariableAsync("myVar");
```

## 相关

"将变量从 MATLAB 传递到 Java"

## putVariable

```java
void putVariable(String varName, T varData)
```

## 描述

同步将变量放入 MATLAB 基础工作区。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `String varName` | 在 MATLAB 基础工作区中创建的变量名称。 |
| `T varData` | 在 MATLAB 基础工作区中创建的变量值。 |

## 异常

- `java.util.concurrent.CancellationException` 此函数的评估已取消。
- `java.lang.InterruptedException` 此函数的评估被中断。
- `java.lang.IllegalStateException` MATLAB 会话可用。

## 示例

```
engine.putVariable("myVar", 100);
```

## 相关

"将变量从 Java 传递到 MATLAB"

## putVariableAsync

```java
Future<Void> putVariableAsync(String varName, T varData)
```

## 描述

异步将变量放入 MATLAB 基础工作区。

## 参数

| 参数 | 说明 |
| :--- | :--- |
| `String varName` | 在 MATLAB 基础工作区中创建的变量名称。 |
| `T varData` | 在 MATLAB 基础工作区中创建的变量值。 |

## 返回

`Future<Void>` 实例

## 异常

`java.lang.IllegalStateException` MATLAB 会话可用。

## 示例

```
Future<Void> future = engine.putVariableAsync("myVar", 100);
```

## 相关

"将变量从 Java 传递到 MATLAB"

## disconnect

```java
void disconnect();
```

## 描述

同步与当前 MATLAB 会话断开连接。

## 异常

`com.mathworks.engine.EngineException` 无法关闭当前 MATLAB 会话。

## 示例

```
engine.disconnect();
```

## 相关

"关闭 MATLAB Engine 会话"

## disconnectAsync

```java
Future<Void> disconnectAsync();
```

## 描述

异步与当前 MATLAB 会话断开连接。

## 示例

```
Future<Void> future = engine.disconnectAsync();
```

## 相关

"关闭 MATLAB Engine 会话"

## quit

```java
void quit()
```

## 描述

同步强制关闭当前 MATLAB 会话。

## 异常

`com.mathworks.engine.EngineException` 无法关闭当前 MATLAB 会话。

## 示例

```
engine.quit();
```

## 相关

"关闭 MATLAB Engine 会话"

## quitAsync

```java
Future<Void> quitAsync()
```

## 描述

异步强制关闭当前 MATLAB 会话，且无需等待结束。

## 返回

`Future<Void>` 实例

## 示例

```
Future<Void> future = engine.quitAsync();
```

## 相关

"关闭 MATLAB Engine 会话"

## close

```java
void close()
```

## 描述

`MatlabEngine` 提供了 `close()` 方法来为 `MatlabEngine` 对象实现 `java.lang.AutoCloseable` 接口。此 `close()` 方法允许你使用 try-with-resources 语句在语句结束时自动断开连接或终止 MATLAB 会话。

`MatlabEngine.close()` 方法根据上下文断开或终止当前的 MATLAB 会话。

- 如果 Java 进程作为默认的非共享会话启动 MATLAB 会话，`close()` 将终止 MATLAB。
- 如果 MATLAB 会话是共享会话，`close()` 将 MATLAB 与此 Java 进程断开。当没有其他连接时，MATLAB 将终止。

要强制关闭或断开当前 MATLAB 会话，请显式调用 `MatlabEngine.quit()`、`MatlabEngine.disconnect()` 或其对应的异步方法。

## 示例

```
engine.close();
```

## 相关

"关闭 MATLAB Engine 会话"

## 版本历史

引入于 R2016b

## 从 MATLAB 调 Java 程序调用 MATLAB

Java 可以使用 `getCurrentMatlab` 方法从 Java 调用 MATLAB。在应用程序中整合此方法允许 MATLAB 用户调用你的 Java 程序的功能。

## 函数执行后显示的文本输出

行为在 R2020b 中发生了变化

在 R2020b 之前，`eval`、`evalAsync`、`feval` 和 `fevalAsync` 方法在 MATLAB 函数评估期间持续向 Java `Writer` 类对象写入文本。对于 R2020b 及更高版本，这些方法在函数评估后向输出对象写入文本。

## 相关

```
matlab.engine.shareEngine | matlab.engine.engineName | matlab.engine.isEngineShared
```

## 主题

- "构建 Java 程序"
- "从 Java  MATLAB 会话"
- "指定启动选项"

# com.mathworks.types.Complex

与 MATLAB 传递复数数据的 Java 类

## 描述

`Complex` 类为 MATLAB 复数数组提供了 Java 支持。使用此类将复数数据传递给 MATLAB。MATLAB 将复数数据作为 `Complex` 实例传递给 Java。

所有 MATLAB 数字类型在 Java 中均转换为 `double`。

## 字段摘要

| 字段 | 说明 |
| :--- | :--- |
| `double real` | 实部 |
| `double imag` | 虚部 |

## 创建

`Complex(double real, double imag)` 根据指定的实部和虚部构造 `Complex` 实例。

## 示例

### 向 MATLAB 函数传递复数变量

```
import com.mathworks.engine.MatlabEngine

MatlabEngine engine = MatlabEngine.startMatlab();
Complex c = new Complex(2,3);
Complex c = engine.feval("conj",c);
```

## 版本历史

引入于 R2016b

## 相关

`com.mathworks.matlab.types.Struct` | `com.mathworks.matlab.types.HandleObject` | `com.mathworks.matlab.types.CellStr`

## 主题

"在 Java 中使用复数变量"

# com.mathworks.types.HandleObject

用于表示 MATLAB 句柄的抽象 Java 类

## 描述

Java 将从 MATLAB 传递的句柄表示为 `HandleObject` 类实例。将句柄传回 MATLAB 时，Java 传递实例的引用。该引用可以是数组或标量，取决于传递给 Java 的原始句柄。

## 创建

无法在 Java 中构造 `HandleObject`。你只能将句柄传递到创建它的 MATLAB 会话。

## 示例

### 从 MATLAB 获取句柄

此示例启动共享 MATLAB 会话并在 MATLAB 工作区创建一个 `containers.Map` 对象。在 MATLAB 工作区评估的语句返回一个指向 Map 对象的句柄变量。

`engine.getVariable` 函数将 MATLAB 句柄变量作为 `HandleObject` 实例返回。该实例用于调用 MATLAB `keys` 函数获取 Map 的键。

```
import com.mathworks.engine.MatlabEngine;
import com.mathworks.engine.matlab.types.*;

MatlabEngine engine = MatlabEngine.startMatlab();
engine.eval('cm = containers.Map({'id','name'},{11,'mw'});\nHandleObject handle = engine.getVariable("cm");
String[] cells = engine.feval("keys", handle);
```

## 版本历史

引入于 R2016b

## 相关

`com.mathworks.matlab.types.Complex` | `com.mathworks.matlab.types.HandleObject` | `com.mathworks.matlab.types.CellStr`

# com.mathworks.matlab.types.Struct

用于在 MATLAB 和 Java 之间传递 MATLAB 结构体的 Java 类

## 描述

`Struct` 类支持以 MATLAB 结构体的形式在 MATLAB 和 Java 之间传递数据。`Struct` 类实现了 `java.util.Map` 接口。

`Struct` 类被设计为不可变类型。尝试更改返回的 `Struct` 的映射、键或值将导致 `UnsupportedOperationException`。调用这些方法可能会引起异常：`put()`、`getAll()`、`entrySet()`、`keySet()` 和 `values()`。

示例请参见“在 Java 中使用 MATLAB 结构”。

## 创建

`Struct s = new Struct("field1","field2",value2, ...)` 创建一个具有指定字段名和值的 `Struct` 实例。

## 方法

### 公有方法

- `containsKey(Object key)` 如果此 map 包含指定键的映射，则返回 true。
- `containsValue(Object key)` 如果此 map 将一个或多个键映射到指定值，则返回 true。
- `entrySet()` 返回此 map 中包含的映射的 Set 视图。
- `equals(Object o)` 将指定的对象与此 map 进行等值比较。
- `get(Object key)` 返回指定键的映射值，如果此 map 不包含该键的映射，则返回 null。
- `hashCode()` 返回此 map 的哈希码值。
- `isEmpty()` 如果此 map 不包含任何键值映射，则返回 true。
- `keySet()` 返回此 map 中包含的键的 Set。
- `size()` 返回此 map 中键值映射的数量。
- `values()` 返回此 map 中包含的值的 Collection 视图。

## 示例

### 为 MATLAB 函数参数创建 Struct

创建一个 `Struct` 并分配一个键和对应值。

```
import com.mathworks.engine.*;
import com.mathworks.matlab.types.*;
class StructProperties {
    public static void main(String[] args) throws Exception {
        MatlabEngine eng = MatlabEngine.startMatlab();
        int[] y = {1,2,3,4,5};
        double[] color = {1.0,0.5,0.7};
        Struct s = new Struct("Color","LineWidth",2);
        eng.feval("plot",y,s);
    }
}
```

## 版本历史

于 R2016b 中引入

## 参见

`com.mathworks.matlab.types.HandleObject` | `com.mathworks.matlab.types.Complex` | `com.mathworks.matlab.types.CellStr`

## 主题

“在 Java 中使用 MATLAB 结构”

# com.mathworks.matlab.types.ValueObject

表示 MATLAB 值对象的抽象 Java 类

## 描述

Java 将从 MATLAB 传递的值对象表示为 `ValueObject` 类的实例。

## 创建

你无法在 Java 中构造 `ValueObject`。你只能将值对象传递到它最初创建它的 MATLAB 会话中。

## 示例

### 在 MATLAB 中创建多形对象

创建一个多形并调用 `numsides` 方法。

```
import com.mathworks.engine.*;
import com.mathworks.matlab.types.*;

public class PassValueObject {
    public static void main(String[] args) throws Exception {
        MatlabEngine eng = MatlabEngine.startMatlab();

        // 创建对象 pgon = polyshape([0 1 3], [0 3 0]);
        ValueObject pgon = eng.feval("polyshape", new int[]{0,1,3}, new int[]{0,3,0});

        // 调用方法 res = numsides(pgon)
        Object ns = eng.feval("numsides", pgon);
        System.out.println("Number of sides: " + ns);

        eng.close();
    }
}
```

## 版本历史

于 R2021a 中引入

## 参见

# com.mathworks.matlab.types.CellStr

表示 MATLAB 字符向量单元格数组的 Java 类

## 描述

`CellStr` 类支持将数据从 Java 传递到 MATLAB 并作为 MATLAB 字符向量单元格数组，参见 MATLAB 中的 `cellStr`，参见 `cellStr`。某些 MATLAB 函数需要字符向量单元格数组作为输入。为了从 Java 向需要 `cellStr` 输入的 MATLAB 函数传递参数，使用 Java `CellStr` 类创建一个兼容类型。

MATLAB `cellStr` 映射到 Java 字符串数组。

## 创建

`CellStr(Object stringArray)` 使用字符串或字符串数组创建 `CellStr`。该数组可以是多个维度。

## 方法

### 公有方法

| 方法 | 描述 |
| :--- | :--- |
| `Object getCStringArray()` | 获取用于创建 `CellStr` 的字符串或字符串数组。 |
| `boolean equals(CellStr1,CellStr2)` | 比较两个 `CellStr` 实例。如果两个 `CellStr` 实例包含的字符串或字符串数组相同，则它们相等。 |

## 示例

### 构造 CellStr

构造一个名为 `keySet` 的 `CellStr` 并将该变量放入 MATLAB 基础工作区。

```
import com.mathworks.engine.*;
import com.mathworks.matlab.types.*;

class CellStr {
    public static void main(String[] args) throws Exception {
        MatlabEngine eng = MatlabEngine.startMatlab();
        CellStr keySet = new CellStr(new String[]{"Jan", "Feb", "Mar", "Apr"});
        eng.putVariable("keySet", keySet);
        eng.close();
    }
}
```

### 构造 CellStr 数组

创建 `CellStr` 数组并传递给 MATLAB `plot` 函数，以更改 MATLAB 生成的图形的外观。对 MATLAB `print` 函数的调用将导出。

## engGetVariable (C)

从 MATLAB 引擎工作空间复制变量

### 语法



# engGetVariable (C)

## C 语法

```c
#include "engine.h"
mxArray *engGetVariable(Engine *ep, const char *name);
```

## 描述

`engGetVariable` 从与 `ep` 相关的 MATLAB 引擎会话读取名为 `mxArray`。

传输的数据大小限制为 2 GB。

在完成操作后，使用 `mxDestroyArray` 销毁由此例程创建的 `mxArray`。

## 输入参数

- **ep** — 引擎指针 `Engine *`
  指向引擎的指针，指定为 `Engine *`。

- **name** — mxArray 的名称 `const char *`
  要从 MATLAB 工作空间获取的 mxArray 名称，指定为 `const char *`。

## 输出参数

- **ptr** — 指向 mxArray 的指针 `mxArray * | NULL`
  指向新分配 mxArray 结构的指针，返回类型为 `mxArray *`。如果尝试失败则返回 `NULL`。如果指定的变量不存在，则 `engGetVariable` 失败。

## 示例

查看 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `engdemo.c` 用于 UNIX 操作系统上的 C 示例。
- `engwindemo.c` 用于 Microsoft Windows 操作系统上的 C 示例。

## 版本历史

在 R2006a 之前引入

## 另见

`engPutVariable` | `mxDestroyArray`

---

# engGetVisible (C)

确定 MATLAB 引擎会话的可见性

## C 语法

```c
#include "engine.h"
int engGetVisible(Engine *ep, bool *value);
```

## 参数

- **ep** — Engine 指针
- **value** — `engGetVisible` 返回的指针值

## 返回

仅限 Microsoft Windows 操作系统

成功时返回 0，否则返回 1。

## 描述

`engGetVisible` 返回 MATLAB 引擎会话 `ep` 的当前可见性设置。可见的引擎会话在 Windows 桌面的窗口中运行，使得引擎可以进行交互。MATLAB 会将不可见的会话从桌面上移除。

## 示例

以下代码打开引擎会话 `ep` 并禁用了它的可见性。

```c
Engine *ep;
bool vis;

ep = engOpen(NULL);
engSetVisible(ep, 0);
```

要确定当前的可见性设置，使用：

```c
engGetVisible(ep, &vis);
```

## 另见

`engSetVisible`

---

# Engine (C)

MATLAB 引擎类型

## 描述

指向 MATLAB 引擎对象的句柄。

`Engine` 是 C 语言的一种不透明类型。

你可以通过编写使用 MATLAB 引擎库的 C 程序来将 MATLAB 调用为计算引擎。`Engine` 是你的程序与独立的 MATLAB 引擎进程之间的链接。

包含此类型的头文件是：

```c
#include "engine.h"
```

## 示例

查看 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `engdemo.c` 显示了如何在 C 程序中调用 MATLAB 引擎函数。
- `engwindemo.c` 显示了如何在针对 Windows 系统的 C 程序中调用 MATLAB 引擎函数。
- `fengdemo.F` 显示了如何从 Fortran 程序中调用 MATLAB 引擎函数。

## 另见

`engOpen`

---

# engOpen (C)

启动 MATLAB 引擎会话

## 语法

```c
#include "engine.h"
Engine *engOpen(const char *startcmd);
```

## 描述

`engOpen` 启动 MATLAB 进程以将 MATLAB 作为计算引擎。

### Windows 平台

`engOpen` 在不带桌面的情况下启动 MATLAB。

该函数打开到 MATLAB 的 COM 通道。启动安装期间注册的 MATLAB 软件。如果你安装期间没有注册，请参见“将 MATLAB 注册为 COM 服务器”。

### UNIX 平台

在 UNIX 系统上，`engOpen`：

1. 创建两个管道。
2. 分叉一个新进程。设置管道将 MATLAB（父进程）的 stdin 和 stdout 传递到引擎程序（子进程）的两个文件描述符。
3. 执行命令运行 MATLAB 软件（远程执行使用 rsh）。

## 输入参数

- **startcmd** — MATLAB 启动命令 `const char * | NULL`
  MATLAB 启动命令，指定为 `const char *`。

  在 Windows 系统上，`startcmd` 必须为 `NULL`。

  在 UNIX 系统上：
  - 如果 `startcmd` 为 `NULL` 或空字符串，`engOpen` 使用命令 `matlab` 在当前主机上启动 MATLAB 进程。
  - 如果 `startcmd` 是主机名，`engOpen` 将通过将指定的主机名字符串嵌入到较大的字符串中，在指定的主机上启动 MATLAB 进程：
    `"rsh hostname /bin/sh -c 'setenv DISPLAY\nhostname:0; matlab\'"`
  - 如果 `startcmd` 是任何其他字符串（包含空格或非字母数字字符），MATLAB 字面上执行该字符串。

## 输出参数

- **ptr** — 指向 MATLAB 引擎的句柄 `Engine * | NULL`
  指向 MATLAB 引擎的句柄，指定为 `Engine *`。如果打开失败则返回 `NULL`。

## 示例

查看 `matlabroot/extern/examples/eng_mat.c`：

- `engdemo.c` 用于 UNIX 操作系统上的 C 示例。
- `engwindemo.c` 用于 Microsoft Windows 操作系统上的 C 示例。

## 版本历史

在 R2006a 之前引入

## 另见

---

# engOpenUse (C)

## C 语法

```c
#include "engine.h"
Engine *engOpenUse(const char *startcmd, int dcom);
```

## 参数

- **startcmd** — 启动 MATLAB 的字符串。在 Windows 系统上，`startcmd` 必须为 `NULL`。
- **dcom** — 预留以后使用。
- **retstatus** — 返回状态。

## 返回

仅限 Windows 操作系统

返回引擎句柄，如果打开失败则返回 `NULL`。

## 描述

此例程允许使用 MATLAB 作为计算引擎来启动 MATLAB 进程。`engOpenUse` 在不带桌面的情况下启动 MATLAB。

该函数打开到 MATLAB 的 COM 通道。启动安装期间注册的 MATLAB 软件。如果你安装期间没有注册，请参见“将 MATLAB 注册为 COM 服务器”。

### UNIX 平台

在 UNIX 系统上，`engOpenUse`：

1. 创建两个管道。
2. 分叉一个新进程。设置管道将 MATLAB（父进程）的 stdin 和 stdout 传递到引擎程序（子进程）的两个文件描述符。
3. 执行命令运行 MATLAB 软件（远程执行使用 rsh）。

---

# engSetVisible (C)

显示或隐藏 MATLAB 引擎会话

## C 语法

```c
#include "engine.h"
int engSetVisible(Engine *ep, bool value);
```

## 参数

- **ep** — 引擎指针
- **value** — 要设置的 Visible（可见）属性。将 `value` 设置为 1 可使引擎窗口可见，设置为 0 则使其隐藏。

## 返回值

仅限 Microsoft Windows 操作系统

成功时返回 0，否则返回 1。

## 描述

`engSetVisible` 在 Windows 桌面上将 MATLAB 引擎会话 `ep` 的窗口设置为可见或隐藏。你可以使用此函数来启用或禁用用户与 MATLAB 引擎会话的交互。

## 示例

以下代码打开引擎会话 `ep` 并禁用了其可见性。

```c
Engine *ep;
bool vis;
ep = engOpen(NULL);
engSetVisible(ep, 0);
```

要确定当前的可见性设置，请使用：

```c
engGetVisible(ep, &vis);
```

## 另见

`engGetVisible`

---

# engClose (Fortran)

退出 MATLAB 引擎会话

## Fortran 语法

```fortran
#include "engine.h"
integer*4 engClose(ep)
mwPointer ep
```

## 描述

向 MATLAB 引擎会话发送退出命令并关闭连接。成功返回 0，失败返回 1。可能的失败原因包括尝试终止一个已经终止的 MATLAB 引擎会话。

## 输入参数

- **ep** — 引擎指针 `mwPointer`
  引擎指针，指定为 `mwPointer`。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `fengdemo.F` 包含一个 Fortran 示例。

## 版本历史

在 R2006a 之前引入

## 另见

`engOpen`

---

# engEvalString (Fortran)

求值字符串中的表达式

## Fortran 语法

```fortran
#include "engine.h"
integer*4 engEvalString(ep, string)
mwPointer ep
character*(*) string
```

## 描述

`engEvalString` 对之前由 `engOpen` 定义的 MATLAB 引擎会话 `ep` 求值字符串包含的表达式。

### UNIX 操作系统

在 UNIX 系统上，`engEvalString` 通过向 MATLAB 的 stdin 进程写入管道来发送命令。MATLAB 将命令通常显示在屏幕上的任何输出从 stdout 读取并存入由 `engOutputBuffer` 定义的缓冲区中。

要在 Fortran 中关闭输出缓冲，请使用：

`engOutputFile(ep, '')`

### Microsoft Windows 操作系统

在 Windows 系统上，`engEvalString` 使用组件对象模型（COM）接口与 MATLAB 通信。

## 输入参数

- **ep** — 引擎指针 `mwPointer`
  引擎指针，指定为 `mwPointer`。

- **string** — 要求值的表达式 `character*(*)`
  要求值的表达式，指定为 `character*(*)`。

## 输出参数

- **status** — 状态 `integer*4`
  状态，返回类型为 `integer*4`。如果引擎会话不再运行或引擎指针无效或为空，则返回 1。否则，即使 MATLAB 引擎会话无法求值命令，也返回 0。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `fengdemo.F` 包含一个 Fortran 示例。

## 版本历史

在 R2006a 之前引入

## 另见

`engOpen` | `engOutputBuffer`

---

# engGetVariable (Fortran)

从 MATLAB 引擎工作区复制变量

## Fortran 语法

```fortran
#include "engine.h"
mwPointer engGetVariable(ep, name)
mwPointer ep
character*(*) name
```

## 描述

`engGetVariable` 从与 `ep` 关联的 MATLAB 引擎会话读取命名的 `mxArray`。

成功返回 0，发生错误返回 1。

传输数据的大小限制为 2 GB。

使用 `mxDestroyArray` 销毁由此函数创建的 `mxArray`。

## 输入参数

- **ep** — 引擎指针 `mwPointer`
  引擎指针，指定为 `mwPointer`。

- **name** — mxArray 的名称 `character*(*)`
  mxArray 的名称，指定为 `character*(*)`。

## 输出参数

- **ptr** — mxArray 的指针 `mwPointer`
  mxArray 的指针。如果成功返回 0，如果发生错误返回 1。

## 版本历史

在 R2006a 之前引入

## 另见

`mxArray`

---

# engOpen (Fortran)

启动 MATLAB 引擎

## Fortran 语法

```fortran
#include "engine.h"
mwPointer engOpen(cmd)
character*(*) cmd
```

## 描述

`engOpen` 在 Windows 平台上启动 MATLAB 引擎。使用 COM 接口启动 MATLAB。

### UNIX 平台

在 UNIX 系统上，`engOpen`：

1. 创建两个管道。
2. 分叉一个进程。
3. 设置 MATLAB 引擎。使用指定的 `cmd` 启动 MATLAB。

## 输入参数

- **cmd** — MATLAB 命令 `character*(*)`
  MATLAB 命令，指定为 `character*(*)`。如果 `cmd` 为空，则启动 MATLAB。

## 返回值

- **ptr** — 引擎指针 `mwPointer`
  引擎指针。如果失败则返回 `NULL`。

---

# matClose (C 和 Fortran)

关闭 MAT-file

## C 语法

```c
#include "mat.h"
int matClose(MATFile *mfp);
```

## Fortran 语法

```fortran
#include "mat.h"
integer*4 matClose(mfp)
mxPointer mfp
```

## 参数

- **mfp** — 指向 MAT-file 信息的指针

## 返回

写入错误时 C 中返回 `EOF`（Fortran 中返回 -1），成功时返回 0。

## 描述

`matClose` 关闭与 `mfp` 关联的 MAT-file。

## 示例

参考 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matcreat.c`
- `matdgns.c`
- `matdemo1.F`
- `matdemo2.F`

## 另见

`matOpen`

## 版本历史

R2006a 之前引入

---

# matDeleteVariable (C 和 Fortran)

从 MAT-file 中删除数组

## C 语法

```c
#include "mat.h"
int matDeleteVariable(MATFile *mfp, const char *name);
```

## Fortran 语法

```fortran
#include "mat.h"
integer*4 matDeleteVariable(mfp, name)
mxPointer mfp
character*(*) name
```

## 参数

- **mfp** — 指向 MAT-file 信息的指针
- **name** — 要删除的 mxArray 名称

## 返回

成功时返回 0，否则返回非零。

## 描述

`matDeleteVariable` 从 `mfp` 指向的 MAT-file 中删除指定的 `mxArray`。

## 示例

参考 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matdemo1.F`

## 版本历史

R2006a 之前引入

---

# MATFile (C 和 Fortran)

MAT-file 类型

## 描述

指向 MAT-file 对象的句柄。MAT-file 是 MATLAB 软件用于保存到磁盘的数据文件格式。

`MATFile` 是 C 语言的一种不透明类型。

MAT-file 接口库包含读取和写入 MAT-file 的例程。可以在自己的 C/C++ 和 Fortran 程序中调用这些例程，使用 `MATFile` 访问您的数据文件。

包含此类型的头文件是：

```c
#include "mat.h"
```

## 示例

参考 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matcreat.c`
- `matdgns.c`
- `matdemo1.F`
- `matdemo2.F`

## 另见

`matOpen` | `matClose` | `matPutVariable` | `matGetVariable` | `mxDestroyArray`

---

# matGetDir (C 和 Fortran)

MAT-file 中的变量列表

## C 语法

```c
#include "mat.h"
char **matGetDir(MATFile *mfp, int *num);
```

## Fortran 语法

```fortran
#include "mat.h"
mxPointer matGetDir(mfp, num)
mxPointer mfp
integer*4 num
```

## 参数

- **mfp** — 指向 MAT-file 信息的指针
- **num** — 指向包含 MAT-file 中 mxArray 数量的指针



## 返回

指向内部数组的指针，该数组包含 `mfp` 指向的 MAT-file 中 `mxArray` 名称的指针。在 C 中，每个名称都是以 NULL 结尾的字符串。输出参数 `num` 是内部数组的长度（MAT-file 中 `mxArray` 的数量）。如果 `num` 为 0，则 `mfp` 不包含任何数组。

`matGetDir` 在 C 中返回 `NULL`（Fortran 中返回 0）。如果 `matGetDir` 失败，会将 `num` 设置为负数。

## 描述

此例程为您提供 MAT-file 中包含的 `mxArray` 名称的列表。

`matGetDir` 使用 `mxCalloc` 为内部字符串数组分配内存。在完成该数组后，使用 `mxFree` 释放内存。

MATLAB 变量名的长度最大可达 `MXNAM`，该值在 C 头文件 `matrix.h` 中定义。

## 示例

参考 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matcreat.c`
- `matdgns.c`
- `matdemo2.F`

## 版本历史

R2006a 之前引入

## matGetFp (C)

指向 MAT-file 的文件指针

### C 语法

```c
#include "mat.h"
FILE *matGetFp(MATFile *mfp);
```

## 参数

- `mfp`: 指向 MAT-file 信息的指针

## 返回

指向句柄 `mfp` 的 MAT-file 的 C 文件句柄。如果 `mfp` 指向基于 HDF5 格式的 MAT-file，则返回 `NULL`。

## 描述

使用 `matGetFp` 获取 MAT-file 的 C 文件句柄。标准 C 例程（如 `error` 和 `eof`）使用文件句柄来检查错误。

## 版本历史

R2006a 之前引入

## matGetNextVariable (C 和 Fortran)

MAT-file 中的下一个数组

### C 语法

```c
#include "mat.h"
mxArray *matGetNextVariable(MATFile *mfp, const char **name);
```

### Fortran 语法

```fortran
#include "mat.h"
mxPointer matGetNextVariable(mfp, name)
mxPointer mfp
char*(*) name
```

## 参数

- `mfp`: 指向 MAT-file 信息的指针
- `name`: 指向包含 `mxArray` 名称的变量的指针

## 返回

指向新分配的 `mxArray` 结构的指针，代表 `mfp` 指向的 MAT-file 中的下一个 `mxArray`。该函数在 `name` 中返回 `mxArray` 的名称。

`matGetNextVariable` 在 C 中返回 `NULL`（Fortran 中返回 0）表示文件结束或发生错误条件。在 C 中，使用标准 C 库的 `feof` 和 `ferror` 来确定状态。

## 描述

`matGetNextVariable` 允许您顺序遍历 MAT-file 并在单次通过读取每个 `mxArray`。该函数读取并返回 `mfp` 指向的 MAT-file 中的下一个 `mxArray`。

请在用 `matopen` 打开 MAT-file 后立即使用 `matGetNextVariable`，并遵循 MAT-file 规则。否则，下一个 `mxArray` 的概念是未定义的。

在完成使用后，使用 `mxDestroyArray` 销毁此运行时创建的 `mxArray`。

连续调用 `matGetNextVariable` 返回的变量顺序不保证与变量写入的顺序相同。

## 示例

参考 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matdgns.c`
- `matdemo2.F`

## 另请参阅

`matGetNextVariable`, `mxDestroyArray`

## 版本历史

R2006a 之前引入

## matGetVariableInfo (C 和 Fortran)

仅包含数组头部信息

### C 语法

```c
#include "mat.h"
mxArray *matGetVariableInfo(MATFile *mfp, const char *name);
```

### Fortran 语法

```fortran
#include "mat.h"
mwPointer matGetVariableInfo(mfp, name)
mwPointer mfp
character*(*) name
```

## 参数

- `mfp`: 指向 MAT-file 信息的指针
- `name`: 要从 MAT-file 获取的 `mxArray` 名称

## 返回

指向一个新分配的 `mxArray` 结构的指针，该结构代表由 `mfp` 指向的 MAT-file 中名为 `name` 的 `mxArray` 的头部信息。

如果尝试返回名为 `name` 的 `mxArray` 的头部信息失败，`matGetVariableInfo` 在 C 中返回 `NULL`（在 Fortran 中返回相应值）。

## 描述

`matGetVariableInfo` 仅加载数组头部信息，包括除 `pr`、`pi`、`ir` 和 `jc` 以外的所有内容，它通过叶子元素递归地创建单元格和结构，但不包括 `pr`、`pi`、`ir` 和 `jc`。

如果使用 `matGetVariableInfo` 加载时 `pr`、`pi`、`ir` 和 `jc` 为非零值，则会将其设置为 -1。这些头部信息仅供参考。永远不要将此类数据传回 MATLAB 工作区或将其保存到 MAT-file。

在使用完此程序创建的 `mxArray` 后，请使用 `mxDestroyArray` 销毁它。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matdemo2.F`

## 另请参阅

`matGetVariable`

## 版本历史

在 R2006a 之前引入

## matGetErrno (C 和 Fortran)

MAT-file API 的错误代码

### C 语法

```c
#include "mat.h"
matError matGetErrno(MATFile *mfp)
```

### Fortran 语法

```fortran
#include "mat.h"
matError matGetErrno(mfp)
mwPointer mfp
```

## 参数

- `mfp`: 指向 MAT-file 的指针

## 返回

`matError` 错误代码枚举

```c
typedef enum {
    mat_NO_ERROR = 0,
    mat_UNKNOWN_ERROR,
    mat_GENERIC_READ_ERROR,
    mat_GENERIC_WRITE_ERROR,
    mat_INDEX_TOO_BIG,
    /* 读取时错误，表示（通常）在 64 位平台上
     * 写入的索引或维度超过了 2^32，而我们正尝试在
     * 32 位平台上读取它。 */
    mat_FILE_FORMAT_VIOLATION,
    /* 读取时错误，表示 MAT 文件内部的某些数据或结构
     * 损坏——损坏或写入不当。 */
    mat_FAIL_TO_IDENTIFY,
    /* 读取时错误，表示文件内容与
     * 已知 MAT 文件类型不匹配。 */
    mat_BAD_ARGUMENT,
    /* 传递给 MAT API 的数据不利 */
    mat_OUTPUT_BAD_DATA,
    /* 写入时错误，表示 mxArray 中包含
     * 不适合写入的内容。 */
    mat_FULL_OBJECT_OUTPUT_CONVERT,
    /* 写入时错误，表示将（不透明或
     * 双精度）转换为可保存格式失败。在这种情况下，对象是
     * 变量的值，该变量将不会被设置。 */
    mat_PART_OBJECT_OUTPUT_CONVERT,
    /* 写入时错误，表示将（不透明或
     * 双精度）转换为可保存格式失败。在这种情况下，对象
     * 是变量的字段或元素，且该变量
     * 将带有该字段或元素中的空值保存。 */
    mat_FULL_OBJECT_INPUT_CONVERT,
    /* 读取时错误，表示将可保存数据
     * 转换为对象（不透明或双精度）失败。在这种情况下，对象
     * 是变量的值，且该变量未加载。 */
    mat_OBJECT_INPUT_CONVERT,
    /* 读取时错误，表示将可保存数据
     * 转换为对象（不透明或双精度）失败。在这种情况下，对象
     * 是变量的字段或元素的值，该变量
     * 将带有该字段或元素中的条目进行加载。 */
    mat_NOT_SUPPORTED
    /* 错误，表示特定的 MAT API 操作
     * 不支持此类 MAT 文件。 */
} matError;
```

从 Python 3.7 版本开始，`async` 是一个关键字，不能作为 `matlab.engine.start_matlab` 的参数。对于“按发布版本的 MATLAB 产品兼容 Python 版本”列出的所有支持的 Python 版本，请使用 `background` 参数。

## 另请参阅

```matlab
matlab.engine.find_matlab | matlab.engine.MatlabEngine
```

## 主题

- "将 MATLAB 连接到运行中的 MATLAB 会话"
- "从 Python 调用 MATLAB"

## matlab.engine.find_matlab

查找共享的 MATLAB 会话以连接到 Python 的 MATLAB Engine

### 语法

```python
names = matlab.engine.find_matlab()
```

## 描述

`names = matlab.engine.find_matlab()` 查找本地机器上所有共享的 MATLAB 会话，并以元组形式返回它们的名称。`names` 中的任何名称都可以作为 `matlab.engine.connect_matlab` 的输入参数。如果本地机器上没有运行的共享会话，`matlab.engine.find_matlab` 返回一个空元组。

## 示例

#### 查找共享的 MATLAB 会话

识别本地机器上运行的共享 MATLAB 会话并连接到其中一个。

```python
import matlab.engine
names = matlab.engine.find_matlab()
names
('MATLAB_6830', 'MATLAB_7090')
```

有两个正在运行的共享 MATLAB 会话，`matlab.engine.find_matlab` 在元组中返回两个名称。

连接到第一个共享 MATLAB 会话。

```python
eng = matlab.engine.connect_matlab('MATLAB_6830')
```

## 版本历史

在 R2015b 中引入

## 另请参阅

`matlab.engine.connect_matlab`

## 主题

- 将 Python 连接到运行中的 MATLAB 会话
- 从 Python 调用 MATLAB

## matlab.engine.FutureResult 类

**包：** `matlab.engine`

存储在 Python 对象中的对 MATLAB 函数异步调用的结果

## 描述

`FutureResult` 类将对 MATLAB 函数的异步调用的结果存储在 Python 对象中。

## 创建

当异步调用 MATLAB 函数时，MATLAB Engine for Python 会创建一个 `FutureResult` 对象。不需要调用 `matlab.engine.FutureResult()` 来创建你自己的 `FutureResult` 对象。

### 方法

## 公共方法

- `cancel` | 从 Python 取消对 MATLAB 函数的异步调用
- `cancelled` | 从 Python 调用 MATLAB 函数的异步调用完成状态
- `done` | 从 Python 调用 MATLAB 函数的异步调用结果

## 异常

- `SyntaxError` | Python 异常，函数调用中的语法错误
- `TypeError` | Python 异常，不支持输出的数据类型
- `matlab.engine.CancelledError` | MATLAB 引擎无法取消函数调用
- `matlab.engine.InterruptedError` | 函数被中断
- `matlab.engine.MatlabExecutionError` | 函数执行失败
- `matlab.engine.RejectedExecutionError` | 引擎终止
- `matlab.engine.TimeoutError` | 无法在超时时间内返回结果

## 示例

#### 从 Python 获取异步 MATLAB 用的结果

从 Python 调用 MATLAB `sqrt` 函数。将 `background` 设置为 `True` 以使函数调用异步进行。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
future = eng.sqrt(4.0, background=True)
ret = future.result()
print(ret)
```

2.0

## 版本历史

在 R2014b 中引入

## 另请参阅

`matlab.engine.MatlabEngine`

## 主题

- "从 Python 调用 MATLAB 函数"
- "从 Python 异步调用 MATLAB 函数"

## cancel

**类：** `matlab.engine.FutureResult`

**包：** `matlab.engine`

从 Python 取消对 MATLAB 函数的异步调用

### 语法

```python
tf = FutureResult.cancel()
```

## 描述

`tf = FutureResult.cancel()` 从 Python 异步取消对 MATLAB 函数的调用。如果 `FutureResult.cancel()` 成功取消了函数，则返回 `True`；如果无法取消函数，则返回 `False`。

### 输出参数

- `tf` — 取消状态

以 `True` 或 `False` 返回取消状态。如果 `FutureResult.cancel()` 成功取消了异步调用，状态 `tf` 为 `True`，否则为 `False`。

## 示例

#### 取消异步调用

在 MATLAB 中通过异步调用 `eval` 函数启动一个无限循环。然后取消它。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
ret = eng.eval("while 1; end", nargout=0, background=True)
tf = ret.cancel()
print(tf)
True
```

## 另请参阅

## cancelled

**类：** `matlab.engine.FutureResult`

**包：** `matlab.engine`

从 Python 调用对 MATLAB 函数的异步调用的取消状态

### 语法

```python
tf = FutureResult.cancelled()
```

## 描述

`tf = FutureResult.cancelled()` 返回从 Python 异步调用 MATLAB 函数的调用的取消状态。如果之前的 `FutureResult.cancel()` 调用成功，则返回 `True`，否则返回 `False`。

### 输出参数

**tf — 取消状态**

`True` | `False`

异步函数调用的取消状态，以 `True` 或 `False` 返回。

## 示例

#### 检查异步调用的取消状态

在 MATLAB 中通过异步调用 `eval` 函数启动一个无限循环。取消它并检测到引擎已停止循环。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
ret = eng.eval("while 1; end", nargout=0, background=True)
tf = ret.cancel()
print(tf)
True
```

## 另请参阅

## done

**类：** `matlab.engine.FutureResult`

**包：** `matlab.engine`

从 Python 调用对 MATLAB 函数的异步调用的完成状态

### 语法

```python
tf = FutureResult.done()
```

## 描述

`tf = FutureResult.done()` 返回从 Python 异步调用 MATLAB 函数的调用的完成状态。如果函数已完成，则返回 `True`，否则返回 `False`。

### 输出参数

**tf — 完成状态**

异步函数调用的完成状态，以 `True` 或 `False` 返回。

## 示例

#### 检查异步调用是否完成

在 MATLAB 中通过 `background=True` 调用 `sqrt` 函数。检查函数调用是否已完成。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
ret = eng.sqrt(4.0, background=True)
tf = ret.done()
print(tf)
True
```

当 `ret.done()` 返回 `True` 时，你可以调用 `ret.result()` 获取结果。

## 另请参阅

## result

**类：** `matlab.engine.FutureResult`

**包：** `matlab.engine`

从 Python 调用 MATLAB 函数异步调用的结果

### 语法

```python
ret = FutureResult.result(timeout=None)
```

## 描述



`ret = FutureResult.result(timeout=None)` 返回从 Python 异步调用 MATLAB 函数的结果。

### 输入参数

- **timeout** — 等待秒数

  `None`（默认） | `float`

  以秒为单位的超时，用于等待函数调用。如果 `timeout = None`，`FutureResult.result()` 将等待函数完成。

### 输出参数

- **ret** — 调用的结果

  Python 对象

  异步调用的结果，以 Python 对象形式返回，即实际输出。

## 示例

#### 从 Python 获取异步 MATLAB 调用的输出

从 Python 调用 MATLAB `sqrt` 函数。将 `background` 设置为 `True`。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
future = eng.sqrt(4.0, background=True)
ret = future.result()
print(ret)
```

```
2.0
```

# 另请参阅

## `matlab.engine.MatlabEngine`

**包：** `matlab.engine`

在 Python 会话中使用 MATLAB 作为引擎的 Python 对象。

## 描述

`MatlabEngine` 类使用 MATLAB 进程作为 Python 的计算引擎。你可以作为 `MatlabEngine` 对象的方法调用 MATLAB 函数，因为这些函数在调用它们时是动态调用的。你可以调用定义的函数和脚本。你可以向与 `MatlabEngine` 对象关联的工作区发送数据并检索数据。

## 创建

`matlab.engine.start_matlab` 方法每次调用时都会创建一个 `MatlabEngine` 对象。不需要调用 `matlab.engine.MatlabEngine()` 来创建自己的 `MatlabEngine` 对象。

## 属性

| 属性 | 描述 |
| --- | --- |
| `workspace` | 包含 MATLAB 变量引用的 Python 字典。可以通过 `workspace` 向 MATLAB 变量赋值。每个 MATLAB 变量名称成为字典的键。`workspace` 中的键必须是有效的 MATLAB 标识符（例如，不能使用数字键）。 |

## 方法

## 公共方法

`matlab.engine.MatlabEngine` 类提供这些方法。

- `matlab.engine.start_matlab` — 启动 MATLAB
- `matlab.engine.find_matlab` — 查找共享的 MATLAB 会话以连接到 Python 的 MATLAB Engine
- `matlab.engine.connect_matlab` — 连接共享 MATLAB 会话

#### 特殊运算符和函数

你可以作为 `MatlabEngine` 对象的方法调用任何 MATLAB 函数。引擎在你调用它时动态调用 MATLAB 函数。语法支持函数调用的位置参数、关键字参数和输出参数。

```python
ret = MatlabEngine.matlabfunc(*args, nargout=1, background=False, stdout=sys.stdout, stderr=sys.stderr)
```

将 `matlabfunc` 替换为任何 MATLAB 函数名称（例如 `isprime` 或 `sqrt`）。将 `args` 替换为 MATLAB 函数调用的输入参数。关键字参数指定：

- 函数返回的输出参数数量
- 引擎是否异步调用该函数
- 仅当所指定的值与语法中显示的默认值不同时，引擎向何处发送标准输出和标准错误。

仅当指定的值与语法中显示的默认值不同时才指定关键字参数。

## MATLAB 函数的输入参数

| 参数 | 描述 | Python 类型 |
| --- | --- | --- |
| `*args` | MATLAB 函数的输入参数，以位置参数的形式指定 | 引擎可以转换为 MATLAB 类型的任何 Python 类型 |

## 引擎的关键字参数

| 参数 | 描述 | Python 类型 |
| --- | --- | --- |
| `nargout` | MATLAB 函数的输出参数数量 | `int` **默认值: 1** |
| `background` | 异步后台调用 MATLAB 函数的标志，是 `async` 的别名。然而，从 Python 3.7 版本开始，`async` 是关键字，不能作为参数使用。对于所有支持的 Python 版本，请使用 `background` 参数代替 `async`。 | `bool` **默认值: False** |
| `stdout` | 标准输出 | `StringIO.StringIO` 对象 (Python 2.7) / `io.StringIO` 对象 (Python 3.x) **默认值: sys.stdout** |
| `stderr` | 标准错误 | `StringIO.StringIO` 对象 (Python 2.7) / `io.StringIO` 对象 (Python 3.x) **默认值: sys.stderr** |

## 输出参数

| 输出类型 | 描述 | 要求的关键字参数 |
| --- | --- | --- |
| Python 变量 | MATLAB 函数的一个输出参数 | 默认值 |
| `tuple` | MATLAB 函数的多个输出参数 | `nargout=n`（其中 `n > 1`） |
| `None` | MATLAB 函数无输出参数 | `nargout=0` |
| `FutureResult` 对象 | 异步调用 MATLAB 函数输出参数的占位符 | `background=True` |

## 异常

| 异常 | 描述 |
| --- | --- |
| `MatlabExecutionError` | 函数执行失败 |
| `RejectedExecutionError` | MATLAB 引擎终止 |
| `SyntaxError` | 函数调用中的语法错误 |
| `TypeError` | 输入或输出参数的数据类型不受支持 |

## 示例

### 从 Python 调用 MATLAB 函数

使用引擎从 Python 调用 MATLAB 的 `sqrt` 函数。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
ret = eng.sqrt(4.0)
print(ret)
```

```
2.0
```

### 将数组放入 MATLAB 工作空间

在 Python 中创建一个数组并将其放入 MATLAB 工作空间中。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
px = eng.linspace(0.0, 6.28, 1000)
```

`px` 是一个 MATLAB 数组，但 `eng.linspace` 将其返回了 Python。若要在 MATLAB 中使用它，请将数组放入 MATLAB 工作空间。

```python
eng.workspace['mx'] = px
```

当你向引擎工作空间字典添加条目时，你也就创建了一个 MATLAB 变量。引擎会将数据转换为 MATLAB 数据类型。

### 从 MATLAB 工作空间获取数据

从 MATLAB 工作空间获取 `pi` 并将其复制到 Python 变量。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
eng.eval('a = pi;', nargout=0)
pi_val = eng.workspace['a']
print(pi_val)
```

```
3.14159265359
```

## 版本历史

在 R2014b 中引入。

## 另见

`matlab.engine.start_matlab` | `matlab.engine.connect_matlab` | `matlab.engine.find_matlab` | `matlab.engine.FutureResult`

## 主题

- "从 Python 调用 MATLAB 函数"
- "从 Python 异步调用 MATLAB 函数"
- "重定向标准输出和错误"
- "从 Python 调用 MATLAB"

## `matlab.engine.start_matlab`

启动 MATLAB 引擎。

## 语法

```python
eng = matlab.engine.start_matlab()
eng = matlab.engine.start_matlab(option)
eng = matlab.engine.start_matlab(background)
```

## 描述

`eng = matlab.engine.start_matlab()` 启动一个新的 MATLAB 进程，返回一个与 MATLAB 通信的 `MatlabEngine` 对象。

`eng = matlab.engine.start_matlab(option)` 启动一个新的 MATLAB 进程，返回一个与 MATLAB 通信的 `MatlabEngine` 对象。引擎支持除“限制”中列出的所有启动选项。

`eng = matlab.engine.start_matlab(background)` 如果 `background` 为 `True` 则异步启动 MATLAB。

## 示例

### 从 Python 启动 MATLAB

使用引擎从 Python 调用 MATLAB `sqrt` 函数。

```python
import matlab.engine
eng = matlab.engine.start_matlab()
```

### 启动多个引擎

启动不同的引擎。

```python
import matlab.engine
eng1 = matlab.engine.start_matlab()
eng2 = matlab.engine.start_matlab()
```

### 带界面的启动

带界面的启动引擎。

```python
import matlab.engine
eng = matlab.engine.start_matlab("-desktop")
```

### 异步启动引擎

使用 `background=True` 启动引擎。

```python
import matlab.engine
future = matlab.engine.start_matlab(background=True)
eng = future.result()
```

## 输入参数

- **option** — MATLAB 的启动选项

  `'-desktop'` (默认值) | `string`

  以字符串形式指定的 MATLAB 进程启动选项。你可以指定多个启动选项。引擎支持“限制”中列出的所有启动选项。选项列表参见特定平台的命令 `matlab` (Windows)、`matlab` (macOS) 或 `matlab` (Linux)。要启动带界面的 MATLAB，请使用 `'-desktop'` 选项。

- **background** — 同步或异步启动

  `False` (默认值) | `logical`

  以关键字参数指定的同步或异步启动。`background` 是 `async` 的别名。

- **async** — 同步或异步启动

  `False` (默认值) | `logical`

  以关键字参数指定的同步或异步启动。不建议。请使用 `background` 参数。更多信息请参见“兼容性考虑”。

## 输出参数

- **eng** — 与 MATLAB 通信的 Python 变量

  `MatlabEngine` 对象 | `FutureResult` 对象

  与 MATLAB 通信的 Python 变量，如果 `async` 或 `background` 设置为 `False`，返回 `MatlabEngine` 对象；如果 `async` 或 `background` 设置为 `True`，返回 `FutureResult` 对象。

## 限制

引擎不支持这些 MATLAB 启动选项：

- `-h`
- `-help`
- `?`
- `-n`
- `-e`
- `-softwareopengl`
- `-logfile`
- "指定启动选项"
- "常用启动选项"
- "从 Python 运行 MATLAB"

# `matOpen` (C 和 Fortran)

打开 MAT-文件。

# C 语法

```c
#include "mat.h"
MATFile *matOpen(const char *filename, const char *mode);
```

# Fortran 语法

```fortran
#include "mat.h"
mwPointer matOpen(filename, mode)
character*(*) filename, mode
```

## 参数

- **filename** — 要打开的文件名
- **mode** — 文件打开模式。下表列出了 `mode` 的有效值。

| 模式 | 描述 |
| --- | --- |
| `r` | 仅以读模式打开文件；通过检查文件确定 MAT-file 的当前版本并保留当前版本。 |
| `u` | 以更新模式打开文件，同时进行读写。如果文件不存在，则不创建文件（相当于 `fopen` 的 `r+` 模式）。通过检查文件确定 MAT-file 的当前版本并保留当前版本。 |
| `w` | 仅以写模式打开文件；如果有之前的内容，则将其删除。 |
| `w4` | 创建与 MATLAB 版本 4 软件及更早兼容的 MAT-file。 |
| `w6` | 创建与 MATLAB 版本 5 (R8) 软件及更早兼容的 MAT-file。相当于 `w7` 模式。 |
| `w7` | 创建与 MATLAB 版本 7.0 (R14) 软件及更早兼容的 MAT-file。相当于 `wz` 模式。 |
| `w2` | 打开文件写入压缩数据。默认情况下，MATLAB `save` 函数在工作区变量保存到 MAT-file 时会压缩。使用 `matOpen` 函数创建 MAT-file 时使用相同的压缩率，请使用 `w2` 选项。相当于 `w7` 模式。 |
| `wH5` | 创建基于 HDF5 格式的 MAT-file，可以存储超过 2 GB 的对象。 |

## 返回

文件句柄；如果打开失败，C 中返回 `NULL`（Fortran 中返回 `0`）。

## 描述

此例程用于读写打开 MAT-file。

## 示例

查看 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matcreat.c`
- `matdgns.c`
- `matdemo1.F`
- `matdemo2.F`

## 另请参阅

`matClose`, `save`

## 版本历史

在 R2006a 之前引入。

# `matPutVariable` (C 和 Fortran)

将数组写入 MAT-file。

# C 语法

```c
#include "mat.h"
int matPutVariable(MATFile *mfp, const char *name, const mxArray *pm);
```

# Fortran 语法

```fortran
#include "mat.h"
integer*4 matPutVariable(mfp, name, pm)
mwPointer mfp, pm
character*(*) name
```

## 参数

- **mfp** — 指向 MAT-file 信息的指针
- **name** — 要放入 MAT-file 的 `mxArray` 名称
- **pm** — `mxArray` 指针

## 返回

成功时返回 `0`，发生错误时返回非零值。在 C 中，使用标准库中的 `feof` 和 `ferror` 配合 `matGetfp` 来确定状态。要解释 `matPutVariable` 返回的错误代码，请调用 `matGetErrno`。

## 描述

此例程将一个 `mxArray` 放入 MAT-file。

`matPutVariable` 将 `mxArray` `pm` 写入 MAT-file `mfp`。如果文件中不存在该 `mxArray`，函数将其附加到末尾。如果文件中存在同名的 `mxArray`，该函数将通过重写文件用新 `mxArray` 替换现有 `mxArray`。

不要使用 MATLAB 函数名作为变量名。与函数名冲突的常见变量名包括 `i`, `j`, `mode`, `char`, `size` 或 `path`。要确定特定名称是否与 MATLAB 函数相关，请使用 `which` 函数。

新 `mxArray` 的大小可以与现有 `mxArray` 不同。

## 示例

查看 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matcreat.c`
- `matdemo1.F`

## 版本历史

在 R2006a 之前引入。

## 另请参阅

`matGetErrno`, `matGetfp`

# `matPutVariableAsGlobal` (C 和 Fortran)

将数组作为全局变量写入 MAT-file。

# C 语法

```c
#include "mat.h"
int matPutVariableAsGlobal(MATFile *mfp, const char *name, const mxArray *pm);
```

# Fortran 语法

```fortran
#include "mat.h"
integer*4 matPutVariableAsGlobal(mfp, name, pm)
mwPointer mfp, pm
character*(*) name
```

## 参数

- **mfp** — 指向 MAT-file 的指针
- **name** — 要放入 MAT-file 的 `mxArray` 名称
- **pm** — `mxArray` 指针

## 返回



成功时返回 0，发生错误时返回非零值。在 C 中，使用标准库中的 `feof` 和 `error` 配合 `matGetfp` 来确定状态。

## 描述

此例程将一个 `mxArray` 放入 MAT-file。

`matPutVariableAsGlobal` 将 `mxArray pm` 写入 MAT-file `mfp`。如果文件中不存在该 `mxArray`，函数将其附加到末尾。如果文件中存在同名的 `mxArray`，该函数将通过重写文件用新 `mxArray` 替换现有 `mxArray`。

不要使用 MATLAB 函数名作为变量名。与函数名冲突的常见变量名包括 `i`, `j`, `mode`, `char`, `size` 或 `path`。要确定特定名称是否与 MATLAB 函数相关，请使用 `which` 函数。

新 `mxArray` 的大小可以与现有 `mxArray` 不同。

## 示例

查看 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matcreat.c`
- `matdemol.F`

## 版本历史

在 R2006a 之前引入

## 另需查看

`matPutVariable`, `matGetfp`

# mexAtExit (C 和 Fortran)

清理 MATLAB 时调用的函数

## C 语法

```c
#include "mat.h"
int mexAtExit(void (*ExitFcn)(void));
```

## Fortran 语法

```fortran
#include "mat.h"
integer*4 mexAtExit(ExitFcn)
```

## 描述

在清理 MATLAB 之前注册一个函数。

每个 MEX 函数只能注册一个活动函数。如果 MEX 函数被锁定，则无法清理。因此，如果你尝试清理锁定的 MEX 文件，MATLAB 不会调用 `ExitFcn`。

在 Fortran 中，在文件作用内声明 `ExitFcn` 为外部函数（`external`）。

> **警告** 在 C 文件中，在 `ExitFcn` 中抛出异常会导致 MATLAB 崩溃。

## 参数

**ExitFcn** — 运行的函数

`void *`

## 输出

**Res** — 返回代码

始终返回 0

## 示例

查看 `matlabroot/extern/examples/mex` 中的示例：

- `mexatexit.c`

## 另需查看

`mexLock`, `mexUnlock`

## 版本历史

在 R2006a 之前引入

# mexCallMATLAB (C)

调用 MATLAB 函数、用户定义函数或 MEX 函数

## C 语法

```c
#include "mat.h"
int mexCallMATLAB(int nlhs, mxArray *plhs[], int nrhs, mxArray *prhs[], const char *functionName);
```

## 描述

**注意** 使用现代 C++ 特性和“MATLAB Data API for C++”编写 MEX 函数请参考“Write C++ Callable from MATLAB”。

使用 `mexCallMATLAB` 调用内部 MATLAB 数学函数、运算符、用户定义函数或其他 MEX 函数。

`mexCallMATLAB` 和 `mexEvalString` 都执行 MATLAB 命令。`mexCallMATLAB` 将结果（左侧参数）返回给 MEX 函数。`mexEvalString` 函数不向 MEX 函数返回值。

## 输入参数

**nlhs — 输出参数数量**

`int`

预期输出 `mxArray` 的数量，指定为小于或等于 50 的整数。

**plhs — MATLAB 数组**

`mxArray*`

指向输出 `mxArray` 的指针数组。

> **警告** `mexCallMATLAB` 的 `plhs` 参数与 `mexFunction` 的 `plhs` 不同。不要销毁 `mexFunction plhs` 中返回的 `mxArray`。

**nrhs — 输入参数数量**

`int`

输入 `mxArray` 的数量，指定为小于或等于 50 的整数。

**prhs — MATLAB 数组**

`mxArray*`

指向输入 `mxArray` 的指针数组。

**functionName — MATLAB 函数名**

`const char*`

要调用的 MATLAB 内置函数、用户定义函数、操作符或 MEX 函数名，指定为 `const char*`。

如果 `functionName` 是操作符，请将操作符放在双引号内，例如 `"+"`。

## 输出参数

**Status — 状态**

`int`

如果成功则返回 0，如果失败则返回非零值。

## 错误处理

如果 `functionName` 检测到错误，MATLAB 将终止 MEX 函数并将控制权交给 MATLAB 提示符。要捕获错误，请使用 `mexCallMATLABWithTrap` 函数。

## 局限性

- *避免在 Simulink® S-functions 中使用 `mexCallMATLAB` 函数。如果确实使用，请勿将生成的 `mxArray` 指针存储在 MEX 函数执行结束后持续存在的 S-function 块状态中。`mexCallMATLAB` 的输出具有临时范围，并在 MEX 函数调用结束时自动销毁。*

- 使用 `mexCallMATLAB` 生成类型为 `mxUNKNOWN_CLASS` 的对象。例如，此函数返回两个变量，但只为其中一个赋值。

```c
function [a,b] = foo(c)
a = 2*c;
```

如果你使用 `mexCallMATLAB` 调用 `foo`，则未赋值的输出变量现在的类型为 `mxUNKNOWN_CLASS`。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexcallmatlab.c`
- `mexevalstring.c`
- `mexcallmatlabwithtrap.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.c`
- `mxcreatecellmatrix.c`
- `mxisclass.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

## 提示

- MATLAB 分配动态内存来存储 `mexCallMATLAB` 在 `plhs` 中使用的数组。MATLAB 在你退出 MEX 函数时会自动释放这些动态内存。然而，如果堆空间紧张，请在完成 `plhs` 中数组的操作后调用 `mxDestroyArray`。

## 版本历史

在 R2006a 之前引入

## 另见

`feval` | `mexFunction` | `mexCallMATLABWithTrap` | `mexEvalString` | `mxDestroyArray`

# mexCallMATLAB (Fortran)

调用 MATLAB 函数、用户定义函数或 MEX 文件

## Fortran 语法

```fortran
#include "fintrf.h"
integer4 mexCallMATLAB(nlhs, plhs, nrhs, prhs, functionName)
integer4 nlhs, nrhs
mwPointer plhs(*), prhs(*)
character(*) functionName
```

## 参数

**nlhs**

输出参数的数量。必须小于或等于 50。

**plhs**

指向输出参数的指针数组

> **注意事项**：`mexCallMATLAB` 的 `plhs` 参数与 `mexFunction` 的 `plhs` 不同。不要销毁 `mexFunction` 在 `plhs` 返回的 `mxArray`。

**nrhs**

输入参数的数量。必须小于或等于 50。

**prhs**

指向输入参数的指针数组

**functionName**

包含要调用的 MATLAB 内置函数、操作符、用户定义函数或 MEX 函数名的字符串。

如果 `functionName` 是操作符，请将操作符放在单引号内，例如 `'+'`。

## 返回

成功则返回 0，失败则返回非零值。

## 描述

使用 `mexCallMATLAB` 调用内部 MATLAB 数值函数、MATLAB 操作符、用户定义函数或其他 MEX 文件。`mexCallMATLAB` 和 `mexEvalString` 都会执行 MATLAB 命令。使用 `mexCallMATLAB` 将结果（左侧参数）返回 MEX 函数。`mexEvalString` 函数不向 MEX 函数返回值。

有关传递给 `functionName` 的输入输出参数的完整描述，请参见 `mexFunction`。

## 错误处理

如果 `functionName` 检测到错误，MATLAB 将终止 MEX 文件并将控制权交给 MATLAB 提示符。要捕获错误，请使用 `mexCallMATLABWithTrap` 函数。

## 局限性

- *避免在 Simulink S-functions 中使用 `mexCallMATLAB` 函数。如果确实使用，请勿将生成的 `plhs mxArray` 指针存储在 MEX 函数执行结束后持续存在的 S-block 状态中。`mexCallMATLAB` 的输出具有临时范围，并在 MEX 函数结束时自动销毁。*

- 使用 `mexCallMATLAB` 生成类型为 `mxUNKNOWN_CLASS` 的对象。例如，此函数返回两个变量，但只为其中一个赋值。

```c
function [a,b] = foo(c)
a = 2*c;
```

如果你使用 `mexCallMATLAB` 调用 `foo`，则未赋值的输出变量现在的类型为 `mxUNKNOWN_CLASS`。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.F`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcreatecellmatrixf.F`

## 提示

- MATLAB 分配动态内存来存储 `mexCallMATLAB` 在 `plhs` 中使用的数组。MATLAB 在你退出 MEX 文件时会自动释放这些动态内存。然而，如果堆空间紧张，请在完成 `plhs` 中数组的操作后调用 `mexDestroyArray`。

## 版本历史

在 R2006a 之前引入

## 另见

`mexFunction` | `mexCallMATLABWithTrap` | `mexEvalString` | `mxDestroyArray`

# mexCallMATLABWithTrap (C 和 Fortran)

调用 MATLAB 函数、用户定义函数或 MEX 文件并捕获错误

## C 语法

```c
#include "mex.h"
mxArray* mexCallMATLABWithTrap(int nlhs, mxArray *plhs[], int nrhs, mxArray *prhs[], const char *functionName);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mexCallMATLABWithTrap(nlhs, plhs, nrhs, prhs, functionName)
integer4 nlhs, nrhs
mwPointer plhs(*), prhs(*)
character(*) functionName
```

## 描述

`mexCallMATLABWithTrap` 函数的功能与 `mexCallMATLAB` 相同。如果 MATLAB 检测到错误，它将终止 MEX 文件并将控制权交给 MATLAB 提示符。

## 输入参数

**nlhs**

输出参数的数量。必须小于或等于 50。

**plhs**

指向输出参数的指针数组

> **注意事项**：`mexCallMATLABWithTrap` 的 `plhs` 参数与 `mexFunction` 的 `plhs` 不同。不要销毁 `mexFunction` 返回的 `mxArray`。

**nrhs**

输入参数的数量。必须小于或等于 50。

**prhs**

指向输入参数的指针数组

**functionName — MATLAB 函数名**

`const char*`

要调用的 MATLAB 内置函数、用户定义函数或 MEX 函数名，指定为 `const char*`。

如果 `functionName` 是操作符，请将操作符放在单引号内，例如 `'+'`。

## 输出参数

**ME — 异常**

`mxArray*` | `mwPointer`

如果没有发生错误则返回 NULL。否则，返回类型为 `MException` 的指针（C 为 `mxArray`，Fortran 为 `mwPointer`）。关于 `MException` 的信息，请参见“处理异常”。

## 版本历史

在 R2008b 中引入

## 另见

`mexCallMATLAB` | `MException`

## 话题

- 处理异常
- MEX 文件中临时数组的清理

# mexErrMsgIdTxt (C 和 Fortran)

带有标识符显示错误消息并返回 MATLAB 提示符

## C 语法

```c
#include "mex.h"
void mexErrMsgIdTxt(const char *errorid, const char *errormsg, ...);
```

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mexErrMsgIdTxt(errorid, errormsg)
      character(*) errorid, errormsg
```

## 参数

**errorid**

包含 MATLAB 标识符的字符串。创建标识符的信息请参见 `MException`。

**errormsg**

要显示的字符串，C 为 `const char*`，Fortran 为 `character(*)`。在 C 中，该函数支持 UTF-8 或本地代码页（LCP）编码，字符串可以包含 ANSI `printf` 函数指定的转换序列。消息文本和转换参数的编码必须一致。

在 C 中，消息中使用的任何参数。每个参数必须有对应的转换规范。请参考文档中的 `printf` 转换表。

## 描述

`mexErrMsgIdTxt` 函数将错误消息写入 MATLAB 窗口。更多信息请参见使用消息标识符的错误语法语句。打印错误消息后，MATLAB 将终止 MEX 文件并将控制权交给 MATLAB 提示符。

调用 `mexErrMsgIdTxt` 不清除 MEX 内存。因此，`mexErrMsgIdTxt` 不调用由 `mexExit` 注册的函数。

如果你的应用程序调用 `mxMalloc` 或一个 `mexCreate*` 例程来分配内存，`mexErrMsgIdTxt` 会自动释放已分配的内存。

> **注意** 如果在使用 `mexErrMsgIdTxt` 时收到警告，可能存在内存管理兼容性问题。更多信息请参见“内存管理问题”。

## 备注

除了 `errorid` 和 `errormsg` 之外，`mexErrMsgIdAndTxt` 函数还会确定错误发生的位置，并显示以下信息。例如，在函数 `foo` 中，`mexErrMsgIdAndTxt` 显示：

Error using foo

如果你使用 MinGW-w64 编译器编译 MEX 文件，请参阅“使用 MinGW-w64 编译 C/C++ MEX 文件的故障排除与限制”中的“异常处理限制”主题。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `arrayFillGetPr.c`
- `matrixDivide.c`
- `timestof.F`
- `xtimesy.F`

## 验证字符输入

以下代码段检查输入参数 `prhs[0]` 是否为字符串。如果不是，代码将显示警告。如果读取输入字符串时出错，代码将显示错误信息并终止 MEX 文件。

```c
char *buf;
int buflen;

// 初始化变量
if (mxIsChar(prhs[0])) {
    if (mxGetString(prhs[0], buf, buflen) == 0)
        fprintf("The input string is: %s\n", buf);
    else
        mexErrMsgIdAndTxt("MyProg:ConvertString", "Could not convert string data.");
        // 退出 MEX 文件
}
else
    mexWarnMsgIdAndTxt("MyProg:InputString", "Input should be a string to print properly.");
}

// 继续处理
```

## 版本历史

在 R2006 之前引入

## 添加 UTF-8 支持

`mexErrMsgIdAndTxt` 函数除了支持向兼容的 LCP 编码字符串外，还接受 UTF-8 编码数据。

## 参见

`mexWarnMsgIdAndTxt` | `error`

## 主题

- “类析构函数的内存考虑”
- “使用 MinGW-w64 编译 C/C++ MEX 文件的故障排除与限制”

# mexErrMsgTxt (C 和 Fortran)

显示错误信息并返回 MATLAB 提示符

**注意**：不建议使用 `mexErrMsgTxt`。请使用 `mexErrMsgIdAndTxt`。

## C 语法

```c
#include "mex.h"
void mexErrMsgTxt(const char *errormsg);
```

## Fortran 语法

```fortran
subroutine mexErrMsgTxt(errormsg)
character(*) errormsg
```

## 参数

**errormsg**

包含要显示的错误信息的字符串

## 描述



`mexErrMsgTxt` 将错误信息写入 MATLAB 窗口。打印错误信息后，MATLAB 会终止 MEX 文件并将控制权交还 MATLAB 提示符。

调用 `mexErrMsgTxt` 不会在内存中清除 MEX 文件。因此，`mexErrMsgTxt` 不调用通过 `mexAfterExit` 注册的函数。

如果你的应用程序调用 `mexCall` 或其中一个 `mexCreate*` 例程来分配内存，`mexErrMsgTxt` 会自动释放分配的内存。

# 备注

除了 `errormsg` 之外，`mexermsgtxt` 函数还会确定错误发生的位置，并显示以下信息。如果在函数 `foo` 中发生标记为“Print my error message”的错误，`mexermsgtxt` 显示：

```
Error using foo

Print my error message
```

# 参见

`mexErrMsgIdAndTxt`, `mexWarnMsgIdAndTxt`

# mexEvalString (C)

在调用者工作区中执行 MATLAB 命令

# C 语法

```c
#include "mex.h"
int mexEvalString(const char *command);
```

注意：若要使用现代 C++ 特性和“MATLAB Data API for C++”编写 MEX 函数，请参阅“从 MATLAB 编写 C++ 函数 (MEX 文件)”。

调用 `mexEvalString` 在调用者的工作区中调用 MATLAB 命令。

`mexEvalString` 和 `mexCallMATLAB` 都执行 MATLAB 命令。使用 `mexCallMATLAB` 返回值（左侧参数）。`mexEvalString` 函数不向 MEX 函数返回结果。

命令字符串中等号右侧出现的所有参数必须是调用者的变量。不要使用 MATLAB 函数名作为变量名。与函数名冲突的常见变量名包括 `i`, `j`, `mode`, `char`, `size` 或 `path`。要确定特定名称是否与 MATLAB 函数关联，请使用函数帮助（`help`）。如需了解更多信息，请参阅“变量名”。

# 输入参数

- MATLAB 命令名称

`const char*`

要执行的 MATLAB 命令名称，指定为 `const char*`。该函数支持 UTF-8 字符。

# 输出参数

- **Status — 状态**

`int`

函数成功时返回 0，如果发生错误则返回 1。

# 错误处理

如果命令检测到错误，MATLAB 将控制权交回 MEX 函数，`mexEvalString` 返回 1。要捕获错误，请使用 `mexEvalStringWithTrap` 函数。

## 示例

参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexevalstring.c`

## 版本历史

在 R2006a 之前引入

添加 UTF-8 支持

`mexEvalString` 函数除了支持向兼容的 LCP 编码字符串外，还接受 UTF-8 编码数据。

# 参见

`mexCallMATLAB` | `mexEvalStringWithTrap` | 第 1-139 页上的“eval”

# mexEvalString (Fortran)

在调用者工作区中执行 MATLAB 命令

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mexEvalString(command)
character*(*) command
```

## 参数

`command`

包含要执行的 MATLAB 命令的字符串

## 返回

成功返回 0，如果发生错误则返回 1。

## 描述

`mexEvalString` 和 `mexCallMATLAB` 都执行 MATLAB 命令。使用 `mexCallMATLAB` 返回值（左侧参数）。`mexEvalString` 函数不向 MEX 函数返回结果。

命令字符串中等号右侧出现的所有参数必须是调用者的变量。不要使用 MATLAB 函数名作为变量名。与函数名冲突的常见变量名包括 `i`, `j`, `mode`, `char`, `size` 或 `path`。要确定特定名称是否与 MATLAB 函数关联，请使用函数帮助（`help`）。如需了解更多信息，请参阅“变量名”。

# 错误处理

如果命令检测到错误，MATLAB 将控制权交回 MEX 函数，`mexEvalString` 返回 1。要捕获错误，请使用 `mexEvalStringWithTrap` 函数。

## 版本历史

在 R2006 之前引入

# 参见

`mexCallMATLAB` | `mexEvalString`

# mexStringWithTrap (C 和 Fortran)

在调用者工作区中执行 MATLAB 命令并捕获错误

# C 语法

```c
#include "mex.h"
mxArray *mexStringWithTrap(const char *command);
```

# Fortran 语法

```fortran
#include "fintrf.h"
void mexStringWithTrap(command)
character(*) command
```

## 描述

`mexStringWithTrap` 功能与 `mexEvalString` 相同，但如果 MATLAB 检测到错误，它会将控制权交回 MEX 文件。

# 输入参数

- command — MATLAB 命令名称

`const char*`

要执行的 MATLAB 命令名称，指定为 `const char*`。该函数支持 UTF-8 字符。

# 输出参数

- ME — 异常

`mxArray*`

如果没有发生错误则返回 NULL。否则返回异常的指针。有关异常的信息，请参阅“响应异常”。

## 版本历史

在 R2006 之前引入

添加 UTF-8 支持

该函数除了支持向兼容的 LCP 编码字符串外，还接受 UTF-8 编码数据。

# 参见

`mexEvalString` | `MException`

# mexFunction (C)

使用 C API 构建的 C MEX 函数的入口

# C 语法

```c
#include "mex.h"
void mexFunction(int nlhs, mxArray *plhs[], int nrhs,
    const mxArray *prhs[])
```

## 描述

若要使用现代 C++ 特性和“MATLAB Data API for C++”编写 MEX 函数，请参阅“从 MATLAB 编写 C++ 函数 (MEX 文件)”。

`mexFunction` 不是一个例程。相反，`mexFunction` 是每个 MEX 函数所需的网关名称。当你调用 MEX 函数时，MATLAB 会找到并加载同名的 MEX 函数。MATLAB 在 MEX 函数内部搜索名为 `mexFunction` 的符号。如果找到，则使用 `mexFunction` 符号的地址调用 MEX 函数。如果在 MEX 函数内部找不到名为 `mexFunction` 的例程，MATLAB 将显示错误信息。

当你调用 MEX 函数时，MATLAB 会用调用参数填充 `nlhs`, `plhs`, `nrhs` 和 `prhs`。在 MATLAB 语言语法中，函数的通用形式为：

```
[a,b,c,...] = fun(d,e,f,...).
```

其中 ... 表示更多相同格式的项目。`a,b,c...` 是左侧输出参数，`d,e,f...` 是右侧输入参数。参数 `nlhs` 和 `nrhs` 左右参数的数量。`prhs` 是长度为 `nrhs` 的 `mxArray` 数组。`plhs` 是长度为 `nlhs` 的数组，你必须在其中为输出 `mxArrays` 设置指针。

> 即使 `nlhs = 0`，也可以返回输出值，这对应于在 `ans` 变量中返回结果。

要实验传递输入参数，请按照“MEX 函数源代码示例表”中的说明构建 `mexFunction.c` 示例。

# 输入参数

- nlhs — 输出参数数量

`int`

预期的 `mxArray` 输出参数数量，指定为整数。

- plhs — MATLAB 数组

`mxArray*`

指向预期的 Array 输出参数的指针数组。

- **nrhs — 输入参数个数**

`int`

输入 `mxArray` 的数量，以整数形式指定。

- **prhs — MATLAB 数组**

`const mxArray*`

指向 `mxArray` 输入参数的指针数组。不要在您的 MEX 文件中修改任何 `prhs` 值。更改这些只读 `mxArray` 中的数据可能会产生意外的副作用。

## 示例

请参阅 `matlabroot/extern/examples/mex/` 中的这些示例：

- `mexfunction.c`

## 版本历史

在 R2006a 之前引入。

# 另请参

`matlab::mex::Function`

# 主题

- "C MEX 文件的组成部分"
- "编写从 MATLAB 调用的 C 函数 (MEX 文件)"
- "C 矩阵 API"

# mexFunction (Fortran)

Fortran MEX 函数的入口点

# Fortran 语法

```fortran
#include "fintrf.h"
subroutine mexFunction(nlhs, plhs, nrhs, prhs)
integer nlhs, nrhs
mwPointer plhs(*), prhs(*)
```

## 参数

`nlhs`

预期的输出 `mxArray` 数量

`plhs`

指向预期输出 `mxArray` 的指针数组

`nrhs`

输入 `mxArray` 的数量

`prhs`

指向输入 `mxArray` 的指针数组。不要在您的 MEX 文件中修改任何 `prhs` 值。更改这些只读 `mxArray` 中的数据可能会产生意外的副作用。

## 描述

`mexFunction` 不是一个调用。相反，`mexFunction` 是 Fortran 中每个 MEX 函数所需的网关子程序。更多信息请参见“C MEX 文件的组成部分”。当您调用 MEX 函数时，MATLAB 会查找并加载同名的函数。如果找到，它将使用地址调用该函数。如果在 MEX 函数内部找不到命名的 `mexFunction`，MATLAB 将显示错误消息。

当您调用 MEX 函数时，MATLAB 会用调用参数填充 `nlhs`、`plhs`、`nrhs` 和 `prhs`。在 MATLAB 语言语法中，函数具有：

```
[a,b,c...] = fun(d,e,f...)
```

其中 ... 表示更多项。`a,b,c...` 是左侧输出参数，`d,e,f...` 是右侧输入参数。参数 `nlhs` 和 `nrhs` 分别包含左侧和右侧参数的数量。`plhs` 是一个 `mxArray` 指针数组，其长度为 `nlhs`，您的函数必须为输出数组设置指针。如果 `nlhs = 0`，则可以返回空，这对应于在变量 `ans` 中返回结果。

## 示例

请参阅 `matlabroot/extern/examples/mex/` 中的这些示例：

- `mexFunction.F`

## 版本历史

在 R2006a 之前引入。

# 另请参

- "C MEX 文件的组成部分"
- "编写从 MATLAB 调用的 Fortran 函数 (MEX 文件)"
- "Fortran 矩阵 API"
- "Fortran MEX API"

# mexFunctionName (C 和 Fortran)

当前 MEX 函数的名称

# C 语法

```c
#include "mex.h"
const char *mexFunctionName(void);
```

# Fortran 语法

```fortran
#include "mxArray.h"
character(*) mexFunctionName()
```

## 描述

`mexFunctionName` 返回当前 MEX 函数的名称。

# 输出参数

fName — MEX 函数名称

`const char*` | `character(*)`

当前 MEX 函数名称，在 C 中返回为 `const char*`，在 Fortran 中返回为 `character(*)`。

## 示例

请参阅 `matlabroot/extern/examples/mex/` 中的这些示例：

- `mexarray.c`

## 版本历史

在 R2006a 之前引入。

# mexGet (C)

指定图形属性的值

注意不要使用 `mexGet`。请使用 `mxGetProperty`。

# C 语法

```c
#include "mex.h"
const mxArray *mexGet(double handle, const char *property);
```

## 参数

`handle`

指向特定图形对象的句柄

`property`

图形属性

## 返回

成功时，返回指定图形对象中指定属性的值。失败时返回 NULL。不要修改 `mexGet` 的返回参数。更改 `const`（只读）`mxArray` 中的数据可能会产生意外的副作用。

## 描述

调用 `mexGet` 获取特定图形对象的属性值。`mexGet` 是 MATLAB `get` 函数的 API 等等物。若要设置图形属性值，请调用 `mexSet`。

# 另请参

`mxGetProperty`, `mxSetProperty`

# mexGetVariable (C)

从指定工作区复制变量

# C 语法

```c
#include "mex.h"
mxArray *mexGetVariable(const char *workspace, const char *varname);
```

## 描述

若要使用现代 C++ 特性和“MATLAB Data API for C++” 编写 MEX 函数，请参见“从 MATLAB 编写 C++ 函数 (MEX 文件)”。

调用 `mexGetVariable` 获取指定变量的副本。返回的 `mxArray` 包含了变量在另一个工作区中的所有数据和特征。对返回的 `mxArray` 的修改不会影响工作区中的变量，除非您使用 `mexPutVariable` 将副本复制回工作区。

完成后，使用 `mxArray` 销毁由运行时创建的 `mxArray`。

# 输入参数

**workspace — 工作区**

`const char*`

`mexGetVariable` 在指定的 `workspace` 中搜索 `varname`，以 `const char*` 指定。可能的值为：

- `base`: 在基础工作区中搜索变量。
- `caller`: 在调用者工作区中搜索变量。
- `global`: 在全局工作区中搜索变量。

**varname — 变量名**

`const char*`

要复制的变量名称，以 `const char*` 指定。

# 输出参数

**var — 变量副本**

`mxArray`

以 `mxArray*` 指定的变量副本。失败时返回空。常见原因是工作区中没有该变量。该变量之前存在于工作区，但现在已删除。

## 示例

请参阅 `matlabroot/extern/examples/mex/` 中的这些示例：

- `mexarray.c`

## 版本历史

在 R2006a 之前引入。

# 另请参

`mexGetVariablePtr` | `mxPutVariable` | 1

# mexGetVariable (Fortran)

从指定工作区复制变量

# Fortran 语法

```fortran
#include "fintrf.h"
subroutine mexGetVariable(var, workspace, varname)
```

## 参数

`workspace`

`mexGetVariable` 在此处搜索 `varname`。可能的值为：

| | |
| :--- | :--- |
| `base` | 在基础工作区中搜索变量 |
| `caller` | 在调用者工作区中搜索变量 |
| `global` | 在全局工作区中搜索变量 |

`varname`

要复制的变量名称

## 返回

成功时返回变量。失败时返回空。常见原因是工作区中没有该变量。该变量之前存在于工作区，但现在已删除。

## 描述

调用 `mexGetVariable` 获取指定变量的副本。返回的 `mxArray` 包含了变量在另一个工作区中的所有数据和特征。对返回的 `mxArray` 的修改不会影响工作区中的变量，除非您使用 `mexPutVariable` 将副本复制回工作区。

完成后，使用 `mxArray` 销毁由运行时创建的 `mxArray`。

## 版本历史

在 R2006a 之前引入。

# 另请参

`mexGetVariablePtr` | `mxPutVariable` | `mxArray`

# mexGetVariablePtr (C 和 Fortran)

来自另一个工作区的只读指针

# C 语法

```c
#include "mex.h"
const mxArray *mexGetVariablePtr(const char *workspace, const char *varname);
```

# Fortran 语法

```fortran
#include <intrf.h>
mwPointer *mexGetVariablePtr(workspace, varname)
```

## 描述

调用 `mexGetVariablePtr` 将指定变量（`varname`）的只读指针获取到您的 MX 文件中。此命令用于检查 `mxArray` 的数据和特征。如果您想更改数据或特征，请使用 `mexGetVariable`（配合 `mexPutVariable`）。

如果您想检查数据或特征，由于调用者只需要数组的指针，`mexGetVariablePtr` 性能更好。

# 输入参数

workspace — 工作区名称

`const char*` | `character(*)`

希望 `mexGetVariablePtr` 搜索的工作区名称，在 C 中以 `const char*` 指定，在 Fortran 中以 `character(*)` 指定。可能的值为：

| | |
| :--- | :--- |
| `base` | 在基础工作区中搜索变量 |
| `caller` | 在调用者工作区中搜索变量 |
| `global` | 在全局工作区中搜索变量 |

varname — 变量名

`const char*` | `character(*)`



另一个工作区中的变量名称，在 C 中以 `const char*` 指定，在 Fortran 中以 `character(*)` 指定。

# 输出参数

`mxArray` — 指向 `mxArray` 的指针

`const mxArray*` | `mwPointer` | `NULL`

成功时返回指向 `mxArray` 的只读指针，在 C 中返回为 `const mxArray*`，在 Fortran 中返回为 `mwPointer`。失败时在 C 中返回 `NULL`，在 Fortran 中返回 `0`。

## 局限性

- 如果你在 Simulink S-functions 中使用此函数，不要将生成的 `plhs` `mxArray` 指针存储在任何在 MEX 函数结束后仍持续的 S-function 块状态中。此函数的输出具有临时作用域，并在 MEX 调用结束时自动销毁。

## 版本历史

引入于 R2006a 之前

## 另请查看

`mexGetVariable`

## mexIsLocked (C 和 Fortran)

确定 MEX 文件是否被锁定

## C 语法

```
#include "mex.h"
bool mexIsLocked(void);
```

## Fortran 语法

```
#include "intrf.h"
integer*4 mexIsLocked()
```

## 描述

调用 `mexIsLocked` 来确定 MEX 文件是否被锁定。默认情况下，MEX 文件是未锁定的，这意味着你可以随时清除 MEX 文件。

要解锁 MEX 文件，请调用 `mexUnlock`。

## 输出参数 — 状态

`res` — `bool` | `integer*4`

如果 MEX 文件被锁定，则返回 true（C 中为逻辑 1，Fortran 中为 `integer*4` 1）。如果文件未锁定，则返回 false（C 中为逻辑 0，Fortran 中为 `integer*4` 0）。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexlock.c`
- `mexlockf.F`

## 另请查看

`mexLock` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent` | `mexUnlock` | `clear`

## mexLock (C 和 Fortran)

防止从内存中清除 MEX 文件

## C 语法

```
#include "mex.h"
void mexLock(void);
```

## Fortran 语法

```
#include "intrf.h"
subroutine mexLock()
```

## 描述

默认情况下，MEX 文件是未锁定的，这意味着你可以随时清除它们。调用 `mexLock` 可以禁止清除 MEX 文件。

要解锁 MEX 文件，请调用 `mexUnlock`。不要使用 `munlock` 函数。

`mexLock` 会增加锁定计数。如果你调用 `mexLock` n 次，请调用 `mexUnlock` n 次来解锁你的 MEX 文件。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexlock.c`
- `mexlockf.f`

## 另请查看

`mexIsLocked`, `mexMakeArrayPersistent`, `mexMakeMemoryPersistent`, `mexUnlock`, `clear`

## mexMakeArrayPersistent (C 和 Fortran)

使数组在 MEX 文件完成后保持持久化

## C 语法

```
#include "mex.h"
void mexMakeArrayPersistent(mxArray *pm);
```

## Fortran 语法

```
#include "fintrf.h"
subroutine mexMakeArrayPersistent(pm)
mwPointer pm
```

默认情况下，通过 `mxCreate` 函数分配的 `mxArray` 不是持久的。MATLAB 内存管理机制会在 MEX 文件执行结束时自动释放非持久存的 `mxArray`。如果你希望 `mxArray` 在 MEX 函数的多次调用中保持持久化，请调用 `mexMakeArrayPersistent` 函数。

> **警告** 不要将使用 `mexMakeArrayPersistent` 函数创建的数组赋值给文件的输出参数 `plhs`。

> **注意** 如果你创建了持久的 `mxArray`，你有责任在 MEX 文件清除时使用 `mxDestroyArray` 销毁它。如果不销毁持久的 `mxArray`，MATLAB 将内存泄漏。查看 `mexATExit` 以了解如何注册在 MEX 文件清除时调用的函数。查看 `mexLock` 以了解如何锁定你的 MEX 文件使其永不被清除。

## 输入参数

- `pm` — 指向 `mxArray` 的指针

`mxArray *` | `mwPointer`

指向通过 `mxCreate` 函数创建的数组的指针，在 C 中指定为 `mxArray *`，在 Fortran 中指定为 `mwPointer`。

## 另请查看

`mxATExit`, `mxDestroyArray`, `mexLock`, `mexMakeMemoryPersistent` 以及 `mxCreate*` 函数

## 版本历史

引入于 R2006a 之前

## mexMakeMemoryPersistent (C 和 Fortran)

使内存在 MEX 文件完成后保持持久化

## C 语法

```
#include "mex.h"
void mexMakeMemoryPersistent(void *ptr);
```

## Fortran 语法

```
#include "intrf.h"
subroutine mexMakeMemoryPersistent(ptr)
mwPointer ptr
```

## 描述

默认情况下，由 MATLAB 分配的内存是非持久的，在 MEX 文件执行时会自动释放。如果你希望内存持久化，请调用 `mexMakeMemoryPersistent`。

> **注意** 如果你创建了持久的内存，你有责任在 MEX 文件清除时将其释放。如果不释放持久内存，MATLAB 将内存泄漏。查看 `mexLock` 以了解如何锁定你的 MEX 文件使其永不被清除。

## 输入参数

- `ptr` — 指向内存的指针

`void *` | `mwPointer`

指向分配的内存的指针，在 C 中指定为 `void *`，在 Fortran 中指定为 `mwPointer`。

## 另请查看

`mexATExit`, `mexLock`, `mexMakeArrayPersistent`

## 版本历史

引入于 R2006a

## mexPrintf (C 和 Fortran)

ANSI 风格的输出函数

## C 语法

```
#include "mex.h"
int mexPrintf(const char *message, ...);
```

## Fortran 语法

```
#include "intrf.h"
integer*4 mexPrintf(character(*) message)
```

## 描述

调用 `mexPrintf` 在屏幕和日志中（如果已启用）打印字符串。默认情况下，MEX 分配的内存是未锁定的。

> **注意** 如果你在 `message` 中使用字面量 `%` 具有特殊含义。在 MEX 文件中，使用 `mexPrintf` 来显示字符串。

## 输入参数

- `message` — 要显示的字符串

`const char *` | `character(*)`

要显示的字符串，在 C 中指定为 `const char *`，在 Fortran 中指定为 `character(*)`。

- `...` — 参数

`const char *`

在 C 中用于 `message` 的转换参数。

## 输出参数

- `res` — 字符数

`int` | `integer*4`

打印的字符数，包括 `\n` 和 `\b` 等转义字符，在 C 中返回为 `int`，在 Fortran 中返回为 `integer*4`。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexfunction.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

## 版本历史

### 增加了 UTF-8 支持

`mexPrintf` 函数除了支持 LCP 字符串外，还接受 UTF-8 编码的数据。

## 另请查看

`sprintf` | `mexErrMsgAndTxt` | `mexWarnIdAndTxt`

## mexPutVariable (C)

从 MEX 函数到指定工作空间的数组

## C 语法

```
#include "mex.h"
int mexPutVariable(const char *workspace, const char *varname,
const mxArray *pm);
```

## 描述

> **注意** 要使用现代 C++ 特性和“MATLAB C++ 数据 API”编写 MEX 函数，请查看“Write C++ Functions from MATLAB”。

调用 `mexPutVariable` 将你的 MEX 函数中的 `mxArray` `pm` 复制到指定的工作空间。MATLAB 为工作空间中的 `mxArray` 分配名称。

`mexPutVariable` 让其他实体（如 MATLAB、自定义函数或其他 MEX 函数）访问该数组。

如果工作空间中存在同名变量，`mexPutVariable` 将用新 `mxArray` 的内容覆盖原有变量。例如，假设 MATLAB 工作空间定义了 `Peaches` 为：

Peaches

+ 1 2 3 4

你调用 `mexPutVariable` 将 `Peaches` 复制到同一个工作空间：

```
mexPutVariable("base", "Peaches", pm)
```

`mexPutVariable` 传递的值替换了 `Peaches` 的旧值。

## 输入参数

- `workspace` — 数组范围

`const char*`

要复制的数组范围，指定为 `const char*`。可能的值：

- `base` 将 `mxArray` 复制到基础工作空间。
- `caller` 将 `mxArray` 复制到调用工作空间。
- `global` 将 `mxArray` 复制到全局变量列表。

- `varname` — 变量名

`const char*`

工作空间中 `mxArray` 的名称，指定为 `const char*`。

不要使用 MATLAB 函数名作为变量名。与函数名冲突的常用变量名包括 `i`, `j`, `mode`, `char`, `size` 或 `path`。要确定特定名称是否与 MATLAB 函数相关，请使用 `which` 函数。

- `pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 的指针。

# 输出参数

`status` — 状态

`int`

状态，成功时返回为 0。失败时返回 1。失败的可能的原因是 `pm` 为 `NULL`。

## 示例

参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexgetarray.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mexGetVariable` | 第 1-142 页上的“setVariable”

## mexPutVariable (Fortran)

将来自 MEX 函数的数组存到指定的工作区

# Fortran 语法

```
#include "fintrf.h"
integer4 mexPutVariable(workspace, varname, pm)
character(**) workspace, varname
mwPointer pm
```

## 参数

`workspace`

指定你正在复制的数组的作用域。`workspace` 的值为：

- `base`: 将数组复制到基础工作区。
- `caller`: 将数组复制到调用者工作区。
- `global`: 将数组复制到全局变量列表。

`varname`

工作区中 `mxArray` 的名称

`pm`

指向 `mxArray` 的指针

## 返回

成功返回 0；失败返回 1。失败的可能的原因是 `pm` 为 0。

## 描述

调用 `mexPutVariable` 将位于指针 `pm` 处的 `mxArray` 从你的 MEX 函数复制到指定的工作区中。MATLAB 软件会在接收的工作区中为复制的 `mxArray` 分配 `varname`。

`mexPutVariable` 使得其他实体（如 MATLAB、用户定义函数或其他 MEX 函数）可以访问该数组。

如果指定的工作区中存在同名变量，`mexPutVariable` 将用新 `mxArray` 的内容覆盖变量的原内容。例如，假设 MATLAB 工作区定义 `Peaches` 如下：

Peaches

- 1 2 3 4

并且由于你调用 `mexPutVariable` 将 `Peaches` 复制到同一个工作区：

```
mexPutVariable("base", "Peaches", pm)
```

`mexPutVariable` 传递的值替换了 `Peaches` 的旧值。

不要使用 MATLAB 函数名作为变量名。与函数名冲突的常用变量名包括 `i`, `j`, `mode`, `char`, `size` 或 `path`。要确定特定名称是否与 MATLAB 函数相关，请使用该函数。

## 版本历史

在 R2006a 之前引入

## 另见

`mexGetVariable`

## mexSet (C)

设置指定图形属性的值

> **注意** 不要使用 `mexSet`。请使用 `mxSetProperty`。

# C 语法

```
#include "mex.h"
int mexSet(double handle, const char *property, mxArray *value);
```

## 描述

调用 `mexSet` 设置某个图形对象属性的值。`mexSet` 是 MATLAB `set` 函数的 API 等效实现。如要获取图形属性的值，请调用 `mexGet`。

# 输入参数

- `handle` — 图形对象句柄

`double`

图形对象句柄，指定为 `double`。

- `property` — 图形属性名称

`const char*`

图形属性名称，指定为 `const char*`。

- `value` — 属性值

`mxArray*`

属性值，指定为指向 `mxArray` 的指针。

# 输出参数

- `status` — 状态

`int`

状态，成功时返回为 0。失败时返回 1。失败可能的原因包括：

- 指定了不存在的属性。
- 为该属性指定了非法值，例如为数值属性指定了字符串值。

## 另见

`mxGetProperty`, `mxSetProperty`

## mexSetTrapFlag (C 和 Fortran)

(已移除) 控制 MEXCALLMATLAB 对错误的响应

> **注意** `mexSetTrapFlag` 已移除。请使用 `mexCallMATLABWithTrap`。更多信息请参阅“兼容性”。

# C 语法

```
#include "mex.h"
void mexSetTrapFlag(int trapflag);
```

# Fortran 语法

```
subroutine mexTrapFlag(trapflag)
       integer*
```

## 参数

`trapflag`

标志。

- `0`: 发生错误时，由 MATLAB 响应。
- `1`: 发生错误时，由 MEX 文件终止。

## 描述

调用 `mexSetTrapFlag` 控制 `MEXCALLMATLAB` 对错误的响应。

> **注意** `mexSetTrapFlag` 已移除。请使用 `mexCallMATLABWithTrap`。更多信息请参阅“兼容性”。

调用 `mexSetTrapFlag` 设置 `trapflag` 为 0，等同于没有调用 `mexTrapFlag`。如果调用 `mexSetTrapFlag` 并设置 `trapflag` 为 1，当发生错误时，MATLAB 响应。

## 版本历史

在 R2008 中引入

## 另见

`mexCallMATLABWithTrap`

## mexUnlock (C 和 Fortran)

允许 MEX 文件从内存中清除

# C 语法

```
#include "mex.h"
void mexUnlock(void);
```

# Fortran 语法

```
#include "intrf.h"
subroutine mexUnlock()
```

## 描述

默认情况下，MEX 文件是未锁定的，你可以随时清除它们。`mexLock` 会锁定 MEX 文件使其无法清除。调用 `mexUnlock` 移除锁定。

`mexLock` 会增加锁定计数。如果你调用了 n 次 `mexLock`，请调用 n 次 `mexUnlock` 以解锁文件。

## 示例

参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexlock.c`
- `mexlock.F`

## 另见

`mexIsLocked`, `mexLock`, `mexMakeArrayPersistent`, `mexMakeMemoryPersistent`, `clear`

## 版本历史

在 R2006a 之前引入

### 增加了对 UTF-8 的支持

`mexWarnMsgIdAndTxt` 函数除了支持为了后兼容性的 LCP 编码字符串外，还接受 UTF-8 编码的数据。

# mexWarnMsgIdAndTxt (C 和 Fortran)

警告消息



**注意** 不建议使用 `mexWarnMsgIdAndTxt`。请使用 `mexWarnMsgIdAndTxt` 代替。

# C 语法

```c
#include "mex.h"
void mexWarnMsgIdAndTxt(const char *warningmsg);
```

# Fortran 语法

```fortran
subroutine mexWarnMsgIdAndTxt(warningmsg)
character*(*) warningmsg
```

## 参数

- `warningmsg`: 包含要显示的警告消息的字符串

## 描述

`mexWarnMsgIdAndTxt` 促使 MATLAB 软件显示 `warningmsg` 的内容。`mexWarnMsgIdAndTxt` 不终止 MEX 文件。

## 另见

`mexErrMsgIdAndTxt`, `mexWarnMsgIdAndTxt`

# mwIndex (C)

用于 `mxArray` 索引值的 C 类型

## 描述

`mwIndex` 是一个表示索引值的类型，例如数组索引。使用此函数以实现跨平台灵活性。默认情况下，`mwIndex` 等于 C 中的 `size_t`。

包含该类型的 C 头文件是：

```c
#include "matrix.h"
```

## 版本历史

在 R2006a 之前引入

## 另见

`mex` | `mwSize` | `mwSignedIndex`

# 主题

- "在 C MEX 文件中创建 2-维元单元格数组"
- "在 C MEX 文件中处理大型 mxArrays"

# mwIndex (Fortran)

用于 `mxArray` 索引值的 Fortran 类型

## 描述

`mwIndex` 是一个表示索引值的类型，例如数组索引。使用此函数以实现跨平台灵活性。默认情况下，根据平台和编译标志，`mwIndex` 等于 `INTEGER*4` 或 `INTEGER*8`。

在 Fortran 中，`mwIndex` 是一个预处理器宏。包含该类型的 Fortran 头文件是：

```fortran
#include "fintrf.h"
```

## 版本历史

在 R2006a 之前引入

## 另见

`mex` | `mwSize` | `mwSignedIndex`

# 主题

- "处理大型 mxArrays"

# mwPointer (Fortran)

Fortran 指针类型

## 描述

`mwPointer` 预处理器宏声明了表示 `mxArray` 指针的适当 Fortran 类型，MATLAB 数据的底层类型。包含该宏的 Fortran 头文件是：

```fortran
#include <fintrf.h>
```

Fortran 预处理器会将 `mwPointer` 翻译为适用于你编译平台的 Fortran 声明。在 64 位平台上，该类型为 `INTEGER*8`。在 32 位平台上，如果 Fortran 编译器支持预处理，你可以使用 `mwPointer` 声明表示指针的函数、参数和变量。无法使用 `mwPointer` 时，请确保你的声明对于编译 Fortran 代码的平台具有正确的大小。

## 示例

此示例声明了 Fortran MEX 文件中 `mexFunction` 的参数。

```fortran
subroutine mexFunction(nlhs, plhs, nrhs, prhs)
mwPointer plhs(*), prhs(*)
integer nlhs, nrhs
```

更多示例请参阅 `matlabroot/extern/examples` 文件夹中名称以 `.F` 结尾的 Fortran 文件。

## 版本历史

在 R2006a 中引入

## 另见

`mexFunction`

# 主题

- "数据类型"
- "MATLAB 数据"

# mwSignedIndex (C)

用于 `mxArray` 尺寸值的符号整数 C 类型

## 描述

`mwSignedIndex` 是一个表示尺寸值（如数组维度）的符号整数类型。使用此函数以实现跨平台灵活性。默认情况下，`mwSignedIndex` 等于 C++ 中的 `ptrdiff_t`。

包含该类型的 C 头文件是：

```c
#include "matrix.h"
```

## 版本历史

在 R2006a 之前引入

## 另见

`mwIndex`

# mwSignedIndex (Fortran)

用于 `mxArray` 尺寸值的符号整数 Fortran 类型

## 描述

`mwSignedIndex` 是一个表示尺寸值（如数组维度）的符号整数类型。使用此函数以实现跨平台灵活性。默认情况下，根据平台和编译标志，`mwSignedIndex` 等于 `INTEGER*4` 或 `INTEGER*8`。

在 Fortran 中，`mwIndex` 是一个预处理器宏。包含该类型的 Fortran 头文件是：

```fortran
#include "fintrf.h"
```

## 版本历史

在 R2009a 中引入

## 另见

`mwSize`

# mwSize (C)

用于 `mxArray` 尺寸值的 C 类型

## 描述

`mwSize` 是一个表示尺寸值（如数组维度）的类型。使用此函数以实现跨平台灵活性。默认情况下，`mwSize` 等于 C++ 中的 `int`。

在使用 `mex-compatibleArray` 时，`mwSize` 等于 `int`。

包含该类型的 C 头文件是：

```c
#include "matrix.h"
```

## 版本历史

在 R2006a 之前引入

## 另见

`mwIndex`

# mwSize (Fortran)

用于 `mxArray` 尺寸值的 Fortran 类型

## 描述

`mwSize` 是一个表示尺寸值（如数组维度）的类型。使用此函数以实现跨平台灵活性。默认情况下，`mwSize` 是一个无符号整数。

在使用 `mex-compatibleArray` 时，`mwSize` 等于 `INTEGER*4` 或 `INTEGER*8`。

在 Fortran 中，`mwSize` 是一个预处理器宏。包含该类型的 Fortran 头文件是：

```fortran
#include "fintrf.h"
```

## 版本历史

在 R2006a 之前引入

## 另见

`mwIndex`

# mxAddField (C 和 Fortran)

向结构添加字段

## C 语法

```c
#include "matrix.h"
int mxAddField(mxArray *pm, const char *fieldname);
```

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxAddField(pm, character(*)
```

## 参数

- `pm`: 结构数组指针
- `fieldname`: 要添加的字段名称

## 返回

成功时返回字段编号，无效时返回 `-1`

## 描述

调用 `mxAddField` 向结构数组添加字段。

## 另见

`mxFieldNumber`

## 版本历史

在 R2006a 之前引入

# mxArray (C)

用于 `mxArray` 的 C 类型

## 描述

MATLAB 数据的底层类型。`mxArray` 是不透明类型。包含该类型的 C 头文件是：

```c
#include "matrix.h"
```

关于 C 语言中如何使用 `mxArray`，请参阅“Components of File”。在 MEX 文件中，使用 `mxArray` 操作数据。`mxArray` 具有临时范围，并在 MEX 函数结束时自动销毁。

## 示例

参见 `matlabroot/extern/examples/mx` 中的示例：

- `mxcreatecharmatrixfromstr.c`

## 限制

- 在 Simulink S 函数中，不要在 MEX 函数结束后存储任何 `mxArray` 指针。

## 提示

- 关于 MATLAB 脚本中的数据，请参阅“Data Types”。
- 关于其他 MathWorks 产品中的 `mxArray`，请搜索该产品的文档。

## 版本历史

在 R2006a 之前引入

## 另见

`mexFunction` | `mxClassID` | `mxCreateDoubleMatrix` | `mxCreateNumericArray` | `mxCreateString` | `mxDestroyArray` | `matlab::data`

# 主题

"Components of C File"

# mxArrayToString (C)

数组转字符串

## C 语法

```c
#include "matrix.h"
char *mxArrayToString(const mxArray *array_ptr);
```

## 描述

`mxArrayToString` 将 `mxCHAR` 数组的字符数据复制到 C 字符串。C 字符串始终以 NULL 结束并按列存储。如果数组包含多行，则按列复制到单个数组中。

此函数与 `mxGetString` 类似，区别在于：

- `mxArrayToString` 不需要字符串长度作为输入。
- 从 R2022a 开始，`mxArrayToString` 返回 UTF-8 编码字符串。

## 输入参数

- `array_ptr`: 指向 `mxCHAR` 数组的指针 (`const mxArray *`)

## 输出参数

- `str`: C 字符串 (`char *` | `NULL`)

本地代码页 (LCP) 编码的 C 字符串，指定为 `char *`。要将数组转换为 UTF-8 编码的字符串，请使用 `mxArrayToUTF8String`。失败时返回 `NULL`。失败的可能原因包括内存不足或指定的数组不是 `mxArray` 数组。

## 示例

参见 `matlabroot/extern/examples/mex` 中的示例：

- `mexatexit.c`
- `mxcreatecharmatrixfromstr.c`

参见 `matlabroot/extern/examples/mx` 中的示例：

- `mxcreatecharmatrixfromstr.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCreateString` | `mxGetString` | `mxArrayToUTF8String` | `mxCreateCharArray` | `mxCreateCharMatrixFromStrings`

# mxArrayToUTF8String (C)

将 UTF-8 编码的数组转换为字符串

## C 语法

```c
#include "matrix.h"
char *mxArrayToUTF8String(const mxArray *array_ptr);
```

## 参数

- `array_ptr`: 指向 `mxCHAR` 数组的指针。

## 返回

UTF-8 编码的 C 风格字符串。失败时返回 `NULL`。失败原因可能包括内存不足或指定的数组不是 `mxCHAR` 数组。

## 描述

调用 `mxArrayToUTF8String` 将 `mxCHAR` 数组的字符数据拷贝到 C 风格字符串中。数据按列主顺序存储。如果数组包含多行，则这些行将按列拷贝到单个数组中。

## 另见

`mxArrayToString`, `mxFree`, `mxCreateCharArray`, `mxCreateString`, `mxGetString`

## 版本历史

在 R2015a 中引入

增加了对 UTF-8 的支持

`mxArrayToUTF8String` 函数返回 UTF-8 编码的数据。

# mxAssert (C)

出于调试目的检查断言值

## C 语法

```c
#include "matrix.h"
void mxAssert(int expr, char *error_message);
```

## 参数

- `expr`: 断言的值
- `error_message`: 断言失败的描述

## 描述

类似于 ANSI C 的 `assert` 宏，`mxAssert` 检查断言的值，并仅在断言成立时才继续执行。如果 `expr` 的求值为 1（真），则 `mxAssert` 不执行任何操作。如果 `expr` 的求值为 0（假），`mxAssert` 将终止 MEX 文件并在 MATLAB 窗口中打印错误信息。该错误包含失败的断言的表达式、发生失败断言的文件名和行号，以及错误消息文本。`error_message` 允许你对断言失败的原因指定更佳的描述。如果你不想在失败的断言消息后跟随描述，请使用空字符串。

`mex` 脚本在构建优化过的 MEX 函数时会关闭这些断言，因此将断言用于调试目的。要使用 `mxAssert`，请使用 `-g filename` 语法构建 MEX。

断言是维护逻辑内部一致性的方法。使用它们防止你遗漏代码，并防止逻辑错误在捕获之前传播。不要使用断言来防止用户遗漏你的代码。

可以通过 C 预处理器从代码中移除断言：你可以在开发期间使用这些检查，并在代码正常工作时将其移除。在开发期间使用断言进行故障排除，不会减慢最终产品。

## 另见

`mxAssert`, `mexErrMsgIdAndTxt`

## 版本历史

在 R2006a 之前引入

# mxAssertS (C)

检查断言值但不打印断言文本

## C 语法

```c
#include "matrix.h"
void mxAssertS(int expr, char *error_message);
```

## 参数

- `expr`: 断言的值
- `error_message`: 断言失败的描述

## 描述

`mxAssertS` 类似于 `mxAssert`，不同之处 `mxAssertS` 不打印失败断言的文本。

## 另见

`mxAssert`

## 版本历史

在 R2006a 之前引入

# mxCalcSingleSubscript (C)

从第一个元素到目标元素的偏移量

## C 语法

```c
#include "matrix.h"
mwIndex mxCalcSingleSubscript(const mxArray *pm, mwSize nsubs, mwIndex *subs);
```

## 描述

调用 `mxCalcSingleSubscript` 确定 `mxArray` 起始与该数组给定元素之间有多少个元素。该函数将下标转换为线性索引。

例如，给定下标如 `(5,7)`，`mxCalcSingleSubscript` 返回从数组第一个元素到 `(5,7)` 元素的距离。记住 `mxArray` 数据在内部表示所有应包含的元素。无论 MATLAB 数组看起来有多少维度，在在一维数组中它们都是表示的。有关显示内部表示的示例，请参见“数据存储”。

避免使用 `mxCalcSingleSubscript` 遍历数组的元素。在 C 中，找到数组的起始地址并使用指针自增来访问后续元素更有效率。例如，要找到数值数组的起始地址，请调用以下函数之一。

## 输入参数

- `pm`: 指向 `mxArray` 的指针，`const mxArray*`
- `nsubs`: 元素数量，`mwSize`
- `subs`: 下标数组，`mwIndex*`

## 版本历史

在 R2006a 之前引入

## 另见

`mxGetCell` | `mxCell`

# mxCalcSingleSubscript (Fortran)

从第一个元素到目标元素的偏移量

## Fortran 语法

```fortran
#include "fintrf.h"
mwIndex mxCalcSingleSubscript(pm, nsubs, subs)
```

## 描述

调用 `mxCalcSingleSubscript` 确定 `mxArray` 起始与数组给定元素之间有多少个元素。该函数将下标转换为线性索引。

例如，给定下标如 `(5,7)`，`mxCalcSingleSubscript` 返回从第一个元素到 `(5,7)` 元素的距离。记住 `mxArray` 数据在内部表示所有应包含的元素。无论 MATLAB 数组看起来有多少维度，在在一维数组中它们都是表示的。有关内部表示的示例，请参见“数据存储”。

## 输入参数

- `pm`: 指向 `mxArray` 的指针，`mwPointer`
- `nsubs`: 元素数量，`mwSize`
- `subs`: 下标数组，`mwIndex`

## 返回

线性索引，`mwIndex`

## 版本历史

在 R2006a 之前引入

## 另见

`mxGetCell` | `mxCell`

# mxCalloc (C 和 Fortran)

使用管理器分配初始化为 0 的数组动态内存

## C 语法

```c
#include "matrix.h"
#include <stdlib.h>
void *mxCalloc(mwSize n, mwSize size);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCalloc(n, size)
mwSize n, size
```

## 参数

- `n`: 分配的元素数量。必须是非负数。
- `size`: 每个元素的字节数。（`sizeof` 操作计算每个元素的字节数。）

## 返回

成功时返回分配动态内存的起始指针。如果在 MAT 或引擎应用程序中失败，`mxCalloc` 在 C 中返回 `NULL`（Fortran 中返回 `0`）。如果在 MEX 文件中失败，MEX 文件将终止并返回 MATLAB 命令行。

`mxCalloc` 在空空间不足时失败。

## 描述

`mxCalloc` 分配连续的空空间来存储每个 `size` 个字节，并将新分配的内存初始化为 0。在 MATLAB 中分配内存时，请使用 `mxCalloc` 代替 ANSI C 调用函数。

在 MEX 文件（而非 MAT 或引擎应用程序）中，`mxCalloc` 将分配的内存向 MATLAB 管理器注册。当返回 MATLAB 命令行时，内存管理器会自动释放或取消分配这些内存。

你管理此函数创建的内存取决于分配它的数据的目的。如果你使用 `mxSetDoubles` 等函数将其赋值给 `plhs[]` 中的输出参数，则 MATLAB 负责释放内存。

如果你在内部使用这些数据，则 MATLAB 内存管理器将维护由函数分配的所有内存列表，并在返回 MATLAB 命令行时自动释放（取消分配）这些内存。通常，我们建议 MEX 文件销毁其临时



数组会自动释放其动态分配的内存。在源 MEX 文件中执行此类清理工作比依赖自动机制更高效。因此，当您完成对此函数分配内存的使用后，请调用 `mxFree` 来释放该内存。

如果您没有将此数据赋值给输出参数，并且希望它在 MEX 文件完成后仍然存在，则请在调用此函数后调用 `mexMakeMemoryPersistent`。如果您编写了带有持久性内存的 MEX 文件，请务必注册一个 `mexAtExit` 函数，以便在您的 MEX 文件被清除时释放已分配的内存。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`
- `arrayFillSetData.c`
- `phonebook.c`
- `revord.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `mxcalcsinglesubscript.c`
- `mxsetdimensions.c`

## 另见

`mxAtExit`、`mexMakeArrayPersistent`、`mexMakeMemoryPersistent`、`mxDestroyArray`、`mxFree`、`mxMalloc`、`mxRealloc`

## 版本历史

在 R2006a 之前引入

# mxChar (C)

字符串数组的类型

MATLAB 将 `mxArray` 存储为 `mxChar` 类型以表示 C 风格的 char 类型。MATLAB 使用 16 位无符号整数字符编码处理 Unicode 字符。

包含此文件的头文件是：

```c
#include "matrix.h"
```

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxmalloc.c`
- `mxcreatecharmatrixfromstr.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 另见

`mxCreateCharArray`

## 提示

- 有关 MATLAB 语言脚本和函数中数据的信息，请参见“数据类型”。

## 版本历史

在 R2006a 之前引入

# mxClassID

标识类数组的枚举值

## C 语法

```c
typedef enum {
    mxUNKNOWN_CLASS,
    mxCELL_CLASS,
    mxSTRUCT_CLASS,
    mxLOGICAL_CLASS,
    mxCHAR_CLASS,
    mxVOID_CLASS,
    mxDOUBLE_CLASS,
    mxSINGLE_CLASS,
    mxINT8_CLASS,
    mxUINT8_CLASS,
    mxINT16_CLASS,
    mxUINT16_CLASS,
    mxINT32_CLASS,
    mxUINT32_CLASS,
    mxINT64_CLASS,
    mxUINT64_CLASS,
    mxFUNCTION_CLASS
} mxClassID;
```

## 描述

各种 C API 函数需要或返回 `mxClassID` 参数。`mxClassID` 标识表示其数据元素的 `mxArray`。

## 常量

### mxUNKNOWN_CLASS

未确定类。您无法为 `mxArray` 指定此类别。然而，如果 `mxGetClassID` 无法识别该类，它将返回此值。

### mxCELL_CLASS

单元 `mxArray`。

### mxSTRUCT_CLASS

结构 `mxArray`。

### mxLOGICAL_CLASS

`mxLogical` 数据的逻辑 `mxArray`。

### mxCHAR_CLASS

`mxChar` 数据的字符串 `mxArray`。

### mxVOID_CLASS

预留。

### mxDOUBLE_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | double |
| --- | --- |
| C 实数类型 | `typedef double mxDouble;` |
| 复数数据类型 | `typedef struct { mxReal, imag; } mxComplexDouble;` |

### mxSINGLE_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | single |
| --- | --- |
| C 实数类型 | `typedef float mxSingle;` |
| 复数数据类型 | `typedef struct { mxReal, imag; } mxComplexSingle;` |

### mxINT8_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | int8 |
| --- | --- |
| C 实数类型 | `typedef int8 mx8;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxUINT8_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | uint8 |
| --- | --- |
| C 实数类型 | `typedef uint8 mx8;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxINT16_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | int16 |
| --- | --- |
| C 实数类型 | `typedef int16 mx16;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxUINT16_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | uint16 |
| --- | --- |
| C 实数类型 | `typedef uint16 mx16;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxINT32_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | int32 |
| --- | --- |
| C 实数类型 | `typedef int32 mx32;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxUINT32_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | uint32 |
| --- | --- |
| C 实数类型 | `typedef uint32 mx32;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxINT64_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | int64 |
| --- | --- |
| C 实数类型 | `typedef int64 mx64;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxUINT64_CLASS

实数或复数数据类型的数值 `mxArray`。

| MATLAB 类型 | uint64 |
| --- | --- |
| C 实数类型 | `typedef uint64 mx64;` |
| 复数数据类型 | `typedef struct { mxReal, imag; }` |

### mxFUNCTION_CLASS

标识函数句柄。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCreateCharArray`

# mxCopyComplex8ToPtr (Fortran)

从 Fortran 数组将 COMPLEX*8 值拷贝到指针数组

注意：`mxCopyComplex8ToPtr` 的函数签名在交织复数 API（Interleaved Complex API）中不同。

## Fortran 语法

### 交织复数 API

```fortran
#include "intrf.h"
integer*4 mxCopyComplex8ToPtr(y, pd, n)
complex*8 y(n)
mwPointer pd
mwSize n
```

### 分离复数 API

```fortran
#include "intrf.h"
subroutine mxCopyComplex8ToPtr(y, pr, pi, n)
complex*8 y(n)
mwPointer pr, pi
mwSize n
```

## 输入参数

- `y`：COMPLEX*8 Fortran 数组
- `pd`：指向双精度 MATLAB 复数数组的指针
- `pr`：指向单精度 MATLAB 数组实部数据的指针
- `pi`：指向单精度 MATLAB 数组虚部数据的指针
- `n`：要拷贝的元素个数

## 输出参数

- `status`：函数状态，使用交织复数 API 时返回为 `integer*4`。

## 描述

`mxCopyComplex8ToPtr` 将 Fortran COMPLEX*8 数组 `y` 中的 `n` 个 COMPLEX*8 值拷贝到指向的 MATLAB 数组中：

- 当使用 `-R2018a` 选项编译的交织复数 API 时，指向 `pd`。
- 当使用 `-R2017b` 选项编译的分离复数 API 时，指向 `pr` 和 `pi`。

设置标准 Fortran 数组用于在 MEX 文件的计算例程之间传递参数。对于不支持 `%VAL` 结构的 Fortran 编译器，请使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另见

`mxCopyPtrToComplex8`、`mxCreateNumericArray`、`mxCreateNumericMatrix`、`mxGetData`、`mxGetImagData`

# mxCopyInteger1ToPtr (Fortran)

从 Fortran 数组将 INTEGER*1 值拷贝到指针数组

## Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxCopyInteger1ToPtr(y, px, n)
integer*1 y(n)
mwPointer px
mwSize n
```

## 参数

- `y`：INTEGER*1 Fortran 数组
- `px`：指向数组实部或虚部数据的指针
- `n`：要拷贝的元素个数

## 描述

`mxCopyInteger1ToPtr` 将 Fortran INTEGER*1 数组中的 `n` 个 INTEGER*1 值拷贝到 `px` 指向的 MATLAB 数组（实部或虚部数组）。

设置标准 Fortran 数组用于在 MEX 文件的计算例程之间传递参数。对于不支持 `%VAL` 结构的 Fortran 编译器，使用此子程序。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `matsqint8.F`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCopyPtrToInteger1`、`mxCreateNumericArray`、`mxCreateNumericMatrix`

# mxCopyInteger2ToPtr (Fortran)

从 Fortran 数组将 INTEGER*2 值拷贝到指针数组

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mxCopyInteger2ToPtr(y, px, n)
integer*2 y(n)
mwPointer px
mwSize n
```

## 参数

- `y`：INTEGER*2 Fortran 数组
- `px`：指向数组实部或虚部数据的指针
- `n`：要拷贝的元素个数

## 描述

`mxCopyInteger2ToPtr` 将 Fortran INTEGER*2 数组 `y` 中的 `n` 个 INTEGER*2 值拷贝到 `px` 指向的 MATLAB 数组（实部或虚部数组）。

设置标准 Fortran 数组用于在 MEX 文件的计算例程之间传递参数。对于不支持 `%VAL` 结构的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另见

`mxCopyPtrToInteger2`、`mxCreateNumericArray`、`mxCreateNumericMatrix`

# mxCopyInteger4ToPtr (Fortran)

从 Fortran 数组将 INTEGER*4 值拷贝到指针数组

## Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxCopyInteger4ToPtr(y, px, n)
integer*4 y(n)
mwPointer px
mwSize n
```

## 参数

- `y`：INTEGER*4 Fortran 数组
- `px`：指向数组实部或虚部数据的指针
- `n`：要拷贝的元素个数

## 描述

`mxCopyInteger4ToPtr` 将 Fortran INTEGER*4 数组 `y` 中的 `n` 个 INTEGER*4 值拷贝到 `px` 指向的 MATLAB 数组（实部或虚部数组）。

设置标准 Fortran 数组用于在 MEX 文件的计算例程之间传递参数。对于不支持 `%VAL` 结构的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另见

`mxCopyPtrToInteger4`、`mxCreateNumericArray`、`mxCreateNumericMatrix`

# mxCopyPtrToCharacter (Fortran)

从指针数组拷贝 CHARACTER 值

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mxCopyPtrToCharacter(px, y, n)
mwPointer px
character(*) y
mwSize n
```

## 参数

- `px`：指向字符数组的指针
- `y`：字符数组
- `n`：要拷贝的元素个数

## 描述

`mxCopyPtrToCharacter` 从 `px` 指向的数组中拷贝 `n` 个字符值。此子程序对于从 Fortran 数组拷贝字符数据至关重要。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `demo2.F`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCopyPtrToPtr`、`mxCreateCharArray`、`mxCreateString`

# mxCopyPtrToComplex16 (Fortran)

从指针数组将 COMPLEX*16 值拷贝到 Fortran 数组

注意：`mxCopyPtrToComplex16` 的函数签名在交织复数 API 中不同。

## Fortran 语法

### 交织复数 API

```fortran
#include "fintrf.h"
integer*4 mxCopyPtrToComplex16(pd, y, n)
mwPointer pd
complex*16 y(n)
mwSize n
```

### 分离复数 API

```fortran
#include "fintrf.h"
subroutine mxCopyPtrToComplex16(pr, pi, y, n)
mwPointer pr, pi
complex*16 y(n)
mwSize n
```

## 输入参数

- `pd`：指向双精度 MATLAB 复数数组的指针
- `pr`：指向双精度 MATLAB 数组实部数据的指针
- `pi`：指向双精度 MATLAB 数组虚部数据的指针
- `y`：COMPLEX*16 Fortran 数组
- `n`：要拷贝的元素个数

## 输出参数

- `status`：函数状态，使用交织复数 API 时返回为 `integer*4`。

## 描述

`mxCopyPtrToComplex16` 将指向的 MATLAB 数组中的 `n` 个 COMPLEX*16 值拷贝到 Fortran COMPLEX*16 数组 `y`：

- 当使用 `-R2018a` 选项编译的交织复数 API 时，指向 `pd`。
- 当使用 `-R2017b` 选项编译的分离复数 API 时，指向 `pr` 和 `pi`。

设置标准 Fortran 数组用于在 MEX 文件的计算例程之间传递参数。对于不支持 `%VAL` 结构的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另见

`mxCopyComplex8ToPtr`、`mxCreateNumericArray`、`mxCreateNumericMatrix`、`mxGetData`、`mxGetImagData`

# mxCopyPtrToInteger1 (Fortran)

从指针数组到 Fortran 数组的 INTEGER*1 值

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mxCopyPtrToInteger1(px, y, n)
mwPointer px
integer*1 y(n)
mwSize n
```

## 参数

- `px`：指向数组实部或虚部数据的指针
- `y`：INTEGER*1 Fortran 数组
- `n`：复制的元素个数

## 描述



# mxCopyPtrToInteger1 (Fortran)

将指针数组中的 INTEGER*1 值复制到 Fortran 数组

## Fortran 语法

```
#include "intrf.h"
subroutine mxCopyPtrToInteger1(px, y, n)
mwPointer px
integer*1 y(n)
mwSize n
```

## 参数

- `px`：指向数组实部或虚部数据的指针
- `y`：INTEGER*1 Fortran 数组
- `n`：复制的元素个数

## 描述

`mxCopyPtrToInteger1` 将 `px` 指向的 MATLAB 数组（实部或虚部）中的 `n` 个 INTEGER*1 值复制到 Fortran INTEGER*1 数组 `y` 中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matsqint8.F`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCopyInteger1ToPtr` | `mxCreateNumericArray` | `mxCreateNumericMatrix`

---

# mxCopyPtrToInteger2 (Fortran)

从指针数组到 Fortran 数组的 INTEGER*2 值

## Fortran 语法

```
#include "intrf.h"
subroutine mxCopyPtrToInteger2(px, y, n)
mwPointer px
integer*2 y(n)
mwSize n
```

## 参数

- `px`：指向数组实部或虚部数据的指针
- `y`：INTEGER*2 Fortran 数组
- `n`：复制的元素个数

## 描述

`mxCopyPtrToInteger2` 将 `px` 指向的 MATLAB 数组（实部或虚部）中的 `n` 个 INTEGER*2 值复制到 Fortran INTEGER*2 数组 `y` 中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCopyInteger2ToPtr` | `mxCreateNumericArray` | `mxCreateNumericMatrix`

---

# mxCopyPtrToInteger4 (Fortran)

从指针数组到 Fortran 数组的 INTEGER*4 值

## Fortran 语法

```
#include "intrf.h"
subroutine mxCopyPtrToInteger4(px, y, n)
mwPointer px
integer*4 y(n)
mwSize n
```

## 参数

- `px`：指向数组实部或虚部数据的指针
- `y`：INTEGER*4 Fortran 数组
- `n`：复制的元素个数

## 描述

`mxCopyPtrToInteger4` 将 `px` 指向的 MATLAB 数组（实部或虚部）中的 `n` 个 INTEGER*4 值复制到 Fortran INTEGER*4 数组 `y` 中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCopyInteger4ToPtr` | `mxCreateNumericArray` | `mxCreateNumericMatrix`

---

# mxCopyPtrToPtrArray (Fortran)

从指针数组到 Fortran 数组的指针值

## Fortran 语法

```
#include "intrff.h"
subroutine mxCopyPtrToPtrArray(px, y, n)
mwPointer px
mwPointer y(n)
mwSize n
```

## 参数

- `px`：指向指针数组的指针
- `y`：包含 `mwPointer` 值的 Fortran 数组
- `n`：复制的指针个数

## 描述

`mxCopyPtrToPtrArray` 将 `px` 指向的 MATLAB 数组中的 `n` 个指针复制到 Fortran 数组 `y`。此子程序对于将 `matGetDir` 的输出复制到指针数组中至关重要。调用此函数后，`y` 的每个元素包含一个指向字符串的指针。你可以通过将 `y` 的每个元素作为第一个参数传递给 `mxCopyPtrToCharacter` 将字符串转换为 Fortran 字符数组。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matdemo2.F`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`matGetDir` | `mxCopyPtrToCharacter`

---

# mxCopyPtrToReal4 (Fortran)

从指针数组到 Fortran 数组的 REAL*4 值

## Fortran 语法

```
#include "intrf.h"
subroutine mxCopyPtrToReal4(px, y, n)
mwPointer px
real*4 y(n)
mwSize n
```

## 参数

- `px`：指向单精度 MATLAB 数组实部或虚部数据的指针
- `y`：REAL*4 Fortran 数组
- `n`：复制的元素个数

## 描述

`mxCopyPtrToReal4` 将 `px` 指向的 MATLAB 数组（实部或虚部）中的 `n` 个 REAL*4 值复制到 Fortran REAL*4 数组 `y` 中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCopyRealToPtr` | `mxCreateNumericArray` | `mxGetData` | `mxGetImagData`

---

# mxCopyPtrToReal8 (Fortran)

从指针数组到 Fortran 数组的 REAL*8 值

## Fortran 语法

```
#include "intrf.h"
subroutine mxCopyPtrToReal8(px, y, n)
mwPointer px
real*8 y(n)
mwSize n
```

## 参数

- `px`：指向双精度 MATLAB 数组实部或虚部数据的指针
- `y`：REAL*8 Fortran 数组
- `n`：复制的元素个数

## 描述

`mxCopyPtrToReal8` 将 `px` 指向的 MATLAB 数组（实部或虚部）中的 `n` 个 REAL*8 值复制到 Fortran REAL*8 数组 `y` 中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的示例：

- `fengdemo.F`

参见 `matlabroot/extern/examples/ref` 中的示例：

- `timestwo.F`
- `xtimes.F`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCopyRealToPtr` | `mxCreateNumericArray` | `mxGetData` | `mxGetImagData`

---

# mxCopyReal4ToPtr (Fortran)

从 Fortran 数组到指针数组的 REAL*4 值

## Fortran 语法

```
#include "intrff.h"
subroutine mxCopyReal4ToPtr(y, px, n)
real*4 y(n)
mwPointer px
mwSize n
```

## 参数

- `y`：REAL*4 Fortran 数组
- `px`：指向单精度 MATLAB 数组实部或虚部数据的指针
- `n`：复制的元素个数

## 描述

`mxCopyReal4ToPtr` 将 Fortran REAL*4 数组中的 `n` 个 REAL*4 值复制到 `px` 指向的 MATLAB 数组（实部或虚部）中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxPtrToReal4` | `mxCreateNumericArray` | `mxGetData` | `mxGetImagData`

---

# mxCopyReal8ToPtr (Fortran)

从 Fortran 数组到指针数组的 REAL*8 值

## Fortran 语法

```
#include "intrff.h"
subroutine mxCopyReal8ToPtr(y, px, n)
real*8 y(n)
mwPointer px
mwSize n
```

## 参数

- `y`：REAL*8 Fortran 数组
- `px`：指向双精度 MATLAB 数组实部或虚部数据的指针
- `n`：复制的元素个数

## 描述

`mxCopyReal8ToPtr` 将 Fortran REAL*8 数组中的 `n` 个 REAL*8 值复制到 `px` 指向的 MATLAB 数组（实部或虚部）中。

设置标准的 Fortran 数组，用于作为 MEX 文件计算程序的参数传入或传出。对于不支持 `%VAL` 构造的 Fortran 编译器，使用此子程序。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的示例：

- `matdemool1.F`
- `fengdemo.F`

参见 `matlabroot/extern/examples/ref` 中的示例：

- `timestwo.F`
- `xtimes.F`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCopyPtrToReal8` | `mxCreateNumericArray` | `mxCreateNumericMatrix` | `mxGetData` | `mxGetImagData`

---

# mxCreateCellArray (C 和 Fortran)

N 维单元数组

## C 语法

```
#include "matrix.h"
mxArray *mxCreateCellArray(mwSize ndim, const mwSize *dims);
```

## Fortran 语法

```
#include "intrf.h"
mwPointer mxCreateCellArray(ndim, dims)
mwSize ndim
mwSize dims(ndim)
```

## 参数

- `ndim`：创建的单元的维度数。例如，要创建一个三维单元 `mxArray`，将 `ndim` 设置为 3。
- `dims`：维度数组。维度中的每个元素包含 `mxArray` 在该维度上的尺寸。例如，在 C 中，将 `dims[0]` 设置为 5，`dims[1]` 设置为 7 可建立一个 5x7 的 `mxArray`。在 Fortran 中，将 `dims(1)` 设置为 5，`dims(2)` 设置为 7。`dims` 通常包含一些维度元素。

## 返回

指向创建的 `mxArray` 的指针。如果在独立应用程序（非 MEX 文件）中执行失败，则在 C 中返回 `NULL`（Fortran 中返回 0）。如果在 MEX 文件中执行失败，MEX 文件将终止并将控制交给 MATLAB 提示符。当没有足够的空堆空间创建 `mxArray` 时，函数执行失败。

## 描述

使用 `mxCreateCellArray` 创建一个由 `ndim` 和 `dims` 定义大小的 cell `mxArray`。例如，在 C 中，要建立一个 4x8x7 的维单元 `mxArray`，设置：

```
ndim = 3;
dims[0] = 4; dims[1] = 8; dims[2] = 7;
```

在 Fortran 中，要建立一个 4x8x7 的维单元 `mxArray`，设置：

```
ndim = 3;
dims(1) = 4; dims(2) = 8; dims(3) = 7;
```

创建的 `cellArray` 是未填充的；`mxCreateCellArray` 将每个单元初始化为 `NULL`。要向单元中放入数据，请调用 `mxSetCell`。

MATLAB 会自动移除 `dims` 参数中指定的任何末尾单维度。例如，如果 `ndim` 等于 5 且 `dims` 等于 `[4 1 7 1 1]`，则生成的数组维度为 4x1x7。

## 示例

请参阅 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

## 另请参阅

`mxCreateCellMatrix` | `mxGetCell` | `mxSetCell` | `mxIsCell`

## 版本历史

在 R2006a 之前引入

---

# mxCreateCellMatrix (C 和 Fortran)

2 维单元数组

## C 语法

```
#include "matrix.h"
mxArray *mxCreateCellMatrix(mwSize m, mwSize n);
```

## Fortran 语法

```
#include "fortran.h"
mxPointer *mxCreateCellMatrix(m, n)
mwSize m, n
```

## 参数

- `m`：行数
- `n`：列数

## 返回

指向所创建的 `mxArray` 的指针。如果是在独立（非 MEX 文件）应用程序中失败，则返回 `NULL`（Fortran 中为 0）。如果是在 MEX 文件中失败，MEX 将终止并将控制交回 MATLAB 提示符。当没有足够的空堆空间来创建 `mxArray` 时，函数失败。

## 描述

使用 `mxCreateCellMatrix` 创建一个 `m` 比 `n` 的二维单元 `mxArray`。所创建的 `mxArray` 是空的；`mxCreateCellMatrix` 将每个单元格初始化为 `NULL`（Fortran 中为 0）。要向单元格中放入数据，请使用 `mxSetCell`。

`mxCreateCellMatrix` 与 `mxCreateCellArray` 相同，但 `mxCreateCellMatrix` 只能创建二维 `mxArrays`，而 `mxCreateCellArray` 可以创建维度大于 1 的任意维度的 `mxArrays`。

## 示例

请参阅 `matlab/extern/examples/mx` 中的这些示例：

- `mxcreatecellmatrix.c`
- `mxcreatecellmatrix.f`

## 另请参阅

`mxCreateCellArray`

## 版本历史

在 R2006a 之前引入

---

# mxCreateCharArray (C)

N 维 mxChar 数组

## C 语法

```
#include "matrix.h"
mxArray *mxCreateCharArray(mwSize ndim, const mwSize *dims);
```

## 描述

使用 `mxCreateCharArray` 创建一个 N 维 `mxChar` 数组，每个元素均设为 `NULL`。

MATLAB 会自动移除 `dims` 参数中指定的任何末尾单维度。例如，如果 `ndim` 等于 5 且 `dims` 等于 `[4 1 7 1 1]`，则生成的数组维度为 4x1x7。

## 输入参数

- **`ndim` — 维度数**：`mwSize`。维度数，指定为 `mwSize`。如果你指定 0、1 或 2，则 `mxCreateCharArray` 会创建一个二维的 `mxArray`。
- **`dims` — 维度数组**：`const mwSize *`。维度数组，指定为 `const mwSize *`。维度数组中的每个元素包含该数组在该维度上的大小。例如，要创建一个 5x7 的数组，将 `dims[0]` 设置为 5 并将 `dims[1]` 设置为 7。通常，`dims` 数组包含 `ndim` 个元素。

## 输出参数

- **`pm` — 指向 mxArray 的指针**：`mxArray * | NULL`。指向一个类型为 `mxChar` 的 `mxArray` 的指针，指定为 `mxArray *`。当没有足够的空堆空间来创建 `mxArray` 时，函数失败。
  - MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 `NULL`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxCreateCharMatrixFromStrings` | `mxCreateString`

---

# mxCreateCharArray (Fortran)

N 维 mxChar 数组

## Fortran 语法

```
#include "fintrf.h"
mxPointer mxCreateCharArray(ndim, dims)
mxSize ndim
mxSize dims(ndim)
```

## 描述

使用 `mxCreateCharArray` 创建一个 N 维 `mxChar` 数组，每个元素均设为 0。

MATLAB 会自动移除 `dims` 参数中指定的任何末尾单维度。例如，如果 `ndim` 等于 5 且 `dims` 等于 `[4 1 7 1 1]`，则生成的数组维度为 4x1x7。

## 输入参数

- **`ndim` — 维度数**：`mxSize`。维度数，指定为 `mxSize`。如果你指定 0、1 或 2，则 `mxCreateCharArray` 会创建一个二维的 `mxArray`。
- **`dims` — 维度数组**：array of `mxSize`。维度数组，指定为 `mxSize` 数组。维度数组中的每个元素包含该数组在该维度上的大小。例如，要创建一个 5x7 的数组，将 `dims(1)` 设置为 5 并将 `dims(2)` 设置为 7。通常，该数组包含 `ndim` 个元素。

## 输出参数

- **`pm` — 指向 mxArray 的指针**：`mxPointer | 0`。指向一个类型为 `mxChar` 的 `mxArray` 的指针，指定为 `mxPointer`。当没有足够的空堆空间来创建 `mxArray` 时，函数失败。
  - MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 版本历史

在 R2006a 之前引入

## 另请参阅

（此处原文无内容）



# mxCreateMatrixFromStrings / mxCreateString

## mxCreateMatrixFromStrings (C)

二维 `mxChar` 数组，初始化为指定值。

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateMatrixFromStrings(mwSize m, const char **str);
```

### 描述

使用 `mxCreateMatrixFromStrings` 创建一个 m 行 n 列的 `mxArray`，每行初始化为一个字符串。`mxArray` 的维度为 m×n，其中 n 是最长字符串的长度。

### 输入参数

- **m** — 行数
  `mwSize`
  行数，指定为 `mwSize`。

- **str** — 字符串数组
  `const char **`
  字符串数组，指定为 `const char **`。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mxArray * | NULL`
  指向一个类型为 `mxChar` 的 `mxArray` 的指针，指定为 `mxArray *`。
  当没有足够的空间来创建 `mxArray` 时，函数失败。

### 示例

请参阅 `matlabroot/extern/examples/mx` 中的这些示例：
- `mxcreatematrixstr.c`

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateCharArray` | `mxGetString`

## mxCreateFromStrings (Fortran)

二维 `mxChar` 数组，初始化为指定值。

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateFromStrings(m, str)
mwSize m
character(*) str(m)
```

### 描述

使用 `mxCreateFromStrings` 创建一个 m 行 n 列的 `mxArray`，每行初始化为一个字符串。`mxArray` 的维度为 m×n，其中 n 是最长字符串的长度。

### 输入参数

- **m** — 行数
  `mwSize`
  行数，指定为 `mwSize`。

- **str** — 字符串数组
  `character(*) str(m)`
  字符串数组，指定为 `character(*) str(m)`。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mwPointer | 0`
  指向一个类型为 `mxChar` 的 `mxArray` 的指针，指定为 `mwPointer`。
  当没有足够的空间来创建 `mxArray` 时，函数失败。

### 示例

请参阅 `matlabroot/extern/examples/mx` 中的这些示例：
- `mxcreatematrixfromstr.f`

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateCharArray` | `mxGetString`

## mxCreateDoubleMatrix (C)

二维双精度浮点数组。

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateDoubleMatrix(mwSize m, mwSize n, mxComplexity complexFlag);
```

### 描述

使用 `mxCreateDoubleMatrix` 创建一个 m 行 n 列的 `mxArray`。

在使用完 `mxArray` 后调用 `mxDestroyArray`。`mxDestroyArray` 函数会释放 `mxArray` 及其相关的实部和虚部元素。

### 输入参数

- **m** — 行数
  `mwSize`
  行数，指定为 `mwSize`。

- **n** — 列数
  `mwSize`
  列数，指定为 `mwSize`。

- **complexFlag** — 复数数组指示
  `mxComplexity`
  复数数组指示，指定为 `mxComplexity` 值。

  对于使用 `mex -R2018a` 命令构建的应用程序，函数将每个数据元素初始化为 0。

  对于其他特定版本的构建选项，函数设置 `pr` 数组中的每个元素。如果 `complexFlag` 为 `mxCOMPLEX`，函数将 `pi` 数组设为 0。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mxArray * | NULL`
  指向一个类型为 `mxDouble` 的 `mxArray` 的指针，指定为 `mxArray *`。
  当没有足够的空间来创建 `mxArray` 时，函数失败。

### 示例

请查看 `matlabroot/extern/examples/refbook` 中的这些示例：
- `convec.c`
- `findnz.c`
- `matrixDivide.c`
- `sincall.c`
- `timestwo.c`
- `xtimesy.c`

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateNumericArray` | `mxDestroyArray`

## mxCreateDoubleMatrix (Fortran)

二维双精度浮点数组。

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateDoubleMatrix(m, n, complexFlag)
mwSize m, n
integer*4 complexFlag
```

### 描述

使用 `mxCreateDoubleMatrix` 创建一个 m 行 n 列的 `mxArray`。

在使用完 `mxArray` 后，调用 `mxDestroyArray`。`mxDestroyArray` 会释放该 `mxArray` 及其相关的实部和虚部元素。

### 输入参数

- **m** — 行数
  `mwSize`
  行数，指定为 `mwSize`。

- **n** — 列数
  `mwSize`
  列数，指定为 `mwSize`。

- **complexFlag** — 复数数组指示
  `0 | 1`
  复数数组指示，指定为 0 或 1。

  对于使用 `mex -R2018a` 命令构建的应用，该函数会将每个数据元素初始化为 0。

  对于所有其他 mex-release 构建选项，该函数会设置 `pr` 数组中的每个元素。如果 `complexFlag` 为 1，该函数将 `pi` 数组设置为 0。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mwPointer | 0`
  指向类型为 `mxDouble` 的 `mxArray`，如果成功，则指定为 `mwPointer`。

  当没有足够的空间来创建 `mxArray` 时，函数执行失败。
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

### 示例

请查看 `matlabroot/extern/examples/refbook` 中的这些示例：
- `convec.F`
- `dblmat.F`
- `matsq.F`
- `timestwo.F`
- `xtimesy.F`

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateNumericArray` | `mxCreateNumericMatrix` | `mxDestroyArray`

## mxCreateDoubleScalar (C)

标量双精度数组，初始化为指定值。

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateDoubleScalar(double value);
```

### 描述

调用 `mxCreateDoubleScalar` 创建一个类型为 `mxDouble` 的标量 `mxArray`。

在以下情况下，可以使用 `mxCreateDoubleScalar` 代替 `mxCreateDoubleMatrix`。

| 替换 | 使用 |
| --- | --- |
| `pa = mxCreateDoubleMatrix(1, 1, mxREAL); *mxGetDoubles(pa) = value;` | `pa = mxCreateDoubleScalar(value);` |

在使用完 `mxArray` 后，调用 `mxDestroyArray`。

### 输入参数

- **value** — 标量值
  `double`
  标量值，指定为 `double`。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mxArray * | NULL`
  指向类型为 `mxDouble` 的 `mxArray`，如果成功，则指定为 `mxArray *`。

  当没有足够的空间来创建 `mxArray` 时，函数执行失败。
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 `NULL`。

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateDoubleMatrix` | `mxDestroyArray`

## mxCreateDoubleScalar (Fortran)

标量双精度数组，初始化为指定值。

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateDoubleScalar(value)
real*8 value
```

### 描述

调用 `mxCreateDoubleScalar` 创建一个标量 `mxArray`。

在使用完 `mxArray` 后，调用 `mxDestroyArray`。

在以下情况下，可以使用 `mxCreateDoubleScalar` 代替 `mxCreateDoubleMatrix`。

| 替换 | 使用 |
| --- | --- |
| `pm = mxCreateDoubleMatrix(1, 1, 0); mxRealTo(pm)` | `pm = mxCreateDoubleScalar(value)` |

### 输入参数

- **value** — 标量值
  `real*8`
  标量值，指定为 `real*8`。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mwPointer`
  指向类型为 `mxDouble` 的 `mxArray`，如果成功，则指定为 `mwPointer`。

  当没有足够的空间来创建 `mxArray` 时，函数执行失败。
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateDoubleMatrix` | `mxDestroyArray`

## mxCreateLogicalArray (C)

N 维逻辑数组。

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateLogicalArray(mwSize ndim, const mwSize *dims);
```

### 输入参数

- **ndim** — 维度数
  `mwSize`
  维度数，指定为 `mwSize`。如果指定的 `ndim` 小于 2，`mxCreateLogicalArray` 将维度数设置为 2。

- **dims** — 维度数组
  `const mwSize *`
  维度数组，指定为 `const mwSize *`。如果指定的 `ndim` 小于 2，`dims` 将被忽略。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mxArray * | NULL`
  指向 `mxArray` 的指针。当没有足够的空间来创建 `mxArray` 时，函数执行失败。

### 描述

调用 `mxCreateLogicalArray` 创建一个 N 维逻辑数组。

在使用完 `mxArray` 后，调用 `mxDestroyArray`。

在以下情况下，可以使用 `mxCreateLogicalArray` 代替 `mxCreateDoubleMatrix`。

MATLAB 会自动删除 `dims` 参数末尾的单维。例如，如果 `ndim` 等于 5 且 `dims` 为 `[4 1 7 1 1]`，则生成的数组维度为 4×1×7。

## mxCreateLogicalMatrix (C)

二维逻辑数组。

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateLogicalMatrix(mwSize m, mwSize n);
```

### 输入参数

- **m** — 行数
  `mwSize`
  行数，指定为 `mwSize`。

- **n** — 列数
  `mwSize`
  列数，指定为 `mwSize`。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mxArray * | NULL`
  指向 `mxArray` 的指针。当没有足够的空间来创建 `mxArray` 时，函数执行失败。

### 描述

使用 `mxCreateLogicalMatrix` 创建一个 m 行 n 列的逻辑数组。

在使用完 `mxArray` 后，调用 `mxDestroyArray`。`mxDestroyArray` 会释放该 `mxArray` 及其相关的实部和虚部元素。

### 示例

请查看 `matlabroot/extern/examples/refbook` 中的这些示例：
- `convec.c`
- `findnz.c`
- `matrixDivide.c`
- `sincall.c`
- `timestwo.c`
- `xtimesy.c`

### 版本历史

在 R2006a 之前引入。

### 另请参阅

`mxCreateNumericArray` | `mxDestroyArray`

## mxCreateNumericArray (C)

N 维数值数组。

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateNumericArray(mwSize ndim, const mwSize *dims, mxClassID classid, mxComplexity complexFlag);
```

### 输入参数

- **ndim** — 维度数
  `mwSize`
  维度数，指定为 `mwSize`。如果 `ndim` 小于 2，`mxCreateNumericArray` 将维度数设置为 2。

- **dims** — 维度数组
  `const mwSize *`
  维度数组，指定为 `const mwSize *`。

  维度数组中的每个元素都包含该数组在对应维度上的大小。例如，要创建一个 5×7 的数组，`dims[0]` 为 5，`dims[1]` 为 7。

  通常，`dims` 数组包含 `ndim` 个元素。

- **classid** — 类标识符
  `mxClassID`
  类标识符，指定为 `mxClassID` 类型。`classid` 决定了数值数据在内存中的表示方式。例如，`mxCreateNumericMatrix` 将 `mxINT16_CLASS` 值存储为 16 位有符号整数。

- **complexFlag** — 复数数组指示
  `mxComplexity`
  复数数组指示，指定为 `mxComplexity` 值。

  对于使用 `mex -R2018a` 命令构建的应用，该函数将每个数据元素初始化为 0。

  对于所有 mex 版本特定的构建选项，该函数会设置 `pr` 数组中的每个元素。如果 `complexFlag` 为 `mxCOMPLEX`，则该函数将 `pi` 数组设置为 0。

### 输出参数

- **pm** — 指向 `mxArray` 的指针
  `mxArray * | NULL`
  指向类型为 `classid` 的 `mxArray` 的指针，指定为 `mxArray *`。

  当没有足够的可用空间创建 `mxArray` 时，函数执行失败。
  - MEX 文件 — 终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 `NULL`。

### 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：
- `phonebook.c`
- `doubleelement.c`
- `matrixDivide.c`
- `matsqint8.F`

查看 `matlabroot/extern/examples/mx` 中的这些示例：
- `mxisfinite.c`

### 版本历史

R2006a 之前引入。

### 另请参阅

`mxClassID` | `mxComplexity` | `mxDestroyArray` | `mxCreateUninitNumericArray` | `mxCreateNumericMatrix`

## mxCreateNumericArray (Fortran)

N 维数值数组。

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateNumericArray(ndim, dims, classid, complexFlag)
mwSize ndim
mwSize dims(ndim)
integer*4 classid, complexFlag
```

### 描述

使用 `mxCreateNumericArray` 创建一个 N 维 `mxArray`。

`mxCreateNumericArray` 与 `mxCreateDoubleMatrix` 的区别如下：

- `mxCreateDoubleMatrix` 中的所有元素都是双精度浮点数。`mxCreateNumericArray` 中的数据元素可以是任何数值类型，包括不同的整数精度。
- `mxCreateDoubleMatrix` 仅创建二维数组。`mxCreateNumericArray` 创建两个或更多维的数组。

MATLAB 会自动移除 `dims` 参数中指定的末尾单维度。例如，如果 `ndim` 等于 5 且 `dims` 等于 `[4 1 7 1 1]`，则生成的数组维度为 4×1×7。

此表显示了与 MATLAB 类等价的 Fortran 类型。

| MATLAB 类名 | Fortran 类型 |
| --- | --- |
| int8 | BYTE |
| int16 | INTEGER*2 |
| int32 | INTEGER*4 |
| int64 | INTEGER*8 |
| single | REAL*4 / COMPLEX*8 |
| double | REAL*8 / COMPLEX*16 |

在完成 `mxArray` 使用后调用 `mxDestroyArray`。`mxDestroyArray` 函数会释放 `mxArray` 及其关联的实部和虚部元素。

### 输入参数

- **ndim** — 维度数
  `mwSize`
  维度数，指定为 `mwSize`。如果 `ndim` 小于 2，则 `mxCreateNumericArray` 将维度数设置为 2。

- **dims** — 维度数组
  `array of mwSize`
  维度数组，指定为 `mwSize` 数组。

  维度数组中的每个元素包含数组在对应维度上的大小。例如，要创建一个 5×7 的数组，将 `dims(1)` 设置为 5，`dims(2)` 设置为 7。

  通常，`dims` 数组包含 `ndim` 个元素。

- **classid** — 类标识符
  `integer*4`
  类标识符，指定为 `integer*4`。

- **complexFlag** — 复数数组指示
  `integer*4`
  复数数组指示，指定为 `integer*4`。



# mxCreateNumericMatrix (C)

## C 语法

```c
#include "matrix.h"
mxArray *mxCreateNumericMatrix(mwSize m, mwSize n, mxClassID classid, mxComplexity ComplexFlag);
```

## 描述

使用 `mxCreateNumericMatrix` 创建一个二维数组。`classid` 指定数组中元素的数值类型。

此表显示了等于 MATLAB 类的 C 值。

| MATLAB 类名 | C 值 |
|---|---|
| int8 | `mxINT8_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| single | `mxSINGLE_CLASS` |
| double | `mxDOUBLE_CLASS` |

在完成 `mxArray` 使用后调用 `mxDestroyArray`。`mxDestroyArray` 释放 `mxArray` 及其关联实部和虚部元素。

## 输入参数

### m — 行数
`mwSize`

行数，指定为 `mwSize`。

### n — 列数
`mwSize`

列数，指定为 `mwSize`。

### classid — 类标识符
`mxClassID`

类标识符，指定为 `mxClassID` 类型。`classid` 参数决定了数值数据在内存中的表示方式。例如，`mxCreateNumericMatrix` 将 `mxINT16_CLASS` 值存储为 16 位有符号整数。

### ComplexFlag — 复数数组指示
`mxComplexity`

复数数组指示，指定为 `mxComplexity` 值。

对于使用 `mex -R2018a` 命令构建的应用，该函数将每个数据元素初始化为 0。

对于所有 mex 版本特定的构建选项，该函数设置 `pr` 数组中的每个元素。如果 `ComplexFlag` 为 `mxCOMPLEX`，则该函数将 `pi` 数组设置为 0。

## 输出参数

### pm — 指向 mxArray 的指针
`mxArray *` | `NULL`

指向类型为类的 `mxArray` 的指针，如果成功，指定为 `mxArray *`。

当没有足够的可用堆空间创建 `mxArray` 时，函数执行失败。

- **MEX 文件** — 终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX）应用程序** — 函数返回 `NULL`。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `arrayFillGet.c`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxClassID` | `mxComplexity` | `mxDestroyArray` | `mxCreateUninitNumericMatrix` | `mxCreateNumericArray`

---

# mxCreateNumericMatrix (Fortran)

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateNumericMatrix(m, n, classid, ComplexFlag)
mwSize m, n
integer*4 classid, ComplexFlag
```

## 描述

使用 `mxCreateNumericMatrix` 创建一个二维 `mxArray`。`classid` 指定数组中元素的数值类型。

此表显示了与 MATLAB 类等价的 Fortran 类型。

| MATLAB 类名 | Fortran 类型 |
|---|---|
| int8 | `BYTE` |
| int16 | `INTEGER*2` |
| int32 | `INTEGER*4` |
| int64 | `INTEGER*8` |
| single | `REAL*4` `COMPLEX*8` |
| double | `REAL*8` `COMPLEX*16` |

在完成 `mxArray` 使用后调用 `mxDestroyArray`。`mxDestroyArray` 释放 `mxArray` 及其关联实部和虚部元素。

## 输入参数

### m — 行数
`mwSize`

行数，指定为 `mwSize`。

### n — 列数
`mwSize`

列数，指定为 `mwSize`。

### classid — 类标识符
`integer*4`

类标识符，指定为 `integer*4`。`classid` 决定了数值数据在内存中的表示方式。使用 `mxClassIdFromClassName` 函数从 MATLAB 类名中派生 `classid`。

### ComplexFlag — 复数数组指示
`0` | `1`

复数数组指示，指定为 0 或 1。

对于使用 `mex -R2018a` 命令构建的应用，该函数将每个数据元素初始化为 0。

对于所有其他 mex 版本特定的构建选项，该函数设置 `pr` 数组中的每个元素。如果 `ComplexFlag` 为 1，则该函数将 `pi` 数组设置为 0。

## 输出参数

### pm — 指向 mxArray 的指针
`mwPointer` | `0`

指向类型为类的 `mxArray` 的指针，指定为 `mwPointer`。

当没有足够的可用堆空间创建 `mxArray` 时，函数执行失败。

## 示例

以下 Fortran 语句创建了一个 4x3 的 `REAL*4` 元素矩阵，该矩阵不包含任何虚部组件：

```fortran
C    Create 4x3 mxArray of REAL*4
    mxCreateNumericMatrix(4, 3, 
    mxClassIDFromClassName('single'), 0)
```

## 版本历史

R2006a 之前引入

## 另请参阅

`mxClassIDFromClassName` | `mxDestroyArray` | `mxCreateNumericArray`

---

# mxCreateSparse (C 和 Fortran)

## C 语法

```c
#include "matrix.h"
mxArray *mxCreateSparse(mwSize m, mwSize n, mwSize nzmax, mxComplexity ComplexFlag);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateSparse(m, n, nzmax, ComplexFlag)
mwSize m, n, nzmax
integer*4 ComplexFlag
```

## 参数

- **m** — 行数
- **n** — 列数
- **nzmax** — `mxCreateSparse` 应该分配的用于存储 `pr`、`ir` 以及（如果 C 中 `ComplexFlag` 为 `mxCOMPLEX`，在 Fortran 中为 1）`pi` 数组的元素数量。将 `nzmax` 的值设置为大于或等于你计划放入 `mxArray` 的非零元素数量，但确保 `nzmax` 小于或等于 `m*n`。`nzmax` 大于或等于 1。
- **ComplexFlag** — 如果你要创建的 `mxArray` 包含虚数据，请将 `ComplexFlag` 设置为 C 中的 `mxCOMPLEX`（Fortran 中的 1）。否则，将 `ComplexFlag` 设置为 C 中的 `mxREAL`（Fortran 中的 0）。

## 返回

指向创建的 `mxArray` 的指针。如果在独立程序（非 MEX 文件）应用中失败，在 C 中返回 `NULL`（Fortran 中返回 0）。如果在 MEX 文件中失败，MEX 文件终止并将控制权返回给 MATLAB 提示符。当没有足够的可用空间来创建 `mxArray` 时，函数失败。在这种情况下，尝试减少 `nzmax`、`m` 或 `n`。

## 描述

调用 `mxCreateSparse` 创建一个未填充稀疏双精度 `mxArray`。返回的稀疏 `mxArray` 不包含稀疏信息，不能作为参数传递给任何 MATLAB 稀疏函数。要使返回的稀疏 `mxArray` 可用，请初始化 `pr`、`ir`、`jc` 以及（如果存在）`pi` 数组。

`mxCreateSparse` 为以下分配空间：

- 长度为 `nzmax` 的 `pr` 数组。
- 长度为 `nzmax` 的 `pi` 数组，但仅当 C 中的 `ComplexFlag` 为 `mxCOMPLEX`（Fortran 中的 1）时。
- 长度为 `nzmax` 的 `ir` 数组。
- 长度为 `n+1` 的 `jc` 数组。

当你完成使用稀疏 `mxArray` 后，调用 `mxDestroyArray` 来回收其所有堆空间。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `fulltoparse.c`
- `fulltoparse.F`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxDestroyArray` | `mxSetNzmax` | `mxSetIr` | `mxSetJc` | `mxComplexity`

---

# mxCreateSparseLogicalMatrix (C)

## C 语法

```c
#include "matrix.h"
mxArray *mxCreateSparseLogicalMatrix(mwSize m, mwSize n, mwSize nzmax);
```

## 参数

- **m** — 行数
- **n** — 列数
- **nzmax** — `mxCreateSparseLogicalMatrix` 分配用于存储数据的元素数量。`nzmax` 的值应大于或等于你计划放入 `mxArray` 的非零元素数量，但确保 `nzmax` 小于或等于 `m*n`。`nzmax` 大于或等于 1。

## 返回

指向创建的 `mxArray` 的指针。如果在独立程序（非 MEX 文件）应用中失败，返回 `NULL`。如果在 MEX 文件中失败，MEX 文件终止并将控制权返回给 MATLAB 提示符。当没有足够的堆空间来创建 `mxArray` 时，函数失败。

## 描述

使用 `mxCreateSparseLogicalMatrix` 创建一个 `m` 比 `n` 的 `mxLogical` 元素 `mxArray`。`mxCreateSparseLogicalMatrix` 将数组中的每个元素初始化为 0。

在完成使用 `mxArray` 后调用 `mxDestroyArray`。`mxDestroyArray` 会释放 `mxArray` 及其元素。

## 版本历史

R2006a 之前引入

## 另请参阅

`mxCreateLogicalArray` | `mxCreateLogicalMatrix` | `mxCreateLogicalScalar` | `mxCreateSparse` | `mxIsLogical`

---

# mxCreateString (C)

## C 语法

```c
#include "matrix.h"
mxArray *mxCreateString(const char *str);
```

## 描述

使用 `mxCreateString` 创建一个 `mxArray`。

完成使用 `mxArray` 后调用 `mxDestroyArray`。

## 输入参数

### str — 字符串
`const char *`

字符串，指定为 `const char *`。

## 输出参数

### pm — 指向 mxArray 的指针
`mxArray *` | `NULL`

如果成功，则指向一个类型为 `mxChar` 的 `mxArray` 的指针，指定为 `mxArray *`。

当没有足够的可用空间来创建 `mxArray` 时，函数失败。

- **MEX 文件** — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- **独立程序（非 MEX 文件）** — 函数返回 `NULL`。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `revord.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `createarray.c`
- `mxfunction.c`
- `mxclass.c`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxCreateCharArrayFromStr` | `mxCreateCharMatrixFromStr`

---

# mxCreateString (Fortran)

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateString(str)
character(*) str
```

## 描述

使用 `mxCreateString` 创建一个 `mxArray`。

完成使用 `mxArray` 后调用 `mxDestroyArray`。

## 输入参数

### str — 字符串
`character(*)`

字符串，指定为 `character(*)`。

## 输出参数

### pm — 指向 mxArray 的指针
`mwPointer` | `0`

如果成功，则指向一个类型为 `mxChar` 的 `mxArray` 的指针，指定为 `mwPointer`。

当没有足够的可用空间来创建 `mxArray` 时，函数失败。

- **MEX 文件** — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- **独立程序（非 MEX 文件）** — 函数返回 0。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `revord.F`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxCreateCharArrayFromStr` | `mxCreateCharMatrixFromStr`

---

# mxCreateStructArray (C)

## C 语法

```c
#include "matrix.h"
mxArray *mxCreateStructArray(const mwSize *dims, mwSize ndim, int nfields, const char **fieldnames);
```

## 描述

调用 `mxCreateStructArray` 创建一个空的结构 `mxArray`。结构 `mxArray` 的每个元素包含相同数量的字段（由 `nfields` 指定）。每个字段都有名称（由 `fieldnames` 指定）。MATLAB 结构概念上等同于 C 语言中的结构数组。

每个字段包含一个初始化为 `NULL` 的 `mxArray` 指针。调用 `mxSetField` 或 `mxSetFieldByNumber` 将非空的 `mxArray` 指针放入字段中。

函数会自动移除 `dims` 参数指定的末尾维度。例如，如果 `ndim` 等于 5 且 `dims` 等于 `[4 1 7 1 1]`，则结果数组的维度为 4x1x7。

在完成使用 `mxArray` 后调用 `mxDestroyArray` 以释放 `mxArray` 及其关联元素。

## 输入参数

### ndim — 维度数
`mwSize`

维度数，指定为 `mwSize`。如果 `ndim` 小于 2，则 `mxCreateStructArray` 将维度数设置为 2。

### dims — 维度数组
`const mwSize *`

维度数组，指定为数组 `const mwSize *` 包含在该维度上的大小。例如，要创建一个 5 比 7 的数组，将 `dims[0]` 设置为 5 并 `dims[1]` 设置为 7。

通常，`dims` 数组包含 `ndim` 个元素。

### nfields — 字段数
`int`

每个元素中的字段数量，指定为 `int`。

### fieldnames — 字段名称
`const char **`

一个或多个字段名，指定为 `const char **`。

字段名必须是有效的 MATLAB 标识符，这意味着它们不能为 `NULL` 或空。字段名对大小写敏感。要确定字段名的最大长度，请使用 `namelengthmax` 函数。



## 输出参数

pm -- 指向 mxArray 的指针

`mxArray *` | `NULL`

指向 mxArray 的指针，指定为 `mxArray *`。

当没有足够的可用空间来创建 mxArray 时，函数执行失败。

- MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 `NULL`。

## 示例

请查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcreatestructarray.c`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxDestroyArray` | `mxAddField` | `mxRemoveField` | `mxSetField` | `mxSetFieldByNumber` | `namelengthmax`

## mxCreateStructArray (Fortran)

N 维结构数组

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateStructArray(ndim, dims, nfields, fieldnames)
mwSize ndim
mwSize dims(ndim)
integer*4 nfields
character(*) fieldnames(nfields)
```

## Description

调用 `mxCreateStructArray` 创建一个已填充的结构体 mxArray。结构 mxArray 的每个元素包含相同数量的字段，由 `nfields` 指定。每个字段都有一个名称，由 `fieldnames` 指定。

每个字段包含一个初始化为 0 的 mxArray 指针。调用 `mxSetField` 或 `mxSetFieldByNumber` 在字段中放置一个非 0 的 mxArray 指针。

该函数会自动移除 `dims` 参数指定的末尾维度。例如，如果 `ndim` 等于 5 且 `dims` 等于 `[4 7 1 1 1]`，则结果数组的维度为 4x1。

在使用完成 mxArray 后，调用 `mxDestroyArray`。`mxDestroyArray` 函数会释放 mxArray 及其关联元素。

## 输入参数

ndim — 维度数

`mwSize`

维度数，指定为 `mwSize`。如果 `ndim` 小于 2，则 `mxCreateStructArray` 将维度数设置为 2。

dims — 维度数组

array of `mwSize`

维度数组，指定为 `mwSize` 类型的 `ndim` 数组。维度数组中的每个元素包含数组在该维度上的尺寸。例如，要创建一个 5x7 的数组，将 `dims(1)` 设置为 5，`dims(2)` 设置为 7。通常，`dims` 数组包含 `ndim` 个元素。

nfields — 字段数

`integer*4`

每个元素中的字段数，指定为 `integer*4`。

fieldnames — 字段名

`character(*)`

一个或多个字段名，指定为 `character(*)`。字段名必须是有效的 MATLAB 标识符，这意味着它们不能为空。字段名对大小写敏感。要确定字段名的最大长度，请使用 `namelengthmax` 函数。

## 输出参数

pm -- 指向 mxArray 的指针

`mwPointer` | `0`

指向 mxArray 的指针，指定为 `mwPointer`。

当没有足够的可用堆空间来创建 mxArray 时，函数执行失败。

- MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 `0`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxDestroyArray` | `mxAddField` | `mxRemoveField` | `mxSetField` | `mxSetFieldByNumber` | `namelengthmax` | `mxCreateStructMatrix`

## mxCreateStructMatrix (C)

2 维结构数组

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateStructMatrix(mwSize m, mwSize n, int nfields, const char **fieldnames);
```

## Description

调用 `mxCreateStructMatrix` 创建一个未填充的、二维的结构体 mxArray。有关该结构的信息，请参见 `mxCreateStructArray`。

在使用完成 mxArray 后，调用 `mxDestroyArray` 以释放 mxArray 及其关联元素。

## 输入参数

- m — 行数

  `mwSize`

  行数，指定为 `mwSize`。

- n — 列数

  `mwSize`

  列数，指定为 `mwSize`。

- nfields — 字段数

  `int`

  每个元素中的字段数，指定为 `int`。

- fieldnames — 字段名

  `const char **`

  一个或多个字段名，指定为 `const char **`。字段名必须是有效的 MATLAB 标识符，这意味着它们不能为 `NULL` 或空。字段名对大小写敏感。要确定字段名的最大长度，请使用 `namelengthmax` 函数。

## 输出参数

- pm — 指向 mxArray 的指针

  `mxArray *` | `NULL`

  如果成功，指向 mxArray 的指针，指定为 `mxArray *`。当没有足够的可用堆空间来创建 mxArray 时，函数执行失败。

  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 `NULL`。

## 示例

请查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxCreateStructArray` | `namelengthmax`

## mxCreateStructMatrix (Fortran)

2 维结构数组

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxCreateStructMatrix(m, n, nfields, fieldnames)
mwSize m, n
integer*4 nfields
character(*) fieldnames
```

## Description

调用 `mxCreateStructMatrix` 创建一个未填充的、二维的结构体 mxArray。有关该结构的信息，请参见 `mxCreateStructArray`。

在使用完成 mxArray 后调用 `mxDestroyArray`。`mxDestroyArray` 函数会释放 mxArray 及其关联元素。

## 输入参数

- m — 行数

  `mwSize`

  行数，指定为 `mwSize`。

- n — 列数

  `mwSize`

  列数，指定为 `mwSize`。

- nfields — 字段数

  `integer*4`

  每个元素中的字段数，指定为 `integer*4`。

- fieldnames — 字段名

  `character(*)`

  一个或多个字段名，指定为 `character(*)`。字段名必须是有效的 MATLAB 标识符，这意味着它们不能为空。字段名对大小写敏感。要确定字段名的最大长度，请使用 `namelengthmax` 函数。

## 输出参数

- pm -- 指向 mxArray 的指针

  `mwPointer` | `0`

  如果成功，指向 mxArray 的指针，指定为 `mwPointer`。当没有足够的可用空间来创建 mxArray 时，函数执行失败。

  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 `0`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxCreateStructArray` | `mxDestroyArray` | `namelengthmax`

## mxCreateUninitNumericArray (C)

未初始化 N 维数组

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateUninitNumericArray(mwSize ndim, const mwSize *dims, mxClassID classid, mxComplexity ComplexFlag);
```

## Arguments

**ndim** — 维度数。如果你指定的 `ndim` 值小于 2，`mxCreateUninitNumericArray` 将维度数设置为 2。

**dims** — 维度数组。维度数组中的每个元素包含数组在该维度上的尺寸。例如，将 `dims[0]` 设置为 5，`dims[1]` 设置为 7 可创建一个 5x7 的 mxArray。通常，`dims` 数组包含数值元素。

**classid** — 数组类的标识符，决定了数值数据在内存中的表示方式。例如，指定 `mxINT16_CLASS` 会导致 mxArray 中的每个数值数据表示为 16 位符号整数。

**ComplexFlag** — 如果创建的 mxArray 包含虚数，将 `ComplexFlag` 设置为 `mxCOMPLEX`。否则，将 `ComplexFlag` 设置为 `mxREAL`。

## Returns

指向所创建的 mxArray。如果在独立（非 MEX 文件）应用程序中失败，则返回 `NULL`。如果在 MEX 文件中失败，则 MEX 文件将终止并将控制权交回 MATLAB 提示符。当没有足够的可用堆空间来创建 mxArray 时，函数执行失败。

## Description

调用 `mxCreateUninitNumericArray` 创建一个 N 维 mxArray，其中所有数据元素具有由 `classid` 指定的类型。数据元素未初始化。

`mxCreateUninitNumericArray` 分配内存来存储创建的 mxArray。调用 `mxDestroyArray` 释放内存。

下表显示了与 MATLAB 类等价的 C 类值。

| MATLAB 类名 | C classid 值 |
|---|---|
| int8 | `mxINT8_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| single | `mxSINGLE_CLASS` |
| double | `mxDOUBLE_CLASS` |

## 另见

`mxDestroyArray`, `mxCreateUninitNumericMatrix`, `mxCreateNumericArray`

## 版本历史

在 R2015a 中引入

## mxCreateUninitNumericMatrix (C)

未初始化的 2 维数值矩阵

### C 语法

```c
#include "matrix.h"
mxArray *mxCreateUninitNumericMatrix(size_t m, size_t n, mxClassID classid, mxComplexity ComplexFlag);
```

## 参数

**m**

行数

**n**

列数

**classid**

数组类的标识符，它决定了数值数据在内存中的表示方式。例如，指定 `mxINT16_CLASS` 会导致 mxArray 中的每段数值数据都表示为 16 位有符号整数。

**ComplexFlag**

如果你创建的 mxArray 用于包含虚数数据，请将 `ComplexFlag` 设置为 `mxCOMPLEX`。否则，将 `ComplexFlag` 设置为 `mxREAL`。

## 返回

指向已创建的 mxArray 的指针，如果执行成功。如果在独立应用程序（非 MEX 文件）中执行失败，则返回 `NULL`。如果在 MEX 文件中执行失败，则 MEX 文件将终止并将控制权交给 MATLAB 提示符。当没有足够的空堆空间来创建 mxArray 时，该函数视为执行失败。

## 示例

参见 `matlab/extern/examples/mx` 中的这些示例：

- `mxcreateuninitnumericmatrix.c`

## 描述

调用 `mxCreateUninitNumericMatrix` 创建一个 2 维 mxArray，其中所有数据元素都具有由类指定的数值数据类型。数据元素未初始化。

`mxCreateUninitNumericMatrix` 分配动态内存来存储创建的 mxArray。调用 `mxDestroyArray` 来释放该内存。

下表显示了与 MATLAB 类等价的 C 类值。

| MATLAB 类名 | C classid 值 |
| --- | --- |
| int8 | `mxINT8_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| single | `mxSINGLE_CLASS` |
| double | `mxDOUBLE_CLASS` |

## 另见

`mxDestroyArray`, `mxCreateUninitNumericArray`, `mxCreateNumericMatrix`

## 版本历史

在 R2015a 中引入

## mxDestroyArray (C)

释放由 MXCREATE* 函数分配的动态内存

### C 语法

```c
#include "matrix.h"
void mxDestroyArray(mxArray *pm);
```

## 描述

`mxDestroyArray` 为指定的 mxArray 释放内存，包括：

- mxArray 的特征字段，例如尺寸（m 和 n）和类型
- 关联的数据数组，例如稀疏数组的 `ir` 和 `jc`
- 结构体数组的字段
- 元胞数组的单元

不要对以下 mxArray 调用 `mxDestroyArray`：

- 在 MEX 文件的左侧返回
- 由 `mxGetField` 或 `mxGetFieldByNumber` 函数返回
- 由 `mxGetCell` 函数返回

## 输入参数

pm — 指向 mxArray 的指针

`mxArray *`

指向要释放的 mxArray 的指针，指定为 `mxArray *`。如果 `pm` 为 `NULL` 指针，则函数不执行任何操作。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `matrixDivide.c`
- `matrixDivideComplex.c`
- `sincall.c`

参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexcallmatlab.c`
- `mexgetarray.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisclass.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCalloc` | `mxMalloc` | `mxFree` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent`

## mxDestroyArray (Fortran)

释放由 MXCREATE* 函数分配的动态内存

### Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxDestroyArray(pm)
mwPointer pm
```

## 描述

`mxDestroyArray` 为指定的 mxArray 释放内存，包括：

- mxArray 的特征字段，例如尺寸（m 和 n）和类型
- 关联的数据数组，例如稀疏数组的 `ir` 和 `jc`
- 结构体数组的字段
- 元胞数组的单元

不要对以下 mxArray 调用 `mxDestroyArray`：

- 在 MEX 文件的左参数中返回
- 由 `mxGetField` 或 `mxGetFieldByNumber` 函数返回
- 由 `mxGetCell` 函数返回

## 输入参数

pm -- 指向 mxArray 的指针

`mwPointer`

指向要释放的 mxArray 的指针，指定为 `mwPointer`。如果 `pm` 为 `0`，则函数不执行任何操作。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcell.F`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCalloc` | `mxMalloc` | `mxFree` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent`



```fortran
#include "intfrf.h"
subroutine mxDestroyArray(pm)
mwPointer pm
```

## 参数

`pm` — 指向 `mxArray` 的指针

`mwPointer`

指向要释放的 `mxArray` 的指针，指定为 `mwPointer`。如果 `pm` 为 0，则函数不执行任何操作。

## 返回

指向已创建的 `mxArray` 的指针，如果执行成功。如果在独立应用程序（非 MEX 文件）中执行失败，则返回 `NULL`。如果在 MEX 文件中执行失败，则 MEX 文件将终止并将控制权交给 MATLAB 提示符。当没有足够的空堆空间来创建 `mxArray` 时，该函数视为执行失败。

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存。

调用 `mxCreateUninitNumericMatrix` 创建 2 维 `mxArray`，其中所有数据元素都具有由类指定的数值数据类型。数据元素未初始化。

`mxCreateUninitNumericMatrix` 分配动态内存来存储创建的 `mxArray`。调用 `mxDestroyArray` 来释放内存。

下表显示了与 MATLAB 类等等的 C 类值。

| MATLAB 类名 | C classid 值 |
| --- | --- |
| int8 | `mxINT8_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| single | `mxSINGLE_CLASS` |
| double | `mxDOUBLE_CLASS` |

## 另见

`mxDestroyArray`, `mxCreateUnitNumericArray`, `mxCreateNumericMatrix`

## 版本历史

在 R2015a 中引入

## mxDestroyArray (C)

释放由 `MXCREATE*` 函数分配的动态内存

## C 语法

```c
#include "matrix.h"
void mxDestroyArray(mxArray *pm);
```

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存，包括：

- `mxArray` 的特征字段，例如尺寸（`m` 和 `n`）和类型
- 关联的数据数组，例如稀疏数组的 `ir` 和 `j`
- 结构体数组的字段
- 元胞数组的单元

不要对 `myArray` 的左侧参数调用 `mxDestroyArray`：

- 在 MEX 文件的左侧返回
- 由 `mxGetField` 或 `mxGetFieldByIndex` 函数返回
- 由 `mxGetCell` 函数返回

## 输入参数

`pm` — 指向 `mxArray` 的指针

`mxArray *`

指向要释放的 `mxArray` 的指针，指定为 `mxArray *`。如果 `pm` 为 `NULL` 指针，则函数不执行任何操作。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `matrixDivide.c`
- `matrixDivideComplex.c`
- `sincall.c`

参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexcallmatlab.c`
- `mexgetarray.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisclass.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCalloc` | `mxMalloc` | `mxFree` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent`

## mxDestroyArray (Fortran)

释放由 `MXCREATE*` 函数分配的动态内存

## Fortran 语法

```fortran
#include "intfrf.h"
subroutine mxDestroyArray(pm)
mwPointer pm
```

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存，包括：

- `mxArray` 的特征字段，例如尺寸（`m` 和 `n`）和类型
- 关联的数据数组，例如稀疏数组的 `ir` 和 `jc`
- 结构体数组的字段
- 元胞数组的单元

不要对以下 `mxArray` 调用 `mxDestroyArray`：

- 在 MEX 文件的左参数中返回
- 由 `mxGetField` 或 `mxGetFieldByNumber` 函数返回
- 由 `mxGetCell` 函数返回

## 输入参数

- `pm` -- 指向 `mxArray` 的指针

`mwPointer`

指向要释放的 `mxArray` 的指针，指定为 `mwPointer`。如果 `pm` 为 0，则函数不执行任何操作。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcell.F`

## 版本历史

在 R2015a 之前引入

## 另见

`mxCalloc` | `mxMalloc` | `mxFree` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent`

## mxDestroyArray (C)

释放由 `MXCREATE*` 函数分配的动态内存

## C 语法

```c
#include "matrix.h"
mArray *mxCreateArray(mxArray(Array);
```

## Fortran 语法

```fortran
#include "intfrf.h"
subroutine mxDestroyArray(pm)
mwPointer pm
```

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存。

调用 `mxDestroyArray(mxArray)`

## 参数

`pm` — 指向 `mxArray` 的指针

`mxArray *`

指向要释放的 `mxArray` 的指针，指定为 `mxArray *`。如果 `pm` 为 `NULL` 指针，则函数不执行任何操作。

## 返回

指向已创建的 `mxArray` 的指针，如果执行成功。如果在独立应用程序（非 MEX 文件）中执行失败，则返回 `NULL`。如果在 MEX 文件中执行失败，则 MEX 文件将终止并将控制权交给 MATLAB 提示符。当没有足够的空堆空间来创建 `mxArray` 时，该函数视为执行失败。

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存。

调用 `mxCreateUninitNumericMatrix` 创建一个 2 维 `mxArray`，其中所有数据元素都具有由类指定的数值数据类型。数据元素未初始化。

`mxCreateUninitNumericMatrix` 分配动态内存来存储创建的 `mxArray`。调用 `mxDestroyArray` 来释放内存。

下表显示了与 MATLAB 类等等的 C 类值。

| MATLAB 类名 | C classid 值 |
| --- | --- |
| int8 | `mxINT8_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| single | `mxSINGLE_CLASS` |
| double | `mxDOUBLE_CLASS` |

## 另见

`mxDestroyArray`, `mxCreateUnitNumericArray`, `mxCreateNumericMatrix`

## 版本历史

在 R2015a 中引入

## mxDestroyArray (C)

释放由 `MXCREATE*` 函数分配的动态内存

## C 语法

```c
#include "matrix.h"
void mxDestroyArray(mxArray *pm);
```

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存，包括：

- `mxArray` 的特征字段，例如尺寸（`m` 和 `n`）和类型
- 关联的数据数组，例如稀疏数组的 `ir` 和 `j`
- 结构体数组的字段
- 元胞数组的单元

不要对 `myArray` 的左侧参数调用 `mxDestroyArray`：

- 在 MEX 文件的左侧返回
- 由 `mxGetField` 或 `mxGetFieldByIndex` 函数返回
- 由 `mxGetCell` 函数返回

## 输入参数

`pm` — 指向 `mxArray` 的指针

`mxArray *`

指向要释放的 `mxArray` 的指针，指定为 `mxArray *`。如果 `pm` 为 `NULL` 指针，则函数不执行任何操作。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `matrixDivide.c`
- `matrixDivideComplex.c`
- `sincall.c`

参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexcallmatlab.c`
- `mexgetarray.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisclass.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxCalloc` | `mxMalloc` | `mxFree` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent`

## mxDestroyArray (Fortran)

释放由 `MXCREATE*` 函数分配的动态内存

## Fortran 语法

```fortran
#include "intfrf.h"
subroutine mxDestroyArray(pm)
mwPointer pm
```

## 描述

`mxDestroyArray` 为指定的 `mxArray` 释放内存，包括：

- `mxArray` 的特征字段，例如尺寸（`m` 和 `n`）和类型
- 关联的数据数组，例如稀疏数组的 `ir` 和 `jc`
- 结构体数组的字段
- 元胞数组的单元

不要对以下 `mxArray` 调用 `mxDestroyArray`：

- 在 MEX 文件的左参数中返回
- 由 `mxGetField` 或 `mxGetFieldByNumber` 函数返回
- 由 `mxGetCell` 函数返回

## 输入参数

- `pm` -- 指向 `mxArray` 的指针

`mwPointer`

指向要释放的 `mxArray` 的指针，指定为 `mwPointer`。如果 `pm` 为 0，则函数不执行任何操作。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcell.F`

## 版本历史

在 R2015a 之前引入

## 另见

`mxCalloc` | `mxMalloc` | `mxFree` | `mexMakeArrayPersistent` | `mexMakeMemoryPersistent`

## mxDestroyArray (C)

释放由 `MXCREATE*` 函数分配的动态内存

## C 语法

```c
#include "matrix.h"
mArray *mxCreateArray(mxArray(Array);
```

## Fortran 语法

```fortran
#include "intfrf.h"
subroutine mxDestroyArray(pm)
mwPointer pm
```

# mxGetCell (C 和 Fortran)

指向单元格数组中元素的指针

# C 语法

```c
#include "matrix.h"
mxArray *mxGetCell(const mxArray *pm, mwIndex index);
```

# Fortran 语法

```fortran
#include "intrf.h"
mwPointer mxGetCell(pm, index)
mwPointer pm
mwIndex index
```

## 参数

- `pm`: 指向单元格类型 `mxArray` 的指针
- `index`: 单元格类型 `mxArray` 中第一个元素与目标元素之间的元素个数。有关计算多维单元格数组中索引的详细信息，请参见 `mxCalcSingleSubscript`。

## 返回

如果成功，返回第 `i` 个单元格 `mxArray` 的指针。否则在 C 中返回 `NULL`（Fortran 中返回 0）。失败原因包括：

- 指定了尚未填充的单元格数组元素的索引。
- 指定了未指向单元格类型 `mxArray` 的 `pm`。
- 指定了超出 `mxArray` 范围的元素索引。
- 堆空间不足。

不要对 `mxGetCell` 函数返回的 `mxArray` 调用 `mxDestroyArray`。

## 描述

调用 `mxGetCell` 获取单元格类型 `mxArray` 中索引元素持有的 `mxArray` 指针。

> 注意：MX 文件的输入是常量只读的 `mxArrays`。不要修改输入内容。使用 `mxCell*` 或 `mxSetField*` 函数修改 MATLAB 参数的单元格或字段将导致不可预测的结果。

## 示例

请参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

# 另请参见

`mxCreateCellArray`, `mxIsCell`, `mxSetCell`

## 版本历史

在 R2006a 之前引入

# mxGetChars (C)

指向字符数组数据的指针

# C 语法

```c
#include "matrix.h"
mxChar *mxGetChars(const mxArray *array_ptr);
```

## 参数

- `array_ptr`: 指向 `mxArray` 的指针

## 返回

`mxArray` 中第一个字符的指针。如果指定的数组不是字符数组，则返回 `NULL`。

## 描述

调用 `mxGetChars` 访问 `array_ptr` 指的 `mxArray` 中的第一个字符。一旦获取了起始地址，你就可以访问 `mxArray` 中的任何其他元素。

# 另请参见

`mxGetString`

## 版本历史

在 R2006a 之前引入

# mxGetClassID (C)

`mxArray` 的类

# C 语法

```c
#include "matrix.h"
mxGetClassID(const mxArray *pm);
```

## 描述

使用 `GetClassID` 确定 `mxArray` 的类。`mxArray` 的类标识了该 `mxArray` 持有的数据类型。例如，如果 `pm` 指向一个逻辑型 `mxArray`，则 `mxGetClassID` 返回 `mxLOGICAL_CLASS`（在 C 语言中）。

`mxGetClassID` 类似于 `mxGetClassName`，区别在于前者以整数标识符返回类，而后者以字符串返回类。

# 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`): 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

# 输出参数

- `ID` — 类的数值标识符 (`mxClassID`): `mxArray` 的类（类别）的数值标识符，指定为 `mxClassID`。有关 C 语言类标识符的列表，请参见 `mxClassID` 函数。对于用户定义类型，`mxGetClassID` 返回一个标识数组内容类的唯一值。使用 `mxIsClass` 来确定数组是否属于特定的用户定义类型。

## 示例

请参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

请参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

## 版本历史

在 R2006a 之前引入

# 另请参见

`mxClassID` | `mxGetClassName` | `mxIsClass`

# mxGetClassName (C)

字符串格式的 `mxArray` 类

> **注意** 对于未通过 `classdef` 语句定义的类请使用 `mxGetClassName`。

# C 语法

```c
#include "matrix.h"
const char *mxGetClassName(const mxArray *pm);
```

## 描述

`mxGetClassName` 返回 `mxArray` 的类。类标识了 `mxArray` 持有的数据类型。例如，如果 `pm` 指向一个逻辑型 `mxArray`，`mxGetClassName` 返回 `logical`。

`mxClassID` 类似于 `mxGetClassName` 函数。

- `mxGetClassNameID` 以整数标识符返回类，如 `mxClassID` 所示。
- `mxGetClassName` 以字符串返回类，如 `mxIsClass` 所示。

# 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`): 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

# 输出参数

- `name` — 类名 (`const char*`): 类名，指定为 `const char*`。

## 示例



请参见 `matlabroot/extern/examples/mex` 中的这些示例：

- `mexfunction.c`

请参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisclass.c`

## 版本历史

在 R2006a 之前引入

# 另请参见

`mxClassID` | `mxIsClass`

# mxGetClassID (Fortran)

mxArray 的类

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxGetClassID(pm, index)
mwPointer pm
mwIndex index
```

## 描述

使用 `GetClassID` 确定 mxArray 的类。mxArray 的类标识了该 mxArray 持有的数据类型。例如，如果 `pm` 指向一个逻辑型 mxArray，则 `mxGetClassID` 返回 `mxLOGICAL_CLASS`（在 C 语言中）。

`mxGetClassID` 类似于 `mxGetClassName`，区别在于前者以整数标识符返回类，而后者以字符串返回类。

# 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`): 指向 mxArray 数组的指针，指定为 `const mxArray*`。

# 输出参数

- `ID` — 类的数值标识符: mxArray 的类（类别）的数值标识符，指定为 `mxClassID`。有关 C 语言类标识符的列表，请参见 `mxClassID` 函数。对于用户定义类型，`mxGetClassID` 返回一个标识数组内容的唯一值。

## 版本历史

在 R2006a 之前引入

# 另请参见

`mxClassID` | `mxGetClassName` | `mxIsClass`

# mxGetClassName (Fortran)

字符串格式的 mxArray 类

> 注意 对于未通过 `classdef` 语句定义的类请使用 `mxGetClassName`。

# Fortran 语法

```fortran
#include "fintrf.h"
character(*) mxGetClassName
mwPointer pm
```

## 描述

`mxGetClassName` 返回 mxArray 的类。类标识了 mxArray 持有的数据类型。例如，如果 `pm` 指向一个逻辑型 mxArray，`mxGetClassName` 返回 `logical`。

`mxClassID` 类似于 `mxGetClassName` 函数。

- `mxGetClassNameID` 以整数标识符返回类，如 `mxClassID` 所示。
- `mxGetClassName` 以字符串返回类，如 `mxIsClass` 所示。

# 输入参数

- `pm` — MATLAB 数组 (`mwPointer`): 指向 mxArray 的指针。

# 输出参数

- `name` — 类名 (`character(*)`): 类名，指定为 `character(*)`。

## 版本历史

在 R2006a 之前引入

# 另请参见

`mxClassID` | `mxIsClass`

# mxGetData (C)

非字符型 mxArray 中的数据

**注意** 对于数值数组不建议使用 `mxGetData`。请使用类型数据函数。

# C 语法

```c
#include "matrix.h"
void *mxGetData(const mxArray *pm);
```

## 描述

使用 `mxGetData` 获取非字符型数组的元素。对于数值数组，MathWorks 建议你创建 MEX 文件并将现有的 MEX 文件更新为交叉 API。更多信息请参见：

- "Typed Data Access in C"
- "MATLAB Support for Interleaved API in MEX Functions"
- "Upgrade MEX Files"
- Example `explore.c`

要构建 MEX 文件，请使用 `-R2018a` 调用 `mex`。

# 输入参数

- `pm` — 指向非字符型 MATLAB 数组 (`mxArray*`): 数组的指针，指定为 `mxArray*`。

# 输出参数

- `pa` — 指向数据数组 (`void *`): mxArray 内部数据的指针，指定为 `void *`。由于 void 指针没有类型，请将返回值转换为与指定的类型匹配的指针。有关 MATLAB 类型到等效 C 类型的映射，请参见 `mxClassID`。

如果 `pm` 为 `NULL`，则函数返回 `NULL`。

## 版本历史

在 R2006a 之前引入

对于复数 mxArray，转换 `mxGetData` 返回取决于编译选项

行为在 R2018a 发生变化

`mxGetData` 返回 `void` 指针。你的代码必须声明与 mxArray 输入参数类型匹配的指针类型。使用 `mxClassID` 来选择正确的类型。对于复数输入，正确的类型取决于创建 MEX 文件时使用的编译选项。

如果你使用默认版本特定选项 (`-R2017b`) 构建 MEX 文件，则该函数返回指向实部值的指针。

如果你使用 `-R2018a` 选项构建 MEX 文件则：

- 当输入参数 `pm` 指向实型 MATLAB 数组时，该函数返回指向第一个元素的指针。
- 当 `pm` 是复数数组时，该函数返回指向交叉实部和虚部值的指针，而不是实部值。

# 另请参见

`mxClassID`

## 话题

`explore.c`

"Typed Data Access in C MEX Files"

"MATLAB Support for Interleaved API in MEX Functions"

# mxGetData (Fortran)

非数值 mxArray 中的数据元素

> 注意：`mxGetData` 不建议用于数值数组。请使用带类型的数据访问函数。有关更多信息，请参阅“兼容性考虑”。

# Fortran 语法

```fortran
#include <fintrf.h>
mwPointer mxGetData(pm)
mwPointer pm
```

## 描述

仅使用 `mxGetData` 获取非数值数组的数据元素。

对于数值数组，MathWorks 建议您创建 MEX 文件并更新现有 MEX 文件以使用交织复合 API（interleaved complex API）中的带类型数据访问函数。更多信息请参见：

- C MEX 文件中的带类型数据访问
- “MATLAB 支持 MEX 函数中的交织复合 API”
- “升级 MEX 文件以使用交织复合 API”

要构建 MEX 文件，请使用带有 `-R2018a` 选项调用 `mex`。

# 输入参数

- `pm` — 指向非数值 MATLAB 数组的指针 (`mwPointer`): 指向一个非数值 MATLAB 数组的指针，指定为 `mwPointer`。

# 输出参数

- `pa` — 数据数组的指针 (`mwPointer` | 0): 指向 mxArray 内部数据数组的指针，指定为 `mwPointer`。由于 void 指针指向一个没有类型的值，请将返回值强制转换为与 mxArray 指定类型相匹配的指针类型。

要从返回的指针拷贝值，请使用 `mxCopyPtrTo*` 函数。例如：

```fortran
c Get the data in mxArray, pm
   mxCopyPtrToReal(mxGetData(pm),data,
   mxGetNumberOfElements(pm))
```

如果 `pm` 为 0，则该函数返回 0。

# 版本历史

在 R2006a 之前引入

对于复数数值 mxArray，强制转换 `mxGetData` 返回值取决于构建选项

行为在 R2018b 中发生变化

`mxGetData` 函数返回 `mwPointer`。您的代码必须声明与 mxArray 输入参数指定的类型匹配的指针类型。对于复数值输入，正确的类型取决于创建 MEX 文件时使用的构建选项。

如果您使用默认的特定版本选项（`-R2017b`）构建 MEX 文件，则该函数返回指向实部值第一个元素的指针。

如果您使用 `-R2018a` 选项构建 MEX 文件，则：

- 当输入参数 `pm` 指向实数 MATLAB 数组时，函数返回指向数据第一个元素的指针。
- 当 `pm` 是复数数组时，函数返回指向交织实部和虚部值第一个元素的指针，而不是仅实部值的指针。

# 另请参见

## 主题

“C MEX 文件中的带类型数据访问”

“MATLAB 支持 MEX 函数中的交织复合 API”

# mxGetDimensions (C)

指向维度数组的指针

# C 语法

```c
#include "matrix.h"
const mwSize *mxGetDimensions(const mxArray *pm);
```

## 描述

`mxGetDimensions` 返回指向维度数组中第一个元素的指针。每个整数维度数组表示特定维度上的元素数量。该数组没有以 `NULL` 终止。

使用 `mxGetDimensions` 确定它所指向的 mxArray 在每个维度上有多少个元素。调用 `mxGetNumberOfDimensions` 获取 mxArray 的维度数。

# 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`): 指向一个 mxArray 数组的指针，指定为 `const mxArray*`。

## 示例

请查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcalingslesubcript.c`
- `mxgeteps.c`
- `mxisisfinite.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `findnz.c`
- `phonebook.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 版本历史

在 R2006a 之前引入

# 另请参见

`mxGetNumberOfDimensions`

# mxGetDimensions (Fortran)

指向维度数组的指针

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetDimensions(pm)
mwPointer pm
```

## 描述

`mxGetDimensions` 返回指向维度数组中第一个元素的指针。维度数组中的每个整数表示特定维度上的元素数量。该数组没有以 `NULL` 终止。

使用 `mxGetDimensions` 确定 `pm` 指向的 mxArray 在每个维度上有多少个元素。调用 `mxNumberOfDimensions` 获取 mxArray 的维度数。

要将值拷贝到 Fortran 中，请按如下方式使用 `mxCopyPtrToInteger4`：

```fortran
C      Get dimensions of mxArray, pm
       mxCopyPtrToInteger4(mxGetDimensions(pm), dims,
       mxNumberOfDimensions(pm))
```

# 输入参数

- `pm` — MATLAB 数组 (`mwPointer`): 指向一个 mxArray 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

# 另请参见

`mxGetNumberOfDimensions`

# mxGetElementSize (C)

存储每个数据元素所需的字节数

**注意** 对于使用交织复合 API 构建的复数 mxArray，`mxGetElementSize` 返回的是独立复合 API 中函数返回值的两倍。更多信息，请参阅“兼容性考虑”。

# C 语法

```c
#include "matrix.h"
size_t mxGetElementSize(const mxArray *pm);
```

## 描述

调用 `mxGetElementSize` 确定 mxArray 中每个数据元素的字节数。例如，如果 mxArray 的 MATLAB 类是 `int16`，则 mxArray 将每个元素存储为 16 位（2 字节）有符号整数。因此，`mxGetElementSize` 返回 2。

当使用非 MATLAB 程处理数据时，`mxGetElementSize` 非常有用。

# 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`): 指向一个 mxArray 的指针，指定为 `const mxArray*`。

# 输出参数

- `nbytes` — 字节数 (`size_t`|0): 存储 mxArray 中一个元素的字节数，返回值为 `size_t`。

如果 `pm` 是复数，则输出取决于您使用的版本：

- 如果您使用交织复合 API（`-R2018a`）构建，则函数返回数据类型的字节数。
- 如果您使用独立复合 API（`-R2017b`）构建，则无论数组是复数还是实数，都返回字节数。

失败时返回 0。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `double.c`
- `phonebook.c`

## 版本历史

在 R2006a 之前引入

```
mxElementSize 根据选项返回不同的值
```

对于复数数值 mxArray，`mxElementSize` 根据选项返回不同的值。更多信息，请参阅输出参数 `nbytes`。

# 另请参见

`mxGetM` | `mxGetN`

# mxGetElementSize (Fortran)

存储每个数据元素所需的字节数

**注意** 对于使用交织复合 API 构建的复数 mxArray，`mxGetElementSize` 返回的是独立复合 API 中函数返回值的两倍。更多信息，请参阅“兼容性考虑”。

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetElementSize(pm)
mwPointer pm
```

## 描述

调用 `mxGetElementSize` 确定 mxArray 中每个数据元素的字节数。例如，如果 mxArray 的 MATLAB 类是 `int16`，则 mxArray 将每个元素存储为 16 位（2 字节）有符号整数。因此，`mxGetElementSize` 返回 2。

当使用非 MATLAB 程序处理数据时，`mxGetElementSize` 非常帮助。

注意 Fortran 没有 `size_t` 等类型，`mwPointer` 是提供相应 Fortran 类型的预处理器宏。然而，该函数的返回值并不是指针。

# 输入参数

- `pm` — MATLAB 数组 (`mwPointer`): 指向一个 mxArray 数组的指针，指定为 `mwPointer`。

# 输出参数

- `nbytes` — 字节数 (`integer*4`|0): 存储指定 mxArray 中一个元素的字节数，返回值为 `integer*4`。

如果 `pm` 是复数，则输出参数取决于您使用的 Fortran Matrix API 版本：

- 如果您使用独立复合 API（`-R2017b` 选项）构建，则无论数组是复数还是实数，都返回数据类型的字节数。
- 如果您使用交织复合 API（`-R2018a` 选项）构建，则返回值为数据类型字节数的两倍。

如果 `pm` 指向一个单元格或结构，则 `mxGetElementSize` 返回指针的大小。该函数不返回单元格或结构中所有元素的大小。

失败时返回 0。失败的主要原因是 `pm` 指向一个具有未识别类别的 `mxArray`。

## 版本历史

在 R2006a 之前引入

`mxGetElementSize` 根据编译选项返回不同的值

行为在 R2018b 中发生变化

对于复杂的数值数组 `myArray`，`mxGetElementSize` 函数根据 mex 编译选项返回不同的值。更多信息，请参阅 `nbytes` 输出参数。

## 另请参见

`mxGetM` | `mxGetN`

# mxGetEps (C 和 Fortran)

## EPS 的值

# C 语法

```c
#include "matrix.h"
double mxGetEps(void);
```

# Fortran 语法

```fortran
real*8 mxGetEps
```

## 返回

MATLAB 变量 `eps` 的值

## 描述

调用 `mxGetEps` 返回 MATLAB `eps` 变量的值。该变量保存了 1.0 到下一个最大浮点数之间的距离。因此，它是浮点精度的衡量标准。MATLAB 的 `pinv` 和 `rank` 函数使用 `eps` 作为默认容差。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxgeteps.c`
- `mxgetepsf.F`

## 另请参见

`mxGetInf`, `mxGetNan`

## 版本历史

在 R2006a 之前引入

# mxGetField (C 和 Fortran)

给定索引和字段名，返回指向结构数组中字段值的指针

# 语法

```c
#include "matrix.h"
mxArray *mxGetField(const mxArray *pm, mwIndex index, const char *fieldname);
```

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetField(pm, index, fieldname)
mwPointer pm
mwIndex index
character*(*) fieldname
```

## 参数

- `pm`: 指向结构体 `mxArray` 的指针
- `index`: 所需元素的索引。

在 C 中，`mxArray` 的第一个元素的索引为 0。最后一个元素的索引为 N-1，其中 N 是数组中的元素数量。在 Fortran 中，`mxArray` 的第一个元素的索引为 1。最后一个元素的索引为 N，其中 N 是数组中的元素数量。

- `fieldname`: 想要提取的值的所属字段名。

## 返回



# mxGetField (C 和 Fortran)

## 返回

成功时，返回指定 `fieldname` 下指定字段的 `mxArray` 指针。如果传递了无效参数，或者指定的字段没有分配任何值，则在 C 中返回 NULL（在 Fortran 中返回 0）。常见的失败原因：

- 指定了一个未指向结构体 `mxArray` 的数组指针 `pm`。要确定 `pm` 是否指向结构体 `mxArray`，请调用 `mxIsStruct`。
- 指定了超出 `mxArray` 范围的索引。例如，给定一个包含 10 个元素的结构体 `mxArray`，在 C 中不能指定大于 9 的索引（Fortran 中为 10）。
- 指定了不存在的 `fieldname`。调用 `mxGetFieldNameByNumber` 或 `mxGetFieldNumber` 获取现有的字段名。
- 堆空间不足。

## 描述

调用 `mxGetField` 获取指定字段的指定元素中包含的值。在伪 C 术语中，`mxGetField` 返回此处的值：

`pm[index].fieldname`

`mxGetFieldByNumber` 类似于 `mxGetField`。两个函数返回相同的值。唯一的区别在于指定字段的方式。`mxGetFieldByNumber` 将字段编号作为第三个参数，而 `mxGetField` 将字段名作为第三个参数。

不要对 `mxGetField` 函数返回的 `mxArray` 调用 `mxDestroyArray`。

注意：MX 文件的输入是常量只读的 `mxArray`。不要修改输入内容。使用 `mxSetCell*` 或 `mxSetField*` 函数修改 MATLAB 参数的单元格或字段会导致不可预测的结果。

在 C 中，调用：

```c
mxGetField(pa, index, "field_name");
```

等同于调用：

```c
field_num = mxGetFieldByNumber(pa, "field_name");
mxGetFieldByNumber(pa, index, field_num);
```

其中，如果你有一个 1x1 的结构体，`index` 为 0。

在 Fortran 中，调用：

```fortran
mxGetField(pm, index, 'fieldname')
```

等同于调用：

```fortran
fieldnum = mxFieldNumber(pm, 'fieldname')
mxGetFieldByNumber(pm, index, fieldnum)
```

其中，如果你有一个 1x1 的结构体，`index` 为 1。

## 示例

参见 `matlabroot/extern/examples/eng_mat` 中的后续示例。

- `matreadstructarray.c`

## 另见

`mxGetFieldByNumber`, `mxGetFieldNameByNumber`, `mxGetFieldNumber`, `mxGetNumberOfFields`, `mxStruct`, `mxSetField`, `mxSetFieldByNumber`

## 版本历史

在 R2006a 之前引入

# mxGetFieldByNumber (C 和 Fortran)

给定索引和字段编号，返回指向结构数组中字段值的指针

## C 语法

```c
#include "matrix.h"
mxArray *mxGetFieldByNumber(const mxArray *pm, mwIndex index, int fieldnumber);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetFieldByNumber(pm, index, fieldnumber)
mwPointer pm
mwIndex index
integer*4 fieldnumber
```

## 参数

- `pm`：指向结构体 `mxArray` 的指针
- `index`：所需元素的索引。在 C 中，`mxArray` 的第一个元素的索引为 0。最后一个元素的索引为 N-1，其中 N 是数组中的元素数量。在 Fortran 中，`mxArray` 的第一个元素的索引为 1。最后一个元素的索引为 N，其中 N 是数组中的元素数量。有关计算索引的详情，请参见 `mxGetSingle`。
- `fieldnumber`：想要提取的字段的位置。在 C 中，每个元素内的第一个字段的编号为 0，第二个字段的编号为 1，以此类推。最后一个字段的编号为 N-1，其中 N 是字段的总数。在 Fortran 中，每个元素内的第一个字段编号为 1，第二个字段的编号为 2，以此类推。最后一个字段的编号为 N，其中 N 是字段的总数。

## 返回

成功时，返回所需元素指定字段的 `mxArray` 指针。如果传递了无效参数或指定的字段没有分配任何值，则在 C 中返回 NULL（在 Fortran 中返回 0）。常见的失败原因包括：

- 指定了一个未指向结构体 `mxArray` 的数组指针 `pm`。调用 `mxIsStruct` 来确定 `pm` 是否指向结构体 `mxArray`。
- 指定了超出 `mxArray` 字段数量范围的值。例如，给定包含 10 个元素的结构，在 C 中不能指定大于 9 的索引（Fortran 中为 10）。
- 指定了不存在的字段编号。调用 `mxFieldNumber` 获取对应的字段名。

## 描述

调用 `mxGetFieldNameByNumber` 获取给定结构体 `mxArray` 中字段的名字。`mxGetFieldNameByNumber` 的典型用法是在循环内部调用，以获取给定 `mxArray` 中所有字段的。

考虑一个初始化为如下 MATLAB 结构体：

```matlab
patient.name = 'John Doe';
patient.billing = 127.00;
patient.test = [79 75 73; 180 178 177.5; 220 210 205];
```

在 C 语言中，字段编号 0 代表字段名；字段编号 1 代表账单（billing）；字段编号 2 代表测试（test）。非 0、1 或 2 的字段编号将导致 `mxGetFieldNameNumber` 返回 NULL。

在 Fortran 语言中，字段编号 1 代表字段名；字段编号 2 代表账单（billing）；字段编号 3 代表测试（test）。非 1、2 或 3 的字段编号将导致 `mxGetFieldNameNumber` 返回 0。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisclass.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 另见

`mxGetField`, `mxGetFieldNameNumber`, `mxGetFieldNameNumber`, `mxGetNumberOfFields`, `mxIsStruct`, `mxSetField`, `mxSetFieldNameNumber`

## 版本历史

2006a 之前引入

# mxGetFieldNumber (C 和 Fortran)

根据字段名从结构数组获取字段编号

## C 语法

```c
#include "matrix.h"
int mxGetFieldNumber(const mxArray *pm, const char *fieldname);
```

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxGetFieldNumber(pm, fieldname)
mwPointer pm
character(*) fieldname
```

## 参数

- `pm`：指向结构体 `mxArray` 的指针
- `fieldname`：结构体 `mxArray` 中的字段名称

## 返回

成功时返回指定字段 `fieldname` 的字段编号。在 C 语言中，第一个字段的编号为 0，第二个字段的编号为 1，依此类推。在 Fortran 中，第一个字段的编号为 1，第二个字段的编号为 2。失败时 C 中返回 -1（Fortran 中返回 0）。常见的失败原因：

- 指定的数组指针未指向结构体 `mxArray`。调用 `mxIsStruct` 来确定 `pm` 是否指向结构体 `mxArray`。
- 指定了不存在的字段 `fieldname`。

## 描述

如果你知道字段名称但不知道其字段编号，请调用 `mxGetFieldNumber`。相反，如果你知道字段编号但不知道其字段名称，请调用 `mxGetFieldNameByNumber`。

例如，初始化如下的 MATLAB 结构体：

```matlab
patient.name = 'John Doe';
patient.billing = 127.00;
patient.test = [79 75 73; 180 177.5; 220 210 205];
```

在 C 语言中，字段 name 的编号为 0；字段 billing 的编号为 1；如果你调用 `mxGetFieldNumber` 并指定了除 name、billing 或 test 以外的任何字段名，`mxGetFieldNumber` 将返回 -1。

如果你有一个 1-by-1 的结构体，那么调用：

```c
mxGetField(pa, index, "field_name");
```

等同于调用：

```c
field_num = mxGetFieldNumber(pa, "field_name");
mxGetFieldByNumber(pa, index, field_num);
```

其中 `index` 为 0。

在 Fortran 语言中，字段 name 的编号为 1；字段 billing 的编号为 2；字段 test 的编号为 3。如果你调用 `mxGetFieldNumber` 并指定了除 name、billing 或 test 以外的任何字段名，`mxGetFieldNumber` 将返回 0。

如果你有一个 1-by-1 的结构体，那么调用：

```fortran
mxGetField(pm, index, 'fieldname');
```

等同于调用：

```fortran
fieldnum = mxGetFieldNumber(pm, 'fieldname')
mxGetFieldByNumber(pm, index, fieldnum)
```

其中 `index` 为 1。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcreatstructarray.c`

## 另见

`mxGetField`, `mxGetFieldByNumber`, `mxGetFieldNameByNumber`, `mxGetNumberOfFields`, `mxIsStruct`, `mxSetField`, `mxSetFieldByNumber`

## 版本历史

R2006a 之前引入

# mxGetImagData (C)

数值型 `mxArray` 中的虚部数据元素

注意：`mxGetImagData` 在交错复数 API（interleaved complex API）中不可用。请使用类型数据访问函数。更多信息请参阅“兼容性考虑”。

## C 语法

```c
#include "matrix.h"
void *mxGetImagData(const mxArray *pm);
```

## 描述

`mxGetImagData` 函数与 `mxGetPi` 类似，但在 C 语言中它返回一个 `void *`。更多信息请参阅 `mxGetData` 的描述。

## 输入参数

- `pm` — 指向 MATLAB 数组的指针，`mxArray *`，指向 MATLAB 数组，指定为 `mxArray *`。

## 输出参数

- `pi` — 指向复数数据数组的指针，`void *` | `NULL`，指向 `mxArray` 内部的复数数据数组，指定为 `void *`。由于 void 指针指向没有类型的值，请将返回值转换为与 `pm` 指定类型相匹配的指针类型。有关 MATLAB 类型到等效 C 类型的映射信息，请参阅 `mxClassID`。如果 `pm` 为 NULL，该函数返回 NULL。复数支持：是

## 版本历史

R2006a 之前引入

### 不要使用独立的复数 API

从 R2018a 开始不建议使用

MathWorks 建议你创建 MEX 文件并更新现有的 MEX 文件，以使用交错复数 API 中的类型数据访问函数。这些函数会验证输入数组是否为复数以及是否符合函数的类型。更多信息请参阅：

- C MEX 文件中的类型数据访问
- MATLAB 对 MEX 函数中交错复数 API 支持
- 将 MEX 文件升级以使用交错复数 API
- 示例 `explore.c`

要构建 MEX 文件，请使用带有 `-R2018a` 选项调用 `mex`。

### 使用交错复数 API 构建 mxGetImagData 错误

从 R2018a 开始的错误

`mxGetImagData` 函数仅在独立的复数 API 中可用。使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2017b myMexFile.c
```

使用此函数构建的现有 MEX 文件将继续运行。

## 另见

`mxClassID`

## 主题

- `explore.c`
- "C MEX 文件中的类型数据访问"
- "MATLAB 对 MEX 函数中交错复数 API 支持"

# mxGetImagData (Fortran)

数值型 `complexArray` 中的虚部数据元素

注意：`mxGetImagData` 在交错复数 API 中不可用。请使用类型数据访问函数。更多信息请参阅“兼容性考虑”。

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetImagData(pm)
mwPointer pm
```

## 描述

`mxGetImagData` 函数与 `mxGetPi` 类似，但它返回 `mwPointer`。更多信息请参阅 `mxGetData` 函数。

## 输入参数

- `pm` — 指向 MATLAB 数组的指针，`mwPointer`，指向 MATLAB 数组，指定为 `mxArray *`。

## 输出参数

- `pi` — 指向复数数据数组的指针，`mwPointer`，指向 `mxArray` 内部的复数数据数组，指定为 `void *`。由于 void 指针指向没有类型的值，请将返回值转换为与 `pm` 指定类型相匹配的指针类型。如果 `pm` 为 0，该函数返回 0。复数支持：是

## 版本历史

2006a 之前引入

### 从 R2018a 开始不建议使用

不要使用独立的复数 API

请使用类型数据访问函数。这些函数会验证输入数组是否为复数以及是否符合函数的类型。更多信息请参阅：

- C MEX 文件中的类型数据访问
- MATLAB 对 MEX 函数中交错复数 API 支持
- 将 MEX 文件升级以使用交错复数 API

要构建 MEX 文件，请使用带有 `-R2018a` 选项调用 `mex`。

### 使用交错复数 API 构建 mxGetImagData 错误

从 R2018a 开始的错误

`mxGetImagData` 函数仅在独立的复数 API 中可用。使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2017b myMexFile.c
```

使用此函数构建的现有 MEX 文件将继续运行。

## 另见

`mxClassID`

## 主题

- "C MEX 文件中的类型数据访问"
- "将 MEX 文件升级以使用交错复数 API"

# mxGetInf (C 和 Fortran)

无穷值

## C 语法

```c
#include "matrix.h"
double mxGetInf(void);
```

## Fortran 语法

```fortran
real*8 mxGetInf
```

## 返回

系统上的无穷值

调用 `mxGetInf` 返回 MATLAB 内部变量 `inf` 的值。`inf` 是一个代表 IEEE 算术正无穷的永久变量。系统指定 `inf` 的值；你无法修改它。

返回无穷值的操作包括：

- 除以 0。例如，5/0 返回无穷大。
- 导致溢出的操作。例如，`exp(10000)` 返回无穷大，因为结果太大无法在你的机器上表示。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxgetinf.c`

## 另见

`mxGetEps`, `mxGetNaN`

## 版本历史

R2006a 之前引入

# mxGetIr (C 和 Fortran)

稀疏矩阵 ir 数组

## C 语法

```c
#include "matrix.h"
mwIndex *mxGetIr(const mxArray *pm);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetIr(pm)
mwPointer pm
```

## 参数

- `pm`：指向稀疏 `mxArray` 的指针

## 返回

如果成功，则返回 ir 数组第一个元素的指针；否则在 C 中返回 NULL（在 Fortran 中返回 0）。

可能出现的失败情况包括：

- 指定了全矩阵（非稀疏）`mxArray`。
- 指定的 `pm` 值为 NULL（在 C 中，在 Fortran 中为 0）。这种失败通常意味着早之前的调用 `mxCreateSparse` 失败了。

## 描述

使用 `mxGetIr` 获取 ir 数组的起始地址。ir 数组是一个整数数组。ir 的长度为 `nzmax`（为稀疏数组分配的存储空间大小）或 `nnz`（非零元素的数量）。例如，如果 `nzmax` 等于 100，则 ir 数组包含 100 个整数。



ir 数组中的每个值表示可以找到非零元素的行（偏移量 1）。`jc` 数组是一个间接指定包含非零元素的列的索引。

关于 `ir` 和 `jc` 数组的详情，请参阅 `mxSetJc`。

## 示例

参考 `matlab/extern/examples/refbook` 中的这些示例：

- `fullsparse.c`
- `fullsparse.F`

参考 `matlab/extern/examples/mx` 中的这些示例：

- `mxsetdimensions.c`
- `mxsetnzmax.c`

参考 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 另

`mxGetJc`, `mxGetNzmax`, `mxSetIr`, `mxSetJc`, `mxSetNzmax`, `nzmax`, `nnz`

## 版本历史

在 R2006a 之前引入

# mxGetJc (C 和 Fortran)

稀疏矩阵 Jc 数组

## C 语法

```c
#include "matrix.h"
mwIndex *mxGetJc(const mxArray *pm);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mPointer mxGetJc(pm)
mwPointer pm
```

## 参数

- `pm`: 指向稀疏 `mxArray` 的指针

## 返回

如果成功，则返回 `jc` 数组第一个元素的指针；否则在 C 中返回 `NULL`（在 Fortran 中返回 0）。

可能导致失败的原因包括：

- 指定了全矩阵（非稀疏）`mxArray`。
- 指定的 `pm` 值为 `NULL`（在 C 中，在 Fortran 中为 0）。这种失败通常意味着早之前的调用 `mxCreateSparse` 失败了。

## 描述

使用 `mxGetJc` 获取 `jc` 数组的起始地址。`jc` 数组是一个具有 n+1 个元素的整数数组，其中 n 是稀疏 `mxArray` 的列数。`jc` 数组中的值间接指示包含非零元素的列。关于 `jc` 数组的详细解释，请参阅 `mxSetJc`。

## 示例

参考 `matlab/extern/examples/refbook` 中的这些示例：

- `fulltosparse.c`
- `fulltosparse.F`

参考 `matlab/extern/examples/mx` 中的这些示例：

- `mxgetnzmax.c`
- `mxsetdimensions.c`
- `mxsetnzmax.c`

参考 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 另

`mxGetIr`, `mxGetNzmax`, `mxSetIr`, `mxSetJc`, `mxSetNzmax`

## 版本历史

在 R2006a 之前引入

# mxGetLogicals (C)

指向逻辑数组数据的指针

## C 语法

```c
#include "matrix.h"
mxLogical *mxGetLogicals(const mxArray *array_ptr);
```

## 参数

- `array_ptr`: 指向 `mxArray` 的指针

## 返回

指向 `mxArray` 中第一个逻辑元素的指针。如果 `mxArray` 不是逻辑数组，则结果未定义。

## 描述

调用 `mxGetLogicals` 访问 `array_ptr` 指向的 `mxArray` 中的第一个逻辑元素。一旦获取了起始地址，就可以访问 `mxArray` 中的任何元素。

## 示例

参考 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxislogical.c`

## 另

`mxLogicalArray`, `mxLogicalMatrix`, `mxLogicalScalar`, `mxIsLogical`, `mxIsLogicalScalar`, `mxIsLogicalTrue`

## 版本历史

在 R2006a 之前引入

# mxGetM (C)

`mxArray` 的行数

## C 语法

```c
#include "matrix.h"
size_t mxGetM(const mxArray *pm);
```

## 描述

`mxGetM` 返回指定数组的行数。无论数组有多少个维度，“行”始终指数组的第一维度。例如，如果 `pm` 指向一个 8x9x5x3 的四维数组，`mxGetM` 返回 8。

## 输入参数

- `pm` - MATLAB 数组 (`const mxArray*`) 指向 `mxArray` 数组，指定为 `const mxArray*`

## 示例

参考 `matlabroot/extern/examples/refbook` 中的这些示例：

- `convex.c`
- `fulltoparse.c`
- `matrixDivide.c`
- `matrixComplex.c`
- `revord.c`
- `timestwo.c`
- `xtimesy.c`

参考 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxalloc.c`
- `mxsetdimensions.c`
- `mxgetznmax.c`
- `mxsetnzmax.c`

参考 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`
- `mexlock.c`
- `yprime.c`

## 版本历史

在 R2006a 之前引入

## 另

`mxGetM` | `mxSetM` | `mxSetN`

# mxGetM (Fortran)

`mxArray` 的行数

## Fortran 语法

```fortran
#include <fintrf.h>
mwPointer mxGetM(pm)
mwPointer pm
```

## 描述

`mxGetM` 返回指定数组的行数。无论数组有多少个维度，“行”始终指数组的第一维度。例如，如果 `pm` 指向一个 8x9x5x3 的四维数组，`mxGetM` 返回 8。

> 注意：Fortran 没有对应的 `size_t`；`mwPointer` 是提供适当 Fortran 类型的预处理器宏。然而，该函数的返回值并不是指针。

## 输入参数

- `pm` — MATLAB 数组 (`mwPointer`) 指向 `mxArray` 数组，指定为 `mwPointer`

## 示例

参考 `matlabroot/extern/examples/refbook` 中的这些示例：

- `convin.F`
- `dblmat.F`
- `fulltosparse.F`
- `matsq.F`
- `timestwo.F`
- `xtimesy.F`

参考 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matdemo2.F`

## 版本历史

在 R2006a 之前引入

## 另

`mxGetN` | `mxSetM` | `mxSetN`

# mxGetN (C)

`mxArray` 的列数

## C 语法

```c
#include "matrix.h"
size_t mxGetN(const mxArray *pm);
```

## 描述

`mxGetN` 返回指定 `mxArray` 的列数。

如果 `pm` 是一个 N 维 `mxArray`，`mxGetN` 是第 2 到第 N 维的积。例如，如果 `pm` 指向一个 13x5x4x6 的四维 `mxArray`，`mxGetN` 返回值 120 (5 x 4 x 6)。如果指定的 `mxArray` 超过两个维度，请调用 `mxGetDimensions` 查看每个维度的大小。

如果 `pm` 指向稀疏 `mxArray`，`mxGetN` 仍然返回列数，而不是占用列数。

## 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`) 指向 `mxArray` 数组，指定为 `const mxArray*`

## 示例

参考 `matlabroot/extern/examples/refbook` 中的这些示例：

- `convec.c`
- `fullsparse.c`
- `revord.c`
- `timestwo.c`
- `xtimesy.c`

参考 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxalloc.c`
- `mxsetdimensions.c`
- `mxgetznmax.c`
- `mxsetnzmax.c`

参考 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`
- `mexlock.c`
- `yprime.c`
- `matdemo2.F`

## 版本历史

在 R2006a 之前引入

## 另

`mxGetM` | `mxGetDimensions` | `mxSetM` | `mxSetN`

# mxGetN (Fortran)

`mxArray` 的列数

## Fortran 语法

```fortran
#include "fintrf.h"
mwmPointer mxGetN(pm)
mwmPointer pm
```

## 描述

`mxGetN` 返回指定 `mxArray` 的列数。

如果 `pm` 是一个 N 维 `mxArray`，`mxGetN` 是第 2 到第 N 维的积。例如，如果 `pm` 指向一个 13x5x4x6 的四维 `mxArray`，`mxGetN` 返回值 120 (5 x 4 x 6)。如果指定的 `mxArray` 超过两个维度，请调用 `mxGetDimensions` 查看每个维度的大小。

如果 `pm` 指向稀疏 `mxArray`，`mxGetN` 仍然返回列数，而不是占用列数。

> 注意：Fortran 没有对应的 `size_t`；`mwmPointer` 是提供适当 Fortran 类型的预处理器宏。然而，该函数的返回值并不是指针。

## 输入参数

- `pm` — MATLAB 数组 (`mwmPointer`) 指向 `mxArray` 数组，指定为 `mwmPointer`

## 示例

参考 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matdemo2.F`

## 版本历史

在 R2006a 之前引入

## 另

`mxGetN` | `mxSetM` | `mxSetN`

## mxGetNaN (C 和 Fortran)

NaN（非数字）的值

## C 语法

```c
#include "matrix.h"
double mxGetNaN(void);
```

## Fortran 语法

```fortran
real*8 mxGetNaN
```

## 返回

您系统中的 NaN（非数字）值

## 描述

调用 `mxGetNaN` 获取您系统的 NaN 值。NaN 是 IEEE 算术中对“非数字”的表示。某些数学运算会返回 NaN 作为结果，例如：

- `0.0/0.0`
- `Inf-Inf`

您的系统指定了“非数字”的值。您无法对其进行修改。

## C 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxgetinf.c`

## 另另

`mxGetEps`, `mxGetInf`

## 版本历史

在 R2006a 之前引入

## mxGetNumberOfDimensions (C)

`mxArray` 中的维度数

## C 语法

```c
#include "matrix.h"
mwSize mxGetNumberOfDimensions(const mxArray *pm);
```

## 描述

`mxGetNumberOfDimensions` 返回指定的 `mxArray` 中的维度数。返回值始终为 2 或更大。

要确定每个维度中有多少个元素，请调用 `mxGetNumberOfDimensions`。

## 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`)

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `findnz.c`
- `fullsparse.c`
- `phonebook.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcalcsingsubcript.c`
- `mxgeteps.c`
- `mxisfinite.c`

## 版本历史

在 R2006a 之前引入

## 另请

`mxSetM` | `mxSetN` | `mxGetDimensions`

## mxGetNumberOfOfDimensions (Fortran)

`mxArray` 中的维度数

## Fortran 语法

```fortran
#include "intrff.h"
mwSize mxGetNumberOfOfDimensions(pm)
mwPointer pm
```

## 描述

`mxGetNumberOfOfDimensions` 返回指定的 `mxArray` 中的维度数。返回值始终为 2 或更大。

要确定每个维度中有多少个元素，请调用 `mxGetDimensions`。

## 输入参数

- `pm` — MATLAB 数组 (`mwPointer`)

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请

`mxSetM` | `mxSetN` | `mxGetDimensions`

## mxGetNumberOfElements (C)

数值型 `mxArray` 中的元素个数

## C 语法

```c
#include "matrix.h"
size_t mxGetNumberOfElements(const mxArray *pm);
```

## 描述

`mxGetNumberOfElements` 返回指定的 `mxArray` 中的元素个数，返回类型为 `size_t`。例如，如果数组的维度是 3x5x10，那么 `mxGetNumberOfElements` 返回数字 150。

## 输入参数

- `pm` — MATLAB 数组 (`const mxArray*`)

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `findnz.c`
- `phonebook.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcalcinglesubcript.c`
- `mxgeteps.c`
- `mxgetinf.c`
- `mxisfinite.c`
- `mxsetdimensions.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 版本历史

在 R2006a 之前引入

## 另请

`mxGetDimensions` | `mxGetM` | `mxGetN` | `mxGetClassID` | `mxGetClassName`

## mxGetNumberOfElements (Fortran)

数值型 `mxArray` 中的元素个数

## Fortran 语法

```fortran
#include "fintrf.h"
wmPointer mxGetNumberOfElements(pm)
mwPointer pm
```

## 描述

`mxGetNumberOfElements` 返回指定的 `mxArray` 中的元素个数，返回相应的 Fortran 类型。例如，如果数组的维度是 3x5x10，`mxGetNumberOfElements` 返回数字 150。

> 注意：Fortran 没有等同于 `size_t` 的类型，`mwPointer` 是一个预处理器宏，提供相应的 Fortran 类型。然而，此函数通过此预处理器返回的值并不是指针。

## 输入参数

- `pm` — MATLAB 数组 (`mwPointer`)

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxgetepsf.F`
- `mxsetdimensionsf.F`

## 版本历史

在 R2006a 之前引入

## 另请

`mxGetDimensions` | `mxGetM` | `mxGetN` | `mxGetClassID` | `mxGetClassName`

## mxGetNumberOfFields (C 和 Fortran)

结构体数组中的字段数

## C 语法

```c
#include "matrix.h"
int mxGetNumberOfFields(const mxArray *pm);
```

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxGetNumberOfFields(pm)
mwPointer pm
```

## 参数

- `pm` — MATLAB 数组 (`mwPointer`)

指向 `mxArray` 数组的指针。

## 返回

成功时返回字段数。失败时返回 0。最常见的原因是 `pm` 不是结构体。

## 描述

调用 `mxGetNumberOfFields` 确定指定的 `mxArray` 中的字段数。使用 `mxIsStruct` 判断 `pm` 是否为结构体。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxclass.c`
- `explore.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## 另请

`mxGetField`, `mxIsStruct`, `mxSetField`

## 版本历史

在 R2006a 之前引入

## mxGetNzmax (C 和 Fortran)

稀疏矩阵 (IR) 和数组中的元素个数

## C 语法



# mxGetNzmax

## C 语法

```c
#include "matrix.h"
mwSize mxGetNzmax(const mxArray *pm);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwSize mxGetNzmax(pm)
mwPointer pm
```

## 参数

- `pm` — MATLAB 数组 (`mwPointer`)

指向 `mxArray` 数组的指针。

## 返回

成功时返回指定的 `mxArray` 中的元素个数。失败时返回 0。最常见的原因是 `pm` 不是稀疏矩阵。

## 描述

使用 `mxGetNzmax` 获取指定的 `mxArray` 中的元素个数。该值始终大于或等于列数。MATLAB 会调整 `nzmax`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxgeteps.c`
- `mxsetdimensions.c`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxSetNzmax`

---

# mxGetPi (C)

（不推荐）`DOUBLE_CLASS` 中的虚部

## C 语法

```c
#include "matrix.h"
mxDouble *mxGetPi(const mxArray *pm);
```

## 描述

**注意** `mxGetPi` 在交叉 API 中不可用。请使用 `mxComplexDoubles`。更多信息请参阅“兼容性考虑”。

在使用独立 API 构建 MEX 时，调用 `mxGetPi` 获取 `pi` 字段的内容。`pi` 是包含 `mxArray` 虚数据的数组。对于其他数值类型，请使用 `ImagData`。

此函数验证输入是否为复数且类型为 `DOUBLE_CLASS`。使用 `mxIsComplex` 判断数据是否为复数。

## 输入参数

- `pi` — MATLAB 数组 (`mxArray*`)

指向类型为 `DOUBLE_CLASS` 的 MATLAB 数组，指定为 `mxArray*`。

## 返回

- `pi` — 数据数组 (`mxDouble*`) | `NULL`

指向 `mxArray` 内数据部分的第一个 `mxDouble` 元素。如果存在虚数据或发生错误，函数返回 `NULL`。

## 版本历史

在 R2006a 之前引入

**不要使用独立 API**

从 R2018a 开始不推荐

## mxGetComplexDoubles

使用交叉 API 中的 `mxComplexDoubles` 函数代替 `mxGetPr` 和 `mxGetPi` 函数。此函数验证输入是否为复数且类型为 `DOUBLE_CLASS`。

MathWorks 建议您创建 MEX 文件并更新现有的 MEX 文件以使用交叉 API 中的类型数据访问函数。更多信息请参见：

- `Typed Data Access in C MEX Files`
- `MATLAB Support for Interleaved Complex API in MEX Functions`
- `Upgrade MEX Files to Use Interleaved Complex API`
- Example `convex.c`

## 使用交叉 API 构建 mxGetPi 的错误

从 R2018a 开始的错误

`mxGetPi` 函数仅在独立复数 API 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2017b myMexFile.c
```

使用此函数构建的现有 MEX 文件可以继续运行。

## 另请参阅

`mxSetNzmax`

## 主题

- `convex.c`
- `Typed Data Access in C MEX Files`
- `MATLAB Support for Interleaved Complex API in MEX Functions`
- `Upgrade MEX Files to Use Interleaved Complex API`

---

# mxGetPi (Fortran)

（不推荐）`mxDOUBLE_CLASS` 数组中的虚部数据元素

**注意** `mxGetPi` 不适用于交错复数 API（interleaved complex API）。请改用 `mxGetComplexDoubles`。更多信息请参见“兼容性考虑”。

## Fortran 语法

```fortran
#include "intrff.h"
mwPointer mxGetPi(pm)
mwPointer pm
```

## 描述

在使用独立复数 API 构建 MEX 文件时，调用 `mxGetPi` 获取 `pi` 字段的内容。`pi` 是一个包含 `mxArray` 虚数据的数组。仅对类型为 `mxDOUBLE_CLASS` 的数组使用 `mxGetPi`。对于数值型 `mxArray` 类型，请使用 `mxGetImagData`。

调用 `mxIsDouble` 验证 `mxArray` 类型。调用 `mxIsComplex` 确定数据是否为复数。

如果用于函数的任何输入矩阵是复数，则 MATLAB 会为所有输入矩阵分配虚部内存空间。

## 输入参数

- `pm` — 指向 MATLAB 数组的指针 (`mwPointer`)

指向类型为 `mxDOUBLE_CLASS` 的 MATLAB 数组的指针，指定为 `mwPointer`。复数支持：是

## 输出参数

- `pi` — 指向数据数组的指针 (`mwPointer`)

指向 `mxArray` 内部数据数组虚部第一个 `mxDouble` 元素的指针，指定为 `mwPointer`。如果不存在虚数据或发生错误，该函数返回 0。

## 版本历史

在 R2006a 之前引入

**请勿使用独立复数 API**

从 R2018b 开始不推荐

请在交错复数 API 中使用 `mxGetComplexDoubles` 函数代替 `mxGetPr` 和 `mxGetPi` 函数。该函数会验证输入数组是否为复数且类型为 `mxDOUBLE_CLASS`。

MathWorks 建议您创建 MEX 文件并更新现有的 MEX 文件以使用交错复数 API 中的类型化数据访问函数。更多信息请参见：

- `C MEX 文件中的类型化数据访问`
- `MATLAB 对 MEX 函数中交错复数 API 的支持`
- `升级 MEX 文件使用交错复数 API`
- Example `convec.F`

要构建 MEX 文件，请使用 `-R2018a` 选项调用 `mex`。

## 使用交错复数 API 构建 mxGetPi 产生的错误

从 R2018b 开始出现错误

`mxGetPi` 函数仅适用于独立复数 API。要使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2017b myMexFile.F
```

使用此函数构建的现有 MEX 文件可以继续运行。

## 另见

`mxGetComplexDoubles`

## 主题

- `convec.F`
- `C MEX 文件中的类型化数据访问`
- `MATLAB 对 MEX 函数中交错复数 API 的支持`

---

# mxGetPr (C)

（不推荐）`mxDOUBLE_CLASS` 数组中的实部数据元素

**注意** 不推荐 `mxGetPr`。请改用 `mxGetDoubles` 或 `mxComplexDoubles`。更多信息请参见“兼容性考虑”。

## C 语法

```c
#include "matrix.h"
mDouble *mxGetPr(const mxArray *pm);
```

## 描述

仅对类型为 `mxDOUBLE_CLASS` 的实数组使用 `mxGetPr`。对于其他数值型 `mxArray` 类型，请使用“C MEX 文件中的类型化数据访问”函数。对于复数数组，请参见第 1-0 页输出参数 `dt` 的描述。

调用 `mxIsDouble` 验证 `mxArray` 类型。调用 `mxIsComplex` 确定数据是否为实数。

## 输入参数

- `pm` — 指向 MATLAB 数组的指针 (`mxArray *`)

指向类型为 `mxDOUBLE_CLASS` 的 MATLAB 数组的指针，指定为 `mxArray *`。

## 输出参数

- `dt` — 指向数据数组的指针 (`mDouble *` | `NULL`)

指向 `mxArray` 内部数据数组的指针，指定为 `mDouble *`。输出中的数据取决于您使用的 C API 版本：

- 如果使用独立复数 API 构建（`mex -R2017b` 选项），则函数返回指向数据实部第一个 `mxDouble` 元素的指针。
- 如果使用交错复数 API 构建（`mex -R2018a` 选项）且 `pm` 为复数，则函数将终止 MEX 文件并将控制权交给 MATLAB 提示符。在非 MEX 文件应用程序中，函数返回 `NULL`。

如果 `pm` 为 `NULL`，则函数返回 `NULL`。

## 版本历史

在 R2006a 之前引入

# 请勿使用独立复数 API

从 R2018a 开始不推荐

对于类型为 `mxDOUBLE_CLASS` 的实输入数组，在交错复数 API 中使用 `mxGetDoubles` 函数。对于类型为 `mxDOUBLE_CLASS` 的复数输入数组使用 `mxGetComplexDoubles`。这些函数会验证输入的类型和复数性，参见：

MathWorks 建议您使用 MEX 文件并使用交错复数 API 中的类型化数据访问函数更新 MEX 文件。更多信息请参见：

- `C MEX 文件中的类型化数据访问`
- `MATLAB 对 MEX 函数中交错复数 API 的支持`
- `升级 MEX 文件使用交错复数 API`
- Example `xtimesy.c`

要构建 MEX 文件，请使用 `-R2018a` 选项调用 `mex`。

# 在 R2018a 构建的交错复数 API 应用中对复数 mxArrays 调用 mxGetPr 的运行时错误

使用 `mxGetComplexDoubles` 代替 `mxGetPr` 和 `mxGetPi`。更多信息请参见 1-0 页输出参数 `dt`。关于如何更新使用 `mxGetPr` 的代码示例，请参见 `convex.c`。

## 另见

`mxGetDoubles` | `mxGetComplexDoubles`

## 主题

- `convex.c`
- `xtimesy.c`
- `C MEX 文件中的类型化数据访问`
- `MATLAB 对 MEX 函数中交错复数 API 的支持`

---

# mxGetPr (Fortran)

（不推荐）`mxDOUBLE_CLASS` 数组中的实部数据元素

**注意** 不推荐 `mxGetPr`。请改用 `mxGetDoubles` 或 `mxComplexDoubles`。更多信息请参见“兼容性考虑”。

## Fortran 语法

```fortran
#include "intrff.h"
mwPointer mxGetPr(pm)
mwPointer pm
```

## 描述

仅对类型为 `mxDOUBLE_CLASS` 的数组使用 `mxGetPr`。对于其他数值型 `mxArray` 类型，请使用“C MEX 文件中的类型化数据访问”函数。对于复数数组，参见输出参数 `dt` 的描述。

调用 `mxIsDouble` 验证 `mxArray` 类型。调用 `mxIsComplex` 确定数据是否为实数。

## 输入参数

- `pm` — 指向 MATLAB 数组的指针 (`mwPointer`)

指向类型为 `mxDOUBLE_CLASS` 的 MATLAB 数组的指针。

## 输出参数

- `dt` — 指向数据数组的指针 (`mwPointer`)

指向 `mxArray` 内部数据数组的指针，指定为 `mwPointer`。输出数据取决于您使用的 API 版本：

- 如果使用独立复数 API 构建（`mex -R2017b` 选项），则函数返回指向数据实部第一个 `mxDouble` 元素的指针。
- 如果使用交错复数 API 构建（`mex -R2018a` 选项）且 `pm` 为复数，则函数将终止 MEX 文件并将控制权交给 MATLAB 提示符。在非 MEX 文件应用程序中，函数返回。

## 版本历史

在 R2006a 之前引入

# 请勿使用独立复数 API

从 R2018b 开始不推荐

在交错复数 API 中对类型为 `mxDOUBLE_CLASS` 的实输入数组使用 `mxGetDoubles`。对类型为 `mxDOUBLE_CLASS` 的复数输入数组使用 `mxGetComplexDoubles`。这些函数会验证输入的类型和复数性。

MathWorks 建议您创建 MEX 文件并使用交错复数 API 中的类型化数据访问函数更新 MEX 文件。更多信息请参见：

- `C MEX 文件中的类型化数据访问`
- `MATLAB 对 MEX 函数中交错复数 API 的支持`
- `升级 MEX 文件使用交错复数 API`
- Example `xtimesy.F`

要构建 MEX 文件，请使用 `-R2018a` 选项调用 `mex`。

# 在 R2018a 构建的交错复数 API 应用中对复数 mxArrays 调用 mxGetPr 产生的错误

使用 `mxGetComplexDoubles` 代替 `mxGetPr` 和 `mxGetPi`。更多信息请参见 1-0 页输出参数 `dt`。关于如何更新使用 `mxGetPr` 的代码示例，请参见 `convex.F`。

## 另见

`mxGetDoubles` | `mxGetComplexDoubles`

## 主题

- `convex.F`
- `xtimesy.F`
- `C MEX 文件中的类型化数据访问`
- `MATLAB 对 MEX 函数中交错复数 API 的支持`

---

# mxGetProperty (C and Fortran)

MATLAB 对象的公共属性值

## C 语法

```c
#include "matrix.h"
mxArray *mxGetProperty(const mxArray *pa, mwIndex index, const char *propname);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mPointer mxGetProperty(pa, index, propname)
mPointer pa
mwIndex index
character(*) propname
```

## 参数

- `pa` — 指向 `mxArray` 的指针。
- `index` — 对象数组中元素的索引。

在 C 中，`mxArray` 的第一个元素索引为 0。最后一个元素的索引为 N-1，其中 N 是数组元素个数。在 Fortran 中，`mxArray` 的第一个元素索引为 1。最后一个元素的索引为 N，其中 N 是数组元素个数。

- `propname` — 要提取的属性名称。

## 返回

成功时返回指向指定属性名的 `mxArray` 指针。失败时返回 `NULL`（C 或 Fortran 中为 0）。常见失败原因包括：

- 指定了不存在的属性名。
- 指定了非公共属性名。
- 指定的索引超出 `mxArray` 范围。测试索引值时，使用 `mxNumberOfElements` 或 `mxGetM` 和 `mxGetN`。

## 描述

调用 `mxGetProperty` 获取指定元素的值。在伪 C 术语中，`mxGetProperty` 返回此处的值：

```c
pa[index].propname
```

`mxGetProperty` 会创建该值的副本。如果该属性使用大量内存，创建副本可能会出现问题。必须有足够的内存（堆内存）来存储该值。

## 示例

### 时间序列的名称属性

在你的 MATLAB 路径下的文件夹中创建一个 MEX 文件，`disproperty.c`。

```c
/*==========================================================
* disproperty() - 显示时间序列名称属性
* 这是一个用于 MATLAB 的 MEX 文件。
* 版权所有 2013 The MathWorks, Inc.
* 保留所有权利
*==========================================================*/
#include "mex.h"
void mexFunction(int nlh, mxArray *plhs[], int nrhs,
                 const mxArray *prhs[])
{
    /* 检查参数数量是否正确。 */
    if(nlh!=1) {
        mxErrMsgMsgIdAndTxt("MATLAB:disproperty:invalidNumInputs",
            "需要一个输入.");
    } else if(nrhs>1) {
        mxErrMsgMsgIdAndTxt("MATLAB:disproperty:maxlhs",
            "参数过多.")
    }
    /* 检查是否为 timeseries 对象。 */
    if (!mxIsClass(prhs[0], "timeseries")) {
        mxErrMsgMsgIdAndTxt("MATLAB:disproperty:invalidClass",
            "输入必须是 timeseries 对象.")
    }
    plhs[0] = mxGetProperty(prhs[0],"Name");
}
```

构建 MEX 文件。

```matlab
mex('-v','disproperty.c')
```

创建一个 timeseries 对象。

```matlab
ts = timeseries(rand(5, 4),'Name','LaunchData');
```

显示名称。

```matlab
tsname = disproperty(ts)
tsname =
LaunchData
```

### 修改对象颜色

在 `matlabroot/extern/examples/mex` 文件夹中打开并构建 `mxgetProperty.c` MEX 文件。

## 局限性

- `mxGetProperty` 不支持独立应用程序，例如使用 MATLAB API 构建的应用程序。
- 不支持 datetime 类型的属性。

## 版本历史

在 R2008a 中引入



## mxSetProperty | mxGetNumberOfElements | mxGetM | mxGetN | "getProperty" 第 1-144 页

## mxGetScalar (C 和 Fortran)

数组中第一个数据元素的实部组件

### C 语法

```c
#include "matrix.h"
double mxGetScalar(const mxArray *pm);
```

### Fortran 语法

```fortran
#include "fintrf.h"
real*8 mxGetScalar(pm)
mwPointer pm
```

### 参数

- `pm` 指向一个 `mxArray` 的指针；不能是 cell `mxArray`、结构体 `mxArray` 或空 `mxArray`。

### 返回

`mxArray` 中第一个实部（非虚部）元素的值。

在 C 中，`mxGetScalar` 返回一个 `double`。如果 `mxArray` 中的元素是 `double` 以外的类型，则 `mxGetScalar` 会自动将标量值转换为 `double`。为了保留标量的原始数据表示，请将值强制转换为所需的数据类型。

如果 `pm` 指向一个稀疏 `mxArray`，则 `mxGetScalar` 返回 `mxArray` 中第一个非零元素的值。如果没有非零元素，则函数返回 0。

### 描述

调用 `mxGetScalar` 获取 `mxArray` 中第一个实部（非虚部）元素的值。

通常，当 `pm` 指向一个包含单个元素（标量）的 `mxArray` 时调用 `mxGetScalar`。然而，如果 `pm` 指向一个包含许多元素的 `mxArray`，则函数返回第一个实部元素的值。如果 `pm` 指向一个二维 `mxArray`，则 `mxGetScalar` 返回 (1,1) 元素的值。如果 `pm` 指向一个三维 `mxArray`，则函数返回 (1,1,1) 元素的值；依此类推。

仅对类型为数值、逻辑或字符的非空 `mxArray` 使用 `mxGetScalar`。要测试这些条件，请使用矩阵库函数，如 `mxIsEmpty`、`mxIsLogical`、`mxIsNumeric` 或 `mxIsChar`。

如果输入到 `mxGetScalar` 的类型为 `int64` 或 `uint64`，且该值大于 `flintmax`，则可能会丢失精度。

### 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `timestowalt.c`
- `xtimesy.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `mxlock.c`
- `mxlockf.`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetdimensions.c`

### 另见

`mxGetM`, `mxGetN`, `mxIsScalar`

## mxGetString (C 和 Fortran)

`mxChar` 数组转换为 C 风格字符串或 Fortran 数组

### C 语法

```c
#include "matrix.h"
int mxGetString(const mxArray *pm, char *str, mwSize strlen);
```

### Fortran 语法

```fortran
#include "intrf.h"
integer4 mxGetString(pm, strlen)
mwPointer pm
character(*) str
mwSize strlen
```

### 参数

- `pm` 指向一个 `mxArray` 的指针。
- `str` 起始位置。`mxGetString` 将字符数据写入 `str`，然后用 NULL 字符终止字符串（以 C 语言的方式）。`str` 可以指向动态内存或静态内存。
- `pm` 指向的 `mxArray` 的字节数。要获取元素个数，请使用 `mxGetN`。

不要使用“多字节编码字符”。

### 返回

成功时返回 0，失败时返回 1。失败的原因包括：

- `mxArray` 不是字符数组。
- `strlen` 长度足够容纳 `mxArray`。

### 描述

调用 `mxGetString` 将 `mxArray` 的字符数据转换为 C 风格字符串或 Fortran 数组。C 风格字符串始终以 NULL 字符终止。

如果 `mxArray` 包含多个行，则函数逐列复制它们。

### 多字节编码字符

仅在单字节编码的 `mxArray` 上使用此函数。为了避免截断，对于多字节编码使用 `mxToString`。

### 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxmalloc.c`

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `mxlock.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `revord.c`

### 另见

`mxToString`, `mxCharArray`, `mxCreateFromString`, `mxCreateString`, `mxChars`

### 版本历史

引入

## mxIsCell (C)

判断 `mxArray` 是否为 cell 类型

### C 语法

```c
#include "matrix.h"
bool mxIsCell(const mxArray *pm);
```

### 描述

如果 `mxArray` 是 cell 数组，则返回逻辑真 (`true`)，否则返回逻辑假 (`false`)。

在 C 中，调用 `mxIsCell` 等同于调用：

`mxGetClassID(pm) == mxCELL_CLASS`

注意：单个 cell 元素可以是任何类型。

### 参数

- `pm` 指向一个 `mxArray` 的指针；类型为 `const mxArray`。

### 版本历史

在...中引入

### 另见

`mxGetClass` | `mxClassID`

## mxIsCell (Fortran)

判断 `mxArray` 是否为 cell 类型

### Fortran 语法

```fortran
#include "intrff.h"
integer*4 mxIsCell(pm)
mwPointer pm
```

### 描述

如果 `mxArray` 是 cell 数组，则返回 1，否则返回 0。

在 Fortran 中，调用 `mxIsCell` 等同于调用：

`mxGetClassName(pm) .eq 'cell'`

注意：单个 cell 元素可以是任何类型。

### 参数

- `pm` 指向一个 `mxArray` 的指针；类型为 `mwPointer`。

### 版本历史

在...中引入

### 另见

`mxGetClass` | `mxClassID`

## mxIsChar (C)

判断输入是否为 `mxChar` 数组

### C 语法

```c
#include "matrix.h"
bool mxIsChar(const mxArray *pm);
```

### 描述

如果 `pm` 指向一个 `mxArray` 数组，则返回逻辑真 (`true`)，否则返回逻辑假 (`false`)。

在 C 中，调用 `mxIsChar` 等同于调用：

`mxGetClassID(pm) == mxCHAR_CLASS`

### 参数

- `pm` 指向一个 `mxArray` 的指针；类型为 `const mxArray*`。

### 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`
- `revord.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcreatechromrixfromstr.c`
- `mxmalloc.c`

### 版本历史

在...中引入

### 另见

`mxGetClass` | `mxClassID`

## mxIsChar (Fortran)

确定输入是否为 `mxChar` 数组

### Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsChar(pm)
mwPointer pm
```

### 描述

如果 `pm` 指向一个 `mxChar` 数组，使用 `mxIsChar` 返回 1；否则，返回 0。

在 Fortran 中，调用 `mxIsChar` 等同于调用：

`mxGetClassName(pm) .eq. 'char'`

### 输入参数

- `pm` — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

### 示例

参见 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matdemol.F`

### 版本历史

在 R2006a 之前引入

### 另见

`mxIsClass` | `mxGetClassID`

## mxIsClass (C)

确定 `mxArray` 是否为指定类的对象

### C 语法

```c
#include "matrix.h"
bool mxIsClass(const mxArray *pm, const char *classname);
```

### 返回

如果 `pm` 指向具有类别 `classname` 的数组，则返回逻辑值 1 (`true`)，否则返回逻辑值 0 (`false`)。

### 描述

每个 `mxArray` 都被标记为特定类型。如果 `mxArray` 是指定的类型，`mxIsClass` 返回逻辑值 1 (`true`)。否则，函数返回逻辑值 0 (`false`)。

MATLAB 不检查该类是否来自某个基类。

在 C 中：

`mxIsClass(pm, "double");`

等同于调用以下两种形式之一：

`mxIsDouble(pm);`
`strcmp(mxGetClassName(pm), "double")==0;`

使用 `mxIsDouble` 形式更高效。

### 输入参数

- `pm` — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

- `classname` — 要测试的数组类别
  `const char*`
  要测试的数组类别，指定为 `const char*`。使用这些预定义常量之一。不要将 `classname` 指定为整数标识符。

| classname 的值 | 对应的类 |
| :--- | :--- |
| cell | `mxCELL_CLASS` |
| char | `mxCHAR_CLASS` |
| double | `mxDOUBLE_CLASS` |
| function handle | `mxFUNCTION_CLASS` |
| int8 | `mxINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| logical | `mxLOGICAL_CLASS` |
| single | `mxSINGLE_CLASS` |
| struct | `mxSTRUCT_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| `<classname>`, 代表特定 MATLAB 自定义对象的名称。你也可以指定你自己的类名。 | `<class_id>` |
| unknown | `mxUNKNOWN_CLASS` |

### 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisclass.c`

### 版本历史

在 R2006a 之前引入

### 另见

`mxClassID` | `mxGetClassID` | `mxIsEmpty` | `mxGetClassName`

## mxIsClass (Fortran)

确定 `mxArray` 是否为指定类的对象

### Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxIsClass(pm, classname)
mPointer pm
character*(*) classname
```

### 描述

每个 `mxArray` 都被标记为特定类型。如果 `mxArray` 是指定的类型，`mxIsClass` 返回 1。否则，函数返回 0。

MATLAB 不检查类是否派生自基类。

在 Fortran 中：

`mxIsClass(pm, 'double')`

等同于调用以下形式之一：

`mxIsDouble(pm)`
`mxGetClassName(pm) .eq 'double'`

使用 `mxIsDouble` 形式更高效。

### 输入参数

- `pm` — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

- `classname` — 要测试的数组类别
  `character(*)`
  要测试的数组类别，指定为 `character(*)`。使用这些预定义常量之一。不要将 `classname` 指定为整数标识符。

| classname 的值 | 对应的类 |
| :--- | :--- |
| cell | `mxCELL_CLASS` |
| char | `mxCHAR_CLASS` |
| double | `mxDOUBLE_CLASS` |
| function handle | `mxFUNCTION_CLASS` |
| int8 | `mxINT8_CLASS` |
| int16 | `mxINT16_CLASS` |
| int32 | `mxINT32_CLASS` |
| int64 | `mxINT64_CLASS` |
| logical | `mxLOGICAL_CLASS` |
| single | `mxSINGLE_CLASS` |
| struct | `mxSTRUCT_CLASS` |
| uint8 | `mxUINT8_CLASS` |
| uint16 | `mxUINT16_CLASS` |
| uint32 | `mxUINT32_CLASS` |
| uint64 | `mxUINT64_CLASS` |
| `<classname>`, 代表特定 MATLAB 自定义对象的名称。你也可以指定你自己的类名。 | `<class_id>` |
| unknown | `mxUNKNOWN_CLASS` |

### 版本历史

在 R2006a 之前引入

### 另见

`mxIDFromClassName` | `mxGetClassID` | `mxIsEmpty`

## mxIsComplex (C)

确定数据是否为复数

### C 语法

```c
#include "matrix.h"
bool mxIsComplex(const mxArray *pm);
```

### 描述

使用 `mxIsComplex` 确定 `mxArray` 是否分配了虚部。如果 `mxArray` 没有虚部数据，则虚部指针 `pi` 为 `NULL`。如果 `mxArray` 是复数，则 `pi` 指向数字数组。

### 输入参数

- `pm` — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

### 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisfinite.c`
- `mxgetinf.c`

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `convex.c`

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `convex.c`
- `get.c`

### 版本历史

在 R2006a 之前引入

### 另见

`mxIsNumeric`

## mxIsComplex (Fortran)

确定数据是否为复数

### Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxIsComplex(pm)
mwPointer pm
```

### 描述

使用 `mxIsComplex` 确定 `mxArray` 是否分配了虚部。如果 `mxArray` 没有虚部数据，则虚部指针 `pi` 为 `NULL`。如果 `mxArray` 是复数，则 `pi` 指向数字数组。

### 输入参数

- `pm` — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

### 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `convex.F`
- `get.F`

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `deomplex.F`

### 版本历史

在 R2006a 之前引入

### 另见

`mxIsNumeric`

## mxIsDouble (C)

确定 `mxArray` 是否表示双精度浮点数

### C 语法

```c
#include "matrix.h"
bool mxIsDouble(const mxArray *pm);
```

### 描述

如果 `pm` 指向具有 `double` 类别的数组，`mxIsDouble` 返回逻辑值 1 (`true`)，否则返回逻辑值 0 (`false`)。

旧版本的 MATLAB 将所有 `mxArray` 数据存储为双精度浮点数。然而，从 MATLAB 5 软件开始，MATLAB 可以以其他格式存储实虚部数据。

在 C 中，调用 `mxIsDouble` 等于调用：

`mxGetClassName(pm) .eq "double"`

### 输入参数

- `pm` — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

### 示例



参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `deomplex.c`
- `get.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClassID`

# mxIsDouble (Fortran)

确定 `mxArray` 是否表示双精度浮点数

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxIsDouble(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向具有 double 类别的数组，`mxIsDouble` 返回 1 (true)，否则返回 0 (false)。

旧版本的 MATLAB 将所有 `mxArray` 数据存储为双精度浮点数。然而，从 MATLAB 5 软件开始，MATLAB 可以以其他格式存储实虚部数据。

在 Fortran 中，调用 `mxIsDouble` 等同于调用：

```
mxGetClassName(pm) .eq 'double'
```

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `deomplex.F`
- `get.F`

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClassID`

# mxIsEmpty (C)

确定 `mxArray` 是否为空

# C 语法

```
#include "matrix.h"
bool mxIsEmpty(const mxArray *pm);
```

## 描述

如果 `mxArray` 为空，`mxIsEmpty` 返回逻辑值 1 (true)。否则，返回逻辑值 0 (false)。

如果 `mxArray` 的任何一个维的大小为 0，则该数组为空。

# 输入参数

- **pm** — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisfinite.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass`

# mxIsEmpty (Fortran)

确定 `mxArray` 是否为空

# Fortran 语法

```
#include "intrf.h"
integer*4 mxIsEmpty(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 为空，`mxIsEmpty` 返回 1。否则，返回 0。如果 `mxArray` 的任何一个维度的大小为 0，则该数组为空。

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxClasses`

# mxIsFinite (C 和 Fortran)

确定输入是否为有限

# C 语法

```
#include "matrix.h"
bool mxIsFinite(double value);
```

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxIsFinite(value)
real*8 value
```

## 参数

**value**

要测试的双精度浮点数

## 返回值

如果 `value` 是有限的，则返回逻辑值 1 (true)，否则返回逻辑值 0 (false)。

## 描述

调用 `mxIsFinite` 来确定 `value` 是否为有限。如果一个数字大于 -Inf 且小于 Inf，则认为它是有限的。

## 示例

查看 `matlabroot/extern/examples/mx/` 中的这些示例：

- `mxisfinite.c`

## 另见

`mxIsInf`, `mxIsNaN`

## 版本历史

在 R2006a 之前引入

# mxIsFromGlobalWS (C)

确定 `mxArray` 是否从 MATLAB 全局工作区拷贝

# C 语法

```
#include "matrix.h"
bool mxIsFromGlobalWS(const mxArray *pm);
```

## 描述

如果数组是从全局工作区复制的，该函数返回逻辑值 1 (true)。否则，返回逻辑值 0 (false)。对于独立的 MAT-file 程序请使用 `mxIsFromGlobalWS`。

# 输入参数

- **pm** — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/eng_mat` 中的这些示例：

- `matcreate.c`
- `matdgns.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsFromGlobalWS` (Fortran)

# mxIsFromGlobalWS (Fortran)

确定 `mxArray` 是否从 MATLAB 全局工作区拷贝

# Fortran 语法

```
#include "intrff.h"
integer*4 mxIsFromGlobalWS(pm)
mwPointer pm
```

## 描述

如果数组是从全局工作区复制的，该函数返回 1。否则，返回 0。对于独立的 MAT-file 程序请使用 `mxIsFromGlobalWS`。

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsFromGlobalWS` (C)

# mxIsInf (C 和 Fortran)

确定输入是否为无穷

# C 语法

```
#include "matrix.h"
bool mxIsInf(double value);
```

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxIsInf(value)
real*8 value
```

## 参数

**value**

要测试的双精度浮点数

## 返回值

如果 `value` 是无穷的，则返回逻辑值 1 (true)，否则返回逻辑值 0 (false)。

## 描述

使用 `mxIsInf` 确定 `value` 是否等于无穷或负无穷。MATLAB 软件将无穷值存储在名为 `Inf` 的永久变量中，它代表 IEEE 算术正无穷。变量 `Inf` 的值是系统内置的；你无法修改它。

返回无穷大的操作：

- 除以 0。例如，`5/0` 返回无穷大。
- 导致溢出的操作。例如，`exp(10000)` 返回无穷大，因为结果太大，无法在你的机器上表示。

如果 `value` 等于 NaN（非数字），则 `mxIsInf` 返回 false。换句话说，NaN 不等于无穷大。

## 示例

查看 `matlabroot/extern/examples/mx/` 下的这些示例：

- `mxisfinite.c`

## 另见

`mxIsFinite`, `mxIsNaN`

## 版本历史

在 R2006a 之前引入

# mxIsInt16 (C)

确定 `mxArray` 是否表示有符号 16 位整数

# C 语法

```
#include "matrix.h"
bool mxIsInt16(const mxArray *pm);
```

## 描述

如果 `mxArray` 将实部和虚部数据存储为 16 位整数，`mxIsInt16` 返回逻辑值 1 (true)。否则返回逻辑值 0 (false)。

在 C 中，调用 `mxIsInt16` 等于调用：

```
mxGetClass(pm) == mxINT16_CLASS
```

# 输入参数

- **pm** — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClass` | `mxIsUint16`

# mxIsInt32 (C)

确定 `mxArray` 是否表示有符号 32 位整数

# C 语法

```
#include "matrix.h"
bool mxIsInt32(const mxArray *pm);
```

## 描述

如果 `mxArray` 将数据存储为 32 位整数，`mxIsInt32` 返回逻辑值 1 (true)。否则返回逻辑值 0 (false)。

在 C 中，调用 `mxIsInt32` 等于调用：

```
mxGetClass(pm) == mxINT32_CLASS
```

# 输入参数

- **pm** — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClass` | `mxIsUint32`

# mxIsInt64 (C)

确定 `mxArray` 是否表示有符号 64 位整数

# C 语法

```
#include "matrix.h"
bool mxIsInt64(const mxArray *pm);
```

## 描述

如果 `mxArray` 将实部和虚部数据存储为 64 位有符号整数，`mxIsInt64` 返回逻辑值 1 (true)。否则返回逻辑值 0 (false)。

在 C 中，调用 `mxIsInt64` 等于调用：

```
mxGetClass(pm) == mxINT64_CLASS
```

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass`, `mxGetClass`, `mxIsUint64`

# mxIsInt8 (C)

确定 `mxArray` 是否表示有符号 8 位整数

# C 语法

```
#include "matrix.h"
bool mxIsInt8(const mxArray *pm);
```

## 描述

使用 `mxIsInt8` 确定指定的数组是否将实部和虚部数据表示为 8 位有符号整数。

在 C 中，调用 `mxIsInt8` 等于调用：

```
mxGetClass(pm) == mxINT8_CLASS
```

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClass` | `mxIsUint8`

# mxIsInt16 (Fortran)

确定 `mxArray` 是否表示有符号 16 位整数

# Fortran 语法

```
#include "intrf.h"
integer*4 mxIsInt16(pm)
mwPointer pm
```

## 描述

如果指定的数组将实部和虚部数据表示为 16 位整数，`mxIsInt16` 返回 1。否则返回 0。

在 C 中，调用 `mxIsInt16` 等于调用：

```
mxGetClassName(pm) == mxINT16_CLASS
```

在 Fortran 中，调用 `mxIsInt16` 等于调用：

```
mxGetClassName(pm) == 'int16'
```

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClassName` | `mxIsUint16`

# mxIsInt32 (Fortran)

确定 `mxArray` 是否表示有符号 32 位整数

# Fortran 语法

```
#include "intrf.h"
integer*4 mxIsInt32(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将数据存储为 32 位整数，`mxIsInt32` 返回 1。否则返回 0。

在 Fortran 中，调用 `mxIsInt32` 等于调用：

```
mxGetClassName(pm) == 'int32'
```

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClassName` | `mxIsUint32`

# mxIsInt64 (Fortran)

确定 `mxArray` 是否表示有符号 64 位整数

# Fortran 语法

```
#include "intrf.h"
integer*4 mxIsInt64(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将数据存储为 64 位有符号整数，`mxIsInt64` 返回 1。否则返回 0。

在 Fortran 中，调用 `mxIsInt64` 等于调用：

```
mxGetClassName(pm) == 'int64'
```

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClassID` | `mxIsUint64`

# mxIsInt8 (Fortran)

确定 `mxArray` 是否表示有符号 8 位整数

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxIsInt8(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将数据存储为 8 位有符号整数，`mxIsInt8` 返回 1。

在 Fortran 中，调用 `mxIsInt8` 等于调用：

```
mxGetClassName(pm) .eq. 'int8'
```

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另见

`mxIsClass` | `mxGetClassName` | `mxIsUint8`

# mxIsLogical (C)

确定 `mxArray` 是否为 `mxLogical` 类型

# C 语法

```
#include "matrix.h"
bool mxIsLogical(const mxArray *pm);
```

## 描述

如果 `mxArray` 中的数据是布尔型（逻辑），`mxIsLogical` 返回 1 (真)。否则，返回 0 (假)。如果 `mxArray` 是逻辑型的，则 MATLAB 将所有 0 视为假，将所有非零值视为真。

# 输入参数

- **pm** — MATLAB 数组
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxislogical.c`

## 版本历史

R2006a 之前引入

## 另见

`mxIsClass`

# 主题

“逻辑（布尔）操作”

# mxIsLogical (Fortran)

确定 `mxArray` 是否为 `mxLogical` 类型

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxIsLogical(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 是逻辑型的，`mxIsLogical` 返回 1。否则，返回 0。如果 `mxArray` 是逻辑型的，则 MATLAB 将所有 0 视为假，将所有非零值视为真。

# 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

R2006a 之前引入

## 另见

`mxIsClass`

# 主题

“逻辑（布尔）操作”

# mxIsLogicalScalar (C)

确定标量数组是否为 `mxLogical` 类型

# C 语法

```c
#include "matrix.h"
bool mxIsLogicalScalar(const mxArray *array_ptr);
```

## 参数

**array_ptr**

指向 `mxArray` 的指针

## 返回

如果 `mxArray` 的类为 `mxLogical` 且维度为 1-by-1，则返回逻辑 1 (真)。否则，返回逻辑 0 (假)。

## 描述

使用 `mxIsLogicalScalar` 确定 MATLAB 将 `mxArray` 中的标量数据处理为逻辑型还是数值型。

## 版本历史

R2006a 之前引入

## 另见

`mxGetScalar` | `mxGetLogicals` | `mxIsLogicalScalarTrue` | `mxIsLogical`

# 主题

“逻辑（布尔）操作”

# mxIsLogicalScalarTrue (C)

确定类型为 `mxLogical` 的标量数组是否为真

# C 语法

```c
#include "matrix.h"
bool mxIsLogicalScalarTrue(const mxArray *array_ptr);
```

## 参数

- **array_ptr**

  指向 `mxArray` 的指针

## 返回

如果 `mxArray` 标量元素的值为真，则返回逻辑 1 (真)。否则，返回逻辑 0 (假)。

## 描述

使用 `mxIsLogicalScalarTrue` 确定标量 `mxArray` 的值为真还是为假。

## 版本历史

R2006a 之前引入

## 另见

`mxGetScalar` | `mxGetLogicals` | `mxIsLogicalScalar` | `mxIsLogical`

# 主题

“逻辑（布尔）操作”

# mxIsNaN (C 和 Fortran)

确定输入是否为 NaN（非数字）

# C 语法



```c
#include "matrix.h"
bool mxIsNaN(double value);
```

# Fortran 语法

```c
#include "fintrf.h"
integer*4 mxIsNaN(value)
real*8 value
```

## 参数

`value`

待测试的双精度浮点数

## 返回

如果 `value` 为 NaN（非数字），则返回逻辑 1 (真)，否则返回逻辑 0 (假)。

## 描述

调用 `mxIsNaN` 确定 `value` 是否为 NaN。NaN 是“非数字”的 IEEE 算术表示法。NaN 是数学上未定义操作的结果，例如：

- `0.0/0.0`
- `Inf-Inf`

系统将一组位模式为 NaN。NaN 用于其他符合 IEEE 标准的应用程序表示错误条件或缺失数据。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxisfinite.c`

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `findnz.c`
- `fulltosparse.c`

## 另请参阅

`mxIsFinite`, `mxIsInf`

## 版本历史

R2006a 之前引入

# mxIsNumeric (C)

确定 `mxArray` 是否为数值型

## C 语法

```c
#include "matrix.h"
bool mxIsNumeric(const mxArray *pm);
```

调用 `mxIsNumeric` 确定指定的数组是否包含数值数据。如果数组具有表示数值数据的存储类型，`mxIsNumeric` 返回 1 (真)。使用 `mxGetClass` 确定存储类型。这些类 ID 表示可以包含数值数据的存储类型：

- `DOUBLE_CLASS`
- `SINGLE_CLASS`
- `INT8_CLASS`
- `UINT8_CLASS`
- `INT16_CLASS`
- `UINT16_CLASS`
- `INT32_CLASS`
- `UINT32_CLASS`
- `INT64_CLASS`
- `UINT64_CLASS`

否则，`mxIsNumeric` 返回 0 (假)。

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxGetClass`

# mxIsNumeric (Fortran)

确定 `mxArray` 是否为数值型

## Fortran 语法

```c
#include "fintrf.h"
integer*4 mxIsNumeric(pm)
mwPointer pm
```

## 描述

调用 `mxIsNumeric` 确定指定的数组是否包含数值数据。如果数组具有表示数值数据的存储类型，`mxIsNumeric` 返回 1。使用 `mxGetClass` 确定存储类型。这些类 ID 表示可以包含数值数据的存储类型：

- `DOUBLE_CLASS`
- `SINGLE_CLASS`
- `INT8_CLASS`
- `UINT8_CLASS`
- `INT16_CLASS`
- `UINT16_CLASS`
- `INT32_CLASS`
- `UINT32_CLASS`
- `INT64_CLASS`
- `UINT64_CLASS`

否则，`mxIsNumeric` 返回 0。

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `demol.c`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxClassID`

# mxIsScalar (C)

确定标量数组是否为 `mxLogical` 类型

## C 语法

```c
#include "matrix.h"
bool mxIsScalar(const mxArray *array_ptr);
```

## 参数

`array_ptr`

指向 `mxArray` 的指针

## 返回

如果 `mxArray` 的类为 `mxLogical` 且维度为 1-by-1，则返回逻辑 1 (真)。否则，返回逻辑 0 (假)。

## 描述

使用 `mxIsScalar` 确定 MATLAB 将 `mxArray` 中的标量数据处理为逻辑型还是数值型。

对于维度为 1-by-1 的 `mxArray` 使用 `mxIsScalar`。由 `mxClassID` 文档。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `misscalar.c`

## 版本历史

R201a 引入

## 另请参阅

`mxGetScalar` | `mxClassID`

# mxIsSingle (C)

确定 `mxArray` 是否用单精度浮点数表示数据

## C 语法

```c
#include "matrix.h"
bool mxIsSingle(const mxArray *pm);
```

## 描述

如果 `mxArray` 将其实部和虚部数据存储为单精度浮点数，`mxIsSingle` 返回 1 (真)。否则，返回逻辑 0 (假)。

在 C 中，调用 `mxIsSingle` 等于：

```c
mxGetClassID(pm) == mxSINGLE_CLASS
```

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxClassID`

# mxIsSingle (Fortran)

确定 `mxArray` 是否用单精度浮点数表示数据

## Fortran 语法

```c
#include "intfrf.h"
integer*4 mxIsSingle(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将其实部和虚部数据存储为单精度浮点数，`mxIsSingle` 返回 1。否则返回 0。

在 Fortran 中，调用 `mxIsSingle` 等于：

```c
mxGetClassName(pm) .eq. 'single'
```

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID`

# mxIsSparse (C)

确定输入是否为稀疏 `mxArray`

## C 语法

```c
#include "matrix.h"
bool mxIsSparse(const mxArray *pm);
```

## 描述

如果 `pm` 指向稀疏 `mxArray`，`mxIsSparse` 返回逻辑 1 (真)。否则，返回逻辑 0 (假)。许多例程（例如 `mxGetIr` 和 `mxGetJ`）需要稀疏 `mxArray` 输入。

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxgetnzmax.c`
- `mxsetdimensions.c`
- `mxsetnzmax.c`

## 版本历史

R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `sparse` | `mxCreateSparse`

## mxIsSparse (Fortran)

确定输入是否为稀疏 `mxArray`

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsSparse(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向稀疏 `mxArray`，`mxIsSparse` 返回 1。否则，返回 0。例如，`mxGetIr` 和 `mxGetJc` 等许多程序需要稀疏 `mxArray` 作为输入。

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetdimensions.F`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassName` | `sparse` | `mxCreateSparse`

## mxIsStruct (C)

确定 `mxArray` 是否为结构体

## C 语法

```c
#include "matrix.h"
bool mxIsStruct(const mxArray *pm);
```

## 描述

如果 `pm` 指向结构体 `mxArray`，`mxIsStruct` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要结构体 `mxArray` 作为参数。

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `phonebook.c`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `mxCreateStructArray`

## mxIsStruct (Fortran)

确定 `mxArray` 是否为结构体

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsStruct(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向结构体 `mxArray`，`mxIsStruct` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要结构体 `mxArray` 作为参数。

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `mxCreateStructArray`

## mxIsUint16 (C)

确定 `mxArray` 是否将数据表示为无符号 16 位整数

## C 语法

```c
#include "matrix.h"
bool mxIsUint16(const mxArray *pm);
```

## 描述

如果 `mxArray` 将其数据存储为 16 位无符号整数，`mxIsUint16` 返回 1 (true)。

否则，返回 0 (false)。

在 C 中，调用 `mxIsUint16` 等同于调用：

```c
mxGetClassID(pm) == mxUINT16_CLASS
```

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `mxIsUint16`

## mxIsUint32 (C)

确定 `mxArray` 是否将数据表示为无符号 32 位整数

## C 语法

```c
#include "matrix.h"
bool mxIsUint32(const mxArray *pm);
```

## 描述

如果 `mxArray` 将其数据存储为 32 位无符号整数，`mxIsUint32` 返回 1 (true)。否则，调用它返回 0 (false)。

在 C 中，调用 `mxIsUint32` 等同于调用：

```c
mxGetClassID(pm) == mxUINT32_CLASS
```

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `mxIsUint32`

## mxIsUint64 (C)

确定 `mxArray` 是否将数据表示为无符号 64 位整数

## C 语法

```c
#include "matrix.h"
bool mxIsUint64(const mxArray *pm);
```

## 描述

如果 `mxArray` 将其数据存储为 64 位无符号整数，`mxIsUint64` 返回逻辑 1 (true)。

否则，返回逻辑 0 (false)。

在 C 中，调用 `mxIsUint64` 等同于调用：

```c
mxGetClassID(pm) == mxUINT64_CLASS
```

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `mxIsUint64`

## mxIsUint8 (C)

确定 `mxArray` 是否将数据表示为无符号 8 位整数

## C 语法

```c
#include "matrix.h"
bool mxIsUint8(const mxArray *pm);
```

## 描述

如果 `mxArray` 将其数据存储为 8 位无符号整数，`mxIsUint8` 返回逻辑 1 (true)。

否则，返回逻辑 0 (false)。

在 C 中，调用 `mxIsUint8` 等同于调用：

```c
mxGetClassID(pm) == mxUINT8_CLASS
```

## 输入参数

`pm` — MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassID` | `mxIsUint8`

## mxIsUint16 (Fortran)

确定 `mxArray` 是否将数据表示为无符号 16 位整数

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsUint16(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将其数据存储为 16 位无符号整数，`mxIsUint16` 返回 1。否则，返回 0。

在 Fortran 中，调用 `mxIsUint16` 等同于调用：

```fortran
mxClassName(pm) == 'uint16'
```

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassName` | `mxIsUint16`

## mxIsUint32 (Fortran)

确定 `mxArray` 是否将数据表示为无符号 32 位整数

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsUint32(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将其数据存储为 32 位无符号整数，`mxIsUint32` 返回 1。否则，返回 0。

在 Fortran 中，调用 `mxIsUint32` 等同于调用：

```fortran
mxClassName(pm) == 'uint32'
```

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassName` | `mxIsUint32`

## mxIsUint64 (Fortran)

确定 `mxArray` 是否将数据表示为无符号 64 位整数

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsUint64(pm)
mwPointer pm
```

## 描述

如果 `mxArray` 将其数据存储为 64 位无符号整数，`mxIsUint64` 返回 1。否则，返回 0。

在 Fortran 中，调用 `mxIsUint64` 等同于调用：

```fortran
mxClassName(pm) == 'uint64'
```

## 输入参数

`pm` — MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxIsClass` | `mxGetClassName` | `mxIsUint64`

## mxIsUint8 (Fortran)

确定 `mxArray` 是否将数据表示为无符号 8 位整数

## Fortran 语法



```fortran
#include "intrf.h"
integer*4 mxIsUint8(pm)
mwPointer pm
```

# mxIsUint8 (Fortran)

## 描述

如果 `mxArray` 将其数据存储为 8 位无符号整数，`mxIsUint8` 返回 1。否则，返回 0。

在 Fortran 中，调用 `mxIsUint8` 等同于调用：

```fortran
mxClassName(pm) == 'uint8'
```

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassName` | `mxIsUint8`

---

# mxIsLogical (C)

确定 `mxArray` 是否为逻辑类型

## C 语法

```c
#include "matrix.h"
bool mxIsLogical(const mxArray *pm);
```

## 描述

如果 `pm` 指向逻辑型 `mxArray`，`mxIsLogical` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要逻辑型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsLogical`

---

# mxIsLogical (Fortran)

确定 `mxArray` 是否为逻辑类型

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsLogical(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向逻辑型 `mxArray`，`mxIsLogical` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要逻辑型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsLogical`

---

# mxIsChar (C)

确定 `mxArray` 是否为字符数组

## C 语法

```c
#include "matrix.h"
bool mxIsChar(const mxArray *pm);
```

## 描述

如果 `pm` 指向字符型 `mxArray`，`mxIsChar` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要字符型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsChar`

---

# mxIsChar (Fortran)

确定 `mxArray` 是否为字符数组

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsChar(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向字符型 `mxArray`，`mxIsChar` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要字符型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsChar`

---

# mxIsDouble (C)

确定 `mxArray` 是否为双精度浮点数

## C 语法

```c
#include "matrix.h"
bool mxIsDouble(const mxArray *pm);
```

## 描述

如果 `pm` 指向双精度 `mxArray`，`mxIsDouble` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要双精度 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsDouble`

---

# mxIsDouble (Fortran)

确定 `mxArray` 是否为双精度浮点数

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsDouble(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向双精度 `mxArray`，`mxIsDouble` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要双精度 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsDouble`

---

# mxIsSingle (C)

确定 `mxArray` 是否为单精度浮点数

## C 语法

```c
#include "matrix.h"
bool mxIsSingle(const mxArray *pm);
```

## 描述

如果 `pm` 指向单精度 `mxArray`，`mxIsSingle` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要单精度 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsSingle`

---

# mxIsSingle (Fortran)

确定 `mxArray` 是否为单精度浮点数

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsSingle(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向单精度 `mxArray`，`mxIsSingle` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要单精度 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsSingle`

---

# mxIsInteger (C)

确定 `mxArray` 是否为整数类型

## C 语法

```c
#include "matrix.h"
bool mxIsInteger(const mxArray *pm);
```

## 描述

如果 `pm` 指向整数型 `mxArray`，`mxIsInteger` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要整数型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsInteger`

---

# mxIsInteger (Fortran)

确定 `mxArray` 是否为整数类型

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsInteger(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向整数型 `mxArray`，`mxIsInteger` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要整数型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsInteger`

---

# mxIsCell (C)

确定 `mxArray` 是否为细胞类型

## C 语法

```c
#include "matrix.h"
bool mxIsCell(const mxArray *pm);
```

## 描述

如果 `pm` 指向细胞型 `mxArray`，`mxIsCell` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要细胞型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsCell`

---

# mxIsCell (Fortran)

确定 `mxArray` 是否为细胞类型

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsCell(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向细胞型 `mxArray`，`mxIsCell` 返回 1。否则，返回 0。许多程序（例如 `mxGetFieldNameByNumber` 和 `mxSetField`）需要细胞型 `mxArray` 作为参数。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsCell`

---

# mxIsSparse (C)

确定 `mxArray` 是否为稀疏数组

## C 语法

```c
#include "matrix.h"
bool mxIsSparse(const mxArray *pm);
```

## 描述

如果 `pm` 指向稀疏 `mxArray`，`mxIsSparse` 返回逻辑 1 (true)。否则，返回逻辑 0 (false)。许多程序（例如 `mxGetIr` 和 `mxGetJc`）需要稀疏 `mxArray` 作为输入。

## 输入参数

- **pm** — MATLAB 数组
  - `const mxArray*`
  - 指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsSparse`

---

# mxIsSparse (Fortran)

确定 `mxArray` 是否为稀疏数组

## Fortran 语法

```fortran
#include "intrf.h"
integer*4 mxIsSparse(pm)
mwPointer pm
```

## 描述

如果 `pm` 指向稀疏 `mxArray`，`mxIsSparse` 返回 1。否则，返回 0。许多程序（例如 `mxGetIr` 和 `mxGetJc`）需要稀疏 `mxArray` 作为输入。

## 输入参数

- **pm** — MATLAB 数组
  - `mwPointer`
  - 指向 `mxArray` 数组的指针，指定为 `mwPointer`。

## 版本历史

在 R2006a 之前引入

## 另请查看

`mxIsClass` | `mxGetClassID` | `mxIsSparse`

---

# mxMakeArrayComplex (C)

## C 语法

```c
#include "matrix.h"
int mxMakeArrayComplex(mxArray *pa);
```

## 描述

使用 `mxMakeArrayComplex` 将实数 `mxArray` 转换为复数 `mxArray`。更新后的数组实部包含原始数组的实部数据。

如果 `pa` 为空，则函数返回一个空 `mxArray`。

如果 `pa` 是复数，则函数不执行任何操作。

## 输入参数

- **pa** — MATLAB 数组
  - `mxArray *`
  - 指向数值 `mxArray` 数组的指针。

## 输出参数

- **status** — 函数状态
  - `int`
  - 函数状态，以 `int` 返回。如果成功，则函数返回 1。
  - 如果失败，则返回 0。如果 `pa` 为 `NULL`、非数值或只读，则函数失败。

## 版本历史

在 R2018a 中引入

## 另请查看

`mxMakeArrayReal`

---

# mxMakeArrayComplex (Fortran)

将实数 `mxArray` 转换为复数，保留实部数据

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxMakeArrayComplex(pa)
mwPointer pa
```

## 描述

使用 `mxMakeArrayComplex` 将实数 `mxArray` 转换为复数 `mxArray`。更新后的数组实部包含原始数组的实部数据。

如果 `pa` 为空，则函数返回一个空 `mxArray`。

如果 `pa` 是复数，则函数不执行任何操作。

## 输入参数

- **pa** — MATLAB 数组
  - `mwPointer`
  - 指向数值 `mxArray` 数组的指针。

## 输出参数

- **status** — 函数状态
  - `integer*4`
  - 函数状态，以 `integer*4` 返回。如果成功，则函数返回 1。
  - 如果失败，则返回 0。如果 `pa` 为 `NULL`、非数值或只读，则函数失败。

## 版本历史

在 R2018b 中引入

## 另请查看

`mxMakeArrayReal`

---

# mxMakeArrayReal (C)

将复数 `mxArray` 转换为实数，保留实部数据

## C 语法

```c
#include "matrix.h"
int mxMakeArrayReal(mxArray *pa);
```

## 描述

使用 `mxMakeArrayReal` 将复数 `mxArray` 转换为实数 `mxArray`。该数组包含原始数组实部的数据。如果原始 `mxArray` 是实数，则函数不执行任何操作。

## 输入参数

- **pa** — MATLAB 数组
  - `mxArray *`
  - 指向数值 `mxArray` 数组的指针。

## 输出参数

- **status** — 函数状态
  - `int`
  - 函数状态，以 `int` 返回。如果成功，则函数返回 1。
  - 如果失败，则返回 0。如果 `pa` 为 `NULL`、非数值或只读，则函数失败。

## 示例

假设您的应用程序要求实部是唯一意义的结果。如果由于数据中的噪声产生了复数结果，程序将丢弃虚部。然而，如果虚部超过阈值，程序将抛出错误。

在示例 `dropComplexIfUnderThreshold.c` 中，阈值被设置为 .2。

```c
#include "mx.h"
/* dropComplexIfUnderThreshold 将输入转换为实型双精度标量
 * 不含虚部数据或虚部数据小于
 * LIMIT 值的数据 */
* 使用此函数处理虚部小于 LIMIT 且可以丢弃的数据，
* 然后将结果恢复为实数数组。
* 用法：B = dropComplexIfUnderThreshold(A);
* 其中：
* A 是双精度标量或实数。
* B 是实数标量，是 A 的实部值的拷贝。
* 在以下情况下会报错：
* nlh = 1
* nrhs = 1
```

## API 参考



* `prhs[0]` 不是双精度标量
* 虚部值大于或等于 `LIMIT`
* 构建：
* `mex -R2018a dropComplexIfUnderThreshold.c - interleaved complex`
* `mex -R2018a dropComplexIfUnderThreshold.c - separate complex`
* 运行：
* `>> dropComplexIfUnderThreshold(3)`
* `ans = 3`
* `>> dropComplexIfUnderThreshold(complex(3,1))`
* `ans = 3`
* `>> dropComplexIfUnderThreshold(complex(1,2))`
* 使用 `dropComplexIfUnderThreshold` 报错
* Data error.

```c
void mexFunction(int nlh, mxArray *plhs[]) {
    int rhs;
    #define LIMIT 2
    /* 输入参数个数 */
    if(nlh != 1) {
        mxErrMsg('MATLAB:mxGeneral:one input required.');
    }

    if(rhs > 1) {
        mxErrMsg('MATLAB:mxGeneral:Too many arguments.');
    }

    if(!mxIsDouble(rhs[0])) {
        mxErrMsg('MATLAB:mxGeneral:input must be double.');
    }

    /* 检查数据 */
    if(mxIsComplex(rhs[0])) {
        if(mxImaginary(rhs[0]) >= LIMIT) {
            mxErrMsg('MATLAB:mxGeneral:Data error.');
        }
        plhs[0] = mxMakeArrayReal(rhs[0]);
    } else {
        plhs[0] = mxCopyArray(rhs[0]);
    }
}
```

# mxRealloc (C语言和 Fortran语言)

使用 MATLAB 内存管理器动态分配内存

## C 语言语法

```c
#include "matrix.h"
#include <stdlib.h>
void mxRealloc(void *ptr, mwSize size);
```

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxRealloc(ptr, size)
mwPointer ptr
mwSize size
```

## 参数

- `ptr`

指向由 `mxCalloc`、`mxMalloc` 或 `mxRealloc` 分配的内存块的指针。

- `size`

分配内存的新尺寸，单位为字节。

## 返回

如果成功，返回指向分配内存块起始位置的指针。如果在 MAT 或独立引擎（engine standalone）应用程序中执行失败，则 `mxRealloc` 在 C语言中返回 `NULL`（在 Fortran 中返回 `0`），并保持原始内存块不变。（使用 `mxFree` 释放原始内存块）。如果在 MEX 文件中执行失败，则 MEX 文件将终止并将控制交回 MATLAB 提示符。

当堆空间不足时，`mxRealloc` 将执行失败。

## 描述

`mxRealloc` 更改通过 `mxCalloc`、`mxMalloc` 或 `mxRealloc` 分配的内存块尺寸。在 MATLAB 应用程序中分配内存，请使用 `mxRealloc` 代替 ANSI C 的 `realloc` 函数。

`mxRealloc` 将 `ptr` 指向的内存块尺寸更改为 `size`。分配内存的内容在旧旧尺寸的较小值范围内保持不变。分配的内存可能与原内存位于不同位置，因此返回的指针可能与 `ptr` 不同。如果内存位置发生变化，`mxRealloc` 会释放 `ptr` 指向的原始内存块。

如果 `size` 大于 0 且 C 中的 `ptr` 为 `NULL`（Fortran 中为 `0`），则 `mxRealloc` 的行为类似于 `mxCalloc`。`mxRealloc` 分配一个 `size` 字节大小的新内存块并返回指向该新块的指针。

## API 引用

如果 `size` 为 0 且 C 中的 `ptr` 不为 `NULL`（Fortran 中为 `0`），则 `mxRealloc` 释放 `ptr` 指向的内存并在 C 中返回 `NULL`（在 Fortran 中返回 `0`）。

在 MEX 文件中（而非 MAT 或引擎应用程序）中，`mxRealloc` 将分配的内存注册到 MATLAB 内存管理器。当控制交回 MATLAB 提示符时，内存管理器会自动释放或取消分配这些内存。

你如何管理由此函数创建的内存取决于数据的用途。如果你将其赋值给 `plhs[]` 中的输出参数并使用如 `mxSetDoubles` 的函数，则 MATLAB 负责释放该内存。

如果你在内部使用它，MATLAB 内存管理器会维护一个由函数分配的所有内存列表，并在控制交回 MATLAB 提示符时自动释放（取消分配）这些内存。通常情况下，我们建议 MEX 文件函数销毁自己的临时数组并释放其动态分配的内存。在源 MEX 文件中执行此类清理比依赖自动机制更高效。在使用由此函数分配的内存时，请调用 `mxFree` 来释放该内存。

如果你没有将此数据赋值给输出参数，并希望它在 MEX 文件完成后仍然存在，请在调用此函数后调用 `mxMakeMemoryPersistent`。如果你编写了带有持久内存的 MEX 文件，请确保注册一个 `mxAtExit` 函数，以便在 MEX 文件被清除时释放分配的内存。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetznmax.c`

## 另见

`mxAtExit`, `mxMakeArrayPersistent`, `mxMakeMemoryPersistent`, `mxCalloc`, `mxDestroyArray`, `mxFree`, `mxMalloc`

## 版本历史

R2006a 之前引入

# mxRemoveField (C语言和 Fortran语言)

从结构体数组中移除字段

## C 语言语法

```c
#include "matrix.h"
void mxRemoveField(mxArray *pm, int fieldnumber);
```

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mxRemoveField(pm, fieldnumber)
mPointer pm
integer*4 fieldnumber
```

## 参数

- `pm`: 指向结构体 `mxArray` 的指针

- `fieldnumber`: 你想要移除的字段编号。在 C语言中，要移除第一个字段，将 `fieldnumber` 设置为 0；要移除第二个字段，将 `fieldnumber` 设置为 1；以此类推。在 Fortran 中，要移除第一个字段，将 `fieldnumber` 设置为 1；要移除第二个字段，将 `fieldnumber` 设置为 2；以此类推。

## 描述

调用 `mxRemoveField` 从结构体数组中移除字段。如果该字段不存在，则无任何操作。此函数不会破坏字段值。要销毁实际值，请调用 `mxRemoveField` 然后调用 `mxDestroyArray`。

考虑一个初始化为的 MATLAB 结构体：

```
patient.name = 'John Doe'
patient.billing = 127.00;
patient.test = [79 75 73; 180 178 177.5; 220 210 205];
```

在 C 中，数字 0 代表字段名；字段编号 1 代表字段 `billing`；字段编号 2 代表字段 `test`。在 Fortran 中，数字 1 代表字段名；数字 2 代表 `billing`；数字 3 代表 `test`。

## 另见

`mxAtArray`, `mxDestroyArray`

## 版本历史

`mxRemoveField`  之前

# mxSetCell (C语言和 Fortran语言)

设置单元的内容

## C 语言语法

```c
#include "matrix.h"
void mxSetCell(mxArray *pm, mwSize index, mxArray *value);
```

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mxSetCell(pm, index, value)
mxPointer pm
mwSize index
mxArray value
```

## 参数

- `pm`: 指向 `mxArray` 的指针

- `index`: 单元的索引

- `value`: 要设置的 `mxArray`

## 描述

调用 `mxSetCell` 设置单元数组的内容。

在 MEX 文件中（而非 MAT 或引擎应用程序）中，`mxSetCell` 将分配的内存注册到 MATLAB 内存管理器。当控制交回 MATLAB 提示符时，内存管理器会自动处理。

你如何管理由此函数创建的内存取决于分配给数据的用途。如果你将其赋值给 `plhs[]` 中的输出参数并使用如 `mxSetDoubles` 的函数，则 MATLAB 负责释放该内存。

如果你在内部使用它，MATLAB 内存管理器会维护一个由函数分配的所有内存列表，并在控制交回 MATLAB 提示符时自动释放（取消分配）这些内存。通常情况下，我们建议 MEX 文件函数销毁自己的临时数组并释放其动态分配的内存。在源 MEX 文件中执行此类清理比依赖自动机制更高效。在使用由此函数分配的内存时，请调用 `mxFree` 来释放该内存。

如果你没有将此数据赋值给输出参数，并希望它在 MEX 文件完成后仍然存在，请在调用此函数后调用 `mxMakeMemoryPersistent`。如果你编写了带有持久内存的 MEX 文件，请确保注册一个 `mxAtExit` 函数，以便在 MEX 文件被清除时释放分配的内存。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcell.c`

## 另见

`mxMakeArray`, `mxDestroyArray`

## 版本历史

R2006a 之前

# mxSetData 的结果根据编译选项而异

行为在 R2018a 中发生变化

对于复杂的数值 `mxArray`，`mxSetData` 函数会根据 mex 编译选项设置不同的值。

如果使用默认的特定发布选项 (`-R2017b`) 编译 MEX 文件，则该函数将数组的元素设置为仅实部值。

如果使用 `-R2018a` 选项编译 MEX 文件，则：

- 当 `pm` 为实数数组时，`pa` 变为 `pm` 的实部组件。

- 当 `pm` 为复数数组时，`pa` 也必须是复数。否则，`pa` 的元素将变为交替的实部和虚部值，而不是仅实部值。

## 另见

主题

- `arrayFillSetData.c`

- "C MEX 文件中的类型数据访问"

- "MATLAB 支持 MEX 函数中的交替复数 API"

# mxSetData (Fortran)

设置非数值 `mxArray` 中数据元素的指针

注意：不建议将 `mxSetData` 用于数值数组。如果是类型数据，请改用数据访问函数。更多信息，请参阅“兼容性考虑”。

## Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxSetData(pm, pr)
mwPointer pm, pr
```

## 

使用 `mxSetData` 为非数值数组设置数据元素。

对于数值数组，MathWorks 建议使用交替复数 API 中的类型数据访问函数创建 MEX 文件并更新现有 MEX 文件。更多信息，请参阅：

- "C MEX 文件中的类型数据访问"

- "MATLAB 支持 MEX 函数中的交替复数 API"

- "升级 MEX 文件使用交替复数 API"

要编译 MEX 文件，请带有 `-R2018a` 选项调用 `mex`。

`mxSetData` 函数不释放为现有数据分配的内存。要释放现有内存，请对 `mxGetData` 返回的指针调用 `mxFree`。

## 输入参数

- `pm` — 指向非数值 MATLAB 数组的指针

`mwPointer`

指向非数值 MATLAB 数组的指针，指定为 `mwPointer`。

- `pa` — 指向数据数组的指针

`mwPointer`

指向 `mxArray` 内部数据数组的指针，指定为 `mwPointer`。

该数组必须在动态内存中。调用 `mxMalloc` 分配此内存。

## 版本历史

在 R2006a 之前引入

## mxSetData 的结果根据编译选项而异

行为在 R2018b 中发生变化

对于复杂的 `mxArray`，`mxSetData` 函数会根据 mex 编译选项设置不同的值。

如果使用默认的特定发布选项 (`-R2017b`) 编译 MEX 文件，则该函数将数组的 mex元素设置为仅实部值。

如果使用 `-R2018a` 选项编译 MEX 文件，则：

- 当 `pm` 为实数数组时，`pa` 变为 `pm` 的实部组件。

- 当 `pm` 为复数数组时，`pa` 也必须是复数。否则，`pa` 的元素将变为交替的实部和虚部值，而不是仅实部值。

## 另见

主题

- "C MEX 文件中的类型数据访问"

- "MATLAB 支持 MEX 函数中的交替复数 API"

# mxSetDimensions (C)

修改维度数量和每个维度的大小

## C 语法

```c
#include "matrix.h"
int mxSetDimensions(mxArray *pm, const mxSize *dims, mxSize nddim);
```

## 

`mxSetDimensions` 成功时返回 0，失败时返回 1。`mxSetDimensions` 分配堆空间来存储输入数组的大小。因此，可能（尽管不太）增加维度数量会导致系统耗尽堆空间。

调用 `mxSetDimensions` 来重塑现有 `mxArray`。`mxSetDimensions` 类似于 `mxSetM` 和 `mxSetN`；但是，`mxSetDimensions` 为重塑超过两个维度的 `mxArray` 提供了更好的控制。

`mxSetDimensions` 不为 `pr` 或 `pi` 数组分配或释放空间。因此，如果你调用 `mxSetDimensions` 增加了 `mxArray` 中的元素数量，请相应地增大 `pr`（以及 `pi`，如果存在）。

如果你调用 `mxSetDimensions` 减少了 `mxArray` 中的元素数量，你可以选择使用 `mxRealloc` 减小 `pr` 和 `pi` 数组的大小。

MATLAB 会自动移除 `dims` 中指定的任何尾随维度。例如，如果 `nddim` 等于 5 且 `dims` 等于 `[4 7 1 1]`，则生成的数组维度为 4-1-by7。

## 输入参数

- MATLAB 数组

`const mxArray*`

指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

- 维度数组

`mwSize`

维度数组。维度数组中的每个元素包含该数组在该维度上的尺寸，指定为 `mwSize`。例如，在 Fortran 中，将 `dims(1)` 设置为 5 `dims(2)` 设置为 7 会建立一个 5-by-7 `mxArray`。在大多数情况下，`dims`数组中有 `nddim` 个元素。

- 维度数量

`mwSize`

维度数量，指定为 `mwSize`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetdimensions.c`

## 版本历史

在 R2006a 之前引入

## 另见

`mxGetNumberOfDimensions` | `mxSetM` | `mxSetN` | `mxRealloc`

# mxSetDimensions (Fortran)

修改维度数量和每个维度的大小

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetDimensions(pm, dims, ndim)
mwPointer pm
mwSize ndim
mwSize dims(ndim)
```

`mxSetDimensions` 成功时返回 0，失败时返回 1。`mxSetDimensions` 分配堆空间来存储输入数组的大小。因此，可能（尽管不太）增加维度数量会导致系统耗尽堆空间。

调用 `mxSetDimensions` 来重塑现有 `mxArray`。`mxSetDimensions` 类似于 `mxSetM` 和 `mxSetN`；但是，`mxSetDimensions` 为重塑超过两个维度的 `mxArray` 提供了更好的控制。

`mxSetDimensions` 不为 `pr` 或 `pi` 数组分配或释放空间。因此，如果你调用 `mxSetDimensions` 增加了 `mxArray` 中的元素数量，请相应地增大 `pr`（以及 `pi`，如果存在）。

如果你调用 `mxSetDimensions` 减少了 `mxArray` 中的元素数量，你可以选择使用 `mxRealloc` 减小 `pr` 和 `pi` 数组的大小。

MATLAB 会自动移除 `dims` 中指定的任何尾随维度。例如，如果 `nddim` 等于 5 且 `dims` 等于 `[4 7 1 1]`，则生成的数组维度为 4-1-by7。

## 输入参数

- MATLAB 数组

`mwPointer`

指向 `mxArray` 数组的指针，指定为 `mwPointer`。

- 维度数组

`mwSize`



# 维度数组

维度数组中的每个元素包含该数组在该维度上的尺寸，指定为 `mwSize`。例如，在 Fortran 中，将 `dims(1)` 设置为 5，`dims(2)` 设置为 7 会建立一个 5-by-7 `mxArray`。在大多数情况下，`dims` 数组中有 `nddim` 个元素。

- 维度数量：`mwSize`

维度数量，指定为 `mwSize`。

## 示例

查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetdimensionsf.F`

## 版本历史

在 R2006a 之前引入

## 另请参阅

`mxGetNumberOfDimensions` | `mxSetM` | `mxSetN` | `mxRealloc`

# mxSetField (C 和 Fortran)

给定索引和字段设置结构数组中的字段值

## C 语法

```c
#include "matrix.h"
void mxSetField(mxArray *pm, mwIndex index,
               const char *fieldname, mxArray *pvalue);
```

## Fortran 语法

```fortran
#include "intrf.h"
subroutine mxSetField(pm, index, fieldname, pvalue)
mwPointer pm, pvalue
mwIndex index
character(*) fieldname
```

## 参数

- `pm`：指向结构 `mxArray` 的指针。调用 `mxIsStruct` 来确定 `pm` 是否指向 `mxArray`。
- `index`：数组中元素的索引。
  - 在 C 中，`mxArray` 的第一个元素索引为 0。最后一个元素的索引为 N-1，其中 N 是数组中的元素数量。
  - 在 Fortran 中，`mxArray` 的第一个元素索引为 1。最后一个元素的索引为 N，其中 N 是数组中的元素数量。
  - 计算索引的详情请参见 `mxCalcSingleSubscript`。
- `fieldname`：结构中的字段名称。该字段必须存在于结构中。调用 `mxFieldNameByNumber` 或 `mxGetFieldNumber` 来确定字段名。
- `pvalue`：指向要分配给 `fieldname` 的 `mxArray` 的指针。

## 描述

使用 `mxSetField` 将 `pvalue` 的内容分配给索引元素的字段。

如果你要替换 `fieldname` 的内容，请释放现有数据的内存。使用 `mxGetField` 函数获取字段指针，对指针调用 `mxDestroyArray`，然后调用 `mxSetField` 分配新值。

你不能将 `pvalue` 分配给结构中的多个元素或分配给 `mxArray` 中的多个元素。如果你想将 `pvalue` 的内容分配给多个字段，请使用 `mxDuplicateArray` 制作数据的副本，然后对每个副本调用 `mxSetField`。

要释放使用此函数创建的结构的内存，请仅对结构体数组调用 `mxDestroyArray`。不要对其指向的数组值调用 `mxDestroyArray`。如果这样做，MATLAB 将尝试两次释放同一内存，这会导致内存损坏。

> **注意** 输入 MEX 文件的输入是常量只读的 `mxArrays`。不要修改输入内容。使用 `mxSetCell*` 或 `mxSetField*` 函数修改 MATLAB 参数的单元格或字段会导致不可预测的结果。

## 示例

请查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcreatstructarray.c`

## 另请参阅

`mxCreateArray`、`mxCreateStructMatrix`、`mxGetField`、`mxGetFieldNameByNumber`、`mxGetFieldNameNumber`、`mxGetNumberOfFields`、`mxIsStruct`、`mxSetFieldByNumber`、`mxDestroyArray`、`mxCalcSingleSubscript`

# 替代方案

## C 语言

在 C 中，你可以将以下语句：

```c
field_num = mxGetFieldNumber(pa, "fieldname");
mxSetFieldByNumber(pa, index, field_num, new_value_pa);
```

替换为调用 `mxSetField`：

```c
mxSetField(pa, index, "fieldname", new_value_pa);
```

## Fortran 语言

在 Fortran 中，你可以将以下语句：

```fortran
fieldname = mxGetFieldNumber(pm, 'fieldname')
mxSetFieldByNumber(pm, index, fieldnum, newvalue)
```

替换为调用 `mxSetField`：

```fortran
mxSetField(pm, index, 'fieldname', newvalue)
```

## 版本历史

在 R2006a 之前引入

# mxSetFieldByNumber (C 和 Fortran)

给定的索引和字段编号，设置结构体数组中的字段值

## C 语法

```c
#include "matrix.h"
void mxSetFieldByNumber(mxArray *pm, mwIndex index,
int fieldnumber, mxArray *pvalue);
```

## Fortran 语法

```fortran
#include "intrf.hf"
subroutine mxSetFieldByNumber(pm, index, fieldnumber, pvalue)
mwPointer pm, pvalue
mwIndex index
integer*4 fieldnumber
```

## 参数

- **`pm`**：指向结构体 `mxArray` 的指针。调用 `mxIsStruct` 来确定 `pm` 是否指向结构体 `mxArray`。
- **`index`**：目标元素的索引。
  - 在 C 中，`mxArray` 的第一个元素的索引为 0。最后一个元素的索引为 N-1，其中 N 是数组中的元素个数。
  - 在 Fortran 中，`mxArray` 的第一个元素的索引为 1。最后一个元素的索引为 N，其中 N 是数组中的元素个数。
  - 索引计算详情请参见 `mxCalcSingleSubscript`。
- **`fieldnumber`**：字段在结构中的位置。该字段必须存在于结构中。
  - 在 C 中，每个元素中的第一个字段的编号为 0。最后一个字段编号为 N-1，其中 N 是字段总数。
  - 在 Fortran 中，每个元素中的第一个字段的编号为 1。最后一个字段的编号为 N，其中 N 是字段总数。
- **`pvalue`**：指向包含要赋值数据的 `mxArray` 的指针。

## 描述

使用 `mxSetFieldByNumber` 将 `pvalue` 的内容分配给元素 `index` 由 `fieldnumber` 指定的字段。`mxSetFieldByNumber` 类似于 `mxSetField`；然而，该函数通过位置编号而不是名称来标识字段。

如果你想替换 `fieldnumber` 处的内容，请先释放现有数据的内存。使用 `mxGetFieldByNumber` 函数获取字段指针，对该指针调用 `mxDestroyArray`，然后调用 `mxSetFieldByNumber` 分配新值。

你不能将 `pvalue` 分配给结构中的多个字段或分配到 `mxArray` 中的多个元素。如果你想将 `pvalue` 的内容分配给多个字段，请使用 `mxDuplicateArray` 创建数据的副本，然后对每个份副本调用 `mxSetFieldByNumber`。

要释放使用此函数创建的结构的内存，请仅对结构体数组调用 `mxDestroyArray`。不要对其指向的数组值调用 `mxDestroyArray`。如果这样做，MATLAB 将尝试两次释放同一内存，这会导致内存损坏。

输入 MEX 文件的输入是常量只读的 `mxArrays`。不要修改输入内容。使用 `mxSetCell*` 或 `mxSetField*` 函数修改 MATLAB 参数的单元格或字段会导致不可预测的结果。

# 替代方案

## C 语言

在 C 中，调用：

```c
mxSetField(pa, index, "field_name", new_value_pa);
```

等同于调用：

```c
field_num = mxGetFieldNumber(pa, "field_name");
mxSetFieldByNumber(pa, index, field_num, new_value_pa);
```

## Fortran 语言

在 Fortran 中，调用：

```fortran
mxSetField(pm, index, 'fieldname', newvalue)
```

等同于调用：

```fortran
fieldnum = mxGetFieldNumber(pm, 'fieldname')
mxSetFieldByNumber(pm, index, fieldnum, newvalue)
```

请查看 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxcreatstructarray.c`

## 另请参阅

`mxCreateStructArray`、`mxCreateStructMatrix`、`mxGetFieldByNumber`、`mxGetFieldNameByNumber`、`mxGetFieldNumber`、`mxGetNumberOfFields`、`mxIsStruct`、`mxSetField`、`mxDestroyArray`、`mxCalcSingleSubscript`

## 版本历史

在 R2006a 之前引入

# mxSetImageData (C)

在 `mxArray` 中设置虚部数据

> **注意** `mxSetImageData` 在 C 中不可用。

## C 语法

```c
#include "matrix.h"
void mxSetImageData(mxArray *pm, void *pi);
```

## 描述

`mxSetImageData` 函数类似于 `mxSetField`；然而，该函数通过位置编号而不是名称来标识字段。

如果你想替换 `fieldnumber` 处的内容，请先释放现有数据的内存。使用 `mxGetFieldBy` 获取字段指针，对该指针调用 `mxDestroyArray`，然后调用 `mxSetField` 分配新值。

你不能将 `pvalue` 分配给结构中的多个字段或分配到 `mxArray` 中的多个元素。如果你想将 `pvalue` 的内容分配给多个字段，请使用 `mxDuplicateArray` 创建数据的副本，然后对每个副本调用 `mxSetField`。

要释放使用此函数创建的结构的内存，请仅对结构体数组调用 `mxDestroyArray`。不要对其指向的数组值调用 `mxDestroyArray`。如果这样做，MATLAB 将尝试两次释放同一内存，这会导致内存损坏。

输入 MEX 文件的输入是常量只读的 `mxArrays`。不要修改输入内容。使用 `mxSetCell*` 或 `mxSetField*` 函数修改 MATLAB 参数的单元格或字段会导致不可预测的结果。

# 替代方案

## C 语言

在 C 中，调用：

```c
mxSetField(pa, index, "field_name", new_value_pa);
```

等同于调用：

```c
field_num = mxGetFieldNumber(pa, "field_name");
mxSetFieldByNumber(pa, index, field_num, new_value_pa);
```

## Fortran 语言

在 Fortran 中，调用：

```fortran
mxSetField(pm, index, 'fieldname', newvalue)
```

等同于调用：

```fortran
fieldnum = mxGetFieldNumber(pm, 'fieldname')
mxSetFieldByNumber(pm, index, fieldnum, newvalue)
```

## 版本历史

在 R2006a 之前引入

# mxSetImageData (Fortran)

在 `mxArray` 中设置虚部数据

> **注意** `mxSetImageData` 在 Fortran 中不可用。

## Fortran 语法

```fortran
#include "intrf.hf"
subroutine mxSetImageData(pm, pi)
mwPointer pm, pi
```

## 描述

`mxSetImageData` 函数类似于 `mxSetField`；然而。

- "MEX 函数中交错复数 API 的 MATLAB 支持"
- "升级 MEX 文件以使用交错复数 API"

要构建 MEX 文件，请带有 `-R2018a` 选项调用 `mex`。

## 使用交错复数 API 构建 mxSetImagData 时出错！

从 R2018b 开始出现的错误

`mxSetImagData` 函数仅在单独的复数 API 中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2017b myMexFile.F
```

使用此函数构建的现有 MEX 文件可以继续运行。

## 另请参阅

### 主题

- "C MEX 文件中的类型化数据访问"
- "MEX 函数中交错复数 API 的 MATLAB 支持"

# mxSetIr (C 和 Fortran)

稀疏数组的 ir 数组

## C 语法

```c
#include "matrix.h"
void mxSetIr(mxArray *mx, mxArray *pm, mwIndex *ir);
```

## Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxSetIr(pm, ir)
mwPointer, pm
mwIndex, ir
```

## 参数

- `pm`：指向稀疏 `mxArray` 的指针
- `ir`：指向 ir 数组的指针。ir 数组必须按列主顺序排序。

## 描述

使用 `mxSetIr` 指定稀疏 `mxArray` 的 ir 数组。ir 数组是一个整数数组；ir 数组的长度等于 `nzmax` 的值（为稀疏数组分配的存储）或 `nnz`（非零矩阵元素数量）。

ir 数组中的每个元素表示可以找到非零元素的行（偏移为 1）。`jc` 数组索引直接指定可以找到非零元素的列。关于 `jc` 的更多细节，请参阅 `mxSetJc`。

例如，假设你通过输入以下代码创建一个包含非零元素的 7x3 稀疏 `mxArray`：

```matlab
Sparse = zeros(7,3);
Sparse(2,1) = 1;
Sparse(5,1) = 1;
Sparse(3,2) = 1;
Sparse(2,3) = 2;
Sparse(5,3) = 1;
Sparse(6,3) = 1;
Sparse = sparse(Sparse);
```

`pr` 存储稀疏矩阵的实数据，在 `Sparse` 中为这五个 1 和一个 2。如果有任何非零数据，则在 `pi` 数组中。

| 下标 | ir | pr | jc | 注释 |
| :--- | :--- | :--- | :--- | :--- |
| (2,1) | 1 | 1 | 0 | 第1列；ir 为 1 是因为行是 2。 |
| (5,1) | 4 | 1 | 2 | 第1列；ir 为 4 是因为行是 5。 |
| (3,2) | 2 | 1 | 3 | 第2列；ir 为 2 是因为行是 3。 |
| (2,3) | 1 | 2 | 6 | 第3列；ir 为 1 是因为行是 2。 |
| (5,3) | 4 | 1 | | 第3列；ir 为 4 是因为行是 5。 |
| (6,3) | 5 | 1 | | 第3列；ir 为 5 是因为行是 6。 |

注意 ir 数组中的每个元素始终比对应非零元素的行数少 1。例如，第一个非零元素在第 2 行；因此，ir 中的第一个元素是 1（即 2 - 1）。第二个非零元素在第 5 行；因此，ir 中的第二个元素是 4 (5-1)。

ir 数组必须按列主顺序排列。ir 数组必须定义行位置。ir 数组必须按列主顺序定义第 1 列的行位置，然后是第 2 列，以此类推。ir 数组中的每个元素始终比对应非零元素的行数少 1。例如，第一个非零元素在第 2 行；因此，ir 中的第一个元素是 1 (即 2 - 1）。第二个非零元素在第 5 行；因此，ir 中的第二个元素是 4 (5-1)。

（注：原文此处存在部分重复描述，译文已按要求逻辑处理）

ir 数组必须按列主顺序排列。ir 数组必须定义第 1 列的行位置，然后是第 2 列，以此类推。

## 相关函数

`mxGetM` | `mxGetN` | `mxSetN` | `mxRealloc`

# mxSetM (Fortran)

设置 `mxArray` 的行数

## Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxSetM(pm, pi, m)
mwPointer pm
mwSize m
```

## 描述

`mxSetM` 设置指定 `mxArray` 的行数。行是指 `mxArray` 的第一维度，无论维度的数量如何。调用 `mxSetN` 来设置列数。

你通常使用 `mxSetM` 来更改现有 `mxArray` 的形状。`mxSetM` 函数不会为 `pr`、`pi`、`ir` 或 `jc` 数组分配或释放任何空间。因此，如果对 `mxSetM` 和 `mxSetN` 的调用增加了 `mxArray` 中的元素数量，则可能需要扩大 `pr`、`pi`、`ir` 和/或 `jc` 数组。调用 `mxRealloc` 来扩大这些数组。



如果调用 `mxSetM` 和 `mxSetN` 减少了 `mxArray` 中的元素数量，你可能希望减小 `pr`、`pi`、`ir` 和/或 `jc` 数组的大小，以更高效地使用堆空间。然而，减小大小不是强制性的。

### 输入参数

- **pm** — MATLAB 数组
  `mwPointer`
  指向 `mxArray` 数组的指针，指定为 `mwPointer`。

- **m** — 行数
  `mwSize`
  行数，指定为 `mwSize`。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.F`

## 版本历史

在 R2006a 之前引入

## 相关

`mxGetM` | `mxGetN` | `mxSetM` | `mxRealloc`

## mxSetN (C)

设置 `mxArray` 的列数

### C 语法

```c
#include "matrix.h"
void mxSetN(mxArray *pm, mwSize n);
```

## 描述

`mxSetN` 设置指定 `mxArray` 的列数。列始终是指矩阵的第二个维度。调用 `mxSetN` 会强制使一个 `mxArray` 具有两个维度。例如，如果 `pm` 指向一个具有三个维度的 `mxArray`，则调用 `mxSetN` 将该 `mxArray` 减少为两个维度。

你通常使用 `mxSetN` 来更改现有 `mxArray` 的形状。`mxSetN` 函数不会为 `pr`、`pi`、`ir` 或 `j` 数组分配或释放任何空间。因此，如果你对 `mxSetN` 和 `mxSetM` 的调用增加了 `mxArray` 中的元素数量，则扩大 `pr`、`pi`、`ir` 和/或 `j` 数组。

如果调用 `mxSetM` 和 `mxSetN` 减少了 `mxArray` 中的元素数量，你可能希望减小 `pr`、`pi`、`ir` 和/或 `j` 数组的大小，以更高效地使用堆空间。然而，减小大小不是强制性的。

### 输入参数

- **MATLAB 数组**
  `const mxArray*`
  指向 `mxArray` 数组的指针，指定为 `const mxArray*`。

- **列数**
  `mwSize`
  列数，指定为 `mwSize`。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetdimensions.c`

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `sincall.`

## 版本历史

在 R2006a 之前引入

## 相关

`mxGetM` | `mxGetN` | `mxSetM`

## mxSetN (Fortran)

设置 `mxArray` 的列数

### Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxSetN(pm, n)
mwPointer pm
mwSize n
```

## 描述

`mxSetN` 设置指定 `mxArray` 的列数。列始终是指矩阵的第二个维度。调用 `mxSetN` 会强制使一个 `mxArray` 具有两个维度。例如，如果 `pm` 指向一个具有三个维度的 `mxArray`，则调用 `mxSetN` 将该 `mxArray` 减少为两个维度。

你通常使用 `mxSetN` 来更改现有 `mxArray` 的形状。`mxSetN` 函数不会为 `pr`、`pi`、`ir` 或 `jc` 数组分配或释放空间。因此，如果对 `mxSetN` 和 `mxSetM` 的调用增加了 `mxArray` 中的元素数量，则扩大 `pr`、`pi`、`ir` 和/或 `jc` 数组。

如果调用 `mxSetM` 和 `mxSetN` 减少了 `mxArray` 中的元素数量，你可能希望减小 `pr`、`pi`、`ir` 和/或 `jc` 数组的大小，以更高效地使用堆空间。然而，减小大小不是强制性的。

### 输入参数

- **MATLAB 数组**
  `mwPointer`
  指向 `mxArray` 的指针，指定为 `mwPointer`。

- **列数**
  `mwSize`
  列数，指定为 `mwSize`。

## 示例

参见 `matlab/root/extern/examples/refbook` 中的这些示例：

- `sincall.F`

## 版本历史

在 R2006a 之前引入

## 相关

`mxGetM` | `mxGetN` | `mxSetM`

## mxSetNzmax (C and Fortran)

为非零元素设置存储空间

### C 语法

```c
#include "matrix.h"
void mxSetNzmax(mxArray *pm, mwSize nzmax);
```

### Fortran 语法

```fortran
#include "intrf.h"
subroutine mxSetNzmax(pm, nzmax)
mwPointer pm
mwSize nzmax
```

## 参数

- **pm**
  指向稀疏 `mxArray` 的指针。

- **nzmax**
  `mxCreateSparse` 分配的元素数量，用于存储由 `ir`、`pr` 和 `pi` 指向的数组（如果存在）。将 `nzmax` 设置为大于等于稀疏 `mxArray` 中的元素数量。如果指定 `nzmax` 为 0，则 `mxSetNzmax` 将 `nzmax` 设置为 1。

## 描述

使用 `mxSetNzmax` 设置稀疏 `mxArray` 的非零元素存储空间。`nzmax` 是稀疏 `mxArray` 中非零元素的数量。`ir`、`pr` 和 `pi` 数组（如果存在）的大小必须大于等于 `nzmax`。

如果对 `mxSetNmax` 和 `mxSetM` 的调用增加了稀疏 `mxArray` 中的非零元素数量，则可能需要扩大 `ir`、`pr`、`pi` 和/或 `j` 数组。调用 `mxalloc` 来扩大它们。

如果调用 `mxSetM` 和 `mxSetN` 减少了稀疏 `mxArray` 中的非零元素数量，你可能希望减小 `ir`、`pr`、`pi` 和/或 `j` 数组的大小，以更高效地使用堆空间。然而，减小大小不是强制性的。

## 示例

参见 `matlabroot/extern/examples/mx` 中的这些示例：

- `mxsetdimensions.c`

## 版本历史

在 R2006a 之前引入

## 相关

`mxGetmax` | `mxRealloc`

## mxSetPi (C)

（不推荐）设置 `mx_CLASS` 中的虚部元素

### C 语法

```c
#include "matrix.h"
void mxSetPi(mxArray *pm, double *pi);
```

## 描述

使用 `mxSetPi` 设置指定 `mxArray` 的虚部数据。`mxCreate*` 函数可选地分配堆空间来存储虚部，并将 `ComplexFlag` 设置为 true。调用此函数用新值替换现有值。

`mxSetPi` 函数不会释放已分配的内存。

### 输入参数

- **pm** — MATLAB 数组
  `mxArray *`
  指向类型为 `mx_CLASS` 的 MATLAB 数组，指定为 `mxArray *`。

- **pi** — 数据的指针
  `double *`
  指向 `mxArray` 内数据虚部分的第一个 `double` 元素，指定为 `double *`。数组中的每个元素包含值的虚部。

## 版本历史

在 R2006a 之前引入

## mxSetComplexDoubles

使用交错 API 中的函数代替代替 `SetPr` 和 `mxSetPi`。该函数验证输入数组是复杂的且类型为 `mx_CLASS`。

MathWorks 建议你创建 MEX 文件并更新现有 MEX 文件以使用交错 API 中的类型数据访问函数。更多信息，请参见：

- "C MEX 文件中的类型数据访问"
- "MATLAB 对交错复杂 API 的支持"
- "升级 MEX 文件以使用交错复杂 API"
- 示例 `arrayFillSetPr.c`

要构建 MEX 文件，请调用带有 `-R2018a` 选项的 `mex`。

## 从 R2018a 开始使用交错复杂 API 构建 mxSetPi 错误

`mxSetPi` 函数仅在独立复杂 API 中可用。使用此函数构建 `myMexFile.c`，请输入：

```
mex -R2017b myMexFile.c
```

使用此函数构建的现有 MEX 文件将继续运行。

## 相关

`mxSetComplexDoubles`

# mxSetPi (Fortran)

(不建议) 在 `mxDOUBLE_CLASS` 数组中设置虚数据元素

**注意** `mxSetPi` 不适用于交错复数 API (interleaved complex API)。请改用 `mxSetComplexDoubles`。更多信息，请参阅“兼容性考虑”（Compatibility Considerations）。

# Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxSetPi(pm, pi)
mwPointer pm, pi
```

# Description

使用 `mxSetPi` 设置指定 `mxArray` 的虚部数据。

大多数 `mxCreate*` 函数选择性地分配堆空间来存储虚部数据。如果你在调用 `mxCreate` 函数时分配了堆，请不要使用 `mxSetPi` 来初始化数组的虚部元素。相反，请调用此函数用新值替换现有值。分配空间的示例包括将 `ComplexFlag` 设置为 `mxCOMPLEX` 或将 `pi` 设置为非零值。

`mxSetPi` 函数不会释放为其覆盖的现有数据所分配的内存。要释放现有内存，请对 `mxGetPi` 返回的指针调用 `mxFree`。

# 输入参数

- **指向 MATLAB 数组的指针**
  `mwPointer`
  指向类型为 `mxDOUBLE_CLASS` 的 MATLAB 数组指针，指定为 `mwPointer`。

- **指向数据数组的指针**
  `mwPointer`
  指向 `mxArray` 内部数据数组虚部第一个 `mxDouble` 元素的指针，指定为 `mwPointer`。数组中的每个元素包含数值的虚部组件。

该数组必须在动态内存中；调用 `mxCalloc` 分配此内存。如果 `pi` 指向静态内存，则可能会导致内存泄漏和其他内存错误。

## 版本历史

在 R2006a 之前引入

**不要使用独立复数 API**

从 R2018b 开始不建议使用

请在交错复数 API 中使用 `mxSetComplexDoubles` 函数代替 `mxSetPr` 和 `mxSetPi`。此函数会验证输入数组是否为复数且类型是否为 `mxDOUBLE_CLASS`。

MathWorks 建议你创建 MEX 文件并更新现有的 MEX 文件，以使用交错复数 API 中的类型化数据访问函数。更多信息，请参阅：

- “Typed Data Access in C MEX Files”（C MEX 文件中的类型化数据访问）
- “MATLAB Support for Interleaved Complex API in MEX Functions”（MATLAB 对 MEX 函数中交错复数 API的支持）
- “Upgrade MEX Files to Use Interleaved Complex API”（升级 MEX 文件以使用交错复数 API）

要构建 MEX 文件，请带有 `-R201ba` 选项调用 `mex`。

**使用交错复数 API 构建 mxSetPi 错误**

从 R2018b 开始出现错误

`mxSetPi` 函数仅在独立复数 API可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2017b myMexFile.F
```

使用此函数构建的现有 MEX 文件可以继续运行。

# 另另相关

`mxSetComplexDoubles`

# 主题

- “Typed Data Access in C MEX Files”
- “MATLAB Support for Interleaved Complex API in MEX Functions”

# mxSetPr (C)

(不建议) 在 `mxDOUBLE_CLASS` 数组中设置实数据元素

**注意** `mxSetPr` 不适用于交错复数 API。请改用 `mxSetDoubles` 或 `mxSetComplexDoubles`。更多信息，请参阅“兼容性考虑”（Compatibility Considerations）。

# C 语法

```c
#include "matrix.h"
void mxSetPr(mxArray*pm, double *pr);
```

# Description

`mxSetPr` 函数设置实 `mxDOUBLE_CLASS` 数组 `pm` 的实部数据。如果你使用交错复数 API（`mex -R2018a` 选项）构建且 `pm` 是复数，该函数将终止 MEX 文件并将控制交回 MATLAB 提示符。在非 MEX 应用中，函数返回 NULL。

调用 `mxIsDouble` 来验证 `mxArray` 类型。调用 `mxIsComplex` 确定数据是否为实数。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常通常使用此函数来初始化数组的实部元素。相反，请调用此函数用新值替换现有值。

`mxSetPr` 函数不会释放为现有数据分配的内存。要释放现有内存，请对 `mxGetPr` 返回的指针调用 `mxFree`。

# 输入参数

- **pm** — 指向 MATLAB 数组的指针
  `mxArray *`
  指向类型为 `mxDOUBLE_CLASS` 的 MATLAB 数组指针，指定为 `mxArray *`。

- **pr** — 指向数据数组的指针
  `double *`
  指向 `mxArray` 内部数据数组实部第一个 `mxDouble` 元素的指针，指定为 `double *`。数组中的每个元素包含数值的实部组件。

数组必须在动态内存中。调用 `mxMalloc` 分配此内存。不要使用 ANSI C `calloc` 函数，这可能会导致内存对齐问题导致程序终止。如果 `pr` 指向静态内存，可能会导致内存泄漏和其他内存错误。

## 版本历史

在 R2006a 之前引入

**不要使用独立复数 API**

从 R2018a 开始不建议使用

对于类型为 `mxDOUBLE_CLASS` 的实数组，在交错复数 API中使用 `mxSetDoubles` 函数。对于类型为 `mxDOUBLE_CLASS` 的复数组使用 `mxSetComplexDoubles`。这些函数会验证输入的类型和复杂度。

Works 建议你创建 MEX 文件并更新现有的 MEX 文件为交错复数 API 中的类型化数据访问函数。更多信息，请参阅：

- “Typed Data Access in C MEX Files”
- “MATLAB Support for Interleaved Complex API in MEX Functions”
- “Upgrade MEX Files to Use Interleaved Complex API”
- Example `fulltosparse.c`

要构建 MEX 文件，请带有 `-R2018a` 选项调用 `mex`。

# 在交错复数 API 构建的应用中对复数 mxArrays 调用 mxSetPr 运行时错误

从 R2018a 开始出现错误

使用 `mxSetComplexDoubles` 函数代替 `mxSetPr` 和 `mxGetPi`。关于更新使用 `mxSetPr` 代码的示例，请参考 `mxsetmax.c`。

# 另另相关

`mxSetDoubles` `mxSetComplexDoubles`

# 主题

- `fulltosparse.c`
- `mxsetmax.c`
- “Typed Data Access in C MEX Files”
- “MATLAB Support for Interleaved Complex API in MEX Functions”

# mxSetPr (Fortran)

(不建议) 在 `mxDOUBLE_CLASS` 数组中设置实数据元素

**注意** `mxSetPr` 不适用于交错复数 API。请改用 `mxSetDoubles` 或 `mxSetComplexDoubles`。更多信息，请参阅“兼容性考虑”（Compatibility Considerations）。

# Fortran 语法

```fortran
#include "fintrf.h"
subroutine mxSetPr(pm, pr)
mwPointer pm, pr
```

# Description

如果你使用交错复数 API（`-R2018a` 选项）构建且 `pm` 是复数，`mxSetPr` 函数设置实 `mxDOUBLE_CLASS` 数组 `pm` 的实部数据将终止 MEX 文件并将控制交回 MATLAB 提示符。在非 MEX 应用中，函数返回 NULL。

调用 `mxIsDouble` 来验证 `mxArray` 类型。调用 `mxIsComplex` 确定数据是否为实数。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常通常使用此函数来初始化数组的实部元素。相反，调用此函数用新值替换现有值。

`mxSetPr` 函数不会释放为现有数据分配的内存。要释放现有内存，请对 `mxGetPr` 返回的指针调用 `mxFree`。

# 输入参数

- **pm** — 指向 MATLAB 数组的指针
  `mwPointer`
  指向类型为 `mxDOUBLE_CLASS` 的 MATLAB 数组指针，指定为 `mwPointer`。

- **pr** — 指向数据数组的指针
  `mwPointer`
  指向 `mxArray` 内部数据数组实部第一个 `mxDouble` 元素的指针，指定为 `mwPointer`。数组中的每个元素包含数值的实部组件。

该数组必须在动态内存中；调用 `mxCalloc` 分配此内存。如果 `pi` 指向静态内存，则可能会导致内存泄漏和其他内存错误。

## 版本历史

在 R2006a 之前引入

**不要使用独立复数 API**

从 R2018b 开始不建议使用

# mxSetProperty (C 和 Fortran)

设置 MATLAB 对象的公共属性值

## C 语法

```c
#include "matrix.h"
void mxSetProperty(mxArray *pa, mwIndex index,
const char *propname, const mxArray *value);
```

## Fortran 语法



```fortran
#include "fintrf.h"
subroutine mxSetProperty(pa, index, propname, value)
mwPointer pa, value
mwIndex index
char(*) propname
```

## 参数

- `pa`: 指向对象的 `mxArray` 指针。
- `index`: 对象数组中目标元素的索引。
- `propname`: 要赋值的属性名称。
- `value`: 指向要赋值的 `mxArray` 指针。

在 C 语言中，`mxArray` 的第一个元素索引为 `N-1`，其中 `N` 是数组中的元素个数。在 Fortran 中，`mxArray` 的第一个元素索引为 1。最后一个元素的索引为 `N`，其中 `N` 是数组中的元素个数。

## 描述

使用 `mxSetProperty` 为指定的属性赋值。在伪 C 术语中，`mxSetProperty` 执行以下赋值：

```c
pa[index].propname = value;
```

属性名必须是存在的公共属性，且索引必须在 `mxArray` 的范围内。要测试索引值，请使用 `mxGetNumberOfElements` 或 `mxGetM` 和 `mxGetN` 函数。

`mxSetProperty` 在分配新属性值之前会对该值进行复制。如果该属性使用了大量内存，复制可能会引起关注。堆中必须有足够的内存来存放该值的副本。

## 局限性

- `mxSetProperty` 不支持独立应用程序，例如使用 MATLAB 引擎 API 构建的应用程序。
- 不支持 datetime 类型的属性。

## 版本历史

在 R2008a 中引入

## 另见

`mxGetProperty` | 第 1-146 页的 "setProperty"

# mxGetDoubles (C) —— 实数数据元素

获取 `mxDOUBLE_CLASS` 数组中的实数数据元素。

## C 语法

```c
#include "matrix.h"
mxDouble *mxGetDoubles(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组
  - `const mxArray *`
  - 指向 `mxDOUBLE_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 | `NULL`
  - 指向数据中第一个 `mxDouble` 元素的指针。如果 `pa` 为 `NULL`，则该函数返回 `NULL`。

如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- 独立（非 MEX）应用程序 — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxDOUBLE_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/mex/` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetDoubles`

# mxGetComplexDoubles (C) —— 复数数据元素

获取 `mxDOUBLE_CLASS` 数组中的复数数据元素。

## C 语法

```c
#include "matrix.h"
mxComplexDouble *mxGetComplexDoubles(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组
  - `const mxArray *`
  - 指向 `mxDOUBLE_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组
  - `mxComplexDouble *`
  - 指向数据中第一个 `mxComplexDouble` 元素的指针。如果 `pa` 为 `NULL`，则该函数返回 `NULL`。

如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- 独立（非 MEX）应用程序 — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxDOUBLE_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/mex/` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetDoubles`

# mxSetDoubles (C)

设置 `mxDOUBLE_CLASS` 数组中的实数数据元素。

## C 语法

```c
#include "matrix.h"
int mxSetDoubles(mxArray *pa, mxDouble *dt);
```

## 描述

使用 `mxSetDoubles` 设置指定数组中的 `mxDouble` 数据。

所有 `mxCreate` 函数都会分配堆空间来存放数据。因此，通常不使用此函数来初始化数组元素。相反，调用该函数是为了替换现有值。

## 输入参数

- `pa` — MATLAB 数组
  - `mxArray *`
  - 指向 `mxDOUBLE_CLASS` 数组的指针。
- `dt` — 数据数组
  - `mxDouble *`
  - 指向数据数组中第一个 `mxDouble` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态
  - `int`
  - 以 `int` 类型返回函数状态。如果成功，函数返回 1。
  - 如果 `pa` 为 `NULL`，则函数返回 0。
  - 如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组，或者数据不是通过 `mxCalloc` 分配的，则函数失败。如果函数失败，则：
    - MEX 文件 — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
    - 独立（非 MEX）应用程序 — 函数返回 `NULL`。

## 示例

查看 `matlabroot/extern/examples/mex/` 中的这些示例。

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetDoubles`

# mxGetComplexInt16s (C)

获取 `mxINT16_CLASS` 数组中的复数元素。

## C 语法

```c
#include "matrix.h"
mxComplexInt16 *mxGetComplexInt16s(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组
  - `const mxArray *`
  - 指向 `mxINT16_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组
  - `mxComplexInt16 *`
  - 指向数据中第一个 `mxComplexInt16` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。

如果 `mxArray` 不是 `mxINT16_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- 独立程序（非 MEX 文件） — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxINT16_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

该函数在交错复数 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetComplexInt16s` | `mxGetInt16s`

# mxSetInt16s (C)

设置 `mxINT16_CLASS` 数组中的实数元素。

## C 语法

```c
#include "matrix.h"
int mxSetInt16s(mxArray *pa, mxInt16 *dt);
```

## 描述

使用 `mxSetInt16s` 在指定的数组中设置 `mxInt16` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组
  - `mxArray *`
  - 指向 `mxINT16_CLASS` 数组的指针。
- `dt` — 数据数组
  - `mxInt16 *`
  - 指向数据数组中第一个 `mxInt16` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- `status` — 函数状态
  - `int`
  - 函数状态，按原返回。如果成功，函数返回 1。
  - 如果 `pa` 为 `NULL`，函数返回 0。
  - 当 `mxArray` 不是共享的 `mxINT16_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：
    - MEX 文件 — 函数返回 MEX 文件并将控制权交回 MATLAB 提示符。
    - 独立程序（非 MEX 文件） — 函数返回 0。

## 示例

参考 `matlab/extern/examples/refbook` 文件夹中的 `arrayFillSetPr.c` 示例，该示例将输入的数据复制到 `mxArray` 中。示例中的数据定义为 `mxDouble`。要将此示例修改为 int16 数据：

- 将数据变量声明为 `mxInt16`
- 使用数值类型 `mxINT16_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetInt16s` 以将 C 数组放入 `mxArray`

## API 版本

该函数在交错复数 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetInt16s` | `mxSetUint16s` | `mxSetComplexInt16s`

# mxSetComplexInt16s (C)

设置 `mxINT16_CLASS` 数组中的复数元素。

## C 语法

```c
#include "matrix.h"
int mxSetComplexInt16s(mxArray *pa, mxComplexInt16 *dt);
```

## 描述

使用 `mxSetComplexInt16s` 在指定的数组中设置 `mxComplexInt16` 数据。

所有 `mxCreate*` 都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组
  - `mxArray *`
  - 指向 `mxINT16_CLASS` 数组的指针。
- `dt` — 数据数组
  - `mxComplexInt16 *`
  - 指向数据数组中第一个 `mxComplexInt16` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- `status` — 函数状态
  - `int`
  - 函数状态，作为 `int` 返回。如果成功，函数返回 1。
  - 如果 `pa` 为 `NULL`，函数返回 0。
  - 如果 `mxArray` 不是未共享的 `mxINT16_CLASS` 数组，或者数据未使用 `mxCalloc` 分配，则函数失败。如果函数失败，则：
    - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
    - 独立程序（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有的复数数据复制到 `mxArray` 中。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数类型的模式。要将此示例修改为复数 int16 数据：

- 将数据变量声明为 `mxInt16`
- 使用数值类型 `mxINT16_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetComplexInt16s` 以将 C 数组放入 `mxArray`

## API 版本

该函数在交错复数 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetInt16s` | `mxSetComplexInt16s`

# mxGetInt16s (C)

获取 `mxINT16_CLASS` 数组中的实数元素。

## C 语法

```c
#include "matrix.h"
mxInt16 *mxGetInt16s(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组
  - `const mxArray *`
  - 指向 `mxINT16_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组
  - `mxInt16 *`
  - 指向数据中第一个 `mxInt16` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。

如果 `mxArray` 不是 `mxINT16_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- 独立程序（非 MEX 文件） — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxINT16_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

该函数在交错复数 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetInt16s` | `mxGetComplexInt16s`

# mxSetUint16s (C)

设置 `mxINT16_CLASS` 数组中的无符号实数元素。

## C 语法

```c
#include "matrix.h"
int mxSetUint16s(mxArray *pa, mxUint16 *dt);
```

## 描述

使用 `mxSetUint16s` 在指定的数组中设置 `mxUint16` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组
  - `mxArray *`
  - 指向 `mxINT16_CLASS` 数组的指针。
- `dt` — 数据数组
  - `mxUint16 *`
  - 指向数据数组中第一个 `mxUint16` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- `status` — 函数状态
  - `int`
  - 函数状态，按原返回。如果成功，函数返回 1。
  - 如果 `pa` 为 `NULL`，函数返回 0。
  - 当 `mxArray` 不是共享的 `mxINT16_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：
    - MEX 文件 — 函数返回 MEX 文件并将控制权交回 MATLAB 提示符。
    - 独立程序（非 MEX 文件） — 函数返回 0。

## 示例

参考 `matlab/extern/examples/refbook` 文件夹中的 `arrayFillSetPr.c` 示例，该示例将输入的数据复制到 `mxArray` 中。示例中的数据定义为 `mxDouble`。要将此示例修改为 uint16 数据：

- 将数据变量声明为 `mxUint16`
- 使用数值类型 `mxINT16_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetUint16s` 以将 C 数组放入 `mxArray`

## API 版本

该函数在交错复数 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetInt16s` | `mxSetUint16s` | `mxSetComplexInt16s`

# mxSetComplexInt32s (C)

设置 `mxINT32_CLASS` 数组中的复数据元素。

## C 语法

```c
#include "matrix.h"
int mxSetComplexInt32s(mxArray *pa, mxComplexInt32 *dt);
```

## 描述

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxComplexInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组
  - `mxArray *`
  - 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组
  - `mxComplexInt32 *`
  - 指向数据数组中第一个 `mxComplexInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- `status` — 函数状态
  - `int`
  - 函数状态，作为 `int` 返回。如果成功，函数返回 1。
  - 如果 `pa` 为 `NULL`，函数返回 0。
  - 如果 `mxArray` 不是 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配，则函数失败。如果函数失败，则：
    - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
    - 独立程序（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有的复数数据复制到 `mxArray` 中。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数类型的模式。要将此示例修改为复数 int32 数据：

- 将数据变量声明为 `mxInt32`
- 使用数值类型 `mxINT32_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetComplexInt32s` 以将 C 数组放入 `mxArray`

## API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```c
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetInt32s` | `mxSetUint32s` | `mxSetComplexInt32s`



# mxSetComplexInt32s (C)

在指定的数组中设置 `mxComplexInt32` 数据。

## 语法

```c
#include "matrix.h"
int mxSetComplexInt32s(mxArray *pa, mxComplexInt32 *dt);
```

## 说明

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxComplexInt32` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)
  
  指向 `mxINT32_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxComplexInt32 *`)
  
  指向数据数组中第一个 `mxComplexInt32` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- **status** — 函数状态 (`int`)
  
  函数状态，以 `int` 类型返回。如果成功，则函数返回 1。
  
  如果 `pa` 为 `NULL`，则函数返回 0。
  
  如果 `mxArray` 不是未共享的 `mxINT32_CLASS` 数组，或者数据没有使用 `mxCalloc` 分配，则函数执行失败。如果函数失败，则：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

请参考 `matlab/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有的复数数值数据复制到 `mxArray` 中。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数 C 数值类型的模式。要修改此示例以适用于复杂的 int32 数据：

- 将数据变量声明为 `mxComplexInt32`
- 使用数值类型 `mxINT32_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetComplexInt32s` 以将 C 数组放入 `mxArray` 中

## API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxGetComplexInt32s` | `mxSetInt32s`

---

# mxGetInt64s (C)

`mxINT64_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
mxInt64 *mxGetInt64s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)
  
  指向 `mxINT64_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxInt64 *`)
  
  指向数据中第一个 `mxInt64` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。
  
  如果 `mxArray` 不是 `mxINT64_CLASS` 数组：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX）文件应用程序 — 返回 `NULL`。`NULL` 返回值表示 `pa` 为空或不是 `mxINT64_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错 API（interleaved API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetInt64s` | `mxGetUint64s` | `mxGetComplexInt64s`

---

# mxGetComplexInt64s (C)

`mxINT64_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
mxComplexInt64 *mxGetComplexInt64s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)
  
  指向 `mxINT64_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxComplexInt64 *`)
  
  指向数据中第一个 `mxComplexInt64` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。
  
  如果 `mxArray` 不是 `mxINT64_CLASS` 数组：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件） — 函数返回 `NULL`。`NULL` 返回值表示 `pa` 为空或不是 `mxINT64_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetComplexInt64s` | `mxGetInt64s`

---

# mxSetInt64s (C)

设置 `mxINT64_CLASS` 数组中的数据

## C 语法

```c
#include "matrix.h"
int mxSetInt64s(mxArray *pa, mxInt64 *dt);
```

## 说明

使用 `mxSetInt64s` 在指定的数组中设置数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)
  
  指向 `mxINT64_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxInt64 *`)
  
  指向数据中第一个 `mxInt64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- **status** — 函数状态 (`int`)
  
  函数状态，以 `int` 类型返回。如果成功，则函数返回 1。
  
  如果 `pa` 为 `NULL`，则函数返回 0。
  
  如果 `mxArray` 不是未共享的 `mxINT64_CLASS` 数组，或者数据没有使用 `mxCalloc` 分配，则函数执行失败。如果函数失败，则：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

请参考 `matlab/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有的复数数值数据复制到 `mxArray` 中。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数 C 数值类型的模式。要修改此示例以适用于复杂的 int32 数据：

- 将数据变量声明为 `mxComplexInt32`
- 使用数值类型 `mxINT32_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetComplexInt32s` 以将 C 数组放入 `mxArray` 中

## API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxGetInt64s` | `mxSetUint64s` | `mxSetComplexInt64s`

---

# mxSetComplexInt64s (C)

设置 `mxINT64_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
int mxSetComplexInt64s(mxArray *pa, mxComplexInt64 *dt);
```

## 说明

使用 `mxSetComplexInt64s` 在指定的数组中设置 `mxComplexInt64` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)
  
  指向 `mxINT64_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxComplexInt64 *`)
  
  指向数据数组中第一个 `mxComplexInt64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- **status** — 函数状态 (`int`)
  
  函数状态，以 `int` 类型返回。如果成功，则函数返回 1。
  
  如果 `pa` 为 `NULL`，则函数返回 0。
  
  如果 `mxArray` 不是未共享的 `mxINT64_CLASS` 数组，或者数据没有使用 `mxCalloc` 分配，则函数执行失败。如果函数失败，则：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

请参考 `matlab/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有的复数数值数据复制到 `mxArray` 中。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数 C 数值类型的模式。要修改此示例以适用于复杂的 int32 数据：

- 将数据变量声明为 `mxComplexInt32`
- 使用数值类型 `mxINT32_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetComplexInt32s` 以将 C 数组放入 `mxArray` 中

## API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxGetComplexInt64s` | `mxSetInt64s`

---

# mxGetInt8s (C)

`mxINT8_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
mxInt8 *mxGetInt8s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)
  
  指向 `mxINT8_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxInt8 *`)
  
  指向数据中第一个 `mxInt8` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。
  
  如果 `mxArray` 不是 `mxINT8_CLASS` 数组：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxINT8_CLASS` 数组。

## 示例

请参考 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交织 API（interleaved API）可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetInt8s` | `mxGetUint8s` | `mxGetComplexInt8s`

---

# mxGetComplexInt8s (C)

`mxINT8_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
mxComplexInt8 *mxGetComplexInt8s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)
  
  指向 `mxINT8_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxComplexInt8 *`)
  
  指向数据中第一个 `mxComplexInt8` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。
  
  如果 `mxArray` 不是 `mxINT8_CLASS` 数组：
  
  - MEX 文件 — 函数终止 MEX 文件并将控制权返回给 MATLAB 提示符。
  - 独立（非 MEX） — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxINT8_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交织 API 可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetComplexInt8s` | `mxGetInt8s`

---

# mxSetInt8s (C)

设置 `mxINT8_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
int mxSetInt8s(mxArray *pa, mxInt8 *dt);
```

## 说明

使用 `mxSetInt8s` 设置指定数组中的 `mxInt8` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)
  
  指向 `mxINT8_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxInt8 *`)
  
  指向数据数组中第一个 `mxInt8` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- **status** — 函数状态 (`int`)
  
  函数状态，按原样返回。如果成功，函数返回 1。
  
  如果 `pa` 为 `NULL`，函数返回 0。
  
  当 `mxArray` 不是未共享的 `mxINT8_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：
  
  - MEX 文件 — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 中的 `arrayFillSetPr.c` 示例，该示例将现有数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。为了针对 int8 数据修改此示例：

- 将数据声明为 `mxInt8`
- 使用类型 `mxINT8_CLASS` 调用 `mxCreateNumericMatrix`
- 使用 `mxSetInt8s` 替换 `mxSetDoubles` 将数组放入 `mxArray`

## API 版本

此函数在交织 API 可用。要使用此函数构建 `myMexFile.c`，请输入：

```bash
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxGetInt8s` | `mxSetUint8s` | `mxSetComplexInt8s`



# mxSetComplexInt8s (C)

设置 `mxINT8_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
int mxSetComplexInt8s(mxArray *pa, mxComplexInt8 *dt);
```

## 描述

使用 `mxSetComplexInt8s` 设置指定数组中的 `ComplexInt8` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)  
  指向 `mxINT8_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxComplexInt8 *`)  
  指向数组中第一个 `mxInt8` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- **status** — 函数状态 (`int`)  
  函数状态，按原样返回。如果成功，函数返回 1。

如果 `pa` 为 `NULL`，函数返回 0。

当 `mxArray` 不是 `mxINT8_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- **MEX 文件** — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 中的 `arrayFillSetPr.c` 示例，该示例将现有数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。你可以将此示例作为任何复数类型的模式：

- 将数据声明为 `mxInt8`
- 使用类型 `mxINT_CLASS` 调用 `mxCreateMatrix`
- 使用 `mxSetInt8` 将 C 数组放入 `mxArray`

## API 版本

此函数在交织复 API 可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxGetComplexInt8s` | `mxGetInt8s`

---

# mxGetSingles (C)

`mxSINGLE_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
mxSingle *mxGetSingles(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)  
  指向 `mxSINGLE_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxSingle *`)  
  指向数据中第一个 `mxSingle` 元素的指针。如果 `pa` 为 `NULL`，函数返回 `NULL`。

如果 `mxArray` 不是 `mxSINGLE_CLASS` 数组：

- **MEX 文件** — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxSINGLE_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/mex.c` 中的这些示例：

- `explore.c`

## API 版本

此函数在交织 API 可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetSingles` | `mxGetComplexSingles`

---

# mxGetComplexSingles (C)

`mxSINGLE_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
mxComplexSingle *mxGetComplexSingles(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)  
  指向 `mxSINGLE_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxComplexSingle *`)  
  指向数据中第一个 `mxComplexSingle` 元素的指针。如果 `pa` 为 `NULL`，函数返回 `NULL`。

如果 `mxArray` 不是 `mxSINGLE_CLASS` 数组：

- **MEX 文件** — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- **独立（非 MEX 应用程序）** — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxSINGLE_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交织复 API 可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetComplexSingles` | `mxGetSingles`

---

# mxSetSingles (C)

设置 `mxSINGLE_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
int mxSetSingles(mxArray *pa, mxSingle *dt);
```

## 描述

使用 `mxSetSingles` 设置指定数组中的 `mxSingle` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)  
  指向 `mxSINGLE_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxSingle *`)  
  指向数据数组中第一个 `mxSingle` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

当 `mxArray` 不是共享的 `mxSINGLE_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- **MEX 文件** — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 中的 `arrayFillSetPr.c` 示例，该示例将现有数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。为了针对单精度数据修改此示例：

---

# mxSetComplexSingles (C)

在 `mxSINGLE_CLASS` 数组中设置复数数据元素。

## C 语法

```c
#include "matrix.h"
int mxSetComplexSingles(mxArray *pa, mxComplexSingle *dt);
```

## 描述

使用 `mxSetComplexSingles` 设置存储数据的 `mxComplexSingle`。所有的 `mxCreate*` 都会分配堆空间来存储数据。因此，通常不使用此函数来初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB数组 (`mxArray *`)  
  指向 `mxSINGLE_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxComplexSingle *`)  
  指向数据数组中第一个 `mxComplexSingle` 元素的指针。`dt` 必须由 `mxMalloc` 或 `mxCalloc` 函数分配。

## 输出参数

- **status** — 函数状态 (`int`)  
  函数状态，以 `int` 形式返回。如果执行成功，函数返回 1。

如果 `pa` 为 `NULL`，函数返回 0。当 `mxArray` 不是未共享的 `mxSINGLE_CLASS` 数组，或者数据不是用 `mxCalloc` 分配时，函数执行失败。

如果函数执行失败，则：

- **MEX文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

## 示例

参考 `matlab/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，它将现有的复数数值数据拷贝到 `mxArray`。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数 C 数值的模式。

要将此示例修改为复数单数据：

- 将数据变量声明为 `mxComplexSingle`
- 使用数值类型 `mxSINGLE_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetComplexSingles` 以将 C 数组放入 `mxArray`。

## API 版本

此函数在交错复数 API 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetSingles` | `mxGetSingles`

---

# mxGetUint16s (C)

`mxUINT16_CLASS` 数组中的实数据元素。

## C 语法

```c
#include "matrix.h"
mxUint16 *mxGetUint16s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB数组 (`const mxArray *`)  
  指向 `mxUINT16_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxUint16 *`)  
  指向数据中 `mxUint16` 元素的指针。如果 `pa` 为 `NULL`，则返回 `NULL`。

如果 `mxArray` 不是 `mxUINT16_CLASS` 数组：

- **MEX文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxUINT16_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错 API 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetUint16s` | `mxGetInt16s` | `mxGetComplexUint16s`

---

# mxGetComplexUint16s (C)

`mxUINT16_CLASS` 数组中的复数数据元素。

## C 语法

```c
#include "matrix.h"
mxComplexUint16 *mxGetComplexUint16s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB数组 (`const mxArray *`)  
  指向 `mxUINT16_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxComplexUint16 *`)  
  指向数据中第一个 `mxComplexUint16` 元素的指针。如果 `pa` 为 `NULL`，则返回 `NULL`。

如果 `mxArray` 不是 `mxUINT16_CLASS` 数组：

- **MEX文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 应用程序）** — 函数返回 `NULL`。返回 `NULL` 值表示 `pa` 为空或不是 `mxUINT16_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错复数 API 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

---

# mxGetUint32s (C)

`mxUINT32_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
mxUint32 *mxGetUint32s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)  
  指向 `mxUINT32_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxUint32 *`)  
  指向数据中第一个 `mxUint32` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。

如果 `mxArray` 不是 `mxUINT32_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 `NULL`。返回值为 `NULL` 表示 `pa` 为空或不是 `mxUINT32_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex.c` 中的这些示例。

- `explore.c`

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetUint32s` | `mxGetInt32s` | `mxGetComplexUint32`

---

# mxGetComplexUint32s (C)

`mxUINT32_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
mxComplexUint32 *mxGetComplexUint32s(const mxArray *pa);
```

## 输入参数

- **pa** — MATLAB 数组 (`const mxArray *`)  
  指向 `mxUINT32_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组 (`mxComplexUint32 *`)  
  指向数据中第一个 `mxComplexUint32` 元素的指针。如果 `pa` 为 `NULL`，则函数返回 `NULL`。

如果 `mxArray` 不是 `mxUINT32_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
- **独立（非 MEX 文件）** — 函数返回 `NULL`。返回值为 `NULL` 表示 `pa` 为空或不是 `mxUINT32_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错复数 API (interleaved complex API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetComplexUint32s` | `mxGetUint32s`

---

# mxSetUint32s (C)

设置 `mxUINT32_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
int mxSetUint32s(mxArray *pa, mxUint32 *dt);
```

## 描述

使用 `mxSetUint32s` 设置指定数组中的 `mxUint32` 数据。

所有的 `mxCreate*` 都会分配堆空间来存储数据。因此，你通常不使用此函数初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组 (`mxArray *`)  
  指向 `mxUINT32_CLASS` 数组的指针。

- **dt** — 数据数组 (`mxUint32 *`)  
  指向数据数组中第一个 `mxUint32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- **status** — 函数状态 (`int`)  
  函数状态，按原样返回。如果成功，函数返回 1。

如果 `pa` 为 `NULL`，函数返回 0。

当 `mxArray` 不是未共享的 `mxUINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
- **独立（非 MEX 应用）** — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSet.c` 示例，它将现有数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。要为 uint32 修改此示例：

- 将数据声明为 `mx32`
- 使用数值类型 `mx32` 调用 `mxCreateNumericMatrix`
- 使用 `mxSetUint32s` 替换 `mxSetDoubles` 将 C 数组放入 `mxArray`

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```mat
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另请参阅

`mxSetComplexUint32s` | `mxGetUint32s`



# mxSetComplex32s (C)

`mxUINT32_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
int mxSetComplex32s(mxArray *pa, mxComplexUint32 *dt);
```

## 描述

使用 `mxSetComplex32s` 设置指定 `mxArray` 的 `mxUint32` 数据。所有的 `mxCreate*` 都会分配堆空间来存储数据。因此你通常不使用此函数初始化数组元素。相反，调用此函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向 `mxUINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mxComplexUint32 *`) 指向数据数组中第一个 `mxComplexUint32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`int`) 函数状态，按原样返回。如果成功，函数返回 1。

如果 `pa` 为 NULL，函数返回 0。如果 `mxArray` 不是未共享的 `mxUINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配，则函数失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
- 独立（非 MEX 文件） — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillComplex.c` 示例，它将现有的复数数据复制到 `mxArray`。你可以将此示例作为任何复数数值类型的模式。要为 `uint32` 修改此示例：

- 将数据声明为 `mx32`
- 使用数值类型 `mx32` 调用 `mxCreateNumericMatrix`
- 使用 `mxSetComplex32s` 替换 `mxSetDoubles` 将 C 数组放入 `mxArray`

## API 版本

此函数在交错复数 API (interleaved complex API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetComplex32s` | `mxSetUint32s`

---

# mxGetUint64s (C)

`mxUINT64_CLASS` 数组中的实数据元素

## C 语法

```c
#include "matrix.h"
mxUint64 *mxGetUint64s(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组 (`const mxArray *`) 指向 `mxUINT64_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mxUint64 *`) 指向数据中第一个 `mxUint64` 元素的指针。如果 `pa` 为 NULL，则函数返回 NULL。

如果 `mxArray` 不是 `mxUINT64_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
- 独立（非 MEX 应用） — 函数返回 NULL。返回值为 NULL 表示 `pa` 为空或不是 `mxUINT64_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex.c` 中的这些示例。

- `explore.c`

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetUint64s` | `mxGetInt64s` | `mxGetComplexUint64`

---

# mxGetComplexUint64s (C)

`mxUINT64_CLASS` 数组中的复数据元素

## C 语法

```c
#include "matrix.h"
mxComplexUint64 *mxGetComplexUint64s(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组 (`const mxArray *`) 指向 `mxUINT64_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mxComplexUint64 *`) 指向数据中第一个 `mxComplexUint64` 元素的指针。如果 `pa` 为 NULL，则函数返回 NULL。

如果 `mxArray` 不是 `mxUINT64_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
- 独立（非 MEX 文件） — 函数返回 NULL。返回值为 NULL 表示 `pa` 为空或不是 `mxUINT64_CLASS` 数组。

## 示例

请查看 `matlabroot/extern/examples/mex` 中的这些示例：

- `explore.c`

## API 版本

此函数在交错 API (interleaved API) 中可用。要使用此函数构建 `myMexFile.c`，请输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetComplexUint64s` | `mxGetUint64s`

---

# mxSetUint64s (C)

在 `mxUINT64_CLASS` 数组中设置数据元素

## C 语法

```c
#include "matrix.h"
int mxSetUint64s(mxArray *pa, mxUint64 *dt);
```

## Description

使用 `mxSetUint64s` 在指定的数组中设置 `mxUint64` 数据。

所有的 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不使用此函数来初始化数组的元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向一个 `mxUINT64_CLASS` 数组的指针。
- `dt` — 数据数组 (`mxUint64 *`) 指向数据数组中第一个 `mxUint64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`int`) 函数状态，按原返回。如果成功，函数返回 1。

如果 `pa` 为 NULL，函数返回 0。

当 `mxArray` 不是未共享的 `mxUINT64_CLASS` 数组，或者数据未由 `mxCalloc` 分配时，函数执行失败。如果函数失败：

- MEX 文件 — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- 独立（非 MEX）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSetPr.c` 示例，该示例将现有数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。要将此示例修改用于 `uint64` 数据：

- 将数据变量声明为 `mxUint64`
- 使用数值类型 `mxUINT64_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetUint64s` 以将 C 数组放入 `mxArray`

## API 版本

此函数在交错复合 API（interleaved complex API）可用。要使用此函数构建 `myMexFile.c`，输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetUint64s` | `mxSetInt64s` | `mxSetComplexUint64s`

---

# mxSetComplexUint64s (C)

在 `mxUINT64_CLASS` 数组中设置复合数据元素

## C 语法

```c
#include "matrix.h"
int mxSetComplexUint64s(mxArray *pa, mxComplexUint64 *dt);
```

## Description

使用 `mxSetComplexUint64s` 在指定的数组中设置复杂的 `mxComplexUint64` 数据。

所有的 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不使用此函数来初始化数组的元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向一个 `mxUINT64_CLASS` 数组的指针。
- `dt` — 数据数组 (`mxComplexUint64 *`) 指向数据数组中第一个 `mxComplexUint64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`int`) 函数状态，作为 `int` 返回。如果成功，函数返回 1。

如果 `pa` 为 NULL，函数返回 0。

当 `mxArray` 不是 `mxUINT64_CLASS` 数组，或者数据未用 `mxCalloc` 分配时，函数执行失败。如果函数失败，控制权：

- MEX 文件 — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有复合数值数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。你可以将此示例作为任何复合数值类型的模式。要将此示例修改用于 `uint64` 数据：

- 将数据变量声明为 `mxUint64`
- 使用数值类型 `mxUINT64_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetUint64s` 以将 C 数组放入 `mxArray`

## API 版本

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetComplexUint64s` | `mxSetUint64s`

---

# mxGetUint8s (C)

`mxUINT8_CLASS` 数组中的实际数据元素

## C 语法

```c
#include "matrix.h"
mxUint8 *mxGetUint8s(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向一个 `mxUINT8_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mxUint8 *`) 指向数据中第一个 `mxUint8` 元素的指针。如果 `pa` 为 NULL，函数返回 NULL。

如果 `mxArray` 不是 `mxUINT8_CLASS` 数组：

- MEX 文件 — 终止 MEX 文件并返回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 NULL。

NULL 值表示 `pa` 为空或不是 `mxUINT8_CLASS` 数组。

## 示例

参考 `matlabroot/extern/examples/mex`: `explore.c`

## API 版本

使用此函数构建 `myMexFile.c`，类型输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetUint8s` | `mxGetInt8s`

---

# mxGetComplexUint8s (C)

`mxUINT8_CLASS` 数组中的复合数据元素

## C 语法

```c
#include "matrix.h"
mxComplexUint8 *mxGetComplexUint8s(const mxArray *pa);
```

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向一个 `mxUINT8_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mxComplexUint8 *`) 指向数据中第一个 `mxComplexUint8` 元素的指针。如果 `pa` 为 NULL，函数返回 NULL。

如果 `mxArray` 不是 `mxUINT8_CLASS` 数组：

- MEX 文件 — 终止 MEX 文件并返回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 NULL。

NULL 值表示 `pa` 为空或不是 `mxUINT8_CLASS` 数组。

## 示例

参考 `matlabroot/extern/examples/mex`: `explore.c`

## API 版本

此函数在交错 API 中可用。使用此函数构建 `myMexFile.c`，输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxSetComplexUint8s` | `mxGetUint8s`

---

# mxSetUint8s (C)

`mxUINT8_CLASS` 数组中的实际数据元素

## C 语法

```c
#include "matrix.h"
int mxSetUint8s(mxArray *pa, mxUint8 *dt);
```

## Description

使用 `mxSetUint8s` 在 `mxUINT8_CLASS` 数组中设置 `uint8` 数据。

所有的 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向一个 `mxUINT8_CLASS` 数组的指针。
- `dt` — 数据数组 (`mxUint8 *`) 指向数据数组中第一个 `mxUint8` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`int`) 函数状态，作为 `int` 返回。如果成功，函数返回 1。

如果 `pa` 为 NULL，函数返回 0。

当 `mxArray` 不是未共享的 `mxUINT8_CLASS` 数组，或者数据未由 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- 独立（非 MEX）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSetPr.c` 示例，该示例将现有数据复制到 `mxArray`。示例中的数据定义为 `mxDouble`。要将此示例修改用于 `uint8` 数据：

- 将数据变量声明为 `mxUint8`
- 使用数值类型 `mxUINT8_CLASS` 调用 `mxCreateNumericMatrix`
- 将 `mxSetDoubles` 替换为 `mxSetUint8s` 以将 C 数组放入 `mxArray`

## API 版本

此函数在交错 API 中可用。使用此函数构建 `myMexFile.c`，输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetUint8s` | `mxSetInt8s`

---

# mxSetComplexUint8s (C)

`mxUINT8_CLASS` 数组中的复合数据元素

## C 语法

```c
#include "matrix.h"
int mxSetComplexUint8s(mxArray *pa, mxComplexUint8 *dt);
```

## Description

使用 `mxSetComplexUint8s` 在 `mxUINT8_CLASS` 数组中设置复杂的 `mxComplexUint8` 数据。

所有的 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mxArray *`) 指向一个 `mxUINT8_CLASS` 数组的指针。
- `dt` — 数据数组 (`mxComplexUint8 *`) 指向数据数组中第一个 `mxComplexUint8` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`int`) 函数状态，作为 `int` 返回。如果成功，函数返回 1。

如果 `pa` 为 NULL，函数返回 0。

当 `mxArray` 不是 `mxUINT8_CLASS` 数组，或者数据未用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 终止 MEX 文件并将控制权返回给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## 示例

参考 `matlabroot/extern/examples/refbook` 文件夹中的 `arrayFillSetComplexPr.c` 示例，该示例将现有复合数值数据复制到 `mxArray`。示例中的数据定义为 `mxComplexDouble`。你可以将此示例作为任何复数类型的模式。要修改此示例以处理复杂的 `uint8` 数据：

- 将数据变量声明为 `mxComplexUint8`
- 调用 `mxCreateNumericMatrix` 并指定数值类型 `mxUINT8_CLASS`
- 将 `mxSetDoubles` 替换为 `mxSetComplexUint8s` 以将 C 数组放入 `mxArray` 中

## API 版本

此函数在交错存储格式的复数型 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.c`，请输入：

```
mex -R2018a myMexFile.c
```

## 版本历史

在 R2018a 中引入

## 另见

`mxGetComplexUint8s` | `mxSetUint8s`

---

# mxGetDoubles (Fortran)

`mxDOUBLE_CLASS` 数组中的实数据元素

## Fortran 语法

```
#include "intrf.h"
mwPointer mxGetDoubles(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`) 指向 `mxDOUBLE_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer` | `0`) 指向数据中第一个 `mxDouble` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxDOUBLE_CLASS` 数组。

## API 版本

此函数在交错存储格式的 API（interleaved API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

`mxSetDoubles` (Fortran)

---

# mxGetComplexDoubles (Fortran)

`mxDOUBLE_CLASS` 数组中的复数数据元素

## Fortran 语法

```
#include "intrf.h"
mwPointer mxGetComplexDoubles(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`) 指向 `mxDOUBLE_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`) 指向数据中第一个 `mxComplexDouble` 元素的指针。如果 `pa` 为 0，则函数返回 0。



如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxDOUBLE_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `convex.F`
- `complexAdd.F`

# API 版本

此函数在交错存储格式的复数型 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

`mxSetComplexDoubles (Fortran)`

# mxSetDoubles (Fortran)

设置 `mxDOUBLE_CLASS` 数组中的实数据元素

## Fortran 语法

```
#include "intrff.h"
integer*4 mxSetDoubles(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetDoubles` 在指定的数组中设置 `mxDouble` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，应调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxDOUBLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxDouble` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态
  - **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - **独立（非 MEX 文件）应用程序** — 函数返回 0。

# API 版本

此函数在交错存储格式的复数型 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

`mxGetDoubles (Fortran)`

# mxSetComplexDoubles (Fortran)

设置 `mxDOUBLE_CLASS` 数组中的复数数据元素

## Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetComplexDoubles(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetComplexDoubles` 在指定的数组中设置 `mxComplexDouble` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxDOUBLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数组中第一个 `mxComplexElement` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：作为 `integer*4` 返回的函数状态。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是 `mxDOUBLE_CLASS` 数组或数据未通过 `mxCalloc` 分配时，函数执行失败：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

# API 版本

此函数在交错存储格式的 API（interleaved API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

# mxGetInts (Fortran)

`mxDOUBLE_CLASS` 数组中的实数据元素

## Fortran 语法

```
#include "intrf.h"
mwPointer mxGetInts(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxDOUBLE_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`)：指向数据中第一个 `mxDouble` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxDOUBLE_CLASS` 数组。

# API 版本

此函数在交错存储格式的 API（interleaved API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

# mxGetComplex16s (Fortran)

`mxDOUBLE_CLASS` 数组中的复数数据元素

## Fortran 语法

```
#include "intrf.h"
mwmPointer mxGetComplex16s(pa)
mwmPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwmPointer` | 0)：指向 `mxDOUBLE_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`)：指向数据中第一个 `mxComplexDouble` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxDOUBLE_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxDOUBLE_CLASS` 数组。

## 示例

查看 `matlabroot/extern/examples/refbook` 中的这些示例：

- `convex.F`
- `complexAdd.F`

# API 版本

此函数在交错存储格式的复数型 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

`mxSetComplexDoubles (Fortran)`

# mxSetDoubles (Fortran)

设置 `mxDOUBLE_CLASS` 数组中的实数据元素

## Fortran 语法

```
#include "intrff.h"
integer*4 mxSetDoubles(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetDoubles` 在指定的数组中设置 `mxDouble` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxDOUBLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxDouble` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态
  - **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
  - **独立（非 MEX 文件）应用程序** — 函数返回 0。

# API 版本

此函数在交错存储格式的复数型 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

`mxGetDoubles (Fortran)`

# mxSetComplexDoubles (Fortran)

设置 `mxDOUBLE_CLASS` 数组中的复数数据元素

## Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetDoubles(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetDoubles` 在指定的数组中设置 `mxComplexDouble` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxDOUBLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数组中第一个 `mxComplexElement` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：作为 `integer*4` 返回的函数状态。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxDOUBLE_CLASS` 数组或数据未通过 `mxCalloc` 分配时，函数执行失败：

- **MEX 文件** — 函数终止 MEX 文件并将控制权交回 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

# API 版本

此函数在交错存储格式的复数型 API（interleaved complex API）中可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另见

# mxSet16s (Fortran)

设置 `mxDOUBLE_CLASS` 数组中的实数据元素

## Fortran 语法

```
#include "fintrf.h"
integer*4 mxSet16s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSet16s` 在指定的数组中设置 `mxInt16` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxDOUBLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxInt16` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：作为 `integer*4` 返回的函数状态。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetInt16s (Fortran)`

# mxSetComplexInt16s (Fortran)

在 `mxINT16_CLASS` 数组中设置复数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt16s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetComplexInt16s` 在指定的数组中设置 `mxComplexInt16` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT16_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxComplexInt16` 元素的指针。`dt` 必须由 `mxMallococ` 或 `mxMalloc` 函数分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT16_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败：

- **MEX 文件** — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

# API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetComplexInt16s (Fortran)`

# mxGetInt32s (Fortran)

`mxINT32_CLASS` 数组中的实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT32_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`)：指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetInt32s (Fortran)`

# mxGetComplexInt32s (Fortran)

`mxINT32_CLASS` 数组中的复数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT32_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer` | 0)：指向数据中第一个 `mxGetComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- **MEX 文件** — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetComplexInt32s (Fortran)`

# mxSetInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt32s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- **MEX 文件** — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- **独立（非 MEX 文件）应用程序** — 函数返回 0。

# API 版本



此函数在交错复数 API（`interleaved complex API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetInt32s` (Fortran)

# mxSetComplexInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt16` 元素的指针。`dt` 必须由 `mxoc` 或 `mxMalloc` 分配。

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT16_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（`interleaved complex API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetComplexInt16s` (Fortran)

# mxGetInt32s (Fortran)

`mxINT32_CLASS` 数组中的实数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（`interleaved API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetInt32s` (Fortran)

# mxGetComplexInt32s (Fortran)

`mxINT32_CLASS` 数组中的复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxGetComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（`interleaved API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetComplexInt32s` (Fortran)

# mxSetInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置实数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（`interleaved complex API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetInt32s` (Fortran)

# mxSetComplexInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt16` 元素的指针。`dt` 必须由 `mxoc` 或 `mxMalloc` 分配。*（注：此处原文 `mxMallococ` 似为 `mxMallococ` 的笔误，译文保留原意或根据上下文微调）*

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT16_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（`interleaved complex API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetComplexInt16s` (Fortran)

# mxGetInt32s (Fortran)

`mxINT32_CLASS` 数组中的实数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（`interleaved API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetInt32s` (Fortran)

# mxGetComplexInt32s (Fortran)

`mxINT32_CLASS` 数组中的复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxGetComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（`interleaved API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetComplexInt32s` (Fortran)

# mxSetInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置实数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（`interleaved complex API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetInt32s` (Fortran)

# mxSetComplexInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt16` 元素的指针。`dt` 必须由 `mxoc` 或 `mxMalloc` 分配。

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT16_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（`interleaved complex API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetComplexInt16s` (Fortran)

# mxGetInt32s (Fortran)

`mxINT32_CLASS` 数组中的实数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（`interleaved API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetInt32s` (Fortran)

# mxGetComplexInt32s (Fortran)

`mxINT32_CLASS` 数组中的复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxGetComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（`interleaved API`）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetComplexInt32s` (Fortran)

# mxSetInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置实数数据元素



# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetInt32s` (Fortran)

---

# mxSetComplexInt32s (Fortran)

在 `mxINT32_CLASS` 数组中设置复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt32s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt16` 元素的指针。`dt` 必须由 `mxoc` 或 `mxMalloc` 分配。

# 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT16_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxGetComplexInt16s` (Fortran)

---

# mxGetInt32s (Fortran)

`mxINT32_CLASS` 数组中的实数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetInt32s` (Fortran)

---

# mxGetComplexInt32s (Fortran)

`mxINT32_CLASS` 数组中的复数数据元素

# Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

# 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

# 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxGetComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

# API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 参见

`mxSetComplexInt32s` (Fortran)



```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

# mxGetComplexInt32s (Fortran)

## mxINT32_CLASS 数组中的复数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxSetComplexInt32s` (Fortran)

---

# mxSetInt32s (Fortran)

## 在 mxINT32_CLASS 数组中设置实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt32s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxGetInt32s` (Fortran)

---

# mxSetComplexInt32s (Fortran)

## 在 mxINT32_CLASS 数组中设置复数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt32s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxComplexInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxGetComplexInt32s` (Fortran)

---

# mxGetInt32s (Fortran)

## mxINT32_CLASS 数组中的实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxSetInt32s` (Fortran)



```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

# mxGetInt32s (Fortran)

mxINT32_CLASS 数组中的实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt32s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxSetInt32s` (Fortran)

---

# mxGetComplexInt32s (Fortran)

mxINT32_CLASS 数组中的复数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt32s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxComplexInt32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT32_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxSetComplexInt32s` (Fortran)

---

# mxSetInt32s (Fortran)

在 mxINT32_CLASS 数组中设置实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt32s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxGetInt32s` (Fortran)

---

# mxSetComplexInt32s (Fortran)

在 mxINT32_CLASS 数组中设置复数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt32s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetComplexInt32s` 在指定的数组中设置 `mxInt32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，通常不会使用此函数来初始化数组的元素。相反，调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT32_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt32` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 形式返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享 `mxINT32_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxGetComplexInt32s` (Fortran)

---

# mxGetInt64s (Fortran)

mxINT64_CLASS 数组中的实数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt64s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT64_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer`): 指向数据中第一个 `mxInt64` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT64_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT64_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxSetInt64s` (Fortran)

---

# mxGetComplexInt64s (Fortran)

mxINT64_CLASS 数组中的复数数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt64s(pa)
mwPointer pa
```

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT64_CLASS` 数组的指针。

## 输出参数

- `dt` — 数据数组 (`mwPointer` | 0): 指向数据中第一个 `mxComplexInt64` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT64_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交还 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxINT64_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。使用此函数构建 `myMexFile.F`，请输入：

```fortran
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 参见

`mxSetComplexInt64s` (Fortran)

---

# mxSetInt64s (Fortran)

设置 mxINT64_CLASS 数组中的数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt64s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetInt64s` 设置所持 `mxArray` 的 `mxInt64` 数据。

所有 `mxCreate` 函数都会分配空间来存储数据。因此，你通常不会使用此函数来初始化数组的元素。相反，请调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT64_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxInt64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxINT64_CLASS` 数组或数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另请参考

`mxGetInt64s` (Fortran)

---

# mxSetComplexInt64s (Fortran)

设置 mxINT64_CLASS 数组中的复数据元素

## Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt64s(pa, dt)
mwPointer pa, dt
```

## Description

使用 `mxSetComplexInt64s` 设置指定数组中的 `mxComplexInt64` 数据。

所有 `mxCreate` 函数都会分配空间来存储数据。因此，你通常不会使用此函数来初始化数组的元素。相反，请调用该函数用新值替换现有值。

## 输入参数

- `pa` — MATLAB 数组 (`mwPointer`): 指向 `mxINT64_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`): 指向数据数组中第一个 `mxComplexInt64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

## 输出参数

- `status` — 函数状态 (`integer*4`): 函数状态，以 `integer*4` 返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxINT64_CLASS` 数组或数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

## 另请参考

`mxGetComplexInt64s` (Fortran)



所有 `mxCreate*` 函数都会分配空间来存储数据。因此，你通常不会使用此函数来初始化数组的元素。相反，请调用该函数用新值替换现有值。

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT64_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxComplexInt64` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

### 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxINT64_CLASS` 数组或数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并返回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxGetComplexInt64s` (Fortran)

## mxGetInt8s (Fortran)

`mxINT8_CLASS` 数组中的实数据元素

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetInt8s(pa)
mwPointer pa
```

### 输入参数

`pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT8_CLASS` 数组的指针。

### 输出参数

`dt` — 数据数组 (`mwPointer`)：指向数据中第一个 `mxInt8` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxINT8_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回 0 表示 `pa` 为空或不是 `mxINT8_CLASS` 数组。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `matsqint8.F`

### API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxSetInt8s` (Fortran)

## mxGetComplexInt8s (Fortran)

`mxINT_CLASS` 数组中的复数据元素

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetComplexInt8s(pa)
mwPointer pa
```

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxINT_CLASS` 数组的指针。

### 输出参数

- `dt` — 数据数组 | 0 (`mwPointer`)：指向数据中第一个 `mxGetComplexInt8` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是共享的 `mxINT_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxSetInt8s` (Fortran)

## mxSetInt8s (Fortran)

`mx8_CLASS` 数组中的实数据元素

### Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetInt8s(pa, dt)
mwPointer pa, dt
```

### Description

使用 `mxSetInt8s` 设置数组中的 Int8 数据。

所有 `mxCreate` 函数都会分配空间来存储数据。因此，你通常不会使用此函数来初始化数组的元素。相反，请调用该函数用新值替换现有值。

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mx8_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 Int8 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

### 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mx8_CLASS` 数组或数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxGetComplexInt8s` (Fortran)

## mxSetComplexInt8s (Fortran)

设置 `mx8_CLASS` 数组中的复数据元素

### Fortran 语法

```fortran
#include "fintrf.h"
integer*4 mxSetComplexInt8s(pa, dt)
mwPointer pa, dt
```

### Description

使用 `mxSetComplexInt8s` 设置指定数组中的 `mxComplexInt8` 数据。

所有 `mxCreate*` 函数都会分配空间来存储数据。因此，你通常不会使用此函数来初始化数组的元素。相反，请调用该函数用新值替换现有值。

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mx8_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxComplexInt8` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

### 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 返回。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mx8_CLASS` 数组或数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并返回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交叉复合 API (interleaved complex API) 中可用。使用此函数构建 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxGetComplexInt64s` (Fortran)

## mxGetSingles (Fortran)

`mxSINGLE_CLASS` 数组中的实数据元素

### Fortran 语法

```fortran
#include "fintrf.h"
mwPointer mxGetSingles(pa)
mwPointer pa
```

### 输入参数

`pa` — MATLAB 数组 (`mwPointer`)：指向 `mxSINGLE_CLASS` 数组的指针。

### 输出参数

`dt` — 数据数组 (`mwPointer`)：指向数据中第一个 `mxSingle` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxSINGLE_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制交回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回 0 表示 `pa` 为空或不是 `mxSINGLE_CLASS` 数组。

## 示例

参见 `matlabroot/extern/examples/refbook` 中的这些示例：

- `matsqint8.F`

## mxGetComplexSingles (Fortran)

`mxSINGLE_CLASS` 数组中的复数数据元素

### Fortran Syntax

```fortran
#include "fintrf.h"
mwPointer mxGetComplexSingles(pa)
mwPointer pa
```

### 输入参数

`pa` — MATLAB 数组 (`mwPointer`)：指向 `mxSINGLE_CLASS` 数组的指针。

### 输出参数

`dt` — 数据数组 (`mwPointer` | 0)：指向数据中第一个 `mxGetComplexelement` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxSINGLE_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxSINGLE_CLASS` 数组。

### API 版本

此函数在交错式 API（interleaved API）中可用。要使用此函数编译 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxSetComplexSingles` (Fortran)

## mxSetSingles (Fortran)

`mxSINGLE_CLASS` 数组中的实数数据元素

### Fortran Syntax

```fortran
#include "fintrf.h"
integer*4 mxSetSingles(pa, dt)
mwPointer pa, dt
```

### Description

使用 `mxSetSingles` 在指定的数组中设置 `mxSingle` 数据。

所有 `mxCreate` 函数都会分配堆空间来存储数据。因此，通常不会使用该函数来初始化数组元素。相反，调用该函数用新值替换现有值。

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxSINGLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxSingle` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

### 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxSINGLE_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数执行失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数编译 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxGetSingles` (Fortran)

## mxSetComplexSingles (Fortran)

`mxSINGLE_CLASS` 数组中的复数数据元素

### Fortran Syntax

```fortran
#include "fintrf.h"
integer*4 mxSetComplexSingles(pa, dt)
mwPointer pa, dt
```

### Description

使用 `mxSetComplexSingles` 在指定的数组中设置 `mxComplexSingle` 数据。

所有 `Complex*` 函数都会分配空间来存储数据。因此，通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxSINGLE_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxComplexSingle` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

### 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。

如果 `pa` 为 0，函数返回 0。

当 `mxArray` 不是共享的 `mxSINGLE_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数执行失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数编译 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxGetComplexSingles` (Fortran)

## mxGetUint16s (Fortran)

`mxUINT16_CLASS` 数组中的实数数据元素

### Fortran Syntax

```fortran
#include "fintrf.h"
mwPointer mxGetUint16s(pa)
mwPointer pa
```

### 输入参数

`pa` — MATLAB 数组 (`mwPointer`)：指向 `mxUINT16_CLASS` 数组的指针。

### 输出参数

`dt` — 数据数组 (`mwPointer`)：指向数据中第一个 `mxUint16` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxUINT16_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxUINT16_CLASS` 数组。

### API 版本

此函数在交错式 API（interleaved API）中可用。要使用此函数编译 `myMexFile.F`，输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxSetUint16s`

## mxGetComplexUint16s (Fortran)

`mxUINT16_CLASS` 数组中的复数数据元素

### Fortran Syntax

```fortran
#include "fintrf.h"
mwPointer mxGetComplexUint16s(pa)
mwPointer pa
```

### 输入参数

`pa` — MATLAB 数组 (`mwPointer`)：指向 `mxUINT16_CLASS` 数组的指针。

### 输出参数

`dt` — 数据数组 (`mwPointer` | 0)：指向数据中第一个 `mxGetComplexU16` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxUINT16_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxUINT16_CLASS` 数组。

### API 版本

此函数在交错式 API（interleaved API）中可用。要使用此函数编译 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxSetUint16s` (Fortran)

## mxSetUint16s (Fortran)

`mxUINT16_CLASS` 数组中的实数数据元素

### Fortran Syntax

```fortran
#include "fintrf.h"
integer*4 mxSetUint16s(pa, dt)
mwPointer pa, dt
```

### Description

使用 `mxSetUint16s` 在指定的数组中设置 `mxUint16` 数据。

所有 `mxCreate` 函数都会分配空间来存储数据。因此，通常不会使用该函数来初始化数组元素。相反，调用该函数用新值替换现有值。

### 输入参数

- `pa` — MATLAB 数组 (`mwPointer`)：指向 `mxUINT16_CLASS` 数组的指针。
- `dt` — 数据数组 (`mwPointer`)：指向数据数组中第一个 `mxUint16` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

### 输出参数

- `status` — 函数状态 (`integer*4`)：函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxUINT16_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数执行失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

### API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数编译 `myMexFile.F`，请输入：

```bash
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

### 另请参考

`mxGetUint16s` (Fortran)



函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxSINGLE_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数执行失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API（interleaved complex API）中可用。要使用此函数编译 `myMexFile.F`，输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxGetComplexSingles` (Fortran)

# mxSetComplexUint16s (Fortran)

`mxUINT16_CLASS` 数组中的复数数据元素

# Fortran Syntax

```
#include "fintrf.h"
integer*4 mxSetComplexUint16s(pa, dt)
mwPointer pa, dt
```

# Description

使用 `mxSetComplexUint16s` 在指定的数组中设置 `mxComplexUint16` 数据。

所有 Complex 函数都会分配空间来存储数据。因此，通常不会使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

# 输入参数

- **pa — MATLAB 数组**

`mwPointer`

指向 `mxSINGLE_CLASS` 数组的指针。

- **dt — 数据数组**

`mwPointer`

指向数据数组中第一个 `mxComplexUint16` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

# 输出参数

- **status — 函数状态**

`integer*4`

函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。

如果 `pa` 为 0，函数返回 0。

当 `mxArray` 不是共享的 `mxSINGLE_CLASS` 数组，或者数据未使用 `mxCalloc` 分配时，函数执行失败。如果函数执行失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxGetComplexUint16s` (Fortran)

# mxGetUint32s (Fortran)

`mxUINT32_CLASS` 数组中的实数据元素

# Fortran 语法

```
#include "fintrf.h"
mwPointer mxGetUint32s(pa)
mwPointer pa
```

# 输入参数

`pa` — MATLAB 数组

`mwPointer`

指向 `mxUINT32_CLASS` 数组的指针。

# 输出参数

`dt` — 数据数组

`mwPointer`

指向数据中第一个 `mxUint32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxUINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxUINT32_CLASS` 数组。

# API 版本

此函数在交错 API 中可用。要使用此函数编译 `myMexFile.F`，请：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxSetUint32s` | `mxGetComplexUint32s`

# mxGetComplexUint32s (Fortran)

`mxUINT32_CLASS` 数组中的复数据元素

# Fortran 语法

```
#include "fintrf.h"
mwPointer mxGetComplexUint32s(pa)
mwPointer pa
```

# 输入参数

`pa` — MATLAB 数组

`mwPointer`

指向 `mxUINT32_CLASS` 数组的指针。

# 输出参数

`dt` — 数据数组

`mwPointer` | 0

指向数据中第一个 `mxComplexUint32` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxUINT32_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxUINT32_CLASS` 数组。

# API 版本

此函数在交错 API 中可用。要使用此函数编译 `myMexFile.F`，请：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxSetComplexUint32s` (Fortran)

# mxSetUint32s (Fortran)

设置 `mxUINT32_CLASS` 数组中的实数据元素

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetUint32s(pa, dt)
mwPointer pa, dt
```

## 描述

使用 `mxSetUint32s` 在指定的数组中设置 `mxUint32` 数据。

所有 `mxCreate*` 函数都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，调用该函数用新值替换现有值。

# 输入参数

`pa` — MATLAB 数组

`mwPointer`

指向 `mxUINT32_CLASS` 数组的指针。

`dt` — 数据数组

`mwPointer`

指向数据数组中第一个 `mxUint32` 元素的指针。`dt` 必须由函数 `mxCalloc` 或 `mxMalloc` 分配。

# 输出参数

`status` — 函数状态

`integer*4`

函数状态，返回类型为 `integer*4`。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxUINT32_CLASS` 数组，或者数据未用 `mxCalloc` 分配时，函数失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并返回 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错复数 API 中可用。要使用此函数编译 `myMexFile.F`，请：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxGetUint32s` (Fortran)

# mxSetComplexUint32s (Fortran)

设置 `mxUINT32_CLASS` 数组中的复数据元素

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetComplexUint32s(pa, dt)
mwPointer pa, dt
```

## 描述

使用 `mxSetComplexUint32s` 设置指定 `mxArray` 的 `mxUint32` 数据。

所有 `mxComplex` 函数都会分配堆空间来存储数据。因此，你通常不使用此函数来初始化数组元素。相反，调用此函数用新值替换现有值。

# 输入参数

- **pa** — MATLAB 数组

`mwPointer`

指向 `mxUINT32_CLASS` 数组的指针。

- **dt** — 数据数组

`mwPointer`

指向数据数组中第一个 `mxComplexUint32` 元素的指针。`dt` 必须由函数 `mxMalloc` 或 `mxMalloc` 分配。

# 输出参数

- **status** — 函数状态

`integer*4`

函数状态，返回类型为 `integer*4`。如果成功，则函数返回 1。

如果 `pa` 为 0，则函数返回 0。

当 `mxArray` 不是共享的 `mxUINT32_CLASS` 数组，或者数据未用 `mxMalloc` 分配时，函数失败。如果函数失败，则：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。

# API 版本

此函数在交错 API 中可用。要使用此函数编译 `myMexFile.F`，请：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxGetUint32s` (Fortran)

# mxGetUint64s (Fortran)

`mxUINT64_CLASS` 数组中的实数据元素

# Fortran 语法

```
#include "fintrf.h"
mwPointer mxGetUint64s(pa)
mwPointer pa
```

# 输入参数

`pa` — MATLAB 数组

`mwPointer`

指向 `mxUINT64_CLASS` 数组的指针。

# 输出参数

`dt` — 数据数组

`mwPointer`

指向数据中第一个 `mxUint64` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxUINT64_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxUINT64_CLASS` 数组。

# API 版本

此函数在交错 API 中可用。要使用此函数编译 `myMexFile.F`，请：

```
mex -R2018a myMexFile.F
```

## 版本历史

在 R2018b 中引入

# 另见

`mxSetUint64s` | `mxGetComplexUint64s`

# mxGetComplexUint64s (Fortran)

`mxUINT64_CLASS` 数组中的复数据元素

# Fortran 语法

```
#include "fintrf.h"
mwPointer mxGetComplexUint64s(pa)
mwPointer pa
```

# 输入参数

`pa` — MATLAB 数组

`mwPointer`

指向 `mxUINT64_CLASS` 数组的指针。

# 输出参数

`dt` — 数据数组

`mwPointer` | 0

指向数据中第一个 `mxComplexUint64` 元素的指针。如果 `pa` 为 0，则函数返回 0。

如果 `mxArray` 不是 `mxUINT64_CLASS` 数组：

- MEX 文件 — 函数终止 MEX 文件并将控制权交还给 MATLAB 提示符。
- 独立（非 MEX 文件）应用程序 — 函数返回 0。返回值 0 表示 `pa` 为空或不是 `mxUINT64_CLASS` 数组。

# API 版本

此函数在交错 API 中可用。要使用此函数编译 `myMexFile.F`，请：

```
mex -R2018a myMexFile.F
```

## 版本历史

引入于 R2018b

# 另见

`mxGetUint64s` (Fortran)

# mxSetComplexUint64s (Fortran)

在 `mxUINT64_CLASS` 数组中设置复数据元素

# Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetComplexUint64s(pa, dt)
mwPointer pa, dt
```

## 描述

使用 `mxSetComplexUint64s` 在指定的数组中设置复杂的 `mxComplexUint64` 数据。

所有的 `Complex*` 函数都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，应该调用该函数用新值替换现有值。

# 输入参数

- **pa** — MATLAB 数组

`mwPointer`

指向 `mxUINT64_CLASS` 数组的指针。



# mxGetComplexUint64s (Fortran)

指向 `mxUINT64_CLASS` 数组的指针。

## 输入参数

- **pa** — MATLAB 数组
  `mwPointer`
  指向 `mxUINT64_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组
  `mwPointer`
  指向数组中第一个 `mxComplexUint64` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- **status** — 函数状态
  `integer*4`
  函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。
  如果 `pa` 为 0，则函数返回 0。
  当 `mxArray` 不是共享的 `mxUINT64_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败。如果函数失败，则：
  - MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

引入于 R2018b

## 另请参阅

`mxGetComplexUint64s` (Fortran)

---

# mxGetUint8s (Fortran)

在 `mxUINT8_CLASS` 数组中的实数数据元素

## Fortran 语法

```
#include "fintrf.h"
mwPointer mxGetUint8s(pa)
mwPointer pa
```

## 输入参数

- **pa** — MATLAB 数组
  `mwPointer`
  指向 `mxUINT8_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组
  `mwPointer`
  指向数据中第一个 `mxUint8` 元素的指针。如果 `pa` 为 0，则函数返回 0。
  如果 `mxArray` 不是第一个 `mxUINT8_CLASS` 数组：
  - MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。返回 0 表示 `pa` 既为空或不是 `mxUINT8_CLASS` 数组。

## API 版本

此函数在交错 API（interleaved API）可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

引入于 R2018b

## 另请参阅

`mxSetUint8s`

---

# mxGetComplexUint8s (Fortran)

在 `mxUINT8_CLASS` 数组中的复数数据元素

## Fortran 语法

```
#include "fintrf.h"
mwPointer mxGetComplexUint8s(pa)
mwPointer pa
```

## 输入参数

- **pa** — MATLAB 数组
  `mwPointer`
  指向 `mxUINT8_CLASS` 数组的指针。

## 输出参数

- **dt** — 数据数组
  `mwPointer` | 0
  指向数据中第一个 `mxGetComplexUint8` 元素的指针。如果 `pa` 为 0，则函数返回 0。
  如果 `mxArray` 不是 `mxUINT8_CLASS` 数组：
  - MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。返回 0 表示 `pa` 既为空或不是 `mxUINT8_CLASS` 数组。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

引入于 R2018b

## 另请参阅

`mxSetComplexUint8s` (Fortran)

---

# mxSetUint8s (Fortran)

在 `mxUint8_CLASS` 数组中设置实数数据元素

## Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetUint8s(pa, dt)
mwPointer pa, dt
```

## 描述

使用 `mxSetUint8s` 在指定的数组中设置 `mxUint8` 数据。
所有的 Create* 都会分配空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，应该调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组
  `mwPointer`
  指向 `mxUint8_CLASS` 数组的指针。
- **dt** — 数据数组
  `mwPointer`
  指向数据数组中第一个 `mxUint8` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- **status** — 函数状态
  `integer*4`
  函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。
  如果 `pa` 为 0，则函数返回 0。
  当 `mxArray` 不是 `mx8_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败。如果函数失败，则：
  - MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

引入于 R2018b

## 另请参阅

`mxGetUint8s` (Fortran)

---

# mxSetComplexUint8s (Fortran)

在 `mxUINT8_CLASS` 数组中设置复数数据元素

## Fortran 语法

```
#include "fintrf.h"
integer*4 mxSetComplexUint8s(pa, dt)
mwPointer pa, dt
```

## 描述

使用 `mxSetComplexUint8s` 在指定的数组中设置 `mxComplexUint8` 数据。
所有的 Complex* 都会分配堆空间来存储数据。因此，你通常不会使用此函数来初始化数组元素。相反，应该调用该函数用新值替换现有值。

## 输入参数

- **pa** — MATLAB 数组
  `mwPointer`
  指向 `mxUINT8_CLASS` 数组的指针。
- **dt** — 数据数组
  `mwPointer`
  指向数组中第一个 `mxComplexUint8` 元素的指针。`dt` 必须由 `mxCalloc` 或 `mxMalloc` 函数分配。

## 输出参数

- **status** — 函数状态
  `integer*4`
  函数状态，以 `integer*4` 类型返回。如果成功，函数返回 1。
  如果 `pa` 为 0，则函数返回 0。
  当 `mxArray` 不是共享的 `mxUINT8_CLASS` 数组，或者数据未使用 `mxMalloc` 分配时，函数执行失败。如果函数失败，则：
  - MEX 文件 — 函数终止 MEX 文件并将控制权交给 MATLAB 提示符。
  - 独立（非 MEX 文件）应用程序 — 函数返回 0。

## API 版本

此函数在交错复数 API（interleaved complex API）可用。要使用此函数构建 `myMexFile.F`，请输入：

```
mex -R2018a myMexFile.F
```

## 版本历史

引入于 R2018b
