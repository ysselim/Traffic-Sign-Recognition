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
```

## Dataset Format

The project expects the training dataset to be organized into numbered folders based on class labels.

Example:

```text
train/
├── 0/
├── 1/
├── 2/
├── ...
└── 42/
```

Each folder contains images for one traffic sign class.

The test dataset should be referenced through `Test.csv`, which contains image paths and their corresponding class IDs.

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
cd YOUR_REPOSITORY_NAME
```

Install the required Python libraries:

```bash
pip install numpy pandas matplotlib opencv-python tensorflow pillow scikit-learn keras
```

## How to Train the Model

Run the training script:

```bash
python traffic_classifier.py
```

The training script will:

1. Load images from the `train` folder
2. Resize each image to `30x30`
3. Convert the images and labels into NumPy arrays
4. Split the data into training and validation sets
5. Convert labels into one-hot encoded format
6. Train the CNN model
7. Save the trained model as `my_model.h5`
8. Display training accuracy and loss graphs

## How to Run the GUI

After training the model, run the GUI file:

```bash
python gui.py
```

The GUI allows the user to:

1. Upload a traffic sign image
2. Preview the selected image
3. Click the classify button
4. View the predicted traffic sign name

## Model Architecture

The CNN model uses the following architecture:

```text
Conv2D
Conv2D
MaxPool2D
Dropout
Conv2D
Conv2D
MaxPool2D
Dropout
Flatten
Dense
Dropout
Dense Softmax
```

The final output layer uses softmax activation to classify an image into one of 43 traffic sign classes.

## Traffic Sign Classes

The model can classify the following traffic signs:

```text
1. Speed limit (20km/h)
2. Speed limit (30km/h)
3. Speed limit (50km/h)
4. Speed limit (60km/h)
5. Speed limit (70km/h)
6. Speed limit (80km/h)
7. End of speed limit (80km/h)
8. Speed limit (100km/h)
9. Speed limit (120km/h)
10. No passing
11. No passing vehicles over 3.5 tons
12. Right-of-way at intersection
13. Priority road
14. Yield
15. Stop
16. No vehicles
17. Vehicles over 3.5 tons prohibited
18. No entry
19. General caution
20. Dangerous curve left
21. Dangerous curve right
22. Double curve
23. Bumpy road
24. Slippery road
25. Road narrows on the right
26. Road work
27. Traffic signals
28. Pedestrians
29. Children crossing
30. Bicycles crossing
31. Beware of ice/snow
32. Wild animals crossing
33. End speed and passing limits
34. Turn right ahead
35. Turn left ahead
36. Ahead only
37. Go straight or right
38. Go straight or left
39. Keep right
40. Keep left
41. Roundabout mandatory
42. End of no passing
43. End no passing vehicles over 3.5 tons
```

## Important Notes

The training script saves the model as:

```text
my_model.h5
```

The GUI file loads:

```text
traffic_classifier.h5
```

To make the GUI work correctly, either rename the trained model:

```bash
mv my_model.h5 traffic_classifier.h5
```

or update this line in the GUI file:

```python
model = load_model('traffic_classifier.h5')
```

to:

```python
model = load_model('my_model.h5')
```

Also, newer versions of TensorFlow/Keras may not support:

```python
model.predict_classes(X_test)
```

Replace it with:

```python
pred = np.argmax(model.predict(X_test), axis=1)
```

In the GUI, replace:

```python
pred = model.predict_classes([image])[0]
```

with:

```python
pred = np.argmax(model.predict(image), axis=1)[0]
```

## Example Usage

After launching the GUI:

1. Click **Upload an image**
2. Select a traffic sign image from your computer
3. Click **Classify Image**
4. The predicted traffic sign name will appear in the window

Example output:

```text
Stop
```

or:

```text
Speed limit (50km/h)
```

## Future Improvements

- Improve the GUI design
- Add confidence score for each prediction
- Add real-time webcam traffic sign detection
- Use data augmentation to improve accuracy
- Deploy the project as a web application
- Add prediction history
- Support drag-and-drop image upload

## Author

Created by Donya.

## License

This project is for educational purposes.
