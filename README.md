# Option Pricing: Black-Scholes & Binomial Tree
NIFTY Index Options — NSE India

---

## What this project does

Prices NIFTY index options using Black-Scholes and the CRR Binomial Tree, extracts implied volatility from market prices, constructs the IV smile, and generates relative mispricing signals across strikes.

---

## Data

Live option chain downloaded from NSE India (nseindia.com). Historical volatility computed from 1-year daily NIFTY returns. Risk-free rate: RBI repo rate (~6.5%).

---

## Methodology

- **Black-Scholes**: closed-form European option pricing and Greeks
- **Binomial Tree (CRR, N=200)**: lattice-based pricing, validated against BS
- **Implied Volatility**: extracted via Brent's root-finding method
- **IV Smile**: quadratic fit across strikes to model market's vol surface
- **Mispricing signal**: deviation of each option's IV from the smile — options sitting >1.5pp above the fit are flagged as expensive, below as cheap

---

## Stack

`pandas` · `numpy` · `scipy` · `yfinance` · `matplotlib`

---

## How to run

1. Download NIFTY option chain CSV from nseindia.com
2. Upload to Google Drive and update the file path in Cell 1
3. Run all cells in Google Colab

---

## Future work

- Swap historical vol for GJR-GARCH conditional volatility
- Extend to full IV surface across multiple expiries
- Back-test mispricing signals with delta-hedged P&L simulation
