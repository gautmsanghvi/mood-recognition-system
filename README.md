# Real Time Emotion/Facial Expressions Detection/Recognition  
**Created by Gautm Sanghvi**

## Abstract

Human facial expressions convey critical non-verbal information. Automated facial expression recognition (FER) is vital for human–machine interaction, with applications ranging from behavioral analysis and healthcare to entertainment and synthetic human expression. Despite advances, accurate real-time identification of expressions remains challenging.

This project leverages deep learning, specifically Convolutional Neural Networks (CNNs), to recognize the seven universal human emotions: **Angry, Disgust, Fear, Happy, Sad, Surprise, and Neutral**.

---

## Table of Contents

- [Introduction](#introduction)
- [Project Formulation](#project-formulation)
- [Dataset Description](#dataset-description)
- [Project Structure](#project-structure)
- [Implementation Steps](#implementation-steps)
- [Software Requirements](#software-requirements)
- [Conclusion](#conclusion)
- [References](#references)

---

## Introduction

Facial expressions are powerful indicators of human emotion and intent. Recognizing these expressions automatically enables applications such as:
- Retail: Assessing customer interest and satisfaction
- Healthcare: Monitoring patient mood during treatment
- Entertainment: Tracking audience engagement

While humans can reliably interpret expressions even as children, computers can potentially surpass human consistency and scale in emotion recognition. This project implements a deep learning-based system that gives machines the ability to interpret facial emotions in real time via webcam input.

---

## Project Formulation

The project is organized into the following tasks:

1. **Introduction**
   - Overview of the dataset and import of essential libraries (NumPy, Matplotlib, Keras)
2. **Dataset Exploration**
   - Visualization of sample images from each emotion class
3. **Data Preprocessing & Augmentation**
   - Generation of real-time augmented training and validation batches
4. **CNN Model Creation**
   - Design and implementation of a CNN with 4 convolutional and 2 fully connected layers
   - Model uses Adam optimizer, categorical crossentropy loss, and accuracy metric
5. **Training and Evaluation**
   - Model training, validation, and checkpointing
   - Visualization of training progress in notebooks
6. **Model Serialization**
   - Saving the model architecture and weights as JSON and H5 files
7. **Web App with Flask**
   - Flask web server serves real-time predictions and webcam images
8. **Prediction Logic**
   - `FacialExpressionModel` class loads the model and performs predictions
9. **Web Interface**
   - Basic HTML template for live emotion detection display
10. **Real-Time Recognition**
    - Webcam-based real-time emotion recognition via Flask app

---

## Dataset Description

- **Source:** [Kaggle Facial Expression Recognition Challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data)
- **Format:** 48x48 pixel grayscale face images, CSV files (`train.csv`, `test.csv`)
- **Classes:** 
  - 0 = Angry
  - 1 = Disgust
  - 2 = Fear
  - 3 = Happy
  - 4 = Sad
  - 5 = Surprise
  - 6 = Neutral
- **Size:** 
  - Training: 28,709 samples
  - Test: 7,178 samples (split for public and private leaderboard)
- **CSV Columns:**
  - `emotion`: Class label (0–6)
  - `pixels`: Space-separated pixel values in row-major order

---

## Project Structure

The typical flow for facial expression recognition:

1. **Face Detection:** Locate faces in an image.
2. **Feature Extraction:** Extract facial features (e.g., eyes, nose, lips).
3. **Expression Analysis:** Analyze feature movement/appearance to infer emotion.
4. **Classification:** Assign one of the seven emotion categories.

---

## Implementation Steps

1. **Preprocessing:** Noise reduction, grayscale conversion, brightness normalization, and geometric transforms.
2. **Face Registration:** Detect and align faces to a standard template.
3. **Feature Extraction:** Identify key facial landmarks/features to create numerical feature vectors.
4. **Emotion Classification:** Use CNN to classify faces into one of the seven emotion classes.

---

## Software Requirements

- **Python 3.6.5+**
- **Libraries:** See `requirements.txt`
- **Anaconda:** For package/environment management
- **Jupyter Notebook:** For exploratory data analysis and visualization
- **Spyder:** Python IDE for scientific computing
- **Flask:** Web framework for serving real-time predictions
- **Atom or any HTML editor:** For editing web UI templates

---

## Example Usage

1. **Clone the repository:**
   ```bash
   git clone https://github.com/gautmsanghvi/mood-recognition-system.git
   cd mood-recognition-system
   ```

2. **Install requirements:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Train the model (if needed):**
   - Run `trainmodel.ipynb` or equivalent training script.

4. **Start the web app:**
   - Run `realtimedetection.py` or `main.py` (as per your repo)
   - Open the displayed URL in your browser for live emotion detection

---

## Output

- Real-time emotion prediction from webcam, displayed via web interface
- Model accuracy and loss plots available in notebooks

---

## Conclusion

This project demonstrates a deep learning pipeline for real-time emotion/facial expression recognition using CNNs. The trained model can recognize seven universal emotions from live webcam feeds, with potential applications in retail, healthcare, entertainment, and beyond.

---

## References

1. [Coursera: Facial Expression Recognition (Keras)](https://www.coursera.org/learn/facial-expression-recognition-keras/supplement/2KrW0/project-based-course-overview)
2. [Kaggle: Facial Expression Classification Tutorial (Keras)](https://www.kaggle.com/ashishpatel26/tutorial-facial-expression-classification-keras)
3. "Fundamentals of Facial/Emotion Recognition"

---
