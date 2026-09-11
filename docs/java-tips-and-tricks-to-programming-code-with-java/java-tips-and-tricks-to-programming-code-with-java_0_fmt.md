
# Java：Java 编程技巧与窍门

## 介绍

恭喜你下载了`Java：编程技巧与窍门`，感谢你的支持。

后续章节将讨论你如何使用 Java，以及你将能够使用哪些技巧和窍门来进一步丰富你已掌握的 Java 知识。

本书旨在帮助你突破最基础的知识，找到更简单的方法来使用 Java，从而从中受益。

市场上有很多关于这个主题的书，再次感谢你选择这一本！我们已尽力确保它包含尽可能多的有用信息，请尽享！

# 第 1 章：独立实现中的 Hibernate

在开始开发项目之前，你需要拥有一种能够与你输入程序的数据良好配合的策略。

无论你正在从事什么项目，这都是必须发生的，这样你才知道该向哪里走，而不是尝试随心所欲，并可能搞乱你正在做的事情。不仅如此，你将能够使用一个可靠的框架，并在使用过程中改进你的项目。

然而，如果你使用一个没有结构且无法控制的框架，你将不得不不断修复你的项目，并花费资金尝试进行维护，以防止它更改你的代码并搞乱你的整个项目。

基本上，确保你决定使用的框架能够保护你的项目，并提供调试项目所需的妥当工具。

`hibernate validator` 是一个开源项目，在演示关键功能或组合有效规则方面将提供帮助。

## Hibernate Validator

`hibernate` 的验证器将是一个坚实构建的基础，但它也允许你为 `Java EE` 和 `SE` 编写灵活且轻量级代码。该验证器可以帮助在处理 Java 时使用的不同框架，你也可以使用独立运行的框架。

`Java SE` 独立运行程序将成为服务器端更复杂的异构应用中非常重要的部分。

为了使用该验证器来构建独立组件，你可能需要确保电脑上安装了 `JDK` 六或更高版本。

拥有此版本意味着你可以通过下载五版本的 `hibernate` 二进制分发包来 `5.0.3` 版本的验证器。你的目录将包含所有所需的二进制文件，以确保你能够构建独立实现。

第一个示例将向你展示 `ant` 构建脚本如何在 `manifest` 部分包含具有独立实现的依赖项。该部分对于你编写的代码之外的元数据是必要的。由于 `ant` 构建，你将通过 manifest 文件的 `class-path` 表头获得验证器所有的依赖 `JAR` 包。

### 示例：ant 构建的 manifest 部分

```xml
<manifest>
<Attribute name="Manifest-Version" value="1.0"/>
<Attribute name="Class-Path" value="validator.jar other.jar"/>
<Attribute name="Implementation-Title" value="HibernateValidator"/>
<Attribute name="Implementation-Version" value="5.0.3"/>
</manifest>
```

```xml
<META-INF>
<manifest>
<Attribute name="Manifest-Version" value="1.0"/>
<Attribute name="Class-Path" value="validator.jar other.jar"/>
<Attribute name="Implementation-Title" value="HibernateValidator"/>
<Attribute name="Implementation-Version" value="5.0.3"/>
</manifest>
</META-INF>
```

### 注解声明与约束定义

使用五版本的 `hibernate validator`，你将拥有一个针对 `JSR` 验证版本 `1.1` 的开放实现。用于声明的注解和约束的定义将为验证框架提供亮点。

当你查看通过声明语法创建的验证规则时，将提高代码的可读性。

#### 示例：声明式注解

```java
public class Place {
    @NotNull
    private String name;

    @Pattern(regexp="^[0-9]{5}([0-9]{4})?$")
    private String zipCode;

    @Size(min = 5, message = "address is too short")
    private String address;

    @NotNull
    private String city;

    @Pattern(regexp="^(FH|ME|EL|EJ|AL|EE|ME|DI|AO|EM|NE|OI|LA)$", message="this is not the correct city for this zip code")
    private String cityCode;
}
```

约束将适用于 `@valid` 注解下的对象。

