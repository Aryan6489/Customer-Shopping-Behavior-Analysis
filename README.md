# 🛍️ Customer Shopping Behavior Analysis

An end-to-end data analysis project covering data cleaning, SQL business analysis, and an interactive Power BI dashboard built on customer retail shopping data.

---

## 📊 Project Overview

| Stage | Tool | Description |
|-------|------|-------------|
| Data Cleaning & EDA | Python, Pandas, Jupyter | Clean raw data, engineer features |
| Database | MySQL + SQLAlchemy | Store cleaned data, run SQL queries |
| Business Questions | MySQL | Answer 10 analytical questions |
| Dashboard | Power BI | Interactive visual dashboard |

---

## 📁 Project Structure

```
customer-shopping-behavior-analysis/
│
├── data/
│   └── customer_shopping_behavior.csv       # Raw dataset (3,900 rows, 18 columns)
│
├── notebook/
│   └── customer_shopping_behavior_eda.ipynb # Data cleaning & feature engineering
│
├── sql/
│   └── customer_shopping_behavior.sql       # 10 business questions with SQL queries
│
├── dashboard/
│   ├── customer_behavior_dashboard.pbix     # Power BI dashboard file
│   └── customer_behavior_dashboard.pdf      # Dashboard screenshot/export
│
├── docs/
│   └── Customer_Shopping_Behavior_Documentation.docx  # Full project documentation
│
└── README.md
```

---

## 📂 Dataset

**File:** `data/customer_shopping_behavior.csv`  
**Rows:** ~3,900 | **Columns:** 18

| Column | Description |
|--------|-------------|
| Customer ID | Unique customer identifier |
| Age | Customer age |
| Gender | Male / Female |
| Item Purchased | Product name |
| Category | Clothing, Accessories, Footwear, Outerwear |
| Purchase Amount (USD) | Transaction value |
| Location | US state |
| Review Rating | Score out of 5 |
| Subscription Status | Yes / No |
| Shipping Type | Standard, Express, Free Shipping, etc. |
| Previous Purchases | Number of past orders |
| Frequency of Purchases | Weekly, Monthly, Annually, etc. |

---

## 🧹 Data Cleaning (Jupyter Notebook)

Steps performed in `notebook/customer_shopping_behavior_eda.ipynb`:

- **Null Handling** — `Review Rating` nulls filled with category-wise median
- **Column Renaming** — Standardised to `snake_case` for SQL compatibility
- **Feature: Age Group** — Created using `pd.qcut` into 4 quartile groups: `Young Adult`, `Adult`, `Middle Age`, `Senior`
- **Feature: Purchase Frequency Days** — Mapped text frequency to numeric days (e.g. Weekly → 7)
- **Drop Redundant Column** — `Promo Code Used` was 100% identical to `Discount Applied`, so it was dropped
- **MySQL Export** — Pushed cleaned DataFrame to MySQL using SQLAlchemy

---

## 🗄️ SQL Business Questions

All 10 queries are in `sql/customer_shopping_behavior.sql`

| # | Question |
|---|----------|
| Q1 | Total revenue by gender |
| Q2 | Discount users who spent above average |
| Q3 | Top 5 products by average review rating |
| Q4 | Standard vs Express shipping — avg purchase amount |
| Q5 | Do subscribed customers spend more? |
| Q6 | Top 5 products by discount usage rate |
| Q7 | Customer segmentation — New / Returning / Loyal |
| Q8 | Top 3 products per category (Window Function) |
| Q9 | Are repeat buyers more likely to subscribe? |
| Q10 | Revenue contribution by age group |

**Concepts used:** `GROUP BY`, `CASE WHEN`, `CTEs`, `Window Functions (ROW_NUMBER)`, `Subqueries`, `HAVING`

---

## 📈 Power BI Dashboard

**File:** `dashboard/customer_behavior_dashboard.pbix`

### KPI Cards
| Metric | Value |
|--------|-------|
| Total Customers | 3.9K |
| Avg Review Rating | 3.75 |
| Avg Purchase Amount | $59.76 |

### Visuals
- 🍩 **Donut Chart** — % of Customers by Subscription Status (No 73% / Yes 27%)
- 📊 **Bar Chart** — Sales by Category
- 📊 **Bar Chart** — Revenue by Category
- 📊 **Horizontal Bar** — Revenue by Age Group
- 📊 **Horizontal Bar** — Sales by Age Group

### Slicers
- Subscription Status, Gender, Category, Shipping Type

---

## 💡 Key Findings

- 🥇 **Clothing** is the top category in both revenue (~$100K) and order volume (~1.8K orders)
- 📉 Only **27% of customers subscribe** — large conversion opportunity
- 👶 **Young Adults** generate the highest revenue and order count
- 🎫 Customers who used discounts still spent above average in many cases
- 🔁 Repeat buyers (>5 purchases) are more likely to be subscribed

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

---

## ⚙️ How to Run

### 1. Clone the repo
```bash
git clone https://github.com/your-username/customer-shopping-behavior-analysis.git
cd customer-shopping-behavior-analysis
```

### 2. Install Python dependencies
```bash
pip install pandas numpy sqlalchemy pymysql
```

### 3. Run the notebook
Open `notebook/customer_shopping_behavior_eda.ipynb` in Jupyter and update the MySQL credentials:
```python
username = "your_username"
password = "your_password"
host = "localhost"
database = "your_database"
```

### 4. Run SQL queries
Import `sql/customer_shopping_behavior.sql` into MySQL Workbench or any MySQL client.

### 5. Open Power BI Dashboard
Open `dashboard/customer_behavior_dashboard.pbix` in Power BI Desktop.

---

## 📄 Documentation

Full step-by-step project documentation is available in `docs/Customer_Shopping_Behavior_Documentation.docx`

---

## 👤 Author

** Aryan Patel **  
📧 Email Id -aryanpatel0390@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/aryan-patel-36237b251)  
🐙 [GitHub](https://github.com/Aryan6489)

---

⭐ If you found this project helpful, give it a star!
