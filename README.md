# 📊 DSA_2040 Data Mining Project

### 🔖 Project Title: **Customer Retail Data Mining and Analysis**  
**Author:** Weldesenbet Zeray Aregay  
**Course:** DSA_2040 – Data Mining  
**Date:** March 8, 2025  

---

## 📁 Overview

This project performs **data preprocessing**, **exploratory data analysis (EDA)**, **discretization**, and advanced **data mining techniques** (such as **Association Rule Mining, Clustering**, and **Decision Tree Classification**) on two large synthetic retail datasets (`retail_data_1.csv` and `new_retail_data_2.csv`).  

The goal is to uncover meaningful **patterns**, **customer segments**, **frequent itemsets**, and **classification rules** that can support **strategic decision-making** in retail.

---

## 🧰 Tools & Technologies

- **Language:** R  
- **Key Libraries:**
  - `tidyverse`, `dplyr`, `lubridate` – Data manipulation
  - `arules`, `arulesViz` – Association Rule Mining
  - `caret`, `rpart`, `rpart.plot` – Classification
  - `ggplot2` – Data Visualization

---

## 📦 Datasets

1. **`retail_data_1.csv`**: Contains transaction-level data including product categories, amounts, and customer information.
2. **`new_retail_data_2.csv`**: Contains customer demographics, transaction history, and product interactions.

Each dataset is sampled to create **50,000-record subsets** for manageable analysis:
- `sampled_dataset_1.csv`
- `sampled_dataset_2.csv`

---

## 🔍 Project Workflow Summary

### ✅ Step 1: Data Cleaning & Preprocessing

- Converted dates into proper formats
- Filled missing values using:
  - Domain-based logic (e.g., `Total_Amount = Amount * Total_Purchases`)
  - Most frequent values (mode)
  - Group-wise imputation for customer ratings
  - ID recovery using associated attributes
- Imputed remaining missing values where applicable

### 📊 Step 2: Exploratory Data Analysis (EDA)

- Structure and summary statistics
- Missing value analysis
- Transaction frequency distribution

### 🛍️ Step 3: Association Rule Mining (ARM)

- Converted product data into transactional format
- Analyzed frequency of itemsets
- Applied:
  - **Apriori Algorithm**
  - **Eclat Algorithm**
- Visualized item frequency with bar plots
- Extracted and interpreted top 10 rules by lift

### 🔢 Step 4: Discretization

- **Equal-width binning** on `Amount` and `Total_Purchases`
- **Equal-frequency binning** on `Age`
- **Custom binning** for `transaction_hour` (e.g., Morning, Afternoon, Evening, Night)

### 🔘 Step 5: Clustering (K-Means)

- Dataset 1: Features – `Total_Purchases`, `Amount`, `Total_Amount`
- Dataset 2: Features – `total_transactions`, `total_sales`, `avg_transaction_value`
- Used **Elbow Method** to choose `k`
- Scaled features and applied K-Means
- Visualized clusters using scatter plots

### 🌳 Step 6: Decision Tree Classification

- Dataset 1 Target: `Customer_Segment`
- Dataset 2 Target: `customer_city`
- Used `rpart` to build decision trees
- Evaluated with **confusion matrix**
- Visualized tree structure using `rpart.plot`
- Observed that imbalance led to biased predictions in Dataset 1

---

## 📌 Key Findings

- Water-related products dominated frequent itemsets
- K-Means identified distinct purchasing patterns and clusters
- Discretization helped in making numerical features interpretable
- Decision Trees showed:
  - In Dataset 1: Model bias due to imbalance
  - In Dataset 2: `Total_Sales` was a strong predictor of customer city

---

## 📚 Folder Structure

├── Project_1.Rmd # Main R Markdown Project Script
├── sampled_dataset_1.csv # Sampled subset of data_1
├── sampled_dataset_2.csv # Sampled subset of data_2
├── retail_data_1.csv # Original Dataset 1
├── new_retail_data_2.csv # Original Dataset 2
└── README.md # Project summary and documentation

---

## ✅ Future Improvements

- Address class imbalance using SMOTE or other resampling methods
- Use Random Forest or XGBoost for better classification
- Perform category-specific ARM for deeper insights
- Build interactive dashboards using **Shiny** or **Power BI**

---

## 📣 Credits

Prepared as part of the **DSA_2040 Data Mining** course, this project demonstrates practical applications of machine learning, data mining, and business analytics concepts.

---

