
# Jackson：Java 数据处理工具

## 关于教程

Jackson 是一个非常流行且高效的基于 Java 的库，用于将 Java 对象序列化为 JSON 或反之亦然。

本教程采用简单直观的方法来解释 Jackson 库 API 的基本功能以及如何在实践中使用这些功能。

## 目标读者

本教程对于大多数 Java 开发者都很有用，无论他们是初学者还是专家。

## Go条件

Jackson 是一个基于 Java 的库，在学习本教程之前，你必须对 Java 编程语言有深入的了解。

![](img/abf38b9a96498be10686313ae639d832_1_0.png)

![](img/abf38b9a96498be10686313ae639d832_2_0.png)

## 1. 概述

Jackson 是一个简单的基于 Java 的库，用于将 Java 对象序列化为 JSON 或反之亦然。

### Jackson 的特性

- **易用** – Jackson API 提供了一个高级抽象，以简化常用场景。
- **无需创建映射** – Jackson API 为大多数要序列化的对象提供了默认映射。
- **性能** – Jackson 运行快速，消耗内存空间少，适用于大型对象图或系统。
- **清晰的 JSON** – Jackson 创建的 JSON 结果清晰且紧凑。
- **无依赖** – Jackson 库 JDK 之外不需要其他库。
- **开源** – Jackson 库是开源且免费使用的。

### 处理 JSON

Jackson 提供了三种不同的方式来处理 JSON：

- **流式 API** – 它作为离散事件读取和写入 JSON 内容。`JsonParser` 读取数据，它是三种方法中最强大的。它的开销最小，是执行读写操作最快的方法。它类似于 XML 的 Stax 解析器。
- **树模型** – 它为 JSON 文档准备内存中的树表示。`ObjectMapper` 构建 `JsonNode` 节点组成的树。它是最灵活的方法。它类似于 XML 的 DOM 解析器。

![](img/abf38b9a96498be10686313ae639d832_5_0.png)

- **数据绑定** – 它使用属性访问器或注解在 JSON 与简单的旧 Java 对象（POJO）之间进行转换。`ObjectMapper` 负责这两种数据绑定的 JSON 读取/写入。数据绑定类似于用于 XML 的 JAXB 解析器。数据绑定分为两种类型：
  - **简单数据绑定** – 它在 JSON 与 Java Maps、Lists、Strings、Numbers、Booleans 和 `null` 对象之间进行转换。
  - **全量数据绑定** – 它在 JSON 与任何 Java 类型之间进行转换。

## 2. 环境设置

本章节描述了如何在你的系统上设置 Jackson 环境。

### 在线尝试选项

你不需要设置自己的环境就可以开始学习 Jackson。我们已经在网上设置了一个在线 Java 编程环境，这样你就可以在线上编译并执行所有可用的示例。可以随时修改任何示例并使用不同的选项检查结果。

使用我们网站上示例代码右上角的 `Try it` 选项尝试以下代码示例：

```
public class MyFirstJavaProgram {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

对于本教程给出的大多数示例，你都会发现一个 `Try it` 选项，帮助你通过实践快速学习。

### 本地环境设置

如果你仍然想为 Java 编程语言设置环境，本节将指导你如何在你的机器上下载并设置 Java。请按照给定的步骤设置环境。

可以通过 [下载 Java](Download Java) 链接免费获取 Java SE。你可以根据你的操作系统下载相应的版本。

按照说明下载 Java 并运行 `.exe` 在你的机器上安装 Java。一旦安装了 Java，你就需要设置环境变量以指向正确的安装目录。

### 为 Windows 2000/XP 设置路径

假设你已将 Java 安装在 `c:\Program Files\java\jdk` 目录下，

- 右键点击“我的电脑”。
- 选择“属性”。

![](img/abf38b9a96498be10686313ae639d832_7_0.png)

- 点击“高级”选项卡下的“环境变量”按钮。
- 修改“Path”变量，使其也包含指向 Java 可执行文件的路径。例如，如果路径当前设置为 `C:\WINDOWS\SYSTEM32`，则将你的路径改为 `C:\WINDOWS\SYSTEM32;C:\Program Files\java\jdk\bin`

### 为 Windows 95/98/ME 设置路径

假设你已将 Java 安装在 `c:\Program Files\java\jdk` 目录下，

- 编辑 `C:\autoexec.bat` 文件
- 在末尾添加以下行：
- `'SET PATH=%PATH%;C:\Program Files\java\jdk\bin'`

### 为 Linux, UNIX, Solaris 和 FreeBSD 设置路径

环境变量 `PATH` 应设置为指向 Java 二进制文件安装的位置。如果你在此操作上遇到困难，请参考你的 shell 文档。

例如，如果你使用 `bash` 作为你的 shell，你需要在 `.bashrc` 的末尾添加以下行：`export PATH=/path/to/java:$PATH`

### 流行的 Java 编辑器

编写 Java 程序，你需要一个文本编辑器。市场上有很多高级的 IDE 可以编写 Java 程序，但目前你可以考虑以下之一：

- **Notepad（记事本）**：在 Windows 平台上，你可以使用任何简单的文本编辑器，如记事本（本教程推荐）或 TextPad。
- **Netbeans**：这是一个开源 Java IDE。可以从 http://www.netbeans.org/index.html 下载。
- **Eclipse**：它也是一个由 Eclipse 开源社区开发的 Java IDE。可以从 http://www.eclipse.org/ 下载。

### 下载 Jackson 存档

从 `jackson-all-1.9.0.jar.zip` 下载最新版本的 Jackson jar 文件。在本教程中，`jackson-1.9.0.jar` 被下载并复制到 `C:\jackson` 文件夹。

![](img/abf38b9a96498be10686313ae639d832_8_0.png)

| 操作系统 | 存档名称 |
| :--- | :--- |
| Windows | `jackson-all-1.9.0.jar` |
| Linux | `jackson-all-1.9.0.jar` |
| Mac | `jackson-all-1.9.0.jar` |

### 设置 Jackson 环境

设置 `jackson_HOME` 环境变量指向指向机器上存储 Jackson jar 的基础目录。根据你所工作的平台，过程会有所不同，如下表所示：

| 操作系统 | 输出 |
| :--- | :--- |
| Windows | 设置环境变量 `jackson_HOME=C:\jackson` |
| Linux | `export jackson_HOME=/usr/local/jackson` |
| Mac | `export jackson_HOME=/Library/jackson` |

### 设置 CLSPATH 变量

设置 `CLSPATH` 变量指向 Jackson jar 所在的位置。

| 操作系统 | 输出 |
| :--- | :--- |
| Windows | 设置环境变量 `CLSPATH=C:\jackson` |
| Linux | `export CLSPATH=/usr/local/jackson` |
| Mac | `export CLSPATH=/Library/jackson` |

## 3. 应用

在深入研究 Jackson 之前，让我们看看应用程序。

### Jackson – 示例

在本示例中，我们将使用 Jackson 来序列化 JSON 并反序列化。

```java
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.core.ParseException;
import com.fasterxml.jackson.databind.MappingException;
import com.fasterxml.jackson.databind.SerializationFeature;
import com.fasterxml.jackson.core.Json;
import java.io.IOException;

