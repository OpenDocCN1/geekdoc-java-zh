

# Java Cucumber：初学者指南

![](img/00011.jpeg)

## 关于作者

Paul Watson 先生在 `BDD` 和 `Cucumber` 方面拥有多年经验。他曾在美国、英国、新加坡、香港、迪拜、澳大利亚和瑞士参与过大型软件项目。

他的爱好包括去新的旅游胜地、看篮球、板球、足球以及学习最新的技术知识。

## 这本书适合谁

本书适用于软件开发人员、自动化测试人员、`Devops` 人以及从事 IT 项目的工程师。无论你是初学者还是丰富的开发者，这本书都将帮助你掌握 `Cucumber` 的技能。

本书从介绍 `Cucumber` 开始，然后深入探讨核心概念，如在 `IntelliJ IDEA` 中创建项目、使用标签、插件、与 `Junit` 集成、执行 `selenium` 测试、使用 `picocontainer` 和 lambda 表达式。

## 前言

本书是为初接触 `Cucumber` 的读者准备的。它将帮助你理解什么是 `Cucumber` 以及如何在软件项目中使用它。

在书中，你将学习到以下主题：

### 1. 简介

`Cucumber` 是 `BDD`（行为驱动开发）测试框架。

关于 `Cucumber` 需要注意的关键有：

1. 开源 `BDD` 测试框架。
2. 跨平台框架。
3. 测试使用英语、法语、德语等多种语言通过 `Gherkin Syntax` 编写。
4. 我们可以使用多种编程语言编写测试，如 `Ruby`、`JRuby`、`PHP`、`Java`、`Jython`、`Groovy`、`Javascript`、`Clojure`、`Gosu`、`Lua`、`.Net`、`C++`。
5. 与 `Jenkins` 和 `TeamCity` 等 CI 服务器良好集成。
6. 可以生成 `HTML`、`JSON`、`JUnit` 风格的报告。
7. `Capybara` - 测试框架是 `Cucumber` 的一部分。
8. 与 `Selenium`、`Appium`、`Spring`、`Watir`、`Ruby on Rails` 等框架良好集成。

### 2. 安装 Cucumber

设置 `Cucumber` 非常简单。你需要安装以下工具：

1. Java `JDK`
2. Java IDE - `IntelliJ IDEA` 或 `Eclipse`
3. `Cucumber` 库
4. 构建工具如 `Maven` 或 `gradle`
5. `IntelliJ IDEA` 插件 - 适用于 `Java` 的 `Gherkin` 和 `cucumber`

创建一个简单的 `Maven` 或 `gradle` 项目并添加以下依赖：

```xml
<dependency>
 <groupId>info.cukes</groupId>
 <artifactId>cucumber-java</artifactId>
 <version>1.2.4</version>
 <scope>test</scope>
</dependency>
```

要在 `Java 8` get `lambda expression` 编写测试步骤，你需要添加以下依赖：

```xml
<dependency>
 <groupId>info.cukes</groupId>
 <artifactId>cucumber-java8</artifactId>
 <version>1.2.4</version>
 <scope>test</scope>
</dependency>
```

你还需要以下 `JUnit` 依赖来将 `Cucumber` 与 `JUnit` 集成：

```xml
<dependency>
 <groupId>junit</groupId>
 <artifactId>junit</artifactId>
 <version>4.12</version>
 <scope>test</scope>
</dependency>
<dependency>
 <groupId>info.cukes</groupId>
 <artifactId>cucumber-junit</artifactId>
 <version>1.2.4</version>
 <scope>test</scope>
</dependency>
```

### 3. 使用 Gherkin 编写 feature 文件

`BDD` 是与敏捷方法一起使用的新兴软件开发模型。关于 `BDD` 需要知道的关键点有：

1. Dan North 创建了第一个 `BDD` 框架 - `Jbehave`。
2. 其他 `BDD` 框架有 `Rbehave`、`Rspec`、`Cucumber`、`Behat`。
3. 测试以故事（stories）或特性（features）的形式用纯文本编写。
4. 使用领域特定语言（`Gherkin`）来编写测试。

#### 什么是 Gherkin?

`Gherkin` 是在 `BDD` 框架（如 `cucumber`）中编写 feature 文件（称为故事文件）的纯文本语言。`Gherkin` 支持世界上大多数语言，如英语、德语、法语等。这意味着任何项目利益相关者都可以编写、阅读和理解用 `Gherkin` 编写的测试。这就是 `Gherkin` 语言的核心。

