# Walmart Sales Prediction

## Table of Contents
1. [Project Overview](#project-overview)
2. [Directory Structure](#directory-structure)
3. [Dataset Information](#dataset-information)
4. [Data Dictionary](#data-dictionary)
5. [Getting Started](#getting-started)

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