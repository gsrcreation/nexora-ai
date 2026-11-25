# NEXORA AI

## Initial Data Dictionary

**Project:** Nexora AI – Retail Analytics
**Prepared By:** Yashvant Thakur
**Department:** AI/ML – Data Foundation
**Status:** Initial Draft

## 1. Introduction

The purpose of this document is to define the initial data requirements for the Nexora AI retail analytics project.

A retail business generates different types of data related to sales, customers, products, and inventory.

Understanding this data is important for data analysis, business intelligence, and machine learning model development.

This document identifies four major entities:

1. Sales
2. Customers
3. Products
4. Inventory

## 2. Sales Entity

Sales data stores information about customer transactions and purchases.

| Column Name    | Data Type | Description                  |
| -------------- | --------- | ---------------------------- |
| order_id       | String    | Unique order identifier      |
| order_date     | Date      | Date of transaction          |
| customer_id    | String    | Unique customer identifier   |
| product_id     | String    | Purchased product identifier |
| quantity       | Integer   | Number of units purchased    |
| unit_price     | Float     | Price of one product         |
| revenue        | Float     | Total revenue generated      |
| discount       | Float     | Discount applied             |
| payment_method | String    | Payment method               |
| sales_channel  | String    | Online or offline            |

## 3. Customers Entity

Customer data stores information about customers and their purchasing relationships with the business.

| Column Name      | Data Type | Description                   |
| ---------------- | --------- | ----------------------------- |
| customer_id      | String    | Unique customer identifier    |
| customer_name    | String    | Name of customer              |
| location         | String    | Customer location             |
| signup_date      | Date      | Registration date             |
| age              | Integer   | Customer age, if available    |
| gender           | String    | Customer gender, if available |
| email            | String    | Customer email                |
| customer_segment | String    | Customer category             |

## 4. Products Entity

Product data contains information about products sold by the business.

| Column Name  | Data Type | Description                         |
| ------------ | --------- | ----------------------------------- |
| product_id   | String    | Unique product identifier           |
| product_name | String    | Name of product                     |
| category     | String    | Product category                    |
| brand        | String    | Product brand                       |
| price        | Float     | Selling price                       |
| cost_price   | Float     | Product purchase or production cost |
| supplier_id  | String    | Supplier identifier                 |

## 5. Inventory Entity

Inventory data stores information about product availability and stock levels.

| Column Name        | Data Type | Description                |
| ------------------ | --------- | -------------------------- |
| inventory_id       | String    | Unique inventory record    |
| product_id         | String    | Related product identifier |
| stock_quantity     | Integer   | Available stock quantity   |
| reorder_level      | Integer   | Minimum stock threshold    |
| warehouse_location | String    | Warehouse location         |
| last_updated       | Date      | Last inventory update      |

## 6. Relationships Between Entities

* Sales and Customers are connected through customer_id.
* Sales and Products are connected through product_id.
* Products and Inventory are connected through product_id.

These relationships allow the business to combine different datasets for analysis.

## 7. Business Applications

The collected information can support:

* Sales performance analysis.
* Customer purchasing behavior analysis.
* Product performance analysis.
* Inventory management.
* Sales forecasting.
* Demand prediction.
* Customer segmentation.

## 8. Notes

* This is an initial data dictionary.
* Actual columns will be finalized after dataset inspection.
* Data types may change depending on the source dataset.
* Missing and duplicate values must be investigated.
* Customer information must be handled securely.

**Prepared by:** Yashvant Thakur
**Project:** Nexora AI
