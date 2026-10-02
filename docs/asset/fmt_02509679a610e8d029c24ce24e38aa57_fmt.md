
## 第 7 章 数组和 ArrayList

### 7.4.7 使用数组分析调查结果

我们的下一个示例使用数组来汇总调查中收集的数据。考虑以下问题描述：

- 要求 20 名学生根据 1 到 5 分的分对食堂的食物质量进行评分，1 分代表“糟糕”，5 分代表“优秀”。将这 20 个响应放在一个整数数组中，并确定每个评分的频率。

这是一个典型的数组处理应用（图 7.8）。我们希望汇总每种类型（即 1–5）响应的数量。数组 `responses`（第 9–10 行）是一个包含 20 个元素的整数数组，包含了学生的调查响应。数组中的最后一个值是故意设置错误的。当程序执行时，会检查数组索引的有效性——所有索引必须大于 0 或小于数组的长度。任何尝试访问该索引范围之外元素的尝试都会导致名为 `ArrayIndexOutOfBoundsException` 的运行时错误。在本节结束时，我们将讨论无效的响应值，演示数组边界检查，并介绍 Java 的异常处理机制，该机制可用于检测到和处理 `ArrayIndexOutOfBoundsException`。

```java
// Fig.7.8: StudentPoll.java
// 调查分析程序。
public class StudentPoll
{
    public static void main(String[] args)
    {
        // 学生响应数组（通常在运行时输入）
        int[] responses = {1, 2, 5, 4, 3, 5, 2, 1, 3, 3, 1, 4, 3, 3, 2, 3};
        int[] frequency = new int[6]; // 频率计数器数组

        // 对于每个答案，选择响应并用于设置值
        // 作为频率索引以确定要递增的元素
        for (int answer = 0; answer < responses.length; answer++) {
            try
            {
                ++frequency[responses[answer]];
            }
            catch (ArrayIndexOutOfBoundsException e)
            {
                System.out.println(e); // 调用 toString 方法
                System.out.printf("responses[%d] = %d%n", answer, responses[answer]);
            }
        }

        System.out.printf("%s%10s%n", "Rating", "Frequency");

        // 输出数组每个元素的值
        for (int rating = 1; rating < frequency.length; rating++)
            System.out.printf("%6d%10d%n", rating, frequency[rating]);
    }
} // StudentPoll 结束
```

```
java.lang.ArrayIndexOutOfBoundsException: 14
responses[19] = 14
```

| Rating | 频率 |
|---|---|
| 1 | 3 |
| 2 | 4 |
| 3 | 8 |
| 4 | 2 |
| 5 | 2 |

图 7.8 调查分析程序。

#### 频率数组

使用六元素数组 `frequency`（第 11 行）来统计每个响应可能的出现类型数量。每个元素都用作可能的调查响应类型的计数器——`frequency[1]` 统计将食物评为 1 分的学生人数，`frequency[2]` 统计将食物评为 2 分的学生人数，以此类推。

#### 汇总结果

语句（第 15–27 行）逐个从 `responses` 数组读取响应，并递增计数器 `frequency[1]` 到 `frequency[5]` 之一；我们忽略了 `frequency[0]`，因为调查响应仅限于 1–5 范围。循环中的关键语句根据 `responses[answer]` 的值来执行。

让我们逐步执行该语句的前几次迭代：

- 当计数器 `answer` 为 0 时，`responses[answer]` 是 `responses[0]` 的值（即 1——参见第 9 行）。在这种情况下，`frequency[responses[answer]]` 被解释为 `frequency[1]`，计数器 `frequency[1]` 增加 1。为了评估该表达式，我们从最内层括 `(answer, 0)` 中的值开始。将 `answer` 的值代入表达式，然后评估下一组括 `(responses[answer])`。该值被用作 `frequency` 数组的索引，以确定递增哪个计数器。

- 当 `answer` 为 1 时，`responses[answer]` 是 `responses[1]` 的值。在这种情况下，`frequency[responses[answer]]` 被解释为 `frequency[2]`，计数器 `frequency[2]` 增加 1。评估该表达式，我们从最内层括 `(answer, 0)` 中的值开始。将 `answer` 的值代入表达式，然后评估下一组括 `(responses[answer])`。该值被用作 `frequency` 数组的索引，以确定递增哪个计数器。

- 当 `answer` 为 2 时，`responses[answer]` 是 `responses[2]` 的值（即 5——参见第 9 行）。在这种情况下，`frequency[responses[answer]]` 被解释为 `frequency[5]`，计数器 `frequency[5]` 增加 1。评估该表达式，我们从最内层括 `(answer, 0)` 中的值开始。将 `answer` 的值代入表达式，然后评估下一组括 `(responses[answer])`。该值被用作 `frequency` 数组的索引，以确定递增哪个计数器。

无论如何，`responses` 数组的第 19 个元素是 14。`responses[19] = 14`。任何尝试访问该索引范围之外元素的尝试都会导致名为 `ArrayIndexOutOfBoundsException` 的运行时错误。在本节结束时，我们将讨论无效的响应值，演示数组边界检查，并介绍 Java 的异常处理机制，该机制可用于检测和处理 `ArrayIndexOutOfBoundsException`。

### 7.6 案例研究：卡牌洗牌与发牌模拟

#### Card 类

