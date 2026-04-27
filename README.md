# 🏥 Leveraging Semi-Supervised Learning for Multimodal Medical Image Classification with Paired CT and MRI

> **📄 Published at ICCIT 2025 — International Conference on Computer and Information Technology**  
> **Author:** Faria Azad Anita | East West University, Dhaka, Bangladesh

---

## 📌 Overview

Medical image classification is a critical task in clinical diagnosis. However, acquiring large amounts of **labeled medical data** is expensive and time-consuming. This research leverages **Semi-Supervised Learning (SSL)** to classify multimodal medical images — **CT scans, T1-MRI, and T2-MRI** — using both labeled and unlabeled data.

Multiple SSL algorithms and backbone architectures are compared to find the most data-efficient and accurate approach for multimodal medical image classification.

---

## 🏆 Published Research

| Detail | Info |
|--------|------|
| 📄 Paper Title | Leveraging Semi-Supervised Learning for Multimodal Medical Image Classification with Paired CT and MRI |
| 🏛️ Conference | ICCIT 2025 (International Conference on Computer and Information Technology) |
| 🎓 Institution | East West University, Dhaka, Bangladesh |
| 👩‍💻 Author | Faria Azad Anita |

---

## 🗃️ Dataset

**Paired MRI (T1, T2) and CT Scans Dataset**

| Modality | Description |
|----------|-------------|
| CT | Computed Tomography scans |
| T1-MRI | T1-weighted MRI scans |
| T2-MRI | T2-weighted MRI scans |

📥 Dataset: [Kaggle — Paired MRI and CT Scans Dataset](https://www.kaggle.com/datasets/fariaanita/pared-ct-scan-and-mri-1)

---

## 🏗️ Models Compared

### Supervised Backbone Models
| Model | Type |
|-------|------|
| ConvNeXt-Tiny | CNN (timm) |
| MobileNetV3-Large | Lightweight CNN |
| DenseNet121 | Dense CNN |
| ViT (Vision Transformer) | Transformer |
| ResNet | Classic CNN |

### Semi-Supervised Learning (SSL) Algorithms
| Algorithm | Description |
|-----------|-------------|
| **FixMatch** | Consistency regularization + pseudo-labeling with fixed threshold |
| **FlexMatch** | Adaptive threshold FixMatch — adjusts per class |
| **Mean Teacher** | Teacher-student mutual learning with exponential moving average |

---

## 🔬 Methodology

### Data Preprocessing
- Load CT, T1-MRI, T2-MRI images
- Resize to 224×224 pixels (preserving aspect ratio with padding)
- Apply CLAHE (Contrast Limited Adaptive Histogram Equalization)
- Gaussian filtering for noise reduction
- Normalize pixel values

### Semi-Supervised Pipeline
```
Labeled Data (small %)  +  Unlabeled Data (large %)
            │                        │
            ▼                        ▼
     Supervised Loss          SSL Consistency Loss
            │                (FixMatch / FlexMatch /
            │                 Mean Teacher)
            └──────────┬──────────────┘
                       ▼
              Combined Training Loss
                       │
                       ▼
            Final Classification Model
            (CT / T1-MRI / T2-MRI)
```

### FixMatch
- Generates **pseudo-labels** from weakly augmented unlabeled images
- Uses **fixed confidence threshold** to filter low-confidence predictions
- Applies strong augmentation for consistency training

### FlexMatch
- Extends FixMatch with **class-adaptive thresholds**
- Addresses class imbalance in medical datasets
- More robust for rare medical conditions

### Mean Teacher
- **Teacher model** = exponential moving average of student weights
- Student learns from both labeled data and teacher's predictions
- Provides stable pseudo-labels over time

---

## 🛠️ Technologies Used

| Category | Tools |
|----------|-------|
| Deep Learning | Python, PyTorch, torchvision, timm |
| SSL Algorithms | FixMatch, FlexMatch, Mean Teacher |
| Medical Imaging | pydicom, OpenCV, PIL |
| Data Processing | NumPy, Pandas, scikit-learn |
| Visualization | Matplotlib, Seaborn |
| Environment | Kaggle (GPU) |

---

## 📂 Repository Structure

```
Semi-Supervised-Medical-Image-Classification/
│
├── paired-ct-and-mri-all-model.ipynb       ← All supervised models comparison
├── paired-ct-mri-vit-fixmatch.ipynb        ← ViT + FixMatch
├── paired-ct-mri-vit-flex-match.ipynb      ← ViT + FlexMatch
├── paired-ct-mri-vit-mean-teacher.ipynb    ← ViT + Mean Teacher
├── paired-mean-teacher.ipynb               ← Mean Teacher baseline
├── paired-mri-ct-fixmatch.ipynb            ← CNN + FixMatch
├── paired-mri-ct-flexmatch.ipynb           ← CNN + FlexMatch
└── README.md
```

---

## ⚙️ Training Configuration

| Parameter | Value |
|-----------|-------|
| Input Size | 224×224 |
| Optimizer | Adam |
| Scheduler | ReduceLROnPlateau |
| Loss | CrossEntropyLoss |
| Classes | 3 (CT, T1-MRI, T2-MRI) |
| Device | GPU (CUDA) |
| Framework | PyTorch + timm |

---

## 👩‍💻 Author

**Faria Azad Anita**  
Undergraduate Student, CSE — East West University, Dhaka, Bangladesh  
📧 faria.azad.anita2001@gmail.com  
🔗 [GitHub](https://github.com/Anita-faria)

---




<p align="center">📄 Published Research | ICCIT 2025 | East West University</p>
