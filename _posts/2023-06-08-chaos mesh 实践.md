---
layout: mypost
title: "chaos mesh实践"
date: 2023-03-30
categories: "linux"
tags: 2023
---

# Minkube 安装 chaos mesh

启动 minikube
```bash
minikube start
```

创建 chaos mesh命名空间
```bash
kubectl create ns chaos-mesh
```

helm安装 chaos mesh
```bash
helm install chaos-mesh chaos-mesh/chaos-mesh -n=chaos-mesh
```

验证 chaos mesh安装
```bash
kubectl get po -n chaos-mesh
```

开启 Chaos Mesh dashboard
```bash
kubectl port-forward -n chaos-mesh svc/chaos-dashboard 2333:2333
```



参考文档：https://chaos-mesh.org/zh/docs/