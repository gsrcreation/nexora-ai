# NEXORA-AI: Data Ingestion Plan

## 1. Objective

The objective of the data ingestion pipeline is to collect business data from different sources, import it into the NEXORA-AI system, inspect its structure and prepare it for validation and processing.

The initial implementation focuses on the Online Retail II dataset.

## 2. Dataset Information

| Attribute | Details |
|---|---|
| Dataset Name | Online Retail II |
| Source | UCI Machine Learning Repository |
| Dataset ID | 502 |
| File Name | online_retail_II.xlsx |
| Format | Excel (.xlsx) |
| Original Source | https://archive.ics.uci.edu/static/public/502/online+retail+ii.zip |
| Licence | CC BY 4.0 |
| Storage Location | data/raw/ |
| Status | Initial ingestion completed |

## 3. Supported Data Sources

NEXORA-AI is designed to support the following data sources:

1. CSV Files (.csv)
2. Excel Files (.xlsx)
3. Relational Databases (PostgreSQL)
4. Approved APIs (JSON responses)

Initial development will focus on Excel and CSV ingestion.

Database and API ingestion will be implemented in later stages.

## 4. Technology Stack

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Pandas | Data ingestion and manipulation |
| NumPy | Numerical operations |
| OpenPyXL | Excel file reading |
| PostgreSQL | Relational data storage |
| SQLAlchemy | Database connectivity (planned) |

## 5. Ingestion Workflow

The proposed ingestion workflow:

1. Identify the data source.
2. Record the source URL and licence.
3. Locate and import the dataset.
4. Inspect column names and data types.
5. Check dataset dimensions.
6. Identify missing values and duplicates.
7. Perform initial data quality checks.
8. Store original data in the raw directory.
9. Pass validated data to the cleaning pipeline.

## 6. Project Directory Structure

```text
data/
    raw/
        online_retail_II.xlsx
    processed/

src/
    ingestion/
        inspect_data.py
        ingest.py
    validation/
        validate.py
```

### Directory Responsibilities

- data/raw/: Stores original, unmodified datasets.
- data/processed/: Stores cleaned and processed datasets.
- src/ingestion/: Contains data importing and inspection scripts.
- src/validation/: Contains data quality and validation checks.

## 7. Data Metadata

The following metadata should be recorded for every imported dataset:

- Dataset name
- Original source URL
- Source platform
- Licence information
- File format
- File name
- Ingestion timestamp
- Number of rows and columns
- Column names
- Data types
- Validation status

## 8. Data Quality Checks

The ingestion and validation stages will investigate:

- Missing values
- Duplicate records
- Incorrect data types
- Negative quantities
- Invalid or zero prices
- Cancelled invoices
- Invalid dates
- Unexpected column names
- Schema inconsistencies

Records will not be deleted automatically without investigation.

## 9. Storage Strategy

NEXORA-AI will maintain separate storage locations for raw and processed data.

### Raw Data
Original datasets will remain unchanged to preserve data integrity and reproducibility.

### Processed Data
Validated and cleaned datasets will be stored separately for exploratory analysis and machine learning.

PostgreSQL will be introduced for structured relational storage as the project develops.

## 10. Current Implementation Status

| Task | Status |
|---|---|
| Dataset selection | Completed |
| Dataset source identification | Completed |
| Licence identification | Completed |
| Excel dataset download | Completed |
| Initial Pandas ingestion | Completed |
| Dataset inspection | In progress |
| Both worksheet inspection | Pending |
| Data quality analysis | Pending |
| Validation script | Pending |
| Cleaning pipeline | Pending |
| PostgreSQL integration | Planned |

## 11. Future Improvements

- Support multiple file formats.
- Implement reusable ingestion functions.
- Add automated schema validation.
- Record ingestion logs and timestamps.
- Add error handling for missing or corrupted files.
- Introduce PostgreSQL connectivity.
- Implement automated data quality checks.
- Make ingestion workflows reproducible.

## 12. Expected Outcome

The ingestion pipeline should provide a consistent and reproducible method for importing business data into NEXORA-AI.

It will serve as the foundation for data validation, cleaning, feature engineering and machine learning workflows.