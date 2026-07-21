# Synthetic Data Assumptions

**Week:** 2  
**Purpose:** Document how educational data is created.

---

## 1. Synthetic Data Boundary

This project uses synthetic educational data only. It must not be presented as real company, customer, citizen, player, patient, government, or platform data.

---

## 2. Domain Assumptions

| Area | Assumption |
|---|---|
| Geography / scope | Hyderabad and nearby engineering colleges |
| Time period | Academic Years 2023–2026 |
| Source systems | Student Information System, Attendance Management System, Placement Portal, and Company Recruitment Records |
| Event types | Student registration, attendance, certification, internship, placement, interview, and offer events |
| Reference data | Departments, companies, job roles, skills, certifications, and academic semesters |

---

## 3. Data Volume Assumptions

| File | Approximate Rows | Reason |
|---|---:|---|
| `students.csv` | 5,000 | Represents student academic records |
| `placements.csv` | 1,800 | Represents placement and offer details |
| `companies.csv` | 120 | Contains company master information |
| `placement_events.json` | 10,000 | Simulates interview, application, and placement event streams |

---

## 4. Controlled Data Quality Issues

| Issue Type | Approx. Share | Why Include It |
|---|---:|---|
| Duplicate IDs | 0.2%–0.5% | Tests uniqueness |
| Missing values | 1%–3% | Tests completeness |
| Invalid reference keys | 0.5%–1% | Tests referential integrity |
| Negative / impossible values | 0.1%–0.5% | Tests range rules |
| Timestamp inconsistencies | 0.1%–0.3% | Tests chronology |

---

## 5. Manual Verification

Before using generated data, the team must check:

- Row counts are realistic for a medium-sized engineering college.
- All required key fields (Student_ID, Company_ID, Placement_ID) are present.
- Dates, CGPA, attendance, package, and numeric values are within realistic ranges.
- Controlled data quality defects exist in small proportions for testing validation rules.
- Source files contain sufficient variation to require data cleaning, standardization, and integration before analytics.
