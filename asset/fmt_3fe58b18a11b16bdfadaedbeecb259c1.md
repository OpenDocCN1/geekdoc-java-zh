
记录枚举定义了一个记录类型，其中有一个唯一字段专门用于提供枚举字面量，以及该类型的一组固定记录列表。通常，记录是由一组字段定义（以原始数据类型属性的形式）定义的，其中其中一个唯一字段被定义为枚举字面量字段，以及一组操作定义。

不幸的是，记录枚举作为枚举数据类型的通用形式，尚未被当前的 UML (2.5) 支持，而该版本支持枚举数据类型的通用形式。然而，我们可以通过使用包含枚举类型属性的类来对它们进行建模。

### 10.1.4 可扩展枚举

可能存在需要扩展的枚举情况，例如可以向列表中添加新值，如图 10.1 所示。由于枚举被用作枚举属性的范围，因此它们被视为数据类型。

> 1 http://en.wikipedia.org/wiki/Enumerated_type

## 10.3 计算语言中的枚举 (Enumerations)

信息建模语言（如 UML 类图）、数据模式定义语言（如 XML Schema，但 SQL 不支持）以及许多编程语言（如 C++ 和 Java，但 JavaScript 不支持原生枚举）都直接支持对枚举的定义。

### 10.3.1 SQL 中的枚举

遗憾的是，标准 SQL 不支持枚举。某些数据库系统（如 MySQL 和 Postgres）在 `CREATE TABLE` 语句中提供了其自己的 SQL 列定义扩展，允许定义枚举值的列。

MySQL 枚举²被指定为列定义中使用 `ENUM` 关键字列出的枚举标签列表，如下所示：

```sql
CREATE TABLE people (
  name VARCHAR(40),
  gender ENUM('MALE','FEMALE', 'UNDETERMINED')
);
```

Postgres 枚举³被指定为一种特殊的用户定义类型，可以用于列定义：

```sql
CREATE TYPE GenderEL AS ENUM ('MALE','FEMALE', 'UNDETERMINED');
CREATE TABLE people (
  name text,
  gender GenderEL
);
```

### 10.3.2 XML Schema 中的枚举

在 XML Schema 中，枚举数据类型可以定义为一个简单类型，通过如下方式对原始类型 `xs:string` 进行限制：

```xml
<xs:simpleType name="BookCategoryEL">
  <xs:restriction base="xs:string">
    <xs:enumeration value="NOVEL"/>
    <xs:enumeration value="BIOGRAPHY"/>
    <xs:enumeration value="TEXTBOOK"/>
  </xs:restriction>
```

² https://dev.mysql.com/doc/refman/5.7/en/enum.html

3 http://postgresguide.com/sexy/enums.html

```xml
<xs:enumeration value="OTHER"/>
<xs:restriction>
<xs:simpleType>
```

### 10.3.3 JavaScript 中的枚举

在 JavaScript 中，我们可以定义一个特殊的 JS 对象，为每个枚举字面量设置属性，使得属性名称为枚举字面量的名称（枚举标签或大写），其值为相应的索引。实现这种方法的方法是使用 `Object.defineProperties` 方法：

这种定义允许在程序语句中使用枚举 `BookCategoryEL.NOVEL`、`BookCategoryEL.BIOGRAPHY` 等，代表枚举索引 1, 2, 3 和 4。注意这种定义如何满足枚举字面量（如 `BookCategoryEL.NOVEL`）是常量且其值在程序执行期间不能更改的要求。这是通过 `Object.defineProperties` 方法中的属性描述符 `writable: false` 实现的。

我们还可以使用一种更通用的方法，以特殊 JS 对象的格式定义一个元类 `Enumeration`：

```javascript
function Enumeration (enumLabels) {
  var i=0, LBL=""; this.MAX = enumLabels.length;
  this.labels = enumLabels;
  // 生成大写的键/属性作为枚举字面量
  for (i=1; i <= enumLabels.length; i++) {
    LBL = enumLabels[i-1].toUpperCase();
    this[LBL] = i;
  }
  // 防止对枚举进行任何更改
  Object.freeze(this);
}
```

## 10 枚举与枚举属性

使用这个 `Enumeration` 类可以如下方式定义新的枚举：

```javascript
var BookCategoryEL = new Enumeration({"novel","biography","textbook","other"});
```

拥有枚举 `BookCategoryEL` 后，我们就可以通过测试其值是否小于 1 且不大于 `BookCategoryEL.MAX`，来检查枚举属性（如 `category`）是否具有允许的值。此外，可以通过以下方式获取标签：

