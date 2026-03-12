# Customer Segmentation Using K-Means Clustering
Project Overview
This project performs customer segmentation using K-Means clustering to identify different groups of customers based on their purchasing behavior.
The goal is to analyze transaction data and group customers into Low Value, Medium Value, and High Value segments using machine learning techniques. These segments help businesses understand customer behavior and design targeted marketing strategies.
The final segmented data is also visualized using Power BI dashboards to provide clear business insights.
Dataset
The dataset contains online retail transaction data with the following columns:
Column	Description
InvoiceNo	Unique transaction number
StockCode	Product identifier
Description	Product name
Quantity	Number of products purchased
InvoiceDate	Transaction date
UnitPrice	Price of each product
CustomerID	Unique customer identifier
Country	Customer location
________________________________________
Project Workflow
1. Data Loading
The dataset was loaded using Pandas for analysis.
import pandas as pd

df = pd.read_excel("cust_segmentation.xlsx")
df.head()
________________________________________
2. Data Understanding
Initial data exploration was performed to understand the dataset structure.
The following checks were performed:
•	Dataset shape
•	Data types
•	Missing values
df.shape
df.info()
df.isnull().sum()
Observations
•	Dataset contains 541,909 records
•	Missing values found in CustomerID and Description
________________________________________
3. Data Cleaning
To ensure reliable analysis, data cleaning steps were applied.
Handling Missing Values
Rows with missing CustomerID were removed because customer identification is required for segmentation.
df = df.dropna(subset=["CustomerID"])
Removing Invalid Transactions
Transactions with negative or incorrect values were removed to maintain data quality.
These cleaning steps ensured that the dataset contained only valid customer transactions.
________________________________________
4. Feature Engineering
A new feature TotalAmount was created to calculate the total purchase value.
df["TotalAmount"] = df["Quantity"] * df["UnitPrice"]
Customer-level features were then generated using aggregation.
customer_df = df.groupby("CustomerID").agg({
    "TotalAmount": "sum",
    "Quantity": "sum",
    "InvoiceNo": "nunique"
}).reset_index()
Final Features Used for Segmentation
Feature	Description
TotalSpend	Total money spent by the customer
TotalQuantity	Total number of products purchased
InvoiceCount	Total number of orders
________________________________________
5. Feature Scaling
Feature scaling was applied using StandardScaler to normalize the feature values before clustering.
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()
scaled_features = scaler.fit_transform(features)
________________________________________
6. Model Building – K-Means Clustering
K-Means clustering was applied to segment customers into 3 clusters.
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=3, random_state=42)

customer_df["Cluster"] = kmeans.fit_predict(scaled_features)
________________________________________
7. Customer Segment Labeling
Clusters were mapped into meaningful business segments.
cluster_map = {
    0: "Low Value",
    1: "High Value",
    2: "Medium Value"
}

customer_df["CustomerSegment"] = customer_df["Cluster"].map(cluster_map)
Final Segmentation Result
Segment	Customers
Low Value	4093
Medium Value	228
High Value	17
________________________________________
Customer Segmentation Visualization
The clusters were visualized using a scatter plot based on Total Spend and Total Quantity.
This visualization clearly shows the separation between low, medium, and high value customers.
________________________________________
Power BI Dashboard
The final segmented dataset was used to create an interactive Power BI dashboard to analyze customer behavior.
Dashboard metrics include:
•	Total Customers: 4338
•	Total Revenue: 8.91M
•	Total Orders: 19K
•	Average Order Value: 480.87
•	Average Orders per Customer: 4.27
The dashboard provides insights such as:
•	Customers per segment
•	Revenue contribution by segment
•	Customer spending patterns
________________________________________
Technologies Used
•	Python
•	Pandas
•	Scikit-learn
•	Matplotlib
•	Seaborn
•	Power BI
________________________________________
Conclusion
Using K-Means clustering, customers were successfully segmented based on their purchasing behavior.
These insights help businesses:
•	Identify high-value customers
•	Improve marketing strategies
•	Increase customer retention
•	Optimize business growth
