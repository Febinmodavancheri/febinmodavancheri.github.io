
# Restaurant ERP Data Analysis

## Overview

This project explores the structure of a restaurant ERP database to understand how operational data such as sales transactions, payments, inventory movements, and customer information are stored and connected.

The goal of this analysis is to identify key data entities and relationships that support restaurant operations and to prepare a foundation for future analytics and data warehouse design.

## Objectives

* Explore the structure of a real-world ERP database
* Understand how restaurant transactions are recorded
* Identify key operational domains such as sales, inventory, and customers
* Map transactional tables for analytical reporting and data warehouse design

## Database Domains Identified

During exploration, the database was organised into functional domains:

* **Sales / POS** – ticket transactions, receipts, and payments
* **Product / Menu** – menu items and product definitions
* **Inventory** – stock movements and item tracking
* **Procurement** – purchasing and supplier interactions
* **Customer / Delivery** – customer information and delivery details
* **Finance** – tax and financial records
* **System Configuration** – system-level configuration tables

## Example Transaction Flow

A typical restaurant sales transaction involves multiple tables:

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

This structure captures the full lifecycle of a sale from order creation to payment processing and tax calculation.

## Tools Used

* MySQL
* SQL
* MySQL Workbench

## Skills Demonstrated

* Database exploration
* SQL analysis
* Understanding relational database structures
* Mapping transactional systems for analytics
* Data architecture thinking
