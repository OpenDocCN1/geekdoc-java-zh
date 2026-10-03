
# 在 Java 中按字母顺序排列列表

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-sort-list-alphabetically>

## 1. 介绍

在本教程中，我们将探索在 Java 中按字母顺序对列表进行排序的各种方法。

首先，我们将从`Collections`类开始，然后使用`Comparator`接口。我们还将使用`List`的 API 按照字母顺序排序，然后是`streams`，最后使用`TreeSet`。

此外，我们将扩展我们的示例来探索几种不同的场景，包括基于特定地区的排序列表、排序重音列表，以及使用`RuleBasedCollator`来定义我们的自定义排序规则。

## 2. 使用 `Collections` 类排序

首先，让我们看看如何使用`Collections`类对列表进行排序。

**`Collections`类提供了一个静态的重载方法`sort`**，它可以获取列表并按照自然顺序进行排序，或者我们可以使用`Comparator`提供定制的排序逻辑。

### 2.1. 按自然/词典顺序排序

首先，我们将定义输入列表:

```java
private static List<String> INPUT_NAMES = Arrays.asList("john", "mike", "usmon", "ken", "harry");
```

现在我们将首先使用`Collections`类以自然顺序对列表进行排序，也称为字典顺序:

```java
@Test
void givenListOfStrings_whenUsingCollections_thenListIsSorted() {
    Collections.sort(INPUT_NAMES);
    assertThat(INPUT_NAMES).isEqualTo(EXPECTED_NATURAL_ORDER);
}
```

其中`EXPECTED_NATURAL_ORDER`是:

```java
private static List<String> EXPECTED_NATURAL_ORDER = Arrays.asList("harry", "john", "ken", "mike", "usmon"); 
```

这里需要注意的一些要点是:

- **列表根据其元素的自然排序按升序排序**
- 我们可以传递任何元素为`Comparable`（实现`Comparable`接口）的`Collection`到`sort`方法
- 这里，**我们正在传递 `String` 类（它是一个 `Comparable`）的 `List`，因此排序工作**
- **`Collections`类改变被传递给`sort`的`List`对象的状态。因此我们不需要返回列表**

### 2.2. 逆序排序

让我们来看看如何按照相反的字母顺序对同一个列表进行排序。

让我们再次使用`sort`方法，但是现在提供一个`Comparator`:

```java
Comparator<String> reverseComparator = (first, second) -> second.compareTo(first);
```

或者，我们可以简单地从`Comparator`接口使用这个静态方法:

```java
Comparator<String> reverseComparator = Comparator.reverseOrder();
```

一旦我们有了反向比较器，我们可以简单地将其传递给`sort`:

```java
@Test
void givenListOfStrings_whenUsingCollections_thenListIsSortedInReverse() {
    Comparator<String> reverseComparator = Comparator.reverseOrder();
    Collections.sort(INPUT_NAMES, reverseComparator); 
    assertThat(INPUT_NAMES).isEqualTo(EXPECTED_REVERSE_ORDER); 
}
```

其中，预期反转顺序为:

```java
private static List<String> EXPECTED_REVERSE_ORDER = Arrays.asList("usmon", "mike", "ken", "john", "harry"); 
```

一些相关的要点如下:

- 由于`String`类是最终的，我们不能扩展和覆盖用于反向排序的`Comparable`接口的`compareTo`方法
- 我们可以使用`Comparator`接口来实现定制的排序策略，即按照`descending`的字母顺序进行排序
- 因为`Comparator`是一个函数式接口，我们可以使用 lambda 表达式

## 3. 使用 `Comparator` 接口自定义排序

通常，我们必须对需要一些自定义排序逻辑的字符串列表进行排序。这时我们实现`Comparator`接口，并提供我们想要的排序标准。

### 3.1. 用大小写混合字符串对列表进行排序的 `Comparator`

可以调用自定义排序的典型场景可以是以大写和小写字母开头的混合字符串列表。

让我们设置并测试这个场景:

```java
@Test
void givenListOfStringsWithUpperAndLowerCaseMixed_whenCustomComparator_thenListIsSortedCorrectly() {
    List<String> movieNames = Arrays.asList("amazing SpiderMan", "Godzilla", "Sing", "Minions");
    List<String> naturalSortOrder = Arrays.asList("Godzilla", "Minions", "Sing", "amazing SpiderMan");
    List<String> comparatorSortOrder = Arrays.asList("amazing SpiderMan", "Godzilla", "Minions", "Sing");

    Collections.sort(movieNames);
    assertThat(movieNames).isEqualTo(naturalSortOrder);

    Collections.sort(movieNames, Comparator.comparing(s -> s.toLowerCase()));
    assertThat(movieNames).isEqualTo(comparatorSortOrder);
}
```

