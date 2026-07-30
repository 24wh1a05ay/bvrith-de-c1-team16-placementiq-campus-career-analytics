# Week 03 Log — [Sprint Name]

**Week:** 3  
**Date range:** 24/07/2026 - 31/07/2026  
**Team:** 16    


**Project:** PlacementIQ – Campus Career Analytics

---

## 1. Sprint Goal

Profile and understand the PlacementIQ source datasets before building the Bronze layer. Explore schemas, validate data quality, identify business keys, analyze relationships between datasets, and document findings to ensure the data is ready for Bronze ingestion in Week 04.

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
| Loaded students.json| Bharani | Done | 01_data_exploration.ipynb |
| Loaded companies.csv | 	Bharani	|   Done |	Notebook |
| Loaded skills.csv |	 Bharani | Done | Notebook |
| Loaded interviews.parquet |	 Bharani	| Done |Notebook |
| Verified schemas and data types | Chandana 	| Done | Spark printSchema() output |
| Calculated row counts and distinct keys | Chandana | Done | SQL queries |
| Performed missing value analysis | Chandana  | Done | Notebook |
| Verified dataset relationships | Chandana | Done | SQL joins |
| Identified business keys and grains|  Chandana  | Done | Documentation |
| Created temporary SQL views | Chandana | Done | Notebook |
---

## 3. Key Decisions
- Selected student_id, company_id, skill_id, and interview_id as the primary business keys for profiling.
- Decided to complete all data profiling and relationship validation before starting the Bronze layer implementation

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
| Nested JSON structure in students.json | Required additional schema exploration | Used Spark schema inspection and documentation |
| Multiple interview versions in Parquet data | | Required careful understanding of interview records | | Verified using profiling queries |
---

## 5. Evidence Added to GitHub

Updated 01_data_exploration.ipynb
Added schema screenshots
Added SQL profiling queries
Added relationship validation results
Added data quality analysis outputs
Committed Week 03 notebook and documentation

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI assisted in structuring the notebook, suggesting Spark SQL queries, markdown documentation, and profiling steps. |
| What we changed after AI suggestion | Updated SQL queries, adapted explanations to the PlacementIQ project, and modified notebook sections to match project requirements. |
| What we verified manually | Verified schema, row counts, relationships, joins, missing values, and query outputs directly in Databricks. |
| What we can explain without AI | Dataset structure, Spark SQL queries, business keys, relationship analysis, profiling process, and Week 03 implementation decisions. |

---

## 7. Next Week Preparation

- Build the Bronze layer by ingesting all source datasets into Delta tables.
- Add metadata columns, data lineage, and validation checks for Bronze tables.
- Prepare source-to-Bronze reconciliation for Week 04.
- Commit Bronze implementation and evidence to GitHub.
