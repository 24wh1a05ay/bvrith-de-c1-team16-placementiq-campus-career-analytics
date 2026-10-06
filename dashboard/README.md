# Power BI Dashboard Folder

The final Power BI dashboard contains two refined report pages built using the approved Gold outputs only.

## Dashboard Pages

### Page 1 — Student & Application Analytics

Purpose:
- Provide an overview of student applications and outcomes.
- Show application volume, student distribution, shortlisting and acceptance.
- Allow users to explore the dashboard using filters and date range selection.

Main visuals:
- Total Applications
- Total Students
- Shortlisted Applications
- Accepted Applications
- Students by Branch
- Application Status
- Final Application Outcomes
- Top Companies by Applications

Filters:
- Application Status
- Branch
- Date Range

---

### Page 2 — Recruitment & Interview Analytics

Purpose:
- Analyse company recruitment and interview activity.
- Show interview volume, completion, interview modes and interview results.
- Provide company-level recruitment comparisons.

Main visuals:
- Total Interviews
- Completed Interviews
- Interviewing Companies
- Selected Candidates
- Interview Mode Distribution
- Interview Results
- Top Companies by Interviews
- Completed Interviews by Company
- Company Interview Summary

Filters:
- Date
- Company
- Interview Mode

---

## Gold Source Register

Power BI connects only to approved Gold outputs.

Gold sources used:

- `Gold_CompletedInterviews.csv` — application-level Gold output
- `Gold_Interviews.csv` — interviews by company and interview mode
- `Gold_Shortlisted.csv` — shortlisted applications by company
- `Gold_TotalApplications.csv` — total applications by company
- `FactApplications.csv` — completed interviews by company and interview result

No raw, Bronze or Silver datasets are connected directly to Power BI.

---

## Data Model

The dashboard uses a dimensional model with `DimCompany` and `DimDate`.

### Company relationships

```text
DimCompany
    |
    | 1 : *
    |
    +---- FactApplications
    |
    +---- Gold_TotalApplications
    |
    +---- Gold_Shortlisted
    |
    +---- Gold_Interviews
    |
    +---- Gold_CompletedInterviews
