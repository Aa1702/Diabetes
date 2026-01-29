
![Diabetes Prediction Using XGBoost](path/to/diabetesimage.png)

# 🩺 Diabetes Prediction Using XGBoost

A machine learning project that predicts the likelihood of diabetes in patients using clinical diagnostic data.  
The project applies **XGBoost**, handles **class imbalance with SMOTE**, and performs **hyperparameter tuning** to achieve improved predictive performance.

---

## 📌 Project Overview

Diabetes is a chronic medical condition that requires early detection for effective management.  
This project builds a supervised machine learning pipeline to predict diabetes outcomes using the **Pima Indians Diabetes Dataset**.

The workflow includes:
- Data cleaning and preprocessing
- Missing value handling
- Class imbalance correction
- Model training and evaluation
- Hyperparameter optimisation

The final tuned model demonstrates improved accuracy and balanced performance across both classes.

---

## 📊 Dataset Description

- **Source**: National Institute of Diabetes and Digestive and Kidney Diseases  
- **Population**: Female Pima Indian patients aged 21 years or older  
- **Total Records**: 768  
- **Target Variable**: `Outcome`  
  - `0` → No Diabetes  
  - `1` → Diabetes  

### 🔍 Feature Information

| Feature | Description |
|------|------------|
| Pregnancies | Number of times pregnant |
| Glucose | Plasma glucose concentration |
| BloodPressure | Diastolic blood pressure (mm Hg) |
| SkinThickness | Triceps skin fold thickness (mm) |
| Insulin | 2-hour serum insulin (mu U/ml) |
| BMI | Body mass index (kg/m²) |
| DiabetesPedigreeFunction | Diabetes pedigree function |
| Age | Age in years |
| Outcome | Diabetes status (Target) |

---

## 🧹 Data Preprocessing

### Missing Values Handling
- Certain features contain zero values that are **medically invalid**
- These zeros were replaced with `NaN` in the following columns:
  - Glucose
  - BloodPressure
  - SkinThickness
  - Insulin
  - BMI
- Missing values were imputed using the **median**, making the approach robust to outliers

### Class Imbalance Handling
- Original class distribution:
  - Non-diabetic: 500
  - Diabetic: 268
- **SMOTE (Synthetic Minority Oversampling Technique)** was applied
- Balanced dataset after SMOTE:
  - Non-diabetic: 500
  - Diabetic: 500

---

## 🧠 Model & Techniques Used

- **Algorithm**: XGBoost Classifier  
- **Feature Scaling**: StandardScaler  
- **Imbalance Handling**: SMOTE  
- **Cross-Validation**: 5-Fold K-Fold  
- **Hyperparameter Optimization**: GridSearchCV  

---

## ⚙️ Model Training Pipeline

1. Load and explore the dataset  
2. Clean and preprocess data  
3. Apply SMOTE for class balancing  
4. Split data into training and testing sets  
5. Scale numerical features  
6. Train baseline XGBoost model  
7. Perform cross-validation  
8. Tune hyperparameters using GridSearchCV  
9. Evaluate the final tuned model  

---

## 📈 Model Performance

### Baseline XGBoost Model
- **Accuracy**: 81%
Precision | Recall | F1-score
Class 0 | 0.82 | 0.79 | 0.81
Class 1 | 0.80 | 0.83 | 0.81


### Cross-Validation
- **Mean CV Accuracy**: 77.62%

---

### 🔧 Hyperparameter Tuning Results

GridSearchCV tested **1,728 parameter combinations**.

**Best Parameters:**
```text
n_estimators: 100
max_depth: 3
learning_rate: 0.2
subsample: 0.8
colsample_bytree: 1.0
min_child_weight: 1
gamma: 0
reg_alpha: 0
reg_lambda: 1

## ✅ Final Tuned Model Performance

Accuracy: 83%
Precision | Recall | F1-score
-----------------------------
Class 0   | 0.85   | 0.80   | 0.82
Class 1   | 0.81   | 0.86   | 0.83

## 🛠️ Installation & Requirements
Make sure you have Python 3.7+ installed.
Install dependencies:

pip install pandas numpy scikit-learn xgboost imblearn


## ▶️ How to Run the Project
Place diabetes.csv in the project directory
Run the Python script or notebook
View printed evaluation metrics in the console


## 📁 Project Structure

Diabetes-Prediction-XGBoost/
│
├── diabetes.csv
├── diabetes_prediction.py
├── README.md
└── requirements.txt

## 🚀 Future Enhancements
SHAP-based model explainability
Feature importance visualisation
ROC-AUC analysis
Model deployment using Streamlit
Testing deep learning models for comparison

##🌟 Final Thoughts
This project reflects a complete, real-world machine learning workflow from raw data to a tuned predictive model.
It was built with the intention of improving discipline, understanding model optimisation, and strengthening applied data science skills.
Simple. Honest. Solid.





