# Exploratory Data Analysis (EDA) on Road Accidents on State Highways in India (2018–2021)

## Problem Statement
Road traffic accidents remain a significant public health and safety concern in India, contributing to substantial loss of life, injuries, and economic costs annually. Despite efforts to improve road safety, the lack of comprehensive, data-driven insights into accident patterns hinders effective policy-making and resource allocation. The available dataset provides total road accident counts on state highways across Indian states and Union Territories (UTs) from 2018 to 2021. However, without a systematic analysis, it is challenging to identify trends, high-risk regions, and potential factors influencing these accidents. This project aims to address this gap by analyzing the frequency and distribution of road accidents on state highways, providing actionable insights to enhance road safety measures.

## Goals
The primary goals of this project are:

- To analyze the temporal trends in road accident frequency on state highways from 2018 to 2021.
- To identify high-risk states and UTs based on accident counts and rankings in 2021.
- To examine regional variations in accident occurrences across India.
- To visualize key findings using appropriate graphical representations for better interpretability.

## Expected Outcomes
This project will deliver:

- A clear understanding of how road accident frequencies on state highways have evolved over the four-year period (2018–2021).
- Identification of states/UTs with consistently high accident counts, enabling targeted safety interventions.
- Visualizations (e.g., bar charts, line plots, and geospatial maps) to highlight trends and high-risk areas.
- Data-driven insights to inform policymakers and road safety authorities about priority regions and potential focus areas for accident prevention, despite the absence of causal factors in the dataset.

## Dataset Overview
**Source**

The dataset is from the "Road Accidents in India" reports published by the Ministry of Road Transport and Highways, available on the Open Government Data (OGD) Platform India (data.gov.in). 


## Description

The dataset contains the following columns:


- **States/UTs:** Names of Indian states and Union Territories (37 unique entries).
- **Total Number of Road Accidents on State Highways during 2018:** Accident counts for 2018.
- **Total Number of Road Accidents on State Highways during 2019:** Accident counts for 2019.
- **Total Number of Road Accidents on State Highways during 2020:** Accident counts for 2020.
- **Total Number of Road Accidents on State Highways during 2021 - Number:** Accident counts for 2021.
- **Total Number of Road Accidents on State Highways during 2021 - Rank:** Ranking of states/UTs based on 2021 accident counts (1 being the highest).

## Scope and Limitations

**Scope:** The data covers only accidents on state highways, not national highways or other roads, and spans 2018–2021.

**Limitations:** It lacks granularity (e.g., no monthly/daily data, severity, causes, weather, or vehicle details), restricting the analysis to frequency and regional patterns.

# Methodology


This section outlines the systematic approach used to analyze the Indian Traffic Accidents Dataset, focusing on road accidents on state highways from 2018 to 2021. The methodology encompasses data preprocessing, exploratory data analysis (EDA), and visualization, leveraging Python and its libraries to derive insights into accident trends and regional patterns.

### Tools and Libraries

The following Python libraries were utilized for the analysis:

- **Pandas:** For data manipulation, cleaning, and aggregation (e.g., handling missing values, calculating totals).
- **NumPy:** For numerical computations, such as percentage changes in accident counts.
- **Matplotlib:** For creating visualizations, including line plots, bar charts, and choropleth maps.
- **Seaborn:** Although not explicitly used in this project, it can be employed for enhanced visualizations in future iterations.
- **Geopandas:** For geospatial analysis, specifically to load GeoJSON files and create choropleth maps of accident distributions.


### Step-by-Step Process

**Step 1: Data Preprocessing**

**Objective:** To prepare the dataset for analysis by cleaning and structuring the data appropriately.

- **Load the Dataset:** The dataset, containing road accident counts on state highways from 2018 to 2021 across Indian states and Union Territories (UTs), was loaded into a Pandas DataFrame.
- **Handle Missing Values:** Replaced "NA" entries with NaN using Pandas’ replace method, and converted numerical columns to float type for consistency.
- **Address Inconsistent Entries:** Identified states with no state highways (e.g., Chandigarh, Delhi, Lakshadweep) and replaced their zero values with NaN to distinguish between actual zeros and missing data.
- **Rename Columns:** Simplified column names (e.g., from "Total Number of Road Accidents on State Highways during 2018" to "Accidents_2018") for clarity and ease of use in analysis.
- **Libraries Used:** Pandas for data manipulation, NumPy for handling NaN values.


