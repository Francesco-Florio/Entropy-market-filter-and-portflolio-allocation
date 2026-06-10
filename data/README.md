# 🗃️ Input Data

This folder contains the prepared, notebook-ready inputs used by the entropy allocation pipeline. The notebook treats these files as fixed inputs and does not download or reconstruct the original market database.

Return to the [main README](../README.md).

## 📁 Files

### `dataset.csv`

Daily price-index matrix with **6,013 observations** and 36 equity series, plus the S&P 500 benchmark.

| Field | Description |
| --- | --- |
| `Date` | Trading date used as the common time index |
| `SP500` | S&P 500 benchmark price index |
| Equity columns | Prepared price-index series identified by ticker |

The notebook converts these levels into simple daily returns before constructing rolling statistics.

### `top10_dictionary.csv`

Daily causal top-10 universe with **6,013 observations**.

| Field | Description |
| --- | --- |
| `Date` | Allocation date |
| `Top 10 tickers` | Ten active ticker symbols for the date |
| `Top 10 stock indices` | Corresponding zero-based positions in the stock matrix |

This file allows the active universe to change through time without repeated ticker searches inside the daily portfolio loop.

### `ticker_mapping.csv`

Lookup table for the **36 equity series** contained in the price matrix.

| Field | Description |
| --- | --- |
| `Ticker` | Human-readable ticker symbol |
| `StockMatrixIndex` | Zero-based position in the notebook's stock matrix |
| `DatasetColumnIndex` | Original column position in `dataset.csv` |

## 🔄 How the Data Is Used

```text
dataset.csv
    └── daily returns, rolling means, covariance, and entropy

top10_dictionary.csv + ticker_mapping.csv
    └── daily active universe and readable portfolio output
```

## 🧪 Data Notes

- The sample ends on December 31, 2024.
- The notebook uses prepared CSV data only; no HDF5 or proprietary source file is required.
- Missing or invalid numeric observations are handled by the notebook's CSV parsing helpers.
- Universe membership is intended to reflect information available before the corresponding allocation.
