
# NEXORA AI - Database Schema

## Database Technology
PostgreSQL

## 1. Customers
- customer_id: BIGINT (Primary Key)
- customer_name: VARCHAR(150)
- location: VARCHAR(100)
- signup_date: DATE

## 2. Products
- product_id: BIGINT (Primary Key)
- product_name: VARCHAR(200)
- category: VARCHAR(100)
- price: NUMERIC(12,2)

## 3. Orders
- order_id: BIGINT (Primary Key)
- customer_id: BIGINT (Foreign Key)
- order_date: TIMESTAMP
- order_status: VARCHAR(50)

## 4. Order Items
- order_item_id: BIGINT (Primary Key)
- order_id: BIGINT (Foreign Key)
- product_id: BIGINT (Foreign Key)
- quantity: INTEGER
- unit_price: NUMERIC(12,2)

## 5. Inventory
- inventory_id: BIGINT (Primary Key)
- product_id: BIGINT (Foreign Key)
- stock_quantity: INTEGER
- last_updated: TIMESTAMP

## 6. Ingestion Logs
- ingestion_id: BIGINT (Primary Key)
- source_name: VARCHAR(255)
- ingestion_time: TIMESTAMP
- records_received: INTEGER
- records_loaded: INTEGER
- ingestion_status: VARCHAR(30)

## Relationships

- Customers → Orders: One-to-Many
- Orders → Order Items: One-to-Many
- Products → Order Items: One-to-Many
- Products → Inventory: One-to-Many

## Notes

This is an initial logical schema.
Final fields and relationships will be revised
after selecting and inspecting the actual dataset.
