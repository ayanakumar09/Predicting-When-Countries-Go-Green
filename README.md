# Green Electricity Index Forecasting and Country Clustering

## 1. Overview

This project analyzes global electricity generation to compute the Green Electricity Index (GEI) for over 190 countries. It forecasts each country's green energy progress using machine learning and clustering techniques, aiming to assess alignment with global sustainability targets.

## 2. Components

### Data Processing and Feature Engineering

- **Dataset**: OWID (Our World in Data) Global Energy Dataset
- **Time Frame**: Data from 2002 onwards (due to sparsity before 2002)
- **Focus**: Electricity generation only
- **Energy Categories**:
  - Green sources: Solar, Wind, Hydro, Nuclear, Biofuel, Other Renewables
  - Fossil sources: Coal, Oil, Gas
- **Key Metric**: Green Electricity Index (GEI), calculated as:

  ```
  GEI = Green Electricity / Total Electricity
  ```

- **Preprocessing Steps**:
  - Removal of incomplete data entries
  - Imputation of missing values
  - Correlation analysis and heatmap-based cleaning

### Machine Learning Techniques

#### Random Forest Regression

- Applied for short-term GEI prediction
- Performance:
  - RMSE: 0.0508
  - R² Score: 0.9434
- Not suited for long-term forecasting due to dependency on lag features

#### Linear Regression

- Used to predict GEI values for the year 2030
- Provided interpretable and consistent estimates for cross-country comparison

#### K-Means Clustering

- Clustered countries based on their GEI trends over time
- Input: Standardized GEI time series (country-wise)
- Resulting Clusters:
  - **Cluster 1**: Late-transitioning countries (e.g., US, China, UK)
  - **Cluster 2**: Green energy leaders (e.g., Norway, Canada, Brazil)
  - **Cluster 3**: Slow-transitioning countries (e.g., India, Australia)

## 3. Summary of Analysis

- **2030 Projections**: Several countries are expected to cross the GEI threshold of 0.75 by 2030 or shortly thereafter.
- **Clustering Insights**: Country trends vary widely, revealing geopolitical and developmental disparities in green energy transition.
- **Global Status (2024)**: The global GEI was calculated to be **0.5862**, indicating moderate progress.

## 4. Future Work

- Improve GEI computation by introducing weights or alternative sustainability metrics
- Integrate economic and demographic variables into predictive models
- Identify actionable policy measures for countries based on cluster membership and trend analysis
