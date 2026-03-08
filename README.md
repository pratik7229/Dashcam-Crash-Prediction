# Dashcam Crash Prediction (Computer Vision and Deep Learning)

Early vehicle collision prediction system built using computer vision and deep learning. The model analyzes dashcam video sequences and predicts potential crashes before they occur, supporting research in autonomous driving and Advanced Driver Assistance Systems (ADAS).

---

# Overview

This project focuses on predicting vehicle collisions from dashcam video sequences. The system processes driving footage, extracts temporal frame sequences, and uses deep learning models to detect patterns that indicate an imminent crash.

The pipeline performs:

* Video preprocessing
* Frame sequence extraction
* Dataset preparation
* Model training on temporal video data
* Ensemble learning using multiple models
* Crash prediction on unseen test videos

The goal is to detect accidents as **early as possible** before the collision occurs.

---

# Features

* Dashcam video preprocessing pipeline
* Automatic frame extraction from videos
* Temporal dataset generation (20-frame sequences)
* Deep learning models for crash prediction
* Ensemble learning for improved accuracy
* Modular training and inference pipeline
* Kaggle competition compatible workflow

---

# Dataset Preparation

The dataset consists of dashcam videos from the Nexar Collision Prediction dataset.

The preprocessing pipeline extracts **20 consecutive frames from each video**, resizes them to **224×224**, and stores them as `.npy` arrays for efficient training.

Run dataset preparation:

```bash
python src/data/prepare_data.py
```

This converts raw videos into a structured dataset used for model training.

---

# Installation

Clone the repository

```bash
git clone https://github.com/pratik7229/Dashcam-Crash-Prediction.git
```

Move into the project directory

```bash
cd dashcam-crash-prediction
```

Create a virtual environment

```bash
python3 -m venv venv
```

Activate the virtual environment

```bash
source venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# Training Pipeline

The training pipeline trains multiple deep learning models on extracted video frame sequences.

Train individual models:

```bash
python src/training/train_model1.py
python src/training/train_model2.py
python src/training/train_model3.py
```

---

# Ensemble Learning

Predictions from multiple trained models are combined to improve robustness and prediction accuracy.

Run ensemble prediction:

```bash
python src/ensemble/ensemble_model.py
```

---

# Testing / Inference

Run prediction on the test dataset and generate Kaggle submission output.

```bash
python src/inference/test.py
```

The output file contains crash probability predictions for each video.

---

# Performance Considerations

To improve training and inference performance:

* Preprocess videos into frame arrays (.npy)
* Use batch loading for frame sequences
* Resize frames to 224×224 for efficient GPU training
* Use ensemble models for better generalization

---

# Applications

This system can be used in:

* Autonomous vehicle safety systems
* Advanced Driver Assistance Systems (ADAS)
* Traffic accident prediction research
* Fleet safety monitoring
* Smart transportation systems

---

# Future Improvements

Possible future improvements include:

* Transformer-based video models
* 3D CNN architectures
* Temporal attention mechanisms
* Real-time crash prediction deployment
* Edge deployment for autonomous vehicles

---

# Author

Pratik Walunj
Robotics Engineer | Robot Perception | Computer Vision | Autonomous Systems

---

# License

This project is licensed under the Apache License 2.0.
