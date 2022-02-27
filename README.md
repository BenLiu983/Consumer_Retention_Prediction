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

     - Behavioral variables: previous brand, enrollment type, enrollment age, Email OR, CTR, coupon redemption rate.

     - Demographic variables: hospital zone, province, educational status, number of children.​

* Machine Learning Models: Logistic Regression, Random Forest.​

* Oversampling due to the imbalanced dataset.

* GridSearchCV to tune the hyperparameters.

## 6. Data Cleaning

* Manipulated output variable columns. (set "MJN" as 1, other brands as 0).

* Create Dummy Variables to transform categorical variables to numeric ones.

* Scaling the column to ensure they are within the same range (0 to 1).

Final Clean Data (the dataframe is transposed in order to be better displayed):

graph 1

### 7.1 Ouput variables (MJN - 1, others - 0):

graph 2

* Will upsample in the next session due to the imbalanced dataset.

### 7.2 Independent variables:

Current Brand vs Enrollment Type:

<img width="500" height="300" alt="brand_enrolltype" src="https://user-images.githubusercontent.com/64850893/150658695-9319ac0b-b0bf-4acd-8769-d35e3e1f5d5e.png">

* Based on the enrollment type distribution plot, we can see that the proportion of "0" (co-registered) is lower in the customer group that uses our brand. This fact could indicate the enrollment type is possibly crucial in forecasting the parent's current brand choice.

Current Brand vs Baby Age:

<img width="600" height="300" alt="brand_babyage" src="https://user-images.githubusercontent.com/64850893/150658790-a211bf6f-0c53-4081-8ffd-33c92f8cedc3.png">

* The above graph demonstrates a similar distribution in terms of baby age within two categories, which could mean that this feature is less critical in the predictive model.

Current Brand vs Email Open Rate:

<img width="500" height="300" alt="brand_or" src="https://user-images.githubusercontent.com/64850893/150658832-007fdd6f-f120-49b2-bb6c-0fb96e0b8b3a.png">

* Taking the average email open rate in two groups, we can observe a significant gap. This aligns with the business logic, since customers who are more engaged with our email campaign will be more likely to choose our brand.

