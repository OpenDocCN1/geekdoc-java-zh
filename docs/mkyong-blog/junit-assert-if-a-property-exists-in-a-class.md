
# JUnit–断言一个属性是否存在于一个类中

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/unittest/junit-assert-if-a-property-exists-in-a-class/>

包括`hamcrest-library`并用`hasProperty()`测试类属性及其值：

*用 JUnit 4.12 和 hamcrest-library 1.3 测试的 PS*

`ClassPropertyTest.java`

```java
package com.mkyong;

import org.junit.Test;

import java.util.Arrays;
import java.util.List;

import static org.hamcrest.CoreMatchers.is;
import static org.hamcrest.Matchers.containsInAnyOrder;
import static org.hamcrest.Matchers.hasProperty;
import static org.junit.Assert.assertThat;

public class ClassPropertyTest {

    //Single Object
    @Test
    public void testClassProperty() {

        Book obj = new Book("Mkyong in Action");

        assertThat(obj, hasProperty("name"));

        assertThat(obj, hasProperty("name", is("Mkyong in Action")));

    }

    // List Objects
    @Test
    public void testClassPropertyInList() {

        List<Book> list = Arrays.asList(
                new Book("Java in Action"),
                new Book("Spring in Action")
        );

        assertThat(list, containsInAnyOrder(
                hasProperty("name", is("Spring in Action")),
                hasProperty("name", is("Java in Action"))
        ));

    }

    public class Book {

        public Book(String name) {
            this.name = name;
        }

        private String name;

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }
    }
}
```

下面是包含`hamcrest-library`的 Maven pom 文件

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

## 参考

1. [hamcrest–hasProperty JavaDoc](http://web.archive.org/web/20190210095034/http://hamcrest.org/JavaHamcrest/javadoc/1.3/org/hamcrest/beans/HasProperty.html)
2. [Maven + JUnit + Hamcrest](http://web.archive.org/web/20190210095034/https://www.mkyong.com/unittest/maven-and-junit-example/)
3. [JUnit–如何测试列表](http://web.archive.org/web/20190210095034/http://www.mkyong.com/unittest/junit-how-to-test-a-list/)

[assert](http://web.archive.org/web/20190210095034/http://www.mkyong.com/tag/assert/) [hamcrest](http://web.archive.org/web/20190210095034/http://www.mkyong.com/tag/hamcrest/) [junit](http://web.archive.org/web/20190210095034/http://www.mkyong.com/tag/junit/)
