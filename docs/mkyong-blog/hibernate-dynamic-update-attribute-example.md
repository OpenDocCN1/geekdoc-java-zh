
# Hibernate–动态更新属性示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/hibernate/hibernate-dynamic-update-attribute-example/>

## 什么是动态更新

动态更新属性告诉 Hibernate 是否在 SQL UPDATE 语句中包含未修改的属性。

## 动态更新示例

### 1. 动态更新=假

`dynamic-update`的默认值是 `false`，这意味着**在 Hibernate 的 SQL update 语句中包含未修改的属性**。

例如，获取一个对象并尝试修改它的值和更新它。

```java
Query q = session.createQuery("from StockTransaction where tranId = :tranId ");
q.setParameter("tranId", 11);
StockTransaction stockTran = (StockTransaction)q.list().get(0);

stockTran.setVolume(4000000L);
session.update(stockTran);
```

Hibernate 将生成下面的更新 SQL 语句。

```java
Hibernate:
    update
        mkyong.stock_transaction
    set
        DATE=?,
        PRICE_CHANGE=?,
        PRICE_CLOSE=?,
        PRICE_OPEN=?,
        STOCK_ID=?,
        VOLUME=?
    where
        TRAN_ID=?
```

Hibernate 将更新所有未修改的列。

### 2. 动态更新=真

如果将 `dynamic-update` 设置为 `true`，这意味着**在 Hibernate 的 SQL update 语句中排除未修改的属性**。

例如，获取一个对象，尝试修改它的值并再次更新它。

```java
Query q = session.createQuery("from StockTransaction where tranId = :tranId ");
q.setParameter("tranId", 11);
StockTransaction stockTran = (StockTransaction)q.list().get(0);

stockTran.setVolume(4000000L);
session.update(stockTran);
```

Hibernate 会生成不同的更新 SQL 语句。

```java
Hibernate:
    update
        mkyong.stock_transaction
    set
        VOLUME=?
    where
        TRAN_ID=?
```

Hibernate 将只更新修改过的列。

**性能问题**

在一个包含许多列（遗留设计）或包含大量数据的大表中，更新一些未修改的列是完全没有必要的，并且会对系统性能产生很大影响。

## 如何配置

您可以通过注释或 XML 映射文件配置 `dynamic-update` 属性。

### 1. 注释

```java
@Entity
@Table(name = "stock_transaction", catalog = "mkyong")
@org.hibernate.annotations.Entity(
        dynamicUpdate = true
)
public class StockTransaction implements java.io.Serializable {
```

### 2. XML 映射

```java
<class ... table="stock_transaction" catalog="mkyong" dynamic-update="true">
    <id name="tranId" type="java.lang.Integer">
        <column name="TRAN_ID" />
        <generator class="identity" />
    </id>
```

## 结论

这个小小的"**动态更新**"调整肯定会提高您的系统性能，强烈推荐这样做。

## 追踪

1. Hibernate-[动态插入属性](http://web.archive.org/web/20210109163601/http://www.mkyong.com/hibernate/hibernate-dynamic-insert-attribute-example/)示例

Tags : [hibernate](http://web.archive.org/web/20210109163601/https://mkyong.com/tag/hibernate/)

### 相关文章

* [Java.lang.ClassNotFoundException: org.objectweb.asm.Type](/web/20210109163601/https://mkyong.com/java/java-lang-classnotfoundexception-org-objectweb-asm-type/)
* [为什么我的项目选择 Hibernate？](/web/20210109163601/https://mkyong.com/hibernate/why-hibernate/)
* [记住序数参数是从 1 开始的！- HibernateTemplate](/web/20210109163601/https://mkyong.com/hibernate/remember-that-ordinal-parameters-are-1-based-hibernatetemplate/)
* [如何显示 Hibernate SQL 参数值 - P6](/web/20210109163601/https://mkyong.com/hibernate/how-to-display-hibernate-sql-parameter-values-solution/)
* [如何在 Hibernate - Logback 中配置日志记录](/web/20210109163601/https://mkyong.com/hibernate/how-to-configure-logging-in-hibernate-logback/)
* [org.hibernate.AnnotationException: Unknown Id.gene](/web/20210109163601/https://mkyong.com/hibernate/org-hibernate-annotationexception-unknown-id-generator/)
* [如何在 Eclipse 中安装 Hibernate / JBoss 工具](/web/20210109163601/https://mkyong.com/hibernate/how-to-install-hibernate-tools-in-eclipse-ide/)
* [如何生成 Hibernate 映射文件 & annotati](/web/20210109163601/https://mkyong.com/hibernate/how-to-generate-code-with-hibernate-tools/)
* [Maven 3 + Hibernate 3.6 + Oracle 11g 示例（XML](/web/20210109163601/https://mkyong.com/hibernate/maven-3-hibernate-3-6-oracle-11g-example-xml-mapping/)
* [Hibernate - 类型注解配置为 de](/web/20210109163601/https://mkyong.com/hibernate/hibernate-the-type-annotationconfiguration-is-deprecated/)
