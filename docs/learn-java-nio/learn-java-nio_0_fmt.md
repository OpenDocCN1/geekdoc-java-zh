
# Java NIO 入门指南

![](img/cover00113.jpeg)

我想将这本书献给将使用这本书的学生们。祝愿你们未来的事业成功，希望你们永不停止学习。

# 概述

`java.nio` 包在 java 1.4 中引入。与 Java I/O 相比，Java NIO 引入了面向缓冲区和通道的 I/O 操作数据流，从而提供了更快的执行和更好的性能。

此外，NIO API 提供了 `selectors`（选择器），它引入了异步或非阻塞的方式监听多个通道的 IO 事件的功能。在 NIO 中，最耗时的 I/O 活动（包括向操作系统填充和排空缓冲区）其速度得到了提升。

NIO API 的核心抽象如下：

- 缓冲区 (Buffers)，它们是数据、字符集及其关联解码器和编码器的容器，用于在字节和 Unicode 字符之间进行转换。
- 各种类型的通道 (Channels)，代表与能够执行 I/O 操作的实体的连接。
- 选择器 (Selectors) 和选择键 (selection keys)，它们与可选通道共同定义了一个复用的、非阻塞的 IO 设施。

# 环境搭建

本节将指导你如何在你的机器上下载并设置 Java。请按照以下步骤设置环境。

Java SE 可以从 **下载 Java** 链接免费获取。因此你可以根据你的操作系统下载相应的版本。

按照说明下载 java 并运行 `.exe` 在你的机器上安装 Java。一旦在你的机器上安装了 Java，你就需要设置环境变量以指向正确的安装目录 ——

## 为 windows 2000/XP 设置路径

假设你已将 Java 安装在 `c:\Program Files\java\jdk` 目录下 ——

- 右键点击“我的电脑”并选择“属性”。
- 点击“高级”选项卡下的“环境变量”按钮。
- 现在修改 `Path` 变量，使其也包含 Java 可执行文件所在的路径。例如，如果路径当前设置为 `'C:\WINDOWS\SYSTEM32'`，则将你的路径更改为 `'C:\WINDOWS\SYSTEM32;c:\Program Files\java\jdk\bin'`

## 为 windows 95/98/ME 设置路径

假设你已将 Java 安装在 `c:\Program Files\java\jdk` 目录下 deme

- 编辑 `'C:\autoexec.bat'` 文件，并在末尾添加以下行：

  `SET PATH = %PATH%;C:\Program Files\java\jdk\bin`

## 为 Linux, UNIX, Solaris, FreeBSD 设置路径

环境变量 `PATH` 应该指向 java 二进制文件安装的位置。如果你在此操作时遇到困难，请参考你的 shell 文档。

例如，如果你使用 `bash` 作为 shell，那么你需要在你的 `.bashrc` 末尾添加以下行：`export PATH = /path/to/java:$PATH`

## 流行的 Java 编辑器

编写 Java 程序需要一个文本编辑器。市场上还有更复杂的 IDE 可用。但目前你可以考虑以下之一 ——

- **Notepad (记事本)** ー 在 Windows 机器上，你可以使用任何简单的文本编辑器，如 Notepad（本教程推荐）、TextPad。
- **Netbeans** ー 是一个开源且免费的 Java IDE，可以从 `http://www.netbeans.org/` 下载。
- **Eclipse** ー 也是一个可以在 `https://www.eclipse.org/` 获取的 Java IDE。

# Java NIO vs IO

我们知道 NIO 是为了改进传统的 IO 而引入的。NIO 和 IO 之间的区别解释如下：

- 如前文所述，引入了面向缓冲区和通道的 I/O 操作数据流，从而提供了更快的执行和更好的性能。
- 此外，NIO API 提供了 `selectors`，它引入了以异步或非阻塞方式监听多个通道的 IO 事件的功能。在 NIO 中，最耗时的 I/O 活动（包括向操作系统填充和排空缓冲区）其速度得到了提升。
- NIO API 的核心抽象如下：

  - 缓冲区 (Buffers)，它们是数据、字符集及其关联解码器和编码器的容器，用于在字节和 Unicode 字符之间进行转换。
  - 各种类型的通道 (Channels)，代表与能够执行 I/O 操作的实体的连接。
  - 选择器 (Selectors) 和选择键 (selection keys)，它们与可选通道共同定义了一个复用的、非阻塞的 IO 设施。

# 通道 (Channels)

正如其名所示，通道被用作从一端到另一端的数据流。在 Java NIO 中，通道在缓冲区和另一端的实体之间起到作用，换句话说，通道用于将数据读取到缓冲区，以及从缓冲区写入数据。

## 通道的实现

Java NIO 通道主要在以下类中实现 deme

- **FileChannel** ー 为了从文件读取数据，我们使用文件通道。文件通道对象只能通过调用文件对象的 `getChannel()` 方法创建，因为我们无法直接创建文件对象。
- **DatagramChannel** ー 数据报通道可以通过 UDP（用户数据报协议）在网络上读取和写入数据。数据报通道对象可以使用工厂方法创建。
- **SocketChannel** - `SocketChannel` 通道可以通过 TCP（传输控制协议）在网络上进行数据的读写。它还使用工厂方法来创建新对象。
- **ServerSocketChannel** - `ServerSocketChannel` 在 TCP 连接上读写数据，类似于 Web 服务器。对于每个入站的连接，都会创建一个 `SocketChannel`。

## 示例

下面的示例从 `C:/Test/temp.txt` 读取文本文件并将内容打印到控制台。

### temp.txt

Hello World!

### ChannelDemo.java

```java
import java.io.IOException;
import java.io.RandomAccessFile;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;

public class ChannelDemo {
    public static void main(String args[]) throws IOException {
        RandomAccessFile file = new RandomAccessFile("C:/Test/temp.txt", "r");
        FileChannel fileChannel = file.getChannel();
        ByteBuffer byteBuffer = ByteBuffer.allocate(512);
        while (fileChannel.read(byteBuffer) > 0) {
            // flip the buffer to prepare for get operation
            byteBuffer.flip();
            while (byteBuffer.hasRemaining()) {
                System.out.print((char) byteBuffer.get());
            }
        }
        file.close();
    }
}
```

## 输出

Hello World!

# File Channel

## 描述

如前所述，Java NIO 通道的 `FileChannel` 实现被用于访问文件的元数据属性，包括创建时间、修改时间、大小等。此外，File Channels 是多线程的，这使得 Java NIO 比 Java IO 更为高效。

总的来说，我们可以说 `FileChannel` 是一个连接到文件的通道，通过它你可以从文件中读取数据并向文件写入数据。`FileChannel` 的另一个重要特性是，它不能被设置为非阻塞模式，并且始终在阻塞模式下运行。

我们无法直接获取文件通道对象，文件通道对象通过以下方式获取：

- `getChannel()` - 任意 `FileInputStream`、`FileOutputStream` 或 `RandomAccessFile` 上的方法。
- `open()` - File channel 的方法，按默认打开该通道。

File channel 对象的类型取决于从对象创建时调用的类类型，例如，如果通过调用 `FileInputStream` 的 `getchannel` 方法创建对象，则 File channel 是为读取打开的，并在尝试写入时将抛出 `NonWritableChannelException`。

