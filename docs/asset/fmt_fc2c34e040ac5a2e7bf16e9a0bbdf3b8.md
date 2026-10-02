
# 数据预处理与特征工程

## 引言

在机器学习工作流中，数据预处理和特征工程是至关重要的步骤。本章将介绍如何使用 Apache Spark 的 `ml` 库在 Java 中执行常见的数据预处理任务，包括分类变量编码、离群值处理和特征工程。

## 分类变量编码

### StringIndexer

`StringIndexer` 将字符串标签列编码为标签索引列。以下是在 Java 中使用 `StringIndexer` 编码 Spark DataFrame 中的类别变量的示例：

```java
import org.apache.spark.ml.feature.StringIndexer;
import org.apache.spark.sql.Dataset;
import org.apache.spark.sql.Row;
import org.apache.spark.sql.SparkSession;

SparkSession spark = SparkSession.builder().getOrCreate();
Dataset<Row> df = spark.createDataFrame(Arrays.asList(
new Row("a", 1.0),
new Row("b", 2.0),
new Row("c", 3.0),
new Row("a", 4.0),
new Row("b", 5.0)),
new StructType(new StructField[] {
new StructField("category", DataTypes.StringType, false,
Metadata.empty()),
new StructField("value", DataTypes.DoubleType, false,
Metadata.empty())
));

StringIndexer indexer = new StringIndexer()
.setInputCol("category")
.setOutputCol("categoryIndex");

StringIndexerModel indexModel = indexer.fit(df);
Dataset<Row> indexedData = indexModel.transform(df);
indexedData.show();
```

### OneHotEncoder

`OneHotEncoder` 将标签索引列编码为二进制向量列。它接受以下参数：

- `inputCol`: 输入列的名称
- `outputCol`: 输出列的名称

以下是在 Java 中使用 `OneHotEncoder` 编码 Spark DataFrame 中的类别变量的示例：

```java
import org.apache.spark.ml.feature.OneHotEncoder;
import org.apache.spark.sql.Dataset;
import org.apache.spark.sql.Row;
import org.apache.spark.sql.SparkSession;

SparkSession spark = SparkSession.builder().getOrCreate();
// ... (df 定义如上) ...

OneHotEncoder encoder = new OneHotEncoder()
.setInputCol("categoryIndex")
.setOutputCol("categoryVector");
OneHotEncoderModel encoderModel = encoder.fit(indexedData);
Dataset<Row> encodedData = encoderModel.transform(indexedData);
encodedData.show();
```

上一个示例使用 `StringIndexer` 将类别变量编码为索引，然后使用 `OneHotEncoder` 将索引编码为二进制向量。

**注意**：你应该在训练数据上拟合编码器，然后使用它来转换训练数据和测试数据。

## 删除离群值

在 Apache Spark 中有多种方法可以删除离群值。以下是一些选项：

### 删除异常值的行

你可以使用 `DataFrame` 类的 `filter` 方法删除具有异常值的行。

示例代码：

```java
import org.apache.spark.sql.Dataset;
import org.apache.spark.sql.Row;
import org.apache.spark.sql.SparkSession;
SparkSession spark = SparkSession.builder().getOrCreate();
Dataset<Row> df = spark.createDataFrame(Arrays.asList(
new Row("a", 1.0),
new Row("b", 2.0),
new Row("c", 3.0),
new Row("a", 4.0),
new Row("b", 5.0)),
new StructType(new StructField[] {
new StructField("category", DataTypes.StringType, false,
Metadata.empty())),
new StructField("value", DataTypes.DoubleType, false,
Metadata.empty())
));

// 删除值大于 3 的行
Dataset<Row> filteredData = df.filter("value <= 3");
filteredData.show();
```

- **将值裁剪到范围**：你可以使用 `DataFrame` 类的 `withColumn()` 方法以及 `when()` 和 `otherwise()` 函数将列的值裁剪到某个范围。例如：

```java
import org.apache.spark.sql.Dataset;
import org.apache.spark.sql.Row;
import org.apache.spark.sql.Session;
import org.apache.spark.sql.functions as functions;

SparkSession spark = SparkSession.builder().getOrCreate();
// ... (df 定义) ...

Dataset<Row> clippedData = df.withColumn("clippedValue",
functions.when(df.col("value").leq(2).geq(4), 4)
.otherwise(df.col("value")));
clippedData.show();
```

- **标准化值**：你可以使用 `ml.feature` 包中的 `StandardScaler` 类来对值进行标准化列。标准化将值缩放为零均值和单位方差。这有助于消除离群值，因为过大或过小的值将被缩放到一个更适中的范围。以下是在 Java 中使用 `StandardScaler` 对 Spark DataFrame 中的列列进行标准化的示例：

