# 🏗️ Data Warehouse SQL

A modern **SQL Server data warehouse** designed to demonstrate end-to-end data engineering practices, including **data source assessment, ETL pipelines, data integration, dimensional modeling, data quality, and analytics**.

The project follows a structured **Bronze → Silver → Gold** architecture to transform raw operational data into clean, analytics-ready datasets.

---

## 📌 Project Overview

This project demonstrates how a data warehouse can be designed and implemented using SQL Server, with a focus on:

* 🔄 ETL / ELT pipeline development
* 🗄️ Data warehouse architecture
* 🧩 Dimensional data modeling
* 🔍 Data source assessment
* 🧹 Data cleansing and transformation
* ✅ Data quality validation
* 📊 Analytics-ready datasets
* 📈 Business intelligence integration

---

## 🏛️ Architecture

The warehouse follows a layered architecture:

```text
                    ┌─────────────────────┐
                    │     Data Sources    │
                    │                     │
                    │ SQL Server          │
                    │ APIs                 │
                    │ CSV / Excel Files   │
                    │ External Systems    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Bronze Layer      │
                    │   Raw Data          │
                    │                     │
                    │ • Source-aligned    │
                    │ • Minimal changes   │
                    │ • Historical copy   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Silver Layer      │
                    │   Cleaned Data      │
                    │                     │
                    │ • Validation        │
                    │ • Standardization   │
                    │ • Deduplication     │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     Gold Layer      │
                    │ Business Data       │
                    │                     │
                    │ • Fact Tables       │
                    │ • Dimension Tables  │
                    │ • KPIs / Metrics    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Analytics & BI      │
                    │                     │
                    │ Power BI / SQL      │
                    │ Reports / Dashboards│
                    └─────────────────────┘
```

---

# 📋 Data Source Assessment & Onboarding

Before a source is connected to the warehouse, it goes through a structured **Data Source Assessment & Onboarding Checklist**.

The purpose is to understand the source's ownership, architecture, extraction capabilities, historical requirements, volume, and security constraints before pipeline development begins.

---

## 📊 Assessment Status

| Section                             |  Items |      Status     |
| :---------------------------------- | -----: | :-------------: |
| 🏢 Business Context & Ownership     |      4 |   ✅ Completed   |
| 🏗️ Architecture & Technology Stack |      2 |   ✅ Completed   |
| 🔄 Extract & Load                   |      6 |   ✅ Completed   |
| **Total**                           | **12** | **✅ Completed** |

---

## 1. 🏢 Business Context & Ownership

This section establishes **why the data exists, who owns it, and how it supports the business**.

| Assessment Area                 | Details / Technical Considerations                                       | Status |
| :------------------------------ | :----------------------------------------------------------------------- | :----: |
| **Data Ownership**              | Data owner, domain lead, business steward, responsible team              |    ✅   |
| **Business Process**            | Operational, transactional, financial, customer, or analytical workflows |    ✅   |
| **System & Data Documentation** | Data dictionaries, ER diagrams, architecture documentation               |    ✅   |
| **Data Model & Catalog**        | Schemas, tables, views, relationships, metadata, data catalog            |    ✅   |

### Key Questions

* Who is responsible for the source data?
* Which business process generates the data?
* What systems consume or depend on the data?
* Is documentation available?
* What are the key entities and relationships?
* Are business definitions and data ownership clearly established?

---

## 2. 🏗️ Architecture & Technology Stack

This section determines **where the data resides and how it can be accessed**.

| Assessment Area              | Details / Technical Considerations                               | Status |
| :--------------------------- | :--------------------------------------------------------------- | :----: |
| **Data Storage**             | SQL Server, Oracle, PostgreSQL, AWS, Azure, cloud storage, etc.  |    ✅   |
| **Integration Capabilities** | API, Kafka, SFTP, file extract, direct database connection, etc. |    ✅   |

### Key Questions

* Where is the source data physically or logically stored?
* What database or storage technology is being used?
* What connectivity options are available?
* Does the source provide APIs?
* Is direct database access permitted?
* Are file-based extracts supported?
* Are there network or firewall restrictions?

---

## 3. 🔄 Extract & Load

This section defines **how data will be extracted and loaded into the warehouse**.

| Assessment Area                    | Details / Technical Considerations                                 | Status |
| :--------------------------------- | :----------------------------------------------------------------- | :----: |
| **Load Strategy**                  | Full load, incremental load, CDC, timestamp-based delta loads      |    ✅   |
| **Data Scope & History**           | Historical depth, active records, backfill requirements            |    ✅   |
| **Extract Size**                   | Record counts, batch size, MB / GB / TB expectations               |    ✅   |
| **Volume Limitations**             | API limits, bandwidth, query timeouts, extraction restrictions     |    ✅   |
| **Source Performance Impact**      | Read replicas, throttling, scheduling, off-peak extraction         |    ✅   |
| **Authentication & Authorization** | IAM roles, service accounts, API tokens, VPN, SSH, IP whitelisting |    ✅   |

### Key Questions

* Should the initial load be a full snapshot?
* How will subsequent changes be identified?
* Does the source support Change Data Capture (CDC)?
* How much historical data is required?
* What is the expected daily/monthly data volume?
* Are there API or query limitations?
* When can extraction safely run?
* What authentication mechanism is required?

---

# 🔐 Data Security Considerations

Security requirements should be established before ingestion.

Key considerations include:

* 🔑 Authentication and authorization
* 👤 Service accounts and role-based access
* 🔒 Encryption in transit and at rest
* 🌐 IP whitelisting and VPN requirements
* 🛡️ Least-privilege database permissions
* 🚫 Protection of sensitive or confidential fields
* 📝 Audit logging and access monitoring
* 🔄 Credential rotation

