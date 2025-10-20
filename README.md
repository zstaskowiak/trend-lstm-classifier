# 📈 Trend Classification Model (LSTM-based)

**Author:** Zuzanna Staśkowiak  
**Part of the project:** *Predicting Online Trends for the Gastronomy Sector: A Machine Learning Approach*   

---

## 📖 Overview

This repository contains the code for the **Trend Classification Model**, one of two main machine learning models developed as part of a research project on forecasting online trends in the gastronomy sector.

The classifier complements the **LSTM Forecaster** by categorizing predicted search trends into three classes:
- 🟩 **Trend**
- 🟨 **Micro-trend**
- ⬛ **No trend**

The classifier takes predicted time series data (from the LSTM forecaster) and outputs a label representing the expected trend behavior.

The notebook demonstrates:
1. Data preprocessing and normalization  
2. Dimensionality reduction and balancing (SMOTE)  
3. Building and training a **Bidirectional LSTM classifier**  
4. Model evaluation (accuracy, confusion matrix)  
5. Comparison and integration with the **LSTM Forecaster** module  

---
### 🔹 Data Source
- The dataset used for this project is available on Kaggle:  
[**Classified Trends Data**](https://www.kaggle.com/input/trends/classified_trends_data.xlsx)
- Data comes from **Google Trends** — relative popularity (0–100) of keywords related to food and drinks.
- Preprocessed and normalized using `MinMaxScaler`.



### 🔹 Model Architecture
- **Bidirectional LSTM** with 10 units.
- Followed by:
  - Batch normalization
  - Dropout layer (0.3)
  - Dense layer (3 units, softmax activation)
- Trained using the **Adam optimizer** (learning rate = 0.0005)  
  with **Sparse Categorical Crossentropy loss**.


### 🔹 Training Details
- Dataset balanced using **SMOTE** (Synthetic Minority Oversampling Technique).
- 80/20 train-test split.
- Early stopping applied (patience = 10).

  
## ⚙️ Technologies & Libraries

- TensorFlow / Keras  
- NumPy & Pandas  
- scikit-learn  
- imbalanced-learn (SMOTE)  
- Matplotlib  

---

### 🧪 Model Performance

To ensure reliable evaluation, 5-Fold Cross-Validation was applied.

- **Cross-Validation Accuracies (per fold):** ranged from ~72% to 94%, with an average around **80%**
- **Final Test Accuracy:** **94.44%** on the last fold's test set


