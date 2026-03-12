# ⚡ Electric Vehicle Population Analysis — Power BI Dashboard

> An end-to-end Power BI analytics project exploring the adoption, distribution, and efficiency of Battery Electric Vehicles (BEVs) and Plug-in Hybrid Electric Vehicles (PHEVs) across the United States.

---

## 📌 Project Overview

This project delivers a comprehensive interactive Power BI dashboard built on the **Electric Vehicle Population Dataset**. It transforms raw registration data into actionable insights — covering market size, geographic distribution, manufacturer dominance, model-level trends, and incentive eligibility — with multi-page navigation for an intuitive user experience.

---

## 📂 Dataset

| Property | Details |
|---|---|
| **Source** | Electric Vehicle Population Dataset (CSV) |
| **Vehicle Types** | Battery Electric Vehicle (BEV), Plug-in Hybrid Electric Vehicle (PHEV) |
| **Key Fields** | Model Year, Make, Model, Electric Range, Vehicle Location (lat/long), CAFV Eligibility |

---

## 🛠️ Data Cleaning & Transformation (Power Query)

The following transformations were applied before building the dashboard:

### 1. Rename Electric Vehicle Type Values
| Original Value | Renamed To |
|---|---|
| Battery Electric Vehicle (BEV) | Battery Electric Vehicle |
| Plug-in Hybrid Electric Vehicle (PHEV) | Hybrid Electric Vehicle |

### 2. Filter Out Blank Locations
All records where the **Vehicle Location** column is blank were excluded from the entire analysis to ensure geographic accuracy.

### 3. Electric Range Bin (New Calculated Column)
A new categorical column — `Electric Range Bin` — was derived from the numeric Electric Range field:

| Range (Miles) | Bin Label |
|---|---|
| 0 – 100 | Low |
| 101 – 200 | Medium |
| > 200 | High |

### 4. Extract Latitude & Longitude (New Columns)
The `Vehicle Location` column contained coordinates in `POINT (longitude latitude)` format. Two new columns were extracted:

- **`Latitude_location`** — first numeric value (e.g., `-122.34301`)
- **`Longitude_location`** — second numeric value (e.g., `47.659185`)

*Example: `POINT (-122.34301 47.659185)` → Latitude: `-122.34301`, Longitude: `47.659185`*

---

## 📊 KPIs (Key Performance Indicators)

The dashboard header surface exposes four high-level KPIs for at-a-glance market assessment:

| KPI | Purpose |
|---|---|
| **Total Vehicles** | Overall count of all EVs (BEV + PHEV) — measures market size and growth |
| **Average Electric Range** | Mean range (miles) across all EVs — gauges technological advancement |
| **Total BEV Vehicles & % of Total** | Count and share of fully electric vehicles — reveals dominance of pure EVs |
| **Total PHEV Vehicles & % of Total** | Count and share of plug-in hybrids — captures hybrid market presence |

---

## 📈 Dashboard Charts & Visualizations

### 1. Total Vehicles by Model Year *(2011 Onwards)*
Tracks year-over-year EV registrations from 2011 to present. Reveals growth trajectories, adoption acceleration points, and the impact of policy or technology milestones on EV uptake.

### 2. Total Vehicles by State
Geographical heatmap/bar chart showing EV registrations by U.S. state. Highlights regional adoption hotspots and markets with untapped potential.

### 3. Top 10 Vehicles by Make
Ranks the top 10 manufacturers by total registered EVs. Surfaces market leaders and competitive dynamics among automakers.

### 4. Total Vehicles by CAFV Eligibility
Breaks down the fleet by **Clean Alternative Fuel Vehicle (CAFV)** incentive eligibility status. Quantifies how government incentive programs are shaping consumer adoption behavior.

### 5. Top 10 Vehicles by Model
Ranks the top 10 individual EV models by registration count. Reflects consumer preferences and the dominance of specific vehicle configurations in the market.

---

## 🧭 Dashboard Navigation

The report is designed as a **multi-page experience**:

- **Main Dashboard** → contains **2 Navigation Buttons** that route users to secondary detail pages
- **Secondary Pages** → each contains a **"Back" button** that returns the user to the main dashboard

This navigation pattern ensures a seamless, app-like exploration flow without relying on default Power BI page tabs.

---

## 🗂️ Project Structure

```
📁 Electric-Vehicle-Population-Analysis/
│
├── 📄 README.md                         ← You are here
├── 📊 Electric_Vehicle_Dashboard.pbix   ← Power BI report file
└── Electric Vehicle Population Dataset.csv
    
```

---

## 🔑 Key Insights (Summary)

- **BEVs dominate** the EV landscape — the majority of registered vehicles are fully electric, reflecting growing consumer confidence in battery-only range.
- **Washington State** leads significantly in EV registrations, driven by strong state-level incentives and infrastructure investment.
- **Tesla** commands an outsized share of the Top 10 Makes, with multiple models also appearing in the Top 10 Models chart.
- **Post-2018 growth** is exponential — model year trends show a sharp uptick correlating with falling battery costs and expanding model availability.
- A significant portion of vehicles qualify for **CAFV incentives**, suggesting that policy-driven incentives remain a powerful adoption lever.
- The **Average Electric Range** has improved materially over recent model years, reflecting rapid battery technology maturation.

---

## 🧰 Tools & Technologies

| Tool | Usage |
|---|---|
| **Power BI Desktop** | Dashboard development, DAX measures, Power Query transformations |
| **Power Query (M)** | Data cleaning, column derivation, type casting |
| **DAX** | KPI calculations, percentage metrics, conditional logic |
| **CSV** | Source data format |

---

## 🚀 How to Run

1. Clone or download this repository.
2. Open `Electric_Vehicle_Dashboard.pbix` in **Power BI Desktop**.
3. If prompted, update the data source path to point to the local `data/` folder.
4. Click **Refresh** to reload the dataset.
5. Explore the dashboard using the navigation buttons on the main page.

---

## 👤 Author

Built as part of a Power BI analytics assignment focusing on real-world EV population data. All design decisions, transformations, and visual layouts reflect independent analytical judgment — the sample Tableau reference was used only for conceptual inspiration, not replication.

---

*Feel free to fork this project, raise issues, or suggest improvements via Pull Requests.*
