# Model-Lightweighting 🚀

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.10%2B-green)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.1+-red)](https://pytorch.org/)
[![Stars](https://img.shields.io/github/stars/uohzey/model-lightweighting?style=social)](https://github.com/uohzey/model-lightweighting)

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

以下是项目中使用的数据集：

- **COCO-2017**
  [COCO-2017 Dataset](https://www.kaggle.com/datasets/awsaf49/coco-2017-dataset)

- **ImageNet-Mini**
  [ImageNet-Mini Dataset](https://www.kaggle.com/datasets/ifigotin/imagenetmini-1000)

- **ImageNet-Tiny**
  [ImageNet-Tiny Dataset](https://www.kaggle.com/datasets/akash2sharma/tiny-imagenet)

- **emotion**

  ```python
  from datasets import load_dataset
  
  emotions = load_dataset("emotion")
  ```

> 注意：部分下载数据集需要 Kaggle 账号，请先注册并登录。

## 📊 实验结果

| 数据集        | 模型架构              | 参数    | 任务                  | device      | acc    | huggingface_hub                                              |
| ------------- | --------------------- | ------- | --------------------- | ----------- | ------ | ------------------------------------------------------------ |
| imagenet-mini | resnet-01             | 20.36MB | imaghe classification | 3060 laptop | 17%    |                                                              |
| imagenet-mini | resnet-02             | 44.1MB  | image classification  | 3060 laptop | 19.35% |                                                              |
| imagenet-mini | resnet18-fine-tune    | 44.6MB  | image classification  | 3060 laptop | 68.82% |                                                              |
| emotion       | distilbert-fine-tune  | 268 MB  | text classification   | Tesla P100  | 89%    | [distilbert-base-uncased-finetuned-emotion ](https://huggingface.co/uohzey/distilbert-base-uncased-finetuned-emotion) |
| panx_ch       | xlm-roberta-fine-tune | 1.11GB  | ner                   | Tesla P100  | 86.46% | [xlm-roberta-base-finetuned-panx-de](https://huggingface.co/uohzey/xlm-roberta-base-finetuned-panx-de) |



---

## 🧠 模型架构

### ResNet-01精简版 (20.36MB)

### ResNet-02精简版 (44.10MB)

### ResNet-18微调版 (44.95MB)

### distilbert微调版(268MB)

### xlm-roberta微调版(1.11GB)

---

## 📜 更新日志

- 2025/02/15: Natural Language Processing with Transformer: Multilingual Named Entity Recognition
- 2025/02/14: Natural Language Processing with Transformer: Transformer Anatomy
- 2025/02/12: Natural Language Processing with Transformer: Text Classification
- 2025/02/04: 环境配置
- 2025/01/30: DETR 模型学习
- 2025/01/27: ResNet-18 微调版基准测试
- 2025/01/26: ResNet 精简版基准测试
- 2025/01/25: 项目初始化

[![Star History Chart](https://api.star-history.com/svg?repos=uohzey/model-lightweighting&type=Date)](https://star-history.com/#uohzey/model-lightweighting&Date)

