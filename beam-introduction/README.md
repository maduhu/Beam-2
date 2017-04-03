# MillWheel介绍

MillWheel是Google内部研发的实时流数据处理系统，具有分布式，低延迟，高可用，支持一次语义的特点。不出意外，MillWheel是Google强大的基础结构和强大的engeering能力的综合体现 - 利用Bigtable / Spanner作为后备状态存储，保证一次特性等等。另外，MillWheel将水印机制发扬光大，对事件时间有着非常好的支持。推荐对流系统感兴趣的朋友一定多读几遍这篇论文 - 虽然这个已经发表了几年，但工业界开源的系统尚未完全达到MillWheel的水平。

## MillWheel论文

本文介绍了MillWheel的编程模型及其实现。 连续异常检测器的案例，可以激活MillWheel的规模使用。 MillWheel的编程模型提供了一个逻辑时间的概念，使得编写基于时间的聚合变得容易。
MillWheel从一开始就设计了容错性并考虑到可扩展性。 在实践中，我们发现MillWheel的
可扩展性，容错性和多功能性的独特组合
编程模式适用于谷歌内部的各种各样问题。

## MillWheel介绍

流处理系统提供的内容对于用户来说至关重要，允许组织做出更快更好的决策，
特别是因为它们提供低延迟的能力结果。 用户需要关于他们周围世界的实时新闻。
企业同样对实时提供的信息价值感兴趣，如股票价格变动、入侵检测。
同样，科学家们必须从实时的原始数据流中找出有价值的结果。

Google的流处理系统需要容错、持久化状态和可扩展性。分布式系统运行在数千个共享上
机器，任何一个都可以随时失效。 基于模型的流处理系统，如异常检测器，依赖于数星期数据的预测，其模型必须随着新数据流入更新，通过命令来扩展这些系统规模不应该导致业务的相应增加
构建和维护系统的成本。

分布式系统的编程模型，如MapReduce，在后台隐藏框架的实现细节。允许用户构建大规模分布式系统
是比较简单的。 而用户仅专注于他们的应用程序逻辑，这种编程模型允许用户推理
他们系统的语义而不需要分布式系统专家帮助。特别是，用户能够依赖于框架级别
正确性和容错保障，极大地限制了错误和错误可以显示的区域。支持各种常见的编程语言
，用户可以利用工具和方便地使用现有的库，而不是受限制的DSL语言。

















































