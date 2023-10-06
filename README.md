# CCTV Person Detection and Tracking

This repository contains a Python script for real-time person detection and tracking in CCTV footage. It utilizes the YOLO (You Only Look Once) object detection for person detection and the SORT (Simple Online and Realtime Tracking) algorithm for tracking individuals. Additionally, it extracts and stores features of detected persons using a pre-trained ResNet50 model.

## Table of Contents

- [Requirements](#requirements)
- [Usage](#usage)
- [Data Collection and Preprocessing](#data-collection-and-preprocessing)
- [Detection and Tracking](#detection-and-tracking)
- [Feature Extraction](#feature-extraction)
- [Directory Structure](#directory-structure)

## Requirements

Before running the script, make sure you have the following requirements installed:

- Python 3.x
- OpenCV
- NumPy
- TensorFlow/Keras
- SORT (Simple Online and Realtime Tracking) library
- YOLOv3 weights, configuration file, and COCO classes file
- Pre-trained ResNet50 model weights (for feature extraction)

## Usage

1. Clone this repository to your local machine:

   ```bash
   git clone https://github.com/yourusername/cctv-person-detection-tracking.git
   ```

2. Install the required libraries:

   ```bash
   pip install opencv-python numpy tensorflow sort
   ```

3. Download the YOLOv3 weights (`yolov3.weights`), configuration file (`yolov3.cfg`), and COCO classes file (`coco.names`) and place them in the project directory.

4. Download the pre-trained ResNet50 model weights from the Keras Applications library.

5. Modify the script to specify the paths to your video file and the pre-trained ResNet50 model weights.

6. Run the script:

   ```bash
   python main.py
   ```

## Data Collection and Preprocessing

In the data collection and preprocessing stage, the script reads frames from a video source (CCTV footage) and preprocesses each frame for object detection and tracking. The preprocessing includes resizing the frames and normalizing pixel values.

## Detection and Tracking

The detection and tracking process is performed using two main components:

- **YOLO (You Only Look Once) Detection**: YOLO is used to detect persons in each frame. It identifies bounding boxes around detected persons and provides confidence scores for each detection.

- **SORT (Simple Online and Realtime Tracking) Algorithm**: SORT is a tracking algorithm that associates detected bounding boxes across frames, assigning unique IDs to tracked individuals. It predicts the movement of each tracked object and matches it with detections in subsequent frames.

## Feature Extraction

Feature extraction involves capturing discriminative features from the detected persons using a pre-trained ResNet50 model. Each person's image is resized, preprocessed, and fed into the ResNet50 model to extract a feature vector. These feature vectors are stored in a dictionary, with track IDs as keys, for further analysis or re-identification.

## Directory Structure

- `output_frames/`: Directory to store saved frames from the video.
- `output_detected/`: Directory to store frames with detected persons and bounding boxes.

---
