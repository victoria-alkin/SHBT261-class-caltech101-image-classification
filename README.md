# Caltech-101 Image Classification Benchmark

This project evaluates classical machine learning and deep learning approaches for image classification on the Caltech-101 dataset. The goal is to compare performance between these models, and to analyze the effects of ablations such as changes in image size and data augmentation.

---

# Project Overview

Four classification approaches were implemented and evaluated:

| Model | Type |
|------|------|
| HOG + LinearSVC | Classical machine learning baseline |
| SimpleCNN | Convolutional neural network trained from scratch |
| ResNet-18 | Pre-trained deep network |
| EfficientNet-B0 | Pre-trained efficient architecture |

The experiments investigate:

- Performance differences between classical and deep learning approaches
- Effects of image resolution
- Effects of data augmentation
- Impact of class imbalance on per-class accuracy

---

# Dataset

**Caltech-101**

- 101 object categories
- ~9,000 images
- Large variation in class sizes (class imbalance)

Image sizes of 128x128 were used for the primary models.

Dataset splits were created using a fixed random seed:

- Train
- Validation
- Test

---

# Models

## 1. HOG + LinearSVC

A classical computer vision pipeline:

1. Histogram of Oriented Gradients (HOG) feature extraction  
2. Linear Support Vector Machine classifier 

---

## 2. SimpleCNN (trained from scratch)

A small convolutional neural network trained directly on the dataset.

This model learns image features directly from data without pretraining.

---

## 3. ResNet-18 (pre-trained)

Transfer learning using a ResNet-18 architecture pretrained on ImageNet

---

## 4. EfficientNet-B0 (pre-trained)

Transfer learning using a EfficientNet-B0 architecture pretrained on ImageNet

---

# Training Configuration

Primary deep learning training setup:

Input size: 128 × 128 RGB
Batch size: 32
Optimizer: Adam
Learning rate: 1e-4
Epochs: 100
Random seed: 42

---

# Evaluation Metrics

Models were evaluated on the test set using:

- Top-1 Accuracy
- Top-5 Accuracy
- Macro Precision
- Macro Recall
- Macro F1 Score
- Weighted Precision
- Weighted Recall
- Weighted F1 Score

---

### Key Findings

- Deep learning models significantly outperform classical feature-based methods.
- Transfer learning significantly improves performance compared to training CNNs from scratch.
- EfficientNet-B0 achieved the best overall classification accuracy.

---

# Ablation Studies

Two ablation studies were conducted to evaluate how different factors affect model performance.

---

## Image Resolution Ablation

Input resolution comparison: 128x128 vs 64x64

---

## Data Augmentation Ablation

Training with and without data augmentation was compared.