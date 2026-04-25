# NIH-CHEST-X-RAY-
Developed a multi-label chest X-ray classifier using DenseNet121 and evaluated the impact of different loss functions (BCE, Focal, ZLPR, FZLPR) with a two-stage training approach.
# 🩺 NIH Chest X-ray Multi-Label Classification with Loss Function Benchmarking

This project focuses on multi-label classification of thoracic diseases using chest X-ray images from the NIH dataset, with a key emphasis on **comparing different loss functions** under a two-stage transfer learning setup.

---

## 📌 Key Contributions

- Multi-label classification of 14 thoracic diseases
- Benchmarking **4 different loss functions**
- Two-stage training strategy:
  - Frozen backbone
  - Unfrozen fine-tuning
- Evaluation using **AUC-ROC (primary metric)**
- Backbone: DenseNet121 (pretrained)

---

## 🧠 Problem Statement

Chest X-rays often contain multiple co-existing diseases, making it a challenging **multi-label classification** problem.

Additionally, **class imbalance** significantly affects performance — making loss function selection critical.

This project explores how different loss functions impact performance in such settings.

---

## ⚙️ Methodology

### 🔹 Dataset
- NIH ChestX-ray14 dataset
- 14 disease labels (multi-label setup)

---

### 🔹 Model Architecture
- Backbone: DenseNet121 (pretrained on ImageNet)
- Final Layer: Fully connected with sigmoid activation
- Output: 14 probability scores

---

### 🔹 Two-Stage Training Strategy

1. **Stage 1 (Frozen Training)**
   - Backbone frozen
   - Only classifier trained

2. **Stage 2 (Fine-tuning)**
   - Entire network unfrozen
   - End-to-end training

---

## 🧪 Loss Functions Compared

The project evaluates the following loss functions:

- Binary Cross Entropy (BCE)
- Focal Loss
- ZLPR Loss
- FZLPR Loss

These were selected to address:
- Class imbalance
- Hard example learning
- Label distribution challenges

---

## 📊 Evaluation Metric

Primary metric:
- **AUC-ROC (per class + average)**

Reason:
- Suitable for imbalanced multi-label classification
- Measures ranking quality instead of threshold-based accuracy

---



## 🔍 Key Insights

- Fine-tuning (unfrozen stage) consistently improves performance
- Advanced loss functions outperform BCE in handling imbalance
- ZLPR/FZLPR show better performance on rare classes
- Focal loss improves hard example learning but may require tuning

---