#### feature 文件的要点

1. 每个 `feature file` 可以包含一个或多个场景（scenarios），以及可选的 `outline` 和 `background`。
2. 每个场景都有 `given`、`when`、`and`、`then`、`but` 等步骤。

#### Gherkin 中的关键字有哪些？

`Gherkin` 保留了一些关键字，这些关键字在 feature 文件的范围内具有特定的含义。

以下是 Gherkin 中的关键字列表：

1. `Given` - 用于指定场景的预置条件
2. `When` - 用于指定动作
3. `And` - 用于指定额外的前置条件和动作
4. `Then` - 用于指定动作的结果
5. `Feature` - 用于指定特性的描述
6. `Scenario` - 用于指定场景的描述
7. `Outline` 和 `Examples`
8. `Background` - 用于指定在执行 feature 文件中的每个场景之前要采取的动作
9. `"""` - 用于以多行格式传递数据
10. `|` - 用于以表格格式传递数据
11. `@` - 用于为场景和功能标记标签（tag）
12. `#` - 用于对 feature 文件中的进行注释

下面的 feature 文件将让你理解 Gherkin 语言的大部分语法。

#### 基础示例 feature 文件

现在让我们来看看 gherkin 中可以拥的最简单的 feature 文件。

```gherkin
Feature: ATM 卡认证

   当 ATM 卡插入 ATM 机后，用户应被要求输入 PIN 码。

   如果输入的 PIN 码错误，用户应收到警告消息。
   如果输入的 PIN 码正确，用户应成功通过认证。

 Scenario: 在 ATM 机上输入错误的 PIN 码

  Given 我将 ATM 卡插入 ATM 机
  And 我被要求输入 PIN 码
  When 我输入正确的 PIN 码
  Then 我应该看到取款选项
```

#### 带有 Outline 和 Examples 关键字的示例 feature 文件

Scenario outline 用于我们需要重复一组动作但使用不同数据组合的情况。例如，在下面的 scenario outline 中，我们需要用不同的用户 ID 和密码组合来测试登录功能。在这种情况下，我们使用 `<VariableData>` 语法来指定变化的数据，并通过 `examples` 关键字提供数据。因此，在下面的场景中，所有步骤将执行 4 次 - 每个用户执行一次。

```gherkin
Scenario Outline: 密码规则

  Given 我们正处于登录页面
  When 我们输入用户 id <ID> 和密码 <PASSWORD>
  Then 登录结果应为 <OUTCOME>

 Examples:

    | ID    | PASSWORD | OUTCOME |
    |  Sagar|  128$9#  |     Fail|
    |  Amol |  98sjdg  |     PASS|
    |  Shaun |  jslush9  |     PASS|
    |    Ben |  KON()%  |     FAIL|
```

#### 带有 Background 的示例 feature 文件

Background 关键字用于在执行每个场景之前执行特定数量的步骤。例如，假设你想在执行每个场景之前清除浏览器 cookie，那么我们可以使用 background 关键字配合清除 cookie 的步骤。

##### 向步骤传递输入数据

每个场景可以有多个步骤，每个步骤都是用户的操作。一个步骤就像系统中的特定操作。一个步骤可能需要对输入数据进行处理。我们可以通过三种方式向步骤传递输入数据：

1. 内联变量（In-line Variables）
2. 多行字符串
3. 表格

##### 使用标签对场景和功能分组

我们在 Gherkin 中使用标签将相似的场景和功能分组在一起。`@` 符号用于标记场景和功能。

### 4. 为 Java 项目添加 Cucumber 依赖

要使用 cucumber 编写测试，我们需要添加 2 类型的依赖：

1. `cucumber-java`
2. `junit`

如果你使用 Maven 构建管理系统，可以在 POM.XML 中使用下面的 XML 块：

```xml
<dependency>
  <groupId>info.cukes</groupId>
  <artifactId>cucumber-java</artifactId>
  <version>1.2.4</version>
</dependency>
<dependency>
  <groupId>junit</groupId>
  <artifactId>junit</artifactId>
  <version>4.12</version>
  <scope>test</scope>
</dependency>
```

### 5. Cucumber 测试

#### 5.1 编写第一个 cucumber 测试

按照下面的步骤在 IntelliJ IDEA 中编写第一个 cucumber 测试：

1. 创建一个 maven 项目。
2. 在 Test Resources 目录下添加包含场景的 feature 文件。
3. 添加 Cucumber 的 maven 依赖。
4. 编写步骤定义（step definitions）并从 feature 文件执行测试。

