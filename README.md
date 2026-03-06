# NordTech Data Analysis Project

ETL pipeline and sentiment analysis project built using Python, Pandas and BERT to extract insights from messy real-world business data.

I have updated my README file, beased on the feedback I got, correcting some mistakes and adding Sentiment Analysis. 



## Project Overview

This project was developed to help **NordTech Solutions** gain better insight into their operational and customer data.
The company had collected data over time but lacked the tools and structured process needed to properly clean, analyze, and extract insights from it.

The goal of this project was to build a **complete ETL pipeline** that transforms raw, inconsistent data into a clean dataset that can be used for analysis and business decision-making.

The project includes:

* Data extraction from raw CSV files
* Data cleaning and transformation
* Feature engineering
* Sentiment analysis using a BERT-based model
* Data validation and quality checks
* Visualizations and insights generation

---

# Dataset

The dataset represents **NordTech sales and customer interaction data**, including:

* Order information
* Product details
* Customer data
* Delivery information
* Customer reviews
* Product ratings

Two datasets were provided:

**Main dataset**

```
data/raw/nordtech_data.csv
```

Used for exploration, cleaning and analysis.

**Validation dataset**

Used to verify that the ETL pipeline works correctly on new incoming data.

---

# ETL Pipeline

The ETL pipeline follows three main stages:

## Extract

Raw data is loaded from CSV files using **Pandas**.

Initial exploration (EDA) was performed to understand:

* column structure
* missing values
* data types
* inconsistencies in formatting

---

## Transform

The transformation phase focuses on making the dataset reliable and analysis-ready.

### Data Cleaning

Several common real-world data issues were handled:

• inconsistent date formats
• currency symbols in price columns
• numeric values stored as text
• missing values in categorical fields
• incorrect delivery times

Raw values were preserved in additional columns (e.g. `_raw`) for auditing purposes.

Example:

```
orderdatum_raw
pris_per_enhet_raw
antal_raw
```

This allows tracking of how data was transformed.

---

### Data Validation

Validation flags were created to detect problematic rows:

* `invalid_order_date`
* `invalid_delivery_date`
* `invalid_quantity`
* `invalid_price`
* `invalid_lead_time`

Only rows that were **truly unusable** were removed, reducing unnecessary data loss.

---

### Feature Engineering

Additional analytical features were created:

* `revenue`
* `lead_time_days`
* `order_weekday`
* `order_month`

These features allow better analysis of customer behavior and operational performance.

---

# Sentiment Analysis

Customer review text was analyzed using a **BERT-based multilingual sentiment model**.

Model used:

```
nlptown/bert-base-multilingual-uncased-sentiment
```

This allowed extraction of sentiment directly from **review text**, rather than relying only on numerical ratings.

Sentiment results were categorized as:

* Positive
* Neutral
* Negative

Rows without review text were left empty and **not interpreted as unknown sentiment**.

This prevents distortion of the analysis.

---

# Analysis

The analysis compares:

* **Customer rating (betyg)**
* **BERT sentiment prediction**

Example insight:

Some reviews with neutral or mixed text did not fully align with the numeric rating, demonstrating the value of **text-based sentiment analysis**.

A cross-tabulation was used to analyze the relationship between ratings and sentiment.

---

# Output Files

Cleaned and enriched dataset:

```
data/processed/nordtech_cleaned_with_sentiment.csv
```

This dataset contains:

* cleaned data
* engineered features
* sentiment analysis results

---

# Project Structure

```
NordTech-Project
│
├── data
│   ├── raw
│   │   └── nordtech_data.csv
│   ├── processed
│   │   └── nordtech_cleaned_with_sentiment.csv
│
├── notebooks
│   ├── 01_nordtech_eda.ipynb
│   └── corrected_nordtech_eda.ipynb
│
├── outputs
│   └── figures
│
├── docs
│   └── data_dictionary.csv
│
├── .gitignore
├── README.md
```

---

# Tools and Technologies

The following tools were used:

* Python
* Pandas
* NumPy
* Matplotlib
* Jupyter Notebook
* HuggingFace Transformers
* BERT Sentiment Model
* Git
* GitHub
* VS Code

---

# Key Insights

Some important observations from the analysis:

• Missing reviews should not be interpreted as unknown sentiment.
They represent cases where customers did not leave feedback.

• Proper data cleaning significantly reduced unnecessary row removal.

• Text-based sentiment analysis provided deeper insight compared to ratings alone.

---





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
