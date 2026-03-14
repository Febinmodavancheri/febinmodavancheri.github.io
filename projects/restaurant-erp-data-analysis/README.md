
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

## Database Domains Identified

During exploration, the ERP database was organised into the following functional domains:

**Sales / POS**

* tickets
* ticketlines
* receipts
* payments
* taxlines

**Product / Menu**

* products
* menu configuration tables

**Inventory**

* stockdiary
* stock movement tables

**Customer / Delivery**

* customers
* customer_address

**Finance**

* tax-related tables
* financial transaction records

**System Configuration**

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

## Example SQL Exploration

Example queries used during database exploration:

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

## Future Work

* Create an entity relationship diagram (ERD) of key tables
* Map operational tables to fact and dimension tables
* Design a conceptual star schema for analytical reporting
* Develop sample SQL queries for business reporting (sales, product performance, customer activity)
