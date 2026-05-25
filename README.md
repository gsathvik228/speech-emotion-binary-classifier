A machine learning-powered application that performs **Speech Emotion Recognition (SER)** to classify audio signals into **Negative** and **Non-Negative** categories. This project features a full end-to-end pipeline, from digital signal processing to a responsive web interface.

## 🚀 Overview
The system analyzes vocal characteristics to detect emotional states. It specifically targets "Negative" triggers (such as anger or frustration) and distinguishes them from "Non-Negative" states like neutral or positive speech. 

### **Key Technical Features:**
* **Signal Processing:** Implements a 5th-order **Butterworth Bandpass Filter** (300Hz–3500Hz) to isolate the human vocal range.
* **Feature Extraction:** Extracts 40 **MFCCs** (Mel-frequency cepstral coefficients) using a Hamming window for high-fidelity spectral analysis.
* **Classification:** Uses a **Support Vector Machine (SVM)** with a polynomial kernel for robust binary classification.
* **Modern UI:** A sleek, interactive frontend featuring glassmorphism and real-time confidence feedback.

## 🛠️ Tech Stack
* **Backend:** Python, Flask, Flask-CORS
* **Machine Learning:** Scikit-learn, NumPy
* **Audio Analysis:** Librosa, SciPy
* **Frontend:** HTML5, CSS3, JavaScript (Fetch API)

## 📂 Project Structure
```text
├── .gitignore           # Excludes dataset & model from version control
├── app.py               # Flask Backend & ML Pipeline
├── index.html           # Frontend User Interface
├── emotion_model.pkl    # Pre-trained SVM Model (included)
├── requirements.txt     # Project Dependencies
└── Audio_Speech_Actors/ # RAVDESS dataset (download separately for retraining)
    ├── Actor_01/
    ├── Actor_02/
    └── ...
```

## ⚡ Quick Start

### 1. Prerequisites
Ensure you have Python 3.8+ installed.

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the Application
The app comes with a **pre-trained model** (`emotion_model.pkl`), so you can run it immediately:
```bash
python app.py
```
Then open `index.html` in your browser and upload a `.wav` file.

## 📥 Dataset (for retraining)

This project uses the **RAVDESS** (Ryerson Audio-Visual Database of Emotional Speech and Song) dataset.

- **Download:** [https://zenodo.org/record/1188976](https://zenodo.org/record/1188976)
- Download the `Audio_Speech_Actors_01-24.zip` file (~1GB)
- Extract it into the project root so the folder structure is:
  ```
  speech-emotion-binary-classifier/
  └── Audio_Speech_Actors/
      ├── Actor_01/
      ├── Actor_02/
      ...
  ```
- The model will automatically train from this dataset on first run if `emotion_model.pkl` doesn't exist.
- To retrain after dataset is in place, hit the `/retrain` endpoint or delete `emotion_model.pkl` and restart the server.

## 🧠 Model Logic
1.  **Preprocessing:** Raw audio is filtered to remove noise and unwanted frequencies.
2.  **Framing:** A **Hamming Window** is applied to the signal to minimize spectral leakage.
3.  **Inference:** Features are fed into the trained SVM model to generate a prediction and probability score.

**Classification Breakdown:**
* **Negative:** Sadness, Anger, Fear, Disgust.
* **Non-Negative:** Neutral, Calm, Happiness, Surprise.

---

## 👥 Credits
This project was developed as a collaborative microproject focusing on Signal Processing for Machine Learning.