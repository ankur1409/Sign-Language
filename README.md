# Sign Language Recognition

A real-time sign language recognition system leveraging deep learning and computer vision. It interprets hand gestures with high accuracy and delivers quick responses for a smooth user experience.

## Key Features

- **High Accuracy** – Over 90% accuracy using a custom-trained CNN model
- **Fast Response** – Flask-based REST API with response times under 200ms
- **Interactive Frontend** – React-based UI for real-time gesture recognition

---

## Prerequisites

- [Python 3.11](https://www.python.org/downloads/release/python-3110/)
- [Node.js & npm](https://nodejs.org/)
- A webcam connected to your machine

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ankur1409/Sign-Language.git
cd Sign-Language
```

---

### 2. Backend Setup

```bash
cd backend

# Create a virtual environment using Python 3.11
py -3.11 -m venv venv

# Activate the virtual environment
# On Git Bash / macOS / Linux:
source ./venv/Scripts/activate
# On Windows (Command Prompt / PowerShell):
.\venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

#### Run the Backend Server

```bash
# Make sure the venv is activated, then:
python server.py

# OR without activating:
./venv/Scripts/python server.py
```

The Flask server will start at: **http://127.0.0.1:8080**

---

### 3. Frontend Setup

```bash
cd frontend

# Install dependencies
npm install

# Start the development server
npm run dev
```

The React app will start at: **http://localhost:5173**

---

## Running Both Together

Open **two separate terminals**:

| Terminal | Command |
|----------|---------|
| Terminal 1 (Backend) | `cd backend && ./venv/Scripts/python server.py` |
| Terminal 2 (Frontend) | `cd frontend && npm run dev` |

Then open your browser at **http://localhost:5173** and allow webcam access.

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/video_feed` | Live MJPEG video stream with predictions |
| `GET` | `/get_prediction` | Returns the latest predicted sign as JSON |

---

## Project Structure

```
Sign-Language/
├── backend/
│   ├── server.py          # Flask API server
│   ├── predictions.py     # Prediction logic using the trained model
│   ├── model_CNN.py       # CNN model definition
│   ├── collect.py         # Data collection script
│   ├── model_json         # Saved model architecture (JSON)
│   ├── model_json.weights.h5  # Trained model weights
│   └── requirements.txt   # Python dependencies
└── frontend/
    ├── src/               # React source files
    └── package.json       # Node dependencies
```
