### 多轮检索式对话系统小结

#### 多轮检索式对话系统

对话系统分类依据不同，类型也不同。若按照任务类型分，可以分为闲聊型以及任务型对话系统；若实现的方式分类可以分为检索式对话系统和生成式对话系统。关于检索式以及生成式的各自特性、优缺点以及区别在 [A Hybrid Retrieval-Generation Neural Conversation Model](<https://arxiv.org/abs/1904.09068?context=cs>) 中描述的很详尽。这里仅总结目前流行的检索式对话。

#### 多轮检索式对话系统中重要的工作

##### 1 Multi-View Response Selection 

![Multi-view response selection model](https://github.com/iezhuozhuo/PaperReading/blob/master/%E6%A3%80%E7%B4%A2%E5%BC%8F%E5%AF%B9%E8%AF%9D/pic/MV.png)

Multi-View 工作的主要核心在于构建词级和句级多角度的特征。其中第一次将utterance化为一个处理单元，并使用utterance的时序关系作为一种监督信号(如：提取的utterance view之后过GRU)。比较有意思的实验结果是添加SOS分隔符会提高Model的性能。具体细节参考：[Multi-view Response Selection](<https://zhuanlan.zhihu.com/p/66365985>)

工作的不足：

- 尽管将utterance作为单元处理，但处理框架比较简单。
- 尽管上下文和回复进行交互，但是交互的层次较高，utterance提取信息阶段回复没有参与，提取信息目的性不明确。这属于简单的交互，没有利用上下文和回复的交互。

##### 2 SMN：Sequential Matching Network

![Architecture of SMN ](https://github.com/iezhuozhuo/PaperReading/blob/master/%E6%A3%80%E7%B4%A2%E5%BC%8F%E5%AF%B9%E8%AF%9D/pic/SMN.png)

SMN是经典的检索式对话模型代表。SMN认为全部utterance拼接是不利的，并且在抽象的高层语义中直接匹配是不可取的。SMN是交互式检索对话的经典模型，贡献有：(1) 简单的浅层特征提取，保证信息的丰富性，避免在抽象的高层中直接匹配；(2) 构建多维度的匹配矩阵(如词级和句级的匹配矩阵)；(3) 开创性的使用CNN+pooling提取匹配矩阵的显著匹配信息；(4) 利用GRU添加重要匹配信息的时序关系。具体细节参考：[SMN：Sequential Matching Network](<https://zhuanlan.zhihu.com/p/66384889>)

##### 3 DUA：Modeling Multi-turn Conversation with Deep Utterance Aggregation 

![Structure overview of the proposed dialogue system ](https://github.com/iezhuozhuo/PaperReading/blob/master/%E6%A3%80%E7%B4%A2%E5%BC%8F%E5%AF%B9%E8%AF%9D/pic/DUA.png)

DUA是SMN的一种改进。它认为last utterance是最为重要的，因为其与response最为衔接。所以它的想法在于用最后一句话来区别前面所有utterance中词的重要程度，所用的方法是图中Gated self Attention。Model中有很多不好解释的地方，比如所谓的Attentive Turns Aggregation部分，最后使用 $P_{u_i}$ 和最后一层的 GRU 计算 context vector来计算得分。具体可以参考：[《DUA》阅读笔记](<https://zhuanlan.zhihu.com/p/64132530>)

##### 4 DAM：Multi-Turn Response Selection  with Deep Attention Matching Network

![Overview of Deep Attention Matching Network](https://github.com/iezhuozhuo/PaperReading/blob/master/%E6%A3%80%E7%B4%A2%E5%BC%8F%E5%AF%B9%E8%AF%9D/pic/DAM.png)

DAM将self-attention发挥的淋漓尽致，通过stacked self-attention构建出不同层级的utterance和response表征，然后在不同层级表征之间构建匹配矩阵。不同层级间构建出两个匹配矩阵 --- $M^{u_i,r}_{self}$ 和 $M^{u_i, r}_{cross}$ ，尤其是 $M^{u_i, r}_{cross}$ 里面包含了双向注意力机制。最终匹配矩阵是一个3D Matching Tensor，对其使用3D CNN以及Pooling 并经过 MLP 得到匹配分数。有意思的点：(1) 堆叠的不同层次的句信息，这样可以构建不同层次的句表征；(2) $M^{u_i, r}_{cross}$ 包含的双向注意力机制作用可观。 具体细节参考：[DAM——Deep Attention Matching Network](<https://zhuanlan.zhihu.com/p/68325669>)

##### 5 MRFN：Multi-Representation Fusion Network for Multi-turn Response Selection 

![Multi-representation fusion network](https://github.com/iezhuozhuo/PaperReading/blob/master/%E6%A3%80%E7%B4%A2%E5%BC%8F%E5%AF%B9%E8%AF%9D/pic/MRFN.png)

MRFN将Muti-View中多粒度的思想发挥淋漓尽致，对utterance和response分别提取六种表征：Character-based Word Embedding、Word2Vec、Sequential Representation、Local Representation、Self-attention、Cross-attention。然后根据六种粒度的表征融合阶段与匹配交互的顺序分为早期融合 (FES)、中期融合 (FIS) 、后期融合 (FLS)。有意思的点：(1) 构建多粒度的表征，虽然证实这些粒度之间信息会有冗余；(2) FLS最后的结果最好，说明不同表征对最终结果集体决策作用；(3) 两个GRU --- $GRU_{t}$ 捕捉utterance句子内部的长期依赖，$GRU_{v}$ 添加utterance句子之间时间依赖。具体细节参考：[MRFN：多表征融合网络](<https://zhuanlan.zhihu.com/p/68381160>)

##### 6 IMN：Interactive Matching Network for Multi-Turn Response Selection 

![An overview of our proposed IMN model ](https://github.com/iezhuozhuo/PaperReading/blob/master/%E6%A3%80%E7%B4%A2%E5%BC%8F%E5%AF%B9%E8%AF%9D/pic/IMN.png)

IMN 实践出真知，很多有用组件的配合使用，无所不用，无所不极。其中 IMN 有四个可以借鉴的点子：(1) 解决OOV问题的三种词嵌入 --- pre-train、char-embedding、train set embedding；(2) 多层表征的贡献量化--可参考原文table 5；(3) 第一个考虑上下文未必全部有用，即对话中有些utterance可能是噪声的paper；(4) 明确的采用双向注意力。**文章的行文、用词真的好，值得一读一学**。具体细节可参考：[IMN：Interactive Matching Network](https://zhuanlan.zhihu.com/p/68590678)
