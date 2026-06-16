# Telco Churn Prediction - End-to-End ML Pipeline

## Project Overview

Customer churn prediction is a critical business problem in the telecommunications industry. This project develops a reusable and production-ready Machine Learning Pipeline using Scikit-learn's Pipeline API to predict whether a customer is likely to leave the company.

---

## Objective

The objective of this project is to:

* Build an end-to-end machine learning pipeline for customer churn prediction.
* Automate data preprocessing using Scikit-learn Pipeline.
* Train and compare multiple machine learning models.
* Perform hyperparameter tuning using GridSearchCV.
* Export the final trained model pipeline for deployment and reuse.

---

## Dataset

**Dataset:** Telco Customer Churn Dataset

The dataset contains customer demographic information, subscribed services, account details, and churn status.

### Target Variable

| Variable | Description                                            |
| -------- | ------------------------------------------------------ |
| Churn    | Indicates whether a customer left the company (Yes/No) |

---

## Methodology / Approach

### 1. Data Loading

* Loaded dataset using Pandas.
* Inspected dataset structure and data types.
* Checked for missing values and duplicates.

### 2. Data Preprocessing

Performed the following preprocessing steps:

* Removed unnecessary columns (`customerID`)
* Converted `TotalCharges` to numeric format
* Handled missing values
* Separated numerical and categorical features

### 3. Pipeline Construction

Implemented preprocessing using:

* `StandardScaler` for numerical features
* `OneHotEncoder` for categorical features
* `ColumnTransformer` for combining transformations
* `Pipeline` for integrating preprocessing and model training

### 4. Model Development

The following models were trained and evaluated:

* Logistic Regression
* Random Forest Classifier

### 5. Hyperparameter Tuning

Used `GridSearchCV` to identify optimal model parameters.

#### Logistic Regression Parameters

* C
* Solver

#### Random Forest Parameters

* n_estimators
* max_depth
* min_samples_split

### 6. Model Evaluation

Models were evaluated using:

* Accuracy Score
* Precision Score
* Recall Score
* F1-Score
* ROC-AUC Score
* Classification Report
* Confusion Matrix

### 7. Model Export

The best-performing pipeline was exported using Joblib for future deployment and reuse.

```python
joblib.dump(best_model, "telco_churn_pipeline.pkl")
```

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Jupyter Notebook

---

## Key Results / Observations

* Successfully built an end-to-end machine learning pipeline.
* Automated preprocessing using Scikit-learn Pipeline API.
* Compared Logistic Regression and Random Forest models.
* Improved model performance through GridSearchCV.
* Exported a reusable production-ready pipeline using Joblib.


* Total records: **7,043 customers**
* Test set size: **1,409 customers**
* Target variable: **Churn (Yes/No)**

### Model Performance

| Model               | Accuracy | Precision | F1-Score | ROC-AUC |
| ------------------- | -------- | --------- | -------- | ------- |
| Logistic Regression | 80.48%   | 65.52%    | 60.32%   | 84.11%  |
| Random Forest       | 79.99%   | 65.65%    | 57.78%   | 83.85%  |

### Hyperparameter Tuning Results

#### Logistic Regression

* Best Parameters:

  * `C = 10`
  * `solver = liblinear`
* Best Cross-Validation ROC-AUC: **84.59%**

#### Random Forest

* Best Parameters:

  * `n_estimators = 200`
  * `max_depth = 10`
  * `min_samples_split = 5`
* Best Cross-Validation ROC-AUC: **84.37%**

### Classification Insights

#### Logistic Regression

* Churn Precision: **66%**
* Churn Recall: **56%**
* Churn F1-Score: **60%**
* Overall Accuracy: **80%**

#### Random Forest

* Churn Precision: **66%**
* Churn Recall: **52%**
* Churn F1-Score: **58%**
* Overall Accuracy: **80%**

### Best Model

* Logistic Regression achieved the best overall performance.
* Highest ROC-AUC score: **84.11%**
* Highest F1-Score: **60.32%**
* Selected as the final production model.
