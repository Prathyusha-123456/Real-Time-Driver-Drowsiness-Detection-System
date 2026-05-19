Real-Time Driver Drowsiness Detection System
Overview

This project presents a Django-based web application designed to detect driver drowsiness in real time using deep learning techniques. The system analyzes facial features through a webcam to identify signs of fatigue such as eye closure and yawning. Upon detecting drowsiness, it triggers an alert to help prevent potential accidents.

The application integrates multiple deep learning models, including Convolutional Neural Networks (CNN), Vision Transformer (ViT), and a hybrid CNN-ViT model, to improve detection accuracy.

Features
Separate authentication system for administrators and drivers
Real-time webcam-based monitoring
Eye state classification (open or closed)
Yawn detection (yawn or no yawn)
Audio alert system for drowsiness detection
Detection history tracking for each driver
Support for multiple deep learning models
Web-based interface accessible through a browser
System Architecture

The system operates through the following pipeline:

Capture video input from the driver's webcam
Detect face using Haar Cascade or dlib
Extract regions of interest such as eyes and mouth
Perform classification using deep learning models
Apply decision logic to determine drowsiness
Trigger alert and log detection results
Technology Stack

Backend: Python, Django
Deep Learning: TensorFlow, Keras
Computer Vision: OpenCV, dlib
Frontend: HTML, CSS, Bootstrap, jQuery
Database: SQLite3
Alert System: WAV audio playback

Project Structure

DriverDrowsiness/
├── admins/
├── users/
│ ├── utility/
│ └── dlibfatigue/
├── assets/
│ ├── static/
│ └── templates/
├── media/
│ ├── models/
│ ├── data/
│ └── alarm.wav
├── DriverDrowsiness/
├── manage.py
└── requirements.txt

Models

The system uses the following trained models:

CNN: Baseline convolutional neural network
Improved CNN: Deeper and regularized version
Vision Transformer (ViT): Transformer-based image classification
Hybrid CNN-ViT: Combined architecture for improved performance
Best Model: Highest accuracy model selected after evaluation
Dataset

The dataset consists of four categories:

Open eyes
Closed eyes
Yawning
No yawning

Data is organized into training and validation sets, with images extracted as regions of interest from facial features.

Installation
Prerequisites
Python (version 3.7 to 3.11)
pip
Webcam
Steps
Clone the repository
git clone https://github.com/your-username/driver-drowsiness-detection.git
Navigate to the project directory
cd driver-drowsiness-detection
Create a virtual environment
python -m venv venv
Activate the environment
On Windows: venv\Scripts\activate
On Linux or macOS: source venv/bin/activate
Install dependencies
pip install -r requirements.txt
Apply database migrations
python manage.py migrate
Create an administrator account
python manage.py createsuperuser
Run the development server
python manage.py runserver

Access the application at http://127.0.0.1:8000

Usage
Administrator
Log in through the admin portal
Manage registered users
View detection logs
Driver
Register and log in
Start the detection module
Allow webcam access
Receive alerts when drowsiness is detected
View personal detection history
Documentation

Detailed project documentation is available in the DOCUMENTS directory, including:

Abstract
Introduction
Literature Survey
System Analysis
System Design
Modules
Test Cases
Conclusion

The base research paper related to the Vision Transformer model is included in the BASEPAPER directory.

Future Enhancements
Mobile application integration
Head pose estimation for distraction detection
Multi-user session handling
Notification system for alerts
Deployment on embedded systems such as Raspberry Pi or Jetson
Integration with vehicle systems for automated responses
License

This project is intended for academic and research purposes. Proper citation is recommended if the work is extended or reused.

Acknowledgements

This project utilizes tools and libraries such as OpenCV and dlib for computer vision and facial landmark detection.
