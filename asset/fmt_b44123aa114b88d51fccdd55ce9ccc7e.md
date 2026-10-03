
# 12.6.2 单表继承 (Single Table Inheritance)

## 12.6.2.1 单表继承 (Single Table Inheritance) 的 SQL 模型

```
invariant
{(category="TextBook" IFF subject_area IS NOT NULL)
(category="Biography" IFF about IS NOT NULL)}
```

**图 12.9:** 表示 `Book` 层次结构的单表 SQL 模型。

一种常见的方法是添加一个特殊的判别列来表示对象所对应的子类类别。该列通常是字符串值的，但受限于子类的名称之一。DBMS 支持枚举，它也可以是枚举值的。我们使用名称作为判别列，在我们的 `Book` 示例中，由于教科书-传记的分段是硬性的，它具有固定值约束。

根据书籍的类别，我们必须强制当且仅当它是 `"TextBook"` 时，其属性 `subjectArea` 有值，且当且仅当它是 `"Biography"` 时，其属性 `about` 有值。这个隐含约束在上面的类图中附加到 `Book` 类上表示，其中逻辑运算符 `IFF` 表示“当且仅当”。它需要在数据库中实现，例如使用 SQL 表 `CHECK` 子句或 SQL 触发器。

当给定的分割是不相交时，使用单值枚举类别来表示实例所属的子类信息。否则，如果是非相交的，则使用多值枚举类别来表示实例所属的子类信息。这种属性可以通过为相应的枚举代码或标签定义一个字符串值列在 SQL 中实现。

考虑图 12.8 中的类层次结构。在 `Employee`、`Manager` 和 `Author` 子类中定义了三个额外属性后，该类层次结构可以使用 STI 方法映射，如表 12.10 中的 SQL 表所示。

| | |
|---|---|
| `person_id[1]` | INTEGER (pkey) |
| `name[1]` | VARCHAR |
| `categories[*]` | VARCHAR (`"Employee"`, `"Manager"`, `"Author"`) |
| `emp_no[0..1]` | INTEGER (unique) |
| `biography[0..1]` | VARCHAR |
| `department[0..1]` | VARCHAR |

**图 12.10:** 表示 `Person` 层次结构的 STI 表。

注意，现在判别列 `categories` 是多值的，`Person` 的分割不是相交的，而是重叠的，这意味着 `Person` 对象可能属于多个类别。同样注意，由于角色分割（如 `Employee`、`Manager`、`Author`）不是硬性的，判别列 `categories` 没有固定值约束。

## 12.7 计算语言中的子类型化与继承

该模型的一个可接受种群示例如下：

| `person_id` | `name` | `categories` | `biography` | `emp_no` | `department` |
| --- | --- | --- | --- | --- | --- |
| 1001 | Harry Wagner | 作者，员工 | 1956年出生于马萨诸塞州波士顿，. . . | 21035 | |
| 1002 | Peter Boss | 经理 | | 23107 | Sales |
| 1003 | Tom Daniels | | | | |
| 1077 | Immanuel Kant | 作者 | 曼努埃尔·康德（1724–1804）是一位德国哲学家。. . . | | |

注意，`Person` 包含了四种不同类型的人：

1. 一个人，Harry Wagner，既是作者（有传记）又是员工（有员工编号）。
2. 一个人，Peter Boss，他是一个经理（员工的一种特殊类型），负责销售部。
3. 一个人，Tom Daniels，他既不是作者也不是员工。
4. 一个人，曼努埃尔·康德，他是一个作者（有传记）。

**STI 方法的优点：** 它能够忠实地表示原始类层次结构中表达的子类型关系；特别是，任何代表子类实例（员工、经理或作者）的行也代表一个父类实例（人）。

**缺点：** (1) 在多级类层次结构中，如果子类之间的共同点较少，STI 方法将无法导致良好的表示。(2) 给定类层次结构在各个元素（类）方面的结构仅被隐式地保留了。

### 12.7.4.2 每类继承表 (Table Per Class Inheritance)

在更真实的模型中，图 12.8 中 `Person` 的子类将拥有更多属性，因此 STI 方法将不再可行。TCI 方法将得到下图 12.11 所示的 SQL 表模型。TCI 模型将类层次结构中的每个具体类表示为一个表，使得每个子类都由一个包含继承属性列的表来表示，从而重复了表示父类的表的列。

