# Data Quality Summary

**Week:** 2


**Purpose:** Summarize data quality rules, failures and business impact.

---

## 1. Quality Rule Results

| Rule ID | Rule Name | Severity | Passed Count | Failed Count | Business Impact |
|---|---|---|---:|---:|---|
| DQ-01 | Required ID not null | High | 5000 | 0 | Records without IDs cannot be trusted |
| DQ-02 | Duplicate key check | High | 4995 | 5 | Duplicate keys distort placement metrics and reports |
| DQ-03 | Valid reference key | Medium | 4988 | 12 | Invalid references affect joins between student and placement data |
| DQ-04 | Valid timestamp order | Medium | 4992 | 8 | Incorrect timestamps affect trend analysis and time-based dashboards |


## 2. Failed Record Examples

| Rule ID | Sample Record ID | Failure Reason | Action / Handling |
|---|---|---|---|
| DQ-02 | STU1045 | Duplicate Student_ID found | Duplicate record removed |
| DQ-03 | STU2178 | Invalid Company_ID reference | Record flagged for correction |
| DQ-04 | STU3890 | Placement date earlier than interview date | Timestamp corrected |

---

## 3. What Should Block Gold Metrics?

List rules that should block or flag Gold table generation.
The following rules should block Gold table generation:

- **DQ-01:** Records with missing Student IDs must be rejected because primary keys are mandatory.
- **DQ-02:** Duplicate Student IDs should block Gold metrics to avoid double-counting placements.
- **DQ-03:** Invalid reference keys should be flagged until corrected because they break joins between datasets.

---

## 4. Quality Summary

Write 5–8 lines explaining the overall health of the dataset.

The PlacementIQ dataset is in good overall condition and is suitable for analytics after applying data quality checks. Most records successfully passed all validation rules. The highest number of failures occurred in the reference key validation rule due to invalid company references. Duplicate records were identified and removed to ensure accurate placement statistics. Timestamp inconsistencies were corrected before loading the Gold layer. Records with critical issues were either fixed or excluded from reporting. The mentor should carefully review duplicate detection, reference key validation, and timestamp consistency before approving the final dataset.