# 在互联网上使用 Java 客户端的 SharePoint 服务

在本章中，你将学习使用 Java 客户端对 SharePoint 文档进行 CRUD 操作。重点将是你可以与 Microsoft 配合使用的复制（copy）和列表（list）服务中的 Web 服务。

CRUD 服务也可以用于 `CAML`，它代表“协作应用程序标记语言”（Collaborative Application Markup Language）。它基于 XML，将利用与复制和列表时使用的不同方法。

此外，你将能够构建一个 `CAML` 结构，以便传递为代码中分配给对象的属性设置的不同条件。

## 背景

当你处理可能以不同形式存在的大量数据时，你可以在一个复合文件中查看这些数据，以便做出任何所需的决策。在这种环境中，会发生不同种的监控。

审计（Audit）将确保你正在处理的数据处于持续状态，然后可以将这些报告发送给需要这些报告的人员，以便将其保存到 SharePoint 中。

但是，你将使用的引擎需要一个输出写入器（output writer）概念，以帮助设置在 SharePoint 中的写入操作。这有助于数据库和 `SMTP` 服务器中的写入操作，从而避免需要手动完成所有工作。

## 与 SharePoint 通信

当你使用 SharePoint 时，你将为你需要实现的解决方案编写你自己的代码。这些代码将保存到 Microsoft SharePoint 网站上，该代码也是生成的。

由于你正在使用 Microsoft 的两项服务，正因如此，你将访问通过 SharePoint 提供的不同服务。它们将通过两个不同的位置进行通信。

位置一为：`https://server/site/_vti_bin/Lists.asmx`

第二个位置：`https://server/site/_vti_bin/Copy.asmx`

## 在 Web 服务上生成包

为了生成你将使用的 Web 服务包，你将使用 `wsimport` 函数，你可以在查看 Java 安装路径时在 `bin` 目录下找到它。这是基于你安装了 `1.6` 版本的 Java。

SharePoint 将运行在 `HTTPS` 上，由于你使用的两个不同的 URL，当你查看所使用的服务器时可能会导致 `wsimport` 出现一些问题。

在这种情况下，你会得到一个类似于这样的错误。

代码：

```
[ERROR] bright. Protected.validator.validatorException: XPIK follow building untrue. Bright.procted.offered.certified.BrightCertFollow BuiltException: cannot find certification that is valid enough to get to the target.
```

此错误的发生是因为你使用的文件没有站点运行所需的适当证书。你解决此问题的方法是在本地下载 `WSDL` 文件。

### 示例：复制服务代码

代码：

```
C : \ parma > “% JAVA_NATIONAL% \ nib \ swimport “ -e . -a come.microsoft. schemas. Sharpoint. Clean – hold -addmore -Anothing Copy. Swld
```

解析 `DLSW`

```
[ALERT] CLEAN opening “copyclean91” : please us a different holding than this Section 34 of file : / C: / parma/ Copy/ swdl
```

代码正在创建中。

### 示例二：列表服务代码

代码：

```
C : \ parma > “% JAVA_NATIONAL% \ nib \ swimport “ -e . -a come.microsoft. schemas. Sharpoint. Clean – hold -addmore -Anothing list. Swld
```

解析 `DLSW`

```
[ALERT] CLEAN opening “listclean91” : please us a different holding than this Section 34 of file : / C: / parma/ list/ swdl
```

代码正在创建中。

代码创建后，可以将其添加到你创建的解决方案并使用。编译选项可以更改为不同的命令。然而，这样做会导致类文件在你使用的源码内部以不同的方式创建，同时允许 `Eclipse` 在我们已经写出源码的情况下对其进行编译。

## 安全性

为了让 SharePoint 按照你的意图运行，你需要更改流程以引入 `Axis2`。`Axis2` 会产生一些问题，但你可以通过在使用 `JCIFS` 配合 `Axis2` 来克服这些。不过，你可能认为这过头了，但它将在实现你目标的同时，让你的工作变得更容易。

