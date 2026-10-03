
JSF `h:selectMenu` 允许通过 HTML 元素 `<f:selectItems value="#{book.languageItems}" />` 创建单选列表。使用表达式 `#{book.languageItems}` 会导致调用 `book` 对象的 `getLanguageItems()` 方法。该方法返回 `SelectItem` 对象的集合，用于填充选择列表。对应的方法如下：

## 220 在 Java EE 中实现枚举属性

```java
public SelectItem[] getLanguageItems() {
    SelectItem[] items = new SelectItem[LanguageEL.values().length];
    int i = 0;
    for (LanguageEL lang : LanguageEL.values()) {
        items[i++] = new SelectItem(lang.name(), lang.getLabel());
    }
    return items;
}
```

多选列表对应于 HTML 元素 `<select multiple="multiple" .../>`，通过 JSF 元素 `h:selectManybox` 创建，并使用相同的 `getLanguageItems` 方法来获取选择列表。

## 12.4.2 单选按钮组和复选框组

由于枚举属性 `category` 和 `publicationForms` 的可能值不超过七个，我们可以使用单选按钮组和复选框来渲染它们：

```xml
<ui:composition template="WEB-INF/templates/page.xhtml">
  ...
  <ui:define name="main">
    <h:form id="createBookForm">
      <div>
        <h:outputLabel for="category" value="分类" />
        <h:selectRadio id="category" value="#{book.category}">
          <f:selectItems value="#{book.categoryItems}" />
        </h:selectRadio>
        <h:message for="category" errorClass="error" />
      </div>
      <div>
        <h:outputLabel for="publicationForms" value="出版形式" />
        <h:selectManyCheckbox id="publicationForms" value="#{book.publicationForms}">
          <f:selectItems value="#{book.publicationForms}" />
        </h:selectManyCheckbox>
        <h:message for="publicationForms" errorClass="error" />
      </div>
      <div>
        <h:commandButton value="保存"
          action="#{bookCtrl.create(book.isbn, book.title, book.year, book.originalLanguage, book.otherAvailableLanguages, book.category, book.publicationForms)}" />
      </div>
    </h:form>
  </ui:define>
</ui:composition>
```

## 12.5 显示多值枚举属性的值集

单选按钮组通过 JSF 元素 `h:selectOneRadio` 渲染 `<input type="radio" />` 元素获得。使用与选择列表相同的技术，单选按钮组用 `SelectItem` 对象的集合填充。`Book` 类中对应的 `getCategoryItems` 方法与 `getLanguageItems` 类似。

复选框组由 `<input type="checkbox" />` 元素组成，通过 JSF 元素 `h:selectManyCheckbox` 创建，并以与单选按钮组或选择列表相同的方式填充。

对于多值属性（如 `otherAvailableLanguages` 或 `publicationForms`），检索/列表视图必须以逗号分隔列表的形式显示值，例如“英语、德语、西班牙语”，如下表所示：

| ISBN | 标题 | 年份 | 原始语言 | 其他可用语言 | 分类 | 出版形式 |
|---|---|---|---|---|---|---|
| 00625187X | 编织万网 | 2000 | 英语 | 德语, 法语 | 教科书 | pdf |
| 046502657 | Gödel, Escher, Bach | 1999 | 法语 | | 硬装 | 平装本 |
| 0465030793 | 奇异性循环 | 2008 | 西班牙语 | 英语, 德语 | | epub |

为了此目的，我们定义一个方法来创建多值属性的序列化，并将其用于 `WebContent/views/listAll`。对于出版形式属性，该方法如下：

```java
public String getPublicationForms() {
  String result = "";
  if (publicationForms != null) {
    for (PublicationEL pf : publicationForms) {
      if (i > 0) result += ", ";
      result += pf.name().toLowerCase();
      i++;
    }
  }
}
```

注意在 `publicationForms` 属性的情况下，底层枚举 `PublicationEL` 没有标签。相反，我们使用枚举字面量作为标签。

## 12.6 运行应用并获取代码

您可以在我们的服务器上运行枚举应用程序，或以 ZIP 格式下载代码。

## 12.7 练习项目

在以下练习项目中，首先列出在该模型中定义的所有约束。然后按照第 9 章的指南定义实体类并开始编写应用程序。如果您对执行后续项目有任何疑问，可以在我们的论坛上提问。

### 12.7.1 项目 1 – 添加评分和类型作为枚举属性

要构建的应用程序目的是管理电影信息。该程序处理一个对象类型 `Movie` 以及两个枚举，如类图所示。