这是我们创建并放入 test resources 文件夹的 feature 文件：

```gherkin
@selenium
Feature: 我的特性

  Scenario: 验证标题
    Given 我在 www.softpost.org 首页
    Then 我验证标题包含 tutorials
```

注意，我们没有为上述 feature 文件中的步骤添加步骤定义。当你执行 feature 文件时，你会看到下面的错误。你可以使用下面的代码片段实现缺失的步骤：

```java
@Given("^I am on the www\\.softpost\\.org home page$")
public void i_am_on_the_www_softpost_org_home_page() throws Throwable {
    // 在此处编写代码将上面的短语转换为具体的动作
    throw new PendingException();
}

@Then("^I verify that title contains tutorials$")
public void i_verify_that_title_contains_tutorials() throws Throwable {
}
```

缺失步骤的错误：

`Given I am on the www.softpost.org home page`

`Then I verify that title contains tutorials`

或者，如果你在 IntelliJ IDEA 中有 cucumber 插件，可以通过按 feature 文件中步骤上的 alt 键来创建步骤定义。以下是带有步骤定义的类：

```java
package org.softpost;

import cucumber.api.java.After;
import cucumber.api.java.Before;
import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import junit.framework.Assert;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

@SuppressWarnings("ALL")
public class seleniumsteps {

    WebDriver driver;

    @Before
    public void launchBrowser() {
        driver = new FirefoxDriver();
    }

    @Given("^I am on the www\\.softpost\\.org home page$")
    public void i_am_on_the_www_softpost_org_home_page() throws Throwable {
        driver.get("http://www.softpost.org");
    }

    @Then("^I verify that title contains tutorials$")
    public void i_verify_that_title_contains_tutorials() throws Throwable {
        Assert.assertTrue(driver.getTitle().toLowerCase().contains("tutorials"));
    }

    @After
    public void killBrowser() {
        driver.close();
        driver.quit();
    }
}
```

编写步骤定义后，你可以像下面的图片一样为 feature 文件创建运行配置（run configuration）。注意 Glue 属性非常重要。你应该在 Glue 中指定包含步骤定义的包名。

然后，你可以右键点击 feature 文件并运行测试。

如果一切正常，测试将成功运行。

`cucumber.api.junit.Cucumber` - 该类存在 `cucumber-junit` 依赖库中。

```xml
<dependency>
  <groupId>junit</groupId>
  <artifactId>junit</artifactId>
  <version>4.12</version>
  <scope>test</scope>
</dependency>

<dependency>
  <groupId>info.cukes</groupId>
  <artifactId>cucumber-junit</artifactId>
  <version>1.2.4</version>
</dependency>
```

然后你可以添加下面的测试类。运行下面的测试后，cucumber 会在 `target/selenium-reports` 生成报告。`Cucumber.class` 包含主方法，用于读取特性文件并执行其中的场景。

```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "classpath:abc.feature",
    glue = "classpath:org.softpost",
    plugin = "html:target/selenium-reports"
)
public class MyTests
{
}
```

## 7. Cucumber 选项

在执行 cucumber 场景时，我们可以传递下面提到的各种选项：

1. `features` - 特性文件的路径
2. `glue` - 步骤定义类的路径
3. `dry run` - 用于检查所有步骤定义是否已设计
4. `monochrome` - true/false，它控制输出的可读性
5. `strict` - 设置为 false 表示跳过未定义的步骤。测试不会失败
6. `name` - 用于过滤特性和场景
7. `plugin` - json, html, junit, pretty
8. `snippets` - 代码段样式可以是驼峰命名法（Camel case）或下划线（Underscore）

这是一个显示所有选项的示例测试类。




```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.SnippetType;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "classpath:abc.feature",
    glue = "classpath:org.softpost",
    tags = "~@blocked",
    plugin = "html:target/selenium-reports",
    dryRun = false,
    monochrome = true,
    strict = true,
    snippets = SnippetType.CAMELCASE
)
public class MyTests
{
}
```

# 8. 过滤场景

## 8.1 为场景标记标签

我们可以像下面的示例所示，在特性文件中使用`@`符号对场景进行标记。注意，我们也可以通过在特性文件开头编写标签来为文件中的所有场景标记。我们还可以为同一个场景关联多个标签。在下面的示例中，我们为场景标记了 4 个标签：selenium、regression、sanity 和 critical。

