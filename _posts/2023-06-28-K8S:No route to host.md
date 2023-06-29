---
layout: mypost
title: "K8S:No route to host.."
date: 2023-06-15
categories: "k8s"
tags: 2023
---

当我们的Service A 调用第三方 Service B 时，此时Service B 在滚动发布。生产环境的业务日志告警会报出一条错误信息：`No route to host (Host unreachable) executing POST http://***/**/query**`



参考：

- [Kubernetes 疑难排查分享: 诡异的 No route to host](https://tencentcloudcontainerteam.github.io/2019/12/15/no-route-to-host/)
- [kube-proxy ipvs conn_reuse_mode setting causes errors with high load from single client #81775](https://github.com/kubernetes/kubernetes/issues/81775)