| Movie | «enumeration» GenreEL | «enumeration» MovieRatingEL |
|---|---|---|
| movieid[1] : PositiveInteger {id} | 动作 | G = 全级级 |
| title[1] : NonEmptyString | 动画 | PG = 家长指导 |
| rating[0..1] : MovieRatingEL | 喜剧 | PG13 = 13 岁以下 |
| genres[1.*] : GenreEL | 纪录片 | R = 受限制 |
| | 剧情 | NC17 = 17 岁以下 |
| | 家庭 | |
| | 黑色电影 | |
| | 恐怖 | |
| | 音乐 | |
| | 浪漫 | |
| | ... | |

您可以使用表 11.1 所示的示例数据来测试您的应用程序。

### 12.7.2 项目 2 – 添加国家代码和关系作为枚举

应用程序的目的是管理国家关系。该程序处理一个对象类型 `Country` 以及两个枚举，如类图所示。

| Country | «enumeration» CountryCodeEL | «enumeration» ReligionEL |
|---|---|---|
| name[1] : NonEmptyString {id} | DE = 德国 | 天主教 |
| code[1] : CountryCodeEL {key} | FR = 法国 | 新教 |
| population[1] : PositiveInteger | RU = 俄罗斯 | 正教 |
| lifeExpectancy[0..1] : PositiveDecimal(max:100) | MC = 摩纳 | 印度教 |
| relions[]* : ReligionEL | IN = 印度 | 伊斯兰教 |
| | | 犹太教 |

与您的验证教程练习项目相比，增加了两个属性：单值枚举属性 `code`（这是一个“键”属性，意味着唯一性约束）以及多值枚举属性 `relations`。

## 12.8 测验题

如果你想查找以下测试题答案，可以查看我们的讨论论坛。如果你在论坛中没有找到答案，可以创建一个帖子来提问特定问题的答案。

### 12.8.1 问题 1：JPA 自定义转换器实现类

补全以下 JPA 自定义转换代码，将类型为 `List<GenreEL>` 的值序列化为 `String`：

```java
@Converter
public class GenreConverter implements AttributeConverter<List<GenreEL>, String>
{
    @Override
    public String convertToDatabaseColumn(List<GenreEL> attributeValue) { ... }
}
```

### 12.8.2 问题 2：枚举属性的基数约束

完成 `languages` 属性的定义，至少需要三个语言。

```java
@Entity
class Book {
    private Set<Languages> languages;
}
```

### 12.8.3 问题 3：JPA 枚举属性序列化注解

使用适当的 JPA 注解（包括参数），使泛型属性的值序列化并存储枚举字面量名称（即作为 `String`），而不是序数值（索引）：

```java
@Entity
public class Book {
    @Enumerated(EnumType.STRING)
    @Size(message="A genre is required!")
    @NotNull
    private GenreEL genre;
    ...
}
```

### 12.8.4 问题 4：JSF 单值枚举属性

以下哪项是用于渲染单值枚举属性选择组件的 JSF 元素名称？

- 1. `selectOneRadio`
- 2. `selectOnlyOne`
- 3. `radioGroup`
- 4. `radioSelect`

### 12.8.5 问题 5：JSF 多值枚举属性

补全以下 facet（部分）代码，使得创建创建 `Book` 实例时，生成的 HTML 代码包含一个允许选择多种语言的复选框：

```html
<h:form id="createBookForm">
...
<h:outputLabel for="languages" value="Select languages " />
<h:selectMultipleCheckbox
  id="languages" value="#{book.languages}">
  <f:selectItems value="#{book.languageItems}" />
</h:selectMultipleCheckbox>
...
</h:form>
```

# IV 特殊数据类型与派生属性

除了标准的数值和字符串数据值外，特殊属性可能具有几种类型的特殊数据值，例如日历日期或数量（如时间或金额），或记录等复合值。某些属性是从其他属性派生的。

# 13 特殊数据类型

在应用程序中，我们必须处理各种类型的属性。虽然许多属性的标准类型是范围（如 `Integer` 或 `String`），但某些属性根据其范围具有特殊的数据类型。例如，通用业务语言（UBL）是一种定义电子商务文档格式的行业标准，它定义了大量的业务数据类型，包括以下内容。

| UBL 数据类型 | 描述 |
| --- | --- |
| Date Time | 根据格里哥日历的一个日。每天发生的时间实例。 |
| DateTime | 时间进程中的某个特定点，以及相关的补充信息。 |
| Percent | 通过计算、计数、排序分配或确定的数值信息，以百分比形式表示。 |
| Amount | 使用给定货币单位指定的货币数量。 |

SemanticWiki 使用以下特殊数据类型。

