# Customer Segmentation Using K-Means Clustering

## Project Overview
This project performs **Customer Segmentation using K-Means Clustering** to identify different groups of customers based on their purchasing behavior.

The goal is to analyze retail transaction data and group customers into meaningful segments that help businesses improve **marketing strategies, customer retention, and revenue growth**.

Customers are segmented into:

- Low Value Customers
- Medium Value Customers
- High Value Customers

The final results are also visualized using **Power BI dashboards** to provide business insights.

---

# Dataset

The dataset contains **online retail transaction data** with the following features:

| Column | Description |
|------|-------------|
| InvoiceNo | Unique invoice number |
| StockCode | Product identifier |
| Description | Product name |
| Quantity | Number of products purchased |
| InvoiceDate | Transaction date |
| UnitPrice | Price of each product |
| CustomerID | Unique customer identifier |
| Country | Customer location |

---

# Project Workflow

### 1️⃣ Data Loading
Retail transaction dataset was loaded using **Pandas** for analysis.

### 2️⃣ Data Understanding
Exploratory analysis was performed to understand the dataset structure.

Key checks included:
- Dataset size
- Data types
- Missing values

**Observation**
- Dataset contains **541,909 records**
- Missing values present in **CustomerID and Description**

---

### 3️⃣ Data Cleaning
Data cleaning was performed to improve data quality.

Cleaning steps:
- Removed rows with missing **CustomerID**
- Filtered invalid or inconsistent transactions

This ensures accurate **customer-level analysis**.

---

### 4️⃣ Feature Engineering
New features were created to represent customer purchasing behavior.

Key features used for clustering:

| Feature | Description |
|------|-------------|
| TotalSpend | Total amount spent by customer |
| TotalQuantity | Total number of items purchased |
| InvoiceCount | Total number of orders |

These features represent **customer purchase behavior**.

---

### 5️⃣ Feature Scaling
Feature scaling was applied using **StandardScaler** to normalize values before clustering.

This step ensures all features contribute equally to the clustering algorithm.

---

### 6️⃣ Model Building – K-Means Clustering
The **K-Means algorithm** was used to segment customers.

- Number of clusters: **3**
- Algorithm: **K-Means Clustering**
- Type: **Unsupervised Learning**

---

### 7️⃣ Customer Segment Labeling

Clusters were mapped into business-friendly labels:

- **Low Value Customers**
- **Medium Value Customers**
- **High Value Customers**

---

# Segmentation Results

| Segment | Customers |
|------|------|
| Low Value | 4093 |
| Medium Value | 228 |
| High Value | 17 |

**Key Insight**

- Majority of customers belong to the **Low Value segment**
- A very small group of customers contributes significantly to revenue.

---

# Customer Segmentation Visualization

Customer segments were visualized using a **scatter plot based on Total Spend and Total Quantity**.

This visualization clearly shows the separation between customer groups based on purchasing behavior.

---

# Power BI Dashboard

The segmented dataset was used to create an **interactive Power BI dashboard**.

### Dashboard Metrics

- Total Customers: **4338**
- Total Revenue: **8.91M**
- Total Orders: **19K**
- Average Order Value: **480.87**
- Average Orders per Customer: **4.27**

### Dashboard Insights

- Customer distribution by segment
- Revenue contribution by segment
- Spending patterns across segments

---

# Technologies Used

- Python
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Power BI

---

# Conclusion

Using **K-Means clustering**, customers were successfully segmented based on their purchasing behavior.

These insights help businesses:

- Identify high-value customers
- Improve targeted marketing strategies
- Increase customer retention
- Optimize revenue growth

