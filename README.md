# Walmart Sales Prediction

## Table of Contents
1. [Project Overview](#project-overview)
2. [Directory Structure](#directory-structure)
3. [Dataset Information](#dataset-information)
4. [Data Dictionary](#data-dictionary)
5. [Getting Started](#getting-started)
6. [Data Preprocessing](#data-preprocessing)
7. [Exploratory Data Analysis](#exploratory-data-analysis)
8. [Outlier Detection](#outlier-detection)
9. [Feature Engineering](#feature-engineering)
10. [Machine Learning Models](#machine-learning-models)
11. [Model Evaluation](#model-evaluation)
12. [Key Insights](#key-insights)
13. [Visualization Highlights](#visualization-highlights)

## Project Overview
This project focuses on predicting weekly sales for Walmart stores based on historical data. By analyzing various factors such as store location, date, temperature, fuel price, consumer price index (CPI), unemployment rate, and the presence of holidays, the goal is to build a robust model to forecast future sales and help in better decision-making and inventory management.

## Directory Structure
The workspace consists of the following structure:
- `data/`: Contains the datasets used for the analysis.
  - `Walmart.csv`: Main dataset file containing Walmart store historical sales data.
- `reports.ipynb`: Jupyter Notebook containing data exploration, visualization, and modeling reports.
- `README.md`: Project documentation file.

## Dataset Information
The dataset used in this project is `Walmart.csv`. A brief preview of the first 9 data rows is represented below to give a clear idea of the structure:

| Store | Date       | Weekly_Sales | Holiday_Flag | Temperature | Fuel_Price | CPI         | Unemployment |
|-------|------------|--------------|--------------|-------------|------------|-------------|--------------|
| 1     | 05-02-2010 | 1643690.90   | 0            | 42.31       | 2.572      | 211.0963582 | 8.106        |
| 1     | 12-02-2010 | 1641957.44   | 1            | 38.51       | 2.548      | 211.2421698 | 8.106        |
| 1     | 19-02-2010 | 1611968.17   | 0            | 39.93       | 2.514      | 211.2891429 | 8.106        |
| 1     | 26-02-2010 | 1409727.59   | 0            | 46.63       | 2.561      | 211.3196429 | 8.106        |
| 1     | 05-03-2010 | 1554806.68   | 0            | 46.50       | 2.625      | 211.3501429 | 8.106        |
| 1     | 12-03-2010 | 1439541.59   | 0            | 57.79       | 2.667      | 211.3806429 | 8.106        |
| 1     | 19-03-2010 | 1472515.79   | 0            | 54.58       | 2.720      | 211.2156350 | 8.106        |
| 1     | 26-03-2010 | 1404429.92   | 0            | 51.45       | 2.732      | 211.0180424 | 8.106        |
| 1     | 02-04-2010 | 1594968.28   | 0            | 62.27       | 2.719      | 210.8204499 | 7.808        |

## Data Dictionary
- **Store**: The store number.
- **Date**: The week of sales.
- **Weekly_Sales**: Sales for the given store in the given week.
- **Holiday_Flag**: Indicates whether the week is a special holiday week (1 = Holiday week, 0 = Non-holiday week).
- **Temperature**: Average temperature in the region on the day of sale.
- **Fuel_Price**: Cost of fuel in the region.
- **CPI**: Prevailing consumer price index.
- **Unemployment**: Prevailing unemployment rate.

## Getting Started
To get started with this project, ensure you have the required dependencies to run the Jupyter notebook `reports.ipynb`. 
1. Ensure you have Python and Jupyter Server installed along with libraries such as Pandas, NumPy, Matplotlib, Seaborn, and Scikit-learn (commonly used for machine learning predictions).
2. Start the Jupyter Notebook server in the project directory.
3. Open `reports.ipynb` to view the analysis and methodologies applied.

## Data Preprocessing

Several preprocessing steps were performed before model training:

- Converted `Date` column to datetime format
- Checked for missing values — result: **0 missing values** across all 8 columns
- Checked for duplicate records — result: **0 duplicate records**
- Standardized data types (e.g., `Date` converted from `object` to `datetime64[ns]`)
- Created additional time-based features

**Libraries used:** Pandas, NumPy

## Exploratory Data Analysis

Exploratory data analysis (EDA) was conducted to understand the data distribution and identify important patterns.

Key analyses included:

- Distribution of weekly sales
- Sales trends over time
- Store-level performance comparison
- Holiday vs non-holiday sales comparison
- Correlation analysis between variables

EDA helped identify important factors that influence weekly sales and guided feature engineering decisions.

## Outlier Detection

Outliers were detected using the Interquartile Range (IQR) method.

**Formula:**

```
IQR = Q3 - Q1

Lower Bound = Q1 - 1.5 x IQR
Upper Bound = Q3 + 1.5 x IQR
```

Outliers are defined as values that fall outside the lower and upper bounds.

**Columns analyzed for outliers:**

- Weekly_Sales
- Temperature
- Unemployment

Handling outliers improves model stability and prediction accuracy.

## Feature Engineering

To improve model performance, several new features were created:

**Time-based features:**
- Year
- Month
- Week

**Holiday features:**
- Super Bowl (12-Feb-10, 11-Feb-11, 10-Feb-12, 8-Feb-13)
- Labor Day (10-Sep-10, 9-Sep-11, 7-Sep-12, 6-Sep-13)
- Thanksgiving (26-Nov-10, 25-Nov-11, 23-Nov-12, 29-Nov-13)
- Christmas (31-Dec-10, 30-Dec-11, 28-Dec-12, 27-Dec-13)

These features help capture seasonality and holiday effects in retail sales.

## Machine Learning Models

Several machine learning models were implemented and compared:

- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor
- LightGBM Regressor

**Dataset split:**
- Training set: 80%
- Testing set: 20%

**Libraries used:** Scikit-learn, XGBoost, LightGBM

## Model Evaluation

Models were evaluated using the following metrics:

- MAE (Mean Absolute Error)
- MSE (Mean Squared Error)
- RMSE (Root Mean Squared Error)
- R² Score

These metrics measure prediction accuracy and model performance.

**Results:**

| Model            | MSE                   | RMSE       | MAE       | R²   |
|------------------|-----------------------|------------|-----------|------|
| Random Forest    | 14,348,330,151.57     | 119,784.52 | 66,104.58 | 0.95 |
| XGBoost          | 8,307,137,949.20      | 91,143.50  | 55,022.79 | 0.97 |
| Gradient Boosting| 21,475,484,766.16     | 146,545.16 | 75,934.67 | 0.93 |
| LightGBM         | 6,049,848,594.98      | 77,780.77  | 48,437.63 | 0.98 |

**Best performing model:** LightGBM with R² = 0.98, RMSE = 77,780.77, and MAE = 48,437.63.

## Key Insights

Several important insights were discovered during the analysis:

1. **Holiday periods significantly increase sales**  
   Weeks around major holidays show higher sales compared to regular weeks.

2. **Sales vary greatly across stores**  
   Some stores consistently outperform others, indicating location-based demand differences.

3. **Strong seasonal patterns exist**  
   Sales tend to increase towards the end of the year, especially during the holiday season.

4. **Economic indicators have limited impact**  
   Variables such as CPI and unemployment show weaker correlation with weekly sales compared to seasonal effects.

## Visualization Highlights

Important visualizations created in the project include:

- Weekly Sales Distribution
- Sales Trends Over Time
- Holiday vs Non-Holiday Sales Comparison
- Store Sales Ranking
- Feature Importance Analysis
- Correlation Heatmap

These visualizations help illustrate the patterns and relationships in the dataset.