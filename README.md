# Predicting Remaining Useful Life and Anomaly Detection for NASA Turbofan Engines

## Overview

This project is an AI-powered predictive maintenance system developed using the NASA C-MAPSS FD001 turbofan engine dataset. The system combines Machine Learning, Deep Learning, anomaly detection, and Local Large Language Model (LLM) integration to analyze engine degradation behavior and estimate Remaining Useful Life (RUL).

The project aims to simulate an intelligent aircraft engine monitoring system capable of:

* Predicting engine degradation
* Estimating Remaining Useful Life (RUL)
* Detecting abnormal engine behavior
* Providing AI-assisted conversational analysis through a chatbot interface

In addition to predictive analytics, the project also integrates a local AI chatbot powered by Ollama and Qwen 2.5 for interactive engine analysis and context-aware conversations.

---

## Project Objectives

The primary objectives of this project are:

* Predict the Remaining Useful Life (RUL) of turbofan engines
* Detect anomalies from multivariate sensor data
* Analyze degradation trends over operational cycles
* Compare Machine Learning and Deep Learning approaches
* Build an AI-assisted predictive maintenance system
* Integrate a conversational AI interface for intelligent analysis

---

## Dataset

The project uses the NASA C-MAPSS FD001 dataset.

Dataset characteristics:

* 100 training engines
* 100 testing engines
* 21 sensor measurements
* Multivariate time-series data
* Single operating condition
* Single fault mode

Dataset files:

```bash id="hhc5yn"
train_FD001.txt
test_FD001.txt
RUL_FD001.txt
```

Each engine record contains:

* Engine ID
* Operational cycle
* Operational settings
* Sensor measurements

The dataset simulates engine degradation from healthy conditions until failure.

---

## System Features

### Remaining Useful Life Prediction

The system predicts the number of operational cycles remaining before engine failure occurs.

Implemented techniques include:

* Time-series prediction
* Sequential degradation modeling
* Sliding window sequence generation
* Sensor-based health estimation

---

### Anomaly Detection

The project analyzes engine sensor behavior to identify abnormal operating conditions.

Functions include:

* Sensor anomaly analysis
* Engine degradation monitoring
* Threshold-based anomaly detection
* Reconstruction-based abnormality analysis

The anomaly detection module helps identify potential failures before complete engine breakdown.

---

### AI Chatbot System

The project includes an AI-powered chatbot integrated with a Local Large Language Model (LLM) using Ollama.

The chatbot is designed for:

* Predictive maintenance interaction
* Engine health explanation
* Context-aware AI conversations
* Anomaly interpretation assistance

The chatbot feature is currently under development and serves as an experimental AI assistant within the system.

Current capabilities include:

* Local LLM inference
* Conversational memory
* Session-based interaction
* Context management
* Interactive web communication

---

## Machine Learning Models

Traditional Machine Learning algorithms are used for baseline comparison and predictive analysis.

Machine Learning models include:

* Linear Regression
* Random Forest (best)
* XGBoost

These models help evaluate predictive performance and compare results with Deep Learning approaches.

---

## Deep Learning Models

Deep Learning architectures are used for sequential degradation learning and time-series prediction.

### GRU (Gated Recurrent Unit)

GRU networks are used to learn temporal degradation patterns from engine sensor sequences.

Advantages:

* Faster training
* Lower computational complexity
* Strong sequential learning capability

### LSTM (Long Short-Term Memory)

LSTM models capture long-term dependencies in multivariate time-series data.

### Autoencoder

Autoencoder-based models used for anomaly detection through reconstruction error analysis.

---

## Data Preprocessing

The preprocessing pipeline includes:

* Sensor normalization
* Feature scaling
* Sliding window generation
* Sequence creation
* RUL labeling
* Noise reduction
* Data cleaning

Preprocessing improves:

* Model stability
* Training efficiency
* Prediction accuracy

---

## Local LLM Integration

The chatbot system integrates a local Large Language Model through Ollama.

The system uses:

* Ollama
* Qwen 2.5 3B
* Local API communication
* Context-aware response generation

Advantages of local deployment:

* Offline AI interaction
* No external API dependency
* Faster response time
* Improved privacy and control

---

## Chatbot Architecture

The chatbot backend is divided into multiple service layers.