请注意:

- `Comparator`之前的排序结果将是不正确的：`["Godzilla", "Minions", "Sing", "amazing SpiderMan"]`
- `String::toLowerCase`是从类型`String`中提取一个`Comparable`排序关键字并返回一个`Comparator<String>`的关键字提取器
- 使用自定义的`Comparator`排序后的正确结果将是：`["amazing SpiderMan", "Godzilla", "Minions", "Sing"]`

### 3.2. 对特殊字符进行排序的 `Comparator`

让我们考虑另一个例子，一些名字以特殊字符“@”开始。

我们希望它们排列在列表的末尾，其余的应该按照自然顺序排列:

```java
@Test
void givenListOfStringsIncludingSomeWithSpecialCharacter_whenCustomComparator_thenListIsSortedWithSpecialCharacterLast() {
    List<String> listWithSpecialCharacters = Arrays.asList("@laska", "blah", "jo", "@sk", "foo");

    List<String> sortedNaturalOrder = Arrays.asList("@laska", "@sk", "blah", "foo", "jo");
    List<String> sortedSpecialCharacterLast = Arrays.asList("blah", "foo", "jo", "@laska", "@sk");

    Collections.sort(listWithSpecialCharacters);
    assertThat(listWithSpecialCharacters).isEqualTo(sortedNaturalOrder);

    Comparator<String> specialSignComparator = Comparator.<String, Boolean>comparing(s -> s.startsWith("@"));
    Comparator<String> specialCharacterComparator = specialSignComparator.thenComparing(Comparator.naturalOrder());

    listWithSpecialCharacters.sort(specialCharacterComparator);
    assertThat(listWithSpecialCharacters).isEqualTo(sortedSpecialCharacterLast);
}
```

最后，一些要点是:

- 没有`Comparator`的排序的输出是：`["@alaska", "@ask", "blah", "foo", "jo"]`，这对于我们的场景是不正确的
- 像以前一样，我们有一个键提取器，它从类型`String`中提取一个`Comparable`排序键，并返回一个`specialCharacterLastComparator`
- 我们可以使用`thenComparing`链接`specialCharacterLastComparator`，期望另一个`Comparator`进行二次排序
- `Comparator.naturalOrder`按自然顺序比较`Comparable`对象
- 使用`Comparator`排序后的最终输出为：`["blah", "foo", "jo", "@alaska", "@ask"]`

## 4. 使用 `Streams` 进行分类

现在，让我们用 Java 8 `Streams` 对`String`的列表进行排序。

### 4.1. 按自然顺序排序

我们先按自然顺序排序:

```java
@Test
void givenListOfStrings_whenSortWithStreams_thenListIsSortedInNaturalOrder() {
    List<String> sortedList = INPUT_NAMES.stream()
      .sorted()
      .collect(Collectors.toList());

    assertThat(sortedList).isEqualTo(EXPECTED_NATURAL_ORDER);
}
```

重要的是，这里的`sorted`方法返回一个按照自然顺序排序的字符串流。

**另外，这个流的元素有`Comparable`**。

### 4.2. 逆序排序

接下来，让我们传递一个`Comparator`到`sorted`，它定义了反向排序策略:

```java
@Test
void givenListOfStrings_whenSortWithStreamsUsingComparator_thenListIsSortedInReverseOrder() {
    List<String> sortedList = INPUT_NAMES.stream()
      .sorted((element1, element2) -> element2.compareTo(element1))
      .collect(Collectors.toList());
    assertThat(sortedList).isEqualTo(EXPECTED_REVERSE_ORDER);
}
```

注意，这里我们用`Lamda`函数来定义比较器。

或者，我们可以得到相同的`Comparator`:

```java
Comparator<String> reverseOrderComparator = Comparator.reverseOrder();
```

然后我们简单地将这个`reverseOrderComparator`传递给`sorted`:

```java
List<String> sortedList = INPUT_NAMES.stream()
  .sorted(reverseOrder)
  .collect(Collectors.toList());
```

## 5. 使用 `TreeSet` 进行分类

