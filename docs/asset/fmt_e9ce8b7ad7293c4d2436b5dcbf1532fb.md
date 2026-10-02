
# JPA 实体生命周期与 Bean Validation 集成

JPA 实体有一个特定的生命周期（`Persist`、`Update`、`Remove`、`Load`），Bean Validation 在此生命周期上挂了钩子。在从数据库持久化或更新实体之前，数据必须是有效的。另一个与 Bean Validation 有有趣集成的是 JPA 如何在生成 schema 时理解某些约束。如果 JPA 发现它能理解的 Bean Validation 约束，它可以使用列表 4 中的实体映射生成相应的 schema。`@NotNull` 提供了 SQL 中的 `not null`，而 `@Size(max)` 会影响 `varchar` 的大小。不需要添加 `@Column(nullable = false)`。仅有 `@NotNull` 就足够让数据库不允许空值。当然，如果验证太复杂或在 SQL 中没有对应项（例如 `@Positive`），它会被忽略。

**列表 4 创建表脚本**

```sql
CREATE TABLE BOOK
(
    ID BIGINT NOT NULL,
    DESCRIPTION VARCHAR(2000),
    ISBN VARCHAR(13),
    NBOFPAGES INTEGER,
    PRICE FLOAT,
    TITLE VARCHAR(255) NOT NULL,
    PRIMARY KEY (ID)
)
```

## CDI 集成

CDI 或上下文依赖注入是 Java EE 的核心技术。[2] 它的编程模型将几乎每个 Java EE 组件转换为可注入、可拦截和管理的 bean。CDI 构建在“松耦合、强类型”的概念之上，这意味着 bean 是松耦合的，但是以强类型的方式进行的。解耦通过为整个平台引入拦截器、装饰器和事件而进一步进一步。同时，CDI 通过统一作用域、上下文和生命周期管理将 Web 层和后端结合在一起。受益于它的事件总线，CDI 也是通过编写平台扩展来扩展 Java EE 的标准方式。

但让我们只用 CDI 进行注入。到目前为止，当我们需要 `EntityManager` 时，我们会通过编程方式给定 `EntityManagerFactory` 创建一个。使用后，我们还需要关闭它。

```java
EntityManager emf = Persistence.createEntityManagerFactory("cdbookstorePU");
EntityManager em = emf.createEntityManager();
em.close();
```

但通过 CDI，我们也可以通过 `@Inject` 注解通过依赖注入获取实体管理器。为了实现这一点，我们需要定义两个 CDI 生产者（producer）：一个创建 `EntityManagerFactory`，另一个创建 `EntityManager`。列表 5 使用 JPA API 构建了一个应用范围的实体管理器工厂。

**列表 5. 产生 EntityManagerFactory**

```java
@ApplicationScoped
public class EntityManagerFactoryProducer {

    @Inject
    private BeanManager beanManager;

    @Produces
    @ApplicationScoped
    public EntityManagerFactory produceEntityManagerFactory() {
        Map<String, Object> props = new HashMap<>();
        props.put("javax.persistence.bean.manager", beanManager);
        return Persistence.createEntityManager("cdbookstorePU");
    }

    public void close(@Disposes EntityManagerFactory emf) {
        emf.close();
    }
}
```

列表 5 显示了一个应用作用范围（application scoped）的，它在应用程序生命周期内初始化一次。它产生并销毁 `EntityManagerFactory`，使其可以被注入。同样，我们需要产生实体管理器（entity manager）。列表 6 注入了列表 5 中产生的 `EntityManagerFactory`，以便产生 `EntityManager`。

**列表 6. 产生 EntityManager**

```java
@ApplicationScoped
public class EntityManagerProducer {

    @Inject
    private EntityManagerFactory emf;

    @Produces
    @RequestScoped
    public EntityManager produceEntityManager() {
        return emf.createEntityManager();
    }

    public void close(@Disposes EntityManager em) {
        em.close();
    }
}
```

有了这些生产者后，我们可以在 `@Inject` 处注入一个实体管理器。列表 7 展示了 `AddressService` 如何注入 `EntityManager`，以便它可以持久化一个 `Address` 实体。

**列表 7. 注入 EntityManager**