```javascript
formEL.category.value = BookCategoryEL.labels[this.category -1];
```

作为一个示例，我们考虑以下带有枚举属性 `category` 的 `Book` 模型：

```javascript
function Book(slots) {
  this.isbn = ""; // string
  this.title = ""; // string
  this.category = 0; // number (BookCategoryEL)
  if (arguments.length > 0) {
    this.setIsbn(slots.isbn);
    this.setTitle(slots.title);
    this.setCategory(slots.category);
  }
}
```

为了对枚举属性 `category` 的输入值验证，我们可以使用以下函数：

```javascript
Book.checkCategory = function (c) {
  if (!c) {
    return new MandatoryInputValueViolation(
      "A category must be provided!");
  } else if (!Number.IsInteger(c) || c < 1 ||
    c > BookCategoryEL.MAX) {
    return new RangeConstraintViolation(
      "The category must be a positive integer " +
      "not greater than " + BookCategoryEL.MAX + " !"
    );
  } else {
    return new NoConstraintViolation();
  }
}
```

注意枚举 `BookCategoryEL` 定义的约束是如何被检查的：测试输入值 `c` 是否为正整数，以及它是否不大于 `BookCategoryEL.MAX`。

## 10.4 在设计模型中处理枚举属性

我们再次考虑之前考虑过的简单数据管理问题。因此，我们应用程序的目的仍然是管理书籍信息。但现在我们有了四个额外的枚举属性，如下图 10.2 中的 UML 类图所示：

- 单值必填属性 `originalLanguage`，其数据类型为枚举；

- 多值可选属性 `otherLanguages`，其数据类型为枚举；

- 单值必填属性 `category`，其数据类型为枚举；

- 多值必填属性 `publicationForms`，其数据类型为枚举。

| «invariant> | {isbn 为 10 位字符串或 9 位字符串} |

|---|---|

| Book | |

| isbn[1]: EmptyString(id) | |

| title[1]: EmptyString(50) | |

| originalLanguage[1]: LanguageEL | |

| otherLanguages[*]: LanguageEL | |

| category[1]: BookCategoryEL | |

| publicationForms[1..]: LanguageEL | {year > 0 and nextYear()} |

| LanguageEL | |

| BookCategoryEL | |

| en = English | |

| de = German | |

| fr = French | |

| es = Spanish | |

| novel textbook other | «enumeration> |

| PublicationFormEL | |

| hardcover | |

| paperback | |

图 10.2 设计模型

注意 `otherLanguages` 和 `publicationForms` 是多值的，正如 `[*]` 和 `[1..]` 所示。这意味着属性的值是枚举字面量集合，例如 `{ePub, PDF}`，在 JavaScript 中表示表示枚举字面量数组，如 `[PublicationFormEL.EPUB, PublicationFormEL.PDF]`。

该设计模型及其枚举属性含义可以通过示例数据填充所示：

| ISBN | 标题 | 原始语言 | 其他语言 | 类别 | 出版形式 |

|---|---|---|---|---|---|

| 0553345842 | The Mind's | English (en) | de, es, fr | novel | paperback, ePub, PDF |

| 1463794762 | The Critique of Pure Reason | German (de) | de, es, fr, ru | other | paperback, PDF |

| 1928565379 | The Critique of Practical Reason | German (de) | de, es, fr, ru | other | paperback |

| 0465030793 | A Strange Loop | English (en) | es | textbook | hardcover, ePub |

表 10.2 Book 的示例数据

## 10.5 测试题

如果你想查看以下测试题的答案，可以查看我们的论坛。如果你在论坛中没有找到，可以发帖询问特定问题的答案。

### 10.5.1 问题 1：支持枚举的语言

哪些语言通过提供定义枚举的结构构造直接支持枚举？单选或多：

- Java

- JavaScript

- UML 类图

- C++

- XML Schema

- SQL

### 10.5.2 问题 2：单值枚举属性的 UI 控件

以下（组合）HTML 元素可以作为单值枚举属性的表单控件（或 UI 控件）？单选或多：

- 包含多个相同名称单选框的 `fieldset` 元素

- 包含多个相同名称复选框的 `fieldset` 元素

- `select` 元素

- 复选框元素

- 单选框元素

## 10.5.3 问题 3：多值枚举属性的 UI 组件

以下哪些 HTML 元素（或组合）可以作为多值枚举属性的表单控件（或 UI 组件）？选择一个或多个：

- 设置了 `multiple="multiple"` 属性的 `select` 元素

- 包含多个具有相同名称的 `radio`（单选）元素的 `fieldset` 元素

