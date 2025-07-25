# Customer Lifetime Value (CLTV) Prediction Project

## 1. Overview

This project aims to calculate and predict Customer Lifetime Value (CLTV) using a dataset from an e-commerce company. The project offers two fundamental approaches:

1.  **Heuristic CLTV Calculation (`cltv.py`):** This script calculates CLTV based on key metrics derived from customers' past purchasing behavior, such as Average Order Value and Purchase Frequency.
2.  **Probabilistic CLTV Prediction (`cltv_prediction.py`):** This script uses statistical models like BG/NBD (Beta Geometric/Negative Binomial Distribution) and Gamma-Gamma to predict future purchasing behavior and the estimated value customers will generate.

The primary goal of the project is to segment customers based on their value, enabling personalized marketing strategies, more efficient resource allocation, and increased customer loyalty.

## 2. Project Structure

The project consists of two main Python scripts:

* `cltv.py`: Contains all the necessary functions and steps to calculate CLTV using formulas based on historical data. This script provides a "snapshot" of value based on existing data.
* `cltv_prediction.py`: Performs future-looking CLTV prediction using machine learning and probabilistic models (BG/NBD and Gamma-Gamma). It includes steps for data preprocessing, model building, and customer segmentation.

```
CRM_ANALITICS-main/
│
├── cltv.py                # Heuristic CLTV calculation script
├── cltv_prediction.py     # CLTV prediction script with BG/NBD and Gamma-Gamma
├── datasets/
│   └── online_retail_II.xlsx # Dataset used in the project
└── README.md              # This file
```

## 3. Dataset

The project uses the **"Online Retail II"** dataset from the UCI Machine Learning Repository.

* **Source:** [https://archive.ics.uci.edu/ml/datasets/Online+Retail+II](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II)
* **Description:** This dataset contains sales data from a UK-based online retail store between 01/12/2009 and 09/12/2011.
* **Variables:** `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, `Country`.

## 4. Techniques and Models Used

Two different data science techniques are applied in this project to analyze CLTV.

### 4.1. Heuristic CLTV Calculation (`cltv.py`)

This approach is based on the sequential calculation of the following metrics:
* **Average Order Value:** `Total Price / Total Transaction`
* **Purchase Frequency:** `Total Transaction / Total Number of Customers`
* **Repeat Rate & Churn Rate:** Calculated based on the ratio of customers who have made more than one purchase.
* **Profit Margin:** Assumed to be a specific percentage of the total price (10% in the project).
* **Customer Value:** `Average Order Value * Purchase Frequency`
* **Customer Lifetime Value:** `(Customer Value / Churn Rate) * Profit Margin`

### 4.2. Probabilistic CLTV Prediction (`cltv_prediction.py`)

This advanced approach uses two core probabilistic models to understand each customer's purchasing and spending habits:

* **BG/NBD Model (Beta Geometric/Negative Binomial Distribution):**
    * **Purpose:** Models the transaction behavior of customers. It predicts the probability of a customer being "alive" and making a purchase within a given period.
    * **Output:** The **expected number of purchases** for a specific future period (e.g., 1 week, 1 month, 3 months).

* **Gamma-Gamma Model:**
    * **Purpose:** Models the monetary value of customers' transactions. It predicts how much a customer is likely to spend on each transaction.
    * **Prerequisite:** There should be no correlation between a customer's transaction frequency and their average monetary value.
    * **Output:** The **expected average profit** for each customer.

By combining these two models, the CLTV for a specific time frame (e.g., 3 months) is predicted for each customer.

## 5. Requirements

To run this project, you will need the following Python libraries:

* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn
* lifetimes

## 6. Installation

1.  Clone the project to your local machine:
    ```bash
    git clone [https://github.com/your-username/CRM_ANALITICS-main.git](https://github.com/your-username/CRM_ANALITICS-main.git)
    ```

2.  Navigate to the project directory:
    ```bash
    cd CRM_ANALITICS-main
    ```

3.  Install the required libraries using a `requirements.txt` file or individually.

    * **Installation via requirements.txt:**
        ```txt
        # requirements.txt
        pandas
        numpy
        scikit-learn
        matplotlib
        seaborn
        lifetimes
        openpyxl 
        ```
        ```bash
        pip install -r requirements.txt
        ```

    * **Individual installation:**
        ```bash
        pip install pandas numpy scikit-learn matplotlib seaborn lifetimes openpyxl
        ```

## 7. Usage

Both scripts can be run directly. Before running the scripts, ensure that the `online_retail_II.xlsx` file is located in the `datasets` folder.

### Example 1: Heuristic CLTV Calculation

The `cltv.py` script reads the dataset, calculates the CLTV metrics, and saves the results to a file named `cltc_c.csv`. The `create_cltv_c` function at the end of the script summarizes the entire process:

```python
# A snippet from cltv.py
import pandas as pd

df_ = pd.read_excel("crm_analitics/datasets/online_retail_II.xlsx", sheet_name="Year 2009-2010")
df = df_.copy()

# Create a dataframe with CLTV calculations using the function
cltv_dataframe = create_cltv_c(df, profit=0.10)
print(cltv_dataframe.head())
```

### Example 2: Probabilistic CLTV Prediction

The `cltv_prediction.py` script trains the BG/NBD and Gamma-Gamma models, predicts the 3-month CLTV, and saves the results to the `cltv_prediction.csv` file. The `create_cltv_p` function automates this process:

```python
# A snippet from cltv_prediction.py
import pandas as pd

df_ = pd.read_excel("crm_analitics/datasets/online_retail_II.xlsx", sheet_name="Year 2010-2011")
df = df_.copy()

# Make a 3-month CLTV prediction using the function
cltv_prediction_dataframe = create_cltv_p(df, month=3)
print(cltv_prediction_dataframe.head())
```

## 8. Interpreting the Results

The output of both scripts segments customers based on their CLTV scores. The `segment` column in the output CSV files divides customers into 4 groups: **A, B, C, and D**.

* **Segment A (Champions):** The most valuable customer group. These customers are loyal and provide the highest revenue.
    * **Action:** Focus on retaining these customers with reward programs, exclusive offers, and VIP services.
* **Segment B (Loyal Customers):** Valuable customers who make regular purchases.
    * **Action:** Campaigns can be designed to increase their spending through upselling and cross-selling opportunities.
* **Segment C (Potential/At-Risk):** Customers with moderate value but at risk of churning.
    * **Action:** Their loyalty can be increased with personalized discounts and re-engagement campaigns.
* **Segment D (Hibernating/Lost):** The least valuable group. They may not have made a purchase in a long time.
    * **Action:** Avoid high-cost marketing activities for this group; attempt to win them back with low-cost, general campaigns.

This segmentation helps business analysts and marketing teams to approach the right customer with the right strategy at the right time.
