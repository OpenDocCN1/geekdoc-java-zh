
# Mapstruct — Bean 映射框架

> 原文：<https://medium.com/javarevisited/mapstruct-bean-mapping-framework-7955ac60a746?source=collection_archive---------1----------------------->

[![](img/12af3c085070f8ae24c2c4bc4fc09541.png)](https://www.java67.com/2016/09/map-reduce-example-java8.html)

你有没有面对过 Java 中属性(Bean)映射的枯燥任务？你曾经需要编写服务 POJO 到 DTO 转换的代码吗？您需要为映射 API 准备一个设计吗？

> MapStruct 是满足上述需求的正确解决方案。

MapStruct 是一个代码生成器，它基于配置方法的约定，极大地简化了 Java bean 类型之间映射的实现。

在本文中，我们将讨论不同的场景及其实现和示例。

## 指数

*   为什么是 MapStruct？
*   如何实施？
*   例子—
    1.  精确名称映射(基本)
    2.  不同的名称映射
    3.  自定义对象映射
    4.  映射的自定义方法
    5.  集合映射
    6.  附加对象映射
    7.  `@BeforeMapping`和`@AfterMapping`批注

那么让我们开始吧。

## 为什么是 MapStruct？

多层应用程序通常需要不同对象模型(例如实体和 DTO)之间的映射。编写这样的映射代码是一项乏味且容易出错的任务。MapStruct 旨在通过尽可能自动化来简化这项工作。

与其他映射框架相比，MapStruct 在编译时生成 bean 映射，这确保了高性能，允许快速的开发人员反馈和彻底的错误检查。

## 如何实施？

MapStruct 是一个注释处理器，它被插入到 Java 编译器中，可以在命令行构建中使用(Maven、Gradle 等)。)以及您首选的 IDE 中。

您需要在编译器插件中添加下面的依赖项和注释标签。

### pom.xml

```
<properties>
 <org.mapstruct.version>1.4.2.Final</org.mapstruct.version>
</properties>

<dependency>
   <groupId>org.mapstruct</groupId>
   <artifactId>mapstruct</artifactId>
   <version>${org.mapstruct.version}</version>
</dependency>

<plugin>
 <groupId>org.apache.maven.plugins</groupId>
 <artifactId>maven-compiler-plugin</artifactId>
 <version>3.8.1</version>
 <configuration>
  <source>1.8</source> <!-- depending on your project -->
  <target>1.8</target> <!-- depending on your project -->
  <annotationProcessorPaths>
   <path>
    <groupId>org.mapstruct</groupId>
    <artifactId>mapstruct-processor</artifactId>
    <version>${org.mapstruct.version}</version>
   </path>
  </annotationProcessorPaths>
 </configuration>
</plugin>
```

## 1. 精确名称映射(基本)

这里我们的任务是从模型层检索`Circuit`对象，并通过创建`CircuitDto`类将其传递给持久层。所以我们将简单的`Circuit`类映射到`CircuitDto`类。

### Circuit.java

```
@Data
public class Circuit{
 private int id;
 private String name;
}
```

### CircuitDto.java

```
@Data
public class CircuitDto {
 private int id;
 private String name;
}
```

为此，我们将创建一个映射器接口。

### CircuitMapper.java

```
@Mapper(componentModel = "spring")
public interface CircuitMapper {
 CircuitDto toDto(Circuit circuit);
}
```

`@Mapper` → MapStruct 的注释创建并生成映射实现。

`componentModel = "spring"` → 在 spring 项目中生成 bean，这样我们可以很容易地将这个 bean 注释为 autowire。

因为两个类有相同的属性名，我们不需要为它写任何显式的映射。MapStruct 将包括这两个字段的映射。

为了测试这个：

### CircuitMapperTest.java

```
@Autowired
CircuitMapper circuitMapper;

@Test
public void testCircuitDtoMapping(){
    Circuit circuit = new Circuit(123, "transportBearer123");
    CircuitDto circuitDto = circuitMapper.toDto(circuit);
    assertEquals(circuit.getId(), circuitDto.getId());
    assertEquals(circuit.getName(), circuitDto.getName());
}
```

## 2. 不同的名称映射

现在让我们在两个 beans 中都包含不同的名称。

### Circuit.java

```
@Data
public class Circuit{
 private int id;
 private String name;
 private long circuitTypeId;
}
```

### CircuitDto.java

```
@Data
public class CircuitDto {
 private int id;
 private String name;
 private long circuit2circuitType;
}
```

现在，映射器将无法自动映射它。为了实现这一点，我们只需简单地提到如下的映射。

### CircuitMapper.java

```
@Mapper(componentModel = "spring")
public interface CircuitMapper {
 @Mapping(source = "circuitTypeId", target = "circuit2circuitType")
 CircuitDto toDto(Circuit circuit);
}
```

## 3. 自定义对象映射

让我们继续上面的例子，`Circuit`有它自己的子对象(`Port`)，我们需要映射它。

### 源类

```
@Data
public class Circuit{
 private int id;
 private String name;
 private long circuitTypeId;
 private Port port;
}

public class Port{
 private int id;
 private String name;
}
```

### 目标类

```
@Data
public class CircuitDto {
 private int id;
 private String name;
 private long circuit2circuitType;
 private PortDto portDto;
}

@Data
public class PortDto{
 private int id;
 private String name;
}
```

要进行子类映射，我们必须创建一个单独的映射器，如`Circuit`，然后像`uses = {PortMapper.class}`一样导入它。