```java
import org.apache.spark.ml.StandardScaler;
import org.apache.spark.sql.Dataset;
import org.apache.spark.sql.Row;
import org.apache.spark.sql.SparkSession;
SparkSession spark = SparkSession.builder().getOrCreate();
Dataset<Row> df = spark.createDataFrame(Arrays.asList(
new Row("a", 1.0),
new Row("b", 2.0),
new Row("c", 3.0),
new Row("a", 4.0),
new Row("b", 5.0)),
new StructType(new StructField[] {
new StructField("category", DataTypes.StringType, false, Metadata.empty()),
new StructField("Value", DataTypes.DoubleType, false, Metadata.empty())
}));

StandardScaler scaler = new StandardScaler()
.setInputCol("value")
.setOutputCol("scaledValue")
.setWithMean(true);
StandardScalerModel scalerModel = scaler.fit(df);
Dataset<Row> scaledData = scalerModel.transform(df);
scaledData.show();
```

前面的示例标准化了 `value` 列的值并将结果存储在名为 `scaledValue` 的新列中。`withStd` 和 `withMean` 参数分别控制是否按标准差缩放值以及减去均值。

## 特征工程

特征工程是从现有数据中提取和创建新特征的过程，以提高机器学习模型的预测能力。在 Apache Spark 中，你可以使用 `ml` 库来执行各种特征工程任务。

以下是在 Apache Spark 中可以执行的特征工程任务的示例：

- **分类变量编码**：你可以使用 `ml.feature` 包中的 `StringIndexer` 和 `OneHotEncoder` 类分别将分类变量编码为标签索引或二进制向量。

- **缩放或归一化数值变量**：你可以使用 `ml.feature` 包中的 `MinMaxScaler` 类将数值变量缩放或归一化为零均值和单位方差，或者缩放到 0 到 1 之间的范围。

- **缺失值填充**：你可以使用 `ml.feature` 包中的 `Imputer` 类通过用列的均值、中位数或众数来填充数据集中的缺失值。

- **从文本中提取特征**：你可以使用 `ml.feature` 包中的 `Tokenizer`、`HashingTF` 和 `IDF` 类分别通过对文本进行分词、对标记进行哈希以及根据其逆文档频率缩放哈希值从文本数据中提取特征。

- **从图像中提取特征**：你可以使用 `ml.image` 包中的 `ImageSchema` 和 `ImageTransformer` 类通过将图像转换为指定格式并提取像素值从图像中提取特征。

## 本章小结

在本章中，我们学习了如何处理数据。介绍了不同的数据类别。我们还理解了数据集以及如何生成它们。最后，我们学习了预处理以及在数据预处理期间执行的不同任务。

在下一章——*数据可视化*中，你将学习 Java 对于机器学习应用的重要性，以及你可以用于实现不同机器学习算法的各种库。

## 问题

1. Java 中不同的数据类型有哪些？
2. 什么是数据集？写下数据集的不同特征。
3. 写出生成数据集的三种方法。
4. 数据预处理是指什么？写下数据集上执行的一些常见预处理任务。
5. 什么是特征工程？

## 记忆点

- Java 中有多种数据类型，可以分类为数值、文本或对象类型。
- 整数类型包括 `byte`、`short`、`int` 和 `long`，它们可以存储不同大小的整数。
- 浮点类型包括 `float` 和 `double`，它们可以存储不同大小和精度的小数。
- *数据集*是一个为了特定目的而组织和结构化的数据集合。
- 数据可以使用多种方法生成，包括数据采集、爬取、生成合成数据等。
- 数据预处理是指为分析或建模准备数据集而采取的步骤。Apache Spark 是一个流行的大数据处理开源平台，为数据预处理提供了许多工具和库。

# 第 3 章 数据可视化

## 引言

本章将深入探讨数据可视化的复杂性，强调其在揭示模式、趋势和离群值方面的关键作用，以促进明智的决策和见解的有效传播。在我们开始这一探索时，意识到可视化在赋能分析师和利益相关者从现有信息中获取可操作智能方面的关键作用至关重要。通过将抽象数据转换为视觉易读的格式，数据可视化充当数据解释的通用语言。

我们进入图形表示世界的中心是开源库 `JFreeChart`。虽然 Python 生态系统中著名的 `Matplotlib` 或 `Seaborn` 等替代方案可能很常见，但我们选择 `JFreeChart` 是基于在 Java 环境中的多功能性、易用性和强大功能。本介绍为全面的探索奠定了基础，涵盖了条形图、直方图、折线图、散点图、箱图、时间序列图和其他高级可视化工具的动态潜力。我们的共同目标是赋予爱好者揭示故事的能力。

