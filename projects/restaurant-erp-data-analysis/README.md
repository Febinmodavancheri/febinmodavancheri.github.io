# Restaurant ERP Data Analysis

## Overview

This project explores the structure and transactional data flow of a restaurant ERP system. The goal of the analysis is to understand how operational data such as sales transactions, payments, inventory movements, and customer records are stored and related within the database.

The project focuses on identifying key data entities and relationships that support restaurant operations and preparing a foundation for analytical reporting and future data warehouse design.

---

## Objectives

* Explore the schema of a real-world ERP database
* Understand how restaurant sales transactions are recorded
* Identify key operational domains such as sales, inventory, and customer management
* Trace transaction flow across multiple relational tables
* Prepare a conceptual foundation for analytics and data warehouse architecture

---

## Example Business Questions

Using the ERP transactional data, several analytical questions can be explored:

* What are the top-selling menu items across restaurants?
* What is the daily or monthly sales trend?
* Which payment methods are most commonly used?
* What are the busiest hours for restaurant transactions?
* How does product performance vary across different locations?

These questions illustrate how operational ERP data can be transformed into insights that support restaurant management and business decision-making.

---

## Database Domains Identified

During exploration, the ERP database was organised into the following functional domains.

### Sales / POS

* tickets
* ticketlines
* receipts
* payments
* taxlines

### Product / Menu

* products
* menu configuration tables

### Inventory

* stockdiary
* stock movement tables

### Customer / Delivery

* customers
* customer_address

### Finance

* tax-related tables
* financial transaction records

### System Configuration

* application configuration tables
* user and system settings

---

## Transaction Flow Analysis

A typical restaurant transaction involves multiple tables working together to record the complete lifecycle of a sale.

Example flow:

```
tickets
   ↓
ticketlines
   ↓
receipts
   ↓
payments
   ↓
taxlines
```

This structure allows the ERP system to capture detailed transactional information including order items, payment methods, and tax calculations.

---

## Data Relationship Overview

During exploration, key relationships between transactional tables were identified to understand how restaurant sales are recorded in the ERP system.

### Core Transaction Tables

```
tickets
   │
   ├── ticketlines
   │        │
   │        └── products
   │
   └── receipts
            │
            ├── payments
            │
            └── taxlines
```

### Explanation

* **tickets** represent a customer order created in the POS system.
* **ticketlines** contain individual items ordered in the ticket.
* **products** store the menu item definitions linked to ticket lines.
* **receipts** record the finalized sale transaction.
* **payments** capture how the transaction was paid (cash, card, etc.).
* **taxlines** store tax calculations applied to the sale.

This structure allows the ERP system to maintain a detailed record of each restaurant transaction from order creation through payment and tax calculation.

---

## Example SQL Exploration

Example queries used during database exploration.

Retrieve recent receipt transactions:

```sql
SELECT *
FROM receipts
ORDER BY id DESC
LIMIT 10;
```

Inspect ticket line items:

```sql
SELECT *
FROM ticketlines
LIMIT 20;
```

These queries were used to understand how transactional data is stored and how different tables relate to each other within the POS system.

---

## Sample Analytics Queries

The following example queries demonstrate how transactional ERP data can be analysed to generate business insights.

### Top Selling Products

Identify the most frequently sold menu items based on ticket line records.

```sql
SELECT product_id, COUNT(*) AS items_sold
FROM ticketlines
GROUP BY product_id
ORDER BY items_sold DESC
LIMIT 10;
```

### Daily Sales Activity

Estimate daily transaction volume using receipt records.

```sql
SELECT DATE(created) AS sale_date, COUNT(*) AS transactions
FROM receipts
GROUP BY sale_date
ORDER BY sale_date DESC;
```

### Payment Method Usage

Analyse how customers pay for their orders.

```sql
SELECT payment_type, COUNT(*) AS usage_count
FROM payments
GROUP BY payment_type
ORDER BY usage_count DESC;
```

### Product Sales Distribution

Understand how product sales are distributed across the menu.

```sql
SELECT product_id, SUM(quantity) AS total_quantity
FROM ticketlines
GROUP BY product_id
ORDER BY total_quantity DESC;
```

These queries demonstrate how operational ERP data can be transformed into meaningful analytical insights such as product performance, sales trends, and payment behaviour.

---

## Tools Used

* MySQL
* SQL
* MySQL Workbench

---

## Skills Demonstrated

* Relational database exploration
* SQL-based data analysis
* Understanding transactional system design
* Mapping operational databases for analytics
* Conceptual thinking for data warehouse architecture

---

## Potential Data Warehouse Model

Based on the exploration of the ERP database, the transactional structure can be transformed into a simplified analytical model for reporting and business intelligence.

### Fact Table

**FactSales**

This table would store transactional sales records and key numerical metrics such as:

* Total sales amount
* Quantity sold
* Tax amount
* Payment value

### Dimension Tables

**DimProduct**

* Product ID
* Product name
* Category
* Menu grouping

**DimCustomer**

* Customer ID
* Customer attributes

**DimRestaurant**

* Restaurant / outlet identifier

**DimDate**

* Date
* Month
* Year
* Day of week

### Conceptual Star Schema

```
            DimProduct
                │
                │
DimDate ─── FactSales ─── DimRestaurant
                │
                │
           DimCustomer
```

This structure simplifies analytical queries and enables efficient reporting such as:

* Daily sales trends
* Product performance analysis
* Customer purchasing patterns
* Restaurant-level performance metrics

---

## Potential Dashboard Metrics

Based on the explored ERP transactional structure, the following metrics could be visualised in a business intelligence dashboard.

### Sales Performance

* Total daily sales
* Monthly revenue trends
* Average transaction value

### Product Performance

* Top-selling menu items
* Least-performing products
* Product category sales distribution

### Operational Insights

* Peak transaction hours
* Number of daily orders
* Sales performance by restaurant location

### Payment Analysis

* Payment method distribution (cash, card, digital)
* Transaction success rates
* Average payment per order

These metrics could be implemented in a BI tool such as **Microsoft Power BI** to create interactive dashboards that help restaurant managers monitor performance and make data-driven decisions.

---

## Future Work

* Create an entity relationship diagram (ERD) of key tables
* Map operational tables to fact and dimension tables
* Design a conceptual star schema for analytical reporting
* Develop sample SQL queries for business reporting (sales, product performance, customer activity)
