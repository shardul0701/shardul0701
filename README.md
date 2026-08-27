<div align="center">
  <img src="assets/banner.svg" alt="Shardul Mehetar — Quant Research Intern · Systematic Equity &amp; Futures" width="100%">
</div>

<div align="center">

[![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)](#)
[![pandas](https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white)](#)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)](#)
[![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat-square&logo=scipy&logoColor=white)](#)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)](#)
[![Parquet](https://img.shields.io/badge/Apache%20Parquet-50ABF1?style=flat-square&logo=apacheparquet&logoColor=white)](#)
[![Polygon.io](https://img.shields.io/badge/Polygon.io-5A31F4?style=flat-square)](#)
[![Alpaca](https://img.shields.io/badge/Alpaca-FFD400?style=flat-square&logoColor=black)](#)

</div>

---

## About

I build **research and execution infrastructure for systematic trading** — the unglamorous
layer that decides whether a backtest is telling you the truth.

Most of my work sits in two places: **point-in-time market data** (so a strategy only ever
sees what was actually knowable on the signal date) and **validation machinery**
(walk-forward, Monte Carlo, cost modelling) that kills strategies before they reach capital.

Currently a **quant research intern**, working across US equities and index futures.

```text
research  →  point-in-time universe  →  signal  →  cost-aware fill  →  walk-forward  →  Monte Carlo  →  paper  →  live
                                                                            ↑
                                                            most ideas die here, on purpose
```

---

## Selected Work

| Repository | What it is |
| :--- | :--- |
| **[SP500-Survivorship-bias-data-2004-2026](https://github.com/shardul0701/SP500-Survivorship-bias-data-2004-2026)** | Point-in-time S&P 500 membership, 2004 → 2026, in canonical YAML. Every addition and removal is dated, so you can reconstruct the exact index on any historical day — including the names that got deleted. Post-2019 changes reconciled against official S&P Global announcements. |
| **[NQ100-Survivorship-bias-data-2004-2026](https://github.com/shardul0701/NQ100-Survivorship-bias-data-2004-2026)** | The same treatment for the Nasdaq-100: yearly membership-change files plus a universe builder that answers *"which tickers were in the index on this date?"* |
| **[Russell-Survivorship-bias-data-2004-2026](https://github.com/shardul0701/Russell-Survivorship-bias-data-2004-2026)** | Russell 3000 and Russell 2000 point-in-time rosters — 46 YAML files spanning 2004 → 2026, built in the same schema as the two above. |
| **[july-backtester](https://github.com/shardul0701/july-backtester)** | Portfolio backtesting engine I work in daily: Monte Carlo robustness scoring, walk-forward analysis, VIX regime heatmaps, √ADV market-impact slippage, and ML-ready trade feature export. |

> The three PIT datasets share one schema on purpose — swap `pit:sp500` for `pit:nq100`
> and the same strategy re-runs on a different survivorship-free universe.

---

## How I Try Not to Fool Myself

Every one of these is a way a backtest lies to you. The right column is what I actually build against it.

| Failure mode | Mitigation |
| :--- | :--- |
| **Survivorship bias** | Point-in-time constituent universes — the backtest only ever sees tickers that were genuinely in the index on the signal date. |
| **Look-ahead** | Signal generated on bar *N*, filled at *N+1* open. `shift(1)` on every regime feature, no exceptions. |
| **Overfitting** | Rolling walk-forward folds plus parameter-sensitivity sweeps — if the edge only exists at one parameter value, it isn't an edge. |
| **Path luck** | Monte Carlo resampling of the trade sequence; block bootstrap when returns are autocorrelated, so win/loss streaks survive the shuffle. |
| **Frictionless fills** | Slippage, per-share commission, √(size/ADV) market impact, and borrow cost debited daily on shorts. |
| **Same-bar ambiguity** | Explicit intrabar resolution when stop and target sit inside one bar — resolving by code order silently inflates results. |

---

## Focus Areas

<table>
<tr>
<td width="33%" valign="top">

**Data Infrastructure**

Point-in-time universes, corporate-action-adjusted price corpora, cross-vendor reconciliation, freshness overlays.

</td>
<td width="33%" valign="top">

**Strategy Research**

Cross-sectional equity momentum and mean reversion, intraday futures breakouts, regime conditioning.

</td>
<td width="33%" valign="top">

**Validation & Execution**

Walk-forward, Monte Carlo, transaction-cost modelling, paper-to-live reconciliation.

</td>
</tr>
</table>

---

<div align="center">

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=shardul0701&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=adbac7&hide=jupyter%20notebook,html,css&langs_count=6" alt="Top languages" height="150">

</div>

---

## Reach Me

[![Email](https://img.shields.io/badge/shardulmehetar07@gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shardulmehetar07@gmail.com)

<sub>Open to conversations about systematic research, market microstructure, and anywhere a backtest is quietly wrong.</sub>
