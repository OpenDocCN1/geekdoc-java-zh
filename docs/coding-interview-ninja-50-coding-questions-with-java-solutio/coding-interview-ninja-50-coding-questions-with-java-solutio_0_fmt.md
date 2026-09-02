
# 编程面试忍者：50 道带 Java 解决方案的编程题，助力你的面试实践指南

![](img/00002.jpeg)

# 引言

获得你梦想中的软件工程师工作可能取决于你在编码面试中的表现。这可能是你面试过程中最重要的一部分。

你的招聘官会建议你重新复习大学的算法和数据结构教科书，以温习计算机科学的基础知识。虽然这是必要的，但远远不够。在算法书中看到的问题类型并不是为了让你在短短 45 分钟的压力下解决而设计的。准备编码面试最好的方法是练习与你可能被要求解决的题目类似的题目。这本书的目的就是：为你提供一些面试编码示例题以及相应的解决方案代码。

由于每家公司的面试流程和出题风格略有不同，强烈建议你在完成本书中题目的练习后，去 CareerCup 和 Glassdoor 等网站查看最近面试候选者遇到的题目。

不要忘记，你不需要知道所有知识，也不需要完美地解决提出的每一个问题才能进入面试流程的下一个阶段。大多数情况下，面试官只是想看到你在处理新问题时的思考过程，以及你的编码熟练程度。

最后，如果你发现任何你认为错误的地方，请随时与我联系。

祝你面试顺利！

# 准备

在开始练习编码面试之前，你需要温习一些计算机科学的基础知识。在我看来，以下是你需要研究的最重要主题列表。这个列表并非完整。

## 编程语言

你必须非常精通你选择的一种编程语言。熟练掌握你选择的语言将让你有更多时间思考实际问题，而不是思考如何实现你脑海中的解决方案。科技公司中最流行的语言是 `Java`、`C/C++` 和 `Python`。

## 运行复杂度

大多数情况下，面试官会询问你程序的运行时间，即大 O 复杂度，也就是运行的最坏情况分析。在某些情况下，例如处理大 O 分析不佳的流行算法（如 `quicksort`），了解其平均运行时间也是有用的。

## 数据结构

### 链表

链表中的每个节点都包含一个数据元素和一个指向下一个节点的指针。链表节点的示例定义如下：

```java
class LLNode {
  int data;
  LLNode next;
  LLNode(int data) {
    this.data = data;
  }
}
```

链表可以是双向链表，这意味着每个节点还有一个指向上一个节点的指针。示例定义如下：

```java
class DLLNode {
  int data;
  DLLNode next, prev;
  DLLNode(int data) {
    this.data = data;
  }
}
```

你可以在 `O(1)` 时间内向链表中插入新节点。要在链表中查找一个元素需要 `O(n)` 时间。

### 树

树中的每个节点都包含一个数据元素和一个指向其子节点的指针列表。最流行的树的形式是二叉树，它只有两个孩子。在后续的所有练习题中使用的示例定义如下：

```java
class TNode {
  int data;
  TNode left, right;
  TNode(int data) {
    this.data = data;
  }
}
```

在某些情况下，树节点可能有一个指向其父节点的指针。

二叉树的一种流行特殊类型是二叉搜索树（`BST`），其中每个节点的元素必须大于其左子树中的所有元素，且小于其右子树中的所有元素。

访问树中每个节点的过程被称为树遍历。按深度优先顺序探索树有三种基本方法。以下示例代码通过三种基本遍历打印树：

```java
public static void preOrder(TNode root) {
  if (root == null) { return; };
  System.out.println(root.data);
  preOrder(root.left);
  preOrder(root.right);
}

public static void inOrder(TNode root) {
  if (root == null) { return; };
  inOrder(root.left);
  System.out.println(root.data);
  inOrder(root.right);
}

public static void postOrder(TNode root) {
  if (root == null) { return; };
  postOrder(root.left);
  postOrder(root.right);
  System.out.println(root.data);
}
```

### 哈希表

哈希映射用于将键与值关联起来。这种数据结构的优势是，理论上每个操作（插入、删除、查找）平均需要 `O(1)` 时间。

要向哈希表中插入新元素，你需要计算键的哈希值。如果计算出的哈希值已存在于结构中，则使用冲突解决技术。两种最常用的解决技术是：

- **单独链法**：每个桶是独立的，对于每个哈希值索引都使用某种动态列表。
- **开放寻址**：不断检查桶直到找到未被占用的桶为止。

在 Java 中创建一个带有 `String` 键和值的新哈希映射数据结构：

```java
HashMap<String, String> hm = new HashMap<String, String>();
```

这也许是面试官中最流行的数据结构了！

### 栈

一种后进先出的数据结构。了解如何使用数组从零实现栈是很有用的，因为面试官可能会要求创建一个具有特殊功能的修改版栈。对于你可能需要栈的所有其他情况，你可以使用语言内置的实现。在 Java 中使用 `String` 类型的栈：

```java
Stack<String> stack = new Stack<String>();
```

### 队列

一种先进先出的数据结构。了解如何使用数组从零实现队列是很有用的，因为面试官可能会要求创建一个修改版队列。在 Java 中使用 `String` 类型的队列：

```java
Queue<String> queue = new LinkedList<String>();
```

### 图

一组通过链接连接的节点。可以使用邻接矩阵或邻接列表表示。面试官可能会问及图论，因为它被广泛应用于许多算法。

### 字典树（Tries）

一种通常持有字符的树数据结构，在字符串处理中有许多应用。通常，节点的所有后代都有与其关联的字符串的前缀，根节点与空字符串关联。这种数据结构的流行应用是词典查询（例如文本框中的简单自动完成功能）。

## 算法

面试官极少要求你实现特定的复杂且长的算法（如 `Dijkstra`、`A*` 等）。然而，你应该了解这些算法的工作原理、用途，并能够在涉及已知算法时进行基础对话。此外，建议了解动态规划是什么以及如何工作，并能够识别它。以下是建议学会如何实现的简单算法，以防面试官要求你实现算法的修改版：

- 广度优先搜索（`BFS`）/深度优先搜索（`DFS`）
- 合并排序（`Mergesort`）
- 快速排序（`Quicksort`）
- 二分查找（`Binary Search`）

## 其他

### 递归

一种用于解决计算机科学问题的强大技术，在面试中经常被问及。有时它会让问题的解决方案变得简单并产生紧凑的代码。记住，这种技术比迭代解决方案消耗更多内存。此外，在编写递归解决方案时不要忘记递归的终止条件。

### 面向对象设计

