# 🩺 Diabetes Prediction Using XGBoost

![Diabetes Prediction Banner](diabetesimage.png)

> **Machine Learning | XGBoost & Clinical Data Science**
> *Leveraging advanced boosting and SMOTE oversampling to improve early-stage chronic disease detection.*

## 📌 1. Background and Overview
Diabetes is a chronic medical condition that requires early detection for effective long-term management. This project builds a high-performance supervised learning pipeline designed to predict the likelihood of diabetes in patients with **83% accuracy**.

The primary challenge of this dataset was its **class imbalance** and the presence of **medically invalid data** (zeros in blood pressure/glucose). This project demonstrates a robust solution using **SMOTE** for balancing and **GridSearchCV** for optimising 1,728 hyperparameter combinations to ensure the model is both precise and reliable.

---

## 📊 2. Data Structure & Initial Checks
The analysis utilises the **Pima Indians Diabetes Dataset** (768 records), featuring critical diagnostic measurements:
* **Target Variable (`Outcome`)**: Binary classification (`0`: No Diabetes, `1`: Diabetes).
* **Key Features**: Glucose levels, Blood Pressure, BMI, Insulin, and Diabetes Pedigree Function (Hereditary Risk).

### 🔍 Feature Information
| Feature | Description |
| :--- | :--- |
| **Pregnancies** | Number of times pregnant |
| **Glucose** | Plasma glucose concentration |
| **BloodPressure** | Diastolic blood pressure (mm Hg) |
| **SkinThickness** | Triceps skin fold thickness (mm) |
| **Insulin** | 2-hour serum insulin (mu U/ml) |
| **BMI** | Body mass index (kg/m²) |
| **DPF** | Diabetes Pedigree Function (hereditary risk) |
| **Age** | Age in years |

**Data Engineering Strategy:**
* **Integrity Check**: Identified that `0` values in Glucose, Blood Pressure, and BMI were medically impossible. 
* **Imputation**: Replaced zeros with `NaN` and imputed values using the **Median** to maintain data distribution integrity.
* **Feature Scaling**: Applied `StandardScaler` to ensure the gradient-based XGBoost model treats all clinical features with equal weight.

---

## 🚀 3. Executive Summary
The transition from a baseline model to an optimised XGBoost pipeline resulted in significant performance gains:
* **Accuracy Boost**: Improved overall accuracy from **81% to 83%** through exhaustive hyperparameter tuning.
* **Sensitivity (Recall)**: Achieved a **Recall of 0.86** for positive cases, which is critical in healthcare settings to minimize "False Negatives" (missed diagnoses).
* **Class Balancing**: Successfully handled the 65/35 class skew using **SMOTE**, creating a balanced training environment of 500 samples per class.

---

## 🔍 4. Insights Deep Dive

### 📈 Model Performance Breakdown
* **Metric**: Precision vs. Recall (Class 1).
* **Story**: In medical diagnostics, missing a patient with diabetes is more dangerous than a false alarm. By tuning the model for high **Recall (0.86)**, we ensure the majority of at-risk patients are correctly identified for further clinical screening.

### Baseline vs. Tuned Results
| Model | Accuracy | Class 1 Precision | Class 1 Recall |
| :--- | :--- | :--- | :--- |
| **Baseline XGB** | 81% | 0.80 | 0.83 |
| **Tuned XGB** | **83%** | **0.81** | **0.86** |

## Best Hyperparameters Found:
```text
n_estimators: 100 | max_depth: 3 | learning_rate: 0.2
subsample: 0.8 | colsample_bytree: 1.0 | gamma: 0
```

### ⚙️ Hyperparameter Optimisation
* **Process**: Utilized **GridSearchCV** with 5-Fold Cross-Validation.
* **Result**: Determined that a lower `max_depth` (3) combined with a moderate `learning_rate` (0.2) prevented the model from overfitting to the oversampled minority class.

---

## ✅ 5. Recommendations & Clinical Value
* **Screening Prioritisation**: Use this model as a "first-pass" screening tool to flag high-risk patients for expensive, formal diagnostic testing (e.g., HbA1c tests).
* **Hereditary Focus**: The **Diabetes Pedigree Function** proved to be a high-impact feature; clinical intake should prioritise gathering detailed family medical history.
* **Real-time Monitoring**: The lightweight nature of the **XGBoost** model makes it ideal for deployment in mobile health apps or clinic-side tablets.

---

## 🛠️ 6. Tools & Technologies
* **Python & Scikit-Learn**: Core pipeline construction and scaling.
* **XGBoost**: Advanced gradient boosting for high-accuracy classification.
* **Imbalanced-Learn (SMOTE)**: Resolving class skew to prevent model bias.
* **GridSearchCV**: Systematic model tuning for peak performance.

---

## 🛠️ 7. Installation & Requirements
Ensure you have Python 3.7+ installed.

Clone the repo:
```
git clone [https://github.com/yourusername/diabetes-prediction.git](https://github.com/Aa1702/diabetes-prediction.git)
```
Install dependencies:
```
pip install pandas numpy scikit-learn xgboost imblearn
```
---

## 8. 📁 Project Structure
Plaintext
```
Diabetes-Prediction-XGBoost/
│
├── diabetes.csv              # Dataset
├── diabetes_prediction.py    # Main implementation script
├── README.md                 # Project documentation
└── requirements.txt          # List of dependencies
```
---

## ⚠️ 9. Caveats and Assumptions
* **Demographic Focus**: The dataset is specifically focused on women of Pima Indian heritage; results may vary when applied to broader, more diverse populations.
* **Diagnostic Limitations**: This model is a predictive tool, not a diagnostic replacement; all "Positive" flags should be verified by a licensed medical professional.

---
