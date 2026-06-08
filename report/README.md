# Report Package

This folder is ready to upload to Overleaf.

## Files

- `report.tex`: main LaTeX source.
- `report.pdf`: compiled report.
- `output/csv/`: generated CSV tables and LaTeX table fragments.
- `output/img/`: generated PNG figures used by `report.tex`.

## Overleaf

Upload the entire `report/` folder contents while preserving this structure:

```text
report.tex
output/
  csv/
  img/
```

Set `report.tex` as the main file and compile with pdfLaTeX. The source already
points to `output/csv/` for table fragments and to `output/img/` for figures.
