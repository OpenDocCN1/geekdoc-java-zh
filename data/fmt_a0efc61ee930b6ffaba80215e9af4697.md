
# 数据库映射关系详解

## 实体与表结构

`Address` 实体对应的数据库表结构如下：

| 字段名 | 类型 | Nullable |
| :--- | :--- | :--- |
| `ADDRESS` | `bigint` | `false` |
| `STREET2` | `varchar(255)` | `true` |
| `STREET1` | `varchar(255)` | `true` |
| `ZIPCODE` | `varchar(255)` | `true` |
| `STATE` | `varchar(255)` | `true` |
| `COUNTRY` | `varchar(255)` | `true` |
| `CITY` | `varchar(255)` | `true` |

`Customer` 实体对应的数据库表结构如下：

| 字段名 | 类型 | Nullable |
| :--- | :--- | :--- |
| `CUSTOMER` | `bigint` | `false` |
| `LASTNAME` | `varchar(255)` | `true` |
| `PHONENUMBER` | `varchar(255)` | `true` |
| `EMAIL` | `varchar(255)` | `true` |
| `FIRSTNAME` | `varchar(255)` | `true` |
| `ADDRESS_FK` | `bigint` | `true` |

图 12. 带有数据库映射的 `Customer` 和 `Address` 代码

在图 12 中，`Address` 实体在其 `@OneToOne` 注解上使用了 `mappedBy` 元素。`Address` 被称为关系的反向所有者（inverse owner），因为它有一个 `mappedBy` 元素。`mappedBy` 元素表示连接列（`address`）是在关系的另一端指定的。事实上，在另一端，`Customer` 实体通过使用 `@JoinColumn` 注解定义了连接列，并重命名了外键 `ADDRESS_FK`。`Customer` 是关系的所有侧，作为所有者，由它来定义连接列映射。`Address` 是反向侧，所有者实体的表包含外键（即 `CUSTOMER` 表是带有 `ADDRESS_FK` 列的表）。这就是为什么我们说，`mappedBy` 标识拥有关系的属性，并在双向关系中是必须的。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_150_0.png)

> 如果你熟悉早期版本的 Hibernate，你可能会认为 JPA 的 `mappedBy` 等同于 Hibernate 的 `inverse` 属性。

## `@OneToOne` 单向关系

实体之间的一一单向关系具有基数为 1 的引用，只能通过一个方向到达。参考客户及其地址的示例，假设客户只有一个地址（基数 1）。从客户（源）向地址（目标）导航以知道客户的住处是重要的。图 13 所示的模型假设我们不需要向反方向导航（例如，你不需要知道哪个客户住在某个特定地址）。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_151_0.png)

图 13. 一个客户对应一个地址

在 Java 中，单向关系意味着 `Customer` 拥有一个 `Address` 属性（列表 36），但 `Address` 没有 `Customer` 属性（列表 37）。

列表 36. 拥有一个地址的 `Customer`

```java
@Entity
public class Customer {
    @Id
    @GeneratedValue
    private Long id;
    private String firstName;
    private String lastName;
    private String email;
    private String phoneNumber;
    private Address address;
    // 构造函数, getter, setter
}
```

列表 37. `Address`

```java
@Entity
public class Address {
    @Id
    @GeneratedValue
    private Long id;
    private String street1;
    private String street2;
    private String city;
    private String state;
    private String zipcode;
    private String country;
    // 构造函数, getter, setter
}
```

现在你知道，在 JPA 中，如果你不对属性进行注解，则将应用默认映射规则。因此，默认情况下，外键的名称是 `ADDRESS_ID`（见列表 38），它是关系属性名称（此处为 `address`）、下划线 `_` 以及目标表主键列名称（此处将是表的 `ID`）的拼接。此外注意，在 DDL 中，`ADDRESS_ID` 列默认是可空的，这意味着默认情况下，一对关联被映射为零（空值）或一。要自定义此映射，你可以使用两个注解。第一个是 `@OneToOne`（因为关系的基数是 1），它可以修改关联本身的一些属性，例如获取目标实体的方式。列表 40 定义了 `@OneToOne` 注解的 API。

列表 40. `@OneToOne` 注解 API

