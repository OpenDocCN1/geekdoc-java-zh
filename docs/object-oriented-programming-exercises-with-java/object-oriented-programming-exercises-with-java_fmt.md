
# Java 面向对象编程练习

## 1. 电影

让我们创建一个处理电影及其评分的程序。我们需要记录关于电影的以下信息：

- 标题
- 导演
- 时长（分钟）
- 发映年份

`Movie` 类应该有一个方法，根据当前年份和发行年份返回电影的年龄。

对于每部电影 `Movie`，我们还应该保留一组范围从 0 到 5 的评分 `Ratings`。此外，类型为 `Movie` 的电影应该能够计算评分的平均值。

在 `main` 方法中，我们应该创建多个电影以及一些评分。然后，我们应该打印每部电影的详情以及评分平均值。

### 建议解决方案

我们从创建 `Movie` 类开始：

```java
import java.time.Year;
import java.util.ArrayList;

public class Movie {
    private String name;
    private int year;
    private int duration;
    private String director;
    private ArrayList<Integer> reviews;
    // 这里有更多内容
}
```

列表 1-1: Movie.java

然后，我们添加另外三个构造函数：默认构造函数、全构造函数和拷贝构造函数：

```java
public Movie() {
    name = "N/A";
    year = 0;
    duration = 0;
    director = "N/A";
    reviews = new ArrayList<>();
}
public Movie(String _name, int _year, int _duration, String _director) {
    name = _name;
    year = _year;
    duration = _duration;
    director = _director;
    reviews = new ArrayList<>();
}
public Movie(Movie _movie) {
    name = _movie.name;
    year = _movie.year;
    duration = _movie.duration;
    director = _movie.director;
    reviews = new ArrayList<>(_movie.reviews);
}
```

列表 1-2: Movie.java

注意，Java 默认并不提供拷贝构造函数；我们必须自己引入它。

此外，在拷贝构造函数中，我们通过使用 `ArrayList` 的拷贝构造函数来实例化 `reviews` 列表。只要列表包含基本数据类型或不可变类型（分别为 `int` 或 `String`），这就能正常工作。

如果列表包含自定义对象，那么我们必须做两件事：首先，我们必须在自定义类中实现 `Cloneable` 接口（即在自定义类内部实现 `clone()` 方法）。然后，我们必须使用以下代码对列表本身进行拷贝：

```java
reviews = (ArrayList<MyCustomClass>)_movie.reviews.clone();
```

接下来，我们添加设置器方法（`setter` 方法）：

```java
public void setName(String _name) {
    name = _name;
}
public void setYear(int _year) {
    year = _year;
}
public void setDuration(int _duration) {
    duration = _duration;
}
public void setDirector(String _director) {
    director = _director;
}
```

列表 1-3: Movie.java

在构造函数和 setter 方法中，我们确实对输入值进行一些检查，例如验证年份值是否大于 1900 年。我们将此类功能留给以后的项目，届时我们将引入与用户的交互。

关于 `reviews` 列表，我们添加了两个方法：一个用于向列表中插入评分，另一个用于计算平均分：

```java
public void addReview(int score) {
  if (score >= 0 && score <= 5)
    reviews.add(score);
  else
    System.out.println("invalid review score");
}
public double getReviewAverage() {
  double sum = 0.0;
  for (int i = 0; i < reviews.size(); i++) {
    sum += reviews.get(i);
  }
  if (reviews.size() > 0)
    return sum / reviews.size();
  else
    return 0;
}
```

列表 1-4: Movie.java

接下来，我们添加一个计算电影年龄的方法：

```java
public int getAge() {
  int current_year = Year.now().getValue();
  return current_year - year;
}
```

列表 1-5: Movie.java

为了从系统获取当前年份，我们使用了 `java.time.Year` 类。

最后，我们添加一个 `toString()` 方法，来提供 `Movie` 对象的字符串表示：

```java
@Override
public String toString() {
    return "Movie{" +
        "name=" + name + "\" +
        "year=" + year +
        "duration=" + duration +
        "director=" + director + "\" +
        "reviews=" + reviews + 
 };}
}
```

列表 1-6: Movie.java

在 `main` 方法中，我们创建了一些电影对象并测试其功能：

```java
public static void main(String[] args) {
    Movie m1 = new Movie();
    Movie m2 = new Movie("Hunger Games", 2012, 142, "Gary Ross");
    m2.addReview(5);
    m2.addReview(4);
    m2.addReview(6);
    Movie m3 = new Movie(m2);
    System.out.println(m1);
    System.out.println(m2);
    System.out.println(m3);
}
```

列表 1-7: Movie.java

你可以在 GitHub 上找到此项目：https://github.com/htset/java_oop_exercises/tree/master

## 2. 医院

在这个项目中，我们将创建一个管理患者的控制台应用程序。医院由诊所组成（例如手术室）。对于每个患者，我们将维护以下信息：

- 姓名
- 出生年份
- 房间号
- 测量列表（温度和时间）

患者类应该能够返回记录的最高温度。在 `main` 方法中，我们应该创建一些诊所以及患者，并为它们添加一些测量数据。

### 建议解决方案

我们从定义 `Clinic` 类开始：

```java
public class Clinic {
    private String name;
    private String director;
    public Clinic(String _name, String _director) {
        name = _name;
        director = _director;
    }
    public Clinic() {
        name = "N/A";
        director = "N/A";
    }
    @Override
    public String toString() {
        return "name=" + name + "\" +
        ", director=" + director + "\"";
    }
    public void setDirector(String _director) {
        director = _director;
    }
}
```

列表 2-1: Clinic.java

我们继续定义 `Patient` 类：

```java
public class Patient {
    private String name;
    private String surname;
    private int yearOfBirth;
    private Clinic clinic;
    private String room;
    private ArrayList<Measurement> pm;
}
```

列表 2-2: Patient.java

这里有两个值得提到的点：首先，`Patient` 对象持有对 `Clinic` 对象的引用。`Clinic` 对象独立于 `Patient` 对象存在，因为多个患者可能属于同一个诊所。这是聚合的一个示例：我们保留了指向外部对象的引用。

聚合的反面是组合：当一个对象包含其他对象时。这就是 `Measurement` 列表的情况。为患者采集的温度与患者紧密相连，离开患者没有任何意义。如果患者对象被删除，删除温度信息也是可以的。

让我们先定义简单的 `Measurement` 类：

```java
import java.time.LocalDateTime;
public class Measurement {
    private double temp;
    private LocalDateTime date;
    public Measurement(double _temp, LocalDateTime _date){
        temp = _temp;
        date = _date;
    }
    public Measurement(){
        temp = 0;
        date = LocalDateTime.now();
    }
    public double getTemp() {
        return temp;
    }
    public LocalDateTime getDate() {
        return date;
    }
    @Override
    public String toString() {
        return "Measurement{" +
            "temp=" + temp +
            ", date=" + date +
            "}";
    }
}
```

列表 2-3: Measurement.java

```java
public Measurement(double _temp, Date _date){
    temp = _temp;
    date = (_date != null ? (Date)_date.clone() : null);
}
```

列表 2-4：示例代码

当我们不确定传递给方法的对象是否会在代码的其他部分被修改时，防御性编程是非常重要的。如果这些对象在某个时间点被修改了，我们将得到出乎意料的结果。为了简单起见，我们将信任我们的对象，并在后续示例不再不再防御性编程，但你明白这个意思。

现在，对于 `Patient` 类的实现，我们添加了所有的构造函数：

```java
public Patient(String _name, String _surname, int _yearOfBirth,
    Clinic _clinic, String _room){
    name = _name;
    yearOfBirth = _yearOfBirth;
    clinic = _clinic;
    room = _room;
    pm = new ArrayList<>();
}
public Patient(){
    name = "N/A";
    surname = "N/A";
    yearOfBirth = 0;
    clinic = null;
    room = "N/A";
    pm = new ArrayList<>();
}
}
```

列表 2-5：Patient.java

然后，我们有了 `Clinic` 的 setter 方法以及两个用于插入 `Measurement` 的方法：

```java
public void setClinic(Clinic _clinic) {
    clinic = _clinic;
}
public void insertMeasurement(Measurement m) {
    pm.add(m);
}
public void insertMeasurement(double _temp, LocalDateTime _date) {
    Measurement m = new Measurement(_temp, _date);
    pm.add(m);
}
```

列表 2-6：Patient.java

接下来，我们实现 `toString()` 方法，以及获取记录最高温度和患者年龄的方法：

```java
public double maxTemp() {
    double maxt = 0.0;
    for (Measurement m : pm) {
        if (m.getTemp() > maxt) {
            maxt = m.getTemp();
        }
    }
    return maxt;
}
@Override
public String toString() {
    return "Patient{" +
    "name="
```

列表 2-7：Patient.java

最后，在 `main()` 方法中，我们定义了许多诊所、患者和测量数据。注意我们如何在一处更改手术诊所主任的名称。此外，我们可以通过分配不同 `Clinic` 对象的引用将患者移动到另一个诊所：



```java
import java.time.LocalDateTime;
public class Hospital {
    public static void main(String[] args){
        Clinic c1 = new Clinic("Surgery", "A. Dobbs");
        Clinic c2 = new Clinic("Cardiology", "B. Smith");
        Clinic c3 = new Clinic("Orthopedics", "C. Stubbs");
        Patient p1 = new Patient("John", "Doe");
        Patient p2 = new Patient("Jane", "Doe", 1985, c2, "306");
        Patient p3 = new Patient("Jimmy", "Doe", 1956, c2, "306");
        p1.insertMeasurement(new Measurement(37.5,
            LocalDateTime.of(2023, 1, 1, 0, 0)));
        p1.insertMeasurement(new Measurement(38.1,
            LocalDateTime.of(2023, 1, 6, 0, 0)));
        p1.insertMeasurement(new Measurement(37.9,
            LocalDateTime.of(2023, 1, 1, 9, 0, 0)));
        p2.insertMeasurement(new Measurement(36.5,
            LocalDateTime.of(2023, 1, 1, 0, 0)));
        p2.insertMeasurement(new Measurement(38.0,
            LocalDateTime.of(2023, 1, 1, 6, 0, 0)));
        p3.insertMeasurement(new Measurement(39.5,
            LocalDateTime.of(2023, 1, 1, 0, 0, 0));
        p3.insertMeasurement(new Measurement(39.1,
            LocalDateTime.of(2023, 1, 1, 6, 0, 0)));
        p3.setClinic(c3);
        c1.setDirector("D. Jones");
        System.out.println(p1);
        System.out.println(p2);
        System.out.println(p3);
    }
}
```

列表 2-8：`Hospital.java`

你可以在 GitHub 上找到此项目：

https://github.com/htset/java_oop_exercises/tree/master/Hospital/src

## 3. 包裹运输

让我们创建一个类层次结构，模拟快递公司提供的不同类型的包裹。共有三种包裹，具有不同的费用和交付时间：

- 基础包裹：每公斤 5 欧元，5 天送达。如果包裹重量超过 10 公斤，则需要额外一天。
- 高级包裹：每公斤 6 欧元，额外收 2 欧元。包裹 2 天后交付。
- 隔夜包裹：第二天送达，每公斤 10 欧元。

在 `main()` 方法中，我们应该能够在同一个数组中插入各种包裹。最后，我们应该打印出所有的包裹。

### 建议解决方案

首先，我们创建一个抽象类作为包裹层次结构的根：

```java
import java.time.LocalDate;

public abstract class Package {
    protected double weight;
    protected LocalDate deliveryDate;

    public Package(double weight, LocalDate deliveryDate) {
        this.weight = weight;
        this.deliveryDate = deliveryDate;
    }

    public abstract double cost();
    public abstract LocalDate deliveryTime();
}
```

列表 3-1：`Package.java`

`BasePackage` 类实现了简单的版本，关于包裹的运输逻辑：

```java
import java.time.LocalDate;

public class BasePackage extends Package {
    public BasePackage(double weight, LocalDate deliveryDate) {
        super(weight, deliveryDate);
    }

    @Override
    public double cost() {
        if (weight > 10) {
            return (weight * 5) + 5;
        }
        return weight * 5;
    }

    @Override
    public LocalDate deliveryTime() {
        return deliveryDate.plusDays(5);
    }
}
```

列表 3-2：`BasePackage.java`

`AdvancedPackage` 类在方法的实现上有所不同，两个方法：

```java
import java.time.LocalDate;

public class AdvancedPackage extends Package {
    public AdvancedPackage(double weight, LocalDate deliveryDate) {
        super(weight, deliveryDate);
    }

    @Override
    public double cost() {
        return (weight * 6) + 2;
    }

    @Override
    public LocalDate deliveryTime() {
        return deliveryDate.plusDays(2);
    }
}
```

列表 3-3：`AdvancedPackage.java`

同样，我们实现了 `OvernightPackage`：

```java
import java.time.LocalDate;

public class OvernightPackage extends Package {
    public OvernightPackage(double weight, LocalDate deliveryDate) {
        super(weight, deliveryDate);
    }

    @Override
    public double cost() {
        return weight * 10;
    }

    @Override
    public LocalDate deliveryTime() {
        return deliveryDate.plusDays(1);
    }
}
```

列表 3-4：`OvernightPackage.java`

常量包含在一个名为 `Constants` 的特殊类中：

```java
class Constants {
    public static final double BASE_COST = 5;
    public static final int BASE_DAYS = 5;
    public static final double BASE_THRESHOLD = 10;
    public static final double ADVANCED_COST = 6;
    public static final double ADVANCED_FEE = 2;
    public static final int ADVANCED_DAYS = 2;
    public static final double OVERNIGHT_COST = 10;
    public static final int OVERNIGHT_DAYS = 1;
}
```

