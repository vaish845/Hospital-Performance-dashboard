# 🏥 Hospital Performance Dashboard

A two-page interactive Power BI report providing a comprehensive overview of hospital operations — covering patient volumes, revenue, doctor performance, departmental trends, and patient demographics.

---

## 📁 File Details

| Property | Value |
|---|---|
| File | `Hospital_Performance_Dashboard1.pbix` |
| Format | Power BI Desktop Report (`.pbix`) |
| Report Version | 1.28 |
| Power BI Version | 2.152.856.0 |
| Created From | Power BI Cloud (Release 2026.03) |
| Theme | Innovate |
| Data Source | Single table — `Cleaned_Data` |

---

## 📊 Report Structure

The report contains **2 pages** and **27 visuals** in total.

---
<img width="1916" height="1015" alt="hospital dashboard" src="https://github.com/user-attachments/assets/4d3e7a8e-b032-4bc7-bfff-114b2e607990" />

<img width="1898" height="978" alt="hospital dashboard1" src="https://github.com/user-attachments/assets/7d3ad167-c120-480b-8121-f83852ec8d99" />


### Page 1 — Hospital Overview

A high-level summary of overall hospital performance across patients, revenue, departments, doctors, and cities.

#### KPI Cards (5)
| Measure | Description |
|---|---|
| Total Patients | Count of all patients |
| Total Revenue | Sum of all revenue generated |
| Avg Treatment Cost | Average cost per treatment |
| Avg Stay | Average patient length of stay |
| Revenue per Patient | Total Revenue ÷ Total Patients |

#### Charts & Visuals

| Visual Type | X-Axis / Category | Y-Axis / Value | Purpose |
|---|---|---|---|
| Donut Chart | Gender | Total Patients | Patient distribution by gender |
| Pie Chart | Room Type | Total Patients | Patient split by room type |
| Clustered Bar Chart | Department | Total Revenue | Revenue contribution by department |
| Clustered Column Chart | Doctor Name | Total Patients | Patient load per doctor |
| Pie Chart | Feedback | Total Patients | Patient satisfaction breakdown |
| Stacked Area Chart | Department | Count of Feedback | Feedback volume by department |
| Clustered Bar Chart | City | Total Patients | Patient geographic distribution |
| Line Chart | Admission Date (Year → Quarter → Month → Day) | Total Patients & Monthly Admissions | Admission trends over time |
| Flow Visual | — | — | Custom visual (process/flow diagram) |

#### Interactivity
- **Page-level filter:** Doctor Name slicer filters all visuals on this page.

---

### Page 2 — Doctor & Departmental Deep Dive

A focused view on doctor-level performance and departmental breakdowns.

#### KPI Cards (4)
| Measure | Description |
|---|---|
| Avg Stay | Average patient length of stay |
| Avg Cost per Doctor | Average treatment cost attributed per doctor |
| Top Doctor by Patients | Doctor with the highest patient count |
| Total Revenue | Total revenue (filtered context) |

#### Charts & Visuals

| Visual Type | X-Axis / Category | Y-Axis / Value | Purpose |
|---|---|---|---|
| Table | Doctor Name | — | Detailed doctor-level data |
| Clustered Bar Chart | Feedback | Total Patients | Patient satisfaction by feedback type |
| Pie Chart | Payment Mode | Total Patients | Split by payment method (cash, insurance, etc.) |
| Clustered Column Chart | Department | Total Patients | Patient volume across departments |
| Donut Chart | Gender | Total Patients | Gender breakdown |
| 100% Stacked Area Chart | — | Total Patients & Sum of Age | Age vs. patient volume composition |

#### Interactivity
- **Page-level filter:** Doctor Name slicer filters all visuals on this page.

---

## 🗂️ Data Model

The report uses a **single flat table** named `Cleaned_Data`.

### Fields Used Across the Report

| Field | Type | Used In |
|---|---|---|
| `Doctor_Name` | Dimension | Page filter, column chart, table |
| `Department` | Dimension | Bar charts, area chart, column chart |
| `Gender` | Dimension | Donut charts |
| `Room_Type` | Dimension | Pie chart |
| `Feedback` | Dimension | Pie chart, bar chart, area chart |
| `City` | Dimension | Bar chart |
| `Payment_Mode` | Dimension | Pie chart |
| `Age` | Measure/Column | 100% stacked area chart |
| `Admission_Date` | Date Hierarchy | Line chart (Year, Quarter, Month, Day) |
| `Total Patients` | Measure | KPI cards, multiple charts |
| `Total Revenue` | Measure | KPI card, bar chart |
| `Avg Treatment Cost` | Measure | KPI card |
| `Avg Stay` | Measure | KPI cards (both pages) |
| `Revenue per Patient` | Measure | KPI card |
| `Monthly Admissions` | Measure | Line chart |
| `Avg Cost per Doctor` | Measure | KPI card (Page 2) |
| `Top Doctor by Patients` | Measure | KPI card (Page 2) |

> All measures are DAX-calculated and derived from the `Cleaned_Data` table.

---

## 🔍 Key Insights Available

- **Patient Volume Trends** — Track daily, monthly, quarterly, and yearly admissions.
- **Revenue Analysis** — Understand which departments and doctors drive the most revenue.
- **Doctor Performance** — Compare patient load, average cost, and stay length by doctor.
- **Patient Demographics** — Gender split, age composition, and city-wise origin of patients.
- **Satisfaction Monitoring** — Feedback distribution across departments and doctors.
- **Room & Payment Analytics** — Room type utilization and payment mode preferences.

---

## 🚀 How to Open

1. Install [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
2. Open Power BI Desktop.
3. Go to **File → Open report → Browse**.
4. Select `Hospital_Performance_Dashboard1.pbix`.
5. Use the **Doctor Name** slicer on either page to filter the entire report.

---

## 🔄 Refreshing Data

The data is embedded directly in the `.pbix` file. To update it:

1. Go to **Home → Transform Data** to open Power Query Editor.
2. Replace or update the source data in the `Cleaned_Data` query.
3. Click **Close & Apply** to reload.
4. Click **Refresh** on the Home ribbon to refresh visuals.

---

## 📋 Requirements

- **Microsoft Power BI Desktop** version 2.152 or later (2026.03 release recommended)
- No external data connections — data is fully embedded in the file.

