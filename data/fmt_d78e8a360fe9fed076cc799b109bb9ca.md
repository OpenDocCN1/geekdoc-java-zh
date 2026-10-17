
| `javax.persistence.validation.group.pre-persist` | 持久化前验证的目标组 |
| `javax.persistence.validation.group.pre-update` | 更新前验证的目标组 |
| `javax.persistence.validation.group.pre-remove` | 删除前验证的目标组 |

# 实体

作为 JPA 的核心部分，我们使用实体管理器进行简单的实体操作和复杂的 JPQL 查询执行。在操作单个实体时，`EntityManager` 接口可以被看作是一个通用的数据访问对象（DAO），它允许对任何实体进行 CRUD 操作（见列表 1）。

为了帮助你更好地理解这些方法，我使用了一个客户（`Customer`）与地址（`Address`）之间单向一对一关系的简单示例。两个实体都有自动生成的标识符（得益于 `@GeneratedValue` 注解），并且 `Customer`（见列表 5）对 `Address` 采用懒性加载（见列表 6）。

**列表 5. 具有单向一对一地址的 Customer 实体**

```java
@Entity
public class Customer {

    @Id
    @GeneratedValue
    private Long id;
    private String firstName;
    private String lastName;
    private String email;
    @OneToOne(fetch = LAZY)
    @JoinColumn(name = "address_fk")
    private Address address;

    // Constructors, getters, setters
}
```

**列表 6. Address 实体**

```java
@Entity
public class Address {

    @Id
    @GeneratedValue
    private Long id;
    private String street1;
    private String city;
    private String zipcode;
    private String country;

    // Constructors, getters, setters
}
```

这两个实体将映射到图 3 所示的数据库结构。注意 `ADDRESS_FK` 列是指向 `ADDRESS` 的外键。

![](img/c29e53007c33cf0fd2f7aed02ac4eb8b_209_0.png)

**图 3. CUSTOMER 和 ADDRESS 表**

为了提高可读性，后续章节中的代码片段假设 `em` 属性类型为 `EntityManager`，`tx` 类型为 `EntityTransaction`。

## 持久化实体

持久化一个实体意味着如果该数据尚不存在，则将其插入数据库。要做到这一点，有必要使用 `new` 操作符创建一个新的实体实例，设置属性值，在存在关联时将一个实体绑定到另一个实体（例如 `customer.setAddress(address)`），最后调用 `EntityManager.persist()` 方法，如列表 7 中的 JUnit 测试用例所示。

**列表 7. 持久化带有地址的客户**

```
Customer customer = new Customer("Anthony", "Balla", "aballa@mail.com");
Address address = new Address("Ritherdon Rd", "London", "8QE", "UK");
customer.setAddress(address);

// 持化对象
tx.begin();
em.persist(customer);
em.persist(address);
tx.commit();
```

在列表 7 中，`customer` 和 `address` 只是存在 JVM 内存中的两个对象。当实体管理器（变量 `em`）通过持久化它们（`em.persist()`）将它们考虑在内时，它们都变成了托管实体。此时，两个对象都具备了插入数据库的条件。当事务提交（`tx.commit()`）时，数据会被刷新到数据库，在 `ADDRESS` 表中插入一条地址记录，并在 `CUSTOMER` 表中插入一条客户记录。由于 `Customer` 是该关系的所有者，其表持有指向 `ADDRESS` 的外键。`assertNotNull` 表达式检查两个实体是否都接收到了生成的标识符（得益于持久化提供者）以及 `@Id` 和 `@GeneratedValue` 注解。

注意 `persist()` 方法的顺序：先持久化客户，然后是地址。如果反过来操作，结果是相同的。在此之前，实体管理器被描述为一级缓存。在事务提交之前，数据一直留在内存中，无法访问数据库。实体管理器缓存数据，当事务提交时，它会按照底层数据库期望的顺序刷新数据（遵守完整性约束）。由于 `CUSTOMER` 表中有外键，`ADDRESS` 的插入语句将首先执行，然后是 `CUSTOMER` 的插入语句。

本章中的大多数实体都没有实现 `Serializable` 接口。这是因为实体不需要按顺序排列就可以持久化到数据库中。它们以引用的方式从一个方法传递到另一个方法，当需要持久化时，就会调用 `EntityManager.persist()` 方法。但如果你需要按值传递实体（远程调用、容器等），则它们必须实现 `java.io.Serializable`（标记）接口。它告诉编译器必须强制要求实体类上的所有字段都是可序列化的，这样任何实例都可以被序列化为字节流，并使用远程方法调用（RMI）进行传递。

