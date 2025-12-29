# Yoga Pose Estimation & Correctness Analysis

This project focuses on using **Computer Vision** to detect yoga poses and evaluate the "correctness" of each posture by comparing real-time body angles against statistical norms.

---

## Project Overview
The system uses a combination of **YOLO (You Only Look Once)** for person detection and **MediaPipe** for high-precision keypoint estimation. The project is split into several methodologies to find the most accurate way to classify poses and provide feedback on whether a user is performing the pose correctly.

---

## Key Components & Methodology

### 1. Person Detection Comparison
- Comparing different YOLO models (**YOLOv8, YOLOv10, YOLOv11**) to determine the most efficient backbone for detecting humans in various yoga environments.

### 2. Angle Distribution & Percentile Analysis
- Analyzed the statistical distribution of joint angles (elbows, knees, hips) across a standard dataset.  
- **Goal:** Establish a "Golden Standard" using the 5th and 95th percentiles ($P_5$ and $P_{95}$) to define the range of motion for "correct" poses.

### 3. Pose Estimation Methods
- **Method 1: Geometric-Based**  
  Uses calculated joint angles and trigonometry to identify poses (e.g., Tree, Warrior II, Downward Dog).  

- **Method 2: Machine Learning-Based**  
  Employs trained classifiers to recognize patterns in keypoint coordinates for more robust detection.

---

## Repository Structure
- `Comparison_YOLO_Person_Detection.ipynb` – Benchmark and selection of the detection model  
- `Angle_distribution_and_Keypoint_Percentile.ipynb` – Data analysis to find thresholds for "correct" vs "incorrect" postures  
- `Yoga_Pose_Estimation_Method_1.ipynb` – Implementation using direct angle calculation  
- `Yoga_Pose_Estimation_Method_2.ipynb` – Implementation using ML-based classification  

---

## Technologies Used
- **Models:** YOLOv8/v11, MediaPipe Pose  
- **Libraries:** ultralytics, mediapipe, opencv-python, scikit-learn, roboflow  
- **Platform:** Google Colab (with T4 GPU acceleration)  

---

## Results & Capabilities
- **Pose Detection:** Real-time identification of common yoga poses (Tree, Plank, Warrior, Goddess, etc.)  
- **Correctness Feedback:** Visualizes keypoints and highlights joints outside the "ideal" angle range to help users correct their form  
- **Video Processing:** Supports batch processing of MP4 files with automated annotation and output generation  

