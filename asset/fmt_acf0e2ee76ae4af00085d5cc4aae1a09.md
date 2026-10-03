
**图 11.3** 处理 `ArithmeticExceptions` 和 `InputMismatchExceptions`。（2 部分中的第 1 部分）

### 11.3 ArithmeticExceptions 和 InputMismatchExceptions

| 输入 | 输出 |
| :--- | :--- |
| Please enter an integer numerator: 100<br>Please enter an integer denominator: 7 | Result: 100 / 7 = 14 |
| Please enter an integer numerator: 100<br>Please enter an integer denominator: 0 | Exception: java.lang.ArithmeticException: / by zero<br>Zero is an invalid denominator. Please try again.<br><br>Please enter an integer numerator: 100<br>Please enter an integer denominator: 7 | Result: 100 / 7 = 14 |
| Please enter an integer numerator: 100<br>Please enter an integer denominator: hello | Exception: java.util.InputMismatchException<br>You must enter integers. Please try again.<br><br>Please enter an integer numerator: 100<br>Please enter an integer denominator: 7 | Result: 100 / 7 = 14 |

**图 11.3** 处理 `ArithmeticExceptions` 和 `InputMismatchExceptions`。（2 部分中的第 2 部分。）

图 11.3 中的第一次执行没有遇到任何问题。在第二次执行中，用户输入了零分母，发生了 `ArithmeticException`。在第三次执行中，用户将字符串 "hello" 作为分母，发生了 `InputMismatchException`。对于每个异常，用户都会被告知错误并要求重试，系统会提示输入两个新整数。在每个示例执行中，程序都成功运行完成。

`InputMismatchException` 在第 3 行导入。`Arithmetic` 类不需要导入，因为它在 `java.lang` 包中。第 18 行创建了布尔变量 `continueLoop`，如果用户没有输入有效输入，则为 `true`。第 20–48 行向用户请求输入，直到接收到有效输入。

#### 将代码封装在 try 块中
第 22–33 行包含一个 try 块，它封装了可能抛出异常的代码以及在发生异常时不应执行的代码（即：如果发生异常，try 块中剩余代码将被跳过）。try 块由关键字以及紧随其后的、用大括号括围的代码块组成。[注：“try 块”一术语有时指的是关键字后面的代码块（不包括关键字本身）。为了简单起见，我们使用“try 块”来指代 try 关键字后面的代码块以及 try 关键字本身。] 从键盘读取整数的语句（第 25 行和第 27 行）使用每个 `nextInt` 方法来读取 int 值。如果读取的值不是整数，`nextInt` 方法将抛出 `InputMismatchException`。

导致 `ArithmeticException` 的除法运算不在 try 块中执行。相反，对 `quotient` 方法的调用（第 29 行）触发了尝试除法的代码（第 12 行）；当分母为零时，JVM 会抛出一个 `ArithmeticException` 对象。

#### 软件工程观察 11.1
异常可能通过 try 块中显式提到的代码出现、通过 try 块中代码的深层方法调用出现，或者在 Java 虚拟机执行字节码时出现。

#### 捕获异常
此示例中的 try 块后面跟着两个 catch 块——一个处理 `InputMismatchException`（第 34–41 行），另一个处理 `ArithmeticException`（第 42–48 行）。catch 块以关键字开头，后面紧跟括号内的异常类型和参数。[注：“catch 子句”一术语指的是关键字后面的代码块，不包括关键字本身。为了简单起见，我们使用“catch 块”来指代 catch 关键字后面的代码块以及 catch 关键字本身。] try 块后面必须至少跟有一个 catch 块。当 try 块中发生异常时，程序控制将转移到后续异常类型与抛出的异常匹配的第一个 catch 块。在图 11.3 中，第一个 catch 块捕获 `InputMismatchExceptions`（当输入无效输入时发生），第二个块捕获 `ArithmeticExceptions`（当尝试除以零时发生）。在异常被处理后，程序控制不会返回到 try 块，因为 try 块已经结束（其局部变量也已丢失）。相反，控制将在最后一个 catch 块之后恢复。这被称为异常处理的终止模型。某些语言使用异常处理的恢复模型，即在异常被处理后，控制将从抛出点之后立即恢复。

请注意，我们根据其类型（`inputMismatchException` 和 `arithmeticException`）为异常参数命名。Java 程序员通常使用字母 `e` 作为异常参数的名称。

执行 catch 块后，此程序的控制流将进入 catch 块后的第一个语句（在本例中为第 48 行）。while 条件为真（`continueLoop` 包含初始值 `true`），控制返回循环开头并提示用户输入。该语句将一直循环直到输入有效。在该点，程序控制到达第 32 行，将 `false` 赋值给 `continueLoop`。try 块随后终止。如果 try 块没有抛出异常，将跳过 catch 块并继续 catch 块后的第一个语句（我们在结束时学习另一种可能性）。

#### 多异常捕获
try 块后面跟着多个 catch 块是相当常见的。如果 catch 体的内容相同，可以使用多捕获（Java 7 引入）在单个 catch 中捕获这些类型。多捕获的语法为：
`catch (Type1 | Type2)` 每个异常类型之间用竖线 (|) 分隔。可以捕获任意数量的 `Throwable` 类型。

