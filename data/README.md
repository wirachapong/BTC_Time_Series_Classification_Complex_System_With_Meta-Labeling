# Data

## Files

| File | Rows | Size | Description |
|------|------|------|-------------|
| `btcusdt_1h_includedfeatures_nonstationary.csv` | 33,721 | 6.1 MB | Hourly BTC/USDT OHLCV with engineered features (non-stationary) |
| `btcusdt_1hour_includedfeatures_stationary.csv` | 31,446 | 5.5 MB | Hourly BTC/USDT OHLCV with engineered features (stationary) |
| `btcusdt_1min_includedma.csv` | 2,058,573 | 160 MB | 1-minute BTC/USDT with moving averages — **not tracked by git** |
| `sample.csv` | 500 | 88 KB | First 500 rows of `btcusdt_1h_includedfeatures_nonstationary.csv` |

## Columns (hourly files)

| Column | Description |
|--------|-------------|
| `price` | BTC/USDT close price |
| `ma7_25h` | Moving average ratio (7h / 25h) |
| `ma25_99h` | Moving average ratio (25h / 99h) |
| `ma7d_25d` | Moving average ratio (7d / 25d) |
| `ret_1h` | 1-hour return |
| `ret_3h` | 3-hour return |
| `vol_12h` | 12-hour rolling volatility |
| `zscore_24h` | 24-hour z-score of price |
| `accel_3h` | 3-hour price acceleration |

## Notes

- The actual data file was excluded from git via `.gitignore`.
- `sample.csv` is provided for quick inspection and CI use.
