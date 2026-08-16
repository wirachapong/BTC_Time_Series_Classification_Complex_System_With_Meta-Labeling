# BTC Time Series Classification Complex System

A machine learning pipeline for classifying BTC/USDT price direction using hourly time series data. The system compares multiple gradient boosting and time-series-aware models with hyperparameter optimization.

## Overview

- **Task:** Binary classification — predict whether the next day(24 hours) BTC/USDT return is positive or negative
- **Data:** Hourly OHLCV with engineered features e.g. moving average ratios, rolling volatility, z-scores, price acceleration
- **Models:** XGBoost, CatBoost, LightGBM, MiniRocket, HIVECOTE
- **Optimization:** Optuna for hyperparameter search; MLflow for experiment tracking

## Project Structure

```
BTCTimeSeriesClassificationComplexSystem/
  main.ipynb          # End-to-end training and evaluation notebook
  requirements.txt    # Python dependencies
  .gitignore
  src/                # Source modules (reserved)
  reports/            # Saved outputs and figures and the main thesis file
  data/
    README.md         # Data dictionary
    sample.csv        # First 500 rows for quick inspection
```

## Important Notes

**Preprocessing:** Feature engineering and data preprocessing were done in a separate pipeline not included in this repository. The `data/` files are already preprocessed outputs ready for model training. To reproduce from raw OHLCV data, you will need to implement your own preprocessing step that generates the same engineered features (moving average ratios, z-scores, rolling volatility, etc.).

**MLflow:** This notebook logs experiments to an MLflow tracking server. You must configure your own MLflow tracking URI before running. Update the `mlflow.set_tracking_uri(...)` and `mlflow.set_experiment(...)` calls in the notebook to point to your own MLflow instance, or remove them to use the default local `mlruns/` directory.

## Setup

```bash
pip install -r requirements.txt
jupyter notebook main.ipynb
```

## Data

Hourly BTC/USDT data with engineered features including moving average ratios, return windows, rolling volatility, z-scores, and price acceleration. The 1-minute file (`btcusdt_1min_includedma.csv`, 160 MB) is excluded from git — see `data/README.md` for the full data dictionary.

## Key Features

- Meta Labeling
- Stationary and non-stationary feature variants for robustness testing
- Walk-forward validation to prevent lookahead bias
- Optuna-driven hyperparameter tuning with MLflow logging
- Feature Preprocessing, Feature Selection

