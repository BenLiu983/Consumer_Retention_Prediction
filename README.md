# Consumer Retention Prediction

## 1. Overview

* Forecasted the probability of a consumer choosing our stage 2 (infant) product with 87.7% accuracy.
* Collected approximately 2k records from the customer data platform and a series of consumer surveys.
* Conducted data cleansing, EDA (exploratory data analysis), feature engineering.
* Implemented ML classification models (Logistic Regression, Random Forest), showcasing the most crucial features.
> Due to NDA (Non-Disclosure Agreement), the dataset has been modified.

<img width="921" alt="lr fea c2" src="https://user-images.githubusercontent.com/64850893/155887997-5a75e3d5-f43c-4752-b055-c1db284e5c3c.png">

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

<img width="898" alt="dataset1_2" src="https://user-images.githubusercontent.com/64850893/155887825-7c6175c5-208b-414c-b3bb-3fb6f66df6fc.png">

### 7.1 Ouput variables (MJN - 1, others - 0):

<img width="989" alt="stage 2 brand 4" src="https://user-images.githubusercontent.com/64850893/155889230-1b53cca2-0e6b-477d-b9ff-a6c5efaf9112.png">

* Will upsample in the next session due to the imbalanced dataset.

### 7.2 Input variables:

The below visualizations will follow a segment analysis (our Stage 2 product user group vs non-user group)

Previous Brand:

<img width="1115" alt="pre brand 3" src="https://user-images.githubusercontent.com/64850893/155889095-575b5a70-d3e2-4390-b735-14274bf40868.png">

* On the left-hand side, for the non-MJN Stage 2 consumers, 34.6% of them used Nestle Stage 1 as their previous brand. 
* On the right-hand side, within the MJN Stage 2 users group, 68.8% selected MJN as their previous brand.

Hospital Zone & Province:

<img width="1019" alt="hos_pro" src="https://user-images.githubusercontent.com/64850893/155888337-731406ab-a5a7-4a1a-8239-8aebdd67ac29.png">

* The left graph reads a notable lift in terms of the percentage of MJN hospital zone in the MJN Stage 2 user group, compared to the non-user group (72% vs 58%). 
* There isn't a significant difference regarding the province distribution percentage between the MJN Stage 2 user group and the non-user group, which could mean that this feature is less critical in the predictive model.

Education & Number of Children:

<img width="1019" alt="edu_numofchild" src="https://user-images.githubusercontent.com/64850893/155888499-b4356f87-ae46-41a1-b530-2ac497b07330.png">

* According to the left plot, the overall educational status is higher within the MJN user group.​
* The distribution of number of children between the user and the non-user group is similar.

Enrollment Type & Enrollment Time by Stage:

<img width="1115" alt="enroll_type_and_age2" src="https://user-images.githubusercontent.com/64850893/155889002-d5a66a9d-595c-403d-83e3-a70f7ad0893c.png">

* The proportion of "self-enrolled" consumers is greater in the user group compared to the non-user group (90% vs 79%).
* Consumers who enrolled in "Stage 0" (prenatally) take up a higher percentage in the non-user group, while those enrolled in "Stage 1" (0-6 months) account for a larger proportion in the user group. 

Email OR, CTR & Coupon Redemption Rate:

<img width="1115" alt="email_coupon2" src="https://user-images.githubusercontent.com/64850893/155889123-55cc7f3c-d2c3-4de2-8554-b9bb41b6c192.png">

* In terms of engagement for the "Prenatal" and "Newborn" emails, the OR and CTR in the user group are drastically higher.
* Similarly, regarding the "Stage 1" coupon performance, the redemption rate is substantially greater in the user group.


## 8. Modeling

### 8.1 Procedure

* Train-test-split
* Cross validation
* Oversampling
* Machine learning algorithms (Logistic Regression, Random Forest)
* GridSearchCV

### 8.2 Model performance:

<img width="1011" alt="model_sum" src="https://user-images.githubusercontent.com/64850893/155891672-6e74397d-6133-4c9e-966d-d56be9b4a38c.png">

* Considering the prediction accuracy as well as the model simplicity, Logistic Regression in Case 2 would be the optimal model, since it is more straightforward to interpret, with relevantly high prediction accuracy.

### 8.3 Confusion Matrix (Logistic Regression): 

<img width="470" alt="cm_git" src="https://user-images.githubusercontent.com/64850893/155891735-bcfcc378-3bc3-4f0b-9d32-8691ab1ed777.png">

### 8.4 Feature Importance (Logistic Regression): 

<img width="921" alt="lr fea c2" src="https://user-images.githubusercontent.com/64850893/155887997-5a75e3d5-f43c-4752-b055-c1db284e5c3c.png">

* Positive features – previous brand as MJN, negative features – previous brand as other brands.
* If the previous brand is "Abbott Specialty", it plays a positive impact on current MJN stage 2 brand choice.
* Number of children is negatively influencing the MJN stage 2 brand selection .

## 9. Conclusion

* Drive MFB members to become Stage 1 users, due to the fact that the previous brand is a primary indicator.
* Maintain/boost the quantity/quality of email campaigns, since the email performance is an essential driver.
* Conduct experimentation to market users with only 1 child, because this metric negatively impact the outcome.

## 10. Next Steps
 
* 1. Modify the output and input variables to tailor other business use cases.
* 2. More experimentation in terms of variables and models.
