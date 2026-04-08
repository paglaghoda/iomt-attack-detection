Data Science Group Activity - Grp 13

# IoMT Attack Detection — CIC IoMT 2024 (WiFi/MQTT)

## Overview
Machine learning model to classify network traffic as benign or one of 
18 cyberattack types using the CIC IoMT 2024 dataset.

## Dataset
- Source: CIC IoMT 2024 — WiFi & MQTT subset
- Train size: 7,160,831 rows | Test size: 1,614,182 rows
- Features: 45 network traffic features
- Classes: 51 labels (Benign + attack variants)

## Model
- Algorithm: Random Forest Classifier
- Parameters: 100 estimators, max_depth=20

## Results
- Accuracy: (fill in after training)
- Key metric: F1-score per class

## How to Run
1. Open `notebook.ipynb` in Google Colab
2. Upload the dataset from Kaggle: `limamateus/cic-iomt-2024-wifi-mqtt`
3. Run all cells in order