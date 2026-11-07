# Harvest — Agricultural Intelligence

A standalone agricultural analytics interface with crop classification results, historical data exploration, batch-level traceability, distributor matching, and seasonal forecast reporting.

## Open the application

- Open `harvest.html` in Chrome or Edge. The landing screen is **Results**, with classification, inventory and buyer-matching outputs.
- Open `seasonal-outlook.html` directly to inspect the seasonal ARIMA series. The forecast page is intentionally not linked from the main navigation.
- No server, Python runtime, or database is needed to use the dashboards. Both pages include their display data internally.

## Files

- `harvest.html`: results, overview, EDA, model evaluation, traceability and records.
- `seasonal-outlook.html`: crop-specific quantity and financial series, forecast estimates and uncertainty ranges.
- `agri_input_data.json`: 5,000 input records, including 2,000 preserved records from `Agriculture_dataset.xlsx` and 3,000 generated records; includes planning-level traceability data.
- `agri_inferenced.json`: classification predictions, evaluation metrics and 12 seasonal ARIMA series.
- `harvest-preview.png` and `forecast-preview.png`: interface screenshots.

## Data and evaluation boundaries

The original source workbook provides 2,000 agricultural observations. The additional 3,000 records were constructed to support a larger illustrative analysis. Farmer IDs, batch dates, stock aging, storage measurements and distributor assignments are generated planning values, not actual tracked shipments.

The classifier attained **94.0%** accuracy on a held-out set of **750 generated extension records**. Accuracy against the original 2,000 workbook labels was **34.2%**. The stronger score must not be presented as a verified field-data result. Model metrics are recorded in `agri_inferenced.json`.

ARIMA series use seasonal crop quantity and recorded sales/investment aggregates for 2020–2024. The next three forecast periods are spring, summer and winter 2025. These are historical out-of-sample projections, not real observed demand or a forward-looking late-2026 forecast.

## Interface details

The results page makes row-level classifications, inventory priorities, buyer scores and per-record information available without leaving the main screen. EDA remains limited to fields from the original source workbook. Forecasting is kept in a separate HTML page.
