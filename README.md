# Real-Time Sign Language Action Detection ver0.1

## Overview

This project demonstrates real-time detection of specific sign language gestures ('hello', 'thanks', 'iloveyou') using OpenCV, MediaPipe for landmark detection, and a TensorFlow/Keras LSTM model for classification.

**Note:** The current model was trained on a small, personally recorded dataset. Accuracy is limited, and work is ongoing to create a larger dataset for improvement.

## Features

*   Real-time sign detection from webcam feed.
*   Uses MediaPipe Holistic for pose, face, and hand tracking.
*   LSTM model for sequence classification.
*   Displays landmarks and recognized signs.

## How it Works

1.  Captures webcam frames (OpenCV).
2.  Detects landmarks (MediaPipe).
3.  Extracts keypoint coordinates.
4.  Buffers keypoints into sequences (last 30 frames).
5.  Predicts action using the trained LSTM model (`sign_language_model.keras`).
6.  Displays results with smoothing/thresholding.

## Dataset

The model was trained on 30 sequences per action, recorded by the author. Expanding this dataset is the primary goal for improving performance.

## Technology Stack

*   Python 3.x
*   OpenCV
*   MediaPipe
*   TensorFlow / Keras
*   NumPy

## Setup

1.  **Prerequisites:** Python 3.8+, Pip, Webcam.
2.  **Clone:** `git clone https://github.com/saikumarsk2210/SignLanguage-Recognition-Using-Actions.git`
3.  **Virtual Environment (Recommended):**
    ```bash
    python -m venv .venv 
    # Activate: .\.venv\Scripts\activate (Win) or source .venv/bin/activate (Mac/Linux)
    ```
4.  **Install Dependencies:**
    ```bash
    !pip install --upgrade tensorflow opencv-python mediapipe scikit-learn matplotlib

    ```

## Usage

1.  Place the `sign_language_model.keras` file in the project root.
2.  **Launch Jupyter:** Open your terminal/command prompt in the project directory and run:
    ```bash
    jupyter notebook 
    # OR
    jupyter lab 
    ```
3.  **Open Notebook:** Your web browser should open the Jupyter interface. Navigate to and open the main project notebook file (e.g., `Sign_Language_Detection.ipynb`).
4.  **Run Cells:** Execute the cells in the notebook sequentially. The cell containing the main detection loop will activate your webcam and open an OpenCV window.
5.  **Perform Signs:** Perform signs in front of the webcam.
6.  **Quit:** To stop the detection, interrupt the kernel in Jupyter (usually via the "Kernel" menu or a stop button) and press 'q' in the active OpenCV window. Close the Jupyter Notebook server in your terminal when finished (usually Ctrl+C).

## Future Improvements

*   **Expand Dataset:** Collect more varied data (in progress).
*   Improve prediction logic & model architecture.
*   Optimize for speed.

## License

*This project is licensed under the MIT License*