## 通过 ID 查找

要通过标识符查找实体，可以使用两种不同的方法。第一种是 `EntityManager.find()` 方法，它有两个参数：实体类和唯一标识符（见列表 8）。如果找到了实体，则返回它；如果未找到，则返回 `null` 值。

**列表 8. 通过 ID 查找客户**

```
Customer customer = em.find(Customer.class, id);
if (customer != null) {
    // 处理对象
}
```

第二方法是 `getReference()`（见列表 9）。它与 `find` 操作非常相似，具有相同的参数，但它获取的是对实体的引用（通过其主键），而不检索其数据。可以将其视为一个实体的代理，而不是实体本身。它适用于需要托管实体实例，但在可能访问实体主键之外不需要访问其他数据的情况。使用 `getReference()` 时，状态数据是懒加载的，这意味着如果你在实体脱离之前没有访问状态，数据可能就不在那里。如果未找到实体，则会抛出 `EntityNotFoundException`。

**列表 9. 通过引用查找客户**

```
try {
  Customer customer = em.getReference(Customer.class, id);
  // 处理对象
  assertNotNull(customer);
} catch (EntityNotFoundException ex) {
  // 未找到实体
}
```

## 移除实体

可以使用 `EntityManager.remove()` 方法移除实体。一旦被移除，实体将从数据库中删除，与实体管理器脱离，并且不再可以访问。在 Java 对象的角度，列表 10 显示了如何移除实体。

**列表 10. 创建和移除实体**

```
Customer customer = new Customer("Anthony", "Balla", "aballa@mail.com");
Address address = new Address("Ritherdon Rd", "London", "8QE", "UK");
customer.setAddress(address);

// 持久化对象
tx.begin();
em.persist(customer);
em.persist(address);
tx.commit();

assertNotNull(customer.getId());
assertNotNull(address.getId());

// 从数据库中移除客户
tx.begin();
em.remove(customer);
tx.commit();

// 客户不在数据库中，地址也不在
customer = em.find(Customer.class, customer.getId());
assertNull(customer);
address = em.find(Address.class, address.getId());
assertNull(address);
```

## 孤儿移除 (Orphan Removal)

为了数据一致性，孤儿对象是不理想的，因为会导致没有任何实体引用的行。通过 JPA，你可以通知持久化提供者在源被移除或关系破坏时（通过将属性设置为 `null`）自动删除目标。要包含此选项，我们在 `@OneToOne` 注解中添加 `orphanRemoval=true`。

**列表 11. 处理孤儿移除的客户实体**

```java
@Entity
public class Customer {

    @Id
    @GeneratedValue
    private Long id;
    private String firstName;
    private String lastName;
    private String email;

    @OneToOne(orphanRemoval = true)
    @JoinColumn(name = "address_fk")
    private Address address;

    // 构造函数、setter
}
```

**列表 12. 仅移除客户实体**

```
Customer customer = new Customer("Anthony", "Balla", "aballa@mail.com");
Address address = new Address("Ritherdon Rd", "London", "8QE", "UK");
customer.setAddress(address);

// 持久化对象
tx.begin();
em.persist(customer);
em.persist(address);
tx.commit();

assertNotNull(customer.getId());
assertNotNull(address.getId());

// 从数据库中移除客户实体
tx.begin();
em.remove(customer);
tx.commit();
```

## 与数据库同步

到目前为止，与数据库的同步是在提交时完成的。实体管理器是一个一级缓存，等待事务提交以便刷新数据到数据库，但当需要插入客户和地址时会发生什么？

```java
tx.begin();
em.persist(customer);
em.persist(address);
tx.commit();
```

所有待处理更改都需要一个 SQL 语句；在这里，只有在数据库事务提交时，才会产生并持久化两个插入语句。对于大多数应用程序，这种自动数据同步是足够的。数据库与持久化上下文中的实体进行同步，但可以显式地将数据刷新（flush）到数据库，或者从数据库刷新实体（refresh）。

如果数据在某一个点被刷新（flush）到数据库，而在代码稍后的位置调用了 `rollback()` 方法，则已刷新的数据将从数据库中移除。

