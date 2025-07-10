# 🧠 CIFAR-10 Image Classification using CNN (TensorFlow + Keras)

This project implements a Convolutional Neural Network (CNN) for image classification on the CIFAR-10 dataset using **TensorFlow** and **Keras**. The model is trained with **real-time data augmentation** and includes dropout regularization and checkpointing for best model saving.

---

## 📦 Dataset: CIFAR-10

- **10 classes**: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck  
- **60,000 32x32 color images**:
  - 50,000 training images
  - 10,000 test images

---

## 🏗️ Model Architecture

| Layer Type         | Filters/Units | Kernel Size | Activation | Extra           |
|--------------------|---------------|-------------|------------|-----------------|
| Input              | -             | (32, 32, 3) | -          | -               |
| Conv2D             | 16            | 3x3         | ReLU       | padding='same'  |
| MaxPooling2D       | -             | 2x2         | -          | -               |
| Conv2D             | 32            | 3x3         | ReLU       | padding='same'  |
| MaxPooling2D       | -             | 2x2         | -          | -               |
| Conv2D             | 64            | 3x3         | ReLU       | padding='same'  |
| MaxPooling2D       | -             | 2x2         | -          | Dropout(0.3)    |
| Conv2D             | 128           | 3x3         | ReLU       | padding='same'  |
| MaxPooling2D       | -             | 2x2         | -          | Dropout(0.3)    |
| Flatten            | -             | -           | -          | -               |
| Dense              | 500           | -           | ReLU       | Dropout(0.4)    |
| Dense (Output)     | 10            | -           | Softmax    | -               |

---

## ⚙️ Training Configuration

| Setting         | Value               |
|-----------------|---------------------|
| Optimizer       | Adam                |
| Loss Function   | Categorical Crossentropy |
| Batch Size      | 64                  |
| Epochs          | 70                  |
| Callback        | ModelCheckpoint     |
| Augmentation    | Horizontal flip, width/height shift |

---

## 🎯 Results

| Dataset         | Accuracy |
|-----------------|----------|
| Training Set    | 78.0%    |
| Test Set        | **79.0%** ✅ |

---

## 📈 Data Augmentation Used

Using `ImageDataGenerator` for real-time augmentation:
```python
ImageDataGenerator(
    width_shift_range=0.1,
    height_shift_range=0.1,
    horizontal_flip=True
)


🧑‍💻 Author
Muhammad Muaaz
