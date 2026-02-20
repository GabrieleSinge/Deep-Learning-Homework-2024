# Deep Learning Homework 2024

This repository contains the Jupyter notebooks and reports developed for the two assignments of the **Artificial Neural Networks and Deep Learning** course, taught by Professors Matteucci and Boracchi at **Politecnico di Milano**.

## Repository structure
- `Homework_1/` – notebooks and material for HW1  
- `Homework 2/` – notebooks and material for HW2  
- `AN2DL_Homework_1_Report_ReLUctant_Learners.pdf` – HW1 report  
- `AN2DL_Homework_2_Report___ReLUctant_Learners.pdf` – HW2 report  

---

## Homework 1: White Blood Cell Classification

### Goal
Classify **96×96 RGB** blood cell images into **8 classes** (multi-class classification).

### Method
We developed a CNN based on the **EfficientNetV2Small** backbone, adding regularization components to improve generalization. Our pipeline included:
- **Data augmentation** to increase sample diversity and robustness  
- **Fine-tuning** of the pretrained backbone  
- **Class balancing** via oversampling to mitigate class imbalance  

### Results
- Development accuracy: **0.90**
---

## Homework 2: Mars Terrain Semantic Segmentation

### Goal
Given **64×128 grayscale** real images of Mars terrain, perform **semantic segmentation** by assigning each pixel to one of **5 terrain classes** (pixel-wise classification).

Competition: **Kaggle – AN2DL 2024–2025 Homework 2**  
Dataset link: https://www.kaggle.com/competitions/an-2-dl-2024-2025-homework-2

### Data
- **Input**: grayscale images with shape **64×128×1**
- **Target**: segmentation masks with the same spatial resolution (**64×128**) and labels in **{0, …, 4}**
- Provided format: typically `.npz` (see the loading code in `Homework 2/` notebooks)

### Approach (overview)
In the HW2 notebook(s) inside `Homework 2/`, we implement a full training pipeline for semantic segmentation, including:
- An **encoder–decoder** segmentation model (U-Net/FCN-style)
- Training with:
  - **Augmentation** suited for grayscale terrain imagery (geometric + intensity transforms)
  - A segmentation loss (e.g., cross-entropy; optionally combined with Dice/Focal if used)
  - Validation metrics such as **mIoU** and/or pixel accuracy

> For full architectural details, hyperparameters, and experiments, refer to: `AN2DL_Homework_2_Report___ReLUctant_Learners.pdf`.

### Results
-  Mean intersection over union metric: **0.67**

## Notes
This repository contains coursework material. Dataset usage and submission rules are defined by the Kaggle competition.