列表 3-5：`Constants.java`

多态的重要性可以在 `main()` 方法中体现：

```java
import java.time.LocalDate;
public class Main {
    public static void main(String[] args) {
        Package[] packages = new Package[4];
        packages[0] = new BasePackage(15, LocalDate.of(2023, 1, 12));
        packages[1] = new BasePackage(9.5, LocalDate.of(2022, 12, 30));
        packages[2] = new AdvancedPackage(15, LocalDate.of(2023, 1, 12));
        packages[3] = new OvernightPackage(1, LocalDate.of(2023, 1, 20));

        int i = 1;
        for (Package p : packages) {
            System.out.println("Package no. " + i++);
            System.out.println("Type: " + p.getClass());
            System.out.println("Delivery date: " + p.deliveryTime());
            System.out.println("Cost: " + p.cost() + "\n");
        }
    }
}
```

列表 3-6：`Main.java`

在这里，我们定义了一个包含 `Package` 对象的数组（也可以是 `ArrayList`）。这意味着我们也可以使用该数组来包含派自 `Package` 的对象的引用，例如 `BasePackage`。这样，我们能够存储不同类型的对象（父类）存入同一个数组，并对它们进行统一处理。

同样注意我们如何找到所指向对象的类型：

```java
p.getClass()
```

当 `p` 引用一个 `BasePackage` 对象时，结果将是 `class BasePackage`。

你可以在 GitHub 上找到此项目：

https://github.com/htset/java_oop_exercises/tree/master/PackageShipping/src

## 4. 带有持久化的包裹运输

我们将继续进行包裹运输项目，并进行以下改进：

- 用户交互：用户应该能够添加和删除包裹、搜索包裹（基于收件人姓名）以及列出所有可用包裹。
- 文件持久化：包裹应该保存到单个文件中。此外，当应用程序启动时，应该从文件中加载包裹。

### 建议的解决方案

首先，让我们看看 `main()` 方法现在是什么样子：

```java
import java.io.IOException;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        try {
            ArrayList<Package> list = new ArrayList<Package>();
            UIService ui = new UIService(list);
            ui.loadFromFile();
            ui.menu();
        } catch (IOException ioe) {
            System.out.println("IO Exception!");
            ioe.printStackTrace();
            System.exit(1);
        }
    }
}
```

### 列表 4-1：`Main.java`

在这里，我们定义了一个 `ArrayList`，它包含对 `Package` 对象（及其派生类）的引用。我们还定义了一个名为 `UIService` 的新类来处理与用户的交互。我们将 `ArrayList` 传递给 `UIService` 类的构造函数，并继续从文本加载包裹。然后，`menu()` 方法处理与用户的所有交互。

`UIService` 类在这里进行了部分定义：

```java
import java.io.*;
import java.time.LocalDate;
import java.util.List;
import java.util.Scanner;

public class UIService {
    private List<Package> packages;

    public UIService(List<Package> _packages) {
        packages = _packages;
    }

...
}
```

### 列表 4-2：`UIService.java`

在类的构造函数中，我们存储了对 Package 列表的引用；我们将在将在后续方法中使用它。

`menu()` 方法维持一个循环并为用户提供选项：

```java
public void menu() throws IOException {
    Scanner in = new Scanner(System.in);
    int option;
    do {
        System.out.println("Options: ");
        System.out.println("1 Add package ");
        System.out.println("2 Search package ");
        System.out.println("3 Delete package ");
        System.out.println("4 View all packages ");
        System.out.println("0 Exit ");
        option = in.nextInt();
        in.nextLine();

        switch (option) {
            case 1:
                addPackage();
                break;
            case 2:
                searchPackage();
                break;
            case 3:
                deletePackage();
                break;
            case 4:
                listPackages();
                break;
            case 0:
                break;
            default:
                System.out.println("Please type again:");
                break;
        }
    } while (option != 0);
}
```

### 列表 4-3：`UIService.java`

关于使用 `Scanner` 类读取的一个注意事项，当我们混合使用 `nextLine()` 和 `nextInt()`（或通用的 `nextXXX()`）时：当我们使用 `nextInt()` 从控制台读取一个整数时，末尾的行不会被读取，并将作为流中的下一个字符存在。如果我们之后使用 `nextLine()`（例如读取一整行），换行符将被读取，该方法将在不读取任何文本的情况下返回。为了解决这个问题，我们在 `nextInt()` 之后调用 `nextLine()`（或任何类似的方法），以便将换行符从流中取出。

接下来，`addPackage()` 方法从用户处获取包裹信息，创建所选类型的 `Package` 并将其插入列表：



```java
private void addPackage() throws IOException {
  Scanner in = new Scanner(System.in);
  int option;
  String recipient_name, recipient_address;
  double weight;

  System.out.println("Type of package (1-Basic, 2-Advanced, 3-Overnight):");
  option = in.nextInt();
  in.nextLine();
  System.out.println("Recipient name: ");
  recipient_name = in.nextLine();
  System.out.println("Recipient address: ");
  recipient_address = in.nextLine();
  System.out.println("Weight (kg):");
  weight = in.nextDouble();
  in.nextLine();

  switch (option) {
    case 1:
        packages.add(new BasePackage(recipient_name, recipient_address, weight, LocalDate.now()));
        saveToFile();
        break;
    case 2:
        packages.add(new AdvancedPackage(recipient_name, recipient_address, weight, LocalDate.now()));
        saveToFile();
        break;
    case 3:
        packages.add(new OvernightPackage(recipient_name, recipient_address, weight, LocalDate.now()));
        saveToFile();
        break;
    default:
        break;
  }
}
```

### 4-4: UIService.java

注意我们如何动态创建新包裹以及如何将它们的引用传递给列表。我们可以根据收件人姓名搜索包裹（或包裹）并打印所有细节：

```java
private void searchPackage() {
    Scanner in = new Scanner(System.in);
    String recipient_name;
    System.out.println("Enter recipient name (partial): ");
    recipient_name = in.nextLine();

    for (Package p : packages) {
        if (p.getRecipient().indexOf(recipient_name) >= 0) {
            System.out.println(p);
        }
    }
}
```

### 4-5: UIService.java

为了删除一个包裹，我们首先根据收件人的姓名搜索它。然后让用户选择要删除的包裹：

```java
private void deletePackage() throws IOException {
    Scanner in = new Scanner(System.in);
    String recipient_name;
    System.out.print("Enter name (partial): ");
    recipient_name = in.nextLine();

    int i = 0;
    System.out.println("The following packages were found:");
    for (Package p : packages) {
        if (p.getRecipient().indexOf(recipient_name) >= 0) {
            System.out.println((i + 1) + ": ");
            System.out.println(p);
        }
        i++;
    }

    int option;
    System.out.println("Please enter the no. to delete (0 to cancel):");
    option = in.nextInt();
    in.nextLine();

    if (option > 0) {
        packages.remove(option - 1);
        System.out.println("package deleted");
        saveToFile();
    }
}
```

### 4-6: UIService.java

`listPackages()` 方法简单地打印列表中所有的包裹：

```java
private void listPackages() {
    for (Package p : packages) {
        System.out.println(p);
    }
}
```

### 4-7: UIService.java

现在是查看文件处理方法。当插入（或删除）新包裹时，我们需要更新存储包裹的文本文件。我们选择的方法是在添加或删除包裹时清空文件并重写。这就是 `saveToFile()` 所做的：

```java
private void saveToFile() throws IOException {
    BufferedWriter writer = new BufferedWriter(new FileWriter("packages.txt"));
    for (Package p : packages) {
        writer.write(p.serialize());
    }
    writer.close();
}
```

### 4-8: UIService.java

启动时，我们加载文件中存储的包裹信息，一个个创建包裹并将它们存储在列表中：

```java
public void loadFromFile() throws IOException {
    packages.clear();

    File file = new File("packages.txt");
    if (!file.exists()) {
        file.createNewFile();
    }

    BufferedReader reader = new BufferedReader(new FileReader(file));
    String line;
    String package_str = "";
    while ((line = reader.readLine()) != null) {
      if (line.indexOf("-") == 0) {
        Package p;
        if (package_str.indexOf("Base Package") == 0) {
          p = new BasePackage();
          p.deserialize(package_str);
          packages.add(p);
        } else if (package_str.indexOf("Advanced Package") == 0) {
          p = new AdvancedPackage();
          p.deserialize(package_str);
          packages.add(p);
        } else if (package_str.indexOf("Overnight Package") == 0) {
          p = new OvernightPackage();
          p.deserialize(package_str);
          packages.add(p);
        } else {
          System.out.println("error loading packages. Exiting..");
          System.exit(1);
        }
        package_str = "";
      } else {
        package_str += line + "\n";
      }
    }
    reader.close();
}
```

### 4-9: UIService.java

### 每个包裹的条目格式如下（此处为 AdvancedPackage ）:

```
Advanced Package

John Doe

1 Main str. Boston

### 11.3

2022/12/27

--
```

注意条目之间是用两个连字符（`--`）分隔的，在条目的第一行我们可以获取包的类型。

处理完这些后，我们可以继续定义 `Package` 类：

```java
import java.time.LocalDate;

public abstract class Package {
    protected String recipient;
    protected String address;
    protected double weight;
    protected LocalDate shipmentDate;

    public Package(String _recipient, String _address, double _weight, LocalDate _shipmentDate) {
        recipient = _recipient;
        address = _address;
        weight = _weight;
        shipmentDate = _shipmentDate;
    }

    public Package() {
        recipient = "";
        address = "";
        weight = 0;
    }

    public String getRecipient() {
        return recipient;
    }

    public abstract String toString();

    public abstract String serialize();

    public abstract void deserialize(String s);

    public abstract double calculateCost();

    public abstract LocalDateTime calculateDeliveryTime();
}
```

Listing 4-11: Package.java

与之前的项目相比，我们增加了两个新的抽象方法 `serialize()` 和 `deserialize()`，它们用于处理从文本文件中写入和读取包。我们还添加了另一个方法 `toString()`，它返回包对象的字符串表示，用于控制台输出。最后，我们添加了一个获取收件人名的 getter 方法，这在以后会派用场。

现在，让我们来看 `BasePackage` 类的定义：

```java
import java.time.LocalDateTime;

public class BasePackage extends Package {
    public BasePackage(String _recipient, String _address, double _weight,
        LocalDate _shipmentDate) {
        super(_recipient, _address, _weight, _shipmentDate);
    }

    public BasePackage() {
        super();
    }

    public double calculateCost() {
        return Constants.BASE_PACKAGE_COST_FACTOR * weight;
    }

    public LocalDate calculateDeliveryTime() {
        if (weight <= Constants.BASE_PACKAGE_MAX_WEIGHT)
            return shipmentDate.plusDays(Constants.BASE_PACKAGE_DAYS);
        else
            return shipmentDate.plusDays(Constants.BASE_PACKAGE_DAYS + 1);
    }

    public String toString() {
        StringBuilder str = new StringBuilder();
        str.append("\n-Base Package-");
        str.append("\nRecipient: " + recipient);
        str.append("\naddress: " + address);
        str.append("\nWeight: " + weight);
        str.append("\nShipment date:" + shipmentDate);
        str.append("\nExpected delivery date:" + 
            calculateDeliveryTime());
        str.append("\nCost:" + calculateCost());
        str.append("\n---------------------");
        return str.toString();
    }

    public String serialize() {
        StringBuilder str = new StringBuilder();
        str.append("Base Package\n");
        str.append(recipient + "\n");
        str.append(address + "\n");
        str.append(weight + "\n");
        str.append(shipmentDate + "\n");
        str.append("-" + "\n");
        return str.toString();
    }

    public void deserialize(String s) {
      String[] lines = s.split("\\R");
      String package_type;

      recipient = lines[1];
      address = lines[2];
      weight = Double.parseDouble(lines[3]);
      shipmentDate = LocalDate.parse(lines[4]);
    }
}
```

List 4-12: BasePackage.java

在前两个新增的方法中，我们使用了 `StringBuilder` 类，它为我们提供了一个缓冲区，以便在连续调用中构建字符串。在第三个方法中，我们根据换行符分割字符串，这样每一行都会插入到字符串数组的不同位置。

`AdvancedPackage` 和 `OvernightPackage` 类的实现与 `BasePackage` 相似。为了完整性，我们在这里提供它们。

```java
import java.time.LocalDate;
public class AdvancedPackage extends Package {
```



## 代码清单 4-13：AdvancedPackage.java

```java
public class AdvancedPackage extends Package {
    public AdvancedPackage(String _recipient, String _address, double _weight,
        LocalDate _shipmentDate) {
        super(_recipient, _address, _weight, _shipmentDate);
    }

    public AdvancedPackage() {
        super();
    }

    public double calculateCost() {
        return Constants.ADVANCED_PACKAGE_COST_FACTOR *
        weight + Constants.ADVANCED_PACKAGE_COST_SUPPLY;
    }

    public LocalDate calculateDeliveryTime() {
        return shipmentDate.plusDays(Constants.ADVANCED_PACKAGE_DAYS);
    }

    public String toString() {
        StringBuilder str = new StringBuilder();
        str.append("\n-Advanced Package-");
        str.append("\nRecipient: " + recipient);
        str.append("\nAddress: " + address);
        str.append("\nWeight: " + weight);
        str.append("\nShipment date:" + shipmentDate);
        str.append("\nExpected delivery date:" + 
        calculateDeliveryTime());
        str.append("\ncost:" + calculateCost());
        str.append("\n---------------------");
        return str.toString();
    }

    public String serialize() {
        StringBuilder str = new StringBuilder();
        str.append("Advanced Package\n");
        str.append(recipient + "\n");
        str.append(address + "\n");
        str.append(weight + "\n");
        str.append(shipmentDate + "\n");
        str.append("-" + "\n");
        return str.toString();
    }

    public void deserialize(String s) {
        String[] lines = s.split("\\R");
        String package_type;

        recipient = lines[1];
        address = lines[2];
        weight = Double.parseDouble(lines[3]);
        shipmentDate = LocalDate.parse(lines[4]);
    }
}
```