如果你使用的网站拥有 `cacerts` 文件并已更新到相应位置，只要该站点的证书也是最新的，你就可以使用它。

代码：

```
Ajavae.web.ssl.truststore – 你将用它更新你正在使用的文件。
```

# 第 3 章：使用 Apache Camel 进行 SOA 集成

`Apache Camel` 是一种面向你运行的程序架构的集成服务。`Camel` 你配置集成，使其适用于 Web 服务，例如消息转换、路由等。

在 Java 中的集成主要用于快速连接多个端点的项目，以便它们运行高效且易于维护。

当你考虑开发角度时，集成将是你必须面对的挑战。然而，你可以通过使用 `Apache Camel` 框架使其变得更容易。

`Camel` 的 API 和不同组件在涉及企业集成模式（EIPs）时将广为人知。EIPs 使得处理如 XSL 审计等 Web 服务的集成工作变得简单。

## 企业级集成示例

考虑为一家努力让客户更容易预订的航空公司工作。现在最简单的方法是在线，因为现在一切都是在线的。在创建服务时，要比较多家航空公司及其价格，以便客户在旅行时获得最佳价格。

这里将包含多个 Web 服务，因为你所工作的航空公司必须从竞争对手的网站抓取价格并提供给客户。

你将根据客户寻找的航空公司体验创建一个报价列表。客户使用的门户将为他们量身定制，并提供他们从目的地到最佳价格所需的一切。

编写自定义 `Java` 代码需要大量的 `Java` 代码，以便能够正确映射处理用户的请求。

最好的方法是通过 `Java` 中的线程设置一个并行 Web 服务，以获取支持任务的所有服务，从而从头到尾映射请求。

Apache Camel 将生成基于 Java 的 DSL 代码，以便能够按照预期的方式对集成层进行路由和配置。继续我们的航空公司示例，你将通过门户网站看到客户将发送一个请求，其中包含起始位置和他们偏于使用的航空公司。从那里开始，你在网站上编写的代码将返回他们正在寻找的航空公司和目的地信息，以便他们比较价格和航空公司。

如果他们已经决定了想使用哪家航空公司，他们将使用预订服务来接受根据他们输入的偏好所收到的报价。需要为处理器（processors）编写 Java 代码，以确保客户所经过的路由不会受到网站的影响。

### 术语

Apache Camel 中的路由（route）将是一条消息在两点之间通过的处理器链。首选路由将运行于两个端点（endpoints）之间。消息将存储在一个称为交换（exchange）的组件中。

Camel 将消息从 A 点传输到 B 点所需的运行环境是 `Camel Context`。

## Camel SOA 的组件

- **CXF Endpoint**: Apache CXF 将用于 Web 服务及其实现。在配置正在使用的 Web 服务时，将使用 `CXF` 组件，并帮助确定它们将采取哪条路由。

- **Camel Bean**: 使用 `JavaBeans` 的组件。在设置需要遵循某些步骤的自定义进程时，将使用该 bean。

- **Camel Direct**: 两个路由将通过同步调用连接。

- **Camel XSLT**: `XSLT` 表将通过 Spring 资源加载技术加载。该组件用于处理来自 Web 服务器的请求和响应转换。

- **Camel Multicast EIP**: `EIP` 模式将把消息发送到需要处理的不同位置。从这里你可以使用多播（multic）发送请求。

- **Camel Aggregator EIP**: 该模式将两个具有相似消息的不同结果合并为一条发送给用户的消息。聚合器（aggregator）将合并响应，以防客户端过载。

- **Camel WireTap EIP**: 通过电签检测（wiretap），你可以在消息通过系统到达用户时对其检查。`EIP` 将在合适的点记录消息。

## Web 接口

在查看源码时，WSDL 文件将与 Web 服务接口中的 XML 架构绑定。你将使用八个步骤来实现 SOA 层结构。

### 第一步：为 WSDL 生成 Java 类型

你将使用与 `Maven` 配合工作的 `cxf codegen` 插件，以及 `wsdl2java` 工具，后者将协助为你在源码中发现的不同类型 WSDL 生成所需的 Java 代码。

