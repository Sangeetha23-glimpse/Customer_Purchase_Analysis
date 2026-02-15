Customer Shopping Behavior Analysis

End-to-end Data Analytics Project | Python • MySQL • Power BI • Gamma

📌 Project Overview

This project analyzes customer shopping behavior to identify purchasing trends, customer segments, and revenue-driving factors.
It demonstrates a complete analytics workflow — from raw data to executive presentation — using industry-standard tools.

📑 Executive Presentation
A stakeholder-ready presentation was created:

🔗 View Presentation
https://gamma.app/docs/Customer-Shopping-Behavior-Analysis-xrhysoe3smgn1y9?mode=doc

🔎 Business Objective

To derive actionable insights that help businesses:

Increase revenue
Improve customer retention
Optimize product strategy
Support data-driven decision-making

🗂️ Project Workflow

Data Loading & Cleaning (Python)
Database Management (MySQL Server)
SQL Querying & Analysis
Interactive Dashboard Development (Power BI)
Insight Reporting
Executive Presentation (Gamma)

📂 Dataset

The dataset contains transactional shopping data, including:
Customer demographics
Product categories
Purchase amounts
Payment methods
Shopping frequency
Store/location data

🧹 Data Loading & Cleaning (Python)
📥 Load Dataset
import pandas as pd
import numpy as np

# Load dataset
df = pd.read_csv("shopping_data.csv")

# Preview data
df.head()

🧽 Handle Missing Values & Duplicates
# Remove duplicates
df.drop_duplicates(inplace=True)

# Check missing values
df.isnull().sum()

# Fill missing numerical values with median
df['Purchase_Amount'].fillna(df['Purchase_Amount'].median(), inplace=True)

# Fill missing categorical values
df['Payment_Method'].fillna("Unknown", inplace=True)

🔄 Data Type Standardization
# Convert date column
df['Purchase_Date'] = pd.to_datetime(df['Purchase_Date'])

# Ensure numeric fields are correct
df['Purchase_Amount'] = pd.to_numeric(df['Purchase_Amount'])

📤 Export Cleaned Data
df.to_csv("cleaned_shopping_data.csv", index=False)

🗄️ MySQL Integration
🔌 Database Connection
import mysql.connector

conn = mysql.connector.connect(
    host="localhost",
    user="your_username",
    password="your_password",
    database="shopping_db"
)

cursor = conn.cursor()

📥 Create Table
create_table_query = """
CREATE TABLE shopping_data (
    customer_id INT,
    age INT,
    gender VARCHAR(50),
    category VARCHAR(100),
    purchase_amount FLOAT,
    payment_method VARCHAR(50),
    purchase_date DATE
);
"""

cursor.execute(create_table_query)

🧠 SQL Analysis
📊 1️⃣ Total Revenue by Category
SELECT category, SUM(purchase_amount) AS total_revenue
FROM shopping_data
GROUP BY category
ORDER BY total_revenue DESC;

📈 2️⃣ Monthly Sales Trend
SELECT 
    MONTH(purchase_date) AS month,
    SUM(purchase_amount) AS monthly_sales
FROM shopping_data
GROUP BY month
ORDER BY month;

👥 3️⃣ Average Spend per Customer
SELECT 
    customer_id,
    AVG(purchase_amount) AS avg_spend
FROM shopping_data
GROUP BY customer_id
ORDER BY avg_spend DESC;

📊 Power BI Dashboard
Dashboard Components

KPI Cards → Total Revenue, Total Orders, Average Spend

Sales Trend Line Chart
Category-wise Revenue Bar Chart
Payment Method Distribution Pie Chart
Customer Segmentation Filters

Example DAX Measure Used
Total Revenue = SUM(shopping_data[purchase_amount])

Average Spend = AVERAGE(shopping_data[purchase_amount])

📈 Key Business Insights

Top-performing product categories contribute the majority of revenue
Certain customer age groups show higher purchase frequency

Digital payment methods dominate transactions
Repeat customers drive significant revenue share
This demonstrates ability to convert raw transactional data into strategic business recommendations.

🚀 How to Run This Project
1️⃣ Clone Repository
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis

2️⃣ Install Dependencies
pip install pandas numpy mysql-connector-python

3️⃣ Run Jupyter Notebook
jupyter notebook

4️⃣ Open Power BI

Open .pbix file

Refresh dataset

🎯 Skills Demonstrated

✔ Data Cleaning & Transformation
✔ SQL Query Optimization
✔ Database Design
✔ Business KPI Development
✔ Data Visualization
✔ End-to-End Analytics Workflow
✔ Executive-Level Communication

👩‍💻 Author

Sangeetha Anand
Data Analytics | SQL | Python | Power BI
