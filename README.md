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
| `images/kubernetes-architecture.png` | Kubernetes 整体架构：Control Plane 与 Worker Node | `Kubernetes-架构组件清单.md` |
| `images/etcd-in-kubernetes.png` | etcd 在 Kubernetes 架构中的位置 | `Kubernetes核心基石-etcd.md` |
| `images/pod-network-ip-per-pod.png` | Pod 网络模型：每个 Pod 一个 IP | `Kubernetes网络.md` |
| `images/pod-structure.png` | Pod 结构：容器运行环境 + 一个或多个容器 | `Pod.md` |
| `images/pod-internal-containers.png` | Pod 内容器之间通过 localhost 通信 | `网络通讯.md` |

## 更新方式

把新图片放到 `images/` 目录，然后：

```bash
cd D:\06_Study\study-kubernetes-img
git add .
git commit -m "add: 新图片"
git push
```

> 注意：新增图片后 jsDelivr 需要几分钟刷新缓存，可用 `https://cdn.jsdelivr.net/gh/zxiny343/study-kubernetes-img@<commit-sha>/...` 立即拿到新图。
