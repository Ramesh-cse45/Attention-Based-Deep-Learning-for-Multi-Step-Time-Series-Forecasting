
# 📘 Advanced Time Series Forecasting using Transformer & LSTM

## 🚀 Project Overview

This project implements a deep learning-based time series forecasting system using **LSTM** and **Transformer (self-attention)** models.

The objective is to predict future values of a **complex multivariate time series** that includes:

* Trend
* Seasonality
* Non-linearity
* Noise

The system uses **walk-forward validation** and evaluates performance using industry-standard metrics.

---

## 🎯 Objectives

* Generate a synthetic multivariate time series dataset
* Build LSTM and Transformer models for forecasting
* Apply walk-forward validation for realistic evaluation
* Compare model performance using statistical metrics
* Visualize predictions and attention mechanisms

---

## 📊 Dataset Description

The dataset consists of:

* **3,500 timesteps**
* **3 variables**:

  * Target series
  * Exogenous feature 1 (seasonal)
  * Exogenous feature 2 (random noise)

### 🔍 Components

* Linear trend
* Daily seasonality
* Weekly seasonality
* Non-linear interactions
* Gaussian noise

---

## ⚙️ Feature Engineering

* Lookback window: **48 timesteps**
* Forecast horizon: **12 timesteps**
* Sliding window sequence generation
* Normalization using **StandardScaler**

---

## 🧠 Models Used

### 1️⃣ LSTM Model

* 1 LSTM layer (64 units)
* Dense output layer (12-step forecast)

### 2️⃣ Transformer Model

* Dense embedding layer (64 dimensions)
* Multi-head attention (4 heads, key_dim = 16)
* 2 Transformer blocks
* Positional encoding
* Global average pooling output

---

## 🏋️ Training Setup

* Optimizer: **Adam (lr = 0.001)**
* Loss function: **Mean Squared Error (MSE)**
* Epochs: **50**
* Batch size: **64**
* Early stopping + learning rate reduction

---

## 🔄 Validation Strategy

* **Walk-forward validation (rolling window)**
* Train size: **2000 timesteps**
* Step size: **12 timesteps**

✅ Prevents data leakage
✅ Mimics real-world forecasting scenarios

---

## 📏 Evaluation Metrics

* **MAE** – Mean Absolute Error
* **RMSE** – Root Mean Squared Error
* **MASE** – Mean Absolute Scaled Error

---

## 📈 Results

| Model       | MAE    | RMSE   | MASE   |
| ----------- | ------ | ------ | ------ |
| LSTM        | 0.9385 | 1.0104 | 8.5384 |
| Transformer | 0.5149 | 0.6243 | 4.5557 |

---

## 🔍 Key Findings

* Transformer outperformed LSTM across all metrics
* ~45% reduction in MAE
* Better capture of seasonality and long-term dependencies
* LSTM showed signs of underfitting

---

## 📊 Forecast Analysis

* Transformer captures seasonal spikes effectively
* LSTM produces smoother but less accurate predictions
* Transformer slightly overestimates peak values

---

## 🧩 Attention Interpretation

* Strong focus on recent timesteps
* Seasonal patterns identified via attention weights
* Long-range dependencies successfully learned

---

## ✅ Conclusion

The **Transformer model** demonstrates superior performance over LSTM in time series forecasting due to its ability to capture **long-range dependencies** using self-attention mechanisms.

However, slight overestimation of peak values suggests scope for:

* Regularization improvements
* Hyperparameter tuning

---

## 🛠️ Tools & Technologies

* Python
* TensorFlow / Keras
* NumPy
* Scikit-learn
* Matplotlib

---

## 📌 Future Work

* Add real-world datasets
* Hyperparameter optimization (Optuna / Grid Search)
* Probabilistic forecasting
* Model ensembling

---

## ⭐ If you like this project

Give it a star ⭐ and feel free to contribute!

---
