# Induction Motor Fault Diagnosis Using Current Signature Analysis

This project focuses on classifying the health status of an induction motor using time-domain current signal data. The data includes healthy and unhealthy conditions under different load levels, with various types and severities of faults. The classification tasks include both **binary classification** (healthy vs unhealthy) and **multiclass classification** (14 fault classes), using **K-Nearest Neighbors (KNN)** and **Logistic Regression**.

---

## 📁 Dataset Description

The dataset contains three-phase current data sampled at **10 kHz** (1000 samples per channel) for induction motors under various fault conditions:

- **Fault Types:**
  - **Bearing Faults (Inner-race, Outer-race)**: Fault severities of 0.7 mm, 0.9 mm, 1.1 mm, 1.3 mm, 1.5 mm, and 1.7 mm.
  - **Broken Rotor Bar Faults (BRB)**: At 100W and 300W load conditions.
- **Loads:** 100W, 200W, and 300W.
- **Total Files:** 39 time-series datasets grouped into 7 folders (by load conditions).
- **Sampling Rate:** 10,000 Hz
- **Block Size:** Each block of **1000 samples** is used as one training sample.

Each 1000-sample block is assigned a corresponding label based on the health condition and load.

---

## ⚙️ Preprocessing Steps

1. Each dataset file was segmented into blocks of 1000 samples.
2. Each segment was labeled according to:
   - **Binary Classification:** `Healthy (0)` vs `Unhealthy (1)`
   - **Multiclass Classification:** 14 distinct labels including various combinations of fault types and load conditions.
3. Processed data was saved into a CSV format for training and testing.

---

## 🧠 Implemented Models

### 1. K-Nearest Neighbors (KNN)
- Implemented for binary classification (`Healthy` vs `Unhealthy`).
- Distance metric: Euclidean.
- Hyperparameter tuning: Cross-validation for optimal `k`.

### 2. Logistic Regression
#### Binary Classification
- Distinguishes between `Healthy` and `Unhealthy` motor conditions.

#### Multiclass Classification (14 Classes)
- One-vs-Rest strategy used to classify among 14 motor condition classes.

---



