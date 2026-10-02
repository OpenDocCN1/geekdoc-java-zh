
`appender` 决定将消息记录在何处。例如，一个 `appender` 可以将消息写入系统控制台，而另一个 `appender` 可以将其写入数据库。

![](img/c89c22ff51802d920b32d2b061ce5aea_109_0.png)

`logger` 可以使用多个 `appender`。

`formatter` 决定消息如何打印。

图 5.11 `appender`、`logger` 和 `formatter` 之间的关系。`logger` 使用一个或多个 `appender`（例如，只记录由包中的对象打印的消息）。`logger` 将要写入的消息传递给一个或多个 `appender`。然后每个 `appender` 实现存储消息的特定方式。`appender` 使用 `formatter` 在存储消息之前对其进行格式化。

## 第 5 章 充分利用日志：审计应用行为

`logger` 定义了应用记录的内容。在示例中，我们使用 `Root` 来写入来自应用任何部分的消息。它的属性 `level` 值为 `info`，意味着只有严重性为 `info` 和更高的消息会被记录。`logger` 还可以决定记录来自特定部分的消息。例如，在使用框架时，你通常对你应用的日志消息感兴趣，因此你可以定义一个 `logger`，排除框架的打印，只打印来自你应用的消息。请记住，你只想编写必要的日志消息。否则，如果你必须过滤掉非必要的日志消息，调查过程可能会变得异常困难。

`appender` 还使用一个 `formatter` 来定义消息的格式。在示例中，`formatter` 指定消息应该包含时间戳和严重性级别，因此应用只需要发送描述信息。

代码列表 5.5 显示了同时定义 `appender` 和 `logger` 的配置。在示例中，我们只定义了一个 `appender`，它告诉 Log4j 将消息写入系统的标准输出流（控制台）。

### 代码列表 5.5 在 `log4j2.xml` 文件中配置 `appender` 和 `logger`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
  <Appenders><!-- 定义一个 appender -->
    <Console name="Console" target="SYSTEM_OUT">
      <PatternLayout="%d{yyyy-MM-dd HH:mm:ss.SSS} [%t] %5level %logger{36} - %msg%n"/>
    </Console>
  </Appenders>
  <Loggers> <!-- 定义 logger 配置 -->
    <Root level="info">
      <AppenderRef ref="Console"/>
    </Root>
  </Loggers>
</Configuration>
```

图 5.12 直观地展示了代码列表 5.5 中的 XML 配置与其定义的三个组件（`logger`、`appender` 和 `formatter`）之间的联系。

## 5.2 实现日志

我们定义了一个名为 `Console` 的 `appender`。它将日志消息发送到系统的标准输出流 `SYSTEM_OUT`。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
  <Appenders>
    <Console name="Console" target="SYSTEM_OUT">
      <Pattern pattern="%d{yyyy-MM-dd HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"/>
    </Console>
  </Appenders>
  <Loggers>
    <Root level="info">
      <AppenderRef ref="Console"/>
    </Root>
  </Loggers>
</Configuration>
```

![](img/c89c22ff51802d920b32d2b061ce5aea_111_0.png)

我们配置了一个 `logger`，接收所有严重性级别为 `info` 的消息，并将它们发送到名为 `Console` 的 `appender`。

`appender` 使用一个 `formatter` 来定义消息的外观。通过使用模式（`pattern`），我们配置 `formatter` 在每条消息上附加时间戳和严重性级别。

图 5.12 配置中的组件。`logger` 接收所有它接受的严重性级别为 `info` 的消息。`logger` 将消息发送到名为 `Console` 的 `appender`。`appender` 配置为将消息发送到系统。它在写入消息之前使用 `formatter` 在消息上附加时间戳和严重性级别。

接下来的片段显示了示例运行时打印的日志部分。注意，`debug` 消息没有被记录，因为它们的严重性低于 `info`（代码列表 5.5 中的第 10 行）。