```java
@Target({METHOD, FIELD})
@Retention(RUNTIME)
public @interface OneToOne {
    Class<?> targetEntity() default void.class;
    CascadeType[] cascade() default {};
    FetchType fetch() default EAGER;
    boolean optional() default true;
    String mappedBy() default "";
    boolean orphanRemoval() default false;
}
```

另一个注解是 `@JoinColumn`（其 API 与列表 12 所示的 `@Column` 非常相似）。它用于自定义所有侧的连接列，即外键。列表 41 显示了你如何使用这两个注解。

列表 38. 带有外键的 `CUSTOMER` 表

```sql
CREATE TABLE CUSTOMER (
    ID BIGINT NOT NULL,
    EMAIL VARCHAR,
    FIRSTNAME VARCHAR,
    LASTNAME VARCHAR,
    PHONENUMBER VARCHAR,
    ADDRESS_FK BIGINT,
    PRIMARY KEY (ID)
);
```

列表 39. `ADDRESS` 表

```sql
CREATE TABLE ADDRESS (
    ID BIGINT NOT NULL,
    CITY VARCHAR,
    COUNTRY VARCHAR,
    STATE VARCHAR,
    STREET1 VARCHAR,
    STREET2 VARCHAR,
    ZIPCODE VARCHAR,
    PRIMARY KEY (ID)
);
```

列表 41. 带有自定义关系映射的 `Customer` 实体

```java
@Entity
public class Customer {
    @Id
    @GeneratedValue
    private Long id;
    private String firstName;
    private String lastName;
    private String email;
    private String phoneNumber;
    @OneToOne(fetch = FetchType.LAZY)
    @JoinColumn(name = "add_fk", nullable = false)
    private Address address;
    // Constructors, getters, setters
}
```

在 JPA 中，外键列被称为连接列（join column）。`@JoinColumn` 注解允许你对外键映射进行自定义。代码列表 41 使用了它将外键列重命名为 `ADD_FK`，并通过拒绝空值（`nullable=false`）使该关系成为强制性。`@ToOne` 注解为持久化提供程序提供了一个提示，用于延迟地获取该关系（稍后会进行详细介绍）。

## `@OneToMany` 单向关系

一对多关系是指一个源对象引用了一组目标对象。例如，一个采购订单由多个订单行组成（见图 14）。订单行可以通过相应的 `@ManyToOne` 注解来引用采购订单，但这种情况下并非如此，因为该关系是单向的。`PurchaseOrder` 是“一”的一侧也是关系的源点，而 `OrderLine` 是“多”的一侧也是目标。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_155_0.png)

图 14. 一个采购订单包含多行

基数是多个的，且导航仅从 `PurchaseOrder` 指向 `OrderLine`。在 Java 中，这种多重性由 `java.util` 包中的 `Collection`、`List` 和 `Set` 接口描述。代码列表 42 显示了 `PurchaseOrder` 实体的代码，它具有指向 `OrderLine` 的单向一对多关系（见代码列表 43）。

列表 42. `PurchaseOrder` 包含 `OrderLines`

```java
@Entity
@Table(name = "purchase_order")
public class PurchaseOrder {
    @Id
    @GeneratedValue
    private Long id;
    private LocalDateTime createdAt;
    private List<OrderLine> orderLines;
    // Constructors, getters, setters
}
```

列表 43. 一个 `OrderLine`

```java
@Entity
@Table(name = "order_line")
public class OrderLine {
    @Id
    @GeneratedValue
    private Long id;
    private String item;
    private Double unitPrice;
    private Integer quantity;
    // Constructors, getters, setters
}
```

列表 42 中的 `PurchaseOrder` 没有任何特殊注解，而是依赖于“通过异常配置”（configuration-by-exception）范式。当实体的类型集合被用作该实体的属性时，默认会触发一对多关系映射。默认情况下，一对多单向关系使用一个包含两个外键列的连接表（join table）。其中一个外键列引用 `PURCHASE_ORDER` 表，且与其主键类型相同，另一个引用 `ORDER_LINE`。该连接表的名称是两个实体的名称，并中间用 `_` 符号分隔。连接表被命名为 `PURCHASE_ORDER_ORDER_LINE`，并将导致如图 15 所示的模式结构。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_157_0.png)

图 15. `PURCHASE_ORDER` 和 `ORDER_LINE` 之间的连接表

