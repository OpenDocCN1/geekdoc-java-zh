
# Kubernetes 与善良

> 原文：<https://web.archive.org/web/20220930061024/https://www.baeldung.com/ops/kubernetes-kind>

## 1. 概观

当使用 Kubernetes 时，我们缺少一个有助于本地开发的工具——一个可以使用 Docker 容器作为节点来运行本地 Kubernetes 集群的工具。

在本教程中，我们将探索 Kubernetes 与善良。`kind`（[链接](https://web.archive.org/web/20220926195301/https://kind.sigs.k8s.io/)）主要是 Kubernetes 的测试工具，对于本地开发和 CI 也很方便。

## 2. 设置

作为先决条件，我们应该确保 Docker 安装在我们的系统中。安装 Docker 的一个简单方法是使用适合我们操作系统（和处理器，在 macOS 的情况下）的 [Docker 桌面](https://web.archive.org/web/20220926195301/https://www.docker.com/products/docker-desktop)。

### 2.1. 安装 Kubernetes 命令行

首先，让我们[安装 Kubernetes 命令行`kubectl`](https://web.archive.org/web/20220926195301/https://kubernetes.io/docs/tasks/tools/)。在 macOS 上，我们可以使用自制软件安装它：

```bash
$ brew install kubectl
```

我们可以使用以下命令来验证安装是否成功：

```bash
$ kubectl version --client

Client Version: version.Info{Major:"1", Minor:"21", GitVersion:"v1.21.3", 
GitCommit:"ca643a4d1f7bfe34773c74f79527be4afd95bf39", GitTreeState:"clean", 
BuildDate:"2021-07-15T21:04:39Z", GoVersion:"go1.16.6", Compiler:"gc", Platform:"darwin/amd64"}
```

同样，我们可以使用`curl`在 Windows 上下载：

```bash
curl -LO https://dl.k8s.io/v1.21.0/bin/windows/amd64/kubectl.exe.sha256
```

然后，我们应该将`kubectl`命令的二进制位置添加到我们的`PATH`变量中。

### 2.2. 安装`kind`

接下来，我们将使用自制软件在 macOS 上安装`kind`：

```bash
$ brew install kind
```

要验证安装是否成功，我们可以尝试以下命令：

```bash
$ kind version
kind v0.11.1 go1.15.6 darwin/amd64
```

但是，如果`kind version`命令不起作用，请将其位置添加到`PATH`变量中。

同样，对于 Windows 操作系统，我们可以使用`curl`下载`kind`：

```bash
curl -Lo kind-windows-amd64.exe https://kind.sigs.k8s.io/dl/v0.11.1/kind-windows-amd64
Move-Item .\kind-windows-amd64.exe c:\kind\kind.exe
```

## 3. 不可思议的群集

现在，我们已经准备好使用 kind 为 Kubernetes 准备本地开发环境。

### 3.1. 创建集群

首先，让我们用默认配置创建一个本地 Kubernetes 集群：

```bash
$ kind create cluster
```

默认情况下，将创建一个名为`kind`的集群。但是，我们可以使用 `–name`参数为集群提供一个名称：

```bash
$ kind create cluster --name baeldung-kind
Creating cluster "baeldung-kind" ...
 ✓ Ensuring node image (kindest/node:v1.21.1) 🖼 
 ✓ Preparing nodes 📦  
 ✓ Writing configuration 📜 
 ✓ Starting control-plane 🕹️ 
 ✓ Installing CNI 🔌 
 ✓ Installing StorageClass 💾 
Set kubectl context to "kind-baeldung-kind"
You can now use your cluster with:
kubectl cluster-info --context kind-baeldung-kind
Thanks for using kind! 😊 
```

此外，我们可以使用 YAML 配置文件来配置集群。例如，让我们在`baeldungConfig.yaml`文件中编写一个简单的配置：

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1
name: baeldung-kind
```

然后，让我们使用配置文件创建集群：

```bash
$ kind create cluster --config baeldungConfig.yaml
```

此外，我们还可以在创建集群时提供特定版本的 Kubernetes 映像：

```bash
$ kind create cluster --image kindest/node:v1.20.7
```

### 3.2. 获取集群

让我们使用`get`命令检查创建的集群：

```bash
$ kind get clusters
baeldung-kind
```

此外，我们可以确认相应的 docker 容器：

```bash
$ docker ps
CONTAINER ID  IMAGE                 COMMAND                 CREATED    STATUS        PORTS                      NAMES
612a98989e99  kindest/node:v1.21.1  "/usr/local/bin/entr…"  1 min ago  Up 2 minutes  127.0.0.1:59489->6443/tcp  baeldung-kind-control-plane
```

或者，我们可以通过`kubectl`确认节点：

```bash
$ kubectl get nodes
NAME                          STATUS   ROLES                  AGE   VERSION
baeldung-kind-control-plane   Ready    control-plane,master   41s   v1.21.1
```

### 3.3. 集群详细信息

一旦集群准备就绪，我们可以使用`kubectl`上的`cluster-info`命令来检查细节：

```bash
$ kubectl cluster-info --context kind-baeldung-kind
Kubernetes master is running at https://127.0.0.1:59489
CoreDNS is running at https://127.0.0.1:59489/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
```

此外，我们可以使用`dump`参数和`cluster-info`命令来提取集群的详细信息：

```bash
$ kubectl cluster-info dump --context kind-baeldung-kind 
```

### 3.4. 删除集群

类似于`get`命令，我们可以使用`delete`命令删除特定的集群：

```bash
$ kind delete cluster --name baeldung-kind
```

## 4. 入口控制器

### 4.1. 安装配置

我们需要一个`ingress`控制器来建立本地环境和 Kubernetes 集群之间的连接。

因此，我们可以使用`kind`的配置选项，如`extraPortMappings`和`node-labels`：

```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
name: baeldung-kind
nodes:
- role: control-plane
  kubeadmConfigPatches:
  - |
    kind: InitConfiguration
    nodeRegistration:
      kubeletExtraArgs:
        node-labels: "ingress-ready=true"    
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP
  - containerPort: 443
    hostPort: 443
    protocol: TCP
```

这里，我们已经更新了我们的`baeldungConfig.yaml`文件来设置入口控制器的配置，将容器端口映射到主机端口。此外，我们通过定义`ingress-ready=true`为入口启用了节点。

然后，我们必须使用修改后的配置重新创建集群：

```bash
kind create cluster --config baeldungConfig.yaml
```

### 4.2. 部署

然后，我们将部署 Kubernetes 支持的[入口 NGINX 控制器](https://web.archive.org/web/20220926195301/https://git.k8s.io/ingress-nginx/README.md#readme)作为反向代理和负载平衡器：

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

此外，我们还可以使用 [AWS](https://web.archive.org/web/20220926195301/https://github.com/kubernetes-sigs/aws-load-balancer-controller#readme) 和 [GCE 负载平衡器](https://web.archive.org/web/20220926195301/https://git.k8s.io/ingress-gce/README.md#readme)控制器。

## 5. 在本地部署服务

最后，我们已经准备好部署我们的服务。对于本教程，我们可以使用一个简单的 [`http-echo` web 服务器作为 docker 镜像](https://web.archive.org/web/20220926195301/https://hub.docker.com/r/hashicorp/http-echo/)。

### 5.1. 安装配置

因此，让我们创建一个定义服务的配置文件，并使用 ingress 在本地托管它：

```yaml
kind: Pod
apiVersion: v1
metadata:
  name: baeldung-app
  labels:
    app: baeldung-app
spec:
  containers:
  - name: baeldung-app
    image: hashicorp/http-echo:0.2.3
    args:
    - "-text=Hello World! This is a Baeldung Kubernetes with kind App"
---
kind: Service
apiVersion: v1
metadata:
  name: baeldung-service
spec:
  selector:
    app: baeldung-app
  ports:
  # Default port used by the image
  - port: 5678
---
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: baeldung-ingress
spec:
  rules:
  - http:
      paths:
      - pathType: Prefix
        path: "/baeldung"
        backend:
          service:
            name: baeldung-service
            port:
              number: 5678
```

这里，我们创建了一个名为`baeldung-app`的 pod，带有`text`参数和一个名为`baeldung-service`的服务。

然后，我们在 5678 端口上通过`/baeldung` URI 建立到`baeldung-service`的入口网络。

### 5.2. 部署

现在我们已经准备好了所有的配置，并且我们的集群与 NGINX 控制器集成，让我们部署我们的服务：

```bash
$ kubectl apply -f baeldung-service.yaml
```

我们可以在`kubectl`上查看服务状态：

```bash
$ kubectl get services
NAME               TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)    AGE
baeldung-service   ClusterIP   10.96.172.116   <none>        5678/TCP   5m38s
kubernetes         ClusterIP   10.96.0.1       <none>        443/TCP    7m5s
```

就是这样！我们的服务已经部署，应该在 `localhost/baeldung`可用：

```bash
$ curl localhost/baeldung
Hello World! This is a Baeldung Kubernetes with kind App 
```

注意：如果我们遇到任何与`validate.nginx.ingress.kubernetes.io` webhook 相关的错误，我们应该删除`ValidationWebhookConfiguration`：

```bash
$ kubectl delete -A ValidatingWebhookConfiguration ingress-nginx-admission
validatingwebhookconfiguration.admissionregistration.k8s.io "ingress-nginx-admission" deleted
```

然后，再次部署服务。

## 6. 结论

在本文中，我们用`kind`探索了 Kubernetes。

首先，我们做了一个设置，包括安装 Kubernetes 命令行`kubectl`和`kind`。然后，我们研究了`kind`的一些特性，以创建/更新一个 Kubernetes 本地集群。

最后，我们集成了入口控制器，并在 Kubernetes 集群上部署了私有的可访问服务。
