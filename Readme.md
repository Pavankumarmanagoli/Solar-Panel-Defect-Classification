# ☀️ Solar Panel Defect Classification

A deep learning project that automatically detects defects on solar panels from images.  
It combines **computer vision**, **transfer learning**, and a **Streamlit web app** to deliver practical inspection support for field teams.

---

## Project Goal

Manual panel inspection is slow and inconsistent. This project builds an automated classifier to identify common panel conditions from photos and improve maintenance response time.

The complete workflow includes:
- Baseline CNN training (from scratch)
- Transfer learning with MobileNetV2 and EfficientNet
- Interactive Streamlit inference app
- Cloud deployment readiness (AWS EC2)

---
## System Architecture  

![Architecture](images/Solar_Panel_Defect_Classification_Architrcture_Diagram.png)  

---

## Tech Stack

- **Deep Learning:** TensorFlow / Keras
- **Models:** CNN, MobileNetV2, EfficientNet
- **App Framework:** Streamlit
- **Deployment :** AWS EC2
- **Core Techstack:** Computer Vision, Transfer Learning, MLOps

---

##  Repository Structure

```text
.
├── Solar_Panel_Classification.ipynb   # Model development, experiments, and training
├── app.py                             # Streamlit app for real-time prediction
├── requirements.txt                   # Python dependencies
├── trained_effnet_finetune.h5         # Trained EfficientNet model used by app
└── README.md                          # Project documentation
```

---

##  Target Classes

The classifier predicts one of the following classes:

1. Bird-drop
2. Clean
3. Dusty
4. Electrical-damage
5. Physical-damage
6. Snow-Covered

---

##  How Inference Works

1. User uploads a panel image (`jpg`, `jpeg`, `png`)
2. App resizes image to **224×224**
3. EfficientNet preprocessing is applied
4. Model outputs class probabilities
5. App shows:
   - Predicted class
   - Confidence score
   - Top-3 predictions
   - All class probabilities

---

##  Quick Start (Local)

### 1) Clone repository

```bash
git clone <your-repo-url>
cd Solar-Panel-Defect-Classification
```

### 2) Create virtual environment

```bash
python -m venv .venv
source .venv/bin/activate    # Linux/macOS
# .venv\Scripts\activate     # Windows (PowerShell)
```

### 3) Install dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

### 4) Ensure model file exists

The app expects this file at project root:

```text
trained_effnet_finetune.h5
```

### 5) Run app

```bash
streamlit run app.py
```


---

##  AWS EC2 Deployment (Outline)

1. Launch Ubuntu EC2 instance
2. Install Python, pip, and venv tools
3. Clone this repo on the instance
4. Install dependencies and place `.h5` model file
5. Run Streamlit on desired host/port
6. Configure EC2 Security Group inbound port
7. (Recommended) Use Nginx reverse proxy + process manager (systemd)
   
---

## License
This repository is licensed under the terms in `MIT LICENSE`.

---

## Demo Video  
https://drive.google.com/file/d/1_Wz3GgCDS9RxQr4QJSz_FnzhwOOvEytY/view?usp=sharing






