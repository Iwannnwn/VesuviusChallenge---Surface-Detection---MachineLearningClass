# SegFormer with Brightness Handling for Papyrus Surface Detection
### Vesuvius Challenge

## 📌 Overview
This project implements a **segmentation framework** for **papyrus surface detection** in the **Vesuvius Challenge dataset**.  
The model is based on **SegFormer**, a transformer-based segmentation architecture, enhanced with **brightness-aware data augmentation** to handle illumination variability in ancient papyrus scans.

The goal is to accurately segment papyrus surface structures from grayscale volumetric images under varying brightness and contrast conditions.

---

## 🗂 Dataset
- **Dataset**: Vesuvius Challenge Dataset  
- **Input**: Grayscale papyrus image slices  
- **Ground Truth**: Binary surface masks  
- **Task**: Binary semantic segmentation (surface vs background)

---

## 🔄 Data Preprocessing & Augmentation

### Input Processing
- Image–mask pair loading
- Normalization

### Data Augmentation (Training Phase)
To improve robustness against illumination variations:
- **Brightness adjustment**
- **Contrast adjustment**
- **Flip & rotation**
- **Spatial cropping**

Augmentation is applied only during the training phase.

---

## 🧠 Model Architecture

### SegFormer Framework
The model uses **SegFormer**, which consists of:
- **Hierarchical Transformer Encoder**
- **Efficient Self-Attention**
- **Mix-FFN**
- **Overlap Patch Merging**
- **Lightweight MLP Decoder**

This design enables efficient learning from high-resolution images with reduced computational cost.

---

## ⚙️ Training Phase
- Input images pass through the SegFormer encoder–decoder architecture
- Multi-scale features are fused for segmentation
- Optimization is performed using supervised learning with ground truth masks

---

## 🔍 Inference
During inference:
- Input image → SegFormer
- Output → Predicted papyrus surface segmentation mask

---

## 📊 Evaluation Metric

### Surface Dice Score
Model performance is evaluated using **Surface Dice**, which measures boundary-level similarity between predicted and ground truth surfaces.

This metric is particularly suitable for **thin surface structures** and fine-grained segmentation tasks.

---

## 🛠 Tech Stack
- Python  
- PyTorch  
- SegFormer  
- OpenCV / Albumentations  
- NumPy  

## 📈 Results
- Improved robustness to illumination changes
- Accurate surface boundary detection
- Stable segmentation performance across varying brightness conditions

## 📜 Reference
Xie, E., Wang, W., Yu, Z., Anandkumar, A., Alvarez, J. M., & Luo, P.  
**SegFormer: Simple and Efficient Design for Semantic Segmentation with Transformers**  
NeurIPS 2021.
