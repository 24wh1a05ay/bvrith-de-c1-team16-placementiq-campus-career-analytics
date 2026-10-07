# Structured Streaming Design

**Week:** 10  
**Project:** PlacementIQ — Campus Career Analytics  
**Purpose:** Explain the SQL-first Structured Streaming simulation using Databricks Auto Loader.

---

## 1. Streaming Scenario

The PlacementIQ streaming simulation demonstrates incremental arrival and processing of recruitment application events.

Synthetic PlacementIQ application JSON files are placed into a source folder. Individual event drops are then copied into a streaming landing folder. Databricks Auto Loader detects the newly arriving JSON files and Structured Streaming processes them incrementally.

The processed records are written to the Streaming Bronze table:

`bronze_placementiq_application_events_stream`

The notebook uses an `AvailableNow` trigger so that all files available at the time of execution are processed and the streaming query then stops. This makes the streaming simulation reproducible and suitable for a weekly project demonstration.

### Event Flow

```text
PlacementIQ Application JSON Drops
                ↓
        week09_source/
                ↓
        week09_landing/
                ↓
          Auto Loader
                ↓
      Structured Streaming
                ↓
bronze_placementiq_application_events_stream
                ↓
       SQL Validation
                ↓
 Recruitment Metrics / Power BI
