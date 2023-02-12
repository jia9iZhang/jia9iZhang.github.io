---
layout: mypost
title: "Charles抓包遇到Not allowed POST connection dropped"
date: 2022-03-11
categories: "2022"
tags: charles
---

***本地环境配置***

> Charles: v4.6.2

***问题发现***

是因为不小心在Charles中配置了白名单，而访问的地址又不在白名单内导致的.

***问题解决***

Allow list setting中取消勾选*关闭白名单*.

- 路径: ``tools --> Allow list setting``
<img src="{{site.url}}/img/image-20230109152319520.png" style="zoom:50%;" align="left">