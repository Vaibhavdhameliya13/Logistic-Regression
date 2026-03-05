# Bank Marketing Campaign Prediction using Logistic Regression

This project implements a **machine learning pipeline** to predict whether a customer will subscribe to a bank term deposit using **Logistic Regression**.

The model is built using the **Bank Marketing Dataset** and includes data preprocessing, exploratory data analysis, multicollinearity detection using VIF, model training, and performance evaluation.

---

## Problem Statement

Banks run marketing campaigns to promote financial products such as term deposits.  
The goal of this project is to build a model that predicts **whether a customer will subscribe to a term deposit** based on their demographic and financial information.

Accurate prediction helps banks:

- Target customers more effectively  
- Reduce marketing costs  
- Improve campaign success rates  

---

## Dataset

The dataset used is the **Bank Marketing Dataset** from the UCI Machine Learning Repository.

It contains information collected during **direct marketing campaigns of a Portuguese banking institution**.

### Target Variable

| Variable | Description |
|---------|-------------|
| y | Whether the client subscribed to a term deposit (Yes/No) |

### Example Features

| Feature | Description |
|-------|-------------|
| age | Age of the client |
| job | Type of job |
| marital | Marital status |
| education | Education level |
| balance | Average yearly account balance |
| housing | Housing loan status |
| loan | Personal loan status |
| campaign | Number of contacts during campaign |

---

## Project Workflow

### 1. Data Preprocessing

- Removed duplicate records
- Checked missing values
- Encoded categorical variables using **Label Encoding**

---

### 2. Exploratory Data Analysis (EDA)

Exploratory analysis was performed to understand the dataset structure and relationships between variables.

Analysis included:

- Distribution plots
- Correlation matrix
- Feature analysis

---

### 3. Outlier Detection

Outliers were detected using the **Interquartile Range (IQR) method**.

This helps reduce the influence of extreme values and improves model stability.

---

### 4. Multicollinearity Detection

Multicollinearity between features was evaluated using **Variance Inflation Factor (VIF)**.

VIF formula:

VIF = 1 / (1 - R²)

Where R² is the coefficient of determination when a predictor is regressed on all other predictors.

### VIF Interpretation

| VIF Value | Interpretation |
|----------|---------------|
| 1 | No correlation |
| 1 - 5 | Moderate correlation |
| >5 | High correlation |
| >10 | Severe multicollinearity |

Features with very high VIF values were analyzed to reduce redundancy while avoiding unnecessary information loss.

---

### 5. Train-Test Split

The dataset was divided into training and testing sets:

- 80% training data
- 20% testing data

Stratified sampling was used to maintain class distribution.

---

### 6. Model Training

A **Logistic Regression model** was trained to predict the probability of customer subscription.

Logistic regression models probability using the **logit function**:

log(p / (1 - p)) = β0 + β1X1 + β2X2 + ... + βnXn

Where:

- p = probability of subscription
- X = predictor variables
- β = model coefficients

---

## Model Evaluation

### Accuracy

Accuracy: **0.893**



### Classification Report

| Metric | Class 0 | Class 1 |
|------|------|------|
| Precision | 0.90 | 0.68 |
| Recall | 0.99 | 0.17 |
| F1 Score | 0.94 | 0.27 |

---

## Result Interpretation

The model achieved an overall **accuracy of approximately 89%**, which is typical for this dataset.

However, the dataset is **imbalanced**:

- Majority class (No subscription): ~88%
- Minority class (Subscription): ~12%

Because of this imbalance:

- The model predicts **non-subscribers very well**
- Detection of **subscribing customers is relatively low**

This is reflected in the **low recall for class 1**.

---

## Possible Improvements

Future improvements could include:

### Class Weighting

Using balanced class weights:


---

## Key Takeaways

- Logistic regression provides a strong baseline model for classification problems.
- Handling class imbalance is crucial for improving minority class prediction.
- Multicollinearity analysis using VIF helps improve model stability and interpretability.
- Proper data preprocessing significantly impacts model performance.

---

## Author

**Vaibhavbhai Nareshbhai Dhameliya**
