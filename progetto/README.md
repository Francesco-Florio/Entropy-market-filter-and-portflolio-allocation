# Notebook Submission

This folder contains the self-contained notebook deliverable.

## Files

- `main.ipynb`: complete project notebook.
- `dataset.csv`: stock-price input data.
- `sp500_top10_universe.csv`: time-varying top-10 S&P 500 universe.
- `sp500_total_return.csv`: S&P 500 total-return benchmark.

## How to run

Open `main.ipynb` from this folder and run all cells.

The notebook does not depend on any local Python script. It reads the three CSV
files listed above from the same directory and creates its outputs under
`output/csv/` and `output/img/` in the working directory.

For a local environment:

```powershell
pip install -r ..\requirements.txt
jupyter notebook main.ipynb
```

For Google Colab, upload `main.ipynb` and the three CSV files together, then run
all cells.
