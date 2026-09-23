# DSE Backtest Terminal — Dhaka Stock Exchange Backtesting Dashboard
#dse-backtest-terminal

An interactive, browser-based backtesting dashboard for the Dhaka Stock Exchange (DSE) — by Ow1nomics

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg) ![Static](https://img.shields.io/badge/backend-none%2C%20fully%20client--side-4fd39a.svg)

If you are looking for a **DSE backtesting tool**, a **Dhaka Stock Exchange portfolio simulator**, or a **Bangladesh stock market efficient-frontier calculator**, this is built for exactly that use case. It runs entirely in the browser — no server, no signup, no API key — on real historical price data from [KnightBase-DB](https://github.com/o-rnob/Knightbase-DB), Bangladesh's largest open-source DSE price dataset.

## What this is

A single self-contained HTML page that lets you:

- Build an equal-weight portfolio from 15 liquid DSE tickers (ACI, BXPHARMA, SQURPHARMA, ISLAMIBANK, BATASHOE, and more) over any date window the underlying data supports
- See live backtest metrics — total return, CAGR, annualized volatility, Sharpe ratio, max drawdown — computed client-side, instantly, with no server round-trip
- Compare the portfolio against a DSEX benchmark proxy
- Explore a 2,000-portfolio Monte Carlo efficient frontier for the selected tickers and window
- Read the data-quality log behind the numbers, instead of trusting a black box

## Why it's built this way

This project follows the same rule as its parent database: **every skip, every gap, and every known limitation is surfaced, not hidden.** Specifically, this dashboard is upfront that:

- ~99.5% of KnightBase-DB's price rows are **unadjusted** for stock splits and dividends — so backtest returns here are price-return only, not true total return
- There is a real, ~3.5-year **blackout in DSE price coverage (Jan 2021 → Aug 2024)** in the source data — the dashboard does not interpolate across it; any date window spanning that gap will simply show fewer usable weeks
- The DSE index tables' `close` column was found to be entirely empty during this build — the dashboard uses the daily `high` value as a labeled proxy instead of silently substituting it

## Live demo

Enable GitHub Pages on this repo (see below) to get a live link, then put it here.

## Running it locally

No build step, no dependencies to install. Download `index.html` and open it in any browser, or serve the folder with any static file server:

```bash
python3 -m http.server 8000
```

## Data source

Built on [KnightBase-DB](https://github.com/o-rnob/Knightbase-DB) — 2,566,157 price rows, 1999–2026, Dhaka Stock Exchange. See that repository for full schema documentation, sourcing, and the complete data-quality log.

## License

MIT — see [LICENSE](LICENSE). The dashboard code is original; the underlying price data follows KnightBase-DB's own sourcing and terms.

## Citation

```
Ornob, K. M. Miad Hassan (Ow1nomics). (2026). DSE Backtest Terminal: An
Open-Source Backtesting Dashboard for the Dhaka Stock Exchange.
https://github.com/o-rnob/dse-backtest-terminal
```

## About the builder

Built by **K M Miad Hassan Ornob** — [Ow1nomics](https://instagram.com/ow1nomics) — BBA Finance, University of Liberal Arts Bangladesh (ULAB). Quantitative finance, data engineering, and DSE market research.

- GitHub: [github.com/o-rnob](https://github.com/o-rnob) — parent project: [KnightBase-DB](https://github.com/o-rnob/Knightbase-DB)
- LinkedIn: [linkedin.com/in/ow1xrd](https://linkedin.com/in/ow1xrd)
- ResearchGate: [K-M-Miad-Hassan-Ornob](https://www.researchgate.net/profile/K-M-Miad-Hassan-Ornob)
- DataCamp Portfolio: [datacamp.com/portfolio/o-rnob](https://www.datacamp.com/portfolio/o-rnob)
- Email: kmmiadhassanornob@gmail.com
