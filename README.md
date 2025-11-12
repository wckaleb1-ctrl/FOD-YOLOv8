# 🌊 FOD-YOLOv8: Enhanced YOLOv8 for Floating Object Detection on Water Surfaces

FOD-YOLOv8 is an improved YOLOv8-based detection framework designed for **robust and precise detection of floating objects on water surfaces**.  
The model enhances YOLOv8n through three key structural modules — **SPDConv**, **CSP_DCNv2CoordConv**, and **C2S_Upsample** — to address challenges such as small-object loss, reflection interference, and multi-scale feature degradation.

---

## 🔍 Model Overview

To address the challenges of small-object detection, visual similarity, and complex water-surface disturbances, our model introduces three key structural improvements based on YOLOv8n — forming the **FOD-YOLOv8 architecture**:

### 1️⃣ SPDConv Module (Sparse and Dynamic Convolution)
Enhances contextual feature extraction through multi-branch sparse convolution and adaptive fusion.  
By dynamically weighting different feature branches, SPDConv improves the model’s ability to discriminate between **visually similar debris categories** (e.g., glass vs. plastic bottles) and retains fine-grained details during downsampling.

### 2️⃣ CSP_DCNv2CoordConv Module
Integrates **Deformable Convolution v2 (DCNv2)** and **Coordinate Convolution (CoordConv)** to strengthen **spatial perception and adaptability** under dynamic lighting and wave disturbances.  
This combination allows the model to adjust to irregular object shapes and illumination variations, significantly improving robustness against **glare, ripples, and deformation** on complex water surfaces.

### 3️⃣ C2S_Upsample Module (Channel-to-Spatial Upsample)
Achieves **cross-scale feature fusion** and **super-resolution reconstruction** during upsampling.  
By reorganizing multi-level features and preserving high-frequency information, it enhances detection performance on **small and distant floating objects**, maintaining clear boundaries and high confidence even under multi-angle perspectives.

> Together, these three modules enable FOD-YOLOv8 to achieve superior precision, recall, and mAP performance compared to standard YOLOv8n, with improved robustness in small-object detection, reflection suppression, and class discrimination across diverse water environments.

---

<div align="center">
  <img width="1000" alt="FOD-YOLOv8 Framework" src="https://github.com/user-attachments/assets/5e05bb55-cf37-4e4e-87b3-4f51703a517f" />
  <br>
  <em>Figure 1. Overall framework of FOD-YOLOv8 showing backbone, neck, and enhanced modules.</em>
</div>

---

## 🧩 Model Architecture

The main components of **FOD-YOLOv8** are illustrated below.

<div align="center">
  <img width="1000" alt="SPDConv Module" src="https://github.com/user-attachments/assets/485d8ed1-15a2-4c96-a805-6923fefb1fe7" />
  <br>
  <em>Figure 2. SPDConv module — multi-branch sparse convolution and dynamic fusion for fine-grained feature extraction.</em>
</div>

<div align="center">
  <img width="1000" alt="CSP_DCNv2CoordConv Module" src="https://github.com/user-attachments/assets/ad04931c-a8c8-4ecd-a8a4-27d0b76f9f3d" />
  <br>
  <em>Figure 3. CSP_DCNv2CoordConv module — integrating deformable and coordinate convolution to enhance spatial perception under complex illumination.</em>
</div>

<div align="center">
  <img width="1000" alt="C2S_Upsample Module" src="https://github.com/user-attachments/assets/1410000f-488d-4086-a0f7-a6ced61e81b7" />
  <br>
  <em>Figure 4. C2S_Upsample module — channel-to-spatial reconstruction and multi-scale fusion for high-resolution feature recovery.</em>
</div>

---

## 📂 Dataset

The dataset used in this study includes **12,000 labeled images** of eight major categories of floating objects:

| Class | Description |
|:------|:-------------|
| Plastic | Bottles, containers, films |
| Glass | Transparent bottles, fragments |
| Metal | Cans, sheets |
| Wood | Branches, planks |
| Rubber | Tires, fragments |
| Foam | Styrofoam, packing materials |
| Net | Fishing nets, ropes |
| Bag | Plastic and woven bags |

**Composition:**
- Public **Roboflow floating-object dataset**  
- Self-collected images from **Nantong canal gates**  
- Synthetic samples generated using **Stable Diffusion 3**  
- Split ratio: **Train 70% / Val 20% / Test 10%**
## 📦 Dataset & Code Access

The repository includes core implementation code and dataset references for FOD-YOLOv8.
The dataset and code can be accessed via Baidu Cloud:

🔗 Link: https://pan.baidu.com/s/1609oL4m8EkIzFu_JmccuMA?pwd=srx6

🔑 Extraction Code: srx6
---

## ⚙️ Environment Setup

```bash
# Recommended environment
Python 3.10
PyTorch 1.13.1
CUDA 11.6
NVIDIA Tesla T4 GPU

# Install dependencies
pip install -r requirements.txt