```gherkin
@selenium
Feature: My feature

  @regression @sanity @critical
  Scenario: Verify title
    Given I am on the www.softpost.org home page
    Then I verify that title contains tutorials
```

要执行带有`regression`和`critical`两个标签的场景，我们可以使用下面的语法。

`tags = ["@regression","@critical"]`

要执行带有`regression`或`critical`两个标签的场景，我们可以使用下面的语法：

`tags = ["@regression,@critical"]`

要跳过标记为`sanity`标签的场景，我们可以使用下面的语法：

`Negative tags = ["~@sanity"]`

我们还可以将`@Before`和`@After`方法与标记了特定名称的场景绑定。例如，下面的`before`方法将只在标记了`selenium`标签的场景之前执行。

`@Before("@selenium")`

这里是一个展示在 Cucumber 中使用标签的示例。考虑下面的特性文件。

```gherkin
@selenium
Feature: My feature

    @regression @sanity @critical
    Scenario: Verify soft title
    Given I am on the www.softpost.org home page
    Then I verify that title contains tutorials

    @sanity
    Scenario: Verify yahoo title
        Given I am on the www.yahoo.com home page
        Then I verify that title contains tutorials
```

查看下面的测试类。执行该测试类后，只有标记了`@sanity`和`@regression`的场景会被执行。

```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.SnippetType;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "classpath:abc.feature",
    glue = "classpath:org.softpost",
    tags = {"@sanity,@regression"},
    plugin = "html:target/selenium-reports",
    dryRun = false,
    monochrome = true,
    strict = true,
    snippets = SnippetType.CAMELCASE
)
public class MyTests
{
}
```

现在查看下面的测试类。执行该测试后，两个场景都会执行，因为它们都标记了`@sanity`。

```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.SnippetType;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "classpath:abc.feature",
    glue = "classpath:org.softpost",
    tags = {"@regression,@critical"},
    plugin = "html:target/selenium-reports",
    dryRun = false,
    monochrome = true,
    strict = true,
    snippets = SnippetType.CAMELCASE
)
public class MyTests
{
}
```

现在查看下面的测试类。执行该测试类后，没有任何场景会被执行，因为标签标记为`~`。

```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "classpath:abc.feature",
    glue = "classpath:org.softpost",
    tags = {"~@sanity"},
    plugin = "html:target/selenium-reports"
)
public class MyTest
{
```

## 8.2 使用`name`选项

我们可以根据名称模式来执行特定的场景。例如——考虑下面的特性文件。

```gherkin
@selenium
Feature: My feature

    @regression @sanity @critical
    Scenario: Verify soft title
    Given I am on the www.softpost.org home page
    Then I verify that title contains tutorials

    @sanity
    Scenario: Verify yahoo title
        Given I am on the www.yahoo.com home page
        Then I verify that title contains tutorials
```

要只执行名为 "softpost" 的场景，我们可以使用下面的测试类。注意我们也可以使用正则表达式来指定场景名称。

```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
    features = "classpath:abc.feature",
    glue = "classpath:org.softpost",
    name = {"softpost"},
    plugin = "html:target/selenium-reports"
)
public class MyTest
{
}
```

# 9. 向步骤传递参数

我们可以像下面的场景所示，从特性将参数传递到步骤方法。在下面的场景中，我们在`Given`步骤中传递了网站名称。传递参数的主要优势是可以在带有不同参数的场景中重用同一个步骤方法。

```gherkin
@selenium
Feature: Simple feature
  Scenario: Test web title
    Given I am on "www.yahoo.com" page
    Then I verify that the title is "yahoo"
  Scenario: Test web title
    Given I am on "www.softpost.org" page
    Then I verify that the title is "tutorials"
```

这里是上述步骤的步骤定义。注意两个场景通过不同的参数重用了相同的步骤定义。

```java
package org.softpost;
import com.google.common.primitives.Bytes;
import cucumber.api.Scenario;
import cucumber.api.java.After;
import cucumber.api.java.Before;
import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import junit.framework.Assert;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
```

