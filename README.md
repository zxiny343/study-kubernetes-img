# study-kubernetes-img

`study-kubernetes` 学习笔记的专用图床仓库。

图片通过 **jsDelivr CDN** 分发，国内可直连访问（`raw.githubusercontent.com` 在部分网络下不可达，因此不使用 raw 链接）。

## 使用方法

```
https://cdn.jsdelivr.net/gh/zxiny343/study-kubernetes-img@main/images/<文件名>
```

- `@main` 也可以用具体 commit SHA 或 tag 替换，得到永久不变的链接
- 仓库必须是 **public**，jsDelivr 才能读取
- 新推的图片大概几分钟内生效（jsDelivr 有缓存）

## 图片清单

| 文件名 | 说明 | 用于笔记 |
| --- | --- | --- |
| `images/kubernetes-architecture.png` | Kubernetes 整体架构：Control Plane 与 Worker Node | `01-08 Kubernetes 是什么`（原始稿：架构组件清单） |
| `images/etcd-in-kubernetes.png` | etcd 在 Kubernetes 架构中的位置 | `02-03 etcd 与集群数据`（原始稿） |
| `images/pod-network-ip-per-pod.png` | Pod 网络模型：每个 Pod 一个 IP | `06-01 网络模型与三层网络`（原始稿） |
| `images/pod-structure.png` | Pod 结构：容器运行环境 + 一个或多个容器 | `03-01 Pod 基础与结构`（原始稿） |
| `images/pod-internal-containers.png` | Pod 内容器之间通过 localhost 通信 | `06-03 Pod 通信的七种路径`（原始稿） |
| `images/01-02-proc-pid-ns-list.png` | `ls /proc/<pid>/ns`：查看进程的六类 namespace | `01-02 容器隔离：namespace 六类视图` |
| `images/01-03-cgroup-memory-limit-oom-flow.png` | cgroup 内存上限到 OOMKill 的完整流程 | `01-03 资源限制：cgroups` |
| `images/01-04-overlayfs-merged-upper-lower.png` | OverlayFS 结构：lowerdir / upperdir / merged | `01-04 容器文件系统：镜像分层与可写层` |
| `images/01-04-image-layers-shared-across-containers.png` | 镜像层在多个容器间共享，磁盘只存一份 | `01-04 容器文件系统：镜像分层与可写层` |
| `images/01-06-unshare-version.png` | 验证 unshare 是否安装 | `01-06 从 docker run 到容器进程` |
| `images/01-06-readlink-pid-ns-before.png` | `readlink /proc/$$/ns/pid`：查看当前 PID namespace | `01-06 从 docker run 到容器进程` |
| `images/01-06-ps-ef-grep-bash.png` | 宿主机视角看到新 bash 进程 | `01-06 从 docker run 到容器进程` |
| `images/01-06-unshare-uts-hostname.png` | uts namespace 内的 hostname 隔离 | `01-06 从 docker run 到容器进程` |
| `images/01-06-cat-cpu-cfs-quota.png` | 查看 cgroup 的 CPU 配额 | `01-06 从 docker run 到容器进程` |
| `images/01-06-mkdir-cgroup-container-demo.png` | 创建 CPU 实验 cgroup | `01-06 从 docker run 到容器进程` |
| `images/01-06-cpu-cfs-quota-set.png` | 设置 CPU 配额后的文件内容 | `01-06 从 docker run 到容器进程` |
| `images/01-06-cgroup-tasks-pid.png` | `cat tasks`：查看被移入 cgroup 的进程 | `01-06 从 docker run 到容器进程` |
| `images/01-06-top-cpu-usage.png` | top 观察进程 CPU 使用率被限制 | `01-06 从 docker run 到容器进程` |
| `images/01-06-cpu-stat-throttled.png` | cpu.stat 中的限流统计 | `01-06 从 docker run 到容器进程` |
| `images/01-06-memory-cgroup-ls.png` | 内存实验 cgroup 的控制文件 | `01-06 从 docker run 到容器进程` |
| `images/01-06-memory-oom-status-1.png` | 查看 memory cgroup 的 OOM 状态（一） | `01-06 从 docker run 到容器进程` |
| `images/01-06-memory-oom-status-2.png` | 查看 memory cgroup 的 OOM 状态（二） | `01-06 从 docker run 到容器进程` |

## 更新方式

把新图片放到 `images/` 目录，然后：

```bash
cd D:\06_Study\study-kubernetes-img
git add .
git commit -m "add: 新图片"
git push
```

> 注意：新增图片后 jsDelivr 需要几分钟刷新缓存，可用 `https://cdn.jsdelivr.net/gh/zxiny343/study-kubernetes-img@<commit-sha>/...` 立即拿到新图。
