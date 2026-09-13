
# JUnit 5 标签和过滤，@标签示例

> 原文：<http://web.archive.org/web/20230101150211/https://mkyong.com/junit5/junit-5-tagging-and-filtering-tag-examples/>

![junit 5 tag](img/328c4613a90ebe5fb23e9966e9ea0cd6.png)

本文向您展示了如何通过`@Tag`注释使用 JUnit 5 标记和过滤。

测试对象：

- JUnit 5.5.2
- Maven 3.6.0
- Gradle 5.6.2

## 1. @标签

一个简单的标签演示。

`TagMethodTest.java`

```java
package com.mkyong.tags;

import org.junit.jupiter.api.Tag;
import org.junit.jupiter.api.Test;

import static org.junit.jupiter.api.Assertions.assertEquals;

@Tag("branch-20")
public class TagMethodTest {

    @Test
    @Tag("feature-168")
    void test1Plus1() {
        assertEquals(2, 1 + 1);
    }

    @Test
    @Tag("integration")
    @Tag("fast")
    void testFastAndIntegration() {
        assertEquals(2, 1 + 1);
    }

    @Test
    @Tag("slow")
    void testSlow() {
        assertEquals(2, 1 + 1);
    }

}
```

## 2. Maven 过滤测试

2.1 在 Maven 中，我们可以通过`maven-surefire-plugin`的配置参数运行基于标签的测试。

`pom.xml`

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-surefire-plugin</artifactId>
    <version>3.0.0-M3</version>
    <configuration>
        <!-- include tags -->
        <groups>integration, feature-168</groups>
        <!-- exclude tags -->
        <excludedGroups>slow</excludedGroups>
    </configuration>
</plugin>
```

2.2 在控制台中，使用`-D`选项。

`Terminal`

```bash
# Run tests which tagged with `integration, slow, feature-168`
$ mvn -Dgroups="integration, fast, feature-168"

# Exclude tests which tagged with 'slow'
$ mvn -DexcludedGroups="slow"
```

## 3. Gradle 过滤测试

3.1 在 Gradle 中，我们可以像这样过滤标签：

`build.gradle`

```groovy
test {
    useJUnitPlatform {
        includeTags 'integration', 'feature-168'
        excludeTags 'slow'
    }
}
```

运行标记有`integration`和`feature-168`的测试。

`Terminal`

```bash
$ gradle clean test

> Task :test

com.mkyong.tags.TagMethodTest > testFastAndIntegration() PASSED

com.mkyong.tags.TagMethodTest > test1Plus1() PASSED
```

3.2 不知道如何在控制台中传递`includeTags`参数，而是创建一个新的测试任务。

`build.gradle`

```groovy
task slowTest(type: Test) {
    useJUnitPlatform {
        includeTags 'slow'
    }
}
```

运行标记为“慢”的测试。

`Terminal`

```bash
$ gradle clean slowtest

> Task :slowTest

com.mkyong.tags.TagMethodTest > testSlow() PASSED
```

**注意**

JUnit 5 支持[标签表达式](http://web.archive.org/web/20221225035521/https://junit.org/junit5/docs/current/user-guide/#running-tests-tag-expressions)。

## 下载源代码

```bash
$ git clone https://github.com/mkyong/junit-examples
$ cd junit5-examples
$ check src/test/java/com/mkyong/tag/*.java
$ check pom.xml, uncomment tags stuff
$ mvn test
$ check build.gradle, uncomment tags stuff
$ gradle test
```

## 参考

- [支持标签特定的 junit5 任务](http://web.archive.org/web/20221225035521/https://github.com/gradle/gradle/issues/6172#issuecomment-409883128)
- [Gradle 测试过滤](http://web.archive.org/web/20221225035521/https://docs.gradle.org/current/userguide/java_testing.html#test_filtering)
- [Maven Surefire 插件](http://web.archive.org/web/20221225035521/https://maven.apache.org/surefire/maven-surefire-plugin/)
- [JUnit 5 运行测试](http://web.archive.org/web/20221225035521/https://junit.org/junit5/docs/current/user-guide/#running-tests-build-maven)
