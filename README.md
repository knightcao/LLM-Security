# 大模型安全防护围栏

## 最新动态

2025.6.20 项目开源启动。

## 概述

大模型安全防护围栏



## 大模型面临的潜在风险

### 风险类型

* 生成内容合规

   人工智能生成内容涉及政治敏感、违反中国法律法规或不符合主流道德观念等。
   
* 生成歧视性内容。

    人工智能生成内容在种族、性别、地域、职业等维度是否可能生成带有偏见、贬低或攻击性言论。

* 其它风险

    其它见《生成式人工智能服务安全基本要求》（TC260-003）。

### 提示注入攻击的逻辑方法

* 假设

* 注意力转移 

* 特权模式

### 提示注入攻击的生成算法

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



## AI安全数据集


| 防护类别      | 防护子类  |  功能描述  |
| - | 场景假设	  | 角色假设  |  责任假设  | 科学实验假设 | 文本延续	|  语序颠倒 | 多语种与翻译 | 特权模式 |
| ----  | --------    | -----    |  ----     |  ----       | ----      |  ----    |  ----       | ----     |
|  TAP  |   -[x]     |   - [ ]  |   - [x]   |   - [x]     |  - [x]    |   - [x]  |   - [x]     |   - [x]  |
|  AutoDAN  |   -[x]     |   - [ ]  |   - [x]   |   - [x]     |  - [x]    |   - [x]  |   - [x]     |   - [x]  |
|  GCG  |   -[x]     |   - [ ]  |   - [x]   |   - [x]     |  - [x]    |   - [x]  |   - [x]     |   - [x]  |
|  GPTFuzz  |   -[x]     |   - [ ]  |   - [x]   |   - [x]     |  - [x]    |   - [x]  |   - [x]     |   - [x]  |  

阡陌*大模型安全评测数据集v1.0								
	假设类				迁移类			权限类
	场景假设	角色假设	责任假设	科学实验假设	文本延续	语序颠倒Flip	多语种与翻译	特权模式
TAP	例：场景假设_TAP_DeepSeekR1.txt  	S	S	S	S	S	S	S
AutoDAN	S	S	S	S	S	S	S	S
GCG	S	S	S	S	S	S	S	S
GPTFuzz	S	S	S	S	S	S	S	S
								
![图片](https://github.com/user-attachments/assets/473930f5-d01c-4fa6-a8fb-c85b420f9d5d)					




## AI安全防护围栏核心模型

| 防护类别      | 防护子类  |  功能描述  |
| --------      | -----:  | :----:  |
| 内容合规防护   | 违反社会主义核心价值观   |  检测问答内容是否涉及政治敏感、违反中国法律法规或不符合主流道德观念，确保输出符合国家政策与社会价值导向     |
|  --           |   歧视性内容   |  检测问答内容在种族、性别、地域、职业等维度是否可能生成带有偏见、贬低或攻击性言论，保障内容包容性与公平性   |
| 提示注入攻击防护 |    $1    |  234  |




## 提示注入防护效果评测


![图片](https://github.com/user-attachments/assets/5345f481-c4fc-4b40-a4e3-83881966fb5e)


## 部署指南

## 声明与使用协议