面试官可能会要求你描述给定系统的基本对象。因此，掌握面向对象原理的基础知识至关重要。

### 测试

面试官可能会要求你测试你自己的解决方案。你需要知道如何创建测试用例，甚至涵盖边界情况（即输入意料之外的内容）。此外，了解 `Unit Testing`（单元测试）的基本原理并提及它是非常建议的。

### 系统编程

可能会问及 `threading`（线程）、`locks`（锁）和 `mutex`（互斥锁）等概念，特别是如果面试包含理论部分的话。

### 位运算

可能会问及使用位运算符的二进制操作，特别是在专注于底层软件的公司。

### 程序内存

`stack`（栈）和 `heap`（堆）内存区域之间的区别以及各自的使用场景。

# 练习题

以下练习题由简洁的描述、（如果适用）要求的输入输出示例、用 `Java` 编写的示例代码以及（如果适用）的时间空间复杂度组成。尽可能使用了 `Java` 的内置类和实用函数，因为面试的目的不是重复轮子，而是为提出的问题提供一个高效的解决方案。

你会发现所选的问题及其答案并不很长。这是由于面试时间有限，面试官不会提问一个需要冗长解决方案的问题。如果你对一个问题想出了非常复杂且冗长的解决方案，说明你考虑得太复杂了。候选人在不到 45 分钟的时间内需要时间来澄清问题、想出解决方案、与面试官讨论解决方案的时间，以及测试解决方案的时间。

在大多数示例解决方案中，都有基础的输入数据验证，例如检查传递的对象是否为 `null` 值。这种输入验证可能并不详尽，你应该让面试官知道你跳过了输入验证，或者你没有进行详尽的检查。请记住，这可能会导致关于如何测试你的程序的后续问题。

如果问题的解决方案需要从主程序以特定方式调用，则该驱动程序的调用记录如下：

`main program calls()`

在编码面试中，你可能被问到理论问题和开放式的系统设计问题。这些不在本书的范围内，但最后两个问题包含了一些你可能会被问到的示例。

## 1. 找到多数元素

在这个问题中，多数元素定义为在数组中出现次数超过 `n/2` 次的数字。

例如：

输入：`3,2,2,1,2,2,1`

输出：`2`

### 解决方案

```java
public static int findMajCandidate(int[] arr) {
    if (arr == null || arr.length == 0) {
        return Integer.MIN_VALUE;
    }
    int count = 1, maj = arr[0];
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] == maj) {
            count++;
        } else {
            count--;
        }
        if (count == 0) {
            maj = arr[i];
            count = 1;
        }
    }
    return maj;
}

public static boolean verifyMajCandidate(int[] arr, int maj) {
    if (arr == null || arr.length == 0) {
        return false;
    }
    int n = arr.length, count = 0;
    for (int i = 0; i < n; i++) {
        if (arr[i] == maj) {
            count++;
        }
        if (count > n / 2) {
            return true;
        }
    }
    return false;
}
```

```java
int maj = findMajCandidate(arr);
if (maj == Integer.MIN_VALUE || verifyMajCandidate(arr, maj) == false) {
    System.out.println("No majority element found.");
} else {
    System.out.println("Majority element: " + maj);
}
```

**运行时间复杂度：** `O(N)`

**空间复杂度：** `O(1)`

## 2. 找到整数数组中连续子序列的最大和

例如：

输入：`1,-3,2,5,-8`

输出：`7`

### 解决方案

```java
public static int maxSubSequence(int[] arr) {
    if (arr == null || arr.length == 0) {
        return Integer.MIN_VALUE;
    }
    int maxSoFar = arr[0], curMax = arr[0];
    for (int i = 1; i < arr.length; i++) {
        curMax = Math.max(curMax + arr[i], arr[i]);
        maxSoFar = Math.max(curMax, maxSoFar);
    }
    return maxSoFar;
}
```

**运行时间复杂度：** `O(N)`

**空间复杂度：** `O(1)`

## 3. 给定两个二叉树，判断它们是否相等（具有相同的内容和结构）

### 解决方案

```java
public static boolean isTreeSame(TNode T1, TNode T2) {
    if (T1 == null && T2 == null) {
        return true;
    }
    if (T1 == null || T2 == null) {
        return false;
    }
    if (T1.data != T2.data) {
        return false;
    }
    return isTreeSame(T1.left, T2.left) && isTreeSame(T1.right, T2.right);
}
```

**运行时间复杂度：** `O(N)`

**空间复杂度：** `O(1)`

## 4. 在二叉搜索树（BST）中找到给定范围内的元素数量

例如：

输入：范围`(2,6)`

树：

```text
    5
   / \
  3   7
```

输出：`2`

### 解决方案

```java
public static int numbersInRange(TNode node, int start, int end) {
    if (node == null) {
        return 0;
    }
    if (node.data > start && node.data < end) {
        return 1 + numbersInRange(node.left, start, end) + numbersInRange(node.right, start, end);
    } else if (node.data <= start) {
        return numbersInRange(node.right, start, end);
    } else {
        return numbersInRange(node.left, start, end);
    }
}
```

**运行时间复杂度：** `O(N)`

**空间复杂度：** `O(1)`

## 5. 给定一个带有父节点指针的树，找到中序遍历的下一个节点

例如：

输入：节点`3`

树：

```text
    5
   / \
  3   7
```

输出：`5`

### 解决方案

```java
public static TNode nextInOrder(TNode n) {
    if (n == null) {
        return null;
    }
    if (n.right != null) {
        TNode curr = n.right;
        while (curr.left != null) {
            curr = curr.left;
        }
        return curr;
    }
    TNode p = n.parent;
    while (p != null && n == p.right) {
        n = p;
        p = p.parent;
    }
    return p;
}
```

**运行时间复杂度：** `O(N)`

**空间复杂度：** `O(1)`

## 6. 给定一个带有父节点指针的树，找到后序遍历的下一个节点

例如：

输入：节点`7`

树：

```text
    5
   / \
  3   7
```

输出：`5`

### 解决方案

```java
public static TNode nextPostOrder(TNode n) {
    if (n == null || n.parent == null) {
        return null;
    }
    if (n != n.parent.left) {
        return n.parent;
    }
    TNode p = n.parent.parent;
    while (p != null && n.parent == p.right) {
        n = p;
        p = p.parent;
    }
    return p;
}
```

```java
if (arr == null) {
    return Integer.MIN_VALUE;
}
int st = 0, end = arr.length - 1;
while (st <= end) {
    int mid = (st + end) / 2;
    if (arr[mid] == num) {
        return mid;
    } else if (num > arr[mid]) {
        st = mid + 1;
    } else {
        end = mid - 1;
    }
}
return Integer.MIN_VALUE;
}
```