- 包含多个具有相同名称的 `checkbox`（复选）元素的 `fieldset` 元素

- `checkbox` 元素

- `radio`（单选）元素

## 11 在原生 JS Web 应用中实现枚举属性

在本章中，我们将展示如何使用原生 JavaScript 构建一个带有**枚举属性**的前端应用程序。除了枚举属性主题外，我们还展示了如何处理**多值属性**，因为在许多情况下，枚举属性是多值的。

## 11.1 新问题

与第 2 部分讨论的验证应用¹ 相比，我们现在要处理以下新问题：

- 我们将基于 ES5 构造函数的模型类 `Book` 定义替换为相应的 ES6 `class` 定义。

- 我们不再定义显式的设置器（setters），而是利用 ES5 属性的隐式 `get/set` 方法功能。

- 枚举数据类型必须作为模型代码的一部分以适当的方式定义。

- 枚举属性必须在模型类中定义，并在合适的选择组件的帮助下在用户界面中处理。

在编码方面，新问题是：

- 在**模型代码**中，我们必须处理：

- 为 `Book` 定义一个 ES6 `class` 而不是构造函数（带有其 `prototype` 对象的额外槽位）；

- 为 `Book` 类定义中的所有属性定义 `get/set` 方法；

- 借助工具类（元类）`Enumeration-` 来定义**枚举**，该类将在下文中讨论；

- 定义**单值枚举属性** `originalLanguage` 和 `category`，以及它们的检查函数 `checkOriginalLanguage` 和 `checkCategory`；

- 定义**多值枚举属性** `AvailableLanguages` 和 `publicationForms`，以及它们的检查函数 `checkAvailableLanguages` 和 `checkPublicationForms`；

- 扩展方法 `Book.update` 和 `Book.prototype.toString`，以便它们能够处理新增的枚举属性。

## 11.2 创建 JavaScript 类模型

2. 在用户界面（“视图”）代码中，我们必须处理：

- a. 在 `retrieveAllListBooks.html` 中添加新表格列，并在 `createBook.html` 和 `updateBook.html` 中添加合适的选择组件；

- b. 在 `p.v.retrieveAndListAllBooks` 的 `setupUserInterface()` 方法中为新属性创建输出；

- c. 在 `p.v.createBook` 和 `p.v.updateBook` 的 `setupUserInterface()` 方法中允许为新属性输入。

## 11.2 创建 JavaScript 类模型

以图 10.2 所示的信息设计模型为起点，我们创建一个 JavaScript 模型，本质上是通过给属性打上 "get/set" 构型（意味着它们具有隐式的 getter 和 setter）并添加（类级别的）检查方法来实现：

```
«invariant>
{isbn 必须是一个 10 位字符串
或是 9 位字符串后跟一个 "X"}
```

| Book |

| :--- |

| <get/set> isbn[1] : NonEmptyString(id) |

| <get/set> title[1] : NonEmptyString(50) |

| <get/set> originalLanguage[1] : LanguageEL |

| <get/set> otherAvailableLanguages[*] : LanguageEL |

| <get/set> category[1] : BookCategory |

| <get/set> publicationForm[*] : PublicationForm |

| checkISBN(String) : ConstraintViolation |

| checkISBNId(in String) : ConstraintViolation |

| checkTitle(in String) : ConstraintViolation |

| checkOriginalLanguage(in : LanguageEL) : ConstraintViolation |

| checkAvailableLanguage(in : LanguageEL) : ConstraintViolation |

| checkAvailableLanguages(in : array(LanguageEL)) : ConstraintViolation |

| checkBookCategory(in String) : ConstraintViolation |

| checkPublicationForm(in pf : PublicationForm) : ConstraintViolation |

| checkPublicationForms(in pf : array(PublicationForm)) : ConstraintViolation |

图 11.1 Book 的类模型

注意，模型中的 "get/set" 构型显示，对于任何多值枚举属性，我们都添加了类级别的检查方法。（注：原文此处存在大量重复，已根据结构进行了清理。）

## 11 在原生 JS Web 应用中实现枚举属性

在本章中，我们将展示如何使用原生 JavaScript 构建一个带有**枚举属性**的前端应用程序。除了枚举属性主题外，我们还展示了如何处理**多值属性**，因为在许多情况下，枚举属性是多值的。

## 11.1 新问题

与第 2 部分讨论的验证应用¹ 相比，我们现在要处理以下新问题：

- 我们将基于 ES5 构造函数的模型类 `Book` 定义替换为相应的 ES6 `class` 定义。

- 我们不再定义显式的设置器（setters），而是利用 ES5 属性的隐式 `get/set` 方法功能。