| SemanticWiki 数据类型 | 描述 |
| --- | --- |
| Geographic coordinate | 存储描述地理位置的坐标 |
| Monolingual text | 将文本值与特定的语言代码关联 |
| Quantity | 存储描述数量的值，包含数字和单位 |
| Record | 允许保存复合属性值，该值由具有固定类型的短值列表组成 |
| Email | 存储电子邮件地址 |
| URL | 存储 URIs、URNs 和 URLs |
| Telephone number | 存储基于 RFC 3962* 的国际电话号码 |

我们讨论了特殊数据类型的几种重要用例，以及如何在模型代码和 HTML 用户界面代码中处理它们。以下类图说明了具有此类特殊数据类型作为范围的属性示例。

在 C++ 和 C# 编程社区中，字符串模式和变体等特殊数据类型也被称为“语义类型”（semantic types）（例如参见 Gibson2016 和 Perkins2015*）。

- 1 https://www.semantic-mediata.org/wiki/Help:List_of_datatypes
- 2 https://tools.ietf.org/html/rfc3966
- 3 https://stackoverflow.com/a/3941703/2799509
- 4 https://www.codepject.com/Articles/860646/Introducing-Semantic-Types-in-Net

# 13.1 布尔值

布尔属性（如 `Smoker`）只能有两个可能值中的一个：`true` 或 `false`，有时用 `yes` 或 `no` 表达更自然。在模型代码中，布尔属性被处理为原始数据类型属性，因为所有编程语言都支持布尔作为原始数据类型。

在用户界面中渲染布尔属性有几个示例，其中最简单的解决方案是使用复选框字段。另一种方法可以使用单选器按钮。

```html
<h:form id="createBookForm">
...
<h:outputLabel for="languages" value="Select languages " />
<h:selectMultipleCheckbox
  id="languages" value="#{book.languages}">
  <f:selectItems value="#{book.languageItems}" />
</h:selectMultipleCheckbox>
...
</h:form>
```

# 13.2 字符串模式

电子邮件地址、URL 和电话号码是必须匹配模式的字符串示例。在数据/文档格式中对它们内置支持是理想的。

## 232 13 特殊数据类型

Diego Perini 脱颖而出，似乎是一个非常好的近似。一旦所有浏览器都支持新构建的 JavaScript 内置类型 `URL`，就可以通过尝试使用给定的 URL 字符串创建一个 `URL` 对象来实现精确的验证检查，然后捕获任何类型为 `SYNTAX_ERROR` 的 `DOMException`。

## 13.3 特殊数值数据类型

### 13.3.1 正整数和非负整数属性

由于正整数或非负整数属性很常见，因此优于使用预定义的属性（如 `PositiveInteger` 和 `NonNegativeInteger`）作为它们在信息设计模型中的范围，而不是通过定义范围为 `Integer` 并添加相应的区间约束来定义它们。

在（JavaScript 或 Java）模型类定义中，这些属性必须实现为带有区间约束的整数值属性。然而，具有对它们的内置支持是理想的，就像数据/文档格式语言 XML Schema 那样。

### 13.3.2 单位区间

某些属性（例如表示概率时）具有单位区间 `[0,1]` 或其开区间变体作为其范围。它们可以实现为带有区间约束的十进制属性。但拥有一个相应的预定义数据类型（如 `UnitInterval`）更为优。

### 13.3.3 百分比

某些属性的值代表百分比，这些小数必须除以 100 才能获得它们所表示的数值。在用户界面中，百分比属性的值带有 `%` 后缀显示，类似于量化属性，需要一个像 `Percent` 这样的特殊预定义数据类型。

8 https://gist.github.com/729294

### 13.3.4 任意精度数字

在广泛使用的编程语言（如 JavaScript 和 Java）中，处理小数的内置标准数据类型（如 JavaScript 中的 `number` 和 Java 中的 `double`）不支持精确计算。例如，在 JavaScript 中，计算减法 `0.3–0.1` 的结果不是 `0.2`，而是 `0.9999999999999`，这接近正确结果但并不相等。即使这种误差在游戏物理模拟等用例中是可以接受的，但在财务会计等用例中是不可接受的。

任意精度数字的概念是允许计算精度仅受可用内存限制，这与计算机算术逻辑单元中实现的固定精度算术不同，后者通常由编程语言的标准算术实现所采用。任意精度数字用于需要精确计算结果（即使是大数字）且计算速度不是关键因素的应用程序。

在 JavaScript 中，我们可以使用库 `big.js` 或 `mathjs`¹ 进行任意精度计算。例如，使用 `big.js` 库，可以通过以下方式获得减法 `0.3–0.1` 的精确结果：
