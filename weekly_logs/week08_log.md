# Week 08 Log — [Sprint Name]

**Week:** 8  

**Date range:** 21-9-26 to 27-9-26 

**Team:** 16

**Project:** PlacementIQ: Campus Career Analytics

---

## 1. Sprint Goal
The goal of Week 08 was to build and refine the Power BI dashboard using the approved Gold-layer tables. We focused on creating meaningful KPIs, charts, filters, relationships, and dashboard pages to analyze student applications, recruitment, and interview activity

---

## 2. Work Completed

| Task | Owner | Status | Evidence |
|---|---|---|---|
|Task|	Owner	|Status|	Evidence|
|Connected approved Gold-layer tables to Power BI|	Team 16	|Done	|Power BI .pbix file
|Created relationships between dimension and Gold/fact tables	|Team 16|	Done	|Power BI Model view screenshot
|Created application-related measures|	Team 16|	Done|	Power BI measures|
|Created recruitment and interview-related measures	|Team 16	|Done|	Power BI measures|
|Designed Student & Application Overview dashboard	|Team 16|	Done|	Power BI Page 1 screenshot|
|Designed Recruitment & Interview Analytics dashboard|	Team 16|	Done|	Power BI Page 2 screenshot|
|Added slicers and filters	|Team 16|	Done|	Power BI dashboard screenshot|
|Added KPI cards	|Team 16	|Done	|Power BI dashboard screenshot|
|Added charts for branch, application status and outcomes|	Team 16|	Done|	Page 1 screenshot|
|Added interview mode, interview result and company analysis visuals	|Team 16	|Done|	Page 2 screenshot|
|Improved dashboard layout and visual titles	|Team 16	|Done|	Final dashboard screenshots|

---

## 3. Key Decisions

-Used the approved Gold-layer tables as the main source for the Power BI dashboard.
-Created separate dashboard pages for Student & Application Overview and Recruitment & Interview Analytics to avoid repeating the same analysis.
-Used dimension tables such as DimCompany and DimDate for filtering and relationships.
-Created measures for important KPIs instead of manually entering values into visuals.
-Used slicers for date, branch, company, application status, and interview mode where applicable.
-Kept the dashboard focused on meaningful business/recruitment insights instead of adding unnecessary visuals.
-Used appropriate visual types such as cards, bar/column charts, donut charts, funnel charts, and area charts.

---

## 4. Blockers / Risks

| Blocker | Impact | Help Needed |
|---|---|---|

|Understanding the correct Power BI relationships between Gold and dimension tables	|Initially caused confusion while building the data model|	Verified relationship cardinality and filter direction|
|Selecting suitable visualizations for different metrics|	Some initial visuals did not communicate the data clearly	|Refined chart types and titles|
|Some automatically generated Power BI values/titles were unclear	|Reduced dashboard readability|	Manually formatted titles, measures and visuals|
|Need to ensure dashboard values match the Gold-layer data	|Risk of incorrect reporting |Values were checked against the relevant Gold tables|
Understanding how slicers affect different visuals|	Could lead to incorrect interpretation of filtered results|	Tested slicers and dashboard interactions manually|

---

## 5. Evidence Added to GitHub
-Updated Power BI dashboard .pbix file.

-Added screenshot of the Power BI Model view and relationships.

-Added screenshot of Student & Application Overview.

-Added screenshot of Recruitment & Interview Analytics.

-Added screenshots showing slicer/filter interactions.


-Added screenshots of important KPI cards and dashboard visuals.

-Updated dashboard documentation/README.

-Added relevant Week 08 dashboard evidence to the project repository.

---

## 6. AI Transparency Note

| Question | Response |
|---|---|
| Where AI helped | AI was used to provide guidance for Power BI dashboard design, DAX measure creation, relationship setup, chart selection, formatting, and documentation structure. |
| What we changed after AI suggestion | We modified the suggested dashboard layouts, chart types, titles, measures, and visual arrangements based on our actual Gold-layer tables and project requirements. |
| What we verified manually | We manually verified table names, column names, relationships, measure outputs, slicer behavior, chart values, and dashboard results against the available Gold-layer data.|
| What we can explain without AI | We can explain the purpose of the Gold-layer tables, Power BI relationships, KPI measures, slicers, dashboard visuals, filtering behavior, and how the dashboard supports student application and recruitment analysis. |

---

## 7. Next Week Preparation
-Refine the existing Power BI dashboards based on testing and feedback.
-Validate important dashboard KPIs against the corresponding Gold-layer tables.
-Test slicers and filter interactions across both dashboard pages.
-Document important dashboard insights with supporting evidence.
-Improve dashboard formatting, readability, and consistency.
-Prepare the dashboard documentation and screenshots required for the next sprint.
-Prepare for the upcoming Week 09 dashboard validation, reconciliation, and documentation activities.
