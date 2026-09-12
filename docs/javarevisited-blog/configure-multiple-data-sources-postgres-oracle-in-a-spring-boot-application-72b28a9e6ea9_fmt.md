
# 在一个 Spring Boot 应用程序中配置多个数据源— Postgres 和 Oracle

> 原文：<https://medium.com/javarevisited/configure-multiple-data-sources-postgres-oracle-in-a-spring-boot-application-72b28a9e6ea9?source=collection_archive---------0----------------------->

最近，我需要将一个 Spring Boot 应用程序连接到两个不同的数据库。详情如下：

1. Postgresql 13.1，主机服务器 1，端口 5432，数据库— `mydb1`
2. Oracle 12c，主机—服务器 2，端口 1521，数据库— `mydb2`，服务名— `mydbservice`

## 步骤

### 1. 将以下依赖项添加到 `pom.xml`

```
<dependency>
   <groupId>com.oracle.database.jdbc</groupId>
   <artifactId>ojdbc8</artifactId>
   <scope>runtime</scope>
  </dependency>
<dependency>
   <groupId>org.postgresql</groupId>
   <artifactId>postgresql</artifactId>
   <scope>runtime</scope>
  </dependency>
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-configuration-processor</artifactId>
  </dependency>
```

### 2. 修改 `application.properties` 文件

```
spring.jpa.show-sql = true
spring.jpa.generate-ddl=false //ddl disabled

spring.db1.datasource.username=pguser
spring.db1.datasource.password=pguser
spring.db1.datasource.jdbc-url=jdbc:postgresql://server1:5432/mydb1
spring.db1.datasource.driver-class-name=org.postgresql.Driver

spring.db2.datasource.username=orauser
spring.db2.datasource.password=orauser
spring.db2.datasource.jdbc-url=jdbc:oracle:thin:@server2:1521:mydbservice
spring.db2.datasource.driver-class-name=oracle.jdbc.OracleDriver
```

**注意：** 对于 Oracle，我们在实体类中使用注解 `@Table(schema="mydb2", name="mytable")` 指定数据库名称。

### 3. 确保连接到 `mydb1` 或 `mydb2` 的存储库类应该属于不同的包

模型、服务和控制器类可以在同一个包中。

在这里，我的文件夹详细信息如下：

- 应用程序名称— `myapp`
- GroupId — `com.example`
- ArtifactId — `myapp`
- 包含 `main()` 方法的基础包— `com.example.myapp`
- 每个数据库的存储库类的单独包：
  - `com.example.myapp.db1repo`
  - `com.example.myapp.db2repo`
- 模型类的包— `com.example.myapp.domain`
- 控制器类包— `com.example.myapp.rest`
- 服务类包— `com.example.myapp.service`
- 配置类包— `com.example.myapp.config`

### 4. 创建两个配置类，为每个数据库源配置一个配置

在配置类中，我们将把域和存储库包配置到特定的数据源。

`Db1Config.java`

```
// db1 is our primary database
package com.example.myapp.config;

@Configuration
@EnableJpaRepositories(
  entityManagerFactoryRef = "db1EntityMgrFactory", 
  transactionManagerRef = "db1TransactionMgr", 
  basePackages = "com.example.myapp.db1repo")
@EnableTransactionManagement
public class Db1Config {

  @Bean(name = "datasource1")
  @ConfigurationProperties(prefix = "spring.db1.datasource")
  @Primary
  public DataSource dataSource() {
    return DataSourceBuilder.create().build();
  }

  @Bean(name = "db1EntityMgrFactory")
  @Primary
  public LocalContainerEntityManagerFactoryBean db1EntityMgrFactory(
    final EntityManagerFactoryBuilder builder,
    @Qualifier("datasource1") final DataSource dataSource) {
    return builder
      .dataSource(dataSource)
      .packages("com.example.myapp.domain")
      .persistenceUnit("db1")
      .build();
  }

  @Bean(name = "db1TransactionMgr")
  @Primary
  public PlatformTransactionManager db1TransactionMgr(
    @Qualifier("db1EntityMgrFactory") final EntityManagerFactory entityManagerFactory) {
    return new JpaTransactionManager(entityManagerFactory);
  }
}
```

`Db2Config.java`

```
package com.example.myapp.config;

@Configuration
@EnableJpaRepositories(
  entityManagerFactoryRef = "db2EntityMgrFactory", 
  transactionManagerRef = "db2TransactionMgr", 
  basePackages = "com.example.myapp.db2repo")
@EnableTransactionManagement
public class EpinetConfig {

  @Bean(name = "datasource2")
  @ConfigurationProperties(prefix = "spring.db2.datasource")
  public DataSource dataSource() {
    return DataSourceBuilder.create().build();
  }

  @Bean(name = "db2EntityMgrFactory")
  public LocalContainerEntityManagerFactoryBean db2EntityMgrFactory(
    final EntityManagerFactoryBuilder builder,
    @Qualifier("datasource2") final DataSource dataSource) {
    final Map<String, String> properties = new HashMap<>();
    properties.put("hibernate.physical_naming_strategy",
      "org.springframework.boot.orm.jpa.hibernate.SpringPhysicalNamingStrategy");
    return builder
      .dataSource(dataSource)
      .properties(properties)
      .packages("com.example.domain")
      .persistenceUnit("db2")
      .build();
  }

  @Bean(name = "db2TransactionMgr")
  public PlatformTransactionManager db2TransactionMgr(
    @Qualifier("db2EntityMgrFactory") final EntityManagerFactory entityManagerFactory) {
    return new JpaTransactionManager(entityManagerFactory);
  }
}
```

> **注意：**
>
> 在 `Db2Config` 类中，我们已经明确指定了 `hibernate.physical_naming_strategy` 的属性值。这样做是因为在 JPA Hibernate 查询到 Oracle 数据库的过程中，实体类属性名称不会自动从 camelCase 转换到 snake_case。
>
> 对于 PostgreSQL，属性名从 camelCase 到 snake_case 的默认转换工作正常，因此没有添加到 `Db1Config` 类中。如果在实体类中使用 `@Column(name="first_name")` 这样的注解显式指定了列名，则可以忽略这一点。

### 5. 连接到 PostgreSQL 数据库的示例域类

```
package com.example.myapp.domain;

@Entity
public class Student {

    @Id
    private Long id;
    private String firstName;
    private String lastName;
    // constructors and getter setter methods
}
```

### 6. 连接到 Oracle 数据库的示例域类

```
package com.example.myapp.domain;

@Entity
@Table(schema = "mydb2", name = "teacher")
public class Teacher {

    @Id
    private Long id;
    private String firstName;
    private String lastName;
    // constructors and getter setter methods
}
```

就是这样。

## 资源

- <https://examples.javacodegeeks.com/how-to-configure-multiple-data-sources-in-a-spring-boot-application/>
- <https://stackoverflow.com/questions/39001044/hibernate-improvednamingstrategy-doesnt-work>
- <https://javarevisited.blogspot.com/2020/02/top-5-courses-to-learn-postgresql-in.html>
- <https://javarevisited.blogspot.com/2021/05/top-5-oracle-database-and-plsql-online-courses.html>
