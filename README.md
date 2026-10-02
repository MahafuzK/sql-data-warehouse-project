
# SQL Data Warehouse & ETL Pipeline

An end-to-end SQL Data Warehouse project built using **Microsoft SQL Server** and **T-SQL**.  
The project demonstrates how raw CRM and ERP datasets can be transformed into a clean, analytics-ready data warehouse using a **Medallion Architecture**.

## 📌 Project Overview

This project builds a data warehouse from raw CSV datasets representing CRM and ERP source systems.

The pipeline follows three layers:

**Bronze → Silver → Gold**

- **Bronze:** Raw data loaded from source CSV files with minimal transformation.
- **Silver:** Data cleaning, validation, standardization, deduplication, and transformation.
- **Gold:** Business-ready dimensional models designed using a **Star Schema** for analytics and reporting.

## 🏗️ Architecture

```text
                Source Systems
              ┌───────────────┐
              │   CRM Data    │
              │   ERP Data    │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │    BRONZE     │
              │  Raw Data     │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │    SILVER     │
              │ Cleaned Data  │
              │ Validated     │
              │ Standardized  │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │     GOLD      │
              │ Star Schema   │
              └───────┬───────┘
                      │
          ┌───────────┴───────────┐
          ▼                       ▼
   dim_customers            dim_products
          \                       /
           \                     /
            └──── fact_sales ────┘