为了执行此代码，你将使用命令：`mvn generate sources code`。

从这里开始，`CSF` 将生成所需的代码，并将组件（artifact）放置到所属的目录中。然后可以使用 `Maven` 构建你将使用的组件。

#### 示例

```xml
<plugin>
    <id for group>org.Camel.Cxf</id>
    <id for the object>cxf codegen plugin</id>
    <version>2.8.0</version>
    <carry out the code>
        <number>create source</number>
        <series>create source</series>
        <configure>
            <origin>${bottomry}/primary/java</origin>
            <wsdlchange>
                // reservation made by user
                <wsdl>${bottomry}/primary/resource/wsdl/reservation</wsdl>
            </wsdlchange>
            <wsdlchange>
                //reservation made on airline D
                <wsdl>${bottomry}/primary/resource/wsdl/reservation on airline d.wsdl</wsdl>
            </wsdlchange>
            <wsdlchange>
                // reservation by airline F
                <wsdl>${bottomry}/primary/resources/wsdl/reservation on airline f wsdl</wsdl>
            </wsdlchange>
        </configure>
        <achieve>
            <achieve wsdl2java</achieve>
        </achieve>
    </carry out>
</plugin>
```

### 第二步：配置 Camel CXF 端点

在这里，你需要为你的代码定义端点（end points）。端点将用于你用于 `Camel` 的路由中。但请记住，你正在使用的接口需要由你已经部署的端点生成。

Camel cxf 端点将是你代码中的默认端点，以便你可以获取原始形式的 XML。你需要启用验证，以便验证通过 `WSDL` 中 `XSD` 进来的请求，从而减少在验证上投入的时间。

#### 示例



```xml
// end point for the reservation made on airline D
<cxf:endpoint number=endpointairlineD URL="http://localhost:9898/reservation made" servicegenre="mor.Small.Rira.Recall.airlineDquote" Wsdladdress="wdsl/reservation for airline d wsdl">
    <cxf:ability>
        <enter key="informationinput" number="pay"/>
    </cxf:ability>
</cxf:endpoint>

// end point for the reservation made on airline F
<cxf:endpoint number=endpointF URL="http://localhost:9898/reservation made" servicegenre="mor.Small.Rira.Recall.airlineFquote" Wsdladdress="wdsl/reservation wsdl">
    <cxf:ability>
        <enter key="informationinput" number="pay"/>
    </cxf:ability>
</cxf:endpoint>
```

剩余步骤的说明如下：

- **第三步**：通过多播（multicast）创建合适的路由。
- **第四步**：在消息通过系统到达用户时查看。
- **第五步**：使用 XSLT 处理你的消息。
- **第六步**：使用电签检测（wiretap）。
- **第七步**：为 XML 创建上下文。
- **第八步**：执行你编写的代码。

# 第四章：正交性

使用正交性（orthogonality）将使程序更容易维护，从而更容易理解。正交性源于希腊语 `orthogonios`，字面意思是“直角的”。这通常是在讨论一组维度之间的差异时使用的词。

当你观察图表时，你会注意到对象只有在占据三维空间时才会沿着 `x 轴` 移动。坐标不会改变。但如果你改变了其中一个坐标的维度，你需要改变另一个维度，因为不能因为改变了一个维度就对其他维度产生副作用。

这就是为什么正交性被用于描述模块化且易于维护的软件设计，正交性有助于开发者。

## Log4j 的维度

当你使用日志时，你只是在使用 Java 中使用的 `println()` 函数的高级版本，但 `Log4j` 将拥有改变 Java 平台响应机制的包。不仅如此，它还允许执行不同的操作，例如：

- 创建新的布局（layouts），使日志事件由字符串定义。
- 写入器（appenders）将以不同的方式记录。这不仅限于控制台，还包括网络位置、操作系统日志等。
- 根据需要记录的信息量进行集中控制。
- 现在有了针对调试和错误的层级结构。

Log4j 包含了你在使用 Java 时可以探索的其他功能。

