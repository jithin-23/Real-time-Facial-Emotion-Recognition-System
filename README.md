# Real-time Facial Emotion Recognition System

The **Real-time Facial Emotion Recognition System** is designed to assist visually impaired individuals in their social interactions by detecting and recognizing human emotions from facial expressions. The system utilizes deep learning techniques, employing a Convolutional Neural Network (CNN) model fine-tuned with transfer learning using the MobileNetV2 architecture. Additionally, the system can identify known faces, making it a comprehensive tool for both emotion detection and facial recognition. Audio output is provided to ensure usability for visually impaired users.

## Features

- **Facial Emotion Recognition**: Detects emotions such as Happy, Sad, Angry, Surprise, Fear, Neutral, and Disgust.
- **Known Face Identification**: Identifies and labels known faces in real-time.
- **Real-time Processing**: Efficiently processes live video feed for emotion and face detection.
- **Audio Output**: Outputs detected faces and predicted emotions as audio.

## Installation and Setup

Follow these steps to set up and run the project on your machine:

### 1. Preparing Anaconda and TensorFlow
- Download and install the Anaconda Distribution: [Anaconda Install Guide](https://docs.anaconda.com/anaconda/install/)
- Open Anaconda Prompt.
- Install TensorFlow in a new environment and activate it: [TensorFlow with Conda Guide](https://docs.anaconda.com/working-with-conda/applications/tensorflow/)
  
    ```sh
    conda create -n tf tensorflow
    conda activate tf
    ``` 

### 2. Clone the Repository and Install Required Packages
- Clone the repository:
    ```sh
    git clone https://github.com/jithin-23/Real-time-Facial-Emotion-Recognition-System.git
    ```
- Navigate to the project directory:
    ```sh
    cd Real-time-Facial-Emotion-Recognition-System
    ```
- Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

### 3. Dataset Preparation
- The dataset used is **FER2013**. Download it [here](https://www.kaggle.com/datasets/msambare/fer2013).
- Create two folders named **Training** and **Test** in your project directory.
  - **Training Folder**: Contains all the images from the 'train' subdirectory of the FER 2013 dataset. Rename the emotions as numbers from 0 to 6 (Anger -> 0, Disgust -> 1, Fear -> 2, Happy -> 3, Sad -> 4, Surprise -> 5, Neutral -> 6).
  - **Test Folder**: Contains all images from the 'test' subdirectory of the FER 2013 dataset, with emotions renamed similarly.
- Balance the classes as necessary due to the imbalanced nature of the FER2013 dataset.
- If using other datasets, ensure the class names align with those in the code.

### 4. Open Jupyter Notebook
- Start Jupyter Notebook:
    ```sh
    jupyter notebook
    ```

### 5. Model Training
- The training code is provided in the file [01_Training_Code.ipynb](01_Training_Code.ipynb). It is recommended to run all files in Jupyter Notebook.
- When saving the model, ensure you rename it as desired:
    ```python
    new_model.save('your_model_name.h5')
    ```
- Ensure that the Training folder is properly set up with subfolders named from 0 to 6.
- Adjust the number of epochs based on your computational resources.
- Refer to this YouTube guide for additional help: [Real-time Face Emotion Recognition](https://www.youtube.com/watch?v=avv9GQ3b6Qg)

### 6. Model Evaluation and Testing
- The evaluation code is available in [02_Test.ipynb](02_Test.ipynb).
- Make sure the Test folder is correctly organized.
- Enter the correct model name when testing.
- The output includes a confusion matrix and accuracy metrics.

### 7. Real-time Emotion Recognition
- The code for real-time emotion recognition is in [03_Emotion_Recognition.ipynb](03_Emotion_Recognition.ipynb).
- Ensure your webcam is functioning correctly.

### 8. Emotion and Face Recognition Execution

#### Installation of Required Modules
Before running the file, install the `face_recognition` module and its dependencies:

1. **Install cmake**:
    ```sh
    pip install cmake
    ```

2. **Install Visual Studio for C++**:
   - Install Visual Studio for C++ for compiling dependencies.
   - Guide: [Installing Visual Studio for C++ on Windows](https://www.youtube.com/watch?v=f9QZQumiC8I)

3. **Install face_recognition**:
    ```sh
    pip install face_recognition
    ```

- **Troubleshooting**:
    - If errors occur during installation, try:
        - **Installing dlib separately**:
        ```sh
        conda install -c conda-forge dlib
        ```
        - **Checking Path Variable**: Ensure the `cl.exe` path from Visual Studio is correctly added to the environment variables.

#### Execution Script
- The code for real-time emotion and face recognition is in [04_Emotion_and_Facial_Recognition.ipynb](04_Emotion_and_Facial_Recognition.ipynb).
  - **Unknown Faces**: Detected faces not in the database will be labeled as 'Unknown'.
  - **Saving New Faces**: Press **n** during execution to save an unknown face. A screenshot will be taken, and you'll be prompted to enter a name for the new face, which will be saved with that name.
  - **Displaying Saved Faces**: Saved faces will be recognized and displayed with the assigned name.

## Contact

For any inquiries, please email: [jithinka23@gmail.com](mailto:jithinka23@gmail.com)

