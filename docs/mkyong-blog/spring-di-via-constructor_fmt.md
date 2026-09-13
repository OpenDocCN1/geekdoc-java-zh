
# 通过构造函数弹出 DI

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring/spring-di-via-constructor/>

使用 Spring 通过构造函数依赖注入 bean。

## 1. `IOutputGenerator`

它的一个接口和实现类。

```java
package com.mkyong.output;

public interface IOutputGenerator
{
	public void generateOutput();
}
```

```java
package com.mkyong.output.impl;

import com.mkyong.output.IOutputGenerator;

public class JsonOutputGenerator implements IOutputGenerator
{
	public void generateOutput(){
		System.out.println("This is Json Output Generator");
	}
}
```

## 2. 助手类

一个助手类，稍后使用 Spring 通过构造函数来定义 `IOutputGenerator`。

```java
package com.mkyong.output;

import com.mkyong.output.IOutputGenerator;

public class OutputHelper {
	IOutputGenerator outputGenerator;

	public void generateOutput() {
		outputGenerator.generateOutput();
	}

	//DI via constructor
	public OutputHelper(IOutputGenerator outputGenerator){
		this.outputGenerator = outputGenerator;
	}
}
```

## 3. 弹簧配置

请看下面的 Spring bean 配置，Spring 将 DI 上面的 `JsonOutputGenerator` 转换成这个 `OutputHelper` 类，通过构造函数 `public OutputHelper(IOutputGenerator outputGenerator)`。

```java
<beans
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans-2.5.xsd">

	<bean id="OutputHelper" class="com.mkyong.output.OutputHelper">
		<constructor-arg>
			<ref bean="JsonOutputGenerator" />
		</constructor-arg>
	</bean>

	<bean id="JsonOutputGenerator" class="com.mkyong.output.impl.JsonOutputGenerator" />
</beans>
```

## 4. 运行它

加载所有内容，并运行它。

```java
package com.mkyong.common;

import org.springframework.context.ApplicationContext;
import org.springframework.context.support.ClassPathXmlApplicationContext;
import com.mkyong.output.OutputHelper;

public class App {
	public static void main(String[] args) {
		ApplicationContext context = new ClassPathXmlApplicationContext(
				"SpringBeans.xml");

		OutputHelper output = (OutputHelper)context.getBean("OutputHelper");
    	        output.generateOutput();
	}
}
```

输出

```java
This is Json Output Generator
```

**构造函数类型歧义**

对于支持多个参数的构造函数，会导致常见的构造函数注入类型歧义问题，请阅读此[解决方案](http://web.archive.org/web/20190223075942/http://www.mkyong.com/spring/constructor-injection-type-ambiguities-in-spring/)。

## 下载源代码

下载它 – [Spring-DI-constructor-example.zip](http://web.archive.org/web/20190223075942/http://www.mkyong.com/wp-content/uploads/2011/06/Spring-DI-constructor-method-example.zip) (6KB)

[dependency injection](http://web.archive.org/web/20190223075942/http://www.mkyong.com/tag/dependency-injection/) [spring](http://web.archive.org/web/20190223075942/http://www.mkyong.com/tag/spring/)
