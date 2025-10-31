# 🧠 Structural Damage Segmentation using R2-U-Net

## 📘 Project Overview

This project implements a **Recurrent Residual U-Net (R2-U-Net)** model for **multiclass semantic segmentation** of structural damage on concrete surfaces.  
It can detect and segment **cracks**, **exposed rebars**, and **structural components** such as walls, beams, columns, slabs, and balconies from a single image.

The pipeline is designed for complex datasets (e.g., ICSHM 2021 Challenge), where multiple annotation folders are dynamically combined into a single **11-class segmentation mask** during training.  
This enables simultaneous detection of damages and structural components, supporting **automated inspection** and **structural health monitoring**.

---

## 🧱 Model Overview

The model is based on the **R2-U-Net** architecture — an enhanced version of U-Net that introduces **recurrent residual connections** using `ConvLSTM2D` layers.

### 🏗️ Key Components
- **Encoder:** Uses `recurrent_conv_block` where one convolution layer is replaced with `ConvLSTM2D`, enabling the model to capture both **spatial** and **sequential** patterns within images.
- **Decoder:** Standard U-Net upsampling path with skip connections to reconstruct fine structural details.
- **Loss Function:** Custom **Dice Loss**, designed for multiclass segmentation while ignoring “Background” and “Ignore” pixels.
- **Metrics:** Includes `dice_coefficient` and `MeanIoU` to evaluate segmentation accuracy across all classes.

### 🎯 Advantages
- Captures **linear and textured features** of cracks and rebars effectively.  
- Handles **multiple damage types and components** in one unified segmentation map.  
- Provides **robust, interpretable**, and **traceable** performance aligned with data quality principles from **ISO/IEC 17025**.

---

## 🧠 Outcome

The R2-U-Net pipeline strengthens **automated visual inspection**, ensuring higher consistency, reliability, and scalability in structural damage assessment.  
It also lays the foundation for future work in **AI-driven damage prediction** and **real-time inspection systems**.
