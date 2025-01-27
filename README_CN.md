# Model-Lightweighting 🚀

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.10%2B-green)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.1+-red)](https://pytorch.org/)
[![Stars](https://img.shields.io/github/stars/yourusername/model-lightweighting?style=social)](https://github.com/yourusername/model-lightweighting)

> 模型轻量化实践项目 | 提供精简模型实现与训练优化方案

![Star Growth Chart](https://starchart.cc/uohzey/model-lightweighting.svg)

---

## 📌 核心要点
- 创建DataLoader时：
  - `shuffle=True`时可设置`num_workers`
  - `shuffle=False`时无需设置`num_workers`
- GPU内存不足解决方案：
  - 减小批量大小（batch size）
  - 使用梯度累计
  - 减小模型复杂度
  - 使用混合精度训练
  - 减小输入图像尺寸

---

## 📊 实验结果

| 数据集        | 模型架构            | 参数    | 任务           | 耗时                      | device      | CPU/GPU  | acc    |
| ------------- | ------------------- | ------- | -------------- | ------------------------- | ----------- | -------- | ------ |
| imagenet-mini | resnet-18-精简      | 20.36MB | classification | 3405.97s/68.12s per epoch | 3060 laptop | 40%/100% | 17%    |
| imagenet-mini | resnet-18-精简      | 44.1MB  | classification | 3635.38s/121.18 per epoch | 3060 laptop | 40%/100% | 19.35% |
| imagenet-mini | resnet-18-fine_tune | 44.6MB  | classification |                           | 3060 laptop |          | 70%    |

---

## 🧠 模型架构

### ResNet-18精简版 (20.36MB)



---

## 🛠️ 使用说明
1. 替换所有`yourusername`为GitHub用户名
2. 添加`requirements.txt`和`LICENSE`文件
3. Star增长图会在项目公开后自动生效

---

## 📜 更新日志
- 2025/01/26: 发布ResNet-18精简版基准测试
- 2025/01/25: 项目初始化

[![Star History Chart](https://api.star-history.com/svg?repos=uohzey/model-lightweighting&type=Date)](https://star-history.com/#yourusername/model-lightweighting)