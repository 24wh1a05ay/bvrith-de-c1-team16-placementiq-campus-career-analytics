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

## 3. Raw File Schema: `[source_file_2].csv`

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| `source_id` | string | Yes | `SRC2-0001` | Unique source record ID |

---

## 4. Reference File Schema

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| `reference_id` | string | Yes | `REF-001` | Reference key |

---

## 5. Canonical Silver Table Design

Final Silver table name:

```text
silver_[project_specific_table_name]
```

| Silver Field | Data Type | Source Mapping | Business Meaning |
|---|---|---|---|
| `record_id` | string | `[source field]` | Canonical record ID |
| `event_date` | date | `[source field]` | Date used for analytics |
| `[silver_field]` | [type] | [mapping] | [meaning] |

---

## 6. Streaming Event Schema

| Field Name | Data Type | Required? | Example | Description |
|---|---|---|---|---|
| `event_id` | string | Yes | `EVT-0001` | Unique event ID |
| `event_timestamp` | timestamp | Yes | `2026-07-03T10:15:00+05:30` | Event time |
| `event_type` | string | Yes | `[event type]` | Event category |
