 Real-Time Driver Drowsiness Detection System
A Django-based web application that detects driver drowsiness in real time using deep learning models — including CNN, Vision Transformer (ViT), and a hybrid approach — to monitor eye state and yawning, and trigger alerts before accidents happen.

📌 Table of Contents

Overview
Features
System Architecture
Tech Stack
Project Structure
Models
Dataset
Installation
Usage
Screenshots
Documents
Future Enhancements


Overview
Driver fatigue is one of the leading causes of road accidents worldwide. This system uses computer vision and deep learning to monitor a driver's face in real time, detect signs of drowsiness (closed eyes, yawning), and immediately trigger an audio alarm alert.
The project is built on Django with a user/admin role system, and uses multiple trained deep learning models for detection — including CNN, Vision Transformer (ViT), and a hybrid CNN+ViT model — along with Haar Cascade and dlib-based facial landmark detection.

Features

🔐 Separate login for Admin and Driver (Autoist)
📷 Real-time webcam-based drowsiness detection
👁️ Eye state classification: Open / Closed
😮 Yawn detection: Yawn / No Yawn
🔔 Audio alarm triggered on drowsiness detection
📊 Detection history log per driver
🧠 Multiple model support: CNN, ViT, Hybrid CNN+ViT
🌐 Web-based interface (accessible via browser)


System Architecture
Driver's Webcam
      ↓
Face Detection (Haar Cascade / dlib)
      ↓
ROI Extraction (Eyes + Mouth)
      ↓
Deep Learning Classification
  ├── Eye State: Open / Closed
  └── Mouth State: Yawn / No Yawn
      ↓
Drowsiness Logic
      ↓
Alarm Trigger + History Logging

Tech Stack
LayerTechnologyBackendPython 3, DjangoDeep LearningTensorFlow / KerasFace DetectionOpenCV (Haar Cascade), dlibModelsCNN, Vision Transformer (ViT), HybridFrontendHTML, CSS, Bootstrap, jQueryDatabaseSQLite3AlarmWAV audio playback

Project Structure
DriverDrowsiness/
├── admins/                  # Admin app (views, models, migrations)
├── users/                   # Driver (Autoist) app
│   ├── utility/
│   │   ├── detections.py    # Core detection logic
│   │   └── model.py         # Model loading utilities
│   └── dlibfatigue/
│       ├── Fatigue_Detection.py
│       └── shape_predictor_68_face_landmarks.dat
├── assets/
│   ├── static/              # CSS, JS, images, fonts
│   └── templates/           # HTML templates (admin + autoist views)
├── DriverDrowsiness/        # Django project settings, URLs, WSGI
├── media/
│   ├── alarm.wav            # Alert sound
│   ├── models/              # Trained model files (.h5)
│   │   ├── cnnCat2.h5
│   │   ├── Dp_cnnCat2.h5
│   │   ├── Dp_vitCat2.h5
│   │   ├── Dp_hybrid_final.h5
│   │   └── best_model.h5
│   ├── haar cascade files/  # OpenCV XML classifiers
│   └── data/
│       ├── train/           # Training images (Open, Closed, Yawn, No_Yawn)
│       └── valid/           # Validation images
├── manage.py
└── requirements.txt

Models
ModelDescriptionFileCNNBaseline convolutional neural networkcnnCat2.h5CNN (Improved)Deeper/regularized CNNDp_cnnCat2.h5ViTVision Transformer for image classificationDp_vitCat2.h5Hybrid CNN+ViTCombined CNN feature extractor + TransformerDp_hybrid_final.h5Best ModelBest-performing checkpointbest_model.h5
The base paper implementing Vision Transformer for accuracy improvement is included in BASEPAPER/.

Dataset
Training data is organized into four classes:
media/data/
├── train/
│   ├── Open/       (~700 images) — open eyes
│   ├── Closed/     (~700 images) — closed eyes
│   ├── yawn/       (~700 images) — yawning mouth
│   └── no_yawn/    (~2600 images) — normal mouth
└── valid/
    ├── Open/
    ├── Closed/
    ├── yawn/
    └── no_yawn/

Eye images are grayscale crops from face regions. Yawn images are mouth region crops.


Installation
Prerequisites

Python 3.7 – 3.11
pip
Webcam

Steps
bash# 1. Clone the repository
git clone https://github.com/your-username/driver-drowsiness-detection.git
cd driver-drowsiness-detection/CODE/DriverDrowsiness

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate        # Linux/macOS
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Apply database migrations
python manage.py migrate

# 5. Create a superuser (admin)
python manage.py createsuperuser

# 6. Run the development server
python manage.py runserver
Then open your browser at http://127.0.0.1:8000
Python Version
Check Python version.txt in the project root for the specific version used during development.

Usage
Admin

Log in at /admin-login
View all registered drivers
Monitor detection histories

Driver (Autoist)

Register and log in at the main page
Navigate to the detection page
Allow webcam access
The system will continuously analyze your face and sound an alarm if drowsiness is detected
View your detection history in the dashboard


Screenshots
Screenshots of the running application are available in DOCUMENTS/SCREEN SHOTS.docx.

Documents
Full project documentation is in the DOCUMENTS/ folder:
DocumentDescriptionABSTRACT.docxProject summaryINTRODUCTION.docxProblem statement and motivationLITERATURE SURVEY.docxRelated work reviewSYSTEM ANALYSIS.docxFeasibility and requirementsSYSTEM DESIGN.docxArchitecture and designMODULES.docxModule breakdownINPUT AND OUTPUT DESIGN.docxI/O specificationsSAMPLE CODE.docxCode excerptsTEST CASES.docxTest scenariosCONCLUSION.docxResults and conclusionsFUTURE ENHANCEMENT.docxPlanned improvementsBIBLOGRAPHY.docxReferences
The base research paper is at:
BASEPAPER/Real-Time_Driver_Drowsiness_Detection_System_using_Vision_Transformer_for_Accura.pdf

Future Enhancements

Mobile app integration for in-vehicle deployment
Head pose estimation for distraction detection
Multi-driver session support
SMS/push notification alerts to fleet managers
Edge deployment (Raspberry Pi, NVIDIA Jetson)
Integration with vehicle CAN bus for automatic speed reduction


License
This project is for academic and research purposes. Please cite the base paper if you build on this work.

Acknowledgements

OpenCV for Haar Cascade face/eye detection
dlib for facial landmark detection (68-point model)
The Vision Transformer (ViT) architecture from the research paper included in BASEPAPER/
