# Smart Grid Electric Vehicle (EV) Peak Load Demand Forecasting

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![PySpark](https://img.shields.io/badge/PySpark-3.x-red.svg)](https://spark.apache.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📌 Project Overview
With the rapid acceleration of Electric Vehicle (EV) adoption, modern smart grids face unprecedented volatility and localized demand surges. Accurately forecasting peak load demand ($kWh$) is essential for utility operators to execute real-time load balancing, optimize grid capacity, and mitigate catastrophic transformer overloads.

This project implements a spatio-temporal deep learning and big data pipeline designed to ingest, process, and forecast peak EV charging demand using continuous time-series data.

---

## 🏗️ Model Architecture

The forecasting pipeline utilizes a hybrid *1D CNN-LSTM Neural Network*:
* *1D Convolutional Layers (1D CNN):* Extract spatial-temporal localized feature patterns and high-frequency variations from time-series load dynamics.
* *Long Short-Term Memory Layers (LSTM):* Capture long-term sequential dependencies, seasonal patterns, and peak charging trends across historical time steps.
* *Dense Output Layer:* Predicts continuous demand metrics ($kWh$) over target forecast horizons.

* Raw Time-Series Data ➔ Data Ingestion & Spark ETL ➔ 1D CNN (Feature Extraction) ➔ LSTM (Temporal Dependencies) ➔ Dense Output (Peak Demand Forecast)

The forecasting pipeline utilizes a hybrid 1D CNN-LSTM Neural Network:
 1D Convolutional Layers (1D CNN): Extract spatial-temporal localized feature patterns and high-frequency variations from time-series load dynamics.
 Long Short-Term Memory Layers (LSTM): Capture long-term sequential dependencies, seasonal patterns, and peak charging trends across historical time steps.
 Dense Output Layer: Predicts continuous demand metrics (kWh) over target forecast horizons.

📊 Evaluation Metrics
The framework evaluates model performance against baseline time-series models (e.g., standard LSTM, ARIMA) using standard regression metrics:
 Root Mean Squared Error (RMSE)
 Mean Absolute Error (MAE)
 Coefficient of Determination (R² Score)
