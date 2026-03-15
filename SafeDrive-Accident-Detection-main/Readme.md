# 🚦 SafeDrive – AI Accident Detection & Alert System
##### SafeDrive is an AI-powered accident detection system that monitors CCTV footage, detects accidents, captures snapshots, and instantly sends ##### alerts (with CCTV location) to nearby police and hospitals via SMS & cloud integration.

## 📸 Features
##### ✅ Detects accidents from CCTV footage (demo or live feed)
##### ✅ Saves snapshots of detected accidents
##### ✅ Uploads snapshots securely to Cloudinary
##### ✅ Sends SMS alerts with CCTV ID & location details
##### ✅ SMS includes accident snapshot link
##### ✅ Allows CCTV registration with location + contacts
##### ✅ GUI interface with video upload & snapshot viewer
 
## 🛠 Tech Stack
#### -YOLOv8 (Ultralytics) for accident detection
#### -OpenCV for video processing
#### -Cloudinary for image hosting
#### -Twilio for SMS alerts
#### -Tkinter for GUI
#### -Python 3.10+

## ⚡ Setup Instructions
### 1️. Clone Repository
``` 
git clone https://github.com/Saswata-pal/SafeDrive-Accident-Detection.git
```
```
cd SafeDrive 
```

### 2️. Install Dependencies
```
pip install -r requirements.txt
```

### 3️. Configure API Keys
#### Create a .env file or edit inside gui.py:

#### Cloudinary
```
cloudinary.config(
    cloud_name="YOUR_CLOUD_NAME",
    api_key="YOUR_API_KEY",
    api_secret="YOUR_API_SECRET"
)
```
#### Twilio
```
account_sid = "YOUR_TWILIO_SID"
auth_token = "YOUR_TWILIO_AUTH_TOKEN"
twilio_phone_number = "+1234567890"
```

### 4️. Add YOLO Model
#### Download or train your YOLO model (already included best1.pt for demo).

### 5️. Run the App
``` python gui.py ```

## 🔄 Training the Model (Optional)

#### Want to retrain the YOLOv8 model with your own dataset?

#### 1️⃣ Install YOLOv8
```pip install ultralytics==8.0.20 albumentations ```
#### 2️⃣ Organize your dataset in YOLO format:
```
dataset/
├── images/
│   ├── train/
│   └── val/
├── labels/
│   ├── train/
│   └── val/
└── data.yaml   # class names + paths
```

#### 3️⃣ Train the model
```
yolo detect train data=data.yaml model=yolov8n.pt epochs=100 imgsz=640
```
#### 4️⃣ Best weights will be saved at
runs/detect/train/weights/best.pt
#### 5️⃣ Validate / Test the trained model
yolo detect val model=runs/detect/train/weights/best.pt data=data.yaml

## <u>Note:</u> *I have already provided my trained accident detection model **best1.pt**, so you can skip this step unless you want to train your own with custom dataset.*



## 🖥 How It Works
#### *Register a CCTV with its ID, location & emergency contacts*
#### *Upload a demo CCTV video*
#### *AI scans frames → Detects accident → Captures snapshot*
#### *Snapshot uploaded to cloud → SMS alert sent instantly*
#### *SMS includes CCTV location & snapshot link*

## 🚀 Future Enhancements
#### -Real-time CCTV live feed integration
#### -Automated ambulance dispatch
#### -Dashboard for monitoring multiple CCTVs

## Demo

🎥 [https://www.linkedin.com/posts/saswata-pal7_ai-computervision-roadsafety-activity-7354749994215575552-ko9y?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAFAqCKIBeDF-RVzM4LsgbKf7jnqhgk5tdWY](#) 

## Screenshots

Coming soon...
## 🙏 Acknowledgment

This project was developed with reference to the SafeDrive Accident Detection project by **Saswata Pal**.

GitHub Reference:
https://github.com/Saswata-pal/SafeDrive-Accident-Detection

The implementation was modified for learning and development purposes.

## 🤝 Contributing
#### Feel free to fork & improve this project. Pull requests are welcome!

  
## 📝 License  
This project is licensed under the [MIT License](LICENSE).  

