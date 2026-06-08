# Entropy Market Filter and Portfolio Allocation

Authors: Salvatore Gabriele Messina and Francesco Florio.

This repository contains the clean submission package for an algorithms project in
quantitative finance. The project studies a daily long-only allocation over the
top-10 S&P 500 companies by market capitalization, where the investable universe
changes through time.

The algorithm uses rolling Shannon entropy as a causal market-regime filter. The
regime controls the maximum single-stock weight, then a constrained portfolio is
computed on the active top-10 universe. Every rolling quantity is lagged by one
day, so weights used on a trading day only depend on information available before
that day.

## Repository layout

```text
progetto/
  main.ipynb                    # self-contained notebook submission
  dataset.csv                   # stock-price input data
  sp500_top10_universe.csv      # time-varying top-10 S&P 500 universe
  sp500_total_return.csv        # S&P 500 total-return benchmark
  README.md                     # notebook execution notes

report/
  report.tex                    # LaTeX source ready for Overleaf
  report.pdf                    # compiled report
  output/csv/                   # generated CSV tables and LaTeX table fragments
  output/img/                   # generated figures used by report.tex
  README.md                     # Overleaf compilation notes

requirements.txt                # local Python dependencies
```

## Notebook

Open `progetto/main.ipynb` and run all cells. The notebook does not import or
execute any local `.py` helper file. It only requires the three CSV inputs in the
same directory:

- `dataset.csv`
- `sp500_top10_universe.csv`
- `sp500_total_return.csv`

When run, the notebook writes reproducible outputs to an `output/` directory in
the current working directory.

## Report and Overleaf

The `report/` directory is the package to upload to Overleaf. Keep its internal
folder structure unchanged:

- `report.tex`
- `output/csv/`
- `output/img/`

Set `report.tex` as the main file and compile with pdfLaTeX. The LaTeX source
uses the table fragments in `output/csv/` and the PNG figures in `output/img/`.

## Local environment

For a local run:

```powershell
pip install -r requirements.txt
cd progetto
jupyter notebook main.ipynb
```

In Google Colab, upload `main.ipynb` and the three CSV files to the same working
directory, then run all cells.
