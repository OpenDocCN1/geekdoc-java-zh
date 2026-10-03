
# JPA 和 Hibernate——标准对比 JPQL 对比 HQL 查询

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/jpql-hql-criteria-query>

JPA 的行为可能因具体使用环境而有很大差异。在本地环境或预发布环境中正常运行的代码，当面对生产环境中的真实规模数据库时，可能会表现糟糕（甚至直接失败）。

在生产环境中调试这类 JPA 问题非常困难——现有的应用程序性能监控工具在代码层面无法提供足够细粒度的洞察，而追踪每一个本应批量查询却逐个查询实体的情况，可能是一项非常耗时而艰巨的任务。

**Lightrun** 是一种在生产环境中进行调试的新方法。使用 Lightrun 的日志和快照功能，您现在无需开放入站端口、重新部署、重启甚至停止运行中的应用，即可在生产环境中获得调试器级别的细粒度信息。

此外，在运行时对 Lightrun 指标进行插桩，可以让您安全且实时地追踪持久化问题。想看看实际效果吗？**观看我们的 2 分钟教程**，了解如何使用 Lightrun 调试生产环境中的 JPA 性能问题：

[>> 使用 Lightrun 调试 Spring 持久化与 JPA 问题](/web/20220524055217/https://www.baeldung.com/lightrun-n-jpa)

## 1. 概览

在本教程中，我们将了解如何使用 JPA 和 Hibernate 进行查询，以及 Criteria、JPQL 和 HQL 查询之间的区别。标准查询使用户能够在不使用原始 SQL 的情况下编写查询。除了标准查询，我们还将探索如何编写 Hibernate 命名查询，以及如何在 Spring Data JPA 中使用`@Query`注解。

在我们深入研究之前，应当注意到，从 Hibernate 5.2 开始，Hibernate Criteria API 已被弃用。因此，**我们将使用 JPA Criteria API**（[参考链接](/web/20220524055217/https://www.baeldung.com/hibernate-criteria-queries)）作为示例，因为它是编写标准查询的新首选工具。因此，从现在开始，我们将其简称为标准 API。

## 2. 标准查询

通过在标准查询对象上应用不同的过滤器和逻辑条件，标准 API 有助于构建标准查询对象。这是操纵对象并从 RDBMS 表返回所需数据的另一种方法。

Hibernate `Session`的`createCriteria()`方法返回持久性对象实例，用于在应用程序中运行条件查询。简单地说，Criteria API 构建了一个应用不同过滤器和逻辑条件的标准查询。

### 2.1. Maven 依赖

让我们获取最新版本的 JPA 参考依赖（[参考链接](https://web.archive.org/web/20220524055217/https://search.maven.org/search?q=g:org.hibernate%20AND%20a:hibernate-core)）——它在 Hibernate 中实现 JPA——并将其添加到我们的`pom.xml`中：

```java
<dependency>
    <groupId>org.hibernate</groupId>
    <artifactId>hibernate-core</artifactId>
    <version>5.3.2.Final</version>
</dependency>
```

### 2.2. 使用条件查询和表达式

根据用户条件，**`CriteriaBuilder`控制查询结果**。它使用来自`CriteriaQuery`的`where()`方法，该方法提供了`CriteriaBuilder`表达式。

让我们来看看我们将在本文中使用的实体：

```java
public class Employee {

    private Integer id;
    private String name;
    private Long salary;

   // standard getters and setters
}
```

让我们来看一个简单的标准查询，它将从数据库中检索所有的 `Employee` 行：

```java
Session session = HibernateUtil.getHibernateSession();
CriteriaBuilder cb = session.getCriteriaBuilder();
CriteriaQuery<Employee> cr = cb.createQuery(Employee.class);
Root<Employee> root = cr.from(Employee.class);
cr.select(root);

Query<Employee> query = session.createQuery(cr);
List<Employee> results = query.getResultList();
session.close();
return results;
```

上述条件查询返回所有项目的集合。让我们看看它是如何发生的：

1.  `SessionFactory`对象创建了`Session`实例。
2.  `Session`使用`getCriteriaBuilder()`方法返回一个`CriteriaBuilder`的实例。
3.  `CriteriaBuilder`使用`createQuery()`方法。该方法创建了`CriteriaQuery()`对象，进一步返回查询实例。
4.  最后，我们调用`getResult()`方法来获取保存结果的查询对象。

让我们来看看`CriteriaQuery`中的另一个表达式：

```java
cr.select(root).where(cb.gt(root.get("salary"), 50000));
```

上述查询返回工资超过 50000 的雇员集合。

## 3. JPQL

JPQL（[参考链接](/web/20220524055217/https://www.baeldung.com/spring-data-jpa-query)）代表 Java 持久性查询语言。Spring Data 提供了多种创建和执行查询的方法，JPQL 就是其中之一。它使用 Spring 中的`@Query`注解来定义查询，以执行 JPQL 和原生 SQL 查询。**查询定义默认使用 JPQL。**

我们使用`@Query`注解在 Spring 中定义一个 SQL 查询。**由`@Query`注解定义的任何查询都比用`@NamedQuery`注解的命名查询具有更高的优先级。**

### 3.1. 使用 JPQL 查询

让我们使用 JPQL 构建一个动态查询：

```java
@Query(value = "SELECT e FROM Employee e")
List<Employee> findAllEmployees(Sort sort);
```

对于带参数的 JPQL 查询，Spring Data 按照与方法声明相同的顺序将方法参数传递给查询。让我们看几个将方法参数传递到查询中的示例：

```java
@Query("SELECT e FROM Employee e WHERE e.salary = ?1")
Employee findAllEmployeesWithSalary(Long salary);
```

```java
@Query("SELECT e FROM Employee e WHERE e.name = ?1 and e.salary = ?2")
Employee findEmployeeByNameAndSalary(String name, Long salary);
```

对于上述后一个查询，`name`方法参数作为索引 1 的查询参数传递，而`salary`参数作为索引 2 的查询参数传递。

### 3.2. 使用 JPQL 本地查询

我们可以使用本地查询直接在数据库中执行这些 SQL 查询，本地查询指的是真实的数据库和表对象。我们需要将`nativeQuery`属性的值设置为`true`来定义一个本地 SQL 查询。**本地 SQL 查询将在注解的`value`属性中定义。**

让我们来看一个本地查询，它展示了一个作为查询参数传递的索引参数：

```java
@Query(
  value = "SELECT * FROM Employee e WHERE e.salary = ?1",
  nativeQuery = true)
Employee findEmployeeBySalaryNative(Long salary);
```

在重构的场景下，使用命名参数使查询更易于阅读，也更不容易出错。让我们看一个 JPQL 和本机格式的简单命名查询示例：

```java
@Query("SELECT e FROM Employee e WHERE e.name = :name and e.salary = :salary")
Employee findEmployeeByNameAndSalaryNamedParameters(
  @Param("name") String name,
  @Param("salary") Long salary);
```

使用命名参数将方法参数传递给查询。我们可以通过在存储库方法声明中使用`@Param`注解来定义命名查询。因此，**`@Param`注解必须有一个与相应的 JPQL 或 SQL 查询名称相匹配的字符串值。**

```java
@Query(value = "SELECT * FROM Employee e WHERE e.name = :name and e.salary = :salary",
  nativeQuery = true)
Employee findUserByNameAndSalaryNamedParamsNative(
  @Param("name") String name,
  @Param("salary") Long salary);
```

## 4. HQL

HQL（[参考链接](/web/20220524055217/https://www.baeldung.com/hibernate-named-query)）代表 Hibernate 查询语言。它是一种类似于 SQL 的面向对象语言，**我们可以用它来查询我们的数据库**。然而，主要的一个缺点是其代码不可读。我们可以将查询定义为命名查询，并将它们放置在访问数据库的实际代码中。

### 4.1. 使用 Hibernate 命名查询

命名查询使用预定义的、不可更改的查询字符串来定义查询。这些查询是快速失败的，因为它们是在创建会话工厂期间进行验证的。让我们使用`org.hibernate.annotations.NamedQuery`注解定义一个命名查询：

```java
@NamedQuery(name = "Employee_FindByEmployeeId",
 query = "from Employee where id = :id")
```

每个`@NamedQuery`注解只将自己附加到一个实体类。我们可以使用`@NamedQueries`注解对一个实体的多个命名查询进行分组：

```java
@NamedQueries({
    @NamedQuery(name = "Employee_findByEmployeeId",
      query = "from Employee where id = :id"),
    @NamedQuery(name = "Employee_findAllByEmployeeSalary",
      query = "from Employee where salary = :salary")
})
```

### 4.2. 存储过程和表达式

总之，我们可以使用`@NamedNativeQuery`注解来定义存储过程和函数：

```java
@NamedNativeQuery(
  name = "Employee_FindByEmployeeId",
  query = "select * from employee emp where id=:id",
  resultClass = Employee.class)
```

## 5. 标准查询相对于 HQL 和 JPQL 查询的优势

与 HQL 相比，标准查询的主要优势在于其漂亮、干净且面向对象的 API。因此，我们可以在编译时检测到 Criteria API 中的错误。

此外，JPQL 查询和条件查询具有相同的性能和效率。

与 HQL 和 JPQL 相比，标准查询更加灵活，为编写动态查询提供了更好的支持。

但是 HQL 和 JPQL 提供了本地查询支持，而标准查询则不能。这是条件查询的缺点之一。

使用 JPQL 原生查询，我们可以轻松地编写复杂的连接，而在使用 Criteria API 时，这些连接则较难管理。

## 6. 结论

在本文中，我们主要研究了 Hibernate 和 JPA 中标准查询、JPQL 查询和 HQL 查询的基础知识。此外，我们还学习了如何使用这些查询，以及每种方法的优缺点。

和往常一样，本文中使用的完整代码示例可以在 GitHub 上找到（[参考链接](https://web.archive.org/web/20220524055217/https://github.com/eugenp/tutorials/tree/master/persistence-modules/spring-data-jpa-query-3)）。