### chat_routes.py

Handles frontend and backend API communication.

### chat_service.py

Processes user requests and chatbot responses.

### context_builder.py

Builds contextual prompts for the LLM.

### llm_service.py

Communicates directly with Ollama.

### memory_service.py

Stores conversation memory and message history.

### session_context_service.py

Maintains user session context.

### engine_state_store.py

Stores engine monitoring information and analysis states.

---

## Frontend Interface

The project provides a web-based interface for:

* AI chatbot interaction
* Engine analysis visualization
* Dynamic response rendering
* User interaction

Frontend technologies:

* HTML
* CSS
* JavaScript

Frontend files:

```bash id="dtxb8j"
chatbox.css
chatbox.js
home.html
detail.html
```

---

## Project Structure

```bash id="p9q1x0"
PROJECT2_LENGOCKHANH/
│
├── app/
│   ├── routes/
│   │   └── chat_routes.py
│   │
│   ├── services/
│   │   ├── chat_service.py
│   │   ├── context_builder.py
│   │   ├── engine_state_store.py
│   │   ├── llm_service.py
│   │   ├── memory_service.py
│   │   └── session_context_service.py
│   │
│   ├── static/
│   │   ├── image/
│   │   ├── upload/
│   │   ├── chatbox.css
│   │   └── chatbox.js
│   │
│   ├── templates/
│   │   ├── home.html
│   │   └── detail.html
│   │
│   └── app.py
│
├── data/
│   ├── train_FD001.txt
│   ├── test_FD001.txt
│   └── RUL_FD001.txt
│
├── data_csv/
├── model/
├── notebook/
│   ├── notebook.ipynb
│   └── notebook2.ipynb
│
├── report/
├── .env
├── .gitignore
└── README.md
```

---

## Technologies Used

### Artificial Intelligence

* Machine Learning
* Deep Learning
* TensorFlow
* Keras
* Scikit-learn
* Ollama
* Qwen 2.5 3B

### Backend

* Python
* Flask
* REST API

### Frontend

* HTML
* CSS
* JavaScript

### Data Science

* NumPy
* Pandas
* Matplotlib
* Seaborn

---

## Installation

### Clone the repository

```bash id="nxmbp8"
git clone https://github.com/khanhdeptra1212/Predicted-RUL-and-detect-anomaly-FD001-Nasa_Turbofan_engines-.git
```

---

## Install dependencies

```bash id="qov4b9"
pip install -r requirements.txt
```

---

## Install Ollama

Download and install Ollama from:

https://ollama.com

---

## Run the Local LLM

Run the Qwen model locally using:

```bash id="f8i3wx"
ollama run qwen2.5:3b
```

The Ollama server must remain active before starting the application.

---

## Run the Application

Start the Flask application using:

```bash id="fw0cvv"
python -m app.app
```

After launching the application, users can:

* Interact with the AI chatbot
* Analyze engine degradation
* Predict Remaining Useful Life
* Detect anomalies from sensor data

---

## Jupyter Notebooks

The notebook directory contains:

* Data preprocessing workflows
* Machine Learning experiments
* Deep Learning model training
* Visualization analysis
* Performance evaluation

Notebook files:

```bash id="5y4zvw"
notebook.ipynb
notebook2.ipynb
```

---

## Evaluation Metrics

The project evaluates model performance using:

* RMSE
* MAE
* R² Score
* Reconstruction Error
* Loss Curves

These metrics are used to measure:

* Prediction accuracy
* Model stability
* Anomaly detection effectiveness

---

## Applications

This project can be applied to:

* Predictive maintenance systems
* Aircraft engine monitoring
* Industrial IoT systems
* Smart manufacturing
* PHM (Prognostics and Health Management)

---

## Future Improvements

Potential future improvements include:

* Transformer-based architectures
* Attention mechanisms
* Real-time monitoring dashboards
* Retrieval-Augmented Generation (RAG)
* Explainable AI (XAI)
* Multi-condition FD002–FD004 support
* Cloud deployment
* Improved chatbot intelligence

---

## Author

Khanh

GitHub:
https://github.com/LeNgocKhanh-AI

Project Repository:
https://github.com/LeNgocKhanh-AI/Predicted-RUL-and-detect-anomaly-FD001-Nasa_Turbofan_engines-
