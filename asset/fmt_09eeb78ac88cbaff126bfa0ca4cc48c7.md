
# 第 14 章 字符串、字符与正则表达式

```java
// 将 'stars' 替换为 'carets'
firstString = firstString.replaceAll("stars", "carets");
```

```java
System.out.printf("\"carets\": substituted for \"stars\": %s%n", firstString);

// 将单词替换为 'word'
System.out.printf("Every word replaced by \"word\": %s%n%n",
    firstString.replaceAll("\\w+", "word"));
```

```java
System.out.printf("Original String 2: %s%n", secondString);

// 将前三个数字替换为 'digit'
for (int i = 0; i < 3; i++)
    secondString = secondString.replaceFirst("\\d", "digit");
```

```java
System.out.printf("First digits replaced by \"digit\": %s%n", secondString);

// 按空白字符分割字符串
String[] results = secondString.split("\\s+"); // 按空白字符分割
System.out.println(Arrays.toString(results));
```