```java
import org.openqa.selenium.firefox.FirefoxDriver;

public class seleniumsteps
{
    WebDriver driver;

    Scenario scenario;

    @Before("@selenium")
    public void launchBrowser(Scenario scenario)
    {
        driver = new FirefoxDriver();
        this.scenario = scenario;
        System.out.println("Executing scenario " + scenario.getName());
    }

    @After("@selenium")
    public void killBrowser()
    {
        scenario.write("Finished scenario");
        if (scenario.isFailed())
        {
            scenario.embed(((TakesScreenshot)driver).getScreenshotAs(OutputType.BYTES), "image/png");
        }
        driver.close();
        driver.quit();
    }

    @Given("^I am on \"([^\"]*)\" page$")
    public void i_am_on_page(String arg1) throws Throwable
    {
        driver.get("http://" + arg1);
    }

    @Then("^I verify that the title is \"([^\"]*)\"$")
    public void i_verify_that_the_title_is(String arg1) throws Throwable
    {
        Assert.assertTrue(driver.getTitle().toLowerCase().contains(arg1));
    }
}
```

# 10. 将数据表格传递给步骤

## 10.1 [键值对数据表格](http://www.softpost.org/cucumber/passing-data-table-with-key-and-values-to-cucumber-steps/)

我们可以像下面的示例所示，传递带有键和值的数据表格。

```gherkin
Feature: Simple Datatable feature

  Scenario: Test web title
    Given I am on home page of xyz site
    And I submit the form with below details
      |name     | sagar  |
      |id       | 98989  |
      |address  | mumbai |
    Then I see that form submission is successful
```

以下是上述场景的步骤定义类。请注意我们是如何将数据表格转换为`map`并访问其键和值的。

```java
package org.softpost;

import cucumber.api.DataTable;
import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import java.util.List;
import java.util.Map;

/**
 * Created by Sagar on 13-07-2016.
 */
public class DatatableSteps
{
    @Given("^I am on home page of xyz site$")
    public void i_am_on_home_page_of_xyz_site() throws Throwable
    {
        System.out.println("Navigate to home page \n");
    }

    @Given("^I submit the form with below details$")
    public void i_submit_the_form_with_below_details(DataTable arg1) throws Throwable
    {
        Map<String,String> m = arg1.asMap(String.class,String.class);
        System.out.println("\nFilling form with below data\n");
        for( String k : m.keySet())
        {
            System.out.println("Key -> " + k + " Value -> " + m.get(k));
        }
    }

    @Then("^I see that form submission is successful$")
    public void i_see_that_form_submission_is_successful() throws Throwable
    {
        System.out.println("\nVerify form success message");
    }
}
```

这是上述 feature 文件的执行输出。

```
Navigate to home page
Filling form with below data
Key -> name Value -> sagar
Key -> id Value -> 98989
Key -> address Value -> mumbai
Verify form success message
1 Scenarios (1 passed)
3 Steps (3 passed)
0m0.525s
```

## 10.2 [Cucumber 中的多列数据表格](http://www.softpost.org/cucumber/multiple-column-datatable-in-cucumber/)

现在让我们来看看如何在 Cucumber 中传递具有多个列的数据表格。



```gherkin
Feature: Multiple column data table

  Scenario: Create new student records
    Given We have below list of students
      | name  | id    | address  |
      | sagar | 288345 | Brisbane |
      | watson| 38829  | London   |
      | paul  | 34223  | Chicago  |
```

现在看下面的`Student`类。该类与数据表格进行了映射。

```java
package org.softpost;
/**
 * Created by Sagar on 13-07-2016.
 */
public class Student
{
    private String name;
    private String address;
    private int id;
    public Student(String name, int id, String address)
    {
        this.name = name;
        this.id = id;
        this.address = address;
    }
    public void printStudent()
    {
        System.out.println("\nStudent -> " + name + ", " + id + ", " + address);
    }
}
```

现在看步骤定义类。注意我们是如何将数据表格转换为对象列表的。

```java
package org.softpost;

import cucumber.api.DataTable;
import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import java.util.List;
import java.util.Map;

/**
 * Created by Sagar on 13-07-2016.
 */
public class DatatableSteps
{
    @Given("^We have below list of students$")
    public void we_have_below_list_of_students(DataTable arg1) throws Throwable
    {
        List<Student> students = arg1.asList(Student.class);
        for(Student s : students)
        {
            s.printStudent();
        }
    }
}
```

这是上述代码的输出。

```
Testing started at 19:48 ...
Student -> sagar, 288345, Brisbane
Student -> watson, 38829, London
Student -> paul, 34223, Chicago
1 Scenarios (1 passed)
1 Steps (1 passed)
0m0.635s
```

# 11. Feature 文件的变体

## 11.1 [场景背景 (Background)](http://www.softpost.org/cucumber/scenario-background-in-cucumber/)