**`TreeSet`使用一个`Comparable`接口按照排序和升序存储对象。**

我们可以简单地将未排序的列表转换成`TreeSet`，然后作为`List`收集回来:

```java
@Test
void givenNames_whenUsingTreeSet_thenListIsSorted() {
    SortedSet<String> sortedSet = new TreeSet<>(INPUT_NAMES);
    List<String> sortedList = new ArrayList<>(sortedSet);
    assertThat(sortedList).isEqualTo(EXPECTED_NATURAL_ORDER);
}
```

这种方法的一个限制是，我们的原始列表不应该有任何重复的值，如果希望在排序后的列表中保留这些值。

## 6. 使用 `List` 上的 `sort` 进行分类

我们还可以使用`List`的`sort`方法对列表进行排序:

```java
@Test
void givenListOfStrings_whenSortOnList_thenListIsSorted() {
    INPUT_NAMES.sort(Comparator.reverseOrder());
    assertThat(INPUT_NAMES).isEqualTo(EXPECTED_REVERSE_ORDER);
} 
```

注意，**`sort`方法根据指定的比较器指定的顺序对列表进行排序**。

## 7. 区域敏感列表排序

**根据语言环境，字母排序的结果会因语言规则而有所不同。**

让我们以`String`的一个`List`为例:

```java
List<String> accentedStrings = Arrays.asList("único", "árbol", "cosas", "fútbol");
```

让我们先按正常方式对它们进行排序:

```java
Collections.sort(accentedStrings);
```

输出应为：`["cosas", "fútbol", "árbol", "único"]`。

但是，我们希望使用特定的语言规则对它们进行排序。

**让我们用特定的`locale`创建一个`Collator`的实例**:

```java
Collator esCollator = Collator.getInstance(new Locale("es")); 
```

注意，这里我们使用`es` locale 创建了一个`Collator`实例。

**然后我们可以将这个排序器作为一个`Comparator`来传递，用于在`list`、`Collection`上进行排序，或者使用`Streams`**:

```java
List<String> sortedList = accentedStrings.stream()
  .sorted(esCollator)
  .collect(Collectors.toList());
```

或者使用`Collections.sort`:

```java
Collections.sort(accentedStrings, esCollator);
```

最终，输出应为：`["árbol", "cosas", "fútbol", "único"]`，符合西班牙语的字母排序规则。

## 8. 排序重音列表

对于包含重音字符的列表，如果我们使用默认的排序方法，结果可能不符合当地语言的字母顺序。

让我们考虑一个包含重音字符的列表:

```java
List<String> accentedStrings = Arrays.asList("único", "árbol", "cosas", "fútbol");
```

使用自然顺序排序后，结果为：

```java
Collections.sort(accentedStrings);
// 输出: ["cosas", "fútbol", "árbol", "único"]
```

**我们可以使用`Collator`和特定的语言环境来正确排序**:

```java
Collator esCollator = Collator.getInstance(new Locale("es"));
Collections.sort(accentedStrings, esCollator);
// 输出: ["árbol", "cosas", "fútbol", "único"]
```

**此外，我们可以定义一个自定义的`RuleBasedCollator`来指定自己的排序规则**:

```java
String rules = "< a < b < c < d < e < f < g < h < i < j < k < l < m < n < ñ < o < ...";
RuleBasedCollator customCollator = new RuleBasedCollator(rules);
Collections.sort(accentedStrings, customCollator);
```

这样，我们就可以完全控制字符串的排序方式，包括特殊字符和重音字符的处理。



```java
accentedStrings.sort((s1, s2) -> {
    return esCollator.compare(s1, s2);
});
```

排序的结果现在应该是：`[árbol, cosas, fútbol, único]`。

最后，让我们一起展示这一切：

```java
@Test
void givenListOfStringsWithAccent_whenSortWithTheCollator_thenListIsSorted() {
    List<String> accentedStrings = Arrays.asList("único", "árbol", "cosas", "fútbol");
    List<String> sortedNaturalOrder = Arrays.asList("cosas", "fútbol", "árbol", "único");
    List<String> sortedLocaleSensitive = Arrays.asList("árbol", "cosas", "fútbol", "único");

    Collections.sort(accentedStrings);
    assertThat(accentedStrings).isEqualTo(sortedNaturalOrder);

    Collator esCollator = Collator.getInstance(new Locale("es"));

    accentedStrings.sort((s1, s2) -> {
        return esCollator.compare(s1, s2);
    });

    assertThat(accentedStrings).isEqualTo(sortedLocaleSensitive);
}
```