### 运行复杂度

`O(logN)`

### 空间复杂度



# O(1)

## 10. 从数字数组中找到一个局部最小值

例如：

输入：9, 7, 2, 8, 5, 6, 3, 4

输出：2 或 5 或 3

### 解决方案

```java
public static int findLocalMin(int[] arr, int st, int end) {
    int mid = (st + end) / 2;
    if ((mid - 1 < 0) || (mid + 1 >= arr.length)) {
        return Integer.MIN_VALUE;
    }
    if ((arr[mid - 1] > arr[mid]) && (arr[mid + 1] > arr[mid])) {
        return mid;
    } else if (arr[mid - 1] < arr[mid]) {
        findLocalMin(arr, st, mid);
    } else {
        findLocalMin(arr, mid, end);
    }
    return Integer.MIN_VALUE;
}
```

### 运行复杂度

`O(logN)`

### 空间复杂度

`O(1)`

## 11. 给定一个先严格递增后严格递减的数字数组，找到最大数

例如：

输入：1, 2, 3, 4, 5, 4, 3, 2

输出：5

### 解决方案

```java
public static int findMax(int[] arr) {
    if (arr == null || arr.length <= 3) {
        return Integer.MIN_VALUE;
    }
    int st = 0, end = arr.length - 1;
    while (st <= end) {
        int mid = (st + end) / 2;
        int midVal = arr[mid];
        if (midVal > arr[mid - 1] && midVal > arr[mid + 1]) {
            return midVal;
        } else if (arr[mid - 1] < midVal) {
            st = mid + 1;
        } else {
            end = mid - 1;
        }
    }
    return Integer.MIN_VALUE;
}
```

### 运行复杂度

`O(logN)`

### 空间复杂度

`O(1)`

## 12. 仅使用整数实现平方根函数（`sqrt`）

例如：

输入：4

输出：2

输入：5

输出：2 或 3（两个值允许，因为正确结果是小数）

### 解决方案

```java
public static int sqrt(int target, int st, int end) {
    if (st >= end) {
        return Math.min(st, end);
    }
    int mid = (st + end) / 2;
    if (mid * mid == target) {
        return mid;
    }
    if (mid * mid > target) {
        return sqrt(target, st, mid - 1);
    } else {
        return sqrt(target, mid + 1, end);
    }
}
```

### 运行复杂度

`O(logN)`

### 空间复杂度

`O(1)`

## 13. 给定一个排序过但旋转了未知次数的数组，找到目标元素的位置

例如：

输入：

旋转后的数组：4, 5, 6, 7, 0, 1, 2

目标：6

输出：2

### 解决方案

```java
public static int binaryRoatedSearch(int[] arr, int target) {
    if (arr == null) {
        return Integer.MIN_VALUE;
    }
    int st = 0;
    int end = arr.length - 1;
    while (st <= end) {
        int mid = (st + end) / 2;
        if (arr[mid] == target) {
            return mid;
        }
        // 至少有一部分是有排序的
        if (arr[st] <= arr[mid]) { // 左部分是有排序的
            if (arr[st] < target && target <= arr[mid]) {
                end = mid - 1;
            } else {
                st = mid + 1;
            }
        } else { // 右部分是有排序的
            if (arr[mid] < target && target <= arr[end]) {
                st = mid + 1;
            } else {
                end = mid - 1;
            }
        }
    }
    return Integer.MIN_VALUE;
}
```

### 信息

如果输入数组包含重复项，则只能通过线性搜索在 `O(N)` 运行时间内找到目标。

### 运行复杂度

`O(logN)`

### 空间复杂度

`O(1)`

## 14. 给定一个包含多个相同整数的排序数组，找到目标整数的起始和结束位置

例如：

排序数组：1, 2, 3, 7, 7, 9, 9

目标：7

输出：

起始位置：3

结束位置：5

### 解决方案

```java
public static int modifiedSearch(int[] arr, int target) {
    int st = 0, end = arr.length - 1;
    while (st <= end) {
        int mid = (st + end) / 2;
        if (target > arr[mid]) {
            st = mid + 1;
        } else {
            end = mid - 1;
        }
    }
    return st;
}

public static int[] findRange(int[] arr, int target) {
    int[] res = { -1, -1 };
    if (arr == null) {
        return res;
    }
    int lo = modifiedSearch(arr, target - 1);
    if (lo >= arr.length || arr[lo] != target) {
        return res;
    }
    int hi = modifiedSearch(arr, target + 1);
    res[0] = lo;
    res[1] = hi;
    return res;
}
```

### 运行复杂度

`O(logN)`

### 空间复杂度

`O(1)`

## 15. 给定一个数组，每个位置表示可以向前移动的步数，找到到达数组结尾的最小步数

例如：

输入：2, 1, 1, 8, 1, 1

输出：3

### 解决方案

```java
public static int minNumOfSteps(int[] arr) {
    if (arr == null) {
        return Integer.MIN_VALUE;
    }
    int[] opt = new int[arr.length];
    opt[0] = 0;
    for (int i = 1; i < arr.length; i++) {
        int min = i;
        for (int k = 0; k < i; k++) {
            if (i - k <= arr[k]) {
                min = Math.min(min, opt[k] + 1);
            }
        }
        opt[i] = min;
    }
    return opt[arr.length - 1];
}
```

### 运行复杂度

`O(N²)`

### 空间复杂度

`O(N)`

## 16. 给定一个整数二维数组和一个起始点，找到与起始点值相同的连续区域

例如：

输入：

起始点：(0,0)

数组：

1 1 2

1 3 2

2 2 1

输出：3

### 解决方案

```java
static int mArea = 0;

public static void findAreaHelper(int[][] arr, boolean[][] visited, int x, int y) {
    if (x < 0 || x >= arr[0].length || y < 0 || y >= arr.length) {
        return;
    }
    if (visited[y][x]) {
        return;
    }
    visited[y][x] = true;
    if (arr[y][x] == value) {
        mArea++;
        findAreaHelper(arr, visited, x + 1, y);
        findAreaHelper(arr, visited, x, y + 1);
        findAreaHelper(arr, visited, x - 1, y);
        findAreaHelper(arr, visited, x, y - 1);
    }
}

public static void findArea(int[][] arr, int x, int y) {
    boolean[][] visited = new boolean[arr.length][arr[0].length];
    mArea = 0;
    findAreaHelper(arr, visited, x, y); // value 应在此处定义
}
```

