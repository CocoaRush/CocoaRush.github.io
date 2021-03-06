---
layout:     post
title:      数据挖掘
subtitle:   分析报告、统计分析和数据挖掘等基本概念
date:       2018-01-14
author:     Pitt
header-img: img/post-bg-0.jpg
catalog: true
tags:
    - 2018.01
    - AI
    - ABC
---


## 概述

分析报告给你后见之明 (hindsight)；
统计分析给你先机 (foresight)；
数据挖掘给你洞察力 (insight)；






### 孙悟空大战二郎神

![](https://ws4.sinaimg.cn/large/006tNc79ly1fnghmkgukrj30fa0dy3zp.jpg)

你看到孙悟空跟二郎神打仗，然后写了个分析报告，说孙悟空在柔韧性上优势明显，二郎神在力气上出类拔萃，所以刚开始不相上下；结果两个人跑到竹林里，在竹子上面打，孙悟空的优势发挥出来，所以孙悟空赢了。这叫**分析报告**。
 
孙悟空要跟二郎神打架了，有个赌徒找你预测。你做了个统计，发现两人斗争4567次，其中孙悟空赢3456次。另外，孙悟空斗牛魔王，胜率是89%，二郎神斗牛魔王胜率是71%。你得出趋势是孙悟空赢。因为你假设了这次胜利跟历史的关系，根据经验作了一个假设。这叫**统计分析**。
 
你什么都没做，让计算机自己做关联分析，自动找到了`出身`、`教育`、`经验`、`单身`四个因素。得出结论是孙悟空赢。计算机通过分析发现贫苦出身的孩子一般比皇亲国戚功夫练得刻苦；打架经验丰富的人因为擅长利用环境而机会更多；在都遇得到明师的情况下，贫苦出身的孩子功夫可能会高些；单身的人功夫总比同样环境非单身的高。孙悟空遇到的名师不亚于二郎神，而打架经验绝对丰富，并且单身，所以这次打头，孙悟空赢。这叫**数据挖掘**。





## 数据挖掘

![](https://ws3.sinaimg.cn/large/006tNc79ly1fnghzcj2xrj30jg070wfv.jpg)

通常我们把信息转化为价值，要经历信息、数据、知识、价值四个层面，数据挖掘就是中间的重要环节，是从数据中发现知识的过程。


### 数据在统计意义上的类型

**Statistical Technique**

### Qualitative Variable

#### nominal Scale
数字只用做对食物进行识别和分类的标志和标签

例如：性别，婚姻状态，国籍等

#### ordinal Scale
数字代表事物拥有某种属性的相对程度／位置，但没有指明差别的大小

例如：偏好排序，市场／行业地位等


### Quantitative Variable

#### interval scale
数字相等的距离代表了被测特性的相等值，即可以比较事物之间差别的大小

例如：偏好量表，重要性评分

#### ratio scale
依据尺度值对事物进行分类、比较等，以及计算相互之间的差值、比率等


### 基本的探测指标

#### 集中趋势指标

* 均值（mean）- 平均数，对异常值（极小或极大）很敏感
* 中位数（median）- 排序后居于中间位置的数值，不受异常值影响
* 众数（mode）- 出现最频繁的数值，代表分布中的高峰

#### 变异性指标

* 极差（range）- 最大值与最小值之差，range = max - min
* 方差（variance）离均差平方的均值，var = 1/(n-1) * sum(Xi - mean)^2
* 标准差（standard deviation）方差的平方根，stdev = Sqrt(var)

#### 变异趋势指标

* 偏度（skewness）- 数据在均值两侧偏差趋势的差异性
* 峰度（kurtosis）- 分布曲线相对平滑或突起程度


### 数据挖掘的算法

* 二元分类器
* 数值预测器
* 回归
* 贝叶斯网络
* Logistics 回归
* 判别式
* 两步
* 排序
* 时间序列
* QUEST
* C&R 树
* CHAID
* GRI
* Apriori
* 异常
* 特征选择
* C5.0
* 神经网络
* 决策列表
* K-means
* Kohonen
* 主成分分析
* SLRM
* SVM
* GenLin
* Cox
* Cama

## 十大经典算法

数据挖掘主要分为分类算法，聚类算法和关联规则三大类，这三类基本上涵盖了目前商业市场对算法的所有需求。

### 1. C4.5
C4.5 以决策树的形式构建了一个分类器。为了做到这一点，需要给定 C4.5 表达内容已分类的数据集合。

决策树学习是创建一种类似与流程图的东西对新数据进行分类。

C4.5 算法和决策树系统的区别

* 算法在生成信息树的时候使用了信息增益
* 使用了一个单向的剪枝过程来缓解过渡拟合
* 既可以处理连续数据也可以处理离散数据

### 2. K-means 均值聚类算法
从一个目标集中创建多个组，每个组的成员都是比较相似的。

* 在多维空间中挑选一些点代表每一个 k 类。他们叫做中心点。
* 每个实例会在这 k 个中心点中找到离自己最近的一个。
* 之后k-means 算法根据它的类成员找到每个聚类的中心。这个中心成为该类新的中心点。
* 重复2-3步直到中心点不再改变，这样类成员也就稳定了。这也叫做收敛性。

K-means 算法的两个关键弱点分别是它对异常值的敏感性和它对初始中心点选择的敏感性。K-means 算法是设计来处理连续数据的。对于离散数据你需要使用一些小技巧后才能让 k-means 算法奏效。


### 3. SVM 支持向量机

支持向量机（SVM）获取一个超平面将数据分成两类。SVM 算法可以算出这个超平面的方程。如果数据复杂到二维空间中一条线不能区分开时，就扩展到更高维的三维空间中，尝试用平面在区分这组数据，以此类推，只到区分出来为止。

* SVM 把数据映射到一个更高维的空间然后找到一个能分类的超平面。
* 类间间隔是超平面和各自类中离超平面最近的数据点间的距离。
* SVM 的关键在于，它试图最大化这个类间间隔，使分类的超平面远离分类实例。这样就能降低误分类的可能性。


### 4. Apriori 关联算法
Apriori算法学习数据的关联规则(association rules)，适用于包含大量事务（transcation）的数据库。

关联规则学习是学习数据库中不同变量中的相互关系的一种数据挖掘技术。

* 项集的大小，想看到的模式是2-itemset或3-itemset 还是其他的？
* 支持的项集，或者是从事务的总数划分出的事务包含的项集。一个满足支持度的项集叫做频繁项集。
* 根据已经统计的项集中某些数据项，计算其他某个数据项出现的信心水准或是条件概率。


基本的 Apriori 算法有三步：

1. 参与，扫描一遍整个数据库，计算1-itemsets 出现的频率。
2. 剪枝，满足支持度和可信度的这些1-itemsets移动到下一轮流程，再寻找出现的2-itemsets。
3. 重复，对于每种水平的项集 一直重复计算，知道我们之前定义的项集大小为止。



### 5. Expectation Maximaization 最大期望值
在概率（probabilistic）模型中寻找参数最大似然估计的算法，其中概率模型依赖于无法观测的隐藏变量（Latent Variabl）。


### 6. PageRank 
根据网站的外部链接和内部链接的数量和质量，衡量网站的价值。其背后的概念是，每个到页面的链接都是对该页面的一次投票， 被链接的越多，就意味着被其他网站投票越多。


### 7. AdaBoost
一种迭代算法，其核心思想是针对同一个训练集训练不同的分类器(弱分类器)，然后把这些弱分类器集合起来，构成一个更强的最终分类器 (强分类器)。

其算法本身是通过改变数据分布来实现的，它根据每次训练集之中每个样本的分类是否正确，以及上次的总体分类的准确率，来确定每个样本的权值。将修改过权值的新数据集送给下层分类器进行训练，最后将每次训练得到的分类器融合起来，作为最后的决策分类器。



### 8. KNN K-Nearrest-Neighbor Classification
如果一个样本在特征空间中的k个最相似（即特征空间中最邻近）的样本中的大多数属于某一个类别，则该样本也属于这个类别。


### 9. Naive Bayes 朴素贝叶斯
在众多的分类模型中，应用最为广泛的两种分类模型是决策树模型(Decision Tree Model)和朴素贝叶斯模型（Naive Bayesian Model，NBC）。 
朴素贝叶斯模型发源于古典数学理论，有着坚实的数学基础，以及稳定的分类效率。同时，NBC模型所需估计的参数很少，对缺失数据不太敏感，算法也比较简单。
理论上，NBC模型与其他分类方法相比具有最小的误差率。但是实际上并非总是如此，这是因为NBC模型假设属性之间相互独立，这个假设在实际应用中往往是不成立的，这给NBC模型的正确分类带来了一定影响。在属性个数比较多或者属性之间相关性较大时，NBC模型的分类效率比不上决策树模型。而在属性相关性较小时，NBC模型的性能最为良好。


### 10. CART Classification and Regression Trees 分类与回归树
在分类树下面有两个关键的思想：第一个是关于递归地划分自变量空间的想法；第二个想法是用验证数据进行剪枝。


**End**

https://zhuanlan.zhihu.com/p/25140821
http://blog.csdn.net/u011067360/article/details/24368085
