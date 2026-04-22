# 🧠 Autoencoder on SVHN Dataset

This project implements a **Convolutional Autoencoder** trained on the **SVHN (Street View House Numbers)** dataset for unsupervised representation learning.

The goal is to learn a compressed latent representation of images and reconstruct them while analyzing the effect of different latent dimensions.

---

## 📌 Overview

- Dataset: SVHN (32×32 RGB images)
- Task: Unsupervised learning (no labels used)
- Model: Convolutional Autoencoder
- Loss Function: Mean Squared Error (MSE)
- Framework: TensorFlow / Keras

---

## 🏗️ Model Architecture

### Encoder
- Conv2D + ReLU + MaxPooling
- Conv2D + ReLU + MaxPooling
- Conv2D + ReLU
- Flatten → Dense (latent vector)

### Decoder
- Dense → Reshape
- Conv2DTranspose (upsampling)
- Conv2D (sigmoid output)

---

## ⚙️ Training Details

- Epochs: 20  
- Batch size: 128  
- Optimizer: Adam  
- Loss: MSE  

---

## 🔬 Experiments

Two latent dimensions were tested:

| Latent Size | Validation MSE |
|------------|---------------|
| 64         | 0.001208      |
| 16         | 0.004766      |

---

## 📊 Results

- Larger latent size (64):
  - Better reconstruction quality
  - Preserves fine details

- Smaller latent size (16):
  - Stronger compression
  - Slightly blurred outputs

✔ The model successfully reconstructs recognizable images in both cases.

---

## 🖼️ Reconstruction Example

Original vs Reconstructed images:

- Latent = 64 → sharper reconstruction  
- Latent = 16 → smoother, less detailed  

---

## 🧠 Key Concepts

### What is a latent representation?
A compressed vector that encodes the most important features of an image.

### Effect of dimensionality reduction
Reducing latent size decreases reconstruction quality due to information loss.

### Why autoencoders?
They learn useful features without labels and are used for:
- Compression
- Denoising
- Feature extraction

---

## 📁 Project Structure
├── Autoencoder_with_SVHN_Dataset.ipynb
├── Autoencoder_with_SVHN_Dataset_Report.pdf
└── README.md

---

## 🚀 How to Run

### Option 1: Google Colab
1. Open the notebook in Colab
2. Run all cells

### Option 2: Local
```bash
pip install tensorflow numpy matplotlib scipy
