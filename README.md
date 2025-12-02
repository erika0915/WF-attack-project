# WF-attack-project
**25-2 EWHA ML Course Project**

## 1. Overview

This repository implements Machine Learning–based Website Fingerprinting (WF) attacks under three scenarios:

- Closed-World Scenario
- Open-World Scenario : Binary Classification
- Open-World Scenario : Multiclass Classification  

The pipeline covers:  

1. Loading raw monitored/unmonitored traffic from `.pkl`  
2. Preprocessing into structured feature datasets (`.csv`)  
3. Training and evaluating ML models (Random Forest) for each scenario  

---

## 2. Repository Structure
```
wf-attack-project/
│
├── README.md
├── requirements.txt
│
├── data/
│ ├── raw/ # raw pkl files (not included)
│ └── preprocessed/ # generated feature CSVs
│
└── src/
├── preprocessing/
│ └── preprocess.py
│
└── training/
├── 1_rf_closed_world.py
├── 2_rf_open_world_binary.py
└── 3_rf_open_world_multiclass.py
```

---

## 3. Installation

Install all dependencies with:
```pip install -r requirements.txt```  

The project uses:
```
pandas==2.2.2
numpy==2.0.2
scikit-learn==1.6.1
matplotlib==3.10.0
seaborn==0.13.2
tqdm>=4.0
optuna==4.6.0
```

---

## 4. Data Preparation
### 4.1 Raw data
Place raw .pkl files in:
```
data/raw/
    mon_standard.pkl
    unmon_standard10.pkl
```
*These files are excluded due to size and policy restrictions.*  

### 4.2 Preprocessing
Run :
```python src/preprocessing/preprocess.py```

Outputs :
```
data/preprocessed/
    monitored_features_1.csv
    unmonitored_features_1.csv
    monitored_features_2.csv
    unmonitored_features_2.csv
    monitored_features_4.csv
    unmonitored_features_4.csv
```

---

## 5. Training & Evaluation
Each training script handles both training and evaluation.

* Closed-World Scenario : ```python src/training/1_rf_closed_world.py```
* Open-World Binary Scenario : ```python src/training/2_rf_open_world_binary.py```
* Open-World Multiclass Scenario : ```python src/training/open_world_multiclass.py```

Each script outputs:
- Accuracy
- Precision / Recall / F1
- Confusion matrix
- Printed logs and metrics

---

## 6. Contributors
Team Lead 김원영 |
Feature : 김경연 윤소진 |
Model :  김현서 최수희