有时，我们需要在每个场景之前执行某些步骤。`Background`允许在多个场景中复用相同的步骤。在在一个 feature 文件中，`Background`中的步骤会在每个场景之前执行。

```gherkin
Feature: Simple background

  Background:
    Given I filter some records

  Scenario: Delete functionality
    Given I click on the delete button of the first record
    Then I verify that record is removed from the table

  Scenario: Update functionality
    Given I click on update button of the first record
    Then I verify that record opens in new window and we can modify it
```

这是步骤定义类。

```java
package org.softpost;

import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;

/**
 * Created by Sagar on 13-07-2016.
 */
public class backgroundsteps
{
    @Given("^I filter some records$")
    public void i_filter_some_records() throws Throwable
    {
        System.out.println("\n\nBackground - Filtering some records\n");
    }

    @Given("^I click on the delete button of the first record$")
    public void i_click_on_the_delete_button_of_the_first_record() throws Throwable
    {
        System.out.println("Click delete button\n");
    }

    @Then("^I verify that record is removed from the table$")
    public void i_verify_that_record_is_removed_from_the_table() throws Throwable
    {
        System.out.println("Verify deleted record\n");
    }

    @Given("^I click on update button of the first record$")
    public void i_click_on_update_button_of_the_first_record() throws Throwable
    {
        System.out.println("Click update button\n");
    }

    @Then("^I verify that record opens in new window and we can modify it$")
    public void i_verify_that_record_opens_in_new_window_and_we_can_modify_it() throws Throwable
    {
        System.out.println("Verify modified record\n");
    }
}
```

这是上述 feature 文件的执行输出。

```
Background - Filtering some records
Click delete button
Verify deleted record
Background - Filtering some records
Click update button
Verify modified record
2 Scenarios (2 passed)
6 Steps (6 passed)
0m0.578s
```

## 11.2 [场景概要 (Scenario outline)](http://www.softpost.org/cucumber/scenario-outline-in-cucumber/)

有时，我们需要使用不同的测试数据执行相同的场景。在这种情况下，我们可以使用名为`scenario outline`的概念。在下面的示例中，相同的场景将执行两次。第一次使用 99 和 100。第二次使用 11 和 200。

```gherkin
Feature: Outline feature

  Scenario Outline: Addition of numbers
    When I add integers <i1> and <i2>

    Examples:
      | 99 | 100 |
      | 11 | 200 |
```

然后我看到的结果为`<sum>`

示例：

| i1 | i2  | sum |
|----|-----|-----|
| 99 | 100 | 199 |
| 11 | 200 | 211 |

这里是步骤定义类。

```java
package org.softpost;

import cucumber.api.java.en.Then;
import cucumber.api.java.en.When;
import junit.framework.Assert;

/**
 * 由 Sagar 于 2016-07-13 创建。
 */
public class outlinesteps
{
 int result = 0;

    @@When("^I add integers (\\d+) and (\\d+)$")
    public void i_add_integers_and(int arg1, int arg2) throws Throwable
    {
      result = arg1 + arg2;
      System.out.println("Adding " + arg1 + " and " + arg2 + "\n\n");
    }

    @Then("^I see the result as (\\d+)$")
    public void i_see_the_result_as(int arg1) throws Throwable
    {
      Assert.assertEquals(result,arg1);
    }
}
```

这里是上述 feature 文件的执行输出。

```
测试开始于 19:18 ...

Adding 99 and 100

Adding 11 and 200

2 Scenarios (2 passed)

4 Steps (4 passed)

0m0.595s
```

# 12. [在 Cucumber 中中运行多个 feature 文件](http://www.softpost.org/cucumber/how-to-run-multiple-feature-files-in-cucumber/)

我们可以像下面的示例所示，在多个 feature 文件中执行场景。我们正在运行 2 个 feature 文件 - `multicolumn`和`outline`。请注意，要执行所有 feature 文件，我们也可以使用`*`运算符。

```java
package org.softpost;

import cucumber.api.CucumberOptions;
import cucumber.api.junit.Cucumber;
import org.junit.runner.RunWith;

@RunWith(Cucumber.class)
@CucumberOptions(
      features = {"classpath:multicolumn.feature","classpath:outline.feature"},
      glue = "classpath:org.softpost",
      plugin = "html:target/selenium-reports"
)
public class MultipleFeatureTest
{
}
```

这里是执行上述测试类后生成的 HTML 报告。

