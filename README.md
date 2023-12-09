# Scorecard Model
Project Based Virtual Internship as Data Scientist at Home Credit Indonesia

## Overview
PT Home Credit Indonesia is a technology-based financing company that has been in operation since 2013, with an extensive network of partner stores in over 200 cities across Indonesia. Home Credit continues to evolve into a trusted financial partner for millions of customers. Currently, we are designing statistical methods and machine learning techniques to generate credit score predictions. By doing so, we ensure that customers capable of making payments are not rejected when applying for loans. Loans can be granted with a principal, maturity, and repayment calendar designed to motivate customers toward success.
### Problem
8% of the total 307,511 customers are experiencing loan defaults, posing a potential risk of financial loss.
### Goals 
Decrease the default rate among customers to minimize the potential risk of financial loss.
### Objective 
Develop a classification model to generate credit score predictions for binary values (0 indicating clients without payment difficulties and 1 indicating clients with payment difficulties), and selectively approve loans based on predictions of 0.
### Business Metrics
Default rate.

## About The Dataset
<img width="662" alt="Screenshot 2023-11-26 163757" src="https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/2cdec96a-12a4-42a6-a5e6-c8c03f021506">

This data is provided by Home Credit Indonesia.
   
```
Not all data will be utilized in this project, as specific columns from each table have been selected based on their perceived influence on the target. The joining process is executed using PostgreSQL and is applied to both the training and test data sets.
```

## Early Insight 
1. Default Rate by Gender and Income  
   <img width="533" alt="image" src="https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/24c7e9a4-3547-4dcd-a094-5a95740d25bd">  
   Those facing payment challenges have a significantly lower average income, highlighting the pronounced impact of income on defaults.  
   <img width="527" alt="image" src="https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/2200291c-d4b8-4f85-a5d3-624c5e00693f">  
   The data suggests that income may not have a significant impact for females, as both default and non-default customers exhibit similar average incomes.
   
   <b>Recommendation:</b> Consider income as a critical factor, especially for male customers.  
   <b>Action:</b> High income may warrant loan approval, while low income may justify rejection to reduce default risk and potential losses.
2. Default by Average Score from External Data Sources  
   ![image](https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/bfae4556-a8ee-4981-ad6c-44da7e19dd4f)
   Customers facing payment difficulties tend to have a lower average score from external data sources compared to customers without payment difficulties.

   <b>Recommendation:</b> Consider the external score as a critical factor.
   <b>Action:</b> A high score may justify loan approval, while a low score may warrant rejection to mitigate default risk and potential losses.

## Modeling
Current recommendations focus on male clients and those with lower external scores. To address wider payment challenges, a machine learning model has been developed for accurate predictions and effective recommendation tailoring. Now, let's review each model's performance.  
![image](https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/4cd64647-afca-48dd-91d5-e80c6733c926)  
The model with the best and consistently good performance is <b>Random Forest</b>. Therefore, predictions for clients with payment difficulties and without payment difficulties on the test data will be conducted using the Random Forest model.

## Feature Importance and Recommendations
![image](https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/fea4ee08-9b4c-403c-ae94-50047f9de217)  
<b> Recommendations:</b>
1. <b>Client Prioritization:</b> Target clients with robust external scores (> 0.4).
2. <b>Document Turnover Rule:</b> Enforce a streamlined 9-year document turnover policy.
3. <b>Annuity Adjustment Strategy:</b> Fine-tune annuity amounts for clients in payment challenges.
4. <b>Registration Stability:</b> Ensure a maximum 12-year registration stability.
5. <b>Credit Payment Cap:</b> Implement a 1.8-year cap for previous credit payments.

## Differences Before and After Building the Model
![image](https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/6a1d3f2b-f643-45c5-9324-fdb03a51a856)

<b>Before:</b>
- All 307,511 loan applications accepted.
- No rejections for clients without payment difficulties.
- 24,825 clients face payment difficulties (8% default rate).
- Potential loss: 12,748,407,075 IDR (Assuming 513,531 IDR loss per client).
- Adjusted potential loss (50% treated): 6,373,946,772 IDR.

<b>After:</b> 
- Only 287,353 predicted non-difficulty clients’ (TN + FP) loans accepted.
- 172 non-difficulty clients' loans rejected.
- 4,839 clients face difficulties (1.7% default rate).
- Potential loss: 2,484,976,509 IDR (Assuming 513,531 IDR loss per client).
- Adjusted potential loss (50% treated): 1,242,231,489 IDR.

```
Model significantly reduces default rate and potential losses.
```

## Prediction Results for the Target using a Random Forest Model on the Test Data
There are 121 (0.25%) clients predicted to experience payment difficulties, while the remaining 48,623 (99.75%) clients do not face payment challenges.
