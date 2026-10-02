
图 E.12 输出根据 `depositAmount` 更改后显示的新账户余额。

## E.4 使用 step、step up 和 next 命令控制执行

有时，您需要逐行执行应用程序以查找并修复错误。通过遍历应用程序的一部分可以帮助您验证方法的代码是否执行正确。在本节中，您将学习如何使用调试器完成此任务。您在本节中学习的命令允许您按行执行方法、一次性执行一个方法的所有语句，或者执行一个方法的剩余语句（如果您已经在方法内部执行了某些部分语句）。

再次，我们假设您正在包含附录示例的目录中工作，并使用 `-g` 编译器选项进行了调试编译。

### 附录 E 使用调试器

1.  **启动调试器**。输入 `jdb` 启动调试器。
2.  **设置断点**。输入 `step at AccountTest:19` 在第 19 行设置断点。
3.  **运行应用程序**。运行 `AccountTest` 来运行应用程序。在应用程序显示两条输出消息后，调试器指示到达断点并显示第 19 行的代码。调试器和应用程序随后等待输入下一个命令。
4.  **使用 step 命令**。`step` 命令执行应用程序中的下一个语句。如果要执行的下一语句是方法调用，控制权将转移到被调用的方法。`step` 命令允许您进入方法并研究该方法的各个语句。例如，您可以使用 `print` 和 `set` 命令查看并修改方法中的变量。现在您通过输入 `step`（图 E.13）进入 Account 类的 `credit` 方法（图 3.8）。调试器指示步进已完成并显示下一个可执行的语句——在这种情况下，是 Account 类的第 21 行（图 3.8）。

```
> Step completed: "thread-main", Account.deposit(), line=24 bci=0
  if (depositAmount > 0.0) // if the depositAmount is valid
main[1]
```

图 E.13 进入 credit 方法。

5.  **使用 step up 命令**。在进入 `credit` 方法后，输入 `step up`。该命令执行方法中的剩余语句并返回到调用该方法的地方。`credit` 方法仅包含一条语句，将方法的参数金额加到实例变量 `balance` 上。`step up` 命令执行此语句，然后在 AccountTest 的第 22 行之前暂停。下一个操作将打印新的账户余额（图 E.14）。在很长的方法中，您可能想看几行代码，然后继续调试调用者的代码。`step` 命令适用于您不希望继续逐步执行整个方法的情况。

```
> Step completed: "thread-main", Account.deposit(), line=22 bci=65
  System.printf("new account balance:
main[1]
```

图 E.14 跳出方法。

### E.4 使用 step、step up 和 next 命令控制执行 1157

6.  **使用 cont 命令继续执行**。输入 `cont` 命令（图 E.15）继续执行。第 22 行的语句执行，应用程序终止。

```
main[1] cont
> new account balance: $75.00
应用程序已退出
C:\examples\debugger>
```

图 E.15 继续执行。

7.  **重启调试器**。使用 `jdb` 重启调试器。
8.  **设置断点**。断点仅持续到调试会话结束。在 E.6 节中，您将学习如何手动清除断点。因此，当调试会话结束时，所有断点将被移除。要重置断点，再次输入 `step at AccountTest:19`。
9.  **运行应用程序**。输入 `run AccountTest` 运行应用程序。如步骤 3 所示，到达第 19 行的断点，然后调试器等待下一个命令。
10. **使用 next 命令**。输入 `next`。该命令的行为类似于 `step` 命令，但它会执行整个方法调用。在这种情况下，它执行方法并暂停在第 22 行。

```
main[1] next
> Step completed: "thread-main", Account.deposit(), line=22 bci=65
  System.printf("new account balance:
main[1]
```

图 E.16 跳过方法调用。

11. **使用 exit 命令**。使用 `exit` 命令结束调试会话（图 E.17）。

```
main[1] exit
c:\examples\debugger>
```

图 E.17 退出调试器。

### 附录 E 使用调试器 1158

## E.5 watch 命令

在本节中，我们介绍 `watch` 命令，调试器将通知您。在本节中，您将学习字段何时发生变化以及字段是如何修改的。

与前面的节一样，我们假设您已按照 E.2 节中的步骤 1 和步骤 2 打开命令提示符、更改目录并为了调试编译 AccountTest 和 Account（即使用 `-g` ）。

1.  **启动调试器**。通过输入 `jdb` 启动调试器。
2.  **观察类字段**。通过输入 `watch Account.balance` 设置 Account 字段的观察（图 E.18）。您可以在调试执行期间对任何字段设置观察。当字段值即将变化时，调试器进入中断模式并通知您值将变化。观察只能放在字段上，不能放在局部变量上。

```
c:\examples\debugger>jdb
Initializing jdb -
watch Account.balance
deferring watch modification of Account.balance.
It will be set after the class is loaded.
>
```

图 E.18 观察 Account 字段。

3.  **运行应用程序**。使用 `run AccountTest` 运行应用程序。调试器将通知您字段余额的值将变化（图 E.19）。当应用程序启动时，创建一个初始余额为 $50.00 的 Account 实例，并将引用赋值给局部变量 account（图 E.1 第 9 行）。回顾 3.8，当此对象的构造函数运行时，如果参数 `initialBalance` 大于 0.0，实例变量 `balance` 被赋值参数 `initialBalance` 的值。调试器将通知您 `balance` 将设置为 50.0。
4.  **向账户增加金额**。输入 `cont` 继续执行应用程序。在到达图 E.1 第 19 行调用 Account 方法 `credit` 的代码之前，应用程序正常执行。调试器将通知您实例变量 `balance` 将发生变化（图 E.20）。尽管 Account 类的第 19 行调用了 `deposit` 方法，但 Account 类 `deposit` 方法的第 25 行实际上更改了 `balance` 的值。