（注：`value` 在原始片段中未定义，但根据上下文暗示）。

### 运行复杂度

`O(N²)`

### 空间复杂度

`O(N)`

## 17. 给定一个元组数组，代表程序所需的 RAM 数量以及开始和结束时间，找到最大 RAM 数量

例如：

输入：

开始时间 结束时间 需要 RAM

2 4 1

3 6 2

3 9 3

输出：6

### 解决方案

```java
class Triple {
    int startTime, endTime, ramNeeded;
}

public static int maxRamNeeded(List<Triple> in) {
    if (in == null) {
        return Integer.MIN_VALUE;
    }
    Map<Integer, Integer> tm = new TreeMap<Integer, Integer>();
    for (Triple t : in) {
        tm.put(t.startTime, t.ramNeeded);
        tm.put(t.endTime, -t.ramNeeded);
    }
    int curRam = 0, maxRam = 0;
    for (Map.Entry<Integer, Integer> entry : tm.entrySet()) {
        curRam += entry.getValue();
        maxRam = Math.max(curRam, maxRam);
    }
    return maxRam;
}
```

### 信息

`TreeMap` 始终根据其键排序。插入代价为 `O(logN)`。

### 运行复杂度

`O(NlogN)`

### 空间复杂度

`O(N)`

## 18. 在不使用内置函数的情况下计算数字的幂

例如：

输入：2³

输出：8

### 解决方案

```java
public static long pow(int a, int b) {
    long[] M = new long[b + 1];
    M[0] = 1;
    M[1] = a;
    return powHelper(a, b, M);
}

public static long powHelper(int a, int b, long[] M) {
    if (b > 0) {
        if (b % 2 == 0) {
            M[b] = powHelper(a, b / 2, M) * powHelper(a, b / 2, M);
        } else {
            M[b] = powHelper(a, (b - 1) / 2, M) * powHelper(a, (b - 1) / 2, M) * a;
        }
    }
    return M[b];
}
```

## 19. 给定一个整数数组，将数组重新排列为波浪数组（`a1 >= a2 <= a3 >= a4 <= a5 >= …`）

例如：

输入：1, 3, 2, 4, 5, 6, 7

输出：2, 1, 4, 3, 6, 5, 7

### 解决方案

```java
public static void waveSort(int[] arr) {
    if (arr == null) {
        return;
    }
    Arrays.sort(arr);
    for (int i = 0; i < arr.length - 1; i += 2) {
        int temp = arr[i];
        arr[i] = arr[i + 1];
        arr[i + 1] = temp;
    }
}
```

### 信息

如果列表中存在重复项，可能无效。

### 运行复杂度

`O(NlogN)`

### 空间复杂度

`O(1)`

## 20. 反转整数的位

例如：

输入：1011

输出：1101

### 解决方案

```java
public static int swapBits(int x, int i, int j) {
    int lo = ((x >> i) & 1);
    int hi = ((x >> j) & 1);
    if ((lo ^ hi) == 1) {
        x ^= ((1 << i) | (1 << j));
    }
    return x;
}
```

```java
public static int revBits(int x, int numOfBits) {
    for (int i = 0; i < numOfBits; i++) {
        x = swapBits(x, i, numOfBits - i - 1);
    }
    return x;
}
```

### 信息

- 与 `1` 进行 `XOR`（`^`）将翻转位的值。
- 与两个位进行 `XOR`（`^`），如果它们不同则返回 `1`。

### 运行复杂度

- `O(N)`

### 空间复杂度

- `O(1)`

## 21. 在无序数组中就地找到第 k 大整数

例如：

**输入：**

- `array`：`5, 8, 3, 1`
- `k`：`2`

**输出：**`3`

### 解决方案



```java
public static void swap(int[] arr, int x, int y) {
    int temp = arr[x];
    arr[x] = arr[y];
    arr[y] = temp;
}

public static int partition(int[] arr, int first, int last) {
    int pivot = first;
    swap(arr, last, pivot);
    for (int i = first; i < last; i++) {
        if (arr[i] > last) {
            swap(arr, i, first);
            first++;
        }
    }
    swap(arr, first, last);
    return first;
}

public static int quickselect(int[] arr, int first, int last, int k) {
    if (first > last)
        return Integer.MIN_VALUE;
    int pivot = partition(arr, first, last);
    if (pivot == k) {
        return arr[pivot];
    }
    if (pivot > k) {
        return quickselect(arr, first, pivot - 1, k);
    } else {
        return quickselect(arr, pivot + 1, last, k);
    }
}
```

### INFO

如果你更明智地选择`pivot`，例如选择每 5 个元素一组的中位数，你可以避免`O(N²)`的最坏时间复杂度。

### AVERAGE RUNNING TIME COMPLEXITY

- `O(N)`

### WORST RUNNING TIME COMPLEXITY

- `O(N²)`

### SPACE COMPLEXITY

- `O(1)`

---

## 22. 给定一棵树是完全二叉树（即每个叶子节点以外的节点有两个孩子）以及该树的前序和后序遍历，请重建它。

e.g:

**输入:**

- `pre-order`: `5, 3, 7`

- `post-order`: `3, 7, 5`

**输出:**

**树:**

```
5
3 7
```

### SOLUTION

```java
static int mPreIndex = 0;
public static TNode constructTree(int[] pre, int[] post, int lo, int hi) {
    if ((lo > hi) || (mPreIndex >= pre.length)) {
        return null;
    }
    TNode root = new TNode(pre[mPreIndex]);
    mPreIndex++;
    if (lo == hi) {
        return root;
    }
    int i;
    for (i = lo; i < hi; i++) {
        if (pre[mPreIndex] == post[i]) {
            break;
        }
    }
    root.left = constructTree(pre, post, lo, i);
    root.right = constructTree(pre, post, i + 1, hi - 1);
    return root;
}
```

---

## 23. 给定一棵树的中序和前序遍历，请重建它。

e.g:

**输入:**

- `in-order`: `3, 5, 7`

- `pre-order`: `3, 7, 5`

**输出:**

**树:**

```
5
3 7
```

### SOLUTION

```java
static int mPreIndex = 0;
public static TNode constructTree(int[] in, int[] pre, int lo, int hi) {
    if ((lo > hi) || (mPreIndex >= pre.length)) {
        return null;
    }
    TNode root = new TNode(pre[mPreIndex]);
    mPreIndex++;
    if (lo == hi) {
        return root;
    }
    int inIndex;
    for (inIndex = lo; inIndex <= hi; inIndex++) {
        if (in[inIndex] == root.data) {
            break;
        }
    }
    root.left = constructTree(in, pre, lo, inIndex - 1);
    root.right = constructTree(in, pre, inIndex + 1, hi);
    return root;
}
```

