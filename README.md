# Customer Lifetime Value (CLTV) Prediction Project

## Overview
This project aims to predict Customer Lifetime Value (CLTV) using various data science techniques. The project is implemented in Python, utilizing two main scripts:
- `cltv.py`: Contains functions and calculations for CLTV.
- `cltv_prediction.py`: Focuses on building and evaluating predictive models for CLTV.

## Project Structure
- **cltv.py**: This script includes the core functions for calculating CLTV based on customer data.
- **cltv_prediction.py**: This script uses machine learning algorithms to predict CLTV. It also includes data preprocessing and model evaluation sections.

## Requirements
To run this project, you'll need the following Python libraries:
- pandas
- numpy
- scikit-learn
- matplotlib (for visualizations)
- seaborn (for visualizations)

You can install the requirements with:
```bash
pip install pandas numpy scikit-learn matplotlib seaborn
# Customer Segmentation with RFM

## Overview
This project implements customer segmentation using RFM (Recency, Frequency, Monetary) analysis. The goal is to divide customers into segments to enable targeted marketing strategies for an e-commerce company.

## Project Structure
1. **Business Problem**: Understanding the need for customer segmentation and its implications for marketing.
2. **Data Understanding**: Analyzing the dataset and its attributes.
3. **Data Preparation**: Cleaning and preparing the data for analysis.
4. **Calculating RFM Metrics**: Computing Recency, Frequency, and Monetary metrics for each customer.
5. **Calculating RFM Scores**: Assigning scores based on RFM metrics.
6. **Creating & Analyzing RFM Segments**: Defining customer segments and analyzing them.
7. **Function Implementation**: Organizing the entire process into a reusable function.

## Dataset
The dataset used for this project is from the Online Retail II dataset, which contains sales data for an online retail store based in the UK from 01/12/2009 to 09/12/2011. 

- **Source**: [Online Retail II Dataset](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II)

### Variables
- **InvoiceNo**: Unique invoice number. Starts with 'C' for canceled transactions.
- **StockCode**: Unique product code for each item.
- **Description**: Name of the product.
- **Quantity**: Number of units sold.
- **InvoiceDate**: Date and time of the invoice.
- **UnitPrice**: Price of the product in pounds.
- **CustomerID**: Unique customer identifier.
- **Country**: Country of the customer.

## Requirements
To run this project, the following Python libraries are required:
- pandas
- numpy

Install the required libraries using:
```bash
pip install pandas numpy
