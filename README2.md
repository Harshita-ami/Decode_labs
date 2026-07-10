# Data Science Project 2: Supervised Learning – Fraud Detection Pipeline

## 📌 Overview
This project is part of my Data Science Internship at **DecodeLabs** (Batch 2026).
The goal is to build a classification pipeline that detects fraudulent credit
card transactions in a highly imbalanced dataset.

## 🎯 Objective
- Handle severe class imbalance using SMOTE
- Train and compare two classification models: Logistic Regression and Random Forest
- Evaluate models using Precision, Recall, and ROC-AUC instead of plain accuracy
- Avoid data leakage by applying SMOTE only on training data

## 📊 Dataset
This project uses the **Credit Card Fraud Detection dataset** (Kaggle, ULB Machine
Learning Group) containing 284,807 transactions, of which only 0.17% are fraudulent.

## 🛠️ Steps Performed

### 1. Exploratory Data Analysis (EDA)
- Checked dataset shape and structure
- Confirmed the severe class imbalance (99.83% legitimate vs 0.17% fraud)

### 2. Train/Test Split (Before Any Resampling)
- Split data into training and test sets using stratified sampling
- Ensured the same fraud ratio was preserved in both sets
- This step was done **before** any SMOTE or scaling to prevent data leakage

### 3. Handling Class Imbalance — SMOTE
- Applied **SMOTE (Synthetic Minority Over-sampling Technique)** only on the
  training data, generating synthetic fraud examples instead of duplicating
  existing ones
- Used `imblearn.pipeline.Pipeline` to ensure SMOTE was applied correctly
  inside the pipeline, never leaking into the test set

### 4. Model Building
Built two separate pipelines:
- **Pipeline A:** StandardScaler → SMOTE → Logistic Regression
- **Pipeline B:** SMOTE → Random Forest (no scaling needed for tree-based models)

### 5. Model Evaluation
Evaluated both models on the untouched test set using:
- **Confusion Matrix** (True Positives, False Positives, etc.)
- **Precision** — how many flagged transactions were truly fraud
- **Recall** — how many actual fraud cases were successfully caught
- **ROC-AUC** — overall ability to distinguish fraud from legitimate transactions

Accuracy was intentionally **not used** as the primary metric, since it gives
a misleading picture on imbalanced datasets like this one.

## 📈 Results
- Both models were compared based on Recall and ROC-AUC, prioritizing the
  ability to catch actual fraud cases
- [Add your actual numbers here once you run it, e.g.: "Random Forest achieved
  a Recall of X% and ROC-AUC of Y%, outperforming Logistic Regression's Recall
  of A% and ROC-AUC of B%."]

## 🧰 Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-Learn
- Imbalanced-learn (SMOTE, imblearn Pipeline)
- Matplotlib / Seaborn

## 📁 Files
- `Project_2_Fraud_Detection.ipynb` — main notebook with all code and outputs

## 🙋 Author
[Harshita V Kundgol]
Data Science Intern @ DecodeLabs, Batch 2026
