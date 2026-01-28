# Tennis Analysis System

## Motivation
Automated tennis analysis is challenging due to fast ball motion,
occlusions, camera motion, and multiple players in the scene.
This project aims to design a robust multi-model computer vision
pipeline that jointly detects players, ball trajectory, and court
geometry to enable downstream sports analytics.


## Introduction
 In this project, we will build a Tennis Analysis System to detect and track players and the tennis ball. For player detection, we will use a pre-trained YOLOv12 model, while for tennis ball detection, we will fine-tune the YOLOv5 model on a tennis ball dataset from Roboflow. Additionally, we will detect tennis court keypoints by fine-tuning a ResNet50 model on the tennis court keypoints dataset.
To enhance the system, we will implement a player selection and filtering mechanism. Using the detected tennis court keypoints, we will detect the two players closest to the court.

## System Architecture
1. Frame extraction from video
2. Player detection and tracking using YOLOv12
3. Tennis ball detection using fine-tuned YOLOv5
4. Court keypoint detection using ResNet50
5. Player filtering based on proximity to court boundaries
6. Visualization and output video generation

## Output Videos
Here is a screenshot from one of the output videos:

![Screenshot](output_videos/screenshot.jpg)

## Models Used
* YOLOv12 for player detection and tracking
* Fine-Tuned YOLOv5 for tennis ball detection
* Fine-Tuned ResNet-50 to detect tennis court keypoints

* Trained YOLOV5 model for Tennis Ball Detection.
* Trained tennis court key point detection model.

## Model Selection Rationale
- YOLOv12 was chosen for player detection due to its superior
  real-time performance and tracking stability.
- YOLOv5 was fine-tuned for tennis ball detection because of
  its flexibility for small object detection.
- ResNet50 was used for keypoint regression due to its strong
  feature extraction capability and training stability.

## Training
* Tennis ball detetcor with YOLOv5: notebooks/tennis_ball_detector_training_yolov5.ipynb
* Tennis court keypoints detection: notebooks/tennis_courts_keypoints_detector_50.ipynb

## Limitations and Future Work
- Ball detection accuracy decreases under motion blur
- Occlusions affect player tracking consistency
- Future work includes trajectory prediction using LSTM/Transformer
- Integrating pose estimation for player movement analysis


## Requirements
* python3.11
* ultralytics
* pytroch
* numpy 
* opencv