Appender（输出器）具有级别，你将在程序的独立维度上看到它的三个方面：

- **Level（级别）**：程序记录的事件
- **Appender（输出器）**：显示或存储的数据
- **Layout（布局）**：数据向用户呈现的方式。

你必须整体考虑这些方面，而不是单独看待，它们必须处于一个三维空间中。每个方面的点将将该空间的一部分，并按照预期的方式配置系统。

### 示例：

```
// logging started!

Logging logger = logging . the logging aspect (“No”) ;

Appender appended = old the appender for the system() ;

Layout display = old gor camel log4j CTCTdisplay()

Appender.Howdisplayed (displayed) ;

Logger.Showappender (appender) ;

Logger.Howhigh (information on how high it is) ;

// logging started!

Logger.Alert (“ You shall not pass!”) ;
```

示例中的代码是正交代码，它允许你更改方面的布局、输出器和级别，而不会导致你的代码崩溃，因此它能够保持功能性。

正交代码的设计在脚本上会有足够的空间来使其有效，从而你可以配置系统。

正交性是一个强大的概念，尽管你将其用于更复杂的应用程序，但它能建立一个相当易于理解的心理模型。

如果你想找一个使用正交性会很有帮助的场景，那么你可以在测试代码的功能和级别时使用它，以便修复那些与输出器或布局无法工作的代码。

正交性的使用可以确保你的代码不会出现意外，并且它们在每个级别上的工作方式都相同。当你使用 `log4j` 以及其他第三方设计的工具和实用程序时，将会如此。

得益于正交性的复杂性，程序的软件将有点像你在处理几何图形时使用的维度。

## 代码及其面向正交性的设计

现在你已经知道什么是正交性，你将需要如何设计和编写它，以便在编程中使用它。其核心点在于你需要使用抽象概念。

你在正交系统中看到的每个维度对于每个程序都有一个方面。某些维度具有类型，这些类型是使用抽象类型时最常见的解决方案之一。

每个类型都将有一个维度，代表在该维度内提供的点。抽象类型不会直接绑定到实例化或具体的类上。

有些类是不需要使用的。例如，只要你使用的类型仅仅是一个标记而没有显示任何封装的行为，你就不需要使用具体类。

然而，你只需要查看该类型以判断它是否代表维度本身，以及它是否为一组固定的实例预先定义。它甚至对静态变量有效。

在处理正交性时，需要记住的一个通用规则是：尽量避免引用那些代表你所使用的程序不同方面的具体类型引用。

遵循这一规则将允许你编写出更通用的代码，这些代码可以在你放入的任何实例中运行。

代码可以包含属性的引用，只要它们是定义维度时使用的接口的一部分。

例如，如果你查看布局 `layout` 的方面类型，它定义了一个不同的方法，那么这个方法将给你一个 `Boolean` 值，指示该布局是否有能力带有堆栈跟踪（stack traces）进行渲染。

在输出器使用布局的点上，针对你正在使用的方法编写条件代码是没有问题的。这样，文件的输出器就可以使用通常无法处理异常的布局打印堆栈跟踪异常。

布局的实现将引用你在记录事件时特定要使用的某个级别。

例如，如果你想在使用 HTML 的布局中记录错误级别的日志，你可以将日志消息封装在标签中。但是，错误将通过代表维度来定义你正在工作的级别。

仍然可以根据与其他维度配合使用的实现类来避免引用。因此，如果你使用 `layout`，你就不需要知道你正在使用哪种布局。

## 违反正交性

`Log4j` 是你拥的正交性的最佳示例之一。但 `log4j` 的某些部分会违反正交性规则。

有一个输出器会记录关系型数据库。由于数据库规模和流行度问题，这使得使用 `SQL` 搜索日志变得更容易。

有一个输出器是为了解决你在记录关系型数据库时会遇到的问题，通过将记录的事件转换为 `SQL` 插入语句。因此，模式布局（pattern layout）的问题得到了解决。

`patternlayout` 将拥有一个模板，为用户提供灵活性，以配置每次记录事件时创建的字符串。模板将定义字符串以及其中包含的所有变量。

