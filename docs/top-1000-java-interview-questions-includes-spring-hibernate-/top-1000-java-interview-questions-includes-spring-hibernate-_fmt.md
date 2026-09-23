
# 1000 道 Java 面试题：涵盖 Spring、Hibernate、微服务、GIT、Maven、JSP、AWS、云计算

# 献辞

致我们的读者！

39. Java 中静态方法和实例方法之间有什么区别？

385. 为什么 Java 8 接口中需要默认方法（`Default method`）？

386. Java 8 接口中静态方法（`Static method`）的目的是什么？

387. Java 8 日期时间 API 的核心思想是什么？

388. Java 8 中新的日期和时间 API 与旧的 `Date` API 相比有哪些优势？

389. Java 传统 日期时间 API 与 Java 8 日期时间 API 之间的主要区别get什么？

390. 如何在 Java 8 中获取两个日期或时间之间的间隔？

391. Java 8 引入的用于多核机器处理数组的新方法族是什么？

392. Java 8 如何解决多重继承中的菱问题（Diamond problem）？

393. Java 8 中 `Predicate`、`Supplier` 和 `Consumer` 之间的区别是什么？

394. 在接口中，如果不使用 `default` 关键字标记，可以定义默认方法吗？

395. 我们可以创建一个实现两个具有相同方法名和签的类吗？

396. Java 8 如何支持多重继承？

397. 如果我们创建一个继承基类并实现接口的类。如果基类和接口都有具有相同名称和参数的默认方法，那么 JVM 会选择哪一个？

398. 如果我们在类、其父类以及该类实现的接口中都定义了相同的方法，那么当我们使用接口引用和类对象访问它时，将调用哪一个定义？

399. 可以通过接口的引用访问接口的静态方法吗？

400. 如何通过反射在 Java 中获取参数（`Parameter`）名称？

401. Java 8 中的 `Optional` 是什么？

402. `Optional` 的用途有哪些？

403. `Optional` 中的哪个方法在值为 `null` 的情况下提供回退备机制（fallback mechanism）？

404. 如何使用 Java 8 的日期/时间 API 获取当前时间？

405. 在接口中可以定义静态方法吗？

406. 如何分析 Java 类和包之间的依赖关系？

407. Java 8 引入了哪些新的 JVM 参数？

408. Java 8 中引入了哪些流行的注解（annotations）？

409. Java 8 中的 `StringJoiner` 是什么？

410. Java 8 中 Lambda 表达式的类型是什么？

411. Lambda 表达式的目标类型（target type）是什么？

412. Java 8 中，带有默认方法的接口与抽象类之间的主要区别是什么？

## Java 陷阱（Tricky Questions）

413. `a = a + b` 和 `a += b` 表达式之间有区别吗？

414. 表达式 `1.0 / 0.00` 返回什么？会有编译错误吗？

415. 可以在多个类中使用多个 `main` 方法吗？

416. Java 允许重写私有或静态方法吗？

417. 在 `HashMap` 中放入一个已存在的键对象会发生什么？

418. 如何确保 N 个线程可以访问 N 个资源而不会产生死锁？

419. 如何从 Java 程序判断 JVM 是 32 位还是 64 位？

420. Java 中表示货币（如美元/英镑）的正确数据类型是什么？

421. 如何在 Java 中实现多重继承？

422. Java 中的 `++` 操作是线程安全的吗？

423. 如何从静态上下文中访问非静态变量？

424. 假设父类中有一个抛出 `NullPointerException` 的方法。我们可以用一个抛出 `RuntimeException` 的方法来重写它吗？

425. 如何在 Java 中标记一个数组变量为 `volatile`？

426. Java 中的线程本地变量（thread local variable）是什么？

427. Java 中 `sleep()` 和 `wait()` 方法的区别是什么？

428. 你可以创建一个包含可变对象的不可变对象（Immutable object）吗？

429. 如何将字节数组（Array of bytes）转换为字符串？

430. `CyclicBarrier` 和 `CountDownLatch` 类之间有什么区别？

431. `StringBuffer` 和 `StringBuilder` 之间有什么区别？

432. 哪个类包含 `clone` 方法？`Cloneable` 还是 `Object` 类？

433. 如何在 Java 中获取线程转储（thread dump）？

434. 可以将 `int` 变量转换为 `byte` 变量吗？如果 `int` 的值大于 `byte` 会发生什么？

435. 在 Java 中，我们可以在不显式强制转换的情况下将 `double` 值存储在 `long` 变量中吗？

436. `5*0.1 = 0.5` 会返回 true 还是 false？

437. 在 `int` 和 `Integer` 之间，哪一个占据的内存更多？

438. 在 Java 的 `switch` 语句可以使用 `String` 吗？

439. 可以在同一个类中使用多个 `main` 方法吗？

440. 在创建抽象类时，在构造函数内部调用抽象方法是一个好主吗？

441. 如何在 Java 中实现构造方法链（constructor chaining）？

442. 如何从 Java 代码查找 JVM 的内存使用情况？

443. Java 中 `x == y` 和 `x.equals(y)` 表达式之间有什么区别？

444. 如何保证垃圾回收（garbage collection）的发生？

445. `x.hashCode()` 方法与 `x.equals(y)` 之间是什么关系？

584. JDK 中解释器模式（Interpreter design pattern）的示例有哪些？

585. JDK 中中者模式（Mediator design pattern）的示例有哪些？

586. JDK 中策略模式的示例有哪些？

587. JDK 中访问者模式（Visitor design pattern）的示例有哪些？

588. 装饰器模式与代理模式有什么区别？

589. 依赖注入（DI）模式中 Setter 注入和构造函数注入的不同场景有哪些？

590. 使用代理模式的不同场景有哪些？

591. 适配器模式（Adapter design pattern）与代理模式的主要区别是什么？

592. 你会在何时使用适配器模式？

593. JDK 中适配器模式的示例有哪些？

594. 工厂模式与抽象工厂模式有什么区别？

595. 软件工程中的开闭原则（Open/closed design principle）是什么？

596. SOLID 设计原则是什么？

597. 什么是构建者模式（Builder design pattern）？

598. 面向对象设计中使用的设计模式分类？

599. 访问元素的设计模式是什么？

600. 我们如何在 Java 中实现生产者模式（Producer design pattern）？

601. 适用于添加新功能的设计模式是什么？

602. 使用什么设计模式解耦抽象与实现？

603. Android 中使用了什么设计模式？

604. 如何通过 `clone()` 方法防止创建多个单例？

605. 拦截器模式（Interceptor design pattern）的作用是什么？

606. 你使用过哪些架构模式（Architectural patterns）？

607. 外观模式（Façade design pattern）的流行用途？

608. 构建者模式与工厂模式有什么区别？

609. 备忘模式（Memento design pattern）是什么？

610. 什么是反模式（Anti-pattern）？

611. 数据访问对象（DAO）设计模式是什么？

## Spring 问题

612. 什么是 Spring 框架？

613. Spring 框架在软件开发中的好处是什么？

614. Spring 核心容器（Core Container）包含哪些模块？

615. Spring 数据访问/集成层包含哪些模块？

616. Web 层包含哪些模块？

617. Spring 核心容器模块的主要用途是什么？

618. Spring Test 模块可以进行什么样的测试？

619. `BeanFactory` 在 Spring 框架中的作用是什么？

620. Spring 中流行的 `BeanFactory` 实现是哪一个？

621. Spring 中的 `XMLBeanFactory` 是什么？

622. Spring 中 AOP 模块的用途是什么？

623. Spring JDBC 抽象层模块的好处是什么？

624. Spring 如何支持对象关系映射（ORM）集成？

625. Spring框架中的 Web 模块是如何工作的？

626. Spring MVC 模块的主要用途是什么？

627. Spring 配置文件的目的是什么？

628. Spring IoC 容器的目的是什么？

629. 反转控制（IOC）原则的主要优势是什么？

630. IOC 容器支持 Bean 的饿实例化（Eager Instantiation）还是懒加载（Lazy loading）？

631. Spring 中 `ApplicationContext` 的好处是什么？

632. 你如何在 Spring 框架中实现 `ApplicationContext`？

633. 说明 Spring 中 `ApplicationContext` 和 `BeanFactory` 的区别？

634. 在 Spring 中，`ApplicationContext` 和 `BeanFactory` 哪一个更优？

635. 一个典型的基于 Spring 的应用程序的主要组件有哪些？

636. 解释 Spring 框架中的依赖注入（DI）概念？

637. 依赖注入（DI）中不同的角色有哪些？

638. Spring 框架提供了哪些种依赖注入机制？

639. 在 Spring 框架中，哪种依赖注入更好？构造函数注入还是 Setter 注入？

640. 依赖注入（DI）有哪些优势？

641. 依赖注入（DI）有哪些缺点？

642. 什么是 Spring Bean？

643. Spring Bean 的定义包含哪些内容？

644. 向 Spring 容器提供配置元数据的不同方式有哪些？

645. Spring 支持哪些不同的 Bean 作用范围（Scopes）？

646. 你如何在 Spring 中定义 bean 的作用范围？

647. 假设 Spring Framework 中的单例（Singleton） Bean 是线程安全的吗？

648. Spring 框架中使用了哪些设计模式？

649. Spring 框架中 Bean 的生命周期是什么？

650. Bean 生命周期中的方法主要分为哪两大类？

651. 我们可以覆盖 Spring 中 Bean 的生命周期方法吗？

652. Spring 中的内部 Bean（Inner beans）是什么？

653. 我们如何在 Spring 框架中注入 Java 集合（Collection）？

654. Spring 中的 Bean 组配（wiring）是什么？

655. Spring 中的自动装配（Autowiring）是什么？

656. Spring 支持哪些不同的自动装配模式？

657. Spring 框架中自动装配可能失效的场景有哪些哪些？

658. Spring 中允许注入 `null` 或空字符串值吗？

659. Spring 中基于 Java 的配置（Java-based Configuration）是什么？

660. `@Configuration` 注解的作用是什么？

661. 全量 `@Configuration` 和 “lite” `@Beans` 模式之间的区别是什么？

662. 在 Spring 框架中，什么是基于注解的容器配置？

663. 你如何在 Spring 中开启基于注解的装配？

664. `@Autowired` 注解是什么？

665. `@Required` 注解是什么？

666. 在 Spring 中启用 `RequiredAnnotationBeanPostProcessor` 的两种方式有哪些？

667. Spring 中的 `@Qualifier` 注解是什么？

668. Spring 框架如何让开发者的 JDBC 编码变得更容易？

669. `JdbcdbTemplate` 的作用是什么？

670. 使用 Spring DAO 有哪些好处？

671. 在 Spring 中使用 Hibernate 的不同方式有哪些？

672. Spring 支持哪些类型的对象关系映射（ORM）？

673. 你如何通过 `HibernateDaoSupport` 整合 Spring 和 Hibernate？

674. Spring 框架支持的事务管理不同类型有哪些？

675. Spring 框架提供的事务管理提供了哪些好处？

676. 在声明式事务管理和程序式事务管理之间进行选择，你会选择哪种方法？

677. 什么是面向切面编程（AOP）？

678. Spring 中的切面（Aspect）是什么？

679. 在 Spring AOP 中，关注点（Concern）和横切关注点（Cross cutting concern）的主要区别是什么？

680. Spring AOP 中的连接点（Joinpoint）是什么？

681. Spring AOP 中的通知（Advice）是什么？

682. Spring AOP 中不同类型的通知（Advice）有哪些哪些？

683. Spring AOP 中的切入点（Pointcut）是什么？

684. Spring AOP 中的引入（Introduction）是什么？

685. Spring AOP 中的目标对象（Target object）是什么？

686. Spring AOP 中的代理（Proxy）是什么？

687. Spring 中不同的自动代理创建器（AutoProxy creators）有哪些哪些？

688. Spring AOP 中的织入（Weaving）是什么？

689. 在 Spring AOP 中，织入是在编译时还是运行时完成的？

690. 什么是基于 XML Schema 的 Aspect 实现？

691. Spring AOP 中基于注解的切面实现是什么？

692. Spring MVC 框架是如何工作的？

693. 什么是 `DispatcherServlet`？

694. 在 Spring MVC 中可以有多个 `DispatcherServlet` 吗？

695. 什么是 `WebApplicationContext`？

696. Spring MVC 中的 Controller？

697. `@RequestMapping` 注解是什么？

698. Spring MVC 有哪些特性？

699. Spring 中，单例（Singleton）和原型（Prototype）作用范围的区别是什么？

700. 你如何决定 bean 的作用范围？

701. Spring 中基于 Setter 的依赖注入（DI）有哪些哪些？

702. 基于构造函数的依赖注入（DI）在 Spring 中是怎样的？

703. Spring 中依赖注入（DI）的哪些方式？

704. Spring 中的 `FileResource` 是什么？

705. 在 Spring 中如何处理文件？

706. Spring MVC 允许哪些操作？

707. Spring MVC 提供了哪些事件？

708. Spring MVC 中的 `ContextLoader` 是什么？

709. 在 Spring 中如何处理异常？

710. Spring Boot 是什么？

711. 什么是 Spring？

712. Hibernate 是什么？

713. 什么是对象关系映射（ORM）？

714. Hibernate 的作用是什么？

715. 什么是接口失配（Impedance mismatch）？

716. 对象关系失配有哪些哪些问题？

717. Hibernate 的核心特性有哪些？

718. Hibernate 支持哪些接口？

719. 如何将类映射到数据库表？

720. Hibernate 如何使用 `.hbm` 文件？

721. Hibernate 中的 `SessionFactory` 是什么？

722. Hibernate 为什么要使用 POJO？

723. 什么是 Hibernate 查询语言（HQL）？

724. 如何在 Hibernate 中调用存储过程？

725. Hibernate 中的 Criteria API 是什么？

726. 为什么要使用 `HibernateTemplate`？

727. 如何查看 Hibernate 生成的 SQL？

728. Hibernate 支持哪些类型的集合？

729. `session.save()` 和 `session.saveUpdate()` 的区别是什么？

730. Hibernate 的统计信息有哪些？

731. 如何获取 `SessionFactory` 信息？

732. 瞬态状态（Transient state）是什么？

733. 离散状态（Detached state）是什么？

734. 脏检查（Dirty Checking）的作用是什么？

735. Hibernate 回调接口（Callback interface）是什么？

736. ORM 有哪些级别哪些？

737. 如何配置 Hibernate？

738. 什么是查询缓存（Query Cache）？

739. Hibernate 支持哪些类型的关联映射？

740. 单向关联映射的类型有哪些哪些？

741. 什么是工作单元（Unit of Work）模式？

742. 在 Hibernate 中，对象如何进入离散状态？

743. 如何使用 Criteria 对结果进行排序？

744. Hibernate 示例是如何工作的？



# Java 面试题

## Java 基础

### 1. JDK 和 JRE 的区别是什么？

JDK 代表 Java 开发工具包。它包含了开发 Java 程序所需的工具和库。它包含了编译 Java 程序所需的编译器和调试器。JRE 代表 Java 运行环境。包含在 JDK 中。JRE 提供运行 Java 程序所需的库和 JVM。

### 2. 什么是 Java虚拟机（JVM）？

Java虚拟机是一个执行字节码的抽象机器。不同的硬件和软件平台有不同的 JVM。因此 JVM 是依赖平台的。JVM 负责加载、验证和执行字节码。

### 3. JVM 分配的不同内存区域有哪些？

在 Java 中，JVM 为不同的进程、方法和对象分配内存。JVM 分配的一些内存区域包括：

- **类加载器（ClassLoader）**：它是 JVM 用于加载类的组件。
- **类区**：存储类结构，如运行时常量池、字段和方法数据以及方法代码。
- **堆（Heap）**：堆在运行时创建，它是存储对象的运行时数据区域。
- **栈（Stack）**：栈在运行时存储局部变量和部分结果。它也有助于方法的调用和返回值。每个线程在创建时都会创建一个私有的 JVM 栈。
- **程序计数器（Program Counter Register）**：该内存区域包含正在执行的 Java 虚拟机指令的地址。
- **原生方法栈（Native Method Stack）**：该区域为应用程序中所有的原生方法保留。

### 4. 什么是 JIT 编译器？

即时编译器也称为 JIT 编译器用于提高 Java 的性能。它是默认开启的。它是执行时而非更早进行的编译。Java 通过将其包含在 JVM 中普及了 JIT 编译器的使用。

### 5. Java 平台与其他平台有什么不同？

Java 是一种平台无关的语言。Java 编译器将 Java 代码转换为字节码，字节码可以由 JVM 解释。几乎所有流行的平台都编写了 JVM。

Java 字节码可以相同的方式运行在任何支持的平台上。而其他语言需要为特定平台编译的库才能运行。

### 6. 为什么人们说 Java 是一种“编写一次，到处运行”的语言？

你可以在 Windows 上编写 Java 代码并在 Windows 平台上进行编译。你从 Windows 平台获得的类文件和 jar 文件可以在 Unix 环境中直接运行。因此，它是一种真正与平台无关的语言。

这种可移植性的背后都是 Java 字节码（byte code）。Java 编译器生成的字节码可以被任何 JVM 解释。因此，在 Java 中编写程序并期望它们运行在任何平台上变得轻而易举得多。

Java 编译器 `javac` 编译 java 代码，而 JVM `java` 运行这些代码。

### 7. Java 中的 ClassLoader 是如何工作的？

在 Java 中，ClassLoader 是一个用于在 JVM 中加载文件的类。ClassLoader 从它们的物理文件位置（例如文件系统、网络位置等）加载文件。

Java 中主要有三种类型的 ClassLoader。

## Hibernate

### 745. Hibernate 事务管理是如何工作的？

### 746. 如何标记实体/集合为不可变？

### 747. 从数据库检索对象的不同方式有哪些？

### 748. 如何自动生成主键？

### 749. 你如何将离散状态的对象重新关联（re-attach）？

### 750. Hibernate 的一级缓存是什么？

### 751. Hibernate 有哪些可用的二级缓存？

### 752. 哪是 Hibernate 默认的事务工厂？

### 753. 如何选项禁用二级缓存？

### 754. Hibernate 中不同的获取策略有哪些？

### 755. 立即加载与懒性加载的区别是什么？

### 756. 什么是额外懒性加载（Extra lazy fetching）？

### 757. 如何通过初始化策略检查集合是否已初始化？

### 758. 缓存映射的哪些策略？

### 759. Hibernate 中 Set 和 Bag 的区别是什么？

### 760. 如何监控 Hibernate 的性能？

### 761. 如何检查对象处于持久、离散还是瞬态状态？

## Maven

### 772. 什么是 Maven？

### 773. Maven 的主要特征有哪些？

### 774. 使用 Maven 管理的项目之间有什么区别？

### 775. Maven 的主要优势有哪些？

### 776. 为什么我们说“Maven 约定优于配置”？

### 777. Maven 这样的构建工具的职责是什么？

### 778. Ant 和 Maven 有什么区别？

### 779. Maven 中的 MOJO 是什么？

### 780. Maven 中的仓库（Repository）是什么？

### 781. Maven 有哪些类型的仓库？

### 782. Maven 中的本地仓库是什么？

### 783. Maven 中的中央仓库是什么？

### 784. Maven 中的远程仓库是什么？

### 785. 为什么我们不将 jar 包存储在 CVS 或其他版本控制系统中，而是使用 Maven 仓库？

### 786. 任何人都可以向中央仓库上传 JARS 或构件吗？

### 787. 什么是 POM？

### 788. 什么是 Super POM？

### 789. POM 文件中主要的必需元素有哪些？

### 790. Maven 构建生命周期（Build lifecycle）中的阶段有哪些？

### 791. 使用什么命令来打包你的 Maven 项目？

### 792. Maven 项目全限定构件名称（fully qualified artifact name）的格式是什么？

### 793. Maven 中的 Archetype 是什么？

### 794. Maven 中生成 Archetype 的命令是什么？

### 795. Maven 的三个主要的构建生命周期是什么？

### 796. Maven 插件（plugin）的主要用途是什么？

### 797. 如何找到正在使用的插件版本？

### 798. Maven 有哪些不同类型的配置（profile）？在何处定义这些配置？

### 799. Maven 有哪些不同的配置文件？在哪里找到这些文件？

### 800. 在 settings.xml 中可以找到哪些主要元素？

### 801. 如何检查系统中 Maven 的版本？

### 802. 如何验证 Windows 上是否安装了 Maven？

### 803. 什么是 Maven 构件（artifact）？

### 804. Maven 中不同的依赖范围（dependency scopes）有哪些？

### 805. 我们如何在 Maven 中排除一个依赖？

### 806. Maven 如何查找与依赖对应的 JAR 包？

### 807. Maven 中的传递性依赖（transitive dependency）是什么？

### 808. Maven 中的被排除依赖（Excluded dependencies）是什么？

### 809. Maven 中的可选依赖（Optional dependencies）是什么？

### 810. 成功编译 Maven 项目后在何处找到类文件？

### 811. Maven 中源码（source）、测试（test）和构建（build）目录的默认位置是什么？

### 812. Maven 中 jar:jar 目标（goal）的结果是什么？

### 813. 如何从 Maven 的执行中获取调试或错误信息？

### 814. Maven 中发布版本（Release version）和快照版本（SNAPSHOT version）有什么区别？

### 815. 如何在 Maven 中运行测试类？

### 816. 有时 Maven 会编译测试类但不运行？原因可能是什么？

### 817. 我们如何在 Maven 中跳过测试运行？

### 818. 我们可以在 Maven 中为项目创建自己的目录结构吗？

### 819. Gradle 和 Maven 有什么区别？

### 820. 继承（Inheritance）和多模块（Multi-module） Maven 有什么区别？

### 821. Maven 中的构建可移植性（Build portability）是什么？

## Git

### 822. 如何在 Git 中查看最近的 n 次提交？

### 823. 如何知道 Git 中的分支是否已经合并到 master 分支？

### 824. `git stash drop` 的目的是什么？

### 825. Git 中的 HEAD 是什么？

### 826. Git 中流行的分支策略是什么？

### 827. 什么是 SubGit？

### 828. `git instaweb` 的用途是什么？

### 829. 什么是 git hooks（钩子）？

### 830. 什么是 Git？

### 831. Git 中的仓库（repository）是什么？

### 832. Git 的主要优点有哪些？

### 833. Git 的缺点有哪些？

### 834. Git 和 SVN 之间有什么主要区别？

### 835. 如何为你的项目启动 Git？

### 836. Git 中的 `git clone` 是什么？

### 837. 如何在 Git 中创建一个仓库？

### 838. 在 Git 中开始工作的不同方式有哪些？

### 839. Git 用什么语言编写的？

### 840. Git 中的 `git pull` 命令在内部做了什么？

### 841. Git 中的 `git push` 命令在内部做了什么？

### 842. 什么是 `git stash`？

### 843. Git 中 `stage`（暂存）的含义？

### 844. `git config` 命令的目的是什么？

### 845. 如何查看 Git 安装的配置设置？

### 846. 如何在 Git 中使用 commit 命令写信息？

### 847. Git 提交对象（commit object）内部存储了什么？

### 848. 在一个 Git 仓库中可以创建多少个 heads？

### 849. 为什么我们在 Git 中创建分支？

### 850. Git 中可以创建哪些类型的分支？

### 851. 如何在 Git 中创建一个新分支？

### 852. 如何向主分支添加新功能？

### 853. Git 中的 pull request（拉取请求）是什么？

### 854. Git 中的合并冲突（merge conflict）是什么？

### 855. 我们如何解决冲突？

### 856. 使用什么命令会删除分支？

### 857. 对于未合并的更改使用什么命令？

### 858. 我们如何进行合并（merge）？

### 859. Git 中的变基（Rebasing）是什么？

### 860. 变基的黄金法则是什么？

### 861. 如何使用交互式变基（Interactive Rebasing）？

### 862. 使用什么命令进行变基？

### 863. `git clone` 和 remote 之间有什么区别？

### 864. 什么是版本控制？

### 865. 你使用 GUI 是为了什么？

### 866. `git diff` 的用途是什么？

### 867. 什么是 rerere？

### 868. 哪些是流行的 git 命令？

### 869. `git status` 的用途是什么？

### 870. `git status` 和 `git add` 之间有什么区别？

### 871. `rm` 命令是什么？

### 872. 我们如何使用 stash？

### 873. Git 中的 cherry-pick 是什么？

### 874. 什么是 shortlog？

### 875. 如何找到被修改的文件名？

### 876. 在 push 事件时运行什么自动化脚本？

### 877. 提交对象包含什么？

### 878. Git hooks 用什么语言编写的？

### 879. 提交信息（commit message）是什么？

### 880. Git 如何保护代码？

### 881. Git 提供了什么灵活性？

### 882. 我们如何修改提交信息？

### 883. 修正提交（amending a commit）是什么？

### 884. 什么是裸仓库（bare repository）？

### 885. 你将如何删除分支？

### 886. 曾经推送到现在的提交？

### 887. 如何切换到一个新分支？

### 888. 如何将 n 次提交压缩为一个提交？

### 889. 你可以创建哪些类型的 Tag（标签）？

### 890. 我们如何重命名远程（remote）？

### 891. 有人使用 `git checkout` 而有人使用 `git switch`。这是为什么可能的？

### 892. 如何查看每个分支的最后提交？

### 893. origin 是 Git 中的特殊分支吗？

### 894. 如何配置 Git 使得每次都询问密码？

### 895. Git 用于数据传输的四种主要协议有哪些？

### 896. Git 协议是什么？

### 897. 我们如何在没有 push 权限的项目上工作？

### 898. `git grep` 是什么？

### 899. 如何在 Git 中重新排序提交？

### 900. 你将如何将一个提交拆分为多个提交？

### 901. Git 中的 filter-branch 是什么？

## AWS

### 931. Amazon Glacier 的用途是什么？

### 932. 可以在 Amazon S3 已启用版本控制存储桶上禁用版本控制吗？

### 933. Amazon S3 跨区域复制（Cross Region Replication）的场景有哪些？

### 934. 可以在不启用存储桶版本控制的情况下在 Amazon S3 中进行跨区域复制吗？

### 935. Amazon S3 对象生命周期（Object Lifecycle Management）中有哪些类型的操作？

### 936. 如何通过 Amazon CloudFront 让应用程序获得更高的性能？

### 937. Amazon CloudFront 边缘缓存（Regional Edge Cache）背后的机制是什么？

### 938. 流媒体内容（Streaming content）有什么优势？

### 939. AWS 中的 Lambda@Edge 是什么？

### 940. Amazon CloudFront 触发了哪些事件？

### 941. Amazon CloudFront 中的地理定位（Geo Targeting）是什么？

### 942. Amazon CloudFront 的主要功能有哪些？

### 943. Amazon S3 有哪些安全机制？

## 云计算

### 944. 云计算有哪些优势？

### 945. 云计算中的按需计算（On-demand computing）是什么？

### 946. 云计算有哪些不同的层？

### 947. 基础设施即服务（IAAS）供应商提供哪些资源？

### 948. 平台即服务（PaaS）的优势是什么？

### 949. PaaS 的主要优点有哪些？

### 950. PaaS 的主要缺点是什么？

### 951. 云计算中有哪些不同的部署模型？

### 952. 可扩展性（Scalability）和弹性（Elasticity）的区别是什么？

### 953. 软件即服务（SaaS）是什么？

### 954. 云计算中有哪些类型的数据中心？

### 955. 解释软件即服务（SaaS）云环境的各种模式？

### 956. 云环境中安全方面需要注意的重要事项有哪些？

### 957. 为什么在云计算环境中使用 API？

### 958. 云安全管理有哪些不同的领域？

### 959. 云端数据中心的主要成本因素有哪些？

### 960. 我们如何衡量云端服务？

### 961. 传统数据中心与云环境有什么不同？

### 962. 你如何在云环境中优化应用程序的可用性？

### 963. 在云中实施 IaaS 策略的要求是什么？

## Docker

### 964. 什么是 Docker？

### 965. Docker 镜像（image）和 Docker 容器（container）之间的区别是什么？

### 966. 如何从 Docker 中删除镜像？

### 967. Docker 容器与虚拟机管理器（hypervisor）有什么不同？

### 968. 可以用 json 文件而不是 yaml 文件写 compose 文件吗？

### 969. 可以 Docker 在一台服务器上运行多个应用吗？

### 970. Docker 的常见用途场景？

### 971. Docker-compose 的主要功能有哪些？

### 972. Docker 最流行的用途是什么？

### 973. 开源开发在 Docker 普及中起了什么作用？

## UNIX Shell

### 974. 如何删除当前目录下的所有文件？包括子目录下两层深的文件。

### 975. Bash 脚本中 -v 和 -x 选项有什么区别？

### 976. Unix 命令中的过滤器（Filter）是什么？

### 977. Unix 操作系统中的内核（Kernel）是什么？

### 978. Unix 操作系统中的 Shell 是什么？

### 979. 你知道 Unix 中哪些不同的 Shell？

### 980. `ls -l` 命令输出的第一个字符是什么？

### 981. 多任务环境和多用户环境的区别是什么？

### 982. Unix 中的命令替换（Command Substitution）是什么？

### 983. Unix 中的 Inode（索引节点）是什么？

### 984. Unix 文件系统中绝对路径和相对路径的区别是什么？

### 985. Unix Shell 的主要责任是什么？

### 986. 什么是 Shell 变量？

## Microservices

### 987. 什么是微服务（Microservice）？

### 988. 微服务架构有哪些优势？

### 989. 架构师在微服务架构中扮演什么角色？

### 990. 微服务架构相比于面向服务的架构（SOA）的优势是什么？

### 991. 为组织中的微服务开发提供定制化的服务模板是一个好主意吗？

### 992. 使用共享库方法拆解单体应用有哪些缺点？

### 993. 良好的微服务具有哪些特征？

### 994. 什么是边界上下文（Bounded Context）？

### 995. 在微服务集成期间有哪些需要注意的点？

### 996. 微服务共享一个数据库是一个好主意吗？

### 997. 微服务之间首选的通信类型是什么？同步还是异步？

### 998. 微服务架构中编排（Orchestration）和编舞（Choreography）的区别是什么？

### 999. 在微服务中使用通过 HTTP 的 REST 有哪些问题？

### 1000. 我们可以将微服务创建为状态机（State Machines）吗？

# 致谢

我们感谢读者们，他们不断发送反馈和评论，激励了我们编写这些包含最新信息的实用书籍！

# 引言

Java 是最流行的编程语言之一。科技公司对 Java 开发人员职位的需求日益增长。

本书包含了面试官针对 Java 技术以及相关主题（如 Spring, Hibernate, Maven, Git, Microservices, AWS 等）提问的技术面试题。

每个问题都附有答案，以便你可以在短时间内准备诸如 Facebook、Oracle、Netflix 等顶尖公司的面试。

当你第一遍过一遍这些问题时，标记出你无法回答的问题。然后，第二遍专门过这些困难的问题。

通过阅读这本书 2-3 遍，你将好好应对从软件工程师到首席工程师级别的 Java 面试。

祝你好运！！



- 1. 启动类加载器 (Bootstrap ClassLoader)：这是第一个加载器。它从 `rt.jar` 文件加载类。
- 2. 扩展类加载器 (Extension ClassLoader)：它从 `jre/lib/ext` 位置加载类文件。
- 3. 应用类加载器 (Application ClassLoader)：这个加载器依赖 `CLASSPATH` 来查找类文件的位置。如果你在 `CLASSPATH` 中指定了你的 jars，那么这个加载器就会加载它们。

### 8. 你认为用于主方法的 `main` 是 Java 中的一个关键字吗？

不是，`main` 只是一个方法名。在类文件中可以有多个同名为 `main` 的方法。它不是 Java 中的一个关键字。

### 9. 我们可以将 main 方法写为 `public void static` 而不是 `public static void` 吗？

不可以，不能这样写。任何方法必须先指定修饰符，然后是返回值。修饰符的顺序可以改变。

我们可以写 `static public void main()` 来代替 `public static void main()`。

### 10. 在 Java 中，如果没有为局部变量指定任何值，局部变量的默认值是什么？

Java 不用任何默认值初始化局部变量。因此，这些变量默认就是 `null`。

### 11. 假设我们运行一个 java 类而没有传递任何参数。Main 方法中 `arguments` 的 String 数组的值是什么？

在 Java 中，`arguments` String 数组的默认值为空。它不是 `null`。

### 12. Java 中 `byte` 和 `char` 数据类型的区别是什么？

`byte` 和 `char` 都是 Java 中的数值数据类型。它们用于表示特定范围内的数字。

它们之间的主要区别是，`byte` 可以存储原始的二进制数据，而 `char` 存储字符或文本数据。

`char` 的用法用例如：`char ch = 'x';`

`byte` 的值范围从 -128 到 127。

一个 `byte` 由 8 位组成。但一个 `char` 由 16 位组成。因此它等于 2 个 `byte`。

## OOP（面向对象）

### 13. 面向对象编程的主要原理有哪些？

面向对象编程（OOPS）的主要原理是：

- 1. 抽象 (Abstraction)
- 2. 封装 (Encapsulation)
- 3. 继承 (Inheritance)
- 4. 多态 (Polymorphism)

### 14. 面向对象编程语言与基于对象的编程语言的区别是什么？

像 Java 和 C++ 这样的面向对象编程语言遵循 OOPS 的概念，如封装、抽象、多态和继承等。

基于对象的编程语言遵循 OOPS 的某些特性，但它们不提供多态和继承的支持。例如 JavaScript、VBScript 等。

基于对象的编程语言提供对象（Objects），你可以通过构造函数构建对象。这些语言也支持封装。这些也被称为原型导型语言（Prototype-oriented languages）。

### 15. 在 Java 中，定义为对象中实例变量的对象引用的默认值是什么？

Java 中所有的实例变量对象引用都是 `null`。

### 16. 为什么 Java 中需要构造函数？

Java 是一种面向对象的语言，我们在其中创建创建并使用对象。构造函数是一段类似于方法的代码。它用于创建对象并设置对象的初始状态。

构造函数是一个特殊的函数，其名称与类名相同。

没有构造函数，就没有其他方法可以创建对象。

默认情况下，Java 为每个对象提供一个默认构造函数。如果我们重载了构造函数，那么我们就必须实现默认构造函数。

### 17. 为什么 Java 类中需要默认构造函数？

默认构造函数是在没有定义其他构造函数时由 Java 自动生成的无参数构造函数。

Java 规范说，如果类中没有重载构造函数，它将提供一个默认构造函数。但它没有提到在类中写了重载构造函数的情况。

我们需要至少一个构造函数来创建对象，这就是为什么 Java 提供了默认构造函数。

当我们有重载构造函数时，Java 假设我们想在代码中进行某些自定义处理。因此它不提供默认构造函数。但根据规范，它需要默认构造函数。所以它会报错。

### 18. Java 构造函数返回什么值？

当我们在 Java 中调用构造函数时，它返回所创建的对象。这就是我们在 Java 中创建新对象。

### 19. 可以继承构造函数吗？

不可以，Java 不支持构造函数的继承。

### 20. 为什么 Java 中的构造函数不能是 final、`static` 或 `abstract`？

如果我们将方法标记为 `final`，意味着我们不希望任何类覆盖它。但构造函数（根据 Java 规范）不能被覆盖。

如果我们将方法标记为 `abstract`，意味着它没有主体，应该在子类中实现。但构造函数总在使用 `new` 关键字时被调用。

如果我们将方法标记为 `static`，意味着它属于类，而不是对象。因此构造函数标记为 `static` 没有意义。

## 继承

### 21. Java 中 `this` 关键字的目的是什么？

在 Java 中，`this` 关键字引用对象的当前实例。

它有助于区分实例变量和局部变量。

它可以用于调用构造函数。

在方法重写的情况下，`this` 用于调用当前类的方法。

### 22. 解释继承的概念？

继承是面向对象编程中一个重要的概念。某些对象共享特性和行为。通过继承，我们可以将共同的行为和特性放在基类中，称为超类（super class）。然后所有具有共同行为的对象继承自这个基类。

它也被表示为 IS-A 关系。

继承了代码重用、方法重写和多态。

### 23. Java 中哪个类是所有类的父类？

Java 是一种面向对象的语言。在 Java 中，`Object` 类是所有类的父类。

### 24. 为什么 Java 不支持多重继承？

多重继承意味着一个类可以从两个或多个父类继承行为。

多重继承的问题在于，两个父类可能对同一个方法有不同的实现。因此它们以不同的方式执行相同的操作。现在子类应该选择哪种实现？

这导致了多重继承中的歧义。这是 Java 在实现不支持多重继承的主要原因。

假设有一个类 `TV` 和另一个类 `AtomBomb`。它们都有 `switchOn()` 方法，但只有 `TV` 有 `switchOff()` 方法。如果你的类继承了这两个类，你就会遇到问题：你可以 `switchOn()` 两个父类，但 `switchOff()` 只会关闭 `TV`。

但你可以在 Java 中实现多个接口。

### 25. 在 OOP 中，组合（composition）指的是什么？

组合也被称为“拥有”（has-a）关系。在组合中，“拥有”关系将两个类联系起来。例如：`Car` 类有一个方向盘。

如果一个类持有另一个类的实例，那么它被称为组合。

### 26. 聚合（Aggregation）和组合（Composition）是哪些不同的概念？

在面向对象编程（OOPS）中，聚合和组合是关联类型。组合是一种强关系。如果组合对象被销毁，那么它所有的部分都会被销毁。例如：汽车有一个方向盘。如果汽车对象被销毁，那么方向盘也就没有意义了。

在聚合中，关系比组合要弱。

例如：图书馆拥有学生。如果图书馆被销毁，学生仍然存在。因此，图书馆和学生之间通过聚合建立联系。图书馆拥有书籍。如果图书馆被销毁，书籍也会被销毁。离开图书馆书籍无法存在。因此，书籍和图书馆之间通过组合建立联系。

### 27. 为什么 Java 中没有指针？

在 Java 中，使用的是引用（references）而不是指针（pointers）。这些引用指向内存中的对象。但无法直接访问这些内存位置。JVM 可以自由地在虚拟机内存中移动对象。

指针的缺失有助于 Java 有效地管理内存和垃圾回收。此外，它为开发者提供了便利性，让他们无需担心内存的分配和释放。

### 28. 如果 Java 中没有指针，为什么我们会得到 NullPointerException（空指针异常）？

在 Java 中，指针的等效物是对象引用（Object reference）。当我们使用它时，它指向对象引用。因此 JVM 使用指针，但程序员只看到对象引用。

如果一个对象引用指向 null 对象，而我们尝试访问其上的方法或成员变量，就会得到 NullPointerException。

### 29. Java 中 ‘super’ 关键字的作用是什么？

`super` 关键字用于子类的方法或构造函数中。它引用对象的直接父类。

通过使用 `super`，我们可以从子类的方法中调用父类的方法。

我们还可以通过 `super` 关键字从子类的构造函数中调用父类的构造函数。

### 30. 是否可以在同一个构造函数同时使用 this() 和 super()？

不可以，Java 不允许在同一个构造函数同时使用 `super()` 和 `this()`。根据 Java 规范，`super()` 或 `this()` 必须是构造函数的第一条语句。

### 31. Java 中对象克隆（object cloning）的含义是什么？

`Object.clone()` 方法用于在 Java 中创建对象的精确副本。它的作用类似于拷贝构造函数。它创建并返回一个对象的副本，该副本具有相同的类，且所有字段的值与原始对象相同。

克隆的一个缺点是返回类型是 `Object`。它必须显式强制转换为实际类型。

## Static

### 32. 在 Java 中，我们为什么要使用静态变量（static variable）？

每当我们想要该类的所有对象拥有一个公共属性时，我们就使用类级变量，即静态变量。

该变量在类加载时仅加载到内存一次。因此它节省了内存，因为它在 Java 中不是按每个对象定义的。

### 33. 为什么在 Java 中创建静态变量不是良好实践？

静态变量对于类的所有对象都是通用的。如果创建一个新对象，没有必要测试静态变量的值。任何使用静态变量的代码都可以处于任何状态。它可以位于新对象内部，也可以位于类级别。因此，静态变量的作用范围在 Java 类中是开放的。

如果我们对范围有更严格的控制，则应该在对象创建级别创建变量。

此外，定义静态变量不是良好实践，因为它们违背了面向对象编程的原则。

### 34. Java 中静态方法（static method）的作用是什么？

Java 提供了静态方法的功能以便在类级别创建行为。静态方法对于该类的所有对象都是通用的。我们不需要创建类的任何对象就可以调用静态方法。因此它提供了无需创建对象即可调用的便利性。

此外，静态方法可以访问和修改静态数据成员。这也有助于在类级别保持行为和状态。

### 35. 为什么我们在 Java 中将 main 方法标记为静态？

Java 中的 `main` 方法被标记为 `static`，以便 JVM 可以调用它来启动程序。如果 `main` 方法不是静态的，那么构造函数将由 Java 进程调用？

因此，在 Java 中将 `main` 方法标记为静态是一个已知约定。但如果我们移除 `static`，就会产生歧义。Java 进程可能不知道调用类中的哪个方法来启动程序。

所以这种约定有助于 Java 进程识别作为参数传递给 Java 进程的类中的启动代码。

### 36. 在什么场景下使用静态块（static block）？

有时，一个类拥有静态成员变量。这些变量需要一些复杂的初始化。此时，静态块可以作为初始化复杂静态成员变量的工具。

静态块在 `main` 方法执行之前就会执行。

有时，我们也可以用类的静态方法来替换静态块。

### 37. 是否可以在不定义 main() 方法的情况下执行程序？

不可以，从 Java 7 开始，你需要一个 `main()` 方法来执行程序。在 Java 的早期版本中，有一种使用静态块进行执行的变通方法。但现在这个漏洞已经被堵上了。

### 38. 如果 main 方法签名中没有提到 static 修饰符会发生什么？

根据 Java 规范，`main` 方法必须是 `static` 的。它只需要一个 String 数组作为参数。

程序可以使用非静态方法编译。但在执行时它会抛出 `NoSuchMethodError`。

### 39. Java 中静态方法（static method）和实例方法（instance method）的区别是什么？

通常，需要为类定义一种不依赖于变量的行为。这种行为被捕获在静态方法中。如果行为依赖于成员变量，我们就不将其标记为 `static`，而是作为实例方法。

作为静态方法调用不需要创建对象。我们只需通过类名调用。但要调用实例方法，我们需要先创建一个对象。

实例变量无法被静态方法访问。但实例方法可以访问实例变量和静态变量。

### 40. 方法重载（Method Overloading）的别名是什么？

方法重载被称为静态多态。

### 41. 你如何在 Java 中实现方法重载？

在 Java 中，一个类可以有多个同名但参数不同的方法。这被称为方法重载。要实现方法重载，我们必须在类中创建同名的方法并执行以下一项或多项：

- 改变参数数量
- 改变参数类型
- 不同的参数顺序

### 42. 方法重载允许哪些类型的参数变化？

方法重载允许同名方法在以下方面有所不同：

- 参数数量
- 参数类型
- 参数顺序

### 43. 为什么通过更改方法的返回类型无法在 Java 中实现方法重载？

如果我们更改重载方法的返回类型，会导致歧义行为。客户端如何知道哪个方法将返回什么类型？由于这个原因，重载方法不允许有不同的返回类型。

### 44. Java 允许重载 main() 方法吗？

是的，Java 允许用户创建许多名为 'main' 的方法。但只有 `public static void main(String[] args)` 方法用于执行。

### 45. 如何在 Java 中实现方法重写（method overriding）？

要重写方法，我们只需要在子类中提供同名方法的新实现。因此，至少会有两个同名方法的实现。一个实现实现在父类中。另一个实现实现在子类中。

### 46. Java 允许重写静态方法吗？

不允许。Java 不允许重写静态方法。如果你在子类中创建一个同名的静态方法，那么它是一个新方法，而不是被重写的方法。

### 47. 为什么 Java 不允许重写静态方法？

要重写一个方法，你需要类的实例。静态方法与类的任何实例都没有关联。因此，重写的概念在这里并不适用。

因此，Java 不允许重写静态方法。

### 48. 允许重写被重载的方法吗？

允许。你可以在 Java 中重写一个被重载的方法。

### 49. Java 中方法重载（overloading）和方法重写（overriding）的区别是什么？

方法重载和重写的区别在于：

- 1. 方法重载是静态多态。方法重写是运行时多态。
- 2. 方法重载发生在同一个类内部。方法重写发生在具有继承关系的两个类之间。
- 3. 方法重载的参数必须不同。方法重写的参数必须相同。
- 4. 方法重载是一个编译时概念。方法重写是一个运行时概念。

### 50. Java 允许虚函数（virtual functions）吗？

允许。Java 中所有的实例方法默认都是虚函数。

Java 中只有类方法和私有实例方法不是虚方法。

### 51. Java 中的协变返回类型（covariant return type）什么意思？

方法的协变返回类型是指方法在子类中被重写时，可以被“更窄”的类型替换。

假设类 B 是类 A 的子类。类 A 和类 B 中 get() 方法。类 A 的 get() 方法返回 A 的实例，而类 B 的 get() 方法返回 B 的实例。这里类 B 重写 get() 方法，但返回类型不同。

在 Java 5 之前，任何重写父类的方法都具有相同的返回类型。

从 Java 5 开始，子类可以重写父类的方法，并且子类方法可以返回父类方法返回对象的子类对象。

## 多态 (Polymorphism)

### 52. 什么是运行时多态？

运行时多态或动态多态是存在于运行时的多态。在方法重写的情况下，运行时将调用哪个方法是未知的。JVM 根据对象的类型决定应该调用的确切方法。

因此，在编译时并不知道运行时将调用哪个方法。

### 53. 在 Java 中可以通过数据成员实现运行时多态吗？

不能。我们需要通过在 Java 继承的两个层次上实现方法来实现运行时多态。

### 54. 解释静态绑定和动态绑定的区别？

在静态绑定中，引用在编译时解析。在动态绑定中，引用在运行时解析。

例如：

```java
Person p = new Person();
p.walk(); // Java 编译器在编译时解析此绑定。

public void walk(Object o) {
    ((Person) o).walk(); // 这是这是动态绑定。
}
```

## 抽象 (Abstraction)

### 55. 面向对象编程中的抽象是什么？

抽象是隐藏对象某些实现细节，并仅向外部世界显示对象本质特征的过程。

它与 Java 中的抽象类（Abstract class）不同。

抽象过程识别共性并隐藏实现上的复杂性。它帮助我们关注与外部世界共享的接口。

### 56. 抽象与封装（Encapsulation）有什么不同？

抽象发生在类级设计阶段。它的结果是隐藏实现细节。封装也被称为“信息隐藏”。封装的一个示例是将成员变量标记为私并为这些成员变量提供 getter 和 setter。

### 57. Java 中的抽象类（abstract class）是什么？

Java 中的抽象类有一个或多个抽象方法。抽象方法仅在抽象类中声明，但没有实现。

在 Java 中，抽象类必须被继承，且其抽象方法必须由子类来实现。此外，Java 不允许创建抽象类的新实例。

### 58. 允许在不标记类为抽象的情况下将方法标记为抽象方法吗？

不允许。Java 规范规定，如果类中至少有一个抽象方法，该类必须标记为抽象。

### 59. 允许同时将方法标记为抽象和 final 吗？

不允许。将一个方法同时标记为 abstract 和 final 是自矛盾的。



抽象方法必须被子类重写。而 `final` 方法不能被重写。因此，在 Java 中，一个方法可以是抽象的，也可以是 `final` 的。

# 60. 可以在 Java 中实例化抽象类吗？

不能。我们不能在 Java 中创建抽象类的实例。

# 61. Java 中的接口（interface）是指什么？

Java 接口是类的抽象类型蓝图。它包含了类必须实现的方法。它像是一个协议。

它包含方法签名和常量声明。

# 62. 允许标记接口方法为 static 吗？

允许，从 Java 8 开始，我们可以在接口中定义静态方法。在 Java 8 之前是不允许的。

# 63. 为什么接口不能标记为 final？

`final` 方法不能被重写。但接口方法必须由另一个类实现。因此接口方法不能是 `final`。

### 64. 什么是标记接口（marker interface）？

有些接口没有任何任何数据成员或方法。

这些接口被称为标记接口。

例如：`Serializable`、`Cloneable`、`Remote`。

# 65. 我们可以用什么代替标记接口？

我们可以使用注解（`annotations`）来代替标记接口。

# 66. 注解比标记接口好在哪里？

注解的作用在不创建独立类型的情况下向类传达元数据。

# 67. 抽象类和接口的区别是什么？

抽象类和接口的区别在于：

1. 抽象类可以有实现的方法（非抽象）。接口只有抽象方法。从 Java 8 开始接口可以有静态/默认方法。
2. 抽象类可以有实例变量。接口不能有实例变量。它只能有常量。
3. 抽象类有构造方法。接口没有构造方法。它必须由其他类实现。
4. 类只能继承一个抽象类。类可以实现多个接口。

# 68. Java 允许在接口变量中使用 private 和 protected 修饰符吗？

不允许。接口中的所有变量隐式为公共。

# 69. 我们如何将对象引用强制转换为接口引用？

实现接口的对象可以强制转换为该接口。由于实现接口的对象已经提供了接口方法的实现，因此根据继承规则这是允许的。

## Final

# 70. 在 Java 中如何更改 final 变量的值？

Java 不允许更改 `final` 变量的值。一旦设置了值，就无法更改。

# 71. Java 中的类可以被标记为 final 吗？

可以，类可以被标记为 `final`。一旦类被标记为 `final`，它就无法被扩展。

# 72. 在 Java 中如何创建一个 final 方法？

要标记一个方法，为该方法添加 `final` 修饰符。`final` 方法不能被子类重写。

# 73. 如何在 Java 中禁止继承？

如果你将一个类标记为 `final`，它就无法被扩展。这将阻止对该类的继承。

# 74. 为什么 Java 中的 Integer 类是 final 的？

`Integer` 类是 `int` 的包装类。如果它不被标记为 `final`，那么任何其他类都可以扩展它并修改 `Integer` 操作的行为。为了避免这种情况，`Integer` 包装类被标记为 `final`。

# 75. 什么是 Java 中的空白 final 变量（blank final variable）？

当我们在声明一个 `final` 变量但不赋予它任何初始值时，它被称为空白 `final` 变量。

# 76. 我们如何初始化空白 final 变量？

空白的 `final` 实例变量可以在构造函数中初始化。

空白的 `final` 静态变量可以在类的静态块中初始化。

# 77. 允许将 main 方法声明为 final 吗？

可以，我们可以将 `main` 方法标记为 `final`。

## Package（包）

# 78. Java 中包的目的是什么？

包用于封装一组类、接口和子包。它通常是用于存储信息的层级结构。通过这种方式，可以更容易组织相关的类和子包。

包还为类和接口提供了访问控制。同时，包还有助于消除命名冲突。

# 79. 什么是 java.lang 包？

在 Java 中，`java.lang` 包包含了对 Java 编程设计至关重要的类。该包最重要的类是 `Object` 类。它还包含了 `Integer`、`Boolean`、`Character` 等包装类。它还提供了用于数学运算的 `Math` 类。

### 80. Java 中最重要的类是哪一个？

这是一个开放式的问题，有很多答案。在我看来，`Object` 类是 Java 语言中最重要的类。它是所有类的根，并提供了一些非常重要的方法。

# 81. 每次都导入 java.lang 是强制性的吗？

不是的。默认情况下，JVM 会在内部加载它。

# 82. 你可以在类中多次导入同一个包或同一个类吗？

如果我们在一个类中多次导入同一个包，编译器只会将其包含一次。JVM 或编译器都不会给出任何错误。但如果你有两个同名的类，就可能会发生冲突。

# 83. 什么是 Java 中的静态导入（static import）？

静态导入与普通导入类似。普通导入允许我们在不使用限定限定符的情况下从包导入类。而静态导入允许我们在不使用限定限定符的情况下从类中导入静态成员。

# 84. com.test.Class 和 com.test.Class 之间有什么区别？

第一个导入是静态导入，第二个导入是对该类的普通导入。第一个导入允许我们导入类的静态成员。

## Internationalization（国际化）

# 85. 什么是 Java 中的 Locale（本地化）？

`Locale` 对象代表特定的地理、政治或文化区域。它用于 Java 中对区域敏感的操作。它有助于在格式化日期、数字等时遵循国家、本源地区的惯例。

# 86. 你将如何在 Java 中使用特定的 Locale？

要使用特定的 `Locale`，我们需要加载该 `Locale`。我们可以使用 `ResourceBundle.getBundle()` 方法来加载 `Locale`。

## Serialization（序列化）

### 87. 什么是序列化？

序列化是将对象转换为字节数组的过程。该字节数组代表了对象的类和内部状态。JVM 可以使用此字节数组通过网络传输对象。

### 88. 序列化的目的是什么？

序列化的某些用途包括：

1. 通信：它用于在两台机器之间通过网络传输对象。
2. 持久：我们可以将对象的状态存储在数据库中并在稍后检索。
3. 缓存：序列化可用于缓存以提高性能。构建一个对象可能需要几分钟，但反序列化该对象可能只需要几秒钟。
4. 跨 JVM 同步：可以在遵循不同架构的多个 JVM 之间使用。

### 89. 什么是反序列化（Deserialization）？

反序列化是从序列化状态重建对象的过程。它是序列化的逆过程。

### 90. 从概念上，序列化和反序列化是什么？

序列化是将对象数据转换为字节流。反序列化是将字节流转换回原始对象的副本。

### 91. 为什么我们将数据成员标记为 transient？

对象的成员变量被标记为 `transient` 表示它们不应该被序列化。在序列化过程中，`transient` 变量不被视为对象持久状态的一部分。

# 92. 允许将方法标记为 transient 吗？

不允许，Java 不允许将方法标记为 `transient`。`transient` 关键字仅对成员变量有效。

# 93. 将字段标记为 transient 如何让对象序列化成为可能？

假设我们有一个实现 `Serializable` 接口的类 `ABC`，但它包含一个没有实现 `Serializable` 接口的类 `XYZ` 的成员变量。由于 `XYZ` 不可序列化，无法序列化类 `ABC`。要解决这个问题，我们可以在类 `ABC` 中将成员变量 `XYZ` 标记为 `transient`。这将允许我们序列化类 `ABC`。

# 94. 什么是 Java 中的 Externalizable 接口？

`Externalizable` 接口扩展了 Java 中的 `Serializable` 接口。它用于让类控制保存和恢复其实例的内容。类实现 `writeExternal()` 和 `readExternal()` 方法来存储和恢复对象。

### 95. Serializable 和 Externalizable 接口之间有什么区别？

`Serializable` 是一个标记接口（`marker interface`），而 `Externalizable` 不是标记接口。当我们实现 `Serializable` 接口时，类默认会被自动序列化。在 `Externalizable` 的情况下，你必须实现 `writeExternal()` 和 `readExternal()` 方法来控制序列化过程。`Serializable` 提供了两个选项：一个是自定义方式，另一个是默认方式。在序列化中，我们需要定义 `serialVersionUID`。如果显式定义，它将根据类的所有字段和方法自动生成。

## Reflection（反射）

# 96. 什么是 Java 中的反射？

反射是 Java 语言在运行时检查和动态调用类、方法、属性等的能力。它有助于在运行时检查或修改类的运行时行为。

### 97. 反射在 Java 中有什么用途？

反射通常用于测试、调试以及集成开发环境（IDE）。反射允许你编写在编译时不需要“知道”所有事情的程序。它使程序更具动态性，因为它们可以在运行时绑定。许多现代框架（如 Spring 等）都使用反射。一些现代语言（如 Python 等）也使用反射。Java XML 解析 API (JAXP) 也使用了反射。

# 98. 我们如何从类外部访问类的私有方法？

我们可以使用反射从类外部访问类的私有方法。在 Java 中，我们使用 `getDeclaredMethod()` 获取私有方法的实例。然后将此方法标记为可访问（`accessible`），最后调用它。在下面的示例代码中，我们通过反射访问 `Foo` 类的私有方法 `message()`。

```
FileName: Foo.java
public class Foo {
  private void message() {System.out.println("hello java");}
}
```

```
FileName: FooMethodCall.java
import java.lang.reflect.Method;
public class FooMethodCall {
  public static void main(String[] args) throws Exception {
    Class c = Class.forName("Foo");
    Object o=c.newInstance();
    Method m=c.getDeclaredMethod("message", null);
    m.setAccessible(true);
    m.invoke(o, null);
  }
}
```

### 99. 如何在 Java 运行时动态创建对象？

我们可以使用反射（Reflection）在 Java 运行时动态创建对象。我们可以使用 `Class.newInstance()` 或 `Constructor.newInstance()` 方法来创建此类对象。

# 垃圾回收 (Garbage Collection)

# 100. 什么是 Java 中的垃圾回收？

Java 有一种名为垃圾回收的内部机制，用于运行时回收未使用项目的内存。

垃圾回收也被称为自动内存管理。

### 101. 为什么 Java 提供垃圾回收器？

在 Java 中，没有指针。内存管理和分配由 JVM 完成。由于内存分配是自动的，在一段时间后 JVM 可能会出现内存不足。此时，JVM 必须从未使用的对象中释放内存。为了帮助回收内存的过程，Java 提供了一个名为垃圾回收器（Garbage Collector）的自动化进程。

### 102. Java 中 gc() 的作用是什么？

Java 两个方法 `System.gc()` 和 `Runtime.gc()` 来请求 JVM 运行垃圾回收。通过这些方法，程序员可以显式地发送垃圾回收请求。但 JVM 进程可能会拒绝此请求，并在运行 GC 之前等待一段时间。

### 103. Java 中的垃圾回收是如何工作的？

Java 有一个名为垃圾回收器的自动化进程用于内存管理。它是 JVM 中的一个守护进程（`daemon`），负责监控内存使用并执行内存清理。一旦 JVM 内存不足，GC 进程就会找到未被其他对象引用的未使用对象。这些未使用的对象会被 JVM 中的垃圾回收器守护进程清理。

# 104. Java 中的对象在什么时候可以被垃圾回收？

如果一个对象是不可达的（`not reachable`），它就可以被 JVM 垃圾回收。判断对象是否符合垃圾回收条件有两种情况：

1. 无法被存活线程访问的对象/实例。
2. 一组循环引用的实例，它们无法被该集合之外的任何其他实例访问。

# 105. 为什么在 Java 中使用 finalize() 方法？

Java 提供了 `finalize()` 方法在垃圾回收之前执行任何清理工作。该方法位于 `Object` 类中，由 JVM 内部调用。开发者可以自由实现此方法，以便在垃圾回收时进行任何自定义清理。

如果一个对象没有被垃圾回收，则此方法可能不会被调用。

该方法 JVM 绝不会调用超过一次。

### 106. Java 中有哪些类型的引用（References）？

在 Java 中，有四种引用：

1. 强引用（Strong Reference）
2. 软引用（Soft Reference）
3. 弱引用（Weak Reference）
4. 虚引用（Phantom Reference）

### 107. 如何再次引用一个未引用的对象？

我们可以在 `finalize()` 方法中提供实现来引用未引用的对象。对于未引用的对象，`finalize()` 方法在垃圾回收时被调用。此时，对象可以将它的引用 `this` 传递给 `finalize()` 方法并复活。

### 108. 垃圾回收线程什么样的进程？

垃圾回收是 JVM 中的守护进程（`Daemon`）。它是一个不断检查内存使用并清理内存的内部进程。

### 109. Runtime 类的作用是什么？

`Runtime` 类的目的是提供对 Java 运行时访问。该类提供了某些重要方法，如：

1. `Runtime.freeMemory()` – 此方法返回 JVM 中空闲内存的值。
2. `Runtime.maxMemory()` - 此方法返回 JVM 可使用的最大内存值。
3. `Runtime.gc()` – 此方法可以调用垃圾回收。

### 110. 如何在 Java 中调用外部进程？

Java 提供了 `Runtime.getRuntime().exec()` 方法来从 JVM 调用外部进程。

### 111. Runtime 类的用处有哪些？

Java 中的 `Runtime` 类提供以下优势：

1. 它允许通过键盘读取数据。
2. 它可以使用系统属性和环境变量。
3. 它有助于在 Java 应用程序内部运行非 Java 程序。

## 内部类 (Inner Classes)

### 112. 什么是嵌套类（Nested class）？

在 Java 中，嵌套类是声明在另一个内部的类。我们可以在一个文件中声明多个类。

# 113. Java 中有多少种类型的嵌套类？

Java 提供了四种嵌套类：

1. 成员内部类（Member inner class）
2. 局部内部类（Local inner class）
3. 匿名内部类（Anonymous inner class）
4. 静态嵌套类（Static nested class）

# 114. 为什么我们要使用嵌套类？

使用嵌套类的原因如下：

1. 逻辑分组：我们可以在逻辑上将类分组在一个地方。如果一个类只对另一个类有用，那么我们就将较小的类放在较大的类内部，并将它们保持在同一个文件中。这种在顶层类中嵌套“辅助类”的方式使得包变得更加精简。
2. 封装：嵌套类增加了封装性。假设有两个顶层类 `Foo` 和 `Bar`。`Bar` 需要访问 `Foo` 的私有成员。我们可以隐藏 `Foo` 类只能被 `Bar` 类访问。这样，`Foo` 的私有成员保持了封装性。
3. 代码清晰性：嵌套类使代码更具读性和组织性。

### 115. 嵌套类和静态类（Static class）有什么区别？

在 Java 中，嵌套类是声明在另一个内部的类。静态嵌套类是标记为 `static` 的嵌套类类型。静态嵌套类可以访问内部类的静态成员。

### 116. 什么是嵌套接口（Nested interface）？

嵌套接口声明在另一个类内部。默认情况下，它是 `static` 的。嵌套接口也被称为静态接口。

### 117. 如何访问类内部的非 final 变量？

Java 允许静态嵌套类访问内部类中为 `static` 的非 final 变量。

### 118. 可以在类中定义接口吗？

可以，我们可以在类中定义静态接口。只有内部类可以访问它。

### 119. 我们必须显式地标记嵌套接口为 `public static` 吗？

嵌套接口是隐式的 `static`。因此，修饰符 `public` 和 `static` 是多余的。

### 120. 为什么在 Java 中使用静态接口？

只有内部类可以访问静态接口。考虑以下代码，其中 `Xyz` 被封装在类 `Abc` 中。

```
public class Abc {

    public interface Xyz {
        void callback();
    }

    public static void registerCallback(Xyz xyz) {...}
}

// Client Code
Abc.registerCallback(new Abc.Xyz() {
    public void callback() {...}
});
```

## String

# 121. 在 Java String 类的背景下，不可变（Immutable）含义含义？



在 Java 中，不可变对象无法被修改。`String` 是一个不可变类。一旦创建了 `String` 对象，就无法更改。当我们给 `String` 赋值新值时，会创建一个新对象。

### 122. 为什么 String 对象被认为是不可变的？

Java 语言将 `String` 用于多种目的。因此它将 `String` 标记为不可变。Java 有字符串字面量（String literal）的概念。假设有两个变量 `A` 和 `B` 引用字符串对象“TestData”。这些变量都引用同一个字符串字面量。如果一个引用变量 `A` 将字符串字面量的值从“TestData”改为“RealData”，它将影响另一个变量，导致 `String` 被认为是不可变的。在这种情况下，如果一个变量 `A` 将值改为“RealData”，将创建一个带有“RealData” 的新字符串字面量，而 `B` 将继续指向“TestData”。

### 123. 下面代码创建了几个对象？

代码：

```java
String s1="HelloWorld";
String s2=" HelloWorld ";
String s3=" HelloWorld ";
```

上述代码只创建了一个对象。由于只创建了一个字符串字面量“HelloWorld”，因此所有的引用都指向同一个对象。

### 124. 在 Java 中有多少种方式可以创建 String 对象？

Java 提供了两种创建 `String` 对象的方法。一种是使用字符串字面量（String Literal），另一种是使用 `new` 算符。

### 125. 下面代码创建了几个对象？

代码：

```java
String s = new String("Hello World");
```

上述代码创建了两个对象。一个对象创建在字符串常量池（String constant pool）中，另一个创建在堆（heap）非池区域。

### 126. 什么是字符串池化（String interning）？

字符串池化指的是对于不同的字符串值，只使用一份不可变（Immutable）的副本的概念。

它在时间和空间复杂度上具有提高字符串处理效率的优势。但在创建字符串时会引入额外的时间开销。

### 127. 为什么 Java 使用字符串字面量概念？

Java 使用字符串字面量概念是为了提高 Java 的内存利用率。如果字符串常量池中已经存在相同的字符串，就可以复用它。这节省了内存消耗。

### 128. String 和 StringBuilder 对象之间的基本区别是什么？

`String` 是一个不可变对象，它的值在创建后无法改变。`StringBuilder` 是一个可变对象，我们可以在 Java 中不断追加或修改 `StringBuilder` 的内容。

### 129. 如何 Java 中创建一个不可变类？

在 Java 中，我们可以将类声明为 `final` 以使其变为不可变。使类变为不可变的详细步骤如下：

1. 给类添加 `final` 修饰符以防止其被继承
2. 给所有字段添加 `private` 修饰符，以防止直接访问
3. 不为成员变量提供任何 setter 方法
4. 给所有可变字段添加 `final` 修饰符，以便只赋值一次
5. 使用深拷贝（Deep Copy）通过构造函数初始化所有字段
6. 在 `clone` 方法中，返回对象的副本而不是实际对象的引用

### 130. Java 中 `toString()` 方法的作用是什么？

在 Java 中，`Object` 类拥有 `toString()` 方法。该方法可以用于返回对象的字符串表示。当我们打印一个对象时，Java 会隐式地调用 `toString()` 方法。

Java 为 `toString()` 方法提供了默认实现。但我们可以重写该方法以返回我们想要打印的格式。

### 131. 将 String、StringBuilder 和 StringBuffer 这三个类按字符串处理操作的效率进行排序？

`StringBuilder` 是效率最高的类。它没有同步（Synchronization）的开销。`StringBuffer` 是同步类（Synchronized class），它的性能比 `String` 好，但比 `StringBuilder` 慢。`String` 在任何字符串处理操作中都是慢的，因为每次修改都会导致新字符串字面量的创建。

因此，效率递减顺序是：`StringBuilder`, `StringBuffer`, `String`

## 异常处理 (Exception Handling)

### 132. 什么是 Java 中的异常处理？

Java 提供了异常处理机制来处理 JVM 中发生的运行时错误（Runtime errors）。程序中存在我们预期在某些情况下会发生的检查异常（checked exceptions）。

异常处理机制会捕获这些检查异常并采取相应的行动。

### 133. 在 Java 中，检查异常（Checked）和未检查异常（Unchecked）的区别是什么？

检查异常继承自 `Throwable` 类，但它们不继承 `RuntimeException` 或 `Error` 类。未检查异常（UncheckedException）继承 `RuntimeException` 类。

检查异常在 Java 编译时被检查。未检查异常发生在运行时，因此在编译时不会被检查。

`IOException`、`SQLException` 等是检查异常的示例。`NullPointerException`、`ArithmeticException` 等是未检查异常的示例。

### 134. Java 中 Error 和 Exception 类的基类是什么？

Java 中的 `Error` 类和 `Exception` 类都派自 `Throwable` 类。

### 135. Java 中的 `finally` 块是什么？

Java 提供了一个与 `try` 块配合使用的 `finally` 块。这是一个可选块，但 `finally` 块会在 `try` 块执行后执行。

### 136. Java 中 `finally` 块的作用是什么？

根据 Java 规范，`finally` 块始终会被执行，无论是否发生错误，无论异常是否被处理。它有助于进行清理工作，如：回滚事务、关闭连接、关闭文件等。

### 137. 可以在不创建 `catch` 块的情况下创建 `finally` 块吗？

可以。`finally` 块可以跟在 `try` 块或 `catch` 块之后。因此我们可以在 `try` 块之后直接定义 `finally` 块。

### 138. 我们必须始终在 `try` 块之后放置 `catch` 块吗？

Java 不强制在 `try` 块之后放置 `catch` 块。我们可以在 `try` 块之后写 `finally` 块。任何想要捕获的异常都可以在 `catch` 块中。

### 139. 在什么情况下 `finally` 块不会执行？

在以下场景下，`finally` 块不会执行：

1. 通过调用 `system.exit()` 退出
2. 致命错误导致 JVM 崩溃

### 140. 可以在 Java 中重抛异常吗？

是的，Java 允许重抛异常。

### 141. Java 中 `throw` 和 `throws` 的区别是什么？

Java 提供 `throw` 关键字用于从方法显式抛出异常。Java 提供 `throws` 关键字用于声明方法中可能抛出的异常。

`throw` 调用发生在方法内部。`throws` 仅用于方法签名。

我们只能通过 `throw` 传播一个异常。但可以使用 `throws` 关键字传播检查异常。

我们一次只能抛出一个异常。但我们可以在 `throws` 子句中列出多个异常。

### 142. 异常传播（Exception Propagation）的概念是什么？

在异常传播中，未捕获的异常会在调用栈中传播，直到堆栈为空。这种传播被称为异常传播。

假设异常从一个方法传播到另一个方法。`A()` 调用 `B()`，`B` 调用 `C()`，`C` 调用 `D()`。如果 `D()` 抛出了异常，异常将从 `D` 传播到 `C` 到 `A`，除非某个方法捕获了它。

### 143. 当我们在子类中重写方法时，可以抛出父类没有抛出的额外异常吗？

是的，Java 允许我们在子类中抛出额外异常，但额外的异常必须是未检查异常（RuntimeException）。

## Java 集合 (Collection)

### 144. Java 中 Collection 和 Collections Framework 的区别是什么？

在 Java 中，`Collection` 是一个在一个单元内包含多个相同类型元素的对象。这些多个元素可以通过一个 `Collection` 对象进行访问。

Java Collections Framework 是用于创建、更新和访问不同类型集合的通用库。在 Collections 框架中，有开发者处理 `Collection` 对象时常用的常用方法。

### 145. Java Collections Framework 的主要优势是什么？

Java Collections Framework 的主要优势如下：

1. **可复用性**：Java Collections Framework 提供了适用于不同集合的通用类和工具方法。这提高了代码的可复用性。开发者不需要通过编写相同的方法来造轮子。
2. **质量**：使用 Java Collection Framework 可以提高程序质量，因为代码已经经过测试并被成千上万的开发者使用。
3. **速度**：大多数程序员报告他们的开发速度增加了，因为他们可以专注于核心逻辑并使用 Java 框架提供的泛型集合。
4. **维护**：由于大多数 Java Collections Framework 代码都是开源的且 API 文档广泛可用，使用 Java Collections Framework 编写的代码易于维护。一个开发者可以轻松理解前一个开发者的代码。

### 146. Java 中 Collection 层次结构的根接口是什么？

Java 中 Collection 层次结构的根接口是 `Collection` 接口。

但 `Collection` 接口继承了 `Iterable` 接口。由于这一点，有些人将 `Iterable` 接口视为根接口。

`Iterable` 接口存在于 `java.lang` 包中，而 `Collection` 接口存在于 `java.util` 包中。Oracle Java API 文档提到 `Collection` 接口是 Java 集合框架（Java Collections framework）的成员。

相反，Java 文档中并没有说明 `Iterable` 接口是 Java 集合框架的一部分。

正因如此，`Collection` 接口是集合框架的根。

### 147. Collection 和 Collections 之间的主要区别是什么？

Collection 和 Collections 之间的主要区别如下：

1. `Collection` 是 Java 中的一个接口（interface）。而 `Collections` 是 Java 中的一个类（class）。
2. `Collection` 是基础接口。`Collections` 是 Java 中的一个工具类（utility class）。
3. `Collection` 定义了用于包含对象的数据结构的方法。`Collections` 定义了用于对 `Collection` 进行访问、查找等操作的方法。

### 148. Java 集合框架中有哪些线程安全的类？

Java 集合框架中的线程安全类有：

- `Stack`
- `Properties`
- `Vector`
- `Hashtable`
- `BlockingQueue`
- `ConcurrentMap`
- `ConcurrentNavigableMap`

### 149. 如何在遍历 Collection 时高效地移除元素？

在遍历集合时从中移除元素的正确方法是使用 `ListIterator.remove()` 方法。

例如：

```java
ListIterator<Integer> iter = myList.listIterator();
while(iter.hasNext()) {
    iter.next(); // 需要先调用 next()
    iter.remove();
}
```

一些开发者使用以下代码来移除元素，这是错误的：

```java
Iterator<Integer> iter = myList.iterator();
while(iter.hasNext()) {
    iter.remove();
}
```

这样做会导致产生 `ConcurrentModificationException`（并发修改异常）。

首先创建一个迭代器来遍历列表。但同时，列表被 `remove()` 方法改变了。

在 Java 中，不允许一个线程在另一个线程遍历集合时修改该集合。`ListIterator` 提供了在遍历期间移除对象的能力。

### 150. 如何将 List 转换为像 `int[]` 这样的整数数组？

我们可以使用 Apache Commons Lang 库中的 `ArrayUtils` 类。

示例代码为：

`int[] intArray = ArrayUtils.toPrimitive(asList.toArray(new Integer[0]));`

如果我们使用 `List.toArray()`，它将把 List 转换为 `Integer[]`。

另一个选项是：

```java
int[] intArray = new int[myList.size()];
for (int i=0; i < myList.size(); i++) {
  intArray[i] = myList.get(i);
}
```

### 151. 如何将基本类型整数数组 `int[]` 转换为 List 集合？

我们可以使用 Apache Commons Lang 库中的 `ArrayUtils`。

示例代码为：

`List<Integer> intList = Arrays.asList(ArrayUtils.toObject(intArray));`

另一个选项是使用 `for` 循环并将整数显式地添加到 List 中。

示例代码为：

```java
int[] intArray = {10,20,30};
List<Integer> intList = new ArrayList<Integer>();
for (int i: intArray) {
  intList.add(i);
}
```

### 152. 如何对 Collection 运行过滤？

我们可以为此使用 Apache 的 `CollectionUtils`。我们必须创建一个 `Predicate`（谓词）来定义过滤条件。然后我们可以在 `filter()` 方法中应用这个谓词。

示例代码为：

在此示例中，我们过滤任何长度小于 5 个字符的名字。

`List<String> namesList = asList("Red", "Blue", "Green");`

`List<String> shortNamesList = new ArrayList<String>();`

`shortNamesList.addAll(namesList);`

```java
CollectionUtils.filter(shortNamesList, new Predicate(){
    public boolean evaluate(Object input) {
        return ((String) input).length() < 5;
    }
});
```

我们也可以使用 Google Guava 库来实现。

在 Java 8 中，我们可以通过 Stream 使用 `Predicate` 来过滤 Collection。

### 153. 如何将 List 转换为 Set？

在 Java 中将 List 转换为 Set 有两种方法。

选项 1：使用 `HashSet`

```java
Set<Integer> mySet = new HashSet<Integer>(myList);
```

在这种情况下，我们将列表放入 `HashSet` 中。内部使用 `hashCode` 方法来识别重复元素。

选项 2：使用 `TreeSet`

在这种情况下，我们使用自己的比较器（comparator）来查找重复对象。

```java
Set<Integer> mySet = new TreeSet<Integer>(myComparator);
mySet.addAll(myList);
```

### 154. 如何从 ArrayList 中移除重复元素？

这个题的技巧是使用一种不允许重复元素的集合。因此我们使用 `Set` 来实现此目的。

选项 1：使用 `Set`

如果元素的顺序不重要，我们只需将 `ArrayList` 的元素放入 `HashSet` 中，然后将它们添加回 `ArrayList`。

示例代码：

```java
ArrayList<Integer> myList = new ArrayList<>(); // 包含重复元素的 ArrayList
Set<Integer> mySet = new HashSet<Integer>(myList);
myList.clear();
myList.addAll(mySet);
```

选项 2：使用 `LinkedHashSet`

如果元素的顺序很重要，我们使用 `LinkedHashSet`。

示例代码：

```java
ArrayList<Integer> myList = new ArrayList<>(); // 包含重复元素的 ArrayList
Set<Integer> mySet = new LinkedHashSet<Integer>(myList);
myList.clear();
myList.addAll(mySet);
```

### 155. 如何维护一个有序的 Collection？

在 Java 中，有许多方法可以维护排序：

1. 使用 `TreeSet`：它维护元素的顺序。
2. 使用 `Collections.sort()`：可以使用此方法对 List 进行排序。
3. 使用 `Comparator`：可以使用自定义比较器进行排序。

### 156. Vector 和 ArrayList 这两个数据结构之间有什么区别？



ArrayList 比 Vector 更新。Vector 被视为一个遗留类（legacy class）。区别在于：

- 1. 同步：Vector 是同步的，但 ArrayList 不是。因此 ArrayList 的操作速度比 Vector 快。
- 2. 数据增长：ArrayList 和 Vector 内部都使用数组存储数据。当 ArrayList 满时，它会增加数组大小的 50%。Vector 则是数组大小翻倍。

## 157. Java 中 Collection 和 Collections 之间有什么区别？

Collection 和 Collections 之间的主要区别是：

- 1. 类型：`Collection` 是 Java 中的接口。`Collections` 是一个类。
- 2. 功能：`Collection` 接口为 `List`、`Set` 和 `Queue` 接口提供了基本的数据结构功能。`Collections` 是用于排序和同步集合的工具类。它具有用于操作集合的多态算法。
- 3. 方法类型：`Collection` 中的大部分方法是实例级别的。`Collections` 类主要拥有静态方法，可以作用于 `Collection` 的实例。

## 158. 在什么种情况下，LinkedList 比 ArrayList 更好？

由于易于使用和随机访问元素的特性，ArrayList 在 Java 中比 LinkedList 更流行。

但在不需要随机访问元素或大量插入、删除元素的场景下，LinkedList 更好。

## 159. Java 中 List 和 Set 集合之间有什么区别？

List 和 Set 之间的主要区别是：

- 1. 顺序：List 集合是元素的有序序列。Set 仅仅是无序的元素集合。
- 2. 位置访问：当我们使用 List 时，可以指定确切在哪个位置插入元素。在 Set 中没有顺序，所以可以在任何地方插入元素而不必担心顺序。
- 3. 重复：在 List 中我们可以存储重复元素。Set 只能包含唯一元素。

## 160. Java 中 HashSet 和 TreeSet 集合之间的区别是什么？

HashSet 和 TreeSet 的主要区别是：

- 1. 排序（Ordering）：在 HashSet 中，元素是随机顺序存储的。在 TreeSet 中，元素根据自然顺序存储。
- 2. 空值元素（Null Value Element）：我们可以在 HashSet 中存储空值对象。TreeSet 不允许添加空值对象。
- 3. 性能（Performance）：HashSet 在常数时间内执行 `add()`、`remove()`、`contains()`、`size()` 等基本操作。TreeSet 在 `log(n)` 时间级内执行这些操作。
- 4. 速度（Speed）：在大多数操作（如 `add()`）中，HashSet 的性能优于 TreeSet。
- 5. 内部结构（Internal Structure）：Java 中的 `HashMap` 在内部支持了 HashSet。`NavigableMap` 在内部支持 TreeSet。
- 6. 特性（Features）：相比 HashSet，TreeSet 拥有更多功能。它拥有如 `pollFirst()`、`pollLast()`、`first()`、`last()`、`ceiling()`、`lower()` 等方法。
- 7. 元素比较（Element Comparison）：HashSet 使用 `equals()` 方法进行比较。TreeSet 使用 `compareTo()` 方法进行比较以维护元素的顺序。

## 161. 在 Java 中，你如何决定何时使用 List、Set 或 Map 集合？

- 1. 如果我们需要一个不存储重复值的集合，我们就使用基于 `Set` 的集合。
- 2. 如果我们需要频繁根据索引值进行元素操作，我们就使用基于 `List` 的集合。例如 `ArrayList`。
- 3. 如果我们想维护集合中元素的插入顺序，我们就使用基于 `List` 的集合。
- 4. 为了根据键值对进行快速搜索操作，我们使用基于 `HashMap` 的集合。
- 5. 如果我们想按排序顺序维护元素，我们就使用基于 `TreeSet` 的集合。

## 162. Java 中 HashMap 和 Hashtable 之间的区别是什么？

HashMap 和 Hashtable 的主要区别是：

- 1. 同步（Synchronization）：HashMap 不是同步集合。如果在多线程环境中使用它，它可能无法提供线程安全。Hashtable 是同步集合。在给定时刻，不多于一个线程可以访问 Hashtable。操作 Hashtable 的线程会获取其锁，并让其他线程等待直到工作完成。
- 2. 空值（Null values）：HashMap 允许一个 null 键和任意数量的 null 值。Hashtable 不允许 null 键和 null 值。
- 3. 排序（Ordering）：由 `LinkedHashMap` 实现的 HashMap 维护元素的插入顺序。`TreeMap` 根据键的升序排列对映射进行排序。相反，Hashtable 不保证任何形式的元素顺序。它不以特定顺序维护键值映射。
- 4. 遗留（Legacy）：Hashtable 并不是 Java 集合框架的初始部分。在经过改造以实现 `Map` 接口后，它成为了集合框架的一员。HashMap 实现了 `Map` 接口，并且从一开始就是集合框架的一部分。
- 5. 迭代器（Iterator）：HashMap 的 `Iterator` 是快速失败（fail-fast），如果任何其他线程通过迭代器自身的 `remove()` 方法以外的插入或删除元素来修改映射，它将抛出 `ConcurrentModificationException`。Hashtable 的 `Enumerator` 不是快速失败的。

## 163. HashMap 和 TreeMap 之间的区别是什么？

Java 中 HashMap 和 TreeMap 的主要区别是：

- 1. 顺序（Order）：HashMap 不维护其键的任何顺序。在 HashMap 中，无法保证先插入的元素会被先取出。
- 2. 在 TreeMap 中，元素根据元素的自然顺序存储。TreeMap 使用 `compareTo()` 方法将元素存储在自然顺序中。
- 3. 内部实现（Internal Implementation）：HashMap 内部使用哈希（Hashing）。TreeMap 内部使用红黑树（Red-Black tree）实现。
- 4. 父接口（Parent Interfaces）：HashMap 实现 `Map` 接口。TreeMap 实现 `NavigableMap` 接口。
- 5. 空值（Null values）：HashMap 可以存储一个 null 键和多个 null 值。TreeMap 不可以包含 null 键，但可以包含多个 null 值。
- 6. 性能（Performance）：HashMap 的 `get()` 和 `put()` 等操作提供常数时间性能。TreeMap 的 `get()` 和 `put()` 方法提供 `log(n)` 时间级的性能。
- 7. 比较（Comparison）：HashMap 使用 `equals()` 方法比较键。TreeMap 使用 `compareTo()` 方法维护自然顺序。
- 8. 特性（Features）：TreeMap 比 HashMap 拥有更多特性。它拥有 `pollFirstEntry()`、`pollLastEntry()`、`tailMap()`、`firstKey()`、`lastKey()` 等 HashMap 未提供的方法。

## 164. Comparable 和 Comparator 之间的区别是什么？

Comparable 和 Comparator 的主要区别是：

- 1. 类型（Type）：`Comparable<T>` 是 Java 中的一个接口，其中 T 是该对象可能比较的对象类型。
- 2. `Comparator<T>` 也是一个接口，其中 T 是该比较器可以比较的对象的类型。
- 3. 排序（Sorting）：在 `Comparable` 中，我们只能创建一个排序序列。在 `Comparator` 中，我们可以创建多个排序序列。
- 4. 使用的方法（Method Used）：Java 中的 `Comparator<T>` 接口具有 `public int compare(Object o1, Object o2)`，当对象 `o1` 小于、等于或大于对象 `o2` 时，它返回一个负整数、零或正整数。`Comparable<T>` 接口具有 `public int compareTo(Object o)`。

## 170. 如何将元素从源列表（Source List）复制到另一个列表？

有两种方法可以将源列表复制到另一个列表。

选项 1：使用 ArrayList 构造函数

```java
ArrayList<Integer> newList = new ArrayList<Integer>(sourceList);
```

选项 2：使用 Collection.copy()

使用 `Collections.copy()` 时，目标列表的大小应大于或等于源列表。

```java
ArrayList<Integer> newList = new ArrayList<Integer>(sourceList.size());
Collections.copy(newList, sourceList);
```

如果目标 List 没有足够的空间包含源列表的所有元素，`Collections.copy()` 将不会重新分配 List 的容量。它会抛出 `IndexOutOfBoundsException`。

`Collections.copy()` 的用处是它保证复制会在线性时间内完成。对于我们想要重用数组而不是在 ArrayList 构造函数中分配更多内存的场景，它非常有用。

`Collections.copy()` 的一个局限性是它只能接受 List 作为源和目标参数。

## 171. 哪些 Java Collection 类实现了 List 接口？

实现 List 接口的 Java 类有：

- AbstractList
- AbstractSequentialList
- ArrayList
- AttributeList
- CopyOnWriteArrayList
- LinkedList
- RoleList
- RoleUnresolvedList
- Stack
- Vector

## 172. 哪些 Java Collection 类实现了 Set 接口？

实现 Set 接口的 Java 类有：

- AbstractSet
- ConcurrentSkipListSet
- CopyOnWriteArraySet
- EnumSet
- HashSet
- JobStateReasons
- LinkedHashSet
- TreeSet

## 173. Java 中 Iterator 和 ListIterator 有什么区别？

Iterator 和 ListIterator 是 Java 中用于遍历数据结构的两个接口。它们之间的区别是：

- 1. ListIterator 只能用于遍历 List。但 Iterator 可以遍历 List、Set 和 Queue。
- 2. Iterator 只能向一个方向遍历元素。它只能向前移动。ListIterator 可以向两个方向遍历元素，即向后和向前移动。
- 3. Iterator 无法提供数据结构中元素的索引。ListIterator 使用 `nextIndex()` 和 `previousIndex()` 等方法在遍历期间获取元素的索引。
- 4. Iterator 不允许在遍历集合时向集合中添加元素。它会抛出 `ConcurrentModificationException`。ListIterator 允许我们在遍历列表的任何时间添加元素。
- 5. 无法使用 Iterator 替换现有元素的值。ListIterator 提供了 `set(e)` 方法来替换由 `next()` 或 `previous()` 方法返回的最后一个元素。

## 174. Iterator 和 Enumeration 有什么区别？

两者都是 Java 中用于访问数据结构的接口。它们的主要区别是：

- 1. Enumeration 是较旧的接口。Iterator 是较新的接口。
- 2. Enumeration 只能遍历旧集合（legacy collections）。Iterator 可以同时遍历旧集合和新集合。
- 3. Enumeration 不提供 `remove()` 方法。因此我们无法在遍历期间删除任何元素。Iterator 提供了 `remove()` 方法。
- 4. Iterator 是一个快速失败（fail-fast）接口，如果任何线程尝试修改正在迭代的集合中的元素，它会抛出 `ConcurrentModificationException`。Enumeration 不是快速失败的。
- 5. Iterator 中的方法名比 Enumeration 中的短。

## 175. ArrayList 和 LinkedList 数据结构之间有什么区别？

ArrayList 和 LinkedList 数据结构之间的主要区别是：

- 1. 数据结构：ArrayList 是一个基于索引的动态数组。LinkedList 是双向链表（Doubly Linked List）结构。
- 2. 插入：在 LinkedList 中插入新元素更容易，因为不需要调整数组大小。ArrayList 中的插入复杂度是 O(n)，因为可能需要调整数组大小并将其内容复制到新数组。
- 3. 删除元素：LinkedList 在删除元素方面的性能优于 ArrayList。
- 4. 内存使用：LinkedList 使用的内存比 ArrayList 多，因为它必须维护指向下一个和上一个节点的链接。
- 5. 访问：LinkedList 访问元素较慢，因为我们必须逐个遍历列表以访问正确的位置。

## 176. Java 中 Set 和 Map 有什么区别？

Java 中 Set 和 Map 的主要区别是：

- 1. 重复元素：Set 不允许插入重复元素。Map 不允许使用重复键，但允许为唯一的键插入重复的值。
- 2. 空值：Set 允许插入最多一个 null 值。在 Map 中，我们最多有一个 null 键以及任意数量的 null 值。
- 3. 排序：Set 不维护元素的任何顺序。Set 的某些子类（如 `LinkedHashSet`）可以按顺序对元素。Map 不维护其元素的任何顺序。它的某些子类（如 `TreeMap`）按键的升序存储 map 元素。

### 177. Dictionary 类的作用是什么？

Java 中的 Dictionary 类用于存储键值对。任何非空对象都可以作为键或值。但我们不能在 Dictionary 中插入 null 键或 null 对象。

Dictionary 类现在已弃用（deprecated）。因此不应在新的实现中使用。

### 178. Java 中 HashMap 的默认负载因子是多少？

HashMap 的默认负载因子是 0.75。

### 179. 负载因子（load factor）在 HashMap 中有什么意义？

负载因子决定了 HashMap 容量翻倍的阈值。例如，如果初始容量为 16 负载因子为 0.75，那么当存储 12 个元素时容量将翻倍。

## 180. HashSet 和 HashMap 的主要区别是什么？

HashSet 和 HashMap 的区别是：

- 1. **基类**：HashSet 类实现了 Set 接口。而 HashMap 类实现了 Map 接口。
- 2. **存储**：HashSet 用于存储不同的对象。HashMap 用于存储键值对，以便可以通过键检索。
- 3. **重复元素**：HashSet 不允许重复元素。HashMap 也不允许重复键。但可以在 HashMap 中存储重复的值。
- 4. **空元素**：在 HashSet 中可以存储一个 null 值。在 HashMap 中可以存储一个 null 键，以及任意数量的 null 值。
- 5. **元素类型**：HashSet 包含对象类型的元素。而 HashMap 包含项（键值对）。
- 6. **迭代**：可以通过 Iterator 迭代 HashSet。但 HashMap 必须转换为 Set 才能迭代。

## 181. Java 中 HashSet 和 HashMap 有什么相似点？

正如名称所示，HashSet 和 HashMap 都是基于哈表的集合。它们的相似之处是：

- 1. **线程安全**：HashMap 和 HashSet 都是非同步集合。因此它们对于线程安全操作并不友好。为了使它们线程安全，我们需要显式使用同步版本。
- 2. **元素顺序**：这些类都不保证元素的顺序。它们是无序集合。
- 3. **内部实现**：HashMap 在内部支持了 HashSet。因此 HashSet 使用 HashMap 来执行操作。
- 4. **性能**：这两个集合在插入和删除元素等基本操作上提供了常数时间性能。

## 182. 重写 equals() 方法的原因是什么？

Object 类中的 `equals()` 方法用于检查两个对象是否相同。如果我们需要自定义实现，可以重写该方法。

例如，Person 类有姓、名和年龄。如果我们希望两个 Person 对象根据姓名和年龄判断是相等的，那么我们就可以重写 `equals()` 方法来比较 Person 对象的姓、名和年龄。

通常在 HashMap 的实现中，如果我们想用一个对象作为键，那么我们需要重写 `equals()` 方法。

### 183. 如何同步 List、Set 或 Map 中的元素？



有时我们需要让集合是线程安全的，以便在多线程环境中使用。在 Java 中，`Collections` 类提供了一些实用的静态方法，可以将 `List`、`Set` 或 `Map` 变为同步集合。其中一些方法如下：

```
static <T> Collection<T> synchronizedCollection(Collection<T> c)
返回一个由指定集合支持的同步（线程安全）集合。
```

```
static <T> List<T> synchronizedList(List<T> list)
返回一个由指定列表支持的同步（线程安全）列表。
```

```
static <K,V> Map<K,V> synchronizedMap(Map<K,V> m)
返回一个由指定映射支持的同步（线程安全）映射。
```

```
static <T> Set<T> synchronizedSet(Set<T> s)
返回一个由指定集合支持的同步（线程安全）集合。
```

```
static SortedMap<K,V> synchronizedSortedMap(SortedMap<K,V> m)
返回一个由指定映射支持的同步（线程安全）排序映射。
```

```
static <T> SortedSet<T> synchronizedSortedSet(SortedSet<T> s)
返回一个由指定排序集合支持的同步（线程安全）排序集合。
```

### 184. 什么是哈希冲突？Java 如何处理 HashMap 中的哈希冲突？

在哈希场景下，有时两个不同的对象可能具有相同的 HashCode，但它们并不相等。因此，Java 在向 `HashMap` 存储具有相同 HashCode 的不同对象时会遇到问题。这种现象就是哈希冲突。

解决或避免哈希冲突的技术有很多。但在 `HashMap` 中，如果发生哈希冲突，Java 只会将旧 Key 处的对象替换为新对象。

### 185. 哈希冲突的解决技术有哪些？

为了解决哈希冲突，我们可以使用以下技术之一：

- 链地址法
- 列表头单元链地址法
- 结合哈希开放寻址法
- 布谷哈希开放寻址法
- 跳表哈希
- 罗宾汉哈希

### 186. 队列（Queue）和栈（Stack）数据结构有什么区别？

队列是一种 FIFO 数据结构，FIFO 代表先入先出。这意味着先添加的元素先从队列中移除。队列的一个现实世界例子是车站买票的排队。先进入队列的人先被服务。

栈是一种 LIFO 数据结构，LIFO 代表后进先出。最后添加的元素先从集合中移除。在栈中，元素从栈的顶部添加或移除。

栈的一个现实世界例子是浏览器的后退按钮。我们只能一个一个地返回，它的工作顺序与网页添加到历史记录的顺序相反。

### 187. Java 中的 Iterator（迭代器）是什么？

`Iterator` 是 Java 中的一个接口，用于访问集合中的元素。

它位于 `java.util` 包中。

它提供了遍历 Java 中 `Collection` 类的方法。

Java 中的 `Iterator` 接口基于迭代器设计模式。通过使用 `Iterator`，可以遍历对象容器并访问容器中的对象。在 Java 中，对象容器就是 `Collection` 类。

### 188. Java 中 Iterator 和 Enumeration 有什么区别？

Java 中 `Iterator` 和 `Enumeration` 之间的主要区别是：

1.  **版本**：`Enumeration` 接口自 JDK 1.0 起就存在。`Iterator` 接口是在 Java 1.2 中引入的。
2.  **`remove()` 方法**：`Enumeration` 和 `Iterator` 接口的主要区别在于 `remove()` 方法。`Enumeration` 只能遍历集合。如果我们使用 `Enumeration`，在遍历过程中无法对集合进行任何修改。`Iterator` 接口提供了 `remove()` 方法，可以在遍历集合时移除元素。`Enumeration` 接口中没有 `remove()` 方法。
3.  **方法名**：`Iterator` 接口中的方法名为 `hasNext()`、`next()`、`remove()`。`Enumeration` 接口中的方法名为 `hasMoreElements()`、`nextElement()`。
4.  **遗留接口**：`Enumeration` 被认为一个遗留接口。它用于遍历 `Vector`、`Stack` 和 `Hashtable` 等遗留类。`Iterator` 是较新的接口，用于遍历 Java 集合框架中几乎所有的类。
5.  **快速失败与故障安全**：`Iterator` 基于快速失败原则。如果在对该集合进行迭代期间修改了集合，它会抛出 `ConcurrentModificationException`。`Enumeration` 基于故障安全原则。如果在遍历期间修改了集合，它不会抛出任何异常。
6.  **安全性**：由于 `Iterator` 是快速失败的且不允许其他线程修改集合，因此被认为比 `Enumeration` 更安全。

### 189. Java 中 Enumeration 的实现使用了什么设计模式？

`Enumeration` 基于迭代器设计模式。迭代器设计模式提供了一个具有遍历对象集合方法的通用接口。它隐藏了集合的底层实现细节。

### 190. 将对象作为 HashMap 的键时，需要重写哪些方法？

如果我们想在 Java 的 `HashMap` 中使用对象作为键，那么必须确保它已经实现了 `equals()` 和 `hashCode()` 方法。

### 191. 如何反转一个 List？

在 `Collections` 类中，Java 提供了一个 `reverse(List)` 方法可以用于反转列表。

例如：

```
Collections.reverse(myList);
```

### 192. 如何将 String 数组转换为 List？

Java 在 `java.util` 包中提供了 `Arrays` 类。`Arrays` 类有一个 `asList` 方法，接受数组并返回 List。

```
String[] myArray = {"George", "Jack"};
List myList = Arrays.asList(myArray);
```

### 193. Queue 接口的 peek()、poll() 和 remove() 方法有什么区别？

在 Java `Queue` 中，`poll()` 和 `remove()` 方法可用于移除头部。主要区别出现在队列为空时。

如果队列为空，`poll()` 方法返回 `null`。如果队列为空，`remove()` 方法会抛出 `NoSuchElementException`。

在 Java `Queue` 中，`peek()` 方法获取头部但不移除它。如果队列为空，`peek()` 方法返回 `null`。

### 194. Java 中 Array 和 ArrayList 有什么区别？

Java 中 `Array` 和 `ArrayList` 之间的主要区别是：

1.  **大小**：Java 数组的大小是固定的。创建后无法更改数组的大小。`ArrayList` 的大小是动态的。向 `ArrayList` 添加元素时，它的容量会增加。
2.  **性能**：Java `Array` 和 `ArrayList` 在不同操作下的性能不同。
3.  **`add()` 或 `get()`**：向数组或 `ArrayList` 对象添加或获取元素的性能相似。这些都是常数时间操作。
4.  **`resize()`**：`ArrayList` 的自动调整大小会影响性能。`ArrayList` 内部由数组支持。在 `resize()` 时，使用临时数组将元素从旧数组复制到新数组。
5.  **基本类型**：数组可以包含基本数据类型以及对象。但 `ArrayList` 不能包含基本类型。它只包含对象。
6.  **迭代器**：我们在 `ArrayList` 中使用 `Iterator` 对象来遍历元素。我们使用 `for` 循环遍历数组中的元素。
7.  **类型安全**：Java 通过泛型帮助确保 `ArrayList` 元素的类型安全。数组可以包含相同类型的对象。如果我们尝试在数组中存储不同数据类型的对象，会抛出 `ArrayStoreException`。

### 195. 如何在 Java 的 HashMap 集合中插入、删除和检索元素？

我们使用以下方法在 `HashMap` 中插入、删除和检索元素。

1.  **检索**：我们使用 `get()` 方法从 `HashMap` 中检索元素。
    `Value get(Object key)`
2.  **插入**：我们使用 `put()` 方法在 `HashMap` 中插入键值对。
    `Value put(Key k, Value v)`
3.  **删除**：我们使用 `remove()` 方法从 `HashMap` 中删除键值对。
    `Value remove(Object key)`

### 196. Java 中 HashMap 和 ConcurrentHashMap 的主要区别是什么？

`HashMap` 和 `ConcurrentHashMap` 之间的主要区别是：

1.  **同步**：`HashMap` 不是同步的。但 `ConcurrentHashMap` 是一个同步对象。
2.  **空键**：`HashMap` 可以有一个 `null` 键和任意数量的 `null` 值。`ConcurrentHashMap` 不能有 `null` 键或 `null` 值。
3.  **多线程**：`ConcurrentHashMap` 在多线程环境下运行良好。

### 197. Java 中以下集合类性能从低到高的顺序是什么？

性能从低到高的顺序是：

- `Hashtable`
- `Collections.SynchronizedMap`
- `ConcurrentHashMap`
- `HashMap`

`Hashtable` 的性能最差，`HashMap` 的性能最好。

### 198. 为什么 Java 中的 Map 接口没有继承 Collection 接口？

`Map` 是集合对象。但 Java 中的 `Map` 接口与 `Collection` 接口不兼容。

`Map` 既需要键也需要值。因此它需要参数来向 `HashMap` 添加元素。

但 `Collection` 接口提供只有一个参数的 `add(Object o)` 方法。

`Map` 集合必须提供像 `valueSet`、`keySet` 等方法。这些方法是 `Map` 集合特有的。而 `Collection` 接口中的方法可以被 `List`、`Set`、`Queue` 等复用。

### 199. Java 中遍历列表元素有哪些方法？

在 Java 中，遍历列表元素主要有两种方式：

1.  **Iterator（迭代器）**：我们可以获取列表的迭代器并使用它来遍历列表中的对象。
2.  **For-each loop（增强 for 循环）**：我们可以使用 for-each 循环来遍历列表的所有元素。

### 200. 什么是 CopyOnWriteArrayList？它与 Java 中的 ArrayList 有什么区别？

`CopyOnWriteArrayList` 是在 Java 5 版本引入的。它是一个线程安全的集合。它类似于 `ArrayList`。

在 `CopyOnWriteArrayList` 中，所有的可变操作（`add`、`set` 等）都是通过对底层数组进行创建新副本来实现的。

`CopyOnWriteArrayList` 的迭代器保证不会抛出 `ConcurrentModificationException`。但迭代器也不会反映在迭代器创建后发生在列表上的任何添加或删除操作。

`CopyOnWriteArrayList` 允许包括 `null` 在内的所有元素。

### 201. HashMap 中的 remove() 方法是如何实现的？

`HashMap` 中的 `remove()` 方法使用的逻辑类似于 `get()` 方法中的逻辑。首先，我们为条目在 `HashMap` 中定位正确的桶。然后在该桶内，我们删除元素 `e`。这与从单链表中删除节点相似。

如果 `e` 是桶中的第一个元素，我们将 Hash 对应的元素设置为 `e.next`。否则，我们将 `e` 之前的一个元素的 `next` 字段处设置为 `e.next`。

### 202. Java 集合中的 BlockingQueue 是什么？

`BlockingQueue` 是在 Java 1.5 中引入的。它扩展了 Java 中的 `Queue` 接口。

`BlockingQueue` 支持在检索元素时等待队列变为非空的操作。它还支持在存储元素时等待队列空间可用的操作。

`BlockingQueue` 的一些特性包括：

- 它不接受 `null` 元素。
- 它的主要用途是生产者-消费者问题。
- `BlockingQueue` 的实现是线程安全的。
- 它可以用于线程间通信。
- 它不支持任何形式的“关闭”或“停机”操作来表示将不再添加更多项。

### 203. Java 中的 TreeMap 类是如何实现的？

在内部，Java 中的 `TreeMap` 类使用红黑树。

它是一个 `NavigableMap`。该映射按自然顺序对键排序，或者可以使用创建时提供的 `Comparator`。

Java 中的 `TreeMap` 实现不是同步的。

### 204. Java 中 Fail-fast（快速失败）和 Fail-safe（安全失败）迭代器的区别是什么？

Fail-fast 和 Fail-safe 迭代器的区别如下：

- Fail-fast 迭代器抛出 `ConcurrentModificationException`。但 Fail-safe 迭代器不会抛出此异常。
- Fail-fast 迭代器不复制原始集合。Fail-safe 迭代器创建原始对象的副本。
- Fail-fast 迭代器在遇到失败时尝试立即抛出异常。Fail-safe 迭代器在集合的副本上工作而不是原始集合。

### 205. Java 中的 ConcurrentHashMap 是如何工作的？

`ConcurrentHashMap` 扩展了 Java 中的 `AbstractMap`。它是在 Java 1.5 中引入的。它为基于 `HashMap` 的集合提供了并发支持。

`ConcurrentHashMap` 中的所有方法都是线程安全的。

内部有一个 `Hashtable` 支撑 `ConcurrentHashMap`。`Hashtable` 支持用于数据检索以及对 `ConcurrentHashMap` 更新的并发方法。

它还支持并行操作。这些操作接受参数。

### 206. hashCode() 和 equals() 方法的重要性是什么？

在 `HashMap` 集合中，键对象实现 `hashCode()` 和 `equals()` 方法是非常重要的。如果所有键的 `hashCode()` 都返回相同的值，那么当 `HashMap` 将相同的视为不同的时就会出现问题。它将覆盖掉该键值对。

正确实现 `hashCode()` 和 `equals()` 方法对于高效的 `HashMap` 至关重要。

### 207. Java 中 hashCode() 和 equals() 方法的约定是什么？

Java 中 `hashCode()` 和 `equals()` 的约定如下：

- 如果 `object1.equals(object2)`，则 `object1.hashCode() == object2.hashCode()` 始终为真。这意味着如果两个对象相等，它们的 hashCode 应该是相同的。
- 如果 `object1.hashCode() == object2.hashCode()` 为真，并不保证 `object1.equals(object2)`。这意味着如果两个对象的 hashCode 相同，值可能是不同的。

### 208. Java 中的 EnumSet 是什么？

`EnumSet` 是 `Set` 的特殊实现。

1.  **用途**：它主要用于枚举类型。
2.  **单一枚举类型**：创建集合时，`EnumSet` 中的所有元素必须来自同一个枚举类型。
3.  **位向量**：内部，`EnumSet` 表示为位向量。
4.  **迭代器**：`EnumSet` 的迭代器按自然顺序遍历元素。（即枚举常量声明的顺序）。
5.  **空值**：`EnumSet` 不允许 `null` 元素。如果我们尝试插入 `null` 元素，会抛出 `NullPointerException`。
6.  **线程安全**：`EnumSet` 不是同步集合。在多线程场景下，应对 `EnumSet` 进行同步。
7.  **位标志**：`EnumSet` 是基于 int 的“位标志”实现的极佳替代方案。

### 209. Java 中主要的并发集合类有哪些？

Java 1.5 提供了一个新包 `java.util.concurrent`。该包包含了线程安全的集合类。这些集合类可以在迭代时进行修改。这些类的迭代器是安全失败的。

Java 8 中主要的并发集合类有：

- `ArrayBlockingQueue`
- `CopyOnWriteArrayList`
- `CopyOnWriteArraySet`
- `ConcurrentHashMap`
- `ConcurrentLinkedDeque`
- `ConcurrentLinkedQueue`
- `LinkedBlockingQueue`
- `LinkedBlockingDeque`
- `PriorityBlockingQueue`

### 210. 在 Java 中如何将 Collection 转换为同步集合？

Java 在 `java.util.Collections` 类中提供了一个简单的方法，可以将普通集合转换为线程安全的集合。



我们可以使用`synchronizedCollection()`方法来实现这一目的。

对于任何类型为`T`的类，我们可以使用以下方法：

```java
static <T> Collection<T> synchronizedCollection(Collection<T>)
```

## 211. IdentityHashMap 与 Java 中的普通 Map 有什么区别？

Java 中的`IdentityHashMap`实现了`Map`接口。但它不是一个通用实现。它通过对`equals()`方法的不同实现，违反了`Map`接口的通用约定。

在`IdentityHashMap`中，两个键`k1`和`k2`相等当且仅当`(k1==k2)`。（在普通的 Map 实现（如`HashMap`）中，两个键`k1`和`k2`被视为相等当且仅当`(k1==null ? k2==null : k1.equals(k2))`）。

它使用哈希表实现`Map`接口，在比较键（以及值）时使用引用相等性（reference-equality）代替对象相等（object-equality）。

## 212. IdentityHashMap 的主要用途是什么？

`IdentityHashMap`的主要用途是：

1. 拓扑结构保持：`IdentityHashMap`类的典型用途是保持拓扑结构的对象图转换，例如序列化或深拷贝。在这种情况下，程序必须维护一个“节点表”来跟踪所有已过的对象引用。
2. 即使不同的对象恰好相等，节点表也不应将它们视为相等的。
3. 代理对象：该类的另一个用途是维护代理对象。调试程序必须为被调试程序中的每个对象维护一个代理对象。

## 213. 我们如何提高 IdentityHashMap 的性能？

`IdentityHashMap`类有一个用于性能改进的调优参数：`expectedMaxSize`。

该参数是该 map 预期持有的键值对映射的最大数量。

我们可以使用此参数来确定哈希表中初始的桶（buckets）数量。预期最大值与桶数量之间的精确关系尚未规定。

如果键值对映射的数量超过了预期最大值，桶的数量就会增加。

增加桶的数量也被称为重哈（rehashing）。重哈可能相当昂贵。因此，最好创建一个具有足够大预期最大值的标识性哈希 map。

但是，对 Map 集合进行迭代所需的时间与哈希表中桶的数量成正比。因此，由于桶数量过多，迭代可能会消耗额外的时间。

因此，设置`expectedMaxSize`的值时应同时考虑这两个方面。

## 214. IdentityHashMap 是线程安全的吗？

`IdentityHashMap`的实现不是线程安全的，因为它的方法没有同步（synchronized）。

`IdentityHashMap`的`iterator`方法返回的迭代器是快速失败（fail-fast）的。但迭代器的快速失败行为无法保证。

由于迭代器是快速失败的，它会抛出`ConcurrentModificationException`。

## 215. Java 中的什么是 WeakHashMap？

`WeakHashMap`是一个与`IdentityHashMap`相似的类。

在内部，它由`Hashtable`表示。

它不是一个同步类。我们可以通过`Collections.synchronizedMap()`方法让`WeakHashMap`变得线程安全。

当`WeakHashMap`中的某个项不再被普通使用时，它会被自动移除。

给定键的映射的存在防止该键被垃圾回收器丢弃。

`WeakHashMap`也允许`null`键和`null`值。

## 216. 在 Java 中如何让 Collection 类只读？

在 Java 中，有实用的方法可以将 Collection 类变为只读。我们可以使用以下方法之一使 Collection 为只读：

- `Collections.unmodifiableMap(Map m)`
- `Collections.unmodifiableList(List l)`
- `Collections.unmodifiableSet(Set s)`
- `Collections.unmodifiableCollection(Collection c)`

## 217. Java 中何时抛出 UnsupportedOperationException？

在 Java 集合中，如果请求的操作不受集合支持，则抛出`UnsupportedOperationException`。

这是一个在可选操作上抛出的未检查异常（unchecked exception）。

如果在只读集合存在可选的`add()`或`remove()`方法，则可能会抛出此异常。

## 218. 假设有一个 Customer 类。我们将 Customer 类的对象添加到 ArrayList 中。我们如何通过 Customer 类的`firstName`属性对 ArrayList 中的 Customer 对象进行排序？

处理此场景有两种方法。我们可以使用这些选项：

- Comparable：为`Customer`类实现`Comparable`接口，并通过`firstName`属性比较客户对象。
- Comparator：实现`Comparator`以根据`firstName`属性比较两个`Customer`对象。然后在`Collections`类的`sort`方法中使用此比较器对象。

## 219. 同步集合（Synchronized Collection）和并发集合（Concurrent Collection）之间有什么区别？

在 Java 1.5 中，SDK 添加了许多并发集合类。这些是`ConcurrentHashMap`、`CopyOnWriteArrayList`、`BlockingQueue`等。

Java 还提供了工具方法，通过使用`Collections.synchronizedList()`和`Collections.synchronizedMap()`方法来获取`ArrayList`、`HashMap`等集合的同步副本。

主要区别在于性能。并发集合类的性能优于同步集合类，因为它们只锁定类的一个部分以实现并发和线程安全。

## 220. Java 中使用 ConcurrentHashMap 的场景是什么？

`ConcurrentHashMap`更适用于我们有多个读取线程和一个写入线程的场景。在这种情况下，map 仅对写操作进行锁定。

如果我们有相同数量的读取线程和写入线程，`ConcurrentHashMap`的性能与`Hashtable`或同步`HashMap`相似。

## 221. 在 Java 中如何创建一个空的 Map？

有两种方法可以创建一个空的 Map。

1. 不变：如果我们需要一个不可变的空 Map，可以使用以下代码：

```java
myMap = Collections.emptyMap();
```

2. 任意：对于所有其他场景，可以通过`new`方法使用以下代码：

```java
myMap = new HashMap();
```

## 222. Collection 的 remove() 方法与 Iterator 的 remove() 方法有什么区别？

在`Collection`接口中，`remove(Object o)`方法用于从集合中删除对象。

`List`接口还提供了`remove(int index)`方法根据特定索引删除对象。

当没有线程正在遍历集合时，这些方法用于从集合中移除项。

当我们正在遍历集合时，必须使用迭代器的`remove()`方法。该方法从迭代器的视角移除当前元素。如果我们使用`Collection`或`List`的`remove`方法，将会得到`ConcurrentModificationException`。

因此，建议在通过迭代器遍历集合时使用迭代器的`remove()`方法。

## 223. 在数组和 ArrayList 之间，哪一个是存储对象的首选集合？

`ArrayList`在内部由数组支持。在 Java 中，使用`ArrayList`比数组有许多可用性优势。

数组在创建时就具有固定长度。一旦创建，我们就无法更改其长度。

`ArrayList`的大小是动态的。一旦它达到阈值，它会自动分配新数组并将旧数组的内容复制到新数组。

此外`ArrayList`提供了泛型（Generics）的支持。但数组不支持泛型。

例如，如果在运行时向 String 数组存储一个`Integer`对象，将抛出`ArrayStoreException`。而如果我们在编译时使用`ArrayList`则会获得错误。这有助于防止错误在运行时发生。

如果我们预先知道大小并且不需要调整集合，则应该使用数组代替`ArrayList`。

## 224. 在 Java 中可以用 ConcurrentHashMap 替换 Hashtable 吗？

是的，在 Java 中可以用`ConcurrentHashMap`替换`Hashtable`。

但它需要仔细观察，因为`Hashtable`的锁定行为与`ConcurrentHashMap`不同。

`Hashtable`锁定的是整个 Map 而不是部分 Map。复合操作如`if(Hashtable.get(key) == null) put(key, value)`在`Hashtable`中可以工作，但在`ConcurrentHashMap`中则不行。

在`ConcurrentHashMap`中，我们使用`putIfAbsent()`方法来处理此类场景。

## 225. CopyOnWriteArrayList 类与 ArrayList 和 Vector 类有什么区别？

`CopyOnWriteArrayList`是在 Java 1.5 中引入的。它实现了`List`接口。

它比 Synchronized List 提供了更好的并发访问方法。

在`CopyOnWriteList`中，并发是通过每次写入时复制`ArrayList`并替换原始数组来实现的，而不是通过锁定。

`CopyOnWriteArrayList`在迭代（Iteration）期间不会抛出任何`ConcurrentModificationException`。

它是一个线程安全的列表。

在并发方面，它与`Vector`不同。`CopyOnWriteArrayList`通过减少读写者之间的竞争提供了更好的并发性。

## 226. 为什么 ListIterator 有 add() 方法而 Iterator 没有？

`ListIterator`可以在集合的两个方向上迭代。它维护了两个指针，分别指向上一个元素和下一个元素。在`ListIterator`中，我们可以使用`add()`方法将元素插入到`next()`方法返回的元素之前。

因此，后续对`next()`方法的调用不会受到影响。对`previous()`方法的调用将返回新添加的元素。

在`Iterator`中，我们只能在一个方向上遍历。因此在那里没有`add()`方法的意义。

## 227. 为什么我们在迭代过程中有时会遇到 ConcurrentModificationException？

当我们在`Iterator`遍历集合时，使用`Collection`或`List`的`remove()`方法移除对象，就会得到`ConcurrentModificationException`。如果`Iterator`检测到集合结构发生了任何结构性变化，它就会抛出`ConcurrentModificationException`。

## 228. 在 Java 中如何将 Map 转换为 List？

在 Java 中，Map 有三个集合视图：

- 键集（key set）
- 值集（value set）
- 键值对集（key-value set）

这些 Set 中的每一个都可以通过构造函数转换为 List：

示例代码如下：

```java
List keyList = new ArrayList(map.keySet());
List valueList = new ArrayList(map.values());
List entryList = new ArrayList(map.entrySet());
```

## 229. 如何在 Java 中创建一个具有反向视图和查找功能的 Map？

在 Map 中，我们可以通过一个唯一的键来查找值。在具有反向视图和查找功能的 Map 中，即使是值也是唯一的。因此，键和值之间存在一对一的映射关系，反之亦然。

如果我们在 Map 上启用这一约束，那么就可以通过值来查找键。这种数据结构被称为双向映射（bi-directional map）。

JDK 中没有提供类似于反向查找 Map 的内置数据结构。

但 Apache Common Collections 和 Guava 库提供了双向映射的实现。它们被称为`BidiMap`和`BiMap`。这两种数据结构都强制了键和值之间一对一映射的约束。

## 230. 如何创建 Map 的浅拷贝？

在 Java 中，Map 接口的大多数实现都提供了一个构造函数来创建另一个 map 的拷贝。但`copy`方法不是同步的。

因此，当一个线程在复制 map 时，另一个线程可以修改它。

为了防止这种情况发生，我们应该使用`Collections.synchronizedMap()`方法先创建一个线程安全的 map。

创建浅拷贝的另一种方法是使用`clone()`方法。但这不被认为是推荐的方法。

## 231. 为什么我们不能在 Java 中创建泛型数组？

Java 不允许创建以泛型作为元素的数组。

在 Java 中，数组必须在运行时知道其元素的类型信息。

此信息在运行时用于如果插入的元素的数据类型与数组的类型不匹配，则抛出`ArrayStoreException`。

在泛型的情况下，集合的类型信息在运行时会被类型擦除（Type Erasure）抹掉。由于这一点，数组无法使用泛型作为元素。

## 232. Java 中的 PriorityQueue 是什么？

`PriorityQueue`是基于队列（Queue）的数据结构。与 Queue 不同，`PriorityQueue`中的元素不是按先进先出（FIFO）顺序返回的。

`PriorityQueue`维护元素的自然顺序，或者使用初始化时提供的`Comparator`。

它是一个基于优先级堆（priority heap）的无界队列。

`PriorityQueue`不允许`null`值。我们不能向`PriorityQueue`添加任何未提供自然排序的对象。

Java 中的`PriorityQueue`不是线程安全的。

它入队和出队操作的时间复杂度为 O(log n)。

## 233. 使用 Java Collections Framework 时，需要记住的重要点有哪些？

使用 Java Collections Framework 时需要记住的一些重要点包括：

1. 接口：对于 Collections，我们应该使用泛型接口编写代码，而不是具体的实现。这样我们就可以保持在以后更改实现的灵活性。
2. 泛型：我们应该使用泛型来实现类型安全，并避免运行时出现`ClassCastException`。
3. Collections：建议使用 Collections 工具类来进行算法以及各种其他常用的集合方法。
4. 正确的类型：我们必须选择正确的集合类型。
5. 初始大小：在某些集合类中，我们可以指定初始大小。
6. Map：我们应该使用 Java 提供的不可变类。

## 234. 如何将集合作为参数传递并确保方法无法修改它？

为了确保方法无法修改集合，我们必须将其变为只读。

我们可以通过使用`Collections.unmodifiableCollection(c)`方法将集合变为只读。

这将确保任何更改集合的操作都会抛出`UnsupportedOperationException`。

## 235. 你能解释 Java HashMap 如何工作吗？

在 Java 中，`HashMap`基于哈希（hashing）原理工作。

Java 中的`HashMap`在桶（bucket）中存储键和值对象。它是作为实现`Map.Entry`接口的 Entry 对象存储的。

`HashMap`中的键对象必须实现`hashCode()`和`equals()`方法。

当使用`put()`方法存储键值对时，`HashMap`实现调用键对象的`hashCode()`方法来计算哈希，该哈希用于找到存储 Entry 对象的桶。

当使用`get()`方法检索对应某个键的值时，我们首先计算键的哈希。然后使用此哈希找到存储该特定键的桶。

一旦找到了键对象的位置，可能会出现多个键存储在同一个位置。这时我们使用`equals()`方法来找到精确的键对象。

## 236. 你能解释 HashSet 在 中是如何实现的吗？

在内部，`HashSet`使用`HashMap`来存储元素并维护元素的唯一性。

当我们创建一个`HashSet`对象时，也会创建一个相应的`HashMap`对象。

当我们向`HashSet`插入元素时，它会被插入到相应的`HashMap`中。

## 237. Java 中的 NavigableMap 是什么？

正如其名，`NavigableMap`在 Java 中提供了导航 Map 键的能力。`NavigableMap`扩展了`SortedMap`接口。

`NavigableMap`的一些有趣的方法包括`descendingKeySet()`、`descendingMap()`、`headMap()`和`tailMap()`。

## 238. NavigableMap 的 descendingKeySet() 和 descendingMap() 方法之间有什么区别？

`NavigableMap`的`descendingKeySet()`方法返回一个`NavigableSet`，其中元素的存储顺序与原始键集相反。



返回的视图在内部由 `NavigableMap` 的原始 `KeySet` 表示。因此，对该降序集合的任何更改也会反映在原始集合中。

但并不建议直接从键集中删除元素。我们应该使用 `Map.remove()` 方法。

`NavigableMap` 的 `descendingMap()` 方法返回一个 `NavigableMap`，它是原始 Map 的一个反向视图。该视图中的元素顺序与原始 Map 中的元素顺序相反。对此视图的任何更改也会反映在原始 Map 中。

# 239. NavigableMap 相比 Map 的优势是什么？

`NavigableMap` 相比 `Map` 的主要优势是导航能力（Navigation capability）。

它在一个集合中同时提供了 `Map`、`SortedMap` 和导航的功能。

它甚至可以为给定的搜索目标返回最匹配的项。

诸如 `lowerKey`、`floorKey`、`ceilingKey` 和 `higherKey` 等方法仅返回相关的键。所有这些方法的设计目的都是定位，而不是遍历条目。

# 240. NavigableMap 的 headMap()、tailMap() 和 subMap() 方法之间有什么区别？

`headMap()` 方法返回原始 `NavigableMap` 的视图，该视图包含小于给定元素的元素。

```
NavigableMap original = new TreeMap();
original.put("1", "1");
original.put("2", "2");
original.put("3", "3");

// 这个 headmap1 将包含元素 "1" 和 "2"
SortedMap headmap1 = original.headMap("3");

// 这个 headmap2 将包含元素 "1", "2", 和 "3"，因为
// "inclusive"=true
NavigableMap headmap2 = original.headMap("3", true);
```

`tailMap()` 方法的工作原理与 `headMap()` 方法类似，但它返回所有大于给定输入元素的元素。

`subMap()` 方法接受两个参数，用于界定返回的视图 map 的边界。

这三个方法都以视图的形式返回原始 map 的子集。

# 241. 如何在 Java List 中按自然顺序（Natural order）对对象进行排序？

我们可以使用 `Collections.sort` 方法按自然顺序对 List 的元素进行排序。要使用此方法，必须确保元素对象实现了 `compareTo()` 方法。

我们还可以使用 `Comparator` 来定义 List 元素的自然排序。然后我们可以在 `Collections` 类的 `sort` 方法中使用这个自定义的 `Comparator`。

# 242. 如何在 Java 中从 List 获取 Stream？

从 Java 8 开始，从 List 获取 `Stream` 非常简单。我们只需要使用 `stream()` 方法即可从元素列表获取 `stream`。

# 243. 我们在 Java 中可以从 Stream 获取 Map 吗？

是的，我们可以从 Stream 的元素创建一个 Map。我们可以使用 `map()` 方法来获取 Map。

例如：

```
items.stream()
.map(item -> item.toLowerCase())
```

在这个示例中，我们正在创建一个 map，其中每个项对象都映射到它的小写等效项。

这也用于 Stream 上的 Map-Reduce 实现。

# 244. Java 中 Deque 的流行实现有哪些？

Java 中 `Deque` 接口最流行的两个实现是：

1. **ArrayDeque**: 它是 Deque 的可变大小数组实现。`ArrayDeque` 的容量可以根据程序需要而增加。它不是线程安全的实现。此外，`ArrayDeque` 迭代器是快速失败（fail-fast）的。

2. **LinkedList**: 这是 Java 中 `Deque` 接口的另一个流行实现。它不是同步的，因此不是线程安全的。它主要提供双向链列表的功能。

## 多线程

# 245. 什么是 Java 线程（Thread）？

Java 线程是运行在另一个进程或线程内部的轻量级进程。

它是应用程序中一条独立的执行路径。JVM 为每个线程提供它自己的方法调用栈。

当我们启动 JVM 时，Java 会启动一个线程。该线程会调用传递给 java 调用参数中的类的 `main` 方法。

### 246. 线程的优先级（priority）是什么？在调度中是如何使用的？

在 Java 中，每个线程都有优先级。该优先级指定为 1 到 10 之间的数字。

Java 调度器根据线程的优先级调度不同的线程。这也被称为抢占式调度（pre-emptive scheduling）。

优先级高的线程在执行上比优先级低的线程更具优先权。

### 247. Java 线程的默认优先级是什么？

在 Java 中，新线程的优先级与创建它的父线程的优先级相同。

线程的默认优先级是 5 (`NORM_PRIORITY`)。

# 248. Java 线程上可以设置哪三个不同的优先级？

我们可以在 Java 线程对象上设置以下三个优先级：

1. **MIN_PRIORITY**: 线程可以拥有的最低优先级。

2. **NORM_PRIORITY**: 分配给线程的默认优先级。

3. **MAX_PRIORITY**: 线程可以拥有的最高优先级。

线程默认优先级是 5 `NORM_PRIORITY`。`MIN_PRIORITY` 的值为 1，`MAX_PRIORITY` 的值为 10。

# 249. Thread 类中 join() 方法的目的是？

在 Java 中，线程调度器控制线程调度。但我们可以在线程上使用 `join()` 方法让当前线程等待另一个线程完成。

当我们使用 `join()` 时，当前线程停止执行。它会等待调用 `join()` 的线程完成。

这确保了当前线程只有在被连接的线程运行结束后才会继续。考虑以下示例：

```
public class ThreadJoin {
    Thread importantThread = new Thread(
        new Runnable() {
            public void run() {
                // 执行某些操作
            }
        });
    Thread currentThread = new Thread(
        new Runnable() {
            public void run() {
                // 执行某些操作
            }
        });
    importantThread.start(); // 第1行
    importantThread.join(); // 第2行
    currentThread.start(); // 第3行
}
```

在上述示例中，主线程正在执行。在第1行，名为 `importantThread` 的新线程已就绪。但在第2行，主线程连接了 `importantThread`。现在在 `importantThread` 完成之前，第3行的 `currentThread` 不会启动。

# 250. wait() 和 sleep() 方法之间的根本区别是什么？

`wait()` 和 `sleep()` 之间的主要区别是 `wait()` 是对象级别的方法，而 `sleep()` 是 `Thread` 类中的静态方法。等待线程可以通过另一个线程对所等待的监视器调用 `notify()` 来唤醒。但睡眠的线程无法被唤醒。

`wait()` 和 `notify()` 必须在同步块内发生。

当我们调用 `wait()` 时，当前线程会释放监视器并进入等待状态。然后另一个线程调用 `notify()` 来唤醒它。

在 `sleep()` 的情况下，当前线程不会释放监视器或锁。它只是睡眠一段时间。

# 251. 在 Java 中是否可以调用 run() 方法而不是 start() 方法？

是的。我们可以调用线程的 `run()` 方法。但它不会作为一个独立的线程工作。它将像主线程中的普通对象一样工作，线程之间不会发生上下文切换。

### 254. 多线程的缺点有哪些？

多线程具有某些缺点。这些是：

1. **难以调试**: 当出现问题时，多线程代码很难进行调试。

2. **并发管理困难**: 由于多个线程的存在，我们可能会遇到各种问题。

3. **代码迁移困难**: 将现有的单线程代码转换为多线程代码是非常困难的。

4. **死锁**: 在多线程情况下，等待相同资源的线程之间可能会发生死锁。

### 255. 什么是 Java 线程？

在 Java 中，线程是运行在另一个进程或线程内部的轻量级进程。它是应用程序中一个独立的执行路径。每个线程都在一个独立的栈栈帧中运行。

默认情况下，当调用类的 main 方法时，Java 会启动一个线程。

### 256. 线程的优先级是什么？在调度中是如何使用的？

在 Java 中，每个 `Thread` 都有优先级。这个优先级被指定为一个整数值。优先级值在调度中用于选择高优先线程进行执行。高优先线程在执行上比比低优先线程获得更多的优待。

任务调度器会先调度高优先级线程，然后是低优先级线程。

## 257. 抢占式调度调度器和时间片调度器之间有什么区别？

在抢占式调度中，最高的任务将持续获得执行时间，直到它进入等待状态或死亡状态，或者有一个更高优先级的任务进入调度队列。

在时间片调度中，每个任务都获得一个预定义的时间片进行执行，然后它进入准备就绪的任务池。调度器根据优先级和各种其他因素选择下一个任务进行执行。

## 258. 在 Java 中是否可以调用 run() 方法而不是 start() 方法启动线程？

可以。我们可以调用线程的 `run()` 方法。但它不会作为一个独立的线程运行。它将仅仅作为主线程中的一个普通对象运行，线程之间不会发生上下文切换。

## 259. 如果用户线程已经启动，如何将其转为守护线程？

不能。一旦线程已经启动，我们就无法将其转换为守护线程。

如果我们通过调用 `setDaemon()` 来这样做，它会抛出 `IllegalThreadStateException`。

## 260. 在 Java 中可以启动两次线程吗？

不可以。在 Java 中，我们只能对线程调用一次 `start()` 方法。如果我们调用两次，它会抛出异常。

### 261. 在什么场景下中断线程？

如果我们想唤醒处于睡眠或等待状态的线程，就可以中断它。

## 262. 在 Java 中，是否可以锁定一个对象以供线程独占使用？

可以。我们可以使用 `synchronized` 块来锁定一个对象。被锁的对象对任何其他线程都是不可见的。只有锁定它的线程才能访问它。

## 263. notify() 方法和 notifyAll() 方法有什么区别？

在 Java 中，`notify()` 方法用于解除处于等待状态特定线程的阻塞。而 `notifyAll()` 方法用于解除所有处于等待状态线程的阻塞。

## 264. 什么是 Java 中的守护线程？

Java 中的守护线程是一种低优先级线程，当程序结束时它不会阻止 JVM 退出。该线程会继续运行。垃圾回收（Garbage Collection）就是守护线程的一个例子。

### 265. 如何在 Java 中将普通线程变为守护线程？

我们可以在线程启动之前调用 `setDaemon(boolean)` 方法将线程更改为守护线程。

## 266. 如果用户线程已经启动，如何将其转为守护线程？

不能。一旦线程已经启动，我们就无法将其转换为守护线程。如果我们通过调用 `setDaemon()` 来这样做，它会抛出 `IllegalThreadStateException`。

## 267. 在 Java 中可以启动两次线程吗？

不可以。在 Java 中，我们只能对线程调用一次 `start()` 方法。如果我们调用两次，它会抛出异常。

### 268. 什么是 Java 中的关闭钩子（Shutdown hook）？

关闭钩子是 JVM 在关机之前被隐式调用的线程。它可以用于清理未使用的资源等。

我们可以使用 `java.lang.Runtime.addShutdownHook(Thread hook)` 方法来注册一个新的虚拟机关闭钩子。

### 269. 什么是 Java 中的同步（synchronization）？

Java 中的同步（Synchronization）概念用于多线程编程。

它是 Java 的一个特性，有助于控制多个线程对共享资源的访问。

它用于防止多个线程之间的死锁。

### 270. Java 中 Synchronized 块的目的是什么？

`synchronized` 块在 Java 多线程环境中有很多用途。其中一些用途包括：

- 它可以防止线程干扰
- 它还用于避免内存不一致性问题

通常情况下，`synchronized` 块的范围比方法的范围小。

### 271. 什么是静态同步（static synchronization）？

我们可以将一个方法标记为 `synchronized`。在静态同步中，锁是在类上的。

### 272. 什么是死锁状态？

死锁是指两个或多个线程互相等待对方释放资源的情况。有时是在等待某种资源。

### 273. 并发（concurrency）的含义是什么？

并发是指程序在机器的多个 CPU 核心上执行多个程序的能力。

## 274. 在 Java 境文中，进程和线程的主要区别是什么？

在 Java 中，进程指的是 Java 虚拟机（JVM）的运行。但线程存在于 JVM 内部，并可以由 Java 应用程序创建或停止。

### 275. 什么是调度器（Scheduler）？

调度器是一个实现调度算法的程序，用于管理 CPU 或 I/O 通道等有限资源。

大多数调度算法的目标是为进程/线程提供负载均衡，并保证每个进程/线程都能获得合理的时间范围来访问资源。

### 276. Java 程序中最少有多少个线程？

在 JVM 中，每个 Java 程序都运行在随 `java.exe` 启动的主进程中。因此，每个 Java 应用程序至少有一个线程。

### 277. Java 线程的属性有哪些？

每个 Java 线程拥有以下属性：

- **标识符（Identifier）**: 在 JVM 内唯一的 `long` 类型标识符
- **名称（Name）**: `String` 类型名称
- **优先级（Priority）**: `int` 类型优先级
- **状态（State）**: `java.lang.Thread.State` 类型状态
- **组（Group）**: 线程所属的组

### 278. Java 线程有哪些不同的状态？

以下是 Java 线程的不同状态：

- **New（新建）**: 处于 New 状态的线程尚未启动。
- **Runnable（可运行）**: 在 JVM 中执行的线程处于 Runnable 状态。
- **Blocked（阻塞）**: 等待监视器锁的线程处于 Blocked 状态。
- **Waiting（等待）**: 无限等待另一个线程执行特定操作的线程处于 Waiting 状态。
- **Timed_waiting（计时等待）**: 在指定的等待时间内等待另一个线程执行操作的线程处于 Timed_waiting 状态。
- **Terminated（已终止）**: 退出的线程处于 Terminated 状态。

### 280. 在 Java 中如何设置线程的优先级？

Java 中线程的优先级可以通过 `setPriority(int priority)` 方法来设置。

我们可以使用常量 `Thread.MAX_PRIORITY` 设置线程的最高优先级。

我们可以使用常量 `Thread.MIN_PRIORITY` 设置线程的最低优先级。

或者我们可以使用常量 `Thread.NORM_PRIORITY` 设置线程的默认优先级。

### 281. Java 中线程组（Thread Groups）的目的是什么？

在 Java 中，每个线程都属于一个线程组。

JDK 类 `java.lang.ThreadGroup` 提供了处理整个线程组的方法。

通过这些方法的帮助，我们可以中断组中的所有线程，或者设置组内所有线程的最大优先级。

因此，线程组用于对一组线程执行集体操作。

## 282. 为什么我们不应该通过调用 stop() 方法来停止线程？

`Thread` 类中的 `stop()` 方法是一个**已废弃的方法（deprecated）**。不建议使用它。

当我们调用 `stop()` 方法时，线程会释放它获取的所有监视器（monitors）。如果任何锁定的对象处于不一致状态，该状态将对所有其他线程可见。

当其他线程对此不一致的对象进行操作时，可能会导致意外行为。

因此，不建议通过调用 `stop()` 方法来停止线程。

## 283. 在 Java 中如何创建线程？

在 Java 中创建线程主要有两种方法：

1. **继承 Thread 类**: 我们可以扩展 `java.lang.Thread` 类并实现 `run()` 方法。调用 `start()` 方法时，它将启动新线程。

2. **实现 Runnable 接口**: 我们可以实现 `java.lang.Runnable` 接口，并将实现的对象传递给 `java.lang.Thread` 类的构造函数。调用 `start()` 时，它将启动新线程。

## 284. 在 Java 中如何能够在执行过程中停止线程？

我们可以使用 `volatile` 变量作为停止线程的指示。

我们可以创建一个指向当前线程的 `volatile` 引用。其他线程可以将此引用设置为 `null`，标记当前线程应该停止执行。

在以下示例中，`threadStopper` 是 `volatile` 引用，其他线程可以在 `stopThread()` 方法中将其设置为 `null`。

示例代码如下：



```java
public static class MyThread extends Thread {

    private volatile Thread threadStopper;

    public void start() {
        threadStopper = new Thread(this);
        threadStopper.start();
    }

    public void stopThread() {
        threadStopper = null;
    }

    public void run() {
        Thread currThread = Thread.currentThread();
        while (currThread == threadStopper) {
            try {
                Thread.sleep(100);
            } catch (InterruptedException e) {
            }
        }
    }
}
```

## 285. 在 Java 程序中如何访问当前线程？

通过调用 `java.lang.Thread` 类的静态方法 `currentThread()` 来访问当前线程。

示例代码如下：

```java
public class MyThread {
    public static void main(String[] args) {
        // 获取当前线程的 ID
        long id = Thread.currentThread().getId();

        // 获取当前线程名称
        String name = Thread.currentThread().getName();
    }
}
```

## 286. 多线程中的忙等待（Busy waiting）是指什么？

忙等待也称为忙循环（busy-looping）或自旋（spinning）。它是多线程技术的一种，进程会反复检查某个条件是否成立。

例如，一个进程可以不断检查是否有键盘输入。

通常情况下，忙等待被认为是一种浪费处理器时间的**反模式（Anti-pattern）**，应该避免。

忙等待的示例代码如下：

```java
Thread thread = new Thread(new Runnable() {
    @Override
    public void run() {
        long timeToStop = System.currentTimeMillis() + 1000;
        long currentTime = System.currentTimeMillis();

        // 忙等待
        while (timeToStop > currentTime) {
            currentTime = System.currentTimeMillis();
        }
    }
});
```

## 287. 在 Java 中如何防止忙等待？

在 Java 中防止忙等待有一种简单的方法。我们只需要让当前线程睡眠指定的时间。

可以通过调用 `java.lang.Thread` 类的 `sleep()` 方法来实现。我们可以将毫秒数作为参数传递给 `sleep()` 方法。

## 288. 在 Java 实时处理中可以使用 Thread.sleep() 方法吗？

Java 不保证 `Thread.sleep()` 会导致线程恰好睡眠 `N` 毫秒。有时线程睡眠的时间超过 `N` 毫秒。

在实时处理中，我们需要线程运行或睡眠的精确时间段。

因此，不建议在实时处理中使用 `Thread.sleep()` 方法。

## 289. 可以使用 Thread.sleep() 方法唤醒被置睡眠的线程吗？

我们可以使用 `java.lang.Thread` 类的 `interrupt()` 方法来中断处于睡眠状态的线程。示例代码如下：

```java
public class ThreadInterrupt implements Runnable {
    public void run() {
        try {
            Thread.sleep(Long.MAX_VALUE);
        } catch (InterruptedException e) {
            System.out.println("Interrupted!");
        }
    }

    public static void main(String[] args) throws InterruptedException {
        Thread myThread = new Thread(new ThreadInterrupt(), "myThread");
        myThread.start();
        System.out.println("Sleeping in main thread");
        Thread.sleep(10000);
        System.out.println("Interrupting myThread");
        myThread.interrupt();
    }
}
```

## 290. 检查线程是否被中断的两种方法是什么？

检查中断有两种方法：

1. 在 Java 中，线程可以调用 `interrupted()` 方法来检查自己是否被中断。
2. 另一个选项是调用 `Thread` 类的 `isInterrupted()` 方法。

## 291. 如何确保父线程等待子线程终止？

我们可以为此目的使用 `join()` 方法。调用 `join()` 方法时，当前线程会等待它所连接的子线程完成。

示例代码如下：

```java
Thread myThread = new Thread(new Runnable() {
    public void run() {
    }
});

myThread.start();
// 对 myThread 执行 join
myThread.join();
```

## 292. 在 Java 中如何处理 InterruptedException？

在 Java 中我们可以从 `sleep()` 或 `join()` 方法获取 `InterruptedException`。抛出 `InterruptedException` 是告知另一个线程中断了此线程的方法。

通常，中断的目的是请求当前线程停止当前执行并意外结束。

因此，通过捕获该异常并仅记录到控制台或日志文件并不是推荐的方法。

`Runnable` 接口的 `run()` 方法不允许抛出任何异常。因此我们无法重新抛出 `InterruptedException`。

因此，处理此异常正确的方法是 `run()` 方法应该自己检查并处理此异常，采取相应的行动。

## 293. Java同步方法获取的是哪个内锁？

当我们将一个方法标记为 `synchronized` 并调用该方法时，该方法将首先获取该方法所在对象的内锁。

一旦同步方法返回，它将释放锁。

如果同步方法抛出异常，内锁也将释放。

等同于同步方法的示例代码如下：

```java
public void myMethod() {
    synchronized (this) {
    }
}
```

## 294. 在 Java 中可以将构造函数标记为同步 吗？

不可以。我们不能将构造函数标记为 `synchronized`。

这会导致编译错误。

背后的原因是，在这种情况下，只有构造对象的线程才需要访问正在构造的对象。

## 295. 可以使用原始类型值作为内锁（intrinsic locks）吗？

不可以。Java 不允许将原始类型值用于内锁。

## 296. 内锁具有重入性属性吗？

是的。同一个线程可以多次访问同一个内锁。因此，内锁是可重入的。

如果不允许重入，那么获取锁的代码就必须避免再次获取它已经获取的锁。

## 297. 什么是原子操作？

原子操作是指相对于其他线程，在单个步骤中完成的操作。

原子操作要么完全执行完毕，要么完全不执行。

原子操作中不存在“中间状态”。

## 298. 在 Java 中，我们可以认为将 `i++` 语句视为原子操作吗？

不可以。`i++` 语句不是原子操作。它包含多个操作。

首先，JVM 从内存中加载 `i` 的当前值。然后对其进行递增。最后，将新值存回变量 `i` 中。

执行此操作的当前线程在上述三个步骤之间的任何一步都可能中断。因此，它不是原子操作。

## 299. Java 中有哪些原子操作？

Java 语言提供了一些基础的原子操作。这些操作可以用于确保并发线程始终看到相同的值。

其中一些原子操作包括：

1. 对引用变量和原始变量的读操作（`long` 和 `double` 除外）
2. 对引用变量和原始变量的写操作（`long` 和 `double` 除外）
3. 对所有声明为 `volatile` 的变量的读操作
4. 对所有声明为 `volatile` 的变量的写操作

## 300. 你能检查以下代码是线程安全的吗？

```java
public class SingletonDoubleCheck {
    private SingletonDoubleCheck instance = null;

    public SingletonDoubleCheck getInstance() {
        if (instance == null) {
            synchronized (SingletonDoubleCheck.class) {
                if (instance == null) {
                    instance = new SingletonDoubleCheck();
                }
            }
        }
        return instance;
    }
}
```

上述代码用于创建单例。但这段代码不是线程安全的。

我们在 `synchronized` 块中第二次检查了 `instance` 的值。但 JIT 编译器可能会重新排列字节码，导致在执行构造函数之前设置对 `SingletonDoubleCheck instance` 的引用。

由于这种原因，`getInstance()` 方法可能会返回一个尚未被正确初始化的对象。

我们可以对 `instance` 使用 `volatile` 关键字来使这段代码变为线程安全。

任何被标记为 `volatile` 的变量只有在对象构造函数完成后，对其他线程可见。

## 301. 程序中出现死锁（Deadlock）的最小条件是什么？

要发生死锁，必须满足以下最小条件：

1. **互斥性（Mutual exclusion）**：必须有一个资源在任何时刻只能由一个线程访问。
2. **资源持有（Resource holding）**：一个线程锁住一个资源并持有它，同时尝试获取另一个互斥资源的的锁。
3. **非抢夺（No preemption）**：没有抢占机制允许在特定时间后释放线程所持有的资源。
4. **循环等待（Circular wait）**：可能会出现一种场景，两个或多个线程各锁定一个资源，并等待对方的资源释放。这导致线程之间对同一组资源产生循环等待。

## 302. 我们如何防止死锁？

为了防止死锁发生，至少必须移除死锁的一个条件：

- **互斥性**：我们可以使用乐观锁（optimistic locking）来防止资源之间的互斥。
- **资源持有**：如果线程未能成功获取所需资源的所有互斥锁，则必须释放它持有的所有互斥锁。
- **非抢夺**：我们可以为互斥锁设置超时时间，以便在给定时间后释放。
- **循环等待**：我们可以检查并确保，当所有线程按相同的顺序获取所有互斥锁时，不会发生循环等待。

## 303. 如何检测死锁状态？

我们可以使用 `ThreadMXBean.findDeadlockedThreads()` 方法来检测 Java 程序中的死锁。这个 bean 随 JDK 提供：

示例代码如下：

```java
ThreadMXBean bean = ManagementFactory.getThreadMXBean();
long[] threadIds = bean.findDeadlockedThreads(); // 无死锁则返回 null
if (threadIds != null) {
    ThreadInfo[] infos = bean.getThreadInfo(threadIds);

    for (ThreadInfo info : infos) {
        StackTraceElement[] stack = info.getStackTrace();
        // 记录或存储堆栈跟踪信息。
    }
}
```

## 304. 什么是活锁（Livelock）？

活锁是指两个或多个线程通过对另一个线程引起的操作做出响应，从而导致相互阻塞的场景。

在死锁情况下，两个或多个线程在一个特定的状态下等待。

在活锁场景中，两个或多个线程改变其状态的方式，阻止了它们正常工作的进展。

例如：考虑两个线程尝试获取两个锁的场景。当它们无法获取第二个锁时，它们会释放已经获取的锁。

在活锁状态下，两个线程都持有不同的锁。只有一个线程会成功，第二个线程可能成功获取锁。因此它们会释放并从头重新尝试。这种情况会不断重复。

## 305. 什么是线程饥饿（Thread starvation）？

在基于优先级的调度中，低优先级的线程获得比高优先级线程更少的时间。

如果低优先级线程执行了耗时计算，可能会导致该线程无法获得足够的时间完成工作。在这种情况下，低优先级线程就会发生饥饿。它会远离高优先级线程。

## 306. `synchronized` 块如何导致 Java 中的线程饥饿？

同步并没有定义哪个线程将进入 `synchronized` 块。可能会出现如果有许多线程等待进入 `synchronized` 块，某些线程必须等待更长时间。

因此，这些低优先级的线程将无法获得足够的时间。

## 307. 什么是竞态条件（Race condition）？

竞态条件是一种异常情况，其中程序尝试同时执行两个或多个操作，由于程序的逻辑，这些操作必须按照正确的顺序执行才能正确运行程序。

由于这是一种不良的行为，它被视为代码中的 Bug。

竞态条件通常发生在“检查再执行”（check then act）场景中。两个线程对相同的值进行检查和执行。但其中一个线程在检查和执行之间执行了操作。通过此示例理解竞态条件。

```java
if (x == 3) // 检查
{
    y = x * 5; // 执行

    // 如果另一个线程在 "if (x==3)"
    // 和 "y = x * 5" 之间改变了 x
    // 那么 y 将不等于 15。
}
```

## 308. 多线程中的什么是公平锁（Fair lock）？

在 Java 中，有一个类 `ReentrantLock` 用于实现公平锁。该类接受一个可选参数 `fairness`。当 `fairness` 设置为 `true` 时，`ReentrantLock` 将授予等待最长的线程。

公平锁最著名的用途是避免线程饥饿。因为在竞争情况下等待最长的线程总是获得优先，因此没有线程会饥饿。

公平锁的缺点是程序的吞吐量较低。由于低优先级或慢速线程多次获取锁，会导致程序执行变慢。

公平锁的唯一例外是 `ReentrantLock` 的 `tryLock()` 方法。该方法不遵守 `fairness` 参数的值。

## 309. Object 类的哪两个方法可以实现生产者-消费者场景？

在生产者-消费者场景中，一个线程是生产者，另一个线程是消费者。

为了让这个场景开始工作，消费者必须知道生产者何时生产了数据。在 `Object` 类中，有一个 `wait()` 方法。消费者调用 `wait` 方法来等待生产者。生产者使用 `Object` 类的 `notify()` 方法来通知消费者它已经生产了数据。

通过这种方式，由于使用了 `wait()` 和 `notify()` 方法，生产和消费操作之间的处理器时间被释放了。

## 310. JVM 如何确定在 `notify()` 时唤醒哪个线程？

如果有多个线程在等待同一个对象的监视器（monitor），JVM 会唤醒其中一个。根据 Java 规范，对该线程的选择是任意的，并且取决于具体的实现。因此，没有保证规则规定某个特定线程会被 JVM 的 `notify()` 方法调用唤醒。

## 311. 检查以下代码在从 Queue 获取整数值时是线程安全的吗？



```java
public class QueueCheck {
    Queue queue;

    public Integer getNextInt() {
        Integer retVal = null;
        synchronized (queue) {
            try {
                while (queue.isEmpty()) {
                    queue.wait();
                }
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
        synchronized (queue) {
            retVal = queue.poll();
            if (retVal == null) {
                System.err.println("retVal is null");
                throw new IllegalStateException();
            }
        }
        return retVal;
    }
}
```

在上述代码中，`Queue` 被用作对象监视器来处理并发问题但在多线程场景下，它的行为可能不正确。

上述代码中有两个独立的同步块。如果两个线程被另一个线程同时唤醒，这两个线程将一个接一个地进入第二个同步块。

在两个线程中只有一个会从队列获取新值并使其为空。第二个线程将在空队列上执行 `poll`，并将无法获得任何非空返回值。

# 312. 我们如何检查一个线程是否对给定对象拥有监视器锁？

在 Java 中，`Thread` 类有一个静态方法 `holdsLock(Object objToCheck)`，用于检查线程是否拥有 `objToLock` 对象的锁。

如果当前线程持有作为该方法参数的 `objToLock` 对象的锁，该方法将返回 `true`。

# 313. Thread 类中 `yield()` 方法的作用是什么？

`Thread` 类的 `yield()` 方法用于向调度器提供提示，表示当前线程想要释放处理器。

调度器既可以使用此提示，也可以直接忽略此提示。由于调度器的行为是不保证的，可能会出现当前线程再次获得处理器的情况。

它可以用于调试或测试目的。但该方法很少有具体的用途。

# 314. 将对象从一个线程传递到另一个线程时，需要考虑的重要点是什么？

这是一个多线程场景。在多线程场景中，最重要的一点是检查两个线程是否可以同时更新同一个对象。

如果两个线程可能同时更新同一个对象，可能会导致竞态条件（race condition）等问题。

因此，建议将对象设为不可变的（Immutable）。这将有助于避免该对象上的任何并发问题。

# 315. 创建不可变对象（Immutable Objects）的规则是什么？

根据 Java 规范，创建不可变对象的规则如下：

- 不要提供修改字段或由字段引用的对象的“setter”方法。
- 将所有字段声明为 `final` 和 `private`。
- 不要允许子类重写方法。实现此点的最简单方法是将类声明为 `final`。更复杂的方法是将构造函数设为 `private` 并在工厂方法中构造实例。
- 如果实例字段包含对可变对象的引用，不要允许这些对象被更改。
- 不要提供修改可变对象的方法。
- 不要共享对可变对象的引用。永远不要共享传递给构造函数的外部可变对象的引用；如有必要，创建副本并存储对副本的引用。同样，在必要时创建内部可变对象的副本，以避免在方法中返回原始对象。

# 316. ThreadLocal 类的作用是什么？

`ThreadLocal` 类提供了线程本地变量。每个线程只访问它自己的局部变量。它拥有该变量的独立副本。

通过使用 `ThreadLocal`，如果线程 X 存储了一个值为 `x` 的变量，而另一个线程 Y 存储了相同变量但值为 `y` 的变量，那么 X 从它的 `ThreadLocal` 实例中获取 `x`，而 Y 从它的 `ThreadLocal` 实例中获取 `y`。

通常，`ThreadLocal` 实例是与线程状态相关的私有静态字段。

# 317. 适用于 ThreadLocal 类的场景有哪些？

我们可以使用 `ThreadLocal` 类的实例在应用程序内部传输信息。

一个用例是在 `ThreadLocal` 实例内部传输安全或登录信息，以便每个方法都能访问它。

另一个用例是跨应用程序传输事务信息，而无需使用方法与方法之间的通信。

# 318. 你将如何通过多线程提高应用程序的性能？

在具有多个 CPU 的环境中，我们可以在多个 CPU 上并行化计算任务。这导致了更大规模任务的并行处理。一个例子是，如果我们有 1000 条数据需要计算和。如果每个文件需要 5 分钟，那么 1000 个文件将需要 5000 分钟。

但通过使用多线程，我们可以通过 10 个线程并行处理这些文件。这样每个线程仅需要 500 分钟。

# 319. 软件的可扩展性（Scalability）是什么？

扩展性是指程序处理增长的工作量的能力，或其适应增长的潜力。

如果一个程序能够处理大量输入数据、大量用户或大量节点，则该程序被认为是可扩展的。

当我们说一个程序不可扩展时，意味着该程序在任务规模增大时会失败。

# 320. 你如何通过使用多个处理器计算应用程序的最大加速比？

阿姆达法则（Amdahl's law）给出了固定工作负载下任务执行延迟的理论加速比。

它提供了为应用程序提供多个处理器可以实现的理论最大加速比公式。

如果 S 是理论加速比，则公式为：

$S(n) = 1 / (B + (1-B)/n)$

其中 n 是处理器的数量

B 是程序无法并行执行的比例。

当 n 趋于无穷大时，项 $(1-B)/n$ 趋于 0。因此，在这种特殊情况下，公式可以简化为 $1/B$。

通常，理论最大加速比与串行执行的比例成反比。这意味着该比例越低，可以实现的理论加速比就越大。

# 321. 多线程中的锁竞争（Lock contention）是什么？

锁竞争是指一个线程等待被另一个线程持有的锁/对象的情况。在另一个线程释放该对象的锁之前，等待线程无法使用该对象。

也被称为线程竞争（Thread contention）。

理想情况下，锁减少了线程竞争。如果没有锁，多个线程可以操作同一个对象并导致异常行为。如果锁实现正确，它可以减少多个线程之间的竞争。

## 322. 减少锁竞争（Lock contention）的技术有哪些？

以下是减少锁竞争的主要技术：

1. 缩小锁的范围。
2. 减少对象池的使用。
3. 减少特定锁被获取的次数。
4. 避免在不必要的地方进行同步。
5. 实现硬件支持的乐观锁来代替同步。

## 323. 在以下代码中，可以使用什么技术来减少锁竞争？

```
synchronized (map) {
    Random r = new Random();
    Integer value = Integer.valueOf(42);
    String key = r.nextString(5);
    map.put(key, value);
}
```

该代码使用了 `Random()` 来获取随机字符串，并使用了 `Integer` 将 `42` 转换为对象。由于这些行代码是特定于该线程的，可以将它们移动到同步块之外。

```
Random r = new Random();
Integer value = Integer.valueOf(42);
String key = r.nextString(5);

synchronized (map) {
    map.put(key, value);
}
```

## 324. 什么是锁拆分（Lock splitting）技术？

锁拆分是一种在多线程中减少锁竞争的技术。它适用于以下场景：使用一个锁来同步对同一个应用程序不同层面的访问。

有时我们用一个锁来保护整个数组。可能会有多个线程尝试获取同一个数组的锁。数组上的这个单锁可能会导致线程之间的锁竞争。为了解决这个问题，我们可以为数组的每个元素分配一个锁。或者，我们可以使用模函数将不同的锁分配给一小组数组元素。通过这种方式，我们可以减少锁竞争的机会。这就是锁拆分技术。

## 325. ReadWriteLock 类使用了什么技术来减少锁竞争？

`ReadWriteLock` 使用了两个锁。一个锁用于只读操作，另一个锁用于写操作。

它的实现基于这样一个前提：当并发线程想要读取一个值时，只要此时没有其他线程正在尝试写入，它们就不需要锁。

在这一实现中，多个线程可以获取读锁。并且该实现保证，一旦写锁释放，所有读操作将立即看到最新的更新值。

## 326. 什么是锁分段（Lock striping）？

在锁拆分中，我们为应用程序的不同部分使用不同的锁。在锁分段中，我们使用多个锁来保护同一个数据结构的不同部分。

Java 的 `ConcurrentHashMap` 类内部使用不同的桶（buckets）来存储其值。每个桶根据键的值进行选择。`ConcurrentHashMap` 使用不同的锁来守护不同的桶。当一个线程尝试访问某个哈希桶时，它可以获取该桶的锁。而另一个线程可以同时获取另一个桶的锁并访问它。在 `HashMap` 的同步版本中，整个 map 只有一个锁。

锁分段技术比对整个数据结构进行同步具有更好的性能。

## 327. 什么是 CAS 操作？

CAS 也称为比较并交换（Compare-And-Swap）操作。

在 CAS 操作中，处理器提供了一条单独的指令，只有当提供的值等于当前值时，它才能更新寄存器的值。

CAS 操作可以作为同步的替代方案。

假设线程 T1 可以通过向 CAS 操作传递其当前值和要更新的新值来更新一个值。如果另一个线程 T2 更新了前一个线程的当前值，那么前一个线程 T1 的当前值就不等于 T2 的当前值。因此，更新操作失败。

在这种情况下，线程 T1 将再次读取当前值并尝试更新它。

这是乐观锁的一个示例。

## 328. 哪些 Java 类使用了 CAS 操作？

诸如 `AtomicInteger` 或 `AtomicBoolean` 等 Java 类内部使用 CAS 操作来支持多线程。

这些类位于 `java.util.concurrent.atomic` 包中。

## 329. 在多线程应用中，通过对象池总是能提高性能吗？

通过在应用程序中使用对象池，我们限制了某个类创建的对象数量。在单线程操作中，可以通过重用从池中已经创建的对象来提高性能。

在多线程应用中，对象池必须为多个线程提供同步访问。由于同步，一次只能有一个线程访问池。此外，由于池上的锁竞争会产生额外成本。这些额外成本可能会超过重用池中对象节省的成本。

因此，使用对象池并不总是能提高多线程应用中的性能。

## 330. 单线程应用中用于性能改进的技术如何降低多线程应用中的性能？

在单线程应用中，我们可以使用对象池进行性能优化。而在多线程环境中，使用对象池可能不是一个好主意。同步开销的增加和锁竞争会降低多线程应用中使用对象池所获得的性能。

另一个例子是实现中 `List` 保留了一个独立的变量来保存元素数量。这种技术在单线程应用中很有用，`size()` 方法可以直接返回该变量的值，而无需计算所有元素。

但在多线程应用中，这个独立的变量会降低性能。由于多个线程可以向列表中插入元素，该变量必须由锁控制。这种额外成本可能会超过使用它带来的收益。

## 331. Executor 和 ExecutorService 接口之间是什么关系？

`Executor` 接口只有一个 `execute(Runnable)` 方法。该接口的实现类需要在未来的某个时刻执行传递的 `Runnable` 实例。

`ExecutorService` 继承自 `Executor` 接口。它提供了如 `invokeAny()`、`invokeAll()`、`shutdown()` 等额外方法。这些方法提供了关闭线程以便后续请求被拒绝的能力。它提供了调用 `Callable` 任务的能力。

## 332. 对队列已满的 ExecutorService 实例调用 `submit()` 方法会发生什么？

当 `ExecutorService` 的队列已满且通过 `submit()` 提交新任务时，该实现将抛出 `RejectedExecutionException`。

## 333. 什么是 ScheduledExecutorService？

`ScheduledExecutorService` 继承自 `Executor`。它提供了多种 `schedule()` 方法，用于在指定的时刻提交新任务。

其中 `schedule()` 方法提供了在给定延迟后执行单次任务的能力。

另一个 `schedule()` 版本提供了在给定延迟后执行 `ScheduledFuture` 的能力。

此外，还有 `scheduleAtFixedRate()` 和 `scheduleWithFixedDelay()` 方法，可以定期执行操作。

## 334. 如何在 Java 中创建线程池？

在 Java 中，`Executors` 框架提供了 `newFixedThreadPool(int nThreads)` 方法，可以使用它创建一个具有固定数量线程的线程池。

示例代码如下：

```java
public static void main(String[] args) throws InterruptedException,
    ExecutionException
{
    ExecutorService myService = Executors.newFixedThreadPool(5);
    Future<Integer>[] futureList = new Future[5];
    for (int i = 0; i < futureList.length; i++) {
        futureList[i] = myService.submit(new MyCallable());
    }
    for (int i = 0; i < futureList.length; i++) {
        Integer retVal = futureList[i].get();
        println(retVal);
    }
    myService.shutdown();
}
```

## 335. Runnable 和 Callable 接口之间的主要区别是什么？

`Runnable` 接口定义了 `run()` 方法，该方法不返回返回值。

`Callable` 接口允许 `call()` 方法向调用者返回一个值。`Callable` 接口在发生错误时还可以抛出异常。此外，`Callable` 是 Java 自 1.5 版本起引入的新特性。

## 336. Java 中 Future 接口的用途是什么？

我们可以使用 `Future` 接口来表示异步计算的结果。

这些是那些结果无法立即获取的操作。

因此，`Future` 接口提供了 `isDone()` 方法来检查异步计算是否完成。

我们还可以通过调用 `isCancelled()` 方法来检查任务是否被取消。

`Future` 还提供了 `cancel()` 方法来尝试取消任务。

## 337. HashMap 和 Hashtable 在并发性方面有什么区别？

在 `Hashtable` 类中，所有方法都是同步的（synchronized）。

在 `HashMap` 实现中，并不是所有方法都是同步的。

因此，`Hashtable` 是线程安全的集合。`HashMap` 不是线程安全的集合。

在多线程环境中，不建议使用普通的 `HashMap`。我们可以在多线程应用中使用 `ConcurrentHashMap` 类。

## 338. 如何创建 List 或 Map 集合的同步实例？

在 Java 中，`Collections` 类提供了对任何集合进行同步的方法。

它还提供了 `synchronizedList(List)` 和 `synchronizedMap(Map)` 方法，可以用它们将 `List` 或 `Map` 转换为同步实例。

## 339. Java 中的 Semaphore（信号量）是什么？

Java 中的 `Semaphore` 类用于实现计数信号量。它被用于限制访问物理或逻辑资源的线程数量。

`Semaphore` 维护一组许可（permits），竞争的线程需要获取这些许可。

我们还可以用它来控制有多少线程可以并发访问程序的关键区域或资源。

`Semaphore` 构造函数的第一个参数是可用许可的总数。每调用一次 `acquire()` 方法都会尝试获取可用许可中的一个。

`acquire()` 方法用于从信号量中获取一个许可。如果我们向 `acquire()` 方法传递所需的许可数量，那么它将阻塞线程，直到有足够数量的许可。

一旦线程完成了工作，我们可以使用 `release()` 方法来释放许可。

## 340. Java 中的 CountDownLatch 是什么？

`CountDownLatch` 类有助于在 Java 中实现同步。它被用于实现此类场景：一个或多个线程必须等待其他线程达到相同的状态，以便所有线程都可以开始。

内部有一个同步计数器，计数器会不断递减直到达到零。一旦达到零，意味着所有等待的线程现在可以继续执行。

它是一个多功能的工具，也可以用于其他的同步场景。它还可以作为开启/关闭的锁或门使用。所有调用 `await()` 方法的线程都会在门处等待，直到由调用 `countDown()` 方法的线程将其打开。

## 341. CountDownLatch 和 CyclicBarrier 之间有什么区别？

`CyclicBarrier` 接受一个可选的 `Runnable` 任务，该任务会在公共屏障条件达成时运行一次。

`CountDownLatch` 用于简单的场景，即只需要简单的启动和停止控制。而 `CyclicBarrier` 适用于需要更多协调的复杂场景，例如 MapReduce 算法实现。



当值达到零时，`CyclicBarrier` 会将内部值重置为初始值。`CyclicBarrier` 可用于线程需要多次相互等待的场景。

## 342. 哪些场景适合使用 Fork/Join 框架？

`ForkJoinPool` 类是 Fork/Join 框架的核心。它是一个可以执行 `ForkJoinTask` 实例的线程池。

`ForkJoinTask` 类提供了 `fork()` 和 `join()` 方法。`fork()` 方法用于启动任务的异步执行。`join()` 方法用于等待计算结果。

因此，可以使用 Fork/Join 框架轻松地实现分治算法。

## 343. RecursiveTask 和 RecursiveAction 类之间有什么区别？

`RecursiveAction` 类拥有 `compute()` 方法，该方法不需要返回值。

当操作必须直接在数据结构上执行时，可以使用 `RecursiveAction`。它不需要返回任何计算后的值。

在 `RecursiveTask` 类中，`compute()` 方法总是返回一个值。

`RecursiveTask` 和 `RecursiveAction` 类都用于 `ForkJoinTask` 的实现。

## 344. 在 Java 8 中，可以使用线程池处理流（stream）操作吗？

在 Java 8 中，`Collections` 提供了 `parallelStream()` 方法来创建一个可以由线程池处理的流。

我们还可以在给定的流上调用中间方法 `parallel()`，将其转换为并行任务的顺序流流。

## 345. Java 8 中使用并行流（parallel stream）的场景有哪些？

Java 8 中的并行流与顺序流相比，其开销（overhead）要高得多。

协调线程需要大量的时间。

我们可以在以下场景中使用并行流：

- 当有大量项目需要处理，且每个项目的处理都需要耗时，并且是可以并行化的时。
- 当顺序处理存在性能问题时。
- 当当前实现尚未运行在多线程环境中。如果已经存在多线程环境，添加并行流可能会降低性能。

## 346. 栈（Stack）和堆（Heap）在多线程中是如何工作的？

栈和堆是内存区域。每个线程都有自己的栈。堆（Heap）由所有线程共享。对象被创建在堆内部。栈用于存储局部变量和方法参数。

我们使用 `volatile` 关键字来标记变量为 volatile，这样线程始终从主内存中读取该值。

## 347. 如何在 Java 中获取线程转储（Thread dump）？

获取线程转储的步骤取决于操作系统。在 Windows 上，可以同时按下 `Ctrl + Break` 来获取线程转储。在 Linux 上，可以执行 `kill -3` 命令获取线程转储。另一种获取线程转储的方法是使用 `jstack` 工具。将 Java 进程的 PID 传递给该工具。

## 348. 哪个参数可以控制线程栈的大小？

我们使用 `-Xss` 参数来控制线程栈的大小。如果设置为 1 MB，每个线程将获得 1MB 的栈空间。

## 349. 有两个线程 T1 和 T2？如何确保这些线程按 T1, T2 的顺序运行？

在 Java 中有多种方法顺序执行线程。最简单的方法之一是 `Thread` 类的 `join()` 方法。我们可以在另一个线程完成后调用 `join()` 方法。我们从最后一个执行的线程开始，让该线程等待下一个线程。在这种情况下，我们先启动线程 T2，然后调用 `T1.join()`，以便线程 T2 等待 T1 完成执行。一旦 T1 完成执行，T2 线程开始执行。

### 351. Java 8 引入的新特性有哪些主要优势？

Java 8 特性的主要优势是：

1. 通过 Lambda 和 Streams 支持函数式编程
2. 通过 Streams 便于海量数据处理
3. 通过反射获取参数名提高易用性
4. 通过增强 Collection API 实现可重用代码
5. 使用 Optional 进行智能异常处理
6. 使用新参数控制 JVM
7. 使用 Base64 增强加密支持
8. 支持 Nashorn JavaScript 引擎实现更快的执行

### 352. 什么是 Java 8 中的 Lambda 表达式？

Lambda 表达式是一个匿名函数。它像是一个不需要任何访问修饰符、名称或返回值声明的方法。它接受一组输入参数并返回结果。

Lambda 表达式可以作为参数传递到方法中。因此，我们可以将 Lambda 表达式中的代码视为数据。这段代码可以传递给其他对象和方法。

### 353. Java 中 Lambda 表达式的三个主要部分是什么？

Lambda 表达式的三个主要部分是：

1. 参数列表：Lambda 表达式可以有零或多个参数。参数列表对于 Lambda 来说是可选的。
2. Lambda 箭头运算符：`->` 被称为 Lambda 箭头运算符。它分隔了参数列表和 Lambda 实体。
3. Lambda 表达式体：我们想要执行的代码段写在 Lambda 表达式体中。

例如在下面的示例中：

```java
Arrays.asList("a", "b", "d").forEach(e -> System.out.println(e));
```

参数列表 = `e`

箭头 = `->`

体 = `System.out.println(e)`

### 354. Lambda 表达式的数据类型是什么？

Lambda 表达式实现了将代码作为数据传递。

Lambda 表达式的数据类型是函数式接口（Functional interface）。

在大多数情况下，它是 `java.lang.Runnable` 接口。

### 355. 下面 lambda 表达式的含义是什么？

```java
(e -> System.out.println(e));
```

这个 Lambda 表达式接受一个参数 `e` 并通过 `System.out` 打印它。

### 356. 为什么 Oracle 发布了像 Java 8 这样的新版本 Java？

Java 8 的核心主题是支持函数式编程。随着数据库规模的增大和多核 CPU 服务器的增长，Java 需要支持此类大规模系统。

通过 Java 8 的新特性，可以创建函数式程序与大数据系统进行高效交互。对 Streams 支持在这方面非常有帮助。

Lambda 表达式对于云计算非常有用，因为我们可以将代码作为数据传递，并在多个服务器上运行相同的代码。

Optional 是从 Google Guava 库中借用的最佳实践，用于处理异常情况。这通过对边缘情况的支持，使程序变得更加健壮。

### 357. Lambda 表达式的优势是什么？

我们可以将 Lambda 表达式作为对象传递给方法。这减少了传递匿名类带来的开销。

我们还可以使用 Lambda 表达式将方法作为参数传递给另一个方法。

### 358. 什么是 Java 8 中的函数式接口（Functional interface）？

Java 中的函数式接口是一个恰有一个抽象方法的接口。

它可以拥有带有具体实现的默认方法（default methods）。默认方法不是抽象的。

在 Java 8 中，`java.lang.Runnable` 和 `java.util.concurrent.Callable` 是两个非常流行的函数式接口。

### 359. 什么是 Java 8 中的单抽象方法（SAM）接口？

函数式接口也称为单抽象方法接口（Single Abstract Method Interface），因为它恰好有一个抽象方法。

### 360. 如何在 Java 8 中定义函数式接口？

要在 Java 8 中定义函数式接口，我们可以创建一个恰好有一个抽象方法的接口。

另一种方法是使用 `@FunctionalInterface` 注解标记接口。即使使用了该注解，我们也必须遵守“恰好一个抽象方法”的规则。

该规则的唯一例外是，如果重写了 `java.lang.Object` 类的方法并将其作为抽象方法，那么它不计入抽象方法。

### 361. 为什么在 Java 中需要函数式接口？

函数式接口主要用于 Lambda 表达式、方法引用和构造器引用。

在函数式编程中，代码可以被当作数据。为了这个目的，引入了 Lambda 表达式。它们可以将一段代码传递给另一个方法或对象。

函数式接口作为 Lambda 表达式的数据类型。由于函数式接口只包含一个抽象方法，该方法的实现就变成了作为参数传递给另一个方法的代码。

### 362. 在 Java 8 中定义函数式接口时，强制使用 @FunctionalInterface 注解吗？

不，强制使用 `@FunctionalInterface` 注解标记函数式接口。

Java 并没有规定这一条。

但是，如果我们用 `@FunctionalInterface` 注解标记接口，那么当我们在接口内部定义了多个抽象方法时，Java 编译器会报错。

### 363. Java 8 中 Collection 和 Stream API 之间有什么区别？

Java 8 中 Collection 和 Stream API 之间的主要区别是：

1. 版本：Collection API 自 Java 1 开始一直使用。Stream API 是 Java 8 新增的。
2. 用途：Collection API 用于存储数据。Stream API 用于数据计算。
3. 有限性：通过 Collection API 我们可以存储有限数量的元素。Stream API 可以处理无限数量的元素。
4. 饥饿与懒惰：Collection API 以饥饿（eager）方式构建对象。Stream API 以延迟（lazy）方式创建对象。
5. 多次消费：大多数 Collection API 支持多次迭代。Stream API 只能消费一次元素。

### 364. Java 8 中 Stream API 的主要用途是什么？

Stream API 的主要用途是：

1. 它帮助以声明式的方式使用数据，无需运行完整的迭代。
2. 它在不担心多线程代码的情况下充分利用多核架构。
3. 我们可以使用 Stream 创建数据操作流水线，流水线可以顺序或并行运行。
4. 它提供了对分组（group by）、排序（order by）等操作的支持。
5. 它支持以函数风格编写代码。
6. 它提供了数据的并行处理。

### 365. Java 8 Streams 中中间操作（Intermediate）和终端操作（Terminal）之间有什么区别？

中间操作和终端操作之间的主要区别如下：

- 求值：在将其与 Stream 的终端操作链之前，中间操作不会被执行。终端操作可以独立求值。
- 输出：中间操作的输出是另一个 Stream。终端操作的输出不是 Stream。
- 懒惰：中间操作以延迟方式求值。终端操作以饥饿方式求值。
- 链式：我们可以在 Stream 中链多个中间操作。终端操作不能多次链。
- 多个：在 Stream 操作中可以有多个中间操作。在 Stream 处理语句中只能有一个终端操作。

### 366. 什么是 Java 8 中的 Spliterator？

Spliterator 是一种特殊的迭代器（Iterator），用于遍历和分区 Java 源中的元素。源可以是集合、IO 通道或生成器函数。

Spliterator 可以单独遍历元素，也可以批量顺序遍历元素。

### 367. Java 8 中 Iterator 和 Spliterator 之间有什么区别？

Iterator 和 Spliterator 之间的主要区别如下：

1. Spliterator 可以与 Java 8 中的 Streams 使用。而 Iterator 仅用于 Collection。
2. Spliterator 使用内部迭代（Internal Iteration）来遍历 Streams。Iterator 使用外部迭代（External Iteration）来遍历 Collections。
3. Spliterator 可以以并行和顺序方式遍历 Streams。Iterator 只能以顺序方式遍历。
4. Spliterator 可以单独遍历元素，也可以批量遍历。Iterator 仅能单独遍历元素。

## 368. 什么是 Java 8 中的类型推断？

Java 编译器可以查看每个方法的调用及其声明，以确定调用时所需的类型参数是什么。

通过**类型推断（Type Inference）**，Java 可以确定参数的类型以及返回结果的类型。

类型推断算法还会尝试寻找能够适用于所有类型参数的最特定类型。

## 369. Java 7 支持类型推断吗？

支持，Java 7 支持类型推断。在 Java 8 中，Oracle 增强了类型推断的概念。现在它可以被用于定义 Lambda 表达式、函数和方法引用。

## 370. Java 8 中的内部迭代（Internal Iteration）是如何运作的？

在迭代器（Iterator）中，根本问题是哪一方控制迭代。是迭代器，还是运行迭代器的集合（Collection）。

当集合控制迭代器时，它被称为外部迭代（External Iteration）。当迭代器控制迭代时，它被称为内部迭代（Internal Iteration）。

在内部迭代的情况下，客户端将操作交由迭代器，由迭代器对所有元素统一应用该操作。

内部迭代更容易实现，因为迭代器不需要存储集合的状态。

## 371. 内部迭代器和外部迭代器的主要区别是什么？

内部迭代器和外部迭代器的主要区别如下：

1. 内部迭代器控制迭代本身。在外部迭代器中，集合控制迭代。
2. 内部迭代器可以逐个迭代元素也可以批量迭代（例如 `forEach`）。外部迭代器是逐个迭代元素。
3. 内部迭代器并不一定只能按顺序迭代元素。外部迭代器总是按顺序迭代。
4. 内部迭代器支持声明式编程风格，与函数式编程完美契合。外部迭代器遵循命令式 OOP 编程。
5. 有些人认为内部迭代器的代码比外部迭代器更具读性。

## 372. Java 8 中内部迭代器优于外部迭代器的主要优势是什么？

内部迭代器的一些优势是：

1. 内部迭代器基于函数式编程，因此它可以在声明式代码上工作。
2. 内部迭代器不需要顺序遍历元素。
3. 内部迭代器的代码更可读、更简洁。
4. 内部迭代器支持并发和并行处理。

## 373. 我们应该在哪些应用中使用内部迭代？

在需要高性能、并行处理、快速迭代和支持批量操作的应用中，我们需要内部迭代器。

此外，在内部迭代应用中，我们对迭代没有太多的控制权。并行处理等其他特性变得更加重要。

## 374. 内部迭代优于外部迭代的主要缺点是什么？

内部迭代相比外部迭代有许多优势。但它有一个巨大的缺点。由于 Java API 负责内部迭代器中的迭代，开发者对迭代没有任何控制权。

## 375. 可以在 Java 接口中提供方法的实现实现吗？

在 Java 8 之前，不允许在接口中提供方法的实现。

Java 8 引入了在接口中提供方法实现的灵活性。这有两种方案：

1. 默认方法（Default Method）：我们可以提供方法的默认实现。
2. 静态方法（Static Method）：我们可以在接口中创建静态方法并提供实现。

## 376. 接口中的默认方法（Default Method）是什么？

在 Java 8 中，我们可以在接口中提供方法的实现，并用 `default` 关键字标记该方法。

通过这种方式，该方法的实现变成了任何实现接口的类的默认行为。

## 377. 为什么 Java 8 接口中需要默认方法？

接口中的默认方法为 Java 8 提供了向后兼容特性。

假设有一个接口 `Car`，它被 BMW、Chevrolet 和 Toyota 类实现。现在 `Car` 需要增加飞行能力。这需要修改 `Car` 接口。某些不具备飞行能力的汽车类可能会失败。因此，在 `Car` 接口中添加飞行方法的默认实现，使得没有飞行能力的汽车可以继续实现原始 `Car` 接口。

## 378. Java 8 接口中静态方法（Static method）的目的是什么？

接口中的静态方法是工具或辅助方法。它不是对象级别的实例方法。接口中静态方法的一些用途包括：

1. 单类：不需要创建一个单独的 Utils 类来存储工具或辅助方法。我们可以将这些方法保留在同一个接口中。
2. 封装：通过静态方法，类的完整行为被封装在同一个类中。不需要维护多个类。
3. 扩展：更容易扩展类/API。如果我们扩展了集合 `ArrayList`，我们就得到了所有方法。我们不需要再扩展 `Collections` 类。

## 379. Java 日期时间 API 的核心思想是什么？

Java 8 日期时间 API 有三个核心思想：

1. 不变值类（Immutable-value classes）：新 API 通过确保所有核心类都是不可变的且代表定义的值，避免了线程安全和并发问题。
2. 领域驱动设计（Domain-driven design）：新 API 基于精确的领域建模，用类表示日期的不同用例。
3. 对领域驱动设计的强调提供了清晰性和可理解性。
4. 年代分离（Separation of chronologies）：新 API 允许人们处理不同的系统。它支持日本或泰国等不遵循 ISO-8601 的用户的需求。

## 380. Java 8 新日期时间 API 相比旧 API 有哪些优势？

Java 8 新日期时间 API 相比旧 API 的优势是：

- 并发：现有的日期时间类（如 `java.util.Date` 和 `SimpleDateFormat`）不是线程安全的。这在并发应用程序中工作效果不好。在新日期时间 API 中，开发者在编写日期代码时不需要处理并发问题。
- 设计更好：Java 8 之前的日期时间类设计糟糕。例如，`java.util.Date` 的年份从 1900 开始，月份从 0 开始，日期从 0 开始。这并不直观。Java 8 日时间 API 处理得很好。
- 无需第三方库：随着 Joda Time 等第三方日期时间库的流行，Java 使其原生日期时间 API 具有竞争性。现在我们可以使用 Java API 而不是第三方库。



## 381. 旧日期时间 API 和 Java 8 日期时间 API 的主要区别是什么？

旧日期时间 API 和 Java 8 日期时间 API 的主要区别是：

1. 旧 API 不是线程安全的。Java 8 API 是线程安全的。
2. 旧 API 有许多可变对象。Java 8 API 基于不可变对象。
3. 旧 API 的性能不好。Java 8 日期时间 API 提供了更好的性能。
4. 旧 API 的可读性和维护性较差。Java 8 API 设计得非常好且更具可读性。
5. 旧 API 的月份值为 0 到 11。新 API 的月份为 1 到 12。

## 382. 在 Java 8 中我们如何获取两个日期或时间之间的持续时间？

在 Java 8 中，我们有一个新的类 `Duration`，它提供了计算两个日期之间持续时间的工具。

我们可以调用静态方法 `Duration.between(date1, date2)` 来获取 `date1` 和 `date2` 之间的小时、分钟、天等时间间隔。

## 383. Java 8 引入了哪些新方法用于在多核机器上处理数组？

Java 8 增强了 `Arrays` 类，增加了可以在多核机器上高效运行的方法。

这些方法以 `parallel` 关键字开头，例如 `Arrays.parallelSetAll()`、`Arrays.parallelSort()` 等。

这组并行方法提供了数组的并行处理，可以在多核机器上非常快地运行 Java 代码。

## 384. Java 8 如何解决多重继承中的菱形问题？

在多重继承中，如果一个类继承了多个类，且这些类对同一个方法有不同的实现，就会导致菱形问题。

考虑以下示例来查看 Java 8 中菱形问题的产生和解决方案：

```java
public interface BaseInterface {
    default void display() { // 代码在此处 }
}
public interface BaseOne extends BaseInterface { }
public interface BaseTwo extends BaseInterface { }
public class ChildClass implements BaseOne, BaseTwo { }
```

在上述代码中，`ChildClass` 类会导致编译时错误。Java 编译器无法决定 `ChildClass` 应该调用哪个 `display` 方法。

为了解决这个问题，Java SE 8 提供了以下补救措施：

```java
public interface A {
    default void display() { // 代码在此处 }
}
public interface B extends A { }
public interface C extends A { }
public class D implements B, C {
    default void display() {
        B.super.display();
    }
}
```

```java
public interface BaseInterface {
    default void display() { // 代码在此处 }
}
public interface BaseOne extends BaseInterface { }
public interface BaseTwo extends BaseInterface { }
public class ChildClass implements BaseOne, BaseTwo {
    default void display() {
        BaseOne.super.display();
    }
}
```

在 `BaseOne.super.display()` 处的方法调用解决了菱形问题，因为它消除了编译器的疑惑。

## 385. Java 8 中 Predicate、Supplier 和 Consumer 的区别是什么？

Java 8 中 `Predicate`、`Supplier` 和 `Consumer` 之间的区别如下：

- `Predicate` 是接受一个参数并返回结果的匿名函数。
- `Supplier` 是不接受任何参数并返回结果的匿名函数。
- `Consumer` 是接受一个参数但不返回任何结果的匿名函数。

## 386. 可以在接口中在不标记 default 关键字的情况下定义默认方法吗？

不可以，我们必须始终在接口中用 `default` 关键字来标记默认方法。

如果我们在接口中创建了一个带有实现的方法，但没有将其标记为 `default`，我们将得到编译时错误。

## 387. 我们可以创建一个实现了两个具有相同名称和签名默认方法的接口的类吗？

不可以，不允许创建一个实现了具有相同默认方法的接口的类。

它会因为重复的默认方法而产生编译时错误。

## 388. Java 8 如何支持多重继承？

在多重继承中，一个类可以从多个父类继承行为。

在 Java 8 之前，一个类可以实现多个接口，但只能继承一个类。

在 Java 8 中，我们可以在接口内部包含方法实现。因此，接口的行为变得像抽象类。

现在，如果我们在类中实现多个具有方法实现的接口，意味着我们正在从多个抽象类继承行为。这就是我们在 Java 8 中获得多重继承的方式。

## 389. 如果我们创建一个继承基类并实现接口的类。如果基类和接口都具有相同名称和参数的默认方法，那么 JVM 将选取哪一个定义？

在这种情况下，JVM 将选取基类中的定义。

## 390. 如果我们在类中定义了相同的方法，在它的父类中以及该类实现的接口中也定义了它，那么当我们使用接口引用和类对象来访问它时，将调用哪个定义？

在所有情况下，类中定义的方法都将被调用。

## 391. 可以使用接口引用访问接口的静态方法吗？

不可以，接口的静态方法必须通过接口名称来调用。

## 392. 如何使用反射获取 Java 中的参数名称？

Java 8 引入了 `Parameter.getName()` 方法，用于通过反射获取参数的名称。

在使用此功能之前，我们需要在 Java 编译器中开启此功能。要开启此功能，只需在运行 `javac` 时带有 `-parameters` 参数即可。

要验证该功能的可用性，我们可以使用 `Parameter.isNamePresent()` 方法。

### 393. Java 8 中的 Optional 是什么？

`Optional` 是一个容器对象，可能包含空值或非空值。如果它有值，则 `isPresent()` 方法返回 `true`。

如果存在值，我们可以调用 `get()` 方法获取该值。否则我们将什么也得不到。

它在处理具有空值的数据时非常有用。

### 394. Optional 的用途有哪些？

Java 中 `Optional` 的一些用途包括：

- 我们可以使用 `Optional` 来避免应用程序中出现 `NullPointerException`。
- `Optional` 在编译时进行空检查，因此我们不会因为空值产生运行时异常。
- `Optional` 通过移除不必要的空检查减少了代码库的污染。
- `Optional` 还可以用于在数据为空时处理数据的默认情况。

### 395. Optional 中的哪个方法在值为空的情况下提供了回退（fallback）机制？

如果 `Optional` 值为空，我们可以使用 `orElseGet()` 方法作为回退机制。如果我们实现了 `orElseGet()` 方法，那么每当 `Optional` 的值为空时，它将会被调用。

## 396. 如何使用 Java 8 的 Date/Time API 获取当前时间？

在 Java 8 中，我们可以使用 `Clock` 获取当前时间。不再使用旧的 `System.currentTimeMillis()`，我们可以创建一个 `Clock` 对象并调用 `millis()` 方法来获取时间。

我们还可以在 `Clock` 对象上调用 `instant()` 方法。

### 397. 可以在接口中定义静态方法吗？

是的，从 Java 8 开始，接口可以拥有静态方法。

### 398. 如何使用反射分析类的依赖关系？

Java 8 自带了一个命令行工具 `jdeps`，可以分析包级和类级的依赖。

我们可以将 jar 名称或类名作为参数传递给工具。它将列出相应的依赖。

### 399. Java 8 引入了哪些 JVM 参数？

在 Java 8 中，ClassLoader 的 PermGen 空间被移除。它被 MetaSpace 取代。

现在我们可以设置 MetaSpace 的初始和最大尺寸。JVM 参数 `-XX:PermSize` 和 `-XX:MaxPermSize` 在 Java 8 中分别被 `-XX:MetaSpaceSize` 和 `-XX:MaxMetaspaceSize` 取代。

### 400. Java 8 引入了哪些流行的注解？

Java 8 引入的一些流行的注解包括：

- `@FunctionalInterface`：用于标记接口为函数式接口。如前所述，函数式接口可以用 Lambda 表达式。
- `@Repeatable`：用于标记另一个注解。它表示被标记的注解可以在类型上多次应用。

### 401. Java 8 中的 StringJoiner 是什么？

`StringJoiner` 是 Java 8 中的一个新类，用于创建字符串。它可以构造由分隔符分隔的字符序列。它还可以为该序列添加前缀和后缀。我们可以使用该序列来获取字符串。

例如：字符串 `[One:Two:Three]` 可以如下所示构造：

```java
StringJoiner sj = new StringJoiner(":", "[", "]");
sj.add("One").add("Two").add("Three");
String desiredString = sj.toString();
```

### 402. Java 8 中 Lambda 表达式的类型是什么？

Lambda 表达式的类型取决于它使用的上下文。

Lambda 类似于方法引用。它没有自己的类型。

通常情况下，Lambda 是函数式接口的实例。

### 403. Lambda 表达式的目标类型是什么？

Lambda 表达式的目标类型表示该表达式可以转换到的类型。

Lambda 表达式的目标类型是一个函数式接口。

Lambda 表达式的参数类型必须与接口中函数的参数类型相同。它的返回类型也必须与函数的返回类型兼容。

## 404. Java 8 中带有默认方法的接口和抽象类之间的区别是什么？

带有默认方法的接口在 Java 中看起来与抽象类相同。但两者之间存在细微的差异。

1. **实例变量**：接口不能拥有实例变量。抽象类可以拥有实例变量。
2. **构造函数**：接口不能有构造函数。抽象类可以有构造函数。
3. **具体方法**：接口除了默认方法外，不能有任何具体方法。抽象类允许定义带有实现的具体方法。
4. **Lambda**：恰好包含一个抽象方法的接口可以用于 Lambda 表达式。抽象类不能用于 Lambda 表达式。

## Java 陷阱题

### 405. a = a + b 和 a += b 表达式之间有区别吗？

我们在 Java 中添加两个整数变量（例如 `byte`、`short` 或 `int` 类型的变量），它们会首先提升为 `int` 类型，然后进行加法运算。

`+=` 运算符会隐式地将加法的结果转换为用于存储结果的变量的类型。

如果在 `try` 或 `catch` 块中放置 `return` 语句或 `System.exit()` 会发生什么？`finally` 块还会执行吗？

这是一个流行的 Java 面试陷阱题。大多数程序员认为无论如何 `finally` 块始终会执行。这个问题通过在 `try` 或 `catch` 块中放置 `return` 语句或从其中调用 `System.exit()` 来挑战这一概念。

你可以回答说，即使我们在 `try` 块或 `catch` 块中放置了 `return` 语句，`finally` 块也会执行。但如果从 `try` 或 `catch` 块中调用 `System.exit()`，`finally` 块将不会执行。

### 406. 表达式 1.0 / 0.0 返回什么？会有编译错误吗？

`Double` 类是许多陷阱面试题的来源。你可能了解 `double` 原生类型和 `Double` 类。但在进行浮点运算时，有些人没有足够关注 `Double.INFINITY`、`NaN` 和 `-0.0`。某些规则规定了涉及 `Double` 的浮点运算计算。

这个问题的答案是 `1.0 / 0.0` 将成功编译。而且它不会抛出 `ArithmeticException`。它只会返回 `Double.INFINITY`。

### 407. 可以在多个类中使用多个 `main` 方法吗？

可以。当我们在 Java 中启动应用程序时，我们只需要向 `java` 命令指定要运行的类名。JVM 只会在传递给 `java` 命令的类中查找 `main` 方法。因此，在多个拥有 `main` 方法的类之间不存在冲突。

### 408. Java 允许重写私有（private）或静态方法吗？

这个问题很有陷阱性，但答案非常简单。在 Java 中你不能重写 `private` 或 `static` 方法。如果我们在子类中创建一个相同返回类型和相同方法参数的相似方法，它将隐藏父类方法。这被称为方法隐藏（method hiding）。

此外，你不能在子类中重写 `private` 方法，因为 `private` 方法即使在子类中也是不可见的。因此，你可以做的是在子类中创建一个同名的另一个 `private` 方法。

所以在在这两种情况下，都不是方法重写。它要么是方法隐藏，要么是一个新方法。

## 409. 当向 HashMap 中放入一个已经存在的键对象时会发生什么？

在 `HashMap` 中有用于存储对象的桶（buckets）。具有相同 `HashCode` 的键对象会进入同一个桶。

如果你再次向 `HashMap` 中放入相同的键，它将替换旧的映射，因为 `HashMap` 不允许重复的键。相同的键将与之前的键对象具有相同的 `HashCode`。由于相同的 `HashCode`，它将存储在桶的相同位置。

### 410. 如何确保 N 个线程可以访问 N 个资源而不会产生死锁？

这个问题检查了你编写多线程代码的知识。如果你有死锁和竞态条件的经验，可以轻松地回答。

答案是，通过资源排序（resource ordering）可以防止死锁。如果我们在程序中始终按照特定顺序获取资源并以相反顺序释放资源，那么我们就可以防止死锁。

这样，等待相同资源的线程在另一个线程尝试获取该资源并持有第一个线程所需的资源时，不会进入死锁状态。如果它们都按照正确的顺序释放资源，其中一个就可以获取它并完成工作。

### 411. 如何从 Java 程序中判断 JVM 是 32 位还是 64 位？

我们可以通过从命令行提示符运行 `java` 命令来找到 JVM 的位数（32 位或 64 位）。

或者我们可以从 Java 程序中获取。

Sun 有一个 Java 系统属性来确定 JVM 的位数：32 或 64：

```java
sun.arch.data.model=32 // 32 位 JVM
sun.arch.data.model=64 // 64 位 JVM
```

我们可以使用 `System.getProperty("sun.arch.data.model")` 从 Java 程序中判断是 32 位还是 64 位。

## 412. Java 中表示货币（如美元/英镑）的正确数据类型是什么？

为了表示货币，数字中需要带有小数点，例如 $1.99。

`BigDecimal` 类提供了表示货币的良好方法。使用 `BigDecimal`，我们可以进行带有小数点的计算和正确的四舍五入。但使用 `BigDecimal` 的内存占用较高。

我们可以使用带精度的 `double`。但计算可能会给出错误的结果。

### 413. 如何在 Java 中实现多重继承？

这是为来自 C++ 和 Scala 背景的人准备的问题。许多面向对象的语言都支持多重继承。但 Java 不是其中之一。

这个问题的答案可以是，Java 通过允许接口继承多个接口来实现多重继承。但你不能继承多个类。因此，默认方法打破了这种行为。

### 414. `++` 操作在 Java 中是线程安全的吗？

不，`++` 操作不是线程安全的。它涉及多个指令，如读取值、对其递增并存回内存。这些指令在多个线程之间可能会交叉。因此它会导致多线程问题。

### 415. 如何在静态方法中访问非静态变量？

在 Java 中无法从静态方法中访问非静态变量。如果你这样写代码将会得到编译错误。这是初学者程序员最常见的问题之一，当他们尝试在 `main` 方法内部访问实例变量时。

由于 `main` 方法是静态的而实例变量是非静态的，解决方案是创建一个实例然后访问实例变量。

## 416. 假设父类中有一个方法抛出 `NullPointerException`。我们可以用一个抛出 `RuntimeException` 的方法来重写它吗？

这个问题正在检查你对 Java 中方法重载和重写概念的理解。

我们可以在重写的方法中抛出 `RuntimeException` 的子类，但如果是受检异常（checked Exception），我们不能这样做。

## 417. 如何将数组标记为 `volatile`？

如果你熟悉多线程，可以轻松地回答。

我们可以在 Java 中将数组标记为 `volatile`。但它只让数组的引用变为 volatile，而不是整个数组。

如果一个线程更改引用变量指向另一个数组，它将提供 volatile 保证。但如果多个线程正在修改单个数组元素，由于引用本身是 volatile，它们并不会获得相同的 volatile 保证。

## 418. 什么是 Java 中的线程局部变量？



线程局部变量是限制在特定线程中的变量。它是线程自己的变量副本，不在多个线程之间共享。Java 提供了 `ThreadLocal` 类来支持线程局部变量。为了实现线程安全，可以使用它。为了避免任何内存泄漏，在工作完成后移除线程局部变量总是好的。

## 419. Java 中 sleep() 和 wait() 方法有什么区别？

在 Java 中，我们使用这些方法来暂停当前运行的线程。它们之间有一个简单的区别。

`sleep()` 实际上用于短时间暂停，因为它不会释放锁。

`wait()` 用于条件等待，它可以释放锁，以便其他线程可以获取该锁并改变它正在等待的条件。

## 420. 你可以创建一个包含可变对象（mutable object）的不可变对象（Immutable object）吗？

在 Java 中，可以创建一个包含一个可变对象的不可变对象。

我们不应该共享该可变对象的引用，因为它是不可变对象内部的。相反，我们可以向其他方法返回它的拷贝。

## 421. 如何将字节数组（Array of bytes）转换为字符串？

你可以使用接受 `byte[]` 的 String 构造函数将字节数组转换为 String 对象。我们需要确保使用了正确的字符编码，否则在转换后可能会得到不同的结果。

## 422. CyclicBarrier 和 CountDownLatch 类之间有什么区别？

CyclicBarrier 和 CountDownLatch 类是从 Java 5 开始引入的。

即使 CyclicBarrier 被破坏了（broken），我们也可以复用它，但在 Java 中我们无法复用 CountDownLatch。

## 423. StringBuffer 和 StringBuilder 之间有什么区别？

StringBuilder 是 Java 5 中引入的。两者之间的主要区别是 StringBuffer 的方法（例如 `length()`、`capacity()`、`append()`）是同步的。而 StringBuilder 中对应的方法不是同步的。

由于这种差异，使用 StringBuilder 拼接字符串比使用 StringBuffer 更快。现在使用 StringBuffer 被认为是一种不好的做法，因为在大多数情况下，我们都在同一个线程中执行字符串拼接。

## 424. 哪个类包含了 clone 方法？是 Cloneable 类还是 Object 类？

这是一个非常基础的陷阱题。`clone()` 方法定义在 Object 类中。Cloneable 是一个标记接口（marker interface），它不包含任何方法。

## 425. 如何在 Java 中获取线程转储（thread dump）？

有特定平台的命令用于在 Java 中获取线程转储。

在 Linux/Unix 中，只需使用 `kill -3 PID`，其中 PID 是 Java 进程的进程 ID。它将给出 Java 进程的线程转储。

在 Windows 中，按下 `Ctrl + Break`。这会指令 JVM 将线程转储打印到标准输出（stdout）或标准错误（stderr）。取决于你的应用程序配置，它也可以进入控制台或日志文件。

## 426. 你可以将 int 变量转换为 byte 变量吗？如果 int 的值大于 byte 会什么？

Java 中的 int 是 32 位的。但 Java 中的 byte 只有 8 位。我们可以将 int 强制转换为 byte。但在转换过程中我们将丢失 int 的高 24 位。因为 byte 只能保存 int 的前 8 位。剩余的 24 位（32-8=24）将会丢失。

## 427. 在 Java 中，我们可以在不进行显式转换的情况下将 double 值存储在 long 变量中吗？

不可以，我们不能在不转换为 long 的情况下将 double 值存储到 long 变量中。double 的范围大于 long。所以我们需要进行类型转换。

要回答这个问题，只需记住 Java 中 double 和 Long 哪一个更大即可。

## 428. 5*0.1 == 0.5 返回什么？true 还是 false？

答案是 false，因为浮点数在 Java 中无法精确表示，所以 5*0.1 不等于 0.5。

## 429. 在 int 和 Integer 之间，哪个占用更多内存？

在 Java 中，Integer 对象比 int 占用更多内存。Integer 是对象，它存储了关于对象的元数据开销（meta-data overhead）。int 是基本类型，所以它占用的内存更少，且没有元数据开销。

## 430. Java 的 switch 语句中使用 String 吗？

可以。从 Java 7 开始，String 可以用于 switch 语句。这为程序员提供了便利。但内部使用了 String 的哈希值（hash code）来进行 switch。

## 431. 可以在同一个类中使用多个 main 方法吗？

可以。你可以在同一个类中有多个名为 `main` 的方法。但只能有一个签名为 `public static void main(String[] args)` 的 main 方法。JVM 只会查找具有此签名的 main 方法。同一个类中其他名为 `main` 的方法会被忽略。

## 432. 在创建抽象类时，在它的构造函数内部调用抽象方法是一个好主意吗？

不，我们应该避免在抽象类的构造函数中调用抽象方法。因为这可能会限制子类实现这些抽象方法的方式。

许多 IDE 对这种实现给出“Overridable method call in constructor”（构造函数中调用可覆盖方法）警告。

这是一个对象初始化顺序的问题。父类构造将在子类构造函数之前运行。这意味着子类尚未初始化。但由于父类中存在重写的方法，当子类尚未完全初始化时就调用了子类的重写方法。

## 433. 如何在 Java 中实现构造链（constructor chaining）？

当我们从同一个类的一个构造函数调用另一个构造函数时，在 Java 中被称为构造链。

## 434. 如何在 Java 中查找内存使用？

我们可以使用 `java.lang.Runtime` 提供的内存相关方法获取空闲内存、总内存和最大内存。

`Runtime.freeMemory()` 返回字节为单位的空闲内存。

`Runtime.totalMemory()` 返回字节为单位的总内存。

`Runtime.maxMemory()` 返回字节为单位的最大内存。

## 435. Java 中 x == y 和 x.equals(y) 有什么区别？

`==` 表达式执行引用匹配，如果 a 和 b 都指向同一个对象，则在两者指向同一个对象时返回 `true`。

`x.equals(y)` 表达式用于逻辑相等，并期望对象提供逻辑映射。如果两个是不同的对象，它将返回 `false`。

## 436. 如何保证垃圾回收的发生？

不能。我们无法保证 Java 中的垃圾回收。Java 文档明确指出不保证进行垃圾回收（GarbageCollection）。

你可以调用 `System.gc()` 请求垃圾回收，但它仅仅是——一个请求。是否运行取决于垃圾回收器的裁量。

## 437. Object 类的 x.hashCode() 方法和 x.equals() 方法有什么关系？

`x.hashCode()` 方法返回与对象实例对应的 int 类型哈希值。它被用于基于哈表的集合类，如 `Hashtable`、`HashMap`、`LinkedHashMap` 等。

`hashCode()` 方法与 `equals()` 方法有关。

根据 Java 规范，使用 `equals()` 方法相等的对象必须具有相同的哈码。

因此，具有相同 hashCode 的两个对象可能相等也可能不相等。但相等的对象应该具有相同的 hashCode。

## 438. 什么是 Java 中的编译时常量（compile time constant）？

编译时常量是 `public static final` 变量。这里 `public` 修饰符是可选的。在编译时，它们会被替换为实际值，因为编译器提前知道它们的值并且知道不能更改。所以它们是常量。

## 439. 解释快速失败（fail-fast）和安全（fail-safe）迭代器的区别？

快速失败和安全迭代器之间的主要区别在于在迭代期间是否可以修改集合。

安全迭代器允许在迭代任务中修改集合。但快速失败迭代器不允许在迭代期间对集合进行任何修改。

在迭代期间，快速失败迭代器一旦发现集合被修改就会失败。修改可以是添加、删除或更新成员。并且它会抛出 `ConcurrentModificationException`。例如 `ArrayList`、`HashSet` 和 `HashMap` 是快速失败的。

`ConcurrentHashMap`、`CopyOnWriteArrayList` 是安全的。

## 440. 你有一个字符数组和一个 String。哪种在存储敏感数据（如密码、出生日期等）时更安全？

简短的回答是，在字符数组中存储敏感信息是安全的。

在 Java 中，String 是不可变的，并且存储在字符串池（String pool）中。一旦 String 被创建，它就会一直留在内存池中，直到被垃圾回收。你无法控制垃圾回收。因此，任何访问内存转储（memory dump）的人都可能提取并使用这些敏感数据。

相比之下，如果你使用像字符数组这样的可变对象来存储值，一旦完成操作，你可以将其置为空。一旦清空，其他人就无法再使用它。

## 441. 为什么在 Java 中使用 `volatile` 关键字？

`volatile` 关键字保证了对变量读写操作的全局排序。这意味着每个访问 `volatile` 字段的线程都会读取变量的当前值，而不是使用缓存值。

通过将变量标记为 `volatile`，变量的值永远不会在线程本地缓存。所有的读取和写入操作将直接访问 Java 的主内存。

## 442. Java 中 `Queue` 接口的 `poll()` 和 `remove()` 方法有什么区别？

这是一个关于 `Queue` 数据结构理解的基础问题。`poll()` 和 `remove()` 方法都会移除并返回队列的头元素。

当 `Queue` 为空时，`poll()` 方法执行失败并返回 `null`，而 `remove()` 方法执行失败并抛出异常（Exception）。

## 443. 你可以在 Java 中捕获由另一个线程抛出的异常吗？

可以的，可以通过 `Thread.UncaughtExceptionHandler` 实现。

Java 文档提到：“当线程准备因一个未捕获的异常而终止时，Java 虚拟机将通过 `Thread.getUncaughtExceptionHandler()` 查询该线程的 `UnExceptionHandler`，这将调用处理器的 `uncaughtException` 方法，并将线程和异常作为参数传递。”

## 444. 你如何决定在 Java 中使用哪种类型的内部类——静态（Static）还是非静态（Non-Static）？

内部类对外部类的字段和方法具有完全访问权限。这对于事件处理器来说非常方便，但也是有代价的。内部类的每个实例都会保留并需要引用其外部类。

由于这种代价，在许多情况下，静态嵌套类（static nested classes）比内部类更优。当嵌套类的实例生命周期长于外部类的实例时，嵌套类应该是静态的，以防止内存泄漏。

有时，由于对外部类的“隐藏”引用，内部类更难通过反射来构造。

## 445. Java 中有哪些类型的类加载器（Classloaders）？

Java 类加载器是 Java 运行环境（JRE）的一部分，负责根据需要将类加载到 Java 虚拟机（JVM）中。

当 JVM 启动时，会使用三种类型的类加载器：

1. 启动类加载器（Bootstrap Classloader）：它从文件夹加载核心 java API 文件 `rt.jar` 类。
2. 扩展类加载器（Extension Classloader）：它从 `lib/ext` 文件夹加载 jar 文件。
3. 系统/应用加载器（System/Application Classloader）：它从环境变量 `CLASSPATH` 指定路径加载 jar 文件。

类可能从本地文件系统、远程文件系统甚至从网络加载。

## 446. 在什么情况下你会选择 `HashSet` 或 `TreeSet`？

在几乎所有方面，`HashSet` 都比 `TreeSet` 好。它为 `add()`、`remove()` 和 `contains()` 操作提供了 $O(1)$ 的复杂度。而 `TreeSet` 对这些操作的复杂度是 $O(\log(N))$。

尽管如此，当你希望保持插入元素的顺序或查询集合中某个范围的元素时，`TreeSet` 是非常有用的。

当我们想要维护顺序时，应该使用 `TreeSet`。或者当读取操作足够多，足以抵消写入操作成本增加的影响时使用它。

## 447. Java 中方法引用（method references）有什么用？

Java 8 引入了方法引用。它允许将构造函数和方法作为 lambda 使用。

方法引用的主要用途是提高代码的组织清晰性和简洁。

## 448. 你认为 Java 枚举（Enums）比整数常量更强大吗？

是的，Java 枚举提供了许多整数常量无法提供的功能。枚举可以被视为具有固定数量实例的 final 类。枚举可以实现接口，但不能继承另一个类。

在实现策略模式时，我们可以利用枚举的这一特性。特别是当策略数量是固定的情况下。

你还可以在 Java 枚举值上附加元数据。此外，枚举值是类型安全的，而整数常量不是。

你还可以在枚举值中定义自定义行为。

从构造函数初始化静态成员的工作量更大。你必须确保每个构造函数都执行了此操作。你需要维护一个标记来指示静态工作已完成。对于未从静态上下文初始化的静态块工作，你可能需要考虑同步或竞态条件。

## 450. 你的客户抱怨你的代码抛出了 `NoClassDefFoundError` 或 `NoSuchMethodError`，尽管你能够无错误地编译代码且该方法在代码中存在。这背后的原因是什么？

有时即使方法名相同，我们也会升级库。但我们忘记让客户知道新版本。由于版本差异，当某个库不兼容这种升级时，在运行时就会遇到 `NoClassDefFoundError` 或 `NoSuchMethodError`。

Java 构建工具和 IDE 还可以生成依赖报告，告诉你哪些库依赖于哪些库。

## 451. 你如何使用正则表达式来检查一个 String 是否为数字？

正则表达式（Regex）是匹配和搜索模式的强大工具。

数字字符串只能包含数字，即 0 到 9。它也可以在字符串开头包含 `-` 号。我们可以为这些规则创建一个正则表达式。一个简单的示例如下：

```java
Pattern pattern = Pattern.compile("\\D");
```

## 452. `s = "Temporary"` 和 `s = new("Temporary")` 表达式之间有什么区别？哪一个更好更高效？

通常情况下，`s = "Temporary"` 比 `s = new("Temporary")` 更高效。

在 `s = "Temporary"` 的情况下，字符串池中会创建一个值为 "Temporary" 的字符串。如果创建另一个相同的字符串（例如 `s2 = "Temporary"`），它将引用字符串池中的同一个对象。

但当你使用 `s = new("Temporary")` 时，Java 在字符串池中创建一个值为 "Temporary" 的字符串。此外，该字符串对象会被传递给 String 对象的构造函数，即 `new String("Temporary")`。这会再次创建另一个（不在字符串池中的）字符串对象。

因此，每次这样的调用都会创建一个额外的字符串对象，而不是重用字符串池中的同一个对象。

所以 `s = "Temporary"` 始终是高效的方法。

## 443. 在 Java 中，两个相等的对象会有不同的哈码吗？

不。两个相等的对象不可能不同的哈码。但两个具有相同哈码的对象可能相等，也可能不相等。

## 454. 如何在 Java 中打印数组（Array）？

通过使用 `Arrays` 类的方法可以打印数组。我们可以使用 `Arrays.toString()` 方法或使用 `Arrays.deepToString()` 方法。

由于数组本身没有实现 `toString()` 方法，直接将数组传递给 `System.out.println()` 不会打印其内容。但可以使用 `Arrays.toString()` 来打印数组的每个元素。

## 455. 在 Java 的 `hashcode()` 方法实现中使用随机数是否？

不可以。对象的 hashcode 应该始终相同。如果你在 `hashcode()` 方法中使用随机数，那么对于同一个对象可能会得到不同的 hashcode 值。这将破坏 hashcode 契约。

## 456. 在构造器注入（constructor injection）和集合注入（setter dependency injection）之间，哪一个更好？

构造器注入保证类在创建时会初始化所有的依赖。但 setter 注入提供了设置可选依赖的灵活性。

如果我们使用 XML 文件来描述依赖关系，setter 注入更可读性。

通常情况下，对于强制性依赖使用构造器注入，对于可选依赖使用 setter 注入这是一种良好的实践。

## 457. Java 中 DOM 解析器和 SAX 解析器有什么区别？

在 Java 中，文档对象模型（DOM）解析器将整个 XML 加载到内存中，并基于 DOM 模型创建一个树。这有助于它快速定位节点并修改 XML 的结构。

另一方面，XML 应用程序接口（SAX）解析器基于事件的解析器。它不会将整个 XML 加载到内存中。由于这个原因，DOM 比 SAX 快，但需要更多内存，且不适合解析大型 XML 文件。

## 458. 在 Java 中，Enumeration（枚举）和 Iterator（迭代器）之间，哪一个性能更好？



Enumeration 接口是一个只读接口。它的性能比 Iterator 好，几乎是 Iterator 的两倍快。它占用的内存也非常少。此外，Enumeration 没有 `remove()` 方法。

另一方面，Iterator 接口比 Enumeration 更安全，因为它可以检查在迭代期间集合是否被修改过。如果 Iterator 正在迭代时集合被更改，它会抛出 `ConcurrentModificationException`。

## 459. 引用传递（pass by reference）和按值传递（pass by value）有什么区别？

每当对象按值传递时，意味着传递的是对象的拷贝。即使对该对象进行了更改，也不会影响原始值。

每当对象按引用传递时，意味着传递的不是实际对象，而是该对象的引用。因此，外部方法所做的任何更改也会反映在实际对象及其引用中。

## 460. 在 Java 中对集合（collection）排序有哪些方法？

在 Java 中排序集合最流行的方法是调用 `Collections.sort()` 方法。你可以为 `sort()` 方法提供自定义的 `Comparator`，以你自定义的方式对数据进行排序。

另一种方法是使用排序集合，如 `TreeSet` 或 `TreeMap`，它们以排序顺序存储信息，然后你可以将其转换为 `List`。

## 461. 为什么 Collection 接口没有扩展 `Cloneable` 和 `Serializable` 接口？

`Collection` 接口仅指定了被称为元素的对象组。`Collection` 的每个具体实现都可以选择它自己的维护和排序元素的方式。

某些集合可能允许重复键，而另一些集合可能不允许。

许多集合实现都有 `clone` 方法，但很多并没有。将其包含在所有实现中是不有意义的，因为 `Collection` 是一个抽象表示。重要的是具体的实现。

克隆和序列化是在进行具体实现时考虑的。因此，集合的具体实现应该决定它们如何被克隆或序列化。

## 462. Java 中进程（process）和线程（thread）有什么区别？

进程仅仅是程序的执行。

线程是进程内部的单一执行序列。

一个进程可能包含多个线程。线程也被称为轻量级进程。

## 463. 使用无序数组相比有序数组有什么好处？

在有序数组中，搜索的时间复杂度为 $O(\log n)$。而在无序数组中，搜索的时间复杂度为 $O(n)$。

在有序数组中，插入操作的时间复杂度为 $O(n)$。而无序数组的插入操作需要常数时间 $O(1)$。

因此，当写操作多于读操作时，使用无序数组更好。

## 464. 在 Java 的 HashSet 和 TreeSet 集合之间，哪一个更好？

`HashSet` 使用 `HashTable` 实现。因此，它的元素是随机顺序存储的。`HashSet` 的 `add()`、`remove()` 和 `contains()` 方法具有常数时间复杂度 $O(1)$。

`TreeSet` 使用树数据结构实现。`TreeSet` 中的元素按自然顺序排序。因此，`add()`、`remove()` 和 `contains()` 方法的时间复杂度为 $O(\log n)$。

所以从性能角度来看，`HashSet` 性能优于 `TreeSet`。但如果你按自然顺序存储元素，`TreeSet` 是更好的集合。

## 465. JVM 何时调用 `finalize()` 方法？

JVM 在从内存中释放对象之前，指示垃圾回收器调用 `finalize` 方法。程序员可以实现 `finalize()` 方法来显式释放对象持有的资源。这将有助于更好的内存管理并避免任何内存泄漏。

## 466. 在 Java 中何时使用串口垃圾回收器（Serial Garbage collector）或吞吐量垃圾回收器（Throughput Garbage collector）？

串口垃圾回收器用于堆内存需求最高 100 MB 的小型应用程序。

吞吐量垃圾回收器用于中大型 Java 应用程序。

## 467. 在 Java 中，如果你将对象引用设置为 `null`，垃圾回收器会立即释放该对象持有的内存吗？

不会。JVM 在内存不足时随时决定运行垃圾回收器。当垃圾回收器运行时，它会寻找可进行垃圾回收的对象，然后释放与该对象相关的内存。

所以，仅仅将对象引用设置为 `null` 会使其符合垃圾回收的条件，但不会立即释放内存。

## 468. 如何在 Java 中使对象符合垃圾回收条件？

要使一个对象符合垃圾回收条件，只需确保它在当前定义/使用的程序中是不可达的。你可以将对象引用设置为 `null` 并确保没有对象引用它。一旦对象无法被触达，垃圾回收就可以可以在下次运行时清理它。

## 469. 在 Java 中何时使用 `Exception` 或 `Error`？它们之间有什么区别？

`Throwable` 类是 Java 中 `Exception` 和 `Error` 类的父类。

当你想要捕获程序可能创建或遇到的异常情况时，请使用 `Exception` 类或 `Exception` 的子类。

当你遇到意料之外的情况时，在 Java 中使用 `Error` 类。此外，在大多数情况下无法从 `Error` 中恢复。因此，终止程序更好。

## 470. 在 Java 中 `PreparedStatement` 相比 `Statement` 类的优势是什么？

`PreparedStatement` 是数据库查询的预编译语句。由于这个原因，它们的性能好得多。此外，我们可以使用不同的输入值重用相同查询的 `PreparedStatement` 对象。

而 `Statement` 类不提供这些功能。

## 471. 在 Java 中，`throw` 和 `throws` 关键字有什么区别？

当我们想在代码中抛出异常时，使用 `throw` 关键字配合要抛出的异常名称。

而 `throws` 关键字用于方法声明。`throws` 关键字告诉我们该方法可能被抛出的 `Exception`。此方法的任何调用者都应该准备好预期此 `Exception`。

另一个微小区别是 `throw` 只能跟一个异常，但 `throws` 可以跟逗号分隔的多个异常列表。

## 472. 异常处理完成后，`Exception` 对象会发生什么？

一旦异常处理完成，`Exception` 对象就是不可达的。然后它在下次垃圾回收器运行时会被垃圾回收。

## 473. 在 Java 中如何找到哪台客户端机器向你的 servlet 发请求？

我们可以使用 `ServletRequest` 类查找客户端机器的 IP 地址或主机名。

有方法 `getRemoteAddr()` 获取客户端机器的 IP 地址以及 `getRemoteHost()` 获取客户端机器的主机名。

## 474. Java 中 Cookie 和 Session 对象之间有什么区别？

Cookie 和 Session 都用于客户端与服务器之间的通信。客户端可以禁用 Cookie，这会导致 Web 服务器无法发送 cookie。但客户端无法禁用 session。因此，无论客户端端如何设置，Session 始终可以工作。

此外，Session 可以存储任何 Java 对象。但 Cookie 只能在 String 对象中存储少量信息。

## 475. 浏览器和 Servlet 之间相互通信使用什么种协议？

HTTP 协议。浏览器和 Servlet 通过 HTTP 协议进行相互通信。

## 476. 什么是 HTTP 隧道技术（HTTP Tunneling）？

互联网上有许多网络通信协议，但其中 HTTP是最流行的。HTTP 隧道技术是一种技术，通过 HTTP 或 HTTPS 协议封装由其他类型协议完成的通信。将其他协议请求伪装成 HTTP 请求的方法被称为 HTTP 隧道技术。

## 477. 为什么在 Java 中我们使用 JSP 而不是 Servlet？

由于 JSP 页面被动态编译成 servlet，程序员可以轻松地对表现层代码进行更新。

为了获得更好的性能，可以对 JSP 页面进行预编译。

此外，JSP 页面提供了结合静态模板 HTML 或 XML 片段的灵活性。

另外，程序员可以在类级别进行逻辑更改，而无需编辑使用该类逻辑的 JSP 页面。

## 478. 空的 ‘.java’文件名在 Java 中是有效的源文件名吗？

是的。你可以创建一个类并将其存储在名为 .java 的文件中。

你可以亲自尝试，通过创建、编译和运行这样的文件。它会正常运行。

## 479. 如何在 Java 中实现 Servlet 链（Servlet Chaining）？

要实现 Servlet 链，必须有多个 servlet。一个 servlet 的输出必须发送到第二个 servlet。第二个 servlet 的输出可以发送到第三个 servlet，以此此类推。通过这种方式形成一个 servlet 链来完成任务。

链中的最后一个 servlet 将负责向客户端发送最终响应。

## 480. 你可以实例化这个类吗？

```java
public class A
{
    A a = new A();
}
```

不能，这个类无法实例化，因为它会导致递归调用其构造函数。

## 481. 为什么 Java 不支持运算符重载？

Java 支持方法重载（Method overloading）但不支持运算符重载（operator overloading）。添加运算符重载会使设计变得复杂。此外，它会使编译器变得复杂。

另一个原因是，运算符重载会降低 JVM 的性能，因为 JVM 需要在运行时执行额外工作来寻找重载运算符的真实含义。

## 482. 为什么 Java 中的 String 类是不可变的（Immutable）或最终的（Final）？

由于 String 对象缓存在字符串池（String pool）中，因此将 String 设计为不可变是合理的。缓存的字符串字面量在多个客户端之间共享。存在一个客户端的操作影响另一个客户端对字符串池访问的可能性。

String 还用作许多 Java 类的参数。例如，在打开网络连接时，你可以作为 String 传递主机名、端口号。如果任何人可以修改你的 String 副本，它就会更改主机名。由于这个原因，在创建 String 后立即将其标记为 final 是合理的。

## 483. sendRedirect 和 forward 方法之间有什么区别？

当你使用 `sendRedirect` 方法时，它会创建一个新的请求。当你使用 `forward` 方法时，它只是将请求转发到新的新目标。

在 `sendRedirect` 的情况下，之前的请求作用域对象是不可用的，因为创建了新的请求。

在 `forward` 方法的情况下，之前的请求作用域对象在转发后仍然可用。

此外，`sendRedirect` 方法认为比 `forward` 方法慢。

## 484. 如果你的 Serializable 类包含一个不可序列化的成员，该如何修复它？

如果你想让一个类变为可序列化的（Serializable），但发现该类包含不可序列化的成员，那么你必须将这些成员标记为 `transient`。这将确保该成员在序列化过程中不会持久化到字节流中。

因此，Java 的 `transient` 关键字在这种情况下提供了帮助。

## 485. Java 中运行时多态（run time polymorphism）的作用是什么？

在运行时，对象的行为可以根据其运行时状态发生变化。因此，Java 引入了运行时多态。如果你在子类中重写了方法，你就是提供了运行时多态。在编译时不会发生任何事情。但在运行时，JVM 会根据对象的类决定将调用哪个方法。

## 486. Java 中方法重载（method overloading）和方法重写（method overriding）的规则是什么？

当我们想要重载一个方法时，需要确保方法名保持相同。但方法签名可以在参数的数量、数据类型或参数顺序上有所不同。

当我们想要重写一个方法时，我们确保该方法抛出的检查异常（checked exceptions）不是比被重写方法声明的新新的或更高的。此外，我们确保方法名、参数和返回类型保持相同。

此外，我们不能在 Java 中重写 Static 和 Final 方法。

## 487. Java 中类（class）和对象（object）之间有什么区别？

类（Class）是待创建对象（Object）的模板或蓝图。对象（Object）是类的实例。类定义了方法和成员变量，但对象填充了值。

因此，类是你用来创建对象的蓝图。对象是你使用特定规范创建的具体的“实体”。大多数面向对象编程概念只有在对象创建时才有效。

## 488. 我们可以创建一个扩展另一个抽象类的抽象类吗？

是的。抽象类可以扩展另一个抽象类。它不需要定义父抽象类的方法。只有非抽象类必须定义抽象方法。

## 489. 为什么要在 Java 中使用向上转型（Upcasting）或向下转型（Downcasting）？

当我们想要将子类转换为父类时，我们使用向上转型。它也被称为宽转换（widening）。向上转型在 Java 中是总是允许的。

当我们想要将父类转换为子类时，我们使用向下转型。它也被称为窄转换（narrowing）。

有时，如果类型检查失败，向下转型可能会抛出 ClassCastException。

## 490. 在 Java 中通过包组织类和接口的原因是什么？

正如名称所示，一个包包含类的集合。它有助于设定文件的分类。例如-它是数据访问对象（DAO）还是一个 API。

它有助于防止命名空间（Namespace）冲突。

此外，我们可以通过包以及类及其方法上正确的修饰符来引入访问限制。

## 491. 什么是 Java 信息隐藏（information hiding）？

信息隐藏是一个面向对象的概念。在 Java 中你可以使用封装（encapsulation）来实现信息隐藏。对象可以使用访问修饰符（如 public、private、protected）向其他对象隐藏其内部细节。这有助于将对象的内部逻辑与外部世界解耦。

通过使用信息隐藏，对象可以更改内部实现而不影响外部调用客户端的代码。

## 492. 为什么 Java 提供默认构造函数（default constructor）？

在 Java 中，所有的交互都发生在对象实例之间。为了创建对象实例，JVM 需要一个构造函数。Java 不强制程序员为每个类定义默认构造函数。

每当需要创建对象且程序员没有提供构造函数时，Java 使用默认构造函数来创建对象。默认构造函数还会将成员变量初始化为默认值。

## 493. Java 中 super 和 this 关键字的区别是什么？

我们使用 `super` 关键字来从子类访问（父类）的方法。

我们使用 `this` 关键字来访问同一个类的方法。

## 494. 在 Java 中使用 Unicode 字符有什么优势？

Unicode 字符在规范中拥有多得多的字符。

它们还包含了亚洲语言字符和非西欧语言字符。

大多数现代技术、网站和浏览器都支持这些 Unicode 字符。

## 495. 在 Java 中可以重写重载方法（overloaded method）吗？

可以。如果该方法不是静态（static）或最终（final）方法，Java 允许重写重载方法。

## 496. 如何更改 JVM 的堆大小？

Java 提供了命令行参数来设置 JVM 的堆大小。

你可以在 `-Xms` 和 `-Xmx` 参数中指定值。这些参数代表 JVM 的初始堆大小和最大堆大小。

## 497. 为什么要在 Java 中定义默认构造函数？

通常情况下，Java 为每个类都提供一个默认构造函数。但在某些情况下，我们想要定义自己的版本的默认构造函数。

当我们想要使用默认值构造对象时，我们就会创建默认构造函数。

有时，我们可以默认构造函数标记为私有（private）。这样任何其他类都无法创建我们类的实例。这种技术通常用于单例模式（Singleton pattern）。

## 498. 如何在 Java 中使对象不可变（Immutable）？

要使对象不可变，请遵循这两个规则：第一，不要使用任何可以更改类字段的 setter 方法。第二，将字段标记为 `final`。通过遵循这些规则，成员变量在初始化后无法更改。这将确保对象的成员变量不会改变。因此，该对象被认为是不可变的。

## 499. 如何在 Java 代码中防止 SQL 注入？

在 Java 中，你可以使用 `PreparedStatement` 来防止 SQL 注入。在 `PreparedStatement` 中，你可以传递带有预定义参数的预编译 SQL 查询。这有助于检查 SQL 查询中参数的类型。从而保护你的代码免受 SQL 注入攻击。

## 500. HashMap 的键 Object 应该始终实现哪两个方法？

任何我们想要作为 HashMap 键或其他任何基于哈希的集合数据结构（例如 Hashtable 或 ConcurrentHashMap）的对象，都必须实现 `equals()` 和 `hashCode()` 方法。

## 501. 为什么用作 HashMap 键的对象应该是不可变的？

键对象应该是不可变的，这样 `hashCode()` 方法始终为该对象返回相同的值。

`hashCode()` 方法返回的 Hashcode 取决于对象成员变量的值。如果对象是可变的，那么成员变量就可以改变。一旦成员变量改变，Hashcode 就会改变。如果同一个对象在不同时间返回不同的哈码，那么它在 HashMap 中使用的就是不可靠的。

假设，当你插入对象时，Hashcode 是 X，HashMap 将其存储在桶 X 中。但当你搜索它时，Hashcode 是 Y，那么 HashMap 将在桶 Y 中寻找该对象。这样你就无法获取你所存储的内容。

为了解决这个问题，键对象应该是不可变的。

尽管编译器没有强制执行这一规则，但一个优秀的程序员总是会记住这条规则。

## 502. 如何在多个线程之间共享一个对象？

有许多方法可以在多个线程之间共享同一个对象。你可以使用 `BlockingQueue`（阻塞队列）将一个对象从一个线程传递到另一个线程。



你也可以为此目的使用 `Exchanger` 类。`Exchanger` 是 Java 中 `SynchronousQueue` 的双向形式。你也可以用它来交换对象。

# 503. 如何判断你的程序是否发生了死锁？

如果我们怀疑应用程序由于死锁而卡住，那么只需使用运行应用程序的环境特定的命令来获取线程转储（thread dump）。例如，在 Linux 中你可以使用 `kill -3` 命令。

在死锁的情况下，你会在线程转储中看到 JVM 中线程当前的状态和堆栈跟踪，其中一个或多个线程会卡在带有 deadlock 消息的状态上。

你也可以通过 JDK 自带的 `ThreadMXBean` 类通过程序实现此功能。

如果你不需要程序化检测，可以使用 JConsole。在“thread（线程）”选项页上有一个“detect deadlock（检测死锁）”按钮。

## 混合

# 1. Java 中的包装类（Wrapper classes）是什么？

Java 有包装类（Wrapper）的概念，允许基本类型作为对象被访问。像 `boolean`、`int`、`double`、`float` 等基本类型有对应的包装类——`Boolean`、`Integer`、`Double`、`Float` 等。

许多这些包装类位于 `java.lang` 包中。

Java 5.0 为 Java 中的包装类引入了自动装箱（Autoboxing）和拆箱（Unboxing）的概念。

例如：

```java
public class WrapperTest{
    public static void main(String args[]){
    //将 int 转换为 Integer
    int count=50;
    Integer i=Integer.valueOf(count);//将 int 转换为 Integer
    Integer j=count;//自动装箱
```

# 2. Java 中 native 方法（原生方法）的目的是什么？

`native` 关键字用于方法，表示该方法是使用 JNI（Java Native Interface）用原生代码实现的。

因此，native 方法允许 Java 开发者直接访问特定平台的 API。

通常，native 方法链接到原生库上。

### 3. 什么是 System 类？

`System.class` 是由 `java.lang` 包提供的最终类（final class）。它包含了几个实用的类字段和方法。

`System` 类的目的是提供对系统资源的访问。

# 4. 在 System.out.println 方法调用中，System、out 和 println 分别是什么？

`System` 是 `java.lang` 包提供的最终类。

`out` 指向 `PrintStream` 类，是 `System` 类的一个静态成员。

`println` 是 `PrintStream` 类的方法。

# 5. Java 中浅拷贝（Shallow Copy）的另一种名称是什么？

对象克隆（Object Cloning）。浅拷贝只复制引用的值。

# 6. Java 中浅拷贝（Shallow Copy）和深拷贝（Deep Copy）的区别是什么？

浅拷贝只复制类中引用的值。

深拷贝也会复制对象的值。

### 7. 什么是单例类（Singleton class）？

Java 中的单例类在 JVM 中始终最多只有一个实例。该类的构造函数的编写方式确保了它不会创建同类类的多个对象。

# 8. 单例类和静态类（Static class）的区别是什么？

Java 中的静态类只有静态方法。它是函数的容器。它是基于过程化编程设计的。

单例类是面向对象设计中的一种模式。单例类在 JVM 中始终只有一个对象实例。这种模式的实现方式确保了始终存在该类的类的实例。

# 13. 如何实现一个线程安全的 JSP 页面？

我们可以使用 `SingleThreadModel` 接口来实现一个线程安全的 JSP 页面。

我们也可以在 JSP 页面中添加 `<@page isThreadSafe="false" %>` 指令来使其线程安全。

# 14. 如何在 JSP 页面中包含静态文件？

我们可以使用 JSP 的 `include` 指令在 JSP 中包含一个静态页面。在这种方法中，我们使用在翻译阶段（translation phase）来包含静态页面。我们必须在该指令中通过 `file` 属性指定要包含的资源 URL。

例如：`<%@ include include="footer.html" %>`

# 15. JSP 的生命周期方法有哪些？

JSP 具有以下生命周期方法：

- 1. `jspInit()`：当 JSP 第一次被调用时会执行此方法。我们可以在此方法中为处理请求进行初始化设置。

- 2. `jspService()`：此方法用于处理 JSP 的每一个请求。

- 3. `jspDestroy()`：一旦我们从容器中移除 JSP，就会调用此方法。它用于清理数据库连接等资源。

# 16. 在 Web 架构中使用 JSP 有什么优势？

在 Web 架构中使用 JSP 我们可以获得以下优势：

- 1. **性能**：由于 JSP 设计使用相同的代码来处理多个请求，它提供了非常好的性能。

- 2. **快速**：由于 JSP 是预编译的，服务器可以非常快速地提供页面。

- 3. **可扩展性**：JSP 基于 Java Servlets。这有助于使用 JDBC、JMS、JNDI 等其他 Java 技术来扩展 JSP 架构。

- 4. **设计**：使用 JSP 设计用户界面更加容易，因为它非常接近 HTML。UI 设计师可以使用模拟数据创建 JSP，而开发者随后可以提供动态数据的实现。

### 17. JSP 相比于 Javascript 的优势是什么？

在 JSP 中，我们可以无缝地编写 Java 代码。它允许编写可以与应用程序其他部分进行交互的代码。

Javascript 代码大部分在客户端执行执行。这限制了在 Javascript 代码中可以完成的任务。我们无法从客户端的 Javascript 连接到数据库服务器。

# 18. JSP 的生命周期是什么？

JSP 具有以下生命周期阶段：

- 1. 编译：当对 JSP 发起请求时，对应的 JSP 会转换为 Servlet 并编译。如果已经存在编译后的 JSP ，且自上次编译以来 JSP 页面没有变化，则此阶段不会执行任何操作。

- 2. 初始化：在此阶段，调用 `jspInit()` 方法来初始化稍后在 `_jspService()` 方法中多次使用的数据或代码。

- 3. 服务：在此阶段，每次对 JSP 的请求，都会调用 `_jspService()` 方法来处理该请求。这是 JSP 的核心逻辑，用于为请求生成响应。

- 4. 销毁：在此阶段，JSP 会从容器/服务器中移除。在移除之前，此阶段会执行 JSP 持有的任何资源的的清理工作。

### 19. 什么是 JSP 表达式（expression）？

JSP 表达式是 JSP 页面中的一个元素，用于评估 Java 表达式并将其转换为字符串。该字符串会被替换到 JSP 页面中表达式出现的所有位置。

例如：`<%= expression%>`

# 20. JSP 中get不同类型的指令标签（directive tags）？

JSP 具有以下指令标签：

- 1. **Page**：此指令用于与页面相关的属性。它可以放在 JSP 页面的任何位置。但按照惯例，我们可以将其放在页面顶部。

例如：`<%@ page attribute="value" %>`

- 2. **Taglib**：我们可以在 JSP 中创建自定义标签，并在 JSP 页面通过 `taglib` 指令使用这些标签。

例如：`<%@ taglib uri="abc.html" prefix="tag_prefix" >`

- 3. **Include**：我们使用 `include` 指令来读取文件并将其内容与 JSP 页面合并。这是在编译阶段完成的。

```
<%@ include file="relative url" >
```

### 21. JSP 中的 session 属性（session attribute）是什么？

JSP 中的 session 属性用于 HTTP 会话机制。如果我们不想在 JSP 中使用 HTTP 会话，则将此属性设置为 `false`。如果设置为 `true`，我们可以在 JSP 中使用内置的 session 对象。

### 22. JSP 对象的不同作用范围（scopes）有哪些？

JSP 对象（无论是隐式的还是显式的）可以具有以下范围之一：

- 1. Page（页面）：在此范围内，对象可以在创建它的页面中被访问。这里的关键点是，当用户刷新页面时，此范围的对象也会被重新创建。

- 2. Request（请求）：在 request 范围内，对象可以被创建该对象的 HTTP 请求访问。

- 3. Session（会话）：在此范围内，对象在整个同一个 HTTP 会话中都可用。

- 4. Application（应用）：这是最广泛的范围。对象在创建 JSP 的整个应用程序中都可用。

### 23. JSP 中的 pageContext 是什么？

在 JSP 中，`pageContext` 是一个隐式对象。它用于存储和访问 JSP 的所有页面范围对象。

它是 `pageContext` 包中 `PageContext` 类的实例。

### 24. jsp:Bean 在 JSP 中的作用是什么？

我们使用 `jsp:Bean` 来创建 JavaBean 的实例。它允许我们在 JSP 页面与 JavaBeans 交互。我们可以用它来设置和获取 bean 的属性。

# 25. include 指令（Directive）和 Action（动作）之间的区别是什么？

include 指令和 Action 之间的一些主要区别如下：

- 1. include 指令在翻译阶段被调用。Action 在运行时执行。

- 2. 无法向 include 指令传递参数。Action 可以通过 `jsp:param` 接收参数。

- 3. include 指令是将内容拷贝到 JSP。Action 会动态处理调用的资源。

### 26. 如何在 JSP 中使用 Java 文件？

我们使用 `import` 标签在 JSP 中导入文件。一旦导入就可以可以使用。这是在 JSP 中使用 Java 类的方便方法。

# 27. 如何在 JSP 中使用继承？

我们可以在页面指令中使用 `extends` 属性来使用现有的基类。

### 28. 为什么 _jspService 方法以下划线开头？

我们在 JSP 中编写的所有代码都会在翻译阶段进入 `_jspService` 方法。我们无法重写该方法。而其他的生命周期方法 `jspInit()` 和 `jspDestroy()` 是可以重写的。

看起来容器使用下划线是为了区分不能被客户端覆盖的方法。

### 29. 为什么要在 JSP 中使用标签库（tag library）？

有时我们想要创建一个带有自定义标签的 UI 框架。在这种情况下，taglib 是 JSP 的一个非常好的特性。通过 taglib 我们可以创建提供自定义功能的标签。

Taglib 也是与 UI 设计师通信的一种良好方式，他们可以在不了解代码实现细节的情况下在 HTML 中使用自定义标签。

taglib 的另一个优点是代码的可重用。这促进了一次编写、多次使用。

# 30. JSTL 中不同的标签库组类型是什么？

JSTL 代表页面标准标签库。在 JSTL 中，我们有一组可以在不同场景下使用的 JSP 标签。JSTL 有以下主要的标签组：

- Core tags（核心标签）

- SQL tags

- Formatting tags（格式化标签）

- XML tags

- JSTL Functions（JSTL 函数）

### 31. 如何从一个 JSP 将信息传递到另一个 JSP？

我们可以通过隐式对象从一个 JSP 向另一个 JSP 传递信息。如果在同一个会话中了不同的 JSP，我们可以使用 session 对象从一个 JSP 传递到另一个。

如果我们想从一个 JSP 向包含在主 JSP 中的另一个 JSP 传递信息，那么可以使用 `jsp:param` 来传递这些信息。

### 32. 如何在 JSP 中调用存储过程？

JSP 允许从 .jsp 文件中运行 Java 代码。我们可以使用 JDBC 代码来调用存储过程。

我们可以从 JSP 代码中调用 `CallableStatement` 来执行存储过程。

如果我们正在使用 Spring 框架，我们可以使用 `JdbcTemplate` 类来从 JSP 中调用存储过程。

### 33. 可以在 JSP 中重写 _jspService() 方法吗？

不可以，JSP 规范不允许在 JSP 中重写 `_jspService` 方法。我们可以重写其他方法，如 `jspInit()` 和 `jspDestroy()`。

### 34. 什么是 JSP 指（directive）？

JSP 指令是一种向 JSP 容器传递消息的机制。JSP 指令不会向页面产生输出，但它与 JSP 容器通信。

例如，`<%@include` 指令用于告诉 JSP 容器在翻译 JSP 时包含另一个文件的内容。

指令可以包含零或多个属性，用于向 JSP 容器传递额外信息。

JSP 中重要的指令有：page、include 和 taglib。

### 35. 如何在 JSP 中实现会话跟踪（Session tracking）？

我们可以使用不同的机制来实现 JSP 会话跟踪。其中一些机制如下：

- 1. Cookies：我们可以使用 cookie 设置会话信息并传递给网络客户端。在随后的请求中，我们可以使用 cookie 中的信息来跟踪会话。

- 2. 隐藏表单字段（Hidden Form Field）：我们可以在 HTML 表单的隐藏字段中发送 session id。通过这种方式我们可以跟踪会话。

- 3. Session 对象：我们可以使用内置的 session 对象在 JSP 中跟踪会话。

- 4. URL 重写（URL Rewriting）：我们也可以在 URL 末尾添加 session id。

例如- www.abcserver.com?sessionid=1234

### 36. 如何在 JSP 中调试代码？

最简单的形式是我们可以编写日志语句或 `System.out.println()` 语句将消息写入日志文件。当我们调用 JSP 时，日志消息会被写入日志中。通过记录有用信息，我们可以轻松地调试代码。

调试的另一种选择是将 JSP 容器与 IDE 关联。一旦将 IDE 调试器链接到 JSP 引擎，我们就可以使用标准的调试操作，如断点、单步等。

### 37. 如何在 JSP 中实现错误页面？

为了在 JSP 中实现错误处理页面，我们首先创建一个带有错误页面处理信息的 JSP。在大多数情况下，我们通过提供用户友好的消息来优雅地处理错误，例如“抱歉！系统出现错误。请刷新页面重试。”

在这个错误页面中，我们向用户显示友好的消息，但也将重要信息（如堆栈跟踪 stack trace）记录到我们的应用程序日志文件中。

我们必须在该页面的 page 指令中添加参数 `isErrorPage=true`。这告诉 JSP 容器这是我们的错误页面。

```
<@page isErrorPage="true" %>
```

现在我们可以在其他需要处理错误的 JSP 中使用此错误页面。在发生错误或异常的情况下，这些 JSP 将将其重定向到 errorPage。

```jsp
<% page errorPage="errorPage.jsp" %>
```

### 38. 如何从 JSP 发送 XML 数据？

通常情况下，JSP 用于将 HTML 数据传递给网络浏览器。如果我们想以 XML 格式发送数据，可以通过在 page 指令中设置 `contentType="text/xml"` 轻松实现。

例如 <%@page contentType="text/xml" %>

# 39. 当我们从浏览器请求 JSP 页面时会发生什么？

当用户从浏览器调用 JSP 页面时，请求首先到达网络服务器。网络服务器检查页面的 `.jsp` 扩展名，并将请求传递给类似 Tomcat 的 JSP 容器。

JSP 容器检查它是否拥有预编译的 JSP 类。如果是第一次调用 JSP，则 JSP 容器将 JSP 翻译成一个 servlet 并进行编译。

编译后，如果 JSP 代码被加载到内存中，JSP 容器将调用 `jspInit()` 方法和 `_jspService()` 方法。

`_jspService()` 方法将创建将由 JSP 容器发送到客户端浏览器的输出。

### 40. 如何在 JSP 中实现页面自动刷新？

我们可以使用 `setIntHeader()` 方法设置我们想要自动刷新 JSP 页面的频率。

我们可以发送键名“Refresh”以及以秒为单位的时间来来实现 JSP 页面的自动刷新。

例如 `response.setIntHeader("Refresh”,10)`

### 41. HTTP 中重要的状态码有哪些？

每个 HTTP 请求都会从服务器返回一个状态码。

HTTP 中重要的状态码如下：

- 1. 200：意味着请求成功。

- 2. 400：意味着请求错误。

- 3. 401：意味着请求未获得授权。

- 4. 404：意味着未找到请求的资源。

- 5. 503：意味着服务不可用。

### 42. HTTP header 中 Accept 属性的含义？

在 HTTP header 中，Accept 属性用于指定 HTTP 客户端或浏览器可以处理的 MIME 类型。MIME 类型是用于指定我们计划通过互联网传递的文件/数据类型的的标识符。

### 43. Expression（表达式）和 Scriptlet（脚本段）之间有什么区别？

我们使用 Expression 返回值并显示它。Scriptlet 用于在 JSP 中编写 Java 代码。

### 44. 如何在 JSP 中删除 Cookie？



我们可以使用以下选项删除 Cookie：

- `setMaxAge()`：我们可以设置 cookie 的最大寿命。
- Header：我们还可以在响应中设置过期时间。

### 45. 如何在 JSP 中使用 Cookie？

我们可以通过以下步骤使用 Cookie：

首先创建一个 Cookie 对象。设置 cookie 的名称和值。通过 `setMaxAge()` 设置过期时间。最后，在 HTTP header 中发送 cookie。

一旦 Cookie 设置在浏览器中，我们可以调用 `getCookies()` 方法获取所有 cookie 列表以及之前设置的值。

### 46. Session 和 Cookie 的主要区别是什么？

Session 始终存储在服务端。在 JSP 中，session 是 JSP 容器的内置对象。

Cookie 始终存储在客户端。

我们可以使用两种方法进行会话跟踪。但 Cookie 方法需要许可在客户端位置存储 cookie。

### 47. 如何在 JSP 中防止创建 session？

我们只需在 page 指令中将 session 属性设置为 false 来防止 session 对象的创建。

```jsp
<% @page session="false" %>
```

### 48. 什么是 JSP 输出注释？

我们可以以某种方式在 JSP 中编写输出，使其成为 HTML 代码中的注释。此注释在网络浏览器中是不可见的。但当我们查看源代码查看 HTML 时，我们可以看到输出注释。

HTML 注释的格式如下：

```html
<!-- comment -->
```

如果我们按照上述格式输出注释，它将对客户端可见。

### 49. 如何在 JSP 中防止网络浏览器缓存 HTML 输出？

我们可以使用响应对象中的 `Cache-Control` header 来指定不缓存。

示例代码如下：

```java
response.setHeader("Cache-Control", "no-store");
response.setDateHeader("Expires", "0");
```

### 50. 如何在 JSP 代码中将请求重定向到另一个页面？

我们可以在 JSP 中使用 `sendRedirect()` 方法将请求重定向到另一个位置或页面。

在这种情况下请求不会返回服务器。它会在浏览器自身进行重定向。

示例代码如下：

```jsp
<% response.sendRedirect(URL); %>
```

### 51. JSP 中 sendRedirect 和 forward 的区别是什么？

forward 和 sendRedirect 都是将客户端发送到另一个页面的机制。它们之间的主要区别如下：

- 在 forward 中，处理发生在**服务端**。在 sendRedirect() 情况下，处理发生在客户端**。
- 在 forward 中，请求被传输到同一服务器内的另一个资源。在 sendRedirect 情况下，请求可以传输到其他服务器上的资源。
- 在 forward 中，只消耗一个请求调用。在 sendRedirect 情况下，会创建并消耗两次请求-响应调用。
- forward 声明在 `RequestDispatcher` 接口中。而 sendRedirect 声明在 `HttpServletResponse` 对象中。

### 52. JSP 中 config 隐式对象的作用是什么？

在 JSP 中，config 对象的类型是 `ServletConfig`。该对象由 Servlet 容器为每个每个 JSP 页面创建。它用于为特定的 JSP 页面设置初始化参数。

### 53. init-param 和 context-param 之间的区别是什么？

我们可以在 `web.xml` 文件中指定 `init-param` 和 `context-param`。

我们使用 `init-param` 来指定特定 servlet 或 jsp 的参数。这些信息被限于该 JSP 的作用范围。

我们使用 `context-param` 来指定整个应用范围的参数。这些信息不会轻易改变。它可以被该容器中的所有 JSP/Servlet 使用。

### 54. RequestDispatcher 的目的是什么？

我们使用 `RequestDispatcher` 接口将请求转发到 HTML、JSP 等其他资源。

它也可以用于在 JSP 中包含另一个页面的内容。

它有两个方法：`forward` 和 `include`。

我们必须先从容器获取 `RequestDispatcher` 对象，然后可以在该对象上调用 `include` 或 `forward` 方法。

- `getParameterMap()`：此方法返回表单中所有参数映射。

### 56. JSP 中的 filter（过滤器）是什么？

我们可以在 JSP 中定义过滤器来拦截来自客户端的请求或更改来自服务器的响应。

过滤器是一个 Java 类，定义在应用程序的 `web.xml` 部署符中。JSP 容器从 web.xml 读取过滤器，并根据过滤器关联的 URL 模式应用过滤器。

JSP 引擎在启动服务器时加载所有过滤器。

### 57. 如何在 JSP 中上传大文件？

要通过 JSP 上传文件，可以使用 HTML 传递的表单数据中的 `<input type="file">`。

如果文件很大，我们可以设置 `entype=multipart/form-data`。

我们必须在表单中使用 `POST` 方法来发送文件。

一旦接收到请求，我们可以在 JSP 的 `doPost()` 方法中实现读取多部分数据的逻辑。JSP 框架中存在方法可以通过此方法读取大文件。

### 58. 在什么情况下，容器会初始化多个 JSP/Servlet 对象？

为了初始化多个 JSP 对象，我们必须在 `web.xml` 中多次指定同一个 Servlet 对象。

这指示 JSP 容器为每个元素初始化独立的 JSP/Servlet 对象。每个 Servlet 实例将拥有它自己的 `ServletConfig` 对象和参数。

## Java 设计模式

### 59. 在 Java 中你何时会使用策略设计模式（Strategy Design Pattern）？

策略模式对于实现一组算法非常有用。它是一种行为级设计模式。

通过策略模式，我们可以在运行时选择算法。我们可以用它来选择数据的排序策略。我们可以用它以不同的格式保存文件，如 `.txt`、`.csv`、`.jpg` 等。

在策略模式中，我们创建一个抽象，客户端客户端与我们的系统交互的接口。在抽象之后，我们创建相同接口具有不同算法的多个实现。

对于客户端来说，在运行时我们可以根据收到的请求类型更改算法。

因此，我们使用策略模式向客户端隐藏算法的实现细节。

Java 的 `Collections.sort()` 方法使用了策略设计模式。

### 60. 什么是观察者模式（Observer design pattern）？

在观察者模式中，有一个主体（Subject），它维护一个观察者（Observers）列表，这些观察者正在等待主体的任何更新。一旦主体发生更新，它会通知所有观察者变化。

例如：在生活中，学生正在等待考试结果。这里学生是观察者，考试是主体。一旦考试结果公布，考试机构就会通知所有学生他们的结果。

观察者模式最流行的用法是在模型-视图控制器（MVC）架构模式。

观察者模式的主要问题是可能会导致内存泄漏。主体持有对观察者的强引用。如果观察者没有及时注销，可能会导致内存泄漏。

### 61. JDK 中观察者设计模式的示例有哪些？

在 JDK 中有很多地方使用了观察者设计模式。其中一些如下：

- `java.util.Observer`, `java.util.Observable`
- `javax.servlet.http.HttpSessionAttributeListener`
- `javax.servlet.http.HttpSessionBindingListener`
- `java.util.EventListener` 的所有实现，以及 Swing 包中
- `javax.faces.event.PhaseListener`

### 62. 策略设计模式与状态模式（State pattern）有什么区别？

状态模式是一种用于定义状态的行为模式。它允许对象在内部状态改变时改变其行为。该对象看起来改变了它的类。

策略模式是一种行为模式，允许你定义一组算法，封装每一个算法并使它们可以互换。策略模式允许算法独立于使用它的客户端发生变化。

策略和状态之间的主要区别是，在策略模式中，客户端通常知道使用哪种策略，而在状态模式中，状态本身通常处理到其他状态的转换。

### 63. 你能用 Java 示例解释装饰器模式（Decorator pattern）吗？

有些人也将装饰器模式称为包装模式（Wrapper pattern）。它被用于给对象添加行为，而不改变其他对象的行为。

装饰器模式的一个非常好的用法是在 `java.io` 包中。我们可以有一个 `FileInputStream` 来处理一个文件。为了添加缓冲行为，我们可以用 `BufferedInputStream` 装饰 `FileInputStream`。为了添加 gzip 行为，我们可以用 `GzipInputStream` 装饰 `BufferedInputStream`。为了给 `GzipInputStream` 添加序列化功能，我们可以用 `ObjectInputStream` 装饰它。

例如：

打开一个 FileInputStream：

`FileInputStream fis = new FileInputStream("/myfile.gz");`

添加缓冲：

`BufferedInputStream bis = new BufferedInputStream(fis);`

添加 Gzip：

`GzipInputStream gis = new GzipInputStream(bis);`

添加序列化：

`ObjectInputStream ois = new ObjectInputStream(gis);`

因此，通过每一步，我们都为 `FileInputStream` 装饰了额外的行为。

### 64. Java 中使用组合设计模式（Composite design Pattern）的良好场景是什么？

组合设计模式可以使用的一些良好场景如下：

- **树形结构**：组合设计模式最常用的用法是树形结构。如果你想在树形数据结构中表示数据，可以使用组合模式。

  例如：在组织中，一个经理有员工。但如果我们从 CEO 级别开始，整个组织结构就有一棵大树。在那棵大树下有许多子树。这可以通过组合模式轻松地表示。

- **递归**：组合模式的另一个用法是递归。如果我们有一个基于递归的算法，我们需要以数据结构传递数据，该结构在递归的每一层均匀地处理单个对象和组合。

  例如：为了实现一个递归的多项式求解算法，我们可以使用组合模式来存储中间结果。

- **图形**：组合设计模式的另一个良好用法是图形。我们可以将形状组合在一个组合中，并创建较小形状组合的高级组合，以完成显示在屏幕上的图形。

### 65. 你在 Java 项目中使用过单例设计模式（Singleton design pattern）吗？

这有助于在唯一的位置中存储应用程序中必须使用的属性。

### 66. 单例设计模式在 Java 项目中的主要用途是什么？

单例设计模式在 Java 中的一些主要用途如下：

- **运行时（Runtime）**：在 JDK 中，`java.lang.Runtime` 是一个基于单例的类。应用程序中只有一个 `Runtime` 实例。这是唯一与 Java 进程运行的环境/机器进行交互的类。
- **枚举（Enum）**：在 Java 中，枚举构造结构也是基于单例模式的。枚举值可以被所有类以相同的方式全局访问。
- **属性（Properties）**：在应用程序中，保留一份所有类都可以访问的属性副本是有意义的。可以通过将属性类设为单例来实现，以便每个类都获得相同的属性副本。
- **Spring**：在 Spring 框架中，所有的 bean 默认都是每个容器一个单例的。因此，一个 Spring IoC 容器中只有一个 bean 实例。但 Spring 也提供了选项来使 bean 在容器中的作用范围变为原型（prototype）。

### 67. 为什么 java.lang.Runtime 在 Java 中是单例？

在 Java 中，`java.lang.Runtime` 是基于单例设计模式实现的。

`Runtime` 是一个与 Java 进程运行的环境作为接口的类。`Runtime` 包含了可以与环境交互的方法。

例如，`totalMemory()` 方法给出 JVM 的总内存。`maxMemory()` 方法给出 JVM 使用的最大内存。

有一个 `exit()` 方法用于退出 Java 进程。我们不希望 JVM 中的多个对象都拥有 `exit()` 方法。

同样，还有一个 `gc()` 方法可以运行垃圾回收器（Garbage Collector）。通过只保留一份 `gc()` 方法副本，我们可以确保当一个 GC 实例正在运行时，没有其他对象可以运行垃圾回收器。

由于所有这些原因，Java 中只存在一个 `Runtime` 副本。为了确保 `Runtime` 的单份副本，它在 Java 中被实现为单例。

### 68. 在 Java 中实现线程安全的单例设计模式的方法是什么？

在 Java 中有许多选项可以实现线程安全的单例模式。其中一些如下：

- **双重检查锁定（Double Checked Locking）**：这是 Java 中实现单例最流行的方法。它基于懒加载初始化（Lazy Initialization）。在此处，我们在获取锁创建对象之前，首先检查锁的条件。在 Java 中我们使用 `volatile` 关键字。

  示例代码：

  ```java
  class DoubleCheckSingleton {
      private volatile HelloSingleton helloSingleton; // 使用 Volatile

      public HelloSingleton getSingleton() {
          HelloSingleton result = helloSingleton;
          if (result == null) {
              synchronized(this) { // 为了线程安全进行同步
                  result = helloSingleton;
                  if (result == null) {
                      result = new HelloSingleton();
                  }
              }
          }
          return result;
      }
  }
  ```

- **Bill Pugh 单例**：我们也可以使用 Bill Pugh 的方法在 Java 中实现单例。在这里我们使用一个内部静态类（Inner Static class）来创建单例实例。

  示例代码：

  ```java
  public class SingletonBillPugh {

      // 持有实例的内部类
      private static class InnerSingleton{
          private static final SingletonBillPugh INSTANCE = new SingletonBillPugh();
      }

      // 私有构造函数
      private SingletonBillPugh(){}

      public static SingletonBillPugh getInstance(){
          return InnerSingleton.INSTANCE;
      }
  }
  ```

  当 `SingletonBillPugh` 第一次加载到内存时，`InnerSingleton` 不会被加载。只有当调用 `getInstance()` 方法时，`InnerSingleton` 类才会被加载并创建一个实例。

- **枚举（Enum）**：我们也可以使用 Java enum 创建线程安全的实现。Java 枚举值是可以全局访问的，因此它们可以作为单例使用。

  示例代码：

  ```java
  public enum SingletonEnum {

      INSTANCE;

      public static void doImplementation(){
          ....
      }
  }
  ```

### 69. JDK 中单例设计模式的示例有哪些？

在 JDK 中有很多地方使用了单例设计模式。其中一些如下：

- `java.lang.Runtime.getRuntime()`：此方法返回 `Runtime` 类，该类在 JVM 中只有一个实例。
- `java.lang.System.getSecurityManager()`：此方法为当前平台返回一个 SecurityManager。
- `java.awt.Desktop.getDesktop()`

### 70. Java 中的模板方法模式（Template Method design pattern）是什么？

它是一种行为设计模式。我们可以用它为算法或复杂操作创建一个大纲。我们首先创建程序的骨架，然后将操作的步骤委托给子类。子类可以重新定义每个步骤的内部实现。

例如，在 Java 中设计一个游戏时，我们可以使用模板方法模式将其实现为算法。游戏中的每一步都可以推给负责处理该步骤的子类。

假设我们在 Java 中实现大富翁游戏（Monopoly）。我们可以创建如 `initializeGame()`、`makeMove()`、`endGame()` 等方法。这些每个方法都可以在子类中以独立的方式处理。



我们可以使用相同的一组抽象方法为象棋游戏使用相同的算法。象棋游戏的子类可以提供如 `initializeGame()`、`makeMove()`、`endGame()` 等方法的具体实现。

模板方法模式在为用户提供可定制类方面非常有用。我们可以创建一个具有高级实现的核心类。用户可以在自定义的子类中对我们的核心类进行定制。

## 71. JDK 中模板方法设计模式的示例有哪些？

在 JDK 中有很多地方使用了模板方法设计模式。其中一些如下：

1. 在 Java 抽象集合类如 `java.util.AbstractList`、`java.util.AbstractSet` 和 `java.util.AbstractMap` 中实现了它们对应的集合。
2. `javax.servlet.HttpServlet`：在 `HttpServlet` 类中，所有的 `doGet()`、`doPost()` 方法都会发送 HTTP 405 "Method Not Allowed" 错误。这种响应是可以进一步定制的模板。
3. 在 `java.io` 包中有流和器类如 `java.io.InputStream`、`java.io.OutputStream`、`java.io.Reader` 和 `java.io.Writer` 提供非抽象方法。这些方法是模板方法的实现。

## 72. 能否提供 Java 中工厂方法设计模式的实现示例？

工厂方法模式是一种创建设计模式。工厂是一个用于创建更多对象的对象。通常，工厂对象拥有用于创建类型对象的方法。有些人也将其称为工厂方法模式。

JDK 中工厂方法模式的一些示例是：

- `java.lang.Class.forName()`
- `java.net.URLStreamFactory.createURLStreamHandler()`
- `java.util.Calendar.getInstance()`
- `java.util.ResourceBundle.getBundle()`
- `java.text.NumberFormat.getInstance()`
- `java.nio.charset.Charset.forName()`
- `java.util.EnumSet.of()`
- `javax.xml.bind.JAXBContext.createMarshaller()`

## 73. 使用静态工厂方法创建对象有什么好处？

通过使用静态工厂方法，我们封装了对象的创建过程。可以使用 `new()` 从构造函数创建对象。相反，我们使用工厂的静态方法来创建对象。使用工厂的主要优势是工厂可以在运行时选择正确的实现并创建正确的对象。方法的调用者可以指定期望的行为。

例如，如果我们有一个带有 `createShape(String type)` 方法的 `ShapeFactory`。客户端可以调用 `ShapeFactory.createShape("Circle")` 来获取圆形。`ShapeFactory.createShape("Square")` 将返回正方形。工厂知道根据调用者的输入创建不同的形状。

工厂的另一个用途是为大量用户提供有限资源的访问。

例如，在连接池（`ConnectionPool`）中，我们可以限制可以创建的连接总数，同时隐藏创建连接的实现细节。这里连接池就是工厂。客户端调用静态方法 `ConnectionPool.getConnection()`。

## 74. JDK 中构建器模式（Builder design pattern）的示例有哪些？

在 JDK 中，有很多地方使用了构建器模式。其中一些如下：

1. `java.lang.StringBuilder.append()`: `StringBuilder` 基于构建器模式。
2. `java.nio.IntBuffer.put()`: 调用 `put()` 方法返回 `IntBuffer`。该方法还有许多变体用于构建 `IntBuffer`。
3. `javax.swing.GroupLayout.Group.addComponent()`: 我们可以使用 `addComponent()` 方法构建包含多个层级组件的 UI。
4. `java.lang.Appendable`
5. `java.lang.StringBuilder.append()`: `StringBuffer` 与 `StringBuilder` 类似，它也基于构建器模式。

## 75. JDK 中抽象工厂模式（Abstract Factory design pattern）的示例有哪些？

在 JDK 中，有很多地方使用了抽象工厂模式。其中一些如下：

- `javax.xml.xpath.XPathFactory.newInstance()`
- `javax.xml.parsers.DocumentBuilderFactory.newInstance()`
- `javax.xml.transform.TransformerFactory.newInstance()`

## 76. JDK 中装饰器模式（Decorator design pattern）的示例有哪些？

在 JDK 中，有很多地方使用了装饰器模式。其中一些如下：

1. 在 `java.io` 包中，许多类使用了装饰器模式。`java.io.InputStream`、`OutputStream`、`Reader` 和 `Writer` 的子类都有一个构造函数，可以接收相同类型的实例并装饰额外的行为。
2. 在 `java.util.Collections` 中，有如 `checkedCollection()`、`checkedList()`、`checkedMap()`、`synchronizedList()`、`synchronizedMap()`、`synchronizedSet()`、`unmodifiableSet()`、`unmodifiableMap()` 和 `unmodifiableList()` 等方法，可以装饰对象并返回相同类型。
3. 在 `javax.servlet` 包中，有如 `javax.servlet.http.HttpServletWrapper` 和 `HttpServletResponseWrapper` 等基于装饰器模式的类。

## 77. JDK 中代理模式（Proxy design pattern）的示例有哪些？

代理模式为访问另一个对象提供了一个额外的间接层。它还可以保护真实对象免受额外复杂性的影响。

在 JDK 中，有很多地方使用了代理模式。其中一些如下：

- `java.lang.reflect.Proxy`
- `java.rmi.*`
- `javax.inject.Inject`
- `javax.ejb.EJB`
- `javax.persistence.PersistenceContext`

## 78. JDK 中责任链模式（Chain of Responsibility design pattern）的示例有哪些？

在 JDK 中，有很多地方使用了责任链模式。其中一些如下：

1. `java.util.logging.Logger.log()`: 在这种情况下，`Logger` 类提供了 `log()` 方法的多种变体，可以在不同场景下承担客户端的日志记录责任。客户端只需调用合适的 `log()` 方法，`Logger` 就会处理这些命令。
2. `javax.servlet.Filter.doFilter()`: 在 `Filter` 类中，当一个请求/响应对通过过滤器链时，容器（`Container`）会调用 `doFilter` 方法。通过过滤器，请求到达链的末尾的适当资源。我们可以在 `doFilter()` 方法中传递 `FilterChain`，允许过滤器将请求和响应传递给链中的下一层。

## 79. 命令模式（Command design pattern）的主要用途有哪些？

命令模式是一种行为级设计模式。我们用它来封装触发事件所需的所有信息。命令模式的一些主要用途包括：

- 图形用户界面（GUI）：在 GUI 和菜单项中，我们使用命令模式。通过点击按钮，我们可以读取 GUI 的当前信息并采取操作。
- 宏录制：如果每个用户操作都实现为一个独立的命令（`Command`），我们就可以将整个宏录制为一系列命令。我们可以使用这一系列来实现“回放”功能。通过这种方式，宏可以在每次重放时执行同一组动作。
- 多步撤销（Undo）：当每一步都被记录为一个命令时，我们可以使用它来实现撤销功能，其中每一步都可以被撤销。它被用于 MS-Word 等文本编辑器。
- 网络：我们还可以通过网络向远程机器发送一个完整的命令，在远程机器上执行命令中封装的所有操作。
- 进度条：我们可以将一个安装程序实现为一系列命令。每个命令提供预估时间。当我们执行安装程序时，通过每个命令可以显示进度条。
- 向导（Wizard）：在向导流中，我们可以将步骤实现为命令。每个步骤可能包含一个复杂的任务，该任务仅实现在一个命令中。
- 事务：在事务行为代码中有多个任务/更新。只有当所有任务完成后，才会提交事务。否则，我们必须回滚事务。在这种情况下，每一步都实现为独立的命令。

## 80. JDK 中命令模式（Command design pattern）的示例有哪些？

在 JDK 中，有很多地方使用了命令模式。其中一些如下：

- 所有 `java.lang.Runnable` 的实现
- 所有 `javax.swing.Action` 的实现

## 81. JDK 中解释器模式（Interpreter design pattern）的示例有哪些？

解释器模式用于评估语言中的句子。例如，在 SQL 中，我们可以通过评估每个关键字（如 `SELECT`、`FROM`、`WHERE` 子句）来评估查询。

在解释器的实现中有一个可以被解释的句子。在 JDK 中，有很多地方使用了解释器模式。其中一些如下：

- `java.util.Pattern`
- `java.text.Format`: `DateFormat`, `MessageFormat`, `NumberFormat`
- `javax.el.ELResolver`: `ArrayResolver`, `MapResolver`, `CompositeResolver`

## 82. JDK 中中者模式（Mediator design pattern）的示例有哪些？

通过使用中者模式，我们可以解耦多个对象。在 JDK 中，有很多地方使用了中者模式。其中一些如下：

- `java.util.Timer`：这里的 `schedule()` 方法及其变体是中者的实现。
- `java.util.concurrent.Executor.execute()`: `execute` 方法处理不同的任务。
- `java.util.concurrent.ExecutorService`
- `java.lang.reflect.Method.invoke()`: 在反射的 `Method` 类中，`invoke()` 方法充当中者。
- `java.util.concurrent.ScheduledExecutorService`

## 83. JDK 中策略模式（Strategy design pattern）的示例有哪些？

在 JDK 中，有很多地方使用了策略模式。其中一些如下：

1. `java.util.Comparator`：在 `Comparator` 中，我们可以使用 `compare()` 方法来改变 `Collections.sort()` 使用的策略。
2. `javax.servlet.http.HttpServlet`：在 `HttpServlet` 类中，`service()` 和 `doGet()` 等方法接收 `HttpServletRequest` 和 `HttpServletResponse`，实现根据选择的策略进行处理。

## 84. JDK 中访问者模式（Visitor design pattern）的示例有哪些？

通过使用访问者模式，我们可以在不修改现有类核心结构的情况下为它们添加新的虚拟方法。在 JDK 中，有很多地方使用了访问者模式。其中一些如下：

- `javax.lang.model.element.AnnotationValue` and `AnnotationValueVisitor`
- `java.nio.file.FileVisitor` and `SimpleFileVisitor`
- `javax.lang.model.type.TypeMirror` and `TypeVisitor`
- `javax.lang.model.element.Element` and `ElementVisitor`
- `javax.faces.component.visit.VisitContext` and `VisitCallback`

## 86. 在依赖注入（DI）设计模式中，使用 Setter 注入和构造函数注入的不同场景有哪些？

我们使用 Setter 注入来提供对象的可选依赖。构造函数注入则用于提供对象的强制性依赖。

在 Spring IoC 中，依赖注入被广泛使用。必须区分适用于 Setter 这种依赖注入和适用于构造函数的依赖注入的场景。

## 87. 使用代理（Proxy）设计模式的不同场景有哪些？

代理设计模式在 Java 中可以用于广泛的场景。其中一些包括：

1. 虚拟代理（Virtual Proxy）：这是一个虚拟对象，作为创建开销极昂的对象的代理。它被用于懒性加载（Lazy Loading）。当客户端发出首次请求时，会创建真实对象。
2. 远程代理（Remote Proxy）：这是一个提供访问远程对象接口的本地对象。它通常用于远程方法调用（RMI）和远程过程调用（RPC）。它也被称为存根（Stub）。
3. 保护代理（Protective Proxy）：这是一个控制对主对象（Master object）访问的对象。它可以对客户端访问主对象进行身份验证和授权。如果客户端拥有相应权限，它将允许客户端访问主对象。
4. 智能代理（Smart Proxy）：它可以为主对象添加额外信息的对象。它可以跟踪其他对象访问主对象的数量。它可以跟踪请求来源的不同客户端。如果请求数量超过阈值，它甚至可以拒绝对象的访问。

## 88. 适配器（Adapter）和代理（Proxy）设计模式的主要区别是什么？

适配器模式为对象提供不同的接口。但代理始终为对象提供相同的接口。

适配器就像提供一个适用于客户端使用的接口。而代理是具有额外功能或检查机制的相同接口。

例如：在电器设备中，我们使用适配器将一种类型的插座转换为另一种类型的插座。在代理案例中，我们有一个带有内置浪涌保护器的插头。插头和原始设备的接口保持不变。

## 89. 在 Java 中你何时会使用适配器设计模式？

如果我们有两个接口不兼容的类，我们使用适配器模式来让它们协同工作。我们创建一个适配器对象，它可以将一个类的接口适配到另一个类。

它通常用于与第三方库一起工作。我们在第三方代码和我们的类之间创建一个适配器类。如果第三方代码发生任何变化，我们只需要更改适配器代码。我们的其他代码可以保持不变，只需调用适配器即可。

## 90. JDK 中适配器设计模式的示例有哪些？

在 JDK 中，有很多地方使用了适配器设计模式。其中一些包括：

- `java.util.Arrays.asList()`: 此方法可以将数组（`Array`）适配为 `List` 以使用。
- `java.util.Collections.list()`: 此方法可以将任何集合（`collection`）适配以提供 `List` 行为。
- `java.util.Collections.enumeration()`: 此方法返回一个集合的枚举器（`enumeration`）。
- `java.io.InputStreamReader(InputStream)`: 此方法将 `Stream` 适配为 `Reader` 类。
- `java.io.OutputStreamWriter(OutputStream)`: 此方法将 `OutputStream` 适配为 `Writer` 类。
- `javax.xml.bind.annotation.adapters.XmlAdapter.marshal()`

## 91. 工厂（Factory）和抽象工厂（Abstract Factory）设计模式的区别是什么？

通过工厂模式，我们可以创建工厂制造的某种类型的具体产品。例如：如果是汽车工厂（`CarFactory`），我们可以生产福特、丰田、本田、玛莎蒂等。

通过抽象工厂模式，我们创建一个工厂的具体实现。例如：设备工厂（`DeviceFactory`）可以是抽象的，通过苹果设备工厂（`AppleDeviceFactory`），我们将得到 iPhone、iPad、Mac 等产品。通过谷歌设备工厂（`GoogleDeviceFactory`），我们将得到 Nexus 手机、Google 平板、Google ChromeBook 等产品。

因此，工厂模式和抽象工厂模式之间存在微妙的区别。记住它们的一种方法是：在抽象工厂模式内部，工厂模式已经被已经了。

## 92. 软件工程中的开闭原则（Open/closed design principle）是什么？

开闭原则规定：“软件实体（类、模块、函数等）应该对扩展开放，对修改关闭”。

“开闭原则”这一术语由 Bertrand Meyer 在他的书《面向对象软件构造》中提出。

根据这一原则，如果一个模块是可以用于扩展的，那么它被认为是开放的。如果一个模块是供其他模块调用的，那么它被认为是关闭的。

进一步地，Robert C. Martin 将其称为面向对象设计 SOLID 原则中的 O。

它被用于状态（`State`）和策略（`Strategy`）设计模式。上下文类（`Context class`）对修改关闭。但可以通过编写新的策略代码来添加新功能。

### 93. 什么是 SOLID 设计原则？

SOLID 设计原则中的 SOLID 单词是以下内容的的缩写：

1. S: 单责任原则（Single responsibility）。一个类应该有一个职责。
2. O: 开闭原则（Open-closed）。软件实体应该对扩展开放，对修改关闭。
3. L: 列表氏替换原则（Liskov substitution）。程序中的对象应该被相同类型的子类替换，而不会产生任何不利影响。



### 4. I: 接口隔离（Interface segregation）
多个特定于客户端的接口比单一通用接口更好。

### 5. D: 依赖倒置（Dependency inversion）
程序应该依赖于抽象实体，不应该依赖于接口的具体实现。

这一原则由 `Robert C. Martin` 提出。它们被认为是面向对象设计的五个基本原则。

如果我们遵循这些原则，就可以创建一个稳定的程序。

构建器模式（Builder pattern）的主要特征是分步构建具有多个选项的复杂对象。

### 95. 面向对象中设计模式有哪些分类？

在面向对象设计中，主要使用三类设计模式。它们是：

#### 创建型设计模式（Creational Design Patterns）
- 构建器（Builder）
- 工厂方法（Factory Method）
- 抽象工厂（Abstract Factory）
- 对象池（Object Pool）
- 单例（Singleton）
- 原型（Prototype）

#### 结构型设计模式（Structural Design Patterns）
- 适配器（Adapter）
- 桥接（Bridge）
- 外观（Facade）
- 装饰器（Decorator）
- 组合（Composite）
- 享元（Flyweight）
- 代理（Proxy）

#### 行为型设计模式（Behavioral Design Patterns）
- 命令（Command）
- 迭代器（Iterator）
- 责任链（Chain of Responsibility）
- 观察者（Observer）
- 状态（State）
- 策略（Strategy）
- 中介者（Mediator）
- 解释器（Interpreter）

### 96. 访问集合元素的设计模式是什么？

我们可以使用`Iterator`（迭代器）设计模式来访问集合的元素。对于有序集合，我们可以获取一个按顺序返回元素的迭代器。

在 Java 中，`Collections` 包中有很多迭代器的实现。我们有像 `Iterator`、`ListIterator` 等实现迭代器模式的类。

### 97. 如何在 Java 中实现生产者-消费者（Producer Consumer）设计模式？

我们可以使用 Java 中的 `BlockingQueue`（阻塞队列）来实现生产者-消费者模式。这是一种并发设计模式。

### 98. 什么设计模式适用于为现有对象添加新功能？

我们可以使用 `Decorator`（装饰器）设计模式为现有对象添加新功能。通过装饰器，我们对相同对象进行操作并返回具有更多功能的对象。但由于所有装饰版本都实现相同的接口，对象的结构保持不变。

### 100. Android 应用中使用了什么设计模式？

Android 应用主要使用 `Model View Presenter`（模型-视图-演示器）设计模式。

1. **Model（模型）**：这是 Android 应用的领域模型。它包含了业务逻辑和业务规则。
2. **View（视图）**：这些是应用程序中的 UI 组件。它们是视图的一部分。此外，UI 组件上的任何事件都属于视图模块的一部分。
3. **Presenter（演示器）**：这是 Model 和 View 之间的桥梁，用于控制通信。`Presenter` 可以查询模型并将数据返回给视图以进行更新。
4. **例如**：如果我们有一个包含大量新闻文章数据的 Model，而 view 只需要标题，那么 presenter 可以从 model 中查询数据并只给 view 提供标题。通过这种方式，在该设计模式下 view 保持得非常轻量。

### 101. 如何通过使用 `clone()` 方法防止用户创建多一个单例对象的实例？

首先，我们不应该让单例对象实现 `Cloneable` 接口。

其次，如果我们必须实现 `Cloneable` 接口，那么我们可以在 `clone()` 方法中抛出异常。

这将确保没有人可以使用 `clone()` 方法或 `Cloneable` 接口创建多一个单例对象的实例。

### 102. 拦截器（Interceptor）设计模式的作用是什么？

拦截器设计模式用于拦截请求。该模式的主要用途是在安全策略的实现中。

我们可以使用该模式来拦截客户端对资源的请求。在拦截时，我们可以对客户端对所访问资源进行身份验证和授权。

在 Java 中，它被用于 `javax.servlet.Filter` 接口中。

该模式也用于 Spring 框架中的 `HandlerInterceptor` 和 MVC 拦截器。

### 103. 你使用过哪些架构模式？

架构模式用于定义软件系统的架构。其中一些模式如下：

1. **MVC：Model View Controller（模型-视图-控制器）**。这种模式在 Spring 框架的架构中被广泛使用。
2. **发布-订阅（Publish-subscribe）**：这种模式是消息架构的基础。在这种情况下，消息被发布到一个 `Topic`（主题）中。订阅者订阅他们感兴趣的主题。一旦消息发布到订阅者感兴趣的 `Topic`，消息就会被相关的订阅者消费。
3. **服务定位器（Service Locator）**：这种设计模式用于像 `JNDI` 这样的服务定位可用服务。它使用中心注册表来维护服务列表。
4. **n 层架构（n-Tier）**：这是一种将架构划分为多个层的通用设计模式。例如，存在具有表现层、应用层和数据访问层的 3 层架构。它也被称为多层设计模式。
5. **数据访问对象（DAO）**：这种模式用于提供对数据库对象的访问。其底层原理是我们可以在不改变业务逻辑的情况下更改底层的数据库系统。由于业务逻辑与 `DAO` 对象通信，因此更改数据库系统对业务逻辑没有影响。
6. **控制反转（IoC）**：这是 Spring 框架中依赖注入（Dependency Injection）的核心。我们使用这种设计模式来增加应用程序的模块化程度。我们通过依赖注入保持对象之间的松耦合。

### 104. 外观（Facade）设计模式的常用用途有哪些？

外观设计模式的某些常用用途如下：

1. 外观模式为经常使用的常用任务提供方便的方法。
2. 外观模式可以让软件库更具可读性。
3. 外观模式可以减少对内部代码运行的外部依赖。
4. 外观模式可以通过封装一组设计得差的 API 来充当单一的设计良好的 API。
5. 当系统非常复杂且难以使用时，可以使用外观模式。它可以简化复杂系统的使用。

### 105. 构建者（Builder）设计模式和工厂（Factory）设计模式之间的区别是什么？

工厂和构建者模式都是创建型设计模式。它们在性质上是相似的，但工厂模式是构建者模式的简化通用版本。

我们使用工厂模式来创建对象的不同具体子类型。工厂的客户端可能不知道具体的子类型。例如，如果我们调用工厂的 `createDrink()`，我们可能会得到茶或咖啡饮料。

我们也可以使用构建者模式来创建对象的不同具体子类型。但在构建者模式中，对象的组合可以更复杂。例如，如果我们为构建者调用 `createDrink()`，我们可以得到带有香草奶油和糖的卡布奇诺咖啡，或者得到带有甜菊糖和牛奶奶油的拿铁咖啡。

因此，构建者可以支持对象大量变体的创建。但工厂可以创建对象更广泛的已知子类型。

### 106. 什么是备忘录（Memento）设计模式？

备忘录设计模式用于在对象实现撤销功能。在备忘录模式中有三个对象：

- **源发器（Originator）**：这是拥有内部状态的对象。
- **管理者（Caretaker）**：这是可以更改源发器状态的对象。但它希望控制回滚更改。
- **备忘录（Memento）**：这是管理者在做出任何更改之前从源发器获取的对象。如果管理者想要回滚更改，它会将备忘录交回源发器。源发器可以使用备忘录将其自己的状态恢复到原始状态。

**例如**：备忘录的一个好用例是在线表单。如果我们想向用户显示一个预填充了某些数据的表单，我们将此副本保存在备忘录中。现在用户可以更新表单。但如果用户随时想重置表单，我们使用备忘录使表单恢复原始状态。如果用户只想保存表单，我们保存表单并更新备忘录。从现在起表单的任何更改都可以回滚到上次的备忘录。

### 107. 什么是反模式（AntiPattern）？

反模式是设计模式的反面。它是组织中一种常见的做法，用于解决反复出现的问题，但其负面影响大于好处。

反模式可以在组织、架构或软件工程中找到。

软件工程中的反模式包括：

1. **镀金（Gold Plating）**：在工作的解决方案上不断添加功能，尽管这些额外功能没有任何价值。
2. **面条代码（Spaghetti Code）**：由于误用数据结构导致编写复杂且难以理解的代码。
3. **异常驱动编码（Coding By Exception）**：为了处理异常情况和边界场景而添加新代码。
4. **复制粘贴编程（Copy Paste Programming）**：多次复制相同的代码，而不是编写可以参数化的通用代码。

### 108. 什么是数据访问对象（DAO）设计模式？

`DAO` 设计模式用于 Java 应用程序的数据持久层。它主要使用面向对象的封装原则。

通过使用 `DAO` 模式，可以使应用程序松耦合并减少对实际数据库的依赖。

我们可以使用 `DAO` 实现一些内存数据库（如 `H2`）来处理单元测试。

简单来说，`DAO` 隐藏了通过 `DAO` 对象访问数据的底层数据库实现。

最近我们可以将 `DAO` 与 Spring 框架结合以注入任何数据库实现。

## Spring

### 109. 什么是 Spring 框架？

Spring 是 Java 编程的开发框架。它是用于企业级 Java 的开源开发框架。

Spring 框架的核心功能可以用于开发 Java 企业应用程序。

它有许多扩展和 jar 包用于在 Java EE 平台之上开发 Web 应用程序。

通过 Spring 我们可以轻松地开发大型复杂的 Java 应用程序。它基于良好的设计模式，如依赖注入、面向切面编程，以开发可扩展且功能丰富的软件。

### 110. Spring 框架在软件开发中有什么好处？

Spring 框架有很多优点：

- **轻量级框架**：基础 Spring 框架的体积非常小。它易于使用，且不会给软件带来过多开销。基础版本仅占 2 MB。
- **容器**：Spring 框架提供了基础容器，用于创建和管理应用对象（如普通 Java 对象 `POJO`）的生命周期。它还存储了待创建的应用对象的配置。
- **依赖注入 (DI)**：Spring 通过依赖注入提供了松耦合。它使用了控制反转（`IOC`）技术，通过这种技术向 Spring 指明对象的依赖关系，而不是自己创建新对象。
- **面向切面编程 (AOP)**：Spring 框架促进并为 Java 中的面向切面编程提供了支持。这有助于将应用程序业务逻辑与所有业务逻辑中通用的系统服务分离。例如，日志记录可以是应用程序中的横切关注点。
- **事务管理**：Spring 提供了一个事务管理框架。因此，开发者不需要从零开始实现。Spring 事务管理非常强大，我们可以将其从一个本地事务扩展到集群中的全局事务。
- **MVC 框架**：对于 Web 应用程序，Spring 提供了 MVC 框架。该框架基于 MVC 设计模式，与其他 Web 框架相比具有更好的特性。
- **异常处理**：Spring 还支持一个通用 API，用于处理如 `Hibernate`、`JDBC` 等各种技术中的异常。

### 111. Spring 框架的核心容器（Core Container）包含哪些模块？

Spring 框架有一个核心容器。核心容器中的模块有：

- `Core` 模块
- `Bean` 模块
- `Context` 模块
- `Spring Expression Language`（Spring 表达式语言）模块

### 112. Spring 框架数据访问/集成层包含哪些模块？

Spring 框架数据访问/集成层的模块：

- `JDBC` 模块：一个消除冗长 `JDBC` 编码的抽象层。
- `ORM` 模块：用于对象关系映射的集成层。
- `OXM` 模块：支持对象 XML 映射的抽象层。
- `Java Message Service (JMS)` 模块：用于生产和消费消息的模块。
- `Transactions`（事务）：针对 `POJO` 类的事务管理。

### 113. Spring 框架 Web 层包含哪些模块？

Spring 框架 Web 层模块有：

- `Web` 模块：提供基本的面向 Web 的集成功能。
    - `Servlet` 模块：支持 `Servlet` 监听器。
    - `WebSocket` 模块：支持 `WebSocket` 风格的通信。
    - `Portlet` 模块：`Portlet` 环境的 MVC 实现。

### 114. Spring 框架中核心容器（Core Container）模块的主要用途是什么？

如名所示，Spring Core Container 是 Spring 框架的核心。它提供了 Spring 的基本功能。Spring 框架的所有部分都是构建在核心容器之上。

它的主要用途是提供依赖注入 (`DI`) 和控制反转 (`IOC`) 功能。

### 115. Spring Test 模块中可以进行什么测试？

`Spring Test` 模块提供对 Spring 组件的单元测试以及集成测试的支持。它允许使用 `JUnit` 或 `TestNG` 测试框架。它还提供了模拟对象以供测试代码使用。

### 116. Spring 框架中 BeanFactory 的作用是什么？

`BeanFactory` 是帮助在 Spring 中实现控制反转模式的主要类。它基于工厂设计模式。它将应用程序的配置和依赖与应用程序的其他代码分离。

使用 Spring 构建的应用程序会使用像 `XmlBeanFactory` 类这样的 `BeanFactory` 实现。

### 117. 哪个是 Spring 中 BeanFactory 最流行的实现？

`XmlBeanFactory` 是 Spring 中 `BeanFactory` 最流行的实现。

### 118. Spring 框架中的 XMLBeanFactory 是什么？

`XmlBeanFactory` 是 Spring 中 `BeanFactory` 最实用的实现之一。该工厂根据 XML 文件中提到的定义来加载其 bean。

Spring 容器从 XML 文件读取 bean 配置元数据，并借助 `XmlBeanFactory` 类创建一个完全配置的应用程序。

### 119. Spring 框架中 AOP 模块的用途是什么？

`AOP` 模块也称为面向切面编程模块。它的用途是：

- 在基于 Spring 的应用程序中开发切面
- 提供 Spring 与其他 AOP 框架之间的互操作性
- 为 Spring 支持元数据编程

### 120. Spring 框架中 JDBC 抽象层模块有什么好处？

Spring `JDBC` 抽象层模块。该模块的主要优点是：

- 有助于保持数据库代码整洁简单。
- 防止因未关闭数据库资源而导致的问题。
- 在不同数据库服务器提供的错误信息之上提供一层有用的异常。
- 基于 Spring 的 `AOP` 模块
- 为 Spring 应用程序中的对象提供事务管理服务。

### 121. Spring 如何支持对象关系映射 (ORM) 集成？

Spring 通过提供 `ORM` 模块来支持对象关系映射 (`ORM`)。该模块有助于与 `Hibernate`、`JDO` 和 `iBATIS SQL Maps` 等流行的 ORM 框架集成。

Spring 框架的事务管理模块也支持所有这些 ORM 框架以及 `JDBC`。

### 122. Spring 框架中的 Web 模块是如何工作的？

Spring 通过使用 `Web` 模块支持开发 Web 应用程序。该模块构建在上下文（`Context`）模块之上，为 Web 应用程序提供上下文。

该模块还支持面向 Web 的集成功能，例如透明地处理上传文件的多部分请求，通过程序方式将请求参数绑定到业务对象。

该模块还支持与 `Struts`、`JSF` 和 `Tapestry` 等流行的 Web 框架集成。

### 123. Spring MVC 模块的主要用途是什么？

`Spring-webmvc` 模块也称为 `Web-servlet` 模块。它基于 Web MVC 模式。

该模块的主要用途是：

- Spring 与其他 MVC 框架集成
- 支持 `IoC` 提供控制器逻辑与业务对象的清晰分离
- 提供领域模型代码与 Web 表单之间的清晰分离
- 允许开发者声明式地将请求参数绑定到业务对象

### 124. Spring 配置文件的用途是什么？

Spring 应用程序可以通过 XML 文件进行配置。该文件包含了类的信息以及这些类如何配置和相互引入。

Spring `IOC` 容器使用某种配置元数据。这些配置元数据表示应用程序开发者如何告诉 Spring 容器实例化、配置和组装应用程序中的对象。这些配置元数据存储在 Spring 配置文件中。

指定配置元数据的其他方法是基于 Java 配置和注解配置。

### 125. Spring IOC 容器的作用是什么？

Spring `IOC` 容器负责：

- 创建对象
- 配置对象
- 管理对象之间的依赖关系（通过依赖注入 (`DI`)）
- 组装对象
- 管理对象的完整生命周期

### 127. IOC 容器支持 Bean 的饿性实例化还是懒性加载？

Spring 中的 `IOC` 容器支持这两种方式。即支持 Bean 的饿性实例化也支持懒性加载。

### 128. Spring 中 ApplicationContext 有哪些优势？

Spring 中的 `ApplicationContext` 提供了以下优势：

- **Bean 工厂方法**：这些方法用于访问应用程序组件
- **加载文件资源**：它帮助以通用的方式加载文件资源
- **发布事件**：它允许向已注册的监听器发布事件
- **国际化支持**：解析消息以支持国际化的能力
- **父级上下文**：继承自父级上下文的能力

### 129. 你如何在 Spring 框架中实现 ApplicationContext？

Spring 中的 `ApplicationContext` 可以通过以下三种方式之一实现：

- `FileSystemXmlApplicationContext`：如果我们想从 XML 文件中加载 bean 的定义，则使用 `FileSystemXmlApplicationContext`。需要向构造函数提供 XML bean 配置文件的完整路径。



# ClassPathXmlApplicationContext

若要从 CLASSPATH 中的 XML 文件中加载 bean 的定义，我们使用 `ClassPathXmlApplicationContext`。它用于嵌入在 jar 包中的应用程序上下文。

# WebXmlContext

为了为 Web 应用程序提供配置，使用 `WebXmlContext`。在应用程序运行期间，它是只读的。但如果底层应用程序支持，它可以被重新加载。

## 130. 解释 Spring 中 ApplicationContext 和 BeanFactory 之间的区别？

ApplicationContext 和 BeanFactory 之间的主要区别是：

- **自动注册 BeanPostProcessor**：`BeanFactory` 不支持注册 `BeanPostProcessor`。而 `ApplicationContext` 支持此操作。
- **自动注册 BeanFactoryPostProcessor**：`BeanFactory` 也不允许自动注册 `BeanFactoryPostProcessor`。而 `ApplicationContext` 允许此操作。
- **MessageSource 访问**：`BeanFactory` 访问 `MessageSource` 不够方便。`ApplicationContext` 访问 `MessageSource` 非常方便。
- **ApplicationEvent**：我们无法通过 `BeanFactory` 发布 `ApplicationEvent`。但 `ApplicationContext` 提供了发布 `ApplicationEvent` 的能力。

## 131. 在 Spring 中 ApplicationContext 和 BeanFactory 之间使用哪一个更好？

Spring 文档在几乎所有情况下都推荐使用 `ApplicationContext`。`ApplicationContext` 拥有 `BeanFactory` 的所有功能。

## 132. 一个典型的基于 Spring 的应用程序的主要组件有哪些？

在基于 Spring 的应用程序中，主要组件有：

- **Spring 配置 XML 文件**：用于配置 Spring 应用程序
- **API 接口**：应用程序提供的函数的 API 接口定义
- **实现**：带有 API 实现的应用程序代码
- **切面（Aspects）**：应用程序实现的 Spring 切面
- **客户端**：用于访问函数的客户端应用程序

## 133. 解释 Spring 框架中的依赖注入（DI）概念？

依赖注入是一种软件设计模式。它被用于在 Spring 框架中实现控制反转（IOC）。根据这种模式，我们不通过调用 `new` 在应用程序中创建对象，而是描述对象应该如何被创建。通过这种方式对象的创建就不会与另一个对象紧耦合。

容器负责创建和装配对象。容器可以在运行时根据配置调用注入代码并装配对象。

## 134. 依赖注入（DI）中有哪些不同的角色？

依赖注入中有四个角色：

- 要使用的服务对象（或对象）
- 依赖于服务的客户端对象
- 定义客户端如何使用服务的接口
- 负责构造服务并将其注入客户端的注入器（Injector）

## 135. Spring 框架提供了哪些类型的依赖注入机制？

Spring 框架提供了两种类型的依赖注入机制：

- **基于构造函数的依赖注入**：Spring 容器可以调用带有多个参数的类构造函数。这代表了对其他类的依赖。
- **基于 setter 的依赖注入**：Spring 容器可以在使用无参构造函数或无参静态工厂方法实例化另一个 bean 后，调用该 bean 的 setter 方法。

## 136. 在 Spring 框架中，哪种依赖注入更好？基于构造函数的 DI 还是基于 setter 的 DI？

Spring 框架对基于构造函数和基于 setter 的依赖注入都提供了支持。在不同的场景下可以使用这些选项。

建议对于强制性依赖使用基于构造函数的 DI。而基于 setter 的 DI 则用于可选的依赖。

## 137. 依赖注入（DI）的优势是什么？

依赖注入（DI） 模式具有以下优势：

- 依赖注入减少了类与依赖项之间的耦合。
- 通过依赖注入（DI），我们可以进行并发或独立的软件开发。两个团队可以并行工作于它们将互相调用的类上。
- 在依赖注入（DI）中，客户端可以以多种方式配置。它只需要与给定的接口工作。其余的实现可以根据不同的功能进行更改和配置。
- 依赖注入还用于将系统的配置细节导出到配置文件中。因此，我们可以根据配置使同一个应用程序运行在不同的环境中。例如：运行在测试环境、UAT 环境和生产环境中。
- 依赖注入（DI）应用程序提供了更强的测试便利性和灵活性。它们可以在单元测试中进行隔离测试。
- 依赖注入（DI）将客户端从设计和实现的更改隔离开。因此，它促进了重用性、可测试性和维护性。

## 138. 依赖注入（DI）的劣势是什么？

依赖注入（DI） 模式具有以下劣势：

- 大多数时候依赖注入迫使开发者使用像 Spring 这样的注入框架。这导致对框架的依赖。
- 通过依赖注入，客户端依赖于配置数据。当应用程序不需要许多自定义配置值时，这变成了开发人员的一项额外任务。
- 在依赖注入中，代码难以追踪和阅读。DI 将行为与对象的构造分离。
- 依赖注入增加了类与类之间链接的复杂性。在类实现之外，管理这种复杂性可能会变得更加困难。

## 139. 什么是 Spring Bean？

Spring Bean 是由 Spring 容器创建并管理的普通 Java 对象（POJO）。

一个 Spring 应用程序中存在多个 bean。但所有这些 Bean 都由 Spring 容器实例化和装配。

开发者向 Spring 容器提供配置元数据，以创建和管理 Spring Bean。

通常 Spring Bean 是单例。每个 bean 有一个名为 "singleton" 的属性。如果其值为 true，则 bean 是单例。如果其值为 false，则 bean 是原型 bean。

该属性的默认值为 true。因此，spring framework 中所有的 bean 默认都是单例。

## 140. Spring Bean 定义包含什么？

Spring Bean 定义包含 bean 的配置元数据。Spring 容器使用这些配置元数据来：

- 创建 bean
- 管理其生命周期
- 解析其依赖

## 141. 向 Spring Container 提供配置元数据的方法有哪些？

Spring 支持三种方式提供配置元数据的方法：

- **基于 XML 的配置**：可以在 XML 文件中指定配置数据。
- **基于注解的配置**：可以使用注解来指定配置。这是从 Spring 2.5 开始引入的。
- **基于 Java 的配置**：从 Spring 3.0 开始引入。可以在 Java 代码中嵌入 `@Bean`、`@Import`、`@Configuration` 等注解来指定配置元数据。

## 142. Spring 支持哪些不同的 Bean 作用域（Scopes）？

Spring 框架支持七种 Bean 作用域。其中，对于 Web 感知的 ApplicationContext，只有五种作用域可用：

- **singleton（单例）**：这是 Bean 的默认作用域。在此作用域下，每个 Spring IoC 容器对应唯一的 Bean 实例。
- **prototype（原型）**：在此作用域下，单个 Bean 定义可以有多个对象实例。
- **request（请求）**：在此作用域下，单个 Bean 定义对应于单个 HTTP 请求的生命周期。每个 HTTP 请求都会为同一个 Bean 定义拥有自己的 Bean 实例。它仅在 Web 感知的 Spring ApplicationContext 上文中有效。
- **session（会话）**：在此作用域下，单个 Bean 定义绑定到 HTTP Session 的生命周期。每个 HTTP Session 都会有一个 Bean 实例。它同样在 Web 感知的 Spring ApplicationContext 上文中有效。
- **globalSession（全局会话）**：该作用域将单个 Bean 定义绑定到全局 HTTP Session 的生命周期。它通常在 Portlet 上文中有效。同样在 Web 感知的 Spring ApplicationContext 上文中有效。
- **application（应用）**：该作用域将单个 Bean 定义限制在 ServletContext 的生命周期内。同样在 Web 感知的 Spring ApplicationContext 上文中有效。
- **websocket（网络连接）**：在此作用域下，单个 Bean 定义绑定到 WebSocket 的生命周期。它同样在 Web 感知的 Spring ApplicationContext 上文中有效。

## 143. 如何在 Spring 中定义 Bean 的作用域？

在 XML 配置中，我们可以在 Bean 的定义中指定其作用域。容器通过此来决定 Spring 中 Bean 的作用域。

例如：

```
<bean id="userService" class="com.um.UserService" scope="prototype"/>
```

这是一个具有 prototype 作用域的 userService Bean 示例。

## 144. 假设 Spring 框架中的单例 Bean 是线程安全的吗？

不一定。Spring 框架不保证任何与单例 Bean 多线程行为相关的特性。开发者有责任处理并发问题并维护单例 Bean 的线程安全。

## 145. Spring 框架中使用了哪些设计模式？

Spring 框架使用了许多设计模式。其中一些模式包括：

- **Singleton（单例模式）**：默认情况下，在 Spring 配置文件中定义的 Bean 是单例的。这些基于单例模式。
- **Template（模板模式）**：该模式用于许多类，如 `JdbcTemplate`、`RestTemplate`、`JmsTemplate`、`JpaTemplate` 等。
- **Dependency Injection（依赖注入）**：该模式是 `BeanFactory` 和 `ApplicationContext` 设计的核心。
- **Proxy（代理模式）**：面向切面编程（AOP）大量使用了代理设计模式。
- **Front Controller（前端控制器模式）**：Spring 中的 `DispatcherServlet` 基于前端控制器模式，用以确保进入的的请求被分发到其他控制器。
- **Factory pattern（工厂模式）**：使用 `BeanFactory` 来创建对象的实例。这基于工厂模式。
- **View Helper（视图辅助器模式）**：Spring 有多种方案将核心代码与视图中的表现层分离。例如- 自定义 JSP 标签、Velocity 宏等。

## 146. Spring 框架中 Bean 的生命周期是怎样的？

Spring 框架中的 Bean 在其生命周期中经历以下阶段：

1. **初始化与创建**：Spring 容器从 XML 文件获取 Bean 的定义并实例化 Bean。它根据 Bean 定义中提到的内容填充 Bean 的所有属性。
2. **设置 Bean 的行为**：如果 Bean 实现了 `BeanNameAware` 接口，Spring 使用 `setBeanName()` 方法传递 Bean 的 id。如果 Bean 实现了 `BeanFactoryAware` 接口，Spring 使用 `setBeanFactory()` 将 BeanFactory 传递给 Bean。
3. **后处理（Post Processing）**：Spring 容器使用 `postProcessorBeforeInitialization()` 方法调用与 Bean 相关的 BeanPostProcessor。Spring 调用 `afterPropertySet()` 方法调用特定的初始化方法。如果 Bean 有任何 BeanPostProcessor，则会调用 `postProcessAfterInitialization()` 方法。
4. **销毁**：在 Bean 销毁期间，如果 Bean 实现了 `DisposableBean`，Spring 会调用 `destroy()` 方法。

## 147. Bean 生命周期中的两个大类方法是什么？

Spring 中的 Bean 有两组主要的生命周期方法。

- **初始化回调（Initialization Callbacks）**：一旦容器设置了 Bean 的所有必要属性，就会使用初始化回调方法执行初始化工作。开发者可以实现此工作 `afterPropertiesSet()` 方法。
- **销毁回调（Destruction Callbacks）**：当 Bean 的容器被销毁时，它会调用 `DisposableBean` 中的方法执行任何清理工作。有一个名为 `destroy()` 的方法可用于此目的来实现销毁回调。

Spring 最近的建议是不要使用这些方法，因为它们会使你的代码与 Spring 代码强耦合。

## 148. 我们可以覆盖 Spring 中 Bean 的主要生命周期方法吗？

可以，Spring 框架允许开发者覆盖 Bean 的生命周期方法。这用于为 Bean 编写自定义行为。

## 149. Spring 中的内部 Bean（Inner beans）是什么？

作为另一个 Bean 的属性使用的 Bean 被称为内部 Bean。它可以在 `<property/>` 或 `<constructor-arg/>` 标签中定义为 `<bean/>`元素。

内部 Bean 强制拥有 id 或名称。它们始终是匿名的。

内部 Bean 不需要作用域。默认是 prototype 作用域。

## 150. 如何在 Spring 框架中注入 Java 集合（Collection）？

Spring 在代码中推广依赖注入（DI）。它不仅支持注入对象，还支持注入集合。

我们可以在 Spring 中注入集合如 list、set、map。可以使用以下标签实现此目的：

- `<list>`：此类型用于注入值列表。在 list 中允许重复。
- `<set>`：此类型用于注入值集合。根据 set 的规定，不允许重复。
- `<map>`：此类型用于以 map 形式注入键值对。键和值可以是任何允许的 map 类型。
- `<props>`：此类型用于注入基于字符串的键值。类似于属性文件。

## 151. Spring 中的什么是 Bean 属性（Wiring）？

Spring 容器负责注入 Bean 之间的依赖关系。这种连接 Bean 的被称为 wiring。

开发者在配置文件中注明 Bean 之间的依赖。Spring 容器读取这些依赖并在创建时进行 wiring。

## 152. Spring 中的什么是自动装（Autowiring）？

自动装是 Spring 的一种功能，容器可以通过读取配置文件来连接/整合 Bean。

开发者只需在 Bean 中定义 `autowire` 属性。

Spring 通过查看自动装 Bean 的属性来解析依赖。

## 153. Spring 支持哪些不同的自动装模式？

Spring 支持五种自动装模式：

- **no**：这是自动装的默认设置。在这种情况下，我们使用 “ref” 模式来指定用于连接的显式 Bean。

  例如：在此示例中，Employee Bean 引用 Manager Bean。

  ```
  <bean id="employee" class="com.dept.Employee">
    <property name="manager" ref="manager" />
  </bean>
  <bean id="manager" class="com.dept.Manager" />
  ```

- **byName**：在这种情况下，Spring 容器在自动装期间尝试名称匹配 Bean。如果 Bean 的名称与自动装 byname 中引用的 Bean 名称相同，则会自动连接它。

  例如：在以下示例中，Manager Bean 按名称连接到 Employee。

  ```
  <bean id="employee" class="com.dept.Employee" autowire="byName" />
  <bean id="manager" class="com.dept.Manager" />
  ```

- **byType**：在这种情况下，Spring 容器检查通过 byType 属性引用的 Bean 属性。然后匹配 Bean 类型并进行连接。如果发现多个相同类型的 Bean，它将抛出致命异常。

  例如：在以下示例中，Manager Bean 按类型连接到 Employee Bean。

  ```
  <bean id="employee" class="com.dept.Employee" autowire="byType" />
  <bean id="manager" class="com.dept.Manager" />
  ```

- **constructor**：在这种情况下，Spring 容器会在构造函数参数中查找 `byType` 属性。它会尝试寻找名称完全相同的 bean。如果找到多个同名的 bean，它将抛出一个致命异常（fatal exception）。这种情况与 `byType` 的情况类似。

  例如：在接下来的示例中，使用了 "constructor" 进行自动注入。

  ```
  <bean id="employee" class="com.dept.Employee" autowire="constructor" />
  <bean id="manager" class="com.dept.Manager" />
  ```

- **autodetect**：这是一种自动注入的高级模式。在这种情况下，默认情况下 Spring 会尝试寻找匹配的构造函数。如果没有找到构造函数，它将使用按类型（by Type）进行自动注入。

  例如：这是一个 `autodetect` 自动注入的示例。

  ```
  <bean id="employee" class="com.dept.Employee" autowire="autodetect" />
  <bean id="manager" class="com.dept.Manager" />
  ```

## 154. 在 Spring 框架中，自动注入可能不起的情况有哪些？

自动注入是 Spring 中一个非常强大的特性。它可以用于大多数情况。但在某些特定场景下，自动注入可能失效。



## 显式注入（Explicit wiring）

由于自动注入是由 Spring 完成的，开发者无法完全控制要使用的精确类。在需要对注入进行完全控制的情况下，最好使用显式注入。

## 基本类型数据类型（Primitive Data types）

自动注入不允许注入基于 `int`、`float` 等基本类型数据类型的属性。

## 155. Spring 允许注入 null 或空字符串值吗？

是的，Spring 允许注入 `null` 或空字符串值。

## 156. 什么是 Spring 基于 Java 的配置（Java-based Configuration）？

Spring 允许基于 Java 的配置，开发者可以使用基于 Java 的注解来指定配置。该功能是在 Spring 3.0 中引入的。

你可以在 Java 类中使用如 `@Configuration`、`@Bean`、`@Import` 和 `@DependsOn` 等注解来指定配置。

## 157. @Configuration 注解的作用是什么？

该注解用于类，用来指示该类是 bean 定义的主要源。该类还可能包含被 `@Bean` 注解标记的 bean 间依赖关系。

## 158. Full @Configuration 和 'lite' @Beans 模式之间的区别是什么？

Spring 允许在未使用 `@Configuration` 注解的类的方法上使用 `@Bean` 注解。这被称为“lite”模式。在这种模式下，bean 方法可以在 `@Component` 或带有任何注解的普通 Java 类中声明。

在“lite”模式下，`@Bean` 方法不能声明 bean 间的依赖关系。

建议在 'lite' 模式下，一个 `@Bean` 方法不要调用另一个 `@Bean` 方法。

Spring 建议在 `@Configuration` 类内部声明的 `@Bean` 方法应用于全配置（full configuration）。这种全模式可以防止许多 bug。

## 159. 在 Spring 框架中，什么是基于注解的容器配置？

从 Spring 2.5 版本开始，可以使用注解提供配置。

要开启此配置，我们需要在 Spring XML 文件中引入 `<context:annotation-config/>`。

现在开发者可以在类文件中使用如 `@Required`、`@Autowired`、`@Qualifier` 等注解来指定 bean 的配置。Spring 容器可以使用来自注解的信息来创建和注入 bean。

## 160. 如何在 Spring 中开启基于注解的注入？

要使用基于注解的注入，我们需要在 Spring 中开启基于注解的配置。

默认情况下，Spring 中的基于注解的配置是关闭的。要开启它，我们可以在 Spring 配置文件中指定 `<context:annotation-config/>` 元素。

一旦开启，我们就可以在 Java 类中使用 `@Autowired` 注解或 `@Required` 注解在 Spring 中进行注入。

## 161. 什么是 @Autowired 注解？

我们可以使用 `@Autowired` 注解在 setter 方法、构造函数或字段上自动注入 bean。`@Autowired` 自动注入是通过匹配数据类型完成的。

在使用 `@Autowired` 注解之前，我们必须注册 `AutowiredAnnotationBeanPostProcessor`。这可以通过在 bean 配置文件中包含 `<context:annotation-config/>` 来实现。

## 162. 什么是 @Required 注解？

我们在属性上使用 `@Required` 注解来检查该属性是否已设置。

如果被标记了 `@Required` 的属性未设置，Spring 容器将抛出 `BeanInitializationException`。

当我们使用 `@Required` 注解时，必须在 Spring 配置文件中注册 `RequiredAnnotationBeanPostProcessor`。

## 163. 在 Spring 中启用 RequiredAnnotationBeanPostProcessor 的两种方式是什么？

在 Spring 中可以通过两种方式启用 `RequiredAnnotationBeanPostProcessor`：

- 包含 `<context:annotation-config />`
- 在 bean 配置文件中添加 Spring context 和 `<context:annotation-config />`。

例如：

```xml
<beans xmlns:context="http://www.springframework.org/schema/context"
        xsi:schemaLocation="http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">
    <context:annotation-config />
</beans>
```

或者，将其包含 bean 配置中：

```xml
<beans xmlns:context="http://www.springframework.org/schema/context"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.xsd">
```

## 164. Spring 中的 @Qualifier 注解是什么？

我们使用 `@Qualifier` 注解标记一个 bean 以准备进行自动注入。该注解与 `@Autowired` 注解一起使用，以指定精确的 bean。

## 165. Spring 框架如何让 JDBC 编码变得更容易？

Spring 提供的 JDBC 框架来支持 JDBC 编码。Spring 以通用的方式处理资源管理以及错误处理。这减少了软件开发者的工作。

他们只需要编写查询和相关的语句来获取或存储数据。

## 166. JdbcTemplate 的作用是什么？

Spring 框架提供的 `JdbcTemplate` 类包含许多方便的方法，用于常规任务，如将数据转换为原始类型或对象、执行预编译语句等。该类使得操作数据库变得非常简单，并且对错误处理提供了很好的支持。

## 167. 使用 Spring DAO 的好处是什么？

使用 Spring DAO 的优点包括：

- 它让操作 JDBC、Hibernate 等不同的数据访问方法变得更容易。
- 它为处理不同的数据访问方法提供了一致且通用的方式。
- Spring DAO 使得在不同的数据持久框架之间切换变得容易。
- 不需要捕获框架特定的异常。

## 168. 在 Spring 中使用 Hibernate 的不同方式有哪些？

Spring 提供了两种使用 Hibernate 的方式：

- 我们可以扩展 `HibernateSupport` 并应用 AOP 拦截器来使用 Hibernate。
- 我们也可以使用 `HibernateTemplate` 和回调（Callback）机制来访问 Hibernate。

## 169. Spring 支持哪些类型的对象关系映射（ORM）？

Spring 支持以下 ORM 框架：

- Hibernate
- Java Persistence API (JPA)
- TopLink
- Java Data Objects (JDO)
- Apache Object Relational Bridge (ORB)

## 170. 如何通过 HibernateDaoSupport 集成 Spring 和 Hibernate？

我们可以通过以下步骤集成 Spring 和 Hibernate：

- 在 pom.xml 中添加 Spring 和 Hibernate 的依赖
- 继承 `HibernateDaoSupport` 实现 DAO
- 通过 `getHibernateTemplate()` 方法使用 Hibernate 函数

## 171. Spring 框架支持哪些类型的事务管理？

Spring 框架提供了两种类型的事务管理支持：

- 编程式（Programmatic）：在这种方法中，我们必须通过显式编程来管理事务。它为开发者提供了灵活性，但不利于维护。
- 声明式（Declarative）：在这种方法中，我们可以将事务管理与应用程序业务代码分离。我们可以使用注解或基于 XML 的配置来以声明的方式管理事务。

## 172. Spring 框架的事务管理提供了哪些好处？

Spring 事务管理的主要优点是：

- 一致性（Consistent）：通过使用 Spring 事务管理，我们可以在不同的事务 API（如 JPA, JDBC, JTA, Hibernate, JDO 等）上使用一致的编程模型。
- 简单性（Simplicity）：Spring TM 提供了简单的 API 来通过编程方式管理事务。
- 声明式（Declarative）：Spring 还支持基于注解或 XML 的声明式事务管理。
- 集成性（Integration）：Spring 事务管理更容易与 Spring 的其他数据访问抽象集成。

## 173. 在声明式和编程式事务管理之间选择，你会选择哪种方法？

在 Spring 中，声明式事务管理是首选。这种方法的侵入性很低，对应用程序业务逻辑的影响也很小。

虽然声明式方法的灵活性低于编程式方法，但从长远来看，它使用更简单且更容易维护。

## 174. 什么是面向切面编程 (AOP)

面向切面编程（AOP）是一种编程范式，它促进程序员在不同的模块中开发代码，这些模块可以是并行的或属于跨关注点。

例如：开发银行软件时，一个团队可以负责取款、存款、转账等业务逻辑；另一个团队可以负责跨多个账户提交事务的事务管理。

在一家汽车公司，一个团队可以负责与汽车不同组件集成的软件；另一个团队可以负责所有组件如何向公共仪表盘发送信号和当前信息。

## 175. Spring 中的什么是 Aspect（切面）？

Aspect 是 AOP 的核心构造。它在一个可重用的模块中封装了影响多个类的行为。

一个 Aspect 可以包含一组提供跨关注点功能的 API。

例如：日志模块可以是应用程序中的一个 Aspect。

应用程序可以根据不同的需求拥有多个 Aspect。

一个 Aspect 可以在类上使用注解 `@Aspect` 来实现。

## 176. 在 Spring AOP 中，Concern（关注点）和 Cross cutting concern（跨关注点）的主要区别是什么？

Spring 中的 Concern 是应用程序的行为或预期。它可以是我们想要实现的主要功能。

Cross cutting concern（跨关注点）也是一种 Concern。它是以轻量方式分散在整个应用程序中的特性或功能。

例如：安全、日志、事务管理等都是应用程序中的跨关注点。

## 177. Spring AOP 中的什么是 Joinpoint（连接点）？

在 Spring AOP 中，Joinpoint 指的是应用程序中可以插入 Aspect 的候选点。

Joinpoint 可以是一个方法、一个异常或正在被修改的字段。

这是 Aspect 代码被插入的地方，以便在现有的执行流中添加新行为。

## 178. Spring AOP 中的什么是 Advice（通知）？

Spring AOP 中的 Advice 是一个包含 Aspect 引入的实际操作的对象。

Advice 是被执行的跨关注点代码。

Spring AOP 中有多种类型的 Advice。

## 179. Spring AOP 中不同的 Advice 类型有哪些？

Spring AOP 提供了五种 Advice：

- **Before Advice（之前通知）**：这种类型的通知在方法执行之前运行。我们可以为此使用 `@Before` 注解。
- **After (finally) Advice（后置通知）**：这种类型的通知在方法执行后立即运行。即使方法失败，此通知也会运行。我们在这里可以使用 `@After` 注解。
- **After Returning Advice（返回后通知）**：这种类型的通知在方法成功执行后运行。可以使用 `@AfterReturning` 注解。
- **After Throwing Advice（异常通知）**：这种类型的通知在方法执行并抛出异常后运行。使用的注解是 `@AfterThrowing`。
- **Around Advice（环绕通知）**：这种类型的通知在方法调用前后都会运行。我们使用 `@Around` 注解。

## 180. Spring AOP 中的什么是 Pointcut（切点）？

Spring AOP 中的 Pointcut 指的是一个或多个可以应用 advice 的 Joinpoints 组。

我们可以将 Advice 应用到任何 Joinpoint。但我们想限制特定类型 Advice 应用的地方。为了实现这一点，我们使用 Pointcut。

我们可以使用类名、方法名或正则表达式来指定 Advice 的 Pointcuts。

## 181. Spring AOP 中的什么是 Introduction（引入）？

在 Spring AOP 中，我们可以代表某种类型声明额外的方法或字段。为了实现这一点，我们使用 Introduction。它也被称为类型声明（inter-type declaration）。

例如：我们可以使用 Introduction 让一个 bean 实现 `IsModified` 接口。

## 182. Spring AOP 中的什么是 Target object（目标对象）？

Target object 是从一个或多个 Aspect 获取 Advice 的对象。

也被称为 advised object（被通知对象）。

在大多数情况下它是一个代理（proxy）。

## 183. Spring AOP 中的什么是 Proxy（代理）？

在 Spring AOP 中，Proxy 是 AOP 框架创建用于实现 Aspect 的对象。它通常是 JDK 动态代理或 CGLIB 代理。

## 184. Spring 中不同的 AutoProxy（自动代理创建器）类型有哪些？

Spring AOP 提供了以下标准的 AutoProxy creators：

- **BeanNameAutoProxyCreator**：通过名称匹配自动创建 AOP 代理的 BeanPostProcessor。
- **DefaultAutoProxyCreator**：比其他 Proxy Creators 更强大。它将合适的顾问应用到上下文中的 bean。
- **AbstractAutoProxyCreator**：DefaultAutoProxyCreator 的父类。我们可以通过扩展此类创建自己的自动代理创建器。

## 185. Spring AOP 中的什么是 Weaving（织入）？

在面向切面编程中，将 Aspect 与其他类型关联创建 Advised 对象。这个过程被称为 Weaving。

没有 Weaving，只有 Aspect 的定义。Weaving 充分利用了 AOP 的潜力。

Weaving 可以在编译时、加载时或运行时进行。

## 186. Spring AOP是在编译时还是运行时完成？

Spring 容器在运行时执行 Weaving。

## 187. 什么是基于 XML 的 Aspect 实现？

Spring 允许使用普通类和基于 XML 的配置来实现 Aspect。这与基于注解的 Aspect 实现不同，但实现了相同的 AOP 目标。

我们可以在 Spring XML 配置中使用元素 `<aop:aspect id="testAspect" ref="testBean" />` 和 `<aop:pointcut id="testPointcut" />`。

要使用它，我们需要如下导入 Spring AOP 架构：

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd
                           http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.0.xsd">
</beans>
```



## 188. Spring AOP 中的基于注解的 Aspect 实现？

这是一种声明式的 AOP 实现。在这种情况下，我们使用 `@Aspect`、`@Pointcut`、`@Joinpoint` 等注解来为代码标记不同类型的 AOP 元素。

这可以在 Java 5 及之后使用，即引入注解支持之后。

## 189. Spring MVC 框架是如何工作的？

Spring 提供了自有的模型视图-控制器（MVC）框架用于开发 Web 应用程序。

Spring MVC 框架基于控制反转（IOC）原则。它将业务对象与控制器分离。

它的设计围绕 `DispatcherServlet` 展开，该 Servlet 负责将请求分发给相关的处理器。

Spring MVC 框架还支持基于注解的请求参数绑定。

## 190. 什么是 DispatcherServlet？

在 Spring MVC 中，`DispatcherServlet` 是核心 servlet，负责处理所有请求并将它们分发给处理器。

Dispatcher servlet 知道要调用的方法与浏览器请求之间的映射关系。它调用特定方法，并将结果与匹配的 JSP 结合创建一个 html 文档，然后将其发送回浏览器。

在 RMI 调用的情况下，它会向客户端应用程序返回响应。

## 191. Spring MVC 中可以有多个 DispatcherServlet 吗？

可以，一个 Spring MVC Web 应用程序可以有多个 `DispatcherServlet`。
每个 `DispatcherServlet` 必须在它自己的命名空间内运行。它必须加载包含映射、处理器等信息的自己的 `ApplicationContext`。

只有根应用上下文会在这些 Servlets 之间共享。

## 192. Spring MVC 中的 WebApplicationContext 是什么？

`WebApplicationContext` 是普通 `ApplicationContext` 的子类。它用于 Web 应用程序。它提供了处理 Web 相关组件的功能，如控制器、视图解析器等。

一个 Web 应用程序可以有多个 `WebApplicationContext` 来处理请求。

每个 `DispatcherServlet` 与一个 `WebApplicationContext` 联。

## 193. Spring MVC 框架中的 Controller 是什么？

Controller 是 Spring MVC 中的一个接口。它在 Web 应用中像 `HttpServlet` 一样接收 `HttpServletRequest` 和 `HttpServletResponse`，但它能够参与 MVC 流。

Controller 类似于基于 Struts 的应用程序中的 Struts Action。

Spring 建议 Controller 接口的实现应该是一个可重用的、线程安全的类，能够在应用程序的生命周期内处理多个 HTTP 请求。

最好使用 JavaBean 来实现 Controller。

Controller 解析用户输入并将其转换为模型（model）。模型通过视图（view）展示给用户。

Spring 以非常通用的方式实现控制器。这使得我们能够创建各种控制器。

### Spring MVC 中的 @Controller 注解是什么？

我们使用 `@Controller` 注解来指示一个类是 Spring MVC 中的 Controller。

Spring 的分发器会扫描带有 `@Controller` 注解的类，以查找映射的方法，并检测 `@RequestMapping`。

## 194. Spring 中的 @RequestMapping 注解是什么？

在 Spring MVC 中，我们使用 `@RequestMapping` 注解将 Web 请求映射到类或处理器方法。

在 `@RequestMapping` 中，我们可以指定 URL 的路径以及 HTTP 方法，如- GET、PUT、POST 等。

`@RequestMapping` 同时也支持将 HTTP Header 指定为属性。

我们还可以在 `@RequestMapping` 中映射由控制器产生的不同媒体类型（media types）。我们使用 HTTP Header Accepts 来实现此目的。

```
@RequestMapping(
    value = "/test/mapping",
    method = GET,
    headers = "Accept=application/json"
)
```



## 195. Spring MVC 的主要特性有哪些？

Spring MVC 具有以下主要特性：

1. **职责的清晰分离**：在 Spring MVC 中，每个角色（如控制器、验证器、`CommandServlet`、表单对象、模型对象、`DispatcherServlet`、处理器映射、视图解析器等）都由专门的对象完成。
2. **可重用性**：Spring MVC 促进业务代码复用以减少重复。我们可以使用现有的业务对象作为命令对象或表单对象，而不是复制它们来扩展特定的框架类。
3. **灵活的模型传输**：Spring MVC 模型传输还支持与其它视图技术的轻松集成。
4. **可自定义的绑定和验证**：在 Spring MVC 中，我们可以对请求和控制器之间进行自定义绑定。即使是非字符串值也可以对其进行验证。
5. **JSP 表单标签库**：从 Spring 2.0 开始，有一个强大的 JSP 表单标签库，它使得在 JSP 页面中编写表单变得简单得多。
6. **可自定义的本地化、时区和主题解析**：Spring MVC 支持本地化、时区等方面的自定义。

## 196. Spring 中单例（Singleton）和原型（Prototype） bean 有什么区别？

Spring 中的每个 bean 都有一个作用范围（scope），定义了它在应用程序中的生存时间。

- **单例范围**：限制每个 Spring IOC 容器中只有一个对象实例。这个单实例受限于特定的 `ApplicationContext`。如果有多个 `ApplicationContext`，那么我们可以有多个 bean 实例。默认情况下，Spring 框架中的所有 bean 都是单例范围 bean。
- **原型范围**：单个 bean 定义可以在 Spring 容器中拥有多个对象实例。在原型范围 bean 中，每当对特定 bean 请求时，Spring IoC 容器都会创建该对象的新实例。

## 197. 你如何决定为 Spring 中的 bean 使用什么范围——原型还是单例？

通常，我们对所有有状态（stateful）bean 使用原型范围，对无状态（stateless）bean 使用单例范围。

- 由于无状态 bean 不维护任何状态，我们可以反复使用同一个对象实例。单例范围 bean 正是如此。
- 在有状态 bean 中，需要在每个请求中维护状态，因此每次调用都有必要使用新的对象实例。原型范围 bean 确保了这一点。

## 198. Spring 中基于 Setter 和基于构造函数的注入（DI）有什么区别？

基于 Setter 和基于构造函数的注入（DI）之间的主要区别是：

- **优先级**：基于 Setter 的注入优先级高于基于构造函数的注入。
- **部分依赖**：我们可以使用 Setter 注入来实现部分依赖。在构造函数注入中，不可能只进行部分依赖。
- **灵活性**：如果类中有两个属性，可以使用 Setter 注入其中一个属性。
- **可读性**：Setter 注入比构造函数注入更具可读性。通常 Setter 方法类似于依赖类。

## 199. Spring 中 Setter 注入（DI）的缺点是什么？

虽然 Setter 注入的优先级高于构造函数注入，但它也有一些缺点。

- **无法保证**：在 Setter 注入中，无法保证某个依赖是否被注入。我们可能拥有一个部分依赖或无依赖的对象。而在基于构造函数的注入中，在所有依赖准备就绪之前对象都不会创建。
- **安全性**：人们可以使用 Setter 注入来覆盖另一个依赖。这可能会导致 Spring 应用程序的安全漏洞。
- **循环依赖**：Setter 注入可能会导致对象之间的循环依赖。而在创建对象期间如果存在循环依赖，基于构造函数的注入将抛出 `ObjectCurrentlyInCreationException`。

## 200. 依赖注入（DI）和工厂模式有什么区别？

依赖注入（DI）和工厂模式之间的主要区别是：

- **耦合**：工厂模式增加了对象、工厂和依赖之间的紧密耦合。在 DI 的情况下，对象之间没有耦合。我们只需提到对不同对象的依赖，容器会解析并引入这些依赖。
- **易于测试**：DI 更容易测试，因为我们可以在测试环境中注入 mock 对象作为依赖。在工厂模式的情况下，我们需要创建实际对象。
- **灵活性**：DI 允许轻松切换不同的 DI 框架。它为 DI 框架的选择提供了灵活性。
- **容器**：DI 总是需要容器来注入依赖。这会导致额外的开销以及应用程序中的额外代码。在工厂模式中，你可以直接使用 POJO 类来实现应用程序，而不需要任何容器。
- **代码整洁**：DI 代码比工厂模式的代码整洁得多。在 DI 中，我们不需要为工厂方法添加额外代码。

## 201. 在 Spring 框架中，FileSystemResource 和 ClassPathResource 的区别是什么？

在 Spring 中，我们可以通过文件或类路径（classpath）指定配置。

- **FileSystemResource**：我们必须提供 Spring 配置文件 `spring-config.xml` 的绝对路径或相对路径。
- **ClassPathResource**：Spring 在 ClassPath 中查找配置文件 `spring-config.xml`。因此，开发者必须将 `spring-config.xml` 包含在 classpath 中。

ClassPathResource 在 CLASSPATH 中查找配置文件，而 FileSystemResource 在文件系统中查找配置文件。

## 202. 请列举一些你在项目中使用的常用 Spring 框架注解？

Spring 有许多注解来满足不同的目的。对于常规使用，我们参考以下常用的 Spring 注解：

- `@Controller`：该注解用于在 Spring MVC 项目中创建控制器类。
- `@RequestMapping`：该注解将 URI 映射到 Spring MVC 中的控制器处理方法。
- `@ResponseBody`：我们使用此注解将对象作为响应发送。
- `@PathVariable`：我们使用此注解将 URI 中的动态值映射到处理方法的参数。
- `@Autowired`：该注解指示 Spring 自动装配 Bean 中的依赖。
- `@Service`：该注解标记 Spring 中的服务类。
- `@Scope`：我们可以通过此注解定义 Spring Bean 的作用范围。
- `@Configuration`：这是用于 Java 配置 Spring 配置的注解。
- `@Aspect`、`@Before`、`@After`、`@Around`、`@Joinpoint`、`@Pointcut`：这些是 Spring 中用于 AspectJ AOP 的注解。

## 203. 如何在 Spring MVC 中上传文件？

在 Spring MVC 框架中，我们可以使用 `MultipartResolver` 接口来上传文件。我们需要更改配置以使其工作。上传文件后，我们必须创建一个 Controller 处理方法来在应用程序中处理上传的文件。

## 204. Spring 框架提供了哪些不同类型的事件？

Spring 框架为 Context 提供了以下五种事件：

- **ContextRefreshedEvent**：每当 ApplicationContext 初始化或刷新时，Spring 都会发布此事件。我们也可以通过使用 `ConfigurableApplicationContext` 接口上的 `refresh()` 方法来触发它。
- **ContextStartedEvent**：当使用 `ConfigurableApplicationContext` 接口上的 `start()` 方法启动 ApplicationContext 时，会发布 ContextStartedEvent。接收此事件后，我们可以轮询数据库或重启任何已停止的应用程序。
- **ContextStoppedEvent**：当使用 `ConfigurableApplicationContext` 接口上的 `stop()` 方法停止 ApplicationContext 时，Spring 会发布此事件。这用于执行任何清理工作。
- **ContextClosedEvent**：一旦使用 `close()` 方法关闭了 ApplicationContext，就会发布 ContextClosedEvent。一旦上下文关闭，它就是其生命周期的最后一个阶段。此之后它将无法被刷新或重启。
- **RequestHandledEvent**：这是一个 Web 特有的事件，通知所有 Bean 一个 HTTP 请求已处理完毕。

## 205. Spring 中 DispatcherServlet 和 ContextLoaderListener 有什么区别？

- **DispatcherServlet**：是 Spring MVC 应用程序的核心。它加载 Spring Bean 配置并初始化配置文件中提到的所有 Bean。如果在 Spring 配置文件中启用了注解，它还会扫描包并配置任何标记了 `@Component`、`@Controller`、`@Repository` 或 `@Service` 注解的 Bean。
- **ContextLoaderListener**：是一个用于启动和关闭 Spring 根 `WebApplicationContext` 的监听器。ContextLoaderListener 将 `ApplicationContext` 的生命周期与 `ServletContext` 的生命周期联系起来。它自动化了 `ApplicationContext` 的创建。它还可以用于定义跨 Spring 上下文使用的共享 Bean。

## 206. 你如何在 Spring MVC 框架中处理异常？

Spring MVC 框架提供了以下机制来帮助我们实现异常处理：

- **基于控制器**：开发者可以在 Controller 类中定义异常处理方法。为此，他们必须在方法上加上 `@ExceptionHandler` 注解。
- **全局异常处理器**：Spring 提供了 `@ControllerAdvice` 注解作为跨切关注点的异常处理。我们可以使用此注解将任何类标记为全局异常处理器。
- **HandlerExceptionResolver 实现**：Spring 框架提供了 `HandlerExceptionResolver` 接口，可以通过实现它来创建全局异常处理器。

## 207. Spring 框架的最佳实践是哪些？

在 Spring 框架中，以下是一些最佳实践：

- 我们可以根据关注点拆分 Spring Bean 配置，例如 `spring-jdbc.xml`、`spring-security.xml`。
- 最好在 schema 引用中避免版本号。这确保了我们拥有最新的配置文件。
- 尽可能配置 Bean 依赖是一个良好的做法。除非有充分理由，否则尽量避免自动装配。
- 对于 Spring MVC 中在多个上下文使用的 Spring Bean，我们可以在根上下文创建它们并使用监听器进行初始化。
- Spring 框架提供了许多功能和模块。我们应该只使用应用程序需要的功能。多余的依赖必须移除。
- 对于应用程序属性（properties），最好创建一个属性文件并在 Spring 配置文件中读取它。
- 注解对于较小的应用程序有用，但对于较大的应用程序，注解可能会变成开销。如果所有配置都在 xml 文件中，会更容易维护。
- 当我们进行 AOP 时，必须保持连接点（Joinpoint）尽可能窄，以避免在不需要的方法上应用建议（Advice）。
- 我们应该为组件或服务使用正确的注解。服务使用 `@Service`，DAO Bean 使用 `@Repository`。
- 在确实有实际益处时必须使用依赖注入（DI）。
- 它不应该仅仅为了解耦而使用。

## 208. 什么是 Spring Boot？

Spring Boot 是一种用于创建具有生产级功能的 Spring 应用程序的现成解决方案。它倾向于约定优于配置（convention over configuration）。

我们可以在用 Spring Boot 创建的应用程序中嵌入 Tomcat 或 Jetty。Spring Boot 会自动配置 Spring。

它不需要任何代码生成或 xml 配置。它是一个创建独立应用程序的简单解决方案。

# Hibernate

## 209. 什么是 Hibernate 框架？

Hibernate 是一个流行的 Java 对象关系映射（ORM）框架。它帮助将对象模型映射到关系型数据库表。

Hibernate 是根据 GNU 许可证分发的免费软件。

Hibernate 还提供了 Java Persistence API（JPA）的实现。

简单来说，它是一个从数据库检索和存储数据的框架。

## 210. 什么是对象关系映射（ORM）？

对象关系映射（ORM）是一种将关系型数据库数据映射到对象模型的编程技术。这是 Hibernate 框架的核心。

在 Java 中，大多数软件都是基于面向对象设计的。但存储在数据库中的数据是基于关系数据库管理系统（RDBMS）的。ORM 帮助以面向对象的方式从 RDBMS 获取数据。

## 211. Hibernate 中 Configuration 接口的作用是什么？

可以在应用程序中实现 `Configuration` 接口，为创建 `SessionFactory` 指定属性和映射文档。

默认情况下，`Configuration` 的新实例使用 `hibernate.properties` 文件中提到的属性。

`Configuration` 主要是一个初始化对象，加载属性并帮助使用这些属性创建 `SessionFactory`。

简而言之，`Configuration` 用于在应用程序中配置 Hibernate。

## 212. 什么是对象关系阻抗失配？

对象关系阻抗失配（Object Relational Impedance Mismatch，ORIM）也称为范式不匹配。这意味着对象模型和关系模型之间工作并不良好。

关系模型或 RDBMS 以电子表格的格式表示数据。对象模型或 OOPS 将数据表示为相互连接的对象图。

混合这两种模型会导致各种问题。这些问题的共同名称是对象关系阻抗失配。

## 213. 对象-关系阻抗失配的主要问题有哪些？

对象模型和关系模型（RDBMS）之间存在以下问题，这些构成了对象-关系阻抗失配：

- **粒度**：对象模型比关系模型更细粒。对象模型中的类比关系模型中对应的表要多。
- **继承**：对象模型支持继承。但关系模型没有继承的概念。
- **标识性**：关系模型判断数据相同性只有一种标准，即基于主键。在 Java 等对象模型中，我们可以使用 `equals` 和 `==` 来判断对象的相等性。
- **关联**：在对象模型中，关联是单向的。在 RDBMS 中，通过外键概念来实现关联。此外，仅观察对象模型很难判断关系的重数（multiplicity）。
- **数据导航**：在对象模型中，你可以从一个对象移动到另一个对象来获取数据。例如：你可以获取一个员工对象，然后进入它的部门对象，再获取该部门对象中的员工。在 RDBMS 中，我们尝试尽量减少 SQL 调用，因此通过连接（joins）来获取所有数据。

## 214. Hibernate 的关键特性有哪些？

Hibernate 具有以下关键特性：

- **对象/关系映射（ORM）**：Hibernate 为开发者提供了 ORM 能力。这样他们就可以编写对象模型代码来连接到关系模型中的数据。
- **JPA 提供者**：Hibernate 提供了 Java Persistence API (JPA) 规范的优秀实现。
- **惯用化持久化**：Hibernate 提供了基于面向对象惯用法的持久化，并对继承、多态、关联、组合以及 Java 集合框架完全支持。它可以对任何数据进行持久化。
- **高性能**：Hibernate 提供了高级的性能支持特性，如延迟初始化、多种获取策略、乐观锁等。Hibernate 不需要自己的数据库表或字段。它可以在系统初始化时生成 SQL，以便在运行时提供更好的性能。
- **可扩展性**：Hibernate 在多服务器集群中运行良好。它具有内置的可扩展性支持。它既适用于小型项目，也适用于大型业务软件。
- **可靠**：Hibernate 是一个非常可靠且稳定的框架。这也是它在全球范围内获得认可并在开发者社区中流行的原因。
- **可扩展**：Hibernate 本质上是非常通用的。可以根据应用程序用例进行配置和扩展。

## 215. 你能介绍一下 Hibernate 框架的核心接口吗？

Hibernate 框架的核心接口如下：

- **Configuration**：`Configuration` 接口可以在应用程序中实现，用于指定在 Hibernate 中创建 `SessionFactory` 的属性和映射文档。Hibernate 应用通过使用此接口启动。
- **SessionFactory**：在 Hibernate 中，`SessionFactory` 用于创建和管理 `Session`。通常，一个数据库对应一个 `SessionFactory`。它是线程安全的接口，在多线程应用程序中运行良好。
- **Session**：`Session` 是一个轻量级对象，在运行时 Java 应用程序和 Hibernate 之间使用。它包含了对实体类创建、读取和删除操作的方法。它是抽象了持久化概念的基础类。
- **Transaction**：这是一个可选接口。它是一个短生命周期的对象，用于基于工作单元设计模式封装整个工作过程。一个 `Session` 可以拥有多个 `Transaction`。
- **Query**：此接口封装了 Hibernate 中面向对象查询的行为。它可以接受参数并执行查询以获取结果。同一个查询可以执行多次。
- **Criteria**：这是一个简化的 API，通过创建 `Criterion` 对象来检索对象。它非常易用于创建类似搜索的功能。

## 216. 在 Hibernate 中你如何将数据库表的列映射到 Java 类的属性？

我们可以通过以下两种方式之一映射类属性和表列：

- **XML**：我们可以在 XML 文件中将表的列映射到类的属性。通常扩展名为 `.hbm.xml`。
- **注解**：我们也可以使用 `@Entity` 和 `@Table` 注解将列映射到类的属性。

## 217. Hibernate 是否强制要求映射文件具有 .hbm.xml 扩展名？

不是。在映射文件名中使用 `.hbm.xml` 扩展名是一种约定，并不是 Hibernate 强制要求的。我们可以根据需要使用任何其他扩展名。

## 218. 在 Hibernate 中创建 SessionFactory 的步骤是什么？

在 Hibernate 中创建 `SessionFactory` 的步骤是：

1. **Configuration**：首先创建一个 `Configuration` 对象。这将引用配置文件的路径。
2. **Resource**：将配置文件资源添加到 `Configuration` 对象中。
3. **Properties**：在 `Configuration` 对象中设置属性。
4. **SessionFactory**：使用 `Configuration` 对象构建 `SessionFactory`。

示例：

```java
Configuration configuration = new Configuration();
configuration.configure("hibernate.cfg.xml");
SessionFactory sessionFactory = configuration.buildSessionFactory();
```



## 219. 为什么在 Hibernate 中使用 POJO？

POJO 代表 Plain Old Java Objects（简单的旧 Java 对象）。POJO 是一个带有每个属性的 getter 和 setter 方法的 Java Bean。

这是一个简单的类，封装了对象的属性并通过 setter 和 getter 提供访问。

在 Hibernate 中使用 POJO 的一些原因包括：

- POJO 强调了该类是一个简单的 Java 类，而不是像 EJB 那样沉重的类。
- POJO 是一个构建良好的类，因此它与 Hibernate 代理配合得很好。
- POJO 还带有一个默认构造函数，这使得通过默认构造函数进行持久化更容易。

## 220. 什么是 Hibernate 查询语言 (HQL)？

Hibernate 查询语言也称为 HQL。它是一种面向对象的语言。但它与 SQL 类似。HQL 与持久化对象及其属性工作良好。HQL 查询被转换为特定于数据库的 SQL 查询。HQL 支持直接运行原生 SQL 查询，但这会产生数据库移植性问题。

### 如何在 Hibernate 中调用存储过程？

Hibernate 支持不仅执行简单查询，还支持存储过程。有三种方法调用存储过程：

#### 1. XML 映射文件
我们可以在 XML 文件中声明存储过程。

```xml
<!-- Employee.hbm.xml -->
<hibernate-mapping>
  <class name="testHibernate.util.Employee" table="employee" ...>
    <id name="employeeId" type="java.Integer">
      <column name="EMPLOYEE_ID" />
      <generator class="identity" />
    </id>
    <property name="employeeId" type="string">
      <column name="EMPLOYEE_ID" length="10" not-null="true" unique="true" />
    </property>
  </class>
  <sql-query name="callEmployeeStoreProcedure" alias="employee" class="testHibernate.util.Employee">
    <![CDATA[CALL GetEmployees(:employeeId)]]>
  </sql-query>
</hibernate-mapping>
```

我们可以通过 `getNamedQuery` 调用它。

```java
Query query = session.getNamedQuery("callEmployeeStoreProcedure")
    .setParameter("employeeId", "1234");
List result = query.list();
for(int i=0; i<result.size(); i++){
    Employee employee = (Employee)result.get(i);
    System.out.println(employee.getEmployeeCode());
}
```

#### 2. 原生 SQL
我们可以使用原生 SQL 直接调用存储过程查询。在这个示例中，正在调用 `GetEmployees()` 存储过程。

```java
Query query = session.createSQLQuery(
    "CALL GetEmployees(:employeeId)")
    .addEntity(Employee.class)
    .setParameter("employeeId", "1234");

List result = query.list();
for(int i=0; i<result.size(); i++){
    Employee employee = (Employee)result.get(i);
    System.out.println(employee.getEmployeeCode());
}
```

#### 3. 使用注解
我们还使用 `@NamedNativeQueries` 注解标记出存储过程。

```java
// Employee.java
@NamedNativeQueries({
    @NamedNativeQuery(
        name = "callEmployeeStoreProcedure",
        query = "CALL GetEmployees(:employeeId)",
        resultClass = Employee.class
    )
})
@Entity
@Table(name = "employee")
public class Employee implements java.io.Serializable {
    ...
}
```

调用方式：

```java
Query query = session.getNamedQuery("callEmployeeStoreProcedure")
    .setParameter("employeeId", "1234");
List result = query.list();
for(int i=0; i<result.size(); i++) {
    Employee employee = (Employee)result.get(i);
    System.out.println(employee.getEmployeeCode());
}
```

## 222. 什么是 Hibernate 中的 Criteria API？

Criteria 是 Hibernate 中一种简化的 API，通过创建 `Criterion` 对象从数据库中获取实体。

对于搜索功能来说是一种非常直观且方便的方法。用户可以为搜索实体指定不同的查询标准，Criteria API 可以处理这些标准。

`Criterion` 实例是通过 `Restrictions` 上的工厂方法获得的。

## 223. 为什么我们使用 HibernateTemplate？

这是一个陷阱题。`HibernateTemplate` 已经被弃用了（deprecated）。早些使用 `HibernateTemplate` 有很好的理由。但现在的趋势已经转变为不再使用它。

## 224. 如何在控制台上查看 Hibernate 生成的 SQL 代码？

要显示 Hibernate 生成的 SQL，我们需要开启 `show_sql` 标志。

可以在 Hibernate 配置中如下实现：

```xml
<property name="show_sql">true</property>
```

## 225. Hibernate 支持哪些不同类型的集合？

Hibernate 支持以下两种类型的集合：

- 索引集合（Indexed Collections）：`List` 和 `Maps`
- 排序集合（Sorted Collections）：`java.util.SortedMap` 和 `java.util.SortedSet`

## 226. Hibernate 中 session.save() 和 session.saveOrUpdate() 方法之间有什么区别？

`save()` 方法首先在数据库中存储一个对象。然后通过分配生成的标识符来持久化给瞬态实例（transient instance）。最后，它返回刚刚创建的实体的 id。

`saveOrUpdate()` 方法调用 `save()` 或 `update()` 方法。它根据标识符是否存在选择这些方法之一。

如果实体存在标识符，则调用 `update()` 方法。如果实体没有标识符，则如前调用 `save()` 方法。

## 227. Hibernate 框架相比 JDBC 有哪些优势？

Hibernate 相比 JDBC 的主要优势如下：

- **数据库可移植性（Database Portability）**：Hibernate 可以用于多种类型的数据库且具有易于移植性。在 JDBC 中，开发者必须编写特定数据库的原生查询。这些原生查询会降低代码的数据库可移植性。
- **连接池（Connection Pool）**：Hibernate 很好地处理连接池。JDBC 需要由开发者定义连接池。
- **复杂性（Complexity）**：Hibernate 通过其 Criteria 等内部 API 很好地处理复杂的查询场景。因此开发者不需要掌握编写复杂 SQL 查询的专家。在 JDBC 应用中，开发者需要编写大部分查询。

## 228. 如何在 Hibernate 中获取 SessionFactory 的统计信息？

在 Hibernate 中，我们可以通过 `Statistics` 接口获取 `SessionFactory` 的统计信息。我们可以获取诸如关闭语句计数、集合获取计数、集合加载计数、实体插入计数等信息。

## 229. Hibernate 中对象的瞬态态（Transient state）是什么？

当一个对象仅使用 `new` 操作符实例化但未与 Hibernate `Session` 关联时，该对象就处于瞬态态。

在瞬态态下，对象在数据库中没有持久化表示。此外，瞬态态下的对象没有被分配标识符。

如果没有引用指向它，处于瞬态态的对象可以被垃圾回收。

## 230. Hibernate 中对象的离线态（Detached state）是什么？

如果一个对象早些时候是持久化的，但现在其对应的 `Session` 已关闭，则该对象处于离线态。

对该对象的任何引用仍然有效。我们甚至可以更新此对象。之后我们甚至可以将离线态的对象附加到新会话并使其持久化。

离线态在应用程序事务中非常有用，用户需要一些时间来完成工作。

## 231. Hibernate 中脏数据检查（Dirty Checking）的作用是什么？

脏数据检查是 Hibernate 用于写入数据库操作的一个非常实用的功能。Hibernate 会监控所有持久化对象的任何变化。它可以检测出一个对象是否被修改过。

通过脏数据检查，只有对象中那些需要更改的字段才会被更新。这减少了耗时的数据库写操作时间。

## 232. Hibernate 中回调接口（Callback interface）的目的是什么？

Hibernate 中的回调接口主要用于接收来自对象的不同事件的通知。

例如，我们可以使用回调在对象加载到数据库或从数据库中移除时获取通知。

## 233. Hibernate 中有哪些不同的 ORM 级别？

Hibernate 中有以下四种不同的 ORM 级别：

- **纯关系型 ORM（Pure Relational ORM）**：在此级别，整个应用程序围绕关系模型设计。此级别下的所有操作都是基于 SQL 的。
- **轻量对象映射（Light Object Mapping）**：在此级别，实体类被手动映射到关系表。业务逻辑代码与数据访问代码分离。实体数量较少的应用程序使用此级别。
- **中级对象映射（Medium Object Mapping）**：在这种情况下，应用程序围绕对象模型设计。大部分 SQL 代码在编译时生成。对象之间的关联由持久化机制支持。使用面向对象的表达式语言来指定查询。
- **全对象映射（Full Object Mapping）**：这是最复杂的级别之一。它支持组合、继承和多态。它透明地为应用程序实现了高效的获取和缓存策略。

## 234. 配置 Hibernate 应用程序的哪些方式？

配置 Hibernate 主要有两种方式：

- **基于 XML**：我们可以在像 `hibernate.cfg.xml` 等 XML 文件中定义 Hibernate 配置。
- **基于编程的**：我们也可以使用代码逻辑来配置 Hibernate。

## 235. Hibernate 中的查询缓存（Query Cache）是什么？

Hibernate 提供查询缓存来提高具有相同参数多次运行查询的性能。

有时缓存会降低事务处理的性能。在 Hibernate 中查询缓存默认是禁用的。

## 236. Hibernate 支持哪些不同的关联映射（Association mappings）？

Hibernate 支持以下四种关联映射：

- **单向关联（Unidirectional association）**：这种关联在一个方向上工作。基于连接表的关联。
- **双向关联（Bidirectional association）**：这种关联在两个方向上工作。基于连接表的关联。

## 237. Hibernate 中单向关联映射有哪些类型？

在 Hibernate 中可能有以下三种类型的单向关联映射：

- 多对一（Many to one）
- 一对一（One to one）
- 一对多（One to many）

## 239. 在 Hibernate 中，对象如何进入离线态（Detached state）？

一旦附加到对象的 `Session` 关闭，该对象就会进入离线态。处于离线态的对象可以在稍后的某个时间被附加到另一个会话。

## 240. 在 Hibernate 中如何对 Criteria 返回的结果进行排序？

Hibernate 提供了一个 `Order` 准则，用于对结果进行排序。这可以根据属性按升序或降序对对象进行排序。

类名为 `org.hibernate.criterion.Order`。

示例如下：

```java
List employees = session.createCriteria(Employee.class)
    .add( Restrictions.like("name", "F%"))
    .addOrder( Order.asc("name") )
    .addOrder( Order.desc("age") )
    .setMaxResults(10)
    .list();
```

## 241. Hibernate 中的 Example 准则是如何工作的？

在 Hibernate 中，我们可以创建一个具有所需属性的对象。然后我们可以使用这个对象来搜索具有相似对象的对象。此时，我们可以使用 `org.hibernate.criterion.Example` 准则。

示例：首先，我们创建一个作者为 Richard、类别为 mystery（悬疑）的示例书籍对象。然后搜索相似的图书。

```java
Book book = new Book();
book.setAuthor('Richard');
book.setCategory(Category.MYSTERY);
List results = session.createCriteria(Book.class)
    .add( Example.create(book) )
    .list();
```

## 242. Hibernate 中的事务管理是如何工作的？

在 Hibernate 中，我们使用 `Session` 接口来获取新事务。一旦获取事务，我们就可以在该事务中运行业务操作。在业务操作成功完成后，我们提交事务。如果发生失败，我们回滚事务。

示例代码如下：

```java
Session s = null;
Transaction trans = null;
try {
    s = sessionFactory.openSession();
    trans = s.beginTransaction();
    doTheAction(s);
    trans.commit();
} catch (RuntimeException exc) {
    trans.rollback();
} finally {
    s.close();
}
```

## 243. 如何在 Hibernate 中将实体/集合标记为不可变？

在 Hibernate 中，默认情况下，实体或集合是可变的。我们可以添加、删除或更新实体/集合。

要将实体/集合标记为不可变，我们可以使用以下方法之一：

- `@Immutable`: 我们可以使用 `@Immutable` 注解将实体或集合标记为不可变。
- **XML 文件**：我们也可以在 XML 文件中为实体设置属性 `mutable=false` 以使其不可变。

## 244. Hibernate 中从数据库检索对象的不同选项有哪些？

在 Hibernate 中，我们可以使用以下选项之一从数据库检索对象：

- **标识符 (Identifier)**：我们可以使用 `load()` 或 `get()` 方法并传递标识符主键从数据库获取对象。
- **HQL**：我们可以创建一个 HQL 查询并在执行查询后获取对象。
- **Criteria API**：我们可以使用 Criteria API 创建从数据库获取对象的搜索条件。
- **原生 SQL (Native SQL)**：我们可以为数据库编写原生 SQL 查询，只需执行它即可获取所需数据并转换为所需的对象。

## 245. 如何在 Hibernate 中自动生成主键？

在 Hibernate 中持久化对象时，我们可以使用类型为 `GenerationType.AUTO` 的主键生成策略自动生成主键。

```java
@Id
@GeneratedValue(strategy=GenerationType.AUTO)
private int id;
```



在持久化时我们可以将其留为 `null`/`0`，Hibernate 会自动为我们生成主键。

有时，`AUTO` 策略指的是 `SEQUENCE` 而不是 `IDENTITY`。

## 246. 在 Hibernate 中如何重新挂载处于游离状态（Detached）的对象？

我们可以调用 `Session.update()`、`Session.saveOrUpdate()` 或 `Session.merge()` 方法之一，在 Hibernate 中将游离状态的对象重新挂载到另一个会话。

## 247. Hibernate 中的一级缓存是什么？

Hibernate `Session` 是事务中持久化数据的一级缓存。

二级缓存位于 JVM 或 `SessionFactory` 级别。

## 248. Hibernate 中提供了哪些不同的二级缓存？

在 Hibernate 中，我们可以使用不同的缓存提供程序在 JVM/`SessionFactory` 级别实现二级缓存。

其中一些包括：

- `Hashtable`
- `EHCache`
- `OSCache`
- `SwarmCache`
- `JBoss Cache 1.x`
- `JBoss Cache 2`

## 249. Hibernate 中默认的事务工厂是哪一个？

在 Hibernate 中，默认的事务工厂是 `JDBCTransactionFactory`。但我们可以通过设置属性 `hibernate.transaction.factory_class` 来更改它。

## 250. 在 Hibernate 中禁用二级缓存的选项有哪些？

这是一个陷阱题。默认情况下，Hibernate 中的二级缓存已经是禁用的。

如果你的项目使用了二级缓存，你可以使用以下选项之一禁用 Hibernate 中的二级缓存：

- 我们可以将 `hibernate.cache.use_second_level_cache` 设置为 `false`。
- 我们可以使用 `CacheMode.IGNORE` 来停止 `Session` 与二级缓存之间的交互。`Session` 只有在发生更新时才会与缓存交互以失效缓存项。

## 251. Hibernate 中不同的获取策略（Fetching Strategies）有哪些？

从 Hibernate 3 开始，有以下获取策略来检索关联对象：

- **关联获取 (Join fetching)**：在 Join 策略中，Hibernate 使用外连接（`OUTER join`）在同一个 `SELECT` 语句中检索关联的实例或集合。
- **选择获取 (Select fetching)**：在 Select 策略中，Hibernate 使用独立的 `SELECT` 来检索关联的集合。
- **子查询获取 (Subselect fetching)**：在 Subselect 策略中，Hibernate 使用单个 `SELECT` 来检索上一个查询中所有实体的集合。
- **批量获取 (Batch fetching)**：在 Batch 策略中，Hibernate 通过指定主键来批量检索实例。

## 252. 立即加载（Immediate fetching）和懒性加载（Lazy fetching）之间的区别是什么？

在即时加载中，关联、集合或属性在加载所有者的同时被检索。但在懒性加载中，只有在调用集合时集合才会被检索。这是 Hibernate 中集合的默认获取策略。

## 253. Hibernate 中的什么是“额外懒性加载”（Extra lazy fetching）？

在额外懒性加载中，只有在需要时才会从数据库检索集合的单个元素。对于大型对象集合，这是一种很好的获取策略。

## 254. 在懒性初始化下如何检查集合是否已初始化？

Hibernate 提供了两个方便的方法 `Hibernate.initialize()` 和 `Hibernate.isInitialized()` 来检查集合是否已初始化。通过使用 `Hibernate.initialize()` 我们可以强制初始化集合。

## 255. Hibernate 中缓存映射的不同策略有哪些？

Hibernate 提供了以下缓存映射策略：

- **只读 (Read only)**：如果应用程序只需要读取操作的缓存而写入操作不需要，则可以使用此策略。它非常简单且能提供很好的性能收益。在集群环境中使用也是安全的。
- **读写 (Read/Write)**：如果应用程序还需要写入操作的缓存，则使用 Read/Write 策略。如果对序列化事务隔离级别有要求，则不应使用读写缓存策略。如果要在集群环境中使用它，我们需要实现锁定机制。
- **非严格读写 (Nonstrict Read/Write)**：如果应用程序偶尔更新数据，则可以使用此策略。它不能用于有序列化事务隔离级别要求的系统。
- **事务型 (Transactional)**：该策略支持完全事务支持的缓存提供程序，如 `JBoss TreeCache`。

## 256. Hibernate 中 Set 和 Bag 的区别是什么？

Hibernate 中的 `Bag` 是一个无序集合。它可以包含重复元素。当我们把对象持久化到 `Bag` 中时，不保证 `Bag` 会保持任何顺序。

Hibernate 中的 `Set` 只能存储唯一对象。如果我们第二次向 `Set` 添加相同的元素，它只会替换旧元素。

## 257. 我们如何监控应用程序中 Hibernate 的性能？

我们可以通过以下方式来监控 Hibernate 性能：

- **监控 SessionFactory**：由于一个应用程序中只有一个 `SessionFactory`，我们可以通过收集 `SessionFactory` 的统计信息来监控性能。Hibernate 提供了 `sessionFactory.getStatistics()` 方法来获取 `SessionFactory` 的统计数据。

  Hibernate 也可以使用 JMX 发布指标。

- **指标（Metrics）**：在 Hibernate 中，我们还可以收集其他指标——打开的会话数、检索的 JDBC 连接、缓存命中、未命中等。

  这些指标可以对 Hibernate 的性能提供极佳的洞察。我们可以根据这些指标来调整 Hibernate 的设置和策略。

## 258. 我们如何检查 Hibernate 中的对象是处于持久态（Persistent）、离散态（Detached）还是瞬态（Transient）状态？

我们可以使用以下方法来检查 Hibernate 中对象的状态：

- **持久态（Persistent State）**：如果调用 `EntityManager.contains(object)` 返回 `true`，则该对象处于持久态。
- **离散态（Detached State）**：如果调用 `PersistenceUnitUtil.getIdentifier(object)` 返回标识符属性，则该对象处于离散态。
- **瞬态（Transient State）**：如果调用 `PersistenceUnitUtil.getIdentifier(object)` 返回 `null`，则对象处于瞬态。

我们可以从 Hibernate 的 `EntityManagerFactory` 获取 `PersistenceUnitUtil`。

## 259. 映射中的“关联的反向端（the inverse side of association）”是什么？

让我们考虑这样一个例子：一个客户可以有多个订单，而每个订单必须有一个客户。

在面向对象（OO）世界中，客户是订单的所有者。在 SQL 世界中，订单有一个对客户 ID 的引用。

这是一个从客户到订单的双向一对多映射。

在这个映射中，反向端是对象的所有者。在这种情况下，客户是订单的所有者。因为没有客户的订单是不存在的。但客户在没有订单的情况下也可以存在。

此外，客户没有用于保存订单数据的列。但订单表可以存储客户 ID，并被用于映射。

## 260. 什么是 ORM 元数据？

ORM 使用元数据进行其内部工作。ORM 维护元数据以生成用于访问列和表的代码。

ORM 将类映射到表并将这些信息存储在元数据（Metadata）中。它将类中的字段映射到表的列。这类映射也是元数据的一部分。

应用程序开发者还可以通过 `ClassMetadata` 和 `CollectionMetadata` 接口以及类型层次结构来访问 Hibernate 元数据。

## 261. Hibernate 中 `load()` 和 `get()` 方法有什么区别？

在 Hibernate 中，`load()` 和 `get()` 方法的功能非常相似。

主要的区别在于，如果在数据库中没有找到与对象对应的行，`load()` 方法将抛出 `ObjectNotFoundException`。

另一方面，当数据库中未找到对象时，`get()` 方法返回 `null` 值。

建议我们在我们确定对象存在于数据库中时才使用 `load()` 方法。

## 262. 我们应该在什么时候使用 Hibernate 的 `get()` 方法或 `load()` 方法？

作为一个经验法则，我们可以遵循以下指南：

- 当我们需要加载一个对象时，应该使用 `get()` 方法。
- 当我们需要一个对象的引用但不想运行额外的 SQL 查询时，应该使用 `load()` 方法。

## 263. 什么是 Hibernate 中的派生属性（derived property）？

在 Hibernate 中，派生属性不映射到数据库表的任何列上。

派生属性是通过评估表达式在运行时计算的。

这些是只读属性。

例如：在这个例子中，`profitMargin` 是由 `salePrice` 和 `buyPrice` 派生的。

```xml
<property name="profitMargin" formula="( SELECT (i.salePrice - i.buyPrice) FROM item i WHERE i.Id = Id)"/>
```

## 264. 如何在 Hibernate 中使用命名查询（Named Query）？

命名 SQL 查询是与字符串名称关联的 HQL 查询，可以通过名称在应用程序中引用。

它可以通过以下方式使用：

- **XML 映射文件**：我们可以在 XML 映射文件中定义它。

```xml
<query name="findBookByAuthor">
<![CDATA[from Book s where s.author = :author]]>
</query>
```

- **注解（Annotation）**：我们也可以用注解标记命名 SQL。

```java
@NamedQueries({
    @NamedQuery(
        name = "findBookByAuthor",
        query = "from Book s where s.author = :author"
    )
})
```



## 265. Hibernate 中的两种锁定策略是什么？

Hibernate 中有两种常用的锁定策略：

- **乐观锁（Optimistic）**：在乐观锁中，我们假设多个事务可以完成且互不影响。因此，我们让事务在初始不锁定资源的情况下工作。在提交之前，我们检查是否有任何资源被另一个事务修改过，如果有则抛出异常并回滚事务。

- **悲观锁（Pessimistic）**：在悲观锁中，我们假设并发事务在处理相同资源时会冲突。因此，事务必须首先获取其想要更新的资源的锁。只有在之前的事务释放锁后，另一个事务才能继续处理该资源。

## 266. Hibernate 中版本号（version number）的作用是什么？

版本号用于 Hibernate 中的乐观锁。当一个事务修改对象时，它会增加其版本号。根据版本号，第二个事务可以确定它早些时候读取的对象是否发生了变化。如果写入时的版本号与读取时的版本号不同，我们就不应该提交事务。

## 267. Hibernate 中 `session.lock()` 的作用是什么？

`session.lock()` 是 Hibernate 中一个已弃用的方法。我们不应该使用它。相反，我们应该调用 `buildLockRequest(LockMode).lock(entityName, object)`。

## 268. Hibernate 支持哪些继承策略？

Hibernate 支持类与表之间的以下继承策略：

- **按类层次结构表（Table per class hierarchy）**：在多种类型书籍的情况下，我们可以有一个类和一张表。我们将 `HardCoverBook`、`PaperBook` 等所有子类存储在同一个表中。但我们可以通过 `BookType` 列来识别子类。

- **按子类表（Table per subclass）**：在这种情况下，我们为每种书籍准备一张单独的表。`HardCoverBook` 表对应 `HardCoverBook` 类，`PaperBook` 表对应 `Book` 类，并且有一个父表 `Book`。

- **按具体类表（Table per concrete class）**：在这种情况下，我们也为每种书籍准备了单独的表。在这种情况下，每个表中都包含继承属性。`Book` 类没有父表，因为它不是一个具体类。

## Maven

## 269. 什么是 Maven？

Maven 是一个软件项目管理工具。它是来自 Apache 软件基金会的开源软件。它用于软件项目的构建、报告和文档编制。它主要基于 POM（项目对象模型）。

## 270. Maven 的主要功能有哪些？

Maven 的主要功能包括：

- **简单**：Maven 提供了基于最佳实践的简单项目设置。
- **快速**：在 Maven 中几秒钟内即可启动新项目或模块。
- **易学**：Maven 的用法和命令在所有项目中都是易于学习的。因此，新开发者的上手时间非常短。
- **依赖管理**：Maven 提供了卓越的依赖管理，包括自动更新和传递性依赖。
- **多项目**：你可以使用 Maven 同时处理多个项目。
- **大型库**：Maven 拥有一个大型且不断增长的库和元数据可以开箱即用。
- **可扩展**：Maven 支持使用 Java 或脚本语言轻松编写插件，以扩展其核心功能。
- **即时**：Maven 是在线的，它通过极少的配置即可即时访问新功能。

## 271. 你可以使用 Maven 管理项目的哪些领域？

Maven 帮助我们管理项目的以下领域：

1. 构建 (Build)
2. 测试 (Testing)
3. 发布 (Release)
4. 报告 (Reporting)
5. 软件变更管理 (SCM)
6. 文档 (Documentation)
7. 分发 (Distribution)

## 272. Maven 的主要优势有哪些？

Maven 在软件开发方面有很多优势。一些主要优势包括：

1. **通用的项目结构**：通过使用 Maven，每个开发者都拥有通用的项目结构，这有助于理解代码以及在新项目中开发新功能。
2. **模块化设计**：Maven 促进模块化设计，将复杂的项目拆分为多个易于管理的模块。通过 Maven，可以更容易管理用于构建、测试、发布等的多个模块。
3. **集中化依赖管理**：通过 Maven，每个开发者不再需要在每个项目或模块中单独包含 jar 包。Maven 提供了集中化的依赖管理，可以帮助提高软件开发的效率。
4. **减少决策**：通过 Maven，开发者必须对与软件开发工作无关的事做出更少的决策。项目结构随 Maven 准备就绪，依赖管理是一种统一的方法，且构建/发布由 Maven 处理。因此，开发者可以专注于软件开发的核心工作。

## 273. 为什么我们说“Maven 使用契约优于配置”？

契约优于配置 (Convention over configuration) 是一种软件设计范式，它在不丢失灵活性的情况下减少了软件开发者所做的决策数量。在 Maven 中，对于设置项目、构建构件、运行单元测试和发布代码有许多约定。这些约定导致了软件开发的通用流程。在其他工具中，存在很多配置选项。但大多数情况下，开发者使用同一组配置选项。因此，将这些设为默认选项更好。Maven 使用来自最佳实践的默认选项，并为软件开发提供了正确的约定。

## 274. 像 Maven 这样的构建工具职责是什么？

像 Maven 这样的构建工具帮助我们完成以下任务：

1. **源代码**：构建工具可以根据模板生成源代码。
2. **文档**：我们可以使用构建工具从源代码中获取文档文件。例如 Javadoc。
3. **编译**：构建工具的主要职责是将源代码编译成可执行代码。
4. **打包**：构建工具将编译后的代码打包成可部署的文件，如 jar、zip、war 等。
5. **部署**：我们可以使用构建工具将包好的代码部署到服务器上。

## 275. Ant 和 Maven 之间有什么区别？

Ant 和 Maven 之间的主要区别：

1. **Ant** 是一个用于构建过程的 Java 库和命令行工具箱。**Maven** 是一个软件开发许多方面的框架，如项目设置、编译、构建、文档等。
2. **Ant** 对项目结构或构建过程没有任何约定。**Maven** 对设置项目结构以及构建过程都有约定。
3. **Ant** 基于过程化编程。我们必须为编译、构建、复制等编写代码。**Maven** 基于声明式编程。我们只需要为我们的项目设置和编程对其进行配置即可。
4. **Ant** 不强制执行任何生命周期。我们需要手动创建任务序列。**Maven** 拥有用于软件构建过程的生命周期。在 Maven 中我们有定义良好的阶段可以使用。
5. **Ant** 脚本无法在多个项目间复用。**Maven** 拥有可以在多个项目间复用的插件。

## 276. Maven 中的 MOJO 是什么？

MOJO 代表 Maven plain Old Java Object（普通 Java 对象）。每个 MOJO 都是 Maven 中的一个可执行目标。它就像一个注解 Java 类。它指定了关于目标的元数据，如名称、目标的生命周期阶段以及目标所需的参数。一个 Maven 插件可以包含多个 MOJO。

## 277. Maven 中的 Repository 是什么？

仓库是文件系统上的一个位置，用于存储构建构件、jars、依赖和 pom.xml 文件。

## 278. Maven 有哪些类型的仓库？

Maven 中主要有三种类型的仓库：

1. **本地仓库 (Local Repository)**：这是你的本地文件夹，其中存储了安装和依赖的副本。
2. **远程仓库 (Remote Repository)**：这是一个远程文件夹，存储了 jars 和其他构建构件。它们可以位于组织内部的服务器上。
3. **中央远程仓库 (Central Remote Repository)**：这是 Maven 中央仓库，位于 repo.maven.apache.org 或 uk.maven.org 或任何其他第三方位置。在这里我们可以找到来自不同提供者的构件，供下载和使用。如 Hibernate、Spring 库等。

## 279. Maven 中的本地仓库是什么？

Maven 本地仓库是你本地文件系统中的一个文件夹，项目安装、依赖 jars、插件等都存储在其中。Maven 本地仓库的默认位置是 `.m2` 文件夹。它可能位于文件系统的以下位置：

- Windows – `C:\Documents and Settings\{ username }\.m2`
- Unix/Linux/Mac – `~/.m2`

## 280. Maven 中的中央仓库是什么？

Maven 中央仓库是一个真正的远程仓库，位于 repo.maven.apache.org 或 uk.maven.org 或任何其他第三方位置。它包含了由各种软件提供的 jars 和构件。在此阶段，Maven 将最终的包复制到远程仓库，以便与其他开发者和项目共享。

## 281. Maven 中的远程仓库是什么？

远程仓库是互联网上的一个位置，用于存储构建构件。这些文件可以通过 `file://` 或 `http://` 协议访问。仓库是文件系统上的一个位置，存储构建构件、jars 和 pom.xml 文件。

## 282. 为什么我们不应该将 jars 存储在 CVS 或其他版本系统中？

Maven 建议将 jars 存储在本地仓库而不是 CVS：

- **节省空间**：仓库很大。
- **更快检出**：如果本地存在，检出会更快。
- **不需要版本控制**：外部依赖并不频繁更改。

## 283. 任何人都可以上传 jars 到中央仓库吗？

不可以，向中央仓库上传 jars 需要特殊权限。

## 284. 什么是 POM？

POM 是 Project Object Model（项目对象模型）的缩写。它是 Maven 的工作单元。名为 `pom.xml` 的 XML 文件。它包含了项目细节和 Maven 构建项目所需的配置。它包含了许多项目的默认值。例如 `target` 是 Java 项目的构建目录。

## 285. 什么是 Super POM？

Super POM 是 Maven 的默认 POM。所有的 POM 文件都继承自 Super POM。

## 286. POM 文件的主要必需元素有哪些？

每个 POM 文件应该包含以下必需元素：

1. `project`（项目根）
2. `modelVersion`（模型版本）
3. `groupID`：项目组的 ID
4. `artifactID`：构件（项目）的 ID
5. `version`：指定组下的构件版本

## 287. Maven 构建生命中有哪些阶段？

在 Maven 中，每个构建生命周期由许多阶段组成。默认构建生命周期包括：

1. **validate（验证）**：在此阶段，Maven 验证项目是否正确以及运行下一个阶段所需的信息。
2. **compile（编译）**：Maven 在此阶段编译项目源代码。
3. **test（测试）**：此阶段对编译后的源码运行单元测试。运行这些测试通常不需要打包或部署代码。
4. **package（打包）**：在此阶段，Maven 将编译后的代码打包成可分发格式，如 JAR。
5. **verify（验证）**：Maven 对集成测试的结果进行任何检查以确保符合质量标准。
6. **install（安装）**：在此阶段，Maven 将包安装到本地仓库。之后它可以在本地的其他项目中作为依赖使用。
7. **deploy（部署）**：在构建环境中，Maven 将最终的包复制到远程仓库，以便与其他开发者和项目共享。

## 288. 使用使用什么命令来打包你的 Maven 项目？

为了将项目打包成可分发的格式，我们使用以下命令：

```
mvn package
```

## 289. Maven 项目全限定构品名称的格式是什么？

Maven 项目的构件名称格式如下：

`<groupId>:<artifactId>:<version>`

以下是一些组织使用的惯例：

**父级 pom (Parent pom)**

- groupid: `org.Orgname.Projectname`
- artifactId: `org.Orgname.Projectname`
- version: `x.x.x`

例如 `org.Orgname.Projectname:org.Orgname.Projectname-1.0.0.pom`

**模块 (Modules)**

- groupid: `org.Orgname.Projectname`
- artifactid: `org.Orgname.Projectname.Modulename`
- version: `x.x.x`

例如 `org.Orgname.Projectname:org.Orgname.Projectname.Modulename-1.0.0.jar`

## 290. 什么是 Maven 中的 Archetype？

根据官方定义，Archetype 是一个 Maven 项目模板工具包。通过使用 Archetype，Archetype 的作者可以创建一个项目模板。该项目模板（archetype）的用户可以向此模板传递不同的参数并开始使用它。Archetype 促进了创建和开发项目过程的一致性。它还有助于缩短新开发者加入项目的上手时间。

## 291. Maven 中生成 Archetype 的命令是什么？

在 Maven 中，我们可以使用以下命令来生成 Archetype：

```
mvn archetype:generate
```

## 292. Maven 的三个主要构建生命周期是什么？

Maven 拥有以下三个构建生命周期，每个生命周期进一步包含多个阶段：

1. **clean**：在此生命周期中，之前构建生成的任何文件都将被删除。
2. **default**：该生命周期用于验证、编译和创建应用程序。它包含多个阶段，如 compile、test、package。
3. **site**：Maven 在此阶段生成并部署站点的文档。

## 293. Maven 插件（plugin）的主要用途是什么？

Maven 主要是一个插件执行框架。在 Maven 的代码中，所有工作都由插件完成。Maven 插件可以用于以下目的：

1. 清理代码
2. 编译代码
3. 创建 JAR 文件
4. 部署构件
5. 运行单元测试
6. 项目文档化
7. 生成项目站点
8. 生成 WAR 文件
9. 生成 checkstyle 报告

## 294. 你如何找到正在使用的插件版本？

Maven Help Plugin 有一个 `describe` 目标。它可以用于列出插件的版本。示例命令为：

```
mvn -Dplugin=install help:describe
```

注意：在上述命令中，将 `-Dplugin` 替换为插件的前缀作为参数。不要在此处使用插件的 artifact ID。

## 295. Maven 中哪些不同类型的配置方案（profile）？在何处定义这些配置方案？

在 Maven 中，我们可以有以下类型的 Profile：

- **项目级 (Per Project)**：定义在 POM 本身（`pom.xml`）中。
- **用户级 (Per User)**：我们可以在 Maven-settings（`%USER_HOME%/.m2/settings.xml`）中定义它。
- **全局 (Global)**：定义在全局 Maven-settings（`${maven.home}/conf/settings.xml`）中。
- **Profile 描述符 (Profile descriptor)**：描述符位于项目根目录（`profiles.xml`）（Maven 3.0 不支持此项）。

## 296. Maven 中哪些不同的配置文件？在何处找到这些文件？

Maven 使用非常简单。其核心部分有一个名为 `settings.xml` 的配置文件。该文件包含 `setting` 元素，用于用不同的选项配置 Maven。找到此文件的主要位置有：

- Maven 安装目录：`${maven.home}/conf/settings.xml`
- 用户主目录：`${user.home}/.m2/settings.xml`

## 297. 我们在 settings.xml 中可以找到哪些元素？

在 `settings.xml` 中我们可以拥有 Maven 的所有配置信息。一些重要的元素是：

- **localRepository**：该元素的值为此构建系统本地仓库的路径。默认值为 `${user.home}/.m2/repository`。它用于主构建服务器，允许所有登录用户从共同的本地仓库进行构建。
- **interactiveMode**：如果为 true，则 Maven 尝试与用户交互以获取输入。如果为 false，则 Maven 不与用户交互。默认设置为 true。
- **usePluginRegistry**：如果为 true，Maven 使用 `${user.home}/.m2/plugin-registry.xml` 文件来管理插件版本。默认是 false。
- **offline**：如果为 true，则此构建系统应该能够在离线模式运行。默认是 false。此元素用于由于网络设置或安全原因无法连接到远程仓库的构建服务器。

## 298. 你如何检查系统中的 Maven 版本？

我们可以在控制台中使用以下命令来检查系统中的 Maven 版本：

```
mvn -version
```



## 299. 你如何验证 Windows 上是否安装了 Maven？

要检查这一点，在 Windows 的命令提示符中输入 `mvn -version`。这将给出 Windows 上安装的 Maven 版本。

## 300. 什么是 Maven 构件（artifact）？

Maven 构件是被部署到 Maven 仓库的文件。在大多数情况下它是一个 JAR 文件。

当 Maven 构建运行时，它产生一个或多个构件。对于 Java 项目，它产生编译 jar 和源码 jar。

每个 Maven 构件都有 group ID、artifact ID 和一个版本字符串。这三个属性唯一地标识一个构件。

在 Maven 中，我们指定项目的依赖作为构件。

## 301. Maven 中有哪些不同的依赖范围（scopes）？

Maven 支持以下依赖范围：

*   **compile**: 这是 Maven 的默认依赖范围。编译级依赖在项目的所有类路径可用。这些依赖也会传递给依赖项目。
*   **provided**: 该范围与 compile 类似。但在该范围下，我们期望 JDK 或容器在运行时提供依赖。例如构建 Java Web 应用时，我们可以将 Servlet API 和相关的 API 设置为 provided。Web 容器将在运行时提供这些类。该范围仅在编译和测试类路径可用，且不是传递性的。
*   **runtime**: 该依赖不需要编译，但执行需要。它在运行时和测试类路径可用。在编译类路径中不存在。
*   **test**: 该范围用于测试编译和执行阶段所需的依赖。该范围不是传递性的。
*   **system**: 该范围与 provided 范围相同，但必须显式提供它的 JAR。在这种情况下，构件始终可用。不需要在仓库中查找。
*   **import**: 该范围仅用于 `<dependencyManagement>` 节类型为 pom 的依赖。在这种情况下，指定的 POM 必须被该 POM 的 `<dependencyManagement>` 节中的依赖所替换。此范围仅在 Maven 2.0.9 或更高版本可用。

## 302. 我们如何在 Maven 中排除依赖？

要排除依赖，我们可以在 pom 的 `<dependency>` 节下添加 `<exclusions>` 标签。

例如：

```xml
<dependencies>
  <dependency>
    <groupId>test.ProjectX</groupId>
    <artifactId>ProjectX</artifactId>
    <version>1.0</version>
    <scope>compile</scope>
    <exclusions>
      <exclusion><!-- 在此处提及排除项 -->
        <groupId>test.ProjectY</groupId>
        <artifactId>ProjectY</artifactId>
      </exclusion>
    </exclusions>
  </dependency>
</dependencies>
```

## 304. 什么是 Maven 中的传递依赖（transitive dependency）？

假设你有一个项目 A 依赖项目 B。项目 B 进一步依赖项目 C。那么项目 C 就是你项目 A 的传递依赖。

在 Maven 中，从 2.0 版本开始，你不需要指定传递依赖。你只需要在 `pom.xml` 中列出你的直接依赖即可。

Maven 会处理传递依赖的解析并自动包含它们。

## 305. 什么是 Maven 中的排除依赖（Excluded dependencies）？

假设项目 A 依赖于项目 B，而项目 B 依赖项目 C。项目 A 的开发者可以显式地排除项目 C 作为依赖。我们可以使用 "exclusion" 元素来排除它。

此类依赖在 Maven 中被称为排除依赖（Excluded dependencies）。

## 306. 什么是 Maven 中的可选依赖（Optional dependencies）？

假设项目 B 依赖于项目 C。项目 B 的开发者可以使用 "optional" 元素将项目 C 标记为可选依赖。

如果项目 A 依赖于项目 B，那么 A 将仅依赖 B 而不依赖 B 的可选依赖 C。

项目 A 的开发者随后可以显式地添加对 C 的依赖。B 对 C 的依赖在 Maven 中被称为可选依赖（Optional dependency）。

## 307. 成功编译 Maven 项目后，可以在哪里找到类文件（class files）？

一旦 Maven 成功完成编译，它会将文件存储在 `target` 文件夹中。类文件的默认位置是：

```
${basedir}/target/classes/
```

## 308. Maven 中源码、测试和构建目录的默认位置是什么？

默认位置如下：

*   源码（Source）：`src/main/java`
*   测试（Test）：`src/test/java` (注：原文为 src/main/test，标准约定为 src/test/java)
*   构建（Build）：`target`

## 309. Maven 中 jar:jar 目标的结果是什么？

在 Maven 中，`jar:jar` 目标会在 Maven 构建目录中创建一个 jar 文件。Jar 文件的命名格式为 `${project.id}-${project.currentVersion}.jar`。

`id` 和 `currentVersion` 在正在构建的项目的 `project.xml`（现通常为 `pom.xml`）中进行了定义。

`jar:jar` 不会重新编译源码。它只是从已经编译的类文件中创建一个 jar 包。

## 310. 我们如何从 Maven 的执行中获取调试或错误信息？

有时 Maven 的项目构建或编译会失败。此时，查看 Maven 执行时的调试或错误信息非常有帮助。

要获取调试信息，我们可以带 `-X` 选项调用 Maven。

要获取错误/异常信息，我们可以带 `-e` 选项调用 Maven。

## 311. Maven 中 Release 版本（发布版本）和 SNAPSHOT 版本（快照版本）的区别是什么？

Maven 中的 SNAPSHOT 版本是尚未发布的版本。

在每个发布版本之前都有一个 SNAPSHOT 版本。在 1.0 版本发布之前，会有 1.0-SNAPSHOT。

如果我们今天下载 1.0-SNAPSHOT，我们获得的文件集可能与昨天下载的不同。由于 SNAPSHOT 版本正处于开发中，其内容可能会不断发生变化。

但发布版本在每次下载时始终提供完全相同的一组文件。

## 312. 你如何在 Maven 中运行测试类（test classes）？

我们需要使用 Surefire 插件来运行 Maven 中的测试类。

要运行单个测试，可以调用以下命令：

```
mvn -Dtest=TestCaseA test
```

我们也可以使用模式来运行多个测试用例：

```
mvn -Dtest=TestCase* test
```

或者

```
mvn -Dtest=TestCaseA,TestCaseB,TestImportant* test
```

## 313. 有时 Maven 编译了测试类但没有运行它们？可能是什么原因？

在 Maven 中，使用 Surefire 插件来运行测试。

我们可以配置它来运行特定的测试类。有时我们可能无意中在 `settings.xml` 或 `pom.xml` 中为 `${test}` 指定了错误的值。

我们需要在 `pom.xml`/`settings.xml` 中查找以下内容并修复它：

```xml
<properties>
  <property>
    <name>test</name>
    <value>some-value</value>
  </property>
</properties>
```

## 314. 如何在 Maven 中跳过测试运行？

我们可以在命令行中使用参数 `-Dmaven.test.skip=true` 或 `-DskipTests=true` 来跳过测试。

参数 `-Dmaven.test.skip=true` 会跳过测试的编译。

参数 `-DskipTests=true` 会跳过测试的执行。

Maven 的 Surefire 插件遵循这些参数。

## 315. 我们可以为 Maven 项目创建自定义的目录结构吗？

可以，Maven 赋予我们创建自定义目录结构的灵活性。我们只需要在 `pom.xml` 的 `<build>` 部分配置如 `<sourceDirectory>`、`<resources>` 等元素即可。

## 316. Gradle 和 Maven 有什么区别？

Gradle 如今变得越来越流行。Google 使用它进行 Android 开发和发布。LinkedIn 这样的公司也使用 Gradle。

Gradle 基于领域特定语言（DSL）。Maven 基于 XML。

Gradle 提供了更大的灵活性来执行类似于 ANT 的自定义任务。Maven 脚本具有预定义的结构，因此灵活性较差。

Maven 主要用于 Java 相关的项目。

## 317. Maven 中继承（Inheritance）和多模块（Multi-module）的区别是什么？

在 Maven 中，继承（Inheritance）允许子项目继承自父项目的配置。这被用于避免多个项目之间的配置重复。

多模块项目（Multi-module projects）允许多个项目在单个父项目下进行统一管理。这是通过父 `pom.xml` 中的 `<modules>` 标签实现的。

## 318. 什么是 Maven 的构建可移植性（Build portability）？

在 Maven 中，构建的可移植性衡量的是将一个特定项目并在不同环境中进行构建的难易程度。

不需要任何自定义的构建比需要大量自定义的构建具有更好的可移植性。

Apache 的开源项目是可移植性的典范。这些构建开箱即用。

## 319. 如何在 GIT 中查看最近的提交？

我们可以使用 `git log` 命令查看提交。要查看最近的三个提交，我们使用以下命令：

```
git log -3
```



# 320. 如何知道分支是否已经合并到 master？

我们可以使用以下命令来实现此目的：

- `git branch --merged master`：列出合并到 master 的分支
- `git branch --merged`：列出合并到 HEAD（即当前分支末端）的分支
- `git branch --no-merged`：列出未合并的分支

默认情况下，这适用于本地分支。

我们可以使用 `-a` 标志显示本地和远程分支。

或者使用 `-r` 标志只显示远程分支。

# 321. git stash drop 的目的是什么？

当我们不需要某个特定的储存（stash）时，使用 `git stash drop` 命令将其从保存列表中删除。

默认情况下，该命令删除最新添加的 stash。

要删除特定的 stash，需要在 `git stash drop <stashname>` 命令中指定参数。

# 322. GIT 中的 HEAD 是什么？

HEAD 是指向当前检出提交的引用。

它是我们已检出分支的符号引用。

在任何时刻，一个头会被选为“当前头”，这个头也被称为 HEAD（始终大写）。

# 323. GIT 中最流行的分支策略是什么？

GIT 中有很多分支方法。最流行的方法之一维护两个分支：

- **master**：该分支用于生产。在该分支中，HEAD 始终处于生产就绪状态。
- **develop**：该分支用于开发。在该分支中存储项目开发的最新代码。这些是开发中的代码。一旦代码准备好部署到生产环境，它将从 develop 分支合并到 master 分支。

## 324. 什么是 SubGit？

SubGit 是用于将 SVN 迁移到 Git 的软件工具。它非常易用。通过它，我们可以为 Subversion 仓库创建一个可写的 Git 镜像。

它创建了一个双向镜像，既可以推送到 Git，也可以提交到 Subversion。

SubGit 还负责 Git 和 Subversion 之间的同步工作。

## 325. git-instaweeb 的作用是什么？

Git-instaweeb 是一个脚本，通过它可以在网页浏览器中浏览 git 仓库。

它会设置 gitweb 和一个服务器，使工作仓库可以在网上访问。

## 326. 什么是 git hooks？

Git hooks 是在 Git 仓库发生事件时可以自动运行的脚本。它们被用于 GIT 中工作流的自动化。

Git hooks 还有助于自定义 GIT 的内部行为。

这些通常用于强制 GIT 提交策略。

## 327. 什么是 GIT？

GIT 是一个成熟的分布式版本控制系统 (DVCS)。它用于源码管理 (SCM)。

它是一个开源软件。由 Linux 系统的创建者 Linus Torvalds 开发。

GIT 与 Eclipse、IntelliJ 等许多集成开发环境 (IDE) 完美配合。

GIT 可以处理小型和大型项目。

## 328. GIT 中的仓库（repository）是什么？

GIT 中的仓库是存储我们软件工作的地方。

它包含一个名为 `.git` 的子目录。项目根目录下只有一个 `.git` 目录。

在 `.git` 中，GIT 存储了仓库的所有元数据。`.git` 目录的内容是仅供 GIT 内部使用的。

## 329. GIT 的主要优点有哪些？

GIT 有以下主要优点：

1. **分布式系统**：GIT 是一个分布式版本控制系统 (DVCS)。因此，你可以将私人工作保留在版本控制中，但完全对他人隐藏。你也可以进行离线工作。
2. **灵活的工作流**：GIT 允许你创建自己的工作流。你可以使用适合你项目的流程。你可以选择集中式、主从式或任何其他工作流。
3. **快速**：与其他版本控制系统相比，GIT 非常快。
4. **数据完整性**：由于 GIT 使用 SHA1，数据不容易被损坏。
5. **免费**：个人使用免费。因此，许多业余爱好者将其用于他们的初始项目。它在大型项目上运行也非常良好。
6. **协作**：对于需要协作的项目，GIT 非常易于使用。全球许多流行的开源软件都在使用 GIT。

## 330. GIT 的缺点有哪些？

GIT 的缺点非常少。这些是 GIT 难以使用的场景，其中包括：

1. **二进制文件**：如果我们的项目中有大量的二进制文件（非文本文件），那么 GIT 会变得非常慢。例如，包含大量图像或 Word 文档的项目。
2. **学习曲线陡峭**：新学者需要一些时间来学习 GIT。某些 GIT 命令对初学者来说并不直观。
3. **远程速度慢**：有时由于网络延迟，使用远程仓库会很慢。尽管如此，GIT 仍然优于其他 VCS。

## 331. GIT 和 SVN 的主要区别是什么？

GIT 和 SVN 的主要区别是：

1. **去中心化**：GIT 是去中心化的。你有一个本地副本作为一个仓库，你可以在其中进行提交。在 SVN 中，你必须始终连接到中央仓库才能提交。
2. **学习复杂**：GIT 对某些开发者来说有点难学。它有更多的概念和命令需要学习。SVN 要容易学习得多。
3. **无法处理二进制文件**：GIT 在处理频繁更改的大型二进制文件时会变慢。SVN 可以轻松地处理大型二进制文件。
4. **内部目录**：GIT 只创建 `.git` 目录。SVN 在每个文件夹中都会创建 `.svn` 目录。
5. **用户界面**：GIT 没有良好的 UI。但 SVN 有良好的用户界面。

## 332. 你将如何为项目启动 GIT？

我们在现有的项目目录中使用 `git init` 命令来启动项目的版本控制。

此后，我们可以使用 `git add` 和 `git commit` 命令将文件添加到我们的 GIT 仓库中。

## 333. GIT 中的 git clone 是什么的？

在 GIT 中，我们使用 `git clone` 命令在本地创建现有 GIT 仓库的副本。

这是开发者之间创建仓库副本最流行的方式。

它类似于 `svn checkout`。但在这种情况下，工作副本是一个功能完整的仓库。

## 334. 你将如何在 GIT 中创建仓库？

为了在 GIT 中创建一个新仓库，我们首先为项目创建一个目录。然后运行 `git init` 命令。

现在，GIT 在我们的项目目录中创建了 `.git` 目录。这就是我们新 GIT 仓库创建的方式。

## 335. 在 GIT 中工作的方式有哪些？

我们可以通过以下方式在 GIT 中开始工作：

- **新项目**：我们使用 `git init` 创建新仓库。
- **现有项目**：我们使用 `git clone` 对现有仓库进行工作。

## 336. GIT 是用什么语言写的？

大部分发行版本是用 C 语言编写的。某些命令是用 Perl 编写的。

## 337. git pull 内部执行了什么？

在 GIT 中，pull 会执行 fetch（抓取）然后执行 merge（合并）。我们使用 pull 命令让我们的本地分支与远程保持同步。

## 338. git push 内部执行了什么？

在 GIT 中，push 执行以下两个命令：

1. **fetch**：首先 GIT 将服务器上的提交复制到本地，并将 `origin/master` 指针移动到新提交上。
2. **merge**：然后将 `origin/master` 分支合并到 master 分支。

## 339. git stash 是什么？

在 GIT 中，有时我们不想提交代码，但又不想丢失。在这种情况下，我们使用 stash 命令将工作目录和索引的状态记录在 stash 中。这会清除当前分支的未提交更改。

## 340. GIT 中“stage”（暂存）的意思是什么？

在 GIT 中，stage 是提交前的步骤。stage 意味着文件已准备好提交。

假设你正在 GIT 中开发两个功能。其中一个功能已经完成，另一个还没有准备好。你想提交然后回家。但你无法提交，因为它们都没有完全准备好。在这种情况下，你可以只 stage 已就绪的功能并提交该部分。另一个功能将保持进行中。

## 341. git config 命令的作用是什么？

我们可以使用 `git config` 命令设置 GIT 安装的配置选项。

## 342. 我们如何查看 GIT 安装的配置设置？

我们可以使用 `git config --list` 命令打印 GIT 安装的所有配置设置。

## 343. 如何使用 commit 命令写入消息？

我们调用以下命令进行带消息的提交：

```
git commit -m <message>
```

## 344. GIT 提交对象内部存储了什么？

GIT 提交对象包含以下信息：

- **SHA1 名称**：标识提交的 40 位字符字符串
- **文件**：代表项目在特定时间点状态的文件列表
- **引用**：指向父提交对象的任何引用

## 345. 在 GIT 仓库中可以创建多少个 head？

仓库中可以有任意数量的 head。

默认情况下，每个 GIT 仓库中有一个被称为 HEAD 的 head。

# 346. 为什么要在 GIT 中创建分支？

如果我们同时在处理多个任务、项目、缺陷或功能，我们需要多个分支。在 GIT 中，我们可以为每个单独的目的创建一个独立的分支。

假设我们正在开发一个功能，我们为该功能创建一个功能分支（feature branch）。在此期间，我们遇到了一个需要处理的缺陷，于是为该缺陷创建另一个分支并进行处理。一旦缺陷处理完成，我们就合并该分支，并继续处理功能分支的工作。

因此，同时处理多个任务是使用多个分支的主要原因。

# 347. GIT 中可以创建哪些不同类型的分支？

在 GIT 中，我们可以出于以下目的创建不同类型的分支：

- **功能分支（Feature branches）**：用于开发某个新功能。
- **发行分支（Release branches）**：用于将代码发布到生产环境。
- **修复修复分支（Hotfix branches）**：用于针对缺陷或紧急修复向生产环境发布热修复。

# 348. 如何在 GIT 中创建一个新分支？

我们使用以下命令在 GIT 中创建新分支：

```
$ git checkout -b <branchname>
```

# 349. 如何将新功能添加到主分支（main branch）？

我们在从主分支（master branch）创建的功能分支上进行开发工作。一旦开发工作完成，我们就使用 `git merge` 命令将其合并到主分支。

# 350. 什么是 GIT 中的 pull request（拉请求）？

GIT 中的 pull request 是已推送到 GIT 仓库的更改列表。通常，这些更改被推送到功能分支或热修复分支中。在推送这些更改后，我们创建一个 pull request，其中包含主分支与我们的功能分支之间的差异。该 pull request 会发送给审核人员审核代码，然后将其合并到开发（develop）或发布（release）分支。

# 351. 什么是 GIT 中的合并冲突（merge conflict）？

GIT 中的合并冲突是合并两个提交的结果。有时，要合并的提交和当前提交的更改位于相同的位置。在这种场景下，GIT 无法判断哪个更改更重要。因此，GIT 会报告合并冲突。这意味着合并未成功。我们可能需要手动检查并解决合并冲突。

# 352. 我们如何解决 GIT 中的合并冲突？

当 GIT 报告文件存在合并冲突时，它会将相关行标记如下：

例如：
本周的工作日是

```
<<<<<<< HEAD
five
------
six
>>>>>>> branch-feature
```

要解决文件中的合并冲突，我们需要编辑文件并修复冲突的更改。在上面的示例中，我们可以保留“five”或“six”。

编辑文件后，我们运行 `git add` 命令，然后运行 `git commit` 命令。由于 GIT 已经意识到这是一个合并冲突，它会将此更改链接到正确的提交上。

# 353. 使用什么命令删除分支？

在功能分支成功合并到主分支后，我们不再需要该功能分支。

要删除不需要的分支，我们使用以下命令：

```
git branch -d <branchname>
```

# 354. 使用什么删除删除未合并更改的分支？

要强制删除带有未合并更改的不需要的分支，我们使用以下命令：

```
git branch -D <branchname>
```

# 355. GIT 中合并（merging）的替代命令是什么？

在 GIT 中合并的另一种替代方案是变基（rebasing）。它是通过 `git rebase` 命令完成的。

# 356. 什么是 GIT 中的变基（Rebasing）？

变基是将分支移动到新基准提交的过程。它就像是重写分支的历史。

在变基过程中，我们将分支从一个提交移动到另一个提交。通过这种方式，我们可以维护线性的项目历史。

一旦提交被推送到公共仓库，使用变基就不是一种良好的做法。

# 357. GIT 中的“变基黄金准则”（Golden Rule of Rebasing）是什么？

变基的黄金准则是：我们绝不应该在公共分支上使用 `git rebase`。如果其他人在使用同一个分支，他们在看到 GIT 变基后 Master 分支中的更改时可能会感到困惑。

因此，不建议在其他协作者使用的公共分支上进行变基。

# 358. 为什么我们使用交互式变基（Interactive Rebasing）代替自动变基（Auto Rebasing）？

通过使用交互式变基，我们可以在将提交移动到新分支之前对其进行修改。

这比自动变基更强大。它让我们对分支的提交历史具有完全控制。

通常，我们在将功能分支合并到主分支之前，使用交互式变基来清理混乱的提交历史。

# 359. Git 中变基的命令是什么？

Git 变基命令是：

```
git rebase <new-commit>
```

# 360. git clone 和 git remote 之间的主要区别是什么？

`git clone` 和 `git remote` 之间的主要区别在于 `git clone` 用于创建一个新的本地仓库，而 `git remote` 用于已有的仓库。

`git remote` 为现有的远程仓库添加新的引用，以跟踪后续更改。

`git clone` 通过复制另一个仓库来创建一个新的本地仓库。

# 361. 什么是版本控制？

GIT 版本控制有助于管理随时间变化的更改。它跟踪软件中所有的更改。如果我们犯了错误，可以回到过去。GIT 版本控制有助于团队进行开发。任何引入的更改都可以通过回溯时间来撤销。

# 362. 你使用什么 GUI 用于 GIT？

有很多 GIT GUI 可以使用。其中一些包括：

- GitHub Desktop
- GitKraken
- Git Cola
- SourceTree
- Git Extensions
- SmartGit
- GitUp

# 363. git diff 命令在 GIT 中的作用是什么？

在 GIT 中，`git diff` 命令用于显示两个版本之间的差异，或者索引与最新提交之间的差异。它还可以显示 blob 对象之间的差异。它有助于进行代码审查。

# 364. 什么是 rerere？

在 GIT 中，rerere 是一个隐藏功能。rerere 的全称是“reuse recorded resolution”。通过使用 rerere，GIT 会记住我们解决冲突的方式。下一次 GIT 看到相同的冲突时，它可以自动为解决。

# 365. git diff 的三个常用版本是什么？

三个最常用的 git diff 命令如下：

- `git diff`：显示工作目录与索引之间的差异。
- `git diff --cached`：显示索引与最新提交之间的差异。
- `git diff HEAD`：显示工作目录与最新提交之间的差异。

# 366. git status 命令的作用是什么？

在 GIT 中，`git status` 命令主要显示工作树的状态。它显示以下项：

1. 索引文件与当前 HEAD 提交之间存在差异的路径
2. 工作树与索引文件之间存在差异的路径
3. 工作树中未被 GIT 跟踪的路径

在上述三项中，第一项是我们可以使用 `git commit` 命令提交的项。第二项和第三项只有在运行 `git add` 命令后才能提交。

# 367. git diff 和 git status 之间的主要区别是什么？

在 GIT 中，`git diff` 显示不同提交之间的差异，或者工作目录与索引之间的差异。而 `git status` 命令只显示工作树的状态。

# 368. git rm 命令在 GIT 中的作用是什么？

在 GIT 中，`git rm` 命令用于从工作树和索引中删除文件。我们使用 `git rm -r` 递归地删除目录中的所有文件。

## 369. 应用储存（stash）的命令是什么？

有时我们想要保存未完成的工作。为了这个目的，我们使用 `git stash` 命令。当我们想要回来并从上次离开的地方继续工作时，我们使用 `git stash apply` 命令来取回未完成的工作。

因此，应用储存的命令是：

```
git stash apply
```

或者我们可以使用

```
git stash apply <stashname>
```



## 370. 为什么我们使用 `git log` 命令？

我们使用 `git log` 命令来在项目历史中搜索特定的提交。

我们可以通过作者、日期或内容搜索 git 历史。它甚至可以列出特定日期之前或之后几天完成的提交。

## 371. 为什么在 GIT 中我们需要 `git add` 命令？

GIT 为我们提供了一个非常好的功能，即在提交之前对更改进行暂存（staging）。要暂存更改，我们使用 `git add` 命令。这会将我们工作目录中的更改添加到索引（index）。

当我们同时处理多个任务并且只想提交已完成的任务时，我们先将完成的更改添加到暂存区，然后进行提交。此时 `git add` 命令非常有帮助。

## 372. 为什么我们使用 `git reset` 命令？

我们使用 `git reset` 命令将当前 HEAD 重置到特定状态。
默认情况下，它是 `git add` 命令的反向操作。

因此，我们使用 `git reset` 命令来撤销 `git add` 命令的更改。

## 373. 提交对象（commit object）包含什么？

当我们使用 `git commit` 命令在 GIT 中进行提交时，GIT 会创建一个新的提交对象。这个提交对象会被保存到 GIT 仓库中。

提交对象包含以下信息：

- **HASH**：Git tree 的 SHA1 哈希值，它指向提交时索引的状态。
- **Commit Author（提交作者）**：执行提交的人员/进程名称以及日期/时间。
- **Comment（注释）**：包含提交原因的某些文本消息。

## 374. 我们如何将 `git log` 消息转换为不同的格式？

我们可以使用 `git log` 命令中的 `pretty` 选项来实现这一点。

`git log --pretty`

该选项将输出格式从默认转换为其他格式。这里有一些预构建的格式供我们使用。

`git log --pretty=oneline`

例如：`git log --pretty=format:"%h - %an, %ar : %s"`
```
ba72a6c - Dave Adams, 3 years ago : changed the version number
```

## 375. git hooks 可以用哪些编程语言编写？

Git hooks 通常用 shell 和 PERL 脚本编写。但只要该语言具有可执行文件，就可以用任何其他语言编写。

Git hooks 也可以用 Python 脚本编写。

## 376. 什么是 GIT 中的提交消息（commit message）？

提交消息是我们添加到提交中的一条注释。我们可以使用提交消息提供关于提交原因的有意义的信息。

在大多数组织中，在每个提交时附带提交消息是强制性的。

通常，提交消息包含项目的 JIRA 工单号、错误 ID、缺陷 ID 等。

## 377. GIT 如何保护仓库中的代码？

GIT 被设计得非常安全，因为它包含了组织的源代码。GIT 仓库中的所有对象都使用一种名为 SHA1 的哈希算法进行加密。

该算法非常强大且快速。它保护源代码和仓库的其他内容免受可能的恶意攻击。

该算法还通过保护更改历史防止意外更改，来维护 GIT 仓库的完整性。

## 378. GIT 如何提供版本控制的灵活性？

GIT 是一个非常灵活的版本控制系统。它支持非线性开发工作流。它支持与外部协议和现有系统兼容流。

GIT 还支持分支（branching）和标签（tagging），这促进了版本控制中多种工作流的发展。

## 379. 我们如何更改 GIT 中的提交消息？

如果提交尚未推送到 GitHub，我们可以使用 `git commit --amend` 命令来更改提交消息。

当我们推送提交时，GitHub 上会显示一条新消息。

## 380. 为什么建议创建一个额外的提交而不是修改（amending）现有的提交？

Git 的 `amend` 在内部会创建一个新提交并替换旧提交。如果提交已经推送到中央仓库，则不应使用它来修改之前的提交。

它通常应该只用于修改 git 注释。

## 381. 什么是 GIT 中的裸仓库（bare repository）？

使用 `git init --bare` 命令创建的仓库是 GIT 中的裸仓库。

裸仓库不包含源文件的任何工作副本或检出副本。裸仓库将 git 修订历史存储在仓库的根目录下，而不是 `.git` 文件夹中。

它主要用于与其他开发者共享和协作。

我们可以创建一个裸仓库，所有开发者都可以向其推送代码。

裸仓库中没有工作树（working tree），因为没有人直接在裸仓库中编辑文件。

## 382. 我们如何将本地仓库放在 GitHub 服务器上？

要将本地仓库放在 GitHub，我们首先将工作目录中的所有文件添加到本地仓库并提交更改。之后，我们调用 `git remote add <Remote Repo URL>` 命令将本地仓库添加到 GitHub 服务器上。

## 383. 你如何在 GIT 中删除分支？

我们使用 `git branch -d <branchname>` 命令进行删除。如果分支没有完全合并，我们使用 `git branch -D <branchname>`。

## 384. 我们如何设置仓库在提交之前运行完整性检查（sanity checks）？

我们可以为此目的使用 hooks。我们可以在 `pre-commit` hook 中编写脚本。如果此 hook 通过，只有提交才会成功。

另一个选项是使用 `pre-push` hook。

## 385. (注：此处原文跳转到了 386)

## 386. 在 GIT 中，你如何将多个提交压缩为一个提交？

我们使用 `rebase` 命令来压缩提交。它会重写历史。应该谨慎操作，因为它可能会导致意外的结果。

## 387. 如何从一个分支切换到另一个？

在 GIT 中，我们可以使用 `git checkout <branchname>` 命令进行切换。

## 388. 我们如何从工作目录清理不需要的文件？

GIT 提供了 clean 命令来递归清理树。它会移除未受控制的文件。如果我们使用 `git clean -x`，忽略的文件也会被移除。

## 389. `git tag` 的目的是什么？

我们使用 `git tag` 命令在 GIT 中添加、删除、列出或验证标签对象。使用 `-a`、`-s`、`-u` 创建的标签对象被称为注释标签。注释标签通常用于发布。

## 390. 什么是 GIT 中的 cherry-pick？

`cherry-pick` 是 GIT 中一个非常有用的功能。通过使用此命令，我们可以选择性地应用现有提交的更改。如果我们想选择性发布一个功能，可以移除不需要的文件并只应用选定的提交。

## 391. 什么是 GIT 中的 shortlog？

GIT 中的 shortlog 是一个总结 `git log` 输出的命令。shortlog 的输出适用于发布公告。

## 392. 你如何找到特定提交中更改的文件名？

GIT 中的每个提交都有一个哈希值。该哈希值唯一标识 GIT 提交对象。我们可以使用 `diff-tree` 命令列出提交中更改的文件名。

命令如下：
`git diff-tree -r <hash of commit>`

## 393. 我们如何挂载自动化脚本以便在 push 命令产生新提交时运行？

在 GIT 中，我们可以使用 hook 在特定事件时运行自动化脚本。我们可以在 `pre-receive`、`update` 或 `post-receive` hook 之间进行选择，并将脚本附加到任何一个 hook 上。

GIT 会在任何一个这些 hook 事件时自动运行脚本。

## 394. GIT 中 `pre-receive`、`update` 和 `post-receive` 钩子有什么区别？

`pre-receive` 钩子在提交（commit）推送到目标仓库时触发。挂载在此钩子上的任何脚本都会更新任何引用（reference）之前执行。这主要用于强制执行最佳实践和策略。

`update` 钩子与 `pre-receive` 钩子类似。它在任何更新完成之前触发。对于推送到目标仓库的每一个提交，该钩子都会被调用一次。

`post-receive` 钩子在更新完成被目标仓库接受后触发。这主要用于配置部署脚本。它还可以调用持续集成（CI）系统，并向仓库的相关方发送通知邮件。

## 395. 我们必须将 GIT 钩子的脚本存储在同一个仓库中吗？

钩子（Hook）对于 GIT 仓库是本地的。但挂载在钩子上的脚本可以创建在 `hooks` 目录内部，也可以存储在独立的仓库中。但是，我们必须在本地仓库中将脚本链接到钩子。

通过这种方式，我们可以在独立的仓库中维护脚本的版本，但在存储钩子的仓库中使用它们。

此外，当我们将脚本存储在独立的公共仓库时，我们可以在多个仓库的不同目的中复用相同的脚本。

## 396. 我们如何确定 GIT 中作为 bug 来源的提交？

在 GIT 中，我们可以使用 `git bisect` 命令来找到引入系统中 bug 的提交。

`git bisect` 命令内部使用二分查找算法来寻找引入 bug 的提交。

我们首先告诉它一个包含 bug 的坏提交（bad commit）和一个在 bug 引入之前不存在的良好提交（good commit）。

然后 `git bisect` 会在这两个端点之间选取一个提交，并询问我们所选提交是好是坏。

它会继续缩小范围，直到发现引入 bug 的精确提交。

## 397. 我们如何查看 GIT 中两个提交之间的差异？

我们可以使用 `git diff` 命令来查看两个提交之间的差异。比较两个提交的简单 `git diff` 命令语法如下：

```
git diff <commit#1> <commit#2>
```

## 398. 在 GIT 中识别提交有哪些不同方法？

GIT 中的每个每个提交对象都有一个唯一的哈希值（hash）。该哈希值是一个 40 位的校验和哈希。它基于 SHA1 哈希算法。我们可以使用哈希值来唯一标识一个 GIT 提交。

Git 还支持为提交创建别名（alias）。这种别名被称为 `refs`。GIT 中的每个标签（tag）都是一个 ref。这些 refs 也可以用来识别提交。GIT 中的一些特殊标签包括 `HEAD`、`FETCH_HEAD` 和 `MERGE_HEAD`。

## 399. 当我们运行 `git branch <branchname>` 时，GIT 如何知道最后一次提交的 SHA-1 值？

GIT 使用名为 `HEAD` 的引用来实现此目的。GIT 中的 `HEAD` 文件是指向我们正在工作的分支的符号引用（symbolic reference）。

符号引用不是包含 SHA-1 值的普通引用。符号引用包含一个指向另一个引用的指针。

当我们打开 `head` 文件时，我们看到：

```
$ cat .git/HEAD
ref: refs/heads/master
```

如果我们运行 `git checkout branchA`，Git 会将文件更新如下所示：

```
$ cat .git/HEAD
ref: refs/heads/branchA
```

## 400. 在 GIT 中可以创建哪些不同类型的标签（Tags）？

在 GIT 中，我们可以创建两种类型的标签。

**轻量级标签（Lightweight Tag）**：轻量级标签是一个不会移动的引用。我们可以通过运行类似的命令来创建轻量级标签：

```
$ git update-ref refs/tags/v1.0
dad0dab538c970e37ae1e769cbde608743bc96d
```

**注释标签（Annotated Tag）**：注释标签是 GIT 中更复杂的对象。当我们创建一个注释标签时，GIT 会创建一个标签对象并写入一个指向该对象的引用，而不是直接指向提交。我们可以按照如下方式创建注释标签：

```
$ git tag -a v1.1 1d410abc13591cb07496601ebc7c059dd55bfe9 -nm 'test tag'
```

## 401. 如何重命名远程仓库？

我们可以使用 `git remote rename` 命令来更改远程仓库的名字。这会更改本地与远程仓库关联的短名。命令格式如下：

```
git remote rename repoOldName repoNewName
```

## 402. 有人使用 `git checkout`，也有人使用 `git co` 进行 checkout。这是怎么可能的？

我们可以通过修改 git 配置来为命令创建别名。

在调用 `git co` 代替 `git checkout` 的情况下，我们可以运行以下命令：

```
git config --global alias.co checkout
```

因此，使用 `git co` 的人们已经在他们自己的环境中为 `git checkout` 创建了别名。

## 403. 我们如何查看 GIT 中每个分支的最后一次提交？

当我们运行 `git branch` 命令时，它会列出本地仓库中的所有分支。要查看与每个分支关联的最新提交，我们使用选项 `-v`。

精确命令是：

```
git branch -v
```

## 413. GIT 维护的三个主树是什么？

GIT 维护以下三个树：

- **HEAD**：这是最后一次提交快照。
- **Index（索引）**：这是下一次提交快照。
- **Working Directory（工作目录）**：这是进行更改的沙箱。

## 414. 工作 GIT 的三个主要步骤是什么？

GIT 在简单的工作流中有以下三个主要步骤：

1. 将项目从 HEAD 检出到工作目录。
2. 将文件从工作目录暂存到索引（Index）。
3. 将更改从索引提交到 HEAD。

## 415. GIT 中的 ours 和 theirs 合并选项是什么？

在 GIT 中，我们有两个简单的选项来解决合并冲突：`ours`（我们的）和 `theirs`（他们的）。

这些选项告诉 GIT 在合并冲突中倾向于哪一方。

在 `ours` 模式中，我们运行类似 `merge -Xours branchA` 的命令。

顾名思义，在 `ours` 中，合并冲突期间，我们分支的更改优于另一个分支。

## 416. 如何忽略由于空格引起的合并冲突？

GIT 在 `git merge` 命令中提供了 `ignore-space-change` 选项来忽略与空格相关的冲突。

执行该操作的命令如下：

```bash
git merge -Xignore-space-change whitespace
```

## 417. 什么是 `git blame`？

在 GIT 中，`git blame` 是一个查找修改特定行的行的非常好选项。当我们对一个文件调用 `git blame` 时，它会显示负责该行更改的提交提交信息和姓名。

以下是一个示例：

```
$ git blame -L 12,19 HelloWorld.java
^1822fe2 (Dave Adams 2016-03-15 10:31:28 -0700 12) public class HelloWorld {
^1822fe2 (Dave Adams 2016-03-15 10:31:28 -0700 13)
^1822fe2 (Dave Adams 2016-03-15 10:31:28 -0700 14) public static void main(String[] args) { // Prints
af6560e4 (Dave Adams 2016-03-17 21:52:20 -0700 16) // "Hello, World!" to the terminal window.
a9aef55d (Dave Adams 2016-04-06 10:15:08 -0700 17)
    System.out.println("Hello, World");
af6560e4 (Dave Adams 2016-03-17 21:52:20 -0700 18) }
af6560e4 (Dave Adams 2016-03-17 21:52:20 -0700 19) }
```



### 418. GIT 中的 submodule（子模块）是什么？

在 GIT 中，我们可以使用 `git submodule` 命令在仓库内部创建子模块。

通过使用 submodule 命令，我们可以将一个 Git 仓库作为另一个 Git 仓库的子目录。

它允许我们将对子模块的提交与主 Git 仓库的提交分开来。

## AWS

### 419. 关于 AWS Region（区域）你了解什么？

AWS Region 是地理区域内一个完全独立的实体。一个 AWS Region 包含两个或更多可用区（Availability Zones）。

在一个区域内，可用区通过低延迟链路连接。

由于每个 AWS Region 都与另一个 Region 隔离，因此它提供了极高的容错能力和稳定性。

对于启动 EC2 实例，我们必须在同一区域内选择 AMI。

### 420. IAM 的重要组件有哪些？

IAM 的重要组件如下：

1. **IAM User（IAM 用户）**：IAM 用户是指与 AWS 交互的人员或服务。用户可以登录 AWS 管理控制台在 AWS 中执行任务。
2. **IAM Group（IAM 组）**：IAM Group 是 IAM 用户的集合。我们可以为 IAM Group 指定权限。这有助于管理大量的 IAM 用户。我们可以简单地向 IAM 组添加或删除 IAM 用户来管理权限。
3. **IAM Role（IAM 角色）**：IAM Role 是我们赋予权限的身份。角色不具有凭据（密码或访问密钥）。我们可以临时给 IAM 用户一个 IAM Role 以在 AWS 中执行某些任务。
4. **IAM Permission（IAM 权限）**：在 IAM 中我们可以创建两种类型的权限：基于身份的和基于资源的。我们可以创建一个用于访问或对 AWS 资源执行操作的权限，并将其分配给用户、角色或组。我们还可以在 S3 桶、Glacier 库等资源上创建权限，并指定谁有权访问资源。
5. **IAM Policy（IAM 策略）**：IAM Policy 是一个文档，我们在其中列出权限以指定操作（Actions）、资源（Resources）和效果（Effects）。该文档为 JSON 格式。我们可以将策略附加到 IAM 用户或组。

### 421. 关于 AWS IAM 的重要点

关于 AWS IAM 的一些重要点如下：

1. IAM 中的新用户默认没有权限。
2. 我们可以使用策略来允许或拒绝。
3. 可以使用命令行界面管理 IAM。
4. 它支持用于程序化访问的访问密钥。
5. 我们使用角色进行临时访问。
6. 可以在需要时创建和删除用户。

### 422. S3 的重要特性有哪些？

S3 的一些重要特性如下：

1. S3 提供了高耐用性。
2. 它支持高达 5 TB 的对象。
3. 数据存储在多个设备上。
4. 它支持各种存储类。
5. 它提供了各种安全选项。
6. 可以使用策略进行访问。

### 423. S3 的持久性是多少？

S3 为存储的数据提供 99.99999999% 的持久性。

### 424. S3 支持哪些一致性？

S3 在创建新对象时支持强一致性（Strong Consistency）。在删除对象时也支持最终一致性（Eventual Consistency）。

### 425. S3 有哪些层级？

S3 的不同存储类包括：

1. **S3 Standard（标准）**：在此层级中，S3 提供立即可用的存储。用于频繁访问的文件。
2. **S3 Standard IA（标准不频繁访问）**：在此层级中，S3 提供立即可用的存储。但该层级的文件访问频率较低。
3. **S3 One Zone-IA（单区不频繁访问）**：在这种情况下，数据复制到一个可用区，但不像标准版那样。

### 426. 如何在 S3 上上传大于 100 MB 文件？

S3 支持存储高达 5 TB 的对象或文件。要上传大于 100 MB 的文件，我们必须使用 AWS 的分段上传（Multipart upload）。通过分段上传，我们可以将大文件分成多个部分。

每个部分将独立上传。上传顺序并不重要。它甚至支持并行上传这些部分以减少时间。一旦所有部分上传完成，该工具会将它们合并为一个对象。

### 427. 当我们从 S3 删除对象时会发生什么？

Amazon S3 提供删除对象的 API。

如果对象所在的桶启用了版本控制，我们可以指定要删除的对象版本。其他版本仍然存在桶中。

如果我们没有指定版本，仅传递密钥，Amazon S3 将删除对象并返回版本 ID。该对象将不再出现在桶中。

如果桶启用了多因素身份验证 (MFA)，如果我们不指定 MFA 令牌，删除请求将失败。

### 429. 我们可以禁用 Amazon S3 中启用了版本控制的存储桶的版本吗？

不可以，我们不能禁用 Amazon S3 中启用了版本控制的存储桶。我们只能暂停 S3 存储桶的版本控制。

一旦我们暂停了版本控制，Amazon S3 将停止创建对象的新版本。它只是带有空版本 ID（null version ID）存储对象。

在覆盖现有对象时，它只是用空版本 ID 的对象替换对象。因此，该对象的任何现有版本仍然保留在存储桶中。但除了空版本 ID 之外，该对象将不再有任何新版本产生。

### 430. Amazon S3 跨区域复制（Cross Region Replication）的用例有哪些？

我们可以使用 Amazon S3 跨区域复制在不同 AWS 区域的桶之间创建对象的副本。这种复制是自动且以异步模式进行的。

我们必须在 S3 的源存储桶上添加复制配置才能使用跨区域复制。它会在源存储桶到不同区域的目标存储桶创建完全相同的副本。

跨区域复制的一些主要用例如下：

1. **合规性**：某些法律/监管要求将数据存储在更远的地理位置。这种合规性可以通过遍布全球的 AWS 区域来实现。
2. **故障转移**：有时，我们希望尽量减少由于区域完全停电导致系统故障的概率。在这种情况下，可以使用跨区域复制。
3. **延迟**：如果我们在为多个地理区域提供服务，将对象复制到更靠近终端客户的地理区域是有意义的。这有助于降低延迟。

不，我们必须在存储桶上启用版本控制才能执行跨区域复制。

### 432. Amazon S3 中对象生命周期管理（Object Lifecycle Management）中有哪些不同类型的操作？

Amazon S3 中主要有两种类型的对象生命周期管理操作。

1. **转换操作（Transition Actions）**：这些操作定义了对象从一种存储类转换到另一种存储类时的状态。例如，一个新对象可以在创建 60 天后转换到 STANDARD_IA（低频访问）类。它可以在创建 180 天后转换到 GLACIER。
2. **过期操作（Expiration Actions）**：这些操作指定了当对象过期时会发生什么。我们可以要求 S3 在对象过期时完全删除对象。

### 433. 如何通过使用 Amazon CloudFront 提高我们应用程序的性能？

如果我们的应用程序内容丰富且在多个位置使用，我们使用 Amazon CloudFront 来提高其性能。Amazon CloudFront 使用的一些技术如下：

**缓存（Caching）**：Amazon CloudFront 在靠近查看者的位置缓存我们应用程序内容的副本。通过这种缓存，我们的用户可以非常快地获取我们的内容。此外，由于缓存，我们主服务器的负载减轻了。

**边缘/区域位置（Edge / Regional Locations）**：CloudFront 使用全球范围的边缘和区域边缘位置网络来缓存我们的内容。这些位置服务于全球几乎所有的地理区域。

**持久连接（Persistent Connections）**：在某些情况下，CloudFront 与主服务器保持持久连接，以快速获取内容。

**其他优化（Other Optimization）**：Amazon CloudFront 还使用其他优化技术，如 TCP 初始拥塞窗口等来提供高性能的体验。

### 434. Amazon CloudFront 中区域边缘缓存（Regional Edge Cache）的机制是什么？

区域边缘缓存位置位于主 Web 服务器和全局边缘位置之间。当某个对象/内容的流行程度降低时，全局边缘位置可能会将其从缓存中移除。

但区域边缘位置维护着更大的缓存。由于对象/内容可以在区域边缘位置停留很长时间，因此 CloudFront 就不需要返回到主 Web 服务器。当它在全局边缘位置中没有找到任何对象时，它只会在区域边缘位置中查找。

这提高了 Amazon CloudFront 为我们的用户提供内容的性能。

### 435. 流式传输内容（Streaming content）的好处是什么？

通过流式传输内容我们可以获得以下益处：

1. **控制（Control）**：我们可以为用户提供更多控制，让他们选择想看的内容。在视频流中，用户可以选择视频中他们想要开始观看的位置。
2. **内容（Content）**：通过流传输，我们的整个内容不会停留在用户的设备上。用户只获得他们正在观看的部分。一旦话结束，内容将从用户的设备中移除。
3. **成本（Cost）**：通过流传输，无需将所有内容下载到用户的设备上。只要部分内容可用，用户就可以开始查看。这节省了成本，因为我们不需要在每次查看会话之前下载大型媒体文件。

### 436. AWS 中的 Lambda@Edge 是什么？

在 AWS 中，我们可以使用 Lambda@Edge 实用程序来解决终端用户网络延迟的问题。

在 Lambda@Edge 中，不需要配置或管理服务器。我们只需要将 Node.js 代码上传到 AWS Lambda，并创建在 CloudFront 请求时触发的函数。

当 CloudFront 边缘位置接收到内容请求时，Lambda 代码就准备好执行了。

这是一个在不管理服务器的情况下扩展 CloudFront 业务的非常好的选择。

### 437. Amazon CloudFront 触发了哪些类型的事件？

Amazon CloudFront 触发的不同类型事件如下：

1. **访问者请求（Viewer Request）**：当 CloudFront 边缘位置接收到内容请求时，Lambda 代码就准备好执行。
2. **访问者响应（Viewer Response）**：当 CloudFront 向访问者提供响应时，会触发此事件。
3. **源请求（Origin Request）**：当 CloudFront 在缓存中未找到对象时，它会向源请求。
4. **源响应（Origin Response）**：当 CloudFront 收到源的响应时。

### 438. Amazon CloudFront 中的地理定位（Geo Targeting）是什么？

在 CloudFront 中，我们可以根据地理位置向不同国家的用户提供不同的内容。

### 439. CloudFront 有哪些主要功能？

CloudFront 的主要功能如下：

1. 设备检测（Device Detection）
2. 协议检测（Protocol Detection）
3. 地理定位（Geo Targeting）
4. 缓存行为（Cache Behavior）
5. 跨源共享（Cross Origin）
6. 多源服务器（Multiple Origin）
7. HTTP Cookie
8. 查询字符串（Query String）
9. 自定义 SSL

### 440. S3 有哪些安全机制？

Amazon S3 是一个非常安全的服务。S3 的安全机制如下：

1. **访问（Access）**：当我们创建存储桶时，只有所有者可以访问桶。
2. **身份验证（Authentication）**：Amazon S3 还支持身份验证以控制谁可以访问桶。
3. **访问控制列表（ACL）**：我们可以创建访问控制列表（ACL）来为用户和组提供选择性权限。
4. **HTTPS**：Amazon S3 还支持 HTTPS 协议以安全地上传和下载数据。
5. **加密（Encryption）**：我们还可以在 S3 中使用服务器端加密（SSE）来加密数据。

## 云计算

### 441. 云计算的好处有哪些？

云计算的主要益处有：

**灵活性（Flexibility）**：具有波动带宽需求的业务需要云计算的灵活性。如果你需要高带宽，可以扩展你的云容量。当你不需要高带宽时，可以只需缩小。不需要被绑定在缺乏灵活性的固定容量基础设施中。

**灾备（Disaster Recovery）**：云计算提供了托管在云端的稳健备份和恢复解决方案。由于这些，不需要在本地灾备上花费额外资源。它还节省了设置灾备的时间。

**自动软件更新（Automatic Software Updates）**：大多数云供应商提供自动软件更新。这减少了安装新软件版本以及跟上最新软件安装的额外任务。

**低资本支出（Low Capital Expenditure）**：云计算模式是按需付费（Pay as you Go）。这意味着前期资本支出非常少。存在基于使用情况的可变付费。

**协作（Collaboration）**：在云环境中，应用程序可以在团队之间共享。这增加了团队成员之间的协作和沟通。

**远程工作（Remote Work）**：云解决方案提供了远程办公的灵活性。没有现场办公。人们可以从任何地方连接并开始工作。

**安全性**：云计算解决方案比常规的现场工作更安全。存储在本地服务器和计算机中的数据极易受到安全攻击。在云计算中，漏洞非常少。云提供商为其用户提供了一个安全的工作环境。

**文档控制**：一旦文档存储在公共仓库中，就会增加公司与其客户之间的可见性和透明度。由于只有一份共享副本，出现差异的几率更低。

**竞争性定价**：在云计算中存在多个参与者，因此他们会相互竞争并提供非常优惠的价格。与其他选项相比，这要便宜得多。

**环保**：云计算还节省了宝贵的环境资源。通过不阻塞资源和带宽来实现这一点。

### 442. 什么是云计算中的“按需计算”？

按需计算（On-demand Computing）是企业系统中最新的模型之一。它与云计算有关。这意味着云提供商可以根据需求提供 IT 资源。

在企业系统中，对计算资源的需求随时间变化。在这种情况下，按需计算可以确保服务器和 IT 资源得到配置，以处理需求的增加或减少。

云提供商维护着一个资源池。该资源池包含网络、服务器、存储、应用程序和服务。这个资源池可以满足各种企业客户对资源和计算不断变化的需求。

有很多如网格计算（grid computing）、公用计算（utility computing）、自主计算（autonomic computing）等概念，与按需计算相似。

这是目前计算模型中最流行的趋势。

### 443. 云计算有哪些不同的层？

云计算的三大主要层如下：

*   **基础设施即服务 (IAAS)**：IAAS 提供商提供物理设备的低级抽象。亚马逊云服务 (AWS) 就是 IAAS 的示例。AWS 提供存储所需的 S3 桶等资源。这一层中的资源主要是硬件，如内存、处理器速度、网络带宽等。
*   **平台即服务 (PAAS)**：PAAS 提供商提供如 Rails、Django 等受托管的服务。PAAS 的一个良好示例是 Google App Engine。这些是开发者可以在其中轻松地开发复杂软件的环境。开发者只需专注于软件开发，而扩展性和性能则由 PAAS 提供商处理。
*   **软件即服务 (SAAS)**：SAAS 提供商为客户提供实际的运行应用程序。Salesforce 和 Github 是 SaaS 的两个良好示例。它们隐藏了软件的底层细节，仅提供一个用于操作系统的界面。在后台，软件的版本可以轻松更改。

### 444. 基础设施即服务 (IAAS) 提供商提供哪些资源？

IAAS 提供商可以提供物理、虚拟或两种类型的资源。这些资源被用于构建云。

IAAS 提供商处理维护和部署这些服务的复杂性。

IAAS 提供商还负责这些服务的安全和备份恢复。IAAS 中的主要资源是服务器、存储、路由器、交换机和其他相关硬件等。

### 445. 平台即服务 (PaaS) 的好处是什么？

平台即服务 (PaaS) 是一种云计算服务。PaaS 提供商提供一个平台，客户可以在该平台上开发、运行和管理应用程序，而无需构建基础设施。

在 PAAS 中，客户通过无需创建和管理与他们想要开发的应用程序相关的基础设施环境来节省时间。

### 446. PaaS 的主要优势是什么？

PaaS 的优势是：

*   它允许在更高级的编程上进行开发工作，复杂度极低。
*   团队可以专注于应用程序的开发，这使得应用程序非常高效。
*   应用程序的维护和增强要容易得多。
*   它适用于多个开发者协作同一个项目但不在同一地工作的情况。

### 447. PaaS 的主要缺点是什么？

PaaS 的最大缺点是开发者只能使用 PaaS 提供商提供的工具。开发者无法使用全范围的传统工具。

某些 PaaS 提供商将客户锁定在他们的平台上。这降低了客户使用 PaaS 的灵活性。

### 448. 云计算有哪些不同的部署模型？

云计算支持以下部署模型：

*   **私有云**：一些公司建立自己的私有云。私有云是一个仅供一个组织拥有、运营使用的全功能平台。私有云的主要原因是安全性。
*   **公有云**：公有云通过互联网向公众提供。由云提供商提供，资源在不同组织之间共享。
*   **混合云**：混合云是私有云和公有云的结合。这种方法为组织提供了两者的功能。

### 449. 可扩展性（Scalability）和弹性（Elasticity）的区别是什么？

可扩展性（Scalability）是系统通过增加资源来处理增加的需求的能力。在高度可扩展的系统中，可以增加硬件/软件。

弹性（Elasticity）是系统动态处理突发流量的能力。弹性是云计算的一个重要特征。弹性意味着你的架构在实时情况下的适应能力如何。例如，如果系统中一个服务器可以处理 100 个用户，2 台服务器可以处理 200 个，10 台服务器可以处理 1000 个。但为了增加 X 个用户，如果你需要 2X 数量的服务器，那么它是可扩展的。如果你的设计可以快速启动 Web 服务器来处理负载，那么你的设计就是弹性的。

### 450. 什么是软件即服务？

软件即服务（SaaS）是云计算的一个类别，其中软件被集中托管，并按订阅方式进行许可。它也被称为按需软件。通常，客户通过使用 Web 浏览器等轻客户端来访问软件。

Google Docs、Microsoft Office 等许多应用程序都为其软件提供了 SaaS 模型。

SaaS 的益处是客户可以根据其当前需求随时增加更多用户。而且客户无需在其场所安装或维护任何软件即可使用该软件。

### 451. 云计算中数据中心有哪些不同的类型？

云计算由网格结构连接的不同类型数据中心组成。云数据中心的主要类型有：

*   **容器化数据中心**：正如其名，容器化数据中心为组织提供了高水平的定制。这些是传统类型的数据中心。我们可以在此数据中心选择不同类型的服务器、内存、网络和其他基础设施资源。我们还需要在这种数据中心内规划温度控制、网络管理和电源管理。
*   **低密度数据中心**：在低密度数据中心中，我们获得高水平的性能。在这样的数据中心——如果我们要增加服务器密度，就会出现电力问题。高密度的服务器会导致区域变热。在这种情况下，会进行有效的热量和电源管理。为了达到高水平的性能，我们必须优化数据中心服务器的数量。

### 452. 请解释软件即服务 (SaaS) 云环境的不同模式？

软件即服务 (SaaS) 用于在云环境中提供不同类型的软件应用程序。通常，这些服务是以订阅制提供的。SaaS 的不同模式有：

*   **简单多租户**：在这种设置中，每个客户端都获得其自己的资源。这些资源不与其他客户端共享。这是一个更安全的选项，因为没有资源共享。但这是一个低效的选项，因为随着需求的增长，为每个客户端进行扩展扩容需要更多的资金。此外，在这种模式下，扩展应用程序也需要时间。
*   **细粒度多租户**：在这种模式下，提供给每个客户端的功能是相同的。资源在多个客户端之间共享。这是一种高效的云服务模式，不同客户端之间的数据保持私密，但计算资源是共享的。此外为不同的客户端扩展 SaaS 实现更加容易且快速。

### 453. 在云环境中安全方面需要注意哪些事项？

在云计算环境中，安全性是最重要的方面之一。

随着对黑客攻击关注增加，每个组织都希望让自己的软件系统和数据变得安全。由于在云计算环境中，软件和硬件不在组织的场所内，因此实施最佳的安全实践变得更加重要。

组织必须确保数据在两个位置之间传输时处于最安全状态。此外，当数据存储在某处时也必须保持数据安全。黑客可以入侵应用程序，也可以获取数据的未经授权副本。因此，在传输和静态存储期间对数据进行加密变得非常重要，以保护其免受恶意黑客的侵害。

### 454. 为什么要在云计算环境中使用 API？

应用程序编程接口 (API) 用于云计算环境访问许多服务。API 非常容易使用。它们为在云环境中创建不同的系列应用程序提供了快速的选项。

API 提供了一个可以用于多种场景的简单接口。

云计算 API 有不同类型的客户端。在云计算环境中，通过 API 更容易满足多个客户端的不同需求。

### 455. 云安全管理包含哪些不同领域？

云中安全管理的不同领域如下：

*   **身份管理**：这一方面创建了不同层级的用户、角色及其凭据，用于访问云中的服务。
*   **访问控制**：在该领域中，我们创建了多个层级的权限和访问区域，可以将其授予用户或角色，以访问云环境中的服务。
*   **身份验证**：在该领域中，我们检查用户的凭据并确认其为正确的用户。通常通过用户密码和多因素身份验证完成，例如通过手机上的一次性代码进行验证。
*   **授权**：在这一方面，我们检查授予用户或角色的权限。如果用户被授权访问某项服务，则允许他们在云环境中使用该服务。

### 456. 云数据中心的主要成本因素有哪些？

基于云的数据中心的成本与传统数据中心不同。基于云的数据中心的主要成本因素如下：

*   **人力成本**：我们需要熟练的员工来操作我们为业务选择的基于云的数据中心。由于云不是一项非常老旧的技术，可能很难获得合适技能的人才来处理基于云的数据中心。
*   **电力成本**：在某些云操作中，电力成本由客户承担。由于它是可变成本，可能会随着规模和使用的增加而增加。
*   **计算成本**：云环境中最大的成本是我们支付给云提供者以获取计算资源的费用。与人力或电力成本相比，这项费用高得多。

### 457. 我们如何衡量云服务？

在云计算环境中，我们为使用的服务付费。因此，衡量云服务的主要标准是其使用情况。

对于计算资源，我们根据时间以及计算资源的能力来衡量使用情况。

对于存储资源，我们根据字节（千字节）和数据传输中使用的带宽来衡量使用情况。

衡量云服务的另一个重要方面是其可用性。云提供商必须指定服务水平协议 (SLA)，规定云端服务可用的时间。

### 458. 传统数据中心与云环境有什么区别？

在传统数据中心中，需要管理硬件和软件。在云环境中，我们只使用提供者提供的资源。云环境更具活性和可扩展性。

在传统数据中心中，扩展是手动且耗时的。在云环境中，扩展是自动化且非常快速。这允许组织快速响应变化。

### 459. 你将如何优化云环境中应用程序的可用性？

为了优化云环境中的可用性，可以使用跨区域的实例。如果某个区域故障，应用程序仍然可以在另一个区域运行。我们还可以使用负载均衡器在多个实例之间分配流量。这确保了应用程序对用户可用。

### 460. 实现 IaaS 有哪些要求？

实现 IaaS 的主要要求如下：

*   **操作系统 (OS)**：我们需要一个支持虚拟机的操作系统。可以使用开源操作系统如 Linux。
*   **网络**：我们需要为 IaaS 定义并实现网络。我们可以使用公用网络或私有网络。
*   **云模型**：我们必须选择正确的云模型。可以是 SaaS、PaaS 或 IaaS。

## DOCKER

### 461. 什么是 Docker？

Docker 是一个开源软件。它提供了 Linux 应用程序部署的自动化。

我们可以通过 Docker 在 Linux 上实现操作系统虚拟化。

Docker 可以将软件封装在一个完整的文件系统中，该系统包含运行所需的代码、运行时环境、系统工具和库。

### 462. Docker 镜像和 Docker 容器的区别是什么？

Docker 容器是 Docker 镜像的实例。

Docker 镜像是一个不可变的文件，是容器的快照。我们使用 `build` 命令创建镜像。

当我们使用 `run` 命令会产生容器。

在编程语言中，镜像是一个类（Class），而容器是类的实例。

### 463. 如何从 Docker 中删除镜像？

我们可以使用 `docker rmi` 命令从本地系统中删除镜像。

准确命令为：

```
docker rmi <image-id>
```



% docker rmi `<Image Id>`

如果我们想找到本地系统中所有 Docker 镜像的 ID，可以使用 `docker images` 命令。

```
% docker images
```

如果我们想删除一个 docker 容器，则使用 `docker rm` 命令。

```
% docker rm <Container Id>
```

## 464. Docker 容器与虚拟机有什么区别？

在虚拟机环境中，我们首先创建一个虚拟机，然后在上面安装操作系统。之后我们再部署应用程序。虚拟机也可以安装在不同的硬件配置上。

在 Docker 环境中，我们直接在 Docker 中部署应用程序。该环境中没有操作系统层。我们指定库，其余的内核由 Docker 引擎提供。

在某种程度上，Docker 容器和虚拟机是互补的。

# 465. 我们可以用 json 文件代替 yaml 写 compose 文件吗？

可以。Yaml 格式是 json 格式的超集。因此，任何 json 文件也是有效的 Yaml 文件。

如果我们使用 json 文件，则必须在 docker 命令中指定我们正在使用 json 文件，如下所示：

```bash
% docker-compose -f docker-compose.json up
```

# 466. 我们可以在一台服务器上通过 Docker 运行多个应用吗？

可以，从理论上讲我们可以在一台 Docker 服务器上运行多个应用程序。但在实践中，将不同的组件运行在独立的容器中会更好。

这样我们可以获得更整洁的环境，并且它可以用于多种用途。

# 467. Docker 的常见用场景有哪些？

Docker 的一些常见用场景如下：

1. 设置开发环境：我们可以使用 Docker 为代码所依赖的应用程序设置开发环境。
2. 自动化测试设置：Docker 还可以帮助创建自动化测试设置。我们可以用 Docker 设置不同的服务和应用来创建自动化测试环境。
3. 生产环境部署：Docker 帮助实现应用程序的生产环境部署。我们可以使用它来创建用于生产部署的精确环境和流程。

# 468. Docker-compose 的主要功能有哪些？

Docker-compose 的一些主要功能如下：

1. 在同一宿主机上运行多个环境：我们可以它在同一宿主机服务器上创建多个环境。
2. 创建容器时保留卷数据：Docker compose 在我们创建容器时也会卷数据。
3. 重新创建更改的容器：我们也可以使用 compose 重新创建更改过的容器。
4. Compose 文件中的变量：Docker compose 还支持 compose 文件中的变量。通过这种方式我们可以创建容器的变体。

# 469. Docker 最流行的用途是什么？

Docker 最流行的用途是在构建流水线（build pipeline）。通过使用 Docker，可以更容易地自动化构建流水线中从开发到部署的过程。

我们使用 Docker 处理从开发工作、测试运行到生产环境的完整构建流。

# 470. 开源开发对 Docker 的流行起了什么作用？

由于 Linux 是一个开源操作系统，它为想要贡献开源系统的开发者开启了新的机会。

开源软件非常非常好的成果之一就是 Docker。它具有非常强大的功能。

Docker 因其易用性以及与不同系统集成的开源方法而被广泛接受。

# UNIX Shell

# 471. 你如何删除当前目录下的所有文件？包括子目录中两层级的文件。

在 Unix 中，我们使用 `rm` 命令来删除文件和子目录。通过 `rm` 命令我们有 `-r` 选项，它代表递归（recursive）。`-r` 选项可以递归地删除目录中的所有文件。

这意味着如果我们当前的目录结构如下：

- My_dir
- Level_1_dir
- Level_1_dir -> Level_2_dir
- Level_1_dir -> Level_2_dir -> a.txt

使用 `rm -r *` 命令，我们可以删除文件 `a.txt` 以及子目录 `Level_1_dir` 和 `Level_2_dir`。

命令：

```bash
rm -r *
```

星号 (`*`) 是一个通配符，代表任何名称的所有文件。

# 472. Bash 脚本中 -v 和 -x 选项的区别是什么？

在 BASH Unix shell 中，我们可以按照如下所示在脚本顶部指定 `-v` 和 `-x` 选项：

```bash
#!/bin/bash -v
```

使用 `-x` 选项，BASH shell 在替换参数和变量后会回显如 `for`、`select`、`case` 等命令。因此，它将是命令的展开形式，显示脚本的所有操作。这对于调试 shell 脚本非常有用。

使用 `-v` 选项，BASH shell 在替换参数和变量的值之前会回显每个命令。在 `-v` 选项中，Unix 会读取时打印每一行。

在 `-v` 选项中，如果我们运行它，Unix 会在读取时打印每一行。

# 473. Unix 中的过滤器（Filter）是什么？

在 Unix 中，过滤器是一个从标准输入流读取输入并向标准输出流写入输出的程序。

例如，`cat`、`grep`、`head`、`tail`、`sort`、`sed`、`awk` 都是处理数据的常用过滤器。

# 474. Unix 中的内核（Kernel）是什么？

内核是操作系统的核心，充当软件和硬件之间的桥梁。它管理 CPU、内存和 I/O 设备等系统资源。

# 475. Unix 中的 Shell 是什么？

Shell 是一个命令行界面，允许用户与 Unix 内核交互。它解释用户输入的命令并将其传递给内核。

# 476. 你知道 Unix 中有哪些不同的 shell？

Unix 有许多 shell。其中一些是：

- Bourne shell (`sh`)
- Bourne Again shell (`bash`)
- Korn shell (`ksh`)
- Z shell (`zsh`)
- C shell (`csh`)
- Enhanced C shell (`tcsh`)

# 477. ls -l 命令输出的第一个字符是什么？

我们使用 `ls -l` 命令列出目录中的文件。通过 `-l` 选项获取长格式。

在此格式中，第一个字符识别类型类型。类型类型可以是以下之一：

- `b` 块设备文件
- `c` 字符设备文件
- `d` 目录
- `l` 符号链接
- `s` 套接字
- `p` FIFO
- `-` 普通文件

通常我们看到目录为 `d`，普通文件为 `-`。

# 478. 多任务环境（Multi-tasking）和多用户环境（Multi-user）的区别是什么？

在多任务环境中，同一个用户可以提交多个任务，操作系统会同时执行它们。

在多用户环境中，多个用户可以同时与操作系统交互。

# 479. Unix 中的命令替换（Command Substitution）是什么？

命令替换是一种机制，Shell 将一个命令的输出作为参数传递给另一个命令。我们甚至可以用它设置变量或在 `for` 循环中使用参数列表。

例如 `rm \`cat files_to_delete\``
在这个示例中，`files_to_delete` 是一个包含要删除列表列表。`cat` 命令输出该文件并将输出传递给 `rm` 命令。`rm` 命令删除文件。

通常命令替换由反引号 `` ` `` 表示。

# 480. Unix 中的 Inode 是什么？

Inode 是 Unix 中的一种数据结构，表示文件系统上的文件或目录。它包含关于文件在磁盘上位置、访问模式、所有者、文件类型等信息。

每个 Inode 都有一个编号，用于索引表。Unix 内核使用 Inode 编号访问 Inode 的内容。

我们可以使用 `ls -i` 命令获取文件的 inode 编号。

## 481. Unix 文件系统中的绝对路径和相对路径有什么区别？

绝对路径是从根目录（root directory）到文件或目录的完整路径。通常，根目录用 `/` 符号表示。如果我们处于某个目录并想知道绝对路径，可以使用 `pwd` 命令。

相对路径是相对于当前目录位置的路径。

例如，在 `/var/user/kevin/mail` 目录结构中，如果我们处于 `kevin` 目录，那么 `pwd` 命令将给出绝对路径为 `/var/user/kevin`。

`mail` 文件夹的绝对路径是 `/var/user/kevin/mail`。对于 `mail` 文件夹，`./mail` 是从 `kevin` 文件夹到 `mail` 目录的相对路径。

## 482. Unix Shell的主要职责是什么？

Unix Shell 的主要职责如下：

1. 程序执行：Shell 负责执行 Unix 中的命令和脚本文件。用户可以在名为终端（terminal）的命令行界面（CLI）中交互式输入命令，也可以运行包含程序的脚本文件。
2. 环境搭建：Shell 可以为用户定义环境。我们可以在 Shell 中设置许多环境变量，并在程序中使用这些变量的值。
3. 解释器：Shell 充当脚本的解释器。它有一个内置的编程语言，可以用于实现逻辑。
4. 管道（Pipeline）：Shell 还可以连接命令管道。当我们运行多个由 `|` 管道符分隔的命令时，Shell 会接接上一个命令的输出并将其传递给管道中的下一个命令。
5. I/O 重定向：Shell 还负责从命令行界面（CLI）获取输入并将输出传回 CLI。我们使用 `>`、`<`、`>>` 字符来实现。

## 483. 什么是 Shell 变量？

Unix Shell 变量是 Shell 维护的内部变量。
它是该 Shell 局部的。它对父 Shell 或子 Shell无效。

在 C shell 中，我们通常对 Shell 变量使用小写名称。

我们可以通过 `set` 命令设置 Shell 变量的值。

例如：`% set max_threads=10`

要删除 Shell 变量，可以使用 `unset` 命令。

在脚本中使用 Shell 变量时，我们在变量名前前加 `$` 符号。

例如：`echo $max_threads`

# 微服务

## 484. 什么是微服务？

微服务是一个微小且自治的代码单元，能够很好地完成某件事。它专注于在大系统中做好某项特定的任务。
它还是一个独立的实体，可以独立设计、开发和部署。

通常，它实现为基于 HTTP 协议的 REST 服务，具有与技术无关的 API。
理想情况下，它不与任何其他服务共享数据库。

## 485. 微服务架构的优点有哪些？

微服务提供了许多优势。一些关键优势包括：

1. 扩展性（Scaling）：由于是多个微服务而不是单体应用，扩展使用频率更频繁的服务变得更容易了。例如，假设你有一个产品查询（Product Lookup）服务和一个产品购买（Product Buy）服务。产品查询的频率远高于产品购买服务。在这种情况下，你只需要扩展产品查询服务，使其运行在具有多个服务器的强力硬件上。同时，产品购买服务可以留在性能较弱的硬件上。
2. 韧性（Resilience）：在微服务架构中，如果其中一个服务宕机，可能不会影响系统的其余部分。其他部分可以继续运行，业务照常进行（BAU）。假设，你有一个产品推荐服务和一个产品购买服务。如果产品推荐服务宕机，产品购买服务仍然可以运行。
3. 技术混合（Technology Mix）：随着技术每天发生变化，你可以为新的微服务继续使用最新技术。与单体架构相比，采用新技术的风险更小。这是微服务架构最大的优点之一。
4. 复用（Reuse）：微服务有助于从一个服务学习并应用到另一个服务。
5. 便于部署（Easy Deployment）：微服务架构如果实施得当，可以使部署过程变得顺畅。

## 486. 架构师在微服务架构中扮演什么角色？

架构师在微服务架构中扮演规划者的角色。他们决定软件的布局。

架构师有助于组件的划分。他们确保组件是高内聚且低耦合的。

架构师需要关注开发中的新进展，解决微服务面临的挑战。

架构师需要提供技术治理，以确保微服务遵循微服务原则。

架构师在微服务架构中担任守护者的角色。

## 487. 微服务架构相比面向服务架构（SOA）有什么优势？

面向服务架构（SOA）是通过创建多个服务来开发软件的方法。它创建了软件部分并提高了软件的可复用。但由于使用了通信协议、中间件等因素，SOA 的开发可能缓慢。

相反，微服务对这些是无关的。你可以使用任何技术栈、任何硬件/中间件，只要你遵循微服务原则。

微服务架构比 SOA 提供了更高的活性、稳定性和开发速度。

## 488. 为微服务开发提供定制的服务模板（Service Template）是明智的吗？

如果你的组织使用相似的技术栈，那么提供一个可以为开发团队定制的服务模板是明智的。这可以加快开发。同时也有助于采用内置在模板中的各种实践。

但如果你的组织使用多种类型的技术，那么为每个服务制作和维护模板可能并不明智。相反，引入帮助所有此类技术维护相同实践的工具更好。

有很多组织为微服务提供定制模板。例如：Dropwizard、Karyon 等。你可以使用这些模板加速组织内服务的开发。

还要记住，模板代码不应促进共享代码。这会导致微服务之间的紧密耦合。

## 489. 使用共享库方法拆分单体应用有什么缺点？

你可以创建共享库来增加团队之间的功能复用和共享。但它也有一些缺点。
由于共享库是用相同的语言实现的，它限制了你使用多种类型的技术。
它无法帮助你扩展需要更好性能的系统。
共享库的部署与单体应用的部署相同，因此存在相同的部署问题。
共享库引入的共享代码增加了软件的耦合。

## 490. 一个良好的微服务具有什么特征？

1. 松散耦合（Loose coupling）：微服务对其他服务的了解很少。它尽可能保持独立。对一个微服务的更改不需要其他微服务发生更改。
2. 高内聚（Highly cohesive）：微服务是高内聚的，因此每个服务都可以独立地提供一组行为。
3. 边界上下文（Bounded Context）：微服务服务领域中的边界上下文，并通过该边界上下文的接口与领域的其余部分通信。
4. 业务能力（Business Capability）：微服务独立地为组织的大图中增加业务能力。

# 491. 什么是边界上下文（Bounded Context）？

边界上下文类似于在特定边界内开发的特定职责。在一个领域中，可以存在多个在内部实现的边界上下文。例如，一个医院系统可以拥有诸如急诊科处理、常规接种、门诊治疗等边界上下文。在每个边界上下文内部，每个子系统都可以独立地进行设计和实现。

# 492. 在微服务集成过程中需要记住哪些点？

在微服务集成过程中，需要记住的一些重要点包括：

- 技术无关的 API（Technology Agnostic APIs）：以与技术无关的方式开发微服务有助于有助于多个微服务的集成。随着时间的推移，技术实现可能会发生变化，但微服务之间的接口可以保持不变。
- 破坏性变更（Breaking Changes）：微服务的任何更改都不应该变成对客户端的破坏性变更。最好能够尽量减少更改对现有客户端的影响，这样现有客户端就不需要不断更改其代码来适应微服务的变化。
- 实现细节隐藏（Implementation Hiding）：每个微服务都应该向其他微服务隐藏其内部实现细节。这有助于减少为了实现共同解决方案而集成的微服务之间的耦合。
- 易于使用：微服务对于消费者来说应该是易于使用的，这样集成点就会更简单。它应该允许客户端选择自己的技术栈。

# 493. 微服务共享同一个数据库是一个好主意吗？

在多个微服务之间共享同一个数据库会增加它们之间的耦合。一个服务可能会开始访问另一个服务的数据表。这会违背边界上下文的。因此，在微服务之间共享数据库并不是一个好主意。

# 494. 微服务之间首选的通信类型是什么？同步还是异步？

同步通信是一种阻塞调用，客户端在等待返回之前会阻塞自己执行其他操作。在异步通信中，客户端在发出异步调用后可以继续执行工作。因此，客户端不会被阻塞。

在同步通信中，微服务可以提供关于成功或失败的实时响应。在实时系统中，同步服务非常有用。在异步通信中，服务必须根据未来收到的响应做出反应。

同步系统被称为基于请求/响应（request/response）。异步系统是基于事件的（event-based）。

同步微服务不是松耦合的。根据业务领域的需求和关键性，微服务可以选择同步或异步的通信形式。

# 495. 微服务架构中编排（Orchestration）和编舞（Choreography）的区别是什么？

在编排中，我们依赖一个中心系统来控制和调用各种微服务以完成任务。在编舞中，每个微服务都像一个状态机，并根据来自其他部分的输入做出反应。
编排是一种集成微服务的紧耦合方法。但编舞引入了松耦合。此外，基于编舞的系统比基于编排的系统更灵活且易于更改。
编排通常通过同步调用完成，而编舞通过异步调用完成。与异步通信相比，同步调用要简单得多。

# 496. 在微服务中使用基于 HTTP 的 REST 有哪些问题？

在 REST over HTTP 中，很难生成客户端存根（client stub）。
某些 Web 服务器也不支持所有的 HTTP 动词，如 `GET`、`PUT`、`POST`、`DELETE` 等。
由于响应中使用了 JSON 或纯文本，REST over HTTP 的性能优于 SOAP。但它不如纯二进制通信。

每个通信请求中都有 HTTP 的开销。
HTTP 并不适用于低延迟通信。
消耗负载时的工作量更多。HTTP 中可能存在序列化和反序列化的开销。

# 497. 我们可以将微服务创建为状态机吗？

可以，微服务是服务特定上下文的独立实体。对于该上下文，微服务可以作为状态机工作。在状态机中，存在导致系统状态改变的生命周期事件。
例如，在图书馆服务中，一本书会根据不同的事件改变状态，如：借书、还书、丢失书籍、逾期还、向目录添加新书等。这些事件和书籍可以构成图书馆微服务的状态机。

# 感谢

如果你喜欢这本书或以任何方式从中汲取了知识，那么我想请你帮个忙。你是否愿意在 Amazon.com 上为这本书留下一条评价？

我将不胜感激！

# 参考文献

- https://aws.amazon.com
- https://www.docker.com/
- https://www.nagios.com
- https://github.com/