```java
@ApplicationScoped
public class AddressService {

    @Inject
    private EntityManager em;

    public Address save(Address address) {
        em.getTransaction().begin();
        em.persist(address);
        em.getTransaction().commit();
        return address;
    }
}
```

从 JPA 2.1 开始，CDI 也被支持在实体监听器（entity listeners）中使用。因此，在列表 8 中，我们有一个实体监听器来检查邮政编码（zipcode）是否有效。它将此任务委托给名为 `ZipCodeChecker` 的辅助类，该类得益于 `@Inject` 注解被注入。

**列表 8. 注入辅助类**

```java
@ApplicationScoped
public class ZipCodeListener {

    @Inject
    private ZipCodeChecker checker;

    @PrePersist
    @PreUpdate
    private void checkZipCode(Address address) {
        if (!checker.isValid(address.getZipcode())) {
            throw new IllegalArgumentException("Invalid zipcode");
        }
    }
}
```

正如在列表 9 中所示，`ZipCodeChecker` 仅仅是一个 CDI Bean。

**列表 9. ZipCodeChecker 辅助类**

```java
@ApplicationScoped
public class ZipCodeChecker {

    private Pattern zipPattern = Pattern.compile("\\d{5}(-\\d{5})?");

    public boolean isValid(String zipcode) {
        if (zipcode == null) {
            return true;
        }
        return zipPattern.matcher(zipcode).matches();
    }
}
```

## JTA 集成

在 Java 中，事务管理通过 JSR 907 指定的 Java 事务 API (JTA) 完成。JTA 定义了一组接口，供应用程序或容器划定事务边界，并定义了处理事务管理器的 API。`javax.transaction` 包定义了这些接口。

到目前为止，本小节中的所有示例都使用 JPA 本地事务。资源本地事务（Resource local transactions）用于 Java SE 环境，而不是托管环境（Spring 或 Java EE）。这意味着我们在配置持久化单元的 `persistence.xml` 文件使用了 `transaction-type="RESOURCE_LOCAL"`：

```xml
<persistence-unit name="cdbookstorePU" transaction-type="RESOURCE_LOCAL">
```

一旦配置，本地事务通过 `EntityTransaction` API 定义，该接口包含了 `begin`、`commit` 和 `rollback` 等基础事务管理：

```java
entityManager.getTransaction().begin();
entityManager.getTransaction().commit();
entityManager.getTransaction().rollback();
```

在调用 `begin` 之前，无法调用 `persist`、`merge` 或 `remove` 等某些操作。在成功 `commit` 之后，`EntityManager` 可以继续使用，且所有受托管的对象都保持受托管状态。`rollback` 操作将回滚数据库事务。

JTA 事务用于 Spring 或 Java EE 等托管环境。要使用 JTA 事务，`persistence.xml` 中的 `transaction-type` 属性应设置为 `JTA`。如果配合数据源使用 JTA 事务，应使用 `<jta-datasource>` 元素引用已配置为 JTA 托管的数据源。

```xml
<persistence-unit name="cdbookstorePU" transaction-type="JTA">
    <jta-data-source>java:jboss/datasources/MyDS</jta-data-source>
    ...
</persistence-unit>
```

列表 10 显示了一个事务服务。得益于 `javax.transaction.Transactional` 注解，你知道该服务是事务性的。该注解负责拦截方法调用并在需要时启动事务。这就是为什么在代码中没有看到任何显式的 `tx.begin()` 或 `tx.commit()`。

**列表 10. 事务型服务**

```java
@ApplicationScoped
public class AddressService {

    @Inject
    private EntityManager em;

    @Transactional(REQUIRED)
    public Address save(Address address) {
        em.persist(address);
        return address;
    }

    @Transactional(MANDATORY)
    public String needsATTransaction() {
        return "Success";
    }
}
```

`@Transactional` 注解可以标记整个类或单个方法。它接受事务类型作为参数。根据你的需求，有几种事务类型可选（见表 1）。

**表 1. 事务类型**

