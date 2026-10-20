
# SQL Data Warehouse & Analytics Project

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A modern Data Warehouse built with SQL Server, including ETL processes, data cleansing, star schema data modeling, and analytics queries.

---

## 📌 Overview

This project implements an end-to-end Data Warehouse solution using SQL Server. It ingests raw CSV datasets from two disparate source systems (CRM and ERP), cleanses and transforms the data through a multi-layer pipeline, models it into a Star Schema, and delivers business-ready views for analytics and reporting.

### Key Objectives
* **Data Engineering:** Build ETL pipelines using T-SQL procedures to move data through Bronze, Silver, and Gold layers.
* **Data Cleansing & Quality:** Resolve duplicates, handle missing values, standardize codes, and enforce referential integrity.
* **Data Modeling:** Construct a dimensional Star Schema (Fact & Dimension tables) optimized for analytical reporting.
* **Data Analytics:** Write SQL analytical queries to extract actionable insights on Customer Behavior, Product Performance, and Sales Trends.

---

## 🏗️ Data Architecture

The architecture follows the **Medallion Architecture** pattern:


```

┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐      ┌─────────────────┐
│  Source Systems │ ───► │  Bronze Layer   │ ───► │  Silver Layer   │ ───► │   Gold Layer    │
│   (CRM & ERP)   │      │   (Raw Ingestion)│      │  (Cleaned/Trans)│      │  (Star Schema)  │
└─────────────────┘      └─────────────────┘      └─────────────────┘      └─────────────────┘

```

1. **Bronze Layer:** Ingests raw CSV data as-is from CRM and ERP source systems into SQL Server staging tables without modification.
2. **Silver Layer:** Handles data scrubbing, normalization, type conversions, and data quality validations.
3. **Gold Layer:** Exposes business-ready dimensional models (Star Schema) with facts and dimensions for BI tools and ad-hoc analytical queries.

---

## 📁 Repository Structure

```text
sql-data-warehouse-project/
├── datasets/            # Source CSV files from CRM and ERP systems
│   ├── source_crm/      # CRM exports (cust_info, prd_info, sales_details)
│   └── source_erp/      # ERP exports (CUST_AZ12, LOC_A101, PX_CAT_G1V2)
├── docs/                # Project specifications, requirements, and architecture diagrams
│   └── requirements.md  # Detailed business and technical requirements
├── scripts/             # T-SQL DDL and ETL stored procedures
│   ├── bronze/          # DDL and ingestion procedures for Bronze layer
│   ├── silver/          # Cleansing, transformation, and load scripts for Silver layer
│   └── gold/            # Dimensional modeling and view definitions for Gold layer
├── tests/               # Quality check scripts and validation queries
├── LICENSE              # Project license (MIT)
└── README.md            # Project documentation

```

---

## 🚀 Getting Started

### Prerequisites

* **Database Engine:** Microsoft SQL Server (2019 or later recommended) or SQL Server in Docker.
* **Management Tool:** SQL Server Management Studio (SSMS) or Azure Data Studio.

### Installation & Execution

1. **Clone the repository:**
```bash
git clone [https://github.com/AsamaeS/sql-data-warehouse-project.git](https://github.com/AsamaeS/sql-data-warehouse-project.git)

```


2. **Database Initialization:**
Execute the database initialization scripts located in `scripts/` to set up schemas (`bronze`, `silver`, `gold`).
3. **Data Ingestion (Bronze):**
Run the Bronze stored procedures in `scripts/bronze/` to load the CSV source files into staging tables.
4. **Data Transformation (Silver):**
Execute the Silver transformation scripts in `scripts/silver/` to clean and standardize the data.
5. **Dimensional Load (Gold):**
Run the Gold scripts in `scripts/gold/` to populate the dimension and fact views.
6. **Data Verification:**
Run the test scripts in `tests/` to verify data integrity and run quality check suites.

---

## 📊 Analytics & Reporting

The Data Warehouse answers key business questions across several domains:

* **Customer Behavior:** Segmentation, purchase history, and demographics analysis.
* **Product Performance:** Sales volume, revenue drivers, and product category analysis.
* **Sales Trends:** Period-over-period growth, regional performance, and transaction patterns.

For detailed specification details, check `docs/requirements.md`.

---

## 🛡️ License

This project is licensed under the MIT License.

---

---

## 👥 Acknowledgments & Credits

* Project design and structure inspired by [Baraa Khatib Salkini](https://github.com/baratali) / **Data With Baraa**.

---

## 👩‍💻 Author

**Asmae SERJI**
* GitHub: [@AsamaeS](https://github.com/AsamaeS)

```

```
