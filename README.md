# 🌿 AI Plant Disease Detection

An AI-powered plant disease detection system that runs entirely in **Google Colab**. Upload a photo of a plant leaf and get an instant diagnosis with treatment recommendations.

![Python](https://img.shields.io/badge/Python-3.10-blue?style=flat-square&logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?style=flat-square&logo=tensorflow)
![Colab](https://img.shields.io/badge/Google_Colab-Ready-yellow?style=flat-square&logo=googlecolab)
![Dataset](https://img.shields.io/badge/Dataset-PlantVillage-green?style=flat-square)

---

## 🚀 Quick Start

1. Click the badge below to open in Colab:

   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

2. Run all cells top to bottom (`Runtime → Run all`)
3. Upload your plant leaf image when prompted
4. Get your diagnosis instantly!

---

## 🔬 What It Does

| Step | Description |
|------|-------------|
| 📷 Upload | User uploads one or more leaf images directly in Colab |
| 🧠 Inference | MobileNetV2 backbone classifies the image into 38 disease classes |
| 📊 Visualise | Top-3 predictions shown as a confidence bar chart |
| 💊 Treatment | Disease name, recommended treatment, medicine, and care advice displayed |

---

## 🌱 Supported Plants & Diseases (38 Classes)

| Plant | Conditions Detected |
|-------|-------------------|
| 🍎 Apple | Apple Scab, Black Rot, Cedar Apple Rust, Healthy |
| 🌽 Corn | Cercospora Leaf Spot, Common Rust, Northern Leaf Blight, Healthy |
| 🍇 Grape | Black Rot, Esca, Leaf Blight, Healthy |
| 🍅 Tomato | Bacterial Spot, Early Blight, Late Blight, Leaf Mold, Septoria Leaf Spot, Spider Mites, Target Spot, Yellow Leaf Curl Virus, Mosaic Virus, Healthy |
| 🥔 Potato | Early Blight, Late Blight, Healthy |
| 🫑 Pepper | Bacterial Spot, Healthy |
| 🍑 Peach | Bacterial Spot, Healthy |
| + more | Blueberry, Cherry, Orange, Raspberry, Soybean, Squash, Strawberry |

---

## 🛠️ Tech Stack

- **Model**: MobileNetV2 (ImageNet pretrained backbone)
- **Fine-tuning**: PlantVillage dataset (~54,000 images, 38 classes)
- **Framework**: TensorFlow / Keras
- **Runtime**: Google Colab (free GPU supported)
- **Visualization**: Matplotlib

---

## 📁 Project Structure

```
plant-disease-detection/
│
├── plant_disease_detection.ipynb   # Main Colab notebook
└── README.md                       # This file
```

---

## 🔌 Using Your Own Model

In **Cell 3** of the notebook, three options are provided:

```python
# Option A: Mount Google Drive and load .h5
from google.colab import drive
drive.mount('/content/drive')
model = tf.keras.models.load_model('/content/drive/MyDrive/your_model.h5')

# Option B: Download via gdown (Google Drive public link)
import gdown
gdown.download('https://drive.google.com/uc?id=YOUR_FILE_ID', 'model.h5')
model = tf.keras.models.load_model('model.h5')

# Option C (default): ImageNet backbone (no fine-tuning)
model = build_model()
```

---

## 📊 Model Performance

| Metric | Value (fine-tuned on PlantVillage) |
|--------|------------------------------------|
| Accuracy | ~96% |
| Classes | 38 |
| Input Size | 224 × 224 px |

> ⚠️ Default model uses ImageNet weights only. Connect a fine-tuned checkpoint for accurate predictions.

---

## 📜 Dataset

[PlantVillage Dataset](https://www.kaggle.com/datasets/abdallahalidev/plantvillage-dataset) — open-access dataset of 54,306 healthy and diseased plant leaf images across 14 crop species.

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first.

---

## 📄 License

MIT License — free to use, modify, and distribute.