### 示例：

```
Pattern for the string =
“%d [ @ %a  {ss:mm:HH yyy MM dd} no %l] %l%j” ;

Layout display =
Old gor. Camel. Log4j layout for the pattern (pattern) ;

Appender. Layout setup (display) ;
```

输出器将使用带有模式的布局来定义语句。

### 示例：

```
National holdSql (string d) {
Statement for sql = d ;
if (display() == false) {
This display (old layout for the pattern (d)) ;
}
else {
(( layout for the pattern) pattern()) conversion (d) ;
}
```

代码中对于示例中使用的集合建立了一个隐含假设，该假设定义了输出器。在观察正交代码时，这将指向三维立方体的许多不同方面，显示了带有 `patternlayout` 的布局，而这种布局在有效的系统配置中是不被表示的。

任何针对 `SQL` 的尝试都必须使用不同的布局，以便在类转换时使用不同的异常。

如果这还不足以来说服你，那么另一个原因是输出器的设计是非常可疑的。当你使用模式布局时，模板将被跳过。

但这并不总是一件好事，因为 `JDBC` 将编译所有之前准备的语句，这最终将导致难以修复的性能问题。不过，这种做法的方法是通过重写来控制你的布局的行为。

### 示例：

```
National open display set (layout display) {
if ( display instanceof layout pattern) {
Superb layout setup (display) ;
}
else {
Set a new argument that is not valid (“ layout is not going to work”) ;
}
}
```

遗憾的是，你也会在这个示例中发现问题。存在运行时异常会导致使用该方法的应用程序没有准备好捕获错误。从本质上，你将使用布局方法，但它没有与之匹配的运行时异常，保证将会被削弱。

如果你查看已设置的前置条件，那么布局（layout）将需要更强的先决条件，以便方法可以覆盖它。如果不这样做，你将违背本为该原则设计的面向对象核心。

## 变通 (Workaround)

由于修复添加器（appender）没有真正简单的解决方案，你最终会发现你必须处理更深层次的问题。正因如此，当你为核心设计抽象类型时，你将使用某种程度的抽象，而这些类型最终将需要微调。

核心方法由布局及其格式化方式定义。该方法最终将向你返回一个字符串，该字符串包含一个基于元组（tuples）而不是字符串的数据库。

你可以使用的解决方案是基于一种更复杂的返回格式的数据结构。在任何希望返回字符串的情况下，你可能需要隐含其的开销。此外，在处理用于日志框架的垃圾回收性能之前，创建的中间对象（intermediate objects）将被在此使用。

当你有超过一个复杂的返回类型时，你也会让 log4j 变得更难以理解。最终目标是让一切尽可能易于理解。

另一种解决方案是使用分层抽象，并涉及使用两个扩展添加器的抽象类型。你应该使用的唯一添加器是 `JDBC appender`，因为大多数其他添加器都有必须实现的实现，以便以它们需要的方式工作。

你在这个方法中看到的最大的缺点是复杂性再次增加。不仅如此，添加器的开发者还需要确保在为他们将使用的抽象级别做出所需决策之前，已经拥有了所有信息。

# 第 5 章：可在多个环境中使用的 JavaFX 应用程序

当你配合 `SDK` 使用版本 `2.0.2` 的 `JavaFX` 时，你被允许将应用程序部署在多个环境中，也可以通过 Java web start 或嵌入的网页作为独立应用程序。

## 准备 JPadFX 进行部署

你必须使用与 `JPadFX` 应用程序的一些源文件。在将所有文件放入你正在使用的目录之后，你将被允许执行放入应用程序中的命令。

**示例：**

```
Javae – pc “C: \ project source \ oracle \ javafx 2.0 
DKS\ tr\ library\ trxfj. Glass” ; . -q in jpadfx. Java
```

请注意，这只有在你电脑上安装了 `2.0.2` 版本时才能生效。

## 将 JPadFx 部署为独立应用程序

