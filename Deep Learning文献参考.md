# Deep Learning文献参考

## 内容

[1.2020](#2020)

- [1.1 [C]CVPR(Computer Vision and Pattern Recognition)](#[C]CVPR)
- [1.2 [C]NeurIPS(Neural Information Processing Systems)](#[C]NeurIPS)

[2.2018](#2018)

- [2.1 [C]ACL(Association for Computational Linguistics)](#CACL-2019)

  

## 数据集



------------------------------------------------------------------------------------------



## <span id="2020">2020</span>

### ArXiv

#### Supervised Contrastive Learning For Pre-Trained Language Model Fine-tuning

自监督对比学习的目的是在未知标签的情况下拉进同样本之间的距离，退远不同样本的距离，达到抽取共性特征的目的。然而其做法会导致同类的样本之间的距离也变远。论文基于此提出了有监督对比学习。

在自监督对比学习流行的基础下提出一个新的损失函数SCL（监督对比学习），将同一类样本互相作为正例，不同样本作为负例，以此达到拉进类内样本、拉开类间距离的目的。

### [C]CVPR

会议概述：人工智能（计算机视觉领域）顶会，CCFA

#### Adversarial Robustness: From Self-Supervised Pre-Training to Fine-Tuning

机构：德克萨斯农工大学、麻省理工学院-IBM沃森人工智能实验室

首次证明对抗样本对自监督学习的模型能力提升有帮助，发现对抗性预训练不仅可以提高最终模型的稳健性，而且可以加快后续的对抗性微调。论文还发现对抗性微调对最终的健壮性改进贡献最大。

### [C]NeurIPS

会议概述：人工智能顶会，CCFA

#### Contrastive Learning with Adversarial Examples

传统的基于对比学习的自监督方法中，往往忽视了难负例，本文通过对抗样本生成更具挑战的正负样本。

#### Adversarial Self-Supervised Contrastive Learning

机构：韩国科学技术院

​     2020年的NeurIPS连续接受了三篇关于基于对抗样本的自监督对比学习文章。

​     相关工作主要总结为：

​     **1.提出了一种不需要任何标签信息的攻击手段。**

​     2.提出了一种对抗性自监督学习方法，这一点和其他文章差不多。

#### Robust Pre-Training by Adversarial Contrastive Learning

在前人证明对抗样本对自监督学习的模型鲁棒性上的优势以后，论文结合了自监督学习中热门的对比学习作为预训练的框架，提出对抗性对比学习（Adversarial Contrastive Learning, ACL）。

在对比学习框架SimCLR的基础上提出了三种训练模式：

1. Adversarial-to-Adversarial：对比学习的样本全是对抗样本；
2. Adversarial-to-Standard：对比学习的样本为一个对抗样本一个普通样本，减轻了编码器需要抵抗两个对抗样本的工作量。需要注意的是归一化层不能共享参数；
3. Dual Stream：前两种的结合，加权（1:1）计算损失。

## 2018

### [C]ACL(Association for Computational Linguistics)

会议概述：自然语言处理四大顶会，CCFA

#### Adversarial Contrastive Estimation

机构：多伦多大学

对比学习的主旨让模型学习正负样本之间的差距，噪声对比估计（Noise Contrastive Estimation，NCE）就是采用这个方法的NLP领域例子，传统的例如在Word2Vec中的NCE通常只通过人的先验知识进行编码，以确定负样本的构成，但往往只生成简单负样本，简单负样本往往不会强迫模型去观察正样本的关键特征，即使出现难负样本，由于样本量小，也仅仅意味着缓慢的收敛。

论文提出对抗样本作为改进对比学习的一种手段，采用GAN的生成器生成难负样本，验证了难负例对模型的学习至关重要。





