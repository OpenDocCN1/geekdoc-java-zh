
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>my-project</artifactId>
    <version>1.0-SNAPSHOT</version>
</project>
```

### Maven 生命周期

Maven 遵循一个生命周期，包括`compile`、`test`、`package`、`install`等阶段。

## 第 5 节：高级技术

### 多线程

Java 内置支持多线程，允许任务的并发执行。

**示例：**

```java
public class ThreadExample {
    public static void main(String[] args) {
        Thread thread1 = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Thread 1 - Count: " + i);
            }
        });

        Thread thread2 = new Thread(() -> {
            for (int i = 0; i < 5; i++) {
                System.out.println("Thread 2 - Count: " + i);
            }
        });

        thread1.start();
        thread2.start();
    }
}
```

### Java 8 流

Java 8 引入了流，它能够对集合进行函数式操作。

**示例：**

```java
import java.util.Arrays;
import java.util.List;

public class StreamExample {
    public static void main(String[] args) {
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);

        // 使用流进行过滤和映射
        numbers.stream()
          .filter(n -> n % 2 == 0)
          .map(n -> n * n)
          .forEach(System.out::println);
    }
}
```

注解允许开发者为类、方法和字段添加元数据并应用行为。

**示例：**

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
public @interface Loggable {
}
```
