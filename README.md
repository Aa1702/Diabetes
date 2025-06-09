# Diabetes Prediction Using XGBoost

## Project Overview
This project builds a machine learning model to predict diabetes in patients using the Pima Indians Diabetes Dataset. The model uses XGBoost, a powerful gradient boosting algorithm, along with hyperparameter tuning to maximize accuracy.

## Dataset
The dataset originates from the National Institute of Diabetes and Digestive and Kidney Diseases. It contains diagnostic data for female Pima Indian patients aged 21 or older.

| Feature                | Description                                |
|------------------------|--------------------------------------------|
| Pregnancies            | Number of times pregnant                    |
| Glucose                | Plasma glucose concentration                |
| BloodPressure          | Diastolic blood pressure (mm Hg)            |
| SkinThickness          | Triceps skin fold thickness (mm)            |
| Insulin                | 2-hour serum insulin (mu U/ml)               |
| BMI                    | Body mass index (weight in kg/(height in m)^2) |
| DiabetesPedigreeFunction | Diabetes pedigree function                  |
| Age                    | Age in years                               |
| Outcome                | Target variable (0 = no diabetes, 1 = diabetes) |

## Features
- Data preprocessing and handling of missing values
- Handling class imbalance with SMOTE
- Training an XGBoost classifier
- Hyperparameter tuning using GridSearchCV
- Model evaluation with accuracy and classification report

## Installation
Make sure you have Python 3.7+ and install the dependencies:

```bash
pip install pandas numpy scikit-learn xgboost imblearn
