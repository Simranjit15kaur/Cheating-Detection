# Cheating Detection System for Online Interviews

## Project Overview
With the rise of online interviews, ensuring the integrity and fairness of the interview process has become a significant challenge. Candidates can exploit the remote nature of interviews to use unauthorized assistance. To address this issue, we propose a cheating detection system that utilizes computer vision and machine learning to monitor candidates in real-time and detect suspicious behavior indicative of cheating.

## Features
- **Multimodal Data Collection**: Captures video, audio, and interaction data.
- **Gaze and Device Detection**: Identifies if a candidate is looking away or using a mobile device.
- **Voice Activity Detection**: Monitors for external audio cues.
- **Behavioral Anomaly Detection**: Identifies irregular keyboard/mouse activity.
- **Real-Time Alerts**: Notifies users upon detecting suspicious behavior.
- **Automated Reporting**: Logs and records detected cheating instances for review.
- **Data Privacy and Security Compliance**: Ensures secure handling of user data.

## Dataset Description
The dataset consists of 200 video samples categorized into four types of cheating behavior:
1. Holding a smartphone
2. Head movement
3. Eye movement
4. Blocking eyes with a hand

Videos are labeled using the format `s_numPerson_scenario.mp4` (e.g., `s_2_3.mp4` represents the second person in the third scenario).

## Pre-Processing
1. **Segmentation**: Identifies key objects within video frames.
2. **Data Augmentation**: Uses the `Albumentations` library to generate more training data.

## Methodology
1. **Video Capture**: A webcam continuously records the candidate.
2. **Feature Extraction**: YOLOv5s is used to detect faces, eyes, and objects.
3. **Behavior Analysis**:
   - CNN for face and gaze tracking
   - RNN for voice anomaly detection
   - Anomaly detection for keyboard/mouse behavior
4. **Cheating Detection Module**: Analyzes movements and raises alerts if necessary.
5. **Real-Time Feedback**: Alerts are sent to candidates upon detecting anomalies.

## Model Design
- **YOLOv5s**: Object detection for face, eyes, and mobile devices.
- **CNN**: Used for face and gaze analysis.
- **RNN**: Detects abnormal voice patterns.
- **Clustering Algorithms**:
  - Self-Organizing Maps (SOM)
  - Fuzzy C-Means
  - Time Series K-Means

## Training Process
- Data is cleaned to remove noise in feature labels.
- Clustering algorithms classify cheating behaviors without predefined labels.
- Experiments with batch sizes (16, 32) and epochs (15) to determine optimal settings.

## Evaluation Metrics
- Images are resized to 450x450 pixels.
- Best accuracy obtained with batch size 16 and 15 epochs.
- The clustering algorithm achieves an average accuracy of **83.60%**.

## Results
- The system successfully detects cheating behavior with high accuracy.
- All clusters achieve over 50% accuracy in classifying behaviors.
- Identified cheating behaviors are stored as video evidence for review.

## Limitations & Future Work
- **Camera Placement**: System accuracy drops if the camera is positioned incorrectly.
- **Behavior Differentiation**: Needs better distinction between similar behaviors (e.g., "eye left" vs. "eye peek left").
- **Future Enhancements**:
  - Collecting data from different angles and multiple subjects.
  - Refining clustering models for improved accuracy.

## Installation & Setup
### Prerequisites
- Python 3.x
- OpenCV
- YOLOv5
- TensorFlow/PyTorch
- Albumentations
- Scikit-learn

   ```

## Contributors
- Simranjit Kaur (102216033)
-  Kriti Singh Behl (102216057)

## License
This project is licensed under the MIT License.

