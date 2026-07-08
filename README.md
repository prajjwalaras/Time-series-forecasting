# Time Series Forecasting for Product Demand (Skyrose)

This repository contains a time series forecasting project that models product demand for three product lines:
- Craft Beer
- Whisky
- White Wine

Each product line is analyzed in its own Jupyter notebook:
- `Skyrose_Craft_Beer.ipynb`
- `Skyrose_Whisky.ipynb`
- `Skyrose_White_Wine.ipynb`

## Project Overview

The goal is to forecast monthly product demand using:
- Moving Average
- Exponential Smoothing (SES, Holt, Holt-Winters)
- ARIMA (including auto-ARIMA via `pmdarima`)

Steps performed for each notebook:
1. Data loading & cleaning
2. Exploratory Data Analysis (trend/seasonality/decomposition)
3. Baseline models (moving average)
4. Exponential smoothing models and parameter tuning
5. ARIMA modeling (ACF/PACF, stationarity tests, auto_arima)
6. Model evaluation using MAE, RMSE, MAPE
7. Forecast generation for 2026 and comparison with baseline

## How to run

1. Create a Python environment (recommended: conda or venv).
2. Install dependencies:
```bash
pip install -r requirements.txt
```
3. Launch Jupyter Notebook:
```bash
jupyter notebook
```
4. Open and run the notebooks (`Skyrose_*.ipynb`) in order. Each notebook is self-contained.

## Files
- `Skyrose_Craft_Beer.ipynb`, `Skyrose_Whisky.ipynb`, `Skyrose_White_Wine.ipynb` - analysis notebooks.
- `README.md` - this file.
- `requirements.txt` - Python package requirements.
- `Skyrose_TimeSeries_Report.pdf` - concise project report.

## Notes & Recommendations
- For reproducibility, set a fixed random seed in notebooks where stochastic methods are used.
- Use `pmdarima`'s `auto_arima` with `stepwise=True` for faster model selection on large datasets.
- Validate forecasts using a holdout (e.g., final 12 months) and consider cross-validation (`statsmodels` or `sklearn` utilities).
- Consider deploying models as a simple REST API or scheduled job for continuous forecasting.