### 11.4 何时使用异常处理

异常处理旨在处理同步错误，这些错误在语句执行时发生。我们在整本书中常见的常见示例包括数组索引越界、算术溢出（即值超出可表示的范围）、除以零、无效的方法参数以及线程中断（我们将在第 23 章中看到）。异常处理的设计**不用于**处理与异步事件相关的问题（例如磁盘 I/O 完成、网络消息到达、鼠标点击和击键），这些事件与程序的控制流并行发生且独立于程序的控制流。

> **软件工程观察 11.2**
> 从设计过程之初就将异常处理和错误恢复策略整合到系统中——在系统实现后再加入这些措施是非常困难的。

> **软件工程观察 11.3**
> 异常处理提供了一种单一、统一的技术，用于记录、检测和恢复错误。这有助于开发大型项目的程序员理解彼此的错误处理代码。

> **软件工程观察 11.4**
> 产生异常的情况非常多——某些异常更容易从中恢复。

### 11.5 Java 异常层次结构

所有 Java 类都直接或间接地继承自 `Exception` 类，形成了一个继承层次结构。你可以用你自己的异常类来扩展这一层次结构。

**图 11.4** Throwable 继承层次的一部分。

`Throwable`（`Object` 的子类）继承层次的一小部分，它是 `Exception` 的父类。你可以用自己的异常类扩展这一层次。`Throwable` 对象可以用于异常处理机制。`Throwable` 有两个直接子类：`Exception` 和 `Error`。`Exception` 类及其子类（例如 `RuntimeException` (`java.lang`) 和 `IOException` (`java.io`)）代表 Java 程序中发生的异常情况，可以被应用程序捕获。`Error` 类及其子类代表发生在 JVM 中的异常情况——应用程序通常无法从中恢复。

Java 异常层次结构包含数百类。有关 Java 异常类的信息可以在整个 Java API 中找到。你可以在 `docs.oracle.com/7/docs/api/java/lang/Throwable.html` 查看 `Throwable` 的文档。从那里你可以查看这些类以获取更多关于 Java 异常和错误的信息。

#### 检查异常与未检查异常
Java 区分了检查异常和未检查异常。这种区别非常重要，因为 Java 编译器对检查异常强制特殊要求（稍后讨论）。异常的类型决定了它是检查异常还是未检查异常。

#### RuntimeException 是未检查异常
所有 `RuntimeException` (`java.lang`) 的直接或间接子类异常都是未检查异常。这些通常是由程序代码中的缺陷引起的。未检查异常的示例包括：

- `ArrayIndexOutOfBoundsException`（在第 7 章讨论过）：通过确保数组索引始终大于等于 0 且小于数组长度可以避免这种异常。
- `ArithmeticException`（如图 11.3 所示）：通过在执行计算之前检查分母是否为 0，可以避免除以零时发生的 `ArithmeticException`。

继承自 `Error` 类（图 11.4）的直接或间接子类是未检查的，因为 `Error` 是如此严重的问题，你的程序不应该尝试处理它们。

#### 检查异常
所有继承自 `Exception` 但不是直接或间接继承自 `RuntimeException` 类的类都被视为检查异常。此类异常通常由不受程序控制的情况引起——例如，在文件处理中，如果文件不存在，程序无法打开它。

#### 编译器与受检查异常
编译器会检查每个方法和方法声明，以确定该方法是否抛出了受检查异常。如果是，编译器会验证该受检查异常是否被捕获或在 `throws` 子句中声明——这被称为捕获或声明要求。我们在接下来的示例中展示如何捕获或声明受检查异常。回想第 11.3 节，`throws` 子句指定了方法抛出的异常。此类异常不会在方法体内被捕获。为了满足捕获或声明要求中的“捕获”部分，产生异常的代码必须封装在 `try` 块中，并为受检查异常类型（或其一个子类）提供一个 `catch` 处理器。为了满足捕获或声明要求中的“声明”部分，包含产生异常代码的方法必须在参数列表之后、方法体之前拥有一个包含该受检查异常类型的 `throws` 子句。如果不满足捕获或声明要求，编译器将发出错误信息。这迫使你去思考当调用抛出受检查异常的方法时会发生的问题。

> **异常预防技巧 11.2**
> 你必须声明所有的受检查异常。相比于简单忽略它们，这会产生更健壮的代码。

> **常见编程错误 11.2**
> 如果子类方法重写父类方法，子类在其 `throws` 子句中列出与父类方法相同的异常将是错误的。然而，子类的 `throws` 子句可以包含父类 `throws` 子句的子集。

> **软件工程观察 11.5**
> 如果你调用抛出受检查异常的其他方法，这些异常必须被捕获或声明。如果异常可以在方法中被有意义地处理，则方法应该捕获异常而不是声明它。

