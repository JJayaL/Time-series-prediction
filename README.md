# CO Concentration Prediction using Time-Series & Deep Learning

## Overview
This project analyzes environmental sensor data to predict **carbon monoxide (CO) concentration** using both classical time-series methods and deep learning models.

The pipeline covers:
- Data exploration and visualization  
- Feature selection and engineering  
- Outlier detection and handling  
- Clustering analysis  
- Sequence modeling (LSTM, GRU, CNN+LSTM)  
- Classical forecasting (ARIMA, SARIMA)

---

## Dataset
Time-series sensor dataset containing:

- Time (s)
- CO (ppm) *(target variable)*
- Humidity (%r.h.)
- Temperature (°C)
- Flow rate, heater voltage
- Sensor resistances (R1–R14)

---

## Pipeline

### 1. Data Exploration
- Time-series plots for key variables  
- CDF analysis  
- Correlation heatmaps  

### 2. Feature Selection
- Correlation-based filtering  
- Removal of low-impact features  

### 3. Outlier Handling
- Z-score based detection  
- Local interpolation replacement  

### 4. Feature Engineering
- Rolling statistics (mean, median, std)  
- Rate of change features  
- Clustered CO target (KMeans)  

### 5. Sequence Preparation
- Normalization (MinMaxScaler)  
- Sliding window sequences (length = 30)  
- Train/test split  

---

## Models

- LSTM (baseline)
- Bidirectional LSTM
- CNN + LSTM
- GRU
- ARIMA / SARIMA (classical methods)

---

## Results (MSE)

| Model               | MSE   |
|--------------------|------|
| LSTM               | **0.114** |
| Bidirectional LSTM | 0.148 |
| GRU                | 0.269 |
| CNN + LSTM         | 0.768 |

**Best performing model:** LSTM

---

## Key Insights
- Sensor resistances (R8–R14) strongly correlate with CO levels  
- Feature engineering significantly improves performance  
- LSTM captures temporal dependencies effectively  
- Classical models provide interpretability but lower flexibility  

---

## Setup

```bash
pip install pandas numpy matplotlib seaborn scikit-learn tensorflow statsmodels
```

---

## Usage

Run the main pipeline:

```bash
python main.py
```

Or open and execute the notebook step by step for exploration.

Ensure the dataset is located at:

```text
dataset/20160930_203718.csv
```

---

## Future Work

- Hyperparameter tuning (Grid / Bayesian optimization)  
- Transformer-based time-series models  
- Real-time CO prediction system  
- Cross-dataset generalization  
- Lightweight deployment (edge/embedded systems)  

---

## ELEC 825 Collaborative Project

A collaborative project developed as part of the **ELEC 825** course.

---

## Contributors

- Jayalekshmi Jayakumar  
- Shadi Zargari  
- Jonathan Cordaro  
- Mohammadreza Parvizimosaed  