---

## 24. 给定一棵树是二叉搜索树 (BST)以及该树的前序遍历，请重建它。

e.g:

**输入:**

- `pre-order`: `5, 3, 7`

**输出:**

**树:**

```
5
3 7
```

### SOLUTION

```java
public static TNode constructTree(int[] pre, int lo, int hi) {
    if (lo > hi) {
        return null;
    }
    TNode root = new TNode(pre[lo]);
    if (lo == hi) {
        return root;
    }
    int i;
    for (i = lo + 1; i <= hi; i++) {
        if (pre[i] > root.data) {
            break;
        }
    }
    root.left = constructTree(pre, lo + 1, i - 1);
    root.right = constructTree(pre, i, hi);
    return root;
}
```

---

## 25. 从二叉搜索树 (BST) 中删除一个节点。

### SOLUTION

```java
public static TNode deleteNodeFromBST(TNode root, int key) {
    if (root == null) {
        return null;
    }
    if (key > root.data) {
        root.right = deleteNodeFromBST(root.right, key);
        return root;
    }
    if (key < root.data) {
        root.left = deleteNodeFromBST(root.left, key);
        return root;
    }
    // 0 或 1 个孩子
    if (root.left == null) {
        return root.right;
    } else if (root.right == null) {
        return root.left;
    }
    // 2 个孩子
    TNode n = root.right;
    while (n.left != null) {
        n = n.left;
    }
    int inOrderSuccess = n.data;
    root.data = inOrderSuccess;
    root.right = deleteNodeFromBST(root.right, inOrderSuccess);
    return root;
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(1)`

---

## 26. 检查给定字符串是否括号平衡。

e.g:

- **输入:** `(())`, **输出:** `true`

- **输入:** `()`, **输出:** `false`

### SOLUTION

```java
public static boolean isBalanced(char[] str) {
    int count = 0, i;
    for (i = 0; i < str.length; i++) {
        if (str[i] == '(') {
            count++;
        } else {
            count--;
            if (count < 0) {
                return false;
            }
        }
    }
    if (count != 0) {
        return false;
    }
    return true;
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(1)`

---

## 27. 检查给定字符串是否包含 `[]`、`()` 或 `{}`。

e.g:

- **输入:** `[{()`, **输出:** `true`

### SOLUTION

```java
public static boolean isBalanced(char[] str) {
    HashMap<Character, Character> hm;
    hm = new HashMap<Character, Character>();
    hm.put('(', ')');
    hm.put('[', ']');
    hm.put('{', '}';
    Stack<Character> s = new Stack<Character>();
    for (int i = 0; i < str.length; i++) {
        char curCh = str[i];
        if (hm.containsKey(curCh)) {
            s.add(hm.get(curCh));
        } else {
            if (s.isEmpty()) {
                return false;
            }
            if (s.pop() != curCh) {
                return false;
            }
        }
    }
    return s.isEmpty();
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(N)`

---

## 28. 在行列均排序的整数二维数组中找到一个数字的位置。

e.g:

**输入:**

- `array`:

```
1 4 7
2 5 8
3 6 9
```

- `num`: `3`

**输出:** `(2, 0)`

### SOLUTION

```java
class Point {
    int x, y;
    Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}

public static Point findNum(int[][] arr, int num) {
    if (arr == null) {
        return null;
    }
    int y = 0;
    int x = arr[0].length - 1;
    while (y < arr.length && x >= 0) {
        if (num == arr[y][x]) {
            return new Point(x, y);
        } else if (num > arr[y][x]) {
            y++;
        } else {
            x--;
        }
    }
    return new Point(-1, -1);
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(1)`

---

## 29. 在每个节点都有指向父节点指针的二叉树中找到两个节点的公共祖先。

e.g:

**输入:**

- `node1`: `1`

- `node2`: `7`

- **树:**

```
5
3 7
1
```

**输出:** `5`

### SOLUTION

```java
public static TNode findLCA(TNode n1, TNode n2, TNode root) {
    HashSet<TNode> set1 = new HashSet<TNode>();
    HashSet<TNode> set2 = new HashSet<TNode>();
    set1.add(n1);
    set2.add(n2);
    TNode cur1 = n1, cur2 = n2;
    while (true) {
        cur1 = cur1.parent;
        set1.add(cur1);
        cur2 = cur2.parent;
        if (set1.contains(cur1)) {
            return cur2;
        }
        set2.add(cur2);
    }
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(N)`

---

## 30. 在二叉树就地找到两个节点的公共祖先（不使用额外内存）。

e.g:

**输入:**

- `node1`: `1`

- `node2`: `7`

- **树:**

```
5
3 7
1
```

**输出:** `5`

### SOLUTION

```java
public static TNode findLCA(TNode n1, TNode n2, TNode root) {
    if (root == null) {
        return null;
    }
    if ((root == n1) || (root == n2)) {
        return root;
    }
    TNode l = findLCA(n1, n2, root.left);
    TNode r = findLCA(n1, n2, root.right);
    if ((l != null) && (r != null)) {
        return root;
    }
    if (l != null) {
        return l;
    } else {
        return r;
    }
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(1)`

---

## 31. 给你一个整数数组，代表某只股票每天的价格。如果你只允许在某一天买入股票并在另一天卖出，找到你能获得的最大收益。

e.g:

- **输入:** `2, 1, 6, 5, 9`

**输出:** `8`

### SOLUTION

```java
public static int maxRevenue(int[] arr) {
    if (arr == null || arr.length == 0) {
        return Integer.MIN_VALUE;
    }
    int lowest = arr[0];
    int maxRev = 0;
    for (int i = 1; i < arr.length; i++) {
        maxRev = Math.max(maxRev, arr[i] - lowest);
        lowest = Math.min(lowest, arr[i]);
    }
    return maxRev;
}
```

### RUNNING TIME COMPLEXITY

- `O(N)`

### SPACE COMPLEXITY

- `O(1)`

---

## 32. 从双向链表中删除整数的单次出现。

e.g:

**输入:**

- `list`: `2 -> 5 -> 8 -> 9`

- `val`: `5`

**输出:** `2 -> 8 -> 9`

### SOLUTION

```java
class DLLNode {
    int  data;
}
```



