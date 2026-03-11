# Marketing Campaign Data Cleaning (Python)

## Overview
This project focuses on cleaning and preparing a messy marketing campaign dataset using Python.  
The dataset initially contained multiple real-world data quality issues such as inconsistent formatting, missing values, incorrect data types, currency formatting problems, categorical typos, and logical inconsistencies.

The goal of this project is to transform raw, unstructured marketing data into a clean and analysis-ready dataset using data cleaning techniques in Python.

The project was developed using **Google Colab** and the **Pandas** library.

---

## Dataset Issues Identified
The dataset contained several common data quality problems:

- Inconsistent column headers
- Currency formatting in numeric fields
- Null and missing values
- Categorical typos
- Mixed boolean representations
- Incorrect date formats
- Logical inconsistencies in data
- Duplicate columns
- Outliers in numerical fields
- Unstructured strings requiring feature extraction

---

## Data Cleaning Steps

### 1. Header Cleaning
Standardized column names by:
- Removing extra spaces
- Converting to lowercase
- Replacing spaces with underscores

### 2. Currency Standardization
The `spend` column contained values with currency symbols and text formatting.  
These were cleaned by removing non-numeric characters and converting the column to numeric format.

### 3. Fixing Categorical Typos
Several values in the `channel` column were inconsistent or misspelled.  
A mapping dictionary was used to standardize them.

Example corrections:
- Facebok → Facebook
- Tik_Tok → TikTok
- Insta_gram → Instagram
- Gogle → Google Ads
- Email → E-mail

### 4. Handling Mixed Boolean Values
The `active` column contained mixed boolean representations such as:
- Yes / No
- Y / N
- 1 / 0

These were mapped into proper `True` and `False` boolean values.

### 5. Date Parsing
Date columns were converted into proper datetime format using Pandas.

Columns cleaned:
- `start_date`
- `end_date`

Invalid dates were handled using coercion.

### 6. Logical Integrity Checks
Two logical issues were verified:

**Clicks vs Impressions**
- Clicks should never exceed impressions

**Campaign Timeline**
- Campaign end dates must occur after start dates

### 7. Duplicate Column Handling
Duplicate columns were detected and removed from the dataset.

### 8. Outlier Detection
Outliers in the `spend` column were detected using the **Interquartile Range (IQR)** method and handled using winsorization techniques.

### 9. Feature Extraction
Structured features were extracted from text fields.

Example:
`campaign_name` was parsed to extract a new feature called:

- `campaign_type`

using regular expressions.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Google Colab

---

## Project Structure

```
marketing-data-cleaning/
│
├── marketing_campaign_data_messy.csv
├── data_cleaning_marketing.ipynb
└── README.md
```

---

## Key Learning Outcomes

This project demonstrates practical data cleaning skills including:

- Handling messy real-world datasets
- Data type conversion
- Feature engineering
- Data validation and integrity checks
- Outlier detection
- Text parsing using regex
- Preparing data for analysis

---

## Future Improvements

Possible next steps include:

- Exploratory Data Analysis (EDA)
- Marketing performance dashboards
- Campaign performance analysis
- Visualization using Power BI or Python

---

## Author

Bhargav Jagtap

Aspiring Data Analyst with interests in data analytics, machine learning, and business intelligence.
