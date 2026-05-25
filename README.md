# Capstone-WalmartSales
A comprehensive data science analysis of Walmart's weekly sales across multiple stores, examining correlations with economic indicators and forecasting future sales trends.

# Description
This project analyzes 6,435 records of Walmart weekly sales data spanning multiple stores to identify patterns and relationships with external economic factors (unemployment, consumer price index, and temperature). The analysis includes correlation studies, statistical significance testing, regression modeling, seasonality decomposition, and time-series forecasting.

# Features

Data Cleaning & Preprocessing: Automated handling of missing values with store-specific median imputation
Outlier Detection: IQR-based outlier flagging per store (identifying potential holiday spikes)
Summary Statistics: Per-store sales metrics (mean, median, std, min, max) ranked by performance
Correlation Analysis:

Overall correlation matrix across all variables
Per-store Pearson correlations with p-values for sales vs. unemployment, CPI, and temperature
Heatmap visualization of store-level correlations
Identification of statistically significant relationships (p < 0.05)


Regression Modeling: OLS regression per store controlling for multiple economic variables (unemployment, temperature, CPI, holiday flag)
Seasonality Analysis:

Seasonal decomposition using additive model (52-week period)
Holiday effect testing via t-tests (holiday vs. non-holiday sales comparison)


Time-Series Forecasting: 12-week ahead forecasts per store using Holt-Winters exponential smoothing
Visualization: Correlation heatmaps, time-series plots, seasonal decomposition charts, and forecast trend lines
Summary Export: Aggregated statistics table combining store performance, correlations, and regression results


# Tech Stack

Language: Python 3
Data Processing: pandas, NumPy
Statistical Analysis: SciPy, statsmodels
Visualization: Matplotlib, Seaborn
Time-Series Forecasting: statsmodels (seasonal_decompose, ExponentialSmoothing)
Environment: Jupyter Notebook / Google Colab

# Running the Analysis
Load Dataset: Execute the initial cells to install dependencies and load the Walmart dataset
Data Exploration: Run the data cleaning and inspection sections to understand data structure
Analysis Sections: Execute sections sequentially:
Correlation Analysis (overall and per-store)
Regression Analysis
Seasonality Decomposition
Time-Series Forecasting
View Results: Visualizations and summaries are generated in-notebook
Export Summary: The final cell generates store_summary.csv with aggregated metrics

# Key Outputs Generated

Per-Store Summary Statistics
Top 10 and bottom 10 stores by mean weekly sales
Sales range: ~$209,986 to ~$1,219,638 (mean weekly sales)


Correlation Results
Stores with significant negative unemployment correlation (sales drop when unemployment rises)
CPI correlations identifying price-sensitive stores
Temperature effects on weekly sales patterns


Regression Summary
Per-store OLS coefficients for unemployment, temperature, CPI, and holiday flag effects
R-squared values indicating model fit quality
Significance tests (p-values) for each predictor


Forecasts
12-week ahead sales predictions per store
Visualized as trend lines overlaid on historical data
Confidence intervals from Holt-Winters model