public class JacksonTester {
    public static void main(String[] args) {
        ObjectMapper mapper = new ObjectMapper();
        String jsonString = "{\"name\":\"Mahesh\",\"age\":21}";

        try {
            Student student = mapper.readValue(jsonString, Student.class);
            System.out.println(student);

            mapper.enable(SerializationFeature.INDENT_OUTPUT);
            jsonString = mapper.writeValueAsString(student);
            System.out.println(jsonString);
        } catch (ParseException e) {
            e.printStackTrace();
        } catch (MappingException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

class Student {
    private String name;
    private int age;

    public Student() {}

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    @Override
    public String toString() {
        return "Student [ name: " + name + ", age: " + age + " ]";
    }
}
```

### 验证结果

使用 `javac` 编译类：

```
C:\path> javac JacksonTester.java
```

运行 `JacksonTester` 查看结果：

```
C:\path> java JacksonTester
```

```text
Student [ name: Mahesh, age: 21 ]
{
  "name" : "Mahesh",
  "age" : 21
}
```

## ObjectMapper – 构造函数

| 序号 | 构造函数及描述 |
|---|---|
| 1 | **ObjectMapper()**<br>默认构造函数，将使用默认的 `JsonFactory` 构建必要的 `JsonParsers` 和/或 `JsonGenerators`。 |
| 2 | **ObjectMapper(JsonFactory jf)**<br>构造使用指定的 `JsonFactory` 来构建必要的 `JsonParsers` 和/或 `JsonGenerators` 的映射器。 |
| 3 | **ObjectMapper(JsonFactory jf, SerializerProvider sp, DeserializerProvider dp)** |
| 4 | **ObjectMapper(JsonFactory jf, SerializerProvider sp, DeserializerProvider dp, SerializationConfig sconfig, DeserializationConfig dconfig)** |
| 5 | **ObjectMapper(SerializerFactory sf)**<br>已弃用。请使用其他构造函数；注意您可以通过 `setSerializerFactory(org.codehaus.jackson.map.SerializerFactory)` 设置序列化器工厂。 |

## ObjectMapper – 方法

| 序号 | 方法及描述 |
|---|---|
| 1 | **protected void _configAndWriteValue(JsonGenerator jgen, Object value)**<br>调用此方法，用于根据需要配置生成器，然后调用功能。 |
| 2 | **protected void _configAndWriteValue(JsonGenerator jgen, value, Class&lt;?gt;)** |
| 3 | **protected Object _convert(Object fromValue, JavaType toValue)** |
| 4 | **protected DeserializationContext _createDeserializationContext(JsonParser jp, DeserializationConfig cfg)** |
| 5 | **protected PrettyPrinter _defaultPrettyPrinter()**<br>辅助方法，当被指示使用默认美化打印器时，应返回用于由此映射器构建生成器的默认美化打印器。 |

![](img/abf38b9a96498be10686313ae639d832_14_0.png)

| 6 | **protected JsonSerializer&Object> _findRootDeserializer(DeserializationConfig cfg, JavaType valueType)**<br>调用此方法以为传递的根层级值定位反序列化器。 |
| 7 | **protected JsonToken _initForReading(JsonParser jp)**<br>调用此方法以确保给定的解析器已准备好读取内容数据绑定。 |
| 8 | **protected Object _readMapAndClose(JsonParser jp, JavaType valueType)** |
| 9 | **protected Object _readValue(DeserializationConfig cfg, JsonParser jp, JavaType valueType)**<br>值读取+绑定操作的实际实现。 |
| 10 | **protected Object _unwrapAndDeserialize(JsonParser jp, JavaType rootType, DeserializationContext cxt, JsonSerializer&lt;Object&gt; deser)** |
| 11 | **boolean canDeserialize(JavaType type)**<br>可以调用此方法来检查映射器认为是否可以反序列化给定类型的对象。 |
| 12 | **boolean canSerialize(Class&lt;?&gt; type)**<br>可以调用此方法来检查映射器认为是否可以序列化给定 `Class` 的实例。 |
| 13 | **ObjectMapper configure(DeserializationConfig.Feature f, boolean state)**<br>更改此对象映射器中开启/关闭反序列化特征状态的方法。 |
| 14 | **ObjectMapper configure(JsonGenerator.Feature f, boolean state)**<br>更改对象映射器使用的 `JsonFactory` 实例中开启/关闭 `JsonSerializer` 特性状态的方法。 |

![](img/abf38b9a96498be10686313ae639d832_15_0.png)

| 15 | **ObjectMapper configure(JsonParser.Feature f, boolean state)**<br>更改对象映射器使用的 `JsonFactory` 实例中开启/关闭 `JsonParser` 特性状态的方法。 |
| 16 | **ObjectMapper configure(SerializationConfig.Feature f, boolean state)**<br>更改此对象映射器中开启/关闭序列化特征状态的方法。 |
| 17 | **JavaType constructType(Type t)**<br>从给定类型（通常为 `java.lang.Class`）构建 `JavaType` 的便利方法，但没有显式上下文。 |



| 18 | `<T> T convertValue(Object fromValue, Class<T> toValue)`<br>从给定值转换为给定值类型实例的两步转换的便利方法。 |

| 19 | `<T> T convertValue(Object fromValue, JavaType toTypeValue)` |

| 20 | `<T> T convertValue(Object fromValue, TypeReference toTypeRef)` |

| 21 | `DeserializationConfig copyDeserializationConfig()`<br>该方法创建共享默认 `DeserializationConfig` 对象的副本，该对象定义了反序列化的配置设置。 |

| 22 | `SerializationConfig copySerializationConfig()`<br>该方法创建共享默认 `SerializationConfig` 对象的副本，该对象定义了序列化的配置设置。 |

| 23 | `ArrayNode createArrayNode()` | 

![](img/abf38b9a96498be10686313ae639d832_16_0.png)

| 24 | `ObjectNode createObjectNode()`<br>注意：返回类型是协变的，因为基础 `ObjectCodec` 无法引用具体类型（实现位于 mapper 包）。 |

| 25 | `ObjectWriter defaultPrettyPrinting()`<br>已弃用。从 1.9 开始，请使用 `writerPrettyPrinter()`。 |

| 26 | `ObjectMapper enable(DeserializationConfig.Feature... f)`<br>启用 `DeserializationConfig` 特征的方法。 |

| 27 | `ObjectMapper enable(SerializationConfig.Feature... f)`<br>启用 `SerializationConfig` 特征的方法。 |

| 28 | `ObjectMapper disableTyping()`<br>禁用自动包含类型信息的方法；如果是这样，将只包含注解的类型。 |

| 29 | `ObjectMapper disable(DeserializationConfig.Feature... f)`<br>禁用 `DeserializationConfig` 特征的方法。 |

| 30 | `ObjectMapper disable(SerializationConfig.Feature... f)`<br>禁用 `SerializationConfig` 特征的方法。 |

| 31 | `ObjectMapper enableTyping(ObjectMapper.Default dti)`<br>等同于调用的便利方法。 |

| 32 | `ObjectMapper enableTyping(ObjectMapper.Default applicability, JsonTypeInfo.As include)`<br>启用自动包含类型信息的方法，用于多态类型的反序列化（除非带有 `JsonTypeInfo`）。 |

| 33 | `ObjectMapper enableTypingAsProperty(ObjectMapper.Default applicability, String propertyName)`<br>启用自动包含类型信息的方法——使用属性机制和指定的属性名称（默认使用 `@class` 作为标识符）。 |

| 34 | `ObjectWriter filteredWriter(FilterProvider)`<br>已弃用。从 1.9 开始，请使用 `writer(FilterProvider)`。 |

| 35 | `JsonSchema generateSchema(Class<?> t)`<br>为指定的类生成 `JsonSchema` 实例。 |

| 36 | `JsonSchema generateSchema(Class<?> t, SerializationConfig cfg)`<br>使用序列化配置为指定的类生成 `JsonSchema` 实例。 |

| 37 | `DeserializationConfig getDeserializationConfig()`<br>返回共享默认 `DeserializationConfig` 对象的方法，该对象定义了反序列化的配置设置。 |

| 38 | `DeserializerProvider getDeserializerProvider()` |

| 39 | `JsonFactory getJsonFactory()`<br>可以使用此方法获取对象映射器在需要构建 `JsonParsers` 和/或 `JsonGenerators` 时使用的 `JsonFactory`。 |

| 40 | `JsonNodeFactory getNodeFactory()`<br>可以使用此方法获取对象映射器在直接构建树 `JsonNode` 实例时使用的 `JsonNodeFactory`。 |

| 41 | `SerializationConfig getSerializationConfig()`<br>返回共享默认 `SerializationConfig` 对象的方法，该对象定义了序列化的配置设置。 |

| 42 | `SerializerProvider getSerializerProvider()` |

| 43 | `SubtypeResolver getSubtypeResolver()`<br>访问正在使用的子类型解析器的方法。 |

| 44 | `TypeFactory getTypeFactory()`<br>获取当前配置的 `TypeFactory` 实例的访问器。 |

| 45 | `VisibilityChecker<?> getChecker()`<br>访问当前配置的可视性检查器；该对象用于确定给定的属性元素（方法、字段、构造函数）是否可以自动检测。 |

| 46 | `boolean isEnabled(DeserializationConfig.Feature f)` |

| 47 | `boolean isEnabled(JsonGenerator.Feature f)` |

| 48 | `boolean isEnabled(JsonParser.Feature f)` |

| 49 | `boolean isEnabled(SerializationConfig.Feature f)` |

| | |

|---|-|

| 51 | `ObjectWriter prettyPrintingWriter(PrettyPrinter pp)` |

| 52 | `ObjectReader reader()` <br>使用默认设置构建 `ObjectReader` 的工厂方法。 |

| 53 | `ObjectReader reader(Class<?> type)` <br>用于构建读取或更新指定类型实例的 `ObjectReader` 的工厂方法。 |

| 54 | `ObjectReader(FormatSchema schema)` <br>用于构建 `ObjectReader` 的工厂方法，该方法会将特定的 schema 对象传递给用于读取内容的 `JsonParser`。 |

| 55 | `ObjectReader(InjectableValues injectableValues)` <br>用于构建使用指定注入值的 `ObjectReader` 的工厂方法。 |

| 56 | `ObjectReader(JavaType type)` <br>用于构建读取或更新指定类型实例的 `ObjectReader` 的工厂方法。 |

| 57 | `ObjectReader reader(JsonNodeFactory f)` <br>用于构建 `ObjectReader` 的工厂方法，该方法将使用指定的 `JsonNodeFactory` 来构建 JSON 树。 |

| 58 | `ObjectReader reader(TypeReference<?> type)` <br>用于构建读取或更新指定类型实例的 `ObjectReader` 的工厂方法。 |

| 59 | `ObjectReader readerForUpdating(Object valueToUpdate)` | 用于构建 `ObjectReader` 的工厂方法，该方法将用 JSON 数据更新指定的 `Object`（通常是 Bean，也可以是 `Collection` 或 `Map`，但不能是数组）。 |

| 60 | `JsonNode readTree(byte[]) content` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

| 61 | `JsonNode readTree(File file)` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

| 62 | `JsonNode readTree(InputStream in)` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

| 63 | `JsonNode readTree(JsonParser jp)` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

| 64 | `JsonNode readTree(JsonParser jp, DeserializationConfig cfg)` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

| 65 | `JsonNode readTree(Reader r)` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

| 66 | `JsonNode readTree(String content)` 方法将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。 |

![](img/abf38b9a96498be10686313ae639d832_21_0.png)

## `JsonNode readTree(URL source)`

将 JSON 内容反序列化为使用一组 `JsonNode` 实例表示的树。

```
<T> T readValue(byte[]) src, Class<T> valueType
```

```
<T> T readValue(byte[]) src, int offset, int len, Class<T> valueType
```

```
<T> T readValue(byte[]) src, int offset, int len, JavaType valueType
```

```
<T> T readValue(byte[]) src, int offset, int len, TypeReference valueTypeRef
```

```
<T> T readValue(byte[]) src, JavaType valueType
```

```
<T> T readValue(byte[]) src, TypeReference valueTypeRef
```

```
<T> T readValue(File src, Class<T> valueType
```

```
<T> T readValue(File src, JavaType valueType
```

```
<T> T readValue(File src, TypeReference valueTypeRef
```

```
<T> T readValue(InputStream src, Class<T> valueType
```

```
<T> T readValue(InputStream src, JavaType valueType
```

```
<T> T readValue(InputStream src, TypeReference valueTypeRef
```

```
<T> T readValue(JsonNode root, Class<T> valueType
```

用于将给定的 JSON 树结果转换为给定值类型的便利方法。

```
<T> T readValue(JsonNode root, JavaType valueType)
```

用于将给定的 JSON 树结果转换为给定值类型的便利方法。

![](img/abf38b9a96498be10686313ae639d832_22_0.png)

| `<T> readValue(JsonNode root, TypeReference valueType)` | 82 | 用于将给定的 JSON 树结果转换为给定值类型的便利方法。 |

| `<T> readValue(JsonParser jp, Class<T> valueType)` | 83 | 将 JSON 内容反序列化为非容器类型的方法（尽管它可以是数组类型）：通常是一个 bean、数组或包装类型（如 `Boolean`）。 |

| `<T> readValue(JsonParser jp, Class<T> valueType, DeserializationConfig cfg)` | 84 | 将 JSON 内容反序列化为非容器类型的方法（尽管它可以是一个数组类型）：通常是一个 bean、数组或包装类型（如 `Boolean`）。 |

| `<T> readValue(JsonParser jp, Java valueType)` | 85 | 将 JSON 内容反序列化为 Java 类型的方法，该类型的引用作为参数传递。 |

| `<T> readValue(JsonParser jp, Java valueType, DeserializationConfig cfg)` | 86 | 将 JSON 内容反序列化为 Java 类型的方法，该类型的引用作为参数传递。 |

| `<T> readValue(JsonParser jp, TypeReference<?> valueType)` | 87 | 将 JSON 内容反序列化为 Java 类型的方法，该类型的引用作为参数传递。 |

| `<T> readValue(JsonParser jp, TypeReference<?> valueType, DeserializationConfig cfg)` | 88 | 将 JSON 内容反序列化为 Java 类型的方法，该类型的引用作为参数传递。 |

| `<T> readValue(Reader src, Class<T> valueType` | 89 | 使用 `Reader src` 反序列化为类型。 |

| `<T> readValue(Reader src, JavaType valueType` | 90 | 使用 `Reader src` 反序列化为类型。 |

| `<T> readValue(Reader src, TypeReference valueTypeRef` | 91 | 使用 `Reader src` 反序列化为类型。 |

| `<T> readValue(String content, Class<T> valueType` | 92 | 使用 `String content` 反序列化为类型。 |

| `<T> readValue(String content, JavaType valueType` | 93 | 使用 `String content` 反序列化为类型。 |

| `<T> readValue(String content, TypeReference valueTypeRef` | 94 | 使用 `String content` 反序列化为类型。 |

| `<T> readValue(URL src, Class<T> valueType` | 95 | 使用 `URL src` 反序列化为类型。 |

| `<T> readValue(URL src, JavaType valueType` | 96 | 使用 `URL src` 反序列化为类型。 |

| `<T> readValue(URL src, TypeReference valueTypeRef` | 97 | 使用 `URL src` 反序列化为类型。 |

| `<T> readValue(JsonNode root, Class<T> valueType` | 98 | 使用 `JsonNode root` 反序列化为类型。 |

| `<T> readValue(JsonNode root, JavaType valueType` | 99 | 使用 `JsonNode root` 反序列化为类型。 |

| `<T> readValue(JsonNode root, TypeReference valueTypeRef` | 100 | 使用 `JsonNode root` 反序列化为类型。 |

| 101 | `void registerModule(Module)` |

| 102 | `void registerSubtypes(Class<?>... classes)` |

| | `void registerSubtypes(NamedType... types)` |

| | `ObjectReader schemaBasedReader(FormatSchema)` |

| | `ObjectWriter schemaBasedWriter(FormatSchema)` |

| | `ObjectMapper setAnnotationIntpector(AnnotationIntpector)` |

| | `void setDateFormat(DateFormat)` |

| | `ObjectMapper setDefaultTyping(TypeResolverBuilder)` |

| | `ObjectMapper setDeserializationConfig(DeserializationConfig)` |

| | `ObjectMapper setDeserializerProvider(DeserializerProvider)` |

![](img/abf38b9a96498be10686313ae639d832_25_0.png)



`void setFilters(FilterProvider)`

`void setHandlerInstantiator(HandlerInstantiator hi)`

用于配置`HandlerInstantiator`以创建处理器实例（如序列化器、反序列化器、类型和 ID 解析器）。

`ObjectMapper setInjectableValues(InjectableValues)`

`ObjectMapper getNodeFactory(JsonNodeFactory f)`

指定用于构建根节点树节点的`JsonFactory`（通过方法`createObjectNode()`）。

`ObjectMapper setPropertyNameStrategy(PropertyNamingStrategy s)`

用于设置使用的自定义属性命名策略。

`ObjectMapper setSerializationConfig(SerializationConfig cfg)`

用于替换共享的默认序列化配置对象。

`ObjectMapper setSerializationInclusion(JsonSerialize.Inclusion incl)`

用于设置序列化时的默认 POJO 属性包含策略。

`ObjectMapper setSerializerFactory(SerializerFactory f)`

用于设置用于构建（bean）序列化器的特定`SerializerFactory`。

`ObjectMapper setSerializerProvider(SerializerProvider p)`

用于设置特定的`SerializerProvider`，以处理`JsonSerializer`实例的缓存。

`void setSubtypeResolver(SubtypeResolver r)`

设置要使用的自定义子类型解析器的方法。

`ObjectMapper setTypeFactory(TypeFactory f)`

用于覆盖此 mapper 所使用的`TypeFactory`实例的方法。

`ObjectMapper setVisibility(JsonMethod forMethod, JsonAutoDetect.Visibility visibility)`

一种便捷方法，允许更改底层`VisibilityChecks`的配置，以更改检测哪些类型属性的细节。

`void setVisibility(VisibilityChecker<?> vc)`

设置当前配置的可见性检查器的方法；该对象用于确定判断给定的属性元素（方法、字段、构造函数）是否可以被自动检测。

`JsonParser treeAsTokens(JsonNode n)`

从 JSON 树表示构建`JsonParser`的方法。

```java
<T> T treeValue(JsonNode n, Class<T> valueType)
```

一种便捷的转换方法，当 JSON 树包含（通常是 bean）类型时，绑定数据。

```java
ObjectWriter typedWriter(Class<?> rootType)
```

已废用。从 1.9 版本起，请使用`writerWithType(Class)`代替。

```java
ObjectWriter typedWriter(JavaType rootType)
```

已废用。从 1.9 版本起，请使用`writerWithType(JavaType)`代替。

## ObjectWriter typedWriter(TypeReference<?> rootType)

已废用。从 1.9 版本起，请使用`writerWithType(TypeReference)`代替。

## ObjectReader updatingReader(Object valueToUpdate)

已废用。从 1.9 版本起，请使用`readerForUpdating(java.lang.Object)`代替。

## <T extends JsonNode> T valueToTree(Object fromValue)

`treeToValue(org.codehaus.jackson.JsonNode, java.lang.Class)`的逆操作；给定一个值（通常是 bean），构建等值的 JSON 树表示。

## Version version()

返回从包含此类的 jar 中存储并读取的版本信息的方法。

## ObjectWriter viewWriter(Class<?> serializationView)

已废用。从 1.9 版本起，请使用`WithView(Class)`代替。

## ObjectMapper withModule(Module module)

`registerModule(org.codehaus.jackson.map.Module)`的流式风格替代方案。

## ObjectWriter writer()

用于使用默认设置构建`ObjectWriter`的便捷方法。

## ObjectWriter writer(DateFormat df)

构建通过指定的`DateFormat`序列化对象的`ObjectWriter`的工厂方法；如果传递 null，则使用时间戳（64 位数字）。

## ObjectWriter writer(FilterProvider filterProvider)

构建使用指定的 filter provider 序列化对象的`ObjectWriter`的工厂方法。

| 138 | **ObjectWriter writer(FormatSchema)** | 构建`ObjectWriter`的工厂方法，该方法传递特定的 schema 对象用于`JsonGenerator`写入内容。 |
|---|---|---|
| 139 | **ObjectWriter writer(PrettyPrinter pp)** | 构建使用指定的 printer 进行缩进（或如果为 null，则无格式化打印）序列化对象的`ObjectWriter`的工厂方法。 |
| 140 | **ObjectWriter withDefaultPrettyPrinter()** | 构建使用默认 printer 进行缩进序列化对象的`ObjectWriter`的工厂方法。 |
| 141 | **ObjectWriter withType(Class<?> rootType)** | 构建`ObjectWriter`的工厂方法，该方法使用指定的根类型序列化对象，而不是值的实际运行时类型。 |
| 142 | **ObjectWriter withType(JavaType rootType)** | 构建`ObjectWriter`的工厂方法，该方法使用指定的根类型序列化对象，而不是值的实际运行时类型。 |
| 143 | **ObjectWriter withType(TypeReference<?> rootType)** | 构建`ObjectWriter`的工厂方法，该方法使用指定的根类型序列化对象，而不是值的实际运行时类型。 |
| 144 | **ObjectWriter withView(Class<?> serializationView)** | 构建`ObjectWriter`的工厂方法，该方法使用指定的 JSON View（过滤器）序列化对象。 |
| 145 | `void writerTree(JsonGenerator jgen, JsonNode rootNode)` | 使用提供的生成器序列化给定的 JSON 树的方法。 |
| 146 | **void writeTree(JsonGenerator jgen, JsonNode rootNode, SerializationConfig cfg)** | 使用提供的生成器序列化给定的 JSON 树的方法。 |
| 147 | **void writeValue(File resultFile, Object value)** | 用于将任何 Java 值序列化为 JSON 输出并写入提供的`File`方法。 |
| 148 | **void writeValue(JsonGenerator jgen, Object value)** | 使用提供的`JsonGenerator`将任何 Java 值序列化为 JSON 输出的方法。 |
| 149 | **void writeValue(JsonGenerator jgen, Object value, SerializationConfig config)** | 使用提供的`JsonGenerator`将任何 Java 值序列化为 JSON 输出，并根据传递的配置对象进行配置。 |
| 150 | **void writeValue(OutputStream out, Object value)** | 使用提供的输出流将任何 Java 值序列化为 JSON 输出的方法（使用`JsonEncoding.UTF8`编码）。 |
| 151 | **void writeValue(Writer w, Object value)** | 使用提供的`Writer`将任何 Java 值序列化为 JSON 输出的方法。 |
| 152 | **byte[] writeValueAsBytes(Object value)** | 将任何 Java 值序列化为字节数组形式的 JSON 输出的方法。 |
| 153 | **String writeValueAsString(Object value)** | 将任何 Java 值序列化为字符串形式的 JSON 输出的方法。 |

## 5. 对象序列化

为了详细了解对象序列化，让我们将一个 Java 对象序列化为 JSON 文件，然后读取该 JSON 文件以获取该对象。

## 对象序列化 – 示例

在接下来的示例中，我们将创建一个`Student`类。之后，我们将创建一个`.json`文件，该文件将包含`Student`对象的 JSON 表示。

首先，在`C:\>Jackson_WORKSPACE`中创建一个名为`JacksonTester`的 Java 类文件。

文件：`JacksonTester.java`

```java
import java.io.File;
import java.io.IOException;

import org.codehaus.jackson.JsonGenerationException;
import org.codehaus.jackson.JsonParseException;
import org.codehaus.jackson.map.JsonMappingException;
import org.codehaus.jackson.map.ObjectMapper;
import org.codehaus.jackson.map.SerializationConfig;

public class JacksonTester {
    private ObjectMapper mapper = new ObjectMapper();

    public void writeJSON(Object obj) throws IOException {
        mapper.writeValue(new File("student.json"), obj);
    }

    public Student readJSON(Student obj) throws IOException {
        return mapper.readValue(new File("student.json"), Student.class);
    }

    public static void main(String[] args[]) {
        JacksonTester tester = new JacksonTester();
        try {
            Student student = new Student();
            student.setAge(10);
            student.setName("Mahesh");
            tester.writeJSON(student);

            Student student1 = tester.readJSON(student);
            System.out.println(student1);

        } catch (JsonParseException e) {
            e.printStackTrace();
        } catch (JsonMappingException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

class Student {
    private String name;
    private int age;
    public Student(){}
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    @Override
    public String toString() {
        return "Student [ name: "+name+", age: "+age+" ]";
    }
}
```

```java
    e.printStackTrace();
} catch (JsonMappingException e) {
    e.printStackTrace();
} catch (IOException e) {
    e.printStackTrace();
}
```

```java
private void writeJSON(Student student) throws JsonGenerationException,
JsonMappingException, IOException {
    ObjectMapper mapper = new ObjectMapper();
    mapper.writeValue(new File("student.json"), student);
}
```

```java
private Student readJSON() throws JsonParseException,
JsonMappingException, IOException {
    ObjectMapper mapper = new ObjectMapper();
    Student student = mapper.readValue(new File("student.json"), Student.class);
    return student;
}
```

```java
class Student {
    private String name;
    private int age;
    public Student(){}
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String toString(){
        return "Student [ name: "+name+", age: "+ age+" ]";
    }
}
```

## 验证结果

使用`javac`编译器按如下方式编译类：

```
C:\Jackson_WORKSPACE>javac JacksonTester.java
```

现在执行`jacksonTester`查看结果。

```
C:\Jackson_WORKSPACE>java JacksonTester
```

验证输出：

```
Student [ name: Mahesh, age: 10 ]
```

# 6. 数据绑定

数据绑定 API（Data Binding API）用于通过属性访问器或注解在 JSON 与普通 Java 对象（POJO）之间进行转换。它包含两种类型之一：

- 简单数据绑定 – 它在 JSON 与 Java Maps、Lists、Strings、Numbers、Booleans 和空对象之间进行转换。
- 全量数据绑定 – 它在 JSON 与任何 Java 类型之间进行转换。



`ObjectMapper`为这两种类型的数据绑定提供了读取/写入 JSON 的。数据绑定类似于用于 XML 的 JAXB 解析器。

我们将在本章中介绍简单数据绑定。全量绑定将在将在章单独讨论。

## 简单数据绑定

简单数据绑定指的是 JSON 到 Java 核心数据类型的映射。表格说明了 JSON 类型与 Java 类型之间的关系。

| 序号 | JSON 类型 | Java 类型 |
|---|---|---|
| 1 | object | `LinkedHashMap<String,Object>` |
| 2 | array | `ArrayList<Object>` |
| 3 | string | `String` |
| 4 | 整数数字 | `Integer`, `Long` or `BigInteger` |
| 5 | 小数数字 | `Double` / `BigDecimal` |
| 6 | true / false | `Boolean` |
| 7 | null | `null` |

## 简单数据绑定 – 示例

让我们通过一个简单的示例来详细简单数据绑定。在这里，我们将 Java 基础类型直接映射到 JSON，反之亦然。

在`C:\Jackson_WORKSPACE`中创建一个名为`JacksonTester`的 Java 类。

![](img/abf38b9a96498be10686313ae639d832_37_0.png)

### 文件：`JacksonTester.java`

```java
import java.io.File;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

import org.codehaus.jackson.JsonGenerationException;
import org.codehaus.jackson.JsonParseException;
import org.codehaus.jackson.map.JsonMappingException;
import org.codehaus.jackson.map.ObjectMapper;

public class JacksonTester {
    public static void main(String[] args) {
        JacksonTester tester = new JacksonTester();
        try {
            ObjectMapper mapper = new ObjectMapper();

            Map<String, Object> studentDataMap = new HashMap<String, Object>();
            int[] marks = {1,2,3};

            Student student = new Student();
            student.setAge(10);
            student.setName("Mahesh");
            // JAVA Object
            studentDataMap.put("student", student);
            // JAVA String
            studentDataMap.put("name", "Mahesh Kumar");
            // JAVA Boolean
            studentDataMap.put("verified", false);
            // Array
            studentDataMap.put("marks", marks);

            mapper.writeValue(new File("student.json"), studentDataMap);
```

![](img/abf38b9a96498be10686313ae639d832_38_0.png)

```json
// result.json
// "student":{"name":"Mahesh","age":10},
// "marks":[1,2,3],
// "verified":false,
// "name":"Mahesh Kumar"
```

```java
studentDataMap = mapper.readValue(new File("student.json"), Student.class);

System.out.println(studentDataMap.get("student"));
System.out.println(studentDataMap.get("name"));
System.out.println(studentDataMap.get("verified"));
System.out.println(studentDataMap.get("marks"));

} catch (JsonParseException e) {
    e.printStackTrace();
} catch (JsonMappingException e) {
    e.printStackTrace();
} catch (IOException e) {
    e.printStackTrace();
}

class Student {
    private String name;
    private int age;
    public Student(){}
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

## Jackson

```java
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String toString() {
        return "Student [ name: "+name+", age: "+age+" ]";
    }
```

## 验证结果

使用`javac`编译器按如下方式编译类：

```
C:\Jackson_WORKSPACE>javac JacksonTester.java
```

现在执行`jacksonTester`查看结果。

```
C:\Jackson_WORKSPACE>java JacksonTester
```

验证输出：

```
{name=Mahesh, age=10}
```

```
Mahesh Kumar
```

```
false
```

```
[1, 2, 3]
```

## 7. 全量数据绑定

全量绑定指的是 JSON 到任何 Java 对象的映射。

```java
// 创建 ObjectMapper 实例
ObjectMapper mapper = new ObjectMapper();

// 将 JSON 映射到 Student 对象
Student student = mapper.readValue(new File("student.json"), Student.class);

mapper.writeValue(new File("student.json"), student);
```

## 全量数据绑定 – 示例

让我们通过一个简单的示例来详细全量数据绑定。在示例中，我们将 Java 对象直接映射到 JSON，反之亦然。

在`C:\Jackson_WORKSPACE`中创建一个名为`JacksonTester`的 Java 类。

### 文件：`JacksonTester`

```java
import java.io.File;
import java.io.IOException;

import org.codehaus.jackson.JsonGenerationException;
import org.codehaus.jackson.JsonParseException;
import org.codehaus.jackson.map.JsonMappingException;
import org.codehaus.jackson.map.ObjectMapper;

public class JacksonTester {
    public static void main(String[] args){
        JacksonTester tester = new JacksonTester();
        try {
            Student student = new Student();
            student.setAge(10);
```

```java
            student.setName("Mahesh");
            tester.writeJSON(student);

            Student student1 = tester.readJSON();
            System.out.println(student1);
```

```java
        } catch (JsonParseException e) {
          e.printStackTrace();
        } catch (JsonMappingException e) {
          e.printStackTrace();
        } catch (IOException e) {
          e.printStackTrace();
        }
```

```java
private void writeJSON(Student student) throws JsonGenerationException,
JsonMappingException, IOException{
    ObjectMapper mapper = new ObjectMapper();
    mapper.writeValue(new File("student.json"), student);
}
```

```java
private Student readJSON() throws JsonParseException,
JsonMappingException, IOException{
    ObjectMapper mapper = new ObjectMapper();
    Student student = mapper.readValue(new File("student.json"), Student.class);

    return student;
}
```

```java
class Student {
  private String name;
  private int age;
```

```java
    public Student(){}
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String toString(){
        return "Student [ name: "+name+", age: "+age+" ]";
    }
}
```

## 验证结果

使用`javac`编译器按如下方式编译类：

```
C:\Jackson_WORKSPACE\javac JacksonTester.java
```

现在执行`jacksonTester`查看结果。

```
C:\Jackson_WORKSPACE>java JacksonTester
```

验证输出：

```
Student [ name: Mahesh, age: 10 ]
```

## 8. 泛型数据绑定

在简单数据绑定中，我们使用了`Map`类，它使用`String`作为键，`Object`作为值对象。相反，我们可以有一个具体的 Java 对象并对其进行类型转换以用于 JSON 绑定。

考虑以下带有`UserData`类的示例，这是一个存储特定数据的类。

在`C:\Jackson_WORKSPACE`中创建一个名为`JacksonTester`的 Java 类文件。

### 文件：`JacksonTester.java`

```java
import java.io.File;
import java.io.IOException;
import java.util.Arrays;
import java.util.HashMap;
import java.util.List;
import java.util.Map;

import org.codehaus.jackson.JsonGenerationException;
import org.codehaus.jackson.JsonParserException;
import org.codehaus.jackson.map.JsonMappingException;
import org.codehaus.jackson.map.ObjectMapper;
import org.codehaus.jackson.type.TypeReference;

public class JacksonTester {
    public static void main(String[] args){
        JacksonTester tester = new JacksonTester();
        try {
            ObjectMapper mapper = new ObjectMapper();

            Map userDataMap = new HashMap();
            UserData studentData = new UserData();
            int[] marks = {1,2,3};
```

```java
Student student = new Student();

student.setAge(10);
student.setName("Mahesh");

// JAVA Object
studentData.setStudent(student);

// JAVA String
studentData.setName("Mahesh Kumar");

// JAVA Boolean
studentData.setVerified(Boolean.FALSE);

// Array
studentData.setMarks(marks);
TypeReference ref = new TypeReference<map>() { };
userDataMap.put("studentData1", studentData);
mapper.writeValue(new File("student.json"), userDataMap);
// {
//   "studentData1":
//   {
//     "student":
//     {
//       "name":"Mahesh",
//       "age":10
//     }
//     "name":"Mahesh Kumar",
//     "verified":false,
//     "marks":[1,2,3]
//     }
//   }
// }
userDataMap = mapper.readValue(new File("student.json"), ref);
```

## Jackson



```java
System.out.println(userDataMap.get("studentData1").getStudent());
System.out.println(userDataMap.get("studentData1").getName());

System.out.println(userDataMap.get("studentData1").getVerified());
System.out.println(Arrays.toString(userDataMap.get("studentData1").getMarks()));
} catch (JsonParseException e) {
    e.printStackTrace();
} catch (JsonMappingException e) {
    e.printStackTrace();
} catch (IOException e) {
    e.printStackTrace();
}
}

class Student {
    private String name;
    private int age;
    public Student(){}
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String toString() {
        return "Student [ name: "+name+", age: "+age+" "]";
    }
}
```

![](img/abf38b9a96498be10686313ae639d832_46_0.png)

```java
}

class UserData {
    private Student student;
    private String name;
    private Boolean verified;
    private int[] marks;

    public UserData(){}

    public Student getStudent() {
        return student;
    }

    public void setStudent(Student student) {
        this.student = student;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Boolean getVerified() {
        return verified;
    }

    public void setVerified(Boolean verified) {
        this.verified = verified;
    }

    public int[] getMarks() {
        return marks;
    }

    public void setMarks(int[] marks) {
        this.marks = marks;
    }
}
```

![](img/abf38b9a96498be10686313ae639d832_47_0.png)

## 验证结果

使用`javac`编译器编译类：

```
C:\Jackson_WORKSPACE>javac JacksonTester.java
```

现在运行`JacksonTester`查看结果：

```
C:\Jackson_WORKSPACE>java JacksonTester
```

验证输出：

| Student [ name: Mahesh, age: 10 ] |
| Mahesh Kumar |
| false |
| [1, 2, 3] |

## 9. 树形模型 (TREE MODEL)

树模型为 JSON 文档准备了内存中的树表示。它是 Jackson 支持的三种处理模式中最具活性的方法。它与 XML 中的 DOM 解析器非常相似。

### 从 JSON 创建树

`ObjectMapper`在读取 JSON 后会提供一个指向树根节点的指针。可以使用根节点来遍历整棵树。考虑以下代码片段以获取提供的 JSON 字符串的根节点。

```java
// 创建 ObjectMapper 实例
ObjectMapper mapper = new ObjectMapper();
String jsonString = "{\"name\":\"Mahesh Kumar\",\"age\":21,\"verified\":false,\"marks\":[100,90,85]}";

// 从 JSON 创建树
JsonNode rootNode = mapper.readTree(jsonString);
```

### 遍历树

在遍历树时，使用相对于根节点的相对路径获取每个节点并处理数据。以下代码片段展示了在拥有根节点信息的情况下如何遍历树。

```java
JsonNode nameNode = rootNode.path("name");
System.out.println("Name: " + nameNode.getTextValue());
JsonNode marksNode = rootNode.path("marks");
Iterator iterator = marksNode.getElements();
```

![](img/abf38b9a96498be10686313ae639d832_49_0.png)

### 树形模型 – 示例

在`C:\Jackson_WORKSPACE`中创建一个名为`JacksonTester`的 Java 类文件。

### 文件: JacksonTester.java

```java
import java.io.IOException;
import java.util.Iterator;
import com.fasterxml.jackson.databind.JsonNode;
import com.fasterxml.jackson.core.JsonParseException;
import com.fasterxml.jackson.databind.JsonMappingException;
import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.node.ArrayNode;
import com.fasterxml.jackson.databind.node.ObjectNode;

public class JacksonTester {
    public static void main(String[] args) {
        ObjectMapper mapper = new ObjectMapper();
        String jsonString = "{\"name\":\"Mahesh Kumar\",\"age\":21,\"verified\":false,\"marks\":[100,90,85]}";
        try {
            JsonNode rootNode = mapper.readTree(jsonString);
            JsonNode nameNode = rootNode.path("name");
            System.out.println("Name: " + nameNode.getTextValue());
            JsonNode ageNode = rootNode.path("age");
            System.out.println("Age: " + ageNode.getIntValue());
            JsonNode verifiedNode = rootNode.path("verified");
            System.out.println("Verified: " + (verifiedNode.booleanValue() ? "Yes" : "No"));
            JsonNode marksNode = rootNode.path("marks");
            Iterator<JsonNode> iterator = marksNode.elements();
            while (iterator.hasNext()) {
                JsonNode node = iterator.next();
                System.out.println("Mark: " + node.asInt());
            }
        } catch (JsonParseException e) {
            e.printStackTrace();
        } catch (JsonMappingException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

```
C:\Jackson_WORKSPACE>java JacksonTester
```

验证输出：

```
Name: Mahesh Kumar
Age: 21
Verified: No
Marks: [ 100 90 85 ]
```

### 将树转换为 Java 对象

在以下示例中，我们将执行以下操作：

- 使用`JsonNode`创建一个树
- 将其写入 JSON 文件
- 重新读取树并将其转换为`Student`对象

首先，在`C:\Jackson_WORKSPACE`中创建一个名为`JacksonTester`的 Java 类。

### 文件：JacksonTester.java

```java
import java.io.File;
import java.io.IOException;
import java.util.Arrays;
import org.codehaus.jackson.JsonNode;
import org.codehaus.jackson.JsonParseException;
import org.codehaus.jackson.map.JsonMappingException;
import org.codehaus.jackson.map.ObjectMapper;
import org.codehaus.jackson.node.ArrayNode;
import org.codehaus.jackson.node.ObjectNode;

public class JacksonTester {
    public static void main(String[] args[]){
        JacksonTester tester = new JacksonTester();
```

![](img/abf38b9a96498be10686313ae639d832_54_0.png)

```java
try {
    ObjectMapper mapper = new ObjectMapper();
    JsonNode rootNode = mapper.createObjectNode();
    JsonNode marksNode = mapper.createArrayNode();
    ((ArrayNode)marksNode).add(100);
    ((ArrayNode)marksNode).add(90);
    ((ArrayNode)marksNode).add(85);
    ((ObjectNode) rootNode).put("name", "Mahesh Kumar");
    ((ObjectNode) rootNode).put("age", 21);
    ((ObjectNode) rootNode).put("verified", false);
    ((ObjectNode) rootNode).put("marks",marksNode);
    mapper.writeValue(new File("student.json"), rootNode);
    rootNode = mapper.readTree(new File("student.json"));
    Student student = mapper.treeValue(rootNode, Student.class);
    System.out.println("Name: " + student.getName());
    System.out.println("Age: " + student.getAge());
    System.out.println("Verified: " + (student.isVerified() ? "Yes":":"No"));
    System.out.println("Marks: "+Arrays.toString(student.getMarks()));
} catch (JsonParseException e) {
    e.printStackTrace();
} catch (JsonMappingException e) {
    e.printStackTrace();
} catch (IOException e) {
    e.printStackTrace();
}
}
```

```java
class Student {
    String name;
    int age;
    boolean verified;
    int[] marks;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public boolean isVerified() {
        return verified;
    }
    public void setVerified(boolean verified) {
        this.verified = verified;
    }
    public int[] getMarks() {
        return marks;
    }
    public void setMarks(int[] marks) {
        this.marks = marks;
    }
}
```

## 验证结果

使用`javac`编译器如下所示编译类：

```
C:\>Jackson_WORKSPACE>javac JacksonTester.java
```

现在执行`JacksonTester`查看结果。

```
C:\>Jackson_WORKSPACE>java JacksonTester
```

验证输出：

```
Name: Mahesh Kumar
Age: 21
Verified: No
Marks: [ 100 90 85 ]
```

## 10. 流式 API (STREAMING API)

流式 API 作为离散事件读取和写入 JSON 内容。`JsonParser`读取数据，而`JsonGenerator`写入数据。

- 它是 Jackson 支持的三种处理模式中最强大的方法。
- 它的开销最低，提供了执行读/写操作最快的方法。
- 它类似于 XML 的 Stax 解析器。

在本章中，我们将讨论如何使用 Jackson 流式 API 读取和写入 JSON 数据。流式 API 基于令牌（token）的概念工作，JSON 的每一个细节都必须仔细处理。以下是本章将使用的两个类：

- `JsonGenerator` - 写入 JSON 字符串。
- `JsonParser` - 解析 JSON 字符串。

## JsonGenerator

`JsonGenerator`是定义写入 JSON 内容公共 API 的基类。实例通过`JsonFactory`实例的工厂方法创建。

### 类声明

以下是`org.fasterxml.jackson.JsonGenerator`类的声明：

```java
public abstract class JsonGenerator
  extends Object
  implements Closeable
```



### 嵌套类

| 序号. | 类与描述 |
| :--- | :--- |
| 1 | 静态类 `JsonGenerator.Feature` 枚举，定义了生成器所有可切换的特性。 |

### 字段

`protected PrettyPrinter getPrinter` - 通常用于添加缩进以提高人类可读性。

### 构造函数

| 序号. | 描述 |
| :--- | :--- |
| 1 | 默认构造函数 |

### 方法

| 序号. | 描述 |
| :--- | :--- |
| 1 | `canUseSchema(FormatSchema schema)` - 检查是否可以使用生成器。 |
| 2 | `close()` - 用于关闭此生成器。 |
| 3 | `configure(JsonGenerator.Feature, boolean state)` - 启用或禁用特性。 |
| 4 | `copyCurrentEvent(JsonParser jp)` - 复制当前事件。 |
| 5 | `copyStructure(JsonParser jp)` - 复制结构。 |
| 6 | `disable(JsonGenerator.Feature)` - 禁用特性。 |
| 7 | `disableFeature(JsonGenerator.Feature)` - 已用，使用 `disable(org.fasterxml.jackson.JsonGenerator.Feature)` |
| 8 | `enable(JsonGenerator.Feature)` - 启用特性。 |
| 9 | `enableFeature(JsonGenerator.Feature)` - 已用，使用 `enable(org.fasterxml.jackson.JsonGenerator.Feature)` |
| 10 | `flush()` - 将缓冲区内容刷新到目标。 |
| 11 | `getCharacterEscapes()` - 获取自定义转义的方法。 |
| 12 | `getCodec()` - 获取用于写入 Java 对象的的方法。 |
| 13 | `getHighestEscapedChar()` - 获取配置的最高未转义字符。 |
| 14 | `getContext()` - 获取流上下文的方法。 |
| 15 | `getOutputTarget()` - 用于访问作为目标对象的方法。 |
| 16 | `isClosed()` - 用于判断生成器是否关闭的方法。 |
| 17 | `isEnabled(JsonGenerator.Feature)` - 检查给定特性是否已启用。 |
| 18 | `isEnabled(JsonGenerator.Feature)` - 已用，使用 `isEnabled(org.fasterxml.jackson.JsonGenerator.Feature)`。 |
| 19 | `setCharacterEscapes(CharacterEscapes esc)` - 定义自定义转义的方法。 |
| 20 | `setCodec(Codec oc)` - 用于设置或重置对象的方法。 |
| 21 | `setFeature(JsonGenerator.Feature, boolean state)` - 已用，使用 `configure`。 |
| 22 | `setHighestNonEscapedChar(int charCode)` - 请求对代码点以上的字符进行转义。 |
| 23 | `setPrettyPrinter(PrettyPrinter pp)` - 设置自定义美化打印器的方法。 |
| 24 | `setSchema(FormatSchema schema)` - 调用以使生成器使用指定的架构。 |

```json
abstract JsonGenerator useDefaultPrettyPrinter()
```

使用默认格式化打印器（`DefaultPrettyPrinter`）启用格式化输出的便利方法。

## Version version()

用于检测实现此接口的组件版本的方法；返回的版本不应为 `null`，但可能会返回特定的“不可用”状态（详见 `Version` 的类）。

```java
void writeArrayFieldStart(String fieldName)
```

用于输出字段条目（"member"）（将包含一个 JSON 数组值）以及 `START_ARRAY` 标记的便利方法。

```java
abstract void writeBinary(Base64Variant b6variant, byte[] data, int offset, int len)
```

将给定的二进制数据块以 base64 编码输出，作为一个完整的字符串值（由双引号包围）的方法。

```java
void writeBinary(byte[] data)
```

与 `writeBinary(Base64Variant, byte[], int, int)` 类似，但假设默认使用 Jackson 的默认 Base64 变体（即 `Base64Variants.MIME_NO_LINEFEEDS`）。

```java
void writeBinary(byte[] data, int offset, int len)
```

与 `writeBinary(Base64Variant, byte[], int, int)` 类似，但默认使用 Jackson 的默认 Base64 变体（即 `Base64Variants.MIME_NO_LINEFEEDS`）。

```java
void writeBinaryField(String fieldName, byte[] data)
```

用于输出包含 base64 编码格式指定数据的字段条目（"member"）的便利方法。

```java
abstract void writeBoolean(boolean state)
```

输出字面 Json 布尔值（字符串 `'true'` 或 `'false'` 之一）的方法。

```java
void writeBooleanField(String fieldName, boolean value)
```

输出具有布尔值字段条目（"member"）的便利方法。

```java
abstract void writeEndArray()
```

写入 JSON 数组值的结束标记（字符 `']'`）的方法，如果启用了格式化输出，则还可能包含空白装饰。

```java
abstract void writeEndObject()
```

写入 JSON 对象值的结束标记（字符 `'}'`）的方法；如果启用了格式化输出，则还可能包含空白装饰。

```java
void writeFieldName(SerializableString)
```

与 `writeFieldName(String)` 类似，主要区别在于执行的某些处理（例如对某些字符加引号或编码为生成器支持的外部编码）可以只执行一次并供后续调用用。

```java
void writeFieldName(SerializedString)
```

与 `writeFieldName(String)` 类似，主要区别在于执行的某些处理（例如对某些字符加引号或编码为生成器支持的外部编码）可以只执行一次并供后续调用用。

```java
abstract void writeFieldName(String)
```

写入字段名的方法（双引号包围的 JSON 字符串：语法上与 JSON 字符串值相同，如果启用了格式化输出，则可能被空白装饰）。

```java
abstract void writeNull()
```

输出字面 Json `null` 值的方法。

```java
void writeNullField(String fieldName)
```

输出具有 JSON 字面值 `null` 的字段条目（"member"）的便利方法。

```java
abstract void writeNumber(BigDecimal dec)
```

输出指示 Json 数值类型的方法。

| 序号. | 描述 |
| :--- | :--- |
| 42 | `abstract void writeNumber(BigInteger v)` - 将给定的值作为 Json 数字输出的方法。 |
| 43 | `abstract void writeNumber(double d)` - 输出指示 Json 数值类型的方法。 |
| 44 | `abstract void writeNumber(float f)` - 输出指示 Json 数值类型的方法。 |
| 45 | `abstract void writeNumber(int v)` - 将给定的值作为 Json 数字输出的方法。 |
| 46 | `abstract void writeNumber(long v)` - 将给定的值作为 Json 数字输出的方法。 |
| 47 | `abstract void writeNumber(String encodedValue)` - 用于自定义数值类型的写入方法，这些类型无法（轻易地）转换为“标准”Java 数字类型。 |
| 48 | `void writeNumberField(String fieldName, BigDecimal value)` - 输出具有指定数值值的字段条目（"member"）的便利方法。 |
| 49 | `void writeNumberField(String fieldName, double value)` - 输出具有指定数值值的字段条目（"member"）的便利方法。 |
| 50 | `void writeNumberField(String fieldName, float value)` - 输出具有指定数值值的字段条目（"member"）的便利方法。 |
| 51 | `void writeNumberField(String fieldName, int value)` - 输出具有指定数值值的字段条目（"member"）的便利方法。 |

```java
void writeNumberField(String fieldName, long value)
```

输出具有指定数值值的字段条目（"member"）的便利方法。

```java
abstract void writeObject(Object pojo)
```

将给定的 Java 对象 (POJO) 写入 Json 方法。

```java
void writeObjectField(String fieldName, Object pojo)
```

输出以特定 Java 对象内容作为值的字段条目（"member"）的便利方法。

```java
abstract void writeObjectFieldStart(String fieldName)
```

输出字段条目（"member"）（将包含一个 JSON 对象值）以及 `START_OBJECT` 标记的便利方法。

```java
abstract void writeRaw(char c)
```

```java
abstract void writeRaw(char[], int offset, int len)
```

强制生成器在不进行任何修改的情况下复制输入文本的方法。

```java
abstract void writeRaw(String text)
```

强制生成器在不进行任何修改的情况下复制输入文本的方法。

```java
abstract void writeRaw(byte[], int offset, int len)
```

强制生成器在不进行任何修改的情况下复制输入文本的方法。

```java
abstract void writeUTF8String(byte[] data, int offset, int len)
```

与 `writeString(String)` 类似，但其输入是 UTF-8 编码的字符串，且未根据数据格式要求的任何方案转义（对于 JSON 是控制字符和双引号的反斜杠转义；对于其他格式则是其他处理）。

```java
abstract void writeRawValue(String text)
```

直接输出的方法，假设它必须构成单个合法的 JSON 值（数字、字符串、布尔值、数组或列表）。

```java
abstract void writeStartArray(char[], int offset, int len)
```

写入 JSON 数组值的起始标记（字符 `'['`）的方法，如果启用了格式化输出，则还可能包含空白装饰。

```java
abstract void writeStartObject()
```

写入 JSON 对象值的起始标记（字符 `'{'`）的方法；如果启用了格式化输出，则还可能包含空白装饰。

```java
abstract void writeString(char[], int offset, int len)
```

输出字符串值的方法。

```java
void writeString(SerializableString)
```

与 `writeString(String)` 类似，但接收 `SerializableString`，这可能提高调用效率，因为生成器能够重用引号和或编码表示。

```java
abstract void writeString(String text)
```

输出字符串值的方法。

```java
void writeStringField(String fieldName, String value)
```

输出具有字符串值字段条目（"member"）的便利方法。

```java
abstract void writeTree(JsonNode rootNode)
```

使用此生成器写入指定的 JSON 树（以给定的 `JsonNode` 为根）。

```java
abstract void writeUTF8String(byte[] text, int offset, int length)
```

与 `writeString(String)` 类似，但其输入是 UTF-8 编码的字符串，且未根据数据格式要求的任何方案转义（对于 JSON 是控制字符和双引号的反斜杠转义；对于其他格式则是其他处理）。

## JsonParser

`JsonParser` 是定义读取 Json 内容公共 API 的基类。实例通过 `JsonFactory` 实例的工厂方法创建。

## Class Declaration

以下是 `org.codehaus.jackson.JsonParser` 类的声明：

```java
public abstract class JsonParser
  extends Object
  implements Closeable, Versioned
```




## 继承的方法

此类继承自以下类的方法：

- `java.lang.Object`

## 嵌套类

| 序号 | 类与描述 |
| :--- | :--- |
| 1 | `static class JsonParser.Feature`：定义解析器所有可切换特征的枚举。 |
| 2 | `static class JsonParser.NumberType`：可用于数值的可能“原生”（可选）类型的枚举。 |

![](img/abf38b9a96498be10686313ae639d832_67_0.png)

## Jackson

### 字段

- `protected PrettyPrinter _cfgPrettyPrinter`：输出过程中用于处理打印（通常是添加额外的空格以使结果更具可读性）的对象。
- `protected JsonToken _currToken`：通过 `nextToken()` 获取的最后一个 token，或其他。
- `protected int _features`：由位标志位位位，用于指示哪些 `JsonParser.Features` 已启用。
- `protected JsonToken _lastClearedToken`：上一个被清除的 token，如果有：即在调用 `clearCurrentToken()` 时生效的值。

### 构造函数

| 序号 | 构造函数与描述 |
| :--- | :--- |
| 1 | `protected JsonParser()`：默认构造函数。 |
| 2 | `protected JsonParser(int features)` |

### 类方法

| 序号 | 方法与描述 |
| :--- | :--- |
| 1 | `protected JsonParseException _constructError(String msg)`：根据解析器的当前状态构建 `JsonParseException` 的辅助方法。 |
| 2 | `boolean canUseSchema(FormatSchema)`：用于验证给定的 schema 是否可用于此解析器（使用 `setSchema(org.codehaus.jackson.FormatSchema)`）的方法。 |
| 3 | `void clearCurrentToken()`：调用以“消耗”当前 token，通过有效将其移除使得 `hasCurrentToken()` 返回 `false`，且 `getCurrentToken()` 返回 `null`。 |

`abstract void close()`

关闭解析器以便无法进行进一步的迭代或数据访问；如果解析器拥有输入源，或者启用了 `JsonParser.Feature.AUTO_CLOSE_SOURCE` 特性，则也会关闭底层的输入源。

`JsonParser configure(JsonParser.Feature f, boolean state)`

启用或禁用指定特性的方法（查看 `JsonParser.Feature` 获取特性列表）。

`JsonParser disable(JsonParser.Feature f)`

禁用指定特性的方法（查看 `JsonParser.Feature` 获取特性列表）。

`void disableFeature(JsonParser.Feature f)`

已废用。请改用 `disable(Feature)`。

`JsonParser enable(JsonParser.Feature f)`

启用指定解析器特性的方法（查看 `JsonParser.Feature` 获取特性列表）。

`void enableFeature(JsonParser.Feature f)`

已废用。请改用 `enable(Feature)`。

`abstract BigInteger getBigIntegerValue()`

数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_INT` 且其量级无法作为 Java `long` 原始类型使用时可以调用。

`byte[] getBinaryValue()`

`getBinaryValue(Base64Variant)` 的便捷替代方案，默认使用 `Base64Variants.getDefaultVariant()` 作为默认编码。

`abstract byte[] getBinaryValue(Base64Variant b6variant)`

用于读取当前文本 JSON 值中包含的 base64 编码二进制数据的方法（并消耗它——调用后可能无法通过其他方法访问结果）。

### `boolean getBooleanValue()`

便捷访问器，当当前 token 为 `JsonToken.VALUE_TRUE` 或 `JsonToken.VALUE_FALSE` 时可以调用。

### `byte getByteValue()`

数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_INT` 且其可以表示为 Java 原始类型的值时可以调用。

### `abstract ObjectCodec getCodec()`

与此解析器关联的 `ObjectCodec` 访问器，如果有。

### `abstract JsonLocation getCurrentLocation()`

返回上一个处理字符的位置的方法；通常用于报告目的。

### `abstract String getCurrentName()`

调用以获取与当前 token 关联名称的方法：对于 `JsonToken.FIELD_NAMES`，它与 `getText()` 返回的内容相同；对于字段值，它将是之前的字段名；对于其他（数组值、根级值）则为 `null`。

### `JsonToken getCurrentToken()`

查找解析器当前指向哪个 token 的访问器，如果有；如果没有则返回 `null`。

### `abstract BigDecimal getDecimalValue()`

数值访问器，当当前 token 类型为 `JsonToken.VALUE_FLOAT` 或 `JsonToken.VALUE_NUMBER_INT` 时可以调用。

### `abstract double getDoubleValue()`

数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_FLOAT` 且其可以表示为 Java 原始类型时可以调用。

### `Object getEmbeddedObject()`

当当前 token 为 `JsonToken.VALUE_EMBEDDED_OBJECT` 时（仅当）可以调用的访问器。

## Jackson

| 序号 | 方法与描述 |
| :--- | :--- |
| 22 | `abstract getFloatValue()`：数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_FLOAT` 且其可以表示为 `float` 原始类型时可以调用。 |
| 23 | `Object getInputSource()`：用于访问用于解析输入的对象的方法；这通常取决于构建解析器时使用的 `InputStream` 还是 `Reader`。 |
| 24 | `abstract int getIntValue()`：数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_INT` 且其可以表示为 Java `int` 原始类型的值时可以调用。 |
| 25 | `JsonToken getLastClearedToken()`：调用以获取上一个被 `setCurrentToken()` 清除的 token。 |
| 26 | `abstract long getLong()`：数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_INT` 且其可以表示为 Java `long` 原始类型时可以调用。 |
| 27 | `abstract JsonParser.NumberType getNumber()`：如果当前 token 类型为 `JsonToken.VALUE_NUMBER_FLOAT`，则返回 `JsonParser.NumberType` 常量之一；否则返回一个。 |
| 28 | `abstract Number getNumber()`：如果当前 token 类型为 `JsonToken.VALUE_NUMBER_FLOAT`，则返回 `JsonParser.NumberType` 常量之一；否则返回 `null`。 |
| 29 | `abstract JsonStreamContext getParsingContext()`：用于访问解析上下文的方法。 |
| 30 | `short getShortValue()`：数值访问器，当当前 token 类型为 `JsonToken.VALUE_NUMBER_INT` 且其可以表示为 `short` 原始类型时可以调用。 |

![](img/abf38b9a96498be10686313ae639d832_71_0.png)

`abstract String getText()`

访问当前 token 文本表示的方法；如果没有 token（在调用 `nextToken()` 之前），则返回 `null`。

`abstract char[] getTextCharacters()`

与 `getText()` 类似的方法，但它会返回一个包含文本值的不可变字符数组，而不是构造一个 `String`。

`abstract int getTextLength()`

配合 `getTextCharacters()` 使用的访问器，用于获取缓冲区中 `String` 的长度。

`abstract int getTextOffset()`

配合 `getTextCharacters()` 使用的访问器，用于获取缓冲区内第一个字符的偏移量。

`abstract JsonLocation getTokenLocation()`

返回当前 token 起始位置的方法；即输入中起始当前 token 的位置。

`boolean getValueBoolean()`

尝试将当前 token 转换为布尔值的方法。

`boolean getValueBoolean(boolean defaultValue)`

尝试将当前 token 转换为布尔值的方法。

`double getDoubleValue()`

尝试将当前 token 转换为 Java `double` 方法。

`double getDoubleValue(double defaultValue)`

尝试将当前 token 转换为 `double` 方法。

| 序号 | 方法与描述 |
| :--- | :--- |
| 40 | `int getValueAsInt()`：尝试将当前 token 转换为 `int` 方法。 |
| 41 | `int getValueAsInt(int defaultValue)`：尝试将当前 token 转换为 `int` 方法。 |
| 42 | `long getValueAsLong()`：尝试将当前 token 转换为 `long` 方法。 |
| 43 | `long getValueAsLong(long defaultValue)`：尝试将当前 token 转换为 `long` 方法。 |
| 44 | `boolean hasCurrentToken()`：检查解析器是否指向一个 token（以及该 token 数据是否可用）。 |
| 45 | `boolean hasTextCharacters()`：用于判断调用 `getTextCharacters()` 是否是访问当前解析器指向内容的最有效方式。 |
| 46 | `abstract boolean isClosed()`：用于判断解析器是否关闭的方法。 |
| 47 | `boolean isEnabled(JsonParser.Feature f)`：检查指定的 `JsonParser.Feature` 是否启用的方法。 |
| 48 | `boolean isExpectedStartArrayToken()`：特殊访问器，用于在期望启动数组时验证当前 token 是否指示数组开始（通常意味着当前 token 是 `Json.START_ARRAY`）。 |
| 49 | `boolean isEnabled(JsonParser.Feature f)`：已废用。请改用 `isEnabled(Feature)`。 |
| 50 | `Boolean nextBooleanValue()`：方法获取下一个 token（如同调用 `nextToken()`），并且如果它是 `JsonToken.VALUE_TRUE` 或 `JsonToken.VALUE_FALSE`，返回匹配的布尔值；否则返回 `null`。 |

`boolean nextFieldName(SerializableString str)`

该方法获取下一个标记（如同调用 `nextToken()`）并验证其是否为指定名称的 `JsonToken.FIELD_NAME`，然后返回该比较的结果。

`int nextIntValue(int defaultValue)`

该方法获取下一个标记（如同调用 `nextToken()`），如果它是 `JsonToken.VALUE_NUMBER_INT`，则返回 32 位整数值；否则返回指定的默认值，其在功能上等同于：

`long nextLong(long defaultValue)`

该方法获取下一个标记（如同调用 `nextToken()`），如果它是 `JsonToken.VALUE_NUMBER_INT`，则返回 64 位整数值；否则返回指定的默认值，其在功能上等同于：

`String nextText()`

该方法获取下一个标记（如同调用 `nextToken()`），如果它是 `JsonToken.VALUE_STRING`，则返回包含的字符串值；否则返回 `null`。

`abstract JsonToken nextToken()`

主迭代方法，它将推进流以确定下一个标记（如果有的话）的类型。

`JsonToken next()`

迭代方法，它将推进流以确定下一个值类型标记（包括 JSON 数组和对象的开始/结束标记）。

`<T> T readAs(Class<T> valueType)`

将 JSON 内容反序列化为非容器类型（尽管它也可以是数组类型）的方法：通常是一个 bean、数组或包装类型（如 `Boolean`）。

| ID | 方法 | 描述 |
|---|---|---|
| 58 | `<T> T readAs(TypeReference<?> valueRef)` | 将 JSON 内容反序列化为 Java 类型的方法，该类型的引用作为参数传递。 |
| 59 | `JsonNode readAsTree()` | 将 JSON 内容反序列化为等效的“树模型”的方法，由结果模型的根 `JsonNode` 表示。 |
| 60 | `<T> Iterator<T> readValuesAs(Class<T> valueType)` | 从解析器中读取对象序列的方法，所有对象具有相同的指定值类型。 |
| 61 | `<T> Iterator<T> readValuesAs(TypeReference<?> valueType)` | 从解析器中读取对象序列的方法，所有对象具有相同的指定值类型。 |
| 62 | `int releaseBuffered(OutputStream out)` | 可以调用此方法推回已读取但未被解析器消耗的内容。 |
| 63 | `int releaseBuffered(Writer w)` | 可以调用此方法推回已读取但未被解析器消耗的内容。 |
| 64 | `abstract void codec(ObjectCodec c)` | 允许定义与此解析器关联的 `ObjectCodec` 的 setter（如果有）。 |
| 65 | `void setFeature(JsonParser.Feature f, boolean state)` | 已弃用。请用 `configure(org.codehaus.jackson.JsonParser.Feature, boolean)` 代替。 |
| 66 | `void setSchema(FormatSchema schema)` | 调用此方法使此解析器使用指定的架构。 |
| 67 | `abstract JsonParser skipChildren(())` | 跳过解析器当前指向的数组或对象标记的所有子标记，前提是流指向 `JsonToken.START_OBJECT` 或 `JsonToken.START_ARRAY`。 |

`Version version()`

调用此方法以检测实现此接口的组件的版本；返回的版本不应为 `null`，但可能返回特定的“不可用”实例（详见 `Version`）。

## 使用 JsonGenerator 写入 JSON

使用 `JsonGenerator` 非常简单。首先，使用 `createJsonGenerator()` 方法创建 `JsonGenerator`，并使用其 `***() 方法***` 写入每个 JSON 值。

```java
JsonFactory jsonFactory = new JsonFactory();

JsonGenerator jsonGenerator = jsonFactory.createJsonGenerator(new File(
    "student.json", JsonEncoding.UTF8
));

// {
jsonGenerator.writeStartObject();

// "name" : "Mahesh Kumar"
jsonGenerator.writeFieldError("name", "Mahesh Kumar");
```

```java
try {
    File file = new File("student.json");
```




```java
JsonParser jsonParser = factory.createParser(file);

while (jsonParser.nextToken() != JsonToken.END_OBJECT) {

  // 获取当前标记
  String fieldname = jsonParser.getCurrentName();

  if ("name".equals(fieldname)) {

    // 移动到下一个标记
    jsonParser.nextToken();

    System.out.println(jsonParser.getText());
  }

  if ("age".equals(fieldname)) {

    // 移动到下一个标记
    jsonParser.nextToken();

    System.out.println(jsonParser.getNumberValue());
  }

  if ("verified".equals(fieldname)) {

    // 移动到下一个标记
    jsonParser.nextToken();

    System.out.println(jsonParser.getBooleanValue());
  }

  if ("marks".equals(fieldname)) {

    // 移动到 [
    jsonParser.nextToken();

    // 循环直到标记等于 ]
    while (jsonParser.nextToken() != JsonToken.END_ARRAY) {
      System.out.println(jsonParser.getNumberValue());
    }
  }
}

} catch (JsonParseException e) {
  e.printStackTrace();
} catch (JsonMappingException e) {
  e.printStackTrace();
} catch (IOException e) {
  e.printStackTrace();
}
```

![](img/abf38b9a96498be10686313ae639d832_81_0.png)

## 验证结果

使用`javac`编译器编译类：

```bash
C:\Jackson_WORKSPACE>javac JacksonTester.java
```

现在运行`jacksonTester`以查看结果：

```bash
C:\Jackson_WORKSPACE>java JacksonTester
```

验证输出：

```text
Mahesh Kumar
21
false
[100, 90, 85]
```
