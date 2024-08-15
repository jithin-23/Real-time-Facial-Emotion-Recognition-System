
# Real-time Facial Emotion Recognition System

The Real-time Facial Emotion Recognition System is designed to aid visually impaired people during their social interactions by detecting and recognizing human emotions from facial expressions. The model is trained using the FER 2013 dataset and employs deep learning techniques, specifically a Convolutional Neural Network (CNN) model fine-tuned with transfer learning using the MobileNetV2 architecture. Additionally, the system can identify known faces, making it a comprehensive tool for both emotion detection and facial recognition. The project provides audio output to ensure usability for visually impaired individuals.

## Features

- **Facial Emotion Recognition**: Detects emotions such as Happy, Sad, Angry, Surprise, Fear, Neutral, and Disgust.
- **Known Face Identification**: Identifies and labels known faces in real-time.
- **Real-time Processing**: Efficiently processes live video feed for emotion and face detection.
- **Audio Output**: The detected face and predicted emotion are given as audio output.

## Steps for Running

To set up the project on your machine, follow these steps:

1. **Preparing Anaconda and TensorFlow**:
    - Download and install the Anaconda Distribution: [Anaconda Install Guide](https://docs.anaconda.com/anaconda/install/)
    - Open Anaconda Prompt.
    - Install TensorFlow in a new environment and activate the environment: [TensorFlow with Conda Guide](https://docs.anaconda.com/working-with-conda/applications/tensorflow/)
      
    ```sh
    conda create -n tf tensorflow
    conda activate tf
    ``` 

2. **Clone the Repository**:
    ```sh
    git clone https://github.com/jithin-23/Real-time-Facial-Emotion-Recognition-System.git
    ```
    - Change the current working directory to 'Real-time-Facial-Emotion-Recognition-System':
      
    ```sh
    cd Real-time-Facial-Emotion-Recognition-System
    ```

    - Install required packages:
      
    ```sh
    pip install -r requirements.txt
    ```
    
3. **Dataset Preparation**:
    - The dataset used is FER2013. Download the dataset [here](https://www.kaggle.com/datasets/msambare/fer2013).
    - Create two folders named **Training** and **Test** in your project directory.
    - The **Training** folder will contain all the photos from the 'train' subdirectory of the FER 2013 dataset. The seven emotions are renamed to numbers from 0 to 6 representing the classes (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, and Neutral -> 6).
    - The **Test** folder will contain all photos from the 'test' subdirectory of the FER 2013 dataset. The emotions are renamed in the same way.
    - Balance the classes as required since the FER2013 dataset has a highly imbalanced number of images across different classes.

4. **Open Jupyter Notebook**:
    ```sh
    jupyter notebook
    ```

5. **Training Code**:
    - The code for training the model is provided in the file [01_Training_Code.ipynb](01_Training_Code.ipynb). (It is recommended to open and run all files in Jupyter Notebook.)
    - Ensure you change the name of the model to your desired name when saving it (this line is near the end of the document):
    ```python
    new_model.save('enter_name_here.h5')
    ```
    - Make sure you have properly created the Training folder and renamed all subfolders to numbers 0 to 6 (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, and Neutral -> 6).
    - Note that training will require substantial computational resources due to the large size of the dataset. Adjust the number of epochs as necessary.

6. **Evaluation and Testing**:
    - The code for evaluating the model is provided in the file [02_Test.ipynb](02_Test.ipynb).
    - Make sure you have properly created the Test folder and renamed all subfolders to numbers 0 to 6 (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, and Neutral -> 6).
    - Ensure you enter the correct name of the model that you saved after training.
    - The output provides a confusion matrix and accuracy values.

7. **Code Execution: Emotion Recognition**:
    - The code for executing real-time emotion recognition is given in the file [03_Emotion_Recognition.ipynb](03_Emotion_Recognition.ipynb).
    - Ensure you have a properly working webcam.

8. **Code Execution: Emotion Recognition and Face Recognition**:

- **Face Storage**: The saved faces are stored in the **images** folder.
- **Execution Script**: The code for executing real-time emotion recognition combined with facial recognition is in the file [04_Emotion_and_Facial_Recognition.ipynb](04_Emotion_and_Facial_Recognition.ipynb).
    - **Unknown Faces**: New faces detected by the system will be labeled as 'Unknown'.
    - **Saving New Faces**: If you wish to save an unknown face during execution, press **n** on your keyboard. This will capture a screenshot from the real-time camera feed, prompt you to enter a name for the new face, and save the image with the provided name.
    - **Display of Saved Faces**: Saved faces will be recognized and displayed with the name assigned during the saving process.

- **Installation of Required Modules**: Before running the file, you need to install the `face_recognition` module and its dependencies:

    1. **Install cmake**:
    ```sh
    pip install cmake
    ```

    2. **Install Visual Studio for C++**:
       - Install Visual Studio for C++ as it is required for compiling some dependencies.
       - You can refer to this guide: [Installing Visual Studio for C++ on Windows](https://www.youtube.com/watch?v=f9QZQumiC8I)

    3. **Install face_recognition**:
    ```sh
    pip install face_recognition
    ```

    - **Troubleshooting Installation Issues**:
        - If you encounter errors during the installation of `face_recognition`, follow these steps:
            - **Install dlib Separately**:
            ```sh
            conda install -c conda-forge dlib
            ```
            - **Ensure Path Variable**: Verify that the path variable for `cl.exe` from Visual Studio is correctly added.
            
