
# Jackson `@JsonView` 示例

> 原文：<http://web.archive.org/web/20230101150211/https://www.mkyong.com/java/jackson-jsonview-examples/>

在 Jackson 中，我们可以使用`@JsonView`来限制或控制不同用户的字段显示。

用于测试的 POJO。

`Staff.java`

```java
package com.mkyong;

public class Staff {

    private String name;
    private int age;
    private String[] position;
    private List<String> skills;
    private Map<String, BigDecimal> salary;

    // getters , setters , boring stuff
}
```

*用杰克逊 2.9.8 测试的 PS*

## 1. 视图

一个标准的 Java 类来定义 3 个视图：普通视图、经理视图和人力资源视图。

`CompanyViews.java`

```java
package com.mkyong;

public class CompanyViews {

    public static class Normal{};

    public static class Manager extends Normal{};

    public static class HR extends Normal{};

}
```

## 2. Json 视图

将`@JsonView`置于字段级别，以限制不同视图的字段显示。

*   正常–显示姓名和年龄。
*   经理-显示姓名、年龄、职位和技能
*   HR–显示姓名、年龄、工资和职位

P.S .经理无权查看薪资字段，HR 不关心你有什么技能🙂

`Staff.java`

```java
package com.mkyong;

import com.fasterxml.jackson.annotation.JsonView;

import java.math.BigDecimal;
import java.util.Arrays;
import java.util.List;
import java.util.Map;

public class Staff {

    @JsonView(CompanyViews.Normal.class)
    private String name;

    @JsonView(CompanyViews.Normal.class)
    private int age;

    // two views
    @JsonView({CompanyViews.HR.class, CompanyViews.Manager.class})
    private String[] position;

    @JsonView(CompanyViews.Manager.class)
    private List<String> skills;

    @JsonView(CompanyViews.HR.class)
    private Map<String, BigDecimal> salary;
}
```

## 3. Jackson–启用`@JsonView`

3.1 下面的例子向您展示了如何使用`mapper.writerWithView()`来启用`JsonView`

`JacksonExample.java`

```java
package com.mkyong;

import com.fasterxml.jackson.databind.ObjectMapper;
import com.fasterxml.jackson.databind.SerializationFeature;

import java.io.IOException;
import java.math.BigDecimal;
import java.util.Arrays;
import java.util.HashMap;
import java.util.Map;

public class JacksonExample {

    public static void main(String[] args) {

        ObjectMapper mapper = new ObjectMapper();

        Staff staff = createStaff();

        try {

            // to enable pretty print
            mapper.enable(SerializationFeature.INDENT_OUTPUT);

            // normal
            String normalView = mapper.writerWithView(CompanyViews.Normal.class).writeValueAsString(staff);

            System.out.format("Normal views\n%s\n", normalView);

            // manager
            String managerView = mapper.writerWithView(CompanyViews.Manager.class).writeValueAsString(staff);

            System.out.format("Manager views\n%s\n", managerView);

            // hr
            String hrView = mapper.writerWithView(CompanyViews.HR.class).writeValueAsString(staff);

            System.out.format("HR views\n%s\n", hrView);

        } catch (IOException e) {
            e.printStackTrace();
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

```java
Normal views
{
  "name" : "mkyong",
  "age" : 38
}

Manager views
{
  "name" : "mkyong",
  "age" : 38,
  "position" : [ "Founder", "CTO", "Writer" ],
  "skills" : [ "java", "python", "node", "kotlin" ]
}

HR views
{
  "name" : "mkyong",
  "age" : 38,
  "position" : [ "Founder", "CTO", "Writer" ],
  "salary" : {
    "2018" : 14000,
    "2012" : 12000,
    "2010" : 10000
  }
}
```

## 参考

*   [Jackson–如何忽略空字段](http://web.archive.org/web/20210814221730/https://www.mkyong.com/java/jackson-how-to-ignore-null-fields/)
*   [@ Spring MVC 上的 JSON view](http://web.archive.org/web/20210814221730/https://www.mkyong.com/spring-mvc/spring-4-mvc-ajax-hello-world-example/)
*   [杰克逊数据绑定](http://web.archive.org/web/20210814221730/https://github.com/FasterXML/jackson-databind/)
*   [Jackson 2–将 Java 对象转换成 JSON 从 JSON 转换过来](http://web.archive.org/web/20210814221730/https://www.mkyong.com/java/jackson-2-convert-java-object-to-from-json/)

Tags : [jackson](http://web.archive.org/web/20210814221730/https://mkyong.com/tag/jackson/) [json](http://web.archive.org/web/20210814221730/https://mkyong.com/tag/json/)
