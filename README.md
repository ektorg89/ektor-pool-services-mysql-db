# Ektor Pool Services — MySQL Database System

## Overview

This repository contains a **portfolio-grade MySQL relational database** that models the core operations of a pool maintenance business: customers, properties, pools, service visits, services performed, weekly invoicing, invoice line items, and payments. The focus of this project is **database design** (normalization, referential integrity, indexing, and business-driven modeling) — **no application/UI layer is included**.

---

## Business Rules Modeled

- A customer can own **multiple properties**
- Each property can have **one or more pools**
- Pools receive **scheduled maintenance visits**
- Each visit can include **multiple services**
- Services are charged **per pool**
- Invoices are generated **weekly per property**
- Invoice totals are calculated from completed visits
- Payments are tracked independently from invoices
- Partial and full payments are supported

---

## Database Entities

- `customers`
- `properties`
- `pools`
- `technicians`
- `service_catalog`
- `visits`
- `visit_services`
- `invoices`
- `invoice_lines`
- `payments`

---

## ERD (Entity Relationship Diagram)

If included in this repo, the ERD can be found here:

![ERD](ERD.png)

---

## Repository Structure

```
sql/
  01_schema.sql
  02_seed.sql
  03_queries.sql

docs/
  ERD.png
```

---

## Quick Start (Run Order)

Run these files in order:

```sql
Create schema
SOURCE sql/01_schema.sql;

Insert sample data
SOURCE sql/02_seed.sql;

Run example queries
SOURCE sql/03_queries.sql;
```

Note: 01_schema.sql defines the default database name as Ektor_Pool_Services. If you want a different database name, change it at the top of 01_schema.sql before running.

---

## What Each SQL File Does

- 01_schema.sql — Creates the database schema (tables, constraints, foreign keys, indexes)

- 02_seed.sql — Inserts fictional sample data (customers, properties, pools, visits, services, invoices, payments)

- 03_queries.sql — Provides example queries for reporting/validation (billing, breakdowns, revenue, payment status)

---

## Design Highlights

- Normalized schema with meaningful relationships and enforced integrity via foreign keys

- Weekly billing model based on completed visits

- Per-pool pricing captured through visit service quantities

- Invoice + line-item structure suitable for real-world billing

- Payments separated from invoices to support partial payments and tracking

- Indexes included to support common operational queries

---

## Disclaimer

All names, addresses, phone numbers, and email addresses in the seed data are fictional and used only for testing and portfolio demonstration.

---

## Author

Ektor M. Gonzalez — Puerto Rico


Created as a personal portfolio project to demonstrate SQL and relational database design skills using a realistic business scenario. This project focuses exclusively on the database layer.