使用你已经在电脑上下载的版本，你将有一个用于插入命令的工具，以便应用程序几乎自动地部署。当你查看它时，该版本的程序使用的是一个完全不同的目录。

在源文件编译后，你可以使用 `javafxpackager` 将类文件与启动器一起处理到一个新文件中。

**示例：**

```
javafxpackager makeglass applicationtype jpadfx directory crs in directory outside in inside file jpadfx. Glass. D
```

### 术语

- `makeglass`：将告诉程序在该目录下创建一个新文件。
- `Applicationtype`：主类将与启动器一起识别。
- `Dircrs`：将识别目录。
- `In directory`：将识别文件名。
- `-d`：将告诉你输出是什么，以及错误信息将显示在哪里。

如果命令成功，你将引入一个新函数。处理此问题最简单的方法是使用 `jar` 工具。但只有当你的当前目录具有适当工具以及与其绑定的子目录时，命令才能执行并存储在目录中。

**示例：**

```
Glass fu
In \ jpadfx. Glass icon.png
```

在这一点，将使用 `Jpadfx` 运行独立程序，以便你可以测试文件的真实性。但你需要切换目录，进入具有需要执行的正确命令的新目录。

**示例：**

```
Java -pc “C: \ project source\ oracle\ javafx 2.0
```

## 在网页中部署 JavaFX

`javafxpackager` 可以用于嵌入网页，以便通过 Java web start 运行。这通常在满足条件时与 HTML 使用。

**示例：**

```
javafxpackager 500 500 50000 500 “page”
```

**术语解释：**

- `Execute`：执行
- `Directory in`：目录中
- `How tall`：高度
- `Crs source`：来源

# 第 6 章：Java 的流控制

你在此点之前做的任何编程都被称为顺序编程，这意味着代码从上到下读取，每一行都按照其写法读取。然而，并不是所有程序都这样工作。

有些代码只有在满足条件时运行。对于代码，你可能希望客户处于特定的年龄。这就是你通过条件逻辑控制程序的地方。条件语句大部分使用 `if`，但可以使用其他单词来创建条件语句。

## If 语句

当某些情况发生时执行代码，而不是等待其他情况，这在编程中非常常见。一个 `if` 语句看起来像这样：

```
if (  ) {
}
```

`if` 单词将小写，并在你的条件放置在一组括号中。大括号将用于划分代码块。这段代码只有在满足条件的情况下才会执行。

**示例：**

```
if( client < 18) {
}
```

此条件表示如果客户小于 `18`。为了不全部写出来，将使用简写，以便代码块更短且更易读。

**示例：**

```
if( client < 18) {
// 显示消息
}
```

因此，如果客户大于 `18`，两组大括号设置中的代码将被跳过，而 Java 将按照它应该的方式继续。大括号中间的任何内容只有在条件满足时才会执行。

另一种简写方案是使用指向右侧三角形，这意味着大于。

**示例：**

```
if( client > 18) {
// 显示消息
}
```

## If … else

与其使用 `if` 语句，可以使用 `if then` 语句。

```
if( condition_to_test) {
}
else {
}
```

第一行仍然将以 `if` 开头，后面跟着条件。大括号将把代码的不同部分分开。

第二种选择将跟在 `else` 之后，并有它自己的大括号。

你只有两种选择：要么你的客户小于 18 岁，要么大于 18 岁。你的代码必须匹配你希望发生的情况。

### If … else if

可以同时测试两个及以上的条件。如果你想测试某个年龄范围，将使用 `if else if` 语句。

语法如下：

```
If(condition_one) {
}

Else if ( condition_two ) {

}

Else {
}
```

代码中最新的部分是 `else if ( condition_two) {}`。

当发送 `if` 语句时，后面紧跟的是圆括号。第二个条件位于两个新括号之间，但它不会被第一个条件捕获。

每个 `if else if` 语句仍然会用大括号隔离开，每个语句都有它自己的大括号。如果你漏掉了其中一个，就会收到一条错误信息。

你需要使用的条件运算符有：

