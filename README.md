# Guardian Insurance — Road Risk Exploratory Data Analysis

A data analytics case study that uses **exploratory data analysis (EDA)** to identify temporal, geographic, severity, and weather-related patterns in road accidents and translate them into practical insights for insurance risk assessment.

## Project Overview

Road-accident risk is influenced by when and where people drive, environmental conditions, and the severity profile of recorded incidents. This project analyzes a large road-accident dataset to identify patterns that may support **Guardian Insurance** in understanding road-risk exposure and making more informed risk-management decisions.

The workflow covers data understanding, cleaning, time-feature engineering, exploratory analysis, visualization, geographic hotspot analysis, correlation analysis, and business interpretation.

## Business Objective

The analysis is designed to answer practical questions relevant to road-risk and insurance analysis, including:

- When are accidents most frequently recorded?
- Which cities and states contain the highest concentrations of accidents?
- How does accident severity differ between daytime and nighttime?
- Which locations combine high accident frequency with higher average severity?
- What weather conditions are most common when accidents are recorded?
- Are individual weather variables strongly associated with accident severity?
- Where are the major geographic accident hotspots?
- How can these findings support underwriting, pricing, monitoring, and safety initiatives?

## Data Preparation

The notebook performs a structured cleaning workflow before analysis. Fully duplicated rows are removed, and duplicated `Record_ID` values are resolved by retaining the most complete record.

After cleaning, the dataset contains **1,545,679 unique accident records**.

Missingness is also reviewed carefully. Variables with substantial missing values are not removed globally when they are unnecessary for every analysis; instead, missing observations are handled where relevant to a specific visualization or calculation.

Time-related features are derived to support analysis by:

- Year
- Month
- Day of week
- Hour
- Time of day
- Season

## Exploratory Data Analysis

### Accident Severity

Accident severity is strongly concentrated in **Severity 2**, which contains **1,170,029 records**. Severity 3 is the next most common category, while Severity 1 and Severity 4 occur less frequently.

### Trends by Year

Recorded accidents generally increase from 2016 through 2022, with **2022 containing 352,976 records**. The lower count in 2023 should be interpreted cautiously because it may reflect incomplete or uneven dataset coverage rather than a true decline in accidents.

### Monthly & Seasonal Patterns

**December** has the highest number of recorded accidents, followed by November and January, while July has the lowest. At the seasonal level, **winter** records the highest accident frequency, followed by fall.

### Day-of-Week Patterns

Weekdays contain substantially more recorded accidents than weekends. **Friday** has the highest frequency, while Sunday has the lowest.

### Peak Accident Hours

The hourly analysis identifies two important high-frequency periods:

- Morning commute: approximately **7–8 AM**
- Afternoon commute: approximately **4–5 PM**

A day-by-hour heatmap further shows strong weekday peaks around morning and afternoon commuting periods, while weekend accident counts are lower and more evenly distributed.

## Day vs. Night Severity

Most accidents occur during daytime hours, but the most severe accidents represent a larger proportion of nighttime incidents.

- Severity 4 at night: approximately **3.50%**
- Severity 4 during the day: approximately **2.23%**

This indicates an important distinction between **accident frequency** and **accident severity**: nighttime accidents are less frequent overall but proportionally more severe.

## Geographic Risk Patterns

### Leading Cities by Accident Frequency

The cities with the highest recorded accident counts include:

1. **Miami — 35,405**
2. **Houston — 32,426**
3. **Los Angeles — 29,723**

### Leading States

**California** has the highest recorded accident count with **331,378 records**, followed by Florida and Texas.

These totals represent recorded accident concentration and should not be interpreted directly as normalized risk rates because state populations, road networks, traffic exposure, and dataset coverage differ.

### Severity by City

Among the ten cities with the highest accident counts, **Dallas has the highest average severity at 2.26**, followed by Los Angeles at 2.23 and Houston at 2.18.

This reinforces that a location with the highest accident frequency is not necessarily the location with the highest accident severity.

## Accident Hotspots

GPS-based density analysis reveals clear geographic accident hotspots rather than a uniform distribution. High concentrations are visible around major urban and highly populated road networks, particularly across parts of the eastern and southeastern United States, Texas, and coastal California.

