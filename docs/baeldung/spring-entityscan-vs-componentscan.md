
# Spring `@EntityScan` 与 `@ComponentScan`

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/spring-entityscan-vs-componentscan>

## 1. 介绍

在编写 Spring 应用程序时，我们可能需要指定包含实体类的特定包列表。类似地，在某些情况下，我们只需要初始化特定的 Spring beans 列表。这时可以利用 `@EntityScan` 或 `@ComponentScan` 注解。

为澄清术语，组件是带有 `@Controller`、`@Service`、`@Repository`、`@Component`、`@Bean` 等注解的类。实体是用 `@Entity` 标注的类。

在本简短教程中，我们将讨论 `@EntityScan` 和 `@ComponentScan` 在 Spring 中的用法，解释它们的用途，并指出它们的区别。

## 2. `@EntityScan` 注解

在编写 Spring 应用程序时，通常会有实体类——即用 `@Entity` 注释的类。实体类的放置方式有两种：

- 放在应用程序主包或其子包下
- 使用完全不同的根包

在第一种场景中，可以使用 `@EnableAutoConfiguration` 让 Spring 自动配置应用程序上下文。

在第二种场景中，需要为应用程序提供包的定位信息。为此，使用 `@EntityScan`。当实体类未放在主应用程序包或其子包中时，需要在主配置类中通过 `@EntityScan` 声明包或包列表，以告知 Spring 实体类的位置：

```java
@Configuration
@EntityScan("com.baeldung.demopackage")
public class EntityScanDemo {
    // ...
}
```

**应当注意，使用 `@EntityScan` 会禁用 Spring Boot 对实体的自动配置扫描。**

## 3. `@ComponentScan` 注解

与 `@EntityScan` 类似，如果希望 Spring 只使用特定的 beans 集合，可使用 `@ComponentScan` 注解。**它将指定 Spring 需要初始化的 bean 类的具体位置**。

该注解可带参数也可不带参数。不带参数时，Spring 会扫描当前包及其子包；带参数时，则明确告知 Spring 搜索的包路径。

参数方面，可以通过 `basePackages` 参数提供要扫描的包列表，或通过 `basePackageClasses` 参数指定特定类（其所属包也会被扫描）。

下面是一个 `@ComponentScan` 的使用示例：

```java
@Configuration
@ComponentScan(
  basePackages = {"com.baeldung.demopackage"}, 
  basePackageClasses = DemoBean.class)
public class ComponentScanExample {
    // ...
}
```

## 4. `@EntityScan` 对 `@ComponentScan`

总而言之，这两种注解的用途完全不同。

它们的相似之处在于，都有助于 Spring 应用程序的配置。`@EntityScan` 用于指定要扫描实体类的包；而 `@ComponentScan` 用于指定要扫描 Spring beans 的包。

## 5. 结论

在本简短教程中，我们讨论了 `@EntityScan` 和 `@ComponentScan` 注解的用法，并指出了它们的区别。
