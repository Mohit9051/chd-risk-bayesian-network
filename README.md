# chd-risk-bayesian-network
Python implementation of IPCW-weighted Bayesian Networks with Cox survival integration for coronary heart disease risk prediction on synthetic EHR data.


# 🫀 Weighted Survival Bayesian Network for CHD Risk Prediction

This repository contains a full, reproducible Python implementation of a **Weighted Survival Bayesian Network (WSBN)** for predicting **3-year coronary heart disease (CHD) risk** using **synthetic EHR data**, reproducing the methodology of the 2024 JAHA study:

Suo X. et al. “Development and Validation of a Bayesian Network-Based Model for Predicting Coronary Heart Disease Risk From Electronic Health Records.” Journal of the American Heart Association (JAHA), 2024.

---

## 📌 Project Objective

The goal of this project was to recreate and validate the complete analytical framework proposed in the JAHA paper, including:

- Bayesian network structure learning  
- IPCW-weighted parameter estimation for censored survival data  
- Cox proportional hazards integration  
- External validation  
- Baseline model comparison  
- Model evaluation and calibration  

Due to restricted access to real EHR data, this implementation uses **synthetic data derived from the Framingham dataset** with expanded EHR-like features.

---

## 🧠 Methodology Overview

This project implements the full WSBN pipeline:

### 1. Bayesian Network Construction
- Structure learning via **Hill-Climbing (BIC score)**
- Conditional Probability Tables (CPTs) learned using **IPCW weights**

### 2. Survival Modeling
- Simulated time-to-event and censoring processes  
- **Inverse Probability of Censoring Weighting (IPCW)**  
- **Cox Proportional Hazards model** for estimating 3-year survival probability

### 3. Synthetic EHR Feature Expansion
- ~50 clinical variables including:
  - demographics  
  - vitals  
  - lab values  
  - medications  
  - comorbidities  

### 4. Baseline Models
- Logistic Regression  
- Random Forest

### 5. External Validation
- Separate synthetic cohort with shifted population distributions

### 6. Evaluation
- AUC  
- Brier Score  
- Calibration curves  
- Decision Curve Analysis (DCA)

---

## 📊 Example Results Summary

| Model | AUC (approx) | Brier Score | Notes |
|-------|--------------|-------------|-------|
| Weighted BN | 0.54 – 0.60 | ~0.03 | Learned interpretable structure; limited by synthetic data |
| Logistic Regression | 0.64 – 0.70 | ~0.031 | Stable baseline performance |
| Random Forest | 0.56 – 0.60 | ~0.033 | Slightly poorer calibration |
| Cox PH | – | – | Used to generate 3-year survival probabilities |

Note: The original JAHA study reports AUC ≈ 0.80–0.84 using large-scale real EHR data (~150,000 patients). Lower performance here is expected due to synthetic data and simplified feature realism.

---

## 🔬 Scientific Contributions

- Full reproduction of the **WSBN computational workflow**
- Integration of **probabilistic graphical models with survival analysis**
- Demonstration of **IPCW-weighted CPT estimation** in Bayesian networks
- Reproducible framework for CHD risk modeling research
- End-to-end pipeline including validation and decision analysis

---

## ⚠ Limitations

- Synthetic data used instead of real EHR  
- Simulated censoring and baseline hazards  
- Reduced feature realism compared to clinical datasets  
- External validation cohort is synthetic  

These limitations affect numerical performance but **not the methodological validity** of the framework.

---

## 🧪 Reproducibility Outputs

The repository includes:

- Learned BN structure graphs  
- Exported CPT tables  
- Model summaries  
- Evaluation plots (AUC, calibration, DCA)  
- External validation results  
- Reproducibility checklist  

---

## 🛠 Technologies Used

- Python  
- pgmpy  
- scikit-learn  
- lifelines  
- pandas  
- numpy  
- matplotlib  
- seaborn  

---

## 📖 Citation / Acknowledgment

If you use this code, please cite:

Suo X. et al., Journal of the American Heart Association, 2024.

And reference this repository as a methodological reproduction study.

---

## 🧾 Abstract-style Statement

“I successfully replicated the analytical workflow of the 2024 JAHA study ‘Development and Validation of a Bayesian Network-Based Model for Predicting Coronary Heart Disease Risk’, implementing a Weighted Survival Bayesian Network (WSBN) in Python using synthetic data derived from the Framingham dataset. The pipeline includes IPCW-weighted CPT estimation, Cox proportional hazards integration for 3-year survival prediction, EHR-level feature expansion, and simulated external validation. This repository provides a reproducible template for CHD risk prediction research using probabilistic graphical models and survival analysis.”

---
