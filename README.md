# 🍬 Candy Sales & Supply Analysis Dashboard

## 📊 Project Overview
The **Candy Sales & Supply Analysis** project is a complete **end-to-end data analytics solution** designed to analyze candy sales performance, inventory flow, and supply efficiency across the United States.  

This project follows the **Medallion Architecture (Bronze → Silver → Gold)** using **SQL and Power BI** to build a clean, scalable, and business-ready data pipeline.

---

## 🏗️ Project Architecture

Source CSV Files → Bronze Layer (Raw)
↓
Silver Layer (Cleaned & Enriched)
↓
Gold Layer (Analytics & KPIs)
↓
Power BI Dashboard


---

## Business Problem
The candy company was facing the following challenges:
Limited visibility into sales performance across regions and products.


Difficulty in identifying top and low-performing products.


Inventory imbalance — overstocking in some regions and stockouts in others.


Inefficient supply and delivery tracking, leading to delayed orders.

---
## Project Objective
The main goal is to build an interactive Power BI dashboard that provides a 360° view of sales, inventory, and supply operations.
 The objectives include:
Analyzing sales trends and identifying profitable products.


Monitoring inventory to ensure balanced stock levels.


Evaluating distributor and factory performance.


Supporting faster, insight-driven business decisions.

---
## 🟫 Bronze Layer (Raw Data Layer)

**Purpose:**  
Stores **raw data directly from source files** (CSV/Excel) with no transformation.  
This layer acts as a *landing zone* for all original datasets.

**Datasets:**
- `candy_sales_raw.csv` – Sales transactions (Transaction ID, Date, Revenue, Units, Factory, ZIP)
- `candy_products_raw.csv` – Product details (Product Name, Category, Price)
- `candy_factories_raw.csv` – Factory information (Factory Name, Location, Capacity)
- `uszips_raw.csv` – ZIP code details (City, State, Population)
- `candy_targets_raw.csv` – Monthly/Regional target values

---

## ⚪ Silver Layer (Cleaned & Enriched Layer)

**Purpose:**  
Performs **data cleaning, transformation, and enrichment** to create standardized, validated tables ready for business logic.

**Key Transformations:**
- Removed duplicates, nulls, and invalid data  
- Standardized column names and data types  
- Joined sales with product, factory, and ZIP code info  
- Added derived fields (Month, Quarter, Year, Avg_Selling_Price, Profit_Estimate)

**Output Tables:**
- `candy_sales_clean`
- `candy_products_clean`
- `candy_factories_clean`
- `uszips_clean`
- `candy_targets_clean`
- `candy_sales_enriched` *(joined master table)*
- `candy_sales_features` *(adds Month, Quarter, Year, Profit, Avg_Price)*

---

## 🟡 Gold Layer (Business & Analytics Layer)

**Purpose:**  
Generates **business-ready views** for analysis and dashboard reporting in Power BI.  
This layer focuses on KPIs, trend analysis, and performance evaluation.

**Key Views:**
- `vw_kpi_overview` → Total, MTD, YTD Sales & Units  
- `vw_monthly_sales_summary` → Monthly/Category Sales Trends  
- `vw_top10_candies_mtd_qtd_ytd` → Top 10 Candies Performance  
- `vw_region_target_vs_actual` → Regional Target vs Actual Sales  
- `vw_factory_efficiency` → Factory Capacity Utilization & Supply Metrics  

---

## 📈 Power BI Dashboard

**Dashboard Pages:**
1. **Executive Overview** – Total Revenue, Units Sold, MTD/YTD KPIs  
2. **Sales Performance** – Monthly Trends, Top 10 Candies (MTD/QTD/YTD)  
3. **Inventory Flow** – Stock levels, Out-of-Stock %, Turnover rate  
4. **Supply Efficiency** – Factory utilization & On-time delivery rate  
5. **Regional Insights** – Sales by State, Target Achievement  
6. **KPI Table (MTD/YTD)** – Time-based comparison table for top metrics  

**Key KPIs:**
- Total Sales Revenue  
- Units Sold  
- Average Selling Price  
- Target Achievement %  
- On-Time Delivery Rate  
- Factory Utilization %  
- Return Rate  

---

## 🧰 Tools & Technologies

| Category | Tools |
|-----------|-------|
| Data Storage | MySQL |
| Data Transformation | SQL (CTE, Joins, Aggregations) |
| Data Modeling | Medallion Architecture (Bronze, Silver, Gold) |
| Visualization | Power BI |
| Data Source | CSV Files (US Candy Distributor Dataset) |

---

## 🔍 Insights & Outcomes

- Identified **Top 10 Best-Selling Candies** across multiple time periods (MTD, QTD, YTD).  
- Analyzed **regional sales trends** and target achievement rates.  
- Evaluated **factory performance** and supply efficiency using utilization metrics.  
- Enabled **data-driven decision-making** through KPI-driven Power BI dashboards.  

---

## 🧠 Learning Highlights

- Implemented **Medallion Data Architecture** in SQL.  
- Applied **ETL best practices** (Extract → Transform → Load).  
- Designed **interactive dashboards** with Power BI.  
- Practiced **data cleaning, enrichment, and business logic modeling**.

---

## 🚀 How to Run

1. Import all CSV files into the `bronze` schema in MySQL.  
2. Run SQL scripts for `silver` and `gold` schemas (included in `/sql_scripts/`).  
3. Connect Power BI to the `gold` schema views.  
4. Build visuals based on Gold layer outputs.  

---

## 📂 Folder Structure

📁 Candy-Sales-Analysis
├── 📂 data
│ ├── Candy_Sales.csv
│ ├── Candy_Products.csv
│ ├── Candy_Factories.csv
│ ├── Candy_Targets.csv
│ ├── uszips.csv
├── 📂 sql_scripts
│ ├── bronze_layer.sql
│ ├── silver_layer.sql
│ ├── gold_layer.sql
├── 📂 powerbi_dashboard
│ ├── Candy_Sales_Analysis.pbix
├── README.md


---

## 👩‍💻 Author
**Samiksha Nikhare**  
🎓 B.Tech in Computer Science (AIML) | G.H. Raisoni College of Engineering, Nagpur  
💡 Passionate about Data Analytics, SQL, and Business Intelligence  

---

## 🏁 Summary Commit Message
> Added Bronze (raw), Silver (cleaned/enriched), and Gold (analytics) layers with SQL-based ETL pipeline and Power BI dashboard for Candy Sales & Supply Analysis.

---


