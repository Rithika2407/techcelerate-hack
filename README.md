# techcelerate-hack
# AI-Powered Predictive System

## Overview
This project is an **AI-powered predictive system** that utilizes **LSTM (Long Short-Term Memory) neural networks** to analyze and predict time-series data. The system includes an **interactive API (FastAPI)** and a **user-friendly Gradio interface** for seamless data processing, model training, and predictions.
It is designed to monitor machine health in factories and provide early maintenance alerts, helping to reduce downtime and improve operational efficiency.

## Features
- **CSV File Upload:** Users can upload datasets via FastAPI or Gradio.
- **Data Preprocessing:** The system normalizes and processes time-series data.
- **LSTM Model Training:** A sequential LSTM network learns from historical data.
- **Prediction API:** Users can input numerical values for feature-based predictions.
- **Chatbot (Future Scope):** A Falcon-7B-based chatbot can provide explanations.
- **Image-Based Predictions (Planned):** The system may integrate CNNs to analyze images alongside numerical data for enhanced forecasting.

## Tech Stack
- **FastAPI** - Backend API
- **Gradio** - Frontend UI for user interaction
- **TensorFlow/Keras** - LSTM Model
- **Pandas & NumPy** - Data processing
- **Scikit-Learn** - Data normalization
- **Ray** - Parallel computing
- **Uvicorn** - Server deployment

---

## LSTM Architecture
The **LSTM model** is designed to predict future values based on **time-series data**. It follows a multi-layered architecture for optimal learning.

### **Data Processing**
- **Normalization:** The dataset is scaled using `MinMaxScaler()`.
- **Sequence Creation:** The model looks at the last **50 timesteps** to predict the next value.

### **Model Architecture**
1. **LSTM Layer 1**: 50 units, `return_sequences=True` (passes sequences to the next layer).
2. **Dropout Layer (0.2)**: Prevents overfitting.
3. **LSTM Layer 2**: 25 units, `return_sequences=False` (final processing layer).
4. **Dropout Layer (0.2)**: Further regularization.
5. **Dense Output Layer**: Single neuron for final prediction.
6. **Loss Function**: `Mean Squared Error (MSE)` for regression accuracy.
7. **Optimizer**: `Adam` for efficient gradient updates.

### **Model Diagram**
![image](https://github.com/user-attachments/assets/e66f12a4-8f55-4f00-8b18-d79fd3249142)

---

## Installation
1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/ai-predictive-system.git
   cd ai-predictive-system
   ```
2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```
3. **Run Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

---



## Usage Guide
### **Uploading Data**
- Use the Gradio UI or FastAPI endpoint `/upload/` to upload a CSV file.
- The system automatically processes the file and extracts numerical columns.
![image](https://github.com/user-attachments/assets/2c272a0f-d91d-4a37-a75b-2804fa52c231)

### **Training the Model**
- Use the Gradio "Train Model" button or FastAPI endpoint `/train/`.
- The model trains on sequences and saves the trained weights.
![image](https://github.com/user-attachments/assets/579e54aa-a615-4e84-a9d5-22c7d71774dc)

### **Making Predictions**
- Users can enter numerical values in the UI or use FastAPI endpoint `/predict/`.
- The system will output a predicted value based on past trends.
![image](https://github.com/user-attachments/assets/9287e0ee-017c-420a-a346-34a8678ac8f5)

---

## Future Enhancements
### **1. AI Chatbot (Falcon-7B Integration)**
- The chatbot will provide insights and explanations on predictions.
- Users can ask why a certain prediction was made.

### **2. Image-Based Predictions**
- Future updates may include CNNs to analyze sensor data, equipment images, or other visual indicators.
- This can help in predicting faults or irregularities using both images and numerical data.

### **3. Model Improvement**
- Adding attention mechanisms for better sequence learning.
- Implementing **Bayesian Optimization** to tune hyperparameters.
- Using larger datasets and real-world cases for fine-tuning.

---

## Contribution Guidelines
- Fork the repository.
- Create a new branch (`feature-branch-name`).
- Submit a pull request with a detailed description.

---

## License
This project is licensed under the MIT License.

---