```
2021-07-28 13:17:39.915 [main] INFO main.StringExtractor - Extracting digits for input abc
2021-07-28 13:17:39.932 [main] INFO main.StringExtractor - Extract digits result for input abc is [1]
```

## 第 5 章 充分利用日志：审计应用行为

```
2021-07-28 13:17:39.943 [main] INFO main.StringExtractor - Extracting digits for input abc
2021-07-28 13:17:39.943 [main] INFO main.StringExtractor - Extract digits result for input abc is [1]
```

如果我们想记录严重性级别为 `debug` 的消息，我们需要更改 5.6。

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
  <Appenders>
    <Console name="Console" target="SYSTEM_OUT">
      <Pattern pattern="%d{yyyy-MM-dd HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"/>
    </Console>
  </Appenders>
  <Loggers>
    <Root level="debug">
      <AppenderRef ref="Console"/>
    </Root>
  </Loggers>
</Configuration>
```

`logger` 属性显示了哪些消息会被写入。5.6 的配置：

```
2021-07-28 13:17:39.943 [main] INFO main.StringExtractor - Extracting digits for input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character a of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character b of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character c of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character d of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character e of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character 1 of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character 2 of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character f of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character g of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character h of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character i of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character j of input abc
2021-07-28 13:17:39.943 [main] DEBUG main.StringExtractor - Parsing character k of input abc
2021-07-28 13:17:39.943 [main] INFO main.StringExtractor - Extract digits result for input abc is [1]
```

日志库提供了灵活性，只记录你需要的内容。编写尽可能少的日志消息是一种良好的实践，这可以帮助你更容易理解日志并保持应用性能良好。日志库还允许你在无需重新编译应用的情况下配置日志。

## 5.2.3 日志引起的问题以及避免它们

我们记录日志是为了理解应用在特定时间点或一段时间内的行为。日志在很多情况下是必要的且非常有用的，但如果处理不当也会变成危害。在本节中，我们讨论了日志可能引起的三个问题以及避免它们的方法（图 5.13）：

- 安全和隐私问题——日志消息暴露了隐私数据
- 性能问题——应用存储了过多或过大的日志消息
- 可维护性问题——日志指令导致源代码更难以阅读

### 安全和隐私问题

安全是我感兴趣的话题之一，也是开发者在实现应用时需要考虑的重要科目之一。我写的一本书就是关于安全的，如果你使用 Spring 框架实现应用并想了解更多如何保护它们，我推荐你阅读：Spring Security in Action（Manning, 2020）。

令人遗憾的是，日志有时会导致应用程序的漏洞，在大多数情况下，这些问题是因为开发者没有注意他们暴露的细节。日志库会使特定的细节对任何可以访问日志的人可见。你都需要考虑你记录给那些可以访问日志的数据（图 5.14）。

# 第 5 章 充分利用日志：审计应用程序的行为

我会记录这些身份验证密钥，以确保我们收到的请求经过正确的签名。

太棒了！我会获取那些私钥，然后我就可以对任何请求签名。

![](img/c89c22ff51802d920b32d2b061ce5aea_114_0.png)

我会记录手机号码，以确保应用向正确的接收者发送短信通知。

太棒了！我会收集这些手机号码并将它们公开，这家公司将受到严重的制裁。

![](img/c89c22ff51802d920b32d2b061ce5aea_114_1.png)

图 5.14 日志消息不应包含秘密或隐私细节。任何开发应用程序或部署应用程序的基础设施的人员都不应访问此类数据。在日志中暴露敏感细节可以帮助恶意人员（黑客）找到更简单的方法破坏系统或创建安全相关问题。

以下代码段显示了一些暴露敏感细节并导致漏洞的日志消息示例：

```
Successful login.
User bob logged in with password RwjBaWIS66
```

```
Failed authentication.
The token is unsigned.
The token should have a signature with IVL4KiKmfz.
```

```
A new notification was sent to
the following phone number +1233...
```

这里显示的日志有什么问题？第一条日志消息暴露了隐私细节。你不应该记录用于签名令牌的密码或私钥，或任何其他交换的信息。密码是由于原因只有其所有者知道的东西。因此，任何应用程序都不应以明文（在日志或数据库中）显示密码。私钥和类似的秘密细节应存储在库中以防止被盗取。如果有人获取了密钥的值，他们就可以冒充应用程序或用户。

第三个日志消息示例暴露了手机号码。手机号码被视为个人细节，全球范围内特定法规限制此类细节的使用。例如，欧盟实施了《通用数据保护条例》(GDPR)。

## 5.2 实现日志记录

2018 年 5 月实施了《通用数据保护条例》(GDPR)。在任何欧盟国家拥有用户的应用程序必须遵守这些规定，以避免严重制裁。这些规定允许任何用户请求应用程序使用的所有个人数据，并请求立即删除这些数据。在日志中存储手机号码等信息会暴露这些隐私细节，并使检索和删除它们变得困难。

### 性能问题

写入日志涉及发送（通常以字符串形式）通过应用程序外部的某个 I/O 流。我们可以简单地将此信息发送到应用程序的控制台（终端），将其存储在文件或数据库中，正如我们在 5.2.1 中讨论的那样。无论哪种方式，你都需要记住记录消息是一个耗时的指令；添加过多日志会显著降低应用程序的性能。

我记得我的团队年前调查过这个问题。亚洲的一个客户报告了我们在工厂实现的用于库存目的应用程序存在问题。该问题并没有引起太大麻烦，但我们发现找到根源很有挑战性，因此我们决定添加更多的日志消息。在交付带有细微更改的补丁后，系统变得非常慢，有时无响应，这最终导致了生产停滞，我们不得不快速撤销我们的更改。我们以某种方式成功地把蚊子变成了大象。

> 我们的客户显然不高兴，但我们成功地快速回滚，避免了非常糟糕的后果。

糟糕的问题！结果还好吗？

![](img/c89c22ff51802d920b32d2b061ce5aea_115_0.png)

> 关键在于，从我身上吸取教训，不要犯同样的错误。

从自己的错误中学习是好的：从别人的错误中学习是最好的。

但简单的日志消息如何会导致如此大的麻烦呢？日志被配置为将消息发送到网络中的另一台服务器，并在那里进行持久化。不仅该工厂的网络极慢，而且日志消息被添加到了遍历大量条目的循环中，导致应用程序变得极其缓慢。

最后，我们学到了一些东西，帮助我们更加小心并避免重复同样的错误：

# 第 5 章 充分利用日志：审计应用程序的行为

- 确保你理解应用程序是如何记录消息的。记住，即使对于同一个应用程序，部署也可能有不同的配置（见第 5.2.2 节）。
- 避免记录过多的消息。不要在遍历大量元素的循环中记录消息。记录过多的消息也会让日志变得复杂。如果你需要在大循环中记录消息，请使用条件来缩小记录消息的迭代次数。
- 确保你的应用程序仅在真正需要时存储日志消息。你通过使用日志级别来限制存储日志消息的数量，正如我们在 5.2.2 节中讨论的那样。
- 实现日志机制，以便你可以在不重启服务的情况下启用和禁用。这将允许你切换到更细粒度的日志级别，获取所需的细节，然后再次降低日志的敏感性。

### 可维护性

日志消息也可能负面影响应用程序的可维护性。如果你过于频繁地添加日志消息，它们会让应用程序的逻辑更难以理解。让我们来看一个例子：尝试对比列表 5.7 和 5.8。哪段代码更容易理解？

#### 列表 5.7 实现简单逻辑的方法

```java
public List<Integer> extractDigits(String input) {
    List<Integer> list = new ArrayList<>();
    for (int i = 0; i < input.length(); i++) {
        if (input.charAt(i) >= '0' && input.charAt(i) <= '9') {
            list.add(Integer.parseInt(String.valueOf(input.charAt(i))));
        }
    }
    return list;
}
```

#### 列表 5.8 充斥日志消息的方法
