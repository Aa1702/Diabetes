# 🩺 Diabetes Prediction Using XGBoost

![Diabetes Prediction Banner](path/to/diabetesimage.png)

A machine learning project that predicts the likelihood of diabetes in patients using clinical diagnostic data. This project applies **XGBoost**, handles **class imbalance with SMOTE**, and performs **GridSearchCV hyperparameter tuning** to achieve high predictive accuracy.

---

## 📌 Project Overview
Diabetes is a chronic medical condition that requires early detection for effective management. This project builds a robust supervised learning pipeline using the **Pima Indians Diabetes Dataset**.

**Key highlights of the workflow:**
* **Data Integrity:** Handling medically invalid zeros as missing values.
* **Balancing:** Using Synthetic Minority Oversampling Technique (SMOTE) to fix class skew.
* **Optimization:** Exhaustive search over 1,728 hyperparameter combinations.
* **Validation:** 5-Fold Cross-Validation to ensure model reliability.

---

## 📊 Dataset Description
* **Source:** National Institute of Diabetes and Digestive and Kidney Diseases
* **Target Variable (`Outcome`):** `0` (No Diabetes), `1` (Diabetes)
* **Size:** 768 Records

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

---

## ⚙️ The Pipeline
1.  **Preprocessing:** Replaced invalid `0` values in Glucose, BP, BMI, etc., with `NaN` and imputed using the **Median**.
2.  **Oversampling:** Applied **SMOTE** to balance the classes (500 samples each).
3.  **Scaling:** Applied `StandardScaler` to normalise feature ranges.
4.  **Training:** Utilized the **XGBoost Classifier**.
5.  **Tuning:** Performed `GridSearchCV` to optimise depth, learning rate, and regularisation.

---

## 📈 Model Performance

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
---

## 🛠️ Installation & Requirements
Ensure you have Python 3.7+ installed.

Clone the repo:
```
git clone [https://github.com/yourusername/diabetes-prediction.git](https://github.com/yourusername/diabetes-prediction.git)
```
Install dependencies:
```
pip install pandas numpy scikit-learn xgboost imblearn
```
---

## 📁 Project Structure
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

## 🚀 Future Enhancements
Implementation of SHAP for model explainability.

Deployment of the model via a Streamlit web app.

Comparison with other boosting algorithms like LightGBM or CatBoost.

Simple. Honest. Solid. Built with the intention of improving discipline and understanding model optimisation in applied data science.
