# Blockchain文献参考

## 内容

[1.2020](#2020)

- [[C]ICBC(IEEE International Conference on Blockchain and Cryptocurrency)](#[C]ICBC)
- [[C]COMPSAC(International Computer Software and Applications Conference)](#[C]COMPSAC)
- [[C]IJCAI(International Joint Conference on Artificial Intelligence)](#[J]IEEE Netw)
- [[J]IEEE Netw(IEEE Network)](#[J]IEEE Netw)

[2.2019](#2019)

- [ArXiv](#ArXiv)
- [[C]NDSS(Network and Distributed System Security Symposium)](#[C]NDSS)

## 数据集



## <span id="2020">2020</span>

### [C]ICBC

#### A Controlled Natural Language to Support Intent-based Blockchain Selection

机构：苏黎世大学

作为加密货币的底层，区块链技术一直是一个流行的方向。各个方面都有着对区块链的实际应用，但需要对区块链的底层有一定的技术了解。为了让非技术人员也能选择合适的区块链解决实际问题，本文提出了一种受控制自然语言来扩展选择方案，提出了基于EBNF的意图表达方式，并通过状态机来分析用户意图，找到最适合用户意愿场景的区块链。

方法本身比较简单，但提供了一个区块链与自然语言结合的思路，可以依靠机器学习或者人工智能技术完成更智能的意图分析。

### [C]COMPSAC

会议概述：软件工程CCFC类的会议，虽然等级不高，但对论文的完整性要求还是很高的

#### Smart Contracts Vulnerability Auditing with Multi-semantics

机构：香港城市大学

区块链上智能合约的漏洞审核至关重要，当前数据驱动的主要方法为将智能合约的代码以一个标准的序列化为一个token序列，然后再进行审核，但这样忽视了代码的连贯性，上下文信息无法体现，基于此本文提出了基于n-gram模型的方式捕获上下文信息，并使用组合策略完成审核工作。

该工作应用于以太坊超过7200个智能合约样品上，达到了超过50%的检测效率。

### [C]IJCAI

#### Smart Contract Vulnerability Detection Using Graph Neural Networks

机构：浙江工商大学

导师：刘振广

现有的智能合约漏洞检测方法严重依赖专家规则，导致检测率较低。本文采用了利用图神经网络进行漏洞检测的方法。主要的贡献点为  设计了一个基于合约代码的构造图过程，使用DG-GCN（他人提出）和TMP（时态消息传播网络，本文提出）来对合约进行漏洞检测。

### [J]IEEE Netw

期刊概述：顶刊，中科院分区1区

#### Smart Contract Vulnerability Analysis and Security Audit

类似综述论文，以太坊上智能合约的漏洞研究引起了广泛关注，论文对未检查发送漏洞（unchecked send/other functIon call）、重入攻击（reentrancy vulnerabilities）、权限控制漏洞（permission control vulnerabilites）、函数可见性漏洞（function visibility vulnerabilites）、时间戳依赖关系（timestamp dependency）、随机数漏洞（random number vulnerabilites）进行描述，并对现有的智能合约审计方法进行了总结，从不同角度对几种主流的审计工具进行了比较。

------------------------------------------------------------------------------------------

## <span id="2019">2019</span>

### ArXiv

#### Machine Learning in/for Blockchain: Future and Challenges

机构：普度大学

综述型论文，主要归纳了近两年将区块链与机器学习相结合的文章。文章介绍的很详细（包括区块链的基础原理），主要分传统机器学习、深度学习和强化学习三个部分进行描述。

- 传统机器学习：1.识别潜在的非法实体（理解为分类问题）；2.比特币价格预测（理解为回归问题）。
- 深度学习：1.构建去中心化的协作学习框架（合作共享数据集）；2.运算能力分配；3.数字货币价格预测（采用的RNN）。
- 强化学习：1.物联网数据收集、存储和处理的安全性；2.使用强化学习对货币投资的组合管理。

未来有许多可以值得研究的地方：

- 设计具有学习能力的"智能代理"来规范区块链。
- 通过大量的数据来评估分散结构的性能，并构造学习模型进行预测。

### [C]NDSS

#### Sereum: Protecting Existing Smart Contracts Against Re-Entrancy Attacks

机构：杜伊斯堡-埃森大学，德国

区块链系统中的智能合约若出现了重大的错误和漏洞，会造成巨大的经济损失（DAO攻击事件），虽然许多文献给出了保护智能合约的建议，但这些建议大多数集中在证明合同中特定类型的漏洞的正确性或不存在，但不能对已经部署的合约进行保护。基于此，本文以攻击为背景，提出了一种新的智能合约安全技术sereum(secure etherum)，以向后兼容的方式保护已部署的现有合同不受重入攻击的影响。





