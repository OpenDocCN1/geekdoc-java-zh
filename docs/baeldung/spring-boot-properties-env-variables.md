
# 在 Spring Boot 的应用程序中使用环境变量

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/spring-boot-properties-env-variables>

## 1. 概观

在本文中，我们将解释如何在 Spring Boot 的`application.properties`中使用环境变量。然后我们将展示如何在代码中引用这些属性。

## 2. 在`application.properties` 文件中使用环境变量

让我们用值“C:\ Program Files \ JAVA \ JDK-11 . 0 . 14”定义一个名为`JAVA_HOME`的全局环境变量。

要在 Spring Boot 的`application.properties`中使用这个变量，我们需要用大括号将它括起来:

```java
java.home=${JAVA_HOME}
```

我们也可以用同样的方式使用系统属性。例如，在 Windows 上，默认情况下定义操作系统属性:

```java
environment.name=${OS}
```

也可以组合几个变量值。让我们用值“Hello Baeldung”定义另一个环境变量`HELLO_BAELDUNG`。我们现在可以像这样连接两个变量:

```java
baeldung.presentation=${HELLO_BAELDUNG}. Java is installed in the folder: ${JAVA_HOME}
```

`property` `baeldung.presentation`现在包含以下文本:“你好 Baeldung。Java 安装在文件夹中:C:\ Program Files \ Java \ JDK-11 . 0 . 14”。

这样，我们的属性根据环境的不同而有不同的值。

## 3. 在代码中使用我们的环境特定属性

假设我们启动了一个 Spring context，现在让我们解释一下如何将属性值注入到我们的代码中。

### 3.1. 用`@Value`注入值

首先，我们可以用`@Value`标注。`@Value`处理设定员、建造员、现场注射:

```java
@Value("${baeldung.presentation}")
private String baeldungPresentation;
```

### 3.2. 从 Spring 的环境中获取

我们还可以通过 Spring 的`Environment`获得属性的值。我们需要自动连线它:

```java
@Autowired
private Environment environment;
```

由于使用了`getProperty`方法，现在可以检索属性值了:

```java
environment.getProperty("baeldung.presentation")
```

### 3.3. 使用`@ConfigurationProperties`对属性进行分组

如果我们想将属性组合在一起，`@ConfigurationProperties`注释非常有用。我们将定义一个`Component`，它将收集带有给定前缀的所有属性，在我们的例子中是`baeldung`。然后我们可以为每个属性定义一个 setter。setter 的名称是属性名称的其余部分。在我们的例子中，我们只有一个叫做`presentation`的:

```java
@Component
@ConfigurationProperties(prefix = "baeldung")
public class BaeldungProperties {

    private String presentation;

    public String getPresentation() {
        return presentation;
    }

    public void setPresentation(String presentation) {
        this.presentation = presentation;
    }
}
```

我们现在可以自动关联一个`BaeldungProperties`对象:

```java
@Autowired
private BaeldungProperties baeldungProperties;
```

最后，为了获得特定属性的值，我们需要使用相应的 getter:

```java
baeldungProperties.getPresentation()
```

## 4. 结论

在本教程中，我们已经看到了如何根据环境用不同的值定义属性，并在代码中使用它们。

和往常一样，代码可以在 GitHub 上获得。
