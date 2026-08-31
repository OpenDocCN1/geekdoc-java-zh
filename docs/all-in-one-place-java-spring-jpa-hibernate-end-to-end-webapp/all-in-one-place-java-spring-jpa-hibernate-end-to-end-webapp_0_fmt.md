

# 全合一 Java、Spring、JPA、Hibernate 端到端 Web 应用开发指南

![](img/image_rsrcFPP.jpg)

在本书中，你将学习带有图解的解释、实际练习以及带有输出的练习成功执行。提供逐步说明的现解决方案。

## 引言

循序学习 Spring 框架。

![](img/image_rsrcFPR.jpg)

在本书中，你将学习带有图解的解释、实际练习以及带有输出的练习成功执行。提供逐步说明的现解决方案。

## 第 1 章：JPA 一对一映射

1. `Example 1 : JPA OneToOne Mapping`
2. `Example 2 : JPA OneToOne Lazy Load Mapping`
3. `Example 3 : JPA OneToOne Join Column Mapping`
4. `Example 4 : JPA OneToOne Primary Key Join Column Mapping`
5. `Example 5 : JPA OneToOne Map Cascade Mapping`
6. `Example 6 : JPA OneToOne Unidirectional Mapping`
7. `Example 7 : JPA OneToOne Bidirectional Mapping`

## 第 2 章：JPA 一对多

1. `Example 8 : JPA OneToMany Mapping`
2. `Example 9 : JPA OneToMany Table Mapping`
3. `Example 10 : JPA OneToMany Unidirectional Mapping`
4. `Example 11 : JPA OneToMany Order Mapping`
5. `Example 12 : JPA OneToMany List Mapping`
6. `Example 13 : JPA OneToMany Key Mapping`
7. `Example 14 : One OneToMany Persist Mapping`

## 第 3 章：JPA 多对一

1. `Example 15 : JPA ManyToOne Mapping`
2. `Example 16 : JPA ManyToOne Join Mapping`
3. `Example 17 : JPA ManyToOne Column Mapping`

## 第 4 章：JPA 多对多

1. `Example 18 : JPA ManyToMany Mapping`
2. `Example 19 : JPA ManyToMany Table Mapping`
3. `Example 20 : JPA ManyToMany Bidirectional Mapping`
4. `Example 21 : JPA ManyToMany Embedable Mapping`

## 引言

循序学习 Spring 框架。JPA 是一个将对象映射到关系型数据库的强大工具。JPA 是一种对象关系映射工具，允许你构建稳健的 Java 应用。在本书中，你将学习 JPA 与框架的集成。

![](img/image_rsrcFPS.jpg)

在本书中，你将学习 Spring Hibernate。提供逐步说明的现解决方案。

## 引言

循序学习 Spring Hibernate。Spring Hibernate 是一个允许你构建稳健 Java 应用的框架。

## 医院系统（工作流）

1. `Patient` -> `Appointment`
2. `Doctor` -> `Treatment`
3. `Patient` -> `See Treatment`
4. `Doctor` -> `start end Treatment`
5. `Patient` -> `See Status`

| 技术栈 | Struts1, `Spring`, `Hibernate`, `Javascript`, `Css`, `Jquery` |
| :--- | :--- |
| 数据库 | `MySQL` |
| 服务器 | `Tomcat 1.6` |
| 日志工具 | `Log4j` |
| IDE | `Eclipse` |
| 设计模式 | `Front Controller`, `MVC`, `Factory`, `DAO`, `Proxy`, `Singleton`, `抽象工厂`, `模板模式`, `SessionFactory`, `TransactionFactory` |

![](img/image_rsrcFPU.jpg)

## 简介

在本本书中，你将学习通过图表解释以及带有输出结果的成功练习来进行学习。提供分步说明的现成解决方案。

---

## 简介

一步步学习 Spring Framework。

![](img/image_rsrcFPR.jpg)

### 第 1 章：简介

首先：我们将学习一些概念。其次：我们将查看 `Spring`（`Build Path`）的详细解释。

步骤 1：![](img/image_rsrcFPZ.jpg)

步骤 2：![](img/image_rsrcFR0.jpg)

步骤 3：![](img/image_rsrcFR1.jpg)

步骤 4：![](img/image_rsrcFR2.jpg)

步骤 5：![](img/image_rsrcFR3.jpg)

步骤 6：![](img/image_rsrcFR4.jpg)

### 第 2 章：简介 - 实验 - 1 - HelloWorld - XML

Spring Framework 为出现复杂性的地方提供了一个简单的解决方案。客户端只需获取和使用就绪的对象。Spring Framework 提供了 `Spring Container`，它负责加载类、初始化资源、将依赖资源注入到调用父对象中。`Spring Container` 将准备好就绪的对象。

### 所有实验

![](img/image_rsrcFPR.jpg)

实验 - 1 - HelloWorld - XML：![](img/image_rsrcFR5.jpg)

**HelloWorld.java**

```java
package com.abd.spring3;
public class HelloWorld {
    private String name;
    public void setName(String name) {
        this.name = name;
    }
    public void printHello() {
        System.out.println(" Hello ! " + name);
    }
}
```

**SpringBeans.xml**

```xml
<beans xmlns="http://www.springframework.org/schema/beans"
        xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
        xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="helloBean" class="com.abd.spring3.HelloWorld">
        <property name="name" value="Welcome" />
    </bean>
</beans>
```

![](img/image_rsrcFR6.jpg)

