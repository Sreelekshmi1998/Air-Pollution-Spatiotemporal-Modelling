
# Results Summary – Air Pollution Analysis Across India

This document summarizes the results of the project **"Analysis of Air Pollution Across India"**, covering spatial, temporal, and statistical analyses of PM10 pollution.

---

## 1. Data Cleansing and Preprocessing
- Collected daily air pollution data (PM10, SO2, NO2, RSPM/PM10) from the **Central Pollution Control Board (CPCB)** for multiple Indian states (2008–2015).
- Integrated health data from the **Institute for Health Metrics and Evaluation (IHME)** to study the impact on mortality.
- Conducted rigorous data cleaning:
  - Standardized date columns and formats.
  - Handled missing values using NA imputation strategies.
  - Computed monthly and spatial averages per monitoring station.
- Prepared a temporal dataset combining years 2008–2015 and a spatial dataset summarizing monitoring stations for mapping and modeling.

---

## 2. Exploratory Data Analysis (EDA)
- Spatial visualizations revealed **higher PM10 levels in northern states** (e.g., Delhi) and lower levels in southern states (e.g., Kerala).
- Seasonal trends highlighted **winter peaks** in pollution due to limited dispersal and increased emissions.
- Year-on-year comparison (2008–2015) indicated:
  - **Delhi:** Persistent high PM10 levels.
  - **Jammu & Kashmir:** Moderate and relatively stable PM10 levels.
  - **Tamil Nadu:** Gradual decrease in PM10 over the years.
- Figures:
  - **Fig 1:** PM10 distribution in 2009 across India using color-coded dots.
  - **Fig 2:** Bar chart comparing most polluted vs least polluted states.

---

## 3. Spatial Modeling – Bayesian Approach (INLA + SPDE)
- Constructed **Bayesian spatial models** using the **Integrated Nested Laplace Approximation (INLA)** with **SPDE** to model spatial PM10 distribution.
- Developed **triangular meshes** over monitoring locations to capture spatial correlation.
- Predictions generated for grid points across India produced:
  - **Mean PM10 surfaces**
  - **Lower and upper credible intervals (95%)**
- Key insights:
  - **Northern and industrialized regions** had consistently higher pollution.
  - Spatial uncertainty (credible intervals) was higher in regions with **sparser monitoring stations**.
- **Fig 3:** Spatial forecast maps for 2015 – mean, lower, and upper PM10 values.

---

## 4. Temporal Modeling – ARIMA/SARIMA
- Constructed **time-series models** for selected states (Kerala, Delhi, Tamil Nadu, Jammu & Kashmir).
- Applied **STL decomposition** to separate seasonal, trend, and residual components.
- **KPSS and ADF tests** confirmed stationarity requirements.
- **Forecasting 2016 PM10 levels**:
  - Kerala: Seasonal variation captured with SARIMA.
  - Delhi: Persistent high levels with minor seasonal fluctuations.
- **Fig 4:** Forecast for Kerala PM10 in 2016.

---

## 5. Statistical Modeling – Air Pollution vs Health
- Combined PM10 data with **annual mortality counts** per state.
- Applied **linear regression, Poisson and quasi-Poisson GLMs**, and **GAM models**:
  - GAM with Poisson: Tamil Nadu
  - GAM with Quasi-Poisson: Jammu & Kashmir
- Key findings:
  - **Significant positive associations** between PM10 and mortality in some states.
  - In states like Delhi and Kerala, **no clear association** due to limited health data or other confounding factors.
- Models demonstrated **good predictive accuracy** for the test data.

---

## 6. Key Insights
- Pollution levels are **highly variable across geography and time**.
- Northern states experience **chronically higher PM10**, whereas southern states generally show **lower or declining trends**.
- Seasonal peaks suggest **policy interventions** may be particularly effective during winter months.
- Health modeling indicates that **long-term exposure to PM10 is associated with increased mortality** in certain regions, emphasizing the importance of pollution control measures.

---

## 7. Future Scope
- Include **PM2.5 and other pollutants** for a more detailed health impact analysis.
- Integrate **meteorological and socio-economic factors** to improve predictive power.
- Explore **machine learning models** (Random Forest, XGBoost) alongside statistical models.
- Conduct **policy impact evaluation** to quantify effectiveness of interventions.
