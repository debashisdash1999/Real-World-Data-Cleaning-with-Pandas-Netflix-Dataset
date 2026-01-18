# Netflix Data Cleaning with Python Pandas

This project implements, in code, the full workflow demonstrated in the video **“Step-by-Step Netflix Data Cleaning with Python Pandas”**

The objective is to take the public **Netflix titles dataset** from Kaggle and transform it from a raw CSV file into a **clean, analysis-ready DataFrame** using **Python** and **Pandas**.

The project focuses on practical, real-world data cleaning techniques commonly used in data analysis and data engineering workflows.

---

## Project Goals

- Inspect and understand the raw Netflix dataset
- Identify and handle:
  - Missing values
  - Duplicate records
  - Incorrect or inconsistent data types
  - Non-standard text and date formats
- Standardize and clean columns for reliable analysis
- Produce a cleaned dataset ready for analysis or visualization

---

## Project Overview

The workflow closely follows the structure of the reference video:

### 1. Introduction
- Overview of the task
- What data cleaning means in a real data science context

### 2. Kaggle Data Card Review
- Understanding the dataset source and schema
- Identifying common data quality issues

### 3. Python Data Cleaning (Core Work)
Performed in a Jupyter Notebook using Pandas:
- Loading the dataset
- Exploring structure and quality
- Cleaning and transforming columns
- Handling missing values and duplicates
- Standardizing text and date formats

### 4. Outro
- Final recap
- How the cleaned dataset can be reused in future projects

---

## Dataset

### Source
- **Kaggle**: Netflix titles dataset  
- Typical file name: `netflix_titles.csv`


### Typical Schema

| Column Name     | Description |
|-----------------|-------------|
| show_id         | Unique identifier for each title |
| type            | Movie or TV Show |
| title           | Title of the content |
| director        | Director name(s) |
| cast            | Main cast |
| country         | Country of production |
| date_added     | Date added to Netflix |
| release_year   | Year of release |
| rating         | Maturity rating (TV-MA, PG-13, etc.) |
| duration       | Duration (e.g., 90 min, 2 Seasons) |
| listed_in      | Genre categories |
| description    | Short description |

### Common Data Issues Addressed

- Missing values in director, cast, country, rating, date_added
- Duplicate records
- Incorrect data types (dates and numeric fields stored as strings)
- Inconsistent text formatting
- Composite string fields with multiple values

---

## Tech Stack

- **Language**: Python
- **Core Library**: pandas
- **Environment**: Jupyter Notebook

### Optional Libraries
- numpy (numeric helpers)
- matplotlib / seaborn (visual checks during analysis)

---

## Data Cleaning Workflow

### 1. Import Libraries
- Imported required Python libraries (`pandas`, optional `numpy`) for data manipulation.

### 2. Load the Raw Dataset
- Loaded the Netflix CSV file into a Pandas DataFrame.
- Performed initial inspection using:
  - Head preview
  - Shape check
  - Data types and null counts
  - Basic statistical summary

### 3. Data Quality Assessment
- Identified missing values across columns.
- Checked for duplicate rows (overall and based on `show_id`).
- Reviewed columns with incorrect data types.
  - `date_added` identified as datetime
  - `release_year` identified as numeric

### 4. Handling Duplicates
- Removed exact duplicate records.
- Removed duplicates based on `show_id`.
- Verified duplicate removal.

### 5. Fixing Data Types
- Converted `date_added` to datetime format.
- Converted `release_year` to numeric integer type with null support.

### 6. Cleaning and Standardizing Text Columns
- Trimmed extra whitespace from text-based columns.
- Standardized categorical values (e.g., `Movie`, `TV Show`).
- Normalized inconsistent category naming.

### 7. Handling Missing Values
- Analyzed missing value counts and percentages.
- Applied column-wise strategies:
  - Dropped rows with missing identifiers or critical fields.
  - Filled descriptive fields with `"Unknown"`.
  - Retained missing dates as `NaT`.

### 8. Parsing and Cleaning `duration`
- Extracted numeric value and unit from the duration column.
- Created separate columns for duration value and duration unit.
- Standardized unit naming for consistency.

### 9. Multi-Value Column Cleanup
- Cleaned comma-separated fields for consistent formatting.
- Optionally split country values into list format for advanced analysis.

### 10. Final Consistency Checks
- Re-validated data types and structure.
- Rechecked missing values and duplicates.
- Performed basic sanity checks on key categorical distributions.

**Outcome:**  
A clean, consistent, and analysis-ready Netflix dataset.
