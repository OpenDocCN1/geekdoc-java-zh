
# 用 Java 实现 2048 求解器

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/2048-java-solver>

## 1. 简介

**最近，我们看了一个解决游戏 2048 的[算法](/web/20220630011049/https://www.baeldung.com/cs/2048-algorithm)。**我们从理论的角度讨论了这一点，并没有任何实际的代码。

在这里，我们要用 Java 写一个实现。这将作为人类和电脑玩家一起玩，展示一个更好的游戏可以玩得多好。

## 2. 初始设置

我们首先需要的是一个可以玩游戏的设置，看看进展如何。

这将为我们提供玩游戏所需的所有构造，并完全实现计算机播放器——反正它只放置随机的瓷砖。这给了我们实现一个“人类”玩家来玩游戏的机会。

### 2.1. 游戏板

首先，我们需要一个游戏板。这是一个可以放置数字的单元格网格。

为了使一些事情更容易处理，**让我们从一个简单的单元格位置表示开始**。这实际上只是一对坐标的包装：

```java
public class Cell {
    private final int x;
    private final int y;

    // constructor, getters, and toString
}
```

**我们现在可以写一个类来代表董事会本身**。这将把值存储在一个简单的二维数组中，但是允许我们通过上面的`Cell`类来访问它们：

```java
public class Board {
    private final int[][] board;
    private final int score;

    public Board(int size) {
        this.board = new int[size][];
        this.score = 0;

        for (int x = 0; x < size; ++x) {
            this.board[x] = new int[size];
            for (int y = 0; y < size; ++y) {
                board[x][y] = 0;
            }
        }
    }

    public int getSize() {
        return board.length;
    }

    public int getScore() {
        return score;
    }

    public int getCell(Cell cell) {
        return board[cell.getX()][cell.getY()];
    }

    public boolean isEmpty(Cell cell) {
        return getCell(cell) == 0;
    }

    public List<Cell> emptyCells() {
        List<Cell> result = new ArrayList<>();
        for (int x = 0; x < board.length; ++x) {
            for (int y = 0; y < board[x].length; ++y) {
                Cell cell = new Cell(x, y);
                if (isEmpty(cell)) {
                    result.add(cell);
                }
            }
        }
        return result;
    }
}
```

这是一个不可变的类，它代表了一个棋盘，并让我们询问它来找出当前的状态。它还记录当前的分数，我们稍后会讲到。

### 2.2. 电脑播放器和放置瓷砖

现在我们有了一个游戏板，我们希望能够玩它。我们首先想要的是电脑播放器，因为这是一个纯粹的随机播放器，而且以后会完全按照需要使用。

电脑玩家所做的不过是在一个格子里放一块瓷砖，所以我们需要一些方法在我们的棋盘上实现它。我们希望保持这一点不变，因此放置一个图块将在新状态下生成一个全新的棋盘。

首先，**我们想要一个构造函数来获取实际的棋盘状态**，而不是我们之前的那个构造一个空白的棋盘：

```java
private Board(int[][] board, int score) {
    this.score = score;
    this.board = new int[board.length][];

    for (int x = 0; x < board.length; ++x) {
        this.board[x] = Arrays.copyOf(board[x], board[x].length);
    }
}
```

这是`private`，因此它只能被同一个类中的其他方法使用。这有助于我们封装电路板。

接下来，我们将添加一个方法来放置瓷砖。这将返回一个全新的板，除了在给定的单元格中有给定的数字之外，它与当前的板完全相同：

```java
public Board placeTile(Cell cell, int number) {
    if (!isEmpty(cell)) {
        throw new IllegalArgumentException("That cell is not empty");
    }

    Board result = new Board(this.board, this.score);
    result.board[cell.getX()][cell.getY()] = number;
    return result;
}
```

最后，我们将编写一个新的类来代表一个计算机玩家。这将有一个单一的方法，该方法将获取当前的板并返回新的板：

```java
public class Computer {
    private final SecureRandom rng = new SecureRandom();

    public Board makeMove(Board input) {
        List<Cell> emptyCells = input.emptyCells();

        double numberToPlace = rng.nextDouble();
        int indexToPlace = rng.nextInt(emptyCells.size());
        Cell cellToPlace = emptyCells.get(indexToPlace);

        return input.placeTile(cellToPlace, numberToPlace >= 0.9 ? 4 : 2);
    }
}
```

这个函数从棋盘上获取每个空白单元格的列表，随机选择一个，然后在里面放一个数字。我们将随机决定在 10%的时间里将“4”放入单元格，而在其他 90%的时间里将“2”放入单元格。

### 2.3. 一个“人类”玩家和移动瓷砖

接下来我们需要的是一个“人类”玩家。这不是最终目标，而是一个纯粹随机的玩家，每次移动时都会选择一个随机的方向来移动牌。这将成为我们打造最佳球员的基础。

首先，我们需要定义一系列可能的移动：

```java
public enum Move {
    UP,
    DOWN,
    LEFT,
    RIGHT
}
```

**接下来，我们需要扩充`Board`类，以支持通过在这些方向之一移动瓷砖来移动。**为了降低这里的复杂性，我们想旋转棋盘，这样我们就可以一直向同一个方向移动方块。

这意味着我们需要一种方法来调换和颠倒棋盘：

```java
private static int[][] transpose(int[][] input) {
    int[][] result = new int[input.length][];

    for (int x = 0; x < input.length; ++x) {
        result[x] = new int[input[0].length];
        for (int y = 0; y < input[0].length; ++y) {
            result[x][y] = input[y][x];
        }
    }

    return result;
}

private static int[][] reverse(int[][] input) {
    int[][] result = new int[input.length][];

    for (int x = 0; x < input.length; ++x) {
        result[x] = new int[input[0].length];
        for (int y = 0; y < input[0].length; ++y) {
            result[x][y] = input[x][input.length - y - 1];
        }
    }

    return result;
}
```

调换棋盘会交换所有的行和列，这样上边就变成了左边。反转棋盘只是简单地镜像它，使左边变成右边。

**接下来，我们向`Board`添加一个方法，在给定的方向上移动，并在新的状态下返回一个新的`Board`。**

我们首先制作一份董事会状态的副本，然后我们可以使用它：

```java
public Board move(Move move) {
    int newScore = 0;

    // Clone the board
    int[][] tiles = new int[this.board.length][];
    for (int x = 0; x < this.board.length; ++x) {
        tiles[x] = Arrays.copyOf(this.board[x], this.board[x].length);
    }
```

接下来，我们操纵我们的副本，以便我们总是将瓷砖向上移动：

```java
if (move == Move.LEFT || move == Move.RIGHT) {
    tiles = transpose(tiles);
}
if (move == Move.DOWN || move == Move.RIGHT) {
    tiles = reverse(tiles);
}
```

我们还需要另一个方块数组——这一次我们将把最终结果构建到其中——以及一个跟踪这次移动获得的新分数的跟踪器：

```java
int[][] result = new int[tiles.length][];
int newScore = 0;
```

现在我们已经准备好开始移动瓷砖，并且我们已经操纵了事物，所以我们总是在同一个方向上工作，我们可以开始了。

我们可以独立于其他列移动每一列。我们只需要迭代列并重复，从构建我们正在移动的瓦片的另一个副本开始。

这次我们将它们构建到一个`LinkedList`中，因为我们希望能够轻松地从中取出值。我们也只添加有数字的实际瓷砖，跳过空瓷砖。

这实现了我们的移动，但还没有合并瓷砖：

```java
for (int x = 0; x < tiles.length; ++x) {
    LinkedList<Integer> thisRow = new LinkedList<>();
    for (int y = 0; y < tiles[0].length; ++y) {
        if (tiles[x][y] > 0) {
            thisRow.add(tiles[x][y]);
        }
    }
```

接下来，我们需要合并瓷砖。**我们需要与上面的分开做；否则，我们会冒多次合并同一个图块的风险。**

这是通过从上面构建另一个`LinkedList`瓷砖来实现的，但这一次我们进行合并：

```java
LinkedList<Integer> newRow = new LinkedList<>();
while (thisRow.size() >= 2) {
    int first = thisRow.pop();
    int second = thisRow.peek();
    if (second == first) {
        int newNumber = first * 2;
        newRow.add(newNumber);
        newScore += newNumber;
        thisRow.pop();
    } else {
        newRow.add(first);
    }
}
newRow.addAll(thisRow);
```

在这里，我们也在计算这一步的新分数。这是合并后创建的图块的总和。

我们现在可以将它构建到结果数组中。一旦我们用完了列表中的图块，剩余的图块将被填充值“0”以表示它们是空白的：

```java
result[x] = new int[tiles[0].length];
for (int y = 0; y < tiles[0].length; ++y) {
    if (newRow.isEmpty()) {
        result[x][y] = 0;
    } else {
        result[x][y] = newRow.pop();
    }
}
```

一旦我们完成移动瓷砖，我们需要操纵他们再次回到正确的旋转。这与我们之前做的完全相反：

```java
if (move == Move.DOWN || move == Move.RIGHT) {
    result = reverse(result);
}
if (move == Move.LEFT || move == Move.RIGHT) {
    result = transpose(result);
}
```

最后，我们可以用这组新的牌和新计算的分数构建并返回一个新的板：

```java
return new Board(result, this.score + newScore);
}
```

我们现在可以写我们随机的“人类”玩家了。这无非是生成一个随机移动并调用上面的方法来进行移动：

```java
public class Human {
    private SecureRandom rng = new SecureRandom();

    public Board makeMove(Board input) {
        Move move = Move.values()[rng.nextInt(4)];
        return input.move(move);
    }
}
```

### 2.4. 玩游戏

**我们有足够的组件来玩这个游戏，尽管不是很成功。**然而，很快我们将会改进`Human`职业的游戏方式，这将会让我们很容易地看到不同之处。

首先，我们需要一种打印游戏板的方法。

对于这个例子，我们只是要打印到控制台，所以`System.out.print`就足够了。对于一个真实的游戏，我们想要做更好的图形：



## 1. 打印棋盘

定义一个`printBoard()`方法来展示当前棋盘状态：

```java
private static void printBoard(Board board) {
    StringBuilder topLines = new StringBuilder();
    StringBuilder midLines = new StringBuilder();
    for (int x = 0; x < board.getSize(); ++x) {
        topLines.append("+--------");
        midLines.append("|        ");
    }
    topLines.append("+");
    midLines.append("|");

    for (int y = 0; y < board.getSize(); ++y) {
        System.out.println(topLines);
        System.out.println(midLines);
        for (int x = 0; x < board.getSize(); ++x) {
            Cell cell = new Cell(x, y);
            System.out.print("|");
            if (board.isEmpty(cell)) {
                System.out.print("        ");
            } else {
                StringBuilder output = new StringBuilder(Integer.toString(board.getCell(cell)));
                while (output.length() < 8) {
                    output.append(" ");
                    if (output.length() < 8) {
                        output.insert(0, " ");
                    }
                }
                System.out.print(output);
            }
        }
        System.out.println("|");
        System.out.println(midLines);
    }
    System.out.println(topLines);
    System.out.println("Score: " + board.getScore());
}
```

## 2. 设置游戏

在打印棋盘的方法之后，我们需要初始化游戏组件。创建棋盘、两个玩家，并让计算机进行两次初始移动（即在棋盘上放置两个随机数）：

```java
Board board = new Board(4);
Computer computer = new Computer();
Human human = new Human();
for (int i = 0; i < 2; ++i) {
    board = computer.makeMove(board);
}
```

## 3. 游戏循环

现在进入真正的游戏循环。**这将是人类和电脑玩家轮流的重复，只有当没有空单元格时才停止**：

```java
printBoard(board);
do {
    System.out.println("Human move");
    System.out.println("==========");
    board = human.makeMove(board);
    printBoard(board);

    System.out.println("Computer move");
    System.out.println("=============");
    board = computer.makeMove(board);
    printBoard(board);
} while (!board.emptyCells().isEmpty());

System.out.println("Final Score: " + board.getScore());
```

运行此程序将展示一个随机进行的 2048 游戏。

## 3. 实现 2048 播放器

有了游戏基础后，我们可以实现一个比随机选择方向更优的“人类”玩家。

### 3.1 模拟移动

我们实现的算法基于 [Expectimax](https://web.archive.org/web/20220630011049/https://en.wikipedia.org/wiki/Expectiminimax) 算法。因此，**算法的核心是模拟每一个可能的移动，给每一个分配一个分数，并选择做得最好的那个**。

我们将大量使用 [Java 8 Streams](https://web.archive.org/web/20220630011049/https://www.baeldung.com/java-streams) 来帮助构建代码。

首先重写`Human`类中的`makeMove()`方法：

```java
public Board makeMove(Board input) {
    return Arrays.stream(Move.values())
      .map(input::move)
      .max(Comparator.comparingInt(board -> generateScore(board, 0)))
      .orElse(input);
}
```

**对于每一个可能的方向，我们生成新棋盘，并开始计分算法**，传入该棋盘和深度`0`，然后选择得分最高的棋步。

`generateScore()`方法模拟每一个可能的计算机移动（将“2”或“4”放入每个空单元格），并评估后续发展：

```java
private int generateScore(Board board, int depth) {
    if (depth >= 3) {
        return calculateFinalScore(board);
    }
    return board.emptyCells().stream()
      .flatMap(cell -> Stream.of(new Pair<>(cell, 2), new Pair<>(cell, 4)))
      .mapToInt(move -> {
          Board newBoard = board.placeTile(move.getFirst(), move.getSecond());
          int boardScore = calculateScore(newBoard, depth + 1);
          return (int) (boardScore * (move.getSecond() == 2 ? 0.9 : 0.1));
      })
      .sum();
}
```

若达到深度限制，则立即返回最终分数；否则继续模拟。

`calculateScore()`方法继续模拟人类移动的等式侧，与`makeMove()`类似，但返回分数而非棋盘：

```java
private int calculateScore(Board board, int depth) {
    return Arrays.stream(Move.values())
      .map(board::move)
      .mapToInt(newBoard -> generateScore(newBoard, depth))
      .max()
      .orElse(0);
}
```

### 3.2 给最终棋盘打分

我们需要为每个模拟分支的最终棋盘生成分数，以确定最佳分支。评分由多种因素组合而成，应用于棋盘的每一行和每一列，最后汇总总分。

先生成需要评分的行列列表：

```java
List<List<Integer>> rowsToScore = new ArrayList<>();
for (int i = 0; i < board.getSize(); ++i) {
    List<Integer> row = new ArrayList<>();
    List<Integer> col = new ArrayList<>();

    for (int j = 0; j < board.getSize(); ++j) {
        row.add(board.getCell(new Cell(i, j)));
        col.add(board.getCell(new Cell(j, i)));
    }

    rowsToScore.add(row);
    rowsToScore.add(col);
}
```

对每个列表评分并求和（此处为占位符）：

```java
return rowsToScore.stream()
    .mapToInt(row -> {
        int score = 0;
        return score;
    })
    .sum();
```

最终评分逻辑基于多个因素：**每行的固定分数、行中数字总和、所有可能的合并、空单元格数，以及行的单调性（数字按升序排列的程度）**。

计算前需建立一些数据。首先，移除空白单元格：

```java
List<Integer> preMerged = row.stream()
  .filter(value -> value != 0)
  .collect(Collectors.toList());
```

统计相邻相同数字的合并次数及严格升序/降序的差异：

```java
int numMerges = 0;
int monotonicityLeft = 0;
int monotonicityRight = 0;
for (int i = 0; i < preMerged.size() - 1; ++i) {
    Integer first = preMerged.get(i);
    Integer second = preMerged.get(i + 1);
    if (first.equals(second)) {
        ++numMerges;
    } else if (first > second) {
        monotonicityLeft += first - second;
    } else {
        monotonicityRight += second - first;
    }
}
```

**计算该行最终分数**：

```java
int score = 1000;
score += 250 * row.stream().filter(value -> value == 0).count();
score += 750 * numMerges;
score -= 10 * row.stream().mapToInt(value -> value).sum();
score -= 50 * Math.min(monotonicityLeft, monotonicityRight);
return score;
```

上述权重为相对任意值，调整它们会影响游戏表现及策略优先级。

## 4. 对算法的改进

当前实现有效，但速度较慢（每次移动约 1 分钟）。可优化如下：

### 4.1 并行处理

使用 Java 流可轻松并行化。只需在流中添加`parallel()`即可，这一改动可将移动时间缩短至约 20 秒。

### 4.2 修剪不可打的树枝

修剪任何不会改变棋盘状态的移动分支，避免浪费计算资源。需在`Board`上实现`equals()`方法：

```java
@Override
public boolean equals(Object o) {
    if (this == o) {
        return true;
    }
    if (o == null || getClass() != o.getClass()) {
        return false;
    }
    Board board1 = (Board) o;
    return Arrays.deepEquals(board, board1.board);
}
```

然后，在流管道中添加过滤器以忽略未改变的棋盘：

```java
return Arrays.stream(Move.values())
    .parallel()
    .map(board::move)
    .filter(moved -> !moved.equals(board))
    ........
```

此优化在游戏早期影响较小（空单元格多时可修剪的少），后期则显著提高效率，将移动时间降至几秒。

## 5. 总结

我们构建了玩 2048 的基础框架，并实现了求解器以提升游戏水平。所有示例代码可在 [GitHub](https://web.archive.org/web/20220630011049/https://github.com/eugenp/tutorials/tree/master/algorithms-modules/algorithms-miscellaneous-6) 上获取。不妨尝试调整规则，观察它们对游戏策略的影响。
