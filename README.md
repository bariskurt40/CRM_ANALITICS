CRM Analytics: Customer Lifetime Value (CLTV)
Overview
This project provides a comprehensive analysis of Customer Lifetime Value (CLTV) using two distinct methodologies on the "Online Retail II" dataset from the UCI Machine Learning Repository. The primary goal is to calculate and predict CLTV to enable effective customer segmentation and guide targeted marketing strategies.

The project contains two main Python scripts:

cltv.py: Calculates CLTV using a heuristic, formula-based approach.

cltv_prediction.py: Predicts CLTV using probabilistic models (BG/NBD and Gamma-Gamma).

The dataset contains transactional data for a UK-based online retail company between 01/12/2009 and 09/12/2011.

Project Scripts
cltv.py: Heuristic CLTV Calculation
This script calculates CLTV based on aggregated customer transaction data from the 2009-2010 period. It follows a step-by-step formulaic approach to determine customer value.

Key Steps:

Data Preparation: Cleans the data by removing returns, handling missing values, and filtering for positive quantities.

Metric Calculation: Computes metrics such as Average Order Value, Purchase Frequency, Repeat Rate, and Churn Rate.

CLTV Formula: A fixed profit margin of 10% is applied to calculate the final CLTV using the formula:

Customer Value = Average Order Value * Purchase Frequency

CLTV = (Customer Value / Churn Rate) x Profit Margin

Segmentation: Customers are segmented into four quartiles (A, B, C, D) based on their calculated CLTV scores.

Output: The final dataframe with CLTV scores and segments is saved to cltc_c.csv.

cltv_prediction.py: Probabilistic CLTV Prediction
This script uses a more advanced probabilistic approach to predict CLTV for a 3-month future period, using data from 2010-2011. It leverages the lifetimes library to model customer purchasing behavior.

Key Models & Steps:

Data Preparation:

Cleans the data by removing returns, handling outliers, and filtering for positive quantity and price values.

Prepares a lifetime data structure with recency, T, frequency, and monetary values for each customer.

BG/NBD Model:

The Beta-Geometric/Negative Binomial Distribution (BG/NBD) model is trained to predict the expected number of future transactions for each customer.

Gamma-Gamma Model:

The Gamma-Gamma model is trained to predict the expected average profit per transaction for each customer.

CLTV Prediction:

The BG/NBD and Gamma-Gamma models are combined to calculate the CLTV for each customer over a specified time horizon.

Segmentation: As in the other script, customers are segmented into four quartiles based on their predicted CLTV.

Output: The final dataframe with predicted CLTV and segments is saved to cltv_prediction.csv.

Requirements
To run this project, you will need Python and the following libraries:

pandas

scikit-learn

lifetimes

matplotlib

Usage
You can run each script from your terminal or preferred IDE.

To run the heuristic calculation:

Bash

python cltv.py
This will generate the cltc_c.csv file in your directory.

To run the probabilistic prediction:

Bash

python cltv_prediction.py
This will generate the cltv_prediction.csv file and display a plot_period_transactions graph to evaluate the BG/NBD model's performance.
