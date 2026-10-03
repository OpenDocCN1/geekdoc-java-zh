
# 继承映射策略

## 单表策略 (Single-table-per-class Strategy)

```java
@Entity
@DiscriminatorValue("C")
public class CD extends Item {

    private String musicCompany;
    private Integer numberOfOfCDs;
    private Float totalDuration;
    private String genre;

    // Constructors, getters, setters
}
```

根实体`Item`通过`@DiscriminatorColumn`为整个层级结构定义了一次鉴别列。然后它通过`@DiscriminatorValue`注解将自身的默认值更改为`I`。子实体只需要重新定义它们自己的鉴别值即可。

表 4 显示了结果。鉴别列及其值与之前表 3 中显示的内容有所不同。

**表 4. 具有不同鉴别名称和值的 ITEM**

| ID | DISC | TITLE | PRICE | DESCRIPTION | MUSICCOMPANY | ISBN | ... |
|---|---|---|---|---|---|---|---|
| 1 | I | Don | 210 | Beautiful black nan | | | |
| 2 | C | Soul Train | 23.50 | Fantastic jazz album | Prestige ... | | |
| 3 | C | Zoot All | 18 | One of the best from Zappa | Warner ... | | |
| 4 | B | The Robots of Dawn | 22.30 | Robots everywhere | 0-8764 ... | | |
| 5 | B | H2G2 | 17.50 | Funny IT book ;) | 1-1689 ... | | |

单表类（single-table-per-class）策略是默认的继承策略，最容易理解，并且当层级结构相对简单稳定时运行良好。然而，它也有一些缺点：向层级中添加新实体或向现有实体添加属性、迁移数据以及更改索引。该策略还要求子实体的列为空。如果`Book`实体的`ISBN`恰好不能为空，则你无法再插入`CD`，因为`CD`实体没有`ISBN`。

## 连接子类策略 (Joined-subclass Strategy)

在连接子类策略中，层级结构中的每个实体都映射到它自己的表中。根实体映射到一个表，该表定义了层级结构中所有表共用的主键以及鉴别列。每个子类由单独的表表示，该表包含它自己的属性（不继承自根类）以及一个引用根表主键的主键。非根表不持有鉴别列。

你可以通过如列表 62 所示，在根实体上标注`@Inheritance`注解来实现连接子类策略（`CD`和`Book`的代码保持不变，与之前相同）。

**列表 62. 使用连接子类策略的 Item 实体**

```java
@Entity
@Inheritance(strategy = InheritanceType.JOINED)
public class Item {

  @Id
  @GeneratedValue
  protected Long id;
  protected String title;
  protected String description;
  protected Float price;

  // Constructors, getters, setters
}
```

从开发者的角度来看，连接子类策略是自然的，因为每个抽象或具体的类将将其状态映射到不同的表。图 22 显示了`Item`、`Book`和`CD`实体将如何映射。

| ITEM | BOOK | CD |
|---|---|---|
| ID bigint | ID bigint | ID bigint |
| ISBN varchar(255) | MUSIC varchar(255) | MUSIC varchar(255) |
| PUBLISHER varchar(255) | NUMBEROFCDs integer | TOTALDURATION double |
| NOFPAGES integer | | GENRE varchar(255) |
| ILLUSTRATIONS smallint | PRICE double | |

**图 22. 使用连接子类策略进行继承映射**

你仍然可以在根实体中使用`@DiscriminatorColumn`和`@DiscriminatorValue`注解来自定义鉴别列和值（`DTYPE`列位于`ITEM`表中）。

连接子类策略直观的，且与你所了解的对象继承机制接近。通过查询子类时，连接子类策略需要执行连接（joins）。层级越深，需要的连接就越多。该策略为多态查询提供了良好的支持。

## 按类表策略 (Table-per-class Strategy)

在按类表策略（或称为实体类表策略）中，层级结构中的每个实体都映射到自己的专用表，与连接子类策略类似。区别在于根实体的所有属性都复制到了叶子表中。这种策略导致模型反规范化，并且没有鉴别列。将我们的示例映射到这种策略只需要在根实体上指定`TABLE_PER_CLASS`（参见列表 63）。

**列表 63. 使用按类表策略的 Item 实体**

```java
@Entity
@Inheritance(strategy = InheritanceType.TABLE_PER_CLASS)
public class Item {

  @Id
  @GeneratedValue
  protected id;
  protected String title;
  protected String description;
  protected Float price;

  // Constructors, getters, setters
}
```