## 刷新实体 (Flushing an Entity)

通过 `EntityManager.flush()` 方法，可以强制持久化提供者将数据刷新到数据库，但不会提交事务。这允许开发者手动触发实体管理器内部用于刷新持久化上下文（persistence context）的进程。

**列表 13. 将 Customer 实体刷新到数据库**

```
Customer customer = new Customer("Anthony", "Balla", "aballa@mail.com")
Address address = new Address("Ritherdon Rd", "London", "8QE", "UK")
customer.setAddress(address);
assertThrows(IllegalStateException.class, () -> {
    tx.begin();
    em.persist(customer);
    em.flush();
    em.persist(address);
    tx.commit();
});
```

列表 13 中发生了两个有趣的情况。首先，`em.flush()` 不等待事务提交，而是强制提供者刷新持久化上下文。在刷新时会生成并执行一条插入语句。其次，由于完整性约束，这段代码将无法工作。在没有显式的情况下，实体管理器会缓存所有的更改和排序，并以一种一致的方式为数据库执行它们。有了显式刷新，对 `CUSTOMER` 表的插入语句将执行，但 `Address` 实体的状态是不一致的。这是因为 `Address` 实体尚未被持久化，因此没有 id（id 被设置为 `null`），但所有其他属性都已设置（街道、城市等）。这就是为什么我们得到了一个 `IllegalStateException`：`Customer` 实体拥有一个除了标识符外都有值的 `Address`。这将导致事务回滚。已刷出的数据也会被回滚。显式刷新应谨慎使用，且仅在需要时使用。

## 刷新实体 (Refreshing an Entity)

`refresh()` 方法用于与刷新相反方向的数据同步，意味着它用数据库中存在的数据覆盖托管实体的当前状态。一个典型的用是使用 `EntityManager.refresh()` 方法撤销仅在内存中对实体进行的更改。列表 14 中的测试代码通过 Id 找到一个 `Customer`，更改了其第一个名，并使用 `refresh()` 方法撤销了这一更改。

**列表 14. 从数据库刷新 Customer 实体**

```
Customer customer = em.find(Customer.class, id);
assertEquals("Anthony", customer.getFirstName());

customer.setFirstName("William");
assertEquals("William", customer.getFirstName());

// 刷新客户实体
em.refresh(customer);
assertEquals("Anthony", customer.getFirstName());
```

## 持久化上下文的内容 (Content of the Persistence Context)

持久化上下文持有托管的实体。通过 `EntityManager` 接口，你可以检查实体是否被托管、将其解离，或清除持久化上下文中的所有实体。

### 包含 (Contains)

实体要么被实体管理器托管，要么没有。`EntityManager.contains()` 方法返回一个布尔值，允许你检查特定的实体实例是否在当前持久化上下文中。在列表 15 的测试用例中，一个 `Customer` 被持久化，你可以立即检查该实体是否被托管（`em.contains(customer)`）。答案是 `true`。此后调用了 `remove()` 方法，实体从数据库和持久化上下文中移除（`em.contains(customer)` 返回 `false`）。

**列表 15. 实体是否在持久化上下文中的测试用例**

```
Customer customer = new Customer("Anthony", "Balla", "aballa@mail.com")
assertFalse(em.contains(customer));

// 持久化对象
tx.begin();
em.persist(customer);
tx.commit();

assertTrue(em.contains(customer));

// 移除对象
tx.begin();
em.remove(customer);
tx.commit();

assertFalse(em.contains(customer));
```

## 清除与解离 (Clear and Detach)

`clear()` 方法非常直观：它清空持久化上下文，导致所有托管实体变为解离状态（请检查第 3 章介绍的“实体生命周期”，更多见第 7 章）。`detach(Object entity)` 将给定的实体从持久化上下移除。执行此类驱逐后，对实体进行的更改将不会同步到数据库。列表 16 创建了一个实体，检查它是否被托管，将其从持久化上下文中解离，并检查它是否已解离。

**列表 16. 检查 Customer 实体是否在持久化上下文中**

```
Customer customer = new Customer("Anthony", "Balla", "aballa@mail.com");

// 持久化对象
tx.begin();
em.persist(customer);
tx.commit();

assertTrue(em.contains(customer));

// 解离实体
em.detach(customer);

assertFalse(em.contains(customer));
```

## 合并实体 (Merging an Entity)