These patterns can support more detailed **location-based risk monitoring**, underwriting analysis, and targeted safety initiatives.

## Weather Analysis

Many accidents are recorded during common weather conditions rather than only during severe weather. The most frequent categories include **Fair, Mostly Cloudy, Cloudy, and Clear** conditions, with Fair weather alone accounting for **486,767 records**.

This suggests that road-accident exposure cannot be attributed only to extreme weather conditions; traffic exposure and other contextual factors also matter.

Temperature observations are concentrated mainly between approximately **40°F and 90°F**. Extreme temperatures occur much less frequently in the dataset.

Average accident severity is also very similar across humidity ranges, suggesting that humidity alone has only a weak relationship with severity.

## Correlation Analysis

Most numerical variables show weak linear correlations with accident severity. No single weather or time variable appears to explain severity well on its own.

This highlights the importance of considering road risk as a **multifactor problem** rather than relying on a single environmental feature.

## Key Findings

- The cleaned dataset contains **1,545,679 unique accident records**.
- **Severity 2** is the dominant accident-severity category.
- Accident frequency is highest during **weekday commuting periods**, especially around 7–8 AM and 4–5 PM.
- **Friday** records the highest accident frequency among days of the week.
- **Winter** is the highest-frequency season, and **December** is the highest-frequency month.
- **California** has the largest recorded accident count among states.
- **Miami, Houston, and Los Angeles** lead the city-level frequency ranking.
- Among the top ten cities by frequency, **Dallas has the highest average severity (2.26)**.
- Daytime accidents are more frequent, but **Severity 4 is proportionally higher at night**.
- Many accidents occur under ordinary weather conditions such as Fair, Cloudy, and Clear.
- Individual weather variables show weak linear relationships with accident severity.
- Geographic density analysis identifies distinct accident hotspots that can support location-based risk assessment.

## Business Implications for Guardian Insurance

The findings can support several insurance-related applications:

**Risk-based pricing:** Temporal and geographic patterns can provide additional context when assessing road-risk exposure.

**Location-based underwriting:** High-frequency cities and geographic hotspots can be prioritized for more detailed analysis rather than treating all locations as having equivalent exposure.

**Risk monitoring:** Weekday commute periods and nighttime driving can receive additional attention because they represent different frequency and severity profiles.

**Targeted safety campaigns:** Safety communication can be focused on high-frequency commuting windows, geographic hotspots, and nighttime driving risk.

These findings should be treated as exploratory evidence rather than causal relationships or direct pricing rules.

## Dataset Limitation

The dataset does **not** contain a direct vehicle traffic-speed or speed-limit variable. `Wind_Speed(mph)` represents **wind speed** and must not be interpreted as vehicle speed.

Therefore, the relationship between vehicle speed, speed limits, and accident likelihood cannot be evaluated reliably using the available data.

## Analysis Workflow

```text
Raw Accident Data
       │
       ▼
Data Understanding
       │
       ▼
Data Cleaning & Duplicate Handling
       │
       ▼
Time Feature Engineering
       │
       ▼
Exploratory Data Analysis
       │
       ├── Severity Analysis
       ├── Temporal Patterns
       ├── Day vs. Night Severity
       ├── Cities & States
       ├── Weather Analysis
       ├── Geographic Hotspots
       └── Correlation Analysis
       │
       ▼
Business Insights & Risk Interpretation
```

## Tools & Libraries

- Python
- pandas
- NumPy
- Matplotlib
- Seaborn
- Exploratory Data Analysis (EDA)
- Data cleaning and feature engineering
- Geographic visualization
- Correlation analysis

## Repository Structure

```text
Guardian-Insurance-Road-Risk-EDA/
├── README.md
├── Guardian_Insurance_Road_Risk_EDA.ipynb
└── Case-Study-Dataset.zip
```

## Running the Analysis

1. Clone or download this repository.
2. Extract `Case-Study-Dataset.zip`.
3. Open `Guardian_Insurance_Road_Risk_EDA.ipynb` in Google Colab or Jupyter Notebook.
4. Update the dataset path if necessary.
5. Run the notebook cells in order.

## Author

**Samaher Alsharif**

Data Science | Data Analytics | Machine Learning
