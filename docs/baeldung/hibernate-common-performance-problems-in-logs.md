
# 3 个常见的 Hibernate 性能问题以及如何在日志文件中找到它们

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/hibernate-common-performance-problems-in-logs>

## 1. 简介

您可能已经读过一些关于 Hibernate 性能差的抱怨，或者您自己也曾与其中一些抱怨进行过斗争。我使用 Hibernate 已经超过 15 年了，我遇到了太多这样的问题。

这些年来，我知道这些问题是可以避免的，而且你可以在你的日志文件中找到很多这样的问题。在这篇文章中，我想告诉你如何找到并修复其中的 3 个。

## 2. 发现并修复性能问题

### 2.1. 在生产中记录 SQL 语句

第一个性能问题非常容易发现，而且经常被忽略。它是生产环境中 SQL 语句的日志记录。

写一些日志语句听起来没什么大不了的，有很多应用程序就是这么做的。但是这是非常低效的，尤其是通过`System.out.println`，因为 Hibernate 会将 Hibernate 配置中的`show_sql`参数设置为`true`:

```java
Hibernate: select 
    order0_.id as id1_2_, 
    order0_.orderNumber as orderNum2_2_, 
    order0_.version as version3_2_ 
  from purchaseOrder order0_
Hibernate: select 
    items0_.order_id as order_id4_0_0_, 
    items0_.id as id1_0_0_, 
    items0_.id as id1_0_1_, 
    items0_.order_id as order_id4_0_1_, 
    items0_.product_id as product_5_0_1_, 
    items0_.quantity as quantity2_0_1_, 
    items0_.version as version3_0_1_ 
  from OrderItem items0_ 
  where items0_.order_id=?
Hibernate: select 
    items0_.order_id as order_id4_0_0_, 
    items0_.id as id1_0_0_, 
    items0_.id as id1_0_1_, 
    items0_.order_id as order_id4_0_1_, 
    items0_.product_id as product_5_0_1_, 
    items0_.quantity as quantity2_0_1_, 
    items0_.version as version3_0_1_ 
  from OrderItem items0_ 
  where items0_.order_id=?
Hibernate: select 
    items0_.order_id as order_id4_0_0_, 
    items0_.id as id1_0_0_, 
    items0_.id as id1_0_1_, 
    items0_.order_id as order_id4_0_1_, 
    items0_.product_id as product_5_0_1_, 
    items0_.quantity as quantity2_0_1_, 
    items0_.version as version3_0_1_ 
  from OrderItem items0_ 
  where items0_.order_id=?
```

在我的一个项目中，通过将`show_sql`设置为`false`，我在几分钟内将性能提高了 20%。这就是你想在下一次站立会议上报告的那种成就🙂

如何解决这个性能问题非常明显。只需打开您的配置（例如`persistence.xml`文件）并将`show_sql`参数设置为`false`。无论如何，您在生产中不需要这些信息。