![Multiple feature files in Cucumber](http://www.softpost.org/wp-content/uploads/2016/07/Multiple-feature-files-in-Cucumber.png)

Cucumber 中的多个 feature 文件

# 13. [使用 PicoContainer 共享 selenium Webdriver 实例](http://www.softpost.org/cucumber/sharing-selenium-webdriver-instance-using-picocontainer/)

在 Selenium 自动化中，我们创建了一个`WebDriver`实例。但我们无法在 Cucumber 的不同步骤定义类中使用同一个驱动实例。

我们可以通过 2 种共享同一个 Webdriver 实例：

1. 通过创建一个静态的`Webdriver`
2. 使用`PicoContainer`（依赖注入）

第一种非常简单。只需创建一个带有`Static WebDriver`字段的类即可。

现在让我们来看看如何使用依赖注入来共享同一个驱动。为此，您将需要下面的依赖。

```xml
<dependency>
  <groupId>org.seleniumhq.selenium</groupId>
  <artifactId>selenium-java</artifactId>
  <version>2.42.2</version>
</dependency>
<dependency>
  <groupId>info.cukes</groupId>
  <artifactId>cucumber-picocontainer</artifactId>
  <version>1.2.4</version>
  <scope>test</scope>
</dependency>
```

接下来，我们需要创建一个类，在其中像下面的示例所示创建一个`Webdriver`实例。请注意，我们只实例化一次驱动。我们有一个方法`getDriver`来获取驱动。

```java
package org.softpost;

import cucumber.api.java.After;
import cucumber.api.java.Before;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

public class SharedClass
{
 private static boolean startBrowser = false;
 private WebDriver driver;

 public String title = "";

    @Before("@sharedselenium")
    public void init() throws Exception
    {
      if (!startBrowser)
      {
         driver = new FirefoxDriver();
         // 如果要在每个场景后停止浏览器，将下面的变量赋值为 true
         startBrowser = false;
      }
    }

    public WebDriver getDriver()
    {
      return driver;
    }

    @After("@sharedselenium")
    public void cleanUp()
    {
      driver.close();
      driver.quit();
    }
}
```

接下来在步骤定义类中，我们可以像下面的示例所示传递上述类的实例。请注意，我们正在使用`getDriver()`方法来访问驱动实例。因此，同样可以将`SharedClass`的实例传递给任何想要使用驱动的步骤定义类。`PicoContainer`在内部被用于连接依赖类。



```java
package org.softpost;

import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import junit.framework.Assert;

public class ShareSelenium
{
    SharedClass sharedClass;

    public ShareSelenium(SharedClass sharedClass)
    {
        this.sharedClass = sharedClass;
    }

    @Given("^I am on the www\\.softpost\\.org home page$")
    public void i_am_on_the_www_softpost_org_home_page() throws Throwable
    {
        sharedClass.getDriver().get("http://www.softpost.org");
    }

    @Then("^I verify that title contains tutorials$")
    public void i_verify_that_title_contains_tutorials() throws Throwable
    {
        Assert.assertTrue(sharedClass.getDriver().getTitle().contains("tutorials"));
    }
}
```

# 14. Cucumber 中的报告

## 14.1 [嵌入截图](http://www.softpost.org/taking-screenshot-and-embed-in-the)

在处理 Selenium 项目时，我们经常需要在失败时截图。Selenium 提供通过 `takesScreenshot` 接口截图的方法。

Cucumber 允许将其嵌入报告中。

这里是简单的代码：

```java
@After("@selenium")
public void killBrowser(Scenario scenario)
{
    if (scenario.isFailed())
    {
        scenario.embed(((TakesScreenshot)driver).getScreenshot(OutputType.BYTES), "image/png");
    }
    driver.close();
    driver.quit();
}
```

下面的图片显示了在 Maven 中查找 HTML 报告的位置。

![Cucumber report in Maven](http://www.softpost.org/wp-content/uploads/2016/07/Cucumber-report-location-in-Maven.png)

Maven 项目中的 Cucumber 报告。

这里是显示捕捉截图的示例 HTML 报告。

![Embeding the screenshot](http://www.softpost.org/wp-content/uploads/2016/07/Embeding-the-screenshot-in-report.png)

在报告中嵌入截图。

## 14.2 [写入 Cucumber HTML 报告](http://www.softpost.org/writing-to-cucumber-reports/)

我们可以使用 `Scenario` 类的 `write` 方法写入 Cucumber HTML 报告。

下面的步骤定义类说明了如何写入 HTML 报告。注意我们如何将 `scenario` 对象传递给 `Before` 方法。

```java
package org.softpost;

import com.google.common.primitives.Bytes;
import cucumber.api.Scenario;
import cucumber.api.java.After;
import cucumber.api.java.Before;
import cucumber.api.java.en.Given;
import cucumber.api.java.en.Then;
import junit.framework.Assert;
import org.openqa.selenium.OutputType;
import org.openqa.selenium.TakesScreenshot;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

/**
 * 由 Sagar 于 2016-07-12 创建。
 */
@SuppressWarnings("ALL")
public class seleniumsteps
{
    WebDriver driver;
    Scenario scenario;

    @Before("@selenium")
    public void launchBrowser(Scenario scenario)
    {
        driver = new FirefoxDriver();
        this.scenario = scenario;
    }

    @Given("^I am on the www\\.softpost\\.org home page$")
    public void i_am_on_the_www_softpost_org_home_page() throws Throwable
    {
        driver.get("http://www.softpost.org");
        scenario.write("Navigated to www.softpost.org");
    }

    @Then("^I verify that title contains tutorials$")
    public void i_verify_that_title_contains_tutorials() throws Throwable
    {
        Assert.assertTrue(driver.getTitle().contains("tutorials"));
    }
}
```

```java
Assert.assertTrue(driver.getTitle().toLowerCase().contains("tutorials"));

}

@Then("^I verify that title contains tutooorials$")
public void i_verify_that_title_contains_tutooorials() throws Throwable {
    Assert.assertTrue(driver.getTitle().toLowerCase().contains("tutooorials"));
}

@After("@selenium")
public void killBrowser() {
    scenario.write("Finished scenario");
    if (scenario.isFailed()) {
        scenario.embed(((TakesScreenshot)driver).getScreenshotAs(OutputType.BYTES), "image/png");
    }
    driver.close();
    driver.quit();
}
```

这是一份示例 HTML 报告。

![写入 cucumber HTML 报告](http://www.softpost.org/wp-content/uploads/2016/07/Writing-to-cucumber-HTML-report.png)

写入 `cucumber` HTML 报告。

# 15. 使用 Lambda 表达式的 Cucumber

## 15.1 [在 Java 8 中使用 Lambda 表达式的 Cucumber 依赖](http://www.softpost.org/cucumber/cucumber-dependency-lambda-expressions-java-8/)

Java 8 引入了 Lambda 表达式。Cucumber 允许你使用 Lambda 表达式编写步骤定义。

要使用 Lambda 表达式编写测试，你需要添加以下依赖：

```xml
<dependency>
    <groupId>info.cukes</groupId>
    <artifactId>cucumber-java8</artifactId>
    <version>1.2.4</version>
    <scope>test</scope>
</dependency>
```

确保 JDK 版本为 `1.8.0_51`。否则，你将获得以下错误：

`Exception in thread "main" cucumber.runtime.CucumberException: Failed to instantiate class  .......CucumberException: java.lang.IllegalArgumentException: Wrong type at constant pool index`

## 15.2 [使用 Lambda 表达式的 Cucumber 测试](http://www.softpost.org/cucumber/cucumber-test-using-lambda-expressions/)

现在让我们使用 Lambda 表达式编写示例的 Cucumber 步骤定义。

这是一个示例特性文件（feature file）：

```gherkin
Feature: Lambda feature
  Scenario: Verify sum
    Given I add 1 and 2
    Then I verify that sum is 3
```

这是一个使用 Lambda 表达式编写步骤定义的示例测试类。注意，`StepClass` 必须实现 `cucmber.api.java8.En` 接口，且 `step` 方法应该位于测试类的构造函数中。你还需要确保 Java 语言级别应为 `1.8`。

```java
package org.softpost;

import cucumber.api.java8.En;

public class StepClass8 implements En {
    public StepClass8() {
        Given("^I add 1 and 2$", () -> {
            System.out.println("Adding 1 and 2");
        });
        Then("^I verify that sum is 3$", () -> {
            System.out.println("Checking that sum is 3");
        });
    }
}
```

如果你使用 Maven，可以在 POM.XML 中的以下 XML 部分中指定 Java 语言级别：

```xml
<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>2.3.2</version>
            <configuration>
                <source>1.8</source>
                <target>1.8</target>
                <encoding>UTF-8</encoding>
            </configuration>
        </plugin>
    </plugins>
</build>
```