## 示例

下面的示例展示了如何从 Java NIO `FileChannel` 读写数据。

下面的示例从 `C:/Test/temp.txt` 读取文本文件并将内容打印到控制台。

### temp.txt

Hello World!

### FileChannelDemo.java

```java
import java.io.IOException;
import java.io.RandomAccessFile;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.charset.Charset;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;
import java.util.HashSet;
import java.util.Set;

public class FileChannelDemo {
    public static void main(String args[]) throws IOException {
        //append the content to existing file
        writeFileChannel(ByteBuffer.wrap("Welcome to TutorialsPoint".getBytes()));
        //read the file
        readFileChannel();
    }

    public static void readFileChannel() throws IOException {
        RandomAccessFile randomAccessFile = new RandomAccessFile("C:/Test/temp.txt", "rw");
        FileChannel fileChannel = randomAccessFile.getChannel();
        ByteBuffer byteBuffer = ByteBuffer.allocate(512);
        Charset charset = Charset.forName("US-ASCII");
        while (fileChannel.read(byteBuffer) > 0) {
            byteBuffer.rewind();
            System.out.print(charset.decode(byteBuffer));
            byteBuffer.flip();
        }
        fileChannel.close();
        randomAccessFile.close();
    }

    public static void writeFileChannel(ByteBuffer byteBuffer) throws IOException {
        Set<StandardOpenOption> options = new HashSet<>();
        options.add(StandardOpenOption.CREATE);
        options.add(StandardOpenOption.APPEND);
        Path path = Paths.get("C:/Test/temp.txt");
        FileChannel fileChannel = FileChannel.open(path, options);
        fileChannel.write(byteBuffer);
        fileChannel.close();
    }
}
```

## 输出

Hello World! Welcome to TutorialsPoint

# Datagram Channel

Java NIO Datagram 被用作通道，可以在无连接的协议上发送和接收 UDP 包。默认情况下，datagram channel 是阻塞的，但也可以在非阻塞模式下使用。为了使其变为非阻塞，我们可以使用 `configureBlocking(false)` 方法。Datagram channel 可以通过调用名为 `open()` 的静态方法之一打开，该方法还可以接受 IP 地址作为参数，以便用于多组播。

Datagram channel 与 `FileChannel` 不同，它默认是不连接的，为了建立连接，我们必须显式调用其 `connect()` 方法。然而，使用 `send` 和 `receive` 方法不需要连接，但使用 `read` 和 `write` 方法时必须处于连接状态，因为这些方法不接受也不返回套接地址。

我们可以通过调用 `isConnected()` 方法检查 datagram channel 的连接状态。一旦连接，datagram channel 将一直保持连接状态，直到被断开。Datagram channels 是线程安全的，并支持多线程。

## datagram channel 的重要方法

- `bind(SocketAddress)` - 此方法用于将 datagram channel 绑定到本地地址。
- `connect(SocketAddress)` - 此方法用于连接套接字。
- `disconnect()` - 此方法用于断开套接字。
- `getRemoteAddress()` - 此方法返回远程位置的地址。
- `isConnected()` - 如前所述，此方法返回 datagram channel 的连接状态。
- `open()` 和 `open(ProtocolFamily)` - 打开单个地址或多个地址的方法。
- `read(ByteBuffer dst)` - 此方法用于从给定的缓冲区读取数据。
- `receive(ByteBuffer dst)` - 此方法用于通过此通道接收数据报文。
- `send(ByteBuffer src, SocketAddress target)` - 此方法用于通过此通道发送数据报文。

## 示例

下面的示例展示了如何从 Java NIO FileChannel 发送数据。

### Server: DatagramChannelServer.java

```java
import java.io.IOException;
import java.net.InetSocketAddress;
import java.net.SocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.DatagramChannel;

public class DatagramChannelServer {
    public static void main(String args[]) throws IOException {
        DatagramChannel server = null;
        server = DatagramChannel.open();
        InetSocketAddress iAdd = new InetSocketAddress("localhost", 8989);
        server.bind(iAdd);
        System.out.println("Server Started: " + iAdd);
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        //receive buffer from client.
        SocketAddress remoteAdd = server.receive(buffer);
        //change mode of buffer
        buffer.flip();
        int limits = buffer.limit();
        byte bytes[] = new byte[limits];
        buffer.get(bytes, 0, limits);
        String msg = new String(bytes);
        System.out.println("Client at " + remoteAdd + " sent: " + msg);
        server.send(buffer,remoteAdd);
        server.close();
    }
}
```

### Client: DatagramChannelClient.java



```java
import java.io.IOException;
import java.net.InetSocketAddress;
import java.net.SocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.DatagramChannel;

public class DatagramChannelClient {
    public static void main(String args[]) throws IOException {
        DatagramChannel client = null;
        client = DatagramChannel.open();
        client.bind(null);
        String msg = "Hello World!";
        ByteBuffer buffer = ByteBuffer.wrap(msg.getBytes());
    }
}
```

```java
InetSocketAddress serverAddress = new InetSocketAddress("localhost", 8989);
client.send(buffer, serverAddress);
buffer.clear();
client.receive(buffer);
buffer.flip();
client.close();
}
}
```

### 输出

运行客户端将在服务器上打印以下输出：

```
Server Started: localhost/127.0.0.1:8989
Client at /127.0.0.1:64857 sent: Hello World!
```

# Socket Channel

Java NIO socket channel 是一种可选的通道类型，这意味着它可以使用 selector 进行多路复用，用于连接接字的面向流的数据流。Socket channel 可以通过其静态 `open()` 方法创建，前提是任何预存在的 socket 尚未存在。Socket channel 是通过调用 `open` 方法创建的，但尚未连接。为了连接 socket channel，需要调用通道的 `connect()` 方法。这里需要提到的一点是，如果通道未连接就尝试进行任何 I/O 操作，该通道将抛出 `NotYetConnectedException`。因此，必须确保在执行任何 IO 操作之前通道已连接。一旦通道建立连接，它将保持连接状态直到被关闭。可以通过调用其 `isConnected` 方法来确定 socket channel 的状态。

socket channel 的连接可以通过调用其 `finishConnect()` 方法完成。是否正在进行连接操作可以通过调用 `isConnectionPending` 方法来确定。默认情况下，socket channel 支持非阻塞连接。此外，它还支持异步关闭，这类似于 `Channel` 类中指定的异步关闭操作。

Socket channels 供多线程并发使用是安全的。它们支持并发读写，尽管在任何给定时刻，最多有一个线程在读取，最多有一个线程在写入。`connect` 和 `finishConnect` 方法之间是互斥同步的，在其中一个方法正在执行期间尝试发起读或写操作将阻塞，直到该调用完成。

## Socket channel 的重要方法

