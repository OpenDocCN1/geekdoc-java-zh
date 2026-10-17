
```java
public NodeP find(String gtin) {
    NodeP current = root;
    if (current == null)
        return null;

    while (current != null) {
        if (gtin.compareTo(current.getGtin()) < 0) {
            current = current.getLeft();
        } else if (gtin.compareTo(current.getGtin()) > 0) {
            current = current.getRight();
        } else {
            return current;
        }
    }
    return null;
}
```

### Tests

```java
@Test
public void test_find() {
  tree.insert("gt1", Arrays.asList(product1));
  tree.insert("gt2", Arrays.asList(product2));
  tree.insert("gt3", Arrays.asList(product3, product4));
  tree.insert("gt4", Arrays.asList(product5));
  tree.insert("gt5", Arrays.asList(product6, product7, product8));
  assertEquals(null, tree.find("gt0"));
  tree.insert("gt6", Arrays.asList(product9));
  assertTrue(tree.find("gt6") != null)
}
```

```java
private NodeP root;

public void insert(String gtin, int productId, String name) {
    Product product = new Product(productId, name);
    NodeP newNode = new NodeP(gtin, product);

    if (root == null) {
        root = newNode;
    } else {
        NodeP current = root;
        NodeP parent;
        while (true) {
            parent = current;
            if (gtin.compareTo(current.getGtin()) < 0) {
                current = current.getLeft();
                if (current == null) {
                    parent.setLeft(newNode);
                    return;
                }
            } else if (gtin.compareTo(current.getGtin()) > 0) {
                current = current.getRight();
                if (current == null) {
                    parent.setRight(newNode);
                    return;
                }
            } else {
                current.setData(product); //already exists
                return;
            }
        }
    }
    return;
}

public String inOrderTraversal(NodeP localRoot, StringJoiner stringJoiner) {
    if (localRoot != null) {
        inOrderTraversal(localRoot.getLeft(), stringJoiner);
        stringJoiner.add(localRoot.getData().getName());
        inOrderTraversal(localRoot.getRight(), stringJoiner);
    }
    return stringJoiner.toString();
}
```

### 测试

```java
import java.util.StringJoiner;
public class TreeADTTest {
    private TreeADT tree;

@Before
public void setup() {
    tree = new TreeADT();
}

@Test
public void test_traverseTree() {
    tree.insert("051414", 12, "apple");
    tree.insert("0301712", 14, "cherry");
    tree.insert("0814101", 13, "mango");
    tree.insert("0401312", 19, "orange");
    tree.insert("0911741", 11, "banana");
    tree.insert("0617411", 16, "grape");
    tree.insert("0210417", 18, "kiwi");
    StringJoiner stringJoiner = new StringJoiner(" -> ", "[", "]");
    assertEquals("kiwi -> cherry -> orange -> apple -> grape -> mango -> banana",
        tree.inOrderTraversal(tree.getRoot(), stringJoiner));
}
}
```

# 图

## 9.0 基础

图（Graph）是一种由节点（顶点）和边（边）组成的非线性数据结构。它的形状取决于我们试图解决的物理或抽象问题。例如，如果节点代表城市，那么连接城市的路线可能由无向边定义。但如果节点代表完成项目的任务，那么它们的边就必须是有向的，以指示哪个任务必须在另一个任务之前完成。

## 术语

图可以模拟将在德国安装的超高速环（Hyperloop）交通。

![](img/60b89ebeda3428b712e02fb7e9fd8b5b_81_0.png)

图 9.0 图 - 术语

图仅显示顶点和边之间的关系，这里最重要的是哪些边连接到哪个顶点。我们也可以说，图模拟了对象之间的连接。

## 邻接

当单条边连接两个顶点时，它们就是相邻的或邻居。在图中，由柏林（Berlin）和莱比锡（Leipzig）代表的顶点是相邻的，但柏林和德累斯顿（Dresden）这两个城市并不相邻。

## 路径

路径是边的序列。图中显示了从柏林到慕尼黑（München）经过莱比锡和纽尼堡（Nürnberg）的路径。那么路径就是柏林、莱比锡、纽尼堡、慕尼黑。

## 连通图

如果每个顶点到每个顶点至少有一个路径，则图是连通的。图中所有城市都是连接的。

## 有向图和加权图

当边具有方向时，图是有向的。在图中，它是无向的，因为超高速环可以从任何方向行驶。从柏林到莱比锡是一样的。

当边赋予权重时，图被称为加权图，例如城市之间的距离可以被加权。图回答了一个问题：从给定城市可以到达哪些城市？我们需要实现算法。搜索图有两种方法：深度优先搜索（DFS）和广度优先搜索（BFS）。

## 9.1 深度优先搜索 (DFS)

