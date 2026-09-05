# Data_warehouse_SQL
A modern data warehouse built with SQL Server, featuring ETL pipelines, data modeling, data integration, and analytics to transform raw data into actionable insights.
# Data Source Assessment & Onboarding Checklist

A structured checklist used to evaluate and document a data source before onboarding it into the pipeline — covering business context, architecture, and extract/load requirements.

## 📋 Status Overview

| Section | Items | Status |
|---|---|---|
| Business Context & Ownership | 4 | ✅ Completed |
| Architecture & Technology Stack | 2 | ✅ Completed |
| Extract & Load | 6 | ✅ Completed |

---

## 1. Business Context & Ownership

| Question | Details / Technical Options | Status |
|---|---|---|
| Who owns the data? | Data owner, domain lead, and business stewards | ✅ Completed |
| What business process does it support? | Core operational, transactional, or analytics workflows | ✅ Completed |
| System & data documentation | Data dictionaries, ER diagrams, architecture specs | ✅ Completed |
| Data model & data catalog | Schema design, tables/views, data catalog registry | ✅ Completed |

## 2. Architecture & Technology Stack

| Question | Details / Technical Options | Status |
|---|---|---|
| How is data stored? | SQL Server, Oracle, AWS, Azure, PostgreSQL, etc. | ✅ Completed |
| What are the integration capabilities? | API, Kafka, file extract, direct DB connection, etc. | ✅ Completed |

## 3. Extract & Load

| Question | Details / Technical Options | Status |
|---|---|---|
| Incremental vs. full loads? | Initial snapshot vs. change data capture (CDC) / delta loads | ✅ Completed |
| Data scope & historical needs | Historical depth, backfill requirements, active data range | ✅ Completed |
| Expected size of extracts | Batch payload size, record counts, expected MB/GB/TB | ✅ Completed |
| Data volume limitations | Bandwidth caps, query timeouts, source extraction limits | ✅ Completed |
| Avoiding source system performance impact | Read replicas, off-peak execution windows, rate throttling | ✅ Completed |
| Authentication and authorization | Tokens, SSH keys, VPN, IP whitelisting, IAM roles | ✅ Completed |

---

*This checklist is intended to be run once per data source before development begins, ensuring ownership, architecture, and extraction constraints are understood ahead of pipeline design.*

<div align="center">

# 📋 Data Source Assessment & Onboarding Checklist

*A pre-ingestion due-diligence checklist for evaluating new data sources before they enter the warehouse.*

![Show Image](https://via.placeholder.com/900x250?text=Banner+Image+Here)

![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Sections](https://img.shields.io/badge/Sections-3-blue?style=for-the-badge)
![Items](https://img.shields.io/badge/Checklist_Items-12-informational?style=for-the-badge)

</div>

---

## 🗂️ Overview

<div align="center">

| 🧩 Section | 📌 Items | ✅ Status |
|:---|:---:|:---:|
| **Business Context & Ownership** | 4 | ![done](https://img.shields.io/badge/-Completed-brightgreen) |
| **Architecture & Technology Stack** | 2 | ![done](https://img.shields.io/badge/-Completed-brightgreen) |
| **Extract & Load** | 6 | ![done](https://img.shields.io/badge/-Completed-brightgreen) |

</div>

---

## 1️⃣ Business Context & Ownership

![Show Image](https://via.placeholder.com/900x180?text=Business+Context+%26+Ownership+Diagram)

<details open>
<summary><strong>Expand section</strong></summary>

| Question | Details / Technical Options | Status |
|---|---|:---:|
| Who owns the data? | Data owner, domain lead, and business stewards | ✅ |
| What business process does it support? | Core operational, transactional, or analytics workflows | ✅ |
| System & data documentation | Data dictionaries, ER diagrams, architecture specs | ✅ |
| Data model & data catalog | Schema design, tables/views, data catalog registry | ✅ |

</details>

---

## 2️⃣ Architecture & Technology Stack

![Show Image](https://via.placeholder.com/900x180?text=Architecture+%26+Tech+Stack+Diagram)

<details open>
<summary><strong>Expand section</strong></summary>

| Question | Details / Technical Options | Status |
|---|---|:---:|
| How is data stored? | SQL Server, Oracle, AWS, Azure, PostgreSQL, etc. | ✅ |
| What are the integration capabilities? | API, Kafka, file extract, direct DB connection, etc. | ✅ |

</details>

---

## 3️⃣ Extract & Load

![Show Image](https://via.placeholder.com/900x180?text=Extract+%26+Load+Flow+Diagram)

<details open>
<summary><strong>Expand section</strong></summary>

| Question | Details / Technical Options | Status |
|---|---|:---:|
| Incremental vs. full loads? | Initial snapshot vs. change data capture (CDC) / delta loads | ✅ |
| Data scope & historical needs | Historical depth, backfill requirements, active data range | ✅ |
| Expected size of extracts | Batch payload size, record counts, expected MB/GB/TB | ✅ |
| Data volume limitations | Bandwidth caps, query timeouts, source extraction limits | ✅ |
| Avoiding source system performance impact | Read replicas, off-peak execution windows, rate throttling | ✅ |
| Authentication and authorization | Tokens, SSH keys, VPN, IP whitelisting, IAM roles | ✅ |

</details>

---

<div align="center">

📌 *Run this checklist once per data source, prior to Bronze-layer ingestion, to confirm the source is well-understood and safe to extract from.*

</div>
