# Cardiovascular Disease Mortality Analysis and Prediction in Michigan

## Project Overview
This project provides an in-depth analysis of cardiovascular disease (CVD) mortality rates in Michigan from 2009 to 2019, leveraging data from the U.S. Department of Health & Human Services. The primary goals are to identify historical trends, analyze disparities across different demographic groups (race and age), and forecast future mortality rates using time series modeling.

## Table of Contents
1.  [Setup and Data Loading](#setup-and-data-loading)
2.  [Data Preprocessing](#data-preprocessing)
3.  [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
4.  [Time Series Modelling with Prophet](#time-series-modelling-with-prophet)


## 1. Setup and Data Loading
This section initializes essential Python libraries for data manipulation (`pandas`), visualization (`matplotlib`, `seaborn`), and machine learning (`sklearn`). The cardiovascular disease dataset is loaded directly from a CDC API endpoint into a pandas DataFrame.

## 2. Data Preprocessing
Raw data is cleaned and prepared for analysis through several steps:
*   **Column Removal:** Irrelevant columns are dropped to streamline the dataset.
*   **Time Filtering:** Data is filtered to focus on the years 2009-2019.
*   **Missing Value Imputation:** Missing `Data_Value`, `Confidence_limit_Low`, and `Confidence_limit_High` entries are filled using the mean of their respective columns.
*   **Duplicate Handling:** Duplicate rows are identified and removed to ensure data integrity.
*   **Type Conversion:** The `Year` column is converted to a numerical year format for consistent analysis.

## 3. Exploratory Data Analysis (EDA)
Exploratory Data Analysis was conducted to uncover patterns, trends, and disparities in CVD mortality across Michigan. Key research questions addressed include:

### RQ1: Overall Trend of CVD Mortality in Michigan
*What is the trend of Cardiovascular Disease Mortality by mortality over the years (2009-2019) across Michigan?*

**Interpretation:** The analysis reveals a general 5% decline in CVD mortality in Michigan between 2009 and 2019, with a significant drop early on (2009-2012) followed by a more gradual decrease. This suggests positive impacts from public health initiatives, improved healthcare access, and advanced treatments, though factors like rising obesity and socioeconomic disparities may slow further decline.

### RQ2: Race-wise CVD Mortality Trends
*Which race has the highest and lowest cardiovascular disease mortality rates, and how do they compare over time?*

**Interpretation:** White individuals consistently exhibit the highest CVD mortality rates in Michigan, despite a notable decline over the period. Other racial groups, such as American Indian/Alaska Native, Asian/Pacific Islander, and Black (Non-Hispanic) populations, show lower but less consistent declines. This highlights persistent disparities, suggesting a higher CVD burden within the White population, potentially due to demographic factors or prevalence of risk factors.

### RQ3: CVD Mortality by Age Group and Race
*How do cardiovascular disease mortality rates differ by race/ethnicity within each age group (35–64 vs. 65+) in Michigan?*

**Interpretation:** As expected, CVD mortality rates are significantly higher for the 65+ age group across all racial categories. White and 'Overall' categories show the highest rates in the older age group, reinforcing the findings from RQ2. This indicates a critical need for targeted interventions, particularly for Michigan's elderly White population.

### RQ4: CVD Mortality by Race and Specific Disease Topic
*How do Cardiovascular disease mortality rates vary by Race across Michigan, and which type of cardiovascular disease exhibits the highest mortality in each race?*

**Interpretation:** 'Cardiovascular disease (CVD)' (as a general topic) consistently records the highest average mortality rates across all racial groups. White and Black (Non-Hispanic) populations experience higher rates for both 'All heart disease' and 'Cardiovascular disease (CVD)' topics, while Hispanic and Asian/Pacific Islander populations generally show lower mortality rates.

## 4. Time Series Modelling with Prophet
Facebook's Prophet library is utilized to forecast future CVD mortality rates in Michigan.

**Methodology:** The yearly average CVD mortality data for Michigan is normalized and prepared for the Prophet model. The model is configured with yearly seasonality and then fitted to the historical data. A future DataFrame is generated to extend the forecast for the next 10 years.

**Interpretation:** The time series forecast predicts a continued and more significant decline in heart disease mortality rates in Michigan through 2026. This positive outlook suggests that ongoing efforts in public health, healthcare improvements, and lifestyle changes could lead to further reductions in CVD mortality. The forecast includes confidence intervals, indicating the range of uncertainty around these predictions.
