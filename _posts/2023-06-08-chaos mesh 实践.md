---
layout: mypost
title: "chaos mesh实践"
date: 2023-03-30
categories: "linux"
tags: 2023
---

# Minkube 安装 chaos mesh

参考：[chaos mesh官方文档](https://chaos-mesh.org/zh/docs/)

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

访问地址：http://localhost:2333/dashboard



# 模拟 Pod 故障

进入 Chaos mesh Dashboard。创建一次实验。

本次 Chaos 详细信息：

![image-20230612150409274](../img/image-20230612150409274.png)

```yml
kind: PodChaos
apiVersion: chaos-mesh.org/v1alpha1
metadata:
  namespace: default
  name: example.com
  annotations:
    experiment.chaos-mesh.org/pause: 'true'
spec:
  selector:
    namespaces:
      - default
    labelSelectors:
      app: hellok8s
  mode: one
  action: pod-failure
```

运行结果：

运行 chaos

![image-20230612150008699](../img/image-20230612150008699.png)

结果：

![image-20230612150021628](../img/image-20230612150021628.png)



暂停chaos：

![image-20230612150040796](../img/image-20230612150040796.png)

结果：

![image-20230612150054841](../img/image-20230612150054841.png)



参考：[模拟 Pod 故障](https://chaos-mesh.org/docs/simulate-pod-chaos-on-kubernetes/)
