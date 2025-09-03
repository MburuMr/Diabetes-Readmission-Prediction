# Diabetes-Readmission-Prediction
This project focuses on developing a machine learning model designed to predict the likelihood of hospital re-admission within 30 days for diabetic patients. Reducing preventable re-admissions is crucial for enhancing patient health outcomes and lowering healthcare expenses. Utilizing structured medical data alongside feature importance analysis, the model delivers precise predictions as well as valuable insights for informed decision-making.

## Problem Statement
Hospital re-admissions contribute significantly to healthcare costs and are frequently preventable. This project creates a predictive tool that identifies patients at high risk of re-admission at the time of discharge, allowing healthcare providers to take proactive measures. The model incorporates a wide range of features, including patient demographics, prior hospitalizations, medications, diagnoses, and additional relevant data.

## Overview of the Dataset
The dataset utilized in this project is obtained from https://archive.ics.uci.edu/ml/datasets/Diabetes+130-US+hospitals+for+years+1999-2008# and comprises more than 100,000 hospital encounter records for diabetic patients across 130 hospitals in the United States.

Key details include:
- 50 features encompassing both categorical and numerical data
- Target variable: readmitted, indicating whether a patient was readmitted within 30 days, after 30 days, or not readmitted at all

### 1. Data Cleaning
- Excluded columns with excessive missing values or low relevance, such as weight, payer_code, and medical_specialty
- Filtered out records with invalid or ambiguous data, including unknown gender entries and patients who expired
- Merged and standardized categorical levels based on the dataset’s provided mappings to ensure consistency

### 2. Exploratory Data Analysis (EDA)
- Analyzed feature distributions, examined class imbalance, and explored correlations among variables
- Studied the associations between patient demographics and the likelihood of re-admission

### 3. Feature Engineering
- Engineered new features including:
 - `total_visits` (total number of hospital visits)
 - `is_chronic_patient` (indicator for chronic condition status)
 - `num_medication_changes` (count of medication adjustments)
 
- Applied appropriate encoding for ordinal and categorical variables
- Standardized numerical features to ensure consistent scaling
- Utilized one-hot encoding for nominal categorical variables where applicable

### 4. Modeling & Evaluation
- Established Logistic Regression as a baseline model
- Trained more advanced classifiers including Decision Tree, Random Forest, and XGBoost
- Addressed class imbalance by applying random oversampling techniques
- Evaluated model performance using multiple metrics:
 - Accuracy
 - Recall
 - F1-score
 - ROC-AUC
 - classification report

### 5. Feature Importance Analysis
- Leveraged model-native feature importance metrics (e.g., `.feature_importances_`, `coef_`) to assess predictor influence
- Identified key factors contributing to patient readmission risk
- Visualized feature importance to enhance interpretability of global model behavior
- Translated insights into actionable strategies to inform healthcare operational decisions


## Key Insights
- Features such as `num_medications`, `time_in_hospital`, and `age` emerged as strong predictors of readmission
- Higher readmission risk was associated with patients undergoing more procedures and presenting multiple chronic conditions
- Specific discharge dispositions and gender-related trends were also found to be statistically significant

## Business Value
This model can be integrated into hospital EHR systems to:
- Proactively flag high-risk patients prior to discharge
- Inform and optimize individualized care plans and follow-up strategies
- Reduce healthcare costs associated with avoidable re-admissions
- Enhance patient satisfaction and overall clinical outcomes