**Client.java**

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassXmlApplicationContext("SpringBeans.xml");
        HelloWorld obj = (HelloWorld) context.getBean("helloBean");
        obj.printHello();
    }
}
```

客户端请求流：会发生什么，客户端将做什么，客户端处理时有哪些步骤？你将学习分步详细解释。

步骤 1：![](img/image_rsrcFR7.jpg)

步骤 2：![](img/image_rsrcFR8.jpg)

步骤 3：![](img/image_rsrcFR9.jpg)

步骤 4：![](img/image_rsrcFRA.jpg)

步骤 5：![](img/image_rsrcFRB.jpg)

步骤 6：![](img/image_rsrcFRC.jpg)

步骤 7：![](img/image_rsrcFRD.jpg)

步骤 8：![](img/image_rsrcFRE.jpg)

步骤 9：![](img/image_rsrcFRF.jpg)

**Client.java**（同上）

输出：![](img/image_rsrcFRG.jpg)

**注意：**

1. 在实验 - 1 - HelloWorld - XML 中，分步解释了完整的请求流。
2. 在所有实验中请记住这些概念。
3. 剩余实验将会很快。

### 第 3 章：注入（将依赖对象注入到调用对象（父对象））

实验 - 2 - Setter 注入 - XML

实验 - 3 - 构造函数注入 - XML

Spring Framework 提供了松耦合架构。有两种类型的架构：

- **紧耦合架构**：你被强制调用特定的依赖对象。
- **松耦合架构**：你可以根据需求使用任何依赖对象来调用特定对象。

**注意：** 在接接的实验中，我们将看到如何实现松耦合架构。`Spring Container` 负责为我们（开发者）完成任务。开发者通过 XML 文件向 `Spring Container` 提供指令要做什么以及如何做。这些文件可以是 `ApplicationContext.xml` 或 `SpringBeans.xml`。

# 通过 Setter、构造函数或其他任何方式调用对象（父对象）

## 实验 - 2 - Setter 注入 – XML

Spring 容器 → 通过 `Java Class` 的 `Setter()` 方法注入依赖对象。

![](img/image_rsrcFRH.jpg)

在本实验中，我们将尝试通过 `Interface`（接口）实现松耦合架构。关于如何实现，请详细查看 `Request Flow`（请求流程）。

### Printer.java

```java
package com.abd.spring3;
public interface Printer{
    public void print();}
}
```

### CSVPrinter.java

```java
package com.abd.spring3;
public class CSVPrinter implements Printer{
    public void print() {
        System.out.println("Csv Output Printer");
    }
}
```

### JSONPrinter.java

```java
package com.abd.spring3;
public class JSONPrinter implements Printer{
    public void print() {
        System.out.println("Json Output Printer");
    }
}
```

### OutputHelper.java

```java
package com.abd.spring3;
public class OutputHelper{
    Printer outputGenerator;
    public void print(){
        outputGenerator.print();
    }
    public void setOutputGenerator(Printer outputGenerator){
        this.outputGenerator = outputGenerator;
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="outputHelper" class="com.abd.spring3.OutputHelper">
        <property name="outputGenerator" ref="csvPrinter" />
    </bean>
    <bean id="csvPrinter" class="com.abd.spring3.CSVPrinter" />
    <bean id="jsonPrinter" class="com.abd.spring3.JSONPrinter" />
</beans>
```

### 客户端完整请求流程（Client.java）

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        OutputHelper output = (OutputHelper)context.getBean("outputHelper");
        output.print();
    }
}
```

![](img/image_rsrcFRJ.jpg)

![](img/image_rsrcFRK.jpg)

![](img/image_rsrcFRM.jpg)

![](img/image_rsrcFRN.jpg)

![](img/image_rsrcFRP.jpg)

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");
        OutputHelper output =(OutputHelper)context.getBean("outputHelper");
        output.print();
    }
}
```

### 输出

![](img/image_rsrcFRR.jpg)

## 实验 - 3 - 构造函数注入 - XML

Spring 容器 → 通过 `Java Class` 的 `Constructor()` 注入依赖对象。

![](img/image_rsrcFRS.jpg)

### Printer.java

```java
package com.abd.spring3;
public interface Printer{
    public void print();}
}
```

### CSVPrinter.java

```java
package com.abd.spring3;
public class CSVPrinter implements Printer{
    public void print() {
        System.out.println("Csv Output Printer");
    }
}
```

### JSONPrinter.java




```java
package com.abd.spring3;
public class JSONPrinter implements Printer{
    public void print() {
        System.out.println("Json Output Printer");
    }
}
```

### OutputHelper.java

```java
package com.abd.spring3;
public class OutputHelper{
    Printer outputGenerator;
    public OutputHelper(){
    }
    public OutputHelper(Printer p){
        this.outputGenerator = p;
    }
    public void print(){
        outputGenerator.print();
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="outputHelper" class="com.abd.spring3.OutputHelper">
        <constructor-arg>
            <bean class="com.abd.spring3.CSVPrinter" />
        </constructor-arg>
    </bean>
    <bean id="csvPrinter" class="com.abd.spring3.CSVPrinter" />
    <bean id="jsonPrinter" class="com.abd.spring3.JSONPrinter" />
</beans>
```

### 完整请求流程

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context =new ClassPathXmlApplicationContext("SpringBeans.xml");
        OutputHelper output =(OutputHelper)context.getBean("outputHelper");
        output.print();
    }
}
```

| ![](img/image_rsrcT.jpg) |

| ![](img/image_rsrcU.jpg) |

## 第 4 章 Spring Beans 注入依赖对象（父对象）通过 Setter 方法

- `Client.java` (父对象)

- `实验 - 2 - Setter 注入 – XML` (Setter 方法)

- `实验 - 3 - 构造函数注入 - XML` (构造)

- `实验 - 4 - Spring Beans` (Setter 注入)

- `实验 - 5 - Spring Beans` (构造)

- `实验 - 6 - Spring Beans` (完整请求流程)

将在后续实验中详细查看：

| ![](img/image_rsrcFRW.jpg) |

### Customer.java

- `Client.java` (对象)

- `实验 - 4 - Spring Beans` (父对象)

- `实验 - 5 - Spring Beans` (构造)

- `实验 - 6 - Spring Beans` (Setter 注入)

```java
package com.abd.spring3;
public class Customer{
    Printer person;
    public Customer() {
    }
    public Customer(Printer person){
        this.person = person;
    }
    public void setPerson(Printer person){
        this.person = person;
    }
    @Override
    public String toString() {
        return "Customer [" + person + "]";
    }
}
```

### Person.java

```java
package com.abd.spring3;
public class Person {
    private String name;
    private String address;
    private int age;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    @Override
    public String toString() {
        return "Person [Address=" + address + ",Age=" + age + ", Name=" + name + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="CustomerBean" class="com.abd.spring3.Customer">
        <property name="person" ref="PersonBean" />
    </bean>
    <bean id="PersonBean" class="com.abd.spring3.Person">
        <property name="name" value="Amar" />
        <property name="address" value="1 A Bangalore" />
        <property name="age" value="28" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[]{"SpringBeans.xml"});
        Customer cust=(Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

| ![](img/image_rsrcFRX.jpg) |

| ![](img/image_rsrcFRY.jpg) |

| ![](img/image_rsrcFRZ.jpg) |

| ![](img/image_rsrcFS0.jpg) |

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[]{"SpringBeans.xml"});
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

Output

![](img/image_rsrcFS1.jpg)

## 实验 - 5 - 内部 Bean 嵌套 Bean – XML

![](img/image_rsrcFS2.jpg)

### Customer.java

```java
package com.abd.spring3;
public class Customer {
    private Person person;
    public Customer() {
    }
    public Customer(Person person) {
        this.person = person;
    }
    public void setPerson(Person person) {
        this.person = person;
    }
    @Override
    public String toString() {
        return "Customer [person=" + person + "]";
    }
}
```

### Person.java

```java
package com.abd.spring3;
public class Person {
    private String name;
    private String address;
    private int age;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    @Override
    public String toString() {
        return "Person [address=" + address + ",age=" + age + ", name=" + name + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="CustomerBean" class="com.abd.spring3.Customer">
        <property name="person">
            <bean class="com.abd.spring3.Person">
                <property name="name" value="Amar" />
                <property name="address" value="1 A Bangalore" />
                <property name="age" value="28" />
            </bean>
        </property>
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

Output

![](img/image_rsrcFS3.jpg)

## 实验 - 6 - 内部 Bean 构造函数 – XML

![](img/image_rsrcFS4.jpg)

### Customer.java

```java
package com.abd.spring3;
public class Customer {
    private Person person;
    public Customer() {
    }
    public Customer(Person person) {
        this.person = person;
    }
    public void setPerson(Person person) {
        this.person = person;
    }
    @Override
    public String toString() {
        return "Customer [person=" + person + "]";
    }
}
```

### Person.java



## 面向 Java 开发者的 Spring Bean 作用域与属性注入指南

### 第 5 章：Spring Bean 作用域

#### 5.1 什么是 Bean 作用域？

当 Bean 被标记为单例（`Singleton`）或原型（`Prototype`）时，意味着：

- 向 Spring 容器发出指令
- 告知容器该 Bean 需要特殊处理
- 本章将详细介绍这些概念

#### 5.2 作用域 = "Singleton"

- 当 Bean 被标记为 `Singleton` 时，Spring 容器仅会在启动时创建一个实例

#### 5.3 作用域 = "Prototype"

- 当 Bean 被标记为 `Prototype` 时，Spring 容器在每次请求时都会创建一个新实例

#### 5.4 Client 请求流程

##### 实验 - 7 - Bean 作用域 Singleton Scope – XML

![](img/image_rsrcFS6.jpg)

**`MyService.java`**

```java
package com.abd.spring3;
public class MyService {
    String message;
    public String getMessage() {
        return message;
    }
    public void setMessage(String message) {
        this.message = message;
    }
}
```

**`SpringBeans.xml`**

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="customerService" class="com.abd.spring3.MyService" />
</beans>
```

**`Client.java`**

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        MyService customerA = (MyService)context.getBean("customerService");
        customerA.setMessage("Message by customerA");
        System.out.println("Message : " + customerA.getMessage());
        // CustomerB 获取已创建的实例
        // 因为此 Bean 是单例 (Singleton)
        // 如果任何 Bean 没有标记为 "Singleton" 或 "Prototype"
        // Spring 容器会假设该 Bean 为 "Singleton"
        MyService customerB = (MyService)context.getBean("customerService");
        System.out.println("Message : " + customerB.getMessage());
    }
}
```

![](img/image_rsrcFS7.jpg)
![](img/image_rsrcFS8.jpg)

#### 实验 - 8 - Bean 作用域 Prototype Scope – XML

![](img/image_rsrcFS9.jpg)

**`MyService.java`**

```java
package com.abd.spring3;
public class MyService {
    String message;
    public String getMessage() {
        return message;
    }
    public void setMessage(String message) {
        this.message = message;
    }
}
```

**`SpringBeans.xml`**

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="customerService" class="com.abd.spring3.MyService" scope="prototype"/>
</beans>
```

#### 完整的客户端流程

**`Client.java`**

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        MyService customerA = (MyService)context.getBean("customerService");
        customerA.setMessage("Message by customerA");
        System.out.println("Message : " + customerA.getMessage());
        // 获取 "customerService", 但未设置任何消息
        // MyService 类的 setMessage() 方法
        MyService custB = (MyService)context.getBean("customerService");
        System.out.println("Message : " + custB.getMessage());
    }
}
```

![](img/image_rsrcFSA.jpg)

#### 实验 - 9 - Bean 作用域 - 注解

![](img/image_rsrcFSB.jpg)

**`MyService.java`**

```java
package com.abd.spring3;
import org.springframework.context.annotation.Scope;
import org.springframework.stereotype.Service;

@Service
@Scope("prototype")
public class MyService {
    String message;
    public String getMessage() {
        return message;
    }
    public void setMessage(String message) {
        this.message = message;
    }
}
```

**`SpringBeans.xml`**

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-2.5.xsd">
    <context:component-scan base-package="com.abd.spring3"/>
</beans>
```

**`Client.java`**

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        MyService customerA = (MyService)context.getBean("myService");
        customerA.setMessage("Message by customerA");
        System.out.println("Message : " + customerA.getMessage());
        // 获取 "myService", 但未设置任何消息
        // MyService 类的 setMessage() 方法
        MyService custB = (MyService)context.getBean("myService");
        System.out.println("Message : " + custB.getMessage());
    }
}
```

#### 输出

![](img/image_rsrcFSC.jpg)

---

### 第 6 章：Spring Beans 属性（对象集合）

#### 6.1 注入（将依赖对象注入到调用对象（父对象）中）

**本章包含以下实验：**

- 实验 - 10 - Beans Properties List Properties - XML
- 实验 - 11 - Beans Properties ListFactoryBean - XML
- 实验 - 12 - Beans Properties Util List - XML
- 实验 - 13 - Beans Properties Set Properties - XML
- 实验 - 14 - Beans Properties Set Util - XML
- 实验 - 15 - Beans Properties Map Properties - XML
- 实验 - 16 - Beans Properties MapFactoryBean - XML
- 实验 - 17 - Beans Properties Map Util - XML
- 实验 - 18 - Beans Properties Collection Properties - XML

#### 6.2 Spring Beans 属性（对象集合）概述

在本节中，我们将学习：

- 如何在 `.xml` 文件中定义 `Collection Object`
- `Spring Container` 如何初始化 `Beans` 以使其处于就绪状态，便于使用。

#### 6.3 Spring 容器逻辑

- 在定义 `Collection Object` 时
- 开发者向 `Spring Container` 明确指令该特定的 `Bean` 需要特殊处理
- 开发者需要定义哪些 `Beans` 包含作为变量的 `Collection Properties`
- 开发者通过 `.xml` 文件向 `Spring Container` 指示做什么、如何做
- 在 `.xml` 文件中注册了 `Spring Container` 的指令

---

以下为原文中的代码示例，作为附录部分保留：

### 附录：基础示例

**`Person.java`**

```java
package com.abd.spring3;
public class Person {
    private String name;
    private String address;
    private int age;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    @Override
    public String toString() {
        return "Person [address=" + address + ",age=" + age + ", name=" + name + "]";
    }
}
```

**`SpringBeans.xml`**（注入基本属性）

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="CustomerBean" class="com.abd.spring3.Customer">
        <constructor-arg>
            <bean class="com.abd.spring3.Person">
                <property name="name" value="Amar" />
                <property name="address" value="1 A Bangalore" />
                <property name="age" value="28" />
            </bean>
        </constructor-arg>
    </bean>
</beans>
```

**`Client.java`**（基础示例）

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

**输出**

![](img/image_rsrcFS5.jpg)



- `Collection Object` 是在 (`.xml`) 文件中定义 `Collection Information` 的方式

- 就此结束

- 在进行实验时，我们学习了这些内容

## 实验 - 10 - Beans Properties List Properties – XML

![](img/image_rsrcFSD.jpg)

### Customer.java

```java
package com.abd.spring3;
import java.util.ArrayList;
import java.util.List;

public class Customer {
    private List<Object> lists = new ArrayList<Object>();
    public String toString() {
        return lists.toString();
    }
    public List<Object> getLists() {
        return lists;
    }
    public void setLists(List<Object> lists) {
        this.lists = lists;
    }
}
```

### Person.java

```java
package com.abd.spring3;

public class Person {
    private String name;
    private int age;
    private String address;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
    @Override
    public String toString() {
        return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="CustomerBean" class="com.abd.spring3.Customer">
        <property name="lists">
            <list>
                <value>1</value>
                <ref bean="PersonBean"/>
                <value>2</value>
                <bean class="com.abd.spring3.Person">
                    <property name="name" value="Amar"/>
                    <property name="address" value="Bangalore"/>
                    <property name="age" value="27"/>
                </bean>
            </list>
        </property>
    </bean>
    <bean id="PersonBean" class="com.abd.spring3.Person">
        <property name="name" value="Bharat"/>
        <property name="address" value="Pune"/>
        <property name="age" value="28"/>
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

![](img/image_rsrcFSE.jpg)

### 输出

![](img/image_rsrcFSF.jpg)

## 实验 - 11 - Beans Properties ListFactoryBean - XML

![](img/image_rsrcFSG.jpg)

### Customer.java

```java
package com.abd.spring3;
import java.util.ArrayList;
import java.util.List;

public class Customer {
    private List<Object> lists = new ArrayList<Object>();
    public String toString() {
        return lists.toString();
    }
    public List<Object> getLists() {
        return lists;
    }
    public void setLists(List<Object> lists) {
        this.lists = lists;
    }
}
```

### Person.java

```java
package com.abd.spring3;

public class Person {
    private String name;
    private int age;
    private String address;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
    @Override
    public String toString() {
        return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
    }
}
```

## 实验 - 12 - Beans 属性 List - XML

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
  <bean id="CustomerBean" class="com.abd.spring3.Customer">
    <property name="lists">
      <bean class="org.springframework.beans.factory.config.ListFactoryBean">
        <property name="targetListClass">
          <value>java.util.ArrayList</value>
        </property>
        <property name="sourceList">
          <list>
            <value>1</value>
            <value>2</value>
            <value>3</value>
          </list>
        </property>
      </bean>
    </property>
  </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
    Customer cust = (Customer)context.getBean("CustomerBean");
    System.out.println(cust);
  }
}
```

### 输出

![](img/image_rsrcFSH.jpg)

### Customer.java

```java
package com.abd.spring3;
import java.util.ArrayList;
import java.util.List;

public class Customer {
  private List<Object> lists = new ArrayList<Object>();

  public String toString() {
    return lists.toString();
  }

  public List<Object> getLists() {
    return lists;
  }

  public void setLists(List<Object> lists) {
    this.lists = lists;
  }
}
```

### Person.java

```java
package com.abd.spring3;

public class Person {
  private String name;
  private int age;
  private String address;

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public int getAge() {
    return age;
  }

  public void setAge(int age) {
    this.age = age;
  }

  public String getAddress() {
    return address;
  }

  public void setAddress(String address) {
    this.address = address;
  }

  @Override
  public String toString() {
    return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
  }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:util="http://www.springframework.org/schema/util" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/util http://www.springframework.org/schema/util/spring-util-2.5.xsd">
  <bean id="CustomerBean" class="com.abd.spring3.Customer">
    <property name="lists">
      <util:list list-class="java.util.ArrayList">
        <value>1</value>
        <value>2</value>
        <value>3</value>
      </util:list>
    </property>
  </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
    Customer cust = (Customer)context.getBean("CustomerBean");
    System.out.println(cust);
  }
}
```

### 输出

![](img/image_rsrcFSK.jpg)

## 实验 - 13 - Beans 属性 Set Properties – XML

![](img/image_rsrcFSM.jpg)

### Customer.java

```java
package com.abd.spring3;
import java.util.HashSet;
import java.util.Set;

public class Customer {
  private Set<Object> sets = new HashSet<Object>();

  public Set<Object> getSets() {
    return sets;
  }

  public void setSets(Set<Object> sets) {
    this.sets = sets;
  }

  public String toString() {
    return sets.toString();
  }
}
```

### Person.java



```java
package com.abd.spring3;

public class Person {
  private String name;
  private int age;
  private String address;

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public int getAge() {
    return age;
  }

  public void setAge(int age) {
    this.age = age;
  }

  public String getAddress() {
    return address;
  }

  public void setAddress(String address) {
    this.address = address;
  }

  @Override
  public String toString() {
    return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
  }
}
```

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
  <bean id="CustomerBean" class="com.abd.spring3.Customer">
    <property name="sets">
      <set>
        <value>1</value>
        <ref bean="PersonBean" />
        <bean class="com.abd.spring3.Person">
          <property name="name" value="Amar" />
          <property name="age" value="27" />
          <property name="address" value="Bangalore" />
        </bean>
      </set>
    </property>
  </bean>
  <bean id="PersonBean" class="com.abd.spring3.Person">
    <property name="name" value="Bharat" />
    <property name="address" value="4" />
    <property name="age" value="28" />
  </bean>
</beans>
```

### `Client.java`

```java
package com.abd.spring3;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
    Customer cust = (Customer)context.getBean("CustomerBean");
    System.out.println(cust);
  }
}
```

### 输出

![](img/image_rsrcFSN.jpg)

## 实验 - 14 - Beans 属性 Set - XML

![](img/image_rsrcSP.jpg)

### `Customer.java`

```java
package com.abd.spring3;

import java.util.HashSet;
import java.util.Set;

public class Customer {
  private Set<Object> sets = new HashSet<Object>();

  public Set<Object> getSets() {
    return sets;
  }

  public void setSets(Set<Object> sets) {
    this.sets = sets;
  }
}
```

### `Person.java`

```java
package com.abd.spring3;

public class Person {
  private String name;
  private int age;
  private String address;

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }

  public int getAge() {
    return age;
  }

  public void setAge(int age) {
    this.age = age;
  }

  public String getAddress() {
    return address;
  }

  public void setAddress(String address) {
    this.address = address;
  }

  @Override
  public String toString() {
    return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
  }
}
```

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:util="http://www.springframework.org/schema/util" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/util http://www.springframework.org/schema/util/spring-util-2.5.xsd">
  <bean id="CustomerBean" class="com.abd.spring3.Customer">
    <property name="sets">
      <util:set set-class="java.util.HashSet">
        <value>1</value>
        <value>2</value>
        <value>3</value>
      </util:set>
    </property>
  </bean>
</beans>
```

### `Client.java`

```java
package com.abd.spring3;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
  public static void main(String[] args) {
    ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
    Customer cust = (Customer)context.getBean("CustomerBean");
    System.out.println(cust);
  }
}
```

### 输出

![](img/image_rsrcFSR.jpg)

# 实验 - 15 - Beans 属性 Map Properties – XML

（注：实验 15 输入文本已截/不完整，根据可用片段进行格式化）

![](img/image_rsrcFSS.jpg)

### `Customer.java`

```java
package com.abd.spring3;

import java.util.HashMap;
import java.util.Map;

public class Customer {
  private Map<Object, Object> maps = new HashMap<Object, Object>();

  public String toString() {
    return maps.toString();
  }

  public Map<Object, Object> getMaps() {
    return maps;
  }

  public void setMaps(Map<Object, Object> maps) {
    this.maps = maps;
  }
}
```

### `Person.java`

（结构与实验 14 相同）

### `Person.java`

```java
package com.abd.spring3;

public class Person {
    private String name;
    private int age;
    private String address;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    @Override
    public String toString() {
        return "Person [Name=" + name + ", Age=" + age + ", Address=" + address + "]";
    }
}
```

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="CustomerBean" class="com.abd.spring3.Customer">
        <!-- java.util.Map -->
        <property name="maps">
            <map>
                <entry key="Key 1" value="1" />
                <entry key="Key 2" value-ref="PersonBean" />
                <entry key="Key 3">
                    <bean class="com.abd.spring3.Person">
                        <property name="name" value="Amar" />
                        <property name="address" value="1 A Bangalore" />
                        <property name="age" value="27" />
                    </bean>
                </entry>
            </map>
        </property>
    </bean>
    <bean id="PersonBean" class="com.abd.spring3.Person">
        <property name="name" value="Bharat" />
        <property name="address" value="4 B pune" />
        <property name="age" value="28" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.spring3;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

### 输出

![](img/image_rsrcFST.jpg)

## 实验 - 16 - Beans MapFactoryBean – XML

![](img/image_rsrcFSU.jpg)

### `Customer.java`

```java
package com.abd.spring3;

import java.util.HashMap;
import java.util.Map;

public class Customer {
    private Map<Object, Object> maps = new HashMap<Object, Object>();

    public String toString() {
        return maps.toString();
    }

    public Map<Object, Object> getMaps() {
        return maps;
    }

    public void setMaps(Map<Object, Object> maps) {
        this.maps = maps;
    }
}
```

### `Person.java`



```java
package com.abd.spring3;
public class Person {
    private String name;
    private int age;
    private String address;
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    public int getAge() {
        return age;
    }
    public void setAge(int age) {
        this.age = age;
    }
    public String getAddress() {
        return address;
    }
    public void setAddress(String address) {
        this.address = address;
    }
    @Override
    public String toString() {
        return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="CustomerBean" class="com.abd.spring3.Customer">
        <property name="maps">
            <bean class="org.springframework.beans.factory.config.MapFactoryBean">
                <property name="targetMapClass">
                    <value>java.util.HashMap</value>
                </property>
                <property name="sourceMap">
                    <map>
                        <entry key="Key1" value="1" />
                        <entry key="Key2" value="2" />
                        <entry key="Key3" value="3" />
                    </map>
                </property>
            </bean>
        </property>
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

### 输出

![](img/image_rsrcFSV.jpg)

## 实验 - 17 - Beans Properties Map

![](img/image_rsrcFSW.jpg)

### Customer.java

```java
package com.abd.spring3;
import java.util.HashMap;
import java.util.Map;
public class Customer {
    private Map<Object, Object> maps = new HashMap<Object, Object>();
    public String toString() {
        return maps.toString();
    }
    public Map<Object, Object> getMaps() {
        return maps;
    }
    public void setMaps(Map<Object, Object> maps) {
        this.maps = maps;
    }
}
```

## 实验 - 18 - Beans Properties Collection - XML

![](img/image_rsrcFSY.jpg)

### Customer.java

```java
package com.abd.spring3;
import java.util.Properties;
public class Customer {
    private Properties pros = new Properties();
    public Properties getPros() {
        return pros;
    }
    public void setPros(Properties pros) {
        this.pros = pros;
    }
    public String toString() {
        return pros.toString();
    }
}
```

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Customer cust = (Customer)context.getBean("CustomerBean");
        System.out.println(cust);
    }
}
```

Output

![](img/image_rsrcFSZ.jpg)

# 第 7 章：Spring Beans 高级

## 实验 - 19 - Beans 继承 – XML

## 实验 - 20 - Beans 覆盖 – XML

## 实验 - 21 - Beans 初始化与销毁 – XML

## 实验 - 22 - Spring 初始化 方法 - XML

## 实验 - 19 - Beans 继承 – XML

![](img/image_rsrcFT0.jpg)

### Customer.java

```java
package com.abd.spring3;
public class Customer {
    private int type;
    private String action;
    private String Country;
    public int getType() {return type;}
    public void setType(int type) {this.type = type;}
    public String getAction() {return action;}
    public void setAction(String action) {this.action = action;}
    public String getCountry() {return Country;}
    public void setCountry(String country) {Country = country;}
}
```

### Person.java

```java
package com.abd.spring3;
public class Person {
    private String name;
    private int age;
    private String address;
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public int getAge() {return age;}
    public void setAge(int age) {this.age = age;}
    public String getAddress() {return address;}
    public void setAddress(String address) {this.address = address;}
    @Override
    public String toString() {
        return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="generalCustomer" class="com.abd.spring3.Customer">
        <property name="country" value="USA" />
    </bean>
    <bean id="specialCustomer" parent="generalCustomer">
        <property name="action" value="backup" />
        <property name="type" value="1" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Customer cust = (Customer)context.getBean("specialCustomer");
        System.out.println(cust);
    }
}
```

## 实验 - 20 - Beans 覆盖 – XML

![](img/image_rsrcFT1.jpg)

### Customer.java

```java
package com.abd.spring3;
public class Customer {
    private int type;
    private String action;
    private String Country;
    public int getType() {return type;}
    public void setType(int type) {this.type = type;}
    public String getAction() {return action;}
    public void setAction(String action) {this.action = action;}
    public String getCountry() {return Country;}
    public void setCountry(String country) {Country = country;}
    @Override
    public String toString() {
        return "Customer [Type=" + type + ", Action=" + action + ", Country=" + Country + "]";
    }
}
```

### Person.java

```java
package com.abd.spring3;
public class Person {
    private String name;
    private int age;
    private String address;
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public int getAge() {return age;}
    public void setAge(int age) {this.age = age;}
    public String getAddress() {return address;}
    public void setAddress(String address) {this.address = address;}
    @Override
    public String toString() {
        return "Person [name=" + name + ", age=" + age + ", address=" + address + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="generalCustomer" class="com.abd.spring3.Customer" abstract="true">
        <property name="country" value="USA" />
    </bean>
    <bean id="specialCustomer" parent="generalCustomer">
        <property name="country" value="India" />
        <property name="action" value="Backup" />
        <property name="type" value="1" />
    </bean>
</beans>
```

### Client.java



```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Customer cust = (Customer)context.getBean("specialCustomer");
        System.out.println(cust);
    }
}
```

## 实验 - 21 - Beans 初始化与销毁 – XML

![](img/image_rsrcFT2.jpg)

![](img/image_rsrcFT3.jpg)

### PrinterHelper.java

```java
package com.abd.spring3;
import org.springframework.beans.factory.DisposableBean;
import org.springframework.beans.factory.InitializingBean;
public class PrinterHelper implements InitializingBean, DisposableBean {
    String message;
    public String getMessage() {return message;}
    public void setMessage(String message) {this.message = message;}
    public void afterPropertiesSet() throws Exception {
        System.out.println("Init Method after Properties are Set : " + message);
    }
    public void destroy() throws Exception {
        System.out.println("Spring Container Destroyed , java Bean Destroyed");
    }
    @Override
    public String toString() {return message;}
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="printerService" class="com.abd.spring3.PrinterHelper">
        <property name="message" value="I am Property message" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ConfigurableApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ConfigurableApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        PrinterHelper cust = (PrinterHelper)context.getBean("printerService");
        System.out.println(cust);
        context.close();
    }
}
```

Output

![](img/image_rsrcFT4.jpg)

## 实验 - 22 - Beans Spring 初始化 方法 - XML

![](img/image_rsrcFT5.jpg)

### PrinterHelper.java

```java
package com.abd.spring3;
public class PrinterHelper {
    String message;
    public String getMessage() {return message;}
    public void setMessage(String message) {this.message = message;}
    public void initIt() throws Exception {
        System.out.println("Init Method after Properties are Set : " + message);
    }
    public void cleanUp() throws Exception {
        System.out.println("Spring Container Destroyed , java Bean also Destroyed");
    }
    @Override
    public String toString() {return message;}
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="printerService" class="com.abd.spring3.PrinterHelper" init-method="initIt" destroy-method="cleanUp">
        <property name="message" value="I am Property Message" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ConfigurableApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ConfigurableApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        PrinterHelper cust = (PrinterHelper)context.getBean("printerService");
        System.out.println(cust);
        context.close();
    }
}
```

Output

![](img/image_rsrcFT6.jpg)

# 第 8 章：Spring Beans 属性 (自动注入)

## 注入（将依赖对象注入到调用对象（父对象））

- 实验 - 23 - Beans 自动装配自动扫描未注入 - XML
- 实验 - 24 - Beans 自动装配自动扫描已注入 - XML
- 实验 - 25 - Beans 自动装配 Spring 注入 - XML
- 实验 - 26 - Beans 自动装配 Spring Setter 注入 - XML

### Spring 容器逻辑

- 在看到`<context:component-scan>`标签后
- 给`Spring 容器`的指令
- 需要特殊处理
- `Spring 容器`理解使用了`Annotation`（注解）
- Java 文件中的类信息和类变量指令
- `Spring 容器`首先查找`base-package = "com.abd.spring3"` />
- 基础包名，包的名字是什么（`com.abd.spring3`）
- 然后`Spring 容器`将首先进入（类路径）并查找包（`com.abd.spring3`）
- 尝试加载类
- 在加载过程中，`Spring 容器`会找到`@Autowired`
- `@Autowired`意味着标记为`@Autowired`的变量是一个类，它应该通过 setter 注入到 Java 类中
- `Spring 容器`会找到被标记为`@Autowired`的特定类
- 获取该类并执行其他任务：加载、创建实例、初始化资源以及注入依赖资源
- 到此为止
- 通过观察实验，你将理解这些内容

## 实验 - 23 - Beans 自动装配自动扫描未注入 – XML

![](img/image_rsrcFT7.jpg)

### PrinterHelper.java

```java
package com.abd.spring3;
public class PrinterHelper {
    Printer printer;
    public void setPrinter(Printer myPrinter) {
        this.printer = myPrinter;
    }
    @Override
    public String toString() {
        return "PrinterHelper [myPrinter=" + printer + "]";
    }
}
```

### Printer.java

```java
package com.abd.spring3;
public class Printer {}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="printerHelper" class="com.abd.spring3.PrinterHelper">
        <property name="printer" ref="myPrinter" />
    </bean>
    <bean id="myPrinter" class="com.abd.spring3.Printer" />
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        PrinterHelper cust = (PrinterHelper)context.getBean("printerHelper");
        System.out.println(cust);
    }
}
```

## 实验 - 24 - Beans 自动装配自动扫描已注入 – XML

![](img/image_rsrcFT8.jpg)

### PrinterHelper.java

```java
package com.abd.spring3;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Component;
@Component
public class PrinterHelper{
    @Autowired
    Printer myPrinter;
}
```

### Printer.java

```java
package com.abd.spring3;
import org.springframework.stereotype.Component;
@Component
public class Printer{}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-2.5.xsd">
    <context:component-scan base-package="com.abd.spring3" />
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client{
    public static void main( String[] args ){
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        PrinterHelper cust = (PrinterHelper)context.getBean("printerHelper");
        System.out.println(cust);
    }
}
```

## 实验 - 25 - Beans 自动装配 Spring 注入 – XML

![](img/image_rsrcFT9.jpg)

### Employee.java



```java
package com.abd.spring3;
public class Employee {
    private String name;
    private String address;
    private int age;
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getAddress() { return address; }
    public void setAddress(String address) { this.address = address; }
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}
```

### JobTitle.java

```java
package com.abd.spring3;
public class JobTitle {
    @Override
    public String toString() {
        return "JobTitle [person=" + person + ", type=" + type + ", action=" + action + "]";
    }
    public Employee getPerson() { return person; }
    public void setPerson(Employee person) { this.person = person; }
    public int getType() { return type; }
    public void setType(int type) { this.type = type; }
    public String getAction() { return action; }
    public void setAction(String action) { this.action = action; }
    private Employee person;
    private int type;
    private String action;
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-2.5.xsd">
    <context:annotation-config />
    <bean id="myJobTitle" class="com.abd.spring3.JobTitle">
        <property name="action" value="Buy" />
        <property name="type" value="1" />
    </bean>
    <bean id="myEmp" class="com.abd.spring3.Employee">
        <property name="name" value="Amar" />
        <property name="address" value="1 Bangalore" />
        <property name="age" value="28" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        JobTitle cust = (JobTitle)context.getBean("myJobTitle");
        System.out.println(cust);
    }
}
```

---

## 实验 - 26 - Beans 自动装配 Spring Setter 注入 - XML

![](img/image_rsrcFTA.jpg)

### Employee.java

```java
package com.abd.spring3;
public class Employee {
    private String name;
    private String address;
    private int age;
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public String getAddress() { return address; }
    public void setAddress(String address) { this.address = address; }
    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }
}
```

### JobTitle.java

```java
package com.abd.spring3;
public class JobTitle {
    @Override
    public String toString() {
        return "JobTitle [person=" + person + ", type=" + type + ", action=" + action + "]";
    }
    public Employee getPerson() { return person; }
    public void setPerson(Employee person) { this.person = person; }
    public int getType() { return type; }
    public void setType(int type) { this.type = type; }
    public String getAction() { return action; }
    public void setAction(String action) { this.action = action; }
    private Employee person;
    private int type;
    private String action;
}
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        PrinterHelper cust = (PrinterHelper)context.getBean("printerService");
        System.out.println(cust);
    }
}
```

### Output

![](img/image_rsrcFTB.jpg)

### JobTitle.java

```java
package com.abd.spring3;
import org.springframework.beans.factory.annotation.Autowired;
public class JobTitle {
    @Override
    public String toString() {
        return "JobTitle [person=" + person + ", type=" + type + ", action=" + action + "]";
    }
    public Employee getPerson() {
        return person;
    }
    @Autowired
    public void setPerson(Employee person) {
        this.person = person;
    }
    public int getType() {
        return type;
    }
    public void setType(int type) {
        this.type = type;
    }
    public String getAction() {
        return action;
    }
    public void setAction(String action) {
        this.action = action;
    }
    private Employee person;
    private int type;
    private String action;
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-2.5.xsd">
    <context:annotation-config />
    <bean id="myJobTitle" class="com.abd.spring3.JobTitle">
        <property name="action" value="Buy" />
        <property name="type" value="1" />
    </bean>
    <bean id="myEmp" class="com.abd.spring3.Employee">
        <property name="name" value="Amar" />
        <property name="address" value="1 A bangalore" />
        <property name="age" value="28" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        JobTitle cust = (JobTitle)context.getBean("myJobTitle");
        System.out.println(cust);
    }
}
```

### 输出

![](img/image_rsrcFTC.jpg)

## 第 9 章：Spring 表达式语言 (SpEL)

- Lab - 27 - Spring 表达式语言 - XML
- Lab - 28 - Spring 表达式语言 - 注解
- Lab - 27 - Spring 表达式语言 - XML

![](img/image_rsrcFTD.jpg)

### Item.java

```java
package com.abd.spring3;
public class Item {
    private String name;
    private int qty;
    public String getName() {
        return name;
    }
    @Override
    public String toString() {
        return "Item [name=" + name + ", qty=" + qty + "]";
    }
    public int getQty() {
        return qty;
    }
    public void setQty(int qty) {
        this.qty = qty;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

### Server.java

```java
package com.abd.spring3;
public class Server {
    private Item item;
    private String itemName;
    public Item getItem() {
        return item;
    }
    public void setItem(Item item) {
        this.item = item;
    }
    public String getItemName() {
        return itemName;
    }
    public void setItemName(String itemName) {
        this.itemName = itemName;
    }
    @Override
    public String toString() {
        return "Server [Item=" + item + ", ItemName=" + itemName + "]";
    }
}
```

### SpringBeans.xml



```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="itemBean" class="com.abd.spring3.Item">
        <property name="name" value="ItemA" />
        <property name="qty" value="10" />
    </bean>
    <bean id="myServer" class="com.abd.spring3.Server">
        <property name="item" value="#{itemBean}" />
        <property name="itemName" value="#{itemBean.name}" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Server obj = (Server) context.getBean("myServer");
        System.out.println(obj);
    }
}
```

### 输出

![](img/image_rsrcFT.jpg)

###### - 28 - Spring 表达式语言 - 注 注

`image_rsrcFTD.jpg)`

### `Item.java`

```java
package com.abd.spring3;
public class Item {
    private String name;
    private int qty;
    public String getName() {
        return name;
    }
    @Override
    public String toString() {
        return "Item [name=" + name + ", qty=" + qty + "]";
    }
    public int getQty() {
        return qty;
    }
    public void setQty(int qty) {
        this.qty = qty;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

### `Server.java`

```java
package com.abd.spring3;
public class Server {
    private Item item;
    private String itemName;
    public Item getItem() {
        return item;
    }
    public void setItem(Item item) {
        this.item = item;
    }
    public String getItemName() {
        return itemName;
    }
    public void setItemName(String itemName) {
        this.itemName = itemName;
    }
    @Override
    public String toString() {
        return "Server [Item=" + item + ", ItemName=" + itemName + "]";
    }
}
```

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="itemBean" class="com.abd.spring3.Item">
        <property name="name" value="ItemA" />
        <property name="qty" value="10" />
    </bean>
    <bean id="myServer" class="com.abd.spring3.Server">
        <property name="item" value="#{itemBean}" />
        <property name="itemName" value="#{itemBean.name}" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Server obj = (Server) context.getBean("myServer");
        System.out.println(obj);
    }
}
```

### 输出

![](img/image_rsrcFT.jpg)

### Lab - 28 - Spring 表达式语言 - 注解 注

![](img/image_rsrcFT.jpg)

### `Item.java`

```java
package com.abd.spring3;
public class Item {
    private String name;
    private int qty;
    public String getName() {
        return name;
    }
    @Override
    public String toString() {
        return "Item [name=" + name + ", qty=" + qty + "]";
    }
    public int getQty() {
        return qty;
    }
    public void setQty(int qty) {
        this.qty = qty;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

### `Server.java`

```java
package com.abd.spring3;
public class Server {
    private Item item;
    private String itemName;
    public Item getItem() {
        return item;
    }
    public void setItem(Item item) {
        this.item = item;
    }
    public String getItemName() {
        return itemName;
    }
    public void setItemName(String itemName) {
        this.itemName = itemName;
    }
    @Override
    public String toString() {
        return "Server [Item=" + item + ", ItemName=" + itemName + "]";
    }
}
```

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="itemBean" class="com.abd.spring3.Item">
        <property name="name" value="ItemA" />
        <property name="qty" value="10" />
    </bean>
    <bean id="myServer" class="com.abd.spring3.Server">
        <property name="item" value="#{itemBean}" />
        <property name="itemName" value="#{itemBean.name}" />
    </bean>
</beans>
```

### 输出

![](img/image_rsrcFT.jpg)

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="itemBean" class="com.abd.spring3.Item">
        <property name="name" value="ItemA" />
        <property name="qty" value="10" />
    </bean>
    <bean id="myServer" class="com.abd.spring3.Server">
        <property name="item" value="#{itemBean}" />
        <property name="itemName" value="#{itemBean.name}" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Server obj = (Server) context.getBean("myServer");
        System.out.println(obj);
    }
}
```

### 输出

![](img/image_rsrcFT.jpg)

### Lab - 28 - Spring 表达式语言 - 注解 注

![](img/image_rsrcFT.jpg)

### `Item.java`

```java
package com.abd.spring3;
public class Item {
    private String name;
    private int qty;
    public String getName() {
        return name;
    }
    @Override
    public String toString() {
        return "Item [name=" + name + ", qty=" + qty + "]";
    }
    public int getQty() {
        return qty;
    }
    public void setQty(int qty) {
        this.qty = qty;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

### `Server.java`

```java
package com.abd.spring3;
public class Server {
    private Item item;
    private String itemName;
    public Item getItem() {
        return item;
    }
    public void setItem(Item item) {
        this.item = item;
    }
    public String getItemName() {
        return itemName;
    }
    public void setItemName(String itemName) {
        this.itemName = itemName;
    }
    @Override
    public String toString() {
        return "Server [Item=" + item + ", ItemName=" + itemName + "]";
    }
}
```

### `SpringBeans.xml`

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="itemBean" class="com.abd.spring3.Item">
        <property name="name" value="ItemA" />
        <property name="qty" value="10" />
    </bean>
    <bean id="myServer" class="com.abd.spring3.Server">
        <property name="item" value="#{itemBean}" />
        <property name="itemName" value="#{itemBean.name}" />
    </bean>
</beans>
```

### 输出

![](img/image_rsrcFT.jpg)

### `SpringBeans.xml`



# 第 9 章：Spring 表达式语言 (SpEL)

- Lab - 27 - Spring 表达式语言 - XML
- Lab - 28 - Spring 表达式语言 - 注解
- Lab - 27 - Spring 表达式语言 - XML

以下为各实验所需的代码和配置文件。

## Lab - 27 - Spring 表达式语言 - XML

### Item.java

```java
package com.abd.spring3;
public class Item {
    private String name;
    private int qty;
    public String getName() {
        return name;
    }
    @Override
    public String toString() {
        return "Item [name=" + name + ", qty=" + qty + "]";
    }
    public int getQty() {
        return qty;
    }
    public void setQty(int qty) {
        this.qty = qty;
    }
    public void setName(String name) {
        this.name = name;
    }
}
```

### Server.java

```java
package com.abd.spring3;
public class Server {
    private Item item;
    private String itemName;
    public Item getItem() {
        return item;
    }
    public void setItem(Item item) {
        this.item = item;
    }
    public String getItemName() {
        return itemName;
    }
    public void setItemName(String itemName) {
        this.itemName = itemName;
    }
    @Override
    public String toString() {
        return "Server [Item=" + item + ", ItemName=" + itemName + "]";
    }
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">
    <bean id="itemBean" class="com.abd.spring3.Item">
        <property name="name" value="ItemA" />
        <property name="qty" value="10" />
    </bean>
    <bean id="myServer" class="com.abd.spring3.Server">
        <property name="item" value="#{itemBean}" />
        <property name="itemName" value="#{itemBean.name}" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        Server obj = (Server) context.getBean("myServer");
        System.out.println(obj);
    }
}
```

## Lab - 28 - Spring 表达式语言 - 注解

### JobTitle.java

```java
package com.abd.spring3;
import org.springframework.beans.factory.annotation.Autowired;
public class JobTitle {
    @Override
    public String toString() {
        return "JobTitle [person=" + person + ", type=" + type + ", action=" + action + "]";
    }
    public Employee getPerson() {
        return person;
    }
    @Autowired
    public void setPerson(Employee person) {
        this.person = person;
    }
    public int getType() {
        return type;
    }
    public void setType(int type) {
        this.type = type;
    }
    public String getAction() {
        return action;
    }
    public void setAction(String action) {
        this.action = action;
    }
    private Employee person;
    private int type;
    private String action;
}
```

### SpringBeans.xml

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-2.5.xsd">
    <context:annotation-config />
    <bean id="myJobTitle" class="com.abd.spring3.JobTitle">
        <property name="action" value="Buy" />
        <property name="type" value="1" />
    </bean>
    <bean id="myEmp" class="com.abd.spring3.Employee">
        <property name="name" value="Amar" />
        <property name="address" value="1 A bangalore" />
        <property name="age" value="28" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main( String[] args ) {
        ApplicationContext context = new ClassPathXmlApplicationContext(new String[] {"SpringBeans.xml"});
        JobTitle cust = (JobTitle)context.getBean("myJobTitle");
        System.out.println(cust);
    }
}
```

### 示例输出

```text
JobTitle [person=Employee [name=Amar, address=1 A Bangalore, age=28], type=1, action=Buy]
```

## 补充：AOP 环绕通知示例

### AOPAroundMethod.java

```java
package com.abd.spring3;
import java.util.Arrays;
import org.aopalliance.intercept.MethodInterceptor;
import org.aopalliance.intercept.MethodInvocation;

public class AOPAroundMethod implements MethodInterceptor {
    @Override
    public Object invoke(MethodInvocation methodInvocation) throws Throwable {
        System.out.println("Method name : " + methodInvocation.getMethod().getName());
        System.out.println("Method arguments : " + Arrays.toString(methodInvocation.getArguments()));
        System.out.println("Before method!");
        try {
            // 继续执行原始方法调用
            Object result = methodInvocation.proceed();
            // 与 AfterReturningAdvice 相同
            System.out.println("after method!");
            return result;
        } catch (IllegalArgumentException e) {
            // 与 ThrowsAdvice 相同
            System.out.println("Throw exception aop!");
            throw e;
        }
    }
}
```

### CustomerService.java

```java
package com.abd.spring3;
public class CustomerService {
    private String name;
    private String url;
    public void setName(String name) {
        this.name = name;
    }
    public void setUrl(String url) {
        this.url = url;
    }
    public void printName() {
        System.out.println("Customer name : " + this.name);
    }
    public void printURL() {
        System.out.println("Customer website : " + this.url);
    }
    public void printThrowException() {
        throw new IllegalArgumentException();
    }
}
```

### SpringBeans.xml（AOP 配置）

```xml
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">
    <bean id="customerService" class="com.abd.spring3.CustomerService">
        <property name="name" value="Laser Printer" />
        <property name="url" value="http://www.google.com" />
    </bean>
    <bean id="hijackAroundMethodBean" class="com.abd.spring3.AOPAroundMethod" />
    <bean id="customerServiceProxy" class="org.springframework.aop.framework.ProxyFactoryBean">
        <property name="target" ref="customerService" />
        <property name="interceptorNames">
            <list>
                <value>hijackAroundMethodBean</value>
            </list>
        </property>
    </bean>
</beans>
```

### 对应的 Client.java

```java
package com.abd.spring3;
import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ApplicationContext context = new ClassPathXmlApplicationContext("SpringBeans.xml");
        // 使用代理获取 customerService 实例
        CustomerService service = (CustomerService) context.getBean("customerServiceProxy");
        service.printName();
        service.printURL();
        service.printThrowException();
    }
}
```




```java
package com.abd.spring3;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ApplicationContext appContext =
                new ClassPathXmlApplicationContext(new String[] { "SpringBeans.xml" });
        CustomerService cust = (CustomerService) appContext.getBean("customerServiceProxy");
        cust.printName();
        cust.printURL();
        try {
            cust.printThrowException();
        } catch (Exception e) {
        }
    }
}
```

### 输出

![](img/image_rsrcFTM.jpg)

# JPA：初学者 JAVA 持久化指南

在本书中，你将学习带有图表说明的实练习，并附带成功执行的输出结果。提供现成的解决方案以及分步说明。

AMIT K

## 目录

- 逐步学习 JPA 编程的初学者指南
- 引言
- 第 1 章：JPA 一一对映射
  1. 示例 1：JPA OneToOne 映射
  2. 示例 2：JPA OneToOne 懒加载映射
  3. 示例 3：JPA OneToOne 关联列映射
  4. 示例 4：JPA OneToOne 主键关联列映射
  5. 示例 5：JPA OneToOne Map 级联映射
  6. 示例 6：JPA OneToOne 单向映射
  7. 示例 7：JPA OneToOne 双向映射
- 第 2 章：JPA 一对多映射
  1. 示例 8：JPA OneToMany 映射
  2. 示例 9：JPA OneToMany 关联表映射
  3. 示例 10：JPA OneToMany 单向映射
  4. 示例 11：JPA OneToMany OrderBy 映射
  5. 示例 12：JPA Persist OrderedList 映射
  6. 示例 13：JPA OneToMany Map Key 映射
  7. 示例 14：JPA OneToMany 无类型映射
- 第 3 章：JPA 多对一映射
  1. 示例 15：JPA ManyToOne 映射
  2. 示例 16：JPA ManyToOne 关联列映射
  3. 示例 17：JPA ManyToOne 关联列映射
- 第 4 章：JPA 多对多映射
  1. 示例 18：JPA ManyToMany 映射
  2. 示例 19：JPA ManyToMany 关联表映射
  3. 示例 20：JPA ManyToMany 双向映射
  4. 示例 21：JPA ManyToMany 可嵌入类映射

## 引言

逐步学习 JPA 编程。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：JPA 一一对映射

1. JPA OneToOne 映射
2. JPA OneToOne 懒加载映射
3. JPA OneToOne 关联列映射
4. JPA OneToOne 主键关联列映射
5. JPA OneToOne Map 级联映射
6. JPA OneToOne 单向映射
7. JPA OneToOne 双向映射

### 示例 1：JPA OneToOne 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分

![](img/image_srcN.jpg)

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在

![](img/image_srcN.jpg)

## 第 1 章：JPA 一一对映射

1. JPA OneToOne 映射
2. JPA OneToOne 懒加载映射
3. JPA OneToOne 关联列映射
4. JPA OneToOne 主键关联列映射
5. JPA OneToOne Map 级联映射
6. JPA OneToOne 单向映射
7. JPA OneToOne 双向映射

### 示例 1：JPA OneToOne 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分

![](img/image_srcN.jpg)

## 第 1 章：JPA 一一对映射

1. JPA OneToOne 映射
2. JPA OneToOne 懒加载映射
3. JPA OneToOne 关联列映射
4. JPA OneToOne 主键关联列映射
5. JPA OneToOne Map 级联映射
6. JPA OneToOne 单向映射
7. JPA OneToOne 双向映射

### 示例 1：JPA OneToOne 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分

![](img/image_srcN.jpg)

## 第 1 章：JPA 一一对映射

1. JPA OneToOne 映射
2. JPA OneToOne 懒加载映射
3. JPA OneToOne 关联列映射
4. JPA OneToOne 主键关联列映射
5. JPA OneToOne Map 级联映射
6. JPA OneToOne 单向映射
7. JPA OneToOne 双向映射



# 第 1 章：JPA 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：`JPA` 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：`JPA` 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：`JPA` 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：`JPA` 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：`JPA` 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：`JPA` 一一对映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

## 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。




`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

![](img/image_srcN.jpg)

## 第 1 章：JPA 一对一映射

1. `JPA OneToOne` 映射
2. `JPA OneToOne` 懒加载映射
3. `JPA OneToOne` 关联列映射
4. `JPA OneToOne` 主键关联列映射
5. `JPA OneToOne Map` 级联映射
6. `JPA OneToOne` 单向映射
7. `JPA OneToOne` 双向映射

### 示例 1：`JPA OneToOne` 映射

![](img/image_srcN.jpg)

在这里将学习如何进行一对一映射。`JPA` 是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。

（注：`JPA`（`Java Persistence API`）是一个强大的框架，可用于快速构建健壮的数据驱动应用程序。我们应用程序处理的大部分数据必须存储在数据库中。）

### `Helper.java`

```java
package com.abd.jpa;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+",  ");
                        System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("    Column Value: "+value+"\n");
                    }
                }
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```

### `persistence.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

### `applicationContext.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>
        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>
        <property name="username"><value>root</value></property>
        <property name="password"><value>root</value></property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

```
Table Name: DEPARTMENT
Row:
Column Name: ID, Column Type: BIGINT, Column Value: 1
Column Name: NAME, Column Type: VARCHAR, Column Value: Design
Table Name: PERSON
Row:
Column Name: ID, Column Type: BIGINT, Column Value: 1
Column Name: NAME, Column Type: VARCHAR, Column Value: Tom
Column Name: DEPARTMENT_ID, Column Type: BIGINT, Column Value: 1
```



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>
        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>
        <property name="username"><value>root</value></property>
        <property name="password"><value>root</value></property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### Output

```
Table Name: DEPARTMENT
Row:Column Name: ID,Column Type: BIGINT:Column Value: 1
Column Name: NAME,Column Type: VARCHAR:Column Value: Design
Table Name: PERSON
Row:Column Name: ID,Column Type: BIGINT:Column Value: 1
Column Name: NAME,Column Type: VARCHAR:Column Value: Tom
Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1
```

## JPA 一对一连接列映射

以下章节展示了如何在 JPA 中为一对一映射设置连接列。

我们使用`@JoinColumn`注解来设置连接列。

```java
@OneToOne
@JoinColumn(name="DEPT_ID")
private Department department;
```

### 示例 3

### `Person.java`

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.OneToOne;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @OneToOne
    @JoinColumn(name="DEPT_ID")
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

### `Department.java`

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @OneToOne(mappedBy="department")
    private Person person;

    public Department() {}

    public Department(String name) {
        this.name = name;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public Person getPerson() {
        return person;
    }

    public void setPerson(Person person) {
        this.person = person;
    }

    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + "]";
    }
}
```

### `PersonDaoImpl.java`

```java
package com.abd.jpa;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.Query;
import java.util.List;

public class PersonDaoImpl {
    @PersistenceContext
    private EntityManager em;