* `bind(SocketAddress local)` – 此方法用于将 socket channel 绑定到作为此方法参数提供的本地地址。
* `connect(SocketAddress remote)` – 此方法用于将 socket 连接到远程地址。
* `finishConnect()` – 此方法用于完成连接一个 socket channel 的过程。
* `getRemoteAddress()` – 此方法返回通道 socket 所连接的远程位置地址。
* `isConnected()` – 如前所述，此方法返回 socket channel 的连接状态，即是否已连接。
* `open()` 和 `open((SocketAddress remote)` – `open` 方法用于为未指定的地址打开 socket channel，而带参数的 `open` 方法则为指定的远程地址打开通道并与之连接。此便利方法的工作方式等同于调用 `open()` 方法，随后在生成的 socket channel 上调用 `connect` 方法，并传递远程地址，然后返回该通道。
* `read(ByteBuffer dst)` – 此方法用于通过 socket channel 从给定的 buffer 读取数据。
* `isConnectionPending()` – 此方法告知此通道上是否正在进行连接操作。

## 示例

以下示例展示了如何从 Java NIO SocketChannel 发送数据。

### C:/Test/temp.txt

```
Hello World!
```

### Client: SocketChannelClient.java

```java
import java.io.IOException;
import java.net.InetSocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.ServerSocketChannel;
import java.nio.channels.SocketChannel;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;
import java.util.EnumSet;

public class SocketChannelClient {
    public static void main(String[] args) throws IOException {
        ServerSocketChannel serverSocket = null;
        SocketChannel client = null;
        serverSocket = ServerSocketChannel.open();
        serverSocket.socket().bind(new InetSocketAddress(9000));
        client = serverSocket.accept();
        System.out.println("Connection Set: " + client.getRemoteAddress());
        Path path = Paths.get("C:/Test/temp1.txt");
        FileChannel fileChannel = FileChannel.open(path,
            EnumSet.of(StandardOpenOption.CREATE,
                StandardOpenOption.TRUNCATE_EXISTING,
                StandardOpenOption.WRITE)
        );
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        while(client.read(buffer) > 0) {
            buffer.flip();
            fileChannel.write(buffer);
            buffer.clear();
        }
        fileChannel.close();
        System.out.println("File Received");
        client.close();
    }
}
```

### 输出

在服务器启动之前，运行客户端不会打印任何内容。

### Server: SocketChannelServer.java

```java
import java.io.IOException;
import java.net.InetSocketAddress;
import java.net.SocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.SocketChannel;
import java.nio.file.Path;
import java.nio.file.Paths;

public class SocketChannelServer {
    public static void main(String[] args) throws IOException {
        SocketChannel server = SocketChannel.open();
        SocketAddress socketAddr = new InetSocketAddress("localhost", 9000);
        server.connect(socketAddr);
        Path path = Paths.get("C:/Test/temp.txt");
        FileChannel fileChannel = FileChannel.open(path);
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        while(fileChannel.read(buffer) > 0) {
            buffer.flip();
            server.write(buffer);
            buffer.clear();
        }
        fileChannel.close();
        System.out.println("File Sent");
        server.close();
    }
}
```

### 输出

运行服务器将打印以下内容：

```
Connection Set: /127.0.0.1:49558
File Received
```

# Server Socket Channel

Java NIO server socket channel 同样是一种可选的通道类型，用于连接接字的面向流的数据流。Server socket channel 可以通过其静态 `open()` 方法创建，前提是任何预存在的 socket 尚未存在。Server Socket channel 是通过调用 `open` 方法创建的，但尚未绑定。为了绑定通道，需要调用 `bind()` 方法。

这里需要提到的一点是，如果通道未绑定就尝试进行任何 I/O 操作，该通道将抛出 `NotYetBoundException`。因此，必须确保在执行任何 IO 操作之前通道已绑定。

server socket channel 的传入连接通过调用 `ServerSocketChannel.accept()` 方法来监听。当 `accept()` 方法返回时，它会返回一个带有传入连接的 `SocketChannel`。因此，`accept()` 方法会阻塞直到有新连接可用。如果通道处于非阻塞模式，当没有挂起的连接时 `accept` 方法将立即返回 `null`。否则，它将无限阻塞直到有新连接或发生 I/O 错误。

新通道的 socket 最初是未绑定的；在接受连接之前，必须通过其 socket 的一个 `bind` 方法绑定到特定地址。此外，新通道是通过调用全局默认 `SelectorProvider` 对象的 `openServerSocketChannel` 方法创建的。

与 socket channel 一，server socket channel 可以 `read()` 方法读取数据。首先分配 buffer。从 `ServerSocketChannel` 读取的数据将存储在 buffer 中。其次我们调用 `ServerSocketChannel.read()` 方法，它从 `ServerSocketChannel` 读取数据并存入 buffer。`read()` 方法的整数值返回了写入 buffer 的字节数。

同样，可以使用 `write()` 方法使用 buffer 参数向 server socket channel 写入数据。通常会在 while 循环中使用 `write` 方法，因为需要重复调用 `write` 方法，直到 `Buffer` 中没有更多可写入的字节为止。

* `bind(SocketAddress local)` - 此方法用于将套接字通道绑定到作为参数提供的本地地址。
* `accept()` - 此方法用于接收连接到此通道套接字的连接。
* `connect(SocketAddress remote)` - 此方法用于将套接字连接到远程地址。
* `finishConnect()` - 此方法用于完成连接套接字通道的过程。
* `getRemoteAddress()` - 此方法返回通道套接字所连接的远程位置地址。
* `isConnected()` - 如前，此方法返回套接字通道的连接状态，即是否已连接。
* `open()` - `open` 方法用于打开一个未指定地址的套接字通道。此便利方法的作用等同于调用 `open()` 方法，在生成的服务器套接字通道上调用 `connect` 方法，并传入远程地址，然后返回该通道。
* `read(ByteBuffer dst)` - 此方法用于通过套接字通道从缓冲区读取数据。
* `setOption(SocketOption<T> name, T value)` - 此方法设置套接字选项的值。
* `socket()` - 此方法获取与此通道相关的服务器套接字。
* `validOps()` - 此方法返回一个标识此通道支持的操作集。服务器套接字通道仅支持接受新连接，因此此方法返回 `SelectionKey.OP_ACCEPT`。

## 示例

以下示例展示了如何从 Java NIO `ServerSocketChannel` 发送数据。

### `C:/Test/temp.txt`

```
Hello World!
```

### 客户端：`SocketChannelClient.java`

```java
import java.io.IOException;
import java.net.InetSocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.ServerSocketChannel;
import java.nio.channels.SocketChannel;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;
import java.util.EnumSet;

public class SocketChannelClient {
    public static void main(String[] args) throws IOException {
        ServerSocketChannel serverSocket = null;
        SocketChannel client = null;
        serverSocket = ServerSocketChannel.open();
        serverSocket.socket().bind(new InetSocketAddress(9000));
        client = serverSocket.accept();
        System.out.println("Connection Set: " + client.getRemoteAddress());
        Path path = Paths.get("C:/Test/temp1.txt");
        FileChannel fileChannel = FileChannel.open(path,
            EnumSet.of(StandardOpenOption.CREATE,
            StandardOpenOption.TRUNCATE_EXISTING,
            StandardOpenOption.WRITE)
        );
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        while(client.read(buffer) > 0) {
            buffer.flip();
            fileChannel.write(buffer);
            buffer.clear();
        }
        fileChannel.close();
        System.out.println("File Received");
        client.close();
    }
}
```

### 输出

在服务器启动之前，运行客户端不会打印任何内容。