但是在开发过程中你可能需要它们。如果没有，您将使用两种不同的 Hibernate 配置（您不应该使用这两种配置），并在那里停用 SQL 语句日志记录。解决方案是为开发和生产使用两种不同的[日志配置](https://web.archive.org/web/20220926183539/http://www.thoughts-on-java.org/hibernate-logging-guide/)，它们针对运行时环境的特定需求进行了优化。

**开发配置**

开发配置应该提供尽可能多的有用信息，以便您可以看到 Hibernate 如何与数据库交互。因此，您至少应该在开发配置中记录生成的 SQL 语句。您可以通过激活`org.hibernate.SQL`类别的`DEBUG`消息来完成此操作。如果您还想查看绑定参数的值，您必须将`org.hibernate.type.descriptor.sql`的日志级别设置为`TRACE`:

```java
log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.Target=System.out
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout
log4j.appender.stdout.layout.ConversionPattern=%d{HH:mm:ss,SSS} %-5p [%c] - %m%n
log4j.rootLogger=info, stdout

# basic log level for all messages
log4j.logger.org.hibernate=info

# SQL statements and parameters
log4j.logger.org.hibernate.SQL=debug
log4j.logger.org.hibernate.type.descriptor.sql=trace
```

下面的代码片段显示了 Hibernate 使用这个日志配置写入的一些示例日志消息。如您所见，您可以获得关于已执行的 SQL 查询以及所有设置和检索的参数值的详细信息:

```java
23:03:22,246 DEBUG SQL:92 - select 
    order0_.id as id1_2_, 
    order0_.orderNumber as orderNum2_2_, 
    order0_.version as version3_2_ 
  from purchaseOrder order0_ 
  where order0_.id=1
23:03:22,254 TRACE BasicExtractor:61 - extracted value ([id1_2_] : [BIGINT]) - [1]
23:03:22,261 TRACE BasicExtractor:61 - extracted value ([orderNum2_2_] : [VARCHAR]) - [order1]
23:03:22,263 TRACE BasicExtractor:61 - extracted value ([version3_2_] : [INTEGER]) - [0]
```

如果激活 Hibernate statistics，Hibernate 会为您提供更多关于某个`Session`的内部信息。您可以通过将系统属性`hibernate.generate_statistics`设置为`true`来实现这一点。

但是，请只在您的开发或测试环境中激活统计数据。收集所有这些信息会降低应用程序的速度，如果在生产环境中激活这些信息，可能会导致性能问题。

您可以在下面的代码片段中看到一些示例统计信息:

```java
23:04:12,123 INFO StatisticalLoggingSessionEventListener:258 - Session Metrics {
 23793 nanoseconds spent acquiring 1 JDBC connections;
 0 nanoseconds spent releasing 0 JDBC connections;
 394686 nanoseconds spent preparing 4 JDBC statements;
 2528603 nanoseconds spent executing 4 JDBC statements;
 0 nanoseconds spent executing 0 JDBC batches;
 0 nanoseconds spent performing 0 L2C puts;
 0 nanoseconds spent performing 0 L2C hits;
 0 nanoseconds spent performing 0 L2C misses;
 9700599 nanoseconds spent executing 1 flushes (flushing a total of 9 entities and 3 collections);
 42921 nanoseconds spent executing 1 partial-flushes (flushing a total of 0 entities and 0 collections)
}
```

我经常在日常工作中使用这些统计数据，以便在生产中出现性能问题之前找到它们，我可以就此写几篇文章。所以让我们只关注最重要的。

第 2 行到第 5 行显示了 Hibernate 在这个会话中使用了多少 JDBC 连接和语句，以及在这个会话上花费了多少时间。你应该经常看看这些价值，并与你的期望进行比较。

如果语句比预期的多得多，那么您很可能遇到了最常见的性能问题，即 n+1 选择问题。您可以在几乎所有的应用程序中找到它，它可能会在更大的数据库上产生巨大的性能问题。我将在下一节更详细地解释这个问题。

第 7 到 9 行展示了 Hibernate 如何与二级缓存交互。这是 Hibernate 的三个缓存之一，它以独立于会话的方式存储实体。如果您在应用程序中使用第二层，您应该始终监控这些统计信息，看看 Hibernate 是否从那里获得了实体。

**生产配置**

生产配置应该针对性能进行优化，并避免任何不迫切需要的消息。通常，这意味着您应该只记录错误消息。如果您使用 Log4j，您可以通过以下配置来实现:

```java
log4j.appender.stdout=org.apache.log4j.ConsoleAppender
log4j.appender.stdout.Target=System.out
log4j.appender.stdout.layout=org.apache.log4j.PatternLayout
log4j.appender.stdout.layout.ConversionPattern=%d{HH:mm:ss,SSS} %-5p [%c] - %m%n
log4j.rootLogger=info, stdout

# basic log level for all messages
log4j.logger.org.hibernate=error
```

### 2.2. N+1 选择问题

正如我已经解释过的，n+1 选择问题是最常见的性能问题。许多开发人员将这个问题归咎于 OR-Mapping 概念，他们并没有完全错。但是如果您理解 Hibernate 如何处理延迟获取的关系，您就可以很容易地避免它。因此，开发人员也有责任，因为他有责任避免这类问题。所以让我先解释为什么这个问题存在，然后告诉你一个简单的方法来防止它。如果你已经熟悉 n+1 选择问题，你可以直接跳到[解决方案](#namedEntityGraph)。

Hibernate 为实体之间的关系提供了非常方便的映射。您只需要一个具有相关实体类型的属性和一些注释来定义它:

```java
@Entity
@Table(name = "purchaseOrder")
public class Order implements Serializable {

    @OneToMany(mappedBy = "order", fetch = FetchType.LAZY)
    private Set<OrderItem> items = new HashSet<OrderItem>();

    ...
}
```

当您现在从数据库加载一个`Order`实体时，您只需要调用`getItems()`方法来获取该订单的所有商品。Hibernate 隐藏了从数据库中获取相关的`OrderItem`实体所需的数据库查询。

当您开始使用 Hibernate 时，您可能已经知道应该对大多数关系使用`FetchType.LAZY`，并且它是多对多关系的默认设置。这告诉 Hibernate，如果使用映射关系的属性，就只获取相关的实体。一般来说，只获取您需要的数据是一件好事，但是这也需要 Hibernate 执行一个额外的查询来初始化每个关系。这可能会导致大量的查询，如果您在实体列表上工作，就像我在下面的代码片段中所做的那样:

```java
List<Order> orders = em.createQuery("SELECT o FROM Order o").getResultList();
for (Order order : orders) {
    log.info("Order: " + order.getOrderNumber());
    log.info("Number of items: " + order.getItems().size());
}
```

您可能不会想到这几行代码可以创建数百甚至数千个数据库查询。但是，如果您使用`FetchType.LAZY`来表示与`OrderItem`实体的关系，就会出现这种情况:

```java
22:47:30,065 DEBUG SQL:92 - select 
    order0_.id as id1_2_, 
    order0_.orderNumber as orderNum2_2_, 
    order0_.version as version3_2_ 
  from purchaseOrder order0_
22:47:30,136 INFO NamedEntityGraphTest:58 - Order: order1
22:47:30,140 DEBUG SQL:92 - select 
    items0_.order_id as order_id4_0_0_, 
    items0_.id as id1_0_0_, 
    items0_.id as id1_0_1_, 
    items0_.order_id as order_id4_0_1_, 
    items0_.product_id as product_5_0_1_, 
    items0_.quantity as quantity2_0_1_, 
    items0_.version as version3_0_1_ 
  from OrderItem items0_ 
  where items0_.order_id=?
22:47:30,171 INFO NamedEntityGraphTest:59 - Number of items: 2
22:47:30,171 INFO NamedEntityGraphTest:58 - Order: order2
22:47:30,172 DEBUG SQL:92 - select 
    items0_.order_id as order_id4_0_0_, 
    items0_.id as id1_0_0_, 
    items0_.id as id1_0_1_, 
    items0_.order_id as order_id4_0_1_, 
    items0_.product_id as product_5_0_1_, 
    items0_.quantity as quantity2_0_1_, 
    items0_.version as version3_0_1_ 
  from OrderItem items0_ 
  where items0_.order_id=?
22:47:30,174 INFO NamedEntityGraphTest:59 - Number of items: 2
22:47:30,174 INFO NamedEntityGraphTest:58 - Order: order3
22:47:30,174 DEBUG SQL:92 - select 
    items0_.order_id as order_id4_0_0_, 
    items0_.id as id1_0_0_, 
    items0_.id as id1_0_1_, 
    items0_.order_id as order_id4_0_1_, 
    items0_.product_id as product_5_0_1_, 
    items0_.quantity as quantity2_0_1_, 
    items0_.version as version3_0_1_ 
  from OrderItem items0_ 
  where items0_.order_id=?
22:47:30,176 INFO NamedEntityGraphTest:59 - Number of items: 2
```

Hibernate 执行一个查询来获取所有的`Order`实体，并为 n 个`Order`实体中的每一个执行一个额外的查询来初始化`orderItem`关系。现在，您知道了为什么这种问题被称为 n+1 选择问题，以及为什么它会产生巨大的性能问题。



更糟糕的是，如果您没有检查`Hibernate`的统计数据，那么在一个小型的测试数据库中，您经常会认不出它。如果测试数据库不包含大量订单，代码片段只需要几十个查询。但是如果您使用包含几千个这样的数据库，那就完全不同了。

我之前说过，你可以很容易地避免这些问题。这是事实。当您从数据库中选择`Order`实体时，您只需要初始化`orderItem`关系。

但是，如果您在业务代码中使用关系，并且不使用`FetchType.EAGER`来总是获取相关的实体，请只这样做。这只是用另一个性能问题代替了您的 n+1 问题。

## 初始化与一个`@NamedEntityGraph`的关系

有几种不同的[选项来初始化关系](https://web.archive.org/web/20220926183539/http://www.thoughts-on-java.org/5-ways-to-initialize-lazy-relations-and-when-to-use-them/)。我更喜欢使用`@NamedEntityGraph`，这是`JPA 2.1`中引入的我最喜欢的[特性之一](https://web.archive.org/web/20220926183539/http://www.thoughts-on-java.org/2015/02/jpa-21-overview.html)。它提供了一种独立于查询的方式来指定`Hibernate`应该从数据库中获取的实体图。在下面的代码片段中，您可以看到一个简单图形的示例，它让`Hibernate`急切地获取实体的`items`属性：

```java
@Entity
@Table(name = "purchase_order")
@NamedEntityGraph(
  name = "graph.Order.items", 
  attributeNodes = @NamedAttributeNode("items"))
public class Order implements Serializable {

    ...
}
```

用`@NamedEntityGraph`注释定义一个实体图并不需要做太多的工作。您只需为图形提供一个唯一的名称，`Hibernate`将急切地为每个属性获取一个`@NamedAttributeNode`注释。在这个例子中，只有`items`属性映射了一个`Order`和几个`OrderItem`实体之间的关系。

现在，您可以使用实体图来控制获取行为或特定的查询。因此，您必须基于`@NamedEntityGraph`定义实例化一个`EntityGraph`，并将其作为提示提供给`EntityManager.find()`方法或您的查询。我在下面的代码片段中这样做，我从数据库中选择`id`为 1 的`Order`实体：

```java
EntityGraph graph = this.em.getEntityGraph("graph.Order.items");

Map hints = new HashMap();
hints.put("javax.persistence.fetchgraph", graph);

return this.em.find(Order.class, 1L, hints);
```

`Hibernate`使用这些信息创建一条`SQL`语句，从数据库中获取`Order`实体的属性和实体图的属性：

```java
17:34:51,310 DEBUG [org.hibernate.loader.plan.build.spi.LoadPlanTreePrinter] (pool-2-thread-1) 
  LoadPlan(entity=blog.thoughts.on.java.jpa21.entity.graph.model.Order) 
    - Returns 
      - EntityReturnImpl(
          entity=blog.thoughts.on.java.jpa21.entity.graph.model.Order, 
          querySpaceUid=<gen:0>, 
          path=blog.thoughts.on.java.jpa21.entity.graph.model.Order) 
        - CollectionAttributeFetchImpl(
            collection=blog.thoughts.on.java.jpa21.entity.graph.model.Order.items, 
            querySpaceUid=<gen:1>, 
            path=blog.thoughts.on.java.jpa21.entity.graph.model.Order.items)
          - (collection element) CollectionFetchableElementEntityGraph(
              entity=blog.thoughts.on.java.jpa21.entity.graph.model.OrderItem, 
              querySpaceUid=<gen:2>, 
              path=blog.thoughts.on.java.jpa21.entity.graph.model.Order.items.<elements>) 
            - EntityAttributeFetchImpl(entity=blog.thoughts.on.java.jpa21.entity.graph.model.Product,
                querySpaceUid=<gen:3>, 
                path=blog.thoughts.on.java.jpa21.entity.graph.model.Order.items.<elements>.product) 
    - QuerySpaces 
      - EntityQuerySpaceImpl(uid=<gen:0>, entity=blog.thoughts.on.java.jpa21.entity.graph.model.Order)
        - SQL table alias mapping - order0_ 
        - alias suffix - 0_ 
        - suffixed key columns - {id1_2_0_} 
        - JOIN (JoinDefinedByMetadata(items)) : <gen:0> -> <gen:1> 
          - CollectionQuerySpaceImpl(uid=<gen:1>, 
              collection=blog.thoughts.on.java.jpa21.entity.graph.model.Order.items) 
            - SQL table alias mapping - items1_ 
            - alias suffix - 1_ 
            - suffixed key columns - {order_id4_2_1_} 
            - entity-element alias suffix - 2_ 
            - 2_entity-element suffixed key columns - id1_0_2_ 
            - JOIN (JoinDefinedByMetadata(elements)) : <gen:1> -> <gen:2> 
              - EntityQuerySpaceImpl(uid=<gen:2>, 
                  entity=blog.thoughts.on.java.jpa21.entity.graph.model.OrderItem) 
                - SQL table alias mapping - items1_ 
                - alias suffix - 2_ 
                - suffixed key columns - {id1_0_2_}
                - JOIN (JoinDefinedByMetadata(product)) : <gen:2> -> <gen:3> 
                  - EntityQuerySpaceImpl(uid=<gen:3>, 
                      entity=blog.thoughts.on.java.jpa21.entity.graph.model.Product) 
                    - SQL table alias mapping - product2_ 
                    - alias suffix - 3_ 
                    - suffixed key columns - {id1_1_3_}
17:34:51,311 DEBUG [org.hibernate.loader.entity.plan.EntityLoader] (pool-2-thread-1) 
  Static select for entity blog.thoughts.on.java.jpa21.entity.graph.model.Order [NONE:-1]: 
  select order0_.id as id1_2_0_, 
    order0_.orderNumber as orderNum2_2_0_, 
    order0_.version as version3_2_0_, 
    items1_.order_id as order_id4_2_1_, 
    items1_.id as id1_0_1_, 
    items1_.id as id1_0_2_, 
    items1_.order_id as order_id4_0_2_, 
    items1_.product_id as product_5_0_2_, 
    items1_.quantity as quantity2_0_2_, 
    items1_.version as version3_0_2_, 
    product2_.id as id1_1_3_, 
    product2_.name as name2_1_3_, 
    product2_.version as version3_1_3_ 
  from purchase_order order0_ 
    left outer join OrderItem items1_ on order0_.id=items1_.order_id 
    left outer join Product product2_ on items1_.product_id=product2_.id 
  where order0_.id=?
```

对于一篇博客文章来说，只初始化一个关系就足够了，但是在一个真实的项目中，您很可能想要构建更复杂的图。让我们开始吧。

当然，您可以提供一组`@NamedAttributeNode`注释来获取同一个实体的多个属性，并且您可以使用`@NamedSubGraph`来为其他级别的实体定义获取行为。我在下面的代码片段中使用它不仅获取所有相关的`OrderItem`实体，还获取每个`OrderItem`的`Product`实体：

```java
@Entity
@Table(name = "purchase_order")
@NamedEntityGraph(
  name = "graph.Order.items", 
  attributeNodes = @NamedAttributeNode(value = "items", subgraph = "items"), 
  subgraphs = @NamedSubgraph(name = "items", attributeNodes = @NamedAttributeNode("product")))
public class Order implements Serializable {

    ...
}
```

如您所见，`@NamedSubGraph`的定义与`@NamedEntityGraph`的定义非常相似。然后，您可以在一个`@NamedAttributeNode`注释中引用这个子图来定义这个特定属性的获取行为。

这些注释的组合允许您定义复杂的实体图，您可以用它来初始化您在用例中使用的所有关系，并避免 n+1 选择问题。如果你想在运行时动态地指定你的实体图，你也可以通过`Java API`来实现。

### 逐个更新实体

如果你以面向对象的方式思考，那么一个接一个地更新实体是非常自然的。您只需获得想要更新的实体，并调用几个`setter`方法来更改它们的属性，就像您对任何其他对象所做的那样。

如果您只需要更改几个实体，这种方法就可以了。但是，当您处理实体列表时，效率会变得非常低，这是您可以在日志文件中很容易发现的第三个性能问题。您只需寻找一堆看起来完全相同的`SQL UPDATE`语句，正如您在以下日志文件中看到的：

```java
22:58:05,829 DEBUG SQL:92 - select 
  product0_.id as id1_1_, 
  product0_.name as name2_1_, 
  product0_.price as price3_1_, 
  product0_.version as version4_1_ from Product product0_
22:58:05,883 DEBUG SQL:92 - update Product set name=?, price=?, version=? where id=? and version=?
22:58:05,889 DEBUG SQL:92 - update Product set name=?, price=?, version=? where id=? and version=?
22:58:05,891 DEBUG SQL:92 - update Product set name=?, price=?, version=? where id=? and version=?
22:58:05,893 DEBUG SQL:92 - update Product set name=?, price=?, version=? where id=? and version=?
22:58:05,900 DEBUG SQL:92 - update Product set name=?, price=?, version=? where id=? and version=?
```

数据库记录的关系表示比面向对象的表示更适合这些用例。使用`SQL`，您可以只编写一条`SQL`语句来更新您想要更改的所有记录。

如果你使用`JPQL`、[native SQL](https://web.archive.org/web/20220926183539/http://www.thoughts-on-java.org/use-native-queries-perform-bulk-updates/) 或者 [CriteriaUpdate API](https://web.archive.org/web/20220926183539/http://www.thoughts-on-java.org/2013/10/criteria-updatedelete-easy-way-to.html) ，你可以用`Hibernate`做同样的事情。这三者非常相似，所以让我们在这个例子中使用`JPQL`。

您可以用与`SQL`中类似的方式定义`JPQL UPDATE`语句。您只需定义要更新哪个实体，如何更改其属性值，并在`WHERE`语句中限制受影响的实体。你可以在下面的代码片段中看到一个例子，我将所有产品的价格提高了 10%：

```java
em.createQuery("UPDATE Product p SET p.price = p.price*0.1").executeUpdate();
```

`Hibernate`基于`JPQL`语句创建一个`SQL UPDATE`语句，并将其发送给执行更新操作的数据库。

很明显，如果您必须更新大量的实体，这种方法要快得多。但是它也有一个缺点。`Hibernate`不知道哪些实体受到更新操作的影响，也不更新它的一级缓存。因此，您应该确保不要在同一个`Hibernate`会话中用`JPQL`语句读取和更新实体，否则您必须将它从缓存中分离出来。

## 总结

在这篇文章中，我向你展示了 3 个`Hibernate`的性能问题，这些问题可以在你的日志文件中找到。

其中两个是由大量`SQL`语句引起的。如果您使用`Hibernate`，这是性能问题的一个常见原因。`Hibernate`将数据库访问隐藏在其`API`之后，这使得猜测`SQL`语句的实际数量变得非常困难。因此，当您对持久层进行更改时，应该总是检查已执行的`SQL`语句。
