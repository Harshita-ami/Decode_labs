# Decode_labs
A summary of the concepts i learned and applied in my internship at decode labs
# Data Science Project 1: Advanced EDA & Feature Engineering

## 📌 Overview
This project is part of my Data Science Internship at **DecodeLabs** (Batch 2026).
The goal is to take a raw, messy dataset and transform it into a clean,
machine-learning-ready dataset using core data preprocessing techniques.

## 🎯 Objective
- Handle missing values using statistical imputation
- Detect and neutralize outliers using the IQR method
- Engineer new predictive features from existing data

## 📊 Dataset
This project uses the **Titanic dataset**, a classic beginner-friendly dataset
containing passenger details (age, fare, family info, survival status, etc.)
with naturally occurring missing values — ideal for practicing data cleaning.

## 🛠️ Steps Performed

### 1. Exploratory Data Analysis (EDA)
- Inspected dataset shape, structure, and data types
- Identified missing values and their percentage per column

### 2. Handling Missing Values
Applied a decision-based approach depending on how much data was missing:
- **< 5% missing** → dropped the affected rows
- **5–20% missing** → filled using the **median** (robust to outliers)
- **> 20% missing** → dropped the column (too sparse to reliably impute)

### 3. Outlier Detection & Treatment
- Used the **Interquartile Range (IQR)** method to identify outliers in the `fare` column
- Instead of deleting outlier rows, values were **capped** at the lower/upper
  bounds using `numpy.clip()` to preserve dataset size

### 4. Feature Engineering
Created 3 new features to add predictive value:
- `family_size` — total family members aboard (siblings/spouses + parents/children + self)
- `is_alone` — binary flag indicating if the passenger was traveling alone
- `age_group` — categorized passengers into Child / Teen / Adult / Senior buckets

## 📈 Results
- All missing values were resolved (0 remaining nulls)
- Outliers in `fare` were successfully capped, reducing distribution skew
- Dataset is now clean and ready for machine learning modeling

## 🧰 Tools & Libraries
- Python
- Pandas
- NumPy
- Seaborn / Matplotlib
- Scikit-learn (KNNImputer)

## 📁 Files
- `Project_1_EDA_Feature_Engineering.ipynb` — main notebook with all code and outputs

## 🙋 Author
[Your Name]
Data Science Intern @ DecodeLabs, Batch 2026
