# 🌾 Agriculture Vision: AI-Powered Computer Vision for Modern Agriculture

<div align="center">

[![Bahasa Indonesia](https://img.shields.io/badge/Language-Bahasa_Indonesia-blue.svg)](README.md)
[![English](https://img.shields.io/badge/Language-English-red.svg)](#)

**[ [Indonesian Version](README.md) ]** | **[ English ]**

---

![License MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue.svg)
![Frameworks](https://img.shields.io/badge/Frameworks-PyTorch%20%7C%20TensorFlow%20%7C%20OpenCV-orange.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8%20%2F%20v11-green.svg)

</div>

Welcome to **Agriculture Vision**, a curated repository containing end-to-end Computer Vision (AI) solutions, models, research experiments, and datasets applied to smart farming and precision agriculture.

This repository serves as a centralized hub for applying deep learning techniques to crop monitoring, disease classification, weed management, yield estimation, and aerial farm analysis.

---

## 📌 Table of Contents

* [Project Overview](#-project-overview)
* [Key Domains & Applications](#-key-domains--applications)
* [Repository Structure](#-repository-structure)
* [Featured Sub-Projects](#-featured-sub-projects)
* [Tech Stack & Tools](#-tech-stack--tools)
* [Getting Started](#-getting-started)
  * [Prerequisites](#prerequisites)
  * [Installation](#installation)
* [Model Deployment](#-model-deployment)
* [Contributing](#-contributing)
* [License](#-license)
* [Contact & Acknowledgments](#-contact--acknowledgments)

---

## 🔍 Project Overview

Precision agriculture relies heavily on actionable data. By leveraging state-of-the-art Computer Vision algorithms, **Agriculture Vision** aims to digitize field assessments, reduce agricultural input waste (pesticides, fertilizers), and maximize crop yield through real-time automated visual inspection.

### Core Objectives:

1. **Early Disease Detection**: Rapid identification of plant pathogens to mitigate crop damage.
2. **Precision Weed Management**: High-precision semantic segmentation to enable localized herbicide spraying.
3. **Automated Yield Forecasting**: Object detection and tracking to count fruits, vegetables, and flowers in real time.
4. **Aerial Agricultural Intelligence**: Multispectral and RGB satellite/drone image processing for large-scale field health checks.

---

## 🌿 Key Domains & Applications

| Domain | Computer Vision Task | Common Architectures / Models |
| :--- | :--- | :--- |
| **Plant Pathology** | Multi-class Image Classification, Bounding Box Detection | ResNet, Vision Transformer (ViT), EfficientNet, YOLOv8 |
| **Weed Identification** | Semantic & Instance Segmentation | U-Net, DeepLabV3+, Mask R-CNN |
| **Harvest Automation** | Object Detection, Multi-Object Tracking (MOT) | YOLOv8/v11, ByteTRACK, Faster R-CNN |
| **Remote Sensing** | Change Detection, Land Cover Classification | SegFormer, Swin Transformer, Random Forest (GIS) |

---

## 📂 Repository Structure

```text
agriculture-vision/
│
├── 01-plant-disease-detection/    # Disease classification and localization models
│   ├── notebooks/                # Training and EDA Jupyter Notebooks
│   ├── models/                   # Saved weight files (.pt, .h5, .onnx)
│   └── src/                      # Source code for training & inference
│
├── 02-crop-weed-segmentation/    # Pixel-level segmentation for precision spraying
│   ├── configs/                  # Model configurations
│   └── src/                      # U-Net & DeepLab implementation scripts
│
├── 03-fruit-detection-counting/  # Real-time yield estimation and fruit tracking
│   ├── tracking/                 # Multi-object tracking implementation
│   └── inference/                # Real-time camera stream scripts
│
├── 04-aerial-crop-monitoring/    # Satellite and drone image processing
│   ├── raster_processing/        # GIS & NDVI calculation tools
│   └── notebooks/                # Satellite imagery analysis
│
├── data/                         # Sample datasets and data pipeline scripts
├── deployment/                   # REST API, Dockerfile, and Web App scripts
├── docs/                         # Extended documentation, diagrams, and paper notes
├── .gitignore                    # Python gitignore configuration
├── LICENSE                       # MIT License
├── README.md                     # Main repository documentation (Bahasa Indonesia)
├── README.en.md                  # English version documentation
└── requirements.txt              # Global Python dependencies
```

---

## 🚀 Featured Sub-Projects

### 1. Plant Leaf Disease Classifier 🍃
* **Goal**: Detect up to 38 plant disease classes from leaf imagery using CNNs and Vision Transformers.
* **Accuracy**: ~98.2% test accuracy on standard benchmark datasets.
* **Quick Run**:
  ```bash
  python 01-plant-disease-detection/src/predict.py --image path/to/leaf.jpg
  ```

### 2. Crop vs. Weed Real-Time Segmentor 🌾
* **Goal**: Separate crops from intrusive weeds under varying lighting conditions to drive robotic weeders.
* **Method**: U-Net architecture trained on high-resolution field imagery.

### 3. Automated Fruit Counter & Weight Estimator 🍎
* **Goal**: Detect and count ripe/unripe apples and tomatoes on trees with object tracking to avoid double counting.
* **Method**: YOLOv8 + ByteTRACK pipeline with bounding box density analysis.

---

## 🛠️ Tech Stack & Tools

* **Core Language**: Python 3.11+
* **Deep Learning Frameworks**: PyTorch, TensorFlow, Keras
* **Computer Vision**: OpenCV, Ultralytics (YOLO), Albumentations
* **Geospatial & Remote Sensing**: Rasterio, GeoPandas, QGIS, Google Earth Engine API
* **Deployment & MLOps**: Streamlit, FastAPI, Docker, ONNX Runtime

---

## 🏁 Getting Started

### Prerequisites

Make sure you have `git`, `Python 3.11+`, and `pip` installed on your system. GPU support (CUDA) is recommended for training models.

### Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/syakiroke/agriculture-vision.git
   cd agriculture-vision
   ```

2. **Create and Activate a Virtual Environment**:
   * **Linux/macOS**:
     ```bash
     python -m venv venv
     source venv/bin/activate
     ```
   * **Windows**:
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

---

## 🌐 Model Deployment

This repository includes deployment templates for real-world field deployment:

* **Web Application (Streamlit)**: Launch a lightweight web interface for model demonstration.
  ```bash
  streamlit run deployment/streamlit_app/app.py
  ```

* **REST API (FastAPI)**: Serve model endpoints for edge device integrations (e.g., Raspberry Pi, Jetson Nano).
  ```bash
  uvicorn deployment.fastapi_app.main:app --reload
  ```

---

## 🤝 Contributing

Contributions make the open-source community an incredible place to learn, inspire, and create. Any contributions you make are **greatly appreciated**!

1. Fork the Project.
2. Create your Feature Branch (`git checkout -b feature/NewAgricultureModel`).
3. Commit your Changes (`git commit -m 'Add new YOLOv11 leaf detection model'`).
4. Push to the Branch (`git push origin feature/NewAgricultureModel`).
5. Open a Pull Request.

---

## 📜 License

Distributed under the **MIT License**. See `LICENSE` for more information.

---

## 📬 Contact & Acknowledgments

* **Author**: Syakir ([@syakiroke](https://github.com/syakiroke))
* **Domain**: Artificial Intelligence in Agriculture / Computer Vision
* **Special Thanks**: Open-source datasets provided by PlantVillage, Roboflow, and various Agricultural AI researchers worldwide.