## 代码清单 4-14：OvernightPackage.java

```java
import java.time.LocalDate;

public class OvernightPackage extends Package {
    public OvernightPackage(String _recipient, String _address, double _weight,
        LocalDate _shipmentDate) {
        super(_recipient, _address, _weight, _shipmentDate);
    }

    public OvernightPackage() {
        super();
    }

    public double calculateCost() {
        return Constants.ADVANCED_PACKAGE_COST_FACTOR *
        weight;
    }

    public LocalDate calculateDeliveryTime() {
        return shipmentDate.plusDays(Constants.ADVANCED_PACKAGE_DAYS);
    }

    public String toString() {
        StringBuilder str = new StringBuilder();
        str.append("\n-Overnight Package-");
        str.append("\nRecipient: " + recipient);
        str.append("\nAddress: " + address);
        str.append("\nWeight: " + weight);
        str.append("\nShipment date:" + shipmentDate);
        str.append("\nExpected delivery date:" + 
        calculateDeliveryTime());
        str.append("\ncost:" + calculateCost());
        str.append("\n---------------------");
        return str.toString();
    }

    public String serialize() {
        StringBuilder str = new StringBuilder();
        str.append("Overnight Package\n");
        str.append(recipient + "\n");
        str.append(address + "\n");
        str.append(weight + "\n");
        str.append(shipmentDate + "\n");
        str.append("-" + "\n");
        return str.toString();
    }

    public void deserialize(String s) {
        String[] lines = s.split("\\R");
        String package_type;

        recipient = lines[1];
        address = lines[2];
        weight = Double.parseDouble(lines[3]);
        shipmentDate = LocalDate.parse(lines[4]);
    }
}
```

你可以在 GitHub 上找到这个项目：

`https://github.com/htset/java_exercises/tree/master/PackageShipping/src`

## 5. 带 GUI 的快递

我们将使用 Java Swing 创建简单的 GUI 来继续之前的练习。这个 GUI 将实现以下功能：

- 展示系统中创建的所有包列表
- 提供插入新包的选项

### 解决方案

在之前的快递练习版本中，控制台 UI 类既处理与用户的交互，也处理了文件的数据存储。在这里，我们将文件处理功能封装在一个新类中，命名为 `PersistenceService`：

## 代码清单 5-1：PersistenceService.java

```java
import java.io.*;
import java.util.List;

public class PersistenceService {
    private List<Package> packages;

    public PersistenceService(List<Package> _packages) {
        packages = _packages;
    }

    public void saveToFile() throws IOException {
        BufferedWriter writer = new BufferedWriter(new FileWriter("packages.txt"));
        for (Package p : packages) {
            writer.write(p.serialize());
        }
        writer.close();
    }

    public void loadFromFile() throws IOException {
        packages.clear();
        File file = new File("packages.txt");
        if (!file.exists()) {
            file.createNewFile();
        }
        BufferedReader reader = new BufferedReader(new FileReader(file));
        String line;
        String package_str = "";
        while ((line = reader.readLine()) != null) {
            if (line.indexOf("---") == 0) {
                Package p;
                if (package_str.indexOf("Base Package") == 0) {
                    p = new BasePackage();
                    p.deserialize(package_str);
                    packages.add(p);
                } else if (package_str.indexOf("Advanced Package") == 0) {
                    p = new AdvancedPackage();
                    p.deserialize(package_str);
                    packages.add(p);
                } else if (package_str.indexOf("Overnight Package") == 0) {
                    p = new OvernightPackage();
                    p.deserialize(package_str);
                    packages.add(p);
                } else {
                    System.out.println("error loading packages. Exiting..");
                    System.exit(0);
                }
                package_str = "";
            } else {
                package_str += line + "\n";
            }
        }
    }
}
```

`PersistenceService` 类接收包列表作为输入参数，并在 `loadFromFile()` 方法中填充它。相反，它在 `saveToFile()` 方法将所有内容存储在同一个文件中。

包列表在主类（Main）中定义，其引用被传递给其他类：

## 代码清单 5-2：Main.java

```java
import java.io.IOException;
import java.util.ArrayList;

public class Main {
    public static void main(String[] args) {
        try {
            ArrayList<Package> list = new ArrayList<>();
            PersistenceService ps = new PersistenceService(list);
            ps.loadFromFile();
            PackagesTable pt = new PackagesTable(ps, list);
        } catch (IOException ioe) {
            System.out.println("IO Exception!");
            ioe.printStackTrace();
            System.exit(1);
        }
    }
}
```

接下来，我们创建 `PackagesTable` 类，它向用户展示一个包含目前为止所有包裹运输的网格：

## 代码清单 5-3：PackagesTable.java

```java
import javax.swing.*;
import javax.swing.table.AbstractTableModel;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.util.ArrayList;

public class PackagesTable extends JFrame implements ActionListener {
    PersistenceService ps;
    ArrayList<Package> list;
    JTable table;
    JScrollPane sp;
    JButton addPackageButton;
    PackageTableModel model;

    public PackagesTable(PersistenceService ps, ArrayList<Package> list) {
        this.ps = ps;
        this.list = list;
        model = new PackageTableModel(this.list);

        setTitle("Packages");
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        Container c = getContentPane();
        c.setLayout(null);

        table = new JTable(model);

        addPackageButton = new JButton("Add New Package");
        addPackageButton.setSize(200, 20);
        addPackageButton.setLocation(300, 360);
        addPackageButton.addActionListener(this);

        sp = new JScrollPane(table);
        sp.setBounds(10, 10, 760, 300);

        c.add(sp);
        c.add(addPackageButton);

        setSize(800, 500);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        PackagesForm form = new PackagesForm(this.ps, this.list);
        model.populateModel();
        ((AbstractTableModel) model).fireTableDataChanged();
    }
}
```

`PackageTable` 类继承自 Swing 的 `JFrame` 类，包含一个 `JTable` 和一个 `JButton` 对象。为了处理 `JTable` 数据，我们定义了一个表格模型（Table Model）类。该类定义在 `PackageTable` 类内部：



## PackageTableModel 类

```java
class PackageTableModel extends AbstractTableModel {
    ArrayList<Package> list;
    private String[] columnNames = {
        "Package Type",
        "Recipient",
        "Address",
        "Shipment Date",
        "Weight",
        "Expected Date",
        "Cost"
    };
    private Object[][] data;

    public PackageTableModel(ArrayList<Package> list) {
        this.list = list;
        populateModel();
    }

    void populateModel() {
        data = new Object[list.size()][7];
        int i = 0;
        for (Package p : this.list) {
            String packageType;
            if (p instanceof BasePackage)
                packageType = "Base Package";
            else if (p instanceof AdvancedPackage)
                packageType = "Advanced Package";
            else if (p instanceof OvernightPackage)
                packageType = "Overnight Package";
            else
                continue;

            Object[] rowdata = new Object[]{
                packageType,
                p.getRecipient(),
                p.getAddress(),
                p.getShipmentDate(),
                p.getWeight(),
                p.calculateDeliveryTime(),
                p.calculateCost()
            };
            data[i++] = rowdata;
        }
    }

    public int getColumnCount() {
        return columnNames.length;
    }

    public int getRowCount() {
        return data.length;
    }

    public String getColumnName(int col) {
        return columnNames[col];
    }

    public Object getValueAt(int row, int col) {
        return data[row][col];
    }
}
```

**列表 5-4：PackageTable.java**

表格模型定义了表头并遍历包裹。当点击 `JButton` 时，会显示一个表单供用户填写详情。以下是 `PackageForm` 的代码：

## PackageForm 类

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.IOException;
import java.time.LocalDateTime;
import java.util.ArrayList;

public class PackageForm extends JDialog implements ActionListener {
    PersistenceService ps;
    ArrayList<Package> list;
    JComboBox packageTypeList;
    JTextField recipientField;
    JTextField addressField;
    JTextField shipmentDateField;
    JTextField weightField;
    JButton saveButton;

    public PackageForm(PersistenceService ps, ArrayList<Package> list) {
        this.ps = ps;
        this.list = list;

        setTitle("Insert Package");
        Container c = getContentPane();
        c.setLayout(null);

        String[] packageTypes = {
            "Base Package",
            "Advanced Package",
            "Overnight Package"
        };
        packageTypeList = new JComboBox(packageTypes);
        packageTypeList.setSize(200, 20);
        packageTypeList.setLocation(10, 20);
        c.add(packageTypeList);

        JLabel recipientLabel = new JLabel("Recipient");
        recipientLabel.setBounds(10, 50, 100, 20);
        c.add(recipientLabel);
        recipientField = new JTextField();
        recipientField.setBounds(120, 50, 200, 20);
        c.add(recipientField);

        JLabel addressLabel = new JLabel("Address");
        addressLabel.setBounds(10, 80, 100, 20);
        c.add(addressLabel);
        addressField = new JTextField();
        addressField.setBounds(120, 80, 200, 20);
        c.add(addressField);

        JLabel shipmentDateLabel = new JLabel("Shipment Date");
        shipmentDateLabel.setBounds(10, 110, 100, 20);
        c.add(shipmentDateLabel);
        shipmentDateField = new JTextField();
        shipmentDateField.setBounds(120, 110, 200, 20);
        c.add(shipmentDateField);

        JLabel weightLabel = new JLabel("Weight");
        weightLabel.setBounds(10, 140, 100, 20);
        c.add(weightLabel);
        weightField = new JTextField();
        weightField.setBounds(120, 140, 200, 20);
        c.add(weightField);

        saveButton = new JButton("Save");
        saveButton.setSize(100, 20);
        saveButton.setLocation(150, 160);
        saveButton.addActionListener(this);
        c.add(saveButton);

        setSize(500, 250);
        setModal(true);
        setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        String packageType = (String) packageTypeList.getSelectedItem();
        String recipient = recipientField.getText();
        String address = addressField.getText();
        String shipmentDate = shipmentDateField.getText();
        String weight = weightField.getText();

        if (packageType.equals("Base Package")) {
            list.add(new BasePackage(recipient, address, Double.parseDouble(weight), LocalDateTime.parse(shipmentDate)));
        } else if (packageType.equals("Advanced Package")) {
            list.add(new AdvancedPackage(recipient, address, Double.parseDouble(weight), LocalDateTime.parse(shipmentDate)));
        } else if (packageType.equals("Overnight Package")) {
            list.add(new OvernightPackage(recipient, address, Double.parseDouble(weight), LocalDateTime.parse(shipmentDate)));
        }

        try {
            ps.saveToFile();
        } catch (IOException ex) {
            throw new RuntimeException(ex);
        }
        dispose();
    }
}
```

**列表 5-5：PackageForm.java**

当点击按钮时，`actionPerformed()` 方法会从文本框读取用户输入，并使用它创建一个新的 `Package` 对象并添加到包列表中。包的类型取决于包下拉列表中的选择。

最后，模态框会自动关闭，控制权返回到 `PackageTable` 类（`actionPerformed()` 方法），我们在那里使用新数据重新填充表格模型：

**列表 5-6：PackageTable.java**

```java
public void actionPerformed(ActionEvent e) {
    PackagesForm form = new PackagesForm(this.ps, this.list);
    model.populateModel();
    ((AbstractTableModel) model).fireTableDataChanged();
}
```

## Package 基类

为了完整性，我们将包含其他类，从基类 `Package` 开始：

**列表 5-7：Package.java**

```java
import java.time.LocalDate;

public abstract class Package {
    protected String recipient;
    protected String address;
    protected double weight;
    protected LocalDate shipmentDate;

    public Package(String _recipient, String _address, double _weight,
        LocalDate _shipmentDate) {
        recipient = _recipient;
        address = _address;
        weight = _weight;
        shipmentDate = _shipmentDate;
    }

    public Package() {
        recipient = "";
        address = "";
        weight = 0;
    }

    public String getRecipient() {
        return recipient;
    }

    public String getAddress() {
        return address;
    }

    public double getWeight() {
        return weight;
    }

    public LocalDate getShipmentDate() {
        return shipmentDate;
    }

    public abstract String toString();
    public abstract String serialize();
    public abstract void deserialize(String s);
    public abstract double calculateCost();
    public abstract LocalDate calculateDeliveryTime();
}
```

## BasePackage 类

**列表 5-8：BasePackage.java**

```java
import java.time.LocalDate;

public class BasePackage extends Package {
    public BasePackage(String _recipient, String _address,
        double _weight, LocalDate _shipmentDate) {
        super(_recipient, _address, _weight, _shipmentDate);
    }

    public BasePackage() {
        super();
    }

    public double calculateCost() {
        return Constants.BASE_PACKAGE_COST_FACTOR * weight;
    }

    public LocalDate calculateDeliveryTime() {
        return shipmentDate.plusDays(Constants.BASE_PACKAGE_DAYS);
    }

    public String toString() {
        StringBuilder str = new StringBuilder();
        str.append("\nBase Package--");
        str.append("\nRecipient: " + recipient);
        str.append("\nAddress: " + address);
        str.append("\nWeight: " + weight);
        str.append("\nShipment date: " + shipmentDate);
        str.append("\nExpected delivery date: " + calculateDeliveryTime());
        str.append("\nCost: " + calculateCost());
        str.append("\n---------------------");
        return str.toString();
    }