图 23 显示了`ITEM`、`BOOK`和`CD`实体。注意表之间没有关联。

当然，记住按类表策略在查询单个实例时性能良好，因为它类似于单表类策略：查询被局限于单个表。缺点是它使得跨层级的多态查询（例如查找所有项目，包括`CD`和书籍）比其他策略更贵；它必须使用`UNION`操作查询所有子类表，当涉及大量数据时这种开销很大。JPA 2.2 对按类表策略的支持仍然是可选的。

## 继承层级中的类型

之前解释映射策略的示例仅使用了实体。`Item`、`Book`和`CD`都是实体。但实体并不总是继承自实体。类层级可以混合各种类型的类：实体和非实体、抽象实体以及映射的超类。继承这些不同类型的类会对映射产生影响。

### 抽象实体 (Abstract Entity)

非实体（Nonentities）也被称为临时类（transient classes），意味着它们是 POJO。实体（entity）可以作为非实体的子类或被非实体扩展。为什么要在层次结构中使用非实体呢？对象建模和继承是共享状态和行为的手段。非实体可以为叶节点实体提供公共的数据结构。非实体父类的状态不是持久化的，因为它不受持久化提供程序（persistence provider）的管理（记住，类被持久化提供程序管理的条件是存在`@Entity`注解）。

例如，`Book`是一个实体（列表 65），并继承自一个非实体`Item`（`Item`没有任何注解），如列表 64 所示。

**列表 64. Item 是一个没有 @Entity 的简单 POJO**

```java
public class Item {
    protected String title;
    protected String description;
    protected Float price;

    // Constructors, getters, setters
}
```

`Book`实体（列表 65）继承自`Item`，因此 Java 代码以常规的、面向对象的方式访问`title`、`price`和`description`属性，以及定义的任何其他方法。`Item`可以是具体的也可以是抽象的，并且对最终映射没有任何影响。

**列表 65. Book 实体继承自一个 POJO**

```java
@Entity
public class Book extends Item {

    @Id
    @Generated
    protected Long id;
    private String isbn;
    private String publisher;
    private Integer nbOfPages;
    private Boolean illustrations;

    // Constructors, getters, setters
}
```

`Book`是一个实体并继承自`Item`。但只有`Book`的属性会被映射到表中。`Item`的任何属性都没有出现在列表 66 定义的表结构中。要持久化`Book`，你需要创建一个`Book`实例，为你想要的任何属性（`title`, `price`, `isbn`, `publisher`等）设置值，但只有`Book`的属性（`id`, `isbn`等）会被持久化。

**列表 66. BOOK 表没有包含来自 Item 的属性**

```sql
CREATE TABLE BOOK
(
    ID BIGINT NOT NULL,
    ILLUSTRATIONS BOOLEAN,
    ISBN VARCHAR,
    NBOFPAGES INTEGER,
    PUBLISHER VARCHAR,
    PRIMARY KEY (ID)
)
```

## 映射父类 (Mapped Superclass)

JPA 定义了一种特殊类，称为映射父类（mapped superclass），用于共享状态和行为，以及实体继承的映射信息。然而，映射父类不是实体。它们不受持久化提供程序管理，没有任何要映射的表，且不能被查询或作为关系的一部分，但它们可以为任何继承自它们的实体提供持久化属性。它们与嵌入类（embeddable classes）相似，不同之处它们可以配合继承使用。通过使用`@MappedSuperclass`注解标记一个类即可将其指示为映射父类。映射父类可以是抽象的也可以是具体的。

如列表 67 所示，根类`Item`标记了`@MappedSuperclass`注解，而不是`@Entity`注解。它定义了一种继承策略（`JOINED`），并在其某些属性上标记了`@Column`注解。由于映射父类没有映射到表，因此不允许使用`@Table`注解。

**列表 67. Item 是一个映射父类**

```java
@MappedSuperclass
@Inheritance(strategy = JOINED)
public abstract class Item {

    @Id
    @GeneratedValue
    protected Long id;
    @Column(length = 50, nullable = false)
    protected String title;
    @Column(length = 2000)
    protected String description;
    protected Float price;

    // Constructors, getters, setters
}
```

如你在列表 67 中所示，`title`和`description`属性标记了`@Column`注解。列表 68 显示了`Book`实体继承自`Item`。

**列表 68. Book 继承自一个映射父类**

