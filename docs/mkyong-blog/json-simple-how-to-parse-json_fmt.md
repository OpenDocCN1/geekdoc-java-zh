
# 简单——如何解析 JSON

> 原文：<http://web.archive.org/web/20230101150211/https://www.mkyong.com/java/json-simple-how-to-parse-json/>

在本教程中，我们将向您展示如何用 [JSON.simple](http://web.archive.org/web/20221117050521/https://cliftonlabs.github.io/json-simple/) 解析 JSON。

**注意**

您可能也有兴趣阅读——如何用 [Jackson](http://web.archive.org/web/20221117050521/https://www.mkyong.com/java/jackson-how-to-parse-json/) 或 [Gson](http://web.archive.org/web/20221117050521/https://www.mkyong.com/java/how-to-parse-json-with-gson/) 解析 JSON。

**JSON.simple 简史**

该项目最初是来自 [Yidong 的 Google code 项目](http://web.archive.org/web/20221117050521/https://github.com/fangyidong/json-simple) 的 JSON.simple 1.x，现在由 Clifton Labs 维护，阅读此 [JSON.simple 历史](http://web.archive.org/web/20221117050521/https://cliftonlabs.github.io/json-simple/)。

*PS 使用 json-simple 3.1.0 测试*

## 1. 下载 JSON.simple

`pom.xml`

```java
<dependency>
    <groupId>com.github.cliftonlabs</groupId>
    <artifactId>json-simple</artifactId>
    <version>3.1.0</version>
</dependency>
```

## 2. POJO + Jsonable

2.1 为了将 Java 对象与 JSON 相互转换，JSON.simple 需要 POJO 实现 `Jsonable`，并覆盖 `toJson()`。

`Staff.java`

```java
package com.mkyong;

import com.github.cliftonlabs.json_simple.JsonObject;
import com.github.cliftonlabs.json_simple.Jsonable;

import java.io.IOException;
import java.io.StringWriter;
import java.io.Writer;
import java.math.BigDecimal;
import java.util.Arrays;
import java.util.List;
import java.util.Map;

public class Staff implements Jsonable {

    private String name;
    private int age;
    private String[] position;
    private List<String> skills;
    private Map<String, BigDecimal> salary;

    //..getters setters

    @Override
    public String toJson() {
        final StringWriter writable = new StringWriter();
        try {
            this.toJson(writable);
        } catch (final IOException e) {
        }
        return writable.toString();
    }

    @Override
    public void toJson(Writer writer) throws IOException {

        final JsonObject json = new JsonObject();
        json.put("name", this.getName());
        json.put("age", this.getAge());
        json.put("position", this.getPosition());
        json.put("skills", this.getSkills());
        json.put("salary", this.getSalary());
        json.toJson(writer);

    }
}
```

## 3. Java 对象转 JSON

3.1 将 Java 对象转换为 JSON 字符串并保存为 `.json` 文件。

`JsonSimple1.java`

```java
package com.mkyong;

import com.github.cliftonlabs.json_simple.Jsoner;

import java.io.FileWriter;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;

public class JsonSimple1 {

    public static void main(String[] args) throws IOException {

        Staff staff = createStaff();

        // Java objects to JSON String
        String json = Jsoner.serialize(staff);

        // pretty print
        json = Jsoner.prettyPrint(json);

        System.out.println(json);

        // Java objects to JSON file
        try (FileWriter fileWriter = new FileWriter("C:\\projects\\user3.json")) {
            Jsoner.serialize(staff, fileWriter);
        }

    }

    private static Staff createStaff() {

        Staff staff = new Staff();

        staff.setName("mkyong");
        staff.setAge(38);
        staff.setPosition(new String[]{"Founder", "CTO", "Writer"});
        Map<String, BigDecimal> salary = new HashMap() {{
            put("2010", new BigDecimal(10000));
            put("2012", new BigDecimal(12000));
            put("2018", new BigDecimal(14000));
        }};
        staff.setSalary(salary);
        staff.setSkills(Arrays.asList("java", "python", "node", "kotlin"));

        return staff;

    }

}
```

输出

`Terminal`

```java
{
    "skills":[
        "java",
        "python",
        "node",
        "kotlin"
    ],
    "name":"mkyong",
    "position":[
        "Founder",
        "CTO",
        "Writer"
    ],
    "salary":{
        "2018":14000,
        "2012":12000,
        "2010":10000
    },
    "age":38
}
```

`C:\\projects\\user3.json`

```java
{"skills":["java","python","node","kotlin"],"name":"mkyong","position":["Founder","CTO","Writer"],"salary":{"2018":14000,"2012":12000,"2010":10000},"age":38}
```

3.2 将对象列表转换为 JSON 数组并保存为 `.json` 文件。

```java
Staff staff = createStaff();

List<Staff> list = Arrays.asList(createStaff(), createStaff());

// list of Java objects to JSON file
try (FileWriter fileWriter = new FileWriter("C:\\projects\\user4.json")) {
    Jsoner.serialize(list, fileWriter);
}
```

输出

`C:\\projects\\user4.json`

```java
[
{"skills":["java","python","node","kotlin"],"name":"mkyong","position":["Founder","CTO","Writer"],"salary":{"2018":14000,"2012":12000,"2010":10000},"age":38},
{"skills":["java","python","node","kotlin"],"name":"mkyong","position":["Founder","CTO","Writer"],"salary":{"2018":14000,"2012":12000,"2010":10000},"age":38}
]
```

## 4. JSON 转 Java 对象

4.1 要将 JSON 转换回 Java 对象，我们需要来自 `dozer` 第三方库的帮助来复制对象属性。

`pom.xml`

```java
<dependency>
    <groupId>net.sf.dozer</groupId>
    <artifactId>dozer</artifactId>
    <version>5.5.1</version>
</dependency>
```

4.2 JSON 字符串转 Java 对象。

`JsonSimple2.java`

```java
package com.mkyong;

import com.github.cliftonlabs.json_simple.JsonException;
import com.github.cliftonlabs.json_simple.JsonObject;
import com.github.cliftonlabs.json_simple.Jsoner;
import org.dozer.DozerBeanMapper;
import org.dozer.Mapper;

import java.io.FileReader;
import java.io.IOException;

public class JsonSimple2 {

    public static void main(String[] args) throws IOException, JsonException {

        // The file `user3.json` is generated from above example 3.1
        try (FileReader fileReader = new FileReader(("C:\\projects\\user3.json"))) {

            JsonObject deserialize = (JsonObject) Jsoner.deserialize(fileReader);

            // need dozer to copy object to staff, json_simple no api for this?
            Mapper mapper = new DozerBeanMapper();

            // JSON to object
            Staff staff = mapper.map(deserialize, Staff.class);

            System.out.println(staff);

        }

    }

}
```

输出

```java
Staff{name='mkyong', age=38, position=[Founder, CTO, Writer],
    skills=[java, python, node, kotlin], salary={2018=14000, 2012=12000, 2010=10000}}
```

4.3 JSON 数组转 Java 对象。

`JsonSimple3.java`

```java
package com.mkyong;

import com.github.cliftonlabs.json_simple.JsonArray;
import com.github.cliftonlabs.json_simple.JsonException;
import com.github.cliftonlabs.json_simple.Jsoner;
import org.dozer.DozerBeanMapper;
import org.dozer.Mapper;

import java.io.FileReader;
import java.io.IOException;
import java.util.List;
import java.util.stream.Collectors;

public class JsonSimple3 {

    public static void main(String[] args) throws IOException, JsonException {

        // The file `user4.json` is generated from above example 3.2
        try (FileReader fileReader = new FileReader(("C:\\projects\\user4.json"))) {

            JsonArray objects = Jsoner.deserializeMany(fileReader);

            Mapper mapper = new DozerBeanMapper();

            JsonArray o = (JsonArray) objects.get(0);
            List<Staff> collect = o.stream()
                .map(x -> mapper.map(x, Staff.class)).collect(Collectors.toList());
            collect.forEach(x -> System.out.println(x));

        }

    }

}
```

输出

```java
Staff{name='mkyong', age=38, position=[Founder, CTO, Writer], skills=[java, python, node, kotlin], salary={2018=14000, 2012=12000, 2010=10000}}
Staff{name='mkyong', age=38, position=[Founder, CTO, Writer], skills=[java, python, node, kotlin], salary={2018=14000, 2012=12000, 2010=10000}}
```

## 参考

- [JSON.simple 项目页面](http://web.archive.org/web/20221117050521/https://cliftonlabs.github.io/json-simple/)
- [Jackson——如何解析 JSON](http://web.archive.org/web/20221117050521/https://www.mkyong.com/java/jackson-how-to-parse-json/)
- [Gson——如何解析 JSON](http://web.archive.org/web/20221117050521/https://www.mkyong.com/java/how-to-parse-json-with-gson/)
