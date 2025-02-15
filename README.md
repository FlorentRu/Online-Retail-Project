# Online Retail Project

# Online Retail Data Analysis and Predictive Modeling

This project demonstrates end-to-end data analysis and predictive modeling on a **Retail.xlsx** dataset. We focus on:

- **Data Cleaning**: Removing duplicates, handling returns with negative quantities, filtering missing customer IDs, etc.
- **Exploratory Data Analysis (EDA)**: Identifying top-selling products, revenue by country, and seasonal sales trends.
- **Regression Modeling**: Predicting invoice totals based on aggregated invoice-level features.
- **Explainable AI with SHAP**: Interpreting model predictions for transparent insights.

---

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Dataset](#dataset)  
3. [Features & Target](#features--target)  
4. [Project Structure](#project-structure)  
5. [Installation & Requirements](#installation--requirements)  
6. [Usage](#usage)  
7. [Results & Findings](#results--findings)  
8. [Next Steps](#next-steps)  
---

## Project Overview

- **Goal**: Provide a comprehensive workflow for cleaning, exploring, and modeling *Retail.xlsx*.  
- **Techniques**:  
  - **Pandas** for data wrangling  
  - **Scikit-learn** for modeling  
  - **Matplotlib/Seaborn** for data visualization  
  - **SHAP** for model explainability  
- **Business Value**: Helps retailers understand key revenue drivers, optimize product strategies, and tailor marketing efforts.

---

## Dataset

**File**: `Retail.xlsx`  
**Source**: Transactions from a UK-based online retailer (circa 2010–2011).  
**Key Columns**:
- **InvoiceNo**: Unique transaction ID.  
- **StockCode**: Product code.  
- **Description**: Product description.  
- **Quantity**: Number of items purchased.  
- **InvoiceDate**: Timestamp of purchase.  
- **UnitPrice**: Cost per unit in GBP.  
- **CustomerID**: Unique customer identifier (when available).  
- **Country**: Customer’s country of purchase.

> **Note**: The dataset may include negative/zero quantities due to returns or canceled orders.

---

## Features & Target

After cleaning, the data is **aggregated at the invoice level**:

1. **total_quantity**: Sum of `Quantity` per invoice  
2. **distinct_items**: Number of unique `StockCode`s per invoice  
3. **avg_unit_price**: Average `UnitPrice`  
4. **Month**, **Year**: Extracted from `InvoiceDate`  
5. **Country**: One-hot encoded  

**Target**:  
- **invoice_total** = Sum of `TotalPrice` (`Quantity * UnitPrice`) for each invoice

---

## Project Structure

A possible folder layout:

. ├── notebooks/ │ ├── 01_data_cleaning_and_eda.ipynb │ ├── 02_modeling.ipynb │ └── 03_shap_explainability.ipynb ├── data/ │ └── Retail.xlsx ├── src/ │ ├── data_preprocessing.py │ ├── modeling.py │ └── shap_analysis.py ├── results/ │ ├── shap_plots/ │ └── model_outputs/ ├── README.md └── requirements.txt

