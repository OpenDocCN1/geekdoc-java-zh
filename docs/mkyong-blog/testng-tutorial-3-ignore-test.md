
# TestNG–如何忽略一个测试方法

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/unittest/testng-tutorial-3-ignore-test/>

在本教程中，我们将向您展示如何用`@Test(enabled = false)`忽略一个测试方法。

`TestIgnore.java`

```java
package com.mkyong.testng.examples.ignore;

import org.testng.Assert;
import org.testng.annotations.Test;

public class TestIgnore {

	@Test //default enable=true
	public void test1() {
		Assert.assertEquals(true, true);
	}

	@Test(enabled = true)
	public void test2() {
		Assert.assertEquals(true, true);
	}

	@Test(enabled = false)
	public void test3() {
		Assert.assertEquals(true, true);
	}

}
```

输出

```java
[TestNG] Running:

PASSED: test1
PASSED: test2

===============================================
    Default test
    Tests run: 2, Failures: 0, Skips: 0
===============================================
```

在上面的例子中，`test3()`测试方法被忽略。

[ignore](http://web.archive.org/web/20190227120518/http://www.mkyong.com/tag/ignore/) [testng](http://web.archive.org/web/20190227120518/http://www.mkyong.com/tag/testng/)
