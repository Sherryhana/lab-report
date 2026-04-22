# 🚗 基于 YOLOv11 的行人与车辆检测实验
> 深圳大学 · 人工智能课程实验项目  
> 报告人：李戎熙 | 学号：2023071078

---

## 📌 项目简介
本项目基于 **YOLOv11** 轻量级目标检测模型，完成了行人与车辆的检测任务。项目包含完整的数据集处理、模型训练、推理验证与结果分析流程，所有代码均在 CPU 环境下可复现。

---

## 📁 项目结构
```text
lab-report/
├── 2023071078 李戎熙 基于YOLOV11的行人与车辆检测.pdf  # 完整实验报告
├── best.pt                                               # 训练得到的最优模型权重
├── yolo11n.pt                                            # YOLOv11 官方预训练权重
├── train.py                                              # 模型训练脚本
├── infer.py                                              # 目标检测推理脚本
└── README.md                                             # 项目说明文档
🛠️ 环境搭建
1. 创建虚拟环境
bash
运行
conda create -n yolo11 python=3.10 -y
conda activate yolo11
2. 安装依赖
bash
运行
pip install ultralytics opencv-python
🚀 使用方法
1. 模型训练
修改 train.py 中的数据集路径和超参数，运行：
bash
运行
python train.py
训练结束后，最优模型会自动保存为 best.pt。
2. 目标检测推理
运行 infer.py 对图片或视频进行检测：
bash
运行
python infer.py
📊 实验说明
模型：YOLOv11n（轻量级版本，适配 CPU 训练）
数据集：公开行人与车辆检测数据集（Roboflow 平台）
训练配置：基础 epoch、批次大小设置，适配低配置设备
评估指标：box loss、cls loss、mAP 等
📝 实验报告
完整的实验流程、数据与分析，可参考：2023071078 李戎熙 基于 YOLOV11 的行人与车辆检测.pdf
✨ 项目亮点
全程 CPU 可运行，无需 GPU 环境
轻量级模型，训练成本低、上手快
完整的代码结构 + 详细实验报告，可直接作为课程作业提交
