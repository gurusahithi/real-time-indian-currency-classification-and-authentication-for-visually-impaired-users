# RupeeVision: Real-Time Indian Currency Classification and Authentication for Visually Impaired Users

## Overview

RupeeVision is an AI-powered assistive technology project designed to help visually impaired individuals recognize Indian currency denominations using a smartphone camera. The system performs real-time currency classification offline using deep learning and provides voice and vibration feedback for an accessible user experience.

As part of this project, a counterfeit currency detection model was also developed and evaluated. Although it achieved promising performance on a controlled dataset, it was not integrated into the final application because it produced inconsistent predictions under real-world conditions.

---

## Features

* Real-time Indian currency denomination recognition
* Supports ₹10, ₹20, ₹50, ₹100, ₹200, ₹500 and ₹2000 notes
* Offline inference using TensorFlow Lite
* Voice feedback through Text-to-Speech
* Haptic feedback for proper note alignment
* TalkBack accessibility support
* Gallery image support for currency recognition
* Counterfeit currency detection model developed for research purposes

---

## Technologies Used

### Machine Learning

* Python
* TensorFlow
* Keras
* MobileNetV2
* TensorFlow Lite
* OpenCV

### Mobile Development

* Kotlin
* Android Studio
* CameraX
* Android Text-to-Speech API

### Development Tools

* Google Colab
* Git
* GitHub

---

## Dataset

The currency classification model was trained on approximately **6,000 images** spanning seven Indian currency denominations.

Supported denominations:

* ₹10
* ₹20
* ₹50
* ₹100
* ₹200
* ₹500
* ₹2000

Images were resized to **224 × 224** pixels and enhanced using data augmentation techniques such as rotation, zoom, brightness adjustment, shifting, and horizontal flipping to improve model robustness.

A separate dataset containing genuine and counterfeit ₹200 and ₹500 notes was used to develop the fake currency detection model.

---

## Model Architecture

### Currency Classification

The denomination classifier is based on **MobileNetV2** using transfer learning.

Architecture:

* MobileNetV2 (ImageNet pretrained)
* Global Average Pooling
* Dense Layer (128 units)
* Dropout (35%)
* Softmax Output Layer

The trained model was converted into **TensorFlow Lite** for efficient mobile deployment.

### Fake Currency Detection

A separate MobileNetV2-based classifier was trained to distinguish genuine and counterfeit Indian currency notes under controlled conditions.

---

## Android Application

An Android application was developed to deploy the trained TensorFlow Lite model and provide an accessible interface for visually impaired users.

### Application Workflow

1. Launch the application.
2. Point the smartphone camera toward an Indian currency note.
3. The application continuously analyzes camera frames to detect proper note alignment.
4. Once alignment is achieved, the phone vibrates to notify the user.
5. Capture the image for high-resolution inference.
6. The TensorFlow Lite model predicts the denomination.
7. The predicted denomination and confidence score are announced using Text-to-Speech.
8. Users can alternatively select a currency image from the device gallery for classification.

---

## Accessibility Features

* Voice guidance using Android Text-to-Speech
* Vibration feedback for note alignment
* TalkBack-compatible interface
* Offline operation without internet connectivity
* Simple and intuitive interface designed for visually impaired users

---

## Results

### Currency Classification

* Validation Accuracy: **94.0%**
* Supports seven Indian currency denominations
* Optimized TensorFlow Lite model for mobile devices

### Fake Currency Detection

* Controlled Test Accuracy: **94.8%**

Although the counterfeit detection model achieved high accuracy on the test dataset, it produced inconsistent predictions on real-world smartphone images under varying lighting conditions and camera angles. To ensure user safety and reliability, this feature was intentionally excluded from the final application.

---

## Screenshots

This repository includes screenshots demonstrating:

* Application home screen

  <img width="450" height="800" alt="image" src="https://github.com/user-attachments/assets/bfc075b4-b2d9-4800-9b85-553415d5dc7f" />
  

* Camera interface

  <img width="450" height="800" alt="image" src="https://github.com/user-attachments/assets/072304d7-300b-4b3b-88aa-c83561333c31" />
  
  
* Prediction results

  <img width="450" height="800" alt="image" src="https://github.com/user-attachments/assets/f676cf0c-e9a9-4dcc-a597-8f3442944d26" />

---

## Future Improvements

* Improve counterfeit detection using larger and more diverse real-world datasets
* Support recognition of Indian coins
* Enhance performance under challenging lighting conditions
* Add multilingual voice assistance
* Extend support to additional currencies

---

## Project Highlights

* MobileNetV2 Transfer Learning
* TensorFlow Lite Deployment
* Computer Vision
* Deep Learning
* Offline Mobile AI
* Android Accessibility
* Assistive Technology
* Real-Time Currency Recognition

---

## License

This project was developed for educational and research purposes.