### 映射器接口

```
@Mapper(componentModel = "spring")
public interface PortMapper {
 PortDto toDto(Port port);
}

@Mapper(componentModel = "spring",
  uses = {PortMapper.class})
public interface CircuitMapper {

 @Mapping(source = "circuitTypeId", target = "circuit2circuitType")
 CircuitDto toDto(Circuit circuit);
}
```

## 4. 映射的自定义方法

如果对于某个属性，我们需要自定义逻辑来映射值。我们还可以编写一个自定义的映射方法。

例如，在源`Circuit`类中，我们有一个子电路列表，而在目标`CircuitDto`类中，我们只需要一个子电路计数。

### Circuit.java

```
@Data
public class Circuit{
 private int id;
 private String name;
 private List<Circuit> childCircuits;
}
```

### CircuitDto.java

```
@Data
public class CircuitDto {
 private int id;
 private String name;
 private int noOfChildCirtcuits;
}
```

这里我们必须编写我们的自定义方法来计算子电路的大小。因此，我们可以用`@Named`编写我们的自定义方法。这可以由映射字段中的`qualifiedByName`提供。

### CircuitMapper.java

```
@Mapper(componentModel = "spring")
public interface CircuitMapper {

 @Mapping(
         source = "childCircuits", 
         target = "noOfChildCirtcuits", 
         qualifiedByName = "countChildCircuits")
 CircuitDto toDto(Circuit circuit);

 @Named("countChildCircuits")
 default int getChildCircuits(List<Circuit> childCircuits) {
      if(childCircuits == null) {
         return 0;
      }
      return childCircuits.size();
 }
}
```

## 5. 集合映射

假设我们有一个这样的属性集合，我们只是想将它映射到目标类中。例如，我们在`Circuit`类的源中有一个端口列表，我们希望将它映射到目标类中的`PortDto`列表。

### 源类

```
@Data
public class Circuit{
 private int id;
 private String name;
 private long circuitTypeId;
 private List<Port> port;
}

public class Port{
 private int id;
 private String name;
}
```

### 目标类

```
@Data
public class CircuitDto {
 private int id;
 private String name;
 private long circuit2circuitType;
 private List<PortDto> portDto;
}

@Data
public class PortDto{
 private int id;
 private String name;
}
```

要进行此列表映射，我们可以简单地在`PortMapper.class`中定义此列表映射，如下所示。

### 映射器接口

```
@Mapper(componentModel = "spring")
public interface PortMapper {
 PortDto toDto(Port port);
 List<PortDto> toPortDtoList(List<Port> ports);
}

@Mapper(componentModel = "spring",
  uses = {PortMapper.class})
public interface CircuitMapper {

 @Mapping(source = "circuitTypeId", target = "circuit2circuitType")
 CircuitDto toDto(Circuit circuit);
}
```

## 6. 附加对象映射

为了迎合这种特殊处理，MapStruct 还在映射字段中提供了一些特殊的属性。

例如，我们希望在目标类中映射固定值。像在目标`CircuitDto`类中一样，我们希望映射具有固定值“Circuit”的字段类型。

我们可以像下面这样直接映射它。

```
@Mapping(target = "type", constant = "Circuit")
```

更多的特殊属性，可以去查阅 MapStruct 的官方文档。

## 7. `@BeforeMapping`和`@AfterMapping`注释

有两个非常重要的注释非常有助于在开头或结尾迎合特殊要求。

`@BeforeMapping` — 在我们开始映射之前，如果我们想要添加一些验证或属性/集合创建。

`@AfterMapping` — 在映射之后，如果我们想对目标类做最后的修改，我们可以把它作为这个方法的一部分来做。

例如，在下面的代码片段中，我们已经在`@BeforeMapping`中初始化了`List<Circuit>`，并且基于子电路的计数，我们已经在`@AfterMapping`中设置了`isChildCircuitAvailable`布尔标志。

```
@Mapper(componentModel = "spring",
  uses = {PortMapper.class})
public interface CircuitMapper {

 @BeforeMapping
 default void setChildCircuitList(Circuit circuit) {
  if(circuit.getChildCircuits == null){
   circuit.setChildCircuits( new ArrayList<Circuit>());
  }
 }

 @Mapping(source = "circuitTypeId", target = "circuit2circuitType")
 CircuitDto toDto(Circuit circuit);

 @AfterMapping
 default void setisChildCircuitsAvailable(CircuitDto circuitDto) {
  if(circuitDto.getNoOfChildCirtcuits > 0){
   circuitDto.isChildCircuitsAvailable(true);
  }
 } 
}
```

## 结论

本文描述了如何利用 MapStruct 库以一种安全而优雅的方式显著减少我们的样板代码。

正如在例子中看到的，MapStruct 提供了大量的功能和配置，允许我们以一种简单快速的方式创建从基本到复杂的映射器。

要了解更多关于 MapStruct 的信息，你可以点击下面的链接。

感谢阅读。享受…！！！😊😊



> 官网—[https://mapstruct.org/](https://mapstruct.org/)
>
> 安装指南—[https://mapstruct.org/documentation/installation/](https://mapstruct.org/documentation/installation/)
>
> 参考指南—[https://mapstruct.org/documentation/reference-guide/](https://mapstruct.org/documentation/reference-guide/)
>
> 例子—[https://github.com/mapstruct/mapstruct-examples](https://github.com/mapstruct/mapstruct-examples)
