
# 修复 JPA 错误“java.lang.String 无法转换为 [Ljava.lang.String;”

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/jpa-error-java-lang-string-cannot-be-cast>

JPA 的行为会根据其运行环境的具体情况而发生很大变化。在本地环境或预发布环境中正常工作的代码，一旦在生产环境中面对真实规模的数据库，性能可能会变得非常糟糕，甚至直接失败。

在生产环境中调试这些 JPA 问题相当困难——现有的 APM（应用性能监控）工具无法在代码层面提供足够细粒度的洞察，而逐一追踪每一处未进行批量查询而是逐条查询实体的代码位置，可能是一件极其枯燥且耗时的工作。

**Lightrun** 是一种在生产环境中进行调试的新方法。借助 Lightrun 的 Logs 和 Snapshots 功能，您现在可以在不开放入站端口、不重新部署、不重启甚至不停止运行中应用程序的情况下，在生产环境中实现调试器级别的细粒度观测。

此外，在运行时对 Lightrun Metrics 进行插桩，可以让您安全、实时地追踪持久化层的问题。想亲眼看看它的效果吗？**请查看我们 2 分钟的教程**，了解如何使用 Lightrun 在生产环境中调试 JPA 性能问题：

[>> 使用 Lightrun 调试 Spring Persistence 和 JPA 问题](/web/20220524032728/https://www.baeldung.com/lightrun-n-jpa)

## 1. 简介

当然，我们从未设想过会在 Java 中将一个`String`转换为一个`String`数组：

```java
java.lang.String cannot be cast to [Ljava.lang.String;
```

但是，这确实是一个常见的 JPA 错误。

在这个快速教程中，我们将展示这个问题是如何出现的，以及如何解决它。

## 2. JPA 中的常见错误场景

在 JPA 中，当我们处理本地查询（Native Query）并使用`EntityManager`的`createNativeQuery`方法时，遇到这个错误**并不罕见。**

其 [Javadoc](https://web.archive.org/web/20220524032728/https://docs.oracle.com/javaee/7/api/javax/persistence/EntityManager.html#createNativeQuery-java.lang.String-) 实际上警告我们**该方法将返回一个`Object[]`列表，或者，如果查询只返回一列，则只返回一个单独的`Object`。**

让我们看一个例子。首先，我们创建一个查询执行器（`QueryExecutor`），希望重用它来执行所有查询：

```java
public class QueryExecutor {
    public static List<String[]> executeNativeQueryNoCastCheck(String statement, EntityManager em) {
        Query query = em.createNativeQuery(statement);
        return query.getResultList();
    }
}
```

如上所述，我们使用了`createNativeQuery()`方法，总是期望结果集包含一个`String`数组。

接下来，为我们的示例创建一个简单的实体：

```java
@Entity
public class Message {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String text;

    // getters and setters

}
```

最后，创建一个测试类，在运行测试前插入一条`Message`记录：

```java
public class SpringCastUnitTest {

    private static EntityManager em;
    private static EntityManagerFactory emFactory;

    @BeforeClass
    public static void setup() {
        emFactory = Persistence.createEntityManagerFactory("jpa-h2");
        em = emFactory.createEntityManager();

        // insert an object into the db
        Message message = new Message();
        message.setText("text");

        EntityTransaction tr = em.getTransaction();
        tr.begin();
        em.persist(message);
        tr.commit();
    }
}
```

现在，我们可以使用我们的`QueryExecutor`来执行一个查询，检索我们实体的`text`字段：

```java
@Test(expected = ClassCastException.class)
public void givenExecutorNoCastCheck_whenQueryReturnsOneColumn_thenClassCastThrown() {
    List<String[]> results = QueryExecutor.executeNativeQueryNoCastCheck("select text from message", em);

    // fails
    for (String[] row : results) {
        // do nothing
    }
}
```

我们可以看到，**因为查询中只有一列，JPA 实际上会返回一个字符串列表，而不是字符串数组列表。**我们得到`ClassCastException`是因为查询返回单个列，而我们期望的却是一个数组。

## 3. 手动类型转换修复

**修复此错误最简单的方法是检查结果集对象的类型**，以避免`ClassCastException`。让我们在`QueryExecutor`中实现一个执行此操作的方法：

```java
public static List<String[]> executeNativeQueryWithCastCheck(String statement, EntityManager em) {
    Query query = em.createNativeQuery(statement);
    List results = query.getResultList();

    if (results.isEmpty()) {
        return new ArrayList<>();
    }

    if (results.get(0) instanceof String) {
        return ((List<String>) results)
          .stream()
          .map(s -> new String[] { s })
          .collect(Collectors.toList());
    } else {
        return (List<String[]>) results;
    }
}
```

然后，我们可以使用此方法执行查询，而不会出现异常：

```java
@Test
public void givenExecutorWithCastCheck_whenQueryReturnsOneColumn_thenNoClassCastThrown() {
    List<String[]> results = QueryExecutor.executeNativeQueryWithCastCheck("select text from message", em);
    assertEquals("text", results.get(0)[0]);
}
```

这并非理想的解决方案，因为如果查询只返回一列，我们仍然需要手动将结果转换为数组。

## 4. JPA 实体映射修复

修复此错误的另一种方法是将结果集映射到一个实体。通过这种方式，**我们可以预先决定如何映射查询结果**，从而避免不必要的类型转换。

让我们为执行器添加另一个方法，以支持自定义实体映射的使用：

```java
public static <T> List<T> executeNativeQueryGeneric(String statement, String mapping, EntityManager em) {
    Query query = em.createNativeQuery(statement, mapping);
    return query.getResultList();
}
```

接下来，创建一个自定义的`SqlResultSetMapping`，将之前查询的结果集映射到`Message`实体：

```java
@SqlResultSetMapping(
  name="textQueryMapping",
  classes={
    @ConstructorResult(
      targetClass=Message.class,
      columns={
        @ColumnResult(name="text")
      }
    )
  }
)
@Entity
public class Message {
    // ...
}
```

在这种情况下，我们还必须添加一个与新建的`SqlResultSetMapping`相匹配的构造函数：

```java
public class Message {

    // ... fields and default constructor

    public Message(String text) {
        this.text = text;
    }

    // ... getters and setters

}
```

最后，我们可以使用新的执行器方法运行测试查询，并获得`Message`列表：

```java
@Test
public void givenExecutorGeneric_whenQueryReturnsOneColumn_thenNoClassCastThrown() {
    List<Message> results = QueryExecutor.executeNativeQueryGeneric(
      "select text from message", "textQueryMapping", em);
    assertEquals("text", results.get(0).getText());
}
```

这个解决方案更加简洁，因为我们将结果集的映射委托给了 JPA。

## 5. 结论

在本文中，我们展示了本地查询（Native Query）是导致`ClassCastException`的常见原因。我们还研究了如何自行进行类型检查，以及如何通过将查询结果映射到传输对象来解决此问题。

与往常一样，示例的完整源代码可在 [GitHub 上获取](https://web.archive.org/web/20220524032728/https://github.com/eugenp/tutorials/tree/master/persistence-modules/java-jpa)。
