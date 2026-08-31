

# Hibernate 命名查询

> 原文：[链接](https://web.archive.org/web/20220930061024/https://www.baeldung.com/hibernate-named-query)

## 1. 概述

将 HQL 和 SQL 语句分散在数据访问对象（DAO）中，会导致代码可读性降低。因此，将所有 HQL 和 SQL 集中在一个位置，在实际的数据访问代码中仅引用它们，是一个更优的方案。Hibernate 通过命名查询功能支持这一实践。

命名查询是静态定义的查询，具有预先定义且不可更改的查询字符串。它们在会话工厂创建时被验证，从而使应用程序在出错时能够快速失败。

**本文将介绍如何使用 `@NamedQuery` 和 `@NamedNativeQuery` 注解来定义和使用 Hibernate 命名查询。**

## 2. 实体类

首先，我们来看一下本文将要使用的实体类：

```java
@Entity
public class DeptEmployee {
    @Id
    @GeneratedValue(strategy = GenerationType.SEQUENCE)
    private long id;

    private String employeeNumber;
    private String designation;
    private String name;

    @ManyToOne
    private Department department;

    // getters and setters
}
```

在我们的示例中，将根据员工编号来检索员工。

## 3. 命名查询（HQL）

要定义一个命名查询，我们使用`org.hibernate.annotations.NamedQuery`注解。它通过 Hibernate 的特性扩展了 `javax.persistence.NamedQuery`。

我们将它作为 `DeptEmployee` 类的注解来定义：

```java
@org.hibernate.annotations.NamedQuery(name = "DeptEmployee_findByEmployeeNumber", 
  query = "from DeptEmployee where employeeNumber = :employeeNo")
```

**请注意，每个 `@NamedQuery` 注解都附着在实体类或映射的超类上。但是，由于命名查询的作用域是整个持久化单元，我们应谨慎选择查询名称以避免冲突。** 我们通过在查询名中添加实体名称作为前缀来实现这一点。

如果一个实体有多个命名查询，我们可以使用 `@NamedQueries` 注解对它们进行分组：

```java
@org.hibernate.annotations.NamedQueries({
    @org.hibernate.annotations.NamedQuery(name = "DeptEmployee_FindByEmployeeNumber", 
      query = "from DeptEmployee where employeeNumber = :employeeNo"),
    @org.hibernate.annotations.NamedQuery(name = "DeptEmployee_FindAllByDesgination", 
      query = "from DeptEmployee where designation = :designation"),
    @org.hibernate.annotations.NamedQuery(name = "DeptEmployee_UpdateEmployeeDepartment", 
      query = "Update DeptEmployee set department = :newDepartment where employeeNumber = :employeeNo"),
...
})
```

注意，HQL 查询可以是 DML 风格的操作，因此它不限于 `select` 语句。例如，我们可以使用更新查询，如上文中的 `DeptEmployee_UpdateEmployeeDesignation` 所示。

### 3.1. 配置查询特性

我们可以通过 `@NamedQuery` 注解设置各种查询特性。让我们看一个例子：

```java
@org.hibernate.annotations.NamedQuery(
  name = "DeptEmployee_FindAllByDepartment", 
  query = "from DeptEmployee where department = :department",
  timeout = 1,
  fetchSize = 10
)
```

这里，我们配置了超时时间和获取大小。除了这两个，我们还可以设置以下特性：

* `cacheable` – 查询（结果）是否可缓存
* `cacheMode` – 本次查询使用的缓存模式；可以是 `GET`, `IGNORE`, `NORMAL`, `PUT`, 或 `REFRESH` 中的一个
* `cacheRegion` – 如果查询结果可缓存，指定要使用的查询缓存区域
* `comment` – 添加到生成的 SQL 查询中的注释；这通常是面向数据库管理员的
* `flushMode` – 本次查询的刷新模式，为 `ALWAYS`, `AUTO`, `COMMIT`, `MANUAL` 或 `PERSISTENCE_CONTEXT` 之一

### 3.2. 使用命名查询

现在我们已经定义了命名查询，让我们使用它来检索一个雇员：

```java
Query<DeptEmployee> query = session.createNamedQuery("DeptEmployee_FindByEmployeeNumber", 
  DeptEmployee.class);
query.setParameter("employeeNo", "001");
DeptEmployee result = query.getSingleResult();
```

这里，我们使用了 `createNamedQuery` 方法。它接受查询的名称并返回一个 `org.hibernate.query.Query` 对象。

## 4. 命名本地查询（SQL）

除了 HQL 查询，我们还可以将原生的 SQL 定义成命名查询。为此，可以使用 `@NamedNativeQuery` 注解。虽然它与 `@NamedQuery` 相似，但它需要更多的配置。

让我们通过一个例子来研究这个注解：

```java
@org.hibernate.annotations.NamedNativeQueries(
    @org.hibernate.annotations.NamedNativeQuery(name = "DeptEmployee_GetEmployeeByName", 
      query = "select * from deptemployee emp where name=:name",
      resultClass = DeptEmployee.class)
)
```

**由于这是一个本地查询，我们必须告诉 Hibernate 将结果映射到哪个实体类。因此，我们使用 `resultClass` 属性来做到这一点。**

**映射结果的另一种方法是使用 `resultSetMapping` 属性。在这里，我们可以指定一个预定义的 `SQLResultSetMapping` 的名称。**

请注意，我们只能使用 `resultClass` 和 `resultSetMapping` 中的一个。

### 4.1. 使用命名的本地查询

为了使用命名的本地查询，我们可以使用 `Session.createNamedQuery()`：

```java
Query<DeptEmployee> query = session.createNamedQuery("DeptEmployee_FindByEmployeeName", DeptEmployee.class);
query.setParameter("name", "John Wayne");
DeptEmployee result = query.getSingleResult();
```

或者使用 `Session.getNamedNativeQuery()`：

```java
NativeQuery query = session.getNamedNativeQuery("DeptEmployee_FindByEmployeeName");
query.setParameter("name", "John Wayne");
DeptEmployee result = (DeptEmployee) query.getSingleResult();
```

这两种方法之间的唯一区别是返回类型。第二种方法返回一个 `NativeQuery`，它是 `Query` 的子类。

## 5. 存储过程与函数

我们也可以使用 `@NamedNativeQuery` 注解来定义对存储过程和函数的调用：

```java
@org.hibernate.annotations.NamedNativeQuery(
  name = "DeptEmployee_UpdateEmployeeDesignation", 
  query = "call UPDATE_EMPLOYEE_DESIGNATION(:employeeNumber, :newDesignation)", 
  resultClass = DeptEmployee.class)
```

注意，虽然这是一个更新查询，但我们仍然使用了 `resultClass` 属性。这是因为 Hibernate 不支持纯本地标量查询。解决这个问题的方法是设置 `resultClass` 或 `resultSetMapping`。

## 6. 结论

在本文中，我们探讨了如何定义和使用命名 HQL 和本地查询。

完整源代码可在 [GitHub](https://web.archive.org/web/20220703153709/https://github.com/eugenp/tutorials/tree/master/persistence-modules/hibernate-queries) 上获取。