| 属性 | 描述 |
| :--- | :--- |
| `REQUIRED` | 此属性（默认值）意味着方法必须在事务中被调用。如果从非事务客户端调用该方法，容器将创建一个新事务。如果客户端具有事务上下文，则业务方法将在客户端的上下文中运行。如果你进行的调用应该在事务中管理，则应使用 `REQUIRED`。 |
| `REQUIRES_NEW` | 容器在执行方法之前总是创建一个新事务，无论客户端是否在事务中执行。如果客户端在事务中运行，容器将临时挂起该事务，创建第二个事务，提交或回滚，然后恢复第一个事务。这意味着第二个事务的成功或失败不会对现有事务产生任何影响。当你不希望回滚影响客户端时，应使用 `REQUIRES_NEW`。 |
| `SUPPORTS` | 事务方法继承客户端的事务上下文。如果可用事务上下文，则方法将使用它；如果不可用，容器将在无事务上下文的情况下调用该方法。当你对数据库表有只读访问权限时，应使用 `SUPPORTS`。 |
| `MANDATORY` | 容器在调用业务方法之前要求存在事务，但不创建新事务。如果客户端具有事务上下文，则对其进行传播；如果没有，则将抛出 `javax.transaction.TransactionalException`。 |
| `NOT_SUPPORTED` | 事务方法不能在事务上下文中调用。如果客户端没有事务上下文，则什么都不会发生；如果有，容器将挂起客户端的事务，调用方法，并在方法返回时恢复事务。 |
| `NEVER` | 事务方法不得从事务型客户端调用。如果客户端在事务上下文中运行，容器将抛出 `javax.transaction.TransactionalException`。 |

## Spring Integration

Spring Framework 创建于 2003 年，是 Java 平台的一个应用程序框架和容器（基于控制反转原则）。[4] 该框架的核心功能可以被任何 Java 应用程序使用，并可以扩展以在 Java EE 平台上构建 Web 应用程序。

今天，“Spring”一词在不同的语境下有不同的含义。它可以指 Spring Framework 本身，也可以指随着时间推移产生的其他 Spring 项目，例如 Spring Boot、Spring MVC、Spring Security、Spring Data、Spring Cloud、Spring Batch、Spring WebFlux 等。

从历史上来看，Spring 在非常早期阶段就增加了对 JPA 的支持，直到今天 JPA 仍然是一项优先集成技术。事实上，你可以在基于 Spring 的应用程序的任何地方集成 JPA，如果你使用 Spring Data 更是如此。[5]

这次我们换一个例子。假设我们需要一个 REST API 将某些地址持久化到关系型数据库中。由于 Spring 支持 JPA，列表 11 中的代码不会让你感到意外。

**列表 11. 地址实体 (Address Entity)**

```java
@Entity
public class Address {

    @Id @GeneratedValue
    private Long id;

    private String street1;
    private String street2;
    private String city;
    private String state;
    private String zipcode;
    private String country;

    // Constructors, getters, setters
}
```

列表 12 定义了 REST 控制器，得益于几个注解，我们能够持久化和查询地址。`createAddress()` 方法通过 HTTP 请求中的 `@RequestBody Address` 接收 `Address`，并通过 `AddressRepository.save()` 方法将其存储在关系型数据库中。所有其他方法都有一个 `@GetMapping` 注解，表示它们在 HTTP 响应中返回数据。`count` 方法通过 `AddressRepository.count()` 方法返回数据库中的地址数量。`getAddressesByCountry()` 和 `getAddressesLikeZip()` 方法都根据某些参数返回地址列表。

**列表 12. Spring REST 控制器**

```java
@RestController
public class AddressEndpoint {

    private final AddressRepository addressRepository;

    @PostMapping("/addresses")
    public Address createAddress(@RequestBody Address address) {
        return addressRepository.save(address);
    }

    @GetMapping(value = "/addresses/count")
    public Long countAll() {
        return addressRepository.count();
    }

    @GetMapping(value = "/addresses/country/{country}")
    public List<Address> getAddressesByCountry(@PathVariable String country) {
        return addressRepository.findAllByCountry(country);
    }

    @GetMapping(value = "/addresses/like/{zip}")
    public List<Address> getAddressesLikeZip(@PathVariable String zip) {
        // 方法体未完整提供
    }
}
```
