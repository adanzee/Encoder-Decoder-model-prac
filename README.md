## Autoencoder on MNIST (Encoder–Decoder Architecture)

## 📌 Overview

This project implements a **fully connected autoencoder** using TensorFlow/Keras to learn compressed representations of handwritten digits from the MNIST dataset. The model learns to encode images into a lower-dimensional latent space and reconstruct them with minimal loss.

---

## 🎯 Objectives

* Learn **dimensionality reduction** using neural networks
* Understand **encoder–decoder architecture**
* Visualize **reconstruction quality**
* Explore **latent space representation** using PCA

---

## 📂 Dataset

* **MNIST Handwritten Digits**
* 60,000 training images and 10,000 test images
* Image size: **28 × 28 grayscale**

---

## ⚙️ Preprocessing

* Normalized pixel values to range **[0, 1]**
* Flattened images from **28×28 → 784-dimensional vectors**

---

## 🏗️ Model Architecture

### 🔹 Encoder

Transforms input into a compressed latent representation:

```
784 → 128 → 64 → 32
```

* Dense(128, ReLU)
* Dense(64, ReLU)
* Dense(32, ReLU) → **Latent Space**

---

### 🔹 Decoder

Reconstructs the original image from latent space:

```
32 → 64 → 128 → 784
```

* Dense(64, ReLU)
* Dense(128, ReLU)
* Dense(784, Sigmoid)

---

### 🔹 Autoencoder

* Combines encoder + decoder
* Input = Output (reconstruction task)

---

## 🧪 Training Details

| Parameter     | Value               |
| ------------- | ------------------- |
| Optimizer     | Adam                |
| Loss Function | Binary Crossentropy |
| Metric        | Mean Squared Error  |
| Epochs        | 20                  |
| Batch Size    | 256                 |

---

## 📊 Results

### 📉 Training Curve

* Plots training and validation loss over epochs
* Saved as: `training_loss.png`

### 🖼️ Reconstruction

* Displays original vs reconstructed images
* Saved as: `reconstruction.png`

### 📉 Latent Space Visualization

* Applied **PCA (2D)** on latent vectors
* Colored by digit class
* Saved as: `latent_space_pca.png`

---

## 📈 Evaluation

* Test Loss (Binary Cross-Entropy)
* Test MSE

These metrics indicate how well the model reconstructs unseen data.

---

## 🚀 How to Run

1. Install dependencies:

```bash
pip install tensorflow numpy matplotlib scikit-learn pillow
```

2. Run the notebook/script:

```bash
python autoencoder.py
```

or open in Google Colab.

---

## 📌 Key Learnings

* Autoencoders can effectively perform **unsupervised feature learning**
* Latent space captures meaningful structure of data
* PCA helps visualize high-dimensional embeddings
* Reconstruction quality improves with better architecture tuning

---

