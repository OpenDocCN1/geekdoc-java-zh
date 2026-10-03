
# Docker-Compose 和 Kubernetes 的区别

> 原文：[https://web.archive.org/web/20220921135705/https://www.baeldung.com/ops/docker-compose-vs-kubernetes](https://web.archive.org/web/20220921135705/https://www.baeldung.com/ops/docker-compose-vs-kubernetes)

## 1. 概观

在处理容器化的应用程序时，我们可能想知道 `Docker Compose` 和 `Kubernetes` 在这种情况下扮演什么角色。

在本教程中，我们将讨论一些最常见的用例，以了解两者之间的区别。

## 2. Docker Compose

**`Docker Compose`** 是一个命令行工具，使用 `YAML` 模板定义运行多个 `Docker` 容器。我们可以从现有的镜像或特定的上下文中构建容器。

我们可以添加一个 Compose 文件格式的 `version` 和至少一个 `service`。可选地，我们可以添加 `volumes` 和 `networks`，我们还可以定义依赖关系和环境变量。

### 2.1. Docker Compose 模板

让我们为连接到 `PostgreSQL` 数据库的 `API` 创建一个 `docker-compose.yml` 文件：

```yaml
version: '3.8'
services:
  db:
    image: postgres:latest
    restart: always
    environment:
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=postgres
    ports:
      - '5432:5432'
    volumes: 
      - db:/var/lib/postgresql/data
    networks:
      - mynet

  api:
    container_name: my-api
    build:
      context: ./
    image: my-api
    depends_on:
      - db
    networks:
      - mynet
    ports:
      - 8080:8080
    environment:
      DB_HOST: db
      DB_PORT: 5432
      DB_USER: postgres
      DB_PASSWORD: postgres
      DB_NAME: postgres

networks:
  mynet:
    driver: bridge

volumes:
  db:
    driver: local
```

最后，我们可以通过运行以下命令在本地或生产环境中开始工作：

```bash
docker-compose up
```

### 2.2. Docker Compose 常见用例

我们通常使用 `Docker Compose` 来创建一个通过网络链接不同服务的微服务基础设施环境。

此外，`Docker Compose` 广泛用于为我们的测试套件创建和销毁隔离的测试环境。

此外，如果我们对可伸缩性感兴趣，我们可以看看 `Docker Swarm`——`Docker` 创建的一个项目，像 `Kubernetes` 一样在编排级别工作。

然而，与 `Kubernetes` 相比，`Docker Swarm` 的产品有限。

## 3. Kubernetes

借助 **`Kubernetes`**（也称为 `K8s`），我们可以在容器化和集群化的环境中自动部署和管理应用。谷歌在 `K8s` 上的最初工作是从开源到捐赠给 `Linux 基金会`，最终作为种子技术启动了云本地计算基金会（`CNCF`）。

在容器时代，`Kubernetes` 得到了极大的关注，以至于它现在是最受欢迎的分布式系统编排器。

完整的 `API` 可用于描述 `Kubernetes` 对象的规格和状态。它还允许与第三方软件集成。

**在 `Kubernetes` 中，不同的组件是一个集群的一部分，该集群由一组名为 `Nodes` 的工作机组成。`Nodes` 在 `Pods` 内部运行我们的容器化应用。**

`Kubernetes` 是关于管理部署在虚拟机或裸机上的工件的。`Nodes` 和它们运行的容器都被分组为一个集群，每个容器都有端点、`DNS`、存储和可伸缩性。

`Pods` 是非永久性资源。例如，`Deployment` 可以动态地创建和销毁它们。通常，我们可以将应用程序公开为 `Services`，以便总是在同一个端点可用。

### 3.1. Kubernetes 模板

**`Kubernetes` 提供了一种声明式或命令式方法，因此我们可以使用模板来创建、更新、删除甚至缩放对象**。例如，让我们为一个 `Deployment` 定义一个模板：

```yaml
-- Postgres Database
apiVersion: apps/v1
kind: Deployment
metadata:
  name: postgresql
  namespace: Database
spec:
  selector:
    matchLabels:
      app: postgresql
  replicas: 1
  template:
    metadata:
      labels:
        app: postgresql
    spec:
      containers:
        - name: postgresql
          image: postgresql:latest
          ports:
            - name: tcp
              containerPort: 5432
          env:
            - name: POSTGRES_USER
              value: postgres
            - name: POSTGRES_PASSWORD
              value: postgres
            - name: POSTGRES_DB
              value: postgres
          volumeMounts:
        - mountPath: /var/lib/postgresql/data
          name: postgredb
      volumes:
        - name: postgredb
          persistentVolumeClaim:
            claimName: postgres-data

-- My Api
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-api
  namespace: Api
spec:
  selector:
    matchLabels:
      app: my-api
  replicas: 1
  template:
    metadata:
      labels:
        app: my-api
    spec:
      containers:
        - name: my-api
          image: my-api:latest
          ports:
            - containerPort: 8080
              name: "http"
          volumeMounts:
            - mountPath: "/app"
              name: my-app-storage
          env:
            - name: POSTGRES_DB
              value: postgres
            - name: POSTGRES_USER
              value: postgres
            - name: POSTGRES_PASSWORD
              value: password
          resources:
            limits:
              memory: 2Gi
              cpu: "1"
      volumes:
        - name: my-app-storage
          persistentVolumeClaim:
            claimName: my-app-data
```

然后我们可以用 `kubectl` 命令行在网络上使用对象。

### 3.2. Kubernetes 和云提供商

`Kubernetes` 本身并不是基础设施即代码（`IaC`）。然而，它与云提供商的容器服务相集成——例如，亚马逊的 `ECS` 或 `EKS`，谷歌的 `GKE`，以及 `RedHat` 的 `OpenShift`。

或者我们可以使用它，例如，和像 `Helm` 这样的工具一起使用。

我们确实经常在公共云基础架构中看到 `Kubernetes`。但是，我们可以建立一个 `Minikube` 或者一个本地的 `Kubeadm` 集群。

同样得到 `CNCF` 的批准，我们可以检查 `K8s` 的轻型版本 `K3s`。

## 4. Kubernetes 和 Docker Compose 之间的差异

虽然 `Docker Compose` 是关于创建和启动一个或多个容器，但 `Kubernetes` 更多的是作为一个平台来创建一个我们可以编排容器的网络。

`Kubernetes` 帮助解决了应用管理中的许多关键问题：

- 资源优化
- 容器的自我修复
- 应用程序重新部署期间的停机时间
- 自动缩放

最后，`Kubernetes` 将多个孤立的容器带到了一个阶段，在这个阶段，资源总是可用的，并具有潜在的最佳分布。

然而，当涉及到开发时，`Docker Compose` 可以配置所有应用程序的服务依赖项，以开始进行我们的自动化测试。所以，这是当地发展的有力工具。

## 5. 结论

在本文中，我们已经看到了 `Docker Compose` 和 `Kubernetes` 之间的区别。当我们需要定义和运行多容器 `Docker` 应用程序时，`Docker Compose` 可以提供帮助。

`Kubernetes` 是一个强大而复杂的框架，用于在集群环境中管理容器化的应用程序。
