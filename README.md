# Kenya Maize Lab

An interactive white-maize price prediction portfolio project by Lucy Akhwale, covering ten Kenyan markets.

## Run locally

No package installation or build is required.

```bash
python -m http.server 8000 --directory dist
```

Open http://localhost:8000. Serve over HTTP because the explorer loads data.json using fetch.

## Features

- Ten-market selector with 24 historical months: November 2024–October 2026.
- Direct 1–3 month forecasts for November 2026–January 2027, originating in October 2026.
- KSh/kg units, unchanged-price baseline, chart data table and downloadable outputs.
- MAE/RMSE comparison, notebook figures, limitations and responsive styling.

## Findings and limitations

Linear Regression did not clearly outperform the unchanged-price baseline. It had slightly lower RMSE but higher MAE at every horizon; no significance test was performed. Forecasts are experimental modeled estimates, not guaranteed prices or live quotes. There are no calibrated prediction intervals. Rainfall, transport costs and supply shocks are not explicit features.

History uses the World Bank modeled close estimate c_maize_fao, not a monthly average or independently verified transaction series. Historical revisions, overlapping targets and related markets limit evaluation. The separately refitted forecasting model has unknown future performance.

## Files

All site files are in dist/: index.html, style.css, app.js, data.json, forecasts.csv, model-card.json, history.png and evaluation.png. The site displays stored model outputs; it does not retrain or execute the Python model. The fitted model binary is not included.

## Updating

Validate a revised model separately, then replace data.json, forecasts.csv and model-card.json. Update the origin, source release and evaluation figures in index.html and app.js together. Notebook/report links currently point to the author's ChatGPT files and require file access; replace with public copies for external reviewers when ready.

## Data source

World Bank, Monthly food price estimates by product and market, Kenya, KEN_2021_RTFP_v02_M, version 2026-10-05: https://microdata.worldbank.org/index.php/catalog/6167

## Hosting

Serve dist/ with a static hosting provider. This upload does not enable GitHub Pages or change the existing Sites audience.