| «SQL table» | «SQL table» |
| :--- | :--- |
| `people` | `employees` |
| `person_id` : INTEGER (pkey) | `person_id` : INTEGER (pkey) |
| `name` : VARCHAR | `name` : VARCHAR |
| | `emp_no` : INTEGER (unique) |
| «SQL table» | «SQL table» |
| `authors` | `managers` |
| `person_id` : INTEGER (pkey) | `person_id` : INTEGER (pkey) |
| `name` : VARCHAR | `name` : VARCHAR |
| `biography` : VARCHAR | `emp_no` : INTEGER (unique) |
| | `department` : VARCHAR |

**图 12.11：** 表示 `Person` 角色层次结构的 TCI 表模型。

通过执行以下步骤可以从信息设计模型导出 TCI 表：

1. 将所有类中的标准 ID 属性修符 `[id]` 替换为 `{pkey}`以指示标准 ID 属性为主键。
2. 将单数（大写）类名（`Person`, `Author`, 等）替换为复数小写表名（`people`, `authors`, 等），并将驼峰命名属性（`personId` 和 `empNo`）替换为小写下划线分隔列名（`personid` 和 `empno`）。
3. 为所有类矩形添加 `<table>` 刻型。
4. 将平台无关的数据类型名称替换为 SQL 数据类型名称。
5. 移除所有泛化/继承箭头，并将父表的所有列（如来自 `people` 的 `person_id` 和 `name`）添加到其子表（`authors` 和 `employees`）中。

每个表将只填充与所表示类的直接实例对应的行。该模型的一个可接受种群示例如下：

| `people` | |
| :--- | :--- |
| `personId` | `name` |
| 1003 | Tom Daniels |

| `authors` | | | |
| `person_id` | `name` | `biography` |
| 1001 | Harry Wagner | 1956年出生于马萨诸塞州波士顿，. . . |
| 1077 | Immanuel Kant | 曼努埃尔·康德（1724–1804）是一位德国哲学家。. . . |

| `person_id` | `name` | `emp_no` |
|---|---|--|
| 101 | Harry Wagner | 21035 |

`employees`

| `person_id` | `name` | `emp_no` | `department` |
|---|---|---|--|
| 1002 | Peter Boss | 23107 | Sales |

`managers`

**TCI 方法的优点：** (1) 给定类层次结构在各个元素（类）方面的结构被显式地表示。(2) 当给定类层次结构的划分互不相交时，TCI 会导致内存高效的冗冗存储。

**缺点：** (1) TCI 方法无法忠实地表示原始类层次结构中表达的子类型关系。特别是，对于任何代表子类（员工、经理或作者）的行，没有信息表明它代表一个父类（人）。因此，TCI 模式没有告知所表示的子类型；相反，保留在应用模型中的元信息与数据库解耦了。(2) TCI 方法需要重复列定义，这是一种模式冗余的形式。(3) 每当子类重叠时，TCI 方法可能会导致数据冗余。在我们的示例中，作者可以是员工，因此对于任何重叠的情况，我们需要复制父类的数据。

### 12.7.4.3 链接继承 (Joined Inheritance)

为了避免重叠情况下的数据冗余，我们采用图 12.12 所示的 JTI 方法，通过将子表（`subtables`）通过父类（`super`）的主键连接到父类（`superclasses`），并使用带有 «fk» 刻型标记的外键列来实现。

**图 12.12：** 表示 `Person` 角色的 JTI 模型。

该模型的一个可接受种群是：

| `person_id` | `name` |
| --- | --- |
| 1001 | Harry Wagner |
| 1002 | Peter Boss |
| 1003 | Tom Daniels |
| 1077 | Immanuel Kant |

| `person_id` | `biography` |
| --- | --- |
| 1001 | 1956年出生于马萨诸塞州波士顿，. . . |
| 1077 | 曼努埃尔·康德（1724–1804）是一位德国哲学家。. . . |

| `person_id` | `emp_no` |
| --- | --- |
| 1001 | 21035 |
| 1002 | 23107 |

| `person_id` | `department` |
| --- | --- |
| 1002 | Sales |

**JTI 方法的优点：** (1) 子类型关系被显式保留。(2) 避免了重叠情况下的数据冗余。

**缺点：** (1) JTI 方法的主要缺点是查询子类时需要连接（join），这可能会产生性能问题。

## 12.8 测验 (Quiz)

如果你想查看这些答案，可以查看我们的论坛。如果你不在论坛上找到答案，可以发帖询问。

### 12.8.1 问题1：关于类层次

考虑以下类模型：

| `Abc` | `Bcd` |
|---|---|
| `a1` : (id) | `b1` : id |
| `a2` : Integer | |
| `a3` : Integer | |

| `Cde` | invariant |
|---|---|
| `c` : key | (`a3` > `a2`) |

以下哪些说法是正确的？选择一个或多个：

