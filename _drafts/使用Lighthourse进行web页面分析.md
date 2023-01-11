# 使用Lighthourse进行web页面分析

介绍:

- 官方仓库:https://github.com/GoogleChrome/lighthouse

生命周期:

Lighthouse 运行测评的过程有一套完整的生命周期，可以划分成三个主要流程：

**Collecting（收集数据）：**首先是 Collecting 流程，这一步会调用内置的驱动程序（Driver） ，其作用是通过谷歌开发工具协议（ Chrome DevTools Protocol） 调起浏览器，并创建新的 tab 请求待测评的站点，通过浏览器采集站点数据并将结果（称之为 Artifacts）保存在本地临时目录。

**Auditing（分析数据）：**然后进入 Auditing 流程，读取 Artifacts 数据，根据内置的评判策略逐条进行检查并计算出各项的数字形式得分。

**Report（生成报告）：**最后进行 Report 流程，将评分结果按照 PWA、性能、无障碍访问、最佳实践等纬度进行划分，以 JSON、HTML 等格式输出。

指标分析:

- 性能（Performance）

- 访问无障碍（Accessibility）

- 最佳实践（Best Practice）

- 搜索引擎优化（SEO）

- PWA（Progressive Web App)
  - Google给出的PWA的基准线[Progressive Web App Checklist](https://developers.google.cn/web/progressive-web-apps/checklist)