---

# 🔄 ETL Pipeline

Once a source passes the onboarding assessment, it can be incorporated into the ETL pipeline.

```text
Source
   │
   ▼
Extract
   │
   ▼
Bronze
   │
   ▼
Transform
   │
   ▼
Silver
   │
   ▼
Validate
   │
   ▼
Gold
   │
   ▼
Analytics
```

### Pipeline Principles

* **Extract** data without unnecessarily impacting production systems.
* **Validate** incoming records and schema structures.
* **Transform** data into standardized formats.
* **Deduplicate** records where required.
* **Track** data quality and pipeline execution.
* **Load** analytics-ready dimensional models.
* **Monitor** failures and unexpected source changes.

---

# 🧩 Data Modeling

The Gold layer is designed for analytical workloads using dimensional modeling principles.

### Example Structure

```text
                 ┌──────────────────┐
                 │   DimCustomer    │
                 └────────┬─────────┘
                          │
                          │
┌──────────────────┐      │      ┌──────────────────┐
│   DimProduct     │──────┼──────│    DimDate       │
└──────────────────┘      │      └──────────────────┘
                          │
                          ▼
                 ┌──────────────────┐
                 │    FactSales     │
                 └──────────────────┘
                          │
                          │
                 ┌──────────────────┐
                 │   DimLocation    │
                 └──────────────────┘
```

### Typical Warehouse Objects

**Fact Tables**

* `FactSales`
* `FactOrders`
* `FactTransactions`

**Dimension Tables**

* `DimCustomer`
* `DimProduct`
* `DimDate`
* `DimLocation`
* `DimEmployee`

---

# 🧹 Data Quality

Data quality checks are incorporated throughout the pipeline.

| Check                     | Purpose                               |
| :------------------------ | :------------------------------------ |
| **Null Validation**       | Identify missing required values      |
| **Duplicate Detection**   | Prevent duplicate business records    |
| **Referential Integrity** | Validate fact/dimension relationships |
| **Data Type Validation**  | Ensure values match expected types    |
| **Range Validation**      | Detect invalid numerical/date values  |
| **Schema Validation**     | Identify unexpected source changes    |
| **Record Count Checks**   | Compare source and target volumes     |
| **Load Reconciliation**   | Confirm successful data movement      |

---

# 🛠️ Technology Stack

| Technology               | Purpose                                     |
| :----------------------- | :------------------------------------------ |
| **Microsoft SQL Server** | Database & warehouse platform               |
| **T-SQL**                | Data transformation & warehouse development |
| **Python**               | Data processing, validation & automation    |
| **Pandas**               | Data manipulation and quality analysis      |
| **Power BI**             | Business intelligence & visualization       |
| **Excel**                | Data inspection and validation              |
| **Git / GitHub**         | Version control & project management        |

---

# 📁 Project Structure

```text
Data_warehouse_SQL/
│
├── datasets/
│   ├── raw/
│   └── processed/
│
├── docs/
│   ├── data_source_assessment.md
│   ├── architecture.md
│   └── data_dictionary.md
│
├── scripts/
│   ├── bronze/
│   ├── silver/
│   └── gold/
│
├── sql/
│   ├── database/
│   ├── staging/
│   ├── transformations/
│   └── analytics/
│
├── tests/
│   └── data_quality/
│
├── dashboards/
│   └── powerbi/
│
└── README.md
```

---

# 🚀 Implementation Workflow

The recommended development workflow is:

```text
01. Assess Data Source
          ↓
02. Document Business Requirements
          ↓
03. Analyze Source Architecture
          ↓
04. Define Extraction Strategy
          ↓
05. Build Bronze Layer
          ↓
06. Clean & Transform → Silver
          ↓
07. Apply Data Quality Checks
          ↓
08. Build Dimensional Model → Gold
          ↓
09. Create Analytical Views
          ↓
10. Connect Power BI / BI Tools
          ↓
11. Monitor & Maintain Pipeline
```

---

# ✅ Data Source Onboarding Checklist

### Business Context & Ownership

* [x] Identify data owner
* [x] Identify business process
* [x] Review system documentation
* [x] Review data model and catalog

### Architecture & Technology

* [x] Identify storage technology
* [x] Identify integration/connectivity options

### Extract & Load

* [x] Define full vs incremental load
* [x] Define historical requirements
* [x] Estimate extraction size
* [x] Identify volume limitations
* [x] Define source-performance safeguards
* [x] Define authentication and authorization

---

# 📈 Analytics & Reporting

The final warehouse layer provides structured datasets that can support:

* Sales analysis
* Customer analytics
* Product performance
* Revenue reporting
* Operational KPIs
* Trend analysis
* Management dashboards
* Ad-hoc SQL analysis

---

# 🎯 Project Goals

The project demonstrates practical understanding of:

* Data warehouse architecture
* ETL/ELT development
* SQL Server
* T-SQL
* Data integration
* Data modeling
* Data quality
* Incremental data loading
* Source-system assessment
* Business intelligence
* Analytics engineering

---

## 📌 Data Source Assessment Principle

> **A data source should be understood before it is engineered.**

This checklist is designed to be completed **once per data source before development and Bronze-layer ingestion**, ensuring that ownership, architecture, extraction requirements, security, historical needs, and operational constraints are understood before the pipeline is built.

---

## 👨‍💻 Project Status

**Status:** 🟢 Active Development

**Primary Platform:** Microsoft SQL Server

**Architecture:** Bronze → Silver → Gold

**Focus:** Data Engineering & Analytics