#### 编译器与未检查异常
与受检查异常不同，Java 编译器不会检查代码以确定未检查异常是否被捕获或声明。未检查异常通常通过正确的编码来防止。例如，`quotient`（第 9–13 行）抛出的未检查异常 `ArithmeticException` 可以在 11.3 节中通过在执行除法之前确保分母不为零来避免。未检查异常不需要在方法的 `throws` 子句中列出——即使不需要应用程序捕获此类异常。

> **软件工程观察 11.6**
> 尽管编译器不强制执行未检查异常的捕获或声明要求，但在已知此类异常可能发生时，请提供异常处理代码。例如，程序应该处理来自 `Integer.parseInt` 抛出的 `NumberFormatException`，尽管 `NumberFormatException` 是 `RuntimeException` 的间接子类（因此是未检查异常）。这使得你的程序更加健壮。

#### 捕获子类异常
如果编写 `catch` 处理器来捕获父类异常对象，那么它也可以捕获该类所有子类的对象。这使得 `catch` 能够以多态方式处理相关异常。如果这些异常需要不同的处理，你可以单独捕获每个子类。

#### 仅执行第一个匹配的 catch
如果多个 `catch` 块匹配特定的异常类型，当发生该类型的异常时，只有第一个匹配的 `catch` 块会执行。在两个不同的 `catch` 块中捕获完全相同的类型是错误的。然而，可以有多个 `catch` 块匹配一个异常——即类型与异常类型或其父类相同。例如，我们可以为 `ArithmeticException` 编写一个 `catch` 块，再为 `Exception` 编写另一个——两者都会匹配 `ArithmeticException`，但只有第一个匹配的 `catch` 会执行。

> **常见编程错误 11.3**
> 在捕获子类类型的 `catch` 块之前放置父类异常类型的 `catch` 块会阻止那些 `catch` 块执行，从而导致编译错误。

> **异常预防技巧 11.3**
> 如果你忘记显式地测试一个或多个子类类型，单独捕获子类会导致错误；捕获父类可以确保所有子类对象。在所有其他子类 `catch` 块之后放置父类类型的 `catch` 块可以确保所有异常最终都被捕获。

> **软件工程观察 11.7**
> 在工业界中，不建议抛出或捕获 `Exception` 类型——我们仅用它演示异常处理机制。在后续章节中，我们通常抛出更具体的异常类型。

### 11.6 finally 块

我们之前讨论了 `finally` 块。现在 `do...while` 循环的条件为假，`main` 方法结束。

try 块及其对应的 catch 和/或 finally 块构成了一个语句。不要混淆“try 块”和“try 语句”这两个术语——后者包含了 try 块以及随其后的 catch 块和/或 finally 块。

与任何其他代码块一样，当 try 结束时，在块中声明的局部变量将超出作用范围且不再可访问；try 块中的变量在相应的 catch 块中是不可见的。当一个 catch 块结束时，在 catch 块内部声明的局部变量（包括该 catch 块的异常）也会超出作用范围并销毁。try 语句中剩余的 catch 块将被忽略，执行将从 try...catch 序列之后的第一行代码继续——如果存在 finally 块，则将执行该块。

### 使用 throws 子句
`quotient` 方法（11.3，第 9–13 行）的第 10 行被称为 `throws` 子句。它指定了发生问题时可能抛出的异常。该子句必须出现在方法的参数列表之后、方法体之前，包含一个用逗号分隔的异常类型列表。此类异常可能由方法体中的语句或从那里调用的方法抛出。我们在应用程序中添加了 `throws` 子句，以指示该方法可能会抛出 `ArithmeticException`。因此，`quotient` 的调用者被告知方法可能会抛出 `ArithmeticException`。某些异常类型（如 `ArithmeticException`）不需要在 `throws` 子句中列出。对于那些必须列出的异常，方法可以抛出与 `throws` 子句中列出的类有关系的异常。你将在第 11.5 节中学习更多信息。

在第 12 行，如果分母为 0，JVM 会抛出 `ArithmeticException`。该对象将被第 42–47 行的 catch 块捕获，该块通过隐式调用异常的 `toString` 方法显示对象的的基本信息，然后要求用户重试。

如果分母不为 0，方法 `quotient` 执行除法并将结果返回给 try 块中 `quotient` 的调用点（第 29 行）。第 30–31 行显示计算结果，第 32 行继续使 `continueLoop` 为 false。如果 try 块成功完成，程序将跳过 catch 块并最终到达第 48 行的条件，方法正常完成执行。

当 `quotient` 抛出 `ArithmeticException` 时，`quotient` 终止且不返回值，`quotient` 的局部变量将超出作用范围（并被销毁）。如果没有对这些对象的其他引用，这些对象将被标记为垃圾回收。此外，当异常发生时，调用 `quotient` 的 try 块会在执行第 30–32 行之前终止。在这里，如果在抛出异常之前在 try 块中创建了局部变量，这些变量也将超出作用范围。

如果第 25 行或 27 行生成了 `InputMismatchException`，try 块终止，执行从第 34–41 行的 catch 块继续。在这种情况下，不会调用方法 `quotient`。然后 `main` 在最后一个 catch 块（第 48 行）之后继续。
