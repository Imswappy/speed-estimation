
# YOLOv8 + DeepSORT Tracking and Speed Estimation in Google Colab
<img width="1894" height="935" alt="Screenshot 2025-08-30 230416" src="https://github.com/user-attachments/assets/984d4ab3-e2b8-4604-8e50-3d7a24166898" />


## Overview
This project integrates YOLOv8 for object detection with DeepSORT for multi-object tracking and adds speed estimation functionality.  
It is designed to run in Google Colab with GPU acceleration for real-time performance.

## Features
- Detect objects using YOLOv8
- Track multiple objects using DeepSORT
- Estimate object speed in video sequences
- Supports local video upload or direct camera feed
- Outputs annotated video with bounding boxes, IDs, and speed

## Table of Contents
1. Setup Colab Environment
2. Clone Repository
3. Install Dependencies
4. Download Pre-trained Models
5. Prepare Input Video
6. Run Tracking and Speed Estimation
7. Download Results
8. Tips and Notes

## 1. Setup Colab Environment
- Open a new Colab notebook
- Select Runtime > Change runtime type > GPU

## 2. Clone Repository

## 3. Install Dependencies
```bash
!pip install -r requirements.txt
!pip install ultralytics opencv-python
```

## 4. Download Pre-trained Models
Download YOLOv8 detection weights and DeepSORT files:
```bash
# Example YOLOv8s model
!wget -O yolov8s.pt https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8s.pt

# DeepSORT checkpoint
!wget -O deepsort_pytorch.ckpt <DeepSORT model URL>
```

## 5. Prepare Input Video
- Upload your video to Colab:
```python
from google.colab import files
uploaded = files.upload()
video_path = list(uploaded.keys())[0]
```
- Alternatively, link a video from Google Drive.

## 6. Run Tracking and Speed Estimation
Open and run the provided notebook:
```bash
YOLOv8_DeepSORT_Tracking_SpeedEstimation.ipynb
```
Steps in the notebook:
1. Initialize YOLOv8 detector
2. Initialize DeepSORT tracker
3. Set video input and output paths
4. Run tracking and speed estimation
5. Display annotated video frames

## 7. Download Results
After processing, download the output video:
```python
from google.colab import files
files.download('output_video.mp4')
```

## 8. Tips and Notes
- Ensure the video resolution matches your GPU memory limits.
- Speed estimation is approximate and depends on camera calibration.
- For multiple videos, loop through each input file using the notebook cells.
- Check GPU usage with `!nvidia-smi` for optimal performance.

## References
- YOLOv8: https://github.com/ultralytics/ultralytics
- DeepSORT PyTorch: https://github.com/mikel-brostrom/Yolov8_DeepSORT
