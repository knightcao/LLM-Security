# 大模型安全防护围栏

## 最新动态

:joy: 2025.6.20 项目开源启动。

## 1.概述

大模型安全防护围栏

随着大模型广泛应用，其安全问题日益受到广泛关注。大模型容易产生“幻觉”，也容易受到越狱攻击、任务劫持等提示词攻击，为控制上述问题，我们开发了大模型安全防护围栏。相当于给大模型加上一堵安全围墙，既能控制它的输出、又能过滤输入它的内容。一方面，用户诱导大模型生成攻击性代码、输出不道德内容的时候，它就会被护栏技术“束缚”，不再输出不安全的内容。另一方面，护栏技术还能保护大模型不受用户的攻击，帮它挡住来自外界的“恶意输入”。

本项目开源了大模型安全防护围栏的核心模型，也开源了为开发围栏而构建的大模型安全数据集。

## 2. 大模型面临的潜在风险

### 2.1 风险类型

* 生成内容合规

   人工智能生成内容涉及政治敏感、违反中国法律法规或不符合主流道德观念等。
   
* 生成歧视性内容。

    人工智能生成内容在种族、性别、地域、职业等维度是否可能生成带有偏见、贬低或攻击性言论。

* 其它风险

    其它见《生成式人工智能服务安全基本要求》（TC260-003）。

### 2.2 提示注入攻击的逻辑方法

* 假设

* 注意力转移 

* 特权模式

### 2.3 提示注入攻击的生成算法

* 重写攻击

[1] Andriushchenko, Maksym, and Nicolas Flammarion. "Does Refusal Training in LLMs Generalize to the Past Tense?." arXiv preprint arXiv:2407.11969 (2024).

* PAIR

[2] Chao, Patrick, Alexander Robey, Edgar Dobriban, Hamed Hassani, George J. Pappas, and Eric Wong. "Jailbreaking black box large language models in twenty queries." In 2025 IEEE Conference on Secure and Trustworthy Machine Learning (SaTML), pp. 23-42. IEEE, 2025.

* GCG

[3] Zou, Andy, Zifan Wang, Nicholas Carlini, Milad Nasr, J. Zico Kolter, and Matt Fredrikson. "Universal and transferable adversarial attacks on aligned language models." arXiv preprint arXiv:2307.15043 (2023).

* AutoDAN

[4] Li, Qizhang, Yiwen Guo, Wangmeng Zuo, and Hao Chen. "Improved generation of adversarial examples against safety-aligned llms." arXiv preprint arXiv:2405.20778 (2024)

* TAP

[5] Mehrotra, Anay, Manolis Zampetakis, Paul Kassianik, Blaine Nelson, Hyrum Anderson, Yaron Singer, and Amin Karbasi. "Tree of attacks: Jailbreaking black-box llms automatically." Advances in Neural Information Processing Systems 37 (2024): 61065-61105.

* Overload Attack

[6] Dong, Yiting, Guobin Shen, Dongcheng Zhao, Xiang He, and Yi Zeng. "Harnessing Task Overload for Scalable Jailbreak Attacks on Large Language Models." arXiv preprint arXiv:2410.04190 (2024).

* ArtPropmt

[7] Jiang, Fengqing, Zhangchen Xu, Luyao Niu, Zhen Xiang, Bhaskar Ramasubramanian, Bo Li, and Radha Poovendran. "Artprompt: Ascii art-based jailbreak attacks against aligned llms." In Proceedings of the 62nd Annual Meeting of the Association for Computational Linguistics (Volume 1: Long Papers), pp. 15157-15173. 2024.

* DeepInception

[8] Li, Xuan, Zhanke Zhou, Jianing Zhu, Jiangchao Yao, Tongliang Liu, and Bo Han. "Deepinception: Hypnotize large language model to be jailbreaker." arXiv preprint arXiv:2311.03191 (2023).

* GPT4-Cipher

[9] Shen, Guobin, Dongcheng Zhao, Linghao Feng, Xiang He, Jihang Wang, Sicheng Shen, Haibo Tong et al. "PandaGuard: Systematic Evaluation of LLM Safety in the Era of Jailbreaking Attacks." arXiv preprint arXiv:2505.13862 (2025).

* SCAV

