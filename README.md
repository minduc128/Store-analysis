# Store-analysis
Analyze orders, revenue, and customers
Project Overview
This project provides a comprehensive end-to-end data analytics solution for Adventure Works, a global manufacturing company. Using Power BI, I transformed raw transactional, product, and customer data into an interactive dashboard to track Key Performance Indicators (KPIs), regional performance, and customer demographics. The goal is to empower stakeholders to identify growth opportunities and optimize product offerings based on real-time data insights.
Dataset Description
The analysis is built upon a relational schema comprising 8 primary datasets (CSV format):
Sales: Transactional records including order dates, quantities, and keys for products and customers
.
Returns: Data on returned items and return dates
.
Products & Categories: A 3-tier hierarchy (Categories > Subcategories > Products)
.
Customers: Demographic details including income, occupation, and home ownership
.
Calendar: A continuous date table for time-intelligence calculations
.
Territories: Global sales regions across North America, Europe, and the Pacific
.
Tools & Technologies
Power BI Desktop: Used for the entire development lifecycle.
Power Query (M): For data extraction, cleaning, and transformation.
DAX (Data Analysis Expressions): For advanced statistical modeling and time-intelligence measures.
Data Modeling: Established a Star Schema with 1:Many relationships.
Project Workflow
Data Extraction: Imported 8 CSV files into Power BI.
Data Cleaning: Performed "ETL" in Power Query to handle fragmented rows and null values.
Data Modeling: Connected fact tables (Sales, Returns) to dimension tables (Products, Customers, Calendar, Territories).
DAX Development: Created 20+ measures for revenue growth, return rates, and rolling totals.
Dashboard Design: Built a multi-page interactive report with drill-through capabilities.
Data Cleaning & Transformation
To ensure data integrity, several critical cleaning steps were performed in Power Query:
Row Fragmentation: Filtered the order_number column to keep only values beginning with "SO", effectively removing fragmented "junk" rows from the CSV source [257, History].
Null Management: Replaced null values in Customer demographics (e.g., Prefix, Gender) with "Unknown" and missing occupations with "Other" to prevent (Blank) categories in visuals [History].
Data Quality: Used "Column Quality" tools to identify and remove empty product keys in the Returns table
.
Power BI Dashboard
The dashboard features three primary views:
Executive Summary: High-level KPIs showing Total Revenue, Total Orders, and Monthly Revenue Growth.
Product Analysis: A Treemap visualization showing the hierarchy of categories and subcategories [History].
Customer Insights: A Combo Chart comparing the number of customers and total income across different Age Groups [History].
Key Insights & Results
Category Performance: While "Components" has a high number of unique products in the catalog, it currently generates zero retail sales, suggesting it may be used strictly for internal assembly [History].
Revenue Growth: Implemented a RevenueLM measure using DATEADD to compare current monthly performance against the previous month, allowing for trend detection [History].
Return Rates: Analysis revealed specific product keys with high return volumes, enabling the quality control team to investigate manufacturing issues [1, History].
Customer Profiles: Customers in professional and management occupations represent the highest revenue-per-customer segment [History].
How to Run the Project
Ensure you have Power BI Desktop installed.
Download the .pbix file and the associated CSV folder from this repository.
Open the .pbix file.
If the data does not load, go to Transform Data > Data Source Settings and update the path to the CSV folder on your local machine.
Click Refresh to populate the report.
