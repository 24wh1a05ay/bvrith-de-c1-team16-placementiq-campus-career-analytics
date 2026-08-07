# Week 05 Log — [Sprint Name]

**Week:** 5  
**Date range:** 7/8/2026 - 14/8/2026  
**Team:** 16 
**Project:** PlacementIQ-Campus Career Analytics

---

## 1. Sprint Goal

The goal for Week 5 was to transform the Bronze-layer data into clean and structured Silver-layer candidate data. The focus was on data cleaning, schema validation, handling missing values, removing duplicates, and preparing the data for further analytics.
 | 
---

## 2. Work Completed

| Inspected Bronze tables and schemas | Bharani | Done | Databricks notebook | 

| Checked record counts and data quality | Bharani | Done | Data exploration notebook | 

| Identified missing and duplicate records | Bharani | one | Silver transformation notebook |

| Cleaned and standardized candidate data | Bharani | Done | Silver candidate notebook |

| Converted Bronze data into Silver-ready format | Bharani | Done | Silver tables |

| Validated Silver table schema and records | Bharani | Done| Databricks screenshots |

| Updated project documentation | Bharani | Done | GitHub Week 05 log |

---

## 3. Key Decisions

- Used the Bronze tables as the source for creating the Silver-layer data.
- Standardized column names and data types during transformation.
- Handled missing and duplicate records before creating Silver tables.
- Kept the Silver layer clean and structured for future analytics and Gold-layer processing.
- Used Databricks notebooks and SQL/PySpark transformations for the data-processing workflow.
---

## 4. Blockers / Risks
| Some Bronze data required cleaning and standardization | Could affect Silver-layer quality | Validate transformation rules |

| Missing values in some columns | May affect downstream analysis | Apply suitable null-handling rules | 

| Different data types/formats across source files | Could cause transformation errors | Schema validation and casting | 

| Need to verify Silver tables against source data | Risk of losing or changing records incorrectly | Perform record-count and sample validation |


---

## 5. Evidence Added to GitHub
- Week 05 sprint log
- Silver-layer transformation notebook
- Updated Databricks notebook
- Screenshots of Bronze and Silver tables
- Silver table schema and record-count validation
- Data-cleaning and transformation queries

---

## 6. AI Transparency Note
| Where AI helped | AI was used to understand the Bronze-to-Silver transformation process, suggest SQL/PySpark approaches, and help troubleshoot transformation errors.|

| What we verified manually | We manually checked schemas, record counts, null values, duplicate records, data types, and sample records after transformation.|

| What we can explain without AI | We can explain the purpose of Bronze and Silver layers, data cleaning, schema validation, null handling, duplicate removal, and the overall ETL transformation process.|

---

## 7. Next Week Preparation
- Validate the completed Silver-layer tables in detail.
- Start preparing the cleaned Silver data for Gold-layer transformations and analytics.
- Identify the key metrics and business requirements needed for the Gold layer.
- Document the transformation rules and data-quality checks.
