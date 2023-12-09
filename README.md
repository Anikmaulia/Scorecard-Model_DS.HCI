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