实现深度优先搜索以遍历图数据结构 ![](img/60b89ebeda3428b712e02fb7e9fd8b5b_82_0.png

### 解决方案

深度优先搜索（DFS）是一种遍历图的算法。该算法从根（选择任意城市作为根）开始，并沿着路径尽可能地探索。图 9.1.1 显示了选择柏林作为根的步骤。

### 实现算法

建模问题：我们需要一个支持包含任何数据的对象。在这个顶点内部，我们定义了一个布尔变量以避免循环，我们在访问它时将其标记为已访问。图 9.1.1 显示了顶点实现。

### 9.1.1 - 顶点类

```java
public class Vertex {
    private String name;
    private boolean visited;

    public Vertex(String name) {
        this.name = name;
        this.visited = false;
    }
    // 省略 setters 和 getter
```

### 邻接矩阵

我们有两种方法来建模顶点如何连接（边）：邻接矩阵和邻接表。对于这种算法，我们在 N 个顶点的图中创建一个 NxN 的二维数组。两个顶点（城市）之间的边由 1 表示。没有连接由 0 表示。

| 柏林 | 莱比锡 | 德累斯顿 | 纽尼堡 |

|---|---|---|---|

| 柏林 | 0 | 1 | 0 | 1 |

| 莱比锡 | 1 | 0 | 1 | 0 |

| 德累斯顿 | 0 | 1 | 0 | 0 |

...

表 9.1.1 邻接矩阵

例如，表格显示莱比锡与柏林、德累斯顿和纽尼堡相邻。

### 创建并初始化抽象类型

我们创建一个名为 `Graph` 的抽象类型来定义我们数据结构的行为。我们需要一个栈结构来记住已访问的顶点。栈遵循后进先出（LIFO）原则，即最后插入的城市是第一个从栈中出来的城市。我们定义 `arrayOfVertex[]` 数组来存储添加到 `Graph` 的新顶点（城市）。我们定义 `numOfVertices` 变量表示已添加到 `Graph` 的顶点数量。由于我们将向 DFS 算法传递字符串参数（城市名称），`mapOfVertex` 被用于注册键值对：城市索引。

### 9.1.2 - Graph 类

```java
public class Graph {
    private final int MAX_VERTEX = 15;
    private Vertex arrayOfVertex[]; //城市
    private Map<String, Integer> mapOfVertex;
    // 邻接矩阵：
    private int matrixAdjVertex[][];
    // 在 arrayOfVertex 中的位置：
    private int numOfVertices;
    private Stack<Integer> stack;

    public Graph() {
        arrayOfVertex = new Vertex[MAX_VERTEX];
        mapOfVertex = new ConcurrentHashMap<>();
        numOfVertices = 0;
        matrixAdjVertex = new int[MAX_VERTEX][MAX_VERTEX];
        stack = new Stack<>();
        // 初始化矩阵
        for (int i = 0; i < MAX_VERTEX; i++) {
            for (int j = 0; j < MAX_VERTEX; j++) {
                matrixAdjVertex[i][j] = 0;
            }
        }
    }
}
```

我们在 `Graph` 类内部定义了以下方法。

### 添加顶点

```java
public void addVertex(Vertex city) {
    mapOfVertex.put(city.getName(), numOfVertices);
    arrayOfVertex[numOfVertices++] = city;
}
```

`numOfVertices` 变量决定了新城市在 `arrayOfVertex` 中的位置（索引）。

### 添加边

我们在 `matrixAdjVertex` 中添加两个条目，因为两个城市是双向连接的。

```java
public void addEdge(String city1, String city2) {
    int start = mapOfVertex.get(city1);
    int end = mapOfVertex.get(city2);
    matrixAdjVertex[start][end] = 1;
    matrixAdjVertex[end][start] = 1;
}
```

这里的点在于，我们需要定义图的拓扑结构，添加顶点（城市）以及连接它们的边。

### 算法

我们的 `dfs(s)` 方法接收城市名称作为参数。然后，我们在 `HashMap` 中定位该城市的索引，将其标记为已访问并将其推入栈中。

我们遍历栈项直到它为空。这就是我们在每次迭代中中所做的：

1. 从栈顶获取顶点（`peek`）。

2. 尝试获取至少一个未访问的邻居。

3. 如果找到一个顶点，将其标记为已访问并推入栈中。

4. 如果没有找到，则弹出栈元素。

```java
// 尚未访问的相邻顶点
private int getAdjVertex(int vertex) {
    for (int adj = 0; adj < numOfVertices; adj++) {
        if (matrixOfAdjVertex[vertex][adj] == 1 &&
            arrayOfAdjVertex[adj].isVisited() == false)
            return adj; // 返回第一个相邻顶点
    }
    return -1; // 未找到顶点
}

public Map<String, Integer> getMapOfVertex() {
    return mapOfVertex;
}

public int[][] getMatrixOfAdjVertex() {
    return matrixOfAdjVertex;
}
```

### 测试 (Tests)

```java
public class GraphTest {

    Graph graph;

    @Before
    public void setup() {
        graph = new Graph();
    }

    @Test
    public void test_addvertex() {
        Vertex city = new Vertex("Berlin");
        graph.addVertex(city);
        assertTrue(graph.getMapOfVertex().size() == 1);
    }

    @Test
    public void test_addedge() {
        String city1 = "Berlin";
        String city2 = "Leipzig";
        Vertex v1 = new Vertex(city1);
        Vertex v2 = new Vertex(city2);
        graph.addVertex(v1); // 位置 0
        graph.addEdge(city1, city2); // 位置 1
        assertTrue(graph.getMatrixOfAdjVertex()[0][1] == 1);
        assertTrue(graph.getMatrixOfAdjVertex()[1][0] == 1);
    }
}
```
