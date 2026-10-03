
# `@Size`、`@Length` 和 `@Column` 之间的差异（`length=value`）

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/jpa-size-length-column-differences>

![announcement - icon](img/09a677d1478a9680c79e73e13487328a.png)

JPA 的行为可能会因使用场景的具体情况而大不相同。在本地环境或预发布环境中运行良好的代码，部署到生产环境、面对真实规模的数据库时，可能会表现得非常糟糕，甚至完全失败。

在生产环境中调试这些 JPA 问题相当困难——现有的 APM 无法在代码级别提供足够细粒度的洞察，而逐一跟踪实体查询位置、判断是否应该批量查询，也可能是一项艰苦且耗时的任务。

**Lightrun** 是一种全新的生产环境调试方式。借助 Lightrun 的 Logs 和 Snapshots，您现在可以在生产环境中获得调试器级别的详细信息，而无需开放入站端口、重新部署、重启，甚至无需停止正在运行的应用程序。

此外，在运行时添加 Lightrun Metrics，可以帮助您安全地实时定位持久化问题。想看看实际效果吗？**查看我们的 2 分钟教程**，了解如何使用 Lightrun 调试生产环境中的 JPA 性能问题：

[>> 使用 Lightrun 调试 Spring 持久化和 JPA 问题](/web/20220525131809/https://www.baeldung.com/lightrun-n-jpa)

## 1.概观

在这个快速教程中，我们将看看 [JSR-330](/web/20220525131809/https://www.baeldung.com/javax-validation) 的 `@Size`、[Hibernate](/web/20220525131809/https://www.baeldung.com/hibernate-4-spring) 的 `@Length` 和 [JPA](/web/20220525131809/https://www.baeldung.com/the-persistence-layer-with-spring-data-jpa) 的 `@Column` 的 `length` 属性。

乍一看，**这些可能看起来一样，但它们执行不同的功能**。让我们看看具体情况。

## 2.起源

简单地说，所有这些注释都是为了**传达一个字段的大小**。

`@Size` 和 `@Length` 类似。我们可以使用其中任何一个来验证字段的大小。第一个是 [Java 标准注释](https://web.archive.org/web/20220525131809/https://docs.oracle.com/javaee/7/tutorial/bean-validation001.htm)，第二个是特定于 Hibernate 的[注释](https://web.archive.org/web/20220525131809/http://docs.jboss.org/ejb3/app-server/HibernateAnnotations/api/org/hibernate/validator/Length.html)。

然而，`@Column` 是一个 [JPA 注释](https://web.archive.org/web/20220525131809/https://docs.oracle.com/javaee/7/api/javax/persistence/Column.html)，我们用它来控制 DDL 语句。

现在，让我们详细地看一下它们。

## 3.`@Size`

对于验证，我们将使用 `@Size`，一个 Bean Validation 注释。让我们使用用 `@Size` 注释的属性 `middleName`，验证其值是否处于属性 `min` 和 `max` 指定的范围内：

```java
public class User {

    // ...

    @Size(min = 3, max = 15)
    private String middleName;

    // ...

}
```

最重要的是，**`@Size` 使 Bean 独立于 JPA 及其供应商（如 Hibernate）**。因此，它比 `@Length` 更具可移植性。

## 4.`@Length`

正如我们刚刚提到的，`@Length` 是 `@Size` 的 Hibernate 特定版本。让我们使用 `@Length` 来限制 `lastName` 的范围：

```java
@Entity
public class User {

    // ...

    @Length(min = 3, max = 15)
    private String lastName;

    // ...

}
```

## 5.`@Column(length=value)`

然而，情况完全不同。

我们将使用 `@Column` **表示物理数据库列的具体特征**。让我们使用 `@Column` 注释的 [`length`](https://web.archive.org/web/20220525131809/http://java.sun.com/javaee/5/docs/api/javax/persistence/Column.html#length%28%29) 属性来指定字符串值列的长度：

```java
@Entity
public class User {

    @Column(length = 3)
    private String firstName;

    // ...

}
```

因此，生成的列将被定义为 `VARCHAR(3)`，尝试插入更长的字符串将导致 SQL 错误。

注意，我们将只使用 `@Column` 来指定表列属性，**因为它不提供验证**。

当然，**我们可以将 `@Column` 与 `@Size` 一起使用**，通过 Bean Validation 来指定数据库列属性。

```java
@Entity
public class User {

    // ...

    @Column(length = 5)
    @Size(min = 3, max = 5)
    private String city;

    // ...

}
```

## 6.结论

在这篇文章中，我们了解了 `@Size` 注释、`@Length` 注释和 `@Column` 的 `length` 属性之间的区别，并分别检查了它们的适用范围。

与往常一样，GitHub 上的[完整源代码提供了示例](https://web.archive.org/web/20220525131809/https://github.com/eugenp/tutorials/tree/master/persistence-modules/hibernate-mapping)。
