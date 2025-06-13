# SMART LOAN RECOVERY SYSTEM USING MACHINE LEARNING

## Overview
The Smart Loan Recovery System is designed to assist financial institutions in optimizing their loan recovery processes. With the increasing number of delinquent loans, particularly among borrowers who have missed multiple payments, this project aims to develop a predictive model that identifies the most effective recovery strategies based on borrower profiles, outstanding loan amounts, and past recovery outcomes.

## Problem Statement
The financial institution faces several challenges in loan recovery, including:
- Identifying borrower segments based on attributes such as loan amount, monthly income, payment history, and missed payments.
- Optimizing collection methods (e.g., legal action, settlement offers, debt collectors, phone calls) to increase recovery rates.
- Minimizing recovery costs while maximizing the amount recovered.
- Developing an early warning system to flag borrowers who are at high risk of default.

## Dataset Overview
The dataset used for this project contains historical data on borrower profiles, loan details, and repayment histories. Key attributes include:

- **Demographic Information**: Age, employment type, income level, and number of dependents.
- **Loan Details**: Loan amount, tenure, interest rate, and collateral value.
- **Repayment History**: Number of missed payments, days past due, and monthly EMI payments.
- **Collection Efforts**: Collection methods used, number of recovery attempts, and legal actions taken.
- **Loan Recovery Status**: Whether the loan was fully recovered, partially recovered, or remains outstanding.

### Sample Data
```python
import pandas as pd
df = pd.read_csv("/content/loan-recovery.csv")
print(df.head())
```

### Summary Statistics
```python
df.describe()
```

## Data Analysis
### Analyzing Data Distribution and Relationships
The analysis begins with visualizing the distribution of loan amounts and their relationship with monthly income. A positive correlation is observed, indicating that individuals with higher income levels tend to secure larger loans.

### Payment History Analysis
The analysis of payment history reveals that loans with on-time payments are mostly fully recovered, while delayed payments result in a mix of partial and full recoveries. Missed payments significantly lower the recovery rate.

### Borrower Segmentation
Using K-Means clustering, borrower segments are created based on monthly income and loan amount. The segments are named according to their financial profiles, such as "High Income, Low Default Risk" and "Moderate Income, High Loan Burden."

## Early Detection System for Loan Defaults
A classification model is built using a Random Forest Classifier to flag borrowers with high default risk. The model predicts the probability of a borrower defaulting based on key financial and behavioral features.

### Recovery Strategy Assignment
A dynamic recovery strategy is assigned based on risk scores:
1. **High Risk (score > 0.75)**: Immediate legal notices & aggressive recovery attempts.
2. **Moderate Risk (0.50 ≤ score ≤ 0.75)**: Settlement offers & repayment plans.
3. **Low Risk (score < 0.50)**: Automated reminders & monitoring.

## Conclusion
The Smart Loan Recovery System leverages borrower profiles, payment behaviors, and clustering techniques to identify high-risk borrowers early and assign targeted recovery strategies. This approach ensures cost-effective and efficient loan recovery efforts.

## Getting Started
To run this project, ensure you have the following libraries installed:
- pandas
- plotly
- scikit-learn

You can install the required libraries using pip:
```bash
pip install pandas plotly scikit-learn
```


