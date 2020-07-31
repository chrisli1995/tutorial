# Adversarial Examples文献参考

## 内容

[1.2020](#2020)

- [1.1 [C]ACL(Association for Computational Linguistics)](#[C]ACL(Association for Computational Linguistics))
- [1.2 [C]AAAI(National Conference of the American Association for Artificial Intelligence)](#[C]AAAI(National Conference of the American Association for Artificial Intelligence))
- [1.3 [J]ACM Transactions on Intelligent Systems and Technology](#[J]ACM Transactions on Intelligent Systems and Technology)
- [1.4 [J]软件学报](#[J]软件学报)

[2.2019](#2019)

- [2.1 [C]NDSS(Network and Distributed System Security Symposium)](#[C]NDSS(Network and Distributed System Security Symposium))

## 数据集

![image.png](https://upload-images.jianshu.io/upload_images/7810235-5d28cd4dbd9daf56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

------------------------------------------------------------------------------------------



## <span id="2020">2020</span>

### <span id="[C]ACL(Association for Computational Linguistics)">[C]ACL(Association for Computational Linguistics)</span>

### Its Morphin Time!Combating Linguistic Discrimination with Inflectional Perturbations

机构：新加坡国立大学、南洋理工大学

论文提出了一个新颖的概念，即在NLP领域的模型应该考虑到不是以英语为母语，但在使用英语的人，他们往往存在一些方言，或者使用一些错误的时态，模型理应对这些情况有“包容性”。具体做法是找到原始语句的中的名词、动词和形容词，在保留词根的情况下，对这些句子中的单词进行替换，找到最佳的替换组合。

实验部分主要与两个任务，自动问答以及机器翻译，主要采用的评估方式为F1值和BLEU，比价评价指标前后的变化。

### Word-level Textual Adversarial Attacking as Combinatorial Optimization

机构：清华大学计算机科学与技术系智能技术与系统国家重点实验室、哥伦比亚大学、[华为诺亚方舟实验室](https://www.baidu.com/link?url=s5Lt6TJHBpNt2634tZ5-bkmOQyQXPvk64RoQSTIEPEUS4ZBpIuOfI0XSrkihMWF1&wd=&eqid=b7b2fc8a000b41da000000055f240b37)

导师：刘知远

主要是针对两个问题（目前看的2020年的词级文本对抗样本的文章均针对的这个两个问题，比较重要：1.减少替换词的搜索空间。2.对抗实例的搜索。两个问题目前均没有一个较好的解决思路，论文提出引入义素的概念（sememes）来保留更多更高质量替换候选词，采用一种基于粒子群优化算法的搜索策略找到对抗样本。

### <span id="[C]AAAI(National Conference of the American Association for Artificial Intelligence)">[C]AAAI(National Conference of the American Association for Artificial Intelligence)</span>

会议概述：AI领域顶会

#### Is BERT Really Robust? A Strong Baseline for Natural Language Attack on Text Classification and Entailment

机构：麻省理工学院计算机科学与人工智能实验室（CSAIL）、香港大学、新加坡科技研究局

​     本论文研究了在黑盒情况下针对最新文本分类和文本蕴含模型的对抗攻击。主要针对目前文本对抗样本所存在的三个普遍问题：1.人对对抗样本的预测应该保持一致；2.对抗样本需要包含于原始样本一样的语义（以人的视角）；3. 对抗样本需要看起来自然，且符合语法。

​     实验结果表明，提出的系统TEXTFOOLER在生成有针对性的对抗文本方面是有效的。人为评估表明，所生成的对抗性文本清晰易读，符合语法规定，并且含义与原始文本相似。

​     主要针对任务：文本分类以及文本蕴含任务。

​     使用的数据集和评价指标值得学习。

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









