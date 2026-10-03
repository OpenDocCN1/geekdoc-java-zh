
| 16 | 0 | 1935 | | 64220 | 43684 | | G3k | mj86 | | -1 | -1 | -1 |
| 16 | 0 | 1935 | | 64220 | 43684 | | G3k | mj86 | | -1 | -1 | -1 |
| 12 | 6 | 820 | 0 | 121385 | 69134 | | | | -1 | -1 | -1 |
| 2 | 72 | 0 | 8 | 416340 | 357038 | | | | -1 | -1 | -1 |
| 114 | 5967 | -28 | 0 | 347248 | | G3k | am7c | | -1 | -1 | -1 |
| 0 | 0 | 15118 | 56 | 0 | 150550 | | | | -1 | -1 | -1 |
| 10 | 0 | 1935 | | 64220 | 43684 | | G3k | mj86 | | -1 | -1 | -1 |
| 16 | 0 | 1935 | | 64220 | 43684 | | G3k | mj86 | | -1 | -1 | -1 |

该表格描绘了 25 个实例，即客户，每个客户由 250 个属性描述。例如，仅显示了 10 个属性。数据集包含许多缺失值或空属性。最后三列对应三个类别标签，对应真实情况，即客户是否需要服务商（流失）、购买了服务（购买意愿）或购买了升级（向上销售）。

## 评估

提交根据三个任务的 ROC 曲线下面积（AUC）的算术平均值进行评估，即流失、购买意愿和向上销售。ROC 曲线通过绘制用于确定分类结果的任意阈值的灵敏度对特异性来展示模型的性能（参见第 1 章《机器学习快速入门》）。现在，AUC 与此曲线下的面积有关，这意味着面积越大，分类器越好。大多数工具箱（包括 Weka）都提供了计算 AUC 分数的 API。

## 朴素贝叶斯分类器基准

根据挑战规则，参赛者必须超过基础朴素贝叶斯分类器，该分类器假设特征是独立的（参见第 1 章《机器学习快速入门》）。

KDD Cup 组织者运行了原始朴素贝叶斯分类器，没有进行任何特征选择或超参数调整。对于大型数据集，朴素贝叶斯在测试集上的总体得分如下：

- 流失问题：AUC = 0.6468
- 购买意愿问题：AUC = 0.6453
- 向上销售问题：AUC = 0.7211

## 获取数据

在 KDD Cup 网页（http://kdd.org/kdd-cup/view/kdd-cup-2009/Data）上，你应该看到一个如截图所示的页面。首先，在 **Small version (230 var)** 标题下，下载 `orange_small_train.zip`。接下来，下载与该训练数据相关的三组真实标签。在 **Real binary targets (small)** 标题下可以找到以下文件：

- `orange_small_train_appencency.labels`
- `orange_small_train_churn.labels`
- `orange_small_train_upselling.labels`

保存并解压红框中的所有文件，如下截图所示：

![](img/19ac99d70883ac011b12e9f3fe27f16b_94_0.png)

在接下来的章节中，我们将首先将数据加载到 Weka 中并使用朴素贝叶斯进行基础建模，以获得自己的基准 AUC 分数。稍后，我们将研究更高级的建模技术和技巧。

## 加载数据

我们将直接从 .csv 格式将数据加载到 Weka。为了此目的，我们将编写一个函数，接受数据文件路径和真实标签文件路径。该函数将加载两个数据集并删除空属性：

```java
public static Instances loadData(String pathData, String pathLabels) throws Exception {
```

首先，我们使用 `CSVLoader()` 类加载数据。此外，我们指定 `\t` 为字段分隔符，并强制将最后 40 个属性解析为名值（nominal）：

```java
// Load data
CSVLoader loader = new CSVLoader();
loader.setFieldSeparator("\t");
loader.setNominalAttributes("191-last");
loader.setSource(new File(pathData));
Instances data = loader.getDataSet();
```

> 该类接受许多额外的参数，用于指定列分隔符、字符串包含符、是否存在表头等。完整文档可参阅此处：
> http://weka.sourceforge.net/doc/weka/weka/converters/CSVLoader.html

接下来，某些属性不包含单一值，Weka 会自动将它们识别为 String 属性。我们不需要它们，因此可以安全地使用 `RemoveType` 过滤器删除它们。此外，我们指定了 `-T` 参数，用于删除特定类型的属性以及我们要删除的属性类型：

