# Real_time_Motion_AI

## 📌 Overview
This project enables **real-time motion prediction** using **accelerometer and gyroscope** data from a mobile device. The data is sent to a **FastAPI backend (hosted on Render)**, processed using **downsized TinyML models (RNN, LSTM, GRU in TFLite format)**, and displayed on a **Streamlit-based web interface** alongside a **live camera feed**.

---

## 🏗️ System Architecture
```
📂 motion-prediction-deployment/
│
├── 📂 backend/                     # FastAPI backend (hosted on Render)
│   ├── main.py                     # FastAPI app with WebSockets
│   ├── models/                      # TFLite models
│   │   ├── rnn_model.tflite
│   │   ├── lstm_model.tflite
│   │   ├── gru_model.tflite
│   ├── requirements.txt             # Dependencies for backend
│   ├── Dockerfile                   # (Optional) For containerized deployment
│   ├── README.md                    # Backend documentation
│
├── 📂 frontend/                     # Streamlit frontend (hosted on Streamlit Cloud)
│   ├── app.py                       # Streamlit UI
│   ├── requirements.txt              # Dependencies for frontend
│   ├── README.md                     # Frontend documentation
│
├── 📂 mobile-web/                   # Web-based sensor streaming (users open this on their phones)
│   ├── index.html                    # Web page for collecting sensor data
│   ├── README.md                      # Documentation for hosting (GitHub Pages/Firebase)
│
├── 📂 scripts/                      # Utility scripts for debugging & testing
│   ├── test_websocket.py             # Script to test WebSocket communication
│   ├── preprocess_data.py            # Script for data formatting
│
├── 📂 docs/                         # Project documentation
│   ├── architecture_diagram.png      # System architecture overview
│   ├── setup_guide.md                # Step-by-step deployment guide
│
├── .gitignore                        # Ignore unnecessary files
├── README.md                         # Project overview
```


## 🛠️ Technologies Used
- **FastAPI** → Backend for real-time sensor data processing.
- **TensorFlow Lite (TFLite)** → Downsized RNN, LSTM, GRU models for inference.
- **Streamlit** → Frontend UI for displaying predictions + live camera feed.
- **JavaScript (Web APIs)** → Collects sensor data from mobile devices.
- **WebSockets** → Ensures low-latency real-time communication.
