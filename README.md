# Anomaly Detection Experiment Summary

This notebook documents experiments on **Anomaly Detection** using three unsupervised models on the iot dataset.

## Models Implemented
- **Isolation Forest**
- **Local Outlier Factor (LOF)**
- **One-Class SVM**

## 🛠️ Workflow Overview
1. **Data Loading & Exploration**
   - Imported dataset
   - Checked for missing values and performed basic data analysis

2. **Preprocessing**
   - Scaled features with `MinMaxScaler`
   - Prepared data for anomaly detection tasks

3. **Model Training & Prediction**
   - Trained each model separately
   - Obtained predictions: `-1` for anomaly, `1` for normal observations

4. **Performance Evaluation**
   - Used **Confusion Matrix** and **Classification Report** for each model
   - Focused on precision, recall, and F1-score for anomalies detection (`-1` class)

---

## 📊 Results Summary

| Model             | Anomaly Precision | Anomaly Recall | Anomaly F1-Score | Accuracy |
|-------------------|--------------------|----------------|-------------------|----------|
| **Isolation Forest** | 0.20 | 1.00 | 0.34 | 0.97 |
| **Local Outlier Factor (LOF)** | 0.00 | 0.00 | 0.00 | 0.99 |
| **One-Class SVM** | 0.08 | 1.00 | 0.14 | 0.90 |

---

## 📌 Observations & Insights
- **Isolation Forest** showed the best compromise between anomaly detection and overall accuracy. It captured all anomalies but with low precision (many false positives).
- **LOF** failed to detect anomalies (0 precision and recall) despite achieving high overall accuracy — likely due to extreme imbalance and model sensitivity.
- **One-Class SVM** detected all anomalies (100% recall) but with even lower precision than Isolation Forest, leading to many false positives and a drop in overall accuracy.

---

## ✅ Conclusion
- **Isolation Forest** is the recommended choice for this dataset when maximizing anomaly recall is critical.
- Model selection should balance recall and precision depending on the real-world cost of false positives vs. false negatives.

---

