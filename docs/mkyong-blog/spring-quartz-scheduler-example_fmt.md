
# Spring 3 + Quartz 1.8.6 调度器示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/spring/spring-quartz-scheduler-example/>

【2012 年 7 月 25 日更新】– 升级文章以使用 Spring 3 和 Quartz 1.8.6（原来是 Spring 2.5.6 和 Quartz 1.6）

在本教程中，我们将向您展示如何将 Spring 与 Quartz scheduler 框架集成。Spring 附带了许多方便的类来支持 Quartz，并将您的类解耦到 Quartz APIs。

使用的工具：

1. Spring 3.1.2.RELEASE
2. Quartz 1.8.6
3. Eclipse 4.2
4. Maven 3

**为什么不用 Quartz 2？**

目前，Spring 3 仍然不支持 Quartz 2 APIs，请参阅此 [SPR-8581 bug 报告](http://web.archive.org/web/20210110054400/https://jira.springsource.org/browse/SPR-8581)。一旦 bug 修复发布，将再次更新本文。

## 1. 项目依赖性

集成 Spring 3 和 Quartz 1.8.6 需要以下依赖项

*文件：`pom.xml`*

```xml
...
<dependencies>

	<!-- Spring 3 dependencies -->
	<dependency>
		<groupId>org.springframework</groupId>
		<artifactId>spring-core</artifactId>
		<version>3.1.2.RELEASE</version>
	</dependency>

	<!-- QuartzJobBean in spring-context-support.jar -->
	<dependency>
		<groupId>org.springframework</groupId>
		<artifactId>spring-context-support</artifactId>
		<version>3.1.2.RELEASE</version>
	</dependency>

	<!-- Spring + Quartz need transaction -->
	<dependency>
		<groupId>org.springframework</groupId>
		<artifactId>spring-tx</artifactId>
		<version>3.1.2.RELEASE</version>
	</dependency>

	<!-- Quartz framework -->
	<dependency>
		<groupId>org.quartz-scheduler</groupId>
		<artifactId>quartz</artifactId>
		<version>1.8.6</version>
	</dependency>

</dependencies>
...
```

## 2. 调度程序任务

创建一个普通的 Java 类，这是您想要在 Quartz 中调度的类。

*文件：`RunMeTask.java`*

```java
package com.mkyong.common;

public class RunMeTask {
	public void printMe() {
		System.out.println("Spring 3 + Quartz 1.8.6 ~");
	}
}
```

## 3. 声明 Quartz 调度程序作业

使用 Spring，您可以通过两种方式声明 Quartz 作业：

**3.1 `MethodInvokingJobDetailFactoryBean`**

这是最简单直接的方法，适合简单的调度器。

```xml
<bean id="runMeJob" 
 	class="org.springframework.scheduling.quartz.MethodInvokingJobDetailFactoryBean">

	<property name="targetObject" ref="runMeTask" />
	<property name="targetMethod" value="printMe" />

</bean>
```

**3.2 `JobDetailBean`**

`QuartzJobBean`更加灵活，适合复杂的调度器。你需要创建一个扩展 Spring 的`QuartzJobBean`类，并在`executeInternal()`方法中定义你想要调度的方法，并通过 setter 方法传递调度器任务（`RunMeTask`）。

*文件：`RunMeJob.java`*

```java
package com.mkyong.common;

import org.quartz.JobExecutionContext;
import org.quartz.JobExecutionException;
import org.springframework.scheduling.quartz.QuartzJobBean;

public class RunMeJob extends QuartzJobBean {
	private RunMeTask runMeTask;

	public void setRunMeTask(RunMeTask runMeTask) {
		this.runMeTask = runMeTask;
	}

	protected void executeInternal(JobExecutionContext context)
		throws JobExecutionException {

		runMeTask.printMe();

	}
}
```

通过`jobClass`配置目标类，通过`jobDataAsMap`配置方法运行。

```xml
<bean name="runMeJob" class="org.springframework.scheduling.quartz.JobDetailBean">

	<property name="jobClass" value="com.mkyong.common.RunMeJob" />

	<property name="jobDataAsMap">
		<map>
			<entry key="runMeTask" value-ref="runMeTask" />
		</map>
	</property>

</bean>
```

## 4. 触发器

配置 Quartz 触发器以定义何时运行调度程序作业。支持两种类型触发器：

**4.1 `SimpleTrigger`**

它允许设置运行作业的开始时间、结束时间、重复间隔。

```xml
<!-- Simple Trigger, run every 5 seconds -->
<bean id="simpleTrigger" 
                class="org.springframework.scheduling.quartz.SimpleTriggerBean">

	<property name="jobDetail" ref="runMeJob" />
	<property name="repeatInterval" value="5000" />
	<property name="startDelay" value="1000" />

</bean>
```

**4.2 `CronTrigger`**

它允许 Unix cron 表达式指定运行作业的日期和时间。

```xml
<!-- Cron Trigger, run every 5 seconds -->
<bean id="cronTrigger"
		class="org.springframework.scheduling.quartz.CronTriggerBean">

	<property name="jobDetail" ref="runMeJob" />
	<property name="cronExpression" value="0/5 * * * * ?" />

</bean>
```

**注意**

Unix cron 表达式高度灵活且功能强大，请参阅以下网站了解更多信息：

1. [http://en.wikipedia.org/wiki/CRON_expression](http://web.archive.org/web/20210110054400/https://en.wikipedia.org/wiki/CRON_expression)
2. [http://www.quartz-scheduler.org/docs/examples/Example3.html](http://web.archive.org/web/20210110054400/http://www.quartz-scheduler.org/docs/examples/Example3.html)

## 5. 调度器工厂

创建一个调度器工厂 bean，将作业细节和触发器集成在一起。

```xml
<bean class="org.springframework.scheduling.quartz.SchedulerFactoryBean">
	<property name="jobDetails">
	   <list>
	      <ref bean="runMeJob" />
	   </list>
	</property>

	<property name="triggers">
	    <list>
		<ref bean="simpleTrigger" />
	    </list>
	</property>
</bean>
```

## 6. Spring Bean 配置文件

完成 Spring 的 bean 配置文件。

*文件：`Spring-Quartz.xml`*

```xml
<beans 
	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://www.springframework.org/schema/beans
	http://www.springframework.org/schema/beans/spring-beans-3.0.xsd">

	<bean id="runMeTask" class="com.mkyong.common.RunMeTask" />

	<!-- Spring Quartz -->
	<bean name="runMeJob" class="org.springframework.scheduling.quartz.JobDetailBean">

		<property name="jobClass" value="com.mkyong.common.RunMeJob" />

		<property name="jobDataAsMap">
		  <map>
			<entry key="runMeTask" value-ref="runMeTask" />
		  </map>
		</property>

	</bean>

	<!-- 
	<bean id="runMeJob" 
            class="org.springframework.scheduling.quartz.MethodInvokingJobDetailFactoryBean"> 
		<property name="targetObject" ref="runMeTask" /> 
		<property name="targetMethod" value="printMe" /> 
	</bean> 
	-->

	<!-- Simple Trigger, run every 5 seconds -->
	<bean id="simpleTrigger" 
                class="org.springframework.scheduling.quartz.SimpleTriggerBean">

		<property name="jobDetail" ref="runMeJob" />
		<property name="repeatInterval" value="5000" />
		<property name="startDelay" value="1000" />

	</bean>

	<!-- Cron Trigger, run every 5 seconds -->
	<bean id="cronTrigger" 
                class="org.springframework.scheduling.quartz.CronTriggerBean">

		<property name="jobDetail" ref="runMeJob" />
		<property name="cronExpression" value="0/5 * * * * ?" />

	</bean>

	<bean class="org.springframework.scheduling.quartz.SchedulerFactoryBean">
		<property name="jobDetails">
			<list>
				<ref bean="runMeJob" />
			</list>
		</property>

		<property name="triggers">
			<list>
				<ref bean="simpleTrigger" />
			</list>
		</property>
	</bean>

</beans>
```

## 7. 演示

运行它~

```java
package com.mkyong.common;

import org.springframework.context.support.ClassPathXmlApplicationContext;

public class App 
{
    public static void main( String[] args ) throws Exception
    {
    	new ClassPathXmlApplicationContext("Spring-Quartz.xml");
    }
}
```

输出到控制台。

```
Jul 25, 2012 3:23:09 PM org.springframework.scheduling.quartz.SchedulerFactoryBean startScheduler
INFO: Starting Quartz Scheduler now
Spring 3 + Quartz 1.8.6 ~ //run every 5 seconds
Spring 3 + Quartz 1.8.6 ~ 
```

## 下载源代码

下载它 – [Spring3-Quartz-Example.zip](http://web.archive.org/web/20210110054400/http://www.mkyong.com/wp-content/uploads/2010/04/Spring3-Quartz-Example.zip)（25 KB）

## 参考

1. [使用带弹簧的石英调度器](http://web.archive.org/web/20210110054400/http://static.springsource.org/spring/docs/3.0.5.RELEASE/reference/scheduling.html#scheduling-quartz)
2. [石英官网](http://web.archive.org/web/20210110054400/http://www.quartz-scheduler.org/)
3. [支柱 2 + 弹簧 3 + 石英 1.8 示例](http://web.archive.org/web/20210110054400/http://www.mkyong.com/struts2/struts-2-spring-3-quartz-1-8-scheduler-example/)

Tags : [integration](http://web.archive.org/web/20210110054400/https://mkyong.com/tag/integration/) [quartz](http://web.archive.org/web/20210110054400/https://mkyong.com/tag/quartz/) [scheduler](http://web.archive.org/web/20210110054400/https://mkyong.com/tag/scheduler/) [spring](http://web.archive.org/web/20210110054400/https://mkyong.com/tag/spring/) [spring3](http://web.archive.org/web/20210110054400/https://mkyong.com/tag/spring3/)

### 相关文章



* [Struts 1+Spring 2.5.6+Quartz 1.6 调度器 exa](/web/20210110054400/https://mkyong.com/struts/struts-spring-quartz-scheduler-integration-example/)
* [Struts 2+Spring 2.5.6+Quartz 1.6 调度器 int](/web/20210110054400/https://mkyong.com/struts2/struts-2-spring-quartz-scheduler-integration-example/)
* [Spring + JDK 定时器调度器示例](/web/20210110054400/https://mkyong.com/spring/spring-jdk-timer-scheduler-example/)
* [Struts 2 + Quartz 2 调度器集成示例](/web/20210110054400/https://mkyong.com/struts2/struts-2-quartz-scheduler-integration-example/)
* [Struts 2 + Spring 3 + Quartz 1.8 调度器示例](/web/20210110054400/https://mkyong.com/struts2/struts-2-spring-3-quartz-1-8-scheduler-example/)
* [JSF 2 +春天 3 整合实例](/web/20210110054400/https://mkyong.com/jsf2/jsf-2-0-spring-integration-example/)
* [Quartz 1.6 调度器教程](/web/20210110054400/https://mkyong.com/java/quartz-scheduler-example/)
* [石英 2 调度器教程](/web/20210110054400/https://mkyong.com/java/quartz-2-scheduler-tutorial/)
* [Quartz 2 JobListener 示例](/web/20210110054400/https://mkyong.com/java/quartz-joblistener-example/)
* [在 Quartz 中运行多个作业的示例](/web/20210110054400/https://mkyong.com/java/example-to-run-multiple-jobs-in-quartz/)
