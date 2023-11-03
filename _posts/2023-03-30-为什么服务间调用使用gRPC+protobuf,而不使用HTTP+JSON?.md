---
layout: mypost
title: "为什么服务间调用使用gRPC+protobuf,而不使用HTTP+JSON?"
date: 2023-03-30
categories: "http"
tags: 2023
---

分布式服务间的通信更注重性能。对比其二者特性可以看出：

使用 gRPC+protobuf（pb）相对于 HTTP+JSON 有以下的优点：

1. 更高效的数据传输：gRPC 使用 Protocol Buffers（protobuf）进行数据序列化，使得数据传输更为高效。Protocol Buffers 是一种轻量级、高效的二进制序列化格式，可以将数据以高度压缩的形式序列化，从而减少网络传输和存储空间。
2. 更快的速度：由于 gRPC 使用基于 HTTP/2 的协议，可以实现双向流（stream）和消息头压缩等功能，可以显著提高客户端和服务端之间的通信效率，因此在性能方面比 HTTP+JSON 更快。
3. 更强的类型检查：gRPC 使用 protobuf 定义接口和消息的结构，因此可以提供更强的类型检查，避免因为数据类型不匹配导致的运行时错误。
4. 易于扩展：gRPC 使用 protobuf 来定义接口和消息的结构，可以通过简单地修改 .proto 文件来添加或删除 API 的方法和参数，因此可以更容易地扩展和维护服务。
5. 可插拔的架构：gRPC 支持多种语言，并且可以使用插件来支持不同的负载均衡、认证和其他功能。这使得 gRPC 成为一个非常灵活可扩展的通信框架，适用于各种场景。

HTTP+JSON 的优点包括：

1. 易于理解和调试：由于 HTTP+JSON 是一种基于文本的协议，因此更容易理解和调试。可以使用浏览器或者 curl 等工具来测试 API 是否正确。
2. 可以通过 RESTful 架构实现简单的 API 设计：RESTful 架构使得 API 的设计更为简单清晰，易于理解和使用。
3. 更加广泛的支持：由于 HTTP+JSON 是一种标准协议，因此可以被任何支持 HTTP 协议的语言和框架使用，包括 Java、JavaScript、Python、PHP 等常用的编程语言。

HTTP+JSON 的缺点包括：

1. 较低的性能：由于 HTTP+JSON 使用文本格式传输数据，并且需要进行解析和序列化，因此在性能方面不如 gRPC+protobuf。
2. 类型检查不如 gRPC+protobuf 强：由于 HTTP+JSON 是一种基于文本的协议，无法提供像 protobuf 这样的强类型检查。
3. 难以实现流式数据传输：由于 HTTP 协议本身不支持双向流式数据传输，因此难以实现像 gRPC 那样的双向流式通信方式。
4. 客户端和服务端之间的通信需要自行协商，没有像 gRPC 那样明确的 API 规范。
5. 不够灵活：由于 HTTP+JSON 是一种基于文本的协议，因此在多语言支持、插件扩展等方面不如 gRPC+protobuf 灵活。

#### 参考

- [比较 gRPC 服务和 HTTP API](https://learn.microsoft.com/zh-cn/aspnet/core/grpc/comparison?view=aspnetcore-6.0)