`Card` 类（图 7.9）包含两个 `String` 实例变量——`face`（花值）和 `suit`（花色），用于存储特定卡牌的名称和花色名称的引用。该类的构造函数（第 10–14 行）接收两个 `String` 来初始化 `face` 和 `suit`。`toString` 方法（第 17–20 行）创建一个由卡牌花值、字符串 " of " 以及花色组成的字符串。`Card` 类的 `toString` 方法可以显式调用，以获取 `Card` 对象的字符串表示（例如，“Ace of Spades”）。当对象在需要 `String` 的地方被使用时，对象的 `toString` 方法会被隐式调用（例如当 `printf` 使用 `%s` 格式说明符输出对象时，或使用 `+` 运算符将对象与字符串拼接时）。为了产生这种行为，必须按照图 7.9 所示的头文件来声明 `toString`。

```java
// 图 7.9: Card.java
// Card 代表一张扑牌。
public class Card {
    private final String face; // 卡牌的花值 ("Ace", "Deuce", ...)
    private final String suit; // 卡牌的花色 ("Hearts", "Diamonds", ...)
    // 双参数构造函数用于初始化卡牌的 face 和 suit
    public Card(String cardFace, String cardSuit) {
        this.face = cardFace; // 初始化卡牌的花值
        this.suit = cardSuit; // 初始化卡牌的花色
    }
    // 返回 Card 的字符串表示
    public String toString() {
        return face + " " + suit;
    }
} // 类结束
```

**图 7.9** | Card 代表一张扑牌。

#### DeckOfCards 类

`DeckOfCards` 类（图 7.10）声明了一个名为 `deck` 的 `Card` 数组实例变量（第 7 行）。引用类型数组的声明方式与其他任何数组相同。`DeckOfCards` 类声明了一个整数实例变量 `currentCard`（第 8 行），代表将从 `deck` 数组中发出的下一张 `Card` 的序列号（0–51），以及一个命名常量 `NUMBER_OF_CARDS`（第 9 行），表示牌组中的卡牌数量（52）。

```java
// 图 7.10: DeckOfCards.java
// DeckOfCards 类代表一组扑牌。
import java.security.SecureRandom;

public class DeckOfCards
{
    private Card[] deck; // 对象数组
    private int currentCard; // 下一个要发出的 Card 的索引 (0-51)
    private static final int NUMBER_OF_CARDS = 52; // 卡牌常量数量
    // 随机生成器
    private static final SecureRandom randomNumbers = new SecureRandom();

    // 构造函数填充牌组
    public DeckOfCards() {
        String[] faces = {"Ace", "Deuce", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Ten", "Jack", "Queen", "King"};
        String[] suits = {"Hearts", "Diamonds", "Clubs", "Spades"};

        deck = new Card[NUMBER_OF_CARDS]; // 创建 Card 对象数组
        currentCard = 0; // 第一张 Card 将是 deck[0]

        // 用 Card 对象填充牌组
        for (int count = 0; count < deck.length; count++) {
            deck[count] = new Card(faces[count % 13], suits[count / 13]);
        }
    }

    // 使用单次算法洗牌
    public void shuffle() {
        // 下一次调用 dealCard 方法应该再次从 deck[0] 开始
        currentCard = 0;
        // 对于每张卡牌，随机选择另一个 Card (0-51) 并交换它们
        for (int first = 0; first < deck.length; first++) {
            // 在 0 到 51 之间选择一个随机数
            int second = randomNumbers.nextInt(NUMBER_OF_CARDS);
            // 将 Card 与随机的 Card 交换
            Card temp = deck[first];
            deck[first] = deck[second];
            deck[second] = temp;
        }
    }

    // 发出一张卡牌
    public Card dealCard() {
        // 判断是否还有剩余卡牌待发
        if (currentCard < deck.length) {
            return deck[currentCard++]; // 返回数组中的当前 Card
        } else {
            return null; // 返回 null 表示所有卡牌已发完
        }
    }
}
```

**图 7.10** | DeckOfCards 类代表一组扑牌。

##### DeckOfCards 构造函数

该类的构造函数实例化 `deck` 数组（第 20 行），包含 `NUMBER_OF_CARDS` (52) 个元素。`deck` 的元素默认为 `null`，构造函数使用第 24–26 行的 `for` 循环来填充牌组。循环将控制变量 `count` 初始化为 0，只要 `count` 小于 `deck.length`，导致 `count` 取从 0 到 51 的每个整数值（`deck` 数组的索引）。每张 `Card` 都被实例化并用两个 `String` 初始化——一个来自 `faces` 数组（包含从 "Ace" 到 "King"），另一个来自 `suits` 数组（包含 "Hearts," "Diamonds," "Clubs" 和 "Spades"）。计算 `count % 13` 始终产生 0 到 12 之间的值（第 16–17 行 `faces` 数组的索引），计算 `count / 13` 始终产生 0 到 3 之间的值（第 18 行 `suits` 数组的索引）。当牌组初始化时，它会按每个花色的顺序创建花值为 "Ace" 到 "King" 的 `Card`（所有的 13 张 "Hearts"，然后是 "Diamonds"，再是 "Clubs"，最后是 "Spades"）。我们在此示例中使用 `String` 来表示花值和花色。在练习 7.3 中，我们要求你修改此示例，使用常量数组来表示花值和花色。

##### DeckOfCards 方法 shuffle

`shuffle()` 方法洗牌牌组中的卡牌。该方法遍历所有 52 张卡牌（索引 0 到 51）。对于每张卡牌，随机选取一个 0 到 51 之间的数字来选择另一张卡牌。接下来，在数组中交换当前 `Card` 和随机选取的对象。这种交换通过第 42–44 行的赋值完成。额外变量临时存储了正在交换的 `Card` 对象之一。

##### DeckOfCards 方法 dealCard
