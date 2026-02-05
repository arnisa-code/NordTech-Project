# NordTech-Project

#  NordTech Sales ETL Pipeline & KPI Analysis

ETL pipeline and data analytics project developed for NordTech Solutions.

---

##  Project Overview

This project builds a complete **ETL pipeline** that processes raw sales data, cleans and transforms it, stores it in a SQLite database, and generates business insights through KPI analysis and visualizations.

The project simulates a real-world data engineering and analytics workflow.

---

##  ETL Pipeline

###  Extract

- Raw sales data is loaded from CSV files
- Initial exploratory data analysis (EDA) is performed to understand:
  - Dataset structure
  - Missing values
  - Data consistency

---

###  Transform

Data cleaning and preparation steps include:

#### Data Cleaning
- Converted date columns to datetime format
- Converted numeric columns to proper data types
- Handled missing values:
  - Removed rows with missing critical business fields
  - Filled optional fields with default values

#### Feature Engineering
- Revenue calculation
- Delivery lead time calculation
- Time-based features:
  - Weekday
  - Month
  - Weekly sales aggregation

#### Sentiment Analysis
Customer reviews are classified into:
- Positive
- Neutral
- Negative  
Based on customer rating scores.

#### Data Dictionary
A structured documentation file describing:
- All dataset columns
- Data types
- Transformations applied

---

###  Load

- Cleaned dataset is stored in a local SQLite database
- Data loading is verified using row count validation

---

###  Validation

The full ETL pipeline is executed on a validation dataset to ensure:

- Automation
- Robust cleaning logic
- Consistent transformations
- No manual adjustments required

---

##  KPI Analysis & Business Insights

The project calculates key business performance indicators:

###  Weekly Sales Trend
Analyzes revenue patterns over time and identifies seasonal behavior.

---

###  Average Order Value (AOV)
Measures customer purchase behavior and overall order profitability.

---

###  Delivery Lead Time
Evaluates logistics performance and delivery efficiency.

---

###  Customer Sentiment
Analyzes customer satisfaction based on review ratings.

---

##  Visualizations

Visualizations are generated using:

- Matplotlib
- Seaborn

Charts include:
- Weekly revenue trends
- Order value distribution
- Delivery performance analysis
- Customer sentiment distribution

---

##  Technologies Used

- Python
- Pandas
- SQLite
- Matplotlib
- Seaborn
- Jupyter Notebook
- Git & GitHub

---

## ▶ How To Run The Project

1. Clone repository:
git clone https://github.com/your-repository-link


2. Open notebook:
notebooks/01_nordtech_eda.ipynb


3. Run all cells

The pipeline will automatically:

- Extract raw data
- Clean and transform dataset
- Load data into SQLite
- Validate pipeline
- Generate KPIs and visualizations

---

##  Project Structure

NordTech-Project
│
├── data
│ ├── raw
│ ├── validation
│ └── processed
│
├── database
│ └── nordtech.db
│
├── docs
│ └── data_dictionary.csv
│
├── notebooks
│ └── 01_nordtech_eda.ipynb
│
├── outputs
│ └── figures
│
├── README.md
├── .gitignore



---

##  Learning Objectives

This project demonstrates:

- Building automated ETL pipelines
- Handling real-world data quality issues
- Feature engineering techniques
- Pipeline validation on new datasets
- Business KPI analysis
- Data visualization & storytelling
- Version control using Git & GitHub

---

## ARNISA GJOKA

Data Science / Data Manager student project  






Updated on: 2026-02-05