# Customer Segmentation Using K-Means Clustering

## Project Overview
This project performs **customer segmentation using K-Means clustering** to identify different groups of customers based on their purchasing behavior.

The goal is to analyze transaction data and group customers into:

- **Low Value Customers**
- **Medium Value Customers**
- **High Value Customers**

These segments help businesses understand customer behavior and design **targeted marketing strategies**.

The final segmented data is also visualized using **Power BI dashboards** to provide business insights.

---

# Dataset

The dataset contains **online retail transaction data** with the following columns:

| Column | Description |
|------|-------------|
| InvoiceNo | Unique transaction number |
| StockCode | Product identifier |
| Description | Product name |
| Quantity | Number of products purchased |
| InvoiceDate | Transaction date |
| UnitPrice | Price of each product |
| CustomerID | Unique customer identifier |
| Country | Customer location |

---

# Project Workflow

## 1. Data Loading

The dataset was loaded using **Pandas**.

```python
import pandas as pd

df = pd.read_excel("cust_segmentation.xlsx")
df.head()
