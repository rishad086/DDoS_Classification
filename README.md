# 🧠 Machine Learning-Based Detection for Cyber Attacks in Internet of Medical Things (IoMT) Devices

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Dataset](https://img.shields.io/badge/Dataset-CIC--IoMT--2024-orange.svg)]()
[![ML](https://img.shields.io/badge/Machine%20Learning-Active-success)]()

---

## 📘 Overview

This project focuses on enhancing **cyber attack detection** in **Internet of Medical Things (IoMT)** devices using the **CIC-IoMT 2024 dataset**.  
It aims to optimize detection of **Denial of Service (DoS)** and **ARP Spoofing** attacks through improved preprocessing, feature engineering, and model tuning.

---

## 🎯 Objectives

- 🧩 Improve baseline model performance for IoMT attack detection.  
- ⚙️ Design optimized preprocessing and feature engineering steps.  
- 🧠 Compare multiple machine learning models for classification.  
- 📈 Validate improvements via key metrics (Accuracy, Precision, Recall, F1-score).

---

## ⚙️ Workflow

### 🧾 Paper’s Original Workflow
1. Load and preprocess the CIC-IoMT 2024 dataset.  
2. Apply basic feature selection.  
3. Train & evaluate models (Decision Tree, Random Forest, Gradient Boosting, XGBoost, RNN).  
4. Compare model performance.

### 🚀 Improvement Workflow
1. **Data Cleaning:** Dropped two features with null values.  
2. **Feature Engineering:** Added four new statistical features:
   - `IAT` → Inter-Arrival Time between packets  
   - `IAT_mean` → Average Inter-Arrival Time  
   - `len_mean_10` → Mean packet length (last 10 packets)  
   - `len_std_10` → Std. deviation of packet lengths (last 10 packets)  
3. **Feature Selection:** Ranked using Fisher Score, Mutual Information, and Random Forest importance.  
4. **Model Training:** Re-evaluated classifiers using optimized data.  
5. **Evaluation:** Compared improved vs. baseline metrics.

---

## 📊 Results Summary

| Model | Accuracy (Paper) | Accuracy (Improved) | Precision | Recall | F1-Score |
|-------|------------------|---------------------|------------|--------|-----------|
| Decision Tree | 0.87 | 0.8474 | 0.8392 | 0.9992 | 0.9123 |
| Random Forest (depth=8, split=10) | 0.84 | **0.9985** | **0.9999** | **0.9982** | **0.9990** |
| Random Forest (depth=10, split=5) | 0.83 | 0.9847 | 0.9826 | 0.9984 | 0.9904 |
| Gradient Boosting | 0.82 | 0.9934 | 0.9934 | 0.9983 | 0.9958 |
| XGBoost | 0.21 | 0.8598 | 0.8508 | 0.9985 | 0.9187 |
| RNN | 0.21 | 0.9749 | 0.9708 | 0.9984 | 0.9844 |

### 🧮 Isolation Forest (Unsupervised)

| Contamination | Paper’s Silhouette Score | Improved Silhouette Score |
|---------------|--------------------------|----------------------------|
| 0.1 | 0.01 | 0.2234 |
| 0.3 | 0.07 | 0.2918 |

---

## 💡 Key Insights

- 🌟 **Random Forest (depth=8, split=10)** achieved **99.85% accuracy** and **99.90% F1-score**, outperforming baseline by over **15%**.  
- ⚡ **RNN** and **XGBoost** models effectively captured complex attack patterns.  
- 🔍 **Isolation Forest** showed strong cluster separation improvement, enhancing anomaly detection quality.  
- 🧠 The optimized preprocessing pipeline dramatically improved generalization and reliability.

---

## 🧰 Technologies Used

| Category | Tools & Libraries |
|-----------|------------------|
| Language | Python 3.9+ |
| ML Frameworks | Scikit-learn, TensorFlow / Keras, XGBoost |
| Data Handling | pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Dataset | CIC-IoMT 2024 |

---

## 📁 Project Structure

