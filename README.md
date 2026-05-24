# Road Safety in India (2018–2021) — Policy Analytics

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python&logoColor=white)
![GeoPandas](https://img.shields.io/badge/GeoPandas-Geospatial-green?style=flat)
![Domain](https://img.shields.io/badge/Domain-Public%20Policy%20Analytics-purple?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=flat)

---

## Overview

Exploratory data analysis of road accidents on **state highways across 37 Indian states and UTs from 2018–2021**, sourced from the Ministry of Road Transport & Highways. This project goes beyond trend identification — it surfaces **3 concrete, data-backed policy recommendations** targeting the highest-impact levers for reducing road fatalities.

---

## Key Numbers

| Year | Total Accidents | Change |
|------|----------------|--------|
| 2018 | 1,17,570 | — |
| 2019 | ~1,10,000 | Declining |
| 2020 | 90,755 | **↓ 16.72%** (COVID-19 effect) |
| 2021 | 96,382 | **↑ 6.20%** (partial recovery) |

---

## Top 3 High-Risk States (2021)

| Rank | State | Accidents (2021) |
|------|-------|-----------------|
| 1 | **Tamil Nadu** | 18,656 |
| 2 | **Madhya Pradesh** | 11,475 |
| 3 | **Uttar Pradesh** | 11,096 |

Tamil Nadu leads by a significant margin — nearly **2× Madhya Pradesh**.

---

## Policy Recommendations

### 1. Priority intervention: Tamil Nadu, Madhya Pradesh, Uttar Pradesh
These 3 states account for the highest absolute accident counts on state highways. Targeted enforcement — speed cameras on state highway corridors and stricter traffic policing — would yield the highest per-rupee reduction in accidents nationally.

### 2. Leverage the 2020 lesson
The **16.72% drop in 2020** proves that reduced traffic volume directly cuts accidents. Staggered work hours and off-peak travel incentives in high-risk states could replicate this effect without lockdowns.

### 3. Southern and central regions need geospatial prioritisation
Choropleth mapping shows accident concentration in **southern India (Tamil Nadu, Karnataka, Kerala)** and **central/northern India (MP, UP)**. Region-specific emergency response systems and road infrastructure upgrades should be deployed here first.

---

## Analysis Structure

- **Temporal analysis** — year-on-year national trends (2018–2021)
- **Regional analysis** — top 5 states by accident count, multi-year trends
- **Geospatial visualisation** — choropleth map (GeoPandas + GeoJSON) coloured by 2021 accident density
- **Percentage change analysis** — NumPy pct_change to quantify year-on-year shifts

---

## Data Challenges & Honest Limitations

- Dataset covers **state highways only** — not national highways or urban roads
- No severity, cause, weather, or vehicle-type data — limits causal analysis
- Geospatial naming mismatches (e.g., "Andaman & Nicobar") required manual standardisation
- States with no state highways (Chandigarh, Delhi, Lakshadweep) treated as NaN, not zero

---

## Tech Stack

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `GeoPandas` · `Jupyter`

---

## Data Source

Ministry of Road Transport & Highways — Open Government Data Platform India ([data.gov.in](https://data.gov.in))

---

## Files

```
├── EDA_Road_Accidents.ipynb    ← main analysis notebook
├── INDIA_STATES.geojson        ← state boundary file for choropleth
├── road_accidents_data.csv     ← dataset
└── README.md
```

---

## Author

**Sameera Ali** | [LinkedIn](https://www.linkedin.com/in/sameera-ali-0055252a2/) | [GitHub](https://github.com/alisameera)
