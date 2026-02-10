# Customer Churn Prediction

An end-to-end machine learning project for predicting **customer churn** using structured banking data.  
The project covers the full pipeline from data analysis to model deployment readiness.

---

## 📌 Project Overview

The goal of this project is to predict whether a customer will leave the bank (`Exited = 1`) based on
demographic, financial, and behavioral features.

The main focus is:
- Robust feature engineering
- Model comparison using multiple algorithms
- ROC-AUC–based evaluation for imbalanced data
- Cross-validation and hyperparameter tuning
- Saving the final model for inference and deployment

---

## 📊 Dataset

- Rows: **165,034**
- Target: `Exited` (binary classification)
- No missing values
- Categorical features encoded
- Multiple engineered behavioral features added

---

## ⚙️ Feature Engineering

Key engineered features include:
- Balance usage indicator (`HasBalance`)
- Balance per product ratio
- Age and credit score segmentation
- Activity × product interaction score
- Tenure and salary-based ratios

Identifier columns (`id`, `CustomerId`, `Surname`) were removed to avoid noise.

---

## 🤖 Models Trained

The following models were evaluated:

- Logistic Regression  
- Decision Tree  
- Random Forest  
- Gradient Boosting  
- AdaBoost  
- LightGBM  
- XGBoost  
- CatBoost  

All models were evaluated using **ROC-AUC** as the primary metric.

---

## 🏆 Model Performance (ROC-AUC)

| Model | ROC-AUC |
|------|--------|
| CatBoost | 0.8898 |
| LightGBM | 0.8896 |
| XGBoost | 0.8893 |
| Gradient Boosting | 0.8881 |
| AdaBoost | 0.8767 |
| Random Forest | 0.8750 |
| Logistic Regression | 0.8180 |

---

## 🔁 Validation & Tuning

- **Stratified K-Fold Cross Validation**
- **RandomizedSearchCV** for hyperparameter tuning
- Class imbalance handled using class weights
- Final model trained with optimal hyperparameters

---

## 🚀 Deployment

The trained model is saved and can be used for inference via:
- Streamlit
- Hugging Face Spaces
- Any Python-based backend

To run the Streamlit app locally:
```bash
streamlit run app.py