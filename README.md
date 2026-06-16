# International Debt Analysis (IDA) Dashboard

A Python + Power BI project that cleans and visualizes 50+ years of World Bank **International Debt Statistics (IDS)** data for five economies — **India, China, Pakistan, Nepal, and Bangladesh** — covering external debt, FDI, IMF support, grants, and currency composition of debt from **1970 to 2031**.

> Note on the name: "IDA" here stands for **International Debt Analysis**, the project's own title (as shown in the dashboard headers) — not to be confused with the World Bank's *International Development Association*. The underlying data is the broader IDS dataset, which includes IMF, bilateral, multilateral, and private creditor flows, not just IDA-administered loans.

## About

This was built as a final-year data analytics project. The raw dataset (`WB_IDS_WIDEF.csv`, World Bank IDS, wide format) was cleaned and reshaped using **pandas** in `final_code.ipynb`: dropping non-informative columns, melting the wide year-columns into a tidy long format, renaming fields for clarity, and splitting the result into one CSV per country (India, China, Pakistan, Nepal, Bangladesh).

These cleaned datasets feed **`IDA_Dashboard.pbix`**, an interactive Power BI report with:

- Five **country pages** (India, China, Pakistan, Nepal, Bangladesh), each with KPI cards, a trend-over-time line chart, an indicator-distribution donut chart, an indicator-comparison bar chart, and filter slicers.
- A **Debt Overview page** with a cross-country choropleth map for quick regional comparison.

The dataset spans **101 indicators** — including external debt stocks, FDI net inflows, current account balance, IMF purchases/repurchases, principal repayments, grants, debt forgiveness, and currency composition of public debt (USD, Euro, Yen, SDR, etc.) — broken down across **300+ creditor/counterpart entities** (countries, IMF, World Bank, regional development banks, and more).

## Tech Stack

- **Python (pandas)** — data cleaning, reshaping, and ETL (`final_code.ipynb`)
- **Power BI** — interactive dashboard and visualization (`IDA_Dashboard.pbix`)
- **CSV / World Bank Open Data** — source and per-country output files

## Repository Structure

| File | Description |
|---|---|
| `final_code.ipynb` | Jupyter notebook with the full data cleaning & transformation pipeline |
| `IDA_Dashboard.pbix` | Power BI dashboard file (6 pages) |
| `NEW_IND.csv` | Cleaned India dataset |
| `China.csv` | Cleaned China dataset |
| `Pak.csv` | Cleaned Pakistan dataset |
| `Nep.csv` | Cleaned Nepal dataset |
| `Bang.csv` | Cleaned Bangladesh dataset |

## How to Use

1. Open `IDA_Dashboard.pbix` in **Power BI Desktop** to explore the dashboard directly.
2. To regenerate the data from scratch, place the original `WB_IDS_WIDEF.csv` in the expected path and run `final_code.ipynb` — it will output fresh per-country CSVs.

## Practical Use Cases

The breakdown below is an **illustrative weighting** (not a measured statistic) meant to give a quick sense of who this project is most useful for and why.

- **Academic & Research Reference — ~35%**: A ready-made, tidy long-format dataset and visual reference for students/researchers studying sovereign debt trends or comparing debt burdens across South Asia and China.
- **Policy & Economic Analysis — ~25%**: Useful for understanding debt sustainability, reliance on IMF/multilateral credit, and how external debt has shifted over five decades.
- **Investment & Country-Risk Assessment — ~20%**: FDI inflow trends and external debt levels are commonly used signals in country-risk and market-entry analysis.
- **Public Awareness & Journalism — ~10%**: Makes a dense, technical World Bank dataset accessible through simple visuals instead of raw spreadsheets.
- **Data Analytics Portfolio Demonstration — ~10%**: Shows an end-to-end skill set — Python ETL on a messy wide-format government dataset, followed by BI dashboard design — useful to showcase to recruiters or in a portfolio.

## Data Source

World Bank **International Debt Statistics (IDS)** database.
