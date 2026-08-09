# 🚗 Drowsy Driver Detection System

A **real-time machine learning and computer vision system** designed to detect driver drowsiness by analyzing eye and facial patterns from a live camera feed. When prolonged eye closure or signs of drowsiness are detected, the system triggers an alert to help prevent fatigue-related accidents.

---

## 📌 Project Overview

Driver fatigue is one of the major causes of road accidents. This project aims to provide an automated solution for detecting early signs of driver drowsiness using **computer vision and deep learning**.

The system captures video frames from a camera, detects the driver's face and eyes, analyzes their eye state, and determines whether the driver is **alert or drowsy**.

If the system detects prolonged eye closure beyond a defined threshold, an **audio alarm** is triggered to notify the driver.

---

## 🎯 Objectives

* Detect the driver's face and eyes in real time.
* Classify the driver's eye state as **Open** or **Closed**.
* Identify prolonged eye closure as a potential sign of drowsiness.
* Trigger an alert when drowsiness is detected.
* Build a lightweight and practical computer vision solution suitable for real-time applications.

---

## 🏗️ System Workflow

```text
        Camera Feed
             │
             ▼
     Capture Video Frame
             │
             ▼
       Face Detection
             │
             ▼
        Eye Detection
             │
             ▼
    Eye State Classification
       ┌────────┴────────┐
       │                 │
     Open              Closed
       │                 │
       ▼                 ▼
   Driver Alert      Track Duration
                           │
                           ▼
                  Drowsiness Threshold
                           │
                    ┌──────┴──────┐
                    │             │
                   No            Yes
                    │             │
                    ▼             ▼
                Continue       🚨 Alarm
```

---

## 🧠 Machine Learning Approach

The system uses a **deep learning-based image classification model** to identify whether the driver's eyes are open or closed.

### Processing Pipeline

1. Capture frames from the webcam.
2. Detect the driver's face.
3. Locate the eye regions.
4. Preprocess the eye images.
5. Pass the eye images through the trained ML/DL model.
6. Predict the eye state.
7. Monitor consecutive closed-eye predictions.
8. Trigger an alarm when the drowsiness threshold is exceeded.

---

## 🛠️ Tech Stack

| Technology             | Purpose                               |
| ---------------------- | ------------------------------------- |
| **Python**             | Core programming language             |
| **OpenCV**             | Real-time image and video processing  |
| **TensorFlow / Keras** | Deep learning model development       |
| **NumPy**              | Numerical and array operations        |
| **Pandas**             | Dataset manipulation and analysis     |
| **Scikit-learn**       | Model evaluation and preprocessing    |
| **CNN**                | Eye-state image classification        |
| **Computer Vision**    | Face and eye detection                |
| **Jupyter Notebook**   | Model development and experimentation |

---

## 📂 Project Structure

```text
Drowsy-Driver-Detection/
│
├── dataset/
│   ├── train/
│   │   ├── open/
│   │   └── closed/
│   └── test/
│       ├── open/
│       └── closed/
│
├── model/
│   └── drowsiness_model.h5
│
├── notebooks/
│   └── model_training.ipynb
│
├── src/
│   ├── train.py
│   ├── detect.py
│   └── alarm.py
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 📊 Dataset

The model is trained using images representing different eye states:

* 👁️ **Open Eyes**
* 😴 **Closed Eyes**

The dataset is divided into training and testing subsets to evaluate the model's ability to generalize to unseen images.

---

## 🤖 Model

A **Convolutional Neural Network (CNN)** is used for eye-state classification.

The CNN learns visual patterns associated with open and closed eyes and predicts the eye state for each detected eye region.

### Example Model Pipeline

```text
Input Image
     │
     ▼
Image Preprocessing
     │
     ▼
Convolution Layer
     │
     ▼
Pooling Layer
     │
     ▼
Convolution Layer
     │
     ▼
Pooling Layer
     │
     ▼
Flatten
     │
     ▼
Dense Layer
     │
     ▼
Output Layer
     │
     ▼
Open / Closed
```

---

## 🚨 Drowsiness Detection Logic

A single closed-eye prediction does not necessarily indicate drowsiness.

Therefore, the system tracks **consecutive frames in which the eyes are detected as closed**.

```text
Eye Closed
    ↓
Track Duration
    ↓
Threshold Reached?
   ↙        ↘
 No         Yes
 ↓           ↓
Continue   Trigger Alarm
```

This helps reduce false alarms caused by normal blinking.

---

## ⚙️ Installation

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/Drowsy-Driver-Detection.git
cd Drowsy-Driver-Detection
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Activate it on Linux/macOS:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Start the real-time detection system:

```bash
python src/detect.py
```

The application will access the webcam and begin monitoring the driver's eye state.

When prolonged eye closure is detected, the system activates the warning alarm.

---

## 📈 Model Evaluation

The trained model can be evaluated using metrics such as:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

Example:

```text
              Precision   Recall   F1-Score

Open Eyes       XX%        XX%       XX%
Closed Eyes     XX%        XX%       XX%

Accuracy: XX%
```

> Replace the placeholder values with the actual results from your trained model.

---

## 🔍 Key Features

* ✅ Real-time webcam monitoring
* ✅ Face and eye detection
* ✅ CNN-based eye-state classification
* ✅ Open/closed eye recognition
* ✅ Drowsiness threshold detection
* ✅ Real-time warning alarm
* ✅ Lightweight computer vision pipeline
* ✅ Machine learning model evaluation

---

## 🚀 Future Improvements

* Integrate **facial landmark detection** for improved accuracy.
* Incorporate **head-pose estimation**.
* Detect **yawning** as an additional fatigue indicator.
* Use **eye aspect ratio (EAR)** for improved drowsiness detection.
* Deploy the model on an **edge device** such as Raspberry Pi.
* Add mobile or IoT-based notifications.
* Improve robustness under different lighting conditions.
* Explore lightweight models such as **MobileNet** for edge deployment.

---

## 💡 Applications

The system can be adapted for:

* 🚗 Personal vehicles
* 🚛 Commercial transportation
* 🚌 Public transportation
* 🚆 Operator monitoring systems
* 🏭 Industrial safety monitoring
* 🚚 Fleet management systems

---

## ⚠️ Limitations

The system's performance may be affected by:

* Poor lighting conditions
* Sunglasses or obstructed eyes
* Camera positioning
* Facial occlusion
* Different camera qualities
* Extreme head movements

This project is intended as a **prototype/research implementation** and should not be considered a replacement for certified automotive safety systems.

---

## 👨‍💻 Skills Demonstrated

This project demonstrates practical experience with:

* Machine Learning
* Deep Learning
* Convolutional Neural Networks
* Computer Vision
* Image Classification
* Real-Time Video Processing
* Model Training & Evaluation
* Python Programming
* OpenCV
* TensorFlow/Keras

---

## 📜 License

This project is available for educational and research purposes. Add an appropriate license to the repository if you intend to distribute or modify the project publicly.

---

## ⭐ Project Highlights

> **Built a real-time drowsiness detection system using Python, OpenCV, and CNN-based image classification to identify prolonged eye closure and trigger driver alerts.**
