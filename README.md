#FashionMNIST Image Classification with MLP and CNN

This project explores and compares the performance of two distinct neural network architectures; Multi-Layer Perceptron (MLP) and Convolutional Neural Network (CNN) for image classification on the FashionMNIST dataset.

## Project Overview

The FashionMNIST dataset is a collection of 28x28 grayscale images of 10 fashion categories. The goal of this project is to train classification models that can accurately identify the category of each image.

## Models Implemented:

1. Multi-Layer Perceptron (MLP): A basic feedforward neural network that flattens the input images into vectors.
2. Convolutional Neural Network (CNN): An architecture specifically designed for image data, utilizing convolutional and pooling layers to capture spatial hierarchies.

## Dataset

The FashionMNIST dataset is used, divided into training, validation, and testing sets. Images are preprocessed with transforms.ToTensor() and transforms.Normalize().

## Model Architectures

### MLP Model

Layers: Three fully connected (linear) layers.
Activation: ReLU activation functions after the first two linear layers.
Regularization: Dropout layer with a probability of 0.3 to prevent overfitting.
Input: Flattened 784-dimensional vector (28x28 pixels).

### CNN Model

Convolutional Layers: Two convolutional layers (conv1, conv2) with ReLU activation and max-pooling (MaxPool2d) to reduce dimensionality and extract features.
Fully Connected Layers: Two fully connected layers (fc1, fc2) after flattening the output of the convolutional layers.
Input: 1-channel, 28x28 grayscale images.

## Training and Evaluation

Both models were trained for 50 epochs using Cross-Entropy Loss (nn.CrossEntropyLoss) and the Stochastic Gradient Descent (optim.SGD) optimizer with a learning rate of 0.001.

## Performance Metrics:

Accuracy: Used to measure the proportion of correct predictions.
Confusion Matrix: Visualized to understand specific misclassifications between classes.
Results

## MLP Model Performance

Validation Accuracy: 79.60%
Test Accuracy: 83.59%
The MLP model struggles to distinguish between visually similar categories, primarily because it flattens the input, losing spatial information crucial for image understanding.

## CNN Model Performance

Validation Accuracy: 83.11%
Test Accuracy: 85.62%
The CNN model demonstrates significantly better performance, which is attributed to its ability to preserve and leverage spatial relationships in the images through convolutional layers.

## Comparison of MLP and CNN

Model  Validation Accuracy  Test Accuracy
MLP	79.60%	83.59%
CNN	83.11%	85.62%
The CNN model clearly outperformed the MLP, reaffirming its suitability for image classification tasks due to its inherent ability to process and extract features from structured image data.

## Tools and Libraries

PyTorch: For building and training neural networks.
Torchvision: For dataset loading and image transformations.
Weights & Biases (WandB): Used for experiment tracking, logging training/validation losses, and accuracy metrics. This provided real-time insights into model learning.
Matplotlib & Seaborn: For plotting confusion matrices and other visualizations.
Scikit-learn: For calculating accuracy scores and confusion matrices.
