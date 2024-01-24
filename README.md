# 计算机前沿技术课程研究报告
## 对论文《Spikformer: When Spiking Neural Network Meets Transformer, [ICLR 2023](https://openreview.net/forum?id=frE4fUwz_h)》的复现

## 原论文源码地址: [GitHub](https://github.com/ZK-Zhou/spikformer)

## 原论文引用
```
@inproceedings{
zhou2023spikformer,
title={Spikformer: When Spiking Neural Network Meets Transformer },
author={Zhaokun Zhou and Yuesheng Zhu and Chao He and Yaowei Wang and Shuicheng YAN and Yonghong Tian and Li Yuan},
booktitle={The Eleventh International Conference on Learning Representations },
year={2023},
url={https://openreview.net/forum?id=frE4fUwz_h}
}
```

### 实验环境
原论文源码和课程实验源码都是在PyTorch官方示例代码、Timm视觉开源库上修改而来，其中脉冲神经元使用SpikingJelly库实现。实验环境部分配置为：
apex == 0.9.10
cupy == 12.2.0
nvidia-cuda == 11.4
nvidia-cudnn == 8.5.0.96
python == 3.10.12
spiklingjelly == 0.0.0.0.14
timm == 0.6.13
torch == 2.0.1
torchvision == 0.15.2

### 使用方法

在cifar10.yml文件中配置超参数，并修改data_dir和dataset至数据集目录位置。
```
cd 代码路径
python train.py
```
构建模型的核心代码位于model.py中，使用注册器将模型类注册到Timm库训练框架中。