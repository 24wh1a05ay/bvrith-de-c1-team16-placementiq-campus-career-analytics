# Week 07 Log — Gold Aggregation

**Week:** 7  

**Date range:** 31/8/26 - 6/9/26

**Team:** 16  

**Project:** PlacementsIQ - Career Campus Analytics

---

## 1. Sprint Goal

Build the Gold layer from the Week 6 Trusted Silver data by defining business KPIs and creating validated, business-ready Gold tables.

The sprint focuses on implementing 8 Gold tables, with one KPI per table, and validating the results for correctness and repeat-run consistency

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
|Reviewed Week 6 Trusted Silver and DQ outputs|	Bharani|	Done|	Week 6 DQ notebook / screenshots|
|Defined Gold KPI contract	|bharani|	Done|	Gold design notebook|
|Created Trusted application view by exploding nested applications|	Bharani|	Done|	Week 7 Gold SQL notebook|
|Created Trusted offer view by exploding nested offers	|Bharani|Done	|Week 7 Gold SQL notebook|
|Created Trusted interview view	|Bharani	|Done|	Week 7 Gold SQL notebook|
|Created gold_total_applications|	Bharani	|Done|	Week 7 Gold notebook|
|Created gold_shortlisted_applications	|Chandana	|Done	|Week 7 Gold notebook|
|Created gold_total_interviews	|chandana|	Done|	Week 7 Gold notebook|
|Created gold_completed_interviews	|chandana	|Done|	Week 7 Gold notebook|
|Created gold_selected_candidates	|chandana|	Done|	Week 7 Gold notebook|
|Created gold_accepted_offers	|chandana|Done	|Week 7 Gold notebook|
|Created gold_joined_candidates|	chandana|Done|	Week 7 Gold notebook|
|Created gold_average_compensation_lpa	|chandana	|Done	|Week 7 Gold notebook|
|Validated KPI relationships and non-negative measures|	chandana	|Done|	Gold validation SQL|
|Prepared consolidated KPI output for verification|	chandana|	Done	|Week 7 Gold notebook|



Gold KPI Tables
|KPI Key	|Gold Table|	KPI|
|KPI-001	|gold_total_applications	|Total Applications|
|KPI-002	|gold_shortlisted_applications	|Shortlisted Applications|
|KPI-003	|gold_total_interviews	|Total Interviews|
|KPI-004	|gold_completed_interviews|	Completed Interviews|
|PI-005	|gold_selected_candidates|	Selected Candidates|
|KPI-006|	gold_accepted_offers	|Accepted Offers|
|KPI-007|	gold_joined_candidates|	Joined Candidates|
|KPI-008|	gold_average_compensation_lpa	|Average Compensation LPA|

---

## 3. Key Decisions
- One KPI = one Gold table was selected to keep the Gold layer simple, clearly traceable, and easy to consume for dashboards and reporting.

- Gold tables are built from Week 6 Trusted Silver data, rather than directly from Candidate or Quarantine data.

- Nested applications and offers arrays from the trusted student data are exploded before calculating application and offer KPIs.

- Interview KPIs are calculated from the trusted interview data.

- COUNT(DISTINCT ...) is used for entity-level KPIs to reduce the impact of repeated nested records.

- Invalid compensation values outside the controlled 0–30 LPA range are excluded from the average compensation calculation.

- Each Gold table contains KPI metadata such as kpi_key, kpi_name, Gold creation timestamp, and Gold schema version.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|
Gold KPIs depend on the correctness of Week 6 Trusted Silver data	|Incorrect Trusted data could affect KPI results	|Continue DQ validation and correct upstream Candidate data when required
Nested applications and offers require careful handling|	Duplicate nested records could affect KPI calculations	|Use distinct business identifiers and validate counts
KPI definitions need to remain consistent across future sprints	|Changes could make historical reporting inconsistent	|Maintain the KPI contract and version the Gold schema
Repeat-run consistency must be verified|	Re-running the Gold pipeline should not create inconsistent results|	Compare baseline and rerun output

---

## 5. Evidence Added to GitHub
- weekly_logs/week07_log.md updated.
- Week 07 Gold design/build notebook updated.
- SQL for all 8 Gold KPI tables added.
- Gold validation queries added.
- KPI output/summary evidence added.
- Screenshots of successful Gold table creation and validation to be added/updated where required.
---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI was used to help structure the Week 7 Gold-layer implementation, suggest KPI definitions, organize the SQL workflow, and review the Gold-table design.|
| What we changed after AI suggestion | We adapted the suggested KPI structure to our PlacementIQ project and selected an 8-table, one-KPI-per-table design instead of directly copying the reference project's Gold implementation. |
| What we verified manually | We manually checked the Trusted Silver table names, nested application/offer structures, KPI filters, table names, SQL logic, and validation queries. |
| What we can explain without AI | We can explain the Silver-to-Gold flow, why Trusted Silver is used, how nested arrays are exploded, how each KPI is calculated, why distinct identifiers are used, and how Gold outputs are validated. |

---

## 7. Next Week Preparation
- Review the completed Gold KPI tables and validation results.
- Perform final repeat-run/reconciliation checks for the Gold layer.
- Prepare dashboard/reporting requirements using the Gold KPIs.
- Document the final Silver → Gold data flow and KPI definitions.
- Organize screenshots and notebook evidence for project submission.