### E.5 watch 命令 1159

```
> run AccountTest
run AccountTest
Set uncaught java.lang.Throwable
Set deferred uncaught java.lang.Throwable
>
VM Started: Set deferred watch modification of Account.balance
Field(Account.balance) is 0.0, will be 50.0: "thread-main", Account.<init>(), line=18 bci=17
	this.balance = balance; // assign to instance variable balance
main[1]
```

**图 E.19** 当账户创建且其余额字段将要修改时，AccountTest 应用程序停止。

```
main[1] cont
> initial account balance: $50.00
adding 25.00 to account balance
Field(Account.balance) is 50.0, will be 75.0: "thread-main", Account.deposit(), line=25 bci=13
	balance = balance + depositAmount; // add it to the balance
main[1]
```

**图 E.20** 通过调用 Account 方法 credit 来更改 balance 的值。

5.  **继续执行**。输入 `cont`——应用程序将完成执行，因为应用程序没有尝试对 `balance` 进行任何额外的更改（图 E.21）。

```
main[1] cont
> new account balance: $75.00
应用程序退出
C:\examples\debugger
```

**图 E.21** 继续执行 AccountTest。

6.  **重启调试器并重置变量的监视**。输入 `jdb` 重启调试器。再次对 Account 实例变量 `balance` 设置监视点——通过输入 `watch Account.balance`，然后运行 `AccountTest` 来运行应用程序。
7.  **移除对字段的监视**。假设你只想在程序执行的部分期间监控某个字段。你可以移除调试器对变量 `Account.balance` 的监视（图 E.22）。输入 `cont`——应用程序将完成执行而不会再次进入断点模式。

### 附录 E 使用调试器

```
main[1] unwatch Account.balance
Removed: watch modification of Account.balance
main[1] cont
> initial account balance: $50.00
adding 25.00 to account balance
new account balance: $75.00
The application exited
:\examples\debugger>
```

**图 E.22** 移除对变量 balance 的监视。

## E.6 clear 命令

在上节中，你学习了如何使用 `unwatch` 命令移除对字段的监视。调试器还提供了 `clear` 命令来从应用程序中移除断点。你经常需要调试应用程序的重复操作，例如循环。你可能想在循环的多次（而非所有）迭代中检查变量的值。如果你在循环体内设置了断点，调试器将在每次执行包含断点的行之前暂停。在确定循环工作正常后，你可能想移除断点并让迭代正常进行。在本节中，我们使用图 5.6 中的复利计算应用程序来演示当你在语句体中设置断点时调试器是如何行为的，以及如何在调试会话中移除断点。

- 打开命令提示符窗口

### E.6 clear 命令

它将在类加载后设置。

```
> run Interest
run Interest
Set uncaught java.lang.Throwable
Set deferred uncaught java.lang.Throwable
>
VM Started: Set deferred breakpoint Interest:22
Set deferred breakpoint Interest:13
Breakpoint hit: "thread-main", Interest.main(), line=13 bci=9
13 System.out.printf("%s%20f%n", "Year", "Amount on deposit")
main[1]
```

图 E.23 到达 Interest 应用程序第 13 行的断点。

```
main[1]
> Year Amount on deposit
Breakpoint hit: "thread-main", Interest.main(), line=22 bci=55
22 System.out.printf("%4d,%20.2f%n", year, amount")
main[1]
```

图 E.24 到达 Interest 应用程序第 22 行的断点。

```
main[1] print year
year = 1
main[1] print amount
amount = 1050.0
main[1]
```

图 E.25 在 Interest 的 for 循环第一次迭代中打印 year 和 amount。

6.  **继续执行**。输入 `cont` 继续执行。第 22 行执行并打印 year 和 amount 的当前值。当 for 进入第二次迭代时，调试器会通知你第 22 行的断点已第二次到达。调试器在每次执行设置了断点的行时都会暂停执行——当断点出现在循环中时，调试器会再次暂停变量的值，以查看自 for 第一次迭代以来值发生了变化（图 E.26）。

```
main[1] cont
> 1 1,050.00
Breakpoint hit: "thread-main", Interest.main(), line=22 bci=55
22 System.out.printf("%4d,%20.2f%n", year, amount")
main[1] print amount
amount = 1102.5
main[1] print year
year = 2
main[1]
```

图 E.26 在 Interest 的第二次迭代中打印 year 和 amount。

7.  **移除断点**。你可以通过输入 `clear` 显示应用程序中所有断点的列表（图 E.27）。假设你认为 Interest 的 for 语句工作正常，因此想移除第 22 行的断点并允许剩余迭代继续。你可以通过 `clear Interest:22` 移除第 22 行的断点。现在输入 `clear` 列出剩余断点。调试器应仅显示第 13 行的断点（图 E.27）。该断点已到达。

```
main[1] clear
Breakpoints set:
  breakpoint Interest:13
  breakpoint Interest:22
main[1] clear Interest:22
Removed: breakpoint Interest:22
main[1] clear
Breakpoints set:
  breakpoint Interest:13
main[1]
```

**图 E.27** 移除第 22 行的断点。

8.  **移除断点后继续执行**。输入 `cont` 继续执行。在执行第 22 行的 printf 语句之前，如果断点已成功移除，应用程序将为当前和剩余迭代产生正确的输出（图 E.28）。

```
main[1] cont
> 2 102.50
  3 157.63
  4 215.51
  5 276.28
  6 340.10
  7 407.10
  8 477.46
  9 551.33
  10 628.89
The application exited
C:\examples\debugger>
```