```java
@Entity
public class Book extends Item {

    private String isbn;
    private String publisher;
    private Integer nbOfPages;
    private Boolean illustrations;

    // Constructors, getters, setters
}
```

此层次结构将被映射为一个表。`Item`不是实体，也没有任何表。`Item`和`Book`的属性将被映射到`BOOK`表的列，但映射父类也会共享它们的映射信息。`Item`的`@Column`注解将被继承。

由于映射父类不是受管理的实体，你无法对其进行持久化或查询。列表 69 显示了具有自定义`TITLE`和`DESCRIPTION`列的`BOOK`结构。

**列表 69. BOOK 表包含来自 Item 的所有属性**

```sql
CREATE TABLE BOOK
(
    ID BIGINT NOT NULL,
    DESCRIPTION VARCHAR(2000),
    ILLUSTRATIONS BOOLEAN,
    ISBN VARCHAR,
    NBOFPAGES INTEGER,
    PRICE DOUBLE,
    PUBLISHER VARCHAR,
    TITLE VARCHAR(50) NOT NULL,
    PRIMARY KEY (ID)
)
```

1. JavaBean: <https://docs.oracle.com/javase/8/docs/api/java/beans/package-summary.html>
2. JPA Specification: <https://jcp.org/en/jsr/detail?id=338>

# 管理实体

Java Persistence API 有两个方面。一个方面是将对象映射到关系型数据库的能力。通过异常配置（Configuration by exception）允许持久化提供程序在不需要大量代码的情况下完成大部分工作，但 JPA 的丰富性也允许从对象到表的自定义映射。JPA 的另一个方面是查询实体的能力。实体管理器（entity manager）提供了创建、查找和同步实例的 API。

> 本章的代码可以在 <https://github.com/agoncal/fascicle-jpa/tree/2.2/managing> 找到。

## 实体管理器 API

在查看如何管理实体之前，让我们先简要概述用于管理实体的 API。图 1 显示了位于不同包中的主要接口。在根包`javax.persistence`下，我们找到了所有与获取、事务和查询相关的内容。子包`javax.persistence.criteria`托管与标准（criteria）相关的接口，而子包`javax.persistence.metamodel`则与元模型（metamodel）相关。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_195_0.png)

## 实体管理器 API

实体管理器管理实体的状态和生命周期，以及在持久化上下查询实体。实体管理器负责创建和删除实体实例，并通过主键查找实体。它可以使用乐观锁或悲观锁锁定实体以防止并发访问，并可以使用 JPQL 查询根据特定标准检索实体（关于并发和锁的更多信息请见第 8 章）。

当实体管理器获取一个实体的引用时，该实体被称为“受管理的（managed）”。在此之前，实体被视为普通的 POJO（即离散的，detached）。JPA 的优势在于实体可以被应用程序的不同层作为普通对象使用，并在你需要向数据库加载或插入数据时由实体管理器管理。当实体受管理状态时，你可以执行持久化操作，实体管理器会自动将实体的状态与数据库同步。当实体处于离散状态（即不受管理）时，它变回简单的 POJO，并供其他层（例如表示层）使用，而无需与数据库同步状态。

关于持久化，真正的工作从实体管理器开始。`EntityManager`是由持久化提供程序实现的接口，它将生成并执行 SQL 语句。`javax.persistence.EntityManager`接口提供了操作实体的 API（子集见列表 1）。

**列表 1. EntityManager API 的子集**

```java
public interface EntityManager {
  // 用于创建实体管理器、关闭它并检查其是否打开
  open
  public void close();
  public boolean isOpen();
  public EntityManagerFactory getEntityManagerFactory();

  // 返回 EntityManager 的底层提供者对象
}
```

```java
public <T> T unwrap(Class<T> cls);
public Object getDelegate();
```

```java
// Sets and gets an entity manager property or hint
public void setProperty(String propertyName, Object value);
public Map<String, Object> getProperties();
```

实体管理器（entity manager）可以看作实体的一级缓存。因此，它有几个方法可以检查实体是否在一级缓存中（即被托管的）、将缓存刷新到数据库，或从数据库刷新缓存。`clear`和`detach`方法会清除实体并从实体管理器中解除。

```java
// Synchronises the persistence context to the underlying database
public void flush();
public void setFlushMode(FlushMode flushMode);
public FlushMode getFlushMode();
```

```java
// Refreshes the state of the entity from the database, overwriting any changes made
public void refresh(Object entity);
public void refresh(Object entity, LockMode lockMode);
```
