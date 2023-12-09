# Scorecard Model
Project Based Virtual Internship as Data Scientist at Home Credit Indonesia

### Overview
PT Home Credit Indonesia is a technology-based financing company that has been in operation since 2013, with an extensive network of partner stores in over 200 cities across Indonesia. Home Credit continues to evolve into a trusted financial partner for millions of customers. Currently, we are designing statistical methods and machine learning techniques to generate credit score predictions. By doing so, we ensure that customers capable of making payments are not rejected when applying for loans. Loans can be granted with a principal, maturity, and repayment calendar designed to motivate customers toward success.
1. <b>Problem:</b> 8% of the total 307,511 customers are experiencing loan defaults, posing a potential risk of financial loss.
2. <b>Goals:</b> Decrease the default rate among customers to minimize the potential risk of financial loss.
3. <b>Objective:</b> Develop a classification model to generate credit score predictions for binary values (0 indicating clients without payment difficulties and 1 indicating clients with payment difficulties), and selectively approve loans based on predictions of 0.
4. <b>Business Metrics:</b> Default rate.

### About The Dataset
<img width="662" alt="Screenshot 2023-11-26 163757" src="https://github.com/Anikmaulia/Scorecard-Model_DS.HCI/assets/129976138/2cdec96a-12a4-42a6-a5e6-c8c03f021506">

This data is provided by Home Credit Indonesia, includes 7 different sources:
1. **application_{train|test}.csv:**
   - Main table for loan applications, split into Train (with TARGET) and Test (without TARGET).
   - Static data for all applications, with each row representing one loan.  
2. **bureau.csv:**
   - Records client's previous credits from other financial institutions reported to the Credit Bureau.
   - Multiple rows per loan, corresponding to the number of credits the client had before the application date.
3. **bureau_balance.csv:**
   - Monthly balances of previous credits reported to the Credit Bureau.
   - One row for each month of history for every previous credit, resulting in (#loans * #credits * #months with observable history) rows.
4. **POS_CASH_balance.csv:**
   - Monthly balance snapshots of previous POS and cash loans with Home Credit.
   - One row for each month of history for every previous credit in Home Credit related to loans in our sample.
5. **credit_card_balance.csv:**
   - Monthly balance snapshots of previous credit cards with Home Credit.
   - One row for each month of history for every previous credit in Home Credit related to loans in our sample.
6. **previous_application.csv:**
   - Records all previous applications for Home Credit loans from clients with loans in our sample.
   - One row for each previous application related to loans in our data sample.
7. **installments_payments.csv:**
   - Repayment history for previously disbursed credits in Home Credit related to loans in our sample.
   - One row for every payment made and one for each missed payment, equivalent to one payment of one installment or one installment corresponding to one payment of one previous Home Credit credit related to loans in our sample.
   
```
Not all data will be utilized in this project, as specific columns from each table have been selected based on their perceived influence on the target. The joining process is executed using PostgreSQL and is applied to both the training and test data sets.
```


