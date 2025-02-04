# Model-Lightweighting 🚀

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.10%2B-green)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.1+-red)](https://pytorch.org/)
[![Stars](https://img.shields.io/github/stars/uohzey/model-lightweighting?style=social)](https://github.com/yourusername/model-lightweighting)

> 模型轻量化实践项目 | 提供精简模型实现与训练优化方案

[![Stargazers over time](https://starchart.cc/uohzey/Model-Lightweighting.svg?variant=adaptive)](https://starchart.cc/uohzey/Model-Lightweighting)

---

## 🛠️ 环境配置指南

### 1. 创建 Conda 环境

使用以下命令创建一个名为 `torch` 的 Python 3.10.16 环境：

```bash
conda create -n torch python=3.10.16 -y
conda activate torch
```

### 2. 安装依赖

根据 `requirements.txt` 安装依赖包，并指定 CUDA 12.1 版本：

```bash
pip install -r requirements.txt --extra-index-url https://download.pytorch.org/whl/cu121
```

## 📌 核心要点

- 创建DataLoader时：
  - `shuffle=True`时可设置`num_workers`
  - `shuffle=False`时不设置`num_workers`
- GPU内存不足解决方案：
  - 减小批量大小（batch size）
  - 使用梯度累计
  - 减小模型复杂度
  - 使用混合精度训练
  - 减小输入图像尺寸

---

## 📥 数据集下载

以下是项目中使用的数据集下载链接：

| 数据集名称    | 下载链接                                                     |
| ------------- | ------------------------------------------------------------ |
| COCO-2017     | [COCO-2017 Dataset](https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset) |
| ImageNet-Mini | [ImageNet-Mini Dataset](https://www.kaggle.com/datasets/ifigotin/imagenetmini-1000) |
| ImageNet-Tiny | [ImageNet-Tiny Dataset](https://www.kaggle.com/datasets/akash2sharma/tiny-imagenet) |

> 注意：下载数据集需要 Kaggle 账号，请先注册并登录。

## 📊 实验结果

| 数据集        | 模型架构            | 参数    | 任务           | 耗时                       | device      | CPU/GPU  | acc    |
| ------------- | ------------------- | ------- | -------------- | -------------------------- | ----------- | -------- | ------ |
| imagenet-mini | resnet-01           | 20.36MB | classification | 3405.97s/68.12s per epoch  | 3060 laptop | 40%/100% | 17%    |
| imagenet-mini | resnet-02           | 44.1MB  | classification | 3635.38s/121.18s per epoch | 3060 laptop | 40%/100% | 19.35% |
| imagenet-mini | resnet-18-fine_tune | 44.6MB  | classification | 8594.05s/859.4s per epoch  | 3060 laptop |          | 68.82% |

---

## 🧠 模型架构

### ResNet-01精简版 (20.36MB)

### ResNet-02精简版 (44.10MB)

### ResNet-18微调版 (44.95MB)

---

## 📜 更新日志

- 2025/02/04:环境配置
- 2025/01/30:DETR 模型学习
- 2025/01/27: ResNet-18 微调版基准测试
- 2025/01/26: ResNet 精简版基准测试
- 2025/01/25: 项目初始化

[![Star History Chart](https://api.star-history.com/svg?repos=uohzey/model-lightweighting&type=Date)](https://star-history.com/#uohzey/model-lightweighting&Date)

