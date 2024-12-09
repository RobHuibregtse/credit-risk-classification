# Module 20 Report Template

## Overview of the Analysis

The purpose of building a machine learning model such as this is to predict, based on financial metrics of a borrower, whether or not the loan the customer has or has requested would be considered at risk of default. The information the model is based off includes: 

- loan_size: The dollar value of the  amount. Larger loans may be more suscepible to default.
- interest_rate: The interest rate of the loan. Higher rates may increase the risk of a default.
- borrower_income: The yearly income of the borrower. Higher income will generally decrease the risk of a default, as the borrower is more able to afford monthly payments with more income.
- total_debt: The total debt, in dollars, that the borrower is carrying. More debt makes the loan more financially difficult for the borrower to pay off, increasing chance of defaulting on the loan.
- debt_to_income: The ratio of the borrower's total debt divided by the borrower's yearly income. The lower this ratio, the easier it is for the borrower to make payments.
- num_of_accounts: The total number of other loan/credit accounts in the borrower's name. Borrowers with a lot of accounts have more individual monthly payments to meet and therefore are at a higher risk of default on their loan.
- derogatory_marks: Total # of derogatory marks against the borrower, usually due to missed payments on their other credit accounts/loans. Having multiple derogatory marks is an indicator that a borrower has difficulties making payments on time, and may be at higher risk of defaulting on their loan. 

When a lender approves a loan, they typically want to only approve loans for borrowers they deem a low risk of defaulting on the loan. This level of risk tolerance, though, may be different between different lenders, depending on their objectives, cash-on-hand, and other financial factors unique to the company. 

## Results

Sum              precision    recall  f1-score   support

Healthy loans (0)  1.00      0.99      1.00     15001
At-risk loans (1)  0.86      0.94      0.90       507

    accuracy                           0.99     15508
   macro avg       0.93      0.97      0.95     15508
weighted avg       0.99      0.99      0.99     15508

## Summary

Based on the classification report, the model successfully predicts healthy loans, and practically never gives a false positive/predicts a healthy loan as unhealthy. However, it may incorrectly predict some unhealthy loans as healthy, as its precision score for 1 (unhealthy) loans is 0.86 and has a lower recall and f1-score as well.

Whether or not the company decides to implement this model for predicting high-risk loans depends on market conditions and the company's current strategy and goals in using this model. If the company's goal is to onboard a large number of new borrowers by running their information against it to make a decision on whether or not to approve the loan, and the company is less concerned about downstream risk of default (perhaps they are planning to sell the debt off) then I think this model could work well. However, if the company is trying to be risk-averse with the loans they are approving, or if the model is specifically being used to find existing borrowers/loans who are a high risk, then this model would not be appropriate.