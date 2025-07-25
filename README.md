<div align="center">

# CUSTOMER LIFETIME VALUE (CLTV) ANALYSIS

### *Transforming Customer Data into Valuable Marketing Strategies*

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-blue?style=for-the-badge&logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Pandas-2.x-blue?style=for-the-badge&logo=pandas" alt="Pandas">
  <img src="https://img.shields.io/badge/Scikit--Learn-1.x-orange?style=for-the-badge&logo=scikit-learn" alt="Scikit-Learn">
    <img src="https.img.shields.io/badge/Lifetimes-0.11%2B-yellow?style=for-the-badge" alt="Lifetimes">
</p>

<p align="center">
  This project offers two distinct methodologies to calculate and predict customer lifetime value.
</p>

---

### 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Installation](#-installation)
- [Usage](#-usage)
- [Interpreting the Results](#-interpreting-the-results)

---

### 📖 Overview

This project aims to determine the **Customer Lifetime Value (CLTV)** for each customer by analyzing the data of an e-commerce company. The project includes both formula-based calculations based on historical data and probabilistic prediction models for future-looking insights. The ultimate goal is to identify the most valuable customer groups to steer marketing resources efficiently.

---

### ✨ Key Features

The core capabilities offered by this project are:

* **📊 Two Different Approaches:** It provides both CLTV calculation with definitive historical metrics (`cltv.py`) and statistical predictions for the future (`cltv_prediction.py`).

* **📈 Probabilistic Modeling:** It uses industry-standard **BG/NBD** and **Gamma-Gamma** models to predict future customer behavior.

* **📉 Customer Segmentation:** It segments customers into groups like `A`, `B`, `C`, and `D` based on their CLTV scores, enabling the creation of targeted marketing strategies for valuable, potential, or at-risk customers.

* **⚙️ Functional Code Structure:** All analysis and prediction processes are encapsulated within reusable functions like `create_cltv_c()` and `create_cltv_p()` for ease of use.

---

### 🚀 Installation

Follow the steps below to run the project on your local machine.

#### Prerequisites
* Python 3.8+
* Pip Package Manager

#### Steps

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/CRM_ANALITICS-main.git](https://github.com/your-username/CRM_ANALITICS-main.git)
    ```

2.  **Navigate to the project directory:**
    ```sh
    cd CRM_ANALITICS-main
    ```

3.  **Install the required libraries:**
    ```sh
    pip install pandas numpy scikit-learn matplotlib seaborn lifetimes openpyxl
    ```

---

### 💻 Usage

The project is run via two main scripts. Each script applies its respective analysis method and saves the results as a `.csv` file.

1.  **For Heuristic CLTV Calculation:**
    *This script performs the formula-based CLTV calculation.*
    ```sh
    python cltv.py
    ```

2.  **For Probabilistic CLTV Prediction:**
    *This script makes future predictions using the BG/NBD and Gamma-Gamma models.*
    ```sh
    python cltv_prediction.py
    ```

---

### 🧠 Interpreting the Results

The output of both scripts divides customers into 4 segments based on their CLTV scores. These segments help shape your marketing strategies:

* **Segment A (Champions):** Your most valuable customers. Reward them and provide exclusive offers.
* **Segment B (Loyal Customers):** Regular shoppers. Ideal for cross-selling and upselling opportunities.
* **Segment C (Potential Customers):** A group that needs personalized campaigns to be won back or retained.
* **Segment D (At-Risk / Lost):** Low-value or long-inactive customers. Engage with low-cost campaigns.