- 所有 `Cde` 实例都有属性 `a1`。
- `Cde` 的标识符是 `a1`。
- 所有 `Cde` 实例引用 `Bcd` 对象。
- `Abc` 的实例具有 `c` 值。
- 对于任何 `Abc` 实例，`a3` 的值必须大于 `a2`。
- 对于任何 `Cde` 实例，`a3` 的值必须大于 `a2`。
- `Cde` 的标识符是 `c`。

### 12.8.2 问题2：类层次合并

考虑以下类模型：

在这种简单的类层次结构情况下，我们可以使用类层次合并模式，将整个类层次结构合并到一个类中。以下哪个模型描述了 `Abc` 类层次结构类层次合并模式的正确实现？选择一个：

1.
| `Abc` | <<enumeration> |
| `a1[1]` : Integer (id) | `AbctypeEL` |
| `category[1]` : `AbctypeEL` | `Bcd` |
| `a2[1]` : String | `Cde` |
| `a3[0..]` : String |

2.
| `Abc` | <<enumeration> |
| `a1[1]` : Integer (id) | `AbctypeEL` |
| `category[0..1]` : `AbctypeEL` | `Bcd` |
| `a2[1]` : String | `Cde` |
| `a3[0..1]` : String |

3.
| `Abc` | <<enumeration> |
| `a1[1]` : Integer (id) | `AbctypeEL` |
| `category[0..1]` : String | `Bcd` |
| `a3[0..1]` : String | `Cde` |

4.
| `Abc` |
| `a1[1]` : Integer (id) |
| `a2[1]` : String |
| `a3[0..1]` : String |

## 13 使用原生 JS 进行子类化

在本章中，我们首先将解释 JavaScript 中基于构造函数的子类化通用方法，然后根据我们运行示例——即上面所示的公共图书馆（Public Library）应用程序的信息模型片段，展示两个案例研究。

在第一个案例研究中，我们考虑了图 12.1 所示的以 `Book` 为根的单级类层次结构，这是一个不完全的刚性划分。我们使用“类层次结构合并”（Class Hierarchy Merge）设计模式将这个简单的类层次结构重构为一个可以映射到持久化数据库映射的单一类。

在第二个案例研究中，我们考虑了图 12.8 所示的由 `Employee`（员工）、`Manager`（经理）和 `Author`（作者）角色组成的多级类层次结构。将 `Person` 划分为 `Employee` 和 `Author` 没有任何约束，这意味着它是完全的、重叠的（非不交）且非刚性的。

对于简单的“经理是员工”（`Manager`-is-`Employee`）子层次结构，我们使用层次结构结构合并设计模式；对于将“员工和作者都是人员”（`Employee`-and-`Author`-is-a-`Person`）类层次结构映射到一组通过外键依赖关联的三个数据库表，我们使用“连接继承”（Joined Inheritance）方法。

在两个案例研究中，我们都展示了：

1. 如何推导出 JS 类模型以及相应的实体表模型，
2. 如何以 JS 模型类的形式编写 JS 类模型，
3. 如何基于模型代码编写视图（view）和控制器代码。

## 13.1 基于构造函数的类的子类化

在 ES2015 版本之前，JavaScript 没有显式的类概念，也不直接支持子类化，它必须在某些代码模式的帮助下实现，提供两种继承机制：(1) 属性继承和 (2) 方法继承。

正如我们在第一卷第 1 章中解释所过的那样，类可以通过两种替代方式定义：基于构造的和基于工厂的。这两种方法都有各自实现继承的方式。

我们通过以下示例总结了使用 ES2015 代码模式，在基于构造函数的单继承类层次结构中定义父类和子类：

| `Person` |
| --- |
| `firstName` : String |
| `lastName` : String |

| `Student` |
| --- |
| `studNo` : Integer |

首先，我们定义一个基类 `Person`，带有两个属性 `firstName` 和 `lastName`，通过 getters 和 setters 定义：

```javascript
class Person {

  constructor ({first, last}) {

    // 通过调用 setters 分配属性
    this.firstName = first;
    this.lastName = last;

  }

  getFirstName () {return this._firstName};
  setFirstName (f) {

    . . . 检查约束
    this._firstName = f;

  }

  getLastName () {return this._lastName};
  setLastName (l) {

    . . . 检查约束
    this._lastName = 1;

  }

}
```

然后，我们定义一个子类 `Student`，带有一个额外的属性 `studNo`：

```javascript
class Student extends Person {

  constructor ({first, last, studNo}) {

    // 调用父类的构造函数
    super({first, last});

    // 分配额外的属性
    this.studNo = studNo;

  }

  get studNo () {return this._studNo;}
  set studNo (sn) {

    // 检查约束
    .. this._studNo = sn;

  }

}
```
