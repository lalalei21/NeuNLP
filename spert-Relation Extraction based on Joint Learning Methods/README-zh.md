## SpERT：基于联合学习的关系抽取模型

[原作repository](https://github.com/markus-eberts/spert)

[论文：Span-based Joint Entity and Relation Extraction with Transformer Pre-training](Span-based Joint Entity and Relation Extraction with Transformer Pre-training.pdf)

[数据集和BERT预训练参数-百度网盘](https://pan.baidu.com/s/1h5GjkG2bf78ZSJZYP1OBlA) -- 提取码：igjq

### 名称解释

- **命名实体识别(Name Entity Recognition, NER)**：识别文本中具有特定意义的实体，包括人名、地名、机构名等。

- **关系抽取(Relation Extraction, RE)**：识别实体对之间的语义关系，$e_1, e_2$表示两个实体，$r$表示他们之间的关系，那么两个实体的关系可以表示为 $(e_1,r,e_2)$。
- **信息抽取(Information Extraction, IE)**：从非结构化或半结构化的文本中自动提取信息，子任务包括*关系抽取、事件抽取、命名实体识别*。
- **联合学习(Joint Learning)**：挖掘不同任务之间的内在联系，采取参数共享等方式构建起统一的模型，多个任务同时优化以期达到全局最优解。（图像处理领域一般称之为多任务学习）。
- **span**：由一个或者多个单词组成的具有语义信息的单元。



### 数据集

1. **ConLL01**

   实体类型：Location, Organization, People

   关系类型：Work for, Kill, Organization base in, Live in, Located in

   训练集：922个句子

   验证集：231个句子

   测试集：288个句子

2. **SciERC**

   实体类型：Task, Method, Metric, Material, Other-Scientific-Term, Generic

   关系类型：Compare, Conjunction, Evaluate-For, Used-For, Feature-Of, Part-Of, Hyponym-Of

   训练集：1861个句子

   验证集：275个句子

   测试集：551个句子

3. **ADE Corpus**

   实体类型：Drug, Adver-Effect

   关系类型：Adverse-Effect

   样本总数：4272个句子

   10折交叉验证



### 环境配置

1. Anaconda下Python 3.6

   ``` bash
   conda install pytorch-gpu
   pip install -r requirements
   ```

2. 将网盘下载的文件解压放到工程根目录下

3. 修改config/train.conf，配置文件路径和模型超参数（默认值已经调好）

4. 训练模型，预测同理

   ``` bash
   python train #复制config/train.conf内容粘贴到后面
   ```

### 参考

``` 
[1] Markus Eberts, Adrian Ulges. Span-based Joint Entity and Relation Extraction with Transformer Pre-training. 24th European Conference on Artificial Intelligence, 2020.
```





