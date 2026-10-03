
# JSF 2 `PostConstructApplicationEvent` 和 `PreDestroyApplicationEvent` 示例

> 原文：<http://web.archive.org/web/20230101150211/http://www.mkyong.com/jsf2/jsf-2-postconstructapplicationevent-and-predestroyapplicationevent-example/>

从 JSF 2.0 开始，你可以注册`javax.faces.event.PostConstructApplicationEvent`和`javax.faces.event.PreDestroyApplicationEvent`系统事件来操纵 JSF 应用的生命周期。

1. **`PostConstructApplicationEvent`** – 在应用程序启动后执行自定义后配置。
2. **`PreDestroyApplicationEvent`** – 在应用程序即将关闭之前执行自定义清理任务。

**Note**

在 JSF 中，你不能依赖标准的`ServletContextListeners`来执行上述任务，因为`ServletContextListeners`可能在 JSF 应用程序启动之前运行。

以下示例向您展示了如何在 JSF 2.0 中创建一个`PostConstructApplicationEvent`和`PreDestroyApplicationEvent`系统事件。

## 1. 实现 `SystemEventListener`

创建一个实现`javax.faces.event.SystemEventListener`的类，并为您的定制后配置和清理任务覆盖`processEvent()`和`isListenerForSource()`方法。

```java
package com.mkyong;

import javax.faces.application.Application;
import javax.faces.event.AbortProcessingException;
import javax.faces.event.PostConstructApplicationEvent;
import javax.faces.event.PreDestroyApplicationEvent;
import javax.faces.event.SystemEvent;
import javax.faces.event.SystemEventListener;

public class FacesAppListener implements SystemEventListener{

  @Override
  public void processEvent(SystemEvent event) throws AbortProcessingException {

	if(event instanceof PostConstructApplicationEvent){
		System.out.println("PostConstructApplicationEvent is Called");
	}

	if(event instanceof PreDestroyApplicationEvent){
		System.out.println("PreDestroyApplicationEvent is Called");
	}

  }

  @Override
  public boolean isListenerForSource(Object source) {
	//only for Application
	return (source instanceof Application);

  }	

}
```

## 2. 注册系统事件

在`faces-config.xml`文件中注册`PostConstructApplicationEvent`和`PreDestroyApplicationEvent`系统事件，如下所示：

*faces-config.xml*

```xml
<?xml version="1.0" encoding="UTF-8"?>
<faces-config

    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://java.sun.com/xml/ns/javaee 
    http://java.sun.com/xml/ns/javaee/web-facesconfig_2_0.xsd"
    version="2.0">
    <application>

    	<!-- Application is started -->
    	<system-event-listener>
		<system-event-listener-class>
			com.mkyong.FacesAppListener
		</system-event-listener-class>
		<system-event-class>
			javax.faces.event.PostConstructApplicationEvent
		</system-event-class>    					
    	</system-event-listener> 	 

    	<!-- Before Application is shut down -->
    	<system-event-listener>
		<system-event-listener-class>
			com.mkyong.FacesAppListener
		</system-event-listener-class>
		<system-event-class>
			javax.faces.event.PreDestroyApplicationEvent
		</system-event-class>    					
    	</system-event-listener> 	 

    </application>
</faces-config>
```

## 3. 演示

运行您的 JSF 应用程序。`processEvent()`方法在您的 JSF 应用程序启动后执行，见下图：

![jsf2-PostConstructApplicationEvent-example](img/972fb758672ac4d6767898288ca57dcd.png "jsf2-PostConstructApplicationEvent-example")

**Note**

然而，`PreDestroyApplicationEvent`并不是真正可靠的，因为如果 JSF 被异常关闭，它不会运行。例如，Java 进程被系统管理员杀死，这种情况经常发生。所以，请明智地使用这个系统事件。

## 下载源代码

下载链接 – [JSF-2-PostConstructApplicationEvent-Example.zip](http://web.archive.org/web/20210319060310/http://www.mkyong.com/wp-content/uploads/2010/11/JSF-2-PostConstructApplicationEvent-Example.zip) (9KB)

## 参考

1. [JSF 2 `PostConstructApplicationEvent` JavaDoc](http://web.archive.org/web/20210319060310/https://javaserverfaces.dev.java.net/nonav/docs/2.0/javadocs/javax/faces/event/PostConstructApplicationEvent.html)
2. [JSF 2 `PreDestroyApplicationEvent` JavaDoc](http://web.archive.org/web/20210319060310/https://javaserverfaces.dev.java.net/nonav/docs/2.0/javadocs/javax/faces/event/PreDestroyApplicationEvent.html)

Tags : [jsf2](http://web.archive.org/web/20210319060310/https://mkyong.com/tag/jsf2/)
