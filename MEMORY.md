# MEMORY.md

NVIDIA (NASDAQ: NVDA) tracking dashboard. Static single page served by
GitHub Pages. This repo is independent of `tempus-dashboard` and
`spacex-dashboard`; keep the three separate (own quote.json, own workflow,
own public link).

## Deployment
- Public link: https://tonytcfu.github.io/nvda-dashboard/
- Source: `index.html` at the `main` branch root, generated from the
  `nvda-dashboard` web artifact (re-export on data updates; do not hand-edit).
- GitHub Pages setting: Deploy from a branch / main / /(root).

## Quote snapshot
- `quote.json` at repo root; refreshed by `.github/workflows/quote.yml`
  (cron `*/15 13-21 * * 1-5` UTC = NYSE 09:30-17:00 ET Mon-Fri, plus manual dispatch).
- Source: Nasdaq official API (`api.nasdaq.com/api/quote/NVDA/info`), real-time.
- Page fallback chain: quote.json -> Nasdaq direct -> Yahoo Finance -> Stooq (nvda.us).
- Format: {"symbol":"NVDA","price":..,"netChange":..,"pctChange":..,"prevClose":..,
  "quoteTime":"YYYY-MM-DD HH:MM","status":"intraday|postmarket|close","source":"Nasdaq"}.

## Data baseline
- Price/financials/short/analyst snapshot: 2026-09-30 close ($228.38, +0.51%).
- Q2 FY2027 earnings (2026-08-26): revenue $96.221B (+106%), Data Center $89.023B
  (+117%), GM 75.0%, GAAP EPS $2.46; Q3 FY2027 guide: revenue $108B ±2%, GM 74.0%.
- Short interest (FINRA 2026-09-15): 294.23M shares, 1.27% of float, 2.6 days to cover.
- Analyst consensus: ~55-59 firms, avg target ~$324-328, median $315 (Oct 2026).
