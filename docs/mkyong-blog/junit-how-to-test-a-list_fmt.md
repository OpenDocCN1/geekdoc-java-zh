
# JUnit——如何测试列表

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/unittest/junit-how-to-test-a-list/>

首先，排除掉`hamcrest-core`的 JUnit 捆绑副本，包含有用的`hamcrest-library`，它包含了很多测试`List`数据类型的有用方法。

`pom.xml`

```java
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

## 1. 断言列表字符串

检查包`org.hamcrest.collection`，它包含许多有用的方法来测试一个`Collection`或`List`。

`ListTest.java`

```java
package com.mkyong;

import org.junit.Test;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

import org.hamcrest.collection.IsEmptyCollection;

import static org.hamcrest.CoreMatchers.*;
import static org.hamcrest.collection.IsCollectionWithSize.hasSize;
import static org.hamcrest.collection.IsIterableContainingInAnyOrder.containsInAnyOrder;
import static org.hamcrest.collection.IsIterableContainingInOrder.contains;
import static org.hamcrest.MatcherAssert.assertThat;

public class ListTest {

    @Test
    public void testAssertList() {

        List<String> actual = Arrays.asList("a", "b", "c");
        List<String> expected = Arrays.asList("a", "b", "c");

        //All passed / true

        //1. Test equal.
        assertThat(actual, is(expected));

        //2. If List has this value?
        assertThat(actual, hasItems("b"));

        //3. Check List Size
        assertThat(actual, hasSize(3));

        assertThat(actual.size(), is(3));

        //4. List order

        // Ensure Correct order
        assertThat(actual, contains("a", "b", "c"));

        // Can be any order
        assertThat(actual, containsInAnyOrder("c", "b", "a"));

        //5. check empty list
        assertThat(actual, not(IsEmptyCollection.empty()));

        assertThat(new ArrayList<>(), IsEmptyCollection.empty());

    }

}
```

## 2. 断言列表整数

检查包`org.hamcrest.number`，它有断言数字的方法。

`ListTest.java`

```java
package com.mkyong;

import org.junit.Test;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.List;

import org.hamcrest.collection.IsEmptyCollection;

import static org.hamcrest.CoreMatchers.*;
import static org.hamcrest.collection.IsCollectionWithSize.hasSize;
import static org.hamcrest.collection.IsIterableContainingInAnyOrder.containsInAnyOrder;
import static org.hamcrest.collection.IsIterableContainingInOrder.contains;

import static org.hamcrest.number.OrderingComparison.greaterThanOrEqualTo;
import static org.hamcrest.number.OrderingComparison.lessThan;

import static org.hamcrest.MatcherAssert.assertThat;

public class ListTest {

    @Test
    public void testAssertList() {

        List<Integer> actual = Arrays.asList(1, 2, 3, 4, 5);
        List<Integer> expected = Arrays.asList(1, 2, 3, 4, 5);

        //All passed / true

        //1. Test equal.
        assertThat(actual, is(expected));

        //2. Check List has this value
        assertThat(actual, hasItems(2));

        //3. Check List Size
        assertThat(actual, hasSize(4));

        assertThat(actual.size(), is(5));

        //4. List order

        // Ensure Correct order
        assertThat(actual, contains(1, 2, 3, 4, 5));

        // Can be any order
        assertThat(actual, containsInAnyOrder(5, 4, 3, 2, 1));

        //5. check empty list
        assertThat(actual, not(IsEmptyCollection.empty()));

        assertThat(new ArrayList<>(), IsEmptyCollection.empty());

        //6. Test numeric comparisons
        assertThat(actual, everyItem(greaterThanOrEqualTo(1)));

        assertThat(actual, everyItem(lessThan(10)));

    }

}
```

**Note**

`org.hamcrest.collection`和`org.hamcrest.number`都属于`hamcrest-library`。

## 3. 断言列表对象

`ListTest.java`

```java
package com.mkyong;

import org.junit.Test;

import java.util.Arrays;
import java.util.List;
import java.util.Objects;

import static org.hamcrest.CoreMatchers.*;
import static org.hamcrest.Matchers.hasProperty;
import static org.hamcrest.collection.IsIterableContainingInAnyOrder.containsInAnyOrder;
import static org.junit.Assert.assertThat;

public class ListTest {

    @Test
    public void testAssertList() {

        List<Fruit> list = Arrays.asList(
                new Fruit("Banana", 99),
                new Fruit("Apple", 20)
        );

        //Test equals
        assertThat(list, hasItems(
                new Fruit("Banana", 99),
                new Fruit("Apple", 20)
        ));

        assertThat(list, containsInAnyOrder(
                new Fruit("Apple", 20),
                new Fruit("Banana", 99)
        ));

        //Test class property, and its value
        assertThat(list, containsInAnyOrder(
                hasProperty("name", is("Apple")),
                hasProperty("name", is("Banana"))
        ));

    }

    public class Fruit {

        public Fruit(String name, int qty) {
            this.name = name;
            this.qty = qty;
        }

        private String name;
        private int qty;

        public int getQty() {
            return qty;
        }

        public void setQty(int qty) {
            this.qty = qty;
        }

        public String getName() {
            return name;
        }

        public void setName(String name) {
            this.name = name;
        }

        //Test equal, override equals() and hashCode()
        @Override
        public boolean equals(Object o) {
            if (this == o) return true;
            if (o == null || getClass() != o.getClass()) return false;
            Fruit fruit = (Fruit) o;
            return qty == fruit.qty &&
                    Objects.equals(name, fruit.name);
        }

        @Override
        public int hashCode() {
            return Objects.hash(name, qty);
        }
    }

}
```

请在下面分享您的测试示例列表🙂

## 参考

1. [Hamcrest 官方网站](http://web.archive.org/web/20221022111204/http://hamcrest.org/)
2. [数组和集合的匹配器——`org.hamcrest.collection`](http://web.archive.org/web/20221022111204/http://hamcrest.org/JavaHamcrest/javadoc/1.3/org/hamcrest/collection/package-summary.html)
3. [执行数字比较的匹配器——`org.hamcrest.number`](http://web.archive.org/web/20221022111204/http://hamcrest.org/JavaHamcrest/javadoc/1.3/org/hamcrest/number/package-summary.html)
4. [Maven 和 JUnit 示例](http://web.archive.org/web/20221022111204/http://www.mkyong.com/unittest/maven-and-junit-example/)
5. [JUnit——如何测试地图](http://web.archive.org/web/20221022111204/http://www.mkyong.com/unittest/junit-how-to-test-a-map/)
6. [Java——如何覆盖 equals 和 hashCode](http://web.archive.org/web/20221022111204/http://www.mkyong.com/java/java-how-to-overrides-equals-and-hashcode/)
7. [JUnit——断言一个属性是否存在于一个类中](http://web.archive.org/web/20221022111204/http://www.mkyong.com/unittest/junit-assert-if-a-property-exists-in-a-class/)

<input type="hidden" id="mkyong-current-postId" value="13986">