### 服务器：`SocketChannelServer.java`



```java
import java.io.IOException;
import java.net.InetSocketAddress;
import java.net.SocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.SocketChannel;
import java.nio.file.Path;
import java.nio.file.Paths;

public class SocketChannelServer {
    public static void main(String[] args) throws IOException {
        SocketChannel server = SocketChannel.open();
        SocketAddress socketAddr = new InetSocketAddress("localhost", 9000);
        server.connect(socketAddr);
        Path path = Paths.get("C:/Test/temp.txt");
        FileChannel fileChannel = FileChannel.open(path);
        ByteBuffer buffer = ByteBuffer.allocate(1024);
        while(fileChannel.read(buffer) > 0) {
            buffer.flip();
            server.write(buffer);
            buffer.clear();
        }
        fileChannel.close();
        System.out.println("File Sent");
        server.close();
    }
}
```

### 输出

运行服务器将打印以下内容：

```
Connection Set: /127.0.0.1:49558
File Received
```

# 散播 (Scatter)

众所周知，与 Java 传统的 IO API 相比，Java NIO 是一个针对数据 IO 操作优化的 API。Java NIO 提供的另一个额外支持是从多个缓冲区向通道读/写数据。这种多重读写支持被称为散播 (Scatter) 和聚集 (Gather)，其中在读取数据时，数据从单个通道散播到多个缓冲区；而在写入数据时，数据则从多个缓冲区聚集到单个通道中。

为了实现这种从通道进行多重读写，Java NIO 提供了 `ScatteringByteChannel` 和 `GatheringByteChannel` API，用于数据的读和写，如下例所示。

## ScatteringByteChannel

**从多个通道读取** - 在这里，我们实现了从单个通道将数据读取到多个缓冲区。为此，我们分配了多个缓冲区并将它们添加到缓冲区类型的数组中。然后，将此数组作为参数传递给 `ScatteringByteChannel.read()` 方法，该方法将按顺序从通道写入数据。一旦某个缓冲区满，通道将移动到下一个缓冲区。

以下示例展示了在 Java 中如何进行数据的散播：

### `C:/Test/temp.txt`

```
Hello World!
```

```java
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.ScatteringByteChannel;

public class Scatter {
    private static String FILENAME = "C:/Test/temp.txt";
    public static void main(String[] args) {
        ByteBuffer bLen1 = ByteBuffer.allocate(1024);
        ByteBuffer bLen2 = ByteBuffer.allocate(1024);
        FileInputStream in;
        try {
            in = new FileInputStream(FILENAME);
            ScatteringByteChannel scatter = in.getChannel();
            scatter.read(new ByteBuffer[]{bLen1, bLen2});
            bLen1.position(0);
            bLen2.position(0);
            int len1 = bLen1.asIntBuffer().get();
            int len2 = bLen2.asIntBuffer().get();
            System.out.println("Scattering : Len1 = " + len1);
            System.out.println("Scattering : Len2 = " + len2);
        } catch (FileNotFoundException exObj) {
            exObj.printStackTrace();
        } catch (IOException ioObj) {
            ioObj.printStackTrace();
        }
    }
}
```

### 输出

```
Scattering : Len1 = 1214606444
Scattering : Len2 = 0
```

最后得出结论，Java NIO 中的散播/聚集方法在合理使用的情况下是优化且支持多任务的。它允许让操作系统完成将数据拆分到多个桶中的繁重工作，或者将分散的数据块组合成整体。无疑这通过避免缓冲区拷贝节省了时间并更有效地使用了操作系统，同时也减少了编写和调试的代码量。

# 聚集 (Gather)

众所周知，与 Java 传统的 IO API 相比，Java NIO 是一个针对数据 IO 操作优化的 API。Java NIO 提供的另一个额外支持是从多个缓冲区向通道读/写数据。这种多重读写支持被称为散播 (Scatter) 和聚集 (Gather)，其中在读取数据时，数据从单个通道散播到多个缓冲区；而在写入数据时，数据则从多个缓冲区聚集到单个通道中。

为了实现这种从通道进行多重读写，Java NIO 提供了 `ScatteringByteChannel` 和 `GatheringByteChannel` API，用于数据的读和写，如下例所示。

## GatheringByteChannel

**写入多个通道** - 在这里，我们实现了从多个缓冲区将数据写入单个通道。为此，再次分配了多个缓冲区并将它们添加到缓冲区类型的数组中。然后，将此数组作为参数传递给 `GatheringByteChannel.write()` 方法，该方法将按缓冲区在数组中出现的顺序从多个缓冲区写入数据。这里需要记住的一点是，只有缓冲区位置和限制之间的数据会被写入。

以下示例展示了在 Java 中如何进行数据的聚集：

```java
import java.io.FileNotFoundException;
```

### 输出

```
Gathering : Len1 = 24
Gathering : Len2 = 25
```

最后可以得出结论，Java NIO 中的分散/聚集（scatter/gather）方法在用得当时被引入为一种优化和多任务方案。它允许你委托操作系统来处理繁重的工作，即将你读取到的数据分离到多个桶中，或将分散的数据块组装成整体。无疑，这通过避免缓冲区拷贝节省了时间，并更有效地利用了操作系统，同时减少了需要编写和调试的代码量。

# Buffer（缓冲区）

Java NIO 中的 Buffer 也可以被视为一种简单的对象，它作为一个固定大小的数据块容器，可以用于向通道写入数据或从通道读取数据，因此 Buffer 充当了通道的端点。

它提供了一组方法，可以更方便地处理内存块，以便从通道中读写数据。

与经典的 IO 相比，Buffer 使得 NIO 包更加高效且快速，因为在 IO 的情况下，数据是以流的形式处理的，而流不支持异步和并发的数据流。此外，IO 不允许以字节块或字节组的形式执行数据。

定义 Java NIO Buffer 的主要参数可以定义为：

*   **Capacity（容量）** — Buffer 中可以存储的最大数据/字节量。Buffer 的 `Capacity` 无法更改。一旦缓冲区满，在向其写入之前必须清除。
*   **Limit（限制）** — `Limit` 的含义取决于 Buffer 的模式。即在 Buffer 的写模式下，`Limit` 等于容量，这意味着可以写入缓冲区的最大数据。而在 Buffer 的读模式下，`Limit` 意味着从 Buffer 中读取数据的限制。
*   **Position（位置）** — 指向缓冲区中当前的位置。在创建缓冲区时初始设置为 0，换句话说，它是下一个要读取或写入元素的索引，由 `get()` 和 `put()` 方法自动更新。
*   **Mark（标记）** — `Mark` 是缓冲区中位置的一个书签。当调用 `mark()` 方法时，会记录当前位置，当调用 `reset()` 时，会恢复到标记的位置。

## Buffer Type（缓冲区类型）

Java NIO Buffer 可以根据其所处理的数据类型分类为以下变体：

*   `ByteBuffer`
*   `MappedByteBuffer`
*   `CharBuffer`
*   `DoubleBuffer`
*   `FloatBuffer`
*   `IntBuffer`
*   `LongBuffer`
*   `ShortBuffer`

## Important methods of Buffer（Buffer 的重要方法）

