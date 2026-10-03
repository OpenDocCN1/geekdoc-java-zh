
# 在 Selenium 中处理浏览器标签

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/java-handle-browser-tabs-selenium>

## 1. 概述

在本教程中，我们将了解如何使用 Selenium 处理浏览器标签。有时点击链接或按钮会在新标签页中打开页面。在这种情况下，我们必须正确处理标签以继续我们的测试。本教程涵盖了在新标签页中打开页面、在标签页之间切换以及关闭标签页的操作。对于我们的示例，我们将使用 <https://testpages.herokuapp.com>。

## 2. 设置

基于 [`WebDriver`设置](/web/20230103152530/https://www.baeldung.com/java-selenium-webdriver-path-error)，我们将创建一个`SeleniumTestBase`类来处理`WebDriver`的设置和拆卸。我们的测试类将扩展这个类。我们还将为 Selenium 的标签处理定义一个辅助类。这个辅助类将包含打开、切换和关闭标签的方法。这些方法将在下面的章节中展示和解释。我们将在`SeleniumTestBase`中初始化该辅助类的一个实例。所有示例均使用 JUnit5。

初始化在`init()`方法中完成，需要用`@BeforeAll`进行注解：

```java
@BeforeAll
public static void init() {
    setupChromeDriver();
}
```

在所有测试之后，teardown 或 cleanup 方法将关闭整个浏览器：

```java
@AfterAll
public static void cleanup() {
    if (driver != null) {
        driver.quit();
    }
}
```

## 3. 基础

### 3.1. 链接目标属性

我们需要处理标签的一个典型情况是，当点击一个链接或按钮时，一个新的标签被打开。网站上`target`属性设置为`_blank`的链接将在新标签中打开，例如：

```java
<a href="https://www.baeldung.com/" target="_blank">Baeldung.com</a>
```

这样的链接会在新标签中打开目标页面，例如 <https://www.baeldung.com>。

### 3.2. 窗口句柄

在 Selenium 中，每个标签都有一个窗口句柄，它是唯一的字符串。对于 Chrome 标签，字符串以`CDwindow,`开头，后跟 32 个十六进制字符，例如`CDwindow-CDE9BEF919431FDAA0FC9CB7EBBD4E1A`。**当切换到特定标签时，我们需要窗口句柄。**因此，我们需要在测试期间存储窗口句柄。

## 4. 标签处理

### 4.1. 打开标签

**有了 Selenium >= 4.0，无需 JavaScript 或浏览器热键即可打开新标签。**`WebDriver`提供了以下方法来打开新标签：

```java
driver.switchTo().newWindow(WindowType.TAB);
```

如前一节所述，有些链接设置了`target`属性。在这些情况下，我们不需要自己打开标签，但需要注意切换和关闭它们。尽管此类链接会在新标签中打开页面，但它不会切换到新标签。我们需要自己解决这个问题。一种方法是将点击链接前的窗口句柄与点击链接后的窗口句柄进行比较。应该有一个新的窗口句柄代表新打开的标签。

我们可以使用以下`WebDriver`方法检索窗口句柄集合和活动标签的窗口句柄：

```java
driver.getWindowHandles();
driver.getWindowHandle()
```

借助这些方法，我们可以在`TabHelper`类中实现一个辅助方法。它会在新标签中打开一个链接，并切换到该标签。只有在打开了新标签的情况下，才会执行标签切换。

```java
String openLinkAndSwitchToNewTab(By link) {
    String windowHandle = driver.getWindowHandle();
    Set<String> windowHandlesBefore = driver.getWindowHandles();

    driver.findElement(link).click();
    Set<String> windowHandlesAfter = driver.getWindowHandles();
    windowHandlesAfter.removeAll(windowHandlesBefore);

    Optional<String> newWindowHandle = windowHandlesAfter.stream().findFirst();
    newWindowHandle.ifPresent(s -> driver.switchTo().window(s));

    return windowHandle;
}
```

通过点击链接前后检索窗口句柄来查找新的窗口句柄。点击前的窗口句柄集合将从点击后的窗口句柄集合中移除。结果将是新标签的窗口句柄或一个空集。该方法还会在切换前返回标签的窗口句柄。

### 4.2. 切换标签

每当我们打开多个标签时，我们需要手动在它们之间切换。我们可以使用以下语句切换到特定标签，其中`destinationWindowHandle`表示我们要切换到的标签的窗口句柄：

```java
driver.switchTo().window(destinationWindowHandle)
```

可以实现一个辅助方法，该方法将目标窗口句柄作为参数，并切换到相应的标签。此外，该方法在切换前返回活动标签的窗口句柄：

```java
public String switchToTab(String destinationWindowHandle) {
    String currentWindowHandle = driver.getWindowHandle();
    driver.switchTo().window(destinationWindowHandle);
    return currentWindowHandle;
}
```

### 4.3. 关闭标签

测试之后，或者当我们不再需要某个标签时，我们需要关闭它。Selenium 提供了一条语句来关闭当前标签，如果它是最后一个打开的标签，则关闭整个浏览器：

```java
driver.close();
```

我们可以使用该语句关闭所有不再需要的标签。使用以下方法，我们可以关闭除特定标签之外的所有标签：

```java
void closeAllTabsExcept(String windowHandle) {
    for (String handle : driver.getWindowHandles()) {
        if (!handle.equals(windowHandle)) {
            driver.switchTo().window(handle);
            driver.close();
        }
    }
    driver.switchTo().window(windowHandle);
}
```

在此方法中，我们遍历所有窗口句柄。如果窗口句柄与提供的不同，我们切换到该标签并关闭它。最后，我们确保再次切换到所需的标签。

我们可以使用此方法关闭除当前打开的标签之外的所有标签：

```java
void closeAllTabsExceptCurrent() {
    String currentWindow = driver.getWindowHandle();
    closeAllTabsExcept(currentWindow);
}
```

我们现在可以在每次测试后在`SeleniumTestBase`类中使用此方法来关闭所有剩余的标签。这在测试未能在开始下一个测试之前清理浏览器的情况下特别有用，以免影响结果。我们将调用一个带有`@AfterEach`注解的方法来执行此操作：

```java
@AfterEach
public void closeTabs() {
    tabHelper.closeAllTabsExceptCurrent();
}
```

### 4.4. 使用热键处理标签

使用 Selenium，有时可以通过浏览器热键处理标签。**不幸的是，由于`ChromeDriver`的改变，这种方法似乎不再有效。**

## 5. 测试

我们可以通过几个简单的测试来验证`TabHelper`类的标签处理是否按预期工作。正如本文简介中提到的，我们的测试类需要扩展`SeleniumTestBase`：

```java
class SeleniumTabsLiveTest extends SeleniumTestBase {
    //...
}
```

对于这些测试，我们在测试类中为 URL 和定位器声明了一些常量，如下所示：

```java
By LINK_TO_ATTRIBUTES_PAGE_XPATH = By.xpath("//a[.='Attributes in new page']");
By LINK_TO_ALERT_PAGE_XPATH = By.xpath("//a[.='Alerts In A New Window From JavaScript']");

String MAIN_PAGE_URL = "https://testpages.herokuapp.com/styled/windows-test.html";
String ATTRIBUTES_PAGE_URL = "https://testpages.herokuapp.com/styled/attributes-test.html";
String ALERT_PAGE_URL = "https://testpages.herokuapp.com/styled/alerts/alert-test.html";
```

在第一个测试案例中，我们在新标签中打开一个链接。我们验证是否打开了两个标签，并且可以在它们之间切换。注意，我们总是存储相应的窗口句柄。以下代码代表此测试案例：

```java
void givenOneTab_whenOpenTab_thenTwoTabsOpen() {
    driver.get(MAIN_PAGE_URL);

    String mainWindow = tabHelper.openLinkAndSwitchToNewTab(LINK_TO_ATTRIBUTES_PAGE_XPATH);
    assertEquals(ATTRIBUTES_PAGE_URL, driver.getCurrentUrl());

    tabHelper.switchToTab(mainWindow);
    assertEquals(MAIN_PAGE_URL, driver.getCurrentUrl());
    assertEquals(2, driver.getWindowHandles().size());
}
```

在第二个测试中，我们想要验证可以关闭除第一个打开的标签之外的所有标签。我们需要提供该标签的窗口句柄。以下代码展示了此测试用例：

```java
void givenTwoTabs_whenCloseAllExceptMainTab_thenOneTabOpen() {
    driver.get(MAIN_PAGE_URL);
    String mainWindow = tabHelper.openLinkAndSwitchToNewTab(LINK_TO_ATTRIBUTES_PAGE_XPATH);
    assertEquals(ATTRIBUTES_PAGE_URL, driver.getCurrentUrl());
    assertEquals(2, driver.getWindowHandles().size());

    tabHelper.closeAllTabsExcept(mainWindow);

    assertEquals(1, driver.getWindowHandles().size());
    assertEquals(MAIN_PAGE_URL, driver.getCurrentUrl());
}
```

## 6. 结论

在本文中，我们学习了如何使用 Selenium 处理浏览器标签。我们了解了如何使用不同的窗口句柄来区分不同的标签。本文介绍了打开标签、切换标签以及完成后关闭标签的操作。

和往常一样，所有这些示例的实现都可以在 GitHub 上找到 <https://github.com/eugenp/tutorials/tree/master/testing-modules/selenium-junit-testng>。
