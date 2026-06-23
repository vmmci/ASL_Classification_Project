# ASL Classification — Computer Vision Project

This project is a deep learning-based image classification system for American Sign Language (ASL) hand gestures. It uses transfer learning with EfficientNetB0 to classify ASL alphabet signs and functional gestures such as `space`, `del`, and `nothing`.

## Project Overview

The goal of this project is to build a computer vision model that recognizes American Sign Language hand gestures from images and predicts the corresponding class. The model was trained on a multi-class ASL dataset containing 29 classes:

* Letters: A–Z
* Functional classes: `space`, `del`, `nothing`

The project also includes an interactive Gradio interface that allows users to upload an image or use a webcam frame to generate predictions and build text from recognized signs.

## Model Architecture

The model uses EfficientNetB0 as a transfer learning backbone.

Main components:

* EfficientNetB0 pretrained on ImageNet
* Global Average Pooling
* Dropout layers for regularization
* Dense layer with ReLU activation
* Softmax output layer for 29-class classification

The training process was divided into two stages:

1. Initial training with the EfficientNetB0 backbone frozen.
2. Fine-tuning by unfreezing the upper layers of EfficientNetB0 using a lower learning rate.

## Dataset

The dataset was organized into training, validation, and test folders.

| Split      | Number of Images |
| ---------- | ---------------: |
| Training   |           20,087 |
| Validation |            1,299 |
| Test       |            1,995 |

## Results

The final model achieved strong performance on the unseen test set.

| Metric            |  Value |
| ----------------- | -----: |
| Test Accuracy     | 97.89% |
| Test Loss         | 0.0608 |
| Number of Classes |     29 |

A confusion matrix and classification report were generated to evaluate per-class performance.

## Interactive Prediction Interface

A Gradio interface was built to make the model easier to test. The interface supports image-based prediction and updates an output text buffer based on the predicted class:

* Letter classes are appended as text.
* `space` adds a space.
* `del` removes the last character.
* `nothing` leaves the text unchanged.

## Technologies Used

* Python
* TensorFlow / Keras
* EfficientNetB0
* Transfer Learning
* NumPy
* Matplotlib
* Scikit-learn
* Gradio

## Project Status

Completed as an academic computer vision project and prepared for portfolio presentation.