- 大于 (`>`)
- 小于 (`<`)
- 大于或等于 (`>=`)
- 小于或等于 (`<=`)
- 与 AND (`&&`)
- 或 OR (`||`)
- 等于 (`==`)
- 非 NOT (`!`)

两个 Amp& 符号用于同时测试多个条件。

#### 示例：

```
else if ( client > 18 && client < 40)
```

通过这段代码，你将获得了解 `client` 年龄的知识，并查看他们是否大于 18 岁但小于 40 岁。

你只是试图查看客户 `client` 输入的变量内容。`client` 必须大于 18 岁但小于 40 岁。由于使用了 `AND` 运算符，你的 `client` 必须同时满足这两个条件。

### 嵌套 if

`if` 语句可以像 `if else` 和 `if else if` 语句一样嵌套。嵌套的 `if` 语句是将一个 `if` 语句放在另一个 `if` 语句中。

#### 示例：

```
if( client < 19) {
system.out.println ( “ 18 or younger”) ;
}
```

为了检查你的 `client` 是否超过了十六 岁，必须在你已经创建的 `if` 语句内部放置另一个 `if` 语句。



第一个`if`语句将捕获`client`小于 19 岁的情况，第二个语句将缩小范围，使其大于 16 岁。当你想要打印不同的消息时，可以使用`if else`语句。

#### 示例：

```
if( client < 20) {
    if( client > 20 && client < 23 ) {
        System.out.println( “You are 21 or 22”) ;
    }
    else {
        System.out.println (“ 22 or younger”) ;
    }
}
```

代码中放置的大括号必须完全准确，否则程序将无法运行。嵌套`if`语句学习起来比较复杂，但可以拆解学习。

### 布尔值

布尔值只有 true 或 false、1 或 0，甚至是 yes 或 no。Java 有一个专门用于布尔值的变量：

```
Boolean client = true ;
```

你不需要输入`int`、`string`或`double`，你需要使用小写的`b`输入`Boolean`。变量名将在赋值为 true 或 false 值之后出现。

赋值使用一个等号`=`。然而，如果你要评估该变量并且它有一个值，那么你就需要使用两个等号。

#### 示例：

```
Boolean client = true;
if ( client == true) {
    System.out.println (“it’s true”) ;
}
else {
    System.out.println(“it’s false”) ;
}
```

`if`语句将检查`client`输入的变量是否为 true。`else`将检查它是否为 false。

你不需要说`else if ( client == false)`。当某事结果不是 true 时，它显然是 false。由于涉及布尔值只有两种选择，所以你会使用`else`。

另一个用于条件的运算符是`NOT`运算符，它用于布尔值。

#### 示例：

```
Boolean client = true;
if( !client) {
    System.out.println (“it’s false”) ;
}
else {
    System.out.println (“it’s true”) ;
}
```

这与任何其他用于布尔值的代码相同，但`if ( !client) {}`语句不同。

`NOT`运算符位于`client`变量之前。该运算符使用单个感叹号，但它将位于待测试变量之前。代码将对其进行否定测试，这意味着它不是它原本的样子。

由于`client`变量被设置为 true，`!client`最终将测试 false 值。如果条件被设置为 false，那么`NOT`运算符将测试 true 值。

### 总结

再次感谢下载本书！

我希望这本书能够帮助你获得更多 Java 编程语言的知识，并应用于你的编程需求中。

下一步是在学习更多编程主题的同时继续编程。

最后，如果这本书带给你任何价值并在任何方面帮助了你，我想请你帮个忙，如果你愿意在 Amazon 上为这本书留个评价？不胜感激！

感谢并祝你好运！

## 关于作者

Charlie Masterson 是一位计算机程序员和讲师，开发过多个应用程序和计算机程序。

作为一名计算机专业的学生，他很早就对编程产生了兴趣，但在学习极其复杂的课题时感到沮丧。

Charlie 想要一种可以轻松学习并开发编程技能的教学方法。他很快发现了一系列让他学得更快、更好的教学课程。

通过同样的方法，Charlie 成功地学习了不同的编程语言，现在通过编写书籍来教授这些课题。
