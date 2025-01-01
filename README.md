# Traffic_sign_recognition
A Python-based project for recognizing traffic signs in images. The system utilizes YOLO for detecting traffic signs, a custom CNN for feature extractions, and computing cosine similarity for classification.

*Download pretrained models of YOLO and CNN here [Traffic_sign_recognition_models](https://drive.google.com/drive/folders/1d3zNdvNpWjqcBXehFX9IUEtI2dRwOkaW?usp=sharing)

## Pipeline
- **Traffic signs detection**: I decided to use YOLO (YOLOv8s version) to perform this task. With our dataset, the model achieved a precision score of **0.923** and a recall score of **0.904** when detecting traffic signs in images.

- **Feature extraction**: I created a custom CNN with the following structure for training and testing. After that, I used layers [0] to [-7] for the feature extraction task.
  - 23 layers:
    -  5 Convolutional blocks (Conv2D, BatchNormalization, MaxPooling2D, Dropout)
    -  1 Flatten layer
    -  4 Dense layers
    -  1 Activation layer
  - Optimizer: Adam
  - Loss function: sparse_categorical_crossentropy
  - Metrics: accuracy

- **Feature preparation**: I extracted features from the signs in the Traffic_sign folder and stored them in features.csv
- **Deloyment**: I used Streamlit to quickly create a UI for this app, including an upload space and a slider to adjust the confidence level of the YOLO model.

## Install and run app
'''Bash
git clone <URL of this repository>
'''
