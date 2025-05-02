# Real-Time Sign Language Action Detection

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
2.  **Clone:** `git clone https://github.com/your_username/your_repository_name.git && cd your_repository_name`
3.  **Virtual Environment (Recommended):**
    ```bash
    python -m venv .venv 
    # Activate: .\.venv\Scripts\activate (Win) or source .venv/bin/activate (Mac/Linux)
    ```
4.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Ensure `requirements.txt` exists)*

## Usage

1.  Place the `sign_language_model.keras` file in the project root.
2.  Run the detection script:
    ```bash
    python realtime_detection.py
    ```
3.  Perform signs in front of the webcam.
4.  Press 'q' to quit.

## Future Improvements

*   **Expand Dataset:** Collect more varied data (in progress).
*   Improve prediction logic & model architecture.
*   Optimize for speed.

## License

*This project is licensed under the MIT License*
