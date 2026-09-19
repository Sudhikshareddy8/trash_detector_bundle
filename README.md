# 🌊 Trash Detection and Segregation in Water

An AI-powered system designed to **detect, classify, and help segregate floating trash in water bodies using computer vision and deep learning**. The system can analyze live camera/video input, identify waste, and generate alerts when required.

## 🚀 Features

* 🎥 Real-time trash detection using camera/video input
* 🤖 AI-based object detection using YOLO
* 🗑️ Classification of different types of floating waste
* 🌊 Designed for rivers, lakes, ponds, and other water bodies
* 📍 Detection of trash location from video frames
* 🚨 Alert generation when specified objects/persons are detected
* 📊 Real-time detection results and confidence scores
* 🔄 Supports image and video-based detection
* 🌱 Helps support water-body cleanliness and environmental monitoring

## 🛠️ Technologies Used

* **Python**
* **YOLO / Ultralytics**
* **OpenCV**
* **NumPy**
* **PyTorch**
* **Roboflow** – Dataset preparation and annotation
* **Google Colab / VS Code**
* **Git & GitHub**

## 📁 Project Structure

```text
trash-detection/
│
├── dataset/
│   ├── images/
│   ├── labels/
│   └── data.yaml
│
├── models/
│   └── best.pt
│
├── runs/
│   └── detect/
│
├── input/
│   ├── images/
│   └── videos/
│
├── output/
│   ├── images/
│   └── videos/
│
├── detect.py
├── train.py
├── requirements.txt
└── README.md
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/trash-detection.git
cd trash-detection
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## 📦 Requirements

Example `requirements.txt`:

```text
ultralytics
opencv-python
numpy
torch
torchvision
matplotlib
pandas
```

## 🧠 Dataset

The dataset contains images of floating waste collected from water environments.

Example classes:

```text
Plastic
Bottle
Plastic Bag
Can
Paper
Other Waste
```

The dataset can be annotated using **Roboflow** or another object-labeling platform and exported in YOLO format.

## 🏋️ Model Training

Train the YOLO model using:

```bash
yolo detect train data=dataset/data.yaml model=yolov8n.pt epochs=50 imgsz=640
```

After training, the best model is generally saved as:

```text
runs/detect/train/weights/best.pt
```

Copy the trained model into:

```text
models/best.pt
```

## 🎯 Detection

Run detection on an image:

```bash
yolo detect predict model=models/best.pt source=input/images
```

Run detection on a video:

```bash
yolo detect predict model=models/best.pt source=input/videos/trash.mp4
```

Run detection using a webcam:

```bash
yolo detect predict model=models/best.pt source=0
```

## 🐍 Python Detection

Example:

```python
from ultralytics import YOLO

model = YOLO("models/best.pt")

results = model.predict(
    source="input/videos/trash.mp4",
    conf=0.5,
    save=True
)

print("Trash detection completed.")
```

## 📊 Output

The system provides:

* Detected object name
* Bounding box
* Confidence score
* Number of detected objects
* Annotated image/video
* Detection timestamp

Example:

```text
Detected Object : Plastic Bottle
Confidence      : 92%
Status          : Detected
```

## 🚨 Alert System

The system can be extended with an alert mechanism.

When a predefined object is detected:

```text
Camera
   ↓
Video Frame
   ↓
YOLO Detection
   ↓
Object Identified
   ↓
Check Detection Rules
   ↓
Generate Alert
   ↓
Store/Send Notification
```

Possible notification methods include:

* Email
* SMS
* Mobile notification
* Web dashboard
* Emergency/police notification where appropriate

## 🌍 Applications

This project can be used for:

* River pollution monitoring
* Lake cleaning
* Smart water-body monitoring
* Municipal waste management
* Environmental research
* Smart-city projects
* Automated waste collection systems

## 🔮 Future Scope

Future versions can include:

* 🚤 Autonomous trash-collecting boats
* 📍 GPS-based trash location mapping
* 📱 Mobile application
* ☁️ Cloud-based monitoring dashboard
* 📈 Pollution analytics
* 🚨 Automated notification system
* 🛰️ Drone-based water monitoring
* ♻️ Automatic trash segregation
* 🔋 Solar-powered monitoring stations
* 🤖 Integration with robotic waste-collection systems

## 👨‍💻 Project Team

**Project:** Trash Detection and Segregation in Water

**Developed by:**
Erukulla Satwik

## 📄 License

This project is developed for educational and research purposes.