### Step 2: Temporal Trend Analysis

**Objective:** Analyzing the overall trend in road accident frequencies over the years 2018–2021.

- **Calculate Yearly Totals:** Used Pandas to sum the accident counts for each year across all states/UTs, providing a national-level overview.
- **Compute Percentage Changes:** Calculated year-over-year percentage changes in accident totals using Pandas’ pct_change method to quantify the rate of increase or decrease.
- **Visualize Trends:** Plotted a line graph using Matplotlib to illustrate the trend in total accidents, with markers at each year to highlight the 2020 dip (likely due to COVID-19) and 2021 recovery.
- **Libraries Used:** Pandas for calculations, Matplotlib for visualization.


### Step 3: Regional Analysis

**Objective:** To identify high-risk states/UTs and examine their accident trends over time.

- **Identify Top States:** Selected the top 5 states/UTs with the highest accident counts in 2021 using Pandas’ nlargest method, focusing on regional hotspots.
- **Bar Chart Visualization:** Created a bar chart with Matplotlib to compare the 2021 accident counts of the top 5 states, highlighting disparities (e.g., Tamil Nadu’s dominance).
- **Trend Analysis for Top States:** Plotted a multi-line graph using Matplotlib to show the accident trends for these top 5 states from 2018 to 2021, revealing patterns like the 2020 decline.
- **Libraries Used:** Pandas for data selection, Matplotlib for visualization.


### Step 4: Geospatial Visualization

**Objective:** Mapping the spatial distribution of accidents across India to identify regional concentrations.

- **Load GeoJSON File:** Used Geopandas to load a GeoJSON file (INDIA_STATES.geojson) containing the boundaries of Indian states and UTs, with state names in the STNAME column.
- **Standardize State Names:** Standardized state names in both the GeoJSON (STNAME) and dataset (State_UT) by converting to uppercase and replacing " AND " with " & " to ensure matching (e.g., "ANDAMAN & NICOBAR").
- **Merge Data:** Merged the GeoJSON data with the accident dataset using Geopandas’ merge method, linking on the standardized state names.
- **Handle Mismatches:** Identified unmatched states (e.g., "ANDAMAN & NICOBAR") and noted the need for further name standardization if additional mismatches occur.
- **Create Choropleth Map:** Plotted a choropleth map using Geopandas and Matplotlib, coloring states by 2021 accident counts with a red gradient (cmap='Reds'), where darker shades indicate higher accident numbers.
- **Libraries Used:** Geopandas for geospatial data handling, Matplotlib for map visualization.


### Workflow Summary
The methodology follows a structured pipeline: data preprocessing ensures quality input, temporal analysis reveals overarching trends, regional analysis pinpoints high-risk areas, and geospatial visualization provides a spatial perspective. Each step leverages specific libraries to handle data manipulation, numerical computations, and visualizations, ensuring a comprehensive analysis of road accident patterns on state highways in India.


### Overall Results and Interpretation

The Exploratory Data Analysis (EDA) of road accidents on state highways in India from 2018 to 2021 reveals significant temporal and regional patterns, offering insights into accident trends and high-risk areas.

**Key Findings**

- **Temporal Trends:** Total accidents decreased from 117,570 in 2018 to 90,755 in 2020, a 16.72% drop likely due to COVID-19 restrictions, followed by a 6.20% increase to 96,382 in 2021, indicating a partial recovery.
- **Regional Hotspots:** Tamil Nadu (18,656 accidents), Madhya Pradesh (11,475), and Uttar Pradesh (11,096) consistently reported the highest accident counts in 2021, with Tamil Nadu leading by a significant margin.
- **Geospatial Distribution:** Southern (Tamil Nadu, Karnataka, Kerala) and central/northern (Madhya Pradesh, Uttar Pradesh) regions showed higher accident concentrations, as visualized in a choropleth map, with Tamil Nadu being the most affected.
- **Data Challenges:** Naming mismatches (e.g., "Andaman & Nicobar") resulted in missing data on the map, and the dataset’s lack of severity or causal factors limited deeper analysis.

