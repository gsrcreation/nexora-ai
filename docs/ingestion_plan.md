# NEXORA-AI: Data Ingestion Plan

## 1. Objective

The objective of the NEXORA-AI data ingestion pipeline is to collect business data from different sources, import it into the system, inspect its structure and prepare it for validation and processing.

The initial implementation uses the Online Retail II dataset from the UCI Machine Learning Repository.

## 2. Dataset Source

| Attribute | Details |
|---|---|
| Dataset Name | Online Retail II |
| Source | UCI Machine Learning Repository |
| Dataset ID | 502 |
| Creator | Daqing Chen |
| Original Download URL | https://archive.ics.uci.edu/static/public/502/online+retail+ii.zip |
| Dataset Page | https://archive.ics.uci.edu/dataset/502/online+retail+ii |
| Licence | CC BY 4.0 |
| File Name | online_retail_II.xlsx |
| Storage Location | data/raw/ |

## 3. File Format

The selected dataset is stored in Excel format (.xlsx).

The dataset contains eight columns:

1. Invoice
2. StockCode
3. Description
4. Quantity
5. InvoiceDate
6. Price
7. Customer ID
8. Country

Python Pandas will be used to read and inspect the Excel data.

Future ingestion support will include:

- CSV (.csv)
- Excel (.xlsx)
- JSON (API responses)
- PostgreSQL relational tables

## 4. Python Data Ingestion

The initial implementation uses Python and Pandas.

### Libraries

| Library | Purpose |
|---|---|
| Pandas | Reading and manipulating datasets |
| OpenPyXL | Reading Excel files |
| SQLAlchemy | PostgreSQL database connectivity |
| NumPy | Numerical operations |

### Reading the Dataset

The dataset will be loaded using Pandas:

```python
import pandas as pd
from pathlib import Path

ROOT = Path(__file__).resolve().parents[2]

DATA_PATH = ROOT / "data" / "raw" / "online_retail_II.xlsx"

df = pd.read_excel(DATA_PATH)

print(df.head())
print(df.shape)
print(df.info())
```

The initial inspection process will examine:

- Dataset dimensions
- Column names
- Data types
- Missing values
- Duplicate records
- Statistical summaries

## 5. Raw Data Storage

Original datasets will be stored in:

`data/raw/`

The original dataset will remain unchanged to preserve data integrity and reproducibility.

Proposed directory structure:

```text
data/
    raw/
        online_retail_II.xlsx

    processed/
        cleaned_retail_data.csv
```

The processed directory will contain validated and cleaned datasets in later development stages.

## 6. PostgreSQL Integration Plan

PostgreSQL will be used for structured relational data storage.

The planned data flow is:

1. Read the original Excel file using Pandas.
2. Perform initial schema and data quality checks.
3. Prepare validated records for database insertion.
4. Establish a PostgreSQL connection using SQLAlchemy.
5. Create an appropriate database table.
6. Insert validated records into PostgreSQL.
7. Verify inserted records using SQL queries.

### Planned Data Flow

```text
Excel Dataset
     |
     v
Python + Pandas
     |
     v
Data Validation
     |
     v
Data Preparation
     |
     v
SQLAlchemy
     |
     v
PostgreSQL Database
```

Database credentials will be stored in environment variables rather than hardcoded into Python scripts.

PostgreSQL integration is planned and has not yet been implemented.

## 7. Required Validation Checks

Before data is used for analysis or machine learning, the following checks will be implemented:

| Validation Check | Purpose |
|---|---|
| Missing values | Identify incomplete records |
| Duplicate records | Identify repeated rows |
| Data type checks | Verify expected column types |
| Schema validation | Verify column names and structure |
| Date validation | Identify invalid dates |
| Quantity checks | Investigate negative and zero quantities |
| Price checks | Investigate negative and zero prices |
| Invoice checks | Identify cancelled invoices |
| Customer ID checks | Identify missing customer identifiers |

Records will not be deleted automatically. Each data quality issue will be investigated before applying cleaning rules.

## 8. Data Metadata

For reproducibility, the following metadata will be recorded:

- Dataset name
- Original source URL
- Licence information
- File name and format
- Ingestion timestamp
- Number of rows and columns
- Column names and data types
- Validation status

## 9. Current Implementation Status

| Task | Status |
|---|---|
| Dataset selection | Completed |
| Dataset source identification | Completed |
| Licence identification | Completed |
| Excel dataset download | Completed |
| Initial Pandas ingestion | Completed |
| Basic dataset inspection | Completed |
| Detailed data quality analysis | In progress |
| Data dictionary | Pending |
| Validation script | Pending |
| Cleaning pipeline | Pending |
| PostgreSQL integration | Planned |

## 10. Expected Outcome

The ingestion pipeline will provide a consistent and reproducible process for importing business data into NEXORA-AI.

It will establish the foundation for data validation, cleaning, exploratory analysis, feature engineering and machine learning.

Future development will extend the pipeline to support PostgreSQL databases and approved external APIs.