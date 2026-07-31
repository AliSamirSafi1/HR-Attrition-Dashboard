# HR Analysis Dashboard

A Power BI dashboard built on the IBM HR Employee Attrition dataset, designed around a proper star schema data model rather than a single flat table. It covers who is leaving, why they're leaving, and what it's costing the business.

## Overview

- **1,470 employee records**, cleaned and remodeled from a single flat CSV into a star schema (1 fact table, 4 dimension tables, and a dedicated measures table).
- **24 DAX measures**, organized by category (Core Metrics, Cost & Compensation, Root Cause Analysis, Time Intelligence).
- **4 report pages**: Executive Overview, Demographic Analysis, Root Cause Analysis, and Performance.
- **Custom theme**: two-color palette (navy `#1F3864` / red `#C0392B`), Inter font throughout.

## Data model

Star schema with `Fact_Employees` at the center, joined to:
- `Dim_Department` — Department, JobRole, JobLevel
- `Dim_Demographics` — AgeGroup, Gender, MaritalStatus, Education
- `Dim_Compensation` — SalaryBand, StockOptionLevel
- `Dim_Date` — full calendar, marked as the model's official Date Table

Key data cleaning steps: removed 3 zero-variance columns (`EmployeeCount`, `Over18`, `StandardHours`), normalized inconsistent category labels, added readable text labels for 7 ordinal rating columns, and derived `AgeGroup` / `SalaryBand` (dynamic quartiles) / `TenureGroup` in Power Query. The dataset has no real hire/promotion dates, only durations — `HireDate` and `PromotionDate` are estimated from tenure for trend analysis, not treated as exact.

## Live Dashboard

🔗 [View the interactive dashboard!](https://app.powerbi.com/view?r=eyJrIjoiNTBhYWFlODMtYjYzMy00MmE1LTljMjktYTBiN2FmZTg0Y2Y2IiwidCI6Ijk3YTkyYjA0LTRjODctNDM0MS05YjA4LWQ4MDUxZWY4ZGNlMiIsImMiOjh9&pageName=5fe07233ac08a6216b03)

## Screenshots

### Executive Overview
![Executive Overview](screenshots/executive-overview.jpg)

### Demographic Analysis
![Demographic Analysis](screenshots/demographic-analysis.jpg)

### Root Cause Analysis
![Root Cause Analysis](screenshots/root-cause-analysis.jpb)

### Performance
![Performance](screenshots/performance.job)

## Tech stack

Power BI Desktop — data modeling, Power Query M, DAX.

---

Created by: Ali Safi
[LinkedIn Account](https://www.linkedin.com/in/alisamirsafi1/)
