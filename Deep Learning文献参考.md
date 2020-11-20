# Deep Learning文献参考

## 内容

[1.2020](#2020)

- [1.1 [C]CVPR(Computer Vision and Pattern Recognition)](#[C]CVPR)
- [1.2 [C]NeurIPS(Neural Information Processing Systems)](#[C]NeurIPS)

[2.2019](#2019)

- [2.1 [C]ACL(Association for Computational Linguistics)](#CACL-2019)

  

## 数据集



------------------------------------------------------------------------------------------



## <span id="2020">2020</span>

### [C]CVPR

会议概述：人工智能（计算机视觉领域）顶会，CCFA

#### Adversarial Robustness: From Self-Supervised Pre-Training to Fine-Tuning

机构：德克萨斯农工大学、麻省理工学院-IBM沃森人工智能实验室

首次证明对抗样本对自监督学习的模型能力提升有帮助，发现对抗性预训练不仅可以提高最终模型的稳健性，而且可以加快后续的对抗性微调。论文还发现对抗性微调对最终的健壮性改进贡献最大。

### [C]NeurIPS

会议概述：人工智能顶会，CCFA

#### Robust Pre-Training by Adversarial Contrastive Learning

在前人证明对抗样本对自监督学习的模型鲁棒性上的优势以后，论文结合了自监督学习中热门的对比学习作为预训练的框架，提出对抗性对比学习（Adversarial Contrastive Learning, ACL）。

在对比学习框架SimCLR的基础上提出了三种训练模式：

1. Adversarial-to-Adversarial：对比学习的样本全是对抗样本；

2. Adversarial-to-Standard：对比学习的样本为一个对抗样本一个普通样本，减轻了编码器需要抵抗两个对抗样本的工作量。需要注意的是归一化层不能共享参数；
3. Dual Stream：前两种的结合，加权（1:1）计算损失。