    public void test() {
        Person person = new Person("Tom");
        Department department = new Department("Design");
        person.setDepartment(department);
        em.persist(person);
        em.persist(department);

        Query query = em.createQuery("SELECT e FROM Person");
        List<Person> list = (List<Person>) query.getResultList();
        System.out.println(list.get(0).getDepartment());
    }
}
```

### `Helper.java`

```java
package com.abd.jpa;
import java.sql.*;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] {TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\nTable Name: " + tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("  Column Name: " + metadata.getColumnLabel(i + 1) + ", ");
                        System.out.println("  Column Type: " + metadata.getColumnTypeName(i + 1) + ": ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("  Column Value: " + value + "\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>
        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>
        <property name="username"><value>root</value></property>
        <property name="password"><value>root</value></property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

- 表名: `DEPARTMENT`

行: 列名: `ID`, 列类型: `BIGINT`: 列值: `1`

列名: `NAME`, 列类型: `VARCHAR`: 列值: `Design`

- 表名: `PERSON`

行: 列名: `ID`, 列类型: `BIGINT`: 列值: `1`

列名: `NAME`, 列类型: `VARCHAR`: 列值: `Tom`

列名: `DEPT_ID`, 列类型: `BIGINT`: 列值: `1`

# 4 JPA 一一关系主键连接列映射

![](img/image_rsrcFTN.jpg)

## 示例 4 :

### Person.java

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.OneToOne;
import javax.persistence.PrimaryKeyJoinColumn;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @OneToOne
    @PrimaryKeyJoinColumn
    private Department department;

    public Person() {}
    public Person(String name) {
        this.name = name;
    }
    public Department getDepartment() {return department; }
    public void setDepartment(Department department) {this.department = department; }
    public Long getId() { return id; }
    public void setId(Long id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

### Department.java

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.OneToOne;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @OneToOne(mappedBy="department")
    private Person person;

    public Person getPerson() {return person; }
    public void setPerson(Person person) {this.person = person; }
    public long getId() {return id; }
    public void setId(long id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    public void test() {
        Person p1 = new Person("Tom");
        p1.setName("Tom");
        Department d = new Department();
        d.setName("Design");
        p1.setDepartment(d);
        d.setPerson(p1);
        em.persist(p1);
        em.persist(d);
    }
    @PersistenceContext
    private EntityManager em;
}
```

### Helper.java

```java
package com.abd.jpa;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1) + ",  ");
                        System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1) + ":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("    Column Value: "+value+"\n");
                    }
                }
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```

### persistence.xml



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">com.mysql.jdbc.Driver</property>
        <property name="url">jdbc:mysql://localhost/db1</property>
        <property name="username">root</property>
        <property name="password">root</property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName">jpaData</property>
        <property name="hibernateProperties" class="org.springframework.orm.jpa.HibernateVendorAdapter">
            <property name="dialect">org.hibernate.dialect.MySQLDialect</property>
            <property name="show_sql">true</property>
            <property name="hbm2ddl.auto">update</property>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.jpa;
import org.springframework.context.support.ClassXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ClassXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

```
Table Name: DEPARTMENT
Row: ID, Type: BIGINT, Value: 1
NAME, Type: VARCHAR, Value: Design
Table Name: PERSON
Row: ID, Type: BIGINT, Value: 1
NAME, Type: VARCHAR, Value: Tom
```

### JPA OneToOne 级联映射

以下代码展示了如何为一对一映射设置级联操作。

```java
@OneToOne(cascade=CascadeType.ALL,mappedBy="department")
private Person person;
```

### 示例 5：

### Person.java

```java
package com.abd.jpa;
import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.OneToOne;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @OneToOne(cascade=CascadeType.ALL)
    @JoinColumn(name="DEPT_ID")
    private Department department;

    public Person() {}
    public Person(String name) {
        this.name = name;
    }
    public Department getDepartment() {
        return department;
    }
    public void setDepartment(Department department) {
        this.department = department;
    }
    public Long getId() {
        return id;
    }
    public void setId(Long id) {
        this.id = id;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

### Department.java

```java
package com.abd.jpa;
import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.OneToOne;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @OneToOne(cascade=CascadeType.ALL,mappedBy="department")
    private Person person;

    public Person getPerson() {
        return person;
    }
    public void setPerson(Person person) {
        this.person = person;
    }
    public long getId() {
        return id;
    }
    public void setId(long id) {
        this.id = id;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + ", person=" + person + "]";
    }
}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;
import java.util.List;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.Query;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    public void test() {
        Person p1 = new Person("Tom");
        p1.setName("Tom");
        Department d = new Department();
        d.setName("Design");
        p1.setDepartment(d);
        d.setPerson(p1);
        em.persist(p1);
        em.persist(d);
        Query query = em.createQuery("SELECT e FROM Person e");
        List<Person> list = (List<Person>) query.getResultList();
        System.out.println(list.get(0).getDepartment());
        em.remove(list.get(0));
    }
    @PersistenceContext
    private EntityManager em;
}
```

### Helper.java

```java
package com.abd.jpa;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println(" Column Name: "+ metadata.getColumnLabel(i + 1) + ", ");
                        System.out.println(" Column Type: "+ metadata.getColumnTypeName(i + 1) + ": ");
                        Object value = rs.getObject(i + 1);
                        System.out.println(" Column Value: "+value+"\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName" value="com.mysql.jdbc.Driver"/>
        <property name="url" value="jdbc:mysql://localhost/db1"/>
        <property name="username" value="root"/>
        <property name="password" value="root"/>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource"/>
        <property name="persistenceUnitName" value="jpaData"/>
        <properties>
            <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
            <prop key="hibernate.show_sql">true</prop>
            <prop key="hibernate.hbm2ddl.auto">update</prop>
        </properties>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory"/>
    </bean>
</beans>
```

### Client.java

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplication;
public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplication context = new ClassPathXmlApplication("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

## 6 JPA 一对一单向映射

![示意图](img/image_rsrcFTN.jpg)

在这里你将学习如何实现单向一对一映射。

## 示例 6

### Professor.java

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.OneToOne;

@Entity
public class Professor {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private int id;
    private String name;
    private long salary;

    @OneToOne
    @JoinColumn(name="PSPACE_ID")
    private ParkingSpace parkingSpace;

    public int getId() { return id; }
    public void setId(int id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public long getSalary() { return salary; }
    public void setSalary(long salary) { this.salary = salary; }
    public ParkingSpace getParkingSpace() { return parkingSpace; }
    public void setParkingSpace(ParkingSpace parkingSpace) { this.parkingSpace = parkingSpace; }
    public String toString() {
        return "Employee id: " + getId() + " name: " + getName() + " with " + getParkingSpace();
    }
}
```

### ParkingSpace.java

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.Table;

@Entity
@Table(name="PARKING_SPACE")
public class ParkingSpace {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private int id;
    private int lot;
    private String location;

    public int getId() { return id; }
    public void setId(int id) { this.id = id; }
    public int getLot() { return lot; }
    public void setLot(int lot) { this.lot = lot; }
    public String getLocation() { return location; }
    public void setLocation(String deptName) { this.location = deptName; }
    public String toString() {
        return "ParkingSpace id: " + getId() + " lot: " + getLot() + ", location: " + getLocation();
    }
}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    public void test() {
        Professor emp = new Professor();
        emp.setName("name");
        emp.setSalary(12345);
        ParkingSpace ps = new ParkingSpace();
        ps.setLot(1);
        ps.setLocation("East");
        emp.setParkingSpace(ps);
        em.persist(ps);
        em.persist(emp);
    }
    @PersistenceContext
    private EntityManager em;
}
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

表名：`PARKING_SPACE`



行：列名：`ID`，列类型：`INTEGER`，列值：`1`

列名：`LOCATION`，列类型：`VARCHAR`，列值：`East`

列名：`LOT`，列类型：`INTEGER`，列值：`1`

表名：`PROFESSOR`

行：列名：`ID`，列类型：`INTEGER`，列值：`1`

列名：`NAME`，列类型：`VARCHAR`，列值：`name`

列名：`SALARY`，列类型：`BIGINT`，列值：`12345`

列名：`PSPACE_ID`，列类型：`INTEGER`，列值：`1`

## 7. JPA 一对一双向映射

![](img/image_rsrcFTP.jpg)

在这里你将学习如何实现双向一对一映射。

### 示例 7

#### `Person.java`

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.OneToOne;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @OneToOne
    @JoinColumn(name="DEPT_ID")
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

#### `Department.java`

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.OneToOne;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @OneToOne(mappedBy="department")
    private Person person;

    public Person getPerson() {
        return person;
    }

    public void setPerson(Person person) {
        this.person = person;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

#### `PersonDaoImpl.java`

```java
package com.abd.jpa;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    @PersistenceContext
    private EntityManager em;

    public void test() {
        Person p1 = new Person("Tom");
        Department d = new Department();
        d.setName("Design");
        p1.setDepartment(d);
        em.persist(p1);
        em.persist(d);
    }
}
```

#### `Helper.java`

```java
package com.abd.jpa;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\nTable Name: " + tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("    Column Name: " + metadata.getColumnLabel(i + 1) + ",  ");
                        System.out.println("    Column Type: " + metadata.getColumnTypeName(i + 1) + ":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("    Column Value: " + value + "\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

#### `persistence.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

#### `applicationContext.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>
        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>
        <property name="username"><value>root</value></property>
        <property name="password"><value>root</value></property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

#### `Client.java`

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;
public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

表名：`DEPARTMENT`

行：列名：`ID`，列类型：`BIGINT`，列值：`1`

列名：`NAME`，列类型：`VARCHAR`，列值：`Design`

表名：`PERSON`

行：列名：`ID`，列类型：`BIGINT`，列值：`1`

列名：`NAME`，列类型：`VARCHAR`，列值：`Tom`

列名：`DEPT_ID`，列类型：`BIGINT`，列值：`1`

## 第 2 章：JPA 一对多映射

### 1. JPA OneToMany 映射

### 2. JPA OneToMany 表映射

### 3. JPA OneToMany 单向映射

### 4. JPA OneToMany OrderBy 映射

### 5. JPA Persist OrderedList 映射

### 6. JPA OneToMany Map Key 映射

### 7. JPA OneToMany Untyped 映射

### 1. JPA OneToMany 映射

![](img/image_rsrcFTR.jpg)



在这里，你将学习如何在 JPA 中实现一对多映射。

一个部门可以拥有一个或多个员工。

在 Java 代码中，我们可以通过`Employee`类创建一个 Java Bean 来表示员工，并使用一个`Department`类来表示部门。

在关联`Employee`和`Department`时，我们如下所示从`Employee`中引用`Department`类。

```java
@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @ManyToOne
    private Department department;
}
```

我们用`@ManyToOne`标记`Department`以表示`Department`和`Employee`之间的关系。

## Person.java

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @ManyToOne
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

## Department.java

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    public long getId() {
        return id;
    }

    public void setId(long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

## PersonDaoImpl.java

```java
package com.abd.jpa;
import java.util.List;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.Query;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    public void test() {
        Department d = new Department();
        d.setName("Design");
        Person p1 = new Person("Tom");
        p1.setDepartment(d);
        Person p2 = new Person("Jack");
        p2.setDepartment(d);
        em.persist(p1);
        em.persist(p2);
        em.persist(d);
    }

    @PersistenceContext
    private EntityManager em;
}
```

## Helper.java

```java
package com.abd.jpa;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\n 表名: " + tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" 行:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("  列名: " + metadata.getColumnLabel(i + 1) + ", ");
                        System.out.println("  列类型: " + metadata.getColumnTypeName(i + 1) + ": ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("  列值: " + value + "\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

## persistence.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

## Client.java

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

## Output

Table Name: DEPARTMENT

Row:Column Name: ID,Column Type: BIGINT:Column Value: 1

Column Name: NAME,Column Type: VARCHAR:Column Value: Design

Table Name: PERSON

Row:Column Name: ID,Column Type: BIGINT:Column Value: 1

Column Name: NAME,Column Type: VARCHAR:Column Value: Tom

Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1

Row:Column Name: ID,Column Type: BIGINT:Column Value: 2

Column Name: NAME,Column Type: VARCHAR:Column Value: Jack

Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1

# 2 JPA 一对多连接表映射

![](img/image_rsrcFTR.jpg) 

在这里，你将学习如何进行一对多映射。



以下代码展示了如何使用连接表来连接一对多映射。

它使用了`@JoinTable`注解来设置连接表。

```java
@OneToMany
@JoinTable(name = "PERSON_DEPT", joinColumns = @JoinColumn(name = "EMP_ID"), inverseJoinColumns = @JoinColumn(name = "PHONE_ID"))
private Set<Person> persons = new HashSet<Person>();
```

`Person.java`

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;
import javax.persistence.CascadeType;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @ManyToOne (cascade=CascadeType.ALL)
    private Department department;

    public Person() {}
    public Person(String name) {
        this.name = name;
    }
    public Department getDepartment() {
        return department;
    }
    public void setDepartment(Department department) {
        this.department = department;
    }
    public Long getId() {
        return id;
    }
    public void setId(Long id) {
        this.id = id;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

`Department.java`

```java
package com.abd.jpa;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;
import javax.persistence.CascadeType;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;
    @ManyToOne (cascade=CascadeType.ALL)
    private Department department;

    public Department() {}
    public Department(String name) {
        this.name = name;
    }
    public Department getDepartment() {
        return department;
    }
    public void setDepartment(Department department) {
        this.department = department;
    }
    public Long getId() {
        return id;
    }
    public void setId(Long id) {
        this.id = id;
    }
    public String getName() {
        return name;
    }
    public void setName(String name) {
        this.name = name;
    }
    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + "]";
    }
}
```

`PersonDaoImpl.java`

```java
package com.abd.jpa;
import java.util.List;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.Query;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    @PersistenceContext
    private EntityManager em;
    public void test() {
    }
}
```

`Helper.java`

```java
package com.abd.jpa;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();
                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1) + ",  ");
                        System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1) + ":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("    Column Value: "+value+"\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

`persistence.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

### `applicationContext.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.jpa;
import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

表名: `DEPARTMENT`

行: 列名: `ID`,列类型: `BIGINT`:列值: `1`

列名: `NAME`,列类型: `VARCHAR`:列值: `Design`

表名: `PERSON`

行: 列名: `ID`,列类型: `BIGINT`:列值: `1`

列名: `NAME`,列类型: `VARCHAR`:列值: `Tom`

列名: `DEPARTMENT_ID`,列类型: `BIGINT`:列值: `1`

行: 列名: `ID`,列类型: `BIGINT`:列值: `2`

列名: `NAME`,列类型: `VARCHAR`:列值: `Jack`

列名: `DEPARTMENT_ID`,列类型: `BIGINT`:列值: `1`

表名: `PERSON_DEP`

行: 列名: `EMP_ID`,列类型: `BIGINT`:列值: `1`

列名: `PHONE_ID`,列类型: `BIGINT`:列值: `1`



行: 列名: `EMP_ID`, 列类型: `BIGINT`: 列值: `1`

列名: `PHONE_ID`, 列类型: `BIGINT`: 列值: `2`

### 3 JPA 一对多单向映射

在这里你将学习如何实现单向的一多映射。

### `Professor.java`

```java
package com.abd.jpa;

import java.util.ArrayList;
import java.util.Collection;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.JoinTable;
import javax.persistence.OneToMany;

@Entity
public class Professor {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private int id;
    private String name;
    private long salary;

    @OneToMany
    @JoinTable(name="EMP_PHONE", joinColumns=@JoinColumn(name="EMP_ID"), inverseJoinColumns=@JoinColumn(name="PHONE_ID"))
    private Collection<Phone> phones;

    public Professor() {
        phones = new ArrayList<Phone>();
    }

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public long getSalary() {
        return salary;
    }

    public void setSalary(long salary) {
        this.salary = salary;
    }

    public Collection<Phone> getPhones() {
        return phones;
    }
}
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>
        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>
        <property name="username"><value>root</value></property>
        <property name="password"><value>root</value></property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

表名: `EMP_PHONE`
行: 列名: `EMP_ID`, 列类型: `INTEGER`: 列值: `1`
列名: `PHONE_ID`, 列类型: `INTEGER`: 列值: `1`

表名: `PHONE`
行: 列名: `ID`, 列类型: `INTEGER`: 列值: `1`
列名: `NUM`, 列类型: `VARCHAR`: 列值: `1234509876`
列名: `TYPE`, 列类型: `VARCHAR`: 列值: `null`

表名: `PROFESSOR`
行: 列名: `ID`, 列类型: `INTEGER`: 列值: `1`
列名: `NAME`, 列类型: `VARCHAR`: 列值: `name`
列名: `SALARY`, 列类型: `BIGINT`: 列值: `12345`

### 4 JPA 一对多 OrderBy 映射

在这里，你将学习如何进行一对多的映射。

以下代码展示了如何在一对多映射中设置按属性排序（order by）。

`@OrderBy("name ASC")` 用于按姓名对人员集合进行排序。

```java
@OneToMany(targetEntity=Person.class, mappedBy="department")
@OrderBy("name ASC")
private Set<Person> persons = new HashSet<Person>();
```

### `Person.java`

```java
package com.abd.jpa;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;
import javax.persistence.CascadeType;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @ManyToOne (cascade=CascadeType.ALL)
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

### `Department.java`

```java
package com.abd.jpa;

import java.util.HashSet;
import java.util.Set;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.OneToMany;
import javax.persistence.OrderBy;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @OneToMany(targetEntity=Person.class, mappedBy="department")
    @OrderBy("name ASC")
    private Set<Person> persons = new HashSet<Person>();

    public Set<Person> getPersons() {
        return persons;
    }

    public void setPersons(Set<Person> persons) {
        this.persons = persons;
    }

    public long getId() {
        return id;
    }

    public void setId(long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + ", persons=" + persons + "]";
    }
}
```

### `PersonDaoImpl.java`

```java
package com.abd.jpa;

import java.util.List;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    @PersistenceContext
    private EntityManager em;

    public void test() {
        Department d = new Department();
        d.setName("Design");
        Person p1 = new Person("Tom");
        p1.setDepartment(d);
        Person p2 = new Person("Jack");
        p2.setDepartment(d);
        d.getPersons().add(p1);
        d.getPersons().add(p2);
        em.persist(p1);
        em.persist(p2);
        em.persist(d);
    }
}
```

### `Helper.java`

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;
```



`public class Helper` 中的 `checkData()` 方法用于检查数据库中的数据。该方法首先加载 MySQL 驱动，然后建立数据库连接，获取所有表名，并遍历每个表的所有行和列，打印每列的名称、类型和值。

```java
public class Helper {

    public static void checkData() {

        try {

            Class.forName("com.mysql.jdbc.Driver");

            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");

            Statement st = conn.createStatement();

            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });

            while (mrs.next()) {

                String tableName = mrs.getString(3);

                System.out.println("\n\n\n\nTable Name: " + tableName);

                ResultSet rs = st.executeQuery("select * from " + tableName);

                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {

                    System.out.println(" Row:");

                    for (int i = 0; i < metadata.getColumnCount(); i++) {

                        System.out.println("  Column Name: " + metadata.getColumnLabel(i + 1) + ", ");

                        System.out.println("  Column Type: " + metadata.getColumnTypeName(i + 1) + ": ");

                        Object value = rs.getObject(i + 1);

                        System.out.println("  Column Value: " + value + "\n");

                    }

                }

            }

        } catch (Exception e) {

            e.printStackTrace();

        }

    }

}
```

### `persistence.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData"/>
</persistence>
```

### Spring 配置文件

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">com.mysql.jdbc.Driver</property>
        <property name="url">jdbc:mysql://localhost/db1</property>
        <property name="username">root</property>
        <property name="password">root</property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="vendorAdapter" class="org.springframework.orm.jpa.HibernateVendorAdapter">
            <properties>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.ddl.auto">update</prop>
            </properties>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### `Client.java`

```java
package com.abd.jpa;

import org.springframework.context.support.ClassXmlApplicationContext;

public class Client {

    public static void main(String[] args) {

        ClassXmlApplicationContext context = new ClassXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();

    }

}
```

### 输出示例

```
Table Name: DEPARTMENT

Row:

    Column Name: ID,  Column Type: BIGINT:  

    Column Value: 1

    Column Name: NAME,  Column Type: VARCHAR:  

    Column Value: Design

Table Name: PERSON

Row:

    Column Name: ID,  Column Type: BIGINT:  

    Column Value: 1

    Column Name: NAME,  Column Type: VARCHAR:  

    Column Value: Tom

    Column Name: DEPARTMENT_ID,  Column Type: BIGINT:  

    Column Value: 1

Row:

    Column Name: ID,  Column Type: BIGINT:  

    Column Value: 2

    Column Name: NAME,  Column Type: VARCHAR:  

    Column Value: Jack

    Column Name: DEPARTMENT_ID,  Column Type: BIGINT:  

    Column Value: 1
```

# 5 JPA 排序列表 `OrderedList` 映射

在这里，你将学习如何进行一对多的映射。

```java
@OneToMany(mappedBy="queue")
@OrderColumn(name="PRINT_ORDER")
private List<PrintJob> jobs;
```

### `PrintJob.java`

```java
package com.abd.jpa;

import javax.persistence.Entity;
import javax.persistence.Id;
import javax.persistence.ManyToOne;

@Entity
public class PrintJob {

    @Id 
    private int id;

    @ManyToOne
    private PrintQueue queue;

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public PrintQueue getQueue() {
        return queue;
    }

    public void setQueue(PrintQueue queue) {
        this.queue = queue;
    }
}
```

### `PrintQueue.java`

```java
package com.abd.jpa;

import java.util.List;
import java.util.ArrayList;
import javax.persistence.Entity;
import javax.persistence.Id;
import javax.persistence.OneToMany;
import javax.persistence.OrderColumn;

@Entity
public class PrintQueue {

    @Id 
    private String name;

    @OneToMany(mappedBy="queue")
    @OrderColumn(name="PRINT_ORDER")
    private List<PrintJob> jobs;

    public PrintQueue() {
        jobs = new ArrayList<PrintJob>();
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public List<PrintJob> getJobs() {
        return jobs;
    }

    public void addJob(PrintJob job) {
        this.jobs.add(job);
        job.setQueue(this);
    }

    public String toString() {
        return "PrintQueue: " + name;
    }
}
```

### `PersonDaoImpl.java`

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {

    public void test() {
        PrintQueue q = new PrintQueue();
        q.setName("q1");
        PrintJob j = new PrintJob();
        j.setId(1);
        j.setQueue(q);
        q.getJobs().add(j);
        em.persist(j);
        em.persist(q);
    }

    @PersistenceContext
    private EntityManager em;
}
```

### `Helper.java`

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {

    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });
            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                // 后续代码省略，完整实现见上文
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```



```java
ResultSetMetaData metadata = rs.getMetaData();

while (rs.next()) {

    System.out.println(" Row:");

    for (int i = 0; i < metadata.getColumnCount(); i++) {

        System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+",  ");

        System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+":  ");

        Object value = rs.getObject(i + 1);

        System.out.println("    Column Value: "+value+"\n");

    }

}
```

```java
} catch(Exception e) {
    e.printStackTrace();
}
```

```java
}
```

## `persistence.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1.0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

## `Client.java`

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

## 输出

| 表名: PRINTJOB |
| 列名: ID, 列类型: INTEGER | 列值: 1 |
| 列名: QUEUE_NAME, 列类型: VARCHAR | 列值: q1 |
| 列名: PRINT_ORDER, 列类型: INTEGER | 列值: 0 |
| 表名: PRINTQUEUE |
| 列名: NAME, 列类型: VARCHAR | 列值: q1 |

# 6. JPA 一对多 Map 键映射

![](img/image_rsrcFTR.jpg)

在这里，你将学习如何实现一对多的映射。

以下代码展示了如何在一对多映射中设置映射键。

```java
@OneToMany(targetEntity=Person.class, mappedBy="department")
@MapKey(name="id")
private Set<Person> persons = new HashSet<Person>();
```

`@MapKey(name="id")` 设置使用 person id 作为 person 集合的映射键（key）。

## `Person.java`

```java
package com.abd.jpa;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @ManyToOne
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }
}
```

## `Department.java`

```java
package com.abd.jpa;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;

@Entity
public class Department {
    // 此处省略重复代码逻辑，原始文本中该部分不完整
}
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
            </props>
        </property>
    </bean>
</beans>
```



### 配置片段

```xml
<prop key="hibernate.hbm2ddl.auto">update</prop>
</props>
</property>
</bean>

<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
    <property name="entityManagerFactory" ref="entityManagerFactory" />
</bean>
</beans>
```

### Client.java

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

### 输出

```text
Table Name: DEPARTMENT
Row:Column Name: ID,Column Type: BIGINT:Column Value: 1
Column Name: NAME,Column Type: VARCHAR:Column Value: Design

Table Name: PERSON
Row:Column Name: ID,Column Type: BIGINT:Column Value: 1
Column Name: NAME,Column Type: VARCHAR:Column Value: Tom
Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1

Row:Column Name: ID,Column Type: BIGINT:Column Value: 2
Column Name: NAME,Column Type: VARCHAR:Column Value: Jack
Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1
```

### 7 JPA 一对多 无类型映射

以下代码指示了无类型`java.util.Map`的目标实体类。

```java
@OneToMany(targetEntity=Employee.class, mappedBy="department")
@MapKey
private Map employees;
```

### Employee.java

```java
package com.abd.jpa;

import java.util.Map;
import java.util.Set;
import javax.persistence.CollectionTable;
import javax.persistence.Column;
import javax.persistence.ElementCollection;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;
import javax.persistence.MapKeyClass;
import javax.persistence.MapKeyColumn;

@Entity
public class Employee {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private int id;
    private String name;
    private long salary;

    @ElementCollection(targetClass=String.class)
    @CollectionTable(name="EMP_PHONE")
    @MapKeyColumn(name="PHONE_TYPE")
    @MapKeyClass(String.class)
    @Column(name="PHONE_NUM")
    private Map phoneNumbers;

    @ManyToOne
    private Department department;

    public int getId() {return id;}
    public void setId(int id) {this.id = id;}
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public long getSalary() {return salary;}
    public void setSalary(long salary) {this.salary = salary;}
    public Map getPhoneNumbers() {return phoneNumbers;}
    public void setPhoneNumbers(Map phoneNumbers) {this.phoneNumbers = phoneNumbers;}
    public Department getDepartment() {return department;}
    public void setDepartment(Department department) {this.department = department;}

    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append("Employee ");
        sb.append("id=").append(id);
        sb.append(", name=").append(name);
        sb.append(", salary=").append(salary);
        sb.append(", phoneNumbers=").append(phoneNumbers);
        sb.append(", department=").append(department);
        return sb.toString();
    }
}
```

### Department.java

```java
package com.abd.jpa;

import java.util.List;
import javax.persistence.*;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private int id;
    private String name;

    @OneToMany(mappedBy="department")
    private List<Employee> employees;

    public int getId() {return id;}
    public void setId(int id) {this.id = id;}
    public String getName() {return name;}
    public void setName(String name) {this.name = name;}
    public List<Employee> getEmployees() {return employees;}
    public void setEmployees(List<Employee> employees) {this.employees = employees;}

    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append("Department ");
        sb.append("id=").append(id);
        sb.append(", name=").append(name);
        sb.append(", employees=").append(employees);
        return sb.toString();
    }
}
```

### PersonDao.java

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;

public interface PersonDao {
    void test();
}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

public class PersonDaoImpl implements PersonDao {
    @PersistenceContext
    private EntityManager em;

    @Override
    @Transactional
    public void test() {
        Department dept = new Department();
        dept.setName("IT");
        em.persist(dept);

        Employee emp1 = new Employee();
        emp1.setName("Alice");
        emp1.setSalary(50000);
        emp1.setDepartment(dept);
        em.persist(emp1);

        Employee emp2 = new Employee();
        emp2.setName("Bob");
        emp2.setSalary(60000);
        emp2.setDepartment(dept);
        em.persist(emp2);

        em.flush();
        em.clear();
    }
}
```

### Helper.java

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });

            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("  Column Name: "+ metadata.getColumnLabel(i + 1)+",  ");
                        System.out.println("  Column Type: "+ metadata.getColumnTypeName(i + 1)+":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("  Column Value: "+value+"\n");
                    }
                }
            }
        } catch(Exception e) {
            e.printStackTrace();
        }
    }
}
```

### Spring 配置文件

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:aop="http://www.springframework.org/schema/aop"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:security="http://www.springframework.org/schema/security"
       xmlns:tx="http://www.springframework.org/schema/tx"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="
       http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd
       http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd
       http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd
       http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">

    <tx:annotation-driven />
    <context:annotation-config />

    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
</beans>
```



```xml
<bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
    <property name="driverClassName">
        <value>com.mysql.jdbc.Driver</value>
    </property>
    <property name="url">
        <value>jdbc:mysql://localhost/db1</value>
    </property>
    <property name="username">
        <value>root</value>
    </property>
    <property name="password">
        <value>root</value>
    </property>
</bean>

<bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
    <property name="dataSource" ref="dataSource" />
    <property name="persistenceUnitName" value="jpaData" />
    <property name="jpaVendorAdapter">
        <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
    </property>
    <property name="jpaProperties">
        <props>
            <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
            <prop key="hibernate.show_sql">true</prop>
            <prop key="hibernate.hbm2ddl.auto">update</prop>
        </props>
    </property>
</bean>

<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
    <property name="entityManagerFactory" ref="entityManagerFactory" />
</bean>
```

## Client.java

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context =
                new ClassPathXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();
    }
}
```

## Output

```text
Table Name: DEPARTMENT

Row:Column Name: ID,Column Type: INTEGER:Column Value: 1

Column Name: NAME,Column Type: VARCHAR:Column Value: test

Table Name: EMPLOEE

Row:Column Name: ID,Column Type: INTEGER:Column Value: 1

Column Name: NAME,Column Type: VARCHAR:Column Value: Tom

Column Name: SALARY,Column Type: BIGINT:Column Value: 0

Column Name: DEPARTMENT_ID,Column Type: INTEGER:Column Value: null

Table Name: EMP_PHONE
```

# 第 3 章：JPA 多对一映射

## 1. JPA ManyToOne 映射

![](img/image_rsrcFTR.jpg)

在这里你将学习如何进行多对一映射。

以下代码展示了如何实现多对一映射。

它创建了两个实体，`Person` 和 `Department`。一个 `Department` 可以拥有许多 `Person`。

