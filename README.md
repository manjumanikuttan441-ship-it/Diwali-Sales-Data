# Diwali-Sales-Data
Diwali Sales in India
# Diwali Sales Dataset – Data Cleaning Using Python

## 📌 Project Overview

This project focuses on cleaning and preprocessing the Diwali Sales Dataset obtained from Kaggle. The main objective is to improve data quality by identifying and handling missing values, removing unnecessary columns, correcting data types, and preparing the dataset for further analysis.

Data cleaning is an important step in the data analysis process because accurate and consistent data helps produce reliable insights.

## 📂 Dataset Information

- **Dataset Name:** Diwali Sales Dataset
- **Source:** Kaggle
- **Dataset Link:** https://www.kaggle.com/datasets/bharathid8/diwali-sales-dataset
- **Initial Records:** 11,251 rows
- **Initial Columns:** 15
- **File Format:** CSV
- **Domain:** Retail Sales Analysis

### Dataset Features

The dataset contains customer and sales-related information, including:

| Column | Description |
|---|---|
| User_ID | Unique customer identification |
| Cust_name | Customer name |
| Product_ID | Product identification |
| Gender | Customer gender |
| Age Group | Customer age category |
| Age | Customer's actual age |
| Marital_Status | Customer's marital status |
| State | Customer's state |
| Zone | Geographical zone |
| Occupation | Customer occupation |
| Product_Category | Category of purchased product |
| Orders | Number of orders |
| Amount | Purchase amount |

## 🛠️ Tools and Technologies Used

- **Python:** Programming language for data cleaning.
- **Pandas:** Data manipulation and preprocessing.
- **NumPy:** Numerical operations.
- **Jupyter Notebook:** Interactive development environment.

## 🧹 Data Cleaning Process

The following data cleaning steps were used as the preprocessing workflow for this dataset.

### 1. Importing Libraries

Imported the required Python libraries for data manipulation and analysis.

```python
import pandas as pd
import numpy as np
```

### 2. Loading the Dataset

Imported the CSV file into a Pandas DataFrame.

```python
df = pd.read_csv('Diwali Sales Data.csv', encoding='unicode_escape')
```

### 3. Understanding the Dataset

Examined the dataset structure, dimensions, column names, and data types.

```python
df.head()
df.shape
df.info()
df.describe()
```

### 4. Handling Unnecessary Columns

Identified and removed two completely empty and irrelevant columns:

- Status
- unnamed1

```python
df.drop(['Status', 'unnamed1'], axis=1, inplace=True)
```

### 5. Handling Missing Values

Checked for missing values in the dataset.

```python
df.isnull().sum()
```

The `Amount` column contained 12 missing values.

Removed rows containing missing values to maintain data consistency.

```python
df.dropna(inplace=True)
```

### 6. Changing Data Types

The `Amount` column was initially stored as a floating-point data type.

Converted it into an integer data type for consistency.

```python
df['Amount'] = df['Amount'].astype('int')
```

### 7. Renaming Columns

Reviewed column names to improve readability.

For example:

```python
df.rename(columns={'Marital_Status': 'Married'}, inplace=True)
```

### 8. Final Data Verification

Verified the cleaned dataset to ensure that the missing values were handled and the data types were corrected.

```python
df.isnull().sum()
df.info()
df.shape
```

## 📊 Cleaning Results

| Description | Before Cleaning | After Cleaning |
|---|---:|---:|
| Total Rows | 11,251 | 11,239 |
| Total Columns | 15 | 13 |
| Missing Amount Values | 12 | 0 |
| Empty Columns | 2 | 0 |
| Amount Data Type | Float | Integer |

## 📁 Final Output

After completing the data cleaning process, the dataset was prepared for Exploratory Data Analysis (EDA).

The cleaned dataset can be used for:
- Customer purchasing behaviour analysis.
- Gender-wise sales analysis.
- Age-group sales analysis.
- State-wise sales performance.
- Occupation-based purchasing analysis.
- Product category analysis.

## 🎯 Project Objectives

- Improve the overall quality of raw sales data.
- Identify and handle missing values.
- Remove unnecessary columns.
- Correct data types.
- Prepare a structured dataset for further analysis.
- Develop practical Python data cleaning skill
