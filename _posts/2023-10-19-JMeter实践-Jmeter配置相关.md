---
layout: mypost
title: "JMeter实践-Jmeter配置相关"
date: 2023-10-19
categories: "JMeter"
tags: 2023
---

# Jmeter配置相关

## 更改输出报告中的时间粒度

在 Jmeter 压测完成后生成的报告中默认的时间粒度为 1 分钟。如图：

![image-20231020171141891]({{site.url}}/img/image-20231020171141891.png)

我们想将时间跨度配置的更久一点，修改"/bin/reportgenerator.properties"文件中配置项：jmeter.reportgenerator.overall_granularity。单位：毫秒

![image-20231020171435610]({{site.url}}/img/image-20231020171435610.png)
