# Traffic Sign Recognition System

A deep learning-based traffic sign recognition program that classifies road signs from images using a Convolutional Neural Network (CNN). The project trains a model on traffic sign image data and includes a simple Tkinter GUI where users can upload an image and receive a predicted traffic sign label.

## Features

- Classifies traffic signs into 43 different categories
- Uses a Convolutional Neural Network for image classification
- Preprocesses images by resizing them to 30x30 pixels
- Splits the dataset into training and validation sets
- Displays accuracy and loss graphs after training
- Evaluates model performance using test data
- Saves the trained model for future use
- Includes a Tkinter GUI for uploading and classifying images

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- OpenCV
- Pillow
- Scikit-learn
- Tkinter

## Project Structure

```text
traffic-sign-recognition/
│
├── train/
│   ├── 0/
│   ├── 1/
│   ├── 2/
│   └── ...
│
├── Test.csv
├── traffic_classifier.py
├── gui.py
├── my_model.h5
├── traffic_classifier.h5
└── README.md
