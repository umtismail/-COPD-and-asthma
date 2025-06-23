# COPD and Asthma Diagnosis Prediction

This project aims to predict whether a patient has Chronic Obstructive Pulmonary Disease (COPD) or asthma using demographic, lifestyle, and clinical data. It was developed as part of the **Statistical Data Mining (IST405)** course at Hacettepe University, Department of Statistics.

## 🎯 Project Objective

The goal of this project is to build a predictive model that distinguishes between COPD and asthma diagnoses based on various patient-related features. The project also focuses on effective missing value handling and exploratory correlation analysis of medical variables.

## 📊 Dataset Overview

The dataset includes **40 features** representing:

- Demographics: Age, Gender, Education Level, Occupation
- Lifestyle: Smoking status (never, former, current smoker)
- Medical history: Family illness history, hospitalization records
- Clinical data: Spirometry results like `FEV1`, `PEF`, `FEV1 %`, `PEF %`, `FEV1/FVC`
- Target variable: `Diagnosis` (1 = Asthma, 2 = COPD)

## 🧹 Data Preprocessing

The dataset contains several missing and inconsistent values. The preprocessing steps include:

- Filling smoking-related fields based on smoking status using median or zero values
- Correcting inconsistencies in family history variables (e.g., `if family history = No`, then all individual family variables = 0)
- Fixing logical mismatches (e.g., patient marked as hospitalized without any hospital stay data)
- Converting fractional years into months, standardizing diagnosis duration into `year` + `month`
- Dropping rows or columns with excessive missing data when necessary

## 📌 Feature Correlation

Key correlations were observed between clinical indicators and diagnosis:

- `Diagnosis` vs `Smoking Status`: **0.41**
- `Diagnosis` vs `FEV1`: **-0.45**
- `Diagnosis` vs `PEF %`: **-0.42**
- `Diagnosis` vs `Age`: **0.37**
- `PEF %` vs `FEV1 %`: **0.80**

These insights were used to guide modeling decisions and feature engineering.

## 🤖 Missing Value Prediction via Machine Learning

Missing values in key features (e.g., `PEF %`, `FEV1`) were predicted using machine learning models. A total of 20+ models were compared.

### Best Model:
- **Model**: Random Forest Regressor
- **R² Score**: 0.96
- **MAE**: 2.90
- **MSE**: 17.57

Other models tested:
- Gradient Boosting, AdaBoost, Linear Regression, Ridge, Lasso
- SVR, KNN, Decision Tree, CatBoost, LGBM, XGBoost, StackingRegressor

## ⚙️ Technologies Used

- **Python** (pandas, numpy, matplotlib, seaborn)
- **Scikit-learn** (modeling and preprocessing pipelines)
- **Jupyter Notebook**
- **LightGBM**, **XGBoost**, **CatBoost**

## 📈 Results

- Successfully predicted missing values with high accuracy using robust ML models
- Identified critical clinical factors related to COPD and asthma
- Demonstrated meaningful relationships between lung function indicators and patient diagnosis
- Created a clean and reliable dataset ready for advanced predictive modeling

---

