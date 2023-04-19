---
layout: mypost
title: "SonarQube提示ES集群启动失败"
date: 2022-04-17
categories: "sonar"
tags: 2022
---

***本地环境配置***

>System: Ubuntu 18.04 LTS
>
>SonarQube: 8.9.10 LTS

***问题发现***

错误信息：``max virtual memory areas vm.max_map_count [65530] is too low, increase to at least [262144]``
<img src="{{site.url}}/img/image-20230109152001736.png" style="zoom:50%;">

***解决方案***

- 配置 /etc/sysctl.conf文件, 添加配置 vm.max_map_count=262144

- 使用命令 sysctl -p ,让配置立即生效
<img src="{{site.url}}/img/image-20230109152017634.png" style="zoom:50%;">
- 重启SonarQube, 成功运行
<img src="{{site.url}}/img/image-20230109152027646.png" style="zoom:50%;">

