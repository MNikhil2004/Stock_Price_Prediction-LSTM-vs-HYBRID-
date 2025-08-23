📈 Stock Price Prediction using LSTM + XGBoost Hybrid Model

This project implements a hybrid machine learning model for stock price prediction, combining the strengths of:

LSTM (Long Short-Term Memory networks) for capturing sequential patterns

XGBoost for residual correction and boosting model accuracy

The app is built with Streamlit for interactive visualization and exploration.

🚀 Features

Download historical Apple (AAPL) stock data (from 1981 to today) via yfinance

Preprocess and scale data with MinMaxScaler

Train an LSTM model on stock closing prices and volumes

Use XGBoost to correct residual errors of the LSTM

Evaluate models with RMSE and a custom accuracy metric

Visualize predictions against actual stock prices with interactive charts

Inspect predictions for specific dates

Generate a 30-day forward forecast (weekdays only)

📂 Project Structure
├── app.py                # Main Streamlit app
├── requirements.txt      # Dependencies
├── README.md             # Project documentation

🛠 Installation

Clone the repository:

git clone https://github.com/your-username/stock-price-prediction.git
cd stock-price-prediction


Create a virtual environment (recommended):

python -m venv venv
source venv/bin/activate   # On Mac/Linux
venv\Scripts\activate      # On Windows


Install dependencies:

pip install -r requirements.txt

▶️ Usage

Run the Streamlit app:

streamlit run app.py


Open the app in your browser at http://localhost:8501

📊 Model Workflow

Data Loading

Downloads AAPL data from Yahoo Finance

Keeps only relevant columns: date, close, high, low, volume

Preprocessing

Scales features and target values

Creates datasets with a configurable look-back window (default: 50 days)

LSTM Training

Sequential model with one LSTM layer and one Dense output layer

Trains for 20 epochs with batch size = 16

Residual Learning with XGBoost

Learns residual errors between LSTM predictions and actual values

Produces hybrid predictions (LSTM + XGBoost correction)

Evaluation

Computes RMSE and accuracy for LSTM and Hybrid models

Provides visualization of actual vs predicted prices

Forecasting

Predicts the next 30 weekdays

Skips weekends

Provides both LSTM and Hybrid predictions

📈 Example Output

Evaluation Metrics

LSTM RMSE and Accuracy

Hybrid RMSE and Accuracy

Prediction Visualization


Forecasting Table

2025-08-25: 🟠 LSTM = $180.25, 🟢 Hybrid = $182.10
2025-08-26: 🟠 LSTM = $181.02, 🟢 Hybrid = $183.50
...

📦 Dependencies

Python 3.8+

Streamlit

NumPy

Pandas

Matplotlib

yfinance

scikit-learn

XGBoost

TensorFlow

Install them via:

pip install -r requirements.txt

Deploy Link : https://stock-price-prediction-lstm-vs-hybrid.streamlit.app/
