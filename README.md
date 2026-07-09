# Roof Type Classification using EfficientNet-V2

## Overview

This project develops a deep learning model to automatically classify building roof types from roof images using transfer learning. The model is built with **PyTorch** and **PyTorch Lightning**, leveraging a pretrained **EfficientNet-V2-S** convolutional neural network to achieve robust image classification performance.

The project demonstrates a complete computer vision workflow, including data preprocessing, augmentation, transfer learning, model training, validation, testing, and performance evaluation.

---

## Motivation

Roof type classification is an important task in computer vision and geospatial analysis. Automatically identifying roof types can support applications such as:

* Building inventory generation
* Urban planning
* Disaster risk assessment
* Infrastructure management
* Remote sensing and GIS analysis

Instead of training a deep neural network from scratch, this project utilizes transfer learning to benefit from features learned from large-scale image datasets.

---

## Dataset

The project assumes a dataset organized into separate training, validation, and testing folders.

Example structure:

```text
dataset/
│
├── train/
│   ├── Class_1/
│   ├── Class_2/
│   └── Class_3/
│
├── validation/
│   ├── Class_1/
│   ├── Class_2/
│   └── Class_3/
│
└── test/
    ├── Class_1/
    ├── Class_2/
    └── Class_3/
```

Each subfolder represents one roof type class.

Images are loaded automatically using:

* `torchvision.datasets.ImageFolder`

---

## Project Workflow

The notebook follows the standard deep learning pipeline:

### 1. Data Loading

* Load images using `ImageFolder`
* Create training, validation, and testing datasets
* Prepare DataLoaders

---

### 2. Image Preprocessing

The input images are preprocessed before training.

Typical preprocessing includes:

* Image resizing
* Tensor conversion
* Normalization

To improve generalization, data augmentation is applied to the training images.

Examples include:

* Random transformations
* Image normalization

---

### 3. Model Architecture

The classifier uses:

**EfficientNet-V2-S**

Transfer learning is used by:

* Loading pretrained ImageNet weights
* Replacing the final classification layer
* Fine-tuning the network for roof classification

Advantages include:

* Faster convergence
* Better feature extraction
* Higher accuracy with limited data

---

### 4. Training

The project is implemented using **PyTorch Lightning**, providing:

* Modular training loops
* Automatic checkpointing
* Cleaner code
* GPU support
* Logging

Training includes:

* Forward propagation
* Loss computation
* Backpropagation
* Optimizer updates
* Validation after each epoch

---

### 5. Model Evaluation

After training, the model is evaluated on the test dataset.

Performance is analyzed using:

* Classification accuracy
* Validation loss
* Training loss
* Confusion matrix

These metrics help understand both overall performance and class-wise prediction behavior.

---

## Model Architecture

```text
Input Image
      │
      ▼
Image Preprocessing
      │
      ▼
EfficientNet-V2-S
(Pretrained CNN)
      │
      ▼
Feature Extraction
      │
      ▼
Fully Connected Layer
      │
      ▼
Roof Type Prediction
```

---

## Technologies Used

### Programming

* Python

### Deep Learning

* PyTorch
* PyTorch Lightning
* Torchvision

### Data Processing

* NumPy
* Pandas

### Visualization

* Matplotlib

### Evaluation

* Confusion Matrix
* Accuracy Metrics

---

---

## Results

The notebook includes:

* Model training
* Validation monitoring
* Learning curves
* Confusion matrix
* Final classification performance

Transfer learning with EfficientNet-V2 enables effective roof type classification while reducing training time compared to training a CNN from scratch.

---

## Learning Outcomes

This project demonstrates practical experience with:

* Image classification
* Convolutional Neural Networks (CNNs)
* Transfer learning
* EfficientNet architectures
* PyTorch Lightning
* Data preprocessing
* Data augmentation
* Model evaluation
* Deep learning workflow development



This project was developed as part of a computer vision and deep learning learning exercise to explore transfer learning techniques for roof type image classification using PyTorch and EfficientNet-V2.
