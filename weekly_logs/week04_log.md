# Week 04 Log — Bronze Layer Data Ingestion

**Week:** 4  
**Date range:** 31/07/2026 – 07/08/2026  
**Team:** 16  
**Project:** PlacementIQ-Campus Career Analytics

---

## 1. Sprint Goal

The goal of this sprint was to ingest the four batch data files into the Bronze layer of the data pipeline. We focused on loading the raw datasets without transformation, preserving the original data for further processing in the Silver layer.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Collected and verified four batch data files | Team 16 | Done | Source files |
| Created Bronze tables for all four batch files | Team 16 | Done | SQL notebook / PySpark notebook |
| Loaded raw batch data into Bronze tables | Team 16 | Done | Notebook output |
| Validated successful data ingestion | Team 16 | Done | Query results / screenshots |
| Verified record counts for each Bronze table | Team 16 | Done | SQL query output |

---

## 3. Key Decisions

- Stored all incoming batch files in the Bronze layer without applying transformations.
- Maintained the original schema and raw data to ensure traceability and data lineage.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Schema mismatch between some batch files | Data loading errors | Updated schema mapping before ingestion |
| Missing values in source files | May affect downstream processing | Will handle data cleaning in the Silver layer |

---

## 5. Evidence Added to GitHub

- Added Bronze table creation notebook.
- Uploaded batch ingestion scripts.
- Added screenshots of Bronze tables.
- Updated project documentation with Week 4 progress.

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted in generating SQL/PySpark code for creating Bronze tables and loading batch files. |
| What we changed after AI suggestion | Adjusted the table schema and file paths to match the project requirements. |
| What we verified manually | Verified successful data loading, record counts, and table structure using SQL queries. |
| What we can explain without AI | Bronze layer architecture, batch data ingestion process, table creation, and validation of loaded data. |

---

## 7. Next Week Preparation

- Clean and transform Bronze data into Silver tables.
- Apply data validation and quality checks.
- Remove duplicates and standardize data formats.
- Begin feature engineering for analytics.