```java
// remove empty attributes identified as String attribute
RemoveType removeString = new RemoveType();
removeString.setOptions(new String[]{"-T", "string"});
removeString.setInputFormat(data);
Instances filteredData = Filter.useFilter(data, removeString);
```

或者，我们也可以使用 `Instances` 类实现的 `deleteStringAttributes()` 方法，它的效果相同，例如 `data.deleteStringAttributes()`。

## 使用集成进行客户关系预测

现在，我们将加载数据并为其分配类别标签。我们将再次利用 `CSVLoader`，并指定文件没有表头行，即设置 `setNoHeaderRowPresent(true)`：

```java
// Load labels
loader = new CSVLoader();
loader.setFieldSeparator("\t");
loader.setNoHeaderRowPresent(true);
loader.setNominalAttributes("first-last");
loader.setSource(new File(pathLabels));
Instances labels = loader.getDataSet();
```

一旦我们加载了两个文件，就可以通过调用 `Instances.mergeInstances` 静态方法合并它们。该方法返回一个新数据集，包含第一个数据集的属性加上第二个数据集的属性。注意，两个数据集中的实例数量将是：

```java
// Append label as class value
labeledData = Instances.mergeInstances(filteredData, labels);
```

最后，我们设置属性（即我们刚刚添加的属性）为目标变量并返回结果的数据集：

```java
// set the attribute as class
labeledData.setClassIndex(labeledData.numAttributes() - 1);

System.out.println(labeledData.toString());
return labeledData;
```

该函数输出如下所示的摘要并返回带标签的数据数据集：

**Relation Name:** orange_small_train.data-weka.filters.unsupervised.attribute.RemoveType-Tstring_orange_small_train_churn.txt

**Num Instances:** 50000

**Num Attributes:** 215

| Name | Type | Num | Int | Real | Missing | Unique | Dist |
|---|---|---|---|---|---|---|---|
| Var1 | Num | 0% | 1% | 0% 48759 / 99% | 8 / 0% | 18 | |
| Var2 | Num | 0% | 2% | 0% 48759 / 98% | 1 / 0% | 2 | |
| Var3 | Num | 0% | 2% | 0% 48760 / 98% | 104 / 0% | 146 | |
| Var4 | Num | 0% | 3% | 0% 48421 / 97% | 1 / 0% | 4 | |

## 基础建模

在本节中，我们将遵循 KDD Cup 采用的方法来实现自己的基准模型。

## 评估

在本节中，我们将遵循 KDD Cup 采用的方法来实现自己的基准模型。然而，在进行建模之前，让我们更仔细地查看评估。评估函数接受一个模型，并报告如下 AUC AUC：

```java
public static double[] evaluate(Classifier model) throws Exception {
    double[] results = new double[3];
    String[] labelFiles = {"churn", "appency", "upselling"};
    double overallScore = 0.0;

    for (int i = 0; i < labelFiles.length; i++) {
        // First, we load the data
        Instances data = loadData(pathData, "orange_small_train_" + labelFiles[i] + ".labels");

        // Next, we will process the data
        Evaluation eval = new Evaluation(data);
        eval.crossValidate(model, data, 5, new Random(1));

        // Finally, we get the results
        results[i] = eval.areaUnderCurve();
        overallScore += results[i];
    }
    return results;
}
```

## 基于集成学习的客户关系预测

## 在开始之前

对于此任务，我们需要一个额外的 Weka 插件 `ensembleLibrary`。Weka 3.7.2 或更高版本支持主要由学术社区开发的外部插件。WEKA 插件列表可以在 http://weka.sourceforge.net/~packageMetaData 处找到，如下所示所示：

![](img/19ac99d70883ac011b12e9f3fe27f16b_100_0.png)

重要提示：确保你的 CLASSPATH 中没有旧版本的 Weka（<3.7.2）。例如通过：

### 插件安装

- 可从 GUIChooser 的“Tools（工具）”菜单使用的 GUI 插件管理器
- `weka.jar`
- 对于命令行插件管理器，请输入：
  `weka.core.PackageManager -`

### 从命令行运行包好的算法

也支持子网匹配。

`weka.runBayes`

### 可用插件 (151个)

| AIDE | 分类 | 平均化 N 依赖性估计器（包含 A1DE 和 A2DE） |
| ArabicStemmers, LightStemmers | 预处理 | 基于上下文感知回归学习器 |
| CMR | 回归, 集成学习 | CHIRP: 基于事务数据复合超立方的新分类器 |
| CHIRP | 分类 | CLOP: 一种用于事务数据的快速高效聚类算法 |
| CLOP | 聚类 | 一种探索属性空间的差异算法 |
| CVAttributeEval | 属性选择 | |

