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
├── app.py              # Flask Backend & ML Pipeline
├── index.html          # Frontend User Interface
├── emotion_model.pkl   # Serialized SVM Model
└── requirements.txt    # Project Dependencies
```

## ⚡ Quick Start

### 1. Prerequisites
Ensure you have Python 3.8+ installed.

### 2. Install Dependencies
```bash
pip install flask flask-cors numpy librosa scipy scikit-learn
```

### 3. Run the Application
1. Start the Flask server:
   ```bash
   python app.py
   ```
2. Open `index.html` in your browser.
3. Upload a `.wav` file (RAVDESS format) to view the classification and confidence score.

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