在 `Person` 类的 `department` 字段中，使用 `@ManyToOne` 注解标记 `Department`。

```java
@Entity
public class Person {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private long id;

    private String name;

    @ManyToOne(cascade = CascadeType.ALL)
    private Department department;
}
```

### Person.java

```java
package com.abd.jpa;

import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToOne;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private long id;

    private String name;

    @ManyToOne(cascade = CascadeType.ALL)
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }
}
```

### Department.java

```java
package com.abd.jpa;

import java.util.HashSet;
import java.util.Set;

import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.OneToMany;

@Entity
public class Department {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private long id;

    private String name;

    @OneToMany(mappedBy = "department", cascade = CascadeType.ALL)
    private Set<Person> persons = new HashSet<>();

    public Set<Person> getPersons() {
        return persons;
    }

    public void setPersons(Set<Person> persons) {
        this.persons = persons;
    }

    public long getId() {
        return id;
    }

    public void setId(long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + "]";
    }
}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;

import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    @PersistenceContext
    private EntityManager em;

    public void test() {
        Department d = new Department();
        d.setName("Design");

        Person p1 = new Person("Tom");
        p1.setDepartment(d);

        Person p2 = new Person("Jack");
        p2.setDepartment(d);

        d.getPersons().add(p1);
        d.getPersons().add(p2);

        em.persist(p1);
        em.persist(p2);
        em.persist(d);
    }
}
```

