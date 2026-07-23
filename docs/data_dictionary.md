# Data Dictionary

**Week:** 2  
**Purpose:** Define raw, reference, Silver, and streaming fields.

---

## 1. Source File Catalog

| File Name | Grain | Purpose | Approx. Rows | Notes |
|---|---|---|---:|---|
| `students.json` | One row per student | Student master data | Synthetic | Contains nested skills and applications |
| `interviews.parquet` | One row per interview | Interview records | Synthetic | Batch source |
| `companies.csv` | One row per company | Company reference | Synthetic | Reference data |
| `skills.csv` | One row per skill | Sill reference | Synthetic | Reference data |
| `interview_status_event.json` | One row per event | Streaming simulation | Synthetic | JSON event stream |

---

## 2. Raw File Schema: `students.json`

| Field Name      | Data Type     | Required? | Example     | Description           |
| --------------- | ------------- | --------- | ----------- | --------------------- |
| student_id      | STRING        | Yes       | STU0001     | Synthetic student key |
| degree          | STRING        | Yes       | B.Tech      | Student degree        |
| branch          | STRING        | Yes       | CSE         | Student branch        |
| graduation_year | INT           | Yes       | 2027        | Graduation year       |
| cohort          | STRING        | Yes       | C1          | Student cohort        |
| readiness_band  | STRING        | Yes       | Ready       | Placement readiness   |
| eligible_flag   | STRING        | Yes       | Y           | Placement eligibility |
| student_skills  | ARRAY<STRUCT> | Yes       | [...]       | Student skills        |
| applications    | ARRAY<STRUCT> | Yes       | [...]       | Student applications  |
| source_system   | STRING        | Yes       | PlacementIQ | Source label          |


---

## 3. Raw File Schema: `interviews.parquet`

| Field Name       | Data Type | Required? | Example    | Description     |
| ---------------- | --------- | --------- | ---------- | --------------- |
| interview_id     | STRING    | Yes       | INT0001    | Interview ID    |
| application_id   | STRING    | Yes       | APP0001    | Application ID  |
| company_id       | STRING    | Yes       | CMP001     | Company ID      |
| interview_date   | DATE      | Yes       | 2026-07-20 | Interview date  |
| interview_round  | STRING    | Yes       | Technical  | Interview round |
| interview_result | STRING    | Yes       | Selected   | Result          |

---

## 4. Reference File Schema: `companies.csv`

| Field Name   | Data Type | Required? | Example   | Description      |
| ------------ | --------- | --------- | --------- | ---------------- |
| company_id   | STRING    | Yes       | CMP001    | Company ID       |
| company_name | STRING    | Yes       | TCS       | Company name     |
| industry     | STRING    | Yes       | IT        | Industry         |
| location     | STRING    | Yes       | Hyderabad | Company location |

---

## 5. Canonical Silver Table Design

Final Silver table name:

```text
silver_students
```

| Silver Field    | Data Type | Source Mapping           | Business Meaning    |
| --------------- | --------- | ------------------------ | ------------------- |
| student_id      | STRING    | students.student_id      | Student identifier  |
| degree          | STRING    | students.degree          | Degree              |
| branch          | STRING    | students.branch          | Branch              |
| graduation_year | INT       | students.graduation_year | Graduation year     |
| readiness_band  | STRING    | students.readiness_band  | Placement readiness |


---

## 6. Streaming Event Schema

| Field Name      | Data Type | Required? | Example                   | Description    |
| --------------- | --------- | --------- | ------------------------- | -------------- |
| event_id        | STRING    | Yes       | EVT001                    | Event ID       |
| event_timestamp | TIMESTAMP | Yes       | 2026-07-03T10:15:00+05:30 | Event time     |
| event_type      | STRING    | Yes       | INTERVIEW_STATUS_UPDATED  | Event category |