    public String serialize() {
        StringBuilder str = new StringBuilder();
        str.append("BasePackage|");
        str.append(recipient + "|");
        str.append(address + "|");
        str.append(weight + "|");
        str.append(shipmentDate);
        return str.toString();
    }

    public void deserialize(String s) {
        String[] parts = s.split("\\|");
        recipient = parts[1];
        address = parts[2];
        weight = Double.parseDouble(parts[3]);
        shipmentDate = LocalDate.parse(parts[4]);
    }
}
```

## AdvancedPackage 类

```java
import java.time.LocalDate;

public class AdvancedPackage extends Package {
    public AdvancedPackage(String _recipient, String _address,
        double _weight, LocalDate _shipmentDate) {
        super(_recipient, _address, _weight, _shipmentDate);
    }

    public AdvancedPackage() {
        super();
    }

    public double calculateCost() {
        return Constants.ADVANCED_PACKAGE_COST_FACTOR * weight + Constants.ADVANCED_PACKAGE_COST_SUPPL;
    }

    public LocalDate calculateDeliveryTime() {
        return shipmentDate.plusDays(Constants.ADVANCED_PACKAGE_DAYS);
    }

    public String toString() {
        StringBuilder str = new StringBuilder();
        str.append("\nAdvanced Package--");
        str.append("\nRecipient: " + recipient);
        str.append("\nAddress: " + address);
        str.append("\nWeight: " + weight);
        str.append("\nShipment date: " + shipmentDate);
        str.append("\nExpected delivery date: " + calculateDeliveryTime());
        str.append("\nCost: " + calculateCost());
        str.append("\n---------------------");
        return str.toString();
    }

    public String serialize() {
        StringBuilder str = new StringBuilder();
        str.append("AdvancedPackage|");
        str.append(recipient + "|");
        str.append(address + "|");
        str.append(weight + "|");
        str.append(shipmentDate);
        return str.toString();
    }

    public void deserialize(String s) {
        String[] parts = s.split("\\|");
        recipient = parts[1];
        address = parts[2];
        weight = Double.parseDouble(parts[3]);
        shipmentDate = LocalDate.parse(parts[4]);
    }
}
```



## 代码示例

```java
str.append("\nExpected delivery date:" + calculateDeliveryTime());

str.append("\nCost:" + calculateCost());

str.append("\n--------------------\n");

return str.toString();
}

public String serialize() {

  StringBuilder str = new StringBuilder();

  str.append("Advanced Package\n");

  str.append(recipient + "\n");

  str.append(address + "\n");

  str.append(weight + "\n");

  str.append(shipmentDate + "\n");

  str.append("--" + "\n");

  return str.toString();
}

public void deserialize(String s) {

  String[] lines = s.split("\\R");

  String package_type;

  recipient = lines[1];

  address = lines[2];

  weight = Double.parseDouble(lines[3]);

  shipmentDate = LocalDate.parse(lines[4]);
}
```

**列表 5-9:** `AdvancePackage.java`

```java
import java.time.LocalDate;

public class OvernightPackage extends Package {

  public OvernightPackage(String _recipient, String _address,
      double _weight,
      LocalDate _shipmentDate) {
    super(_recipient, _address, _weight, _shipmentDate);
  }

  public OvernightPackage() {
    super();
  }

  public double calculateCost() {
    return Constants.OVERNIGHT_PACKAGE_COST_FACTOR * weight;
  }

  public LocalDate calculateDeliveryTime() {
    return shipmentDate.plusDays(Constants.OVERNIGHT_PACKAGE_DAYS);
  }

  public String toString() {
    StringBuilder str = new StringBuilder();
    str.append("\n-Overnight Package--");
    str.append("\nRecipient: " + recipient);
    str.append("\nAddress: " + address);
    str.append("\nWeight: " + weight);
    str.append("\nShipment date:" + shipmentDate);
    str.append("\nExpected delivery date:" + calculateDeliveryTime());
    str.append("\nCost:" + calculateCost());
    str.append("\n--------------------");
    return str.toString();
  }

  public String serialize() {
    StringBuilder str = new StringBuilder();
    str.append("Advanced Package\n");
    str.append(recipient + "\n");
    str.append(address + "\n");
    str.append(weight + "\n");
    str.append(shipmentDate + "\n");
    str.append("--" + "\n");
    return str.toString();
  }

  public void deserialize(String s) {
    String[] lines = s.split("\\R");
    String package_type;
    recipient = lines[1];
    address = lines[2];
    weight = Double.parseDouble(lines[3]);
    shipmentDate = LocalDate.parse(lines[4]);
  }
}
```

**Listing 5-10:** `OvernightPackage.java`

```java
public class Constants {
    static final double ADVANCED_PACKAGE_COST_FACTOR = 5;
    static final int ADVANCED_PACKAGE_DAYS = 2;
    static final double ADVANCED_PACKAGE_COST_SUPPL = 100;
    static final double OVERNIGHT_PACKAGE_COST_FACTOR = 10;
    static final int OVERNIGHT_PACKAGE_DAYS = 1;
}
```

**Listing 5-11:** `Constants.java`

```java
public double calculateCost() {
    return -age + 0.05 * coverage + 10 * carAge;
}
```

```java
public String toString() {
    StringBuilder buffer = new StringBuilder();
    buffer.append("\n----Auto Insurance policy-----");
    buffer.append("\nName: " + name);
    buffer.append("\nAge: " + age);
    buffer.append("\nCoverage: " + coverage);
    buffer.append("\nCar Age: " + carAge);
    buffer.append("\nYearly cost: " + calculateCost());
    return buffer.toString();
}
```

**列表 6-3:** `AutoInsurance.java`

按照要求，我们还需要创建一个方法，接收一个保险对象（无论是人寿险还是车险）并将其保存到文本文件中。

我们可以编写两个独立的方法来执行此任务，为每种对象类型编写一个。然而，我们可以利用多态性只写一个方法。我们将该方法（静态的）放在 `Main` 类中：

```java
import java.io.FileWriter;
import java.io.IOException;
import java.io.PrintWriter;

public class Main {
    static void saveInsurance(Insurance insurance) throws IOException {
        PrintWriter output = new PrintWriter(new FileWriter("insurance.txt", true), true);
        output.println(insurance.toString());
        // 无法编译
        // output.println(insurance.getCarAge())
        if (insurance.getClass().toString().equals("class AutoInsurance"))
            output.println(">>>Car age: " + ((AutoInsurance) insurance).getCarAge());
        output.close();
    }

    public static void main(String[] args) {
        try {
            AutoInsurance i1 = new AutoInsurance("John Doe", 30, 15000, 2);
            System.out.println(i1.toString());
            LifeInsurance i2 = new LifeInsurance("John Doe", 30, 1000000);
            System.out.println(i2.toString());
            saveInsurance(i1);
            saveInsurance(i2);
        } catch (IOException ioe) {
            System.out.println("IOException");
        }
    }
}
```

**列表 6-4:** `Main.java`

该方法接收 `Insurance` 引用作为输入。通过多态，它会调用相应的 `toString()` 方法，并且每次获取不同的字符串。

多态性也有其局限性。注意，我们只能访问在基类（`Insurance`）中定义的参数和方法。因此，我们无法调用仅在 `AutoInsurance` 类中定义的 `getCarAge()` 方法。如果我们需要执行该操作，必须将引用强制转换为 `AutoInsurance` 的引用，如下所示：

```java
if (insurance.getClass().toString().equals("AutoInsurance"))
```

你可以在 GitHub 上找到此项目：
https://github.com/htset/java_oop_exercises/tree/master/Insurance/src

## 7. 预订

在本次练习中，我们将创建一个处理公寓预订（类似 AirBnB 风格）的应用程序。

我们需要管理以下信息：

**公寓（Apartments）：**
- 地址
- 容量（最大入住人数）
- 每日价格

**预订（Reservations）：**
- 预订人的姓名和姓氏
- 开始日期
- 持续时间
- 入住的人员列表。对于人员，我们需要：
  - 姓名和姓氏
  - 出生日期

我们将所有信息存储在 MySQL 数据库中。

我们还将创建一个控制台 UI，用于处理以下操作：
- 添加新预订
- 根据人的姓氏搜索预订
- 列出所有预订

为了简单起见，我们不会在 UI 中处理公寓。它们将直接通过 SQL 插入到 `Apartments` 表中。此外，我们不考虑多次预订同一公寓的情况，以保持实现易于理解。

### 建议的解决方案

我们从定义数据库表开始。本次练习我们将使用 MySQL，因为它对于初级程序员来说，具有最直观的 API。

以下是创建表的 SQL 语句：

```sql
CREATE DATABASE `test`;

