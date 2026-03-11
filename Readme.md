# Stock Market Prediction using Deep Learning (MLP)

## Overview
This project predicts **stock closing prices** using a **Deep Learning Multi-Layer Perceptron (MLP)** model.  
Real stock data is extracted from **Yahoo Finance** and processed to train a neural network that forecasts the next day's closing price.

---

## Workflow

1. **Data Extraction**
   - Source: Yahoo Finance (`yfinance`)
   - Example ticker: `AAPL`
   - Data period: **2 years**
   - Interval: **1 day**

2. **Data Preparation**
   Selected features:
   - Close
   - High
   - Low
   - Open
   - Volume

3. **Feature Scaling**
   - Method: `MinMaxScaler`
   - Range: **0 → 1**

4. **Dataset Split**
   - **Training Data:** 80%
   - **Testing Data:** 20%

5. **Model Architecture**

| Layer | Neurons | Activation |
|------|--------|-----------|
| Input | 64 | ReLU |
| Hidden | 32 | ReLU |
| Hidden | 16 | ReLU |
| Output | 1 | Linear |

6. **Training Configuration**

| Parameter | Value |
|-----------|------|
| Optimizer | RMSprop |
| Loss | Mean Squared Error (MSE) |
| Epochs | 50 |

---

## Model Evaluation

Metric used:
- **R² Score (Coefficient of Determination)**

Interpretation:

| R² Score | Model Performance |
|---------|------------------|
| 90% – 100% | Excellent prediction |
| 70% – 89% | Good prediction |
| 50% – 69% | Moderate prediction |
| < 50% | Poor prediction |

Example output:

```

R² Score ≈ 0.87
Prediction Accuracy ≈ 87%

````

---

## Prediction Process

1. Model predicts **scaled closing price**
2. Values are **inverse transformed** using the scaler
3. Predicted prices are compared with **actual prices**

---

## Visualization

The model plots:

- **Actual Close Price**
- **Predicted Close Price**

to visually evaluate prediction performance.

---

## Technologies Used

- Python
- TensorFlow / Keras
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- yfinance

---

## How to Run

```bash
pip install yfinance tensorflow scikit-learn pandas numpy matplotlib
````

Run the notebook to:

1. Download stock data
2. Train the neural network
3. Predict closing prices
4. Visualize predictions