## 结构

在本章中，我们将涵盖以下主题：

- 图表和投影类型
- `JFreeChart` 简介
- 条形图
- 直方图
- 折线图
- 散点图
- 时间序列图
- 箱图
- 饼图
- 高级可视化工具

## 图表和投影类型

分析中使用了多种类型的图表和投影来视觉化和总结数据。以下是一些示例：

- **条形图**：条形图是具有矩形条的图表，其长度与其表示的值成正比。用于比较不同的类别或组。
- **直方图**：直方图是表示连续数据分布的图表。用于显示频率。
- **折线图**：折线图通过直线连接的一系列点显示数据。用于显示随时间变化的趋势。
- **散点图**：散点图使用点表示两个不同变量值的图表。用于显示变量之间的关系。
- **时间序列图**：时间序列图用于可视化随时间变化的数据。时间序列是在定期间隔内测量的数据点集合。时间序列图的 x 轴表示时间，y 轴表示数据点的值。
- **箱图**：箱图通过四位数表示一组连续数据的分布的图表。用于显示离散程度并识别离群值。
- **饼图**：饼图是以圆形格式表示数据的图表，饼的每个部分代表不同的类别或数据比例。用于显示比例或百分比。

## 柱状图

柱状图是一种数据的图形表示形式，它使用条形来表示不同的类别或组，或者通过条形的高度或长度来表示与这些类别或组相关的数据。柱状图广泛用于显示不同数据集之间的比较。

`JFreeChart` 是一个用于创建图表和图形的免费开源 Java 库。它支持多种图表类型，包括柱状图。要使用 `JFreeChart` 创建柱状图，您需要执行以下步骤：

1. **创建数据集**：数据集包含要可视化的数据。对于柱状图，您可以使用 `JFreeChart` 提供的内置数据集类之一，例如 `DefaultCategoryDataset`。
2. **创建图表**：图表是表示图表的主要对象。对于柱状图，您可以使用 `JFreeChart` 构造函数并传递标题、x 轴标签、y 轴标签和数据集。
3. **创建绘图区域**：绘图区域是控制数据可视化的对象。对于柱状图，您可以使用 `CategoryPlot` 类。
4. **创建渲染器**：渲染器负责在图表上绘制条形。对于柱状图，您可以使用 `BarRenderer` 类。
5. **显示图表**：最后，您可以在 Swing 窗口中显示图表，或将其保存为图像文件。

下面是一个使用 `JFreeChart` 创建简单柱状图的示例代码段：

```java
import org.jfree.chart.ChartFactory;
import org.jfree.chart.ChartFrame;
import org.jfree.chart.JFreeChart;
import org.jfree.chart.plot.CategoryPlot;
import org.jfree.chart.plot.PlotOrientation;
import org.jfree.data.category.DefaultCategoryDataset;
import org.jfree.chart.renderer.category.BarRenderer;

public class BarChartExample {
    public static void main(String[] args) {
        // Step 1: 创建数据集
        DefaultCategoryDataset dataset = new DefaultCategoryDataset();
        dataset.setValue(50, "Sales", "January");
        dataset.setValue(70, "Sales", "February");
        dataset.setValue(90, "Sales", "March");

        // Step 2: 创建图表
        JFreeChart chart = ChartFactory.createBarChart("Monthly\nSales", "Month", "Sales", dataset, PlotOrientation.VERTICAL,
        false, true, false);

        // Step 3: 创建绘图区域
        CategoryPlot plot = chart.getCategoryPlot();

        // Step 4: 创建渲染器
        BarRenderer renderer = (BarRenderer) plot.getRenderer();
        renderer.setSeriesPaint(0, java.awt.Color.blue);

        // Step 5: 显示图表
        ChartFrame frame = new ChartFrame("Monthly Sales", chart);
        frame.pack();
        frame.setVisible(true);
    }
}
```

在这个示例中，我们首先创建一个 `DefaultCategoryDataset` 并向其添加一些数据。然后，我们创建一个 `JFreeChart` 对象，传递数据集、图表标题、x 轴标签、y 轴标签和绘图方向。接着，我们创建一个 `CategoryPlot` 对象，它负责在图表上可视化这些数据。最后，我们创建一个 `BarRenderer` 来渲染图表上的条形，并在 `ChartFrame` 中显示图表。

代码的输出所示如图 3.1：

![](img/5aebcd8930cbace5a8e0362244fbe703_84_0)