CREATE TABLE `apartments` (
  `id` int NOT NULL AUTO_INCREMENT,
  `address` varchar(45) DEFAULT NULL,
  `capacity` int DEFAULT NULL,
  `price` int DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT CHARSET=utfmb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `reservations` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(45) DEFAULT NULL,
  `surname` varchar(45) DEFAULT NULL,
  `date` date DEFAULT NULL,
  `duration` int DEFAULT NULL,
  `cost` decimal(10,0) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=8 CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `persons` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(45) DEFAULT NULL,
  `surname` varchar(45) DEFAULT NULL,
  `birth_year` int DEFAULT NULL,
  `reservation_id` int DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=5 CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

```java
"\surname=" + surname +
"nbirthYear=" + birthYear;
}
```

**列表 7-4:** `Person.java`

应用程序的 `main` 方法也非常简单，因为工作被委托给了 `UIService` 和 `PersistenceService` 类处理：

```java
public static void main(String args[]) {
    PersistenceService ps = new PersistenceService();
    UIService ui = new UIService(ps);
    ui.menu();
}
```

**列表 7-5:** `Main.java`

现在，让我们来看一些有趣的内容。首先定义处理与用户交互的 `UIService` 类：

```java
import java.time.LocalDate;
import java.util.ArrayList;
import java.util.Scanner;
```

```java
public class UIService {
    PersistenceService ps;
```

```java
public UIService(PersistenceService _ps) {
    ps = _ps;
}
```

**列表 7-6:** `UIService.java`

注意在 `UIService` 类内部，我们保留了对 `PersistenceService` 对象的引用。该引用是在 `UIService` 构造函数中提供的。

`menu()` 方法包含了与用户交互的主循环：

```java
public void menu() {
    Scanner in = new Scanner(System.in);
    int option;
    do {
        System.out.println("Options: ");
        System.out.println("1) Add reservation ");
        System.out.println("2) Search reservation ");
        System.out.println("3) View all reservations ");
        System.out.println("0) Exit ");
        System.out.print("Enter your selection:");
        option = in.nextInt();
        in.nextLine();

        switch (option) {
            case 1:
                addReservation();
                break;
            case 2:
                searchReservation();
                break;
            case 3:
                listReservations();
                break;
            case 0:
                break;
            default:
                System.out.print("Please enter selection again:");
                break;
        }
    } while (option != 0);
}
```

**列表 7-7:** `UIService` 操作

### 当用户按下 1 时，调用 `addReservation()` 方法：

```java
private void addReservation() {
  Scanner in = new Scanner(System.in);
  int option;
  String name, surname, startDateStr;
  int duration, day, month, year;
```



## 代码示例：用户输入与公寓选择

```java
System.out.print("Name: ");
name = in.nextLine();

System.out.print("Surname: ");
surname = in.nextLine();

System.out.print("Start date (YYYY-MM-DD): ");
startDateStr = in.nextLine();

LocalDate date = LocalDate.parse(startDateStr);

System.out.print("Duration: ");
duration = in.nextInt();
in.nextLine();

System.out.println("Available apartments: ");
ArrayList<Apartment> apartments = ps.getApartments();

int i = 1;
```

```java
for (Apartment a : apartments) {
    System.out.println("Apartment no." + (i++) + ":");
    System.out.println(a);
}

System.out.print("Press 0 to cancel): ");
option = in.nextInt();
in.nextLine();

if (option > 0 && option <= apartments.size()) {
    Reservation res = new Reservation(0, name, surname,
        startDate, duration,
        apartments.get(option - 1).getPrice());
    addPersons(res);
    ps.insertReservation(res);
}
```

列表 7-8: `UIService.java`

用户输入所需的预订开始日期和持续时间后，系统会显示一个可用公寓列表。通常情况下，我们会搜索这些日期内的空闲公寓，但为了简单起见，我们获取数据库中的所有公寓。公寓列表是通过使用 `PersistenceService` 对象（`getAvailableApartments()` 方法）获取的。选择公寓后，用户会被提示插入所有入住该公寓的人。这是通过 `addPersons()` 方法（`UIService` 类内部的一个私有方法）完成的：

```java
private void addPersons(Reservation resv) {
    Scanner in = new Scanner(System.in);
    String name, surname, selection;
    int birthYear;

    System.out.println("Give the persons:");
    do {
        System.out.print("Name: ");
        name = in.nextLine();
        System.out.print("Surname: ");
        surname = in.nextLine();
        System.out.print("Birth Year: ");
        birthYear = in.nextInt();
        in.nextLine();

        resv.addPerson(new Person(0, name, surname, birthYear));

        System.out.print("Add another person? (y/n): ");
        selection = in.nextLine();
    } while (!selection.equals("n") && !selection.equals("N"));
}
```

列表 7-9: `UIService.java`

### `UIService` 中的两个查询方法

```java
private void searchReservation() {
    Scanner in = new Scanner(System.in);
    String surname;
    System.out.print("Enter surname (also partial): ");
    surname = in.nextLine();
    ArrayList<Reservation> reservations = ps.getReservationsBySurname(surname);

    for (Reservation r : reservations) {
        System.out.println(r);
    }
}

private void listReservations() {
    ArrayList<Reservation> reservations = ps.getAllReservations();
    for (Reservation r : reservations) {
        System.out.println(r);
    }
}
```

列表 7-10: `UIService.java`

## `PersistenceService` 类

现在我们转向 `PersistenceService` 类。这是处理数据库连接的类：

```java
import java.sql.*;
import java.util.ArrayList;

public class PersistenceService {
    private Connection connection = null;
    private PreparedStatement preparedStatement = null;
    private ResultSet resultSet = null;
}
```

列表 7-11: `PersistenceService.java`

我们将数据库功能放在这个类中。注意其他类使用这个类。在构造函数中，我们创建连接对象：

```java
public PersistenceService() {
    try {
        connection = DriverManager.getConnection("jdbc:mysql://localhost/test?user=root&password=1234");
        connection.setAutoCommit(false);
    } catch (SQLException e) {
        System.out.println("Could not connect to database.");
        System.exit(1);
    }
}
```

列表 7-12: `PersistenceService.java`

所有的数据库操作都执行在 `try-catch` 块中。注意我们禁用了自动提交。这意味着我们需要提交更改才能生效。`getAvailableApartments()` 方法获取所有公寓：

```java
public ArrayList<Apartment> getAvailableApartments() {
    ArrayList<Apartment> result = new ArrayList<>();
    try {
        preparedStatement = connection.prepareStatement("SELECT * from Apartments");
        resultSet = preparedStatement.executeQuery();
        while (resultSet.next()) {
            result.add(new Apartment(resultSet.getInt("id"),
                resultSet.getString("address"),
                resultSet.getInt("capacity"),
                resultSet.getDouble("price")));
        }
    } catch (SQLException e) {
        System.out.println("Database error. Exiting..");
        e.printStackTrace();
        close();
        System.exit(1);
    }
    return result;
}
```

`getAllReservations()` 获取数据库中的所有预订：

```java
public ArrayList<Reservation> getAllReservations() {
    ArrayList<Reservation> result = new ArrayList<>();
    try {
        preparedStatement = connection.prepareStatement("SELECT * from Reservations");
        resultSet = preparedStatement.executeQuery();
        while (resultSet.next()) {
            Reservation res = new Reservation(resultSet.getInt("id"),
                resultSet.getString("name"),
                resultSet.getString("surname"),
                resultSet.getDate("start_date").toLocalDate(),
                resultSet.getInt("duration"),
                resultSet.getDouble("cost"));
            PreparedStatement newStatement = connection
                .prepareStatement("SELECT * from Persons where reservation_id=?");
            newStatement.setInt(1, res.getId());
            ResultSet newRes = newStatement.executeQuery();
            while (newRes.next()) {
                res.addPerson(new Person(newRes.getInt("id"),
                    newRes.getString("name"),
                    newRes.getString("surname"),
                    newRes.getInt("birth_year")));
            }
            result.add(res);
            newRes.close();
            newStatement.close();
        }
    } catch (SQLException e) {
        System.out.println("Database error. Exiting..");
        e.printStackTrace();
        close();
        System.exit(1);
    }
    return result;
}
```

列表 7-13: `PersistenceService.java`

`getReservationsBySurname` 方法返回特定姓氏的预订列表：

```java
public ArrayList<Reservation> getReservationsBySurname(String surname) {
    ArrayList<Reservation> result = new ArrayList<>();
    try {
        preparedStatement = connection.prepareStatement("SELECT * from Reservations WHERE surname LIKE ?");
        preparedStatement.setString(1, "%" + surname + "%");
        ResultSet res = preparedStatement.executeQuery();
        while (res.next()) {
            result.add(new Reservation(res.getInt("id"),
                res.getString("name"),
                res.getString("surname"),
                res.getDate("start_date").toLocalDate(),
                res.getInt("duration"),
                res.getDouble("cost")));
        }
    } catch (SQLException e) {
        System.out.println("Database error. Exiting..");
        e.printStackTrace();
        System.exit(1);
    }
    return result;
}
```

列表 7-15: `PersistenceService.java`

我们还有一个方法用于在数据库中插入新的预订（以及相应的人）：

```java
public void insertReservation(Reservation res) {
    try {
        preparedStatement = connection
            .prepareStatement("insert into Reservations(name, surname, start_date, duration, cost) values(?, ?, ?, ?, ?)",
                Statement.RETURN_GENERATED_KEYS);
        preparedStatement.setString(1, res.getName());
        preparedStatement.setString(2, res.getSurname());
        preparedStatement.setDate(3, Date.valueOf(res.getStartDate()));
        preparedStatement.setInt(4, res.getDuration());
        preparedStatement.setDouble(5, res.getCost());

        preparedStatement.executeUpdate();
        int lastInsertedId = 0;
        ResultSet rs = preparedStatement.getGeneratedKeys();
        if (rs.next()) {
            lastInsertedId = rs.getInt(1);
        }

        ArrayList<Person> persons = res.getPersons();
        PreparedStatement newStatement = connection
            .prepareStatement("insert into Persons(name, surname, birth_year, reservation_id) values(?, ?, ?, ?)");
        for (Person p : persons) {
            newStatement.setString(1, p.getName());
            newStatement.setString(2, p.getSurname());
            newStatement.setInt(3, p.getBirthYear());
            newStatement.setInt(4, lastInsertedId);
            newStatement.executeUpdate();
        }

        connection.commit();
        newStatement.close();
    } catch (SQLException e) {
        System.out.println("Database error. Exiting..");
        e.printStackTrace();
        close();
        System.exit(1);
    }
}
```

列表 7-16: `PersistenceService.java` 在 `Reservations` 表中插入新行。

在 `insertReservation()` 中，我们首先在 `Reservations` 表中插入一条新行。预订的 `id` 字段是由数据库自动创建的，因为我们在创建表时已将其定义为 `AUTO_INCREMENT`。

在成功插入行后，我们获取新生成的预订 ID，因为我们需要在每一条新的人员行中使用（在 `reservation_id` 字段中）它。

我们执行了连续的插入，每个人员执行一次，并在最后提交更改。如果发生异常，我们可以回滚事务并返回起始位置。

最后，我们提供了一个 `close()` 方法，它按照以下顺序关闭 `ResultSet`、`PreparedStatement` 和 `Connection` 对象：

```java
private void close() {
    try {
        if (resultSet != null) {
            resultSet.close();
        }
        if (preparedStatement != null) {
            preparedStatement.close();
        }
        if (connection != null) {
            connection.close();
        }
    } catch (Exception e) {
        System.out.println("Error: Could not close connection");
        e.printStackTrace();
    }
}
```



列表 7-17: `PersistenceService.java`

你可以在 GitHub 上找到此项目：

https://github.com/htset/java_oop_exercises/tree/master/Reservations/src

## 8. 纳税申报

在本次练习中，我们将创建一个用于提交房产税申报的应用。我们的应用程序将支持三种物业（公寓、商店和地块），并有不同的方法来计算相应的税：

- 公寓（Apartment）：税费 = 1.3 * 面积 + 10 * 楼层 + 150
- 商店（Store）：税费 = 2.5 * 面积 + 20 * 商业指数 + 100
- 地块（Plot）：税费 = 0.3 * 面积 + 100 * (是否耕种 + 是否在市区)

税费取决于以下参数：

- 物业的面积
- 公寓的楼层
- 商店的商业指数（1 到 5 之间）
- 地块是否耕种
- 地块是否位于市区范围内

我们将创建一个接口，为用户提供以下选项：

- 创建新申报并根据属性计算结果税
- 删除现有的申报
- 搜索申报

此外，应用程序应该提供有关申报的统计信息：

- 所有申报的总税
- 产生的最高税

我们将创建一个持久化无关的应用。也就是说，我们将申报存储在文件中或数据库中。

### 解决方案

从 `Property` 基类开始：

```java
import com.fasterxml.jackson.annotation.JsonIgnoreProperties;
import com.fasterxml.jackson.annotation.JsonSubTypes;
import com.fasterxml.jackson.annotation.JsonTypeInfo;

@JsonIgnoreProperties(ignoreUnknown = true)
@JsonTypeInfo(use = JsonTypeInfo.Id.NAME, property = "type")
@JsonSubTypes({
  @JsonSubTypes.Type(value = Apartment.class, name = "Apartment"),
  @JsonSubTypes.Type(value = Store.class, name = "Store"),
  @JsonSubTypes.Type(value = Plot.class, name = "Plot")
})
public abstract class Property {
    protected int id;
    protected int surface;
    protected Address address;

    public Property(int id, int surface, Address address) {
        this.id = id;
        this.surface = surface;
        this.address = address;
    }

    public Property() {
    }

    public abstract double calculateTax();

    public int getId() {
        return id;
    }

    public void setId(int id) {
        this.id = id;
    }

    public int getSurface() {
        return surface;
    }

    public void setSurface(int surface) {
        this.surface = surface;
    }

    public Address getAddress() {
        return address;
    }

    public void setAddress(Address address) {
        this.address = address;
    }
}
```

列表 8-1: `Property.java`

注意 `Property` 定义了一个抽象方法 `calculateTax()`。这意味着它不能被实例化。派生类必须实现该方法。`Property` 类包含了所有物业类型通用的 `surface` 参数。它还包含一个定义的 `Address` 对象：

```java
class Address {
    private String street;
    private String number;
    private String zip;
    private String city;

    public Address(String street, String number, String zip, String city) {
        this.street = street;
        this.number = number;
        this.zip = zip;
        this.city = city;
    }

    public Address() {
    }

    public String getStreet() {
        return street;
    }

    public void setStreet(String street) {
        this.street = street;
    }

    public String getNumber() {
        return number;
    }

    public void setNumber(String number) {
        this.number = number;
    }

    public String getZip() {
        return zip;
    }

    public void setZip(String zip) {
        this.zip = zip;
    }

    public String getCity() {
        return city;
    }

    public void setCity(String city) {
        this.city = city;
    }

    @Override
    public String toString() {
        return "Address{" +
            "street='" + street + '\'' +
            ", number='" + number + '\'' +
            ", zip='" + zip + '\'' +
            ", city='" + city + '\'' +
            '}';
    }
}
```

列表 8-2: `Address.java`

接下来，我们添加 `Apartment` 类：

```java
public class Apartment extends Property {
    private int floor;

    public Apartment(int id, int surface, Address address, int floor) {
        super(id, surface, address);
        this.floor = floor;
    }

    public Apartment() {
        super();
    }

    @Override
    public String toString() {
        return "Apartment{" +
            "floor=" + floor +
            ", id=" + id +
            ", surface=" + surface +
            ", address=" + address +
            '}';
    }

    public double calculateTax() {
        return (1.3 * surface + 10 * floor + 150);
    }

    public int getFloor() {
        return floor;
    }

    public void setFloor(int floor) {
        this.floor = floor;
    }
}
```

列表 8-3: `Apartment.java`

现在，我们添加 `Store` 类。该类增加了 `commerciality` 参数，用于衡量该区域对商业的盈利程度：

```java
public class Store extends Property {
    private int commerciality;

    public Store(int id, int surface, Address address, int commerciality) {
        super(id, surface, address);
        this.commerciality = commerciality;
    }

    public Store() {
        super();
    }

    @Override
    public String toString() {
        return "Store{" +
            "commerciality=" + commerciality +
            ", id=" + id +
            ", surface=" + surface +
            ", address=" + address +
            '}';
    }

    public double calculateTax() {
        return (2.5 * surface + 20 * commerciality + 100);
    }

    public int getCommerciality() {
        return commerciality;
    }

    public void setCommerciality(int commerciality) {
        this.commerciality = commerciality;
    }
}
```

列表 8-4: `Store.java`

继承自 `Property` 的第三类是 `Plot`。该类模拟了可以耕的土地，或者位于城市内部（这使得它们更有利润）：

```java
public class Plot extends Property {
    private boolean withinCityLimits;
    private boolean cultivated;

    public Plot(int id, int surface, Address address, boolean withinCityLimits, boolean cultivated) {
        super(id, surface, address);
        this.withinCityLimits = withinCityLimits;
        this.cultivated = cultivated;
    }

    public Plot() {
        super();
    }

    @Override
    public String toString() {
        return "Plot(" +
            "withinCityLimits=" + withinCityLimits +
            ", cultivated=" + cultivated +
            ", id=" + id +
            ", surface=" + surface +
            ", address=" + address +
            ")";
    }

    public double calculateTax() {
        return (0.3 * surface + 100 * (cultivated ? 1 : 0)
            + 200 * (withinCityLimits ? 1 : 0));
    }

    public boolean isWithinCityLimits() {
        return withinCityLimits;
    }

    public void setWithinCityLimits(boolean withinCityLimits) {
        this.withinCityLimits = withinCityLimits;
    }

    public boolean isCultivated() {
        return cultivated;
    }

    public void setCultivated(boolean cultivated) {
        this.cultivated = cultivated;
    }
}
```

列表 8-5: `Plot.java`

现在我们已经定义了核心类，让我们转向周围的服务。`main()` 方法非常简单：

```java
public class Main {
    public static void main(String args[]) {
        PersistenceService ps = new DBService();
        // PersistenceService ps = new FileService("td.json")
        StatisticsService ss = new StatisticsService();
        UIService ui = new UIService(ps, ss);
        ui.menu();
    }
}
```

列表 8-6: `Main.java`

我们在这里做的重要事情是为以下每个类都创建一个对象：

- `UIService`：与用户交互（基于控制台）
- `StatisticsService`：提供统计数据
- `PersistenceService`：数据存储

`PersistenceService` 是一个接口，`UIService` 应该使用它来处理从数据库或文件中保存、删除和搜索数据：

```java
import java.util.ArrayList;

public interface PersistenceService {
    void insertTaxDeclaration(TaxDeclaration td);
    void removeTaxDeclaration(TaxDeclaration td);
    ArrayList<TaxDeclaration> getTaxDeclarations(String vat, int year);
}
```

列表 8-7: `PersistenceService.java`

该接口定义了三个方法，用于插入、删除和搜索数据。`UIService` 将使用这三个方法与数据存储交互。`UIService` 与底层存储是分离的；存储可以是数据库或文件（或其他内容）。它取决于我们决定在 `UIService` 构造函数中传递什么种对象（`DBService` 或 `FileService`）。上面的代码片段是我们考虑到使用 `DBService` 对象设计的，让我们先看看 `UIService` 如何工作：

```java
import java.util.ArrayList;
import java.util.Scanner;

public class UIService {
    private PersistenceService ps;
    private StatisticsService ss;

    public UIService(PersistenceService ps, StatisticsService ss) {
        this.ps = ps;
        this.ss = ss;
    }
    ...
}
```



## 列表 8-8: UIService.java

`UIService` 类只有两个公共方法：构造函数和 `menu()` 方法：

```java
public void menu() {
    int sel;
    Scanner in = new Scanner(System.in);
    TaxDeclaration td;
    do {
        System.out.println("Options: ");
        System.out.println("--Transactions--");
        System.out.println("1: Add new Tax Declaration");
        System.out.println("2: Delete Tax Declaration: ");
        System.out.println("3: Find Tax Declaration: ");
        System.out.println("--Statistics--");
        System.out.println("11: Get total tax");
        System.out.println("12: Get Tax Declaration with highest tax");
        System.out.println("0: exit");
        System.out.print("Your choice: ");
        sel = in.nextInt();
        in.nextLine();
        switch (sel) {
            case 1:
                create();
                break;
            case 2:
                remove();
                break;
            case 3:
                search();
                break;
            case 11:
                System.out.println("Total Tax is: " + ss.getTotalTax());
                break;
            case 12:
                td = ss.getHighestDeclaration();
                System.out.println("Highest Tax Declaration is: " + td);
                break;
            default:
                break;
        }
    } while (sel != 0);
}
```

## 列表 8-9: UIService.java

注意我们在构造函数中存储对 `PersistenceService` 和 `StatisticsService` 对象的引用。此外，注意 `menu()` 方法中的循环。

接下来，是 `UIService` 类中的 `create()`、`remove()` 和 `search()` 方法：

```java
private void create() {
    Scanner in = new Scanner(System.in);
    String sel = "y";
    TaxDeclaration tax = enterDetails();
    System.out.println("Now enter properties:");
    while (sel.equals("y")) {
        Property p = enterProperty();
        if (p != null) {
            ps.insertTaxDeclaration(tax);
            System.out.println("Property added");
        } else {
            System.out.println("No property added");
        }
        System.out.println("Would you like to add another? (y/n)");
        sel = in.nextLine();
    }
    System.out.println("Tax created!");
}

private void remove() {
    Scanner in = new Scanner(System.in);
    String search_vat;
    int submissionYear;
    System.out.print("Enter VAT number for search: ");
    search_vat = in.nextLine();
    System.out.print("Enter year: ");
    submissionYear = in.nextInt();
    ArrayList<TaxDeclaration> td = ps.getTaxDeclarations(search_vat, submissionYear);
    if (td.size() > 0) {
        System.out.println("Found Tax Declaration:");
        for (TaxDeclaration d : td) {
            System.out.println(d);
        }
        System.out.println("Delete Tax Declaration? (y/n) ");
        sel = in.nextLine();
        if (sel.equals("y")) {
            ps.removeTaxDeclaration(td.get(0));
            System.out.println("Tax deleted");
        } else {
            System.out.println("Tax not deleted");
        }
    } else {
        System.out.println("Tax not found");
    }
}

private TaxDeclaration enterDetails() {
    Scanner in = new Scanner(System.in);
    String name, surname, tel;
    int year;
    System.out.print("Name: ");
    name = in.nextLine();
    System.out.print("Surname: ");
    surname = in.nextLine();
    System.out.print("VAT number: ");
    vat = in.nextLine();
    System.out.print("Telephone: ");
    tel = in.nextLine();
    System.out.print("Fiscal Year: ");
    year = in.nextInt();
    return new TaxDeclaration(name, surname, vat, tel, year);
}

private Property enterProperty() {
    Scanner in = new Scanner(System.in);
    String sel, inside, cultivated;
    Address address;
    int surface, floor, commerciality;
    System.out.println("Type of property? (1: Plot, 2: Store) ");
    sel = in.nextLine();
    if (sel.equals("1")) {
        System.out.print("Inside city limits? (y/n) ");
        inside = in.nextLine();
        System.out.print("Cultivated? (y/n) ");
        cultivated = in.nextLine();
        address = enterAddress();
        return new Plot(0, 0, address, inside.equals("y"), cultivated.equals("y"));
    } else if (sel.equals("2")) {
        System.out.print("Surface area: ");
        surface = in.nextInt();
        System.out.print("Floor: ");
        floor = in.nextInt();
        System.out.print("Commerciality: ");
        commerciality = in.nextInt();
        address = enterAddress();
        return new Store(0, surface, floor, commerciality, address);
    }
    return null;
}

private Address enterAddress() {
    Scanner in = new Scanner(System.in);
    String street, number, zip, city;
    System.out.print("Street: ");
    street = in.nextLine();
    System.out.print("\nNumber: ");
    number = in.nextLine();
    System.out.print("\nZip code: ");
    zip = in.nextLine();
    System.out.println("\nCity: ");
    city = in.nextLine();
    return new Address(street, number, zip, city);
}
```

```java
System.out.print("Select 1 for Apartment, 2 for Store, 3 for Plot, any other to abort: ");
sel = in.nextLine();
```

```java
switch (sel) {
    case "1":
        address = enterAddress();
        System.out.print("Surface: ");
        surface = in.nextInt();
        in.nextLine();
        System.out.println("Floor: ");
        floor = in.nextInt();
        in.nextLine();
        return new Apartment(0, surface, address, floor);
    case "2":
        address = enterAddress();
        System.out.print("Surface: ");
        surface = in.nextInt();
        in.nextLine();
        System.out.print("Commerciality: ");
        commerciality = in.nextInt();
        in.nextLine();
        return new Store(0, surface, address, commerciality);
    case "3":
        address = enterAddress();
        System.out.print("Surface: ");
        surface = in.nextInt();
        in.nextLine();
        System.out.print("Inside town? ");
        inside = in.nextLine();
        System.out.print("Cultivated? ");
        cultivated = in.nextLine();
        return new Plot(0, surface, address,
        (inside.equals("y")) ? true : false,
        (cultivated.equals("y")) ? true : false);
    default:
        return null;
}
}
```

## 列表 8-11: UIService.java

### StatisticsService 类提供了检索有关税收申报统计信息的接口：

```java
import java.util.ArrayList;

public class StatisticsService {
    PersistenceService ps;

    public StatisticsService(PersistenceService ps) {
        this.ps = ps;
    }

    public double getTotalTax() {
        double totalTax = 0;
        for (TaxDeclaration td : ps.getTaxDeclarations("", 0)) {
            totalTax += td.calculateTax();
        }
        return totalTax;
    }

    public TaxDeclaration getHighestDeclaration() {
        ArrayList<TaxDeclaration> declarations = ps.getTaxDeclarations("", 0);
        if (declarations.size() > 0) {
            TaxDeclaration max = declarations.get(0);
            double highestTax = 0;
            for (TaxDeclaration td : declarations) {
                if (td.calculateTax() > highestTax) {
                    max = td;
                    highestTax = td.calculateTax();
                }
            }
            return max;
        } else
            return null;
    }
}
```

## 列表 8-12: StatisticsService.java

注意 `StatisticsService` 类如何使用实现 `PersistenceService` 定义接口的对象的引用。

现在，让我们看看如何使用 MySQL 数据库来存储税收申报的数据。首先，我们必须在 Tax 数据库中创建表：

```sql
CREATE TABLE `addresses` (
`id` int NOT NULL AUTO_INCREMENT,
`street` varchar(45) DEFAULT NULL,
`number` varchar(45) DEFAULT NULL,
`zip` varchar(45) DEFAULT NULL,
`city` varchar(45) DEFAULT NULL,
`propertyId` int DEFAULT NULL,
PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=10
CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

```sql
CREATE TABLE `apartments` (
`id` int NOT NULL AUTO_INCREMENT,
`surface` int DEFAULT NULL,
`floor` int DEFAULT NULL,
```



## 数据库表结构

```sql
CREATE TABLE `plots` (
  `id` int NOT NULL AUTO_INCREMENT,
  `surface` int DEFAULT NULL,
  `cultivated` int DEFAULT NULL,
  `withinCityLimits` int DEFAULT NULL,
  `taxDeclarationId` int DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=3 DEFAULT
CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `stores` (
  `id` int NOT NULL AUTO_INCREMENT,
  `surface` int DEFAULT NULL,
  `commerciality` int DEFAULT NULL,
  `taxDeclarationId` int DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=4 DEFAULT
CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;

CREATE TABLE `taxdeclarations` (
  `id` int NOT NULL AUTO_INCREMENT,
  `name` varchar(45) DEFAULT NULL,
  `surname` varchar(45) DEFAULT NULL,
  `vat` varchar(45) DEFAULT NULL,
  `phone` varchar(45) DEFAULT NULL,
  `submissionYear` int DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=14 DEFAULT
CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
```

Listing 8-13: SQL 代码

## DBService 类实现

接下来，我们定义实现 `PersistenceService` 的 `DBService` 类。

```java
import java.sql.*;
import java.util.ArrayList;

public class DBService implements PersistenceService {
    private Connection connection;
    private PreparedStatement preparedStatement;
    private ResultSet resultSet = null;

    public DBService() {
        try {
            connection = DriverManager.getConnection("jdbc:mysql://localhost/tax?user=password");
            connection.setAutoCommit(false);
        } catch (SQLException e) {
            System.out.println("Could not connect to database");
            System.exit(0);
        }
    }
}
```

Listing 8-14: DBService.java

注意 `StatisticsService` 类如何使用实现 `PersistenceService` 定义接口的对象引用。

现在，让我们看看如何使用 MySQL 数据库来存储税收申报的数据。`getTaxDeclarations()` 方法在数据库中搜索：

```java
public ArrayList<TaxDeclaration> getTaxDeclarations(String vat, int year) {
    ArrayList<TaxDeclaration> result = new ArrayList<>();
    try {
        preparedStatement = connection.prepareStatement("SELECT * from taxdeclarations WHERE vat = ? AND submissionYear = ?");
        preparedStatement.setString(1, vat);
        preparedStatement.setInt(2, year);
        resultSet = preparedStatement.executeQuery();
        while (resultSet.next()) {
            TaxDeclaration td = new TaxDeclaration(
                resultSet.getInt("id"),
                resultSet.getString("name"),
                resultSet.getString("surname"),
                resultSet.getString("vat"),
                resultSet.getString("phone"),
                resultSet.getInt("submissionYear")
            );
            result.add(td);
        }
    } catch (SQLException e) {
        System.out.println("error");
    }
    return result;
}
```

... (后续代码因输入文本截断未翻译)

```java
newRes.getInt("id"),
newRes.getInt("surface"),
addr,
newRes.getInt("commerciality");
```

```java
td.addSprite(st);
} else {
    System.out.println("error");
    System.exit(0);
}
```

```java
newStatement = connection
    .prepareStatement("SELECT * from Plots where tDeclarationId = ?");
```

```java
newStatement.setInt(1, res.getInt("id"));
newRes = newStatement.executeQuery();
```

```java
while (newRes.next()) {
    PreparedStatement newStatement2 = connection
        .prepareStatement("SELECT * from Addresses where propertyId = ?");
```

```java
newStatement2.setInt(1, newRes.getInt("id"));
ResultSet newRes2 = newStatement2.executeQuery();
```

```java
if (newRes2.next()) {
    Address addr = new Address(
        newRes2.getString("street"),
        newRes2.getString("number"),
        newRes2.getString("zip"),
        newRes2.getString("city"));
```

```java
Plot pl = new Plot(
    newRes.getInt("id"),
```

```java
newRes.getInt("surface"),
addr,
newRes.getBoolean("cultivated"),
newRes.getBoolean("withinCityLimits");
td.addProperty(pl);
} else {
    System.out.println("error");
    System.exit(0);
}
}
result.add(td);
} catch (SQLException e) {
    System.out.println("Database error. Exiting.");
    e.printStackTrace();
    close();
    System.exit(0);
}
return result;
}
```

Listing 8-15: DBService.java

### 方法 `insertTaxDeclaration()` 在数据库中插入一条新声明

```java
public void insertTaxDeclaration(TaxDeclaration td) {
    try {
        preparedStatement = connection
            .prepareStatement("insert into TaxDeclarations(name, surname, vat, phone, submissionYear) values(?, ?, ?, ?, ?)",
            Statement.RETURN_GENERATED_KEYS);

        preparedStatement.setString(1, td.getName());
        preparedStatement.setString(2, td.getSurname());
        preparedStatement.setString(3, td.getVat());
        preparedStatement.setString(4, td.getPhone());
        preparedStatement.setInt(5, td.getSubmissionYear());

        preparedStatement.executeUpdate();

        int lastInsertedId = 0;
        ResultSet rs = preparedStatement.getGeneratedKeys();
        if (rs.next()) {
            lastInsertedId = rs.getInt(1);
        }

        ArrayList<Property> properties = td.getProperties();
        for (Property p : properties) {
            if (p instanceof Apartment) {
                Apartment temp = (Apartment) p;
                PreparedStatement newStatement = connection
                    .prepareStatement("insert into Apartments(surface, floor, taxDeclarationId) values(?, ?, ?)",
                    Statement.RETURN_GENERATED_KEYS);

                newStatement.setInt(1, temp.getSurface());
                newStatement.setInt(2, temp.getFloor());
                newStatement.setInt(3, lastInsertedId);
                newStatement.executeUpdate();

                int lastInsertPropertyId = 0;
                ResultSet rs1 = newStatement.getGeneratedKeys();
                if (rs1.next()) {
                    lastInsertPropertyId = rs1.getInt(1);
                }

                PreparedStatement newStatement1 = connection
                    .prepareStatement("insert into Addresses(street, number, zip, city, propertyId) values(?, ?, ?, ?)");

                newStatement1.setString(1, temp.getAddress().getStreet());
                newStatement1.setString(2, temp.getAddress().getNumber());
                newStatement1.setString(3, temp.getAddress().getZip());
                newStatement1.setString(4, temp.getAddress().getCity());
                newStatement1.setInt(5, lastInsertPropertyId);
                newStatement1.executeUpdate();
            } else if (p instanceof Store) {
                Store temp = (Store) p;
                PreparedStatement newStatement = connection
                    .prepareStatement("insert into Stores(surface, commerciality, taxDeclarationId) values(?, ?, ?)",
                    Statement.RETURN_GENERATED_KEYS);

                newStatement.setInt(1, temp.getSurface());
                newStatement.setInt(2, temp.getCommerciality());
                newStatement.setInt(3, lastInsertedId);
                newStatement.executeUpdate();

                int lastInsertPropertyId = 0;
                ResultSet rs1 = newStatement.getGeneratedKeys();
                if (rs1.next()) {
                    lastInsertPropertyId = rs1.getInt(1);
                }

                PreparedStatement newStatement1 = connection
                    .prepareStatement("insert into Addresses(street, number, zip, city, propertyId) values(?, ?, ?, ?)");

                newStatement1.setString(1, temp.getAddress().getStreet());
                newStatement1.setString(2, temp.getAddress().getNumber());
                newStatement1.setString(3, temp.getAddress().getZip());
                newStatement1.setString(4, temp.getAddress().getCity());
                newStatement1.setInt(5, lastInsertPropertyId);
                newStatement1.executeUpdate();
            }
            if (p instanceof Plot) {
                Plot temp = (Plot) p;
                PreparedStatement newStatement = connection
                    .prepareStatement("insert into Plots(surface, cultivated, withinCityLimits, taxDeclarationId) values(?, ?, ?, ?)",
                    Statement.RETURN_GENERATED_KEYS);

                newStatement.setInt(1, temp.getSurface());
                newStatement.setInt(2, temp.isCultivated() ? 1 : 0);
                newStatement.setInt(3, temp.isWithinCityLimits() ? 1 : 0);
                newStatement.setInt(4, lastInsertedId);
                newStatement.executeUpdate();

                int lastInsertPropertyId = 0;
                ResultSet rs = newStatement.getGeneratedKeys();
                if (rs.next()) {
                    lastInsertPropertyId = rs.getInt(1);
                }

                PreparedStatement newStatement1 = connection
                    .prepareStatement("insert into Addresses(street, number, zip, city, propertyId) values(?, ?, ?, ?)");
            }
        }
    } catch (SQLException e) {
        e.printStackTrace();
    }
}
```



```java
newStatement1.setString(1, temp.getAddress().getStreet());
newStatement1.setString(2, temp.getAddress().getZip());
newStatement1.setString(3, temp.getAddress().getZip());
newStatement1.setString(4, temp.getAddress().getCity());
newStatement1.setInt(5, lastInsertPropertyId);
newStatement1.executeUpdate();
```

Listing 8-16: DBService.java

### 方法 `removeTaxDeclaration()` 从数据库中删除一条声明（以及与之关联的属性和地址）

```java
public void removeTaxDeclaration(TaxDeclaration td) {
    try {
        preparedStatement = connection
            .prepareStatement("delete from TaxDeclarations where id = ?");

        preparedStatement.setInt(1, td.getId());
        preparedStatement.executeUpdate();

        preparedStatement = connection
            .prepareStatement("delete from Apartments where taxDeclarationId = ?");

        preparedStatement.setInt(1, td.getId());
        preparedStatement.executeUpdate();

        preparedStatement = connection
            .prepareStatement("delete from Stores where taxDeclarationId = ?");

        preparedStatement.setInt(1, td.getId());
        preparedStatement.executeUpdate();

        preparedStatement = connection
            .prepareStatement("delete from Plots where taxDeclarationId = ?");

        preparedStatement.setInt(1, td.getId());
        preparedStatement.executeUpdate();

        preparedStatement = connection
            .prepareStatement("delete from Addresses where propertyId IN (select id from Apartments where taxDeclarationId = ?) or select id from Stores where taxDeclarationId = ? or select id from Plots where taxDeclarationId = ?)");

        preparedStatement.setInt(1, td.getId());
        preparedStatement.setInt(2, td.getId());
        preparedStatement.setInt(3, td.getId());
        preparedStatement.executeUpdate();

        connection.commit();
    } catch (SQLException e) {
        try {
            connection.rollback();
        } catch (SQLException se) {
            System.out.println("Database error. Exiting.");
            e.printStackTrace();
            System.exit(0);
        }
        System.out.println("Database error. Exiting.");
        e.printStackTrace();
        close();
        System.exit(0);
    }
}
```

Listing 8-17: DBService.java

### 接下来，我们定义 `FileService` 类，用于将数据存储在文本文件中

```java
import com.fasterxmlxml.jackson.core.type.Reference;
import com.fasterxmlxml.jackson.core.util.DefaultPrettyPrinter;
import com.fasterxmlxml.jackson.databind.ObjectMapper;
import com.fasterxmlxml.jackson.databind.ObjectReader;
import com.fasterxmlxml.jackson.databind.ObjectWriter;
import java.io.*;
import java.nio.file.Paths;
import java.util.ArrayList;

public class FileService implements PersistenceService {
    ArrayList<TaxDeclaration> declarations;
    String filename;

    public FileService(String filename) {
        this.filename = filename;
        this.declarations = new ArrayList<>();
        loadFromFile();
    }
    ...
}
```

Listing 8-18: FileService.java

注意，在 `FileService` 类的构造函数中，我们打开了一个文本文件并加载了其中包含的所有数据。

`loadFromFile()` 方法是类中的私有方法，它将数据从文本文件加载到 `TaxDeclaration` 对象列表中：

```java
private void loadFromFile() {
    try {
        File file = new File(filename);
        if (!file.exists()) {
            file.createNewFile();
        }

        if (file.length() > 0) {
            ObjectMapper objectMapper = new ObjectMapper();
            ObjectReader reader = objectMapper
                .readerFor(new TypeReference<ArrayList<TaxDeclaration>>() {
            });
            declarations = reader.readValue(Paths.get(filename).toFile());
        } else {
            declarations = new ArrayList<>();
        }
    } catch (IOException e) {
        System.out.println("Problem reading from file. Exiting...");
        e.printStackTrace();
        System.exit(0);
    }
}
```

Listing 8-19: FileService.java

在 `FileService` 中，我们使用 Jackson 库以 JSON 格式存储数据。Jackson 让我们能够通过一个简单的方法调用将整个 `ArrayList<Object>` 转换为 JSON 格式。注意 Jackson 的 `ObjectMapper` 对象如何为我们提供 `StreamReader`，它可以一次将 JSON 数组解析为 `ArrayList<TaxDeclaration>` 对象（通过 `readValue()`）。

Jackson 同样允许我们将 `ArrayList<TaxDeclaration>` 对象转换为 JSON 数组。我们在 `saveToFile()` 中使用了它：

```java
private void saveToFile() {
    ObjectMapper mapper = new ObjectMapper();
    ObjectWriter writer = mapper.writer(new DefaultPrettyPrinter());
    try {
        writer.writeValue(new File(filename), declarations);
    } catch (IOException e) {
        System.out.println("Problem writing to file. Exiting...");
        e.printStackTrace();
        System.exit(0);
    }
}
```

Listing 8-20: FileService.java

当数据发生变化时，例如当我们创建一个新声明或删除现有的声明时，我们将所有的 `TaxDeclaration` 对象保存到文件中（我们将覆盖文件中现有的数据）。正如我们在之前的练习中指出的，无法在文本文件的中间插入或删除条目，因此我们必须从头创建一个新文件。

虽然 Jackson 可以轻松解析对象以及简单的对象列表，但在使用多态对象时，它需要我们的帮助。例如，当从 JSON 字符串读取属性对象时，Jackson 无法知道它是一个 `Apartment` 对象还是 `Plot` 对象。为了实现这一功能，我们在 `Property` 基类中添加了注解，这些注解会在 Jackson 解析和写入期间被使用：

```java
import com.fasterxml.xml.jackson.annotation.JsonIgnoreProperties;
import com.fasterxml.xml.jackson.annotation.JsonSubTypes;
import com.fasterxml.xml.jackson.annotation.JsonTypeInfo;

@JsonIgnoreProperties(ignoreUnknown = true)
@JsonTypeInfo(use = JsonTypeInfo.Id.NAME, include = JsonTypeInfo.As.PROPERTY)
@JsonSubTypes({
    @JsonSubTypes.Type(value = Apartment.class, name = "Apartment"),
    @JsonSubTypes.Type(value = Store.class, name = "Store"),
    @JsonSubTypes.Type(value = Plot.class, name = "Plot")
})
public abstract class Property {
```

Listing 8-21: Property.java

通过使用这些注解，我们指示 Jackson 在生成的 JSON 字符串的 `Property` 对象中添加实际的类名：

```json
{
  "type": "Apartment",
  "id": 0,
  "surface": 33,
  "address": {
    "street": "Main str.",
    "number": "23",
    "zip": "2344432",
    "city": "Boston"
  },
  "floor": 4
}
```

Listing 8-22: JSON text

当 JSON 字符串被 Jackson 解析时，`@type` 属性被用于确定这个对象的类型。

要在我们的项目中使用 Jackson，我们必须在项目中包含以下三个 JAR 包：

- `jackson-core`
- `jackson-annotations`
- `jackson-databind`

让我们看看这里实现的 `PersistenceService` 接口。首先是 `getTaxDeclarations()` 方法：

```java
public ArrayList<TaxDeclaration> getTaxDeclarations(String vat, int submissionYear) {
    if (vat.trim().equals("") && submissionYear == 0)
        return declarations;

    ArrayList<TaxDeclaration> ret = new ArrayList<>();
    for (TaxDeclaration td : declarations) {
        if (!vat.equals("")) {
            if (submissionYear != 0) {
                if (td.getVat().equals(vat) && td.getSubmissionYear() == submissionYear)
                    ret.add(td);
            } else {
                if (td.getVat().equals(vat))
                    ret.add(td);
            }
        } else {
            if (submissionYear != 0) {
                if (td.getSubmissionYear() == submissionYear)
                    ret.add(td);
            }
        }
    }
    return ret;
}
```

Listing 8-23: FileService.java

接下来是 `insertDeclaration()` 方法：

```java
public void insertDeclaration(TaxDeclaration td) {
    declarations.add(td);
    saveToFile();
}
```

Listing 8-24: FileService.java

最后是 `removeDeclaration()` 方法：

```java
public void removeDeclaration(TaxDeclaration declaration) {
    for (TaxDeclaration td : declarations) {
        if (td.equals(declaration)) {
            declarations.remove(td);
            break;
        }
    }
}
```

Listing 8-25: FileService.java

你可以在 GitHub 上找到此项目：https://github.com/htset/java_exercises/tree/master/TaxDeclaration

## 9. Pacman 游戏

我们将创建一个简单的 Pacman 游戏。

Pacman 和 Ghost 具有相似的特征：迷宫的位置。此外，它们都需要访问迷宫以知道它们位于哪里。

通过这种方式，我们定义了一个基类 `Entity`：

```java
public abstract class Entity {
    public int x;
    public int y;
    public Direction direction;
    public EntityType type;
    public Game game;

    void move(int newX, int newY) {
        game.map[newX][newY].entity = game;
        game.map[x][y].entity = null;
        x = newX;
        y = newY;
    }

    public abstract void play();
}
```

Listing 9-1: Entity.java

现在，让我们看看迷宫是如何组织的。首先我们展示一些工具类和枚举。迷宫由 `Block` 对象组成：

```java
public class Block {
    public BlockType type;
    public Entity entity;
}
```

Listing 9-2: Block.java

每个 `Block` 有特定的 `BlockType`：

- 墙
- 带有点的空间
- 空格

实体可以移动到空间，无论是空的还是带有点的。当实体移动到某个区块时，该区块内部的实体引用将指向该实体对象。

```java
public enum BlockType {
    Wall, Point, Empty
}
```

Listing 9-3: BlockType.java

每个 `Entity` 有特定的 `EntityType`：

```java
public enum EntityType {
    Pacman, Ghost
}
```

Listing 9-4: EntityType.java

每个 `Entity` 可以向特定的 `Direction` 移动：



```java
public enum Direction {
    Up, Right, Down, Left
}
```

Listing 9-5: Direction.java

我们还定义了一个 `Pair` 类，它对于处理迷宫位置非常有用。`Pair` 类的实现如下。正如我们之后看到的，我们还需要自己实现 `equals()` 方法：

```java
import java.util.Objects;
public class Pair {
    public int x;
    public int y;
    public Pair(int x, int y) {
        this.x = x;
        this.y = y;
    }
    public Pair() {
        this.x = 0;
        this.y = 0;
    }
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Pair pair = (Pair) o;
        return x == pair.x && y == pair.y;
    }
    @Override
    public int hashCode() {
        return Objects.hash(x, y);
    }
}
```

Listing 9-6: Pair.java

现在，让我们来看看程序的核心，`Game` 类：

```java
import java.awt.event.KeyEvent;

public class Game {
    public Block map[];
    public int sizeX = 32;
    public int sizeY = 28;
    public boolean isActive = true;
    public Pair pacmanLocation;
    public int pointsLeft;
    public Entity[] player;
}
```

...

### 列表 9-7: Game.java

在构造 `Game` 对象期间，我们解析了一个字符串数组，它组成了迷宫的文本表示。我们还跟踪游戏中的剩余分数（变量 `pointsLeft`）。最后，我们创建了游戏实体并将它们放置在迷宫的初始位置：

```java
public Game() {
    map = new Block[32][28];
    player = new Entity[4];
    pointsLeft = 0;
    for (int i = 0; i < 32; i++) {
        String line = Chart.chart[i];
        for (int j = 0; j < 28; j++) {
            map[i][j] = new Block();
            map[i][j].entity = null;
            if (line.charAt(j) == '.') {
                map[i][j].type = BlockType.Point;
                pointsLeft++;
            } else if (line.charAt(j) == '*') {
                map[i][j].type = BlockType.Wall;
            } else if (line.charAt(j) == ' ') {
                map[i][j].type = BlockType.Empty;
            }
        }
    }
    player[0] = new PacMan(this, 23, 13);
    this.map[23][13].entity = player[0];
    this.pacmanLocation = new Pair(23, 13);
    player[1] = new Ghost(this, 5, 5);
    this.map[5][5].entity = player[1];
    player[2] = new Ghost(this, 5, 20);
    this.map[5][20].entity = player[2];
    player[3] = new Ghost(this, 8, 5);
    this.map[8][5].entity = player[3];
}
```

Listing 9-8: Game.java

注意新创建的实体是如何放置在地图上的。这意味着地图和实体之间存在双向关系，因为每个对象都持有对方的引用。

以下是用于初始化游戏地图的字符串数组：

```java
public class Chart {
    public static String chart[] = {
        "************************",
        "*      **      ***** **** *",
        "* **** ***** ***** ** ****** **** *",
        "* **** ***** ***** ** ****** **** *",
        "*                               ",
        "* **** ***** ***** ** ****** **** *",
        "* **      **      **      *      ",
        "************ **** ** ** ****** *******",
        "***********      ********",
        "***********      ********",
        "*********** ** ** ****** *******",
        "*            **      *******",
        "*********** ******** ******** *******",
        "*********** ** ** ****** *******",
        "*********** ******** *******",
        "********  ******",
        "******** ******* *******",
        "****** ** ****** ******",
        "*      **          *",
        "***** ***** ***** ****** **** *",
        "***** ***** ***** ****** **** *",
        "*  **      ****** ** ***",
        "*** ** *********** ** ***",
        "*  **  **  **  **  *",
        "*      **  **  **  ......*",
        "* ************ ************ *",
        "* ************ ************ *",
        "*             *",
        "********************************"
    };
}
```

Listing 9-9: Chart.java

星号表示墙，点表示带有分数的空格。最后，还有一些用空格符号表示的空区域。

`keyPressed()` 方法获取被按的键码并改变吃豆人 PacMan 的方向：

```java
public void keyPressed(KeyEvent keyEvent) {
    int key = keyEvent.getKeyCode();
    System.out.println("Key pressed: " + key);

    if (key == KeyEvent.VK_UP) {
        player[0].direction = Direction.Up;
    }
    if (key == KeyEvent.VK_RIGHT) {
        player[0].direction = Direction.Right;
    }
    if (key == KeyEvent.VK_DOWN) {
        player[0].direction = Direction.Down;
    }
    if (key == KeyEvent.VK_LEFT) {
        player[0].direction = Direction.Left;
    }
}
```

### 列表 9-10: Game.java

通过两个方法结束 `Game` 类的定义：

```java
public void playRound() {
    for (int i = 0; i < 4; i++) {
        player[i].play();
    }
}
public Block[][] getMap() {
    return map;
}
```

### 列表 9-11: Game.java

第一个方法在循环期间被调用并处理实体的。关于循环，让我们看看 `Main.java` 中的实现：

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.KeyEvent;
import java.awt.event.KeyListener;

public class Main extends JFrame {
    public static int CANVAS_WIDTH = 420;
    public static int CANVAS_HEIGHT = 480;
    private Game game;

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            @Override
            public void run() {
                new Main();
            }
        });
    }
}
```

### 列表 9-12: Main.java

`Main` 类继承自 `JFrame` 并包含了 `GameCanvas` 对象。在 `Main` 构造函数中，我们创建 `GameCanvas` 并将其添加：

```java
public Main() {
    game = new Game();
    GameCanvas gameCanvas = new GameCanvas();
    gameCanvas.setPreferredSize(new Dimension(CANVAS_WIDTH, CANVAS_HEIGHT));
    add(gameCanvas);
    setDefaultCloseOperation(EXIT_ON_CLOSE);
    pack();
    setTitle("PacMan!");
    setVisible(true);
}
```

现在让我们看看 `GameCanvas` 定义。`GameCanvas` 类持有 `Game` 对象的引用。它每 500 毫秒触发一次定时器：

```java
private class GameCanvas extends JPanel implements ActionListener, KeyListener {
    public Game game;
    private Timer timer;
    private final int DELAY = 500;

    public GameCanvas() {
        timer = new Timer(DELAY, this);
        timer.start();
    }
}
```

当定时器触发时，`actionPerformed` 方法被调用：

```java
@Override
public void actionPerformed(ActionEvent e) {
    game.playRound();
    if (!game.isActive) {
        timer.stop();
        repaint();
    }
}
```

### 列表 9-13: Main.java

`GameCanvas` 类实现了 `KeyListener` 接口。该类还实现了以下方法：

```java
@Override
public void keyTyped(KeyEvent e) { }
@Override
public void keyPressed(KeyEvent e) {
    game.keyPressed(e);
}
@Override
public void keyReleased(KeyEvent e) { }
```

### 列表 9-14: Main.java

`keyPressed` 方法将键事件传递给 `Game` 对象，从而改变了吃豆人的方向。最后，这里是当需要面板重绘时自动调用的方法：

```java
@Override
public void paintComponent(Graphics graphics) {
    super.paintComponent(graphics);
```

### 列表 9-15: Main.java

当用户按下按键时，`Game` 对象的 `keyPressed` 方法接收到键事件，这会导致吃豆人的移动。

### 列表 9-16: Main.java

`paintComponent` 方法在需要重绘时被调用。这里是逻辑逻辑：

```java
    Block[][] map = game.getMap();
    int BLOCK_WIDTH = 15;
    setBackground(Color.BLACK);
    for (int i = 0; i < 32; i++) {
        for (int j = 0; j < 28; j++) {
            if (map[i][j].entity != null) {
                if (map[i][j].entity.getClass().toString().indexOf("PacMan") >= 0) {
                    graphics.setColor(Color.YELLOW);
                    graphics.fillRect(j * BLOCK_WIDTH, i * BLOCK_WIDTH, BLOCK_WIDTH, BLOCK_WIDTH);
                } else {
                    graphics.setColor(Color.MAGENTA);
                    graphics.fillRect(j * BLOCK_WIDTH, i * BLOCK_WIDTH, BLOCK_WIDTH, BLOCK_WIDTH);
                }
            } else {
                if (map[i][j].type == BlockType.Wall) {
                    graphics.setColor(Color.WHITE);
                    graphics.fillRect(j * BLOCK_WIDTH, i * BLOCK_WIDTH, BLOCK_WIDTH, BLOCK_WIDTH);
                } else if (map[i][j].type == BlockType.Point) {
                    graphics.setColor(Color.RED);
                    graphics.fillRect(j * BLOCK_WIDTH, i * BLOCK_WIDTH, BLOCK_WIDTH, BLOCK_WIDTH);
                } else if (map[i][j].type == BlockType.Empty) {
                }
            }
        }
    }
    if (!game.gameActive()) {
        graphics.setColor(Color.RED);
        graphics.drawString("GAME OVER", 180, 200);
    }
}
```

### 列表 9-17: Main.java

绘图逻辑简单；我们遍历游戏地图，并用不同的颜色绘制各种组件（实体、墙和走廊）。

### 现在，让我们来看 PacMan 类定义：



```java
import java.util.ArrayList;

public class PacMan extends Entity {
    public PacMan(Game map, int x, int y) {
        this.game = map;
        this.type = EntityType.PacMan;
        this.x = x;
        this.y = y;
    }

    public void play() {
        ArrayList<Pair> candidateBlocks = new ArrayList<>();
        for (int i = x - 1; i <= x + 1; i++) {
            for (int j = y - 1; j <= y + 1; j++) {
                if (i >= 0 && i < game.sizeX
                    && j >= 0 && j < game.sizeY
                    && !(i == x && j == y)
                    && game.map[i][j].type != BlockType.Wall) {
                    candidateBlocks.add(new Pair(i, j));
                }
            }
        }

        if (direction == Direction.Up
            && candidateBlocks.contains(new Pair(x - 1, y))) {
            move(x - 1, y);
        } else if (direction == Direction.Right
            && candidateBlocks.contains(new Pair(x, y + 1))) {
            move(x, y + 1);
        } else if (direction == Direction.Down
            && candidateBlocks.contains(new Pair(x + 1, y))) {
            move(x + 1, y);
        } else if (direction == Direction.Left
            && candidateBlocks.contains(new Pair(x, y - 1))) {
            move(x, y - 1);
        }
    }

    game.pacmanLocation.x = x;
    game.pacmanLocation.y = y;
    if (game.map[x][y].type == BlockType.Point) {
        game.map[x][y].type = BlockType.Empty;
        game.pointsLeft--;
        if (game.pointsLeft == 0)
            game.gameActive = false;
    }
}
```

### 列表 9-18: PacMan.java

重要的内容在于 `play()` 方法的实现。首先，我们找到所有 PacMan 可以移动的相邻方格（实际上不是墙），并将它们放入一个候选方格列表中。

接下来，根据用户当前选择的方向（使用方向键），我们将 PacMan 移动到相应的方格（如果可用）。将 PacMan 移动到方格中意味着还要更新地图上 PacMan 的位置，并消除该方格中的点（如果有的话）。后者通过将方格类型更改为 `Empty` 并将游戏剩余分数减 1 来完成。如果分数变为 0，游戏就会结束。

`play()` 方法是多态性应用的一个示例。在 `Game.java` 中，每次循环中我们都会调用每个实体的 `play()` 方法。程序会根据实体对象的类型（PacMan 或 Ghost）来调用正确的方法。

现在让我们来看 Ghost 的定义：

```java
import java.util.ArrayList;
import java.util.Collections;

public class Ghost extends Entity {
    public Ghost(Game map, int x, int y) {
        this.game = map;
        this.type = EntityType.Ghost;
        this.x = x;
        this.y = y;
    }

    public void play() {
        ArrayList<Pair> candidateBlocks = new ArrayList<>();
        ArrayList<Double> distanceToPacman = new ArrayList<>();

        for (int i = x - 1; i <= x + 1; i++) {
            for (int j = y - 1; j <= y + 1; j++) {
                if (i >= 0 && i < game.sizeX
                    && j >= 0 && j < game.sizeY) {
                    if (game.map[i][j].type != BlockType.Wall) {
                        candidateBlocks.add(new Pair(i, j));
                        distanceToPacman.add(
                            Double.valueOf(
                                Math.sqrt(Math.pow(i - game.pacmanLocation.x, 2)
                                + Math.pow(j - game.pacmanLocation.y, 2))))
                        );
                    }
                }
            }
        }

        int minDistIn = 
            distanceToPacman.indexOf(Collections.min(distanceToPacman));

        if (game.map[candidateBlocks.get(minDistIn).x]
            [candidateBlocks.get(minDistIn).y]
          .entity != null) {
          //仅当 pacman 在那里时移动
          if (game.map[candidateBlocks.get(minDistIn).x]
            [candidateBlocks.get(minDistIn).y]
          .entity == TokenType.PacMan) {
            // 吃掉 pacman
            game.map[candidateBlocks.get(minDistIn).x]
            [candidateBlocks.get(minDistIn).y]
            .entity = null;
            game.gameActive = false;
            move(candidateBlocks.get(minDistIn).x,
            candidateBlocks.get(minDistIn).y);
          }
        } else {
          move(candidateBlocks.get(minDistIn).x,
          candidateBlocks.get(minDistIn).y);
        }
    }
}
```

### 列表 9-19: Ghost.java

在 `play()` 方法中，我们再次寻找移动的候选方格。此外，我们计算了每个候选位置到 PacMan 实体的直线距离数组。

我们使用 `Collections.min()` 方法来找到 `distanceToPacman` 列表中包含最近位置的 `Pair` 的索引。这里需要 `Pair` 类的 `equals()` 方法。在这里，我们定义两个 `Pair` 对象仅当它们的内容（x 和 y）相同时才为相等。相比之下，默认的 `equals()` 方法仅在两个引用指向同一个对象时返回 true。如果使用该方法的默认实现，我们将无法让这些代码工作。

在计算出距离较小的方格后，Ghost 将移动到该方格，以尽量接近 PacMan。Ghost 不能移动到有另一个 Ghost 的方格中，但它可以移动到 PacMan 所在的方格。在这种情况下，PacMan 会被 Ghost 吃掉，游戏结束。

这个游戏显然还有很多工作要做。例如，我们必须实现模式切换，即 PacMan 吞下大药丸并在短时间内开始追逐 Ghost。这种功能留给读者作为练习题。

你可以在 GitHub 上找到这个项目：

https://github.com/htset/java_oop_exercises/tree/master/PacMan/src