如果你不喜欢连接表和外键名称，或者你正在映射到一张现有表，可以使用 JPA 注解来重新定义这些默认值。连接列的默认值是映射该关联的属性名称、符号 `_` 以及被引用的主键名称的拼接。由于可以使用 `@JoinColumn` 注解来更改外键列，因此 `@JoinTable` 注解（见代码列表 44）也可以对连接表映射执行相同的操作。你还可以使用 `@OneToMany` 注解（见代码列表 45），它像 `@ToOne` 一样可以自定义关系本身（使用获取模式等）。

列表 44. `@JoinTable` 注解 API

```java
@Target({METHOD, FIELD})
@Retention(RUNTIME)
public @interface JoinTable {
    String name() default "";
    String catalog() default "";
    String schema() default "";
    JoinColumn[] joinColumns() default {};
    JoinColumn[] inverseJoinColumns() default {};
    ForeignKey foreignKey() default @ForeignKey(PROVIDER_DEFAULT);
    ForeignKey inverseForeignKey() default @ForeignKey(PROVIDER_DEFAULT);
    UniqueConstraint[] uniqueConstraints() default {};
    Index[] indexes() default {};
}
```

列表 45. 使用注解的一对多 `PurchaseOrder` 实体

```java
@Entity
@Table(name = "purchase_order")
public class PurchaseOrder {
    @Id
    @GeneratedValue
    private Long id;
    private LocalDateTime createdAt;
    @OneToMany(fetch = FetchType.EAGER)
    @JoinColumn(name = "order_fk")
    private List<OrderLine> orderLines;
    // Constructors, getters, setters
}
```

`@JoinTable` 注解（见代码列表 44）可以对连接表映射执行相同的操作。你还可以使用 `@OneToMany` 注解（见代码列表 45），它像 `@ToOne` 一样可以自定义关系本身（使用获取模式等）。

一对多单向关系的默认规则是使用连接表，但对于遗留数据库，可以很容易更改为使用外键。`PurchaseOrder` 实体必须提供 `@JoinColumn` 而不是 `@JoinTable`，如列表 47 所示。

```java
@Entity
@Table(name = "purchase_order")
public class PurchaseOrder {
    @Id
    @GeneratedValue
    private Long id;
    private LocalDateTime createdAt;
    @OneToMany(fetch = FetchType.EAGER)
    @JoinColumn(name = "order_fk")
    private List<OrderLine> orderLines;
    // Constructors, getters, setters
}
```

`OrderLine` 实体的代码（如前文列表 43 所示）没有变化。通过使用 `@JoinColumn`，外键策略随后映射了单向关联。外键通过注解重命名为 `ORDER_FK` 并存在于目标表（`ORDER_LINE`）中。结果如图 16 所示的数据库结构。没有连接表，两个表之间的引用通过外键 `ORDER_FK` 实现。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_161_0.png)

图 16. `PURCHASE_ORDER` 和 `ORDER_LINE` 之间的连接列

## `@ManyToMany` 双向关系

多多双向关系存在一个源对象引用多个目标，且目标引用多个源的情况。例如，一张 CD 专辑由多个艺术家创作，一个艺术家出现在多个专辑中。在 Java 世界中，每个实体将拥有一个目标实体集合。在关系世界中，映射多多关系的唯一方法是使用连接表（连接列不起作用），并且正如你之前看到的，在双向关系中，你需要显式定义所有者（使用 `mappedBy` 元素）。

假设 `Artist` 实体是关系的所有者，意味着 `CD` 是反向所有者（见列表 48）。因此，`CD` 需要在其 `@ManyToMany` 注解上使用 `mappedBy` 元素。`mappedBy` 告诉持久化提供程序 `appearOnCDs` 是所有者实体对应的属性名称。

列表 48. 多位艺术家出现在一张 CD 上

```java
@Entity
public class CD {
    @Id
    @GeneratedValue
    private Long id;
    private String title;
    private Float price;
    private String description;
    @ManyToOne(mappedBy = "appearsOnCDs")
    private List<Artist> createdByArtists;
    // 构造函数, getters, setters
}
```

因此，如果 `Artist` 是关系的所有者（如列表 49 所示），则应由它来通过 `@JoinTable` 和 `@JoinColumn` 注解来定制连接表映射。

列表 49. 一位艺术家出现在多张 CD 专辑中
