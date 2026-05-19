# Real-Time Driver Drowsiness Detection System using Vision Transformer

A real-time driver drowsiness monitoring system using Vision Transformer (ViT) for accurate eye state analysis. The system achieves an accuracy of 98.8% in detecting driver drowsiness and triggers an instant alarm to prevent fatigue-related road accidents.

---

## About the Project

Driver fatigue is responsible for over 1.3 million deaths in road accidents each year according to the World Health Organization. This project presents an intelligent, non-intrusive real-time system that continuously monitors the driver's eye state using a Vision Transformer (ViT) model — alerting them the moment drowsiness is detected.

The system was developed and presented at the 2024 International Conference on Intelligent Systems and Advanced Applications (ICISAA), Pune, India.

---

## Features

- Real-time video processing via webcam or dashboard camera
- Face detection using Haar Cascade Classifier
- Eye state classification using fine-tuned Vision Transformer (ViT) model
- Detects open eye and closed eye states with high accuracy
- Instant audio alarm triggered when drowsiness is detected
- Works under varied lighting conditions including shady and dark environments
- Trained on 84,900 images with 98.8% accuracy

---

## Tech Stack

- Python
- OpenCV
- Vision Transformer (ViT) - google/vit-base-patch16-224-in21k
- PyTorch
- Haar Cascade Classifier
- NumPy

---

## How It Works

1. Camera captures live video feed of the driver
2. Haar Cascade Classifier detects the face in each frame
3. Feature extraction is performed using the ViT model feature extractor
4. Fine-tuned ViT model classifies the eye state as open or closed
5. If closed eye probability exceeds threshold of 0.5, drowsiness is detected
6. Alarm sound is triggered immediately to alert the driver

---

## Model Details

- Base Model: google/vit-base-patch16-224-in21k
- Additional fully connected layers with 128, 256, and 384 hidden units
- ReLU activation functions with dropout rate of 0.5
- Dataset: 84,900 images of open and closed eyes
- Data Split: 80% training, 10% validation, 10% testing
- Training Images: 67,920
- Epochs: 10
- Learning Rate: 0.00001
- Batch Size: 64 (training), 32 (validation and testing)

---

## Results

| Metric | Value |
|---|---|
| Detection Accuracy | 98.8% |
| Closed Eye Precision | 99.51% |
| Closed Eye Recall | 98.97% |
| Closed Eye F1-Score | 99.15% |
| Open Eye Precision | 99.91% |
| Open Eye Recall | 98.81% |
| Open Eye F1-Score | 99.16% |

---

## Getting Started

### Prerequisites

- Python 3.8 or higher
- Webcam or USB camera
- pip package manager

### Installation

1. Clone the repository

```bash
git clone https://github.com/Prathyusha-123456/Driver-Drowsiness-Detection.git
cd Driver-Drowsiness-Detection
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Run the system

```bash
python drowsiness_detection.py
```

---

## Project Structure

```
Driver-Drowsiness-Detection/
├── drowsiness_detection.py
├── app.py
├── model/
│   └── drowsiness_model.h5
├── requirements.txt
├── ABSTRACT.docx
├── INTRODUCTION.docx
├── SYSTEM_ANALYSIS.docx
├── INPUT_AND_OUTPUT_DESIGN.docx
├── TEST_CASES.docx
├── CONCLUSION.docx
├── FUTURE_ENHANCEMENT.docx
├── BIBLIOGRAPHY.docx
└── README.md
```

---

## Limitations

- Requires a front-facing camera for accurate detection
- Performance may reduce in complete darkness
- Does not detect drowsiness for drivers wearing sunglasses
- Designed for single driver monitoring only
- Requires moderate computing resources for real-time processing

---

## Future Enhancement

- Integrating head pose estimation and yawning detection
- Heart rate monitoring and steering behavior analysis
- Infrared or thermal imaging for nighttime driving
- Edge deployment on Raspberry Pi or NVIDIA Jetson
- Integration with Advanced Driver Assistance Systems (ADAS)
- IoT platform integration for real-time alerts to emergency services
- Online learning for personalized driver behavior adaptation

---

## Publication

This project was presented at:

2024 International Conference on Intelligent Systems and Advanced Applications (ICISAA), Pune, India, Oct 25-26, 2024.

DOI: 10.1109/ICISAA62385.2024.10829106

---

## Acknowledgements

- Vishwakarma Institute of Information Technology, Pune
- OpenCV — Computer vision framework
- Hugging Face — Vision Transformer model
- IEEE ICISAA 2024 — Conference publication

---

## Project Files

| File | Description |
|---|---|
| drowsiness_detection.py | Main detection script — runs the real-time drowsiness detection |
| app.py | Web application script — launches the system interface |
| model/drowsiness_model.h5 | Trained Vision Transformer model file |
| requirements.txt | List of all Python packages required to run the project |
| rainfall in india 1901-2015.csv | Dataset used for training and testing |
| README.md | Project documentation and setup guide |
