# Adversarial Examples文献参考

## 内容

[1.2020](#2020)

- [1.1 [C]AAAI(National Conference of the American Association for Artificial Intelligence)](#CAAAI)
- [1.2 [C]ACL(Association for Computational Linguistics)](#CACL)
- [1.3 [J]TITS(ACM Transactions on Intelligent Systems and Technology)](#JTITS)
- [1.4 [J]TACL(Transactions of the Association for Computational Linguistics)](#JTACL)
- [1.5 [J]JMLR(Journal of Machine Learning Research)](#JJMLR)
- [1.6 [J]软件学报](#[J]软件学报)

[2.2019](#2019)

- [2.1 [C]EMNLP(Empirical Methods in Natural Language Processing)](#CEMNLP)
- [2.2 [C]ICASSP(International Conference on Acoustics, Speech and Signal Processing)](#CICASSP)
- [2.3 [C]NAACL(North American Chapter of the Association for Computational Linguistics)](#CNAACL)
- [2.4 [C]NDSS(Network and Distributed System Security Symposium)](#CNDSS)

[3.2018](#2018)

- [[C]EMNLP(Empirical Methods in Natural Language Processing)](#[C]EMNLP)



## 数据集

![image.png](https://upload-images.jianshu.io/upload_images/7810235-5d28cd4dbd9daf56.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

------------------------------------------------------------------------------------------



## <span id="2020">2020</span>

### [C]AAAI

会议概述：AI领域顶会

#### A Robust Adversarial Training Approach to Machine Reading Comprehension

机构：百度、厦门大学、北京大学

导师：李素建（北京大学）

​     一种最简单的对抗样本防御策略就是将生成的对抗样本重新放入数据集进行学习，本文主要是在机器阅读理解领域提出一个新的训练方式来完成模型学习。具体步骤为：1.将模型视为一个黑盒，从原始数据中的备选的单词（实验部分又改为了自己建造的一个词表，为了模型更容易收敛，结果看得更好）中找到可以扰动结果的序列；2.从原文嵌入扰动序列，生成对抗样本；3.重复训练模型。主要的创新点集中在2，定义一个权重矩阵（需训练），来找到什么序列能够扰动结果，并且这是一个定向攻击（看到的比较少）。

#### Is BERT Really Robust? A Strong Baseline for Natural Language Attack on Text Classification and Entailment

机构：麻省理工学院计算机科学与人工智能实验室（CSAIL）、香港大学、新加坡科技研究局

​     本论文研究了在黑盒情况下针对最新文本分类和文本蕴含模型的对抗攻击。主要针对目前文本对抗样本所存在的三个普遍问题：1.人对对抗样本的预测应该保持一致；2.对抗样本需要包含于原始样本一样的语义（以人的视角）；3. 对抗样本需要看起来自然，且符合语法。

​     实验结果表明，提出的系统TEXTFOOLER在生成有针对性的对抗文本方面是有效的。人为评估表明，所生成的对抗性文本清晰易读，符合语法规定，并且含义与原始文本相似。

​     主要针对任务：文本分类以及文本蕴含任务。

​     使用的数据集和评价指标值得学习。

#### Joint Character-level Word Embedding and Adversarial Stability Training to Defend Adversarial Text

机构：中国科学院 

​     本文主要针对字符集的对抗样本进行防御，首先提出来了目前字符级防御急需解决的两个问题：1.修改的词出现OOV问题（这也是为什么字符级的对抗样本能够产生扰动的主要原因）。2.对抗样本和原本的分布不同（说白了就是模型没有适应对抗样本）。针对第一个问题，本文采用了字符级的编码来最小的使得机器学习字符之间的联系，减小对抗样本带来的影响，因此也不存在OOV的问题了。针对第二个问题，主要还是采用自定义的损失去更新模型。

​     实验部分对五个常用的文本分类数据集在字符级的LSTM以及CNN上面完成了实验（Char-LSTM、Char-CNN）。

#### Seq2Sick: Evaluating the Robustness of Sequence to Sequence Models with Adversarial Examples

机构：加州大学洛杉矶分校

论文虽然是2020年发表在AAAI会议上的，但是在2018年就在arxiv上发表了（会议也能拖这么久）。所以在一开始看的时候并没有感觉到太多的创新点。按照文章的说法，本文是第一个攻击seq2seq模型的文章（之前其实看过很多文章攻击的都是类似的结构），针对性的提出两种攻击方式：第一种是无重叠攻击，即对抗样本和原始输出不会有重复的地方；第二种是关键字攻击，即对抗样本需要保留给定的关键字。显然，关键字攻击的难度更大。

文章证明了稍微修改seq2seq模型的输入能够达到显著修改输出，seq2seq模型比传统的CNN模型更加健壮，想要产生对抗样本会造成更大的失真，且更易被感知。

### [C]ACL

#### Evaluating and Enhancing the Robustness of Neural Network-based Dependency Parsing Models with Adversarial Examples

机构：复旦大学上海市智能信息处理重点实验室、加州大学洛杉矶分校

导师：郑骁庆

对抗样本问题的存在使得深度学习模型在应用落地上存在大量的潜在风险，对抗样本已经在计算机视觉领域取得了不少研究成果，包括多种攻击与防御方法，最终目的是为了提高深度学习模型的鲁棒性。在自然语言处理领域，与对抗样本相关的研究较少，本次分享从文本对抗样本问题出发，分析主要做法、存在问题，并将其拓展到依存句法领域。

主要的贡献点是把对抗样本扩展到依存句法领域，由于对这一块了解的不多，所以并没有细看。替换词的生成采用BERT，具体如何生成并没有给出。

#### Its Morphin Time!Combating Linguistic Discrimination with Inflectional Perturbations

机构：新加坡国立大学、南洋理工大学

论文提出了一个新颖的概念，即在NLP领域的模型应该考虑到不是以英语为母语，但在使用英语的人，他们往往存在一些方言，或者使用一些错误的时态，模型理应对这些情况有“包容性”。具体做法是找到原始语句的中的名词、动词和形容词，在保留词根的情况下，对这些句子中的单词进行替换，找到最佳的替换组合。

实验部分主要与两个任务，自动问答以及机器翻译，主要采用的评估方式为F1值和BLEU，比价评价指标前后的变化。

#### On the Robustness of Language Encoders against Grammatical Errors

机构：北京大学、上海交通大学、加州大学洛杉矶分校

文章对目前比较流行的几个预训练模型进行了攻击（ELMO、BERT 、RoBERTa），攻击的手段主要以语法出发（这里的语法实际上也是对特定的token，或者token组合进行替换，例如growing替换成grows），之前针对语法的攻击要不是针对指定的语料库，要不是严重依赖于人类注释和专家知识，文章提出了一种自动生成对抗样本的方法，且样本满足各类语法错误。

在此基础上分析了语法错误的识别在预训练模型的不同层上的识别能力，通过BERT来挖掘出存在语法错误的token。

#### Robust Encodings: A Framework for Combating Adversarial Typos

机构：斯坦福大学

​     以防御为主的文本对抗样本文章，提出了一个名为RobEn的框架，用于可以抵御对抗扰动的系统。主要可以实现对拼写错误，同义词替换等攻击方式的抵御。主要通过聚类的方式，将错别字与原文定义在同一个空间当中。方式是尽量使得不同的错别字与可能的会受到干扰的词放在同一簇里面。

#### Word-level Textual Adversarial Attacking as Combinatorial Optimization

机构：清华大学计算机科学与技术系智能技术与系统国家重点实验室、哥伦比亚大学、[华为诺亚方舟实验室](https://www.baidu.com/link?url=s5Lt6TJHBpNt2634tZ5-bkmOQyQXPvk64RoQSTIEPEUS4ZBpIuOfI0XSrkihMWF1&wd=&eqid=b7b2fc8a000b41da000000055f240b37)

导师：刘知远

主要是针对两个问题（目前看的2020年的词级文本对抗样本的文章均针对的这个两个问题，比较重要：1.减少替换词的搜索空间。2.对抗实例的搜索。两个问题目前均没有一个较好的解决思路，论文提出引入义素的概念（sememes）来保留更多更高质量替换候选词，采用一种基于粒子群优化算法的搜索策略找到对抗样本。

### [J]TITS

期刊概述：ISSN：2157-6904

SCI工程技术2区，三年平均IF：3.010

#### Adversarial Attacks on Deep Learning Models in Natural Language Processing A Survey(2020, 11(3): 24-41)

机构：Macquarie University（麦考瑞大学，澳大利亚），武汉大学

导师：盛权政（Michael Sheng）

针对文本领域的对抗样本综述文章。主要内容为：第三章，介绍了攻击图像数据与攻击文本数据的区别，简要说明攻击图像相关的神经网络的历程，为NLP领域提供参考。第四章，介绍目前主流的攻击文本深度神经网络的方法。第五章，探讨了防御的方法（这里在没有接触这个领域的时候，有疑惑，并不知道对抗样本实际的应用场景）。第六章，提出目前领域内还未解决的问题。

### [J]TACL

期刊概述：ACL旗下的期刊，NLP领域内的顶刊了，但是不知道CCF和中科院查不到。

#### Trick Me If You Can Human-in-the-Loop Generation of Adversarial Examples for Question Answering

对抗评估（adversarial evaluation）强调测试模型对自然语言的理解能力。由于过去的方法只能发现表层的规律，获得的对抗样本只有有限的复杂性和多样性。本文中，研究人员提出了一种人类参与的对抗样本生成循环流程。在流程中，人类作者可以被引导用于中断模型。研究人员给作者们提供了交互式界面，用于解释模型的预测结果。

研究人员在 Quizbowl 这一机器问答任务（猜词任务，随着给的问题越来越多，猜词难度也会越来越小）上使用提出的生成框架，由热衷于 trivia 游戏的人制作对抗问题。而最终生成的文本通过人机匹配进行验证：尽管生成的问题对人类很普通，但可能会全面地难倒神经模型或信息抽取模型。这些对抗样本涵盖了多种多样的特征，从多跳推理（multi-hop reasoning）到实体类型干扰项，暴露出了鲁棒的机器问答研究中的许多开放挑战。（本质上就是提出了一个人工对抗性数据集，人工的过程可以理解）

生成对抗样本的交互界面和数据展示。人类作者首先在右上写下一个问题。而模型则会在左侧提供预测结果，并解释这样推断的原因（会高亮得出判断是因为哪些词）。而人类作者可以选择接受这个问题，用于迷惑模型。

### [J]JMLR

期刊概述：ISSN：1532-4435

SCI工程技术2区，3年平均IF：3.791，CCFA类期刊（人工智能）

#### Greedy Attack and Gumbel Attack: Generating Adversarial Examples for Discrete Data

机构：加州大学

虽然是2020期刊，但是其实内容是在18年就发表的，所以现在来看它的创新性不是太足，主要步骤还是先找到特征对文本分类任务的影响最大的点，然后对它进行替换，替换的方式是采用GloVe生成的词向量找到欧式距离最近的词。

分两种方式完成以上步骤，greedy attack就是采用贪心的方式来完成，效果比较好，但效率不高；gumbel attack，主要是采用梯度的方式，效率更高。

### <span id="[J]软件学报">[J]软件学报</span>

期刊概述：三大学报

#### 对抗样本生成技术综述(2020, 31(1): 67-81)

机构：浙江大学

导师：宋明黎

并没有细看，主要是针对图像深度学习领域的综述，前面的基础知识更容易理解，一些专业名词的中文翻译。

------------------------------------------------------------------------------------------

## <span id="2019">2019</span>

### [C]EMNLP

#### Universal Adversarial Triggers for Attacking and Analyzing NLP

机构：马里兰大学，加里福利亚大学

以前，NLP中的对抗攻击一般都是针对特定输入的，那么他们对任意的输入是否有效呢？

本文针对这个问题，搜索通用的对抗性触发器：与输入无关的token序列，当连接到来自数据集的任何输入时，这些token序列触发模型生成特定的预测。例如，触发器导致SNLI隐含精度从89.94%下降到 0.55%，72%的“为什么”问题在SQuAD中回答“杀死美国人”，而gps -2语言模型即使在非种族背景下也会输出种族主义。（这就很厉害了。）

主要攻击了三个任务：

1.文本分类任务，主要对三个模型进行了攻击：BI-LSTM、Word2Vec、ELMO

2.阅读理解任务，主要攻击模型BiDAF（baseline）

3.条件文本生成，主要攻击模型GPT-2

### [C]ICASSP

会议概述：语音识别顶会

#### Universal Adversarial Attacks on Text Classifiers

机构：伊朗沙力夫理工大学，伊朗清华

文章说的比较清楚，目的是在构造一个通用的模型生成对抗样本，只要攻击的是文本分类模型。与以往的研究有一点不一样的是，它是通过梯度方式找到合适的替换词。其他的没有什么特别的地方。

### [C]NAACL

会议概述：自然语言处理领域四大顶会之一（ACL、HAACL、EMNLP、COLING），CCFC会议

#### Text Processing Like Humans Do Visually Attacking and Shielding NLP Systems

机构：达姆施塔特工业大学（德国）

​     2019年的文章，字符级的攻击，思想不同于其他文章的地方在于，在文本中添加视觉扰动，具体方案为规定概率的情况的下，每个字符都基于这个概率在字符空间中寻找与其相近的字符。字符空间除了使用常用的向量空间以外（用于词嵌入），还有基于描述的字符空间和简单字符空间，前者是通过在Unicode编码的基础上找到相邻的字符，后者单纯的在每个字符上下两个部分加入标记来完成。

### [C]NDSS

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

-------------------------------------

## 2018

### [C]EMNLP

#### Generating Natural Language Adversarial Examples

2018的文章比较老，但在效果在文本分类的两个任务上结果非常好（情感分析+文本蕴含），并且是定向攻击。在看的文章中为数不多的采用老牌启发式算法寻找最佳对抗样本的方法。基本思路是通过遗传算法迭代产生对抗样本，每生成一代样本通过函数筛选出质量高的数据，高质量数据更有可能“培育”出下一代，直至产生能够扰动到目标标签的样本。









