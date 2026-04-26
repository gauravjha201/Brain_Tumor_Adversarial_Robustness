
# 🧠 Robust Brain Tumor Detection using CNN under Adversarial Attacks

## 📌 Overview

This project focuses on building a **robust deep learning model** for brain tumor detection using MRI images.  
Unlike traditional models that focus only on accuracy, this project explores **adversarial robustness** — the ability of a model to withstand malicious perturbations.

---

## 🎯 Problem Statement

Deep learning models achieve high accuracy in medical imaging tasks but are vulnerable to **adversarial attacks**, which can cause incorrect predictions with minimal changes to input images.

This project investigates:
- How vulnerable CNN models are to adversarial attacks
- How to improve robustness using adversarial training

---

## 🧠 Model Architecture

- Base Model: **MobileNetV2 (Pretrained on ImageNet)**
- Transfer Learning approach
- Custom layers:
  - GlobalAveragePooling2D
  - Dense (128, ReLU)
  - Dropout (0.3)
  - Output Layer (Sigmoid)

---

## 📂 Dataset

- Brain Tumor MRI Dataset (Binary Classification)
  - Class 0: No Tumor
  - Class 1: Tumor

### Preprocessing:
- Resize images to **224 × 224**
- Normalize pixel values to **[0,1]**
- Train/Validation split: 80/20

---

## ⚔️ Adversarial Attacks Implemented

### 1️⃣ FGSM (Fast Gradient Sign Method)
Single-step attack:

### 2️⃣ BIM (Basic Iterative Method)
Iterative version of FGSM

### 3️⃣ PGD (Projected Gradient Descent)
Strongest first-order attack with projection step

---

## 🛡️ Defense Strategy

### Adversarial Training

- Generated adversarial examples during training
- Combined clean + adversarial data
- Improved robustness against attacks

---

## 📊 Results

### 🔹 Before Defense

| Metric | Value |
|-------|------|
| Clean Accuracy | ~98% |
| FGSM Accuracy | ~70% |

---

### 🔹 After Defense

| Metric | Value |
|-------|------|
| Clean Accuracy | ~92% |
| FGSM Accuracy | ~50% |

---

## 📈 Key Insights

- High accuracy does NOT guarantee robustness ❌  
- Adversarial attacks significantly degrade performance  
- Adversarial training improves stability but introduces trade-offs  

---

## 🖼️ Visualization

The project includes:
- Original vs Adversarial images
- Perturbation (difference images)
- Accuracy comparison graphs

---

## 🛠️ Tech Stack

- Python  
- TensorFlow / Keras  
- NumPy  
- Matplotlib  
- Google Colab  

---

## 🚀 How to Run

```bash
# Clone repository
git clone https://github.com/your-username/your-repo-name.git

# Open in Google Colab
Upload notebooks and run cells step-by-step
