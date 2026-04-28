# 📊 Customer Segmentation using RFM & K-Means Clustering

## 📌 Project Overview
This project performs customer segmentation using **RFM (Recency, Frequency, Monetary) analysis** combined with **K-Means clustering** on an e-commerce dataset.

The goal is to identify high-value customers, understand purchasing behavior, and generate actionable business insights.

---

## 📂 Dataset
- Dataset: Online Retail Dataset  ![Data](https://drive.google.com/drive/folders/1WFbydEBn44SZOopSImRq1TDZKBChhdim?usp=drive_link)
- Total Records: ~541,000 transactions  
- Features:
  - InvoiceNo
  - StockCode
  - Description
  - Quantity
  - InvoiceDate
  - UnitPrice
  - CustomerID
  - Country  

---

## ⚙️ Workflow

### 🔹 Data Preprocessing
- Converted `InvoiceDate` to datetime format  
- Removed duplicate invoices for accurate frequency calculation  
- Created new feature:
  ```python
  df["total"] = df["Quantity"] * df["UnitPrice"]
-Handled transaction anomalies (e.g., cancellations with negative values)

### 🔹 2. RFM Feature Engineering
- Recency (R): Days since last purchase
- Frequency (F): Number of unique purchases
- Monetary (M): Total spending

### 🔹 3. Feature Scaling
- Applied StandardScaler to normalize RFM values before clustering

### 🔹 4. Optimal Cluster Selection
- Used Elbow Method (SSE) to determine optimal K
- Validated using Yellowbrick KElbowVisualizer
Selected:
👉 K = 3

### 🔹 5. K-Means Clustering
- Applied KMeans clustering on scaled RFM data
- Assigned cluster labels to each customer

###  🛠️ Tech Stack
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Yellowbrick

###  📈 Key Insights
- 💎 Diamond (23 customers) generate extremely high revenue
- 🥇 Gold (3238 customers) are the core customer base
- 🥈 Silver (1111 customers) are low engagement / at-risk

### 💡 Business Recommendations
#### 🎯 Diamond Customers
- Loyalty rewards
- Exclusive offers
#### 🔁 Gold Customers
- Personalized promotions
- Upselling
#### ⚠️ Silver Customers
- Re-engagement campaigns
- Discount strategies
