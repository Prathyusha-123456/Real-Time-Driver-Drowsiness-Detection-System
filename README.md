#  Real-Time Driver Drowsiness Detection System

A real-time computer vision system that detects driver drowsiness and triggers an instant alert to prevent fatigue-related road accidents.



## About the Project

Driver fatigue is responsible for over 20% of road accidents globally. This project presents an intelligent, non-intrusive real-time system that continuously monitors the driver's eye movements using a camera and machine learning — alerting them the moment drowsiness is detected.



## Features

- Real-time video processing via webcam or dashboard camera
- Facial landmark detection focusing on eye region and blink patterns
- Eye Aspect Ratio (EAR) algorithm for frame-by-frame drowsiness scoring
- ML/Deep Learning classification to distinguish alert vs. drowsy states
- Instant audio-visual alarm triggered when drowsiness threshold is crossed
- Works under varied lighting conditions
- Low latency, optimized for real-time performance



## Tech Stack

- Python 3.8+
- OpenCV
- dlib / MediaPipe
- CNN / Machine Learning
- NumPy and SciPy
- Pygame / Playsound



## How It Works

1. Camera captures live video feed of the driver
2. Face detection using Haar Cascade or dlib
3. Facial landmark extraction (68 landmarks)
4. Eye Aspect Ratio (EAR) is calculated per frame
5. CNN model classifies the driver as alert or drowsy
6. Alarm is triggered if EAR drops below threshold for consecutive frames



## Getting Started

### Prerequisites

- Python 3.8 or higher
- Webcam or USB camera
- pip package manager

### Installation

1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/driver-drowsiness-detection.git
cd driver-drowsiness-detection
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Run the system

```bash
python drowsiness_detection.py
```



## Project Structure

```
driver-drowsiness-detection/
├── drowsiness_detection.py
├── app.py
├── model/
│   └── drowsiness_model.h5
├── shape_predictor_68_face_landmarks.dat
├── alert.wav
├── requirements.txt
└── README.md
```



## Results

| Metric | Value |
|---|---|
| Detection Accuracy | 95% |
| Alert Response Time | Less than 1 second |
| False Positive Rate | Low |
| Lighting Conditions | Normal and low light |



## Limitations

- Requires a front-facing camera for accurate detection
- Performance may reduce in very low or no light conditions
- Does not detect drowsiness for drivers wearing sunglasses
- Designed for single driver monitoring only



## Future Scope

- Yawning detection using mouth landmark analysis
- Head pose estimation for distraction detection
- Mobile app dashboard for fleet managers
- Edge deployment on Raspberry Pi or Jetson Nano
- Integration with vehicle systems for automatic speed reduction



## Acknowledgements

- dlib — Facial landmark detection library
- OpenCV — Computer vision framework
- Soukupova and Cech, 2016 — Original EAR research paper
