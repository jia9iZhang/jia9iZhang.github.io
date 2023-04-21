---
layout: mypost
title: "为什么服务间调用使用gRPC+PB,而不使用HTTP+JSON?"
date: 2023-03-30
categories: "http"
tags: 2023
---

分布式服务间的通信更注重性能。对比其二者特性可以看出：

HTTP+gRPC:

- Http和 gRPC都是是标准的请求-响应模型。
- gRPC是数据传输基于二进制格式的，在网络传输的速度和效率更高。HTTP的数据传输是二进制的，但是HTTP报文是基于文本的。在这方面性能就不如 gRPC了。

PB和 JSON：

- Protobuf 在服务器和客户端上可以非常快速地序列化。

- PB的二进制格式更紧凑，可以提供更高效的传输和存储。而 XML 和 JSON 等文本格式需要使用更多的字符和标记来表示同样的数据，在传输时会产生更大的数据体积和传输延迟。

所以分布式服务间的通信更多使用gRPC+PB。



#### 参考

- [比较 gRPC 服务和 HTTP API](https://learn.microsoft.com/zh-cn/aspnet/core/grpc/comparison?view=aspnetcore-6.0)

为什么客户端-服务端交互使用 Http+JSON?而不使用 gRPC+PB?

//TODO