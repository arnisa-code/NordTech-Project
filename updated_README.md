Updated README file, after correcting the mistakes and adding Sortiment Analysis: 


# NordTech Data Analysis Project

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

# Author

Arnisa Gjoka
Data Manager / Data Analytics Student
TUC Yrkeshögskola