```java
class DLLNode {
    int data;
    DLLNode next, prev;
}

public static DLLNode removeNode(DDLNode head, int x) {
    if (head == null) {
        return null;
    }
    if (head.data == x) {
        head.next.previous = null;
        return head.next;
    }
    DDLNode runner = head;
    while (runner.next != null) {
        if (runner.next.data == x) {
            runner.next = runner.next.next;
            runner.next.previous = runner;
            break;
        }
        runner = runner.next;
    }
    return head;
}
```

运行时间复杂度：

`O(N)`

空间复杂度：

`O(1)`

---

### 33. 给定双向链表，在原地反转它

例如：

输入：`2 -> 5 -> 8 -> 9`

输出：`9 -> 8 -> 5 -> 2`

### 解决方案

```java
class DLLNode {
    int data;
    DLLNode next, prev;
}

public static DLLNode revList(DLLNode head) {
    if (head == null) {
        return null;
    }
    while (head.next != null) {
        DLLNode temp = head.next;
        head.next = head.prev;
        head.prev = temp;
        head = temp;
    }
    head.next = head.prev;
    head.prev = null;
    return head;
}
```

运行时间复杂度：

`O(N)`

空间复杂度：

`O(1)`

---

### 34. 给定一个排序后的整数数组和一个目标整数，判断是否可以通过两个整数之和生成该目标整数

例如：

输入：

数组：`1, 2, 5, 7, 8, 9`

目标：`7`

输出：`true`

### 解决方案

```java
public static boolean is2SumTarget(int[] arr, int target) {
    if (arr == null) {
        return false;
    }
    int st = 0;
    int end = arr.length - 1;
    while (st < end) {
        int sum = arr[st] + arr[end];
        if (sum == target) {
            return true;
        } else if (sum > target) {
            end--;
        } else {
            st++;
        }
    }
    return false;
}
```

运行时间复杂度：

`O(N)`

空间复杂度：

`O(1)`

---

### 35. 给定一个排序后的整数数组和一个目标整数，判断是否可以通过三个整数之和生成该目标整数

例如：

输入：

数组：`1, 2, 5, 7, 8, 9`

目标：`17`

输出：`true`

### 解决方案

```java
public static boolean is3SumTarget(int[] arr, int target) {
    if (arr == null) {
        return false;
    }
    for (int i = 0; i < arr.length - 2; i++) {
        int st = i + 1;
        int end = arr.length - 1;
        while (st < end) {
            int sum = arr[i] + arr[st] + arr[end];
            if (sum == target) {
                return true;
            } else if (sum > target) {
                end--;
            } else {
                st++;
            }
        }
    }
    return false;
}
```

运行时间复杂度：

`O(N²)`

空间复杂度：

`O(1)`

---

### 36. 给定一棵二叉树，判断它是否为二叉搜索树（BST）

例如：

输入：

树：

```text
5

9 7
```

输出：`false`

### 解决方案

```java
public static boolean isBST(TNode root, int min, int max) {
    if (root == null) {
        return true;
    }
    if (root.data > min && root.data < max) {
        return isBST(root.left, min, root.data)
        && isBST(root.right, root.data, max);
    }
    return false;
}
```

`isBST(root, Integer.MIN_VALUE, Integer.MAX_VALUE);`

运行时间复杂度：

`O(N)`

空间复杂度：

`O(1)`

---

### 37. 给定一个整数数组，其中所有整数都出现两次，只有一个出现一次，找到那个只出现一次的整数

例如：

输入：`2, 4, 2, 3, 5, 3, 4`

输出：`5`

### 解决方案

```java
public static int findSingle(int[] arr) {
    if (arr == null) {
        return Integer.MIN_VALUE;
    }
    HashSet<Integer> set = new HashSet<Integer>();
    int sum = 0;
    for (int i = 0; i < arr.length; i++) {
        int cur = arr[i];
        if (set.contains(cur)) {
            sum -= cur;
        } else {
            set.add(cur);
            sum += cur;
        }
    }
    return sum;
}
```

运行时间复杂度：

`O(N)`

空间复杂度：

`O(N)`

---

### 38. 给定一个整数数组，除一个整数外所有整数都重复多次，找到重复次数最多的整数

例如：

输入：`1, 1, 4, 4, 4, 5, 6`

输出：`4`

### 解决方案

```java
public static int findMost(int[] arr) {
    if (arr == null || arr.length == 0) {
        return Integer.MIN_VALUE;
    }
    int element = arr[0];
    int count = 1;
    int maxElement = arr[0];
    int maxCount = 1;
    for (int i = 1; i < arr.length; i++) {
        if (arr[i] == element) {
            count++;
        } else {
            count = 1;
            element = arr[i];
        }
        if (count > maxCount) {
            maxCount = count;
            maxElement = element;
        }
    }
    return maxElement;
}
```

运行时间复杂度：

`O(N)`

空间复杂度：

`O(1)`

---

### 39. 打印二叉树的垂直层序

例如：

输入：

树：

```text
5

9 7
```

输出：

`9 5 7`

### 解决方案

```java
public static void makeVerticalOrder(TNode root, int hd, HashMap<Integer, List<Integer>> hm, int[] minMax) {
    if (root == null) {
        return;
    }
    // 保存根节点的最小和最大水平距离
    if (hd < minMax[0]) minMax[0] = hd;
    if (hd > minMax[1]) minMax[1] = hd;
    if (!hm.containsKey(hd)) {
        hm.put(hd, new ArrayList<Integer>());
    }
    hm.get(hd).add(root.data);
    makeVerticalOrder(root.left, hd - 1, hm, minMax);
    makeVerticalOrder(root.right, hd + 1, hm, minMax);
}

// 生成包含垂直层的 map
for (int lvl = minMax[0]; lvl <= minMax[1]; lvl++) {
    List<Integer> curLevel = hm.get(lvl);
    for (Integer node : curLevel) {
        System.out.print(node + " ");
    }
}
System.out.println();
```

---

### 40. 打印二叉树的层序遍历

例如：

输入：

树：

```text
5

9 7
```

输出：

`5 9 7`

### 解决方案

```java
public static void printLevelOrder(TNode root) {
    if (root == null) {
        return;
    }
    Queue<TNode> curLevel = new LinkedList<>();
    Queue<TNode> nextLevel = new LinkedList<>();
    curLevel.add(root);
    while (!curLevel.isEmpty()) {
        TNode node = curLevel.poll();
        System.out.print(node.data + " ");
        if (node.left != null) {
            nextLevel.add(node.left);
        }
        if (node.right != null) {
            nextLevel.add(node.right);
        }
    }
    System.out.println();
    curLevel = nextLevel;
}
```