如前所述，Buffer 作为内存对象提供了一组更方便处理内存块的方法。以下是 Buffer 的重要方法：

*   `allocate(int capacity)` — 该方法用于分配一个容量为参数的新缓冲区。如果传递的容量为负整数，`allocate()` 方法将抛出 `IllegalArgumentException`。
*   `read()` 和 `put()` — 通道的 `read()` 方法用于将数据从通道写入缓冲区，而 `put()` 是缓冲区的一个方法，用于向缓冲区中写入数据。
*   `flip()` — `flip()` 方法将 Buffer 的模式从写模式切换到读模式。它还会将位置置回 0，并将限制设置为写入时位置所在的位置。
*   `write()` 和 `get()` — 通道的 `write()` 方法用于将数据从缓冲区写入通道，而 `get()` 是缓冲区的一个方法，用于从缓冲区中读取数据。
*   `rewind()` — 当需要重新读取时使用 `rewind()` 方法，因为它将位置置回零且不改变限制的值。
*   `clear()` 和 `compact()` — `clear()` 和 `compact()` 两个方法都用于：`clear()` 方法将位置置为零并将限制等于容量。另一方面，`compact()` 方法将所有未读的数据拷贝到缓冲区的开头并将位置设置为正确的位置。
*   `mark()` 和 `reset()` — `mark()` 是缓冲区中位置的标记。调用 `mark()` 方法时会记录当前位置，调用 `reset()` 时会恢复到标记的位置。

## Example（示例）

以下示例展示了上述方法的实现。

```java
import java.nio.ByteBuffer;
import java.nio.CharBuffer;

public class BufferDemo {
    public static void main (String[] args) {
        // 分配一个字符缓冲区
        CharBuffer buffer = CharBuffer.allocate(10);
        String text = "bufferDemo";
        System.out.println("Input text: " + text);
        for (int i = 0; i < text.length(); i++) {
            char c = text.charAt(i);
            // 将字符放入缓冲区
            buffer.put(c);
        }
        int buffPos = buffer.position();
        System.out.println("Position after data is written into buffer: " + buffPos);
        buffer.flip();
        System.out.println("Reading buffer contents:");
        while (buffer.hasRemaining()) {
            System.out.println(buffer.get());
        }
        // 将缓冲区的位置设置为 5
        buffer.position(5);
        // 在当前位置设置标记
        buffer.mark();
        // 尝试更改位置
        buffer.position(6);
        // 调用 reset 方法恢复到标记的位置
        buffer.reset();
        System.out.println("Restored buffer position : " + buffer.position());
    }
}
```

### 输出

```
Input text: bufferDemo
Position after data is written into buffer: 10
Reading buffer contents:
b
u
f
f
e
r
D
e
m
o
Restored buffer position : 5
```



# Selector（选择器）

众所周知，Java NIO 支持通道和缓冲区之间的多次事务。因此，为了检查一个或多个通道并确定哪些通道准备好进行数据事务（即读取或写入），Java NIO 提供了 `Selector`。

通过 `Selector`，我们可以创建一个线程来感知哪些通道已准备好进行数据读写，并处理特定的通道。

我们可以通过调用其静态方法 `open()` 获取 `selector` 实例。打开 `selector` 后，我们需要将其注册一个非阻塞模式的通道，这将返回一个 `SelectionKey` 实例。

`SelectionKey` 基本上是与通道可以执行的操作集合，或者说，我们可以通过选择 key 了解通道的状态。

由选择 key 表示的主要操作或状态有：

- `SelectionKey.OP_CONNECT` — 准备好连接到服务器的通道。
- `SelectionKey.OP_ACCEPT` — 准备好接受传入连接的通道。
- `SelectionKey.OP_READ` — 准备好读取数据的通道。
- `SelectionKey.OP_WRITE` — 准备好写入数据的通道。

注册后获取的选择 key 包含下面提到的一些重要方法：

- `attach()` — 此方法用于将一个对象绑定到 key 上。将对象绑定到通道的主要目的是为了识别同一个通道。
- `attachment()` — 此方法用于从通道中获取绑定的对象。
- `channel()` — 此方法用于获取创建特定 key 的通道。
- `selector()` — 此方法用于获取创建特定 key 的 `selector`。
- `isValid()` — 此方法返回 key 是否有效。
- `isReadable()` — 此方法表示 key 对应的通道是否已准备好读取。
- `isWritable()` — 此方法表示 key 对应的通道是否已准备好写入。
- `isAcceptable()` — 此方法表示 key 对应的通道是否已准备好接受传入的连接。
- `isConnectable()` — 此方法测试此 key 的通道是否已完成或未完成其套接连接操作。
- `interestOps()` — 此方法获取此 key 的感兴趣集（interest set）。
- `readyOps()` — 此方法获取就绪集，即通道已准备好的操作集合。

我们可以通过调用其静态方法 `select()` 从 `selector` 中选择通道。`selector` 的 `select` 方法有重载，如下：

- `select()` — 此方法阻塞当前线程，直到至少有一个通道为其所注册的事件准备好就绪。
- `select(long timeout)` — 此方法的作用与 `select()` 相同，但它最多阻塞线程 `timeout` 毫秒（参数值）。
- `selectNow()` — 此方法完全不阻塞。它会立即返回所有已就绪的通道。

此外，为了离开调用 `select` 方法的阻塞线程，可以从 `selector` 实例调用 `wakeup()` 方法，之后在 `select()` 内部等待的线程将立即返回。

最后，我们可以通过调用 `close()` 方法关闭 `selector`，这同时会失效与该 `Selector` 注册的所有 `SelectionKey` 实例并关闭 `selector`。

## Example

```java
import java.io.FileInputStream;
import java.io.IOException;
import java.net.InetSocketAddress;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.SelectionKey;
import java.nio.channels.Selector;
import java.nio.channels.ServerSocketChannel;
import java.nio.channels.SocketChannel;
import java.util.Iterator;
import java.util.Set;

public class SelectorDemo {
    public static void main(String[] args) throws IOException {
        String demo_text = "This is a demo String";
        Selector selector = Selector.open();
        ServerSocketChannel serverSocket = ServerSocketChannel.open();
        serverSocket.bind(new InetSocketAddress("localhost", 5454));
        serverSocket.configureBlocking(false);
        serverSocket.register(selector, SelectionKey.OP_ACCEPT);
        ByteBuffer buffer = ByteBuffer.allocate(256);
        while (true) {
            selector.select();
            Set<SelectionKey> selectedKeys = selector.selectedKeys();
            Iterator<SelectionKey> iter = selectedKeys.iterator();
            while (iter.hasNext()) {
                SelectionKey key = iter.next();
                int interestOps = key.interestOps();
                System.out.println(interestOps);
                if (key.isAcceptable()) {
                    SocketChannel client = serverSocket.accept();
                    client.configureBlocking(false);
                    client.register(selector, SelectionKey.OP_READ);
                }
                if (key.isReadable()) {
                    SocketChannel client = (SocketChannel) key.channel();
                    client.read(buffer);
                    if (new String(buffer.array()).trim().equals(demo_text)) {
                        client.close();
                        System.out.println("Not accepting client messages anymore");
                    }
                    buffer.flip();
                    client.write(buffer);
                    buffer.clear();
                }
                iter.remove();
            }
        }
    }
}
```

