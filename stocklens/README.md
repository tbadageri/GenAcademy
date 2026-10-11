# StockLens

Week 1: Data Analysis with Vibe Coding — Path A, Stock Portfolio Analyzer.

Live app: https://tanmay-stock-lens.coppergrass9.chatgpt.site

## Run locally

No dependencies or build step are needed. From this directory:

```sh
python3 -m http.server 8080
```

Open http://localhost:8080. Import `sample-portfolio.csv`, or explore the built-in illustrative portfolio.

## Features

- CSV import with required-column and nonnegative numeric validation (5 MB maximum).
- Portfolio value, invested capital, unrealized gain/loss, return, and largest position.
- Sector-allocation donut and up to six positions ranked by absolute return.
- Shared search and sector filters; sortable holdings table.
- Sample CSV download, filtered CSV export, and demo reset.

## Dataset and formulas

Columns: `symbol,name,sector,shares,avg_cost,price`.

The five-row sample is synthetic, uses USD, and does not represent real trades or current market prices. Only long positions are supported. Value = shares × price; invested capital = shares × average cost; gain = value − invested capital; return = gain / invested capital × 100. A zero cost basis displays an undefined percentage as an em dash. Metrics reflect the filtered holdings.

CSV data stays in browser memory and resets on reload. The app has no market-data API, database, or portfolio-upload endpoint. Google Fonts is an external styling dependency.

## Files

- `index.html`: dashboard structure and accessible labels.
- `style.css`: responsive visual design.
- `app.js`: CSV parser, validation, metrics, filtering, charts, and downloads.
- `sample-portfolio.csv`: reproducible example dataset.

## Development and verification

Developed with Codex and published using Sites. During publication, the HTML referenced a missing app.js file; Codex implemented the missing behavior before deployment. Node syntax and calculation checks passed. Browser observations confirmed the public overview and AAPL search (value $5,550; invested $4,500; gain $1,050). Full browser regression testing was not performed.

Limitations: supplied-price snapshots only; no dividends, fees, taxes, FX conversion, realized gains, or historical time series. This is an educational prototype, not investment advice.
