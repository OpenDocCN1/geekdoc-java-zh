
# Maven 和 JUnit 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/unittest/maven-and-junit-example/>

在 Maven 中，您可以像这样声明 JUnit 依赖关系：

`pom.xml`

```xml
<dependencies>
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.12</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

但是，它附带了一个捆绑的`hamcrest-core`库副本。

```bash
$ mvn dependency:tree
...
[INFO] \- junit:junit:jar:4.12:test
[INFO]    \- org.hamcrest:hamcrest-core:jar:1.3:test
...
```

## 1. Maven + JUnit + Hamcrest

**注意**

不建议使用 JUnit 默认捆绑的`hamcrest-core`副本，最好将其排除。

再次查看更新后的`pom.xml`，它排除了`hamcrest-core`的 JUnit 捆绑副本。另一方面，它还包括有用的`hamcrest-library`：

`pom.xml`

```xml
<dependencies>
    <dependency>
        <groupId>junit</groupId>
        <artifactId>junit</artifactId>
        <version>4.12</version>
        <scope>test</scope>
        <exclusions>
            <exclusion>
                <groupId>org.hamcrest</groupId>
                <artifactId>hamcrest-core</artifactId>
            </exclusion>
        </exclusions>
    </dependency>
    <!-- This will get hamcrest-core automatically -->
    <dependency>
        <groupId>org.hamcrest</groupId>
        <artifactId>hamcrest-library</artifactId>
        <version>1.3</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

再次查看依赖关系树。

```bash
$ mvn dependency:tree
...
[INFO] +- junit:junit:jar:4.12:test
[INFO] \- org.hamcrest:hamcrest-library:jar:1.3:test
[INFO]    \- org.hamcrest:hamcrest-core:jar:1.3:test
...
```

## 参考

1. [如何用 Maven 创建 Java 项目](http://web.archive.org/web/20190215000831/http://www.mkyong.com/maven/how-to-create-a-java-project-with-maven/)
2. [Maven–显示项目依赖性](http://web.archive.org/web/20190215000831/http://www.mkyong.com/maven/maven-display-project-dependency/)
3. [JUnit–与 Maven 一起使用](http://web.archive.org/web/20190215000831/https://github.com/junit-team/junit4/wiki/Use-with-Maven)

[junit](http://web.archive.org/web/20190215000831/http://www.mkyong.com/tag/junit/) [maven](http://web.archive.org/web/20190215000831/http://www.mkyong.com/tag/maven/)
