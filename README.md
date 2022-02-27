# Consumer Retention Prediction

## 1. Overview

* Forecasted the probability of a consumer choosing our stage 2 (infant) product with 87.7% accuracy.
* Collected approximately 2k records from the customer data platform and a series of consumer surveys.
* Conducted data cleansing, EDA (exploratory data analysis), feature engineering.
* Implemented ML classification models (Logistic Regression, Random Forest), showcasing the most crucial features.
> Due to NDA (Non-Disclosure Agreement), the dataset has been modified.

## 2. Code and Packages

* Python Version: 3.9

* Packages: pandas, numpy, sklearn, matplotlib, seaborn

## 3. Objectives

* Consumer insight: Stage 2 users are 12% more likely to become Stage 3 users.​

* Business goal: Understand the variables that trigger MFB members to be MJN Stage 2 formula users.


## 4. Data Sources

The samples are collected from the customer data plarform and a set of surveys, and the time period is from Q1 2020 to Q1 2021. 


## 5. Methodology

* Dependent variable: Current Stage 2 formula brand.

* Independent variables: 
** Behavioral variables: previous brand, Email OR, CTR, coupon redemption rate, enrollment type, enrollment age.
** Demographic variables: province, hospital zone, educational status, number of children.​

* Machine Learning Models: Logistic Regression, Random Forest.​

* Oversampling due to the imbalanced dataset.

* GridSearchCV to tune the hyperparameters.
