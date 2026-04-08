# Data Science Group Activity - Grp 13

| Registration No | Name                  |
|-----------------|-----------------------|
| 24BCE10412      | CHANDRAMANI           |
| 24BCE10455      | RITABRATA KARMAKAR    |
| 24BCE10843      | OMKAR SAHAY           |
| 24BCE11527      | ANSHU KUMAR           |
| 24BCY10005      | SANKALP TRIPATHI      |
| 24BCY10010      | RAGHAWENDRA TIWARI    |

## IoMT Attack Detection — CIC IoMT 2024 (WiFi/MQTT)

## Overview
A machine learning model that classifies network traffic as **benign or an attack**
using the CIC IoMT 2024 dataset (WiFi & MQTT subset). This is a binary classification
problem trained on real IoMT device traffic including 18 types of cyberattacks.

## Dataset
- **Source:** [CIC IoMT 2024 — WiFi & MQTT (Kaggle)](https://www.kaggle.com/datasets/limamateus/cic-iomt-2024-wifi-mqtt)
- **Train size:** 7,160,831 rows (20% sample used)
- **Test size:** 1,614,182 rows (20% sample used)
- **Features:** 45 network traffic features
- **Task:** Binary classification — Benign (0) vs Attack (1)

## Model
- **Algorithm:** Random Forest Classifier
- **Parameters:** 50 estimators, max_depth=15, random_state=42

## Results

### Accuracy: 99.85%

| Class   | Precision | Recall | F1-Score | Support |
|---------|-----------|--------|----------|---------|
| Benign  | 0.97      | 0.97   | 0.97     | 7,525   |
| Attack  | 1.00      | 1.00   | 1.00     | 315,311 |
| **Overall** | **1.00** | **1.00** | **1.00** | 322,836 |

### Confusion Matrix
<img width="591" height="470" alt="Confusion Matrix" src="https://github.com/user-attachments/assets/e43732b2-a115-4a86-8c6a-a0c4b8a2bfd5" />

> Out of 322,836 test samples:
> - **7,269** benign correctly identified ✅
> - **315,072** attacks correctly caught ✅
> - **256** benign incorrectly flagged as attack (false positives)
> - **239** attacks missed (false negatives)

### Top 15 Most Important Features
<img width="989" height="590" alt="Feature Importance" src="https://github.com/user-attachments/assets/81fb0ad7-a891-4e67-b3a5-dfd7c42d85f5" />

> The model relies most heavily on `rst_count`, `psh_flag_number`, and `IAT`
> (Inter-Arrival Time) — all network-level indicators of abnormal traffic patterns.

## How to Run
1. Open `notebook.ipynb` in Google Colab
2. Download dataset via Kaggle API:
```python
!kaggle datasets download -d limamateus/cic-iomt-2024-wifi-mqtt
!unzip cic-iomt-2024-wifi-mqtt.zip
```
3. Run all cells in order

## Requirements
- Python 3.x
- pandas, numpy, matplotlib, seaborn
- scikit-learn
- joblib
