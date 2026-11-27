# Does Gold Act as a True Safe Haven During S&P 500 Drawdowns?

**Course:** Advanced Mathematics (Vrije Universiteit Brussel)  
**Author:** Marcell Mayer  
**Live Website:** https://FELHASZNALONEVED.github.io/advanced-math-safe-haven/

## Research Question
Does gold (`GLD`) provide statistically significant positive returns during extreme equity market downturns (`SPY`), and how stable is the linear relationship between the two assets over time?

## Data Source
Daily adjusted closing prices for `SPY` (SPDR S&P 500 ETF Trust) and `GLD` (SPDR Gold Shares) covering **2,739 trading days** (January 2016 – November 2026), retrieved via Yahoo Finance (`yfinance`).

## Analyses & Main Findings
1. **Distribution Check & Regime Hypothesis Testing:** Jarque–Bera tests strongly reject normality for both return series ($p < 0.0001$), confirming heavy-tailed distributions. Partitioning the sample into S&P 500 stress days (worst 5%, $\le -1.69\%$, $n = 137$) and normal days ($n = 2,602$), gold earns a mean daily return of $+0.0288\%$ on stress days vs. $+0.0427\%$ on normal days. Both Welch's $t$-test ($t = -0.1070, p = 0.9150$) and the Mann–Whitney $U$ test ($p = 0.5368$) show no statistically significant difference, indicating that gold acts as a **weak safe haven** (preserving value without surging during crashes).
2. **OLS Regression & 60-Day Rolling Correlation:** Full-sample OLS regression yields $r_{\text{GLD}} = 0.00037 + 0.0893 \cdot r_{\text{SPY}}$ ($r = 0.0954, R^2 = 0.0091, p < 0.0001$), confirming near-zero average sensitivity. However, the 60-day rolling Pearson correlation fluctuates between $-0.626$ and $+0.804$ (mean $0.045$), showing that cross-asset dependence shifts substantially during acute liquidity shocks.

## Repository Structure
- `fetch_data.py` / `fetch_data.ipynb` – Script to download and clean historical closing prices.
- `market_data.csv` – Saved daily closing price dataset for reproducibility.
- `analysis.ipynb` – Python notebook performing statistical tests, OLS regression, rolling correlation, and figure export.
- `fig1_distributions.pdf` & `fig2_regression_correlation.pdf` – High-resolution vector PDF visualisations.
- `fig1_distributions.png` & `fig2_regression_correlation.png` – Web-ready visualisations embedded in the project website.
- `index.html` – Source file for the GitHub Pages project website.
