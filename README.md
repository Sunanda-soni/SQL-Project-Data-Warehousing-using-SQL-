# SQL-Project-Data-Warehousing
SQL Warehouse Project

**1. Project Overview & Objective**
The goal of this project is to design and implement a centralized Data Warehouse for a global bicycle and sporting goods retailer. The business acquires data from two distinct legacy source systems (or third-party vendors), which causes data silos. By building an automated ETL (Extract, Transform, Load) pipeline using SQL, this project integrates disparate customer, product, and sales datasets into a structured analytical data model. The resulting data warehouse acts as the single source of truth for downstream Business Intelligence (BI) tools to track sales performance, customer demographics, and product catalog maintenance.

**2. Source Systems Overview**
The project integrates data from six files coming from two different source systems.
**Source System 1:** Core Transaction & Master Data System**
**Source System 2:** Extended Demographics & Catalog Categorization**

**3. Target Data Warehouse Architecture**
The target data model follows a classic Star Schema, optimized for fast aggregations and OLAP (Online Analytical Processing) workloads.
**Fact Table: Fact_Sales**
Granularity: One row per product line item per sales order.
Keys: SalesOrderNumber, CustomerID, ProductID.
Measures: SalesAmount, OrderQuantity, UnitPrice.
Role-Playing Dates: OrderDate, ShipDate, DueDate.

**Dimension Tables:**
Dim_Customer: A conformed dimension consolidating cust_info, CUST_AZ12, and LOC_A101. It provides a unified 360-degree view of the customer (Name, Gender, Marital Status, Age/Birthdate, Country, and Account Age).
Dim_Product: A conformed dimension consolidating prd_info and PX_CAT_G1V2. It tracks product names, costs, product lines, and groups them functionally into Categories and Sub-categories. It also contains historical valid dates to act as a Type 2 Slowly Changing Dimension (SCD Type 2).
Dim_Date: (Implicit or generated) Used to slice and dice sales by Year, Quarter, Month, and Week based on the integer date formats found in sales_details (e.g., 20101229).

### 4. Specifications
- **Data Sources**: Import data from two source systems (ERP and CRM) provided as CSV files.  
- **Data Quality**: Cleanse and resolve data quality issues prior to analysis.  
- **Integration**: Combine both sources into a single, user-friendly data model designed for analytical queries.  
- **Scope**: Focus on the latest dataset only; historization of data is not required.  
- **Documentation**: Provide clear documentation of the data model to support both business stakeholders and analytics teams.

**5.. Business Value & Analytical Use Cases**
Once the data warehouse is populated, it unlocks the ability to answer vital business questions using SQL, Power BI, or Tableau:
Geographical Performance: Which countries (CNTRY) generate the highest revenue and order volume?
Demographic Targeting: What is the average order value (AOV) broken down by Customer Age (derived from BDATE), Gender, and Marital Status?
Product Profitability & Maintenance: Are products flagged as requiring MAINTENANCE generating more volume than non-maintenance products? Which Sub-categories (e.g., Mountain Bikes vs. Touring Bikes) drive the most profit?
Supply Chain Efficiency: What is the average lead time (difference between sls_order_dt and sls_ship_dt), and does it vary by product category?, Develop sql based analytics to deliver detailed insights into Customer Behaviour, Product Performance, Sales TrendsThese insights empower stakeholders with key business matrics, enabling stratergic business making.

**👋 About Me**
Hi! I'm Sunanda, an aspiring Data Analyst passionate about transforming raw data into actionable insights.
**Skills:** SQL, Python, Tableau, Power BI, Databricks, Excel, Data Visualization, Data Cleaning, ETL, Data Warehousing
I work on end-to-end analytics and data warehouse projects, including building dashboards, performing data analysis, and designing data pipelines. My GitHub showcases projects on e-commerce analytics, stock analysis, and data warehouse implementations.
Currently focused on improving my data analytics and data warehousing skills through hands-on projects.
When I'm not analyzing data, I enjoy reading, exploring new technologies, and sharing knowledge with the community.
  



















