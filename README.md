# Real-time Facial Emotion Recognition System

The Real-time Facial Emotion Recognition System is designed to aid visually impaired people during their social interactions by detecting and recognizing human emotions from facial expressions. The model is trained utilizing the FER 2013 dataset. This project employs deep learning techniques, specifically a Convolutional Neural Network (CNN) model fine-tuned with transfer learning using the MobileNetV2 architecture. Additionally, the system is capable of identifying known faces, making it a comprehensive tool for both emotion detection and facial recognition. The project provides output in audio format to ensure usability for visually impaired individuals.

## Features

- **Facial Emotion Recognition**: Detects emotions such as Happy, Sad, Angry, Surprise, Fear, Neutral, and Disgust.
- **Known Face Identification**: Identifies and labels known faces in real-time.
- **Real-time Processing**: Efficiently processes live video feed for emotion and face detection.
- **Audio Output**: The detected face and predicted emotion are given as audio output.

## Steps for Running

To set up the project on your machine, follow these steps:

1. **Clone the repository**:
    ```sh
    git clone [[https://github.com/your-username/Facial-Emotion-Recognition-System.git](https://github.com/jithin-23/Real-time-Facial-Emotion-Recognition-System)](https://github.com/jithin-23/Real-time-Facial-Emotion-Recognition-System)
    cd Facial-Emotion-Recognition-System
    ```

2. **Preparing Anaconda and TensorFlow**:
    - Download and install Anaconda Distribution: [Anaconda Install Guide](https://docs.anaconda.com/anaconda/install/)
    - Open Anaconda Prompt.
    - Install TensorFlow in a new environment and activate the newly created environment: [TensorFlow with Conda Guide](https://docs.anaconda.com/working-with-conda/applications/tensorflow/)
      
    ```sh
    conda create -n tf tensorflow
    conda activate tf
    ```
    
    - Install required packages:
      
    ```sh
    pip install -r requirements.txt
    ```
    
    - Open Jupyter Notebook:
      
    ```sh
    jupyter notebook
    ```

3. **Dataset Preparation**:
    - The dataset used is FER2013. Download the dataset [here](https://www.kaggle.com/datasets/msambare/fer2013).
    - Create two folders named **Training** and **Test** in your project directory.
    - The **Training** folder will contain all the photos from the 'train' subdirectory of FER 2013 dataset. The seven emotions are renamed to numbers from 0 to 6 representing the classes (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, and Neutral -> 6).
    - The **Test** folder will contain all photos from the 'test' subdirectory of FER 2013 dataset. The emotions are renamed in the same way.
    - Balance the classes as required since the FER2013 dataset has a highly imbalanced number of images across different classes.

4. **Training Code**:
    - The code for training the model is provided in the file [01_Training_Code.ipynb](01_Training_Code.ipynb). (Recommend opening and running all files in Jupyter Notebook)
    - Ensure you change the name to which you save the model to your desired name (this line is near the end of the document):
    ```python
    new_model.save('enter_name_here.h5')
    ```
    - Make sure you have properly created the Training folder and renamed all subfolders to names 0 to 6 (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, and Neutral -> 6).
    - Note that training will require substantial computational resources due to the large size of the dataset. Adjust the number of epochs as necessary.

5. **Evaluation and Testing**:
    - The code for evaluation of the model is provided in the file [02_Test.ipynb](02_Test.ipynb).
    - Make sure you have properly created the Test folder and renamed all subfolders to names 0 to 6 (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, and Neutral -> 6).
    - Ensure you enter the correct name of the model that you saved after training.
    - The output provides a confusion matrix and accuracy values.

6. **Code Execution: Emotion Recognition**:
    - The code for execution of real-time emotion recognition is given in the file [03_Emotion_Recognition.ipynb](03_Emotion_Recognition.ipynb).
    - Ensure you have a properly working webcam.

7. **Code Execution: Emotion Recognition and Face Recognition**:
    - The saved faces are stored in the folder **images**.
    - The code for execution of real-time emotion recognition and facial recognition is given in the file [04_Emotion_and_Facial_Recognition.ipynb](04_Emotion_and_Facial_Recognition.ipynb).
    - New faces are output as 'Unknown'.
    - If at any point you need to save an unknown face, press **n** on your keyboard. A screenshot is taken from the real-time camera feed and is stored with the new name. A prompt will ask for the name of the new face.
    - The saved faces will be shown with the name which is the name of your image file.



