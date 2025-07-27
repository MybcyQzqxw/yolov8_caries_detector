# 基于YOLOv8神经网络的龋齿检测Web服务

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![YOLOv8](https://img.shields.io/badge/YOLOv8-Ultralytics-orange.svg)](https://github.com/ultralytics/ultralytics)

本仓库包含基于YOLOv8目标检测模型的Web服务，用于检测图像中的龋齿和其他牙齿疾病。此外，还包含了用于准备源数据集、训练模型和运行测试预测的脚本。

[English](README.md) | 中文

## ✨ 特性

- 🦷 **精确检测**: 使用YOLOv8检测龋齿、蛀洞和牙裂
- 🌐 **Web界面**: 简洁的上传和检测界面
- 📊 **实时预测**: 快速处理并显示检测结果
- 📓 **完整工具链**: 包含数据转换、训练和预测的完整Jupyter笔记本

## 🎯 演示

观看演示视频: https://youtu.be/OzpPIsxB_4U

## 📁 项目结构

```
yolov8_caries_detector/
├── convert.ipynb       # Supervisely到YOLOv8格式转换器
├── train.ipynb         # 模型训练代码
├── predict.ipynb       # 自定义图像预测和可视化代码
├── best.pt            # 训练好的YOLOv8模型（30个epochs）
├── object_detector.py  # Web服务后端
├── index.html         # Web服务前端
├── caries.jpg         # 示例龋齿图像
├── requirements.txt   # 项目依赖
└── README.md          # 项目说明
```

## 🚀 快速开始

### 环境要求

- Python 3.7+
- pip3

### 安装步骤

1. **克隆仓库**
   ```bash
   git clone https://github.com/MybcyQzqxw/yolov8_caries_detector.git
   cd yolov8_caries_detector
   ```

2. **创建环境并安装依赖**
   ```bash
   conda create -n yolov8_caries python=3.8 -y
   conda activate yolov8_caries
   pip install -r requirements.txt
   ```

### 运行Web服务

1. **确保必要文件位于同一目录**
   - `object_detector.py`
   - `index.html` 
   - `best.pt`

2. **启动服务**
   ```bash
   python object_detector.py
   ```

3. **访问Web界面**
   
   在浏览器中打开 **http://localhost:8080**，上传牙齿图像即可检测是否包含龋齿。

## 📖 使用说明

### Web界面检测
1. 启动Web服务后，在浏览器中访问 **http://localhost:8080**
2. 在上传区域点击"选择文件"按钮或直接拖拽图片文件
3. 选择牙齿图像文件（支持JPG、PNG、GIF格式）
4. 点击"🔍 开始检测"按钮进行分析
5. 等待检测完成，查看标注结果和检测统计信息

### Jupyter笔记本

- **`convert.ipynb`**: 将Supervisely格式数据集转换为YOLOv8格式
- **`train.ipynb`**: 使用转换后的数据集训练YOLOv8模型
- **`predict.ipynb`**: 在自定义图像上运行预测并可视化结果

## 📊 数据集

本项目使用DentalAI数据集进行模型训练。您可以从以下地址下载：
https://datasetninja.com/dentalai

如果要运行自己的训练过程，需要使用 `convert.ipynb` 笔记本中的脚本将数据集转换为YOLOv8格式。

## 🔧 模型信息

- **模型架构**: YOLOv8
- **训练轮次**: 30 epochs
- **检测类别**: 
  - 龋齿 (Caries)
  - 蛀洞 (Cavity) 
  - 牙裂 (Cracks)

## 📝 详细教程

阅读详细技术文章了解代码创建和工作原理：
[Teeth caries detection using YOLOv8 neural network](https://dev.to/andreygermanov/teeth-caries-detection-using-yolov8-neural-network-3fap)

## 🤝 贡献

欢迎提交问题和拉取请求！如果您想为项目做出贡献，请：

1. Fork 本仓库
2. 创建您的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交您的更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个拉取请求

## 📄 许可证

本项目采用 MIT 许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 📧 联系方式

如有问题或建议，请通过以下方式联系：

- 创建 [Issue](https://github.com/MybcyQzqxw/yolov8_caries_detector/issues)
- 提交 [Pull Request](https://github.com/MybcyQzqxw/yolov8_caries_detector/pulls)

## 🌟 致谢

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) - 强大的目标检测框架
- [DentalAI Dataset](https://datasetninja.com/dentalai) - 提供优质的牙齿疾病数据集

---

⭐ 如果这个项目对您有帮助，请给我们一个星标！
