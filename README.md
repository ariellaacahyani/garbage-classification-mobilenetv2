# ♻️ EcoVision: Garbage Classification using MobileNetV2 

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00.svg?logo=tensorflow)
![Computer Vision](https://img.shields.io/badge/Domain-Computer_Vision-success)

## 📌 Project Overview
This project implements a robust Image Classification model designed to detect and categorize **12 different classes** of garbage/waste. Built with edge deployment in mind, the model utilizes **MobileNetV2** as its base architecture, leveraging Transfer Learning to achieve high accuracy while maintaining a lightweight footprint suitable for mobile and web applications.

## 🗂️ Dataset (The 12 Classes)
<!-- Catatan: Silakan ganti list di bawah ini dengan 12 kelas sampah kamu yang sebenarnya -->
The model is trained to recognize the following categories:
`Battery` | `Biological` | `Brown Glass` | `Cardboard` | `Clothes` | `Green Glass` | `Metal` | `Paper` | `Plastic` | `Shoes` | `Trash` | `White Glass`

## 🧠 Model Architecture & Training Strategy
* **Base Model**: MobileNetV2 (Pre-trained on ImageNet).
* **Approach**: Feature Extraction followed by Fine-Tuning on the top layers to adapt to the specific visual features of the waste dataset.
* **Optimization**: Implemented callbacks such as `ReduceLROnPlateau` and `EarlyStopping` to ensure strong generalization and mitigate overfitting.

## 📊 Performance Metrics
The model demonstrates excellent generalization with a minimal gap between training and unseen data:
* **Training Accuracy**: ~98.82%
* **Validation Accuracy**: ~95.66%
* **Test Accuracy**: ~95.84%

*(Optional: You can insert your loss/accuracy plot image here)*
<!-- ![Accuracy Plot](link-to-your-image.png) -->

## 🚀 Deployment Formats
To support various production environments, the model has been exported into three standard formats:
1. **SavedModel** (`/saved_model`): Standard TensorFlow format containing the `.pb` file and variables for backend serving.
2. **TensorFlow Lite (TFLite)** (`/tflite`): Optimized flatbuffer model (`model.tflite`) accompanied by `label.txt` for mobile and IoT edge inference.
3. **TensorFlow.js (TFJS)** (`/tfjs_model`): Web-ready model format. The weights have been dynamically sharded into exactly 5 `.bin` files to optimize parallel downloading and client-side load times in the browser.

## 🛠️ Quick Start & Installation

**1. Clone the repository**

```bash
git clone https://github.com/ariellaacahyani/garbage-classification-mobilenetv2.git
cd garbage-classification-mobilenetv2
```
