# Dashboard Insights

**Week:** 9  
**Purpose:** Explain the refined Power BI dashboard, its key insights, Gold data sources, and validation results.

---

## 1. Dashboard Pages

| **Page** | **Purpose** | **Main Visuals** |
|---|---|---|
| **Page 1: Student & Application Analytics** | Provides a high-level view of student applications, branches, application status, outcomes and company applications. | KPI cards, Treemap, Donut chart, Column chart, Bar chart, filters |
| **Page 2: Recruitment & Interview Analytics** | Analyses company recruitment activity, interviews, interview modes, interview results and completed interviews. | KPI cards, Pie chart, Bar charts, Area chart, filters |

### Page 1 — Student & Application Overview

The first page focuses on the overall application and student picture.

Main KPIs:

- Total Applications
- Total Students
- Shortlisted Applications
- Accepted Applications

Main analysis:

- Students by Branch
- Application Status
- Final Application Outcomes
- Applications by Company

Available filters include:

- Application Status
- Branch
- Date Range

---

### Page 2 — Recruitment & Interview Analytics

The second page focuses on recruitment and interview activity.

Main KPIs:

- Total Interviews
- Completed Interviews
- Interviewing Companies
- Selected Candidates

Main analysis:

- Interview Mode Distribution
- Interview Results
- Top Companies by Interviews
- Completed Interviews by Company

Available filters include:

- Date
- Company
- Interview Mode

---

## 2. Key Insights

The following insights are based on the approved Gold outputs and the Power BI dashboard.

### Insight 1 — Application Volume

The dashboard contains approximately **8,000 applications** across the application dataset.

**Source:** `gold_applications` / `gold_total_applications`  
**Measure:** Distinct application count / sum of total applications

---

### Insight 2 — Student Participation

The application data represents approximately **1,500 unique students**.

**Source:** `gold_applications`  
**Measure:** Distinct `student_id`

---

### Insight 3 — Shortlisted Applications

Approximately **7,000 applications** are marked as shortlisted.

**Source:** `gold_short_applications`  
**Measure:** Sum of `shortlisted_applications`

---

### Insight 4 — Accepted Applications

The dashboard shows **634 accepted applications**.

**Source:** `gold_applications`  
**Measure:** Applications where `final_outcome = ACCEPTED`

---

### Insight 5 — Interview Activity

The Gold interview data contains **24,989 total interviews**.

**Source:** `gold_total_interviews`  
**Measure:** Sum of `total_interviews`

---

### Insight 6 — Completed Interviews

The dashboard's Gold source contains **24,461 completed interviews**.

**Source:** `gold_completed_interviews`  
**Measure:** Sum of `completed_interviews`

---

### Insight 7 — Interview Modes

The interview dashboard compares interview activity across the available interview modes, including:

- HYBRID
- ONLINE
- ONSITE

The distribution can be explored using the **Interview Mode Distribution** visual and the Interview Mode filter.

**Source:** `gold_total_interviews`  
**Measure:** Sum of `total_interviews`

---

### Insight 8 — Interview Results

The completed-interview dashboard shows the distribution of interview results, including:

- ADVANCED
- REJECTED
- SELECTED

The **Interview Results** visual allows comparison of completed interviews across these outcomes.

**Source:** `gold_completed_interviews`  
**Measure:** Sum of `completed_interviews`

---

## 3. How the Dashboard Uses Gold Tables

The Power BI dashboard uses the approved Gold outputs only.

| **Dashboard Page** | **Gold Table** | **Important Fields** |
|---|---|---|
| Student & Application Overview | `gold_applications` | `application_id`, `student_id`, `branch`, `application_status`, `final_outcome`, `company_id`, `application_date` |
| Student & Application Overview | `gold_total_applications` | `company_id`, `total_applications` |
| Student & Application Overview | `gold_short_applications` | `company_id`, `shortlisted_applications` |
| Recruitment & Interview Analytics | `gold_total_interviews` | `company_id`, `interview_mode`, `total_interviews` |
| Recruitment & Interview Analytics | `gold_completed_interviews` | `company_id`, `interview_result`, `completed_interviews` |

### Gold-only rule

Power BI does **not** connect directly to:

- Raw datasets
- Bronze tables
- Silver tables

All dashboard visuals are based on the approved Gold outputs and the required dimensional model.

---

## 4. Power BI Validation

The Week 9 dashboard was refined and validated against the approved Gold outputs.

### KPI validation

| **Metric** | **Validated Value** |
|---|---:|
| Total Applications | 8,000 |
| Total Students | 1,500 |
| Shortlisted Applications | 7,000 |
| Accepted Applications | 634 |
| Total Interviews | 24,989 |
| Completed Interviews | 24,461 |

### Validation checks

- [x] Dashboard connects to Gold outputs only.
- [x] Page 1 filters were tested.
- [x] Page 2 filters were tested.
- [x] Date range filtering was tested.
- [x] Company filtering was tested.
- [x] Interview Mode filtering was tested.
- [x] Important KPI totals were reconciled with Gold outputs.
- [x] Dashboard visual titles and layout were refined.
- [x] Final Outcome visual was refined to show actual values rather than 100% for every category.
- [x] Dashboard screenshots are saved in `screenshots/`.
- [x] Dashboard insights are documented in this file.
- [x] Dashboard story is explainable by all students.

---

## 5. Dashboard Story

### Page 1 — Student & Application Overview

This page answers:

> **How many students and applications are involved, where are the students distributed, and what are the application outcomes?**

It provides a high-level view of:

- Application volume
- Student participation
- Branch distribution
- Application status
- Final outcomes
- Company-level application activity

---

### Page 2 — Recruitment & Interview Analytics

This page answers:

> **How active are companies in recruitment, how are interviews conducted, and what are the interview results?**

It provides a deeper view of:

- Interview volume
- Completed interviews
- Interviewing companies
- Interview modes
- Interview results
- Company interview activity

---

## 6. Limitations

The dashboard provides **descriptive analytics** based on the available Gold data.

The dashboard does not establish:

- Why one branch has more applications than another.
- Why a particular company has more interviews.
- Why a candidate received a particular interview result.
- Causal relationships between application and interview outcomes.

Insights should therefore be interpreted as observations from the available data rather than causal conclusions.

---

## 7. Evidence

Week 9 evidence is stored in:

```text
screenshots/