**Interpretation**

- **Impact of External Factors:** The sharp decline in 2020 highlights the influence of reduced mobility during the pandemic, while the 2021 recovery suggests a return to pre-COVID traffic levels, though still below 2018–2019 figures.
- **Persistent High-Risk Areas:** Tamil Nadu, Madhya Pradesh, and Uttar Pradesh emerge as priority regions for road safety interventions, with Tamil Nadu’s consistently high numbers indicating systemic challenges.
- **Regional Disparities:** The concentration of accidents in southern and central/northern India points to regional variations in traffic density, road conditions, or safety enforcement, necessitating targeted measures.
- **Need for Enhanced Data:** The absence of severity, causal factors, and complete geospatial coverage underscores the need for more comprehensive data to inform policy and improve road safety outcomes.


## Implications
The findings from the Exploratory Data Analysis (EDA) of road accidents on state highways in India (2018–2021) provide actionable insights for improving road safety, with implications for policy, infrastructure, and future research.

### Policy and Safety Interventions
- **Targeted Measures in High-Risk States:** Tamil Nadu (18,656 accidents in 2021), Madhya Pradesh (11,475), and Uttar Pradesh (11,096) require urgent safety programs, such as stricter traffic enforcement and awareness campaigns, especially in Tamil Nadu due to its significantly higher accident counts.
- **Regional Focus:** Southern (Tamil Nadu, Karnataka, Kerala) and central/northern (Madhya Pradesh, Uttar Pradesh) regions, identified as hotspots, need prioritized resources, including advanced traffic management and emergency response systems.
- **Leveraging the 2020 Decline:** The 16.72% drop in 2020 suggests that reducing traffic volume (e.g., through staggered work hours or off-peak travel incentives) can lower accidents, a strategy worth piloting in high-risk states.

### Infrastructure and Traffic Management
- **Road Upgrades:** High-risk regions like Tamil Nadu and Madhya Pradesh should prioritize infrastructure improvements, such as road widening, better signage, and speed control measures, to address accident-prone areas.
- **Enhanced Monitoring:** Deploying speed cameras and increasing traffic police presence in hotspot regions can deter unsafe driving, particularly during peak hours.


### Data and Research Improvements
- **Comprehensive Data Collection:** The lack of severity and causal data (e.g., weather, speeding) limits analysis; future datasets should include these factors to enable deeper insights into accident causes.
- **Geospatial Standardization:** Naming mismatches (e.g., Andaman & Nicobar) highlight the need for standardized state names across datasets and GeoJSON files to ensure complete coverage.
- **Causal Analysis:** Future studies should explore factors like road conditions and driver behavior to better understand accident drivers, using advanced methods like regression analysis.

### Broader Impacts
- **Public Health and Economy:** Reducing accidents in high-risk states can lower healthcare costs and economic losses, freeing resources for development.
- **Behavioral Change:** Region-specific safety education (e.g., anti-speeding campaigns in Tamil Nadu) can foster safer driving habits, addressing regional variations.

### Future Directions
- **Pilot Programs:** Test smart traffic systems in high-risk states to evaluate their impact before broader implementation.
- **Stakeholder Collaboration:** Engage local authorities in Tamil Nadu and other hotspots to ensure contextually relevant interventions.


# Conclusion
The implications of this analysis highlight the need for a multi-faceted approach to road safety, combining policy interventions, infrastructure improvements, and enhanced data collection. By focusing on high-risk states and regions, leveraging lessons from the 2020 decline, and addressing data gaps, stakeholders can develop evidence-based strategies to reduce road accidents on state highways, ultimately improving public safety and economic outcomes across India.


# Final Remarks
This EDA serves as a foundational step toward improving road safety on state highways in India. By highlighting high-risk areas and temporal patterns, it lays the groundwork for evidence-based interventions that can save lives and reduce economic losses. Moving forward, collaboration between policymakers, transport authorities, and researchers will be crucial to address the identified gaps, implement targeted safety measures, and monitor their impact. Ultimately, this study underscores the power of data-driven approaches in tackling public safety challenges, paving the way for a safer and more sustainable road network in India.