# Pipe

在 Java NIO 中，`pipe` 是一种用于在两个线程之间读写数据的组件。`Pipe` 主要由两个负责数据传播的通道组成。

在两个组成通道中，一个被称为 `Sink channel`（汇通道），主要用于写入数据；另一个是 `Source channel`（源通道），其主要目的是从 `Sink` 通道读取数据。

在数据读写过程中会保持数据同步，因为必须确保读取数据的顺序与写入 `Pipe` 的顺序相同。

必须注意，`Pipe` 中是单向数据流，即数据只写入 `Sink` 通道，且只能从 `Source` 通道读取。

在 Java NIO 中，`pipe` 被定义为一个抽象类，主要包含三个方法，其中两个是抽象方法。

## Methods of Pipe class

- `open()` — 此方法用于获取 `Pipe` 实例，或者说通过调用此方法创建 `pipe`。
- `sink()` — 此方法返回 `Pipe` 的 `sink channel`，通过调用其 `write()` 方法来写入数据。
- `source()` — 此方法返回 `Pipe` 的 `source channel`，通过调用其 `read()` 方法读取数据。

## Example

以下示例展示了 Java NIO `pipe` 的实现。

```java
import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.Pipe;

public class PipeDemo {
    public static void main(String[] args) throws IOException {
        // 创建 Pipe 实例
        Pipe pipe = Pipe.open();
        // 获取 pipe 的 sink channel
        Pipe.SinkChannel skChannel = pipe.sink();
        String testData = "Test Data to Check java NIO Pipe.";
        ByteBuffer buffer = ByteBuffer.allocate(512);
        buffer.clear();
        buffer.put(testData.getBytes());
        buffer.flip();
        // 将数据写入 sink channel
        while(buffer.hasRemaining()) {
            skChannel.write(buffer);
        }
        // 获取 pipe 的 source channel
        Pipe.SourceChannel sourceChannel = pipe.source();
        buffer = ByteBuffer.allocate(512);
        // 将数据写入控制台
        while(sourceChannel.read(buffer) > 0){
            // limit 设置为当前位置，位置置为 0
            buffer.flip();
            while(buffer.hasRemaining()){
                char ch = (char) buffer.get();
                System.out.print(ch);
            }
            // 位置置为 0，limit 设置为容量以清空 buffer
            buffer.clear();
        }
    }
}
```

## Output

```
Test Data to Check java NIO Pipe.
```

假设有一个文件 `c:/test.txt`，内容如下。该文件将作为我们示例程序的输入。

# Path

正如名称所示，`Path` 是文件系统中某个实体（如文件或目录）的特定位置，以便在该位置对其进行搜索和访问。

从 Java 技术角度来看，`Path` 是在 Java 7 版本引入 Java NIO `file` 包中的一个接口，它是特定文件系统中位置的表示。由于 `path` 接口位于 Java NIO 包，因此其全限定名为 `java.nio.file.Path`。

通常，实体的路径有两种类型：一种是绝对路径（absolute path），另一种是相对路径（relative path）。正如路径名称所示，绝对路径是从根目录到实体的位置地址，而相对路径是相对于其他路径的位置地址。`Path` 在其定义中使用分隔符，Windows 使用 `\`，Unix 操作系统使用 `/`。

为了获取 `Path` 实例，我们可以使用 `java.nio.file.Paths` 类的静态方法 `get()`。此方法将路径字符串或一组组合成路径字符串的字符串转换为 `Path` 实例。如果传递的参数包含非法字符，该方法还会抛出运行时异常 `InvalidPathException`。

如上所述，绝对路径是通过传递根元素和定位文件所需的完整目录列表来获取的。相对路径可以通过结合基路径与相对路径来获取。接下来的示例将演示两种路径的获取。

## Example

```java
package com.java.nio;

import java.io.IOException;
import java.nio.Buffer;
import java.nio.ByteBuffer;
import java.nio.file.FileSystem;
import java.nio.file.LinkOption;
import java.nio.file.Path;
import java.nio.file.Paths;

public class PathDemo {
    public static void main(String[] args) throws IOException {
        Path relative = Paths.get("file2.txt");
        System.out.println("Relative path: " + relative);
        Path absolute = relative.toAbsolutePath();
        System.out.println("Absolute path: " + absolute);
    }
}
```

到目前为止，我们已经知道了什么是 `Path` 接口、为什么需要它以及如何访问它。现在，我们将了解 `Path` 接口为我们提供的重要方法。

## Path 接口的重要方法

- `getFileName()` — 返回创建此对象的文件的系统。
- `getName()` — 返回此路径的名称元素，类型为 `Path` 对象。
- `getNameCount()` — 返回路径中名称元素的数量。
- `subpath()` — 返回一个作为此路径名称元素子序列的相对 `Path`。
- `getParent()` — 返回父路径，如果此路径没有父路径则返回 `null`。
- `getRoot()` — 返回此路径的根组件，类型为 `Path` 对象；如果此路径没有根组件，则返回 `null`。
- `toAbsolutePath()` — 返回一个表示此路径绝对路径的 `Path` 对象。
- `toRealPath()` — 返回现有文件的真实路径。
- `toFile()` — 返回表示此路径的 `File` 对象。
- `normalize()` — 返回一个消除了冗余名称元素的路径。
- `compareTo(Path other)` — 按照字典顺序比较两个抽象路径。如果参数与此路径相等，则返回零；如果此路径在字典顺序上小于参数，则返回小于零的值；如果此路径在字典顺序上大于参数，则返回大于零的值。
- `endsWith(Path other)` — 测试此路径是否以给定路径结尾。如果给定路径具有 N 个元素且没有根组件，且此路径有 N 或更多元素，那么如果每个路径从离根最远的元素开始的最后 N 个元素相等，则此路径就以给定路径结尾。
- `endsWith(String other)` — 测试此路径是否以按照 `endsWith(Path)` 方法指定的方式转换给定路径字符串构造而成的 `Path` 结尾。

## Example

以下示例说明了上述的 `Path` 接口的不同方法：

```java
package com.java.nio;

import java.io.IOException;
import java.nio.Buffer;
import java.nio.ByteBuffer;
import java.nio.file.FileSystem;
import java.nio.file.LinkOption;
import java.nio.file.Path;
import java.nio.file.Paths;

