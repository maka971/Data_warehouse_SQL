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
