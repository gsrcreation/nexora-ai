-# NEXORA AI

## Expected Data Quality Problems

**Prepared By:** Yashvant Thakur

## 1. Introduction

Data quality is an important part of any data analytics and machine learning project.

Real-world retail datasets may contain missing values, duplicate records, incorrect data types, and inconsistent information.

The following are potential data quality problems that should be investigated in the Nexora AI project.

## 2. Missing Values

Some records may have missing information.

Examples:

* Missing customer_id.
* Missing product_id.
* Missing order_date.
* Missing revenue.
* Missing product category.

Impact:
Missing values can affect statistical analysis and machine learning model performance.

## 3. Duplicate Records

The dataset may contain repeated records.

Examples:

* Same order ID appearing multiple times.
* Duplicate customer records.
* Repeated product information.

Impact:
Duplicates can produce incorrect sales calculations and business reports.

## 4. Incorrect Data Types

Some columns may have incorrect data formats.

Examples:

* Dates stored as strings.
* Revenue stored as text.
* Quantity stored in an incorrect numerical format.

Impact:
Incorrect data types can cause errors during data processing and analysis.

## 5. Invalid Values

The dataset may contain impossible or incorrect values.

Examples:

* Negative product quantity.
* Negative selling price.
* Invalid transaction dates.
* Negative stock quantity.

Impact:
Invalid values can create misleading business insights.

## 6. Inconsistent Categories

The same category may be represented in different formats.

Examples:

* Electronics
* electronics
* ELECTRONICS

Impact:
Inconsistent categories can affect grouping and visualization.

## 7. Outliers

Some records may contain unusually high or low values.

Examples:

* Extremely high product prices.
* Unusually large order quantities.
* Very high transaction revenue.

Impact:
Outliers may affect statistical analysis and prediction models.

## 8. Inconsistent Customer Information

Examples:

* Different spellings of customer names.
* Duplicate customer IDs.
* Missing customer locations.
* Incorrect customer information.

Impact:
Customer analysis may become inaccurate.

## 9. Inventory Data Problems

Examples:

* Negative stock quantity.
* Incorrect product identifiers.
* Missing inventory update dates.
* Inconsistent stock records.

Impact:
Inventory analysis and demand forecasting may become unreliable.

## 10. Conclusion

These are expected data quality issues based on common retail data characteristics.

The actual problems will be identified after collecting and examining the project dataset.

Data cleaning and validation will be performed before machine learning model development.

**Prepared by:** Yashvant Thakur