[10] Xu, Zhihao, Ruixuan Huang, Changyu Chen, and Xiting Wang. "Uncovering safety risks of large language models through concept activation vector." Advances in Neural Information Processing Systems 37 (2024): 116743-116782.

* RandomSearch

[11] Andriushchenko, Maksym, Francesco Croce, and Nicolas Flammarion. "Jailbreaking leading safety-aligned llms with simple adaptive attacks." arXiv preprint arXiv:2404.02151 (2024).

* ICA

[12] Wei, Zeming, Yifei Wang, Ang Li, Yichuan Mo, and Yisen Wang. "Jailbreak and guard aligned language models with only few in-context demonstrations." arXiv preprint arXiv:2310.06387 (2023).

* Cold Attack

[13] Guo, Xingang, Fangxu Yu, Huan Zhang, Lianhui Qin, and Bin Hu. "Cold-attack: Jailbreaking llms with stealthiness and controllability." arXiv preprint arXiv:2402.08679 (2024).

* GPTFuzzer

[14] Yu, Jiahao, Xingwei Lin, Zheng Yu, and Xinyu Xing. "Gptfuzzer: Red teaming large language models with auto-generated jailbreak prompts." arXiv preprint arXiv:2309.10253 (2023).

* ReNeLLM

[15] Ding, Peng, Jun Kuang, Dan Ma, Xuezhi Cao, Yunsen Xian, Jiajun Chen, and Shujian Huang. "A Wolf in Sheep's Clothing: Generalized Nested Jailbreak Prompts can Fool Large Language Models Easily." arXiv preprint arXiv:2311.08268 (2023).



## 3. AI安全数据集

为了验证风险评估模型的有效性，我们构建了 XXX 个中文 QA 对，构建了一个大模型安全数据集。

### 3.1 数据生成方法

我们基于人工测试的经验，面向生成内容合规性和生成内容非歧视性，收集和构建了一定经典测试用例。再利用TAP、AutoDAN等算法，生成覆盖假设类、注意力转移类、特权类等类型的大模型安全数据集。

### 3.2 数据集构成

阡陌*大模型安全评测数据集v1.0

| - | 假设类     |-         |  -        |  -          |  注意力转移类  | -  |  -  | 特权类 |
| - | 场景假设	  | 角色假设  |  责任假设  | 科学实验假设 | 文本续写   |  语序颠倒 | 多语种与翻译 | 特权模式 |
| ----  | --------    | -----    |  ----     |  ----       | ----      |  ----    |  ----       | ----     |
|  TAP      |   &#x2705; 500 条数据     |   &#x2705;  |   &#x2705;   |   &#x2705;     |  &#x2705;    |   &#x2705; |   &#x2705;     |   &#x1f504;  |
|  AutoDAN  |  &#x2705; 600 条数据  |   &#x2705;  |   &#x2705;   |   &#x2705;     |  &#x2705;    |   &#x2705;  |   &#x2705;     |   &#x1f504;   |
|  GCG      |   &#x23f3;     |   &#x23f3;  |   &#x23f3;   |   &#x23f3;    |  &#x23f3;   |   &#x23f3;  |   &#x23f3;     |   &#x274c;  |
|  GPTFuzz  |   &#x23f3;     |   &#x23f3;  |   &#x23f3;   |  &#x23f3;     | &#x23f3;   |   &#x23f3;  |   &#x23f3;     |  &#x274c;  |  



| -       | 假设类  |||| 注意力转移类   ||| 特权模式 |
| :-----: | :-----:    | :-----:  | :-----:    | :-----:    | :-----:    | :-----:  | :-----:     | :-----: |
| -       | 场景假设	  | 角色假设  |  责任假设  | 科学实验假设 | 文本续写   |  语序颠倒 | 多语种与翻译 | 特权模式 |
|  TAP      |   &#x2705; 500 条数据     |   &#x2705;  |   &#x2705;   |   &#x2705;     |  &#x2705;    |   &#x2705; |   &#x2705;     |   &#x1f504;  |
|  AutoDAN  |  &#x2705; 600 条数据  |   &#x2705;  |   &#x2705;   |   &#x2705;     |  &#x2705;    |   &#x2705;  |   &#x2705;     |   &#x1f504;   |
|  GCG      |   &#x23f3;     |   &#x23f3;  |   &#x23f3;   |   &#x23f3;    |  &#x23f3;   |   &#x23f3;  |   &#x23f3;     |   &#x274c;  |
|  GPTFuzz  |   &#x23f3;     |   &#x23f3;  |   &#x23f3;   |  &#x23f3;     | &#x23f3;   |   &#x23f3;  |   &#x23f3;     |  &#x274c;  |  



