# AQI Index Analysis using Power BI

## Project Overview

**Project Title:** AQI Index Analysis

**Tool Used:** Power BI Desktop

**Data Source:** Day-wise Air Quality Index dataset (state, area/city, AQI value, AQI category, prominent pollutants)

This project demonstrates data visualization and geo-analytical dashboarding skills used by Data Analysts to monitor air quality trends across Indian states and cities. It replicates a real-world environmental monitoring scenario — tracking AQI severity, pollutant composition, and city-wise/state-wise air quality patterns on a single interactive Power BI page.

![AQI_index_project](A-PBI- AQI Index Analysis.png

The project covers the complete BI workflow: data modeling with a dedicated date table, DAX measure creation for dynamic titles and KPIs, and an interactive single-page dashboard with cascading Year / State / Area filters.

## Objectives

**Data Modeling**
Build a relational model with a fact table (`day_wise_aqi_data`) containing state, area, AQI value, AQI category, and prominent pollutants, linked to a `Calendar_Table` date dimension for time intelligence.

**KPI Design**
Surface headline air quality metrics for a selected state — current average AQI, maximum AQI recorded, primary pollutant, and AQI category — using dynamic DAX measures.

**Geo-Spatial Analysis**
Plot AQI readings across India on a bubble map, sized by average AQI and color-coded by severity category, to spot regional pollution hotspots at a glance.

**Trend Analysis**
Track how AQI moves over time (by year and month) using a dedicated date hierarchy, to identify seasonal pollution spikes.

**Business Analysis**
Answer real-world questions around which cities/areas have the worst air quality, how AQI severity is distributed, and which pollutants occur most frequently (individually or in combination).

## Data Model

| Table | Key Fields |
|---|---|
| `day_wise_aqi_data` (fact table) | `state`, `area`, `aqi_value`, `AQI_Category`, `prominent_pollutants` |
| `Calendar_Table` (date dimension) | `Date` (with Year / Month / Day hierarchy) |
| `All_Measure` (measures table) | `Avg_AQI`, `Primary_Pollutant`, `AQI_Category_KPI`, `Count_Of_Rows`, plus dynamic title measures (`KPI-Title`, `State_Map_Title`, `AQI_Level_Title`, `Title_For_Monthly_Charts`, `Title_for_city`, `Donut_Title`, `Pollutant_Title`, `Label`) |

*(Field and measure names above are taken directly from the report's data model — paste your exact DAX formula bodies from the Power BI measure pane if you want them documented here too.)*

## Dashboard Structure

### Page: AQI Index Analysis

**Global Filters**
- Year (e.g. 2025)
- State (e.g. Delhi)
- Area (e.g. All)

**Headline KPI Panel (selected state)**
- Gauge chart — current Average AQI for the selected state (e.g. Delhi: **208**)
- Max AQI recorded (e.g. **397**)
- Primary Pollutant (e.g. **PM2.5**)
- AQI Category (e.g. **Very Unhealthy**)

**AQI by State (Bubble Map)**
A bubble map of India plotting monitoring locations, bubble size driven by Average AQI and color-coded by AQI severity category, for spotting regional pollution hotspots.

**AQI_Level (Reference Legend)**
A color-coded severity legend used across the report:
- Good: 50–100
- Moderate: 101–150
- Poor: 151–200
- Unhealthy: 201–250
- Very Unhealthy: 251–300
- Hazardous: > 301

**AQI Trend**
An area chart showing Average AQI over time (day-level, from the `Calendar_Table` date hierarchy), with independent Year and Month slicers (e.g. Year 2025, Month March) for drilling into a specific period.

**AQI by City**
A bar chart ranking areas/cities by Average AQI, e.g.:

| City/Area | AQI |
|---|---|
| Delhi | 208 |
| Hajipur | 197 |
| Gurugram | 190 |
| Panchkula | 185 |
| Rohtak | 178 |
| Charkhi Dadri | 175 |
| Ghaziabad | 174 |
| Baghpat | 166 |
| Patna | 162 |
| Baddi | 159 |

**AQI Level Distribution**
A donut chart breaking down the number of days/records falling into each AQI category (Moderate, Poor, Unhealthy, Very Unhealthy, Hazardous), shown with both count and percentage of total.

**Pollutant Occurrence Frequency**
A clustered bar chart counting how often each pollutant (or combination of pollutants) was recorded as the prominent pollutant, e.g.:

| Pollutant(s) | Occurrences |
|---|---|
| PM2.5 | 38 |
| O3 | 32 |
| PM2.5, PM10 | 30 |
| PM10 | 24 |
| PM10, O3 | 22 |
| O3, PM2.5, PM10 | 11 |
| PM2.5, O3 | 9 |
| PM10, CO | 1 |
| PM10, NO2, O3 | 1 |

## Findings

- **State-level severity** — Delhi shows an average AQI of 208 ("Very Unhealthy") with a recorded maximum of 397, and PM2.5 as the dominant pollutant — consistent with vehicular/industrial pollution patterns typical of North Indian metros.
- **City comparison** — Among the top monitored areas, AQI values cluster tightly in the 150–210 range (Delhi through Baddi), indicating a broader regional pollution problem rather than a single-city anomaly.
- **Pollutant mix** — PM2.5 alone is the single most frequent prominent pollutant (38 occurrences), followed closely by O3 (32) — but a large share of days show *combined* pollutant readings (e.g. PM2.5+PM10, PM10+O3), suggesting multiple pollution sources overlapping rather than one dominant cause.
- **Severity distribution** — The AQI Level Distribution donut shows the bulk of records falling into "Unhealthy" and "Moderate" bands, with a smaller but non-trivial share reaching "Very Unhealthy" — useful for prioritizing which regions need intervention first.
- **Time-based drilldown** — The Year/Month-filtered trend chart allows spotting seasonal spikes (e.g. winter months typically showing elevated AQI in North Indian cities), supporting policy/timing-based analysis.

## Skills Demonstrated

✔ Data Modeling (fact table + date dimension)
✔ DAX Measures (dynamic titles, KPI aggregations, category-based metrics)
✔ Geo-Spatial Visualization (bubble map)
✔ Time Intelligence & Date Hierarchies
✔ Cascading Slicers (Year, State, Area, Month)
✔ Categorical Segmentation (AQI severity bands)
✔ Dashboard Storytelling & Dark-Theme Layout Design

## Conclusion

This project strengthened practical Power BI skills in geo-spatial visualization, dynamic KPI design, and building a single-page environmental monitoring dashboard that supports both macro (state/national) and micro (city/day-level) analysis.

The insights generated can support decision-making around pollution hotspot identification, seasonal policy planning, and pollutant-source prioritization.

## How To Use

1. Download or clone this repository.
2. Open `AQI_Index_Project.pbix` in Power BI Desktop.
3. If prompted, update the data source path to point to your AQI dataset on your local machine.
4. Refresh the data model.
5. Explore the dashboard using the Year, State, Area, and Month filters.

## Author

**Anand Kumar**
MIS Executive | Data Analytics| 

PostgreSQL | DAX | Power BI | Power Query | Power Pivot |

This project is part of my Data Analytics portfolio showcasing Power BI dashboarding skills required for Data Analyst roles.

Feel free to connect, provide feedback, or collaborate on future projects.