在 http://downloads.sourceforge.net/weka/ensembleLibrary1.0.5.zip?download 并下载最新的 `ensembleLibrary` 插件。

解压包后，找到 `ensembleLibrary.jar` 并将其导入到你的代码中，如下：

```java
import weka.classifiers.meta.EnsembleSelection;
```

## 数据预处理

首先，我们将利用 `weka.filters.unsupervised.attribute.RemoveUseless` 过滤器，它的功能正如其名。它会移除变化不大的属性，例如，移除常量属性，并随机移除变化过大的属性。最大方差（仅适用于名目属性）通过 `-M` 参数指定。默认参数为 99%，这意味着如果超过 99% 的实例具有唯一的属性值，则该属性将被移除如下：

```java
RemoveUseless removeUseless = new RemoveUseless();
removeUseless.setOptions(new String[] {"-M", "99%"}); // 阈值
removeUseless.setInputFormat(data);
data = Filter.useFilter(data, removeUseless);
```

接下来，我们将使用 `weka.filters.unsupervised.attribute.ReplaceMissingValues` 过滤器，通过训练数据的众数（名目属性）和平均值（数值属性）替换数据集中的所有缺失值。通常情况下，替换缺失值时应谨慎，并考虑属性的含义和上下文：

```java
ReplaceMissingValues fixMissingValues = new ReplaceMissingValues();
fixMissingValues.setInputFormat(data);
data = Filter.useFilter(data, fixMissingValues);
```

最后，我们将对数值属性进行离散化，即使用 `weka.filters.unsupervised.attribute.Discretize` 过滤器将数值属性转换为区间。通过 `-B` 选项，我们将数值属性划分为四个区间，通过 `-R` 选项指定属性的范围（仅对数值属性进行离散化）：

```java
Discretize discretizeNumeric = new Discretize();
discretizeNumeric.setOptions(new String[] {
    "-B", "4", // 分箱数量
    "-R", "first-last"}); // 属性范围
discretizeNumeric.setInputFormat(data);
data = Filter.useFilter(data, discretizeNumeric);
```

## 属性选择

在下一步中，我们将只选择具有信息性的属性，即可能有助于预测的属性。解决此问题的标准方法是检查每个属性携带的信息增益。我们将使用 `weka.attributeSelection.AttributeSelection` 过滤器，它需要两个额外方法：评估器（evaluator），即如何计算属性的有用性；以及搜索算法（search algorithms），即选择属性子集。

在我们的案例中，首先初始化实现信息增益计算的 `weka.attributeSelection.InfoGainAttributeEval`：

```java
InfoGainAttributeEval eval = new InfoGainAttributeEval();
Ranker search = new Ranker();
```

为了仅选择高于某些阈值的属性，我们初始化 `weka.attributeSelection.Ranker`，对信息增益高于特定阈值的属性进行排序。我们通过 `-T` 参数指定此，同时保持较低的阈值以保留属性的某些信息：

```java
search.setOptions(new String[] { "-T", "0.001" });
```

![](img/19ac99d70883ac011b12e9f3fe27f16b_102_0.png)

接下来，我们可以初始化 `AttributeSelection` 类，设置评估器和排序器，并将属性选择应用到我们的数据集：

```java
AttributeSelection attSelect = new AttributeSelection();
attSelect.setEvaluator(eval);
attSelect.setSearch(search);
```

```java
// 应用属性选择
attSelect.selectAttributes(data);
```

最后，通过调用 `reduceDimensionality(data)` 移除未被选中的属性。

```java
// 移除未被选中的属性
data = attSelect.reduceDimensionality(data);
```

最后，我们留下了：

## 模型选择

多年来，机器学习领域的从业者开发了多种算法。为了完成示例，我们添加以下：

```java
EnsembleLibrary ensembleLib = new EnsembleLibrary();
```

## 客户关系预测

接下来，通过实例化 `weka.classifiers.meta.EnsembleSelection` 类来初始化集成选择算法。让我们先回顾以下选项：

- `-L <path/to/modelLibrary>`: 指定模型库文件。
- `-W <path/to/working/directory>`: 指定存储所有模型的工作目录。
- `-B <numBags>`: 设置包，即运行集成选择算法的迭代次数。