## 8. 带重音字符的排序列表

在 Unicode 中，带有重音符号或其他修饰符号的字符可以用几种不同的方式编码，因此排序也不同。

我们可以在排序前将重音字符标准化，或者从字符中移除重音。

让我们来看看这两种排序重音列表的方法。

### 8.1. 规范化重音列表和排序

为了对这样的字符串列表进行精确排序，让我们使用`java.text.Normalizer`来规范化重音字符。

让我们从重音字符串列表开始：

```java
List<String> accentedStrings = Arrays.asList("único","árbol", "cosas", "fútbol");
```

接下来，让我们用一个`Normalize`函数定义一个`Comparator`，并将其传递给我们的`sort`方法：

```java
Collections.sort(accentedStrings, (o1, o2) -> {
    o1 = Normalizer.normalize(o1, Normalizer.Form.NFD);
    o2 = Normalizer.normalize(o2, Normalizer.Form.NFD);
    return o1.compareTo(o2);
});
```

归一化后的排序列表将是：`[árbol, cosas, fútbol, único]`。

重要的是，这里我们使用格式`Normalizer.Form.NFD`对重音字符使用规范分解来规范化数据。还有一些其他形式也可以用于规范化。

### 8.2. 去除重音符号并排序

让我们使用`Comparator`中的`StringUtils.stripAccents`方法，并将其传递给`sort`方法：

```java
@Test
void givenListOfStrinsWithAccent_whenComparatorWithNormalizer_thenListIsNormalizedAndSorted() {
    List<String> accentedStrings = Arrays.asList("único", "árbol", "cosas", "fútbol");

    List<String> naturalOrderSorted = Arrays.asList("cosas", "fútbol", "árbol", "único");
    List<String> stripAccentSorted = Arrays.asList("árbol","cosas", "fútbol","único");

    Collections.sort(accentedStrings);
    assertThat(accentedStrings).isEqualTo(naturalOrderSorted);
    Collections.sort(accentedStrings, Comparator.comparing(input -> StringUtils.stripAccents(input)));
    assertThat(accentedStrings).isEqualTo(stripAccentSorted); 
}
```

## 9. 使用`RuleBasedCollator`进行分类

我们还可以使用`java.text.RuleBasedCollator`定义自定义规则来按字母顺序排序。

这里，让我们定义自定义排序规则，并将其传递给`RuleBasedCollator`：

```java
@Test
void givenListofStrings_whenUsingRuleBasedCollator_thenListIsSortedUsingRuleBasedCollator() throws ParseException {
    List<String> movieNames = Arrays.asList(
      "Godzilla","AmazingSpiderMan","Smurfs", "Minions");

    List<String> naturalOrderExpected = Arrays.asList(
      "AmazingSpiderMan", "Godzilla", "Minions", "Smurfs");
    Collections.sort(movieNames);

    List<String> rulesBasedExpected = Arrays.asList(
      "Smurfs", "Minions", "AmazingSpiderMan", "Godzilla");

    assertThat(movieNames).isEqualTo(naturalOrderExpected);

    String rule = "< s, S < m, M < a, A < g, G";

    RuleBasedCollator rulesCollator = new RuleBasedCollator(rule);
    movieNames.sort(rulesCollator);

    assertThat(movieNames).isEqualTo(rulesBasedExpected); 
}
```

需要考虑的一些要点是：

- `RuleBasedCollator`将字符映射到排序键。
- 上面定义的规则是形式`<relations>`的，但是在规则中还有其他形式。
- 字符`s`小于`M`，`M`小于`A`，根据规则定义`A`小于`g`。
- 如果规则的构建过程失败，将引发格式异常。
- `RuleBasedCollator`实现了`Comparator`接口，因此可以传递给`sort`。

## 10. 结论

在本文中，我们研究了在 Java 中按字母顺序排列列表的各种技术。

首先，我们使用了`Collections`，然后我们用一些常见的例子解释了`Comparator`接口。

在`Comparator`之后，我们研究了`List`的`sort`方法，然后是`TreeSet`。

我们还探索了如何在不同的语言环境中处理对列表`String`的排序，规范化和排序重音列表，以及使用带有自定义规则的`RuleBasedCollator`。

一如既往，本文的完整源代码可以在 GitHub 上找到。
