# 基于YOLOv11的行人与车辆检测实验

这是深圳大学《人工智能》课程的一个实验项目，旨在通过完整的实践流程，掌握最新的YOLOv11目标检测模型在低配置硬件（CPU）上的训练与部署。

## 🎯 项目亮点
低门槛：无需GPU，在CPU上即可完成从环境配置到模型推理的全流程。

流程完整：涵盖数据准备、模型训练、评估与验证的完整实践。

即拿即用：提供简洁、可直接运行的训练与推理脚本。

## ⚙️ 环境配置与数据准备
1. 创建虚拟环境
conda create -n yolo11 python=3.10 -y
conda activate yolo11
pip install ultralytics
2. 获取数据集
本实验使用来自 Roboflow的公开数据集。
搜索关键词：vehicle pedestrian detection
格式选择：YOLOv11
数据规模：约1,464张已标注图片

## 📁 项目结构
将数据集下载并解压后，建议的目录结构如下：
Your_Project/

├── dataset/

│   ├── data.yaml

│   ├── train/

│   ├── valid/

│   └── test/

├── train.py

├── infer.py

└── README.md


## 🧰 环境配置

conda create -n ai_env python=3.8

conda activate ai_env

pip install ultralytics opencv-python


## 📊 实验结果
在CPU环境下训练10个epoch后，模型在验证集上的主要评估指标如下：

| Epoch | box_loss | cls_loss | mAP@0.5 | mAP@0.5:0.95 |
| :---- | :------- | :------- | :------ | :----------- |
| 2     | 1.810    | 2.357    | 0.246   | 0.125        |
| 5     | 1.758    | 2.131    | 0.250   | 0.144        |
| 8     | 1.545    | 1.739    | 0.358   | 0.216        |
| **10**| **1.428**| **1.594**| **0.377**| **0.235**    |

最终精度：模型在IoU阈值为0.5时的平均精度（mAP@0.5）达到 0.377。

## 💡 实验发现与总结
硬件友好性：通过设置较小的输入尺寸(imgsz=416)和批次大小(batch=4)，成功在CPU上完成了训练（约30-60分钟），证明了该方案在低配环境下的可行性。

数据便捷性：利用Roboflow等公开数据集平台，可以跳过繁琐的数据标注工作，快速启动项目。

模型轻量化：YOLOv11n (nano) 模型参数量小，非常适合在资源受限的设备上进行原型验证和快速实验。

优化方向：实验结果表明，在CPU上短时间训练能达到初步可用精度。若需更高精度，可在GPU环境（如Google Colab）上增加训练轮次(epochs)和图像尺寸(imgsz)。检测，结果将保存在 `runs/detect/predict/` 目录下。