---

### 41. 给定双向链表，用递归和迭代的方法在原地反转它

例如：

输入：`3 -> 9 -> 6 -> 2`

输出：`2 -> 6 -> 9 -> 3`

### 递归

```java
public static DLLNode revList(DLLNode head, DLLNode prev) {
    if (head == null) {
        return prev;
    }
    DLLNode next = head.next;
    head.next = prev;
    if (next == null) {
        return head;
    } else {
        return revList(next, head);
    }
}
```

`revList(head, null);`

### 迭代

```java
public static DLLNode revList(DLLNode head) {
    if (head == null) {
        return null;
    }
    DLLNode cur = head, prev = null;
    while (cur != null) {
        DLLNode next = cur.next;
        cur.next = prev;
        prev = cur;
        cur = next;
    }
    return prev;
}
```

`revList(head);`

运行时间复杂度：

`O(N)`

空间复杂度：

`O(1)`

---

### 42. 实现一个模式匹配函数

其中：

1. `.` 匹配任意单个字符。
2. `*` 匹配所在字符的零个或多个实例。

例如：

输入：

字符串：`aabc`

模式：`a*b.`

输出：`true`

输入：

字符串：`bc`

模式：`a*b.`

输出：`true`

### 解决方案

```java
public static boolean isMatch(char[] str, char[] pat, int s, int p) {
    if (s >= str.length) {
        return (p >= pat.length);
    }
    // 当前字符是点或字母
    if (p == pat.length - 1 || pat[p + 1] != '*') {
        return (str[s] == pat[p] || pat[p] == '.')
        && isMatch(str, pat, s + 1, p + 1);
    }
    // 当前字符后面跟着星号，所以：
    // 1. 忽略星号
    // 2. 记住星号并检查相等性
    return isMatch(str, pat, s, p + 2) ||
    (isMatch(str, pat, s + 1, p) && (str[s] == pat[p]));
}
```

`boolean result = isMatch(str, pat, 0, 0);`

---

### 43. 给定一个只包含 0、1 或 2 的数组，不使用任何排序函数进行排序

例如：

输入：`0, 1, 1, 0, 2, 1`

输出：`0, 0, 1, 1, 1, 2`

### 解决方案

```java
public static void swap(int[] arr, int x, int y) {
    int temp = arr[x];
    arr[x] = arr[y];
    arr[y] = temp;
}

public static void sort012(int[] arr) {
    if (arr == null) {
        return;
    }
}
```

```java
int st = 0, mid = 0, end = arr.length - 1;

while (mid <= end) {
    switch (arr[mid]) {
        case 0:
            swap(arr, st, mid);
            st++;
            mid++;
            break;
        case 1:
            mid++;
            break;
        case 2:
            swap(arr, mid, end);
            end--;
            break;
    }
}
```

**运行时间复杂度：**

`O(N)`

**空间复杂度：**

`O(1)`

---

## 44. 计算两个字符数组形式给出的二进制数的和，以字符串形式返回

**示例：**

输入：

num 1: `001`

num2: `101`

输出：`110`

### 解决方案



```java
public static String addBinary(char[] num1, char[] num2) {
    int p1 = num1.length - 1;
    int p2 = num2.length - 1;
    int carry = 0;
    String res = "";
    while (p1 >= 0 || p2 >= 0 || carry != 0) {
        int curSum = carry;
        curSum += (p1 >= 0) ? (num1[p1] - '0') : 0;
        curSum += (p2 >= 0) ? (num2[p2] - '0') : 0;
        p1--;
        p2--;
        carry = (curSum >= 2) ? 1 : 0;
        int newDigit = curSum % 2;
        res = newDigit + res;
    }
    return res;
}
```

**运行时间复杂度：**

`O(N)`

`N`: `max(num1.length, num2.length)`

**空间复杂度：**

`O(1)`

## 45. 在不使用任何内置函数的情况下反转整数。

**示例：**

输入: `123`

输出: `321`

输入: `-123`

输出: `-321`

### 解决方案

```java
public static int revInt(int x) {
    boolean negative = false;
    if (x < 0) {
        x = x * -1;
        negative = true;
    }
    int res = 0;
    while (x > 0) {
        int LSB = x % 10;
        x = x / 10;
        res = res * 10 + LSB;
    }
    if (negative == true) {
        res = res * -1;
    }
    return res;
}
```

**运行时间复杂度：**

`O(N)`

`N`: `x` 的数字位数

**空间复杂度：**

`O(1)`

## 46. 合并两个有序的链表。

**示例：**

输入：

`list 1`: `2 -> 4 -> 5`

`list 2`: `3 -> 7`

输出: `2 -> 3 -> 4 -> 5 -> 7`

### 解决方案

```java
public static LLNode mergeLists(LLNode n1, LLNode n2) {
    if (n1 == null) {
        return n2;
    }
    if (n2 == null) {
        return n1;
    }
    LLNode res;
    if (n1.data <= n2.data) {
        res = n1;
        n1.next = mergeLists(n1.next, n2);
    } else {
        res = n2;
        n2.next = mergeLists(n1, n2.next);
    }
    return res;
}
```

**运行时间复杂度：**

`O(N)`

**空间复杂度：**

`O(1)`

## 47. 给定一个单词列表，在每行打印使用相同字母可以创建的单词。

**示例：**

输入: `abc`, `hello`, `cba`

输出：

`abc cba`

`hello`

### 解决方案

```java
public static void bucketAnagram(List<String> input) {
    HashMap<String, List<String>> hm;
    hm = new HashMap<String, List<String>>();
    for (String word : input) {
        char[] wordArr = word.toCharArray();
        Arrays.sort(wordArr);
        String key = new String(wordArr);
        List<String> list;
        if (hm.containsKey(key) == false) {
            list = new LinkedList<String>();
        } else {
            list = hm.get(key);
        }
        list.add(word);
        hm.put(key, list);
    }
    for (Map.Entry<String, List<String>> entry : hm.entrySet()) {
        for (String word : entry.getValue()) {
            System.out.print(word + " ");
        }
        System.out.println();
    }
}
```

**运行时间复杂度：**

`O(N*MlogM)`

`N`: 输入单词的个数

`M`: 最大输入单词中的字符数

**空间复杂度：**

`O(NM)`

## 48. 给出一个长度为 `K` 的整数数组，其中数组的最后一个元素为空，且其他所有值（从 `1` 到 `k`）都在数组中，找到缺失的数字。

**示例：**

输入: `4, 5, 1, 3, _`

输出: `2`

### 解决方案

