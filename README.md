# Walmart Weekly Sales Analytics

A comprehensive data science analysis of Walmart's weekly sales across multiple stores, examining correlations with economic indicators and forecasting future sales trends.

## Description

This project analyzes 6,435 records of Walmart weekly sales data spanning multiple stores to identify patterns and relationships with external economic factors (unemployment, consumer price index, and temperature). The analysis includes correlation studies, statistical significance testing, regression modeling, seasonality decomposition, and time-series forecasting.

## Features

- **Data Cleaning & Preprocessing**: Automated handling of missing values with store-specific median imputation
- **Outlier Detection**: IQR-based outlier flagging per store (identifying potential holiday spikes)
- **Summary Statistics**: Per-store sales metrics (mean, median, std, min, max) ranked by performance
- **Correlation Analysis**:
  - Overall correlation matrix across all variables
  - Per-store Pearson correlations with p-values for sales vs. unemployment, CPI, and temperature
  - Heatmap visualization of store-level correlations
  - Identification of statistically significant relationships (p < 0.05)
- **Regression Modeling**: OLS regression per store controlling for multiple economic variables (unemployment, temperature, CPI, holiday flag)
- **Seasonality Analysis**:
  - Seasonal decomposition using additive model (52-week period)
  - Holiday effect testing via t-tests (holiday vs. non-holiday sales comparison)
- **Time-Series Forecasting**: 12-week ahead forecasts per store using Holt-Winters exponential smoothing
- **Visualization**: Correlation heatmaps, time-series plots, seasonal decomposition charts, and forecast trend lines
- **Summary Export**: Aggregated statistics table combining store performance, correlations, and regression results

## Tech Stack

- **Language**: Python 3
- **Data Processing**: pandas, NumPy
- **Statistical Analysis**: SciPy, statsmodels
- **Visualization**: Matplotlib, Seaborn
- **Time-Series Forecasting**: statsmodels (seasonal_decompose, ExponentialSmoothing)
- **Environment**: Jupyter Notebook / Google Colab

## Installation Instructions

### Prerequisites
- Python 3.7+
- Jupyter Notebook or Google Colab (recommended)

### Running the Analysis

1. **Open the Notebook**: Launch `Capstone_Project__Walmart_.ipynb` in Jupyter or Colab
2. **Load Dataset**: Execute the initial cells to install dependencies and load the Walmart dataset
3. **Data Exploration**: Run the data cleaning and inspection sections to understand data structure
4. **Analysis Sections**: Execute sections sequentially:
   - Correlation Analysis (overall and per-store)
   - Regression Analysis
   - Seasonality Decomposition
   - Time-Series Forecasting
5. **View Results**: Visualizations and summaries are generated in-notebook
6. **Export Summary**: The final cell generates `store_summary.csv` with aggregated metrics


## Example Output / Behavior

### Key Outputs Generated

1. **Per-Store Summary Statistics**
   - Top 10 and bottom 10 stores by mean weekly sales
   - Sales range: ~$209,986 to ~$1,219,638 (mean weekly sales)

2. **Correlation Results**
   - Stores with significant negative unemployment correlation (sales drop when unemployment rises)
   - CPI correlations identifying price-sensitive stores
   - Temperature effects on weekly sales patterns

3. **Regression Summary**
   - Per-store OLS coefficients for unemployment, temperature, CPI, and holiday flag effects
   - R-squared values indicating model fit quality
   - Significance tests (p-values) for each predictor

4. **Forecasts**
   - 12-week ahead sales predictions per store
   - Visualized as trend lines overlaid on historical data
   - Confidence intervals from Holt-Winters model

5. **Artifacts Generated**
   - `store_summary.csv`: Consolidated metrics for all stores
   - Visualization plots: correlation heatmaps, decomposition charts, forecast graphs

## File Structure

```
walmart-sales-analytics/
├── Capstone_Project__Walmart_.ipynb     # Main analysis notebook
└── README.md                            # This file
```

### Dataset Columns

- **Store**: Store identifier (integer)
- **Date**: Sale date (DD-MM-YYYY format, converted to datetime)
- **Weekly_Sales**: Weekly sales in dollars (float)
- **Holiday_Flag**: Binary flag for holiday weeks (0 or 1)
- **Temperature**: Average temperature for the week (Fahrenheit)
- **Fuel_Price**: Fuel price index (float)
- **CPI**: Consumer Price Index (float)
- **Unemployment**: Unemployment rate (percentage)

## Future Improvements

- **Advanced Forecasting**: Implement ARIMA, SARIMA, or Prophet models for comparison
- **Feature Engineering**: Create lagged variables, moving averages, and interaction terms
- **Machine Learning**: Apply random forests, gradient boosting, or neural networks for sales prediction
- **Geographic Analysis**: Cluster stores by region and region-specific insights
- **Real-Time Updates**: Integrate automated data pipelines for continuous analysis
- **Dashboard**: Build interactive Plotly/Dash dashboards for business stakeholder consumption
- **Causal Inference**: Estimate causal effects of interventions beyond observational correlations
- **Anomaly Detection**: Implement isolation forests or other anomaly detection methods for unusual sales patterns

## License

MIT License - See LICENSE file for details

---

**Author**: Yogesh Bahl  
**Course**: EPGC DS AI – BC = 242007_B (Python)  
**Dataset**: Walmart Weekly Sales (6,435 records)  
**Last Updated**: 2026