public class PathDemo {
    public static void main(String[] args) throws IOException {
        Path path = Paths.get("D:/workspace/ContentW/Saurav_CV.docx");
        FileSystem fs = path.getFileSystem();
        System.out.println(fs.toString());
        System.out.println(path.isAbsolute());
        System.out.println(path.getFileName());
        System.out.println(path.toAbsolutePath().toString());
        System.out.println(path.getRoot());
        System.out.println(path.getParent());
        System.out.println(path.getNameCount());
        System.out.println(path.getName(0));
        System.out.println(path.subpath(0, 2));
        System.out.println(path.toString());
        System.out.println(path.getNameCount());
        Path realPath = path.toRealPath(LinkOption.NOFOLLOW_LINKS);
        System.out.println(realPath.toString());
        String originalPath = "d:\\data\\projects\\a-project\\..\\another-project";
        Path path1 = Paths.get(originalPath);
        Path path2 = path1.normalize();
    }
}
```



# File

Java NIO 包提供了另一个名为`Files`的实用 API，它主要用于通过其静态方法操作文件和目录，这些方法大多作用于`Path`对象。

正如 Path 教程提到的，`Path`接口是在 Java 7 版本中引入 Java NIO 包的 file 包中的。因此，本教程也是针对同一个 file 包。

该类完全由操作文件、目录或其他类型文件的静态方法组成。在大多数情况下，在这里定义的方法将委托给关联的文件系统提供程序来执行文件操作。

`Files`类中定义了许多方法，也可以从 Java 文档中读取。在本教程中，我们尝试涵盖 Java NIO `Files`类所有方法中的一些重要方法。

## Files 类的重要方法

以下是 Java NIO `Files`类中定义的重要方法。

* `createFile(Path filePath, FileAttribute attrs)` − `Files`类提供此方法使用指定的`Path`创建文件。

## Example

```java
package com.java.nio;

import java.io.IOException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;