```java
public static int missingNumber(int[] arr) {
    if (arr == null) {
        return Integer.MIN_VALUE;
    }
    int sumFrom1toK = arr.length;
    int sumOfArray = 0;
    for (int i = 0; i < arr.length - 1; i++) {
        sumOfArray += arr[i];
        sumFrom1toK += i + 1;
    }
    return sumFrom1toK - sumOfArray;
}
```

**说明：** 也可以使用等差数列求和公式 `sum1toK = k*(k+1))/2`。`K` 是数组的长度。

**运行时间复杂度：**

`O(N)`

**空间复杂度：**

`O(1)`

## 49. 给定一个二叉树，找到路径的最大和。路径可以从任意节点开始并到任意节点结束。

**示例：**

输入：

`tree`: `5`

`3 1`

`10`

输出: `9`

### 解决方案

```java
static int mPathSum = Integer.MIN_VALUE;
public static int maxPathIntree(Node root) {
    if (root == null) {
        return 0;
    }
    int leftSum = maxPathIntree(root.left);
    int rightSum = maxPathIntree(root.right);
    // 更新最大路径，考虑当前节点
    mPathSum = Math.max(mPathSum, leftSum + root.data + rightSum);
    // 返回当前节点下的最大路径
    return root.data + Math.max(0, Math.max(leftSum, rightSum));
}
```

**说明：** 函数使用全局变量 `mPathSum` 来返回结果。

**运行时间复杂度：**

`O(N)`

**空间复杂度：**

`O(1)`

## 50. 给无图图，每个节点包含一个标签和一个邻居列表，复制整个数据结构。

### 解决方案

```java
class Node {
    String label;
    ArrayList<Node> adjList = new ArrayList<Node>();
    Node(String label) {
        this.label = label;
    }
}
public static Node copyGraph(Node node) {
    if (node == null) {
        return null;
    }
    Queue<Node> queue = new LinkedList<Node>();
    HashMap<Node, Node> hm = new HashMap<Node, Node>();
    Node newNode = new Node(node.label);
    // 哈希表存储原始节点作为键，复制的节点作为值
    hm.put(node, newNode);
    // 队列存储尚未处理的原始节点
    queue.add(node);
    while (queue.isEmpty() == false) {
        Node curNode = queue.poll();
        for (Node adjNode : curNode.adjList) {
            if (hm.containsKey(adjNode) == false) {
                Node copyOfAdjNode = new Node(adjNode.label);
                hm.put(adjNode, copyOfAdjNode);
                curNode.adjList.add(copyOfAdjNode);
                queue.add(adjNode);
            } else {
                curNode.adjList.add(hm.get(adjNode));
            }
        }
    }
    return newNode;
}
```

**运行时间复杂度：**

`O(N)`

**空间复杂度：**

`O(N)`

## 51. 以下是面试中可能会问的一些理论问题。注意，大公司通常不问这类问题，但很多其他公司会。

- 什么是 `HashMap`？它是如何工作的？

- Java 中 `HashMap` 和 `TreeMap` 有什么区别？

- 如果我想在 Java 中使用自定义对象作为 `HashMap` 的键，需要重写哪些函数？

- 什么是虚拟内存？它是如何工作的？

- 进程和线程之间有什么区别？

- C/C++ 中的虚构造函数和析构函数是什么？

- 值传递和引用传递是什么？

- 什么是 `AVL` 树和红树（`RBTree`）？自平衡树和普通树的插入/删除/查找时间是多少？

- 定义资源管理中的死锁和饥饿。

- 非阻塞线程安全意味着什么？

- 如何防止死锁？

- 如何实现 `mutex`锁？

- 互斥锁（`Mutex`）和信号量（`Semaphore`）有什么区别？

- 垃圾回收器如何检测哪些对象不再被使用？

- 抢占式和协作式多任务有什么区别？

- 进程间通信（`IPC`）的哪些形式？

- `IPC` 中的管道（`Pipes`）、消息队列（`Message Queues`）、共享内存（`Shared Memory`）、映射文件（`Mapped Files`）有什么区别？

- C++ 中 `struct` 和 `class` 有什么区别？

- Java 中抽象类（`Abstract class`）和接口（`Interface`）有什么区别？

- 在什么情况下使用抽象类，什么情况下使用接口？

- C++ 和 Java 的主要区别是什么？

- 什么是小端序（`Little Endian`）和大端序（`Big Endian`）？

- 逻辑移位和算术移位有什么区别？

- 什么是栈溢出（`stack overflow`）？

- 什么是多态？

- Java 中的泛型（`Generics`）是什么？

- 什么是内存碎片？

- 如果 `int` 值在 C++ 中溢出会发生什么？在 Java 中会发生什么？

- 什么是单元测试（`Unit Testing`）？

- 你如何让你的解决方案并行运行？

- 你知道哪些软件设计模式？

- 系统开发生命周期（`SDLC`）是什么？

- 什么是软件原型（`prototyping`）？

- 缓存的某些淘汰策略（`eviction policies`）有哪些？

- 什么是分布式文件系统？

# 52. 以下是在编程面试中可能被到的开放式问题。这些问题可能是系统设计题，也可能是面向对象的设计题。这些问题没有标准答案，面试官只是想看到你对大规模问题的解决方案进行高层设计的方法。

- 设计并解释停车场管理软件所需的必要类和架构。

- 设计并解释一个可以绘制不同形状的软件所需的必要类和架构。

- 设计并解释扑牌游戏所需的必要类和架构。

- 设计并解释即时通讯应用所需的必要类和架构。

- 设计并解释蛇吃大游戏所需的必要类和架构。

- 设计一个提供校园内导航路线的应用程序。

- 设计一个具有 `LRU` 淘汰策略和 `O(1)` 访问时间的缓存。

- 设计一个可以缓存结果的 `HTTP` 下载器。

- 设计一个类似 `PasteBin` 的服务。

- 设计一个 `URL` 缩短器服务。

- 设计一个用于动态提供地图图像的服务器架构。

- 设计一个为每个请求返回唯一 ID 的系统。该 ID 应随着时间的推移而增加。

- 如何确保程序没有内存泄漏？

- 设计一个存储键值对的分布式系统。

- 设计一个公司员工使用访问卡来记录工作时间的系统。

- 在数百万用户同时发送请求的系统（例如搜索引擎）中，设计一种方法给第十亿个请求请求者发放奖励。

- 你如何为应用程序设计一个全自动的构建/测试/部署系统？

- 如何设计一个文本编辑器？

- 你如何在存储介质中表示 `URL` 以避免重复？
