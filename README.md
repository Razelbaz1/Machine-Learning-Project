# Machine-Learning-Project


# Advanced Machine Learning Project - COVID-19 Analysis in Israel

## Project Overview
This project focuses on using advanced machine learning techniques to analyze COVID-19 spread patterns, detect anomalies, classify risk levels, and group similar regions in Israel based on socio-demographic and epidemiological data. The results aim to assist policymakers in designing targeted interventions and improving public health strategies.

## Motivation
The COVID-19 pandemic posed significant challenges to health systems worldwide. This project aims to explore:
1. **Anomaly Detection**: Identifying unusual patterns to prompt immediate responses.
2. **Classification**: Categorizing areas by risk levels to predict and manage outbreak hotspots.
3. **Clustering**: Grouping regions with similar characteristics for tailored policy planning.

## Dataset
The dataset combines daily COVID-19 statistics (2020–2022) from the **Ministry of Health** and **Central Bureau of Statistics (CBS)**. It includes:
- Epidemiological data (e.g., cases, recoveries, hospitalizations, deaths).
- Vaccination rates for first, second, and third doses.
- Demographic and geographic data (e.g., population age groups, urban/rural classification).

Key features include:
- **agas_code**: Statistical region code.
- **style_code**: Town character (e.g., urban/rural, Jewish/Arab).
- **daily_cases**: New daily confirmed cases.
- **accumulated_vaccination_first_dose**: Total vaccinated with the first dose.
- **latitude** and **longitude**: Geographical coordinates for spatial analysis.

## Data Preparation
Steps included:
1. Merging data from different sources using unique region and town codes.
2. Handling missing values and outliers:
   - Replacing missing demographic data with averages or external references.
   - Removing duplicate rows.
3. Creating derived features:
   - Weekly metrics for clearer trends (e.g., `weekly_cases_ratio`).
   - Unique keys for simplified data management.
4. Spatial processing:
   - Adding coordinates for geographical analysis.

## Methodology
### 1. Anomaly Detection
Three approaches were implemented:
- **PCA with t-SNE and Isolation Forest**: Reduced data dimensions while preserving 92% variance.
- **Normalized Data with Isolation Forest**: Focused on precise numerical anomaly detection.
- **PCA with Isolation Forest**: Identified anomalies across entire data structures.

### 2. Classification
- Target variable: **weekly_cases_ratio** (classified into three levels: no cases, low risk, high risk).
- Models tested:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - XGBoost (best performance with an F1 score of 0.89)
  - Neural Networks

### 3. Clustering
Clustering methods used:
- **K-Means and K-Means++**: Optimal clusters determined as K=4.
- **Gaussian Mixture Model**: Selected N=2 for its flexibility in handling overlaps.
- **DBSCAN**: Limited success due to density variations.

## Results
- **Anomalies**: Identified unique socio-demographic and epidemiological patterns, such as significant differences in rural vs. urban areas.
- **Classification**: XGBoost achieved the highest performance for detecting high-risk zones.
- **Clustering**: Revealed distinct groups, such as urban centers with higher vaccination rates and rural regions with older populations.

## Visualization
- Heatmaps to detect correlations.
- Geospatial plots to show disease spread and vaccination coverage.
- Time-series analysis to identify seasonal trends.

## Repository Structure
- `data/`: Raw and processed datasets.
- `info/`: Documentation and explanations about the raw dataset.
- `pics/`: Pre-generated images to prevent unnecessary runtime.
- `plots/`: All graphs and visualizations generated from the code notebooks.
- `README.md`: Project documentation.

## How to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/Razelbaz1/Machine-Learning-Project

## Authors
- **Raz Elbaz**
- **Noa Anaki**

## Acknowledgments
We thank Dr. Chen Hajaj for guidance and support.

## Future Directions
1. Extend analysis to the complete dataset for increased stability.
2. Experiment with advanced models (e.g., GANs, deep neural networks).
3. Integrate external data on family demographics and population density.
4. Enhance model training by increasing the dataset split to 30%.