### 3.3 数据集分配				

将数据集按照7:2:1分配为训练集``trian.zip``、测试集``test.zip``和验证集``val.zip``。

``trian.zip`` 下载地址： https://huggingface.co/

``test.zip`` 下载地址： https://huggingface.co/

``val.zip`` 下载地址： https://huggingface.co/

### 3.4 数据文件命名

每个数据集中包括多个``.txt``文件，按 ``A_B_C.txt``方式命名，其中：

* A表示：提示注入方法名称，包括：场景假设、文本续写等；

* B表示：提示注入生成算法命名称，包括：AutoDAN、TAP等；

* C表示：用于生成用例的基础模型名称，包括：DeepSeekR1、Qwen2.5等。

## 4. AI安全防护围栏核心模型

### 4.1 关键技术

我们基于 Transformer 和 Bert 架构，训练出多个分类模型，进行综合决策，用于识别大模型的输入是否被恶意攻击、输出是否异常，是否应该需要进行过滤和发出警告。对提升模型精度，我们对现有的通用算法进行了一些技术改进。

#### 蒸馏技术

利用蒸馏技术，准确率提升了XX%。

#### 基于人类强化学习

通过RLHF技术，不断生成高质量数据语料，自动化进行筛选和标注。采用RLHF技术，准确率提升了XX%。

#### 稀疏混合专家模型 MoE

利用混合专家模型MoE方法，构建一个稀疏的模型，进行综合决策。采用MoE方法，准确率提升了XX%。


### 4.2 模型版本

生成的模型包括：``Base版(XX B)``、``Large版（XX B）``，``Small版(XX B)``等，其中Base版开源供测试对比，``Large版（XX B）``，``Small版(XX B)``作为商用化产品的核心引擎。


| 模型名称   | 模型版本  |  备注  | 下载链接  | 
| --------  | -----:  | :----:  |  :----:  |
| QianMo商用 Large版   | XX B |  作为商用产品内核  | |
| QianMo商用 Small版   | XX B |  作为商用产品内核  | |
| QianMo开源版    | XX B  |  开源版 | https://huggingface.co/ |
| QianMo开源版    | XX B  |  开源版 | https://huggingface.co/ |
| QianMo开源版    | XX B  |  开源版 | https://huggingface.co/ |

## 5. 大模型安全防护效果评测

### 5.1 评测指标

我们采用业界通行的F1得分（又称平衡F得分）作为综合评价指标。F1得分平衡的精准率和召回率指标。F1得分的定义为：

$$F1=2 \times \frac{Precison \times Recall}{Precision + Recall}$$

其中， $$Precision$$ 是精准率， $$Recall$$ 是召回率，定义分别为：

$$Precision = \frac{TP}{TP+FP}$$

$$Recall = \frac{TP}{TP+FN}$$

| -     | 判断为真  |  判断不为真  |
| --------      | -----:  | :----:  |
| 事实为真    | TP  |  FN  |
| 事实不为真    | FP  |  TN  |

### 5.2 评测对比

我们选择当前国内外业界声称的Sota算法进行对比，包括：Llama Prompt Guard 2、等。

| 模型名称     | 模型体量 |  备注  |
| --------      | -----:  | :----:  |
| QianMo商用版  | XXM |  Ours, 商用  |
| QianMo开源版  | XXM |  Ours, 商用  |
| Llama Prompt Guard  2  | 22M |    |

### 5.3 评测结果

![图片](https://github.com/user-attachments/assets/5345f481-c4fc-4b40-a4e3-83881966fb5e)


## 6. 部署指南

### 6.1 安装最新版本

`` pip install git+https://github.com/XXX.git ``

### 6.2 启动服务

`` qianmo serve  ``

### 6.3 使用方法

## 7. 声明与使用协议

