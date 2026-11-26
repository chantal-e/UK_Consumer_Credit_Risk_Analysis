# UK Consumer Credit Risk Analysis and Predictive Modelling

## Project Overview

This project explores UK consumer credit trends and borrower-level credit risk indicators using Python. It combines real economic data published by the Bank of England with a synthetic borrower dataset to investigate affordability, identify potential default risk factors and develop a predictive classification model.

The project demonstrates data cleaning, exploratory data analysis, feature engineering and machine learning techniques relevant to credit risk analysis.

## Objectives

* Analyse trends in UK consumer credit lending.
* Examine changes in unsecured credit availability and default expectations.
* Investigate borrower affordability using debt-to-income and loan-to-income ratios.
* Identify factors associated with higher simulated default risk.
* Build and evaluate a logistic regression model to classify potential borrower defaults.
* Explore the trade-off between false positives and false negatives when adjusting classification thresholds.

## Data Sources

### 1. Bank of England – Money and Credit

Monthly UK consumer credit lending data, excluding the Student Loans Company.

Used to examine changes in outstanding consumer credit over time.

Source: Bank of England – Money and Credit

### 2. Bank of England – Credit Conditions Survey

The Q3 2026 Credit Conditions Survey was used to examine changes in unsecured credit availability and lender-reported default trends.

Source: Bank of England – Credit Conditions Survey, Q3 2026

### 3. Synthetic Borrower Dataset

A dataset of 5,000 fictional borrower records was generated using Python. It includes variables such as:

* Age
* Annual income
* Credit score
* Existing debt
* Loan amount and loan term
* Missed payments
* Employment status
* Monthly debt payments

Default outcomes were simulated using an assumed probability of default formula based on selected borrower risk indicators.

Important: The borrower records and default outcomes are synthetic and do not represent actual bank customers or observed defaults.

## Methodology

**1. Data Cleaning and Exploration**

* Imported and cleaned datasets using Pandas.
* Checked data types, missing values and descriptive statistics.
* Explored consumer credit trends using visualisations.
* Compared borrower characteristics across simulated default groups.

**2. Feature Engineering**

Created additional financial indicators to assess borrower affordability:

* Debt-to-Income Ratio (DTI): Existing debt relative to annual income.
* Monthly Debt-to-Income Ratio: Monthly debt repayments relative to monthly income.
* Loan-to-Income Ratio (LTI): Requested loan amount relative to annual income.

**3. Probability of Default**

Developed an assumed probability of default calculation using borrower characteristics, including credit score, missed payments, affordability and employment status.

Simulated default outcomes were generated using these probabilities.

**4. Predictive Modelling**

Developed a logistic regression classification model using Scikit-learn.

The modelling process included:

* An 80:20 training and testing split.
* Feature scaling using StandardScaler.
* Categorical variable encoding using OneHotEncoder.
* Logistic regression classification.
* Evaluation using accuracy, precision, recall, F1-score and ROC-AUC.

The simulated probability and risk score used to generate the target variable were excluded from the model’s input features to avoid direct target leakage.

**5. Classification Threshold Analysis**

Compared classification thresholds of 0.50, 0.30 and 0.20 to investigate how changes affect default identification.

This highlighted the trade-off between identifying more potential defaults and increasing false-positive classifications.

## Key Findings

**UK Consumer Credit Trends**

* Outstanding UK consumer credit increased over the period analysed.
* The September 2026 outstanding balance reached approximately £261.2 billion.
* The increase in outstanding balances highlights the importance of monitoring household borrowing and affordability.

**Borrower Affordability**

* Average debt-to-income ratio: approximately 29.24%.
* Average monthly debt-to-income ratio: approximately 20.24%.
* Average loan-to-income ratio: approximately 46.60%.

**Simulated Default Analysis**

Borrowers classified as simulated defaults had:

* Lower average credit scores.
* Higher average debt-to-income ratios.
* Higher average monthly debt-to-income ratios.

This demonstrated how affordability and creditworthiness indicators can contribute to borrower risk assessment within the simulated dataset.

## Model Performance

The logistic regression model achieved the following results at the default classification threshold of 0.50:

Metric	Result
Accuracy	87.6%
Precision	64.0%
Recall	33.1%
F1-score	43.6%
ROC-AUC	0.811

## Threshold Comparison

Threshold	Accuracy	Precision	Recall	F1-score
0.50	87.6%	64%	33.1%	43.6%
0.30	85.2%	49%	50.3%	50.0%
0.20	81.0%	40%	60.7%	48.0%

Lowering the classification threshold increased recall, meaning the model identified a greater proportion of simulated defaults. However, this also increased false positives.

The 0.30 threshold achieved the highest F1-score among the three thresholds tested, while 0.20 achieved the highest recall.

This demonstrates why classification thresholds should be considered in the context of the relative costs of missed defaults and incorrectly flagged borrowers.

## Limitations

* Borrower-level data and default outcomes are synthetic.
* The probability of default formula uses assumed coefficients rather than estimates calibrated against observed default data.
* Model performance reflects the simulated dataset and should not be interpreted as evidence of predictive performance on real borrowers.
* The classification threshold has not been optimised using real-world business costs.
* Further validation against real, representative borrower and repayment data would be required before any practical lending application.

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab
* GitHub

## Skills Demonstrated

* Credit risk analysis
* Exploratory data analysis
* Data cleaning and preparation
* Financial ratio analysis
* Feature engineering
* Probability of default modelling
* Logistic regression
* Model evaluation
* Classification threshold analysis
* Interpretation of model performance and limitations

## Project Outcome

This project provided practical experience applying statistical analysis and machine learning techniques to a credit risk problem. It strengthened my understanding of borrower affordability, probability of default, classification performance and the trade-offs involved in identifying potential credit defaults.