public class CreateFile {
    public static void main(String[] args) {
        //initialize Path
        Path path = Paths.get("D:file.txt");
        //create file
        try {
            Path createdFilePath = Files.createFile(path);
            System.out.println("Created a file at :createdFilePath);
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

## Output

Created a file at : D:\file.txt

* `copy(InputStream in, Path target, CopyOption)` − 此方法用于从指定的输入流复制到指定的目标文件，并返回读取或写入的字节数。`LinkOption`用于参数的值如下：
* `COPY_ATTRIBUTES` 将属性复制到新文件，例如最后修改时间。
* `REPLACE_EXISTING` 如果文件存在，则替换它。
* `NOFOLLOW_LINKS` 如果文件是符号链接，则复制链接本身而不是目标。

## Example

```java
package com.java.nio;

import java.io.IOException;
import java.nio.charset.Charset;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardCopyOption;
import java.util.List;

public class WriteFile {
    public static void main(String[] args) {
        Path sourceFile = Paths.get("D:file.txt");
        Path targetFile = Paths.get("D:fileCopy.txt");
        try {
            Files.copy(sourceFile, targetFile, StandardCopyOption.REPLACE_EXISTING);
        } catch (IOException ex) {
            System.err.format("I/O Error when copying file");
        }
        Path wiki_path = Paths.get("D:fileCopy.txt");
        Charset charset = Charset.forName("ISO-8859-1");
        try {
            List<String> lines = Files.readAllLines(wiki_path, charset);
            for (String line : lines) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

欢迎来到 file。

* `size(Path path)` — 此方法用于获取指定路径的文件的大小（单位为字节）。
* `write(Path path, byte[] bytes, OpenOption… options)` — 此方法用于将字节数组写入指定路径的文件。

## 示例

```java
package com.java.nio;

import java.io.IOException;
import java.nio.charset.Charset;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.List;

public class WriteFile {
    public static void main(String[] args) {
        Path path = Paths.get("D:file.txt");
        String question = "To be or not to be?";
        Charset charset = Charset.forName("ISO-8859-1");
        try {
            Files.write(path, question.getBytes());
            List<String> lines = Files.readAllLines(path, charset);
            for (String line : lines) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

## 输出

To be or not to be?

# 异步文件通道

众所周知，Java NIO 支持并发和多线程，这允许我们同时处理不同的通道。因此，Java NIO 包中负责此项工作的 API 是`AsynchronousFileChannel`，它定义在 NIO channels 包下。因此，`AsynchronousFileChannel`的全限定名为`java.nio.channels.AsynchronousFileChannel`。

`AsynchronousFileChannel`与 NIO 的`FileChannel`类似，不同之处在于该通道允许文件操作异步执行，而不是像同步 I/O 操作那样（同步操作中线程会进入动作并等待直到请求完成）。因此，异步通道供多个并发线程安全使用。

在异步模式下，请求由线程传递给操作系统内核执行，而线程继续处理其他任务。一旦内核完成任务，它会向线程发送信号，然后线程确认信号并中断当前任务，根据需要处理 I/O 任务。

为了实现并发，该通道提供了两种方法：一种是返回一个`java.util.concurrent.Future`对象，另一种是向操作传递一个类型为`java.nio.channels.CompletionHandler`的对象。

我们将通过示例逐一理解这两种方法。

* `Future 对象` — 在这种方法中，通道返回`Future`接口的实例。`Future`接口中有一个`get()`方法，它返回异步处理的操作状态，根据该状态可以决定其他任务的后续执行。我们还可以通过调用其`isDone`方法来检查任务是否完成。

## 示例

以下示例展示了如何使用 Future 对象并异步执行任务。

```java
package com.java.nio;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.AsynchronousFileChannel;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;
import java.util.concurrent.ExecutionException;
import java.util.concurrent.Future;

public class FutureObject {
    public static void main(String[] args) throws Exception {
        readFile();
    }

    private static void readFile() throws IOException, InterruptedException, ExecutionException {
        String filePath = "D:fileCopy.txt";
        printFileContents(filePath);
        Path path = Paths.get(filePath);
        AsynchronousFileChannel channel = AsynchronousFileChannel.open(path, StandardOpenOption.READ);
        ByteBuffer buffer = ByteBuffer.allocate(400);
        Future<Integer> result = channel.read(buffer, 0);  // position = 0
        while (! result.isDone()) {
            System.out.println("Task of reading file is in progress asynchronously.");
        }
        System.out.println("Reading done: " + result.isDone());
        System.out.println("Bytes read from file: " + result.get());
        buffer.flip();
        System.out.print("Buffer contents: ");
        while (buffer.hasRemaining()) {
            System.out.print((char) buffer.get());
        }
        System.out.println(" ");
        buffer.clear();
        channel.close();
    }

    private static void printFileContents(String path) throws IOException {
        FileReader fr = new FileReader(path);
        BufferedReader br = new BufferedReader(fr);
        // ... logic omitted for brevity as per core content
    }
}
```

## 输出

Task of reading file is in progress asynchronously.
Task of reading file is in progress asynchronously.
Reading done: true
Bytes read from file: 
Buffer contents: 

Reading done: true
Bytes read from file: 

## Completion Handler

以下示例展示了如何使用 CompletionHandler 异步执行任务。

```java
package com.java.nio;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.AsynchronousFileChannel;
import java.nio.channels.CompletionHandler;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;

public class CompletionHandlerDemo {
    public static void main(String[] args) throws Exception {
        writeFile();
    }

    private static void writeFile() throws IOException {
        String input = "Content to be written to the file.";
        System.out.println("Input string: " + input);
        byte[] byteArray = input.getBytes();
        ByteBuffer buffer = ByteBuffer.wrap(byteArray);
        Path path = Paths.get("D:fileCopy.txt");
        AsynchronousFileChannel channel = AsynchronousFileChannel.open(path, StandardOpenOption.WRITE);
        CompletionHandler handler = new CompletionHandler() {
            @Override
            public void completed(Object result, Object attachment) {
                System.out.println(attachment + " completed and " + result + " bytes are written.");
            }

            @Override
            public void failed(Throwable exc, Object attachment) {
                System.out.println(attachment + " failed with exception:");
                exc.printStackTrace();
            }
        };
        channel.write(buffer, 0, "Async Task", handler);
        channel.close();
        printFileContents(path.toString());
    }

    private static void printFileContents(String path) throws IOException {
        FileReader fr = new FileReader(path);
        BufferedReader br = new BufferedReader(fr);
        String textRead = br.readLine();
        System.out.println("File contents: ");
        while (textRead != null) {



`System.out.println(" " + textRead);`

`textRead = br.readLine();`

`fr.close();`

`br.close();`

## 输出

Input string: Content to be written to the file.
Async Task completed and 34 bytes are written.
File contents:

 Content to be written to the file.

# 字符集

在 Java 中，每个字符都有一个定义的 Unicode 代码单元，这些由 JVM 内部处理。因此，Java NIO 包定义了一个名为 `Charset` 的抽象类，主要用于字符集和 Unicode 的编码与解码。

## 标准字符集

Java 支持的字符集列如下：

* `US-ASCII` — 七位 ASCII 字符。
* `ISO-8859-1` — ISO 拉丁字母。
* `UTF-8` — 这是一种 8 位 UCS 转换格式。
* `UTF-16BE` — 这是一个大端字节序的 16 位 UCS 转换格式。
* `UTF-16LE` — 这是一个小端字节序的 16 位 UCS 转换格式。
* `UTF-16` — 16 位 UCS 转换格式。

## `Charset` 类的重要方法

* `forName()` — 该方法为指定的字符集名称创建一个字符集对象。该名称可以是规范名称，也可以是别名。
* `displayName()` — 该方法返回给定字符集的规范名称。
* `canEncode()` — 该方法检查指定的字符集是否支持编码。
* `decode()` — 该方法将给定字符集的字符串解码为 Unicode 字符集的 `charbuffer`。
* `encode()` — 该方法将 Unicode 字符集的 `charbuffer` 编码为指定字符集的字节缓冲区（byte buffer）。

## 示例

以下示例说明了 `Charset` 类的重要方法。

```java
package com.java.nio;

import java.nio.ByteBuffer;
import java.nio.CharBuffer;
import java.nio.charset.Charset;

public class CharsetExample {
    public static void main(String[] args) {
        Charset charset = Charset.forName("US-ASCII");
        System.out.println(charset.displayName());
        System.out.println(charset.canEncode());
        String str = "Demo text for conversion.";
        //将给定字符集中的字节缓冲区转换为 unicode 的字符缓冲区
        ByteBuffer byteBuffer = ByteBuffer.wrap(str.getBytes());
        CharBuffer charBuffer = charset.decode(byteBuffer);
        //将 unicode 的字符缓冲区转换为给定字符集中的字节缓冲区
        ByteBuffer newByteBuffer = charset.encode(charBuffer);
        while(newbb.hasRemaining()){
            char ch = (char) newByteBuffer.get();
            System.out.print(ch);
        }
        newByteBuffer.clear();
    }
}
```

## 输出

US-ASCII

Demo text for conversion.

# 文件锁 (File Lock)

众所周知，Java NIO 支持并发和多线程，这使得它能够处理同时在多个文件上操作的多个线程。但在某些情况下，我们要求文件不会被任何线程共享并变得不可访问。

对于这种需求，NIO 再次提供了名为 `FileLock` 的 API，它用于对整个文件或文件的部分提供锁，以便文件或其部分不会被共享或访问。

为了提供或应用此类锁，我们必须使用 `FileChannel` 或 `AsynchronousFileChannel`，它们为此提供了两个方法：`lock()` 和 `tryLock()`。提供的锁可能有两种类型——

* `排斥锁 (Exclusive Lock)` — 排斥锁防止其他程序获取任何类型的重叠锁。
* `共享锁 (Shared Lock)` — 共享锁防止其他并发运行的程序获取重叠的排斥锁，但允许它们获取重叠的共享锁。

用于获取文件上锁的方法——

* `lock()` — `FileChannel` 或 `AsynchronousFileChannel` 的此方法获取与给定通道关联的文件的排斥锁。该方法的返回类型为 `FileLock`，进一步用于监控获取的锁。
* `lock(long position, long size, boolean shared)` — 该方法是 `lock` 方法的重载版本，用于锁定文件的特定部分。
* `tryLock()` — 该方法尝试在此通道的文件上获取显式的排斥锁，如果无法获取锁则返回 null。
* `tryLock(long position, long size, boolean shared)` — 该方法尝试获取此通道文件指定区域的锁，该锁可以是排斥类型，也可以是共享类型。

## `FileLock` 类的方法

* `acquiredBy()` — 该方法返回获取文件锁的通道。
* `position()` — 该方法返回被锁定区域的第一个字节在文件中的位置。锁定区域不需要包含在实际的底层文件中，甚至不需要与其重叠，因此该方法返回的值可能会超过文件当前的大小。
* `size()` — 该方法返回锁定区域的大小（以字节为单位）。锁定区域不需要包含在实际的底层文件中，甚至不需要与其重叠，因此该方法返回的值可能会超过文件当前的大小。
* `isShared()` — 该方法用于判断锁是否为共享锁。
* `overlaps(long position,long size)` — 该方法告知此锁是否与给定的锁范围重叠。
* `isValid()` — 该方法告知获取的锁是否有效。锁对象在释放或关联的文件通道关闭之前一直有效，以先发生者为准。
* `release()` — 释放获取的锁。如果锁对象有效，则调用此方法将释放锁并使对象无效。如果此锁对象无效，则调用此方法将没有影响。
* `close()` — 该方法调用 `release()` 方法。将其添加到类中是为了可以与自动资源管理结构结合使用。

## 显示文件锁的示例

以下示例对文件创建锁并向其写入内容

```java
package com.java.nio;

import java.io.IOException;
import java.nio.ByteBuffer;
import java.nio.channels.FileChannel;
import java.nio.channels.FileLock;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.nio.file.StandardOpenOption;

public class FileLockExample {
    public static void main(String[] args) throws IOException {
        String input = "Demo text to be written in locked mode.";
        System.out.println("Input string to the test file is: " + input);
        ByteBuffer buf = ByteBuffer.wrap(input.getBytes());
        String fp = "D:file.txt";
        Path pt = Paths.get(fp);
        FileChannel channel = FileChannel.open(pt, StandardOpenOption.WRITE,StandardOpenOption.APPEND);
        channel.position(channel.size() - 1);   //将光标移动到文件末尾
        FileLock lock = channel.lock();
        System.out.println("The Lock is shared: " + lock.isShared());
        channel.write(buf);
        channel.close();  //释放锁
        System.out.println("Content Writing is complete. Therefore close the channel and release the lock.");
        PrintFileCreated.print(fp);
    }
}
```

```java
package com.java.nio;

import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class PrintFileCreated {
    public static void print(String path) throws IOException {
        FileReader filereader = new FileReader(path);
        BufferedReader bufferedreader = new BufferedReader(filereader);
        String tr = bufferedreader.readLine();
        System.out.println("The Content of testout.txt file is: ");
        while (tr != null) {
            System.out.println(" " + tr);
            tr = bufferedreader.readLine();
        }
        filereader.close();
        bufferedreader.close();
    }
}
```
