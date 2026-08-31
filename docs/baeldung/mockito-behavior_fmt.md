
# 烹饪书

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/mockito-behavior>

## 1. 概述

这本食谱展示了**如何使用 Mockito 在各种示例和用例中配置行为**。

食谱的**格式是以示例为中心的**并且实用——不需要多余的细节和解释。

当然，如果你想了解更多关于用 Mockito 测试的知识，可以看看这里的其他文章。

## 延伸阅读：

### [Mockito 验证食谱](/web/20221026103513/https://www.baeldung.com/mockito-verify)

**Mockito Verify** 示例、用法和最佳实践。[Read more](/web/20221026103513/https://www.baeldung.com/mockito-verify) →

### [Mockito——利用间谍](/web/20221026103513/https://www.baeldung.com/mockito-spy)

在 Mockito 中善用 Spies，以及 Spies 与 Mocks 的区别。[Read more](/web/20221026103513/https://www.baeldung.com/mockito-spy) →

### [Mockito 的模拟方法](/web/20221026103513/https://www.baeldung.com/mockito-mock-methods)

本教程演示了 Mockito API 中标准静态模拟方法的各种用途。[Read more](/web/20221026103513/https://www.baeldung.com/mockito-mock-methods) →

我们将**模拟一个简单的 `list`** 实现，这与我们在之前的烹饪书中使用的实现相同：

```java
public class MyList extends AbstractList<String> {

    @Override
    public String get(final int index) {
        return null;
    }
    @Override
    public int size() {
        return 1;
    }
}
```

## 2. 烹饪书

**为模拟配置简单返回行为：**

```java
MyList listMock = Mockito.mock(MyList.class);
when(listMock.add(anyString())).thenReturn(false);

boolean added = listMock.add(randomAlphabetic(6));
assertThat(added).isFalse();
```

**以另一种方式配置 mock 的返回行为：**

```java
MyList listMock = Mockito.mock(MyList.class);
doReturn(false).when(listMock).add(anyString());

boolean added = listMock.add(randomAlphabetic(6));
assertThat(added).isFalse();
```

**配置 mock 在方法调用时抛出异常：**

```java
@Test(expected = IllegalStateException.class)
public void givenMethodIsConfiguredToThrowException_whenCallingMethod_thenExceptionIsThrown() {
    MyList listMock = Mockito.mock(MyList.class);
    when(listMock.add(anyString())).thenThrow(IllegalStateException.class);

    listMock.add(randomAlphabetic(6));
}
```

**配置返回类型为 `void` 的方法的行为——抛出异常：**

```java
MyList listMock = Mockito.mock(MyList.class);
doThrow(NullPointerException.class).when(listMock).clear();

listMock.clear();
```

**配置多个调用的行为：**

```java
MyList listMock = Mockito.mock(MyList.class);
when(listMock.add(anyString()))
  .thenReturn(false)
  .thenThrow(IllegalStateException.class);

listMock.add(randomAlphabetic(6));
listMock.add(randomAlphabetic(6)); // will throw the exception
```

**配置间谍的行为：**

```java
MyList instance = new MyList();
MyList spy = Mockito.spy(instance);

doThrow(NullPointerException.class).when(spy).size();
spy.size(); // will throw the exception
```

**配置方法以调用真实的、底层的方法（在模拟对象上）：**

```java
MyList listMock = Mockito.mock(MyList.class);
when(listMock.size()).thenCallRealMethod();

assertThat(listMock).hasSize(1);
```

**用自定义答案配置模拟方法调用：**

```java
MyList listMock = Mockito.mock(MyList.class);
doAnswer(invocation -> "Always the same").when(listMock).get(anyInt());

String element = listMock.get(1);
assertThat(element).isEqualTo("Always the same");
```

## 3. 结论

本指南的目标是让这些信息在网上随时可用。我已经出版了几本类似的关于 [Google Guava](https://web.archive.org/web/20221026103513/https://www.baeldung.com/guava-guide) 和 [Hamcrest](https://web.archive.org/web/20221026103513/https://www.baeldung.com/java-junit-hamcrest-guide) 的开发食谱。

所有这些例子和代码片段**的实现可以在 [GitHub](https://web.archive.org/web/20221026103513/https://github.com/eugenp/tutorials/tree/master/testing-modules/mockito-simple "Github Project exemplifying Mockito.verify") 上找到。这是一个基于 Maven 的项目，因此应该很容易导入和运行。**