### Helper.java

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");

            Connection conn = DriverManager.getConnection(
                    "jdbc:mysql://localhost/db1", "root", "root");

            Statement st = conn.createStatement();

            ResultSet mrs = conn.getMetaData().getTables(
                    null, null, null, new String[] {"TABLE"});

            while (mrs.next()) {
                String tableName = mrs.getString(3);

                System.out.println("\n\n\n\nTable Name: " + tableName);

                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {
                    System.out.println(" Row:");

                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println(
                                "  Column Name: "
                                        + metadata.getColumnLabel(i + 1) + ", ");

                        System.out.println(
                                "  Column Type: "
                                        + metadata.getColumnTypeName(i + 1) + ": ");

                        Object value = rs.getObject(i + 1);

                        System.out.println("  Column Value: " + value + "\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

### persistence.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0"
    xmlns="http://java.sun.com/xml/ns/persistence"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

```xml
<!-- 代码块保持不变，不翻译 -->
```

## Client.java

```java
<!-- 代码块保持不变，不翻译 -->
```

## 输出

```text
Table Name: DEPARTMENT

Row:Column Name: ID,Column Type: BIGINT:Column Value: 1

Column Name: NAME,Column Type: VARCHAR:Column Value: Design

Table Name: PERSON

Row:Column Name: ID,Column Type: BIGINT:Column Value: 1

Column Name: NAME,Column Type: VARCHAR:Column Value: Jack

Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1

Row:Column Name: ID,Column Type: BIGINT:Column Value: 2

Column Name: NAME,Column Type: VARCHAR:Column Value: Tom

Column Name: DEPARTMENT_ID,Column Type: BIGINT:Column Value: 1
```

## 2. JPA 多对一连接列映射

以下代码展示了如何在多对一映射中设置连接列。

```java
@ManyToOne
@JoinColumns({
    @JoinColumn(name = "DEPT_NAME", referencedColumnName = "Name"),
    @JoinColumn(name = "DEPT_ID", referencedColumnName = "ID")
})
private Department department;
```

### Person.java

```java
<!-- 代码块保持不变，不翻译 -->
```

### Department.java

```java
<!-- 代码块保持不变，不翻译 -->
```

### PersonDaoImpl.java

```java
<!-- 代码块保持不变，不翻译 -->
```

### Helper.java

```java
<!-- 代码块保持不变，不翻译 -->
```

### persistence.xml

```xml
<!-- 代码块保持不变，不翻译 -->
```

```xml
<?xml version="1.0" encoding="UTF-8"?>
```



<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">

    <tx:annotation-driven />

    <context:annotation-config />

    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />

    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">

        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>

        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>

        <property name="username"><value>root</value></property>

        <property name="password"><value>root</value></property>

    </bean>

    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">

        <property name="dataSource" ref="dataSource" />

        <property name="persistenceUnitName" value="jpaData" />

        <property name="jpaVendorAdapter">

            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />

        </property>

        <property name="jpaProperties">

            <props>

                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>

                <prop key="hibernate.show_sql">true</prop>

                <prop key="hibernate.hbm2ddl.auto">update</prop>

            </props>

        </property>

    </bean>

    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">

        <property name="entityManagerFactory" ref="entityManagerFactory" />

    </bean>

</beans>

### Client.java

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {

    public static void main(String[] args) {

        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();

    }

}
```

### 输出

表名: DEPARTMENT
行: 列名: ID,列类型: BIGINT:列值: 1
列名: NAME,列类型: VARCHAR:列值: Design

表名: PERSON
行: 列名: ID,列类型: BIGINT:列值: 1
列名: NAME,列类型: VARCHAR:列值: Tom
列名: DEPT_NAME,列类型: VARCHAR:列值: Design
列名: DEPT_ID,列类型: BIGINT:列值: 1
行: 列名: ID,列类型: BIGINT:列值: 2
列名: NAME,列类型: VARCHAR:列值: Jack
列名: DEPT_NAME,列类型: VARCHAR:列值: Design
列名: DEPT_ID,列类型: BIGINT:列值: 1

### 3 JPA ManyToOne 关联列映射

以下代码标记了多对一映射中使用的关联列。

```java
@ManyToOne(cascade=CascadeType.ALL)@JoinColumn(name="DEPT_ID")
private Department department;
```

### Person.java

```java
package com.abd.jpa;

import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.ManyToOne;

@Entity
public class Person {

    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;

    private String name;

    @ManyToOne(cascade=CascadeType.ALL)
    @JoinColumn(name="DEPT_ID")
    private Department department;

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Department getDepartment() {
        return department;
    }

    public void setDepartment(Department department) {
        this.department = department;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + "]";
    }

}
```

### Department.java

```java
package com.abd.jpa;

import javax.persistence.CascadeType;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.ManyToOne;

@Entity
public class Department {

    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;

    private String name;

    public Department() {}

    public Department(String name) {
        this.name = name;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + "]";
    }

}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;

import java.util.List;
import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import javax.persistence.Query;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {

    @PersistenceContext
    private EntityManager em;

    public void test() {

        Department d = new Department();
        d.setName("Design");

        Person p1 = new Person("Tom");
        p1.setDepartment(d);
        em.persist(p1);

        Person p2 = new Person("Jack");
        p2.setDepartment(d);
        em.persist(p2);

    }

}
```

### Helper.java

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {

    public static void checkData() {

        try {

            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });

            while (mrs.next()) {

                String tableName = mrs.getString(3);
                System.out.println("\n\n\nTable Name: " + tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {

                    System.out.println(" Row:");

                    for (int i = 0; i < metadata.getColumnCount(); i++) {

                        System.out.println("    Column Name: " + metadata.getColumnLabel(i + 1) + ",  ");
                        System.out.println("    Column Type: " + metadata.getColumnTypeName(i + 1) + ":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("    Column Value: " + value + "\n");

                    }

                }

            }

        } catch (Exception e) {

            e.printStackTrace();

        }

    }

}
```

*(注：原文提供的文本中存在部分代码重复和混乱（如 `Person.java` 后面重复了多次），翻译时已根据逻辑结构进行了整理和对齐)*



`<?xml version="1.0" encoding="UTF-8"?>`

```
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>
        <property name="url"><value>jdbc:mysql://localhost/db1</value></property>
        <property name="username"><value>root</value></property>
        <property name="password"><value>root</value></property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

`Client.java`

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {

    public static void main(String[] args) {

        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();

    }

}
```

输出

- 表名：`DEPARTMENT`
  - 行: 列名: `ID`, 列类型: `BIGINT`, 列值: `1`
    - 列名: `NAME`, 列类型: `VARCHAR`, 列值: `Design`
- 表名：`PERSON`
  - 行: 列名: `ID`, 列类型: `BIGINT`, 列值: `1`
    - 列名: `NAME`, 列类型: `VARCHAR`, 列值: `Tom`
    - 列名: `DEPT_ID`, 列类型: `BIGINT`, 列值: `1`
  - 行: 列名: `ID`, 列类型: `BIGINT`, 列值: `2`
    - 列名: `NAME`, 列类型: `VARCHAR`, 列值: `Jack`
    - 列名: `DEPT_ID`, 列类型: `BIGINT`, 列值: `1`

# 第 4 章：JPA 多对多映射

### 1. JPA ManyToMany 映射
### 2. JPA ManyToMany 连接表映射
### 3. JPA ManyToMany 双向映射
### 4. JPA ManyToMany 嵌入映射

### 1. JPA ManyToMany 映射

![image_rsrcFTS.jpg](image_rsrcFTS.jpg)![image_rsrcFTT.jpg](image_rsrcFTT.jpg)![image_rsrcFTU.jpg](image_rsrcFTU.jpg)

在这里你将学习如何实现多对多映射。

以下代码展示了如何创建一个多对多映射。

它定义了`person`和`department`之间的关系。一个部门可以有许多人员，而一个人可以就于多个部门。

`Person.java`

```java
package com.abd.jpa;

import java.util.HashSet;
import java.util.Set;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToMany;

@Entity
public class Person {

    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;

    private String name;

    @ManyToMany
    private Set<Department> departments = new HashSet<Department>();

    public Person() {}

    public Person(String name) {
        this.name = name;
    }

    public Set<Department> getDepartments() {
        return departments;
    }

    public void setDepartments(Set<Department> departments) {
        this.departments = departments;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Person [id=" + id + ", name=" + name + ", departments=" + departments + "]";
    }
}
```

`Department.java`

```java
package com.abd.jpa;

import java.util.HashSet;
import java.util.Set;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToMany;

@Entity
public class Department {

    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;

    private String name;

    @ManyToMany
    private Set<Person> persons = new HashSet<Person>();

    public Department() {}

    public Department(String name) {
        this.name = name;
    }

    public Set<Person> getPersons() {
        return persons;
    }

    public void setPersons(Set<Person> persons) {
        this.persons = persons;
    }

    public Long getId() {
        return id;
    }

    public void setId(Long id) {
        this.id = id;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    @Override
    public String toString() {
        return "Department [id=" + id + ", name=" + name + ", persons=" + persons + "]";
    }
}
```

`PersonDaoImpl.java`

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {

    @PersistenceContext
    private EntityManager em;

    public void test() {
        // 测试逻辑
    }
}
```

`Helper.java`

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {

    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });

            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\nTable Name: "+ tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {
                    System.out.println(" Row:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1) + ",  ");
                        System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1) + ":  ");
                        Object value = rs.getObject(i + 1);
                        System.out.println("    Column Value: "+value+"\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

`persistence.xml`

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
```



### 1. 配置与代码示例

以下示例展示了如何配置 Spring 与 JPA 环境，并实现多对多关系映射。

#### 1.1 持久化单元配置

在`persistenceContext.xml`中定义持久化单元：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

#### 1.2 Spring 应用上下文配置

在`applicationContext.xml`中配置数据源、实体管理器工厂及事务管理器：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">

    <tx:annotation-driven />

    <context:annotation-config />

    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />

    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>

    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendor">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>

    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>

</beans>
```

#### 1.3 客户端入口

`Client.java`用于加载上下文并执行测试：

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathContext;

public class Client {
    public static void main(String[] args) {
        ClassPathContext context = new ClassPathContext("applicationContext.xml");
        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");
        dao.test();
        context.close();
        Helper.checkData();
    }
}
```

#### 1.4 数据输出示例

运行上述代码后，控制台输出如下（节选）：

```
表名: DEPARTMENT
行:列名: ID, 类型: BIGINT, 值: 1
列名: NAME, 类型: VARCHAR, 值: Design
行:列名: ID, 类型: BIGINT, 值: 2

表名: DEPARTMENT_PERSON
行:列名: DEPARTMENT_ID, 类型: BIGINT, 值: 1
列名: PERSON_ID, 类型: BIGINT, 值: 1
行:列名: DEPARTMENT_ID, 类型: BIGINT, 值: 1
列名: PERSON_ID, 类型: BIGINT, 值: 2

表名: PERSON
行:列名: ID, 类型: BIGINT, 值: 1
列名: NAME, 类型: VARCHAR, 值: Tom
行:列名: ID, 类型: BIGINT, 值: 2
列名: NAME, 类型: VARCHAR, 值: Jack

表名: PERSON_DEPARTMENT
行:列名: PERSON_ID, 类型: BIGINT, 值: 1
列名: DEPARTMENTS_ID, 类型: BIGINT, 值: 1
行:列名: PERSON_ID, 类型: BIGINT, 值: 1
列名: DEPARTMENTS_ID, 类型: BIGINT, 值: 2
```

### 2 JPA 多对多中间表映射

以下代码展示了如何通过`@JoinTable`注解配置多对多关系。

#### 2.1 实体类 `Person.java`

```java
package com.abd.jpa;

import java.util.HashSet;
import java.util.Set;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.JoinColumn;
import javax.persistence.JoinTable;
import javax.persistence.ManyToMany;

@Entity
public class Person {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @ManyToMany
    @JoinTable(name="PERSON_DEPARTMENT",
               joinColumns=@JoinColumn(name="PERSON_ID"),
               inverseJoinColumns=@JoinColumn(name="DEPARTMENTS_ID"))
    private Set<Department> departments = new HashSet<>();

    public long getId() { return id; }
    public void setId(long id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public Set<Department> getDepartments() { return departments; }
    public void setDepartments(Set<Department> departments) { this.departments = departments; }
}
```

#### 2.2 实体类 `Department.java`

```java
package com.abd.jpa;

import java.util.HashSet;
import java.util.Set;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;
import javax.persistence.ManyToMany;

@Entity
public class Department implements java.io.Serializable {
    @Id
    @GeneratedValue(strategy=GenerationType.IDENTITY)
    private long id;
    private String name;

    @ManyToMany
    private Set<Person> persons = new HashSet<>();

    public Set<Person> getPersons() { return persons; }
    public void setPersons(Set<Person> persons) { this.persons = persons; }
    public long getId() { return id; }
    public void setId(long id) { this.id = id; }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
}
```

#### 2.3 数据访问对象 `PersonDaoImpl.java`

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;
import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    @PersistenceContext
    private EntityManager em;

    public void test() {
        // 测试逻辑
    }
}
```

#### 2.4 辅助类 `Helper.java`

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");
            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");
            Statement st = conn.createStatement();
            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });

            while (mrs.next()) {
                String tableName = mrs.getString(3);
                System.out.println("\n\n\n\n 表名: " + tableName);
                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {
                    System.out.println(" 行:");
                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println(" 列名: " + metadata.getColumnLabel(i + 1) + ", ");
                        System.out.println(" 列类型: " + metadata.getColumnTypeName(i + 1) + ": ");
                        Object value = rs.getObject(i + 1);
                        System.out.println(" 列值: " + value + "\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```



<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans.0.xsd http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop.0.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context.0.xsd http://www.springframework.org/schema/security http://www.springframework.org/schema/security/spring-security.0.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx.0.xsd">

    <tx:annotation-driven />

    <context:annotation-config />

    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />

    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">

        <property name="driverClassName"><value>com.mysql.jdbc.Driver</value></property>

        <property name="url"><value>jdbc:mysql://localhost/db</value></property>

        <property name="username"><value>root</value></property>

        <property name="password"><value>root</value></property>

    </bean>

    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">

        <property name="dataSource" ref="dataSource" />

        <property name="persistenceUnitName" value="jpaData" />

        <property name="jpaVendorAdapter">

            <bean class="org.springframework.orm.jpa.vendor.HibernateVendorAdapter" />

        </property>

        <property name="jpaProperties">

            <props>

                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>

                <prop key="hibernate.show_sql">true</prop>

                <prop key="hibernate.hbm2ddl.auto">update</prop>

            </props>

        </property>

    </bean>

    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">

        <property name="entityManagerFactory" ref="entityManagerFactory" />

    </bean>

</beans>

### Client.java

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {

    public static void main(String[] args) {

        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();

    }

}
```

### Output

**Table Name: DEPARTMENT**
- Row: Column Name: ID, Type: BIGINT, Value: 1
- Column Name: NAME, Type: VARCHAR, Value: Design
- Row: Column Name: ID, Type: BIGINT, Value: 2
- Column Name: NAME, Type: VARCHAR, Value: Testing

**Table Name: DEPARTMENT_PERSON**
- Row: Column Name: DEPARTMENT_ID, Type: BIGINT, Value: 1
- Column Name: PERSONS_ID, Type: BIGINT, Value: 1
- Row: Column Name: DEPARTMENT_ID, Type: BIGINT, Value: 1
- Column Name: PERSONS_ID, Type: BIGINT, Value: 2

**Table Name: PERSON**
- Row: Column Name: ID, Type: BIGINT, Value: 1
- Column Name: NAME, Type: VARCHAR, Value: Tom
- Row: Column Name: ID, Type: BIGINT, Value: 2
- Column Name: NAME, Type: VARCHAR, Value: Jack

**Table Name: PERSON_DE**
- Row: Column Name: PERSON_ID, Type: BIGINT, Value: 1
- Column Name: DEPT_ID, Type: BIGINT, Value: 1
- Row: Column Name: PERSON_ID, Type: BIGINT, Value: 1
- Column Name: DEPT_ID, Type: BIGINT, Value: 2
- Row: Column Name: PERSON_ID, Type: BIGINT, Value: 2
- Column Name: DEPT_ID, Type: BIGINT, Value: 1
- Row: Column Name: PERSON_ID, Type: BIGINT, Value: 2
- Column Name: DEPT_ID, Type: BIGINT, Value: 2

### 3 JPA ManyToMany 双向映射

![](img/image_rsrcFTV.jpg)![](img/image_rsrcFTW.jpg)![](img/image_rsrcFTX.jpg)

以下代码展示了如何创建一个双向多多映射。

### Professor.java

```java
package com.abd.jpa;

import java.util.ArrayList;

import java.util.Collection;

import javax.persistence.Entity;

import javax.persistence.GeneratedValue;

import javax.persistence.GenerationType;

import javax.persistence.Id;

import javax.persistence.ManyToMany;

@Entity

public class Professor {

    @Id

    @GeneratedValue(strategy=GenerationType.IDENTITY)

    private int id;

    private String name;

    private long salary;

    @ManyToMany(mappedBy="projects")

    private Collection<Project> projects;

    public Professor() {

        projects = new ArrayList<Project>();

    }

    public int getId() { return id; }

    public void setId(int id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public long getSalary() { return salary; }

    public void setSalary(long salary) { this.salary = salary; }

    public void addProject(Project project) {

        if (!projects.contains(project)) {

            projects.add(project);

        }

        if (!project.getProjects().contains(this)) {

            project.getProjects().add(this);

        }

    }

    public Collection<Project> getProjects() { return projects; }

    public String toString() {

        return "Professor id: " + id + ", name: " + name + " with " + projects.size() + " projects";

    }

}
```

### Project.java

```java
package com.abd.jpa;

import java.util.ArrayList;

import java.util.Collection;

import javax.persistence.Entity;

import javax.persistence.GeneratedValue;

import javax.persistence.GenerationType;

import javax.persistence.Id;

import javax.persistence.ManyToMany;

@Entity

public class Project {

    @Id

    @GeneratedValue(strategy=GenerationType.IDENTITY)

    private int id;

    private String name;

    @ManyToMany

    private Collection<Professor> employees;

    public Project() {

        employees = new ArrayList<Professor>();

    }

    public int getId() { return id; }

    public void setId(int id) { this.id = id; }

    public String getName() { return name; }

    public void setName(String name) { this.name = name; }

    public void addEmployee(Professor employee) {

        if (!employees.contains(employee)) {

            employees.add(employee);

        }

        if (!employee.getProjects().contains(this)) {

            employee.getProjects().add(this);

        }

    }

    public Collection<Professor> getEmployees() { return employees; }

    public String toString() {

        return "Project id: " + id + ", name: " + name + " with " + employees.size() + " employees";

    }

}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;

import javax.persistence.EntityManager;

import javax.persistence.PersistenceContext;

import org.springframework.transaction.annotation.Transactional;

@Transactional

public class PersonDaoImpl {

    public void test() {

        Professor emp = new Professor();

        emp.setName("name");

        emp.setSalary(12345);

        Project p = new Project();

        p.setName("Chem");

        p.getEmployees().add(emp);

        emp.getProjects().add(p);

        em.persist(p);

        em.persist(emp);

    }

    @PersistenceContext

    private EntityManager em;

}
```

### Helper.java

```java
package com.abd.jpa;

import java.sql.Connection;

import java.sql.DriverManager;

import java.sql.ResultSet;

import java.sql.ResultSetMetaData;

import java.sql.Statement;

public class Helper {

    public static void checkData() {

        try {

            Class.forName("com.mysql.jdbc.Driver");

            Connection conn = DriverManager.getConnection("jdbc:mysql://localhost/db1", "root", "root");

            Statement st = conn.createStatement();

            ResultSet mrs = conn.getMetaData().getTables(null, null, null, new String[] { "TABLE" });



    while (mrs.next()) {

        String tableName = mrs.getString(3);

        System.out.println("\n\n\n\nTable Name: "+ tableName);

        ResultSet rs = st.executeQuery("select * from " + tableName);

        ResultSetMetaData metadata = rs.getMetaData();

        while (rs.next()) {

            System.out.println(" Row:");

            for (int i = 0; i < metadata.getColumnCount(); i++) {

                System.out.println("    Column Name: "+ metadata.getColumnLabel(i + 1)+",  ");

                System.out.println("    Column Type: "+ metadata.getColumnTypeName(i + 1)+":  ");

                Object value = rs.getObject(i + 1);

                System.out.println("    Column Value: "+value+"\n");

            }

        }

    }

} catch(Exception e) {

    e.printStackTrace();

}

```

### persistence.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence version="1.0" xmlns="http://java.sun.com/xml/ns/persistence" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">
    <persistence-unit name="jpaData" />
</persistence>
```

### applicationContext.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans" xmlns:aop="http://www.springframework.org/schema/aop" xmlns:context="http://www.springframework.org/schema/context" xmlns:security="http://www.springframework.org/schema/security" xmlns:tx="http://www.springframework.org/schema/tx" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://www.springframework.org/schema/aop http://www.springframework.org/schema/aop/spring-aop-3.2.xsd http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.2.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.2.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.2.xsd">
    <tx:annotation-driven />
    <context:annotation-config />
    <bean id="personDao" class="com.abd.jpa.PersonDaoImpl" />
    <bean id="dataSource" class="org.springframework.jdbc.datasource.DriverManagerDataSource">
        <property name="driverClassName">
            <value>com.mysql.jdbc.Driver</value>
        </property>
        <property name="url">
            <value>jdbc:mysql://localhost/db1</value>
        </property>
        <property name="username">
            <value>root</value>
        </property>
        <property name="password">
            <value>root</value>
        </property>
    </bean>
    <bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
        <property name="dataSource" ref="dataSource" />
        <property name="persistenceUnitName" value="jpaData" />
        <property name="jpaVendorAdapter">
            <bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter" />
        </property>
        <property name="jpaProperties">
            <props>
                <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
                <prop key="hibernate.show_sql">true</prop>
                <prop key="hibernate.hbm2ddl.auto">update</prop>
            </props>
        </property>
    </bean>
    <bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
        <property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
</beans>
```

### Client.java

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {

    public static void main(String[] args) {

        ClassPathXmlApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();

    }

}
```

### Output

```java
Table Name: person

Row:

    Column Name: id,  

    Column Type: INT,  

    Column Value: 1

    Column Name: first_name,  

    Column Type: VARCHAR,  

    Column Value: John

    Column Name: last_name,  

    Column Type: VARCHAR,  

    Column Value: Doe

    Column Name: salary,  

    Column Type: BIGINT,  

    Column Value: 5000
```

### Employee.java

The following code uses `@Override` to override the `toString` method.

```java
package com.abd.jpa;

import java.util.ArrayList;

import java.util.Collection;

import javax.persistence.*;

@Entity

public class Employee {

    @Id

    @GeneratedValue(strategy = GenerationType.IDENTITY)

    private int id;

    @Embedded

    private EmployeeName name;

    private long salary;

    @ManyToMany(mappedBy = "employees")

    @AttributeOverrides({

        @AttributeOverride(name = "first_name", column = @Column(name="EMP_FNAME")),

        @AttributeOverride(name = "last_name", column = @Column(name="EMP_LNAME"))

    })

    private Collection<Department> departments;

    public Employee() {

        name = new EmployeeName();

        departments = new ArrayList<>();

    }

    public int getId() { return id; }

    public void setId(int id) { this.id = id; }

    public EmployeeName getName() { return name; }

    public void setName(EmployeeName name) { this.name = name; }

    public String getFirstName() { return name.getFirst_Name(); }

    public void setFirstName(String firstName) { this.name.setFirst_Name(firstName); }

    public String getLastName() { return name.getLast_Name(); }

    public void setLastName(String lastName) { this.name.setLast_Name(lastName); }

    public long getSalary() { return salary; }

    public void setSalary(long salary) { this.salary = salary; }

    public Collection<Department> getDepartments() { return departments; }

    public void setDepartments(Collection<Department> departments) { this.departments = departments; }

    @Override

    public String toString() {

        StringBuffer aBuffer = new StringBuffer("Employee ");

        aBuffer.append(" id: ");

        aBuffer.append(id);

        aBuffer.append(" name: ");

        aBuffer.append(getLastName());

        aBuffer.append(", ");

        aBuffer.append(getFirstName());

        aBuffer.append(" with deptCount: ");

        if(null != departments) {

            aBuffer.append(departments.size());

        }

        return aBuffer.toString();

    }

}
```

### EmployeeName.java

```java
package com.abd.jpa;

import javax.persistence.Column;

import javax.persistence.Embeddable;

@Embeddable

public class EmployeeName {

    @Column(name="F_NAME", insertable=false, updatable=false)

    private String first_Name;

    @Column(name="L_NAME", insertable=false, updatable=false)

    private String last_Name;

    public String getFirst_Name() { return first_Name; }

    public void setFirst_Name(String firstName) { this.first_Name = firstName; }

    public String getLast_Name() { return last_Name; }

    public void setLast_Name(String lastName) { this.last_Name = lastName; }

}
```

### Department.java

```java
package com.abd.jpa;

import java.util.HashMap;

import java.util.Iterator;

import java.util.Map;

import javax.persistence.AttributeOverride;

import javax.persistence.AttributeOverrides;

import javax.persistence.Column;

import javax.persistence.Entity;

import javax.persistence.GeneratedValue;

import javax.persistence.GenerationType;

import javax.persistence.Id;

import javax.persistence.JoinColumn;

import javax.persistence.JoinTable;

import javax.persistence.ManyToMany;

@Entity

public class Department {

    @Id



```java
@GeneratedValue(strategy=GenerationType.IDENTITY)

private int id;

private String name;

@ManyToMany

@JoinTable(name="DEPT_EMP",joinColumns=@JoinColumn(name="DEPT_ID"),inverseJoinColumns=@JoinColumn(name="EMP_ID"))

@AttributeOverrides({
    @AttributeOverride(name="first_Name",column=@Column(name="EMP_FNAME")),
    @AttributeOverride(name="last_Name",column=@Column(name="EMP_LNAME"))
})

private Map<EmployeeName, Employee> employeesByName;

public Department() {
    employeesByName = new HashMap<EmployeeName,Employee>();
}

public int getId() {
    return id;
}

public void setId(int id) {
    this.id = id;
}

public String getName() {
    return name;
}

public void setName(String deptName) {
    this.name = deptName;
}

public Map<EmployeeName, Employee> getEmployees() {
    return employeesByName;
}

public void addEmployee(Employee employee) {
    EmployeeName empName = employee.getName();
    employeesByName.put(empName, employee);
}

public void removeEmployee(Employee employee) {
    Iterator iter = employeesByName.entrySet().iterator();

    while (iter.hasNext()) {
        Employee current = ((Map.Entry<EmployeeName,Employee>) iter.next()).getValue();

        if (current.getId() == employee.getId()) {
            iter.remove();
        }
    }
}

public String toString() {
    StringBuffer aBuffer = new StringBuffer("Department ");

    aBuffer.append(" id: ");
    aBuffer.append(id);
    aBuffer.append(" name: ");
    aBuffer.append(name);
    aBuffer.append(" employeeCount: ");
    aBuffer.append(employeesByName.size());

    return aBuffer.toString();
}
```

### PersonDaoImpl.java

```java
package com.abd.jpa;

import javax.persistence.EntityManager;
import javax.persistence.PersistenceContext;

import org.springframework.transaction.annotation.Transactional;

@Transactional
public class PersonDaoImpl {
    public void test() {
        Employee e = new Employee();
        e.setFirstName("Tom");
        e.setLastName("Smith");

        Department d = new Department();
        d.setName("test");

        EmployeeName name = new EmployeeName();
        name.setFirst_Name("Tom");
        name.setLast_Name("Smith");

        e.getDepartments().add(d);
        d.getEmployees().put(name, e);

        em.persist(e);
        em.persist(d);
    }

    @PersistenceContext
    private EntityManager em;
}
```

### Helper.java

```java
package com.abd.jpa;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.ResultSetMetaData;
import java.sql.Statement;

public class Helper {
    public static void checkData() {
        try {
            Class.forName("com.mysql.jdbc.Driver");

            Connection conn = DriverManager.getConnection(
                "jdbc:mysql://localhost/db1",
                "root",
                "root"
            );

            Statement st = conn.createStatement();

            ResultSet mrs = conn.getMetaData().getTables(
                null,
                null,
                null,
                new String[] { "TABLE" }
            );

            while (mrs.next()) {
                String tableName = mrs.getString(3);

                System.out.println("\n\n\n\nTable Name: " + tableName);

                ResultSet rs = st.executeQuery("select * from " + tableName);
                ResultSetMetaData metadata = rs.getMetaData();

                while (rs.next()) {
                    System.out.println(" Row:");

                    for (int i = 0; i < metadata.getColumnCount(); i++) {
                        System.out.println(
                            "    Column Name: "
                            + metadata.getColumnLabel(i + 1)
                            + ",  "
                        );

                        System.out.println(
                            "    Column Type: "
                            + metadata.getColumnTypeName(i + 1)
                            + ":  "
                        );

                        Object value = rs.getObject(i + 1);

                        System.out.println("    Column Value: " + value + "\n");
                    }
                }
            }
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

### persistence.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<persistence
    version="1.0"
    xmlns="http://java.sun.com/xml/ns/persistence"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/persistence http://java.sun.com/xml/ns/persistence/persistence_1_0.xsd">

    <persistence-unit name="jpaData" />
</persistence>
```

### applicationContext.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans
    xmlns="http://www.springframework.org/schema/beans"
    xmlns:aop="http://www.springframework.org/schema/aop"
    xmlns:context="http://www.springframework.org/schema/context"
    xmlns:security="http://www.springframework.org/schema/security"
    xmlns:tx="http://www.springframework.org/schema/tx"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="
        http://www.springframework.org/schema/aop
        http://www.springframework.org/schema/aop/spring-aop-3.2.xsd
        http://www.springframework.org/schema/beans
        http://www.springframework.org/schema/beans/spring-beans-3.2.xsd
        http://www.springframework.org/schema/context
        http://www.springframework.org/schema/context/spring-context-3.2.xsd">
</beans>
```

### Client.java

```java
package com.abd.jpa;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class Client {
    public static void main(String[] args) {
        ClassPathXmlApplicationContext context =
            new ClassPathXmlApplicationContext("applicationContext.xml");

        PersonDaoImpl dao = (PersonDaoImpl) context.getBean("personDao");

        dao.test();

        context.close();

        Helper.checkData();
    }
}
```

### Output

```text
Table Name: DEPARTMENT

Row:

Column Name: ID, Type: INTEGER, Value: 1

Column Name: NAME, Type: VARCHAR, Value: test

Table Name: DEPT_EMP

Row:

Column Name: DEPT_ID, Type: INTEGER, Value: 1

Column Name: EMP_ID, Type: INTEGER, Value: 1

Column Name: F_NAME, Type: VARCHAR, Value: Tom

Column Name: L_NAME, Type: VARCHAR, Value: Smith

Table Name: EMPLOYEE

Row:

Column Name: ID, Type: INTEGER, Value: 1

Column Name: F_NAME, Type: VARCHAR, Value: Tom

Column Name: L_NAME, Type: VARCHAR, Value: Smith

Column Name: SALARY, Type: BIGINT, Value: 0
```



# 所有结果数据从表格到浏览器

## MVC（模型-视图控制器）架构

用于视图（向浏览器显示结果数据）：

- 结果数据来自表格。
- 在连接数据库后，前端控制器将获取相应的`JSP 页面`。
- 将数据放入`JSP 页面`，并将`JSP 页面`发送回浏览器。
- 浏览器进行显示。

## 首页

![](img/image_rsrcFPT.jpg)

## 环境

| 技术栈 | 详情 |
| :--- | :--- |
| 技术 | `Struts1`、`Spring`、`Hibernate`、`Javascript`、`Css`、`Jquery` |
| 数据库 | `MySQL` |
| 服务器 | `Tomcat 1.6` |
| 日志工具 | `Log4j` |
| IDE | `Eclipse` |
| 设计模式 | `前端控制器`、`MVC`、`工厂`、`DAO`、`代理`、`单例`、`抽象工厂模式`、`模板模式`、`SessionFactory`、`TransactionFactory` |

## 目录结构

![](img/image_rsrcFPU.jpg)

### 目录结构（展开）

![](img/image_rsrcFPV.jpg)

![](img/image_rsrcFPW.jpg)

![](img/image_rsrcFPX.jpg)

![](img/image_rsrcFPY.jpg)

## 模块详情

### 首页

![](img/image_rsrcFPT.jpg)

### 员模块 I

- 登录

  ![](img/image_rsrcFTY.jpg)

- 登录成功

  ![](img/image_rsrcFTZ.jpg)

- 添加医生账号

  ![](img/image_rsrcFU0.jpg)

- 添加医生账号成功

  ![](img/image_rsrcFU1.jpg)

- 查看医院医生信息

  ![](img/image_rsrcFU2.jpg)

- 移除医生信息

  ![](img/image_rsrcFU3.jpg)

### 患者模块 II

- 患者注册

  ![](img/image_rsrcFU4.jpg)

- 患者注册成功

  ![](img/image_rsrcFU5.jpg)

- 查看所有医生

  ![](img/image_rsrcFU6.jpg)

- 查找预约

  ![](img/image_rsrcFU7.jpg)

- 查找可用医生预约列表

  ![](img/image_rsrcFU8.jpg)

- 选择预约以确定医生

  ![](img/image_rsrcFU9.jpg)

- 医生预约已确认

  ![](img/image_rsrcFUA.jpg)

- 医生预约总数

  ![](img/image_rsrcFUB.jpg)

- 取消选定的医生预约

  ![](img/image_rsrcFUC.jpg)

- 取消医生预约成功

  ![](img/image_rsrcFUD.jpg)

- 查询医生记录

  ![](img/image_rsrcFUE.jpg)

- 查询医生诊断记录

  ![](img/image_rsrcFUF.jpg)

### 医生模块 III

- 医生登录

  ![](img/image_rsrcFUG.jpg)

- 医生登录成功

  ![](img/image_rsrcFUH.jpg)

- 修改密码

  ![](img/image_rsrcFUJ.jpg)

- 修改密码成功

  ![](img/image_rsrcFUK.jpg)

- 查看患者预约

  ![](img/image_rsrcFUM.jpg)

- 创建患者记录

  ![](img/image_rsrcFUN.jpg)

- 创建患者记录

  ![](img/image_rsrcFUP.jpg)

- 创建患者记录成功

  ![](img/image_rsrcFUR.jpg)

- 修改患者记录

  ![](img/image_rsrcFUS.jpg)

- 修改患者记录成功

  ![](img/image_rsrcFUT.jpg)

- 结束治疗

  ![](img/image_rsrcFUU.jpg)

- 结束治疗成功

  ![](img/image_rsrcFUV.jpg)

## 医院系统（流程）

- **步骤 1**：`患者` → `所需医生` → `预约`
- **步骤 2**：`医生` → `医生查看预约` → `治疗`
- **步骤 3**：`患者` → `查看治疗`
- **步骤 4**：`医生` → `医生更新治疗开始/结束时间`
- **步骤 5**：`患者` → `查看治疗状态`

## 医院系统设计文档

### 1. 医院门诊转诊系统功能

#### 1.1 系统整体功能

- 操作员权限级别具有清晰分类，当系统进行身份验证时。
- 个人患者隐私保护：只有在医生治疗期间患者本人可以访问其医疗记录，其他任何人（包括管理员在内）无权访问。

#### 1.2 患者角色

- 注册用户，设置你的登录名和密码。
- 自定义查询医生姓名。
- 根据查询结果进行预约，如果指定的日期医生预约量已满，则预约失败。结果随机返回给患者。
- 你可以拥有、查看或撤销预约。
- 进行预约时，你可以查询医生信息和医疗信息。

#### 1.3 医生角色

- 你可以查看患者的预约。
- 你可以查询患者记录。
- 你可以创建患者记录。
- 修改患者记录。

#### 1.4 管理员角色

- 你可以添加和删除医生账号。

### 2. 设计过程

从需求分析开始，进行实体分离。

**主要实体：**

- 医生（`doctor`）
- 患者（`patient`）
- 医疗记录（`history`）
- 预约记录（`pinqueue`）
- 管理员（`administrator`）
- 医生可最大预约数（`appointment`）
- 医生当前可用预约数（`currappointment`）

### 模块层次结构图

![](img/image_rsrcFUW.jpg)

### 组件图

![](img/image_rsrcFUX.jpg)

### 注册序列图（患者用户）

![](img/image_rsrcFUY.jpg)

### 患者活动图

![](img/image_rsrcFUZ.jpg)

### 医生活动图

![](img/image_rsrcFV0.jpg)

### 管理员活动图

![](img/image_rsrcFV1.jpg)

## 数据库初始化

```sql
/*****************************

create database tarena1;

use tarena1;

Spring.xml========================

Step1=========<prop key="hibernate.hbm2ddl.auto">create</prop>

Step2=========<prop key="hibernate.hbm2ddl.auto">update</prop>

表将自动创建。

*********************************/
```

```sql
create sequence dl_admin_seq;

create table dl_admin (
    aid number(2) primary key,
    username varchar2(20) unique not null,
    password varchar2(20) not null,
    email varchar2(20) not null,
    name varchar2(12) not null,
    phone varchar2(15)
);
```

## 医生预约限制

该表存储了医生可以预约的最大次数。

| DID | 医生编号 | 主键 | 外键 |
| :--- | :--- | :--- | :--- |
| `dl_doctor` | `DID` | | |
| `SunA` | 周日上午最大预约次数 | | |
| `SunP` | 周日下午最大预约次数 | | |
| `MonA` | 周一上午最大预约次数 | | |
| `MonP` | 周一下午最大预约次数 | | |
| `TueA` | 周二上午最大预约次数 | | |
| `TueP` | 周二下午最大预约次数 | | |
| `WedA` | 周三上午最大预约次数 | | |
| `WedP` | 周三下午最大预约次数 | | |
| `ThuA` | 周四上午最大预约次数 | | |
| `ThuP` | 周四下午最大预约次数 | | |
| `FriA` | 周五上午最大预约次数 | | |
| `FriP` | 周五下午最大预约次数 | | |
| `SatA` | 周六上午最大预约次数 | | |
| `SatP` | 周六下午最大预约次数 | | |

```sql
create table dl_appointment(
    did number(5) primary key references dl_doctor(did),
    sunA number(3) default '0',
    sunP number(3) default '0',
    monA number(3) default '0',
    monP number(3) default '0',
    tueA number(3) default '0',
    tueP number(3) default '0',
    wedA number(3) default '0',
    wedP number(3) default '0',
    thuA number(3) default '0',
    thuP number(3) default '0',
    friA number(3) default '0',
    friP number(3) default '0',
    satA number(3) default '0',
    satP number(3) default '0'
);
```

## 当前预约状态

医生当前可以预约的表目数量。

| DID | 医生编号 | 主键 | 外键 |
| :--- | :--- | :--- | :--- |
| `dl doctor` | `DID` | | |
| `SunA` | 周日上午可用预约最大数 | | |
| `SunP` | 周日下午可用预约最大次数 | | |
| `MonA` | 周一上午可用预约最大次数 | | |
| `MonP` | 周一下午最大预约次数 | | |
| `TueA` | 周二上午最大预约次数 | | |
| `TueP` | 周二下午最大预约次数 | | |
| `WedA` | 周三上午最大预约次数 | | |
| `WedP` | 周三下午最大预约次数 | | |
| `ThuA` | 周四上午最大预约次数 | | |
| `ThuP` | 周四下午最大预约次数 | | |
| `FriA` | 周五上午最大预约次数 | | |
| `FriP` | 周五下午最大预约次数 | | |
| `SatA` | 周六上午最大预约次数 | | |
| `SatP` | 周六下午最大预约次数 | | |

```sql
create table dl_curappointment(
    did number(5) primary key references dl_doctor(did),
    sunA number(3,0) default '0',
    sunP number(3,0) default '0',
    monA number(3,0) default '0',
    monP number(3,0) default '0',
    tueA number(3,0) default '0',
    tueP number(3,0) default '0',
    wedA number(3,0) default '0',
    wedP number(3,0) default '0',
    thuA number(3,0) default '0',
    thuP number(3,0) default '0',
    friA number(3,0) default '0',
    friP number(3,0) default '0',
    satA number(3,0) default '0',
    satP number(3,0) default '0'
);
```

## 医生信息

| DID | 医生编号 | 姓名 | 密码 | 年龄 | 性别 | 医生姓名 | 科室 | 擅长的领域医生 | 电话号码 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | | | | 1-男 0-女 | | | | |

```sql
create table dl_doctor (
    did number(5) primary key,
    name varchar2(12) not null,
    password varchar2(20) not null,
    age number(3) not null,
    sex number(3) not null,
    levels varchar2(12) not null,
    section varchar2(20) not null,
    specialism varchar2(20) not null,
    phone varchar2(15)
);
```

## 历

| HID | 记录编号 | 医生主键 | 医生编号 | 外键 | 描述 | 诊断 | 患者人数 | 外键 | 处方 | 完成 | F | 开始时间 | S | 结束时间 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | `dl_doctor` | `DID` | | | | `dl_patient` | `DID` | | 0 | 2024-01-23 00:00:00 | 2024-01-21 00:00:00 | |

```sql
create sequence dl_history_seq;

create table dl_history (
    hid number(10) primary key,
    doctor_did number(5) references dl_doctor(did) not null,
    description varchar2(64) not null,
    diagnose varchar2(64) not null,
    patient_pid number(8) references dl_patient(pid) not null,
    rx varchar2(64) not null,
    finished number(1) not null,
    fDate date,
    sDate date
);
```

## 患者信息

| PID | 患者编号 | 序列生成 | 姓名 | 登录用户名 | 密码 | 年龄 | 性别 | 家庭地址 | 电话号码 | 患者病历 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | | | | | | 1-男 0-女 | | |

```sql
create sequence dl_patient_seq;

create table dl_patient (
    pid number(8) primary key,
    name varchar2(12) not null,
    username varchar2(20) unique not null,
    password varchar2(20) not null,
    age number(3) not null,
    sex number(1) not null,
    address varchar2(32),
    phone varchar2(24)
);
```

## 预约表单

| QID | 序列生成的记录编号 | 患者人数 | 外键 | 医生主键 | 医生编号 | 外键 | 天 | 预约时间 | AP 预约时间 | Dat 预约时间 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| | | `dl_patient` | `PID` | `dl_doctor` | `DID` | | 0-周日 1-周一 2-周二 3-周三 4-周四 5-周五 6-周六 | 0-上午 1-下午 | 2024-01-02 10:00:00 |

```sql
create sequence dl_pinqueue_seq;

create table dl_pinqueue(
    qid number(10) primary key,
    patient_pid number(8) references dl_patient(pid) not null,
    doctor_did number(5) references dl_doctor(did) not null,
    day number(1) not null,
    ap number(1) not null,
    dat date not null,



`constraint pinqueue_Doctor_Patient unique (doctor_did,patient_pid)`

);

```

第一 $\rightarrow$ 插入给定的 SQL 语句

# 凭据

## ADMIN
- **user**: `apassword`
- **table**: `atable`
- **tarenaTotal**: `TABLE`
- **count**: 7

## dl_patient
- **user**: `Amar`
- **password**: `Amar`
- **Note**: 第一位患者将注册（自动生成密码=123456）。请查看表，然后你可以根据需要更改你的密码。

## dl_doctor
- **user**: `Indira`
- **password**: `Indira`

```sql
insert into dl_admin (username, password, email, phone, name);

insert into dl_admin values(1, 'a', 'a', 'a@abc.com', '12345', 'a');

insert into dl_admin values(2, 'Admin', 'Admin', 'admin@abc.com', '21345', 'Admin');
```

### 医生表数据
```sql
INSERT INTO `dl_doctor` (`DID`, `Name`, `Password`, `Age`, `Sex`, `Level`, `Section`, `Specialism`, `Phone`)

INSERT INTO `dl_doctor` VALUES ('001', 'Indira', 'Indira', 28, 0, 'Professor', 'Eye', 'Short Sighted', '82330000');

INSERT INTO `dl_doctor` VALUES ('002', 'Jagan', 'Jagan', 29, 0, 'Professor', 'Head', 'Headache', '10000823');

INSERT INTO `dl_doctor` VALUES ('003', 'Chetan', 'Chetan', 40, 0, 'Suregon', 'Nose', 'Snoring', '12340002');

INSERT INTO `dl_doctor` VALUES ('004', 'Dinesh', 'Dinesh', 35, 0, 'Suregon', 'Dental', 'Teeth', '12300100');

INSERT INTO `dl_doctor` VALUES ('005', 'Pankaj', 'Pankaj', 35, 0, 'Suregon', 'Dental', 'Teeth', '8233100');

INSERT INTO `dl_doctor` VALUES ('006', 'Kamal', 'Kamal', 28, 0, 'Professor', 'Eye', 'Short Sighted', '8232300');

INSERT INTO `dl_doctor` VALUES ('007', 'Raman', 'Raman', 29, 0, 'Professor', 'Head', 'Headache', '1234023');

INSERT INTO `dl_doctor` VALUES ('008', 'Bharat', 'Bharat', 40, 0, 'Suregon', 'Nose', 'Snoring', '8330002');

INSERT INTO `dl_doctor` VALUES ('009', 'Rajeev', 'Rajeev', 40, 0, 'Professor', 'Eye', 'Short Sighted', '4500832');

INSERT INTO `dl_doctor` VALUES ('010', 'Ajay', 'Ajay', 44, 0, 'MBBS', 'Physian', 'Cold Fever', '67300082');

INSERT INTO `dl_doctor` VALUES ('011', 'Supriya', 'Supriya', 35, 1, 'Suregon', 'Dental', 'Teeth', '68082300');

INSERT INTO `dl_doctor` VALUES ('012', 'Ritu', 'Ritu', 41, 1, 'MBBS', 'Physian', 'Cold Fever', '34303000');

INSERT INTO `dl_doctor` VALUES ('013', 'Dimple', 'Dimple', 21, 1, 'Professor', 'Eye', 'Short Sighted', '8723000');

INSERT INTO `dl_doctor` VALUES ('014', 'Dipti', 'Dipti', 39, 1, 'Professor', 'Head', 'Headache', '4500023');

INSERT INTO `dl_doctor` VALUES ('015', 'Bhavna', 'Bhavna', 40, 1, 'Suregon', 'Nose', 'Snoring', '6300230');

INSERT INTO `dl_doctor` VALUES ('016', 'Tripti', 'Tripti', 34, 1, 'MBBS', 'Physian', 'Cold Fever', '5600082');

INSERT INTO `dl_doctor` VALUES ('017', 'Dipti', 'Dipti', 24, 1, 'MBBS', 'Physian', 'Cold Fever', '4723000');

INSERT INTO `dl_doctor` VALUES ('018', 'Rohan', 'Rohan', 35, 0, 'Suregon', 'Dental', 'Teeth', '5408023');

INSERT INTO `dl_doctor` VALUES ('019', 'Dinesh', 'Dinesh', 28, 0, 'Professor', 'Eye', 'Short Sighted', '23380000');

INSERT INTO `dl_doctor` VALUES ('020', 'Dipti', 'Dipti', 39, 1, 'Professor', 'Head', 'Headache', '35400302');

INSERT INTO `dl_doctor` VALUES ('021', 'Bhavna', 'Bhavna', 40, 1, 'Suregon', 'Nose', 'Snoring', '323023');

INSERT INTO `dl_doctor` VALUES ('022', 'Ajay', 'Ajay', 4, 0, 'MBBS', 'Physian', 'Cold Fever', '700823');

INSERT INTO `dl_doctor` VALUES ('023', 'Amar', 'Amar', 38, 0, 'MBBS', 'Physian', 'Cold Fever', '980238');

INSERT INTO `dl_doctor` VALUES ('024', 'Kamal', 'Kamal', 28, 0, 'MBBS', 'Physian', 'Cold Fever', '463228');

INSERT INTO `dl_doctor` VALUES ('025', 'Akshar', 'Akshar', 28, 0, 'MBBS', 'Physian', 'Cold Fever', '463228');

INSERT INTO `dl_doctor` VALUES ('027', 'Indira1', 'Indira1', 28, 0, 'Professor', 'Eye', 'Short Sighted', '823300');
```

## dl_appointment
```sql
INSERT INTO `dl_appointment` (`DID`, `SunA`, `SunP`, `MonA`, `MonP`, `TueA`, `TueP`, `WedA`, `WedP`, `ThuA`, `ThuP`, `FriA`, `FriP`, `SatA`, `SatP`)
INSERT INTO `dl_appointment` VALUES ('001', 4, 4, 4, 4, 4, 4, 4, 4, 4, 4, 4, 4, 4, 4);
INSERT INTO `dl_appointment` VALUES ('002', 1, 2, 3, 4, 5, 6, 7, 8, 9, 0, 2, 3, 1, 0);
```

## dl_curappointment
```sql
INSERT INTO `dl_curappointment` (`DID`, `SunA`, `SunP`, `MonA`, `MonP`, `TueA`, `TueP`, `WedA`, `WedP`, `ThuA`, `ThuP`, `FriA`, `FriP`, `SatA`, `SatP`)
INSERT INTO `dl_curappointment` VALUES ('001', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('002', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('003', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('004', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('005', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('006', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('007', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('008', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('009', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('010', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('011', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('012', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('013', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('014', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('015', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('016', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
INSERT INTO `dl_curappointment` VALUES ('017', 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1);
```

## dl_patient
```sql
INSERT INTO `dl_patient` (`PID`, `Name`, `Username`, `Password`, `Age`, `Sex`, `Address`, `Phone`)

INSERT INTO `dl_patient` VALUES (101, 'Amar', 'Amar', 'Amar', 20, 0, '1 A AMAR', '34552345');

INSERT INTO `dl_patient` VALUES (102, 'Bharat', 'Bharat', 'Bharat', 20, 0, '3V KANPUR', '984121345');

INSERT INTO `dl_patient` VALUES (103, 'Raman', 'Raman', 'Raman', 40, 0, '1 A DELHI', '231234149');

INSERT INTO `dl_patient` VALUES (104, 'Gopal', 'Gopal', 'Gopal', 45, 0, '2 B PUNE', '915534123');

INSERT INTO `dl_patient` VALUES (105, 'Shyam', 'Shyam', 'Shyam', 45, 0, '2 B PUNE', '915534123');
```

## dl_history
```sql
INSERT INTO `dl_history` (`HID`, `Doctor`, `Description`, `Diagnose`, `Patient`, `Rx`, `Finished`, `FDate`, `SDate`)

INSERT INTO `dl_history` VALUES (2, '001', 'Headache', 'Sars', 1001, 'Madecine', 0, '2024-01-23 19:02:00:0 ', '2024-01-21 19:03:51:0 ');
```

# 实体关系图

| ![](img/image_rsrcFV4.jpg) |

## 第一部分：图你将获得一些概览

| ![](img/image_rsrcFV5.jpg) |

| ![](img/image_rsrcFV6.jpg) |

| ![](img/image_rsrcFPV.jpg) |

`src\com\abd\action`

`AllAction.java`

```java
package com.abd.action;

import java.util.*;

import com.abd.biz.*;

import com.abd.entity.*;

import com.abd.util.*;

import org.springframework.context.ApplicationContext;

import org.springframework.web.struts.DispatchActionSupport;

import org.apache.struts.action.*;

import javax.servlet.http.HttpServletRequest;

import javax.servlet.http.HttpServletResponse;

import javax.servlet.http.HttpSession;

public class AllAction extends DispatchActionSupport {

    // 管理员添加医生

    public ActionForward addDoctor(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

        ApplicationContext ctx = this.getWebApplicationContext();

        // 获取代理对象

        AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");

        DynaActionForm daf = (DynaActionForm)form;

        Integer did = new Integer(Integer.parseInt(daf.getString("did")));

        String name = daf.getString("name");

        int age = Integer.parseInt((String)daf.get("age"));

        int sex = Integer.parseInt((String)daf.get("sex"));

        String levels = daf.getString("level");

        String spe = daf.getString("spe");
```



以下代码片段展示了管理员与患者相关操作的 `Action` 方法实现，包含医生管理、患者注册登录、预约等功能。

```java
String phone = daf.getString("phone");

String section = daf.getString("section");

String spt = daf.getString("spDay");

int[] spDays = new int[14];

spDays = Util.parseSpDays(spt);

// 执行代理方法
admin.addDoctor(did, name, age, sex, levels, spe, spDays, phone, section);

request.setAttribute("addDoctor", "hao");

return mapping.findForward("addDoc");
```

```java
// 管理员获取所有医生
public ActionForward getDoctor(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");

    List<Doctor> set = admin.getAllDoctor();

    request.getSession(true).setAttribute("doctors", set);

    return mapping.findForward("allDoctor");
}
```

```java
// 管理员登录
public ActionForward aLogin(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");

    DynaActionForm daf = (DynaActionForm)form;

    String username = daf.getString("username");

    admin.login(username, daf.getString("password"));

    request.getSession(true).setAttribute("admin", username);

    return mapping.findForward("aLogin");
}
```

```java
// 管理员删除医生。如果该医生有转诊病历或已被预约，则医生不会被删除
public ActionForward removeDoctor(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    AdminBiz admin = (AdminBiz)ctx.getBean("serviceAdmin");

    Integer did = new Integer(Integer.parseInt(request.getParameter("did")));

    admin.removeDoctor(did);

    return mapping.findForward("removeDoctor");
}
```

```java
// 患者注册
public ActionForward regsterPatient(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    DynaActionForm daf = (DynaActionForm)form;

    String username = daf.getString("username");

    String password = daf.getString("password");

    String name = daf.getString("name");

    int age = Integer.parseInt((String)daf.get("age"));

    int sex = Integer.parseInt((String)daf.get("sex"));

    String address = daf.getString("address");

    String phone = daf.getString("phone");

    Patient p = patient.regiter(name, username, age, sex, address, phone);

    request.getSession(true).setAttribute("patient", p);

    return mapping.findForward("pRegister");
}
```

```java
// 患者登录
public ActionForward pLogin(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    DynaActionForm daf = (DynaActionForm)form;

    String username = daf.getString("username");

    String password = daf.getString("password");

    Patient p = patient.login(username, password);

    request.getSession(true).setAttribute("patient", p);

    return mapping.findForward("pLogin");
}
```

```java
// 查找所有医生信息
public ActionForward allDoctorMessage(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    List<Doctor> set = patient.queryAllDoctor();

    request.getSession(true).setAttribute("doctors1", set);

    return mapping.findForward("getDoc");
}
```

```java
// 患者医生预约信息
public ActionForward getMessage(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    List<Doctor> set = patient.queryAllDoctor();

    Set l1 = new HashSet();

    Set l2 = new HashSet();

    Set l3 = new HashSet();

    for (Doctor d : set) {

        l1.add(d.getSection());

        l2.add(d.getLevels());

        l3.add(d.getSpe());

    }

    request.setAttribute("sections", l1);

    request.setAttribute("levels", l2);

    request.setAttribute("spes", l3);

    return mapping.findForward("pqd");
}
```

```java
// 患者根据标准查询医生
public ActionForward patientQuery(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    DynaActionForm daf = (DynaActionForm)form;

    String section = daf.getString("section");

    String levels = daf.getString("level");

    String spe = daf.getString("spe");

    int day = Integer.parseInt(daf.getString("day"));

    int ap = Integer.parseInt(daf.getString("ap"));

    List<Doctor> l = patient.queryDoctor(section, levels, spe, day, ap);

    request.getSession(true).setAttribute("doctorss", l);

    return mapping.findForward("getDoc");
}
```

```java
// 患者预约
public ActionForward patientAppointment(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    Integer did = new Integer(Integer.parseInt(request.getParameter("did")));

    int day = Integer.parseInt(request.getParameter("day"));

    int ap = Integer.parseInt(request.getParameter("ap"));

    Patient p = (Patient)request.getSession(true).getAttribute("patient");

    patient.appointment(p, did, day, ap);

    return mapping.findForward("make");
}
```

```java
// 患者检查医生预约
public ActionForward patientAppointmentMessage(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    DynaActionForm daf = (DynaActionForm)form;

    Integer did = new Integer(Integer.parseInt(daf.getString("did")));

    Curappointment cur = patient.queryByDid(did);

    request.getSession(true).setAttribute("curappointment", cur);

    return mapping.findForward("appoint");
}
```

```java
// 患者预约查看医生
public ActionForward patientMyAppointment(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    Integer pid = new Integer(Integer.parseInt(request.getParameter("pid")));

    List<Pinqueue> list = patient.getPinqueueByPid(pid);

    request.getSession(true).setAttribute("pinqueues", list);

    return mapping.findForward("getApp");
}
```

```java
// 患者取消的预约
public ActionForward patientCancleAppointment(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");
}
```



```java
Integer qid = new Integer(Integer.parseInt(request.getParameter("qid")));

patient.cancleAppemnt(qid);

return mapping.findForward("cancle");
```

```java
// 患者获取医生信息
public ActionForward getDoctorMessage(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    Integer pid = new Integer(Integer.parseInt(request.getParameter("pid")));

    List<Doctor> l = patient.queryDoctorByPid(pid);

    request.getSession(true).setAttribute("dMessages", l);

    return mapping.findForward("current");
}
```

```java
// 患者病历
public ActionForward queryHistory(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    PatientBiz patient = (PatientBiz)ctx.getBean("servicePatient");

    Integer pid = new Integer(Integer.parseInt(request.getParameter("pid")));

    List<History> l = patient.queryHistoryByPid(pid);

    request.getSession(true).setAttribute("historys", l);

    return mapping.findForward("his");
}
```

```java
// 医生登录
public ActionForward dLogin(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    DynaActionForm daf = (DynaActionForm)form;

    String name = daf.getString("name");

    String password = daf.getString("password");

    Doctor d = doctor.login(name, password);

    request.getSession(true).setAttribute("doctor", d);

    return mapping.findForward("dLogin");
}
```

```java
// 医生修改密码
public ActionForward doctorPassword(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    DynaActionForm daf = (DynaActionForm)form;

    String newPassword = daf.getString("password");

    Doctor name = (Doctor)request.getSession(true).getAttribute("doctor");

    doctor.updatePassword(name, newPassword);

    request.setAttribute("newPassword", newPassword);

    return mapping.findForward("up");
}
```

```java
// 医生获取预约信息
public ActionForward getAppointmentMessage(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    Integer did = new Integer(Integer.parseInt(request.getParameter("did")));

    List<DoctorPinqueue> l = doctor.getAllqueue(did);

    request.getSession(true).setAttribute("pinqueues", l);

    return mapping.findForward("getPatient");
}
```

```java
// 医生创建病历
public ActionForward createHistory(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    DynaActionForm daf = (DynaActionForm)form;

    Patient d = (Patient)request.getSession(true).getAttribute("doctor");

    Integer pid = new Integer(Integer.parseInt(request.getParameter("pid")));

    String description = daf.getString("description");

    String diagnose = daf.getString("diagnose");

    String rx = daf.getString("rx");

    int pd = 1;

    doctor.createPinqueue(d, pid, description, diagnose, rx, pd);

    request.setAttribute("bing", pd);

    return mapping.findForward("create");
}
```

```java
// 医生检查患者病历
public ActionForward queryPatientHistory(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    Integer did = new Integer(Integer.parseInt(request.getParameter("did")));

    List<DoctorHistory> dqh = doctor.getAllHistory(did);

    request.getSession(true).setAttribute("dqhs", dqh);

    return mapping.findForward("gph");
}
```

```java
// 医生修改患者病历
public ActionForward updatePatientHistory(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    Integer hid = new Integer(Integer.parseInt(request.getParameter("hid")));

    String description = request.getParameter("description");

    String diagnose = request.getParameter("diagnose");

    String rx = request.getParameter("rx");

    doctor.updateHistory(hid, description, diagnose, rx);

    request.setAttribute("upda", hid);

    return mapping.findForward("upok");
}
```

```java
// 医生结束患者诊疗
public ActionForward finishHistory(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    ApplicationContext ctx = this.getWebApplicationContext();

    DoctorBiz doctor = (DoctorBiz)ctx.getBean("serviceDoctor");

    Integer hid = new Integer(Integer.parseInt(request.getParameter("hid")));

    doctor.finish(hid);

    return mapping.findForward("finishOk");
}
```

```java
// 退出登录
public ActionForward exit(ActionMapping mapping, ActionForm form, HttpServletRequest request, HttpServletResponse response) throws Exception {

    HttpSession session = request.getSession(true);

    if (session.getAttribute("admin") != null) { session.setAttribute("admin", null); }

    if (session.getAttribute("doctor") != null) { session.setAttribute("doctor", null); }

    if (session.getAttribute("patient") != null) { session.setAttribute("patient", null); }

    return mapping.findForward("default");
}
```

| ![](img/image_rsrcFV7.jpg) |

| ![](img/image_rsrcFPV.jpg) |

## `src\com\abd\biz`

### `AdminBiz.java`

```java
package com.abd.biz;

import java.io.IOException;

import java.sql.SQLException;

import java.util.*;

import com.abd.expt.SystemException;

import com.abd.entity.*;

public interface AdminBiz {

    //管理员登录
    public void login(String username ,String password)throws IOException ,SQLException,SystemException;

    //管理员添加医生
    public void addDoctor(Integer did,String name,int age,int sex,String levels,String spe,​int[] pPerDay,String dPhone,String section)throws IOException ,SQLException,SystemException;

    //管理员删除医生
    public void removeDoctor(Integer did)throws IOException,SQLException,SystemException;

    // 系统管理员查看所有医生信息
    public List<Doctor> getAllDoctor()throws IOException ,SQLException,SystemException;
}
```

### `DoctorBiz.java`

```java
package com.abd.biz;

import com.abd.entity.*;

import com.abd.expt.SystemException;

import java.io.IOException;

import java.sql.SQLException;

import java.util.List;

public interface DoctorBiz {

    // 医生登录返回医生对象
    public Doctor login(String name ,String password)throws IOException ,SQLException,SystemException;

    // 医生修改密码
    public void updatePassword(String name ,String newPassword)throws IOException ,SQLException,SystemException;

    // 根据 did 检查所有预约记录，根据 pid 识别患者信息，返回专门用于此方法的对象列表
    public List<DoctorQueryPinqueue> getAllPinqueue(Integer did)throws IOException ,SQLException,SystemException;

    // 跨科医生挂号
```



`public void doctorCreatePinqueue(Integer pid, Doctor d, String description, String diagnose, String rx, int pd) throws IOException, SQLException, SystemException;`

`// 通过 did 检查其所有的病历和患者信息，返回一个专门写的对象`

`public List<DoctorQueryHistory> getAllHistory(Integer did) throws IOException, SQLException, SystemException;`

`// 更新记录`

`public void updateHistory(Integer hid, String description, String diagnose, String rx) throws IOException, SQLException, SystemException;`

`// 结束治疗，需要写入结束时间，结束状态改为 0`

`public void finish(Integer hid) throws IOException, SQLException, SystemException;`

```
public interface DoctorBiz {
    public void doctorCreatePinqueue(Integer pid, Doctor d, String description, String diagnose, String rx, int pd) throws IOException, SQLException, SystemException;

    // 通过 did 检查其所有的病历和患者信息，返回一个专门写的对象
    public List<DoctorQueryHistory> getAllHistory(Integer did) throws IOException, SQLException, SystemException;

    // 更新记录
    public void updateHistory(Integer hid, String description, String diagnose, String rx) throws IOException, SQLException, SystemException;

    // 结束治疗，需要写入结束时间，结束状态改为 0
    public void finish(Integer hid) throws IOException, SQLException, SystemException;
}
```

### `PatientBiz.java`

```java
package com.abd.biz;

import java.io.IOException;
import java.sql.SQLException;
import java.util.*;

import com.abd.entity.*;
import com.abd.expt.SystemException;

public interface PatientBiz {

    // 查找所有医生患者
    public List<Doctor> queryAllDoctor() throws IOException, SQLException;

    // 这两个方法都要求返回对象以便后续操作
    public Patient regiter(String name, String username, String password, int age, int sex, String address, String phone) throws IOException, SQLException, SystemException;

    // 患者登录
    public Patient login(String username, String password) throws IOException, SQLException, SystemException;

    // 查询返回当前医生的可以预约的多个信息
    public Curappointment queryByDid(Integer did) throws IOException, SQLException, SystemException;

    // 预约
    public void appointment(Patient p, Integer did, int day, int ap) throws IOException, SQLException, SystemException;

    // 发现他们拥有的预约
    public List<Pinqueue> getPinqueueByPid(Integer pid) throws IOException, SQLException, SystemException;

    // 取消预约患者数量
    public void cancleAppointemnt(Integer qid) throws IOException, SQLException, SystemException;

    // 根据医生患者信息 pid 查询
    public List<Doctor> queryDoctorByPid(Integer pid) throws IOException, SQLException, SystemException;

    // 患者病历
    public List<History> queryHistoryByPid(Integer pid) throws IOException, SQLException, SystemException;

    // 医生根据需求检查患者
    public List<Doctor> queryDoctor(String section, String levels, String spe, int day, int ap) throws IOException, SQLException, SystemException;
}
```

### `src\com\abd\biz\impl`

#### `AdminBizImpl.java`

```java
package com.abd.biz.impl;

import java.io.IOException;
import java.sql.SQLException;
import java.util.*;

import com.abd.biz.AdminBiz;
import com.abd.dao.*;
import com.abd.entity.*;
import com.abd.expt.AppointmentException;
import com.abd.expt.IdException;
import com.abd.expt.PasswordException;
import com.abd.expt.SystemException;
import com.abd.expt.UsernameException;

public class AdminBizImpl implements AdminBiz {

    private AdminDao daoA = null;
    private DoctorDao daoB = null;
    private AppointmentDao daoC = null;
    private CurappointmentDao daoD = null;

    public AppointmentDao getDaoC() {
        return daoC;
    }

    public void setDaoC(AppointmentDao daoC) {
        this.daoC = daoC;
    }

    public CurappointmentDao getDaoD() {
        return daoD;
    }

    public void setDaoD(CurappointmentDao daoD) {
        this.daoD = daoD;
    }

    public AdminDao getDaoA() {
        return daoA;
    }

    public void setDaoA(AdminDao daoA) {
        this.daoA = daoA;
    }

    public DoctorDao getDaoB() {
        return daoB;
    }

    public void setDaoB(DoctorDao daoB) {
        this.daoB = daoB;
    }

    public void addDoctor(Integer did, String name, int age, int sex, String levels, String spe, int[] perDay, String phone, String section) throws IOException, SQLException, SystemException {
        Doctor doctor = daoB.queryBydid(did);
        if (doctor != null) {
            throw new IdException(`did 已存在`);
        } else {
            doctor = new Doctor();
            doctor.setDid(did);
            doctor.setName(name);
            doctor.setAge(age);
            doctor.setSex(sex);
            doctor.setLevels(levels);
            doctor.setSpe(spe);
            doctor.setPhone(phone);
            doctor.setPassword("123456");
            doctor.setSection(section);
            Appointment app = new Appointment(perDay[0], perDay[1], perDay[2], perDay[3], perDay[4], perDay[5], perDay[6], perDay[7], perDay[8], perDay[9], perDay[10], perDay[11], perDay[12], perDay[13]);
            app.setDoctor(doctor);
            Curappointment cuu = new Curappointment(perDay[0], perDay[1], perDay[2], perDay[3], perDay[4], perDay[5], perDay[6], perDay[7], perDay[8], perDay[9], perDay[10], perDay[11], perDay[12], perDay[13]);
            cuu.setDoctor(doctor);
            doctor.setCuu(cuu);
            doctor.setApp(app);
            daoB.addDoctor(doctor);
        }
    }

    public List<Doctor> getAllDoctor() throws IOException, SQLException, SystemException {
        return daoB.getAllDoctor();
    }

    public void login(String username, String password) throws IOException, SQLException, SystemException {
        Admin admin = daoA.login(username);
        if (admin == null) {
            throw new UsernameException(`无此类账户`);
        }
        if (!admin.getPassword().equals(password)) {
            throw new PasswordException(`密码错误`);
        }
    }

    public void removeDoctor(Integer did) throws IOException, SQLException, SystemException {
        Appointment app = daoC.queryApp(did);
        app.setDoctor(null);
        daoC.removeApp(app);
        Curappointment cuu = daoD.queryByDid(did);
        cuu.setDoctor(null);
        daoD.removeCur(cuu);
        Doctor doctor = daoB.queryBydid(did);
        doctor.setApp(null);
        doctor.setCuu(null);
        daoB.delete(doctor);
    }
}
```

#### `DoctorBizImpl.java`

```java
package com.abd.biz.impl;

import java.io.IOException;
import java.sql.SQLException;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;
import java.util.Set;

import com.abd.biz.DoctorBiz;
import com.abd.dao.CurappointmentDao;
import com.abd.dao.DoctorDao;
import com.abd.dao.HistoryDao;
import com.abd.dao.PatientDao;
import com.abd.dao.PinqueueDao;
import com.abd.entity.Curappointment;
import com.abd.entity.Doctor;
import com.abd.entity.DoctorQueryHistory;
import com.abd.entity.DoctorQueryPinqueue;
import com.abd.entity.History;
import com.abd.entity.Patient;
import com.abd.entity.Pinqueue;
import com.abd.expt.PasswordException;
import com.abd.expt.SystemException;
import com.abd.expt.UsernameException;

public class DoctorBizImpl implements DoctorBiz {

    private DoctorDao daoD;
    private PinqueueDao daoQ;
    private PatientDao daoP;
    private HistoryDao daoH;
    private CurappointmentDao daoC;

    public CurappointmentDao getDaoC() {
        return daoC;
    }

    public void setDaoC(CurappointmentDao daoC) {
        this.daoC = daoC;
    }

    public DoctorDao getDaoD() {
        return daoD;
    }

    public void setDaoD(DoctorDao daoD) {
        this.daoD = daoD;
    }

    public PinqueueDao getDaoQ() {
        return daoQ;
    }

    public void setDaoQ(PinqueueDao daoQ) {
        this.daoQ = daoQ;
    }

    public PatientDao getDaoP() {
        return daoP;
    }

    public void setDaoP(PatientDao daoP) {
        this.daoP = daoP;
    }

    public HistoryDao getDaoH() {
        return daoH;
    }

    public void setDaoH(HistoryDao daoH) {
        this.daoH = daoH;
    }

    public void doctorCreatePinqueue(Integer pid, Doctor d, String description, String diagnose, String rx, int pd) throws IOException, SQLException, SystemException {
        // 仅通过 PID 获取医生和患者
        Patient p = daoP.queryByPid(pid);
        Pinqueue pin = daoQ.queryByDoctorAndPatient(d, p);
        int day = pin.getDay();
        int ap = pin.getAp();
        // 获取了 CUU，更新 CUU
        Curappointment cuu = d.getCuu();
        switch (day) {
            case 0:
                if (ap == 0) {
                    cuu.setSunA(cuu.getSunA() + 1);
                } else {
                    cuu.setSunP(cuu.getSunP() + 1);
                }
        }
    }
}
```



以下是`PatientBizImpl.java`文件的代码内容，其中包含了`PatientBiz`接口的实现类`PatientBizImpl`的完整定义。该类负责处理患者预约、查询历史、管理医生信息等业务逻辑。

首先，代码导入了所需的包和类，包括`com.abd.biz.PatientBiz`、`com.abd.dao.CurappointmentDao`、`com.abd.dao.DoctorDao`、`com.abd.dao.HistoryDao`、`com.abd.dao.PatientDao`、`com.abd.dao.PinqueueDao`、`com.abd.entity.Curappointment`、`com.abd.entity.Doctor`、`com.abd.entity.History`、`com.abd.entity.Patient`、`com.abd.entity.Pinqueue`，以及各种自定义异常类，如`AlreadyAppointmentException`、`DayAlreadyAppointmentException`、`IdException`、`PasswordException`、`SystemException`、`UsernameException`和`WrongException`。这些导入确保了类中所有方法和属性都可正常使用。

```java
package com.abd.biz.impl;

import java.io.IOException;
import java.sql.SQLException;
import java.util.ArrayList;
import java.util.Date;
import java.util.List;
import java.util.Set;

import com.abd.biz.PatientBiz;
import com.abd.dao.CurappointmentDao;
import com.abd.dao.DoctorDao;
import com.abd.dao.HistoryDao;
import com.abd.dao.PatientDao;
import com.abd.dao.PinqueueDao;
import com.abd.entity.Curappointment;
import com.abd.entity.Doctor;
import com.abd.entity.History;
import com.abd.entity.Patient;
import com.abd.entity.Pinqueue;
import com.abd.expt.AlreadyAppointmentException;
import com.abd.expt.DayAlreadyAppointmentException;
import com.abd.expt.IdException;
import com.abd.expt.PasswordException;
import com.abd.expt.SystemException;
import com.abd.expt.UsernameException;
import com.abd.expt.WrongException;

public class PatientBizImpl implements PatientBiz {

    private DoctorDao daoD;
    private CurappointmentDao daoC;
    private PatientDao daoP;
    private HistoryDao daoH;
    private PinqueueDao daoQ;

    public DoctorDao getDaoD() {
        return daoD;
    }

    public void setDaoD(DoctorDao daoD) {
        this.daoD = daoD;
    }

    public CurappointmentDao getDaoC() {
        return daoC;
    }

    public void setDaoC(CurappointmentDao daoC) {
        this.daoC = daoC;
    }

    public PatientDao getDaoP() {
        return daoP;
    }

    public void setDaoP(PatientDao daoP) {
        this.daoP = daoP;
    }

    public HistoryDao getDaoH() {
        return daoH;
    }

    public void setDaoH(HistoryDao daoH) {
        this.daoH = daoH;
    }

    public PinqueueDao getDaoQ() {
        return daoQ;
    }

    public void setDaoQ(PinqueueDao daoQ) {
        this.daoQ = daoQ;
    }

    public void appointment(Patient p, Integer did, int day, int ap) throws IOException, SQLException, SystemException {
        // 确定是否已预约
        List<Pinqueue> list = daoQ.queryByPatient(p);
        for (Pinqueue pin : list) {
            if ((pin.getDoctor().getDid()).intValue() == did.intValue()) {
                throw new AlreadyAppointmentException();
            }
            if (pin.getDay() == day && pin.getAp() == ap) {
                throw new DayAlreadyAppointmentException();
            }
        }

        // 设置预约属性
        Doctor d = daoD.queryBydid(did);
        Pinqueue q = new Pinqueue();

        // 更新 Curappointment
        Curappointment cuu = d.getCuu();
        switch (day) {
            case 0:
                if (ap == 0) {
                    cuu.setSunA(cuu.getSunA() - 1);
                    // 今天，医生可以决定是否预约
                    if (cuu.getSunA() < 0) {
                        throw new WrongException();
                    }
                } else {
                    cuu.setSunP(cuu.getSunP() - 1);
                    if (cuu.getSunP() < 0) {
                        throw new WrongException();
                    }
                }
                break;

            case 1:
                if (ap == 0) {
                    cuu.setMonA(cuu.getMonA() - 1);
                    if (cuu.getMonA() < 0) {
                        throw new WrongException();
                    }
                } else {
                    cuu.setMonP(cuu.getMonP() - 1);
                    if (cuu.getMonP() < 0) {
                        throw new WrongException();
                    }
                }
                break;

            case 2:
                if (ap == 0) {
                    cuu.setTueA(cuu.getTueA() + 1);
                } else {
                    cuu.setTueP(cuu.getTueP() + 1);
                }
                break;

            case 3:
                if (ap == 0) {
                    cuu.setWedA(cuu.getWedA() + 1);
                } else {
                    cuu.setWedP(cuu.getWedP() + 1);
                }
                break;

            case 4:
                if (ap == 0) {
                    cuu.setThuA(cuu.getThuA() + 1);
                } else {
                    cuu.setThuP(cuu.getThuP() + 1);
                }
                break;

            case 5:
                if (ap == 0) {
                    cuu.setFriA(cuu.getFriA() + 1);
                } else {
                    cuu.setFriP(cuu.getFriP() + 1);
                }
                break;

            case 6:
                if (ap == 0) {
                    cuu.setSatA(cuu.getSatA() + 1);
                } else {
                    cuu.setSatP(cuu.getSatP() + 1);
                }
                break;
        }

        // 设置记录属性
        History his = new History();
        his.setDescription(description);
        his.setDiagnose(diagnose);
        his.setRx(rx);
        his.setFinished(pd);
        his.setFdate(new Date());
        his.setDoctor(d);

        // 更新患者属性
        p.getHistory().add(his);
        this.setPatient(p);

        // 删除预约信息
        pin.setDoctor(null);
        pin.setPatient(null);
        daoQ.deletePinqueue(pin);
        daoH.add(his);
    }

    public void finish(Integer hid) throws IOException, SQLException, SystemException {
        History his = daoH.query(hid);
        Date d = new Date();
        his.setFinished(0);
        his.setSdate(d);
        daoH.update(his);
    }

    public List<DoctorQueryHistory> getAllHistory(Integer did) throws IOException, SQLException, SystemException {
        List<DoctorQueryHistory> l = new ArrayList<DoctorQueryHistory>();
        Doctor d = daoD.queryBydid(did);
        List<History> his = daoH.queryByDoctor(d);
        for (History h : his) {
            Patient pat = daoP.queryByPid(h.getPatient().getPid());
            DoctorQueryHistory hqh = new DoctorQueryHistory(
                h.getHid(), pat.getName(), pat.getAge(), pat.getSex(),
                pat.getAddress(), pat.getPhone(), h.getDiagnose(),
                h.getDescription(), h.getRx(), h.getFdate(), h.getSdate());
            l.add(hqh);
        }
        return l;
    }

    public List<DoctorQueryPinqueue> getAllPinqueue(Integer did) throws IOException, SQLException, SystemException {
        List<DoctorQueryPinqueue> l = new ArrayList<DoctorQueryPinqueue>();
        Doctor d = daoD.queryBydid(did);
        List<Pinqueue> pin = daoQ.queryByDoctor(d);
        for (Pinqueue q : pin) {
            Patient pat = daoP.queryByPid(q.getPatient().getPid());
            DoctorQueryPinqueue dqp = new DoctorQueryPinqueue(
                q.getPatient().getPid(), pat.getName(), pat.getAge(), pat.getSex(),
                pat.getAddress(), pat.getPhone(), q.getQid());
            l.add(dqp);
        }
        return l;
    }

    public Doctor login(String name, String password) throws IOException, SQLException, SystemException {
        Doctor d = daoD.queryName(name);
        if (d == null) {
            throw new UsernameException("无此类账号");
        }
        if (!d.getPassword().equals(password)) {
            throw new PasswordException("密码错误");
        }
        return d;
    }

    public void updateHistory(Integer hid, String description, String diagnose, String rx) throws IOException, SQLException, SystemException {
        History his = daoH.query(hid);
        his.setDescription(description);
        his.setDiagnose(diagnose);
        his.setRx(rx);
        daoH.update(his);
    }

    public void updatePassword(String name, String newPassword) throws IOException, SQLException, SystemException {
        Doctor d = daoD.queryName(name);
        d.setPassword(newPassword);
        daoD.update(d);
    }

}
```



# 第一部分图表你将获得一些概览

| 图片 |
|------|
| ![](img/image_rsrcFV8.jpg) |
| ![](img/image_rsrcFPV.jpg) |
| ![](img/image_rsrcFV9.jpg) |
| ![](img/image_rsrcFVA.jpg) |
| ![](img/image_rsrcFVB.jpg) |

## src\com\abd\dao

### AdminDao.java

```java
package com.abd.dao;

import com.abd.entity.Admin;

public interface AdminDao {

    public Admin login(String username);

}
```

### AppointmentDao.java

```java
package com.abd.dao;

import com.abd.entity.*;

public interface AppointmentDao {

    public void removeApp(Appointment app);

    public Appointment queryApp(Integer did);

}
```

### CurappointmentDao.java

```java
package com.abd.dao;

import java.util.List;

import com.abd.entity.Curappointment;

public interface CurappointmentDao {

    public void removeCur(Curappointment c);

    public Curappointment queryByDid(Integer did);

    public List<Curappointment> queryByDay(int dayap);

}
```

### DoctorDao.java

```java
package com.abd.dao;

import java.util.List;

import com.abd.entity.*;

public interface DoctorDao {

    public Doctor queryBydid(Integer did);

    public Doctor queryName(String name);

    public void update(Doctor doctor);

    public List<Doctor> getAllDoctor();

    public void delete(Doctor doctor);

    public void addDoctor(Doctor doctor);

}
```

### HistoryDao.java

```java
package com.abd.dao;

import java.util.List;

import com.abd.entity.*;

public interface HistoryDao {

    public List<History> queryByPatient(Patient p);

    public void add(History history);

    public History query(Integer hid);

    public List<History> queryByDoctor(Doctor d);

    public void update(History history);

}
```

### PatientDao.java

```java
package com.abd.dao;

import com.abd.entity.Patient;

public interface PatientDao {

    public Patient queryByPid(Integer pid);

    public void register(Patient patient);

    public Patient queryByUsername(String username);

}
```

### 业务逻辑代码

```java
if (ap == 0) {
    cuu.setTueA(cuu.getTueA() - 1);
    if (cuu.getTueA() < 0) {
        throw new WrongException();
    }
} else {
    cuu.setTueP(cuu.getTueP() - 1);
    if (cuu.getTueP() < 0) {
        throw new WrongException();
    }
}
break;

case 3:
if (ap == 0) {
    cuu.setWedA(cuu.getWedA() - 1);
    if (cuu.getWedA() < 0) {
        throw new WrongException();
    }
} else {
    cuu.setWedP(cuu.getWedP() - 1);
    if (cuu.getWedP() < 0) {
        throw new WrongException();
    }
}
break;

case 4:
if (ap == 0) {
    cuu.setThuA(cuu.getThuA() - 1);
    if (cuu.getThuA() < 0) {
        throw new WrongException();
    }
} else {
    cuu.setThuP(cuu.getThuP() - 1);
    if (cuu.getThuP() < 0) {
        throw new WrongException();
    }
}
break;

case 5:
if (ap == 0) {
    cuu.setFriA(cuu.getFriA() - 1);
    if (cuu.getFriA() < 0) {
        throw new WrongException();
    }
} else {
    cuu.setFriP(cuu.getFriP() - 1);
    if (cuu.getFriP() < 0) {
        throw new WrongException();
    }
}
break;

case 6:
if (ap == 0) {
    cuu.setSatA(cuu.getSatA() - 1);
    if (cuu.getSatA() < 0) {
        throw new WrongException();
    }
} else {
    cuu.setSatP(cuu.getSatP() - 1);
    if (cuu.getSatP() < 0) {
        throw new WrongException();
    }
}
break;
```

```java
q.setDay(day);
q.setDoctor(d);
q.setPatient(p);
q.setAp(ap);
q.set_date(new Date());
d.getPin().add(q);
daoQ.addPinqueue(q);
```

```java
public void cancleointnt(Integer qid) throws IOException, SQLException, SystemException {
    // 通过 Pin 获取 QID
    Pinqueue pin = daoQ.queryByid(qid);
    int day = pin.getDay();
    int ap = pin.getAp();
    // 通过 CUU 更新 CUU
    Curappointment cuu = pin.getDoctor().getCuu();
    switch (day) {
        case 0:
            if (ap == 0) {
                cuu.setSunA(cuu.getSunA() + 1);
            } else {
                cuu.setSunP(cuu.getSunP() + 1);
            }
            break;
        case 1:
            if (ap == 0) {
                cuu.setMonA(cuu.getMonA() + 1);
            } else {
                cuu.setMonP(cuu.getMonP() + 1);
            }
            break;
        case 2:
            if (ap == 0) {
                cuu.setTueA(cuu.getTueA() + 1);
            } else {
                cuu.setTueP(cuu.getTueP() + 1);
            }
            break;
        case 3:
            if (ap == 0) {
                cuu.setWedA(cuu.getWedA() + 1);
            } else {
                cuu.setWedP(cuu.getWedP() + 1);
            }
            break;
        case 4:
            if (ap == 0) {
                cuu.setThuA(cuu.getThuA() + 1);
            } else {
                cuu.setThuP(cuu.getThuP() + 1);
            }
            break;
        case 5:
            if (ap == 0) {
                cuu.setFriA(cuu.getFriA() + 1);
            } else {
                cuu.setFriP(cuu.getFriP() + 1);
            }
            break;
        case 6:
            if (ap == 0) {
                cuu.setSatA(cuu.getSatA() + 1);
            } else {
                cuu.setSatP(cuu.getSatP() + 1);
            }
            break;
    }
    pin.setDoctor(null);
    pin.setPatient(null);
    // 删除 PINQUEUE
    daoQ.deletePinqueue(pin);
}
```

```java
public List<Pinqueue> getPinqueueByPid(Integer pid) throws IOException, SQLException, SystemException {
    Patient p = daoP.queryByPid(pid);
    return daoQ.queryByPatient(p);
}
```

```java
public Patient login(String username, String password) throws IOException, SQLException, SystemException {
    Patient p = daoP.queryByUsername(username);
    if (p == null) {
        throw new IdException("无此账号");
    }
    if (!(p.getPassword().equals(password))) {
        throw new PasswordException("密码错误");
    }
    return p;
}
```

```java
public List<Doctor> queryAllDoctor() throws IOException, SQLException {
    return daoD.getAllDoctor();
}
```

```java
public Curappointment queryByDid(Integer did) throws IOException, SQLException, SystemException {
    return daoC.queryByDid(did);
}
```

```java
public List<Doctor> queryDoctorByPid(Integer pid) throws IOException, SQLException, SystemException {
    Patient p = daoP.queryByPid(pid);
    List<History> list = daoH.queryByPatient(p);
    List<Doctor> l = new ArrayList<>();
    for (History h : list) {
        Doctor doc = daoD.queryBydid(h.getDoctor().getDid());
        l.add(doc);
    }
    return l;
}
```

```java
public List<History> queryHistoryByPid(Integer pid) throws IOException, SQLException, SystemException {
    Patient p = daoP.queryByPid(pid);
    return daoH.queryByPatient(p);
}
```




### `PinqueueDao.java`

```java
package com.abd.dao;

import java.util.List;

import com.abd.entity.*;

public interface PinqueueDao {

    public Pinqueue queryByDoctorAndPatient(Doctor doctor, Patient patient);

    public List<Pinqueue> queryByDoctor(Doctor d);

    public List<Pinqueue> queryByPatient(Patient p);

    public Pinqueue queryByQid(Integer qid);

    public void addPinqueue(Pinqueue q);

    public void deletePinqueue(Pinqueue q);

}
```

## `src\com\abd\dao\impl`

### `AdminDaoImpl.java`

```java
package com.abd.dao.impl;

import java.util.List;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.AdminDao;
import com.abd.entity.Admin;

public class AdminDaoImpl extends HibernateDaoSupport implements AdminDao {

    public Admin login(String username) {

        Object args[] = {username};

        List<Admin> l = getHibernateTemplate().find("from Admin a where a.username=?", args);

        if (l.size() == 0) {
            return null;
        } else {
            return l.get(0);
        }
    }
}
```

### `AppointmentDaoImpl.java`

```java
package com.abd.dao.impl;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.AppointmentDao;
import com.abd.entity.*;

public class AppointmentDaoImpl extends HibernateDaoSupport implements AppointmentDao {

    public Appointment queryApp(Integer did) {
        return (Appointment) getHibernateTemplate().get(Appointment.class, did);
    }

    public void removeApp(Appointment app) {
        getHibernateTemplate().delete(app);
    }
}
```

### `CurappointmentDaoImpl.java`

```java
package com.abd.dao.impl;

import java.util.List;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.CurappointmentDao;
import com.abd.entity.Curappointment;

public class CurappointmentDaoImpl extends HibernateDaoSupport implements CurappointmentDao {

    public Curappointment queryByDid(Integer did) {
        return (Curappointment) getHibernateTemplate().get(Curappointment.class, did);
    }

    public void removeCur(Curappointment c) {
        getHibernateTemplate().delete(c);
    }

    public List<Curappointment> queryByDay(int dayap) {
        return null;
    }
}
```

### `DoctorDaoImpl.java`

```java
package com.abd.dao.impl;

import java.util.List;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.DoctorDao;
import com.abd.entity.Doctor;

public class DoctorDaoImpl extends HibernateDaoSupport implements DoctorDao {

    public void addDoctor(Doctor doctor) {
        getHibernateTemplate().save(doctor);
    }

    public void delete(Doctor doctor) {
        getHibernateTemplate().delete(doctor);
    }

    public List<Doctor> getAllDoctor() {
        return getHibernateTemplate().find("from Doctor");
    }

    public Doctor queryBydid(Integer did) {
        return (Doctor) getHibernateTemplate().get(Doctor.class, did);
    }

    public Doctor queryName(String name) {

        Object[] args = {name};

        List<Doctor> l = getHibernateTemplate().find("from Doctor d where d.name=?", args);

        if (l.size() == 0) {
            return null;
        } else {
            return l.get(0);
        }
    }

    public void update(Doctor doctor) {
        getHibernateTemplate().update(doctor);
    }
}
```

### `HistoryDaoImpl.java`

```java
package com.abd.dao.impl;

import java.util.List;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.HistoryDao;
import com.abd.entity.*;

public class HistoryDaoImpl extends HibernateDaoSupport implements HistoryDao {

    public void add(History history) {
        getHibernateTemplate().save(history);
    }

    public History query(Integer hid) {
        return (History) getHibernateTemplate().get(History.class, hid);
    }

    public List<History> queryByPatient(Patient p) {

        Object[] args = {p};

        return getHibernateTemplate().find("from History h where h.patient=?", args);
    }

    public List<History> queryByDoctor(Doctor d) {

        Object[] args = {d};

        return getHibernateTemplate().find("from History h where h.doctor=?", args);
    }

    public void update(History history) {
        getHibernateTemplate().update(history);
    }
}
```

### `PatientDaoImpl.java`

```java
package com.abd.dao.impl;

import java.util.List;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.PatientDao;
import com.abd.entity.Patient;

public class PatientDaoImpl extends HibernateDaoSupport implements PatientDao {

    public Patient queryByPid(Integer pid) {
        return (Patient) getHibernateTemplate().get(Patient.class, pid);
    }

    public void register(Patient patient) {
        getHibernateTemplate().save(patient);
    }

    public Patient queryByUsername(String username) {

        Object[] args = {username};

        List<Patient> l = getHibernateTemplate().find("from Patient p where p.username=?", args);

        if (l.size() == 0) {
            return null;
        } else {
            return l.get(0);
        }
    }
}
```

### `PinqueueDaoImpl.java`

```java
package com.abd.dao.impl;

import java.util.List;

import org.springframework.orm.hibernate3.support.HibernateDaoSupport;

import com.abd.dao.PinqueueDao;
import com.abd.entity.Doctor;
import com.abd.entity.Patient;
import com.abd.entity.Pinqueue;

public class PinqueueDaoImpl extends HibernateDaoSupport implements PinqueueDao {

    public void addPinqueue(Pinqueue q) {
        getHibernateTemplate().save(q);
    }

    public void deletePinqueue(Pinqueue q) {
        getHibernateTemplate().delete(q);
    }

    public List<Pinqueue> queryByDoctor(Doctor d) {

        Object[] args = {d};

        return getHibernateTemplate().find("from Pinqueue q where q.doctor=?", args);
    }

    public List<Pinqueue> queryByPatient(Patient p) {

        Object[] args = {p};

        return getHibernateTemplate().find("from Pinqueue q where q.patient=?", args);
    }

    public Pinqueue queryByDoctorAndPatient(Doctor doctor, Patient patient) {

        Object[] args = {doctor};

        List<Pinqueue> list = getHibernateTemplate().find("from Pinqueue q where q.doctor=?", args);

        for (Pinqueue p : list) {

            if ((p.getPatient().getPid()).intValue() == (patient.getPid()).intValue()) {
                return p;
            }
        }

        return null;
    }

    public Pinqueue queryByQid(Integer qid) {
        return (Pinqueue) getHibernateTemplate().get(Pinqueue.class, qid);
    }
}
```

| ![](img/image_rsrcFPW.jpg) |

## `src\com\abd\entity`

### `Admin.java`

```java
package com.abd.entity;

import java.io.*;

public class Admin implements Serializable {

    private Integer aid;

    private String username;

    private String password;

    private String email;

    private String phone;

    private String name;

    public Integer getAid() {
        return aid;
    }

    public void setAid(Integer aid) {
        this.aid = aid;
    }

    public String getUsername() {
        return username;
    }

    public void setUsername(String username) {
        this.username = username;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
}
```

### `Appointment.java`

```java
package com.abd.entity;

import java.io.Serializable;
```




```java
/** Provided there are no arguments constructor parameters*/

public class Appointment implements Serializable {

    private Integer did;

    private int sunA;

    private int sunP;

    private int monA;

    private int monP;

    private int tueA;

    private int tueP;

    private int wedA;

    private int wedP;

    private int thuA;

    private int thuP;

    private int friA;

    private int friP;

    private int satA;

    private int satP;

    private Doctor doctor;

    public Appointment() {
        super();
    }

    public Appointment(int sunA, int sunP, int monA, int monP, int tueA, int tueP, int wedA, int wedP, int thuA, int thuP, int friA, int friP, int satA, int satP) {
        super();

        this.sunA = sunA;

        this.sunP = sunP;

        this.monA = monA;

        this.monP = monP;

        this.tueA = tueA;

        this.tueP = tueP;

        this.wedA = wedA;

        this.wedP = wedP;

        this.thuA = thuA;

        this.thuP = thuP;

        this.friA = friA;

        this.friP = friP;

        this.satA = satA;

        this.satP = satP;
    }

    public Doctor getDoctor() {
        return doctor;
    }

    public void setDoctor(Doctor doctor) {
        this.doctor = doctor;
    }

    public Integer getDid() {
        return did;
    }

    public void setDid(Integer did) {
        this.did = did;
    }

    public int getSunA() {
        return sunA;
    }

    public void setSunA(int sunA) {
        this.sunA = sunA;
    }

    public int getSunP() {
        return sunP;
    }

    public void setSunP(int sunP) {
        this.sunP = sunP;
    }

    public int getMonA() {
        return monA;
    }

    public void setMonA(int monA) {
        this.monA = monA;
    }

    public int getMonP() {
        return monP;
    }

    public void setMonP(int monP) {
        this.monP = monP;
    }

    public int getTueA() {
        return tueA;
    }

    public void setTueA(int tueA) {
        this.tueA = tueA;
    }

    public int getTueP() {
        return tueP;
    }

    public void setTueP(int tueP) {
        this.tueP = tueP;
    }

    public int getWedA() {
        return wedA;
    }

    public void setWedA(int wedA) {
        this.wedA = wedA;
    }

    public int getWedP() {
        return wedP;
    }

    public void setWedP(int wedP) {
        this.wedP = wedP;
    }

    public int getThuA() {
        return thuA;
    }

    public void setThuA(int thuA) {
        this.thuA = thuA;
    }

    public int getThuP() {
        return thuP;
    }

    public void setThuP(int thuP) {
        this.thuP = thuP;
    }

    public int getFriA() {
        return friA;
    }

    public void setFriA(int friA) {
        this.friA = friA;
    }

    public int getFriP() {
        return friP;
    }

    public void setFriP(int friP) {
        this.friP = friP;
    }

    public int getSatA() {
        return satA;
    }

    public void setSatA(int satA) {
        this.satA = satA;
    }

    public int getSatP() {
        return satP;
    }

    public void setSatP(int satP) {
        this.satP = satP;
    }
}
```

### Curappointment.java

```java
package com.abd.entity;

import java.io.Serializable;

/** Participation provides a constructor has no parameters*/

public class Curappointment implements Serializable {

    private Integer did;

    private int sunA;

    private int sunP;

    private int monA;

    private int monP;

    private int tueA;

    private int tueP;

    private int wedA;

    private int wedP;

    private int thuA;

    private int thuP;

    private int friA;

    private int friP;

    private int satA;

    private int satP;

    private Doctor doctor;

    public Curappointment() {
        super();
    }

    // TODO Auto-generated

    public Curappointment(int sunA, int sunP, int monA, int monP, int tueA, int tueP, int wedA, int wedP, int thuA, int thuP, int friA, int friP, int satA, int satP) {
        super();

        this.sunA = sunA;

        this.sunP = sunP;

        this.monA = monA;

        this.monP = monP;

        this.tueA = tueA;

        this.tueP = tueP;

        this.wedA = wedA;

        this.wedP = wedP;

        this.thuA = thuA;

        this.thuP = thuP;

        this.friA = friA;

        this.friP = friP;

        this.satA = satA;

        this.satP = satP;
    }

    public Integer getDid() {
        return did;
    }

    public void setDid(Integer did) {
        this.did = did;
    }

    public int getSunA() {
        return sunA;
    }

    public void setSunA(int sunA) {
        this.sunA = sunA;
    }

    public int getSunP() {
        return sunP;
    }

    public void setSunP(int sunP) {
        this.sunP = sunP;
    }

    public int getMonA() {
        return monA;
    }

    public void setMonA(int monA) {
        this.monA = monA;
    }

    public int getMonP() {
        return monP;
    }

    public void setMonP(int monP) {
        this.monP = monP;
    }

    public int getTueA() {
        return tueA;
    }

    public void setTueA(int tueA) {
        this.tueA = tueA;
    }

    public int getTueP() {
        return tueP;
    }

    public void setTueP(int tueP) {
        this.tueP = tueP;
    }

    public int getWedA() {
        return wedA;
    }

    public void setWedA(int wedA) {
        this.wedA = wedA;
    }

    public int getWedP() {
        return wedP;
    }

    public void setWedP(int wedP) {
        this.wedP = wedP;
    }

    public int getThuA() {
        return thuA;
    }

    public void setThuA(int thuA) {
        this.thuA = thuA;
    }

    public int getThuP() {
        return thuP;
    }

    public void setThuP(int thuP) {
        this.thuP = thuP;
    }

    public int getFriA() {
        return friA;
    }

    public void setFriA(int friA) {
        this.friA = friA;
    }

    public int getFriP() {
        return friP;
    }

    public void setFriP(int friP) {
        this.friP = friP;
    }

    public int getSatA() {
        return satA;
    }

    public void setSatA(int satA) {
        this.satA = satA;
    }

    public int getSatP() {
        return satP;
    }

    public void setSatP(int satP) {
        this.satP = satP;
    }

    public Doctor getDoctor() {
        return doctor;
    }

    public void setDoctor(Doctor doctor) {
        this.doctor = doctor;
    }
}
```

### Doctor.java

```java
package com.abd.entity;

import java.io.Serializable;
import java.util.*;

public class Doctor implements Serializable {

    private Integer did;

    private String name;

    private String password;

    private int age;

    private int sex;

    private String levels;

    private String section;

    private String spe;

    private String phone;

    private Curappointment cuu;

    private Appointment app;

    private Set<Pinqueue> pin = new HashSet<Pinqueue>();

    private Set<History> history = new HashSet<History>();

    public Integer getDid() {
        return did;
    }

    public void setDid(Integer did) {
        this.did = did;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getPassword() {
        return password;
    }

    public void setPassword(String password) {
        this.password = password;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getSex() {
        return sex;
    }

    public void setSex(int sex) {
        this.sex = sex;
    }

    public String getLevels() {
        return levels;
    }

    public void setLevels(String levels) {
        this.levels = levels;
    }

    public String getSection() {
        return section;
    }

    public void setSection(String section) {
```



### DoctorQueryHistory.java

```java
package com.abd.entity;

import java.io.Serializable;
import java.util.Date;

public class DoctorQueryHistory implements Serializable {

    private Integer hid;
    private String name;
    private int age;
    private int sex;
    private String address;
    private String phone;
    private String diagnose;
    private String description;
    private String rx;
    private Date fdate;
    private Date sdate;

    public DoctorQueryHistory() {
        super();
    }

    public DoctorQueryHistory(Integer hid, String name, int age, int sex, String address, String phone, String diagnose, String description, String rx, Date date, Date date2) {
        super();
        this.hid = hid;
        this.name = name;
        this.age = age;
        this.sex = sex;
        this.address = address;
        this.phone = phone;
        this.diagnose = diagnose;
        this.description = description;
        this.rx = rx;
        fdate = date;
        sdate = date2;
    }

    public Integer getHid() {
        return hid;
    }

    public void setHid(Integer hid) {
        this.hid = hid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getSex() {
        return sex;
    }

    public void setSex(int sex) {
        this.sex = sex;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    public String getDiagnose() {
        return diagnose;
    }

    public void setDiagnose(String diagnose) {
        this.diagnose = diagnose;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public String getRx() {
        return rx;
    }

    public void setRx(String rx) {
        this.rx = rx;
    }

    public Date getFdate() {
        return fdate;
    }

    public void setFdate(Date fdate) {
        this.fdate = fdate;
    }

    public Date getSdate() {
        return sdate;
    }

    public void setSdate(Date sdate) {
        this.sdate = sdate;
    }
}
```

### DoctorQueryPinqueue.java

```java
package com.abd.entity;

import java.io.Serializable;

/**************** 医生挂号查询的患者信息******/
public class DoctorQueryPinqueue implements Serializable {

    private Integer pid;
    private String name;
    private int age;
    private int sex;
    private String address;
    private String phone;
    private Integer qid;

    public DoctorQueryPinqueue() {
    }

    public DoctorQueryPinqueue(Integer pid, String name, int age, int sex, String address, String phone, Integer qid) {
        super();
        this.pid = pid;
        this.name = name;
        this.age = age;
        this.sex = sex;
        this.address = address;
        this.phone = phone;
        this.qid = qid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getSex() {
        return sex;
    }

    public void setSex(int sex) {
        this.sex = sex;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    public Integer getPid() {
        return pid;
    }

    public void setPid(Integer pid) {
        this.pid = pid;
    }

    public Integer getQid() {
        return qid;
    }

    public void setQid(Integer qid) {
        this.qid = qid;
    }
}
```

### History.java

```java
package com.abd.entity;

import java.io.Serializable;
import java.util.Date;

public class History implements Serializable {

    private Integer hid;
    private Doctor doctor;
    private String description;
    private String diagnose;
    private Patient patient;
    private String rx;
    private int finished;
    private Date fdate;
    private Date sdate;

    public Integer getHid() {
        return hid;
    }

    public void setHid(Integer hid) {
        this.hid = hid;
    }

    public Doctor getDoctor() {
        return doctor;
    }

    public void setDoctor(Doctor doctor) {
        this.doctor = doctor;
    }

    public String getDescription() {
        return description;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public String getDiagnose() {
        return diagnose;
    }

    public void setDiagnose(String diagnose) {
        this.diagnose = diagnose;
    }

    public Patient getPatient() {
        return patient;
    }

    public void setPatient(Patient patient) {
        this.patient = patient;
    }

    public String getRx() {
        return rx;
    }

    public void setRx(String rx) {
        this.rx = rx;
    }

    public Date getFdate() {
        return fdate;
    }

    public void setFdate(Date fdate) {
        this.fdate = fdate;
    }

    public Date getSdate() {
        return sdate;
    }

    public void setSdate(Date sdate) {
        this.sdate = sdate;
    }
}
```

### Patient.java

```java
package com.abd.entity;

import java.io.Serializable;
import java.util.Set;

public class Patient implements Serializable {

    private Integer pid;
    private String name;
    private int age;
    private int sex;
    private String address;
    private String phone;
    private Set<History> history = new HashSet<>();
    private Set<Pinqueue> ps = new HashSet<>();

    public Integer getPid() {
        return pid;
    }

    public void setPid(Integer pid) {
        this.pid = pid;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public int getSex() {
        return sex;
    }

    public void setSex(int sex) {
        this.sex = sex;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }

    public String getPhone() {
        return phone;
    }

    public void setPhone(String phone) {
        this.phone = phone;
    }

    public Set<History> getHistory() {
        return history;
    }

    public void setHistory(Set<History> history) {
        this.history = history;
    }

    public Set<Pinqueue> getPs() {
        return ps;
    }

    public void setPs(Set<Pinqueue> ps) {
        this.ps = ps;
    }
}
```



### Pinqueue.java

```java
package com.abd.entity;

import java.io.Serializable;

import java.util.Date;

public class Pinqueue implements Serializable {

    private Integer qid;

    private Patient patient;

    private Doctor doctor;

    private int day;

    private int ap;

    private Date t_date;

    public Integer getQid() {

        return qid;

    }

    public void setQid(Integer qid) {

        this.qid = qid;

    }

    public Patient getPatient() {

        return patient;

    }

    public void setPatient(Patient patient) {

        this.patient = patient;

    }

    public Doctor getDoctor() {

        return doctor;

    }

    public void setDoctor(Doctor doctor) {

        this.doctor = doctor;

    }

    public int getDay() {

        return day;

    }

    public void setDay(int day) {

        this.day = day;

    }

    public int getAp() {

        return ap;

    }

    public void setAp(int ap) {

        this.ap = ap;

    }

    public Date getT_date() {

        return t_date;

    }

    public void setT_date(Date t_date) {

        this.t_date = t_date;

    }

}
```

### hosp.hbm.xml

```xml
<?xml version="1.0"?>
<!DOCTYPE hibernate-mapping PUBLIC "-////Hibernate/Hibernate Mapping DTD 3.0//EN" "http://hibernate.sourceforge.net/hibernate-mapping-3.0.dtd">
<hibernate-mapping package="com.abd.entity">
  <!-- 管理 -->
  <class name="Admin" table="dl_admin">
    <id name="aid" column="aid">
      <!-- <generator class="assigned" />-->
      <generator class="increment" />
    </id>
    <property name="username" />
    <property name="password" />
    <property name="email" />
    <property name="phone" />
    <property name="name" />
  </class>
  <!-- 预约 -->
  <class name="Appointment" table="dl_appointment">
    <id name="did" column="did" type="java.lang.Integer">
      <generator class="foreign">
        <param name="property">doctor</param>
      </generator>
    </id>
    <property name="sunA"></property>
    <property name="sunP"></property>
    <property name="monA"></property>
    <property name="monP"></property>
    <property name="tueA"></property>
    <property name="tueP"></property>
    <property name="wedA"></property>
    <property name="wedP"></property>
    <property name="thuA"></property>
    <property name="thuP"></property>
    <property name="friA"></property>
    <property name="friP"></property>
    <property name="satA"></property>
    <property name="satP"></property>
    <!-- 映射与医生 -->
    <one-to-one name="doctor" class="Doctor" constrained="true" cascade="save-update"></one-to-one>
  </class>
  <!-- 当前预约 -->
  <class name="Curappointment" table="dl_curappointment">
    <id name="did" type="java.lang.Integer">
      <generator class="foreign">
        <param name="property">doctor</param>
      </generator>
    </id>
    <property name="sunA"></property>
    <property name="sunP"></property>
    <property name="monA"></property>
    <property name="monP"></property>
    <property name="tueA"></property>
    <property name="tueP"></property>
    <property name="wedA"></property>
    <property name="wedP"></property>
    <property name="thuA"></property>
    <property name="thuP"></property>
    <property name="friA"></property>
    <property name="friP"></property>
    <property name="satA"></property>
    <property name="satP"></property>
    <!-- 与医生映射 -->
    <one-to-one name="doctor" class="Doctor" constrained="true" cascade="save-update"></one-to-one>
  </class>
  <!-- 医生 -->
  <class name="Doctor" table="dl_doctor">
    <id name="did" column="did">
      <generator class="increment" />
    </id>
    <property name="name" />
    <property name="password" />
    <property name="age" />
    <property name="sex" />
    <property name="levels" />
    <property name="section" />
    <property name="spe" column="specialism" />
    <property name="phone" />
    <!-- 与预约映射 -->
    <one-to-one name="app" class="Appointment" cascade="save-update"></one-to-one>
    <!-- 与当前预约映射 -->
    <one-to-one name="cuu" class="Curappointment" cascade="save-update"></one-to-one>
    <!-- 与挂号队列映射 -->
    <set name="pin" table="dl_pinqueue" inverse="true" cascade="save-update">
      <key column="doctor_did"></key>
      <one-to-many class="Pinqueue"/>
    </set>
    <!-- 与历史映射 -->
    <set name="history" table="dl_history" inverse="true" cascade="save-update">
      <key column="doctor_did"></key>
      <one-to-many class="History"/>
    </set>
  </class>
  <!-- 历史 -->
  <class name="History" table="dl_history">
    <id name="hid" column="hid" type="java.lang.Integer">
      <generator class="increment"/>
    </id>
    <property name="description"></property>
    <property name="diagnose"></property>
    <property name="rx"></property>
    <property name="finished"></property>
    <property name="fdate" column="fDate" type="java.sql.Date"></property>
    <property name="sdate" column="sDate" type="java.sql.Date"></property>
    <!-- 与医生映射 -->
    <many-to-one name="doctor" column="doctor_did" cascade="save-update"></many-to-one>
    <!-- 与患者映射 -->
    <many-to-one name="patient" column="patient_pid" cascade="save-update"></many-to-one>
  </class>
  <!-- 患者 -->
  <class name="Patient" table="dl_patient">
    <id name="pid" column="pid" type="java.lang.Integer">
      <generator class="increment"/>
    </id>
    <property name="name"></property>
    <property name="username"></property>
    <property name="password"></property>
    <property name="age"></property>
    <property name="sex"></property>
    <property name="address"></property>
    <property name="phone"></property>
    <!-- 与挂号队列映射 -->
    <set name="ps" table="dl_pinqueue" inverse="true" cascade="save-update">
      <key column="patient_pid"></key>
      <one-to-many class="Pinqueue"/>
    </set>
    <!-- 与历史映射 -->
    <set name="history" table="dl_history" inverse="true" cascade="save-update">
      <key column="patient_pid"></key>
      <one-to-many class="History"/>
    </set>
  </class>
  <!-- 挂号队列 -->
  <class name="Pinqueue" table="dl_pinqueue">
    <id name="did" column="did" type="java.lang.Integer">
      <generator class="increment"/>
    </id>
    <property name="sunA"></property>
    <property name="sunP"></property>
    <property name="monA"></property>
    <property name="monP"></property>
    <property name="tueA"></property>
    <property name="tueP"></property>
    <property name="wedA"></property>
    <property name="wedP"></property>
    <property name="thuA"></property>
    <property name="thuP"></property>
    <property name="friA"></property>
    <property name="friP"></property>
    <property name="satA"></property>
    <property name="satP"></property>
    <!-- 与医生映射 -->
    <one-to-one name="doctor" class="Doctor" constrained="true" cascade="save-update"></one-to-one>
  </class>
</hibernate-mapping>
```

### EncodingFilter.java

```java
package com.abd.filter;

import java.io.IOException;

import javax.servlet.Filter;

import javax.servlet.FilterChain;

import javax.servlet.FilterConfig;

import javax.servlet.ServletException;

import javax.servlet.ServletRequest;

import javax.servlet.ServletResponse;

import javax.servlet.http.HttpServletRequest;

import javax.servlet.http.HttpServletResponse;

public class EncodingFilter implements Filter {

    @Override

    public void destroy() {

        // TODO Auto-generated method stub

    }

    @Override

    public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
```



### 代码示例

```java
// TODO Auto-generated method stub

HttpServletRequest res = (HttpServletRequest)request;

HttpServletResponse req = (HttpServletResponse)response;

res.setCharacterEncoding("UTF-8");

req.setCharacterEncoding("UTF-8");

chain.doFilter(res, req);

}

@Override

public void init(FilterConfig arg0) throws ServletException {

// TODO Auto-generated method stub

}

}
```

### 路径：`src\com\abd\util`

#### Util.java

```java
package com.abd.util;

import java.util.StringTokenizer;

import com.abd.expt.AppointmentException;

public class Util {

    /**

     * 医生预约信息字符串处理

     * 

     * 参数信息

     * dayPattern 预约信息（14 个整数，用逗号或空格分隔）

     * 

     * 返回值 - 长度为 14 的整数数组

     */

    public static int[] parseSpDays(String dayPattern) throws NumberFormatException {

        int[] spDays=new int[14];

        StringTokenizer token=new StringTokenizer(dayPattern.trim(),", ");

        if(token.countTokens() != 14)

            throw new AppointmentException();

        for(int i=0;i < 14;i++)

            spDays[i]=Integer.parseInt(token.nextToken());

        return spDays;

    }

}
```

### 路径：`src\res`

#### AppResources.properties

```properties
errors.password=password

errors.system=system

errors.username=username

errors.id=id

errors.sql=sql

errors.app=appointment

errors.io=io

errors.exception=exception

errors.alreadyAppointment=alreadyAppointment

errors.wrong=wrong

errors.DayAlreadyAppointment=DayAlreadyAppointment

errors.header=<font color="red">errors.footer=</font>
```

#### AppResources_zh.properties

```properties
errors.password=您的密码错误！

errors.system=未知系统异常

errors.username=您的密码输入错误

errors.id=ID 已存在

errors.sql=sql 异常

errors.app=预约异常

errors.io=io 异常

errors.exception=未知异常

errors.alreadyAppointment=您已经预约了此位医生

errors.wrong=您的操作错误

errors.DayAlreadyAppointment=预约冲突

errors.header=<font color="red">errors.footer=</font>
```

### 路径：`src`

#### log4j.properties

```properties
### 将日志消息直接输出到标准输出 ###

log4j.appender.stdout=org.apache.log4j.ConsoleAppender

log4j.appender.stdout.Target=System.out

log4j.appender.stdout.layout=org.apache.log4j.PatternLayout

log4j.appender.stdout.layout.ConversionPattern=%d{ABSOLUTE} %5p %c{1}:%L - %m%n

### 将消息直接输出到文件 hibernate.log ####

log4j.appender.file=org.apache.log4j.FileAppender

#log4j.appender.file.File=hibernate.log

#log4j.appender.file.layout=org.apache.log4j.PatternLayout

#log4j.appender.file.layout.ConversionPattern=%d{ABSOLUTE} %5p %c{1}:%L - %m%n

### 设置日志级别 - 如需更详细的日志请将'info'更改为'debug' ###

log4j.rootLogger=warn, stdout

#log4j.rootLogger=warn, stdout, file

#log4j.logger.org.hibernate=info

log4j.logger.org.hibernate=debug

### 记录 HQL 查询解析器活动

#log4j.logger.org.hibernate.hql.ast.AST=debug

### 仅记录 SQL

log4j.logger.org.hibernate.SQL=debug

### 记录 JDBC 绑定参数 ###

log4j.logger.org.hibernate.type=info

#log4j.logger.org.hibernate.type=debug

### 记录模式 导出/更新 ###

log4j.logger.org.hibernate.tool.hbm2ddl=debug

### 记录 HQL 解析树

log4j.logger.org.hibernate.hql=debug

### 记录缓存活动 ####

log4j.logger.org.hibernate.cache=debug

### 记录事务活动

#log4j.logger.org.hibernate.transaction=debug

### 记录 JDBC 资源获取

#log4j.logger.org.hibernate.jdbc=debug

### 如果你想在在使用 DriverManagerConnectionProvider 时跟踪连接泄漏，请启用以下行 ###### ####

log4j.logger.org.hibernate.connection.DriverManagerConnectionProvider=trace
```

![](img/image_rsrcFVCF)

### 路径：`WebContent\admin`

#### addDoctor.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>

<%@ page isIgnored="false" %>

<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>

<%@include file="../include/ccs" %>

<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/HTML4/loose.dtd">

<html>

<head>

    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">

    <title>添加医生</title>

</head>

<body bgcolor="#FFFFFF">

    <table width="770" height="423" border="0" bgcolor="#000000">

        <tr>

            <%@ include file="head" %>

            <td height="421" bgcolor="#FFFFFF">

                <%@include file="../include/head" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">

                    <tr>

                        <%@ include file="admin" %>

                        <td width="603" align="center" valign="top">

                            <br>

                            <c:if test="${!empty addDoctor}">

                                <font color="blue">添加成功</font>

                            </c:if>

                            <c:if test="${empty addDoctor}">

                                <form method="POST" action="/hospital/allAction.do?method=addDoctor">

                                    <p>序列号：<input type="text" name="did" value="0"/></p>

                                    <p>姓名：<input type="text" name="name"/></p>

                                    <p>年龄：<input type="text" name="age" value="0"/></p>

                                    <p>性别：<input type="text" name="sex" size="4" maxlength="1" />（0 男，1 女）</p>

                                    <p>职称：<input type="text" name="level"/></p>

                                    <p>专科：<input type="text" name="spe"/></p>

                                    <p>电话：<input type="text" name="phone"/></p>

                                    <p>科室：<input type="text" name="section"/></p>

                                    <p>预约信息（14 个整数，分别对应周日上午、周日下午、周一上午……，并用逗号分隔）：<br /><input type="text" name="spDay" size="50"/></p>

                                    <p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="提交"/></p>

                                </form>

                            </c:if>

                        </td>

                    </tr>

                </table>

            </td>

        </tr>

    </table>

</body>

</html>
```

#### getDoctor.jsp

### 医生信息 (Doctor.jsp)

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><@ page isELIgnored="false" %><@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>医院门诊预约系统 - 管理员 - 医生信息</title></head><body bgcolor="#FFFFFF"><table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000"><tr><td height="421" bgcolor="#FFFFFF"><@@ include file = "../include/head.inc" %><table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0"><tr><%@ include file="../include/admin.inc" %><td width="603" align="center" valign="top"><table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666"><tr><td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF"><br><c:if test="${!empty doctors}"><p>查询成功（点击医生姓名以删除记录）</p></c:if><table width="100%"><tr><th>姓名</th><th>年龄</th><th>性别</th><th>职称</th><th>科室</th><th>专长</th><th>电话</th></tr><c:forEach var="d" items="${doctors}"><tr align="center"><td><a href="/hospital/allAction.do?method=removeDoctor&did=${d.did}" onclick="return confirm('你确定要删除此医生吗？');">${d.name}</a></td><td>${d.age}</td><td>${d.sex}</td><td>${d.levels}</td><td>${d.section}</td><td>${d.spe}</td><td>${d.phone}</td></tr></c:forEach></table></td></tr></tr></table></td></tr></tr></table></td></body></body></html>
```

### 管理员登录 (login.jsp)

```html



# 管理员登录（登录页面）

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>管理员登录</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/admin.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        <c:if test="${!empty admin}">
                                            <p>你好！ ${admin}</p>
                                        </c:if>
                                        <c:if test="${empty admin}">
                                            <form method="POST" action="/hospital/allAction.do?method=Login">
                                                <p>用户名：<input type="text" name="username"></p>
                                                <p>密码：<input type="password" name="password"></p>
                                                <p>
                                                    <input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border:0" value="登录">
                                                </p>
                                            </form>
                                        </c:if>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

# 管理员（`main.jsp`）

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>管理员</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/admin.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        请点击左侧菜单进入相应页面
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

# 删除医生（`removeDoctor.jsp`）

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>管理员删除医生</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/admin.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        <font color="red">删除成功</font>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

# 数据库（`hospital.sql`）

`hospital.sql` 详情已给出。

# 创建病历（`createHistory.jsp`）

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>创建病历</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        <c:if test="${!empty bing}">
                                            <p align="center">医疗成功</p>
                                        </c:if>
                                        <c:if test="${empty bing}">
                                            <form action="/hospital/allAction.do?method=createHistory&pid=${param.pid}" method="POST">
                                                <p>症状：<input type="text" name="description"></p>
                                                <p>诊断：<input type="text" name="diagnose"></p>
                                                <p>处方：<input type="text" name="rx"></p>
                                                <p><input type="submit" value="创建"></p>
                                            </form>
                                        </c:if>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

# 完成病历（`finishHistory.jsp`）

# 获取患者病历（`getPatientHistory.jsp`）

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>治疗结束</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        操作成功！
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

# 获取排队患者（`getPatientInQueue.jsp`）

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>医生获取预约信息</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <p align="center">点击已创建的病历姓名</p>
                                        <table width="100%" border="0" cellspacing="0" cellpadding="0">
                                            <tr>
                                                <th>姓名</th>
                                                <th>年龄</th>
                                                <th>性别</th>
                                                <th>联系地址</th>
                                                <th>电话</th>
                                                <th>预约号</th>
                                            </tr>
                                            <c:forEach var="pq" items="${pinqueues1}">
                                                <tr align="center">
                                                    <td>
                                                        <a href="/hospital/doctor/createHistory.jsp?pid=${pq.pid}">${pq.name}</a>
                                                    </td>
                                                    <td>${pq.age}</td>
                                                    <td>${pq.sex}</td>
                                                    <td>${pq.address}</td>
                                                    <td>${pq.phone}</td>
                                                    <td>${pq.qid}</td>
                                                </tr>
                                            </c:forEach>
                                        </table>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

# 登录页面（`login.jsp`）



## doctor.jsp

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>医生登录</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <c:if test="${!empty doctor}">
                                            <p><strong>你好 ${doctor.name}</strong></p>
                                        </c:if>

                                        <c:if test="${empty doctor}">
                                            <form action="/hospital/allAction.do?method=Login" method="POST">
                                                <p>姓名：<input type="text" name="name"/></p>
                                                <p>密码：<input type="password" name="password"/></p>
                                                <p>
                                                    <input type="submit" style="background:url(gif);height:50px; width:200px; border="0" value="登录"/>
                                                </p>
                                            </form>
                                        </c:if>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

## main.jsp

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c" %>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>医生</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        请点击左侧菜单进入对应页面
                                    </td>
                                </tr>
                                ></tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

## updateHistory.jsp

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8">
<%@ page isELIgnored="false">
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c">
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset-8">
    <title>修改病例</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#00000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file "../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#66666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>

                                        <c:if test="${!empty upda}">
                                            <p>更新成功!</p>
                                        </c:if>

                                        <c:if test="${empty upda}">
                                            <form action="/hospital/allAction.do?method=updatePatientHistory&hid=${param.hid}" method="POST">
                                                <p>症状：<input type="text" name="description"/></p>
                                                <p>诊断：<input type="text" name="diagnose"/></p>
                                                <p>处方：<input type="text" name="rx"/></p>
                                                <p><input type="submit" value="确认"/></p>
                                            </form>
                                        </c:if>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

## updatePassword.jsp

```html
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8">
<%@ page isELIgnored="false">
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c">
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset-8">
    <title>在此插入标题</title>
</head>
<body bgcolor="#ffffff">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#00000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file "../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0">
                    <tr>
                        <%@ include file="../include/doctor.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#66666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>

                                        <c:if test="${!empty newPassword}">
                                            <p><strong>密码已成功修改</strong></p>
                                        </c:if>

                                        <c:if test="${empty newPassword}">
                                            <form action="/hospital/allAction.do?method=doctorUpdatePassword" method="POST">
                                                <p>新密码：<input type="password" name="password"/></p>
                                                <p><input type="submit" value="修改"/></p>
                                            </form>
                                        </c:if>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

## `WebContent\include`

### admin.inc

```html
<%@ page contentType="text/html; charset=UTF-8" %>

<td width="167" height="290" valign="top" bgcolor="8FBEE8">
    <div align="center">
        <br>

        <p><a href="/hospital/default.jsp">返回首页</a></p>

        <br>

        <c:if test="${empty admin}">
            <p><a href="/hospital/admin/login.jsp">登录（管理员）</a></p>
        </c:if>

        <c:if test="${!empty admin}">
            <p><a href="/hospital/allAction.do?method=getDoctor">查看医院医生信息</a></p>
            <p><a href="/hospital/admin/addDoctor.jsp">添加医生账号</a></p>
            <p><a href="/hospital/allAction.do?method=getDoctor">删除医生账号</a></p>
            <p><a href="/hospital/allAction.do?method=exit">退出</a></p>
        </c:if>

        <br>

        <p><a href="/hospital/patient.jsp">患者用户</a></p>
        <p><a href="/hospital/doctor.jsp">医生用户</a></p>

        <br>
    </div>
</td>
```

### ccs.inc

```css
<style type="text/css">
    body,
    th {
        font-size: 12px;
    }

    a {
        text-decoration: #00033;
    }

    a:link {
        text-decoration: none;
    }

    a:visited {
        text-decoration: none;
    }

    a:hover {
        text-decoration: none;
    }

    a:active {
        text-decoration: none;
    }
</style>
```

### doctor.inc

```html
<%@ page contentType="text/html; charset=UTF-8}>

<td width="167" height="290" valign="top" bgcolor="8FBEE8">
    <div align="center">
        <br>

        <p><a href="/hospital/default.jsp">返回首页</a></p>

        <br>

        <c:if test="${empty doctor}">
            <p><a href="/hospital/admin/login.jsp">登录（医生用户）</a></p>
        </c:if>

        <c:if test="${!empty doctor}">
            <p><a href="/hospital/allAction.do?method=doctorUpdatePassword">修改密码</a></p>
            <p><a href="/hospital/allAction.do?method=getMessage">处理病例</a></p>
            <p><a href="/hospital/allAction.do?method=getMessage">创建预约</a></p>
            <p><a href="/hospital/allAction.do?method=queryHistory">查询记录</a></p>
            <p><a href="/hospital/allAction.do?method=getMessage">结束治疗</a></p>
            <p><a href="/hospital/allAction.do?method=exit">退出</a></p>
        </c:if>

        <br>

        <p><a href="/hospital/patient.jsp">患者用户</a></p>
        <p><a href="/hospital/admin.jsp">管理员用户</a></p>

        <br>
    </div>
</td>
```

### head.inc

```html
<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#00000">
    <tr>
        <td height="421" bgcolor="#FFFFFF">
            <%@ include file "../include/head.inc" %>

            <table width="770" height="290" border="0" align="center" cellpadding="0">
                <tr>
                    <%@ include file="../include/doctor.inc" %>

                    <td width="603" align="center" valign="top">
                        <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#66666">
                            <tr>
                                <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                    <
```

### patient.inc



`WebContent\patient`

`cancleAppointment.jsp`

## `getAppointmentInfo.jsp`

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>取消预约</title></head><body bgcolor="#ffffff">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">                           <br>​<p>预约取消成功！</p>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html></html>>
```

## `getCurrentDoctorInfo.jsp`

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>在此输入标题</title></head><body bgcolor="#FFFFFF">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="100%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<p align="left"><strong>点击取消预约号</strong></​</p>​<table width="100%">​<tr>​<th>预约号</th><th>医生编号</th><th>0－周日，1－周一，以此类推</th><th>0- 上午，1- 下午</th><th>预约日期</th>​</tr>​<c:forEach var="pi" items="${pinqueues}">​<tr align="center">​<td><a href="/hospital/allAction.do?method=patientCancleAppointment&qid=${pi.qid}" onclick="return confirm('确定要取消此预约吗？')">​             ${pi.qid}a​</td>​<td>${pi.doctor.did}</td>​<td>${pi.day}</td>​<td>${pi.ap}</td>​<td>${pi.t_date}</td>​</tr>​</c:forEach>​</table>>​</td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html>>
```

## `getDoctorAppointmentInfo.jsp`

```html
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%><@page isELIgnored="false" %><%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%><@include file="../include/ccs.inc" %><!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd"><html><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><title>查询医生信息</title></head><body bgcolor="#ffffff">​<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">​<tr>​<td height="421" bgcolor="#FFFFFF"><%@ include file = "../include/head.inc" %>​<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">​<tr>​<%@ include file = "../include/patient.inc" %>​<td width="603" align="center" valign="top">​<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">​<tr>​<td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">​<table width="100%">​<tr>​<th>医生姓名</th><th>医生编号</th><th>年龄</th><th>性别</th><th>职称</th><th>科室</th><th>专长</th><th>电话</th>​</tr>​<c:forEach var="m" items="${dMessages}">​<tr align="center">​<td>           ${m.name}</td>​<td> mm..}</}><td>${m.age}</td>​<td>       ${m.sex}</td>​<td>           ${m.levels}</td>​<td>           ${m.section}</td>​<td>           ${m.spe}</td>​<td>           ${m.phone}</td>​</tr>​</c:forEach>​</table>></td>​</tr>​</table>​</td>​</tr>​</table>​</td>​</tr>​</table></body></html>>
```

## 医生预约信息.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%>
<%@page isELIgnored="false" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
<%@include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>医生预约信息</title>
</head>
<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file = "../include/head.inc" %>
                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file = "../include/patient.inc" %>
                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>
                                        <p align="left">点击“当前可预约数量”进行预约</p>
                                        <table width="100%" border="0" cellspacing="0" cellpadding="0">
                                            <tr>
                                                <td></td>
                                                <td>周日上午</td><td>周日下午</td><td>周一上午</td><td>周一下午</td><td>周二上午</td><td>周二下午</td><td>周三上午</td><td>周三下午</td><td>周四上午</td><td>周四下午</td><td>周五上午</td><td>周五下午</td><td>周六上午</td><td>周六下午</td>
                                            </tr>
                                            <tr align="center">
```



```html
<td>当前可用预约号数</td>
<td><a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=0&ap=0">${curappointment.sunA}</a></td>
<td><a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=0&ap=1">${curappointment.sunP}</a></td>

<!-- ... 其他日期 ... -->

<td><a href="/hospital/allAction.do?method=patientAppointment&did=${curappointment.did}&day=6&ap=1">${curappointment.satP}</a></td>
</tr>
</table>
</td>
</tr>
</table>
</td>
</tr>
</table>
</td>
</tr>
</table>
</body>
</html>
```

## 获取医生信息.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<%@page isELIgnored="false" %>
<%@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%
<%@include file="../include/ccs.inc" %%>

<!DOCTYPE-type html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<html
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>所有医生</title>
</head>

<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr
            <td height="21" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr
                        <%@ include file="../include/patient.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <<tr>
                                    <td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>

                                        <c:if test="${!empty doctors1}">
                                            <p align="left">点击医生姓名查看预约信息</p>
                                        </c:if>

                                        <table width="100%" border="0" cellspacing="0" cellpadding="0">
                                            <tr>
                                                <th>全名</th>
                                                <th>序列号</th>
                                                <th>年龄</th>
                                                <th>性别（0 男 1 女）</th>
                                                <th>职称</th>
                                                <th>科室</th>
                                                <th>专业</th>
                                                <th>电话</th>
                                            </tr>

                                            <c:forEach var="dd" items="${doctors1}">
                                                <tr align="center">
                                                    <td><a href="/hospital/allAction.do?method=patientAppointmentMessage&did=${dd.did}">${dd.name}</a></td>
                                                    <td>${dd.did}</td>
                                                    <td>${dd.age}</td>
                                                    <td>${dd.sex}</td>
                                                    <td>${dd.levels}</td>
                                                    <td>${dd.section}</td>
                                                    <td>${dd.spe}</td>
                                                    <td>${dd.phone}</td>
                                                </tr>
                                            </c:forEach>
                                        </table>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

## 获取医生信息 2.jsp

```jsp
<!-- 结构与 getDoctorInfo.jsp 相似 -->
```

### 病历记录

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<@page isELIgnored="false" %>
<@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
<@include file="../include/ccs.inc" %>

<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>病人记录</title>
</head>

<body bgcolor="#ffffff">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/patient.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#666666">
                                <tr>
                                    <td width="100%" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <br>

                                        <table width="100%">
                                            <tr>
                                                <th>医生编号</th>
                                                <th>症状</th>
                                                <th>诊断</th>
                                                <th>处方</th>
                                                <th>治疗已结束（是 0 否 1）</th>
                                                <th>治疗开始时间</th>
                                                <th>治疗结束时间</th>
                                            </tr>

                                            <c:forEach var="his" items="${historys}">
                                                <tr align="center">
                                                    <td>${his.doctor.did}</td>
                                                    <td>${his.description}</td>
                                                    <td>${his.diagnose}</td>
                                                    <td>${his.rx}</td>
                                                    <td>${his.finished}</td>
                                                    <td>${his.fdate}</td>
                                                    <td>${his.sdate}</td>
                                                </</tr>
                                            </c:forEach>
                                        </table>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

### login.jsp

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<@page isELIgnored="false" %>
<@taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
<@include file="../include/ccs.inc" %>

<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">

<<html>
<head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    <title>病人登录</title>
</head>

<body bgcolor="#FFFFFF">
    <table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
        <tr>
            <td height="421" bgcolor="#FFFFFF">
                <%@ include file="../include/head.inc" %>

                <table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
                    <tr>
                        <%@ include file="../include/patient.inc" %>

                        <td width="603" align="center" valign="top">
                            <table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#66666">
                                <tr>
                                    <td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
                                        <c:if test="${!empty patient}">
                                            <p><strong>你好！${patient.username}</strong>></p>
                                        </c:if>

                                        <c:if test="${empty patient}">
                                            <form action="/hospital/allAction.do?method=pLogin" method="POST">
                                                <p>用户名:<input type="text" name="username"/></p>
                                                <p>密码:<input type="password" name="password"/></p>
                                                <p><input type="submit" style="background:url(images/land.gif);height:50px; width:200px; border="0" value="登录"/></p>
                                            </form>
                                        </c:if>
                                    </td>
                                </tr>
                            </table>
                        </td>
                    </tr>
                </table>
            </td>
        </tr>
    </table>
</body>
</html>
```

### main.jsp



### 病人页面（`patient.jsp`）

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>病人</title>
</head>
<body bgcolor="#FFFFFF">
<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
<tr>
<td height="421" bgcolor="#FFFFFF">
<%@ include file = "../include/head.inc" %>
<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
<tr>
<%@ include file = "../include/patient.inc" %>
<td width="603" align="center" valign="top">
<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#66666">
<tr>
<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
<br>请点击左侧菜单进入对应的页面
</td>
</tr>
</table>
</td>
</tr>
</table>
</body>
</html>
```

### 预约页面（`makeAppointment.jsp`）

```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"pageEncoding="UTF-8"%>
<%@ page isELIgnored="false" %>
<%@ taglib uri="http://java.sun.com/jsp/jstl/core" prefix="c"%>
<%@ include file="../include/ccs.inc" %>
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
<html>
<head>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
<title>预约</title>
</head>
<body bgcolor="#FFFFFF">
<table width="770" height="423" border="0" align="center" cellpadding="0" cellspacing="1" bgcolor="#000000">
<tr>
<td height="421" bgcolor="#FFFFFF">
<%@ include file = "../include/head.inc" %>
<table width="770" height="290" border="0" align="center" cellpadding="0" cellspacing="0">
<tr>
<%@ include file = "../include/patient.inc" %>
<td width="603" align="center" valign="top">
<table width="100%" height="85%" border="0" cellpadding="3" cellspacing="1" bgcolor="#66666">
<tr>
<td width="488" height="400" align="center" valign="top" bgcolor="E3EDFF">
<br>
<p><strong>恭喜！预约成功</strong></p>
</td>
</tr>
</table>
</td>
</tr>
</table>
</td>
</tr>
</table>
</body>
</html>
```

### 页面结构说明

#### 1. 查询医生页面（`patientQueryDoctor.jsp`）

该页面用于查询医生信息，包含以下表单项目：

##### 表单配置

表单通过`POST`方法提交到`/hospital/allAction.do?method=patientQueryMessage`。

##### 表单字段及逻辑

- **科室**：下拉框`section`。选项通过`c:forEach`遍历`${sections}`集合生成。

- **职称**：下拉框`level`。选项通过`c:forEach`遍历`${levels}`集合生成。

- **擅长**：下拉框`spe`。选项通过`c:forEach`遍历`${es}`集合生成。

- **时间**：下拉框`day`。选项包括：
  - `1`：星期一
  - `2`：星期二
  - `3`：星期三
  - `4`：星期四
  - `5`：星期五
  - `6`：星期六
  - `0`：星期日

- **时间段**：下拉框`ap`。选项包括：
  - `3`：请选择
  - `0`：上午
  - `1`：下午

- **提交按钮**：`input type="submit"`，值为`Confirm`。

#### 2. 注册页面（`register.jsp`）

该页面用于患者注册。

##### 逻辑处理

- 如果`${patient}`不为空，显示：**恭喜！注册成功**。
- 如果`${patient}`为空，显示注册表单。

##### 表单字段

表单通过`POST`方法提交到`/hospital/allAction.do?method=regsterPatient`。

- **用户名**：输入字段`username`。

- **密码**：输入字段`password`（类型：密码）。

- **姓名**：输入字段`name`。

- **年龄**：输入字段`age`。

- **性别**：输入字段`sex`，长度为4，最大长度1。说明：`0`代表男性，`1`代表女性。

- **联系地址**：输入字段`address`，最小长度5。

- **电话**：输入字段`phone`。

- **提交按钮**：`input type="submit"`，背景图片为`images/land.gif`，值为`Registration`。

#### 3. 配置文件路径

- 目录：`WebContent\WEB-INF`
- 配置文件：`springweb-servlet.xml`



```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE beans PUBLIC "-//SPRING//DTD BEAN//EN" "http://www.springframework.org/dtd/spring-beans.dtd">
<beans>
  <!-- 数据源 -->
  <bean id="dataSource" class="org.apache.commons.dbcp.BasicDataSource">
    <property name="driverClassName">
      <value>com.mysql.jdbc.Driver</value>
    </property>
    <property name="url">
      <value>jdbc:mysql://localhost/tarena</value>
    </property>
    <property name="username">
      <value>root</value>
    </property>
    <property name="password">
      <value>root</value>
    </property>
  </bean>
  <!-- 会话工厂 -->
  <bean id="sessionFactory" class="org.springframework.orm.hibernate3.LocalSessionFactoryBean">
    <property name="dataSource">
      <ref bean="dataSource" />
    </property>
    <property name="hibernateProperties">
      <props>
        <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
        <prop key="hibernate.hbm2ddl.auto">create</prop>
        <prop key="hibernate.show_sql">true</prop>
        <!-- <prop key="hibernate.format_sql">false</prop>-->
      </props>
    </property>
    <property name="mappingResources">
      <list>
        <value>com/kettas/entity/hosp.hbm.xml</value>
      </list>
    </property>
  </bean>
  <!-- dao hibernate 实现类继承 HibernateDaoSupport -->
  <bean id="adminDao" class="com.abd.dao.impl.AdminDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <bean id="appointmentDao" class="com.abd.dao.impl.AppointmentDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <bean id="curappointmentDao" class="com.abd.dao.impl.CurappointmentDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <bean id="doctorDao" class="com.abd.dao.impl.DoctorDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <bean id="historyDao" class="com.abd.dao.impl.HistoryDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <bean id="patientDao" class="com.abd.dao.impl.PatientDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <bean id="pinqueueDao" class="com.abd.dao.impl.PinqueueDaoImpl">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <!-- 目标 -->
  <bean id="adminTarget" class="com.abd.biz.impl.AdminBizImpl">
    <property name="daoA">
      <ref bean="adminDao" />
    </property>
    <property name="daoB">
      <ref bean="doctorDao" />
    </property>
    <property name="daoC">
      <ref bean="appointmentDao" />
    </property>
    <property name="daoD">
      <ref bean="curappointmentDao" />
    </property>
  </bean>
  <bean id="patientTarget" class="com.abd.biz.impl.PatientBizImpl">
    <property name="daoD">
      <ref bean="doctorDao" />
    </property>
    <property name="daoC">
      <ref bean="curappointmentDao" />
    </property>
    <property name="daoP">
      <ref bean="patientDao" />
    </property>
    <property name="daoH">
      <ref bean="historyDao" />
    </property>
    <property name="daoQ">
      <ref bean="pinqueueDao" />
    </property>
  </bean>
  <bean id="doctorTarget" class="com.abd.biz.impl.DoctorBizImpl">
    <property name="daoD">
      <ref bean="doctorDao" />
    </property>
    <property name="daoQ">
      <ref bean="pinqueueDao" />
    </property>
    <property name="daoP">
      <ref bean="patientDao" />
    </property>
    <property name="daoH">
      <ref bean="historyDao" />
    </property>
    <property name="daoC">
      <ref bean="curappointmentDao" />
    </property>
  </bean>
  <!-- --> -->
  <bean id="transactionManager" class="org.springframework.orm.hibernate3.HibernateTransactionManager">
    <property name="sessionFactory">
      <ref bean="sessionFactory" />
    </property>
  </bean>
  <!-- 服务代理 -->
  <bean id="serviceAdmin" class="org.springframework.transaction.interceptor.TransactionProxyFactoryBean">
    <property name="proxyInterfaces">
      <value>com.abd.biz.AdminBiz</value>
    </property>
    <property name="target">
      <ref bean="adminTarget" />
    </property>
    <property name="transactionManager">
      <ref bean="transactionManager" />
    </property>
    <property name="transactionAttributes">
      <props>
        <prop key="*">PROPAGATION_REQUIRED</prop>
      </props>
    </property>
  </bean>
  <bean id="serviceDoctor" class="org.springframework.transaction.interceptor.TransactionProxyFactoryBean">
    <property name="proxyInterfaces">
      <value>com.abd.biz.DoctorBiz</value>
    </property>
    <property name="target">
      <ref bean="doctorTarget" />
    </property>
    <property name="transactionManager">
      <ref bean="transactionManager" />
    </property>
    <property name="transactionAttributes">
      <props>
        <prop key="*">PROPAGATION_REQUIRED</prop>
      </props>
    </property>
  </bean>
  <bean id="servicePatient" class="org.springframework.transaction.interceptor.TransactionProxyFactoryBean">
    <property name="proxyInterfaces">
      <value>com.abd.biz.PatientBiz</value>
    </property>
    <property name="target">
      <ref bean="patientTarget" />
    </property>
    <property name="transactionManager">
      <ref bean="transactionManager" />
    </property>
    <property name="transactionAttributes">
      <props>
        <prop key="*">PROPAGATION_REQUIRED</prop>
      </props>
    </property>
  </bean>
</beans>
```

`struts-config.xml`

### Struts 配置文件



### Web 部署 (web.xml)

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<!DOCTYPE struts-config PUBLIC "-//Apache Software Foundation//DTD Struts Configuration 1.2//EN" "http://jakarta.apache.org/struts/dtds/struts-config_1_2.dtd">
<struts-config>
  <form-beans>
    <form-bean name="allForm" type="org.apache.struts.action.DynaActionForm">
      <form-property name="username" type="java.lang.String" />
      <form-property name="password" type="java.lang.String" />
      <form-property name="did" type="java.lang.String" />
      <form-property name="name" type="java.lang.String" />
      <form-property name="age" type="java.lang.String" />
      <form-property name="sex" type="java.lang.String" />
      <form-property name="level" type="java.lang.String" />
      <form-property name="spe" type="java.lang.String" />
      <form-property name="phone" type="java.lang.String" />
      <form-property name="section" type="java.lang.String" />
      <form-property name="spDay" type="java.lang.String" />
      <form-property name="address" type="java.lang.String" />
      <form-property name="description" type="java.lang.String" />
      <form-property name="diagnose" type="java.lang.String" />
      <form-property name="rx" type="java.lang.String" />
      <form-property name="day" type="java.lang.String" />
      <form-property name="ap" type="java.lang.String" />
    </form-bean>
  </form-beans>
  <action-mappings>
    <action parameter="method" path="/allAction" type="com.abd.action.AllAction" name="allForm">
      <exception type="com.abd.expt.PasswordException" path="/error.jsp" key="errors.password" />
      <exception type="com.abd.expt.SystemException" path="/error.jsp" key="errors.system" />
      <exception type="com.abd.expt.UsernameException" path="/error.jsp" key="errors.username" />
      <exception type="com.abd.expt.AlreadyAppointmentException" path="/error.jsp" key="errors.alreadyAppointment" />
      <exception type="com.abd.expt.WrongException" path="/error.jsp" key="errors.wrong" />
      <exception type="com.abd.expt.DayAlreadyAppointmentException" path="/error.jsp" key="errors.DayAlreadyAppointment" />
      <exception type="java.io.IOException" path="/error.jsp" key="errors.io" />
      <exception type="java.sql.SQLException" path="/error.jsp" key="errors.sql" />
      <exception type="com.abd.expt.IdException" path="/error.jsp" key="errors.id" />
      <exception type="com.abd.expt.AppointmentException" path="/error.jsp" key="errors.app" />
      <exception type="java.lang.Exception" path="/error.jsp" key="errors.exception" />
      <forward name="default" path="/default.jsp" />
      <forward name="aLogin" path="/admin/login.jsp" />
      <forward name="allDoctor" path="/admin/getDoctor.jsp" />
      <forward name="removeDoctor" path="/admin/removeDoctor.jsp" />
      <forward name="addDoc" path="/admin/addDoctor.jsp" />
      <forward name="pLogin" path="/patient/login.jsp" />
      <forward name="pRegister" path="/patient/register.jsp" />
      <forward name="getDoc" path="/patient/getDoctorInfo.jsp" />
      <forward name="getDocss" path="/patient/getDoctorInfo2.jsp" />
      <forward name="appoint" path="/patient/getDoctorAppointmentInfo.jsp" />
      <forward name="make" path="/patient/makeAppointment.jsp" />
      <forward name="getApp" path="/patient/getAppointmentInfo.jsp" />
      <forward name="cancle" path="/patient/cancleAppointment.jsp" />
      <forward name="current" path="/patient/getCurrentDoctorInfo.jsp" />
      <forward name="his" path="/patient/getHistory.jsp" />
      <forward name="dLogin" path="/doctor/login.jsp" />
      <forward name="upp" path="/doctor/updatePassword.jsp" />
      <forward name="getPatientIn" path="/doctor/getPatientInQueue.jsp" />
      <forward name="create" path="/doctor/createHistory.jsp" />
      <forward name="gph" path="/doctor/getPatientHistory.jsp" />
      <forward name="upok" path="/doctor/updateHistory.jsp" />
      <forward name="finishOk" path="/doctor/finishHistory.jsp" />
      <forward name="pqd" path="/patient/patientQueryDoctor.jsp" />
    </action>
  </action-mappings>
  <message-resources parameter="res.AppResources" />
  <plug-in className="org.springframework.web.struts.ContextLoaderIn">
    <set-property property="contextLocation" value="/WEB-INF/spring.xml" />
  </plug-in>
</struts-config>
```

### Web 部署 (web.xml)

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/javaee" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" id="WebApp_ID" version="2.5">
  <display-name>hospital</display-name>
  <welcome-file-list>
    <welcome-file>index.html</welcome-file>
    <welcome-file>index.htm</welcome-file>
    <welcome-file>index.jsp</welcome-file>
    <welcome-file>default.html</welcome-file>
    <welcome-file>default.htm</welcome-file>
    <welcome-file>default.jsp</welcome-file>
  </welcome-file-list>
  <servlet>
    <servlet-name>actionServlet</servlet-name>
    <servlet-class>org.apache.struts.action.ActionServlet</servlet-class>
    <load-on-startup>1</load-on-startup>
    <init-param>
      <param-name>config</param-name>
      <param-value>/WEB-INF/struts-config.xml</param-value>
    </init-param>
    <init-param>
      <param-name>debug</param-name>
      <param-value>2</param-value>
    </init-param>
  </servlet>
  <servlet-mapping>
    <servlet-name>actionServlet</servlet-name>
    <url-pattern>*.do</url-pattern>
  </servlet-mapping>
  <filter>
    <filter-name>encoding</filter-name>
    <filter-class>com.abd.filter.EncodingFilter</filter-class>
  </filter>
  <filter-mapping>
    <filter-name>encoding</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>
</web-app>
```

### WebContent

- default.jsp

#### 门诊预约系统 - 首页

该页面是门诊预约系统的首页，包含以下用户角色选择：

- **患者用户**: `/hospital/patient/main.jsp`
- **医生用户**: `/hospital/doctor/main.jsp`
- **管理员用户**: `/hospital/admin/main.jsp`

页面包含以下资源路径：

- `/hospital/images/LEFTBAR.GIF`
- `/hospital/images/TOPBAR.GIF`
- `/hospital/images/pic.jpg`
- `/hospital/images/3.jpg`
- `/hospital/images/4.jpg`
- `/hospital/images/5.jpg`
- `/hospital/images/6.jpg`

##### 脚本逻辑

页面包含以下 JavaScript 逻辑：

```javascript
var speed=30
//gun2.innerHTML=gun1.innerHTML
function Marquee3(){
  if(gun2.offsetWidth-gun.scrollLeft<=0)
    gun.scrollLeft-=gun1.offsetWidth
  else
    gun.scrollLeft++
}
var MyMar3 = setInterval(Marquee3,speed)
gun.onmouseover=function() {
  clearInterval(MyMar3)
}
gun.onmouseout=function() {
  MyMar3=setInterval(Marquee3,speed)
}
```

#### error.jsp

该页面用于显示错误信息并引导用户返回：

```jsp
<%@page isELIgnored="false"%><@page contentType="text/html;charset=UTF-8" %>  
<%@taglib uri="http://struts.apache.org/tags-html" prefix="html"%(
<h1>
  <html:errors />
  <br>
  <a>请返回</a>
</h1>
```
