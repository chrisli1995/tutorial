# Adversarial Examples文献参考

## 内容

[1.2020](#2020)

- [1.1 [J][C]ACL(Association for Computational Linguistics)](#[C]ACL(Association for Computational Linguistics))
- [1.2 [J]ACM Transactions on Intelligent Systems and Technology](#[J]ACM Transactions on Intelligent Systems and Technology)
- [1.3 [J]软件学报](#[J]软件学报)

[2.2019](#2019)

- [2.1 [C]NDSS(Network and Distributed System Security Symposium)](#[C]NDSS(Network and Distributed System Security Symposium))

## 数据集

![image.png](https://upload-images.jianshu.io/upload_images/7810235-5d28cd4dbd9daf56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

------------------------------------------------------------------------------------------



## <span id="2020">2020</span>

### <span id="[C]ACL(Association for Computational Linguistics)">[C]ACL(Association for Computational Linguistics)</span>

#### Attention Guided Graph Convolutional Networks for Relation Extraction

### <span id="[J]ACM Transactions on Intelligent Systems and Technology">[J]ACM Transactions on Intelligent Systems and Technology</span>

期刊概述：ISSN：2157-6904

SCI工程技术2区，三年平均IF：3.010

#### Adversarial Attacks on Deep Learning Models in Natural Language Processing A Survey(2020, 11(3): 24-41)

机构：Macquarie University（麦考瑞大学，澳大利亚），武汉大学

导师：盛权政（Michael Sheng）

针对文本领域的对抗样本综述文章。主要内容为：第三章，介绍了攻击图像数据与攻击文本数据的区别，简要说明攻击图像相关的神经网络的历程，为NLP领域提供参考。第四章，介绍目前主流的攻击文本深度神经网络的方法。第五章，探讨了防御的方法（这里在没有接触这个领域的时候，有疑惑，并不知道对抗样本实际的应用场景）。第六章，提出目前领域内还未解决的问题。

### <span id="[J]软件学报">[J]软件学报</span>

期刊概述：三大学报

#### 对抗样本生成技术综述(2020, 31(1): 67-81)

机构：浙江大学

导师：宋明黎

并没有细看，主要是针对图像深度学习领域的综述，前面的基础知识更容易理解，一些专业名词的中文翻译。

------------------------------------------------------------------------------------------



## <span id="2019">2019</span>

### <span id="[C]NDSS(Network and Distributed System Security Symposium)">[C]NDSS(Network and Distributed System Security Symposium)</span>

会议概述：计算机系统安全领域四大顶会之一（NDSS、CSS、USENIX SECURITY、IEEE S&P），CCFB

#### TextBugger: Generating Adversarial Text Against Real-world Applications

机构：浙江大学，University of Illinois at Urbana-Champaign（伊利诺伊大学厄巴纳-香槟分校，UIUC，美国）

导师：纪守领，浙江大学教授

经典文章，提出了textbugger这个框架，可以在白盒与黑盒两个场景下生成保留样本意愿的对抗样本。在白盒场景下计算雅各比矩阵来找到句子中的关键词，主要方法为五种策略对关键词进行修改，通过置信度的变化找到最佳的修改方案；在黑盒场景下，先找到对结构最影响力的句子，再通过评分函数寻找句子中的关键词，关键词的修改方案与白盒的相同（也是textbugger的本质）。

主要贡献可以分为以下三点：

1.提出textbugger框架，在白盒和黑盒两个场景下生成高效的对抗样本。

2给出了四种对抗样本和原样本的相似度评估方式。（看论文比较少，应该不是自己提出）

3.讨论了两种防御策略，拼写检测与对抗训练。

攻击评估方式1采用了情感分析，数据集为IMDB数据集和Rotten Tomatoes Movie Reviews数据。

白盒攻击：针对LR、CNN 和 LSTM 模型。

黑盒攻击：Google Cloud NLP、IBM Waston Natural Language Understanding (IBM Watson)、Microsoft Azure Text Analytics (Microsoft Azure)、Amazon AWS Comprehend (Amazon AWS)、Facebook fast-Text (fastText)、ParallelDots、TheySay Sentiment、Aylien Sentiment、TextProcessing、Mashape Sentiment 等参数未知的模型。

Baseline：(1) 随机算法：每个句子，随机选择10%的单词来修改。

(2) FGSM+NNS：使用快速梯度符号法寻找单词嵌入层的最佳扰动，再在词典中通过最近邻搜索的方式寻找到最接近的单词。

(3) DeepFool+NNS：使用DeepFool方法寻找穿越多分类问题决策边界的方向，进而找到最佳扰动，再在词典中通过最近邻搜索的方法寻找最接近的单词。

攻击评估方式2为有害内容检测（有害内容检测是NLP应用的重要组成部分，可以净化网络环境）。数据集为kaggle 有害内容检测竞赛数据集。









